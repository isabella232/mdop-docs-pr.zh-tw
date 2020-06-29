---
title: Application Virtualization Client 安裝程式命令列參數
description: Application Virtualization Client 安裝程式命令列參數
author: dansimp
ms.assetid: 508fa404-52a5-4919-8788-2a3dfb00639b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 911d333c80060c1881c96430c1d2d0516b6a4855
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802329"
---
# Application Virtualization Client 安裝程式命令列參數


下表列出所有可用的 Microsoft Application Virtualization 用戶端安裝程式命令列參數、其值，以及每個參數的簡短描述。 參數區分大小寫，且必須以全大寫字母輸入。 所有參數值都必須以雙引號括住。

**注意**  
-   在 App-v 4.6 版中，在用戶端升級期間無法使用命令列參數。

-   在命令列上不能結合*SWICACHESIZE*和*MINFREESPACEMB*參數。 如果同時使用兩者，則會忽略*SWICACHESIZE*參數。



<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">參數</th>
<th align="left">相對值</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><em>ALLOWINDEPENDENTFILESTREAMING</em></p></td>
<td align="left"><p>TRUE</p>
<p>FALSE</p></td>
<td align="left"><p>指示是否要啟用來自檔案的資料流程，不論用戶端是否已使用 <em> APPLICATIONSOURCEROOT 參數進行設定 </em> 。 如果設定為 FALSE，即使 OSD HREF 或 <em> APPLICATIONSOURCEROOT 參數包含檔案路徑，傳輸也不會啟用檔案的資料流程 </em> 。</p>
<p>可能的值：</p>
<ul>
<li><p>TRUE-可能會從磁片載入手動部署的應用程式。</p></li>
<li><p>FALSE-所有應用程式都必須來自來來源資料流伺服器。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><em>APPLICATIONSOURCEROOT</em></p></td>
<td align="left"><p>RTSP:// <em> URL </em> （適用于動態套件傳遞）</p>
<p>File:// <em> URL </em> 或 <em> UNC </em> （從檔案套件傳送中載入）</p></td>
<td align="left"><p>若要啟用系統管理員或電子軟體發佈系統，以確保應用程式載入與拓撲管理配置相容，可以覆寫應用程式 HREF 元素的 OSD 基本代碼（來源位置）。 如果值是 ""，這是預設值，則會使用現有的 OSD 檔案設定。</p>
<p>URL 有數個部分：</p>
<p>&lt;通訊協定/ &gt; / &lt; 伺服器 &gt; ： &lt; 埠 &gt; / &lt; 路徑 &gt; / &lt; ？ query &gt; &lt; #fragment&gt;</p>
<p>UNC 路徑有三個部分：</p>
<p>&amp;lt; computername &gt; &amp; lt; 共用資料夾 &gt; &amp; lt; 資源&gt;</p>
<p>如果 <em> APPLICATIONSOURCEROOT </em> 參數是在用戶端上指定，用戶端會將來自 OSD 檔案的 URL 或 UNC 路徑中斷到其構成元件，並將 osd 區段取代為對應的 <em> APPLICATIONSOURCEROOT </em> 區段。</p>
<div class="alert">
<strong>重要</strong><br/><p>在搭配 UNC 路徑使用 file://時，請務必使用正確的格式。 正確的格式是 file://[lt]; [ &amp; 伺服器 &gt; &amp; lt; share] &gt; 。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><em>ICONSOURCEROOT</em></p></td>
<td align="left"><p><em>UNC</em></p>
<p>HTTP:// <em> url </em> 或 HTTPS:// <em> url</em></p></td>
<td align="left"><p>可讓系統管理員在發佈期間指定已排序之應用程式套件的圖示檢索來源位置。 圖示來源根支援 UNC 路徑和 Url （HTTP 或 HTTPS）。 如果值是 ""，這是預設值，則會使用現有的 OSD 檔案設定。</p>
<p>URL 有數個部分：</p>
<p>&lt;通訊協定/ &gt; / &lt; 伺服器 &gt; ： &lt; 埠 &gt; / &lt; 路徑 &gt; / &lt; ？ query &gt; &lt; #fragment&gt;</p>
<p>UNC 路徑有三個部分：</p>
<p>&amp;lt; computername &gt; &amp; lt; 共用資料夾 &gt; &amp; lt; 資源&gt;</p>
<div class="alert">
<strong>重要</strong><br/><p>使用 UNC 路徑時，請務必使用正確的格式。 可接受的格式為 &amp; lt; server &gt; &amp; lt; share &gt; 或 &lt; drive 字母 &gt; ： &amp; lt; 資料夾 &gt; 。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><em>OSDSOURCEROOT</em></p></td>
<td align="left"><p><em>UNC</em></p>
<p>HTTP:// <em> url </em> 或 HTTPS:// <em> url</em></p></td>
<td align="left"><p>讓系統管理員在發佈期間指定應用程式套件的 OSD 檔案檢索源位置。 OSD 來源根支援 UNC 路徑和 Url （HTTP 或 HTTPS）。 如果值是 ""，這是預設值，則會使用現有的 OSD 檔案設定。</p>
<p>URL 有數個部分：</p>
<p>&lt;通訊協定/ &gt; / &lt; 伺服器 &gt; ： &lt; 埠 &gt; / &lt; 路徑 &gt; / &lt; ？ query &gt; &lt; #fragment&gt;</p>
<p>UNC 路徑有三個部分：</p>
<p>&amp;lt; computername &gt; &amp; lt; 共用資料夾 &gt; &amp; lt; 資源&gt;</p>
<div class="alert">
<strong>重要</strong><br/><p>使用 UNC 路徑時，請務必使用正確的格式。 可接受的格式為 &amp; lt; server &gt; &amp; lt; share &gt; 或 &lt; drive 字母 &gt; ： &amp; lt; 資料夾 &gt; 。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><em>AUTOLOADONLOGIN</em></p>
<p><em>AUTOLOADONLAUNCH</em></p>
<p><em>AUTOLOADONREFRESH</em></p></td>
<td align="left"><p>[0 | 1]</p></td>
<td align="left"><p>AutoLoad 觸發程式，定義啟動自動載入應用程式的事件。 AutoLoad 會隱式使用背景資料流程，讓應用程式完全載入到快取中。</p>
<p>將會儘快載入主要功能區塊。 剩餘的功能區塊會在背景中載入，以啟用前景作業，例如使用者與應用程式互動、取得優先順序，以及提供最佳效能。</p>
<div class="alert">
<strong>注意</strong><br/><p><em>AUTOLOADTARGET </em> 參數會決定自動載入哪些應用程式。 根據預設，已使用的套件會自動載入（除非 <em> </em> 已設定 AUTOLOADTARGET）。</p>
</div>
<div>

</div>
<p>每個參數都會影響載入行為，如下所示：</p>
<ul>
<li><p><em>AUTOLOADONLOGIN </em> -在使用者登入時開始載入。</p></li>
<li><p><em>AUTOLOADONLAUNCH </em> -當使用者開始使用應用程式時，就會開始載入。</p></li>
<li><p><em>AUTOLOADONREFRESH </em> -在進行發佈更新時開始載入。</p></li>
</ul>
<p>這三個值可以結合。 在下列範例中，使用者登入和發佈重新整理時會啟用 AutoLoad 觸發程式：</p>
<p><em>AUTOLOADONLOGIN AUTOLOADONREFRESH</em></p>
<div class="alert">
<strong>注意</strong><br/><p>如果在第一次安裝時會將用戶端設定為使用這些值，則在使用者下次登入並重新登入時，就不會觸發 Autoload。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><em>AUTOLOADTARGET</em></p></td>
<td align="left"><p>所有</p>
<p>同時</p>
<p>PREVUSED</p></td>
<td align="left"><p>指示在任何指定的 AutoLoad 觸發程式發生時，將會自動載入哪些內容。</p>
<p>可能的值：</p>
<ul>
<li><p>無：不會自動載入，不論可能會設定哪些觸發程式。</p></li>
<li><p>[全部]-如果已啟用任何 AutoLoad 觸發程式，則會自動載入所有套件，不論它們是否曾啟動。</p>
<div class="alert">
<strong>注意</strong><br/><p>此設定是使用 SFTMIME [ <strong> 新增套件] </strong> 並 <strong> 設定套件命令來針對個別套件進行設定 </strong> 。 如需這些命令的詳細資訊，請參閱 <a href="sftmime--command-reference.md" data-raw-source="[SFTMIME Command Reference](sftmime--command-reference.md)"> SFTMIME 命令參考 </a> 。</p>
</div>
<div>

</div></li>
<li><p>PREVUSED-如果已啟用任何 AutoLoad 觸發程式，請只載入套件中以前使用過的套件（亦即啟動或 precached）。</p></li>
</ul>
<div class="alert">
<strong>注意</strong><br/><p>當您安裝 App-V 用戶端以使用唯讀快取（例如，作為 VDI 伺服器實現）時，您必須將 <em> AUTOLOADTARGET </em> 參數設定為 NONE，以免用戶端嘗試更新唯讀快取中的應用程式。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><em>DOTIMEOUTMINUTES</em></p></td>
<td align="left"><p>29600（預設值）</p>
<p>1–1439998560分鐘（範圍）</p></td>
<td align="left"><p>指出應用程式在中斷式作業中可使用的分鐘數。</p></td>
</tr>
<tr class="even">
<td align="left"><p><em>INSTALLDIR</em></p></td>
<td align="left"><p>&lt;pathname&gt;</p></td>
<td align="left"><p>指定 App-V 用戶端的安裝目錄。</p>
<p>範例： INSTALLDIR = &quot; C:\Program Files\Microsoft 應用程式虛擬化用戶端&quot;</p></td>
</tr>
<tr class="odd">
<td align="left"><p><em>OPTIN</em></p></td>
<td align="left"><p>滿足</p>
<p>“”</p></td>
<td align="left"><p>當您將更新提供給一般公用時，microsoft 應用程式虛擬化用戶端元件會透過 Microsoft Update 進行升級。 在 Windows 作業系統上安裝的 Microsoft Update 代理程式要求使用者明確選擇使用該服務。 針對裝置上的所有應用程式，此自願加入只需要一次。 如果您已加入宣告 Microsoft Update，裝置上的 Microsoft 應用程式虛擬化元件將會自動利用該服務。</p>
<p>針對命令列安裝，使用 Microsoft Update 是預設退出宣告（除非前一個應用程式已啟用裝置），因為您需要手動加入宣告 Microsoft Update。 因此，在命令列安裝中，選擇 [加入] 必須是明確的。 將命令列參數 OPTIN 設定 <em> </em> 為 TRUE，就會強制設定 Microsoft Update 自願加入。</p></td>
</tr>
<tr class="even">
<td align="left"><p><em>REQUIREAUTHORIZATIONIFCACHED</em></p></td>
<td align="left"><p>TRUE</p>
<p>FALSE</p></td>
<td align="left"><p>指出是否總是需要授權（無論是否已在快取中有應用程式）。</p>
<p>可能的值：</p>
<ul>
<li><p>TRUE-應用程式永遠必須在啟動時授權。 針對 RTSP 流程式應用程式，會將使用者授權權杖傳送到伺服器以進行授權。 對於以檔案為基礎的應用程式，檔案 Acl 會指示使用者是否可以存取應用程式。</p></li>
<li><p>FALSE —請務必連線到伺服器。 如果無法建立伺服器連線，用戶端仍可讓使用者啟動先前載入到快取中的應用程式。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><em>SWICACHESIZE</em></p></td>
<td align="left"><p>快取記憶體大小（MB）</p></td>
<td align="left"><p>指定用戶端快取的大小（以 mb 為單位）。 預設大小為 4096 MB，最大大小為 1048576 MB （1 TB）。 系統會在安裝時檢查可用的空間，但不保留空間。</p>
<p>範例： <strong> SWICACHESIZE = &quot; 1024&quot;</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><em>SWIPUBSVRDISPLAY</em></p></td>
<td align="left"><p>顯示名稱</p></td>
<td align="left"><p>指定發佈伺服器的顯示名稱;<em>使用 SWIPUBSVRHOST 時 </em> 是必要的。</p>
<p>範例： <strong> SWIPUBSVRDISPLAY = &quot; 生產環境&quot;</strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><em>SWIPUBSVRTYPE</em></p></td>
<td align="left"><p>[HTTP |RTSP</p></td>
<td align="left"><p>指定發佈伺服器類型。 預設伺服器類型是 Application Virtualization 伺服器。 <strong>/Secure </strong> 開關不區分大小寫。</p>
<ul>
<li><p>HTTP-標準 HTTP 伺服器</p></li>
<li><p>HTTP <strong> /secure </strong> -增強的安全性 HTTP 伺服器</p></li>
<li><p>RTSP-應用程式虛擬化伺服器</p></li>
<li><p>RTSP <strong> /secure </strong> -增強的安全性應用程式虛擬化伺服器</p></li>
</ul>
<p>範例： <strong> SWIPUBSVRTYPE = &quot; HTTP/secure&quot;</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><em>SWIPUBSVRHOST</em></p></td>
<td align="left"><p>IP 位址 | 主機名稱</p></td>
<td align="left"><p>指定應用程式虛擬化伺服器的 IP 位址，或伺服器的主機名稱（可解析成伺服器&#39;s IP 位址）;<em>使用 SWIPUBSVRDISPLAY 時 </em> 是必要的。</p>
<p>範例： <strong> SWIPUBSVRHOST = &quot; SERVER01&quot;</strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><em>SWIPUBSVRPORT</em></p></td>
<td align="left"><p>埠號碼</p></td>
<td align="left"><p>指定此應用程式虛擬化伺服器用來偵聽用戶端要求的邏輯埠（default = 554）。</p>
<ul>
<li><p>標準 HTTP 伺服器—預設 = 80。</p></li>
<li><p>增強的安全性 HTTP 伺服器（預設 = 443）。</p></li>
<li><p>應用程式虛擬化伺服器—預設 = 554。</p></li>
<li><p>增強型安全性應用程式虛擬化伺服器—預設 = 322。</p></li>
</ul>
<p>範例： <strong> SWIPUBSVRPORT = &quot; 443&quot;</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><em>SWIPUBSVRPATH</em></p></td>
<td align="left"><p>路徑名稱</p></td>
<td align="left"><p>指定檔案發佈伺服器上定義檔案類型關聯的位置（預設 =/）;在 <em> SWIPUBSVRTYPE </em> 參數值為 HTTP 時是必要的。</p>
<p>範例： <strong> SWIPUBSVRPATH = &quot; /AppVirt/appsntypes.xml&quot;</strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><em>SWIPUBSVRREFRESH</em></p></td>
<td align="left"><p>[開啟 |出</p></td>
<td align="left"><p>指定當使用者登入用戶端時，用戶端是否會自動查詢檔案類型關聯和應用程式的發佈伺服器（預設 = 開啟）。</p>
<p>範例： <strong> SWIPUBSVRREFRESH = &quot; off&quot;</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><em>SWIGLOBALDATA</em></p></td>
<td align="left"><p>全域資料目錄</p></td>
<td align="left"><p>指定要儲存資料的目錄，而不是特定的使用者（預設 = C:\Documents 和 Settings\All Users\Documents）。</p>
<p>範例： <strong> SWIGLOBALDATA = &quot; D:\Microsoft Application Virtualization Client\Global&quot;</strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><em>SWIUSERDATA</em></p></td>
<td align="left"><p>使用者資料目錄</p></td>
<td align="left"><p>指定將儲存特定使用者專用之資料的目錄（預設值 =% APPDATA%）。</p>
<p>範例： <strong> SWIUSERDATA = &quot; H:\Windows\Microsoft Application Virtualization 用戶端&quot;</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><em>SWIFSDRIVE</em></p></td>
<td align="left"><p>首選的磁片磁碟機號</p></td>
<td align="left"><p>對應至您針對虛擬磁片磁碟機所選取的磁片磁碟機字母。</p>
<p>範例： <strong> SWIFSDRIVE = &quot; S&quot;</strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><em>SYSTEMEVENTLOGLEVEL</em></p></td>
<td align="left"><p>0–4</p></td>
<td align="left"><p>指出記錄層級，日誌訊息會寫入 NT 事件記錄。 此值表示記錄的閾值，也就是等於或小於該值的所有專案都會登入。 例如，0x3 （Warning）的值表示記錄警告（0x3）、錯誤（0x2）及嚴重錯誤（0x1）。</p>
<p>可能的值：</p>
<ul>
<li><p>0 = = 無</p></li>
<li><p>1 = = 臨界</p></li>
<li><p>2 = = 錯誤</p></li>
<li><p>3 = = 警告</p></li>
<li><p>4 = = 資訊</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><em>MINFREESPACEMB</em></p></td>
<td align="left"><p>以 MB 為單位</p></td>
<td align="left"><p>指定在快取大小增加前，在主機上必須提供的可用空間大小（mb）。 下列範例會將用戶端設定為確保磁片上至少有 5 GB 的可用空間，才能讓快取的大小增加。 在安裝時，磁片上的可用磁碟空間大小預設為 5000 MB。</p>
<p>範例： <strong> MINFREESPACEMB = &quot; 5000 &quot; （5 GB）</strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><em>KEEPCURRENTSETTINGS</em></p></td>
<td align="left"><p>[0 | 1]</p></td>
<td align="left"><p>在部署用戶端之前（例如使用群組原則），在您已套用完登錄設定的情況下使用。 部署用戶端時，請將此參數設定為1的值，這樣就不會覆寫註冊表設定。</p>
<div class="alert">
<strong>重要</strong><br/><p>如果設定為值1，則會忽略下列用戶端安裝程式命令列參數：</p>
<p><strong>SWICACHESIZE </strong> 、 <strong> MINFREESPACEMB </strong> 、 <strong> ALLOWINDEPENDENTFILESTREAMING </strong> 、 <strong> APPLICATIONSOURCEROOT </strong> 、 <strong> ICONSOURCEROOT </strong> 、 <strong> </strong> <strong> </strong> <strong> </strong> <strong> </strong> <strong> </strong> <strong> </strong> <strong> </strong> <strong> </strong> OSDSOURCEROOT、SYSTEMEVENTLOGLEVEL、SWIGLOBALDATA、DOTIMEOUTMINUTES、SWIFSDRIVE、AUTOLOADTARGET、AUTOLOADTRIGGERS、SWIUSERDATA、、、、、和。</p>
<p>如需在安裝後設定這些值的進一步資訊，請參閱在應用程式虛擬化（App-v）操作指南（）中的「如何使用命令列來設定 App-v Client Registry 設定」 <a href="https://go.microsoft.com/fwlink/?LinkId=122939" data-raw-source="[https://go.microsoft.com/fwlink/?LinkId=122939](https://go.microsoft.com/fwlink/?LinkId=122939)"> https://go.microsoft.com/fwlink/?LinkId=122939 </a> 。</p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



## 相關主題


[如何手動安裝 Application Virtualization Client](how-to-manually-install-the-application-virtualization-client.md)

[如何升級 Application Virtualization Client](how-to-upgrade-the-application-virtualization-client.md)

[SFTMIME 命令參考](sftmime--command-reference.md)









