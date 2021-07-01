---
title: 如何使用 MBAM 做為 Windows 部署的一部分來啟用 BitLocker
description: 如何使用 MBAM 做為 Windows 部署的一部分來啟用 BitLocker
author: dansimp
ms.assetid: 7609ad7a-bb06-47be-b186-0a2db787c8a5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 04/23/2017
ms.openlocfilehash: cd4086ca6bb2ea8d253ea3b743f4efe7efbbb6c1
ms.sourcegitcommit: 325c4b77f9a9df0f3de268457fed06184623bb94
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/30/2021
ms.locfileid: "11626180"
---
# <a name="how-to-enable-bitlocker-by-using-mbam-as-part-of-a-windows-deployment"></a><span data-ttu-id="5411d-103">如何使用 MBAM 做為 Windows 部署的一部分來啟用 BitLocker</span><span class="sxs-lookup"><span data-stu-id="5411d-103">How to Enable BitLocker by Using MBAM as Part of a Windows Deployment</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5411d-104">這些指示與 Configuration Manager BitLocker 管理並不相關。</span><span class="sxs-lookup"><span data-stu-id="5411d-104">These instructions do not pertain to Configuration Manager BitLocker Management.</span></span> <span data-ttu-id="5411d-105">`Invoke-MbamClientDeployment.ps1`PowerShell 腳本不支援在 Configuration Manager 中與 BitLocker Management 一起使用。</span><span class="sxs-lookup"><span data-stu-id="5411d-105">The `Invoke-MbamClientDeployment.ps1` PowerShell script is not supported for use with BitLocker Management in Configuration Manager.</span></span> <span data-ttu-id="5411d-106">這包括在 Configuration Manager 工作順序期間代管 BitLocker 修復金鑰。</span><span class="sxs-lookup"><span data-stu-id="5411d-106">This includes escrowing of BitLocker recovery keys during a Configuration Manager task sequence.</span></span> <span data-ttu-id="5411d-107">此外，從 Configuration Manager Current Branch 2103 開始，Configuration Manager BitLocker Management 就不會再使用<a0></a0>的 <<a1></a1><a2>：</a2><a3></a3><a4></a4><a5>：</a5> <a6> </a6> <a7> </a7></span><span class="sxs-lookup"><span data-stu-id="5411d-107">Furthermore, starting with Configuration Manager Current Branch 2103, Configuration Manager BitLocker Management no longer uses the MBAM key recovery services site to escrow keys.</span></span> <span data-ttu-id="5411d-108">嘗試在 Configuration Manager Current Branch 2103 或更新版本使用 PowerShell 腳本可能會導致 `Invoke-MbamClientDeployment.ps1` Configuration Manager 網站發生嚴重問題。</span><span class="sxs-lookup"><span data-stu-id="5411d-108">Attempting to use the `Invoke-MbamClientDeployment.ps1` PowerShell script with Configuration Manager Current Branch 2103 or newer can result in serious problems with the Configuration Manager site.</span></span> <span data-ttu-id="5411d-109">已知問題包括建立大量針對所有裝置的策略，可能會導致策略暴風。</span><span class="sxs-lookup"><span data-stu-id="5411d-109">Known problems include creation of a large amount of policy targeted to all devices which can cause policy storms.</span></span> <span data-ttu-id="5411d-110">這會在 Configuration Manager 中導致主要在管理點SQL的績效嚴重降低。</span><span class="sxs-lookup"><span data-stu-id="5411d-110">This will lead to severe degradation of performance in Configuration Manager primarily in SQL and with Management Points.</span></span>

<span data-ttu-id="5411d-111">本主題說明如何在使用者電腦上啟用 BitLocker，在影像和部署過程中，使用 WINDOWS的一部分。</span><span class="sxs-lookup"><span data-stu-id="5411d-111">This topic explains how to enable BitLocker on an end user's computer by using MBAM as part of your Windows imaging and deployment process.</span></span> <span data-ttu-id="5411d-112">如果您在安裝階段結束) 之後重新開機 (時看到黑色螢幕，表示無法解除鎖定硬碟，請參閱先前 Windows 版本在 「設定 Windows 和 Configuration Manager」步驟之後，如果預布布位 BitLocker 已與 Windows 10 版本[1511](https://support.microsoft.com/en-us/help/4494799/earlier-windows-versions-don-t-start-after-you-use-pre-provision-bitlo)一起使用，請參閱先前 Windows 版本不會啟動。</span><span class="sxs-lookup"><span data-stu-id="5411d-112">If you see a black screen at restart (after Install phase concludes) indicating that the drive cannot be unlocked, see [Earlier Windows versions don't start after "Setup Windows and Configuration Manager" step if Pre-Provision BitLocker is used with Windows 10, version 1511](https://support.microsoft.com/en-us/help/4494799/earlier-windows-versions-don-t-start-after-you-use-pre-provision-bitlo).</span></span>

**<span data-ttu-id="5411d-113">必要條件：</span><span class="sxs-lookup"><span data-stu-id="5411d-113">Prerequisites:</span></span>**

-   <span data-ttu-id="5411d-114">必須Windows現有的映射部署程式 ：Microsoft 部署工具組 (MDT) 、Microsoft System Center Configuration Manager 或其他影像工具或程式</span><span class="sxs-lookup"><span data-stu-id="5411d-114">An existing Windows image deployment process – Microsoft Deployment Toolkit (MDT), Microsoft System Center Configuration Manager, or some other imaging tool or process – must be in place</span></span>

-   <span data-ttu-id="5411d-115">TPM 必須在BIOS 中啟用，且對作業系統可見</span><span class="sxs-lookup"><span data-stu-id="5411d-115">TPM must be enabled in the BIOS and visible to the OS</span></span>

-   <span data-ttu-id="5411d-116">必須就地且易於訪問的 IBMM 伺服器基礎結構</span><span class="sxs-lookup"><span data-stu-id="5411d-116">MBAM server infrastructure must be in place and accessible</span></span>

-   <span data-ttu-id="5411d-117">必須建立 BitLocker 所需的系統磁碟分割</span><span class="sxs-lookup"><span data-stu-id="5411d-117">The system partition required by BitLocker must be created</span></span>

-   <span data-ttu-id="5411d-118">電腦在映射處理期間必須先加入網域，然後才完全啟用 BITLocker</span><span class="sxs-lookup"><span data-stu-id="5411d-118">The machine must be domain joined during imaging before MBAM fully enables BitLocker</span></span>

**<span data-ttu-id="5411d-119">若要在部署中啟用 BITLocker，在部署時使用 WINDOWS 2.5 SP1</span><span class="sxs-lookup"><span data-stu-id="5411d-119">To enable BitLocker using MBAM 2.5 SP1 as part of a Windows deployment</span></span>**

1. <span data-ttu-id="5411d-120">在 2.5 SP1 中，建議在部署期間啟用 BitLocker Windows使用 `Invoke-MbamClientDeployment.ps1` PowerShell 腳本。</span><span class="sxs-lookup"><span data-stu-id="5411d-120">In MBAM 2.5 SP1, the recommended approach to enable BitLocker during a Windows Deployment is by using the `Invoke-MbamClientDeployment.ps1` PowerShell script.</span></span>

   -   <span data-ttu-id="5411d-121">腳本 `Invoke-MbamClientDeployment.ps1` 在映射程式期間會啟動 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="5411d-121">The `Invoke-MbamClientDeployment.ps1` script enacts BitLocker during the imaging process.</span></span> <span data-ttu-id="5411d-122">當 BitLocker 策略有需要時，當網域使用者第一次在映射後登錄時，該網域使用者會立即提示網域使用者建立 PIN 或密碼。</span><span class="sxs-lookup"><span data-stu-id="5411d-122">When required by BitLocker policy, the MBAM agent immediately prompts the domain user to create a PIN or password when the domain user first logs on after imaging.</span></span>

   -   <span data-ttu-id="5411d-123">輕鬆與 MDT、System Center Configuration Manager或獨立影像程式一起使用</span><span class="sxs-lookup"><span data-stu-id="5411d-123">Easy to use with MDT, System Center Configuration Manager, or standalone imaging processes</span></span>

   -   <span data-ttu-id="5411d-124">與 PowerShell 2.0 或更高版本相容</span><span class="sxs-lookup"><span data-stu-id="5411d-124">Compatible with PowerShell 2.0 or higher</span></span>

   -   <span data-ttu-id="5411d-125">使用 TPM 金鑰保護裝置加密作業系統音量</span><span class="sxs-lookup"><span data-stu-id="5411d-125">Encrypt OS volume with TPM key protector</span></span>

   -   <span data-ttu-id="5411d-126">完全支援 BitLocker 預置備</span><span class="sxs-lookup"><span data-stu-id="5411d-126">Fully support BitLocker pre-provisioning</span></span>

   -   <span data-ttu-id="5411d-127">選擇性加密 FDD</span><span class="sxs-lookup"><span data-stu-id="5411d-127">Optionally encrypt FDDs</span></span>

   -   <span data-ttu-id="5411d-128">針對第 7 Windows代管 TPM 擁有者驗證，PMM 必須擁有 TPM 以代管。</span><span class="sxs-lookup"><span data-stu-id="5411d-128">Escrow TPM OwnerAuth For Windows 7, MBAM must own the TPM for escrow to occur.</span></span>
   <span data-ttu-id="5411d-129">對於 Windows 8.1，Windows 10 RTM Windows 10版本 1511，支援代管 TPM OwnerAuth。</span><span class="sxs-lookup"><span data-stu-id="5411d-129">For Windows 8.1, Windows 10 RTM and Windows 10 version 1511, escrow of TPM OwnerAuth is supported.</span></span>
   <span data-ttu-id="5411d-130">對於 Windows 10版本 1607 或更新版本，Windows才能取得 TPM 的擁有權。</span><span class="sxs-lookup"><span data-stu-id="5411d-130">For Windows 10, version 1607 or later, only Windows can take ownership of the TPM.</span></span> <span data-ttu-id="5411d-131">在 addiiton 中Windows在配置 TPM 時，不會保留 TPM 擁有者密碼。</span><span class="sxs-lookup"><span data-stu-id="5411d-131">In addiiton, Windows will not retain the TPM owner password when provisioning the TPM.</span></span> <span data-ttu-id="5411d-132">請參閱 [TPM 擁有者密碼以](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password) 進一步詳細資料。</span><span class="sxs-lookup"><span data-stu-id="5411d-132">See [TPM owner password](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password) for further details.</span></span>

   -   <span data-ttu-id="5411d-133">代管修復金鑰及修復金鑰套件</span><span class="sxs-lookup"><span data-stu-id="5411d-133">Escrow recovery keys and recovery key packages</span></span>

   -   <span data-ttu-id="5411d-134">立即報告加密狀態</span><span class="sxs-lookup"><span data-stu-id="5411d-134">Report encryption status immediately</span></span>

   -   <span data-ttu-id="5411d-135">新的 WMI 提供者</span><span class="sxs-lookup"><span data-stu-id="5411d-135">New WMI providers</span></span>

   -   <span data-ttu-id="5411d-136">詳細記錄</span><span class="sxs-lookup"><span data-stu-id="5411d-136">Detailed logging</span></span>

   -   <span data-ttu-id="5411d-137">強大的錯誤處理</span><span class="sxs-lookup"><span data-stu-id="5411d-137">Robust error handling</span></span>

   <span data-ttu-id="5411d-138">您可以從下載中心 `Invoke-MbamClientDeployment.ps1` 下載 [Microsoft.com 腳本](https://www.microsoft.com/download/details.aspx?id=54439)。</span><span class="sxs-lookup"><span data-stu-id="5411d-138">You can download the `Invoke-MbamClientDeployment.ps1` script from [Microsoft.com Download Center](https://www.microsoft.com/download/details.aspx?id=54439).</span></span> <span data-ttu-id="5411d-139">這是部署系統會撥打的主要腳本，以設定 BitLocker 磁片磁碟機加密，以及使用 IBMM Server 記錄復原金鑰。</span><span class="sxs-lookup"><span data-stu-id="5411d-139">This is the main script that your deployment system will call to configure BitLocker drive encryption and record recovery keys with the MBAM Server.</span></span>

   <span data-ttu-id="5411d-140">**適用于 MMI 的 WMI 部署方法：** 下列 WMI 方法已新增到 ：在 2.5 SP1 中，以支援使用 PowerShell 腳本啟用 `Invoke-MbamClientDeployment.ps1` BitLocker。</span><span class="sxs-lookup"><span data-stu-id="5411d-140">**WMI deployment methods for MBAM:** The following WMI methods have been added in MBAM 2.5 SP1 to support enabling BitLocker by using the `Invoke-MbamClientDeployment.ps1` PowerShell script.</span></span>

   <a href="" id="mbam-machine-wmi-class"></a><span data-ttu-id="5411d-141">**在 WMI 課程_MACHINE管理課程** 
   **PrepareTpmAndEscrowOwnerAuth：** 讀取 TPM OwnerAuth，然後使用 PMM 修復服務將其傳送至 PMM 修復資料庫。</span><span class="sxs-lookup"><span data-stu-id="5411d-141">**MBAM\_Machine WMI Class**
**PrepareTpmAndEscrowOwnerAuth:** Reads the TPM OwnerAuth and sends it to the MBAM recovery database by using the MBAM recovery service.</span></span> <span data-ttu-id="5411d-142">如果 TPM 未擁有，且未啟動自動置備，則會產生 TPM OwnerAuth 並取得擁有權。</span><span class="sxs-lookup"><span data-stu-id="5411d-142">If the TPM is not owned and auto-provisioning is not on, it generates a TPM OwnerAuth and takes ownership.</span></span> <span data-ttu-id="5411d-143">如果失敗，會返回錯誤碼以進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="5411d-143">If it fails, an error code is returned for troubleshooting.</span></span>

   <span data-ttu-id="5411d-144">**附注**對於 Windows 10版本 1607 或更新版本，Windows才能取得 TPM 的擁有權。</span><span class="sxs-lookup"><span data-stu-id="5411d-144">**Note** For Windows 10, version 1607 or later, only Windows can take ownership of the TPM.</span></span> <span data-ttu-id="5411d-145">在 addiiton 中Windows在配置 TPM 時，不會保留 TPM 擁有者密碼。</span><span class="sxs-lookup"><span data-stu-id="5411d-145">In addiiton, Windows will not retain the TPM owner password when provisioning the TPM.</span></span> <span data-ttu-id="5411d-146">請參閱 [TPM 擁有者密碼以](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password) 進一步詳細資料。</span><span class="sxs-lookup"><span data-stu-id="5411d-146">See [TPM owner password](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password) for further details.</span></span>

| <span data-ttu-id="5411d-147">參數</span><span class="sxs-lookup"><span data-stu-id="5411d-147">Parameter</span></span> | <span data-ttu-id="5411d-148">描述</span><span class="sxs-lookup"><span data-stu-id="5411d-148">Description</span></span> |
| -------- | ----------- |
| <span data-ttu-id="5411d-149">RecoveryServiceEndPoint</span><span class="sxs-lookup"><span data-stu-id="5411d-149">RecoveryServiceEndPoint</span></span> | <span data-ttu-id="5411d-150">指定 ：指定此為 ：：一個字串，用於指定一個服務端點。</span><span class="sxs-lookup"><span data-stu-id="5411d-150">A string specifying the MBAM recovery service endpoint.</span></span> |

<span data-ttu-id="5411d-151">以下是常見錯誤訊息的清單：</span><span class="sxs-lookup"><span data-stu-id="5411d-151">Here are a list of common error messages:</span></span>

| <span data-ttu-id="5411d-152">常見的退貨值</span><span class="sxs-lookup"><span data-stu-id="5411d-152">Common return values</span></span> | <span data-ttu-id="5411d-153">錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="5411d-153">Error message</span></span> |
| -------------------- | ------------- |
|  **<span data-ttu-id="5411d-154">S_OK</span><span class="sxs-lookup"><span data-stu-id="5411d-154">S_OK</span></span>**<br /><span data-ttu-id="5411d-155">0 (0x0) </span><span class="sxs-lookup"><span data-stu-id="5411d-155">0 (0x0)</span></span> | <span data-ttu-id="5411d-156">方法已成功。</span><span class="sxs-lookup"><span data-stu-id="5411d-156">The method was successful.</span></span> |
| **<span data-ttu-id="5411d-157">MBAM_E_TPM_NOT_PRESENT</span><span class="sxs-lookup"><span data-stu-id="5411d-157">MBAM_E_TPM_NOT_PRESENT</span></span>**<br /><span data-ttu-id="5411d-158">2147746304 (0x80040200) </span><span class="sxs-lookup"><span data-stu-id="5411d-158">2147746304 (0x80040200)</span></span> | <span data-ttu-id="5411d-159">TPM 不在電腦中，或是在BIOS 組組中停用。</span><span class="sxs-lookup"><span data-stu-id="5411d-159">TPM is not present in the computer or is disabled in the BIOS configuration.</span></span> |
| **<span data-ttu-id="5411d-160">MBAM_E_TPM_INCORRECT_STATE</span><span class="sxs-lookup"><span data-stu-id="5411d-160">MBAM_E_TPM_INCORRECT_STATE</span></span>**<br /><span data-ttu-id="5411d-161">2147746305 (0x80040201) </span><span class="sxs-lookup"><span data-stu-id="5411d-161">2147746305 (0x80040201)</span></span> | <span data-ttu-id="5411d-162">TPM 在啟用、啟用 (且允許擁有者安裝時) 。</span><span class="sxs-lookup"><span data-stu-id="5411d-162">TPM is not in the correct state (enabled, activated and owner installation allowed).</span></span> |
| **<span data-ttu-id="5411d-163">MBAM_E_TPM_AUTO_PROVISIONING_PENDING</span><span class="sxs-lookup"><span data-stu-id="5411d-163">MBAM_E_TPM_AUTO_PROVISIONING_PENDING</span></span>**<br /><span data-ttu-id="5411d-164">2147746306 (0x80040202) </span><span class="sxs-lookup"><span data-stu-id="5411d-164">2147746306 (0x80040202)</span></span> | <span data-ttu-id="5411d-165">由於自動置備擱置中，因此，PMM 無法取得 TPM 的擁有權。</span><span class="sxs-lookup"><span data-stu-id="5411d-165">MBAM cannot take ownership of TPM because auto-provisioning is pending.</span></span> <span data-ttu-id="5411d-166">完成自動置備之後，請再試一次。</span><span class="sxs-lookup"><span data-stu-id="5411d-166">Try again after auto-provisioning is completed.</span></span> |
| **<span data-ttu-id="5411d-167">MBAM_E_TPM_OWNERAUTH_READFAIL</span><span class="sxs-lookup"><span data-stu-id="5411d-167">MBAM_E_TPM_OWNERAUTH_READFAIL</span></span>**<br /><span data-ttu-id="5411d-168">2147746307 (0x80040203) </span><span class="sxs-lookup"><span data-stu-id="5411d-168">2147746307 (0x80040203)</span></span> | <span data-ttu-id="5411d-169">PMM 無法讀取 TPM 擁有者授權值。</span><span class="sxs-lookup"><span data-stu-id="5411d-169">MBAM cannot read the TPM owner authorization value.</span></span> <span data-ttu-id="5411d-170">成功代管之後，值可能已經移除。</span><span class="sxs-lookup"><span data-stu-id="5411d-170">The value might have been removed after a successful escrow.</span></span> <span data-ttu-id="5411d-171">在 Windows 7，如果 TPM 為其他人所擁有，則 PMM 無法讀取值。</span><span class="sxs-lookup"><span data-stu-id="5411d-171">On Windows 7, MBAM cannot read the value if the TPM is owned by others.</span></span> |
| **<span data-ttu-id="5411d-172">MBAM_E_REBOOT_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="5411d-172">MBAM_E_REBOOT_REQUIRED</span></span>**<br /><span data-ttu-id="5411d-173">2147746308 (0x80040204) </span><span class="sxs-lookup"><span data-stu-id="5411d-173">2147746308 (0x80040204)</span></span> | <span data-ttu-id="5411d-174">電腦必須重新開機，才能將 TPM 設定為正確的狀態。</span><span class="sxs-lookup"><span data-stu-id="5411d-174">The computer must be restarted to set TPM to the correct state.</span></span> <span data-ttu-id="5411d-175">您可能需要手動重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="5411d-175">You might need to manually reboot the computer.</span></span> |
| **<span data-ttu-id="5411d-176">MBAM_E_SHUTDOWN_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="5411d-176">MBAM_E_SHUTDOWN_REQUIRED</span></span>**<br /><span data-ttu-id="5411d-177">2147746309 (0x80040205) </span><span class="sxs-lookup"><span data-stu-id="5411d-177">2147746309 (0x80040205)</span></span> | <span data-ttu-id="5411d-178">電腦必須關閉並重新開啟，以將 TPM 設定為正確的狀態。</span><span class="sxs-lookup"><span data-stu-id="5411d-178">The computer must be shut down and turned back on to set TPM to the correct state.</span></span> <span data-ttu-id="5411d-179">您可能需要手動重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="5411d-179">You might need to manually reboot the computer.</span></span> |
| **<span data-ttu-id="5411d-180">WS_E_ENDPOINT_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="5411d-180">WS_E_ENDPOINT_ACCESS_DENIED</span></span>**<br /><span data-ttu-id="5411d-181">2151481349 (0x803D0005) </span><span class="sxs-lookup"><span data-stu-id="5411d-181">2151481349 (0x803D0005)</span></span> | <span data-ttu-id="5411d-182">遠端端點拒絕存取。</span><span class="sxs-lookup"><span data-stu-id="5411d-182">Access was denied by the remote endpoint.</span></span> |
| **<span data-ttu-id="5411d-183">WS_E_ENDPOINT_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="5411d-183">WS_E_ENDPOINT_NOT_FOUND</span></span>**<br /><span data-ttu-id="5411d-184">2151481357 (0x803D000D) </span><span class="sxs-lookup"><span data-stu-id="5411d-184">2151481357 (0x803D000D)</span></span> | <span data-ttu-id="5411d-185">遠端端點不存在或無法定位。</span><span class="sxs-lookup"><span data-stu-id="5411d-185">The remote endpoint does not exist or could not be located.</span></span> |
| <span data-ttu-id="5411d-186">\*\*WS_E_ENDPOINT_FAILURE</span><span class="sxs-lookup"><span data-stu-id="5411d-186">\*\*WS_E_ENDPOINT_FAILURE</span></span><br /><span data-ttu-id="5411d-187">2151481357 (0x803D000F) </span><span class="sxs-lookup"><span data-stu-id="5411d-187">2151481357 (0x803D000F)</span></span> | <span data-ttu-id="5411d-188">遠端端點無法處理要求。</span><span class="sxs-lookup"><span data-stu-id="5411d-188">The remote endpoint could not process the request.</span></span> |
| **<span data-ttu-id="5411d-189">WS_E_ENDPOINT_UNREACHABLE</span><span class="sxs-lookup"><span data-stu-id="5411d-189">WS_E_ENDPOINT_UNREACHABLE</span></span>**<br /><span data-ttu-id="5411d-190">2151481360 (0x803D0010) </span><span class="sxs-lookup"><span data-stu-id="5411d-190">2151481360 (0x803D0010)</span></span> | <span data-ttu-id="5411d-191">無法到達遠端端點。</span><span class="sxs-lookup"><span data-stu-id="5411d-191">The remote endpoint was not reachable.</span></span> |
| **<span data-ttu-id="5411d-192">WS_E_ENDPOINT_FAULT_RECEIVED</span><span class="sxs-lookup"><span data-stu-id="5411d-192">WS_E_ENDPOINT_FAULT_RECEIVED</span></span>**<br /><span data-ttu-id="5411d-193">2151481363 (0x803D0013) </span><span class="sxs-lookup"><span data-stu-id="5411d-193">2151481363 (0x803D0013)</span></span> | <span data-ttu-id="5411d-194">從遠端端點收到包含錯誤的訊息。</span><span class="sxs-lookup"><span data-stu-id="5411d-194">A message containing a fault was received from the remote endpoint.</span></span> <span data-ttu-id="5411d-195">請確定您連接到正確的服務端點。</span><span class="sxs-lookup"><span data-stu-id="5411d-195">Make sure you are connecting to the correct service endpoint.</span></span> |
| <span data-ttu-id="5411d-196">**WS_E_INVALID_ENDPOINT_URL** 2151481376 (0x803D0020) </span><span class="sxs-lookup"><span data-stu-id="5411d-196">**WS_E_INVALID_ENDPOINT_URL** 2151481376 (0x803D0020)</span></span> | <span data-ttu-id="5411d-197">端點位址 URL 無效。</span><span class="sxs-lookup"><span data-stu-id="5411d-197">The endpoint address URL is not valid.</span></span> <span data-ttu-id="5411d-198">URL 必須以 "HTTP" 或 "HTTPs" 開始。</span><span class="sxs-lookup"><span data-stu-id="5411d-198">The URL must start with “http” or “https”.</span></span> |

   <span data-ttu-id="5411d-199">**ReportStatus：** 讀取該卷的合規性狀態，然後使用 SQLM 狀態報表服務將其傳送至</span><span class="sxs-lookup"><span data-stu-id="5411d-199">**ReportStatus:** Reads the compliance status of the volume and sends it to the MBAM compliance status database by using the MBAM status reporting service.</span></span> <span data-ttu-id="5411d-200">狀態包括密碼強度、保護程式類型、保護程式狀態和加密狀態。</span><span class="sxs-lookup"><span data-stu-id="5411d-200">The status includes cipher strength, protector type, protector state and encryption state.</span></span> <span data-ttu-id="5411d-201">如果失敗，會返回錯誤碼以進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="5411d-201">If it fails, an error code is returned for troubleshooting.</span></span>

   | <span data-ttu-id="5411d-202">參數</span><span class="sxs-lookup"><span data-stu-id="5411d-202">Parameter</span></span> | <span data-ttu-id="5411d-203">描述</span><span class="sxs-lookup"><span data-stu-id="5411d-203">Description</span></span> |
   | --------- | ----------- |
   | <span data-ttu-id="5411d-204">ReportingServiceEndPoint</span><span class="sxs-lookup"><span data-stu-id="5411d-204">ReportingServiceEndPoint</span></span> | <span data-ttu-id="5411d-205">指定 ：指定一個字串，指定一個資料包報服務端點。</span><span class="sxs-lookup"><span data-stu-id="5411d-205">A string specifying the MBAM status reporting service endpoint.</span></span> |

   <span data-ttu-id="5411d-206">以下是常見錯誤訊息的清單：</span><span class="sxs-lookup"><span data-stu-id="5411d-206">Here are a list of common error messages:</span></span>

   | <span data-ttu-id="5411d-207">常見的退貨值</span><span class="sxs-lookup"><span data-stu-id="5411d-207">Common return values</span></span> | <span data-ttu-id="5411d-208">錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="5411d-208">Error message</span></span> |
   | -------------------- | ------------- |
   | **<span data-ttu-id="5411d-209">S_OK</span><span class="sxs-lookup"><span data-stu-id="5411d-209">S_OK</span></span>**<br /> <span data-ttu-id="5411d-210">0 (0x0) </span><span class="sxs-lookup"><span data-stu-id="5411d-210">0 (0x0)</span></span> | <span data-ttu-id="5411d-211">方法成功</span><span class="sxs-lookup"><span data-stu-id="5411d-211">The method was successful</span></span> |
   | **<span data-ttu-id="5411d-212">WS_E_ENDPOINT_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="5411d-212">WS_E_ENDPOINT_ACCESS_DENIED</span></span>**<br /><span data-ttu-id="5411d-213">2151481349 (0x803D0005) </span><span class="sxs-lookup"><span data-stu-id="5411d-213">2151481349 (0x803D0005)</span></span> | <span data-ttu-id="5411d-214">遠端端點拒絕存取。</span><span class="sxs-lookup"><span data-stu-id="5411d-214">Access was denied by the remote endpoint.</span></span>|
   | **<span data-ttu-id="5411d-215">WS_E_ENDPOINT_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="5411d-215">WS_E_ENDPOINT_NOT_FOUND</span></span>**<br /><span data-ttu-id="5411d-216">2151481357 (0x803D000D) </span><span class="sxs-lookup"><span data-stu-id="5411d-216">2151481357 (0x803D000D)</span></span> | <span data-ttu-id="5411d-217">遠端端點不存在或無法找到。</span><span class="sxs-lookup"><span data-stu-id="5411d-217">The remote endpoint does not exist or could not be located.</span></span> |
   | **<span data-ttu-id="5411d-218">WS_E_ENDPOINT_FAILURE</span><span class="sxs-lookup"><span data-stu-id="5411d-218">WS_E_ENDPOINT_FAILURE</span></span>**<br /> <span data-ttu-id="5411d-219">2151481357 (0x803D000F) </span><span class="sxs-lookup"><span data-stu-id="5411d-219">2151481357 (0x803D000F)</span></span> | <span data-ttu-id="5411d-220">遠端端點無法處理要求。</span><span class="sxs-lookup"><span data-stu-id="5411d-220">The remote endpoint could not process the request.</span></span> |
   | **<span data-ttu-id="5411d-221">WS_E_ENDPOINT_UNREACHABLE</span><span class="sxs-lookup"><span data-stu-id="5411d-221">WS_E_ENDPOINT_UNREACHABLE</span></span>**<br /><span data-ttu-id="5411d-222">2151481360 (0x803D0010) </span><span class="sxs-lookup"><span data-stu-id="5411d-222">2151481360 (0x803D0010)</span></span> | <span data-ttu-id="5411d-223">無法到達遠端端點。</span><span class="sxs-lookup"><span data-stu-id="5411d-223">The remote endpoint was not reachable.</span></span> |
   | **<span data-ttu-id="5411d-224">WS_E_ENDPOINT_FAULT_RECEIVED</span><span class="sxs-lookup"><span data-stu-id="5411d-224">WS_E_ENDPOINT_FAULT_RECEIVED</span></span>**<br /><span data-ttu-id="5411d-225">2151481363 (0x803D0013) </span><span class="sxs-lookup"><span data-stu-id="5411d-225">2151481363 (0x803D0013)</span></span> | <span data-ttu-id="5411d-226">從遠端端點收到包含錯誤的訊息。</span><span class="sxs-lookup"><span data-stu-id="5411d-226">A message containing a fault was received from the remote endpoint.</span></span> <span data-ttu-id="5411d-227">請確定您連接到正確的服務端點。</span><span class="sxs-lookup"><span data-stu-id="5411d-227">Make sure you are connecting to the correct service endpoint.</span></span> |
   | **<span data-ttu-id="5411d-228">WS_E_INVALID_ENDPOINT_URL</span><span class="sxs-lookup"><span data-stu-id="5411d-228">WS_E_INVALID_ENDPOINT_URL</span></span>**<br /><span data-ttu-id="5411d-229">2151481376 (0x803D0020) </span><span class="sxs-lookup"><span data-stu-id="5411d-229">2151481376 (0x803D0020)</span></span> | <span data-ttu-id="5411d-230">端點位址 URL 無效。</span><span class="sxs-lookup"><span data-stu-id="5411d-230">The endpoint address URL is not valid.</span></span> <span data-ttu-id="5411d-231">URL 必須以 "HTTP" 或 "HTTPs" 開始。</span><span class="sxs-lookup"><span data-stu-id="5411d-231">The URL must start with “http” or “https”.</span></span> |

   <a href="" id="mbam-volume-wmi-class"></a><span data-ttu-id="5411d-232">**MBAM\_Volume WMI Class** **EscrowRecoveryKey:** Reads the recovery numerical password and key package of the volume and sends them to the MBAM recovery database by using the MBAM recovery service.</span><span class="sxs-lookup"><span data-stu-id="5411d-232">**MBAM\_Volume WMI Class** **EscrowRecoveryKey:** Reads the recovery numerical password and key package of the volume and sends them to the MBAM recovery database by using the MBAM recovery service.</span></span> <span data-ttu-id="5411d-233">如果失敗，會返回錯誤碼以進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="5411d-233">If it fails, an error code is returned for troubleshooting.</span></span>

   | <span data-ttu-id="5411d-234">參數</span><span class="sxs-lookup"><span data-stu-id="5411d-234">Parameter</span></span> | <span data-ttu-id="5411d-235">描述</span><span class="sxs-lookup"><span data-stu-id="5411d-235">Description</span></span> |
   | --------- | ----------- |
   | <span data-ttu-id="5411d-236">RecoveryServiceEndPoint</span><span class="sxs-lookup"><span data-stu-id="5411d-236">RecoveryServiceEndPoint</span></span> | <span data-ttu-id="5411d-237">指定 ：指定此為 ：：一個字串，用於指定一個服務端點。</span><span class="sxs-lookup"><span data-stu-id="5411d-237">A string specifying the MBAM recovery service endpoint.</span></span> |

   <span data-ttu-id="5411d-238">以下是常見錯誤訊息的清單：</span><span class="sxs-lookup"><span data-stu-id="5411d-238">Here are a list of common error messages:</span></span>

   | <span data-ttu-id="5411d-239">常見的退貨值</span><span class="sxs-lookup"><span data-stu-id="5411d-239">Common return values</span></span> | <span data-ttu-id="5411d-240">錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="5411d-240">Error message</span></span> |
   | -------------------- | ------------- |
   | **<span data-ttu-id="5411d-241">S_OK</span><span class="sxs-lookup"><span data-stu-id="5411d-241">S_OK</span></span>**<br /><span data-ttu-id="5411d-242">0 (0x0) </span><span class="sxs-lookup"><span data-stu-id="5411d-242">0 (0x0)</span></span> | <span data-ttu-id="5411d-243">方法成功</span><span class="sxs-lookup"><span data-stu-id="5411d-243">The method was successful</span></span> |
   | **<span data-ttu-id="5411d-244">FVE_E_LOCKED_VOLUME</span><span class="sxs-lookup"><span data-stu-id="5411d-244">FVE_E_LOCKED_VOLUME</span></span>**<br /><span data-ttu-id="5411d-245">2150694912 (0x80310000) </span><span class="sxs-lookup"><span data-stu-id="5411d-245">2150694912 (0x80310000)</span></span> | <span data-ttu-id="5411d-246">音量已鎖定。</span><span class="sxs-lookup"><span data-stu-id="5411d-246">The volume is locked.</span></span> |
   | **<span data-ttu-id="5411d-247">FVE_E_PROTECTOR_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="5411d-247">FVE_E_PROTECTOR_NOT_FOUND</span></span>**<br /><span data-ttu-id="5411d-248">2150694963 (0x80310033) </span><span class="sxs-lookup"><span data-stu-id="5411d-248">2150694963 (0x80310033)</span></span> | <span data-ttu-id="5411d-249">找不到音量的數值密碼保護程式。</span><span class="sxs-lookup"><span data-stu-id="5411d-249">A Numerical Password protector was not found for the volume.</span></span> |
   | **<span data-ttu-id="5411d-250">WS_E_ENDPOINT_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="5411d-250">WS_E_ENDPOINT_ACCESS_DENIED</span></span>**<br /><span data-ttu-id="5411d-251">2151481349 (0x803D0005) </span><span class="sxs-lookup"><span data-stu-id="5411d-251">2151481349 (0x803D0005)</span></span> | <span data-ttu-id="5411d-252">遠端端點拒絕存取。</span><span class="sxs-lookup"><span data-stu-id="5411d-252">Access was denied by the remote endpoint.</span></span> |
   | **<span data-ttu-id="5411d-253">WS_E_ENDPOINT_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="5411d-253">WS_E_ENDPOINT_NOT_FOUND</span></span>**<br /><span data-ttu-id="5411d-254">2151481357 (0x803D000D) </span><span class="sxs-lookup"><span data-stu-id="5411d-254">2151481357 (0x803D000D)</span></span> | <span data-ttu-id="5411d-255">遠端端點不存在或無法找到。</span><span class="sxs-lookup"><span data-stu-id="5411d-255">The remote endpoint does not exist or could not be located.</span></span> |
   | **<span data-ttu-id="5411d-256">WS_E_ENDPOINT_FAILURE</span><span class="sxs-lookup"><span data-stu-id="5411d-256">WS_E_ENDPOINT_FAILURE</span></span>**<br /><span data-ttu-id="5411d-257">2151481357 (0x803D000F) </span><span class="sxs-lookup"><span data-stu-id="5411d-257">2151481357 (0x803D000F)</span></span> | <span data-ttu-id="5411d-258">遠端端點無法處理要求。</span><span class="sxs-lookup"><span data-stu-id="5411d-258">The remote endpoint could not process the request.</span></span> |
   | **<span data-ttu-id="5411d-259">WS_E_ENDPOINT_UNREACHABLE</span><span class="sxs-lookup"><span data-stu-id="5411d-259">WS_E_ENDPOINT_UNREACHABLE</span></span>**<br /><span data-ttu-id="5411d-260">2151481360 (0x803D0010) </span><span class="sxs-lookup"><span data-stu-id="5411d-260">2151481360 (0x803D0010)</span></span> | <span data-ttu-id="5411d-261">無法到達遠端端點。</span><span class="sxs-lookup"><span data-stu-id="5411d-261">The remote endpoint was not reachable.</span></span> |
   | **<span data-ttu-id="5411d-262">WS_E_ENDPOINT_FAULT_RECEIVED</span><span class="sxs-lookup"><span data-stu-id="5411d-262">WS_E_ENDPOINT_FAULT_RECEIVED</span></span>**<br /><span data-ttu-id="5411d-263">2151481363 (0x803D0013) </span><span class="sxs-lookup"><span data-stu-id="5411d-263">2151481363 (0x803D0013)</span></span> | <span data-ttu-id="5411d-264">從遠端端點收到包含錯誤的訊息。</span><span class="sxs-lookup"><span data-stu-id="5411d-264">A message containing a fault was received from the remote endpoint.</span></span> <span data-ttu-id="5411d-265">請確定您連接到正確的服務端點。</span><span class="sxs-lookup"><span data-stu-id="5411d-265">Make sure you are connecting to the correct service endpoint.</span></span> |
   | **<span data-ttu-id="5411d-266">WS_E_INVALID_ENDPOINT_URL</span><span class="sxs-lookup"><span data-stu-id="5411d-266">WS_E_INVALID_ENDPOINT_URL</span></span>**<br /><span data-ttu-id="5411d-267">2151481376 (0x803D0020) </span><span class="sxs-lookup"><span data-stu-id="5411d-267">2151481376 (0x803D0020)</span></span> | <span data-ttu-id="5411d-268">端點位址 URL 無效。</span><span class="sxs-lookup"><span data-stu-id="5411d-268">The endpoint address URL is not valid.</span></span> <span data-ttu-id="5411d-269">URL 必須以 "HTTP" 或 "HTTPs" 開始。</span><span class="sxs-lookup"><span data-stu-id="5411d-269">The URL must start with “http” or “https”.</span></span> |
     

2. **<span data-ttu-id="5411d-270">使用 Microsoft 部署工具組和 PowerShell (MDT) 部署 MDM</span><span class="sxs-lookup"><span data-stu-id="5411d-270">Deploy MBAM by using Microsoft Deployment Toolkit (MDT) and PowerShell</span></span>**

   1.  <span data-ttu-id="5411d-271">在 MDT 中，建立新的部署共用或開啟現有的部署共用。</span><span class="sxs-lookup"><span data-stu-id="5411d-271">In MDT, create a new deployment share or open an existing deployment share.</span></span>

       **<span data-ttu-id="5411d-272">注意</span><span class="sxs-lookup"><span data-stu-id="5411d-272">Note</span></span>**  
       <span data-ttu-id="5411d-273">`Invoke-MbamClientDeployment.ps1`PowerShell 腳本可用於任何影像程式或工具。</span><span class="sxs-lookup"><span data-stu-id="5411d-273">The `Invoke-MbamClientDeployment.ps1` PowerShell script can be used with any imaging process or tool.</span></span> <span data-ttu-id="5411d-274">本節將說明如何使用 MDT 進行整合，但步驟與將其與其他程式或工具整合類似。</span><span class="sxs-lookup"><span data-stu-id="5411d-274">This section shows how to integrate it by using MDT, but the steps are similar to integrating it with any other process or tool.</span></span>

       **<span data-ttu-id="5411d-275">謹慎</span><span class="sxs-lookup"><span data-stu-id="5411d-275">Caution</span></span>**  
       <span data-ttu-id="5411d-276">如果您使用的是 BitLocker 預配置 (WinPE) ，並想要維持 TPM 擁有者的授權值，您必須在 WinPE 中新增腳本，安裝重新開機至完整作業系統之前。 `SaveWinPETpmOwnerAuth.wsf`</span><span class="sxs-lookup"><span data-stu-id="5411d-276">If you are using BitLocker pre-provisioning (WinPE) and want to maintain the TPM owner authorization value, you must add the `SaveWinPETpmOwnerAuth.wsf` script in WinPE immediately before the installation reboots into the full operating system.</span></span> **<span data-ttu-id="5411d-277">如果您沒有使用此腳本，重新開機時就會失去 TPM 擁有者的授權值。</span><span class="sxs-lookup"><span data-stu-id="5411d-277">If you do not use this script, you will lose the TPM owner authorization value on reboot.</span></span>**

   2.  <span data-ttu-id="5411d-278">複製到 `Invoke-MbamClientDeployment.ps1` \*\* &lt; DeploymentShare &gt; \\Scripts\*\*。</span><span class="sxs-lookup"><span data-stu-id="5411d-278">Copy `Invoke-MbamClientDeployment.ps1` to **&lt;DeploymentShare&gt;\\Scripts**.</span></span> <span data-ttu-id="5411d-279">如果您使用的是預部署，請複製檔案 `SaveWinPETpmOwnerAuth.wsf` 至\*\* &lt; DeploymentShare &gt; \\Scripts\*\*。</span><span class="sxs-lookup"><span data-stu-id="5411d-279">If you are using pre-provisioning, copy the `SaveWinPETpmOwnerAuth.wsf` file into **&lt;DeploymentShare&gt;\\Scripts**.</span></span>

   3.  <span data-ttu-id="5411d-280">在部署共用中的應用程式節點中新增一個 ：將<a0>2.5 SP1 SP1 用戶端應用程式新增到應用程式節點 。</a1></span><span class="sxs-lookup"><span data-stu-id="5411d-280">Add the MBAM 2.5 SP1 client application to the Applications node in the deployment share.</span></span>

       1.  <span data-ttu-id="5411d-281">在 [ **應用程式節點」** 下，按一下 **[新增應用程式**> 。</span><span class="sxs-lookup"><span data-stu-id="5411d-281">Under the **Applications** node, click **New Application**.</span></span>

       2.  <span data-ttu-id="5411d-282">選取 **具有來源檔案的應用程式**。</span><span class="sxs-lookup"><span data-stu-id="5411d-282">Select **Application with Source Files**.</span></span> <span data-ttu-id="5411d-283">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="5411d-283">Click **Next**.</span></span>

       3.  <span data-ttu-id="5411d-284">在 **應用程式名稱中**，輸入「INM 2.5 SP1 用戶端」。</span><span class="sxs-lookup"><span data-stu-id="5411d-284">In **Application Name**, type “MBAM 2.5 SP1 Client”.</span></span> <span data-ttu-id="5411d-285">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="5411d-285">Click **Next**.</span></span>

       4.  <span data-ttu-id="5411d-286">流覽至包含 `MBAMClientSetup-<Version>.msi` 的目錄。</span><span class="sxs-lookup"><span data-stu-id="5411d-286">Browse to the directory containing `MBAMClientSetup-<Version>.msi`.</span></span> <span data-ttu-id="5411d-287">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="5411d-287">Click **Next**.</span></span>

       5.  <span data-ttu-id="5411d-288">輸入要建立之目錄的 「：「2.5 SP1 用戶端」。</span><span class="sxs-lookup"><span data-stu-id="5411d-288">Type “MBAM 2.5 SP1 Client” as the directory to create.</span></span> <span data-ttu-id="5411d-289">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="5411d-289">Click **Next**.</span></span>

       6.  <span data-ttu-id="5411d-290">在 `msiexec /i MBAMClientSetup-<Version>.msi /quiet` 命令列輸入。</span><span class="sxs-lookup"><span data-stu-id="5411d-290">Enter `msiexec /i MBAMClientSetup-<Version>.msi /quiet` at the command line.</span></span> <span data-ttu-id="5411d-291">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="5411d-291">Click **Next**.</span></span>

       7.  <span data-ttu-id="5411d-292">接受其餘的預設值以完成新應用程式精靈。</span><span class="sxs-lookup"><span data-stu-id="5411d-292">Accept the remaining defaults to complete the New Application wizard.</span></span>

   4.  <span data-ttu-id="5411d-293">在 MDT 中，以滑鼠右鍵按一下部署共用的名稱，然後按一下 [ **屬性**> 。</span><span class="sxs-lookup"><span data-stu-id="5411d-293">In MDT, right-click the name of the deployment share and click **Properties**.</span></span> <span data-ttu-id="5411d-294">按一下 [ **規則>** 選項卡。新增下列行：</span><span class="sxs-lookup"><span data-stu-id="5411d-294">Click the **Rules** tab. Add the following lines:</span></span>

       `SkipBitLocker=YES``BDEInstall=TPM``BDEInstallSuppress=NO``BDEWaitForEncryption=YES`

       <span data-ttu-id="5411d-295">按一下 [確定> 以關閉視窗。</span><span class="sxs-lookup"><span data-stu-id="5411d-295">Click OK to close the window.</span></span>

   5.  <span data-ttu-id="5411d-296">在任務順序節點下，編輯用於部署Windows順序。</span><span class="sxs-lookup"><span data-stu-id="5411d-296">Under the Task Sequences node, edit an existing task sequence used for Windows Deployment.</span></span> <span data-ttu-id="5411d-297">您可以按一下滑鼠右鍵按一下任務順序節點、選取新的工作順序，然後\*\*\*\* 完成精靈，以建立\*\*\*\* 新工作順序。</span><span class="sxs-lookup"><span data-stu-id="5411d-297">If you want, you can create a new task sequence by right-clicking the **Task Sequences** node, selecting **New Task Sequence**, and completing the wizard.</span></span>

       <span data-ttu-id="5411d-298">在所選 **工作順序** 的工作列上，執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="5411d-298">On the **Task Sequence** tab of the selected task sequence, perform these steps:</span></span>

       1.  <span data-ttu-id="5411d-299">如果您希望在\*\*\*\* WinPE 中啟用**BitLocker，** 請啟用選擇性工作 ：啟用 BitLocker (離線) ，因為 WinPE 只會加密已使用的空間。</span><span class="sxs-lookup"><span data-stu-id="5411d-299">Under the **Preinstall** folder, enable the optional task **Enable BitLocker (Offline)** if you want BitLocker enabled in WinPE, which encrypts used space only.</span></span>

       2.  <span data-ttu-id="5411d-300">若要在使用預布建時保留 TPM OwnerAuth，允許稍後由 PMM 代管，請執行下列操作：</span><span class="sxs-lookup"><span data-stu-id="5411d-300">To persist TPM OwnerAuth when using pre-provisioning, allowing MBAM to escrow it later, do the following:</span></span>

           1.  <span data-ttu-id="5411d-301">尋找 **安裝作業系統** 步驟</span><span class="sxs-lookup"><span data-stu-id="5411d-301">Find the **Install Operating System** step</span></span>

           2.  <span data-ttu-id="5411d-302">在之後 **新增執行命令列** 步驟</span><span class="sxs-lookup"><span data-stu-id="5411d-302">Add a new **Run Command Line** step after it</span></span>

           3.  <span data-ttu-id="5411d-303">命名持續 **TPM 擁有者驗證的步驟**</span><span class="sxs-lookup"><span data-stu-id="5411d-303">Name the step **Persist TPM OwnerAuth**</span></span>

           4.  <span data-ttu-id="5411d-304">將命令列設定為附注：Windows 10版本 1607 或更新版本，Windows才能取得 `cscript.exe "%SCRIPTROOT%/SaveWinPETpmOwnerAuth.wsf"`
            \*\* \*\*TPM 的擁有權。</span><span class="sxs-lookup"><span data-stu-id="5411d-304">Set the command line to `cscript.exe "%SCRIPTROOT%/SaveWinPETpmOwnerAuth.wsf"`
**Note:** For Windows 10, version 1607 or later, only Windows can take ownership of the TPM.</span></span> <span data-ttu-id="5411d-305">在 addiiton 中Windows在配置 TPM 時，不會保留 TPM 擁有者密碼。</span><span class="sxs-lookup"><span data-stu-id="5411d-305">In addiiton, Windows will not retain the TPM owner password when provisioning the TPM.</span></span> <span data-ttu-id="5411d-306">請參閱 [TPM 擁有者密碼以](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password) 進一步詳細資料。</span><span class="sxs-lookup"><span data-stu-id="5411d-306">See [TPM owner password](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password) for further details.</span></span>

       3.  <span data-ttu-id="5411d-307">在狀態 **還原資料夾中** ，刪除啟用 **BitLocker** 工作。</span><span class="sxs-lookup"><span data-stu-id="5411d-307">In the **State Restore** folder, delete the **Enable BitLocker** task.</span></span>

       4.  <span data-ttu-id="5411d-308">In the **State Restore** folder under **Custom Tasks**, create a new **Install Application** task and name it **Install MBAM Agent**.</span><span class="sxs-lookup"><span data-stu-id="5411d-308">In the **State Restore** folder under **Custom Tasks**, create a new **Install Application** task and name it **Install MBAM Agent**.</span></span> <span data-ttu-id="5411d-309">按一下 [ **安裝單一應用程式單** 一應用程式選項按鈕並流覽至先前所建立之的 [2.5 SP1 SP1 用戶端應用程式>。</span><span class="sxs-lookup"><span data-stu-id="5411d-309">Click the **Install Single Application** radio button and browse to the MBAM 2.5 SP1 client application created earlier.</span></span>

       5.  <span data-ttu-id="5411d-310">在自訂\*\*\*\* 工作下的狀態還原\*\*\*\* 資料夾中，在使用下列設定)  (之後，使用下列設定 (建立新的執行**PowerShell 腳本**工作 (，並針對您的環境更新參數) ：</span><span class="sxs-lookup"><span data-stu-id="5411d-310">In the **State Restore** folder under **Custom Tasks**, create a new **Run PowerShell Script** task (after the MBAM 2.5 SP1 Client application step) with the following settings (update the parameters as appropriate for your environment):</span></span>

           -   <span data-ttu-id="5411d-311">名稱：設定 BITLocker for</span><span class="sxs-lookup"><span data-stu-id="5411d-311">Name: Configure BitLocker for MBAM</span></span>

           -   <span data-ttu-id="5411d-312">PowerShell 腳本：</span><span class="sxs-lookup"><span data-stu-id="5411d-312">PowerShell script:</span></span> `Invoke-MbamClientDeployment.ps1`

           -   <span data-ttu-id="5411d-313">參數：</span><span class="sxs-lookup"><span data-stu-id="5411d-313">Parameters:</span></span>

               <table>
               <colgroup>
               <col width="33%" />
               <col width="33%" />
               <col width="33%" />
               </colgroup>
               <tbody>
               <tr class="odd">
               <td align="left"><p><span data-ttu-id="5411d-314">-RecoveryServiceEndpoint</span><span class="sxs-lookup"><span data-stu-id="5411d-314">-RecoveryServiceEndpoint</span></span></p></td>
               <td align="left"><p><span data-ttu-id="5411d-315">必要</span><span class="sxs-lookup"><span data-stu-id="5411d-315">Required</span></span></p></td>
               <td align="left"><p><span data-ttu-id="5411d-316">管理與修復服務端點</span><span class="sxs-lookup"><span data-stu-id="5411d-316">MBAM recovery service endpoint</span></span></p></td>
               </tr>
               <tr class="even">
               <td align="left"><p><span data-ttu-id="5411d-317">-StatusReportingServiceEndpoint</span><span class="sxs-lookup"><span data-stu-id="5411d-317">-StatusReportingServiceEndpoint</span></span></p></td>
               <td align="left"><p><span data-ttu-id="5411d-318">選用</span><span class="sxs-lookup"><span data-stu-id="5411d-318">Optional</span></span></p></td>
               <td align="left"><p><span data-ttu-id="5411d-319">資料包報服務端點的</span><span class="sxs-lookup"><span data-stu-id="5411d-319">MBAM status reporting service endpoint</span></span></p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p><span data-ttu-id="5411d-320">-EncryptionMethod</span><span class="sxs-lookup"><span data-stu-id="5411d-320">-EncryptionMethod</span></span></p></td>
               <td align="left"><p><span data-ttu-id="5411d-321">選用</span><span class="sxs-lookup"><span data-stu-id="5411d-321">Optional</span></span></p></td>
               <td align="left"><p><span data-ttu-id="5411d-322">預設加密 (：AES 128) </span><span class="sxs-lookup"><span data-stu-id="5411d-322">Encryption method (default: AES 128)</span></span></p></td>
               </tr>
               <tr class="even">
               <td align="left"><p><span data-ttu-id="5411d-323">-EncryptAndEscrowDataVolume</span><span class="sxs-lookup"><span data-stu-id="5411d-323">-EncryptAndEscrowDataVolume</span></span></p></td>
               <td align="left"><p><span data-ttu-id="5411d-324">切換</span><span class="sxs-lookup"><span data-stu-id="5411d-324">Switch</span></span></p></td>
               <td align="left"><p><span data-ttu-id="5411d-325">指定加密資料量 () 並代管資料量復原金鑰 () </span><span class="sxs-lookup"><span data-stu-id="5411d-325">Specify to encrypt data volume(s) and escrow data volume recovery key(s)</span></span></p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p><span data-ttu-id="5411d-326">-WaitForEncryptionToComplete</span><span class="sxs-lookup"><span data-stu-id="5411d-326">-WaitForEncryptionToComplete</span></span></p></td>
               <td align="left"><p><span data-ttu-id="5411d-327">切換</span><span class="sxs-lookup"><span data-stu-id="5411d-327">Switch</span></span></p></td>
               <td align="left"><p><span data-ttu-id="5411d-328">指定以等待加密完成</span><span class="sxs-lookup"><span data-stu-id="5411d-328">Specify to wait for the encryption to complete</span></span></p></td>
               </tr>
               <tr class="even">
               <td align="left"><p><span data-ttu-id="5411d-329">-DoNotResumeSuspendedEncryption</span><span class="sxs-lookup"><span data-stu-id="5411d-329">-DoNotResumeSuspendedEncryption</span></span></p></td>
               <td align="left"><p><span data-ttu-id="5411d-330">切換</span><span class="sxs-lookup"><span data-stu-id="5411d-330">Switch</span></span></p></td>
               <td align="left"><p><span data-ttu-id="5411d-331">指定部署腳本不會繼續暫停加密</span><span class="sxs-lookup"><span data-stu-id="5411d-331">Specify that the deployment script will not resume suspended encryption</span></span></p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p><span data-ttu-id="5411d-332">-IgnoreEscrowOwnerAuthFailure</span><span class="sxs-lookup"><span data-stu-id="5411d-332">-IgnoreEscrowOwnerAuthFailure</span></span></p></td>
               <td align="left"><p><span data-ttu-id="5411d-333">切換</span><span class="sxs-lookup"><span data-stu-id="5411d-333">Switch</span></span></p></td>
               <td align="left"><p><span data-ttu-id="5411d-334">指定以忽略 TPM 擁有者-驗證代管失敗。</span><span class="sxs-lookup"><span data-stu-id="5411d-334">Specify to ignore TPM owner-auth escrow failure.</span></span> <span data-ttu-id="5411d-335">它應用於無法讀取 TPM 擁有者驗證的情況，例如已啟用 TPM 自動布建</span><span class="sxs-lookup"><span data-stu-id="5411d-335">It should be used in the scenarios where MBAM is not able to read the TPM owner-auth, e.g. if TPM auto provisioning is enabled</span></span></p></td>
               </tr>
               <tr class="even">
               <td align="left"><p><span data-ttu-id="5411d-336">-IgnoreEscrowRecoveryKeyFailure</span><span class="sxs-lookup"><span data-stu-id="5411d-336">-IgnoreEscrowRecoveryKeyFailure</span></span></p></td>
               <td align="left"><p><span data-ttu-id="5411d-337">切換</span><span class="sxs-lookup"><span data-stu-id="5411d-337">Switch</span></span></p></td>
               <td align="left"><p><span data-ttu-id="5411d-338">指定以忽略大量修復金鑰代管失敗</span><span class="sxs-lookup"><span data-stu-id="5411d-338">Specify to ignore volume recovery key escrow failure</span></span></p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p><span data-ttu-id="5411d-339">-IgnoreReportStatusFailure</span><span class="sxs-lookup"><span data-stu-id="5411d-339">-IgnoreReportStatusFailure</span></span></p></td>
               <td align="left"><p><span data-ttu-id="5411d-340">切換</span><span class="sxs-lookup"><span data-stu-id="5411d-340">Switch</span></span></p></td>
               <td align="left"><p><span data-ttu-id="5411d-341">指定以忽略狀態報表失敗</span><span class="sxs-lookup"><span data-stu-id="5411d-341">Specify to ignore status reporting failure</span></span></p></td>
               </tr>
               </tbody>
               </table>

                 

**<span data-ttu-id="5411d-342">若要在部署中啟用 BITLocker，在部署時使用 WINDOWS 2.5 或更Windows程式</span><span class="sxs-lookup"><span data-stu-id="5411d-342">To enable BitLocker using MBAM 2.5 or earlier as part of a Windows deployment</span></span>**

1.  <span data-ttu-id="5411d-343">安裝 <管理及管理用戶端。.</span><span class="sxs-lookup"><span data-stu-id="5411d-343">Install the MBAM Client.</span></span> <span data-ttu-id="5411d-344">有關指示，請參閱[如何使用命令列來部署的。](how-to-deploy-the-mbam-client-by-using-a-command-line.md)</span><span class="sxs-lookup"><span data-stu-id="5411d-344">For instructions, see [How to Deploy the MBAM Client by Using a Command Line](how-to-deploy-the-mbam-client-by-using-a-command-line.md).</span></span>

2.  <span data-ttu-id="5411d-345">將電腦加入網域， (建議) 。</span><span class="sxs-lookup"><span data-stu-id="5411d-345">Join the computer to a domain (recommended).</span></span>

    -   <span data-ttu-id="5411d-346">如果電腦未加入網域，則修復密碼不會儲存于 INM 金鑰修復服務中。</span><span class="sxs-lookup"><span data-stu-id="5411d-346">If the computer is not joined to a domain, the recovery password is not stored in the MBAM Key Recovery service.</span></span> <span data-ttu-id="5411d-347">根據預設，除非可以儲存修復金鑰，否則，如果無法加密，則不會允許進行加密。</span><span class="sxs-lookup"><span data-stu-id="5411d-347">By default, MBAM does not allow encryption to occur unless the recovery key can be stored.</span></span>

    -   <span data-ttu-id="5411d-348">如果電腦在將修復金鑰儲存于 IBMM Server 之前，會以復原模式啟動，則沒有可用的復原方法，而且必須重新想像電腦。</span><span class="sxs-lookup"><span data-stu-id="5411d-348">If a computer starts in recovery mode before the recovery key is stored on the MBAM Server, no recovery method is available, and the computer has to be reimaged.</span></span>

3.  <span data-ttu-id="5411d-349">以系統管理員的名符開啟命令提示，並停止該服務。</span><span class="sxs-lookup"><span data-stu-id="5411d-349">Open a command prompt as an administrator, and stop the MBAM service.</span></span>

4.  <span data-ttu-id="5411d-350">輸入下列命令，\*\*\*\* 將服務**設定為**手動或隨用：</span><span class="sxs-lookup"><span data-stu-id="5411d-350">Set the service to **Manual** or **On demand** by typing the following commands:</span></span>

    **<span data-ttu-id="5411d-351">net stop 的</span><span class="sxs-lookup"><span data-stu-id="5411d-351">net stop mbamagent</span></span>**

    **<span data-ttu-id="5411d-352">sc config 的啟動= demand</span><span class="sxs-lookup"><span data-stu-id="5411d-352">sc config mbamagent start= demand</span></span>**

5.  <span data-ttu-id="5411d-353">設定註冊表值，讓 B0 電腦管理中心用戶端忽略群組原則設定，而是設定加密Windows部署至該用戶端電腦的時間。</span><span class="sxs-lookup"><span data-stu-id="5411d-353">Set the registry values so that the MBAM Client ignores the Group Policy settings and instead sets encryption to start the time Windows is deployed to that client computer.</span></span>

    **<span data-ttu-id="5411d-354">謹慎</span><span class="sxs-lookup"><span data-stu-id="5411d-354">Caution</span></span>**  
    <span data-ttu-id="5411d-355">此步驟說明如何修改Windows註冊表。</span><span class="sxs-lookup"><span data-stu-id="5411d-355">This step describes how to modify the Windows registry.</span></span> <span data-ttu-id="5411d-356">不正確地使用登錄編輯器可能會導致嚴重問題，而這些問題可能會要求您重新安裝Windows。</span><span class="sxs-lookup"><span data-stu-id="5411d-356">Using Registry Editor incorrectly can cause serious issues that can require you to reinstall Windows.</span></span> <span data-ttu-id="5411d-357">我們無法保證因不正確使用登錄編輯器而產生的問題可以解決。</span><span class="sxs-lookup"><span data-stu-id="5411d-357">We cannot guarantee that issues resulting from the incorrect use of Registry Editor can be resolved.</span></span> <span data-ttu-id="5411d-358">請自行承擔使用登錄編輯程式的風險。</span><span class="sxs-lookup"><span data-stu-id="5411d-358">Use Registry Editor at your own risk.</span></span>

    1.  <span data-ttu-id="5411d-359">設定僅適用于作業系統的\*\*\*\* TPM 加密、執行 Regedit.exe，然後從 C：\\Program Files\\Microsoft\\MDOP MDM\\MDMDeploymentKeyTemplate.reg 導入註冊表金鑰範本。</span><span class="sxs-lookup"><span data-stu-id="5411d-359">Set the TPM for **Operating system only encryption**, run Regedit.exe, and then import the registry key template from C:\\Program Files\\Microsoft\\MDOP MBAM\\MBAMDeploymentKeyTemplate.reg.</span></span>

    2.  <span data-ttu-id="5411d-360">在 Regedit.exe，請前往 HKLM\\SOFTWARE\\Microsoft\\\TM，並設定下表所列的設定。</span><span class="sxs-lookup"><span data-stu-id="5411d-360">In Regedit.exe, go to HKLM\\SOFTWARE\\Microsoft\\MBAM, and configure the settings that are listed in the following table.</span></span>

        **<span data-ttu-id="5411d-361">注意</span><span class="sxs-lookup"><span data-stu-id="5411d-361">Note</span></span>**  
        <span data-ttu-id="5411d-362">您可以在這裡設定與 B0 電腦管理中心相關的群組原則設定或註冊表值。</span><span class="sxs-lookup"><span data-stu-id="5411d-362">You can set Group Policy settings or registry values related to MBAM here.</span></span> <span data-ttu-id="5411d-363">這些設定會取代先前設定的值。</span><span class="sxs-lookup"><span data-stu-id="5411d-363">These settings will override previously set values.</span></span>

        <span data-ttu-id="5411d-364">登錄機碼目 設定設定</span><span class="sxs-lookup"><span data-stu-id="5411d-364">Registry entry Configuration settings</span></span>

        <span data-ttu-id="5411d-365">DeploymentTime</span><span class="sxs-lookup"><span data-stu-id="5411d-365">DeploymentTime</span></span>

        <span data-ttu-id="5411d-366">0 = 關閉</span><span class="sxs-lookup"><span data-stu-id="5411d-366">0 = Off</span></span>

        <span data-ttu-id="5411d-367">1 = 使用部署時間 (設定) 預設設定 - 使用此設定在將 Windows部署到用戶端電腦時啟用加密。</span><span class="sxs-lookup"><span data-stu-id="5411d-367">1 = Use deployment time policy settings (default) – use this setting to enable encryption at the time Windows is deployed to the client computer.</span></span>

        <span data-ttu-id="5411d-368">UseKeyRecoveryService</span><span class="sxs-lookup"><span data-stu-id="5411d-368">UseKeyRecoveryService</span></span>

        <span data-ttu-id="5411d-369">0 = 請勿使用金鑰代管 (在此案例中，系統不需要接下來的兩個登錄機碼目) </span><span class="sxs-lookup"><span data-stu-id="5411d-369">0 = Do not use key escrow (the next two registry entries are not required in this case)</span></span>

        <span data-ttu-id="5411d-370">1 = 在金鑰修復系統使用金鑰代管 (預設) </span><span class="sxs-lookup"><span data-stu-id="5411d-370">1 = Use key escrow in Key Recovery system (default)</span></span>

        <span data-ttu-id="5411d-371">這是建議設定，可讓的</span><span class="sxs-lookup"><span data-stu-id="5411d-371">This is the recommended setting, which enables MBAM to store the recovery keys.</span></span> <span data-ttu-id="5411d-372">電腦必須能與管理管理中心金鑰修復服務通訊。</span><span class="sxs-lookup"><span data-stu-id="5411d-372">The computer must be able to communicate with the MBAM Key Recovery service.</span></span> <span data-ttu-id="5411d-373">請確認電腦可以與服務通訊，然後再繼續進行。</span><span class="sxs-lookup"><span data-stu-id="5411d-373">Verify that the computer can communicate with the service before you proceed.</span></span>

        <span data-ttu-id="5411d-374">KeyRecoveryOptions</span><span class="sxs-lookup"><span data-stu-id="5411d-374">KeyRecoveryOptions</span></span>

        <span data-ttu-id="5411d-375">0 = 僅上傳修復金鑰</span><span class="sxs-lookup"><span data-stu-id="5411d-375">0 = Uploads Recovery Key only</span></span>

        <span data-ttu-id="5411d-376">1 = 上傳修復金鑰和金鑰修復套件 (預設) </span><span class="sxs-lookup"><span data-stu-id="5411d-376">1 = Uploads Recovery Key and Key Recovery Package (default)</span></span>

        <span data-ttu-id="5411d-377">KeyRecoveryServiceEndPoint</span><span class="sxs-lookup"><span data-stu-id="5411d-377">KeyRecoveryServiceEndPoint</span></span>

        <span data-ttu-id="5411d-378">將此值設定為執行 Key Recovery 服務之伺服器的 URL，例如，HTTP:// &lt; 電腦名稱稱 &gt; /IBMMRecoveryAndWarewareService/CoreService.svc。</span><span class="sxs-lookup"><span data-stu-id="5411d-378">Set this value to the URL for the server running the Key Recovery service, for example, http://&lt;computer name&gt;/MBAMRecoveryAndHardwareService/CoreService.svc.</span></span>


6.  <span data-ttu-id="5411d-379">在部署時，即會重新開機系統。</span><span class="sxs-lookup"><span data-stu-id="5411d-379">The MBAM Client will restart the system during the MBAM Client deployment.</span></span> <span data-ttu-id="5411d-380">當您準備好重新開機時，請以系統管理員的指令提示執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="5411d-380">When you are ready for this restart, run the following command at a command prompt as an administrator:</span></span>

    **<span data-ttu-id="5411d-381">net start 的</span><span class="sxs-lookup"><span data-stu-id="5411d-381">net start mbamagent</span></span>**

7.  <span data-ttu-id="5411d-382">當電腦重新開機，而BIOS 提示您時，請接受 TPM 變更。</span><span class="sxs-lookup"><span data-stu-id="5411d-382">When the computers restarts, and the BIOS prompts you, accept the TPM change.</span></span>

8.  <span data-ttu-id="5411d-383">在 Windows作業系統映射程式期間，當您準備好要開始加密時，請以系統管理員的方程式開啟命令提示，然後輸入下列命令，將開始設定為自動，並重新啟動\*\*\*\* 的 MRM 用戶端代理程式：</span><span class="sxs-lookup"><span data-stu-id="5411d-383">During the Windows client operating system imaging process, when you are ready to start encryption, open a command prompt as an administrator, and type the following commands to set the start to **Automatic** and to restart the MBAM Client agent:</span></span>

    **<span data-ttu-id="5411d-384">sc config 的啟動= auto</span><span class="sxs-lookup"><span data-stu-id="5411d-384">sc config mbamagent start= auto</span></span>**

    **<span data-ttu-id="5411d-385">net start 的</span><span class="sxs-lookup"><span data-stu-id="5411d-385">net start mbamagent</span></span>**

9.  <span data-ttu-id="5411d-386">若要刪除忽略的註冊表值，請執行 Regedit.exe，然後前往 HKLM\\SOFTWARE\\Microsoft 登錄機碼目。</span><span class="sxs-lookup"><span data-stu-id="5411d-386">To delete the bypass registry values, run Regedit.exe, and go to the HKLM\\SOFTWARE\\Microsoft registry entry.</span></span> <span data-ttu-id="5411d-387">以滑鼠右鍵按一下 **[管理及** 管理及管理管理及管理管理> 節點，然後按一下 **[刪除**。</span><span class="sxs-lookup"><span data-stu-id="5411d-387">Right-click the **MBAM** node, and then click **Delete**.</span></span>

## <a name="related-topics"></a><span data-ttu-id="5411d-388">相關主題</span><span class="sxs-lookup"><span data-stu-id="5411d-388">Related topics</span></span>

[<span data-ttu-id="5411d-389">部署 MBAM 2.5 用戶端</span><span class="sxs-lookup"><span data-stu-id="5411d-389">Deploying the MBAM 2.5 Client</span></span>](deploying-the-mbam-25-client.md)

[<span data-ttu-id="5411d-390">MBAM 2.5 用戶端部署規劃</span><span class="sxs-lookup"><span data-stu-id="5411d-390">Planning for MBAM 2.5 Client Deployment</span></span>](planning-for-mbam-25-client-deployment.md)

## <a name="got-a-suggestion-for-mbam"></a><span data-ttu-id="5411d-391">有關于 MM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="5411d-391">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="5411d-392">在這裡新增或投票支援 [建議](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)。</span><span class="sxs-lookup"><span data-stu-id="5411d-392">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span>
- <span data-ttu-id="5411d-393">針對的為 ：針對[的為 ：使用 ：：使用 ：。](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)</span><span class="sxs-lookup"><span data-stu-id="5411d-393">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>
