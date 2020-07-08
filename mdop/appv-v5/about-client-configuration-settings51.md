---
title: 關於 Client 組態設定
description: 關於 Client 組態設定
author: dansimp
ms.assetid: 18bb307a-7eda-4dd6-a83e-6afaefd99470
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fb547eedf63bf165b1e8f5fd024839b3c2af3e4c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800720"
---
# 關於 Client 組態設定


Microsoft Application Virtualization （App-v）5.1 用戶端將其設定儲存在註冊表中。 如果您瞭解註冊表中的資料格式，就可以收集一些有關用戶端的有用資訊。 您也可以透過變更登錄專案來設定多個用戶端動作。 本主題列出 App-v 5.1 用戶端設定設定並說明其用法。 您可以使用 PowerShell 來修改用戶端設定。 如需有關使用 PowerShell 與 App-v 5.1 的詳細資訊，請參閱[使用 Powershell 管理 App-v 5.1](administering-app-v-51-by-using-powershell.md)。

## <a href="" id="---------app-v-5-1-client-configuration-settings"></a> App-V 5.1 用戶端配置設定


下表顯示 App-V 5.1 用戶端配置設定的相關資訊：

|設定名稱 | 設定標誌 | 描述 | 設定選項 | 登錄機碼值 | 已停用原則狀態金鑰和值 |
|-------------|------------|-------------|-----------------|--------------------|--------------------------------------|
| PackageInstallationRoot | PACKAGEINSTALLATIONROOT | 指定將安裝所有新應用程式和更新的目錄。 | 字串 | Streaming\PackageInstallationRoot | 未寫入原則值（與 [未設定] 相同） |
| PackageSourceRoot | PACKAGESOURCEROOT | 覆寫下載套件內容的來源位置。 | 字串 | Streaming\PackageSourceRoot | 未寫入原則值（與 [未設定] 相同） |
| AllowHighCostLaunch | 無法使用。 |此設定會控制是否要在透過計量付費網路連線（例如4G）連線的 Windows 10 電腦上啟動虛擬化應用程式。 | True （enabled）;False （停用狀態） | Streaming\AllowHighCostLaunch | 0 |
| ReestablishmentRetries | 無法使用。 | 指定重試刪除的會話的次數。 | Integer （0-99） | Streaming\ReestablishmentRetries | 未寫入原則值（與 [未設定] 相同） |
| ReestablishmentInterval | 無法使用。 | 指定嘗試重建已刪除的會話之間的秒數。 | Integer （0-3600） | Streaming\ReestablishmentInterval | 未寫入原則值（與 [未設定] 相同） |
| LocationProvider | 無法使用。 | 指定 IAppvPackageLocationProvider 介面的相容實現的 CLSID。 | 字串 | Streaming\LocationProvider | 未寫入原則值（與 [未設定] 相同） |
| CertFilterForClientSsl | 無法使用。 | 指定憑證存放區中有效憑證的路徑。 | 字串 | Streaming\CertFilterForClientSsl | 未寫入原則值（與 [未設定] 相同） |
| VerifyCertificateRevocationList | 無法使用。 | 在使用 HTTPS steaming 前驗證服務器憑證吊銷狀態。 | True （enabled）;False （停用狀態） | Streaming\VerifyCertificateRevocationList | 0 |
| SharedContentStoreMode | SHAREDCONTENTSTOREMODE | 指定不會將流式套件內容儲存到本機硬碟。 | True （enabled）;False （停用狀態） | Streaming\SharedContentStoreMode | 0 |
| 名稱<br>**記事**此設定無法使用**AppvclientConfiguration** cmdLet 進行修改。 您必須使用**AppvPublishingServer** Cmdlet。 | PUBLISHINGSERVERNAME | 顯示發佈伺服器的名稱。 | 字串 | Publishing\Servers\ {serverId} \ FriendlyName | 未寫入原則值（與 [未設定] 相同） |
| URL<br>**記事**此設定無法使用**AppvclientConfiguration** cmdLet 進行修改。 您必須使用**AppvPublishingServer** Cmdlet。 | PUBLISHINGSERVERURL | 顯示發佈伺服器的 URL。 | 字串 | Publishing\Servers\ {serverId} \ URL | 未寫入原則值（與 [未設定] 相同） |
| GlobalRefreshEnabled<br>**記事**此設定無法使用**AppvclientConfiguration** cmdLet 進行修改。 您必須使用**AppvPublishingServer** Cmdlet。 | GLOBALREFRESHENABLED | 啟用全域發佈重新整理（布林值） | True （enabled）;False （停用狀態） | Publishing\Servers\{serverId}\GlobalEnabled | False |
| GlobalRefreshOnLogon<br>**記事**此設定無法使用**AppvclientConfiguration** cmdLet 進行修改。 您必須使用**AppvPublishingServer** Cmdlet。 | GLOBALREFRESHONLOGON | 在登入時觸發全域發佈重新整理。 布林值 | True （enabled）;False （停用狀態） | Publishing\Servers\{serverId}\GlobalLogonRefresh | False |
| GlobalRefreshInterval<br>**記事**此設定無法使用**AppvclientConfiguration** cmdLet 進行修改。 您必須使用**AppvPublishingServer** Cmdlet。 | GLOBALREFRESHINTERVAL | 使用 GlobalRefreshIntervalUnit 指定發佈重新整理間隔。 若要停用套件重新整理，請選取 [0]。 | Integer （0-744） | Publishing\Servers\{serverId}\GlobalPeriodicRefreshInterval | 0 |
| GlobalRefreshIntervalUnit <br>**記事**此設定無法使用**AppvclientConfiguration** cmdLet 進行修改。 您必須使用**AppvPublishingServer** Cmdlet。 | GLOBALREFRESHINTERVALUNI | 指定間隔單位（小時0-23，天0-31）。 | 0代表小時，1代表日 | Publishing\Servers\{serverId}\GlobalPeriodicRefreshIntervalUnit | sr-1 |
| UserRefreshEnabled<br>**記事**此設定無法使用**AppvclientConfiguration** cmdLet 進行修改。 您必須使用**AppvPublishingServer** Cmdlet。 | USERREFRESHENABLED | 啟用使用者發佈更新（布林值） | True （enabled）;False （停用狀態） | Publishing\Servers\{serverId}\UserEnabled | False |
| UserRefreshOnLogon<br>**記事**此設定無法使用**AppvclientConfiguration** cmdLet 進行修改。 您必須使用**AppvPublishingServer** Cmdlet。 | USERREFRESHONLOGON | 觸發使用者發佈重新整理 onlogon。 布林值<br>字數統計（含空格）：60 | True （enabled）;False （停用狀態） | Publishing\Servers\{serverId}\UserLogonRefresh | False |
| UserRefreshInterval<br>**記事**此設定無法使用**AppvclientConfiguration** cmdLet 進行修改。 您必須使用**AppvPublishingServer** Cmdlet。 | USERREFRESHINTERVAL | 使用 UserRefreshIntervalUnit 指定發佈重新整理間隔。 若要停用套件重新整理，請選取 [0]。 | 字數統計（含空格）：85<br>整數（0-744 小時） | Publishing\Servers\{serverId}\UserPeriodicRefreshInterval | 0 |
| UserRefreshIntervalUnit<br>**記事**此設定無法使用**AppvclientConfiguration** cmdLet 進行修改。 您必須使用**AppvPublishingServer** Cmdlet。 | USERREFRESHINTERVALUNIT | 指定間隔單位（小時0-23，天0-31）。 | 0代表小時，1代表日 | Publishing\Servers\{serverId}\UserPeriodicRefreshIntervalUnit | sr-1 |
| MigrationMode | MIGRATIONMODE | [遷移] 模式可讓 App-V 用戶端修改使用舊版 App-v 所建立之套件的快速鍵與 FTA。 | True （啟用狀態）;False （停用狀態） | Coexistence\MigrationMode | |
| CEIPOPTIN | CEIPOPTIN | 允許執行 App-v 5.1 用戶端的電腦收集並傳回特定的使用資訊，以協助我們進一步改善應用程式。 | 0：停用;1以啟用 | 軟體/Microsoft/AppV/CEIP/CEIPEnable | 0 | 
| EnablePackageScripts | ENABLEPACKAGESCRIPTS | 啟用要執行之設定檔案的套件資訊清單中定義的腳本。 | True （enabled）;False （停用狀態） | \Scripting\EnablePackageScripts | | 
| RoamingFileExclusions | ROAMINGFILEEXCLUSIONS | 指定相對於% userprofile% （不會與使用者的設定檔漫遊）的檔路徑。 範例用法：/ROAMINGFILEEXCLUSIONS = ' 桌面; 我的圖片」 | | | |
| RoamingRegistryExclusions | ROAMINGREGISTRYEXCLUSIONS | 指定不使用使用者設定檔漫遊的登錄路徑。 範例用法：/ROAMINGREGISTRYEXCLUSIONS = software\\classes; software\\clients | 字串 | Integration\RoamingRegistryExclusions | 未寫入原則值（與 [未設定] 相同） |
| IntegrationRootUser | 無法使用。 | 指定位置，以建立與每個使用者已發佈套件之目前版本相關聯的符號連結。 所有的虛擬應用程式延伸（例如快速鍵與檔案類型關聯）都會指向這個路徑。 如果您沒有指定路徑，則在發佈套件時不會使用符號連結。 例如：%localappdata%\Microsoft\AppV\Client\Integration。| 字串 | Integration\IntegrationRootUser | 未寫入原則值（與 [未設定] 相同） |
|IntegrationRootGlobal | 無法使用。| 指定位置，以建立與全域發佈套件目前版本相關聯的符號連結。 所有的虛擬應用程式延伸（例如快速鍵與檔案類型關聯）都會指向這個路徑。 如果您沒有指定路徑，則在發佈套件時不會使用符號連結。 例如：%allusersprofile%\Microsoft\AppV\Client\Integration | 字串 | Integration\IntegrationRootGlobal | 未寫入原則值（與 [未設定] 相同） |
| VirtualizableExtensions | 無法使用。 | 以逗號分隔的副檔名清單，可用於判斷本機安裝的應用程式是否可以在虛擬環境中執行。<br>在發佈期間建立 [快捷方式]、[FTAs] 和其他延伸點時，如果與延伸點相關聯的應用程式是在本機安裝，App-v 會將檔案副檔名與清單進行比較。 如果副檔名位於這個位置，就會新增**RunVirtual**命令列參數，而應用程式將會在實際執行。<br>如需**RunVirtual**參數的詳細資訊，請參閱[使用虛擬化應用程式在虛擬環境中執行本機安裝的應用程式](running-a-locally-installed-application-inside-a-virtual-environment-with-virtualized-applications51.md)。 | 字串 | Integration\VirtualizableExtensions | 未寫入原則值 |
| ReportingEnabled | 無法使用。 | 可讓用戶端傳回信息給報表伺服器。 | True （enabled）;False （停用狀態） | Reporting\EnableReporting | False |
| ReportingServerURL | 無法使用。 | 指定報表服務器上儲存用戶端資訊的位置。 | 字串 | Reporting\ReportingServer | 未寫入原則值（與 [未設定] 相同） |
| ReportingDataCacheLimit | 無法使用。 | 指定儲存報告資訊的 XML 快取大小上限（MB）。 此大小會套用到記憶體中的快取。 當達到限制時，記錄檔案將會滾過。 設定為0至1024。 | 整型 [0-1024] | Reporting\DataCacheLimit | 未寫入原則值（與 [未設定] 相同） |
| ReportingDataBlockSize| 無法使用。 | 指定要傳送給伺服器以取得報告上傳要求的最大大小（以位元組為單位）。 當記錄達到大量大小時，這可以協助避免永久傳輸失敗。 在1024和無限制之間設定。 | 整數 [1024-無限制] | Reporting\DataBlockSize | 未寫入原則值（與 [未設定] 相同） |
| ReportingStartTime | 無法使用。 | 指定啟動用戶端以傳送資料至報表伺服器的時間。 您必須在0-23 之間指定有效的整數，以對應到一天中的每個小時。 根據預設， **ReportingStartTime**會在 [10] P. M. 或22日的當天開始。<br>**記事**在執行 App-v 5.1 用戶端的電腦最不可能處於離線狀態時，您應該將此設定設定為時間。 | 整數（0到23） | 報告 \ StartTime | 未寫入原則值（與 [未設定] 相同） |
| ReportingInterval | 無法使用。 | 指定用戶端將用來重新傳送資料至報表伺服器的重試時間間隔。 | 整數 | Reporting\RetryInterval | 未寫入原則值（與 [未設定] 相同） |
| ReportingRandomDelay | 無法使用。 | 指定將資料傳送到報表伺服器的最大延遲（以分鐘為單位）。 當排程的任務開始時，用戶端會在0與**ReportingRandomDelay**之間產生隨機延遲，並在傳送資料之前等待指定的持續時間。 這有助於避免在伺服器上發生衝突。 | Integer [0-ReportingRandomDelay] | Reporting\RandomDelay | 未寫入原則值（與 [未設定] 相同） |
| EnableDynamicVirtualization<br>**重要**此設定僅適用于 App-v 5.0 SP2 或更新版本。 | 無法使用。 | 啟用支援的命令介面延伸、瀏覽器 Helper 物件，以及使用中 X 控制項來虛擬化並與虛擬應用程式一起執行。 | 1（啟用），0（停用） | HKEY_LOCAL_MACHINE \Software\Microsoft\AppV\Client\Virtualization | |
| EnablePublishingRefreshUI<br>**重要**此設定僅適用于 App-v 5.0 SP2。 | 無法使用。 | 針對執行 App-v 5.1 用戶端的電腦啟用 [發佈更新進度] 列。 | 1（啟用），0（停用） | HKEY_LOCAL_MACHINE \Software\Microsoft\AppV\Client\Publishing | |
| HideUI<br>**重要** 此設定僅適用于 App-v 5.0 SP2。| 無法使用。 | 隱藏發佈更新進度列。 | 1（啟用），0（停用） | | |
| ProcessesUsingVirtualComponents | 無法使用。 | 指定程式路徑的清單（可能包含萬用字元），這是使用動態虛擬化（支援的命令介面延伸、瀏覽器 helper 物件和 ActiveX 控制項）的候選項目。 只有其完整路徑符合其中一個專案的進程才能使用動態虛擬化。 | 字串 | Virtualization\ProcessesUsingVirtualComponents | 空字串。 |






## 相關主題


[部署 App-V 5.1 排序器和用戶端](deploying-the-app-v-51-sequencer-and-client.md)

[如何使用 ADMX 範本和群組原則來修改 App-V 5.1 用戶端組態](how-to-modify-app-v-51-client-configuration-using-the-admx-template-and-group-policy.md)

[如何部署 App-V 用戶端](how-to-deploy-the-app-v-client-51gb18030.md)

 

 





