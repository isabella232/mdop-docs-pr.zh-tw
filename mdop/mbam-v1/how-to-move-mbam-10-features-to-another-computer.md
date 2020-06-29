---
title: 如何將 MBAM 1.0 功能移到其他電腦
description: 如何將 MBAM 1.0 功能移到其他電腦
author: dansimp
ms.assetid: e1907d92-6b42-4ba3-b0e4-60a9cc8285cc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 874c3983220f341e39fa5fb7c60f655e2f208082
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800221"
---
# <span data-ttu-id="40975-103">如何將 MBAM 1.0 功能移到其他電腦</span><span class="sxs-lookup"><span data-stu-id="40975-103">How to Move MBAM 1.0 Features to Another Computer</span></span>


<span data-ttu-id="40975-104">本主題說明將一或多個 Microsoft BitLocker 管理和監控（MBAM）功能移至不同電腦時應採取的步驟。</span><span class="sxs-lookup"><span data-stu-id="40975-104">This topic describes the steps that you should take to move one or more Microsoft BitLocker Administration and Monitoring (MBAM) features to a different computer.</span></span> <span data-ttu-id="40975-105">當您將多個 MBAM 功能移至另一部電腦時，應依下列順序移動它們：</span><span class="sxs-lookup"><span data-stu-id="40975-105">When you move more than one MBAM feature to another computer, you should move them in the following order:</span></span>

1.  <span data-ttu-id="40975-106">恢復與硬體資料庫</span><span class="sxs-lookup"><span data-stu-id="40975-106">Recovery and Hardware Database</span></span>

2.  <span data-ttu-id="40975-107">合規性和審核資料庫</span><span class="sxs-lookup"><span data-stu-id="40975-107">Compliance and Audit Database</span></span>

3.  <span data-ttu-id="40975-108">合規性與審計報告</span><span class="sxs-lookup"><span data-stu-id="40975-108">Compliance and Audit Reports</span></span>

4.  <span data-ttu-id="40975-109">管理和監控</span><span class="sxs-lookup"><span data-stu-id="40975-109">Administration and Monitoring</span></span>

## <span data-ttu-id="40975-110">移動恢復與硬體資料庫</span><span class="sxs-lookup"><span data-stu-id="40975-110">To move the Recovery and Hardware Database</span></span>


<span data-ttu-id="40975-111">您可以使用下列程式，將 MBAM 復原和硬體資料庫從一部電腦移到另一台電腦（您可以將此 MBAM 伺服器功能從伺服器 A 移至伺服器 B）：</span><span class="sxs-lookup"><span data-stu-id="40975-111">You can use the following procedure to move the MBAM Recovery and Hardware Database from one computer to another (you can move this MBAM Server feature from Server A to Server B):</span></span>

****

1.  <span data-ttu-id="40975-112">停止 MBAM 管理和監視網站的所有實例。</span><span class="sxs-lookup"><span data-stu-id="40975-112">Stop all instances of the MBAM Administration and Monitoring web site.</span></span>

2.  <span data-ttu-id="40975-113">在伺服器 B 上執行 MBAM 設定。</span><span class="sxs-lookup"><span data-stu-id="40975-113">Run the MBAM Setup on Server B.</span></span>

3.  <span data-ttu-id="40975-114">在伺服器 A 上備份 MBAM 復原與硬體資料庫。</span><span class="sxs-lookup"><span data-stu-id="40975-114">Back up the MBAM Recovery and Hardware database on Server A.</span></span>

4.  <span data-ttu-id="40975-115">從伺服器 A MBAM 恢復和硬體資料庫至 B</span><span class="sxs-lookup"><span data-stu-id="40975-115">MBAM Recovery and Hardware database from Server A to B</span></span>

5.  <span data-ttu-id="40975-116">在伺服器 B 上還原 MBAM 復原與硬體資料庫</span><span class="sxs-lookup"><span data-stu-id="40975-116">Restore the MBAM Recovery and Hardware database on Server B</span></span>

6.  <span data-ttu-id="40975-117">在伺服器 B 上設定對 MBAM 復原和硬體資料庫的存取權</span><span class="sxs-lookup"><span data-stu-id="40975-117">Configure the access to the MBAM Recovery and Hardware database on Server B</span></span>

7.  <span data-ttu-id="40975-118">更新 MBAM 管理和監視伺服器上的資料庫連線資料</span><span class="sxs-lookup"><span data-stu-id="40975-118">Update the database connection data on MBAM Administration and Monitoring servers</span></span>

8.  <span data-ttu-id="40975-119">繼續 MBAM 管理和監控網站的所有實例</span><span class="sxs-lookup"><span data-stu-id="40975-119">Resume all instances of the MBAM Administration and Monitoring web site</span></span>

**<span data-ttu-id="40975-120">若要停止 MBAM 管理和監視網站的所有實例</span><span class="sxs-lookup"><span data-stu-id="40975-120">To stop all instances of the MBAM Administration and Monitoring website</span></span>**

1.  <span data-ttu-id="40975-121">使用 Internet Information Services （IIS）管理員主控台，在執行 MBAM 管理和監視功能的每個伺服器上停止 MBAM 網站。</span><span class="sxs-lookup"><span data-stu-id="40975-121">Use the Internet Information Services (IIS) Manager console to stop the MBAM website on each of the servers that run the MBAM Administration and Monitoring feature.</span></span> <span data-ttu-id="40975-122">MBAM 網站已命名為**Microsoft BitLocker 管理和監視**。</span><span class="sxs-lookup"><span data-stu-id="40975-122">The MBAM website is named **Microsoft BitLocker Administration and Monitoring**.</span></span>

2.  <span data-ttu-id="40975-123">若要自動化此程式，您可以使用 Windows PowerShell，在命令提示字元中使用類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="40975-123">To automate this procedure, you can use a command at the command prompt that is similar to the following, by using Windows PowerShell:</span></span>

    `PS C:\> Stop-Website “Microsoft BitLocker Administration and Monitoring”`

    **<span data-ttu-id="40975-124">注意</span><span class="sxs-lookup"><span data-stu-id="40975-124">Note</span></span>**  
    <span data-ttu-id="40975-125">若要執行此 PowerShell 命令提示字元，您必須將 PowerShell 的 IIS 模組新增到 PowerShell 的目前實例。</span><span class="sxs-lookup"><span data-stu-id="40975-125">To run this PowerShell command prompt, you must add the IIS Module for PowerShell to the current instance of PowerShell.</span></span> <span data-ttu-id="40975-126">此外，您必須更新 PowerShell 執行原則，以啟用腳本執行。</span><span class="sxs-lookup"><span data-stu-id="40975-126">In addition, you must update the PowerShell execution policy to enable the execution of scripts.</span></span>



**<span data-ttu-id="40975-127">若要在伺服器 B 上執行 MBAM 設定</span><span class="sxs-lookup"><span data-stu-id="40975-127">To run MBAM setup on Server B</span></span>**

1.  <span data-ttu-id="40975-128">在伺服器 B 上執行 [MBAM 設定]，然後選取要安裝的復原和硬體資料庫。</span><span class="sxs-lookup"><span data-stu-id="40975-128">Run the MBAM setup on Server B and select the Recovery and Hardware Database for installation.</span></span>

2.  <span data-ttu-id="40975-129">若要自動化此程式，您可以使用 Windows PowerShell，在命令提示字元中使用類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="40975-129">To automate this procedure, you can use a command at the command prompt that is similar to the following, by using Windows PowerShell:</span></span>

    `PS C:\> MbamSetup.exe /qn I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 AddLocal=KeyDatabase ADMINANDMON_MACHINENAMES=$DOMAIN$\$SERVERNAME$$ RECOVERYANDHWDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$`

    **<span data-ttu-id="40975-130">注意</span><span class="sxs-lookup"><span data-stu-id="40975-130">Note</span></span>**  
    <span data-ttu-id="40975-131">在上述範例中，將下列值取代為符合您環境的專案：</span><span class="sxs-lookup"><span data-stu-id="40975-131">Replace the following values in the example above with those that match your environment:</span></span>

    -   <span data-ttu-id="40975-132">$SERVERNAME $ \ \ $SQLINSTANCENAME $-輸入要將恢復與硬體資料庫移動到其中的伺服器和實例名稱。</span><span class="sxs-lookup"><span data-stu-id="40975-132">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the name of the server and instance to which the Recovery and Hardware database will be moved.</span></span>

    -   <span data-ttu-id="40975-133">$DOMAIN $ \ \ $SERVERNAME $-輸入每個 MBAM 應用程式和監視伺服器的網域和伺服器名稱，即可與復原與硬體資料庫聯繫。</span><span class="sxs-lookup"><span data-stu-id="40975-133">$DOMAIN$\\$SERVERNAME$ - Enter the domain and server names of each MBAM Application and Monitoring Server that will contact the Recovery and Hardware database.</span></span> <span data-ttu-id="40975-134">如果有多個網域和伺服器名稱，請使用分號分隔清單中的每一個名稱。</span><span class="sxs-lookup"><span data-stu-id="40975-134">If there are multiple domain and server names, use a semicolon to separate each one of them in the list.</span></span> <span data-ttu-id="40975-135">例如，$DOMAIN \\SERVERNAME $; $DOMAIN \ \ $SERVERNAME $ $。</span><span class="sxs-lookup"><span data-stu-id="40975-135">For example, $DOMAIN\\SERVERNAME$;$DOMAIN\\$SERVERNAME$$.</span></span> <span data-ttu-id="40975-136">此外，每個伺服器名稱後面必須加 a **$** 。</span><span class="sxs-lookup"><span data-stu-id="40975-136">Additionally, each server name must be followed by a **$**.</span></span> <span data-ttu-id="40975-137">例如，MyDomain\\MyServerName1 $，MyDomain\\MyServerName2 $。</span><span class="sxs-lookup"><span data-stu-id="40975-137">For example, MyDomain\\MyServerName1$, MyDomain\\MyServerName2$.</span></span>



**<span data-ttu-id="40975-138">若要備份伺服器 A 上的資料庫</span><span class="sxs-lookup"><span data-stu-id="40975-138">To back up the Database on Server A</span></span>**

1.  <span data-ttu-id="40975-139">若要在伺服器 A 上備份復原和硬體資料庫，請使用 SQL Server Management Studio 及名為 [Back ...] 的工作 **。**</span><span class="sxs-lookup"><span data-stu-id="40975-139">To back up the Recovery and Hardware database on Server A, use SQL Server Management Studio and the Task named **Back Up…**.</span></span> <span data-ttu-id="40975-140">根據預設，資料庫名稱是**MBAM 復原和硬體資料庫**。</span><span class="sxs-lookup"><span data-stu-id="40975-140">By default, the database name is **MBAM Recovery and Hardware Database**.</span></span>

2.  <span data-ttu-id="40975-141">若要自動化此程式，請建立包含下列 SQL 腳本的 SQL 檔案（.sql）：</span><span class="sxs-lookup"><span data-stu-id="40975-141">To automate this procedure, create a SQL file (.sql) that contains the following SQL script:</span></span>

    <span data-ttu-id="40975-142">修改 MBAM 復原與硬體資料庫，以使用完整的復原模式。</span><span class="sxs-lookup"><span data-stu-id="40975-142">Modify the MBAM Recovery and Hardware Database to use the full recovery mode.</span></span>

    ```sql
    USE master;

    GO

    ALTER DATABASE "MBAM Recovery and Hardware"

       SET RECOVERY FULL;

    GO
    ```

    <span data-ttu-id="40975-143">建立 MBAM 復原與硬體資料庫資料，並 MBAM 恢復邏輯備份裝置。</span><span class="sxs-lookup"><span data-stu-id="40975-143">Create MBAM Recovery and Hardware Database Data and MBAM Recovery logical backup devices.</span></span>

    ```sql
    USE master

    GO

    EXEC sp_addumpdevice 'disk', 'MBAM Recovery and Hardware Database Data Device',

    'Z:\MBAM Recovery and Hardware Database Data.bak';

    GO
    ```

    <span data-ttu-id="40975-144">備份完整的 MBAM 還原與硬體資料庫。</span><span class="sxs-lookup"><span data-stu-id="40975-144">Back up the full MBAM Recovery and Hardware database.</span></span>

    ```sql
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

    **<span data-ttu-id="40975-145">注意</span><span class="sxs-lookup"><span data-stu-id="40975-145">Note</span></span>**  
    <span data-ttu-id="40975-146">以與您的環境相符的方式，將前述範例中的值取代：</span><span class="sxs-lookup"><span data-stu-id="40975-146">Replace the values from the preceding example with those that match your environment:</span></span>

    -   <span data-ttu-id="40975-147">$PASSWORD $-輸入將用來加密私密金鑰檔案的密碼。</span><span class="sxs-lookup"><span data-stu-id="40975-147">$PASSWORD$ - Enter a password that you will use to encrypt the Private Key file.</span></span>



3.  <span data-ttu-id="40975-148">使用 SQL Server PowerShell 和類似下列的命令來執行 SQL 檔案：</span><span class="sxs-lookup"><span data-stu-id="40975-148">Execute the SQL file by using SQL Server PowerShell and a command that is similar to the following:</span></span>

    `PS C:\> Invoke-Sqlcmd -InputFile 'Z:\BackupMBAMRecoveryandHardwarDatabaseScript.sql' -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$`

    **<span data-ttu-id="40975-149">注意</span><span class="sxs-lookup"><span data-stu-id="40975-149">Note</span></span>**  
    <span data-ttu-id="40975-150">將上一個範例中的值取代成與您的環境相符的值：</span><span class="sxs-lookup"><span data-stu-id="40975-150">Replace the value in the previous example with those that match your environment:</span></span>

    -   <span data-ttu-id="40975-151">$SERVERNAME $ \ \ $SQLINSTANCENAME $-輸入伺服器的名稱，以及您要備份復原和硬體資料庫的實例。</span><span class="sxs-lookup"><span data-stu-id="40975-151">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the name of the server and the instance from which you back up the Recovery and Hardware database.</span></span>



**<span data-ttu-id="40975-152">將資料庫和憑證從伺服器 A 移至 B</span><span class="sxs-lookup"><span data-stu-id="40975-152">To move the Database and Certificate from Server A to B</span></span>**

1.  <span data-ttu-id="40975-153">使用 Windows Explorer，將 MBAM 復原與硬體資料庫資料從伺服器 A 移到伺服器 B。</span><span class="sxs-lookup"><span data-stu-id="40975-153">Move the MBAM Recovery and Hardware database data.bak from Server A to Server B by using Windows Explorer.</span></span>

2.  <span data-ttu-id="40975-154">若要移動加密資料庫的憑證，您將需要使用下列自動化步驟。</span><span class="sxs-lookup"><span data-stu-id="40975-154">To move the certificate for the encrypted database, you will need to use the following automation steps.</span></span> <span data-ttu-id="40975-155">若要自動化此程式，您可以使用 Windows PowerShell 輸入類似以下的命令：</span><span class="sxs-lookup"><span data-stu-id="40975-155">To automate this procedure, you can use Windows PowerShell to enter a command that is similar to the following:</span></span>

    `PS C:\> Copy-Item “Z:\MBAM Recovery and Hardware Database Data.bak” \\$SERVERNAME$\$DESTINATIONSHARE$`

    `PS C:\> Copy-Item “Z:\SQLServerInstanceCertificateFile” \\$SERVERNAME$\$DESTINATIONSHARE$`

    `PS C:\> Copy-Item “Z:\SQLServerInstanceCertificateFilePrivateKey” \\$SERVERNAME$\$DESTINATIONSHARE$`

    **<span data-ttu-id="40975-156">注意</span><span class="sxs-lookup"><span data-stu-id="40975-156">Note</span></span>**  
    <span data-ttu-id="40975-157">將上述範例中的值取代為符合您環境的專案：</span><span class="sxs-lookup"><span data-stu-id="40975-157">Replace the value from the preceding example with those that match your environment:</span></span>

    -   <span data-ttu-id="40975-158">$SERVERNAME $-輸入要將檔案複製到其中的伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="40975-158">$SERVERNAME$ - Enter the name of the server to which the files will be copied.</span></span>

    -   <span data-ttu-id="40975-159">$DESTINATIONSHARE $-輸入要將檔案複製到其中的共用名稱稱和路徑。</span><span class="sxs-lookup"><span data-stu-id="40975-159">$DESTINATIONSHARE$ - Enter the name of the share and path to which the files will be copied.</span></span>



**<span data-ttu-id="40975-160">在伺服器 B 上還原資料庫</span><span class="sxs-lookup"><span data-stu-id="40975-160">To restore the Database on Server B</span></span>**

1.  <span data-ttu-id="40975-161">在伺服器 B 上使用 SQL Server Management Studio 及名為 [**還原資料庫**] 的工作來還原恢復與硬體資料庫。</span><span class="sxs-lookup"><span data-stu-id="40975-161">Restore the Recovery and Hardware database on Server B by using the SQL Server Management Studio and the Task named **Restore Database**.</span></span>

2.  <span data-ttu-id="40975-162">工作執行之後，請選取 [**發件**人] 選項，然後使用 [Add] （**新增**）命令來選擇 [MBAM 復原] 和 [硬體資料庫**資料 .bak** ]。</span><span class="sxs-lookup"><span data-stu-id="40975-162">Once the task has been executed, choose the database backup file by selecting the **From Device** option, and then use the **Add** command to choose the MBAM Recovery and Hardware database **Data.bak** file.</span></span>

3.  <span data-ttu-id="40975-163">選取 **[確定]** 以完成還原程式。</span><span class="sxs-lookup"><span data-stu-id="40975-163">Select **OK** to complete the restoration process.</span></span>

4.  <span data-ttu-id="40975-164">若要自動化此程式，請建立包含下列 SQL 腳本的 SQL 檔案（.sql）：</span><span class="sxs-lookup"><span data-stu-id="40975-164">To automate this procedure, create a SQL file (.sql) that contains the following SQL script:</span></span>

    ```sql
    -- Restore MBAM Recovery and Hardware Database. 

    USE master

    GO
    ```

    <span data-ttu-id="40975-165">刪除由 MBAM 安裝程式所建立的憑證。</span><span class="sxs-lookup"><span data-stu-id="40975-165">Drop the certificate created by MBAM Setup.</span></span>

    ```sql
    DROP CERTIFICATE [MBAM Recovery Encryption Certificate]

    GO
    ```

    <span data-ttu-id="40975-166">新增憑證</span><span class="sxs-lookup"><span data-stu-id="40975-166">Add certificate</span></span>

    ```sql
    CREATE CERTIFICATE [MBAM Recovery Encryption Certificate]

    FROM FILE = 'Z: \SQLServerInstanceCertificateFile'

    WITH PRIVATE KEY

    (

        FILE = ' Z:\SQLServerInstanceCertificateFilePrivateKey',

        DECRYPTION BY PASSWORD = '$PASSWORD$'

    );

    GO
    ```

    <span data-ttu-id="40975-167">還原 MBAM 復原及硬體資料庫資料及記錄檔。</span><span class="sxs-lookup"><span data-stu-id="40975-167">Restore the MBAM Recovery and Hardware database data and the log files.</span></span>

    ```sql
    RESTORE DATABASE [MBAM Recovery and Hardware]

       FROM DISK = 'Z:\MBAM Recovery and Hardware Database Data.bak'

       WITH REPLACE
    ```

    **<span data-ttu-id="40975-168">注意</span><span class="sxs-lookup"><span data-stu-id="40975-168">Note</span></span>**  
    <span data-ttu-id="40975-169">以與您的環境相符的方式，將前述範例中的值取代：</span><span class="sxs-lookup"><span data-stu-id="40975-169">Replace the values from the preceding example with those that match your environment:</span></span>

    -   <span data-ttu-id="40975-170">$PASSWORD $-輸入您用來加密私人金鑰檔案的密碼。</span><span class="sxs-lookup"><span data-stu-id="40975-170">$PASSWORD$ - Enter the password that you used to encrypt the Private Key file.</span></span>



5.  <span data-ttu-id="40975-171">使用 Windows PowerShell 輸入類似以下的命令列：</span><span class="sxs-lookup"><span data-stu-id="40975-171">Use Windows PowerShell to enter a command line that is similar to the following:</span></span>

    `PS C:\> Invoke-Sqlcmd -InputFile 'Z:\RestoreMBAMRecoveryandHardwarDatabaseScript.sql' -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$`

    **<span data-ttu-id="40975-172">注意</span><span class="sxs-lookup"><span data-stu-id="40975-172">Note</span></span>**  
    <span data-ttu-id="40975-173">以與您的環境相符的方式，將 receding 範例中的值取代：</span><span class="sxs-lookup"><span data-stu-id="40975-173">Replace the value from the receding example with those that match your environment:</span></span>

    -   <span data-ttu-id="40975-174">$SERVERNAME $ \ \ $SQLINSTANCENAME $-輸入伺服器名稱，以及要還原恢復與硬體資料庫的實例。</span><span class="sxs-lookup"><span data-stu-id="40975-174">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the name of the server and the instance to which the Recovery and Hardware Database will be restored.</span></span>



**<span data-ttu-id="40975-175">在伺服器 B 上設定對資料庫的存取權</span><span class="sxs-lookup"><span data-stu-id="40975-175">Configure the access to the Database on Server B</span></span>**

1.  <span data-ttu-id="40975-176">在伺服器 B 上，使用 [伺服器管理員] 中的 [本機使用者和群組] 管理單元，將每個伺服器上執行 MBAM 管理和監控功能的電腦帳戶新增到名為 [MBAM 復原]**和 [硬體資料庫存取**] 的本機群組。</span><span class="sxs-lookup"><span data-stu-id="40975-176">On Server B, use the Local user and Groups snap-in from Server Manager, to add the computer accounts from each server that runs the MBAM Administration and Monitoring feature to the Local Group named **MBAM Recovery and Hardware DB Access**.</span></span>

2.  <span data-ttu-id="40975-177">若要自動化此程式，您可以在伺服器 B 上使用 Windows PowerShell，輸入類似以下的命令：</span><span class="sxs-lookup"><span data-stu-id="40975-177">To automate this procedure, you can use Windows PowerShell on Server B to enter a command that is similar to the following:</span></span>

    `PS C:\> net localgroup "MBAM Recovery and Hardware DB Access" $DOMAIN$\$SERVERNAME$$  /add`

    **<span data-ttu-id="40975-178">注意</span><span class="sxs-lookup"><span data-stu-id="40975-178">Note</span></span>**  
    <span data-ttu-id="40975-179">以適用于您環境的值取代上述範例中的值：</span><span class="sxs-lookup"><span data-stu-id="40975-179">Replace the values from the preceding example with the applicable values for your environment:</span></span>

    -   <span data-ttu-id="40975-180">$DOMAIN $ \ \ $SERVERNAME $ $-輸入 MBAM 管理和監視伺服器的功能變數名稱和電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="40975-180">$DOMAIN$\\$SERVERNAME$$ - Enter the domain name and machine name of the MBAM Administration and Monitoring Server.</span></span> <span data-ttu-id="40975-181">伺服器名後面必須加 a **$** ，例如，MyDomain\\MyServerName1 $。</span><span class="sxs-lookup"><span data-stu-id="40975-181">The server name must be followed by a **$**, for example, MyDomain\\MyServerName1$.</span></span>



~~~
You must run the command for each Administration and Monitoring Server that will be accessing the database in your environment.
~~~

**<span data-ttu-id="40975-182">在 MBAM 管理和監視伺服器上更新資料庫連線資料</span><span class="sxs-lookup"><span data-stu-id="40975-182">To update the Database Connection data on MBAM Administration and Monitoring Servers</span></span>**

1. <span data-ttu-id="40975-183">在執行 MBAM 管理和監視功能的每個伺服器上，使用 Internet Information Services （IIS）管理員主控台來更新下列應用程式的連線字串資訊，這些應用程式是由 Microsoft BitLocker 管理和監視網站所託管。</span><span class="sxs-lookup"><span data-stu-id="40975-183">On each of the servers that run the MBAM Administration and Monitoring feature, use the Internet Information Services (IIS) Manager console to update the Connection String information for the following applications, which are hosted in the Microsoft BitLocker Administration and Monitoring website:</span></span>

   -   <span data-ttu-id="40975-184">MBAM 系統管理服務</span><span class="sxs-lookup"><span data-stu-id="40975-184">MBAM Administration Service</span></span>

   -   <span data-ttu-id="40975-185">MBAM 恢復與硬體服務</span><span class="sxs-lookup"><span data-stu-id="40975-185">MBAM Recovery And Hardware Service</span></span>

2. <span data-ttu-id="40975-186">選取每個應用程式，並使用 [設定**編輯器**] 功能（位於**功能視圖**的 [**管理**] 區段底下）。</span><span class="sxs-lookup"><span data-stu-id="40975-186">Select each application and use the **Configuration Editor** feature, which is located under the **Management** section of the **Feature View**.</span></span>

3. <span data-ttu-id="40975-187">從區段清單控制項選取 [ **configurationStrings** ] 選項。</span><span class="sxs-lookup"><span data-stu-id="40975-187">Select the **configurationStrings** option from the Section list control.</span></span>

4. <span data-ttu-id="40975-188">選擇名為 **（集合）** 的列，然後選取列右側的按鈕來開啟**集合編輯器**。</span><span class="sxs-lookup"><span data-stu-id="40975-188">Choose the row named **(Collection)**, and open the **Collection Editor** by selecting the button on the right side of the row.</span></span>

5. <span data-ttu-id="40975-189">在**集合編輯器**中，當您更新「MBAMAdministrationService」應用程式的設定時，請選擇名為**KeyRecoveryConnectionString**的列，或選擇名為 Mbam 的列 <strong> 。 </strong>ConnectionString，更新 "MBAMRecoveryAndHardwareService" 的設定。</span><span class="sxs-lookup"><span data-stu-id="40975-189">In the **Collection Editor**, choose the row named **KeyRecoveryConnectionString** when you updated the configuration for the ‘MBAMAdministrationService’ application, or choose the row named <strong>Microsoft.Mbam.RecoveryAndHardwareDataStore.</strong>ConnectionString, when updating the configuration for the ‘MBAMRecoveryAndHardwareService’.</span></span>

6. <span data-ttu-id="40975-190">更新**configurationStrings**屬性的**資料來源 =** 值，以列出伺服器名稱，以及將復原和硬體資料庫移動到哪個實例。</span><span class="sxs-lookup"><span data-stu-id="40975-190">Update the **Data Source=** value for the **configurationStrings** property to list the server name and the instance where the Recovery and Hardware Database was moved to.</span></span> <span data-ttu-id="40975-191">例如，$SERVERNAME $ \ \ $SQLINSTANCENAME $。</span><span class="sxs-lookup"><span data-stu-id="40975-191">For example, $SERVERNAME$\\$SQLINSTANCENAME$.</span></span>

7. <span data-ttu-id="40975-192">若要自動化此程式，您可以使用與下列命令類似的命令，方法是在每個管理和監視伺服器上使用 Windows PowerShell：</span><span class="sxs-lookup"><span data-stu-id="40975-192">To automate this procedure, you can use a command that is similar to the following one, by using Windows PowerShell on each Administration and Monitoring Server:</span></span>

   `PS C:\> Set-WebConfigurationProperty '/connectionStrings/add[@name="KeyRecoveryConnectionString"]' -PSPath "IIS:\sites\Microsoft BitLocker Administration and Monitoring\MBAMAdministrationService" -Name "connectionString" -Value “Data Source=$SERVERNAME$\$SQLINSTANCENAME$;Initial Catalog=MBAM Recovery and Hardware;Integrated Security=SSPI;”`

   `PS C:\> Set-WebConfigurationProperty '/connectionStrings/add[@name="Microsoft.Mbam.RecoveryAndHardwareDataStore.ConnectionString"]' -PSPath "IIS:\sites\Microsoft BitLocker Administration and Monitoring\MBAMRecoveryAndHardwareService" -Name "connectionString" -Value "Data Source=$SERVERNAME$\$SQLINSTANCENAME$;Initial Catalog=MBAM Recovery and Hardware;Integrated Security=SSPI;"`

   **<span data-ttu-id="40975-193">注意</span><span class="sxs-lookup"><span data-stu-id="40975-193">Note</span></span>**  
   <span data-ttu-id="40975-194">將上述範例中的值取代為符合您環境的專案：</span><span class="sxs-lookup"><span data-stu-id="40975-194">Replace the value from the preceding example with those that match your environment:</span></span>

   -   <span data-ttu-id="40975-195">$SERVERNAME $ \ \ $SQLINSTANCENAME $-輸入 [恢復] 和 [硬體] 資料庫所在的伺服器名稱和實例。</span><span class="sxs-lookup"><span data-stu-id="40975-195">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the server name and instance where the Recovery and Hardware database is.</span></span>



**<span data-ttu-id="40975-196">若要繼續 MBAM 管理和監視網站的所有實例</span><span class="sxs-lookup"><span data-stu-id="40975-196">To resume all instances of the MBAM Administration and Monitoring website</span></span>**

1.  <span data-ttu-id="40975-197">在執行 MBAM 管理和監視功能的每個伺服器上，使用 Internet Information Services （IIS）管理員主控台來啟動名為**Microsoft BitLocker 管理和監視**的 MBAM 網站。</span><span class="sxs-lookup"><span data-stu-id="40975-197">On each of the servers that run the MBAM Administration and Monitoring feature, use the Internet Information Services (IIS) Manager console to Start the MBAM website, which is named **Microsoft BitLocker Administration and Monitoring**.</span></span>

2.  <span data-ttu-id="40975-198">若要自動化此程式，您可以使用 Windows PowerShell，使用與下列命令類似的命令：</span><span class="sxs-lookup"><span data-stu-id="40975-198">To automate this procedure, you can use a command that is similar to the following one, by using Windows PowerShell:</span></span>

    `PS C:\> Start-Website “Microsoft BitLocker Administration and Monitoring”`

## <span data-ttu-id="40975-199">若要移動 [合規性狀態資料庫] 功能</span><span class="sxs-lookup"><span data-stu-id="40975-199">To move the Compliance Status Database feature</span></span>


<span data-ttu-id="40975-200">如果您選擇將 [MBAM 合規性狀態資料庫] 功能從一部電腦移到另一台電腦（例如從伺服器 A 移至伺服器 B），您應該使用下列程式：</span><span class="sxs-lookup"><span data-stu-id="40975-200">If you choose to move the MBAM Compliance Status Database feature from one computer to another, such as from Server A to Server B, you should use the following procedure:</span></span>

1.  <span data-ttu-id="40975-201">停止 MBAM 管理和監視網站的所有實例</span><span class="sxs-lookup"><span data-stu-id="40975-201">Stop all instances of the MBAM Administration and Monitoring website</span></span>

2.  <span data-ttu-id="40975-202">在伺服器 B 上執行 MBAM 設定</span><span class="sxs-lookup"><span data-stu-id="40975-202">Run MBAM setup on Server B</span></span>

3.  <span data-ttu-id="40975-203">在伺服器 A 上備份資料庫</span><span class="sxs-lookup"><span data-stu-id="40975-203">Backup the Database on Server A</span></span>

4.  <span data-ttu-id="40975-204">將資料庫從伺服器 A 移至 B</span><span class="sxs-lookup"><span data-stu-id="40975-204">Move the Database from Server A to B</span></span>

5.  <span data-ttu-id="40975-205">在伺服器 B 上還原資料庫</span><span class="sxs-lookup"><span data-stu-id="40975-205">Restore the Database on Server B</span></span>

6.  <span data-ttu-id="40975-206">在伺服器 B 上設定對資料庫的存取權</span><span class="sxs-lookup"><span data-stu-id="40975-206">Configure Access to the Database on Server B</span></span>

7.  <span data-ttu-id="40975-207">在 MBAM 管理和監視伺服器上更新資料庫連線資料</span><span class="sxs-lookup"><span data-stu-id="40975-207">Update database connection data on MBAM Administration and Monitoring servers</span></span>

8.  <span data-ttu-id="40975-208">繼續 MBAM 管理和監視網站的所有實例</span><span class="sxs-lookup"><span data-stu-id="40975-208">Resume all instances of the MBAM Administration and Monitoring website</span></span>

**<span data-ttu-id="40975-209">若要停止 MBAM 管理和監視網站的所有實例</span><span class="sxs-lookup"><span data-stu-id="40975-209">To stop all instances of the MBAM Administration and Monitoring website</span></span>**

1.  <span data-ttu-id="40975-210">在執行 MBAM 管理和監視功能的每個伺服器上，使用 Internet Information Services （IIS）管理員主控台來停止名為**Microsoft BitLocker 管理和監視**的 MBAM 網站。</span><span class="sxs-lookup"><span data-stu-id="40975-210">On each of the servers that run the MBAM Administration and Monitoring feature, use the Internet Information Services (IIS) Manager console to Stop the MBAM website, which is named **Microsoft BitLocker Administration and Monitoring**.</span></span>

2.  <span data-ttu-id="40975-211">若要自動化此程式，您可以使用 Windows PowerShell，使用與下列命令類似的命令：</span><span class="sxs-lookup"><span data-stu-id="40975-211">To automate this procedure, you can use a command that is similar to the following one,by using Windows PowerShell:</span></span>

    `PS C:\> Stop-Website “Microsoft BitLocker Administration and Monitoring”`

    **<span data-ttu-id="40975-212">注意</span><span class="sxs-lookup"><span data-stu-id="40975-212">Note</span></span>**  
    <span data-ttu-id="40975-213">若要執行此命令，您必須將 PowerShell 的 IIS 模組新增至目前的 PowerShell 實例。</span><span class="sxs-lookup"><span data-stu-id="40975-213">To execute this command, you must add the IIS Module for PowerShell to current instance of PowerShell.</span></span> <span data-ttu-id="40975-214">此外，您必須更新 PowerShell 執行原則，以啟用腳本執行。</span><span class="sxs-lookup"><span data-stu-id="40975-214">In addition, you must update the PowerShell execution policy to enable the execution of scripts.</span></span>



**<span data-ttu-id="40975-215">若要在伺服器 B 上執行 MBAM 設定</span><span class="sxs-lookup"><span data-stu-id="40975-215">To run MBAM Setup on Server B</span></span>**

1.  <span data-ttu-id="40975-216">在伺服器 B 上執行 MBAM 安裝程式，然後選取 [規範狀態資料庫] 功能以進行安裝。</span><span class="sxs-lookup"><span data-stu-id="40975-216">Run MBAM Setup on Server B and select the Compliance Status Database feature for installation.</span></span>

2.  <span data-ttu-id="40975-217">若要自動化此程式，您可以使用 Windows PowerShell，使用與下列命令類似的命令：</span><span class="sxs-lookup"><span data-stu-id="40975-217">To automate this procedure, you can use a command that is similar to the following one, by using Windows PowerShell:</span></span>

    `PS C:\> MbamSetup.exe /qn I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 AddLocal= ReportsDatabase ADMINANDMON_MACHINENAMES=$DOMAIN$\$SERVERNAME$ COMPLIDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ REPORTS_USERACCOUNT=$DOMAIN$\$USERNAME$`

    **<span data-ttu-id="40975-218">注意</span><span class="sxs-lookup"><span data-stu-id="40975-218">Note</span></span>**  
    <span data-ttu-id="40975-219">以與您的環境相符的方式，將前述範例中的值取代：</span><span class="sxs-lookup"><span data-stu-id="40975-219">Replace the values from the preceding example with those that match your environment:</span></span>

    -   <span data-ttu-id="40975-220">$SERVERNAME $ \ \ $SQLINSTANCENAME $-輸入要將合規性狀態資料庫移至其中的伺服器名稱和實例。</span><span class="sxs-lookup"><span data-stu-id="40975-220">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the server name and instance where the Compliance Status Database will be moved to.</span></span>

    -   <span data-ttu-id="40975-221">$DOMAIN $ \ \ $SERVERNAME $-輸入每個 MBAM 應用程式和監視伺服器的功能變數名稱和伺服器名稱，即可與合規性狀態資料庫聯繫。</span><span class="sxs-lookup"><span data-stu-id="40975-221">$DOMAIN$\\$SERVERNAME$ - Enter the domain names and server names of each MBAM Application and Monitoring Server that will contact the Compliance Status Database.</span></span> <span data-ttu-id="40975-222">如果有多個功能變數名稱和伺服器名稱，請使用分號分隔清單中的每一個名稱。</span><span class="sxs-lookup"><span data-stu-id="40975-222">If there are multiple domain names and server names, use a semicolon to separate each one of them in the list.</span></span> <span data-ttu-id="40975-223">例如，$DOMAIN \\SERVERNAME $; $DOMAIN \ \ $SERVERNAME $ $。</span><span class="sxs-lookup"><span data-stu-id="40975-223">For example, $DOMAIN\\SERVERNAME$;$DOMAIN\\$SERVERNAME$$.</span></span> <span data-ttu-id="40975-224">每個伺服器名稱後面必須加 a **$** ，如範例所示。</span><span class="sxs-lookup"><span data-stu-id="40975-224">Each server name must be followed by a **$** as shown in the example.</span></span> <span data-ttu-id="40975-225">例如，MyDomain\\MyServerName1 $，MyDomain\\MyServerName2 $。</span><span class="sxs-lookup"><span data-stu-id="40975-225">For example, MyDomain\\MyServerName1$, MyDomain\\MyServerName2$.</span></span>

    -   <span data-ttu-id="40975-226">$DOMAIN $ \ \ $USERNAME $-輸入將由合規性和審核報告功能用來連線至合規性狀態資料庫的網域和使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="40975-226">$DOMAIN$\\$USERNAME$ - Enter the domain and user name that will be used by the Compliance and Audit reports feature to connect to the Compliance Status Database.</span></span>



**<span data-ttu-id="40975-227">若要在伺服器 A 上備份合規性資料庫</span><span class="sxs-lookup"><span data-stu-id="40975-227">To back up the Compliance Database on Server A</span></span>**

1.  <span data-ttu-id="40975-228">若要在伺服器 A 上備份合規性資料庫，請使用 SQL Server Management Studio 及名為 [ **Back up ...**] 的工作。</span><span class="sxs-lookup"><span data-stu-id="40975-228">To back up the Compliance Database on Server A, use SQL Server Management Studio and the Task named **Back Up…**.</span></span> <span data-ttu-id="40975-229">根據預設，資料庫名稱是**MBAM 合規性狀態資料庫**。</span><span class="sxs-lookup"><span data-stu-id="40975-229">By default, the database name is **MBAM Compliance Status Database**.</span></span>

2.  <span data-ttu-id="40975-230">若要自動化此程式，請建立包含下列 SQL 腳本的 SQL 檔案（.sql）：</span><span class="sxs-lookup"><span data-stu-id="40975-230">To automate this procedure, create a SQL file (.sql) that contains the following-SQL script:</span></span>

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

    -- Back up the full MBAM Recovery and Hardware database.

    BACKUP DATABASE [MBAM Compliance Status] TO [MBAM Compliance Status Database Data Device];

    GO
    ```

3.  <span data-ttu-id="40975-231">使用 SQL Server PowerShell，執行 SQL 檔案，並使用與下列命令類似的命令：</span><span class="sxs-lookup"><span data-stu-id="40975-231">Run the SQL file with a command that is similar to the following one, by using the SQL Server PowerShell:</span></span>

    `PS C:\> Invoke-Sqlcmd -InputFile "Z:\BackupMBAMComplianceStatusDatabaseScript.sql" –ServerInstance $SERVERNAME$\$SQLINSTANCENAME$`

    **<span data-ttu-id="40975-232">注意</span><span class="sxs-lookup"><span data-stu-id="40975-232">Note</span></span>**  
    <span data-ttu-id="40975-233">將上述範例中的值取代為符合您環境的專案：</span><span class="sxs-lookup"><span data-stu-id="40975-233">Replace the value from the preceding example with those that match your environment:</span></span>

    -   <span data-ttu-id="40975-234">$SERVERNAME $ \ \ $SQLINSTANCENAME $-輸入伺服器名稱，以及將備份合規性狀態資料庫的實例。</span><span class="sxs-lookup"><span data-stu-id="40975-234">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the server name and the instance from where the Compliance Status database will be backed up.</span></span>



**<span data-ttu-id="40975-235">若要將資料庫從伺服器 A 移至 B</span><span class="sxs-lookup"><span data-stu-id="40975-235">To move the Database from Server A to B</span></span>**

1.  <span data-ttu-id="40975-236">使用 Windows Explorer 將下列檔案從伺服器 A 移至伺服器 B：</span><span class="sxs-lookup"><span data-stu-id="40975-236">Move the following files from Server A to Server B, by using Windows Explorer:</span></span>

    -   <span data-ttu-id="40975-237">MBAM 合規性狀態資料庫資料 .bak</span><span class="sxs-lookup"><span data-stu-id="40975-237">MBAM Compliance Status Database Data.bak</span></span>

2.  <span data-ttu-id="40975-238">若要自動化此程式，您可以使用與下列使用 Windows PowerShell 類似的命令：</span><span class="sxs-lookup"><span data-stu-id="40975-238">To automate this procedure, you can use a command that is similar to the following using Windows PowerShell:</span></span>

    `PS C:\> Copy-Item “Z:\MBAM Compliance Status Database Data.bak” \\$SERVERNAME$\$DESTINATIONSHARE$`

    **<span data-ttu-id="40975-239">注意</span><span class="sxs-lookup"><span data-stu-id="40975-239">Note</span></span>**  
    <span data-ttu-id="40975-240">將上述範例中的值取代為符合您環境的專案：</span><span class="sxs-lookup"><span data-stu-id="40975-240">Replace the value from the preceding example with those that match your environment:</span></span>

    -   <span data-ttu-id="40975-241">$SERVERNAME $-輸入要將檔案複製到其中的伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="40975-241">$SERVERNAME$ - Enter the server name where the files will be copied to.</span></span>

    -   <span data-ttu-id="40975-242">$DESTINATIONSHARE $-輸入要將檔案複製到其中的共用名稱稱和路徑。</span><span class="sxs-lookup"><span data-stu-id="40975-242">$DESTINATIONSHARE$ - Enter the name of share and path where the files will be copied to.</span></span>



**<span data-ttu-id="40975-243">在伺服器 B 上還原資料庫</span><span class="sxs-lookup"><span data-stu-id="40975-243">To restore the Database on Server B</span></span>**

1.  <span data-ttu-id="40975-244">在伺服器 B 上使用 SQL Server Management Studio 及名為 [**還原資料庫 ...**] 的工作來還原合規性狀態資料庫 .。。</span><span class="sxs-lookup"><span data-stu-id="40975-244">Restore the Compliance Status database on Server B by using SQL Server Management Studio and the Task named **Restore Database…**.</span></span>

2.  <span data-ttu-id="40975-245">執行工作後，選取資料庫備份檔案，方法是選取 [寄件者] 選項，然後使用 [Add] （新增）命令，選擇 [MBAM 合規性狀態資料庫資料 .bak] 檔。</span><span class="sxs-lookup"><span data-stu-id="40975-245">Once the task is executed, select the database backup file, by selecting the From Device option, and then use the Add command to choose the MBAM Compliance Status Database Data.bak file.</span></span> <span data-ttu-id="40975-246">按一下 [確定] 以完成還原程式。</span><span class="sxs-lookup"><span data-stu-id="40975-246">Click OK to complete the restoration process.</span></span>

3.  <span data-ttu-id="40975-247">若要自動化此程式，請建立包含下列 SQL 腳本的 SQL 檔案（.sql）：</span><span class="sxs-lookup"><span data-stu-id="40975-247">To automate this procedure, create a SQL file (.sql) that contains the following-SQL script:</span></span>

    ```sql
    -- Create MBAM Compliance Status Database Data logical backup devices. 

    Use master

    GO

    -- Restore the MBAM Compliance Status database data files.

    RESTORE DATABASE [MBAM Compliance Status Database]

       FROM DISK = 'C:\test\MBAM Compliance Status Database Data.bak'

       WITH REPLACE
    ```

4.  <span data-ttu-id="40975-248">使用 SQL Server PowerShell，執行 SQL 檔案，並使用與下列命令類似的命令：</span><span class="sxs-lookup"><span data-stu-id="40975-248">Run the SQL File with a command that is similar to the following one, by using the SQL Server PowerShell:</span></span>

    `PS C:\> Invoke-Sqlcmd -InputFile "Z:\RestoreMBAMComplianceStatusDatabaseScript.sql" -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$`

    **<span data-ttu-id="40975-249">注意</span><span class="sxs-lookup"><span data-stu-id="40975-249">Note</span></span>**  
    <span data-ttu-id="40975-250">將上述範例中的值取代為符合您環境的專案：</span><span class="sxs-lookup"><span data-stu-id="40975-250">Replace the value from the preceding example with those that match your environment:</span></span>

    -   <span data-ttu-id="40975-251">$SERVERNAME $ \ \ $SQLINSTANCENAME $-輸入將會還原合規性狀態資料庫的伺服器名稱和實例。</span><span class="sxs-lookup"><span data-stu-id="40975-251">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the server name and instance where the Compliance Status Database will be restored to.</span></span>



**<span data-ttu-id="40975-252">在伺服器 B 上設定對資料庫的存取權</span><span class="sxs-lookup"><span data-stu-id="40975-252">To configure the Access to the Database on Server B</span></span>**

1.  <span data-ttu-id="40975-253">在伺服器 B 上，使用 [伺服器管理員] 中的 [本機使用者和群組] 管理單元，將每個伺服器上執行 MBAM 管理和監控功能的電腦帳戶新增到名為 [ **MBAM 合規性狀態 DB 存取**] 的本機群組。</span><span class="sxs-lookup"><span data-stu-id="40975-253">On Server B use the Local user and Groups snap-in from Server Manager to add the machine accounts from each server that runs the MBAM Administration and Monitoring feature to the Local Group named **MBAM Compliance Status DB Access**.</span></span>

2.  <span data-ttu-id="40975-254">若要自動化此程式，您可以使用與下列命令類似的命令，方法是在伺服器 B 上使用 Windows PowerShell：</span><span class="sxs-lookup"><span data-stu-id="40975-254">To automate this procedure, you can use a command that is similar to the following one, by using Windows PowerShell on Server B:</span></span>

    `PS C:\> net localgroup "MBAM Compliance Auditing DB Access" $DOMAIN$\$SERVERNAME$$  /add`

    `PS C:\> net localgroup "MBAM Compliance Auditing DB Access" $DOMAIN$\$REPORTSUSERNAME$  /add`

    **<span data-ttu-id="40975-255">注意</span><span class="sxs-lookup"><span data-stu-id="40975-255">Note</span></span>**  
    <span data-ttu-id="40975-256">以適用于您環境的值取代前一個範例中的值：</span><span class="sxs-lookup"><span data-stu-id="40975-256">Replace the value from the preceding example with the applicable values for your environment:</span></span>

    -   <span data-ttu-id="40975-257">$DOMAIN $ \ \ $SERVERNAME $ $-輸入 MBAM 管理和監視伺服器的網域和電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="40975-257">$DOMAIN$\\$SERVERNAME$$ - Enter the domain and machine name of the MBAM Administration and Monitoring Server.</span></span> <span data-ttu-id="40975-258">伺服器名稱後面必須加 a **$** 。例如，MyDomain\\MyServerName1 $。</span><span class="sxs-lookup"><span data-stu-id="40975-258">The server name must be followed by a **$**.For example, MyDomain\\MyServerName1$.</span></span>

    -   <span data-ttu-id="40975-259">$DOMAIN $ \ \ $REPORTSUSERNAME $-輸入用來設定合規性和審核報告之資料來源的使用者帳戶名稱</span><span class="sxs-lookup"><span data-stu-id="40975-259">$DOMAIN$\\$REPORTSUSERNAME$ - Enter the user account name that was used to configure the data source for the Compliance and Audit reports</span></span>



~~~
For each Administration and Monitoring Server that will access the database of your environment, you must run the command that will add the servers to the MBAM Compliance Auditing DB Access local group.
~~~

**<span data-ttu-id="40975-260">在 MBAM 管理和監視伺服器上更新資料庫連線資料</span><span class="sxs-lookup"><span data-stu-id="40975-260">To update the database connection data on MBAM Administration and Monitoring servers</span></span>**

1.  <span data-ttu-id="40975-261">在執行 MBAM 管理和監視功能的每個伺服器上，使用 Internet Information Services （IIS）管理員主控台來更新下列應用程式的連線字串資訊，這些應用程式是由 Microsoft BitLocker 管理和監視網站所託管。</span><span class="sxs-lookup"><span data-stu-id="40975-261">On each of the servers that run the MBAM Administration and Monitoring feature, use the Internet Information Services (IIS) Manager console to update the Connection String information for the following Applications, which are hosted in the Microsoft BitLocker Administration and Monitoring website:</span></span>

    -   <span data-ttu-id="40975-262">MBAMAdministrationService</span><span class="sxs-lookup"><span data-stu-id="40975-262">MBAMAdministrationService</span></span>

    -   <span data-ttu-id="40975-263">MBAMComplianceStatusService</span><span class="sxs-lookup"><span data-stu-id="40975-263">MBAMComplianceStatusService</span></span>

2.  <span data-ttu-id="40975-264">選取每個應用程式，並使用 [設定**編輯器**] 功能（位於**功能視圖**的 [**管理**] 區段底下）。</span><span class="sxs-lookup"><span data-stu-id="40975-264">Select each application and use the **Configuration Editor** feature, which is located under the **Management** section of the **Feature View**.</span></span>

3.  <span data-ttu-id="40975-265">從區段清單控制項選取 [ **configurationStrings** ] 選項。</span><span class="sxs-lookup"><span data-stu-id="40975-265">Select the **configurationStrings** option from the Section list control.</span></span>

4.  <span data-ttu-id="40975-266">選取名為 **（集合）** 的列，然後選取列右側的按鈕來開啟集合編輯器。</span><span class="sxs-lookup"><span data-stu-id="40975-266">Select the row named **(Collection)**, and open the Collection Editor by selecting the button on the right side of the row.</span></span>

5.  <span data-ttu-id="40975-267">在**集合編輯器**中，當您更新 MBAMComplianceStatusService 的設定時，請選取名為**ComplianceStatusConnectionString**的列、更新 MBAMAdministrationService 應用程式的設定，或是名為**BitLockerManagement**的列。</span><span class="sxs-lookup"><span data-stu-id="40975-267">In the **Collection Editor**, select the row named **ComplianceStatusConnectionString**, when you update the configuration for the MBAMAdministrationService application, or the row named **Microsoft.Windows.Mdop.BitLockerManagement.StatusReportDataStore.ConnectionString**, when you update the configuration for the MBAMComplianceStatusService.</span></span>

6.  <span data-ttu-id="40975-268">更新**configurationStrings**屬性的**資料來源 =** 值，以列出伺服器名稱和實例名稱。</span><span class="sxs-lookup"><span data-stu-id="40975-268">Update the **Data Source=** value for the **configurationStrings** property to list the server name and the instance name.</span></span> <span data-ttu-id="40975-269">例如，$SERVERNAME $ \ \ $SQLINSTANCENAME，即會將復原和硬體資料庫移動到哪個位置。</span><span class="sxs-lookup"><span data-stu-id="40975-269">For example, $SERVERNAME$\\$SQLINSTANCENAME, to which the Recovery and Hardware Database was moved.</span></span>

7.  <span data-ttu-id="40975-270">若要自動化此程式，您可以使用 Windows PowerShell，在每個管理和監視伺服器上輸入類似以下的命令：</span><span class="sxs-lookup"><span data-stu-id="40975-270">To automate this procedure, you can use Windows PowerShell to enter a command that is similar to the following one on each Administration and Monitoring Server:</span></span>

    `PS C:\> Set-WebConfigurationProperty '/connectionStrings/add[@name="ComplianceStatusConnectionString"]' -PSPath "IIS:\sites\Microsoft BitLocker Administration and Monitoring\MBAMAdministrationService" -Name "connectionString" -Value "Data Source=$SERVERNAME$\$SQLINSTANCENAME$;Initial Catalog=MBAM Compliance Status;Integrated Security=SSPI;"`

    `PS C:\> Set-WebConfigurationProperty '/connectionStrings/add[@name="Microsoft.Windows.Mdop.BitLockerManagement.StatusReportDataStore.ConnectionString"]' -PSPath "IIS:\sites\Microsoft BitLocker Administration and Monitoring\MBAMComplianceStatusService" -Name "connectionString" -Value "Data Source=$SERVERNAME$\$SQLINSTANCENAME;Initial Catalog=MBAM Compliance Status;Integrated Security=SSPI;"`

    **<span data-ttu-id="40975-271">注意</span><span class="sxs-lookup"><span data-stu-id="40975-271">Note</span></span>**  
    <span data-ttu-id="40975-272">將上述範例中的值取代為符合您環境的專案：</span><span class="sxs-lookup"><span data-stu-id="40975-272">Replace the value from the preceding example with those that match your environment:</span></span>

    -   <span data-ttu-id="40975-273">$SERVERNAME $ \ \ $SQLINSTANCENAME $-輸入恢復與硬體資料庫所在的伺服器名稱和實例名稱。</span><span class="sxs-lookup"><span data-stu-id="40975-273">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the server name and instance name where the Recovery and Hardware Database is located.</span></span>



**<span data-ttu-id="40975-274">若要繼續 MBAM 管理和監視網站的所有實例</span><span class="sxs-lookup"><span data-stu-id="40975-274">To resume all instances of the MBAM Administration and Monitoring website</span></span>**

1.  <span data-ttu-id="40975-275">在執行 MBAM 管理和監視功能的每個伺服器上，使用 Internet Information Services （IIS）管理員主控台來啟動名為**Microsoft BitLocker 管理和監視**的 MBAM 網站。</span><span class="sxs-lookup"><span data-stu-id="40975-275">On each of the servers running the MBAM Administration and Monitoring feature, use the Internet Information Services (IIS) Manager console to start the MBAM web site named **Microsoft BitLocker Administration and Monitoring**.</span></span>

2.  <span data-ttu-id="40975-276">若要自動化此程式，您可以使用 Windows PowerShell 輸入類似以下的命令：</span><span class="sxs-lookup"><span data-stu-id="40975-276">To automate this procedure, you can use Windows PowerShell to enter a command that is similar to the following:</span></span>

    **<span data-ttu-id="40975-277">PS C:\\ &gt; 啟動-網站 "Microsoft BitLocker 管理與監控"</span><span class="sxs-lookup"><span data-stu-id="40975-277">PS C:\\&gt; Start-Website “Microsoft BitLocker Administration and Monitoring”</span></span>**

## <span data-ttu-id="40975-278">移動合規性和審核報告</span><span class="sxs-lookup"><span data-stu-id="40975-278">To moving the Compliance and Audit Reports</span></span>


<span data-ttu-id="40975-279">如果您選擇將 MBAM 合規性和審核報告從一部電腦移到另一台電腦（特別是，如果您將功能從伺服器 A 移到伺服器 B），您應該使用下列程式及步驟：</span><span class="sxs-lookup"><span data-stu-id="40975-279">If you choose to move the MBAM Compliance and Audit Reports from one computer to another (specifically, if you move feature from Server A to Server B), you should use the following procedure and steps:</span></span>

1.  <span data-ttu-id="40975-280">在伺服器 B 上執行 MBAM 設定</span><span class="sxs-lookup"><span data-stu-id="40975-280">Run MBAM setup on Server B</span></span>

2.  <span data-ttu-id="40975-281">在伺服器 B 上設定合規性和審核報告的存取權</span><span class="sxs-lookup"><span data-stu-id="40975-281">Configure Access to the Compliance and Audit Reports on Server B</span></span>

3.  <span data-ttu-id="40975-282">停止 MBAM 管理和監視網站的所有實例</span><span class="sxs-lookup"><span data-stu-id="40975-282">Stop all instances of the MBAM Administration and Monitoring website</span></span>

4.  <span data-ttu-id="40975-283">更新 MBAM 管理和監視伺服器上的報表連線資料</span><span class="sxs-lookup"><span data-stu-id="40975-283">Update the reports connection data on MBAM Administration and Monitoring servers</span></span>

5.  <span data-ttu-id="40975-284">繼續 MBAM 管理和監視網站的所有實例</span><span class="sxs-lookup"><span data-stu-id="40975-284">Resume all instances of the MBAM Administration and Monitoring website</span></span>

**<span data-ttu-id="40975-285">若要在伺服器 B 上執行 MBAM 設定</span><span class="sxs-lookup"><span data-stu-id="40975-285">To run MBAM setup on Server B</span></span>**

1.  <span data-ttu-id="40975-286">在伺服器 B 上執行 MBAM 安裝程式，然後只選取要安裝的相容性和審核功能。</span><span class="sxs-lookup"><span data-stu-id="40975-286">Run MBAM setup on Server B and only select the Compliance and Audit feature for installation.</span></span>

2.  <span data-ttu-id="40975-287">若要自動執行此程式，您可以使用 Windows PowerShell，使用類似下列的命令：</span><span class="sxs-lookup"><span data-stu-id="40975-287">To automate this procedure, you can use a command that is similar to the following, by using Windows PowerShell:</span></span>

    `PS C:\> MbamSetup.exe /qn I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 AddLocal=Reports COMPLIDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ REPORTS_USERACCOUNTPW=$PASSWORD$`

    **<span data-ttu-id="40975-288">注意</span><span class="sxs-lookup"><span data-stu-id="40975-288">Note</span></span>**  
    <span data-ttu-id="40975-289">以與您的環境相符的方式，將前述範例中的值取代：</span><span class="sxs-lookup"><span data-stu-id="40975-289">Replace the values from the preceding example with those that match your environment:</span></span>

    -   <span data-ttu-id="40975-290">$SERVERNAME $ \ \ $SQLINSTANCENAME $-輸入合規性狀態資料庫所在的伺服器名稱和實例。</span><span class="sxs-lookup"><span data-stu-id="40975-290">$SERVERNAME$\\$SQLINSTANCENAME$ - Enter the server name and instance where the Compliance Status Database is located.</span></span>

    -   <span data-ttu-id="40975-291">$DOMAIN $ \ \ $USERNAME $-輸入要用來連線至合規性狀態資料庫的 [合規性] 和 [審核報告] 功能所使用的功能變數名稱和使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="40975-291">$DOMAIN$\\$USERNAME$ - Enter the domain name and user name that will be used by the Compliance and Audit reports feature to connect to the Compliance Status Database.</span></span>

    -   <span data-ttu-id="40975-292">$PASSWORD $-輸入將用來連線至合規性狀態資料庫之使用者帳戶的密碼。</span><span class="sxs-lookup"><span data-stu-id="40975-292">$PASSWORD$ - Enter the password of the user account that will be used to connect to the Compliance Status Database.</span></span>



**<span data-ttu-id="40975-293">在伺服器 B 上設定對合規性和審核報告的存取權</span><span class="sxs-lookup"><span data-stu-id="40975-293">To configure the access to the Compliance and Audit Reports on Server B</span></span>**

1.  <span data-ttu-id="40975-294">在伺服器 B 上，使用 [伺服器管理員] 中的 [本機使用者和群組] 管理單元，新增能夠存取合規性和審核報告的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="40975-294">On Server B, use the Local user and Groups snap-in from Server Manager to add the user accounts that will have access to the Compliance and Audit Reports.</span></span> <span data-ttu-id="40975-295">將使用者帳戶新增到名為「MBAM 報告使用者」的本機群組中。</span><span class="sxs-lookup"><span data-stu-id="40975-295">Add the user accounts to the local group named “MBAM Report Users”.</span></span>

2.  <span data-ttu-id="40975-296">若要自動化此程式，您可以使用與下列類似的命令，方法是在伺服器 B 上使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="40975-296">To automate this procedure, you can use a command that is similar to the following, by using Windows PowerShell on Server B.</span></span>

    `PS C:\> net localgroup "MBAM Report Users" $DOMAIN$\$REPORTSUSERNAME$  /add`

    **<span data-ttu-id="40975-297">注意</span><span class="sxs-lookup"><span data-stu-id="40975-297">Note</span></span>**  
    <span data-ttu-id="40975-298">將上述範例中的下列值取代為您的環境適用的值：</span><span class="sxs-lookup"><span data-stu-id="40975-298">Replace the following value from the preceding example with the applicable values for your environment:</span></span>

    -   <span data-ttu-id="40975-299">$DOMAIN $ \ \ $REPORTSUSERNAME $-輸入用來設定合規性和審核報告之資料來源的使用者帳戶名稱</span><span class="sxs-lookup"><span data-stu-id="40975-299">$DOMAIN$\\$REPORTSUSERNAME$ - Enter the user account name that was used to configure the data source for the Compliance and Audit reports</span></span>



~~~
The command to add the users to the MBAM Report Users local group must be run for each user that will be accessing the reports in your environment.
~~~

**<span data-ttu-id="40975-300">若要停止 MBAM 管理和監視網站的所有實例</span><span class="sxs-lookup"><span data-stu-id="40975-300">To stop all instances of the MBAM Administration and Monitoring website</span></span>**

1.  <span data-ttu-id="40975-301">在執行 MBAM 管理和監視功能的每個伺服器上，使用 Internet Information Services （IIS）管理員主控台來停止名為**Microsoft BitLocker 管理及監視**的 MBAM 網站。</span><span class="sxs-lookup"><span data-stu-id="40975-301">On each of the servers that run the MBAM Administration and Monitoring Feature use the Internet Information Services (IIS) Manager console to Stop the MBAM website named **Microsoft BitLocker Administration and Monitoring**.</span></span>

2.  <span data-ttu-id="40975-302">若要自動化此程式，您可以使用 Windows PowerShell，使用與下列命令類似的命令：</span><span class="sxs-lookup"><span data-stu-id="40975-302">To automate this procedure, you can use a command that is similar to the following one, by using Windows PowerShell:</span></span>

    `PS C:\> Stop-Website “Microsoft BitLocker Administration and Monitoring”`

**<span data-ttu-id="40975-303">在 MBAM 管理和監視伺服器上更新資料庫連線資料</span><span class="sxs-lookup"><span data-stu-id="40975-303">To update the Database Connection Data on MBAM Administration and Monitoring Servers</span></span>**

1. <span data-ttu-id="40975-304">在執行 MBAM 管理和監視功能的每個伺服器上，使用 Internet Information Services （IIS）管理員主控台來更新合規性報告 URL。</span><span class="sxs-lookup"><span data-stu-id="40975-304">On each of the servers that run the MBAM Administration and Monitoring Feature, use the Internet Information Services (IIS) Manager console to update the Compliance Reports URL.</span></span>

2. <span data-ttu-id="40975-305">選取 [ **Microsoft BitLocker 管理及監視**網站]，然後使用 [設定**編輯器**] 功能，可在**功能視圖**的 [**管理**] 區段下找到。</span><span class="sxs-lookup"><span data-stu-id="40975-305">Select the **Microsoft BitLocker Administration and Monitoring** website and use the **Configuration Editor** feature which can be found under the **Management** section of the **Feature View**.</span></span>

3. <span data-ttu-id="40975-306">從區段清單控制項選取 [ **appSettings** ] 選項。</span><span class="sxs-lookup"><span data-stu-id="40975-306">Select the **appSettings** option from the Section list control.</span></span>

4. <span data-ttu-id="40975-307">從這裡選取名為 **（集合）** 的列，然後選取列右側的按鈕來開啟**集合編輯器**。</span><span class="sxs-lookup"><span data-stu-id="40975-307">From here, select the row named **(Collection)**, and open the **Collection Editor** by selecting the button on the right side of the row.</span></span>

5. <span data-ttu-id="40975-308">在**集合編輯器**中，選取名為「Mbam. .url」的列。</span><span class="sxs-lookup"><span data-stu-id="40975-308">In the **Collection Editor**, select the row named “Microsoft.Mbam.Reports.Url”.</span></span>

6. <span data-ttu-id="40975-309">更新 Mbam 的值，以反映伺服器 B 的伺服器名稱。如果 [規範] 和 [審核報告] 功能安裝在命名的 SQL Reporting Services 實例上，請務必新增或更新該實例的名稱至 URL。</span><span class="sxs-lookup"><span data-stu-id="40975-309">Update the value for Microsoft.Mbam.Reports.Url to reflect the server name for Server B. If the Compliance and Audit reports feature was installed on a named SQL Reporting Services instance, make sure that you add or update the name of the instance to the URL.</span></span> <span data-ttu-id="40975-310">例如，HTTP://$SERVERNAME $/ReportServer\_ $ SQLSRSINSTANCENAME $/Pages..。。</span><span class="sxs-lookup"><span data-stu-id="40975-310">For example, http://$SERVERNAME$/ReportServer\_$SQLSRSINSTANCENAME$/Pages....</span></span>

7. <span data-ttu-id="40975-311">若要自動化此程式，您可以使用 Windows PowerShell，在每個管理和監視伺服器上輸入類似以下的命令：</span><span class="sxs-lookup"><span data-stu-id="40975-311">To automate this procedure, you can use Windows PowerShell to enter a command that is similar to the following one on each Administration and Monitoring Server:</span></span>

   `PS C:\> Set-WebConfigurationProperty '/appSettings/add[@key="Microsoft.Mbam.Reports.Url"]' -PSPath "IIS:\sites\Microsoft BitLocker Administration and Monitoring" -Name "Value" -Value “http://$SERVERNAME$/ReportServer_$SRSINSTANCENAME$/Pages/ReportViewer.aspx?/Malta+Compliance+Reports/”`

   **<span data-ttu-id="40975-312">注意</span><span class="sxs-lookup"><span data-stu-id="40975-312">Note</span></span>**  
   <span data-ttu-id="40975-313">將上述範例中的值取代為符合您環境的專案：</span><span class="sxs-lookup"><span data-stu-id="40975-313">Replace the value from the preceding example with those that match your environment:</span></span>

   -   <span data-ttu-id="40975-314">$SERVERNAME $-輸入已安裝 [合規性] 與 [審核報告] 的伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="40975-314">$SERVERNAME$ - Enter the name of the server to which the Compliance and Audit Reports were installed.</span></span>

   -   <span data-ttu-id="40975-315">$SRSINSTANCENAME $-輸入已安裝合規性和審核報告之 SQL Reporting Services 實例的名稱。</span><span class="sxs-lookup"><span data-stu-id="40975-315">$SRSINSTANCENAME$ - Enter the name of the SQL Reporting Services instance to which the Compliance and Audit Reports were installed.</span></span>



**<span data-ttu-id="40975-316">若要繼續 MBAM 管理和監視網站的所有實例</span><span class="sxs-lookup"><span data-stu-id="40975-316">To resume all instances of the MBAM Administration and Monitoring website</span></span>**

1.  <span data-ttu-id="40975-317">在執行 MBAM 管理和監視功能的每個伺服器上，使用 Internet Information Services （IIS）管理員主控台來啟動名為**Microsoft BitLocker 管理和監視**的 MBAM 網站。</span><span class="sxs-lookup"><span data-stu-id="40975-317">On each of the servers that run the MBAM Administration and Monitoring feature, use the Internet Information Services (IIS) Manager console to Start the MBAM web site named **Microsoft BitLocker Administration and Monitoring**.</span></span>

2.  <span data-ttu-id="40975-318">若要自動化此程式，您可以使用 Windows PowerShell，使用與下列命令類似的命令：</span><span class="sxs-lookup"><span data-stu-id="40975-318">To automate this procedure, you can use a command that is similar to the following one, by using Windows PowerShell:</span></span>

    `PS C:\> Start-Website “Microsoft BitLocker Administration and Monitoring”`

    **<span data-ttu-id="40975-319">注意</span><span class="sxs-lookup"><span data-stu-id="40975-319">Note</span></span>**  
    <span data-ttu-id="40975-320">若要執行此命令，必須將 PowerShell 的 IIS 模組新增到目前的 PowerShell 實例。</span><span class="sxs-lookup"><span data-stu-id="40975-320">To execute this command, the IIS Module for PowerShell must be added to the current instance of PowerShell.</span></span> <span data-ttu-id="40975-321">此外，您必須更新 PowerShell 執行原則，以啟用腳本執行。</span><span class="sxs-lookup"><span data-stu-id="40975-321">In addition, you must update the PowerShell execution policy to enable execution of scripts.</span></span>



## <span data-ttu-id="40975-322">若要移動 [管理及監視] 功能</span><span class="sxs-lookup"><span data-stu-id="40975-322">To move the Administration and Monitoring feature</span></span>


<span data-ttu-id="40975-323">如果您選擇將 [MBAM 管理] 和 [監視報告] 功能從一部電腦移到另一部，（如果您將功能從伺服器 A 移到伺服器 B），您應該使用下列程式。</span><span class="sxs-lookup"><span data-stu-id="40975-323">If you choose to move the MBAM Administration and Monitoring Reports feature from one computer to another, (if you move feature from Server A to Server B), you should use the following procedure.</span></span> <span data-ttu-id="40975-324">此套裝程式含下列步驟：</span><span class="sxs-lookup"><span data-stu-id="40975-324">The process includes the following steps:</span></span>

1.  <span data-ttu-id="40975-325">在伺服器 B 上執行 MBAM 設定</span><span class="sxs-lookup"><span data-stu-id="40975-325">Run MBAM setup on Server B</span></span>

2.  <span data-ttu-id="40975-326">在伺服器 B 上設定對資料庫的存取權</span><span class="sxs-lookup"><span data-stu-id="40975-326">Configure Access to the Database on Server B</span></span>

**<span data-ttu-id="40975-327">若要在伺服器 B 上執行 MBAM 設定</span><span class="sxs-lookup"><span data-stu-id="40975-327">To run MBAM setup on Server B</span></span>**

1.  <span data-ttu-id="40975-328">在伺服器 B 上執行 MBAM 安裝程式，然後只選取 [安裝] 的 [管理] 功能。</span><span class="sxs-lookup"><span data-stu-id="40975-328">Run MBAM setup on Server B and only select the Administration feature for installation.</span></span>

2.  <span data-ttu-id="40975-329">若要自動化此程式，您可以使用 Windows PowerShell，使用與下列命令類似的命令：</span><span class="sxs-lookup"><span data-stu-id="40975-329">To automate this procedure, you can use a command that is similar to the following one, by using Windows PowerShell:</span></span>

    `PS C:\> MbamSetup.exe /qn I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 AddLocal=AdministrationMonitoringServer,HardwareCompatibility COMPLIDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ RECOVERYANDHWDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ SRS_REPORTSITEURL=$REPORTSSERVERURL$`

    **<span data-ttu-id="40975-330">注意</span><span class="sxs-lookup"><span data-stu-id="40975-330">Note</span></span>**  
    <span data-ttu-id="40975-331">以與您的環境相符的方式，將前述範例中的值取代：</span><span class="sxs-lookup"><span data-stu-id="40975-331">Replace the values from the preceding example with those that match your environment:</span></span>

    -   <span data-ttu-id="40975-332">$SERVERNAME $ \ \ $SQLINSTANCENAME $-若為 COMPLIDB \ _SQLINSTANCE 參數，請輸入合規性狀態資料庫所在的伺服器名稱和實例。</span><span class="sxs-lookup"><span data-stu-id="40975-332">$SERVERNAME$\\$SQLINSTANCENAME$ - For the COMPLIDB\_SQLINSTANCE parameter, input the server name and instance where the Compliance Status Database is located.</span></span> <span data-ttu-id="40975-333">針對 RECOVERYANDHWDB \ _SQLINSTANCE 參數，輸入恢復與硬體資料庫所在的伺服器名稱和實例。</span><span class="sxs-lookup"><span data-stu-id="40975-333">For the RECOVERYANDHWDB\_SQLINSTANCE parameter, input the server name and instance where the Recovery and Hardware Database is located.</span></span>

    -   <span data-ttu-id="40975-334">$DOMAIN $ \ \ $USERNAME $-輸入將由合規性和審核報告功能用來連線至合規性狀態資料庫的網域和使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="40975-334">$DOMAIN$\\$USERNAME$ - Enter the domain and user name that will be used by the Compliance and Audit reports feature to connect to the Compliance Status Database.</span></span>

    -   <span data-ttu-id="40975-335">$ REPORTSSERVERURL $-輸入 SQL Reporting Services 網站之家用位置的 URL。</span><span class="sxs-lookup"><span data-stu-id="40975-335">$ REPORTSSERVERURL$ - Enter the URL for the Home location of the SQL Reporting Service website.</span></span> <span data-ttu-id="40975-336">如果報告已安裝到預設的 SRS 實例，URL 格式會格式化為「HTTP://$SERVERNAME $/ReportServer」。</span><span class="sxs-lookup"><span data-stu-id="40975-336">If the reports were installed to a default SRS instance the URL format will formatted “http:// $SERVERNAME$/ReportServer”.</span></span> <span data-ttu-id="40975-337">如果報告已安裝到預設的 SRS 實例，URL 格式將會格式化為 "HTTP://$SERVERNAME $/ReportServer\_ $ SQLINSTANCENAME $"。</span><span class="sxs-lookup"><span data-stu-id="40975-337">If the reports were installed to a default SRS instance, the URL format will be formatted to “http://$SERVERNAME$/ReportServer\_$SQLINSTANCENAME$”.</span></span>



**<span data-ttu-id="40975-338">設定資料庫的存取權</span><span class="sxs-lookup"><span data-stu-id="40975-338">To configure the Access to the Databases</span></span>**

1.  <span data-ttu-id="40975-339">在恢復與硬體所在的伺服器或伺服器上，而且已部署合規性和審核資料庫，請使用 [伺服器管理員] 中的 [本機使用者和群組] 管理單元，將電腦帳戶從執行 MBAM 管理和監視功能的每個伺服器新增到名為「MBAM 復原及硬體資料庫存取」（復原與硬體 DB 伺服器）和「MBAM 合規性狀態</span><span class="sxs-lookup"><span data-stu-id="40975-339">On server or servers where the Recovery and Hardware, and Compliance and Audit databases are deployed, use the Local user and Groups snap-in from Server Manager to add the machine accounts from each server that run the MBAM Administration and Monitoring feature to the Local Groups named “MBAM Recovery and Hardware DB Access” (Recovery and Hardware DB Server) and “MBAM Compliance Status DB Access” (Compliance and Audit DB Server).</span></span>

2.  <span data-ttu-id="40975-340">若要自動化此程式，您可以使用與下列命令類似的命令，方法是在部署合規性與審核資料庫的伺服器上使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="40975-340">To automate this procedure, you can use a command that is similar to the following one, by using Windows PowerShell on the server where the Compliance and Audit databases were deployed.</span></span>

    `PS C:\> net localgroup "MBAM Compliance Auditing DB Access" $DOMAIN$\$SERVERNAME$$  /add`

    `PS C:\> net localgroup "MBAM Compliance Auditing DB Access" $DOMAIN$\$REPORTSUSERNAME$  /add`

3.  <span data-ttu-id="40975-341">在部署復原與硬體資料庫的伺服器上，使用 Windows PowerShell 執行與下列命令類似的命令。</span><span class="sxs-lookup"><span data-stu-id="40975-341">On the server where the Recovery and Hardware databases were deployed, run a command that is similar to the following one, by using Windows PowerShell.</span></span>

    `PS C:\> net localgroup "MBAM Recovery and Hardware DB Access" $DOMAIN$\$SERVERNAME$$  /add`

    **<span data-ttu-id="40975-342">注意</span><span class="sxs-lookup"><span data-stu-id="40975-342">Note</span></span>**  
    <span data-ttu-id="40975-343">以適用于您環境的值取代前一個範例中的值：</span><span class="sxs-lookup"><span data-stu-id="40975-343">Replace the value from the preceding example with the applicable values for your environment:</span></span>

    -   <span data-ttu-id="40975-344">$DOMAIN $ \ \ $SERVERNAME $ $-輸入 MBAM 管理和監視伺服器的網域和電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="40975-344">$DOMAIN$\\$SERVERNAME$$ - Enter the domain and machine name of the MBAM Administration and Monitoring Server.</span></span> <span data-ttu-id="40975-345">伺服器名稱後面必須加 a **$** 。</span><span class="sxs-lookup"><span data-stu-id="40975-345">The server name must be followed by a **$**.</span></span> <span data-ttu-id="40975-346">例如，MyDomain\\MyServerName1 $）</span><span class="sxs-lookup"><span data-stu-id="40975-346">For example, MyDomain\\MyServerName1$)</span></span>

    -   <span data-ttu-id="40975-347">$DOMAIN $ \ \ $REPORTSUSERNAME $-輸入用來設定合規性和審核報告之資料來源的使用者帳戶名稱。</span><span class="sxs-lookup"><span data-stu-id="40975-347">$DOMAIN$\\$REPORTSUSERNAME$ - Enter the user account name that was used to configure the data source for the Compliance and Audit reports.</span></span>



~~~
The commands listed for adding the server computer accounts to the MBAM local groups must be run for each Administration and Monitoring Server that will be accessing the databases in your environment.
~~~

## <span data-ttu-id="40975-348">相關主題</span><span class="sxs-lookup"><span data-stu-id="40975-348">Related topics</span></span>


[<span data-ttu-id="40975-349">管理 MBAM 1.0 功能</span><span class="sxs-lookup"><span data-stu-id="40975-349">Administering MBAM 1.0 Features</span></span>](administering-mbam-10-features.md)









