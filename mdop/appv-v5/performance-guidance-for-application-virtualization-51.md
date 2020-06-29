---
title: Application Virtualization 5.1 的效能指引
description: Application Virtualization 5.1 的效能指引
author: dansimp
ms.assetid: 5f2643c7-5cf7-4a29-adb7-45bf9f5b0364
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 3382a7958e12cc28b8101a6d5b7384a6975e6e82
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800364"
---
# <span data-ttu-id="aafd2-103">Application Virtualization 5.1 的效能指引</span><span class="sxs-lookup"><span data-stu-id="aafd2-103">Performance Guidance for Application Virtualization 5.1</span></span>


<span data-ttu-id="aafd2-104">瞭解如何設定 App-V 5.1 以取得最佳效能、優化虛擬 App 套件，以及使用 RDS 和 VDI 提供較佳的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="aafd2-104">Learn how to configure App-V 5.1 for optimal performance, optimize virtual app packages, and provide a better user experience with RDS and VDI.</span></span>

<span data-ttu-id="aafd2-105">實現多個方法可協助您改善最終使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="aafd2-105">Implementing multiple methods can help you improve the end-user experience.</span></span> <span data-ttu-id="aafd2-106">不過，您的環境可能不支援所有方法。</span><span class="sxs-lookup"><span data-stu-id="aafd2-106">However, your environment may not support all methods.</span></span>

<span data-ttu-id="aafd2-107">閱讀此檔之前，您應該閱讀並瞭解下列資訊。</span><span class="sxs-lookup"><span data-stu-id="aafd2-107">You should read and understand the following information before reading this document.</span></span>

-   [<span data-ttu-id="aafd2-108">Microsoft Application Virtualization 5.1 系統管理員指南</span><span class="sxs-lookup"><span data-stu-id="aafd2-108">Microsoft Application Virtualization 5.1 Administrator's Guide</span></span>](microsoft-application-virtualization-51-administrators-guide.md)

-   [<span data-ttu-id="aafd2-109">App-v 5 SP2 應用程式發佈與用戶端互動</span><span class="sxs-lookup"><span data-stu-id="aafd2-109">App-V 5 SP2 Application Publishing and Client Interaction</span></span>](https://go.microsoft.com/fwlink/?LinkId=395206)

-   [<span data-ttu-id="aafd2-110">Microsoft Application Virtualization 排序指南</span><span class="sxs-lookup"><span data-stu-id="aafd2-110">Microsoft Application Virtualization Sequencing Guide</span></span>](https://go.microsoft.com/fwlink/?LinkId=269953)

**<span data-ttu-id="aafd2-111">注意</span><span class="sxs-lookup"><span data-stu-id="aafd2-111">Note</span></span>**  
<span data-ttu-id="aafd2-112">根據外部來源和內容，此檔中使用的一些字詞可能會有不同的含義。</span><span class="sxs-lookup"><span data-stu-id="aafd2-112">Some terms used in this document may have different meanings depending on external source and context.</span></span> <span data-ttu-id="aafd2-113">如需本檔中所使用之術語的詳細資訊，後面加上星號 **\\** \* 請參閱本檔的[Application Virtualization 效能指南術語](#bkmk-terms1)一節。</span><span class="sxs-lookup"><span data-stu-id="aafd2-113">For more information about terms used in this document followed by an asterisk **\\**\* review the [Application Virtualization Performance Guidance Terminology](#bkmk-terms1) section of this document.</span></span>



<span data-ttu-id="aafd2-114">最後，本檔將提供資訊來設定執行 App-v 5.1 用戶端的電腦，以及最佳效能。</span><span class="sxs-lookup"><span data-stu-id="aafd2-114">Finally, this document will provide you with the information to configure the computer running App-V 5.1 client and the environment for optimal performance.</span></span> <span data-ttu-id="aafd2-115">使用 sequencer 來優化您的虛擬應用程式套件，並瞭解如何使用使用者體驗虛擬化（UE-V）或其他使用者環境管理技術，以在遠端桌面服務（RDS）和非持久性虛擬桌面基礎結構（VDI）中使用 App-v 5.1 提供最佳的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="aafd2-115">Optimize your virtual application packages for performance using the sequencer, and to understand how to use User Experience Virtualization (UE-V) or other user environment management technologies to provide the optimal user experience with App-V 5.1 in both Remote Desktop Services (RDS) and non-persistent virtual desktop infrastructure (VDI).</span></span>

<span data-ttu-id="aafd2-116">若要協助判斷與您的環境相關的資訊，您應該查看每個區段的簡短概述及適用性檢查清單。</span><span class="sxs-lookup"><span data-stu-id="aafd2-116">To help determine what information is relevant to your environment you should review each section’s brief overview and applicability checklist.</span></span>

## <a href="" id="---------app-v-5-1-in-stateful--non-persistent-deployments"></a> <span data-ttu-id="aafd2-117">在狀態 \ \* 非持續性部署中的 app-v 5。1</span><span class="sxs-lookup"><span data-stu-id="aafd2-117">App-V 5.1 in stateful\* non-persistent deployments</span></span>


<span data-ttu-id="aafd2-118">本節提供一種方法的相關資訊，協助確保使用者在登入後的幾秒鐘內就能存取所有的虛擬應用程式。</span><span class="sxs-lookup"><span data-stu-id="aafd2-118">This section provides information about an approach that helps ensure a user will have access to all virtual applications within seconds after logging in.</span></span> <span data-ttu-id="aafd2-119">如此一來，就能以唯一的方式來解決經常執行的 App-v 5.1 發佈重新整理。</span><span class="sxs-lookup"><span data-stu-id="aafd2-119">This is achieved by uniquely addressing the often long-running App-V 5.1 publishing refresh.</span></span> <span data-ttu-id="aafd2-120">您會發現此方法的基礎，這是最快的發佈重新整理，就是不需要實際執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="aafd2-120">As you will discover the basis of the approach, the fastest publishing refresh, is one that doesn’t have to actually do anything.</span></span> <span data-ttu-id="aafd2-121">必須符合幾個條件，並遵循步驟來提供最佳的使用者體驗。</span><span class="sxs-lookup"><span data-stu-id="aafd2-121">A number of conditions must be met and steps followed to provide the optimal user experience.</span></span>

<span data-ttu-id="aafd2-122">如需詳細資訊，請使用下一節中的資訊：</span><span class="sxs-lookup"><span data-stu-id="aafd2-122">Use the information in the following section for more information:</span></span>

<span data-ttu-id="aafd2-123">[使用案例](#bkmk-us)-當您查看兩種情況時，請記住這些是最極端的方法。</span><span class="sxs-lookup"><span data-stu-id="aafd2-123">[Usage Scenarios](#bkmk-us) - As you review the two scenarios, keep in mind that these are the approach extremes.</span></span> <span data-ttu-id="aafd2-124">根據您的使用需求，您可以選擇將這些步驟套用至使用者和/或虛擬應用程式套件的子集。</span><span class="sxs-lookup"><span data-stu-id="aafd2-124">Based on your usage requirements, you may choose to apply these steps to a subset of users and/or virtual applications packages.</span></span>

-   <span data-ttu-id="aafd2-125">針對效能優化-若要提供最佳的體驗，您可以預期基本影像包含部分 App-v 虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="aafd2-125">Optimized for Performance – To provide the optimal experience, you can expect the base image to include some of the App-V virtual application package.</span></span> <span data-ttu-id="aafd2-126">本文將討論這及其他需求。</span><span class="sxs-lookup"><span data-stu-id="aafd2-126">This and other requirements are discussed.</span></span>

-   <span data-ttu-id="aafd2-127">針對儲存進行優化-如果您關心儲存空間的影響，請遵循這個案例將協助解決這些問題。</span><span class="sxs-lookup"><span data-stu-id="aafd2-127">Optimized for Storage – If you are concerned with the storage impact, following this scenario will help address those concerns.</span></span>

[<span data-ttu-id="aafd2-128">準備您的環境</span><span class="sxs-lookup"><span data-stu-id="aafd2-128">Preparing your Environment</span></span>](#bkmk-pe)

-   <span data-ttu-id="aafd2-129">準備基本映射的步驟（無論是在非持久性 VDI 或 RDSH 環境中），基本映射中必須完成幾個步驟，才能啟用此方法。</span><span class="sxs-lookup"><span data-stu-id="aafd2-129">Steps to Prepare the Base Image – Whether in a non-persistent VDI or RDSH environment, only a few steps must be completed in the base image to enable this approach.</span></span>

-   <span data-ttu-id="aafd2-130">使用 UE-V 2.1 做為應用程式 V 方法的使用者設定檔管理（UPM）方案–這種方法的基礎是 UEM 解決方案只保留幾個註冊表和檔案位置的內容的能力。</span><span class="sxs-lookup"><span data-stu-id="aafd2-130">Use UE-V 2.1 as the User Profile Management (UPM) solution for the App-V approach – the cornerstone of this approach is the ability of a UEM solution to persist the contents of just a few registry and file locations.</span></span> <span data-ttu-id="aafd2-131">這些位置組成使用者整合 \ \*。</span><span class="sxs-lookup"><span data-stu-id="aafd2-131">These locations constitute the user integrations\*.</span></span> <span data-ttu-id="aafd2-132">請務必審查 UPM 方案的特定需求。</span><span class="sxs-lookup"><span data-stu-id="aafd2-132">Be sure to review the specific requirements for the UPM solution.</span></span>

[<span data-ttu-id="aafd2-133">使用者體驗逐步指導</span><span class="sxs-lookup"><span data-stu-id="aafd2-133">User Experience Walk-through</span></span>](#bkmk-uewt)

-   <span data-ttu-id="aafd2-134">逐步引導–這是 App V 與 UE-V 作業的逐步逐步引導，以及使用者應該擁有的預期。</span><span class="sxs-lookup"><span data-stu-id="aafd2-134">Walk-through – This is a step-by-step walk-through of the App-V and UE-V operations and the expectations users should have.</span></span>

-   <span data-ttu-id="aafd2-135">結果–這會說明預期的結果。</span><span class="sxs-lookup"><span data-stu-id="aafd2-135">Outcome – This describes the expected results.</span></span>

[<span data-ttu-id="aafd2-136">對套件生命週期的影響</span><span class="sxs-lookup"><span data-stu-id="aafd2-136">Impact to Package Lifecycle</span></span>](#bkmk-plc)

[<span data-ttu-id="aafd2-137">透過效能優化/調整來加強 VDI 體驗</span><span class="sxs-lookup"><span data-stu-id="aafd2-137">Enhancing the VDI Experience through Performance Optimization/Tuning</span></span>](#bkmk-evdi)

### <a href="" id="applicability-checklist-"></a><span data-ttu-id="aafd2-138">適用性檢查清單</span><span class="sxs-lookup"><span data-stu-id="aafd2-138">Applicability Checklist</span></span>

<span data-ttu-id="aafd2-139">部署環境</span><span class="sxs-lookup"><span data-stu-id="aafd2-139">Deployment Environment</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="aafd2-140">非持久性 VDI 或 RDSH。</span><span class="sxs-lookup"><span data-stu-id="aafd2-140">Non-Persistent VDI or RDSH.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="aafd2-141">使用者體驗虛擬化（UE-V）、其他 UPM 解決方案或使用者設定檔磁片（UPD）。</span><span class="sxs-lookup"><span data-stu-id="aafd2-141">User Experience Virtualization (UE-V), other UPM solutions or User Profile Disks (UPD).</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="aafd2-142">預期配置</span><span class="sxs-lookup"><span data-stu-id="aafd2-142">Expected Configuration</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="aafd2-143">使用者體驗虛擬化（UE-V），其中已啟用 App-v 使用者狀態範本或使用者設定檔管理（UPM）軟體。</span><span class="sxs-lookup"><span data-stu-id="aafd2-143">User Experience Virtualization (UE-V) with the App-V user state template enabled or User Profile Management (UPM) software.</span></span> <span data-ttu-id="aafd2-144">非 UE-V UPM 軟體必須能夠在登入或處理/應用程式啟動和登出時觸發。</span><span class="sxs-lookup"><span data-stu-id="aafd2-144">Non-UE-V UPM software must be capable of triggering on Login or Process/Application Start and Logoff.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="aafd2-145">App-V 共用的內容存儲區（SCS）已設定或可設定。</span><span class="sxs-lookup"><span data-stu-id="aafd2-145">App-V Shared Content Store (SCS) is configured or can be configured.</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="aafd2-146">IT 管理</span><span class="sxs-lookup"><span data-stu-id="aafd2-146">IT Administration</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="aafd2-147">系統管理員可能需要定期更新 VM 基本影像，以確保最佳效能或系統管理員可能需要管理不同使用者群組的多個影像。</span><span class="sxs-lookup"><span data-stu-id="aafd2-147">Admin may need to update the VM base image regularly to ensure optimal performance or Admin may need to manage multiple images for different user groups.</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-us"></a><span data-ttu-id="aafd2-148">使用案例</span><span class="sxs-lookup"><span data-stu-id="aafd2-148">Usage Scenario</span></span>

<span data-ttu-id="aafd2-149">當您複習這兩種情況時，請記住，這些是最極端的做法。</span><span class="sxs-lookup"><span data-stu-id="aafd2-149">As you review the two scenarios, keep in mind that these approach the extremes.</span></span> <span data-ttu-id="aafd2-150">根據您的使用需求，您可以選擇將這些步驟套用到使用者的子集、虛擬應用程式套件，或兩者。</span><span class="sxs-lookup"><span data-stu-id="aafd2-150">Based on your usage requirements, you may choose to apply these steps to a subset of users, virtual application packages, or both.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="aafd2-151">針對效能優化</span><span class="sxs-lookup"><span data-stu-id="aafd2-151">Optimized for Performance</span></span></th>
<th align="left"><span data-ttu-id="aafd2-152">針對儲存進行優化</span><span class="sxs-lookup"><span data-stu-id="aafd2-152">Optimized for Storage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="aafd2-153">為了提供最佳的使用者體驗，此方法會利用 UPM 方案的功能，而且需要額外的影像管理額外負荷。</span><span class="sxs-lookup"><span data-stu-id="aafd2-153">To provide the most optimal user experience, this approach leverages the capabilities of a UPM solution and requires additional image preparation and can incur some additional image management overhead.</span></span></p>
<p><span data-ttu-id="aafd2-154">下列說明在狀態非持續性部署中的許多效能改善。</span><span class="sxs-lookup"><span data-stu-id="aafd2-154">The following describes many performance improvements in stateful non-persistent deployments.</span></span> <span data-ttu-id="aafd2-155">如需詳細資訊，請參閱 <strong> </strong> <strong> </strong> <strong> 此檔的 [請參閱] 區段中 </strong> 的 [針對發佈效能優化套件的先後順序步驟和應用程式-V 順序參考指南]。</span><span class="sxs-lookup"><span data-stu-id="aafd2-155">For more information, see the <strong>Sequencing Steps to Optimize Packages for Publishing Performance</strong> and reference to <strong>App-V Sequencing Guide</strong> in the <strong>See Also section of this document</strong>.</span></span></p></td>
<td align="left"><p><span data-ttu-id="aafd2-156">上述案例的一般預期仍會適用于這裡。</span><span class="sxs-lookup"><span data-stu-id="aafd2-156">The general expectations of the previous scenario still apply here.</span></span> <span data-ttu-id="aafd2-157">不過，請記住，VM 影像通常會儲存在非常昂貴的陣列中;已對此方法進行一些輕微的變更。</span><span class="sxs-lookup"><span data-stu-id="aafd2-157">However, keep in mind that VM images are typically stored in very costly arrays; a slight alteration has been made to the approach.</span></span> <span data-ttu-id="aafd2-158">請勿在基本影像中預先設定以使用者為目標的虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="aafd2-158">Do not pre-configure user-targeted virtual application packages in the base image.</span></span></p>
<p><span data-ttu-id="aafd2-159">這項變更的影響將在這份檔的 [使用者經驗] 演練一節中詳細說明。</span><span class="sxs-lookup"><span data-stu-id="aafd2-159">The impact of this alteration is detailed in the User Experience Walkthrough section of this document.</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-pe"></a><span data-ttu-id="aafd2-160">準備您的環境</span><span class="sxs-lookup"><span data-stu-id="aafd2-160">Preparing your Environment</span></span>

<span data-ttu-id="aafd2-161">下表顯示準備基本映射與 UE-V 或該方法的其他 UPM 方案所需的步驟。</span><span class="sxs-lookup"><span data-stu-id="aafd2-161">The following table displays the required steps to prepare the base image and the UE-V or another UPM solution for the approach.</span></span>

**<span data-ttu-id="aafd2-162">準備基底影像</span><span class="sxs-lookup"><span data-stu-id="aafd2-162">Prepare the Base Image</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="aafd2-163">針對效能優化</span><span class="sxs-lookup"><span data-stu-id="aafd2-163">Optimized for Performance</span></span></th>
<th align="left"><span data-ttu-id="aafd2-164">針對儲存進行優化</span><span class="sxs-lookup"><span data-stu-id="aafd2-164">Optimized for Storage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="aafd2-165">安裝 App-V 5.1 用戶端版本的用戶端。</span><span class="sxs-lookup"><span data-stu-id="aafd2-165">Install the App-V 5.1 client version of the client.</span></span></p></li>
<li><p><span data-ttu-id="aafd2-166">安裝 UE-V，然後從 UE-V 範本庫下載 App-v 設定範本，請參閱下列步驟。</span><span class="sxs-lookup"><span data-stu-id="aafd2-166">Install UE-V and download the App-V Settings Template from the UE-V template Gallery, see the following steps.</span></span></p></li>
<li><p><span data-ttu-id="aafd2-167">針對共用內容儲存區（SCS）模式進行設定。</span><span class="sxs-lookup"><span data-stu-id="aafd2-167">Configure for Shared Content Store (SCS) mode.</span></span> <span data-ttu-id="aafd2-168">如需詳細資訊，請參閱 <a href="how-to-install-the-app-v-51-client-for-shared-content-store-mode.md" data-raw-source="[How to Install the App-V 5.1 Client for Shared Content Store Mode](how-to-install-the-app-v-51-client-for-shared-content-store-mode.md)"> 如何安裝 App-V 5.1 用戶端以取得共用內容存放區模式 </a> 。</span><span class="sxs-lookup"><span data-stu-id="aafd2-168">For more information see <a href="how-to-install-the-app-v-51-client-for-shared-content-store-mode.md" data-raw-source="[How to Install the App-V 5.1 Client for Shared Content Store Mode](how-to-install-the-app-v-51-client-for-shared-content-store-mode.md)">How to Install the App-V 5.1 Client for Shared Content Store Mode</a>.</span></span></p></li>
<li><p><span data-ttu-id="aafd2-169">設定 [在登入登錄註冊表中保留使用者整合] DWORD。</span><span class="sxs-lookup"><span data-stu-id="aafd2-169">Configure Preserve User Integrations on Login Registry DWORD.</span></span></p></li>
<li><p><span data-ttu-id="aafd2-170">預先設定所有的使用者和全域目標套件（例如， <strong> 附加 AppvClientPackage） </strong> 。</span><span class="sxs-lookup"><span data-stu-id="aafd2-170">Pre-configure all user- and global-targeted packages for example, <strong>Add-AppvClientPackage</strong>.</span></span></p></li>
<li><p><span data-ttu-id="aafd2-171">預先設定所有使用者和全域目標連線群組（例如， <strong> 附加 AppvClientConnectionGroup） </strong> 。</span><span class="sxs-lookup"><span data-stu-id="aafd2-171">Pre-configure all user- and global-targeted connection groups for example, <strong>Add-AppvClientConnectionGroup</strong>.</span></span></p></li>
<li><p><span data-ttu-id="aafd2-172">預先發佈所有全域目標套件。</span><span class="sxs-lookup"><span data-stu-id="aafd2-172">Pre-publish all global-targeted packages.</span></span></p>
<p></p>
<p><span data-ttu-id="aafd2-173">當然</span><span class="sxs-lookup"><span data-stu-id="aafd2-173">Alternatively,</span></span></p>
<ul>
<li><p><span data-ttu-id="aafd2-174">執行全域發佈/重新整理。</span><span class="sxs-lookup"><span data-stu-id="aafd2-174">Perform a global publishing/refresh.</span></span></p></li>
<li><p><span data-ttu-id="aafd2-175">執行使用者發佈/重新整理。</span><span class="sxs-lookup"><span data-stu-id="aafd2-175">Perform a user publishing/refresh.</span></span></p></li>
<li><p><span data-ttu-id="aafd2-176">取消發佈所有以使用者為目標的套件。</span><span class="sxs-lookup"><span data-stu-id="aafd2-176">Un-publish all user-targeted packages.</span></span></p></li>
<li><p><span data-ttu-id="aafd2-177">刪除下列使用者虛擬檔案系統（VFS）專案。</span><span class="sxs-lookup"><span data-stu-id="aafd2-177">Delete the following user-Virtual File System (VFS) entries.</span></span></p></li>
</ul>
<p><code>AppData\Local\Microsoft\AppV\Client\VFS</code></p>
<p><code>AppData\Roaming\Microsoft\AppV\Client\VFS</code></p></li>
</ul></td>
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="aafd2-178">安裝 App-V 5.1 用戶端版本的用戶端。</span><span class="sxs-lookup"><span data-stu-id="aafd2-178">Install the App-V 5.1 client version of the client.</span></span></p></li>
<li><p><span data-ttu-id="aafd2-179">安裝 UE-V，然後從 UE-V 範本庫下載 App-v 設定範本，請參閱下列步驟。</span><span class="sxs-lookup"><span data-stu-id="aafd2-179">Install UE-V and download the App-V Settings Template from the UE-V template Gallery, see the following steps.</span></span></p></li>
<li><p><span data-ttu-id="aafd2-180">針對共用內容儲存區（SCS）模式進行設定。</span><span class="sxs-lookup"><span data-stu-id="aafd2-180">Configure for Shared Content Store (SCS) mode.</span></span> <span data-ttu-id="aafd2-181">如需詳細資訊，請參閱 <a href="how-to-install-the-app-v-51-client-for-shared-content-store-mode.md" data-raw-source="[How to Install the App-V 5.1 Client for Shared Content Store Mode](how-to-install-the-app-v-51-client-for-shared-content-store-mode.md)"> 如何安裝 App-V 5.1 用戶端以取得共用內容存放區模式 </a> 。</span><span class="sxs-lookup"><span data-stu-id="aafd2-181">For more information see <a href="how-to-install-the-app-v-51-client-for-shared-content-store-mode.md" data-raw-source="[How to Install the App-V 5.1 Client for Shared Content Store Mode](how-to-install-the-app-v-51-client-for-shared-content-store-mode.md)">How to Install the App-V 5.1 Client for Shared Content Store Mode</a>.</span></span></p></li>
<li><p><span data-ttu-id="aafd2-182">設定 [在登入登錄註冊表中保留使用者整合] DWORD。</span><span class="sxs-lookup"><span data-stu-id="aafd2-182">Configure Preserve User Integrations on Login Registry DWORD.</span></span></p></li>
<li><p><span data-ttu-id="aafd2-183">預先設定所有全域目標套件（例如， <strong> 附加 AppvClientPackage） </strong> 。</span><span class="sxs-lookup"><span data-stu-id="aafd2-183">Pre-configure all global-targeted packages for example, <strong>Add-AppvClientPackage</strong>.</span></span></p></li>
<li><p><span data-ttu-id="aafd2-184">預先設定所有全域目標連線群組（例如， <strong> 附加 AppvClientConnectionGroup） </strong> 。</span><span class="sxs-lookup"><span data-stu-id="aafd2-184">Pre-configure all global-targeted connection groups for example, <strong>Add-AppvClientConnectionGroup</strong>.</span></span></p></li>
<li><p><span data-ttu-id="aafd2-185">預先發佈所有全域目標套件。</span><span class="sxs-lookup"><span data-stu-id="aafd2-185">Pre-publish all global-targeted packages.</span></span></p>
<p></p></li>
</ul></td>
</tr>
</tbody>
</table>



<span data-ttu-id="aafd2-186">**配置**-適用于重要的 App-v 用戶端設定，若想要更多內容和操作說明，請參閱下列資訊：</span><span class="sxs-lookup"><span data-stu-id="aafd2-186">**Configurations** - For critical App-V Client configurations and for a little more context and how-to, review the following information:</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="aafd2-187">配置設定</span><span class="sxs-lookup"><span data-stu-id="aafd2-187">Configuration Setting</span></span></th>
<th align="left"><span data-ttu-id="aafd2-188">這會有什麼作用？</span><span class="sxs-lookup"><span data-stu-id="aafd2-188">What does this do?</span></span></th>
<th align="left"><span data-ttu-id="aafd2-189">我該如何使用它？</span><span class="sxs-lookup"><span data-stu-id="aafd2-189">How should I use it?</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="aafd2-190">共用內容存放區（SCS）模式</span><span class="sxs-lookup"><span data-stu-id="aafd2-190">Shared Content Store (SCS) Mode</span></span></p>
<ul>
<li><p><span data-ttu-id="aafd2-191">可在 PowerShell 中使用 <strong> AppvClientConfiguration </strong> -SharedContentStoreMode <strong> 設定 </strong> ，或</span><span class="sxs-lookup"><span data-stu-id="aafd2-191">Configurable in PowerShell using <strong>Set- AppvClientConfiguration</strong> –<strong>SharedContentStoreMode</strong>, or</span></span></p></li>
<li><p><span data-ttu-id="aafd2-192">在 App-V 用戶端安裝期間。</span><span class="sxs-lookup"><span data-stu-id="aafd2-192">During installation of the App-V client.</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="aafd2-193">在執行 [共用內容存放區] 時，只會在硬碟上維護髮布資料其他虛擬應用程式資產會保留在記憶體（RAM）中。</span><span class="sxs-lookup"><span data-stu-id="aafd2-193">When running the shared content store only publishing data is maintained on hard disk; other virtual application assets are maintained in memory (RAM).</span></span></p>
<p><span data-ttu-id="aafd2-194">這有助於節省本機儲存空間，並將每秒最小化磁片 i/o （IOPS）。</span><span class="sxs-lookup"><span data-stu-id="aafd2-194">This helps to conserve local storage and minimize disk I/O per second (IOPS).</span></span></p></td>
<td align="left"><p><span data-ttu-id="aafd2-195">當 App-v 用戶端和 SCS 內容伺服器（SAN）之間提供低延遲連線時，建議您這麼做。</span><span class="sxs-lookup"><span data-stu-id="aafd2-195">This is recommended when low-latency connections are available between the App-V Client endpoint and the SCS content server, SAN.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="aafd2-196">PreserveUserIntegrationsOnLogin</span><span class="sxs-lookup"><span data-stu-id="aafd2-196">PreserveUserIntegrationsOnLogin</span></span></p>
<ul>
<li><p><span data-ttu-id="aafd2-197">在 [ <strong> HKEY_LOCAL_MACHINE </strong>  \  <strong> 軟體 </strong>  \  <strong> Microsoft </strong>  \  <strong> AppV </strong>  \  <strong> 用戶端 </strong>  \  <strong> 整合 </strong> ] 下的 [登錄] 中進行設定。</span><span class="sxs-lookup"><span data-stu-id="aafd2-197">Configure in the Registry under <strong>HKEY_LOCAL_MACHINE</strong> \ <strong>Software</strong> \ <strong>Microsoft</strong> \ <strong>AppV</strong> \ <strong>Client</strong> \ <strong>Integration</strong>.</span></span></p></li>
<li><p><span data-ttu-id="aafd2-198"><strong>使用值1建立 DWORD 值 PreserveUserIntegrationsOnLogin </strong> <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="aafd2-198">Create the DWORD value <strong>PreserveUserIntegrationsOnLogin</strong> with a value of <strong>1</strong>.</span></span></p></li>
<li><p><span data-ttu-id="aafd2-199">重新開機應用程式-V 用戶端服務，或重新開機執行 App-v 用戶端的電腦。</span><span class="sxs-lookup"><span data-stu-id="aafd2-199">Restart the App-V client service or restart the computer running the App-V Client.</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="aafd2-200">如果您尚未預先設定（ <strong> 載入 AppvClientPackage </strong> ）特定的套件，且未設定此設定，App-v 用戶端將會解除整合 \*，然後重新整合 \*。</span><span class="sxs-lookup"><span data-stu-id="aafd2-200">If you have not pre-configured (<strong>Add-AppvClientPackage</strong>) a specific package and this setting is not configured, the App-V Client will de-integrate\* the persisted user integrations, then re-integrate\*.</span></span></p>
<p><span data-ttu-id="aafd2-201">針對符合上述條件的每個套件，有效地將作業的兩倍，在發佈/重新整理期間完成。</span><span class="sxs-lookup"><span data-stu-id="aafd2-201">For every package that meets the above conditions, effectively twice the work will be done during publishing/refresh.</span></span></p></td>
<td align="left"><p><span data-ttu-id="aafd2-202">如果您不打算預先設定基本影像中每個可用的使用者套件，請使用此設定。</span><span class="sxs-lookup"><span data-stu-id="aafd2-202">If you don’t plan to pre-configure every available user package in the base image, use this setting.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="aafd2-203">MaxConcurrentPublishingRefresh</span><span class="sxs-lookup"><span data-stu-id="aafd2-203">MaxConcurrentPublishingRefresh</span></span></p>
<ul>
<li><p><span data-ttu-id="aafd2-204">在 [ <strong> HKEY_LOCAL_MACHINE </strong> &lt; 強 &gt; 軟體 </strong>  \  <strong> Microsoft </strong>  \  <strong> AppV </strong> &lt; 加強 &gt; 用戶端 </strong>  \  <strong> 發佈 </strong> ] 底下的 [登錄] 中進行設定。</span><span class="sxs-lookup"><span data-stu-id="aafd2-204">Configure in the Registry under <strong>HKEY_LOCAL_MACHINE</strong> &lt;strong&gt;Software</strong> \ <strong>Microsoft</strong> \ <strong>AppV</strong> &lt;strong&gt;Client</strong> \ <strong>Publishing</strong>.</span></span></p></li>
<li><p><span data-ttu-id="aafd2-205"><strong> </strong> 以所需的併發發佈更新數量限制，建立 DWORD 值 MaxConcurrentPublishingrefresh。</span><span class="sxs-lookup"><span data-stu-id="aafd2-205">Create the DWORD value <strong>MaxConcurrentPublishingrefresh</strong> with the desired maximum number of concurrent publishing refreshes.</span></span></p></li>
<li><p><span data-ttu-id="aafd2-206">App-v 用戶端服務和電腦不需要重新開機。</span><span class="sxs-lookup"><span data-stu-id="aafd2-206">The App-V client service and computer do not need to be restarted.</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="aafd2-207">這個設定決定了可以同時執行發佈重新整理/同步處理的使用者數目。</span><span class="sxs-lookup"><span data-stu-id="aafd2-207">This setting determines the number of users that can perform a publishing refresh/sync at the same time.</span></span> <span data-ttu-id="aafd2-208">預設設定為 [無限制]。</span><span class="sxs-lookup"><span data-stu-id="aafd2-208">The default setting is no limit.</span></span></p></td>
<td align="left"><p><span data-ttu-id="aafd2-209">限制併發發佈的重新整理數可避免過度使用的 CPU 使用量，這可能會影響電腦效能。</span><span class="sxs-lookup"><span data-stu-id="aafd2-209">Limiting the number of concurrent publishing refreshes prevents excessive CPU usage that could impact computer performance.</span></span> <span data-ttu-id="aafd2-210">建議在 RDS 環境中使用這個限制，多個使用者可以同時登入同一部電腦並執行發佈重新整理同步處理。</span><span class="sxs-lookup"><span data-stu-id="aafd2-210">This limit is recommended in an RDS environment, where multiple users can log in to the same computer at the same time and perform a publishing refresh sync.</span></span></p>
<p><span data-ttu-id="aafd2-211">如果達到併發發佈重新整理閾值，發佈新應用程式時所需的時間，並在使用者登入時將它們提供給最終使用者，可能會有不確定的時間長度。</span><span class="sxs-lookup"><span data-stu-id="aafd2-211">If the concurrent publishing refresh threshold is reached, the time required to publish new applications and make them available to end users after they log in could take an indeterminate amount of time.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="aafd2-212">針對 App-v 方法設定 UE-V 解決方案</span><span class="sxs-lookup"><span data-stu-id="aafd2-212">Configure UE-V solution for App-V Approach</span></span>

<span data-ttu-id="aafd2-213">我們建議使用 Microsoft 使用者體驗虛擬化（UE-V）來捕獲並集中特定使用者的應用程式設定和 Windows 作業系統設定。</span><span class="sxs-lookup"><span data-stu-id="aafd2-213">We recommend using Microsoft User Experience Virtualization (UE-V) to capture and centralize application settings and Windows operating system settings for a specific user.</span></span> <span data-ttu-id="aafd2-214">然後，這些設定會套用到使用者所存取的不同電腦，包括桌上型電腦、膝上型電腦和虛擬桌面基礎結構（VDI）會話。</span><span class="sxs-lookup"><span data-stu-id="aafd2-214">These settings are then applied to the different computers that are accessed by the user, including desktop computers, laptop computers, and virtual desktop infrastructure (VDI) sessions.</span></span> <span data-ttu-id="aafd2-215">UE-V 已針對 RDS 和 VDI 案例進行優化。</span><span class="sxs-lookup"><span data-stu-id="aafd2-215">UE-V is optimized for RDS and VDI scenarios.</span></span>

<span data-ttu-id="aafd2-216">如需詳細資訊，請參閱[使用者體驗虛擬化的快速入門 2.0](https://technet.microsoft.com/library/dn458926.aspx)</span><span class="sxs-lookup"><span data-stu-id="aafd2-216">For more information see [Getting Started With User Experience Virtualization 2.0](https://technet.microsoft.com/library/dn458926.aspx)</span></span>

<span data-ttu-id="aafd2-217">實質上，您只需要安裝 UE-V 用戶端，然後從[Microsoft 使用者經驗虛擬化（ue-v）範本庫](https://gallery.technet.microsoft.com/Authored-UE-V-Settings-bb442a33)下載下列 microsoft 撰寫的 app-v 設定範本。</span><span class="sxs-lookup"><span data-stu-id="aafd2-217">In essence all that is required is to install the UE-V client and download the following Microsoft authored App-V settings template from the [Microsoft User Experience Virtualization (UE-V) template gallery](https://gallery.technet.microsoft.com/Authored-UE-V-Settings-bb442a33).</span></span> <span data-ttu-id="aafd2-218">註冊範本。</span><span class="sxs-lookup"><span data-stu-id="aafd2-218">Register the template.</span></span> <span data-ttu-id="aafd2-219">如需 UE-V 範本的詳細資訊，請參閱[用於取得及註冊範本的 ue-v 特定資源](https://technet.microsoft.com/library/dn458926.aspx)。</span><span class="sxs-lookup"><span data-stu-id="aafd2-219">For more information around UE-V templates see [The UE-V specific resource for acquiring and registering the template](https://technet.microsoft.com/library/dn458926.aspx).</span></span>

**<span data-ttu-id="aafd2-220">注意</span><span class="sxs-lookup"><span data-stu-id="aafd2-220">Note</span></span>**  
<span data-ttu-id="aafd2-221">若不執行額外的設定步驟，Microsoft 使用者環境虛擬化（UE-V）將無法同步處理目的電腦上的開始功能表快速鍵（.lnk 檔案）。</span><span class="sxs-lookup"><span data-stu-id="aafd2-221">Without performing an additional configuration step, the Microsoft User Environment Virtualization (UE-V) will not be able to synchronize the Start menu shortcuts (.lnk files) on the target computer.</span></span> <span data-ttu-id="aafd2-222">預設會排除 .lnk 檔案類型。</span><span class="sxs-lookup"><span data-stu-id="aafd2-222">The .lnk file type is excluded by default.</span></span>

<span data-ttu-id="aafd2-223">UE-V 只支援從 RDS 和 VDI 案例中的排除清單中移除 .lnk 檔案類型，而每個使用者的裝置都將有一組相同的應用程式安裝在相同的位置，且每個 .lnk 檔案對於所有使用者的裝置都是有效的。</span><span class="sxs-lookup"><span data-stu-id="aafd2-223">UE-V will only support removing the .lnk file type from the exclusion list in the RDS and VDI scenarios, where every user’s device will have the same set of applications installed to the same location and every .lnk file is valid for all the users’ devices.</span></span> <span data-ttu-id="aafd2-224">例如，UE-V 目前不支援下列2種案例，因為最終結果是該快速鍵將在一個（而非所有）裝置上生效。</span><span class="sxs-lookup"><span data-stu-id="aafd2-224">For example, UE-V would not currently support the following 2 scenarios, because the net result will be that the shortcut will be valid on one but not all devices.</span></span>

-   <span data-ttu-id="aafd2-225">如果使用者已在一部裝置上安裝應用程式，且在另一個裝置上安裝了相同的原生應用程式，且已啟用 .lnk 檔案的不同安裝根目錄。</span><span class="sxs-lookup"><span data-stu-id="aafd2-225">If a user has an application installed on one device with .lnk files enabled and the same native application installed on another device to a different installation root with .lnk files enabled.</span></span>

-   <span data-ttu-id="aafd2-226">如果使用者已在一部裝置上安裝應用程式，但沒有已啟用 .lnk 檔案的其他應用程式。</span><span class="sxs-lookup"><span data-stu-id="aafd2-226">If a user has an application installed on one device but not another with .lnk files enabled.</span></span>



**<span data-ttu-id="aafd2-227">重要</span><span class="sxs-lookup"><span data-stu-id="aafd2-227">Important</span></span>**  
<span data-ttu-id="aafd2-228">本主題說明如何使用 [登錄編輯程式] 變更 Windows 登錄。</span><span class="sxs-lookup"><span data-stu-id="aafd2-228">This topic describes how to change the Windows registry by using Registry Editor.</span></span> <span data-ttu-id="aafd2-229">如果您不正確地變更 Windows 登錄，可能會導致嚴重的問題，可能需要重新安裝 Windows。</span><span class="sxs-lookup"><span data-stu-id="aafd2-229">If you change the Windows registry incorrectly, you can cause serious problems that might require you to reinstall Windows.</span></span> <span data-ttu-id="aafd2-230">變更登錄前，您應該先製作一份登錄檔案（系統 .dat 和使用者 .dat）的備份複本。</span><span class="sxs-lookup"><span data-stu-id="aafd2-230">You should make a backup copy of the registry files (System.dat and User.dat) before you change the registry.</span></span> <span data-ttu-id="aafd2-231">Microsoft 不能保證變更註冊表時可能會發生的問題，可以解決。</span><span class="sxs-lookup"><span data-stu-id="aafd2-231">Microsoft cannot guarantee that the problems that might occur when you change the registry can be resolved.</span></span> <span data-ttu-id="aafd2-232">變更註冊表的風險由您自行承擔。</span><span class="sxs-lookup"><span data-stu-id="aafd2-232">Change the registry at your own risk.</span></span>



<span data-ttu-id="aafd2-233">使用 Microsoft Registry Editor （regedit.exe）流覽至**HKEY \ _LOCAL \ _MACHINE**  \\  **軟體**  \\  **Microsoft**  \\  **UEV**  \\  **Agent**設定  \\  **Configuration**  \\  **ExcludedFileTypes**並從排除的檔案類型中移除 **.lnk** 。</span><span class="sxs-lookup"><span data-stu-id="aafd2-233">Using the Microsoft Registry Editor (regedit.exe), navigate to **HKEY\_LOCAL\_MACHINE** \\ **Software** \\ **Microsoft** \\ **UEV** \\ **Agent** \\ **Configuration** \\ **ExcludedFileTypes** and remove **.lnk** from the excluded file types.</span></span>

**<span data-ttu-id="aafd2-234">針對 App-v 方法設定其他使用者設定檔管理（UPM）方案</span><span class="sxs-lookup"><span data-stu-id="aafd2-234">Configure other User Profile Management (UPM) solution for App-V Approach</span></span>**

<span data-ttu-id="aafd2-235">在有狀態的環境中的預期是已實現 UPM 方案，而且可支援跨會話和登錄之間的使用者資料持續性。</span><span class="sxs-lookup"><span data-stu-id="aafd2-235">The expectation in a stateful environment is that a UPM solution is implemented and can support persistence of user data across sessions and between logins.</span></span>

<span data-ttu-id="aafd2-236">UPM 方案的需求如下所示。</span><span class="sxs-lookup"><span data-stu-id="aafd2-236">The requirements for the UPM solution are as follows.</span></span>

<span data-ttu-id="aafd2-237">若要啟用優化的登入體驗（例如使用者的 app-v 5.1 方法），解決方案必須具備下列各項：</span><span class="sxs-lookup"><span data-stu-id="aafd2-237">To enable an optimized login experience, for example the App-V 5.1 approach for the user, the solution must be capable of:</span></span>

-   <span data-ttu-id="aafd2-238">在使用者設定檔/角色中保留下列使用者整合。</span><span class="sxs-lookup"><span data-stu-id="aafd2-238">Persisting the below user integrations as part of the user profile/persona.</span></span>

-   <span data-ttu-id="aafd2-239">在登入（或應用程式啟動）時觸發使用者設定檔同步處理，可保證在發佈/重新整理開始前已套用所有使用者整合，或者</span><span class="sxs-lookup"><span data-stu-id="aafd2-239">Triggering a user profile sync on login (or application start), which can guarantee that all user integrations are applied before publishing/refresh begin, or,</span></span>

-   <span data-ttu-id="aafd2-240">附加與分離使用者設定檔磁片（UPD）或包含使用者集成的類似技術。</span><span class="sxs-lookup"><span data-stu-id="aafd2-240">Attaching and detaching a user profile disk (UPD) or similar technology that contains the user integrations.</span></span>

    **<span data-ttu-id="aafd2-241">注意</span><span class="sxs-lookup"><span data-stu-id="aafd2-241">Note</span></span>**  
    <span data-ttu-id="aafd2-242">只有在整個設定檔儲存在使用者設定檔磁片上時，才支援使用 UPD。</span><span class="sxs-lookup"><span data-stu-id="aafd2-242">App-V is supported when using UPD only when the entire profile is stored on the user profile disk.</span></span>

    <span data-ttu-id="aafd2-243">將 UPD 與使用者設定檔磁片中儲存的選取資料夾結合使用時，不支援 app-v 套件。</span><span class="sxs-lookup"><span data-stu-id="aafd2-243">App-V packages are not supported when using UPD with selected folders stored in the user profile disk.</span></span> <span data-ttu-id="aafd2-244">[寫入時複製] 驅動程式不會處理 UPD 選取的資料夾。</span><span class="sxs-lookup"><span data-stu-id="aafd2-244">The Copy on Write driver does not handle UPD selected folders.</span></span>



-   <span data-ttu-id="aafd2-245">在會話登出之前，捕獲對位置所做的變更，這些位置組成使用者整合。</span><span class="sxs-lookup"><span data-stu-id="aafd2-245">Capturing changes to the locations, which constitute the user integrations, prior to session logoff.</span></span>

<span data-ttu-id="aafd2-246">在您新增發佈伺服器時，使用 App-v 5.1 （**載入 AppvPublishingServer**），您可以設定同步處理，例如在登入期間進行重新整理，或在指定的重新整理間隔之後進行重新整理。</span><span class="sxs-lookup"><span data-stu-id="aafd2-246">With App-V 5.1 when you add a publishing server (**Add-AppvPublishingServer**) you can configure synchronization, for example refresh during log on and/or after a specified refresh interval.</span></span> <span data-ttu-id="aafd2-247">在這兩種情況下，都會建立排程任務。</span><span class="sxs-lookup"><span data-stu-id="aafd2-247">In both cases a scheduled task is created.</span></span>

<span data-ttu-id="aafd2-248">在舊版 App-V 5.1 中，兩個排程的任務都是使用 VBScript 來啟動使用者和全域重新整理。</span><span class="sxs-lookup"><span data-stu-id="aafd2-248">In previous versions of App-V 5.1, both scheduled tasks were configured using a VBScript that would initiate the user and global refresh.</span></span> <span data-ttu-id="aafd2-249">針對應用程式虛擬化5.0 的修復程式套件4，使用者會在登錄時重新整理（由**SyncAppvPublishingServer.exe**啟動）。</span><span class="sxs-lookup"><span data-stu-id="aafd2-249">With Hotfix Package 4 for Application Virtualization 5.0 SP2 the user refresh on log on was initiated by **SyncAppvPublishingServer.exe**.</span></span> <span data-ttu-id="aafd2-250">引入此變更是為了提供 UPM 解決方案的觸發程式。</span><span class="sxs-lookup"><span data-stu-id="aafd2-250">This change was introduced to provide UPM solutions a trigger process.</span></span> <span data-ttu-id="aafd2-251">這個處理常式會延遲發佈/refresh，以允許 UPM 方案套用使用者整合。</span><span class="sxs-lookup"><span data-stu-id="aafd2-251">This process delays the publish /refresh to allow the UPM solution to apply the user integrations.</span></span> <span data-ttu-id="aafd2-252">發佈/重新整理完成後，就會結束。</span><span class="sxs-lookup"><span data-stu-id="aafd2-252">It will exit once the publishing/refresh is complete.</span></span>

**<span data-ttu-id="aafd2-253">使用者整合</span><span class="sxs-lookup"><span data-stu-id="aafd2-253">User Integrations</span></span>**

<span data-ttu-id="aafd2-254">Registry – HKEY \ _CURRENT \ _USER</span><span class="sxs-lookup"><span data-stu-id="aafd2-254">Registry – HKEY\_CURRENT\_USER</span></span>

-   <span data-ttu-id="aafd2-255">路徑-Software\\Classes</span><span class="sxs-lookup"><span data-stu-id="aafd2-255">Path - Software\\Classes</span></span>

    <span data-ttu-id="aafd2-256">[排除]：本機設定、ActivatableClasses、AppX \ \*</span><span class="sxs-lookup"><span data-stu-id="aafd2-256">Exclude: Local Settings, ActivatableClasses, AppX\*</span></span>

-   <span data-ttu-id="aafd2-257">路徑-Software\\Microsoft\\AppV</span><span class="sxs-lookup"><span data-stu-id="aafd2-257">Path - Software\\Microsoft\\AppV</span></span>

-   <span data-ttu-id="aafd2-258">路徑 Software\\Microsoft\\Windows\\CurrentVersion\\App 路徑</span><span class="sxs-lookup"><span data-stu-id="aafd2-258">Path- Software\\Microsoft\\Windows\\CurrentVersion\\App Paths</span></span>

**<span data-ttu-id="aafd2-259">檔案位置</span><span class="sxs-lookup"><span data-stu-id="aafd2-259">File Locations</span></span>**

-   <span data-ttu-id="aafd2-260">Root-"環境變數" APPDATA</span><span class="sxs-lookup"><span data-stu-id="aafd2-260">Root – “Environment Variable” APPDATA</span></span>

    <span data-ttu-id="aafd2-261">Path – Microsoft\\AppV\\Client\\Catalog</span><span class="sxs-lookup"><span data-stu-id="aafd2-261">Path – Microsoft\\AppV\\Client\\Catalog</span></span>

-   <span data-ttu-id="aafd2-262">Root-"環境變數" APPDATA</span><span class="sxs-lookup"><span data-stu-id="aafd2-262">Root – “Environment Variable” APPDATA</span></span>

    <span data-ttu-id="aafd2-263">Path – Microsoft\\AppV\\Client\\Integration</span><span class="sxs-lookup"><span data-stu-id="aafd2-263">Path – Microsoft\\AppV\\Client\\Integration</span></span>

-   <span data-ttu-id="aafd2-264">Root-"環境變數" APPDATA</span><span class="sxs-lookup"><span data-stu-id="aafd2-264">Root – “Environment Variable” APPDATA</span></span>

    <span data-ttu-id="aafd2-265">Path-Microsoft\\Windows\\Start Menu\\Programs</span><span class="sxs-lookup"><span data-stu-id="aafd2-265">Path - Microsoft\\Windows\\Start Menu\\Programs</span></span>

-   <span data-ttu-id="aafd2-266">（若要保留所有桌面快速鍵、虛擬和非虛擬）</span><span class="sxs-lookup"><span data-stu-id="aafd2-266">(To persist all desktop shortcuts, virtual and non-virtual)</span></span>

    <span data-ttu-id="aafd2-267">Root-"KnownFolder" {B4BFCC3A-DB2C-424C-B029-7FE99A87C641} FileMask-\ \* .lnk</span><span class="sxs-lookup"><span data-stu-id="aafd2-267">Root - “KnownFolder” {B4BFCC3A-DB2C-424C-B029-7FE99A87C641}FileMask - \*.lnk</span></span>

**<span data-ttu-id="aafd2-268">Microsoft 使用者體驗虛擬化（UE-V）</span><span class="sxs-lookup"><span data-stu-id="aafd2-268">Microsoft User Experience Virtualization (UE-V)</span></span>**

<span data-ttu-id="aafd2-269">此外，我們建議使用 Microsoft 使用者體驗虛擬化（UE-V）來捕獲與集中特定使用者的應用程式設定和 Windows 作業系統設定。</span><span class="sxs-lookup"><span data-stu-id="aafd2-269">Additionally, we recommend using Microsoft User Experience Virtualization (UE-V) to capture and centralize application settings and Windows operating system settings for a specific user.</span></span> <span data-ttu-id="aafd2-270">然後，這些設定會套用到使用者所存取的不同電腦，包括桌上型電腦、膝上型電腦和虛擬桌面基礎結構（VDI）會話。</span><span class="sxs-lookup"><span data-stu-id="aafd2-270">These settings are then applied to the different computers that are accessed by the user, including desktop computers, laptop computers, and virtual desktop infrastructure (VDI) sessions.</span></span>

<span data-ttu-id="aafd2-271">如需詳細資訊，請參閱[使用者體驗虛擬化1.0 快速入門](https://technet.microsoft.com/library/jj680015.aspx)和[使用 Ue-v 範本庫共用設定位置範本](https://technet.microsoft.com/library/jj679972.aspx)。</span><span class="sxs-lookup"><span data-stu-id="aafd2-271">For more information see [Getting Started With User Experience Virtualization 1.0](https://technet.microsoft.com/library/jj680015.aspx) and [Sharing Settings Location Templates with the UE-V Template Gallery](https://technet.microsoft.com/library/jj679972.aspx).</span></span>

### <a href="" id="bkmk-uewt"></a><span data-ttu-id="aafd2-272">使用者體驗逐步指導</span><span class="sxs-lookup"><span data-stu-id="aafd2-272">User Experience Walk-through</span></span>

<span data-ttu-id="aafd2-273">以下是 App-V 與 UPM 作業的逐步逐步說明，以及使用者預期的預期。</span><span class="sxs-lookup"><span data-stu-id="aafd2-273">This following is a step-by-step walk-through of the App-V and UPM operations and the expectations users should expect.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="aafd2-274">針對效能優化</span><span class="sxs-lookup"><span data-stu-id="aafd2-274">Optimized for Performance</span></span></th>
<th align="left"><span data-ttu-id="aafd2-275">針對儲存進行優化</span><span class="sxs-lookup"><span data-stu-id="aafd2-275">Optimized for Storage</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="aafd2-276">在 VDI/RDSH 環境中實現此方法之後，請在第一次登入時，</span><span class="sxs-lookup"><span data-stu-id="aafd2-276">After implementing this approach in the VDI/RDSH environment, on first login,</span></span></p>
<ul>
<li><p><span data-ttu-id="aafd2-277">一道啟動使用者發佈/重新整理。</span><span class="sxs-lookup"><span data-stu-id="aafd2-277">(Operation) A user-publishing/refresh is initiated.</span></span> <span data-ttu-id="aafd2-278">認為如果這是使用者第一次發佈的虛擬應用程式（例如非永久性），這將會採取發佈/重新整理的一般持續時間。</span><span class="sxs-lookup"><span data-stu-id="aafd2-278">(Expectation) If this is the first time a user has published virtual applications (e.g. non-persistent), this will take the usual duration of a publishing/refresh.</span></span></p></li>
<li><p><span data-ttu-id="aafd2-279">一道在發佈/重新整理之後，UPM 方案會捕獲使用者整合。</span><span class="sxs-lookup"><span data-stu-id="aafd2-279">(Operation) After the publishing/refresh, the UPM solution captures the user integrations.</span></span> <span data-ttu-id="aafd2-280">認為視 UPM 方案的設定方式而定，這可能會在登出程式中發生。</span><span class="sxs-lookup"><span data-stu-id="aafd2-280">(Expectation) Depending on how the UPM solution is configured, this may occur as part of the logoff process.</span></span> <span data-ttu-id="aafd2-281">這將會產生與使用者狀態保持不變相同/類似的額外負荷。</span><span class="sxs-lookup"><span data-stu-id="aafd2-281">This will incur the same/similar overhead as persisting the user state.</span></span></p></li>
</ul>
<p><span data-ttu-id="aafd2-282">在後續的登錄：</span><span class="sxs-lookup"><span data-stu-id="aafd2-282">On subsequent logins:</span></span></p>
<ul>
<li><p><span data-ttu-id="aafd2-283">一道在發佈/重新整理前，UPM 解決方案會將使用者整合套用至系統。</span><span class="sxs-lookup"><span data-stu-id="aafd2-283">(Operation) UPM solution applies the user integrations to the system prior to publishing/refresh.</span></span></p>
<p><span data-ttu-id="aafd2-284">認為桌面或 [開始] 功能表中將會顯示快捷方式，這會立即起作用。</span><span class="sxs-lookup"><span data-stu-id="aafd2-284">(Expectation) There will be shortcuts present on the desktop, or in the start menu, which work immediately.</span></span> <span data-ttu-id="aafd2-285">發佈/重新整理完成後（亦即封裝權利變更），部分可能會消失。</span><span class="sxs-lookup"><span data-stu-id="aafd2-285">When the publishing/refresh completes (i.e., package entitlements change), some may go away.</span></span></p></li>
<li><p><span data-ttu-id="aafd2-286">一道發佈/重新整理會處理使用者套件權利變更的取消發佈及發佈作業。</span><span class="sxs-lookup"><span data-stu-id="aafd2-286">(Operation) Publishing/refresh will process un-publish and publish operations for changes in user package entitlements.</span></span> <span data-ttu-id="aafd2-287">認為如果沒有任何權利變更，publishing1 將會在幾秒內完成。</span><span class="sxs-lookup"><span data-stu-id="aafd2-287">(Expectation) If there are no entitlement changes, publishing1 will complete in seconds.</span></span> <span data-ttu-id="aafd2-288">否則，發佈/重新整理會相對於虛擬應用程式的數量和複雜性 \* 而增加</span><span class="sxs-lookup"><span data-stu-id="aafd2-288">Otherwise, the publishing/refresh will increase relative to the number and complexity\* of virtual applications</span></span></p></li>
<li><p><span data-ttu-id="aafd2-289">一道UPM 解決方案將在登出時再次捕獲使用者整合。</span><span class="sxs-lookup"><span data-stu-id="aafd2-289">(Operation) UPM solution will capture user integrations again at logoff.</span></span> <span data-ttu-id="aafd2-290">認為與上一節相同。</span><span class="sxs-lookup"><span data-stu-id="aafd2-290">(Expectation) Same as previous.</span></span></p></li>
</ul>
<p><span data-ttu-id="aafd2-291">¹發佈作業（ <strong> 發佈 AppVClientPackage）會 </strong> 將專案新增至使用者目錄、將權利對應給使用者、識別當地商店，以及完成任何整合步驟完成。</span><span class="sxs-lookup"><span data-stu-id="aafd2-291">¹ The publishing operation (<strong>Publish-AppVClientPackage</strong>) adds entries to the user catalog, maps entitlement to the user, identifies the local store, and finishes by completing any integration steps.</span></span></p></td>
<td align="left"><p><span data-ttu-id="aafd2-292">在 VDI/RDSH 環境中實現此方法之後，請在第一次登入時，</span><span class="sxs-lookup"><span data-stu-id="aafd2-292">After implementing this approach in the VDI/RDSH environment, on first login,</span></span></p>
<ul>
<li><p><span data-ttu-id="aafd2-293">一道啟動使用者發佈/重新整理。</span><span class="sxs-lookup"><span data-stu-id="aafd2-293">(Operation) A user-publishing/refresh is initiated.</span></span> <span data-ttu-id="aafd2-294">認為</span><span class="sxs-lookup"><span data-stu-id="aafd2-294">(Expectation)</span></span></p>
<ul>
<li><p><span data-ttu-id="aafd2-295">如果這是使用者第一次發佈虛擬應用程式（例如，非永久性），這將會採取發佈/重新整理的一般持續時間。</span><span class="sxs-lookup"><span data-stu-id="aafd2-295">If this is the first time a user has published virtual applications (e.g., non-persistent), this will take the usual duration of a publishing/refresh.</span></span></p></li>
<li><p><span data-ttu-id="aafd2-296">首先，系統會根據預先設定套件（新增/重新整理）來影響後續的登錄。</span><span class="sxs-lookup"><span data-stu-id="aafd2-296">First and subsequent logins will be impacted by pre-configuring of packages (add/refresh).</span></span></p>
<p></p></li>
</ul></li>
<li><p><span data-ttu-id="aafd2-297">一道在發佈/重新整理之後，UPM 方案會捕獲使用者整合。</span><span class="sxs-lookup"><span data-stu-id="aafd2-297">(Operation) After the publishing/refresh, the UPM solution captures the user integrations.</span></span> <span data-ttu-id="aafd2-298">認為視 UPM 方案的設定方式而定，這可能會在登出程式中發生。</span><span class="sxs-lookup"><span data-stu-id="aafd2-298">(Expectation) Depending on how the UPM solution is configured, this may occur as part of the logoff process.</span></span> <span data-ttu-id="aafd2-299">這將會產生與使用者狀態保持不變的相同/類似負荷</span><span class="sxs-lookup"><span data-stu-id="aafd2-299">This will incur the same/similar overhead as persisting the user state</span></span></p></li>
</ul>
<p><span data-ttu-id="aafd2-300">在後續的登錄：</span><span class="sxs-lookup"><span data-stu-id="aafd2-300">On subsequent logins:</span></span></p>
<ul>
<li><p><span data-ttu-id="aafd2-301">一道在發佈/重新整理前，UPM 解決方案會將使用者整合套用至系統。</span><span class="sxs-lookup"><span data-stu-id="aafd2-301">(Operation) UPM solution applies the user integrations to the system prior to publishing/refresh.</span></span></p></li>
<li><p><span data-ttu-id="aafd2-302">一道[新增/重新整理] 必須預先設定所有由使用者為目標的應用程式。</span><span class="sxs-lookup"><span data-stu-id="aafd2-302">(Operation) Add/refresh must pre-configure all user targeted applications.</span></span> <span data-ttu-id="aafd2-303">認為</span><span class="sxs-lookup"><span data-stu-id="aafd2-303">(Expectation)</span></span></p>
<ul>
<li><p><span data-ttu-id="aafd2-304">這可能會顯著增加應用程式可用性的時間（10秒的順序）。</span><span class="sxs-lookup"><span data-stu-id="aafd2-304">This may increase the time to application availability significantly (on the order of 10’s of seconds).</span></span></p></li>
<li><p><span data-ttu-id="aafd2-305">這會增加相對於虛擬應用程式數目和複雜性 \* 的發佈重新整理時間。</span><span class="sxs-lookup"><span data-stu-id="aafd2-305">This will increase the publishing refresh time relative to the number and complexity\* of virtual applications.</span></span></p>
<p></p></li>
</ul></li>
<li><p><span data-ttu-id="aafd2-306">一道發佈/重新整理將處理取消發佈及發佈作業，以變更使用者套件權利的變更。</span><span class="sxs-lookup"><span data-stu-id="aafd2-306">(Operation) Publishing/refresh will process un-publish and publish operations for changes to user package entitlements.</span></span></p></li>
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
<th align="left"><span data-ttu-id="aafd2-307">負面</span><span class="sxs-lookup"><span data-stu-id="aafd2-307">Outcome</span></span></th>
<th align="left"><span data-ttu-id="aafd2-308">負面</span><span class="sxs-lookup"><span data-stu-id="aafd2-308">Outcome</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p></p>
<ul>
<li><p><span data-ttu-id="aafd2-309">因為使用者整合完全保持不變，所以不需要進行任何工作，例如發佈/重新整理完成的整合。</span><span class="sxs-lookup"><span data-stu-id="aafd2-309">Because the user integrations are entirely preserved, there will be no work for example, integration for the publishing/refresh to complete.</span></span> <span data-ttu-id="aafd2-310">所有虛擬應用程式將在登入後的幾秒鐘內提供。</span><span class="sxs-lookup"><span data-stu-id="aafd2-310">All virtual applications will be available within seconds of login.</span></span></p></li>
<li><p><span data-ttu-id="aafd2-311">發佈/重新整理會將變更處理給擁有虛擬應用程式的使用者，這些使用者會影響體驗。</span><span class="sxs-lookup"><span data-stu-id="aafd2-311">The publishing/refresh will process changes to the users entitled virtual applications which impacts the experience.</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="aafd2-312">因為 [新增/重新整理] 必須重新設定所有虛擬應用程式至 VM，所以每個登入的發佈重新整理時間都會得到延伸。</span><span class="sxs-lookup"><span data-stu-id="aafd2-312">Because the add/refresh must re-configure all the virtual applications to the VM, the publishing refresh time on every login will be extended.</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="bkmk-plc"></a><span data-ttu-id="aafd2-313">影響封裝的生命週期</span><span class="sxs-lookup"><span data-stu-id="aafd2-313">Impact to Package Life Cycle</span></span>

<span data-ttu-id="aafd2-314">升級套件是套件生命週期的一個重要層面。</span><span class="sxs-lookup"><span data-stu-id="aafd2-314">Upgrading a package is a crucial aspect of the package lifecycle.</span></span> <span data-ttu-id="aafd2-315">若要協助使用者能存取適當升級（已發佈）或降級（未發佈）虛擬應用程式套件，建議您更新基本映射以反映這些變更。</span><span class="sxs-lookup"><span data-stu-id="aafd2-315">To help guarantee users have access to the appropriate upgraded (published) or downgraded (un-published) virtual application packages, it is recommended you update the base image to reflect these changes.</span></span> <span data-ttu-id="aafd2-316">若要瞭解為什麼要查看下列章節：</span><span class="sxs-lookup"><span data-stu-id="aafd2-316">To understand why review the following section:</span></span>

<span data-ttu-id="aafd2-317">App-v 5.0 SP2 引進了擱置狀態的概念。</span><span class="sxs-lookup"><span data-stu-id="aafd2-317">App-V 5.0 SP2 introduced the concept of pending states.</span></span> <span data-ttu-id="aafd2-318">在過去，</span><span class="sxs-lookup"><span data-stu-id="aafd2-318">In the past,</span></span>

-   <span data-ttu-id="aafd2-319">如果系統管理員變更了 [權利] 或 [建立新版本的套件（已升級）]，且在打包期間進行發佈/重新整理時，將無法使用 [取消發佈] 或 [發佈] 作業。</span><span class="sxs-lookup"><span data-stu-id="aafd2-319">If an administrator changed entitlements or created a new version of a package (upgraded) and during a publishing/refresh that package was in-use, the un-publish or publish operation, respectively, would fail.</span></span>

-   <span data-ttu-id="aafd2-320">現在，如果套件是在使用中，則會暫停該作業。</span><span class="sxs-lookup"><span data-stu-id="aafd2-320">Now, if a package is in-use the operation will be pended.</span></span> <span data-ttu-id="aafd2-321">[取消發佈] 和 [發佈-待定] 作業將會在服務重新開機時處理，或在發出另一個發佈或取消發佈命令時進行處理。</span><span class="sxs-lookup"><span data-stu-id="aafd2-321">The un-publish and publish-pend operations will be processed on service restart or if another publish or un-publish command is issued.</span></span> <span data-ttu-id="aafd2-322">在後一種情況下，如果虛擬應用程式是在使用中，則虛擬應用程式將會保持擱置狀態。</span><span class="sxs-lookup"><span data-stu-id="aafd2-322">In the latter case, if the virtual application is in-use otherwise, the virtual application will remain in a pending state.</span></span> <span data-ttu-id="aafd2-323">針對全域發佈的套件，通常需要重新開機（或重新開機服務）。</span><span class="sxs-lookup"><span data-stu-id="aafd2-323">For globally published packages, a restart (or service restart) often needed.</span></span>

<span data-ttu-id="aafd2-324">在非持久性環境中，不可能會處理這些暫停的作業。</span><span class="sxs-lookup"><span data-stu-id="aafd2-324">In a non-persistent environment, it is unlikely these pended operations will be processed.</span></span> <span data-ttu-id="aafd2-325">暫停的作業（例如工作）會在**HKEY \ _CURRENT \ _USER**  \\  **軟體**  \\  **Microsoft**  \\  **AppV**  \\  **用戶端**  \\  \*\* \*\*] 下捕獲。</span><span class="sxs-lookup"><span data-stu-id="aafd2-325">The pended operations, for example tasks are captured under **HKEY\_CURRENT\_USER** \\ **Software** \\ **Microsoft** \\ **AppV** \\ **Client** \\ **PendingTasks**.</span></span> <span data-ttu-id="aafd2-326">雖然此位置是由 UPM 解決方案所保留，但在登入前未將它套用到環境，否則就不會處理它。</span><span class="sxs-lookup"><span data-stu-id="aafd2-326">Although this location is persisted by the UPM solution, if it is not applied to the environment prior to log on, it will not be processed.</span></span>

### <a href="" id="bkmk-evdi"></a><span data-ttu-id="aafd2-327">透過效能優化調整來增強 VDI 體驗</span><span class="sxs-lookup"><span data-stu-id="aafd2-327">Enhancing the VDI Experience through Performance Optimization Tuning</span></span>

<span data-ttu-id="aafd2-328">下列各節包含 Microsoft 檔和下載相關資訊的清單，這些資訊在優化您的環境以提高效能時可能會很有用。</span><span class="sxs-lookup"><span data-stu-id="aafd2-328">The following section contains lists with information about Microsoft documentation and downloads that may be useful when optimizing your environment for performance.</span></span>

**<span data-ttu-id="aafd2-329">.NET NGEN 博客及腳本（強烈建議）</span><span class="sxs-lookup"><span data-stu-id="aafd2-329">.NET NGEN Blog and Script (Highly Recommended)</span></span>**

<span data-ttu-id="aafd2-330">關於 NGEN 技術</span><span class="sxs-lookup"><span data-stu-id="aafd2-330">About NGEN technology</span></span>

-   [<span data-ttu-id="aafd2-331">如何加速 NGEN 優化</span><span class="sxs-lookup"><span data-stu-id="aafd2-331">How to speed up NGEN optimization</span></span>](https://blogs.msdn.com/b/dotnet/archive/2013/08/06/wondering-why-mscorsvw-exe-has-high-cpu-usage-you-can-speed-it-up.aspx)

-   [<span data-ttu-id="aafd2-332">指令碼</span><span class="sxs-lookup"><span data-stu-id="aafd2-332">Script</span></span>](https://aka.ms/DrainNGenQueue)

**<span data-ttu-id="aafd2-333">Windows Server 和伺服器角色</span><span class="sxs-lookup"><span data-stu-id="aafd2-333">Windows Server and Server Roles</span></span>**

<span data-ttu-id="aafd2-334">伺服器效能調整指導方針</span><span class="sxs-lookup"><span data-stu-id="aafd2-334">Server Performance Tuning Guidelines for</span></span>

-   [<span data-ttu-id="aafd2-335">Microsoft Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="aafd2-335">Microsoft Windows Server 2012 R2</span></span>](https://msdn.microsoft.com/library/windows/hardware/dn529133.aspx)

-   [<span data-ttu-id="aafd2-336">Microsoft Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="aafd2-336">Microsoft Windows Server 2012</span></span>](https://download.microsoft.com/download/0/0/B/00BE76AF-D340-4759-8ECD-C80BC53B6231/performance-tuning-guidelines-windows-server-2012.docx)

-   [<span data-ttu-id="aafd2-337">Microsoft Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="aafd2-337">Microsoft Windows Server 2008 R2</span></span>](https://download.microsoft.com/download/6/B/2/6B2EBD3A-302E-4553-AC00-9885BBF31E21/Perf-tun-srv-R2.docx)

**<span data-ttu-id="aafd2-338">伺服器角色</span><span class="sxs-lookup"><span data-stu-id="aafd2-338">Server Roles</span></span>**

-   [<span data-ttu-id="aafd2-339">遠端桌面虛擬化主機</span><span class="sxs-lookup"><span data-stu-id="aafd2-339">Remote Desktop Virtualization Host</span></span>](https://msdn.microsoft.com/library/windows/hardware/dn567643.aspx)

-   [<span data-ttu-id="aafd2-340">遠端桌面工作階段主機</span><span class="sxs-lookup"><span data-stu-id="aafd2-340">Remote Desktop Session Host</span></span>](https://msdn.microsoft.com/library/windows/hardware/dn567648.aspx)

-   [<span data-ttu-id="aafd2-341">IIS 關聯性： App-v 管理、發佈、報告 Web 服務</span><span class="sxs-lookup"><span data-stu-id="aafd2-341">IIS Relevance: App-V Management, Publishing, Reporting Web Services</span></span>](https://msdn.microsoft.com/library/windows/hardware/dn567678.aspx)

-   [<span data-ttu-id="aafd2-342">檔案伺服器（SMB）關聯性：如果用於在 SCS 模式中使用 App-v 內容儲存與傳遞</span><span class="sxs-lookup"><span data-stu-id="aafd2-342">File Server (SMB) Relevance: If used for App-V Content Storage and Delivery in SCS Mode</span></span>](https://technet.microsoft.com/library/jj134210.aspx)

**<span data-ttu-id="aafd2-343">Windows 用戶端（來賓 OS）效能調整指導方針</span><span class="sxs-lookup"><span data-stu-id="aafd2-343">Windows Client (Guest OS) Performance Tuning Guidance</span></span>**

-   [<span data-ttu-id="aafd2-344">Microsoft Windows 7</span><span class="sxs-lookup"><span data-stu-id="aafd2-344">Microsoft Windows 7</span></span>](https://download.microsoft.com/download/E/5/7/E5783D68-160B-4366-8387-114FC3E45EB4/Performance Tuning Guidelines for Windows 7 Desktop Virtualization v1.9.docx)

-   [<span data-ttu-id="aafd2-345">優化腳本：（由 Microsoft 支援人員提供）</span><span class="sxs-lookup"><span data-stu-id="aafd2-345">Optimization Script: (Provided by Microsoft Support)</span></span>](https://blogs.technet.com/b/jeff_stokes/archive/2012/10/15/the-microsoft-premier-field-engineer-pfe-view-on-virtual-desktop-vdi-density.aspx)

-   [<span data-ttu-id="aafd2-346">Microsoft Windows 8</span><span class="sxs-lookup"><span data-stu-id="aafd2-346">Microsoft Windows 8</span></span>](https://download.microsoft.com/download/6/0/1/601D7797-A063-4FA7-A2E5-74519B57C2B4/Windows_8_VDI_Image_Client_Tuning_Guide.pdf)

-   [<span data-ttu-id="aafd2-347">優化腳本：（由 Microsoft 支援人員提供）</span><span class="sxs-lookup"><span data-stu-id="aafd2-347">Optimization Script: (Provided by Microsoft Support)</span></span>](https://blogs.technet.com/b/jeff_stokes/archive/2013/04/09/hot-off-the-presses-get-it-now-the-windows-8-vdi-optimization-script-courtesy-of-pfe.aspx)

## <span data-ttu-id="aafd2-348">針對發佈效能優化套件的先後順序步驟</span><span class="sxs-lookup"><span data-stu-id="aafd2-348">Sequencing Steps to Optimize Packages for Publishing Performance</span></span>


<span data-ttu-id="aafd2-349">幾個 App-v 功能可協助新案例或啟用新的客戶部署案例。</span><span class="sxs-lookup"><span data-stu-id="aafd2-349">Several App-V features facilitate new scenarios or enable new customer deployment scenarios.</span></span> <span data-ttu-id="aafd2-350">下列功能可能會影響發佈與啟動作業的效能。</span><span class="sxs-lookup"><span data-stu-id="aafd2-350">These following features can impact the performance of the publishing and launch operations.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="aafd2-351">步驟</span><span class="sxs-lookup"><span data-stu-id="aafd2-351">Step</span></span></th>
<th align="left"><span data-ttu-id="aafd2-352">考量</span><span class="sxs-lookup"><span data-stu-id="aafd2-352">Consideration</span></span></th>
<th align="left"><span data-ttu-id="aafd2-353">權益</span><span class="sxs-lookup"><span data-stu-id="aafd2-353">Benefits</span></span></th>
<th align="left"><span data-ttu-id="aafd2-354">負面</span><span class="sxs-lookup"><span data-stu-id="aafd2-354">Tradeoffs</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="aafd2-355">沒有功能區塊1（FB1，也稱為主要的 FB）</span><span class="sxs-lookup"><span data-stu-id="aafd2-355">No Feature Block 1 (FB1, also known as Primary FB)</span></span></p></td>
<td align="left"><p><span data-ttu-id="aafd2-356">[無 FB1] 表示應用程式將立即啟動，資料流程錯誤（應用程式需要檔案、DLL 且必須在網路上向下拉入）。如果有網路限制，FB1 將會：</span><span class="sxs-lookup"><span data-stu-id="aafd2-356">No FB1 means the application will launch immediately and stream fault (application requires file, DLL and must pull down over the network) during launch.If there are network limitations, FB1 will:</span></span></p>
<ul>
<li><p><span data-ttu-id="aafd2-357">減少當您第一次啟動應用程式時所使用的資料流程錯誤和網路頻寬數目。</span><span class="sxs-lookup"><span data-stu-id="aafd2-357">Reduce the number of stream faults and network bandwidth used when you launch an application for the first time.</span></span></p></li>
<li><p><span data-ttu-id="aafd2-358">延遲啟動，直到整個 FB1 都已流入為止。</span><span class="sxs-lookup"><span data-stu-id="aafd2-358">Delay launch until the entire FB1 has been streamed.</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="aafd2-359">資料流程錯誤減少了啟動時間。</span><span class="sxs-lookup"><span data-stu-id="aafd2-359">Stream faulting decreases the launch time.</span></span></p></td>
<td align="left"><p><span data-ttu-id="aafd2-360">已設定 FB1 的虛擬應用程式套件將需要重新排序。</span><span class="sxs-lookup"><span data-stu-id="aafd2-360">Virtual application packages with FB1 configured will need to be re-sequenced.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="aafd2-361">移除 FB1</span><span class="sxs-lookup"><span data-stu-id="aafd2-361">Removing FB1</span></span>

<span data-ttu-id="aafd2-362">移除 FB1 不需要原始應用程式安裝程式。</span><span class="sxs-lookup"><span data-stu-id="aafd2-362">Removing FB1 does not require the original application installer.</span></span> <span data-ttu-id="aafd2-363">完成下列步驟之後，建議您將執行 sequencer 的電腦還原為乾淨的快照。</span><span class="sxs-lookup"><span data-stu-id="aafd2-363">After completing the following steps, it is suggested that you revert the computer running the sequencer to a clean snapshot.</span></span>

<span data-ttu-id="aafd2-364">**SEQUENCER UI** -建立新的虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="aafd2-364">**Sequencer UI** - Create a New Virtual Application Package.</span></span>

1.  <span data-ttu-id="aafd2-365">完成進行自訂資料流程的先後順序步驟 &gt; 。</span><span class="sxs-lookup"><span data-stu-id="aafd2-365">Complete the sequencing steps up to Customize -&gt; Streaming.</span></span>

2.  <span data-ttu-id="aafd2-366">在 [資料流程] 步驟中，請勿選取 **[在低速或不可靠的網路上針對部署來優化套件**]。</span><span class="sxs-lookup"><span data-stu-id="aafd2-366">At the Streaming step, do not select **Optimize the package for deployment over slow or unreliable network**.</span></span>

3.  <span data-ttu-id="aafd2-367">如有需要，請移至**目標作業系統**。</span><span class="sxs-lookup"><span data-stu-id="aafd2-367">If desired, move on to **Target OS**.</span></span>

**<span data-ttu-id="aafd2-368">修改現有的虛擬應用程式套件</span><span class="sxs-lookup"><span data-stu-id="aafd2-368">Modify an Existing Virtual Application Package</span></span>**

1.  <span data-ttu-id="aafd2-369">完成排序步驟直至進行流式處理。</span><span class="sxs-lookup"><span data-stu-id="aafd2-369">Complete the sequencing steps up to Streaming.</span></span>

2.  <span data-ttu-id="aafd2-370">請勿選取 **[在慢速或不可靠的網路上優化套件以進行部署**]。</span><span class="sxs-lookup"><span data-stu-id="aafd2-370">Do not select **Optimize the package for deployment over a slow or unreliable network**.</span></span>

3.  <span data-ttu-id="aafd2-371">移至 [**建立套件**]。</span><span class="sxs-lookup"><span data-stu-id="aafd2-371">Move to **Create Package**.</span></span>

<span data-ttu-id="aafd2-372">**PowerShell** -更新現有的虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="aafd2-372">**PowerShell** - Update an Existing Virtual Application Package.</span></span>

1.  <span data-ttu-id="aafd2-373">開啟提升許可權的 PowerShell 會話。</span><span class="sxs-lookup"><span data-stu-id="aafd2-373">Open an elevated PowerShell session.</span></span>

2.  <span data-ttu-id="aafd2-374">匯入-模組**appvsequencer**。</span><span class="sxs-lookup"><span data-stu-id="aafd2-374">Import-module **appvsequencer**.</span></span>

3.  <span data-ttu-id="aafd2-375">**更新-AppvSequencerPackage**  - **AppvPackageFilePath**</span><span class="sxs-lookup"><span data-stu-id="aafd2-375">**Update-AppvSequencerPackage** - **AppvPackageFilePath**</span></span>

    <span data-ttu-id="aafd2-376">"C:\\Packages\\MyPackage.appv"-安裝程式</span><span class="sxs-lookup"><span data-stu-id="aafd2-376">"C:\\Packages\\MyPackage.appv" -Installer</span></span>

    <span data-ttu-id="aafd2-377">"C:\\PackageInstall\\PackageUpgrade.exe empty.exe"-OutputPath</span><span class="sxs-lookup"><span data-stu-id="aafd2-377">"C:\\PackageInstall\\PackageUpgrade.exe empty.exe" -OutputPath</span></span>

    <span data-ttu-id="aafd2-378">"C:\\UpgradedPackages"</span><span class="sxs-lookup"><span data-stu-id="aafd2-378">"C:\\UpgradedPackages"</span></span>

    **<span data-ttu-id="aafd2-379">注意</span><span class="sxs-lookup"><span data-stu-id="aafd2-379">Note</span></span>**  
    <span data-ttu-id="aafd2-380">這個 Cmdlet 需要可執行檔（.exe）或批次處理檔案（.bat）。</span><span class="sxs-lookup"><span data-stu-id="aafd2-380">This cmdlet requires an executable (.exe) or batch file (.bat).</span></span> <span data-ttu-id="aafd2-381">您必須提供空白（無任何）可執行檔或批次處理檔案。</span><span class="sxs-lookup"><span data-stu-id="aafd2-381">You must provide an empty (does nothing) executable or batch file.</span></span>



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="aafd2-382">步驟</span><span class="sxs-lookup"><span data-stu-id="aafd2-382">Step</span></span></th>
<th align="left"><span data-ttu-id="aafd2-383">考量</span><span class="sxs-lookup"><span data-stu-id="aafd2-383">Considerations</span></span></th>
<th align="left"><span data-ttu-id="aafd2-384">權益</span><span class="sxs-lookup"><span data-stu-id="aafd2-384">Benefits</span></span></th>
<th align="left"><span data-ttu-id="aafd2-385">負面</span><span class="sxs-lookup"><span data-stu-id="aafd2-385">Tradeoffs</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="aafd2-386">發佈時不安裝 SXS （預先安裝的 SxS 元件）</span><span class="sxs-lookup"><span data-stu-id="aafd2-386">No SXS Install at Publish (Pre-Install SxS assemblies)</span></span></p></td>
<td align="left"><p><span data-ttu-id="aafd2-387">虛擬應用程式套件不需要重新排序。</span><span class="sxs-lookup"><span data-stu-id="aafd2-387">Virtual Application packages do not need to be re-sequenced.</span></span> <span data-ttu-id="aafd2-388">SxS 元件可以保留在虛擬應用程式套件中。</span><span class="sxs-lookup"><span data-stu-id="aafd2-388">SxS Assemblies can remain in the virtual application package.</span></span></p></td>
<td align="left"><p><span data-ttu-id="aafd2-389">在發佈時不會安裝 SxS 元件相依性。</span><span class="sxs-lookup"><span data-stu-id="aafd2-389">The SxS Assembly dependencies will not install at publishing time.</span></span></p></td>
<td align="left"><p><span data-ttu-id="aafd2-390">必須預先安裝 SxS 元件相依性。</span><span class="sxs-lookup"><span data-stu-id="aafd2-390">SxS Assembly dependencies must be pre-installed.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="aafd2-391">在 sequencer 上建立新的虛擬應用程式套件</span><span class="sxs-lookup"><span data-stu-id="aafd2-391">Creating a new virtual application package on the sequencer</span></span>

<span data-ttu-id="aafd2-392">如果在排序器監視期間，在應用程式的安裝過程中會安裝一個 SxS 元件（例如 VC + + 執行時間），則會自動偵測並包含在套件中的 SxS 元件。</span><span class="sxs-lookup"><span data-stu-id="aafd2-392">If, during sequencer monitoring, an SxS Assembly (such as a VC++ Runtime) is installed as part of an application’s installation, SxS Assembly will be automatically detected and included in the package.</span></span> <span data-ttu-id="aafd2-393">系統管理員會收到通知，並提供排除 SxS 元件的選項。</span><span class="sxs-lookup"><span data-stu-id="aafd2-393">The administrator will be notified and will have the option to exclude the SxS Assembly.</span></span>

<span data-ttu-id="aafd2-394">**用戶端**：</span><span class="sxs-lookup"><span data-stu-id="aafd2-394">**Client Side**:</span></span>

<span data-ttu-id="aafd2-395">發佈虛擬應用程式套件時，App-V 用戶端會偵測到是否已安裝所需的 SxS 相依性。</span><span class="sxs-lookup"><span data-stu-id="aafd2-395">When publishing a virtual application package, the App-V Client will detect if a required SxS dependency is already installed.</span></span> <span data-ttu-id="aafd2-396">如果相依性在電腦上無法使用，且包含在套件中，則是傳統的 Windows 安裝程式（.**msi**）將會啟動 SxS 元件的安裝。</span><span class="sxs-lookup"><span data-stu-id="aafd2-396">If the dependency is unavailable on the computer and it is included in the package, a traditional Windows Installer (.**msi**) installation of the SxS assembly will be initiated.</span></span> <span data-ttu-id="aafd2-397">如先前所述，只需在執行用戶端的電腦上安裝相依性，以確保不會發生 Windows Installer （.msi）安裝。</span><span class="sxs-lookup"><span data-stu-id="aafd2-397">As previously documented, simply install the dependency on the computer running the client to ensure that the Windows Installer (.msi) installation will not occur.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="aafd2-398">步驟</span><span class="sxs-lookup"><span data-stu-id="aafd2-398">Step</span></span></th>
<th align="left"><span data-ttu-id="aafd2-399">考量</span><span class="sxs-lookup"><span data-stu-id="aafd2-399">Considerations</span></span></th>
<th align="left"><span data-ttu-id="aafd2-400">權益</span><span class="sxs-lookup"><span data-stu-id="aafd2-400">Benefits</span></span></th>
<th align="left"><span data-ttu-id="aafd2-401">負面</span><span class="sxs-lookup"><span data-stu-id="aafd2-401">Tradeoffs</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="aafd2-402">選擇性地使用動態設定檔</span><span class="sxs-lookup"><span data-stu-id="aafd2-402">Selectively Employ Dynamic Configuration files</span></span></p></td>
<td align="left"><p><span data-ttu-id="aafd2-403">App-v 5.1 用戶端必須分析並處理這些動態設定檔。</span><span class="sxs-lookup"><span data-stu-id="aafd2-403">The App-V 5.1 client must parse and process these Dynamic Configuration files.</span></span></p>
<p><span data-ttu-id="aafd2-404">關注檔案的大小與複雜性（腳本執行、VREG 包含/排除）。</span><span class="sxs-lookup"><span data-stu-id="aafd2-404">Be conscious of size and complexity (script execution, VREG inclusions/exclusions) of the file.</span></span></p>
<p><span data-ttu-id="aafd2-405">許多虛擬應用程式套件可能已經擁有使用者或電腦專用的動態配置檔案。</span><span class="sxs-lookup"><span data-stu-id="aafd2-405">Numerous virtual application packages may already have User- or computer–specific dynamic configurations files.</span></span></p></td>
<td align="left"><p><span data-ttu-id="aafd2-406">如果有選擇性地使用這些檔案或根本不使用，發佈時間就會得到改善。</span><span class="sxs-lookup"><span data-stu-id="aafd2-406">Publishing times will improve if these files are used selectively or not at all.</span></span></p></td>
<td align="left"><p><span data-ttu-id="aafd2-407">虛擬應用程式套件需要個別重新配置，或是透過 App V 伺服器管理主控台來移除相關聯的動態設定檔案。</span><span class="sxs-lookup"><span data-stu-id="aafd2-407">Virtual application packages would need to be reconfigured individually or via the App-V server management console to remove associated Dynamic Configuration files.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="aafd2-408">使用 Powershell 停用動態設定</span><span class="sxs-lookup"><span data-stu-id="aafd2-408">Disabling a Dynamic Configuration using Powershell</span></span>

-   <span data-ttu-id="aafd2-409">在已發佈的套件中，您可以使用 `Set-AppVClientPackage –Name Myapp –Path c:\Packages\Apps\MyApp.appv` 不含</span><span class="sxs-lookup"><span data-stu-id="aafd2-409">For already published packages, you can use `Set-AppVClientPackage –Name Myapp –Path c:\Packages\Apps\MyApp.appv` without</span></span>

    <span data-ttu-id="aafd2-410">**-DynamicDeploymentConfiguration**參數</span><span class="sxs-lookup"><span data-stu-id="aafd2-410">**-DynamicDeploymentConfiguration** parameter</span></span>

-   <span data-ttu-id="aafd2-411">同樣地，當您使用來新增套件時 `Add-AppVClientPackage –Path c:\Packages\Apps\MyApp.appv` ，請不要使用</span><span class="sxs-lookup"><span data-stu-id="aafd2-411">Similarly, when adding new packages using `Add-AppVClientPackage –Path c:\Packages\Apps\MyApp.appv`, do not use the</span></span>

    <span data-ttu-id="aafd2-412">**-DynamicDeploymentConfiguration**參數。</span><span class="sxs-lookup"><span data-stu-id="aafd2-412">**-DynamicDeploymentConfiguration** parameter.</span></span>

<span data-ttu-id="aafd2-413">如需有關如何套用動態設定的檔，請參閱：</span><span class="sxs-lookup"><span data-stu-id="aafd2-413">For documentation on How to Apply a Dynamic Configuration, see:</span></span>

-   [<span data-ttu-id="aafd2-414">如何使用 PowerShell 來套用使用者設定檔案</span><span class="sxs-lookup"><span data-stu-id="aafd2-414">How to Apply the User Configuration File by Using PowerShell</span></span>](how-to-apply-the-user-configuration-file-by-using-powershell51.md)

-   [<span data-ttu-id="aafd2-415">如何使用 PowerShell 來套用部署設定檔案</span><span class="sxs-lookup"><span data-stu-id="aafd2-415">How to Apply the Deployment Configuration File by Using PowerShell</span></span>](how-to-apply-the-deployment-configuration-file-by-using-powershell51.md)

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="aafd2-416">步驟</span><span class="sxs-lookup"><span data-stu-id="aafd2-416">Step</span></span></th>
<th align="left"><span data-ttu-id="aafd2-417">考量</span><span class="sxs-lookup"><span data-stu-id="aafd2-417">Considerations</span></span></th>
<th align="left"><span data-ttu-id="aafd2-418">權益</span><span class="sxs-lookup"><span data-stu-id="aafd2-418">Benefits</span></span></th>
<th align="left"><span data-ttu-id="aafd2-419">負面</span><span class="sxs-lookup"><span data-stu-id="aafd2-419">Tradeoffs</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="aafd2-420">在套件生命週期期間執行同步腳本的帳戶。</span><span class="sxs-lookup"><span data-stu-id="aafd2-420">Account for Synchronous Script Execution during Package Lifecycle.</span></span></p></td>
<td align="left"><p><span data-ttu-id="aafd2-421">如果將腳本宣傳資料內嵌在套件中，Add （Powershell）可能會有很大的下降速度。</span><span class="sxs-lookup"><span data-stu-id="aafd2-421">If script collateral is embedded in the package, Add (Powershell) may be significantly slower.</span></span></p>
<p><span data-ttu-id="aafd2-422">在虛擬應用程式啟動期間執行腳本（StartVirtualEnvironment、StartProcess）和/或 Add + 發佈會影響在一或多個這些週期作業期間的感知效能。</span><span class="sxs-lookup"><span data-stu-id="aafd2-422">Running of scripts during virtual application launch (StartVirtualEnvironment, StartProcess) and/or Add+Publish will impact the perceived performance during one or more of these lifecycle operations.</span></span></p></td>
<td align="left"><p><span data-ttu-id="aafd2-423">使用非同步（無封鎖）腳本可確保週期作業能有效完成。</span><span class="sxs-lookup"><span data-stu-id="aafd2-423">Use of Asynchronous (Non-Blocking) Scripts will ensure that the lifecycle operations complete efficiently.</span></span></p></td>
<td align="left"><p><span data-ttu-id="aafd2-424">這個步驟需要使用內嵌的腳本宣傳資料（具有相關聯的動態配置檔案，以及同步處理及執行腳本）的所有虛擬應用程式套件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="aafd2-424">This step requires working knowledge of all virtual application packages with embedded script collateral, which have associated dynamic configurations files and which reference and run scripts synchronously.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="aafd2-425">從套件中移除無關的虛擬字型。</span><span class="sxs-lookup"><span data-stu-id="aafd2-425">Remove Extraneous Virtual Fonts from Package.</span></span></p></td>
<td align="left"><p><span data-ttu-id="aafd2-426">App-V 產品小組所調查的大部分應用程式都包含少量字型，通常少於20個。</span><span class="sxs-lookup"><span data-stu-id="aafd2-426">The majority of applications investigated by the App-V product team contained a small number of fonts, typically fewer than 20.</span></span></p></td>
<td align="left"><p><span data-ttu-id="aafd2-427">虛擬字型會影響發佈更新效能。</span><span class="sxs-lookup"><span data-stu-id="aafd2-427">Virtual Fonts impact publishing refresh performance.</span></span></p></td>
<td align="left"><p><span data-ttu-id="aafd2-428">需要在本機啟用/安裝所需的字型。</span><span class="sxs-lookup"><span data-stu-id="aafd2-428">Desired fonts will need to be enabled/installed natively.</span></span> <span data-ttu-id="aafd2-429">如需相關指示，請參閱安裝或卸載字型。</span><span class="sxs-lookup"><span data-stu-id="aafd2-429">For instructions, see Install or uninstall fonts.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="aafd2-430">判斷套件中存在哪些虛擬字型</span><span class="sxs-lookup"><span data-stu-id="aafd2-430">Determining what virtual fonts exist in the package</span></span>

-   <span data-ttu-id="aafd2-431">製作套件的複本。</span><span class="sxs-lookup"><span data-stu-id="aafd2-431">Make a copy of the package.</span></span>

-   <span data-ttu-id="aafd2-432">將套件 \ _copy 的 appv 重新命名為 Package\_copy.zip</span><span class="sxs-lookup"><span data-stu-id="aafd2-432">Rename Package\_copy.appv to Package\_copy.zip</span></span>

-   <span data-ttu-id="aafd2-433">開啟 AppxManifest.xml 並找出下列專案：</span><span class="sxs-lookup"><span data-stu-id="aafd2-433">Open AppxManifest.xml and locate the following:</span></span>

    <span data-ttu-id="aafd2-434">&lt;appv：延伸類別 = "AppV. Fonts"&gt;</span><span class="sxs-lookup"><span data-stu-id="aafd2-434">&lt;appv:Extension Category="AppV.Fonts"&gt;</span></span>

    <span data-ttu-id="aafd2-435">&lt;appv：字型&gt;</span><span class="sxs-lookup"><span data-stu-id="aafd2-435">&lt;appv:Fonts&gt;</span></span>

    <span data-ttu-id="aafd2-436">&lt;appv：字型路徑 = "\ [{Fonts} \] \\private\\CalibriL.ttf" DelayLoad = "true" &gt; &lt; /Appv： Font&gt;</span><span class="sxs-lookup"><span data-stu-id="aafd2-436">&lt;appv:Font Path="\[{Fonts}\]\\private\\CalibriL.ttf" DelayLoad="true"&gt;&lt;/appv:Font&gt;</span></span>

    **<span data-ttu-id="aafd2-437">注意</span><span class="sxs-lookup"><span data-stu-id="aafd2-437">Note</span></span>**  
    <span data-ttu-id="aafd2-438">如果有標示為**DelayLoad**的字型，這些字型將不會影響第一次啟動。</span><span class="sxs-lookup"><span data-stu-id="aafd2-438">If there are fonts marked as **DelayLoad**, those will not impact first launch.</span></span>



~~~
&lt;/appv:Fonts&gt;
~~~

### <span data-ttu-id="aafd2-439">從套件中排除虛擬字型</span><span class="sxs-lookup"><span data-stu-id="aafd2-439">Excluding virtual fonts from the package</span></span>

<span data-ttu-id="aafd2-440">針對電腦上所有使用者、特定使用者或使用者的使用者設定，使用最符合使用者範圍的動態設定檔。</span><span class="sxs-lookup"><span data-stu-id="aafd2-440">Use the dynamic configuration file that best suits the user scope – deployment configuration for all users on computer, user configuration for specific user or users.</span></span>

-   <span data-ttu-id="aafd2-441">使用 [部署] 或 [使用者設定] 停用字型。</span><span class="sxs-lookup"><span data-stu-id="aafd2-441">Disable fonts with the deployment or user configuration.</span></span>

<span data-ttu-id="aafd2-442">字型</span><span class="sxs-lookup"><span data-stu-id="aafd2-442">Fonts</span></span>

--&gt;

<span data-ttu-id="aafd2-443">&lt;已啟用的字型 = "false"/&gt;</span><span class="sxs-lookup"><span data-stu-id="aafd2-443">&lt;Fonts Enabled="false" /&gt;</span></span>

<span data-ttu-id="aafd2-444">&lt;!--</span><span class="sxs-lookup"><span data-stu-id="aafd2-444">&lt;!--</span></span>

## <a href="" id="bkmk-terms1"></a> <span data-ttu-id="aafd2-445">App-V 5.1 效能指南術語</span><span class="sxs-lookup"><span data-stu-id="aafd2-445">App-V 5.1 Performance Guidance Terminology</span></span>


<span data-ttu-id="aafd2-446">描述與 App-v 5.1 效能優化相關的概念和動作時，會用到下列字詞。</span><span class="sxs-lookup"><span data-stu-id="aafd2-446">The following terms are used when describing concepts and actions related to App-V 5.1 performance optimization.</span></span>

-   <span data-ttu-id="aafd2-447">**複雜性**–指的是一或多個在預設定（**AppvClientPackage**）或整合（**Publish-AppvClientPackage**）期間可能會影響效能的封裝特性。</span><span class="sxs-lookup"><span data-stu-id="aafd2-447">**Complexity** – Refers to the one or more package characteristics that may impact performance during pre-configure (**Add-AppvClientPackage**) or integration (**Publish-AppvClientPackage**).</span></span> <span data-ttu-id="aafd2-448">一些範例特性包括：資訊清單大小、虛擬字型數、檔案數目。</span><span class="sxs-lookup"><span data-stu-id="aafd2-448">Some example characteristics are: manifest size, number of virtual fonts, number of files.</span></span>

-   <span data-ttu-id="aafd2-449">**取消整合**–移除使用者整合</span><span class="sxs-lookup"><span data-stu-id="aafd2-449">**De-Integrate** – Removes the user integrations</span></span>

-   <span data-ttu-id="aafd2-450">**重新整合**–運用使用者整合。</span><span class="sxs-lookup"><span data-stu-id="aafd2-450">**Re-Integrate** – Applies the user integrations.</span></span>

-   <span data-ttu-id="aafd2-451">**非持久，彙集**-在每次登入時，建立執行虛擬環境的電腦。</span><span class="sxs-lookup"><span data-stu-id="aafd2-451">**Non-Persistent, Pooled** – Creates a computer running a virtual environment each time they log in.</span></span>

-   <span data-ttu-id="aafd2-452">**Persistent，個人**–執行虛擬環境的電腦，每次登入都保持不變。</span><span class="sxs-lookup"><span data-stu-id="aafd2-452">**Persistent, Personal** – A computer running a virtual environment that remains the same for every login.</span></span>

-   <span data-ttu-id="aafd2-453">[有**狀態**-適用于此檔]，表示使用者整合是在會話之間保留，而使用者環境管理技術則與非持久性 RDSH 或 VDI 搭配使用。</span><span class="sxs-lookup"><span data-stu-id="aafd2-453">**Stateful** - For this document, implies that user integrations are persisted between sessions and a user environment management technology is used in conjunction with non-persistent RDSH or VDI.</span></span>

-   <span data-ttu-id="aafd2-454">**無狀態**–代表沒有在會話之間保留任何使用者狀態的情況。</span><span class="sxs-lookup"><span data-stu-id="aafd2-454">**Stateless** – Represents a scenario when no user state is persisted between sessions.</span></span>

-   <span data-ttu-id="aafd2-455">**Trigger** –（或原生動作觸發程式）。</span><span class="sxs-lookup"><span data-stu-id="aafd2-455">**Trigger** – (or Native Action Triggers).</span></span> <span data-ttu-id="aafd2-456">UPM 使用這些類型的觸發程式來啟動監視或同步處理作業。</span><span class="sxs-lookup"><span data-stu-id="aafd2-456">UPM uses these types of triggers to initiate monitoring or synchronization operations.</span></span>

-   <span data-ttu-id="aafd2-457">**使用者體驗**-在 App-V 5.1 的內容中，使用者體驗（quantitatively）是下列各部分的總和：</span><span class="sxs-lookup"><span data-stu-id="aafd2-457">**User Experience** - In the context of App-V 5.1, the user experience, quantitatively, is the sum of the following parts:</span></span>

    -   <span data-ttu-id="aafd2-458">使用者在能操縱桌面時，啟動登入的點。</span><span class="sxs-lookup"><span data-stu-id="aafd2-458">From the point that users initiate a log-in to when they are able to manipulate the desktop.</span></span>

    -   <span data-ttu-id="aafd2-459">在使用 App-v 5.1 full server 基礎結構時，從桌面可以與發佈重新整理開始（在 PowerShell 術語中為同步處理）的點。</span><span class="sxs-lookup"><span data-stu-id="aafd2-459">From the point where the desktop can be interacted with to the point a publishing refresh begins (in PowerShell terms, sync) when using the App-V 5.1 full server infrastructure.</span></span> <span data-ttu-id="aafd2-460">在獨立實例中，啟動 [**載入 AppVClientPackage** ] 和 [**發佈-AppVClientPackage] Powershell**命令。</span><span class="sxs-lookup"><span data-stu-id="aafd2-460">In standalone instances, it is when the **Add-AppVClientPackage** and **Publish-AppVClientPackage Powershell** commands are initiated.</span></span>

    -   <span data-ttu-id="aafd2-461">[從開始-完成] 發佈重新整理。</span><span class="sxs-lookup"><span data-stu-id="aafd2-461">From start to completion of the publishing refresh.</span></span> <span data-ttu-id="aafd2-462">在獨立實例中，這是第一次發佈的虛擬應用程式。</span><span class="sxs-lookup"><span data-stu-id="aafd2-462">In standalone instances, this is the first to last virtual application published.</span></span>

    -   <span data-ttu-id="aafd2-463">從可從快捷方式啟動虛擬應用程式的位置。</span><span class="sxs-lookup"><span data-stu-id="aafd2-463">From the point where the virtual application is available to launch from a shortcut.</span></span> <span data-ttu-id="aafd2-464">或者，它是從已登錄檔案類型關聯的點開始，並啟動指定的虛擬應用程式。</span><span class="sxs-lookup"><span data-stu-id="aafd2-464">Alternatively, it is from the point at which the file type association is registered and will launch a specified virtual application.</span></span>

-   <span data-ttu-id="aafd2-465">**使用者設定檔管理**–管理與環境相關的使用者元件的可控與結構化方法。</span><span class="sxs-lookup"><span data-stu-id="aafd2-465">**User Profile Management** – The controlled and structured approach to managing user components associated with the environment.</span></span> <span data-ttu-id="aafd2-466">例如，使用者設定檔、喜好設定與原則管理、應用程式控制和應用程式部署。</span><span class="sxs-lookup"><span data-stu-id="aafd2-466">For example, user profiles, preference and policy management, application control and application deployment.</span></span> <span data-ttu-id="aafd2-467">您可以使用腳本或協力廠商解決方案視需要設定環境。</span><span class="sxs-lookup"><span data-stu-id="aafd2-467">You can use scripting or third-party solutions configure the environment as needed.</span></span>






## <span data-ttu-id="aafd2-468">相關主題</span><span class="sxs-lookup"><span data-stu-id="aafd2-468">Related topics</span></span>


[<span data-ttu-id="aafd2-469">Microsoft Application Virtualization 5.1 系統管理員指南</span><span class="sxs-lookup"><span data-stu-id="aafd2-469">Microsoft Application Virtualization 5.1 Administrator's Guide</span></span>](microsoft-application-virtualization-51-administrators-guide.md)









