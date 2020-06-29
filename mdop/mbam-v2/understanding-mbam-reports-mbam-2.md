---
title: 瞭解 MBAM 報告
description: 瞭解 MBAM 報告
author: dansimp
ms.assetid: 8778f333-760e-4f26-acb4-4e73b6fbb536
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3c3ca5e4da4cbcea80c87520f0ecd05e1e7d6be0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810179"
---
# <span data-ttu-id="84d4f-103">瞭解 MBAM 報告</span><span class="sxs-lookup"><span data-stu-id="84d4f-103">Understanding MBAM Reports</span></span>


<span data-ttu-id="84d4f-104">如果您在安裝 Microsoft BitLocker 管理和監控（MBAM）時選擇獨立拓撲，您可以在 MBAM 中執行不同的報告，以監控 BitLocker 使用量與合規性。</span><span class="sxs-lookup"><span data-stu-id="84d4f-104">If you chose the Stand-alone topology when you installed Microsoft BitLocker Administration and Monitoring (MBAM), you can run different reports in MBAM to monitor BitLocker usage and compliance.</span></span> <span data-ttu-id="84d4f-105">MBAM 報告合規性，以及其所管理之所有電腦和裝置的其他相關資訊。</span><span class="sxs-lookup"><span data-stu-id="84d4f-105">MBAM reports compliance and other information about all of the computers and devices it manages.</span></span> <span data-ttu-id="84d4f-106">本主題中的資訊可用來協助您瞭解企業及個別電腦相容性的 Microsoft BitLocker 管理和監控報告，以及主要的復原活動。</span><span class="sxs-lookup"><span data-stu-id="84d4f-106">The information in this topic can be used to help you understand the Microsoft BitLocker Administration and Monitoring reports for enterprise and individual computer compliance and for key recovery activity.</span></span>

<span data-ttu-id="84d4f-107">**記事** 如果您在安裝 Microsoft BitLocker 管理和監控（MBAM）時選擇 Configuration Manager 拓撲，則會從 Configuration Manager 而不是從 MBAM 產生報告。</span><span class="sxs-lookup"><span data-stu-id="84d4f-107">**Note** If you chose the Configuration Manager topology when you installed Microsoft BitLocker Administration and Monitoring (MBAM), reports are generated from Configuration Manager rather than from MBAM.</span></span> <span data-ttu-id="84d4f-108">如需從 Configuration Manager 執行之報告的詳細資訊，請參閱[在 Configuration manager 中瞭解 MBAM 報告](understanding-mbam-reports-in-configuration-manager.md)。</span><span class="sxs-lookup"><span data-stu-id="84d4f-108">For more information about reports that are run from Configuration Manager, see [Understanding MBAM Reports in Configuration Manager](understanding-mbam-reports-in-configuration-manager.md).</span></span>

 

## <span data-ttu-id="84d4f-109">瞭解報表</span><span class="sxs-lookup"><span data-stu-id="84d4f-109">Understanding Reports</span></span>


<span data-ttu-id="84d4f-110">若要存取 Microsoft BitLocker 管理和監控的報告功能，請開啟網頁瀏覽器，然後開啟 [管理與監控] 網站。</span><span class="sxs-lookup"><span data-stu-id="84d4f-110">To access the Reports feature of Microsoft BitLocker Administration and Monitoring, open a web browser and open the Administration and Monitoring website.</span></span> <span data-ttu-id="84d4f-111">選取左側功能表列中的 [**報表**]，然後從頂端功能表列選取您要產生的報表類型。</span><span class="sxs-lookup"><span data-stu-id="84d4f-111">Select **Reports** in the left menu bar and then select from the top menu bar the kind of report that you want to generate.</span></span>

### <span data-ttu-id="84d4f-112">企業合規性報告</span><span class="sxs-lookup"><span data-stu-id="84d4f-112">Enterprise Compliance Report</span></span>

<span data-ttu-id="84d4f-113">使用此報告類型，收集貴組織中的整體 BitLocker 合規性的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="84d4f-113">Use this report type to collect information on overall BitLocker compliance in your organization.</span></span> <span data-ttu-id="84d4f-114">您可以使用不同的篩選，將搜尋結果縮小至合規性狀態和錯誤狀態。</span><span class="sxs-lookup"><span data-stu-id="84d4f-114">You can use different filters to narrow your search results to Compliance state and Error status.</span></span> <span data-ttu-id="84d4f-115">報告資訊每6小時更新一次。</span><span class="sxs-lookup"><span data-stu-id="84d4f-115">The report information is updated every six hours.</span></span>

**<span data-ttu-id="84d4f-116">企業合規性報告欄位</span><span class="sxs-lookup"><span data-stu-id="84d4f-116">Enterprise Compliance Report Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="84d4f-117">欄名稱</span><span class="sxs-lookup"><span data-stu-id="84d4f-117">Column Name</span></span></th>
<th align="left"><span data-ttu-id="84d4f-118">描述</span><span class="sxs-lookup"><span data-stu-id="84d4f-118">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="84d4f-119">電腦名稱稱</span><span class="sxs-lookup"><span data-stu-id="84d4f-119">Computer Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="84d4f-120">由 MBAM 管理的使用者指定的 DNS 名稱。</span><span class="sxs-lookup"><span data-stu-id="84d4f-120">User-specified DNS name that is being managed by MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="84d4f-121">網功能變數名稱稱</span><span class="sxs-lookup"><span data-stu-id="84d4f-121">Domain Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="84d4f-122">用戶端電腦所在的完整功能變數名稱，且由 MBAM 管理。</span><span class="sxs-lookup"><span data-stu-id="84d4f-122">Fully qualified domain name where the client computer resides and is managed by MBAM.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="84d4f-123">合規性狀態</span><span class="sxs-lookup"><span data-stu-id="84d4f-123">Compliance Status</span></span></p></td>
<td align="left"><p><span data-ttu-id="84d4f-124">根據電腦所指定的原則，為電腦提供符合的狀態。</span><span class="sxs-lookup"><span data-stu-id="84d4f-124">State of compliance for the computer, according to the policy specified for the computer.</span></span> <span data-ttu-id="84d4f-125">狀態是不相容且合規性。</span><span class="sxs-lookup"><span data-stu-id="84d4f-125">The states are Noncompliant and Compliant.</span></span> <span data-ttu-id="84d4f-126">如需有關如何解讀合規性狀態的詳細資訊，請參閱企業合規性報告合規性狀態資料表。</span><span class="sxs-lookup"><span data-stu-id="84d4f-126">See the Enterprise Compliance Report Compliance States table for more information about how to interpret compliance states.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="84d4f-127">合規性狀態詳細資料</span><span class="sxs-lookup"><span data-stu-id="84d4f-127">Compliance Status Details</span></span></p></td>
<td align="left"><p><span data-ttu-id="84d4f-128">根據指定原則，電腦符合性狀態的錯誤與狀態訊息。</span><span class="sxs-lookup"><span data-stu-id="84d4f-128">Error and status messages of the compliance state of the computer in accordance to the policy specified.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="84d4f-129">最後一個連絡人</span><span class="sxs-lookup"><span data-stu-id="84d4f-129">Last Contact</span></span></p></td>
<td align="left"><p><span data-ttu-id="84d4f-130">電腦上次與伺服器聯繫以報告合規性狀態的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="84d4f-130">Date and time when the computer last contacted the server to report compliance status.</span></span> <span data-ttu-id="84d4f-131">連絡人頻率可設定（請參閱 MBAM 原則設定）。</span><span class="sxs-lookup"><span data-stu-id="84d4f-131">The contact frequency is configurable (see MBAM policy settings).</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="84d4f-132">企業合規性報告合規性狀態</span><span class="sxs-lookup"><span data-stu-id="84d4f-132">Enterprise Compliance Report Compliance States</span></span>**

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="84d4f-133">合規性狀態</span><span class="sxs-lookup"><span data-stu-id="84d4f-133">Compliance Status</span></span></th>
<th align="left"><span data-ttu-id="84d4f-134">免除</span><span class="sxs-lookup"><span data-stu-id="84d4f-134">Exemption</span></span></th>
<th align="left"><span data-ttu-id="84d4f-135">描述</span><span class="sxs-lookup"><span data-stu-id="84d4f-135">Description</span></span></th>
<th align="left"><span data-ttu-id="84d4f-136">使用者動作</span><span class="sxs-lookup"><span data-stu-id="84d4f-136">User Action</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="84d4f-137">標準</span><span class="sxs-lookup"><span data-stu-id="84d4f-137">Noncompliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="84d4f-138">未免除</span><span class="sxs-lookup"><span data-stu-id="84d4f-138">Not Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="84d4f-139">根據指定的原則，電腦是不相容的。</span><span class="sxs-lookup"><span data-stu-id="84d4f-139">The computer is noncompliant, according to the specified policy.</span></span></p></td>
<td align="left"><p><span data-ttu-id="84d4f-140">按一下 [ <strong> 電腦名稱稱] </strong> ，並判斷每個磁片磁碟機的狀態是否符合指定原則，以展開電腦合規性報告詳細資料。</span><span class="sxs-lookup"><span data-stu-id="84d4f-140">Expand the Computer Compliance Report details by clicking <strong>Computer Name</strong>, and determine whether the state of each drive complies with the specified policy.</span></span> <span data-ttu-id="84d4f-141">如果加密狀態指出電腦未加密，可能正在進行加密，或電腦上出現錯誤。</span><span class="sxs-lookup"><span data-stu-id="84d4f-141">If the encryption state indicates that the computer is not encrypted, encryption may be in process, or there is an error on the computer.</span></span> <span data-ttu-id="84d4f-142">如果沒有錯誤，可能是因為電腦仍在連線或建立加密狀態的進程中。</span><span class="sxs-lookup"><span data-stu-id="84d4f-142">If there is no error, the likely cause is that the computer is still in the process of connecting or establishing the encryption status.</span></span> <span data-ttu-id="84d4f-143">稍後再次查看以判斷狀態是否變更。</span><span class="sxs-lookup"><span data-stu-id="84d4f-143">Check back later to determine if the state changes.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="84d4f-144">達到</span><span class="sxs-lookup"><span data-stu-id="84d4f-144">Compliant</span></span></p></td>
<td align="left"><p><span data-ttu-id="84d4f-145">未免除</span><span class="sxs-lookup"><span data-stu-id="84d4f-145">Not Exempt</span></span></p></td>
<td align="left"><p><span data-ttu-id="84d4f-146">根據指定的原則，電腦符合規範。</span><span class="sxs-lookup"><span data-stu-id="84d4f-146">The computer is compliant, according to the specified policy.</span></span></p></td>
<td align="left"><p><span data-ttu-id="84d4f-147">不需要任何動作;您可以透過查看電腦合規性報告來確認電腦的狀態。</span><span class="sxs-lookup"><span data-stu-id="84d4f-147">No action needed; the state of the computer can be confirmed by viewing the Computer Compliance Report.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="84d4f-148">電腦合規性報告</span><span class="sxs-lookup"><span data-stu-id="84d4f-148">Computer Compliance Report</span></span>

<span data-ttu-id="84d4f-149">使用此報告類型可收集電腦或使用者專用的資訊。</span><span class="sxs-lookup"><span data-stu-id="84d4f-149">Use this report type to collect information that is specific to a computer or user.</span></span>

<span data-ttu-id="84d4f-150">您可以按一下企業合規性報告中的電腦名稱稱，或在電腦合規性報告中輸入電腦名稱稱，以查看此報告。</span><span class="sxs-lookup"><span data-stu-id="84d4f-150">This report can be viewed by clicking the computer name in the Enterprise Compliance Report, or by typing the computer name in the Computer Compliance Report.</span></span> <span data-ttu-id="84d4f-151">電腦合規性報告提供電腦上每個磁片磁碟機（作業系統及固定資料磁碟機）的詳細加密資訊，以及針對電腦上的每個磁片磁碟機類型所套用的原則的指示。</span><span class="sxs-lookup"><span data-stu-id="84d4f-151">The Computer Compliance Report provides detailed encryption information about each drive (operating system and fixed data drives) on a computer, and also an indication of the policy that is applied to each drive type on the computer.</span></span> <span data-ttu-id="84d4f-152">若要查看每個磁片磁碟機的詳細資料，請展開 [電腦名稱稱] 專案。</span><span class="sxs-lookup"><span data-stu-id="84d4f-152">To view the details of each drive, expand the Computer Name entry.</span></span>

<span data-ttu-id="84d4f-153">**記事** 在報告中不會顯示 [可移動資料量] 加密狀態。</span><span class="sxs-lookup"><span data-stu-id="84d4f-153">**Note** Removable Data Volume encryption status will not be shown in the report.</span></span>

 

**<span data-ttu-id="84d4f-154">電腦合規性報告欄位</span><span class="sxs-lookup"><span data-stu-id="84d4f-154">Computer Compliance Report Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="84d4f-155">欄名稱</span><span class="sxs-lookup"><span data-stu-id="84d4f-155">Column Name</span></span></th>
<th align="left"><span data-ttu-id="84d4f-156">描述</span><span class="sxs-lookup"><span data-stu-id="84d4f-156">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="84d4f-157">電腦名稱稱</span><span class="sxs-lookup"><span data-stu-id="84d4f-157">Computer Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="84d4f-158">由 MBAM 管理的使用者指定 DNS 電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="84d4f-158">User-specified DNS computer name that is being managed by MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="84d4f-159">網功能變數名稱稱</span><span class="sxs-lookup"><span data-stu-id="84d4f-159">Domain Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="84d4f-160">用戶端電腦駐留且由 MBAM 管理的完整功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="84d4f-160">Fully qualified domain name, where the client computer resides and is managed by MBAM.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="84d4f-161">電腦類型</span><span class="sxs-lookup"><span data-stu-id="84d4f-161">Computer Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="84d4f-162">電腦類型。</span><span class="sxs-lookup"><span data-stu-id="84d4f-162">Type of computer.</span></span> <span data-ttu-id="84d4f-163">有效類型為非便攜且可移植。</span><span class="sxs-lookup"><span data-stu-id="84d4f-163">Valid types are non-Portable and Portable.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="84d4f-164">作業系統</span><span class="sxs-lookup"><span data-stu-id="84d4f-164">Operating System</span></span></p></td>
<td align="left"><p><span data-ttu-id="84d4f-165">在 MBAM 管理的用戶端電腦上找到的作業系統類型。</span><span class="sxs-lookup"><span data-stu-id="84d4f-165">Operating system type found on the MBAM-managed client computer.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="84d4f-166">合規性狀態</span><span class="sxs-lookup"><span data-stu-id="84d4f-166">Compliance Status</span></span></p></td>
<td align="left"><p><span data-ttu-id="84d4f-167">由 MBAM 管理之電腦的整體合規性狀態。</span><span class="sxs-lookup"><span data-stu-id="84d4f-167">Overall compliance status of the computer managed by MBAM.</span></span> <span data-ttu-id="84d4f-168">有效的狀態是相容且不相容。</span><span class="sxs-lookup"><span data-stu-id="84d4f-168">Valid states are Compliant and Noncompliant.</span></span> <span data-ttu-id="84d4f-169">請注意，每個磁片磁碟機的相容性狀態（請參閱下表）可能表示不同的合規性狀態。</span><span class="sxs-lookup"><span data-stu-id="84d4f-169">Notice that the compliance status per drive (see the following table) may indicate different compliance states.</span></span> <span data-ttu-id="84d4f-170">不過，這個欄位會根據指定的原則代表符合性狀態。</span><span class="sxs-lookup"><span data-stu-id="84d4f-170">However, this field represents that compliance state, according to the specified policy.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="84d4f-171">原則密碼強度</span><span class="sxs-lookup"><span data-stu-id="84d4f-171">Policy Cipher Strength</span></span></p></td>
<td align="left"><p><span data-ttu-id="84d4f-172">系統管理員在 MBAM 原則規格期間選取的密碼強度（例如，使用擴散器的128位）。</span><span class="sxs-lookup"><span data-stu-id="84d4f-172">Cipher strength selected by the administrator during MBAM policy specification (for example, 128-bit with Diffuser).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="84d4f-173">原則作業系統磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="84d4f-173">Policy Operating System Drive</span></span></p></td>
<td align="left"><p><span data-ttu-id="84d4f-174">表示作業系統是否需要加密，並顯示適當的保護器類型。</span><span class="sxs-lookup"><span data-stu-id="84d4f-174">Indicates if encryption is required for the operating system and shows the appropriate protector type.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="84d4f-175">原則-固定資料磁碟機</span><span class="sxs-lookup"><span data-stu-id="84d4f-175">Policy-Fixed Data Drive</span></span></p></td>
<td align="left"><p><span data-ttu-id="84d4f-176">表示固定資料磁碟機是否需要加密。</span><span class="sxs-lookup"><span data-stu-id="84d4f-176">Indicates if encryption is required for the fixed data drive.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="84d4f-177">策略移除資料磁碟機</span><span class="sxs-lookup"><span data-stu-id="84d4f-177">Policy Removable Data Drive</span></span></p></td>
<td align="left"><p><span data-ttu-id="84d4f-178">表示是否需要對移除磁片磁碟機進行加密。</span><span class="sxs-lookup"><span data-stu-id="84d4f-178">Indicates if encryption is required for the removable drive.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="84d4f-179">裝置使用者</span><span class="sxs-lookup"><span data-stu-id="84d4f-179">Device Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="84d4f-180">由 MBAM 管理的電腦上的已知使用者。</span><span class="sxs-lookup"><span data-stu-id="84d4f-180">Known users on the computer that is being managed by MBAM.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="84d4f-181">製造商</span><span class="sxs-lookup"><span data-stu-id="84d4f-181">Manufacturer</span></span></p></td>
<td align="left"><p><span data-ttu-id="84d4f-182">電腦製造商名稱，如電腦 BIOS 所示。</span><span class="sxs-lookup"><span data-stu-id="84d4f-182">Computer manufacturer name, as it appears in the computer BIOS.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="84d4f-183">型號</span><span class="sxs-lookup"><span data-stu-id="84d4f-183">Model</span></span></p></td>
<td align="left"><p><span data-ttu-id="84d4f-184">電腦製造商模型名稱，如電腦 BIOS 所示。</span><span class="sxs-lookup"><span data-stu-id="84d4f-184">Computer manufacturer model name, as it appears in the computer BIOS.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="84d4f-185">合規性狀態詳細資料</span><span class="sxs-lookup"><span data-stu-id="84d4f-185">Compliance Status Details</span></span></p></td>
<td align="left"><p><span data-ttu-id="84d4f-186">符合指定原則的電腦合規性狀態的錯誤與狀態訊息。</span><span class="sxs-lookup"><span data-stu-id="84d4f-186">Error and status messages of the compliance state of the computer, in accordance with the specified policy.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="84d4f-187">最後一個連絡人</span><span class="sxs-lookup"><span data-stu-id="84d4f-187">Last Contact</span></span></p></td>
<td align="left"><p><span data-ttu-id="84d4f-188">電腦上次取得伺服器以報告合規性狀態的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="84d4f-188">Date and time that the computer last contacted the server to report compliance status.</span></span> <span data-ttu-id="84d4f-189">連絡人頻率可設定（請參閱 MBAM 原則設定）。</span><span class="sxs-lookup"><span data-stu-id="84d4f-189">The contact frequency is configurable (see MBAM policy settings).</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="84d4f-190">電腦合規性報告磁片磁碟機欄位</span><span class="sxs-lookup"><span data-stu-id="84d4f-190">Computer Compliance Report Drive Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="84d4f-191">欄名稱</span><span class="sxs-lookup"><span data-stu-id="84d4f-191">Column Name</span></span></th>
<th align="left"><span data-ttu-id="84d4f-192">描述</span><span class="sxs-lookup"><span data-stu-id="84d4f-192">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="84d4f-193">磁片磁碟機盤符</span><span class="sxs-lookup"><span data-stu-id="84d4f-193">Drive Letter</span></span></p></td>
<td align="left"><p><span data-ttu-id="84d4f-194">使用者指派給特定磁片磁碟機的電腦磁碟機盤符。</span><span class="sxs-lookup"><span data-stu-id="84d4f-194">Computer drive letter that was assigned to the particular drive by the user.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="84d4f-195">磁片磁碟機類型</span><span class="sxs-lookup"><span data-stu-id="84d4f-195">Drive Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="84d4f-196">磁片磁碟機類型。</span><span class="sxs-lookup"><span data-stu-id="84d4f-196">Type of drive.</span></span> <span data-ttu-id="84d4f-197">有效值為作業系統磁片磁碟機及固定資料磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="84d4f-197">Valid values are Operating System Drive and Fixed Data Drive.</span></span> <span data-ttu-id="84d4f-198">這些是物理磁片磁碟機，而不是邏輯磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="84d4f-198">These are physical drives rather than logical volumes.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="84d4f-199">密碼強度</span><span class="sxs-lookup"><span data-stu-id="84d4f-199">Cipher Strength</span></span></p></td>
<td align="left"><p><span data-ttu-id="84d4f-200">管理員在 MBAM 原則規格期間選取的密碼強度。</span><span class="sxs-lookup"><span data-stu-id="84d4f-200">Cipher strength selected by the administrator during MBAM policy specification.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="84d4f-201">保護器類型</span><span class="sxs-lookup"><span data-stu-id="84d4f-201">Protector Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="84d4f-202">透過用來加密作業系統或固定資料量的原則所選取的保護者類型。</span><span class="sxs-lookup"><span data-stu-id="84d4f-202">Type of protector selected via the policy used to encrypt an operating system or fixed data volume.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="84d4f-203">保護器狀態</span><span class="sxs-lookup"><span data-stu-id="84d4f-203">Protector State</span></span></p></td>
<td align="left"><p><span data-ttu-id="84d4f-204">指示由 MBAM 管理的電腦已啟用原則中指定的保護器類型。</span><span class="sxs-lookup"><span data-stu-id="84d4f-204">Indicates that the computer being managed by MBAM has enabled the protector type that is specified in the policy.</span></span> <span data-ttu-id="84d4f-205">[有效] 狀態為 [開啟] 或 [關閉]。</span><span class="sxs-lookup"><span data-stu-id="84d4f-205">The valid states are ON or OFF.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="84d4f-206">加密狀態</span><span class="sxs-lookup"><span data-stu-id="84d4f-206">Encryption State</span></span></p></td>
<td align="left"><p><span data-ttu-id="84d4f-207">磁片磁碟機的加密狀態。</span><span class="sxs-lookup"><span data-stu-id="84d4f-207">Encryption state of the drive.</span></span> <span data-ttu-id="84d4f-208">有效的狀態為 [已加密]、[未加密] 和 [加密]。</span><span class="sxs-lookup"><span data-stu-id="84d4f-208">Valid states are Encrypted, Not Encrypted, and Encrypting.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="84d4f-209">合規性狀態</span><span class="sxs-lookup"><span data-stu-id="84d4f-209">Compliance Status</span></span></p></td>
<td align="left"><p><span data-ttu-id="84d4f-210">指出磁片磁碟機是否符合原則的狀態。</span><span class="sxs-lookup"><span data-stu-id="84d4f-210">State that indicates whether the drive is in accordance with the policy.</span></span> <span data-ttu-id="84d4f-211">狀態為不相容且合規性。</span><span class="sxs-lookup"><span data-stu-id="84d4f-211">States are Noncompliant and Compliant.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="84d4f-212">合規性狀態詳細資料</span><span class="sxs-lookup"><span data-stu-id="84d4f-212">Compliance Status Details</span></span></p></td>
<td align="left"><p><span data-ttu-id="84d4f-213">根據指定原則，電腦合規性狀態的錯誤與狀態訊息。</span><span class="sxs-lookup"><span data-stu-id="84d4f-213">Error and status messages of the compliance state of the computer, according to the specified policy.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="84d4f-214">復原審核報告</span><span class="sxs-lookup"><span data-stu-id="84d4f-214">Recovery Audit Report</span></span>

<span data-ttu-id="84d4f-215">使用此報告類型來審核已要求存取復原金鑰的使用者。</span><span class="sxs-lookup"><span data-stu-id="84d4f-215">Use this report type to audit users who have requested access to recovery keys.</span></span> <span data-ttu-id="84d4f-216">報告根據所需的篩選準則提供數個篩選。</span><span class="sxs-lookup"><span data-stu-id="84d4f-216">The report offers several filters based on the desired filtering criteria.</span></span> <span data-ttu-id="84d4f-217">使用者可以篩選特定類型的使用者（無論是技術支援人員的使用者或使用者）、要求失敗或已成功、所要求的特定金鑰類型，以及發生檢索的日期範圍。</span><span class="sxs-lookup"><span data-stu-id="84d4f-217">Users can filter on a specific type of user, either a Help Desk user or an end user, whether the request failed or was successful, the specific type of key requested, and a date range during which the retrieval occurred.</span></span> <span data-ttu-id="84d4f-218">系統管理員可以根據需要產生相關的報告。</span><span class="sxs-lookup"><span data-stu-id="84d4f-218">The administrator can produce contextual reports based on need.</span></span>

**<span data-ttu-id="84d4f-219">復原審核報告欄位</span><span class="sxs-lookup"><span data-stu-id="84d4f-219">Recovery Audit Report Fields</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="84d4f-220">欄名稱</span><span class="sxs-lookup"><span data-stu-id="84d4f-220">Column Name</span></span></th>
<th align="left"><span data-ttu-id="84d4f-221">描述</span><span class="sxs-lookup"><span data-stu-id="84d4f-221">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="84d4f-222">要求日期和時間</span><span class="sxs-lookup"><span data-stu-id="84d4f-222">Request Date and Time</span></span></p></td>
<td align="left"><p><span data-ttu-id="84d4f-223">由最終使用者或技術支援人員使用者所做的金鑰檢索要求的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="84d4f-223">Date and time that a key retrieval request was made by an end user or Help Desk user.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="84d4f-224">要求狀態</span><span class="sxs-lookup"><span data-stu-id="84d4f-224">Request Status</span></span></p></td>
<td align="left"><p><span data-ttu-id="84d4f-225">要求的狀態。</span><span class="sxs-lookup"><span data-stu-id="84d4f-225">Status of the request.</span></span> <span data-ttu-id="84d4f-226">有效狀態為 [成功] （已檢索到金鑰），或失敗（未檢索到金鑰）。</span><span class="sxs-lookup"><span data-stu-id="84d4f-226">Valid statuses are either Successful (the key was retrieved), or Failed (the key was not retrieved).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="84d4f-227">支援人員的使用者</span><span class="sxs-lookup"><span data-stu-id="84d4f-227">Helpdesk User</span></span></p></td>
<td align="left"><p><span data-ttu-id="84d4f-228">已啟動金鑰檢索要求的技術支援使用者。</span><span class="sxs-lookup"><span data-stu-id="84d4f-228">Help Desk user that initiated the request for key retrieval.</span></span> <span data-ttu-id="84d4f-229">注意：如果技術支援人員的使用者是代表最終使用者來檢索索引鍵，則 [使用者] 欄位會是空白的。</span><span class="sxs-lookup"><span data-stu-id="84d4f-229">Note: If the Help Desk user retrieves the key on behalf on an end-user, the End User field will be blank.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="84d4f-230">使用者</span><span class="sxs-lookup"><span data-stu-id="84d4f-230">User</span></span></p></td>
<td align="left"><p><span data-ttu-id="84d4f-231">已啟動金鑰取回要求的使用者。</span><span class="sxs-lookup"><span data-stu-id="84d4f-231">End user who initiated the request for key retrieval.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="84d4f-232">金鑰類型</span><span class="sxs-lookup"><span data-stu-id="84d4f-232">Key Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="84d4f-233">技術支援人員使用者或使用者所要求的金鑰類型。</span><span class="sxs-lookup"><span data-stu-id="84d4f-233">Type of key that was requested by either the Help Desk user or the end user.</span></span> <span data-ttu-id="84d4f-234">MBAM 收集的三種金鑰類型有：復原金鑰密碼（用來在復原模式中復原電腦）、復原金鑰識別碼（用來以其他使用者的復原模式復原電腦），以及 TPM 密碼雜湊（用來復原已鎖定的 TPM 的電腦）。</span><span class="sxs-lookup"><span data-stu-id="84d4f-234">The three types of keys that MBAM collects are: Recovery Key Password (used to recovery a computer in recovery mode), Recovery Key ID (used to recover a computer in recovery mode on behalf of another user), and TPM Password Hash (used to recover a computer with a locked TPM).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="84d4f-235">原因描述</span><span class="sxs-lookup"><span data-stu-id="84d4f-235">Reason Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="84d4f-236">說明： [技術支援人員] 使用者或 [最終使用者] 要求指定的金鑰類型。</span><span class="sxs-lookup"><span data-stu-id="84d4f-236">Reason the specified Key Type was requested by the Help Desk user or the end user.</span></span> <span data-ttu-id="84d4f-237">原因是在 [磁片磁碟機復原] 和 [管理及監視] 網站的 TPM 功能中指定。</span><span class="sxs-lookup"><span data-stu-id="84d4f-237">The reasons are specified in the Drive Recovery and Manage TPM features of the Administration and Monitoring website.</span></span> <span data-ttu-id="84d4f-238">有效的專案為使用者輸入的文字，或下列其中一個原因代碼：</span><span class="sxs-lookup"><span data-stu-id="84d4f-238">The valid entries are either user-entered text, or one of the following reason codes:</span></span></p>
<ul>
<li><p><span data-ttu-id="84d4f-239">作業系統啟動順序已變更</span><span class="sxs-lookup"><span data-stu-id="84d4f-239">Operating System Boot Order changed</span></span></p></li>
<li><p><span data-ttu-id="84d4f-240">BIOS 已變更</span><span class="sxs-lookup"><span data-stu-id="84d4f-240">BIOS Changed</span></span></p></li>
<li><p><span data-ttu-id="84d4f-241">已變更作業系統檔案</span><span class="sxs-lookup"><span data-stu-id="84d4f-241">Operating System files changed</span></span></p></li>
<li><p><span data-ttu-id="84d4f-242">遺失的啟動金鑰</span><span class="sxs-lookup"><span data-stu-id="84d4f-242">Lost Startup key</span></span></p></li>
<li><p><span data-ttu-id="84d4f-243">遺失的 PIN</span><span class="sxs-lookup"><span data-stu-id="84d4f-243">Lost PIN</span></span></p></li>
<li><p><span data-ttu-id="84d4f-244">TPM 重設</span><span class="sxs-lookup"><span data-stu-id="84d4f-244">TPM Reset</span></span></p></li>
<li><p><span data-ttu-id="84d4f-245">遺失密碼</span><span class="sxs-lookup"><span data-stu-id="84d4f-245">Lost Passphrase</span></span></p></li>
<li><p><span data-ttu-id="84d4f-246">遺失的智慧卡</span><span class="sxs-lookup"><span data-stu-id="84d4f-246">Lost Smartcard</span></span></p></li>
<li><p><span data-ttu-id="84d4f-247">重設 PIN 鎖定</span><span class="sxs-lookup"><span data-stu-id="84d4f-247">Reset PIN lockout</span></span></p></li>
<li><p><span data-ttu-id="84d4f-248">開啟 TPM</span><span class="sxs-lookup"><span data-stu-id="84d4f-248">Turn on TPM</span></span></p></li>
<li><p><span data-ttu-id="84d4f-249">關閉 TPM</span><span class="sxs-lookup"><span data-stu-id="84d4f-249">Turn off TPM</span></span></p></li>
<li><p><span data-ttu-id="84d4f-250">變更 TPM 密碼</span><span class="sxs-lookup"><span data-stu-id="84d4f-250">Change TPM password</span></span></p></li>
<li><p><span data-ttu-id="84d4f-251">清除 TPM</span><span class="sxs-lookup"><span data-stu-id="84d4f-251">Clear TPM</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="84d4f-252">**記事** 您可以按一下 [報表] 功能表列上的 [**匯出**] 按鈕，將報告結果儲存至檔案。</span><span class="sxs-lookup"><span data-stu-id="84d4f-252">**Note** Report results can be saved to a file by clicking the **Export** button on the reports menu bar.</span></span> <span data-ttu-id="84d4f-253">如需如何執行 MBAM 報告的詳細資訊，請參閱[如何產生 MBAM 報告](how-to-generate-mbam-reports-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="84d4f-253">For more information about how to run MBAM reports, see [How to Generate MBAM Reports](how-to-generate-mbam-reports-mbam-2.md).</span></span>

 

## <span data-ttu-id="84d4f-254">相關主題</span><span class="sxs-lookup"><span data-stu-id="84d4f-254">Related topics</span></span>


[<span data-ttu-id="84d4f-255">使用 MBAM 2.0 監視與報告 BitLocker 符合性</span><span class="sxs-lookup"><span data-stu-id="84d4f-255">Monitoring and Reporting BitLocker Compliance with MBAM 2.0</span></span>](monitoring-and-reporting-bitlocker-compliance-with-mbam-20-mbam-2.md)

 

 





