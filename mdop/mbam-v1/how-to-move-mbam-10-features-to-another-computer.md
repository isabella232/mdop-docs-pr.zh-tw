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
# 如何將 MBAM 1.0 功能移到其他電腦


本主題說明將一或多個 Microsoft BitLocker 管理和監控（MBAM）功能移至不同電腦時應採取的步驟。 當您將多個 MBAM 功能移至另一部電腦時，應依下列順序移動它們：

1.  恢復與硬體資料庫

2.  合規性和審核資料庫

3.  合規性與審計報告

4.  管理和監控

## 移動恢復與硬體資料庫


您可以使用下列程式，將 MBAM 復原和硬體資料庫從一部電腦移到另一台電腦（您可以將此 MBAM 伺服器功能從伺服器 A 移至伺服器 B）：

****

1.  停止 MBAM 管理和監視網站的所有實例。

2.  在伺服器 B 上執行 MBAM 設定。

3.  在伺服器 A 上備份 MBAM 復原與硬體資料庫。

4.  從伺服器 A MBAM 恢復和硬體資料庫至 B

5.  在伺服器 B 上還原 MBAM 復原與硬體資料庫

6.  在伺服器 B 上設定對 MBAM 復原和硬體資料庫的存取權

7.  更新 MBAM 管理和監視伺服器上的資料庫連線資料

8.  繼續 MBAM 管理和監控網站的所有實例

**若要停止 MBAM 管理和監視網站的所有實例**

1.  使用 Internet Information Services （IIS）管理員主控台，在執行 MBAM 管理和監視功能的每個伺服器上停止 MBAM 網站。 MBAM 網站已命名為**Microsoft BitLocker 管理和監視**。

2.  若要自動化此程式，您可以使用 Windows PowerShell，在命令提示字元中使用類似下列的命令：

    `PS C:\> Stop-Website “Microsoft BitLocker Administration and Monitoring”`

    **注意**  
    若要執行此 PowerShell 命令提示字元，您必須將 PowerShell 的 IIS 模組新增到 PowerShell 的目前實例。 此外，您必須更新 PowerShell 執行原則，以啟用腳本執行。



**若要在伺服器 B 上執行 MBAM 設定**

1.  在伺服器 B 上執行 [MBAM 設定]，然後選取要安裝的復原和硬體資料庫。

2.  若要自動化此程式，您可以使用 Windows PowerShell，在命令提示字元中使用類似下列的命令：

    `PS C:\> MbamSetup.exe /qn I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 AddLocal=KeyDatabase ADMINANDMON_MACHINENAMES=$DOMAIN$\$SERVERNAME$$ RECOVERYANDHWDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$`

    **注意**  
    在上述範例中，將下列值取代為符合您環境的專案：

    -   $SERVERNAME $ \ \ $SQLINSTANCENAME $-輸入要將恢復與硬體資料庫移動到其中的伺服器和實例名稱。

    -   $DOMAIN $ \ \ $SERVERNAME $-輸入每個 MBAM 應用程式和監視伺服器的網域和伺服器名稱，即可與復原與硬體資料庫聯繫。 如果有多個網域和伺服器名稱，請使用分號分隔清單中的每一個名稱。 例如，$DOMAIN \\SERVERNAME $; $DOMAIN \ \ $SERVERNAME $ $。 此外，每個伺服器名稱後面必須加 a **$** 。 例如，MyDomain\\MyServerName1 $，MyDomain\\MyServerName2 $。



**若要備份伺服器 A 上的資料庫**

1.  若要在伺服器 A 上備份復原和硬體資料庫，請使用 SQL Server Management Studio 及名為 [Back ...] 的工作 **。** 根據預設，資料庫名稱是**MBAM 復原和硬體資料庫**。

2.  若要自動化此程式，請建立包含下列 SQL 腳本的 SQL 檔案（.sql）：

    修改 MBAM 復原與硬體資料庫，以使用完整的復原模式。

    ```sql
    USE master;

    GO

    ALTER DATABASE "MBAM Recovery and Hardware"

       SET RECOVERY FULL;

    GO
    ```

    建立 MBAM 復原與硬體資料庫資料，並 MBAM 恢復邏輯備份裝置。

    ```sql
    USE master

    GO

    EXEC sp_addumpdevice 'disk', 'MBAM Recovery and Hardware Database Data Device',

    'Z:\MBAM Recovery and Hardware Database Data.bak';

    GO
    ```

    備份完整的 MBAM 還原與硬體資料庫。

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

    **注意**  
    以與您的環境相符的方式，將前述範例中的值取代：

    -   $PASSWORD $-輸入將用來加密私密金鑰檔案的密碼。



3.  使用 SQL Server PowerShell 和類似下列的命令來執行 SQL 檔案：

    `PS C:\> Invoke-Sqlcmd -InputFile 'Z:\BackupMBAMRecoveryandHardwarDatabaseScript.sql' -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$`

    **注意**  
    將上一個範例中的值取代成與您的環境相符的值：

    -   $SERVERNAME $ \ \ $SQLINSTANCENAME $-輸入伺服器的名稱，以及您要備份復原和硬體資料庫的實例。



**將資料庫和憑證從伺服器 A 移至 B**

1.  使用 Windows Explorer，將 MBAM 復原與硬體資料庫資料從伺服器 A 移到伺服器 B。

2.  若要移動加密資料庫的憑證，您將需要使用下列自動化步驟。 若要自動化此程式，您可以使用 Windows PowerShell 輸入類似以下的命令：

    `PS C:\> Copy-Item “Z:\MBAM Recovery and Hardware Database Data.bak” \\$SERVERNAME$\$DESTINATIONSHARE$`

    `PS C:\> Copy-Item “Z:\SQLServerInstanceCertificateFile” \\$SERVERNAME$\$DESTINATIONSHARE$`

    `PS C:\> Copy-Item “Z:\SQLServerInstanceCertificateFilePrivateKey” \\$SERVERNAME$\$DESTINATIONSHARE$`

    **注意**  
    將上述範例中的值取代為符合您環境的專案：

    -   $SERVERNAME $-輸入要將檔案複製到其中的伺服器名稱。

    -   $DESTINATIONSHARE $-輸入要將檔案複製到其中的共用名稱稱和路徑。



**在伺服器 B 上還原資料庫**

1.  在伺服器 B 上使用 SQL Server Management Studio 及名為 [**還原資料庫**] 的工作來還原恢復與硬體資料庫。

2.  工作執行之後，請選取 [**發件**人] 選項，然後使用 [Add] （**新增**）命令來選擇 [MBAM 復原] 和 [硬體資料庫**資料 .bak** ]。

3.  選取 **[確定]** 以完成還原程式。

4.  若要自動化此程式，請建立包含下列 SQL 腳本的 SQL 檔案（.sql）：

    ```sql
    -- Restore MBAM Recovery and Hardware Database. 

    USE master

    GO
    ```

    刪除由 MBAM 安裝程式所建立的憑證。

    ```sql
    DROP CERTIFICATE [MBAM Recovery Encryption Certificate]

    GO
    ```

    新增憑證

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

    還原 MBAM 復原及硬體資料庫資料及記錄檔。

    ```sql
    RESTORE DATABASE [MBAM Recovery and Hardware]

       FROM DISK = 'Z:\MBAM Recovery and Hardware Database Data.bak'

       WITH REPLACE
    ```

    **注意**  
    以與您的環境相符的方式，將前述範例中的值取代：

    -   $PASSWORD $-輸入您用來加密私人金鑰檔案的密碼。



5.  使用 Windows PowerShell 輸入類似以下的命令列：

    `PS C:\> Invoke-Sqlcmd -InputFile 'Z:\RestoreMBAMRecoveryandHardwarDatabaseScript.sql' -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$`

    **注意**  
    以與您的環境相符的方式，將 receding 範例中的值取代：

    -   $SERVERNAME $ \ \ $SQLINSTANCENAME $-輸入伺服器名稱，以及要還原恢復與硬體資料庫的實例。



**在伺服器 B 上設定對資料庫的存取權**

1.  在伺服器 B 上，使用 [伺服器管理員] 中的 [本機使用者和群組] 管理單元，將每個伺服器上執行 MBAM 管理和監控功能的電腦帳戶新增到名為 [MBAM 復原]**和 [硬體資料庫存取**] 的本機群組。

2.  若要自動化此程式，您可以在伺服器 B 上使用 Windows PowerShell，輸入類似以下的命令：

    `PS C:\> net localgroup "MBAM Recovery and Hardware DB Access" $DOMAIN$\$SERVERNAME$$  /add`

    **注意**  
    以適用于您環境的值取代上述範例中的值：

    -   $DOMAIN $ \ \ $SERVERNAME $ $-輸入 MBAM 管理和監視伺服器的功能變數名稱和電腦名稱稱。 伺服器名後面必須加 a **$** ，例如，MyDomain\\MyServerName1 $。



~~~
You must run the command for each Administration and Monitoring Server that will be accessing the database in your environment.
~~~

**在 MBAM 管理和監視伺服器上更新資料庫連線資料**

1. 在執行 MBAM 管理和監視功能的每個伺服器上，使用 Internet Information Services （IIS）管理員主控台來更新下列應用程式的連線字串資訊，這些應用程式是由 Microsoft BitLocker 管理和監視網站所託管。

   -   MBAM 系統管理服務

   -   MBAM 恢復與硬體服務

2. 選取每個應用程式，並使用 [設定**編輯器**] 功能（位於**功能視圖**的 [**管理**] 區段底下）。

3. 從區段清單控制項選取 [ **configurationStrings** ] 選項。

4. 選擇名為 **（集合）** 的列，然後選取列右側的按鈕來開啟**集合編輯器**。

5. 在**集合編輯器**中，當您更新「MBAMAdministrationService」應用程式的設定時，請選擇名為**KeyRecoveryConnectionString**的列，或選擇名為 Mbam 的列 <strong> 。 </strong>ConnectionString，更新 "MBAMRecoveryAndHardwareService" 的設定。

6. 更新**configurationStrings**屬性的**資料來源 =** 值，以列出伺服器名稱，以及將復原和硬體資料庫移動到哪個實例。 例如，$SERVERNAME $ \ \ $SQLINSTANCENAME $。

7. 若要自動化此程式，您可以使用與下列命令類似的命令，方法是在每個管理和監視伺服器上使用 Windows PowerShell：

   `PS C:\> Set-WebConfigurationProperty '/connectionStrings/add[@name="KeyRecoveryConnectionString"]' -PSPath "IIS:\sites\Microsoft BitLocker Administration and Monitoring\MBAMAdministrationService" -Name "connectionString" -Value “Data Source=$SERVERNAME$\$SQLINSTANCENAME$;Initial Catalog=MBAM Recovery and Hardware;Integrated Security=SSPI;”`

   `PS C:\> Set-WebConfigurationProperty '/connectionStrings/add[@name="Microsoft.Mbam.RecoveryAndHardwareDataStore.ConnectionString"]' -PSPath "IIS:\sites\Microsoft BitLocker Administration and Monitoring\MBAMRecoveryAndHardwareService" -Name "connectionString" -Value "Data Source=$SERVERNAME$\$SQLINSTANCENAME$;Initial Catalog=MBAM Recovery and Hardware;Integrated Security=SSPI;"`

   **注意**  
   將上述範例中的值取代為符合您環境的專案：

   -   $SERVERNAME $ \ \ $SQLINSTANCENAME $-輸入 [恢復] 和 [硬體] 資料庫所在的伺服器名稱和實例。



**若要繼續 MBAM 管理和監視網站的所有實例**

1.  在執行 MBAM 管理和監視功能的每個伺服器上，使用 Internet Information Services （IIS）管理員主控台來啟動名為**Microsoft BitLocker 管理和監視**的 MBAM 網站。

2.  若要自動化此程式，您可以使用 Windows PowerShell，使用與下列命令類似的命令：

    `PS C:\> Start-Website “Microsoft BitLocker Administration and Monitoring”`

## 若要移動 [合規性狀態資料庫] 功能


如果您選擇將 [MBAM 合規性狀態資料庫] 功能從一部電腦移到另一台電腦（例如從伺服器 A 移至伺服器 B），您應該使用下列程式：

1.  停止 MBAM 管理和監視網站的所有實例

2.  在伺服器 B 上執行 MBAM 設定

3.  在伺服器 A 上備份資料庫

4.  將資料庫從伺服器 A 移至 B

5.  在伺服器 B 上還原資料庫

6.  在伺服器 B 上設定對資料庫的存取權

7.  在 MBAM 管理和監視伺服器上更新資料庫連線資料

8.  繼續 MBAM 管理和監視網站的所有實例

**若要停止 MBAM 管理和監視網站的所有實例**

1.  在執行 MBAM 管理和監視功能的每個伺服器上，使用 Internet Information Services （IIS）管理員主控台來停止名為**Microsoft BitLocker 管理和監視**的 MBAM 網站。

2.  若要自動化此程式，您可以使用 Windows PowerShell，使用與下列命令類似的命令：

    `PS C:\> Stop-Website “Microsoft BitLocker Administration and Monitoring”`

    **注意**  
    若要執行此命令，您必須將 PowerShell 的 IIS 模組新增至目前的 PowerShell 實例。 此外，您必須更新 PowerShell 執行原則，以啟用腳本執行。



**若要在伺服器 B 上執行 MBAM 設定**

1.  在伺服器 B 上執行 MBAM 安裝程式，然後選取 [規範狀態資料庫] 功能以進行安裝。

2.  若要自動化此程式，您可以使用 Windows PowerShell，使用與下列命令類似的命令：

    `PS C:\> MbamSetup.exe /qn I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 AddLocal= ReportsDatabase ADMINANDMON_MACHINENAMES=$DOMAIN$\$SERVERNAME$ COMPLIDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ REPORTS_USERACCOUNT=$DOMAIN$\$USERNAME$`

    **注意**  
    以與您的環境相符的方式，將前述範例中的值取代：

    -   $SERVERNAME $ \ \ $SQLINSTANCENAME $-輸入要將合規性狀態資料庫移至其中的伺服器名稱和實例。

    -   $DOMAIN $ \ \ $SERVERNAME $-輸入每個 MBAM 應用程式和監視伺服器的功能變數名稱和伺服器名稱，即可與合規性狀態資料庫聯繫。 如果有多個功能變數名稱和伺服器名稱，請使用分號分隔清單中的每一個名稱。 例如，$DOMAIN \\SERVERNAME $; $DOMAIN \ \ $SERVERNAME $ $。 每個伺服器名稱後面必須加 a **$** ，如範例所示。 例如，MyDomain\\MyServerName1 $，MyDomain\\MyServerName2 $。

    -   $DOMAIN $ \ \ $USERNAME $-輸入將由合規性和審核報告功能用來連線至合規性狀態資料庫的網域和使用者名稱。



**若要在伺服器 A 上備份合規性資料庫**

1.  若要在伺服器 A 上備份合規性資料庫，請使用 SQL Server Management Studio 及名為 [ **Back up ...**] 的工作。 根據預設，資料庫名稱是**MBAM 合規性狀態資料庫**。

2.  若要自動化此程式，請建立包含下列 SQL 腳本的 SQL 檔案（.sql）：

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

3.  使用 SQL Server PowerShell，執行 SQL 檔案，並使用與下列命令類似的命令：

    `PS C:\> Invoke-Sqlcmd -InputFile "Z:\BackupMBAMComplianceStatusDatabaseScript.sql" –ServerInstance $SERVERNAME$\$SQLINSTANCENAME$`

    **注意**  
    將上述範例中的值取代為符合您環境的專案：

    -   $SERVERNAME $ \ \ $SQLINSTANCENAME $-輸入伺服器名稱，以及將備份合規性狀態資料庫的實例。



**若要將資料庫從伺服器 A 移至 B**

1.  使用 Windows Explorer 將下列檔案從伺服器 A 移至伺服器 B：

    -   MBAM 合規性狀態資料庫資料 .bak

2.  若要自動化此程式，您可以使用與下列使用 Windows PowerShell 類似的命令：

    `PS C:\> Copy-Item “Z:\MBAM Compliance Status Database Data.bak” \\$SERVERNAME$\$DESTINATIONSHARE$`

    **注意**  
    將上述範例中的值取代為符合您環境的專案：

    -   $SERVERNAME $-輸入要將檔案複製到其中的伺服器名稱。

    -   $DESTINATIONSHARE $-輸入要將檔案複製到其中的共用名稱稱和路徑。



**在伺服器 B 上還原資料庫**

1.  在伺服器 B 上使用 SQL Server Management Studio 及名為 [**還原資料庫 ...**] 的工作來還原合規性狀態資料庫 .。。

2.  執行工作後，選取資料庫備份檔案，方法是選取 [寄件者] 選項，然後使用 [Add] （新增）命令，選擇 [MBAM 合規性狀態資料庫資料 .bak] 檔。 按一下 [確定] 以完成還原程式。

3.  若要自動化此程式，請建立包含下列 SQL 腳本的 SQL 檔案（.sql）：

    ```sql
    -- Create MBAM Compliance Status Database Data logical backup devices. 

    Use master

    GO

    -- Restore the MBAM Compliance Status database data files.

    RESTORE DATABASE [MBAM Compliance Status Database]

       FROM DISK = 'C:\test\MBAM Compliance Status Database Data.bak'

       WITH REPLACE
    ```

4.  使用 SQL Server PowerShell，執行 SQL 檔案，並使用與下列命令類似的命令：

    `PS C:\> Invoke-Sqlcmd -InputFile "Z:\RestoreMBAMComplianceStatusDatabaseScript.sql" -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$`

    **注意**  
    將上述範例中的值取代為符合您環境的專案：

    -   $SERVERNAME $ \ \ $SQLINSTANCENAME $-輸入將會還原合規性狀態資料庫的伺服器名稱和實例。



**在伺服器 B 上設定對資料庫的存取權**

1.  在伺服器 B 上，使用 [伺服器管理員] 中的 [本機使用者和群組] 管理單元，將每個伺服器上執行 MBAM 管理和監控功能的電腦帳戶新增到名為 [ **MBAM 合規性狀態 DB 存取**] 的本機群組。

2.  若要自動化此程式，您可以使用與下列命令類似的命令，方法是在伺服器 B 上使用 Windows PowerShell：

    `PS C:\> net localgroup "MBAM Compliance Auditing DB Access" $DOMAIN$\$SERVERNAME$$  /add`

    `PS C:\> net localgroup "MBAM Compliance Auditing DB Access" $DOMAIN$\$REPORTSUSERNAME$  /add`

    **注意**  
    以適用于您環境的值取代前一個範例中的值：

    -   $DOMAIN $ \ \ $SERVERNAME $ $-輸入 MBAM 管理和監視伺服器的網域和電腦名稱稱。 伺服器名稱後面必須加 a **$** 。例如，MyDomain\\MyServerName1 $。

    -   $DOMAIN $ \ \ $REPORTSUSERNAME $-輸入用來設定合規性和審核報告之資料來源的使用者帳戶名稱



~~~
For each Administration and Monitoring Server that will access the database of your environment, you must run the command that will add the servers to the MBAM Compliance Auditing DB Access local group.
~~~

**在 MBAM 管理和監視伺服器上更新資料庫連線資料**

1.  在執行 MBAM 管理和監視功能的每個伺服器上，使用 Internet Information Services （IIS）管理員主控台來更新下列應用程式的連線字串資訊，這些應用程式是由 Microsoft BitLocker 管理和監視網站所託管。

    -   MBAMAdministrationService

    -   MBAMComplianceStatusService

2.  選取每個應用程式，並使用 [設定**編輯器**] 功能（位於**功能視圖**的 [**管理**] 區段底下）。

3.  從區段清單控制項選取 [ **configurationStrings** ] 選項。

4.  選取名為 **（集合）** 的列，然後選取列右側的按鈕來開啟集合編輯器。

5.  在**集合編輯器**中，當您更新 MBAMComplianceStatusService 的設定時，請選取名為**ComplianceStatusConnectionString**的列、更新 MBAMAdministrationService 應用程式的設定，或是名為**BitLockerManagement**的列。

6.  更新**configurationStrings**屬性的**資料來源 =** 值，以列出伺服器名稱和實例名稱。 例如，$SERVERNAME $ \ \ $SQLINSTANCENAME，即會將復原和硬體資料庫移動到哪個位置。

7.  若要自動化此程式，您可以使用 Windows PowerShell，在每個管理和監視伺服器上輸入類似以下的命令：

    `PS C:\> Set-WebConfigurationProperty '/connectionStrings/add[@name="ComplianceStatusConnectionString"]' -PSPath "IIS:\sites\Microsoft BitLocker Administration and Monitoring\MBAMAdministrationService" -Name "connectionString" -Value "Data Source=$SERVERNAME$\$SQLINSTANCENAME$;Initial Catalog=MBAM Compliance Status;Integrated Security=SSPI;"`

    `PS C:\> Set-WebConfigurationProperty '/connectionStrings/add[@name="Microsoft.Windows.Mdop.BitLockerManagement.StatusReportDataStore.ConnectionString"]' -PSPath "IIS:\sites\Microsoft BitLocker Administration and Monitoring\MBAMComplianceStatusService" -Name "connectionString" -Value "Data Source=$SERVERNAME$\$SQLINSTANCENAME;Initial Catalog=MBAM Compliance Status;Integrated Security=SSPI;"`

    **注意**  
    將上述範例中的值取代為符合您環境的專案：

    -   $SERVERNAME $ \ \ $SQLINSTANCENAME $-輸入恢復與硬體資料庫所在的伺服器名稱和實例名稱。



**若要繼續 MBAM 管理和監視網站的所有實例**

1.  在執行 MBAM 管理和監視功能的每個伺服器上，使用 Internet Information Services （IIS）管理員主控台來啟動名為**Microsoft BitLocker 管理和監視**的 MBAM 網站。

2.  若要自動化此程式，您可以使用 Windows PowerShell 輸入類似以下的命令：

    **PS C:\\ &gt; 啟動-網站 "Microsoft BitLocker 管理與監控"**

## 移動合規性和審核報告


如果您選擇將 MBAM 合規性和審核報告從一部電腦移到另一台電腦（特別是，如果您將功能從伺服器 A 移到伺服器 B），您應該使用下列程式及步驟：

1.  在伺服器 B 上執行 MBAM 設定

2.  在伺服器 B 上設定合規性和審核報告的存取權

3.  停止 MBAM 管理和監視網站的所有實例

4.  更新 MBAM 管理和監視伺服器上的報表連線資料

5.  繼續 MBAM 管理和監視網站的所有實例

**若要在伺服器 B 上執行 MBAM 設定**

1.  在伺服器 B 上執行 MBAM 安裝程式，然後只選取要安裝的相容性和審核功能。

2.  若要自動執行此程式，您可以使用 Windows PowerShell，使用類似下列的命令：

    `PS C:\> MbamSetup.exe /qn I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 AddLocal=Reports COMPLIDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ REPORTS_USERACCOUNTPW=$PASSWORD$`

    **注意**  
    以與您的環境相符的方式，將前述範例中的值取代：

    -   $SERVERNAME $ \ \ $SQLINSTANCENAME $-輸入合規性狀態資料庫所在的伺服器名稱和實例。

    -   $DOMAIN $ \ \ $USERNAME $-輸入要用來連線至合規性狀態資料庫的 [合規性] 和 [審核報告] 功能所使用的功能變數名稱和使用者名稱。

    -   $PASSWORD $-輸入將用來連線至合規性狀態資料庫之使用者帳戶的密碼。



**在伺服器 B 上設定對合規性和審核報告的存取權**

1.  在伺服器 B 上，使用 [伺服器管理員] 中的 [本機使用者和群組] 管理單元，新增能夠存取合規性和審核報告的使用者帳戶。 將使用者帳戶新增到名為「MBAM 報告使用者」的本機群組中。

2.  若要自動化此程式，您可以使用與下列類似的命令，方法是在伺服器 B 上使用 Windows PowerShell。

    `PS C:\> net localgroup "MBAM Report Users" $DOMAIN$\$REPORTSUSERNAME$  /add`

    **注意**  
    將上述範例中的下列值取代為您的環境適用的值：

    -   $DOMAIN $ \ \ $REPORTSUSERNAME $-輸入用來設定合規性和審核報告之資料來源的使用者帳戶名稱



~~~
The command to add the users to the MBAM Report Users local group must be run for each user that will be accessing the reports in your environment.
~~~

**若要停止 MBAM 管理和監視網站的所有實例**

1.  在執行 MBAM 管理和監視功能的每個伺服器上，使用 Internet Information Services （IIS）管理員主控台來停止名為**Microsoft BitLocker 管理及監視**的 MBAM 網站。

2.  若要自動化此程式，您可以使用 Windows PowerShell，使用與下列命令類似的命令：

    `PS C:\> Stop-Website “Microsoft BitLocker Administration and Monitoring”`

**在 MBAM 管理和監視伺服器上更新資料庫連線資料**

1. 在執行 MBAM 管理和監視功能的每個伺服器上，使用 Internet Information Services （IIS）管理員主控台來更新合規性報告 URL。

2. 選取 [ **Microsoft BitLocker 管理及監視**網站]，然後使用 [設定**編輯器**] 功能，可在**功能視圖**的 [**管理**] 區段下找到。

3. 從區段清單控制項選取 [ **appSettings** ] 選項。

4. 從這裡選取名為 **（集合）** 的列，然後選取列右側的按鈕來開啟**集合編輯器**。

5. 在**集合編輯器**中，選取名為「Mbam. .url」的列。

6. 更新 Mbam 的值，以反映伺服器 B 的伺服器名稱。如果 [規範] 和 [審核報告] 功能安裝在命名的 SQL Reporting Services 實例上，請務必新增或更新該實例的名稱至 URL。 例如，HTTP://$SERVERNAME $/ReportServer\_ $ SQLSRSINSTANCENAME $/Pages..。。

7. 若要自動化此程式，您可以使用 Windows PowerShell，在每個管理和監視伺服器上輸入類似以下的命令：

   `PS C:\> Set-WebConfigurationProperty '/appSettings/add[@key="Microsoft.Mbam.Reports.Url"]' -PSPath "IIS:\sites\Microsoft BitLocker Administration and Monitoring" -Name "Value" -Value “http://$SERVERNAME$/ReportServer_$SRSINSTANCENAME$/Pages/ReportViewer.aspx?/Malta+Compliance+Reports/”`

   **注意**  
   將上述範例中的值取代為符合您環境的專案：

   -   $SERVERNAME $-輸入已安裝 [合規性] 與 [審核報告] 的伺服器名稱。

   -   $SRSINSTANCENAME $-輸入已安裝合規性和審核報告之 SQL Reporting Services 實例的名稱。



**若要繼續 MBAM 管理和監視網站的所有實例**

1.  在執行 MBAM 管理和監視功能的每個伺服器上，使用 Internet Information Services （IIS）管理員主控台來啟動名為**Microsoft BitLocker 管理和監視**的 MBAM 網站。

2.  若要自動化此程式，您可以使用 Windows PowerShell，使用與下列命令類似的命令：

    `PS C:\> Start-Website “Microsoft BitLocker Administration and Monitoring”`

    **注意**  
    若要執行此命令，必須將 PowerShell 的 IIS 模組新增到目前的 PowerShell 實例。 此外，您必須更新 PowerShell 執行原則，以啟用腳本執行。



## 若要移動 [管理及監視] 功能


如果您選擇將 [MBAM 管理] 和 [監視報告] 功能從一部電腦移到另一部，（如果您將功能從伺服器 A 移到伺服器 B），您應該使用下列程式。 此套裝程式含下列步驟：

1.  在伺服器 B 上執行 MBAM 設定

2.  在伺服器 B 上設定對資料庫的存取權

**若要在伺服器 B 上執行 MBAM 設定**

1.  在伺服器 B 上執行 MBAM 安裝程式，然後只選取 [安裝] 的 [管理] 功能。

2.  若要自動化此程式，您可以使用 Windows PowerShell，使用與下列命令類似的命令：

    `PS C:\> MbamSetup.exe /qn I_ACCEPT_ENDUSER_LICENSE_AGREEMENT=1 AddLocal=AdministrationMonitoringServer,HardwareCompatibility COMPLIDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ RECOVERYANDHWDB_SQLINSTANCE=$SERVERNAME$\$SQLINSTANCENAME$ SRS_REPORTSITEURL=$REPORTSSERVERURL$`

    **注意**  
    以與您的環境相符的方式，將前述範例中的值取代：

    -   $SERVERNAME $ \ \ $SQLINSTANCENAME $-若為 COMPLIDB \ _SQLINSTANCE 參數，請輸入合規性狀態資料庫所在的伺服器名稱和實例。 針對 RECOVERYANDHWDB \ _SQLINSTANCE 參數，輸入恢復與硬體資料庫所在的伺服器名稱和實例。

    -   $DOMAIN $ \ \ $USERNAME $-輸入將由合規性和審核報告功能用來連線至合規性狀態資料庫的網域和使用者名稱。

    -   $ REPORTSSERVERURL $-輸入 SQL Reporting Services 網站之家用位置的 URL。 如果報告已安裝到預設的 SRS 實例，URL 格式會格式化為「HTTP://$SERVERNAME $/ReportServer」。 如果報告已安裝到預設的 SRS 實例，URL 格式將會格式化為 "HTTP://$SERVERNAME $/ReportServer\_ $ SQLINSTANCENAME $"。



**設定資料庫的存取權**

1.  在恢復與硬體所在的伺服器或伺服器上，而且已部署合規性和審核資料庫，請使用 [伺服器管理員] 中的 [本機使用者和群組] 管理單元，將電腦帳戶從執行 MBAM 管理和監視功能的每個伺服器新增到名為「MBAM 復原及硬體資料庫存取」（復原與硬體 DB 伺服器）和「MBAM 合規性狀態

2.  若要自動化此程式，您可以使用與下列命令類似的命令，方法是在部署合規性與審核資料庫的伺服器上使用 Windows PowerShell。

    `PS C:\> net localgroup "MBAM Compliance Auditing DB Access" $DOMAIN$\$SERVERNAME$$  /add`

    `PS C:\> net localgroup "MBAM Compliance Auditing DB Access" $DOMAIN$\$REPORTSUSERNAME$  /add`

3.  在部署復原與硬體資料庫的伺服器上，使用 Windows PowerShell 執行與下列命令類似的命令。

    `PS C:\> net localgroup "MBAM Recovery and Hardware DB Access" $DOMAIN$\$SERVERNAME$$  /add`

    **注意**  
    以適用于您環境的值取代前一個範例中的值：

    -   $DOMAIN $ \ \ $SERVERNAME $ $-輸入 MBAM 管理和監視伺服器的網域和電腦名稱稱。 伺服器名稱後面必須加 a **$** 。 例如，MyDomain\\MyServerName1 $）

    -   $DOMAIN $ \ \ $REPORTSUSERNAME $-輸入用來設定合規性和審核報告之資料來源的使用者帳戶名稱。



~~~
The commands listed for adding the server computer accounts to the MBAM local groups must be run for each Administration and Monitoring Server that will be accessing the databases in your environment.
~~~

## 相關主題


[管理 MBAM 1.0 功能](administering-mbam-10-features.md)









