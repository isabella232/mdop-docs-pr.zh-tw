---
title: 如何移動 MBAM 2.5 資料庫
description: 如何移動 MBAM 2.5 資料庫
author: dansimp
ms.assetid: 34b46f2d-0add-4377-8e4e-04b628fdfcf1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/15/2018
ms.openlocfilehash: 63c509e7ae1460ece815ef6c0a22350f76b52018
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800084"
---
# <span data-ttu-id="292db-103">如何移動 MBAM 2.5 資料庫</span><span class="sxs-lookup"><span data-stu-id="292db-103">How to Move the MBAM 2.5 Databases</span></span>

<span data-ttu-id="292db-104">使用這些程式將下列資料庫從一部電腦移到另一部電腦;從伺服器 A 到伺服器 B，例如：</span><span class="sxs-lookup"><span data-stu-id="292db-104">Use these procedures to move the following databases from one computer to another; from Server A to Server B, for example:</span></span>

-   <span data-ttu-id="292db-105">合規性和審核資料庫</span><span class="sxs-lookup"><span data-stu-id="292db-105">Compliance and Audit Database</span></span>

-   <span data-ttu-id="292db-106">復原資料庫</span><span class="sxs-lookup"><span data-stu-id="292db-106">Recovery Database</span></span>

>[!NOTE]
><span data-ttu-id="292db-107">請務必先將資料庫還原到電腦 B，然後再執行 MBAM 設定向導來更新/設定。</span><span class="sxs-lookup"><span data-stu-id="292db-107">It is important that the databases be restored to Machine B PRIOR to running the MBAM Configuration Wizard to update/configure them.</span></span>

<span data-ttu-id="292db-108">如果資料庫不存在，則 [設定] 嚮導會建立新的、空的資料庫。</span><span class="sxs-lookup"><span data-stu-id="292db-108">If the databases are NOT present, the Configuration Wizard creates NEW, empty, databases.</span></span> <span data-ttu-id="292db-109">當您的現有資料庫已還原之後，此程式會中斷 MBAM 設定。</span><span class="sxs-lookup"><span data-stu-id="292db-109">When your existing databases are then restored, this process will break the MBAM configuration.</span></span>

<span data-ttu-id="292db-110">首先還原資料庫，然後執行 [MBAM 設定] 嚮導，選擇 [資料庫] 選項，[設定] 嚮導會將 [連線] 到您還原的資料庫;如有需要，請在程式中進行升級。</span><span class="sxs-lookup"><span data-stu-id="292db-110">Restore the databases FIRST, then run the MBAM Configuration Wizard, choose the database option, and the Configuration Wizard will “connect” to the databases you restored; upgrading them if needed as part of the process.</span></span>

**<span data-ttu-id="292db-111">如果您要移動多個功能，請以下列順序移動它們：</span><span class="sxs-lookup"><span data-stu-id="292db-111">If you are moving multiple features, move them in the following order:</span></span>**

1.  <span data-ttu-id="292db-112">復原資料庫</span><span class="sxs-lookup"><span data-stu-id="292db-112">Recovery Database</span></span>

2.  <span data-ttu-id="292db-113">合規性和審核資料庫</span><span class="sxs-lookup"><span data-stu-id="292db-113">Compliance and Audit Database</span></span>

3.  <span data-ttu-id="292db-114">報告</span><span class="sxs-lookup"><span data-stu-id="292db-114">Reports</span></span>

4.  <span data-ttu-id="292db-115">管理和監控網站</span><span class="sxs-lookup"><span data-stu-id="292db-115">Administration and Monitoring Website</span></span>

5.  <span data-ttu-id="292db-116">自助服務入口網站</span><span class="sxs-lookup"><span data-stu-id="292db-116">Self-Service Portal</span></span>

>[!Note]
><span data-ttu-id="292db-117">若要執行本主題中提供的 Windows PowerShell 腳本範例，您必須更新 Windows PowerShell 執行原則，才能執行腳本。</span><span class="sxs-lookup"><span data-stu-id="292db-117">To run the example Windows PowerShell scripts provided in this topic, you must update the Windows PowerShell execution policy to enable scripts to be run.</span></span> <span data-ttu-id="292db-118">請參閱執行[Windows PowerShell 腳本](https://technet.microsoft.com/library/ee176949.aspx)以取得相關指示。</span><span class="sxs-lookup"><span data-stu-id="292db-118">See [Running Windows PowerShell Scripts](https://technet.microsoft.com/library/ee176949.aspx) for instructions.</span></span>

## <span data-ttu-id="292db-119">移動恢復資料庫</span><span class="sxs-lookup"><span data-stu-id="292db-119">Move the Recovery Database</span></span>

<span data-ttu-id="292db-120">移動恢復資料庫的高層步驟如下：</span><span class="sxs-lookup"><span data-stu-id="292db-120">The high-level steps for moving the Recovery Database are:</span></span>

1.  <span data-ttu-id="292db-121">停止 MBAM 管理和監視網站的所有實例</span><span class="sxs-lookup"><span data-stu-id="292db-121">Stop all instances of the MBAM Administration and Monitoring Website</span></span>

2.  <span data-ttu-id="292db-122">在伺服器 A 上備份恢復資料庫</span><span class="sxs-lookup"><span data-stu-id="292db-122">Back up the Recovery Database on Server A</span></span>

3.  <span data-ttu-id="292db-123">將恢復資料庫從伺服器 A 移至伺服器 B</span><span class="sxs-lookup"><span data-stu-id="292db-123">Move the Recovery Database from Server A to Server B</span></span>

4.  <span data-ttu-id="292db-124">在伺服器 B 上還原恢復資料庫</span><span class="sxs-lookup"><span data-stu-id="292db-124">Restore the Recovery Database on Server B</span></span>

5.  <span data-ttu-id="292db-125">在伺服器 B 上設定對資料庫的存取權並更新連接資料</span><span class="sxs-lookup"><span data-stu-id="292db-125">Configure access to the Database on Server B and update connection data</span></span>

6.  <span data-ttu-id="292db-126">在伺服器 B 上安裝 MBAM Server 軟體並執行 [MBAM 伺服器設定] 嚮導</span><span class="sxs-lookup"><span data-stu-id="292db-126">Install MBAM Server software and run the MBAM Server Configuration wizard on Server B</span></span>

7.  <span data-ttu-id="292db-127">繼續管理和監控網站的實例</span><span class="sxs-lookup"><span data-stu-id="292db-127">Resume the instance of the Administration and Monitoring Website</span></span>

### <span data-ttu-id="292db-128">如何移動恢復資料庫</span><span class="sxs-lookup"><span data-stu-id="292db-128">How to move the Recovery Database</span></span>

**<span data-ttu-id="292db-129">停止 MBAM 管理和監視網站的所有實例。</span><span class="sxs-lookup"><span data-stu-id="292db-129">Stop all instances of the MBAM Administration and Monitoring Website.</span></span>** <span data-ttu-id="292db-130">在執行 MBAM 管理和監視伺服器網站的每個伺服器上，使用 [網際網路資訊服務（IIS）管理員] 主控台來停止 [管理及監視] 網站。</span><span class="sxs-lookup"><span data-stu-id="292db-130">On each server that is running the MBAM Administration and Monitoring Server Website, use the Internet Information Services (IIS) Manager console to stop the Administration and Monitoring Website.</span></span>

<span data-ttu-id="292db-131">若要自動化此程式，您可以使用 Windows PowerShell 輸入類似以下的命令：</span><span class="sxs-lookup"><span data-stu-id="292db-131">To automate this procedure, you can use Windows PowerShell to enter a command that is similar to the following:</span></span>

```powershell
Stop-Website "Microsoft BitLocker Administration and Monitoring"
```

>[!NOTE]
><span data-ttu-id="292db-132">若要執行此命令，您必須將適用于 Windows PowerShell 的 Internet Information Services （IIS）模組新增到目前的 Windows PowerShell 實例。</span><span class="sxs-lookup"><span data-stu-id="292db-132">To run this command, you must add the Internet Information Services (IIS) module for Windows PowerShell to the current instance of Windows PowerShell.</span></span>

### <span data-ttu-id="292db-133">在伺服器 A 上備份恢復資料庫</span><span class="sxs-lookup"><span data-stu-id="292db-133">Back up the Recovery Database on Server A</span></span>

1.  <span data-ttu-id="292db-134">使用 SQL Server Management Studio 中的 [**備份**] 工作來備份伺服器 A 上的 [恢復] 資料庫。 根據預設，資料庫名稱是 MBAM 的 [**恢復資料庫**]。</span><span class="sxs-lookup"><span data-stu-id="292db-134">Use the **Back Up** task in SQL Server Management Studio to back up the Recovery Database on Server A.  By default, the database name is **MBAM Recovery Database**.</span></span>

2.  <span data-ttu-id="292db-135">若要自動化此程式，請建立包含下列 SQL 腳本的 SQL 檔案（.sql），並將 MBAM 復原資料庫變更為使用完整復原模式：</span><span class="sxs-lookup"><span data-stu-id="292db-135">To automate this procedure, create a SQL file (.sql) that contains the following SQL script, and change the MBAM Recovery Database to use the full recovery mode:</span></span>

    ```
    USE master;

    GO

    ALTER DATABASE "MBAM Recovery and Hardware"

    SET RECOVERY FULL;

    GO

    -- Create MBAM Recovery Database Data and MBAM Recovery logical backup devices.

    USE master

    GO

    EXEC sp_addumpdevice 'disk', 'MBAM Recovery and Hardware Database Data Device',

    'Z:\MBAM Recovery Database Data.bak';

    GO

    -- Back up the full MBAM Recovery Database.

    BACKUP DATABASE [MBAM Recovery and Hardware] TO [MBAM Recovery and Hardware Database Data Device];

    GO

    BACKUP CERTIFICATE [MBAM Recovery Encryption Certificate]

    TO FILE = 'Z:\SQLServerInstanceCertificateFile'

    WITH PRIVATE KEY

    (

    FILE = ' Z:\SQLServerInstanceCertificateFilePrivateKey',

    ENCRYPTION BY PASSWORD = '$PASSWORD$'

    );

    GO
    ```

3.  <span data-ttu-id="292db-136">使用下列值，以與您的環境相符的值來取代程式碼範例中的值：</span><span class="sxs-lookup"><span data-stu-id="292db-136">Use the following value to replace the values in the code example with values that match your environment:</span></span>

    <span data-ttu-id="292db-137">**$PASSWORD $** -用來加密私密金鑰檔案的密碼。</span><span class="sxs-lookup"><span data-stu-id="292db-137">**$PASSWORD$** - password that you use to encrypt the Private Key file.</span></span>

4.  <span data-ttu-id="292db-138">在 Windows PowerShell 中，執行儲存在檔案中的腳本，並類似以下所示：</span><span class="sxs-lookup"><span data-stu-id="292db-138">In Windows PowerShell, run the script that is stored in the file and similar to the following:</span></span>

    ```powershell
    Invoke-Sqlcmd -InputFile
    'Z:\BackupMBAMRecoveryandHardwarDatabaseScript.sql' -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$
    ```
5.  <span data-ttu-id="292db-139">使用下列值，以與您的環境相符的值來取代程式碼範例中的值：</span><span class="sxs-lookup"><span data-stu-id="292db-139">Use the following value to replace the values in the code example with values that match your environment:</span></span>

    <span data-ttu-id="292db-140">**$SERVERNAME $ \ $SQLINSTANCENAME $** -伺服器名稱和實例，將從它備份恢復資料庫。</span><span class="sxs-lookup"><span data-stu-id="292db-140">**$SERVERNAME$\$SQLINSTANCENAME$** - server name and instance from which the Recovery Database will be backed up.</span></span>

### <span data-ttu-id="292db-141">將恢復資料庫從伺服器 A 移至伺服器 B</span><span class="sxs-lookup"><span data-stu-id="292db-141">Move the Recovery Database from Server A to Server B</span></span>

<span data-ttu-id="292db-142">使用 Windows 資源管理器，將來自伺服器 A 的**MBAM 復原資料庫資料 .bak**檔案從伺服器 a 移至伺服器 B。</span><span class="sxs-lookup"><span data-stu-id="292db-142">Use Windows Explorer to move the **MBAM Recovery Database Data.bak** file from Server A to Server B.</span></span>

<span data-ttu-id="292db-143">若要自動化此程式，您可以使用 Windows PowerShell 來執行類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="292db-143">To automate this procedure, you can use Windows PowerShell to run a command that is similar to the following:</span></span>

```powershell
Copy-Item "Z:\MBAM Recovery Database Data.bak"
\\$SERVERNAME$\$DESTINATIONSHARE$

Copy-Item "Z:\SQLServerInstanceCertificateFile"
\\$SERVERNAME$\$DESTINATIONSHARE$

Copy-Item "Z:\SQLServerInstanceCertificateFilePrivateKey"
\\$SERVERNAME$\$DESTINATIONSHARE$
```
<span data-ttu-id="292db-144">您可以使用下表中的資訊，以與您的環境相符的值來取代程式碼範例中的值。</span><span class="sxs-lookup"><span data-stu-id="292db-144">Use the information in the following table to replace the values in the code example with values that match your environment.</span></span>

| **<span data-ttu-id="292db-145">參數</span><span class="sxs-lookup"><span data-stu-id="292db-145">Parameter</span></span>**        | **<span data-ttu-id="292db-146">描述</span><span class="sxs-lookup"><span data-stu-id="292db-146">Description</span></span>**  |
|----------------------|------------------|
| <span data-ttu-id="292db-147">$SERVERNAME $</span><span class="sxs-lookup"><span data-stu-id="292db-147">$SERVERNAME$</span></span>       | <span data-ttu-id="292db-148">要將檔案複製到其中的伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="292db-148">Name of the server to which the files will be copied.</span></span> |
| <span data-ttu-id="292db-149">$DESTINATIONSHARE $</span><span class="sxs-lookup"><span data-stu-id="292db-149">$DESTINATIONSHARE$</span></span> | <span data-ttu-id="292db-150">要將檔案複製到其中的共用和路徑的名稱。</span><span class="sxs-lookup"><span data-stu-id="292db-150">Name of the share and path to which the files will be copied.</span></span> |


### <span data-ttu-id="292db-151">在伺服器 B 上還原恢復資料庫</span><span class="sxs-lookup"><span data-stu-id="292db-151">Restore the Recovery Database on Server B</span></span>

1.  <span data-ttu-id="292db-152">使用 SQL Server Management Studio 中的 [**還原資料庫**工作]，還原伺服器 B 上的復原資料庫。</span><span class="sxs-lookup"><span data-stu-id="292db-152">Restore the Recovery Database on Server B by using the **Restore Database** task in SQL Server Management Studio.</span></span>

2.  <span data-ttu-id="292db-153">在前一個工作完成時，請選取 [**從裝置**]，然後選取資料庫備份檔案。</span><span class="sxs-lookup"><span data-stu-id="292db-153">When the previous task finishes, select **From Device**, and then select the database backup file.</span></span>

3.  <span data-ttu-id="292db-154">使用 [ **Add** ] （新增）命令選取**MBAM 復原資料庫資料 .bak**盤案，然後按一下 **[確定]** 以完成還原程式。</span><span class="sxs-lookup"><span data-stu-id="292db-154">Use the **Add** command to select the **MBAM Recovery Database Data.bak** file, and click **OK** to complete the restoration process.</span></span>

4.  <span data-ttu-id="292db-155">若要自動化此程式，請建立包含下列 SQL 腳本的 SQL 檔案（.sql）：</span><span class="sxs-lookup"><span data-stu-id="292db-155">To automate this procedure, create a SQL file (.sql) that contains the following SQL script:</span></span>

    ```
    -- Restore MBAM Recovery Database.

    USE master

    GO

    -- Drop certificate created by MBAM Setup.

    DROP CERTIFICATE [MBAM Recovery Encryption Certificate]

    GO

    --Add certificate

    CREATE CERTIFICATE [MBAM Recovery Encryption Certificate]

    FROM FILE = 'Z:\SQLServerInstanceCertificateFile'

    WITH PRIVATE KEY

    (

    FILE = ' Z:\SQLServerInstanceCertificateFilePrivateKey',

    DECRYPTION BY PASSWORD = '$PASSWORD$'

    );

    GO

    -- Restore the MBAM Recovery Database data and log files.

    RESTORE DATABASE [MBAM Recovery and Hardware]

    FROM DISK = 'Z:\MBAM Recovery Database Data.bak'

    WITH REPLACE
    ```

5.  <span data-ttu-id="292db-156">使用下列值，以與您的環境相符的值來取代程式碼範例中的值。</span><span class="sxs-lookup"><span data-stu-id="292db-156">Use the following value to replace the values in the code example with values that match your environment.</span></span>

    <span data-ttu-id="292db-157">**$PASSWORD $** -您用來加密私密金鑰檔案的密碼。</span><span class="sxs-lookup"><span data-stu-id="292db-157">**$PASSWORD$** - password that you used to encrypt the Private Key file.</span></span>

6.  <span data-ttu-id="292db-158">在 Windows PowerShell 中，執行儲存在檔案中的腳本，並類似以下所示：</span><span class="sxs-lookup"><span data-stu-id="292db-158">In Windows PowerShell, run the script that is stored in the file and similar to the following:</span></span>

    ```powershell
    Invoke-Sqlcmd -InputFile 'Z:\RestoreMBAMRecoveryandHardwarDatabaseScript.sql' -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$
    ```
7.  <span data-ttu-id="292db-159">使用下列值，以與您的環境相符的值來取代程式碼範例中的值。</span><span class="sxs-lookup"><span data-stu-id="292db-159">Use the following value to replace the values in the code example with values that match your environment.</span></span>

    <span data-ttu-id="292db-160">**$SERVERNAME $ \ $SQLINSTANCENAME $** -要還原恢復資料庫的伺服器名稱和實例。</span><span class="sxs-lookup"><span data-stu-id="292db-160">**$SERVERNAME$\$SQLINSTANCENAME$** - Server name and instance to which the Recovery Database will be restored.</span></span>

### <span data-ttu-id="292db-161">在伺服器 B 上設定對資料庫的存取權並更新連接資料</span><span class="sxs-lookup"><span data-stu-id="292db-161">Configure access to the Database on Server B and update connection data</span></span>

1. <span data-ttu-id="292db-162">確認在已還原的資料庫上啟用 [恢復資料庫存取] 的 Microsoft SQL Server 使用者登錄已對應至您在設定程式期間提供的 access 帳戶。</span><span class="sxs-lookup"><span data-stu-id="292db-162">Verify that the Microsoft SQL Server user login that enables Recovery Database access on the restored database is mapped to the access account that you provided during the configuration process.</span></span>

   >[!NOTE]
   ><span data-ttu-id="292db-163">如果登入不相同，請使用 SQL Server Management Studio 建立登入，然後將它對應至現有的資料庫使用者。</span><span class="sxs-lookup"><span data-stu-id="292db-163">If the login is not the same, create a login by using SQL Server Management Studio, and map it to the existing database user.</span></span>

2. <span data-ttu-id="292db-164">在執行管理和監視網站的伺服器上，使用 Internet Information Services （IIS）管理員主控台來更新 MBAM 網站的連線字串資訊。</span><span class="sxs-lookup"><span data-stu-id="292db-164">On the server that is running the Administration and Monitoring Website, use the Internet Information Services (IIS) Manager console to update the connection string information for the MBAM websites.</span></span>

3. <span data-ttu-id="292db-165">編輯下列登錄機碼：</span><span class="sxs-lookup"><span data-stu-id="292db-165">Edit the following registry key:</span></span>

   **<span data-ttu-id="292db-166">HKLM\\Software\\Microsoft\\MBAM Server\\Web\\RecoveryDBConnectionString</span><span class="sxs-lookup"><span data-stu-id="292db-166">HKLM\\Software\\Microsoft\\MBAM Server\\Web\\RecoveryDBConnectionString</span></span>**

4. <span data-ttu-id="292db-167">使用伺服器和實例的名稱（例如，\ $SERVERNAME \ $ \\ $SQLINSTANCENAME）來更新已移動復原資料庫的**資料來源**值。</span><span class="sxs-lookup"><span data-stu-id="292db-167">Update the **Data Source** value with the name of the server and instance (for example, \$SERVERNAME\$\\\$SQLINSTANCENAME) to which the Recovery Database was moved.</span></span>

5. <span data-ttu-id="292db-168">使用已復原的資料庫名稱來更新**初始目錄**值。</span><span class="sxs-lookup"><span data-stu-id="292db-168">Update the **Initial Catalog** value with the recovered database name.</span></span>

6. <span data-ttu-id="292db-169">若要自動化此程式，您可以使用 Windows PowerShell 命令提示字元，在 [管理與監視伺服器] 上輸入如下所示的命令列：</span><span class="sxs-lookup"><span data-stu-id="292db-169">To automate this process, you can use the Windows PowerShell command prompt to enter a command line on the Administration and Monitoring Server that is similar to the following:</span></span>

   ```powershell
   reg add "HKEY_LOCAL_MACHINE\SOFTWARE\\Microsoft\MBAM Server\\Web" /v
   RecoveryDBConnectionString /t REG_SZ /d "Integrated Security=SSPI;Initial
   Catalog=$DATABASE$;Data Source=$SERVERNAME$\$SQLINSTANCENAME$" /f

   Set-WebConfigurationProperty
   'connectionStrings/add[@name="KeyRecoveryConnectionString"]' -PSPath
   "IIS:\sites\Microsoft Bitlocker Administration and
   Monitoring\MBAMAdministrationService" -Name "connectionString" -Value "Data
   Source=$SERVERNAME$\$SQLINSTANCENAME$;Initial Catalog=MBAM Recovery and
   Hardware;Integrated Security=SSPI;"

   Set-WebConfigurationProperty
   'connectionStrings/add[\@name="Microsoft.Mbam.RecoveryAndHardwareDataStore.ConnectionString"]'
   -PSPath "IIS:\sites\Microsoft Bitlocker Administration and
   Monitoring\MBAMRecoveryAndHardwareService" -Name "connectionString" -Value
   "Data Source=$SERVERNAME$\$SQLINSTANCENAME$;Initial Catalog=MBAM Recovery
   and Hardware;Integrated Security=SSPI;"
   ```

   >[!Note]
   ><span data-ttu-id="292db-170">這個連線字串是由所有本機 MBAM web 應用程式所共用。</span><span class="sxs-lookup"><span data-stu-id="292db-170">This connection string is shared by all local MBAM web applications.</span></span> <span data-ttu-id="292db-171">因此，每個伺服器只需要更新一次。</span><span class="sxs-lookup"><span data-stu-id="292db-171">Therefore, it needs to be updated only once per server.</span></span>


7. <span data-ttu-id="292db-172">使用下表，以與您的環境相符的值來取代程式碼範例中的值。</span><span class="sxs-lookup"><span data-stu-id="292db-172">Use the following table to replace the values in the code example with values that match your environment.</span></span>

   |<span data-ttu-id="292db-173">參數</span><span class="sxs-lookup"><span data-stu-id="292db-173">Parameter</span></span>|<span data-ttu-id="292db-174">描述</span><span class="sxs-lookup"><span data-stu-id="292db-174">Description</span></span>|
   |---------|-----------|
   |<span data-ttu-id="292db-175">$SERVERNAME $/\ $SQLINSTANCENAME $</span><span class="sxs-lookup"><span data-stu-id="292db-175">$SERVERNAME$/\$SQLINSTANCENAME$</span></span>|<span data-ttu-id="292db-176">恢復資料庫所在之 SQL Server 的伺服器名稱和實例。</span><span class="sxs-lookup"><span data-stu-id="292db-176">Server name and instance of SQL Server where the Recovery Database is located.</span></span>|
   |<span data-ttu-id="292db-177">$DATABASE $</span><span class="sxs-lookup"><span data-stu-id="292db-177">$DATABASE$</span></span>|<span data-ttu-id="292db-178">恢復資料庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="292db-178">Name of the Recovery database.</span></span>|


### <span data-ttu-id="292db-179">在伺服器 B 上安裝 MBAM Server 軟體並執行 [MBAM 伺服器設定] 嚮導</span><span class="sxs-lookup"><span data-stu-id="292db-179">Install MBAM Server software and run the MBAM Server Configuration wizard on Server B</span></span>

1.  <span data-ttu-id="292db-180">在伺服器 B 上安裝 MBAM 2.5 Server 軟體。如需詳細資訊，請參閱[安裝 MBAM 2.5 Server 軟體](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/installing-the-mbam-25-server-software)。</span><span class="sxs-lookup"><span data-stu-id="292db-180">Install the MBAM 2.5 Server software on Server B. For details, see [Installing the MBAM 2.5 Server Software](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/installing-the-mbam-25-server-software).</span></span>

2.  <span data-ttu-id="292db-181">在伺服器 B 上，啟動 [MBAM 伺服器設定向導]，按一下 [新增**功能**]，然後只選取 [**恢復資料庫**] 功能。</span><span class="sxs-lookup"><span data-stu-id="292db-181">On Server B, start the MBAM Server Configuration wizard, click **Add New Features**, and then select only the **Recovery Database** feature.</span></span> <span data-ttu-id="292db-182">如需如何設定資料庫的詳細資訊，請參閱[如何設定 MBAM 2.5 資料庫](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-configure-the-mbam-25-databases)。</span><span class="sxs-lookup"><span data-stu-id="292db-182">For details on how to configure the databases, see [How to Configure the MBAM 2.5 Databases](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-configure-the-mbam-25-databases).</span></span>

    >[!TIP]
    ><span data-ttu-id="292db-183">或者，您也可以使用**Enable-MbamDatabase** Windows PowerShell Cmdlet 來設定恢復資料庫。</span><span class="sxs-lookup"><span data-stu-id="292db-183">Alternatively, you can use the **Enable-MbamDatabase** Windows PowerShell cmdlet to configure the Recovery Database.</span></span>


### <span data-ttu-id="292db-184">繼續管理和監控網站的實例</span><span class="sxs-lookup"><span data-stu-id="292db-184">Resume the instance of the Administration and Monitoring Website</span></span>

<span data-ttu-id="292db-185">在執行管理和監視網站的伺服器上，使用 Internet Information Services （IIS）管理員主控台來啟動 [管理和監控] 網站。</span><span class="sxs-lookup"><span data-stu-id="292db-185">On the server that is running the Administration and Monitoring Website, use the Internet Information Services (IIS) Manager console to start the Administration and Monitoring Website.</span></span>

<span data-ttu-id="292db-186">若要自動化此程式，您可以使用 Windows PowerShell 來執行類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="292db-186">To automate this procedure, you can use Windows PowerShell to run a command that is similar to the following:</span></span>

```powershell
Start-Website "Microsoft BitLocker Administration and Monitoring"
```

>[!NOTE]
><span data-ttu-id="292db-187">若要執行此命令，您必須將適用于 Windows PowerShell 的 IIS 模組新增至目前的 Windows PowerShell 實例。</span><span class="sxs-lookup"><span data-stu-id="292db-187">To run this command, you must add the IIS module for Windows PowerShell to the current instance of Windows PowerShell.</span></span>

## <span data-ttu-id="292db-188">移動合規性和審核資料庫</span><span class="sxs-lookup"><span data-stu-id="292db-188">Move the Compliance and Audit Database</span></span>

<span data-ttu-id="292db-189">移動合規性和審核資料庫的高層步驟如下：</span><span class="sxs-lookup"><span data-stu-id="292db-189">The high-level steps for moving the Compliance and Audit Database are:</span></span>

1.  <span data-ttu-id="292db-190">停止 MBAM 管理和監視網站的所有實例</span><span class="sxs-lookup"><span data-stu-id="292db-190">Stop all instances of the MBAM Administration and Monitoring Website</span></span>

2.  <span data-ttu-id="292db-191">在伺服器 A 上備份合規性和審核資料庫</span><span class="sxs-lookup"><span data-stu-id="292db-191">Back up the Compliance and Audit Database on Server A</span></span>

3.  <span data-ttu-id="292db-192">將合規性和審核資料庫從伺服器 A 移至伺服器 B</span><span class="sxs-lookup"><span data-stu-id="292db-192">Move the Compliance and Audit Database from Server A to Server B</span></span>

4.  <span data-ttu-id="292db-193">在伺服器 B 上還原合規性和審核資料庫</span><span class="sxs-lookup"><span data-stu-id="292db-193">Restore the Compliance and Audit Database on Server B</span></span>

5.  <span data-ttu-id="292db-194">在伺服器 B 上設定對資料庫的存取權並更新連接資料</span><span class="sxs-lookup"><span data-stu-id="292db-194">Configure access to the Database on Server B and update connection data</span></span>

6.  <span data-ttu-id="292db-195">在伺服器 B 上安裝 MBAM Server 軟體並執行 [MBAM 伺服器設定] 嚮導</span><span class="sxs-lookup"><span data-stu-id="292db-195">Install MBAM Server software and run the MBAM Server Configuration wizard on Server B</span></span>

7.  <span data-ttu-id="292db-196">繼續管理和監控網站的實例</span><span class="sxs-lookup"><span data-stu-id="292db-196">Resume the instance of the Administration and Monitoring Website</span></span>

### <span data-ttu-id="292db-197">如何移動合規性和審核資料庫</span><span class="sxs-lookup"><span data-stu-id="292db-197">How to move the Compliance and Audit Database</span></span>

**<span data-ttu-id="292db-198">停止 MBAM 管理和監視網站的所有實例。</span><span class="sxs-lookup"><span data-stu-id="292db-198">Stop all instances of the MBAM Administration and Monitoring Website.</span></span>**  <span data-ttu-id="292db-199">在執行 MBAM 管理和監視伺服器網站的每個伺服器上，使用 [網際網路資訊服務（IIS）管理員] 主控台來停止 [管理及監視] 網站。</span><span class="sxs-lookup"><span data-stu-id="292db-199">On each server that is running the MBAM Administration and Monitoring Server Website, use the Internet Information Services (IIS) Manager console to stop the Administration and Monitoring Website.</span></span>

<span data-ttu-id="292db-200">若要自動化此程式，您可以使用 Windows PowerShell 輸入類似以下的命令：</span><span class="sxs-lookup"><span data-stu-id="292db-200">To automate this procedure, you can use Windows PowerShell to enter a command that is similar to the following:</span></span>

```powershell
Stop-Website "Microsoft BitLocker Administration and Monitoring"
```

>[!NOTE]
><span data-ttu-id="292db-201">若要執行此命令，您必須將適用于 Windows PowerShell 的 Internet Information Services （IIS）模組新增到目前的 Windows PowerShell 實例。</span><span class="sxs-lookup"><span data-stu-id="292db-201">To run this command, you must add the Internet Information Services (IIS) module for Windows PowerShell to the current instance of Windows PowerShell.</span></span>

### <span data-ttu-id="292db-202">在伺服器 A 上備份合規性和審核資料庫</span><span class="sxs-lookup"><span data-stu-id="292db-202">Back up the Compliance and Audit Database on Server A</span></span>

1.  <span data-ttu-id="292db-203">使用 SQL Server Management Studio 中的 [**備份**] 工作，在伺服器 A 上備份合規性和審核資料庫。根據預設，資料庫名稱是**MBAM 合規性狀態資料庫**。</span><span class="sxs-lookup"><span data-stu-id="292db-203">Use the **Back Up** task in SQL Server Management Studio to back up the Compliance and Audit Database on Server A. By default, the database name is **MBAM Compliance Status Database**.</span></span>

2.  <span data-ttu-id="292db-204">若要自動化此程式，請建立包含下列 SQL 腳本的 SQL 檔案（.sql）：</span><span class="sxs-lookup"><span data-stu-id="292db-204">To automate this procedure, create a SQL file (.sql) that contains the following SQL script:</span></span>

    ```
    USE master;

    GO

    ALTER DATABASE "MBAM Compliance Status"

    SET RECOVERY FULL;

    GO

    -- Create MBAM Compliance Status Data logical backup devices.

    USE master

    GO

    EXEC sp_addumpdevice 'disk', 'MBAM Compliance Status Database Data Device',

    'Z: \MBAM Compliance Status Database Data.bak';

    GO

    -- Back up the full MBAM Compliance Recovery database.

    BACKUP DATABASE [MBAM Compliance Status] TO [MBAM Compliance Status Database Data Device];

    GO

    ```

3.  <span data-ttu-id="292db-205">使用類似下列的 Windows PowerShell 命令來執行儲存在 .sql 檔案中的腳本：</span><span class="sxs-lookup"><span data-stu-id="292db-205">Run the script that is stored in the .sql file by using a Windows PowerShell command that is similar to the following:</span></span>

    ```powershell
    Invoke-Sqlcmd -InputFile "Z:\BackupMBAMComplianceStatusDatabaseScript.sql" –ServerInstance     $SERVERNAME$\$SQLINSTANCENAME$

    ```

4.  <span data-ttu-id="292db-206">使用下列值，以與您的環境相符的值取代程式碼範例中的值：</span><span class="sxs-lookup"><span data-stu-id="292db-206">Using the following value, replace the values in the code example with values that match your environment:</span></span>

    <span data-ttu-id="292db-207">**$SERVERNAME $ \ $SQLINSTANCENAME $** -伺服器名稱和實例，將會將合規性和審核資料庫備份到其中。</span><span class="sxs-lookup"><span data-stu-id="292db-207">**$SERVERNAME$\$SQLINSTANCENAME$** - server name and instance from which the Compliance and Audit Database will be backed up.</span></span>

### <span data-ttu-id="292db-208">將合規性和審核資料庫從伺服器 A 移至伺服器 B \* \*</span><span class="sxs-lookup"><span data-stu-id="292db-208">Move the Compliance and Audit Database from Server A to Server B\*\*</span></span>

1.  <span data-ttu-id="292db-209">使用 Windows 資源管理器，將伺服器 A 的**MBAM 合規性狀態資料庫資料 .bak**檔案移至伺服器 B。</span><span class="sxs-lookup"><span data-stu-id="292db-209">Use Windows Explorer to move the **MBAM Compliance Status Database Data.bak** file from Server A to Server B.</span></span>

2.  <span data-ttu-id="292db-210">若要自動化此程式，您可以使用 Windows PowerShell 來執行類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="292db-210">To automate this procedure, you can use Windows PowerShell to run a command that is similar to the following:</span></span>

    ```powershell
    Copy-Item "Z:\MBAM Compliance Status Database Data.bak"
    \\$SERVERNAME$\$DESTINATIONSHARE$
    ```

3.  <span data-ttu-id="292db-211">使用下表，以與您的環境相符的值取代程式碼範例中的值。</span><span class="sxs-lookup"><span data-stu-id="292db-211">Using the following table, replace the values in the code example with values that match your environment.</span></span>

    | **<span data-ttu-id="292db-212">參數</span><span class="sxs-lookup"><span data-stu-id="292db-212">Parameter</span></span>**        | **<span data-ttu-id="292db-213">描述</span><span class="sxs-lookup"><span data-stu-id="292db-213">Description</span></span>**                                               |
    |----------------------|---------------------------------------------------------------|
    | <span data-ttu-id="292db-214">$SERVERNAME $</span><span class="sxs-lookup"><span data-stu-id="292db-214">$SERVERNAME$</span></span>       | <span data-ttu-id="292db-215">要將檔案複製到其中的伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="292db-215">Name of the server to which the files will be copied.</span></span>         |
    | <span data-ttu-id="292db-216">$DESTINATIONSHARE $</span><span class="sxs-lookup"><span data-stu-id="292db-216">$DESTINATIONSHARE$</span></span> | <span data-ttu-id="292db-217">要將檔案複製到其中的共用和路徑的名稱。</span><span class="sxs-lookup"><span data-stu-id="292db-217">Name of the share and path to which the files will be copied.</span></span> |


### <span data-ttu-id="292db-218">在伺服器 B 上還原合規性和審核資料庫</span><span class="sxs-lookup"><span data-stu-id="292db-218">Restore the Compliance and Audit Database on Server B</span></span>

1.  <span data-ttu-id="292db-219">使用 SQL Server Management Studio 中的 [**還原資料庫**] 工作，在伺服器 B 上還原合規性和審核資料庫。</span><span class="sxs-lookup"><span data-stu-id="292db-219">Restore the Compliance and Audit Database on Server B by using the **Restore Database** task in SQL Server Management Studio.</span></span>

2.  <span data-ttu-id="292db-220">在前一個工作完成時，請選取 [**從裝置**]，然後選取資料庫備份檔案。</span><span class="sxs-lookup"><span data-stu-id="292db-220">When the previous task finishes, select **From Device**, and then select the database backup file.</span></span>

3.  <span data-ttu-id="292db-221">使用 [ **Add** ] （新增）命令選取**MBAM 合規性狀態資料庫資料 .bak**檔案，然後按一下 **[確定]** 以完成還原程式。</span><span class="sxs-lookup"><span data-stu-id="292db-221">Use the **Add** command to select the **MBAM Compliance Status Database Data.bak** file and click **OK** to complete the restoration process.</span></span>

4.  <span data-ttu-id="292db-222">若要自動化此程式，請建立包含下列 SQL 腳本的 SQL 檔案（.sql）：</span><span class="sxs-lookup"><span data-stu-id="292db-222">To automate this procedure, create a SQL file (.sql) that contains the following SQL script:</span></span>

    ```
    -- Create MBAM Compliance Status Database Data logical backup devices.

    Use master

    GO

    -- Restore the MBAM Compliance Status database data files.

    RESTORE DATABASE [MBAM Compliance Status]

    FROM DISK = 'C:\test\MBAM Compliance Status Database Data.bak'

    WITH REPLACE

    ```

5.  <span data-ttu-id="292db-223">在 Windows PowerShell 中，執行儲存在檔案中的腳本，並類似以下所示：</span><span class="sxs-lookup"><span data-stu-id="292db-223">In Windows PowerShell, run the script that is stored in the file and similar to the following:</span></span>

    ```powershell
    Invoke-Sqlcmd -InputFile "Z:\RestoreMBAMComplianceStatusDatabaseScript.sql" -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$

    ```

6.  <span data-ttu-id="292db-224">使用下列值，以與您的環境相符的值取代程式碼範例中的值。</span><span class="sxs-lookup"><span data-stu-id="292db-224">Using the following value, replace the values in the code example with values that match your environment.</span></span>

    <span data-ttu-id="292db-225">**$SERVERNAME $ \ $SQLINSTANCENAME $** -伺服器名稱和實例，將會還原合規性和審核資料庫。</span><span class="sxs-lookup"><span data-stu-id="292db-225">**$SERVERNAME$\$SQLINSTANCENAME$** - Server name and instance to which the Compliance and Audit Database will be restored.</span></span>

### <span data-ttu-id="292db-226">在伺服器 B 上設定對資料庫的存取權並更新連接資料</span><span class="sxs-lookup"><span data-stu-id="292db-226">Configure access to the Database on Server B and update connection data</span></span>

1. <span data-ttu-id="292db-227">確認在已還原的資料庫上啟用合規性和審核資料庫存取的 Microsoft SQL Server 使用者登入會對應到您在設定過程中提供的存取帳戶。</span><span class="sxs-lookup"><span data-stu-id="292db-227">Verify that the Microsoft SQL Server user login that enables Compliance and Audit Database access on the restored database is mapped to the access account that you provided during the configuration process.</span></span>

   >[!NOTE]
   ><span data-ttu-id="292db-228">如果登入不相同，請使用 SQL Server Management Studio 建立登入，然後將它對應至現有的資料庫使用者。</span><span class="sxs-lookup"><span data-stu-id="292db-228">If the login is not the same, create a login by using SQL Server Management Studio, and map it to the existing database user.</span></span>

2. <span data-ttu-id="292db-229">在執行管理和監視網站的伺服器上，使用 Internet Information Services （IIS）管理員主控台來更新網站的連線字串資訊。</span><span class="sxs-lookup"><span data-stu-id="292db-229">On the server that is running the Administration and Monitoring Website, use the Internet Information Services (IIS) Manager console to update the connection string information for the Website.</span></span>

3. <span data-ttu-id="292db-230">編輯下列登錄機碼：</span><span class="sxs-lookup"><span data-stu-id="292db-230">Edit the following registry key:</span></span>

   **<span data-ttu-id="292db-231">HKLM\\Software\\Microsoft\\MBAM Server\\Web\\ComplianceDBConnectionString</span><span class="sxs-lookup"><span data-stu-id="292db-231">HKLM\\Software\\Microsoft\\MBAM Server\\Web\\ComplianceDBConnectionString</span></span>**

4. <span data-ttu-id="292db-232">使用伺服器和實例的名稱（例如，\ $SERVERNAME \ $ \\ $SQLINSTANCENAME）來更新已移動復原資料庫的**資料來源**值。</span><span class="sxs-lookup"><span data-stu-id="292db-232">Update the **Data Source** value with the name of the server and instance (for example, \$SERVERNAME\$\\\$SQLINSTANCENAME) to which the Recovery Database was moved.</span></span>

5. <span data-ttu-id="292db-233">使用已復原的資料庫名稱來更新**初始目錄**值。</span><span class="sxs-lookup"><span data-stu-id="292db-233">Update the **Initial Catalog** value with the recovered database name.</span></span>

6. <span data-ttu-id="292db-234">若要自動化此程式，您可以使用 Windows PowerShell 命令提示字元，在 [管理與監視伺服器] 上輸入如下所示的命令列：</span><span class="sxs-lookup"><span data-stu-id="292db-234">To automate this process, you can use the Windows PowerShell command prompt to enter a command line on the Administration and Monitoring Server that is similar to the following:</span></span>

   ```powershell
   reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MBAM Server\Web" /v
   ComplianceDBConnectionString /t REG_SZ /d "Integrated Security=SSPI;Initial
   Catalog=$DATABASE$;Data Source=$SERVERNAME$\$SQLINSTANCENAME$" /f
   ```
   >[!NOTE]
   ><span data-ttu-id="292db-235">這個連線字串是由所有本機 MBAM web 應用程式所共用。</span><span class="sxs-lookup"><span data-stu-id="292db-235">This connection string is shared by all local MBAM web applications.</span></span> <span data-ttu-id="292db-236">因此，每個伺服器只需要更新一次。</span><span class="sxs-lookup"><span data-stu-id="292db-236">Therefore, it needs to be updated only once per server.</span></span>


7. <span data-ttu-id="292db-237">使用下表，以與您的環境相符的值取代程式碼範例中的值。</span><span class="sxs-lookup"><span data-stu-id="292db-237">Using the following table, replace the values in the code example with values that match your environment.</span></span>

   |<span data-ttu-id="292db-238">參數</span><span class="sxs-lookup"><span data-stu-id="292db-238">Parameter</span></span> | <span data-ttu-id="292db-239">描述</span><span class="sxs-lookup"><span data-stu-id="292db-239">Description</span></span> |
   |---------|------------|
   |<span data-ttu-id="292db-240">$SERVERNAME $ \ $SQLINSTANCENAME $</span><span class="sxs-lookup"><span data-stu-id="292db-240">$SERVERNAME$\$SQLINSTANCENAME$</span></span> | <span data-ttu-id="292db-241">恢復資料庫所在之 SQL Server 的伺服器名稱和實例。</span><span class="sxs-lookup"><span data-stu-id="292db-241">Server name and instance of SQL Server where the Recovery Database is located.</span></span>|
   |<span data-ttu-id="292db-242">$DATABASE $</span><span class="sxs-lookup"><span data-stu-id="292db-242">$DATABASE$</span></span>|<span data-ttu-id="292db-243">已復原資料庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="292db-243">Name of the recovered database.</span></span>|

### <span data-ttu-id="292db-244">在伺服器 B 上安裝 MBAM Server 軟體並執行 [MBAM 伺服器設定] 嚮導</span><span class="sxs-lookup"><span data-stu-id="292db-244">Install MBAM Server software and run the MBAM Server Configuration wizard on Server B</span></span>

1.  <span data-ttu-id="292db-245">在伺服器 B 上安裝 MBAM 2.5 Server 軟體。如需詳細資訊，請參閱[安裝 MBAM 2.5 Server 軟體](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/installing-the-mbam-25-server-software)。</span><span class="sxs-lookup"><span data-stu-id="292db-245">Install the MBAM 2.5 Server software on Server B. For details, see [Installing the MBAM 2.5 Server Software](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/installing-the-mbam-25-server-software).</span></span>

2.  <span data-ttu-id="292db-246">在伺服器 B 上，啟動 [MBAM 伺服器設定] 嚮導，按一下 [新增**功能**]，然後只選取 [**合規性] 和 [審核資料庫**] 功能。</span><span class="sxs-lookup"><span data-stu-id="292db-246">On Server B, start the MBAM Server Configuration wizard, click **Add New Features**, and then select only the **Compliance and Audit Database** feature.</span></span> <span data-ttu-id="292db-247">如需如何設定資料庫的詳細資訊，請參閱[如何設定 MBAM 2.5 資料庫](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-configure-the-mbam-25-databases)。</span><span class="sxs-lookup"><span data-stu-id="292db-247">For details on how to configure the databases, see [How to Configure the MBAM 2.5 Databases](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-configure-the-mbam-25-databases).</span></span>

    >[!TIP]
    ><span data-ttu-id="292db-248">或者，您也可以使用**Enable-MbamDatabase** Windows PowerShell Cmdlet 來設定合規性和審核資料庫。</span><span class="sxs-lookup"><span data-stu-id="292db-248">Alternatively, you can use the **Enable-MbamDatabase** Windows PowerShell cmdlet to configure the Compliance and Audit Database.</span></span>


### <span data-ttu-id="292db-249">繼續管理和監控網站的實例</span><span class="sxs-lookup"><span data-stu-id="292db-249">Resume the instance of the Administration and Monitoring Website</span></span>

<span data-ttu-id="292db-250">在執行管理和監視網站的伺服器上，使用 Internet Information Services （IIS）管理員主控台來啟動 [管理和監控] 網站。</span><span class="sxs-lookup"><span data-stu-id="292db-250">On the server that is running the Administration and Monitoring Website, use the Internet Information Services (IIS) Manager console to start the Administration and Monitoring Website.</span></span>

<span data-ttu-id="292db-251">若要自動化此程式，您可以使用 Windows PowerShell 來執行類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="292db-251">To automate this procedure, you can use Windows PowerShell to run a command that is similar to the following:</span></span>

```powershell
Start-Website "Microsoft BitLocker Administration and Monitoring"
```

>[!NOTE]
><span data-ttu-id="292db-252">若要執行此命令，您必須將適用于 Windows PowerShell 的 IIS 模組新增至目前的 Windows PowerShell 實例。</span><span class="sxs-lookup"><span data-stu-id="292db-252">To run this command, you must add the IIS module for Windows PowerShell to the current instance of Windows PowerShell.</span></span>
