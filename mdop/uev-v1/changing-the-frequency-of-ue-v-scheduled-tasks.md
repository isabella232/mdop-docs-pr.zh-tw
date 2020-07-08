---
title: 變更 UE-V 排程工作的頻率
description: 變更 UE-V 排程工作的頻率
author: dansimp
ms.assetid: 33c2674e-0df4-4717-9c3d-820a90b16e19
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ced608608ffae82a29fb5ca84cfca281082b8127
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809506"
---
# 變更 UE-V 排程工作的頻率


Microsoft User Experience Virtualization （UE-V） Agent 安裝程式（AgentSetup.exe）會在 UE-V Agent 安裝期間建立兩個排程的任務。 這兩個工作為 [**範本自動更新**] 工作，以及 [**設定儲存位置狀態**] 任務。 這些排程的任務無法使用 UE-V 工具進行設定。 如果系統管理員想要變更這些專案的排程任務，就可以建立使用 Schtasks.exe 命令列選項的腳本。

如需 Schtasks.exe 的詳細資訊，請參閱[如何使用 Schtasks、exe 來排程 Windows Server 2003 中的任務](https://go.microsoft.com/fwlink/?LinkID=264854)。

## 範本自動更新


**範本自動更新**工作會檢查 [設定] 範本目錄，以瞭解新的、更新或移除的範本。 只有在 SettingsTemplateCatalog 已設定的情況下，才會執行此工作。 **範本自動更新**工作會執行 ApplySettingsCatalog.exe 檔案，該檔案位於 ue-v agent 安裝目錄中。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">任務名稱</th>
<th align="left">預設觸發程式</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>\Microsoft\UE-V\Template 自動更新</p></td>
<td align="left"><p>每天3:30</p></td>
</tr>
</tbody>
</table>

 

**範例：** 下列命令會將代理程式設定為每小時檢查設定範本的目錄存放區。

``` syntax
schtasks /change /tn "Microsoft\UE-V\Template Auto Update" /ri 60
```

## 設定儲存位置狀態


**設定儲存位置狀態**任務會執行下列動作：

1.  檢查以確認 UE-V 資料夾仍受到固定或使用 [離線檔案] 功能進行註冊。

2.  檢查設定儲存位置是否為 [離線] 或 [線上]。

3.  根據指定的間隔強行進行同步處理，而不是離線檔案的預設間隔。

4.  同步處理所有設定為預回遷的設定套件。

5.  檢查 Active Directory 主目錄路徑是否已變更。

6.  將目前的設定儲存空間配置寫入下列位置

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">任務名稱</th>
    <th align="left">預設觸發程式</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>\Microsoft\UE-V\Settings 儲存位置狀態</p></td>
    <td align="left"><p>在任何使用者登入之後，每隔30分鐘重複一次。</p></td>
    </tr>
    </tbody>
    </table>

     

**範例：** 下列命令會將代理程式設定為在每小時執行上述動作。

``` syntax
schtasks /change /tn "\Microsoft\UE-V\Settings Storage Location Status" /ri 60
```

## 相關主題


[管理 UE-V 1.0](administering-ue-v-10.md)

[UE-V 1.0 作業](operations-for-ue-v-10.md)

 

 





