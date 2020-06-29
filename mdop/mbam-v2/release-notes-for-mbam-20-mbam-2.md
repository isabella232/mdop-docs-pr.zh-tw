---
title: MBAM 2.0 版本資訊
description: MBAM 2.0 版本資訊
author: dansimp
ms.assetid: c3f16cf3-94f2-47ac-b3a4-3dc505c6a8dd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2d5d3c7d539cf2828d28c1844321bc34ab7736ac
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811246"
---
# MBAM 2.0 版本資訊


若要搜尋這些版本筆記，請按 Ctrl + F。

安裝 Microsoft BitLockerAdministration 和 Monitoring （MBAM）2.0 之前，請先閱讀這些版本資訊。 這些版本資訊包含成功安裝 BitLockerAdministration 和監控2.0 所需的資訊，且包含產品檔中無法提供的資訊。 如果這些版本資訊與其他 MBAM 2.0 檔之間有差異，最新的變更應該視為權威性。 這些版本資訊取代本產品隨附的內容。

## <a href="" id="---------mbam-2-0-known-issues"></a> MBAM 2.0 已知問題


本節包含適用于 MBAM 2.0 的版本資訊。

### 當您使用 Microsoft System Center Configuration Manager 2007 執行 MBAM 時，[電腦名稱稱] 欄位可能不會出現在 BitLocker 電腦合規性和 BitLocker Enterprise 合規性詳細資料包告中。

當您將 MBAM 與 Configuration Manager 2007 搭配使用時，在 BitLocker 電腦合規性和 BitLocker Enterprise 合規性詳細資料包告中，[電腦名稱稱] 欄位可能是空白的。

因應措施：無。

### 在您升級獨立的 MBAM 伺服器基礎結構之後，企業合規性報告無法更新

如果您使用的是 MBAM 獨立拓朴，且您將伺服器基礎結構從版本1.0 升級到2.0，則企業合規性報告無法更新。

因應措施：升級之後，請針對合規性和審核資料庫執行下列腳本：

```sql
-- =============================================
-- Script Template
-- =============================================

DECLARE @DatabaseName nvarchar(255);
SET @DatabaseName = DB_NAME()

USE msdb;

DECLARE @JobID BINARY(16)
SELECT @JobID = job_id
FROM msdb.dbo.sysjobs
WHERE (name = N'CreateCache')

if (@JobID IS NOT NULL)
BEGIN
    EXEC dbo.sp_delete_job
         @job_name = N'CreateCache';
END

EXEC dbo.sp_add_job
    @job_name = N'CreateCache',
    @enabled = 1;

EXEC dbo.sp_add_jobstep
     @job_name = N'CreateCache',
     @step_name = N'Copy Data',
     @subsystem = N'TSQL',
     @command = N'EXEC [ComplianceCore].UpdateCache',
     @database_name = @DatabaseName,
     @retry_attempts = 5,
     @retry_interval = 5;


EXEC dbo.sp_add_jobschedule
     @job_name = N'CreateCache',
     @name = N'ReportCacheSchedule1am',
     @freq_type = 4,
     @freq_interval = 1,
     @active_start_time = 010000,
     @active_end_time = 020000;

EXEC dbo.sp_attach_schedule
     @job_name = N'CreateCache',
     @schedule_name = N'ReportCacheSchedule1am';

EXEC dbo.sp_add_jobschedule
     @job_name = N'CreateCache',
     @name = N'ReportCacheSchedule7am',
     @freq_type = 4,
     @freq_interval = 1,
     @active_start_time = 070000,
     @active_end_time = 080000;

EXEC dbo.sp_attach_schedule
     @job_name = N'CreateCache',
     @schedule_name = N'ReportCacheSchedule7am';

EXEC dbo.sp_add_jobschedule
     @job_name = N'CreateCache',
     @name = N'ReportCacheSchedule1pm',
     @freq_type = 4,
     @freq_interval = 1,
     @active_start_time = 130000,
     @active_end_time = 140000;

EXEC dbo.sp_attach_schedule
     @job_name = N'CreateCache',
     @schedule_name = N'ReportCacheSchedule1pm';

EXEC dbo.sp_add_jobschedule
     @job_name = N'CreateCache',
     @name = N'ReportCacheSchedule7pm',
     @freq_type = 4,
     @freq_interval = 1,
     @active_start_time = 190000,
     @active_end_time = 200000;

EXEC dbo.sp_attach_schedule
     @job_name = N'CreateCache',
     @schedule_name = N'ReportCacheSchedule7pm';

EXEC dbo.sp_add_jobserver
     @job_name = N'CreateCache';
```

### 如果未在 SSRS 中設定 SSL，說明服務台入口網站中的報表會顯示警告

如果 SQL Server Reporting Services （SSRS）未設定為使用安全通訊端層（SSL），那麼當您安裝 MBAM 伺服器時，會將報表的 URL 設定為 HTTP，而不是 HTTPS。 如果您接著流覽至 [技術支援中心] 入口網站，然後選取報表，則會顯示下列訊息：「只會顯示安全內容」。

解決方法：若要顯示報表，請按一下 [**顯示所有內容**]。 若要解決此問題，請移至安裝 SQL Server Reporting Services 的 MBAM 電腦、執行**Reporting Services Configuration Manager**，然後按一下 [ **Web 服務 URL**]。 針對伺服器選取適當的 SSL 憑證，輸入適當的 SSL 埠（預設埠是443），**然後按一下 [** 套用]。

### 不支援 Configuration Manager 資料庫的非預設實例

MBAM 只會在 Configuration Manager 2007 和 SystemCenter2012 ConfigurationManager 中尋找 Configuration Manager 資料庫的預設實例。 如果您使用非預設的實例，您就無法安裝 MBAM。

因應措施：無。

### <a href="" id="clicking--back--in-the-compliance-summary-report-might-throw-an-error"></a>按一下 [規範摘要] 報告中的 [上一步] 可能會引發錯誤

如果您向下切入至 [合規性摘要] 報告，然後按一下 SSRS 報表中的 [**返回**] 連結，可能會引發錯誤。

因應措施：無。

### 只有使用中的空間加密無法正常運作

如果您在安裝 MBAM 用戶端後第一次將電腦加密，且已將群組原則物件設定為只執行加密，請 MBAM 錯誤地加密整個磁片，而不是只加密磁片的已使用空間。 如果您在安裝 MBAM 用戶端時，電腦已經過加密，且您已設定相同的群組原則物件，則加密會正常運作，且只加密電腦上已使用的磁碟空間。

因應措施：無。

### 密碼強度在電腦合規性報告上無法正確顯示

如果您沒有在 [**選擇磁片磁碟機加密方法] 和 [密碼強度**] 群群組原則物件中設定特定的密碼強度，即使密碼強度使用預設的128位加密，Configuration Manager 整合拓撲中的電腦合規性報告仍會顯示密碼強度 "unknown"。 如果您在群組原則物件中設定特定的密碼強度，報告會顯示正確的密碼強度。

因應措施：在 [**選擇磁片磁碟機加密方法及密碼強度**] 群群組原則物件中，永遠都要設定特定的密碼強度。

### 依磁片磁碟機類型進行合規性狀態發佈會在您更新設定專案後顯示舊資料

更新 SystemCenter2012 ConfigurationManager 中的 MBAM 設定專案之後，由 BitLocker Enterprise 合規性儀表板上的 [磁碟機類型] 橫條圖顯示的 [遵從性狀態發佈] 會顯示以舊版本的設定項目資訊為基礎的資料。

因應措施：無。 不支援修改 MBAM 設定專案，而且報告可能不會如預期所示。

### [增強的安全性設定] 可能會導致報告無法正確顯示

如果開啟 Internet Explorer 增強的安全性設定（ESC），當您嘗試在 MBAM 伺服器上查看報告時，可能會出現「拒絕存取」訊息。 根據預設，ESC 會開啟以保護伺服器，方法是將伺服器暴露在網頁內容和應用程式腳本中可能會發生的可能攻擊。

因應措施：如果在您嘗試在 MBAM 伺服器上查看報告時，出現「拒絕存取」訊息，您可以在影像中設定群組原則物件或手動變更預設值，以停用增強的安全性設定。 您也可以在未啟用 ESC 的另一部電腦上，查看報表。

### 從 SQL Server 2008 升級至 SQL Server 2012 時，MBAM 伺服器安裝失敗

如果您從 SQL Server 2008 升級至 SQL Server 2012，然後嘗試安裝合規性和審核資料庫或復原資料庫，安裝就會失敗並回滾。 發生失敗的原因是，在 SQL 升級期間已移除所需的 SQLCMD.exe 檔案，且 MBAM 安裝程式無法找到該檔案。 MSI 記錄檔行可能看起來類似下列：

RunDbInstallScript 復原資料庫 CA： BinDir-E:\\MSSQL\\100\\Tools\\Binn\\SqlCmd.exeRunDbInstallScript 復原資料庫 CA： dbInstance-xxxxxx\\I01RunDbInstallScript Recovery Db CA： sqlScript-C:\\program files Files\\Microsoft\\Microsoft _HardwareRunDbInstallScript _and _Recovery \ [\ Monitoring\\Setup\\KeyRecovery.sqlRunDbInstallScript db ca： dbName-MBAM \ _Recovery \ _and _HardwareRunDbInstallScript Recovery Db CA： DefaultFileName-MBAMI01\\MSSQL\\DATA\\RunDbInstallScript Recovery Db CA： defaultLogPath-K:\\MSSQL\\MSSQL10。I01\\MSSQL\\Data\\RunDbInstallScript 復原資料庫 CA： scriptLogPath-C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\InstallKeyComplianceDatabase.log-e-E-S xxxxxxx\\I01-i "C:\\program files Files\\Microsoft\\Microsoft BitLocker 管理和 Monitoring\\Setup\\KeyRecovery.sql"-v DatabaseName = "MBAM \ _Recovery \ _and \ _Hardware" DefaultFileName = "MBAM \ _Recovery \ _and \ _Hardware" DefaultDataPath = "F:\\MSSQL\\MSSQL10。I01\\MSSQL\\DATA\\ "DefaultLogPath =" K:\\MSSQL\\MSSQL10。I01\\MSSQL\\Data\\ "-o" C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\InstallKeyComplianceDatabase.log "RunDbInstallScript 復原資料庫 ca：開始執行恢復資料庫的安裝 scriptRunDbInstallScript 復原資料庫 CA： Sqlcmd 記錄檔案位於 C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\\\InstallKeyRecoveryDatabase.logRunDbInstallScript 復原 Db CA 例外狀況：安裝復原資料庫自訂操作命令列輸出例外狀況：系統找不到指定的檔案

您可以在 [HKLM\\Software\\Microsoft\\Microsoft SQL Server\\100\\Tools\\ClientSetup.] 下的 [登錄] 中查看 [Path 字串] 值，在 MBAM Server Windows 安裝程式上進行硬編碼，以尋找 SQLCMD.exe 路徑。 在從 SQL Server 2008 遷移至 SQL Server 2012 期間，仍會出現金鑰，但由於 SQL 升級程式已移除檔案，因此資料值所參照的路徑不會包含 SQLCMD.exe 的檔案。

因應措施：暫時將 HKLM\\Software\\Microsoft\\Microsoft SQL Server\\100\\Tools\\ClientSetup Path 字串值重新命名為**Path \ _old**，然後重新執行 MBAM Server Windows 安裝程式。 成功完成安裝並在 SQL Server 2012 中建立資料庫後，請將**路徑 \ _old**值重新命名為**path**。

## MBAM 2.0 的修補程式和知識庫文章


本節包含適用于 MBAM 2.0 的修補程式和知識庫文章。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong>知識庫文章</strong></th>
<th align="left">Title</th>
<th align="left"><strong>連結</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>2831166</p></td>
<td align="left"><p>安裝 Microsoft BitLocker 管理和監控（MBAM）2.0 失敗， &quot; 已安裝 System CENTER CM 物件&quot;</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2831166/EN-US" data-raw-source="[support.microsoft.com/kb/2831166/EN-US](https://support.microsoft.com/kb/2831166/EN-US)">support.microsoft.com/kb/2831166/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2870849</p></td>
<td align="left"><p>使用者無法使用 MBAM 2.0 自助服務入口網站來取得 BitLocker 復原金鑰</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870849/EN-US" data-raw-source="[support.microsoft.com/kb/2870849/EN-US](https://support.microsoft.com/kb/2870849/EN-US)">support.microsoft.com/kb/2870849/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2756402</p></td>
<td align="left"><p>事件描述中的 MBAM 用戶端將無法使用事件 ID 4 和錯誤碼0x8004100E</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2756402/EN-US" data-raw-source="[support.microsoft.com/kb/2756402/EN-US](https://support.microsoft.com/kb/2756402/EN-US)">support.microsoft.com/kb/2756402/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2620287</p></td>
<td align="left"><p>按一下 MBAM 中的 [報表] 索引標籤時，出現「/Reports ' 應用程式」的 [伺服器錯誤] 錯誤訊息</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2620287/EN-US" data-raw-source="[support.microsoft.com/kb/2620287/EN-US](https://support.microsoft.com/kb/2620287/EN-US)">support.microsoft.com/kb/2620287/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2639518</p></td>
<td align="left"><p>在 MBAM 中開啟企業或電腦合規性報告時發生錯誤</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2639518/EN-US" data-raw-source="[support.microsoft.com/kb/2639518/EN-US](https://support.microsoft.com/kb/2639518/EN-US)">support.microsoft.com/kb/2639518/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2620269</p></td>
<td align="left"><p>MBAM 企業報告無法取得更新</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2620269/EN-US" data-raw-source="[support.microsoft.com/kb/2620269/EN-US](https://support.microsoft.com/kb/2620269/EN-US)">support.microsoft.com/kb/2620269/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2712461</p></td>
<td align="left"><p>不支援在網網域控制站上安裝 MBAM</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2712461/EN-US" data-raw-source="[support.microsoft.com/kb/2712461/EN-US](https://support.microsoft.com/kb/2712461/EN-US)">support.microsoft.com/kb/2712461/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2876732</p></td>
<td align="left"><p>您在獨立或 Configuration Manager 集成設定 MBAM 2.0 期間收到錯誤代碼0x80071a90</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2876732/EN-US" data-raw-source="[support.microsoft.com/kb/2876732/EN-US](https://support.microsoft.com/kb/2876732/EN-US)">support.microsoft.com/kb/2876732/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2754259</p></td>
<td align="left"><p>MBAM 及安全的網路通訊</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2754259/EN-US" data-raw-source="[support.microsoft.com/kb/2754259/EN-US](https://support.microsoft.com/kb/2754259/EN-US)">support.microsoft.com/kb/2754259/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2870842</p></td>
<td align="left"><p>MBAM 2.0 安裝程式在 Configuration Manager 整合案例中使用 SQL Server 2008 失敗</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870842/EN-US" data-raw-source="[support.microsoft.com/kb/2870842/EN-US](https://support.microsoft.com/kb/2870842/EN-US)">support.microsoft.com/kb/2870842/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2668533</p></td>
<td align="left"><p>如果未正確設定 SQL SSRS，則 MBAM 安裝程式會失敗</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2668533/EN-US" data-raw-source="[support.microsoft.com/kb/2668533/EN-US](https://support.microsoft.com/kb/2668533/EN-US)">support.microsoft.com/kb/2668533/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2870847</p></td>
<td align="left"><p>MBAM 2.0 安裝失敗， &quot; 檢索 &#39;Reporting Services Point&#39; 角色的 Configuration Manager 伺服器角色設定時發生錯誤&quot;</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870847/EN-US" data-raw-source="[support.microsoft.com/kb/2870847/EN-US](https://support.microsoft.com/kb/2870847/EN-US)">support.microsoft.com/kb/2870847/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2870839</p></td>
<td align="left"><p>由於 SQL 作業 CreateCache 失敗，所以無法在 MBAM 2.0 獨立拓朴中重新整理 MBAM 2.0 企業報告</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870839/EN-US" data-raw-source="[support.microsoft.com/kb/2870839/EN-US](https://support.microsoft.com/kb/2870839/EN-US)">support.microsoft.com/kb/2870839/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2620269</p></td>
<td align="left"><p>MBAM 企業報告無法取得更新</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2620269/EN-US" data-raw-source="[support.microsoft.com/kb/2620269/EN-US](https://support.microsoft.com/kb/2620269/EN-US)">support.microsoft.com/kb/2620269/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2935997</p></td>
<td align="left"><p>MBAM 支援的電腦合規性報告不正確包含不支援的產品</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2935997/EN-US" data-raw-source="[support.microsoft.com/kb/2935997/EN-US](https://support.microsoft.com/kb/2935997/EN-US)">support.microsoft.com/kb/2935997/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2612822</p></td>
<td align="left"><p>在 MBAM 中，電腦記錄遭到拒絕</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2612822/EN-US" data-raw-source="[support.microsoft.com/kb/2612822/EN-US](https://support.microsoft.com/kb/2612822/EN-US)">support.microsoft.com/kb/2612822/EN-US</a></p></td>
</tr>
</tbody>
</table>

 

## 相關主題


[關於 MBAM 2.0](about-mbam-20-mbam-2.md)

 

 





