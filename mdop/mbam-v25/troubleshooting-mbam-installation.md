---
title: MBAM 2.5 安裝問題疑難排解
description: 如何疑難排解 2.5 安裝問題。
author: Deland-Han
ms.reviewer: dcscontentpm
manager: dansimp
ms.author: delhan
ms.sitesec: library
ms.prod: w10
ms.date: 09/16/2019
ms.openlocfilehash: 6ea152792801c630fa365f37d1668d1a4d84b3a5
ms.sourcegitcommit: 3e0500abde44d6a09c7ac8e3caf5e25929b490a4
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/23/2021
ms.locfileid: "11910628"
---
# <a name="troubleshooting-mbam-25-installation-problems"></a>MBAM 2.5 安裝問題疑難排解

本文將介紹如何在獨立組 (中疑難排解 Microsoft BitLocker 系統管理 (監控) 2.5 安裝問題。

## <a name="referring-mbam-log-files-for-troubleshooting"></a>參照用於疑難排解的一些 MM 記錄檔案

IBMM 包含伺服器安裝、用戶端安裝和事件的記錄。 此記錄應參考以進行疑難排解。 
 
### <a name="mbam-server-installation-log-files"></a>IBMM 伺服器安裝記錄檔案

MBAMServerSetup.exe在安裝期間，在使用者的 %temp% 資料夾中產生下列記錄檔案：<br /> **Microsoft_BitLocker_Administration_and_Monitoring_<14 個數字>記錄**

MBAMServerSetup.exe記錄在<a0></a0>的<a1> </a1> <a2>：</a2><a3></a3><a4></a4><a5></a5><A5<br /> **Microsoft_BitLocker_Administration_and_Monitoring_<14_numbers>_0_MBAMServer.msi.log**

MBAMServerSetup.exe記錄安裝期間執行的其他動作。

### <a name="mbam-client-installation-log-file"></a>管理與管理管理用戶端安裝記錄檔案

用戶端安裝會記錄在 %temp% 資料夾的下列記錄 (或自訂位置中，視用戶端的安裝方式) ： <br />**MSI \<five random characters\> .log**

此記錄包含在安裝期間執行的動作。
 
### <a name="mbam-client-event-logging-channel"></a>資料記錄通道

該 MM 有個別的事件記錄通道。 系統管理、分析及營運記錄檔案位於事件檢視器中，位於應用程式和服務記錄**** Microsoft Windows  >  ****  >  ****  >  **中**。

下表提供每個事件記錄簡介。
 
|事件記錄檔| 描述|
|----------|-------|
|Microsoft-Windows-MICROSOFT-WINDOWS M/Admin|  包含錯誤訊息|
|Microsoft-Windows-WINDOWS/Analytic|   包含進位記錄資訊|
|Microsoft-Windows-MICROSOFT-WINDOWS/營運|    包含成功訊息|

### <a name="mbam-server-event-logging-channel"></a>IBMM 伺服器事件記錄通道

記錄檔案位於事件檢視器中，位於應用程式與**服務記錄**Microsoft Windows  >  ****  >  ****  >  **中**。 下表包含在 IBMM 2.5 中引入的伺服器事件記錄：

|事件記錄檔| 描述|
|--------|-------------|
|Microsoft-Windows-MICROSOFT-WINDOWS M/Admin|  包含錯誤訊息|
|Microsoft-Windows-WINDOWS/Analytic|   包含進位記錄資訊|
|Microsoft-Windows-MICROSOFT-WINDOWS/營運|    包含成功訊息|

### <a name="mbam-web-service-logs"></a>2010 年 12 月 15 日

每個的 WEB 服務記錄記錄會將記錄資訊寫入 SVCLOG 檔案。 根據預設，每個 Web 服務在 C：\inetpub\Microsoft BitLocker Management Solution\Logs 資料夾中使用其名稱的資料夾下寫入追蹤檔案。

您可以使用服務追蹤檢視器工具 (部分Microsoft Visual Studio) svclog 追蹤。

## <a name="troubleshooting-encryption-and-reporting-issues"></a>加密與報告問題的疑難排解

本節包含伺服器功能、用戶端功能、設定設定和已知問題的疑難排解資訊：
 
### <a name="mbam-client-installation-group-policy-settings"></a>管理管理管理程式用戶端安裝、群組原則設定

判斷是否已在用戶端電腦上安裝該管理管理代理程式。 安裝之後，它會建立名為 BitLocker 管理用戶端服務的服務。 此服務已配置為自動啟動。 判斷服務是否進行中。

請確定在用戶端電腦上已應用了 B0 電腦管理區策略設定 。 如果用戶端電腦上已使用群組原則設定，會建立下列註冊表子機HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement****

請確認此金鑰是否存在，並且會使用每個群組原則設定的值來填上。

### <a name="mbam-agent-in-the-initial-delay-period"></a>初始延遲期間中的一個服務代理程式

安裝之後，即無法立即啟動作業。 初始隨機延遲為 1 到 18 分鐘，然後才開始其作業。 除了初始延遲之外，還有至少 90 分鐘的延遲。  (延遲取決於針對檢查用戶端狀態的頻率所設定之群組原則設定。) 因此，用戶端啟動作業前的總延遲是隨機啟動延遲用戶端檢查**  +  *頻率*延遲。

如果營運和系統管理事件記錄為空白，則用戶端尚未開始作業，且目前為先前提及的延遲期間。 如果您想要忽略延遲，請遵循下列步驟：
 
1. 停止 BitLocker 管理用戶端服務。

2. 在**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MBAM註冊表**子機值下，建立**NoStartupDelay**註冊表值，將類型設為 REG_DWORD **，然後將**其值設為**1。**

3. 在**HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement**中，將**ClientWakeupFrequency**和**StatusReportingFrequency**值設為**1。** 當群組原則更新位於電腦上之後，這些值會還原為原始設定。

4. 啟動 BitLocker 管理用戶端服務。

服務啟動之後，如果您在電腦本地登入且沒有錯誤，您應該在一分鐘內收到加密電腦的要求。 如果您未收到要求，您應該檢查 <管理及管理記錄管理中是否有任何錯誤專案。

### <a name="computer-does-not-have-a-tpm-device-or-the-tpm-device-is-not-enabled-in-the-bios"></a>電腦沒有 TPM 裝置，或在BIOS 中未啟用 TPM 裝置

請閱閱該名管理管理員事件記錄。 在 INM 系統管理事件記錄中，您會看到類似下列的事件專案：

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

開啟 TPM 管理 (tpm.msc) ，然後檢查電腦是否有 TPM 裝置。 如果 tpm.msc 未顯示裝置，請開啟 Device Manager (devmgmt.msc) ，並檢查安全性裝置下的信任平臺模組。 如果您沒看到信任的平臺模組裝置，這可能是因為下列其中一個原因：

* 您的系統沒有信任的平臺模組 (TPM/Security) 裝置。

* 在BIOS 中，TPM 裝置已停用。

* TPM 裝置在BIOS 中已啟用，但從作業系統設定管理 TPM 裝置在BIOS 中會停用。

* 您不是在 TPM 裝置上使用 Microsoft 驅動程式。 查看裝置管理器中列出的裝置，以識別 Microsoft TPM 裝置驅動程式。

如果 TPM 裝置並未使用 C:\Windows\System32\tpm.sys 驅動程式，您應該選取 C：\Windows\Inf\tpm.inf 檔案來更新驅動程式。

### <a name="computer-does-not-have-a-valid-system-partition"></a>電腦沒有有效的 SYSTEM 分區

請閱閱該名管理管理員事件記錄。 在 INM 系統管理事件記錄中，您會看到類似下列的事件專案：

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

BitLocker 需要 SYSTEM 分區才能在 (7 中啟用[bitLocker](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-7/ee449438(v=ws.10)?redirectedfrom=MSDN#bkmk_partitions)磁片磁碟機加密Windows：常見問題) 。

但是，系統磁碟分割不會自動建立。 您可以使用 BitLocker 磁片磁碟機準備公用程式 (bdehdcfg.exe) 建立系統磁碟分割並移動所需的啟動檔案。

例如，您可以使用命令 **%windir%\system32\bdeHdCfg.exe -target 預設 -size 300 -quiet，** 在部署要加密磁片磁碟機的部署時，先以無提示方式準備磁片磁碟機。 這需要重新開機。 如果需要，您也可以為動作編寫腳本。 下列檔說明 BitLocker 硬碟準備工具：

[BitLocker 硬碟準備工具的描述](https://support.microsoft.com/help/933246)

### <a name="drives-are-not-formatted-to-have-a-compatible-file-system"></a>磁片磁碟機未格式化為具有相容的檔案系統

請參閱 [TechNet 文章，瞭解 BitLocker 的檔案系統需求](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-7/ee449438(v=ws.10)?redirectedfrom=MSDN#bkmk_hsrequirements)。

### <a name="group-policy-conflict"></a>群組原則衝突

在 INM 系統管理事件記錄中，您會看到類似下列的事件專案：

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

驗證您的群組原則設定，以確保您沒有在的群組原則設定之間設定衝突。

您應該使用 MDOP 的 MDOP BM 範本來設定群組原則，而不是 BitLocker 磁片磁碟機加密範本。

例如：

在作業系統磁片磁碟機加密設定下，您選取 TPM 做為保護程式，而且您也選取了允許 **增強型 PIN 啟動**。 這些設定相互衝突，因為 TPM 僅保護不需要 PIN。 因此，您應該停用增強的 PIN 設定。

### <a name="user-may-have-requested-an-exemption"></a>使用者可能要求免稅

如果您啟用電腦群組設定\系統管理範本\Windows Components\MDOP 慢化管理 (BitLocker 管理) \Client Management\Configure User exemption policy Group Policy 設定，系統就會提供使用者要求免稅的選項。

根據預設，如果使用者要求免稅，免稅的有效期為 7 天，且使用者不會在此期間收到加密的提示。  (在策略組定期間，預設值可能會增加或減少。) 免稅期間結束後，系統會提示使用者加密。

當電腦在使用者免稅時，您將在 INM 系統管理事件記錄中看到下列專案：

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

如果您想要手動取代電腦的使用者免稅，請遵循下列步驟：
 
1. 將 AllowUserExemption 值設定為 **0** 在下列註冊表子機下： <br />
**HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement**

2. 刪除下列註冊表子機下的所有註冊表值，但**AgentVersion、EncodedComputerName**和**已安裝除外**： ****<br />
**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MBAM**

    **附注** 您必須重新開機該資料代理程式，變更才能生效。

請注意，將群組原則適用于電腦後，這些值可能會還原為原始設定。

### <a name="wmi-issue"></a>WMI 問題

在管理 BitLocker 時，WIN32_ENCRYPTABLEVOLUME採用不同類別的方法。 如果此模組未註冊或已損壞，則的  ：：

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

此外，您可能會注意到，修復和硬體原則不適用於錯誤碼0x8007007e。 這表示「找不到指定的模組」。

若要解決此問題，您應該使用下列命令重新註冊 win32_encryptablevolume**類：**

```cmd
mofcomp c:\Windows\System32\wbem\win32_encryptablevolume.mof
```

## <a name="troubleshooting-mbam-agent-communication-issues"></a>疑難排解的 MM Agent 通訊問題

此區段包含下列與 "服務人員通訊" 相關問題的疑難排解資訊：

### <a name="incorrect-mbam-service-url"></a>不正確的服務 URL

如果 INSM 合規性狀態服務或修復與硬體服務的值不正確，您就會在用戶端電腦上的 <管理管理事件記錄中，看到類似下列的事件專案：

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

在用戶端電腦上的下列註冊表子機名下，驗證 **KeyRecoveryServiceEndPoint** 和 **StatusReportingServiceEndpoint** 的值： <br />
**HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement**

根據預設，KEYRecoveryServiceEndPoint (與硬體服務端點的 URL) 格式為： <br />
**HTTP:// ： \<servername\> \<port\> /A0 /1993-2013-2013-2013-2013-2013-2013-2013-2013-2**

根據預設，STATUSReportingServiceEndpoint (的 URL) 為下列格式：<br />
**HTTP:// \<servername\> ： \<port\> /A0 /A0 /2012/2013/1994/433-433-2013-2013-2013-2013-2**

> [!Note]
> URL 中不應有空格。

如果服務 URL 不正確，您應該在下列群組原則設定中修正服務 URL：

**電腦群組組**  > **政策**  > **系統管理範本**  > **Windows元件**  > **MDOP MDM (BitLocker Management) **  > **用戶端管理**  > **設定 MM Services**

### <a name="connectivity-issue-that-affects-the-mbam-administration-server"></a>影響 IBMM 系統管理伺服器的連接問題

如果用戶端代理程式與 IBMM 系統管理伺服器之間存在連接問題，則 IBMM 代理程式將無法將任何更新張貼至資料庫。 在此案例中，您將注意到用戶端電腦上 ，INM 系統管理事件記錄中的連接失敗專案：

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

* 根據名稱和 IP ping AM 系統管理伺服器，驗證基本連接。 檢查您是否可以使用 telnet 或 portqry 來連結至的管理網站或服務埠。

* 請確認 IIS 服務在 IBMM 系統管理與監控伺服器上執行，且該網管服務正在與在 () 上所配置的相同埠 `netstat –ano | find "portnumber"` 進行聆聽。

* 請確認為   網站所配置的埠號碼是使用 IIS Manager (inetmgr) 。 請確定埠號碼與用戶端正在聆聽的埠號碼相同。 請確定另一個應用程式未共用埠號碼。 例如，伺服器上另一個應用程式不應使用相同的埠。

* 如果有防火牆，請確定埠在防火牆或 Proxy 伺服器中已開啟。

* 如果用戶端與伺服器之間的通訊是安全的，請確定您使用的是有效的 SSL 憑證。

* 確認 Web 服務器與資料要插入之資料庫伺服器之間的網路連接。 您可以使用 ODBC 資料來源系統管理員，檢查從 Web 服務器到資料庫伺服器的資料庫連接。 有關SQL Server疑難排解的詳細資訊，請參閱如何疑難排解連接[至SQL Server 資料庫引擎。](https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx)

#### <a name="troubleshooting-the-connectivity-issue"></a>針對連接問題進行疑難排解

確認用戶端上所配置的服務 URL 正確無誤。 從註冊表複製 KeyRecoveryServiceEndPoint ** (HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement) ** URL 值，然後于 Internet Explorer 中開啟。

同樣地，複製 StatusReportingServiceEndpoint 的 URL 值 ** (HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement) ， ** 然後于 Internet Explorer 中開啟。

> [!Note]
> 如果您無法從用戶端電腦流覽到 URL，您應該測試從用戶端到執行 IIS 的伺服器的基本網路連接。 請參閱上一節中的點 1、2、3 和 4。

此外，檢閱系統管理與監控伺服器上應用程式記錄的任何錯誤。

您可以在用戶端與伺服器之間進行並行網路追蹤，並檢閱追蹤，判斷用戶端代理程式與 IBMM 系統管理伺服器之間連接失敗的原因。

> [!Note]
> 如果您從用戶端電腦流覽到服務 URL，而且在 IBMM 系統管理事件記錄中出現連接錯誤專案，這可能是因為系統管理伺服器與資料庫伺服器之間的連接失敗。

如果您能夠成功流覽到這兩個服務 URL，而且用戶端與執行中的伺服器之間有連接，IIS 就可以運作。 不過，執行 IIS 的伺服器與資料庫伺服器之間的通訊可能有問題。

由於網路問題或不正確的資料庫連接字串設定，因此，IBMM 服務可能無法連接到資料庫伺服器。 檢閱系統管理與監控伺服器上的應用程式記錄。 您可能會在 2.0.50727.0 ASP.NET 2.0.50727.0 中看到類似下列記錄專案的錯誤專案或警告：

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

#### <a name="possible-causes"></a>可能的原因

##### <a name="cause-1"></a>原因 1

系統管理員在安裝系統管理及監控伺服器元件期間，可能指定不正確資料庫實例名稱/資料庫名稱。

您可以使用 IIS 管理主控台驗證及修正資料庫連接字串。 若要這麼做，請開啟 IIS Manager，然後流覽至 Microsoft BitLocker 系統管理與監控。 針對左側所列的每個服務，請遵循下列步驟來變更資料庫連接字串：

1. 在 **功能視圖**中，按兩下 **連接字串**。

2. 在連接 **字串** 頁面上，選取您想要變更的連接字串。

3. 在動作**窗格中****，選取**編輯 。

4. 在 [ **編輯連接字串** 」 對話方塊中，變更您想要變更的屬性，然後選取 [ **確定**。

##### <a name="cause-2"></a>原因 2

SQL Server防火牆中封鎖的埠。 確認已SQL Server要聆聽的埠號碼，並確認系統管理伺服器與資料庫伺服器之間的防火牆中已開啟該埠。

##### <a name="cause-3"></a>原因 3

不正確的SQL TCP/IP 綁定。 在SQL伺服器中SQL Server 組態管理員 TCP/IP 綁定。 TCP/IP 和命名的管道通訊協定必須啟用，以連接到資料庫。

##### <a name="cause-4"></a>原因 4

NT Authority\Network Service 帳戶或 NTM 系統管理伺服器的電腦帳戶沒有連接到資料庫SQL許可權。

在資料庫伺服器上安裝資料庫元件期間，安裝程式會建立兩個本地群組：一組是：IBMM 合規性稽核 DB Access 和 IBMM 修復與硬體 DB Access。

NT Authority\Network Service 帳戶、IBMM 系統管理伺服器的電腦帳戶，以及安裝資料庫元件的使用者，都會自動新增到這些群組中。

這些群組在安裝期間會獲得資料庫上所需的許可權。 屬於此群組的所有使用者會自動收到資料庫上所需的許可權。

如果下列一或多個條件為 True，Web 服務可能無法連接到資料庫伺服器，因為許可權問題：

* 先前提及的群組會從資料庫伺服器上的本地群組中移除。

* NT Authority\Network Service 帳戶和 IBMM 系統管理伺服器的電腦帳戶不是這些群組的成員。

* 這些群組沒有資料庫所需的許可權。

如果有任何先前的條件為 True，您就會注意到在 IBMM 系統管理與監控伺服器上應用程式記錄中與許可權相關的錯誤。 在這種情況下，您應該手動新增 NT Authority\Network Service 帳戶和 IBMM 系統管理伺服器的電腦帳戶，並授予他們在 SQL 資料庫伺服器上使用 SQL Server Management Studio (的全伺服器公用角色 https://msdn.microsoft.com/library/aa337562.aspx) 。

#### <a name="review-the-web-service-logs"></a>檢查 Web 服務記錄

如果 IBMM 系統管理伺服器上沒有記錄應用程式記錄中的事件，現在該是檢閱託管于 IBMM 系統管理與監控伺服器的網服務記錄 (.svclog) 的時間。 您必須使用服務追蹤檢視器工具 (SvcTraceViewer.exe) https://msdn.microsoft.com/library/ms732023.aspx 檢視記錄檔案。

您應該主要調查 Recovery andWarewareService 和 ComplianceStatusService 的服務追蹤記錄。 根據預設，Web 服務記錄會位於 C：\inetpub\Microsoft BitLocker Management Solution\Logs 資料夾中。 在那裡，每個服務會在其自己的資料夾下寫入其 .svclog 檔案。

檢查服務追蹤記錄中的活動是否有錯誤或警告專案。 根據預設，錯誤專案會以紅色顯示。 選取追蹤檢視器右窗格中的錯誤描述，以檢視錯誤專案的詳細資訊。 以下是追蹤記錄中的範例錯誤專案：

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

## <a name="re-installation-or-reconfiguration-of-mbam-infrastructure"></a>重新安裝或重新組建的

若要重新安裝或重新重設<a0></a0>的<a1> </a1> <a2>：</a2><a3></a3><a4></a4><a5

* 應用程式庫帳戶

* 支援人員、 (、進位、報表使用者群組群組) 

* 2010 年 12 月 15 日

* SQL Server名稱和資料庫名稱

* 然後，請用同一個資料來閱讀

### <a name="application-pool-account"></a>應用程式庫帳戶

若要尋找應用程式庫帳戶，請登入的 IBMM Web Server，Internet Information Services (**IIS) Manager，** 然後選取應用程式**庫**：

![應用程式庫。](images/troubleshooting-MBAM-installation-1.png)

必須在此帳戶中 (SPN) 服務主體名稱。 此設定對於<a0></a0>的<a1> </a1> <a2>，對於</a2> <a3></a3

### <a name="mbam-groups-helpdesk-advanced-report-users-group-and-reports-url"></a>由 (支援人員、進 (、報表使用者群組和報表 URL 連結所組成) 

![2010 年 12 月 15 日](images/troubleshooting-MBAM-installation-2.png)

這提供如 Helpdesk 群組、進位服務台群組、報表使用者群組和 <B0 即為<a0></a0> URL 等資訊。 您必須在 HTTPM 設定中提供 HTTPM 報告 URL，並且應該會讀取為：HTTP () ：//servername/ReportServer。

### <a name="sql-server-name-and-database-db-names"></a>SQL Server資料庫名稱 (資料庫) 名稱

若要尋找託管SQL SERVER MDB 的功能變數名稱和實例，請登入 ：IBMM Web (IIS) 伺服器，然後流覽至登錄子機機：

**HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MBAM Server\Web**

![Regedit。](images/troubleshooting-MBAM-installation-3.png)

強調的部分為連接字串。 這些名稱、資料庫SQL Server名稱，以及實例 (名稱) 。

### <a name="mbam-readwrite-and-readonly-accounts"></a>然後，請用同一個資料來閱讀和閱讀

這項資訊會位於SQL Server資料庫中，我們已從 Web 服務器找到名稱。

#### <a name="readwrite-account"></a>ReadWrite 帳戶

1. 登入SQL Management Studio。

2. 以滑鼠右鍵 **按一下 [管理與修復及硬體**>，選取 **[內容**，然後選取 **許可權**> 。

例如，實驗室帳戶名稱為 **：。。** 應用程式庫和 ReadWrite 帳戶設定為相同。

![SQLDB。](images/troubleshooting-MBAM-installation-4.png)

![DB 屬性。](images/troubleshooting-MBAM-installation-5.png)

流覽至**安全性****，然後在**SQL Management Studio。 流覽至上一個螢幕擷取畫面中顯示的帳戶。

![SQL安全。](images/troubleshooting-MBAM-installation-6.png)

以滑鼠右鍵按一下帳戶，然後前往 **[屬性使用者映射**，並找出 [管理及修復及硬體資料庫：

![使用者映射。](images/troubleshooting-MBAM-installation-7.png)

#### <a name="readonly-account"></a>ReadOnly 帳戶

開啟SQL Server Reporting Services SSRS Server 上的組組管理員。 選取**報表管理員 URL，** 然後流覽**URL：**

![報表管理員。](images/troubleshooting-MBAM-installation-8.png)

選取 **Microsoft Bitlocker 系統管理與監控**：

![Bitlocker 系統管理與監控。](images/troubleshooting-MBAM-installation-9.png)

選取 **MaltaDatasource**：

![Dbs。](images/troubleshooting-MBAM-installation-10.png)

![MaltaDatasource。](images/troubleshooting-MBAM-installation-11.png)

MaltaDataSource 應具有 ReadOnly 帳戶名稱，且應該用於的  。

## <a name="reference"></a>參考

如需詳細資訊，請參閱下列文章：

[在獨立配置中部署 OFFICEM 2.5](https://support.microsoft.com/help/3046555)

[Microsoft BitLocker Administration and Monitoring 2.5](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/)
