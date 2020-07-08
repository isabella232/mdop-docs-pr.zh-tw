---
title: 規劃搭配 App-V 使用資料夾重新導向
description: 規劃搭配 App-V 使用資料夾重新導向
author: dansimp
ms.assetid: 6bea9a8f-a915-4d7d-be67-ef1cca1398ed
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 507aef186579da0efdb3af7b6e1088a5e725ad70
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800330"
---
# 規劃搭配 App-V 使用資料夾重新導向


Microsoft Application Virtualization （App-v）5.1 支援使用 [資料夾重新導向]，這項功能可讓使用者和系統管理員將資料夾路徑重新導向至新的位置。

本主題包含下列各節：

-   [使用資料夾重新導向的需求](#bkmk-folder-redir-reqs)

-   [如何設定要與 App-v 搭配使用的資料夾重新導向](#bkmk-folder-redir-cfg)

-   [資料夾重新導向如何與 App-v 搭配使用](#bkmk-folder-redir-works)

-   [資料夾重新導向概述](#bkmk-folder-redir-overview)

## <a href="" id="bkmk-folder-redir-reqs"></a>使用資料夾重新導向的需求與不受支援的案例


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>需求</p></td>
<td align="left"><p>若要使用% AppData% 資料夾重新導向，您必須：</p>
<ul>
<li><p>擁有 AppData 虛擬檔案系統（VFS）資料夾的 App-v 套件。</p></li>
<li><p>[啟用資料夾重新導向]，並將使用者的資料夾重新導向至共用資料夾（通常是網路資料夾）。</p></li>
<li><p>在下列兩種情況下或兩者皆能漫遊：</p>
<ul>
<li><p>[%Appdata%\Microsoft\AppV\Client\Catalog] 下的檔案</p></li>
<li><p>[HKEY_CURRENT_USER \Software\Microsoft\AppV\Client\Packages] 下的 [登錄] 設定</p>
<p>如需詳細資訊，請參閱 <a href="application-publishing-and-client-interaction.md#bkmk-clt-inter-roam-reqs" data-raw-source="[Application Publishing and Client Interaction](application-publishing-and-client-interaction.md#bkmk-clt-inter-roam-reqs)"> 應用程式發佈與用戶端互動 </a> 。</p></li>
</ul></li>
<li><p>確保登入執行 App-v 5.0 SP2 或更新版本用戶端之電腦的每位使用者都可以使用下列資料夾：</p>
<ul>
<li><p>% AppData% 已設定為想要的網路位置（有或不 <a href="https://technet.microsoft.com/library/cc780552.aspx" data-raw-source="[Offline Files](https://technet.microsoft.com/library/cc780552.aspx)"> 支援離線檔案 </a> ）。</p></li>
<li><p>% LocalAppData% 已設定為想要的本機資料夾。</p></li>
</ul></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>不支援的案例</p></td>
<td align="left"><ul>
<li><p>將% LocalAppData% 設定為網路磁碟機。</p></li>
<li><p>針對多位使用者將 [開始] 功能表重新導向到單一資料夾。</p></li>
<li><p>如果是漫遊 AppData （% AppData%）已重新導向至無法使用的網路共用，App-v 應用程式將無法啟動，如下所示：</p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">App-V 版本</th>
<th align="left">案例描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>在 app-v 5.0 的 app-V 5.0 SP2 加上修復程式</p></td>
<td align="left"><p>無論是否已啟用 [離線檔案]，都不會發生此錯誤。</p></td>
</tr>
<tr class="even">
<td align="left"><p>在 App-V 5.0 SP3 及更新版本中</p></td>
<td align="left"><p>如果已為離線檔案啟用無法使用的網路共用，App-v 應用程式將會順利啟動。</p></td>
</tr>
</tbody>
</table>
<p> </p></li>
</ul></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-folder-redir-cfg"></a>如何設定要與 App-v 搭配使用的資料夾重新導向


[資料夾重新導向] 可套用至不同的資料夾，例如 [桌面]、[我的檔]、[我的圖片] 等等。不過，影響 App-v 應用程式使用的唯一資料夾是使用者的 [漫遊 AppData] 資料夾（% AppData%）。 您可以將資料夾重新導向套用到任何其他支援的資料夾，而不會影響 App-v。

## <a href="" id="bkmk-folder-redir-works"></a>資料夾重新導向如何與 App-v 搭配使用


下表說明當% AppData% 重新導向至網路時，資料夾重新導向的運作方式，以及您符合本文前面所列的需求。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">虛擬環境狀態</th>
<th align="left">發生的動作</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>虛擬環境啟動時</p></td>
<td align="left"><p>虛擬檔案系統（VFS） AppData 資料夾會對應到本機 AppData 資料夾（% LocalAppData%）而不是使用者的漫遊 AppData 資料夾（% AppData%）。</p>
<ul>
<li><p>LocalAppData 包含使用者的 [漫遊 AppData] 資料夾的本機快取，以供使用中的套件。 本機快取位於：</p>
<p><code>%LocalAppData%\Microsoft\AppV\Client\VFS\PackageGUID\AppData</code></p></li>
<li><p>使用者的 [漫遊 AppData] 資料夾中的最新資料會複製到並取代本機快取中目前的資料。</p></li>
<li><p>虛擬環境執行時，資料會繼續儲存到本機快取。 資料只會在% LocalAppData% 中提供，而且不會移動或與% AppData% 進行同步處理，直到最終使用者關閉電腦為止。</p></li>
<li><p>使用使用者內容（而非系統內容）來建立 AppData 資料夾的專案。</p></li>
</ul>
<div class="alert">
<strong>注意</strong><br/><p>App-V 用戶端的資料夾重新導向有時無法將檔案從% AppData% 移到% LocalAppData%。 請參閱 <a href="release-notes-for-app-v-50-sp2.md#bkmk-folderredirection" data-raw-source="[Release Notes for App-V 5.0 SP2](release-notes-for-app-v-50-sp2.md#bkmk-folderredirection)"> app-v 5.0 SP2 的版本資訊 </a> 。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>當虛擬環境關閉時</p></td>
<td align="left"><p>AppData （漫遊）中的本機快取資料會壓縮並複製到% AppData% 中的「實際」漫遊 AppData 資料夾中。 時間戳記（表示最近已知上傳）在下列情況下會同時儲存為登錄機碼：</p>
<p><code>HKCU\Software\Microsoft\AppV\Client\Packages&amp;lt;PACKAGE_GUID&gt;\AppDataTime</code></p>
<p>為了提供冗余，App-v 會將壓縮資料的三個最新複本保留在% AppData% 下。</p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-folder-redir-overview"></a>資料夾重新導向概述


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>用途</p></td>
<td align="left"><p>讓使用者能夠使用已重新導向至另一個資料夾的檔案，就像檔案仍在本機磁片磁碟機上。</p></td>
</tr>
<tr class="even">
<td align="left"><p>描述</p></td>
<td align="left"><p>[資料夾重新導向] 可讓使用者和系統管理員將資料夾的路徑重新導向至網路位置。 該資料夾中的檔可供來自網路上任何電腦的使用者使用。</p>
<ul>
<li><p>[資料夾重新導向] 可讓使用者和系統管理員將資料夾的路徑重新導向至網路位置。 該資料夾中的檔可供來自網路上任何電腦的使用者使用。</p></li>
<li><p>新位置可以是本機電腦上的資料夾，或是共用網路上的資料夾。</p></li>
<li><p>[資料夾重新導向] 會立即更新檔案，而漫遊資料通常是在使用者登入或登出時進行同步處理。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>用法範例</p></td>
<td align="left"><p>您可以將 [檔] 資料夾重新導向至網路位置，這通常會儲存在電腦&#39;s 本機硬碟上。 使用者可以從網路上的任何電腦存取資料夾中的檔。</p></td>
</tr>
<tr class="even">
<td align="left"><p>更多資源</p></td>
<td align="left"><p><a href="https://technet.microsoft.com/library/cc778976.aspx" data-raw-source="[Folder redirection overview](https://technet.microsoft.com/library/cc778976.aspx)">資料夾重新導向概述</a></p></td>
</tr>
</tbody>
</table>
















