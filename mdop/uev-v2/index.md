---
title: Microsoft 消費者體驗虛擬化 (UE-V) 2.x
description: Microsoft 消費者體驗虛擬化 (UE-V) 2.x
author: dansimp
ms.assetid: b860fed0-b846-415d-bdd6-ba60231a64be
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 04/19/2017
ms.openlocfilehash: 79748e04ae1a59afdc8f9dae3c5dc77c50e3c253
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910538"
---
# <a name="microsoft-user-experience-virtualization-ue-v-2x"></a>Microsoft 消費者體驗虛擬化 (UE-V) 2.x

>[!NOTE]
>本檔適用于 MICROSOFT 桌面優化套件 UE-V MDOP (中) 。 有關最新版 UE-V包含在 Windows 10 企業版 中的資訊，請參閱入門[的UE-V。](https://docs.microsoft.com/windows/configuration/ue-v/uev-getting-started)


使用 2.0 或 2.1 來Windows並集中化使用者的應用程式設定，Microsoft 消費者體驗虛擬化 (UE-V) OS 設定。 然後，將這些設定適用于企業使用者存取的裝置，例如桌上型電腦、膝上型電腦或虛擬桌面基礎結構 (VDI) 會話。

**您可以UE-V...**

-   指定同步處理哪些應用程式和桌面設定

-   為整個企業的使用者隨時隨地提供設定

-   為協力廠商或企業營運應用程式建立自訂範本

-   在硬體更換或升級之後，或將虛擬機器重新映射至初始狀態後復原設定

## <a name="components-of-ue-v-2x"></a>2.x UE-V的元件


此圖表顯示部署UE-V元件如何共同作業以同步處理設定。

![uev2 架構圖表。](images/uev2archdiagram.gif)

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
<td align="left"><p><strong>UE-V代理</strong></p></td>
<td align="left"><p>安裝于需要同步處理設定的每一部電腦上，UE-V代理程式會監控已註冊的應用程式，而作業系統會針對任何設定變更，然後在電腦之間同步 <strong> </strong> 處理這些設定。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>設定套件</strong></p></td>
<td align="left"><p>應用程式設定和Windows設定會儲存在由代理程式所建立UE-V <strong> </strong> 套件中。 設定套件建置後會儲存到本機，然後複製到設定儲存位置。</p>
<ul>
<li><p>桌面應用程式的 <strong> 設定 </strong> 值會于使用者關閉應用程式時儲存。</p></li>
<li><p>使用者Windows、電腦鎖定時，或使用者從電腦遠端中斷連接時，系統會儲存這些設定 <strong> </strong> 的值。</p></li>
</ul>
<p>同步處理提供者會決定應用程式或作業系統設定何時從應用程式套件設定 <strong> 同步 </strong> 處理。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>設定儲存位置</strong></p></td>
<td align="left"><p>這是使用者可以存取的標準網路共用。 代理UE-V驗證位置，並建立隱藏的系統資料夾，以儲存及取回使用者設定。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>設定位置範本</strong></p></td>
<td align="left"><p>UE-V XML 檔案做為設定位置範本，以監控及同步處理桌面應用程式設定，Windows電腦之間的桌面設定。 根據預設，某些設定位置範本會包含在 UE-V。 您也可以管理自訂應用程式的設定同步處理，以建立、編輯或驗證自訂設定 <a href="#customapps" data-raw-source="[managing settings synchronization for custom applications](#customapps)"> 位置範本 </a> 。</p>
<div class="alert">
<strong>注意</strong><br/><p>設定應用程式不需要任何位置Windows範本。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Windows應用程式清單</strong></p></td>
<td align="left"><p>設定應用程式Windows應用程式會動態捕獲並應用。 應用程式開發人員會指定每個 App 同步的設定。 UE-V使用Windows應用程式清單，決定哪些應用程式已啟用設定同步處理。 根據預設，此清單包含大部分Windows應用程式。</p>
<p>您可以遵循此處顯示的程式，Windows應用程式清單中新增或移除 <a href="https://technet.microsoft.com/library/dn458925.aspx" data-raw-source="[here](https://technet.microsoft.com/library/dn458925.aspx)"> 應用程式 </a> 。</p></td>
</tr>
</tbody>
</table>



### <a name="managing-settings-synchronization-for-custom-applications"></a><a href="" id="customapps"></a>管理設定應用程式的同步處理

使用這些UE-V元件，為協力廠商或企業經營應用程式建立及管理自訂範本。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>UE-V發電機</strong></p></td>
<td align="left"><p>使用 <strong> UE-V建立 </strong> 自訂設定位置範本，然後發佈給使用者電腦。 UE-V產生器也可讓您編輯現有的範本，或驗證使用另一個 XML 編輯器所建立範本。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>設定範本目錄</strong></p></td>
<td align="left"><p>設定範本目錄是電腦上的資料夾路徑UE-V或儲存自訂設定位置範本之 SMB (SMB) 伺服器訊息封鎖 <strong> </strong> 。 代理UE-V每天檢查此位置一次、取回新的或更新的範本，並更新其同步處理行為。</p>
<p>如果您只使用預設UE-V設定位置範本，則不需要設定範本目錄。 有關設定部署目錄詳細資訊，請參閱設定 <a href="https://technet.microsoft.com/library/dn458942.aspx#deploycatalogue" data-raw-source="[Configure a UE-V settings template catalog](https://technet.microsoft.com/library/dn458942.aspx#deploycatalogue)"> UE-V範本目錄 </a> 。</p></td>
</tr>
</tbody>
</table>



![ue-v 產生程式。](images/ue-vgeneratorprocess.gif)

## <a name="settings-synchronized-by-default"></a>設定預設同步


UE-V同步處理這些應用程式的設定。 有關完整清單和詳細資訊，請參閱設定部署中自動同步處理UE-V[清單](https://technet.microsoft.com/library/dn458932.aspx#autosyncsettings)。

Microsoft Office 2013 應用程式 (UE-V 2.1 SP1 和 2.1) 

Microsoft Office 2010 (UE-V SP1、2.1 和 2.0) 

Microsoft Office 2007 應用程式 (UE-V 2.0) 

Internet Explorer 8、9 和 10

Internet Explorer 11 UE-V 2.1 SP1 和 2.1

許多Windows應用程式，例如 Xbox

許多Windows桌面應用程式，例如記事本

許多Windows設定，例如桌面背景或牆紙

**注意**  
您也可以自訂[應用程式UE-V同步](https://technet.microsoft.com/library/dn458942.aspx)處理預設同步處理的應用程式設定。



## <a name="compare-ue-v-to-other-microsoft-products"></a>比較UE-V與其他 Microsoft 產品


使用此表格可比較 UE-V 7 中的同步Windows設定檔、Windows 8 中的同步設定檔，以及 Microsoft 帳戶的同步設定同步電腦功能。

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
<th align="left">使用 7 同步Windows設定檔</th>
<th align="left">使用檔案同步Windows 8</th>
<th align="left">使用檔案同步Windows 10</th>
<th align="left">Microsoft 帳戶</th>
<th align="left">UE-V 2.0</th>
<th align="left">UE-V 2.1 和 2.1 SP1</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>同步處理多部電腦之間的設定</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
</tr>
<tr class="even">
<td align="left"><p>在實體和虛擬應用程式之間同步設定</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
</tr>
<tr class="odd">
<td align="left"><p>同步Windows應用程式設定</p></td>
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
<td align="left"><p>安裝程式的最小化設定</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
</tr>
<tr class="odd">
<td align="left"><p>支援非網域加入的電腦</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>支援主機電腦 Active Directory 屬性</p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>在虛擬桌面基礎結構與 VDI (/Remote Desktop Services) RDS (和豐富桌面) 同步設定</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
</tr>
<tr class="even">
<td align="left"><p>無限設定儲存空間</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
</tr>
<tr class="odd">
<td align="left"><p>選擇要同步的 App 設定</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>●</p></td>
</tr>
<tr class="even">
<td align="left"><p>IT 備份/還原Pro</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>●</p></td>
<td align="left"><p>部分</p></td>
<td align="left"><p>●</p></td>
</tr>
</tbody>
</table>



## <a name="ue-v-2x-release-notes"></a>UE-V2.x 版本資訊


有關詳細資訊，以及未納入檔的最新消息，請參閱

-   [Microsoft User Experience Virtualization (UE-V) 2.1 SP1 版本資訊](microsoft-user-experience-virtualization--ue-v--21-sp1-release-notes.md)

-   [Microsoft User Experience Virtualization (UE-V) 2.1 版本資訊](microsoft-user-experience-virtualization--ue-v--21-release-notesuevv21.md)

-   [Microsoft User Experience Virtualization (UE-V) 2.0 版本資訊](microsoft-user-experience-virtualization--ue-v--20-release-notesuevv2.md)

## <a name="other-resources-for-this-product"></a>此產品的其他資源


-   [UE-V 2.x 入門](get-started-with-ue-v-2x-new-uevv2.md)

-   [準備 2.x UE-V部署](prepare-a-ue-v-2x-deployment-new-uevv2.md)

-   [管理 UE-V 2.x](administering-ue-v-2x-new-uevv2.md)

-   [2.x UE-V疑難排解](troubleshooting-ue-v-2x-both-uevv2.md)

-   [UE-V 2.x 技術參考](technical-reference-for-ue-v-2x-both-uevv2.md)

### <a name="more-information"></a>其他資訊

<a href="" id="mdop-techcenter-page"></a>[MDOP TechCenter 頁面](https://go.microsoft.com/fwlink/p/?LinkId=225286) 瞭解最新的 MDOP 資訊和資源。

<a href="" id="mdop-information-experience"></a>[MDOP 資訊體驗](https://go.microsoft.com/fwlink/p/?LinkId=236032) 尋找 MDOP 技術的檔、影片和其他資源。 您也可以在 [Facebook](mailto:MDOPDocs@microsoft.com) 或 [Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242445) 上關注我們，傳送意見或瞭解 [更新](https://go.microsoft.com/fwlink/p/?LinkId=242447)。














