---
title: 檢視 Configuration Manager 整合拓撲的 MBAM 2.5 報告
description: 檢視 Configuration Manager 整合拓撲的 MBAM 2.5 報告
author: dansimp
ms.assetid: 60d11b2f-3a76-4023-8da4-f89e9f35b790
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3384fee62d302ac47775fe106265456ef119ab47
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810317"
---
# <span data-ttu-id="460fd-103">檢視 Configuration Manager 整合拓撲的 MBAM 2.5 報告</span><span class="sxs-lookup"><span data-stu-id="460fd-103">Viewing MBAM 2.5 Reports for the Configuration Manager Integration Topology</span></span>


<span data-ttu-id="460fd-104">本主題說明當您將 Microsoft BitLocker 管理和監控（MBAM）與 Configuration Manager 整合拓撲進行設定時，可用的報告。</span><span class="sxs-lookup"><span data-stu-id="460fd-104">This topic describes the reports that are available when you configure Microsoft BitLocker Administration and Monitoring (MBAM) with the Configuration Manager Integration topology.</span></span> <span data-ttu-id="460fd-105">報告會顯示企業及 MBAM 管理的個別電腦和裝置的 BitLocker 合規性。</span><span class="sxs-lookup"><span data-stu-id="460fd-105">The reports show BitLocker compliance for the enterprise and for individual computers and devices that MBAM manages.</span></span> <span data-ttu-id="460fd-106">報告提供表格式資訊和圖表，而且這些篩選可讓您從不同的觀點來查看資料。</span><span class="sxs-lookup"><span data-stu-id="460fd-106">The reports provide tabular information and charts, and they have filters that let you view data from different perspectives.</span></span>

<span data-ttu-id="460fd-107">在 Configuration Manager 整合拓撲中，您可以從 Configuration Manager （而不是從 [管理] 和 [監視] 網站）來查看報表，除了 [**恢復審核] 報告**以外，您還會從 [管理] 和 [監視] 網站繼續進行查看。</span><span class="sxs-lookup"><span data-stu-id="460fd-107">In the Configuration Manager Integration topology, you view reports from Configuration Manager rather than from the Administration and Monitoring Website, with the exception of the **Recovery Audit Report**, which you continue to view from the Administration and Monitoring Website.</span></span>

<span data-ttu-id="460fd-108">如需獨立拓朴 MBAM 報告的相關資訊，請參閱[針對獨立拓朴查看 MBAM 2.5 報告](viewing-mbam-25-reports-for-the-stand-alone-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="460fd-108">For information about MBAM reports for the Stand-alone topology, see [Viewing MBAM 2.5 Reports for the Stand-alone Topology](viewing-mbam-25-reports-for-the-stand-alone-topology.md).</span></span>

## <span data-ttu-id="460fd-109">在 Configuration Manager 中存取報表</span><span class="sxs-lookup"><span data-stu-id="460fd-109">Accessing reports in Configuration Manager</span></span>


<span data-ttu-id="460fd-110">若要存取 Configuration Manager 中的 [報表] 功能：</span><span class="sxs-lookup"><span data-stu-id="460fd-110">To access the Reports feature in Configuration Manager:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="460fd-111">Configuration Manager 版本</span><span class="sxs-lookup"><span data-stu-id="460fd-111">Version of Configuration Manager</span></span></th>
<th align="left"><span data-ttu-id="460fd-112">如何查看報表</span><span class="sxs-lookup"><span data-stu-id="460fd-112">How to view the reports</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="460fd-113">SystemCenter2012 ConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="460fd-113">SystemCenter2012 ConfigurationManager</span></span></p></td>
<td align="left"><ol>
<li><p><span data-ttu-id="460fd-114">在左窗格中，選取 [ <strong> 監視] </strong> 工作區。</span><span class="sxs-lookup"><span data-stu-id="460fd-114">In the left pane, select the <strong>Monitoring</strong> workspace.</span></span></p></li>
<li><p><span data-ttu-id="460fd-115">在樹狀結構中，展開 <strong> [總覽報表 </strong> &gt; <strong> </strong> &gt; <strong> 報告] </strong> &gt; <strong> MBAM </strong> 。</span><span class="sxs-lookup"><span data-stu-id="460fd-115">In the tree, expand <strong>Overview</strong> &gt; <strong>Reporting</strong> &gt; <strong>Reports</strong> &gt; <strong>MBAM</strong>.</span></span></p></li>
<li><p><span data-ttu-id="460fd-116">選取代表您要用來查看報表之語言的資料夾，然後從右窗格中選取報表。</span><span class="sxs-lookup"><span data-stu-id="460fd-116">Select the folder that represents the language in which you want to view reports, and then select the report from the right pane.</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="460fd-117">Configuration Manager 2007</span><span class="sxs-lookup"><span data-stu-id="460fd-117">Configuration Manager 2007</span></span></p></td>
<td align="left"><ol>
<li><p><span data-ttu-id="460fd-118">在左窗格中，展開 [ <strong> 電腦管理 </strong> &gt; <strong> 報告 </strong> &gt; <strong> 服務] </strong> &gt; <strong> &lt; 伺服器名稱 &gt; </strong> &gt; <strong> 報告資料夾 </strong> &gt; <strong> MBAM </strong> 。</span><span class="sxs-lookup"><span data-stu-id="460fd-118">In the left pane, expand <strong>Computer Management</strong> &gt; <strong>Reporting</strong> &gt; <strong>Reporting Services</strong> &gt; <strong>&lt;server name&gt;</strong> &gt; <strong>Report folders</strong> &gt; <strong>MBAM</strong>.</span></span></p></li>
<li><p><span data-ttu-id="460fd-119">選取代表您要用來查看報表之語言的資料夾，然後從右窗格中選取報表。</span><span class="sxs-lookup"><span data-stu-id="460fd-119">Select the folder that represents the language in which you want to view reports, and then select the report from the right pane.</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="460fd-120">Configuration Manager 中的報表描述</span><span class="sxs-lookup"><span data-stu-id="460fd-120">Description of reports in Configuration Manager</span></span>


<span data-ttu-id="460fd-121">Configuration Manager 整合拓朴與獨立拓朴的報告有幾項細微的差異。</span><span class="sxs-lookup"><span data-stu-id="460fd-121">There are a few minor differences in the reports for the Configuration Manager Integration topology and the Stand-alone topology.</span></span> <span data-ttu-id="460fd-122">下列各節說明 Configuration Manager 整合拓朴的 MBAM 報告中的資料：</span><span class="sxs-lookup"><span data-stu-id="460fd-122">The following sections describe the data in the MBAM reports for the Configuration Manager Integration topology:</span></span>

-   [<span data-ttu-id="460fd-123">BitLocker Enterprise 合規性儀表板</span><span class="sxs-lookup"><span data-stu-id="460fd-123">BitLocker Enterprise Compliance Dashboard</span></span>](#bkmk-dashboard)

-   [<span data-ttu-id="460fd-124">BitLocker 企業合規性詳細資料</span><span class="sxs-lookup"><span data-stu-id="460fd-124">BitLocker Enterprise Compliance Details</span></span>](#bkmk-compliancedetails)

-   [<span data-ttu-id="460fd-125">BitLocker Enterprise 合規性摘要</span><span class="sxs-lookup"><span data-stu-id="460fd-125">BitLocker Enterprise Compliance Summary</span></span>](#bkmk-compliancesummary)

-   [<span data-ttu-id="460fd-126">BitLocker 電腦合規性報告</span><span class="sxs-lookup"><span data-stu-id="460fd-126">BitLocker Computer Compliance Report</span></span>](#bkmk-compliancereport)

### <a href="" id="bkmk-dashboard"></a><span data-ttu-id="460fd-127">BitLocker Enterprise 合規性儀表板</span><span class="sxs-lookup"><span data-stu-id="460fd-127">BitLocker Enterprise Compliance Dashboard</span></span>

<span data-ttu-id="460fd-128">BitLocker Enterprise 合規性儀表板提供下列圖表，在整個企業中顯示 BitLocker 合規性狀態：</span><span class="sxs-lookup"><span data-stu-id="460fd-128">The BitLocker Enterprise Compliance Dashboard provides the following graphs, which show BitLocker compliance status across the enterprise:</span></span>

-   <span data-ttu-id="460fd-129">合規性狀態發佈</span><span class="sxs-lookup"><span data-stu-id="460fd-129">Compliance Status Distribution</span></span>

-   <span data-ttu-id="460fd-130">不相容的錯誤發佈</span><span class="sxs-lookup"><span data-stu-id="460fd-130">Non Compliant Errors Distribution</span></span>

-   <span data-ttu-id="460fd-131">依磁片磁碟機類型進行合規性狀態發佈</span><span class="sxs-lookup"><span data-stu-id="460fd-131">Compliance Status Distribution by Drive Type</span></span>

**<span data-ttu-id="460fd-132">合規性狀態發佈</span><span class="sxs-lookup"><span data-stu-id="460fd-132">Compliance Status Distribution</span></span>**

<span data-ttu-id="460fd-133">此圓形圖顯示企業內部電腦的合規性狀態。</span><span class="sxs-lookup"><span data-stu-id="460fd-133">This pie chart shows compliance status for computers within the enterprise.</span></span> <span data-ttu-id="460fd-134">它也會顯示電腦的百分比，與所選集合中擁有該符合性狀態之電腦總數的比較。</span><span class="sxs-lookup"><span data-stu-id="460fd-134">It also shows the percentage of computers, compared to the total number of computers in the selected collection, that has that compliance status.</span></span> <span data-ttu-id="460fd-135">也會顯示每個狀態的實際電腦數。</span><span class="sxs-lookup"><span data-stu-id="460fd-135">The actual number of computers with each status is also shown.</span></span> <span data-ttu-id="460fd-136">圓形圖顯示下列合規性狀態：</span><span class="sxs-lookup"><span data-stu-id="460fd-136">The pie chart shows the following compliance statuses:</span></span>

-   <span data-ttu-id="460fd-137">達到</span><span class="sxs-lookup"><span data-stu-id="460fd-137">Compliant</span></span>

-   <span data-ttu-id="460fd-138">不符合</span><span class="sxs-lookup"><span data-stu-id="460fd-138">Non Compliant</span></span>

-   <span data-ttu-id="460fd-139">使用者豁免</span><span class="sxs-lookup"><span data-stu-id="460fd-139">User Exempt</span></span>

-   <span data-ttu-id="460fd-140">暫時使用者豁免</span><span class="sxs-lookup"><span data-stu-id="460fd-140">Temporary User Exempt</span></span>

-   <span data-ttu-id="460fd-141">未強制執行原則</span><span class="sxs-lookup"><span data-stu-id="460fd-141">Policy Not Enforced</span></span>

-   <span data-ttu-id="460fd-142">清楚.</span><span class="sxs-lookup"><span data-stu-id="460fd-142">Unknown.</span></span> <span data-ttu-id="460fd-143">這些電腦報告狀態錯誤，或它們是集合的一部分，但從未報告其符合性狀態。</span><span class="sxs-lookup"><span data-stu-id="460fd-143">These computers reported a status error, or they are part of the collection, but have never reported their compliance status.</span></span> <span data-ttu-id="460fd-144">如果電腦斷開與組織的連線，則無法使用合規性狀態。</span><span class="sxs-lookup"><span data-stu-id="460fd-144">The lack of a compliance status could occur if the computer is disconnected from the organization.</span></span>

**<span data-ttu-id="460fd-145">不相容的錯誤發佈</span><span class="sxs-lookup"><span data-stu-id="460fd-145">Non Compliant Errors Distribution</span></span>**

<span data-ttu-id="460fd-146">此圓形圖顯示企業中不符合 BitLocker 磁碟機加密原則的電腦類別，並顯示每個類別中的電腦數。</span><span class="sxs-lookup"><span data-stu-id="460fd-146">This pie chart shows the categories of computers in the enterprise that are not compliant with the BitLocker Drive Encryption policy, and shows the number of computers in each category.</span></span> <span data-ttu-id="460fd-147">每個類別百分比是從集合中不相容電腦的總數計算而來。</span><span class="sxs-lookup"><span data-stu-id="460fd-147">Each category percentage is calculated from the total number of non-compliant computers in the collection.</span></span>

-   <span data-ttu-id="460fd-148">使用者已延遲加密</span><span class="sxs-lookup"><span data-stu-id="460fd-148">User postponed encryption</span></span>

-   <span data-ttu-id="460fd-149">找不到相容的 TPM</span><span class="sxs-lookup"><span data-stu-id="460fd-149">Unable to find compatible TPM</span></span>

-   <span data-ttu-id="460fd-150">系統磁碟分割無法使用或太大</span><span class="sxs-lookup"><span data-stu-id="460fd-150">System partition not available or large enough</span></span>

-   <span data-ttu-id="460fd-151">原則衝突</span><span class="sxs-lookup"><span data-stu-id="460fd-151">Policy conflict</span></span>

-   <span data-ttu-id="460fd-152">正在等待 TPM 自動預配</span><span class="sxs-lookup"><span data-stu-id="460fd-152">Waiting for TPM auto provisioning</span></span>

-   <span data-ttu-id="460fd-153">發生未知的錯誤</span><span class="sxs-lookup"><span data-stu-id="460fd-153">An unknown error has occurred</span></span>

-   <span data-ttu-id="460fd-154">沒有任何資訊。</span><span class="sxs-lookup"><span data-stu-id="460fd-154">No information.</span></span> <span data-ttu-id="460fd-155">這些電腦沒有安裝 MBAM 用戶端，或已安裝 MBAM 用戶端，但尚未啟用（例如，服務無法運作）。</span><span class="sxs-lookup"><span data-stu-id="460fd-155">These computers do not have the MBAM Client installed, or they have the MBAM Client installed but not activated (for example, the service is not working).</span></span>

**<span data-ttu-id="460fd-156">依磁片磁碟機類型進行合規性狀態發佈</span><span class="sxs-lookup"><span data-stu-id="460fd-156">Compliance Status Distribution by Drive Type</span></span>**

<span data-ttu-id="460fd-157">此橫條圖顯示 [依磁片磁碟機類型列出目前的 BitLocker 合規性狀態]。</span><span class="sxs-lookup"><span data-stu-id="460fd-157">This bar chart shows the current BitLocker compliance status by drive type.</span></span> <span data-ttu-id="460fd-158">狀態**符合規範**且**不相容**。</span><span class="sxs-lookup"><span data-stu-id="460fd-158">The statuses are **Compliant** and **Non Compliant**.</span></span> <span data-ttu-id="460fd-159">會顯示 [固定資料磁碟機] 和 [作業系統磁片磁碟機] 的橫條圖。</span><span class="sxs-lookup"><span data-stu-id="460fd-159">Bars are shown for fixed data drives and operating system drives.</span></span> <span data-ttu-id="460fd-160">包括沒有固定資料磁碟機的電腦，而且只會顯示**作業系統磁片磁碟機**列中的值。</span><span class="sxs-lookup"><span data-stu-id="460fd-160">Computers that do not have a fixed data drive are included and show a value only in the **Operating System Drive** bar.</span></span> <span data-ttu-id="460fd-161">圖表不包括已從 BitLocker 磁碟機加密原則或 [無原則] 類別獲授權的使用者。</span><span class="sxs-lookup"><span data-stu-id="460fd-161">The chart does not include users who have been granted an exemption from the BitLocker Drive Encryption policy or the No Policy category.</span></span>

### <a href="" id="bkmk-compliancedetails"></a><span data-ttu-id="460fd-162">BitLocker 企業合規性詳細資料</span><span class="sxs-lookup"><span data-stu-id="460fd-162">BitLocker Enterprise Compliance Details</span></span>

<span data-ttu-id="460fd-163">此報告會在您的企業中顯示針對以 BitLocker 為目標的電腦集合的整個 BitLocker 規範的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="460fd-163">This report shows information about the overall BitLocker compliance across your enterprise for the collection of computers that is targeted for BitLocker use.</span></span>

**<span data-ttu-id="460fd-164">BitLocker 企業合規性詳細資料欄位</span><span class="sxs-lookup"><span data-stu-id="460fd-164">BitLocker Enterprise Compliance Details Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="460fd-165">欄名稱</span><span class="sxs-lookup"><span data-stu-id="460fd-165">Column Name</span></span></th>
<th align="left"><span data-ttu-id="460fd-166">描述</span><span class="sxs-lookup"><span data-stu-id="460fd-166">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="460fd-167">受管理的電腦</span><span class="sxs-lookup"><span data-stu-id="460fd-167">Managed Computers</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-168">MBAM 管理的電腦數。</span><span class="sxs-lookup"><span data-stu-id="460fd-168">Number of computers that MBAM manages.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="460fd-169">符合百分比</span><span class="sxs-lookup"><span data-stu-id="460fd-169">% Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-170">企業中合規性電腦的百分比。</span><span class="sxs-lookup"><span data-stu-id="460fd-170">Percentage of compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="460fd-171">非相容性%</span><span class="sxs-lookup"><span data-stu-id="460fd-171">% Non-Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-172">企業中不相容的電腦百分比。</span><span class="sxs-lookup"><span data-stu-id="460fd-172">Percentage of non-compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="460fd-173">% 的未知規範</span><span class="sxs-lookup"><span data-stu-id="460fd-173">% Unknown Compliance</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-174">相容性狀態為未知的電腦所占的百分比。</span><span class="sxs-lookup"><span data-stu-id="460fd-174">Percentage of computers with a compliance state that is not known.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="460fd-175">% 豁免</span><span class="sxs-lookup"><span data-stu-id="460fd-175">% Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-176">免除 BitLocker 加密需求的電腦所占的百分比。</span><span class="sxs-lookup"><span data-stu-id="460fd-176">Percentage of computers exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="460fd-177">非豁免%</span><span class="sxs-lookup"><span data-stu-id="460fd-177">% Non-Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-178">不受 BitLocker 加密需求免除的電腦百分比。</span><span class="sxs-lookup"><span data-stu-id="460fd-178">Percentage of computers not exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="460fd-179">達到</span><span class="sxs-lookup"><span data-stu-id="460fd-179">Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-180">企業中合規性電腦的百分比。</span><span class="sxs-lookup"><span data-stu-id="460fd-180">Percentage of compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="460fd-181">不相容</span><span class="sxs-lookup"><span data-stu-id="460fd-181">Non-Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-182">企業中不相容的電腦百分比。</span><span class="sxs-lookup"><span data-stu-id="460fd-182">Percentage of non-compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="460fd-183">未知的合規性</span><span class="sxs-lookup"><span data-stu-id="460fd-183">Unknown Compliance</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-184">相容性狀態為未知的電腦所占的百分比。</span><span class="sxs-lookup"><span data-stu-id="460fd-184">Percentage of computers with a compliance state that is not known.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="460fd-185">免除</span><span class="sxs-lookup"><span data-stu-id="460fd-185">Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-186">免除 BitLocker 加密需求的電腦總數。</span><span class="sxs-lookup"><span data-stu-id="460fd-186">Total computers that are exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="460fd-187">非豁免</span><span class="sxs-lookup"><span data-stu-id="460fd-187">Non-Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-188">未免除 BitLocker 加密需求的電腦總數。</span><span class="sxs-lookup"><span data-stu-id="460fd-188">Total computers that are not exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="460fd-189">BitLocker Enterprise 合規性詳細資料狀態</span><span class="sxs-lookup"><span data-stu-id="460fd-189">BitLocker Enterprise Compliance Details States</span></span>**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="460fd-190">合規性狀態</span><span class="sxs-lookup"><span data-stu-id="460fd-190">Compliance Status</span></span></th>
<th align="left"><span data-ttu-id="460fd-191">免除</span><span class="sxs-lookup"><span data-stu-id="460fd-191">Exemption</span></span></th>
<th align="left"><span data-ttu-id="460fd-192">描述</span><span class="sxs-lookup"><span data-stu-id="460fd-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="460fd-193">標準</span><span class="sxs-lookup"><span data-stu-id="460fd-193">Noncompliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-194">未免除</span><span class="sxs-lookup"><span data-stu-id="460fd-194">Not exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-195">根據指定的原則，電腦是不相容的。</span><span class="sxs-lookup"><span data-stu-id="460fd-195">The computer is noncompliant, according to the specified policy.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="460fd-196">達到</span><span class="sxs-lookup"><span data-stu-id="460fd-196">Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-197">未免除</span><span class="sxs-lookup"><span data-stu-id="460fd-197">Not exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-198">根據指定的原則，電腦符合規範。</span><span class="sxs-lookup"><span data-stu-id="460fd-198">The computer is compliant in accordance with the specified policy.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="bkmk-compliancesummary"></a><span data-ttu-id="460fd-199">BitLocker Enterprise 合規性摘要</span><span class="sxs-lookup"><span data-stu-id="460fd-199">BitLocker Enterprise Compliance Summary</span></span>

<span data-ttu-id="460fd-200">您可以使用此報告類型來顯示整個企業的 BitLocker 合規性相關資訊，以及顯示針對 BitLocker 使用之電腦集合中的個別電腦的相容性。</span><span class="sxs-lookup"><span data-stu-id="460fd-200">Use this report type to show information about the overall BitLocker compliance across your enterprise and to show the compliance for individual computers that are in the collection of computers that is targeted for BitLocker use.</span></span>

**<span data-ttu-id="460fd-201">BitLocker Enterprise 合規性摘要欄位</span><span class="sxs-lookup"><span data-stu-id="460fd-201">BitLocker Enterprise Compliance Summary Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="460fd-202">欄名稱</span><span class="sxs-lookup"><span data-stu-id="460fd-202">Column Name</span></span></th>
<th align="left"><span data-ttu-id="460fd-203">描述</span><span class="sxs-lookup"><span data-stu-id="460fd-203">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="460fd-204">受管理的電腦</span><span class="sxs-lookup"><span data-stu-id="460fd-204">Managed Computers</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-205">MBAM 管理的電腦數。</span><span class="sxs-lookup"><span data-stu-id="460fd-205">Number of computers that MBAM manages.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="460fd-206">符合百分比</span><span class="sxs-lookup"><span data-stu-id="460fd-206">% Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-207">企業中合規性電腦的百分比。</span><span class="sxs-lookup"><span data-stu-id="460fd-207">Percentage of compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="460fd-208">非相容性%</span><span class="sxs-lookup"><span data-stu-id="460fd-208">% Non-Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-209">企業中不相容的電腦百分比。</span><span class="sxs-lookup"><span data-stu-id="460fd-209">Percentage of non-compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="460fd-210">% 的未知規範</span><span class="sxs-lookup"><span data-stu-id="460fd-210">% Unknown Compliance</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-211">相容性狀態為未知的電腦所占的百分比。</span><span class="sxs-lookup"><span data-stu-id="460fd-211">Percentage of computers with a compliance state that is not known.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="460fd-212">% 豁免</span><span class="sxs-lookup"><span data-stu-id="460fd-212">% Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-213">免除 BitLocker 加密需求的電腦所占的百分比。</span><span class="sxs-lookup"><span data-stu-id="460fd-213">Percentage of computers exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="460fd-214">非豁免%</span><span class="sxs-lookup"><span data-stu-id="460fd-214">% Non-Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-215">不受 BitLocker 加密需求免除的電腦百分比。</span><span class="sxs-lookup"><span data-stu-id="460fd-215">Percentage of computers not exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="460fd-216">達到</span><span class="sxs-lookup"><span data-stu-id="460fd-216">Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-217">企業中合規性電腦的百分比。</span><span class="sxs-lookup"><span data-stu-id="460fd-217">Percentage of compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="460fd-218">不相容</span><span class="sxs-lookup"><span data-stu-id="460fd-218">Non-Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-219">企業中不相容的電腦百分比。</span><span class="sxs-lookup"><span data-stu-id="460fd-219">Percentage of non-compliant computers in the enterprise.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="460fd-220">未知的合規性</span><span class="sxs-lookup"><span data-stu-id="460fd-220">Unknown Compliance</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-221">相容性狀態為未知的電腦所占的百分比。</span><span class="sxs-lookup"><span data-stu-id="460fd-221">Percentage of computers with a compliance state that is not known.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="460fd-222">免除</span><span class="sxs-lookup"><span data-stu-id="460fd-222">Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-223">免除 BitLocker 加密需求的電腦總數。</span><span class="sxs-lookup"><span data-stu-id="460fd-223">Total computers that are exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="460fd-224">非豁免</span><span class="sxs-lookup"><span data-stu-id="460fd-224">Non-Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-225">未免除 BitLocker 加密需求的電腦總數。</span><span class="sxs-lookup"><span data-stu-id="460fd-225">Total computers that are not exempt from the BitLocker encryption requirement.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="460fd-226">BitLocker Enterprise 合規性摘要電腦詳細資料</span><span class="sxs-lookup"><span data-stu-id="460fd-226">BitLocker Enterprise Compliance Summary Computer Details</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="460fd-227">欄名稱</span><span class="sxs-lookup"><span data-stu-id="460fd-227">Column Name</span></span></th>
<th align="left"><span data-ttu-id="460fd-228">描述</span><span class="sxs-lookup"><span data-stu-id="460fd-228">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="460fd-229">電腦名稱稱</span><span class="sxs-lookup"><span data-stu-id="460fd-229">Computer Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-230">由 MBAM 管理的使用者指定 DNS 電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="460fd-230">User-specified DNS computer name that is being managed by MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="460fd-231">網功能變數名稱稱</span><span class="sxs-lookup"><span data-stu-id="460fd-231">Domain Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-232">用戶端電腦駐留且由 MBAM 管理的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="460fd-232">Fully qualified domain name, where the client computer resides and is managed by MBAM.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="460fd-233">合規性狀態</span><span class="sxs-lookup"><span data-stu-id="460fd-233">Compliance Status</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-234">由 MBAM 管理之電腦的整體合規性狀態。</span><span class="sxs-lookup"><span data-stu-id="460fd-234">Overall compliance status of the computer managed by MBAM.</span></span> <span data-ttu-id="460fd-235">有效的狀態是相容且不相容。</span><span class="sxs-lookup"><span data-stu-id="460fd-235">Valid states are Compliant and Noncompliant.</span></span> <span data-ttu-id="460fd-236">請注意，每個磁片磁碟機的相容性狀態（請參閱後面的資料表）可能會指出不同的合規性狀態。</span><span class="sxs-lookup"><span data-stu-id="460fd-236">Notice that the compliance status per drive (see the table that follows) may indicate different compliance states.</span></span> <span data-ttu-id="460fd-237">不過，這個欄位會根據指定的原則來代表符合性狀態。</span><span class="sxs-lookup"><span data-stu-id="460fd-237">However, this field represents that compliance state, in accordance with the policy specified.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="460fd-238">免除</span><span class="sxs-lookup"><span data-stu-id="460fd-238">Exemption</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-239">此狀態表示使用者是否已免除或未免除 BitLocker 原則。</span><span class="sxs-lookup"><span data-stu-id="460fd-239">Status that indicates whether the user is exempt or non-exempt from the BitLocker policy.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="460fd-240">裝置使用者</span><span class="sxs-lookup"><span data-stu-id="460fd-240">Device Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-241">裝置的使用者。</span><span class="sxs-lookup"><span data-stu-id="460fd-241">User of the device.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="460fd-242">合規性狀態詳細資料</span><span class="sxs-lookup"><span data-stu-id="460fd-242">Compliance Status Details</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-243">符合指定原則之電腦符合性狀態的錯誤與狀態訊息。</span><span class="sxs-lookup"><span data-stu-id="460fd-243">Error and status messages about the compliance state of the computer in accordance with the policy specified.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="460fd-244">最後一個連絡人</span><span class="sxs-lookup"><span data-stu-id="460fd-244">Last Contact</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-245">電腦上次取得伺服器以報告合規性狀態的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="460fd-245">Date and time that the computer last contacted the server to report compliance status.</span></span> <span data-ttu-id="460fd-246">連絡人頻率可透過 [群組原則] 設定進行設定。</span><span class="sxs-lookup"><span data-stu-id="460fd-246">The contact frequency is configurable through the Group Policy settings.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="bkmk-compliancereport"></a><span data-ttu-id="460fd-247">BitLocker 電腦合規性報告</span><span class="sxs-lookup"><span data-stu-id="460fd-247">BitLocker Computer Compliance Report</span></span>

<span data-ttu-id="460fd-248">使用此報告類型可收集電腦專用的資訊。</span><span class="sxs-lookup"><span data-stu-id="460fd-248">Use this report type to collect information that is specific to a computer.</span></span> <span data-ttu-id="460fd-249">BitLocker 電腦合規性報告提供電腦上每個磁片磁碟機的詳細加密資訊（作業系統及固定資料磁碟機）。</span><span class="sxs-lookup"><span data-stu-id="460fd-249">The BitLocker Computer Compliance Report provides detailed encryption information about each drive on a computer (operating system and fixed data drives).</span></span> <span data-ttu-id="460fd-250">它也會提供應用於電腦上每個磁片磁碟機類型的原則的指示。</span><span class="sxs-lookup"><span data-stu-id="460fd-250">It also provides an indication of the policy that is applied to each drive type on the computer.</span></span> <span data-ttu-id="460fd-251">若要查看每個磁片磁碟機的詳細資料，請展開 [電腦名稱稱] 專案。</span><span class="sxs-lookup"><span data-stu-id="460fd-251">To view the details of each drive, expand the Computer Name entry.</span></span>

<span data-ttu-id="460fd-252">**記事** 此報告中不會顯示 [移除資料量] 加密狀態。</span><span class="sxs-lookup"><span data-stu-id="460fd-252">**Note** The Removable Data Volume encryption status is not shown in this report.</span></span>

 

**<span data-ttu-id="460fd-253">BitLocker 電腦合規性報告： [電腦詳細資料] 欄位</span><span class="sxs-lookup"><span data-stu-id="460fd-253">BitLocker Computer Compliance Report: Computer Details Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="460fd-254">欄名稱</span><span class="sxs-lookup"><span data-stu-id="460fd-254">Column Name</span></span></th>
<th align="left"><span data-ttu-id="460fd-255">描述</span><span class="sxs-lookup"><span data-stu-id="460fd-255">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="460fd-256">電腦名稱稱</span><span class="sxs-lookup"><span data-stu-id="460fd-256">Computer Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-257">由 MBAM 管理的使用者指定 DNS 電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="460fd-257">User-specified DNS computer name that is being managed by MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="460fd-258">網功能變數名稱稱</span><span class="sxs-lookup"><span data-stu-id="460fd-258">Domain Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-259">用戶端電腦駐留且由 MBAM 管理的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="460fd-259">Fully qualified domain name, where the client computer resides and is managed by MBAM.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="460fd-260">電腦類型</span><span class="sxs-lookup"><span data-stu-id="460fd-260">Computer Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-261">電腦類型。</span><span class="sxs-lookup"><span data-stu-id="460fd-261">Type of computer.</span></span> <span data-ttu-id="460fd-262">有效類型為非便攜且可移植。</span><span class="sxs-lookup"><span data-stu-id="460fd-262">Valid types are Non-Portable and Portable.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="460fd-263">作業系統</span><span class="sxs-lookup"><span data-stu-id="460fd-263">Operating System</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-264">在 MBAM managed 用戶端電腦上找到的作業系統類型。</span><span class="sxs-lookup"><span data-stu-id="460fd-264">Operating System type found on the MBAM managed client computer.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="460fd-265">整體合規性</span><span class="sxs-lookup"><span data-stu-id="460fd-265">Overall Compliance</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-266">由 MBAM 管理之電腦的整體合規性狀態。</span><span class="sxs-lookup"><span data-stu-id="460fd-266">Overall compliance status of the computer managed by MBAM.</span></span> <span data-ttu-id="460fd-267">有效的狀態是相容且不相容。</span><span class="sxs-lookup"><span data-stu-id="460fd-267">Valid states are Compliant and Noncompliant.</span></span> <span data-ttu-id="460fd-268">請注意，每個磁片磁碟機的相容性狀態（請參閱後面的資料表）可能會指出不同的合規性狀態。</span><span class="sxs-lookup"><span data-stu-id="460fd-268">Notice that the compliance status per drive (see the table that follows) may indicate different compliance states.</span></span> <span data-ttu-id="460fd-269">不過，這個欄位會根據指定的原則來代表符合性狀態。</span><span class="sxs-lookup"><span data-stu-id="460fd-269">However, this field represents that compliance state in accordance with the policy specified.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="460fd-270">作業系統合規性</span><span class="sxs-lookup"><span data-stu-id="460fd-270">Operating System Compliance</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-271">由 MBAM 管理之作業系統的合規性狀態。</span><span class="sxs-lookup"><span data-stu-id="460fd-271">Compliance status of the operating system that is managed by MBAM.</span></span> <span data-ttu-id="460fd-272">有效的狀態是相容且不相容。</span><span class="sxs-lookup"><span data-stu-id="460fd-272">Valid states are Compliant and Noncompliant.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="460fd-273">固定資料磁碟機合規性</span><span class="sxs-lookup"><span data-stu-id="460fd-273">Fixed Data Drive Compliance</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-274">由 MBAM 管理的固定資料磁碟機的合規性狀態。</span><span class="sxs-lookup"><span data-stu-id="460fd-274">Compliance status of the fixed data drive that is managed by MBAM.</span></span> <span data-ttu-id="460fd-275">有效的狀態是相容且不相容。</span><span class="sxs-lookup"><span data-stu-id="460fd-275">Valid states are Compliant and Noncompliant.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="460fd-276">上次更新日期</span><span class="sxs-lookup"><span data-stu-id="460fd-276">Last Update Date</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-277">電腦上次取得伺服器以報告合規性狀態的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="460fd-277">Date and time that the computer last contacted the server to report compliance status.</span></span> <span data-ttu-id="460fd-278">連絡人頻率可透過 [群組原則] 設定進行設定。</span><span class="sxs-lookup"><span data-stu-id="460fd-278">The contact frequency is configurable through the Group Policy settings.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="460fd-279">免除</span><span class="sxs-lookup"><span data-stu-id="460fd-279">Exemption</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-280">此狀態表示使用者是否已免除或未免除 BitLocker 原則。</span><span class="sxs-lookup"><span data-stu-id="460fd-280">Status that indicates whether the user is exempt or non-exempt from the BitLocker policy.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="460fd-281">免除的使用者</span><span class="sxs-lookup"><span data-stu-id="460fd-281">Exempted User</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-282">從 BitLocker 原則免除的使用者。</span><span class="sxs-lookup"><span data-stu-id="460fd-282">User who is exempt from the BitLocker policy.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="460fd-283">免除日期</span><span class="sxs-lookup"><span data-stu-id="460fd-283">Exemption Date</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-284">授與免除的日期。</span><span class="sxs-lookup"><span data-stu-id="460fd-284">Date on which the exemption was granted.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="460fd-285">合規性狀態詳細資料</span><span class="sxs-lookup"><span data-stu-id="460fd-285">Compliance Status Details</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-286">符合指定原則之電腦符合性狀態的錯誤與狀態訊息。</span><span class="sxs-lookup"><span data-stu-id="460fd-286">Error and status messages about the compliance state of the computer in accordance with the policy specified.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="460fd-287">原則密碼強度</span><span class="sxs-lookup"><span data-stu-id="460fd-287">Policy Cipher Strength</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-288">系統管理員在 MBAM 原則規格期間選取的密碼強度（例如，使用擴散器的128位）。</span><span class="sxs-lookup"><span data-stu-id="460fd-288">Cipher strength selected by the Administrator during the MBAM policy specification (for example, 128-bit with diffuser).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="460fd-289">原則：作業系統磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="460fd-289">Policy: Operating System Drive</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-290">表示作業系統是否需要加密，以及適當的保護器類型。</span><span class="sxs-lookup"><span data-stu-id="460fd-290">Indicates if encryption is required for the operating system and the appropriate protector type.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="460fd-291">原則：固定資料磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="460fd-291">Policy: Fixed Data Drive</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-292">表示固定資料磁碟機是否需要加密。</span><span class="sxs-lookup"><span data-stu-id="460fd-292">Indicates if encryption is required for the fixed data drive.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="460fd-293">製造商</span><span class="sxs-lookup"><span data-stu-id="460fd-293">Manufacturer</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-294">電腦製造商出現在電腦 BIOS 中的名稱。</span><span class="sxs-lookup"><span data-stu-id="460fd-294">Computer manufacturer name as it appears in the computer BIOS.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="460fd-295">型號</span><span class="sxs-lookup"><span data-stu-id="460fd-295">Model</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-296">電腦製造商模型名稱，如電腦 BIOS 中所示。</span><span class="sxs-lookup"><span data-stu-id="460fd-296">Computer manufacturer model name as it appears in the computer BIOS.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="460fd-297">裝置使用者</span><span class="sxs-lookup"><span data-stu-id="460fd-297">Device Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-298">由 MBAM 管理的電腦上的已知使用者。</span><span class="sxs-lookup"><span data-stu-id="460fd-298">Known users on the computer that is being managed by MBAM.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="460fd-299">BitLocker 電腦合規性報告： [電腦卷] 欄位</span><span class="sxs-lookup"><span data-stu-id="460fd-299">BitLocker Computer Compliance Report: Computer Volume Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="460fd-300">欄名稱</span><span class="sxs-lookup"><span data-stu-id="460fd-300">Column Name</span></span></th>
<th align="left"><span data-ttu-id="460fd-301">描述</span><span class="sxs-lookup"><span data-stu-id="460fd-301">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="460fd-302">磁片磁碟機盤符</span><span class="sxs-lookup"><span data-stu-id="460fd-302">Drive Letter</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-303">使用者指派給特定磁片磁碟機的電腦磁碟機盤符。</span><span class="sxs-lookup"><span data-stu-id="460fd-303">Computer drive letter that was assigned to the particular drive by the user.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="460fd-304">磁片磁碟機類型</span><span class="sxs-lookup"><span data-stu-id="460fd-304">Drive Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-305">磁片磁碟機類型。</span><span class="sxs-lookup"><span data-stu-id="460fd-305">Type of drive.</span></span> <span data-ttu-id="460fd-306">有效值為作業系統磁片磁碟機及固定資料磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="460fd-306">Valid values are Operating System Drive and Fixed Data Drive.</span></span> <span data-ttu-id="460fd-307">這些是物理磁片磁碟機，而不是邏輯磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="460fd-307">These are physical drives rather than logical volumes.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="460fd-308">密碼強度</span><span class="sxs-lookup"><span data-stu-id="460fd-308">Cipher Strength</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-309">管理員在 MBAM 原則規格期間選取的密碼強度。</span><span class="sxs-lookup"><span data-stu-id="460fd-309">Cipher strength selected by the Administrator during MBAM policy specification.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="460fd-310">保護器類型</span><span class="sxs-lookup"><span data-stu-id="460fd-310">Protector Types</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-311">透過用來加密作業系統或固定資料磁碟機之原則所選取的保護者類型。</span><span class="sxs-lookup"><span data-stu-id="460fd-311">Type of protector selected through the policy used to encrypt an operating system or fixed data drive.</span></span> <span data-ttu-id="460fd-312">作業系統的有效保護器類型為 [TPM] 或 [TPM + PIN]。</span><span class="sxs-lookup"><span data-stu-id="460fd-312">The valid protector types for an operating system are TPM or TPM+PIN.</span></span> <span data-ttu-id="460fd-313">固定資料磁碟機的有效保護器類型是密碼。</span><span class="sxs-lookup"><span data-stu-id="460fd-313">The valid protector type for a fixed data drive is a password.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="460fd-314">保護器狀態</span><span class="sxs-lookup"><span data-stu-id="460fd-314">Protector State</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-315">指示由 MBAM 管理的電腦已啟用原則中指定的保護器類型。</span><span class="sxs-lookup"><span data-stu-id="460fd-315">Indicates that the computer being managed by MBAM has enabled the protector type specified in the policy.</span></span> <span data-ttu-id="460fd-316">[有效] 狀態為 [開啟] 或 [關閉]。</span><span class="sxs-lookup"><span data-stu-id="460fd-316">The valid states are ON or OFF.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="460fd-317">加密狀態</span><span class="sxs-lookup"><span data-stu-id="460fd-317">Encryption State</span></span></p></td>
<td align="left"><p><span data-ttu-id="460fd-318">磁片磁碟機的加密狀態。</span><span class="sxs-lookup"><span data-stu-id="460fd-318">Encryption state of the drive.</span></span> <span data-ttu-id="460fd-319">有效的狀態為 [已加密]、[未加密] 和 [加密]。</span><span class="sxs-lookup"><span data-stu-id="460fd-319">Valid states are Encrypted, Not Encrypted, and Encrypting.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="460fd-320">相關主題</span><span class="sxs-lookup"><span data-stu-id="460fd-320">Related topics</span></span>


[<span data-ttu-id="460fd-321">使用 MBAM 2.5 監視與報告 BitLocker 符合性</span><span class="sxs-lookup"><span data-stu-id="460fd-321">Monitoring and Reporting BitLocker Compliance with MBAM 2.5</span></span>](monitoring-and-reporting-bitlocker-compliance-with-mbam-25.md)

 

## <span data-ttu-id="460fd-322">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="460fd-322">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="460fd-323">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="460fd-323">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="460fd-324">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="460fd-324">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





