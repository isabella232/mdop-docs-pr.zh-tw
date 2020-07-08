---
title: UE-V 2.x 入門
description: UE-V 2.x 入門
author: dansimp
ms.assetid: 526ecbf0-0dee-4f0b-b017-8f8d25357b14
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 02/13/2017
ms.openlocfilehash: d3f01dd67ea9e5f6cfcf5dc3425265deff3f7df1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809866"
---
# UE-V 2.x 入門


請依照本指南中的步驟，在小型測試環境中快速部署 Microsoft 使用者體驗虛擬化（UE-V）2.0 或2.1。 這可協助您判斷 UE-V 是否是正確的解決方案，可在企業中的多個裝置上管理使用者設定。

**記事** 本區段中的資訊會在整個檔中更詳細地重複。 因此，如果您已經知道 UE-V 2 是正確的解決方案，而且您不需要評估它，您可以直接[使用 [準備 ue-v 2. x] 部署](prepare-a-ue-v-2x-deployment-new-uevv2.md)。

 

UE-V 的標準安裝會同步處理預設的 Microsoft Windows 和 Office 設定，以及許多 Windows 應用程式設定。 請確定您的測試環境包含兩個或多個共用網路存取的使用者電腦，而且您會在一段短期內評估 UE-V。

-   [步驟1：確認先決條件](#step1)：請確定您的環境能夠執行 ue-v，包括支援的設定的詳細資料。

-   [步驟2：部署 ue-v 2 的設定儲存位置](#step2)：所有 Ue-v 部署都需要包含同步處理設定值之設定套件的位置。

-   [步驟3：部署 ue-v 2 代理](#step3)：若要使用 ue-v 同步處理設定，裝置必須已安裝並執行 ue-v Agent。

-   [步驟4：測試您的 ue-v 2 評估部署](#step4)：在裝有 ue-v agent 的兩部電腦上執行一些測試，並瞭解 ue-v 的運作方式。

就是這樣！ 遵循這些步驟之後，您就可以評估 UE-V 在企業中的運作方式。

**進一步評估：** 您也可以執行其他步驟來設定部分協力廠商與行業應用程式，以使用 UE-V 同步處理其設定，請參閱[部署 UE-v （自訂應用程式](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)）。

## <a href="" id="step1"></a>步驟1：確認先決條件


在您繼續進行之前，請確定您的環境包含執行 UE-V 的這些需求。

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong>作業系統</strong></th>
<th align="left"><strong>版本</strong></th>
<th align="left"><strong>Service pack</strong></th>
<th align="left"><strong>系統架構</strong></th>
<th align="left"><strong>Windows PowerShell</strong></th>
<th align="left"><strong>Microsoft .NET Framework</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows7</p></td>
<td align="left"><p>旗艦版、企業版或專業版</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>32 位元或 64 位元</p></td>
<td align="left"><p>Windows PowerShell 3.0 或更新版本</p></td>
<td align="left"><p>.NET Framework 4 或更新版本</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008R2</p></td>
<td align="left"><p>標準版、企業版、資料中心或 Web 服務器</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 位元</p></td>
<td align="left"><p>Windows PowerShell 3.0 或更新版本</p></td>
<td align="left"><p>.NET Framework 4 或更新版本</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows 8.1</p></td>
<td align="left"><p>企業或專業版</p></td>
<td align="left"><p>無</p></td>
<td align="left"><p>32 位元或 64 位元</p></td>
<td align="left"><p>Windows PowerShell 3.0 或更新版本</p></td>
<td align="left"><p>.NET Framework 4。5</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2012 或 Windows Server 2012 R2</p></td>
<td align="left"><p>標準或資料中心</p></td>
<td align="left"><p>無</p></td>
<td align="left"><p>64 位元</p></td>
<td align="left"><p>Windows PowerShell 3.0 或更新版本</p></td>
<td align="left"><p>.NET Framework 4。5</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows 10、1607以前的 verison</p></td>
<td align="left"><p>企業或專業版</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 位元或 64 位元</p></td>
<td align="left"><p>Windows PowerShell 3.0 或更新版本</p></td>
<td align="left"><p>.NET Framework 4。5</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2016</p></td>
<td align="left"><p>標準或資料中心</p></td>
<td align="left"><p>無</p></td>
<td align="left"><p>64 位元</p></td>
<td align="left"><p>Windows PowerShell 3.0 或更新版本</p></td>
<td align="left"><p>.NET Framework 4。5</p></td>
</tr>
</tbody>
</table>

**注意：** 從 Windows 10 開始，版本1607、UE-V 已包含在企業版[windows 10](https://www.microsoft.com/WindowsForBusiness/windows-for-enterprise)中，而且不再是 Microsoft 桌面優化套件的一部分

另外 .。。

-   **MDOP 授權：** 這項技術是 Microsoft 桌面優化套件（MDOP）的一部分。 企業客戶可以使用 Microsoft 軟體保證進行 MDOP。 如需 Microsoft 軟體保證及取得 MDOP 的詳細資訊，請參閱如何取得 MDOP （ https://go.microsoft.com/fwlink/p/?LinkId=322049) 。

-   您要安裝之任何電腦的系統**管理認證**

## <a href="" id="step2"></a>步驟2：部署 UE-V 2 的設定儲存位置


您必須部署設定儲存位置，即使用者設定儲存在設定套件檔案中的標準網路共用。 當您建立設定儲存區共用時，應該限制存取需要的使用者。 [[部署設定] 儲存位置](https://technet.microsoft.com/library/dn458891.aspx#ssl)可提供更詳細的資訊。

**建立網路共用**

1.  建立新的安全性群組，並將 UE-V 使用者新增到其中。

2.  在集中位置的電腦上建立儲存 UE-V 設定套件的新資料夾，然後授與 UE-V 使用者存取資料夾的群組許可權。 支援 UE-V 的管理員必須擁有此共用資料夾的許可權。

3.  指派 UE-V 使用者在連線時建立目錄的許可權。 授與該目錄所有子目錄的完整許可權，但封鎖上述任何內容的存取權。

    1.  針對 [設定儲存位置] 資料夾設定下列共用層伺服器訊息區塊（SMB）許可權。

        <table>
        <colgroup>
        <col width="50%" />
        <col width="50%" />
        </colgroup>
        <thead>
        <tr class="header">
        <th align="left"><strong>使用者帳戶</strong></th>
        <th align="left"><strong>建議的許可權</strong></th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td align="left"><p>所有人</p></td>
        <td align="left"><p>沒有許可權</p></td>
        </tr>
        <tr class="even">
        <td align="left"><p>UE-V 使用者的安全性群組</p></td>
        <td align="left"><p>完全控制</p></td>
        </tr>
        </tbody>
        </table>

         

    2.  針對 [設定儲存位置] 資料夾設定下列 NTFS 檔案系統許可權。

        <table>
        <colgroup>
        <col width="33%" />
        <col width="33%" />
        <col width="33%" />
        </colgroup>
        <thead>
        <tr class="header">
        <th align="left"><strong>使用者帳戶</strong></th>
        <th align="left"><strong>建議的許可權</strong></th>
        <th align="left"><strong>資料夾</strong></th>
        </tr>
        </thead>
        <tbody>
        <tr class="odd">
        <td align="left"><p>建立者/擁有者</p></td>
        <td align="left"><p>完全控制</p></td>
        <td align="left"><p>僅限子資料夾和檔案</p></td>
        </tr>
        <tr class="even">
        <td align="left"><p>UE-V 使用者的安全性群組</p></td>
        <td align="left"><p>列出資料夾/讀取資料、建立資料夾/附加資料</p></td>
        <td align="left"><p>僅限此資料夾</p></td>
        </tr>
        </tbody>
        </table>

         

**安全性注意事項：**

如果您在執行 Windows Server 作業系統的電腦上建立 [設定儲存空間共用]，請設定 UE-V，確認 [本機管理員] 群組或 [目前的使用者] 是儲存設定套件的資料夾擁有者。 若要啟用此額外的安全性，請在 Windows Server 登錄編輯程式中指定此設定：

1.  將名為 **"RepositoryOwnerCheckEnabled"** 的**REG \ _DWORD**登錄機碼新增至**HKEY \ _LOCAL \ _MACHINE \\software\\microsoft\\uev\\agent\\configuration**]。

2.  將 [登錄機碼] 值設定為*1*。

## <a href="" id="step3"></a>步驟3：部署 UE-V 2 代理程式


UE-V Agent 會在使用者的電腦和裝置之間同步處理應用程式和 Windows 設定。 針對評估目的，請在您的測試環境中，將代理安裝在屬於同一位使用者的至少兩台電腦上。

從命令列執行 AgentSetup.exe 檔案，以安裝 UE-V Agent。 它是在32位和64位作業系統上安裝。

``` syntax
AgentSetup.exe SettingsStoragePath=\\server\settingsshare\%username%
```

您必須將 SettingsStoragePath 命令列參數指定為步驟2的網路共用。 [部署 Ue-v Agent](https://technet.microsoft.com/library/dn458891.aspx#agent)提供更詳細的資訊。

## <a href="" id="step4"></a>步驟4：測試您的 UE-V 2 評估部署


您現在可以在 UE-V 評估部署上執行一些測試，以瞭解 UE-V 的運作方式。

****

1.  在第一部電腦（電腦 A）上，進行下列其中一項或多項變更：

    1.  開啟至 Windows 桌面並將工作列移至視窗中的其他位置。

    2.  變更預設字型。

    3.  開啟 [計算機] 並設定為 [**科學**]。

    4.  變更任何 Windows 應用程式的行為，如[管理使用 Windows PowerShell 和 WMI 的 ue-v A.x 設定位置範本](managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md)中所述。

    5.  停用 Microsoft 帳戶設定同步處理和漫遊設定檔。

2.  登出電腦 A：當使用者鎖定、登出、結束應用程式時，或同步處理提供程式執行時（每30分鐘預設），設定就會儲存在 UE-V 設定套件中。

3.  登入第二部電腦（電腦 B）做為電腦 A 的同一個使用者。

4.  開啟至 Windows 桌面並確認工作列位置與電腦 A 相符。請確認預設字型相符，且該計算機已設定為**科學型**。 此外，請確認您對任何 Windows app 所做的變更。

您可以將電腦 B 中的設定變更回原始電腦的設定。 然後登出電腦 B 並登入電腦 A 以驗證變更。

## 此產品的其他資源


-   [Microsoft 使用者體驗虛擬化（UE-V） 2. x](index.md)

-   [準備 UE-V a.x 部署](prepare-a-ue-v-2x-deployment-new-uevv2.md)

-   [管理 UE-V 2。](administering-ue-v-2x-new-uevv2.md)

-   [疑難排解 UE-V 2. x](troubleshooting-ue-v-2x-both-uevv2.md)

-   [UE-V 2.x 技術參考](technical-reference-for-ue-v-2x-both-uevv2.md)






 

 





