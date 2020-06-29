---
title: Application Virtualization 5.0 的效能指引
description: Application Virtualization 5.0 的效能指引
author: dansimp
ms.assetid: 6b3a3255-b957-4b9b-8bfc-a93fe8438a81
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 3b0f5ef07935fc34adce772e7b2fff85a12b01dc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800368"
---
# <span data-ttu-id="5efd5-103">Application Virtualization 5.0 的效能指引</span><span class="sxs-lookup"><span data-stu-id="5efd5-103">Performance Guidance for Application Virtualization 5.0</span></span>


<span data-ttu-id="5efd5-104">瞭解如何設定 App-V 5.0 以取得最佳效能、優化虛擬 App 套件，以及使用 RDS 和 VDI 提供較佳的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="5efd5-104">Learn how to configure App-V 5.0 for optimal performance, optimize virtual app packages, and provide a better user experience with RDS and VDI.</span></span>

<span data-ttu-id="5efd5-105">實現多個方法可協助您改善最終使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="5efd5-105">Implementing multiple methods can help you improve the end-user experience.</span></span> <span data-ttu-id="5efd5-106">不過，您的環境可能不支援所有方法。</span><span class="sxs-lookup"><span data-stu-id="5efd5-106">However, your environment may not support all methods.</span></span>

<span data-ttu-id="5efd5-107">閱讀此檔之前，您應該閱讀並瞭解下列資訊。</span><span class="sxs-lookup"><span data-stu-id="5efd5-107">You should read and understand the following information before reading this document.</span></span>

-   [<span data-ttu-id="5efd5-108">Microsoft Application Virtualization 5.0 系統管理員指南</span><span class="sxs-lookup"><span data-stu-id="5efd5-108">Microsoft Application Virtualization 5.0 Administrator's Guide</span></span>](microsoft-application-virtualization-50-administrators-guide.md)

-   [<span data-ttu-id="5efd5-109">App-v 5 SP2 應用程式發佈與用戶端互動</span><span class="sxs-lookup"><span data-stu-id="5efd5-109">App-V 5 SP2 Application Publishing and Client Interaction</span></span>](https://go.microsoft.com/fwlink/?LinkId=395206)

-   [<span data-ttu-id="5efd5-110">Microsoft Application Virtualization 5.0 排序指南</span><span class="sxs-lookup"><span data-stu-id="5efd5-110">Microsoft Application Virtualization 5.0 Sequencing Guide</span></span>](https://go.microsoft.com/fwlink/?LinkId=269953)

**<span data-ttu-id="5efd5-111">注意</span><span class="sxs-lookup"><span data-stu-id="5efd5-111">Note</span></span>**  
<span data-ttu-id="5efd5-112">根據外部來源和內容，此檔中使用的一些字詞可能會有不同的含義。</span><span class="sxs-lookup"><span data-stu-id="5efd5-112">Some terms used in this document may have different meanings depending on external source and context.</span></span> <span data-ttu-id="5efd5-113">如需本檔中所使用之術語的詳細資訊，後面加上星號 **\\** \* 請參閱本檔的[Application Virtualization 效能指南術語](#bkmk-terms1)一節。</span><span class="sxs-lookup"><span data-stu-id="5efd5-113">For more information about terms used in this document followed by an asterisk **\\**\* review the [Application Virtualization Performance Guidance Terminology](#bkmk-terms1) section of this document.</span></span>



<span data-ttu-id="5efd5-114">最後，本檔將提供資訊來設定執行 App-v 5.0 用戶端的電腦，以及最佳效能。</span><span class="sxs-lookup"><span data-stu-id="5efd5-114">Finally, this document will provide you with the information to configure the computer running App-V 5.0 client and the environment for optimal performance.</span></span> <span data-ttu-id="5efd5-115">使用 sequencer 來優化您的虛擬應用程式套件，並瞭解如何使用使用者體驗虛擬化（UE-V）或其他使用者環境管理技術，以在遠端桌面服務（RDS）和非持久性虛擬桌面基礎結構（VDI）中使用 App-v 5.0 提供最佳的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="5efd5-115">Optimize your virtual application packages for performance using the sequencer, and to understand how to use User Experience Virtualization (UE-V) or other user environment management technologies to provide the optimal user experience with App-V 5.0 in both Remote Desktop Services (RDS) and non-persistent virtual desktop infrastructure (VDI).</span></span>

<span data-ttu-id="5efd5-116">若要協助判斷與您的環境相關的資訊，您應該查看每個區段的簡短概述及適用性檢查清單。</span><span class="sxs-lookup"><span data-stu-id="5efd5-116">To help determine what information is relevant to your environment you should review each section’s brief overview and applicability checklist.</span></span>

## <a href="" id="---------app-v-5-0-in-stateful--non-persistent-deployments"></a> <span data-ttu-id="5efd5-117">在狀態 \ \* 非持續性部署中的 app-v 5。0</span><span class="sxs-lookup"><span data-stu-id="5efd5-117">App-V 5.0 in stateful\* non-persistent deployments</span></span>


<span data-ttu-id="5efd5-118">本節提供一種方法的相關資訊，協助確保使用者在登入後的幾秒鐘內就能存取所有的虛擬應用程式。</span><span class="sxs-lookup"><span data-stu-id="5efd5-118">This section provides information about an approach that helps ensure a user will have access to all virtual applications within seconds after logging in.</span></span> <span data-ttu-id="5efd5-119">如此一來，就能以唯一的方式來解決經常執行的 App-v 5.0 發佈重新整理。</span><span class="sxs-lookup"><span data-stu-id="5efd5-119">This is achieved by uniquely addressing the often long-running App-V 5.0 publishing refresh.</span></span> <span data-ttu-id="5efd5-120">您會發現此方法的基礎，這是最快的發佈重新整理，就是不需要實際執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="5efd5-120">As you will discover the basis of the approach, the fastest publishing refresh, is one that doesn’t have to actually do anything.</span></span> <span data-ttu-id="5efd5-121">必須符合幾個條件，並遵循步驟來提供最佳的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="5efd5-121">A number of conditions must be met and steps followed to provide the optimal user experience.</span></span>

<span data-ttu-id="5efd5-122">如需詳細資訊，請使用下一節中的資訊：</span><span class="sxs-lookup"><span data-stu-id="5efd5-122">Use the information in the following section for more information:</span></span>

<span data-ttu-id="5efd5-123">[使用案例](#bkmk-us)-當您查看兩種情況時，請記住這些是最極端的方法。</span><span class="sxs-lookup"><span data-stu-id="5efd5-123">[Usage Scenarios](#bkmk-us) - As you review the two scenarios, keep in mind that these are the approach extremes.</span></span> <span data-ttu-id="5efd5-124">根據您的使用需求，您可以選擇將這些步驟套用至使用者和/或虛擬應用程式套件的子集。</span><span class="sxs-lookup"><span data-stu-id="5efd5-124">Based on your usage requirements, you may choose to apply these steps to a subset of users and/or virtual applications packages.</span></span>

-   <span data-ttu-id="5efd5-125">針對效能優化-若要提供最佳的體驗，您可以預期基本影像包含部分 App-v 虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="5efd5-125">Optimized for Performance – To provide the optimal experience, you can expect the base image to include some of the App-V virtual application package.</span></span> <span data-ttu-id="5efd5-126">本文將討論這及其他需求。</span><span class="sxs-lookup"><span data-stu-id="5efd5-126">This and other requirements are discussed.</span></span>

-   <span data-ttu-id="5efd5-127">針對儲存進行優化-如果您關心儲存空間的影響，請遵循這個案例將協助解決這些問題。</span><span class="sxs-lookup"><span data-stu-id="5efd5-127">Optimized for Storage – If you are concerned with the storage impact, following this scenario will help address those concerns.</span></span>

[<span data-ttu-id="5efd5-128">準備您的環境</span><span class="sxs-lookup"><span data-stu-id="5efd5-128">Preparing your Environment</span></span>](#bkmk-pe)

-   <span data-ttu-id="5efd5-129">準備基本映射的步驟（無論是在非持久性 VDI 或 RDSH 環境中），基本映射中必須完成幾個步驟，才能啟用此方法。</span><span class="sxs-lookup"><span data-stu-id="5efd5-129">Steps to Prepare the Base Image – Whether in a non-persistent VDI or RDSH environment, only a few steps must be completed in the base image to enable this approach.</span></span>

-   <span data-ttu-id="5efd5-130">使用 UE-V 2.0 做為應用程式 V 方法的使用者設定檔管理（UPM）方案–這種方法的基礎是 UEM 解決方案只保留幾個註冊表和檔案位置的內容的能力。</span><span class="sxs-lookup"><span data-stu-id="5efd5-130">Use UE-V 2.0 as the User Profile Management (UPM) solution for the App-V approach – the cornerstone of this approach is the ability of a UEM solution to persist the contents of just a few registry and file locations.</span></span> <span data-ttu-id="5efd5-131">這些位置組成使用者整合 \ \*。</span><span class="sxs-lookup"><span data-stu-id="5efd5-131">These locations constitute the user integrations\*.</span></span> <span data-ttu-id="5efd5-132">請務必審查 UPM 方案的特定需求。</span><span class="sxs-lookup"><span data-stu-id="5efd5-132">Be sure to review the specific requirements for the UPM solution.</span></span>

[<span data-ttu-id="5efd5-133">使用者體驗逐步指導</span><span class="sxs-lookup"><span data-stu-id="5efd5-133">User Experience Walk-through</span></span>](#bkmk-uewt)

-   <span data-ttu-id="5efd5-134">逐步引導–這是 App V 與 UE-V 作業的逐步逐步引導，以及使用者應該擁有的預期。</span><span class="sxs-lookup"><span data-stu-id="5efd5-134">Walk-through – This is a step-by-step walk-through of the App-V and UE-V operations and the expectations users should have.</span></span>

-   <span data-ttu-id="5efd5-135">結果–這會說明預期的結果。</span><span class="sxs-lookup"><span data-stu-id="5efd5-135">Outcome – This describes the expected results.</span></span>

[<span data-ttu-id="5efd5-136">對套件生命週期的影響</span><span class="sxs-lookup"><span data-stu-id="5efd5-136">Impact to Package Lifecycle</span></span>](#bkmk-plc)

[<span data-ttu-id="5efd5-137">透過效能優化/調整來加強 VDI 體驗</span><span class="sxs-lookup"><span data-stu-id="5efd5-137">Enhancing the VDI Experience through Performance Optimization/Tuning</span></span>](#bkmk-evdi)

### <a href="" id="applicability-checklist-"></a><span data-ttu-id="5efd5-138">適用性檢查清單</span><span class="sxs-lookup"><span data-stu-id="5efd5-138">Applicability Checklist</span></span>

<span data-ttu-id="5efd5-139">部署環境</span><span class="sxs-lookup"><span data-stu-id="5efd5-139">Deployment Environment</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="5efd5-140">非持久性 VDI 或 RDSH。</span><span class="sxs-lookup"><span data-stu-id="5efd5-140">Non-Persistent VDI or RDSH.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="5efd5-141">使用者體驗虛擬化（UE-V）、其他 UPM 解決方案或使用者設定檔磁片（UPD）。</span><span class="sxs-lookup"><span data-stu-id="5efd5-141">User Experience Virtualization (UE-V), other UPM solutions or User Profile Disks (UPD).</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="5efd5-142">預期配置</span><span class="sxs-lookup"><span data-stu-id="5efd5-142">Expected Configuration</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="5efd5-143">使用者體驗虛擬化（UE-V），其中已啟用 App-v 使用者狀態範本或使用者設定檔管理（UPM）軟體。</span><span class="sxs-lookup"><span data-stu-id="5efd5-143">User Experience Virtualization (UE-V) with the App-V user state template enabled or User Profile Management (UPM) software.</span></span> <span data-ttu-id="5efd5-144">非 UE-V UPM 軟體必須能夠在登入或處理/應用程式啟動和登出時觸發。</span><span class="sxs-lookup"><span data-stu-id="5efd5-144">Non-UE-V UPM software must be capable of triggering on Login or Process/Application Start and Logoff.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="5efd5-145">App-V 共用的內容存儲區（SCS）已設定或可設定。</span><span class="sxs-lookup"><span data-stu-id="5efd5-145">App-V Shared Content Store (SCS) is configured or can be configured.</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="5efd5-146">IT 管理</span><span class="sxs-lookup"><span data-stu-id="5efd5-146">IT Administration</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="5efd5-147">系統管理員可能需要定期更新 VM 基本影像，以確保最佳效能或系統管理員可能需要管理不同使用者群組的多個影像。</span><span class="sxs-lookup"><span data-stu-id="5efd5-147">Admin may need to update the VM base image regularly to ensure optimal performance or Admin may need to manage multiple images for different user groups.</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-us"></a><span data-ttu-id="5efd5-148">使用案例</span><span class="sxs-lookup"><span data-stu-id="5efd5-148">Usage Scenario</span></span>

<span data-ttu-id="5efd5-149">當您複習這兩種情況時，請記住，這些是最極端的做法。</span><span class="sxs-lookup"><span data-stu-id="5efd5-149">As you review the two scenarios, keep in mind that these approach the extremes.</span></span> <span data-ttu-id="5efd5-150">根據您的使用需求，您可以選擇將這些步驟套用到使用者的子集、虛擬應用程式套件，或兩者。</span><span class="sxs-lookup"><span data-stu-id="5efd5-150">Based on your usage requirements, you may choose to apply these steps to a subset of users, virtual application packages, or both.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5efd5-151">針對效能優化</span><span class="sxs-lookup"><span data-stu-id="5efd5-151">Optimized for Performance</span></span></th>
<th align="left"><span data-ttu-id="5efd5-152">針對儲存進行優化</span><span class="sxs-lookup"><span data-stu-id="5efd5-152">Optimized for Storage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5efd5-153">為了提供最佳的使用者體驗，此方法會利用 UPM 方案的功能，而且需要額外的影像管理額外負荷。</span><span class="sxs-lookup"><span data-stu-id="5efd5-153">To provide the most optimal user experience, this approach leverages the capabilities of a UPM solution and requires additional image preparation and can incur some additional image management overhead.</span></span></p>
<p><span data-ttu-id="5efd5-154">下列說明在狀態非持續性部署中的許多效能改善。</span><span class="sxs-lookup"><span data-stu-id="5efd5-154">The following describes many performance improvements in stateful non-persistent deployments.</span></span> <span data-ttu-id="5efd5-155">如需詳細資訊，請參閱 <strong> 此檔的 [請參閱] 區段中的 [針對發佈效能優化套件的先後順序步驟 </strong> 和 <strong> App-V 5.0 排序指南] </strong> <strong> 一節 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="5efd5-155">For more information, see the <strong>Sequencing Steps to Optimize Packages for Publishing Performance</strong> and reference to <strong>App-V 5.0 Sequencing Guide</strong> in the <strong>See Also section of this document</strong>.</span></span></p></td>
<td align="left"><p><span data-ttu-id="5efd5-156">上述案例的一般預期仍會適用于這裡。</span><span class="sxs-lookup"><span data-stu-id="5efd5-156">The general expectations of the previous scenario still apply here.</span></span> <span data-ttu-id="5efd5-157">不過，請記住，VM 影像通常會儲存在非常昂貴的陣列中;已對此方法進行一些輕微的變更。</span><span class="sxs-lookup"><span data-stu-id="5efd5-157">However, keep in mind that VM images are typically stored in very costly arrays; a slight alteration has been made to the approach.</span></span> <span data-ttu-id="5efd5-158">請勿在基本影像中預先設定以使用者為目標的虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="5efd5-158">Do not pre-configure user-targeted virtual application packages in the base image.</span></span></p>
<p><span data-ttu-id="5efd5-159">這項變更的影響將在這份檔的 [使用者經驗] 演練一節中詳細說明。</span><span class="sxs-lookup"><span data-stu-id="5efd5-159">The impact of this alteration is detailed in the User Experience Walkthrough section of this document.</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-pe"></a><span data-ttu-id="5efd5-160">準備您的環境</span><span class="sxs-lookup"><span data-stu-id="5efd5-160">Preparing your Environment</span></span>

<span data-ttu-id="5efd5-161">下表顯示準備基本映射與 UE-V 或該方法的其他 UPM 方案所需的步驟。</span><span class="sxs-lookup"><span data-stu-id="5efd5-161">The following table displays the required steps to prepare the base image and the UE-V or another UPM solution for the approach.</span></span>

**<span data-ttu-id="5efd5-162">準備基底影像</span><span class="sxs-lookup"><span data-stu-id="5efd5-162">Prepare the Base Image</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5efd5-163">針對效能優化</span><span class="sxs-lookup"><span data-stu-id="5efd5-163">Optimized for Performance</span></span></th>
<th align="left"><span data-ttu-id="5efd5-164">針對儲存進行優化</span><span class="sxs-lookup"><span data-stu-id="5efd5-164">Optimized for Storage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="5efd5-165">針對應用程式虛擬化 5.0 SP2 用戶端版本安裝修補程式套件4。</span><span class="sxs-lookup"><span data-stu-id="5efd5-165">Install the Hotfix Package 4 for Application Virtualization 5.0 SP2 client version of the client.</span></span></p></li>
<li><p><span data-ttu-id="5efd5-166">安裝 UE-V，然後從 UE-V 範本庫下載 App-v 設定範本，請參閱下列步驟。</span><span class="sxs-lookup"><span data-stu-id="5efd5-166">Install UE-V and download the App-V Settings Template from the UE-V template Gallery, see the following steps.</span></span></p></li>
<li><p><span data-ttu-id="5efd5-167">針對共用內容儲存區（SCS）模式進行設定。</span><span class="sxs-lookup"><span data-stu-id="5efd5-167">Configure for Shared Content Store (SCS) mode.</span></span> <span data-ttu-id="5efd5-168">如需詳細資訊，請參閱 <a href="how-to-install-the-app-v-50-client-for-shared-content-store-mode.md" data-raw-source="[How to Install the App-V 5.0 Client for Shared Content Store Mode](how-to-install-the-app-v-50-client-for-shared-content-store-mode.md)"> 如何安裝 App-V 5.0 用戶端以取得共用內容存放區模式 </a> 。</span><span class="sxs-lookup"><span data-stu-id="5efd5-168">For more information see <a href="how-to-install-the-app-v-50-client-for-shared-content-store-mode.md" data-raw-source="[How to Install the App-V 5.0 Client for Shared Content Store Mode](how-to-install-the-app-v-50-client-for-shared-content-store-mode.md)">How to Install the App-V 5.0 Client for Shared Content Store Mode</a>.</span></span></p></li>
<li><p><span data-ttu-id="5efd5-169">設定 [在登入登錄註冊表中保留使用者整合] DWORD。</span><span class="sxs-lookup"><span data-stu-id="5efd5-169">Configure Preserve User Integrations on Login Registry DWORD.</span></span></p></li>
<li><p><span data-ttu-id="5efd5-170">預先設定所有的使用者和全域目標套件（例如， <strong> 附加 AppvClientPackage） </strong> 。</span><span class="sxs-lookup"><span data-stu-id="5efd5-170">Pre-configure all user- and global-targeted packages for example, <strong>Add-AppvClientPackage</strong>.</span></span></p></li>
<li><p><span data-ttu-id="5efd5-171">預先設定所有使用者和全域目標連線群組（例如， <strong> 附加 AppvClientConnectionGroup） </strong> 。</span><span class="sxs-lookup"><span data-stu-id="5efd5-171">Pre-configure all user- and global-targeted connection groups for example, <strong>Add-AppvClientConnectionGroup</strong>.</span></span></p></li>
<li><p><span data-ttu-id="5efd5-172">預先發佈所有全域目標套件。</span><span class="sxs-lookup"><span data-stu-id="5efd5-172">Pre-publish all global-targeted packages.</span></span></p>
<p></p>
<p><span data-ttu-id="5efd5-173">當然</span><span class="sxs-lookup"><span data-stu-id="5efd5-173">Alternatively,</span></span></p>
<ul>
<li><p><span data-ttu-id="5efd5-174">執行全域發佈/重新整理。</span><span class="sxs-lookup"><span data-stu-id="5efd5-174">Perform a global publishing/refresh.</span></span></p></li>
<li><p><span data-ttu-id="5efd5-175">執行使用者發佈/重新整理。</span><span class="sxs-lookup"><span data-stu-id="5efd5-175">Perform a user publishing/refresh.</span></span></p></li>
<li><p><span data-ttu-id="5efd5-176">取消發佈所有以使用者為目標的套件。</span><span class="sxs-lookup"><span data-stu-id="5efd5-176">Un-publish all user-targeted packages.</span></span></p></li>
<li><p><span data-ttu-id="5efd5-177">刪除下列使用者虛擬檔案系統（VFS）專案。</span><span class="sxs-lookup"><span data-stu-id="5efd5-177">Delete the following user-Virtual File System (VFS) entries.</span></span></p></li>
</ul>
<p><code>AppData\Local\Microsoft\AppV\Client\VFS</code></p>
<p><code>AppData\Roaming\Microsoft\AppV\Client\VFS</code></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="5efd5-178">針對應用程式虛擬化 5.0 SP2 用戶端版本安裝修補程式套件4。</span><span class="sxs-lookup"><span data-stu-id="5efd5-178">Install the Hotfix Package 4 for Application Virtualization 5.0 SP2 client version of the client.</span></span></p></li>
<li><p><span data-ttu-id="5efd5-179">安裝 UE-V，然後從 UE-V 範本庫下載 App-v 設定範本，請參閱下列步驟。</span><span class="sxs-lookup"><span data-stu-id="5efd5-179">Install UE-V and download the App-V Settings Template from the UE-V template Gallery, see the following steps.</span></span></p></li>
<li><p><span data-ttu-id="5efd5-180">針對共用內容儲存區（SCS）模式進行設定。</span><span class="sxs-lookup"><span data-stu-id="5efd5-180">Configure for Shared Content Store (SCS) mode.</span></span> <span data-ttu-id="5efd5-181">如需詳細資訊，請參閱 <a href="how-to-install-the-app-v-50-client-for-shared-content-store-mode.md" data-raw-source="[How to Install the App-V 5.0 Client for Shared Content Store Mode](how-to-install-the-app-v-50-client-for-shared-content-store-mode.md)"> 如何安裝 App-V 5.0 用戶端以取得共用內容存放區模式 </a> 。</span><span class="sxs-lookup"><span data-stu-id="5efd5-181">For more information see <a href="how-to-install-the-app-v-50-client-for-shared-content-store-mode.md" data-raw-source="[How to Install the App-V 5.0 Client for Shared Content Store Mode](how-to-install-the-app-v-50-client-for-shared-content-store-mode.md)">How to Install the App-V 5.0 Client for Shared Content Store Mode</a>.</span></span></p></li>
<li><p><span data-ttu-id="5efd5-182">設定 [在登入登錄註冊表中保留使用者整合] DWORD。</span><span class="sxs-lookup"><span data-stu-id="5efd5-182">Configure Preserve User Integrations on Login Registry DWORD.</span></span></p></li>
<li><p><span data-ttu-id="5efd5-183">預先設定所有全域目標套件（例如， <strong> 附加 AppvClientPackage） </strong> 。</span><span class="sxs-lookup"><span data-stu-id="5efd5-183">Pre-configure all global-targeted packages for example, <strong>Add-AppvClientPackage</strong>.</span></span></p></li>
<li><p><span data-ttu-id="5efd5-184">預先設定所有全域目標連線群組（例如， <strong> 附加 AppvClientConnectionGroup） </strong> 。</span><span class="sxs-lookup"><span data-stu-id="5efd5-184">Pre-configure all global-targeted connection groups for example, <strong>Add-AppvClientConnectionGroup</strong>.</span></span></p></li>
<li><p><span data-ttu-id="5efd5-185">預先發佈所有全域目標套件。</span><span class="sxs-lookup"><span data-stu-id="5efd5-185">Pre-publish all global-targeted packages.</span></span></p>
<p></p></li>
</ul></td>
</tr>
</tbody>
</table>



<span data-ttu-id="5efd5-186">**配置**-適用于重要的 App-v 用戶端設定，若想要更多內容和操作說明，請參閱下列資訊：</span><span class="sxs-lookup"><span data-stu-id="5efd5-186">**Configurations** - For critical App-V Client configurations and for a little more context and how-to, review the following information:</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5efd5-187">配置設定</span><span class="sxs-lookup"><span data-stu-id="5efd5-187">Configuration Setting</span></span></th>
<th align="left"><span data-ttu-id="5efd5-188">這會有什麼作用？</span><span class="sxs-lookup"><span data-stu-id="5efd5-188">What does this do?</span></span></th>
<th align="left"><span data-ttu-id="5efd5-189">我該如何使用它？</span><span class="sxs-lookup"><span data-stu-id="5efd5-189">How should I use it?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5efd5-190">共用內容存放區（SCS）模式</span><span class="sxs-lookup"><span data-stu-id="5efd5-190">Shared Content Store (SCS) Mode</span></span></p>
<ul>
<li><p><span data-ttu-id="5efd5-191">可在 PowerShell 中使用 <strong> AppvClientConfiguration </strong> -SharedContentStoreMode <strong> 設定 </strong> ，或</span><span class="sxs-lookup"><span data-stu-id="5efd5-191">Configurable in PowerShell using <strong>Set- AppvClientConfiguration</strong> –<strong>SharedContentStoreMode</strong>, or</span></span></p></li>
<li><p><span data-ttu-id="5efd5-192">安裝 App-v 5.0 用戶端的過程中。</span><span class="sxs-lookup"><span data-stu-id="5efd5-192">During installation of the App-V 5.0 client.</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="5efd5-193">在執行 [共用內容存放區] 時，只會在硬碟上維護髮布資料其他虛擬應用程式資產會保留在記憶體（RAM）中。</span><span class="sxs-lookup"><span data-stu-id="5efd5-193">When running the shared content store only publishing data is maintained on hard disk; other virtual application assets are maintained in memory (RAM).</span></span></p>
<p><span data-ttu-id="5efd5-194">這有助於節省本機儲存空間，並將每秒最小化磁片 i/o （IOPS）。</span><span class="sxs-lookup"><span data-stu-id="5efd5-194">This helps to conserve local storage and minimize disk I/O per second (IOPS).</span></span></p></td>
<td align="left"><p><span data-ttu-id="5efd5-195">當 App-v 用戶端和 SCS 內容伺服器（SAN）之間提供低延遲連線時，建議您這麼做。</span><span class="sxs-lookup"><span data-stu-id="5efd5-195">This is recommended when low-latency connections are available between the App-V Client endpoint and the SCS content server, SAN.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5efd5-196">PreserveUserIntegrationsOnLogin</span><span class="sxs-lookup"><span data-stu-id="5efd5-196">PreserveUserIntegrationsOnLogin</span></span></p>
<ul>
<li><p><span data-ttu-id="5efd5-197">在 [ <strong> HKEY_LOCAL_MACHINE </strong>  \  <strong> 軟體 </strong>  \  <strong> Microsoft </strong>  \  <strong> AppV </strong>  \  <strong> 用戶端 </strong>  \  <strong> 整合 </strong> ] 下的 [登錄] 中進行設定。</span><span class="sxs-lookup"><span data-stu-id="5efd5-197">Configure in the Registry under <strong>HKEY_LOCAL_MACHINE</strong> \ <strong>Software</strong> \ <strong>Microsoft</strong> \ <strong>AppV</strong> \ <strong>Client</strong> \ <strong>Integration</strong>.</span></span></p></li>
<li><p><span data-ttu-id="5efd5-198"><strong>使用值1建立 DWORD 值 PreserveUserIntegrationsOnLogin </strong> <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="5efd5-198">Create the DWORD value <strong>PreserveUserIntegrationsOnLogin</strong> with a value of <strong>1</strong>.</span></span></p></li>
<li><p><span data-ttu-id="5efd5-199">重新開機應用程式-V 用戶端服務，或重新開機執行 App-v 用戶端的電腦。</span><span class="sxs-lookup"><span data-stu-id="5efd5-199">Restart the App-V client service or restart the computer running the App-V Client.</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="5efd5-200">如果您尚未預先設定（ <strong> 載入 AppvClientPackage </strong> ）特定的套件，且未設定此設定，App-v 用戶端將會解除整合 \*，然後重新整合 \*。</span><span class="sxs-lookup"><span data-stu-id="5efd5-200">If you have not pre-configured (<strong>Add-AppvClientPackage</strong>) a specific package and this setting is not configured, the App-V Client will de-integrate\* the persisted user integrations, then re-integrate\*.</span></span></p>
<p><span data-ttu-id="5efd5-201">針對符合上述條件的每個套件，有效地將作業的兩倍，在發佈/重新整理期間完成。</span><span class="sxs-lookup"><span data-stu-id="5efd5-201">For every package that meets the above conditions, effectively twice the work will be done during publishing/refresh.</span></span></p></td>
<td align="left"><p><span data-ttu-id="5efd5-202">如果您不打算預先設定基本影像中每個可用的使用者套件，請使用此設定。</span><span class="sxs-lookup"><span data-stu-id="5efd5-202">If you don’t plan to pre-configure every available user package in the base image, use this setting.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5efd5-203">MaxConcurrentPublishingRefresh</span><span class="sxs-lookup"><span data-stu-id="5efd5-203">MaxConcurrentPublishingRefresh</span></span></p>
<ul>
<li><p><span data-ttu-id="5efd5-204">在 [ <strong> HKEY_LOCAL_MACHINE </strong> &lt; 強 &gt; 軟體 </strong>  \  <strong> Microsoft </strong>  \  <strong> AppV </strong> &lt; 加強 &gt; 用戶端 </strong>  \  <strong> 發佈 </strong> ] 底下的 [登錄] 中進行設定。</span><span class="sxs-lookup"><span data-stu-id="5efd5-204">Configure in the Registry under <strong>HKEY_LOCAL_MACHINE</strong> &lt;strong&gt;Software</strong> \ <strong>Microsoft</strong> \ <strong>AppV</strong> &lt;strong&gt;Client</strong> \ <strong>Publishing</strong>.</span></span></p></li>
<li><p><span data-ttu-id="5efd5-205"><strong> </strong> 以所需的併發發佈更新數量限制，建立 DWORD 值 MaxConcurrentPublishingrefresh。</span><span class="sxs-lookup"><span data-stu-id="5efd5-205">Create the DWORD value <strong>MaxConcurrentPublishingrefresh</strong> with the desired maximum number of concurrent publishing refreshes.</span></span></p></li>
<li><p><span data-ttu-id="5efd5-206">App-v 用戶端服務和電腦不需要重新開機。</span><span class="sxs-lookup"><span data-stu-id="5efd5-206">The App-V client service and computer do not need to be restarted.</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="5efd5-207">這個設定決定了可以同時執行發佈重新整理/同步處理的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="5efd5-207">This setting determines the number of users that can perform a publishing refresh/sync at the same time.</span></span> <span data-ttu-id="5efd5-208">預設設定為 [無限制]。</span><span class="sxs-lookup"><span data-stu-id="5efd5-208">The default setting is no limit.</span></span></p></td>
<td align="left"><p><span data-ttu-id="5efd5-209">限制併發發佈的重新整理數可避免過度使用的 CPU 使用量，這可能會影響電腦效能。</span><span class="sxs-lookup"><span data-stu-id="5efd5-209">Limiting the number of concurrent publishing refreshes prevents excessive CPU usage that could impact computer performance.</span></span> <span data-ttu-id="5efd5-210">建議在 RDS 環境中使用這個限制，多個使用者可以同時登入同一部電腦並執行發佈重新整理同步處理。</span><span class="sxs-lookup"><span data-stu-id="5efd5-210">This limit is recommended in an RDS environment, where multiple users can log in to the same computer at the same time and perform a publishing refresh sync.</span></span></p>
<p><span data-ttu-id="5efd5-211">如果達到併發發佈重新整理閾值，發佈新應用程式時所需的時間，並在使用者登入時將它們提供給最終使用者，可能會有不確定的時間長度。</span><span class="sxs-lookup"><span data-stu-id="5efd5-211">If the concurrent publishing refresh threshold is reached, the time required to publish new applications and make them available to end users after they log in could take an indeterminate amount of time.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="5efd5-212">針對 App-v 方法設定 UE-V 解決方案</span><span class="sxs-lookup"><span data-stu-id="5efd5-212">Configure UE-V solution for App-V Approach</span></span>

<span data-ttu-id="5efd5-213">我們建議使用 Microsoft 使用者體驗虛擬化（UE-V）來捕獲並集中特定使用者的應用程式設定和 Windows 作業系統設定。</span><span class="sxs-lookup"><span data-stu-id="5efd5-213">We recommend using Microsoft User Experience Virtualization (UE-V) to capture and centralize application settings and Windows operating system settings for a specific user.</span></span> <span data-ttu-id="5efd5-214">然後，這些設定會套用到使用者所存取的不同電腦，包括桌上型電腦、膝上型電腦和虛擬桌面基礎結構（VDI）會話。</span><span class="sxs-lookup"><span data-stu-id="5efd5-214">These settings are then applied to the different computers that are accessed by the user, including desktop computers, laptop computers, and virtual desktop infrastructure (VDI) sessions.</span></span> <span data-ttu-id="5efd5-215">UE-V 已針對 RDS 和 VDI 案例進行優化。</span><span class="sxs-lookup"><span data-stu-id="5efd5-215">UE-V is optimized for RDS and VDI scenarios.</span></span>

<span data-ttu-id="5efd5-216">如需詳細資訊，請參閱[使用者體驗虛擬化的快速入門 2.0](https://technet.microsoft.com/library/dn458936.aspx)</span><span class="sxs-lookup"><span data-stu-id="5efd5-216">For more information see [Getting Started With User Experience Virtualization 2.0](https://technet.microsoft.com/library/dn458936.aspx)</span></span>

<span data-ttu-id="5efd5-217">實質上，您只需要安裝 UE-V 用戶端，然後從[Microsoft 使用者經驗虛擬化（ue-v）範本庫](https://gallery.technet.microsoft.com/Authored-UE-V-Settings-bb442a33)下載下列 microsoft 撰寫的 app-v 設定範本。</span><span class="sxs-lookup"><span data-stu-id="5efd5-217">In essence all that is required is to install the UE-V client and download the following Microsoft authored App-V settings template from the [Microsoft User Experience Virtualization (UE-V) template gallery](https://gallery.technet.microsoft.com/Authored-UE-V-Settings-bb442a33).</span></span> <span data-ttu-id="5efd5-218">註冊範本。</span><span class="sxs-lookup"><span data-stu-id="5efd5-218">Register the template.</span></span> <span data-ttu-id="5efd5-219">如需 UE-V 範本的詳細資訊，請參閱[用於取得及註冊範本的 ue-v 特定資源](https://technet.microsoft.com/library/dn458936.aspx)。</span><span class="sxs-lookup"><span data-stu-id="5efd5-219">For more information around UE-V templates see [The UE-V specific resource for acquiring and registering the template](https://technet.microsoft.com/library/dn458936.aspx).</span></span>

**<span data-ttu-id="5efd5-220">注意</span><span class="sxs-lookup"><span data-stu-id="5efd5-220">Note</span></span>**  
<span data-ttu-id="5efd5-221">若不執行額外的設定步驟，Microsoft 使用者環境虛擬化（UE-V）將無法同步處理目的電腦上的開始功能表快速鍵（.lnk 檔案）。</span><span class="sxs-lookup"><span data-stu-id="5efd5-221">Without performing an additional configuration step, the Microsoft User Environment Virtualization (UE-V) will not be able to synchronize the Start menu shortcuts (.lnk files) on the target computer.</span></span> <span data-ttu-id="5efd5-222">預設會排除 .lnk 檔案類型。</span><span class="sxs-lookup"><span data-stu-id="5efd5-222">The .lnk file type is excluded by default.</span></span>

<span data-ttu-id="5efd5-223">UE-V 只支援從 RDS 和 VDI 案例中的排除清單中移除 .lnk 檔案類型，而每個使用者的裝置都將有一組相同的應用程式安裝在相同的位置，且每個 .lnk 檔案對於所有使用者的裝置都是有效的。</span><span class="sxs-lookup"><span data-stu-id="5efd5-223">UE-V will only support removing the .lnk file type from the exclusion list in the RDS and VDI scenarios, where every user’s device will have the same set of applications installed to the same location and every .lnk file is valid for all the users’ devices.</span></span> <span data-ttu-id="5efd5-224">例如，UE-V 目前不支援下列2種案例，因為最終結果是該快速鍵將在一個（而非所有）裝置上生效。</span><span class="sxs-lookup"><span data-stu-id="5efd5-224">For example, UE-V would not currently support the following 2 scenarios, because the net result will be that the shortcut will be valid on one but not all devices.</span></span>

-   <span data-ttu-id="5efd5-225">如果使用者已在一部裝置上安裝應用程式，且在另一個裝置上安裝了相同的原生應用程式，且已啟用 .lnk 檔案的不同安裝根目錄。</span><span class="sxs-lookup"><span data-stu-id="5efd5-225">If a user has an application installed on one device with .lnk files enabled and the same native application installed on another device to a different installation root with .lnk files enabled.</span></span>

-   <span data-ttu-id="5efd5-226">如果使用者已在一部裝置上安裝應用程式，但沒有已啟用 .lnk 檔案的其他應用程式。</span><span class="sxs-lookup"><span data-stu-id="5efd5-226">If a user has an application installed on one device but not another with .lnk files enabled.</span></span>



**<span data-ttu-id="5efd5-227">重要</span><span class="sxs-lookup"><span data-stu-id="5efd5-227">Important</span></span>**  
<span data-ttu-id="5efd5-228">本主題說明如何使用 [登錄編輯程式] 變更 Windows 登錄。</span><span class="sxs-lookup"><span data-stu-id="5efd5-228">This topic describes how to change the Windows registry by using Registry Editor.</span></span> <span data-ttu-id="5efd5-229">如果您不正確地變更 Windows 登錄，可能會導致嚴重的問題，可能需要重新安裝 Windows。</span><span class="sxs-lookup"><span data-stu-id="5efd5-229">If you change the Windows registry incorrectly, you can cause serious problems that might require you to reinstall Windows.</span></span> <span data-ttu-id="5efd5-230">變更登錄前，您應該先製作一份登錄檔案（系統 .dat 和使用者 .dat）的備份複本。</span><span class="sxs-lookup"><span data-stu-id="5efd5-230">You should make a backup copy of the registry files (System.dat and User.dat) before you change the registry.</span></span> <span data-ttu-id="5efd5-231">Microsoft 不能保證變更註冊表時可能會發生的問題，可以解決。</span><span class="sxs-lookup"><span data-stu-id="5efd5-231">Microsoft cannot guarantee that the problems that might occur when you change the registry can be resolved.</span></span> <span data-ttu-id="5efd5-232">變更註冊表的風險由您自行承擔。</span><span class="sxs-lookup"><span data-stu-id="5efd5-232">Change the registry at your own risk.</span></span>



<span data-ttu-id="5efd5-233">使用 Microsoft Registry Editor （regedit.exe）流覽至**HKEY \ _LOCAL \ _MACHINE**  \\  **軟體**  \\  **Microsoft**  \\  **UEV**  \\  **Agent**設定  \\  **Configuration**  \\  **ExcludedFileTypes**並從排除的檔案類型中移除 **.lnk** 。</span><span class="sxs-lookup"><span data-stu-id="5efd5-233">Using the Microsoft Registry Editor (regedit.exe), navigate to **HKEY\_LOCAL\_MACHINE** \\ **Software** \\ **Microsoft** \\ **UEV** \\ **Agent** \\ **Configuration** \\ **ExcludedFileTypes** and remove **.lnk** from the excluded file types.</span></span>

**<span data-ttu-id="5efd5-234">針對 App-v 方法設定其他使用者設定檔管理（UPM）方案</span><span class="sxs-lookup"><span data-stu-id="5efd5-234">Configure other User Profile Management (UPM) solution for App-V Approach</span></span>**

<span data-ttu-id="5efd5-235">在有狀態的環境中的預期是已實現 UPM 方案，而且可支援跨會話和登錄之間的使用者資料持續性。</span><span class="sxs-lookup"><span data-stu-id="5efd5-235">The expectation in a stateful environment is that a UPM solution is implemented and can support persistence of user data across sessions and between logins.</span></span>

<span data-ttu-id="5efd5-236">UPM 方案的需求如下所示。</span><span class="sxs-lookup"><span data-stu-id="5efd5-236">The requirements for the UPM solution are as follows.</span></span>

<span data-ttu-id="5efd5-237">若要啟用優化的登入體驗（例如使用者的 app-v 5.0 方法），解決方案必須具備下列各項：</span><span class="sxs-lookup"><span data-stu-id="5efd5-237">To enable an optimized login experience, for example the App-V 5.0 approach for the user, the solution must be capable of:</span></span>

-   <span data-ttu-id="5efd5-238">在使用者設定檔/角色中保留下列使用者整合。</span><span class="sxs-lookup"><span data-stu-id="5efd5-238">Persisting the below user integrations as part of the user profile/persona.</span></span>

-   <span data-ttu-id="5efd5-239">在登入（或應用程式啟動）時觸發使用者設定檔同步處理，可保證在發佈/重新整理開始前已套用所有使用者整合，或者</span><span class="sxs-lookup"><span data-stu-id="5efd5-239">Triggering a user profile sync on login (or application start), which can guarantee that all user integrations are applied before publishing/refresh begin, or,</span></span>

-   <span data-ttu-id="5efd5-240">附加與分離使用者設定檔磁片（UPD）或包含使用者集成的類似技術。</span><span class="sxs-lookup"><span data-stu-id="5efd5-240">Attaching and detaching a user profile disk (UPD) or similar technology that contains the user integrations.</span></span>

-   <span data-ttu-id="5efd5-241">在會話登出之前，捕獲對位置所做的變更，這些位置組成使用者整合。</span><span class="sxs-lookup"><span data-stu-id="5efd5-241">Capturing changes to the locations, which constitute the user integrations, prior to session logoff.</span></span>

<span data-ttu-id="5efd5-242">在您新增發佈伺服器時，使用 App-v 5.0 （**載入 AppvPublishingServer**），您可以設定同步處理，例如在登入期間進行重新整理，或在指定的重新整理間隔之後進行重新整理。</span><span class="sxs-lookup"><span data-stu-id="5efd5-242">With App-V 5.0 when you add a publishing server (**Add-AppvPublishingServer**) you can configure synchronization, for example refresh during log on and/or after a specified refresh interval.</span></span> <span data-ttu-id="5efd5-243">在這兩種情況下，都會建立排程任務。</span><span class="sxs-lookup"><span data-stu-id="5efd5-243">In both cases a scheduled task is created.</span></span>

<span data-ttu-id="5efd5-244">在舊版 App-V 5.0 中，兩個排程的任務都是使用 VBScript 來啟動使用者和全域重新整理。</span><span class="sxs-lookup"><span data-stu-id="5efd5-244">In previous versions of App-V 5.0, both scheduled tasks were configured using a VBScript that would initiate the user and global refresh.</span></span> <span data-ttu-id="5efd5-245">針對應用程式虛擬化5.0 的修復程式套件4，使用者會在登錄時重新整理（由**SyncAppvPublishingServer.exe**啟動）。</span><span class="sxs-lookup"><span data-stu-id="5efd5-245">With Hotfix Package 4 for Application Virtualization 5.0 SP2 the user refresh on log on is initiated by **SyncAppvPublishingServer.exe**.</span></span> <span data-ttu-id="5efd5-246">引入此變更是為了提供 UPM 解決方案的觸發程式。</span><span class="sxs-lookup"><span data-stu-id="5efd5-246">This change was introduced to provide UPM solutions a trigger process.</span></span> <span data-ttu-id="5efd5-247">這個處理常式會延遲發佈/refresh，讓 UPM 方案能夠套用使用者整合。</span><span class="sxs-lookup"><span data-stu-id="5efd5-247">This process will delay the publish /refresh to allow the UPM solution to apply the user integrations.</span></span> <span data-ttu-id="5efd5-248">發佈/重新整理完成後，就會結束。</span><span class="sxs-lookup"><span data-stu-id="5efd5-248">It will exit once the publishing/refresh is complete.</span></span>

**<span data-ttu-id="5efd5-249">使用者整合</span><span class="sxs-lookup"><span data-stu-id="5efd5-249">User Integrations</span></span>**

<span data-ttu-id="5efd5-250">Registry – HKEY \ _CURRENT \ _USER</span><span class="sxs-lookup"><span data-stu-id="5efd5-250">Registry – HKEY\_CURRENT\_USER</span></span>

-   <span data-ttu-id="5efd5-251">路徑-Software\\Classes</span><span class="sxs-lookup"><span data-stu-id="5efd5-251">Path - Software\\Classes</span></span>

    <span data-ttu-id="5efd5-252">[排除]：本機設定、ActivatableClasses、AppX \ \*</span><span class="sxs-lookup"><span data-stu-id="5efd5-252">Exclude: Local Settings, ActivatableClasses, AppX\*</span></span>

-   <span data-ttu-id="5efd5-253">路徑-Software\\Microsoft\\AppV</span><span class="sxs-lookup"><span data-stu-id="5efd5-253">Path - Software\\Microsoft\\AppV</span></span>

-   <span data-ttu-id="5efd5-254">路徑 Software\\Microsoft\\Windows\\CurrentVersion\\App 路徑</span><span class="sxs-lookup"><span data-stu-id="5efd5-254">Path- Software\\Microsoft\\Windows\\CurrentVersion\\App Paths</span></span>

**<span data-ttu-id="5efd5-255">檔案位置</span><span class="sxs-lookup"><span data-stu-id="5efd5-255">File Locations</span></span>**

-   <span data-ttu-id="5efd5-256">Root-"環境變數" APPDATA</span><span class="sxs-lookup"><span data-stu-id="5efd5-256">Root – “Environment Variable” APPDATA</span></span>

    <span data-ttu-id="5efd5-257">Path – Microsoft\\AppV\\Client\\Catalog</span><span class="sxs-lookup"><span data-stu-id="5efd5-257">Path – Microsoft\\AppV\\Client\\Catalog</span></span>

-   <span data-ttu-id="5efd5-258">Root-"環境變數" APPDATA</span><span class="sxs-lookup"><span data-stu-id="5efd5-258">Root – “Environment Variable” APPDATA</span></span>

    <span data-ttu-id="5efd5-259">Path – Microsoft\\AppV\\Client\\Integration</span><span class="sxs-lookup"><span data-stu-id="5efd5-259">Path – Microsoft\\AppV\\Client\\Integration</span></span>

-   <span data-ttu-id="5efd5-260">Root-"環境變數" APPDATA</span><span class="sxs-lookup"><span data-stu-id="5efd5-260">Root – “Environment Variable” APPDATA</span></span>

    <span data-ttu-id="5efd5-261">Path-Microsoft\\Windows\\Start Menu\\Programs</span><span class="sxs-lookup"><span data-stu-id="5efd5-261">Path - Microsoft\\Windows\\Start Menu\\Programs</span></span>

-   <span data-ttu-id="5efd5-262">（若要保留所有桌面快速鍵、虛擬和非虛擬）</span><span class="sxs-lookup"><span data-stu-id="5efd5-262">(To persist all desktop shortcuts, virtual and non-virtual)</span></span>

    <span data-ttu-id="5efd5-263">Root-"KnownFolder" {B4BFCC3A-DB2C-424C-B029-7FE99A87C641} FileMask-\ \* .lnk</span><span class="sxs-lookup"><span data-stu-id="5efd5-263">Root - “KnownFolder” {B4BFCC3A-DB2C-424C-B029-7FE99A87C641}FileMask - \*.lnk</span></span>

**<span data-ttu-id="5efd5-264">Microsoft 使用者體驗虛擬化（UE-V）</span><span class="sxs-lookup"><span data-stu-id="5efd5-264">Microsoft User Experience Virtualization (UE-V)</span></span>**

<span data-ttu-id="5efd5-265">此外，我們建議使用 Microsoft 使用者體驗虛擬化（UE-V）來捕獲與集中特定使用者的應用程式設定和 Windows 作業系統設定。</span><span class="sxs-lookup"><span data-stu-id="5efd5-265">Additionally, we recommend using Microsoft User Experience Virtualization (UE-V) to capture and centralize application settings and Windows operating system settings for a specific user.</span></span> <span data-ttu-id="5efd5-266">然後，這些設定會套用到使用者所存取的不同電腦，包括桌上型電腦、膝上型電腦和虛擬桌面基礎結構（VDI）會話。</span><span class="sxs-lookup"><span data-stu-id="5efd5-266">These settings are then applied to the different computers that are accessed by the user, including desktop computers, laptop computers, and virtual desktop infrastructure (VDI) sessions.</span></span>

<span data-ttu-id="5efd5-267">如需詳細資訊，請參閱[使用者體驗虛擬化1.0 快速入門](https://technet.microsoft.com/library/jj680015.aspx)和[使用 Ue-v 範本庫共用設定位置範本](https://technet.microsoft.com/library/jj679972.aspx)。</span><span class="sxs-lookup"><span data-stu-id="5efd5-267">For more information see [Getting Started With User Experience Virtualization 1.0](https://technet.microsoft.com/library/jj680015.aspx) and [Sharing Settings Location Templates with the UE-V Template Gallery](https://technet.microsoft.com/library/jj679972.aspx).</span></span>

### <a href="" id="bkmk-uewt"></a><span data-ttu-id="5efd5-268">使用者體驗逐步指導</span><span class="sxs-lookup"><span data-stu-id="5efd5-268">User Experience Walk-through</span></span>

<span data-ttu-id="5efd5-269">以下是 App-V 與 UPM 作業的逐步逐步說明，以及使用者預期的預期。</span><span class="sxs-lookup"><span data-stu-id="5efd5-269">This following is a step-by-step walk-through of the App-V and UPM operations and the expectations users should expect.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5efd5-270">針對效能優化</span><span class="sxs-lookup"><span data-stu-id="5efd5-270">Optimized for Performance</span></span></th>
<th align="left"><span data-ttu-id="5efd5-271">針對儲存進行優化</span><span class="sxs-lookup"><span data-stu-id="5efd5-271">Optimized for Storage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5efd5-272">在 VDI/RDSH 環境中實現此方法之後，請在第一次登入時，</span><span class="sxs-lookup"><span data-stu-id="5efd5-272">After implementing this approach in the VDI/RDSH environment, on first login,</span></span></p>
<ul>
<li><p><span data-ttu-id="5efd5-273">一道啟動使用者發佈/重新整理。</span><span class="sxs-lookup"><span data-stu-id="5efd5-273">(Operation) A user-publishing/refresh is initiated.</span></span> <span data-ttu-id="5efd5-274">認為如果這是使用者第一次發佈的虛擬應用程式（例如非永久性），這將會採取發佈/重新整理的一般持續時間。</span><span class="sxs-lookup"><span data-stu-id="5efd5-274">(Expectation) If this is the first time a user has published virtual applications (e.g. non-persistent), this will take the usual duration of a publishing/refresh.</span></span></p></li>
<li><p><span data-ttu-id="5efd5-275">一道在發佈/重新整理之後，UPM 方案會捕獲使用者整合。</span><span class="sxs-lookup"><span data-stu-id="5efd5-275">(Operation) After the publishing/refresh, the UPM solution captures the user integrations.</span></span> <span data-ttu-id="5efd5-276">認為視 UPM 方案的設定方式而定，這可能會在登出程式中發生。</span><span class="sxs-lookup"><span data-stu-id="5efd5-276">(Expectation) Depending on how the UPM solution is configured, this may occur as part of the logoff process.</span></span> <span data-ttu-id="5efd5-277">這將會產生與使用者狀態保持不變相同/類似的額外負荷。</span><span class="sxs-lookup"><span data-stu-id="5efd5-277">This will incur the same/similar overhead as persisting the user state.</span></span></p></li>
</ul>
<p><span data-ttu-id="5efd5-278">在後續的登錄：</span><span class="sxs-lookup"><span data-stu-id="5efd5-278">On subsequent logins:</span></span></p>
<ul>
<li><p><span data-ttu-id="5efd5-279">一道在發佈/重新整理前，UPM 解決方案會將使用者整合套用至系統。</span><span class="sxs-lookup"><span data-stu-id="5efd5-279">(Operation) UPM solution applies the user integrations to the system prior to publishing/refresh.</span></span></p>
<p><span data-ttu-id="5efd5-280">認為桌面或 [開始] 功能表中將會顯示快捷方式，這會立即起作用。</span><span class="sxs-lookup"><span data-stu-id="5efd5-280">(Expectation) There will be shortcuts present on the desktop, or in the start menu, which work immediately.</span></span> <span data-ttu-id="5efd5-281">發佈/重新整理完成後（亦即封裝權利變更），部分可能會消失。</span><span class="sxs-lookup"><span data-stu-id="5efd5-281">When the publishing/refresh completes (i.e., package entitlements change), some may go away.</span></span></p></li>
<li><p><span data-ttu-id="5efd5-282">一道發佈/重新整理會處理使用者套件權利變更的取消發佈及發佈作業。</span><span class="sxs-lookup"><span data-stu-id="5efd5-282">(Operation) Publishing/refresh will process un-publish and publish operations for changes in user package entitlements.</span></span> <span data-ttu-id="5efd5-283">認為如果沒有任何權利變更，publishing1 將會在幾秒內完成。</span><span class="sxs-lookup"><span data-stu-id="5efd5-283">(Expectation) If there are no entitlement changes, publishing1 will complete in seconds.</span></span> <span data-ttu-id="5efd5-284">否則，發佈/重新整理會相對於虛擬應用程式的數量和複雜性 \* 而增加</span><span class="sxs-lookup"><span data-stu-id="5efd5-284">Otherwise, the publishing/refresh will increase relative to the number and complexity\* of virtual applications</span></span></p></li>
<li><p><span data-ttu-id="5efd5-285">一道UPM 解決方案將在登出時再次捕獲使用者整合。</span><span class="sxs-lookup"><span data-stu-id="5efd5-285">(Operation) UPM solution will capture user integrations again at logoff.</span></span> <span data-ttu-id="5efd5-286">認為與上一節相同。</span><span class="sxs-lookup"><span data-stu-id="5efd5-286">(Expectation) Same as previous.</span></span></p></li>
</ul>
<p><span data-ttu-id="5efd5-287">¹發佈作業（ <strong> 發佈 AppVClientPackage）會 </strong> 將專案新增至使用者目錄、將權利對應給使用者、識別當地商店，以及完成任何整合步驟完成。</span><span class="sxs-lookup"><span data-stu-id="5efd5-287">¹ The publishing operation (<strong>Publish-AppVClientPackage</strong>) adds entries to the user catalog, maps entitlement to the user, identifies the local store, and finishes by completing any integration steps.</span></span></p></td>
<td align="left"><p><span data-ttu-id="5efd5-288">在 VDI/RDSH 環境中實現此方法之後，請在第一次登入時，</span><span class="sxs-lookup"><span data-stu-id="5efd5-288">After implementing this approach in the VDI/RDSH environment, on first login,</span></span></p>
<ul>
<li><p><span data-ttu-id="5efd5-289">一道啟動使用者發佈/重新整理。</span><span class="sxs-lookup"><span data-stu-id="5efd5-289">(Operation) A user-publishing/refresh is initiated.</span></span> <span data-ttu-id="5efd5-290">認為</span><span class="sxs-lookup"><span data-stu-id="5efd5-290">(Expectation)</span></span></p>
<ul>
<li><p><span data-ttu-id="5efd5-291">如果這是使用者第一次發佈虛擬應用程式（例如，非永久性），這將會採取發佈/重新整理的一般持續時間。</span><span class="sxs-lookup"><span data-stu-id="5efd5-291">If this is the first time a user has published virtual applications (e.g., non-persistent), this will take the usual duration of a publishing/refresh.</span></span></p></li>
<li><p><span data-ttu-id="5efd5-292">首先，系統會根據預先設定套件（新增/重新整理）來影響後續的登錄。</span><span class="sxs-lookup"><span data-stu-id="5efd5-292">First and subsequent logins will be impacted by pre-configuring of packages (add/refresh).</span></span></p>
<p></p></li>
</ul></li>
<li><p><span data-ttu-id="5efd5-293">一道在發佈/重新整理之後，UPM 方案會捕獲使用者整合。</span><span class="sxs-lookup"><span data-stu-id="5efd5-293">(Operation) After the publishing/refresh, the UPM solution captures the user integrations.</span></span> <span data-ttu-id="5efd5-294">認為視 UPM 方案的設定方式而定，這可能會在登出程式中發生。</span><span class="sxs-lookup"><span data-stu-id="5efd5-294">(Expectation) Depending on how the UPM solution is configured, this may occur as part of the logoff process.</span></span> <span data-ttu-id="5efd5-295">這將會產生與使用者狀態保持不變的相同/類似負荷</span><span class="sxs-lookup"><span data-stu-id="5efd5-295">This will incur the same/similar overhead as persisting the user state</span></span></p></li>
</ul>
<p><span data-ttu-id="5efd5-296">在後續的登錄：</span><span class="sxs-lookup"><span data-stu-id="5efd5-296">On subsequent logins:</span></span></p>
<ul>
<li><p><span data-ttu-id="5efd5-297">一道在發佈/重新整理前，UPM 解決方案會將使用者整合套用至系統。</span><span class="sxs-lookup"><span data-stu-id="5efd5-297">(Operation) UPM solution applies the user integrations to the system prior to publishing/refresh.</span></span></p></li>
<li><p><span data-ttu-id="5efd5-298">一道[新增/重新整理] 必須預先設定所有由使用者為目標的應用程式。</span><span class="sxs-lookup"><span data-stu-id="5efd5-298">(Operation) Add/refresh must pre-configure all user targeted applications.</span></span> <span data-ttu-id="5efd5-299">認為</span><span class="sxs-lookup"><span data-stu-id="5efd5-299">(Expectation)</span></span></p>
<ul>
<li><p><span data-ttu-id="5efd5-300">這可能會顯著增加應用程式可用性的時間（10秒的順序）。</span><span class="sxs-lookup"><span data-stu-id="5efd5-300">This may increase the time to application availability significantly (on the order of 10’s of seconds).</span></span></p></li>
<li><p><span data-ttu-id="5efd5-301">這會增加相對於虛擬應用程式數目和複雜性 \* 的發佈重新整理時間。</span><span class="sxs-lookup"><span data-stu-id="5efd5-301">This will increase the publishing refresh time relative to the number and complexity\* of virtual applications.</span></span></p>
<p></p></li>
</ul></li>
<li><p><span data-ttu-id="5efd5-302">一道發佈/重新整理將處理取消發佈及發佈作業，以變更使用者套件權利的變更。</span><span class="sxs-lookup"><span data-stu-id="5efd5-302">(Operation) Publishing/refresh will process un-publish and publish operations for changes to user package entitlements.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5efd5-303">負面</span><span class="sxs-lookup"><span data-stu-id="5efd5-303">Outcome</span></span></th>
<th align="left"><span data-ttu-id="5efd5-304">負面</span><span class="sxs-lookup"><span data-stu-id="5efd5-304">Outcome</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="5efd5-305">因為使用者整合完全保持不變，所以不需要進行任何工作，例如發佈/重新整理完成的整合。</span><span class="sxs-lookup"><span data-stu-id="5efd5-305">Because the user integrations are entirely preserved, there will be no work for example, integration for the publishing/refresh to complete.</span></span> <span data-ttu-id="5efd5-306">所有虛擬應用程式將在登入後的幾秒鐘內提供。</span><span class="sxs-lookup"><span data-stu-id="5efd5-306">All virtual applications will be available within seconds of login.</span></span></p></li>
<li><p><span data-ttu-id="5efd5-307">發佈/重新整理會將變更處理給擁有虛擬應用程式的使用者，這些使用者會影響體驗。</span><span class="sxs-lookup"><span data-stu-id="5efd5-307">The publishing/refresh will process changes to the users entitled virtual applications which impacts the experience.</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="5efd5-308">因為 [新增/重新整理] 必須重新設定所有虛擬應用程式至 VM，所以每個登入的發佈重新整理時間都會得到延伸。</span><span class="sxs-lookup"><span data-stu-id="5efd5-308">Because the add/refresh must re-configure all the virtual applications to the VM, the publishing refresh time on every login will be extended.</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-plc"></a><span data-ttu-id="5efd5-309">影響封裝的生命週期</span><span class="sxs-lookup"><span data-stu-id="5efd5-309">Impact to Package Life Cycle</span></span>

<span data-ttu-id="5efd5-310">升級套件是套件生命週期的一個重要層面。</span><span class="sxs-lookup"><span data-stu-id="5efd5-310">Upgrading a package is a crucial aspect of the package lifecycle.</span></span> <span data-ttu-id="5efd5-311">若要協助使用者能存取適當升級（已發佈）或降級（未發佈）虛擬應用程式套件，建議您更新基本映射以反映這些變更。</span><span class="sxs-lookup"><span data-stu-id="5efd5-311">To help guarantee users have access to the appropriate upgraded (published) or downgraded (un-published) virtual application packages, it is recommended you update the base image to reflect these changes.</span></span> <span data-ttu-id="5efd5-312">若要瞭解為什麼要查看下列章節：</span><span class="sxs-lookup"><span data-stu-id="5efd5-312">To understand why review the following section:</span></span>

<span data-ttu-id="5efd5-313">App-v 5.0 SP2 引進了擱置狀態的概念。</span><span class="sxs-lookup"><span data-stu-id="5efd5-313">App-V 5.0 SP2 introduced the concept of pending states.</span></span> <span data-ttu-id="5efd5-314">在過去，</span><span class="sxs-lookup"><span data-stu-id="5efd5-314">In the past,</span></span>

-   <span data-ttu-id="5efd5-315">如果系統管理員變更了 [權利] 或 [建立新版本的套件（已升級）]，且在打包期間進行發佈/重新整理時，將無法使用 [取消發佈] 或 [發佈] 作業。</span><span class="sxs-lookup"><span data-stu-id="5efd5-315">If an administrator changed entitlements or created a new version of a package (upgraded) and during a publishing/refresh that package was in-use, the un-publish or publish operation, respectively, would fail.</span></span>

-   <span data-ttu-id="5efd5-316">現在，如果套件是在使用中，則會暫停該作業。</span><span class="sxs-lookup"><span data-stu-id="5efd5-316">Now, if a package is in-use the operation will be pended.</span></span> <span data-ttu-id="5efd5-317">[取消發佈] 和 [發佈-待定] 作業將會在服務重新開機時處理，或在發出另一個發佈或取消發佈命令時進行處理。</span><span class="sxs-lookup"><span data-stu-id="5efd5-317">The un-publish and publish-pend operations will be processed on service restart or if another publish or un-publish command is issued.</span></span> <span data-ttu-id="5efd5-318">在後一種情況下，如果虛擬應用程式是在使用中，則虛擬應用程式將會保持擱置狀態。</span><span class="sxs-lookup"><span data-stu-id="5efd5-318">In the latter case, if the virtual application is in-use otherwise, the virtual application will remain in a pending state.</span></span> <span data-ttu-id="5efd5-319">針對全域發佈的套件，通常需要重新開機（或重新開機服務）。</span><span class="sxs-lookup"><span data-stu-id="5efd5-319">For globally published packages, a restart (or service restart) often needed.</span></span>

<span data-ttu-id="5efd5-320">在非持久性環境中，不可能會處理這些暫停的作業。</span><span class="sxs-lookup"><span data-stu-id="5efd5-320">In a non-persistent environment, it is unlikely these pended operations will be processed.</span></span> <span data-ttu-id="5efd5-321">暫停的作業（例如工作）會在**HKEY \ _CURRENT \ _USER**  \\  **軟體**  \\  **Microsoft**  \\  **AppV**  \\  **用戶端**  \\  \*\* \*\*] 下捕獲。</span><span class="sxs-lookup"><span data-stu-id="5efd5-321">The pended operations, for example tasks are captured under **HKEY\_CURRENT\_USER** \\ **Software** \\ **Microsoft** \\ **AppV** \\ **Client** \\ **PendingTasks**.</span></span> <span data-ttu-id="5efd5-322">雖然此位置是由 UPM 解決方案所保留，但在登入前未將它套用到環境，否則就不會處理它。</span><span class="sxs-lookup"><span data-stu-id="5efd5-322">Although this location is persisted by the UPM solution, if it is not applied to the environment prior to log on, it will not be processed.</span></span>

### <a href="" id="bkmk-evdi"></a><span data-ttu-id="5efd5-323">透過效能優化調整來增強 VDI 體驗</span><span class="sxs-lookup"><span data-stu-id="5efd5-323">Enhancing the VDI Experience through Performance Optimization Tuning</span></span>

<span data-ttu-id="5efd5-324">下列各節包含 Microsoft 檔和下載相關資訊的清單，這些資訊在優化您的環境以提高效能時可能會很有用。</span><span class="sxs-lookup"><span data-stu-id="5efd5-324">The following section contains lists with information about Microsoft documentation and downloads that may be useful when optimizing your environment for performance.</span></span>

**<span data-ttu-id="5efd5-325">.NET NGEN 博客及腳本（強烈建議）</span><span class="sxs-lookup"><span data-stu-id="5efd5-325">.NET NGEN Blog and Script (Highly Recommended)</span></span>**

<span data-ttu-id="5efd5-326">關於 NGEN 技術</span><span class="sxs-lookup"><span data-stu-id="5efd5-326">About NGEN technology</span></span>

-   [<span data-ttu-id="5efd5-327">如何加速 NGEN 優化</span><span class="sxs-lookup"><span data-stu-id="5efd5-327">How to speed up NGEN optimization</span></span>](https://blogs.msdn.com/b/dotnet/archive/2013/08/06/wondering-why-mscorsvw-exe-has-high-cpu-usage-you-can-speed-it-up.aspx)

-   [<span data-ttu-id="5efd5-328">指令碼</span><span class="sxs-lookup"><span data-stu-id="5efd5-328">Script</span></span>](https://aka.ms/DrainNGenQueue)

**<span data-ttu-id="5efd5-329">Windows Server 和伺服器角色</span><span class="sxs-lookup"><span data-stu-id="5efd5-329">Windows Server and Server Roles</span></span>**

<span data-ttu-id="5efd5-330">伺服器效能調整指導方針</span><span class="sxs-lookup"><span data-stu-id="5efd5-330">Server Performance Tuning Guidelines for</span></span>

-   [<span data-ttu-id="5efd5-331">Microsoft Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="5efd5-331">Microsoft Windows Server 2012 R2</span></span>](https://msdn.microsoft.com/library/windows/hardware/dn529133.aspx)

-   [<span data-ttu-id="5efd5-332">Microsoft Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="5efd5-332">Microsoft Windows Server 2012</span></span>](https://download.microsoft.com/download/0/0/B/00BE76AF-D340-4759-8ECD-C80BC53B6231/performance-tuning-guidelines-windows-server-2012.docx)

-   [<span data-ttu-id="5efd5-333">Microsoft Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="5efd5-333">Microsoft Windows Server 2008 R2</span></span>](https://download.microsoft.com/download/6/B/2/6B2EBD3A-302E-4553-AC00-9885BBF31E21/Perf-tun-srv-R2.docx)

**<span data-ttu-id="5efd5-334">伺服器角色</span><span class="sxs-lookup"><span data-stu-id="5efd5-334">Server Roles</span></span>**

-   [<span data-ttu-id="5efd5-335">遠端桌面虛擬化主機</span><span class="sxs-lookup"><span data-stu-id="5efd5-335">Remote Desktop Virtualization Host</span></span>](https://msdn.microsoft.com/library/windows/hardware/dn567643.aspx)

-   [<span data-ttu-id="5efd5-336">遠端桌面工作階段主機</span><span class="sxs-lookup"><span data-stu-id="5efd5-336">Remote Desktop Session Host</span></span>](https://msdn.microsoft.com/library/windows/hardware/dn567648.aspx)

-   [<span data-ttu-id="5efd5-337">IIS 關聯性： App-v 管理、發佈、報告 Web 服務</span><span class="sxs-lookup"><span data-stu-id="5efd5-337">IIS Relevance: App-V Management, Publishing, Reporting Web Services</span></span>](https://msdn.microsoft.com/library/windows/hardware/dn567678.aspx)

-   [<span data-ttu-id="5efd5-338">檔案伺服器（SMB）關聯性：如果用於在 SCS 模式中使用 App-v 內容儲存與傳遞</span><span class="sxs-lookup"><span data-stu-id="5efd5-338">File Server (SMB) Relevance: If used for App-V Content Storage and Delivery in SCS Mode</span></span>](https://technet.microsoft.com/library/jj134210.aspx)

**<span data-ttu-id="5efd5-339">Windows 用戶端（來賓 OS）效能調整指導方針</span><span class="sxs-lookup"><span data-stu-id="5efd5-339">Windows Client (Guest OS) Performance Tuning Guidance</span></span>**

-   [<span data-ttu-id="5efd5-340">Microsoft Windows 7</span><span class="sxs-lookup"><span data-stu-id="5efd5-340">Microsoft Windows 7</span></span>](https://download.microsoft.com/download/E/5/7/E5783D68-160B-4366-8387-114FC3E45EB4/Performance Tuning Guidelines for Windows 7 Desktop Virtualization v1.9.docx)

-   [<span data-ttu-id="5efd5-341">優化腳本：（由 Microsoft 支援人員提供）</span><span class="sxs-lookup"><span data-stu-id="5efd5-341">Optimization Script: (Provided by Microsoft Support)</span></span>](https://blogs.technet.com/b/jeff_stokes/archive/2012/10/15/the-microsoft-premier-field-engineer-pfe-view-on-virtual-desktop-vdi-density.aspx)

-   [<span data-ttu-id="5efd5-342">Microsoft Windows 8</span><span class="sxs-lookup"><span data-stu-id="5efd5-342">Microsoft Windows 8</span></span>](https://download.microsoft.com/download/6/0/1/601D7797-A063-4FA7-A2E5-74519B57C2B4/Windows_8_VDI_Image_Client_Tuning_Guide.pdf)

-   [<span data-ttu-id="5efd5-343">優化腳本：（由 Microsoft 支援人員提供）</span><span class="sxs-lookup"><span data-stu-id="5efd5-343">Optimization Script: (Provided by Microsoft Support)</span></span>](https://blogs.technet.com/b/jeff_stokes/archive/2013/04/09/hot-off-the-presses-get-it-now-the-windows-8-vdi-optimization-script-courtesy-of-pfe.aspx)

## <span data-ttu-id="5efd5-344">針對發佈效能優化套件的先後順序步驟</span><span class="sxs-lookup"><span data-stu-id="5efd5-344">Sequencing Steps to Optimize Packages for Publishing Performance</span></span>


<span data-ttu-id="5efd5-345">App-v 5.0 和 App-v 5.0 SP2 在其各自的發行中提供重要的價值。</span><span class="sxs-lookup"><span data-stu-id="5efd5-345">App-V 5.0 and App-V 5.0 SP2 provide significant value in their respective releases.</span></span> <span data-ttu-id="5efd5-346">有數個功能可協助新案例或啟用新的客戶部署案例。</span><span class="sxs-lookup"><span data-stu-id="5efd5-346">Several features facilitate new scenarios or enabled new customer deployment scenarios.</span></span> <span data-ttu-id="5efd5-347">下列功能可能會影響發佈與啟動作業的效能。</span><span class="sxs-lookup"><span data-stu-id="5efd5-347">These following features can impact the performance of the publishing and launch operations.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5efd5-348">步驟</span><span class="sxs-lookup"><span data-stu-id="5efd5-348">Step</span></span></th>
<th align="left"><span data-ttu-id="5efd5-349">考量</span><span class="sxs-lookup"><span data-stu-id="5efd5-349">Consideration</span></span></th>
<th align="left"><span data-ttu-id="5efd5-350">權益</span><span class="sxs-lookup"><span data-stu-id="5efd5-350">Benefits</span></span></th>
<th align="left"><span data-ttu-id="5efd5-351">負面</span><span class="sxs-lookup"><span data-stu-id="5efd5-351">Tradeoffs</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5efd5-352">沒有功能區塊1（FB1，也稱為主要的 FB）</span><span class="sxs-lookup"><span data-stu-id="5efd5-352">No Feature Block 1 (FB1, also known as Primary FB)</span></span></p></td>
<td align="left"><p><span data-ttu-id="5efd5-353">[無 FB1] 表示應用程式將立即啟動，資料流程錯誤（應用程式需要檔案、DLL 且必須在網路上向下拉入）。如果有網路限制，FB1 將會：</span><span class="sxs-lookup"><span data-stu-id="5efd5-353">No FB1 means the application will launch immediately and stream fault (application requires file, DLL and must pull down over the network) during launch.If there are network limitations, FB1 will:</span></span></p>
<ul>
<li><p><span data-ttu-id="5efd5-354">減少當您第一次啟動應用程式時所使用的資料流程錯誤和網路頻寬數目。</span><span class="sxs-lookup"><span data-stu-id="5efd5-354">Reduce the number of stream faults and network bandwidth used when you launch an application for the first time.</span></span></p></li>
<li><p><span data-ttu-id="5efd5-355">延遲啟動，直到整個 FB1 都已流入為止。</span><span class="sxs-lookup"><span data-stu-id="5efd5-355">Delay launch until the entire FB1 has been streamed.</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="5efd5-356">資料流程錯誤減少了啟動時間。</span><span class="sxs-lookup"><span data-stu-id="5efd5-356">Stream faulting decreases the launch time.</span></span></p></td>
<td align="left"><p><span data-ttu-id="5efd5-357">已設定 FB1 的虛擬應用程式套件將需要重新排序。</span><span class="sxs-lookup"><span data-stu-id="5efd5-357">Virtual application packages with FB1 configured will need to be re-sequenced.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="5efd5-358">移除 FB1</span><span class="sxs-lookup"><span data-stu-id="5efd5-358">Removing FB1</span></span>

<span data-ttu-id="5efd5-359">移除 FB1 不需要原始應用程式安裝程式。</span><span class="sxs-lookup"><span data-stu-id="5efd5-359">Removing FB1 does not require the original application installer.</span></span> <span data-ttu-id="5efd5-360">完成下列步驟之後，建議您將執行 sequencer 的電腦還原為乾淨的快照。</span><span class="sxs-lookup"><span data-stu-id="5efd5-360">After completing the following steps, it is suggested that you revert the computer running the sequencer to a clean snapshot.</span></span>

<span data-ttu-id="5efd5-361">**SEQUENCER UI** -建立新的虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="5efd5-361">**Sequencer UI** - Create a New Virtual Application Package.</span></span>

1.  <span data-ttu-id="5efd5-362">完成進行自訂資料流程的先後順序步驟 &gt; 。</span><span class="sxs-lookup"><span data-stu-id="5efd5-362">Complete the sequencing steps up to Customize -&gt; Streaming.</span></span>

2.  <span data-ttu-id="5efd5-363">在 [資料流程] 步驟中，請勿選取 **[在低速或不可靠的網路上針對部署來優化套件**]。</span><span class="sxs-lookup"><span data-stu-id="5efd5-363">At the Streaming step, do not select **Optimize the package for deployment over slow or unreliable network**.</span></span>

3.  <span data-ttu-id="5efd5-364">如有需要，請移至**目標作業系統**。</span><span class="sxs-lookup"><span data-stu-id="5efd5-364">If desired, move on to **Target OS**.</span></span>

**<span data-ttu-id="5efd5-365">修改現有的虛擬應用程式套件</span><span class="sxs-lookup"><span data-stu-id="5efd5-365">Modify an Existing Virtual Application Package</span></span>**

1.  <span data-ttu-id="5efd5-366">完成排序步驟直至進行流式處理。</span><span class="sxs-lookup"><span data-stu-id="5efd5-366">Complete the sequencing steps up to Streaming.</span></span>

2.  <span data-ttu-id="5efd5-367">請勿選取 **[在慢速或不可靠的網路上優化套件以進行部署**]。</span><span class="sxs-lookup"><span data-stu-id="5efd5-367">Do not select **Optimize the package for deployment over a slow or unreliable network**.</span></span>

3.  <span data-ttu-id="5efd5-368">移至 [**建立套件**]。</span><span class="sxs-lookup"><span data-stu-id="5efd5-368">Move to **Create Package**.</span></span>

<span data-ttu-id="5efd5-369">**PowerShell** -更新現有的虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="5efd5-369">**PowerShell** - Update an Existing Virtual Application Package.</span></span>

1.  <span data-ttu-id="5efd5-370">開啟提升許可權的 PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="5efd5-370">Open an elevated PowerShell session.</span></span>

2.  <span data-ttu-id="5efd5-371">匯入-模組**appvsequencer**。</span><span class="sxs-lookup"><span data-stu-id="5efd5-371">Import-module **appvsequencer**.</span></span>

3.  <span data-ttu-id="5efd5-372">**更新-AppvSequencerPackage**  - **AppvPackageFilePath**</span><span class="sxs-lookup"><span data-stu-id="5efd5-372">**Update-AppvSequencerPackage** - **AppvPackageFilePath**</span></span>

    <span data-ttu-id="5efd5-373">"C:\\Packages\\MyPackage.appv"-安裝程式</span><span class="sxs-lookup"><span data-stu-id="5efd5-373">"C:\\Packages\\MyPackage.appv" -Installer</span></span>

    <span data-ttu-id="5efd5-374">"C:\\PackageInstall\\PackageUpgrade.exe empty.exe"-OutputPath</span><span class="sxs-lookup"><span data-stu-id="5efd5-374">"C:\\PackageInstall\\PackageUpgrade.exe empty.exe" -OutputPath</span></span>

    <span data-ttu-id="5efd5-375">"C:\\UpgradedPackages"</span><span class="sxs-lookup"><span data-stu-id="5efd5-375">"C:\\UpgradedPackages"</span></span>

    **<span data-ttu-id="5efd5-376">注意</span><span class="sxs-lookup"><span data-stu-id="5efd5-376">Note</span></span>**  
    <span data-ttu-id="5efd5-377">這個 Cmdlet 需要可執行檔（.exe）或批次處理檔案（.bat）。</span><span class="sxs-lookup"><span data-stu-id="5efd5-377">This cmdlet requires an executable (.exe) or batch file (.bat).</span></span> <span data-ttu-id="5efd5-378">您必須提供空白（無任何）可執行檔或批次處理檔案。</span><span class="sxs-lookup"><span data-stu-id="5efd5-378">You must provide an empty (does nothing) executable or batch file.</span></span>



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5efd5-379">步驟</span><span class="sxs-lookup"><span data-stu-id="5efd5-379">Step</span></span></th>
<th align="left"><span data-ttu-id="5efd5-380">考量</span><span class="sxs-lookup"><span data-stu-id="5efd5-380">Considerations</span></span></th>
<th align="left"><span data-ttu-id="5efd5-381">權益</span><span class="sxs-lookup"><span data-stu-id="5efd5-381">Benefits</span></span></th>
<th align="left"><span data-ttu-id="5efd5-382">負面</span><span class="sxs-lookup"><span data-stu-id="5efd5-382">Tradeoffs</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5efd5-383">發佈時不安裝 SXS （預先安裝的 SxS 元件）</span><span class="sxs-lookup"><span data-stu-id="5efd5-383">No SXS Install at Publish (Pre-Install SxS assemblies)</span></span></p></td>
<td align="left"><p><span data-ttu-id="5efd5-384">虛擬應用程式套件不需要重新排序。</span><span class="sxs-lookup"><span data-stu-id="5efd5-384">Virtual Application packages do not need to be re-sequenced.</span></span> <span data-ttu-id="5efd5-385">SxS 元件可以保留在虛擬應用程式套件中。</span><span class="sxs-lookup"><span data-stu-id="5efd5-385">SxS Assemblies can remain in the virtual application package.</span></span></p></td>
<td align="left"><p><span data-ttu-id="5efd5-386">在發佈時不會安裝 SxS 元件相依性。</span><span class="sxs-lookup"><span data-stu-id="5efd5-386">The SxS Assembly dependencies will not install at publishing time.</span></span></p></td>
<td align="left"><p><span data-ttu-id="5efd5-387">必須預先安裝 SxS 元件相依性。</span><span class="sxs-lookup"><span data-stu-id="5efd5-387">SxS Assembly dependencies must be pre-installed.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="5efd5-388">在 sequencer 上建立新的虛擬應用程式套件</span><span class="sxs-lookup"><span data-stu-id="5efd5-388">Creating a new virtual application package on the sequencer</span></span>

<span data-ttu-id="5efd5-389">如果在排序器監視期間，在應用程式的安裝過程中會安裝一個 SxS 元件（例如 VC + + 執行時間），則會自動偵測並包含在套件中的 SxS 元件。</span><span class="sxs-lookup"><span data-stu-id="5efd5-389">If, during sequencer monitoring, an SxS Assembly (such as a VC++ Runtime) is installed as part of an application’s installation, SxS Assembly will be automatically detected and included in the package.</span></span> <span data-ttu-id="5efd5-390">系統管理員會收到通知，並提供排除 SxS 元件的選項。</span><span class="sxs-lookup"><span data-stu-id="5efd5-390">The administrator will be notified and will have the option to exclude the SxS Assembly.</span></span>

<span data-ttu-id="5efd5-391">**用戶端**：</span><span class="sxs-lookup"><span data-stu-id="5efd5-391">**Client Side**:</span></span>

<span data-ttu-id="5efd5-392">發佈虛擬應用程式套件時，App-v 5.0 SP2 用戶端會偵測到是否已安裝所需的 SxS 相依性。</span><span class="sxs-lookup"><span data-stu-id="5efd5-392">When publishing a virtual application package, the App-V 5.0 SP2 Client will detect if a required SxS dependency is already installed.</span></span> <span data-ttu-id="5efd5-393">如果相依性在電腦上無法使用，且包含在套件中，則是傳統的 Windows 安裝程式（.**msi**）將會啟動 SxS 元件的安裝。</span><span class="sxs-lookup"><span data-stu-id="5efd5-393">If the dependency is unavailable on the computer and it is included in the package, a traditional Windows Installer (.**msi**) installation of the SxS assembly will be initiated.</span></span> <span data-ttu-id="5efd5-394">如先前所述，只需在執行用戶端的電腦上安裝相依性，以確保不會發生 Windows Installer （.msi）安裝。</span><span class="sxs-lookup"><span data-stu-id="5efd5-394">As previously documented, simply install the dependency on the computer running the client to ensure that the Windows Installer (.msi) installation will not occur.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5efd5-395">步驟</span><span class="sxs-lookup"><span data-stu-id="5efd5-395">Step</span></span></th>
<th align="left"><span data-ttu-id="5efd5-396">考量</span><span class="sxs-lookup"><span data-stu-id="5efd5-396">Considerations</span></span></th>
<th align="left"><span data-ttu-id="5efd5-397">權益</span><span class="sxs-lookup"><span data-stu-id="5efd5-397">Benefits</span></span></th>
<th align="left"><span data-ttu-id="5efd5-398">負面</span><span class="sxs-lookup"><span data-stu-id="5efd5-398">Tradeoffs</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5efd5-399">選擇性地使用動態設定檔</span><span class="sxs-lookup"><span data-stu-id="5efd5-399">Selectively Employ Dynamic Configuration files</span></span></p></td>
<td align="left"><p><span data-ttu-id="5efd5-400">App-v 5.0 用戶端必須分析並處理這些動態設定檔。</span><span class="sxs-lookup"><span data-stu-id="5efd5-400">The App-V 5.0 client must parse and process these Dynamic Configuration files.</span></span></p>
<p><span data-ttu-id="5efd5-401">關注檔案的大小與複雜性（腳本執行、VREG 包含/排除）。</span><span class="sxs-lookup"><span data-stu-id="5efd5-401">Be conscious of size and complexity (script execution, VREG inclusions/exclusions) of the file.</span></span></p>
<p><span data-ttu-id="5efd5-402">許多虛擬應用程式套件可能已經擁有使用者或電腦專用的動態配置檔案。</span><span class="sxs-lookup"><span data-stu-id="5efd5-402">Numerous virtual application packages may already have User- or computer–specific dynamic configurations files.</span></span></p></td>
<td align="left"><p><span data-ttu-id="5efd5-403">如果有選擇性地使用這些檔案或根本不使用，發佈時間就會得到改善。</span><span class="sxs-lookup"><span data-stu-id="5efd5-403">Publishing times will improve if these files are used selectively or not at all.</span></span></p></td>
<td align="left"><p><span data-ttu-id="5efd5-404">虛擬應用程式套件需要個別重新配置，或是透過 App V 伺服器管理主控台來移除相關聯的動態設定檔案。</span><span class="sxs-lookup"><span data-stu-id="5efd5-404">Virtual application packages would need to be reconfigured individually or via the App-V server management console to remove associated Dynamic Configuration files.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="5efd5-405">使用 Powershell 停用動態設定</span><span class="sxs-lookup"><span data-stu-id="5efd5-405">Disabling a Dynamic Configuration using Powershell</span></span>

-   <span data-ttu-id="5efd5-406">在已發佈的套件中，您可以使用 `Set-AppVClientPackage –Name Myapp –Path c:\Packages\Apps\MyApp.appv` 不含</span><span class="sxs-lookup"><span data-stu-id="5efd5-406">For already published packages, you can use `Set-AppVClientPackage –Name Myapp –Path c:\Packages\Apps\MyApp.appv` without</span></span>

    <span data-ttu-id="5efd5-407">**-DynamicDeploymentConfiguration**參數</span><span class="sxs-lookup"><span data-stu-id="5efd5-407">**-DynamicDeploymentConfiguration** parameter</span></span>

-   <span data-ttu-id="5efd5-408">同樣地，當您使用來新增套件時 `Add-AppVClientPackage –Path c:\Packages\Apps\MyApp.appv` ，請不要使用</span><span class="sxs-lookup"><span data-stu-id="5efd5-408">Similarly, when adding new packages using `Add-AppVClientPackage –Path c:\Packages\Apps\MyApp.appv`, do not use the</span></span>

    <span data-ttu-id="5efd5-409">**-DynamicDeploymentConfiguration**參數。</span><span class="sxs-lookup"><span data-stu-id="5efd5-409">**-DynamicDeploymentConfiguration** parameter.</span></span>

<span data-ttu-id="5efd5-410">如需有關如何套用動態設定的檔，請參閱：</span><span class="sxs-lookup"><span data-stu-id="5efd5-410">For documentation on How to Apply a Dynamic Configuration, see:</span></span>

-   [<span data-ttu-id="5efd5-411">如何使用 PowerShell 來套用使用者設定檔案</span><span class="sxs-lookup"><span data-stu-id="5efd5-411">How to Apply the User Configuration File by Using PowerShell</span></span>](how-to-apply-the-user-configuration-file-by-using-powershell.md)

-   [<span data-ttu-id="5efd5-412">如何使用 PowerShell 來套用部署設定檔案</span><span class="sxs-lookup"><span data-stu-id="5efd5-412">How to Apply the Deployment Configuration File by Using PowerShell</span></span>](how-to-apply-the-deployment-configuration-file-by-using-powershell.md)

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5efd5-413">步驟</span><span class="sxs-lookup"><span data-stu-id="5efd5-413">Step</span></span></th>
<th align="left"><span data-ttu-id="5efd5-414">考量</span><span class="sxs-lookup"><span data-stu-id="5efd5-414">Considerations</span></span></th>
<th align="left"><span data-ttu-id="5efd5-415">權益</span><span class="sxs-lookup"><span data-stu-id="5efd5-415">Benefits</span></span></th>
<th align="left"><span data-ttu-id="5efd5-416">負面</span><span class="sxs-lookup"><span data-stu-id="5efd5-416">Tradeoffs</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5efd5-417">在套件生命週期期間執行同步腳本的帳戶。</span><span class="sxs-lookup"><span data-stu-id="5efd5-417">Account for Synchronous Script Execution during Package Lifecycle.</span></span></p></td>
<td align="left"><p><span data-ttu-id="5efd5-418">如果將腳本宣傳資料內嵌在套件中，Add （Powershell）可能會有很大的下降速度。</span><span class="sxs-lookup"><span data-stu-id="5efd5-418">If script collateral is embedded in the package, Add (Powershell) may be significantly slower.</span></span></p>
<p><span data-ttu-id="5efd5-419">在虛擬應用程式啟動期間執行腳本（StartVirtualEnvironment、StartProcess）和/或 Add + 發佈會影響在一或多個這些週期作業期間的感知效能。</span><span class="sxs-lookup"><span data-stu-id="5efd5-419">Running of scripts during virtual application launch (StartVirtualEnvironment, StartProcess) and/or Add+Publish will impact the perceived performance during one or more of these lifecycle operations.</span></span></p></td>
<td align="left"><p><span data-ttu-id="5efd5-420">使用非同步（無封鎖）腳本可確保週期作業能有效完成。</span><span class="sxs-lookup"><span data-stu-id="5efd5-420">Use of Asynchronous (Non-Blocking) Scripts will ensure that the lifecycle operations complete efficiently.</span></span></p></td>
<td align="left"><p><span data-ttu-id="5efd5-421">這個步驟需要使用內嵌的腳本宣傳資料（具有相關聯的動態配置檔案，以及同步處理及執行腳本）的所有虛擬應用程式套件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="5efd5-421">This step requires working knowledge of all virtual application packages with embedded script collateral, which have associated dynamic configurations files and which reference and run scripts synchronously.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5efd5-422">從套件中移除無關的虛擬字型。</span><span class="sxs-lookup"><span data-stu-id="5efd5-422">Remove Extraneous Virtual Fonts from Package.</span></span></p></td>
<td align="left"><p><span data-ttu-id="5efd5-423">App-V 產品小組所調查的大部分應用程式都包含少量字型，通常少於20個。</span><span class="sxs-lookup"><span data-stu-id="5efd5-423">The majority of applications investigated by the App-V product team contained a small number of fonts, typically fewer than 20.</span></span></p></td>
<td align="left"><p><span data-ttu-id="5efd5-424">虛擬字型會影響發佈更新效能。</span><span class="sxs-lookup"><span data-stu-id="5efd5-424">Virtual Fonts impact publishing refresh performance.</span></span></p></td>
<td align="left"><p><span data-ttu-id="5efd5-425">需要在本機啟用/安裝所需的字型。</span><span class="sxs-lookup"><span data-stu-id="5efd5-425">Desired fonts will need to be enabled/installed natively.</span></span> <span data-ttu-id="5efd5-426">如需相關指示，請參閱安裝或卸載字型。</span><span class="sxs-lookup"><span data-stu-id="5efd5-426">For instructions, see Install or uninstall fonts.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="5efd5-427">判斷套件中存在哪些虛擬字型</span><span class="sxs-lookup"><span data-stu-id="5efd5-427">Determining what virtual fonts exist in the package</span></span>

-   <span data-ttu-id="5efd5-428">製作套件的複本。</span><span class="sxs-lookup"><span data-stu-id="5efd5-428">Make a copy of the package.</span></span>

-   <span data-ttu-id="5efd5-429">將套件 \ _copy 的 appv 重新命名為 Package\_copy.zip</span><span class="sxs-lookup"><span data-stu-id="5efd5-429">Rename Package\_copy.appv to Package\_copy.zip</span></span>

-   <span data-ttu-id="5efd5-430">開啟 AppxManifest.xml 並找出下列專案：</span><span class="sxs-lookup"><span data-stu-id="5efd5-430">Open AppxManifest.xml and locate the following:</span></span>

    <span data-ttu-id="5efd5-431">&lt;appv：延伸類別 = "AppV. Fonts"&gt;</span><span class="sxs-lookup"><span data-stu-id="5efd5-431">&lt;appv:Extension Category="AppV.Fonts"&gt;</span></span>

    <span data-ttu-id="5efd5-432">&lt;appv：字型&gt;</span><span class="sxs-lookup"><span data-stu-id="5efd5-432">&lt;appv:Fonts&gt;</span></span>

    <span data-ttu-id="5efd5-433">&lt;appv：字型路徑 = "\ [{Fonts} \] \\private\\CalibriL.ttf" DelayLoad = "true" &gt; &lt; /Appv： Font&gt;</span><span class="sxs-lookup"><span data-stu-id="5efd5-433">&lt;appv:Font Path="\[{Fonts}\]\\private\\CalibriL.ttf" DelayLoad="true"&gt;&lt;/appv:Font&gt;</span></span>

    **<span data-ttu-id="5efd5-434">注意</span><span class="sxs-lookup"><span data-stu-id="5efd5-434">Note</span></span>**  
    <span data-ttu-id="5efd5-435">如果有標示為**DelayLoad**的字型，這些字型將不會影響第一次啟動。</span><span class="sxs-lookup"><span data-stu-id="5efd5-435">If there are fonts marked as **DelayLoad**, those will not impact first launch.</span></span>



~~~
&lt;/appv:Fonts&gt;
~~~

### <span data-ttu-id="5efd5-436">從套件中排除虛擬字型</span><span class="sxs-lookup"><span data-stu-id="5efd5-436">Excluding virtual fonts from the package</span></span>

<span data-ttu-id="5efd5-437">針對電腦上所有使用者、特定使用者或使用者的使用者設定，使用最符合使用者範圍的動態設定檔。</span><span class="sxs-lookup"><span data-stu-id="5efd5-437">Use the dynamic configuration file that best suits the user scope – deployment configuration for all users on computer, user configuration for specific user or users.</span></span>

-   <span data-ttu-id="5efd5-438">使用 [部署] 或 [使用者設定] 停用字型。</span><span class="sxs-lookup"><span data-stu-id="5efd5-438">Disable fonts with the deployment or user configuration.</span></span>

<span data-ttu-id="5efd5-439">字型</span><span class="sxs-lookup"><span data-stu-id="5efd5-439">Fonts</span></span>

--&gt;

<span data-ttu-id="5efd5-440">&lt;已啟用的字型 = "false"/&gt;</span><span class="sxs-lookup"><span data-stu-id="5efd5-440">&lt;Fonts Enabled="false" /&gt;</span></span>

<span data-ttu-id="5efd5-441">&lt;!--</span><span class="sxs-lookup"><span data-stu-id="5efd5-441">&lt;!--</span></span>

## <a href="" id="bkmk-terms1"></a> <span data-ttu-id="5efd5-442">App-V 5.0 效能指南術語</span><span class="sxs-lookup"><span data-stu-id="5efd5-442">App-V 5.0 Performance Guidance Terminology</span></span>


<span data-ttu-id="5efd5-443">描述與 App-v 5.0 效能優化相關的概念和動作時，會用到下列字詞。</span><span class="sxs-lookup"><span data-stu-id="5efd5-443">The following terms are used when describing concepts and actions related to App-V 5.0 performance optimization.</span></span>

-   <span data-ttu-id="5efd5-444">**複雜性**–指的是一或多個在預設定（**AppvClientPackage**）或整合（**Publish-AppvClientPackage**）期間可能會影響效能的封裝特性。</span><span class="sxs-lookup"><span data-stu-id="5efd5-444">**Complexity** – Refers to the one or more package characteristics that may impact performance during pre-configure (**Add-AppvClientPackage**) or integration (**Publish-AppvClientPackage**).</span></span> <span data-ttu-id="5efd5-445">一些範例特性包括：資訊清單大小、虛擬字型數、檔案數目。</span><span class="sxs-lookup"><span data-stu-id="5efd5-445">Some example characteristics are: manifest size, number of virtual fonts, number of files.</span></span>

-   <span data-ttu-id="5efd5-446">**取消整合**–移除使用者整合</span><span class="sxs-lookup"><span data-stu-id="5efd5-446">**De-Integrate** – Removes the user integrations</span></span>

-   <span data-ttu-id="5efd5-447">**重新整合**–運用使用者整合。</span><span class="sxs-lookup"><span data-stu-id="5efd5-447">**Re-Integrate** – Applies the user integrations.</span></span>

-   <span data-ttu-id="5efd5-448">**非持久，彙集**-在每次登入時，建立執行虛擬環境的電腦。</span><span class="sxs-lookup"><span data-stu-id="5efd5-448">**Non-Persistent, Pooled** – Creates a computer running a virtual environment each time they log in.</span></span>

-   <span data-ttu-id="5efd5-449">**Persistent，個人**–執行虛擬環境的電腦，每次登入都保持不變。</span><span class="sxs-lookup"><span data-stu-id="5efd5-449">**Persistent, Personal** – A computer running a virtual environment that remains the same for every login.</span></span>

-   <span data-ttu-id="5efd5-450">[有**狀態**-適用于此檔]，表示使用者整合是在會話之間保留，而使用者環境管理技術則與非持久性 RDSH 或 VDI 搭配使用。</span><span class="sxs-lookup"><span data-stu-id="5efd5-450">**Stateful** - For this document, implies that user integrations are persisted between sessions and a user environment management technology is used in conjunction with non-persistent RDSH or VDI.</span></span>

-   <span data-ttu-id="5efd5-451">**無狀態**–代表沒有在會話之間保留任何使用者狀態的情況。</span><span class="sxs-lookup"><span data-stu-id="5efd5-451">**Stateless** – Represents a scenario when no user state is persisted between sessions.</span></span>

-   <span data-ttu-id="5efd5-452">**Trigger** –（或原生動作觸發程式）。</span><span class="sxs-lookup"><span data-stu-id="5efd5-452">**Trigger** – (or Native Action Triggers).</span></span> <span data-ttu-id="5efd5-453">UPM 使用這些類型的觸發程式來啟動監視或同步處理作業。</span><span class="sxs-lookup"><span data-stu-id="5efd5-453">UPM uses these types of triggers to initiate monitoring or synchronization operations.</span></span>

-   <span data-ttu-id="5efd5-454">**使用者體驗**-在 App-V 5.0 的內容中，使用者體驗（quantitatively）是下列各部分的總和：</span><span class="sxs-lookup"><span data-stu-id="5efd5-454">**User Experience** - In the context of App-V 5.0, the user experience, quantitatively, is the sum of the following parts:</span></span>

    -   <span data-ttu-id="5efd5-455">使用者在能操縱桌面時，啟動登入的點。</span><span class="sxs-lookup"><span data-stu-id="5efd5-455">From the point that users initiate a log-in to when they are able to manipulate the desktop.</span></span>

    -   <span data-ttu-id="5efd5-456">在使用 App-v 5.0 full server 基礎結構時，從桌面可以與發佈重新整理開始（在 PowerShell 術語中為同步處理）的點。</span><span class="sxs-lookup"><span data-stu-id="5efd5-456">From the point where the desktop can be interacted with to the point a publishing refresh begins (in PowerShell terms, sync) when using the App-V 5.0 full server infrastructure.</span></span> <span data-ttu-id="5efd5-457">在獨立實例中，啟動 [**載入 AppVClientPackage** ] 和 [**發佈-AppVClientPackage] Powershell**命令。</span><span class="sxs-lookup"><span data-stu-id="5efd5-457">In standalone instances, it is when the **Add-AppVClientPackage** and **Publish-AppVClientPackage Powershell** commands are initiated.</span></span>

    -   <span data-ttu-id="5efd5-458">[從開始-完成] 發佈重新整理。</span><span class="sxs-lookup"><span data-stu-id="5efd5-458">From start to completion of the publishing refresh.</span></span> <span data-ttu-id="5efd5-459">在獨立實例中，這是第一次發佈的虛擬應用程式。</span><span class="sxs-lookup"><span data-stu-id="5efd5-459">In standalone instances, this is the first to last virtual application published.</span></span>

    -   <span data-ttu-id="5efd5-460">從可從快捷方式啟動虛擬應用程式的位置。</span><span class="sxs-lookup"><span data-stu-id="5efd5-460">From the point where the virtual application is available to launch from a shortcut.</span></span> <span data-ttu-id="5efd5-461">或者，它是從已登錄檔案類型關聯的點開始，並啟動指定的虛擬應用程式。</span><span class="sxs-lookup"><span data-stu-id="5efd5-461">Alternatively, it is from the point at which the file type association is registered and will launch a specified virtual application.</span></span>

-   <span data-ttu-id="5efd5-462">**使用者設定檔管理**–管理與環境相關的使用者元件的可控與結構化方法。</span><span class="sxs-lookup"><span data-stu-id="5efd5-462">**User Profile Management** – The controlled and structured approach to managing user components associated with the environment.</span></span> <span data-ttu-id="5efd5-463">例如，使用者設定檔、喜好設定與原則管理、應用程式控制和應用程式部署。</span><span class="sxs-lookup"><span data-stu-id="5efd5-463">For example, user profiles, preference and policy management, application control and application deployment.</span></span> <span data-ttu-id="5efd5-464">您可以使用腳本或協力廠商解決方案視需要設定環境。</span><span class="sxs-lookup"><span data-stu-id="5efd5-464">You can use scripting or third-party solutions configure the environment as needed.</span></span>






## <span data-ttu-id="5efd5-465">相關主題</span><span class="sxs-lookup"><span data-stu-id="5efd5-465">Related topics</span></span>


[<span data-ttu-id="5efd5-466">Microsoft Application Virtualization 5.0 系統管理員指南</span><span class="sxs-lookup"><span data-stu-id="5efd5-466">Microsoft Application Virtualization 5.0 Administrator's Guide</span></span>](microsoft-application-virtualization-50-administrators-guide.md)









