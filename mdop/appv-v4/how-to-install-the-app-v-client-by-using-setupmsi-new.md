---
title: 如何使用 Setup.msi 安裝 App-V Client
description: 如何使用 Setup.msi 安裝 App-V Client
author: dansimp
ms.assetid: 7221f384-36d6-409a-94a2-86f54fd75322
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7fb3a145a6c57cccbae3f4e6b191b89d93278ff8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801374"
---
# 如何使用 Setup.msi 安裝 App-V Client


本主題描述如何使用 setup.msi 程式來安裝 App-v 用戶端。 在您使用 setup.msi 程式安裝 App-V 用戶端之前，您必須先判斷是否必須安裝任何必要的軟體，然後才能安裝它。 若要安裝必備軟體，請參閱本主題的[安裝必備軟體](#prereq-sw)一節。 若要安裝用戶端軟體，請參閱本主題的[使用 Setup.msi 程式區段來安裝 App-V 用戶端](#msi-setup)。

## <a href="" id="prereq-sw"></a>安裝必備軟體


您可以使用下列程式來安裝必備軟體。 您可以建立命令檔並從命令提示字元執行命令，或者您可以使用「VBScript」或「Windows PowerShell」等指令碼語言來執行命令。

**記事** 在應用程式 V 用戶端的 x86 和 x64 版本中，都需要下列軟體的 x86 版本。

 

**若要安裝 Microsoft VisualC + + 2005SP1 可再發行套件（x86）**

1. 從 Microsoft 下載中心下載[Microsoft Visual c + + 2005 SP1 可再發行套件（x86）](https://go.microsoft.com/fwlink/?LinkId=119961)軟體套件 <https://go.microsoft.com/fwlink/?LinkId=119961> 。 \ [範本權杖值 \] 針對版本 4.5 SP2 及更新版本的 App-V 用戶端，從[Microsoft Visual c + + 2005 Service Pack 1 的可再發行套件](https://go.microsoft.com/fwlink/?LinkId=169360)（ https://go.microsoft.com/fwlink/?LinkId=169360).\ [Template Token 值 \]）下載 vcredist\_x86.exe

2. 若要自行安裝，請在命令列選項 "/Q" 中使用 vcredist\_x86.exe，例如**vcredist\_x86.exe/q**。

3. 若要使用 vcredist\_x86.msi 檔案來安裝軟體，請使用命令列選項 "/C/T： &lt; fullpathtofolder &gt; " 將檔案 vcredist.msi，然後 vcredis1.cab 從 vcredist\_x86.exe 到暫存檔案夾。 若要自行安裝，請使用命令列選項/quiet，例如， **msiexec/i vcredist.msi** /quiet。

### 若要安裝 Microsoft VisualC + + 2008SP1 可再發行套件（x86）

**重要** 針對應用程式-V 用戶端的4.6 及更新版本，您也必須安裝 Microsoft Visual c + + 2008 Service Pack 1 可重新發佈的套件 ATL 安全性更新。

 

****

1.  從 Microsoft 下載中心下載[Microsoft Visual c + + 2008 Service Pack 1 可再發行套件 [ATL Security Update](https://go.microsoft.com/fwlink/?LinkId=150700)軟體套件] https://go.microsoft.com/fwlink/?LinkId=150700) 。

2.  若要自行安裝，請在命令列選項 "/Q" 中使用 vcredist\_x86.exe，例如**vcredist\_x86.exe/q**。

### 安裝 Microsoft Core XML Services （MSXML） 6.0 SP1 （x86）

****

1.  從 Microsoft 下載中心下載[Microsoft CORE XML Services （MSXML） 6.0 sp1 （x86）](https://go.microsoft.com/fwlink/?LinkId=63266)軟體套件（ https://go.microsoft.com/fwlink/?LinkId=63266) 。

2.  若要自行安裝，請使用命令列選項/quiet，例如， **msiexec/i msxml6\_x86.msi/quiet**。

### 若要安裝 Microsoft 應用程式錯誤報表

安裝 Microsoft 應用程式錯誤報表時，您必須使用*APPGUID*參數來指定 app-v 產品代碼。 產品代碼對於每個 App-v 用戶端類型和版本都是唯一的。 從下表中選取正確的產品代碼。

**重要** 在 App-v 4.6 SP2 及更新版本中，您不再需要安裝 Microsoft 應用程式錯誤報表（dw20shared.msi）。 App-v 現在使用 Microsoft 錯誤報表。

 

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">版本</th>
<th align="left">桌面用戶端的產品代碼</th>
<th align="left">適用于遠端桌面服務之用戶端的產品代碼</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-V 4.5 CU1</p></td>
<td align="left"><p>FE495DBC-6D42-4698-B61F-86E655E0796D</p></td>
<td align="left"><p>8A97C241-D92A-47DC-B360-E716C1AAA929</p></td>
</tr>
<tr class="even">
<td align="left"><p>App-V 4.5 SP1</p></td>
<td align="left"><p>93468B43-C19D-44F9-8BCC-114076DB0443</p></td>
<td align="left"><p>0042AD3C-99A4-4E58-B5F0-744D5AD96E1C</p></td>
</tr>
<tr class="odd">
<td align="left"><p>App-v 4.5 SP2</p></td>
<td align="left"><p>C6FC75B9-7D86-4C44-8BDB-EAFE1F0E200D</p></td>
<td align="left"><p>ECF80BBA-CA07-4A74-9ED6-E064F38AF1F5</p></td>
</tr>
<tr class="even">
<td align="left"><p>應用程式-V 4.6 x86</p></td>
<td align="left"><p>9E9D30B2-2065-4FDE-B756-8F1A6EABAFC3</p></td>
<td align="left"><p>439FAC21-B423-41D4-8126-54F9FCB70039</p></td>
</tr>
<tr class="odd">
<td align="left"><p>App-V 4.6 x64</p></td>
<td align="left"><p>E569E45F-7BA6-4C7F-B6BA-3FFCBE92FC22</p></td>
<td align="left"><p>D2977C18-D88A-47CB-AFD8-652DD36F4D0D</p></td>
</tr>
<tr class="even">
<td align="left"><p>App-V 4.6 x86 ¹</p></td>
<td align="left"><p>40C3258B-F9D1-46DF-AE97-72C1F86F2427</p></td>
<td align="left"><p>9915D911-CC73-4122-AF4F-564F89454655</p></td>
</tr>
<tr class="odd">
<td align="left"><p>App-V 4.6 x64 ¹</p></td>
<td align="left"><p>1650E31F-23B8-40B5-A60A-C5934F557E3B</p></td>
<td align="left"><p>7580D918-C621-49E7-9877-3CC59F9BD1DA</p></td>
</tr>
<tr class="even">
<td align="left"><p>App-V 4.6 x86 SP1</p></td>
<td align="left"><p>DB9F70CD-29BC-480B-8BA2-C9C2232C4553</p></td>
<td align="left"><p>1354855A-2298-4C73-9022-EF0686C65991</p></td>
</tr>
<tr class="odd">
<td align="left"><p>App-V 4.6 x64 SP1</p></td>
<td align="left"><p>342C9BB8-65A0-46DE-AB7A-8031E151AF69</p></td>
<td align="left"><p>B2C6C8D5-FE76-4056-A326-EE5D633EA175</p></td>
</tr>
</tbody>
</table>

 

¹ App-V "語言" 版本。

**記事** 如果您需要尋找產品代碼，您可以使用 Orca.exe 資料庫編輯器或類似的工具來檢查 Windows 安裝程式檔案，以找出*ProductCode*屬性的值。 如需使用 Orca.exe 的詳細資訊，請參閱[Windows 安裝程式開發工具](https://go.microsoft.com/fwlink/?LinkId=150008)（ https://go.microsoft.com/fwlink/?LinkId=150008) 。

 

****

1.  找出 Microsoft 應用程式錯誤報表安裝程式，dw20shared.msi，可以在發行媒體的**Support\\Watson**資料夾中找到。

2.  若要安裝軟體，請執行下列命令：

         **msiexec /i dw20shared.msi APPGUID={valuefromtable} REBOOT=Suppress REINSTALL=ALL REINSTALLMODE=vomus**

## <a href="" id="msi-setup"></a>使用 Setup.msi 程式安裝 App V 用戶端


使用下列程式來安裝 App-v 用戶端。 確認已安裝任何必要的必備軟體。 \ [Template 標記值 \] 在應用程式 V 用戶端的版本4.6 及更新版本中，setup.msi 程式會檢查系統，如果未安裝必備軟體，則會產生錯誤訊息，指出安裝無法繼續執行。 \ [範本標記值 \]

**使用 Setup.msi 安裝應用程式虛擬化用戶端**

1.  確認您是以在電腦上擁有系統管理員許可權的帳戶登入。

2.  使用較高的權限開啟命令提示字元視窗，然後將目錄變更為內含安裝程式檔案的資料夾。 在安裝版本4.6 或更新版本的 App-v 用戶端時，您必須針對電腦的作業系統、32位或64位使用正確的安裝程式。 如果您使用的是錯誤的安裝程式，安裝將會失敗，並會顯示錯誤訊息。

3.  在命令提示字元中輸入安裝命令字串。 或者，您可以建立命令檔，然後從命令提示字元執行它。 您也可以使用「VBScript」或「Windows PowerShell」等指令碼語言來執行命令。

4.  下列命令列範例會說明如何將 setup.msi 用於許多選用的參數。 如需這些參數的詳細資訊，請參閱[應用程式虛擬化用戶端安裝程式命令列參數](application-virtualization-client-installer-command-line-parameters.md)。

    **msiexec.exe/i "setup.msi" SWICACHESIZE = "10240" SWIPUBSVRDISPLAY = "生產系統" SWIPUBSVRTYPE = ""/secure "SWIPUBSVRHOST =" PRODSYS "SWIPUBSVRPORT =" 443 "SWIPUBSVRPATH ="/AppVirt/appsntype.xml "SWIPUBSVRREFRESH =" @ "SWIGLOBALDATA ^ D:\\AppVirt\\Global Virtualization 用戶端" SWIUSERDATA = "S"**

    **重要**  
    -   Windows Installer 開關 "**/q**" 是用來將它設為無訊息安裝。

    -   " **%** **% HomeDrive%**" 中的 "" 字元前面必須是 " **^** " 逸出字元。 否則，Windows 命令 shell 會將值設定為執行安裝的使用者。

    -   若要開啟安裝記錄，請使用 msiexec 開關 **/l\ * v filename. 記錄**。

     

## 相關主題


[如何使用命令列安裝用戶端](how-to-install-the-client-by-using-the-command-line-new.md)

 

 





