---
title: 管理由 UE-V 2. x 的系統管理備份和還原
description: 管理由 UE-V 2. x 的系統管理備份和還原
author: dansimp
ms.assetid: 2eb5ae75-65e5-4afc-adb6-4e83cf4364ae
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 11c168b54b71731c51417b2b7c4737c85f42035a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812326"
---
# 管理由 UE-V 2. x 的系統管理備份和還原


如果您是 Microsoft 使用者體驗虛擬化（UE-V）2.0、2.1 或 2.1 SP1 的管理員，您可以將應用程式和 Windows 設定還原至其原始狀態。 此外，UE-V 2.1 中的新功能，您也可以在使用者採用新的裝置時還原其他設定。

## 當使用者採用新的裝置時，在 UE-V 2.1 或 UE-V 2.1 SP1 中還原設定


若要在使用者採用新的裝置時還原設定，您可以使用 UevTemplateProfile PowerShell Cmdlet，將 [設定位置] 範本放在**備份**或**漫遊（預設）** 設定檔中。 這可讓電腦設定與新電腦同步處理，以及使用者設定。 系統會針對該裝置備份指派給備份設定檔的範本，並針對每個裝置進行設定。 若要備份範本的設定，請在 Windows PowerShell 中使用下列 Cmdlet：

``` syntax
Set-UevTemplateProfile -ID <TemplateID> -Profile <backup>
```

-   &lt;TemplateID &gt; 是 Ue-v 範本識別碼

-   &lt;備份 &gt; 可以是 [備份] 或 [漫遊]

如果使用者的網域、使用者名稱和裝置名稱全部相符，當您取代使用者的裝置 UE-V 時，系統會自動還原設定。 所有已同步處理，且所有備份資料都會自動在裝置上還原。

您也可以使用新的 PowerShell Cmdlet （還原-UevBackup）來還原不同裝置上的設定。 若要克隆新裝置的設定套件，請在 Windows PowerShell 中使用下列 Cmdlet：

``` syntax
Restore-UevBackup –Machine <MachineName>
```

其中， &lt; MachineName &gt; 是裝置的電腦名稱稱。

包括許多應用程式的 Office 2013 範本等範本，都可以全部包含在漫遊（預設）或備份設定檔中。 範本套件中的個別應用程式會跟隨群組。 Office 2013 的內框範本包括漫遊和只備份設定。 [僅限備份] 設定不能包含在漫遊設定檔中。

在 [備份/還原] 功能中，UE-V 將 [**上一個已知的良好（LKG）** ] 新增到 [回滾至設定] 的選項。 在這個版本中，您可以返回原始設定或 LKG 設定。 [LKG] 設定可讓使用者回滾到設定的 UE-V 之前的中間與穩定點。

### 如何使用 UE-V 備份/還原範本

以下是 UE-V 的主要備份和還原元件：

-   範本設定檔

-   [設定] 儲存位置範本中的 [設定套件] 位置

-   備份觸發程式

-   如何還原設定

**範本設定檔**

UE-V 範本設定檔是在您在裝置上註冊範本，或是透過 PowerShell/WMI 配置實用程式進行發佈時定義。 配置檔案類型包括：

-   漫遊（預設）

-   備份

-   BackupOnly

除非另外指定，否則在註冊前，所有範本都包含在漫遊設定檔中。 這些範本會將設定同步處理到已啟用對應範本的所有 UE-V 啟用裝置。

您可以使用 UevTemplateProfile Cmdlet，在擁有 PowerShell 或 WMI 的備份設定檔中新增範本。 備份設定檔中的範本將這些設定備份到特殊裝置名稱目錄中的 [設定] 儲存位置。 指定的設定會備份到此位置。

指定 BackupOnly 的範本包含該裝置專用的設定，除非明確還原，否則不應進行同步處理。 這些設定會儲存在設定儲存位置上與 [Backedup 設定] 中相同的裝置特定設定套件位置。 這些範本有一個特殊的識別碼內嵌在範本中，指定它們應該是此設定檔的一部分。

**[設定] 儲存位置範本中的 [設定套件] 位置**

漫遊設定檔設定會儲存在設定儲存位置。 指派給備份或 BackupOnly 設定檔的範本會將其設定儲存到特殊裝置名稱目錄中的 [設定] 儲存位置。 每個裝置都有在這些設定檔中擁有範本，都有自己的裝置名稱。 UE-V 不會清除這些目錄。

**備份觸發程式**

備份是由觸發 UE-V 同步處理的相同事件觸發。

**如何還原設定**

還原使用者的裝置會將目前已註冊範本的設定從另一個裝置的 [備份] 資料夾及所有已同步處理的設定還原至目前的電腦。 您可以透過以下兩種方式還原設定：

-   **自動還原**

    如果使用者的 UE-V 設定 [儲存路徑]、[網域] 和 [電腦名稱稱] 與目前使用者相符，就表示該使用者的所有設定都已同步處理，只會套用最新設定。 如果使用者第一次登入新的裝置，且符合這些準則，設定資料就會套用到該裝置。

    **注意**  
    [協助工具] 和 [Windows 桌面設定] 需要使用者重新登入 Windows 才能套用。



-   **手動還原**

    如果您想要在更新期間透過還原裝置來協助使用者，您可以選擇使用 UevBackup Cmdlet。 這個命令會從 [設定] 儲存位置下載使用者的設定。

## 將應用程式和 Windows 設定還原成原始狀態


在安裝 UE-V Agent 之後，當應用程式第一次啟動時，WMI 和 Windows PowerShell 命令可讓您將應用程式和 Windows 設定還原至電腦上的設定值。 此還原動作是在每個應用程式或 Windows 設定基礎上執行。 這些設定會在應用程式下次執行時還原，或在使用者登入作業系統時還原設定。

**若要使用 Windows PowerShell （即 UE-V 2）還原應用程式設定和 Windows 設定。**

1.  開啟 [Windows PowerShell] 視窗。

2.  輸入下列 Windows PowerShell Cmdlet 來還原應用程式設定和 Windows 設定。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong>Windows PowerShell Cmdlet</strong></th>
    <th align="left"><strong>描述</strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><code>Restore-UevUserSetting -&lt;TemplateID&gt;</code></p></td>
    <td align="left"><p>還原應用程式的使用者設定或還原一組 Windows 設定。</p></td>
    </tr>
    </tbody>
    </table>



**使用 WMI 來還原應用程式設定和 Windows 設定**

1.  開啟 Windows PowerShell 視窗。

2.  輸入下列 WMI 命令來還原應用程式設定和 Windows 設定。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong>WMI 命令</strong></th>
    <th align="left"><strong>描述</strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class UserSettings -Name RestoreByTemplateId -ArgumentList &lt;template_ID&gt;</code></p></td>
    <td align="left"><p>還原應用程式的使用者設定或還原一組 Windows 設定。</p></td>
    </tr>
    </tbody>
    </table>



~~~
**Note**  
UE-V does not provide a settings rollback for Windows apps.
~~~








## 相關主題


[使用 Windows PowerShell 和 WMI 管理 UE-V 2. x](administering-ue-v-2x-with-windows-powershell-and-wmi-both-uevv2.md)

[管理 UE-V 2。](administering-ue-v-2x-new-uevv2.md)









