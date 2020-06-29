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
ms.openlocfilehash: 4b2cbf333c705088d0a068521fb65e99551bb1f1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811630"
---
# <span data-ttu-id="cc3da-103">如何使用 MBAM 做為 Windows 部署的一部分來啟用 BitLocker</span><span class="sxs-lookup"><span data-stu-id="cc3da-103">How to Enable BitLocker by Using MBAM as Part of a Windows Deployment</span></span>


<span data-ttu-id="cc3da-104">本主題說明如何使用 MBAM 作為 Windows 影像和部署程式的一部分，在最終使用者的電腦上啟用 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="cc3da-104">This topic explains how to enable BitLocker on an end user's computer by using MBAM as part of your Windows imaging and deployment process.</span></span> <span data-ttu-id="cc3da-105">如果您在重新開機時看到黑屏（安裝階段結束之後），指出無法解除鎖定磁片磁碟機，請參閱在[windows 10 版本1511中使用預配 BitLocker 時，舊版的 Windows 版本不會在「安裝程式視窗和建構管理員」步驟之後啟動](https://support.microsoft.com/en-us/help/4494799/earlier-windows-versions-don-t-start-after-you-use-pre-provision-bitlo)。</span><span class="sxs-lookup"><span data-stu-id="cc3da-105">If you see a black screen at restart (after Install phase concludes) indicating that the drive cannot be unlocked, see [Earlier Windows versions don't start after "Setup Windows and Configuration Manager" step if Pre-Provision BitLocker is used with Windows 10, version 1511](https://support.microsoft.com/en-us/help/4494799/earlier-windows-versions-don-t-start-after-you-use-pre-provision-bitlo).</span></span>

**<span data-ttu-id="cc3da-106">必要條件：</span><span class="sxs-lookup"><span data-stu-id="cc3da-106">Prerequisites:</span></span>**

-   <span data-ttu-id="cc3da-107">現有的 Windows 映像部署程式– Microsoft 部署工具套件（MDT）、Microsoft System Center Configuration Manager 或其他影像工具或程式–必須在適當的地方</span><span class="sxs-lookup"><span data-stu-id="cc3da-107">An existing Windows image deployment process – Microsoft Deployment Toolkit (MDT), Microsoft System Center Configuration Manager, or some other imaging tool or process – must be in place</span></span>

-   <span data-ttu-id="cc3da-108">您必須先在 BIOS 中啟用 TPM，然後才能看到作業系統</span><span class="sxs-lookup"><span data-stu-id="cc3da-108">TPM must be enabled in the BIOS and visible to the OS</span></span>

-   <span data-ttu-id="cc3da-109">MBAM 伺服器基礎結構必須就緒且易於存取</span><span class="sxs-lookup"><span data-stu-id="cc3da-109">MBAM server infrastructure must be in place and accessible</span></span>

-   <span data-ttu-id="cc3da-110">必須建立 BitLocker 所需的系統磁碟分割</span><span class="sxs-lookup"><span data-stu-id="cc3da-110">The system partition required by BitLocker must be created</span></span>

-   <span data-ttu-id="cc3da-111">在 MBAM 中，電腦必須先加入網域，才能完全啟用 BitLocker</span><span class="sxs-lookup"><span data-stu-id="cc3da-111">The machine must be domain joined during imaging before MBAM fully enables BitLocker</span></span>

**<span data-ttu-id="cc3da-112">若要在 Windows 部署中使用 MBAM 2.5 SP1 啟用 BitLocker</span><span class="sxs-lookup"><span data-stu-id="cc3da-112">To enable BitLocker using MBAM 2.5 SP1 as part of a Windows deployment</span></span>**

1. <span data-ttu-id="cc3da-113">在 MBAM 2.5 SP1 中，在 Windows 部署期間啟用 BitLocker 的建議方法是使用 `Invoke-MbamClientDeployment.ps1` PowerShell 腳本。</span><span class="sxs-lookup"><span data-stu-id="cc3da-113">In MBAM 2.5 SP1, the recommended approach to enable BitLocker during a Windows Deployment is by using the `Invoke-MbamClientDeployment.ps1` PowerShell script.</span></span>

   -   <span data-ttu-id="cc3da-114">在 `Invoke-MbamClientDeployment.ps1` 影像處理常式期間，腳本會 Enacts BitLocker。</span><span class="sxs-lookup"><span data-stu-id="cc3da-114">The `Invoke-MbamClientDeployment.ps1` script enacts BitLocker during the imaging process.</span></span> <span data-ttu-id="cc3da-115">當 BitLocker 原則需要時，MBAM 代理程式會在網域使用者第一次登入影像之後，立即提示網域使用者建立 PIN 或密碼。</span><span class="sxs-lookup"><span data-stu-id="cc3da-115">When required by BitLocker policy, the MBAM agent immediately prompts the domain user to create a PIN or password when the domain user first logs on after imaging.</span></span>

   -   <span data-ttu-id="cc3da-116">輕鬆搭配 MDT、System Center Configuration Manager 或獨立影像處理常式使用</span><span class="sxs-lookup"><span data-stu-id="cc3da-116">Easy to use with MDT, System Center Configuration Manager, or standalone imaging processes</span></span>

   -   <span data-ttu-id="cc3da-117">與 PowerShell 2.0 或更新版本相容</span><span class="sxs-lookup"><span data-stu-id="cc3da-117">Compatible with PowerShell 2.0 or higher</span></span>

   -   <span data-ttu-id="cc3da-118">使用 TPM 金鑰保護裝置加密 OS 容量</span><span class="sxs-lookup"><span data-stu-id="cc3da-118">Encrypt OS volume with TPM key protector</span></span>

   -   <span data-ttu-id="cc3da-119">完全支援 BitLocker 預配</span><span class="sxs-lookup"><span data-stu-id="cc3da-119">Fully support BitLocker pre-provisioning</span></span>

   -   <span data-ttu-id="cc3da-120">選擇性地加密 FDDs</span><span class="sxs-lookup"><span data-stu-id="cc3da-120">Optionally encrypt FDDs</span></span>

   -   <span data-ttu-id="cc3da-121">針對 Windows 7 的託管 TPM OwnerAuth，MBAM 必須擁有 TPM 才能進行保管。</span><span class="sxs-lookup"><span data-stu-id="cc3da-121">Escrow TPM OwnerAuth For Windows 7, MBAM must own the TPM for escrow to occur.</span></span>
   <span data-ttu-id="cc3da-122">針對 Windows 8.1、Windows 10 RTM 和 Windows 10 版本1511，支援以 TPM OwnerAuth 進行保管。</span><span class="sxs-lookup"><span data-stu-id="cc3da-122">For Windows 8.1, Windows 10 RTM and Windows 10 version 1511, escrow of TPM OwnerAuth is supported.</span></span>
   <span data-ttu-id="cc3da-123">如果您使用的是 Windows 10 版本1607或更新版本，則只有 Windows 可以取得 TPM 擁有權。</span><span class="sxs-lookup"><span data-stu-id="cc3da-123">For Windows 10, version 1607 or later, only Windows can take ownership of the TPM.</span></span> <span data-ttu-id="cc3da-124">在 addiiton 中，Windows 將不會在預配 TPM 時保留 TPM 擁有者密碼。</span><span class="sxs-lookup"><span data-stu-id="cc3da-124">In addiiton, Windows will not retain the TPM owner password when provisioning the TPM.</span></span> <span data-ttu-id="cc3da-125">如需詳細資訊，請參閱[TPM 擁有者密碼](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password)。</span><span class="sxs-lookup"><span data-stu-id="cc3da-125">See [TPM owner password](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password) for further details.</span></span>

   -   <span data-ttu-id="cc3da-126">已保管的復原金鑰與復原金鑰套件</span><span class="sxs-lookup"><span data-stu-id="cc3da-126">Escrow recovery keys and recovery key packages</span></span>

   -   <span data-ttu-id="cc3da-127">立即報告加密狀態</span><span class="sxs-lookup"><span data-stu-id="cc3da-127">Report encryption status immediately</span></span>

   -   <span data-ttu-id="cc3da-128">新的 WMI 提供者</span><span class="sxs-lookup"><span data-stu-id="cc3da-128">New WMI providers</span></span>

   -   <span data-ttu-id="cc3da-129">詳細記錄</span><span class="sxs-lookup"><span data-stu-id="cc3da-129">Detailed logging</span></span>

   -   <span data-ttu-id="cc3da-130">強健的錯誤處理</span><span class="sxs-lookup"><span data-stu-id="cc3da-130">Robust error handling</span></span>

   <span data-ttu-id="cc3da-131">您可以 `Invoke-MbamClientDeployment.ps1` 從[Microsoft.com 下載中心](https://www.microsoft.com/download/details.aspx?id=54439)下載腳本。</span><span class="sxs-lookup"><span data-stu-id="cc3da-131">You can download the `Invoke-MbamClientDeployment.ps1` script from [Microsoft.com Download Center](https://www.microsoft.com/download/details.aspx?id=54439).</span></span> <span data-ttu-id="cc3da-132">這是您的部署系統將呼叫以設定 BitLocker 磁碟機加密的主要腳本，以及使用 MBAM 伺服器來記錄復原金鑰。</span><span class="sxs-lookup"><span data-stu-id="cc3da-132">This is the main script that your deployment system will call to configure BitLocker drive encryption and record recovery keys with the MBAM Server.</span></span>

   <span data-ttu-id="cc3da-133">**MBAM 的 WMI 部署方法：** 已在 MBAM 2.5 SP1 中新增下列 WMI 方法，以支援使用 PowerShell 腳本啟用 BitLocker `Invoke-MbamClientDeployment.ps1` 。</span><span class="sxs-lookup"><span data-stu-id="cc3da-133">**WMI deployment methods for MBAM:** The following WMI methods have been added in MBAM 2.5 SP1 to support enabling BitLocker by using the `Invoke-MbamClientDeployment.ps1` PowerShell script.</span></span>

   <a href="" id="mbam-machine-wmi-class"></a><span data-ttu-id="cc3da-134">**MBAM \ _MACHINE WMI 類別** 
   **PrepareTpmAndEscrowOwnerAuth：** 讀取 TPM OwnerAuth，並使用 MBAM 復原服務將它傳送到 MBAM 復原資料庫。</span><span class="sxs-lookup"><span data-stu-id="cc3da-134">**MBAM\_Machine WMI Class**
**PrepareTpmAndEscrowOwnerAuth:** Reads the TPM OwnerAuth and sends it to the MBAM recovery database by using the MBAM recovery service.</span></span> <span data-ttu-id="cc3da-135">如果 TPM 不是擁有且自動預配未開啟，它會產生 TPM OwnerAuth 並取得擁有權。</span><span class="sxs-lookup"><span data-stu-id="cc3da-135">If the TPM is not owned and auto-provisioning is not on, it generates a TPM OwnerAuth and takes ownership.</span></span> <span data-ttu-id="cc3da-136">如果失敗，則會傳回錯誤代碼以進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="cc3da-136">If it fails, an error code is returned for troubleshooting.</span></span>

   <span data-ttu-id="cc3da-137">**記事**如果您使用的是 Windows 10 版本1607或更新版本，則只有 Windows 可以取得 TPM 擁有權。</span><span class="sxs-lookup"><span data-stu-id="cc3da-137">**Note** For Windows 10, version 1607 or later, only Windows can take ownership of the TPM.</span></span> <span data-ttu-id="cc3da-138">在 addiiton 中，Windows 將不會在預配 TPM 時保留 TPM 擁有者密碼。</span><span class="sxs-lookup"><span data-stu-id="cc3da-138">In addiiton, Windows will not retain the TPM owner password when provisioning the TPM.</span></span> <span data-ttu-id="cc3da-139">如需詳細資訊，請參閱[TPM 擁有者密碼](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password)。</span><span class="sxs-lookup"><span data-stu-id="cc3da-139">See [TPM owner password](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password) for further details.</span></span>

| <span data-ttu-id="cc3da-140">參數</span><span class="sxs-lookup"><span data-stu-id="cc3da-140">Parameter</span></span> | <span data-ttu-id="cc3da-141">描述</span><span class="sxs-lookup"><span data-stu-id="cc3da-141">Description</span></span> |
| -------- | ----------- |
| <span data-ttu-id="cc3da-142">RecoveryServiceEndPoint</span><span class="sxs-lookup"><span data-stu-id="cc3da-142">RecoveryServiceEndPoint</span></span> | <span data-ttu-id="cc3da-143">指定 MBAM 復原服務端點的字串。</span><span class="sxs-lookup"><span data-stu-id="cc3da-143">A string specifying the MBAM recovery service endpoint.</span></span> |

<span data-ttu-id="cc3da-144">以下是常見的錯誤訊息清單：</span><span class="sxs-lookup"><span data-stu-id="cc3da-144">Here are a list of common error messages:</span></span>

| <span data-ttu-id="cc3da-145">常見傳回值</span><span class="sxs-lookup"><span data-stu-id="cc3da-145">Common return values</span></span> | <span data-ttu-id="cc3da-146">錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="cc3da-146">Error message</span></span> |
| -------------------- | ------------- |
|  **<span data-ttu-id="cc3da-147">S_OK</span><span class="sxs-lookup"><span data-stu-id="cc3da-147">S_OK</span></span>**<br /><span data-ttu-id="cc3da-148">0（0x0）</span><span class="sxs-lookup"><span data-stu-id="cc3da-148">0 (0x0)</span></span> | <span data-ttu-id="cc3da-149">方法已成功完成。</span><span class="sxs-lookup"><span data-stu-id="cc3da-149">The method was successful.</span></span> |
| **<span data-ttu-id="cc3da-150">MBAM_E_TPM_NOT_PRESENT</span><span class="sxs-lookup"><span data-stu-id="cc3da-150">MBAM_E_TPM_NOT_PRESENT</span></span>**<br /><span data-ttu-id="cc3da-151">2147746304（0x80040200）</span><span class="sxs-lookup"><span data-stu-id="cc3da-151">2147746304 (0x80040200)</span></span> | <span data-ttu-id="cc3da-152">電腦中不存在 TPM，或 BIOS 設定中已停用 TPM。</span><span class="sxs-lookup"><span data-stu-id="cc3da-152">TPM is not present in the computer or is disabled in the BIOS configuration.</span></span> |
| **<span data-ttu-id="cc3da-153">MBAM_E_TPM_INCORRECT_STATE</span><span class="sxs-lookup"><span data-stu-id="cc3da-153">MBAM_E_TPM_INCORRECT_STATE</span></span>**<br /><span data-ttu-id="cc3da-154">2147746305（0x80040201）</span><span class="sxs-lookup"><span data-stu-id="cc3da-154">2147746305 (0x80040201)</span></span> | <span data-ttu-id="cc3da-155">TPM 不處於正確的狀態（啟用、啟動且允許擁有者安裝）。</span><span class="sxs-lookup"><span data-stu-id="cc3da-155">TPM is not in the correct state (enabled, activated and owner installation allowed).</span></span> |
| **<span data-ttu-id="cc3da-156">MBAM_E_TPM_AUTO_PROVISIONING_PENDING</span><span class="sxs-lookup"><span data-stu-id="cc3da-156">MBAM_E_TPM_AUTO_PROVISIONING_PENDING</span></span>**<br /><span data-ttu-id="cc3da-157">2147746306（0x80040202）</span><span class="sxs-lookup"><span data-stu-id="cc3da-157">2147746306 (0x80040202)</span></span> | <span data-ttu-id="cc3da-158">MBAM 無法取得 TPM 的擁有權，因為自動配為擱置中。</span><span class="sxs-lookup"><span data-stu-id="cc3da-158">MBAM cannot take ownership of TPM because auto-provisioning is pending.</span></span> <span data-ttu-id="cc3da-159">自動預配完成後再試一次。</span><span class="sxs-lookup"><span data-stu-id="cc3da-159">Try again after auto-provisioning is completed.</span></span> |
| **<span data-ttu-id="cc3da-160">MBAM_E_TPM_OWNERAUTH_READFAIL</span><span class="sxs-lookup"><span data-stu-id="cc3da-160">MBAM_E_TPM_OWNERAUTH_READFAIL</span></span>**<br /><span data-ttu-id="cc3da-161">2147746307（0x80040203）</span><span class="sxs-lookup"><span data-stu-id="cc3da-161">2147746307 (0x80040203)</span></span> | <span data-ttu-id="cc3da-162">MBAM 無法讀取 TPM 擁有者授權值。</span><span class="sxs-lookup"><span data-stu-id="cc3da-162">MBAM cannot read the TPM owner authorization value.</span></span> <span data-ttu-id="cc3da-163">此值可能已在成功進行委託之後被移除。</span><span class="sxs-lookup"><span data-stu-id="cc3da-163">The value might have been removed after a successful escrow.</span></span> <span data-ttu-id="cc3da-164">在 Windows 7 上，如果 TPM 是由其他人所擁有，則 MBAM 無法讀取這個值。</span><span class="sxs-lookup"><span data-stu-id="cc3da-164">On Windows 7, MBAM cannot read the value if the TPM is owned by others.</span></span> |
| **<span data-ttu-id="cc3da-165">MBAM_E_REBOOT_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="cc3da-165">MBAM_E_REBOOT_REQUIRED</span></span>**<br /><span data-ttu-id="cc3da-166">2147746308（0x80040204）</span><span class="sxs-lookup"><span data-stu-id="cc3da-166">2147746308 (0x80040204)</span></span> | <span data-ttu-id="cc3da-167">必須重新開機電腦，才能將 TPM 設定為正確的狀態。</span><span class="sxs-lookup"><span data-stu-id="cc3da-167">The computer must be restarted to set TPM to the correct state.</span></span> <span data-ttu-id="cc3da-168">您可能需要手動重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="cc3da-168">You might need to manually reboot the computer.</span></span> |
| **<span data-ttu-id="cc3da-169">MBAM_E_SHUTDOWN_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="cc3da-169">MBAM_E_SHUTDOWN_REQUIRED</span></span>**<br /><span data-ttu-id="cc3da-170">2147746309（0x80040205）</span><span class="sxs-lookup"><span data-stu-id="cc3da-170">2147746309 (0x80040205)</span></span> | <span data-ttu-id="cc3da-171">電腦必須關閉並再次開啟，才能將 TPM 設定為正確的狀態。</span><span class="sxs-lookup"><span data-stu-id="cc3da-171">The computer must be shut down and turned back on to set TPM to the correct state.</span></span> <span data-ttu-id="cc3da-172">您可能需要手動重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="cc3da-172">You might need to manually reboot the computer.</span></span> |
| **<span data-ttu-id="cc3da-173">WS_E_ENDPOINT_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="cc3da-173">WS_E_ENDPOINT_ACCESS_DENIED</span></span>**<br /><span data-ttu-id="cc3da-174">2151481349（0x803D0005）</span><span class="sxs-lookup"><span data-stu-id="cc3da-174">2151481349 (0x803D0005)</span></span> | <span data-ttu-id="cc3da-175">遠端端點拒絕存取。</span><span class="sxs-lookup"><span data-stu-id="cc3da-175">Access was denied by the remote endpoint.</span></span> |
| **<span data-ttu-id="cc3da-176">WS_E_ENDPOINT_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="cc3da-176">WS_E_ENDPOINT_NOT_FOUND</span></span>**<br /><span data-ttu-id="cc3da-177">2151481357（0x803D000D）</span><span class="sxs-lookup"><span data-stu-id="cc3da-177">2151481357 (0x803D000D)</span></span> | <span data-ttu-id="cc3da-178">遠端端點不存在或無法找到。</span><span class="sxs-lookup"><span data-stu-id="cc3da-178">The remote endpoint does not exist or could not be located.</span></span> |
| <span data-ttu-id="cc3da-179">\* \* WS_E_ENDPOINT_FAILURE</span><span class="sxs-lookup"><span data-stu-id="cc3da-179">\*\*WS_E_ENDPOINT_FAILURE</span></span><br /><span data-ttu-id="cc3da-180">2151481357（0x803D000F）</span><span class="sxs-lookup"><span data-stu-id="cc3da-180">2151481357 (0x803D000F)</span></span> | <span data-ttu-id="cc3da-181">遠端端點無法處理要求。</span><span class="sxs-lookup"><span data-stu-id="cc3da-181">The remote endpoint could not process the request.</span></span> |
| **<span data-ttu-id="cc3da-182">WS_E_ENDPOINT_UNREACHABLE</span><span class="sxs-lookup"><span data-stu-id="cc3da-182">WS_E_ENDPOINT_UNREACHABLE</span></span>**<br /><span data-ttu-id="cc3da-183">2151481360（0x803D0010）</span><span class="sxs-lookup"><span data-stu-id="cc3da-183">2151481360 (0x803D0010)</span></span> | <span data-ttu-id="cc3da-184">無法到達遠端端點。</span><span class="sxs-lookup"><span data-stu-id="cc3da-184">The remote endpoint was not reachable.</span></span> |
| **<span data-ttu-id="cc3da-185">WS_E_ENDPOINT_FAULT_RECEIVED</span><span class="sxs-lookup"><span data-stu-id="cc3da-185">WS_E_ENDPOINT_FAULT_RECEIVED</span></span>**<br /><span data-ttu-id="cc3da-186">2151481363（0x803D0013）</span><span class="sxs-lookup"><span data-stu-id="cc3da-186">2151481363 (0x803D0013)</span></span> | <span data-ttu-id="cc3da-187">從遠端端點收到包含錯誤的郵件。</span><span class="sxs-lookup"><span data-stu-id="cc3da-187">A message containing a fault was received from the remote endpoint.</span></span> <span data-ttu-id="cc3da-188">請確定您連線到正確的服務端點。</span><span class="sxs-lookup"><span data-stu-id="cc3da-188">Make sure you are connecting to the correct service endpoint.</span></span> |
| <span data-ttu-id="cc3da-189">**WS_E_INVALID_ENDPOINT_URL** 2151481376 （0x803D0020）</span><span class="sxs-lookup"><span data-stu-id="cc3da-189">**WS_E_INVALID_ENDPOINT_URL** 2151481376 (0x803D0020)</span></span> | <span data-ttu-id="cc3da-190">端點位址 URL 無效。</span><span class="sxs-lookup"><span data-stu-id="cc3da-190">The endpoint address URL is not valid.</span></span> <span data-ttu-id="cc3da-191">URL 必須以 "HTTP" 或 "HTTPs" 開頭。</span><span class="sxs-lookup"><span data-stu-id="cc3da-191">The URL must start with “http” or “https”.</span></span> |

   <span data-ttu-id="cc3da-192">**ReportStatus：** 使用 MBAM 狀態報表服務，讀取卷的合規性狀態，並將它傳送到 MBAM 合規性狀態資料庫。</span><span class="sxs-lookup"><span data-stu-id="cc3da-192">**ReportStatus:** Reads the compliance status of the volume and sends it to the MBAM compliance status database by using the MBAM status reporting service.</span></span> <span data-ttu-id="cc3da-193">狀態包括密碼強度、保護器類型、保護程式狀態與加密狀態。</span><span class="sxs-lookup"><span data-stu-id="cc3da-193">The status includes cipher strength, protector type, protector state and encryption state.</span></span> <span data-ttu-id="cc3da-194">如果失敗，則會傳回錯誤代碼以進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="cc3da-194">If it fails, an error code is returned for troubleshooting.</span></span>

   | <span data-ttu-id="cc3da-195">參數</span><span class="sxs-lookup"><span data-stu-id="cc3da-195">Parameter</span></span> | <span data-ttu-id="cc3da-196">描述</span><span class="sxs-lookup"><span data-stu-id="cc3da-196">Description</span></span> |
   | --------- | ----------- |
   | <span data-ttu-id="cc3da-197">ReportingServiceEndPoint</span><span class="sxs-lookup"><span data-stu-id="cc3da-197">ReportingServiceEndPoint</span></span> | <span data-ttu-id="cc3da-198">指定 MBAM 狀態報表服務端點的字串。</span><span class="sxs-lookup"><span data-stu-id="cc3da-198">A string specifying the MBAM status reporting service endpoint.</span></span> |

   <span data-ttu-id="cc3da-199">以下是常見的錯誤訊息清單：</span><span class="sxs-lookup"><span data-stu-id="cc3da-199">Here are a list of common error messages:</span></span>

   | <span data-ttu-id="cc3da-200">常見傳回值</span><span class="sxs-lookup"><span data-stu-id="cc3da-200">Common return values</span></span> | <span data-ttu-id="cc3da-201">錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="cc3da-201">Error message</span></span> |
   | -------------------- | ------------- |
   | **<span data-ttu-id="cc3da-202">S_OK</span><span class="sxs-lookup"><span data-stu-id="cc3da-202">S_OK</span></span>**<br /> <span data-ttu-id="cc3da-203">0（0x0）</span><span class="sxs-lookup"><span data-stu-id="cc3da-203">0 (0x0)</span></span> | <span data-ttu-id="cc3da-204">方法成功</span><span class="sxs-lookup"><span data-stu-id="cc3da-204">The method was successful</span></span> |
   | **<span data-ttu-id="cc3da-205">WS_E_ENDPOINT_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="cc3da-205">WS_E_ENDPOINT_ACCESS_DENIED</span></span>**<br /><span data-ttu-id="cc3da-206">2151481349（0x803D0005）</span><span class="sxs-lookup"><span data-stu-id="cc3da-206">2151481349 (0x803D0005)</span></span> | <span data-ttu-id="cc3da-207">遠端端點拒絕存取。</span><span class="sxs-lookup"><span data-stu-id="cc3da-207">Access was denied by the remote endpoint.</span></span>|
   | **<span data-ttu-id="cc3da-208">WS_E_ENDPOINT_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="cc3da-208">WS_E_ENDPOINT_NOT_FOUND</span></span>**<br /><span data-ttu-id="cc3da-209">2151481357（0x803D000D）</span><span class="sxs-lookup"><span data-stu-id="cc3da-209">2151481357 (0x803D000D)</span></span> | <span data-ttu-id="cc3da-210">遠端端點不存在或無法找到。</span><span class="sxs-lookup"><span data-stu-id="cc3da-210">The remote endpoint does not exist or could not be located.</span></span> |
   | **<span data-ttu-id="cc3da-211">WS_E_ENDPOINT_FAILURE</span><span class="sxs-lookup"><span data-stu-id="cc3da-211">WS_E_ENDPOINT_FAILURE</span></span>**<br /> <span data-ttu-id="cc3da-212">2151481357（0x803D000F）</span><span class="sxs-lookup"><span data-stu-id="cc3da-212">2151481357 (0x803D000F)</span></span> | <span data-ttu-id="cc3da-213">遠端端點無法處理要求。</span><span class="sxs-lookup"><span data-stu-id="cc3da-213">The remote endpoint could not process the request.</span></span> |
   | **<span data-ttu-id="cc3da-214">WS_E_ENDPOINT_UNREACHABLE</span><span class="sxs-lookup"><span data-stu-id="cc3da-214">WS_E_ENDPOINT_UNREACHABLE</span></span>**<br /><span data-ttu-id="cc3da-215">2151481360（0x803D0010）</span><span class="sxs-lookup"><span data-stu-id="cc3da-215">2151481360 (0x803D0010)</span></span> | <span data-ttu-id="cc3da-216">無法到達遠端端點。</span><span class="sxs-lookup"><span data-stu-id="cc3da-216">The remote endpoint was not reachable.</span></span> |
   | **<span data-ttu-id="cc3da-217">WS_E_ENDPOINT_FAULT_RECEIVED</span><span class="sxs-lookup"><span data-stu-id="cc3da-217">WS_E_ENDPOINT_FAULT_RECEIVED</span></span>**<br /><span data-ttu-id="cc3da-218">2151481363（0x803D0013）</span><span class="sxs-lookup"><span data-stu-id="cc3da-218">2151481363 (0x803D0013)</span></span> | <span data-ttu-id="cc3da-219">從遠端端點收到包含錯誤的郵件。</span><span class="sxs-lookup"><span data-stu-id="cc3da-219">A message containing a fault was received from the remote endpoint.</span></span> <span data-ttu-id="cc3da-220">請確定您連線到正確的服務端點。</span><span class="sxs-lookup"><span data-stu-id="cc3da-220">Make sure you are connecting to the correct service endpoint.</span></span> |
   | **<span data-ttu-id="cc3da-221">WS_E_INVALID_ENDPOINT_URL</span><span class="sxs-lookup"><span data-stu-id="cc3da-221">WS_E_INVALID_ENDPOINT_URL</span></span>**<br /><span data-ttu-id="cc3da-222">2151481376（0x803D0020）</span><span class="sxs-lookup"><span data-stu-id="cc3da-222">2151481376 (0x803D0020)</span></span> | <span data-ttu-id="cc3da-223">端點位址 URL 無效。</span><span class="sxs-lookup"><span data-stu-id="cc3da-223">The endpoint address URL is not valid.</span></span> <span data-ttu-id="cc3da-224">URL 必須以 "HTTP" 或 "HTTPs" 開頭。</span><span class="sxs-lookup"><span data-stu-id="cc3da-224">The URL must start with “http” or “https”.</span></span> |

   <a href="" id="mbam-volume-wmi-class"></a><span data-ttu-id="cc3da-225">**MBAM \ _VOLUME WMI Class** **EscrowRecoveryKey：** 讀取大量的復原數位密碼和金鑰套件，並使用 MBAM 復原服務將其傳送至 MBAM 復原資料庫。</span><span class="sxs-lookup"><span data-stu-id="cc3da-225">**MBAM\_Volume WMI Class** **EscrowRecoveryKey:** Reads the recovery numerical password and key package of the volume and sends them to the MBAM recovery database by using the MBAM recovery service.</span></span> <span data-ttu-id="cc3da-226">如果失敗，則會傳回錯誤代碼以進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="cc3da-226">If it fails, an error code is returned for troubleshooting.</span></span>

   | <span data-ttu-id="cc3da-227">參數</span><span class="sxs-lookup"><span data-stu-id="cc3da-227">Parameter</span></span> | <span data-ttu-id="cc3da-228">描述</span><span class="sxs-lookup"><span data-stu-id="cc3da-228">Description</span></span> |
   | --------- | ----------- |
   | <span data-ttu-id="cc3da-229">RecoveryServiceEndPoint</span><span class="sxs-lookup"><span data-stu-id="cc3da-229">RecoveryServiceEndPoint</span></span> | <span data-ttu-id="cc3da-230">指定 MBAM 復原服務端點的字串。</span><span class="sxs-lookup"><span data-stu-id="cc3da-230">A string specifying the MBAM recovery service endpoint.</span></span> |

   <span data-ttu-id="cc3da-231">以下是常見的錯誤訊息清單：</span><span class="sxs-lookup"><span data-stu-id="cc3da-231">Here are a list of common error messages:</span></span>

   | <span data-ttu-id="cc3da-232">常見傳回值</span><span class="sxs-lookup"><span data-stu-id="cc3da-232">Common return values</span></span> | <span data-ttu-id="cc3da-233">錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="cc3da-233">Error message</span></span> |
   | -------------------- | ------------- |
   | **<span data-ttu-id="cc3da-234">S_OK</span><span class="sxs-lookup"><span data-stu-id="cc3da-234">S_OK</span></span>**<br /><span data-ttu-id="cc3da-235">0（0x0）</span><span class="sxs-lookup"><span data-stu-id="cc3da-235">0 (0x0)</span></span> | <span data-ttu-id="cc3da-236">方法成功</span><span class="sxs-lookup"><span data-stu-id="cc3da-236">The method was successful</span></span> |
   | **<span data-ttu-id="cc3da-237">FVE_E_LOCKED_VOLUME</span><span class="sxs-lookup"><span data-stu-id="cc3da-237">FVE_E_LOCKED_VOLUME</span></span>**<br /><span data-ttu-id="cc3da-238">2150694912（0x80310000）</span><span class="sxs-lookup"><span data-stu-id="cc3da-238">2150694912 (0x80310000)</span></span> | <span data-ttu-id="cc3da-239">該卷已鎖定。</span><span class="sxs-lookup"><span data-stu-id="cc3da-239">The volume is locked.</span></span> |
   | **<span data-ttu-id="cc3da-240">FVE_E_PROTECTOR_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="cc3da-240">FVE_E_PROTECTOR_NOT_FOUND</span></span>**<br /><span data-ttu-id="cc3da-241">2150694963（0x80310033）</span><span class="sxs-lookup"><span data-stu-id="cc3da-241">2150694963 (0x80310033)</span></span> | <span data-ttu-id="cc3da-242">找不到該卷的數位密碼保護器。</span><span class="sxs-lookup"><span data-stu-id="cc3da-242">A Numerical Password protector was not found for the volume.</span></span> |
   | **<span data-ttu-id="cc3da-243">WS_E_ENDPOINT_ACCESS_DENIED</span><span class="sxs-lookup"><span data-stu-id="cc3da-243">WS_E_ENDPOINT_ACCESS_DENIED</span></span>**<br /><span data-ttu-id="cc3da-244">2151481349（0x803D0005）</span><span class="sxs-lookup"><span data-stu-id="cc3da-244">2151481349 (0x803D0005)</span></span> | <span data-ttu-id="cc3da-245">遠端端點拒絕存取。</span><span class="sxs-lookup"><span data-stu-id="cc3da-245">Access was denied by the remote endpoint.</span></span> |
   | **<span data-ttu-id="cc3da-246">WS_E_ENDPOINT_NOT_FOUND</span><span class="sxs-lookup"><span data-stu-id="cc3da-246">WS_E_ENDPOINT_NOT_FOUND</span></span>**<br /><span data-ttu-id="cc3da-247">2151481357（0x803D000D）</span><span class="sxs-lookup"><span data-stu-id="cc3da-247">2151481357 (0x803D000D)</span></span> | <span data-ttu-id="cc3da-248">遠端端點不存在或無法找到。</span><span class="sxs-lookup"><span data-stu-id="cc3da-248">The remote endpoint does not exist or could not be located.</span></span> |
   | **<span data-ttu-id="cc3da-249">WS_E_ENDPOINT_FAILURE</span><span class="sxs-lookup"><span data-stu-id="cc3da-249">WS_E_ENDPOINT_FAILURE</span></span>**<br /><span data-ttu-id="cc3da-250">2151481357（0x803D000F）</span><span class="sxs-lookup"><span data-stu-id="cc3da-250">2151481357 (0x803D000F)</span></span> | <span data-ttu-id="cc3da-251">遠端端點無法處理要求。</span><span class="sxs-lookup"><span data-stu-id="cc3da-251">The remote endpoint could not process the request.</span></span> |
   | **<span data-ttu-id="cc3da-252">WS_E_ENDPOINT_UNREACHABLE</span><span class="sxs-lookup"><span data-stu-id="cc3da-252">WS_E_ENDPOINT_UNREACHABLE</span></span>**<br /><span data-ttu-id="cc3da-253">2151481360（0x803D0010）</span><span class="sxs-lookup"><span data-stu-id="cc3da-253">2151481360 (0x803D0010)</span></span> | <span data-ttu-id="cc3da-254">無法到達遠端端點。</span><span class="sxs-lookup"><span data-stu-id="cc3da-254">The remote endpoint was not reachable.</span></span> |
   | **<span data-ttu-id="cc3da-255">WS_E_ENDPOINT_FAULT_RECEIVED</span><span class="sxs-lookup"><span data-stu-id="cc3da-255">WS_E_ENDPOINT_FAULT_RECEIVED</span></span>**<br /><span data-ttu-id="cc3da-256">2151481363（0x803D0013）</span><span class="sxs-lookup"><span data-stu-id="cc3da-256">2151481363 (0x803D0013)</span></span> | <span data-ttu-id="cc3da-257">從遠端端點收到包含錯誤的郵件。</span><span class="sxs-lookup"><span data-stu-id="cc3da-257">A message containing a fault was received from the remote endpoint.</span></span> <span data-ttu-id="cc3da-258">請確定您連線到正確的服務端點。</span><span class="sxs-lookup"><span data-stu-id="cc3da-258">Make sure you are connecting to the correct service endpoint.</span></span> |
   | **<span data-ttu-id="cc3da-259">WS_E_INVALID_ENDPOINT_URL</span><span class="sxs-lookup"><span data-stu-id="cc3da-259">WS_E_INVALID_ENDPOINT_URL</span></span>**<br /><span data-ttu-id="cc3da-260">2151481376（0x803D0020）</span><span class="sxs-lookup"><span data-stu-id="cc3da-260">2151481376 (0x803D0020)</span></span> | <span data-ttu-id="cc3da-261">端點位址 URL 無效。</span><span class="sxs-lookup"><span data-stu-id="cc3da-261">The endpoint address URL is not valid.</span></span> <span data-ttu-id="cc3da-262">URL 必須以 "HTTP" 或 "HTTPs" 開頭。</span><span class="sxs-lookup"><span data-stu-id="cc3da-262">The URL must start with “http” or “https”.</span></span> |
     

2. **<span data-ttu-id="cc3da-263">使用 Microsoft 部署工具套件（MDT）和 PowerShell 部署 MBAM</span><span class="sxs-lookup"><span data-stu-id="cc3da-263">Deploy MBAM by using Microsoft Deployment Toolkit (MDT) and PowerShell</span></span>**

   1.  <span data-ttu-id="cc3da-264">在 MDT 中，建立新的部署共用或開啟現有的部署共用。</span><span class="sxs-lookup"><span data-stu-id="cc3da-264">In MDT, create a new deployment share or open an existing deployment share.</span></span>

       **<span data-ttu-id="cc3da-265">注意</span><span class="sxs-lookup"><span data-stu-id="cc3da-265">Note</span></span>**  
       <span data-ttu-id="cc3da-266">`Invoke-MbamClientDeployment.ps1`PowerShell 腳本可以與任何影像進程或工具搭配使用。</span><span class="sxs-lookup"><span data-stu-id="cc3da-266">The `Invoke-MbamClientDeployment.ps1` PowerShell script can be used with any imaging process or tool.</span></span> <span data-ttu-id="cc3da-267">本節說明如何使用 MDT 整合它，但步驟與將它與任何其他進程或工具整合的方式類似。</span><span class="sxs-lookup"><span data-stu-id="cc3da-267">This section shows how to integrate it by using MDT, but the steps are similar to integrating it with any other process or tool.</span></span>

       **<span data-ttu-id="cc3da-268">警告</span><span class="sxs-lookup"><span data-stu-id="cc3da-268">Caution</span></span>**  
       <span data-ttu-id="cc3da-269">如果您使用的是 BitLocker 預配（WinPE），且想要維持 TPM 擁有者授權值，您必須 `SaveWinPETpmOwnerAuth.wsf` 立即在 WinPE 中新增腳本，然後才能在完整作業系統中重新開機安裝。</span><span class="sxs-lookup"><span data-stu-id="cc3da-269">If you are using BitLocker pre-provisioning (WinPE) and want to maintain the TPM owner authorization value, you must add the `SaveWinPETpmOwnerAuth.wsf` script in WinPE immediately before the installation reboots into the full operating system.</span></span> **<span data-ttu-id="cc3da-270">如果您不使用此腳本，您將會在重新開機時遺失 TPM 擁有者授權值。</span><span class="sxs-lookup"><span data-stu-id="cc3da-270">If you do not use this script, you will lose the TPM owner authorization value on reboot.</span></span>**

   2.  <span data-ttu-id="cc3da-271">複製 `Invoke-MbamClientDeployment.ps1` 至\*\* &lt; DeploymentShare &gt; \\Scripts\*\*。</span><span class="sxs-lookup"><span data-stu-id="cc3da-271">Copy `Invoke-MbamClientDeployment.ps1` to **&lt;DeploymentShare&gt;\\Scripts**.</span></span> <span data-ttu-id="cc3da-272">如果您使用的是預配，請將檔案複製 `SaveWinPETpmOwnerAuth.wsf` 到\*\* &lt; DeploymentShare &gt; \\Scripts\*\*。</span><span class="sxs-lookup"><span data-stu-id="cc3da-272">If you are using pre-provisioning, copy the `SaveWinPETpmOwnerAuth.wsf` file into **&lt;DeploymentShare&gt;\\Scripts**.</span></span>

   3.  <span data-ttu-id="cc3da-273">將 MBAM 2.5 SP1 用戶端應用程式新增到部署共用中的 [應用程式] 節點。</span><span class="sxs-lookup"><span data-stu-id="cc3da-273">Add the MBAM 2.5 SP1 client application to the Applications node in the deployment share.</span></span>

       1.  <span data-ttu-id="cc3da-274">在 [**應用程式**] 節點底下，按一下 [**新增應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="cc3da-274">Under the **Applications** node, click **New Application**.</span></span>

       2.  <span data-ttu-id="cc3da-275">選取 [**使用來源檔案的應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="cc3da-275">Select **Application with Source Files**.</span></span> <span data-ttu-id="cc3da-276">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="cc3da-276">Click **Next**.</span></span>

       3.  <span data-ttu-id="cc3da-277">在 [**應用程式名稱**] 中，輸入 "MBAM 2.5 SP1 用戶端]。</span><span class="sxs-lookup"><span data-stu-id="cc3da-277">In **Application Name**, type “MBAM 2.5 SP1 Client”.</span></span> <span data-ttu-id="cc3da-278">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="cc3da-278">Click **Next**.</span></span>

       4.  <span data-ttu-id="cc3da-279">流覽至包含的目錄 `MBAMClientSetup-<Version>.msi` 。</span><span class="sxs-lookup"><span data-stu-id="cc3da-279">Browse to the directory containing `MBAMClientSetup-<Version>.msi`.</span></span> <span data-ttu-id="cc3da-280">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="cc3da-280">Click **Next**.</span></span>

       5.  <span data-ttu-id="cc3da-281">輸入 "MBAM 2.5 SP1 用戶端] 作為您要建立的目錄。</span><span class="sxs-lookup"><span data-stu-id="cc3da-281">Type “MBAM 2.5 SP1 Client” as the directory to create.</span></span> <span data-ttu-id="cc3da-282">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="cc3da-282">Click **Next**.</span></span>

       6.  <span data-ttu-id="cc3da-283">`msiexec /i MBAMClientSetup-<Version>.msi /quiet`在命令列中輸入。</span><span class="sxs-lookup"><span data-stu-id="cc3da-283">Enter `msiexec /i MBAMClientSetup-<Version>.msi /quiet` at the command line.</span></span> <span data-ttu-id="cc3da-284">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="cc3da-284">Click **Next**.</span></span>

       7.  <span data-ttu-id="cc3da-285">接受其餘的預設值來完成 [新增應用程式] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="cc3da-285">Accept the remaining defaults to complete the New Application wizard.</span></span>

   4.  <span data-ttu-id="cc3da-286">在 MDT 中，以滑鼠右鍵按一下部署共用的名稱，然後按一下 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="cc3da-286">In MDT, right-click the name of the deployment share and click **Properties**.</span></span> <span data-ttu-id="cc3da-287">按一下 [**規則**] 索引標籤。新增下列各列：</span><span class="sxs-lookup"><span data-stu-id="cc3da-287">Click the **Rules** tab. Add the following lines:</span></span>

       `SkipBitLocker=YES``BDEInstall=TPM``BDEInstallSuppress=NO``BDEWaitForEncryption=YES`

       <span data-ttu-id="cc3da-288">按一下 [確定] 以關閉視窗。</span><span class="sxs-lookup"><span data-stu-id="cc3da-288">Click OK to close the window.</span></span>

   5.  <span data-ttu-id="cc3da-289">在 [任務順序] 節點底下，編輯 Windows 部署所用的現有任務序列。</span><span class="sxs-lookup"><span data-stu-id="cc3da-289">Under the Task Sequences node, edit an existing task sequence used for Windows Deployment.</span></span> <span data-ttu-id="cc3da-290">如果您想要的話，您可以用滑鼠右鍵按一下 [**任務序列**] 節點，選取 [**新增任務序列**]，然後完成嚮導，以建立新的任務序列。</span><span class="sxs-lookup"><span data-stu-id="cc3da-290">If you want, you can create a new task sequence by right-clicking the **Task Sequences** node, selecting **New Task Sequence**, and completing the wizard.</span></span>

       <span data-ttu-id="cc3da-291">在所選任務序列的 [**任務順序**] 索引標籤上，執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="cc3da-291">On the **Task Sequence** tab of the selected task sequence, perform these steps:</span></span>

       1.  <span data-ttu-id="cc3da-292">如果您想在 WinPE 中啟用 BitLocker，且只加密已使用的空間，請在 [**預先安裝**] 資料夾底下啟用 [**啟用 bitlocker （離線）** ] 選項。</span><span class="sxs-lookup"><span data-stu-id="cc3da-292">Under the **Preinstall** folder, enable the optional task **Enable BitLocker (Offline)** if you want BitLocker enabled in WinPE, which encrypts used space only.</span></span>

       2.  <span data-ttu-id="cc3da-293">若要在使用預配時保留 TPM OwnerAuth，允許 MBAM 稍後進行保管，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="cc3da-293">To persist TPM OwnerAuth when using pre-provisioning, allowing MBAM to escrow it later, do the following:</span></span>

           1.  <span data-ttu-id="cc3da-294">尋找 [**安裝作業系統**] 步驟</span><span class="sxs-lookup"><span data-stu-id="cc3da-294">Find the **Install Operating System** step</span></span>

           2.  <span data-ttu-id="cc3da-295">在其後加入新的**執行命令列**步驟</span><span class="sxs-lookup"><span data-stu-id="cc3da-295">Add a new **Run Command Line** step after it</span></span>

           3.  <span data-ttu-id="cc3da-296">為步驟**保留 TPM OwnerAuth**命名</span><span class="sxs-lookup"><span data-stu-id="cc3da-296">Name the step **Persist TPM OwnerAuth**</span></span>

           4.  <span data-ttu-id="cc3da-297">將命令列設定為 [ `cscript.exe "%SCRIPTROOT%/SaveWinPETpmOwnerAuth.wsf"`
            **注意事項]：** 對於 windows 10 版本1607或更新版本，只有 WINDOWS 可以取得 TPM 擁有權。</span><span class="sxs-lookup"><span data-stu-id="cc3da-297">Set the command line to `cscript.exe "%SCRIPTROOT%/SaveWinPETpmOwnerAuth.wsf"`
**Note:** For Windows 10, version 1607 or later, only Windows can take ownership of the TPM.</span></span> <span data-ttu-id="cc3da-298">在 addiiton 中，Windows 將不會在預配 TPM 時保留 TPM 擁有者密碼。</span><span class="sxs-lookup"><span data-stu-id="cc3da-298">In addiiton, Windows will not retain the TPM owner password when provisioning the TPM.</span></span> <span data-ttu-id="cc3da-299">如需詳細資訊，請參閱[TPM 擁有者密碼](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password)。</span><span class="sxs-lookup"><span data-stu-id="cc3da-299">See [TPM owner password](https://docs.microsoft.com/windows/security/hardware-protection/tpm/change-the-tpm-owner-password) for further details.</span></span>

       3.  <span data-ttu-id="cc3da-300">在 [**狀態還原**] 資料夾中，刪除 [**啟用 BitLocker** ] 任務。</span><span class="sxs-lookup"><span data-stu-id="cc3da-300">In the **State Restore** folder, delete the **Enable BitLocker** task.</span></span>

       4.  <span data-ttu-id="cc3da-301">在 [**自訂**工作] 下的 [**狀態還原**] 資料夾中，建立新的**安裝應用程式**工作，並將其命名為**安裝 MBAM Agent**。</span><span class="sxs-lookup"><span data-stu-id="cc3da-301">In the **State Restore** folder under **Custom Tasks**, create a new **Install Application** task and name it **Install MBAM Agent**.</span></span> <span data-ttu-id="cc3da-302">按一下 [**安裝單一應用程式**] 選項按鈕，然後流覽至先前建立的 MBAM 2.5 SP1 用戶端應用程式。</span><span class="sxs-lookup"><span data-stu-id="cc3da-302">Click the **Install Single Application** radio button and browse to the MBAM 2.5 SP1 client application created earlier.</span></span>

       5.  <span data-ttu-id="cc3da-303">在 [**自訂**工作] 下的 [**狀態還原**] 資料夾中，建立新的**執行 POWERSHELL 腳本**工作（在 MBAM 2.5 SP1 用戶端應用程式步驟之後），並使用下列設定（根據您的環境更新參數）：</span><span class="sxs-lookup"><span data-stu-id="cc3da-303">In the **State Restore** folder under **Custom Tasks**, create a new **Run PowerShell Script** task (after the MBAM 2.5 SP1 Client application step) with the following settings (update the parameters as appropriate for your environment):</span></span>

           -   <span data-ttu-id="cc3da-304">Name （名稱）：針對 MBAM 設定 BitLocker</span><span class="sxs-lookup"><span data-stu-id="cc3da-304">Name: Configure BitLocker for MBAM</span></span>

           -   <span data-ttu-id="cc3da-305">PowerShell 腳本：</span><span class="sxs-lookup"><span data-stu-id="cc3da-305">PowerShell script:</span></span> `Invoke-MbamClientDeployment.ps1`

           -   <span data-ttu-id="cc3da-306">參數</span><span class="sxs-lookup"><span data-stu-id="cc3da-306">Parameters:</span></span>

               <table>
               <colgroup>
               <col width="33%" />
               <col width="33%" />
               <col width="33%" />
               </colgroup>
               <tbody>
               <tr class="odd">
               <td align="left"><p><span data-ttu-id="cc3da-307">-RecoveryServiceEndpoint</span><span class="sxs-lookup"><span data-stu-id="cc3da-307">-RecoveryServiceEndpoint</span></span></p></td>
               <td align="left"><p><span data-ttu-id="cc3da-308">必要</span><span class="sxs-lookup"><span data-stu-id="cc3da-308">Required</span></span></p></td>
               <td align="left"><p><span data-ttu-id="cc3da-309">MBAM recovery 服務端點</span><span class="sxs-lookup"><span data-stu-id="cc3da-309">MBAM recovery service endpoint</span></span></p></td>
               </tr>
               <tr class="even">
               <td align="left"><p><span data-ttu-id="cc3da-310">-StatusReportingServiceEndpoint</span><span class="sxs-lookup"><span data-stu-id="cc3da-310">-StatusReportingServiceEndpoint</span></span></p></td>
               <td align="left"><p><span data-ttu-id="cc3da-311">選用</span><span class="sxs-lookup"><span data-stu-id="cc3da-311">Optional</span></span></p></td>
               <td align="left"><p><span data-ttu-id="cc3da-312">MBAM 狀態報表服務端點</span><span class="sxs-lookup"><span data-stu-id="cc3da-312">MBAM status reporting service endpoint</span></span></p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p><span data-ttu-id="cc3da-313">-EncryptionMethod</span><span class="sxs-lookup"><span data-stu-id="cc3da-313">-EncryptionMethod</span></span></p></td>
               <td align="left"><p><span data-ttu-id="cc3da-314">選用</span><span class="sxs-lookup"><span data-stu-id="cc3da-314">Optional</span></span></p></td>
               <td align="left"><p><span data-ttu-id="cc3da-315">加密方法（預設： AES 128）</span><span class="sxs-lookup"><span data-stu-id="cc3da-315">Encryption method (default: AES 128)</span></span></p></td>
               </tr>
               <tr class="even">
               <td align="left"><p><span data-ttu-id="cc3da-316">-EncryptAndEscrowDataVolume</span><span class="sxs-lookup"><span data-stu-id="cc3da-316">-EncryptAndEscrowDataVolume</span></span></p></td>
               <td align="left"><p><span data-ttu-id="cc3da-317">切換</span><span class="sxs-lookup"><span data-stu-id="cc3da-317">Switch</span></span></p></td>
               <td align="left"><p><span data-ttu-id="cc3da-318">指定加密資料量及保管資料量的資料量修復金鑰（s）</span><span class="sxs-lookup"><span data-stu-id="cc3da-318">Specify to encrypt data volume(s) and escrow data volume recovery key(s)</span></span></p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p><span data-ttu-id="cc3da-319">-WaitForEncryptionToComplete</span><span class="sxs-lookup"><span data-stu-id="cc3da-319">-WaitForEncryptionToComplete</span></span></p></td>
               <td align="left"><p><span data-ttu-id="cc3da-320">切換</span><span class="sxs-lookup"><span data-stu-id="cc3da-320">Switch</span></span></p></td>
               <td align="left"><p><span data-ttu-id="cc3da-321">指定等待加密完成</span><span class="sxs-lookup"><span data-stu-id="cc3da-321">Specify to wait for the encryption to complete</span></span></p></td>
               </tr>
               <tr class="even">
               <td align="left"><p><span data-ttu-id="cc3da-322">-DoNotResumeSuspendedEncryption</span><span class="sxs-lookup"><span data-stu-id="cc3da-322">-DoNotResumeSuspendedEncryption</span></span></p></td>
               <td align="left"><p><span data-ttu-id="cc3da-323">切換</span><span class="sxs-lookup"><span data-stu-id="cc3da-323">Switch</span></span></p></td>
               <td align="left"><p><span data-ttu-id="cc3da-324">指定部署腳本將不會繼續暫停加密</span><span class="sxs-lookup"><span data-stu-id="cc3da-324">Specify that the deployment script will not resume suspended encryption</span></span></p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p><span data-ttu-id="cc3da-325">-IgnoreEscrowOwnerAuthFailure</span><span class="sxs-lookup"><span data-stu-id="cc3da-325">-IgnoreEscrowOwnerAuthFailure</span></span></p></td>
               <td align="left"><p><span data-ttu-id="cc3da-326">切換</span><span class="sxs-lookup"><span data-stu-id="cc3da-326">Switch</span></span></p></td>
               <td align="left"><p><span data-ttu-id="cc3da-327">指定以忽略 TPM 擁有者-驗證的保管失敗。</span><span class="sxs-lookup"><span data-stu-id="cc3da-327">Specify to ignore TPM owner-auth escrow failure.</span></span> <span data-ttu-id="cc3da-328">它應該用於 MBAM 無法讀取 TPM 擁有者驗證（例如，如果已啟用 TPM 自動預配）的情況。</span><span class="sxs-lookup"><span data-stu-id="cc3da-328">It should be used in the scenarios where MBAM is not able to read the TPM owner-auth, e.g. if TPM auto provisioning is enabled</span></span></p></td>
               </tr>
               <tr class="even">
               <td align="left"><p><span data-ttu-id="cc3da-329">-IgnoreEscrowRecoveryKeyFailure</span><span class="sxs-lookup"><span data-stu-id="cc3da-329">-IgnoreEscrowRecoveryKeyFailure</span></span></p></td>
               <td align="left"><p><span data-ttu-id="cc3da-330">切換</span><span class="sxs-lookup"><span data-stu-id="cc3da-330">Switch</span></span></p></td>
               <td align="left"><p><span data-ttu-id="cc3da-331">指定以忽略大量復原金鑰的保管失敗</span><span class="sxs-lookup"><span data-stu-id="cc3da-331">Specify to ignore volume recovery key escrow failure</span></span></p></td>
               </tr>
               <tr class="odd">
               <td align="left"><p><span data-ttu-id="cc3da-332">-IgnoreReportStatusFailure</span><span class="sxs-lookup"><span data-stu-id="cc3da-332">-IgnoreReportStatusFailure</span></span></p></td>
               <td align="left"><p><span data-ttu-id="cc3da-333">切換</span><span class="sxs-lookup"><span data-stu-id="cc3da-333">Switch</span></span></p></td>
               <td align="left"><p><span data-ttu-id="cc3da-334">[指定以忽略狀態報表失敗]</span><span class="sxs-lookup"><span data-stu-id="cc3da-334">Specify to ignore status reporting failure</span></span></p></td>
               </tr>
               </tbody>
               </table>

                 

**<span data-ttu-id="cc3da-335">若要在 Windows 部署中使用 MBAM 2.5 或較舊版本啟用 BitLocker</span><span class="sxs-lookup"><span data-stu-id="cc3da-335">To enable BitLocker using MBAM 2.5 or earlier as part of a Windows deployment</span></span>**

1.  <span data-ttu-id="cc3da-336">安裝 MBAM 用戶端。</span><span class="sxs-lookup"><span data-stu-id="cc3da-336">Install the MBAM Client.</span></span> <span data-ttu-id="cc3da-337">如需相關指示，請參閱[如何使用命令列部署 MBAM 用戶端](how-to-deploy-the-mbam-client-by-using-a-command-line.md)。</span><span class="sxs-lookup"><span data-stu-id="cc3da-337">For instructions, see [How to Deploy the MBAM Client by Using a Command Line](how-to-deploy-the-mbam-client-by-using-a-command-line.md).</span></span>

2.  <span data-ttu-id="cc3da-338">將電腦加入網域（建議使用）。</span><span class="sxs-lookup"><span data-stu-id="cc3da-338">Join the computer to a domain (recommended).</span></span>

    -   <span data-ttu-id="cc3da-339">如果電腦未加入網域，則無法將恢復密碼儲存在 MBAM 金鑰復原服務中。</span><span class="sxs-lookup"><span data-stu-id="cc3da-339">If the computer is not joined to a domain, the recovery password is not stored in the MBAM Key Recovery service.</span></span> <span data-ttu-id="cc3da-340">根據預設，除非能儲存復原金鑰，否則 MBAM 不允許進行加密。</span><span class="sxs-lookup"><span data-stu-id="cc3da-340">By default, MBAM does not allow encryption to occur unless the recovery key can be stored.</span></span>

    -   <span data-ttu-id="cc3da-341">如果電腦在修復金鑰儲存在 MBAM 伺服器上之前以復原模式啟動，則不提供任何復原方法，且必須 reimaged 電腦。</span><span class="sxs-lookup"><span data-stu-id="cc3da-341">If a computer starts in recovery mode before the recovery key is stored on the MBAM Server, no recovery method is available, and the computer has to be reimaged.</span></span>

3.  <span data-ttu-id="cc3da-342">以系統管理員身分開啟命令提示字元，並停止 MBAM 服務。</span><span class="sxs-lookup"><span data-stu-id="cc3da-342">Open a command prompt as an administrator, and stop the MBAM service.</span></span>

4.  <span data-ttu-id="cc3da-343">輸入下列命令，將服務設定為 [**手動**] 或 [按**需**]：</span><span class="sxs-lookup"><span data-stu-id="cc3da-343">Set the service to **Manual** or **On demand** by typing the following commands:</span></span>

    **<span data-ttu-id="cc3da-344">net stop mbamagent</span><span class="sxs-lookup"><span data-stu-id="cc3da-344">net stop mbamagent</span></span>**

    **<span data-ttu-id="cc3da-345">sc config mbamagent start = 要求</span><span class="sxs-lookup"><span data-stu-id="cc3da-345">sc config mbamagent start= demand</span></span>**

5.  <span data-ttu-id="cc3da-346">設定登錄值，讓 MBAM 用戶端忽略群組原則設定，而是設定加密，以啟動將 Windows 部署到該用戶端電腦的時間。</span><span class="sxs-lookup"><span data-stu-id="cc3da-346">Set the registry values so that the MBAM Client ignores the Group Policy settings and instead sets encryption to start the time Windows is deployed to that client computer.</span></span>

    <span data-ttu-id="cc3da-347">**小心** 此步驟說明如何修改 Windows 註冊。</span><span class="sxs-lookup"><span data-stu-id="cc3da-347">**Caution** This step describes how to modify the Windows registry.</span></span> <span data-ttu-id="cc3da-348">無法正確使用登錄編輯程式，可能會導致嚴重問題，可能需要您重新安裝 Windows。</span><span class="sxs-lookup"><span data-stu-id="cc3da-348">Using Registry Editor incorrectly can cause serious issues that can require you to reinstall Windows.</span></span> <span data-ttu-id="cc3da-349">我們無法保證因無法正確使用登錄編輯程式而造成的問題無法解決。</span><span class="sxs-lookup"><span data-stu-id="cc3da-349">We cannot guarantee that issues resulting from the incorrect use of Registry Editor can be resolved.</span></span> <span data-ttu-id="cc3da-350">使用登錄編輯程式的風險由您自負。</span><span class="sxs-lookup"><span data-stu-id="cc3da-350">Use Registry Editor at your own risk.</span></span>

    1.  <span data-ttu-id="cc3da-351">設定**僅限作業系統加密**的 TPM、執行 Regedit.exe，然後從 C:\\program files Files\\Microsoft\\MDOP MBAM\\MBAMDeploymentKeyTemplate.reg. 匯入登錄機碼範本</span><span class="sxs-lookup"><span data-stu-id="cc3da-351">Set the TPM for **Operating system only encryption**, run Regedit.exe, and then import the registry key template from C:\\Program Files\\Microsoft\\MDOP MBAM\\MBAMDeploymentKeyTemplate.reg.</span></span>

    2.  <span data-ttu-id="cc3da-352">在 Regedit.exe 中，移至 HKLM\\SOFTWARE\\Microsoft\\MBAM，並設定下表所列的設定。</span><span class="sxs-lookup"><span data-stu-id="cc3da-352">In Regedit.exe, go to HKLM\\SOFTWARE\\Microsoft\\MBAM, and configure the settings that are listed in the following table.</span></span>

        <span data-ttu-id="cc3da-353">**記事** 您可以在這裡設定與 MBAM 相關的群組原則設定或登錄值。</span><span class="sxs-lookup"><span data-stu-id="cc3da-353">**Note** You can set Group Policy settings or registry values related to MBAM here.</span></span> <span data-ttu-id="cc3da-354">這些設定會覆寫先前設定的值。</span><span class="sxs-lookup"><span data-stu-id="cc3da-354">These settings will override previously set values.</span></span>

        <span data-ttu-id="cc3da-355">登錄專案設定</span><span class="sxs-lookup"><span data-stu-id="cc3da-355">Registry entry Configuration settings</span></span>

        <span data-ttu-id="cc3da-356">DeploymentTime</span><span class="sxs-lookup"><span data-stu-id="cc3da-356">DeploymentTime</span></span>

        <span data-ttu-id="cc3da-357">0 = 關閉</span><span class="sxs-lookup"><span data-stu-id="cc3da-357">0 = Off</span></span>

        <span data-ttu-id="cc3da-358">1 = 使用部署時間原則設定（預設）–在 Windows 部署到用戶端電腦時，請使用此設定來啟用加密。</span><span class="sxs-lookup"><span data-stu-id="cc3da-358">1 = Use deployment time policy settings (default) – use this setting to enable encryption at the time Windows is deployed to the client computer.</span></span>

        <span data-ttu-id="cc3da-359">UseKeyRecoveryService</span><span class="sxs-lookup"><span data-stu-id="cc3da-359">UseKeyRecoveryService</span></span>

        <span data-ttu-id="cc3da-360">0 = 不使用金鑰保管（這種情況下，不需要接下來的兩個登錄專案）</span><span class="sxs-lookup"><span data-stu-id="cc3da-360">0 = Do not use key escrow (the next two registry entries are not required in this case)</span></span>

        <span data-ttu-id="cc3da-361">1 = 在金鑰還原系統中使用金鑰委託（預設）</span><span class="sxs-lookup"><span data-stu-id="cc3da-361">1 = Use key escrow in Key Recovery system (default)</span></span>

        <span data-ttu-id="cc3da-362">這是建議的設定，可讓 MBAM 儲存修復金鑰。</span><span class="sxs-lookup"><span data-stu-id="cc3da-362">This is the recommended setting, which enables MBAM to store the recovery keys.</span></span> <span data-ttu-id="cc3da-363">電腦必須能夠與 MBAM 金鑰復原服務進行通訊。</span><span class="sxs-lookup"><span data-stu-id="cc3da-363">The computer must be able to communicate with the MBAM Key Recovery service.</span></span> <span data-ttu-id="cc3da-364">繼續進行之前，請先確認電腦可以與服務進行通訊。</span><span class="sxs-lookup"><span data-stu-id="cc3da-364">Verify that the computer can communicate with the service before you proceed.</span></span>

        <span data-ttu-id="cc3da-365">KeyRecoveryOptions</span><span class="sxs-lookup"><span data-stu-id="cc3da-365">KeyRecoveryOptions</span></span>

        <span data-ttu-id="cc3da-366">0 = 僅限上傳復原金鑰</span><span class="sxs-lookup"><span data-stu-id="cc3da-366">0 = Uploads Recovery Key only</span></span>

        <span data-ttu-id="cc3da-367">1 = 上傳復原金鑰和金鑰復原套件（預設）</span><span class="sxs-lookup"><span data-stu-id="cc3da-367">1 = Uploads Recovery Key and Key Recovery Package (default)</span></span>

        <span data-ttu-id="cc3da-368">KeyRecoveryServiceEndPoint</span><span class="sxs-lookup"><span data-stu-id="cc3da-368">KeyRecoveryServiceEndPoint</span></span>

        <span data-ttu-id="cc3da-369">將此值設定為執行金鑰復原服務之伺服器的 URL，例如，HTTP://[ &lt; 電腦名稱稱] &gt; /MBAMRecoveryAndHardwareService/CoreService.svc。</span><span class="sxs-lookup"><span data-stu-id="cc3da-369">Set this value to the URL for the server running the Key Recovery service, for example, http://&lt;computer name&gt;/MBAMRecoveryAndHardwareService/CoreService.svc.</span></span>


6.  <span data-ttu-id="cc3da-370">MBAM 用戶端將在 MBAM 用戶端部署期間重新開機系統。</span><span class="sxs-lookup"><span data-stu-id="cc3da-370">The MBAM Client will restart the system during the MBAM Client deployment.</span></span> <span data-ttu-id="cc3da-371">當您準備好進行此重新開機時，請以系統管理員的命令提示字元執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="cc3da-371">When you are ready for this restart, run the following command at a command prompt as an administrator:</span></span>

    **<span data-ttu-id="cc3da-372">net start mbamagent</span><span class="sxs-lookup"><span data-stu-id="cc3da-372">net start mbamagent</span></span>**

7.  <span data-ttu-id="cc3da-373">當電腦重新開機且 BIOS 提示您時，請接受 TPM 變更。</span><span class="sxs-lookup"><span data-stu-id="cc3da-373">When the computers restarts, and the BIOS prompts you, accept the TPM change.</span></span>

8.  <span data-ttu-id="cc3da-374">在 Windows 用戶端作業系統影像程式期間，當您準備好要開始加密時，請以系統管理員身分開啟命令提示字元，然後輸入下列命令，將 [開始] 設定為 [**自動**]，然後重新開機 MBAM 用戶端代理程式：</span><span class="sxs-lookup"><span data-stu-id="cc3da-374">During the Windows client operating system imaging process, when you are ready to start encryption, open a command prompt as an administrator, and type the following commands to set the start to **Automatic** and to restart the MBAM Client agent:</span></span>

    **<span data-ttu-id="cc3da-375">sc config mbamagent start = auto</span><span class="sxs-lookup"><span data-stu-id="cc3da-375">sc config mbamagent start= auto</span></span>**

    **<span data-ttu-id="cc3da-376">net start mbamagent</span><span class="sxs-lookup"><span data-stu-id="cc3da-376">net start mbamagent</span></span>**

9.  <span data-ttu-id="cc3da-377">若要刪除旁路登錄值，請執行 Regedit.exe，然後移至 HKLM\\SOFTWARE\\Microsoft 登錄機碼目。</span><span class="sxs-lookup"><span data-stu-id="cc3da-377">To delete the bypass registry values, run Regedit.exe, and go to the HKLM\\SOFTWARE\\Microsoft registry entry.</span></span> <span data-ttu-id="cc3da-378">以滑鼠右鍵按一下 [ **MBAM** ] 節點，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="cc3da-378">Right-click the **MBAM** node, and then click **Delete**.</span></span>

## <span data-ttu-id="cc3da-379">相關主題</span><span class="sxs-lookup"><span data-stu-id="cc3da-379">Related topics</span></span>

[<span data-ttu-id="cc3da-380">部署 MBAM 2.5 用戶端</span><span class="sxs-lookup"><span data-stu-id="cc3da-380">Deploying the MBAM 2.5 Client</span></span>](deploying-the-mbam-25-client.md)

[<span data-ttu-id="cc3da-381">MBAM 2.5 用戶端部署規劃</span><span class="sxs-lookup"><span data-stu-id="cc3da-381">Planning for MBAM 2.5 Client Deployment</span></span>](planning-for-mbam-25-client-deployment.md)

## <span data-ttu-id="cc3da-382">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="cc3da-382">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="cc3da-383">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="cc3da-383">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span>
- <span data-ttu-id="cc3da-384">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="cc3da-384">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>
