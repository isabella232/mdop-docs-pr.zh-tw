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
# <span data-ttu-id="b2853-103">MBAM 2.5 安裝問題疑難排解</span><span class="sxs-lookup"><span data-stu-id="b2853-103">Troubleshooting MBAM 2.5 installation problems</span></span>

<span data-ttu-id="b2853-104">本文將說明如何在獨立設定中針對 Microsoft BitLocker 管理和監控（MBAM）2.5 安裝問題進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="b2853-104">This article introduces how to troubleshoot Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 installation issues in a standalone configuration.</span></span>

## <span data-ttu-id="b2853-105">參照 MBAM 記錄檔以進行疑難排解</span><span class="sxs-lookup"><span data-stu-id="b2853-105">Referring MBAM log files for troubleshooting</span></span>

<span data-ttu-id="b2853-106">MBAM 包括伺服器安裝、用戶端安裝和事件的記錄。</span><span class="sxs-lookup"><span data-stu-id="b2853-106">MBAM includes logging for server installation, client installation, and events.</span></span> <span data-ttu-id="b2853-107">應參閱此記錄以進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="b2853-107">This logging should be referred to for troubleshooting.</span></span> 
 
### <span data-ttu-id="b2853-108">MBAM server 安裝記錄檔</span><span class="sxs-lookup"><span data-stu-id="b2853-108">MBAM server installation log files</span></span>

<span data-ttu-id="b2853-109">在 MBAM 安裝期間，MBAMServerSetup.exe 會在使用者的% temp% 資料夾中產生下列記錄檔：</span><span class="sxs-lookup"><span data-stu-id="b2853-109">MBAMServerSetup.exe generates the following log files in the user’s %temp% folder during MBAM installation:</span></span><br /> **<span data-ttu-id="b2853-110">Microsoft_BitLocker_Administration_and_Monitoring_<14 個數字> .log</span><span class="sxs-lookup"><span data-stu-id="b2853-110">Microsoft_BitLocker_Administration_and_Monitoring_<14 numbers>.log</span></span>**

<span data-ttu-id="b2853-111">MBAMServerSetup.exe 記錄在 MBAM 設定和 MBAM 伺服器功能安裝期間所採取的動作：</span><span class="sxs-lookup"><span data-stu-id="b2853-111">MBAMServerSetup.exe logs the actions that were taken during MBAM setup and MBAM server feature installation:</span></span><br /> **<span data-ttu-id="b2853-112">Microsoft_BitLocker_Administration_and_Monitoring_<14_numbers # C1_0_MBAMServer.msi .log</span><span class="sxs-lookup"><span data-stu-id="b2853-112">Microsoft_BitLocker_Administration_and_Monitoring_<14_numbers>_0_MBAMServer.msi.log</span></span>**

<span data-ttu-id="b2853-113">MBAMServerSetup.exe 記錄安裝期間所採取的其他動作。</span><span class="sxs-lookup"><span data-stu-id="b2853-113">MBAMServerSetup.exe logs additional actions that were taken during installation.</span></span>

### <span data-ttu-id="b2853-114">MBAM 用戶端安裝記錄檔</span><span class="sxs-lookup"><span data-stu-id="b2853-114">MBAM client installation log file</span></span>

<span data-ttu-id="b2853-115">用戶端安裝會記錄在% temp% 資料夾中的下列記錄檔（或自訂位置，視用戶端的安裝方式而定）：</span><span class="sxs-lookup"><span data-stu-id="b2853-115">The client installation is recorded in the following log file in the %temp% folder (or a custom location, depending on how the client was installed):</span></span> <br />**<span data-ttu-id="b2853-116">MSI \<five random characters\> .log</span><span class="sxs-lookup"><span data-stu-id="b2853-116">MSI\<five random characters\>.log</span></span>**

<span data-ttu-id="b2853-117">此記錄包含在 MBAM 用戶端安裝期間所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="b2853-117">This log contains the actions that are taken during MBAM client installation.</span></span>
 
### <span data-ttu-id="b2853-118">MBAM 用戶端事件-記錄通道</span><span class="sxs-lookup"><span data-stu-id="b2853-118">MBAM client event-logging channel</span></span>

<span data-ttu-id="b2853-119">MBAM 有個別的事件記錄通道。</span><span class="sxs-lookup"><span data-stu-id="b2853-119">MBAM has separate event-logging channels.</span></span> <span data-ttu-id="b2853-120">系統會在事件檢視器的 [**應用程式和服務記錄**  >  **Microsoft**  >  **Windows**  >  **MBAM**] 底下找到 [管理員]、[分析] 和 [操作] 記錄檔。</span><span class="sxs-lookup"><span data-stu-id="b2853-120">The Admin, Analytical, and Operational log files are located in Event Viewer, under **Application and Services Logs** > **Microsoft** > **Windows** > **MBAM**.</span></span>

<span data-ttu-id="b2853-121">下表提供每個事件記錄記錄的簡短描述。</span><span class="sxs-lookup"><span data-stu-id="b2853-121">The following table provides a brief description of each event log.</span></span>
 
|<span data-ttu-id="b2853-122">事件記錄檔</span><span class="sxs-lookup"><span data-stu-id="b2853-122">Event log</span></span>| <span data-ttu-id="b2853-123">說明</span><span class="sxs-lookup"><span data-stu-id="b2853-123">Description</span></span>|
|----------|-------|
|<span data-ttu-id="b2853-124">Microsoft-Windows-MBAM/系統管理員</span><span class="sxs-lookup"><span data-stu-id="b2853-124">Microsoft-Windows-MBAM/Admin</span></span>|  <span data-ttu-id="b2853-125">包含錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="b2853-125">Contains error messages</span></span>|
|<span data-ttu-id="b2853-126">Microsoft-Windows-MBAM/分析</span><span class="sxs-lookup"><span data-stu-id="b2853-126">Microsoft-Windows-MBAM/Analytic</span></span>|   <span data-ttu-id="b2853-127">包含高級記錄資訊</span><span class="sxs-lookup"><span data-stu-id="b2853-127">Contains advanced logging information</span></span>|
|<span data-ttu-id="b2853-128">Microsoft-Windows-MBAM/運作</span><span class="sxs-lookup"><span data-stu-id="b2853-128">Microsoft-Windows-MBAM/Operational</span></span>|    <span data-ttu-id="b2853-129">包含成功訊息</span><span class="sxs-lookup"><span data-stu-id="b2853-129">Contains success messages</span></span>|

### <span data-ttu-id="b2853-130">MBAM 伺服器事件-記錄通道</span><span class="sxs-lookup"><span data-stu-id="b2853-130">MBAM server event-logging channel</span></span>

<span data-ttu-id="b2853-131">記錄檔位於 [事件檢視器] 中的 [**應用程式和服務記錄**  >  **Microsoft**  >  **Windows**  >  **MBAM**] 底下。</span><span class="sxs-lookup"><span data-stu-id="b2853-131">The log files are located in Event Viewer, under **Application and Services Logs** > **Microsoft** > **Windows** > **MBAM**.</span></span> <span data-ttu-id="b2853-132">下表包含在 MBAM 2.5 中引入的伺服器事件記錄：</span><span class="sxs-lookup"><span data-stu-id="b2853-132">The following table includes server event logs that were introduced in MBAM 2.5:</span></span>

|<span data-ttu-id="b2853-133">事件記錄檔</span><span class="sxs-lookup"><span data-stu-id="b2853-133">Event log</span></span>| <span data-ttu-id="b2853-134">說明</span><span class="sxs-lookup"><span data-stu-id="b2853-134">Description</span></span>|
|--------|-------------|
|<span data-ttu-id="b2853-135">Microsoft-Windows-MBAM/系統管理員</span><span class="sxs-lookup"><span data-stu-id="b2853-135">Microsoft-Windows-MBAM/Admin</span></span>|  <span data-ttu-id="b2853-136">包含錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="b2853-136">Contains error messages</span></span>|
|<span data-ttu-id="b2853-137">Microsoft-Windows-MBAM/分析</span><span class="sxs-lookup"><span data-stu-id="b2853-137">Microsoft-Windows-MBAM/Analytic</span></span>|   <span data-ttu-id="b2853-138">包含高級記錄資訊</span><span class="sxs-lookup"><span data-stu-id="b2853-138">Contains advanced logging information</span></span>|
|<span data-ttu-id="b2853-139">Microsoft-Windows-MBAM/運作</span><span class="sxs-lookup"><span data-stu-id="b2853-139">Microsoft-Windows-MBAM/Operational</span></span>|    <span data-ttu-id="b2853-140">包含成功訊息</span><span class="sxs-lookup"><span data-stu-id="b2853-140">Contains success messages</span></span>|

### <span data-ttu-id="b2853-141">MBAM web 服務記錄</span><span class="sxs-lookup"><span data-stu-id="b2853-141">MBAM web service logs</span></span>

<span data-ttu-id="b2853-142">每個 MBAM web 服務記錄都會將記錄資訊寫入 SVCLOG 檔案。</span><span class="sxs-lookup"><span data-stu-id="b2853-142">Each MBAM web service log writes logging information to an SVCLOG file.</span></span> <span data-ttu-id="b2853-143">根據預設，每個 web 服務都會在 C:\inetpub\Microsoft BitLocker 管理 Solution\Logs 資料夾中使用其名稱的資料夾下寫入追蹤檔案。</span><span class="sxs-lookup"><span data-stu-id="b2853-143">By default, each web service writes the trace file under a folder that uses its name in the C:\inetpub\Microsoft BitLocker Management Solution\Logs folder.</span></span>

<span data-ttu-id="b2853-144">您可以使用服務追蹤檢視器工具（Microsoft Visual Studio 的一部分）來查看 svclog 追蹤。</span><span class="sxs-lookup"><span data-stu-id="b2853-144">You can use the service trace viewer tool (part of Microsoft Visual Studio) to review the svclog traces.</span></span>

## <span data-ttu-id="b2853-145">疑難排解加密和報告問題</span><span class="sxs-lookup"><span data-stu-id="b2853-145">Troubleshooting encryption and reporting issues</span></span>

<span data-ttu-id="b2853-146">本節包含伺服器功能、用戶端功能、配置設定及已知問題的疑難排解資訊：</span><span class="sxs-lookup"><span data-stu-id="b2853-146">This section contains troubleshooting information for server functionality, client functionality, configuration settings, and known issues:</span></span>
 
### <span data-ttu-id="b2853-147">MBAM 用戶端安裝，群組原則設定</span><span class="sxs-lookup"><span data-stu-id="b2853-147">MBAM client installation, Group Policy settings</span></span>

<span data-ttu-id="b2853-148">判斷用戶端電腦上是否已安裝 MBAM 代理程式。</span><span class="sxs-lookup"><span data-stu-id="b2853-148">Determine whether the MBAM agent is installed on the client computer.</span></span> <span data-ttu-id="b2853-149">安裝 MBAM 時，它會建立一個名為 BitLocker 管理用戶端服務的服務。</span><span class="sxs-lookup"><span data-stu-id="b2853-149">When MBAM is installed, it creates a service that is named BitLocker Management Client Service.</span></span> <span data-ttu-id="b2853-150">此服務已設定為自動啟動。</span><span class="sxs-lookup"><span data-stu-id="b2853-150">This service is configured to start automatically.</span></span> <span data-ttu-id="b2853-151">判斷服務是否正在執行。</span><span class="sxs-lookup"><span data-stu-id="b2853-151">Determine whether the service is running.</span></span>

<span data-ttu-id="b2853-152">確定用戶端電腦上已套用 [MBAM] 群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="b2853-152">Make sure that MBAM Group Policy settings are applied on the client computer.</span></span> <span data-ttu-id="b2853-153">如果用戶端電腦上已套用群組原則設定，就會建立下列登錄子機碼： **HKEY_LOCAL_MACHINE \software\policies\microsoft\fve\mdopbitlockermanagement**</span><span class="sxs-lookup"><span data-stu-id="b2853-153">The following registry subkey is created if the Group Policy settings were applied on the client computer: **HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement**</span></span>

<span data-ttu-id="b2853-154">確認此金鑰存在，並使用每個群組原則設定的值來填入。</span><span class="sxs-lookup"><span data-stu-id="b2853-154">Verify that this key exists and is populated by using values per Group Policy settings.</span></span>

### <span data-ttu-id="b2853-155">在初始延遲期間 MBAM 代理程式</span><span class="sxs-lookup"><span data-stu-id="b2853-155">MBAM Agent in the initial delay period</span></span>

<span data-ttu-id="b2853-156">MBAM 用戶端無法在安裝後立即啟動作業。</span><span class="sxs-lookup"><span data-stu-id="b2853-156">The MBAM client doesn't start the operation immediately after installation.</span></span> <span data-ttu-id="b2853-157">在 MBAM Agent 啟動作業之前，會有1到18分鐘的初始隨機延遲時間。</span><span class="sxs-lookup"><span data-stu-id="b2853-157">There is an initial random delay of 1–18 minutes before the MBAM Agent starts its operation.</span></span> <span data-ttu-id="b2853-158">除了初始延遲之外，還會有至少90分鐘的延遲。</span><span class="sxs-lookup"><span data-stu-id="b2853-158">In addition to the initial delay, there is a delay of at least 90 minutes.</span></span> <span data-ttu-id="b2853-159">（延遲取決於針對檢查用戶端狀態的頻率所設定的群組原則設定。）因此，在用戶端開始作業前的總延遲是*隨機啟動延遲*  +  *用戶端檢查頻率的延遲*。</span><span class="sxs-lookup"><span data-stu-id="b2853-159">(The delay depends on the Group Policy settings that are configured for the frequency of checking the client status.) Therefore, the total delay before a client starts operation is *random startup delay* + *client checking frequency delay*.</span></span>

<span data-ttu-id="b2853-160">如果 [操作] 和 [系統管理] 事件記錄是空白的，用戶端還沒有啟動該作業，而且是在前面提到的延遲期間中。</span><span class="sxs-lookup"><span data-stu-id="b2853-160">If the Operational and Admin event logs are blank, the client has not started the operation yet and is in the delay period that was mentioned earlier.</span></span> <span data-ttu-id="b2853-161">如果您想要略過延遲，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="b2853-161">If you want to bypass the delay, follow these steps:</span></span>
 
1. <span data-ttu-id="b2853-162">停止 BitLocker 管理用戶端服務服務。</span><span class="sxs-lookup"><span data-stu-id="b2853-162">Stop the BitLocker Management Client Service service.</span></span>

2. <span data-ttu-id="b2853-163">在**HKEY_LOCAL_MACHINE \software\microsoft\mbam** registry 子機碼底下，**建立 NoStartupDelay**登錄值，將其類型設定為 [ **REG_DWORD**]，然後將它的值設定為**1**。</span><span class="sxs-lookup"><span data-stu-id="b2853-163">Under the **HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MBAM** registry subkey, create the **NoStartupDelay** registry value, set its type to **REG_DWORD**, and then set its value to **1**.</span></span>

3. <span data-ttu-id="b2853-164">在 [ **HKEY_LOCAL_MACHINE \software\policies\microsoft\fve\mdopbitlockermanagement**] 底下，將 [ **ClientWakeupFrequency** ] 和 [ **StatusReportingFrequency** ] 值設定為**1**。</span><span class="sxs-lookup"><span data-stu-id="b2853-164">Under **HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement**, set the **ClientWakeupFrequency** and **StatusReportingFrequency** values to **1**.</span></span> <span data-ttu-id="b2853-165">當您在電腦上進行群組原則更新之後，這些值就會還原為原始設定。</span><span class="sxs-lookup"><span data-stu-id="b2853-165">These values will revert to their original settings after Group Policy updates are on the computer.</span></span>

4. <span data-ttu-id="b2853-166">啟動 BitLocker 管理用戶端服務服務。</span><span class="sxs-lookup"><span data-stu-id="b2853-166">Start the BitLocker Management Client Service service.</span></span>

<span data-ttu-id="b2853-167">在服務啟動後，如果您在本機電腦上登入，但沒有任何錯誤，您應該會在一分鐘內收到加密電腦的要求。</span><span class="sxs-lookup"><span data-stu-id="b2853-167">After the service starts, if you log in locally on the computer and there are no errors, you should receive a request to encrypt the computer within one minute.</span></span> <span data-ttu-id="b2853-168">如果您沒有收到要求，您應該在 MBAM 系統管理記錄中查看任何錯誤專案。</span><span class="sxs-lookup"><span data-stu-id="b2853-168">If you do not receive a request, you should review the MBAM Admin logs for any error entries.</span></span>

### <span data-ttu-id="b2853-169">電腦沒有 TPM 裝置，或未在 BIOS 中啟用 TPM 裝置</span><span class="sxs-lookup"><span data-stu-id="b2853-169">Computer does not have a TPM device, or the TPM device is not enabled in the BIOS</span></span>

<span data-ttu-id="b2853-170">查看 MBAM 系統管理員事件記錄檔。</span><span class="sxs-lookup"><span data-stu-id="b2853-170">Review the MBAM Admin event log.</span></span> <span data-ttu-id="b2853-171">您會在 MBAM 系統管理員事件記錄中看到類似下列的事件專案：</span><span class="sxs-lookup"><span data-stu-id="b2853-171">You will see an event entry that resembles the following in the MBAM Admin event log:</span></span>

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

<span data-ttu-id="b2853-172">開啟 [TPM 管理（TPM）]，並檢查電腦是否有 TPM 裝置。</span><span class="sxs-lookup"><span data-stu-id="b2853-172">Open TPM Management (tpm.msc), and check whether the computer has a TPM device.</span></span> <span data-ttu-id="b2853-173">如果您的 devmgmt 沒有顯示裝置，請開啟 [裝置管理器] （），然後檢查 [安全裝置] 底下的 [受信任的平臺] 模組。</span><span class="sxs-lookup"><span data-stu-id="b2853-173">If tpm.msc does not show a device, open Device Manager (devmgmt.msc), and check for a Trusted Platform Module under Security Devices.</span></span> <span data-ttu-id="b2853-174">如果您沒有看到受信任的平臺模組裝置，這可能是下列其中一個原因所導致：</span><span class="sxs-lookup"><span data-stu-id="b2853-174">If you do not see a Trusted Platform Module device, this might be true for one of the following reasons:</span></span>

* <span data-ttu-id="b2853-175">您的系統沒有受信任的平臺模組（TPM/安全性）裝置。</span><span class="sxs-lookup"><span data-stu-id="b2853-175">Your system doesn't have a Trusted Platform Module (TPM/Security) device.</span></span>

* <span data-ttu-id="b2853-176">TPM 裝置在 BIOS 中停用。</span><span class="sxs-lookup"><span data-stu-id="b2853-176">The TPM device is disabled in the BIOS.</span></span>

* <span data-ttu-id="b2853-177">在 BIOS 中啟用 TPM 裝置，但在 BIOS 中停用了從作業系統設定管理 TPM 裝置。</span><span class="sxs-lookup"><span data-stu-id="b2853-177">TPM Device is enabled in the BIOS, but management of the TPM device from the operating system setting is disabled in the BIOS.</span></span>

* <span data-ttu-id="b2853-178">您不是針對 TPM 裝置使用 Microsoft 驅動程式。</span><span class="sxs-lookup"><span data-stu-id="b2853-178">You aren't using a Microsoft driver for the TPM device.</span></span> <span data-ttu-id="b2853-179">查看 [裝置管理器] 中所列的裝置，以找出 Microsoft TPM 裝置驅動程式。</span><span class="sxs-lookup"><span data-stu-id="b2853-179">Review the devices that are listed in device manager to identify the Microsoft TPM device driver.</span></span>

<span data-ttu-id="b2853-180">如果 TPM 裝置未使用 C:\Windows\System32\tpm.sys 驅動程式，您應該選取 C:\Windows\Inf\tpm.inf 檔案來更新驅動程式。</span><span class="sxs-lookup"><span data-stu-id="b2853-180">If the TPM device is not using the C:\Windows\System32\tpm.sys driver, you should update the driver by selecting the C:\Windows\Inf\tpm.inf file.</span></span>

### <span data-ttu-id="b2853-181">電腦沒有有效的系統磁碟分割</span><span class="sxs-lookup"><span data-stu-id="b2853-181">Computer does not have a valid SYSTEM partition</span></span>

<span data-ttu-id="b2853-182">查看 MBAM 系統管理員事件記錄檔。</span><span class="sxs-lookup"><span data-stu-id="b2853-182">Review the MBAM Admin event log.</span></span> <span data-ttu-id="b2853-183">您會在 MBAM 系統管理員事件記錄中看到類似下列的事件專案：</span><span class="sxs-lookup"><span data-stu-id="b2853-183">You will see an event entry that resembles the following in the MBAM Admin event log:</span></span>

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

<span data-ttu-id="b2853-184">BitLocker 需要系統磁碟分割來啟用加密（[在 Windows 7 中使用 BitLocker 磁片磁碟機加密）：常見問題](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-7/ee449438(v=ws.10)?redirectedfrom=MSDN#bkmk_partitions)）。</span><span class="sxs-lookup"><span data-stu-id="b2853-184">BitLocker requires a SYSTEM partition to enable encryption ([BitLocker Drive Encryption in Windows 7: Frequently Asked Questions](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-7/ee449438(v=ws.10)?redirectedfrom=MSDN#bkmk_partitions)).</span></span>

<span data-ttu-id="b2853-185">MBAM 不會自動建立系統磁碟分割。</span><span class="sxs-lookup"><span data-stu-id="b2853-185">MBAM doesn't create the system partition automatically.</span></span> <span data-ttu-id="b2853-186">您可以使用 BitLocker 磁碟機準備實用程式（bdehdcfg.exe）來建立系統磁碟分割並移動所需的啟動檔案。</span><span class="sxs-lookup"><span data-stu-id="b2853-186">You can use the BitLocker drive preparation utility (bdehdcfg.exe) to create the system partition and move the required startup files.</span></span>

<span data-ttu-id="b2853-187">例如，您可以使用命令 **% windir% \system32\bdeHdCfg.exe 目標預設大小 300-quiet** ，在您部署 MBAM 以進行磁片加密前，預先準備好磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="b2853-187">For example, you can use the command **%windir%\system32\bdeHdCfg.exe -target default -size 300 –quiet** to prepare the drive silently before you deploy MBAM to encrypt the drives.</span></span> <span data-ttu-id="b2853-188">這需要重新開機。</span><span class="sxs-lookup"><span data-stu-id="b2853-188">This requires a restart.</span></span> <span data-ttu-id="b2853-189">您也可以在需要時編寫動作腳本。</span><span class="sxs-lookup"><span data-stu-id="b2853-189">You can also script the action if this is required.</span></span> <span data-ttu-id="b2853-190">下列檔說明 BitLocker 磁碟機準備工具：</span><span class="sxs-lookup"><span data-stu-id="b2853-190">The following document describes the BitLocker Drive Preparation Tool:</span></span>

[<span data-ttu-id="b2853-191">BitLocker 磁片磁碟機準備工具的描述</span><span class="sxs-lookup"><span data-stu-id="b2853-191">Description of the BitLocker Drive Preparation Tool</span></span>](https://support.microsoft.com/help/933246)

### <span data-ttu-id="b2853-192">磁片磁碟機沒有格式化成具有相容的檔案系統</span><span class="sxs-lookup"><span data-stu-id="b2853-192">Drives are not formatted to have a compatible file system</span></span>

<span data-ttu-id="b2853-193">請參閱[TechNet 文章，瞭解 BitLocker 的檔案系統需求](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-7/ee449438(v=ws.10)?redirectedfrom=MSDN#bkmk_hsrequirements)。</span><span class="sxs-lookup"><span data-stu-id="b2853-193">See the [TechNet article for file system requirements for BitLocker](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-7/ee449438(v=ws.10)?redirectedfrom=MSDN#bkmk_hsrequirements).</span></span>

### <span data-ttu-id="b2853-194">群組原則衝突</span><span class="sxs-lookup"><span data-stu-id="b2853-194">Group Policy conflict</span></span>

<span data-ttu-id="b2853-195">您會在 MBAM 系統管理員事件記錄中看到類似下列的事件專案：</span><span class="sxs-lookup"><span data-stu-id="b2853-195">You will see an event entry that resembles the following in the MBAM Admin event log:</span></span>

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

<span data-ttu-id="b2853-196">確認您的群組原則設定，以確認您在 MBAM 群組原則設定之間沒有相衝突的設定。</span><span class="sxs-lookup"><span data-stu-id="b2853-196">Verify your Group Policy settings to make sure that you do not have a conflicting setting among the MBAM Group Policy settings.</span></span>

<span data-ttu-id="b2853-197">您應該使用 [MDOP MBAM] 範本而不是 BitLocker 磁片磁碟機加密範本來設定群組原則。</span><span class="sxs-lookup"><span data-stu-id="b2853-197">You should configure Group Policy by using the MDOP MBAM template and not the BitLocker Drive Encryption template.</span></span>

<span data-ttu-id="b2853-198">例如：</span><span class="sxs-lookup"><span data-stu-id="b2853-198">For example:</span></span>

<span data-ttu-id="b2853-199">在 [作業系統磁片磁碟機加密設定] 下，您已選取 [TPM] 作為保護器，而且您也已選取 [**允許增強的 pin 以進行啟動**]。</span><span class="sxs-lookup"><span data-stu-id="b2853-199">Under Operating system drive encryption settings, you selected TPM as the protector, and you also selected **Allow enhanced PINs for startup**.</span></span> <span data-ttu-id="b2853-200">因為僅 TPM 保護不需要 PIN，所以這些是衝突的設定。</span><span class="sxs-lookup"><span data-stu-id="b2853-200">These are conflicting settings because TPM-only protection doesn't require a PIN.</span></span> <span data-ttu-id="b2853-201">因此，您應該停用 [增強式 Pin] 設定。</span><span class="sxs-lookup"><span data-stu-id="b2853-201">Therefore, you should disable the enhanced PINs setting.</span></span>

### <span data-ttu-id="b2853-202">使用者可能已要求豁免</span><span class="sxs-lookup"><span data-stu-id="b2853-202">User may have requested an exemption</span></span>

<span data-ttu-id="b2853-203">如果您已啟用電腦配置 \ 管理範本 \Windows Components\MDOP MBAM （BitLocker Management） \Client Management\Configure 使用者豁免原則組原則設定，系統會提供要求例外的選項。</span><span class="sxs-lookup"><span data-stu-id="b2853-203">If you enabled the Computer Configuration\Administrative Templates\Windows Components\MDOP MBAM (BitLocker Management)\Client Management\Configure user exemption policy Group Policy setting, users will be offered the option to request an exemption.</span></span>

<span data-ttu-id="b2853-204">根據預設，如果使用者要求免除，該免除將有效期為7天，而且使用者在此期間將不會收到加密的提示。</span><span class="sxs-lookup"><span data-stu-id="b2853-204">By default, if the user requests an exemption, the exemption will be valid for 7 days, and the user will not receive prompts to encrypt during this period.</span></span> <span data-ttu-id="b2853-205">（您可以在原則配置期間增加或減少預設值。）在免除期限結束之後，系統會提示使用者進行加密。</span><span class="sxs-lookup"><span data-stu-id="b2853-205">(The default value can be increased or decreased during policy configuration.) After the exemption period is over, the user is prompted to encrypt.</span></span>

<span data-ttu-id="b2853-206">當電腦處於 [使用者豁免] 下時，在 MBAM 系統管理員事件記錄中，您會看到下列專案：</span><span class="sxs-lookup"><span data-stu-id="b2853-206">You will see the following entry in the MBAM Admin event log when a computer is under user exemption:</span></span>

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

<span data-ttu-id="b2853-207">如果您想要手動覆寫電腦的使用者豁免，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="b2853-207">If you want to manually override user exemption for a computer, follow these steps:</span></span>
 
1. <span data-ttu-id="b2853-208">在下列登錄子機碼底下，將 AllowUserExemption 值設定為**0** ：</span><span class="sxs-lookup"><span data-stu-id="b2853-208">Set the AllowUserExemption value to **0** under the following registry subkey:</span></span> <br />
**<span data-ttu-id="b2853-209">HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement</span><span class="sxs-lookup"><span data-stu-id="b2853-209">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement</span></span>**

2. <span data-ttu-id="b2853-210">刪除下列登錄子機子 AgentVersion 下的所有登錄值（除了是 [ \*\* **]、[ **EncodedComputerName**] 及 [**安裝\*\*]）：</span><span class="sxs-lookup"><span data-stu-id="b2853-210">Delete all the registry values under the following registry subkey except for **AgentVersion**, **EncodedComputerName**, and **Installed**:</span></span><br />
**<span data-ttu-id="b2853-211">HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\MBAM</span><span class="sxs-lookup"><span data-stu-id="b2853-211">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MBAM</span></span>**

    <span data-ttu-id="b2853-212">**記事**您必須重新開機 MBAM 代理程式，變更才會生效。</span><span class="sxs-lookup"><span data-stu-id="b2853-212">**Note** You must restart the MBAM agent for the changes to take effect.</span></span>

<span data-ttu-id="b2853-213">請注意，在您將群組原則套用到電腦之後，這些值可能會還原為原始設定。</span><span class="sxs-lookup"><span data-stu-id="b2853-213">Be aware that after you apply Group Policy to the computer, these values may revert to their original settings.</span></span>

### <span data-ttu-id="b2853-214">WMI 問題</span><span class="sxs-lookup"><span data-stu-id="b2853-214">WMI issue</span></span>

<span data-ttu-id="b2853-215">MBAM 使用 win32_encryptablevolume 類別的方法來管理 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="b2853-215">MBAM uses methods of the win32_encryptablevolume class to manage BitLocker.</span></span> <span data-ttu-id="b2853-216">如果此模組已取消註冊或損毀，MBAM 用戶端將無法正常運作，而且您會在 MBAM 系統管理員事件記錄中看到下列事件專案：</span><span class="sxs-lookup"><span data-stu-id="b2853-216">If this module is unregistered or corrupted, the MBAM client will not operate correctly, and you will see the following event entry in the MBAM Admin event log:</span></span>

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

<span data-ttu-id="b2853-217">此外，您可能會發現 [恢復] 和 [硬體] 原則不適用於錯誤碼0x8007007e。</span><span class="sxs-lookup"><span data-stu-id="b2853-217">Additionally, you may notice that the Recovery and Hardware policies do not apply with Error Code 0x8007007e.</span></span> <span data-ttu-id="b2853-218">這會轉換為「找不到指定的模組」。</span><span class="sxs-lookup"><span data-stu-id="b2853-218">This translates to "The specified module could not be found."</span></span>

<span data-ttu-id="b2853-219">若要解決此問題，您應該使用下列命令重新註冊**win32_encryptablevolume**類別：</span><span class="sxs-lookup"><span data-stu-id="b2853-219">To resolve this issue, you should reregister the **win32_encryptablevolume** class by using the following command:</span></span>

```cmd
mofcomp c:\Windows\System32\wbem\win32_encryptablevolume.mof
```

## <span data-ttu-id="b2853-220">MBAM 代理通訊問題的疑難排解</span><span class="sxs-lookup"><span data-stu-id="b2853-220">Troubleshooting MBAM Agent communication issues</span></span>

<span data-ttu-id="b2853-221">本節包含下列與 MBAM agent 通訊相關之問題的疑難排解資訊：</span><span class="sxs-lookup"><span data-stu-id="b2853-221">This section contains troubleshooting information for the following issues that are related to MBAM agent communication:</span></span>

### <span data-ttu-id="b2853-222">不正確的 MBAM 服務 URL</span><span class="sxs-lookup"><span data-stu-id="b2853-222">Incorrect MBAM service URL</span></span>

<span data-ttu-id="b2853-223">如果 MBAM 合規性狀態服務或復原及硬體服務的值不正確，您會在用戶端電腦上的 MBAM 系統管理員事件記錄中看到如下所示的事件專案：</span><span class="sxs-lookup"><span data-stu-id="b2853-223">If the value of MBAM Compliance Status Service or Recovery and Hardware Service is incorrect, you'll see an event entry that resembles the following in the MBAM Admin event log on the client computer:</span></span>

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

<span data-ttu-id="b2853-224">在用戶端電腦上的下列登錄子項下，確認**KeyRecoveryServiceEndPoint**和**StatusReportingServiceEndpoint**的值：</span><span class="sxs-lookup"><span data-stu-id="b2853-224">Verify the values of **KeyRecoveryServiceEndPoint** and **StatusReportingServiceEndpoint** under the following registry subkey on the client computer:</span></span> <br />
**<span data-ttu-id="b2853-225">HKEY_LOCAL_MACHINE \SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement</span><span class="sxs-lookup"><span data-stu-id="b2853-225">HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement</span></span>**

<span data-ttu-id="b2853-226">根據預設，KeyRecoveryServiceEndPoint （MBAM 復原與硬體服務端點）的 URL 會採用下列格式：</span><span class="sxs-lookup"><span data-stu-id="b2853-226">By default, the URL for KeyRecoveryServiceEndPoint (MBAM Recovery and Hardware service endpoint) is in the following format:</span></span> <br />
**<span data-ttu-id="b2853-227">HTTP:// \<servername\> ： \<port\> /MBAMRecoveryAndHardwareService/CoreService.svc</span><span class="sxs-lookup"><span data-stu-id="b2853-227">http://\<servername\>:\<port\>/MBAMRecoveryAndHardwareService/CoreService.svc</span></span>**

<span data-ttu-id="b2853-228">根據預設，StatusReportingServiceEndpoint （MBAM 狀態報表服務端點）的 URL 會採用下列格式：</span><span class="sxs-lookup"><span data-stu-id="b2853-228">By default, the URL for StatusReportingServiceEndpoint (MBAM Status reporting service endpoint) is in the following format:</span></span><br />
**<span data-ttu-id="b2853-229">HTTP:// \<servername\> ： \<port\> /MBAMComplianceStatusService/StatusReportingService.svc</span><span class="sxs-lookup"><span data-stu-id="b2853-229">http://\<servername\>:\<port\>/MBAMComplianceStatusService/StatusReportingService.svc</span></span>**

> [!Note]
> <span data-ttu-id="b2853-230">URL 中不應有空格。</span><span class="sxs-lookup"><span data-stu-id="b2853-230">There should be no spaces in the URL.</span></span>

<span data-ttu-id="b2853-231">如果服務 URL 不正確，您應該在下列群組原則設定中修正服務 URL：</span><span class="sxs-lookup"><span data-stu-id="b2853-231">If the service URL is incorrect, you should correct the service URL in the following Group Policy setting:</span></span>

<span data-ttu-id="b2853-232">**電腦配置**  > **原則**  > **管理範本**  > **Windows 元件**  > **MDOP MBAM （BitLocker 管理）**  > **用戶端管理**  > **設定 MBAM 服務**</span><span class="sxs-lookup"><span data-stu-id="b2853-232">**Computer configuration** > **Policies** > **Administrative Templates** > **Windows Components** > **MDOP MBAM (BitLocker Management)** > **Client Management** > **Configure MBAM Services**</span></span>

### <span data-ttu-id="b2853-233">影響 MBAM 管理伺服器的連接問題</span><span class="sxs-lookup"><span data-stu-id="b2853-233">Connectivity issue that affects the MBAM administration server</span></span>

<span data-ttu-id="b2853-234">如果用戶端代理程式與 MBAM 管理伺服器之間存在連線問題，則 MBAM 代理程式將無法將任何更新發佈至資料庫。</span><span class="sxs-lookup"><span data-stu-id="b2853-234">The MBAM agent will be unable to post any updates to the database if connectivity issues exist between the client agent and the MBAM administration server.</span></span> <span data-ttu-id="b2853-235">在這種情況下，您會在用戶端電腦上的 MBAM 系統管理員事件記錄中發現連線失敗專案：</span><span class="sxs-lookup"><span data-stu-id="b2853-235">In this case, you will notice connectivity failure entries in the MBAM Admin event log on the client computer:</span></span>

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

<span data-ttu-id="b2853-236">基本檢查：</span><span class="sxs-lookup"><span data-stu-id="b2853-236">Basic checks:</span></span>

* <span data-ttu-id="b2853-237">透過 [名稱] 和 [IP] ping MBAM 管理伺服器來驗證基本連通性。</span><span class="sxs-lookup"><span data-stu-id="b2853-237">Verify basic connectivity by pinging the MBAM administration server by name and IP.</span></span> <span data-ttu-id="b2853-238">檢查您是否可以使用 telnet 或 portqry 連線到 MBAM 管理網站或服務埠。</span><span class="sxs-lookup"><span data-stu-id="b2853-238">Check whether you can connect to the MBAM administration website or service port by using telnet or portqry.</span></span>

* <span data-ttu-id="b2853-239">確認 IIS 服務正在 MBAM 管理和監視伺服器上執行，且 MBAM web 服務正在偵聽 MBAM 用戶端電腦上設定的同一個埠（ `netstat –ano | find "portnumber"` ）。</span><span class="sxs-lookup"><span data-stu-id="b2853-239">Verify that the IIS service is running on the MBAM administration and monitoring server and that the MBAM web service is listening on the same port that is configured on the MBAM client computer (`netstat –ano | find "portnumber"`).</span></span>

* <span data-ttu-id="b2853-240">確認為 MBAM 網站設定的埠號碼是使用 IIS 管理員（inetmgr）。</span><span class="sxs-lookup"><span data-stu-id="b2853-240">Verify that the port number that is configured for the MBAM website is using IIS Manager (inetmgr).</span></span> <span data-ttu-id="b2853-241">確認埠號碼與用戶端正在其上接聽的埠號碼相同。</span><span class="sxs-lookup"><span data-stu-id="b2853-241">Make sure that the port number is the same as the port number on which the client is listening.</span></span> <span data-ttu-id="b2853-242">確認埠號碼不是由其他應用程式所共用。</span><span class="sxs-lookup"><span data-stu-id="b2853-242">Make sure that the port number is not shared by another application.</span></span> <span data-ttu-id="b2853-243">例如，伺服器上的另一個應用程式不應使用相同的埠。</span><span class="sxs-lookup"><span data-stu-id="b2853-243">For example, another application on the server should not be using the same port.</span></span>

* <span data-ttu-id="b2853-244">如果有防火牆，請確定該埠已在防火牆或 proxy 伺服器中開啟。</span><span class="sxs-lookup"><span data-stu-id="b2853-244">If there is a firewall, make sure that the port is open in the firewall or proxy server.</span></span>

* <span data-ttu-id="b2853-245">如果用戶端與伺服器之間的通訊是安全的，請確定您使用的是有效的 SSL 憑證。</span><span class="sxs-lookup"><span data-stu-id="b2853-245">If the communication between client and server is secure, make sure that you are using a valid SSL certificate.</span></span>

* <span data-ttu-id="b2853-246">驗證要傳送資料以進行插入的 web 伺服器與資料庫伺服器之間的網路連線。</span><span class="sxs-lookup"><span data-stu-id="b2853-246">Verify network connectivity between the web server and the database server to which the data is sent for insertion.</span></span> <span data-ttu-id="b2853-247">您可以使用 ODBC 資料來源系統管理員，檢查從 web 伺服器到資料庫伺服器的資料庫連線能力。</span><span class="sxs-lookup"><span data-stu-id="b2853-247">You can check database connectivity from the web server to the database server by using ODBC Data Source Administrator.</span></span> <span data-ttu-id="b2853-248">詳細的 SQL Server 連線疑難排解資訊可在[如何疑難排解連線至 SQL Server 資料庫引擎的問題](https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx)中取得。</span><span class="sxs-lookup"><span data-stu-id="b2853-248">Detailed SQL Server connection troubleshooting information is available in [How to Troubleshoot Connecting to the SQL Server Database Engine](https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx).</span></span>

#### <span data-ttu-id="b2853-249">疑難排解連接問題</span><span class="sxs-lookup"><span data-stu-id="b2853-249">Troubleshooting the connectivity issue</span></span>

<span data-ttu-id="b2853-250">確定用戶端上設定的服務 URL 正確無誤。</span><span class="sxs-lookup"><span data-stu-id="b2853-250">Make sure that the service URL that is configured on the client is correct.</span></span> <span data-ttu-id="b2853-251">從 registry 複製 KeyRecoveryServiceEndPoint （**HKEY_LOCAL_MACHINE \software\policies\microsoft\fve\mdopbitlockermanagement**） URL 的值，然後在 Internet Explorer 中開啟。</span><span class="sxs-lookup"><span data-stu-id="b2853-251">Copy the value of the URL for KeyRecoveryServiceEndPoint (**HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement**) from the registry, and open it in Internet Explorer.</span></span>

<span data-ttu-id="b2853-252">同樣地，複製 StatusReportingServiceEndpoint 的 URL 值（**HKEY_LOCAL_MACHINE \software\policies\microsoft\fve\mdopbitlockermanagement**），然後在 Internet Explorer 中開啟它。</span><span class="sxs-lookup"><span data-stu-id="b2853-252">Similarly, copy the value of the URL for StatusReportingServiceEndpoint (**HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\FVE\MDOPBitLockerManagement**), and open it in Internet Explorer.</span></span>

> [!Note]
> <span data-ttu-id="b2853-253">如果您無法從用戶端電腦流覽至 URL，您應該測試從用戶端到執行 IIS 之伺服器的基本網路連線性。</span><span class="sxs-lookup"><span data-stu-id="b2853-253">If you cannot browse to the URL from the client computer, you should test basic network connectivity from the client to the server that is running IIS.</span></span> <span data-ttu-id="b2853-254">請參閱上一節中的1、2、3和4點。</span><span class="sxs-lookup"><span data-stu-id="b2853-254">See points 1, 2, 3, and 4 in the previous section.</span></span>

<span data-ttu-id="b2853-255">此外，請在 [管理和監控伺服器] 上查看應用程式記錄，以取得任何錯誤。</span><span class="sxs-lookup"><span data-stu-id="b2853-255">Additionally, review the Application logs on the administration and monitoring server for any errors.</span></span>

<span data-ttu-id="b2853-256">您可以在用戶端與伺服器之間建立併發網路追蹤，並查看追蹤，以判斷用戶端代理與 MBAM 管理伺服器之間的連線失敗原因。</span><span class="sxs-lookup"><span data-stu-id="b2853-256">You can make a concurrent network trace between the client and the server, and review the trace to determine the cause of connection failure between the client agent and the MBAM administration server.</span></span>

> [!Note]
> <span data-ttu-id="b2853-257">如果您可以流覽用戶端電腦的服務 Url，並在 MBAM admin 事件記錄中出現連接錯誤專案，這可能是因為管理伺服器與資料庫伺服器之間的連線失敗。</span><span class="sxs-lookup"><span data-stu-id="b2853-257">If you can browse to the service URLs from the client computer and there are connectivity error entries in the MBAM admin event logs, this might be because of a connectivity failure between the administration server and the database server.</span></span>

<span data-ttu-id="b2853-258">如果您可以成功流覽兩個服務 Url，且用戶端與執行中的伺服器之間有連線，則表示 IIS 正在運作。</span><span class="sxs-lookup"><span data-stu-id="b2853-258">If you can successfully browse to both service URLs, and there is connectivity between the client and the server that is running, IIS is working.</span></span> <span data-ttu-id="b2853-259">不過，在執行 IIS 和資料庫伺服器的伺服器之間，可能會發生通訊問題。</span><span class="sxs-lookup"><span data-stu-id="b2853-259">However, there may be a problem in communication between the server that is running IIS and the database server.</span></span>

<span data-ttu-id="b2853-260">由於網路問題或資料庫連線字串設定不正確，因此 MBAM services 可能無法連線到資料庫伺服器。</span><span class="sxs-lookup"><span data-stu-id="b2853-260">The MBAM services may be unable to connect to the database server because of a network issue or an incorrect database connection string setting.</span></span> <span data-ttu-id="b2853-261">在 [管理及監視伺服器] 上查看應用程式記錄。</span><span class="sxs-lookup"><span data-stu-id="b2853-261">Review the Application logs on the administration and monitoring server.</span></span> <span data-ttu-id="b2853-262">您可能會看到來源 ASP.NET 2.0.50727.0 中的錯誤專案或警告，類似下列記錄專案：</span><span class="sxs-lookup"><span data-stu-id="b2853-262">You might see errors entries or warnings from source ASP.NET 2.0.50727.0 that resemble the following log entry:</span></span>

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

#### <span data-ttu-id="b2853-263">可能原因</span><span class="sxs-lookup"><span data-stu-id="b2853-263">Possible causes</span></span>

##### <span data-ttu-id="b2853-264">原因1</span><span class="sxs-lookup"><span data-stu-id="b2853-264">Cause 1</span></span>

<span data-ttu-id="b2853-265">在安裝管理與監視伺服器元件期間，管理員可能指定了不正確資料庫實例名稱/資料庫名稱。</span><span class="sxs-lookup"><span data-stu-id="b2853-265">The administrator may have specified an invalid database instance name/database name during installation of administration and monitoring server components.</span></span>

<span data-ttu-id="b2853-266">您可以使用 IIS 管理主控台驗證並修正資料庫連接字串。</span><span class="sxs-lookup"><span data-stu-id="b2853-266">You can verify and correct the database connection strings by using the IIS Management console.</span></span> <span data-ttu-id="b2853-267">若要這樣做，請開啟 IIS 管理員，然後流覽至 Microsoft BitLocker 管理與監視。</span><span class="sxs-lookup"><span data-stu-id="b2853-267">To do this, open IIS Manager, and browse to Microsoft BitLocker Administration and Monitoring.</span></span> <span data-ttu-id="b2853-268">針對左側所列的每個服務，請遵循下列步驟來變更資料庫連線字串：</span><span class="sxs-lookup"><span data-stu-id="b2853-268">For each service that is listed on the left side, follow these steps to change the database connection strings:</span></span>

1. <span data-ttu-id="b2853-269">在 [**功能] 視圖**中，按兩下 [**連接字串**]。</span><span class="sxs-lookup"><span data-stu-id="b2853-269">In **Features View**, double-select **Connection Strings**.</span></span>

2. <span data-ttu-id="b2853-270">在 [**連接字串**] 頁面上，選取您要變更的連接字串。</span><span class="sxs-lookup"><span data-stu-id="b2853-270">On the **Connection Strings** page, select the connection string that you want to change.</span></span>

3. <span data-ttu-id="b2853-271">在 [**動作**] 窗格中，選取 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="b2853-271">In the **Actions** pane, select **Edit**.</span></span>

4. <span data-ttu-id="b2853-272">在 [**編輯連接字串**] 對話方塊中，變更您要變更的屬性，然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="b2853-272">In the **Edit Connection String** dialog box, change the properties that you want to change, and then select **OK**.</span></span>

##### <span data-ttu-id="b2853-273">原因2</span><span class="sxs-lookup"><span data-stu-id="b2853-273">Cause 2</span></span>

<span data-ttu-id="b2853-274">在防火牆中封鎖 SQL Server 埠。</span><span class="sxs-lookup"><span data-stu-id="b2853-274">SQL Server port blocked in firewall.</span></span> <span data-ttu-id="b2853-275">確認 SQL Server 設定為要監聽的埠號碼，並確定該埠已在系統管理伺服器和資料庫伺服器之間的防火牆中開啟。</span><span class="sxs-lookup"><span data-stu-id="b2853-275">Verify the port number to which SQL Server is configured to listen, and make sure that the port is open in the firewall between the administration server and database server.</span></span>

##### <span data-ttu-id="b2853-276">原因3</span><span class="sxs-lookup"><span data-stu-id="b2853-276">Cause 3</span></span>

<span data-ttu-id="b2853-277">不正確的 SQL server TCP/IP 系結。</span><span class="sxs-lookup"><span data-stu-id="b2853-277">Incorrect SQL server TCP/IP bindings.</span></span> <span data-ttu-id="b2853-278">在資料庫伺服器上，確認 SQL Server Configuration Manager 中的 SQL TCP/IP 系結。</span><span class="sxs-lookup"><span data-stu-id="b2853-278">Verify SQL TCP/IP bindings in SQL Server Configuration Manager on the database server.</span></span> <span data-ttu-id="b2853-279">MBAM 需要啟用 TCP/IP 和具名管道通訊協定才能連線至資料庫。</span><span class="sxs-lookup"><span data-stu-id="b2853-279">MBAM requires that the TCP/IP and Named Pipes protocols are enabled to connect to the database.</span></span>

##### <span data-ttu-id="b2853-280">原因4</span><span class="sxs-lookup"><span data-stu-id="b2853-280">Cause 4</span></span>

<span data-ttu-id="b2853-281">NT Authority\Network 服務帳戶或 MBAM 管理伺服器的電腦帳戶不具備連線至 SQL 資料庫所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="b2853-281">The NT Authority\Network Service account or the MBAM Administration Server’s computer account doesn't have the required permissions to connect to the SQL database.</span></span>

<span data-ttu-id="b2853-282">在資料庫伺服器上安裝資料庫元件期間，安裝程式會建立兩個本機群組： MBAM 合規性審核資料庫存取和 MBAM 復原與硬體資料庫存取。</span><span class="sxs-lookup"><span data-stu-id="b2853-282">During the installation of database components on the database server, the installer creates two local groups: MBAM Compliance Auditing DB Access and MBAM Recovery and Hardware DB Access.</span></span>

<span data-ttu-id="b2853-283">NT Authority\Network 服務帳戶、MBAM 管理伺服器的電腦帳戶，以及安裝資料庫元件的使用者，都會自動新增到這些群組中。</span><span class="sxs-lookup"><span data-stu-id="b2853-283">The NT Authority\Network Service account, the MBAM administration server’s computer account, and the user who installs the database components are automatically added to these groups.</span></span>

<span data-ttu-id="b2853-284">在安裝期間，系統會將這些群組授與資料庫所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="b2853-284">These groups are granted the required permissions on the database during the installation.</span></span> <span data-ttu-id="b2853-285">屬於這個群組的所有使用者，都會自動收到資料庫所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="b2853-285">All users who are part of this group automatically receive the required permissions on the database.</span></span>

<span data-ttu-id="b2853-286">由於下列一或多個條件屬實，所以 web 服務可能無法連線到資料庫伺服器：</span><span class="sxs-lookup"><span data-stu-id="b2853-286">The web service may not connect to the database server because of a permissions issue if one or more of the following conditions are true:</span></span>

* <span data-ttu-id="b2853-287">前面提到的群組會從資料庫伺服器上的本機群組中移除。</span><span class="sxs-lookup"><span data-stu-id="b2853-287">The groups that were mentioned earlier are removed from the local groups on the database server.</span></span>

* <span data-ttu-id="b2853-288">NT Authority\Network 服務帳戶和 MBAM 管理伺服器的電腦帳戶不是這些群組的成員。</span><span class="sxs-lookup"><span data-stu-id="b2853-288">The NT Authority\Network Service account and the MBAM administration server’s computer account are not members of these groups.</span></span>

* <span data-ttu-id="b2853-289">這些群組沒有資料庫所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="b2853-289">These groups do not have the required permissions on the database.</span></span>

<span data-ttu-id="b2853-290">如果上述任何情況屬實，您會注意到 MBAM 管理和監視伺服器上的應用程式記錄中的許可權相關錯誤。</span><span class="sxs-lookup"><span data-stu-id="b2853-290">You will notice permissions-related errors in the Application logs on the MBAM administration and monitoring server if any of the previous conditions are true.</span></span> <span data-ttu-id="b2853-291">在這種情況下，您應該手動新增 NT Authority\Network 服務帳戶和 MBAM 管理伺服器的電腦帳戶，並在使用 SQL Server Management Studio （.）的 SQL 資料庫伺服器上，授與伺服器範圍的公用角色 https://msdn.microsoft.com/library/aa337562.aspx) 。</span><span class="sxs-lookup"><span data-stu-id="b2853-291">In that case, you should manually add the NT Authority\Network Service account and MBAM administration server’s computer account and grant them a server-wide public role on the SQL database server that is using SQL Server Management Studio (https://msdn.microsoft.com/library/aa337562.aspx).</span></span>

#### <span data-ttu-id="b2853-292">查看 web 服務記錄</span><span class="sxs-lookup"><span data-stu-id="b2853-292">Review the web service logs</span></span>

<span data-ttu-id="b2853-293">如果 MBAM 管理伺服器上的應用程式記錄中沒有記錄任何事件，現在就可以查看 MBAM 管理和監視伺服器上所託管之 MBAM web 服務的 web 服務記錄（svclog）。</span><span class="sxs-lookup"><span data-stu-id="b2853-293">If no events are logged in the Application logs on the MBAM administration server, it’s time to review the web service logs (.svclog) of the MBAM web service that is hosted on the MBAM administration and monitoring server.</span></span> <span data-ttu-id="b2853-294">您必須使用服務追蹤檢視器工具（SvcTraceViewer.exe） https://msdn.microsoft.com/library/ms732023.aspx 來查看記錄檔。</span><span class="sxs-lookup"><span data-stu-id="b2853-294">You will have to use the Service Trace Viewer Tool (SvcTraceViewer.exe) https://msdn.microsoft.com/library/ms732023.aspx to view the log file.</span></span>

<span data-ttu-id="b2853-295">您應該主要調查 RecoveryandHardwareService 和 ComplianceStatusService 的服務追蹤記錄。</span><span class="sxs-lookup"><span data-stu-id="b2853-295">You should primarily investigate the service trace logs of RecoveryandHardwareService and ComplianceStatusService.</span></span> <span data-ttu-id="b2853-296">根據預設，web 服務記錄位於 [C:\inetpub\Microsoft BitLocker 管理 Solution\Logs] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="b2853-296">By default, web service logs are located in the C:\inetpub\Microsoft BitLocker Management Solution\Logs folder.</span></span> <span data-ttu-id="b2853-297">在這裡，每個服務都會在自己的資料夾下寫入其 svclog 檔案。</span><span class="sxs-lookup"><span data-stu-id="b2853-297">There, each service writes its .svclog file under its own folder.</span></span>

<span data-ttu-id="b2853-298">在服務追蹤記錄中，查看任何錯誤或警告專案的活動。</span><span class="sxs-lookup"><span data-stu-id="b2853-298">Review the activity in the service trace log for any error or warning entries.</span></span> <span data-ttu-id="b2853-299">根據預設，錯誤專案會以紅色醒目提示。</span><span class="sxs-lookup"><span data-stu-id="b2853-299">By default, error entries are highlighted in red.</span></span> <span data-ttu-id="b2853-300">選取 [追蹤檢視器] 右窗格中的 [錯誤描述]，以查看錯誤專案的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="b2853-300">Select the error description on the right pane of the trace viewer to view detailed information about the error entry.</span></span> <span data-ttu-id="b2853-301">以下是追蹤記錄中的範例錯誤專案：</span><span class="sxs-lookup"><span data-stu-id="b2853-301">The following is a sample error entry from the trace log:</span></span>

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

## <span data-ttu-id="b2853-302">重新安裝或重新配置 MBAM 基礎結構</span><span class="sxs-lookup"><span data-stu-id="b2853-302">Re-installation or reconfiguration of MBAM infrastructure</span></span>

<span data-ttu-id="b2853-303">若要重新安裝或重新設定 MBAM 基礎結構，您必須知道下列事項：</span><span class="sxs-lookup"><span data-stu-id="b2853-303">To re-install or reconfigure MBAM infrastructure, you must know the following things:</span></span>

* <span data-ttu-id="b2853-304">應用程式池帳戶</span><span class="sxs-lookup"><span data-stu-id="b2853-304">Application Pool account</span></span>

* <span data-ttu-id="b2853-305">MBAM 群組（[技術支援]、[高級]、[報表使用者] 群組）</span><span class="sxs-lookup"><span data-stu-id="b2853-305">MBAM Groups (Helpdesk, Advanced, Report Users Group)</span></span>

* <span data-ttu-id="b2853-306">MBAM 報表 URL</span><span class="sxs-lookup"><span data-stu-id="b2853-306">MBAM Reports URL</span></span>

* <span data-ttu-id="b2853-307">SQL Server 名稱與資料庫名稱</span><span class="sxs-lookup"><span data-stu-id="b2853-307">SQL Server name and database names</span></span>

* <span data-ttu-id="b2853-308">MBAM ReadWrite 與 ReadOnly 帳戶</span><span class="sxs-lookup"><span data-stu-id="b2853-308">MBAM ReadWrite and ReadOnly Accounts</span></span>

### <span data-ttu-id="b2853-309">應用程式池帳戶</span><span class="sxs-lookup"><span data-stu-id="b2853-309">Application Pool account</span></span>

<span data-ttu-id="b2853-310">若要尋找應用程式池帳戶，請登入 MBAM Web 服務器、開啟 [**網際網路資訊服務（IIS）管理員**]，然後選取 [**應用程式池**]：</span><span class="sxs-lookup"><span data-stu-id="b2853-310">To find the Application Pool account, log on to the MBAM Web Server, open **Internet Information Services (IIS) Manager**, and then select **Application Pools**:</span></span>

![應用程式池](images/troubleshooting-MBAM-installation-1.png)

<span data-ttu-id="b2853-312">服務主體名稱（SPN）必須在這個帳戶中設定。</span><span class="sxs-lookup"><span data-stu-id="b2853-312">The Service Principal Name (SPN) must be set in this account.</span></span> <span data-ttu-id="b2853-313">這個設定對 MBAM 的功能非常重要。</span><span class="sxs-lookup"><span data-stu-id="b2853-313">This setting is very important to the functionality of MBAM.</span></span>

### <span data-ttu-id="b2853-314">MBAM 群組（[技術支援]、[高級]、[報表使用者] 群組和報表 URL）</span><span class="sxs-lookup"><span data-stu-id="b2853-314">MBAM Groups (Helpdesk, Advanced, Report Users Group and Reports URL)</span></span>

![MBAM 群組](images/troubleshooting-MBAM-installation-2.png)

<span data-ttu-id="b2853-316">這會提供 [服務台] 群組、[高級支援人員] 群組、[報告使用者] 群組，以及 MBAM 報表 URL 等相關資訊。</span><span class="sxs-lookup"><span data-stu-id="b2853-316">This provides information such as Helpdesk Group, Advanced Helpdesk Group, Report Users group, and MBAM Reports URL.</span></span> <span data-ttu-id="b2853-317">MBAM 報表 URL 必須在 [MBAM 設定] 中提供，且應閱讀為： HTTP （s）：//servername/ReportServer。</span><span class="sxs-lookup"><span data-stu-id="b2853-317">The MBAM Reports URL must be provided in the MBAM setup and should read as: http(s)://servername/ReportServer.</span></span>

### <span data-ttu-id="b2853-318">SQL Server 名稱和資料庫（DB）名稱</span><span class="sxs-lookup"><span data-stu-id="b2853-318">SQL Server name and database (DB) names</span></span>

<span data-ttu-id="b2853-319">若要尋找託管 MBAM 的 SQL Server 名稱和實例，請登入 MBAM Web （IIS）伺服器，然後流覽至 folowing 登錄子機碼：</span><span class="sxs-lookup"><span data-stu-id="b2853-319">To find the SQL Server names and instances hosting the MBAM DBs, log on to the MBAM Web (IIS) server and browse to the folowing registry subkey:</span></span>

**<span data-ttu-id="b2853-320">HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\MBAM Server\Web</span><span class="sxs-lookup"><span data-stu-id="b2853-320">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MBAM Server\Web</span></span>**

![註冊表](images/troubleshooting-MBAM-installation-3.png)

<span data-ttu-id="b2853-322">醒目提示的部分是連接字串。</span><span class="sxs-lookup"><span data-stu-id="b2853-322">The highlighted portions are connection strings.</span></span> <span data-ttu-id="b2853-323">這些應該有 SQL Server 名稱、資料庫名稱和實例（如果已命名的話）。</span><span class="sxs-lookup"><span data-stu-id="b2853-323">These should have the SQL Server name, database names, and instances (if named).</span></span>

### <span data-ttu-id="b2853-324">MBAM ReadWrite 與 ReadOnly 帳戶</span><span class="sxs-lookup"><span data-stu-id="b2853-324">MBAM ReadWrite and ReadOnly accounts</span></span>

<span data-ttu-id="b2853-325">這項資訊將會在 SQL Server 資料庫中，我們已找到來自網頁伺服器的名稱。</span><span class="sxs-lookup"><span data-stu-id="b2853-325">This information will be in the SQL Server database, for which we already found the name from the web server.</span></span>

#### <span data-ttu-id="b2853-326">ReadWrite 帳戶</span><span class="sxs-lookup"><span data-stu-id="b2853-326">ReadWrite account</span></span>

1. <span data-ttu-id="b2853-327">登入 SQL Management Studio。</span><span class="sxs-lookup"><span data-stu-id="b2853-327">Log in to the SQL Management Studio.</span></span>

2. <span data-ttu-id="b2853-328">以滑鼠右鍵按一下 [ **MBAM 復原及硬體**]，選取 [**屬性**]，然後選取 [**許可權**]。</span><span class="sxs-lookup"><span data-stu-id="b2853-328">Right-click **MBAM Recovery and Hardware**, select **Properties**, and then select **Permissions**.</span></span>

<span data-ttu-id="b2853-329">例如，lab 帳戶名稱是**MBAMWrite**。</span><span class="sxs-lookup"><span data-stu-id="b2853-329">For example, The the lab account name is **MBAMWrite**.</span></span> <span data-ttu-id="b2853-330">應用程式池和 ReadWrite 帳戶已設定為相同。</span><span class="sxs-lookup"><span data-stu-id="b2853-330">The Application Pool and ReadWrite accounts are set to be the same.</span></span>

![SQL 資料庫](images/troubleshooting-MBAM-installation-4.png)

![DB 屬性](images/troubleshooting-MBAM-installation-5.png)

<span data-ttu-id="b2853-333">流覽至 [**安全性**]，然後流覽至 SQL Management Studio 中的 [**登錄**]。</span><span class="sxs-lookup"><span data-stu-id="b2853-333">Browse to **Security** and then **Logins** in SQL Management Studio.</span></span> <span data-ttu-id="b2853-334">流覽至上一個螢幕擷取畫面中顯示的帳戶。</span><span class="sxs-lookup"><span data-stu-id="b2853-334">Browse to the account shown in the previous screenshot.</span></span>

![SQL 安全性](images/troubleshooting-MBAM-installation-6.png)

<span data-ttu-id="b2853-336">以滑鼠右鍵按一下帳戶，移至 [**屬性使用者對應**]，然後找出 MBAM 復原與硬體資料庫：</span><span class="sxs-lookup"><span data-stu-id="b2853-336">Right-click the accounts, go to **Properties User Mapping**, and locate the MBAM Recovery and Hardware database:</span></span>

![使用者對應](images/troubleshooting-MBAM-installation-7.png)

#### <span data-ttu-id="b2853-338">唯讀帳戶</span><span class="sxs-lookup"><span data-stu-id="b2853-338">ReadOnly account</span></span>

<span data-ttu-id="b2853-339">在 SSRS 伺服器上開啟 [SQL Server Reporting Services Configuration Manager]。</span><span class="sxs-lookup"><span data-stu-id="b2853-339">Open SQL Server Reporting Services Configuration Manager on the SSRS Server.</span></span> <span data-ttu-id="b2853-340">選取 [**報表管理員 URL**]，然後流覽**url**：</span><span class="sxs-lookup"><span data-stu-id="b2853-340">Select **Report Manager URL**, and then browse the **URLs**:</span></span>

![報表管理員](images/troubleshooting-MBAM-installation-8.png)

<span data-ttu-id="b2853-342">選取 [ **Microsoft Bitlocker 管理及監視**]：</span><span class="sxs-lookup"><span data-stu-id="b2853-342">Select **Microsoft Bitlocker Administration and Monitoring**:</span></span>

![Bitlocker 管理和監視](images/troubleshooting-MBAM-installation-9.png)

<span data-ttu-id="b2853-344">選取 [ **MaltaDatasource**]：</span><span class="sxs-lookup"><span data-stu-id="b2853-344">Select **MaltaDatasource**:</span></span>

![[](images/troubleshooting-MBAM-installation-10.png)

![MaltaDatasource](images/troubleshooting-MBAM-installation-11.png)

<span data-ttu-id="b2853-347">MaltaDataSource 應該具有唯讀帳戶名稱，且應該用於 MBAM 設定。</span><span class="sxs-lookup"><span data-stu-id="b2853-347">MaltaDataSource should have the ReadOnly Account name and should be used in MBAM setup.</span></span>

## <span data-ttu-id="b2853-348">參考</span><span class="sxs-lookup"><span data-stu-id="b2853-348">Reference</span></span>

<span data-ttu-id="b2853-349">如需詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="b2853-349">For more information, see the following articles:</span></span>

[<span data-ttu-id="b2853-350">在獨立配置中部署 MBAM 2。5</span><span class="sxs-lookup"><span data-stu-id="b2853-350">Deploying MBAM 2.5 in a standalone configuration</span></span>](https://support.microsoft.com/help/3046555)

[<span data-ttu-id="b2853-351">Microsoft BitLocker Administration and Monitoring 2.5</span><span class="sxs-lookup"><span data-stu-id="b2853-351">Microsoft BitLocker Administration and Monitoring 2.5</span></span>](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/)
