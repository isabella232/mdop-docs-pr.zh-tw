---
title: 為搭配 Office 使用 App-V 進行規劃
description: 為搭配 Office 使用 App-V 進行規劃
author: dansimp
ms.assetid: c4371869-4bfc-4d13-9198-ef19f99fc192
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ff523c8f8827e295c8fb9a2d9fd0e02d5b019aa8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800340"
---
# 為搭配 Office 使用 App-V 進行規劃


使用下列資訊來規劃如何使用 App-v 來部署 Office。 本文包括：

-   [語言套件的 app-v 支援](#bkmk-lang-pack)

-   [支援的 Microsoft Office 版本](#bkmk-office-vers-supp-appv)

-   [規劃與共存版本的 Office 一起使用 App-v](#bkmk-plan-coexisting)

-   [部署時，Office 與 Windows 整合的方式使用 App-v 部署 Office](#bkmk-office-integration-win)

## <a href="" id="bkmk-lang-pack"></a>語言套件的 app-v 支援


您可以使用 App-v 5.0 Sequencer 來建立語言套件、語言介面套件、校訂工具及工具提示語言的外掛程式套件。 接著，您可以在連線群組中包含外掛程式套件，以及使用 Office 部署工具組建立的 Office 2013 套件。 Office 應用程式和外掛程式語言套件在相同的連線群組中無縫互動，就像在連線群組中組成群組的任何其他套件一樣。

**記事** Microsoft Visio 與 Microsoft Project 不提供泰語語言套件支援。

 

## <a href="" id="bkmk-office-vers-supp-appv"></a>支援的 Microsoft Office 版本


下表列出 App-v 所支援的 Microsoft Office 版本、Office 套件建立的方法、支援的授權，以及支援的部署。

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
<th align="left">支援的 Office 版本</th>
<th align="left">支援的 App-v 版本</th>
<th align="left">建立套件</th>
<th align="left">支援的授權</th>
<th align="left">支援的部署</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>適用于企業的 Microsoft 365 應用程式</p>
<p>還支援：</p>
<ul>
<li><p>Visio Pro for Office 365</p></li>
<li><p>Project Pro for Office 365</p></li>
</ul></td>
<td align="left"><ul>
<li><p>App-V 5。0</p></li>
<li><p>App-V 5.0 SP1</p></li>
<li><p>App-v 5.0 SP2</p></li>
</ul></td>
<td align="left"><p>Office 部署工具</p></td>
<td align="left"><p>訂閱</p></td>
<td align="left"><ul>
<li><p>桌面</p></li>
<li><p>個人 VDI</p></li>
<li><p>[彙集] VDI</p></li>
<li><p>句</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>Office 專業增強版2013</p>
<p>還支援：</p>
<ul>
<li><p>Visio 專業版2013</p></li>
<li><p>Project 專業版2013</p></li>
</ul></td>
<td align="left"><ul>
<li><p>App-V 5。0</p></li>
<li><p>App-V 5.0 SP1</p></li>
<li><p>App-v 5.0 SP2</p></li>
</ul></td>
<td align="left"><p>Office 部署工具</p></td>
<td align="left"><p>大量授權</p></td>
<td align="left"><ul>
<li><p>桌面</p></li>
<li><p>個人 VDI</p></li>
<li><p>[彙集] VDI</p></li>
<li><p>句</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-plan-coexisting"></a>規劃與共存版本的 Office 一起使用 App-v


您可以在同一部電腦上使用「Microsoft Office 共存」，並排安裝多個版本的 Microsoft Office。 您可以使用 Windows Installer （MSi）版本的 Office、隨選即用，以及 App-v 5.0 SP2，來實現 Office 共存，以及所有主要版本的 Office 與安裝方法的結合。 不過 Microsoft 不建議使用 Office 共存。

Microsoft 的建議最佳做法是完全避免 Office 共存，以避免相容性問題。 不過，當您遷移至較新版本的 Office 時，偶爾會出現無法立即解決的問題，因此您可以暫時實現共存，協助您更快速地遷移到最新的產品版本。 我們不建議使用長期基礎的 Office 共存，而且您的組織應該有一個計畫在立即進行。

### 在您實現 Office 共存之前

在執行 Office 共存之前，請先查看下列 Office 檔。 選擇對應到最新版本的 Office 的文章，您打算在該文章中實施共存。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Office 版本</th>
<th align="left">連結至指南</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Office 2013</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2784668" data-raw-source="[Information about how to use Office 2013 suites and programs (MSI deployment) on a computer that is running another version of Office](https://support.microsoft.com/kb/2784668)">如何在執行其他 Office 版本的電腦上使用 Office 2013 套件與程式（MSI 部署）的相關資訊</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>Office 2010</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2121447" data-raw-source="[Information about how to use Office 2010 suites and programs on a computer that is running another version of Office](https://support.microsoft.com/kb/2121447)">如何在執行其他 Office 版本的電腦上使用 Office 2010 套件與程式的相關資訊</a></p></td>
</tr>
</tbody>
</table>

 

Office 檔針對 Office 的 Windows 安裝程式（MSi）與隨選即用安裝，提供大量的共存指導方針。 此 App-v 主題的共存是對 Office 指南進行補充，其資訊更特定于 App-v 部署。

### 支援的 Office 共存案例

下表摘要列出支援的共存案例。 根據您開始使用的版本和部署方法，以及您要遷移的版本和部署方法來組織它們。 在將所有共存解決方案部署到成品物件之前，請務必先完整測試。

**記事** Microsoft 不支援在已啟用遠端桌面工作階段主機角色服務的 Windows Server 環境中使用多個版本的 Office。 若要執行 Office 共存案例，您必須停用此角色服務。

 

### Windows 集成 & 的 Office 共存

Windows 安裝程式與隨選即用 Office 安裝方法會與基礎 Windows 作業系統的特定點整合。 當您使用共存功能時，在兩個 Office 版本之間的一般作業系統整合可能會衝突，從而導致相容性與使用者體驗問題。 在 App-v 中，您可以將某些版本的 Office 排序，以排除整合，從而將它們「隔離」至作業系統。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left">在此模式中，App-v 可將這個版本的 Office 排序</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Office 2007</p></td>
<td align="left"><p>永遠不會整合。 App-v 不會提供與虛擬化版本的 Office 2007 有關的任何作業系統整合。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Office 2010</p></td>
<td align="left"><p>整合和非整合模式。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Office 2013</p></td>
<td align="left"><p>永遠整合。 Windows 作業系統集成無法停用。</p></td>
</tr>
</tbody>
</table>

 

Microsoft 建議您只使用一個整合的 Office 實例來部署 Office 共存。 例如，如果您使用 App-v 來部署 Office 2010 和 Office 2013，您應該在非整合模式中順序排列 Office 2010。 如需在非整合（獨立）模式中排序 Office 的詳細資訊，請參閱[如何在 Microsoft Application Virtualization 5.0 中排序 Microsoft Office 2010](https://support.microsoft.com/kb/2830069)。

### Office 共存案例的已知限制

下列各節說明當您使用 App-v 來實現與 Office 的共存時，可能會遇到的一些問題。

### Windows 安裝程式/隨選即用與 App-v Office 共存案例的常見限制

當您在同一部電腦上安裝下列版本的 Office 時，可能會發生下列限制：

-   使用 Windows 安裝程式的版本建立 Office 2010

-   使用 App-v 的 Office 2013

在您使用 App-v 與舊版 Windows 安裝程式的 Office 2010 發佈 Office 2013 之後，也可能會造成 Windows 安裝程式啟動。 這是因為 Windows 安裝程式或隨選即用版本的 Office 2010 嘗試自動將自己註冊到電腦。

若要略過原生 Word 2010 的自動註冊作業，請遵循下列步驟：

1.  退出 Word 2010。

2.  執行下列動作，啟動 [登錄編輯程式]：

    -   在 Windows 7 中：按一下 [**開始**]，在 [開始搜尋] 方塊中輸入**regedit** ，然後按 enter。

    -   在 Windows 8 中，輸入**regedit** ，在起始頁面上按 enter，然後按 enter。

    如果系統提示您輸入系統管理員密碼或進行確認，請輸入密碼，或按一下 [**繼續**]。

3.  找出下列登錄子機碼，然後選取該子項：

    ``` syntax
    HKEY_CURRENT_USER\Software\Microsoft\Office\14.0\Word\Options
    ```

4.  在 [**編輯**] 功能表上，按一下 [**新增**]，然後按一下 [ **DWORD 值**]。

5.  輸入**NoReReg**，然後按 enter。

6.  以滑鼠右鍵按一下 [ **NoReReg** ]，然後按一下 [**修改**]。

7.  在 [ **Valuedata** ] 方塊中，輸入**1**，然後按一下 **[確定]**。

8.  在 [檔案] 功能表上 **，按一下 [** 結束] 來關閉 [登錄編輯程式]。

## <a href="" id="bkmk-office-integration-win"></a>使用 App-v 部署 Office 時，Office 與 Windows 整合的方式


當您使用 App-v 部署 Office 2013 時，Office 會與作業系統完全整合，這可讓使用者擁有的功能和功能與 Office 在部署但不含 App-v 時一樣。

Office 2013 App-v 套件支援下列整合點與 Windows 作業系統：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">延伸點</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>適用于 Firefox 和 Chrome 的 Lync 會議加入外掛程式</p></td>
<td align="left"><p>使用者可以從 Firefox 和 Chrome 加入 Lync 會議</p></td>
</tr>
<tr class="even">
<td align="left"><p>已傳送至 OneNote 列印驅動程式</p></td>
<td align="left"><p>使用者可以列印至 OneNote</p></td>
</tr>
<tr class="odd">
<td align="left"><p>OneNote 連結筆記</p></td>
<td align="left"><p>OneNote 連結筆記</p></td>
</tr>
<tr class="even">
<td align="left"><p>傳送至 OneNote Internet Explorer 增益集</p></td>
<td align="left"><p>使用者可以從 IE 傳送至 OneNote</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Lync 和 Outlook 的防火牆例外狀況</p></td>
<td align="left"><p>Lync 和 Outlook 的防火牆例外狀況</p></td>
</tr>
<tr class="even">
<td align="left"><p>MAPI 用戶端</p></td>
<td align="left"><p>原生應用程式和增益集可透過 MAPI 與虛擬 Outlook 互動</p></td>
</tr>
<tr class="odd">
<td align="left"><p>適用于 Firefox 的 SharePoint 外掛程式</p></td>
<td align="left"><p>使用者可以在 Firefox 中使用 SharePoint 功能</p></td>
</tr>
<tr class="even">
<td align="left"><p>[郵件] 控制台小程式</p></td>
<td align="left"><p>使用者在 Outlook 中取得 [郵件] 控制台小程式</p></td>
</tr>
<tr class="odd">
<td align="left"><p>主要 Interop 元件</p></td>
<td align="left"><p>支援受管理的增益集</p></td>
</tr>
<tr class="even">
<td align="left"><p>Office 檔快取處理常式</p></td>
<td align="left"><p>允許 Office 應用程式的檔快取</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Outlook 通訊協定搜尋處理常式</p></td>
<td align="left"><p>使用者可以在 outlook 中搜尋</p></td>
</tr>
<tr class="even">
<td align="left"><p>Active X 控制項：</p></td>
<td align="left"><p>如需有關 ActiveX 控制項的詳細資訊，請參閱 <a href="https://go.microsoft.com/fwlink/p/?LinkId=331361" data-raw-source="[ActiveX Control API Reference](https://go.microsoft.com/fwlink/p/?LinkId=331361)"> Activex 控制項 API 參考 </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>   Groove. SiteClient</p></td>
<td align="left"><p>Active X 控制項</p></td>
</tr>
<tr class="even">
<td align="left"><p>   PortalConnect.PersonalSite</p></td>
<td align="left"><p>Active X 控制項</p></td>
</tr>
<tr class="odd">
<td align="left"><p>   OpenDocuments</p></td>
<td align="left"><p>Active X 控制項</p></td>
</tr>
<tr class="even">
<td align="left"><p>   ExportDatabase</p></td>
<td align="left"><p>Active X 控制項</p></td>
</tr>
<tr class="odd">
<td align="left"><p>   SpreadSheetLauncher</p></td>
<td align="left"><p>Active X 控制項</p></td>
</tr>
<tr class="even">
<td align="left"><p>   StssyncHander</p></td>
<td align="left"><p>Active X 控制項</p></td>
</tr>
<tr class="odd">
<td align="left"><p>   DragUploadCtl</p></td>
<td align="left"><p>Active X 控制項</p></td>
</tr>
<tr class="even">
<td align="left"><p>   DragDownloadCtl</p></td>
<td align="left"><p>Active X 控制項</p></td>
</tr>
<tr class="odd">
<td align="left"><p>   OpenXMLDocuments</p></td>
<td align="left"><p>Active X 控制項</p></td>
</tr>
<tr class="even">
<td align="left"><p>   ClipboardCtl</p></td>
<td align="left"><p>Active X 控制項</p></td>
</tr>
<tr class="odd">
<td align="left"><p>   WinProj Activator</p></td>
<td align="left"><p>Active X 控制項</p></td>
</tr>
<tr class="even">
<td align="left"><p>   NameCtrl</p></td>
<td align="left"><p>Active X 控制項</p></td>
</tr>
<tr class="odd">
<td align="left"><p>   STSUPld.CopyCtl</p></td>
<td align="left"><p>Active X 控制項</p></td>
</tr>
<tr class="even">
<td align="left"><p>   CommunicatorMeetingJoinAx.JoinManager</p></td>
<td align="left"><p>Active X 控制項</p></td>
</tr>
<tr class="odd">
<td align="left"><p>   LISTNET.Listnet</p></td>
<td align="left"><p>Active X 控制項</p></td>
</tr>
<tr class="even">
<td align="left"><p>   OneDrive 專業版瀏覽器協助程式</p></td>
<td align="left"><p>Active X 控制項]</p></td>
</tr>
<tr class="odd">
<td align="left"><p>OneDrive Pro 圖示重迭</p></td>
<td align="left"><p>當使用者查看資料夾 OneDrive Pro 資料夾時，Windows Explorer shell 圖示會重迭</p></td>
</tr>
<tr class="even">
<td align="left"><p>殼層延伸</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>方式</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Search</p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 






 

 





