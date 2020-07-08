---
title: MBAM 2.5 安裝問題疑難排解
description: 簡介如何針對 MBAM 2.5 安裝問題進行疑難排解。
author: Deland-Han
ms.reviewer: dcscontentpm
manager: dansimp
ms.author: delhan
ms.sitesec: library
ms.prod: w10
ms.date: 09/16/2019
ms.openlocfilehash: ed56a87496e09601c44028b7f948eda39143e8c0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800200"
---
# MBAM 2.5 安裝問題疑難排解

本文將說明如何在獨立設定中針對 Microsoft BitLocker 管理和監控（MBAM）2.5 安裝問題進行疑難排解。

## 參照 MBAM 記錄檔以進行疑難排解

MBAM 包括伺服器安裝、用戶端安裝和事件的記錄。 應參閱此記錄以進行疑難排解。 
 
### MBAM server 安裝記錄檔

在 MBAM 安裝期間，MBAMServerSetup.exe 會在使用者的% temp% 資料夾中產生下列記錄檔：<br /> **Microsoft_BitLocker_Administration_and_Monitoring_<14 個數字> .log**

MBAMServerSetup.exe 記錄在 MBAM 設定和 MBAM 伺服器功能安裝期間所採取的動作：<br /> **Microsoft_BitLocker_Administration_and_Monitoring_<14_numbers # C1_0_MBAMServer.msi .log**

MBAMServerSetup.exe 記錄安裝期間所採取的其他動作。

### MBAM 用戶端安裝記錄檔

用戶端安裝會記錄在% temp% 資料夾中的下列記錄檔（或自訂位置，視用戶端的安裝方式而定）： <br />**MSI \<five random characters\> .log**

此記錄包含在 MBAM 用戶端安裝期間所採取的動作。
 
### MBAM 用戶端事件-記錄通道

MBAM 有個別的事件記錄通道。 系統會在事件檢視器的 [**應用程式和服務記錄**  >  **Microsoft**  >  **Windows**  >  **MBAM**] 底下找到 [管理員]、[分析] 和 [操作] 記錄檔。

下表提供每個事件記錄記錄的簡短描述。
 
|事件記錄檔| 說明|
|----------|-------|
|Microsoft-Windows-MBAM/系統管理員|  包含錯誤訊息|
|Microsoft-Windows-MBAM/分析|   包含高級記錄資訊|
|Microsoft-Windows-MBAM/運作|    包含成功訊息|

### MBAM 伺服器事件-記錄通道

記錄檔位於 [事件檢視器] 中的 [**應用程式和服務記錄**  >  **Microsoft**  >  **Windows**  >  **MBAM**] 底下。 下表包含在 MBAM 2.5 中引入的伺服器事件記錄：

|事件記錄檔| 說明|
|--------|-------------|
|Microsoft-Windows-MBAM/系統管理員|  包含錯誤訊息|
|Microsoft-Windows-MBAM/分析|   包含高級記錄資訊|
|Microsoft-Windows-MBAM/運作|    包含成功訊息|

### MBAM web 服務記錄

每個 MBAM web 服務記錄都會將記錄資訊寫入 SVCLOG 檔案。 根據預設，每個 web 服務都會在 C:\inetpub\Microsoft BitLocker 管理 Solution\Logs 資料夾中使用其名稱的資料夾下寫入追蹤檔案。

您可以使用服務追蹤檢視器工具（Microsoft Visual Studio 的一部分）來查看 svclog 追蹤。

## 疑難排解加密和報告問題

本節包含伺服器功能、用戶端功能、配置設定及已知問題的疑難排解資訊：
 
### MBAM 用戶端安裝，群組原則設定

判斷用戶端電腦上是否已安裝 MBAM 代理程式。 安裝 MBAM 時，它會建立一個名為 BitLocker 管理用戶端服務的服務。 此服務已設定為自動啟動。 判斷服務是否正在執行。

確定用戶端電腦上已套用 [MBAM] 群組原則設定。 如果用戶端電腦上已套用群組原則設定，就會建立下列登錄子機碼： **HKEY_LOCAL_MACHINE \software\policies\microsoft\fve\mdopbitlockermanagement**

確認此金鑰存在，並使用每個群組原則設定的值來填入。

### 在初始延遲期間 MBAM 代理程式

MBAM 用戶端無法在安裝後立即啟動作業。 在 MBAM Agent 啟動作業之前，會有1到18分鐘的初始隨機延遲時間。 除了初始延遲之外，還會有至少90分鐘的延遲。 （延遲取決於針對檢查用戶端狀態的頻率所設定的群組原則設定。）因此，在用戶端開始作業前的總延遲是*隨機啟動延遲*  +  *用戶端檢查頻率的延遲*。

如果 [操作] 和 [系統管理] 事件記錄是空白的，用戶端還沒有啟動該作業，而且是在前面提到的延遲期間中。 如果您想要略過延遲，請執行下列步驟：
 
1. 停止 BitLocker 管理用戶端服務服務。

2. 在**HKEY_LOCAL_MACHINE \software\microsoft\mbam** registry 子機碼底下，**建立 NoStartupDelay**登錄值，將其類型設定為 [ **REG_DWORD**]，然後將它的值設定為**1**。

3. 在 [ **HKEY_LOCAL_MACHINE \software\policies\microsoft\fve\mdopbitlockermanagement**] 底下，將 [ **ClientWakeupFrequency** ] 和 [ **StatusReportingFrequency** ] 值設定為**1**。 當您在電腦上進行群組原則更新之後，這些值就會還原為原始設定。

4. 啟動 BitLocker 管理用戶端服務服務。

在服務啟動後，如果您在本機電腦上登入，但沒有任何錯誤，您應該會在一分鐘內收到加密電腦的要求。 如果您沒有收到要求，您應該在 MBAM 系統管理記錄中查看任何錯誤專案。

### 電腦沒有 TPM 裝置，或未在 BIOS 中啟用 TPM 裝置

查看 MBAM 系統管理員事件記錄檔。 您會在 MBAM 系統管理員事件記錄中看到類似下列的事件專案：

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          8/3/2013 12:31:10 PM
    Event ID:      9
    Task Category: None
    Level:         Error
    Keywords:      
    User:          SYSTEM
    Computer:      Mbamclient.contoso.com
    Description:
    The TPM hardware is missing.
    TPM is needed to encrypt the operating system drive with any TPM protector.

開啟 [TPM 管理（TPM）]，並檢查電腦是否有 TPM 裝置。 如果您的 devmgmt 沒有顯示裝置，請開啟 [裝置管理器] （），然後檢查 [安全裝置] 底下的 [受信任的平臺] 模組。 如果您沒有看到受信任的平臺模組裝置，這可能是下列其中一個原因所導致：

* 您的系統沒有受信任的平臺模組（TPM/安全性）裝置。

* TPM 裝置在 BIOS 中停用。

* 在 BIOS 中啟用 TPM 裝置，但在 BIOS 中停用了從作業系統設定管理 TPM 裝置。

* 您不是針對 TPM 裝置使用 Microsoft 驅動程式。 查看 [裝置管理器] 中所列的裝置，以找出 Microsoft TPM 裝置驅動程式。

如果 TPM 裝置未使用 C:\Windows\System32\tpm.sys 驅動程式，您應該選取 C:\Windows\Inf\tpm.inf 檔案來更新驅動程式。

### 電腦沒有有效的系統磁碟分割

查看 MBAM 系統管理員事件記錄檔。 您會在 MBAM 系統管理員事件記錄中看到類似下列的事件專案：

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          8/3/2013 4:13:37 AM
    Event ID:      8
    Task Category: None
    Level:         Error
    Keywords:      
    User:          SYSTEM
    Computer:      BITTESTVM.xtremelabs.com
    Description:
    The system volume is missing.
    SystemVolume is needed to encrypt the operating system drive.

BitLocker 需要系統磁碟分割來啟用加密（[在 Windows 7 中使用 BitLocker 磁片磁碟機加密）：常見問題](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-7/ee449438(v=ws.10)?redirectedfrom=MSDN#bkmk_partitions)）。

MBAM 不會自動建立系統磁碟分割。 您可以使用 BitLocker 磁碟機準備實用程式（bdehdcfg.exe）來建立系統磁碟分割並移動所需的啟動檔案。

例如，您可以使用命令 **% windir% \system32\bdeHdCfg.exe 目標預設大小 300-quiet** ，在您部署 MBAM 以進行磁片加密前，預先準備好磁片磁碟機。 這需要重新開機。 您也可以在需要時編寫動作腳本。 下列檔說明 BitLocker 磁碟機準備工具：

[BitLocker 磁片磁碟機準備工具的描述](https://support.microsoft.com/help/933246)

### 磁片磁碟機沒有格式化成具有相容的檔案系統

請參閱[TechNet 文章，瞭解 BitLocker 的檔案系統需求](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-7/ee449438(v=ws.10)?redirectedfrom=MSDN#bkmk_hsrequirements)。

### 群組原則衝突

您會在 MBAM 系統管理員事件記錄中看到類似下列的事件專案：

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          7/25/2013 9:27:58 PM
    Event ID:      22
    Task Category: None
    Level:         Error
    Keywords:      
    User:          SYSTEM
    Computer:      Mbamclient.contoso.com
    Description:
    Detected Fixed Data Drive volume encryption policies conflict.
    Check BitLocker and MBAM policies related to FDD drive protectors.

確認您的群組原則設定，以確認您在 MBAM 群組原則設定之間沒有相衝突的設定。

您應該使用 [MDOP MBAM] 範本而不是 BitLocker 磁片磁碟機加密範本來設定群組原則。

例如：

在 [作業系統磁片磁碟機加密設定] 下，您已選取 [TPM] 作為保護器，而且您也已選取 [**允許增強的 pin 以進行啟動**]。 因為僅 TPM 保護不需要 PIN，所以這些是衝突的設定。 因此，您應該停用 [增強式 Pin] 設定。

### 使用者可能已要求豁免

如果您已啟用電腦配置 \ 管理範本 \Windows Components\MDOP MBAM （BitLocker Management） \Client Management\Configure 使用者豁免原則組原則設定，系統會提供要求例外的選項。

根據預設，如果使用者要求免除，該免除將有效期為7天，而且使用者在此期間將不會收到加密的提示。 （您可以在原則配置期間增加或減少預設值。）在免除期限結束之後，系統會提示使用者進行加密。

當電腦處於 [使用者豁免] 下時，在 MBAM 系統管理員事件記錄中，您會看到下列專案：

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          8/3/2013 3:06:40 PM
    Event ID:      13
    Task Category: None
    Level:         Warning
    Keywords:      
    User:          SYSTEM
    Computer:      MBAMCLIENT.contoso.com
    Description:
    The user is exempt from encryption.

如果您想要手動覆寫電腦的使用者豁免，請遵循下列步驟：
 
1. 在下列登錄子機碼底下，將 AllowUserExemption 值設定為**0** ： <br />
**HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement**

2. 刪除下列登錄子機子 AgentVersion 下的所有登錄值（除了是 [ ** **]、[ **EncodedComputerName**] 及 [**安裝**]）：<br />
**HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\MBAM**

    **記事**您必須重新開機 MBAM 代理程式，變更才會生效。

請注意，在您將群組原則套用到電腦之後，這些值可能會還原為原始設定。

### WMI 問題

MBAM 使用 win32_encryptablevolume 類別的方法來管理 BitLocker。 如果此模組已取消註冊或損毀，MBAM 用戶端將無法正常運作，而且您會在 MBAM 系統管理員事件記錄中看到下列事件專案：

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          7/27/2013 11:18:51 PM
    Event ID:      4
    Task Category: None
    Level:         Error
    Keywords:      
    User:          SYSTEM
    Computer:      BITTEST.xtremelabs.com
    Description:
    An error occurred while sending encryption status data.
    Error code:
    0x80041016 
    Details:
    NULL

此外，您可能會發現 [恢復] 和 [硬體] 原則不適用於錯誤碼0x8007007e。 這會轉換為「找不到指定的模組」。

若要解決此問題，您應該使用下列命令重新註冊**win32_encryptablevolume**類別：

```cmd
mofcomp c:\Windows\System32\wbem\win32_encryptablevolume.mof
```

## MBAM 代理通訊問題的疑難排解

本節包含下列與 MBAM agent 通訊相關之問題的疑難排解資訊：

### 不正確的 MBAM 服務 URL

如果 MBAM 合規性狀態服務或復原及硬體服務的值不正確，您會在用戶端電腦上的 MBAM 系統管理員事件記錄中看到如下所示的事件專案：

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          8/3/2013 4:13:36 PM
    Event ID:      4
    Task Category: None
    Level:         Error
    Keywords:     
    User:          SYSTEM
    Computer:      Mbamclient.contoso.com
    Description:
    An error occurred while sending encryption status data.
    Error code:
    0x803d0010
    Details:
    The remote endpoint was not reachable.

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          8/3/2013 4:13:33 PM
    Event ID:      18
    Task Category: None
    Level:         Error
    Keywords:     
    User:          SYSTEM
    Computer:      Mbamclient.contoso.com
    Description:
    Unable to connect to the MBAM Recovery and Hardware service.
    Error code:
    0x803d0010
    Details:
    The remote endpoint was not reachable.

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          8/3/2013 4:20:32 PM
    Event ID:      4
    Task Category: None
    Level:         Error
    Keywords:     
    User:          SYSTEM
    Computer:      Mbamclient.contoso.com
    Description:
    An error occurred while sending encryption status data.
    Error code:
    0x803d0020
    Details:
    The endpoint address URL is invalid.

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          8/3/2013 4:20:32 PM
    Event ID:      18
    Task Category: None
    Level:         Error
    Keywords:     
    User:          SYSTEM
    Computer:      Mbamclient.contoso.com
    Description:
    Unable to connect to the MBAM Recovery and Hardware service.
    Error code:
    0x803d0020
    Details:
    The endpoint address URL is invalid.

在用戶端電腦上的下列登錄子項下，確認**KeyRecoveryServiceEndPoint**和**StatusReportingServiceEndpoint**的值： <br />
**HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement**

根據預設，KeyRecoveryServiceEndPoint （MBAM 復原與硬體服務端點）的 URL 會採用下列格式： <br />
**HTTP:// \<servername\> ： \<port\> /MBAMRecoveryAndHardwareService/CoreService.svc**

根據預設，StatusReportingServiceEndpoint （MBAM 狀態報表服務端點）的 URL 會採用下列格式：<br />
**HTTP:// \<servername\> ： \<port\> /MBAMComplianceStatusService/StatusReportingService.svc**

> [!Note]
> URL 中不應有空格。

如果服務 URL 不正確，您應該在下列群組原則設定中修正服務 URL：

**電腦配置**  > **原則**  > **管理範本**  > **Windows 元件**  > **MDOP MBAM （BitLocker 管理）**  > **用戶端管理**  > **設定 MBAM 服務**

### 影響 MBAM 管理伺服器的連接問題

如果用戶端代理程式與 MBAM 管理伺服器之間存在連線問題，則 MBAM 代理程式將無法將任何更新發佈至資料庫。 在這種情況下，您會在用戶端電腦上的 MBAM 系統管理員事件記錄中發現連線失敗專案：

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          29-04-2014 18:21:22
    Event ID:      2
    Task Category: None
    Level:         Error
    Keywords:     
    User:          SYSTEM
    Computer:      TESTLABS.CONTOSO.COM
    Description:
    An error occurred while applying MBAM policies.
    Volume ID:\\?\Volume{871c5858-2467-4d0b-8c83-d68af8ce10e5}\ 
    Error code:
    0x803D0010 
    Details:
    The remote endpoint was not reachable.
 
    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          29-04-2014 23:06:48
    Event ID:      2
    Task Category: None
    Level:         Error
    Keywords:     
    User:          SYSTEM
    Computer:      TESTLABS.CONTOSO.COM
    Description:
    An error occurred while applying MBAM policies.
    Volume ID:\\?\Volume{871c5858-2467-4d0b-8c83-d68af8ce10e5}\ 
    Error code:
    0x803D0006 
    Details:
    The operation did not complete within the time allotted.

    Log Name:      Microsoft-Windows-MBAM/Admin
    Source:        Microsoft-Windows-MBAM
    Date:          02-09-2013 02:02:04
    Event ID:      18
    Task Category: None
    Level:         Error
    Keywords:     
    User:          SYSTEM
    Computer:      TESTLABS.CONTOSO.COM
    Description:
    Unable to connect to the MBAM Recovery and Hardware service.
    Error code:
    0x803D0010 
    Details:
    The remote endpoint was not reachable.

基本檢查：

* 透過 [名稱] 和 [IP] ping MBAM 管理伺服器來驗證基本連通性。 檢查您是否可以使用 telnet 或 portqry 連線到 MBAM 管理網站或服務埠。

* 確認 IIS 服務正在 MBAM 管理和監視伺服器上執行，且 MBAM web 服務正在偵聽 MBAM 用戶端電腦上設定的同一個埠（ `netstat –ano | find "portnumber"` ）。

* 確認為 MBAM 網站設定的埠號碼是使用 IIS 管理員（inetmgr）。 確認埠號碼與用戶端正在其上接聽的埠號碼相同。 確認埠號碼不是由其他應用程式所共用。 例如，伺服器上的另一個應用程式不應使用相同的埠。

* 如果有防火牆，請確定該埠已在防火牆或 proxy 伺服器中開啟。

* 如果用戶端與伺服器之間的通訊是安全的，請確定您使用的是有效的 SSL 憑證。

* 驗證要傳送資料以進行插入的 web 伺服器與資料庫伺服器之間的網路連線。 您可以使用 ODBC 資料來源系統管理員，檢查從 web 伺服器到資料庫伺服器的資料庫連線能力。 詳細的 SQL Server 連線疑難排解資訊可在[如何疑難排解連線至 SQL Server 資料庫引擎的問題](https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx)中取得。

#### 疑難排解連接問題

確定用戶端上設定的服務 URL 正確無誤。 從 registry 複製 KeyRecoveryServiceEndPoint （**HKEY_LOCAL_MACHINE \software\policies\microsoft\fve\mdopbitlockermanagement**） URL 的值，然後在 Internet Explorer 中開啟。

同樣地，複製 StatusReportingServiceEndpoint 的 URL 值（**HKEY_LOCAL_MACHINE \software\policies\microsoft\fve\mdopbitlockermanagement**），然後在 Internet Explorer 中開啟它。

> [!Note]
> 如果您無法從用戶端電腦流覽至 URL，您應該測試從用戶端到執行 IIS 之伺服器的基本網路連線性。 請參閱上一節中的1、2、3和4點。

此外，請在 [管理和監控伺服器] 上查看應用程式記錄，以取得任何錯誤。

您可以在用戶端與伺服器之間建立併發網路追蹤，並查看追蹤，以判斷用戶端代理與 MBAM 管理伺服器之間的連線失敗原因。

> [!Note]
> 如果您可以流覽用戶端電腦的服務 Url，並在 MBAM admin 事件記錄中出現連接錯誤專案，這可能是因為管理伺服器與資料庫伺服器之間的連線失敗。

如果您可以成功流覽兩個服務 Url，且用戶端與執行中的伺服器之間有連線，則表示 IIS 正在運作。 不過，在執行 IIS 和資料庫伺服器的伺服器之間，可能會發生通訊問題。

由於網路問題或資料庫連線字串設定不正確，因此 MBAM services 可能無法連線到資料庫伺服器。 在 [管理及監視伺服器] 上查看應用程式記錄。 您可能會看到來源 ASP.NET 2.0.50727.0 中的錯誤專案或警告，類似下列記錄專案：

    Log Name:      Application
    Source:        ASP.NET 2.0.50727.0
    Date:          7/11/2013 6:16:34 PM
    Event ID:      1310
    Task Category: Web Event
    Level:         Warning
    Keywords:      Classic
    User:          N/A
    Computer:      MBAM2-Admin.contoso.com
    Description:
    Event code: 100001
    Event message: SQL error occurred
    Event time: 7/11/2013 6:16:34 PM
    Event time (UTC): 7/11/2013 12:46:34 PM
    Event ID: 6615fb8eb9d54e778b933d5bb7ca91ed
    Event sequence: 2
    Event occurrence: 1
    Event detail code: 0 
    Application information:
        Application domain: /LM/W3SVC/2/ROOT/MBAMAdministrationService-1-130180202570338699
        Trust level: Full
        Application Virtual Path: /MBAMAdministrationService
        Application Path: C:\inetpub\Microsoft BitLocker Management Solution\Administration Service\
        Machine name: MBAM2-ADMIN 
    
    Process information:
        Process ID: 1940
        Process name: w3wp.exe
        Account name: NT AUTHORITY\NETWORK SERVICE 
    
    Exception information:
        Exception type: SqlException
        Exception message: A network-related or instance-specific error occurred while establishing a connection to SQL Server. The server was not found or was not accessible. Verify that the instance name is correct and that SQL Server is configured to allow remote connections. (provider: Named Pipes Provider, error: 40 - Could not open a connection to SQL Server) 
    
    Request information:
        Request URL: 
        Request path: 
        User host address: 
        User: 
        Is authenticated: False
        Authentication Type: 
        Thread account name: NT AUTHORITY\NETWORK SERVICE 
    
    Thread information:
        Thread ID: 7
        Thread account name: NT AUTHORITY\NETWORK SERVICE
        Is impersonating: False
        Stack trace:    at System.Data.SqlClient.SqlInternalConnection.OnError(SqlException exception, Boolean breakConnection)
       at System.Data.SqlClient.TdsParser.ThrowExceptionAndWarning(TdsParserStateObject stateObj)
       at System.Data.SqlClient.TdsParser.Connect(ServerInfo serverInfo, SqlInternalConnectionTds connHandler, Boolean ignoreSniOpenTimeout, Int64 timerExpire, Boolean encrypt, Boolean trustServerCert, Boolean integratedSecurity, SqlConnection owningObject)
       at System.Data.SqlClient.SqlInternalConnectionTds.AttemptOneLogin(ServerInfo serverInfo, String newPassword, Boolean ignoreSniOpenTimeout, Int64 timerExpire, SqlConnection owningObject)
       at System.Data.SqlClient.SqlInternalConnectionTds.LoginNoFailover(String host, String newPassword, Boolean redirectedUserInstance, SqlConnection owningObject, SqlConnectionString connectionOptions, Int64 timerStart)
       at System.Data.SqlClient.SqlInternalConnectionTds.OpenLoginEnlist(SqlConnection owningObject, SqlConnectionString connectionOptions, String newPassword, Boolean redirectedUserInstance)
       at System.Data.SqlClient.SqlInternalConnectionTds..ctor(DbConnectionPoolIdentity identity, SqlConnectionString connectionOptions, Object providerInfo, String newPassword, SqlConnection owningObject, Boolean redirectedUserInstance)
       at System.Data.SqlClient.SqlConnectionFactory.CreateConnection(DbConnectionOptions options, Object poolGroupProviderInfo, DbConnectionPool pool, DbConnection owningConnection)
       at System.Data.ProviderBase.DbConnectionFactory.CreatePooledConnection(DbConnection owningConnection, DbConnectionPool pool, DbConnectionOptions options)
       at System.Data.ProviderBase.DbConnectionPool.CreateObject(DbConnection owningObject)
       at System.Data.ProviderBase.DbConnectionPool.UserCreateRequest(DbConnection owningObject)
       at System.Data.ProviderBase.DbConnectionPool.GetConnection(DbConnection owningObject)
       at System.Data.ProviderBase.DbConnectionFactory.GetConnection(DbConnection owningConnection)
       at System.Data.ProviderBase.DbConnectionClosed.OpenConnection(DbConnection outerConnection, DbConnectionFactory connectionFactory)
       at System.Data.SqlClient.SqlConnection.Open()
       at System.Data.Linq.SqlClient.SqlConnectionManager.UseConnection(IConnectionUser user)
       at System.Data.Linq.SqlClient.SqlProvider.get_IsSqlCe()
       at System.Data.Linq.SqlClient.SqlProvider.InitializeProviderMode()
       at System.Data.Linq.SqlClient.SqlProvider.System.Data.Linq.Provider.IProvider.Execute(Expression query)
       at System.Data.Linq.DataContext.ExecuteMethodCall(Object instance, MethodInfo methodInfo, Object[] parameters)
       at Microsoft.Mbam.Server.ServiceCommon.KeyRecoveryModelDataContext.GetRecoveryKeyIds(String partialRecoveryKeyId, String reason)
       at Microsoft.Mbam.ApplicationSupportService.AdministrationService.GetRecoveryKeyIds(String partialRecoveryKeyId, String reasonCode)
    
    Custom event details:
        Application: MBAMAdministrationService
        Sql Server:
        Database: MBAM Recovery and Hardware
        Database: MBAM Compliance Status
        Sql ErrorCode: 5
        Error Message: A network-related or instance-specific error occurred while establishing a connection to SQL Server. The server was not found or was not accessible. Verify that the instance name is correct and that SQL Server is configured to allow remote connections. (provider: Named Pipes Provider, error: 40 - Could not open a connection to SQL Server)

#### 可能原因

##### 原因1

在安裝管理與監視伺服器元件期間，管理員可能指定了不正確資料庫實例名稱/資料庫名稱。

您可以使用 IIS 管理主控台驗證並修正資料庫連接字串。 若要這樣做，請開啟 IIS 管理員，然後流覽至 Microsoft BitLocker 管理與監視。 針對左側所列的每個服務，請遵循下列步驟來變更資料庫連線字串：

1. 在 [**功能] 視圖**中，按兩下 [**連接字串**]。

2. 在 [**連接字串**] 頁面上，選取您要變更的連接字串。

3. 在 [**動作**] 窗格中，選取 [**編輯**]。

4. 在 [**編輯連接字串**] 對話方塊中，變更您要變更的屬性，然後選取 **[確定]**。

##### 原因2

在防火牆中封鎖 SQL Server 埠。 確認 SQL Server 設定為要監聽的埠號碼，並確定該埠已在系統管理伺服器和資料庫伺服器之間的防火牆中開啟。

##### 原因3

不正確的 SQL server TCP/IP 系結。 在資料庫伺服器上，確認 SQL Server Configuration Manager 中的 SQL TCP/IP 系結。 MBAM 需要啟用 TCP/IP 和具名管道通訊協定才能連線至資料庫。

##### 原因4

NT Authority\Network 服務帳戶或 MBAM 管理伺服器的電腦帳戶不具備連線至 SQL 資料庫所需的許可權。

在資料庫伺服器上安裝資料庫元件期間，安裝程式會建立兩個本機群組： MBAM 合規性審核資料庫存取和 MBAM 復原與硬體資料庫存取。

NT Authority\Network 服務帳戶、MBAM 管理伺服器的電腦帳戶，以及安裝資料庫元件的使用者，都會自動新增到這些群組中。

在安裝期間，系統會將這些群組授與資料庫所需的許可權。 屬於這個群組的所有使用者，都會自動收到資料庫所需的許可權。

由於下列一或多個條件屬實，所以 web 服務可能無法連線到資料庫伺服器：

* 前面提到的群組會從資料庫伺服器上的本機群組中移除。

* NT Authority\Network 服務帳戶和 MBAM 管理伺服器的電腦帳戶不是這些群組的成員。

* 這些群組沒有資料庫所需的許可權。

如果上述任何情況屬實，您會注意到 MBAM 管理和監視伺服器上的應用程式記錄中的許可權相關錯誤。 在這種情況下，您應該手動新增 NT Authority\Network 服務帳戶和 MBAM 管理伺服器的電腦帳戶，並在使用 SQL Server Management Studio （.）的 SQL 資料庫伺服器上，授與伺服器範圍的公用角色 https://msdn.microsoft.com/library/aa337562.aspx) 。

#### 查看 web 服務記錄

如果 MBAM 管理伺服器上的應用程式記錄中沒有記錄任何事件，現在就可以查看 MBAM 管理和監視伺服器上所託管之 MBAM web 服務的 web 服務記錄（svclog）。 您必須使用服務追蹤檢視器工具（SvcTraceViewer.exe） https://msdn.microsoft.com/library/ms732023.aspx 來查看記錄檔。

您應該主要調查 RecoveryandHardwareService 和 ComplianceStatusService 的服務追蹤記錄。 根據預設，web 服務記錄位於 [C:\inetpub\Microsoft BitLocker 管理 Solution\Logs] 資料夾中。 在這裡，每個服務都會在自己的資料夾下寫入其 svclog 檔案。

在服務追蹤記錄中，查看任何錯誤或警告專案的活動。 根據預設，錯誤專案會以紅色醒目提示。 選取 [追蹤檢視器] 右窗格中的 [錯誤描述]，以查看錯誤專案的詳細資訊。 以下是追蹤記錄中的範例錯誤專案：

    <E2ETraceEvent xmlns="http://schemas.microsoft.com/2004/06/E2ETraceEvent">
    <System xmlns="http://schemas.microsoft.com/2004/06/windows/eventlog/system">
    <EventID>15183</EventID>
    <Type>3</Type>
    <SubType Name="Error">0</SubType>
    <Level>2</Level>
    <TimeCreated SystemTime="2013-07-05T14:48:06.2821550Z" />
    <Source Name="Microsoft.Mbam.CoreService" />
    <Correlation ActivityID="{00000000-0000-0000-0000-000000000000}" />
    <Execution ProcessName="w3wp" ProcessID="4332" ThreadID="11" />
    <Channel />
    <Computer>XXXXXXXXXXX</Computer>
    </System>
    <ApplicationData>AddUpdateVolume: While executing sql transaction for add volume to store exception occurred Key Recovery Data Store processing error: Violation of UNIQUE KEY constraint 'UniqueRecoveryKeyId'. Cannot insert duplicate key in object 'RecoveryAndHardwareCore.Keys'. The duplicate key value is (8637036e-b379-4798-bd9e-5a0b36296de3).
    </ApplicationData>
    </E2ETraceEvent>

## 重新安裝或重新配置 MBAM 基礎結構

若要重新安裝或重新設定 MBAM 基礎結構，您必須知道下列事項：

* 應用程式池帳戶

* MBAM 群組（[技術支援]、[高級]、[報表使用者] 群組）

* MBAM 報表 URL

* SQL Server 名稱與資料庫名稱

* MBAM ReadWrite 與 ReadOnly 帳戶

### 應用程式池帳戶

若要尋找應用程式池帳戶，請登入 MBAM Web 服務器、開啟 [**網際網路資訊服務（IIS）管理員**]，然後選取 [**應用程式池**]：

![應用程式池](images/troubleshooting-MBAM-installation-1.png)

服務主體名稱（SPN）必須在這個帳戶中設定。 這個設定對 MBAM 的功能非常重要。

### MBAM 群組（[技術支援]、[高級]、[報表使用者] 群組和報表 URL）

![MBAM 群組](images/troubleshooting-MBAM-installation-2.png)

這會提供 [服務台] 群組、[高級支援人員] 群組、[報告使用者] 群組，以及 MBAM 報表 URL 等相關資訊。 MBAM 報表 URL 必須在 [MBAM 設定] 中提供，且應閱讀為： HTTP （s）：//servername/ReportServer。

### SQL Server 名稱和資料庫（DB）名稱

若要尋找託管 MBAM 的 SQL Server 名稱和實例，請登入 MBAM Web （IIS）伺服器，然後流覽至 folowing 登錄子機碼：

**HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\MBAM Server\Web**

![註冊表](images/troubleshooting-MBAM-installation-3.png)

醒目提示的部分是連接字串。 這些應該有 SQL Server 名稱、資料庫名稱和實例（如果已命名的話）。

### MBAM ReadWrite 與 ReadOnly 帳戶

這項資訊將會在 SQL Server 資料庫中，我們已找到來自網頁伺服器的名稱。

#### ReadWrite 帳戶

1. 登入 SQL Management Studio。

2. 以滑鼠右鍵按一下 [ **MBAM 復原及硬體**]，選取 [**屬性**]，然後選取 [**許可權**]。

例如，lab 帳戶名稱是**MBAMWrite**。 應用程式池和 ReadWrite 帳戶已設定為相同。

![SQL 資料庫](images/troubleshooting-MBAM-installation-4.png)

![DB 屬性](images/troubleshooting-MBAM-installation-5.png)

流覽至 [**安全性**]，然後流覽至 SQL Management Studio 中的 [**登錄**]。 流覽至上一個螢幕擷取畫面中顯示的帳戶。

![SQL 安全性](images/troubleshooting-MBAM-installation-6.png)

以滑鼠右鍵按一下帳戶，移至 [**屬性使用者對應**]，然後找出 MBAM 復原與硬體資料庫：

![使用者對應](images/troubleshooting-MBAM-installation-7.png)

#### 唯讀帳戶

在 SSRS 伺服器上開啟 [SQL Server Reporting Services Configuration Manager]。 選取 [**報表管理員 URL**]，然後流覽**url**：

![報表管理員](images/troubleshooting-MBAM-installation-8.png)

選取 [ **Microsoft Bitlocker 管理及監視**]：

![Bitlocker 管理和監視](images/troubleshooting-MBAM-installation-9.png)

選取 [ **MaltaDatasource**]：

![[](images/troubleshooting-MBAM-installation-10.png)

![MaltaDatasource](images/troubleshooting-MBAM-installation-11.png)

MaltaDataSource 應該具有唯讀帳戶名稱，且應該用於 MBAM 設定。

## 參考

如需詳細資訊，請參閱下列文章：

[在獨立配置中部署 MBAM 2。5](https://support.microsoft.com/help/3046555)

[Microsoft BitLocker Administration and Monitoring 2.5](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/)
