---
title: 如何將 MBAM 用戶端部署為 Windows 部署的一部分
description: 如何將 MBAM 用戶端部署為 Windows 部署的一部分
author: dansimp
ms.assetid: 8704bf33-535d-41da-b9b2-45b60754367e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a63311bcc93d84472ceff5c80c9222fefd5445c0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810839"
---
# <span data-ttu-id="4245b-103">如何將 MBAM 用戶端部署為 Windows 部署的一部分</span><span class="sxs-lookup"><span data-stu-id="4245b-103">How to Deploy the MBAM Client as Part of a Windows Deployment</span></span>


<span data-ttu-id="4245b-104">Microsoft BitLocker 管理和監控（MBAM）用戶端可讓系統管理員在企業中的電腦上強制執行及監視 BitLocker 磁片磁碟機加密。</span><span class="sxs-lookup"><span data-stu-id="4245b-104">The Microsoft BitLocker Administration and Monitoring (MBAM) Client enables administrators to enforce and monitor BitLocker drive encryption on computers in the enterprise.</span></span> <span data-ttu-id="4245b-105">您可以在電腦影像和 Windows 部署程式期間，在用戶端電腦上啟用 BitLocker 管理和加密，以將 BitLocker 用戶端整合到組織中。</span><span class="sxs-lookup"><span data-stu-id="4245b-105">The BitLocker Client can be integrated into an organization by enabling BitLocker management and encryption on client computers during the computer imaging and Windows deployment process.</span></span>

**<span data-ttu-id="4245b-106">注意</span><span class="sxs-lookup"><span data-stu-id="4245b-106">Note</span></span>**  
<span data-ttu-id="4245b-107">若要查看 MBAM 用戶端系統需求，請參閱[MBAM 1.0 支援](mbam-10-supported-configurations.md)的設定。</span><span class="sxs-lookup"><span data-stu-id="4245b-107">To review the MBAM Client system requirements, see [MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md).</span></span>



<span data-ttu-id="4245b-108">在 Windows 部署的初始影像階段中使用 BitLocker 加密用戶端電腦，可以降低 MBAM 實現的管理負荷。</span><span class="sxs-lookup"><span data-stu-id="4245b-108">Encryption of client computers with BitLocker during the initial imaging stage of a Windows deployment can lower the administrative overhead for MBAM implementation.</span></span> <span data-ttu-id="4245b-109">這個方法也可確保已部署的每個電腦都已執行 BitLocker 且設定正確。</span><span class="sxs-lookup"><span data-stu-id="4245b-109">This approach also ensures that every computer that is deployed already has BitLocker running and is configured correctly.</span></span>

**<span data-ttu-id="4245b-110">警告</span><span class="sxs-lookup"><span data-stu-id="4245b-110">Warning</span></span>**  
<span data-ttu-id="4245b-111">本主題說明如何使用 [登錄編輯程式] 變更 Windows 登錄。</span><span class="sxs-lookup"><span data-stu-id="4245b-111">This topic describes how to change the Windows registry by using Registry Editor.</span></span> <span data-ttu-id="4245b-112">如果您不正確地變更 Windows 登錄，可能會導致嚴重的問題，可能需要重新安裝 Windows。</span><span class="sxs-lookup"><span data-stu-id="4245b-112">If you change the Windows registry incorrectly, you can cause serious problems that might require you to reinstall Windows.</span></span> <span data-ttu-id="4245b-113">變更登錄前，您應該先製作一份登錄檔案（系統 .dat 和使用者 .dat）的備份複本。</span><span class="sxs-lookup"><span data-stu-id="4245b-113">You should make a backup copy of the registry files (System.dat and User.dat) before you change the registry.</span></span> <span data-ttu-id="4245b-114">Microsoft 不能保證變更註冊表時可能會發生的問題，可以解決。</span><span class="sxs-lookup"><span data-stu-id="4245b-114">Microsoft cannot guarantee that the problems that might occur when you change the registry can be resolved.</span></span> <span data-ttu-id="4245b-115">變更註冊表的風險由您自行承擔。</span><span class="sxs-lookup"><span data-stu-id="4245b-115">Change the registry at your own risk.</span></span>



**<span data-ttu-id="4245b-116">若要將電腦加密為 Windows 部署的一部分</span><span class="sxs-lookup"><span data-stu-id="4245b-116">To encrypt a computer as part of Windows deployment</span></span>**

1.  <span data-ttu-id="4245b-117">如果您的組織打算在 BitLocker 中使用受信任的平臺模組（TPM）保護器或 TPM + PIN 保護器選項，您必須先啟動 TPM 晶片，然後才能開始部署 MBAM。</span><span class="sxs-lookup"><span data-stu-id="4245b-117">If your organization plans to use the Trusted Platform Module (TPM) protector or the TPM + PIN protector options in BitLocker, you must activate the TPM chip before the initial deployment of MBAM.</span></span> <span data-ttu-id="4245b-118">當您啟用 TPM 晶片時，您會在稍後的程式中避免重新開機，並確保根據貴組織的需求正確地設定 TPM 晶片。</span><span class="sxs-lookup"><span data-stu-id="4245b-118">When you activate the TPM chip, you avoid a reboot later in the process, and you ensure that the TPM chips are correctly configured according to the requirements of your organization.</span></span> <span data-ttu-id="4245b-119">您必須在電腦的 BIOS 中手動啟用 TPM 晶片。</span><span class="sxs-lookup"><span data-stu-id="4245b-119">You must activate the TPM chip manually in the computer's BIOS.</span></span> <span data-ttu-id="4245b-120">如需有關如何設定 TPM 晶片的詳細資訊，請參閱製造商檔。</span><span class="sxs-lookup"><span data-stu-id="4245b-120">Refer to the manufacturer documentation for more details about how to configure the TPM chip.</span></span>

2.  <span data-ttu-id="4245b-121">安裝 MBAM 用戶端代理程式。</span><span class="sxs-lookup"><span data-stu-id="4245b-121">Install the MBAM client agent.</span></span>

3.  <span data-ttu-id="4245b-122">我們建議您將電腦加入網域 .。。</span><span class="sxs-lookup"><span data-stu-id="4245b-122">We recommend that you join the computer to a domain...</span></span>

    -   <span data-ttu-id="4245b-123">如果電腦未加入網域，則無法將恢復密碼儲存在 MBAM 金鑰復原服務中。</span><span class="sxs-lookup"><span data-stu-id="4245b-123">If the computer is not joined to a domain, the recovery password is not stored in the MBAM Key Recovery service.</span></span> <span data-ttu-id="4245b-124">根據預設，除非能儲存復原金鑰，否則 MBAM 不允許進行加密。</span><span class="sxs-lookup"><span data-stu-id="4245b-124">By default, MBAM does not allow encryption to occur unless the recovery key can be stored.</span></span>

    -   <span data-ttu-id="4245b-125">如果電腦在修復金鑰儲存在 MBAM 伺服器上之前以 [復原] 模式啟動，電腦必須是 reimaged。</span><span class="sxs-lookup"><span data-stu-id="4245b-125">If a computer starts in recovery mode before the recovery key is stored on the MBAM server, the computer has to be reimaged.</span></span> <span data-ttu-id="4245b-126">沒有可用的恢復方法。</span><span class="sxs-lookup"><span data-stu-id="4245b-126">No recovery method is available.</span></span>

4.  <span data-ttu-id="4245b-127">以系統管理員身分開啟命令提示字元，停止 MBAM 服務，然後將服務設定為 [**手動**] 或 [按**需**]。</span><span class="sxs-lookup"><span data-stu-id="4245b-127">Open a command prompt as an administrator, stop the MBAM service, and then set the service to **manual** or **on demand**.</span></span> <span data-ttu-id="4245b-128">然後，執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="4245b-128">Then, run the following commands:</span></span>

    **<span data-ttu-id="4245b-129">net stop mbamagent</span><span class="sxs-lookup"><span data-stu-id="4245b-129">net stop mbamagent</span></span>**

    **<span data-ttu-id="4245b-130">sc config mbamagent start = 要求</span><span class="sxs-lookup"><span data-stu-id="4245b-130">sc config mbamagent start= demand</span></span>**

5.  <span data-ttu-id="4245b-131">將 MBAM 代理程式的登錄設定設為 [忽略群組原則]，並執行**僅限作業系統加密**執行此動作、執行**regedit**，然後從 c:\\program files Files\\Microsoft\\MDOP 匯入登錄機碼範本 MBAM\\MBAMDeploymentKeyTemplate.reg。</span><span class="sxs-lookup"><span data-stu-id="4245b-131">Set the registry settings for the MBAM agent to ignore Group Policy and run the TPM for **operating system only encryption** To do this, run **regedit**, and then import the registry key template from C:\\Program Files\\Microsoft\\MDOP MBAM\\MBAMDeploymentKeyTemplate.reg.</span></span>

6.  <span data-ttu-id="4245b-132">在 regedit 中，移至 HKLM\\SOFTWARE\\Microsoft\\MBAM 並設定下表所列的設定。</span><span class="sxs-lookup"><span data-stu-id="4245b-132">In regedit, go to HKLM\\SOFTWARE\\Microsoft\\MBAM and configure the settings that are listed in the following table.</span></span>

    <span data-ttu-id="4245b-133">登錄專案</span><span class="sxs-lookup"><span data-stu-id="4245b-133">Registry entry</span></span>

    <span data-ttu-id="4245b-134">組態設定</span><span class="sxs-lookup"><span data-stu-id="4245b-134">Configuration settings</span></span>

    <span data-ttu-id="4245b-135">DeploymentTime</span><span class="sxs-lookup"><span data-stu-id="4245b-135">DeploymentTime</span></span>

    <span data-ttu-id="4245b-136">0 = 關閉</span><span class="sxs-lookup"><span data-stu-id="4245b-136">0 = OFF</span></span>

    <span data-ttu-id="4245b-137">1 = 使用部署時間原則設定（預設）</span><span class="sxs-lookup"><span data-stu-id="4245b-137">1 = Use deployment time policy settings (default)</span></span>

    <span data-ttu-id="4245b-138">UseKeyRecoveryService</span><span class="sxs-lookup"><span data-stu-id="4245b-138">UseKeyRecoveryService</span></span>

    <span data-ttu-id="4245b-139">0 = 不使用金鑰委託（在這種情況下，不需要接下來的兩個登錄專案）。</span><span class="sxs-lookup"><span data-stu-id="4245b-139">0 = Do not use key escrow (The next two registry entries are not required in this case.)</span></span>

    <span data-ttu-id="4245b-140">1 = 在金鑰還原系統中使用金鑰委託（預設）</span><span class="sxs-lookup"><span data-stu-id="4245b-140">1 = Use key escrow in Key Recovery system (default)</span></span>

    <span data-ttu-id="4245b-141">建議：電腦必須能夠與金鑰復原服務進行通訊。</span><span class="sxs-lookup"><span data-stu-id="4245b-141">Recommended: The computer must be able to communicate with the Key Recovery service.</span></span> <span data-ttu-id="4245b-142">繼續進行之前，請先確認電腦可以與服務進行通訊。</span><span class="sxs-lookup"><span data-stu-id="4245b-142">Verify that the computer can communicate with the service before you proceed.</span></span>

    <span data-ttu-id="4245b-143">KeyRecoveryOptions</span><span class="sxs-lookup"><span data-stu-id="4245b-143">KeyRecoveryOptions</span></span>

    <span data-ttu-id="4245b-144">0 = 僅上傳復原金鑰</span><span class="sxs-lookup"><span data-stu-id="4245b-144">0 = Upload Recovery Key Only</span></span>

    <span data-ttu-id="4245b-145">1 = 上傳復原金鑰和金鑰復原套件（預設）</span><span class="sxs-lookup"><span data-stu-id="4245b-145">1 = Upload Recovery Key and Key Recovery Package (default)</span></span>

    <span data-ttu-id="4245b-146">KeyRecoveryServiceEndPoint</span><span class="sxs-lookup"><span data-stu-id="4245b-146">KeyRecoveryServiceEndPoint</span></span>

    <span data-ttu-id="4245b-147">將此值設定為金鑰復原網頁伺服器的 URL。</span><span class="sxs-lookup"><span data-stu-id="4245b-147">Set this value to the URL for the Key Recovery web server.</span></span>

    <span data-ttu-id="4245b-148">範例： HTTP:// &lt; 電腦名稱稱 &gt; /MBAMRecoveryAndHardwareService/CoreService.svc。</span><span class="sxs-lookup"><span data-stu-id="4245b-148">Example: http://&lt;computer name&gt;/MBAMRecoveryAndHardwareService/CoreService.svc.</span></span>



~~~
**Note**  
MBAM policy or registry values can be set here to override the previously set values.
~~~



7. <span data-ttu-id="4245b-149">MBAM agent 會在 MBAM 用戶端部署期間重新開機系統。</span><span class="sxs-lookup"><span data-stu-id="4245b-149">The MBAM agent restarts the system during MBAM client deployment.</span></span> <span data-ttu-id="4245b-150">當您準備好進行此重新開機時，請以系統管理員的命令提示字元執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="4245b-150">When you are ready for this reboot, run the following command at a command prompt as an administrator:</span></span>

   **<span data-ttu-id="4245b-151">net start mbamagent</span><span class="sxs-lookup"><span data-stu-id="4245b-151">net start mbamagent</span></span>**

8. <span data-ttu-id="4245b-152">當電腦重新開機且 BIOS 提示您接受 TPM 變更時，請接受變更。</span><span class="sxs-lookup"><span data-stu-id="4245b-152">When the computers restarts and the BIOS prompts you to accept a TPM change, accept the change.</span></span>

9. <span data-ttu-id="4245b-153">在 Windows 用戶端作業系統影像處理常式中，當您準備好要開始加密時，請重新開機 MBAM 代理服務。</span><span class="sxs-lookup"><span data-stu-id="4245b-153">During the Windows client operating system imaging process, when you are ready to start encryption, restart the MBAM agent service.</span></span> <span data-ttu-id="4245b-154">接著，若要將 [開始] 設定為 [**自動**]，請以系統管理員身分開啟命令提示字元，並執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="4245b-154">Then, to set start to **automatic**, open a command prompt as an administrator and run the following commands:</span></span>

   **<span data-ttu-id="4245b-155">sc config mbamagent start = auto</span><span class="sxs-lookup"><span data-stu-id="4245b-155">sc config mbamagent start= auto</span></span>**

   **<span data-ttu-id="4245b-156">net start mbamagent</span><span class="sxs-lookup"><span data-stu-id="4245b-156">net start mbamagent</span></span>**

10. <span data-ttu-id="4245b-157">移除 [旁路] 註冊表值。</span><span class="sxs-lookup"><span data-stu-id="4245b-157">Remove the bypass registry values.</span></span> <span data-ttu-id="4245b-158">若要這樣做，請執行 regedit，流覽至 HKLM\\SOFTWARE\\Microsoft 登錄專案，以滑鼠右鍵按一下 [ **MBAM** ] 節點，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="4245b-158">To do this, run regedit, browse to the HKLM\\SOFTWARE\\Microsoft registry entry, right-click the **MBAM** node, and then click **Delete**.</span></span>

## <span data-ttu-id="4245b-159">相關主題</span><span class="sxs-lookup"><span data-stu-id="4245b-159">Related topics</span></span>


[<span data-ttu-id="4245b-160">部署 MBAM 1.0 用戶端</span><span class="sxs-lookup"><span data-stu-id="4245b-160">Deploying the MBAM 1.0 Client</span></span>](deploying-the-mbam-10-client.md)









