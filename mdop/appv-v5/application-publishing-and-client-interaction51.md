---
title: 應用程式發佈與用戶端互動
description: 應用程式發佈與用戶端互動
author: dansimp
ms.assetid: 36a4bf6f-a917-41a6-9856-6248686df352
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: b94ef87043d428ac92fe1656b3afeb8a8b743808
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910818"
---
# <a name="application-publishing-and-client-interaction"></a>應用程式發佈與用戶端互動


本文提供有關一般 App-V 用戶端作業及其與本地作業系統整合的技術資訊。

-   [由序列器所建立 App-V 套件檔案](#bkmk-appv-pkg-files-list)

-   [Appv 檔案中有什麼內容？](#bkmk-appv-file-contents)

-   [App-V 用戶端資料儲存位置](#bkmk-files-data-storage)

-   [套件註冊表](#bkmk-pkg-registry)

-   [App-V 套件存放區行為](#bkmk-pkg-store-behavior)

-   [漫遊註冊表和資料](#bkmk-roaming-reg-data)

-   [App-V 用戶端應用程式生命週期管理](#bkmk-clt-app-lifecycle)

-   [整合 App-V 套件](#bkmk-integr-appv-pkgs)

-   [動態組組處理](#bkmk-dynamic-config)

-   [並排元件](#bkmk-sidebyside-assemblies)

-   [用戶端記錄](#bkmk-client-logging)

有關其他參考資訊，請參閱 [Microsoft Application Virtualization (App-V) 檔資源下載頁面](https://www.microsoft.com/download/details.aspx?id=27760)。

## <a name="app-v-package-files-created-by-the-sequencer"></a><a href="" id="bkmk-appv-pkg-files-list"></a>由序列器所建立 App-V 套件檔案


順序器會建立 App-V 套件，並產生虛擬化應用程式。 排序程式會建立下列檔案：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">檔案</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>.appv</p></td>
<td align="left"><ul>
<li><p>主套件檔案，其中包含從排序程式所捕獲的資產和狀態資訊。</p></li>
<li><p>封裝檔案的架構、發佈資訊，以及可在傳遞時重新套用至電腦和特定使用者的權杖化表單登錄。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>.MSI</p></td>
<td align="left"><p>可執行部署包裝器，您可以使用它手動或使用協力廠商部署平臺來部署 .appv 檔案。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>_DeploymentConfig.XML</p></td>
<td align="left"><p>用來自訂套件中所有應用程式的預設發佈參數的檔案，該套件會全域部署給執行 App-V 用戶端的電腦上的所有使用者。</p></td>
</tr>
<tr class="even">
<td align="left"><p>_UserConfig.XML</p></td>
<td align="left"><p>用來自訂套件中所有應用程式的發佈參數的檔案，該套件是部署至執行 App-V 用戶端的電腦上的特定使用者。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Report.xml</p></td>
<td align="left"><p>排序程式產生的訊息摘要，包括省略的驅動程式、檔案和註冊表位置。</p></td>
</tr>
<tr class="even">
<td align="left"><p>.CAB</p></td>
<td align="left"><p><em>選擇性：用來自動重建先前排序的虛擬應用程式套件 </em> 的封裝快速鍵檔案。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>.apprv</p></td>
<td align="left"><p><em>選擇性：用來保留一般重複使用的序列器設定的順序 </em> 器範本檔案。</p></td>
</tr>
</tbody>
</table>

 

有關排序的資訊，請參閱 [應用程式虛擬化排序指南](https://go.microsoft.com/fwlink/?LinkID=269810)。

## <a name="whats-in-the-appv-file"></a><a href="" id="bkmk-appv-file-contents"></a>Appv 檔案中有什麼內容？


Appv 檔案是一個容器，將 XML 與非 XML 檔案儲存在單一實體中。 此檔案是以 AppX 格式建立，其基礎是 OPEN 封裝慣例和OPC () 標準。

若要查看 appv 檔案內容，請製作套件的複本，然後將複製的檔案重新命名為 ZIP 副檔名。

Appv 檔案包含下列資料夾和檔案，這些資料夾和檔案用於建立和發佈虛擬應用程式：

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名稱</th>
<th align="left">類型</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>根目錄</p></td>
<td align="left"><p>檔案資料夾</p></td>
<td align="left"><p>包含在排序期間所捕獲之虛擬化應用程式的檔案系統的目錄。</p></td>
</tr>
<tr class="even">
<td align="left"><p>[Content_Types].xml</p></td>
<td align="left"><p>XML 檔案</p></td>
<td align="left"><p>Appv 檔案中的核心內容類型清單 (例如 DLL、EXE、BIN) 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AppxBlockMap.xml</p></td>
<td align="left"><p>XML 檔案</p></td>
<td align="left"><p>Appv 檔案的版面配置，使用啟用 App-V 套件中檔案位置和驗證的檔案、封鎖和 BlockMap 元素。</p></td>
</tr>
<tr class="even">
<td align="left"><p>AppxManifest.xml</p></td>
<td align="left"><p>XML 檔案</p></td>
<td align="left"><p>包含新增、發佈和啟動套件所需資訊的套件中繼資料。 包含擴展 (檔案類型關聯和快捷方式) 以及與套件相關聯的名稱和 GUID。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>FilesystemMetadata.xml</p></td>
<td align="left"><p>XML 檔案</p></td>
<td align="left"><p>連續處理期間所捕獲的檔案清單，包括 (、檔案、不透明目錄、空白目錄，以及長) 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>PackageHistory.xml</p></td>
<td align="left"><p>XML 檔案</p></td>
<td align="left"><p>有關電腦與作業系統 (Internet Explorer 版本、.Net Framework 版本) ，以及升級 (套件版本) 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Registry.dat</p></td>
<td align="left"><p>DAT 檔案</p></td>
<td align="left"><p>在套件的排序程式期間所捕獲的登錄機碼和值。</p></td>
</tr>
<tr class="even">
<td align="left"><p>StreamMap.xml</p></td>
<td align="left"><p>XML 檔案</p></td>
<td align="left"><p>主要和發佈功能區塊的檔案清單。 發佈功能區塊包含 ICO 檔案，以及發佈套件時 (EXE 和 DLL) 部分檔案。 當出現時，主要功能區塊包含在排序程式期間針對串流優化的檔案。</p></td>
</tr>
</tbody>
</table>

 

## <a name="app-v-client-data-storage-locations"></a><a href="" id="bkmk-files-data-storage"></a>App-V 用戶端資料儲存位置


App-V 用戶端會執行工作，以確保虛擬應用程式正確執行，並像本地安裝的應用程式一樣運作。 開啟及執行虛擬應用程式的過程需要從虛擬檔案系統和登錄進行映射，以確保應用程式具有使用者預期的傳統應用程式所需元件。 本節說明執行虛擬應用程式所需的資產，並列出 App-V 儲存資產的位置。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名稱</th>
<th align="left">位置</th>
<th align="left">說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>套件市</p></td>
<td align="left"><p>%ProgramData%\App-V</p></td>
<td align="left"><p>唯讀套件檔案的預設位置</p></td>
</tr>
<tr class="even">
<td align="left"><p>電腦目錄</p></td>
<td align="left"><p>%ProgramData%\Microsoft\AppV\Client\Catalog</p></td>
<td align="left"><p>包含每部電腦群組組檔</p></td>
</tr>
<tr class="odd">
<td align="left"><p>使用者目錄</p></td>
<td align="left"><p>%AppData%\Microsoft\AppV\Client\Catalog</p></td>
<td align="left"><p>包含每個使用者的組組檔</p></td>
</tr>
<tr class="even">
<td align="left"><p>快速鍵備份</p></td>
<td align="left"><p>%AppData%\Microsoft\AppV\Client\Integration\ShortCutBackups</p></td>
<td align="left"><p>儲存先前在套件上啟用還原的整合點</p></td>
</tr>
<tr class="odd">
<td align="left"><p>在寫入或 (時複製) 漫遊</p></td>
<td align="left"><p>%AppData%\Microsoft\AppV\Client\VFS</p></td>
<td align="left"><p>可撰寫的漫遊位置以修改套件</p></td>
</tr>
<tr class="even">
<td align="left"><p>在寫入或 (上複製) 本地</p></td>
<td align="left"><p>%LocalAppData%\Microsoft\AppV\Client\VFS</p></td>
<td align="left"><p>可寫入的非漫遊位置，用於套件修改</p></td>
</tr>
<tr class="odd">
<td align="left"><p>電腦註冊表</p></td>
<td align="left"><p>HKLM\Software\Microsoft\AppV</p></td>
<td align="left"><p>包含套件狀態資訊，包括適用于機器的 VReg 或機器配置單元 (全域發佈的套件) </p></td>
</tr>
<tr class="even">
<td align="left"><p>使用者登錄</p></td>
<td align="left"><p>HKCU\Software\Microsoft\AppV</p></td>
<td align="left"><p>包含使用者套件狀態資訊，包括 VReg</p></td>
</tr>
<tr class="odd">
<td align="left"><p>使用者登錄類別</p></td>
<td align="left"><p>HKCU\Software\Classes\AppV</p></td>
<td align="left"><p>包含其他使用者套件狀態資訊</p></td>
</tr>
</tbody>
</table>

 

表格的其他詳細資料會于下方章節和整份檔中提供。

### <a name="package-store"></a>套件存放區

App-V Client 會管理套件存放區中裝載的應用程式資產。 此預設儲存位置為 ，但您可以在設定期間或之後使用 PowerShell 命令進行設定，該命令會修改主鍵 (的 `%ProgramData%\App-V` `Set-AppVClientConfiguration` `PackageInstallationRoot` `HKLM\Software\Microsoft\AppV\Client\Streaming`) 。 套件存放區必須位於用戶端作業系統上的本地路徑。 個別的套件會儲存在套件存放區中，其子目錄命名為套件 GUID 和版本 GUID。

特定應用程式的路徑範例：

``` syntax
C:\ProgramData\App-V\PackGUID\VersionGUID
```

若要在設定期間變更套件存放區的預設位置，請參閱如何 [部署 App-V 用戶端](how-to-deploy-the-app-v-client-51gb18030.md)。

### <a name="shared-content-store"></a>共用內容存放區

如果 App-V 用戶端是在共用內容存放區模式中進行，則當資料流程錯誤發生時，不會將資料寫入磁片，這表示套件需要最小的本地磁碟空間， (發佈) 。 在可限制本地儲存空間的 VDI 環境中，使用較少的磁碟空間非常理想，而從高效能網路位置 (例如 SAN) 串流應用程式) 比較理想。 有關共用內容儲存模式詳細資訊，請參閱 <https://go.microsoft.com/fwlink/p/?LinkId=392750> 。

**注意**  
即使您使用 App-V 用戶端的共用內容存放區配置，電腦和套件存放區也必須位於本機磁碟機上。

 

### <a name="package-catalogs"></a>套件目錄

App-V 用戶端會管理下列兩個以檔案為基礎的位置：

-   **使用者和 (目錄) 。**

-   **註冊表位置** - 取決於套件發佈的目標方式。 有電腦 (目錄) ，以及每個使用者的目錄。 電腦目錄會儲存適用于所有使用者或任何使用者的全域資訊，而使用者目錄會儲存適用于特定使用者的資訊。 目錄是動態組和清單檔案的集合;每個套件版本的檔案和註冊表都有離散資料。 

### <a name="machine-catalog"></a>電腦目錄

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>描述</p></td>
<td align="left"><p>在新增和發佈套件時，儲存電腦上使用者可用的套件檔。 不過，如果發佈時套件是「全域」，則所有使用者都可以使用整合。</p>
<p>如果套件是非全域的，則整合只會發佈給特定使用者，但用戶端電腦上的任何人 (例如，套件目錄位於共用磁片位置) 中，仍有全域資源經過修改且可見。</p>
<p>如果全域或非全域 (電腦上使用者可以使用套件，) 清單會儲存在電腦目錄。 當套件全域發佈時，有一個動態組組檔案，儲存在電腦目錄;因此，根據電腦目錄中是否有原則檔案 (UserDeploymentConfiguration 檔案) 定義套件是否全域。</p></td>
</tr>
<tr class="even">
<td align="left"><p>預設儲存位置</p></td>
<td align="left"><p><code>%programdata%\Microsoft\AppV\Client\Catalog&lt;/code&gt;</p>
<p>此位置與套件存放區位置不同。 套件存放區是封裝檔案的黃金或原始副本。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>電腦目錄中的檔案</p></td>
<td align="left"><ul>
<li><p>Manifest.xml</p></li>
<li><p>DeploymentConfiguration.xml</p></li>
<li><p>UserManifest.xml (全域發佈套件) </p></li>
<li><p>UserDeploymentConfiguration.xml (全域發佈套件) </p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>當套件是連接群組的一部分時，會使用的其他電腦目錄位置</p></td>
<td align="left"><p>除了上述特定套件位置之外，還有下列位置：</p>
<p><code>%programdata%\Microsoft\AppV\Client\Catalog\PackageGroups\ConGroupGUID\ConGroupVerGUID</code></p></td>
</tr>
<tr class="odd">
<td align="left"><p>當套件屬於連接群組時，電腦目錄中的其他檔案</p></td>
<td align="left"><ul>
<li><p>PackageGroupDescriptor.xml</p></li>
<li><p>UserPackageGroupDescriptor.xml (發佈連接群組) </p></li>
</ul></td>
</tr>
</tbody>
</table>

 

### <a name="user-catalog"></a>使用者目錄

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>描述</p></td>
<td align="left"><p>在發佈過程中建立。 包含用來發佈套件的資訊，以及用於啟動時用來確保套件已配置給特定使用者的資訊。 在漫遊位置建立，並包含使用者特定的發佈資訊。</p>
<p>當使用者發佈套件時，系統原則檔案會儲存在使用者目錄。 同時，清單的一份副本也會儲存在使用者目錄。 當使用者移除套件權利時，相關的套件檔案會從使用者目錄中移除。 在查看使用者目錄時，系統管理員可以查看動態群組原則檔案的目前狀態，這表示該套件已授權該使用者。</p>
<p>對於漫遊使用者，使用者目錄必須位於漫遊或共用位置，才能保留預設以使用者為目標的舊 App-V 行為。 權利與策略系結至使用者，而非電腦，因此在資源配置後，應該與使用者漫遊。</p></td>
</tr>
<tr class="even">
<td align="left"><p>預設儲存位置</p></td>
<td align="left"><p><code>appdata\roaming\Microsoft\AppV\Client\Catalog\Packages\PkgGUID\VerGUID</code></p></td>
</tr>
<tr class="odd">
<td align="left"><p>使用者目錄中的檔案</p></td>
<td align="left"><ul>
<li><p>UserManifest.xml</p></li>
<li><p>DynamicConfiguration.xml或UserDeploymentConfiguration.xml</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>當套件是連接群組的一部分時，會使用的其他使用者目錄位置</p></td>
<td align="left"><p>除了上述特定套件位置之外，還有下列位置：</p>
<p><code>appdata\roaming\Microsoft\AppV\Client\Catalog\PackageGroups\PkgGroupGUID\PkgGroupVerGUID</code></p></td>
</tr>
<tr class="odd">
<td align="left"><p>當套件屬於連接群組時，電腦目錄中的其他檔案</p></td>
<td align="left"><p><code>UserPackageGroupDescriptor.xml</code></p></td>
</tr>
</tbody>
</table>

 

### <a name="shortcut-backups"></a>快速鍵備份

在發佈程式期間，App-V 用戶端會備份任何快捷方式和整合點至此備份，當套件未發佈時，這些整合點會還原為先前的 `%AppData%\Microsoft\AppV\Client\Integration\ShortCutBackups.` 版本。

### <a name="copy-on-write-files"></a>在寫入檔案上複製

套件市集包含從發佈伺服器串流之套件檔案的原始副本。 在 App-V 應用程式正常作業期間，使用者或服務可能會要求變更檔案。 這些變更不會在套件存放區中進行，以保留您修復應用程式的能力，因此會移除這些變更。 這些位置稱為在寫入時複製 (或) ，同時支援漫遊和非漫遊位置。 修改的儲存位置取決於應用程式在原生體驗中寫入變更的程式。

### <a name="cow-roaming"></a>牛漫遊

上述的省/市漫遊位置會儲存針對一般 %AppData% 位置或 \\Users\\{username}\AppData\\Roaming 位置的檔案和目錄變更。 然後，這些目錄和檔案會根據作業系統設定漫遊。

### <a name="cow-local"></a>一個本地的一對一

一開始，一開始，一開始一直使用一個網路漫遊位置，但目錄和檔案不會漫遊到其他電腦，即使已配置漫遊支援。 上述的一般區段位置會儲存適用于一般視窗的變更，而非 %AppData% 位置。 列出的目錄會有所不同，但任何一般 Windows 位置 (例如 Common AppData 和 Common AppDataS) 。 當 **虛擬** 服務要求變更為與登入使用者不同的提升使用者時，S 代表受限制的位置。 非**S** 位置會儲存使用者為基礎的變更。

## <a name="package-registry"></a><a href="" id="bkmk-pkg-registry"></a>套件註冊表


應用程式必須先將套件註冊表資料提供給應用程式，應用程式才能存取套件註冊表資料。 App-V Client 會使用真正的註冊表做為所有註冊表資料的支援存放區。

新增套件至 App-V 用戶端時，即為 REGISTRY 的一份副本。套件中的 DAT 檔案會建立于 `%ProgramData%\Microsoft\AppV\Client\VREG\{Version GUID}.dat` 。 檔案名是具有 的版本 GUID。DAT 擴充功能。 複製此副本的原因，是為了確保套件中的實際配置區檔案永遠不會使用，這樣可防止稍後移除套件。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>Package Store 的 Registry.dat</strong></p></td>
<td align="left"><p><strong> &gt; </strong></p></td>
<td align="left"><p><strong>%ProgramData%\Microsoft\AppV\Client\Vreg{VersionGuid}.dat</strong></p></td>
</tr>
</tbody>
</table>

 

當套件的第一個應用程式在用戶端上啟動時，用戶端會從配置區檔案中分期或複製內容，以替代位置重新建立套件註冊表資料 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\AppV\Client\Packages\PackageGuid\Versions\VersionGuid\REGISTRY` 。 階段登錄資料有兩種不同的電腦資料和使用者資料類型。 電腦資料會跨電腦上所有使用者共用。 使用者資料會針對每個使用者分期到使用者特定位置 `HKCU\Software\Microsoft\AppV\Client\Packages\PackageGuid\Registry\User` 。 在套件移除時，電腦資料最終會移除，使用者資料會從使用者取消發佈作業中移除。

### <a name="package-registry-staging-vs-connection-group-registry-staging"></a>套件註冊表暫存與連接組註冊表分段

當存在連接群組時，上一個暫存註冊表程式會保留為 True，但除了要處理一個配置區檔案外，還有一多個檔案。 檔案的處理方式會以連接群組 XML 的顯示順序進行，而第一位作者則勝於任何衝突。

階段註冊表的保留方式與單一套件案例相同。 階段使用者登錄資料會保留為連接群組，直到其停用;在移除連接群組時，會移除階段電腦註冊資料。

### <a name="virtual-registry"></a>虛擬註冊表

VREG (虛擬) 的目的是為應用程式提供套件註冊表和原生註冊表的單一合併視圖。 它也提供寫入時複製 (或) 功能 ，也就是說，從虛擬程式上下文對註冊表進行的任何變更，都是對個別的一個的一個一個的一個。。 這表示 VREG 必須結合最多三個不同的註冊表位置，以根據註冊表的一個位置 ，在 REGISTR 的一個 VIEW - &gt; 套件 - &gt; 原生。 針對註冊表資料提出要求時，它會以順序找到，直到找到要求的資料。 也就是說，如果一個值儲存在一個牛皮位置，它將不會繼續到其他位置，不過，如果一個資料沒有在一個區位中，它會繼續到套件，然後是原生位置，直到它找到適當的資料。

### <a name="registry-locations"></a>註冊表位置

App-V Client 會根據套件是個別發佈還是作為連接群組的一部分來儲存註冊表資訊，共有兩個套件註冊表位置和兩個連接組位置。 有三個套件的一個或三個連接群組的一個區位，這些位置是由 VREG 建立和管理。 設定套件和連接群組的共用物件：

**單一套件 VReg：**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>位置</strong></p></td>
<td align="left"><p><strong>說明</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>牛</strong></p></td>
<td align="left"><ul>
<li><p>Machine Registry\Client\Packages\PkgGUID\REGISTRY (只有提升程式才能撰寫) </p></li>
<li><p>使用者登錄\Client\Packages\PkgGUID\REGISTRY\REGISTRY (在 HKCU 下寫入任何內容 ，軟體\課程除外</p></li>
<li><p>使用者登錄課程\Client\Packages\PkgGUID\REGISTRY (HKCU\Software\Classes 針對非提升程式撰寫和 HKLM) </p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>套件</strong></p></td>
<td align="left"><ul>
<li><p>Machine Registry\Client\Packages\PkgGUID\Versions\VerGuid\Registry\Machine</p></li>
<li><p>使用者登錄類別\Client\Packages\PkgGUID\Versions\VerGUID\Registry</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><strong>本地</strong></p></td>
<td align="left"><ul>
<li><p>原生應用程式註冊表位置</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

 

**連接組 VReg：**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>位置</strong></p></td>
<td align="left"><p><strong>說明</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>牛</strong></p></td>
<td align="left"><ul>
<li><p>Machine Registry\Client\PackageGroups\GrpGUID\REGISTRY (只有提升程式才能撰寫) </p></li>
<li><p>使用者登錄\Client\PackageGroups\GrpGUID\REGISTRY (軟體\課程以外的任何寫入至 HKCU 的內容</p></li>
<li><p>使用者登錄類別\Client\PackageGroups\GrpGUID\REGISTRY</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>套件</strong></p></td>
<td align="left"><ul>
<li><p>Machine Registry\Client\PackageGroups\GrpGUID\Versions\VerGUID\REGISTRY</p></li>
<li><p>使用者登錄類別\Client\PackageGroups\GrpGUID\Versions\VerGUID\REGISTRY</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><strong>本地</strong></p></td>
<td align="left"><ul>
<li><p>原生應用程式註冊表位置</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

 

HKLM 有兩個一個區位;提升和非提升的流程。 提升的流程會一直將 HKLM 變更寫入 HKLM 下的安全的一個記錄。 非提升程式會一直將 HKLM 變更寫入 HKCU\\Software\\Classes 下的非安全性的一個記錄。 當應用程式讀取來自 HKLM 的變更時，提升的流程會讀取來自 HKLM 下之 SECURE 的變更。 非提升讀取兩者，先支援在不安全的一致性的一致性中進行變更。

### <a name="pass-through-keys"></a>傳遞鍵

傳遞鍵可讓系統管理員設定特定金鑰，以便他們只能從原生登錄讀取，而忽略套件和省去位置。 傳遞位置是全域到電腦 (而不是封裝特定的) ，而且可以新增路徑至金鑰來進行配置，而該路徑應視為傳遞至**REG\_MULTI\_SZ**值，稱為金鑰的**PassThroughPaths。** `HKLM\Software\Microsoft\AppV\Subsystem\VirtualRegistry` 此多字串值下顯示的任何 (及其子) 都會視為傳遞。

根據預設，下列位置會配置為傳遞位置：

-   HKEY\_CURRENT\_USER\\SOFTWARE\\Classes\\local 設定\\Software\\Microsoft\\\Windows\CurrentVersion\\AppModel

-   HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Classes\\Local 設定\\Software\\Microsoft\\Windows\\CurrentVersion\\AppModel

-   HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WINERV

-   HKEY\_LOCAL\_MACHINE\\SYSTEM\CurrentControlSet\\services\\eventlog\\Application

-   HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\WMI\\Autologger

-   HKEY\_CURRENT\_USER\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet 設定

-   HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Perflib

-   HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Policies

-   HKEY\_CURRENT\_USER\\SOFTWARE\\Policies

傳遞鍵的用途是為了確保虛擬應用程式不會在 VReg 中寫入非虛擬應用程式成功的操作或整合所需的註冊表資料。 策略鍵可確保使用系統管理員所設定之群組原則設定，而不是每個套件設定。 與新式 UI 應用程式整合時，Windows AppModel 金鑰。 建議系統管理不要修改任何預設的傳遞鍵，但在某些情況下，根據應用程式行為，可能需要新增額外的傳遞鍵。

## <a name="app-v-package-store-behavior"></a><a href="" id="bkmk-pkg-store-behavior"></a>App-V 套件存放區行為


App-V 5 會管理套件存放區，這是儲存 Appv 檔案中展開資產檔案的位置。 根據預設，此位置會儲存在 %ProgramData%\\App-V，且僅受限於可用空間的儲存功能。 如上一節所述，套件存放區是由套件和版本的 GUID 組織。

### <a name="add-packages"></a>新增套件

App-V 套件會于使用 App-V 用戶端的電腦之外進行階段化。 App-V 用戶端提供暫存。 在發佈或手動 Add-AppVClientPackage 期間，資料結構會建在套件存放區 (c：\\programdata\\App-V\\{PkgGUID}\\{VerGUID}) 。 系統會新增在 StreamMap.xml中定義的發佈區塊中識別的套件檔案，並分期處理頂層資料夾和子檔案，以確保啟動時有適當的應用程式資產。

### <a name="mounting-packages"></a>安裝套件

您可以使用 PowerShell 或 App-V 用戶端 UI 下載套件來明確 `Mount-AppVClientPackage` 載入套件。 **** 此作業將整個套件完全載入至套件存放區。

### <a name="streaming-packages"></a>串流套件

App-V 用戶端可以配置為變更串流的預設行為。 所有串流策略都儲存在下列登錄機碼下 `HKEY_LOCAL_MAcHINE\Software\Microsoft\AppV\Client\Streaming` ：。 策略是使用 PowerShell Cmdlet 來設定 `Set-AppvClientConfiguration` 。 下列原則適用于串流：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">原則</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>AllowHighCostLaunch</p></td>
<td align="left"><p>在 Windows 8 及之後，允許串流至 3G 和行動電話網路</p></td>
</tr>
<tr class="even">
<td align="left"><p>自動載入</p></td>
<td align="left"><p>指定背景載入設定：</p>
<p><strong>0 </strong> - 已停用</p>
<p><strong>1 </strong> – 先前僅使用過的套件</p>
<p><strong>2 </strong> – 所有套件</p></td>
</tr>
<tr class="odd">
<td align="left"><p>PackageInstallationRoot</p></td>
<td align="left"><p>本機電腦中套件存放區之根資料夾</p></td>
</tr>
<tr class="even">
<td align="left"><p>PackageSourceRoot</p></td>
<td align="left"><p>應從其中串流處理套件的根重寫</p></td>
</tr>
<tr class="odd">
<td align="left"><p>SharedContentStoreMode</p></td>
<td align="left"><p>啟用 VDI 案例的共用內容存放區使用</p></td>
</tr>
</tbody>
</table>

 

 

這些設定會影響將 App-V 套件資產串流至用戶端的行為。 根據預設，App-V 只會下載初始發佈和主要功能區塊之後所需的資產。 串流套件的三種特定行為必須說明：

-   背景串流

-   優化串流

-   串流錯誤

### <a name="background-streaming"></a>背景串流

PowerShell Cmdlet 可用來判斷目前使用自動載入設定進行背景串流的模式，並且使用 `Get-AppvClientConfiguration` Cmdlet Set-AppvClientConfiguration 修改，或從註冊表 (HKLM\\SOFTWARE\\Microsoft\\AppV\\ClientStreaming 鍵) 修改。 背景串流是預設設定，其中自動載入設定設定為下載先前使用的套件。 根據預設設定 (value=1 的行為) 應用程式啟動之後，會下載背景中的 App-V 資料區塊。 不論所有套件是否已啟動 (value=0) 或針對所有套件 (value=2) ，都可以一起停用此設定。

### <a name="optimized-streaming"></a>優化串流

在排序期間，App-V 套件可以使用主要功能區塊進行配置。 此設定可讓排序工程師監控特定應用程式或應用程式的啟動檔案，並標記 App-V 套件中的資料區塊，以在套件中任何應用程式第一次啟動時串流。

### <a name="stream-faults"></a>串流錯誤

在任何發佈資料的初始串流和主要功能區塊之後，其他檔案的要求會執行串流錯誤。 這些資料區塊會根據需要下載到套件存放區。 這允許使用者只下載套件的一小部分，通常足以啟動套件並執行一般工作。 當使用者啟動需要目前不在套件存放區中之資料的作業時，會下載所有其他區塊。

有關 App-V 套件串流流覽詳細資訊 <https://go.microsoft.com/fwlink/?LinkId=392770> ：。

串流優化的排序方法可在： <https://go.microsoft.com/fwlink/?LinkId=392771> .

### <a name="package-upgrades"></a>套件升級

App-V 套件需要更新應用程式的整個生命週期。 App-V 套件升級與套件發佈作業類似，因為每個版本都會在各自的 PackageRoot 位置建立 `%ProgramData%\App-V\{PkgGUID}\{newVerGUID}` ：。 升級作業已優化，從相同套件的其他版本建立相同和串流檔案的硬連結。

### <a name="package-removal"></a>移除套件

移除套件時，App-V 用戶端的行為取決於移除的方法。 使用 App-V 完整基礎結構來取消發佈應用程式，全域發佈應用程式 (的使用者目錄檔案 (電腦目錄) 會移除，但會保留套件存放區位置和一個 MACHINE 位置。 當 PowerShell Cmdlet 用來移除 `Remove-AppVClientPackge` App-V 套件時，套件存放區位置會清除。 請記住，從管理伺服器取消發佈 App-V 套件不會執行移除作業。 這兩個作業均不會移除套件市/市套件檔案。

## <a name="roaming-registry-and-data"></a><a href="" id="bkmk-roaming-reg-data"></a>漫遊註冊表和資料


App-V 5 可以在漫遊時提供接近原生的體驗，視所使用的應用程式撰寫方式而不同。 根據預設，App-V 會根據作業系統的漫遊配置，漫遊儲存在漫遊位置中的 AppData。 儲存檔案型資料的其他位置不會在電腦間漫遊，因為它們位於未漫遊的位置。

### <a name="roaming-requirements-and-user-catalog-data-storage"></a><a href="" id="bkmk-clt-inter-roam-reqs"></a>漫遊需求和使用者目錄資料儲存空間

App-V 會以以下形式儲存代表使用者目錄狀態的資料：

-   %appdata%\\Microsoft\\AppV\\Client\\Catalog 下的檔案

-   下的註冊表設定 `HKEY_CURRENT_USER\Software\Microsoft\AppV\Client\Packages`

這些檔案和登錄設定一起代表使用者的目錄，因此這兩者都必須漫遊，或兩者都必須漫遊給指定使用者。 App-V 不支援漫遊 %AppData%，但不支援漫遊使用者的設定檔 (登錄) ，反之亦然。

**注意**  
**Repair-AppvClientPackage** Cmdlet 無法修復套件的發佈狀態，因為使用者的 App-V 狀態在 %appdata%中遺失或與資料不符 `HKEY_CURRENT_USER` 。

 

### <a name="registry-based-data"></a>以註冊表為基礎的資料

App-V 註冊表漫遊分為兩種情況，如下表所示。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">案例</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>以標準使用者執行的應用程式</p></td>
<td align="left"><p>當標準使用者啟動 App-V 應用程式時，適用于 App-V 的 HKLM 和 HKCU 應用程式會儲存在本機上的 HKCU 配置區中。 這呈現為兩種不同的路徑：</p>
<ul>
<li><p>HKLM：HKCU\SOFTWARE\Classes\AppV\Client\Packages{PkgGUID}\REGISTRY\MACHINE\SOFTWARE</p></li>
<li><p>HKCU：HKCU\SOFTWARE\Microsoft\AppV\Client\Packages{PkgGUID}\REGISTRY\USER{UserSID}\SOFTWARE</p></li>
</ul>
<p>位置會根據作業系統設定啟用漫遊。</p></td>
</tr>
<tr class="even">
<td align="left"><p>使用標高執行的應用程式</p></td>
<td align="left"><p>當應用程式以高度啟動時：</p>
<ul>
<li><p>HKLM 資料會儲存在本地電腦的 HKLM 配置區中</p></li>
<li><p>HKCU 資料會儲存在使用者登錄位置</p></li>
</ul>
<p>在此情境中，這些設定不會以一般作業系統漫遊設定漫遊，產生的登錄機碼和值會儲存在下列位置：</p>
<ul>
<li><p>HKLM\SOFTWARE\Microsoft\AppV\Client\Packages{PkgGUID}{UserSID}\REGISTRY\MACHINE\SOFTWARE</p></li>
<li><p>HKCU\SOFTWARE\Microsoft\AppV\Client\Packages{PkgGUID}\Registry\User{UserSID}\SOFTWARE</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

### <a name="app-v-and-folder-redirection"></a>App-V 和資料夾重新導向

App-V 5.1 支援漫遊 AppData 資料夾的資料夾重新導向 (%AppData%) 。 當虛擬環境啟動時，使用者的漫遊 AppData 目錄的漫遊 AppData 狀態會複製到本機快取。 相反地，當虛擬環境關閉時，與特定使用者的漫遊 AppData 相關聯的本機快取會傳輸至該使用者漫遊的 AppData 目錄的實際位置。

一般的套件會對應多個位置，以在使用者的支援存放區中對應 AppData\\Local 和 AppData\\Roaming 中的設定。 這些位置是每個使用者儲存在使用者設定檔中的寫入時複製位置，用來儲存對套件 VFS 目錄的變更，以及保護預設的套件 VFS。

下表顯示尚未執行資料夾重新導向時的本地和漫遊位置。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">套件中的 VFS 目錄</th>
<th align="left">備份存放區對應位置</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>ProgramFilesX86</p></td>
<td align="left"><p>C：\users\jsmith\AppData &lt; Strong &gt; Local </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \ProgramFilesX86</p></td>
</tr>
<tr class="even">
<td align="left"><p>SystemX86</p></td>
<td align="left"><p>C：\users\jsmith\AppData &lt; Strong &gt; Local </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \SystemX86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows</p></td>
<td align="left"><p>C：\users\jsmith\AppData &lt; Strong &gt; Local </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \Windows</p></td>
</tr>
<tr class="even">
<td align="left"><p>appv_ROOT</p></td>
<td align="left"><p>C：\users\jsmith\AppData &lt; Strong &gt; Local </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \appv_ROOT</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AppData</p></td>
<td align="left"><p>C：\users\jsmith\AppData &lt; 強 &gt; 漫遊 </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \AppData</p></td>
</tr>
</tbody>
</table>

 

 

下表顯示本地和漫遊位置，當 %AppData% 已實現資料夾重新導向，且位置已重新導向 (通常會重新導向到網路) 。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">套件中的 VFS 目錄</th>
<th align="left">備份存放區對應位置</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>ProgramFilesX86</p></td>
<td align="left"><p>C：\users\jsmith\AppData &lt; Strong &gt; Local </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \ProgramFilesX86</p></td>
</tr>
<tr class="even">
<td align="left"><p>SystemX86</p></td>
<td align="left"><p>C：\users\jsmith\AppData &lt; Strong &gt; Local </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \SystemX86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows</p></td>
<td align="left"><p>C：\users\jsmith\AppData &lt; Strong &gt; Local </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \Windows</p></td>
</tr>
<tr class="even">
<td align="left"><p>appv_ROOT</p></td>
<td align="left"><p>C：\users\jsmith\AppData &lt; Strong &gt; Local </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \appv_ROOT</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AppData</p></td>
<td align="left"><p><strong>\Fileserver </strong> \users\jsmith\roaming\Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \AppData</p></td>
</tr>
</tbody>
</table>

 

 

目前的 App-V 用戶端 VFS 驅動程式無法寫入網路位置，因此 App-V 用戶端會在發佈和虛擬環境啟動時偵測資料夾重新導向是否存在，並複製本地磁片磁碟機上的資料。 使用者關閉 App-V 應用程式且 App-V Client 關閉虛擬環境之後，VFS AppData 的本地儲存空間會複製回網路，以漫遊至其他電腦，而此程式會重複執行。 程式的詳細步驟如下：

1.  在發佈或虛擬環境啟動期間，App-V 用戶端會偵測 AppData 目錄的位置。

2.  如果漫遊 AppData 路徑是本地或 ino AppData\\Roaming 位置已對應，則沒有任何反應。

3.  如果漫遊 AppData 路徑不是本地路徑，則 VFS AppData 目錄會對應到本地 AppData 目錄。

此程式可解決 App-V 用戶端 VFS 驅動程式不支援的非本地 %AppData% 問題。 不過，儲存在這個新位置的資料不會隨著資料夾重新導向而漫遊。 應用程式執行期間的所有變更都發生在本地 AppData 位置，而且必須複製到重新導向的位置。 此程式的詳細步驟為：

1.  App-V 應用程式已關閉，這會關閉虛擬環境。

2.  漫遊 AppData 位置的本機快取會壓縮並儲存在 ZIP 檔案中。

3.  ZIP 封裝程式結尾的時間戳記會用來命名檔案。

4.  時間戳記會記錄在註冊表中：HKEY\_CURRENT\_USER\Software\\Microsoft\\AppV\\Client\Packages\\ &lt; GUID \\AppDataTime 做為最後一個已知的 AppData 時間戳記。 &gt;

5.  資料夾重新導向程式會稱為評估並啟動上傳到漫遊 AppData 目錄的 ZIP 檔案。

時間戳記用於判斷發生衝突時「最後一位作者勝負」案例，並用於優化 App-V 應用程式發佈或虛擬環境啟動時資料的下載。 資料夾重新導向會提供支援政策涵蓋之任何其他用戶端的資料，並啟動將 AppData\\Roaming 資料儲存到用戶端上的本地 AppData 位置的流程。 詳細程式如下：

1.  使用者啟動應用程式以啟動虛擬環境。

2.  應用程式的虛擬環境會檢查最新的時間戳記 ZIP 檔案 ，如果有。

3.  會針對上次已知的上傳時間戳記檢查註冊表 ，如果有。

4.  除非當地上次已知的上傳時間戳記大於或等於 ZIP 檔案的時間戳記，否則會下載最新的 ZIP 檔案。

5.  如果本地上次已知的上傳時間戳記早于漫遊 AppData 位置中最新的 ZIP 檔案，ZIP 檔案會解壓縮到使用者設定檔中的本地臨時目錄。

6.  成功解壓縮 ZIP 檔案後，漫遊 AppData 目錄的本機快取會重新命名，新資料會移至就地。

7.  重新命名的目錄會被刪除，應用程式隨即開啟，其中會包含最近儲存的漫遊 AppData 資料。

這已完成 AppData\\Roaming 位置中應用程式設定的成功漫遊。 唯一必須解決的其他條件是套件修復作業。 程式詳細資料為：

1.  在修復期間，偵測使用者漫遊 AppData 目錄的路徑是否非本地。

2.  地圖非本地漫遊 AppData 路徑目標會重新建立預期的漫遊和本地 AppData 位置。

3.  刪除儲存在註冊表中的時間戳記 ，如果有。

此程式會為 AppData 重新建立本地和網路位置，並移除時間戳記的註冊表記錄。

## <a name="app-v-client-application-lifecycle-management"></a><a href="" id="bkmk-clt-app-lifecycle"></a>App-V 用戶端應用程式生命週期管理


在 App-V 完整基礎結構中，應用程式排序之後，會透過 App-V 管理和發佈伺服器管理併發布給使用者或電腦。 本節詳細說明在一般 App-V 應用程式生命週期作業期間發生的作業 (新增、發佈、啟動、升級和移除) 以及從 App-V 用戶端角度變更及修改的檔案和註冊表位置。 App-V 用戶端作業是在執行 App-V 用戶端的電腦上啟動的一系列 PowerShell 命令執行。

本檔著重于 App-V 完整基礎結構解決方案。 有關 App-V 與 Configuration Manager 2012 整合的特定資訊，請流覽： <https://go.microsoft.com/fwlink/?LinkId=392773> 。

App-V 應用程式生命週期工作在使用者登入時觸發 (預設) 機器啟動，或做為背景時間作業。 App-V 用戶端作業的設定 ，包括發佈伺服器、重新更新間隔、套件腳本啟用及其他設定，在用戶端設定期間或使用 PowerShell 命令進行設定之後設定。 請參閱如何在 TechNet 上部署用戶端一節： [如何部署 App-V 用戶端](how-to-deploy-the-app-v-client-51gb18030.md) 或使用 PowerShell：

```powershell
get-command *appv*
```

### <a name="publishing-refresh"></a>發佈重新版

發佈重新處理是由幾個在 App-V 用戶端上執行的較小作業所組成。 由於 App-V 是應用程式虛擬化技術，而非任務排程技術，因此 Windows 任務排程器會用來在使用者登入、電腦啟動和排定的時間間隔啟用程式。 上述設定期間用戶端的設定是將用戶端發佈至具有正確設定的大型電腦群組時的首選方法。 這些用戶端設定可設定為下列 PowerShell Cmdlet：

-   **Add-AppVPublishingServer：** 使用提供 App-V 套件的 App-V 發佈伺服器來設定用戶端。

-   **Set-AppVPublishingServer：** 修改 App-V 發佈伺服器目前的設定。

-   **Set-AppVClientConfiguration：** 修改 App-V 用戶端的目前設定。

-   **Sync-AppVPublishingServer：** 手動啟動 App-V 發佈重新更新程式。 這也用於發佈伺服器組組期間所建立之排程任務。

下列各節的焦點是詳述 App-V 發佈重新更新的不同階段期間發生的作業。 主題包括：

-   新增 App-V 套件

-   發佈 App-V 套件

### <a name="adding-an-app-v-package"></a>新增 App-V 套件

新增 App-V 套件至用戶端是發佈重新更新程式的第一個步驟。 最終結果與 PowerShell 中的 Cmdlet 相同，除非在發佈重新更新新增程式期間，系統會與已配置的發佈伺服器聯繫，並傳回應用程式高層級清單回用戶端，以提取更詳細的資訊，而不是單一套件新增 `Add-AppVClientPackage` 作業。 程式會持續進行，針對套件或連接群組新增或更新進行用戶端，然後存取 appv 檔案。 接下來，Appv 檔案的內容會展開，並放置在適當的位置的本地作業系統上。 以下是程式的詳細工作流程，假設套件已針對錯誤串流進行配置。

**如何新增 App-V 套件**

1.  透過 PowerShell 或發佈重新發佈程式的工作順序開始手動啟動。

    1.  App-V 用戶端會建立 HTTP 連接，並依據目標要求應用程式清單。 發佈重新處理支援目的電腦或使用者。

    2.  App-V 發佈伺服器會使用啟動目標、使用者或機器的身分識別，並查詢資料庫以尋找授權應用程式的清單。 應用程式清單提供為 XML 回應，用戶端會用來傳送其他要求至伺服器，以依據每個套件提供詳細資訊。

2.  App-V 用戶端上的發佈代理程式會執行下列序列化的所有動作。

    評估未發佈或停用的任何連接群組，因為無法處理屬於連接群組的套件版本更新。

3.  識別新增或更新作業來設定套件。

    1.  App-V 用戶端會使用 AppX API Windows從發佈伺服器存取 Appv 檔案。

    2.  套件檔案會開啟，AppXManifest.xmlStreamMap.xml下載至套件存放區。

    3.  完全串流發佈區塊資料，定義于 StreamMap.xml。 將發佈區塊資料儲存在套件市集\\PkgGUID\\VerGUID\\root中。

        -   圖示：擴充點的目標。

        -   可攜式可執行 (頁首) ：包含磁片、直接存取或檔案類型之影像需求之基本資訊的擴充點目標。

        -   腳本：下載腳本目錄，以用於整個發佈程式。

    4.  填入套件存放區：

        1.  在磁片上建立代表所列任何目錄之解壓縮套件的稀疏檔案。

        2.  在根目錄下階段頂層檔案和目錄。

        3.  所有其他檔案都是當目錄在磁片上列為稀疏目錄並按需求串流時建立。

    5.  建立電腦目錄專案。 如果套件Manifest.xmlDeploymentConfiguration.xml，請從套件 (建立DeploymentConfiguration.xml並建立預留位置) 。

    6.  在註冊表中建立套件存放區的位置 HKLM\\Software\\Microsoft\\AppV\\Client\Package\\PkgGUID\\Versions\\VerGUID\Catalog

    7.  從套件存放區建立 Registry.dat 檔案至 %ProgramData%\\Microsoft\\AppV\\Client\\VReg\\{VersionGUID}.dat

    8.  使用 App-V 核心模式驅動程式 HKLM\\Microsoft\\Software\\AppV\\MAV 註冊套件

    9.  從檔或檔案AppxManifest.xml腳本DeploymentConfig.xml套件新增時間。

4.  新增及啟用或停用來設定連接群組。

5.  移除未發佈到目標物件 (或電腦) 。

    **注意**  
    這不會執行套件刪除，而是移除特定目標 (使用者或電腦) 的整合點，並移除全域發佈 (中的使用者目錄檔案 (電腦目錄) 。

     

6.  根據用戶端組組來調用背景載入安裝。

7.  已針對電腦或使用者發佈資訊的套件會立即還原。

    **注意**  
    此情況會以移除產品發生，而不會以封裝的背景新增來取消發佈。

     

這會完成發佈重新處理 App-V 套件的新增。 下一個步驟是發佈套件至特定目標 (或使用者) 。

![套件新增檔案和註冊表資料。](images/packageaddfileandregistrydata.png)

### <a name="publishing-an-app-v-package"></a>發佈 App-V 套件

在發佈重新整理作業期間，特定的發佈作業 (Publish-AppVClientPackage) 會新增專案至使用者目錄、將許可權地圖給使用者、識別本地市集，然後完成任何整合步驟。 以下是詳細步驟。

**如何發佈與 App-V 套件**

1.  套件專案會新加到使用者目錄

    1.  使用者目標套件：UserDeploymentConfiguration.xml使用者UserManifest.xml目錄中的機器上放置一組和一組

    2.  機器目標 (全域) 套件：UserDeploymentConfiguration.xml位於電腦目錄

2.  在 HKLM\\Software\\Microsoft\\AppV\\MAV 向使用者的核心模式驅動程式註冊套件

3.  執行整合工作。

    1.  建立延伸點。

    2.  在使用者的登錄和漫遊設定檔中儲存備份資訊 (快捷方式) 。

        **注意**  
        這會在套件未發佈時啟用還原擴充點。

         

    3.  執行針對發佈時間所針對的腳本。

發佈屬於連接群組的 App-V 套件與上述程式非常類似。 對於連接群組，儲存特定目錄資訊的路徑包括作為目錄目錄子目錄子目錄的 PackageGroups。 請查看上述機器和使用者目錄資訊以查看詳細資料。

![套件新增檔案和註冊表資料 - 全域。](images/packageaddfileandregistrydata-global.png)

### <a name="application-launch"></a>應用程式啟動

發佈重新更新程式之後，使用者會啟動 App-V 應用程式，然後重新開機應用程式。 此程式非常簡單且經過優化，能以最小的網路流量快速啟動。 App-V 用戶端會檢查發佈期間所建立之檔案的使用者目錄路徑。 建立啟動套件的權利之後，App-V Client 會建立虛擬環境、開始串流任何必要的資料，並套用在虛擬環境建立期間適用的清單和部署設定檔。 建立虛擬環境並針對特定套件和應用程式進行配置後，應用程式即會啟動。

**如何啟動 App-V 應用程式**

1.  使用者按一下快捷方式或檔案類型的啟動應用程式。

2.  App-V 用戶端會驗證下列檔案的使用者目錄是否存在

    -   UserDeploymentConfiguration.xml

    -   UserManifest.xml

3.  如果檔案存在，應用程式即有資格供該特定使用者使用，應用程式會啟動啟動程式。 此時沒有網路流量。

4.  接下來，App-V 用戶端會檢查登錄 App-V 用戶端服務之套件的路徑是否位於登錄中。

5.  找到套件存放區的路徑後，即會建立虛擬環境。 如果這是第一次啟動，則主要功能區塊會下載 ，如果有。

6.  下載之後，App-V 用戶端服務會耗用清單和部署設定檔，以設定虛擬環境，並載入所有 App-V 子系統。

7.  應用程式會啟動。 針對套件存放區中任何遺失的檔案 (的) ，App-V 會根據需要串流錯誤檔案。

    ![套件新增檔案和註冊表資料 - stream。](images/packageaddfileandregistrydata-stream.png)

### <a name="upgrading-an-app-v-package"></a>升級 App-V 套件

App-V 5 套件升級程式與舊版 App-V 不同。 App-V 在有權擁有不同使用者之電腦上支援同一套件的多個版本。 當套件存放區與目錄更新為新的資源時，您隨時都可以新增套件版本。 新增新版本資源的唯一程式是儲存優化。 升級期間，只會將新檔案新加入新版本存放區位置，並針對未改變的檔案建立硬連結。 這只會在一個磁片位置呈現檔案，然後將檔案放在磁片上有檔案位置專案的所有資料夾，以減少整體儲存空間。 升級 App-V 套件的特定詳細資料如下：

**如何升級 App-V 套件**

1.  App-V 用戶端會執行發佈重新更新，並探索較新版本的 App-V 套件。

2.  套件專案會新版新版的適當目錄新增到

    1.  使用者目標套件：UserDeploymentConfiguration.xml和 UserManifest.xml 會放在使用者目錄中的機器上，位置為 appdata\\roaming\\Microsoft\\AppV\\Client\\Catalog\Packages\\PkgGUID\\VerGUID

    2.  電腦 (全域) 套件：UserDeploymentConfiguration.xml 會置於電腦目錄中 %programdata%\\Microsoft\\AppV\\Client\\Catalog\Packages\\PkgGUID\\VerGUID

3.  在 HKLM\\Software\\Microsoft\\AppV\\MAV 向使用者的核心模式驅動程式註冊套件

4.  執行整合工作。

    -   從清單和動態 (整合 (EP) 點。

    1.  檔案型 EP 資料會利用套件存放區中的連接點，儲存在 AppData 資料夾中。

    2.  版本 1 EPs 已在新版本可用時存在。

    3.  擴充點會切換至電腦或使用者目錄中的版本 2 位置，以用於任何較新的或更新的擴充點。

5.  執行針對發佈時間所針對的腳本。

6.  根據需要並排安裝元件。

### <a name="upgrading-an-in-use-app-v-package"></a>升級使用中的 App-V 套件

**從 App-V 5 SP2**開始：如果您嘗試升級使用者使用的套件，升級工作會置於擱置狀態。 根據下列規則，升級稍後會執行：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">工作類型</th>
<th align="left">適用規則</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>使用者型工作，例如發佈套件給使用者</p></td>
<td align="left"><p>待處理的工作將在使用者登出後執行，然後重新登錄。</p></td>
</tr>
<tr class="even">
<td align="left"><p>全域任務，例如啟用全域連接群組</p></td>
<td align="left"><p>當電腦關閉並重新啟動時，將會執行擱置的工作。</p></td>
</tr>
</tbody>
</table>

 

當工作處於擱置狀態時，App-V 用戶端也會為擱置的工作產生一個登錄機碼，如下所示：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">使用者型或全域型工作</th>
<th align="left">產生登錄機碼的地方</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>使用者型工作</p></td>
<td align="left"><p>KEY_CURRENT_USER\Software\Microsoft\AppV\Client\PendingTasks</p></td>
</tr>
<tr class="even">
<td align="left"><p>全域任務</p></td>
<td align="left"><p>HKEY_LOCAL_MACHINE\Software\Microsoft\AppV\Client\PendingTasks</p></td>
</tr>
</tbody>
</table>

 

使用者必須先完成下列作業，才能使用較新版本的套件：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">工作</th>
<th align="left">詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>將套件新增到電腦</p></td>
<td align="left"><p>這項工作是電腦專用，您隨時都可以完成上述的套件新增區段的步驟來執行。</p></td>
</tr>
<tr class="even">
<td align="left"><p>發佈套件</p></td>
<td align="left"><p>請參閱上方的套件發佈一節以瞭解步驟。 此程式要求您更新系統上的擴充點。 完成這項工作時，使用者無法使用應用程式。</p></td>
</tr>
</tbody>
</table>

 

使用下列範例案例做為更新套件的指南。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">案例</th>
<th align="left">需求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>當您嘗試升級時，App-V 套件並未使用中</p></td>
<td align="left"><p>套件的下列元件均無法使用：虛擬應用程式、COM 伺服器或 shell 擴充程式。</p>
<p>系統管理員會發佈較新版本的套件，下次啟動套件內的元件或應用程式時，升級會運作。 新版本的套件會串流並執行。 在此案例的 App-V 5 SP2 中，App-V 5 的先前版本沒有任何變更。</p></td>
</tr>
<tr class="even">
<td align="left"><p>當系統管理員發佈較新版本的套件時，App-V 套件已使用中</p></td>
<td align="left"><p>App-V Client 將升級作業設定為擱置，這表示該作業會排入佇列，並稍後在套件未使用時執行。</p>
<p>如果套件應用程式使用中，使用者會關閉虛擬應用程式，之後就可以進行升級。</p>
<p>如果套件具有 2013 (Office 2013) ，且由 Windows Explorer 永久載入，使用者就無法登入。 使用者必須登出並重新登入，才能啟動 App-V 套件升級。</p></td>
</tr>
</tbody>
</table>

 

### <a name="global-vs-user-publishing"></a>全域與使用者發佈

App-V 套件可以以兩種方式之一發布;將 App-V 套件授權給特定使用者或使用者群組的使用者，以及將 App-V 套件授權給整部機器的全域使用者。 一旦已掛上套件升級，且 App-V 套件並未使用，請考慮以下兩種發佈類型：

-   **全域發佈**：應用程式會發佈至電腦;該電腦上所有使用者都可以使用它。 升級將在 App-V 用戶端服務啟動時進行，這實際上表示電腦重新開機。

-   **使用者已發佈**：應用程式會發佈給使用者。 如果電腦上有多個使用者，應用程式可以發佈給使用者的子集。 當使用者登錄或重新發佈時 (、ConfigMgr 策略重新更新和評估，或 App-V 定期發佈/重新更新，或明確透過 PowerShell 命令或) 時，就會進行升級。

### <a name="removing-an-app-v-package"></a>移除 App-V 套件

在完整基礎結構中移除 App-V 應用程式是未發佈的作業，而且不會執行套件移除。 此程式與上述發佈程式相同，但移除程式會反轉 App-V 套件的變更，而不是新增移除程式。

### <a name="repairing-an-app-v-package"></a>修復 App-V 套件

修復作業非常簡單，但可能會影響到電腦上許多位置。 先前提及的在寫入時複製 (或) 會移除，延伸點會取消整合，然後再重新整合。 請審查在登錄中註冊的一些位置，以檢查其資料放置位置。 這項作業會自動完成，除了從 App-V 用戶端主控台或 PowerShell (Repair-AppVClientPackage) 啟動修復作業外，沒有任何系統管理) 。

## <a name="integration-of-app-v-packages"></a><a href="" id="bkmk-integr-appv-pkgs"></a>整合 App-V 套件


App-V 用戶端和套件架構在新增和發佈套件期間提供與本地作業系統的特定整合。 三個檔案定義 App-V 套件的整合或擴充點：

-   AppXManifest.xml：儲存在套件內，並儲存于套件存放區與使用者設定檔中的備份複本。 包含排序程式期間建立的選項。

-   DeploymentConfig.xml：提供電腦和使用者整合擴充點的組組資訊。

-   UserConfig.xml：僅提供使用者Deploymentconfig.xml且只以使用者為基礎的擴充點為目標之集合。

### <a name="rules-of-integration"></a>整合規則

當 App-V 應用程式發佈至具有 App-V Client 的電腦時，會執行一些特定動作，如下列清單所述：

-   全域發佈：快速鍵會儲存在所有使用者設定檔位置，而其他擴充點則儲存在 HKLM 配置區登錄中。

-   使用者發佈：快速鍵會儲存在目前的使用者帳戶設定檔中，其他擴充點則儲存在 HKCU 配置區中的登錄中。

-   備份與還原：現有的原生應用程式資料和登錄 (例如 FTA 註冊) 發佈期間會備份。

    1.  App-V 套件會根據最後一個整合套件獲得擁有權，而該套件的擁有權會傳遞至最新發佈的 App-V 應用程式。

    2.  當擁有 App-V 套件未發佈時，擁有權會從一個 App-V 套件移轉到另一個套件。 這不會啟動資料或註冊表的還原。

    3.  當最後一個套件未發佈或以每個擴充點為基礎移除時，還原備份的資料。

### <a name="extension-points"></a>延伸點

App-V 發佈檔案 (和動態) 提供數個擴充點，可讓應用程式與本地作業系統整合。 這些擴充點會執行一般應用程式安裝工作，例如放置快捷方式、建立檔案類型關聯，以及註冊元件。 由於這些虛擬化應用程式與傳統應用程式安裝的方式不同，因此有一些差異。 以下是本節涵蓋的擴充點清單：

-   快捷方式

-   檔案類型關聯

-   Shell 擴充功能

-   COM

-   軟體用戶端

-   應用程式功能

-   URL 通訊協定處理常式

-   AppPath

-   虛擬應用程式

### <a name="shortcuts"></a>快捷方式

短片是與作業系統整合的基本元素之一，也是使用者直接啟動 App-V 應用程式的介面。 在發佈和取消發佈 App-V 應用程式期間。

從套件清單和動態組塊 XML 檔案，特定應用程式可執行檔的路徑可在類似下列章節找到：

```xml
<Extension Category="AppV.Shortcut">
          <Shortcut>
            <File>[{Common Desktop}]\Adobe Reader 9.lnk</File>
            <Target>[{AppVPackageRoot}]\Reader\AcroRd32.exe</Target>
            <Icon>[{Windows}]\Installer\{AC76BA86-7AD7-1033-7B44-A94000000001}\SC_Reader.ico</Icon>
            <Arguments />
            <WorkingDirectory />
            <ShowCommand>1</ShowCommand>
            <ApplicationId>[{AppVPackageRoot}]\Reader\AcroRd32.exe</ApplicationId>
          </Shortcut>
        </Extension>
```

如先前所述，App-V 快速鍵預設會根據重新更新作業，置於使用者的設定檔中。 全域重新處理會將快捷方式放在所有使用者設定檔中，而使用者重新更新會將它們儲存在特定使用者的設定檔中。 實際的可執行檔會儲存在套件市中。 ICO 檔案的位置是 App-V 套件中的權杖化位置。

### <a name="file-type-associations"></a>檔案類型關聯

App-V 用戶端可在發佈期間管理本地作業系統檔案類型關聯，讓使用者使用檔案類型的調用，或開啟具有特定註冊副檔名的檔案 (.docx) 以啟動 App-V 應用程式。 檔案類型關聯存在於清單和動態組組檔案中，如下列範例所示：

```xml
<Extension Category="AppV.FileTypeAssociation">
          <FileTypeAssociation>
            <FileExtension MimeAssociation="true">
              <Name>.xdp</Name>
              <ProgId>AcroExch.XDPDoc</ProgId>
              <ContentType>application/vnd.adobe.xdp+xml</ContentType>
            </FileExtension>
            <ProgId>
              <Name>AcroExch.XDPDoc</Name>
              <Description>Adobe Acrobat XML Data Package File</Description>
              <EditFlags>65536</EditFlags>
              <DefaultIcon>[{Windows}]\Installer\{AC76BA86-7AD7-1033-7B44-A94000000001}\XDPFile_8.ico</DefaultIcon>
              <ShellCommands>
                <DefaultCommand>Read</DefaultCommand>
                <ShellCommand>
                  <ApplicationId>[{AppVPackageRoot}]\Reader\AcroRd32.exe</ApplicationId>
                  <Name>Open</Name>
                  <CommandLine>"[{AppVPackageRoot}]\Reader\AcroRd32.exe" "%1"</CommandLine>
                </ShellCommand>
                <ShellCommand>
                  <ApplicationId>[{AppVPackageRoot}]\Reader\AcroRd32.exe</ApplicationId>
                  <Name>Printto</Name>
                  <CommandLine>"[{AppVPackageRoot}]\Reader\AcroRd32.exe"  /t "%1" "%2" "%3" "%4"</CommandLine>
                </ShellCommand>
                <ShellCommand>
                  <ApplicationId>[{AppVPackageRoot}]\Reader\AcroRd32.exe</ApplicationId>
                  <Name>Read</Name>
                  <FriendlyName>Open with Adobe Reader 9</FriendlyName>
                  <CommandLine>"[{AppVPackageRoot}]\Reader\AcroRd32.exe" "%1"</CommandLine>
                </ShellCommand>
              </ShellCommands>
            </ProgId>
          </FileTypeAssociation>
        </Extension>
```

**注意**  
在此範例中：

-   `<Name>.xdp</Name>` 是擴充功能

-   `<Name>AcroExch.XDPDoc</Name>` 是 ProgId 值 (指向連續的 ProgId) 

-   `<CommandLine>"[{AppVPackageRoot}]\Reader\AcroRd32.exe" "%1"</CommandLine>` 是命令列，指向應用程式可執行檔

 

### <a name="shell-extensions"></a>殼層延伸

在排序程式期間，Shell 延伸模組會自動內嵌于套件中。 當套件全域發佈時，shell 擴充功能會提供使用者與安裝應用程式時相同的功能。 應用程式不需要在用戶端上進行額外的設定或設定，以啟用 shell 擴充功能。

**使用 shell 擴充功能的需求：**

-   包含內嵌 shell 擴充模組的套件必須全域發佈。

-   應用程式、Sequencer 和 App-V 用戶端的「位度」必須相符，否則 shell 擴充功能無法工作。 例如：

    -   應用程式版本為 64 位。

    -   順序器在 64 位電腦上執行。

    -   此套件正在傳送到 64 位 App-V 用戶端電腦。

下表顯示支援的 shell 擴充功能。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">處理器</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>操作功能表處理常式</p></td>
<td align="left"><p>新增功能表項目至操作功能表。 在操作功能表顯示之前，會先進行調用。</p></td>
</tr>
<tr class="even">
<td align="left"><p>拖放處理常式</p></td>
<td align="left"><p>以滑鼠右鍵按一下拖放時控制動作，並修改出現的操作功能表。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>放置目標處理常式</p></td>
<td align="left"><p>控制資料物件在拖放到放置目標後的動作，例如檔案。</p></td>
</tr>
<tr class="even">
<td align="left"><p>資料物件處理常式</p></td>
<td align="left"><p>控制將檔案複製到剪貼簿或拖放到下拉目標後的動作。 它可以為下拉目標提供額外的剪貼簿格式。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>屬性工作表處理常式</p></td>
<td align="left"><p>取代或新增頁面至物件的屬性工作表對話方塊。</p></td>
</tr>
<tr class="even">
<td align="left"><p>資訊提示處理常式</p></td>
<td align="left"><p>允許在滑鼠游標移動時，在快顯視窗工具提示中，取回專案的標誌和資訊提示資訊。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>欄處理常式</p></td>
<td align="left"><p>允許在瀏覽器詳細資料檢視中建立Windows <em> 顯示自訂欄 </em> 。 它可以用來延伸排序和群組。</p></td>
</tr>
<tr class="even">
<td align="left"><p>預覽處理常式</p></td>
<td align="left"><p>啟用檔案預覽，以在檔案檔案的檔案預覽窗格中Windows檔案。</p></td>
</tr>
</tbody>
</table>

 

### <a name="com"></a>COM

App-V 用戶端支援發佈應用程式，支援 COM 整合和虛擬化。 COM 整合可讓 App-V Client 在本地作業系統和物件的虛擬化上註冊 COM 物件。 為了本檔的目的，整合 COM 物件需要額外的詳細資料。

App-V 支援使用兩種程式類型將 COM 物件從套件註冊到本地作業系統：非程式處理和程式內。 註冊 COM 物件時，會針對特定 App-V 套件完成一種或多個作業模式組合，包括關閉、隔離和整合。 整合模式是針對程式外或程式內類型所配置。 COM 模式和類型的組態是使用動態組態 (deploymentconfig.xml或userconfig.xml) 。

有關 App-V 整合的詳細資訊，請參閱： <https://go.microsoft.com/fwlink/?LinkId=392834> 。

### <a name="software-clients-and-application-capabilities"></a>軟體用戶端和應用程式功能

App-V 支援特定的軟體用戶端和應用程式功能擴充點，可讓虛擬應用程式向作業系統的軟體用戶端註冊。 這可讓使用者為電子郵件、立即訊息和媒體播放程式等作業選取預設程式。 此作業是在具有設定程式存取和電腦預設值的控制台中執行，且是在順序排序時，在清單或動態組設定檔中設定。 只有在 App-V 應用程式全域發佈時，才支援應用程式功能。

App-V 型郵件用戶端的軟體用戶端註冊範例。

```xml
    <SoftwareClients Enabled="true">
      <ClientConfiguration EmailEnabled="true" />
      <Extensions>
        <Extension Category="AppV.SoftwareClient">
          <SoftwareClients>
            <EMail MakeDefault="true">
              <Name>Mozilla Thunderbird</Name>
              <Description>Mozilla Thunderbird</Description>
              <DefaultIcon>[{ProgramFilesX86}]\Mozilla Thunderbird\thunderbird.exe,0</DefaultIcon>
              <InstallationInformation>
                <RegistrationCommands>
                  <Reinstall>"[{ProgramFilesX86}]\Mozilla Thunderbird\uninstall\helper.exe" /SetAsDefaultAppGlobal</Reinstall>
                  <HideIcons>"[{ProgramFilesX86}]\Mozilla Thunderbird\uninstall\helper.exe" /HideShortcuts</HideIcons>
                  <ShowIcons>"[{ProgramFilesX86}]\Mozilla Thunderbird\uninstall\helper.exe" /ShowShortcuts</ShowIcons>
                </RegistrationCommands>
                <IconsVisible>1</IconsVisible>
                <OEMSettings />
              </InstallationInformation>
              <ShellCommands>
                <ApplicationId>[{ProgramFilesX86}]\Mozilla Thunderbird\thunderbird.exe</ApplicationId>
                <Open>"[{ProgramFilesX86}]\Mozilla Thunderbird\thunderbird.exe" -mail</Open>
              </ShellCommands>
              <MAPILibrary>[{ProgramFilesX86}]\Mozilla Thunderbird\mozMapi32_InUse.dll</MAPILibrary>
              <MailToProtocol>
                <Description>Thunderbird URL</Description>
                <EditFlags>2</EditFlags>
                <DefaultIcon>[{ProgramFilesX86}]\Mozilla Thunderbird\thunderbird.exe,0</DefaultIcon>
                <ShellCommands>
                  <ApplicationId>[{ProgramFilesX86}]\Mozilla Thunderbird\thunderbird.exe</ApplicationId>
                  <Open>"[{ProgramFilesX86}]\Mozilla Thunderbird\thunderbird.exe" -osint -compose "%1"</Open>
                </ShellCommands>
              </MailToProtocol>
            </EMail>
          </SoftwareClients>
        </Extension>
      </Extensions>
    </SoftwareClients>
```

**注意**  
在此範例中：

-   `<ClientConfiguration EmailEnabled="true" />` 是整合電子郵件用戶端的整體軟體用戶端設定

-   `<EMail MakeDefault="true">` 是將特定電子郵件用戶端設為預設電子郵件用戶端的標誌

-   `<MAPILibrary>[{ProgramFilesX86}]\Mozilla Thunderbird\mozMapi32_InUse.dll</MAPILibrary>` 是 MAPI dll 註冊

 

### <a name="url-protocol-handler"></a>URL 通訊協定處理常式

應用程式不一定一定特別稱為使用檔案類型的虛擬應用程式。 例如，在支援內嵌 mailto：檔或網頁內連結的應用程式中，使用者按一下 mailto：連結，並預期會取得其註冊的郵件用戶端。 App-V 支援 URL 通訊協定處理常式，可在每個套件上向本地作業系統註冊。 在排序期間，URL 通訊協定處理常式會自動新加到套件中。

如果可以註冊特定 URL 通訊協定處理常式的應用程式超過一個，可以使用動態組組檔案來修改行為，並隱藏或停用不應啟動主應用程式之應用程式的這項功能。

### <a name="apppath"></a>AppPath

AppPath 擴充點支援直接從作業系統撥打 App-V 應用程式。 這通常是從執行或開始畫面完成，視作業系統而不同，可讓系統管理員從作業系統命令或腳本提供 App-V 應用程式的存取權，而不需要呼叫可執行檔的特定路徑。 因此，它可避免修改所有系統上的系統路徑環境變數，因為此變數是在發佈期間完成的。

AppPath 擴充點是在清單或動態組態檔案中，在使用者發佈期間，會儲存在本機電腦登錄中。 有關 AppPath 評論的其他資訊 <https://go.microsoft.com/fwlink/?LinkId=392835> ：。

### <a name="virtual-application"></a>虛擬應用程式

此子系統提供在排序期間所捕獲的應用程式清單，這些應用程式通常會由其他 App-V 元件使用。 您可以使用動態組組檔案來停用屬於特定應用程式的擴充點整合。 例如，如果套件包含兩個應用程式，可以停用屬於一個應用程式的所有擴充點，以便只允許整合其他應用程式的擴充點。

### <a name="extension-point-rules"></a>擴充點規則

上述擴充點會根據套件的發佈方式，整合至作業系統。 全域發佈在公用電腦位置中會提供擴充點，使用者發佈會將擴充點位於使用者位置。 例如，在桌面建立並全域發佈的快捷方式，會導致快捷方式 (%Public%\\\Desktop) 和註冊表資料 (HKLM\\Software\\Classes) 的檔案資料。 相同的快速鍵會包含檔案資料 (%UserProfile%\\\Desktop) 及登錄資料 (HKCU\\Software\\Classes) 。

擴充點並非全部都是以相同的方式發佈，其中某些擴充點需要全域發佈，而其他擴充點則需要在提供擴充點的特定作業系統和架構上進行順序排序。 下表說明這兩項關鍵規則。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">虛擬擴充功能</th>
<th align="left">需要目標作業系統排序</th>
<th align="left">需要全域發佈</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>快捷方式</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>檔案類型關聯</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>URL 通訊協定</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>AppPaths</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>COM 模式</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>軟體用戶端</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>應用程式功能</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p>X</p></td>
</tr>
<tr class="even">
<td align="left"><p>操作功能表處理常式</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p>X</p></td>
</tr>
<tr class="odd">
<td align="left"><p>拖放處理常式</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>Data Object 處理常式</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>屬性工作表處理常式</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>資訊提示處理常式</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>欄處理常式</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>Shell 擴充功能</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>瀏覽器說明程式物件</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p>X</p></td>
</tr>
<tr class="even">
<td align="left"><p>活動 X 物件</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p>X</p></td>
</tr>
</tbody>
</table>

 

## <a name="dynamic-configuration-processing"></a><a href="" id="bkmk-dynamic-config"></a>動態組組處理


將 App-V 套件部署到一部電腦或使用者非常簡單。 不過，當組織跨業務線及地理與政治邊界部署 AppV 應用程式時，使用一組設定一次排序應用程式的能力變得不可能。 App-V 是專為此案例所設計，因為它在清單檔案的排序期間會捕獲特定設定和設定，但也支援使用動態組設定檔案進行修改。

App-V 動態組式配置可讓您在電腦層級或使用者層級指定套件的策略。 動態組式檔案可讓排序工程師修改套件的組式、排序後，以滿足個別使用者或機器群組的需求。 在某些情況下，可能需要修改應用程式，在 App-V 環境中提供適當的功能。 例如，可能需要對 \_\*config.xml 檔案進行修改，以允許在應用程式執行期間指定時間執行特定動作，例如停用 mailto 擴充功能，以防止虛擬化應用程式覆寫另一個應用程式延伸模組。

App-V 套件包含 Appv 套件檔案內的清單檔案，代表排序作業，且是選擇的政策，除非將 Dynamic Configuration 檔案指派給特定套件。 在順序之後，動態組式檔案可以修改，以允許將應用程式發佈至不同的桌面或具有不同擴充點的使用者。 兩個動態組組檔案是 DDC (部署組) 和 DYNAMIC User Configuration (DUC) 檔案。 本節著重說明清單和動態組組檔案的組合。

### <a name="example-for-dynamic-configuration-files"></a>動態組組檔案範例

下列範例顯示發佈後及一般作業期間清單、部署組態和使用者組態檔案的組合。 這些範例是每個檔案的縮寫範例。 目的只會顯示檔案的組合，而不是每個檔案中可用之特定類別的完整描述。 詳細資訊請參閱 App-V 5 排序指南：： <https://go.microsoft.com/fwlink/?LinkID=269810>

**清單**

```xml
<appv:Extension Category="AppV.Shortcut">
     <appv:Shortcut>
          <appv:File>[{Common Programs}]\7-Zip\7-Zip File Manager.lnk</appv:File>
          <appv:Target>[{AppVPackageRoot}]\7zFM.exe</appv:Target>
          <appv:Icon>[{AppVPackageRoot}]\7zFM exe.O.ico</appv:Icon>
     </appv:Shortcut>
</appv:Extension>
```

**部署組**

```xml
<MachineConfiguration>
     <Subsystems>
          <Registry>
               <Include>
                    <Key Path= "\REGISTRY\Machine\Software\7zip">
                    <Value Type="REG_SZ" Name="Config" Data="1234"/>
                    </Key>
               </Include>
          </Registry>
     </Subsystems>
```

**使用者組組**

```xml
<UserConfiguration>
     <Subsystems>
<appv:ExtensionCategory="AppV.Shortcut">
     <appv:Shortcut>
          <appv:File>[{Desktop}]\7-Zip\7-Zip File Manager.lnk</appv:File>
          <appv:Target>[{AppVPackageRoot}]\7zFM.exe</appv:Target>
          <appv:Icon>[{AppVPackageRoot}]\7zFM exe.O.ico</appv:Icon>
     </appv:Shortcut>
</appv:Extension>
     </Subsystems>
<UserConfiguration>
     <Subsystems>
<appv:Extension Category="AppV.Shortcut">
     <appv:Shortcut>
          <appv:Fìle>[{Desktop}]\7-Zip\7-Zip File Manager.lnk</appv:File>
          <appv:Target>[{AppVPackageRoot}]\7zFM.exe</appv:Target>
          <appv:Icon>[{AppVPackageRoot}]\7zFM.exe.O.ico</appv:Icon>
     </appv:Shortcut>
     <appv:Shortcut>
          <appv:File>[{Common Programs}]\7-Zip\7-Zip File Manager.Ink</appv:File>
          <appv:Target>[{AppVPackageRoot}]\7zFM.exe</appv:Target>
          <appv:Icon>[{AppVPackageRoot)]\7zFM.exe.O.ico</appv: Icon>
     </appv:Shortcut>
</appv:Extension>
     </Subsystems>
<MachineConfiguration>
     <Subsystems>
          <Registry>
               <Include>
                    <Key Path="\REGISTRY\Machine\Software\7zip">
                    <Value Type=”REG_SZ" Name="Config" Data="1234"/>
               </Include>
          </Registry>
     </Subsystems>
```

## <a name="side-by-side-assemblies"></a><a href="" id="bkmk-sidebyside-assemblies"></a>並排元件


App-V 支援在虛擬應用程式發佈期間 (用戶端上的排序) 並排封裝 SxS 和元件。 App-V 5 SP2 支援在排序過程中捕獲 SxS 程式集，以在排序電腦上不存在的程式集。 對於包含 Visual C++ (版本 8 及更新版本) 和/或 MSXML 執行時間的程式集，即使監控期間未安裝這些相依性，序列器也會自動偵測並捕獲這些相依性。 並排元件功能會移除先前 App-V 版本的限制，其中 App-V 序列器並未捕獲序列工作站上已存在的程式集，並將每個套件的程式集限制為一位版本。 此行為導致將 App-V 應用程式部署到用戶端時遺失所需的 SxS 程式集，導致應用程式啟動失敗。 這強制封裝程式進行檔化，然後確保套件所需的所有程式集都安裝在使用者的用戶端作業系統上，以確保虛擬應用程式的支援。 根據程式集數量，以及缺少所需相依性的應用程式檔，這項工作是一項管理和執行挑戰。

App-V 中的並排程式集支援具有下列功能。

-   在排序期間自動捕獲 SxS 元件，無論該元件是否已安裝在排序工作站上。

-   App-V 用戶端會在沒有 SxS 程式集時，在發佈時自動將所需的 SxS 程式集安裝至用戶端電腦。

-   順序器會報告 Sequencer 報告機制中的VC 運行時相依性。

-   順序器允許選擇不封裝已在序列器上安裝的程式集，支援先前已在目的電腦上安裝程式集的情況。

### <a name="automatic-publishing-of-sxs-assemblies"></a>自動發佈 SxS 程式集

在發佈具有 SxS 程式集的 App-V 套件時，App-V 用戶端會檢查該程式集是否位於電腦上。 如果程式集不存在，用戶端就會將程式集部署到電腦。 屬於連接群組的套件會仰賴基礎套件的並排元件安裝，因為連接群組不包含任何有關元件安裝的資訊。

**注意**  
使用元件取消發佈或移除套件不會移除該套件的程式集。

 

## <a name="client-logging"></a><a href="" id="bkmk-client-logging"></a>用戶端記錄


App-V 用戶端會以標準 ETW 格式Windows事件記錄記錄資訊。 特定 App-V 事件可在活動檢視器的應用程式和服務記錄\\\Microsoft\\AppV\\Client 下找到。

**注意**  
在 App-V 5.0 SP3 中，某些記錄已合併並移至下列位置：

`Event logs/Applications and Services Logs/Microsoft/AppV/ServiceLog`

有關移動記錄的清單，請參閱 [關於 App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-event-logs-moved)。

 

有三種特定類別的事件記錄如下所述。

**系統管理員**：記錄要適用于 App-V 用戶端之配置的事件，並包含主要警告和錯誤。

**營運**：記錄個別元件的一般 App-V 執行及使用狀況，以建立 App-V 用戶端上已完成之 App-V 作業的稽核記錄。

**虛擬應用程式**：記錄虛擬應用程式的啟動及虛擬化子系統的使用。






 

 





