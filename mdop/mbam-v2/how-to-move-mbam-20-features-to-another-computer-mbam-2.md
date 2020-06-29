---
title: 如何將 MBAM 2.0 功能移到其他電腦
description: 如何將 MBAM 2.0 功能移到其他電腦
author: dansimp
ms.assetid: 49bc0792-60a4-473f-89cc-ada30191e04a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 340d87e26d87f124a9ab64c63d33e89c293d8a86
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810940"
---
# <span data-ttu-id="582b2-103">如何將 MBAM 2.0 功能移到其他電腦</span><span class="sxs-lookup"><span data-stu-id="582b2-103">How to Move MBAM 2.0 Features to Another Computer</span></span>


<span data-ttu-id="582b2-104">本主題說明將一或多個 Microsoft BitLocker 管理和監控（MBAM）功能移至不同電腦時應採取的步驟。</span><span class="sxs-lookup"><span data-stu-id="582b2-104">This topic describes the steps that you should take to move one or more Microsoft BitLocker Administration and Monitoring (MBAM) features to a different computer.</span></span> <span data-ttu-id="582b2-105">在移動一個以上的 Microsoft BitLocker 管理和監視功能時，您應該依下列順序移動它們：</span><span class="sxs-lookup"><span data-stu-id="582b2-105">When moving more than one Microsoft BitLocker Administration and Monitoring feature, you should move them in the following order:</span></span>

1.  <span data-ttu-id="582b2-106">復原資料庫</span><span class="sxs-lookup"><span data-stu-id="582b2-106">Recovery Database</span></span>

2.  <span data-ttu-id="582b2-107">合規性和審核資料庫</span><span class="sxs-lookup"><span data-stu-id="582b2-107">Compliance and Audit Database</span></span>

3.  <span data-ttu-id="582b2-108">合規性與審計報告</span><span class="sxs-lookup"><span data-stu-id="582b2-108">Compliance and Audit Reports</span></span>

4.  <span data-ttu-id="582b2-109">管理和監控</span><span class="sxs-lookup"><span data-stu-id="582b2-109">Administration and Monitoring</span></span>

## <span data-ttu-id="582b2-110">移動恢復資料庫</span><span class="sxs-lookup"><span data-stu-id="582b2-110">Moving the Recovery Database</span></span>


<span data-ttu-id="582b2-111">若要將復原資料庫從一部電腦移到另一台電腦（例如，從伺服器 A 移至伺服器 B），請使用下列程式。</span><span class="sxs-lookup"><span data-stu-id="582b2-111">To move the Recovery Database from one computer to another (for example, from Server A to Server B), use the following procedure.</span></span>

1.  <span data-ttu-id="582b2-112">停止管理和監控網站的所有實例。</span><span class="sxs-lookup"><span data-stu-id="582b2-112">Stop all instances of the Administration and Monitoring web site.</span></span>

2.  <span data-ttu-id="582b2-113">在伺服器 B 上執行 MBAM 安裝程式。</span><span class="sxs-lookup"><span data-stu-id="582b2-113">Run MBAM Setup on Server B.</span></span>

3.  <span data-ttu-id="582b2-114">在伺服器 A 上備份 MBAM 修復資料庫。</span><span class="sxs-lookup"><span data-stu-id="582b2-114">Back up the MBAM Recovery Database on Server A.</span></span>

4.  <span data-ttu-id="582b2-115">將 MBAM 復原資料庫從伺服器 A 移至 B。</span><span class="sxs-lookup"><span data-stu-id="582b2-115">Move the MBAM Recovery Database from Server A to B.</span></span>

5.  <span data-ttu-id="582b2-116">在伺服器 B 上還原 MBAM 修復資料庫。</span><span class="sxs-lookup"><span data-stu-id="582b2-116">Restore the MBAM Recovery Database on Server B.</span></span>

6.  <span data-ttu-id="582b2-117">在伺服器 B 上設定對 MBAM 復原資料庫的存取權。</span><span class="sxs-lookup"><span data-stu-id="582b2-117">Configure access to the MBAM Recovery Database on Server B.</span></span>

7.  <span data-ttu-id="582b2-118">更新 MBAM 管理和監視伺服器上的資料庫連線資料。</span><span class="sxs-lookup"><span data-stu-id="582b2-118">Update the database connection data on MBAM Administration and Monitoring servers.</span></span>

8.  <span data-ttu-id="582b2-119">繼續 MBAM 管理和監視網站的所有實例。</span><span class="sxs-lookup"><span data-stu-id="582b2-119">Resume all instances of the MBAM Administration and Monitoring website.</span></span>

**<span data-ttu-id="582b2-120">停止 MBAM 管理和監視網站的所有實例</span><span class="sxs-lookup"><span data-stu-id="582b2-120">Stop All Instances of the MBAM Administration and Monitoring Website</span></span>**

1.  <span data-ttu-id="582b2-121">在執行 MBAM 管理和監視功能的每個伺服器上，使用 Internet Information Services （IIS）管理員主控台來停止名為**Microsoft BitLocker 管理和監視**的 MBAM 網站。</span><span class="sxs-lookup"><span data-stu-id="582b2-121">On each of the servers running the MBAM Administration and Monitoring feature, use the Internet Information Services (IIS) Manager console to stop the MBAM website, which is named **Microsoft BitLocker Administration and Monitoring**.</span></span>

2.  <span data-ttu-id="582b2-122">若要自動化此程式，您可以使用 Windows PowerShell 來輸入類似以下的命令列：</span><span class="sxs-lookup"><span data-stu-id="582b2-122">To automate this procedure, you can use Windows PowerShell to enter command line that is similar to the:</span></span>

    `PS C:\> Stop-Website “Microsoft BitLocker Administration and Monitoring”`

    **<span data-ttu-id="582b2-123">注意</span><span class="sxs-lookup"><span data-stu-id="582b2-123">Note</span></span>**  
    <span data-ttu-id="582b2-124">若要執行此 PowerShell 命令列，必須將 PowerShell 的 IIS 模組新增到目前的 PowerShell 實例。</span><span class="sxs-lookup"><span data-stu-id="582b2-124">To run this PowerShell command line, the IIS Module for PowerShell must be added to current instance of PowerShell.</span></span> <span data-ttu-id="582b2-125">此外，您必須更新 PowerShell 執行原則，以啟用腳本執行。</span><span class="sxs-lookup"><span data-stu-id="582b2-125">In addition, you must update the PowerShell execution policy to enable execution of scripts.</span></span>



**<span data-ttu-id="582b2-126">在伺服器 B 上執行 MBAM 設定</span><span class="sxs-lookup"><span data-stu-id="582b2-126">Run MBAM Setup on Server B</span></span>**

1.  <span data-ttu-id="582b2-127">在伺服器 B 上執行 MBAM 安裝程式，然後只選取要安裝的復原**資料庫**。</span><span class="sxs-lookup"><span data-stu-id="582b2-127">Run MBAM Setup on Server B and select only the **Recovery Database** for installation.</span></span>

2.  <span data-ttu-id="582b2-128">若要自動化此程式，您可以使用 Windows PowerShell 來輸入類似以下的命令列：</span><span class="sxs-lookup"><span data-stu-id="582b2-128">To automate this procedure, you can use Windows PowerShell to enter command line that is similar to the following:</span></span>

    `PS C:\> MbamSetup.exe /qn I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 AddLocal=KeyDatabase ADMINANDMON_MACHINENAMES=$DOMAIN$\$SERVERNAME$$ RECOVERYANDHWDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ TOPOLOGY=$X$`

    **<span data-ttu-id="582b2-129">注意</span><span class="sxs-lookup"><span data-stu-id="582b2-129">Note</span></span>**  
    <span data-ttu-id="582b2-130">在上述範例中，將下列值取代為符合您環境的專案：</span><span class="sxs-lookup"><span data-stu-id="582b2-130">Replace the following values in the example above with those that match your environment:</span></span>

    -   <span data-ttu-id="582b2-131">$SERVERNAME $ \ \ $SQLINSTANCENAME $-輸入要將恢復資料庫移動到其中的伺服器和實例名稱。</span><span class="sxs-lookup"><span data-stu-id="582b2-131">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the name of the server and instance to which the Recovery Database will be moved.</span></span>

    -   <span data-ttu-id="582b2-132">$DOMAIN $ \ \ $SERVERNAME $-輸入將會與恢復資料庫聯絡的每個 MBAM 管理和監視伺服器的網域和伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="582b2-132">$DOMAIN$\\$SERVERNAME$ - Enter the domain and server names of each MBAM Administration and Monitoring Server that will contact the Recovery Database.</span></span> <span data-ttu-id="582b2-133">使用分號來分隔清單中的每個網域和伺服器配對（例如，$DOMAIN \\SERVERNAME $; $DOMAIN \\ $SERVERNAME $ $）。</span><span class="sxs-lookup"><span data-stu-id="582b2-133">Use a semi-colon to separate each domain and server pairs in the list (for example, $DOMAIN\\SERVERNAME$;$DOMAIN\\$SERVERNAME$$).</span></span> <span data-ttu-id="582b2-134">每個伺服器名稱後面必須加一個 "$" 符號，如下例所示（MyDomain\\MyServerName1 $;MyDomain\\MyServerName2 $）。</span><span class="sxs-lookup"><span data-stu-id="582b2-134">Each server name must be followed by a “$” symbol, as shown in the example (MyDomain\\MyServerName1$; MyDomain\\MyServerName2$).</span></span>

    -   <span data-ttu-id="582b2-135">如果您要安裝 MBAM 獨立拓朴，請 $X $-輸入**0** ; 如果您要安裝 MBAM Configuration Manager 拓撲，則為**1** 。</span><span class="sxs-lookup"><span data-stu-id="582b2-135">$X$ - Enter **0** if you are installing the MBAM Stand-alone topology, or **1** if you are installing the MBAM Configuration Manager topology.</span></span>



**<span data-ttu-id="582b2-136">在伺服器 A 上備份恢復資料庫</span><span class="sxs-lookup"><span data-stu-id="582b2-136">Back Up the Recovery Database on Server A</span></span>**

1.  <span data-ttu-id="582b2-137">若要在伺服器 A 上備份復原資料庫，請使用 SQL Server Management Studio 及名為 Back 的工作。</span><span class="sxs-lookup"><span data-stu-id="582b2-137">To back up the Recovery Database on Server A, use SQL Server Management Studio and the Task named Back Up.</span></span> <span data-ttu-id="582b2-138">根據預設，資料庫名稱是 MBAM 的 [**恢復資料庫**]。</span><span class="sxs-lookup"><span data-stu-id="582b2-138">By default, the database name is **MBAM Recovery Database**.</span></span>

2.  <span data-ttu-id="582b2-139">若要自動化此程式，請建立包含下列 SQL 腳本的 SQL 檔案（.sql）：</span><span class="sxs-lookup"><span data-stu-id="582b2-139">To automate this procedure, create a SQL file (.sql) that contains the following SQL script:</span></span>

    <span data-ttu-id="582b2-140">修改 MBAM 復原資料庫，以使用完整的復原模式。</span><span class="sxs-lookup"><span data-stu-id="582b2-140">Modify the MBAM Recovery Database to use the full recovery mode.</span></span>

    ```sql
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

    **<span data-ttu-id="582b2-141">注意</span><span class="sxs-lookup"><span data-stu-id="582b2-141">Note</span></span>**  
    <span data-ttu-id="582b2-142">在上述範例中，將下列值取代為符合您環境的專案：</span><span class="sxs-lookup"><span data-stu-id="582b2-142">Replace the following values in the example above with those that match your environment:</span></span>

    -   <span data-ttu-id="582b2-143">$PASSWORD $-輸入將用來加密私密金鑰檔案的密碼。</span><span class="sxs-lookup"><span data-stu-id="582b2-143">$PASSWORD$ - Enter a password that you will use to encrypt the Private Key file.</span></span>



3.  <span data-ttu-id="582b2-144">使用 SQL Server PowerShell 和類似下列的命令列來執行 SQL 檔案：</span><span class="sxs-lookup"><span data-stu-id="582b2-144">Run the SQL File by using SQL Server PowerShell and a command line that is similar to the following:</span></span>

    `PS C:\> Invoke-Sqlcmd -InputFile 'Z:\BackupMBAMRecoveryandHardwarDatabaseScript.sql' -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$`

    **<span data-ttu-id="582b2-145">注意</span><span class="sxs-lookup"><span data-stu-id="582b2-145">Note</span></span>**  
    <span data-ttu-id="582b2-146">在上述範例中，將下列值取代為符合您環境的專案：</span><span class="sxs-lookup"><span data-stu-id="582b2-146">Replace the following values in the example above with those that match your environment:</span></span>

    -   <span data-ttu-id="582b2-147">$SERVERNAME $ \ \ $SQLINSTANCENAME $-輸入將備份恢復資料庫的伺服器和實例名稱。</span><span class="sxs-lookup"><span data-stu-id="582b2-147">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the name of the server and instance from which the Recovery Database will be backed up.</span></span>



**<span data-ttu-id="582b2-148">從伺服器 A 將復原資料庫和憑證移至伺服器 B</span><span class="sxs-lookup"><span data-stu-id="582b2-148">Move the Recovery Database and Certificate from Server A to Server B</span></span>**

1.  <span data-ttu-id="582b2-149">使用 Windows 資源管理器，將下列檔案從伺服器 A 移至伺服器 B。</span><span class="sxs-lookup"><span data-stu-id="582b2-149">Move the following file from Server A to Server B by using Windows Explorer.</span></span>

    -   <span data-ttu-id="582b2-150">MBAM 恢復資料庫資料 .bak</span><span class="sxs-lookup"><span data-stu-id="582b2-150">MBAM Recovery Database data.bak</span></span>

2.  <span data-ttu-id="582b2-151">若要移動加密資料庫的憑證，請使用下列自動化步驟。</span><span class="sxs-lookup"><span data-stu-id="582b2-151">To move the certificate for the encrypted database, use the following automation steps.</span></span> <span data-ttu-id="582b2-152">若要自動化此程式，您可以使用 Windows PowerShell 輸入類似以下的命令列：</span><span class="sxs-lookup"><span data-stu-id="582b2-152">To automate this procedure, you can use Windows PowerShell to enter a command line that is similar to the following:</span></span>

    `PS C:\> Copy-Item “Z:\MBAM Recovery Database Data.bak” \\$SERVERNAME$\$DESTINATIONSHARE$`

    `PS C:\> Copy-Item “Z:\SQLServerInstanceCertificateFile” \\$SERVERNAME$\$DESTINATIONSHARE$`

    `PS C:\> Copy-Item “Z:\SQLServerInstanceCertificateFilePrivateKey” \\$SERVERNAME$\$DESTINATIONSHARE$`

    **<span data-ttu-id="582b2-153">注意</span><span class="sxs-lookup"><span data-stu-id="582b2-153">Note</span></span>**  
    <span data-ttu-id="582b2-154">在上述範例中，將下列值取代為符合您環境的專案：</span><span class="sxs-lookup"><span data-stu-id="582b2-154">Replace the following value in the example above with those that match your environment:</span></span>

    -   <span data-ttu-id="582b2-155">$SERVERNAME $-輸入要將檔案複製到其中的伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="582b2-155">$SERVERNAME$ - Enter the name of the server to which the files will be copied.</span></span>

    -   <span data-ttu-id="582b2-156">$DESTINATIONSHARE $-輸入要將檔案複製到其中的共用名稱稱和路徑。</span><span class="sxs-lookup"><span data-stu-id="582b2-156">$DESTINATIONSHARE$ - Enter the name of the share and path to which the files will be copied.</span></span>



**<span data-ttu-id="582b2-157">在伺服器 B 上還原恢復資料庫</span><span class="sxs-lookup"><span data-stu-id="582b2-157">Restore the Recovery Database on Server B</span></span>**

1.  <span data-ttu-id="582b2-158">在伺服器 B 上使用 SQL Server Management Studio 及名為 [**還原資料庫**] 的工作來還原恢復資料庫。</span><span class="sxs-lookup"><span data-stu-id="582b2-158">Restore the Recovery Database on Server B by using SQL Server Management Studio and the task named **Restore Database**.</span></span>

2.  <span data-ttu-id="582b2-159">完成工作後，請選取 [**發件**人] 選項，然後使用 [Add] （**新增**）命令選取 MBAM 復原資料庫**資料 .bak**盤案，以選取資料庫備份檔案。</span><span class="sxs-lookup"><span data-stu-id="582b2-159">Once the task has been completed, select the database backup file by selecting the **From Device** option and then use the **Add** command to select the MBAM Recovery database **Data.bak** file.</span></span>

3.  <span data-ttu-id="582b2-160">選取 **[確定]** 以完成還原程式。</span><span class="sxs-lookup"><span data-stu-id="582b2-160">Select **OK** to complete the restoration process.</span></span>

4.  <span data-ttu-id="582b2-161">若要自動化此程式，請建立包含下列 SQL 腳本的 SQL 檔案（.sql）：</span><span class="sxs-lookup"><span data-stu-id="582b2-161">To automate this procedure, create a SQL file (.sql) that contains the following-SQL script:</span></span>

    ```sql
    -- Restore MBAM Recovery Database. 

    USE master

    GO

    -- Drop certificate created by MBAM Setup.

    DROP CERTIFICATE [MBAM Recovery Encryption Certificate]

    GO

    --Add certificate

    CREATE CERTIFICATE [MBAM Recovery Encryption Certificate]

    FROM FILE = 'Z: \SQLServerInstanceCertificateFile'

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

    **<span data-ttu-id="582b2-162">注意</span><span class="sxs-lookup"><span data-stu-id="582b2-162">Note</span></span>**  
    <span data-ttu-id="582b2-163">在上述範例中，將下列值取代為符合您環境的專案：</span><span class="sxs-lookup"><span data-stu-id="582b2-163">Replace the following values in the example above with those that match your environment:</span></span>

    -   <span data-ttu-id="582b2-164">$PASSWORD $-輸入您用來加密私人金鑰檔案的密碼。</span><span class="sxs-lookup"><span data-stu-id="582b2-164">$PASSWORD$ - Enter a password that you used to encrypt the Private Key file.</span></span>



5.  <span data-ttu-id="582b2-165">您可以使用 Windows PowerShell 來輸入類似以下的命令列：</span><span class="sxs-lookup"><span data-stu-id="582b2-165">You can use Windows PowerShell to enter a command line that is similar to the following:</span></span>

    `PS C:\> Invoke-Sqlcmd -InputFile 'Z:\RestoreMBAMRecoveryandHardwarDatabaseScript.sql' -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$`

    **<span data-ttu-id="582b2-166">注意</span><span class="sxs-lookup"><span data-stu-id="582b2-166">Note</span></span>**  
    <span data-ttu-id="582b2-167">在上述範例中，將下列值取代為符合您環境的專案：</span><span class="sxs-lookup"><span data-stu-id="582b2-167">Replace the following value in the example above with those that match your environment:</span></span>

    -   <span data-ttu-id="582b2-168">$SERVERNAME $ \ \ $SQLINSTANCENAME $-輸入將還原恢復資料庫的伺服器和實例名稱。</span><span class="sxs-lookup"><span data-stu-id="582b2-168">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the name of the server and instance to which the Recovery Database will be restored.</span></span>



**<span data-ttu-id="582b2-169">在伺服器 B 上設定存取恢復資料庫</span><span class="sxs-lookup"><span data-stu-id="582b2-169">Configure Access to the Recovery Database on Server B</span></span>**

1.  <span data-ttu-id="582b2-170">在伺服器 B 上，使用 [伺服器管理員] 中的 [本機使用者和群組] 管理單元，將執行 MBAM 管理和監控功能的每個伺服器上的電腦帳戶新增到名為**MBAM 復原及硬體資料庫存取權**的本機群組。</span><span class="sxs-lookup"><span data-stu-id="582b2-170">On Server B, use the Local user and Groups snap-in from Server Manager to add the computer accounts from each server that is running the MBAM Administration and Monitoring feature to the Local Group named **MBAM Recovery and Hardware DB Access**.</span></span>

2.  <span data-ttu-id="582b2-171">確認已還原的資料庫上的 SQL 登入**MBAM 復原及硬體 Db 存取**已對應至 [登入名稱] **$MachineName $ \\MBAM 復原與硬體資料庫存取**。</span><span class="sxs-lookup"><span data-stu-id="582b2-171">Verify that the SQL login **MBAM Recovery and Hardware DB Access** on the restored database is mapped to the login name **$MachineName$\\MBAM Recovery and Hardware DB Access**.</span></span> <span data-ttu-id="582b2-172">如果未如所述對應，請使用類似的群組成員資格建立另一個登入，然後將它對應至登入名稱 **$MachineName $ \\MBAM 復原與硬體資料庫存取**。</span><span class="sxs-lookup"><span data-stu-id="582b2-172">If it is not mapped as described, create another login with similar group memberships, and map it to the login name **$MachineName$\\MBAM Recovery and Hardware DB Access**.</span></span>

3.  <span data-ttu-id="582b2-173">若要自動化此程式，您可以在伺服器 B 上使用 Windows PowerShell，輸入類似以下的命令列：</span><span class="sxs-lookup"><span data-stu-id="582b2-173">To automate this procedure, you can use Windows PowerShell on Server B to enter a command line that is similar to the following:</span></span>

    `PS C:\> net localgroup "MBAM Recovery and Hardware DB Access" $DOMAIN$\$SERVERNAME$$  /add`

    **<span data-ttu-id="582b2-174">注意</span><span class="sxs-lookup"><span data-stu-id="582b2-174">Note</span></span>**  
    <span data-ttu-id="582b2-175">請以適用于您環境的值取代上述範例中的下列值：</span><span class="sxs-lookup"><span data-stu-id="582b2-175">Replace the following values in the example above with the applicable values for your environment:</span></span>

    -   <span data-ttu-id="582b2-176">$DOMAIN $ \ \ $SERVERNAME $ $-輸入 MBAM 管理和監視伺服器的網域和電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="582b2-176">$DOMAIN$\\$SERVERNAME$$ - Enter the domain and machine name of the MBAM Administration and Monitoring Server.</span></span> <span data-ttu-id="582b2-177">伺服器名稱必須後接 $，如範例中所示（例如，MyDomain\\MyServerName1 $）。</span><span class="sxs-lookup"><span data-stu-id="582b2-177">The server name must be followed by a $, as shown in the example (for example, MyDomain\\MyServerName1$).</span></span>



~~~
This command line must be run for each Administration and Monitoring Server that will be accessing the database in your environment.
~~~

**<span data-ttu-id="582b2-178">更新 MBAM 管理和監視伺服器上的復原資料庫連線資料</span><span class="sxs-lookup"><span data-stu-id="582b2-178">Update the Recovery Database Connection Data on the MBAM Administration and Monitoring Servers</span></span>**

1. <span data-ttu-id="582b2-179">在執行 MBAM 管理和監視功能的每個伺服器上，使用 Internet Information Services （IIS）管理員主控台來更新下列應用程式的連線字串資訊，這些應用程式是託管于 [管理] 和 [監視] 網站：</span><span class="sxs-lookup"><span data-stu-id="582b2-179">On each of the servers running the MBAM Administration and Monitoring feature, use the Internet Information Services (IIS) Manager console to update the Connection String information for the following applications, which are hosted in the Administration and Monitoring website:</span></span>

   -   <span data-ttu-id="582b2-180">MBAMAdministrationService</span><span class="sxs-lookup"><span data-stu-id="582b2-180">MBAMAdministrationService</span></span>

   -   <span data-ttu-id="582b2-181">MBAMRecoveryAndHardwareService</span><span class="sxs-lookup"><span data-stu-id="582b2-181">MBAMRecoveryAndHardwareService</span></span>

2. <span data-ttu-id="582b2-182">選取每個應用程式，並使用 [設定**編輯器**] 功能（位於**功能視圖**的 [**管理**] 區段底下）。</span><span class="sxs-lookup"><span data-stu-id="582b2-182">Select each application and use the **Configuration Editor** feature, which is located under the **Management** section of the **Feature View**.</span></span>

3. <span data-ttu-id="582b2-183">從**區段清單**控制項選取 [ **configurationStrings** ] 選項。</span><span class="sxs-lookup"><span data-stu-id="582b2-183">Select the **configurationStrings** option from the **Section list** control.</span></span>

4. <span data-ttu-id="582b2-184">選取名為 **（集合）** 的列，然後選取列右側的按鈕來開啟**集合編輯器**。</span><span class="sxs-lookup"><span data-stu-id="582b2-184">Select the row named **(Collection)** and open the **Collection Editor** by selecting the button on the right side of the row.</span></span>

5. <span data-ttu-id="582b2-185">在**集合編輯器**中，更新 MBAMAdministrationService 應用程式的設定或名為 Mbam 的列時，請選取名為**KeyRecoveryConnectionString**的列 <strong> 。 </strong>更新 MBAMRecoveryAndHardwareService 的設定時的 ConnectionString。</span><span class="sxs-lookup"><span data-stu-id="582b2-185">In the **Collection Editor**, select the row named **KeyRecoveryConnectionString** when updating the configuration for the MBAMAdministrationService application or the row named <strong>Microsoft.Mbam.RecoveryAndHardwareDataStore.</strong>ConnectionString when updating the configuration for the MBAMRecoveryAndHardwareService.</span></span>

6. <span data-ttu-id="582b2-186">更新**configurationStrings**屬性的**資料來源 =** 值，以列出伺服器名稱和實例（例如，$SERVERNAME $ \ \ $SQLINSTANCENAME $），並將恢復資料庫移至該伺服器。</span><span class="sxs-lookup"><span data-stu-id="582b2-186">Update the **Data Source=** value for the **configurationStrings** property to list the server name and instance (for example, $SERVERNAME$\\$SQLINSTANCENAME$) where the Recovery Database was moved to.</span></span>

7. <span data-ttu-id="582b2-187">若要自動化此程式，您可以在每個管理和監視伺服器上使用 Windows 輸入命令列，這與下列類似：</span><span class="sxs-lookup"><span data-stu-id="582b2-187">To automate this procedure, you can use Windows to enter a command line, that is similar to the following, on each Administration and Monitoring Server:</span></span>

   `PS C:\> Set-WebConfigurationProperty '/connectionStrings/add[@name="KeyRecoveryConnectionString"]' -PSPath "IIS:\sites\Microsoft Bitlocker Administration and Monitoring\MBAMAdministrationService" -Name "connectionString" -Value “Data Source=$SERVERNAME$\$SQLINSTANCENAME$;Initial Catalog=MBAM Recovery and Hardware;Integrated Security=SSPI;”`

   `PS C:\> Set-WebConfigurationProperty '/connectionStrings/add[@name="Microsoft.Mbam.RecoveryAndHardwareDataStore.ConnectionString"]' -PSPath "IIS:\sites\Microsoft Bitlocker Administration and Monitoring\MBAMRecoveryAndHardwareService" -Name "connectionString" -Value "Data Source=$SERVERNAME$\$SQLINSTANCENAME$;Initial Catalog=MBAM Recovery and Hardware;Integrated Security=SSPI;"`

   **<span data-ttu-id="582b2-188">注意</span><span class="sxs-lookup"><span data-stu-id="582b2-188">Note</span></span>**  
   <span data-ttu-id="582b2-189">在上述範例中，將下列值取代為符合您環境的專案：</span><span class="sxs-lookup"><span data-stu-id="582b2-189">Replace the following value in the example above with those that match your environment:</span></span>

   -   <span data-ttu-id="582b2-190">$SERVERNAME $ \ \ $SQLINSTANCENAME $-輸入恢復資料庫的伺服器名稱和實例。</span><span class="sxs-lookup"><span data-stu-id="582b2-190">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the server name and instance where the Recovery Database is.</span></span>



**<span data-ttu-id="582b2-191">繼續 MBAM 管理和監視網站的所有實例</span><span class="sxs-lookup"><span data-stu-id="582b2-191">Resume all Instances of the MBAM Administration and Monitoring Website</span></span>**

1.  <span data-ttu-id="582b2-192">在執行 MBAM 管理和監視功能的每個伺服器上，使用 Internet Information Services （IIS）管理員主控台來啟動名為**Microsoft BitLocker 管理和監視**的 MBAM 網站。</span><span class="sxs-lookup"><span data-stu-id="582b2-192">On each server that is running the MBAM Administration and Monitoring feature, use the Internet Information Services (IIS) Manager console to start the MBAM website, which is named **Microsoft BitLocker Administration and Monitoring**.</span></span>

2.  <span data-ttu-id="582b2-193">若要自動化此程式，您可以使用 Windows PowerShell 輸入類似以下的命令列：</span><span class="sxs-lookup"><span data-stu-id="582b2-193">To automate this procedure, you can use Windows PowerShell to enter a command line that is similar to the:</span></span>

    `PS C:\> Start-Website “Microsoft BitLocker Administration and Monitoring”`

## <span data-ttu-id="582b2-194">移動合規性與審計資料庫功能</span><span class="sxs-lookup"><span data-stu-id="582b2-194">Moving the Compliance and Audit Database Feature</span></span>


<span data-ttu-id="582b2-195">如果您想要將 MBAM 合規性和審核資料庫從一部電腦移到另一台電腦（也就是將資料庫從伺服器 A 移至伺服器 B），請使用下列程式。</span><span class="sxs-lookup"><span data-stu-id="582b2-195">If you want to move the MBAM Compliance and Audit Database from one computer to another (that is, move the database from Server A to Server B), use the following procedure.</span></span> <span data-ttu-id="582b2-196">此套裝程式含下列高層次步驟：</span><span class="sxs-lookup"><span data-stu-id="582b2-196">The process includes the following high-level steps:</span></span>

1.  <span data-ttu-id="582b2-197">停止管理和監控網站的所有實例。</span><span class="sxs-lookup"><span data-stu-id="582b2-197">Stop all instances of the Administration and Monitoring website.</span></span>

2.  <span data-ttu-id="582b2-198">在伺服器 B 上執行 MBAM 安裝程式。</span><span class="sxs-lookup"><span data-stu-id="582b2-198">Run MBAM setup on Server B.</span></span>

3.  <span data-ttu-id="582b2-199">在伺服器 A 上備份資料庫。</span><span class="sxs-lookup"><span data-stu-id="582b2-199">Back up the Database on Server A.</span></span>

4.  <span data-ttu-id="582b2-200">將資料庫從伺服器 A 移至 B。</span><span class="sxs-lookup"><span data-stu-id="582b2-200">Move the Database from Server A to B.</span></span>

5.  <span data-ttu-id="582b2-201">在伺服器 B 上還原資料庫。</span><span class="sxs-lookup"><span data-stu-id="582b2-201">Restore the Database on Server B.</span></span>

6.  <span data-ttu-id="582b2-202">在伺服器 B 上設定對資料庫的存取權。</span><span class="sxs-lookup"><span data-stu-id="582b2-202">Configure access to the Database on Server B.</span></span>

7.  <span data-ttu-id="582b2-203">更新 MBAM 管理和監視伺服器上的資料庫連線資料。</span><span class="sxs-lookup"><span data-stu-id="582b2-203">Update the database connection data on the MBAM Administration and Monitoring servers.</span></span>

8.  <span data-ttu-id="582b2-204">使用合規性和審核資料庫的新位置來更新 SSRS 報表資料來源連線字串。</span><span class="sxs-lookup"><span data-stu-id="582b2-204">Update the SSRS reports data source connection string with the new location of the Compliance and Audit Database.</span></span>

9.  <span data-ttu-id="582b2-205">繼續所有管理和監控網站的實例。</span><span class="sxs-lookup"><span data-stu-id="582b2-205">Resume all instances of the Administration and Monitoring website.</span></span>

**<span data-ttu-id="582b2-206">停止管理和監控網站的所有實例</span><span class="sxs-lookup"><span data-stu-id="582b2-206">Stop All Instances of the Administration and Monitoring Website</span></span>**

1.  <span data-ttu-id="582b2-207">在執行 MBAM 管理和監視功能的每個伺服器上，使用 Internet Information Services （IIS）管理員主控台來停止名為**Microsoft BitLocker 管理及監視**的 MBAM 網站。</span><span class="sxs-lookup"><span data-stu-id="582b2-207">On each server that is running the MBAM Administration and Monitoring feature, use the Internet Information Services (IIS) Manager console to stop the MBAM website named **Microsoft BitLocker Administration and Monitoring**.</span></span>

2.  <span data-ttu-id="582b2-208">若要自動化此程式，您可以使用 Windows PowerShell 輸入類似以下的命令列：</span><span class="sxs-lookup"><span data-stu-id="582b2-208">To automate this procedure, you can use Windows PowerShell to enter a command line that is similar to the following:</span></span>

    `PS C:\> Stop-s “Microsoft BitLocker Administration and Monitoring”`

    **<span data-ttu-id="582b2-209">注意</span><span class="sxs-lookup"><span data-stu-id="582b2-209">Note</span></span>**  
    <span data-ttu-id="582b2-210">若要執行此命令列，您必須將 PowerShell 的 IIS 模組新增至目前的 PowerShell 實例。</span><span class="sxs-lookup"><span data-stu-id="582b2-210">To run this command line, you must add the IIS Module for PowerShell to the current instance of PowerShell.</span></span> <span data-ttu-id="582b2-211">此外，您必須更新 PowerShell 執行原則，才能執行腳本。</span><span class="sxs-lookup"><span data-stu-id="582b2-211">In addition, you must update the PowerShell execution policy to enable scripts to be run.</span></span>



**<span data-ttu-id="582b2-212">在伺服器 B 上執行 MBAM 設定</span><span class="sxs-lookup"><span data-stu-id="582b2-212">Run MBAM Setup on Server B</span></span>**

1.  <span data-ttu-id="582b2-213">在伺服器 B 上執行 MBAM 安裝程式，然後只選取**合規性和審核資料庫**以進行安裝。</span><span class="sxs-lookup"><span data-stu-id="582b2-213">Run MBAM Setup on Server B and select only the **Compliance and Audit Database** for installation.</span></span>

2.  <span data-ttu-id="582b2-214">若要自動化此程式，您可以使用 Windows PowerShell 輸入類似以下的命令列：</span><span class="sxs-lookup"><span data-stu-id="582b2-214">To automate this procedure, you can use Windows PowerShell to enter a command line that is similar to the following:</span></span>

    `PS C:\> MbamSetup.exe /qn I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 AddLocal= ReportsDatabase ADMINANDMON_MACHINENAMES=$DOMAIN$\$SERVERNAME$ COMPLIDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ REPORTS_USERACCOUNT=$DOMAIN$\$USERNAME$ TOPOLOGY=$X$`

    **<span data-ttu-id="582b2-215">注意</span><span class="sxs-lookup"><span data-stu-id="582b2-215">Note</span></span>**  
    <span data-ttu-id="582b2-216">注意：請將上述範例中的下列值取代成與您的環境相符的值：</span><span class="sxs-lookup"><span data-stu-id="582b2-216">Note: Replace the following values in the example above with those that match your environment:</span></span>

    -   <span data-ttu-id="582b2-217">$SERVERNAME $ \ \ $SQLINSTANCENAME $-輸入要將合規性和審核資料庫移至其中的伺服器名稱和實例。</span><span class="sxs-lookup"><span data-stu-id="582b2-217">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the server name and instance where the Compliance and Audit Database will be moved to.</span></span>

    -   <span data-ttu-id="582b2-218">$DOMAIN $ \ \ $SERVERNAME $-輸入將會與合規性和審核資料庫聯繫的每個 MBAM 管理和監視伺服器的網域和伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="582b2-218">$DOMAIN$\\$SERVERNAME$ - Enter the domain and server names of each MBAM Administration and Monitoring Server that will contact the Compliance and Audit Database.</span></span> <span data-ttu-id="582b2-219">使用分號來分隔清單中的每個網域和伺服器對（例如，$DOMAIN \\SERVERNAME $; $DOMAIN \\ $SERVERNAME $ $）。</span><span class="sxs-lookup"><span data-stu-id="582b2-219">Use a semi-colon to separate each domain and server pair in the list (for example, $DOMAIN\\SERVERNAME$;$DOMAIN\\$SERVERNAME$$).</span></span> <span data-ttu-id="582b2-220">每個伺服器名稱後面必須加一個 "$" 符號，如下例所示（MyDomain\\MyServerName1 $;MyDomain\\MyServerName2 $）。</span><span class="sxs-lookup"><span data-stu-id="582b2-220">Each server name must be followed by a “$” symbol, as shown in the example (MyDomain\\MyServerName1$; MyDomain\\MyServerName2$).</span></span>

    -   <span data-ttu-id="582b2-221">$DOMAIN $ \ \ $USERNAME $-輸入將由合規性和審核報告功能用來連線至合規性和審核資料庫的網域和使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="582b2-221">$DOMAIN$\\$USERNAME$ - Enter the domain and user name that will be used by the Compliance and Audit Reports feature to connect to the Compliance and Audit Database.</span></span>

    -   <span data-ttu-id="582b2-222">如果您要安裝 MBAM 獨立拓朴，請 $X $-輸入**0** ; 如果您要安裝 MBAM Configuration Manager 拓撲，則為**1** 。</span><span class="sxs-lookup"><span data-stu-id="582b2-222">$X$ - Enter **0** if you are installing the MBAM Stand-alone topology, or **1** if you are installing the MBAM Configuration Manager topology.</span></span>



**<span data-ttu-id="582b2-223">在伺服器 A 上備份合規性和審核資料庫</span><span class="sxs-lookup"><span data-stu-id="582b2-223">Back Up the Compliance and Audit Database on Server A</span></span>**

1.  <span data-ttu-id="582b2-224">若要在伺服器 A 上備份合規性和審核資料庫，請使用 SQL Server Management Studio 及名為**back**的工作。</span><span class="sxs-lookup"><span data-stu-id="582b2-224">To back up the Compliance and Audit Database on Server A, use SQL Server Management Studio and the task named **Back Up**.</span></span> <span data-ttu-id="582b2-225">根據預設，資料庫名稱是**MBAM 合規性狀態資料庫**。</span><span class="sxs-lookup"><span data-stu-id="582b2-225">By default, the database name is **MBAM Compliance Status Database**.</span></span>

2.  <span data-ttu-id="582b2-226">若要自動化此程式，請建立包含下列 SQL 腳本的 SQL 檔案（.sql）：</span><span class="sxs-lookup"><span data-stu-id="582b2-226">To automate this procedure, create a SQL file (.sql) that contains the following-SQL script:</span></span>

    ```sql
    -- Modify the MBAM Compliance Status Database to use the full recovery model.

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

    -- Back up the full MBAM Recovery database.

    BACKUP DATABASE [MBAM Compliance Status] TO [MBAM Compliance Status Database Data Device];

    GO
    ```

3.  <span data-ttu-id="582b2-227">使用與下列類似的 Windows PowerShell 命令列來執行 SQL 檔案：</span><span class="sxs-lookup"><span data-stu-id="582b2-227">Run the SQL file by using a Windows PowerShell command line that is similar to the following:</span></span>

    `PS C:\> Invoke-Sqlcmd -InputFile "Z:\BackupMBAMComplianceStatusDatabaseScript.sql" –ServerInstance $SERVERNAME$\$SQLINSTANCENAME$`

    **<span data-ttu-id="582b2-228">注意</span><span class="sxs-lookup"><span data-stu-id="582b2-228">Note</span></span>**  
    <span data-ttu-id="582b2-229">在上述範例中，將下列值取代為符合您環境的專案：</span><span class="sxs-lookup"><span data-stu-id="582b2-229">Replace the following value in the example above with those that match your environment:</span></span>

    -   <span data-ttu-id="582b2-230">$SERVERNAME $ \ \ $SQLINSTANCENAME $-輸入要備份合規性和審核資料庫的伺服器名稱和實例。</span><span class="sxs-lookup"><span data-stu-id="582b2-230">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the server name and instance where the Compliance and Audit database will be backed up from.</span></span>



**<span data-ttu-id="582b2-231">將合規性和審核資料庫從伺服器 A 移至 B</span><span class="sxs-lookup"><span data-stu-id="582b2-231">Move the Compliance and Audit Database from Server A to B</span></span>**

1.  <span data-ttu-id="582b2-232">使用 Windows 資源管理器，將下列檔案從伺服器 A 移至伺服器 B。</span><span class="sxs-lookup"><span data-stu-id="582b2-232">Move the following files from Server A to Server B using Windows Explorer.</span></span>

    -   <span data-ttu-id="582b2-233">MBAM 合規性狀態資料庫資料 .bak</span><span class="sxs-lookup"><span data-stu-id="582b2-233">MBAM Compliance Status Database Data.bak</span></span>

2.  <span data-ttu-id="582b2-234">若要自動化此程式，您可以使用 Windows PowerShell 輸入類似以下的命令列：</span><span class="sxs-lookup"><span data-stu-id="582b2-234">To automate this procedure, you can use Windows PowerShell to enter a command line that is similar to the following:</span></span>

    `PS C:\> Copy-Item “Z:\MBAM Compliance Status Database Data.bak” \\$SERVERNAME$\$DESTINATIONSHARE$`

    **<span data-ttu-id="582b2-235">注意</span><span class="sxs-lookup"><span data-stu-id="582b2-235">Note</span></span>**  
    <span data-ttu-id="582b2-236">在上述範例中，將下列值取代為符合您環境的專案：</span><span class="sxs-lookup"><span data-stu-id="582b2-236">Replace the following values in the example above with those that match your environment:</span></span>

    -   <span data-ttu-id="582b2-237">$SERVERNAME $-輸入要將檔案複製到其中的伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="582b2-237">$SERVERNAME$ - Enter the server name where the files will be copied to.</span></span>

    -   <span data-ttu-id="582b2-238">$DESTINATIONSHARE $-輸入要將檔案複製到其中的共用名稱稱和路徑。</span><span class="sxs-lookup"><span data-stu-id="582b2-238">$DESTINATIONSHARE$ - Enter the name of share and path where the files will be copied to.</span></span>



**<span data-ttu-id="582b2-239">在伺服器 B 上還原合規性和審核資料庫</span><span class="sxs-lookup"><span data-stu-id="582b2-239">Restore the Compliance and Audit Database on Server B</span></span>**

1.  <span data-ttu-id="582b2-240">在伺服器 B 上使用 SQL Server Management Studio 及名為 [**還原資料庫**] 的工作來還原合規性和審核資料庫。</span><span class="sxs-lookup"><span data-stu-id="582b2-240">Restore the Compliance and Audit Database on Server B by using SQL Server Management Studio and the task named **Restore Database**.</span></span>

2.  <span data-ttu-id="582b2-241">完成工作後，請選取 [**發件**人] 選項，然後使用 [Add] （**新增**）命令選取 MBAM 合規性狀態資料庫資料 .bak 檔案。</span><span class="sxs-lookup"><span data-stu-id="582b2-241">Once the task has been completed, select the database backup file by selecting the **From Device** option and then use the **Add** command to select the MBAM Compliance Status Database Data.bak file.</span></span> <span data-ttu-id="582b2-242">選取 **[確定]** 以完成還原程式。</span><span class="sxs-lookup"><span data-stu-id="582b2-242">Select **OK** to complete the restoration process.</span></span>

3.  <span data-ttu-id="582b2-243">若要自動化此程式，請建立包含下列 SQL 腳本的 SQL 檔案（.sql）：</span><span class="sxs-lookup"><span data-stu-id="582b2-243">To automate this procedure, create a SQL file (.sql) that contains the following-SQL script:</span></span>

    ```sql
    -- Create MBAM Compliance Status Database Data logical backup devices. 

    Use master

    GO

    -- Restore the MBAM Compliance Status database data files.

    RESTORE DATABASE [MBAM Compliance Status]

       FROM DISK = 'C:\test\MBAM Compliance Status Database Data.bak'

       WITH REPLACE
    ```

4.  <span data-ttu-id="582b2-244">使用與下列類似的 Windows PowerShell 命令列來執行 SQL 檔案：</span><span class="sxs-lookup"><span data-stu-id="582b2-244">Run the SQL File by using a Windows PowerShell command line that is similar to the following:</span></span>

    `PS C:\> Invoke-Sqlcmd -InputFile "Z:\RestoreMBAMComplianceStatusDatabaseScript.sql" -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$`

    **<span data-ttu-id="582b2-245">注意</span><span class="sxs-lookup"><span data-stu-id="582b2-245">Note</span></span>**  
    <span data-ttu-id="582b2-246">在上述範例中，將下列值取代為符合您環境的專案：</span><span class="sxs-lookup"><span data-stu-id="582b2-246">Replace the following value in the example above with those that match your environment:</span></span>

    -   <span data-ttu-id="582b2-247">$SERVERNAME $ \ \ $SQLINSTANCENAME $-輸入要將合規性和審核資料庫還原至其中的伺服器名稱和實例。</span><span class="sxs-lookup"><span data-stu-id="582b2-247">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the server name and instance where the Compliance and Audit Database will be restored to.</span></span>



**<span data-ttu-id="582b2-248">在伺服器 B 上設定對合規性和審核資料庫的存取權</span><span class="sxs-lookup"><span data-stu-id="582b2-248">Configure Access to the Compliance and Audit Database on Server B</span></span>**

1.  <span data-ttu-id="582b2-249">在伺服器 B 上，使用 [伺服器管理員] 中的 [本機使用者和群組] 管理單元，將執行 MBAM 管理和監控功能的每個伺服器上的電腦帳戶新增到名為 [ **MBAM 合規性狀態 DB 存取**] 的本機群組。</span><span class="sxs-lookup"><span data-stu-id="582b2-249">On Server B, use the Local user and Groups snap-in from Server Manager to add the computer accounts from each server that is running the MBAM Administration and Monitoring feature to the local group named **MBAM Compliance Status DB Access**.</span></span>

2.  <span data-ttu-id="582b2-250">確認 SQL 登入**MBAM 相容性審核資料庫存取**已還原的資料庫已對應至登入名稱 **$MACHINENAME $ \\ MBAM 合規性審核資料庫存取**。</span><span class="sxs-lookup"><span data-stu-id="582b2-250">Verify that the SQL login **MBAM Compliance Auditing DB Access** on the restored database is mapped to the login name **$MachineName$\\ MBAM Compliance Auditing DB Access**.</span></span> <span data-ttu-id="582b2-251">如果未如所述對應，請使用類似的群組成員資格建立另一個登入，然後將它對應至登入名稱 **$MachineName $ \ \ MBAM 合規性審核資料庫存取**。</span><span class="sxs-lookup"><span data-stu-id="582b2-251">If it is not mapped as described, create another login with similar group memberships, and map it to the login name **$MachineName$\\ MBAM Compliance Auditing DB Access**.</span></span>

3.  <span data-ttu-id="582b2-252">若要自動化此程式，您可以使用 Windows PowerShell 在伺服器 B 上輸入如下所示的命令列：</span><span class="sxs-lookup"><span data-stu-id="582b2-252">To automate this procedure, you can use Windows PowerShell to enter a command line on Server B that is similar to the following:</span></span>

    `PS C:\> net localgroup "MBAM Compliance Auditing DB Access" $DOMAIN$\$SERVERNAME$$  /add`

    `PS C:\> net localgroup "MBAM Compliance Auditing DB Access" $DOMAIN$\$REPORTSUSERNAME$  /add`

    **<span data-ttu-id="582b2-253">注意</span><span class="sxs-lookup"><span data-stu-id="582b2-253">Note</span></span>**  
    <span data-ttu-id="582b2-254">請以適用于您環境的值取代上述範例中的下列值：</span><span class="sxs-lookup"><span data-stu-id="582b2-254">Replace the following values in the example above with the applicable values for your environment:</span></span>

    -   <span data-ttu-id="582b2-255">$DOMAIN $ \ \ $SERVERNAME $ $-輸入 MBAM 管理和監視伺服器的網域和電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="582b2-255">$DOMAIN$\\$SERVERNAME$$ - Enter the domain and machine name of the MBAM Administration and Monitoring Server.</span></span> <span data-ttu-id="582b2-256">伺服器名稱必須後接「$」，如範例所示。</span><span class="sxs-lookup"><span data-stu-id="582b2-256">The server name must be followed by a “$” as shown in the example.</span></span> <span data-ttu-id="582b2-257">（例如，MyDomain\\MyServerName1 $）</span><span class="sxs-lookup"><span data-stu-id="582b2-257">(for example, MyDomain\\MyServerName1$)</span></span>

    -   <span data-ttu-id="582b2-258">$DOMAIN $ \ \ $REPORTSUSERNAME $-輸入用來設定合規性和審核報告之資料來源的使用者帳戶名稱。</span><span class="sxs-lookup"><span data-stu-id="582b2-258">$DOMAIN$\\$REPORTSUSERNAME$ - Enter the user account name that was used to configure the data source for the Compliance and Audit Reports.</span></span>



~~~
The command line for adding the servers to the MBAM Compliance and Audit Database access local group must be run for each Administration and Monitoring Server that will be accessing the database in your environment.
~~~

**<span data-ttu-id="582b2-259">更新 MBAM 管理和監視伺服器上的資料庫連線資料</span><span class="sxs-lookup"><span data-stu-id="582b2-259">Update the Database Connection Data on MBAM Administration and Monitoring Servers</span></span>**

1.  <span data-ttu-id="582b2-260">在執行 MBAM 管理和監視功能的每個伺服器上，使用 Internet Information Services （IIS）管理員主控台來更新下列應用程式的連線字串資訊，這些應用程式是託管于 [管理] 和 [監視] 網站：</span><span class="sxs-lookup"><span data-stu-id="582b2-260">On each server that is running the MBAM Administration and Monitoring feature, use the Internet Information Services (IIS) Manager console to update the connection string information for the following applications, which are hosted in the Administration and Monitoring website:</span></span>

    -   <span data-ttu-id="582b2-261">MBAMAdministrationService</span><span class="sxs-lookup"><span data-stu-id="582b2-261">MBAMAdministrationService</span></span>

    -   <span data-ttu-id="582b2-262">MBAMComplianceStatusService</span><span class="sxs-lookup"><span data-stu-id="582b2-262">MBAMComplianceStatusService</span></span>

2.  <span data-ttu-id="582b2-263">選取每個應用程式，並使用 [設定**編輯器**] 功能（位於**功能視圖**的 [**管理**] 區段底下）。</span><span class="sxs-lookup"><span data-stu-id="582b2-263">Select each application and use the **Configuration Editor** feature, which is located under the **Management** section of the **Feature View**.</span></span>

3.  <span data-ttu-id="582b2-264">從**區段清單**控制項選取 [ **configurationStrings** ] 選項。</span><span class="sxs-lookup"><span data-stu-id="582b2-264">Select the **configurationStrings** option from the **Section list** control.</span></span>

4.  <span data-ttu-id="582b2-265">選取名為 **（集合）** 的列，然後選取列右側的按鈕來開啟**集合編輯器**。</span><span class="sxs-lookup"><span data-stu-id="582b2-265">Select the row named **(Collection)**, and open the **Collection Editor** by selecting the button on the right side of the row.</span></span>

5.  <span data-ttu-id="582b2-266">在**集合編輯器**中，更新 MBAMAdministrationService 應用程式的設定時，請選取名為**ComplianceStatusConnectionString**的列，或者在更新 MBAMComplianceStatusService 的設定時，選取名為**BitLockerManagement**的列。</span><span class="sxs-lookup"><span data-stu-id="582b2-266">In the **Collection Editor**, select the row named **ComplianceStatusConnectionString** when updating the configuration for the MBAMAdministrationService application, or the row named **Microsoft.Windows.Mdop.BitLockerManagement.StatusReportDataStore.ConnectionString** when updating the configuration for the MBAMComplianceStatusService.</span></span>

6.  <span data-ttu-id="582b2-267">更新**configurationStrings**屬性的**資料來源 =** 值，以列出已將復原資料庫移動到其中的伺服器和實例名稱（例如 $SERVERNAME $ \ \ $SQLINSTANCENAME）。</span><span class="sxs-lookup"><span data-stu-id="582b2-267">Update the **Data Source=** value for the **configurationStrings** property to list the name of the server and instance (for example, $SERVERNAME$\\$SQLINSTANCENAME) to which the Recovery Database was moved.</span></span>

7.  <span data-ttu-id="582b2-268">若要自動化此程式，您可以使用 Windows 在與下列類似的每個管理和監視伺服器上輸入命令列：</span><span class="sxs-lookup"><span data-stu-id="582b2-268">To automate this procedure, you can use Windows to enter a command line on each Administration and Monitoring Server that is similar to the following:</span></span>

    `PS C:\> Set-WebConfigurationProperty '/connectionStrings/add[@name="ComplianceStatusConnectionString"]' -PSPath "IIS:\sites\Microsoft Bitlocker Administration and Monitoring\MBAMAdministrationService" -Name "connectionString" -Value "Data Source=$SERVERNAME$\$SQLINSTANCENAME$;Initial Catalog=MBAM Compliance Status;Integrated Security=SSPI;"`

    `PS C:\> Set-WebConfigurationProperty '/connectionStrings/add[@name="Microsoft.Windows.Mdop.BitLockerManagement.StatusReportDataStore.ConnectionString"]' -PSPath "IIS:\sites\Microsoft Bitlocker Administration and Monitoring\MBAMComplianceStatusService" -Name "connectionString" -Value "Data Source=$SERVERNAME$\$SQLINSTANCENAME;Initial Catalog=MBAM Compliance Status;Integrated Security=SSPI;"`

    **<span data-ttu-id="582b2-269">注意</span><span class="sxs-lookup"><span data-stu-id="582b2-269">Note</span></span>**  
    <span data-ttu-id="582b2-270">在上述範例中，將下列值取代為符合您環境的專案：</span><span class="sxs-lookup"><span data-stu-id="582b2-270">Replace the following values in the example above with those that match your environment:</span></span>

    -   <span data-ttu-id="582b2-271">$SERVERNAME $ \ \ $SQLINSTANCENAME $-輸入恢復資料庫所在的伺服器名稱和實例。</span><span class="sxs-lookup"><span data-stu-id="582b2-271">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the server name and instance where the Recovery Database is located.</span></span>



**<span data-ttu-id="582b2-272">繼續 MBAM 管理和監視網站的所有實例</span><span class="sxs-lookup"><span data-stu-id="582b2-272">Resume All Instances of the MBAM Administration and Monitoring Website</span></span>**

1.  <span data-ttu-id="582b2-273">在執行 MBAM 管理和監視功能的每個伺服器上，使用 Internet Information Services （IIS）管理員主控台來啟動名為**Microsoft BitLocker 管理和監視**的 MBAM 網站。</span><span class="sxs-lookup"><span data-stu-id="582b2-273">On each server that is running the MBAM Administration and Monitoring feature, use the Internet Information Services (IIS) Manager console to start the MBAM website named **Microsoft BitLocker Administration and Monitoring**.</span></span>

2.  <span data-ttu-id="582b2-274">若要自動化此程式，您可以使用 Windows PowerShell 輸入類似以下的命令列：</span><span class="sxs-lookup"><span data-stu-id="582b2-274">To automate this procedure, you can use Windows PowerShell to enter a command line that is similar to the following:</span></span>

    `PS C:\> Start-Website “Microsoft BitLocker Administration and Monitoring”`

## <span data-ttu-id="582b2-275">移動合規性與審計報告</span><span class="sxs-lookup"><span data-stu-id="582b2-275">Moving the Compliance and Audit Reports</span></span>


<span data-ttu-id="582b2-276">如果您想要將 MBAM 合規性和審核報告從一部電腦移到另一台電腦（也就是將報表從伺服器 A 移至伺服器 B），請使用下列程式，其中包含下列高級步驟：</span><span class="sxs-lookup"><span data-stu-id="582b2-276">If you want to move the MBAM Compliance and Audit Reports from one computer to another (that is, move the reports from Server A to Server B), use the following procedure, which includes the following high-level steps:</span></span>

1.  <span data-ttu-id="582b2-277">在伺服器 B 上執行 MBAM 安裝程式。</span><span class="sxs-lookup"><span data-stu-id="582b2-277">Run MBAM setup on Server B.</span></span>

2.  <span data-ttu-id="582b2-278">在伺服器 B 上設定對合規性和審核報告的存取權。</span><span class="sxs-lookup"><span data-stu-id="582b2-278">Configure access to the Compliance and Audit Reports on Server B.</span></span>

3.  <span data-ttu-id="582b2-279">停止 MBAM 管理和監視網站的所有實例。</span><span class="sxs-lookup"><span data-stu-id="582b2-279">Stop all instances of the MBAM Administration and Monitoring website.</span></span>

4.  <span data-ttu-id="582b2-280">更新 MBAM 管理和監視伺服器上的報表連線資料。</span><span class="sxs-lookup"><span data-stu-id="582b2-280">Update the reports connection data on MBAM Administration and Monitoring servers.</span></span>

5.  <span data-ttu-id="582b2-281">繼續 MBAM 管理和監視網站的所有實例。</span><span class="sxs-lookup"><span data-stu-id="582b2-281">Resume all instances of the MBAM Administration and Monitoring website.</span></span>

**<span data-ttu-id="582b2-282">在伺服器 B 上執行 MBAM 設定</span><span class="sxs-lookup"><span data-stu-id="582b2-282">Run MBAM Setup on Server B</span></span>**

1.  <span data-ttu-id="582b2-283">在伺服器 B 上執行 MBAM 安裝程式，然後只選取 [**合規性] 和 [審核報告**] 功能進行安裝。</span><span class="sxs-lookup"><span data-stu-id="582b2-283">Run MBAM Setup on Server B and select only the **Compliance and Audit Reports** feature for installation.</span></span>

2.  <span data-ttu-id="582b2-284">若要自動化此程式，您可以使用 Windows PowerShell 輸入類似以下的命令列：</span><span class="sxs-lookup"><span data-stu-id="582b2-284">To automate this procedure, you can use Windows PowerShell to enter a command line that is similar to the following:</span></span>

    `PS C:\> MbamSetup.exe /qn I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 AddLocal=Reports COMPLIDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ REPORTS_USERACCOUNTPW=$PASSWORD$ TOPOLOGY=$X$`

    **<span data-ttu-id="582b2-285">注意</span><span class="sxs-lookup"><span data-stu-id="582b2-285">Note</span></span>**  
    <span data-ttu-id="582b2-286">在上述範例中，將下列值取代為符合您環境的專案：</span><span class="sxs-lookup"><span data-stu-id="582b2-286">Replace the following values in the example above with those that match your environment:</span></span>

    -   <span data-ttu-id="582b2-287">$SERVERNAME $ \ \ $SQLINSTANCENAME $-輸入合規性和審核資料庫所在的伺服器名稱和實例。</span><span class="sxs-lookup"><span data-stu-id="582b2-287">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the server name and instance where the Compliance and Audit Database is located.</span></span>

    -   <span data-ttu-id="582b2-288">$DOMAIN $ \ \ $USERNAME $-輸入將由合規性和審核報告功能用來連線至合規性和審核資料庫的網域和使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="582b2-288">$DOMAIN$\\$USERNAME$ - Enter the domain and user name that will be used by the Compliance and Audit Reports feature to connect to the Compliance and Audit Database.</span></span>

    -   <span data-ttu-id="582b2-289">$PASSWORD $-輸入將用來連線至合規性和審核資料庫之使用者帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="582b2-289">$PASSWORD$ - Enter the password of the user account that will be used to connect to the Compliance and Audit Database.</span></span>

    -   <span data-ttu-id="582b2-290">如果您要安裝 MBAM 獨立拓朴，請 $X $-輸入**0** ; 如果您要安裝 MBAM Configuration Manager 拓撲，則為**1** 。</span><span class="sxs-lookup"><span data-stu-id="582b2-290">$X$ - Enter **0** if you are installing the MBAM Stand-alone topology, or **1** if you are installing the MBAM Configuration Manager topology.</span></span>



**<span data-ttu-id="582b2-291">在伺服器 B 上設定合規性和審核報告的存取權</span><span class="sxs-lookup"><span data-stu-id="582b2-291">Configure Access to the Compliance and Audit Reports on Server B</span></span>**

1.  <span data-ttu-id="582b2-292">在伺服器 B 上，使用 [伺服器管理員] 中的 [本機使用者和群組] 管理單元，新增能夠存取合規性和審核報告的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="582b2-292">On Server B, use the Local user and Groups snap-in from Server Manager to add the user accounts that will have access to the Compliance and Audit Reports.</span></span> <span data-ttu-id="582b2-293">將使用者帳戶新增到名為 MBAM 報告使用者的本機群組。</span><span class="sxs-lookup"><span data-stu-id="582b2-293">Add the user accounts to the local group named MBAM Report Users.</span></span>

2.  <span data-ttu-id="582b2-294">若要自動化此程式，您可以使用 Windows PowerShell 在伺服器 B 上輸入如下所示的命令列：</span><span class="sxs-lookup"><span data-stu-id="582b2-294">To automate this procedure, you can use Windows PowerShell to enter a command line on Server B that is similar to the following:</span></span>

    `PS C:\> net localgroup "MBAM Report Users" $DOMAIN$\$REPORTSUSERNAME$  /add`

    **<span data-ttu-id="582b2-295">注意</span><span class="sxs-lookup"><span data-stu-id="582b2-295">Note</span></span>**  
    <span data-ttu-id="582b2-296">請以適用于您環境的值取代上述範例中的下列值：</span><span class="sxs-lookup"><span data-stu-id="582b2-296">Replace the following values in the example above with the applicable values for your environment:</span></span>

    -   <span data-ttu-id="582b2-297">$DOMAIN $ \ \ $REPORTSUSERNAME $-輸入用來設定合規性和審核報告之資料來源的使用者帳戶名稱。</span><span class="sxs-lookup"><span data-stu-id="582b2-297">$DOMAIN$\\$REPORTSUSERNAME$ - Enter the user account name that was used to configure the data source for the Compliance and Audit reports.</span></span>



~~~
The command line for adding the users to the MBAM Report Users local group must be run for each user that will be accessing the reports in your environment.
~~~

**<span data-ttu-id="582b2-298">停止 MBAM 管理和監視網站的所有實例</span><span class="sxs-lookup"><span data-stu-id="582b2-298">Stop All Instances of the MBAM Administration and Monitoring Website</span></span>**

1.  <span data-ttu-id="582b2-299">在執行 MBAM 管理和監視伺服器功能的每個伺服器上，使用 Internet Information Services （IIS）管理員主控台來停止名為**Microsoft BitLocker 管理和監視**的 MBAM 網站。</span><span class="sxs-lookup"><span data-stu-id="582b2-299">On each server that is running the MBAM Administration and Monitoring Server feature, use the Internet Information Services (IIS) Manager console to stop the MBAM website named **Microsoft BitLocker Administration and Monitoring**.</span></span>

2.  <span data-ttu-id="582b2-300">若要自動化此程式，您可以使用 Windows PowerShell 輸入類似以下的命令列：</span><span class="sxs-lookup"><span data-stu-id="582b2-300">To automate this procedure, you can use Windows PowerShell to enter a command line that is similar to the following:</span></span>

    `PS C:\> Stop-Website “Microsoft BitLocker Administration and Monitoring”`

**<span data-ttu-id="582b2-301">更新 MBAM 管理和監視伺服器上的資料庫連線資料</span><span class="sxs-lookup"><span data-stu-id="582b2-301">Update the Database Connection Data on the MBAM Administration and Monitoring Servers</span></span>**

1. <span data-ttu-id="582b2-302">在執行 MBAM 管理和監視伺服器功能的每個伺服器上，使用 [網際網路資訊服務（IIS）管理員] 主控台來更新合規性和審核報告 URL。</span><span class="sxs-lookup"><span data-stu-id="582b2-302">On each server that is running the MBAM Administration and Monitoring Server feature, use the Internet Information Services (IIS) Manager console to update the Compliance and Audit Reports URL.</span></span>

2. <span data-ttu-id="582b2-303">選取 [ **Microsoft BitLocker 管理及監視**網站]，然後使用 [**功能] 視圖**[**管理**] 區段底下的 [設定**編輯器**] 功能。</span><span class="sxs-lookup"><span data-stu-id="582b2-303">Select the **Microsoft BitLocker Administration and Monitoring** website, and use the **Configuration Editor** feature that is location under the **Management** section of the **Feature View**.</span></span>

3. <span data-ttu-id="582b2-304">從**區段清單**控制項選取 [ **appSettings** ] 選項。</span><span class="sxs-lookup"><span data-stu-id="582b2-304">Select the **appSettings** option from the **Section list** control.</span></span>

4. <span data-ttu-id="582b2-305">選取名為 **（集合）** 的列，然後選取列右側的按鈕來開啟**集合編輯器**。</span><span class="sxs-lookup"><span data-stu-id="582b2-305">Select the row named **(Collection)** and open the **Collection Editor** by selecting the button on the right side of the row.</span></span>

5. <span data-ttu-id="582b2-306">在**集合編輯器**中，選取名為**Mbam**的資料列。</span><span class="sxs-lookup"><span data-stu-id="582b2-306">In the **Collection Editor**, select the row named **Microsoft.Mbam.Reports.Url**.</span></span>

6. <span data-ttu-id="582b2-307">更新**Mbam**的值，以反映伺服器 B 的伺服器名稱。如果 [規範] 和 [審核報告] 功能已安裝在命名的 SQL Reporting Services 實例上，請務必在 URL 中新增或更新實例的名稱（例如，HTTP://$SERVERNAME $/ReportServer\_ $ SQLSRSINSTANCENAME $/Pages....）</span><span class="sxs-lookup"><span data-stu-id="582b2-307">Update the value for **Microsoft.Mbam.Reports.Url** to reflect the server name for Server B. If the Compliance and Audit Reports feature was installed on a named SQL Reporting Services instance, be sure to add or update the name of the instance to the URL (for example, http://$SERVERNAME$/ReportServer\_$SQLSRSINSTANCENAME$/Pages....)</span></span>

7. <span data-ttu-id="582b2-308">若要自動化此程式，您可以使用 Windows PowerShell，在與下列類似的每個管理和監視伺服器上輸入命令列：</span><span class="sxs-lookup"><span data-stu-id="582b2-308">To automate this procedure, you can use Windows PowerShell to enter a command line on each Administration and Monitoring Server that is similar to the following:</span></span>

   `PS C:\> Set-WebConfigurationProperty '/appSettings/add[@key="Microsoft.Mbam.Reports.Url"]' -PSPath "IIS:\ \sites\Microsoft Bitlocker Administration and Monitoring\HelpDesk" -Name "Value" -Value “http://$SERVERNAME$/ReportServer_$SRSINSTANCENAME$/Pages/ReportViewer.aspx?/ Microsoft+BitLocker+Administration+and+Monitoring/”`

   **<span data-ttu-id="582b2-309">注意</span><span class="sxs-lookup"><span data-stu-id="582b2-309">Note</span></span>**  
   <span data-ttu-id="582b2-310">在上述範例中，將下列值取代為符合您環境的專案：</span><span class="sxs-lookup"><span data-stu-id="582b2-310">Replace the following values in the example above with those that match your environment:</span></span>

   -   <span data-ttu-id="582b2-311">$SERVERNAME $-輸入已安裝 [合規性] 與 [審核報告] 的伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="582b2-311">$SERVERNAME$ - Enter the name of the server name to which the Compliance and Audit Reports were installed.</span></span>

   -   <span data-ttu-id="582b2-312">$SRSINSTANCENAME $-輸入已安裝合規性和審核報告之 SQL Reporting Services 實例的名稱。</span><span class="sxs-lookup"><span data-stu-id="582b2-312">$SRSINSTANCENAME$ - Enter the name of the SQL Reporting Services instance to which the Compliance and Audit Reports were installed.</span></span>



**<span data-ttu-id="582b2-313">繼續 MBAM 管理和監視網站的所有實例</span><span class="sxs-lookup"><span data-stu-id="582b2-313">Resume All Instances of the MBAM Administration and Monitoring Website</span></span>**

1.  <span data-ttu-id="582b2-314">在執行 MBAM 管理和監視伺服器功能的每個伺服器上，使用 Internet Information Services （IIS）管理員主控台來啟動名為**Microsoft BitLocker 管理和監視**的 MBAM 網站。</span><span class="sxs-lookup"><span data-stu-id="582b2-314">On each server that is running the MBAM Administration and Monitoring Server feature, use the Internet Information Services (IIS) Manager console to Start the MBAM website named **Microsoft BitLocker Administration and Monitoring**.</span></span>

2.  <span data-ttu-id="582b2-315">若要自動化此程式，您可以使用 Windows PowerShell 輸入類似以下的命令列：</span><span class="sxs-lookup"><span data-stu-id="582b2-315">To automate this procedure, you can use Windows PowerShell to enter a command line that is similar to the following:</span></span>

    `PS C:\> Start-Website “Microsoft BitLocker Administration and Monitoring”`

    **<span data-ttu-id="582b2-316">注意</span><span class="sxs-lookup"><span data-stu-id="582b2-316">Note</span></span>**  
    <span data-ttu-id="582b2-317">若要執行此命令列，您必須將 PowerShell 的 IIS 模組新增至目前的 PowerShell 實例。</span><span class="sxs-lookup"><span data-stu-id="582b2-317">To run this command line, you must add the IIS Module for PowerShell to current instance of PowerShell.</span></span> <span data-ttu-id="582b2-318">此外，您必須更新 PowerShell 執行原則，才能執行腳本。</span><span class="sxs-lookup"><span data-stu-id="582b2-318">In addition, you must update the PowerShell execution policy to enable scripts to be run.</span></span>



## <span data-ttu-id="582b2-319">移動 [管理及監視] 功能</span><span class="sxs-lookup"><span data-stu-id="582b2-319">Moving the Administration and Monitoring Feature</span></span>


<span data-ttu-id="582b2-320">如果您想要將 MBAM 管理和監控報告功能從一部電腦移到另一台電腦（也就是將功能從伺服器 A 移到伺服器 B），請使用下列程式，其中包括下列高級步驟：</span><span class="sxs-lookup"><span data-stu-id="582b2-320">If you want to move the MBAM Administration and Monitoring Reports feature from one computer to another (that is, move the feature from Server A to Server B), use the following procedure, which includes the following high-level steps:</span></span>

1.  <span data-ttu-id="582b2-321">在伺服器 B 上執行 MBAM 安裝程式。</span><span class="sxs-lookup"><span data-stu-id="582b2-321">Run MBAM Setup on Server B.</span></span>

2.  <span data-ttu-id="582b2-322">在伺服器 B 上設定對資料庫的存取權。</span><span class="sxs-lookup"><span data-stu-id="582b2-322">Configure access to the Database on Server B.</span></span>

**<span data-ttu-id="582b2-323">在伺服器 B 上執行 MBAM 設定</span><span class="sxs-lookup"><span data-stu-id="582b2-323">Run MBAM Setup on Server B</span></span>**

1.  <span data-ttu-id="582b2-324">在伺服器 B 上執行 MBAM 安裝程式，然後只選取 [**管理及監視伺服器**] 功能進行安裝。</span><span class="sxs-lookup"><span data-stu-id="582b2-324">Run MBAM Setup on Server B and select only the **Administration and Monitoring Server** feature for installation.</span></span>

2.  <span data-ttu-id="582b2-325">若要自動化此程式，您可以使用 Windows PowerShell 輸入類似以下的命令列：</span><span class="sxs-lookup"><span data-stu-id="582b2-325">To automate this procedure, you can use Windows PowerShell to enter a command line that is similar to the following:</span></span>

    `PS C:\> MbamSetup.exe /qn I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 AddLocal=AdministrationMonitoringServer, COMPLIDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ RECOVERYANDHWDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ SRS_REPORTSITEURL=$REPORTSSERVERURL$ TOPOLOGY=$X$`

    **<span data-ttu-id="582b2-326">注意</span><span class="sxs-lookup"><span data-stu-id="582b2-326">Note</span></span>**  
    <span data-ttu-id="582b2-327">在上述範例中，將下列值取代為符合您環境的專案：</span><span class="sxs-lookup"><span data-stu-id="582b2-327">Replace the following values in the example above with those that match your environment:</span></span>

    -   <span data-ttu-id="582b2-328">$SERVERNAME $ \ \ $SQLINSTANCENAME $-若為 COMPLIDB \ _SQLINSTANCE 參數，請輸入合規性和審核資料庫所在的伺服器名稱和實例。</span><span class="sxs-lookup"><span data-stu-id="582b2-328">$SERVERNAME$\\$SQLINSTANCENAME$ - For the COMPLIDB\_SQLINSTANCE parameter, enter the server name and instance where the Compliance and Audit Database is located.</span></span> <span data-ttu-id="582b2-329">針對 RECOVERYANDHWDB \ _SQLINSTANCE 參數，輸入恢復資料庫所在的伺服器名稱和實例。</span><span class="sxs-lookup"><span data-stu-id="582b2-329">For the RECOVERYANDHWDB\_SQLINSTANCE parameter, enter the server name and instance where the Recovery Database is located.</span></span>

    -   <span data-ttu-id="582b2-330">$DOMAIN $ \ \ $USERNAME $-輸入將由合規性和審核報告功能用來連線至合規性和審核資料庫的網域和使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="582b2-330">$DOMAIN$\\$USERNAME$ - Enter the domain and user name that will be used by the Compliance and Audit Reports feature to connect to the Compliance and Audit Database.</span></span>

    -   <span data-ttu-id="582b2-331">$ REPORTSSERVERURL $-輸入 SQL Reporting Services 網站之家用位置的 URL。</span><span class="sxs-lookup"><span data-stu-id="582b2-331">$ REPORTSSERVERURL$ - Enter the URL for the Home location of the SQL Reporting Service website.</span></span> <span data-ttu-id="582b2-332">如果報告已安裝到預設的 SRS 實例，URL 格式將會採用「HTTP://$SERVERNAME $/ReportServer」格式。</span><span class="sxs-lookup"><span data-stu-id="582b2-332">If the reports were installed to a default SRS instance, the URL format will have the format “http:// $SERVERNAME$/ReportServer”.</span></span> <span data-ttu-id="582b2-333">如果報告已安裝到預設的 SRS 實例，URL 格式的格式會為「HTTP://$SERVERNAME $/ReportServer\_ $ SQLINSTANCENAME $」。</span><span class="sxs-lookup"><span data-stu-id="582b2-333">If the reports were installed to a default SRS instance, the URL format will have the format “http://$SERVERNAME$/ReportServer\_$SQLINSTANCENAME$”.</span></span>

    -   <span data-ttu-id="582b2-334">如果您要安裝 MBAM 獨立拓朴，請 $X $-輸入**0** ; 如果您要安裝 MBAM Configuration Manager 拓撲，則為**1** 。</span><span class="sxs-lookup"><span data-stu-id="582b2-334">$X$ - Enter **0** if you are installing the MBAM Stand-alone topology, or **1** if you are installing the MBAM Configuration Manager topology.</span></span>



**<span data-ttu-id="582b2-335">設定資料庫的存取權</span><span class="sxs-lookup"><span data-stu-id="582b2-335">Configure Access to the Databases</span></span>**

1.  <span data-ttu-id="582b2-336">在已部署復原資料庫及合規性和審核資料庫的伺服器上，請使用 [伺服器管理員] 中的 [本機使用者和群組] 管理單元，將執行 MBAM 管理和監視伺服器功能的每個伺服器上的電腦帳戶新增到名為 MBAM 復原與**硬體資料庫存取**（復原 DB 伺服器）及**MBAM 合規性狀態 DB 存取**（合規性和審核資料庫伺服器）的</span><span class="sxs-lookup"><span data-stu-id="582b2-336">On the server or servers where the Recovery Database and Compliance and Audit Database are deployed, use the Local user and Groups snap-in from Server Manager to add the computer accounts from each server that is running the MBAM Administration and Monitoring Server feature to the local groups named **MBAM Recovery and Hardware DB Access** (Recovery DB Server) and **MBAM Compliance Status DB Access** (Compliance and Audit Database Server).</span></span>

2.  <span data-ttu-id="582b2-337">若要自動化此程式，您可以使用 Windows PowerShell，在部署合規性和審核資料庫的伺服器上，輸入如下所示的命令列。</span><span class="sxs-lookup"><span data-stu-id="582b2-337">To automate this procedure, you can use Windows PowerShell to enter a command line, that is similar to the following, on the server where the Compliance and Audit Database was deployed.</span></span>

    `PS C:\> net localgroup "MBAM Compliance Auditing DB Access" $DOMAIN$\$SERVERNAME$$  /add`

3.  <span data-ttu-id="582b2-338">在部署復原資料庫的伺服器上，您可以使用 Windows PowerShell 來輸入類似以下的命令列：</span><span class="sxs-lookup"><span data-stu-id="582b2-338">On the server where the Recovery database was deployed, you can use Windows PowerShell to enter a command line that is similar to the following:</span></span>

    `PS C:\> net localgroup "MBAM Recovery and Hardware DB Access" $DOMAIN$\$SERVERNAME$$  /add`

    **<span data-ttu-id="582b2-339">注意</span><span class="sxs-lookup"><span data-stu-id="582b2-339">Note</span></span>**  
    <span data-ttu-id="582b2-340">將上述範例中的下列值取代為您的環境適用的值：</span><span class="sxs-lookup"><span data-stu-id="582b2-340">Replace the following value in the example above with the applicable values for your environment:</span></span>

    -   <span data-ttu-id="582b2-341">$DOMAIN $ \ \ $SERVERNAME $ $-輸入管理和監視伺服器的網域和電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="582b2-341">$DOMAIN$\\$SERVERNAME$$ - Enter the domain and machine name of the Administration and Monitoring Server.</span></span> <span data-ttu-id="582b2-342">伺服器名稱必須後接 "$" 符號，如範例中所示（例如，MyDomain\\MyServerName1 $）。</span><span class="sxs-lookup"><span data-stu-id="582b2-342">The server name must be followed by a “$” symbol, as shown in the example (for example, MyDomain\\MyServerName1$).</span></span>

    -   <span data-ttu-id="582b2-343">$DOMAIN $ \ \ $REPORTSUSERNAME $-輸入用來設定合規性和審核報告之資料來源的使用者帳戶名稱。</span><span class="sxs-lookup"><span data-stu-id="582b2-343">$DOMAIN$\\$REPORTSUSERNAME$ - Enter the user account name that was used to configure the data source for the Compliance and Audit Reports.</span></span>



~~~
The command lines that are listed for adding server computer accounts to the MBAM local groups must be run for each Administration and Monitoring Server that will be accessing the databases in your environment.
~~~

## <span data-ttu-id="582b2-344">相關主題</span><span class="sxs-lookup"><span data-stu-id="582b2-344">Related topics</span></span>


[<span data-ttu-id="582b2-345">維護 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="582b2-345">Maintaining MBAM 2.0</span></span>](maintaining-mbam-20-mbam-2.md)









