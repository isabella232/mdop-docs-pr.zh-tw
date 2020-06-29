---
title: 關於 App-V 5.1
description: 關於 App-V 5.1
author: dansimp
ms.assetid: 35bc9908-d502-4a9c-873f-8ee17b6d9d74
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 4f2404dcd431b32f5d9a4ae7c49f1e376979e04e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800721"
---
# 關於 App-V 5.1


使用下列各節，查看適用于應用程式虛擬化（App-v）5.1 的重大變更資訊：

[App-V 5.1 軟體先決條件及支援的設定](#bkmk-51-prereq-configs)

[遷移至 App-v 5。1](#bkmk-migrate-to-51)

[App-v 5.1 的新功能](#bkmk-whatsnew)

[Windows 10 版 app-v 支援](#bkmk-win10support)

[App-v 管理主控台變更](#bkmk-mgmtconsole)

[排序器改善](#bkmk-seqimprove)

[套件轉換器的改良功能](#bkmk-pkgconvimprove)

[在單一事件觸發程式支援多個腳本](#bkmk-supmultscripts)

[已將安裝資料夾的硬編碼路徑重新導向至虛擬檔案系統根目錄](#bkmk-hardcodepath)

## <a href="" id="bkmk-51-prereq-configs"></a>App-V 5.1 軟體先決條件及支援的設定


請參閱應用程式 V 5.1 軟體先決條件和支援的設定的下列連結。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">連結至先決條件和支援的設定</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="app-v-51-prerequisites.md" data-raw-source="[App-V 5.1 Prerequisites](app-v-51-prerequisites.md)">App-V 5.1 必要條件</a></p></td>
<td align="left"><p>在開始安裝 App-v 5.1 之前必須安裝的必備軟體</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="app-v-51-supported-configurations.md" data-raw-source="[App-V 5.1 Supported Configurations](app-v-51-supported-configurations.md)">App-V 5.1 支援的組態</a></p></td>
<td align="left"><p>支援的作業系統與 App-v Server、Sequencer 及用戶端元件的硬體需求</p></td>
</tr>
</tbody>
</table>



**支援在 app-v 中使用 Configuration Manager：** App-V 5.1 支援 System Center 2012 R2 Configuration Manager SP1。 請參閱[規劃與 Configuration manager 的 App-v 整合](https://technet.microsoft.com/library/jj822982.aspx)，以取得有關將 app-v 環境與 configuration Manager 與 configuration manager 整合在一起的資訊。

## <a href="" id="bkmk-migrate-to-51"></a>遷移至 App-v 5。1


使用下列資訊從舊版升級到 app-v 5.1。 如需詳細資訊，請參閱[從舊版本遷移至 app-v 5.1](migrating-to-app-v-51-from-a-previous-version.md) 。

### 開始升級前

在您開始升級前，請先查看下列資訊：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">升級前要檢查的專案</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>要升級的元件（依任何順序）</p></td>
<td align="left"><ol>
<li><p>App-v Server</p></li>
<li><p>Midi</p></li>
<li><p>App-V 用戶端或 App-v 遠端桌面服務（RDS）用戶端</p></li>
</ol>
<div class="alert">
<strong>注意</strong><br/><p>在 App-V 5.0 SP2 之前，用戶端管理使用者介面（UI）是由 App-v 用戶端安裝所提供。 針對 App-v 5.0 SP2 安裝（或更新版本），您可以透過從 <a href="https://www.microsoft.com/download/details.aspx?id=41186" data-raw-source="[Application Virtualization 5.0 Client UI Application](https://www.microsoft.com/download/details.aspx?id=41186)"> 應用程式虛擬化5.0 用戶端 Ui 應用程式下載來使用用戶端管理 UI </a> 。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>從 App-v （V）升級</p></td>
<td align="left"><p>您必須先升級到 App-v 5.0。 您無法直接從 App-v 升級到 App-v 5.1。 如需詳細資訊，請參閱：</p>
<ul>
<li><p><a href="about-app-v-50.md" data-raw-source="[About App-V 5.0](about-app-v-50.md)">關於 app-v 5.0 中的 [app-v 4.6 與 app-v 5.0 之間的差異]</a></p></li>
<li><p><a href="planning-for-migrating-from-a-previous-version-of-app-v.md" data-raw-source="[Planning for Migrating from a Previous Version of App-V](planning-for-migrating-from-a-previous-version-of-app-v.md)">規劃從舊版 App-V 移轉</a></p></li>
</ul>
<p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>從 App-v 5.0 或更新版本升級</p></td>
<td align="left"><p>您可以直接從下列任何一個版本升級到 App-v 5.1：</p>
<ul>
<li><p>App-V 5。0</p></li>
<li><p>App-V 5.0 SP1</p></li>
<li><p>App-v 5.0 SP2</p></li>
<li><p>App-V 5.0 SP3</p></li>
</ul>
<p>若要升級至 app-v 5.1，請依照本主題其餘章節中的步驟進行。</p>
<p>套件和連線群組會繼續搭配 App-V 5.1 使用，就像目前所做的一樣。</p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-steps-upgrd-infrastruc"></a>升級 App-v 基礎結構的步驟

完成下列步驟，將 App-v 基礎結構的每個元件升級到 App-v 5.1。 下列訂單只是一個建議;您可以依任何順序升級元件。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">步驟</th>
<th align="left">其他資訊</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>步驟1：升級 App-v 伺服器。</p>
<div class="alert">
<strong>注意</strong><br/><p>如果您不是使用 App-v Server，請跳過這個步驟，然後移至下一個步驟。</p>
</div>
<div>

</div></td>
<td align="left"><p>請依照下列步驟執行：</p>
<ol>
<li><p>視您用來升級管理資料庫和/或報告資料庫的方法而定，請執行下列其中一項操作：</p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">資料庫升級方法</th>
<th align="left">步驟</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows Installer</p></td>
<td align="left"><p>跳過這個步驟，移至步驟2，"如果您要升級 App-v Server ..."</p></td>
</tr>
<tr class="even">
<td align="left"><p>SQL 腳本</p></td>
<td align="left"><p>依照 <a href="how-to-deploy-the-app-v-databases-by-using-sql-scripts.md" data-raw-source="[How to Deploy the App-V Databases by Using SQL Scripts](how-to-deploy-the-app-v-databases-by-using-sql-scripts.md)"> 如何使用 SQL 腳本部署 App-v 資料庫的步驟進行 </a> 。</p></td>
</tr>
</tbody>
</table>
<li><p>如果您要從 App-v 5.0 SP1 修復程式套件3或更新版本升級 app-v Server，請完成 <a href="check-reg-key-svr.md" data-raw-source="[Check registry keys after installing the App-V 5.0 SP3 Server](check-reg-key-svr.md)"> 安裝 app-v 5.0 SP3 Server 後檢查登錄機碼一節中的步驟 </a> 。</p></li>
<li><p>遵循 <a href="how-to-deploy-the-app-v-51-server.md" data-raw-source="[How to Deploy the App-V 5.1 Server](how-to-deploy-the-app-v-51-server.md)"> 如何部署 app-v 5.1 Server 的步驟進行</a></p></li>
<p> </p></li>
</ol></td>
</tr>
<tr class="even">
<td align="left"><p>步驟2：升級 App-v 排序器。</p></td>
<td align="left"><p>瞭解 <a href="how-to-install-the-sequencer-beta-gb18030.md" data-raw-source="[How to Install the Sequencer](how-to-install-the-sequencer-beta-gb18030.md)"> 如何安裝排序器 </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>步驟3：升級 App-v 用戶端或 App-v RDS 用戶端。</p></td>
<td align="left"><p>瞭解 <a href="how-to-deploy-the-app-v-client-gb18030.md" data-raw-source="[How to Deploy the App-V Client](how-to-deploy-the-app-v-client-gb18030.md)"> 如何部署 App-v 用戶端 </a> 。</p></td>
</tr>
</tbody>
</table>



### 轉換使用舊版 App-v （V）建立的套件

使用套件轉換器實用程式來升級在 App-v 5.0 之前使用 app-v 版本建立的虛擬應用程式套件。 套件轉換器使用 PowerShell 來轉換套件，如果您有多個需要轉換的套件，就能協助自動處理常式。

**注意**  
App-v 5.1 套件與 App-v 5.0 套件完全相同。 版本之間沒有任何套件格式的變更，因此不需要將 App-v 5.0 套件轉換成 App-v 5.1 套件。



## <a href="" id="bkmk-whatsnew"></a>App-v 5.1 的新功能


以下各節適用于已熟悉 App-v 的使用者，並且想要瞭解 App-v 5.1 中已變更的專案。 如果您還不熟悉 App V，您應該首先閱讀[app-v 5.1 的規劃](planning-for-app-v-51.md)。

### <a href="" id="bkmk-win10support"></a>Windows 10 版 app-v 支援

下表列出應用程式 V 的 Windows 10 支援。 App-V 5.1 之前的 app-v 版本不支援 Windows 10。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">元件</th>
<th align="left">App-V 5.1</th>
<th align="left">App-V 5。0</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>App-v 用戶端</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>否</p></td>
</tr>
<tr class="even">
<td align="left"><p>App-V RDS 用戶端</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>否</p></td>
</tr>
<tr class="odd">
<td align="left"><p>App-v 排序器</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>否</p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-mgmtconsole"></a>App-v 管理主控台變更

本節比較 App V 管理主控台的目前及以前的功能。

### 已不再需要 Silverlight

管理主控台 UI 不再需要 Silverlight。 5.1 管理主控台是在 HTML5 和 JAVAscript 上建立。

### 通知和訊息會個別顯示在對話方塊中

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">App-v 5.1 中的新功能</th>
<th align="left">App-v 5.1 之前</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>郵件指標的數目：</strong></p>
<p>在 App-v 管理主控台的標題列上，現在會在 [旗標] 圖示旁顯示一個數位，以指出等候讀取的訊息數目。</p></td>
<td align="left"><p>您一次只能看到一則訊息或錯誤，而且無法判斷有多少郵件。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>訊息外觀：</strong></p>
<ul>
<li><p>需要使用者輸入的訊息會顯示在您正在查看的目前頁面上方，並需要回應，才能解除它們。</p></li>
<li><p>郵件和錯誤會出現在清單中，而其中一個則位於另一個清單中。</p></li>
</ul></td>
<td align="left"><p>您一次只能看到一則訊息或錯誤。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>關閉郵件：</strong></p>
<p>使用 [ <strong> 全部消除] </strong> 連結，一次關閉所有的郵件和錯誤，或一次解除一個。</p></td>
<td align="left"><p>您一次只能解除一個郵件和錯誤。</p></td>
</tr>
</tbody>
</table>



### 現在，主控台頁面是獨立的 Url

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">App-v 5.1 中的新功能</th>
<th align="left">App-v 5.1 之前</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>主機中的每個頁面都有不同的 URL，可讓您在將來將特定頁面加上書簽供您快速存取。</p>
<p>出現在部分 Url 中的數位代表特定套件。 這些數位是唯一的。</p></td>
<td align="left"><p>所有的主控台頁面都是透過同一個 URL 來存取。</p></td>
</tr>
</tbody>
</table>



### [新增，個別的連線群組] 頁面和功能表選項

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">App-v 5.1 中的新功能</th>
<th align="left">App-v 5.1 之前</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>[連線群組] 頁面現在是主要功能表的一部分，在與 [套件] 頁面相同的層級。</p></td>
<td align="left"><p>若要開啟 [連線群組] 頁面，請流覽 [套件] 頁面。</p></td>
</tr>
</tbody>
</table>



### 套件的功能表選項已變更

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">App-v 5.1 中的新功能</th>
<th align="left">App-v 5.1 之前</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>下列選項現在會出現在 [套件] 頁面底部的按鈕：</p>
<ul>
<li><p>新增或升級</p></li>
<li><p>發佈</p></li>
<li><p>解除發佈</p></li>
<li><p>刪除</p></li>
</ul>
<p>當您以滑鼠右鍵按一下套件以開啟下拉式操作功能表時，仍會顯示下列選項：</p>
<ul>
<li><p>發佈</p></li>
<li><p>解除發佈</p></li>
<li><p>編輯廣告存取</p></li>
<li><p>編輯部署配置</p></li>
<li><p>傳送部署設定的來源 .。。</p></li>
<li><p>轉移存取與設定的來源 .。。</p></li>
<li><p>刪除</p></li>
</ul>
<p>當您按一下 [ <strong> 刪除 </strong> ] 以移除套件時，會開啟一個對話方塊，要求您確認要刪除套件。</p></td>
<td align="left"><p>[ <strong> 新增] 或 [升級] </strong> 選項是位於 [套件] 頁面右上角的按鈕。</p>
<p>[ <strong> 發佈] </strong> 、[ <strong> 取消發佈] 和 [刪除] </strong> <strong> </strong> 選項只有在 [套件] 清單中以滑鼠右鍵按一下套件名稱時才能使用。</p></td>
</tr>
<tr class="even">
<td align="left"><p>在每個套件的 [套件詳細資料] 頁面上，下列套件操作現在都是按鈕：</p>
<ul>
<li><p>[傳輸] （具有下列選項的下拉式功能表）：</p>
<ul>
<li><p>傳送部署設定的來源 .。。</p></li>
<li><p>轉移存取與設定的來源 .。。</p></li>
</ul></li>
<li><p>編輯（連線群組和 AD 存取）</p></li>
<li><p>解除發佈</p></li>
<li><p>刪除</p></li>
<li><p>編輯預設設定</p></li>
</ul></td>
<td align="left"><p>只有當您在 [套件] 清單中以滑鼠右鍵按一下套件名稱時，才能使用這些套件選項。</p></td>
</tr>
</tbody>
</table>



### 左窗格中的圖示有新的色彩和文字

左窗格中圖示的色彩已變更，並新增文字，讓圖示與其他 Microsoft 產品保持一致。

### [概覽] 頁面已移除

在管理主控台的左窗格中，[概覽] 功能表選項及其相關的 [概覽] 頁面都已移除。

### <a href="" id="bkmk-seqimprove"></a>排序器改善

在 App-v 5.1 排序器中，已對套件編輯器進行下列改進。

### 匯入及匯出資訊清單檔案

您可以匯入及匯出 AppxManifest.xml 檔案。 若要匯出資訊清單檔案，請選取 [**高級**] 索引標籤，然後在 [資訊清單檔案] 方塊中，按一下 [**匯出 ...**]。您可以變更資訊清單檔案，例如移除 shell 副檔名或編輯檔案類型關聯。

進行變更之後，按一下 [匯**入**]，然後選取您編輯的檔案。 成功將它匯入後，會立即在套件編輯器中更新資訊清單檔案。

**警告**  
當您匯入檔案時，您的變更會針對 XML 架構進行驗證。 如果檔案無效，您會收到錯誤訊息。 請注意，您可以匯入針對 XML 架構驗證的檔案，但由於其他原因，可能仍無法執行該檔案。



### 新增 Windows 10 至作業系統清單

在 [部署] 索引標籤中，已在您可以為套件排序的作業系統清單中新增 Windows 10 32 位和 Windows 10-64 位。 如果您選取**任何作業系統**，Windows 10 會自動包含在已排序的套件所支援的作業系統中。

### 目前路徑會顯示在虛擬登錄編輯程式的底部

在 [虛擬機器] 索引標籤中，路徑現在會顯示在虛擬的 [註冊編輯器] 底部，可讓您判斷目前選取的索引鍵。 先前，您必須在登錄目錄樹中滾動，才能找到目前選取的索引鍵。

### <a href="" id="combined--find-and-replace--dialog-box-and-shortcut-keys-added-in-virtual-registry-editor"></a>合併的 [尋找及取代] 對話方塊和快速鍵已新增在虛擬登錄編輯程式中

在虛擬登錄編輯程式中，[尋找] 選項（Ctrl + F）已新增快速鍵，並新增了一個對話方塊，其中結合了 [尋找] 和「取代」工作，可讓您尋找及取代值與資料。 若要存取 [組合] 對話方塊，請選取按鍵，然後執行下列其中一項操作：

-   按**Ctrl + H**

-   以滑鼠右鍵按一下索引鍵，然後選取 [**取代**]。

-   選取 [**查看** &gt; **虛擬的註冊表** &gt; **取代**]。

先前，[取代] 對話方塊不存在，您必須手動進行變更。

### 成功重新命名登錄機碼與封裝檔案

您可以重新命名虛擬登錄機碼與檔案，而不會遇到 Sequencer 問題。 先前，如果您嘗試重新命名金鑰，Sequencer 就會停止運作。

### 匯入及匯出虛擬登錄機碼

您可以匯入及匯出虛擬登錄機碼。 若要匯入金鑰，請以滑鼠右鍵按一下要匯入該索引鍵的節點，流覽至您要匯入的索引鍵，然後按一下 [匯**入**]。 若要匯出金鑰，請以滑鼠右鍵按一下該索引鍵，然後選取 [**匯出**]。

### 將目錄匯入虛擬檔案系統

您可以將目錄匯入 VFS。 若要匯入目錄，請按一下 [**套件**檔案] 索引標籤，然後按一下 [**查看** &gt; **虛擬檔案系統**匯 &gt; **入目錄**]。 如果您嘗試匯入的目錄包含 VFS 中的檔案，則匯入會失敗，並會顯示說明性訊息。 在 App-V 5.1 之前，您無法匯入目錄。

### 匯入或匯出 VFS 檔案，而不需刪除，然後再將它新增到套件

您可以將檔案匯入或匯出 VFS 中的檔案，而不必刪除檔案，然後再將檔案新增到套件中。 例如，您可以使用此功能，將變更記錄匯出到本機磁片磁碟機、使用外部編輯器編輯檔案，然後再將檔案匯入 VFS。

若要匯出檔案，請選取 [**封裝**檔案] 索引標籤，以滑鼠右鍵按一下 [VFS] 中的檔案，按一下 [**匯出**]，然後選擇您可以從中進行編輯的匯出位置。

若要匯入檔案，請選取 [**封裝**檔案] 索引標籤，然後以滑鼠右鍵按一下您匯出的檔案。 流覽至您編輯的檔案，然後按一下 [匯**入**]。 匯入的檔案會覆寫現有的檔案。

匯入檔案之後，您必須按一下 [儲存檔案]**來儲存套件** &gt; ** **。

### 新增套件檔案的功能表已移動

已移動 [新增套件檔案] 的功能表選項。 若要尋找 [新增] 選項，請選取 [**封裝**檔案] 索引標籤，然後按一下 [**查看** &gt; **虛擬檔案系統**] [ &gt; **新增**檔案]。 在先前，您以滑鼠右鍵按一下 [VFS] 節點下的資料夾，然後選擇 [**新增**檔案]。

### 根據預設，虛擬登錄節點會展開電腦和使用者配置單元

當您開啟虛擬登錄時，電腦和使用者配置單元會顯示在最上層的登錄節點下方。 先前，您必須展開 [登錄] 節點，才能在下方顯示配置單元。

### 啟用或停用瀏覽器小幫手物件

您可以在排序器使用者介面的 [高級] 索引標籤上選取新的核取方塊，以啟用或停用瀏覽器小幫手物件。 如果瀏覽器小幫手物件：

-   存在於套件中，且已啟用，則預設會選取核取方塊。

-   在套件中存在，且已停用，預設會清除該核取方塊。

-   存在於套件中，有一個或多個啟用，且有一個或多個停用，此核取方塊預設會設定為未定。

-   在套件中不存在，則會停用此核取方塊。

### <a href="" id="bkmk-pkgconvimprove"></a>套件轉換器的改良功能

您現在可以使用套件轉換器來轉換內含腳本的 App-v 4.6 套件，而來源 .osd 檔案的登錄資訊和腳本現在已包含在套件轉換程式輸出中。

如需詳細資訊（包括範例），請參閱[從舊版遷移到 app-v 5.1](migrating-to-app-v-51-from-a-previous-version.md)。

### <a href="" id="bkmk-supmultscripts"></a>在單一事件觸發程式支援多個腳本

App-v 5.1 支援在 App V 套件的單一事件觸發程式上使用多個腳本，包括您要從 App-v 4.6 轉換到 App-v 5.0 或更新版本的套件。 若要啟用多個腳本的使用，App-v 5.1 使用名為 ScriptRunner.exe 的腳本啟動器應用程式，該應用程式是由應用程式 V 用戶端安裝的一部分所安裝。

如需詳細資訊（包括事件觸發程式清單及腳本可執行檔內容），請參閱[關於 app-v 5.1 動態](about-app-v-51-dynamic-configuration.md)設定中的 [腳本] 區段。

### <a href="" id="bkmk-hardcodepath"></a>已將安裝資料夾的硬編碼路徑重新導向至虛擬檔案系統根目錄

當您將套件從 App-v 4.6 轉換為5.1 時，App-v 5.1 套件可以存取您在建立4.6 套件時所需使用的硬驅式硬碟。 磁碟機盤符就是您在4.6 順序電腦上選取為安裝磁碟機的磁片磁碟機。 （預設的磁片磁碟機盤符為 Q:\\.）

先前無法辨識4.6 根資料夾，且 App-v 5.0 套件無法存取。 App-v 5.1 套件可透過完整路徑存取硬編碼檔案，或以程式設計方式列舉 App-v 4.6 安裝根目錄下的檔案。

**技術詳細資料：** App-v 5.1 套件轉換器將在 Filesystem 元素的 FilesystemMetadata.xml 檔案中儲存 App-V 4.6 安裝根資料夾和短資料夾名稱。 當 App-v 5.1 用戶端建立虛擬流程時，它會將 App-v 4.6 安裝根的要求對應至虛擬檔案系統根目錄。

## 如何取得 MDOP 技術


App-v 是 Microsoft 桌面優化套件（MDOP）的一部分。 MDOP 是 Microsoft 軟體保證的一部分。 如需 Microsoft 軟體保證及取得 MDOP 的詳細資訊，請參閱[如何取得 mdop](https://go.microsoft.com/fwlink/?LinkId=322049)。






## 相關主題


[App-V 5.1 的版本資訊](release-notes-for-app-v-51.md)









