---
title: 關於 Client 組態設定
description: 關於 Client 組態設定
author: dansimp
ms.assetid: cc7ae28c-b2ac-4f68-b992-5ccdbd5316a4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 289f5b35ac223d488152ff7ee1f42b1cf50341df
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800719"
---
# 關於 Client 組態設定


Microsoft Application Virtualization （App-v）5.0 用戶端將其設定儲存在註冊表中。 如果您瞭解註冊表中的資料格式，就可以收集一些有關用戶端的有用資訊。 您也可以透過變更登錄專案來設定多個用戶端動作。 本主題列出 App-v 5.0 用戶端設定設定並說明其用法。 您可以使用 PowerShell 來修改用戶端設定。 如需有關使用 PowerShell 與 App-v 5.0 的詳細資訊，請參閱[使用 Powershell 管理 App-v](administering-app-v-by-using-powershell.md)。

## <a href="" id="---------app-v-5-0-client-configuration-settings"></a> App-V 5.0 用戶端配置設定


下表顯示 App-V 5.0 用戶端配置設定的相關資訊：

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
<th align="left">設定名稱</th>
<th align="left">設定標誌</th>
<th align="left">描述</th>
<th align="left">設定選項</th>
<th align="left">登錄機碼值</th>
<th align="left">已停用原則狀態金鑰和值</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>PackageInstallationRoot</p></td>
<td align="left"><p>PACKAGEINSTALLATIONROOT</p></td>
<td align="left"><p>指定將安裝所有新應用程式和更新的目錄。</p></td>
<td align="left"><p>字串</p></td>
<td align="left"><p>Streaming\PackageInstallationRoot</p></td>
<td align="left"><p>未寫入原則值（與 [未設定] 相同）</p></td>
</tr>
<tr class="even">
<td align="left"><p>PackageSourceRoot</p></td>
<td align="left"><p>PACKAGESOURCEROOT</p></td>
<td align="left"><p>覆寫下載套件內容的來源位置。</p></td>
<td align="left"><p>字串</p></td>
<td align="left"><p>Streaming\PackageSourceRoot</p></td>
<td align="left"><p>未寫入原則值（與 [未設定] 相同）</p></td>
</tr>
<tr class="odd">
<td align="left"><p>AllowHighCostLaunch</p></td>
<td align="left"><p>無法使用。</p></td>
<td align="left"><p>此設定會控制是否要在透過計量付費網路連線（例如4G）連線的 Windows 8 電腦上啟動虛擬化應用程式。</p></td>
<td align="left"><p>True （enabled）;False （停用狀態）</p></td>
<td align="left"><p>Streaming\AllowHighCostLaunch</p></td>
<td align="left"><p>0</p></td>
</tr>
<tr class="even">
<td align="left"><p>ReestablishmentRetries</p></td>
<td align="left"><p>無法使用。</p></td>
<td align="left"><p>指定重試刪除的會話的次數。</p></td>
<td align="left"><p>Integer （0-99）</p></td>
<td align="left"><p>Streaming\ReestablishmentRetries</p></td>
<td align="left"><p>未寫入原則值（與 [未設定] 相同）</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ReestablishmentInterval</p></td>
<td align="left"><p>無法使用。</p></td>
<td align="left"><p>指定嘗試重建已刪除的會話之間的秒數。</p></td>
<td align="left"><p>Integer （0-3600）</p></td>
<td align="left"><p>Streaming\ReestablishmentInterval</p></td>
<td align="left"><p>未寫入原則值（與 [未設定] 相同）</p></td>
</tr>
<tr class="even">
<td align="left"><p>AutoLoad</p></td>
<td align="left"><p>AUTOLOAD</p></td>
<td align="left"><p>指定如何在特定電腦上使用 App-v 自動載入新套件。</p></td>
<td align="left"><p>（0x0）無;（0x1）先前已使用;（0x2） All</p></td>
<td align="left"><p>Streaming\AutoLoad</p></td>
<td align="left"><p>未寫入原則值（與 [未設定] 相同）</p></td>
</tr>
<tr class="odd">
<td align="left"><p>LocationProvider</p></td>
<td align="left"><p>無法使用。</p></td>
<td align="left"><p>指定 IAppvPackageLocationProvider 介面的相容實現的 CLSID。</p></td>
<td align="left"><p>字串</p></td>
<td align="left"><p>Streaming\LocationProvider</p></td>
<td align="left"><p>未寫入原則值（與 [未設定] 相同）</p></td>
</tr>
<tr class="even">
<td align="left"><p>CertFilterForClientSsl</p></td>
<td align="left"><p>無法使用。</p></td>
<td align="left"><p>指定憑證存放區中有效憑證的路徑。</p></td>
<td align="left"><p>字串</p></td>
<td align="left"><p>Streaming\CertFilterForClientSsl</p></td>
<td align="left"><p>未寫入原則值（與 [未設定] 相同）</p></td>
</tr>
<tr class="odd">
<td align="left"><p>VerifyCertificateRevocationList</p></td>
<td align="left"><p>無法使用。</p></td>
<td align="left"><p>在使用 HTTPS steaming 前驗證服務器憑證吊銷狀態。</p></td>
<td align="left"><p>True （enabled）;False （停用狀態）</p></td>
<td align="left"><p>Streaming\VerifyCertificateRevocationList</p></td>
<td align="left"><p>0</p></td>
</tr>
<tr class="even">
<td align="left"><p>SharedContentStoreMode</p></td>
<td align="left"><p>SHAREDCONTENTSTOREMODE</p></td>
<td align="left"><p>指定不會將流式套件內容儲存到本機硬碟。</p></td>
<td align="left"><p>True （enabled）;False （停用狀態）</p></td>
<td align="left"><p>Streaming\SharedContentStoreMode</p></td>
<td align="left"><p>0</p></td>
</tr>
<tr class="odd">
<td align="left"><p>名稱</p>
<div class="alert">
<strong>注意</strong><br/><p>此設定無法使用 <strong> AppvclientConfiguration cmdLet 進行修改 </strong> 。 您必須使用 <strong> AppvPublishingServer </strong> Cmdlet。</p>
</div>
<div>

</div></td>
<td align="left"><p>PUBLISHINGSERVERNAME</p></td>
<td align="left"><p>顯示發佈伺服器的名稱。</p></td>
<td align="left"><p>字串</p></td>
<td align="left"><p>Publishing\Servers {serverId} \ FriendlyName</p></td>
<td align="left"><p>未寫入原則值（與 [未設定] 相同）</p></td>
</tr>
<tr class="even">
<td align="left"><p>URL</p>
<div class="alert">
<strong>注意</strong><br/><p>此設定無法使用 <strong> AppvclientConfiguration cmdLet 進行修改 </strong> 。 您必須使用 <strong> AppvPublishingServer </strong> Cmdlet。</p>
</div>
<div>

</div></td>
<td align="left"><p>PUBLISHINGSERVERURL</p></td>
<td align="left"><p>顯示發佈伺服器的 URL。</p></td>
<td align="left"><p>字串</p></td>
<td align="left"><p>Publishing\Servers {serverId} \ URL</p></td>
<td align="left"><p>未寫入原則值（與 [未設定] 相同）</p></td>
</tr>
<tr class="odd">
<td align="left"><p>GlobalRefreshEnabled</p>
<div class="alert">
<strong>注意</strong><br/><p>此設定無法使用 <strong> AppvclientConfiguration cmdLet 進行修改 </strong> 。 您必須使用 <strong> AppvPublishingServer </strong> Cmdlet。</p>
</div>
<div>

</div></td>
<td align="left"><p>GLOBALREFRESHENABLED</p></td>
<td align="left"><p>啟用全域發佈重新整理（布林值）</p></td>
<td align="left"><p>True （enabled）;False （停用狀態）</p></td>
<td align="left"><p>Publishing\Servers{serverId}\GlobalEnabled</p></td>
<td align="left"><p>False</p></td>
</tr>
<tr class="even">
<td align="left"><p>GlobalRefreshOnLogon</p>
<div class="alert">
<strong>注意</strong><br/><p>此設定無法使用 <strong> AppvclientConfiguration cmdLet 進行修改 </strong> 。 您必須使用 <strong> AppvPublishingServer </strong> Cmdlet。</p>
</div>
<div>

</div></td>
<td align="left"><p>GLOBALREFRESHONLOGON</p></td>
<td align="left"><p>在登入時觸發全域發佈重新整理。 布林值</p></td>
<td align="left"><p>True （enabled）;False （停用狀態）</p></td>
<td align="left"><p>Publishing\Servers{serverId}\GlobalLogonRefresh</p></td>
<td align="left"><p>False</p></td>
</tr>
<tr class="odd">
<td align="left"><p>GlobalRefreshInterval</p>
<div class="alert">
<strong>注意</strong><br/><p>此設定無法使用 <strong> AppvclientConfiguration cmdLet 進行修改 </strong> 。 您必須使用 <strong> AppvPublishingServer </strong> Cmdlet。</p>
</div>
<div>

</div></td>
<td align="left"><p>GLOBALREFRESHINTERVAL  </p></td>
<td align="left"><p>使用 GlobalRefreshIntervalUnit 指定發佈重新整理間隔。 若要停用套件重新整理，請選取 [0]。</p></td>
<td align="left"><p>Integer （0-744</p></td>
<td align="left"><p>Publishing\Servers{serverId}\GlobalPeriodicRefreshInterval</p></td>
<td align="left"><p>0</p></td>
</tr>
<tr class="even">
<td align="left"><p>GlobalRefreshIntervalUnit</p>
<div class="alert">
<strong>注意</strong><br/><p>此設定無法使用 <strong> AppvclientConfiguration cmdLet 進行修改 </strong> 。 您必須使用 <strong> AppvPublishingServer </strong> Cmdlet。</p>
</div>
<div>

</div></td>
<td align="left"><p>GLOBALREFRESHINTERVALUNI</p></td>
<td align="left"><p>指定間隔單位（小時0-23，天0-31）。 </p></td>
<td align="left"><p>0代表小時，1代表日</p></td>
<td align="left"><p>Publishing\Servers{serverId}\GlobalPeriodicRefreshIntervalUnit</p></td>
<td align="left"><p>sr-1</p></td>
</tr>
<tr class="odd">
<td align="left"><p>UserRefreshEnabled</p>
<div class="alert">
<strong>注意</strong><br/><p>此設定無法使用 <strong> AppvclientConfiguration cmdLet 進行修改 </strong> 。 您必須使用 <strong> AppvPublishingServer </strong> Cmdlet。</p>
</div>
<div>

</div></td>
<td align="left"><p>USERREFRESHENABLED </p></td>
<td align="left"><p>啟用使用者發佈更新（布林值）</p></td>
<td align="left"><p>True （enabled）;False （停用狀態）</p></td>
<td align="left"><p>Publishing\Servers{serverId}\UserEnabled</p></td>
<td align="left"><p>False</p></td>
</tr>
<tr class="even">
<td align="left"><p>UserRefreshOnLogon</p>
<div class="alert">
<strong>注意</strong><br/><p>此設定無法使用 <strong> AppvclientConfiguration cmdLet 進行修改 </strong> 。 您必須使用 <strong> AppvPublishingServer </strong> Cmdlet。</p>
</div>
<div>

</div></td>
<td align="left"><p>USERREFRESHONLOGON</p></td>
<td align="left"><p>觸發使用者發佈重新整理 onlogon。 布林值</p>
<p>字數統計（含空格）：60</p></td>
<td align="left"><p>True （enabled）;False （停用狀態）</p></td>
<td align="left"><p>Publishing\Servers{serverId}\UserLogonRefresh</p></td>
<td align="left"><p>False</p></td>
</tr>
<tr class="odd">
<td align="left"><p>UserRefreshInterval</p>
<div class="alert">
<strong>注意</strong><br/><p>此設定無法使用 <strong> AppvclientConfiguration cmdLet 進行修改 </strong> 。 您必須使用 <strong> AppvPublishingServer </strong> Cmdlet。</p>
</div>
<div>

</div></td>
<td align="left"><p>USERREFRESHINTERVAL     </p></td>
<td align="left"><p>使用 UserRefreshIntervalUnit 指定發佈重新整理間隔。 若要停用套件重新整理，請選取 [0]。</p>
<p>字數統計（含空格）：85</p></td>
<td align="left"><p>整數（0-744 小時）</p></td>
<td align="left"><p>Publishing\Servers{serverId}\UserPeriodicRefreshInterval</p></td>
<td align="left"><p>0</p></td>
</tr>
<tr class="even">
<td align="left"><p>UserRefreshIntervalUnit</p>
<div class="alert">
<strong>注意</strong><br/><p>此設定無法使用 <strong> AppvclientConfiguration cmdLet 進行修改 </strong> 。 您必須使用 <strong> AppvPublishingServer </strong> Cmdlet。</p>
</div>
<div>

</div></td>
<td align="left"><p>USERREFRESHINTERVALUNIT  </p></td>
<td align="left"><p>指定間隔單位（小時0-23，天0-31）。 </p></td>
<td align="left"><p>0代表小時，1代表日</p></td>
<td align="left"><p>Publishing\Servers{serverId}\UserPeriodicRefreshIntervalUnit</p></td>
<td align="left"><p>sr-1</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MigrationMode</p></td>
<td align="left"><p>MIGRATIONMODE</p></td>
<td align="left"><p>[遷移] 模式可讓 App-V 用戶端修改使用舊版 App-v 所建立之套件的快速鍵與 FTA。</p></td>
<td align="left"><p>True （啟用狀態）;False （停用狀態）</p></td>
<td align="left"><p>Coexistence\MigrationMode</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>CEIPOPTIN</p></td>
<td align="left"><p>CEIPOPTIN</p></td>
<td align="left"><p>允許執行 App-v 5.0 用戶端的電腦收集並傳回特定的使用資訊，以協助我們進一步改善應用程式。</p></td>
<td align="left"><p>0：停用;1以啟用</p></td>
<td align="left"><p>軟體/Microsoft/AppV/CEIP/CEIPEnable</p></td>
<td align="left"><p>0</p></td>
</tr>
<tr class="odd">
<td align="left"><p>EnablePackageScripts</p></td>
<td align="left"><p>ENABLEPACKAGESCRIPTS</p></td>
<td align="left"><p>啟用要執行之設定檔案的套件資訊清單中定義的腳本。</p></td>
<td align="left"><p>True （enabled）;False （停用狀態）</p></td>
<td align="left"><p>\Scripting\EnablePackageScripts</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>RoamingFileExclusions</p></td>
<td align="left"><p>ROAMINGFILEEXCLUSIONS</p></td>
<td align="left"><p>指定相對於% userprofile% （不會與使用者&#39;s 設定檔漫遊）的檔路徑。 範例用法：/ROAMINGFILEEXCLUSIONS =&#39;桌面; 我的圖片&#39;</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>RoamingRegistryExclusions</p></td>
<td align="left"><p>ROAMINGREGISTRYEXCLUSIONS</p></td>
<td align="left"><p>指定不使用使用者設定檔漫遊的登錄路徑。 範例用法：/ROAMINGREGISTRYEXCLUSIONS = software\classes; software\clients</p></td>
<td align="left"><p>字串</p></td>
<td align="left"><p>Integration\RoamingRegistryExclusions</p></td>
<td align="left"><p>未寫入原則值（與 [未設定] 相同）</p></td>
</tr>
<tr class="even">
<td align="left"><p>IntegrationRootUser</p></td>
<td align="left"><p>無法使用。</p></td>
<td align="left"><p>指定位置，以建立與每個使用者已發佈套件之目前版本相關聯的符號連結。 所有的虛擬應用程式延伸（例如快速鍵與檔案類型關聯）都會指向這個路徑。 如果您沒有指定路徑，則在發佈套件時不會使用符號連結。 例如：%localappdata%\Microsoft\AppV\Client\Integration。</p></td>
<td align="left"><p>字串</p></td>
<td align="left"><p>Integration\IntegrationRootUser</p></td>
<td align="left"><p>未寫入原則值（與 [未設定] 相同）</p></td>
</tr>
<tr class="odd">
<td align="left"><p>IntegrationRootGlobal</p></td>
<td align="left"><p>無法使用。</p></td>
<td align="left"><p>指定位置，以建立與全域發佈套件目前版本相關聯的符號連結。 所有的虛擬應用程式延伸（例如快速鍵與檔案類型關聯）都會指向這個路徑。 如果您沒有指定路徑，則在發佈套件時不會使用符號連結。 例如：%allusersprofile%\Microsoft\AppV\Client\Integration</p></td>
<td align="left"><p>字串</p></td>
<td align="left"><p>Integration\IntegrationRootGlobal</p></td>
<td align="left"><p>未寫入原則值（與 [未設定] 相同）</p></td>
</tr>
<tr class="even">
<td align="left"><p>VirtualizableExtensions</p></td>
<td align="left"><p>無法使用。</p></td>
<td align="left"><p>以逗號分隔的副檔名清單，可用於判斷本機安裝的應用程式是否可以在虛擬環境中執行。</p>
<p>在發佈期間建立 [快捷方式]、[FTAs] 和其他延伸點時，如果與延伸點相關聯的應用程式是在本機安裝，App-v 會將檔案副檔名與清單進行比較。 如果副檔名位於這個位置， <strong> 就會 </strong> 新增 RunVirtual 命令列參數，而應用程式將會在實際執行。</p>
<p>如需 RunVirtual 參數的詳細資訊 <strong> </strong> ，請參閱 <a href="running-a-locally-installed-application-inside-a-virtual-environment-with-virtualized-applications.md" data-raw-source="[Running a Locally Installed Application Inside a Virtual Environment with Virtualized Applications](running-a-locally-installed-application-inside-a-virtual-environment-with-virtualized-applications.md)"> 使用虛擬化應用程式在虛擬環境中執行本機安裝的應用程式 </a> 。</p></td>
<td align="left"><p>字串</p></td>
<td align="left"><p>Integration\VirtualizableExtensions</p></td>
<td align="left"><p>未寫入原則值</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ReportingEnabled</p></td>
<td align="left"><p>無法使用。</p></td>
<td align="left"><p>可讓用戶端傳回信息給報表伺服器。</p></td>
<td align="left"><p>True （enabled）;False （停用狀態）</p></td>
<td align="left"><p>Reporting\EnableReporting</p></td>
<td align="left"><p>False</p></td>
</tr>
<tr class="even">
<td align="left"><p>ReportingServerURL</p></td>
<td align="left"><p>無法使用。</p></td>
<td align="left"><p>指定報表服務器上儲存用戶端資訊的位置。</p></td>
<td align="left"><p>字串</p></td>
<td align="left"><p>Reporting\ReportingServer</p></td>
<td align="left"><p>未寫入原則值（與 [未設定] 相同）</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ReportingDataCacheLimit</p></td>
<td align="left"><p>無法使用。</p></td>
<td align="left"><p>指定儲存報告資訊的 XML 快取大小上限（MB）。 此大小會套用到記憶體中的快取。 當達到限制時，記錄檔案將會滾過。 設定為0至1024。</p></td>
<td align="left"><p>整型 [0-1024]</p></td>
<td align="left"><p>Reporting\DataCacheLimit</p></td>
<td align="left"><p>未寫入原則值（與 [未設定] 相同）</p></td>
</tr>
<tr class="even">
<td align="left"><p>ReportingDataBlockSize</p></td>
<td align="left"><p>無法使用。</p></td>
<td align="left"><p>指定要傳送給伺服器以取得報告上傳要求的最大大小（以位元組為單位）。 當記錄達到大量大小時，這可以協助避免永久傳輸失敗。 在1024和無限制之間設定。</p></td>
<td align="left"><p>整數 [1024-無限制]</p></td>
<td align="left"><p>Reporting\DataBlockSize</p></td>
<td align="left"><p>未寫入原則值（與 [未設定] 相同）</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ReportingStartTime</p></td>
<td align="left"><p>無法使用。</p></td>
<td align="left"><p>指定啟動用戶端以傳送資料至報表伺服器的時間。 您必須在0-23 之間指定有效的整數，以對應到一天中的每個小時。 根據預設， <strong> ReportingStartTime </strong> 會在 [10] P. M. 或22日的當天開始。</p>
<div class="alert">
<strong>注意</strong><br/><p>在執行 App-v 5.0 用戶端的電腦最不可能處於離線狀態時，您應該將此設定設定為時間。</p>
</div>
<div>

</div></td>
<td align="left"><p>整數（0到23）</p></td>
<td align="left"><p>報告 \ StartTime</p></td>
<td align="left"><p>未寫入原則值（與 [未設定] 相同）</p></td>
</tr>
<tr class="even">
<td align="left"><p>ReportingInterval</p></td>
<td align="left"><p>無法使用。</p></td>
<td align="left"><p>指定用戶端將用來重新傳送資料至報表伺服器的重試時間間隔。</p></td>
<td align="left"><p>整數</p></td>
<td align="left"><p>Reporting\RetryInterval</p></td>
<td align="left"><p>未寫入原則值（與 [未設定] 相同）</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ReportingRandomDelay</p></td>
<td align="left"><p>無法使用。</p></td>
<td align="left"><p>指定將資料傳送到報表伺服器的最大延遲（以分鐘為單位）。 當排程的任務開始時，用戶端會在0與 ReportingRandomDelay 之間產生隨機延遲， <strong> </strong> 並在傳送資料之前等待指定的持續時間。 這有助於避免在伺服器上發生衝突。</p></td>
<td align="left"><p>Integer [0-ReportingRandomDelay]</p></td>
<td align="left"><p>Reporting\RandomDelay</p></td>
<td align="left"><p>未寫入原則值（與 [未設定] 相同）</p></td>
</tr>
<tr class="even">
<td align="left"><p>EnableDynamicVirtualization</p>
<div class="alert">
<strong>重要</strong><br/><p>此設定僅適用于 App-v 5.0 SP2 或更新版本。</p>
</div>
<div>

</div></td>
<td align="left"><p>無法使用。</p></td>
<td align="left"><p>啟用支援的命令介面延伸、瀏覽器 Helper 物件，以及使用中 X 控制項來虛擬化並與虛擬應用程式一起執行。</p></td>
<td align="left"><p>1（啟用），0（停用）</p></td>
<td align="left"><p>HKEY_LOCAL_MACHINE \Software\Microsoft\AppV\Client\Virtualization</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>EnablePublishingRefreshUI</p>
<div class="alert">
<strong>重要</strong><br/><p>此設定僅適用于 App-v 5.0 SP2。</p>
</div>
<div>

</div></td>
<td align="left"><p>無法使用。</p></td>
<td align="left"><p>針對執行 App-v 5.0 用戶端的電腦啟用 [發佈更新進度] 列。</p></td>
<td align="left"><p>1（啟用），0（停用）</p></td>
<td align="left"><p>HKEY_LOCAL_MACHINE \Software\Microsoft\AppV\Client\Publishing</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>HideUI</p>
<div class="alert">
<strong>重要</strong><br/><p>此設定僅適用于 App-v 5.0 SP2。</p>
</div>
<div>

</div></td>
<td align="left"><p>無法使用。</p></td>
<td align="left"><p>隱藏發佈更新進度列。</p></td>
<td align="left"><p>1（啟用），0（停用）</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>ProcessesUsingVirtualComponents</p></td>
<td align="left"><p>無法使用。</p></td>
<td align="left"><p>指定程式路徑的清單（可能包含萬用字元），這是使用動態虛擬化（支援的命令介面延伸、瀏覽器 helper 物件和 ActiveX 控制項）的候選項目。 只有其完整路徑符合其中一個專案的進程才能使用動態虛擬化。</p></td>
<td align="left"><p>字串</p></td>
<td align="left"><p>Virtualization\ProcessesUsingVirtualComponents</p></td>
<td align="left"><p>空字串。</p></td>
</tr>
</tbody>
</table>








## 相關主題


[部署 App-V 5.0 排序器和用戶端](deploying-the-app-v-50-sequencer-and-client.md)

[如何使用 ADMX 範本和群組原則來修改 App-V 5.0 用戶端組態](how-to-modify-app-v-50-client-configuration-using-the-admx-template-and-group-policy.md)

[如何部署 App-V 用戶端](how-to-deploy-the-app-v-client-gb18030.md)









