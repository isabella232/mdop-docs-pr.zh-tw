---
title: 了解 MBAM 2.5 獨立報告
description: 了解 MBAM 2.5 獨立報告
author: dansimp
ms.assetid: 78b5aaf4-8257-4722-8eb9-e0de48db6a11
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 45e84c7c3b2bcb1602890c7c5a09592324da691e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800178"
---
# <span data-ttu-id="3e908-103">了解 MBAM 2.5 獨立報告</span><span class="sxs-lookup"><span data-stu-id="3e908-103">Understanding MBAM 2.5 Stand-alone Reports</span></span>


<span data-ttu-id="3e908-104">本主題說明當您在獨立拓撲中執行 Microsoft BitLocker 管理和監控（MBAM）時可使用的報表。</span><span class="sxs-lookup"><span data-stu-id="3e908-104">This topic describes the reports that are available when you are running Microsoft BitLocker Administration and Monitoring (MBAM) in the Stand-alone topology.</span></span>

**<span data-ttu-id="3e908-105">注意</span><span class="sxs-lookup"><span data-stu-id="3e908-105">Note</span></span>**  
<span data-ttu-id="3e908-106">如果您是使用 Configuration Manager 整合拓朴執行 MBAM，則會從 Configuration Manager 產生報表，而不是從 MBAM。</span><span class="sxs-lookup"><span data-stu-id="3e908-106">If you are running MBAM with the Configuration Manager Integration topology, you generate reports from Configuration Manager rather than from MBAM.</span></span> <span data-ttu-id="3e908-107">如需有關這些報告的詳細資訊，請參閱[查看 Configuration Manager 整合拓朴的 MBAM 2.5 報告](viewing-mbam-25-reports-for-the-configuration-manager-integration-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="3e908-107">See [Viewing MBAM 2.5 Reports for the Configuration Manager Integration Topology](viewing-mbam-25-reports-for-the-configuration-manager-integration-topology.md) for more information about these reports.</span></span>



## <span data-ttu-id="3e908-108">瞭解 MBAM 獨立拓朴報告</span><span class="sxs-lookup"><span data-stu-id="3e908-108">Understanding the MBAM Stand-alone topology reports</span></span>


<span data-ttu-id="3e908-109">MBAM 提供三種報告類型，您可以用來監視貴組織的 BitLocker 合規性：</span><span class="sxs-lookup"><span data-stu-id="3e908-109">MBAM provides three report types that you can use to monitor your organization for BitLocker compliance:</span></span>

-   [<span data-ttu-id="3e908-110">企業合規性報告</span><span class="sxs-lookup"><span data-stu-id="3e908-110">Enterprise Compliance Report</span></span>](#bkmk-enterprisecompliance)

-   [<span data-ttu-id="3e908-111">電腦合規性報告</span><span class="sxs-lookup"><span data-stu-id="3e908-111">Computer Compliance Report</span></span>](#bkmk-compliance)

-   [<span data-ttu-id="3e908-112">復原審核報告</span><span class="sxs-lookup"><span data-stu-id="3e908-112">Recovery Audit Report</span></span>](#bkmk-recovery)

<span data-ttu-id="3e908-113">若要在獨立拓撲中執行 MBAM 時存取 MBAM 報表，請開啟網頁瀏覽器，然後開啟 [管理及監視] 網站。</span><span class="sxs-lookup"><span data-stu-id="3e908-113">To access MBAM reports when you are running MBAM in the Stand-alone topology, open a web browser, and then open the Administration and Monitoring Website.</span></span> <span data-ttu-id="3e908-114">選取左側功能表列中的 [**報表**]。</span><span class="sxs-lookup"><span data-stu-id="3e908-114">Select **Reports** in the left menu bar.</span></span> <span data-ttu-id="3e908-115">從上方的功能表列中，選取您要產生的報表類型。</span><span class="sxs-lookup"><span data-stu-id="3e908-115">From the top menu bar, select the kind of report that you want to generate.</span></span> <span data-ttu-id="3e908-116">如需有關產生這些報告的詳細資訊，請參閱[產生 MBAM 2.5 獨立報告](generating-mbam-25-stand-alone-reports.md)。</span><span class="sxs-lookup"><span data-stu-id="3e908-116">For more information about generating these reports, see [Generating MBAM 2.5 Stand-alone Reports](generating-mbam-25-stand-alone-reports.md).</span></span>

### <a href="" id="bkmk-enterprisecompliance"></a><span data-ttu-id="3e908-117">企業合規性報告</span><span class="sxs-lookup"><span data-stu-id="3e908-117">Enterprise Compliance Report</span></span>

<span data-ttu-id="3e908-118">使用此報告類型，收集貴組織中的整體 BitLocker 規範資訊。</span><span class="sxs-lookup"><span data-stu-id="3e908-118">Use this report type to collect information about overall BitLocker compliance in your organization.</span></span> <span data-ttu-id="3e908-119">您可以使用篩選來縮小搜尋結果的範圍，以深入瞭解貴組織中電腦的相容性狀態與錯誤狀態。</span><span class="sxs-lookup"><span data-stu-id="3e908-119">You can use filters to narrow your search results to learn more about the compliance state and error status of computers in your organization.</span></span>

**<span data-ttu-id="3e908-120">企業合規性概述</span><span class="sxs-lookup"><span data-stu-id="3e908-120">Enterprise Compliance Overview</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3e908-121">欄名稱</span><span class="sxs-lookup"><span data-stu-id="3e908-121">Column Name</span></span></th>
<th align="left"><span data-ttu-id="3e908-122">描述</span><span class="sxs-lookup"><span data-stu-id="3e908-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3e908-123">受管理的電腦</span><span class="sxs-lookup"><span data-stu-id="3e908-123">Managed Computers</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-124">MBAM 管理的電腦數。</span><span class="sxs-lookup"><span data-stu-id="3e908-124">Number of computers that MBAM manages.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3e908-125">符合百分比</span><span class="sxs-lookup"><span data-stu-id="3e908-125">% Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-126">企業中合規性電腦的百分比。</span><span class="sxs-lookup"><span data-stu-id="3e908-126">Percentage of compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3e908-127">非相容性%</span><span class="sxs-lookup"><span data-stu-id="3e908-127">% Non-Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-128">企業中不相容的電腦百分比。</span><span class="sxs-lookup"><span data-stu-id="3e908-128">Percentage of non-compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3e908-129">% 豁免</span><span class="sxs-lookup"><span data-stu-id="3e908-129">% Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-130">免除 BitLocker 加密需求的電腦所占的百分比。</span><span class="sxs-lookup"><span data-stu-id="3e908-130">Percentage of computers exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3e908-131">非豁免%</span><span class="sxs-lookup"><span data-stu-id="3e908-131">% Non-Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-132">不受 BitLocker 加密需求免除的電腦百分比。</span><span class="sxs-lookup"><span data-stu-id="3e908-132">Percentage of computers not exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3e908-133">達到</span><span class="sxs-lookup"><span data-stu-id="3e908-133">Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-134">企業中合規性電腦的百分比。</span><span class="sxs-lookup"><span data-stu-id="3e908-134">Percentage of compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3e908-135">不相容</span><span class="sxs-lookup"><span data-stu-id="3e908-135">Non-Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-136">企業中不相容的電腦百分比。</span><span class="sxs-lookup"><span data-stu-id="3e908-136">Percentage of non-compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3e908-137">免除</span><span class="sxs-lookup"><span data-stu-id="3e908-137">Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-138">免除 BitLocker 加密需求的電腦總數。</span><span class="sxs-lookup"><span data-stu-id="3e908-138">Total computers that are exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3e908-139">非豁免</span><span class="sxs-lookup"><span data-stu-id="3e908-139">Non-Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-140">未免除 BitLocker 加密需求的電腦總數。</span><span class="sxs-lookup"><span data-stu-id="3e908-140">Total computers that are not exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="3e908-141">企業規範電腦詳細資料</span><span class="sxs-lookup"><span data-stu-id="3e908-141">Enterprise Compliance Computer Details</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3e908-142">欄名稱</span><span class="sxs-lookup"><span data-stu-id="3e908-142">Column Name</span></span></th>
<th align="left"><span data-ttu-id="3e908-143">描述</span><span class="sxs-lookup"><span data-stu-id="3e908-143">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3e908-144">電腦名稱稱</span><span class="sxs-lookup"><span data-stu-id="3e908-144">Computer Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-145">由 MBAM 管理的使用者指定 DNS 名稱。</span><span class="sxs-lookup"><span data-stu-id="3e908-145">User-specified DNS name that is managed by MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3e908-146">網功能變數名稱稱</span><span class="sxs-lookup"><span data-stu-id="3e908-146">Domain Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-147">用戶端電腦所在的完整功能變數名稱，且由 MBAM 管理。</span><span class="sxs-lookup"><span data-stu-id="3e908-147">Fully qualified domain name where the client computer resides and is managed by MBAM.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3e908-148">合規性狀態</span><span class="sxs-lookup"><span data-stu-id="3e908-148">Compliance Status</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-149">根據電腦所指定的原則，為電腦提供符合的狀態。</span><span class="sxs-lookup"><span data-stu-id="3e908-149">State of compliance for the computer, according to the policy specified for the computer.</span></span> <span data-ttu-id="3e908-150">狀態是不相容且合規性。</span><span class="sxs-lookup"><span data-stu-id="3e908-150">The states are Noncompliant and Compliant.</span></span> <span data-ttu-id="3e908-151">如需有關如何解讀合規性狀態的詳細資訊，請參閱下列企業合規性報告相容性狀態資料表。</span><span class="sxs-lookup"><span data-stu-id="3e908-151">See the following Enterprise Compliance Report Compliance States table for more information about how to interpret compliance states.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3e908-152">免除</span><span class="sxs-lookup"><span data-stu-id="3e908-152">Exemption</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-153">指出此電腦是否不受 BitLocker 原則免除的狀態。</span><span class="sxs-lookup"><span data-stu-id="3e908-153">Status that indicates whether this computer is exempt from the BitLocker policy.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3e908-154">合規性狀態詳細資料</span><span class="sxs-lookup"><span data-stu-id="3e908-154">Compliance Status Details</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-155">符合指定原則之電腦符合性狀態的錯誤與狀態訊息。</span><span class="sxs-lookup"><span data-stu-id="3e908-155">Error and status messages about the compliance state of the computer in accordance to the policy specified.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3e908-156">最後一個連絡人</span><span class="sxs-lookup"><span data-stu-id="3e908-156">Last Contact</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-157">電腦上次與伺服器聯繫以報告合規性狀態的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="3e908-157">Date and time when the computer last contacted the server to report compliance status.</span></span> <span data-ttu-id="3e908-158">連絡人頻率是可設定的。</span><span class="sxs-lookup"><span data-stu-id="3e908-158">The contact frequency is configurable.</span></span> <span data-ttu-id="3e908-159">如需詳細資訊，請參閱 MBAM 群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="3e908-159">For more information, see the MBAM Group Policy settings.</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-compliance"></a><span data-ttu-id="3e908-160">電腦合規性報告</span><span class="sxs-lookup"><span data-stu-id="3e908-160">Computer Compliance Report</span></span>

<span data-ttu-id="3e908-161">使用此報告類型可收集電腦或使用者專用的資訊。</span><span class="sxs-lookup"><span data-stu-id="3e908-161">Use this report type to collect information that is specific to a computer or user.</span></span>

<span data-ttu-id="3e908-162">若要查看此報告，請按一下企業合規性報告中的電腦名稱稱，或在電腦合規性報告中輸入電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="3e908-162">View this report by clicking the computer name in the Enterprise Compliance Report, or by typing the computer name in the Computer Compliance Report.</span></span> <span data-ttu-id="3e908-163">此報告顯示電腦上每個磁片磁碟機（作業系統及固定資料磁碟機）的詳細加密資訊。</span><span class="sxs-lookup"><span data-stu-id="3e908-163">This report shows detailed encryption information about each drive (operating system and fixed data drives) on a computer.</span></span> <span data-ttu-id="3e908-164">它也會指出已套用到電腦上每個磁片磁碟機類型的原則。</span><span class="sxs-lookup"><span data-stu-id="3e908-164">It also indicates the policy that is applied to each drive type on the computer.</span></span> <span data-ttu-id="3e908-165">若要查看每個磁片磁碟機的詳細資料，請展開 [電腦名稱稱] 專案。</span><span class="sxs-lookup"><span data-stu-id="3e908-165">To view the details of each drive, expand the Computer Name entry.</span></span>

**<span data-ttu-id="3e908-166">注意</span><span class="sxs-lookup"><span data-stu-id="3e908-166">Note</span></span>**  
<span data-ttu-id="3e908-167">在此報告中不會顯示 [可移動資料量] 加密狀態。</span><span class="sxs-lookup"><span data-stu-id="3e908-167">Removable Data Volume encryption status is not shown in this report.</span></span>



**<span data-ttu-id="3e908-168">電腦合規性報告欄位</span><span class="sxs-lookup"><span data-stu-id="3e908-168">Computer Compliance Report Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3e908-169">欄名稱</span><span class="sxs-lookup"><span data-stu-id="3e908-169">Column Name</span></span></th>
<th align="left"><span data-ttu-id="3e908-170">描述</span><span class="sxs-lookup"><span data-stu-id="3e908-170">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3e908-171">電腦名稱稱</span><span class="sxs-lookup"><span data-stu-id="3e908-171">Computer Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-172">由 MBAM 管理的使用者指定 DNS 電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="3e908-172">User-specified DNS computer name that is managed by MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3e908-173">網功能變數名稱稱</span><span class="sxs-lookup"><span data-stu-id="3e908-173">Domain Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-174">用戶端電腦所在的完整功能變數名稱，且由 MBAM 管理。</span><span class="sxs-lookup"><span data-stu-id="3e908-174">Fully qualified domain name where the client computer resides and is managed by MBAM.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3e908-175">電腦類型</span><span class="sxs-lookup"><span data-stu-id="3e908-175">Computer Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-176">電腦類型。</span><span class="sxs-lookup"><span data-stu-id="3e908-176">Type of computer.</span></span> <span data-ttu-id="3e908-177">有效類型為非便攜且可移植。</span><span class="sxs-lookup"><span data-stu-id="3e908-177">Valid types are Non-Portable and Portable.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3e908-178">作業系統</span><span class="sxs-lookup"><span data-stu-id="3e908-178">Operating System</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-179">在由 MBAM 管理的用戶端電腦上找到的作業系統類型。</span><span class="sxs-lookup"><span data-stu-id="3e908-179">Operating system type found on the client computer that is managed by MBAM.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3e908-180">合規性狀態</span><span class="sxs-lookup"><span data-stu-id="3e908-180">Compliance Status</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-181">由 MBAM 管理之電腦的整體合規性狀態。</span><span class="sxs-lookup"><span data-stu-id="3e908-181">Overall compliance status of the computer that is managed by MBAM.</span></span> <span data-ttu-id="3e908-182">有效的狀態是相容且不相容。</span><span class="sxs-lookup"><span data-stu-id="3e908-182">Valid states are Compliant and Noncompliant.</span></span></p>
<p><span data-ttu-id="3e908-183">請注意，每個磁片磁碟機的相容性狀態（請參閱下表）可能表示不同的合規性狀態。</span><span class="sxs-lookup"><span data-stu-id="3e908-183">Notice that the compliance status per drive (see the following table) may indicate different compliance states.</span></span> <span data-ttu-id="3e908-184">不過，這個欄位會根據指定的原則代表符合性狀態。</span><span class="sxs-lookup"><span data-stu-id="3e908-184">However, this field represents that compliance state, according to the specified policy.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3e908-185">原則密碼強度</span><span class="sxs-lookup"><span data-stu-id="3e908-185">Policy Cipher Strength</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-186">系統管理員在 MBAM 原則規格期間選取的密碼強度（例如，使用擴散器的128位）。</span><span class="sxs-lookup"><span data-stu-id="3e908-186">Cipher strength selected by the administrator during MBAM policy specification (for example, 128-bit with diffuser).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3e908-187">原則作業系統磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="3e908-187">Policy Operating System Drive</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-188">表示作業系統是否需要加密，並顯示適當的保護器類型。</span><span class="sxs-lookup"><span data-stu-id="3e908-188">Indicates if encryption is required for the operating system and shows the appropriate protector type.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3e908-189">原則-固定資料磁碟機</span><span class="sxs-lookup"><span data-stu-id="3e908-189">Policy-Fixed Data Drive</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-190">表示固定資料磁碟機是否需要加密。</span><span class="sxs-lookup"><span data-stu-id="3e908-190">Indicates if encryption is required for the fixed data drive.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3e908-191">策略移除資料磁碟機</span><span class="sxs-lookup"><span data-stu-id="3e908-191">Policy Removable Data Drive</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-192">表示是否需要對移除磁片磁碟機進行加密。</span><span class="sxs-lookup"><span data-stu-id="3e908-192">Indicates if encryption is required for the removable drive.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3e908-193">裝置使用者</span><span class="sxs-lookup"><span data-stu-id="3e908-193">Device Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-194">由 MBAM 管理的電腦上的已知使用者。</span><span class="sxs-lookup"><span data-stu-id="3e908-194">Known users on the computer that is managed by MBAM.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3e908-195">免除</span><span class="sxs-lookup"><span data-stu-id="3e908-195">Exemption</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-196">指出此電腦是否不受 BitLocker 原則免除的狀態。</span><span class="sxs-lookup"><span data-stu-id="3e908-196">Status that indicates whether this computer is exempt from the BitLocker policy.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3e908-197">製造商</span><span class="sxs-lookup"><span data-stu-id="3e908-197">Manufacturer</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-198">電腦製造商名稱，如電腦 BIOS 所示。</span><span class="sxs-lookup"><span data-stu-id="3e908-198">Computer manufacturer name, as it appears in the computer BIOS.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3e908-199">型號</span><span class="sxs-lookup"><span data-stu-id="3e908-199">Model</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-200">電腦製造商模型名稱，如電腦 BIOS 所示。</span><span class="sxs-lookup"><span data-stu-id="3e908-200">Computer manufacturer model name, as it appears in the computer BIOS.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3e908-201">合規性狀態詳細資料</span><span class="sxs-lookup"><span data-stu-id="3e908-201">Compliance Status Details</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-202">根據指定原則，瞭解電腦合規性狀態的錯誤與狀態訊息。</span><span class="sxs-lookup"><span data-stu-id="3e908-202">Error and status messages about the compliance state of the computer, in accordance with the specified policy.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3e908-203">最後一個連絡人</span><span class="sxs-lookup"><span data-stu-id="3e908-203">Last Contact</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-204">電腦上次取得伺服器以報告合規性狀態的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="3e908-204">Date and time that the computer last contacted the server to report compliance status.</span></span> <span data-ttu-id="3e908-205">連絡人頻率是可設定的。</span><span class="sxs-lookup"><span data-stu-id="3e908-205">The contact frequency is configurable.</span></span> <span data-ttu-id="3e908-206">如需詳細資訊，請參閱 MBAM 群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="3e908-206">For more information, see the MBAM Group Policy settings.</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="3e908-207">電腦合規性報告磁片磁碟機欄位</span><span class="sxs-lookup"><span data-stu-id="3e908-207">Computer Compliance Report Drive Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3e908-208">欄名稱</span><span class="sxs-lookup"><span data-stu-id="3e908-208">Column Name</span></span></th>
<th align="left"><span data-ttu-id="3e908-209">描述</span><span class="sxs-lookup"><span data-stu-id="3e908-209">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3e908-210">磁片磁碟機盤符</span><span class="sxs-lookup"><span data-stu-id="3e908-210">Drive Letter</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-211">使用者指派給特定磁片磁碟機的電腦磁碟機盤符。</span><span class="sxs-lookup"><span data-stu-id="3e908-211">Computer drive letter that was assigned to the particular drive by the user.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3e908-212">磁片磁碟機類型</span><span class="sxs-lookup"><span data-stu-id="3e908-212">Drive Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-213">磁片磁碟機類型。</span><span class="sxs-lookup"><span data-stu-id="3e908-213">Type of drive.</span></span> <span data-ttu-id="3e908-214">有效值為作業系統磁片磁碟機及固定資料磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="3e908-214">Valid values are Operating System Drive and Fixed Data Drive.</span></span> <span data-ttu-id="3e908-215">這些是物理磁片磁碟機，而不是邏輯磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="3e908-215">These are physical drives rather than logical volumes.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3e908-216">密碼強度</span><span class="sxs-lookup"><span data-stu-id="3e908-216">Cipher Strength</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-217">管理員在 MBAM 原則規格期間選取的密碼強度。</span><span class="sxs-lookup"><span data-stu-id="3e908-217">Cipher strength selected by the administrator during MBAM policy specification.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3e908-218">保護器類型</span><span class="sxs-lookup"><span data-stu-id="3e908-218">Protector Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-219">透過用來加密作業系統或固定資料量的群組原則設定所選取的保護者類型。</span><span class="sxs-lookup"><span data-stu-id="3e908-219">Type of protector selected through the Group Policy setting used to encrypt an operating system or fixed data volume.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3e908-220">保護器狀態</span><span class="sxs-lookup"><span data-stu-id="3e908-220">Protector State</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-221">指示由 MBAM 管理的電腦已啟用原則中指定的保護器類型。</span><span class="sxs-lookup"><span data-stu-id="3e908-221">Indicates that the computer being managed by MBAM has enabled the protector type that is specified in the policy.</span></span> <span data-ttu-id="3e908-222">[有效] 狀態為 [開啟] 或 [關閉]。</span><span class="sxs-lookup"><span data-stu-id="3e908-222">The valid states are ON or OFF.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3e908-223">加密狀態</span><span class="sxs-lookup"><span data-stu-id="3e908-223">Encryption State</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-224">磁片磁碟機的加密狀態。</span><span class="sxs-lookup"><span data-stu-id="3e908-224">Encryption state of the drive.</span></span> <span data-ttu-id="3e908-225">有效的狀態為 [已加密]、[未加密] 和 [加密]。</span><span class="sxs-lookup"><span data-stu-id="3e908-225">Valid states are Encrypted, Not Encrypted, and Encrypting.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3e908-226">合規性狀態</span><span class="sxs-lookup"><span data-stu-id="3e908-226">Compliance Status</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-227">指出磁片磁碟機是否符合原則的狀態。</span><span class="sxs-lookup"><span data-stu-id="3e908-227">State that indicates whether the drive is in accordance with the policy.</span></span> <span data-ttu-id="3e908-228">狀態為不相容且合規性。</span><span class="sxs-lookup"><span data-stu-id="3e908-228">States are Noncompliant and Compliant.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3e908-229">合規性狀態詳細資料</span><span class="sxs-lookup"><span data-stu-id="3e908-229">Compliance Status Details</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-230">根據指定原則，電腦合規性狀態的錯誤與狀態訊息。</span><span class="sxs-lookup"><span data-stu-id="3e908-230">Error and status messages of the compliance state of the computer, according to the specified policy.</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-recovery"></a><span data-ttu-id="3e908-231">復原審核報告</span><span class="sxs-lookup"><span data-stu-id="3e908-231">Recovery Audit Report</span></span>

<span data-ttu-id="3e908-232">使用此報告類型來審核已要求存取 BitLocker 復原金鑰的使用者。</span><span class="sxs-lookup"><span data-stu-id="3e908-232">Use this report type to audit users who have requested access to BitLocker recovery keys.</span></span> <span data-ttu-id="3e908-233">報告根據所需的篩選準則提供數個篩選。</span><span class="sxs-lookup"><span data-stu-id="3e908-233">The report offers several filters based on the desired filtering criteria.</span></span> <span data-ttu-id="3e908-234">您可以篩選特定類型的使用者（技術支援人員或使用者）、是否已失敗或已成功、要求的特定金鑰類型，以及發生檢索的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="3e908-234">You can filter on a specific type of user (a Help Desk user or an end user), whether the request failed or was successful, the specific type of key requested, and a date range during which the retrieval occurred.</span></span>

**<span data-ttu-id="3e908-235">復原審核報告欄位</span><span class="sxs-lookup"><span data-stu-id="3e908-235">Recovery Audit Report Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3e908-236">欄名稱</span><span class="sxs-lookup"><span data-stu-id="3e908-236">Column Name</span></span></th>
<th align="left"><span data-ttu-id="3e908-237">描述</span><span class="sxs-lookup"><span data-stu-id="3e908-237">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3e908-238">要求日期和時間</span><span class="sxs-lookup"><span data-stu-id="3e908-238">Request Date and Time</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-239">由最終使用者或技術支援人員使用者所做的金鑰檢索要求的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="3e908-239">Date and time that a key retrieval request was made by an end user or Help Desk user.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3e908-240">審核要求來源</span><span class="sxs-lookup"><span data-stu-id="3e908-240">Audit Request Source</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-241">啟動要求的網站。</span><span class="sxs-lookup"><span data-stu-id="3e908-241">The site from which the request was initiated.</span></span> <span data-ttu-id="3e908-242">這個專案會有兩個值中的一個： <strong> 自助服務入口網站 </strong> 或 <strong> 支援人員 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="3e908-242">This entry will have one of two values: <strong>Self-Service Portal</strong> or <strong>Helpdesk</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3e908-243">要求狀態</span><span class="sxs-lookup"><span data-stu-id="3e908-243">Request Status</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-244">要求的狀態。</span><span class="sxs-lookup"><span data-stu-id="3e908-244">Status of the request.</span></span> <span data-ttu-id="3e908-245">有效狀態為 [成功] （已檢索到金鑰），或失敗（未檢索到金鑰）。</span><span class="sxs-lookup"><span data-stu-id="3e908-245">Valid statuses are Successful (the key was retrieved), or Failed (the key was not retrieved).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3e908-246">支援人員的使用者</span><span class="sxs-lookup"><span data-stu-id="3e908-246">Helpdesk User</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-247">已開始取得金鑰檢索要求的技術支援使用者。</span><span class="sxs-lookup"><span data-stu-id="3e908-247">Help Desk user who initiated the request for key retrieval.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="3e908-248">注意</span><span class="sxs-lookup"><span data-stu-id="3e908-248">Note</span></span></strong><br/><p><span data-ttu-id="3e908-249">如果 [高級支援人員] 使用者在不指定使用者的情況下就能修復金鑰，則 [ <strong> 使用者] </strong> 欄位會是空白的。</span><span class="sxs-lookup"><span data-stu-id="3e908-249">If an Advanced Helpdesk User recovers the key without specifying the end user, the <strong>End User</strong> field will be blank.</span></span> <span data-ttu-id="3e908-250">標準的支援人員使用者必須指定最終使用者，該使用者就會出現在此欄位中。</span><span class="sxs-lookup"><span data-stu-id="3e908-250">A standard Helpdesk User must specify the end user, and that user will appear in this field.</span></span></p>
<p><span data-ttu-id="3e908-251">透過自助入口網站的復原將會在此欄位和 [使用者] 欄位中列出要求的最終使用者 <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="3e908-251">A recovery via the Self-Service Portal will list the requesting end user both in this field and in the <strong>End User</strong> field.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3e908-252">使用者</span><span class="sxs-lookup"><span data-stu-id="3e908-252">End User</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-253">已啟動金鑰取回要求的使用者。</span><span class="sxs-lookup"><span data-stu-id="3e908-253">End user who initiated the request for key retrieval.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3e908-254">電腦</span><span class="sxs-lookup"><span data-stu-id="3e908-254">Computer</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-255">已復原電腦的電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="3e908-255">Computer name of the computer that was recovered.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3e908-256">金鑰類型</span><span class="sxs-lookup"><span data-stu-id="3e908-256">Key Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-257">技術支援人員使用者或使用者所要求的金鑰類型。</span><span class="sxs-lookup"><span data-stu-id="3e908-257">Type of key that was requested by the Help Desk user or the end user.</span></span> <span data-ttu-id="3e908-258">MBAM 收集的三種金鑰類型如下：</span><span class="sxs-lookup"><span data-stu-id="3e908-258">The three types of keys that MBAM collects are:</span></span></p>
<ul>
<li><p><span data-ttu-id="3e908-259">復原金鑰密碼（用來在復原模式中復原電腦）</span><span class="sxs-lookup"><span data-stu-id="3e908-259">Recovery Key Password (used to recover a computer in recovery mode)</span></span></p></li>
<li><p><span data-ttu-id="3e908-260">復原金鑰識別碼（用來代表另一個使用者在復原模式中復原電腦）</span><span class="sxs-lookup"><span data-stu-id="3e908-260">Recovery Key ID (used to recover a computer in recovery mode on behalf of another user)</span></span></p></li>
<li><p><span data-ttu-id="3e908-261">TPM 密碼雜湊（用於復原已鎖定的 TPM 的電腦）</span><span class="sxs-lookup"><span data-stu-id="3e908-261">TPM Password Hash (used to recover a computer with a locked TPM)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3e908-262">原因描述</span><span class="sxs-lookup"><span data-stu-id="3e908-262">Reason Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="3e908-263">說明： [技術支援人員] 使用者或 [最終使用者] 要求指定的金鑰類型。</span><span class="sxs-lookup"><span data-stu-id="3e908-263">Reason the specified key type was requested by the Help Desk user or the end user.</span></span> <span data-ttu-id="3e908-264">原因是在 [磁片磁碟機復原] 和 [管理及監視] 網站的 TPM 功能中指定。</span><span class="sxs-lookup"><span data-stu-id="3e908-264">The reasons are specified in the Drive Recovery and Manage TPM features of the Administration and Monitoring Website.</span></span> <span data-ttu-id="3e908-265">有效的專案是使用者輸入的文字，或是下列其中一個原因代碼：</span><span class="sxs-lookup"><span data-stu-id="3e908-265">The valid entries are user-entered text or one of the following reason codes:</span></span></p>
<ul>
<li><p><span data-ttu-id="3e908-266">作業系統啟動順序已變更</span><span class="sxs-lookup"><span data-stu-id="3e908-266">Operating System Boot Order changed</span></span></p></li>
<li><p><span data-ttu-id="3e908-267">BIOS 已變更</span><span class="sxs-lookup"><span data-stu-id="3e908-267">BIOS Changed</span></span></p></li>
<li><p><span data-ttu-id="3e908-268">已變更作業系統檔案</span><span class="sxs-lookup"><span data-stu-id="3e908-268">Operating System files changed</span></span></p></li>
<li><p><span data-ttu-id="3e908-269">遺失的啟動金鑰</span><span class="sxs-lookup"><span data-stu-id="3e908-269">Lost Startup key</span></span></p></li>
<li><p><span data-ttu-id="3e908-270">遺失的 PIN</span><span class="sxs-lookup"><span data-stu-id="3e908-270">Lost PIN</span></span></p></li>
<li><p><span data-ttu-id="3e908-271">TPM 重設</span><span class="sxs-lookup"><span data-stu-id="3e908-271">TPM Reset</span></span></p></li>
<li><p><span data-ttu-id="3e908-272">遺失密碼</span><span class="sxs-lookup"><span data-stu-id="3e908-272">Lost Passphrase</span></span></p></li>
<li><p><span data-ttu-id="3e908-273">遺失的智慧卡</span><span class="sxs-lookup"><span data-stu-id="3e908-273">Lost Smartcard</span></span></p></li>
<li><p><span data-ttu-id="3e908-274">重設 PIN 鎖定</span><span class="sxs-lookup"><span data-stu-id="3e908-274">Reset PIN lockout</span></span></p></li>
<li><p><span data-ttu-id="3e908-275">開啟 TPM</span><span class="sxs-lookup"><span data-stu-id="3e908-275">Turn on TPM</span></span></p></li>
<li><p><span data-ttu-id="3e908-276">關閉 TPM</span><span class="sxs-lookup"><span data-stu-id="3e908-276">Turn off TPM</span></span></p></li>
<li><p><span data-ttu-id="3e908-277">變更 TPM 密碼</span><span class="sxs-lookup"><span data-stu-id="3e908-277">Change TPM password</span></span></p></li>
<li><p><span data-ttu-id="3e908-278">清除 TPM</span><span class="sxs-lookup"><span data-stu-id="3e908-278">Clear TPM</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="3e908-279">注意</span><span class="sxs-lookup"><span data-stu-id="3e908-279">Note</span></span>**  
<span data-ttu-id="3e908-280">您可以按一下 [**報表**] 功能表列上的 [**匯出**] 按鈕，將報告結果儲存至檔案。</span><span class="sxs-lookup"><span data-stu-id="3e908-280">Report results can be saved to a file by clicking the **Export** button on the **Reports** menu bar.</span></span>




## <span data-ttu-id="3e908-281">相關主題</span><span class="sxs-lookup"><span data-stu-id="3e908-281">Related topics</span></span>


[<span data-ttu-id="3e908-282">使用 MBAM 2.5 監視與報告 BitLocker 符合性</span><span class="sxs-lookup"><span data-stu-id="3e908-282">Monitoring and Reporting BitLocker Compliance with MBAM 2.5</span></span>](monitoring-and-reporting-bitlocker-compliance-with-mbam-25.md)

[<span data-ttu-id="3e908-283">產生 MBAM 2.5 獨立報告</span><span class="sxs-lookup"><span data-stu-id="3e908-283">Generating MBAM 2.5 Stand-alone Reports</span></span>](generating-mbam-25-stand-alone-reports.md)



## <span data-ttu-id="3e908-284">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="3e908-284">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="3e908-285">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="3e908-285">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="3e908-286">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="3e908-286">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





