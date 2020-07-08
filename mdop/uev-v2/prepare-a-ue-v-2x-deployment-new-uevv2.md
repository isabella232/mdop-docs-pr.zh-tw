---
title: 準備 UE-V a.x 部署
description: 準備 UE-V a.x 部署
author: dansimp
ms.assetid: c429fd06-13ff-48c5-b9c9-fa1ec01ab800
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 04/19/2017
ms.openlocfilehash: e6b2de407990536e1a08532632dcea19ea0d0ee9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811745"
---
# 準備 UE-V a.x 部署


在將 Microsoft 使用者體驗虛擬化（UE-V）2.0 或2.1 部署為可在使用者在企業中存取的裝置之間同步處理設定的方案之前，必須先進行一些規劃及準備。 本主題可協助您判斷您要執行的部署類型，以及您可以提前進行的準備，以便順利進行部署。

首先，讓我們來看看部署 UE-V 要執行的工作：

-   規劃您的 UE-V 部署

    在您部署任何專案之前，最好先進行一些規劃，讓您可以判斷您要部署哪些 UE-V 功能。 因此，如果您離開此頁面，請務必返回並閱讀下面的規劃資訊。

-   [部署 UE-V 2.x 的必要功能](deploy-required-features-for-ue-v-2x-new-uevv2.md)

    每個 UE-V 部署都需要下列活動：

    -   [定義設定儲存位置](https://technet.microsoft.com/library/dn458891.aspx#ssl)

    -   [決定如何部署 UE-V Agent 及管理 UE-V 設定](https://technet.microsoft.com/library/dn458891.aspx#config)

    -   在每個需要同步處理設定的使用者電腦上[安裝 Ue-v Agent](https://technet.microsoft.com/library/dn458891.aspx#agent)

-   或者，您也可以[為自訂應用程式部署 ue-v 2. x](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)

    規劃將可協助您判斷是否希望 UE-V 支援針對自訂應用程式（協力廠商或商務線）的設定同步處理，而這需要下列 UE-V 功能：

    -   [安裝 UEV 發生器](https://technet.microsoft.com/library/dn458942.aspx#uevgen)，讓您可以建立、編輯及驗證同步處理自訂應用程式設定所需的自訂設定位置範本

    -   使用 UE-V 發生器[建立自訂設定位置範本](https://technet.microsoft.com/library/dn458942.aspx#createcustomtemplates)

    -   部署您用來儲存您的自訂設定位置範本的[ue-v 設定範本目錄](https://technet.microsoft.com/library/dn458942.aspx#deploycatalogue)

此工作流程圖表可讓您深入瞭解 UE-V 部署，以及決定如何在企業中部署 UE-V 的決定。

![deploymentworkflow](images/deploymentworkflow.png)

**規劃 ue-v 部署：** 首先，您想要執行一些規劃，讓您可以判斷要部署哪些 UE-V 元件。 規劃 UE-V 部署包括下列專案：

-   [決定是否要同步處理自訂應用程式的設定](#deciding)

    這會判斷您是否要在部署期間安裝 UE-V 發生器，這可讓您建立自訂設定位置範本。 它包含下列專案：

    查看[在 ue-v 部署中自動同步](#autosyncsettings)處理的設定。

    [判斷您是否需要同步處理其他應用程式的設定](#determinesettingssync)。

-   查看[部署 ue-v 的其他考慮](#considerations)（例如高可用性和容量規劃）。

-   [確認 UE-V 的先決條件和支援的設定](#prereqs)

## <a href="" id="deciding"></a>決定是否要同步處理自訂應用程式的設定


在 UE-V 部署中，許多設定會自動同步處理。 但您也可以自訂 UE-V，以同步處理其他應用程式的設定，例如企業與協力廠商應用程式。

決定是否要讓 UE-V 同步處理自訂應用程式的設定，這可能是規劃 UE-V 部署最重要的部分。 本節中的主題將協助您做出這項決策。

### <a href="" id="autosyncsettings"></a>在 UE-V 部署中自動同步處理的設定

本節提供與 UE-V 預設同步處理之設定的相關資訊，包括下列各項：

預設會同步處理設定的桌面應用程式

預設會同步處理的 Windows 桌面設定

Windows 應用程式設定同步處理的支援語句

請參閱[適用于 Microsoft Office 的使用者體驗虛擬化（ue-v）設定範本](https://www.microsoft.com/download/details.aspx?id=46367)，下載已由 ue-v 同步處理的特定 Microsoft office 2013、microsoft office 2010 及 Microsoft office 2007 設定的完整清單。

### UE-V 2.1 和 UE-V 2.1 SP1 中的預設同步處理桌面應用程式

當您安裝 UE-V 2.1 或 2.1 SP1 代理程式時，它會註冊一個預設的設定位置範本群組，以捕獲這些常見 Microsoft 應用程式的設定值。

**提示**  
**Microsoft office 2007 設定同步**處理-在 ue-v 2.1 和 2.1 SP1 中，Office 2007 應用程式預設不再包含設定位置範本。 不過，您仍然可以使用 UE-V 2.0 或較舊版本的 Office 2007 範本，並可從[ue-v 範本庫](https://go.microsoft.com/fwlink/p/?LinkID=246589)取得範本。



<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong>應用程式類別</strong></th>
<th align="left"><strong>描述</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft Office 2010 應用程式</p>
<p>（ <a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)"> 下載所有設定已同步處理的清單 </a> ）</p></td>
<td align="left"><p>Microsoft Word 2010</p>
<p>Microsoft Excel 2010</p>
<p>Microsoft Outlook 2010</p>
<p>Microsoft Access 2010</p>
<p>Microsoft Project 2010</p>
<p>Microsoft PowerPoint 2010</p>
<p>Microsoft Publisher 2010</p>
<p>Microsoft Visio 2010</p>
<p>Microsoft SharePoint Workspace 2010</p>
<p>Microsoft InfoPath 2010</p>
<p>Microsoft Lync 2010</p>
<p>Microsoft OneNote 2010</p>
<p>Microsoft SharePoint Designer 2010</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Office 2013 應用程式</p>
<p>（ <a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)"> 下載所有設定已同步處理的清單 </a> ）</p></td>
<td align="left"><p>Microsoft Word 2013</p>
<p>Microsoft Excel 2013</p>
<p>Microsoft Outlook 2013</p>
<p>Microsoft Access 2013</p>
<p>Microsoft Project 2013</p>
<p>Microsoft PowerPoint 2013</p>
<p>Microsoft Publisher 2013</p>
<p>Microsoft Visio 2013</p>
<p>Microsoft InfoPath 2013</p>
<p>Microsoft Lync 2013</p>
<p>Microsoft OneNote 2013</p>
<p>Microsoft SharePoint Designer 2013</p>
<p>Microsoft Office 2013 上傳中心</p>
<p>Microsoft 商務用 OneDrive 2013</p>
<p>UE-V 2.1 和 2.1 SP1 Microsoft Office 2013 設定位置範本包括改良的 Outlook 簽名支援。 我們已新增新、回復和轉寄電子郵件的預設簽名設定同步處理。</p>
<div class="alert">
<strong>注意</strong><br/><p>您必須為使用者要同步處理其 Outlook 簽名的任何裝置建立 Outlook 設定檔。 如果尚未建立設定檔，使用者可以建立一個，然後重新開機該裝置上的 Outlook，以啟用簽名同步處理。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>瀏覽器選項： Internet Explorer 8、Internet Explorer 9、Internet Explorer 10 和 Internet Explorer 11</p></td>
<td align="left"><p>[我的最愛]、[首頁]、[定位點] 和工具列</p>
<div class="alert">
<strong>注意</strong><br/><p>UE-V 不會漫遊 Internet Explorer cookie 的設定。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 附件</p></td>
<td align="left"><p>Microsoft 計算機、記事本、寫字板。</p></td>
</tr>
</tbody>
</table>



**注意**  
UE-V 2.1 SP1 不會同步處理 Windows 10 中的 Microsoft 計算機與舊版作業系統中的 Microsoft 計算機之間的設定。



### UE-V 2.0 中預設同步處理的桌面應用程式

當您安裝 UE-V 2.0 Agent 時，它會註冊一個預設的設定位置範本群組，以捕獲這些常見 Microsoft 應用程式的設定值。

**提示**  
**Microsoft office 2013 設定同步**處理-在 Ue-v 2.0 中，預設不會包含 Office 2013 應用程式的設定位置範本，但可從[ue-v 範本庫](https://go.microsoft.com/fwlink/p/?LinkID=246589)下載。 將[office 2013 與 ue-v 2.0 同步](synchronizing-office-2013-with-ue-v-20-both-uevv2.md)處理可提供同步處理 office 2013 設定之支援範本的詳細資料。



<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong>應用程式類別</strong></th>
<th align="left"><strong>描述</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft Office 2007 應用程式</p>
<p>（ <a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)"> 下載所有設定已同步處理的清單 </a> ）</p></td>
<td align="left"><p>Microsoft Access 2007</p>
<p>Microsoft Communicator 2007</p>
<p>Microsoft Excel 2007</p>
<p>Microsoft InfoPath 2007</p>
<p>Microsoft OneNote 2007</p>
<p>Microsoft Outlook 2007</p>
<p>Microsoft PowerPoint 2007</p>
<p>Microsoft Project 2007</p>
<p>Microsoft Publisher 2007</p>
<p>Microsoft SharePoint Designer 2007</p>
<p>Microsoft Visio 2007</p>
<p>Microsoft Word 2007</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Office 2010 應用程式</p>
<p>（ <a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)"> 下載所有設定已同步處理的清單 </a> ）</p></td>
<td align="left"><p>Microsoft Word 2010</p>
<p>Microsoft Excel 2010</p>
<p>Microsoft Outlook 2010</p>
<p>Microsoft Access 2010</p>
<p>Microsoft Project 2010</p>
<p>Microsoft PowerPoint 2010</p>
<p>Microsoft Publisher 2010</p>
<p>Microsoft Visio 2010</p>
<p>Microsoft SharePoint Workspace 2010</p>
<p>Microsoft InfoPath 2010</p>
<p>Microsoft Lync 2010</p>
<p>Microsoft OneNote 2010</p>
<p>Microsoft SharePoint Designer 2010</p></td>
</tr>
<tr class="odd">
<td align="left"><p>瀏覽器選項： Internet Explorer 8、Internet Explorer 9 和 Internet Explorer 10</p></td>
<td align="left"><p>[我的最愛]、[首頁]、[定位點] 和工具列</p>
<div class="alert">
<strong>注意</strong><br/><p>UE-V 不會漫遊 Internet Explorer cookie 的設定。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 附件</p></td>
<td align="left"><p>Microsoft 計算機、記事本、寫字板。</p></td>
</tr>
</tbody>
</table>



### <a href="" id="autosyncsettings2"></a>Windows 設定預設會同步處理

UE-V 包含設定位置範本，可捕獲這些 Windows 設定的設定值。

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Windows 設定</th>
<th align="left">描述</th>
<th align="left">適用</th>
<th align="left">匯出開啟</th>
<th align="left">預設狀態</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>桌面背景</p></td>
<td align="left"><p>目前使用中的桌面背景或牆紙。</p></td>
<td align="left"><p>登入、解除鎖定、遠端連線、排程任務事件。</p></td>
<td align="left"><p>登出、鎖定、遠端中斷、使用者 <strong> 在 [公司設定中心] 中按一下 [立即同步處理] </strong> 或 [排程的任務間隔]</p></td>
<td align="left"><p>啟用</p></td>
</tr>
<tr class="even">
<td align="left"><p>輕鬆存取</p></td>
<td align="left"><p>協助工具和輸入設定、Microsoft 放大鏡、朗讀程式及螢幕小鍵盤。</p></td>
<td align="left"><p>僅限登入。</p></td>
<td align="left"><p>登出、使用者按一下 [ <strong> 公司設定中心] 中的 [立即同步處理] </strong> 或 [排程的任務間隔]</p></td>
<td align="left"><p>啟用</p></td>
</tr>
<tr class="odd">
<td align="left"><p>桌面設定</p></td>
<td align="left"><p>[開始] 功能表和工作列設定、[資料夾選項]、[預設桌面圖示]、[其他時鐘] 和 [地區及語言設定]。</p></td>
<td align="left"><p>僅限登入。</p></td>
<td align="left"><p>登出，使用者按一下 [ <strong> 公司設定中心] 中的 [立即同步處理] </strong> ，或 [排程] 任務</p></td>
<td align="left"><p>啟用</p></td>
</tr>
</tbody>
</table>



**注意**  
從 Windows 8 開始，UE-V 不會漫遊與 [開始] 畫面相關的設定，例如 [專案] 和 [位置]。 此外，UE-V 不支援同步處理固定的工作列專案或 Windows 檔案快速鍵。



**重要**  
UE-V 2.1 SP1 會在 Windows 10 裝置之間漫遊工作列設定。 不過，UE-V 不會在執行舊版作業系統的 Windows 10 裝置與裝置之間同步處理工作列設定。



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">設定群組</th>
<th align="left">類別</th>
<th align="left">奪取</th>
<th align="left">[套用]</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>應用程式設定</strong></p></td>
<td align="left"><p>Windows 應用程式</p></td>
<td align="left"><p>關閉應用程式</p>
<p>Windows 應用程式設定變更事件</p></td>
<td align="left"><p>啟動時啟動 UE-V 應用程式監視器</p>
<p>開啟 app</p>
<p>Windows 應用程式設定變更事件</p>
<p>已到達設定套件</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p>傳統型應用程式</p></td>
<td align="left"><p>應用程式關閉</p></td>
<td align="left"><p>應用程式隨即開啟和關閉</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>桌面設定</strong></p></td>
<td align="left"><p>桌面背景</p></td>
<td align="left"><p>鎖定或登出</p></td>
<td align="left"><p>[登入]、[解除鎖定]、[遠端連線]、[新套件到貨] 的通知、[ <strong> </strong> 在公司設定中心立即同步處理] 或 [排程的工作]</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p>輕鬆存取（一般-協助工具、朗讀程式、放大鏡、螢幕小鍵盤）</p></td>
<td align="left"><p>鎖定或登出</p></td>
<td align="left"><p>標識</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p>輕鬆存取（Shell-音訊、協助工具、鍵盤、滑鼠）</p></td>
<td align="left"><p>鎖定或登出</p></td>
<td align="left"><p>登入、解除鎖定、遠端連線、新套件到貨的通知、使用者按一下 [ <strong> 公司設定中心] 中的 [立即同步處理] </strong> 或 [排程任務執行]</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p>桌面設定</p></td>
<td align="left"><p>鎖定或登出</p></td>
<td align="left"><p>標識</p></td>
</tr>
</tbody>
</table>



### UE-V-對 Windows 應用程式的支援

如果是 Windows 應用程式，應用程式開發人員會指定同步處理的設定。 您可以指定哪些 Windows 應用程式已啟用設定同步處理。

若要在 Windows PowerShell 命令提示字元上顯示可同步處理電腦設定的 Windows app 清單，以及其套件系列名稱、啟用狀態，以及已啟用的來源，請輸入： `Get-UevAppxPackage`

**注意**  
從 Windows 8 開始，如果網域使用者將登入認證連結到其 Microsoft 帳戶，UE-V 就不會同步處理 Windows 應用程式設定。 此連結會將設定同步處理到 Microsoft OneDrive，以讓 UE-V 停用 Windows 應用程式設定的同步處理。



### UE-V-對漫遊印表機的支援

UE-V 2.1 SP1 可讓網路印表機在裝置之間漫遊，讓使用者在登入網路上的任何裝置時都能存取其網路印表機。 這包括將其設為預設值的印表機漫遊。

UE-V 中的印表機漫遊需要下列其中一種情況：

-   列印伺服器可以在漫遊至新裝置時下載所需的驅動程式。

-   漫遊網路印表機的驅動程式已預先安裝在任何需要存取該網路印表機的裝置上。

-   您可以從 Windows Update 取得印表機驅動程式。

**注意**  
UE-V 印表機漫遊**功能不會漫遊印表機**設定或喜好設定，例如雙面列印。



### <a href="" id="determinesettingssync"></a>判斷您是否需要同步處理其他應用程式的設定

在您已複習在 UE-V 部署中自動同步處理的設定之後，您想要決定是否要同步處理其他應用程式的設定，因為這會決定您在整個企業中部署 UE-V 的方式。

如果您是系統管理員，當您認為要在 UE-V 解決方案中包含哪些桌面應用程式時，請考慮哪些設定可由使用者自訂，以及應用程式儲存其設定的方式和位置。 並非所有的桌面應用程式都有可自訂或經常由使用者自訂的設定。 此外，並非所有桌面應用程式設定都能安全地跨多個電腦或環境進行同步處理。

一般來說，您可以同步處理符合下列準則的設定：

-   儲存在使用者可存取位置的設定。 例如，請勿同步處理儲存在 System32 或 HKEY \ _CURRENT \ _USER （HKCU）區段的設定。

-   特定電腦不專用的設定。 例如，排除網路或硬體設定。

-   可以在電腦之間同步處理的設定，不會造成資料損毀的風險。 例如，請勿使用儲存在資料庫檔案中的設定。

### <a href="" id="checklistsettingssync"></a>評估自訂應用程式的檢查清單

如果您已決定您需要同步處理其他應用程式的設定，您可以使用這個檢查清單來協助找出您要包含哪些應用程式。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>此應用程式是否包含使用者可自訂的設定？</p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>對使用者來說，這些設定是否已同步處理是很重要的？</p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>這些使用者設定已經由應用程式管理或設定原則方案所管理嗎？ 在登入、解除鎖定或遠端連線事件時，UE-V 會在應用程式啟動和 Windows 設定中套用應用程式設定。 如果您將 UE-V 與其他設定共用解決方案搭配使用，使用者可能會在同步處理設定中遇到不一致的問題。</p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>電腦是否有特定的應用程式設定？ 與硬體或特定電腦設定相關聯的應用程式喜好設定和自訂，不會持續同步處理多個會話，而且可能會造成應用程式經驗不佳。</p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>[應用程式檔案] 目錄或位於 [使用者名稱] 的檔案目錄中的 [應用程式 <strong> 儲存 </strong> ] 設定 [ &lt; 強 &gt; AppData </strong> &lt; 強 &gt; LocalLow] </strong> 目錄？ 儲存在上述任一位置的應用程式資料通常不應與使用者進行同步處理，因為這項資料是針對電腦所特有的，或因為資料太大而無法進行同步處理。</p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>應用程式會將任何設定儲存在檔案中，包含不應該同步處理的其他應用程式資料？ UE-V 會將檔案同步處理為單一單元。 如果設定儲存在包括 [設定] 以外的應用程式資料的檔案中，則同步處理這項額外的資料可能會造成不佳的應用程式體驗。</p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>包含這些設定的檔案有多大？ 較大的檔案可能會影響設定同步處理的效能。 包括大型檔案會影響設定同步處理的效能。</p></td>
</tr>
</tbody>
</table>



## <a href="" id="considerations"></a>準備 UE-V 部署時的其他考慮事項


當您準備好要部署 UE-V 時，您也應該考慮下列事項：

-   [管理認證同步處理](#creds)

-   [Windows 應用程式設定同步處理](#appxsettings)

-   [自訂 UE-V 設定位置範本](#custom)

-   [無意間的使用者設定設定](#prevent)

-   [效能與容量](#capacity)

-   [高可用性](#high)

-   [電腦時鐘同步處理](#clocksync)

### <a href="" id="creds"></a>在 UE-V 2.1 和 UE-V 2.1 SP1 中管理認證同步處理

許多企業應用程式（包括 Microsoft Outlook 和 Lync）會在登入時提示使用者輸入其網域認證。 使用者可以選擇將其認證儲存至磁片，避免在每次開啟這些應用程式時都必須輸入它們。 啟用漫遊認證同步處理可讓使用者在一部電腦上儲存其認證，避免在他們在其環境中所使用的每一部電腦上重新輸入。 使用者可以將部分網域認證與 UE-V 2.1 和 2.1 SP1 同步處理。

**重要**  
認證同步處理預設為停用。 在部署期間，您必須明確啟用認證同步處理，才能執行這項功能。



UE-V 2.1 和 2.1 SP1 可以同步處理企業認證，但不會漫遊認證僅供在本機電腦上使用。

認證是同步處理設定，這表示在 UE-V 同步處理之後，第一次登入您的電腦時，會將它們套用到您的個人檔案。

認證同步處理是由它自己的設定位置範本所管理，預設為停用。 您可以透過其他範本所用的相同方法來啟用或停用此範本。 此功能的範本識別碼是 RoamingCredentialSettings。

**重要**  
如果您在您的環境中使用 Active Directory 認證漫遊，我們建議您不要啟用 UE-V 認證漫遊範本。



使用下列其中一種方法來啟用認證同步處理：

-   公司設定中心

-   PowerShell

-   群組原則

**注意**  
認證會在同步處理期間進行加密。



[[公司設定中心](https://technet.microsoft.com/library/dn458903.aspx)]**：** 核取 [Windows 設定] 下的 [漫遊認證設定] 核取方塊，以啟用認證同步處理。 取消核取核取方塊以停用它。 如果您的帳戶未設定為使用 Microsoft 帳戶同步處理設定，此核取方塊只會出現在 [公司設定中心] 中。

[Powershell](https://technet.microsoft.com/library/dn458937.aspx)**：** 此 PowerShell Cmdlet 可啟用認證同步處理：

``` syntax
Enable-UevTemplate RoamingCredentialSettings
```

此 PowerShell Cmdlet 會停用認證同步處理：

``` syntax
Disable-UevTemplate RoamingCredentialSettings
```

[群組原則](https://technet.microsoft.com/library/dn458893.aspx)**：** 您必須[部署最新的 MDOP ADMX 範本](https://go.microsoft.com/fwlink/p/?LinkId=393944)，才能透過群組原則啟用憑證同步處理。 認證同步處理是使用 Windows 設定來管理。 若要使用群組原則管理這項功能，請啟用 [同步處理 Windows 設定] 原則。

1.  開啟 [群組原則編輯器]，然後流覽至 [使用者設定]-[系統**管理範本]-Windows 元件-Microsoft 使用者體驗虛擬化**。

2.  按兩下 [**同步處理 Windows 設定**]。

3.  如果啟用此原則，您可以核取 [**漫遊認證**] 核取方塊，或 [停用認證同步處理] 來啟用認證同步處理。

4.  按一下 \[確定\] ****。

### 由 UE-V 同步處理認證位置

應用程式儲存在下列位置的認證檔案是已同步處理：

-   %UserProfile%\\AppData\\Roaming\\Microsoft\\Credentials\\

-   %UserProfile%\\AppData\\Roaming\\Microsoft\\Crypto\\

-   %UserProfile%\\AppData\\Roaming\\Microsoft\\Protect\\

-   %UserProfile%\\AppData\\Roaming\\Microsoft\\SystemCertificates\\

儲存在其他位置的認證不會透過 UE-V 進行同步處理。

### <a href="" id="appxsettings"></a>Windows 應用程式設定同步處理

UE-V 會以三種方式管理 Windows 應用程式設定同步處理：

-   **同步處理 Windows 應用程式：** 允許或拒絕任何 Windows 應用程式同步處理

-   **Windows 應用程式清單：** 同步處理 Windows 應用程式清單

-   未**列出的預設同步處理行為：** 判斷 windows 應用程式清單以外的 Windows 應用程式的同步處理行為。

如需詳細資訊，請參閱[Windows 應用程式清單](https://technet.microsoft.com/library/dn458925.aspx#win8applist)。

### <a href="" id="custom"></a>自訂 UE-V 設定位置範本

如果您要部署 UE-V 來同步處理自訂應用程式的設定，您將會使用 UE-V 發生器來為這些桌面應用程式建立自訂設定位置範本。 在測試環境中建立並測試自訂設定位置範本之後，您可以將設定位置範本部署到企業中的電腦。

自訂設定位置範本必須使用現有的部署基礎結構（例如系統中心建構管理員、含喜好設定，或設定 UE-V 設定範本目錄）來部署。 您必須使用 UE-V WMI 或 Windows PowerShell 來註冊使用 Configuration Manager 或群組原則部署的範本。

如需自訂設定位置範本的詳細資訊，請參閱[針對自訂應用程式部署 ue-v 2.](deploy-ue-v-2x-for-custom-applications-new-uevv2.md) 如需使用 UE-V 與 Configuration Manager 的詳細資訊，請參閱[使用 System Center Configuration manager 2012 設定 ue-v 2. x](configuring-ue-v-2x-with-system-center-configuration-manager-2012-both-uevv2.md)。

### <a href="" id="prevent"></a>防止無意間的使用者設定設定

UE-V 會從設定儲存位置下載新的使用者設定資訊，並將設定套用到本機電腦的下列情況：

-   每次啟動應用程式時，都會有已註冊的 UE-V 範本。

-   當使用者登入電腦時。

-   當使用者解除鎖定電腦時。

-   在已安裝 UE-V 的遠端桌面電腦建立連線時。

-   當同步處理控制器應用程式排程任務執行時。

如果 UE-V 是安裝在電腦 A 和電腦 B 上，而您想要用於應用程式的設定是在電腦 A 上，那麼電腦 A 應該先開啟並關閉應用程式。 如果應用程式先于電腦 B 開啟和關閉，則電腦 A 上的應用程式設定會設定為電腦 B 上的應用程式設定。每個應用程式都要在電腦之間同步處理設定。 隨著時間的推移，在電腦開啟和關閉時，這些設定會隨著喜好設定而持續保持不變。

此案例也適用于 Windows 設定。 如果電腦 B 上的 Windows 設定應該與電腦 A 上的 Windows 設定相同，則使用者應該先登入電腦，然後再登入電腦 A。

如果使用者所要套用的使用者設定的順序不正確，則可以在重寫設定的電腦上針對特定應用程式或 Windows 設定執行還原作業來復原這些設定。 如需詳細資訊，請參閱[管理 ue-v 2-d 中的系統管理備份和還原](manage-administrative-backup-and-restore-in-ue-v-2x-new-topic-for-21.md)。

### <a href="" id="capacity"></a>效能與容量規劃

針對標準磁片容量和網路狀況監視，指定您對 UE-V 的需求。

UE-V 使用伺服器訊息區塊（SMB）共用來儲存設定套件。 [設定] 套件的大小會根據每個應用程式的設定資訊而有所不同。 雖然大部分的設定套件都很小，但同步處理可能較大的檔案（例如桌面影像），可能會導致效能較差，特別是在較慢的網路上。

若要減少網路延遲的問題，請在使用者電腦所在的同一個本機網路上建立設定儲存位置。 針對設定儲存位置，我們建議每個使用者有 20 MB 的磁碟空間。

根據預設，UE-V 同步處理會在2秒後超時，以避免由於大型設定套件而造成過多的延遲。 您可以使用[群組原則物件](https://technet.microsoft.com/library/dn458893.aspx)來設定 SyncMethod = SyncProvider 設定。

### <a href="" id="high"></a>UE-V 的高可用性

UE-V 設定儲存位置和設定範本目錄支援將使用者資料儲存在任何可寫入的共用上。 若要確保高可用性，請遵循下列準則：

-   使用 NTFS 檔案系統格式化儲存空間。

-   共用可以使用分散式檔案系統（DFS），但有一些限制。
具體來說，會支援分散式檔案系統複製（DFS-R）單一目標設定或不含分散式檔案系統命名空間（DFS-N）。
同樣地，DFS-N 只支援單一目標設定。
如需詳細資訊，請參閱有關[複製的使用者設定檔資料的 Microsoft 支援聲明](https://go.microsoft.com/fwlink/p/?LinkId=313991)，以及[適用于 DFS R 和 dfs N 部署案例的 microsoft 支援原則的相關資訊](https://support.microsoft.com/kb/2533009)。

    此外，因為 SYSVOL 使用 DFS 進行複製，所以無法將 SYSVOL 用於 UE-V 資料檔案複製。

-   根據[部署 ue-v 2-d 的設定儲存位置](https://technet.microsoft.com/library/dn458891.aspx#ssl)中所指定的共用許可權和 NTFS 存取控制清單（acl）來設定。

-   使用檔案伺服器叢集與 UE-V Agent，在通訊發生故障時提供使用者狀態資料複本的存取權。

-   您可以將設定儲存路徑資料（使用者資料）及設定範本目錄範本儲存在群集共用、DFS-N 共用或兩者上。

### <a href="" id="clocksync"></a>同步處理 UE-V 設定同步處理電腦的時鐘

執行 UE-V Agent 的電腦必須使用時間伺服器來維持一致的設定體驗。 UE-V 使用時間戳來判斷設定是否必須從設定儲存位置進行同步處理。 如果電腦時鐘不准確，較舊的設定會覆寫較新的設定，或者新設定可能不會儲存到設定儲存位置。

## <a href="" id="prereqs"></a>確認 UE-V 的先決條件和支援的設定


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
<td align="left"><p>Windows 7</p></td>
<td align="left"><p>旗艦版、企業版或專業版</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>32 位元或 64 位元</p></td>
<td align="left"><p>Windows PowerShell 3.0 或更新版本</p></td>
<td align="left"><p>針對 UE-V 2.1 的 .NET Framework 4.5 或更新版本。</p>
<p>UE-V 2.0 的 .NET Framework 4 或更新版本。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2008 R2</p></td>
<td align="left"><p>標準版、企業版、資料中心或 Web 服務器</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 位元</p></td>
<td align="left"><p>Windows PowerShell 3.0 或更新版本</p></td>
<td align="left"><p>針對 UE-V 2.1 的 .NET Framework 4.5 或更新版本。</p>
<p>UE-V 2.0 的 .NET Framework 4 或更新版本。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows 8 和 Windows 8。1</p></td>
<td align="left"><p>企業或專業版</p></td>
<td align="left"><p>無</p></td>
<td align="left"><p>32 位元或 64 位元</p></td>
<td align="left"><p>Windows PowerShell 3.0 或更新版本</p></td>
<td align="left"><p>.NET Framework 4.5 或更新版本</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 10 （預1607版）</p>
<div class="alert">
<strong>注意</strong><br/><p>只有 UE-V 2.1 SP1 支援 Windows 10 （預1607版本）</p>
</div>
<div>

</div></td>
<td align="left"><p>企業或專業版</p></td>
<td align="left"><p>無</p></td>
<td align="left"><p>32 位元或 64 位元</p></td>
<td align="left"><p>Windows PowerShell 3.0 或更新版本</p></td>
<td align="left"><p>.NET Framework 4.6</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2012 和 Windows Server 2012 R2</p></td>
<td align="left"><p>標準或資料中心</p></td>
<td align="left"><p>無</p></td>
<td align="left"><p>64 位元</p></td>
<td align="left"><p>Windows PowerShell 3.0 或更新版本</p></td>
<td align="left"><p>.NET Framework 4.5 或更新版本</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2016</p></td>
<td align="left"><p>標準或資料中心</p></td>
<td align="left"><p>無</p></td>
<td align="left"><p>64 位元</p></td>
<td align="left"><p>Windows PowerShell 3.0 或更新版本</p></td>
<td align="left"><p>.NET Framework 4.6 或更新版本</p></td>
</tr>
</tbody>
</table>



另外 .。。

-   **MDOP 授權：** 這項技術是 Microsoft 桌面優化套件（MDOP）的一部分。 企業客戶可以使用 Microsoft 軟體保證進行 MDOP。 如需 Microsoft 軟體保證及取得 MDOP 的詳細資訊，請參閱如何取得 MDOP （ https://go.microsoft.com/fwlink/p/?LinkId=322049) 。

-   您要安裝之任何電腦的系統**管理認證**

**注意**  

-   從 WIndows 10 版本1607開始，UE-V 已包含在[企業版 windows 10](https://www.microsoft.com/WindowsForBusiness/windows-for-enterprise)中，而且不再是 Microsoft 桌面優化套件的一部分。

-   UE-V Agent 的 UE-V Windows PowerShell 功能需要 .NET Framework 4 或更新版本，以及啟用 Windows PowerShell 3.0 或更新版本。 請[在此](https://go.microsoft.com/fwlink/?LinkId=309609)下載 Windows PowerShell 3.0。

-   在執行 Windows 7 或 Windows Server 2008 R2 作業系統的電腦上安裝 .NET Framework 4 或 .NET Framework 4.5。 Windows 8、Windows 8.1 和 Windows Server 2012 作業系統隨附 .NET Framework 4.5 安裝。 Windows 10 作業系統隨附安裝 .NET Framework 4.6。
-   UE-V 不支援強制設定檔的 [刪除漫遊快取] 原則，因此不應使用此功能。



UE-V 沒有專用的隨機存取記憶體（RAM）需求。

### 透過同步處理提供者同步處理設定

同步處理提供者是使用者的預設設定，會將本機快取與這些實例中的設定儲存位置同步處理：

-   登入/登出

-   鎖定/解除鎖定

-   遠端桌面連線/中斷連接

-   開啟/關閉應用程式

[排程工作] 會每30分鐘或透過特定應用程式的觸發事件，來管理這個設定的同步處理。 如需詳細資訊，請參閱[變更 ue-v 2. x 排程任務的頻率](changing-the-frequency-of-ue-v-2x-scheduled-tasks-both-uevv2.md)。

UE-V Agent 會同步處理並非一直連線至商業網路（遠端電腦和膝上型電腦）的電腦的使用者設定，以及永遠連線至網路的電腦（執行 Windows Server 及主機虛擬桌面介面（VDI）會話的電腦）。

**同步處理具有永遠可用連線的電腦：** 當您在一直連線到網路的電腦上使用 UE-V 時，您必須設定 UE-V Agent，以使用*SyncMethod = None*參數來同步處理設定，這會將設定儲存伺服器視為標準網路共用。 在此設定中，UE-V Agent 可以設定為在應用程式設定匯入延遲時通知您。

透過下列其中一種方法來啟用此設定：

-   在 UE-V 安裝期間，請在命令提示字元或批次處理檔案中，將 AgentSetup.exe 參數*SyncMethod = None*。 [部署 ue-v 2. x 代理程式](https://technet.microsoft.com/library/dn458891.aspx#agent)會提供更多詳細資訊。

-   UE-V 安裝之後，請使用 System Center 2012 Configuration Manager 或 MDOP ADMX 範本中的設定管理功能來推*SyncMethod = None*設定。

-   使用 Windows PowerShell 或 Windows 管理工具（WMI）來設定*SyncMethod = None*配置。

    **注意**  
    這最後兩個方法不適用於虛擬桌面基礎結構（VDI）環境。



您必須先重新開機電腦，設定才會開始同步處理。

**注意**  
如果您將 [ *SyncMethod = 無*] 設定為 [無]，任何設定變更都會直接儲存到伺服器。 如果找不到設定儲存路徑的網路連線，則會將設定變更放在裝置上，並在下次同步處理提供者執行時進行同步處理。 如果找不到設定儲存路徑，且在登出時從彙集的 VDI 環境中移除使用者設定檔，則會遺失設定變更，而且當電腦重新連線至設定儲存路徑時，使用者必須重新套用變更。



**外部同步處理引擎的同步處理：***SyncMethod = External*參數指定如果 ue-v 設定是寫入使用者電腦上的本機資料夾，則任何外部同步處理引擎（例如商務用 OneDrive、工作資料夾、Sharepoint 或 Dropbox）都可以用來將這些設定套用到使用者存取的不同電腦上。

**支援共用的 VDI 會話：** UE-V 2.1 和 2.1 SP1 為在使用者之間共用的 VDI 會話提供支援。 您可以登錄並設定特殊的 VDI 範本，這可確保 UE-V 在非持久性 VDI 會話中完整保留其所有功能。

**注意**  
如果您沒有為非持久性 VDI 會話啟用 VDI 模式，則某些功能無法運作，例如[備份/還原和上次已知良好（LKG）](https://technet.microsoft.com/library/dn878331.aspx)。



VDI 範本是由 UE-V 2.1 和 2.1 SP1 提供，在安裝之後，通常可在這裡取得： C:\\program files Files\\Microsoft 使用者體驗 Virtualization\\Templates\\VdiState.xml

### UE-V 發生器支援的先決條件

在用來建立自訂設定位置範本的電腦上安裝 UE-V 發生器。 此電腦應該能夠執行其設定已同步處理的應用程式。 您必須是執行 UE-V 發生器軟體之電腦上系統管理員群組的成員。

UE-V 發生器必須安裝在使用 NTFS 檔案系統的電腦上。 UE-V 發生器軟體需要 .NET Framework 4。 如需詳細資訊，請參閱[部署自訂應用程式的 ue-v 2.](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)

## 此產品的其他資源


-   [Microsoft 使用者體驗虛擬化（UE-V） 2. x](index.md)

-   [UE-V 2.x 入門](get-started-with-ue-v-2x-new-uevv2.md)

-   [管理 UE-V 2。](administering-ue-v-2x-new-uevv2.md)

-   [疑難排解 UE-V 2. x](troubleshooting-ue-v-2x-both-uevv2.md)

-   [UE-V 2.x 技術參考](technical-reference-for-ue-v-2x-both-uevv2.md)














