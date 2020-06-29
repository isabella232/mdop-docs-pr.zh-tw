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
# <span data-ttu-id="fa174-103">MBAM 2.0 版本資訊</span><span class="sxs-lookup"><span data-stu-id="fa174-103">Release Notes for MBAM 2.0</span></span>


<span data-ttu-id="fa174-104">若要搜尋這些版本筆記，請按 Ctrl + F。</span><span class="sxs-lookup"><span data-stu-id="fa174-104">To search these release notes, press Ctrl+F.</span></span>

<span data-ttu-id="fa174-105">安裝 Microsoft BitLockerAdministration 和 Monitoring （MBAM）2.0 之前，請先閱讀這些版本資訊。</span><span class="sxs-lookup"><span data-stu-id="fa174-105">Read these release notes thoroughly before you install Microsoft BitLockerAdministration and Monitoring(MBAM)2.0.</span></span> <span data-ttu-id="fa174-106">這些版本資訊包含成功安裝 BitLockerAdministration 和監控2.0 所需的資訊，且包含產品檔中無法提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="fa174-106">These release notes contain information that is required to successfully install BitLockerAdministration and Monitoring2.0 and contain information that is not available in the product documentation.</span></span> <span data-ttu-id="fa174-107">如果這些版本資訊與其他 MBAM 2.0 檔之間有差異，最新的變更應該視為權威性。</span><span class="sxs-lookup"><span data-stu-id="fa174-107">If there is a difference between these release notes and other MBAM2.0 documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="fa174-108">這些版本資訊取代本產品隨附的內容。</span><span class="sxs-lookup"><span data-stu-id="fa174-108">These release notes supersede the content that is included with this product.</span></span>

## <a href="" id="---------mbam-2-0-known-issues"></a> <span data-ttu-id="fa174-109">MBAM 2.0 已知問題</span><span class="sxs-lookup"><span data-stu-id="fa174-109">MBAM2.0 Known Issues</span></span>


<span data-ttu-id="fa174-110">本節包含適用于 MBAM 2.0 的版本資訊。</span><span class="sxs-lookup"><span data-stu-id="fa174-110">This section contains release notes for MBAM2.0.</span></span>

### <span data-ttu-id="fa174-111">當您使用 Microsoft System Center Configuration Manager 2007 執行 MBAM 時，[電腦名稱稱] 欄位可能不會出現在 BitLocker 電腦合規性和 BitLocker Enterprise 合規性詳細資料包告中。</span><span class="sxs-lookup"><span data-stu-id="fa174-111">Computer Name field may not appear in the BitLocker Computer Compliance and BitLocker Enterprise Compliance Details reports when you run MBAM with Microsoft System Center Configuration Manager 2007</span></span>

<span data-ttu-id="fa174-112">當您將 MBAM 與 Configuration Manager 2007 搭配使用時，在 BitLocker 電腦合規性和 BitLocker Enterprise 合規性詳細資料包告中，[電腦名稱稱] 欄位可能是空白的。</span><span class="sxs-lookup"><span data-stu-id="fa174-112">The Computer Name field may be blank in the BitLocker Computer Compliance and BitLocker Enterprise Compliance Details reports when you use MBAM with Configuration Manager 2007.</span></span>

<span data-ttu-id="fa174-113">因應措施：無。</span><span class="sxs-lookup"><span data-stu-id="fa174-113">WORKAROUND: None.</span></span>

### <span data-ttu-id="fa174-114">在您升級獨立的 MBAM 伺服器基礎結構之後，企業合規性報告無法更新</span><span class="sxs-lookup"><span data-stu-id="fa174-114">Enterprise Compliance Report fails to update after you upgrade the Stand-alone MBAM server infrastructure</span></span>

<span data-ttu-id="fa174-115">如果您使用的是 MBAM 獨立拓朴，且您將伺服器基礎結構從版本1.0 升級到2.0，則企業合規性報告無法更新。</span><span class="sxs-lookup"><span data-stu-id="fa174-115">If you are using the MBAM Stand-alone topology, and you upgrade the server infrastructure from version 1.0 to 2.0, the Enterprise Compliance Report fails to update.</span></span>

<span data-ttu-id="fa174-116">因應措施：升級之後，請針對合規性和審核資料庫執行下列腳本：</span><span class="sxs-lookup"><span data-stu-id="fa174-116">WORKAROUND: After the upgrade, run the following script on the Compliance and Audit Database:</span></span>

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

### <span data-ttu-id="fa174-117">如果未在 SSRS 中設定 SSL，說明服務台入口網站中的報表會顯示警告</span><span class="sxs-lookup"><span data-stu-id="fa174-117">Reports in the Help Desk Portal display a warning if SSL is not configured in SSRS</span></span>

<span data-ttu-id="fa174-118">如果 SQL Server Reporting Services （SSRS）未設定為使用安全通訊端層（SSL），那麼當您安裝 MBAM 伺服器時，會將報表的 URL 設定為 HTTP，而不是 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="fa174-118">If SQL Server Reporting Services (SSRS) was not configured to use Secure Socket Layer (SSL), the URL for the reports will be set to HTTP instead of HTTPS when you install the MBAM Server.</span></span> <span data-ttu-id="fa174-119">如果您接著流覽至 [技術支援中心] 入口網站，然後選取報表，則會顯示下列訊息：「只會顯示安全內容」。</span><span class="sxs-lookup"><span data-stu-id="fa174-119">If you then browse to the Help Desk Portal and select a report, the following message displays: “Only Secure Content is Displayed.”</span></span>

<span data-ttu-id="fa174-120">解決方法：若要顯示報表，請按一下 [**顯示所有內容**]。</span><span class="sxs-lookup"><span data-stu-id="fa174-120">WORKAROUND: To show the report, click **Show All Content**.</span></span> <span data-ttu-id="fa174-121">若要解決此問題，請移至安裝 SQL Server Reporting Services 的 MBAM 電腦、執行**Reporting Services Configuration Manager**，然後按一下 [ **Web 服務 URL**]。</span><span class="sxs-lookup"><span data-stu-id="fa174-121">To address this issue, go to the MBAM computer where SQL Server Reporting Services is installed, run **Reporting Services Configuration Manager**, and then click **Web Service URL**.</span></span> <span data-ttu-id="fa174-122">針對伺服器選取適當的 SSL 憑證，輸入適當的 SSL 埠（預設埠是443），**然後按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="fa174-122">Select the appropriate SSL certificate for the server, enter the appropriate SSL port (the default port is 443), and then click **Apply**.</span></span>

### <span data-ttu-id="fa174-123">不支援 Configuration Manager 資料庫的非預設實例</span><span class="sxs-lookup"><span data-stu-id="fa174-123">Non-default instances of the Configuration Manager database are not supported</span></span>

<span data-ttu-id="fa174-124">MBAM 只會在 Configuration Manager 2007 和 SystemCenter2012 ConfigurationManager 中尋找 Configuration Manager 資料庫的預設實例。</span><span class="sxs-lookup"><span data-stu-id="fa174-124">MBAM looks only for the default instance of the Configuration Manager database in Configuration Manager 2007 and SystemCenter2012 ConfigurationManager.</span></span> <span data-ttu-id="fa174-125">如果您使用非預設的實例，您就無法安裝 MBAM。</span><span class="sxs-lookup"><span data-stu-id="fa174-125">If you use a non-default instance, you cannot install MBAM.</span></span>

<span data-ttu-id="fa174-126">因應措施：無。</span><span class="sxs-lookup"><span data-stu-id="fa174-126">WORKAROUND: None.</span></span>

### <a href="" id="clicking--back--in-the-compliance-summary-report-might-throw-an-error"></a><span data-ttu-id="fa174-127">按一下 [規範摘要] 報告中的 [上一步] 可能會引發錯誤</span><span class="sxs-lookup"><span data-stu-id="fa174-127">Clicking “Back” in the Compliance Summary report might throw an error</span></span>

<span data-ttu-id="fa174-128">如果您向下切入至 [合規性摘要] 報告，然後按一下 SSRS 報表中的 [**返回**] 連結，可能會引發錯誤。</span><span class="sxs-lookup"><span data-stu-id="fa174-128">If you drill down into a Compliance Summary report, and then click the **Back** link in the SSRS report, an error might be thrown.</span></span>

<span data-ttu-id="fa174-129">因應措施：無。</span><span class="sxs-lookup"><span data-stu-id="fa174-129">WORKAROUND: None.</span></span>

### <span data-ttu-id="fa174-130">只有使用中的空間加密無法正常運作</span><span class="sxs-lookup"><span data-stu-id="fa174-130">Used Space Only Encryption does not work correctly</span></span>

<span data-ttu-id="fa174-131">如果您在安裝 MBAM 用戶端後第一次將電腦加密，且已將群組原則物件設定為只執行加密，請 MBAM 錯誤地加密整個磁片，而不是只加密磁片的已使用空間。</span><span class="sxs-lookup"><span data-stu-id="fa174-131">If you encrypt a computer for the first time after you install the MBAM Client, and you have set a Group Policy Object to implement Used Space Only encryption, MBAM erroneously encrypts the entire disk instead of encrypting only the disk’s used space.</span></span> <span data-ttu-id="fa174-132">如果您在安裝 MBAM 用戶端時，電腦已經過加密，且您已設定相同的群組原則物件，則加密會正常運作，且只加密電腦上已使用的磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="fa174-132">If a computer is already encrypted when you install the MBAM Client, and you have set the same Group Policy Object, the encryption works correctly and encrypts only the used disk space on your computer.</span></span>

<span data-ttu-id="fa174-133">因應措施：無。</span><span class="sxs-lookup"><span data-stu-id="fa174-133">WORKAROUND: None.</span></span>

### <span data-ttu-id="fa174-134">密碼強度在電腦合規性報告上無法正確顯示</span><span class="sxs-lookup"><span data-stu-id="fa174-134">Cipher strength displays incorrectly on the Computer Compliance report</span></span>

<span data-ttu-id="fa174-135">如果您沒有在 [**選擇磁片磁碟機加密方法] 和 [密碼強度**] 群群組原則物件中設定特定的密碼強度，即使密碼強度使用預設的128位加密，Configuration Manager 整合拓撲中的電腦合規性報告仍會顯示密碼強度 "unknown"。</span><span class="sxs-lookup"><span data-stu-id="fa174-135">If you do not set a specific cipher strength in the **Choose drive encryption method and cipher strength** Group Policy Object, the Computer Compliance report in the Configuration Manager Integration topology always displays “unknown” for the cipher strength, even when the cipher strength uses the default of 128-bit encryption.</span></span> <span data-ttu-id="fa174-136">如果您在群組原則物件中設定特定的密碼強度，報告會顯示正確的密碼強度。</span><span class="sxs-lookup"><span data-stu-id="fa174-136">The report displays the correct cipher strength if you set a specific cipher strength in the Group Policy Object.</span></span>

<span data-ttu-id="fa174-137">因應措施：在 [**選擇磁片磁碟機加密方法及密碼強度**] 群群組原則物件中，永遠都要設定特定的密碼強度。</span><span class="sxs-lookup"><span data-stu-id="fa174-137">WORKAROUND: Always set a specific cipher strength in the **Choose drive encryption method and cipher strength** Group Policy Object.</span></span>

### <span data-ttu-id="fa174-138">依磁片磁碟機類型進行合規性狀態發佈會在您更新設定專案後顯示舊資料</span><span class="sxs-lookup"><span data-stu-id="fa174-138">Compliance Status Distribution By Drive Type displays old data after you update configuration items</span></span>

<span data-ttu-id="fa174-139">更新 SystemCenter2012 ConfigurationManager 中的 MBAM 設定專案之後，由 BitLocker Enterprise 合規性儀表板上的 [磁碟機類型] 橫條圖顯示的 [遵從性狀態發佈] 會顯示以舊版本的設定項目資訊為基礎的資料。</span><span class="sxs-lookup"><span data-stu-id="fa174-139">After you update MBAM configuration items in SystemCenter2012 ConfigurationManager, the Compliance Status Distribution By Drive Type bar chart on the BitLocker Enterprise Compliance Dashboard shows data that is based on information from old versions of the configuration items.</span></span>

<span data-ttu-id="fa174-140">因應措施：無。</span><span class="sxs-lookup"><span data-stu-id="fa174-140">WORKAROUND: None.</span></span> <span data-ttu-id="fa174-141">不支援修改 MBAM 設定專案，而且報告可能不會如預期所示。</span><span class="sxs-lookup"><span data-stu-id="fa174-141">Modification of the MBAM configuration items is not supported, and the report might not appear as expected.</span></span>

### <span data-ttu-id="fa174-142">[增強的安全性設定] 可能會導致報告無法正確顯示</span><span class="sxs-lookup"><span data-stu-id="fa174-142">Enhanced Security Configuration may cause reports to display incorrectly</span></span>

<span data-ttu-id="fa174-143">如果開啟 Internet Explorer 增強的安全性設定（ESC），當您嘗試在 MBAM 伺服器上查看報告時，可能會出現「拒絕存取」訊息。</span><span class="sxs-lookup"><span data-stu-id="fa174-143">If Internet Explorer Enhanced Security Configuration (ESC) is turned on, an “Access Denied” message might appear when you try to view reports on the MBAM Server.</span></span> <span data-ttu-id="fa174-144">根據預設，ESC 會開啟以保護伺服器，方法是將伺服器暴露在網頁內容和應用程式腳本中可能會發生的可能攻擊。</span><span class="sxs-lookup"><span data-stu-id="fa174-144">By default, ESC is turned on to protect the server by decreasing the server’s exposure to potential attacks that can occur through web content and application scripts.</span></span>

<span data-ttu-id="fa174-145">因應措施：如果在您嘗試在 MBAM 伺服器上查看報告時，出現「拒絕存取」訊息，您可以在影像中設定群組原則物件或手動變更預設值，以停用增強的安全性設定。</span><span class="sxs-lookup"><span data-stu-id="fa174-145">WORKAROUND: If the “Access Denied” message appears when you try to view reports on the MBAM Server, you can set a Group Policy Object or change the default manually in your image to disable Enhanced Security Configuration.</span></span> <span data-ttu-id="fa174-146">您也可以在未啟用 ESC 的另一部電腦上，查看報表。</span><span class="sxs-lookup"><span data-stu-id="fa174-146">You can also alternatively view the reports from another computer on which ESC is not enabled.</span></span>

### <span data-ttu-id="fa174-147">從 SQL Server 2008 升級至 SQL Server 2012 時，MBAM 伺服器安裝失敗</span><span class="sxs-lookup"><span data-stu-id="fa174-147">MBAM Server installation fails when you upgrade from SQL Server 2008 to SQL Server 2012</span></span>

<span data-ttu-id="fa174-148">如果您從 SQL Server 2008 升級至 SQL Server 2012，然後嘗試安裝合規性和審核資料庫或復原資料庫，安裝就會失敗並回滾。</span><span class="sxs-lookup"><span data-stu-id="fa174-148">If you upgrade from SQL Server 2008 to SQL Server 2012, and then try to install the Compliance and Audit Database or the Recovery Database, the installation fails and rolls back.</span></span> <span data-ttu-id="fa174-149">發生失敗的原因是，在 SQL 升級期間已移除所需的 SQLCMD.exe 檔案，且 MBAM 安裝程式無法找到該檔案。</span><span class="sxs-lookup"><span data-stu-id="fa174-149">The failure occurs because the required SQLCMD.exe file was removed during the SQL upgrade and cannot be found by the MBAM installer.</span></span> <span data-ttu-id="fa174-150">MSI 記錄檔行可能看起來類似下列：</span><span class="sxs-lookup"><span data-stu-id="fa174-150">The MSI log file lines may look similar to the following:</span></span>

<span data-ttu-id="fa174-151">RunDbInstallScript 復原資料庫 CA： BinDir-E:\\MSSQL\\100\\Tools\\Binn\\SqlCmd.exeRunDbInstallScript 復原資料庫 CA： dbInstance-xxxxxx\\I01RunDbInstallScript Recovery Db CA： sqlScript-C:\\program files Files\\Microsoft\\Microsoft _HardwareRunDbInstallScript _and _Recovery \ [\ Monitoring\\Setup\\KeyRecovery.sqlRunDbInstallScript db ca： dbName-MBAM \ _Recovery \ _and _HardwareRunDbInstallScript Recovery Db CA： DefaultFileName-MBAMI01\\MSSQL\\DATA\\RunDbInstallScript Recovery Db CA： defaultLogPath-K:\\MSSQL\\MSSQL10。I01\\MSSQL\\Data\\RunDbInstallScript 復原資料庫 CA： scriptLogPath-C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\InstallKeyComplianceDatabase.log-e-E-S xxxxxxx\\I01-i "C:\\program files Files\\Microsoft\\Microsoft BitLocker 管理和 Monitoring\\Setup\\KeyRecovery.sql"-v DatabaseName = "MBAM \ _Recovery \ _and \ _Hardware" DefaultFileName = "MBAM \ _Recovery \ _and \ _Hardware" DefaultDataPath = "F:\\MSSQL\\MSSQL10。I01\\MSSQL\\DATA\\ "DefaultLogPath =" K:\\MSSQL\\MSSQL10。I01\\MSSQL\\Data\\ "-o" C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\InstallKeyComplianceDatabase.log "RunDbInstallScript 復原資料庫 ca：開始執行恢復資料庫的安裝 scriptRunDbInstallScript 復原資料庫 CA： Sqlcmd 記錄檔案位於 C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\\\InstallKeyRecoveryDatabase.logRunDbInstallScript 復原 Db CA 例外狀況：安裝復原資料庫自訂操作命令列輸出例外狀況：系統找不到指定的檔案</span><span class="sxs-lookup"><span data-stu-id="fa174-151">RunDbInstallScript Recovery Db CA: BinDir - E:\\MSSQL\\100\\Tools\\Binn\\SqlCmd.exeRunDbInstallScript Recovery Db CA: dbInstance - xxxxxx\\I01RunDbInstallScript Recovery Db CA: sqlScript- C:\\Program Files\\Microsoft\\Microsoft BitLocker Administration and Monitoring\\Setup\\KeyRecovery.sqlRunDbInstallScript Recovery Db CA: dbName- MBAM\_Recovery\_and\_HardwareRunDbInstallScript Recovery Db CA: defaultFileName- MBAM\_Recovery\_and\_HardwareRunDbInstallScript Recovery Db CA: defaultDataPath- F:\\MSSQL\\MSSQL10.I01\\MSSQL\\DATA\\RunDbInstallScript Recovery Db CA: defaultLogPath- K:\\MSSQL\\MSSQL10.I01\\MSSQL\\Data\\RunDbInstallScript Recovery Db CA: scriptLogPath - C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\InstallKeyComplianceDatabase.log-e -E -S xxxxxxx\\I01 -i "C:\\Program Files\\Microsoft\\Microsoft BitLocker Administration and Monitoring\\Setup\\KeyRecovery.sql" -v DatabaseName="MBAM\_Recovery\_and\_Hardware" DefaultFileName="MBAM\_Recovery\_and\_Hardware" DefaultDataPath="F:\\MSSQL\\MSSQL10.I01\\MSSQL\\DATA\\" DefaultLogPath="K:\\MSSQL\\MSSQL10.I01\\MSSQL\\Data\\" -o "C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\InstallKeyComplianceDatabase.log"RunDbInstallScript Recovery Db CA:Starting to run the Recovery database install scriptRunDbInstallScript Recovery Db CA: Sqlcmd log file is located in C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\\\InstallKeyRecoveryDatabase.logRunDbInstallScript Recovery Db CA Exception: Install Recovery database Custom Action command line output Exception: The system cannot find the file specified</span></span>

<span data-ttu-id="fa174-152">您可以在 [HKLM\\Software\\Microsoft\\Microsoft SQL Server\\100\\Tools\\ClientSetup.] 下的 [登錄] 中查看 [Path 字串] 值，在 MBAM Server Windows 安裝程式上進行硬編碼，以尋找 SQLCMD.exe 路徑。</span><span class="sxs-lookup"><span data-stu-id="fa174-152">The MBAM Server Windows Installer is hardcoded to find the SQLCMD.exe path by looking in the Path string value in the registry under HKLM\\Software\\Microsoft\\Microsoft SQL Server\\100\\Tools\\ClientSetup.</span></span> <span data-ttu-id="fa174-153">在從 SQL Server 2008 遷移至 SQL Server 2012 期間，仍會出現金鑰，但由於 SQL 升級程式已移除檔案，因此資料值所參照的路徑不會包含 SQLCMD.exe 的檔案。</span><span class="sxs-lookup"><span data-stu-id="fa174-153">The key is still present during the migration from SQL Server 2008 to SQL Server 2012, but the path that is referenced by the data value does not contain the SQLCMD.exe file, because the SQL upgrade process removed the file.</span></span>

<span data-ttu-id="fa174-154">因應措施：暫時將 HKLM\\Software\\Microsoft\\Microsoft SQL Server\\100\\Tools\\ClientSetup Path 字串值重新命名為**Path \ _old**，然後重新執行 MBAM Server Windows 安裝程式。</span><span class="sxs-lookup"><span data-stu-id="fa174-154">WORKAROUND: Temporarily rename the HKLM\\Software\\Microsoft\\Microsoft SQL Server\\100\\Tools\\ClientSetup Path string value to **Path\_old**, and then re-run the MBAM Server Windows Installer.</span></span> <span data-ttu-id="fa174-155">成功完成安裝並在 SQL Server 2012 中建立資料庫後，請將**路徑 \ _old**值重新命名為**path**。</span><span class="sxs-lookup"><span data-stu-id="fa174-155">When the installation completes successfully and creates the databases in SQL Server 2012, rename the **Path\_old** value to **Path**.</span></span>

## <span data-ttu-id="fa174-156">MBAM 2.0 的修補程式和知識庫文章</span><span class="sxs-lookup"><span data-stu-id="fa174-156">Hotfixes and Knowledge Base articles for MBAM2.0</span></span>


<span data-ttu-id="fa174-157">本節包含適用于 MBAM 2.0 的修補程式和知識庫文章。</span><span class="sxs-lookup"><span data-stu-id="fa174-157">This section contains hotfixes and KB articles for MBAM2.0.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="fa174-158">知識庫文章</span><span class="sxs-lookup"><span data-stu-id="fa174-158">KB Article</span></span></strong></th>
<th align="left"><span data-ttu-id="fa174-159">Title</span><span class="sxs-lookup"><span data-stu-id="fa174-159">Title</span></span></th>
<th align="left"><strong><span data-ttu-id="fa174-160">連結</span><span class="sxs-lookup"><span data-stu-id="fa174-160">Link</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="fa174-161">2831166</span><span class="sxs-lookup"><span data-stu-id="fa174-161">2831166</span></span></p></td>
<td align="left"><p><span data-ttu-id="fa174-162">安裝 Microsoft BitLocker 管理和監控（MBAM）2.0 失敗， &quot; 已安裝 System CENTER CM 物件&quot;</span><span class="sxs-lookup"><span data-stu-id="fa174-162">Installing Microsoft BitLocker Administration and Monitoring (MBAM) 2.0 fails with &quot;System Center CM Objects Already Installed&quot;</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2831166/EN-US" data-raw-source="[support.microsoft.com/kb/2831166/EN-US](https://support.microsoft.com/kb/2831166/EN-US)"><span data-ttu-id="fa174-163">support.microsoft.com/kb/2831166/EN-US</span><span class="sxs-lookup"><span data-stu-id="fa174-163">support.microsoft.com/kb/2831166/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="fa174-164">2870849</span><span class="sxs-lookup"><span data-stu-id="fa174-164">2870849</span></span></p></td>
<td align="left"><p><span data-ttu-id="fa174-165">使用者無法使用 MBAM 2.0 自助服務入口網站來取得 BitLocker 復原金鑰</span><span class="sxs-lookup"><span data-stu-id="fa174-165">Users cannot retrieve BitLocker Recovery key using MBAM2.0 Self Service Portal</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870849/EN-US" data-raw-source="[support.microsoft.com/kb/2870849/EN-US](https://support.microsoft.com/kb/2870849/EN-US)"><span data-ttu-id="fa174-166">support.microsoft.com/kb/2870849/EN-US</span><span class="sxs-lookup"><span data-stu-id="fa174-166">support.microsoft.com/kb/2870849/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="fa174-167">2756402</span><span class="sxs-lookup"><span data-stu-id="fa174-167">2756402</span></span></p></td>
<td align="left"><p><span data-ttu-id="fa174-168">事件描述中的 MBAM 用戶端將無法使用事件 ID 4 和錯誤碼0x8004100E</span><span class="sxs-lookup"><span data-stu-id="fa174-168">MBAM client would fail with Event ID 4 and error code 0x8004100E in the Event description</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2756402/EN-US" data-raw-source="[support.microsoft.com/kb/2756402/EN-US](https://support.microsoft.com/kb/2756402/EN-US)"><span data-ttu-id="fa174-169">support.microsoft.com/kb/2756402/EN-US</span><span class="sxs-lookup"><span data-stu-id="fa174-169">support.microsoft.com/kb/2756402/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="fa174-170">2620287</span><span class="sxs-lookup"><span data-stu-id="fa174-170">2620287</span></span></p></td>
<td align="left"><p><span data-ttu-id="fa174-171">按一下 MBAM 中的 [報表] 索引標籤時，出現「/Reports ' 應用程式」的 [伺服器錯誤] 錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="fa174-171">Error Message “Server Error in ‘/Reports’ Application” When You Click Reports Tab in MBAM</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2620287/EN-US" data-raw-source="[support.microsoft.com/kb/2620287/EN-US](https://support.microsoft.com/kb/2620287/EN-US)"><span data-ttu-id="fa174-172">support.microsoft.com/kb/2620287/EN-US</span><span class="sxs-lookup"><span data-stu-id="fa174-172">support.microsoft.com/kb/2620287/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="fa174-173">2639518</span><span class="sxs-lookup"><span data-stu-id="fa174-173">2639518</span></span></p></td>
<td align="left"><p><span data-ttu-id="fa174-174">在 MBAM 中開啟企業或電腦合規性報告時發生錯誤</span><span class="sxs-lookup"><span data-stu-id="fa174-174">Error opening Enterprise or Computer Compliance Reports in MBAM</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2639518/EN-US" data-raw-source="[support.microsoft.com/kb/2639518/EN-US](https://support.microsoft.com/kb/2639518/EN-US)"><span data-ttu-id="fa174-175">support.microsoft.com/kb/2639518/EN-US</span><span class="sxs-lookup"><span data-stu-id="fa174-175">support.microsoft.com/kb/2639518/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="fa174-176">2620269</span><span class="sxs-lookup"><span data-stu-id="fa174-176">2620269</span></span></p></td>
<td align="left"><p><span data-ttu-id="fa174-177">MBAM 企業報告無法取得更新</span><span class="sxs-lookup"><span data-stu-id="fa174-177">MBAM Enterprise Reporting Not Getting Updated</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2620269/EN-US" data-raw-source="[support.microsoft.com/kb/2620269/EN-US](https://support.microsoft.com/kb/2620269/EN-US)"><span data-ttu-id="fa174-178">support.microsoft.com/kb/2620269/EN-US</span><span class="sxs-lookup"><span data-stu-id="fa174-178">support.microsoft.com/kb/2620269/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="fa174-179">2712461</span><span class="sxs-lookup"><span data-stu-id="fa174-179">2712461</span></span></p></td>
<td align="left"><p><span data-ttu-id="fa174-180">不支援在網網域控制站上安裝 MBAM</span><span class="sxs-lookup"><span data-stu-id="fa174-180">Installing MBAM on a Domain Controller is not supported</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2712461/EN-US" data-raw-source="[support.microsoft.com/kb/2712461/EN-US](https://support.microsoft.com/kb/2712461/EN-US)"><span data-ttu-id="fa174-181">support.microsoft.com/kb/2712461/EN-US</span><span class="sxs-lookup"><span data-stu-id="fa174-181">support.microsoft.com/kb/2712461/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="fa174-182">2876732</span><span class="sxs-lookup"><span data-stu-id="fa174-182">2876732</span></span></p></td>
<td align="left"><p><span data-ttu-id="fa174-183">您在獨立或 Configuration Manager 集成設定 MBAM 2.0 期間收到錯誤代碼0x80071a90</span><span class="sxs-lookup"><span data-stu-id="fa174-183">You receive error code 0x80071a90 during Standalone or Configuration Manager Integration setup of MBAM2.0</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2876732/EN-US" data-raw-source="[support.microsoft.com/kb/2876732/EN-US](https://support.microsoft.com/kb/2876732/EN-US)"><span data-ttu-id="fa174-184">support.microsoft.com/kb/2876732/EN-US</span><span class="sxs-lookup"><span data-stu-id="fa174-184">support.microsoft.com/kb/2876732/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="fa174-185">2754259</span><span class="sxs-lookup"><span data-stu-id="fa174-185">2754259</span></span></p></td>
<td align="left"><p><span data-ttu-id="fa174-186">MBAM 及安全的網路通訊</span><span class="sxs-lookup"><span data-stu-id="fa174-186">MBAM and Secure Network Communication</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2754259/EN-US" data-raw-source="[support.microsoft.com/kb/2754259/EN-US](https://support.microsoft.com/kb/2754259/EN-US)"><span data-ttu-id="fa174-187">support.microsoft.com/kb/2754259/EN-US</span><span class="sxs-lookup"><span data-stu-id="fa174-187">support.microsoft.com/kb/2754259/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="fa174-188">2870842</span><span class="sxs-lookup"><span data-stu-id="fa174-188">2870842</span></span></p></td>
<td align="left"><p><span data-ttu-id="fa174-189">MBAM 2.0 安裝程式在 Configuration Manager 整合案例中使用 SQL Server 2008 失敗</span><span class="sxs-lookup"><span data-stu-id="fa174-189">MBAM2.0 Setup fails during Configuration Manager Integration Scenario with SQL Server 2008</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870842/EN-US" data-raw-source="[support.microsoft.com/kb/2870842/EN-US](https://support.microsoft.com/kb/2870842/EN-US)"><span data-ttu-id="fa174-190">support.microsoft.com/kb/2870842/EN-US</span><span class="sxs-lookup"><span data-stu-id="fa174-190">support.microsoft.com/kb/2870842/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="fa174-191">2668533</span><span class="sxs-lookup"><span data-stu-id="fa174-191">2668533</span></span></p></td>
<td align="left"><p><span data-ttu-id="fa174-192">如果未正確設定 SQL SSRS，則 MBAM 安裝程式會失敗</span><span class="sxs-lookup"><span data-stu-id="fa174-192">MBAM Setup fails if SQL SSRS is not configured properly</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2668533/EN-US" data-raw-source="[support.microsoft.com/kb/2668533/EN-US](https://support.microsoft.com/kb/2668533/EN-US)"><span data-ttu-id="fa174-193">support.microsoft.com/kb/2668533/EN-US</span><span class="sxs-lookup"><span data-stu-id="fa174-193">support.microsoft.com/kb/2668533/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="fa174-194">2870847</span><span class="sxs-lookup"><span data-stu-id="fa174-194">2870847</span></span></p></td>
<td align="left"><p><span data-ttu-id="fa174-195">MBAM 2.0 安裝失敗， &quot; 檢索 &#39;Reporting Services Point&#39; 角色的 Configuration Manager 伺服器角色設定時發生錯誤&quot;</span><span class="sxs-lookup"><span data-stu-id="fa174-195">MBAM 2.0 Setup fails with &quot;Error retrieving Configuration Manager Server role settings for &#39;Reporting Services Point&#39; role&quot;</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870847/EN-US" data-raw-source="[support.microsoft.com/kb/2870847/EN-US](https://support.microsoft.com/kb/2870847/EN-US)"><span data-ttu-id="fa174-196">support.microsoft.com/kb/2870847/EN-US</span><span class="sxs-lookup"><span data-stu-id="fa174-196">support.microsoft.com/kb/2870847/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="fa174-197">2870839</span><span class="sxs-lookup"><span data-stu-id="fa174-197">2870839</span></span></p></td>
<td align="left"><p><span data-ttu-id="fa174-198">由於 SQL 作業 CreateCache 失敗，所以無法在 MBAM 2.0 獨立拓朴中重新整理 MBAM 2.0 企業報告</span><span class="sxs-lookup"><span data-stu-id="fa174-198">MBAM2.0 Enterprise Reports are not refreshed in MBAM2.0 Standalone topology due to SQL job CreateCache failure</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870839/EN-US" data-raw-source="[support.microsoft.com/kb/2870839/EN-US](https://support.microsoft.com/kb/2870839/EN-US)"><span data-ttu-id="fa174-199">support.microsoft.com/kb/2870839/EN-US</span><span class="sxs-lookup"><span data-stu-id="fa174-199">support.microsoft.com/kb/2870839/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="fa174-200">2620269</span><span class="sxs-lookup"><span data-stu-id="fa174-200">2620269</span></span></p></td>
<td align="left"><p><span data-ttu-id="fa174-201">MBAM 企業報告無法取得更新</span><span class="sxs-lookup"><span data-stu-id="fa174-201">MBAM Enterprise Reporting Not Getting Updated</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2620269/EN-US" data-raw-source="[support.microsoft.com/kb/2620269/EN-US](https://support.microsoft.com/kb/2620269/EN-US)"><span data-ttu-id="fa174-202">support.microsoft.com/kb/2620269/EN-US</span><span class="sxs-lookup"><span data-stu-id="fa174-202">support.microsoft.com/kb/2620269/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="fa174-203">2935997</span><span class="sxs-lookup"><span data-stu-id="fa174-203">2935997</span></span></p></td>
<td align="left"><p><span data-ttu-id="fa174-204">MBAM 支援的電腦合規性報告不正確包含不支援的產品</span><span class="sxs-lookup"><span data-stu-id="fa174-204">MBAM Supported Computers compliance reporting incorrectly includes unsupported products</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2935997/EN-US" data-raw-source="[support.microsoft.com/kb/2935997/EN-US](https://support.microsoft.com/kb/2935997/EN-US)"><span data-ttu-id="fa174-205">support.microsoft.com/kb/2935997/EN-US</span><span class="sxs-lookup"><span data-stu-id="fa174-205">support.microsoft.com/kb/2935997/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="fa174-206">2612822</span><span class="sxs-lookup"><span data-stu-id="fa174-206">2612822</span></span></p></td>
<td align="left"><p><span data-ttu-id="fa174-207">在 MBAM 中，電腦記錄遭到拒絕</span><span class="sxs-lookup"><span data-stu-id="fa174-207">Computer Record is Rejected in MBAM</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2612822/EN-US" data-raw-source="[support.microsoft.com/kb/2612822/EN-US](https://support.microsoft.com/kb/2612822/EN-US)"><span data-ttu-id="fa174-208">support.microsoft.com/kb/2612822/EN-US</span><span class="sxs-lookup"><span data-stu-id="fa174-208">support.microsoft.com/kb/2612822/EN-US</span></span></a></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="fa174-209">相關主題</span><span class="sxs-lookup"><span data-stu-id="fa174-209">Related topics</span></span>


[<span data-ttu-id="fa174-210">關於 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="fa174-210">About MBAM 2.0</span></span>](about-mbam-20-mbam-2.md)

 

 





