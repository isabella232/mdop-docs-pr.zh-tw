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
# 如何移動 MBAM 2.5 資料庫

使用這些程式將下列資料庫從一部電腦移到另一部電腦;從伺服器 A 到伺服器 B，例如：

-   合規性和審核資料庫

-   復原資料庫

>[!NOTE]
>請務必先將資料庫還原到電腦 B，然後再執行 MBAM 設定向導來更新/設定。

如果資料庫不存在，則 [設定] 嚮導會建立新的、空的資料庫。 當您的現有資料庫已還原之後，此程式會中斷 MBAM 設定。

首先還原資料庫，然後執行 [MBAM 設定] 嚮導，選擇 [資料庫] 選項，[設定] 嚮導會將 [連線] 到您還原的資料庫;如有需要，請在程式中進行升級。

**如果您要移動多個功能，請以下列順序移動它們：**

1.  復原資料庫

2.  合規性和審核資料庫

3.  報告

4.  管理和監控網站

5.  自助服務入口網站

>[!Note]
>若要執行本主題中提供的 Windows PowerShell 腳本範例，您必須更新 Windows PowerShell 執行原則，才能執行腳本。 請參閱執行[Windows PowerShell 腳本](https://technet.microsoft.com/library/ee176949.aspx)以取得相關指示。

## 移動恢復資料庫

移動恢復資料庫的高層步驟如下：

1.  停止 MBAM 管理和監視網站的所有實例

2.  在伺服器 A 上備份恢復資料庫

3.  將恢復資料庫從伺服器 A 移至伺服器 B

4.  在伺服器 B 上還原恢復資料庫

5.  在伺服器 B 上設定對資料庫的存取權並更新連接資料

6.  在伺服器 B 上安裝 MBAM Server 軟體並執行 [MBAM 伺服器設定] 嚮導

7.  繼續管理和監控網站的實例

### 如何移動恢復資料庫

**停止 MBAM 管理和監視網站的所有實例。** 在執行 MBAM 管理和監視伺服器網站的每個伺服器上，使用 [網際網路資訊服務（IIS）管理員] 主控台來停止 [管理及監視] 網站。

若要自動化此程式，您可以使用 Windows PowerShell 輸入類似以下的命令：

```powershell
Stop-Website "Microsoft BitLocker Administration and Monitoring"
```

>[!NOTE]
>若要執行此命令，您必須將適用于 Windows PowerShell 的 Internet Information Services （IIS）模組新增到目前的 Windows PowerShell 實例。

### 在伺服器 A 上備份恢復資料庫

1.  使用 SQL Server Management Studio 中的 [**備份**] 工作來備份伺服器 A 上的 [恢復] 資料庫。 根據預設，資料庫名稱是 MBAM 的 [**恢復資料庫**]。

2.  若要自動化此程式，請建立包含下列 SQL 腳本的 SQL 檔案（.sql），並將 MBAM 復原資料庫變更為使用完整復原模式：

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

3.  使用下列值，以與您的環境相符的值來取代程式碼範例中的值：

    **$PASSWORD $** -用來加密私密金鑰檔案的密碼。

4.  在 Windows PowerShell 中，執行儲存在檔案中的腳本，並類似以下所示：

    ```powershell
    Invoke-Sqlcmd -InputFile
    'Z:\BackupMBAMRecoveryandHardwarDatabaseScript.sql' -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$
    ```
5.  使用下列值，以與您的環境相符的值來取代程式碼範例中的值：

    **$SERVERNAME $ \ $SQLINSTANCENAME $** -伺服器名稱和實例，將從它備份恢復資料庫。

### 將恢復資料庫從伺服器 A 移至伺服器 B

使用 Windows 資源管理器，將來自伺服器 A 的**MBAM 復原資料庫資料 .bak**檔案從伺服器 a 移至伺服器 B。

若要自動化此程式，您可以使用 Windows PowerShell 來執行類似下列的命令：

```powershell
Copy-Item "Z:\MBAM Recovery Database Data.bak"
\\$SERVERNAME$\$DESTINATIONSHARE$

Copy-Item "Z:\SQLServerInstanceCertificateFile"
\\$SERVERNAME$\$DESTINATIONSHARE$

Copy-Item "Z:\SQLServerInstanceCertificateFilePrivateKey"
\\$SERVERNAME$\$DESTINATIONSHARE$
```
您可以使用下表中的資訊，以與您的環境相符的值來取代程式碼範例中的值。

| **參數**        | **描述**  |
|----------------------|------------------|
| $SERVERNAME $       | 要將檔案複製到其中的伺服器名稱。 |
| $DESTINATIONSHARE $ | 要將檔案複製到其中的共用和路徑的名稱。 |


### 在伺服器 B 上還原恢復資料庫

1.  使用 SQL Server Management Studio 中的 [**還原資料庫**工作]，還原伺服器 B 上的復原資料庫。

2.  在前一個工作完成時，請選取 [**從裝置**]，然後選取資料庫備份檔案。

3.  使用 [ **Add** ] （新增）命令選取**MBAM 復原資料庫資料 .bak**盤案，然後按一下 **[確定]** 以完成還原程式。

4.  若要自動化此程式，請建立包含下列 SQL 腳本的 SQL 檔案（.sql）：

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

5.  使用下列值，以與您的環境相符的值來取代程式碼範例中的值。

    **$PASSWORD $** -您用來加密私密金鑰檔案的密碼。

6.  在 Windows PowerShell 中，執行儲存在檔案中的腳本，並類似以下所示：

    ```powershell
    Invoke-Sqlcmd -InputFile 'Z:\RestoreMBAMRecoveryandHardwarDatabaseScript.sql' -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$
    ```
7.  使用下列值，以與您的環境相符的值來取代程式碼範例中的值。

    **$SERVERNAME $ \ $SQLINSTANCENAME $** -要還原恢復資料庫的伺服器名稱和實例。

### 在伺服器 B 上設定對資料庫的存取權並更新連接資料

1. 確認在已還原的資料庫上啟用 [恢復資料庫存取] 的 Microsoft SQL Server 使用者登錄已對應至您在設定程式期間提供的 access 帳戶。

   >[!NOTE]
   >如果登入不相同，請使用 SQL Server Management Studio 建立登入，然後將它對應至現有的資料庫使用者。

2. 在執行管理和監視網站的伺服器上，使用 Internet Information Services （IIS）管理員主控台來更新 MBAM 網站的連線字串資訊。

3. 編輯下列登錄機碼：

   **HKLM\\Software\\Microsoft\\MBAM Server\\Web\\RecoveryDBConnectionString**

4. 使用伺服器和實例的名稱（例如，\ $SERVERNAME \ $ \\ $SQLINSTANCENAME）來更新已移動復原資料庫的**資料來源**值。

5. 使用已復原的資料庫名稱來更新**初始目錄**值。

6. 若要自動化此程式，您可以使用 Windows PowerShell 命令提示字元，在 [管理與監視伺服器] 上輸入如下所示的命令列：

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
   >這個連線字串是由所有本機 MBAM web 應用程式所共用。 因此，每個伺服器只需要更新一次。


7. 使用下表，以與您的環境相符的值來取代程式碼範例中的值。

   |參數|描述|
   |---------|-----------|
   |$SERVERNAME $/\ $SQLINSTANCENAME $|恢復資料庫所在之 SQL Server 的伺服器名稱和實例。|
   |$DATABASE $|恢復資料庫的名稱。|


### 在伺服器 B 上安裝 MBAM Server 軟體並執行 [MBAM 伺服器設定] 嚮導

1.  在伺服器 B 上安裝 MBAM 2.5 Server 軟體。如需詳細資訊，請參閱[安裝 MBAM 2.5 Server 軟體](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/installing-the-mbam-25-server-software)。

2.  在伺服器 B 上，啟動 [MBAM 伺服器設定向導]，按一下 [新增**功能**]，然後只選取 [**恢復資料庫**] 功能。 如需如何設定資料庫的詳細資訊，請參閱[如何設定 MBAM 2.5 資料庫](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-configure-the-mbam-25-databases)。

    >[!TIP]
    >或者，您也可以使用**Enable-MbamDatabase** Windows PowerShell Cmdlet 來設定恢復資料庫。


### 繼續管理和監控網站的實例

在執行管理和監視網站的伺服器上，使用 Internet Information Services （IIS）管理員主控台來啟動 [管理和監控] 網站。

若要自動化此程式，您可以使用 Windows PowerShell 來執行類似下列的命令：

```powershell
Start-Website "Microsoft BitLocker Administration and Monitoring"
```

>[!NOTE]
>若要執行此命令，您必須將適用于 Windows PowerShell 的 IIS 模組新增至目前的 Windows PowerShell 實例。

## 移動合規性和審核資料庫

移動合規性和審核資料庫的高層步驟如下：

1.  停止 MBAM 管理和監視網站的所有實例

2.  在伺服器 A 上備份合規性和審核資料庫

3.  將合規性和審核資料庫從伺服器 A 移至伺服器 B

4.  在伺服器 B 上還原合規性和審核資料庫

5.  在伺服器 B 上設定對資料庫的存取權並更新連接資料

6.  在伺服器 B 上安裝 MBAM Server 軟體並執行 [MBAM 伺服器設定] 嚮導

7.  繼續管理和監控網站的實例

### 如何移動合規性和審核資料庫

**停止 MBAM 管理和監視網站的所有實例。**  在執行 MBAM 管理和監視伺服器網站的每個伺服器上，使用 [網際網路資訊服務（IIS）管理員] 主控台來停止 [管理及監視] 網站。

若要自動化此程式，您可以使用 Windows PowerShell 輸入類似以下的命令：

```powershell
Stop-Website "Microsoft BitLocker Administration and Monitoring"
```

>[!NOTE]
>若要執行此命令，您必須將適用于 Windows PowerShell 的 Internet Information Services （IIS）模組新增到目前的 Windows PowerShell 實例。

### 在伺服器 A 上備份合規性和審核資料庫

1.  使用 SQL Server Management Studio 中的 [**備份**] 工作，在伺服器 A 上備份合規性和審核資料庫。根據預設，資料庫名稱是**MBAM 合規性狀態資料庫**。

2.  若要自動化此程式，請建立包含下列 SQL 腳本的 SQL 檔案（.sql）：

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

3.  使用類似下列的 Windows PowerShell 命令來執行儲存在 .sql 檔案中的腳本：

    ```powershell
    Invoke-Sqlcmd -InputFile "Z:\BackupMBAMComplianceStatusDatabaseScript.sql" –ServerInstance     $SERVERNAME$\$SQLINSTANCENAME$

    ```

4.  使用下列值，以與您的環境相符的值取代程式碼範例中的值：

    **$SERVERNAME $ \ $SQLINSTANCENAME $** -伺服器名稱和實例，將會將合規性和審核資料庫備份到其中。

### 將合規性和審核資料庫從伺服器 A 移至伺服器 B * *

1.  使用 Windows 資源管理器，將伺服器 A 的**MBAM 合規性狀態資料庫資料 .bak**檔案移至伺服器 B。

2.  若要自動化此程式，您可以使用 Windows PowerShell 來執行類似下列的命令：

    ```powershell
    Copy-Item "Z:\MBAM Compliance Status Database Data.bak"
    \\$SERVERNAME$\$DESTINATIONSHARE$
    ```

3.  使用下表，以與您的環境相符的值取代程式碼範例中的值。

    | **參數**        | **描述**                                               |
    |----------------------|---------------------------------------------------------------|
    | $SERVERNAME $       | 要將檔案複製到其中的伺服器名稱。         |
    | $DESTINATIONSHARE $ | 要將檔案複製到其中的共用和路徑的名稱。 |


### 在伺服器 B 上還原合規性和審核資料庫

1.  使用 SQL Server Management Studio 中的 [**還原資料庫**] 工作，在伺服器 B 上還原合規性和審核資料庫。

2.  在前一個工作完成時，請選取 [**從裝置**]，然後選取資料庫備份檔案。

3.  使用 [ **Add** ] （新增）命令選取**MBAM 合規性狀態資料庫資料 .bak**檔案，然後按一下 **[確定]** 以完成還原程式。

4.  若要自動化此程式，請建立包含下列 SQL 腳本的 SQL 檔案（.sql）：

    ```
    -- Create MBAM Compliance Status Database Data logical backup devices.

    Use master

    GO

    -- Restore the MBAM Compliance Status database data files.

    RESTORE DATABASE [MBAM Compliance Status]

    FROM DISK = 'C:\test\MBAM Compliance Status Database Data.bak'

    WITH REPLACE

    ```

5.  在 Windows PowerShell 中，執行儲存在檔案中的腳本，並類似以下所示：

    ```powershell
    Invoke-Sqlcmd -InputFile "Z:\RestoreMBAMComplianceStatusDatabaseScript.sql" -ServerInstance $SERVERNAME$\$SQLINSTANCENAME$

    ```

6.  使用下列值，以與您的環境相符的值取代程式碼範例中的值。

    **$SERVERNAME $ \ $SQLINSTANCENAME $** -伺服器名稱和實例，將會還原合規性和審核資料庫。

### 在伺服器 B 上設定對資料庫的存取權並更新連接資料

1. 確認在已還原的資料庫上啟用合規性和審核資料庫存取的 Microsoft SQL Server 使用者登入會對應到您在設定過程中提供的存取帳戶。

   >[!NOTE]
   >如果登入不相同，請使用 SQL Server Management Studio 建立登入，然後將它對應至現有的資料庫使用者。

2. 在執行管理和監視網站的伺服器上，使用 Internet Information Services （IIS）管理員主控台來更新網站的連線字串資訊。

3. 編輯下列登錄機碼：

   **HKLM\\Software\\Microsoft\\MBAM Server\\Web\\ComplianceDBConnectionString**

4. 使用伺服器和實例的名稱（例如，\ $SERVERNAME \ $ \\ $SQLINSTANCENAME）來更新已移動復原資料庫的**資料來源**值。

5. 使用已復原的資料庫名稱來更新**初始目錄**值。

6. 若要自動化此程式，您可以使用 Windows PowerShell 命令提示字元，在 [管理與監視伺服器] 上輸入如下所示的命令列：

   ```powershell
   reg add "HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MBAM Server\Web" /v
   ComplianceDBConnectionString /t REG_SZ /d "Integrated Security=SSPI;Initial
   Catalog=$DATABASE$;Data Source=$SERVERNAME$\$SQLINSTANCENAME$" /f
   ```
   >[!NOTE]
   >這個連線字串是由所有本機 MBAM web 應用程式所共用。 因此，每個伺服器只需要更新一次。


7. 使用下表，以與您的環境相符的值取代程式碼範例中的值。

   |參數 | 描述 |
   |---------|------------|
   |$SERVERNAME $ \ $SQLINSTANCENAME $ | 恢復資料庫所在之 SQL Server 的伺服器名稱和實例。|
   |$DATABASE $|已復原資料庫的名稱。|

### 在伺服器 B 上安裝 MBAM Server 軟體並執行 [MBAM 伺服器設定] 嚮導

1.  在伺服器 B 上安裝 MBAM 2.5 Server 軟體。如需詳細資訊，請參閱[安裝 MBAM 2.5 Server 軟體](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/installing-the-mbam-25-server-software)。

2.  在伺服器 B 上，啟動 [MBAM 伺服器設定] 嚮導，按一下 [新增**功能**]，然後只選取 [**合規性] 和 [審核資料庫**] 功能。 如需如何設定資料庫的詳細資訊，請參閱[如何設定 MBAM 2.5 資料庫](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-configure-the-mbam-25-databases)。

    >[!TIP]
    >或者，您也可以使用**Enable-MbamDatabase** Windows PowerShell Cmdlet 來設定合規性和審核資料庫。


### 繼續管理和監控網站的實例

在執行管理和監視網站的伺服器上，使用 Internet Information Services （IIS）管理員主控台來啟動 [管理和監控] 網站。

若要自動化此程式，您可以使用 Windows PowerShell 來執行類似下列的命令：

```powershell
Start-Website "Microsoft BitLocker Administration and Monitoring"
```

>[!NOTE]
>若要執行此命令，您必須將適用于 Windows PowerShell 的 IIS 模組新增至目前的 Windows PowerShell 實例。
