---
title: 用戶端事件記錄檔
description: 用戶端事件記錄檔
author: dansimp
ms.assetid: d5c2f270-db6a-45f1-8557-8c6fb28fd568
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7324d07bf018944fcbe24168bba2e9abea9cea41
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810407"
---
# <span data-ttu-id="2cb88-103">用戶端事件記錄檔</span><span class="sxs-lookup"><span data-stu-id="2cb88-103">Client Event Logs</span></span>

<span data-ttu-id="2cb88-104">MBAM 用戶端事件記錄位於 [事件檢視器]-[應用程式和服務記錄]-Microsoft – Windows – MBAM-操作路徑中。</span><span class="sxs-lookup"><span data-stu-id="2cb88-104">MBAM Client event logs are located in Event Viewer – Applications and Services Logs – Microsoft – Windows – MBAM - Operational path.</span></span>
<span data-ttu-id="2cb88-105">下表包含可在 MBAM 用戶端上發生的事件 Id。</span><span class="sxs-lookup"><span data-stu-id="2cb88-105">The following table contains event IDs that can occur on the MBAM Client.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2cb88-106">事件識別碼</span><span class="sxs-lookup"><span data-stu-id="2cb88-106">Event ID</span></span></th>
<th align="left"><span data-ttu-id="2cb88-107">通道</span><span class="sxs-lookup"><span data-stu-id="2cb88-107">Channel</span></span></th>
<th align="left"><span data-ttu-id="2cb88-108">事件符號</span><span class="sxs-lookup"><span data-stu-id="2cb88-108">Event symbol</span></span></th>
<th align="left"><span data-ttu-id="2cb88-109">訊息</span><span class="sxs-lookup"><span data-stu-id="2cb88-109">Message</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2cb88-110">sr-1</span><span class="sxs-lookup"><span data-stu-id="2cb88-110">1</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-111">操作</span><span class="sxs-lookup"><span data-stu-id="2cb88-111">Operational</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-112">VolumeEnactmentSuccessful</span><span class="sxs-lookup"><span data-stu-id="2cb88-112">VolumeEnactmentSuccessful</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-113">已成功套用 MBAM 原則。</span><span class="sxs-lookup"><span data-stu-id="2cb88-113">The MBAM policies were applied successfully.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2cb88-114">pplx-2</span><span class="sxs-lookup"><span data-stu-id="2cb88-114">2</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-115">系統管理員</span><span class="sxs-lookup"><span data-stu-id="2cb88-115">Admin</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-116">VolumeEnactmentFailed</span><span class="sxs-lookup"><span data-stu-id="2cb88-116">VolumeEnactmentFailed</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-117">套用 MBAM 原則時發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="2cb88-117">An error occurred while applying MBAM policies.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2cb88-118">3</span><span class="sxs-lookup"><span data-stu-id="2cb88-118">3</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-119">操作</span><span class="sxs-lookup"><span data-stu-id="2cb88-119">Operational</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-120">TransferStatusDataSuccessful</span><span class="sxs-lookup"><span data-stu-id="2cb88-120">TransferStatusDataSuccessful</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-121">已成功傳送加密狀態資料。</span><span class="sxs-lookup"><span data-stu-id="2cb88-121">The encryption status data was sent successfully.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2cb88-122">4</span><span class="sxs-lookup"><span data-stu-id="2cb88-122">4</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-123">系統管理員</span><span class="sxs-lookup"><span data-stu-id="2cb88-123">Admin</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-124">TransferStatusDataFailed</span><span class="sxs-lookup"><span data-stu-id="2cb88-124">TransferStatusDataFailed</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-125">傳送加密狀態資料時發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="2cb88-125">An error occurred while sending encryption status data.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2cb88-126">型</span><span class="sxs-lookup"><span data-stu-id="2cb88-126">8</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-127">系統管理員</span><span class="sxs-lookup"><span data-stu-id="2cb88-127">Admin</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-128">SystemVolumeNotFound</span><span class="sxs-lookup"><span data-stu-id="2cb88-128">SystemVolumeNotFound</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-129">系統磁碟區遺失。</span><span class="sxs-lookup"><span data-stu-id="2cb88-129">The system volume is missing.</span></span> <span data-ttu-id="2cb88-130">需要 SystemVolume 以加密作業系統磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="2cb88-130">SystemVolume is needed to encrypt the operating system drive.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2cb88-131">9</span><span class="sxs-lookup"><span data-stu-id="2cb88-131">9</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-132">系統管理員</span><span class="sxs-lookup"><span data-stu-id="2cb88-132">Admin</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-133">TPMNotFound</span><span class="sxs-lookup"><span data-stu-id="2cb88-133">TPMNotFound</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-134">TPM 硬體遺失。</span><span class="sxs-lookup"><span data-stu-id="2cb88-134">The TPM hardware is missing.</span></span> <span data-ttu-id="2cb88-135">需要 TPM 來加密作業系統磁片磁碟機與任何 TPM 保護器。</span><span class="sxs-lookup"><span data-stu-id="2cb88-135">TPM is needed to encrypt the operating system drive with any TPM protector.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2cb88-136">第</span><span class="sxs-lookup"><span data-stu-id="2cb88-136">10</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-137">系統管理員</span><span class="sxs-lookup"><span data-stu-id="2cb88-137">Admin</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-138">MachineHWExempted</span><span class="sxs-lookup"><span data-stu-id="2cb88-138">MachineHWExempted</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-139">電腦已免除加密。</span><span class="sxs-lookup"><span data-stu-id="2cb88-139">The computer is exempted from Encryption.</span></span> <span data-ttu-id="2cb88-140">電腦的硬體狀態：已免除</span><span class="sxs-lookup"><span data-stu-id="2cb88-140">Machine’s hardware status: Exempted</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2cb88-141">11</span><span class="sxs-lookup"><span data-stu-id="2cb88-141">11</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-142">系統管理員</span><span class="sxs-lookup"><span data-stu-id="2cb88-142">Admin</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-143">MachineHWUnknown</span><span class="sxs-lookup"><span data-stu-id="2cb88-143">MachineHWUnknown</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-144">電腦已免除加密。</span><span class="sxs-lookup"><span data-stu-id="2cb88-144">The computer is exempted from encryption.</span></span> <span data-ttu-id="2cb88-145">電腦的硬體狀態：未知</span><span class="sxs-lookup"><span data-stu-id="2cb88-145">Machine’s hardware status: Unknown</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2cb88-146">之間</span><span class="sxs-lookup"><span data-stu-id="2cb88-146">12</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-147">系統管理員</span><span class="sxs-lookup"><span data-stu-id="2cb88-147">Admin</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-148">HWCheckFailed</span><span class="sxs-lookup"><span data-stu-id="2cb88-148">HWCheckFailed</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-149">硬體免除檢查失敗。</span><span class="sxs-lookup"><span data-stu-id="2cb88-149">Hardware exemption check failed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2cb88-150">合</span><span class="sxs-lookup"><span data-stu-id="2cb88-150">13</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-151">系統管理員</span><span class="sxs-lookup"><span data-stu-id="2cb88-151">Admin</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-152">UserIsExempted</span><span class="sxs-lookup"><span data-stu-id="2cb88-152">UserIsExempted</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-153">使用者不受加密。</span><span class="sxs-lookup"><span data-stu-id="2cb88-153">The user is exempt from encryption.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2cb88-154">4</span><span class="sxs-lookup"><span data-stu-id="2cb88-154">14</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-155">系統管理員</span><span class="sxs-lookup"><span data-stu-id="2cb88-155">Admin</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-156">UserIsWaiting</span><span class="sxs-lookup"><span data-stu-id="2cb88-156">UserIsWaiting</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-157">使用者要求例外。</span><span class="sxs-lookup"><span data-stu-id="2cb88-157">The user requested an exemption.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2cb88-158">工資</span><span class="sxs-lookup"><span data-stu-id="2cb88-158">15</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-159">系統管理員</span><span class="sxs-lookup"><span data-stu-id="2cb88-159">Admin</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-160">UserExemptionCheckFailed</span><span class="sxs-lookup"><span data-stu-id="2cb88-160">UserExemptionCheckFailed</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-161">使用者豁免檢查失敗。</span><span class="sxs-lookup"><span data-stu-id="2cb88-161">User exemption check failed.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2cb88-162">位</span><span class="sxs-lookup"><span data-stu-id="2cb88-162">16</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-163">系統管理員</span><span class="sxs-lookup"><span data-stu-id="2cb88-163">Admin</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-164">UserPostponed</span><span class="sxs-lookup"><span data-stu-id="2cb88-164">UserPostponed</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-165">使用者已延遲加密處理常式。</span><span class="sxs-lookup"><span data-stu-id="2cb88-165">The user postponed the encryption process.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2cb88-166">11x17</span><span class="sxs-lookup"><span data-stu-id="2cb88-166">17</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-167">系統管理員</span><span class="sxs-lookup"><span data-stu-id="2cb88-167">Admin</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-168">TPMInitializationFailed</span><span class="sxs-lookup"><span data-stu-id="2cb88-168">TPMInitializationFailed</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-169">TPM 初始化失敗。</span><span class="sxs-lookup"><span data-stu-id="2cb88-169">TPM initialization failed.</span></span> <span data-ttu-id="2cb88-170">使用者拒絕 BIOS 變更。</span><span class="sxs-lookup"><span data-stu-id="2cb88-170">The user rejected the BIOS changes.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2cb88-171">滿</span><span class="sxs-lookup"><span data-stu-id="2cb88-171">18</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-172">系統管理員</span><span class="sxs-lookup"><span data-stu-id="2cb88-172">Admin</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-173">CoreServiceDown</span><span class="sxs-lookup"><span data-stu-id="2cb88-173">CoreServiceDown</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-174">無法連線至 MBAM 復原與硬體服務。</span><span class="sxs-lookup"><span data-stu-id="2cb88-174">Unable to connect to the MBAM Recovery and Hardware service.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2cb88-175">合</span><span class="sxs-lookup"><span data-stu-id="2cb88-175">19</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-176">操作</span><span class="sxs-lookup"><span data-stu-id="2cb88-176">Operational</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-177">CoreServiceUp</span><span class="sxs-lookup"><span data-stu-id="2cb88-177">CoreServiceUp</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-178">已成功連線至 MBAM 復原與硬體服務。</span><span class="sxs-lookup"><span data-stu-id="2cb88-178">Successfully connected to the MBAM Recovery and Hardware service.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2cb88-179">20</span><span class="sxs-lookup"><span data-stu-id="2cb88-179">20</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-180">系統管理員</span><span class="sxs-lookup"><span data-stu-id="2cb88-180">Admin</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-181">PolicyMismatch</span><span class="sxs-lookup"><span data-stu-id="2cb88-181">PolicyMismatch</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-182">MBAM 原則發生衝突或已損毀。</span><span class="sxs-lookup"><span data-stu-id="2cb88-182">The MBAM policy is in conflict or corrupt.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2cb88-183">日前</span><span class="sxs-lookup"><span data-stu-id="2cb88-183">21</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-184">系統管理員</span><span class="sxs-lookup"><span data-stu-id="2cb88-184">Admin</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-185">ConflictingOSVolumePolicies</span><span class="sxs-lookup"><span data-stu-id="2cb88-185">ConflictingOSVolumePolicies</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-186">偵測到 OS 大量加密原則發生衝突。</span><span class="sxs-lookup"><span data-stu-id="2cb88-186">Detected OS volume encryption policies conflict.</span></span> <span data-ttu-id="2cb88-187">檢查與操作系統磁碟機保護器相關的 BitLocker 與 MBAM 原則。</span><span class="sxs-lookup"><span data-stu-id="2cb88-187">Check BitLocker and MBAM policies related to OS drive protectors.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2cb88-188">22</span><span class="sxs-lookup"><span data-stu-id="2cb88-188">22</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-189">系統管理員</span><span class="sxs-lookup"><span data-stu-id="2cb88-189">Admin</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-190">ConflictingFDDVolumePolicies</span><span class="sxs-lookup"><span data-stu-id="2cb88-190">ConflictingFDDVolumePolicies</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-191">偵測到固定資料磁片磁碟機的大量加密原則衝突。</span><span class="sxs-lookup"><span data-stu-id="2cb88-191">Detected Fixed Data Drive volume encryption policies conflict.</span></span> <span data-ttu-id="2cb88-192">檢查與 FDD 磁碟機保護器相關的 BitLocker 與 MBAM 原則。</span><span class="sxs-lookup"><span data-stu-id="2cb88-192">Check BitLocker and MBAM policies related to FDD drive protectors.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2cb88-193">27</span><span class="sxs-lookup"><span data-stu-id="2cb88-193">27</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-194">系統管理員</span><span class="sxs-lookup"><span data-stu-id="2cb88-194">Admin</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-195">EncryptionFailedNoDra</span><span class="sxs-lookup"><span data-stu-id="2cb88-195">EncryptionFailedNoDra</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-196">加密時發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="2cb88-196">An error occurred while encrypting.</span></span> <span data-ttu-id="2cb88-197">在適用于 Windows 8.1 電腦的 FIPS 模式中，需要有資料復原代理程式（DRA）保護器。</span><span class="sxs-lookup"><span data-stu-id="2cb88-197">A Data Recovery Agent (DRA) protector is required in FIPS mode for pre-Windows 8.1 machines.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2cb88-198">28</span><span class="sxs-lookup"><span data-stu-id="2cb88-198">28</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-199">操作</span><span class="sxs-lookup"><span data-stu-id="2cb88-199">Operational</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-200">TpmOwnerAuthEscrowed</span><span class="sxs-lookup"><span data-stu-id="2cb88-200">TpmOwnerAuthEscrowed</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-201">TPM OwnerAuth 已 escrowed。</span><span class="sxs-lookup"><span data-stu-id="2cb88-201">The TPM OwnerAuth has been escrowed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2cb88-202">5</span><span class="sxs-lookup"><span data-stu-id="2cb88-202">29</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-203">操作</span><span class="sxs-lookup"><span data-stu-id="2cb88-203">Operational</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-204">RecoveryKeyEscrowed</span><span class="sxs-lookup"><span data-stu-id="2cb88-204">RecoveryKeyEscrowed</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-205">已 escrowed 該卷的 BitLocker 復原金鑰。</span><span class="sxs-lookup"><span data-stu-id="2cb88-205">The BitLocker recovery key for the volume has been escrowed.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2cb88-206">為期</span><span class="sxs-lookup"><span data-stu-id="2cb88-206">30</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-207">操作</span><span class="sxs-lookup"><span data-stu-id="2cb88-207">Operational</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-208">RecoveryKeyReset</span><span class="sxs-lookup"><span data-stu-id="2cb88-208">RecoveryKeyReset</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-209">已更新此卷的 BitLocker 復原金鑰。</span><span class="sxs-lookup"><span data-stu-id="2cb88-209">The BitLocker recovery key for the volume has been updated.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2cb88-210">31</span><span class="sxs-lookup"><span data-stu-id="2cb88-210">31</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-211">操作</span><span class="sxs-lookup"><span data-stu-id="2cb88-211">Operational</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-212">EnforcePolicyDateSet</span><span class="sxs-lookup"><span data-stu-id="2cb88-212">EnforcePolicyDateSet</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-213">已 <em> &lt; &gt; </em> 為此卷設定強制原則日期、日期</span><span class="sxs-lookup"><span data-stu-id="2cb88-213">The enforce policy date, <em>&lt;date&gt;</em>, has been set for the volume</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2cb88-214">32</span><span class="sxs-lookup"><span data-stu-id="2cb88-214">32</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-215">操作</span><span class="sxs-lookup"><span data-stu-id="2cb88-215">Operational</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-216">EnforcePolicyDateCleared</span><span class="sxs-lookup"><span data-stu-id="2cb88-216">EnforcePolicyDateCleared</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-217">已 <em> &lt; &gt; </em> 清除該卷的 [強制原則日期]、[日期]。</span><span class="sxs-lookup"><span data-stu-id="2cb88-217">The enforce policy date, <em>&lt;date&gt;</em>, has been cleared for the volume.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2cb88-218">33</span><span class="sxs-lookup"><span data-stu-id="2cb88-218">33</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-219">操作</span><span class="sxs-lookup"><span data-stu-id="2cb88-219">Operational</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-220">TpmLockOutResetSucceeded</span><span class="sxs-lookup"><span data-stu-id="2cb88-220">TpmLockOutResetSucceeded</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-221">已成功重設 TPM 封鎖。</span><span class="sxs-lookup"><span data-stu-id="2cb88-221">Successfully reset TPM lockout.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2cb88-222">34</span><span class="sxs-lookup"><span data-stu-id="2cb88-222">34</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-223">系統管理員</span><span class="sxs-lookup"><span data-stu-id="2cb88-223">Admin</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-224">TpmLockOutResetFailed</span><span class="sxs-lookup"><span data-stu-id="2cb88-224">TpmLockOutResetFailed</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-225">無法重設 TPM 封鎖。</span><span class="sxs-lookup"><span data-stu-id="2cb88-225">Failed to reset TPM lockout.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2cb88-226">35</span><span class="sxs-lookup"><span data-stu-id="2cb88-226">35</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-227">操作</span><span class="sxs-lookup"><span data-stu-id="2cb88-227">Operational</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-228">TpmOwnerAuthRetrievalSucceeded</span><span class="sxs-lookup"><span data-stu-id="2cb88-228">TpmOwnerAuthRetrievalSucceeded</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-229">已成功從 MBAM 服務中檢索到 TPM OwnerAuth。</span><span class="sxs-lookup"><span data-stu-id="2cb88-229">Successfully retrieved TPM OwnerAuth from MBAM services.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2cb88-230">36</span><span class="sxs-lookup"><span data-stu-id="2cb88-230">36</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-231">系統管理員</span><span class="sxs-lookup"><span data-stu-id="2cb88-231">Admin</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-232">TpmOwnerAuthRetrievalFailed</span><span class="sxs-lookup"><span data-stu-id="2cb88-232">TpmOwnerAuthRetrievalFailed</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-233">無法從 MBAM services 中取得 TPM OwnerAuth。</span><span class="sxs-lookup"><span data-stu-id="2cb88-233">Failed to retrieve TPM OwnerAuth from MBAM services.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2cb88-234">37</span><span class="sxs-lookup"><span data-stu-id="2cb88-234">37</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-235">系統管理員</span><span class="sxs-lookup"><span data-stu-id="2cb88-235">Admin</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-236">WmiProviderDllSearchPathUpdateFailed</span><span class="sxs-lookup"><span data-stu-id="2cb88-236">WmiProviderDllSearchPathUpdateFailed</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-237">無法更新 WMI 提供者的 DLL 搜尋路徑。</span><span class="sxs-lookup"><span data-stu-id="2cb88-237">Failed to update the DLL search path for WMI provider.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2cb88-238">38</span><span class="sxs-lookup"><span data-stu-id="2cb88-238">38</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-239">系統管理員</span><span class="sxs-lookup"><span data-stu-id="2cb88-239">Admin</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-240">TimedOutWaitingForWmiProvider</span><span class="sxs-lookup"><span data-stu-id="2cb88-240">TimedOutWaitingForWmiProvider</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-241">代理程式停止-等待 MBAM WMI 提供者實例超時。</span><span class="sxs-lookup"><span data-stu-id="2cb88-241">Agent Stopping - Timed-out waiting for MBAM WMI Provider Instance.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2cb88-242">39</span><span class="sxs-lookup"><span data-stu-id="2cb88-242">39</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-243">操作</span><span class="sxs-lookup"><span data-stu-id="2cb88-243">Operational</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-244">RemovableDriveMounted</span><span class="sxs-lookup"><span data-stu-id="2cb88-244">RemovableDriveMounted</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-245">已裝入抽取式磁碟磁碟機。</span><span class="sxs-lookup"><span data-stu-id="2cb88-245">Removable drive was mounted.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2cb88-246">40</span><span class="sxs-lookup"><span data-stu-id="2cb88-246">40</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-247">操作</span><span class="sxs-lookup"><span data-stu-id="2cb88-247">Operational</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-248">RemovableDriveDismounted</span><span class="sxs-lookup"><span data-stu-id="2cb88-248">RemovableDriveDismounted</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-249">抽取式磁碟磁碟機已卸載。</span><span class="sxs-lookup"><span data-stu-id="2cb88-249">Removable drive was unmounted.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2cb88-250">41</span><span class="sxs-lookup"><span data-stu-id="2cb88-250">41</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-251">操作</span><span class="sxs-lookup"><span data-stu-id="2cb88-251">Operational</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-252">FailedToEnactEndpointUnreachable</span><span class="sxs-lookup"><span data-stu-id="2cb88-252">FailedToEnactEndpointUnreachable</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-253">無法連線至 MBAM 復原與硬體服務，無法成功將 MBAM 原則套用到該卷。</span><span class="sxs-lookup"><span data-stu-id="2cb88-253">Failure to connect to the MBAM Recovery and Hardware service prevented MBAM policies from being applied successfully to the volume.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2cb88-254">42</span><span class="sxs-lookup"><span data-stu-id="2cb88-254">42</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-255">操作</span><span class="sxs-lookup"><span data-stu-id="2cb88-255">Operational</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-256">FailedToEnactLockedVolume</span><span class="sxs-lookup"><span data-stu-id="2cb88-256">FailedToEnactLockedVolume</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-257">已鎖定的磁片狀態會使 MBAM 原則無法順利套用到該卷。</span><span class="sxs-lookup"><span data-stu-id="2cb88-257">Locked volume state prevented MBAM policies from being applied successfully to the volume.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2cb88-258">43</span><span class="sxs-lookup"><span data-stu-id="2cb88-258">43</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-259">操作</span><span class="sxs-lookup"><span data-stu-id="2cb88-259">Operational</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-260">TransferStatusDataFailedEndpointUnreachable</span><span class="sxs-lookup"><span data-stu-id="2cb88-260">TransferStatusDataFailedEndpointUnreachable</span></span></p></td>
<td align="left"><p><span data-ttu-id="2cb88-261">無法連線至 MBAM 合規性與狀態服務，因此無法傳輸加密狀態資料。</span><span class="sxs-lookup"><span data-stu-id="2cb88-261">Failure to connect to the MBAM Compliance and Status service prevented the transfer of encryption status data.</span></span></p></td>
</tr>
</tbody>
</table>

 


## <span data-ttu-id="2cb88-262">相關主題</span><span class="sxs-lookup"><span data-stu-id="2cb88-262">Related topics</span></span>
[<span data-ttu-id="2cb88-263">MBAM 2.5 技術參考資料</span><span class="sxs-lookup"><span data-stu-id="2cb88-263">Technical Reference for MBAM 2.5</span></span>](technical-reference-for-mbam-25.md)

[<span data-ttu-id="2cb88-264">伺服器事件記錄檔</span><span class="sxs-lookup"><span data-stu-id="2cb88-264">Server Event Logs</span></span>](server-event-logs.md)

 


## <span data-ttu-id="2cb88-265">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="2cb88-265">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="2cb88-266">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="2cb88-266">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="2cb88-267">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="2cb88-267">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





