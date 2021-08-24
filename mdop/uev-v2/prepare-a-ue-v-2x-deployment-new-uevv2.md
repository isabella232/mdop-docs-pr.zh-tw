---
title: 準備 2.x UE-V部署
description: 準備 2.x UE-V部署
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
ms.openlocfilehash: 3e4d4b69975deda473372345733d8e8593a4775d
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910528"
---
# <a name="prepare-a-ue-v-2x-deployment"></a>準備 2.x UE-V部署


在部署 Microsoft 消費者體驗虛擬化 (UE-V) 2.0 或 2.1 之前，您需要先進行一些規劃與準備，以在使用者存取的企業裝置之間同步處理設定。 本主題可協助您決定要執行哪種類型的部署，以及您可以事先進行哪些準備，以順利部署。

首先，讓我們來看看您將執行的工作，以部署UE-V：

-   規劃您的UE-V部署

    部署任何專案之前，一個好的第一步就是進行一些規劃，以便決定UE-V部署哪些功能。 因此，如果您離開此頁面，請確定您回來閱讀下列規劃資訊。

-   [部署 UE-V 2.x 的必要功能](deploy-required-features-for-ue-v-2x-new-uevv2.md)

    每個UE-V部署都需要這些活動：

    -   [定義設定儲存位置](https://technet.microsoft.com/library/dn458891.aspx#ssl)

    -   [決定如何部署代理程式UE-V管理UE-V組](https://technet.microsoft.com/library/dn458891.aspx#config)

    -   [在UE-V](https://technet.microsoft.com/library/dn458891.aspx#agent)同步設定的每一部使用者電腦上安裝代理程式

-   您也可以選擇部署[2.x UE-V自訂應用程式](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)

    規劃可協助您判斷您是否想要UE-V支援自訂應用程式 (協力廠商或企業行) 的設定同步處理，這需要這些UE-V功能：

    -   [安裝 UEV Generator，](https://technet.microsoft.com/library/dn458942.aspx#uevgen) 以便建立、編輯及驗證同步處理自訂應用程式設定所需的自訂設定位置範本

    -   [使用 UE-V](https://technet.microsoft.com/library/dn458942.aspx#createcustomtemplates)建立自訂設定UE-V範本

    -   [部署UE-V設定範本目錄](https://technet.microsoft.com/library/dn458942.aspx#deploycatalogue)，以儲存自訂設定位置範本

此工作流程圖表提供企業部署UE-V，以及決定企業部署UE-V決策。

![deploymentworkflow。](images/deploymentworkflow.png)

**規劃UE-V部署：** 首先，您想要進行一些規劃，以便決定UE-V部署哪些元件。 規劃部署UE-V涉及以下專案：

-   [決定是否同步處理自訂應用程式的設定](#deciding)

    這決定您是否在部署期間安裝 UE-V產生器，這可讓您建立自訂設定位置範本。 它涉及下列專案：

    查看[在部署中自動同步處理UE-V設定](#autosyncsettings)。

    [決定是否需要同步處理其他應用程式的設定](#determinesettingssync)。

-   請[審查部署應用程式的其他UE-V，](#considerations)例如高可用性和容量規劃。

-   [確認系統的先決條件和支援UE-V](#prereqs)

## <a name="decide-whether-to-synchronize-settings-for-custom-applications"></a><a href="" id="deciding"></a>決定是否要同步設定自訂應用程式


在部署UE-V，許多設定會自動同步處理。 但您也可以自訂UE-V，以同步處理其他應用程式的設定，例如企業經營和協力廠商應用程式。

決定是否要同步UE-V自訂應用程式的設定，可能是規劃您的部署UE-V部分。 本節的主題可協助您做出決策。

### <a name="settings-that-are-automatically-synchronized-in-a-ue-v-deployment"></a><a href="" id="autosyncsettings"></a>設定部署中自動同步處理UE-V同步處理

本節提供有關預設在 UE-V 同步設定的資訊，包括下列：

預設同步處理其設定的桌面應用程式

Windows同步的桌面設定

支援應用程式設定同步Windows聲明

請參閱 Microsoft Office 的使用者體驗[虛擬化 (UE-V) ](https://www.microsoft.com/download/details.aspx?id=46367)設定範本，以下載由 UE-V 同步的特定 Microsoft Office 2013、Microsoft Office 2010 和 Microsoft Office 2007 設定的完整清單。

### <a name="desktop-applications-synchronized-by-default-in-ue-v-21-and-ue-v-21-sp1"></a>桌面應用程式預設在 UE-V 2.1 和 UE-V 2.1 SP1 中同步處理

當您安裝 UE-V 2.1 或 2.1 SP1 代理程式時，它會註冊一組預設設定位置範本，以捕獲這些常見 Microsoft 應用程式的設定值。

**提示**  
**Microsoft Office 2007**設定同步處理 – 在 UE-V 2.1 和 2.1 SP1 中，Office 2007 應用程式預設不再包含設定位置範本。 不過，您仍然可以使用 Office 2.0 UE-V 2007 範本，並可以從 UE-V 範本庫中[取得範本](https://go.microsoft.com/fwlink/p/?LinkID=246589)。



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
<p> (<a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)"> 下載所有已同步) </a></p></td>
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
<p>Microsoft SharePoint設計工具 2010</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Office 2013 應用程式</p>
<p> (<a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)"> 下載所有已同步) </a></p></td>
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
<p>Microsoft SharePoint設計工具 2013</p>
<p>Microsoft Office 2013 Upload中心</p>
<p>Microsoft OneDrive商務用 2013</p>
<p>2013 UE-V 2.1 和 2.1 SP1 Microsoft Office設定位置範本包含改良Outlook簽名支援。 我們已新增新電子郵件、回復和轉轉電子郵件的預設簽名設定同步處理功能。</p>
<div class="alert">
<strong>注意</strong><br/><p>使用者Outlook要同步其簽名的任何裝置，都必須建立Outlook設定檔。 如果設定檔尚未建立，使用者可以建立設定檔，然後重新開機Outlook，以啟用簽名同步處理。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>瀏覽器選項：Internet Explorer 8、Internet Explorer 9、Internet Explorer 10和 Internet Explorer 11</p></td>
<td align="left"><p>我的最愛、首頁、定位停駐點和工具列。</p>
<div class="alert">
<strong>注意</strong><br/><p>UE-V Internet Explorer Cookie 的漫遊設定。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>Windows配件</p></td>
<td align="left"><p>Microsoft 小算盤、記事本、WordPad。</p></td>
</tr>
</tbody>
</table>



**注意**  
UE-V 2.1 SP1 不會同步處理 Microsoft 小算盤 中的Windows 10與Microsoft 小算盤作業系統中的設定。



### <a name="desktop-applications-synchronized-by-default-in-ue-v-20"></a>桌面應用程式預設在 UE-V 2.0 中同步處理

當您安裝 UE-V 2.0 Agent 時，它會註冊一組預設設定位置範本，以捕獲這些常見 Microsoft 應用程式的設定值。

**提示**  
**Microsoft Office 2013**設定同步處理 – 在 UE-V 2.0 中，Office 2013 應用程式預設不會包含設定位置範本，但可從[UE-V](https://go.microsoft.com/fwlink/p/?LinkID=246589)範本庫下載。 [使用 Office 2.0 同步處理 2013](synchronizing-office-2013-with-ue-v-20-both-uevv2.md) UE-V提供同步處理 2013 設定Office範本的詳細資訊。



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
<p> (<a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)"> 下載所有已同步) </a></p></td>
<td align="left"><p>Microsoft Access 2007</p>
<p>Microsoft Communicator 2007</p>
<p>Microsoft Excel 2007</p>
<p>Microsoft InfoPath 2007</p>
<p>Microsoft OneNote 2007</p>
<p>Microsoft Outlook 2007</p>
<p>Microsoft PowerPoint 2007</p>
<p>Microsoft Project 2007</p>
<p>Microsoft Publisher 2007</p>
<p>Microsoft SharePoint設計工具 2007</p>
<p>Microsoft Visio 2007</p>
<p>Microsoft Word 2007</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Office 2010 應用程式</p>
<p> (<a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)"> 下載所有已同步) </a></p></td>
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
<p>Microsoft SharePoint設計工具 2010</p></td>
</tr>
<tr class="odd">
<td align="left"><p>瀏覽器選項：Internet Explorer 8、Internet Explorer 9 和 Internet Explorer 10</p></td>
<td align="left"><p>我的最愛、首頁、定位停駐點和工具列。</p>
<div class="alert">
<strong>注意</strong><br/><p>UE-V Internet Explorer Cookie 的漫遊設定。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>Windows配件</p></td>
<td align="left"><p>Microsoft 小算盤、記事本、WordPad。</p></td>
</tr>
</tbody>
</table>



### <a name="windows-settings-synchronized-by-default"></a><a href="" id="autosyncsettings2"></a>Windows同步設定

UE-V包含可捕獲這些設定之設定值的設定位置Windows範本。

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
<th align="left">適用于</th>
<th align="left">匯出于</th>
<th align="left">預設狀態</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>桌面背景</p></td>
<td align="left"><p>目前使用中桌面背景或牆紙。</p></td>
<td align="left"><p>登入、解除鎖定、遠端連線、排定的任務事件。</p></td>
<td align="left"><p>登出、鎖定、遠端中斷連接、使用者按一下 設定 中心中的立即同步處理， <strong> </strong> 或排定的工作間隔</p></td>
<td align="left"><p>啟用</p></td>
</tr>
<tr class="even">
<td align="left"><p>輕鬆存取</p></td>
<td align="left"><p>協助工具和輸入設定、Microsoft 放大鏡、旁白和螢幕小鍵盤。</p></td>
<td align="left"><p>僅登入。</p></td>
<td align="left"><p>登出、使用者按一下在公司 <strong> </strong> 中心設定立即同步處理，或排定的工作間隔</p></td>
<td align="left"><p>啟用</p></td>
</tr>
<tr class="odd">
<td align="left"><p>桌面設定</p></td>
<td align="left"><p>[開始] 功能表工作列設定、資料夾選項、預設桌面圖示、其他時鐘，以及地區與語言設定。</p></td>
<td align="left"><p>僅登入。</p></td>
<td align="left"><p>登出、使用者按一下在公司 <strong> </strong> 中心設定立即同步處理，或排定的工作</p></td>
<td align="left"><p>啟用</p></td>
</tr>
</tbody>
</table>



**注意**  
從 Windows 8開始，UE-V不會漫遊與開始畫面相關的設定，例如專案和位置。 此外，UE-V釘釘工作列專案或檔案快捷方式Windows同步處理。



**重要**  
UE-V 2.1 SP1 在裝置之間漫遊工作列Windows 10設定。 不過，UE-V不會同步處理Windows 10裝置與執行先前作業系統的裝置之間的工作列設定。



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
<th align="left">捕獲</th>
<th align="left">[套用]</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>應用程式設定</strong></p></td>
<td align="left"><p>Windows 應用程式</p></td>
<td align="left"><p>關閉應用程式</p>
<p>Windows應用程式設定變更事件</p></td>
<td align="left"><p>啟動時UE-V應用程式監視器</p>
<p>開啟應用程式</p>
<p>Windows應用程式設定變更事件</p>
<p>設定套件的抵達</p></td>
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
<td align="left"><p>登入、解除鎖定、遠端連線、新包裹抵達通知、使用者按一下在公司中心設定立即同步處理，或執行排定 <strong> </strong> 的工作。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p>輕鬆存取 (- 協助工具、旁白、放大鏡、螢幕-鍵盤) </p></td>
<td align="left"><p>鎖定或登出</p></td>
<td align="left"><p>登錄</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p>輕鬆存取 shell (- 音訊、協助工具、鍵盤、滑鼠) </p></td>
<td align="left"><p>鎖定或登出</p></td>
<td align="left"><p>登入、解除鎖定、遠端連線、新包裹抵達通知、使用者按一下 設定 中心中的立即同步處理， <strong> </strong> 或已排程任務執行</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p>桌面設定</p></td>
<td align="left"><p>鎖定或登出</p></td>
<td align="left"><p>登錄</p></td>
</tr>
</tbody>
</table>



### <a name="ue-v-support-for-windows-apps"></a>UE-V應用程式Windows支援

針對Windows，應用程式開發人員會指定同步的設定。 您可以指定哪些Windows應用程式啟用設定同步處理。

若要顯示可Windows套件家庭名稱、啟用狀態及已啟用來源之設定的電腦應用程式清單，請在Windows PowerShell提示輸入： `Get-UevAppxPackage`

**注意**  
截至Windows 8，UE-V網域使用者Windows其 Microsoft 帳戶的登錄認證時，系統不會同步Windows應用程式設定。 此連結會同步處理Microsoft OneDrive，UE-V同步處理應用程式Windows同步處理。



### <a name="ue-v-support-for-roaming-printers"></a>UE-V漫遊印表機的客戶支援

UE-V 2.1 SP1 可讓網路印表機在裝置之間漫遊，讓使用者在登入網路的任何裝置時，能夠存取其網路印表機。 這包括漫遊他們設定為預設值的印表機。

印表機在 UE-V漫遊需要以下其中一種情況：

-   當列印伺服器漫遊到新裝置時，可以下載所需的驅動程式。

-   漫遊網路印表機的驅動程式已預先安裝在任何需要存取網路印表機的裝置上。

-   印表機驅動程式可以從更新Windows取得。

**注意**  
印表機UE-V漫遊功能**不會**漫遊印表機設定或喜好設定，例如雙面列印。



### <a name="determine-whether-you-need-settings-synchronized-for-other-applications"></a><a href="" id="determinesettingssync"></a>判斷您是否需要同步處理其他應用程式的設定

在您查看在 UE-V 部署中自動同步處理設定之後，您想要決定是否要同步處理其他應用程式的設定，因為這會決定您在整個UE-V部署的方式。

做為系統管理員，當您考慮要納入 UE-V 解決方案中的桌面應用程式時，請考慮使用者可以自訂哪些設定，以及應用程式儲存其設定的方法和位置。 並非所有桌面應用程式都有可自訂或使用者例行自訂的設定。 此外，並非所有桌面應用程式設定都可以安全地跨多部電腦或環境同步處理。

一般而言，您可以同步設定，符合下列準則：

-   設定儲存在使用者易於訪問的位置。 例如，請勿同步處理儲存在 System32 或 HKEY\_CURRENT\_USER (HKCU) 區段外的設定。

-   設定特定電腦的特定資料。 例如，排除網路或硬體組組。

-   設定在電腦之間同步處理，而不會有資料損壞的風險。 例如，請勿使用儲存在資料庫檔案中的設定。

### <a name="checklist-for-evaluating-custom-applications"></a><a href="" id="checklistsettingssync"></a>評估自訂應用程式的檢查清單

如果您決定需要同步處理其他應用程式的設定，您可以使用這份檢查清單來協助瞭解您將包含哪些應用程式。

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
<td align="left"><p>此應用程式是否包含使用者可以自訂的設定？</p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>同步這些設定對於使用者來說很重要嗎？</p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>這些使用者設定是否已經由應用程式管理或設定策略解決方案管理？ UE-V應用程式啟動時，會使用應用程式設定，Windows登入、解除鎖定或遠端連線事件時設定。 如果您使用其他UE-V共用解決方案，使用者可能會遇到同步設定之間的不一致。</p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>應用程式設定是否特定于電腦？ 與硬體或特定電腦設定相關聯的應用程式喜好設定和自訂專案無法跨會話一致地同步處理，並可能導致應用程式體驗不佳。</p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>應用程式是否將設定儲存在 [程式檔案] 目錄或位於 [使用者名稱] 強 <strong> </strong> &lt; &gt; AppData </strong> &lt; 強 &gt; LocalLow 目錄的檔案 </strong> 目錄中？ 儲存在上述任一位置的應用程式資料通常不應與使用者同步處理，因為這些資料是電腦特有的資料，或因為資料太大無法同步處理。</p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>應用程式是否將任何設定儲存在檔案中，其中包含不應同步處理的其他應用程式資料？ UE-V將檔案同步處理為單一單元。 如果設定儲存在包含設定外的應用程式資料的檔案中，則同步處理此額外資料可能會導致應用程式體驗不佳。</p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>包含這些設定的檔案大小如何？ 設定同步處理效果會受到大型檔案影響。 包含大型檔案可能會影響設定同步處理的表現。</p></td>
</tr>
</tbody>
</table>



## <a name="other-considerations-when-preparing-a-ue-v-deployment"></a><a href="" id="considerations"></a>準備部署時的其他UE-V考慮


當您準備部署以下專案時，您也應該UE-V：

-   [管理認證同步處理](#creds)

-   [Windows應用程式設定同步處理](#appxsettings)

-   [自訂UE-V設定位置範本](#custom)

-   [非故意的使用者設定設定](#prevent)

-   [績效與容量](#capacity)

-   [高可用性](#high)

-   [電腦時鐘同步處理](#clocksync)

### <a name="managing-credentials-synchronization-in-ue-v-21-and-ue-v-21-sp1"></a><a href="" id="creds"></a>管理 2.1 UE-V 2.1 SP1 UE-V認證同步處理

許多企業應用程式 ，包括 Microsoft Outlook Lync，會在登入時提示使用者提供其網域認證。 使用者可以選擇將認證存到磁片，以避免每次開啟這些應用程式時都輸入。 啟用漫遊認證同步處理可讓使用者將認證儲存于一部電腦上，並避免在環境中使用的每一部電腦上重新輸入認證。 使用者可以將部分網域認證與 UE-V 2.1 和 2.1 SP1 同步處理。

**重要**  
認證同步處理預設為停用。 您必須在部署期間明確啟用認證同步處理，才能執行這項功能。



UE-V 2.1 和 2.1 SP1 可以同步企業認證，但請勿漫遊僅供本地電腦上使用的認證。

認證是同步設定，也就是說，當您在同步處理之後第一次登入電腦時，認證會UE-V設定檔。

認證同步處理是由自己的設定位置範本管理，預設會停用此範本。 您可以透過其他範本所使用的相同方法啟用或停用此範本。 此功能的範本識別碼為 RoamingCredentialSettings。

**重要**  
如果您在環境中使用 Active Directory 認證漫遊，建議您不要啟用 UE-V認證漫遊範本。



使用其中一種方法啟用認證同步處理：

-   公司設定中心

-   PowerShell

-   群組原則

**注意**  
同步處理期間會加密認證。



[公司設定](https://technet.microsoft.com/library/dn458903.aspx)**中心：** 勾選 設定 下的漫遊認證Windows 設定以啟用認證同步處理。 取消勾選方塊以停用它。 如果您的帳戶未設定為使用 Microsoft 帳戶同步設定，此核取方塊只會出現在公司中心。

[PowerShell：](https://technet.microsoft.com/library/dn458937.aspx)**** 此 PowerShell Cmdlet 可啟用認證同步處理：

``` syntax
Enable-UevTemplate RoamingCredentialSettings
```

此 PowerShell Cmdlet 會停用認證同步處理：

``` syntax
Disable-UevTemplate RoamingCredentialSettings
```

[群組原則](https://technet.microsoft.com/library/dn458893.aspx)**：** 您必須 [部署最新的 MDOP ADMX 範本](https://go.microsoft.com/fwlink/p/?LinkId=393944) ，才能透過群組原則啟用認證同步處理。 認證同步處理是使用Windows管理。 若要使用群組原則管理此功能，請啟用同步處理Windows設定策略。

1.  開啟群組原則編輯器，然後流覽至使用者組Windows管理範本 **– Microsoft 消費者體驗虛擬化。**

2.  按兩下 [同步**Windows設定**。

3.  如果已啟用此策略，您可以檢查漫遊認證核取方塊來啟用認證同步處理****，或取消勾選以停用認證同步處理。

4.  按一下**確定**。

### <a name="credential-locations-synchronized-by-ue-v"></a>認證位置已同步UE-V

應用程式儲存至下列位置的認證檔案會同步處理：

-   %UserProfile%\\AppData\\Roaming\\Microsoft\\Credentials\\

-   %UserProfile%\\AppData\\Roaming\\Microsoft\\Crypto\\

-   %UserProfile%\\AppData\\Roaming\\Microsoft\\Protect\\

-   %UserProfile%\\AppData\\Roaming\\Microsoft\\SystemCertificates\\

儲存至其他位置的認證不會同步UE-V。

### <a name="windows-app-settings-synchronization"></a><a href="" id="appxsettings"></a>Windows應用程式設定同步處理

UE-V三Windows管理應用程式設定同步處理：

-   **同步Windows應用程式：** 允許或拒絕任何應用程式Windows同步處理

-   **Windows應用程式清單：** 同步管理應用程式Windows清單

-   **未列出的預設同步執行行為：** 判斷未Windows應用程式清單中的應用程式Windows行為。

詳細資訊，請參閱應用程式Windows[清單](https://technet.microsoft.com/library/dn458925.aspx#win8applist)。

### <a name="custom-ue-v-settings-location-templates"></a><a href="" id="custom"></a>自訂UE-V設定位置範本

如果您要部署 UE-V同步處理自訂應用程式的設定，您將使用 UE-V Generator 為這些桌面應用程式建立自訂設定位置範本。 在測試環境中建立和測試自訂設定位置範本之後，您可以將設定位置範本部署到企業中的電腦。

自訂設定位置範本必須使用現有的部署基礎結構進行部署，例如企業軟體發佈 (ESD) 方法 ，例如 System Center Configuration Manager、喜好設定，或設定 UE-V 設定範本目錄。 使用 Configuration Manager 或群組原則部署的範本必須使用 WMI 或 UE-V 註冊Windows PowerShell。

有關自訂設定位置範本的資訊，請參閱部署[UE-V 2.x 自訂應用程式 。](deploy-ue-v-2x-for-custom-applications-new-uevv2.md) 有關在 Configuration Manager 中UE-V，請參閱在[2012 UE-V 2.x 中System Center Configuration Manager 2.x。](configuring-ue-v-2x-with-system-center-configuration-manager-2012-both-uevv2.md)

### <a name="prevent-unintentional-user-settings-configuration"></a><a href="" id="prevent"></a>防止非故意的使用者設定設定

UE-V從設定儲存位置下載新的使用者設定資訊，並在這些實例中將設定適用于本地電腦：

-   每次啟動具有已註冊範本UE-V應用程式。

-   當使用者登錄電腦時。

-   當使用者解除鎖定電腦時。

-   當連接到已安裝遠端桌面電腦的UE-V。

-   執行同步控制器應用程式排程任務時。

如果UE-V A 和電腦 B 上安裝，而您想要的應用程式設定是在電腦 A 上，則電腦 A 應先開啟並關閉應用程式。 如果應用程式先在電腦 B 上開啟和關閉，則電腦上的應用程式設定會設定為電腦上的應用程式設定 B。設定 會根據每個應用程式在電腦之間同步處理。 隨著時間的過去，設定在電腦之間會隨著偏好設定而開啟和關閉時保持一致。

此案例也適用于Windows設定。 如果Windows B 上的設定應該與電腦 A Windows設定相同，則使用者應該先登入並登出電腦 A。

如果使用者想要的使用者設定以錯誤的順序使用，可以在被覆蓋設定的電腦上，針對特定應用程式或 Windows 設定執行還原作業，以復原這些設定。 詳細資訊，請參閱在[2.x UE-V管理備份和還原](manage-administrative-backup-and-restore-in-ue-v-2x-new-topic-for-21.md)。

### <a name="performance-and-capacity-planning"></a><a href="" id="capacity"></a>績效與容量規劃

使用標準磁片容量UE-V網路健康情況監控來指定您的需求。

UE-V使用伺服器訊息封鎖 (SMB) 共用來儲存設定套件。 設定套件的大小會因每個應用程式的設定資訊而異。 雖然大部分設定套件都很小，但同步處理可能的大型檔案 ，例如桌面影像，可能會導致不佳的績效，尤其是在網路速度變慢時。

若要減少網路延遲的問題，請于使用者電腦所在的同一個本地網路上建立設定儲存位置。 我們建議您為每個使用者設定儲存位置的磁碟空間為 20 MB。

根據預設，UE-V同步處理時間超過 2 秒，以避免因大型設定套件而過度延遲。 您可以使用群組原則物件來設定 SyncMethod=SyncProvider [設定](https://technet.microsoft.com/library/dn458893.aspx)。

### <a name="high-availability-for-ue-v"></a><a href="" id="high"></a>適用于 UE-V

設定UE-V位置和設定範本目錄支援在任何可寫入的共用上儲存使用者資料。 若要確保高可用性，請遵循下列準則：

-   使用 NTFS 檔案系統格式化儲存空間。

-   共用可以在 DFS (使用分散式檔案系統) 但有限制。
具體來說，支援具有或不含分散式檔案系統命名空間 (DFS-N) 的分散式檔案系統複製 (DFS-N) 目標群組。
同樣地，DFS-N 僅支援單一目標群組式。
有關詳細資訊，請參閱 [Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=313991) 關於複製使用者設定檔資料的支援聲明，以及 [DFS-R 和 DFS-N](https://support.microsoft.com/kb/2533009)部署案例的 Microsoft 支援政策相關資訊。

    此外，由於 SYSVOL 使用 DFS-R 進行複製，因此 SYSVOL UE-V資料檔案複製。

-   設定共用許可權和 NTFS 存取控制清單 (ACL) 如部署 設定 儲存體 位置 UE-V [2.x](https://technet.microsoft.com/library/dn458891.aspx#ssl)中指定。

-   使用檔案伺服器集UE-V代理程式，在通訊失敗時提供使用者狀態資料複本的存取權。

-   您可以將設定儲存路徑資料儲存 (資料) 組集共用、DFS-N 共用或兩者上的設定範本目錄範本。

### <a name="synchronize-computer-clocks-for-ue-v-settings-synchronization"></a><a href="" id="clocksync"></a>同步處理電腦時鐘UE-V設定同步處理

執行代理程式UE-V必須使用時間伺服器來維持一致的設定體驗。 UE-V時間戳記來判斷設定是否必須從設定儲存位置同步。 如果電腦時鐘不正確，較舊的設定可能會覆寫較新的設定，或新設定可能不會儲存到設定儲存位置。

## <a name="confirm-prerequisites-and-supported-configurations-for-ue-v"></a><a href="" id="prereqs"></a>確認系統的先決條件和支援UE-V


在繼續之前，請確定您的環境包含執行此UE-V。

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
<th align="left"><strong>Service Pack</strong></th>
<th align="left"><strong>系統架構</strong></th>
<th align="left"><strong>Windows PowerShell</strong></th>
<th align="left"><strong>Microsoft .NET Framework</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows 7</p></td>
<td align="left"><p>終極版、Enterprise版或 Professional版</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>32 位元或 64 位元</p></td>
<td align="left"><p>Windows PowerShell 3.0 或更高版本</p></td>
<td align="left"><p>.NET Framework 2.1 的 UE-V 4.5 或更高版本。</p>
<p>.NET Framework 2.0 UE-V 4 或更高版本。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2008 R2</p></td>
<td align="left"><p>標準、Enterprise、資料中心或 Web Server</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 位元</p></td>
<td align="left"><p>Windows PowerShell 3.0 或更高版本</p></td>
<td align="left"><p>.NET Framework 2.1 的 UE-V 4.5 或更高版本。</p>
<p>.NET Framework 2.0 UE-V 4 或更高版本。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows 8和Windows 8.1</p></td>
<td align="left"><p>Enterprise或Pro</p></td>
<td align="left"><p>無</p></td>
<td align="left"><p>32 位元或 64 位元</p></td>
<td align="left"><p>Windows PowerShell 3.0 或更高版本</p></td>
<td align="left"><p>.NET Framework 4.5 或更高版本</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 10 1607 之前的版本</p>
<div class="alert">
<strong>注意</strong><br/><p>只有 UE-V 2.1 SP1 Windows 10 1607 之前的版本</p>
</div>
<div>

</div></td>
<td align="left"><p>Enterprise或Pro</p></td>
<td align="left"><p>無</p></td>
<td align="left"><p>32 位元或 64 位元</p></td>
<td align="left"><p>Windows PowerShell 3.0 或更高版本</p></td>
<td align="left"><p>.NET Framework 4.6</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2012和 Windows Server 2012 R2</p></td>
<td align="left"><p>標準或資料中心</p></td>
<td align="left"><p>無</p></td>
<td align="left"><p>64 位元</p></td>
<td align="left"><p>Windows PowerShell 3.0 或更高版本</p></td>
<td align="left"><p>.NET Framework 4.5 或更高版本</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2016</p></td>
<td align="left"><p>標準或資料中心</p></td>
<td align="left"><p>無</p></td>
<td align="left"><p>64 位元</p></td>
<td align="left"><p>Windows PowerShell 3.0 或更高版本</p></td>
<td align="left"><p>.NET Framework 4.6 或更高版本</p></td>
</tr>
</tbody>
</table>



也。。。

-   **MDOP 授權：** 這項技術是 MICROSOFT 桌面優化套件的一部分， (MDOP) 。 Enterprise Microsoft 軟體保證取得 MDOP。 有關 Microsoft 軟體保證和取得 MDOP 的資訊，請參閱如何取得 MDOP https://go.microsoft.com/fwlink/p/?LinkId=322049) (。

-   **將安裝** 之任何電腦的系統管理認證

**注意**  

-   從 WIndows 10 版本 1607 開始，UE-V 已包含在 Windows 10 Enterprise 中[，](https://www.microsoft.com/WindowsForBusiness/windows-for-enterprise)且不再是 Microsoft 桌面優化套件的一部分。

-   UE-V Windows PowerShell代理程式UE-V功能.NET Framework 4 或更新Windows PowerShell 3.0 或更新。 在這裡Windows PowerShell 3.0。 [](https://go.microsoft.com/fwlink/?LinkId=309609)

-   在.NET Framework 7 或 .NET Framework Server 2008 R2 作業系統的電腦上，Windows 4 或 Windows 4.5。 系統Windows 8、Windows 8.1和 Windows Server 2012 4.5 .NET Framework一起安裝。 系統Windows 10隨附 4.6 .NET Framework 4.6。
-   系統不支援強制設定檔的「刪除漫遊緩存」UE-V，因此不應使用。



RAM 沒有特殊的隨機存取記憶體 (記憶體) 特定需求UE-V。

### <a name="synchronization-of-settings-through-the-sync-provider"></a>透過同步設定同步處理同步處理

同步處理提供者是使用者的預設設定，會同步處理本機快取與這些實例中的設定儲存位置：

-   登入/登出

-   鎖定/解除鎖定

-   遠端桌面連線/中斷連接

-   應用程式開啟/關閉

排程任務每隔 30 分鐘管理此設定同步處理，或透過特定應用程式的特定觸發事件管理此同步處理。 詳細資訊，請參閱變更[2.x UE-V排程工作的頻率](changing-the-frequency-of-ue-v-2x-scheduled-tasks-both-uevv2.md)。

UE-V 代理程式會同步處理不一定連接到商業網路的電腦 (遠端電腦和膝上型電腦) 以及一直連接到網路的電腦 (執行 Windows Server 和主機虛擬桌面介面 (VDI) 會話) 的電腦的使用者設定。

**具有隨時可用連結的電腦同步處理：** 當您在UE-V電腦上使用 UE-V 時，您必須設定 UE-V Agent，以使用 SyncMethod=None 參數同步處理設定，而*SyncMethod=None*參數會將設定儲存伺服器視為標準網路共用。 在此設定中，UE-V代理程式可以設定為通知應用程式設定是否延遲的輸入。

透過以下其中一種方法啟用此組組：

-   安裝UE-V，在命令提示符或批次處理檔案中，設定 AgentSetup.exe *SyncMethod = None*。 [部署 2.x UE-V代理](https://technet.microsoft.com/library/dn458891.aspx#agent)程式會提供詳細資訊。

-   安裝UE-V之後，請使用 設定 2012 Configuration Manager 中的 System Center 管理功能或 MDOP ADMX 範本來推送*SyncMethod = None*組式。

-   使用 Windows PowerShell 或 Windows管理 (套) 設定*SyncMethod = None*設定。

    **注意**  
    這兩種方法在 VDI 或 VDI 環境中無法 (虛擬) 基礎結構。



您必須重新開機電腦，才能開始同步設定。

**注意**  
如果您設定 *SyncMethod = None，* 任何設定變更會直接儲存至伺服器。 如果找不到與設定儲存路徑的網路連接，則設定變更會緩存在裝置上，且同步化提供者下次執行時會同步。 如果找不到設定儲存路徑，且登出時使用者設定檔已從集中式 VDI 環境移除，則設定變更會遺失，且使用者必須在電腦重新連接到設定儲存路徑時重新申請變更。



**外部同步處理引擎的同步處理：***SyncMethod=External*參數指定如果 UE-V 設定寫入使用者電腦上的本地資料夾，則任何外部同步處理引擎 (例如 商務用 OneDrive、工作資料夾、Sharepoint 或 Dropbox) 都可以用來將這些設定適用于使用者存取的不同電腦。

**支援共用的 VDI 會話：UE-V** 2.1 和 2.1 SP1 提供 VDI 會話的支援，供使用者共用。 您可以註冊和設定特殊的 VDI 範本，UE-V非持續性 VDI 會話保持其所有功能不變。

**注意**  
如果您未針對非持續性 VDI 會話啟用 VDI 模式，某些功能無法運作，例如備份/還原和上次已知良好[ (LKG) 。](https://technet.microsoft.com/library/dn878331.aspx)



VDI 範本提供 UE-V 2.1 和 2.1 SP1，一般可在安裝之後在這裡使用：C：\\Program Files\\Microsoft 使用者體驗Virtualization\\Templates\\VdiState.xml

### <a name="prerequisites-for-ue-v-generator-support"></a>使用產生器支援UE-V先決條件

在UE-V用來建立自訂設定位置範本的電腦上安裝 UE-V Generator。 此電腦應該可以執行其設定已同步處理的應用程式。 您必須是執行 UE-V 軟體之電腦的系統管理員群組成員。

UE-V產生器必須安裝在使用 NTFS 檔案系統的電腦上。 UE-V產生器軟體需要 .NET Framework 4。 詳細資訊，請參閱部署[UE-V 2.x 自訂應用程式 。](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)

## <a name="other-resources-for-this-product"></a>此產品的其他資源


-   [Microsoft 消費者體驗虛擬化 (UE-V) 2.x](index.md)

-   [UE-V 2.x 入門](get-started-with-ue-v-2x-new-uevv2.md)

-   [管理 UE-V 2.x](administering-ue-v-2x-new-uevv2.md)

-   [2.x UE-V疑難排解](troubleshooting-ue-v-2x-both-uevv2.md)

-   [UE-V 2.x 技術參考](technical-reference-for-ue-v-2x-both-uevv2.md)














