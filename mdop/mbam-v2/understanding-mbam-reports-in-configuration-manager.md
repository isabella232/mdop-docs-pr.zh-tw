---
title: 瞭解 Configuration Manager 中的 MBAM 報告
description: 瞭解 Configuration Manager 中的 MBAM 報告
author: dansimp
ms.assetid: b2582190-c9de-4e64-bd5a-f31ac1916f53
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 995d628cafd03c8bdd209e467c9d22169b7e03c3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810185"
---
# <span data-ttu-id="4876b-103">瞭解 Configuration Manager 中的 MBAM 報告</span><span class="sxs-lookup"><span data-stu-id="4876b-103">Understanding MBAM Reports in Configuration Manager</span></span>


<span data-ttu-id="4876b-104">當 Microsoft BitLocker 管理與監控（MBAM）與 Configuration Manager 整合拓朴一起安裝時，硬體合規性和報告功能會移至 Configuration Manager 基礎結構，並移至 MBAM。</span><span class="sxs-lookup"><span data-stu-id="4876b-104">When Microsoft BitLocker Administration and Monitoring (MBAM) is installed with the Configuration Manager Integrated topology, the hardware compliance and reporting features are moved into the Configuration Manager infrastructure and out of MBAM.</span></span> <span data-ttu-id="4876b-105">當您使用 Configuration Manager 拓撲結構時，您會從 Configuration Manager （而不是從 MBAM）執行報表，而不是從 [恢復] 審核報告（您可以使用 [管理] 和 [監視] 網站繼續存取）除外。</span><span class="sxs-lookup"><span data-stu-id="4876b-105">When you use the Configuration Manager topology, you run reports from Configuration Manager rather than from MBAM, except for the Recovery Audit Report, which you continue to access by using the Administration and Monitoring Website.</span></span>

<span data-ttu-id="4876b-106">Configuration Manager 整合拓朴的報告會顯示企業及 MBAM 管理的個別電腦和裝置的 BitLocker 合規性。</span><span class="sxs-lookup"><span data-stu-id="4876b-106">The reports for the Configuration Manager Integrated topology show BitLocker compliance for the enterprise and for individual computers and devices that MBAM manages.</span></span> <span data-ttu-id="4876b-107">報告提供表格式資訊與圖表，並可讓您篩選報表，以從不同的觀點查看資料。</span><span class="sxs-lookup"><span data-stu-id="4876b-107">The reports provide both tabular information and charts, and enable you to filter reports to view data from different perspectives.</span></span>

<span data-ttu-id="4876b-108">本主題中的資訊說明您從 Configuration Manager 執行的 MBAM 報告。</span><span class="sxs-lookup"><span data-stu-id="4876b-108">The information in this topic describes the MBAM reports that you run from Configuration Manager.</span></span> <span data-ttu-id="4876b-109">如需獨立拓朴 MBAM 報告的相關資訊，請參閱[瞭解 MBAM 報告](understanding-mbam-reports-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="4876b-109">For information about MBAM reports for the Stand-alone topology, see [Understanding MBAM Reports](understanding-mbam-reports-mbam-2.md).</span></span>

## <span data-ttu-id="4876b-110">在 Configuration Manager 中存取報表</span><span class="sxs-lookup"><span data-stu-id="4876b-110">Accessing Reports in Configuration Manager</span></span>


<span data-ttu-id="4876b-111">若要存取 Configuration Manager 中的報告功能，請開啟**Configuration manager 主控台**。</span><span class="sxs-lookup"><span data-stu-id="4876b-111">To access the Reports feature in Configuration Manager, open the **Configuration Manager console**.</span></span> <span data-ttu-id="4876b-112">若要顯示可用報表的清單：</span><span class="sxs-lookup"><span data-stu-id="4876b-112">To display the list of available reports:</span></span>

-   <span data-ttu-id="4876b-113">在 Configuration Manager 2007 中，展開 [**電腦管理**] 節點，然後展開 [**報告**] 節點。</span><span class="sxs-lookup"><span data-stu-id="4876b-113">In Configuration Manager 2007, expand the **Computer Management** node, and then expand the **Reporting** node.</span></span>

-   <span data-ttu-id="4876b-114">在 SystemCenter2012 ConfigurationManager 的 [監視] 工作區中，展開 [概覽] 底下的 [**報告**] 節點，然後按一下 **[\*\*\*\*報告**]。</span><span class="sxs-lookup"><span data-stu-id="4876b-114">In SystemCenter2012 ConfigurationManager, in the Monitoring workspace under **Overview**, expand the **Reporting** node and then click **Reports**.</span></span>

### <span data-ttu-id="4876b-115">BitLocker Enterprise 合規性儀表板</span><span class="sxs-lookup"><span data-stu-id="4876b-115">BitLocker Enterprise Compliance Dashboard</span></span>

<span data-ttu-id="4876b-116">BitLocker Enterprise 合規性儀表板提供下列圖表，在整個企業中顯示 BitLocker 合規性狀態：</span><span class="sxs-lookup"><span data-stu-id="4876b-116">The BitLocker Enterprise Compliance Dashboard provides the following graphs, which show BitLocker compliance status across the enterprise:</span></span>

-   <span data-ttu-id="4876b-117">合規性狀態發佈</span><span class="sxs-lookup"><span data-stu-id="4876b-117">Compliance Status Distribution</span></span>

-   <span data-ttu-id="4876b-118">不相容的錯誤發佈</span><span class="sxs-lookup"><span data-stu-id="4876b-118">Non Compliant Errors Distribution</span></span>

-   <span data-ttu-id="4876b-119">依磁片磁碟機類型進行合規性狀態發佈</span><span class="sxs-lookup"><span data-stu-id="4876b-119">Compliance Status Distribution by Drive Type</span></span>

**<span data-ttu-id="4876b-120">合規性狀態發佈</span><span class="sxs-lookup"><span data-stu-id="4876b-120">Compliance Status Distribution</span></span>**

<span data-ttu-id="4876b-121">此圓形圖顯示企業內部的電腦合規性狀態，並顯示電腦的百分比，與所選集合中擁有該符合性狀態的電腦總數。</span><span class="sxs-lookup"><span data-stu-id="4876b-121">This pie chart shows computer compliance statuses within the enterprise, and shows the percentage of computers, compared to the total number of computers in the selected collection, that have that compliance status.</span></span> <span data-ttu-id="4876b-122">也會顯示每個狀態的實際電腦數。</span><span class="sxs-lookup"><span data-stu-id="4876b-122">The actual number of computers with each status is also shown.</span></span> <span data-ttu-id="4876b-123">圓形圖顯示下列合規性狀態：</span><span class="sxs-lookup"><span data-stu-id="4876b-123">The pie chart shows the following compliance statuses:</span></span>

-   <span data-ttu-id="4876b-124">達到</span><span class="sxs-lookup"><span data-stu-id="4876b-124">Compliant</span></span>

-   <span data-ttu-id="4876b-125">不符合</span><span class="sxs-lookup"><span data-stu-id="4876b-125">Non Compliant</span></span>

-   <span data-ttu-id="4876b-126">使用者豁免</span><span class="sxs-lookup"><span data-stu-id="4876b-126">User Exempt</span></span>

-   <span data-ttu-id="4876b-127">暫時使用者豁免</span><span class="sxs-lookup"><span data-stu-id="4876b-127">Temporary User Exempt</span></span>

-   <span data-ttu-id="4876b-128">未強制執行原則</span><span class="sxs-lookup"><span data-stu-id="4876b-128">Policy Not Enforced</span></span>

-   <span data-ttu-id="4876b-129">未知-已報告錯誤的電腦，或屬於集合一部分但未報告其合規性狀態的裝置，例如，如果它們已從組織中斷連線</span><span class="sxs-lookup"><span data-stu-id="4876b-129">Unknown -computers whose status was reported as an error, or devices that are part of the collection but have never reported their compliance status, for example, if they are disconnected from the organization</span></span>

**<span data-ttu-id="4876b-130">不相容的錯誤發佈</span><span class="sxs-lookup"><span data-stu-id="4876b-130">Non Compliant Errors Distribution</span></span>**

<span data-ttu-id="4876b-131">此圓形圖顯示企業中不符合 BitLocker 磁碟機加密原則的電腦類別，並顯示每個類別中的電腦數。</span><span class="sxs-lookup"><span data-stu-id="4876b-131">This pie chart shows the categories of computers in the enterprise that are not compliant with the BitLocker drive encryption policy, and shows the number of computers in each category.</span></span> <span data-ttu-id="4876b-132">每個類別百分比是從集合中不相容電腦的總數計算而來。</span><span class="sxs-lookup"><span data-stu-id="4876b-132">Each category percentage is calculated from the total number of non-compliant computers in the collection.</span></span>

-   <span data-ttu-id="4876b-133">使用者已延遲加密</span><span class="sxs-lookup"><span data-stu-id="4876b-133">User postponed encryption</span></span>

-   <span data-ttu-id="4876b-134">找不到相容的 TPM</span><span class="sxs-lookup"><span data-stu-id="4876b-134">Unable to find compatible TPM</span></span>

-   <span data-ttu-id="4876b-135">系統磁碟分割無法使用或太大</span><span class="sxs-lookup"><span data-stu-id="4876b-135">System Partition not available or large enough</span></span>

-   <span data-ttu-id="4876b-136">原則衝突</span><span class="sxs-lookup"><span data-stu-id="4876b-136">Policy conflict</span></span>

-   <span data-ttu-id="4876b-137">正在等待 TPM 自動預配</span><span class="sxs-lookup"><span data-stu-id="4876b-137">Waiting for TPM auto provisioning</span></span>

-   <span data-ttu-id="4876b-138">發生未知的錯誤</span><span class="sxs-lookup"><span data-stu-id="4876b-138">An unknown error has occurred</span></span>

-   <span data-ttu-id="4876b-139">無資訊-沒有安裝 MBAM 用戶端的電腦，或已安裝 MBAM 用戶端但尚未啟用的電腦，例如，服務無法運作</span><span class="sxs-lookup"><span data-stu-id="4876b-139">No information – computers that do not have the MBAM Client installed, or that have the MBAM Client installed but not activated, for example, the service is not working</span></span>

**<span data-ttu-id="4876b-140">依磁片磁碟機類型進行合規性狀態發佈</span><span class="sxs-lookup"><span data-stu-id="4876b-140">Compliance Status Distribution by Drive Type</span></span>**

<span data-ttu-id="4876b-141">此橫條圖顯示 [依磁片磁碟機類型列出目前的 BitLocker 合規性狀態]。</span><span class="sxs-lookup"><span data-stu-id="4876b-141">This bar chart shows the current BitLocker compliance status by drive type.</span></span> <span data-ttu-id="4876b-142">狀態為「符合性」和「不相容」。</span><span class="sxs-lookup"><span data-stu-id="4876b-142">The statuses are “Compliant” and “Non Compliant.”</span></span> <span data-ttu-id="4876b-143">會顯示 [固定資料磁碟機] 和 [作業系統磁片磁碟機] 的橫條圖。</span><span class="sxs-lookup"><span data-stu-id="4876b-143">Bars are shown for fixed data drives and operating system drives.</span></span> <span data-ttu-id="4876b-144">包括沒有固定資料磁碟機的電腦，而且只會顯示作業系統磁片磁碟機列中的值。</span><span class="sxs-lookup"><span data-stu-id="4876b-144">Computers that do not have a fixed data drive are included and show a value only in the Operating System Drive bar.</span></span> <span data-ttu-id="4876b-145">圖表不包括已從 BitLocker 磁碟機加密原則或 "無原則" 類別獲授權的使用者。</span><span class="sxs-lookup"><span data-stu-id="4876b-145">The chart does not include users who have been granted an exemption from the BitLocker drive encryption policy or the “No Policy” category.</span></span>

### <span data-ttu-id="4876b-146">BitLocker 企業合規性詳細資料包表</span><span class="sxs-lookup"><span data-stu-id="4876b-146">BitLocker Enterprise Compliance Details Report</span></span>

<span data-ttu-id="4876b-147">此報告會在您的企業中顯示針對以 BitLocker 為目標的電腦集合的整個 BitLocker 規範的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="4876b-147">This report shows information about the overall BitLocker compliance across your enterprise for the collection of computers that is targeted for BitLocker use.</span></span>

**<span data-ttu-id="4876b-148">BitLocker Enterprise 合規性詳細資料包表字段</span><span class="sxs-lookup"><span data-stu-id="4876b-148">BitLocker Enterprise Compliance Details Report Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4876b-149">欄名稱</span><span class="sxs-lookup"><span data-stu-id="4876b-149">Column Name</span></span></th>
<th align="left"><span data-ttu-id="4876b-150">描述</span><span class="sxs-lookup"><span data-stu-id="4876b-150">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4876b-151">受管理的電腦</span><span class="sxs-lookup"><span data-stu-id="4876b-151">Managed Computers</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-152">MBAM 管理的電腦數。</span><span class="sxs-lookup"><span data-stu-id="4876b-152">Number of computers that MBAM manages.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4876b-153">符合百分比</span><span class="sxs-lookup"><span data-stu-id="4876b-153">% Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-154">企業中合規性電腦的百分比。</span><span class="sxs-lookup"><span data-stu-id="4876b-154">Percentage of compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4876b-155">非相容性%</span><span class="sxs-lookup"><span data-stu-id="4876b-155">% Non-Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-156">企業中不相容的電腦百分比。</span><span class="sxs-lookup"><span data-stu-id="4876b-156">Percentage of non-compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4876b-157">% 的未知規範</span><span class="sxs-lookup"><span data-stu-id="4876b-157">% Unknown Compliance</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-158">合規性狀態未知的電腦百分比。</span><span class="sxs-lookup"><span data-stu-id="4876b-158">Percentage of computers whose compliance state is not known.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4876b-159">% 豁免</span><span class="sxs-lookup"><span data-stu-id="4876b-159">% Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-160">免除 BitLocker 加密需求的電腦所占的百分比。</span><span class="sxs-lookup"><span data-stu-id="4876b-160">Percentage of computers exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4876b-161">非豁免%</span><span class="sxs-lookup"><span data-stu-id="4876b-161">% Non-Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-162">免除 BitLocker 加密需求的電腦所占的百分比。</span><span class="sxs-lookup"><span data-stu-id="4876b-162">Percentage of computers exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4876b-163">達到</span><span class="sxs-lookup"><span data-stu-id="4876b-163">Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-164">企業中合規性電腦的百分比。</span><span class="sxs-lookup"><span data-stu-id="4876b-164">Percentage of compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4876b-165">不相容</span><span class="sxs-lookup"><span data-stu-id="4876b-165">Non-Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-166">企業中不相容的電腦百分比。</span><span class="sxs-lookup"><span data-stu-id="4876b-166">Percentage of non-compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4876b-167">未知的合規性</span><span class="sxs-lookup"><span data-stu-id="4876b-167">Unknown Compliance</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-168">合規性狀態未知的電腦百分比。</span><span class="sxs-lookup"><span data-stu-id="4876b-168">Percentage of computers whose compliance state is not known.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4876b-169">免除</span><span class="sxs-lookup"><span data-stu-id="4876b-169">Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-170">免除 BitLocker 加密需求的電腦總數。</span><span class="sxs-lookup"><span data-stu-id="4876b-170">Total computers that are exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4876b-171">非豁免</span><span class="sxs-lookup"><span data-stu-id="4876b-171">Non-Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-172">未免除 BitLocker 加密需求的電腦總數。</span><span class="sxs-lookup"><span data-stu-id="4876b-172">Total computers that are not exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="4876b-173">BitLocker Enterprise 合規性詳細資料包表-合規性狀態</span><span class="sxs-lookup"><span data-stu-id="4876b-173">BitLocker Enterprise Compliance Details Report - Compliance States</span></span>**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4876b-174">合規性狀態</span><span class="sxs-lookup"><span data-stu-id="4876b-174">Compliance Status</span></span></th>
<th align="left"><span data-ttu-id="4876b-175">免除</span><span class="sxs-lookup"><span data-stu-id="4876b-175">Exemption</span></span></th>
<th align="left"><span data-ttu-id="4876b-176">描述</span><span class="sxs-lookup"><span data-stu-id="4876b-176">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4876b-177">標準</span><span class="sxs-lookup"><span data-stu-id="4876b-177">Noncompliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-178">未免除</span><span class="sxs-lookup"><span data-stu-id="4876b-178">Not Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-179">根據指定的原則，電腦是不相容的。</span><span class="sxs-lookup"><span data-stu-id="4876b-179">The computer is noncompliant, according to the specified policy.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4876b-180">達到</span><span class="sxs-lookup"><span data-stu-id="4876b-180">Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-181">未免除</span><span class="sxs-lookup"><span data-stu-id="4876b-181">Not Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-182">根據指定的原則，電腦符合規範。</span><span class="sxs-lookup"><span data-stu-id="4876b-182">The computer is compliant in accordance with the specified policy.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="4876b-183">BitLocker Enterprise 相容性摘要報告</span><span class="sxs-lookup"><span data-stu-id="4876b-183">BitLocker Enterprise Compliance Summary Report</span></span>

<span data-ttu-id="4876b-184">您可以使用此報告類型來顯示整個企業的 BitLocker 合規性相關資訊，以及顯示針對 BitLocker 使用之電腦集合中的個別電腦的相容性。</span><span class="sxs-lookup"><span data-stu-id="4876b-184">Use this report type to show information about the overall BitLocker compliance across your enterprise and to show the compliance for individual computers that are in the collection of computers that is targeted for BitLocker use.</span></span>

**<span data-ttu-id="4876b-185">BitLocker Enterprise 合規性摘要報表欄位</span><span class="sxs-lookup"><span data-stu-id="4876b-185">BitLocker Enterprise Compliance Summary Report Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4876b-186">欄名稱</span><span class="sxs-lookup"><span data-stu-id="4876b-186">Column Name</span></span></th>
<th align="left"><span data-ttu-id="4876b-187">描述</span><span class="sxs-lookup"><span data-stu-id="4876b-187">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4876b-188">受管理的電腦</span><span class="sxs-lookup"><span data-stu-id="4876b-188">Managed Computers</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-189">MBAM 管理的電腦數。</span><span class="sxs-lookup"><span data-stu-id="4876b-189">Number of computers that MBAM manages.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4876b-190">符合百分比</span><span class="sxs-lookup"><span data-stu-id="4876b-190">% Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-191">企業中合規性電腦的百分比。</span><span class="sxs-lookup"><span data-stu-id="4876b-191">Percentage of compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4876b-192">非相容性%</span><span class="sxs-lookup"><span data-stu-id="4876b-192">% Non-Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-193">企業中不相容的電腦百分比。</span><span class="sxs-lookup"><span data-stu-id="4876b-193">Percentage of non-compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4876b-194">% 的未知規範</span><span class="sxs-lookup"><span data-stu-id="4876b-194">% Unknown Compliance</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-195">合規性狀態未知的電腦百分比。</span><span class="sxs-lookup"><span data-stu-id="4876b-195">Percentage of computers whose compliance state is not known.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4876b-196">% 豁免</span><span class="sxs-lookup"><span data-stu-id="4876b-196">% Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-197">免除 BitLocker 加密需求的電腦所占的百分比。</span><span class="sxs-lookup"><span data-stu-id="4876b-197">Percentage of computers exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4876b-198">非豁免%</span><span class="sxs-lookup"><span data-stu-id="4876b-198">% Non-Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-199">免除 BitLocker 加密需求的電腦所占的百分比。</span><span class="sxs-lookup"><span data-stu-id="4876b-199">Percentage of computers exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4876b-200">達到</span><span class="sxs-lookup"><span data-stu-id="4876b-200">Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-201">企業中合規性電腦的百分比。</span><span class="sxs-lookup"><span data-stu-id="4876b-201">Percentage of compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4876b-202">不相容</span><span class="sxs-lookup"><span data-stu-id="4876b-202">Non-Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-203">企業中不相容的電腦百分比。</span><span class="sxs-lookup"><span data-stu-id="4876b-203">Percentage of non-compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4876b-204">未知的合規性</span><span class="sxs-lookup"><span data-stu-id="4876b-204">Unknown Compliance</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-205">合規性狀態未知的電腦百分比。</span><span class="sxs-lookup"><span data-stu-id="4876b-205">Percentage of computers whose compliance state is not known.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4876b-206">免除</span><span class="sxs-lookup"><span data-stu-id="4876b-206">Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-207">免除 BitLocker 加密需求的電腦總數。</span><span class="sxs-lookup"><span data-stu-id="4876b-207">Total computers that are exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4876b-208">非豁免</span><span class="sxs-lookup"><span data-stu-id="4876b-208">Non-Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-209">未免除 BitLocker 加密需求的電腦總數。</span><span class="sxs-lookup"><span data-stu-id="4876b-209">Total computers that are not exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="4876b-210">BitLocker Enterprise 合規性摘要報告-電腦詳細資料</span><span class="sxs-lookup"><span data-stu-id="4876b-210">BitLocker Enterprise Compliance Summary Report - Computer Details</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4876b-211">欄名稱</span><span class="sxs-lookup"><span data-stu-id="4876b-211">Column Name</span></span></th>
<th align="left"><span data-ttu-id="4876b-212">描述</span><span class="sxs-lookup"><span data-stu-id="4876b-212">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4876b-213">電腦名稱稱</span><span class="sxs-lookup"><span data-stu-id="4876b-213">Computer Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-214">由 MBAM 管理的使用者指定 DNS 電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="4876b-214">User-specified DNS computer name that is being managed by MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4876b-215">網功能變數名稱稱</span><span class="sxs-lookup"><span data-stu-id="4876b-215">Domain Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-216">用戶端電腦駐留且由 MBAM 管理的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="4876b-216">Fully qualified domain name, where the client computer resides and is managed by MBAM.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4876b-217">合規性狀態</span><span class="sxs-lookup"><span data-stu-id="4876b-217">Compliance Status</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-218">由 MBAM 管理之電腦的整體合規性狀態。</span><span class="sxs-lookup"><span data-stu-id="4876b-218">Overall Compliance Status of the computer managed by MBAM.</span></span> <span data-ttu-id="4876b-219">有效的狀態是相容且不相容。</span><span class="sxs-lookup"><span data-stu-id="4876b-219">Valid states are Compliant and Noncompliant.</span></span> <span data-ttu-id="4876b-220">請注意，每個磁片磁碟機的相容性狀態（請參閱後面的資料表）可能表示不同的合規性狀態。</span><span class="sxs-lookup"><span data-stu-id="4876b-220">Notice that the compliance status per drive (see table that follows) may indicate different compliance states.</span></span> <span data-ttu-id="4876b-221">不過，這個欄位會根據指定的原則來代表符合性狀態。</span><span class="sxs-lookup"><span data-stu-id="4876b-221">However, this field represents that compliance state, in accordance with the policy specified.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4876b-222">免除</span><span class="sxs-lookup"><span data-stu-id="4876b-222">Exemption</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-223">此狀態表示使用者是否已免除或未免除 BitLocker 原則。</span><span class="sxs-lookup"><span data-stu-id="4876b-223">Status that indicates whether the user is exempt or non-exemption from the BitLocker policy.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4876b-224">裝置使用者</span><span class="sxs-lookup"><span data-stu-id="4876b-224">Device Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-225">裝置的使用者。</span><span class="sxs-lookup"><span data-stu-id="4876b-225">User of the device.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4876b-226">合規性狀態詳細資料</span><span class="sxs-lookup"><span data-stu-id="4876b-226">Compliance Status Details</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-227">根據指定原則，電腦符合性狀態的錯誤與狀態訊息。</span><span class="sxs-lookup"><span data-stu-id="4876b-227">Error and status messages of the compliance state of the computer in accordance to the policy specified.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4876b-228">最後一個連絡人</span><span class="sxs-lookup"><span data-stu-id="4876b-228">Last Contact</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-229">電腦上次取得伺服器以報告合規性狀態的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="4876b-229">Date and time that the computer last contacted the server to report compliance status.</span></span> <span data-ttu-id="4876b-230">連絡人頻率可設定（請參閱 MBAM 原則設定）。</span><span class="sxs-lookup"><span data-stu-id="4876b-230">The contact frequency is configurable (see MBAM policy settings).</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="4876b-231">BitLocker 電腦合規性報告</span><span class="sxs-lookup"><span data-stu-id="4876b-231">BitLocker Computer Compliance Report</span></span>

<span data-ttu-id="4876b-232">使用此報告類型可收集電腦專用的資訊。</span><span class="sxs-lookup"><span data-stu-id="4876b-232">Use this report type to collect information that is specific to a computer.</span></span> <span data-ttu-id="4876b-233">電腦合規性報告提供電腦上每個磁片磁碟機（作業系統及固定資料磁碟機）的詳細加密資訊，以及針對電腦上的每個磁片磁碟機類型所套用的原則的指示。</span><span class="sxs-lookup"><span data-stu-id="4876b-233">The Computer Compliance Report provides detailed encryption information about each drive (Operating System and Fixed data drives) on a computer, and also an indication of the policy that is applied to each drive type on the computer.</span></span> <span data-ttu-id="4876b-234">若要查看每個磁片磁碟機的詳細資料，請展開 [電腦名稱稱] 專案。</span><span class="sxs-lookup"><span data-stu-id="4876b-234">To view the details of each drive, expand the Computer Name entry.</span></span>

<span data-ttu-id="4876b-235">**記事** 報告中不會顯示 [可移動資料量] 加密狀態。</span><span class="sxs-lookup"><span data-stu-id="4876b-235">**Note** Removable Data Volume encryption status is not shown in the report.</span></span>

 

**<span data-ttu-id="4876b-236">BitLocker 電腦合規性報告–電腦詳細資料欄位</span><span class="sxs-lookup"><span data-stu-id="4876b-236">BitLocker Computer Compliance Report – Computer Details Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4876b-237">欄名稱</span><span class="sxs-lookup"><span data-stu-id="4876b-237">Column Name</span></span></th>
<th align="left"><span data-ttu-id="4876b-238">描述</span><span class="sxs-lookup"><span data-stu-id="4876b-238">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4876b-239">電腦名稱稱</span><span class="sxs-lookup"><span data-stu-id="4876b-239">Computer Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-240">由 MBAM 管理的使用者指定 DNS 電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="4876b-240">User-specified DNS computer name that is being managed by MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4876b-241">網功能變數名稱稱</span><span class="sxs-lookup"><span data-stu-id="4876b-241">Domain Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-242">用戶端電腦駐留且由 MBAM 管理的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="4876b-242">Fully qualified domain name, where the client computer resides and is managed by MBAM.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4876b-243">電腦類型</span><span class="sxs-lookup"><span data-stu-id="4876b-243">Computer Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-244">電腦類型。</span><span class="sxs-lookup"><span data-stu-id="4876b-244">Type of computer.</span></span> <span data-ttu-id="4876b-245">有效類型為非便攜且可移植。</span><span class="sxs-lookup"><span data-stu-id="4876b-245">Valid types are non-Portable and Portable.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4876b-246">作業系統</span><span class="sxs-lookup"><span data-stu-id="4876b-246">Operating System</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-247">在 MBAM managed 用戶端電腦上找到的作業系統類型。</span><span class="sxs-lookup"><span data-stu-id="4876b-247">Operating System type found on the MBAM managed client computer.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4876b-248">整體合規性</span><span class="sxs-lookup"><span data-stu-id="4876b-248">Overall Compliance</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-249">由 MBAM 管理之電腦的整體合規性狀態。</span><span class="sxs-lookup"><span data-stu-id="4876b-249">Overall Compliance Status of the computer managed by MBAM.</span></span> <span data-ttu-id="4876b-250">有效的狀態是相容且不相容。</span><span class="sxs-lookup"><span data-stu-id="4876b-250">Valid states are Compliant and Noncompliant.</span></span> <span data-ttu-id="4876b-251">請注意，每個磁片磁碟機的相容性狀態（請參閱後面的資料表）可能表示不同的合規性狀態。</span><span class="sxs-lookup"><span data-stu-id="4876b-251">Notice that the compliance status per drive (see table that follows) may indicate different compliance states.</span></span> <span data-ttu-id="4876b-252">不過，這個欄位會根據指定的原則來代表符合性狀態。</span><span class="sxs-lookup"><span data-stu-id="4876b-252">However, this field represents that compliance state, in accordance with the policy specified.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4876b-253">作業系統合規性</span><span class="sxs-lookup"><span data-stu-id="4876b-253">Operating System Compliance</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-254">由 MBAM 管理之作業系統的合規性狀態。</span><span class="sxs-lookup"><span data-stu-id="4876b-254">Compliance status of the operating system that is managed by MBAM.</span></span> <span data-ttu-id="4876b-255">有效的狀態是相容且不相容。</span><span class="sxs-lookup"><span data-stu-id="4876b-255">Valid states are Compliant and Noncompliant.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4876b-256">固定資料磁碟機合規性</span><span class="sxs-lookup"><span data-stu-id="4876b-256">Fixed Data Drive Compliance</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-257">由 MBAM 管理的固定資料磁碟機的合規性狀態。</span><span class="sxs-lookup"><span data-stu-id="4876b-257">Compliance status of the Fixed Data Drive that is managed by MBAM.</span></span> <span data-ttu-id="4876b-258">有效的狀態是相容且不相容。</span><span class="sxs-lookup"><span data-stu-id="4876b-258">Valid states are Compliant and Noncompliant.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4876b-259">上次更新日期</span><span class="sxs-lookup"><span data-stu-id="4876b-259">Last Update Date</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-260">電腦上次取得伺服器以報告合規性狀態的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="4876b-260">Date and time that the computer last contacted the server to report compliance status.</span></span> <span data-ttu-id="4876b-261">連絡人頻率可設定（請參閱 MBAM 原則設定）。</span><span class="sxs-lookup"><span data-stu-id="4876b-261">The contact frequency is configurable (see MBAM policy settings).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4876b-262">免除</span><span class="sxs-lookup"><span data-stu-id="4876b-262">Exemption</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-263">此狀態表示使用者是否已免除或未免除 BitLocker 原則。</span><span class="sxs-lookup"><span data-stu-id="4876b-263">Status that indicates whether the user is exempt or non-exemption from the BitLocker policy.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4876b-264">免除的使用者</span><span class="sxs-lookup"><span data-stu-id="4876b-264">Exempted User</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-265">從 BitLocker 原則免除的使用者。</span><span class="sxs-lookup"><span data-stu-id="4876b-265">User who is exempt from the BitLocker policy.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4876b-266">免除日期</span><span class="sxs-lookup"><span data-stu-id="4876b-266">Exemption Date</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-267">授與免除的日期。</span><span class="sxs-lookup"><span data-stu-id="4876b-267">Date on which the exemption was granted.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4876b-268">合規性狀態詳細資料</span><span class="sxs-lookup"><span data-stu-id="4876b-268">Compliance Status Details</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-269">根據指定原則，電腦符合性狀態的錯誤與狀態訊息。</span><span class="sxs-lookup"><span data-stu-id="4876b-269">Error and status messages of the compliance state of the computer in accordance to the policy specified.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4876b-270">原則密碼強度</span><span class="sxs-lookup"><span data-stu-id="4876b-270">Policy Cipher Strength</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-271">管理員在 MBAM 原則規格期間選取的密碼強度。</span><span class="sxs-lookup"><span data-stu-id="4876b-271">Cipher Strength selected by the Administrator during MBAM policy specification.</span></span> <span data-ttu-id="4876b-272">（例如，使用擴散器的128位）。</span><span class="sxs-lookup"><span data-stu-id="4876b-272">(for example, 128-bit with Diffuser).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4876b-273">原則：作業系統磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="4876b-273">Policy: Operating System Drive</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-274">表示 O/S 和適當的保護器類型是否需要加密。</span><span class="sxs-lookup"><span data-stu-id="4876b-274">Indicates if encryption is required for the O/S and the appropriate protector type.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4876b-275">原則：固定資料磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="4876b-275">Policy:Fixed Data Drive</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-276">表示固定磁碟機是否需要加密。</span><span class="sxs-lookup"><span data-stu-id="4876b-276">Indicates if encryption is required for the Fixed Drive.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4876b-277">製造商</span><span class="sxs-lookup"><span data-stu-id="4876b-277">Manufacturer</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-278">電腦製造商出現在電腦 BIOS 中的名稱。</span><span class="sxs-lookup"><span data-stu-id="4876b-278">Computer manufacturer name as it appears in the computer BIOS.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4876b-279">型號</span><span class="sxs-lookup"><span data-stu-id="4876b-279">Model</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-280">電腦製造商模型名稱，如電腦 BIOS 中所示。</span><span class="sxs-lookup"><span data-stu-id="4876b-280">Computer manufacturer model name as it appears in the computer BIOS.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4876b-281">裝置使用者</span><span class="sxs-lookup"><span data-stu-id="4876b-281">Device Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-282">由 MBAM 管理的電腦上的已知使用者。</span><span class="sxs-lookup"><span data-stu-id="4876b-282">Known users on the computer that is being managed by MBAM.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="4876b-283">BitLocker 電腦合規性報告–電腦卷欄位</span><span class="sxs-lookup"><span data-stu-id="4876b-283">BitLocker Computer Compliance Report – Computer Volume Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4876b-284">欄名稱</span><span class="sxs-lookup"><span data-stu-id="4876b-284">Column Name</span></span></th>
<th align="left"><span data-ttu-id="4876b-285">描述</span><span class="sxs-lookup"><span data-stu-id="4876b-285">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4876b-286">磁片磁碟機盤符</span><span class="sxs-lookup"><span data-stu-id="4876b-286">Drive Letter</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-287">使用者指派給特定磁片磁碟機的電腦磁碟機盤符。</span><span class="sxs-lookup"><span data-stu-id="4876b-287">Computer drive letter that was assigned to the particular drive by the user.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4876b-288">磁片磁碟機類型</span><span class="sxs-lookup"><span data-stu-id="4876b-288">Drive Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-289">磁片磁碟機類型。</span><span class="sxs-lookup"><span data-stu-id="4876b-289">Type of drive.</span></span> <span data-ttu-id="4876b-290">有效值為作業系統磁片磁碟機及固定資料磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="4876b-290">Valid values are Operating System Drive and Fixed Data Drive.</span></span> <span data-ttu-id="4876b-291">這些是物理磁片磁碟機，而不是邏輯磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="4876b-291">These are physical drives rather than logical volumes.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4876b-292">密碼強度</span><span class="sxs-lookup"><span data-stu-id="4876b-292">Cipher Strength</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-293">管理員在 MBAM 原則規格期間選取的密碼強度。</span><span class="sxs-lookup"><span data-stu-id="4876b-293">Cipher Strength selected by the Administrator during MBAM policy specification.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4876b-294">保護器類型</span><span class="sxs-lookup"><span data-stu-id="4876b-294">Protector Types</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-295">透過用來加密作業系統或固定容量的原則所選取的保護者類型。</span><span class="sxs-lookup"><span data-stu-id="4876b-295">Type of protector selected via policy used to encrypt an operating system or Fixed volume.</span></span> <span data-ttu-id="4876b-296">作業系統上有效的保護器類型為 [TPM] 或 [TPM + PIN]，而 [固定資料量] 則是密碼。</span><span class="sxs-lookup"><span data-stu-id="4876b-296">The valid protector types on an operating system are TPM or TPM+PIN and for a Fixed Data Volume is Password.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4876b-297">保護器狀態</span><span class="sxs-lookup"><span data-stu-id="4876b-297">Protector State</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-298">指示由 MBAM 管理的電腦已啟用原則中指定的保護器類型。</span><span class="sxs-lookup"><span data-stu-id="4876b-298">Indicates that the computer being managed by MBAM has enabled the protector type specified in the policy.</span></span> <span data-ttu-id="4876b-299">[有效] 狀態為 [開啟] 或 [關閉]。</span><span class="sxs-lookup"><span data-stu-id="4876b-299">The valid states are ON or OFF.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4876b-300">加密狀態</span><span class="sxs-lookup"><span data-stu-id="4876b-300">Encryption State</span></span></p></td>
<td align="left"><p><span data-ttu-id="4876b-301">磁片磁碟機的加密狀態。</span><span class="sxs-lookup"><span data-stu-id="4876b-301">Encryption state of the drive.</span></span> <span data-ttu-id="4876b-302">有效的狀態為 [已加密]、[未加密] 和 [加密]。</span><span class="sxs-lookup"><span data-stu-id="4876b-302">Valid states are Encrypted, Not Encrypted, and Encrypting.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="4876b-303">相關主題</span><span class="sxs-lookup"><span data-stu-id="4876b-303">Related topics</span></span>


[<span data-ttu-id="4876b-304">使用 MBAM 搭配 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="4876b-304">Using MBAM with Configuration Manager</span></span>](using-mbam-with-configuration-manager.md)

 

 





