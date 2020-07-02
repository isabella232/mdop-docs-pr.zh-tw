---
title: Microsoft 使用者體驗虛擬化（UE-V） 2. x
description: Microsoft 使用者體驗虛擬化（UE-V） 2. x
author: dansimp
ms.assetid: b860fed0-b846-415d-bdd6-ba60231a64be
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 04/19/2017
ms.openlocfilehash: 573b8bb2027e5c7f117a8254005a43c656f047a9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10795566"
---
# Microsoft 使用者體驗虛擬化（UE-V） 2. x

>[!NOTE]
>本檔是 Microsoft 桌面優化套件（MDOP）中包含的 UE-V 版本。 如需 Windows 10 企業版中包含的最新版本 UE-V 的相關資訊，請參閱[從 Ue-v 開始使用](https://docs.microsoft.com/windows/configuration/ue-v/uev-getting-started)。


透過執行 Microsoft 使用者體驗虛擬化（UE-V）2.0 或2.1，來捕獲並集中使用者的應用程式設定和 Windows 作業系統設定。 然後，將這些設定套用到企業中的使用者存取的裝置，例如桌上型電腦、膝上型電腦或虛擬桌面基礎結構（VDI）會話。

**使用 UE-V，您可以 .。。**

-   指定要同步處理哪些應用程式和桌面設定

-   為整個企業的使用者隨時隨地提供設定

-   為協力廠商或企業營運應用程式建立自訂範本

-   在硬體更換或升級之後或將虛擬機器重設為初始狀態之後復原設定

## UE-V 2. x 的元件


此圖表顯示部署的 UE-V 元件如何共同運作，以同步處理設定。

![uev2 結構圖表](images/uev2archdiagram.gif)

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">元件</th>
<th align="left">函式</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>UE-V Agent</strong></p></td>
<td align="left"><p>在需要同步處理設定的每台電腦上安裝， <strong> Ue-v agent 會 </strong> 監視已註冊的應用程式與作業系統的任何設定變更，然後在電腦之間同步處理這些設定。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>設定套件</strong></p></td>
<td align="left"><p>[應用程式設定] 和 [Windows 設定] 儲存在 <strong> </strong> 由 ue-v agent 建立的設定套件中。 設定套件建置後會儲存到本機，然後複製到設定儲存位置。</p>
<ul>
<li><p><strong> </strong> 當使用者關閉應用程式時，會儲存桌面應用程式的設定值。</p></li>
<li><p><strong>Windows 設定的值 </strong> 會在使用者登出、電腦被鎖定時，或當使用者從電腦上遠端斷開時儲存。</p></li>
</ul>
<p>同步處理提供者會判斷何時從設定套件中讀取應用程式或作業系統的設定 <strong> </strong> ，並進行同步處理。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>設定儲存位置</strong></p></td>
<td align="left"><p>這是您的使用者可以存取的標準網路共用。 UE-V Agent 會驗證位置，並建立隱藏的系統資料夾，以儲存及檢索使用者設定。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>設定位置範本</strong></p></td>
<td align="left"><p>UE-V 使用 XML 檔案做為設定位置範本，在使用者電腦之間監視及同步處理桌面應用程式設定與 Windows 桌面設定。 根據預設，在 UE-V 中包含一些設定位置範本。 您也可以透過 <a href="#customapps" data-raw-source="[managing settings synchronization for custom applications](#customapps)"> 管理自訂應用程式的設定同步處理，來建立、編輯或驗證自訂設定位置範本 </a> 。</p>
<div class="alert">
<strong>注意</strong><br/><p>Windows 應用程式不需要設定位置範本。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Windows 應用程式清單</strong></p></td>
<td align="left"><p>Windows 應用程式的設定會被動態捕獲並套用。 App 開發人員會為每個 app 指定同步處理的設定。 UE-V 會判斷使用受管理的應用程式清單來啟用設定同步處理的 Windows 應用程式。 根據預設，此清單包含大部分的 Windows 應用程式。</p>
<p>您可以按照此處所示的程式，在 Windows 應用程式清單中新增或移除應用程式 <a href="https://technet.microsoft.com/library/dn458925.aspx" data-raw-source="[here](https://technet.microsoft.com/library/dn458925.aspx)"> </a> 。</p></td>
</tr>
</tbody>
</table>



### <a href="" id="customapps"></a>管理自訂應用程式的設定同步處理

使用這些 UE-V 元件來建立及管理協力廠商或商務用端應用程式的自訂範本。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>UE-V 發生器</strong></p></td>
<td align="left"><p>使用 <strong> Ue-v 發生器 </strong> 來建立自訂設定位置範本，您可以將它發佈到使用者電腦。 UE-V 發生器也可讓您編輯現有的範本，或驗證使用其他 XML 編輯器所建立的範本。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>設定範本目錄</strong></p></td>
<td align="left"><p>[ <strong> 設定範本目錄] </strong> 是 ue-v 電腦或伺服器郵件區塊（SMB）網路共用上的資料夾路徑，可儲存自訂設定位置範本。 UE-V Agent 會一天檢查這個位置，檢索新的或更新的範本，並更新其同步處理行為。</p>
<p>如果您只使用 UE-V 預設設定位置範本，則不需要設定範本目錄。 如需設定部署目錄的詳細資訊，請參閱 <a href="https://technet.microsoft.com/library/dn458942.aspx#deploycatalogue" data-raw-source="[Configure a UE-V settings template catalog](https://technet.microsoft.com/library/dn458942.aspx#deploycatalogue)"> 設定 ue-v 設定範本目錄 </a> 。</p></td>
</tr>
</tbody>
</table>



![ue-v 發生器程式](images/ue-vgeneratorprocess.gif)

## 預設同步處理的設定


UE-V 預設會同步處理這些應用程式的設定。 如需完整清單及更詳細的資訊，請參閱[在 ue-v 部署中自動同步](https://technet.microsoft.com/library/dn458932.aspx#autosyncsettings)處理的設定。

Microsoft Office 2013 應用程式（UE-V 2.1 SP1 及2.1）

Microsoft Office 2010 應用程式（UE-V 2.1 SP1、2.1 和2.0）

Microsoft Office 2007 應用程式（僅限 UE-V 2.0）

Internet Explorer 8、9和10

UE-V 2.1 SP1 和2.1 中的 Internet Explorer 11

許多 Windows 應用程式，例如 Xbox

許多 Windows 桌面應用程式，例如記事本

許多 Windows 設定（例如桌面背景或牆紙）

**注意**  
您也可以[自訂 ue-v，以同步處理](https://technet.microsoft.com/library/dn458942.aspx)除預設值以外的應用程式的設定。



## 比較 UE-V 與其他 Microsoft 產品


使用此表格比較 UE-V 以在 Windows 7 中同步處理設定檔、在 Windows 8 中同步處理設定檔，以及 Microsoft 帳戶的 [同步電腦設定] 功能。

<table style="width:100%;">
<colgroup>
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">功能</th>
<th align="left">使用 Windows 7 同步處理設定檔</th>
<th align="left">使用 Windows 8 同步處理設定檔</th>
<th align="left">使用 Windows 10 同步處理設定檔</th>
<th align="left">Microsoft 帳戶</th>
<th align="left">UE-V 2。0</th>
<th align="left">UE-V 2.1 和 2.1 SP1</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>同步處理多個電腦之間的設定</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
</tr>
<tr class="even">
<td align="left"><p>在物理與虛擬 app 之間同步處理設定</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
</tr>
<tr class="odd">
<td align="left"><p>同步處理 Windows 應用程式設定</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
</tr>
<tr class="even">
<td align="left"><p>透過 WMI 管理</p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
</tr>
<tr class="odd">
<td align="left"><p>定期同步處理設定變更</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
</tr>
<tr class="even">
<td align="left"><p>設定的最低配置</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
</tr>
<tr class="odd">
<td align="left"><p>在未加入網域的電腦上支援</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>支援主要電腦 Active Directory 屬性</p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>在虛擬桌面基礎結構（VDI）/Remote 桌面服務（RDS）與胖桌面之間同步處理設定</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
</tr>
<tr class="even">
<td align="left"><p>設定儲存空間無限制</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
</tr>
<tr class="odd">
<td align="left"><p>您可以選擇要同步處理之應用程式設定的選項</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
</tr>
<tr class="even">
<td align="left"><p>IT 專業人員的備份/還原</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>部分</p></td>
<td align="left"><p>●</p></td>
</tr>
</tbody>
</table>



## UE-V 2. x 版本資訊


如需詳細資訊，以及未在檔中顯示的最新消息，請參閱

-   [Microsoft User Experience Virtualization (UE-V) 2.1 SP1 版本資訊](microsoft-user-experience-virtualization--ue-v--21-sp1-release-notes.md)

-   [Microsoft User Experience Virtualization (UE-V) 2.1 版本資訊](microsoft-user-experience-virtualization--ue-v--21-release-notesuevv21.md)

-   [Microsoft User Experience Virtualization (UE-V) 2.0 版本資訊](microsoft-user-experience-virtualization--ue-v--20-release-notesuevv2.md)

## 此產品的其他資源


-   [UE-V 2.x 入門](get-started-with-ue-v-2x-new-uevv2.md)

-   [準備 UE-V a.x 部署](prepare-a-ue-v-2x-deployment-new-uevv2.md)

-   [管理 UE-V 2。](administering-ue-v-2x-new-uevv2.md)

-   [疑難排解 UE-V 2. x](troubleshooting-ue-v-2x-both-uevv2.md)

-   [UE-V 2.x 技術參考](technical-reference-for-ue-v-2x-both-uevv2.md)

### 詳細資訊

<a href="" id="mdop-techcenter-page"></a>[MDOP 技術中心頁面](https://go.microsoft.com/fwlink/p/?LinkId=225286)瞭解最新的 MDOP 資訊和資源。

<a href="" id="mdop-information-experience"></a>[MDOP 資訊體驗](https://go.microsoft.com/fwlink/p/?LinkId=236032)尋找您的 MDOP 技術的檔、影片及其他資源。 您也可以在[Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445)或[Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447)上關注我們，以[傳送意見](mailto:MDOPDocs@microsoft.com)反應或瞭解更新。














