---
title: 瞭解 MBAM 報告
description: 瞭解 MBAM 報告
author: dansimp
ms.assetid: 34e4aaeb-7f89-41a1-b816-c6fe8397b060
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa64a4724c87a42774e569b556013bfec2ed5514
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809614"
---
# <span data-ttu-id="83eed-103">瞭解 MBAM 報告</span><span class="sxs-lookup"><span data-stu-id="83eed-103">Understanding MBAM Reports</span></span>


<span data-ttu-id="83eed-104">Microsoft BitLocker 管理和監控（MBAM）會產生各種報告，以監控 BitLocker 使用量與合規性。</span><span class="sxs-lookup"><span data-stu-id="83eed-104">Microsoft BitLocker Administration and Monitoring (MBAM) generates various reports to monitor BitLocker usage and compliance.</span></span> <span data-ttu-id="83eed-105">本主題說明適用于企業合規性、個別電腦、硬體相容性及金鑰復原活動的 MBAM 報告。</span><span class="sxs-lookup"><span data-stu-id="83eed-105">This topic describes the MBAM reports for enterprise compliance, individual computers, hardware compatibility, and key recovery activity.</span></span>

## <span data-ttu-id="83eed-106">瞭解報表</span><span class="sxs-lookup"><span data-stu-id="83eed-106">Understanding Reports</span></span>


<span data-ttu-id="83eed-107">若要存取 MBAM 的報告功能，請開啟 MBAM 管理網站。</span><span class="sxs-lookup"><span data-stu-id="83eed-107">To access the Reports feature of MBAM, open the MBAM administration website.</span></span> <span data-ttu-id="83eed-108">選取 [功能窗格] 中的 [**報表**]。</span><span class="sxs-lookup"><span data-stu-id="83eed-108">Select **Reports** in the navigation pane.</span></span> <span data-ttu-id="83eed-109">接著，在 [主要內容] 窗格中，按一下您報表類型的索引標籤：**企業規範報告**、**電腦合規性報告**、**硬體審核報告**，或復原**審核報告**。</span><span class="sxs-lookup"><span data-stu-id="83eed-109">Then, in the main content pane, click the tab for your report type: **Enterprise Compliance Report**, **Computer Compliance Report**, **Hardware Audit Report**, or **Recovery Audit Report**.</span></span>

### <span data-ttu-id="83eed-110">企業合規性報告</span><span class="sxs-lookup"><span data-stu-id="83eed-110">Enterprise Compliance Report</span></span>

<span data-ttu-id="83eed-111">企業合規性報告提供貴組織中的整體 BitLocker 合規性資訊。</span><span class="sxs-lookup"><span data-stu-id="83eed-111">An Enterprise Compliance Report provides information on overall BitLocker compliance in your organization.</span></span> <span data-ttu-id="83eed-112">此報告可用的篩選器可讓您根據合規性狀態和錯誤狀態來縮小搜尋結果。</span><span class="sxs-lookup"><span data-stu-id="83eed-112">The available filters for this report allow you to narrow your search results according to Compliance state and Error status.</span></span> <span data-ttu-id="83eed-113">此報告每6小時執行一次。</span><span class="sxs-lookup"><span data-stu-id="83eed-113">This report runs every six hours.</span></span>

**<span data-ttu-id="83eed-114">企業合規性報告欄位</span><span class="sxs-lookup"><span data-stu-id="83eed-114">Enterprise Compliance Report fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="83eed-115">欄名稱</span><span class="sxs-lookup"><span data-stu-id="83eed-115">Column Name</span></span></th>
<th align="left"><span data-ttu-id="83eed-116">描述</span><span class="sxs-lookup"><span data-stu-id="83eed-116">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="83eed-117">電腦名稱稱</span><span class="sxs-lookup"><span data-stu-id="83eed-117">Computer Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-118">由 MBAM 管理的使用者指定 DNS 名稱。</span><span class="sxs-lookup"><span data-stu-id="83eed-118">The user-specified DNS name that is being managed by MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="83eed-119">網功能變數名稱稱</span><span class="sxs-lookup"><span data-stu-id="83eed-119">Domain Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-120">用戶端電腦所在的完整功能變數名稱，且由 MBAM 管理。</span><span class="sxs-lookup"><span data-stu-id="83eed-120">The fully qualified domain name where the client computer resides and is managed by MBAM.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="83eed-121">合規性狀態</span><span class="sxs-lookup"><span data-stu-id="83eed-121">Compliance Status</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-122">根據電腦所指定的原則，為電腦規範的狀態。</span><span class="sxs-lookup"><span data-stu-id="83eed-122">The state of compliance for the computer, according to the policy specified for the computer.</span></span> <span data-ttu-id="83eed-123">可能的狀態是不相容且合規性。</span><span class="sxs-lookup"><span data-stu-id="83eed-123">The possible states are Noncompliant and Compliant.</span></span> <span data-ttu-id="83eed-124">如需詳細資訊，請參閱本主題中的企業合規性報告合規性狀態。</span><span class="sxs-lookup"><span data-stu-id="83eed-124">For more information, see Enterprise Compliance Report Compliance States in this topic.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="83eed-125">免除</span><span class="sxs-lookup"><span data-stu-id="83eed-125">Exemption</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-126">電腦硬體的狀態，決定硬體類型的識別，以及電腦是否免除原則。</span><span class="sxs-lookup"><span data-stu-id="83eed-126">The state of the computer hardware for determining the identification of the hardware type and whether the computer is exempt from policy.</span></span> <span data-ttu-id="83eed-127">有三種可能的狀態：硬體未知（MBAM 未辨識硬體類型）、硬體免除（硬體類型已識別且已標示為不受 MBAM 原則的免除），而且不會免除（硬體已識別且不會免除原則）。</span><span class="sxs-lookup"><span data-stu-id="83eed-127">There are three possible states: Hardware Unknown (the hardware type has not been identified by MBAM), Hardware Exempt (the hardware type was identified and was marked as exempt from MBAM policy), and Not Exempt (the hardware was identified and is not exempt from policy).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="83eed-128">裝置使用者</span><span class="sxs-lookup"><span data-stu-id="83eed-128">Device Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-129">由 MBAM 管理的電腦上的已知使用者。</span><span class="sxs-lookup"><span data-stu-id="83eed-129">Known users on the computer that is being managed by MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="83eed-130">合規性狀態詳細資料</span><span class="sxs-lookup"><span data-stu-id="83eed-130">Compliance Status Details</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-131">符合指定原則之電腦合規性狀態的錯誤與狀態訊息。</span><span class="sxs-lookup"><span data-stu-id="83eed-131">Error and status messages about the compliance state of the computer in accordance to the specified policy.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="83eed-132">最後一個連絡人</span><span class="sxs-lookup"><span data-stu-id="83eed-132">Last Contact</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-133">電腦上次與伺服器聯繫以報告合規性狀態的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="83eed-133">Date and time when the computer last contacted the server to report compliance status.</span></span> <span data-ttu-id="83eed-134">這次是可設定的。</span><span class="sxs-lookup"><span data-stu-id="83eed-134">This time is configurable.</span></span> <span data-ttu-id="83eed-135">請參閱 MBAM 原則設定。</span><span class="sxs-lookup"><span data-stu-id="83eed-135">See MBAM policy settings.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="83eed-136">企業合規性報告合規性狀態</span><span class="sxs-lookup"><span data-stu-id="83eed-136">Enterprise Compliance Report Compliance states</span></span>**

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="83eed-137">合規性狀態</span><span class="sxs-lookup"><span data-stu-id="83eed-137">Compliance Status</span></span></th>
<th align="left"><span data-ttu-id="83eed-138">免除</span><span class="sxs-lookup"><span data-stu-id="83eed-138">Exemption</span></span></th>
<th align="left"><span data-ttu-id="83eed-139">描述</span><span class="sxs-lookup"><span data-stu-id="83eed-139">Description</span></span></th>
<th align="left"><span data-ttu-id="83eed-140">使用者動作</span><span class="sxs-lookup"><span data-stu-id="83eed-140">User Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="83eed-141">標準</span><span class="sxs-lookup"><span data-stu-id="83eed-141">Noncompliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-142">未免除</span><span class="sxs-lookup"><span data-stu-id="83eed-142">Not Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-143">根據指定的原則，電腦不相容，且未以策略免除該硬體類型。</span><span class="sxs-lookup"><span data-stu-id="83eed-143">The computer is noncompliant according to the specified policy, and the hardware type has not been indicated as exempt from policy.</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-144">按一下 [ <strong> 電腦名稱稱] </strong> ，展開電腦合規性報告，並判斷每個磁片磁碟機的狀態是否符合指定的原則。</span><span class="sxs-lookup"><span data-stu-id="83eed-144">Click <strong>Computer Name</strong> to expand the Computer Compliance Report and determine whether the state of each drive complies with the specified policy.</span></span> <span data-ttu-id="83eed-145">如果加密狀態指出電腦未加密，可能仍在進行加密，或電腦上可能有錯誤。</span><span class="sxs-lookup"><span data-stu-id="83eed-145">If the encryption state indicates that the computer is not encrypted, encryption might still be in process, or there might be an error on the computer.</span></span> <span data-ttu-id="83eed-146">如果沒有錯誤，可能是因為電腦仍在連線或建立加密狀態的進程中。</span><span class="sxs-lookup"><span data-stu-id="83eed-146">If there is no error, the likely cause is that the computer is still in the process of connecting or establishing the encryption status.</span></span> <span data-ttu-id="83eed-147">稍後再次查看以判斷狀態是否變更。</span><span class="sxs-lookup"><span data-stu-id="83eed-147">Check back later to determine if the state changes.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="83eed-148">達到</span><span class="sxs-lookup"><span data-stu-id="83eed-148">Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-149">未免除</span><span class="sxs-lookup"><span data-stu-id="83eed-149">Not Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-150">根據指定的原則，電腦符合規範。</span><span class="sxs-lookup"><span data-stu-id="83eed-150">The computer is compliant in accordance with the specified policy.</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-151">不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="83eed-151">No Action needed.</span></span> <span data-ttu-id="83eed-152">您也可以選擇查看電腦合規性報告，以確認電腦的狀態。</span><span class="sxs-lookup"><span data-stu-id="83eed-152">Optionally, you can view the Computer Compliance Report to confirm the state of the computer.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="83eed-153">達到</span><span class="sxs-lookup"><span data-stu-id="83eed-153">Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-154">硬體豁免</span><span class="sxs-lookup"><span data-stu-id="83eed-154">Hardware Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-155">如果硬體類型是免除的。</span><span class="sxs-lookup"><span data-stu-id="83eed-155">If the Hardware type is exempt.</span></span> <span data-ttu-id="83eed-156">不論原則設定如何，或是每個硬驅的個別狀態，整體狀態都被認為是合規性的。</span><span class="sxs-lookup"><span data-stu-id="83eed-156">Regardless of how the policy is set or the individual status of each hard-drive, the overall state is considered to be compliant.</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-157">不需要任何動作。</span><span class="sxs-lookup"><span data-stu-id="83eed-157">No action needed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="83eed-158">達到</span><span class="sxs-lookup"><span data-stu-id="83eed-158">Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-159">硬體未知</span><span class="sxs-lookup"><span data-stu-id="83eed-159">Hardware Unknown</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-160">MBAM 會辨識硬體類型，但 MBAM 不知道它是不例外與否。</span><span class="sxs-lookup"><span data-stu-id="83eed-160">MBAM recognizes the hardware type, but MBAM does not know whether it is exempt or not exempt.</span></span> <span data-ttu-id="83eed-161">如果系統管理員沒有設定硬體的相容狀態，就會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="83eed-161">This occurs if the administrator has not set the Compatible status for the hardware.</span></span> <span data-ttu-id="83eed-162">因此，MBAM 預設會還原為相容性狀態。</span><span class="sxs-lookup"><span data-stu-id="83eed-162">Therefore, MBAM reverts to Compliant status by default.</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-163">這是新部署的 MBAM 用戶端的初始狀態。</span><span class="sxs-lookup"><span data-stu-id="83eed-163">This is the initial state of a newly deployed MBAM client.</span></span> <span data-ttu-id="83eed-164">通常只有暫時狀態。</span><span class="sxs-lookup"><span data-stu-id="83eed-164">It is typically only a transient state.</span></span> <span data-ttu-id="83eed-165">即使系統管理員已將硬體標示為相容，在用戶端電腦傳回報告前，可能會有很大的延遲或可設定的等待時間。</span><span class="sxs-lookup"><span data-stu-id="83eed-165">Even if the administrator has marked the Hardware as Compatible, there can be a significant delay or configurable wait time before the client computer reports back in.</span></span> <span data-ttu-id="83eed-166">記下最後一個聯絡人的時間，然後在指定的間隔之後再次查看，以查看狀態是否已變更。</span><span class="sxs-lookup"><span data-stu-id="83eed-166">Make note of the time of Last Contact, and check in again after the specified interval to see if the state has changed.</span></span> <span data-ttu-id="83eed-167">如果狀態沒有變更，此電腦或硬體類型可能會有錯誤。</span><span class="sxs-lookup"><span data-stu-id="83eed-167">If the state has not changed, there may be an error for this computer or hardware type.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="83eed-168">電腦合規性報告</span><span class="sxs-lookup"><span data-stu-id="83eed-168">Computer Compliance Report</span></span>

<span data-ttu-id="83eed-169">電腦合規性報告會顯示電腦或使用者專用的資訊。</span><span class="sxs-lookup"><span data-stu-id="83eed-169">The Computer Compliance Report displays information that is specific to a computer or user.</span></span>

<span data-ttu-id="83eed-170">電腦合規性報告會針對電腦上的每個磁片磁碟機提供詳細的加密資訊和適當的原則，包括操作系統磁碟機和固定資料磁碟機。</span><span class="sxs-lookup"><span data-stu-id="83eed-170">The Computer Compliance Report provides detailed encryption information and applicable policies for each drive on a computer, including operating system drives and fixed data drives.</span></span> <span data-ttu-id="83eed-171">若要查看此報告類型，請在企業合規性報告中按一下電腦名稱稱，或在電腦合規性報告中輸入電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="83eed-171">To view this report type, click the computer name in the Enterprise Compliance Report or type the computer name in the Computer Compliance Report.</span></span> <span data-ttu-id="83eed-172">若要查看每個磁片磁碟機的詳細資料，請展開 [電腦名稱稱] 專案。</span><span class="sxs-lookup"><span data-stu-id="83eed-172">To view the details of each drive, expand the Computer Name entry.</span></span>

<span data-ttu-id="83eed-173">**記事** 此報告不會提供可移除資料量的加密狀態。</span><span class="sxs-lookup"><span data-stu-id="83eed-173">**Note** This report does not provide encryption status for Removable Data Volumes.</span></span>

 

**<span data-ttu-id="83eed-174">電腦合規性報告欄位</span><span class="sxs-lookup"><span data-stu-id="83eed-174">Computer Compliance Report fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="83eed-175">欄名稱</span><span class="sxs-lookup"><span data-stu-id="83eed-175">Column Name</span></span></th>
<th align="left"><span data-ttu-id="83eed-176">描述</span><span class="sxs-lookup"><span data-stu-id="83eed-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="83eed-177">電腦名稱稱</span><span class="sxs-lookup"><span data-stu-id="83eed-177">Computer Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-178">由 MBAM 管理的使用者指定 DNS 電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="83eed-178">The user-specified DNS computer name that is being managed by MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="83eed-179">網功能變數名稱稱</span><span class="sxs-lookup"><span data-stu-id="83eed-179">Domain Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-180">用戶端電腦所在的完整功能變數名稱，且由 MBAM 管理。</span><span class="sxs-lookup"><span data-stu-id="83eed-180">The fully qualified domain name where the client computer resides and is managed by MBAM.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="83eed-181">電腦類型</span><span class="sxs-lookup"><span data-stu-id="83eed-181">Computer Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-182">電腦的可攜性類型。</span><span class="sxs-lookup"><span data-stu-id="83eed-182">The portability type of computer.</span></span> <span data-ttu-id="83eed-183">有效類型為非便攜且可移植。</span><span class="sxs-lookup"><span data-stu-id="83eed-183">Valid types are non-Portable and Portable.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="83eed-184">作業系統</span><span class="sxs-lookup"><span data-stu-id="83eed-184">Operating System</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-185">在 MBAM managed 用戶端電腦上安裝的作業系統類型。</span><span class="sxs-lookup"><span data-stu-id="83eed-185">Operating System type installed on the MBAM managed client computer.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="83eed-186">合規性狀態</span><span class="sxs-lookup"><span data-stu-id="83eed-186">Compliance Status</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-187">由 MBAM 管理之電腦的整體合規性狀態。</span><span class="sxs-lookup"><span data-stu-id="83eed-187">The overall Compliance Status of the computer managed by MBAM.</span></span> <span data-ttu-id="83eed-188">有效的狀態是相容且不相容。</span><span class="sxs-lookup"><span data-stu-id="83eed-188">Valid states are Compliant and Noncompliant.</span></span> <span data-ttu-id="83eed-189">雖然您可以在同一部電腦中擁有相容且不相容的磁片磁碟機，但這個欄位會指出每個指定原則的電腦總體相容性。</span><span class="sxs-lookup"><span data-stu-id="83eed-189">While it is possible to have Compliant and Noncompliant drives in the same computer, this field indicates the overall computer compliance per specified policy.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="83eed-190">原則 Cypher 強度</span><span class="sxs-lookup"><span data-stu-id="83eed-190">Policy Cypher Strength</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-191">MBAM 原則規格期間管理員所選取的密碼強度。</span><span class="sxs-lookup"><span data-stu-id="83eed-191">The Cipher Strength selected by the Administrator during MBAM policy specification.</span></span> <span data-ttu-id="83eed-192">例如，使用擴散器的128位</span><span class="sxs-lookup"><span data-stu-id="83eed-192">For example, 128-bit with Diffuser</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="83eed-193">原則作業系統磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="83eed-193">Policy Operating System Drive</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-194">指明 O/S 和保護器類型是否適用，是否需要加密。</span><span class="sxs-lookup"><span data-stu-id="83eed-194">Indicates whether encryption is required for the O/S and the protector type as applicable.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="83eed-195">原則固定資料磁碟機</span><span class="sxs-lookup"><span data-stu-id="83eed-195">Policy Fixed Data Drive</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-196">指出固定磁碟機是否需要加密。</span><span class="sxs-lookup"><span data-stu-id="83eed-196">Indicates whether encryption is required for the Fixed Drive.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="83eed-197">策略移除資料磁碟機</span><span class="sxs-lookup"><span data-stu-id="83eed-197">Policy Removable Data Drive</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-198">指出抽取式磁碟磁碟機是否需要加密。</span><span class="sxs-lookup"><span data-stu-id="83eed-198">Indicates whether encryption is required for the Removable Drive.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="83eed-199">裝置使用者</span><span class="sxs-lookup"><span data-stu-id="83eed-199">Device Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-200">提供電腦上已知使用者的身分識別。</span><span class="sxs-lookup"><span data-stu-id="83eed-200">Provides the identity of known users on the computer.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="83eed-201">免除</span><span class="sxs-lookup"><span data-stu-id="83eed-201">Exemption</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-202">指出電腦硬體類型是否可由 MBAM 辨識，如果已知，是否已將電腦指示為策略例外。</span><span class="sxs-lookup"><span data-stu-id="83eed-202">Indicates whether the computer hardware type is recognized by MBAM and, if known, whether the computer has been indicated as exempt from policy.</span></span> <span data-ttu-id="83eed-203">有三種狀態：硬體未知（MBAM 已找不到硬體類型）;硬體例外（硬體類型已識別且已標示為不受 MBAM 原則的免除）;而且不會免除（硬體已識別且不是從原則免除）。</span><span class="sxs-lookup"><span data-stu-id="83eed-203">There are three states: Hardware Unknown (the hardware type has not been identified by MBAM); Hardware Exempt (the hardware type was identified and was marked as exempt from MBAM policy); and Not Exempt (the hardware was identified and is not exempt from policy).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="83eed-204">製造商</span><span class="sxs-lookup"><span data-stu-id="83eed-204">Manufacturer</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-205">電腦製造商出現在電腦 BIOS 中的名稱。</span><span class="sxs-lookup"><span data-stu-id="83eed-205">The computer manufacturer name as it appears in the computer BIOS.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="83eed-206">型號</span><span class="sxs-lookup"><span data-stu-id="83eed-206">Model</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-207">電腦製造商模型名稱，顯示在電腦 BIOS 中。</span><span class="sxs-lookup"><span data-stu-id="83eed-207">The computer manufacturer model name as it appears in the computer BIOS.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="83eed-208">合規性狀態詳細資料</span><span class="sxs-lookup"><span data-stu-id="83eed-208">Compliance Status Details</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-209">根據指定原則，電腦符合性狀態的錯誤與狀態訊息。</span><span class="sxs-lookup"><span data-stu-id="83eed-209">Error and status messages of the compliance state of the computer in accordance with the specified policy.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="83eed-210">最後一個連絡人</span><span class="sxs-lookup"><span data-stu-id="83eed-210">Last Contact</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-211">電腦上次取得伺服器以報告合規性狀態的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="83eed-211">Date and time that the computer last contacted the server to report compliance status.</span></span> <span data-ttu-id="83eed-212">T</span><span class="sxs-lookup"><span data-stu-id="83eed-212">T</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="83eed-213">電腦合規性報告磁片磁碟機欄位</span><span class="sxs-lookup"><span data-stu-id="83eed-213">Computer Compliance Report Drive fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="83eed-214">欄名稱</span><span class="sxs-lookup"><span data-stu-id="83eed-214">Column Name</span></span></th>
<th align="left"><span data-ttu-id="83eed-215">描述</span><span class="sxs-lookup"><span data-stu-id="83eed-215">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="83eed-216">磁片磁碟機盤符</span><span class="sxs-lookup"><span data-stu-id="83eed-216">Drive Letter</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-217">使用者指派給這個特定磁片磁碟機的電腦磁碟機盤符。</span><span class="sxs-lookup"><span data-stu-id="83eed-217">Computer drive letter that was assigned to this particular drive by the user.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="83eed-218">磁片磁碟機類型</span><span class="sxs-lookup"><span data-stu-id="83eed-218">Drive Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-219">磁片磁碟機類型。</span><span class="sxs-lookup"><span data-stu-id="83eed-219">Type of drive.</span></span> <span data-ttu-id="83eed-220">有效值為作業系統磁片磁碟機及固定資料磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="83eed-220">Valid values are Operating System Drive and Fixed Data Drive.</span></span> <span data-ttu-id="83eed-221">這些是物理磁片磁碟機，而不是邏輯磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="83eed-221">These are physical drives rather than logical volumes.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="83eed-222">Cypher 強度</span><span class="sxs-lookup"><span data-stu-id="83eed-222">Cypher Strength</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-223">管理員在 MBAM 原則規格期間選取的密碼強度。</span><span class="sxs-lookup"><span data-stu-id="83eed-223">Cipher Strength selected by the Administrator during MBAM policy specification.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="83eed-224">保護器類型</span><span class="sxs-lookup"><span data-stu-id="83eed-224">Protector Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-225">透過用來加密作業系統或固定容量的原則所選取的保護者類型。</span><span class="sxs-lookup"><span data-stu-id="83eed-225">Type of protector selected via policy used to encrypt an operating system or Fixed volume.</span></span> <span data-ttu-id="83eed-226">作業系統磁片磁碟機上的有效保護器類型為 [TPM] 或 [TPM + PIN]。</span><span class="sxs-lookup"><span data-stu-id="83eed-226">The valid protector types on an operating system drive are TPM or TPM+PIN.</span></span> <span data-ttu-id="83eed-227">固定資料量的唯一有效保護器類型為 [密碼]。</span><span class="sxs-lookup"><span data-stu-id="83eed-227">The only valid protector type for a Fixed Data Volume is Password.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="83eed-228">保護器狀態</span><span class="sxs-lookup"><span data-stu-id="83eed-228">Protector State</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-229">此欄位會指出電腦是否已啟用原則中指定的保護器類型。</span><span class="sxs-lookup"><span data-stu-id="83eed-229">This field indicates whether the computer has enabled the protector type specified in the policy.</span></span> <span data-ttu-id="83eed-230">[有效] 狀態為 [開啟] 或 [關閉]。</span><span class="sxs-lookup"><span data-stu-id="83eed-230">The valid states are ON or OFF.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="83eed-231">加密狀態</span><span class="sxs-lookup"><span data-stu-id="83eed-231">Encryption State</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-232">這是磁片的目前加密狀態。</span><span class="sxs-lookup"><span data-stu-id="83eed-232">This is the current encryption state of the drive.</span></span> <span data-ttu-id="83eed-233">有效的狀態為 [已加密]、[未加密] 和 [加密]。</span><span class="sxs-lookup"><span data-stu-id="83eed-233">Valid states are Encrypted, Not Encrypted, and Encrypting.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="83eed-234">合規性狀態</span><span class="sxs-lookup"><span data-stu-id="83eed-234">Compliance Status</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-235">指出磁片磁碟機是否符合原則。</span><span class="sxs-lookup"><span data-stu-id="83eed-235">Indicates whether the drive is in accordance with the policy.</span></span> <span data-ttu-id="83eed-236">狀態為不相容且合規性。</span><span class="sxs-lookup"><span data-stu-id="83eed-236">States are Noncompliant and Compliant.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="83eed-237">合規性狀態詳細資料</span><span class="sxs-lookup"><span data-stu-id="83eed-237">Compliance Status Details</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-238">包含有關電腦合規性狀態的錯誤與狀態訊息。</span><span class="sxs-lookup"><span data-stu-id="83eed-238">Contains error and status messages regarding the compliance state of the computer.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="83eed-239">硬體審計報告</span><span class="sxs-lookup"><span data-stu-id="83eed-239">Hardware Audit Report</span></span>

<span data-ttu-id="83eed-240">此報告可協助您審核對特定電腦產生與模型的硬體相容性狀態所做的變更。</span><span class="sxs-lookup"><span data-stu-id="83eed-240">This report can help you audit changes to the Hardware Compatibility status of specific computer makes and models.</span></span> <span data-ttu-id="83eed-241">為了協助您縮小搜尋結果的範圍，此報告包含篩選準則的篩選，例如變更類型和時間發生的時間。</span><span class="sxs-lookup"><span data-stu-id="83eed-241">To help you narrow your search results, this report includes filtering on criteria such as type of change and time of occurrence.</span></span> <span data-ttu-id="83eed-242">每個狀態變更都是依使用者及日期和時間進行追蹤。</span><span class="sxs-lookup"><span data-stu-id="83eed-242">Each state change is tracked by user and date and time.</span></span> <span data-ttu-id="83eed-243">硬體類型是由在用戶端電腦上執行的 MBAM 代理程式自動填入。</span><span class="sxs-lookup"><span data-stu-id="83eed-243">The Hardware Type is automatically populated by the MBAM agent that runs on the client computer.</span></span> <span data-ttu-id="83eed-244">此報告會追蹤使用者對從 MBAM managed 電腦直接收集之資訊所做的變更。</span><span class="sxs-lookup"><span data-stu-id="83eed-244">This report tracks user changes to the information collected directly from the MBAM managed computer.</span></span> <span data-ttu-id="83eed-245">典型的管理變更是從 [相容性] 變更為 [不相容]。</span><span class="sxs-lookup"><span data-stu-id="83eed-245">A typical administrative change is changing from Compatible to incompatible.</span></span> <span data-ttu-id="83eed-246">不過，系統管理員也可以修改任何欄位。</span><span class="sxs-lookup"><span data-stu-id="83eed-246">However, the administrator can also revise any field.</span></span>

**<span data-ttu-id="83eed-247">硬體審計報告欄位</span><span class="sxs-lookup"><span data-stu-id="83eed-247">Hardware Audit Report fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="83eed-248">欄名稱</span><span class="sxs-lookup"><span data-stu-id="83eed-248">Column Name</span></span></th>
<th align="left"><span data-ttu-id="83eed-249">描述</span><span class="sxs-lookup"><span data-stu-id="83eed-249">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="83eed-250">日期及時間</span><span class="sxs-lookup"><span data-stu-id="83eed-250">Date and Time</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-251">對硬體類型進行變更的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="83eed-251">Date and time that a change was made to the Hardware Type.</span></span> <span data-ttu-id="83eed-252">請注意，每個唯一的硬體類型都指派給至少一個專案。</span><span class="sxs-lookup"><span data-stu-id="83eed-252">Note that every unique hardware type is assigned to at least one entry.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="83eed-253">使用者</span><span class="sxs-lookup"><span data-stu-id="83eed-253">User</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-254">已針對特定專案進行變更的管理使用者。</span><span class="sxs-lookup"><span data-stu-id="83eed-254">Administrative user that has made the change for the particular entry.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="83eed-255">變更類型</span><span class="sxs-lookup"><span data-stu-id="83eed-255">Change Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-256">對硬體類型資訊所做的變更類型。</span><span class="sxs-lookup"><span data-stu-id="83eed-256">Type of change that was made to the hardware type information.</span></span> <span data-ttu-id="83eed-257">有效值為加法（新增專案）、更新（變更現有專案）或刪除（移除現有的專案）。</span><span class="sxs-lookup"><span data-stu-id="83eed-257">Valid values are Addition (new entry), Update (change existing entry), or Deletion (remove existing entry).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="83eed-258">原始值</span><span class="sxs-lookup"><span data-stu-id="83eed-258">Original Value</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-259">變更之前的硬體類型規格值。</span><span class="sxs-lookup"><span data-stu-id="83eed-259">Value of the hardware type specification before the change was made.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="83eed-260">目前值</span><span class="sxs-lookup"><span data-stu-id="83eed-260">Current Value</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-261">變更之後硬體類型規格的值。</span><span class="sxs-lookup"><span data-stu-id="83eed-261">Value of the hardware type specification after the change was made.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="83eed-262">復原審核報告</span><span class="sxs-lookup"><span data-stu-id="83eed-262">Recovery Audit Report</span></span>

<span data-ttu-id="83eed-263">[恢復審核報告] 可協助您審核已要求存取復原金鑰的使用者。</span><span class="sxs-lookup"><span data-stu-id="83eed-263">The Recovery Audit Report can help you audit users who have requested access to recovery keys.</span></span> <span data-ttu-id="83eed-264">此報告的篩選準則包括提出要求的使用者類型、要求的金鑰類型、發生時間、成功或失敗、發生時間及使用者要求的類型（說明服務台、最終使用者）。</span><span class="sxs-lookup"><span data-stu-id="83eed-264">The filter criteria for this report includes type of user making the request, type of key requested, time of occurrence, success or fail, time of occurrence, and type of user requesting (help desk, end user).</span></span> <span data-ttu-id="83eed-265">此報告可讓系統管理員根據需要產生內容報告。</span><span class="sxs-lookup"><span data-stu-id="83eed-265">This report enables administrators to produce contextual reports based on need.</span></span>

**<span data-ttu-id="83eed-266">復原審核報告欄位</span><span class="sxs-lookup"><span data-stu-id="83eed-266">Recovery Audit Report Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="83eed-267">欄名稱</span><span class="sxs-lookup"><span data-stu-id="83eed-267">Column Name</span></span></th>
<th align="left"><span data-ttu-id="83eed-268">描述</span><span class="sxs-lookup"><span data-stu-id="83eed-268">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="83eed-269">要求日期和時間</span><span class="sxs-lookup"><span data-stu-id="83eed-269">Request Date and Time</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-270">由最終使用者或技術支援人員使用者所做的金鑰檢索要求的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="83eed-270">The date and time that a key retrieval request was made by an end user or help desk user.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="83eed-271">要求狀態</span><span class="sxs-lookup"><span data-stu-id="83eed-271">Request Status</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-272">要求的狀態。</span><span class="sxs-lookup"><span data-stu-id="83eed-272">Status of the request.</span></span> <span data-ttu-id="83eed-273">有效狀態為成功（檢索到金鑰）或失敗（未檢索到金鑰）。</span><span class="sxs-lookup"><span data-stu-id="83eed-273">Valid statuses are either Successful (the key was retrieved) or Failed (the key was not retrieved).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="83eed-274">支援人員的使用者</span><span class="sxs-lookup"><span data-stu-id="83eed-274">Helpdesk User</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-275">啟動金鑰取回要求的技術支援使用者。</span><span class="sxs-lookup"><span data-stu-id="83eed-275">The help desk user who initiated the request for key retrieval.</span></span> <span data-ttu-id="83eed-276">如果技術支援人員代表使用者自行取得金鑰，則 [最終使用者] 欄位會是空白的。</span><span class="sxs-lookup"><span data-stu-id="83eed-276">If the help desk user retrieves the key on behalf of an end user, the End User field will be blank.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="83eed-277">使用者</span><span class="sxs-lookup"><span data-stu-id="83eed-277">User</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-278">已啟動金鑰取回要求的最終使用者。</span><span class="sxs-lookup"><span data-stu-id="83eed-278">The end user who initiated the request for key retrieval.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="83eed-279">金鑰類型</span><span class="sxs-lookup"><span data-stu-id="83eed-279">Key Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-280">所要求的金鑰類型。</span><span class="sxs-lookup"><span data-stu-id="83eed-280">The type of key that was requested.</span></span> <span data-ttu-id="83eed-281">MBAM 會收集三個主要類型：復原金鑰密碼（在復原模式中復原電腦）;復原金鑰識別碼（代表另一個使用者在復原模式中復原電腦）;以及受信任的平臺模組（TPM）密碼雜湊（使用已鎖定的 TPM 復原電腦）。</span><span class="sxs-lookup"><span data-stu-id="83eed-281">MBAM collects three key types: Recovery Key Password (to recovery a computer in recovery mode); Recovery Key ID (to recover a computer in recovery mode on behalf of another user); and Trusted Platform Module (TPM) Password Hash (to recover a computer with a locked TPM).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="83eed-282">原因描述</span><span class="sxs-lookup"><span data-stu-id="83eed-282">Reason Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="83eed-283">要求指定的金鑰類型的原因。</span><span class="sxs-lookup"><span data-stu-id="83eed-283">The reason that the specified Key Type was requested.</span></span> <span data-ttu-id="83eed-284">原因是在系統管理網站的 [磁碟機復原] 和 [管理 TPM 功能] 中指定。</span><span class="sxs-lookup"><span data-stu-id="83eed-284">The reasons are specified in the Drive Recovery and Manage TPM features of the Administrative web site.</span></span> <span data-ttu-id="83eed-285">有效的專案包括使用者輸入的文字或下列其中一個原因代碼：</span><span class="sxs-lookup"><span data-stu-id="83eed-285">Valid entries include user-entered text or one of the following reason codes:</span></span></p>
<ul>
<li><p><span data-ttu-id="83eed-286">作業系統啟動順序已變更</span><span class="sxs-lookup"><span data-stu-id="83eed-286">Operating System Boot Order changed</span></span></p></li>
<li><p><span data-ttu-id="83eed-287">BIOS 已變更</span><span class="sxs-lookup"><span data-stu-id="83eed-287">BIOS changed</span></span></p></li>
<li><p><span data-ttu-id="83eed-288">已變更作業系統檔案</span><span class="sxs-lookup"><span data-stu-id="83eed-288">Operating System files changed</span></span></p></li>
<li><p><span data-ttu-id="83eed-289">遺失的啟動金鑰</span><span class="sxs-lookup"><span data-stu-id="83eed-289">Lost Startup key</span></span></p></li>
<li><p><span data-ttu-id="83eed-290">遺失的 PIN</span><span class="sxs-lookup"><span data-stu-id="83eed-290">Lost PIN</span></span></p></li>
<li><p><span data-ttu-id="83eed-291">TPM 重設</span><span class="sxs-lookup"><span data-stu-id="83eed-291">TPM Reset</span></span></p></li>
<li><p><span data-ttu-id="83eed-292">遺失密碼</span><span class="sxs-lookup"><span data-stu-id="83eed-292">Lost Passphrase</span></span></p></li>
<li><p><span data-ttu-id="83eed-293">遺失的智慧卡</span><span class="sxs-lookup"><span data-stu-id="83eed-293">Lost Smartcard</span></span></p></li>
<li><p><span data-ttu-id="83eed-294">重設 PIN 鎖定</span><span class="sxs-lookup"><span data-stu-id="83eed-294">Reset PIN lockout</span></span></p></li>
<li><p><span data-ttu-id="83eed-295">開啟 TPM</span><span class="sxs-lookup"><span data-stu-id="83eed-295">Turn on TPM</span></span></p></li>
<li><p><span data-ttu-id="83eed-296">關閉 TPM</span><span class="sxs-lookup"><span data-stu-id="83eed-296">Turn off TPM</span></span></p></li>
<li><p><span data-ttu-id="83eed-297">變更 TPM 密碼</span><span class="sxs-lookup"><span data-stu-id="83eed-297">Change TPM password</span></span></p></li>
<li><p><span data-ttu-id="83eed-298">清除 TPM</span><span class="sxs-lookup"><span data-stu-id="83eed-298">Clear TPM</span></span></p></li>
</ul>
<p></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="83eed-299">**記事** 若要將報表結果儲存至檔案，請按一下 [報表] 功能表列上的 [**匯出**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="83eed-299">**Note** To save report results to a file, click the **Export** button on the reports menu bar.</span></span>

 

## <span data-ttu-id="83eed-300">相關主題</span><span class="sxs-lookup"><span data-stu-id="83eed-300">Related topics</span></span>


[<span data-ttu-id="83eed-301">使用 MBAM 1.0 監視與報告 BitLocker 符合性</span><span class="sxs-lookup"><span data-stu-id="83eed-301">Monitoring and Reporting BitLocker Compliance with MBAM 1.0</span></span>](monitoring-and-reporting-bitlocker-compliance-with-mbam-10.md)

 

 





