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
ms.openlocfilehash: 69fcf119faaf35e53ae36f386bcb3480e2ee3b0e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800667"
---
# 應用程式發佈與用戶端互動


本文提供有關常見 App V 用戶端作業及其與本機作業系統整合的技術資訊。

-   [排序器所建立的 app-v 封裝檔案](#bkmk-appv-pkg-files-list)

-   [Appv 檔案中有什麼？](#bkmk-appv-file-contents)

-   [App-V 用戶端資料儲存位置](#bkmk-files-data-storage)

-   [套件註冊](#bkmk-pkg-registry)

-   [App-v 套件儲存行為](#bkmk-pkg-store-behavior)

-   [漫遊登錄與資料](#bkmk-roaming-reg-data)

-   [App-V 用戶端應用程式週期管理](#bkmk-clt-app-lifecycle)

-   [集成 App-v 套件](#bkmk-integr-appv-pkgs)

-   [動態配置處理](#bkmk-dynamic-config)

-   [並列元件](#bkmk-sidebyside-assemblies)

-   [用戶端記錄](#bkmk-client-logging)

如需其他參考資訊，請參閱[Microsoft 應用程式虛擬化（app-v）檔資源下載頁面](https://www.microsoft.com/download/details.aspx?id=27760)。

## <a href="" id="bkmk-appv-pkg-files-list"></a>排序器所建立的 app-v 封裝檔案


排序器會建立 App-v 套件並產生虛擬化的應用程式。 排序過程會建立下列檔案：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">檔案</th>
<th align="left">說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>appv</p></td>
<td align="left"><ul>
<li><p>主要套件檔案，其中包含從排序處理常式中捕獲的資產和狀態資訊。</p></li>
<li><p>封裝形式的套件檔案、發佈資訊和註冊表的架構，可以在傳送時，將它重新套用到電腦和特定使用者。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>..MSI</p></td>
<td align="left"><p>您可以用來手動部署 appv 檔案或使用協力廠商部署平臺的可執行部署包裝程式。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>_DeploymentConfig.XML</p></td>
<td align="left"><p>此檔案可供您自訂套件中所有應用程式的預設發佈參數，這些元件會全域部署到執行 App-v 用戶端的電腦上的所有使用者。</p></td>
</tr>
<tr class="even">
<td align="left"><p>_UserConfig.XML</p></td>
<td align="left"><p>此檔案用來針對在執行 App-v 用戶端之電腦上的特定使用者部署之套件中的所有應用程式，自訂發佈參數。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Report.xml</p></td>
<td align="left"><p>排序進程所產生的訊息摘要，包括遺漏的驅動程式、檔案和註冊表位置。</p></td>
</tr>
<tr class="even">
<td align="left"><p>.間</p></td>
<td align="left"><p><em>[選用]： </em> 套件加速器檔案，用來自動重建先前已排序的虛擬應用程式套件。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>.appvt</p></td>
<td align="left"><p><em>選用： </em> sequencer 範本檔案，用來保留常用的 Sequencer 設定。</p></td>
</tr>
</tbody>
</table>

 

如需排序的相關資訊，請參閱[應用程式虛擬化順序指南](https://go.microsoft.com/fwlink/?LinkID=269810)。

## <a href="" id="bkmk-appv-file-contents"></a>Appv 檔案中有什麼？


Appv 檔案是一個容器，可將 XML 和非 XML 檔案儲存在單一實體中。 此檔案是從 AppX 格式所建立，這是以開放式封裝慣例（OPC）標準為基礎。

若要查看 appv 檔案內容，請製作套件複本，然後將複製的檔案重新命名為 ZIP 延伸。

Appv 檔案包含下列資料夾及檔案，這些資料夾和檔案是在建立及發佈虛擬應用程式時使用：

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
<td align="left"><p>包含在排序期間捕獲之虛擬化應用程式之檔案系統的目錄。</p></td>
</tr>
<tr class="even">
<td align="left"><p>[Content_Types] .xml</p></td>
<td align="left"><p>XML 檔案</p></td>
<td align="left"><p>Appv 檔案（例如 DLL、EXE、BIN）中的核心內容類型清單。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AppxBlockMap.xml</p></td>
<td align="left"><p>XML 檔案</p></td>
<td align="left"><p>Appv 檔案的版面配置，該檔案使用檔案、區塊及 BlockMap 元素，可在 App-v 套件中啟用檔案位置及驗證。</p></td>
</tr>
<tr class="even">
<td align="left"><p>AppxManifest.xml</p></td>
<td align="left"><p>XML 檔案</p></td>
<td align="left"><p>套件的中繼資料，其中包含新增、發佈及啟動套件所需的資訊。 包括延伸點（檔案類型關聯和快速鍵），以及與套件關聯的名稱和 Guid。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>FilesystemMetadata.xml</p></td>
<td align="left"><p>XML 檔案</p></td>
<td align="left"><p>在排序期間捕獲的檔案清單，包括屬性（例如目錄、檔案、不透明目錄、空目錄、長名稱和短名稱）。</p></td>
</tr>
<tr class="even">
<td align="left"><p>PackageHistory.xml</p></td>
<td align="left"><p>XML 檔案</p></td>
<td align="left"><p>有關先後順序電腦（作業系統版本、Internet Explorer 版本、.Net Framework 版本）與程式（升級、套件版本）的資訊。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Registry （dat）</p></td>
<td align="left"><p>DAT 檔案</p></td>
<td align="left"><p>在封裝的排序程式期間捕獲的登錄機碼和值。</p></td>
</tr>
<tr class="even">
<td align="left"><p>StreamMap.xml</p></td>
<td align="left"><p>XML 檔案</p></td>
<td align="left"><p>主要和發佈功能區塊的檔案清單。 發佈功能區塊包含用於發佈套件的 .ICO 檔案，以及檔案（EXE 和 DLL）的必要部分。 當簡報時，主要的功能區塊會包含已針對排序程式在進行中進行流式處理的檔案。</p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-files-data-storage"></a>App-V 用戶端資料儲存位置


App-v 用戶端會執行工作，以確保虛擬應用程式正常運作且能正常運作（例如本機安裝的應用程式）。 開啟及執行虛擬應用程式的程式需要從虛擬檔案系統和註冊表進行對應，以確保應用程式具有使用者預期的傳統應用程式所需的元件。 本節將說明執行虛擬應用程式所需的資產，並列出 App V 儲存資產的位置。

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
<td align="left"><p>套件存放區</p></td>
<td align="left"><p>%ProgramData%\App-V</p></td>
<td align="left"><p>唯讀套件檔案的預設位置</p></td>
</tr>
<tr class="even">
<td align="left"><p>電腦目錄</p></td>
<td align="left"><p>%ProgramData%\Microsoft\AppV\Client\Catalog</p></td>
<td align="left"><p>包含每電腦設定檔</p></td>
</tr>
<tr class="odd">
<td align="left"><p>使用者目錄</p></td>
<td align="left"><p>%AppData%\Microsoft\AppV\Client\Catalog</p></td>
<td align="left"><p>包含每個使用者的設定檔</p></td>
</tr>
<tr class="even">
<td align="left"><p>快捷方式備份</p></td>
<td align="left"><p>%AppData%\Microsoft\AppV\Client\Integration\ShortCutBackups</p></td>
<td align="left"><p>儲存先前的整合點，以便在套件取消發佈時啟用還原</p></td>
</tr>
<tr class="odd">
<td align="left"><p>寫入時複製（牛）漫遊</p></td>
<td align="left"><p>%AppData%\Microsoft\AppV\Client\VFS</p></td>
<td align="left"><p>套件修改的可寫入漫遊位置</p></td>
</tr>
<tr class="even">
<td align="left"><p>寫入時複製（牛）本機</p></td>
<td align="left"><p>%LocalAppData%\Microsoft\AppV\Client\VFS</p></td>
<td align="left"><p>適用于套件修改的可寫入非漫遊位置</p></td>
</tr>
<tr class="odd">
<td align="left"><p>電腦註冊表</p></td>
<td align="left"><p>HKLM\Software\Microsoft\AppV</p></td>
<td align="left"><p>包含套件狀態資訊，包括電腦或全域發佈套件（電腦配置單元）的 VReg</p></td>
</tr>
<tr class="even">
<td align="left"><p>使用者註冊表</p></td>
<td align="left"><p>HKCU\Software\Microsoft\AppV</p></td>
<td align="left"><p>包含使用者套件狀態資訊，包括 VReg</p></td>
</tr>
<tr class="odd">
<td align="left"><p>使用者註冊類別</p></td>
<td align="left"><p>HKCU\Software\Classes\AppV</p></td>
<td align="left"><p>包含其他使用者套件狀態資訊</p></td>
</tr>
</tbody>
</table>

 

表格的其他詳細資料會在下一節和整份檔中提供。

### 套件存放區

App-V 用戶端會管理套件存放區中裝載的應用程式資產。 這個預設儲存位置是 `%ProgramData%\App-V` ，但您可以使用 PowerShell 命令在安裝期間或之後進行設定 `Set-AppVClientConfiguration` ，這會修改本機登錄（ `PackageInstallationRoot` 在金鑰底下的值 `HKLM\Software\Microsoft\AppV\Client\Streaming` ）。 套件存放區必須位於用戶端作業系統上的本機路徑中。 個別套件會儲存在套件 GUID 與版本 GUID 命名的子目錄中。

特定應用程式路徑範例：

``` syntax
C:\ProgramData\App-V\PackGUID\VersionGUID
```

若要在安裝期間變更套件存放區的預設位置，請參閱[如何部署 App-v 用戶端](how-to-deploy-the-app-v-client-51gb18030.md)。

### 共用內容存放區

如果 App-v 用戶端是在 [共用內容存放區] 模式中設定，則當出現資料流程錯誤時，就不會將資料寫入磁片，這表示套件需要最少的本機磁碟空間（發佈資料）。 在 VDI 環境中使用較少的磁碟空間非常可取，在這種情況下，可以限制本機儲存空間，並以高效能網路位置（例如 SAN）來流式處理應用程式。 如需共用內容存放區模式的詳細資訊，請參閱 <https://go.microsoft.com/fwlink/p/?LinkId=392750> 。

**記事** 即使您使用的是 App-v 用戶端的共用內容存放區設定，電腦和套件存放區也必須位於本機磁片磁碟機上。

 

### 套件目錄

App-v 用戶端會管理下列兩個以檔案為基礎的位置：

-   **[編目] （使用者與電腦）。**

-   登錄**位置**-視套件的目標發佈方式而定。 該電腦有一個 [目錄（資料儲存區）]，以及每個個別使用者的目錄。 電腦目錄會儲存適用于所有使用者或任何使用者的全域資訊，而使用者目錄會儲存適用于特定使用者的資訊。 目錄是動態配置和資訊清單檔案的集合;每個套件版本的檔案和註冊表都有離散資料。 

### 電腦目錄

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>說明</p></td>
<td align="left"><p>在新增及發佈套件時，儲存可供電腦使用者使用的套件檔。 不過，如果在發佈時套件是「全域」，則所有使用者都能使用這些整合。</p>
<p>如果套件是非全域的，則只會針對特定使用者發佈整合，但用戶端電腦上的任何人都已修改且可見的全域資源（例如，套件目錄位於共用磁片位置）。</p>
<p>如果電腦上的使用者可以使用套件（全域或非全域），資訊清單就會儲存在電腦目錄中。 當套件是全域發佈時，就會有一個動態設定檔案，儲存在電腦目錄中;因此，根據電腦目錄中是否有原則檔案（UserDeploymentConfiguration 檔案），決定是否為全域套件。</p></td>
</tr>
<tr class="even">
<td align="left"><p>預設儲存位置</p></td>
<td align="left"><p><code>%programdata%\Microsoft\AppV\Client\Catalog&lt;/code&gt;</p>
<p>這個位置與套件儲存位置不同。 套件存放區是套件檔案的黃金或 pristine 複本。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>電腦目錄中的檔案</p></td>
<td align="left"><ul>
<li><p>Manifest.xml</p></li>
<li><p>DeploymentConfiguration.xml</p></li>
<li><p>UserManifest.xml （全域發佈的套件）</p></li>
<li><p>UserDeploymentConfiguration.xml （全域發佈的套件）</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>其他電腦目錄位置，在套件是連線群組的一部分時使用</p></td>
<td align="left"><p>下列位置除了上述所述的特定套件位置之外：</p>
<p><code>%programdata%\Microsoft\AppV\Client\Catalog\PackageGroups\ConGroupGUID\ConGroupVerGUID</code></p></td>
</tr>
<tr class="odd">
<td align="left"><p>當套件是連線群組的一部分時，電腦目錄中的其他檔案</p></td>
<td align="left"><ul>
<li><p>PackageGroupDescriptor.xml</p></li>
<li><p>UserPackageGroupDescriptor.xml （全域發佈的連線群組）</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

### 使用者目錄

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>說明</p></td>
<td align="left"><p>在發佈程式期間建立。 包含發佈套件所用的資訊，也可在啟動時使用，以確保將套件提供給特定的使用者。 在漫遊位置建立，並包含使用者專用的發佈資訊。</p>
<p>當您為使用者發佈套件時，原則檔案會儲存在使用者目錄中。 同時，也會將資訊清單複本儲存在使用者目錄中。 當使用者移除套件權利時，相關的套件檔案就會從使用者目錄中移除。 在查看使用者目錄時，系統管理員可以查看動態設定檔案是否存在，這表示該套件適用于該使用者。</p>
<p>針對漫遊使用者，使用者目錄必須位於漫遊或共用位置，才能預設保留目標使用者的舊版 App-v 行為。 權利與原則會與使用者（而非電腦）相關聯，所以在使用者提供之後，就應該與使用者一起漫遊。</p></td>
</tr>
<tr class="even">
<td align="left"><p>預設儲存位置</p></td>
<td align="left"><p><code>appdata\roaming\Microsoft\AppV\Client\Catalog\Packages\PkgGUID\VerGUID</code></p></td>
</tr>
<tr class="odd">
<td align="left"><p>使用者目錄中的檔案</p></td>
<td align="left"><ul>
<li><p>UserManifest.xml</p></li>
<li><p>DynamicConfiguration.xml 或 UserDeploymentConfiguration.xml</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>其他使用者目錄位置，在套件是連線群組的一部分時使用</p></td>
<td align="left"><p>下列位置除了上述所述的特定套件位置之外：</p>
<p><code>appdata\roaming\Microsoft\AppV\Client\Catalog\PackageGroups\PkgGroupGUID\PkgGroupVerGUID</code></p></td>
</tr>
<tr class="odd">
<td align="left"><p>當套件是連線群組的一部分時，電腦目錄中的其他檔案</p></td>
<td align="left"><p><code>UserPackageGroupDescriptor.xml</code></p></td>
</tr>
</tbody>
</table>

 

### 快捷方式備份

在發佈程式期間，App-V 用戶端會備份任何快速鍵及整合點至 `%AppData%\Microsoft\AppV\Client\Integration\ShortCutBackups.` 此備份，在未發佈套件時，可將這些整合點還原到先前的版本。

### 在寫入檔案時複製

套件存放區包含已從發佈伺服器傳送資料流程的套件檔案 pristine 複本。 在 App-V 應用程式的正常運作期間，使用者或服務可能需要變更檔案。 在套件存放區中不會進行這些變更，以保留您修復應用程式的能力，這會移除這些變更。 這些位置稱為 [寫入時複製（牛）]，支援漫遊和非漫遊位置。 儲存修改的位置，取決於應用程式在原生體驗中編寫變更的程式。

### 牛漫遊

上面所述的 [牛漫遊位置] 會儲存針對典型% AppData% location 或 \\Users\\{username}\\AppData\\Roaming 位置的檔案和目錄所做的變更。 然後，這些目錄和檔案會根據作業系統設定進行漫遊。

### 牛 [本機]

[牛本機位置] 與漫遊位置類似，但目錄和檔案不會漫遊至其他電腦，即使已設定漫遊支援也一樣。 上述的 [牛本機位置] 會儲存適用于一般視窗而不是% AppData% 位置的變更。 列出的目錄會有差異，但在任何典型的 Windows 位置（例如一般 AppData 及常見的 AppDataS），都會有兩個位置。 **S**代表受限制的位置，在虛擬服務要求使用者從已登入的使用者進行變更時，會以不同的許可權傳送給使用者。 非**S**位置會儲存以使用者為基礎的變更。

## <a href="" id="bkmk-pkg-registry"></a>套件註冊


應用程式必須先將套件註冊資料提供給應用程式，才能讓應用程式存取套件註冊資料。 App-v 用戶端會針對所有登錄資料使用真實的登錄作為後備存放區。

將新的套件新增到 App-v 用戶端時，就是一份複本。已建立來自套件的 DAT 檔案 `%ProgramData%\Microsoft\AppV\Client\VREG\{Version GUID}.dat` 。 檔案的名稱是版本 GUID，且副檔名為。DAT 延伸。 這份製作的原因是要確保套件中的實際設定檔檔案永遠不會被使用，從而避免日後移除套件。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>[套件存放區] 的 [Registry] （dat）</strong></p></td>
<td align="left"><p><strong> &gt; </strong></p></td>
<td align="left"><p><strong>%ProgramData%\Microsoft\AppV\Client\Vreg {VersionGuid} .dat</strong></p></td>
</tr>
</tbody>
</table>

 

當在用戶端上啟動套件中的第一個應用程式時，用戶端階段或將內容複寫到 hive 檔案中，在備用位置重新建立套件註冊資料 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\AppV\Client\Packages\PackageGuid\Versions\VersionGuid\REGISTRY` 。 分段登錄資料有兩種不同類型的電腦資料和使用者資料。 機器資料會在電腦上的所有使用者之間共用。 針對每位使用者將使用者資料轉移至 userspecific 位置 `HKCU\Software\Microsoft\AppV\Client\Packages\PackageGuid\Registry\User` 。 在套件移除時，電腦資料最終會移除，而在使用者取消發佈作業時，就會移除使用者資料。

### 套件註冊暫存與連接群組登錄

當連線群組存在時，前一次暫存登錄的程式會保留為 true，但不會有一個要處理的 hive 檔案。 檔案會按照其在連線群組 XML 中出現的順序進行處理，第一個寫入程式入選任何衝突。

分段式登錄的保持方式與單一套件大小寫中相同。 分段的使用者登錄資料會保留在連線群組中，直到停用為止;在移除連線群組時，會移除分段式電腦登錄資料。

### 虛擬註冊表

虛擬 registry （VREG）的用途是提供單一合併的套件註冊和原生登錄視圖給應用程式。 它也提供寫操作（牛）功能，即從虛擬程式內容對註冊表所做的任何變更，都是在個別的牛位置進行。 這表示 VREG 必須將最多三個不同的登錄位置合併成單一視圖，這是根據在註冊表的 [牛封裝-非本機] 中所填入的位置 &gt; &gt; 。 針對登錄資料進行要求時，系統會依順序找到該資料，直到找到所要求的資料為止。 意義如果在牛位置儲存的值不會繼續進行其他位置，不過，如果您在 [牛位置] 中沒有任何資料，就會繼續進行，直到找到適當的資料為止。

### 登錄位置

應用程式-V 用戶端根據套件是個別發行或連線群組的一部分，有兩個套件登錄位置和兩個連線群組位置。 套件有三個牛位置，而連接群組則是3個，由 VREG 建立及管理。 套件和連線群組的設定不會共用：

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
<li><p>電腦 Registry\Client\Packages\PkgGUID\REGISTRY （只有提升程式可以寫入）</p></li>
<li><p>使用者 Registry\Client\Packages\PkgGUID\REGISTRY （除了 Software\Classes 外，在 HKCU 下寫入的任何內容）</p></li>
<li><p>使用者登錄 Classes\Client\Packages\PkgGUID\REGISTRY （針對非提升程式的 HKCU\Software\Classes 寫入和 HKLM\）</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>套件</strong></p></td>
<td align="left"><ul>
<li><p>電腦 Registry\Client\Packages\PkgGUID\Versions\VerGuid\Registry\Machine</p></li>
<li><p>使用者註冊 Classes\Client\Packages\PkgGUID\Versions\VerGUID\Registry</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><strong>原始</strong></p></td>
<td align="left"><ul>
<li><p>原生應用程式登錄位置</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

 

**連接群組 VReg：**

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
<li><p>電腦 Registry\Client\PackageGroups\GrpGUID\REGISTRY （只有提升程式可以寫入）</p></li>
<li><p>使用者 Registry\Client\PackageGroups\GrpGUID\REGISTRY （除了 Software\Classes 之外，任何已寫入 HKCU 的專案</p></li>
<li><p>使用者註冊 Classes\Client\PackageGroups\GrpGUID\REGISTRY</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>套件</strong></p></td>
<td align="left"><ul>
<li><p>電腦 Registry\Client\PackageGroups\GrpGUID\Versions\VerGUID\REGISTRY</p></li>
<li><p>使用者註冊 Classes\Client\PackageGroups\GrpGUID\Versions\VerGUID\REGISTRY</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><strong>原始</strong></p></td>
<td align="left"><ul>
<li><p>原生應用程式登錄位置</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

 

在 HKLM 中有兩個牛位置;已提升和未提升的程式。 已提升的處理常式永遠會將 HKLM 變更寫入在 HKLM 下的安全牛。 未提升的處理常式在 HKCU\\Software\\Classes. 下，永遠會將 HKLM\ 變更寫入非安全的牛 當應用程式從 HKLM 讀取變更時，提升的進程會從 HKLM 下的安全牛讀取變更。 非升高的讀取，請 favoring 在不安全的牛中進行的變更。

### 傳遞按鍵

[傳遞金鑰] 可讓系統管理員設定某些金鑰，讓其只能從原生登錄讀取，不需要封裝和牛位置。 直通位置是在電腦（而非套裝軟體專用）中全域使用，而且可以透過新增該金鑰的路徑加以設定，而這應該會被視為傳遞到 _MULTI**金鑰的** **_SZ**值 `HKLM\Software\Microsoft\AppV\Subsystem\VirtualRegistry` 。 出現在這個多重字串值（及其子系）底下的任何索引鍵，都會被視為傳遞。

預設會將下列位置設定為傳遞位置：

-   HKEY \ _CURRENT \ _USER \\SOFTWARE\\Classes\\Local Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\AppModel

-   HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Classes\\Local Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\AppModel

-   HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WINEVT

-   HKEY \ _LOCAL \ _MACHINE \\SYSTEM\\CurrentControlSet\\services\\eventlog\\Application

-   HKEY \ _LOCAL \ _MACHINE \\SYSTEM\\CurrentControlSet\\Control\\WMI\\Autologger

-   HKEY \ _CURRENT \ _USER \\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet 設定

-   HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Perflib

-   HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Policies

-   HKEY \ _CURRENT \ _USER \\SOFTWARE\\Policies

傳遞金鑰的目的是確保虛擬應用程式不會在 VReg 中寫入非虛擬應用程式所需的登錄資料，以進行成功的操作或整合。 原則金鑰可確保系統會利用管理員設定的 [群組原則] 設定，而不是 [每個套件] 設定。 需要使用 AppModel 金鑰來與 Windows 新式 UI 應用程式整合。 建議管理不要修改任何預設的傳遞金鑰，但在某些情況下，根據應用程式的行為，可能需要新增額外的傳遞按鍵。

## <a href="" id="bkmk-pkg-store-behavior"></a>App-v 套件儲存行為


App-V 5 管理套件存放區，這是儲存 appv 檔案之擴充資產檔案的位置。 根據預設，此位置會儲存在%ProgramData%\\App-V，而且只會根據可用磁碟空間來限制儲存功能。 套件存放區是按照上一節中提到的封裝與版本的 Guid 來組織。

### 新增套件

使用 App-v 用戶端加入電腦時，會暫存 app-v 套件。 App-v 用戶端提供隨選即用的轉移。 在發佈或手動載入 AppVClientPackage 期間，會在套件存放區（c:\\programdata\\App-V\\{PkgGUID}\\{VerGUID}）中建立資料結構。 在 StreamMap.xml 中定義的發佈區塊中所識別的套件檔案會新增至系統以及暫存頂層資料夾和子檔案，以確保啟動時有適當的應用程式資產。

### 安裝套件

您可以使用 PowerShell 來顯式載入套件， `Mount-AppVClientPackage` 或使用**App-v 用戶端 UI**來下載套件。 這個作業會將整個套件完全載入到套件存放區中。

### 流式套件

App-v 用戶端可以設定為變更資料流程的預設行為。 所有的資料流程原則都儲存在下列登錄機碼下： `HKEY_LOCAL_MAcHINE\Software\Microsoft\AppV\Client\Streaming` 。 原則是使用 PowerShell Cmdlet 來設定 `Set-AppvClientConfiguration` 。 下列原則適用于流式處理：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">原則</th>
<th align="left">說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>AllowHighCostLaunch</p></td>
<td align="left"><p>在 Windows 8 和更新版本中，它可讓您在3G 與行動網路上傳輸</p></td>
</tr>
<tr class="even">
<td align="left"><p>AutoLoad</p></td>
<td align="left"><p>指定背景載入設定：</p>
<p><strong>0 </strong> - 停用</p>
<p><strong>1 </strong> -僅限先前使用的套件</p>
<p><strong>2 </strong> -所有套件</p></td>
</tr>
<tr class="odd">
<td align="left"><p>PackageInstallationRoot</p></td>
<td align="left"><p>本機電腦中套件存放區的根資料夾</p></td>
</tr>
<tr class="even">
<td align="left"><p>PackageSourceRoot</p></td>
<td align="left"><p>應從哪個部分來流式處理套件的根覆寫</p></td>
</tr>
<tr class="odd">
<td align="left"><p>SharedContentStoreMode</p></td>
<td align="left"><p>啟用在 VDI 案例中使用共用內容存放區</p></td>
</tr>
</tbody>
</table>

 

 

這些設定會影響流式處理 app-v 套件資產與用戶端的行為。 根據預設，App-v 只會在下載初始發佈及主要功能區塊之後，下載所需的資產。 流式套件有三個具體的行為，必須加以說明：

-   背景資料流程

-   優化的資料流程

-   資料流程錯誤

### 背景資料流程

您 `Get-AppvClientConfiguration` 可以使用 PowerShell Cmdlet 來判斷背景資料流程使用 AutoLoad 設定的目前模式，並使用 Cmdlet Set-AppvClientConfiguration 或從 registry （HKLM\\SOFTWARE\\Microsoft\\AppV\\ClientStreaming 金鑰）進行修改。 [背景資料流程] 是預設設定，其中 [Autoload] 設定設為 [下載先前使用的套件]。 根據預設設定（值 = 1）的行為會在應用程式啟動後，在背景下載 app-v 資料區塊。 不論是否已啟動，此設定都可以同時停用（值 = 0）或啟用所有套件（值 = 2）。

### 優化的資料流程

在排序期間，您可以使用主要功能區塊來設定 app-v 套件。 這項設定可讓排序工程針對特定應用程式或應用程式監視啟動檔案，並在套件中第一次啟動應用程式時，將 App-v 套件中的資料區塊標示為流式處理。

### 資料流程錯誤

在任何發佈資料和主要功能區塊的初始資料流程之後，需要其他檔案的要求才能執行串流錯誤。 這些資料區塊會根據需要下載到套件存放區。 這可讓使用者只下載套件的一小部分，通常是足以啟動套件並執行一般工作。 當使用者啟動的作業需要目前不在套件存放區中的資料時，就會下載所有其他區塊。

如需 App-V 套件流式處理就診的詳細資訊： <https://go.microsoft.com/fwlink/?LinkId=392770> 。

您可以在以下網址找到流式處理優化的順序： <https://go.microsoft.com/fwlink/?LinkId=392771> 。

### 套件升級

App-v 套件在整個應用程式週期中需要更新。 App-v 套件升級與套件發佈作業類似，因為每個版本都會在自己的 PackageRoot 位置中建立： `%ProgramData%\App-V\{PkgGUID}\{newVerGUID}` 。 升級作業是透過從同一個套件的其他版本建立相同與流式處理檔案的硬連結來優化。

### 套件移除

移除套件時，應用程式 V 用戶端的行為視用於移除的方法而定。 使用 App-v 完整基礎結構來取消發佈應用程式，會移除使用者目錄檔案（全域發佈的應用程式的電腦目錄），但會保留套件儲存位置和牛位置。 使用 PowerShell Cmdlet `Remove-AppVClientPackge` 來移除 App-v 套件時，會清除套件儲存區位置。 請記住，從管理伺服器取消發佈 App-v 套件並不會執行移除作業。 這兩個操作都會移除套件儲存套件檔案。

## <a href="" id="bkmk-roaming-reg-data"></a>漫遊登錄與資料


App-V 5 可以在漫遊時提供近乎原生的體驗，視使用的應用程式的撰寫方式而定。 根據預設，App-v 會根據作業系統的漫遊設定，將儲存在漫遊位置的 AppData 漫遊。 儲存檔案資料的其他位置並不會從電腦漫遊到電腦，因為它們位於不在漫遊的位置。

### <a href="" id="bkmk-clt-inter-roam-reqs"></a>漫遊需求與使用者目錄資料儲存

App-v 會儲存資料，代表使用者的目錄狀態，形式如下：

-   [%Appdata%\\Microsoft\\AppV\\Client\\Catalog] 下的檔案

-   中的 [登錄] 設定 `HKEY_CURRENT_USER\Software\Microsoft\AppV\Client\Packages`

總之，這些檔案和登錄設定代表使用者的目錄，所以兩者都必須是漫遊，或者都不是特定使用者的漫遊。 App-v 不支援漫遊% AppData%，但無法漫遊使用者的設定檔（registry），或相反的情況。

**記事** **AppvClientPackage** Cmdlet 不會修復套件的發佈狀態，即使用者的 app-v 狀態 `HKEY_CURRENT_USER` 缺失或與% appdata% 中的資料不匹配。

 

### 以註冊表為基礎的資料

App-v registry 漫遊分為兩個案例，如下表所示。

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
<td align="left"><p>以標準使用者身分執行的應用程式</p></td>
<td align="left"><p>當標準使用者啟動 App-v 應用程式時，應用程式 V 應用程式的 HKLM\ 和 HKCU 都儲存在電腦上的 HKCU hive 中。 這會顯示為兩個不同的路徑：</p>
<ul>
<li><p>HKLM\： HKCU\SOFTWARE\Classes\AppV\Client\Packages {PkgGUID} \ REGISTRY\MACHINE\SOFTWARE</p></li>
<li><p>HKCU： HKCU\SOFTWARE\Microsoft\AppV\Client\Packages {PkgGUID} \ REGISTRY\USER {UserSID} \ 軟體</p></li>
</ul>
<p>位置會根據作業系統設定而啟用漫遊。</p></td>
</tr>
<tr class="even">
<td align="left"><p>以提升方式執行的應用程式</p></td>
<td align="left"><p>使用仰角啟動應用程式時：</p>
<ul>
<li><p>HKLM 資料儲存在本機電腦上的 HKLM hive 中</p></li>
<li><p>HKCU 資料會儲存在使用者的登錄位置</p></li>
</ul>
<p>在這種情況下，這些設定不是使用標準作業系統漫遊配置進行漫遊，且產生的登錄機碼和值會儲存在下列位置：</p>
<ul>
<li><p>HKLM\SOFTWARE\Microsoft\AppV\Client\Packages{PkgGUID}{UserSID}\REGISTRY\MACHINE\SOFTWARE</p></li>
<li><p>HKCU\SOFTWARE\Microsoft\AppV\Client\Packages {PkgGUID} \ Registry\User {UserSID} \ 軟體</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

### App-v 與資料夾重新導向

App-V 5.1 支援漫遊 AppData 資料夾的資料夾重新導向（% AppData%）。 啟動虛擬環境時，會將來自使用者的漫遊 AppData 目錄的漫遊 AppData 狀態複製到本機快取。 相反地，當虛擬環境關閉時，會將與特定使用者的漫遊 AppData 相關聯的本機快取傳送到該使用者的 [漫遊 AppData] 目錄的實際位置。

典型的封裝會在使用者的後備儲存體中對應數個位置，以取得 AppData\\Local 和 AppData\\Roaming. 中的設定。 這些位置是儲存在使用者設定檔中每位使用者的寫位置上的複本，且用來儲存對套件 VFS 目錄所做的變更，以及保護預設套件 VFS。

下表顯示在尚未實現資料夾重新導向時的本機和漫遊位置。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">套件中的 VFS 目錄</th>
<th align="left">後備存放區的對應位置</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>ProgramFilesX86</p></td>
<td align="left"><p>C:\users\jsmith\AppData &lt; 強勁的 &gt; Local </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \ProgramFilesX86</p></td>
</tr>
<tr class="even">
<td align="left"><p>SystemX86</p></td>
<td align="left"><p>C:\users\jsmith\AppData &lt; 強勁的 &gt; Local </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \SystemX86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows</p></td>
<td align="left"><p>C:\users\jsmith\AppData &lt; 強勁的 &gt; Local </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \windows</p></td>
</tr>
<tr class="even">
<td align="left"><p>appv_ROOT</p></td>
<td align="left"><p>C:\users\jsmith\AppData &lt; 強勁的 &gt; Local </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \ appv_ROOT</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AppData</p></td>
<td align="left"><p>C:\users\jsmith\AppData &lt; 強 &gt; 漫遊 </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \AppData</p></td>
</tr>
</tbody>
</table>

 

 

下表顯示本機和漫遊位置、已完成% AppData% 的資料夾重新導向，且位置已經重新導向（通常是網路位置）。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">套件中的 VFS 目錄</th>
<th align="left">後備存放區的對應位置</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>ProgramFilesX86</p></td>
<td align="left"><p>C:\users\jsmith\AppData &lt; 強勁的 &gt; Local </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \ProgramFilesX86</p></td>
</tr>
<tr class="even">
<td align="left"><p>SystemX86</p></td>
<td align="left"><p>C:\users\jsmith\AppData &lt; 強勁的 &gt; Local </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \SystemX86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows</p></td>
<td align="left"><p>C:\users\jsmith\AppData &lt; 強勁的 &gt; Local </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \windows</p></td>
</tr>
<tr class="even">
<td align="left"><p>appv_ROOT</p></td>
<td align="left"><p>C:\users\jsmith\AppData &lt; 強勁的 &gt; Local </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \ appv_ROOT</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AppData</p></td>
<td align="left"><p><strong>\Fileserver </strong> \users\jsmith\roaming\Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \AppData</p></td>
</tr>
</tbody>
</table>

 

 

目前的 App-V 用戶端 VFS 驅動程式無法寫入網路位置，因此 App-V 用戶端會偵測到資料夾重新導向的狀態，並在發行期間和虛擬環境啟動時，複製本機磁片磁碟機上的資料。 在使用者關閉 App V 應用程式，且 App-v 用戶端關閉虛擬環境之後，會將 VFS AppData 的本地儲存空間複製回網路，並啟用其他電腦的漫遊，而這會重複處理常式。 處理常式的詳細步驟如下：

1.  在發佈或虛擬環境啟動期間，App-V 用戶端會偵測 AppData 目錄的位置。

2.  如果漫遊 AppData 路徑是 [本機] 或 [.ino AppData\\Roaming 位置已對應]，則不會發生任何情況。

3.  如果漫遊 AppData 路徑不是本機路徑，則 VFS AppData 目錄會對應到本機 AppData 目錄。

這個處理常式可解決 App-v 用戶端用戶端 VFS 驅動程式不支援的非本機% AppData% 的問題。 不過，儲存在這個新位置的資料不會與 [資料夾重新導向] 漫遊。 在應用程式執行期間的所有變更，都是在本機 AppData 位置進行，而且必須複製到重新導向的位置。 此處理程式的詳細步驟如下：

1.  App-v 應用程式會關閉，進而關閉虛擬環境。

2.  漫遊 AppData 位置的本機快取會壓縮並儲存在 ZIP 檔案中。

3.  ZIP 封裝程式結尾的時間戳記是用來命名檔案。

4.  時間戳記會記錄在註冊表中： HKEY \ _CURRENT \ _USER \\Software\\Microsoft\\AppV\\Client\\Packages\\ &lt; GUID &gt; \\AppDataTime 做為最近已知的 AppData 時間戳記。

5.  呼叫資料夾重新導向程式是為了評估並啟動上傳到漫遊 AppData 目錄的 ZIP 檔案。

如果發生衝突，則會使用時間戳來判斷「最後一個寫入程式入選」案例，並用於在發佈 app-v 應用程式或啟動虛擬環境時，優化下載資料。 [資料夾重新導向] 會讓支援原則所涵蓋的任何其他用戶端提供該資料，並啟動將 AppData\\Roaming 資料儲存到用戶端上的本機 AppData 位置的程式。 詳細的程式如下：

1.  使用者啟動應用程式，即可啟動虛擬環境。

2.  應用程式的虛擬環境會檢查最近一時間戳的 ZIP 檔案（如果有的話）。

3.  針對最近已知上傳的時間戳記（如果有的話），就會選取該註冊表。

4.  除非當地的上一個已知上傳時間戳記大於或等於 ZIP 檔案中的時間戳記，否則會下載最新的 ZIP 檔案。

5.  如果當地的上次已知上傳時間戳記早于漫遊 AppData 位置中的最新 ZIP 檔案，則會將 ZIP 檔案解壓縮至使用者設定檔中的本機 temp 目錄。

6.  在成功解壓縮 ZIP 檔案之後，就會重新命名漫遊 AppData 目錄的本機快取，並將新資料移至 [位置]。

7.  已重新命名的目錄隨即刪除，且應用程式會開啟最近儲存的漫遊 AppData 資料。

這會完成 AppData\\Roaming 位置中存在的應用程式設定成功漫遊。 唯一必須解決的其他條件是套件修復操作。 處理常式的詳細資料如下：

1.  在修復期間，偵測使用者的漫遊 AppData 目錄路徑是否不在本機。

2.  將非本機漫遊 AppData 路徑目標重新建立在預期的漫遊和本機 AppData 位置。

3.  刪除儲存在註冊表中的時間戳記（如果有的話）。

這個程式將會重新建立 AppData 的本機和網路位置，並移除時間戳記的註冊記錄。

## <a href="" id="bkmk-clt-app-lifecycle"></a>App-V 用戶端應用程式週期管理


在 App-v 完整基礎結構中，將應用程式排序之後，會透過 App-v 管理和發佈伺服器來管理併發布至使用者或電腦。 本節詳細說明常見 App-v 應用程式生命週期作業（新增、發佈、啟動、升級及移除）期間發生的作業，以及從 App-v 用戶端角度變更並修改的檔案和註冊表位置。 App-v 用戶端作業是以在執行 App-v 用戶端的電腦上啟動的一系列 PowerShell 命令來執行。

本檔的重點是應用程式-V 完整基礎結構解決方案。 如需與 Configuration Manager 2012 進行 App-v 整合的特定資訊，請造訪： <https://go.microsoft.com/fwlink/?LinkId=392773> 。

App-v 應用程式週期任務會在使用者登入（預設）、電腦啟動或背景定時作業時觸發。 App-V 用戶端作業的設定，包括發佈伺服器、重新整理間隔、套件腳本啟用及其他，都是在設定用戶端或使用 PowerShell 命令進行安裝後設定。 請參閱 TechNet 上的 [如何部署用戶端] 區段，網址為：[如何部署 App-v 用戶端](how-to-deploy-the-app-v-client-51gb18030.md)或使用 PowerShell：

```powershell
get-command *appv*
```

### 發佈更新

發佈重新整理程式是由在 App-V 用戶端上執行的數個較小的操作所組成。 因為 App-v 是應用程式虛擬化技術，而不是任務排程技術，所以使用 Windows 工作計畫程式在使用者登入、電腦啟動時，以及按排程的時間間隔啟用該處理常式。 當您將用戶端發佈至具有正確設定的大型電腦群組時，以上所列的設定是用戶端的設定。 您可以使用下列 PowerShell Cmdlet 來設定這些用戶端設定：

-   **載入 AppVPublishingServer：** 使用提供 App-v 套件的 App-v 發佈伺服器來設定用戶端。

-   **AppVPublishingServer：** 修改 App V 發佈伺服器的目前設定。

-   **AppVClientConfiguration：** 修改 App-V 用戶端的電流設定。

-   **同步處理-AppVPublishingServer：** 手動啟動 App-V 發佈重新整理程式。 在配置發佈伺服器期間建立的排程任務中，也會使用此功能。

下列各節的重點是詳細說明在 App-v 發佈重新整理的不同階段期間發生的操作。 主題包括：

-   新增 app-v 套件

-   發佈 App-v 套件

### 新增 app-v 套件

將 app-v 套件新增到用戶端是發佈重新整理程式的第一個步驟。 最終結果與 `Add-AppVClientPackage` PowerShell 中的 Cmdlet 相同，但在發佈重新整理 add 程式期間，已設定的發佈伺服器會取得聯繫，並將一個高層級的應用程式傳回到用戶端，以拉出更詳細的資訊，而不是單一套件新增作業。 此程式會繼續設定封裝或連線群組的用戶端新增或更新，然後存取 appv 檔案。 接著，會將 appv 檔案的內容擴充並放在本機作業系統的適當位置。 下列是程式的詳細工作流程（假設套件已設定為可進行故障流式處理）。

**如何新增 app-v 套件**

1.  透過 PowerShell 啟動手動啟動，或啟動發佈重新整理程式的任務順序。

    1.  App-V 用戶端會建立 HTTP 連線，並根據目標要求應用程式清單。 發佈更新程式支援以電腦或使用者為目標。

    2.  App-v 發佈伺服器會使用起始目標、使用者或電腦的身分識別，然後查詢資料庫以取得有資格的應用程式清單。 應用程式清單是以 XML 回應形式提供，用戶端使用它來傳送其他要求給伺服器，以取得每個套件的詳細資訊。

2.  App-V 用戶端上的發佈代理程式會執行序列化下列所有動作。

    評估已取消發佈或停用的任何連線群組，因為無法處理屬於連線群組的套件版本更新。

3.  透過識別新增或更新作業來設定套件。

    1.  App-V 用戶端利用來自 Windows 的 AppX API，並從發佈伺服器存取 appv 檔案。

    2.  隨即會開啟套件檔案，並將 AppXManifest.xml 和 StreamMap.xml 下載到套件存放區。

    3.  完整的資料流程發佈區塊資料 StreamMap.xml 中定義。 在套件 Store\\PkgGUID\\VerGUID\\Root. 中儲存發佈區塊資料

        -   圖示：延伸點的目標。

        -   可移植的可執行檔頭（PE 標題）：延伸點的目標，包含有關影像的基本資訊需要磁片上、直接存取或透過檔案類型。

        -   腳本：下載要在整個發佈程式中使用的腳本目錄。

    4.  填入套件存放區：

        1.  在磁片上建立可代表所列之任何目錄的提取套件的稀疏檔案。

        2.  將頂層檔案和目錄階段放在 root 之下。

        3.  當目錄在磁片上列為稀疏，且依需求傳送時，就會建立所有其他檔案。

    5.  建立電腦目錄專案。 從套件檔案建立 Manifest.xml 和 DeploymentConfiguration.xml （如果沒有建立預留位置的套件中有 DeploymentConfiguration.xml 檔案）。

    6.  在註冊表 HKLM\\Software\\Microsoft\\AppV\\Client\\Packages\\PkgGUID\\Versions\\VerGUID\\Catalog 中建立套件存放區的位置

    7.  建立從套件存放區到%ProgramData%\\Microsoft\\AppV\\Client\\VReg\\ {VersionGUID} .dat 的 Registry .dat 檔案。

    8.  使用 App-v 核心模式驅動程式 HKLM\\Microsoft\\Software\\AppV\\MAV 註冊套件

    9.  從 [AppxManifest.xml] 或 [DeploymentConfig.xml 檔案] 中為套件 [新增時間] 調用腳本。

4.  透過新增及啟用或停用來設定連線群組。

5.  移除未發佈至目標（使用者或電腦）的物件。

    **記事** 這將不會執行套件刪除，而是移除特定目標（使用者或電腦）的整合點，並移除使用者目錄檔案（適用于全域發佈的電腦目錄檔案）。

     

6.  根據用戶端設定來喚醒呼叫背景載入。

7.  已立即還原已擁有電腦或使用者之發佈資訊的套件。

    **記事** 這種情況是在未以背景新增套件的情況下，在移除的產品中發生。

     

這樣就完成了發佈重新整理程式的新增-V 套件。 下一個步驟是將套件發佈到特定的目標（電腦或使用者）。

![封裝新增檔案和登錄資料](images/packageaddfileandregistrydata.png)

### 發佈 App-v 套件

在發佈重新整理作業期間，特定的發佈作業（發佈 AppVClientPackage）會將專案新增至使用者目錄、將權利對應給使用者、識別本地書店，以及完成任何整合步驟完成。 以下是詳細步驟。

**如何發佈和 App-v 套件**

1.  套件專案會新增至使用者目錄

    1.  使用者目標套件： UserDeploymentConfiguration.xml 和 UserManifest.xml 都放在電腦上的使用者目錄中

    2.  電腦目標（全域）套件： UserDeploymentConfiguration.xml 位於 [電腦目錄] 中

2.  在 HKLM\\Software\\Microsoft\\AppV\\MAV 上使用使用者的核心模式驅動程式註冊套件

3.  執行整合作業。

    1.  建立延伸點。

    2.  將備份資訊儲存在使用者的 [登錄] 和 [漫遊] 設定檔（快捷方式備份）中。

        **記事** 這可讓您在未發佈套件的情況下，還原延伸點。

         

    3.  針對發佈時間執行腳本。

發佈屬於連線群組的 app-v 套件與上述程式非常類似。 針對 [連線群組]，儲存特定目錄資訊的路徑，包括 [PackageGroups] 作為目錄目錄的子項。 如需詳細資訊，請查看上述電腦和使用者目錄資訊。

![封裝新增檔案和註冊表資料-全域](images/packageaddfileandregistrydata-global.png)

### 應用程式啟動

發佈重新整理程式之後，使用者會啟動並重新啟動 App-v 應用程式。 這個程式非常簡單且經過優化，可使用最少的網路流量快速啟動。 App-v 用戶端會針對發佈期間建立的檔案，檢查使用者目錄的路徑。 已建立啟動套件的許可權之後，應用程式 V 用戶端會建立虛擬環境、開始流式處理任何必要的資料，以及在虛擬環境建立期間套用適當的資訊清單和部署設定檔。 在針對特定套件和應用程式建立並設定虛擬環境的情況下，應用程式就會啟動。

**如何啟動 App-v 應用程式**

1.  使用者透過按一下快捷方式或檔案類型的調用來啟動應用程式。

2.  App-v 用戶端會驗證以下檔案在使用者目錄中是否存在

    -   UserDeploymentConfiguration.xml

    -   UserManifest.xml

3.  如果檔案存在，應用程式就擁有該特定使用者的資格，而應用程式將會啟動啟動程式。 此時沒有任何網路流量。

4.  接著，應用程式-V 用戶端會檢查在登錄中找到的為 App-v 用戶端服務註冊的套件路徑。

5.  尋找套件存放區的路徑後，就會建立虛擬環境。 如果這是第一次啟動，主要功能會封鎖下載（如果有的話）。

6.  下載之後，應用程式 V 用戶端服務會使用資訊清單和部署設定檔來設定虛擬環境，並載入所有 App-v 子系統。

7.  應用程式啟動。 針對套件存放區（稀疏檔案）中任何遺失的檔案，App-v 會視需要將檔案錯誤地資料流。

    ![封裝新增檔案和登錄資料-資料流程](images/packageaddfileandregistrydata-stream.png)

### 升級 app-v 套件

App-v 5 套件升級程式與較舊版本的 App-v 不同。 App-v 支援針對不同使用者的電腦上的多個版本。 您可以隨時新增套件版本，因為套件存放區和目錄是以新的資源更新。 加入新的版本資源所專用的唯一程式是儲存優化。 在升級期間，只會將新檔案新增至新的版本存放位置，並為未改動的檔案建立硬連結。 這會減少整個儲存空間，只要將檔案呈現在一個磁片位置，然後使用磁片上的 [檔案位置] 專案將它投影到所有資料夾中。 升級 App-v 套件的特定詳細資料如下所示：

**如何升級 app-v 套件**

1.  應用程式-V 用戶端會執行發佈重新整理並探索較新的 app-v 套件版本。

2.  套件專案會新增至新版本的適當目錄

    1.  使用者目標套件： UserDeploymentConfiguration.xml 和 UserManifest.xml 會放在電腦上的使用者目錄中 appdata\\roaming\\Microsoft\\AppV\\Client\\Catalog\\Packages\\PkgGUID\\VerGUID

    2.  電腦目標（全域）套件： UserDeploymentConfiguration.xml 位於電腦目錄中的%programdata%\\Microsoft\\AppV\\Client\\Catalog\\Packages\\PkgGUID\\VerGUID

3.  在 HKLM\\Software\\Microsoft\\AppV\\MAV 上使用使用者的核心模式驅動程式註冊套件

4.  執行整合作業。

    -   整合資訊清單和動態配置檔案的延伸點（EP）。

    1.  以檔案為基礎的 EP 資料會儲存在利用套件存放區中連接點的 AppData 資料夾中。

    2.  新版本推出時，版本 1 EPs 已存在。

    3.  針對任何更新或更新的延伸點，將延伸點切換至電腦或使用者目錄中的版本2位置。

5.  針對發佈時間執行腳本。

6.  根據需要安裝並排的元件。

### 升級使用中的 app-v 套件

**從 app-v 5 SP2 開始**：如果您嘗試升級的套件是由最終使用者所使用，則升級工作會放在擱置中的狀態。 稍後會根據下列規則來執行升級：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">任務類型</th>
<th align="left">適用的規則</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>以使用者為基礎的工作，例如，將套件發佈給使用者</p></td>
<td align="left"><p>暫停的工作將會在使用者登出後執行，然後重新登入。</p></td>
</tr>
<tr class="even">
<td align="left"><p>以全域為基礎的工作，例如，全域啟用連接群組</p></td>
<td align="left"><p>當電腦關閉後再重新開機時，會執行待處理的工作。</p></td>
</tr>
</tbody>
</table>

 

當任務放在擱置狀態時，App-v 用戶端也會產生未決工作的登錄機碼，如下所示：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">以使用者為基礎或以全域為基礎的工作</th>
<th align="left">登錄機碼的產生位置</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>以使用者為基礎的工作</p></td>
<td align="left"><p>KEY_CURRENT_USER \Software\Microsoft\AppV\Client\PendingTasks</p></td>
</tr>
<tr class="even">
<td align="left"><p>全域基礎任務</p></td>
<td align="left"><p>HKEY_LOCAL_MACHINE \Software\Microsoft\AppV\Client\PendingTasks</p></td>
</tr>
</tbody>
</table>

 

必須先完成下列作業，使用者才能使用較新版本的套件：

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
<td align="left"><p>這項工作是特定于電腦的，您可以透過完成上方 [封裝] 新增區段中的步驟，隨時執行此工作。</p></td>
</tr>
<tr class="even">
<td align="left"><p>發佈套件</p></td>
<td align="left"><p>如需步驟，請參閱上述套件發佈區段。 這個程式要求您更新系統上的延伸點。 當您完成此工作時，使用者就無法使用該應用程式。</p></td>
</tr>
</tbody>
</table>

 

使用下列範例案例作為更新套件的指南。

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
<td align="left"><p>嘗試升級時，未使用 app-v 套件</p></td>
<td align="left"><p>套件的下列元件都無法使用：虛擬應用程式、COM 伺服器或命令介面延伸。</p>
<p>系統管理員會發佈較新版本的套件，且下次啟動套件中的元件或應用程式時，升級就會生效。 新版本的套件會進行流式處理並執行。 在此案例中，從舊版 App-V 5 發行的 app-v 5 SP2 中沒有任何變更。</p></td>
</tr>
<tr class="even">
<td align="left"><p>當系統管理員發佈更新版本的套件時，會使用 app-v 套件</p></td>
<td align="left"><p>升級作業是由 App-v 用戶端設定為擱置，這表示該操作已排入佇列，稍後在套件未使用時執行。</p>
<p>如果封裝應用程式在使用中，使用者會關閉虛擬應用程式，之後就可以進行升級。</p>
<p>如果套件有 shell 擴充功能（Office 2013），而這些副檔名是由 Windows Explorer 永久載入，使用者就無法登入。 使用者必須登出，然後再重新登入，以啟動 App-v 套件升級。</p></td>
</tr>
</tbody>
</table>

 

### 全域與使用者發佈

您可以使用兩種方法的其中一種來發佈 app-v 套件;使用者在特定使用者或一組使用者和全域群組中擁有 App V 套件的不足，該使用者可以在整個電腦上為電腦的所有使用者提供 App-v （機器翻譯）。 一旦已暫停套件升級且未使用 App-v 套件，請考慮兩種發佈類型：

-   已**全域發佈**：應用程式已發佈至電腦;該電腦上的所有使用者都可以使用它。 當 App-v 用戶端服務啟動時，就會發生升級，這會有效地表示電腦重新開機。

-   **使用者已發佈**：應用程式已發佈給使用者。 如果電腦上有多個使用者，應用程式可以發佈到使用者的子集。 當使用者登入或再次發佈時（定期、ConfigMgr 原則重新整理和評估，或由 PowerShell 命令顯式進行 App-v 發佈/重新整理），就會發生升級。

### 移除 App-v 套件

在完整基礎結構中移除 App-v 應用程式是取消發佈操作，不會執行套件移除。 該程式與上述發佈程式相同，但不是新增移除程式，而是顛倒對 App-v 套件所做的變更。

### 修復 App-v 套件

修復操作非常簡單，但可能會影響電腦上的許多位置。 先前提到的 [寫入時複製（牛）] 位置已移除，而延伸點則是解除整合，然後再重新整合。 請透過查看在註冊表中登錄的位置，查看牛資料放置位置。 這個作業會自動完成，而且除了從 App-v 用戶端主控台或透過 PowerShell 啟動修復作業以外，沒有任何管理控制權。

## <a href="" id="bkmk-integr-appv-pkgs"></a>集成 App-v 套件


App-V 用戶端與套件架構可在新增套件和發佈套件期間，提供與本機作業系統的特定整合。 三個檔案可為 App-v 套件定義整合或延伸點：

-   AppXManifest.xml：儲存在套件內，並將回退複本儲存在套件存放區和使用者設定檔中。 包含在排序程式期間建立的選項。

-   DeploymentConfig.xml：提供電腦和使用者的整合延伸點的配置資訊。

-   UserConfig.xml： Deploymentconfig.xml 的子集，只提供使用者專用的設定，且僅限以使用者為基礎的延伸點。

### 整合規則

使用 App-v 用戶端將 App-v 應用程式發佈到電腦時，以下清單中所述就會發生一些特定動作：

-   全域發佈：快速鍵會儲存在 [所有使用者] 設定檔位置，而其他延伸點則會儲存在 HKLM hive 中的 [檔案] 中。

-   使用者發佈：快速鍵會儲存在目前的使用者帳戶設定檔中，而其他延伸點則會儲存在 HKCU 配置儲存格中的登錄。

-   備份與還原：現有的原生應用程式資料和註冊表（例如 FTA 註冊）是在發佈期間進行備份。

    1.  根據上一個整合式套件，將擁有權傳遞到最新發佈的 app-v 應用程式，以提供對 app-v 套件的擁有權。

    2.  未發佈擁有的 app-v 套件時，擁有權從一個 App-v 套件轉移到另一個應用程式。 這不會啟動資料或註冊表的還原。

    3.  在針對每個延伸點取消發佈或移除最後一個套件時，還原已備份的資料。

### 延伸點

App-v 發佈檔案（資訊清單和動態配置）提供數個延伸點，讓應用程式能夠與本機作業系統整合。 這些延伸點會執行一般的應用程式安裝工作，例如放置快速鍵、建立檔案類型關聯，以及註冊元件。 因為這些程式是與傳統應用程式不同的方式來安裝的虛擬化應用程式，所以有一些差異。 以下是本節所涵蓋延伸點的清單：

-   方式

-   檔案類型關聯

-   命令介面延伸

-   COM

-   軟體用戶端

-   應用程式功能

-   URL 通訊協定處理常式

-   AppPath

-   虛擬應用程式

### 方式

[簡短剪下] 是與作業系統整合的其中一個基本元素，也就是 [直接使用者啟動] App-v 應用程式的介面。 在發佈和取消發佈 App-v 應用程式期間。

從封裝資訊清單和動態配置 XML 檔案，您可以在類似下列的章節中找到特定應用程式可執行檔的路徑：

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

如先前所述，在使用者的設定檔中根據重新整理的操作，預設會放置 App-v 快速鍵。 全域重新整理會將 [所有使用者] 設定檔中的快速鍵放在一起，而 [使用者重新整理] 會將它們儲存在特定使用者 實際的可執行檔會儲存在套件存放區中。 .ICO 檔案的位置是 App-v 封裝中的標記位置。

### 檔案類型關聯

App-V 用戶端會在發佈期間管理本機作業系統的檔案類型關聯，這可讓使用者使用檔案類型調用，或使用特殊註冊副檔名（.docx）來開啟檔案，以啟動 App-v 應用程式。 檔案類型關聯在資訊清單和動態配置檔案中存在，如下列範例所示：

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

**記事** 在這個範例中：

-   `<Name>.xdp</Name>` 是延伸

-   `<Name>AcroExch.XDPDoc</Name>` 是 ProgId 值（指向連續的 ProgId）

-   `<CommandLine>"[{AppVPackageRoot}]\Reader\AcroRd32.exe" "%1"</CommandLine>` 是指向應用程式可執行檔的命令列

 

### 殼層延伸

在排序過程中，會自動將 Shell 延伸內嵌在套件中。 當套件是全域發行時，shell 延伸會提供與應用程式在本機安裝時相同的功能。 應用程式在用戶端上不需要任何額外的設定或配置，就能啟用 shell 擴充功能。

**使用命令介面延伸的需求：**

-   包含內嵌命令介面延伸的套件必須全域發佈。

-   應用程式、Sequencer 和 App-v 用戶端的 "位數" 必須相符，否則 shell 延伸將無法運作。 例如：

    -   應用程式的版本為64位。

    -   排序器正在64位電腦上執行。

    -   套件正在傳送至64位的 App-v 用戶端電腦。

下表顯示支援的命令介面延伸。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">處理</th>
<th align="left">說明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>操作功能表處理常式</p></td>
<td align="left"><p>將功能表項目新增至操作功能表。 在顯示操作功能表前呼叫該內容。</p></td>
</tr>
<tr class="even">
<td align="left"><p>拖放處理常式</p></td>
<td align="left"><p>在按住滑鼠右鍵按一下並修改所出現的操作功能表時，控制動作。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>拖放目標處理常式</p></td>
<td align="left"><p>控制將資料物件拖曳至拖放目標（例如檔案）之後的動作。</p></td>
</tr>
<tr class="even">
<td align="left"><p>資料物件處理常式</p></td>
<td align="left"><p>控制將檔案複製到 [剪貼簿] 或拖放至拖放目標之後的動作。 它可以提供其他剪貼簿格式至拖放目標。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>屬性工作表處理常式</p></td>
<td align="left"><p>取代或新增頁面至物件的 [屬性工作表] 對話方塊。</p></td>
</tr>
<tr class="even">
<td align="left"><p>提示處理常式</p></td>
<td align="left"><p>允許您在滑鼠懸停時，為專案檢索標誌和資訊提示資訊，並在彈出工具提示中顯示。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>欄處理常式</p></td>
<td align="left"><p>可讓您在 Windows 資源管理器的詳細資料檢視中建立和顯示自訂欄 <em> </em> 。 它可以用來延伸排序與分組。</p></td>
</tr>
<tr class="even">
<td align="left"><p>預覽處理常式</p></td>
<td align="left"><p>啟用要在 Windows 資源管理器預覽窗格中顯示的檔案預覽。</p></td>
</tr>
</tbody>
</table>

 

### COM

App-V 用戶端支援支援 COM 整合與虛擬化的發佈應用程式。 COM 整合可讓 App-v 用戶端在本機作業系統上註冊 COM 物件，以及物件的虛擬化。 針對這份檔而言，COM 物件的整合需要額外的詳細資料。

App-v 支援使用兩個處理常式類型，將 COM 物件從套件註冊到本機作業系統：不在處理常式中。 註冊 COM 物件是使用一種或多種不同的應用程式-V 套件（包括關閉、隔離及整合）的方式來完成。 整合模式是針對進程外或進程內類型進行設定。 COM 模式與類型的設定是使用動態配置檔案（deploymentconfig.xml 或 userconfig.xml）來完成。

您可以在以下網址取得 App V 整合的詳細資料： <https://go.microsoft.com/fwlink/?LinkId=392834> 。

### 軟體用戶端和應用程式功能

App-v 支援特定軟體用戶端和應用程式功能延伸點，可讓虛擬化的應用程式在作業系統的軟體用戶端註冊。 這可讓使用者選取 [電子郵件]、[立即訊息] 和 [媒體播放機] 等作業的預設程式。 這個作業是在 [控制台] 中使用 [設定程式存取及電腦預設值] 執行，並在資訊清單或動態設定檔案的排序期間進行設定。 只有在全域發佈 App-v 應用程式時，才支援應用程式功能。

應用程式-以 V 為基礎的郵件用戶端註冊的軟體用戶端範例。

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

**記事** 在這個範例中：

-   `<ClientConfiguration EmailEnabled="true" />` 是整合電子郵件用戶端的整體軟體用戶端設定

-   `<EMail MakeDefault="true">` 是將特定電子郵件客戶程式設定為預設電子郵件用戶端的標誌

-   `<MAPILibrary>[{ProgramFilesX86}]\Mozilla Thunderbird\mozMapi32_InUse.dll</MAPILibrary>` 是 MAPI dll 註冊

 

### URL 通訊協定處理常式

應用程式不一定是使用檔案類型呼叫的虛擬化應用程式。 舉例來說，在支援內嵌 mailto：的應用程式中，在檔或網頁內，使用者按一下 mailto：連結，並預期會取得他們已登錄的郵件用戶端。 App-v 支援 URL 協定處理常式，可以使用本機作業系統針對每個套件進行註冊。 在排序期間，URL 通訊協定處理常式會自動新增到套件中。

如果您有多個應用程式可以登錄特定的 URL 通訊協定處理常式，則可以利用動態配置檔案來修改行為，並針對不應啟動主要應用程式的應用程式，隱含或停用此功能。

### AppPath

AppPath 延伸點支援直接從作業系統呼叫 App V 應用程式。 這通常是從 Run 或 Start 畫面完成，視作業系統而定，這可讓系統管理員提供來自作業系統命令或腳本的 App-v 應用程式存取權，而不需呼叫可執行檔的特定路徑。 因此，它可以避免在所有系統中修改系統 path 環境變數，就像在發佈期間完成。

AppPath 延伸點是在資訊清單或動態配置檔案中設定，而且會儲存在本機電腦上的登錄中，以供使用者發佈時使用。 如需 AppPath 評論的其他資訊： <https://go.microsoft.com/fwlink/?LinkId=392835> 。

### 虛擬應用程式

此子系統提供在排序期間所捕獲的應用程式清單，這些應用程式通常是由其他 App-v 元件所使用。 您可以使用動態設定檔來停用屬於特定應用程式的延伸點整合。 例如，如果套件包含兩個應用程式，則可以停用所有屬於某個應用程式的延伸點，以便只整合其他應用程式的延伸點。

### 延伸點規則

上述延伸點會根據套件發佈的方式，融入作業系統。 [全域發佈] 會將延伸點放在公用電腦位置，使用者發佈會將延伸點放在使用者位置。 例如，在桌面上建立並全域發佈的快捷方式，會產生快捷方式（%Public%\\Desktop）和登錄資料（HKLM\\Software\\Classes）的檔案資料。 相同的快捷方式就是檔案資料（%UserProfile%\\Desktop）和登錄資料（HKCU\\Software\\Classes）。

延伸點不會以相同的方式發佈，因為某些延伸點會需要全域發佈，而其他延伸點則需要在其提供的特定作業系統和架構上進行排序。 以下是描述這兩個主要規則的表格。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">虛擬延伸</th>
<th align="left">需要目標 OS 順序</th>
<th align="left">需要全域發佈</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>快捷</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>檔案類型關聯</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>URL 協定</p></td>
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
<td align="left"><p>資料物件處理常式</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>屬性工作表處理常式</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>提示處理常式</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>欄處理常式</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>命令介面延伸</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>瀏覽器小幫手物件</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p>X</p></td>
</tr>
<tr class="even">
<td align="left"><p>Active X 物件</p></td>
<td align="left"><p>X</p></td>
<td align="left"><p>X</p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-dynamic-config"></a>動態配置處理


將 App-v 套件部署到一個電腦或使用者非常簡單。 不過，隨著組織跨商業線與地理與政治界限部署 AppV 應用程式，只需一次將應用程式排序，就無法使用一組設定。 App-v 是針對此案例設計的，因為它會在資訊清單檔案中的排序期間捕獲特定設定和設定，但也支援使用動態設定檔進行修改。

App-v 動態配置可讓您在電腦層級或使用者層級指定套件的原則。 動態設定檔可讓排序工程師修改套件的設定、後續排序，以解決個別使用者群組或電腦的需求。 在某些情況下，可能需要對應用程式進行修改，才能在 App-v 環境中提供適當的功能。 例如，您可能需要對 \ _ \ * config.xml 檔案進行修改，以便在應用程式執行期間，在指定的時間執行特定動作，例如停用 mailto 延伸，以避免虛擬化的應用程式覆寫其他應用程式的副檔名。

App-v 套件包含在 appv 封裝檔案內的資訊清單檔案，它代表排序運算，而且是選擇原則，除非將動態設定檔指派給特定套件。 排序後，可以修改動態配置檔案，以允許將應用程式發佈到不同的桌面或具有不同延伸點的使用者。 這兩個動態配置檔案是動態部署配置（DDC）和動態使用者設定（DUC）檔案。 本節將重點放在資訊清單和動態設定檔案的組合中。

### 動態設定檔範例

下列範例顯示發佈之後及正常運作期間，資訊清單、部署配置和使用者設定檔的組合。 這些範例是每個檔案的縮寫範例。 用途只會顯示檔案的組合，而不是在每個檔案中所提供的特定類別的完整說明。 如需詳細資訊，請參閱 App-V 5 排序指南，網址為： <https://go.microsoft.com/fwlink/?LinkID=269810>

**Manifest**

```xml
<appv:Extension Category="AppV.Shortcut">
     <appv:Shortcut>
          <appv:File>[{Common Programs}]\7-Zip\7-Zip File Manager.lnk</appv:File>
          <appv:Target>[{AppVPackageRoot}]\7zFM.exe</appv:Target>
          <appv:Icon>[{AppVPackageRoot}]\7zFM exe.O.ico</appv:Icon>
     </appv:Shortcut>
</appv:Extension>
```

**部署設定**

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

**使用者設定**

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

## <a href="" id="bkmk-sidebyside-assemblies"></a>並列元件


App-v 支援在虛擬應用程式發佈期間，在用戶端排序和部署期間自動封裝並行（SxS）元件。 在順序電腦上不存在的元件排序期間，app-v 5 SP2 支援捕獲 SxS 元件。 而且對於由 Visual c + + （版本8及更新版本）和/或 MSXML 執行時間組成的元件，Sequencer 會自動偵測並捕獲這些相依性，即使在監視期間未安裝這些相依性也一樣。 [並列元件] 功能會移除舊版 App-v 的限制，其中 App-v 排序器並未捕獲排序工作站上已存在的元件，並 privatizing 每個套件的每位版本限制的元件。 此行為會導致已將 App-v 應用程式部署到用戶端缺少必要的 SxS 元件，從而導致應用程式啟動失敗。 這會強制進行封裝程式，然後確保套件所需的所有元件都已在本機安裝在使用者的用戶端作業系統上，以確保支援虛擬應用程式。 根據元件的數目和缺少所需相依性的應用程式檔，這項工作既是管理又是實現挑戰。

App-v 中的並行元件支援具有下列功能。

-   在排序期間自動捕獲 SxS 元件，不論該元件是否已安裝在先後順序工作站上。

-   App-v 用戶端會在發佈期間，自動將必要的 SxS 元件安裝至用戶端電腦（如果它們不存在）。

-   Sequencer 會在 Sequencer 報告機制中報告 VC 執行時間相依性。

-   排序器可讓您選擇不封裝已安裝在 Sequencer 上的元件，以支援先前已在目的電腦上安裝元件的情況。

### 自動發佈 SxS 元件

在使用 SxS 元件發佈 app-v 套件期間，App-v 用戶端會檢查電腦上是否存在該元件。 如果元件不存在，用戶端會將元件部署到電腦。 屬於連線群組的套件會依賴並行元件安裝（基本套件的一部分），因為連線群組不包含元件安裝的任何相關資訊。

**記事** 在元件中取消發佈或移除套件時，並不會移除該套件的元件。

 

## <a href="" id="bkmk-client-logging"></a>用戶端記錄


App-v 用戶端會將資訊以標準 ETW 格式記錄到 Windows 事件記錄。 您可以在事件檢視器中的 [應用程式和服務 Logs\\Microsoft\\AppV\\Client.] 底下找到特定的 App-v 事件

**記事** 在 App-v 5.0 SP3 中，部分記錄已整合並移到下列位置：

`Event logs/Applications and Services Logs/Microsoft/AppV/ServiceLog`

如需已移動之記錄的清單，請參閱[關於 App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-event-logs-moved)。

 

以下所記錄的事件有三種特定類別。

系統**管理員**：記錄應用到 App-v 用戶端之設定的事件，並包含主要警告和錯誤。

[作業 **]：記錄**個別元件的一般 App V 執行與使用方式，建立已在 App-v 用戶端上完成之 app-v 作業的審核記錄。

**虛擬應用程式**：記錄虛擬應用程式啟動和使用虛擬化子系統的功能。






 

 





