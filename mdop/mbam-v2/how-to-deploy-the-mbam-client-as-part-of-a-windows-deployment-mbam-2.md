---
title: 如何將 MBAM 用戶端部署為 Windows 部署的一部分
description: 如何將 MBAM 用戶端部署為 Windows 部署的一部分
author: dansimp
ms.assetid: 67387de7-8b02-4412-9850-3b8d8e5c18af
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d75e5748167d2d4866f98e9d3611584067ecd418
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810665"
---
# <span data-ttu-id="a22ef-103">如何將 MBAM 用戶端部署為 Windows 部署的一部分</span><span class="sxs-lookup"><span data-stu-id="a22ef-103">How to Deploy the MBAM Client as Part of a Windows Deployment</span></span>


<span data-ttu-id="a22ef-104">Microsoft BitLocker 管理和監控（MBAM）用戶端可讓系統管理員在企業中的電腦上強制執行及監視 BitLocker 磁片磁碟機加密。</span><span class="sxs-lookup"><span data-stu-id="a22ef-104">The Microsoft BitLocker Administration and Monitoring (MBAM) Client enables administrators to enforce and monitor BitLocker drive encryption on computers in the enterprise.</span></span> <span data-ttu-id="a22ef-105">如果有受信任的平臺模組（TPM）晶片的電腦，則可在用戶端電腦上啟用 BitLocker 管理和加密等，將 BitLocker 用戶端整合到組織中。</span><span class="sxs-lookup"><span data-stu-id="a22ef-105">If computers that have a Trusted Platform Module (TPM) chip, the BitLocker client can be integrated into an organization by enabling BitLocker management and encryption on client computers as part of the imaging and Windows deployment process.</span></span>

**<span data-ttu-id="a22ef-106">注意</span><span class="sxs-lookup"><span data-stu-id="a22ef-106">Note</span></span>**  
<span data-ttu-id="a22ef-107">若要查看 Microsoft BitLocker 管理及監視用戶端系統需求，請參閱[MBAM 2.0 支援](mbam-20-supported-configurations-mbam-2.md)的設定。</span><span class="sxs-lookup"><span data-stu-id="a22ef-107">To review the Microsoft BitLocker Administration and Monitoring Client system requirements, see [MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md).</span></span>



<span data-ttu-id="a22ef-108">在 Windows 部署的初始影像階段中使用 BitLocker 加密用戶端電腦，可以降低在組織中執行 MBAM 所需的管理負荷。</span><span class="sxs-lookup"><span data-stu-id="a22ef-108">Encrypting client computers with BitLocker during the initial imaging stage of a Windows deployment can lower the administrative overhead necessary for implementing MBAM in an organization.</span></span> <span data-ttu-id="a22ef-109">它也可確保已部署的每個電腦都已執行 BitLocker 且設定正確。</span><span class="sxs-lookup"><span data-stu-id="a22ef-109">It also ensures that every computer that is deployed already has BitLocker running and is configured correctly.</span></span>

**<span data-ttu-id="a22ef-110">注意</span><span class="sxs-lookup"><span data-stu-id="a22ef-110">Note</span></span>**  
<span data-ttu-id="a22ef-111">本主題中的程式說明如何修改 Windows 註冊。</span><span class="sxs-lookup"><span data-stu-id="a22ef-111">The procedure in this topic describes modifying the Windows registry.</span></span> <span data-ttu-id="a22ef-112">無法正確使用登錄編輯程式，可能會導致嚴重問題，可能需要重新安裝 Windows。</span><span class="sxs-lookup"><span data-stu-id="a22ef-112">Using Registry Editor incorrectly can cause serious problems that may require you to reinstall Windows.</span></span> <span data-ttu-id="a22ef-113">Microsoft 無法保證無法正確使用登錄編輯程式所造成的問題，因此無法解決。</span><span class="sxs-lookup"><span data-stu-id="a22ef-113">Microsoft cannot guarantee that problems resulting from the incorrect use of Registry Editor can be solved.</span></span> <span data-ttu-id="a22ef-114">使用登錄編輯程式的風險由您自負。</span><span class="sxs-lookup"><span data-stu-id="a22ef-114">Use Registry Editor at your own risk.</span></span>



**<span data-ttu-id="a22ef-115">若要將電腦加密為 Windows 部署的一部分</span><span class="sxs-lookup"><span data-stu-id="a22ef-115">To encrypt a computer as part of Windows deployment</span></span>**

1.  <span data-ttu-id="a22ef-116">如果您的組織打算在 BitLocker 中使用受信任的平臺模組（TPM）保護器或 TPM + PIN 保護器選項，您必須先啟動 TPM 晶片，然後才能開始部署 MBAM。</span><span class="sxs-lookup"><span data-stu-id="a22ef-116">If your organization is planning to use the Trusted Platform Module (TPM) protector or the TPM + PIN protector options in BitLocker, you must activate the TPM chip before the initial deployment of MBAM.</span></span> <span data-ttu-id="a22ef-117">當您啟用 TPM 晶片時，您會在稍後的程式中避免重新開機，並確保根據貴組織的需求正確地設定 TPM 晶片。</span><span class="sxs-lookup"><span data-stu-id="a22ef-117">When you activate the TPM chip, you avoid a reboot later in the process, and you ensure that the TPM chips are correctly configured according to the requirements of your organization.</span></span> <span data-ttu-id="a22ef-118">您必須在電腦的 BIOS 中手動啟用 TPM 晶片。</span><span class="sxs-lookup"><span data-stu-id="a22ef-118">You must activate the TPM chip manually in the BIOS of the computer.</span></span>

    **<span data-ttu-id="a22ef-119">注意</span><span class="sxs-lookup"><span data-stu-id="a22ef-119">Note</span></span>**  
    <span data-ttu-id="a22ef-120">某些廠商提供的工具可在作業系統中從 BIOS 開啟及啟動 TPM 晶片。</span><span class="sxs-lookup"><span data-stu-id="a22ef-120">Some vendors provide tools to turn on and activate the TPM chip in the BIOS from within the operating system.</span></span> <span data-ttu-id="a22ef-121">如需有關如何設定 TPM 晶片的詳細資訊，請參閱製造商檔。</span><span class="sxs-lookup"><span data-stu-id="a22ef-121">Refer to the manufacturer documentation for more details about how to configure the TPM chip.</span></span>



2.  <span data-ttu-id="a22ef-122">安裝 Microsoft BitLocker 管理及監視用戶端代理程式。</span><span class="sxs-lookup"><span data-stu-id="a22ef-122">Install the Microsoft BitLocker Administration and Monitoring client agent.</span></span>

3.  <span data-ttu-id="a22ef-123">將電腦加入網域（建議使用）。</span><span class="sxs-lookup"><span data-stu-id="a22ef-123">Join the computer to a domain (recommended).</span></span>

    -   <span data-ttu-id="a22ef-124">如果電腦未加入網域，則無法將恢復密碼儲存在 MBAM 金鑰復原服務中。</span><span class="sxs-lookup"><span data-stu-id="a22ef-124">If the computer is not joined to the domain, the recovery password is not stored in the MBAM Key Recovery service.</span></span> <span data-ttu-id="a22ef-125">根據預設，除非能儲存復原金鑰，否則 MBAM 不允許進行加密。</span><span class="sxs-lookup"><span data-stu-id="a22ef-125">By default, MBAM does not allow encryption to occur unless the recovery key can be stored.</span></span>

    -   <span data-ttu-id="a22ef-126">如果電腦在修復金鑰儲存在 MBAM 伺服器上之前以 [復原] 模式啟動，電腦必須是 reimaged。</span><span class="sxs-lookup"><span data-stu-id="a22ef-126">If a computer starts in recovery mode before the recovery key is stored on the MBAM Server, the computer has to be reimaged.</span></span> <span data-ttu-id="a22ef-127">沒有可用的恢復方法。</span><span class="sxs-lookup"><span data-stu-id="a22ef-127">No recovery method is available.</span></span>

4.  <span data-ttu-id="a22ef-128">以系統管理員身分執行命令提示字元、停止 MBAM 服務，然後將服務設定為 [**手動**] 或 [**按需**]，然後輸入下列命令：</span><span class="sxs-lookup"><span data-stu-id="a22ef-128">Run the command prompt as an administrator, stop the MBAM service, and then set the service to **manual** or **on demand**, and then start by typing the following commands:</span></span>

    **<span data-ttu-id="a22ef-129">net stop mbamagent</span><span class="sxs-lookup"><span data-stu-id="a22ef-129">net stop mbamagent</span></span>**

    **<span data-ttu-id="a22ef-130">sc config mbamagent start = 要求</span><span class="sxs-lookup"><span data-stu-id="a22ef-130">sc config mbamagent start= demand</span></span>**

5.  <span data-ttu-id="a22ef-131">將 MBAM agent 的登錄設定設為 [忽略群組原則]，並執行電腦版 TPM，**只**需執行**Regedit**，然後從 c:\\program files Files\\Microsoft\\MDOP 匯入登錄機碼範本 MBAM\\MBAMDeploymentKeyTemplate.reg。</span><span class="sxs-lookup"><span data-stu-id="a22ef-131">Set the registry settings for the MBAM agent to ignore Group Policy and run the TPM for **operating system only encryption** by running **Regedit**, and then importing the registry key template from C:\\Program Files\\Microsoft\\MDOP MBAM\\MBAMDeploymentKeyTemplate.reg.</span></span>

6.  <span data-ttu-id="a22ef-132">在 regedit 中，移至 HKLM\\SOFTWARE\\Microsoft\\MBAM，並設定下表所列的設定。</span><span class="sxs-lookup"><span data-stu-id="a22ef-132">In regedit, go to HKLM\\SOFTWARE\\Microsoft\\MBAM, and configure the settings that are listed in the following table.</span></span>

    <span data-ttu-id="a22ef-133">登錄專案</span><span class="sxs-lookup"><span data-stu-id="a22ef-133">Registry entry</span></span>

    <span data-ttu-id="a22ef-134">組態設定</span><span class="sxs-lookup"><span data-stu-id="a22ef-134">Configuration settings</span></span>

    <span data-ttu-id="a22ef-135">DeploymentTime</span><span class="sxs-lookup"><span data-stu-id="a22ef-135">DeploymentTime</span></span>

    <span data-ttu-id="a22ef-136">0 = 關閉</span><span class="sxs-lookup"><span data-stu-id="a22ef-136">0 = OFF</span></span>

    <span data-ttu-id="a22ef-137">1 = 使用部署時間原則設定（預設）</span><span class="sxs-lookup"><span data-stu-id="a22ef-137">1 = Use deployment time policy settings (default)</span></span>

    <span data-ttu-id="a22ef-138">UseKeyRecoveryService</span><span class="sxs-lookup"><span data-stu-id="a22ef-138">UseKeyRecoveryService</span></span>

    <span data-ttu-id="a22ef-139">0 = 不使用金鑰保管（這種情況下，不需要接下來的兩個登錄專案）</span><span class="sxs-lookup"><span data-stu-id="a22ef-139">0 = Do not use key escrow ( the next two registry entries are not required in this case)</span></span>

    <span data-ttu-id="a22ef-140">1 = 在金鑰還原系統中使用金鑰委託（預設）</span><span class="sxs-lookup"><span data-stu-id="a22ef-140">1 = Use key escrow in Key Recovery system (default)</span></span>

    <span data-ttu-id="a22ef-141">建議：電腦必須能夠與金鑰復原服務進行通訊。</span><span class="sxs-lookup"><span data-stu-id="a22ef-141">Recommended: The computer must be able to communicate with the Key Recovery service.</span></span> <span data-ttu-id="a22ef-142">繼續進行之前，請先確認電腦可以與服務進行通訊。</span><span class="sxs-lookup"><span data-stu-id="a22ef-142">Verify that the computer can communicate with the service before you proceed.</span></span>

    <span data-ttu-id="a22ef-143">KeyRecoveryOptions</span><span class="sxs-lookup"><span data-stu-id="a22ef-143">KeyRecoveryOptions</span></span>

    <span data-ttu-id="a22ef-144">0 = 僅限上傳復原金鑰</span><span class="sxs-lookup"><span data-stu-id="a22ef-144">0 = Uploads Recovery Key Only</span></span>

    <span data-ttu-id="a22ef-145">1 = 上傳復原金鑰和金鑰復原套件（預設）</span><span class="sxs-lookup"><span data-stu-id="a22ef-145">1 = Uploads Recovery Key and Key Recovery Package (default)</span></span>

    <span data-ttu-id="a22ef-146">KeyRecoveryServiceEndPoint</span><span class="sxs-lookup"><span data-stu-id="a22ef-146">KeyRecoveryServiceEndPoint</span></span>

    <span data-ttu-id="a22ef-147">將此值設定為金鑰復原網頁伺服器的 URL，例如，HTTP://[ &lt; 電腦名稱稱] &gt; /MBAMRecoveryAndHardwareService/CoreService.svc。</span><span class="sxs-lookup"><span data-stu-id="a22ef-147">Set this value to the URL for the Key Recovery web server, for example, http://&lt;computer name&gt;/MBAMRecoveryAndHardwareService/CoreService.svc.</span></span>



~~~
**Note**  
MBAM policy or registry values can be set here to override previously set values.
~~~



7. <span data-ttu-id="a22ef-148">MBAM agent 會在 MBAM 用戶端部署期間重新開機系統。</span><span class="sxs-lookup"><span data-stu-id="a22ef-148">The MBAM agent restarts the system during MBAM client deployment.</span></span> <span data-ttu-id="a22ef-149">當您準備好進行此重新開機時，請以系統管理員的命令提示字元執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="a22ef-149">When you are ready for this reboot, run the following command at a command prompt as an administrator:</span></span>

   **<span data-ttu-id="a22ef-150">net start mbamagent</span><span class="sxs-lookup"><span data-stu-id="a22ef-150">net start mbamagent</span></span>**

8. <span data-ttu-id="a22ef-151">當電腦重新開機且 BIOS 提示您接受 TPM 變更時，請接受變更。</span><span class="sxs-lookup"><span data-stu-id="a22ef-151">When the computers restarts, and the BIOS prompts you to accept a TPM change, accept the change.</span></span>

9. <span data-ttu-id="a22ef-152">在 Windows 用戶端作業系統影像程式期間，當您準備好要開始加密時，請重新開機 MBAM agent 服務，並將命令提示字元設為系統管理員，然後輸入下列命令，以將 [開始] 設定為 [**自動**]：</span><span class="sxs-lookup"><span data-stu-id="a22ef-152">During the Windows client operating system imaging process, when you are ready to start encryption, restart the MBAM agent service, and set start to **automatic** by running a command prompt as an administrator and typing the following commands:</span></span>

   **<span data-ttu-id="a22ef-153">sc config mbamagent start = auto</span><span class="sxs-lookup"><span data-stu-id="a22ef-153">sc config mbamagent start= auto</span></span>**

   **<span data-ttu-id="a22ef-154">net start mbamagent</span><span class="sxs-lookup"><span data-stu-id="a22ef-154">net start mbamagent</span></span>**

10. <span data-ttu-id="a22ef-155">執行 Regedit 並移至 HKLM\\SOFTWARE\\Microsoft 登錄專案，以移除旁路登錄值。</span><span class="sxs-lookup"><span data-stu-id="a22ef-155">Remove the bypass registry values by running Regedit and going to the HKLM\\SOFTWARE\\Microsoft registry entry.</span></span> <span data-ttu-id="a22ef-156">若要刪除**MBAM**節點，請以滑鼠右鍵按一下節點，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="a22ef-156">To delete the **MBAM** node, right-click the node and click **Delete**.</span></span>

## <span data-ttu-id="a22ef-157">相關主題</span><span class="sxs-lookup"><span data-stu-id="a22ef-157">Related topics</span></span>


[<span data-ttu-id="a22ef-158">部署 MBAM 2.0 用戶端</span><span class="sxs-lookup"><span data-stu-id="a22ef-158">Deploying the MBAM 2.0 Client</span></span>](deploying-the-mbam-20-client-mbam-2.md)









