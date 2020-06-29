---
title: Microsoft 進階群組原則管理 4.0 逐步指南
description: Microsoft 進階群組原則管理 4.0 逐步指南
author: dansimp
ms.assetid: dc6f9b16-b1d4-48f3-88bb-f29301f0131c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 819d536451095d23080115799016aa0ac5242dee
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802521"
---
# <span data-ttu-id="89ed3-103">Microsoft 進階群組原則管理 4.0 逐步指南</span><span class="sxs-lookup"><span data-stu-id="89ed3-103">Step-by-Step Guide for Microsoft Advanced Group Policy Management 4.0</span></span>


<span data-ttu-id="89ed3-104">本逐步指南說明使用群組原則管理主控台（GPMC）和 Microsoft 高級群組原則管理（AGPM）的群組原則管理的高級技術。</span><span class="sxs-lookup"><span data-stu-id="89ed3-104">This step-by-step guide demonstrates advanced techniques for Group Policy management that use the Group Policy Management Console (GPMC) and Microsoft Advanced Group Policy Management (AGPM).</span></span> <span data-ttu-id="89ed3-105">AGPM 會增加 GPMC 的功能，提供：</span><span class="sxs-lookup"><span data-stu-id="89ed3-105">AGPM increases the capabilities of the GPMC, providing:</span></span>

-   <span data-ttu-id="89ed3-106">將管理群組原則物件（Gpo）委派給多個群組原則管理員的標準角色，以及委派對生產環境中 Gpo 的存取權的功能。</span><span class="sxs-lookup"><span data-stu-id="89ed3-106">Standard roles for delegating permissions to manage Group Policy Objects (GPOs) to multiple Group Policy administrators, in addition to the ability to delegate access to GPOs in the production environment.</span></span>

-   <span data-ttu-id="89ed3-107">[封存] 可讓群組原則管理員在 Gpo 部署到生產環境之前，建立及修改 Gpo。</span><span class="sxs-lookup"><span data-stu-id="89ed3-107">An archive to enable Group Policy administrators to create and modify GPOs offline before the GPOs are deployed into a production environment.</span></span>

-   <span data-ttu-id="89ed3-108">回滾到封存中任何舊版 GPO 的功能，以及限制儲存在封存中的版本數。</span><span class="sxs-lookup"><span data-stu-id="89ed3-108">The ability to roll back to any earlier version of a GPO in the archive and to limit the number of versions stored in the archive.</span></span>

-   <span data-ttu-id="89ed3-109">Gpo 的存回和取出功能，以確保群組原則系統管理員不會無意中覆寫對方的工作。</span><span class="sxs-lookup"><span data-stu-id="89ed3-109">Check-in and check-out capability for GPOs to make sure that Group Policy administrators do not unintentionally overwrite each other's work.</span></span>

-   <span data-ttu-id="89ed3-110">能夠搜尋具有特定屬性的 Gpo，以及篩選顯示的 Gpo 清單。</span><span class="sxs-lookup"><span data-stu-id="89ed3-110">The ability to search for GPOs with specific attributes and to filter the list of GPOs displayed.</span></span>

## <span data-ttu-id="89ed3-111">AGPM 案例概述</span><span class="sxs-lookup"><span data-stu-id="89ed3-111">AGPM scenario overview</span></span>


<span data-ttu-id="89ed3-112">在這種情況下，您將針對 AGPM 中的每個角色使用個別的使用者帳戶，示範如何在具有多個群群組原則管理員且具有不同許可權等級的環境中管理群組原則。</span><span class="sxs-lookup"><span data-stu-id="89ed3-112">For this scenario, you will use a separate user account for each role in AGPM to demonstrate how Group Policy can be managed in an environment that has multiple Group Policy administrators who have different levels of permissions.</span></span> <span data-ttu-id="89ed3-113">具體來說，您將會執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="89ed3-113">Specifically, you will perform the following tasks:</span></span>

-   <span data-ttu-id="89ed3-114">使用網域系統管理員群組成員的帳戶，安裝 AGPM 服務器並將 AGPM 系統管理員角色指派給帳戶或群組。</span><span class="sxs-lookup"><span data-stu-id="89ed3-114">Using an account that is a member of the Domain Admins group, install AGPM Server and assign the AGPM Administrator role to an account or group.</span></span>

-   <span data-ttu-id="89ed3-115">使用您將指派 AGPM 角色的帳戶，安裝 AGPM 用戶端。</span><span class="sxs-lookup"><span data-stu-id="89ed3-115">Using accounts to which you will assign AGPM roles, install AGPM Client.</span></span>

-   <span data-ttu-id="89ed3-116">使用具有 AGPM 系統管理員角色的帳戶，設定 AGPM 並委派對 Gpo 的存取權，方法是指派角色給其他帳戶。</span><span class="sxs-lookup"><span data-stu-id="89ed3-116">Using an account that has the AGPM Administrator role, configure AGPM and delegate access to GPOs by assigning roles to other accounts.</span></span>

-   <span data-ttu-id="89ed3-117">從擁有 [編輯者] 角色的帳戶，要求建立新的 GPO，然後使用擁有核准者角色的帳戶來進行核准。</span><span class="sxs-lookup"><span data-stu-id="89ed3-117">From an account that has the Editor role, request that a new GPO be created that you then approve by using an account that has the Approver role.</span></span> <span data-ttu-id="89ed3-118">使用 [編輯] 帳戶，將 GPO 從封存中核取，編輯 GPO，將該 GPO 檢查到封存，然後要求部署。</span><span class="sxs-lookup"><span data-stu-id="89ed3-118">Use the Editor account to check the GPO out of the archive, edit the GPO, check the GPO into the archive, and then request deployment.</span></span>

-   <span data-ttu-id="89ed3-119">使用具有核准者角色的帳戶，查看 GPO 並將它部署到您的生產環境。</span><span class="sxs-lookup"><span data-stu-id="89ed3-119">Using an account that has the Approver role, review the GPO and deploy it to your production environment.</span></span>

-   <span data-ttu-id="89ed3-120">使用具有編輯者角色的帳戶，建立一個 GPO 範本，並使用它做為建立新 GPO 的起點。</span><span class="sxs-lookup"><span data-stu-id="89ed3-120">Using an account that has the Editor role, create a GPO template and use it as a starting point to create a new GPO.</span></span>

-   <span data-ttu-id="89ed3-121">使用具有核准者角色的帳戶，刪除並還原 GPO。</span><span class="sxs-lookup"><span data-stu-id="89ed3-121">Using an account that has the Approver role, delete and restore a GPO.</span></span>

![群組原則物件開發程式](images/ab77a1f3-f430-4e7d-be58-ee8f9bd1140e.gif)

## <span data-ttu-id="89ed3-123">需求</span><span class="sxs-lookup"><span data-stu-id="89ed3-123">Requirements</span></span>


<span data-ttu-id="89ed3-124">您想要安裝 AGPM 的電腦必須符合下列需求，而且您必須建立帳戶才能在這個案例中使用。</span><span class="sxs-lookup"><span data-stu-id="89ed3-124">Computers on which you want to install AGPM must meet the following requirements, and you must create accounts for use in this scenario.</span></span>

<span data-ttu-id="89ed3-125">**記事** 如果您已安裝 AGPM 2.5，且它是從 Windows Server®2003升級至 Windows Server2008R2 或 Windows Server2008，或是從 WindowsVista 升級至 WindowsVista （SP1） Windows7 或® Pack1，您必須先升級作業系統，才能升級至 AGPM 4.0。</span><span class="sxs-lookup"><span data-stu-id="89ed3-125">**Note** If you have AGPM 2.5 installed and are upgrading from Windows Server®2003 to Windows Server2008R2 or Windows Server2008, or are upgrading from WindowsVista with no service packs installed to Windows7 or WindowsVista® with Service Pack1 (SP1), you must upgrade the operating system before you can upgrade to AGPM4.0.</span></span>

<span data-ttu-id="89ed3-126">如果您已安裝 AGPM 3.0，則在升級至 AGPM 4.0 之前，您不需要升級作業系統</span><span class="sxs-lookup"><span data-stu-id="89ed3-126">If you have AGPM 3.0 installed, you do not have to upgrade the operating system before you upgrade to AGPM 4.0</span></span>

 

<span data-ttu-id="89ed3-127">在包含更新版本及較舊版本作業系統的混合環境中，功能有一些限制，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="89ed3-127">In a mixed environment that includes both newer and older operating systems, there are some limitations to functionality, as indicated in the following table.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="89ed3-128">在其上執行 AGPM Server 4.0 的作業系統</span><span class="sxs-lookup"><span data-stu-id="89ed3-128">Operating system on which AGPM Server 4.0 runs</span></span></th>
<th align="left"><span data-ttu-id="89ed3-129">在其上執行 AGPM 用戶端4.0 的作業系統</span><span class="sxs-lookup"><span data-stu-id="89ed3-129">Operating system on which AGPM Client 4.0 runs</span></span></th>
<th align="left"><span data-ttu-id="89ed3-130">AGPM 4.0 支援的狀態</span><span class="sxs-lookup"><span data-stu-id="89ed3-130">Status of AGPM 4.0 support</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="89ed3-131">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="89ed3-131">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="89ed3-132">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="89ed3-132">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="89ed3-133">支援</span><span class="sxs-lookup"><span data-stu-id="89ed3-133">Supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="89ed3-134">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="89ed3-134">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="89ed3-135">Windows Server2008 或 Windows Vista （含 SP1）</span><span class="sxs-lookup"><span data-stu-id="89ed3-135">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="89ed3-136">支援，但無法編輯僅存在於 Windows Server2008R2 或 Windows7 的原則設定或喜好設定專案</span><span class="sxs-lookup"><span data-stu-id="89ed3-136">Supported, but cannot edit policy settings or preference items that exist only in Windows Server2008R2 or Windows7</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="89ed3-137">Windows Server2008 或 Windows Vista （含 SP1）</span><span class="sxs-lookup"><span data-stu-id="89ed3-137">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="89ed3-138">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="89ed3-138">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="89ed3-139">不支援</span><span class="sxs-lookup"><span data-stu-id="89ed3-139">Unsupported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="89ed3-140">Windows Server2008 或 Windows Vista （含 SP1）</span><span class="sxs-lookup"><span data-stu-id="89ed3-140">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="89ed3-141">Windows Server2008 或 Windows Vista （含 SP1）</span><span class="sxs-lookup"><span data-stu-id="89ed3-141">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="89ed3-142">支援，但無法報告或編輯僅存在於 Windows Server2008R2 或 Windows7 的原則設定或喜好設定專案</span><span class="sxs-lookup"><span data-stu-id="89ed3-142">Supported, but cannot report or edit policy settings or preference items that exist only in Windows Server2008R2 or Windows7</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="89ed3-143">AGPM 服務器需求</span><span class="sxs-lookup"><span data-stu-id="89ed3-143">AGPM Server requirements</span></span>

<span data-ttu-id="89ed3-144">AGPM Server 4.0 需要 Windows Server2008R2、Windows Server2008、Windows7 和 GPMC （來自遠端伺服器管理工具（RSAT）），或 Windows Vista （在 RSAT 中安裝 GPMC）。</span><span class="sxs-lookup"><span data-stu-id="89ed3-144">AGPM Server4.0 requires Windows Server2008R2, Windows Server2008, Windows7 and the GPMC from Remote Server Administration Tools (RSAT), or Windows Vista with SP1 and the GPMC from RSAT installed.</span></span> <span data-ttu-id="89ed3-145">支援32位和64位版本。</span><span class="sxs-lookup"><span data-stu-id="89ed3-145">Both 32-bit and 64-bit versions are supported.</span></span>

<span data-ttu-id="89ed3-146">在安裝 AGPM Server 之前，您必須是 Domain 系統管理員群組的成員，除非另有說明，否則必須存在下列 Windows 功能：</span><span class="sxs-lookup"><span data-stu-id="89ed3-146">Before you install AGPM Server, you must be a member of the Domain Admins group and the following Windows features must be present unless otherwise noted:</span></span>

-   <span data-ttu-id="89ed3-147">GPMC</span><span class="sxs-lookup"><span data-stu-id="89ed3-147">GPMC</span></span>

    -   <span data-ttu-id="89ed3-148">Windows Server2008R2 或 Windows Server2008：如果 GPMC 不存在，則會透過 AGPM 自動安裝。</span><span class="sxs-lookup"><span data-stu-id="89ed3-148">Windows Server2008R2 or Windows Server2008: If the GPMC is not present, it is automatically installed by AGPM.</span></span>

    -   <span data-ttu-id="89ed3-149">Windows7：您必須從 RSAT 安裝 GPMC，才能安裝 AGPM。</span><span class="sxs-lookup"><span data-stu-id="89ed3-149">Windows7: You must install the GPMC from RSAT before you install AGPM.</span></span> <span data-ttu-id="89ed3-150">如需詳細資訊，請參閱[Windows 7 的遠端伺服器管理工具](https://go.microsoft.com/fwlink/?LinkID=131280)（ https://go.microsoft.com/fwlink/?LinkID=131280) 。</span><span class="sxs-lookup"><span data-stu-id="89ed3-150">For more information, see [Remote Server Administration Tools for Windows 7](https://go.microsoft.com/fwlink/?LinkID=131280) (https://go.microsoft.com/fwlink/?LinkID=131280).</span></span>

    -   <span data-ttu-id="89ed3-151">Windows Vista 與 SP1：安裝 AGPM 前，您必須從 RSAT 安裝 GPMC。</span><span class="sxs-lookup"><span data-stu-id="89ed3-151">Windows Vista with SP1: You must install the GPMC from RSAT before you install AGPM.</span></span> <span data-ttu-id="89ed3-152">如需詳細資訊，請參閱適用[于 Windows Vista 的遠端伺服器管理工具（含 Service Pack 1](https://go.microsoft.com/fwlink/?LinkID=116179) （） https://go.microsoft.com/fwlink/?LinkID=116179) 。</span><span class="sxs-lookup"><span data-stu-id="89ed3-152">For more information, see [Remote Server Administration Tools for Windows Vista with Service Pack 1](https://go.microsoft.com/fwlink/?LinkID=116179) (https://go.microsoft.com/fwlink/?LinkID=116179).</span></span>

-   <span data-ttu-id="89ed3-153">.NET Framework 3.5 或更新版本</span><span class="sxs-lookup"><span data-stu-id="89ed3-153">The .NET Framework 3.5 or later versions</span></span>

    -   <span data-ttu-id="89ed3-154">Windows Server2008R2 或 Windows7：如果未提供 .NET Framework 3.5 或更新版本，則會透過 AGPM 自動安裝 .NET Framework 3.5。</span><span class="sxs-lookup"><span data-stu-id="89ed3-154">Windows Server2008R2 or Windows7: If the .NET Framework 3.5 or later version is not present, the .NET Framework 3.5 is automatically installed by AGPM.</span></span>

    -   <span data-ttu-id="89ed3-155">Windows Server2008 或 Windows Vista （含 SP1）：安裝 AGPM 前，您必須先安裝 .NET Framework 3.5 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="89ed3-155">Windows Server2008 or Windows Vista with SP1: You must install the .NET Framework 3.5 or a later version before you install AGPM.</span></span>

<span data-ttu-id="89ed3-156">AGPM 服務器需要下列 Windows 功能，如果不存在，就會自動安裝這些功能：</span><span class="sxs-lookup"><span data-stu-id="89ed3-156">The following Windows features are required by AGPM Server and will be automatically installed if they are not present:</span></span>

-   <span data-ttu-id="89ed3-157">WCF 啟用;非 HTTP 啟用</span><span class="sxs-lookup"><span data-stu-id="89ed3-157">WCF Activation; Non-HTTP Activation</span></span>

-   <span data-ttu-id="89ed3-158">Windows 處理序啟用服務</span><span class="sxs-lookup"><span data-stu-id="89ed3-158">Windows Process Activation Service</span></span>

    -   <span data-ttu-id="89ed3-159">處理模型</span><span class="sxs-lookup"><span data-stu-id="89ed3-159">Process Model</span></span>

    -   <span data-ttu-id="89ed3-160">.NET 環境</span><span class="sxs-lookup"><span data-stu-id="89ed3-160">The .NET Environment</span></span>

    -   <span data-ttu-id="89ed3-161">配置 Api</span><span class="sxs-lookup"><span data-stu-id="89ed3-161">Configuration APIs</span></span>

### <span data-ttu-id="89ed3-162">AGPM 用戶端需求</span><span class="sxs-lookup"><span data-stu-id="89ed3-162">AGPM Client requirements</span></span>

<span data-ttu-id="89ed3-163">您的 AGPM 用戶端4.0 需要 Windows Server2008R2、Windows Server2008、Windows7 和 GPMC （來自 RSAT），或 Windows Vista （在 RSAT 中安裝了 SP1 和 GPMC）。</span><span class="sxs-lookup"><span data-stu-id="89ed3-163">AGPM Client4.0 requires Windows Server2008R2, Windows Server2008, Windows7 and the GPMC from RSAT, or Windows Vista with SP1 and the GPMC from RSAT installed.</span></span> <span data-ttu-id="89ed3-164">支援32位和64位版本。</span><span class="sxs-lookup"><span data-stu-id="89ed3-164">Both 32-bit and 64-bit versions are supported.</span></span> <span data-ttu-id="89ed3-165">您可以在執行 AGPM 服務器的電腦上安裝 AGPM 用戶端。</span><span class="sxs-lookup"><span data-stu-id="89ed3-165">AGPM Client can be installed on a computer that is running AGPM Server.</span></span>

<span data-ttu-id="89ed3-166">AGPM 用戶端需要下列 Windows 功能，除非另有說明不存在，否則會自動安裝：</span><span class="sxs-lookup"><span data-stu-id="89ed3-166">The following Windows features are required by AGPM Client and unless otherwise noted are automatically installed if they are not present:</span></span>

-   <span data-ttu-id="89ed3-167">GPMC</span><span class="sxs-lookup"><span data-stu-id="89ed3-167">GPMC</span></span>

    -   <span data-ttu-id="89ed3-168">Windows Server2008R2 或 Windows Server2008：如果 GPMC 不存在，則會透過 AGPM 自動安裝。</span><span class="sxs-lookup"><span data-stu-id="89ed3-168">Windows Server2008R2 or Windows Server2008: If the GPMC is not present, it is automatically installed by AGPM.</span></span>

    -   <span data-ttu-id="89ed3-169">Windows7：您必須從 RSAT 安裝 GPMC，才能安裝 AGPM。</span><span class="sxs-lookup"><span data-stu-id="89ed3-169">Windows7: You must install the GPMC from RSAT before you install AGPM.</span></span> <span data-ttu-id="89ed3-170">如需詳細資訊，請參閱[Windows 7 的遠端伺服器管理工具](https://go.microsoft.com/fwlink/?LinkID=131280)（ https://go.microsoft.com/fwlink/?LinkID=131280) 。</span><span class="sxs-lookup"><span data-stu-id="89ed3-170">For more information, see [Remote Server Administration Tools for Windows 7](https://go.microsoft.com/fwlink/?LinkID=131280) (https://go.microsoft.com/fwlink/?LinkID=131280).</span></span>

    -   <span data-ttu-id="89ed3-171">Windows Vista 與 SP1：安裝 AGPM 前，您必須從 RSAT 安裝 GPMC。</span><span class="sxs-lookup"><span data-stu-id="89ed3-171">Windows Vista with SP1: You must install the GPMC from RSAT before you install AGPM.</span></span> <span data-ttu-id="89ed3-172">如需詳細資訊，請參閱適用[于 Windows Vista 的遠端伺服器管理工具（含 Service Pack 1](https://go.microsoft.com/fwlink/?LinkID=116179) （） https://go.microsoft.com/fwlink/?LinkID=116179) 。</span><span class="sxs-lookup"><span data-stu-id="89ed3-172">For more information, see [Remote Server Administration Tools for Windows Vista with Service Pack 1](https://go.microsoft.com/fwlink/?LinkID=116179) (https://go.microsoft.com/fwlink/?LinkID=116179).</span></span>

-   <span data-ttu-id="89ed3-173">.NET Framework 3.0 或更新版本</span><span class="sxs-lookup"><span data-stu-id="89ed3-173">The .NET Framework 3.0 or later version</span></span>

    -   <span data-ttu-id="89ed3-174">Windows Server2008R2 或 Windows7：如果未提供 .NET Framework 3.0 或更新版本，則會透過 AGPM 自動安裝 .NET Framework 3.5。</span><span class="sxs-lookup"><span data-stu-id="89ed3-174">Windows Server2008R2 or Windows7: If the .NET Framework 3.0 or later version is not present, the .NET Framework 3.5 is automatically installed by AGPM.</span></span>

    -   <span data-ttu-id="89ed3-175">Windows Server2008 或 Windows Vista （含 SP1）：如果不存在 .NET Framework 3.0 或更新版本，則會透過 AGPM 自動安裝 .NET Framework 3.0。</span><span class="sxs-lookup"><span data-stu-id="89ed3-175">Windows Server2008 or Windows Vista with SP1: If the .NET Framework 3.0 or later version is not present, the .NET Framework 3.0 is automatically installed by AGPM.</span></span>

### <span data-ttu-id="89ed3-176">案例需求</span><span class="sxs-lookup"><span data-stu-id="89ed3-176">Scenario requirements</span></span>

<span data-ttu-id="89ed3-177">開始這個案例之前，請先建立四個使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="89ed3-177">Before you begin this scenario, create four user accounts.</span></span> <span data-ttu-id="89ed3-178">在案例中，您會將下列其中一個 AGPM 角色指派給每個帳戶： AGPM 系統管理員（完全控制）、審核者、編輯者和檢閱者。</span><span class="sxs-lookup"><span data-stu-id="89ed3-178">During the scenario, you will assign one of the following AGPM roles to each of these accounts: AGPM Administrator (Full Control), Approver, Editor, and Reviewer.</span></span> <span data-ttu-id="89ed3-179">這些帳戶必須能夠傳送及接收電子郵件訊息。</span><span class="sxs-lookup"><span data-stu-id="89ed3-179">These accounts must be able to send and receive e-mail messages.</span></span> <span data-ttu-id="89ed3-180">針對具有 AGPM 系統管理員、核准者及（選擇性）編輯者角色的帳戶，指派**連結 gpo**許可權。</span><span class="sxs-lookup"><span data-stu-id="89ed3-180">Assign **Link GPOs** permission to the accounts that have the AGPM Administrator, Approver, and (optionally) Editor roles.</span></span>

<span data-ttu-id="89ed3-181">**記事** 
預設會將 [**連結 gpo** ] 許可權指派給網域管理員和企業系統管理員的成員。</span><span class="sxs-lookup"><span data-stu-id="89ed3-181">**Note**
**Link GPOs** permission is assigned to members of Domain Administrators and Enterprise Administrators by default.</span></span> <span data-ttu-id="89ed3-182">若要將**連結 gpo**許可權指派給其他使用者或群組（例如擁有 AGPM 管理員或核准者角色的帳戶），請按一下該網域的節點，然後按一下 [**委派**] 索引標籤，選取 [**連結 Gpo**]，按一下 [**新增**]，然後選取您要指派許可權的使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="89ed3-182">To assign **Link GPOs** permission to additional users or groups (such as accounts that have the roles of AGPM Administrator or Approver), click the node for the domain and then click the **Delegation** tab, select **Link GPOs**, click **Add**, and select users or groups to which you want to assign the permission.</span></span>

 

## <span data-ttu-id="89ed3-183">安裝和設定 AGPM 的步驟</span><span class="sxs-lookup"><span data-stu-id="89ed3-183">Steps for installing and configuring AGPM</span></span>


<span data-ttu-id="89ed3-184">您必須完成下列步驟，才能安裝及設定 AGPM。</span><span class="sxs-lookup"><span data-stu-id="89ed3-184">You must complete the following steps to install and configure AGPM.</span></span>

[<span data-ttu-id="89ed3-185">步驟1：安裝 AGPM 服務器</span><span class="sxs-lookup"><span data-stu-id="89ed3-185">Step 1: Install AGPM Server</span></span>](#bkmk-config1)

[<span data-ttu-id="89ed3-186">步驟2：安裝 AGPM 用戶端</span><span class="sxs-lookup"><span data-stu-id="89ed3-186">Step 2: Install AGPM Client</span></span>](#bkmk-config2)

[<span data-ttu-id="89ed3-187">步驟3：設定 AGPM 服務器連線</span><span class="sxs-lookup"><span data-stu-id="89ed3-187">Step 3: Configure an AGPM Server connection</span></span>](#bkmk-config3)

[<span data-ttu-id="89ed3-188">步驟4：設定電子郵件通知</span><span class="sxs-lookup"><span data-stu-id="89ed3-188">Step 4: Configure e-mail notification</span></span>](#bkmk-config4)

[<span data-ttu-id="89ed3-189">步驟5：委派存取權</span><span class="sxs-lookup"><span data-stu-id="89ed3-189">Step 5: Delegate access</span></span>](#bkmk-config5)

### <a href="" id="bkmk-config1"></a><span data-ttu-id="89ed3-190">步驟1：安裝 AGPM 服務器</span><span class="sxs-lookup"><span data-stu-id="89ed3-190">Step 1: Install AGPM Server</span></span>

<span data-ttu-id="89ed3-191">在這個步驟中，您會在將執行 AGPM 服務的成員伺服器或網網域控制站上安裝 [AGPM 服務器]，然後設定封存。</span><span class="sxs-lookup"><span data-stu-id="89ed3-191">In this step, you install AGPM Server on the member server or domain controller that will run the AGPM Service, and you configure the archive.</span></span> <span data-ttu-id="89ed3-192">所有的 AGPM 作業都是透過此 Windows 服務來管理，並以服務的認證執行。</span><span class="sxs-lookup"><span data-stu-id="89ed3-192">All AGPM operations are managed through this Windows service and are executed with the service's credentials.</span></span> <span data-ttu-id="89ed3-193">您可以將 AGPM 服務器所管理的封存放在該伺服器或同一林中的另一台伺服器上。</span><span class="sxs-lookup"><span data-stu-id="89ed3-193">The archive managed by an AGPM Server can be hosted on that server or on another server in the same forest.</span></span>

**<span data-ttu-id="89ed3-194">若要在將裝載 AGPM 服務的電腦上安裝 AGPM 服務器</span><span class="sxs-lookup"><span data-stu-id="89ed3-194">To install AGPM Server on the computer that will host the AGPM Service</span></span>**

1.  <span data-ttu-id="89ed3-195">以網域系統管理員群組成員的帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="89ed3-195">Log on with an account that is a member of the Domain Admins group.</span></span>

2.  <span data-ttu-id="89ed3-196">啟動 Microsoft 桌面優化套件 CD，然後依照螢幕上的指示進行，以選取 [**高級群組原則管理-伺服器**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-196">Start the Microsoft Desktop Optimization Pack CD and follow the instructions on screen to select **Advanced Group Policy Management - Server**.</span></span>

3.  <span data-ttu-id="89ed3-197">在 [**歡迎**] 對話方塊中，按一下 **[下一步**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-197">In the **Welcome** dialog box, click **Next**.</span></span>

4.  <span data-ttu-id="89ed3-198">在 [ **Microsoft 軟體授權條款**] 對話方塊中，接受條款，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="89ed3-198">In the **Microsoft Software License Terms** dialog box, accept the terms and then click **Next**.</span></span>

5.  <span data-ttu-id="89ed3-199">在 [**應用程式路徑**] 對話方塊中，選取要安裝 [AGPM 服務器] 的位置。</span><span class="sxs-lookup"><span data-stu-id="89ed3-199">In the **Application Path** dialog box, select a location in which to install AGPM Server.</span></span> <span data-ttu-id="89ed3-200">安裝了 AGPM 服務器的電腦將會主持 AGPM 服務並管理封存。</span><span class="sxs-lookup"><span data-stu-id="89ed3-200">The computer on which AGPM Server is installed will host the AGPM Service and manage the archive.</span></span> <span data-ttu-id="89ed3-201">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="89ed3-201">Click **Next**.</span></span>

6.  <span data-ttu-id="89ed3-202">在 [封存**路徑**] 對話方塊中，針對 AGPM 服務器選取要封存的位置。</span><span class="sxs-lookup"><span data-stu-id="89ed3-202">In the **Archive Path** dialog box, select a location for the archive in relation to the AGPM Server.</span></span> <span data-ttu-id="89ed3-203">封存路徑可以指向您在 AGPM 服務器或其他位置的資料夾。</span><span class="sxs-lookup"><span data-stu-id="89ed3-203">The archive path can point to a folder on the AGPM Server or elsewhere.</span></span> <span data-ttu-id="89ed3-204">不過，您應該選取一個位置，讓您有足夠的空間來儲存此 AGPM 服務器所管理的所有 Gpo 及歷程記錄資料。</span><span class="sxs-lookup"><span data-stu-id="89ed3-204">However, you should select a location with sufficient space to store all GPOs and history data managed by this AGPM Server.</span></span> <span data-ttu-id="89ed3-205">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="89ed3-205">Click **Next**.</span></span>

7.  <span data-ttu-id="89ed3-206">在 [ **Agpm 服務帳戶**] 對話方塊中，選取 agpm 服務將在其下執行的服務帳戶，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="89ed3-206">In the **AGPM Service Account** dialog box, select a service account under which the AGPM Service will run and then click **Next**.</span></span>

    <span data-ttu-id="89ed3-207">這個帳戶必須是網域系統管理員群組的成員，或是針對最低許可權設定，由 AGPM 服務器管理的每個網域中的下列群組：</span><span class="sxs-lookup"><span data-stu-id="89ed3-207">This account must be a member of the either the Domain Admins group or, for a least-privilege configuration, the following groups in each domain managed by the AGPM Server:</span></span>

    -   <span data-ttu-id="89ed3-208">群組原則建立者擁有者</span><span class="sxs-lookup"><span data-stu-id="89ed3-208">Group Policy Creator Owners</span></span>

    -   <span data-ttu-id="89ed3-209">備份運算子</span><span class="sxs-lookup"><span data-stu-id="89ed3-209">Backup Operators</span></span>

    <span data-ttu-id="89ed3-210">此外，這個帳戶需要下列資料夾的 [完全控制] 許可權：</span><span class="sxs-lookup"><span data-stu-id="89ed3-210">Additionally, this account requires Full Control permission for the following folders:</span></span>

    -   <span data-ttu-id="89ed3-211">您的 AGPM 封存資料夾，此許可權會在安裝在本機磁片磁碟機上的 AGPM 服務器期間自動授與。</span><span class="sxs-lookup"><span data-stu-id="89ed3-211">The AGPM archive folder, for which this permission is automatically granted during the installation of AGPM Server if it is installed on a local drive.</span></span>

    -   <span data-ttu-id="89ed3-212">本機系統 temp 資料夾，通常是%windir%\\temp。</span><span class="sxs-lookup"><span data-stu-id="89ed3-212">The local system temp folder, typically %windir%\\temp.</span></span>

8.  <span data-ttu-id="89ed3-213">在 [封存**擁有**者] 對話方塊中，選取您指派 [AGPM 管理員] （完全控制）角色的帳戶或群組。</span><span class="sxs-lookup"><span data-stu-id="89ed3-213">In the **Archive Owner** dialog box, select an account or group to which you assign the AGPM Administrator (Full Control) role.</span></span> <span data-ttu-id="89ed3-214">AGPM 管理員可以為其他群組原則管理員指派 AGPM 角色和許可權，以便在稍後您可以將 AGPM 系統管理員的角色指派給其他的群組原則系統管理員。</span><span class="sxs-lookup"><span data-stu-id="89ed3-214">AGPM Administrators can assign AGPM roles and permissions to other Group Policy administrators, so that later you can assign the role of AGPM Administrator to additional Group Policy administrators.</span></span> <span data-ttu-id="89ed3-215">在此案例中，選取要在 AGPM 系統管理員角色中提供的帳戶。</span><span class="sxs-lookup"><span data-stu-id="89ed3-215">For this scenario, select the account to serve in the AGPM Administrator role.</span></span> <span data-ttu-id="89ed3-216">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="89ed3-216">Click **Next**.</span></span>

9.  <span data-ttu-id="89ed3-217">在 [**埠**設定] 對話方塊中，輸入 AGPM 服務應該聆聽的埠。</span><span class="sxs-lookup"><span data-stu-id="89ed3-217">In the **Port Configuration** dialog box, type a port on which the AGPM Service should listen.</span></span> <span data-ttu-id="89ed3-218">除非您手動設定埠例外狀況，或使用規則來設定埠例外，否則請不要清除 [**將埠例外新增到防火牆**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="89ed3-218">Do not clear the **Add port exception to firewall** check box unless you manually configure port exceptions or use rules to configure port exceptions.</span></span> <span data-ttu-id="89ed3-219">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="89ed3-219">Click **Next**.</span></span>

10. <span data-ttu-id="89ed3-220">在 [**語言**] 對話方塊中，選取一或多個要為 AGPM 服務器安裝的顯示語言。</span><span class="sxs-lookup"><span data-stu-id="89ed3-220">In the **Languages** dialog box, select one or more display languages to install for AGPM Server.</span></span>

11. <span data-ttu-id="89ed3-221">按一下 [**安裝**]，然後按一下 **[完成] 結束**設定向導。</span><span class="sxs-lookup"><span data-stu-id="89ed3-221">Click **Install**, and then click **Finish** to exit the Setup Wizard.</span></span>

    <span data-ttu-id="89ed3-222">**小心** 請勿透過作業系統中的 [**管理工具**] 和 [**服務**] 來變更 AGPM 服務的設定。</span><span class="sxs-lookup"><span data-stu-id="89ed3-222">**Caution** Do not change settings for the AGPM Service through **Administrative Tools** and **Services** in the operating system.</span></span> <span data-ttu-id="89ed3-223">執行此動作可能會使 AGPM 服務無法啟動。</span><span class="sxs-lookup"><span data-stu-id="89ed3-223">Doing this can prevent the AGPM Service from starting.</span></span> <span data-ttu-id="89ed3-224">如需如何變更服務設定的相關資訊，請參閱高級群組原則管理的說明。</span><span class="sxs-lookup"><span data-stu-id="89ed3-224">For information about how to change settings for the service, see Help for Advanced Group Policy Management.</span></span>

     

### <a href="" id="bkmk-config2"></a><span data-ttu-id="89ed3-225">步驟2：安裝 AGPM 用戶端</span><span class="sxs-lookup"><span data-stu-id="89ed3-225">Step 2: Install AGPM Client</span></span>

<span data-ttu-id="89ed3-226">每個群組原則管理員（任何建立、編輯、部署、評論或刪除 Gpo 的人）都必須在其所用的電腦上安裝 AGPM 用戶端，才能管理 Gpo。</span><span class="sxs-lookup"><span data-stu-id="89ed3-226">Each Group Policy administrator—anyone who creates, edits, deploys, reviews, or deletes GPOs—must have AGPM Client installed on computers that they use to manage GPOs.</span></span> <span data-ttu-id="89ed3-227">您用來執行許多 GPO 管理工作的 [變更控制] 節點，只會在您安裝 AGPM 用戶端時，才會出現在 [群組原則管理] 主控台中。</span><span class="sxs-lookup"><span data-stu-id="89ed3-227">The Change Control node, which you use to perform many of the GPO management tasks, appears in the Group Policy Management Console only if you install the AGPM Client.</span></span> <span data-ttu-id="89ed3-228">在這種情況下，您必須在至少一部電腦上安裝 [AGPM 用戶端]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-228">For this scenario, you install AGPM Client on at least one computer.</span></span> <span data-ttu-id="89ed3-229">您不需要在不執行「組原則管理」的最終使用者電腦上安裝 AGPM 用戶端。</span><span class="sxs-lookup"><span data-stu-id="89ed3-229">You do not need to install AGPM Client on the computers of end users who do not perform Group Policy administration.</span></span>

**<span data-ttu-id="89ed3-230">在群組原則系統管理員的電腦上安裝 AGPM 用戶端</span><span class="sxs-lookup"><span data-stu-id="89ed3-230">To install AGPM Client on the computer of a Group Policy administrator</span></span>**

1.  <span data-ttu-id="89ed3-231">啟動 Microsoft 桌面優化套件 CD，然後依照螢幕上的指示選取 [**高級組原則管理-用戶端**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-231">Start the Microsoft Desktop Optimization Pack CD and follow the instructions on screen to select **Advanced Group Policy Management - Client**.</span></span>

2.  <span data-ttu-id="89ed3-232">在 [**歡迎**] 對話方塊中，按一下 **[下一步**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-232">In the **Welcome** dialog box, click **Next**.</span></span>

3.  <span data-ttu-id="89ed3-233">在 [ **Microsoft 軟體授權條款**] 對話方塊中，接受條款，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="89ed3-233">In the **Microsoft Software License Terms** dialog box, accept the terms and then click **Next**.</span></span>

4.  <span data-ttu-id="89ed3-234">在 [**應用程式路徑**] 對話方塊中，選取要安裝 AGPM 用戶端的位置。</span><span class="sxs-lookup"><span data-stu-id="89ed3-234">In the **Application Path** dialog box, select a location in which to install AGPM Client.</span></span> <span data-ttu-id="89ed3-235">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="89ed3-235">Click **Next**.</span></span>

5.  <span data-ttu-id="89ed3-236">在 [ **Agpm 伺服器**] 對話方塊中，輸入您要連接的 agpm 伺服器和埠的 DNS 名稱或 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="89ed3-236">In the **AGPM Server** dialog box, type the DNS name or IP address for the AGPM Server and the port to which you want to connect.</span></span> <span data-ttu-id="89ed3-237">AGPM 服務的預設埠是4600。</span><span class="sxs-lookup"><span data-stu-id="89ed3-237">The default port for the AGPM Service is 4600.</span></span> <span data-ttu-id="89ed3-238">請勿清除 [**透過防火牆允許 Microsoft 管理主控台**] 核取方塊，除非您手動設定埠例外狀況，或使用規則來設定埠例外狀況。</span><span class="sxs-lookup"><span data-stu-id="89ed3-238">Do not clear the **Allow Microsoft Management Console through the firewall** check box unless you manually configure port exceptions or use rules to configure port exceptions.</span></span> <span data-ttu-id="89ed3-239">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="89ed3-239">Click **Next**.</span></span>

6.  <span data-ttu-id="89ed3-240">在 [**語言**] 對話方塊中，選取一或多個要為 AGPM 用戶端安裝的顯示語言。</span><span class="sxs-lookup"><span data-stu-id="89ed3-240">In the **Languages** dialog box, select one or more display languages to install for AGPM Client.</span></span>

7.  <span data-ttu-id="89ed3-241">按一下 [**安裝**]，然後按一下 **[完成] 結束**設定向導。</span><span class="sxs-lookup"><span data-stu-id="89ed3-241">Click **Install**, and then click **Finish** to exit the Setup Wizard.</span></span>

### <a href="" id="bkmk-config3"></a><span data-ttu-id="89ed3-242">步驟3：設定 AGPM 服務器連線</span><span class="sxs-lookup"><span data-stu-id="89ed3-242">Step 3: Configure an AGPM Server connection</span></span>

<span data-ttu-id="89ed3-243">AGPM 會儲存每個受控群組原則物件（GPO）的所有版本，也就是在中央封存中，AGPM 提供變更控制的每個 GPO。</span><span class="sxs-lookup"><span data-stu-id="89ed3-243">AGPM stores all versions of each controlled Group Policy Object (GPO), that is, each GPO for which AGPM provides change control, in a central archive.</span></span> <span data-ttu-id="89ed3-244">這可讓群組原則管理員在離線時查看和變更 Gpo，而不會立即影響每個 GPO 的部署版本。</span><span class="sxs-lookup"><span data-stu-id="89ed3-244">This lets Group Policy administrators view and change GPOs offline without immediately affecting the deployed version of each GPO.</span></span>

<span data-ttu-id="89ed3-245">在這個步驟中，您要設定 AGPM 服務器連線，並確保所有群組原則管理員都連線到相同的 AGPM 服務器。</span><span class="sxs-lookup"><span data-stu-id="89ed3-245">In this step, you configure an AGPM Server connection and ensure that all Group Policy administrators connect to the same AGPM Server.</span></span> <span data-ttu-id="89ed3-246">（如需有關如何設定多個 AGPM 服務器的詳細資訊，請參閱高級群組原則管理的說明。）</span><span class="sxs-lookup"><span data-stu-id="89ed3-246">(For information about how to configure multiple AGPM Servers, see Help for Advanced Group Policy Management.)</span></span>

**<span data-ttu-id="89ed3-247">針對所有群組原則管理員設定 AGPM 服務器連線</span><span class="sxs-lookup"><span data-stu-id="89ed3-247">To configure an AGPM Server connection for all Group Policy administrators</span></span>**

1.  <span data-ttu-id="89ed3-248">在已安裝 AGPM 用戶端的電腦上，以您選取做為封存擁有者的使用者帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="89ed3-248">On a computer on which you have installed AGPM Client, log on with the user account that you selected as the Archive Owner.</span></span> <span data-ttu-id="89ed3-249">此使用者擁有 AGPM 系統管理員的角色（完全控制）。</span><span class="sxs-lookup"><span data-stu-id="89ed3-249">This user has the role of AGPM Administrator (Full Control).</span></span>

2.  <span data-ttu-id="89ed3-250">按一下 [**開始**]，指向 [系統**管理工具**]，然後按一下 [**群組原則管理**] 來開啟 GPMC。</span><span class="sxs-lookup"><span data-stu-id="89ed3-250">Click **Start**, point to **Administrative Tools**, and then click **Group Policy Management** to open the GPMC.</span></span>

3.  <span data-ttu-id="89ed3-251">編輯套用至所有群組原則系統管理員的 GPO。</span><span class="sxs-lookup"><span data-stu-id="89ed3-251">Edit a GPO that is applied to all Group Policy administrators.</span></span>

4.  <span data-ttu-id="89ed3-252">在 [**群組原則管理編輯器**] 視窗中，按兩下 [**使用者**設定]、[**原則**]、[系統**管理範本**]、[ **Windows 元件**] 和 [ **AGPM**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-252">In the **Group Policy Management Editor** window, double-click **User Configuration**, **Policies**, **Administrative Templates**, **Windows Components**, and **AGPM**.</span></span>

5.  <span data-ttu-id="89ed3-253">在 [詳細資料] 窗格中，按兩下 [ **agpm]：指定預設的 Agpm 伺服器（所有網域）**。</span><span class="sxs-lookup"><span data-stu-id="89ed3-253">In the details pane, double-click **AGPM: Specify default AGPM Server (all domains)**.</span></span>

6.  <span data-ttu-id="89ed3-254">在 [**屬性**] 視窗中，選取 [**啟用**]，然後輸入裝載封存之伺服器的 DNS 名稱或 IP 位址與埠（例如， **server.contoso.com:4600**）。</span><span class="sxs-lookup"><span data-stu-id="89ed3-254">In the **Properties** window, select **Enabled** and type the DNS name or IP address and port (for example, **server.contoso.com:4600**) for the server hosting the archive.</span></span> <span data-ttu-id="89ed3-255">根據預設，AGPM 服務會使用埠4600。</span><span class="sxs-lookup"><span data-stu-id="89ed3-255">By default, the AGPM Service uses port 4600.</span></span>

7.  <span data-ttu-id="89ed3-256">按一下 **[確定]**，然後關閉 [**群組原則管理編輯器**] 視窗。</span><span class="sxs-lookup"><span data-stu-id="89ed3-256">Click **OK**, and then close the **Group Policy Management Editor** window.</span></span> <span data-ttu-id="89ed3-257">更新群組原則時，會針對每個群組原則管理員設定 AGPM 服務器連線。</span><span class="sxs-lookup"><span data-stu-id="89ed3-257">When Group Policy is updated, the AGPM Server connection is configured for each Group Policy administrator.</span></span>

### <a href="" id="bkmk-config4"></a><span data-ttu-id="89ed3-258">步驟4：設定電子郵件通知</span><span class="sxs-lookup"><span data-stu-id="89ed3-258">Step 4: Configure e-mail notification</span></span>

<span data-ttu-id="89ed3-259">在 AGPM 系統管理員（完全控制）中，您可以指定要在編輯者嘗試建立、部署或刪除 GPO 時，傳送包含要求之電子郵件訊息之核准者和 AGPM 系統管理員的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="89ed3-259">As an AGPM Administrator (Full Control), you designate the e-mail addresses of Approvers and AGPM Administrators to whom an e-mail message that contains a request is sent when an Editor tries to create, deploy, or delete a GPO.</span></span> <span data-ttu-id="89ed3-260">您也可以決定要從哪個別名傳送郵件。</span><span class="sxs-lookup"><span data-stu-id="89ed3-260">You also determine the alias from which these messages are sent.</span></span>

**<span data-ttu-id="89ed3-261">若要設定 AGPM 的電子郵件通知</span><span class="sxs-lookup"><span data-stu-id="89ed3-261">To configure e-mail notification for AGPM</span></span>**

1.  <span data-ttu-id="89ed3-262">在 [**群組原則管理編輯器**] 中，流覽至 [**變更控制**] 資料夾</span><span class="sxs-lookup"><span data-stu-id="89ed3-262">In **Group Policy Management Editor** , navigate to the **Change Control** folder</span></span> 

2.  <span data-ttu-id="89ed3-263">在 [詳細資料] 窗格中，按一下 [**網域委派**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="89ed3-263">In the details pane, click the **Domain Delegation** tab.</span></span>

3.  <span data-ttu-id="89ed3-264">在 [**寄件者電子郵件地址**] 欄位中，輸入要傳送通知的 AGPM 電子郵件別名。</span><span class="sxs-lookup"><span data-stu-id="89ed3-264">In the **From e-mail address** field, type the e-mail alias for AGPM from which notifications should be sent.</span></span>

4.  <span data-ttu-id="89ed3-265">在 [收**件者電子郵件地址**] 欄位中，輸入您要指派核准者角色的使用者帳戶的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="89ed3-265">In the **To e-mail address** field, type the e-mail address for the user account to which you intend to assign the Approver role.</span></span>

5.  <span data-ttu-id="89ed3-266">在 [ **SMTP 伺服器**] 欄位中，輸入有效的 SMTP 郵件伺服器。</span><span class="sxs-lookup"><span data-stu-id="89ed3-266">In the **SMTP server** field, type a valid SMTP mail server.</span></span>

6.  <span data-ttu-id="89ed3-267">在 [**使用者名稱**] 和 [**密碼**] 欄位中，輸入具有 SMTP 服務存取權的使用者認證。</span><span class="sxs-lookup"><span data-stu-id="89ed3-267">In the **User name** and **Password** fields, type the credentials of a user who has access to the SMTP service.</span></span> <span data-ttu-id="89ed3-268">按一下 **\[Apply\]** (套用)。</span><span class="sxs-lookup"><span data-stu-id="89ed3-268">Click **Apply**.</span></span>

### <a href="" id="bkmk-config5"></a><span data-ttu-id="89ed3-269">步驟5：委派存取權</span><span class="sxs-lookup"><span data-stu-id="89ed3-269">Step 5: Delegate access</span></span>

<span data-ttu-id="89ed3-270">作為 AGPM 系統管理員（完全控制），您可以委派網域層級對 Gpo 的存取權，將角色指派給每個群組原則管理員的帳戶。</span><span class="sxs-lookup"><span data-stu-id="89ed3-270">As an AGPM Administrator (Full Control), you delegate domain-level access to GPOs, assigning roles to the account of each Group Policy administrator.</span></span>

<span data-ttu-id="89ed3-271">**記事** 您也可以在 GPO 層級（而非網域層級）委派存取權。</span><span class="sxs-lookup"><span data-stu-id="89ed3-271">**Note** You can also delegate access at the GPO level instead of the domain level.</span></span> <span data-ttu-id="89ed3-272">如需詳細資訊，請參閱高級群組原則管理的說明。</span><span class="sxs-lookup"><span data-stu-id="89ed3-272">For more information, see Help for Advanced Group Policy Management.</span></span>

 

<span data-ttu-id="89ed3-273">**重要** 您應該限制 [群組原則建立者擁有者] 群組中的成員資格，讓它不能用來避開對 Gpo 的 [AGPM] 管理。</span><span class="sxs-lookup"><span data-stu-id="89ed3-273">**Important** You should restrict membership in the Group Policy Creator Owners group so that it cannot be used to circumvent AGPM management of access to GPOs.</span></span> <span data-ttu-id="89ed3-274">（在 [**群組原則管理主控台**] 中，按一下要管理 gpo 的林和網域中的 [**群組原則物件**]，按一下 [**委派**]，然後設定設定以符合貴組織的需求。）</span><span class="sxs-lookup"><span data-stu-id="89ed3-274">(In the **Group Policy Management Console**, click **Group Policy Objects** in the forest and domain in which you want to manage GPOs, click **Delegation**, and then configure the settings to meet the needs of your organization.)</span></span>

 

**<span data-ttu-id="89ed3-275">若要委派整個網域中所有 Gpo 的存取權</span><span class="sxs-lookup"><span data-stu-id="89ed3-275">To delegate access to all GPOs throughout a domain</span></span>**

1.  <span data-ttu-id="89ed3-276">在 [**網域委派**] 索引標籤上，按一下 [**新增**] 按鈕，選取 [群組原則管理員] 的使用者帳戶作為 [核准者]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="89ed3-276">On the **Domain Delegation** tab, click the **Add** button, select the user account of the Group Policy administrator to serve as Approver, and then click **OK**.</span></span>

2.  <span data-ttu-id="89ed3-277">在 [**新增群組或使用者**] 對話方塊中，選取要指派該角色給帳戶的**核准者**角色，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="89ed3-277">In the **Add Group or User** dialog box, select the **Approver** role to assign that role to the account, and then click **OK**.</span></span> <span data-ttu-id="89ed3-278">（此角色包含檢閱者角色）。</span><span class="sxs-lookup"><span data-stu-id="89ed3-278">(This role includes the Reviewer role.)</span></span>

3.  <span data-ttu-id="89ed3-279">按一下 [**新增**] 按鈕，選取 [群組原則管理員] 的使用者帳戶做為 [編輯者]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="89ed3-279">Click the **Add** button, select the user account of the Group Policy administrator to serve as Editor, and then click **OK**.</span></span>

4.  <span data-ttu-id="89ed3-280">在 [**新增群組或使用者**] 對話方塊中，選取要將該角色指派給帳戶的 [**編輯**者角色]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="89ed3-280">In the **Add Group or User** dialog box, select the **Editor** role to assign that role to the account, and then click **OK**.</span></span> <span data-ttu-id="89ed3-281">（此角色包含檢閱者角色）。</span><span class="sxs-lookup"><span data-stu-id="89ed3-281">(This role includes the Reviewer role.)</span></span>

5.  <span data-ttu-id="89ed3-282">按一下 [**新增**] 按鈕，選取 [群組原則管理員] 的使用者帳戶作為 [審查員]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="89ed3-282">Click the **Add** button, select the user account of the Group Policy administrator to serve as Reviewer, and then click **OK**.</span></span>

6.  <span data-ttu-id="89ed3-283">在 [**新增群組或使用者**] 對話方塊中，選取**檢閱者**角色，只將該角色指派給該帳戶。</span><span class="sxs-lookup"><span data-stu-id="89ed3-283">In the **Add Group or User** dialog box, select the **Reviewer** role to assign only that role to the account.</span></span>

## <span data-ttu-id="89ed3-284">管理 Gpo 的步驟</span><span class="sxs-lookup"><span data-stu-id="89ed3-284">Steps for managing GPOs</span></span>


<span data-ttu-id="89ed3-285">您必須完成下列步驟，才能使用 AGPM 來建立、編輯、審閱及部署 Gpo。</span><span class="sxs-lookup"><span data-stu-id="89ed3-285">You must complete the following steps to create, edit, review, and deploy GPOs by using AGPM.</span></span> <span data-ttu-id="89ed3-286">此外，您還會建立範本、刪除 GPO，並還原刪除的 GPO。</span><span class="sxs-lookup"><span data-stu-id="89ed3-286">Additionally, you will create a template, delete a GPO, and restore a deleted GPO.</span></span>

[<span data-ttu-id="89ed3-287">步驟1：建立 GPO</span><span class="sxs-lookup"><span data-stu-id="89ed3-287">Step 1: Create a GPO</span></span>](#bkmk-manage1)

[<span data-ttu-id="89ed3-288">步驟2：編輯 GPO</span><span class="sxs-lookup"><span data-stu-id="89ed3-288">Step 2: Edit a GPO</span></span>](#bkmk-manage2)

[<span data-ttu-id="89ed3-289">步驟3：審查及部署 GPO</span><span class="sxs-lookup"><span data-stu-id="89ed3-289">Step 3: Review and deploy a GPO</span></span>](#bkmk-manage3)

[<span data-ttu-id="89ed3-290">步驟4：使用範本建立 GPO</span><span class="sxs-lookup"><span data-stu-id="89ed3-290">Step 4: Use a template to create a GPO</span></span>](#bkmk-manage4)

[<span data-ttu-id="89ed3-291">步驟5：刪除及還原 GPO</span><span class="sxs-lookup"><span data-stu-id="89ed3-291">Step 5: Delete and restore a GPO</span></span>](#bkmk-manage5)

### <a href="" id="bkmk-manage1"></a><span data-ttu-id="89ed3-292">步驟1：建立 GPO</span><span class="sxs-lookup"><span data-stu-id="89ed3-292">Step 1: Create a GPO</span></span>

<span data-ttu-id="89ed3-293">在有多個群組原則管理員的環境中，具有 [編輯者] 角色的人員可以要求建立新的 Gpo。</span><span class="sxs-lookup"><span data-stu-id="89ed3-293">In an environment that has multiple Group Policy administrators, those with the Editor role can request that new GPOs be created.</span></span> <span data-ttu-id="89ed3-294">不過，該要求必須由擁有核准者角色的人員核准。</span><span class="sxs-lookup"><span data-stu-id="89ed3-294">However, that request must be approved by someone with the Approver role.</span></span>

<span data-ttu-id="89ed3-295">在這個步驟中，您會使用具有 Editor 角色的帳戶，以要求建立新的 GPO。</span><span class="sxs-lookup"><span data-stu-id="89ed3-295">In this step, you use an account that has the Editor role to request that a new GPO be created.</span></span> <span data-ttu-id="89ed3-296">您可以使用擁有核准者角色的帳戶，核准此要求以建立 GPO。</span><span class="sxs-lookup"><span data-stu-id="89ed3-296">Using an account that has the Approver role, you approve this request to create the GPO.</span></span>

**<span data-ttu-id="89ed3-297">要求透過 AGPM 建立並管理新的 GPO</span><span class="sxs-lookup"><span data-stu-id="89ed3-297">To request that a new GPO be created and managed through AGPM</span></span>**

1.  <span data-ttu-id="89ed3-298">在已安裝 AGPM 用戶端的電腦上，以 AGPM 中指派了 [編輯者角色] 的使用者帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="89ed3-298">On a computer on which you have installed AGPM Client, log on with a user account that is assigned the Editor role in AGPM.</span></span>

2.  <span data-ttu-id="89ed3-299">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-299">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

3.  <span data-ttu-id="89ed3-300">以滑鼠右鍵按一下 [**變更控制**] 節點，然後按一下 [**新增受控制的 GPO**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-300">Right-click the **Change Control** node, and then click **New Controlled GPO**.</span></span>

4.  <span data-ttu-id="89ed3-301">在 [**新的受控 GPO** ] 對話方塊中：</span><span class="sxs-lookup"><span data-stu-id="89ed3-301">In the **New Controlled GPO** dialog box:</span></span>

    1.  <span data-ttu-id="89ed3-302">若要接收申請的複本，請在 [**抄送**] 欄位中輸入您的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="89ed3-302">To receive a copy of the request, type your e-mail address in the **Cc** field.</span></span>

    2.  <span data-ttu-id="89ed3-303">輸入**MyGPO**做為新 GPO 的名稱。</span><span class="sxs-lookup"><span data-stu-id="89ed3-303">Type **MyGPO** as the name for the new GPO.</span></span>

    3.  <span data-ttu-id="89ed3-304">輸入新 GPO 的批註。</span><span class="sxs-lookup"><span data-stu-id="89ed3-304">Type a comment for the new GPO.</span></span>

    4.  <span data-ttu-id="89ed3-305">按一下 [**建立即時**]，讓新的 GPO 在核准後立即部署到生產環境。</span><span class="sxs-lookup"><span data-stu-id="89ed3-305">Click **Create live** so that the new GPO will be deployed to the production environment immediately upon approval.</span></span> <span data-ttu-id="89ed3-306">按一下 **\[提交\]**。</span><span class="sxs-lookup"><span data-stu-id="89ed3-306">Click **Submit**.</span></span>

5.  <span data-ttu-id="89ed3-307">當 [ **AGPM 進度**] 視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-307">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="89ed3-308">新的 GPO 會顯示在 [**擱置**] 索引標籤上。</span><span class="sxs-lookup"><span data-stu-id="89ed3-308">The new GPO is displayed on the **Pending** tab.</span></span>

**<span data-ttu-id="89ed3-309">核准擱置的要求以建立 GPO</span><span class="sxs-lookup"><span data-stu-id="89ed3-309">To approve the pending request to create a GPO</span></span>**

1.  <span data-ttu-id="89ed3-310">在已安裝 [AGPM 用戶端] 的電腦上，使用在 AGPM 中擁有核准者角色的使用者帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="89ed3-310">On a computer on which you have installed AGPM Client, log on with a user account that has the role of Approver in AGPM.</span></span>

2.  <span data-ttu-id="89ed3-311">開啟該帳戶的電子郵件收件匣，請注意，您已從 AGPM 別名收到一封電子郵件，並要求您建立 GPO。</span><span class="sxs-lookup"><span data-stu-id="89ed3-311">Open the e-mail inbox for the account, and notice that you have received an e-mail message from the AGPM alias with the Editor's request to create a GPO.</span></span>

3.  <span data-ttu-id="89ed3-312">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-312">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

4.  <span data-ttu-id="89ed3-313">在 [**內容**] 索引標籤上，按一下 [**未決**] 索引標籤以顯示擱置中的 gpo。</span><span class="sxs-lookup"><span data-stu-id="89ed3-313">On the **Contents** tab, click the **Pending** tab to display the pending GPOs.</span></span>

5.  <span data-ttu-id="89ed3-314">以滑鼠右鍵按一下 [ **MyGPO**]，然後按一下 [**核准**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-314">Right-click **MyGPO**, and then click **Approve**.</span></span>

6.  <span data-ttu-id="89ed3-315">按一下 **[是]** 以確認核准，然後將 GPO 移至 [**受控**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="89ed3-315">Click **Yes** to confirm approval and move the GPO to the **Controlled** tab.</span></span>

### <a href="" id="bkmk-manage2"></a><span data-ttu-id="89ed3-316">步驟2：編輯 GPO</span><span class="sxs-lookup"><span data-stu-id="89ed3-316">Step 2: Edit a GPO</span></span>

<span data-ttu-id="89ed3-317">您可以使用 Gpo 來設定電腦或使用者設定，並將它們部署到許多電腦或使用者。</span><span class="sxs-lookup"><span data-stu-id="89ed3-317">You can use GPOs to configure computer or user settings and deploy them to many computers or users.</span></span> <span data-ttu-id="89ed3-318">在這個步驟中，您會使用擁有 Editor 角色的帳戶來從封存中取出 GPO、離線編輯 GPO、將編輯過的 GPO 核取到封存，並要求將 GPO 部署到生產環境。</span><span class="sxs-lookup"><span data-stu-id="89ed3-318">In this step, you use an account that has the Editor role to check out a GPO from the archive, edit the GPO offline, check the edited GPO into the archive, and request deployment of the GPO to the production environment.</span></span> <span data-ttu-id="89ed3-319">在這種情況下，您可以設定 GPO 中的設定，以要求密碼至少為八個字元長。</span><span class="sxs-lookup"><span data-stu-id="89ed3-319">For this scenario, you configure a setting in the GPO to require that the password be at least eight characters long.</span></span>

**<span data-ttu-id="89ed3-320">從封存檢查 GPO 以進行編輯</span><span class="sxs-lookup"><span data-stu-id="89ed3-320">To check the GPO out from the archive for editing</span></span>**

1.  <span data-ttu-id="89ed3-321">在已安裝 AGPM 用戶端的電腦上，使用在 AGPM 中擁有 [編輯者角色] 的使用者帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="89ed3-321">On a computer on which you have installed AGPM Client, log on with a user account that has the role of Editor in AGPM.</span></span>

2.  <span data-ttu-id="89ed3-322">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-322">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

3.  <span data-ttu-id="89ed3-323">在 [詳細資料] 窗格的 [**內容**] 索引標籤上，按一下 [**受控**] 索引標籤以顯示受控 gpo。</span><span class="sxs-lookup"><span data-stu-id="89ed3-323">On the **Contents** tab in the details pane, click the **Controlled** tab to display the controlled GPOs.</span></span>

4.  <span data-ttu-id="89ed3-324">以滑鼠右鍵按一下 [ **MyGPO**]，然後按一下 **[取出]。**</span><span class="sxs-lookup"><span data-stu-id="89ed3-324">Right-click **MyGPO**, and then click **Check Out**.</span></span>

5.  <span data-ttu-id="89ed3-325">輸入要在已取出之 GPO 之歷程記錄中顯示的批註，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="89ed3-325">Type a comment to be displayed in the history of the GPO while it is checked out, and then click **OK**.</span></span>

6.  <span data-ttu-id="89ed3-326">當 [ **AGPM 進度**] 視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-326">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="89ed3-327">在 [**受控**] 索引標籤上，GPO 的狀態會標示為 [**已取出**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-327">On the **Controlled** tab, the state of the GPO is identified as **Checked Out**.</span></span>

**<span data-ttu-id="89ed3-328">若要離線編輯 GPO 並設定最小密碼長度</span><span class="sxs-lookup"><span data-stu-id="89ed3-328">To edit the GPO offline and configure the minimum password length</span></span>**

1.  <span data-ttu-id="89ed3-329">在 [**受控**] 索引標籤上，以滑鼠右鍵按一下 [ **MyGPO**]，然後按一下 [**編輯**] 以開啟 [**群組原則管理編輯器**] 視窗，並變更 GPO 的離線複本。</span><span class="sxs-lookup"><span data-stu-id="89ed3-329">On the **Controlled** tab, right-click **MyGPO**, and then click **Edit** to open the **Group Policy Management Editor** window and change an offline copy of the GPO.</span></span> <span data-ttu-id="89ed3-330">在此案例中，請設定最小密碼長度：</span><span class="sxs-lookup"><span data-stu-id="89ed3-330">For this scenario, configure the minimum password length:</span></span>

    1.  <span data-ttu-id="89ed3-331">在 [**電腦**設定] 底下，按兩下 [**原則**]、[ **Windows 設定**]、[**安全性設定**]、[**帳戶原則**] 和 [**密碼原則**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-331">Under **Computer Configuration**, double-click **Policies**, **Windows Settings**, **Security Settings**, **Account Policies**, and **Password Policy**.</span></span>

    2.  <span data-ttu-id="89ed3-332">在 [詳細資料] 窗格中，按兩下 [**最小密碼長度**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-332">In the details pane, double-click **Minimum password length**.</span></span>

    3.  <span data-ttu-id="89ed3-333">在 [屬性] 視窗中，選取 [**定義這個原則設定**] 核取方塊，將字元數設為**8**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="89ed3-333">In the properties window, select the **Define this policy setting** check box, set the number of characters to **8**, and then click **OK**.</span></span>

2.  <span data-ttu-id="89ed3-334">關閉 [**群組原則管理編輯器**] 視窗。</span><span class="sxs-lookup"><span data-stu-id="89ed3-334">Close the **Group Policy Management Editor** window.</span></span>

**<span data-ttu-id="89ed3-335">將 GPO 檢查到封存</span><span class="sxs-lookup"><span data-stu-id="89ed3-335">To check the GPO into the archive</span></span>**

1.  <span data-ttu-id="89ed3-336">在 [**受控**] 索引標籤上，以滑鼠右鍵按一下**MyGPO** ，然後按一下 [**存回**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-336">On the **Controlled** tab, right-click **MyGPO** and then click **Check In**.</span></span>

2.  <span data-ttu-id="89ed3-337">輸入批註，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="89ed3-337">Type a comment, and then click **OK**.</span></span>

3.  <span data-ttu-id="89ed3-338">當 [ **AGPM 進度**] 視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-338">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="89ed3-339">在 [**受控**] 索引標籤上，GPO 的狀態會標示為 [**已核**取]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-339">On the **Controlled** tab, the state of the GPO is identified as **Checked In**.</span></span>

**<span data-ttu-id="89ed3-340">向生產環境要求 GPO 部署</span><span class="sxs-lookup"><span data-stu-id="89ed3-340">To request the deployment of the GPO to the production environment</span></span>**

1.  <span data-ttu-id="89ed3-341">在 [**受控**] 索引標籤上，以滑鼠右鍵按一下**MyGPO** ，然後按一下 [**部署**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-341">On the **Controlled** tab, right-click **MyGPO** and then click **Deploy**.</span></span>

2.  <span data-ttu-id="89ed3-342">因為此帳戶不是核准者或 AGPM 管理員，所以您必須提交部署的要求。</span><span class="sxs-lookup"><span data-stu-id="89ed3-342">Because this account is not an Approver or AGPM Administrator, you must submit a request for deployment.</span></span> <span data-ttu-id="89ed3-343">若要接收申請的複本，請在 [**抄送**] 欄位中輸入您的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="89ed3-343">To receive a copy of the request, type your e-mail address in the **Cc** field.</span></span> <span data-ttu-id="89ed3-344">輸入要顯示在 GPO 歷程記錄中的批註，然後按一下 [**提交**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-344">Type a comment to be displayed in the history of the GPO, and then click **Submit**.</span></span>

3.  <span data-ttu-id="89ed3-345">當 [ **AGPM 進度**] 視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-345">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="89ed3-346">**MyGPO**會顯示在 [**擱置**] 索引標籤上的 [gpo] 清單中。</span><span class="sxs-lookup"><span data-stu-id="89ed3-346">**MyGPO** is displayed on the list of GPOs on the **Pending** tab.</span></span>

### <a href="" id="bkmk-manage3"></a><span data-ttu-id="89ed3-347">步驟3：審查及部署 GPO</span><span class="sxs-lookup"><span data-stu-id="89ed3-347">Step 3: Review and deploy a GPO</span></span>

<span data-ttu-id="89ed3-348">在這個步驟中，您會擔當核准者、建立報告並分析設定，以及變更 GPO 中的設定，以判斷是否應該核准。</span><span class="sxs-lookup"><span data-stu-id="89ed3-348">In this step, you act as an Approver, creating reports and analyzing the settings and changes to settings in the GPO to determine whether you should approve them.</span></span> <span data-ttu-id="89ed3-349">在您評估 GPO 之後，您可以將它部署到生產環境，並將 GPO 連結至網域或組織單位（OU）。</span><span class="sxs-lookup"><span data-stu-id="89ed3-349">After you evaluate the GPO, you deploy it to the production environment and link the GPO to a domain or an organizational unit (OU).</span></span> <span data-ttu-id="89ed3-350">當針對該域或組織單位中的電腦重新整理群組原則時，GPO 就會生效。</span><span class="sxs-lookup"><span data-stu-id="89ed3-350">The GPO takes effect when Group Policy is refreshed for computers in that domain or OU.</span></span>

**<span data-ttu-id="89ed3-351">若要查看 GPO 中的設定</span><span class="sxs-lookup"><span data-stu-id="89ed3-351">To review settings in the GPO</span></span>**

1. <span data-ttu-id="89ed3-352">在已安裝 AGPM 用戶端的電腦上，以 AGPM 中指派擁有者角色的使用者帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="89ed3-352">On a computer on which you have installed AGPM Client, log on with a user account that is assigned the role of Approver in AGPM.</span></span> <span data-ttu-id="89ed3-353">任何具有檢閱者角色（包含在所有其他角色中）的群組原則管理員，都可以查看 GPO 中的設定。</span><span class="sxs-lookup"><span data-stu-id="89ed3-353">Any Group Policy administrator with the Reviewer role, which is included in all of the other roles, can review the settings in a GPO.</span></span>

2. <span data-ttu-id="89ed3-354">開啟該帳戶的電子郵件收件匣，請注意，您已收到來自 AGPM 別名的電子郵件，並要求您要部署 GPO。</span><span class="sxs-lookup"><span data-stu-id="89ed3-354">Open the e-mail inbox for the account and notice that you have received an e-mail message from the AGPM alias with an Editor's request to deploy a GPO.</span></span>

3. <span data-ttu-id="89ed3-355">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-355">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

4. <span data-ttu-id="89ed3-356">在 [詳細資料] 窗格的 [**內容**] 索引標籤上，按一下 [**擱置**] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="89ed3-356">On the **Contents** tab in the details pane, click the **Pending** tab.</span></span>

5. <span data-ttu-id="89ed3-357">按兩下 [ **MyGPO** ] 以顯示其歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="89ed3-357">Double-click **MyGPO** to display its history.</span></span>

6. <span data-ttu-id="89ed3-358">查看最新版本的 MyGPO 中的設定：</span><span class="sxs-lookup"><span data-stu-id="89ed3-358">Review the settings in the most recent version of MyGPO:</span></span>

   1.  <span data-ttu-id="89ed3-359">在 [歷程**記錄**] 視窗中，以滑鼠右鍵按一下包含最近時間戳記的 GPO 版本，按一下 [**設定**]，然後按一下 [ **HTML 報告**]，以顯示 GPO 設定的摘要。</span><span class="sxs-lookup"><span data-stu-id="89ed3-359">In the **History** window, right-click the GPO version with the most recent time stamp, click **Settings**, and then click **HTML Report** to display a summary of the GPO's settings.</span></span>

   2.  <span data-ttu-id="89ed3-360">在網頁瀏覽器中，按一下 [**全部顯示**] 以顯示 GPO 中的所有設定。</span><span class="sxs-lookup"><span data-stu-id="89ed3-360">In the Web browser, click **show all** to display all the settings in the GPO.</span></span> <span data-ttu-id="89ed3-361">關閉瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="89ed3-361">Close the browser.</span></span>

7. <span data-ttu-id="89ed3-362">將最新版本的 MyGPO 與簽入到封存的第一個版本進行比較：</span><span class="sxs-lookup"><span data-stu-id="89ed3-362">Compare the most recent version of MyGPO to the first version checked in to the archive:</span></span>

   1. <span data-ttu-id="89ed3-363">在 [歷程**記錄**] 視窗中，按一下包含最近時間戳記的 GPO 版本。</span><span class="sxs-lookup"><span data-stu-id="89ed3-363">In the **History** window, click the GPO version with the most recent time stamp.</span></span> <span data-ttu-id="89ed3-364">按住 CTRL，然後按一下**電腦版本**不是 \* \* \ \* \* \* 的最舊 GPO 版本。</span><span class="sxs-lookup"><span data-stu-id="89ed3-364">Press CTRL and then click the oldest GPO version for which the **Computer Version** is not \*\*\\*\*\*.</span></span>

   2. <span data-ttu-id="89ed3-365">按一下 [**差異**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="89ed3-365">Click the **Differences** button.</span></span> <span data-ttu-id="89ed3-366">[**帳戶原則/密碼原則**] 區段會以綠色醒目提示，並在前面加上**\ [+ \]**。</span><span class="sxs-lookup"><span data-stu-id="89ed3-366">The **Account Policies/Password Policy** section is highlighted in green and preceded by **\[+\]**.</span></span> <span data-ttu-id="89ed3-367">這表示設定只會在後一個 GPO 版本中設定。</span><span class="sxs-lookup"><span data-stu-id="89ed3-367">This indicates that the setting is configured only in the latter version of the GPO.</span></span>

   3. <span data-ttu-id="89ed3-368">按一下 [**帳戶原則/密碼原則**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-368">Click **Account Policies/Password Policy**.</span></span> <span data-ttu-id="89ed3-369">[**最小密碼長度**] 設定也會以綠色醒目提示，並在前面加上**\ [+ \]**，指出它僅在後一個 GPO 版本中進行設定。</span><span class="sxs-lookup"><span data-stu-id="89ed3-369">The **Minimum password length** setting is also highlighted in green and preceded by **\[+\]**, indicating that it is configured only in the latter version of the GPO.</span></span>

   4. <span data-ttu-id="89ed3-370">關閉網頁瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="89ed3-370">Close the Web browser.</span></span>

**<span data-ttu-id="89ed3-371">將 GPO 部署到生產環境</span><span class="sxs-lookup"><span data-stu-id="89ed3-371">To deploy the GPO to the production environment</span></span>**

1.  <span data-ttu-id="89ed3-372">在 [**擱置**] 索引標籤上，以滑鼠右鍵按一下 [ **MyGPO** ]，然後按一下 [**核准**]</span><span class="sxs-lookup"><span data-stu-id="89ed3-372">On the **Pending** tab, right-click **MyGPO** and then click **Approve**.</span></span>

2.  <span data-ttu-id="89ed3-373">輸入要包含在 GPO 歷程記錄中的批註。</span><span class="sxs-lookup"><span data-stu-id="89ed3-373">Type a comment to include in the history of the GPO.</span></span>

3.  <span data-ttu-id="89ed3-374">按一下 **\[是\]**。</span><span class="sxs-lookup"><span data-stu-id="89ed3-374">Click **Yes**.</span></span> <span data-ttu-id="89ed3-375">當 [ **AGPM 進度**] 視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-375">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="89ed3-376">GPO 已部署至生產環境。</span><span class="sxs-lookup"><span data-stu-id="89ed3-376">The GPO is deployed to the production environment.</span></span>

**<span data-ttu-id="89ed3-377">將 GPO 連結至網域或組織單位</span><span class="sxs-lookup"><span data-stu-id="89ed3-377">To link the GPO to a domain or organizational unit</span></span>**

1.  <span data-ttu-id="89ed3-378">在 GPMC 中，以滑鼠右鍵按一下您要套用您所設定之 GPO 的網域或組織單位（OU），然後按一下 [**連結現有的 gpo**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-378">In the GPMC, right-click either the domain or an organizational unit (OU) to which you want to apply the GPO that you configured, and then click **Link an Existing GPO**.</span></span>

2.  <span data-ttu-id="89ed3-379">在 [**選取 GPO** ] 對話方塊中，按一下 [ **MyGPO**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="89ed3-379">In the **Select GPO** dialog box, click **MyGPO**, and then click **OK**.</span></span>

### <a href="" id="bkmk-manage4"></a><span data-ttu-id="89ed3-380">步驟4：使用範本建立 GPO</span><span class="sxs-lookup"><span data-stu-id="89ed3-380">Step 4: Use a template to create a GPO</span></span>

<span data-ttu-id="89ed3-381">在這個步驟中，您會使用具有 Editor 角色的帳戶來建立及使用範本。</span><span class="sxs-lookup"><span data-stu-id="89ed3-381">In this step, you use an account that has the Editor role to create and use a template.</span></span> <span data-ttu-id="89ed3-382">該範本是 GPO 的靜態版本，用作建立新 Gpo 的起點。</span><span class="sxs-lookup"><span data-stu-id="89ed3-382">That template is a static version of a GPO for use as a starting point for creating new GPOs.</span></span> <span data-ttu-id="89ed3-383">雖然您無法編輯範本，但您可以根據範本建立新的 GPO。</span><span class="sxs-lookup"><span data-stu-id="89ed3-383">Although you cannot edit a template, you can create a new GPO based on a template.</span></span> <span data-ttu-id="89ed3-384">範本適用于快速建立包含許多相同原則設定的多個 Gpo。</span><span class="sxs-lookup"><span data-stu-id="89ed3-384">Templates are useful for quickly creating multiple GPOs that include many of the same policy settings.</span></span>

**<span data-ttu-id="89ed3-385">根據現有的 GPO 建立範本</span><span class="sxs-lookup"><span data-stu-id="89ed3-385">To create a template based on an existing GPO</span></span>**

1.  <span data-ttu-id="89ed3-386">在已安裝 AGPM 用戶端的電腦上，使用在 AGPM 中指派了 [編輯者角色] 的使用者帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="89ed3-386">On a computer on which you have installed AGPM Client, log on with a user account that is assigned the role of Editor in AGPM.</span></span>

2.  <span data-ttu-id="89ed3-387">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-387">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

3.  <span data-ttu-id="89ed3-388">在 [詳細資料] 窗格的 [**內容**] 索引標籤上，按一下 [**受控**] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="89ed3-388">On the **Contents** tab in the details pane, click the **Controlled** tab.</span></span>

4.  <span data-ttu-id="89ed3-389">以滑鼠右鍵按一下 [ **MyGPO**]，然後按一下 [**另存為範本**]，建立包含目前 MyGPO 中所有設定的範本。</span><span class="sxs-lookup"><span data-stu-id="89ed3-389">Right-click **MyGPO**, and then click **Save as Template** to create a template incorporating all settings currently in MyGPO.</span></span>

5.  <span data-ttu-id="89ed3-390">輸入**MyTemplate**做為範本的名稱和批註，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="89ed3-390">Type **MyTemplate** as the name for the template and a comment, and then click **OK**.</span></span>

6.  <span data-ttu-id="89ed3-391">當 [ **AGPM 進度**] 視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-391">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="89ed3-392">新範本隨即出現在 [**範本**] 索引標籤上。</span><span class="sxs-lookup"><span data-stu-id="89ed3-392">The new template appears on the **Templates** tab.</span></span>

**<span data-ttu-id="89ed3-393">要求透過 AGPM 建立並管理新的 GPO</span><span class="sxs-lookup"><span data-stu-id="89ed3-393">To request that a new GPO be created and managed through AGPM</span></span>**

1.  <span data-ttu-id="89ed3-394">按一下 [**受控**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="89ed3-394">Click the **Controlled** tab.</span></span>

2.  <span data-ttu-id="89ed3-395">以滑鼠右鍵按一下 [**變更控制**] 節點，然後按一下 [**新增受控制的 GPO**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-395">Right-click the **Change Control** node, and then click **New Controlled GPO**.</span></span>

3.  <span data-ttu-id="89ed3-396">在 [**新的受控 GPO** ] 對話方塊中：</span><span class="sxs-lookup"><span data-stu-id="89ed3-396">In the **New Controlled GPO** dialog box:</span></span>

    1.  <span data-ttu-id="89ed3-397">若要接收申請的複本，請在 [**抄送**] 欄位中輸入您的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="89ed3-397">To receive a copy of the request, type your e-mail address in the **Cc** field.</span></span>

    2.  <span data-ttu-id="89ed3-398">輸入**MyOtherGPO**做為新 GPO 的名稱。</span><span class="sxs-lookup"><span data-stu-id="89ed3-398">Type **MyOtherGPO** as the name for the new GPO.</span></span>

    3.  <span data-ttu-id="89ed3-399">輸入新 GPO 的批註。</span><span class="sxs-lookup"><span data-stu-id="89ed3-399">Type a comment for the new GPO.</span></span>

    4.  <span data-ttu-id="89ed3-400">按一下 [**建立即時**]，讓新的 GPO 在核准後立即部署到生產環境。</span><span class="sxs-lookup"><span data-stu-id="89ed3-400">Click **Create live** so that the new GPO will be deployed to the production environment immediately upon approval.</span></span>

    5.  <span data-ttu-id="89ed3-401">針對 [ **GPO 範本**]，選取 [ **MyTemplate**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-401">For **From GPO template**, select **MyTemplate**.</span></span> <span data-ttu-id="89ed3-402">按一下 **\[提交\]**。</span><span class="sxs-lookup"><span data-stu-id="89ed3-402">Click **Submit**.</span></span>

4.  <span data-ttu-id="89ed3-403">當 [ **AGPM 進度**] 視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-403">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="89ed3-404">新的 GPO 會顯示在 [**擱置**] 索引標籤上。</span><span class="sxs-lookup"><span data-stu-id="89ed3-404">The new GPO is displayed on the **Pending** tab.</span></span>

<span data-ttu-id="89ed3-405">使用獲指派核准者角色的帳戶來核准擱置的要求，以建立 GPO，就像您在[步驟1：建立 gpo](#bkmk-manage1)一樣。</span><span class="sxs-lookup"><span data-stu-id="89ed3-405">Use an account that is assigned the role of Approver to approve the pending request to create the GPO as you did in [Step 1: Create a GPO](#bkmk-manage1).</span></span> <span data-ttu-id="89ed3-406">MyTemplate 合併了您在 MyGPO 中設定的所有設定。</span><span class="sxs-lookup"><span data-stu-id="89ed3-406">MyTemplate incorporates all the settings that you configured in MyGPO.</span></span> <span data-ttu-id="89ed3-407">因為 MyOtherGPO 是使用 MyTemplate 建立的，所以第一次包含 MyGPO 在 MyTemplate 建立時所包含的所有設定。</span><span class="sxs-lookup"><span data-stu-id="89ed3-407">Because MyOtherGPO was created using MyTemplate, it at first contains all the settings that MyGPO contained at the time that MyTemplate was created.</span></span> <span data-ttu-id="89ed3-408">您可以產生差異報告來比較 MyOtherGPO 與 MyTemplate，以進行確認。</span><span class="sxs-lookup"><span data-stu-id="89ed3-408">You can confirm this by generating a difference report to compare MyOtherGPO to MyTemplate.</span></span>

**<span data-ttu-id="89ed3-409">從封存檢查 GPO 以進行編輯</span><span class="sxs-lookup"><span data-stu-id="89ed3-409">To check the GPO out from the archive for editing</span></span>**

1.  <span data-ttu-id="89ed3-410">在已安裝 AGPM 用戶端的電腦上，使用在 AGPM 中指派了 [編輯者角色] 的使用者帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="89ed3-410">On a computer on which you have installed AGPM Client, log on with a user account that is assigned the role of Editor in AGPM.</span></span>

2.  <span data-ttu-id="89ed3-411">以滑鼠右鍵按一下 [ **MyOtherGPO**]，然後按一下 **[取出]。**</span><span class="sxs-lookup"><span data-stu-id="89ed3-411">Right-click **MyOtherGPO**, and then click **Check Out**.</span></span>

3.  <span data-ttu-id="89ed3-412">輸入要在已取出之 GPO 之歷程記錄中顯示的批註，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="89ed3-412">Type a comment to be displayed in the history of the GPO while it is checked out, and then click **OK**.</span></span>

4.  <span data-ttu-id="89ed3-413">當 [ **AGPM 進度**] 視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-413">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="89ed3-414">在 [**受控**] 索引標籤上，GPO 的狀態會標示為 [**已取出**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-414">On the **Controlled** tab, the state of the GPO is identified as **Checked Out**.</span></span>

**<span data-ttu-id="89ed3-415">若要離線編輯 GPO 並設定帳戶鎖定時間</span><span class="sxs-lookup"><span data-stu-id="89ed3-415">To edit the GPO offline and configure the account lockout duration</span></span>**

1.  <span data-ttu-id="89ed3-416">在 [**受控**] 索引標籤上，以滑鼠右鍵按一下 [ **MyOtherGPO**]，然後按一下 [**編輯**] 以開啟 [**群組原則管理編輯器**] 視窗，並變更 GPO 的離線複本。</span><span class="sxs-lookup"><span data-stu-id="89ed3-416">On the **Controlled** tab, right-click **MyOtherGPO**, and then click **Edit** to open the **Group Policy Management Editor** window and change an offline copy of the GPO.</span></span> <span data-ttu-id="89ed3-417">在此案例中，請設定最小密碼長度：</span><span class="sxs-lookup"><span data-stu-id="89ed3-417">For this scenario, configure the minimum password length:</span></span>

    1.  <span data-ttu-id="89ed3-418">在 [**電腦**設定] 底下，按兩下 [**原則**]、[ **Windows 設定**]、[**安全性設定**]、[**帳戶原則**] 和 [**帳戶封鎖原則**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-418">Under **Computer Configuration**, double-click **Policies**, **Windows Settings**, **Security Settings**, **Account Policies**, and **Account Lockout Policy**.</span></span>

    2.  <span data-ttu-id="89ed3-419">在 [詳細資料] 窗格中，按兩下 [**帳戶鎖定時間**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-419">In the details pane, double-click **Account lockout duration**.</span></span>

    3.  <span data-ttu-id="89ed3-420">在 [屬性] 視窗中，核取 [**定義此原則設定**]，將 [持續時間] 設定為**30**分鐘，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="89ed3-420">In the properties window, check **Define this policy setting**, set the duration to **30** minutes, and then click **OK**.</span></span>

2.  <span data-ttu-id="89ed3-421">關閉 [**群組原則管理編輯器**] 視窗。</span><span class="sxs-lookup"><span data-stu-id="89ed3-421">Close the **Group Policy Management Editor** window.</span></span>

<span data-ttu-id="89ed3-422">將 MyOtherGPO 簽入封存並要求部署，就像您在[步驟2：編輯 GPO](#bkmk-manage2)中所做的一樣。</span><span class="sxs-lookup"><span data-stu-id="89ed3-422">Check MyOtherGPO into the archive and request deployment as you did for MyGPO in [Step 2: Edit a GPO](#bkmk-manage2).</span></span> <span data-ttu-id="89ed3-423">您可以使用 [差異] 報告，將 MyOtherGPO 與 MyGPO 或 MyTemplate 進行比較。</span><span class="sxs-lookup"><span data-stu-id="89ed3-423">You can compare MyOtherGPO to MyGPO or to MyTemplate by using difference reports.</span></span> <span data-ttu-id="89ed3-424">任何包含檢閱者角色的帳戶（AGPM 系統管理員 \ [完全控制 \]、審核者、編輯者或檢閱者）都可以產生報告。</span><span class="sxs-lookup"><span data-stu-id="89ed3-424">Any account that includes the Reviewer role (AGPM Administrator \[Full Control\], Approver, Editor, or Reviewer) can generate reports.</span></span>

**<span data-ttu-id="89ed3-425">比較 GPO 與另一個 GPO 及範本</span><span class="sxs-lookup"><span data-stu-id="89ed3-425">To compare a GPO to another GPO and to a template</span></span>**

1.  <span data-ttu-id="89ed3-426">若要比較 MyGPO 和 MyOtherGPO：</span><span class="sxs-lookup"><span data-stu-id="89ed3-426">To compare MyGPO and MyOtherGPO:</span></span>

    1.  <span data-ttu-id="89ed3-427">在 [**受控**] 索引標籤上，按一下 [ **MyGPO**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-427">On the **Controlled** tab, click **MyGPO**.</span></span> <span data-ttu-id="89ed3-428">按 CTRL 鍵，然後按一下 [ **MyOtherGPO**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-428">Press CTRL and then click **MyOtherGPO**.</span></span>

    2.  <span data-ttu-id="89ed3-429">以滑鼠右鍵按一下 [ **MyOtherGPO**]，指向 [**差異**]，然後按一下 [ **HTML 報表**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-429">Right-click **MyOtherGPO**, point to **Differences**, and then click **HTML Report**.</span></span>

2.  <span data-ttu-id="89ed3-430">若要比較 MyOtherGPO 和 MyTemplate：</span><span class="sxs-lookup"><span data-stu-id="89ed3-430">To compare MyOtherGPO and MyTemplate:</span></span>

    1.  <span data-ttu-id="89ed3-431">在 [**受控**] 索引標籤上，按一下 [ **MyOtherGPO**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-431">On the **Controlled** tab, click **MyOtherGPO**.</span></span>

    2.  <span data-ttu-id="89ed3-432">以滑鼠右鍵按一下 [ **MyOtherGPO**]，指向 [**差異**]，然後按一下 [**範本**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-432">Right-click **MyOtherGPO**, point to **Differences**, and then click **Template**.</span></span>

    3.  <span data-ttu-id="89ed3-433">選取 [ **MyTemplate**及**HTML 報表**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="89ed3-433">Select **MyTemplate** and **HTML Report**, and then click **OK**.</span></span>

### <a href="" id="bkmk-manage5"></a><span data-ttu-id="89ed3-434">步驟5：刪除及還原 GPO</span><span class="sxs-lookup"><span data-stu-id="89ed3-434">Step 5: Delete and restore a GPO</span></span>

<span data-ttu-id="89ed3-435">在此步驟中，您會擔任核准者來刪除 GPO。</span><span class="sxs-lookup"><span data-stu-id="89ed3-435">In this step, you act as an Approver to delete a GPO.</span></span>

**<span data-ttu-id="89ed3-436">刪除 GPO</span><span class="sxs-lookup"><span data-stu-id="89ed3-436">To delete a GPO</span></span>**

1.  <span data-ttu-id="89ed3-437">在已安裝 AGPM 用戶端的電腦上，以已指派核准者角色的使用者帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="89ed3-437">On a computer on which you have installed AGPM Client, log on with a user account that is assigned the role of Approver.</span></span>

2.  <span data-ttu-id="89ed3-438">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-438">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

3.  <span data-ttu-id="89ed3-439">在 [**內容**] 索引標籤上，按一下 [**受控**] 索引標籤以顯示受控制的 gpo。</span><span class="sxs-lookup"><span data-stu-id="89ed3-439">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

4.  <span data-ttu-id="89ed3-440">以滑鼠右鍵按一下 [ **MyGPO**]，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-440">Right-click **MyGPO**, and then click **Delete**.</span></span> <span data-ttu-id="89ed3-441">按一下 [**從封存及生產刪除 GPO** ]，即可刪除在生產環境中的 [封存] 和 [已部署的 gpo] 版本。</span><span class="sxs-lookup"><span data-stu-id="89ed3-441">Click **Delete GPO from archive and production** to delete both the version in the archive and the deployed version of the GPO in the production environment.</span></span>

5.  <span data-ttu-id="89ed3-442">輸入要顯示在 GPO 的審核追蹤中的批註，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="89ed3-442">Type a comment to be displayed in the audit trail for the GPO, and then click **OK**.</span></span>

6.  <span data-ttu-id="89ed3-443">當 [ **AGPM 進度**] 視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-443">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="89ed3-444">該 GPO 隨即會從 [**受控**] 索引標籤中移除，並顯示在 [**回收站**] 索引標籤上，可供您還原或銷毀。</span><span class="sxs-lookup"><span data-stu-id="89ed3-444">The GPO is removed from the **Controlled** tab and is displayed on the **Recycle Bin** tab, where it can be restored or destroyed.</span></span>

<span data-ttu-id="89ed3-445">有時候，您可能會在刪除仍需要的 GPO 之後進行探索。</span><span class="sxs-lookup"><span data-stu-id="89ed3-445">Occasionally you may discover after you delete a GPO that it is still needed.</span></span> <span data-ttu-id="89ed3-446">在此步驟中，您會擔任核准者來還原已刪除的 GPO。</span><span class="sxs-lookup"><span data-stu-id="89ed3-446">In this step, you act as an Approver to restore a GPO that was deleted.</span></span>

**<span data-ttu-id="89ed3-447">還原已刪除的 GPO</span><span class="sxs-lookup"><span data-stu-id="89ed3-447">To restore a deleted GPO</span></span>**

1.  <span data-ttu-id="89ed3-448">在 [**內容**] 索引標籤上，按一下 [**回收站**] 索引標籤以顯示已刪除的 gpo。</span><span class="sxs-lookup"><span data-stu-id="89ed3-448">On the **Contents** tab, click the **Recycle Bin** tab to display deleted GPOs.</span></span>

2.  <span data-ttu-id="89ed3-449">以滑鼠右鍵按一下 [ **MyGPO**]，然後按一下 [**還原**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-449">Right-click **MyGPO**, and then click **Restore**.</span></span>

3.  <span data-ttu-id="89ed3-450">輸入要顯示在 GPO 歷程記錄中的批註，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="89ed3-450">Type a comment to be displayed in the history of the GPO, and then click **OK**.</span></span>

4.  <span data-ttu-id="89ed3-451">當 [ **AGPM 進度**] 視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-451">When the **AGPM Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="89ed3-452">該 GPO 隨即會從 [**回收站**] 索引標籤中移除，並顯示在 [**受控**] 索引標籤上。</span><span class="sxs-lookup"><span data-stu-id="89ed3-452">The GPO is removed from the **Recycle Bin** tab and is displayed on the **Controlled** tab.</span></span>

    <span data-ttu-id="89ed3-453">**記事** 將 GPO 還原到封存後並不會自動將它重新部署到生產環境。</span><span class="sxs-lookup"><span data-stu-id="89ed3-453">**Note** Restoring a GPO to the archive does not automatically redeploy it to the production environment.</span></span> <span data-ttu-id="89ed3-454">若要將 GPO 傳回生產環境，請像在步驟3中一樣部署 GPO [：審查及部署 gpo](#bkmk-manage3)。</span><span class="sxs-lookup"><span data-stu-id="89ed3-454">To return the GPO to the production environment, deploy the GPO as in [Step 3: Review and deploy a GPO](#bkmk-manage3).</span></span>

     

<span data-ttu-id="89ed3-455">在編輯和部署 GPO 之後，您可能會發現對 GPO 所做的最近變更會造成問題。</span><span class="sxs-lookup"><span data-stu-id="89ed3-455">After editing and deploying a GPO, you may discover that recent changes to the GPO are causing a problem.</span></span> <span data-ttu-id="89ed3-456">在這個步驟中，您會擔任核准者來回滾到舊版的 GPO。</span><span class="sxs-lookup"><span data-stu-id="89ed3-456">In this step, you act as an Approver to roll back to an earlier version of the GPO.</span></span> <span data-ttu-id="89ed3-457">您可以返回 GPO 歷程記錄中的任何版本。</span><span class="sxs-lookup"><span data-stu-id="89ed3-457">You can roll back to any version in the history of the GPO.</span></span> <span data-ttu-id="89ed3-458">您可以使用 [批註] 和 [標籤] 來識別已知良好的版本，以及何時進行特定的變更。</span><span class="sxs-lookup"><span data-stu-id="89ed3-458">You can use comments and labels to identify known good versions and when specific changes were made.</span></span>

**<span data-ttu-id="89ed3-459">若要回滾至較舊版本的 GPO</span><span class="sxs-lookup"><span data-stu-id="89ed3-459">To roll back to an earlier version of a GPO</span></span>**

1.  <span data-ttu-id="89ed3-460">在 [**內容**] 索引標籤上，按一下 [**受控**] 索引標籤以顯示受控制的 gpo。</span><span class="sxs-lookup"><span data-stu-id="89ed3-460">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

2.  <span data-ttu-id="89ed3-461">按兩下 [ **MyGPO** ] 以顯示其歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="89ed3-461">Double-click **MyGPO** to display its history.</span></span>

3.  <span data-ttu-id="89ed3-462">以滑鼠右鍵按一下要部署的版本，按一下 [**部署**]，然後按一下 **[是]**。</span><span class="sxs-lookup"><span data-stu-id="89ed3-462">Right-click the version to be deployed, click **Deploy**, and then click **Yes**.</span></span>

4.  <span data-ttu-id="89ed3-463">當**進度**視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-463">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="89ed3-464">在 [歷程**記錄**] 視窗中，按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-464">In the **History** window, click **Close**.</span></span>

    <span data-ttu-id="89ed3-465">**記事** 若要確認重新部署的版本是否為所需版本，請檢查兩個版本的差異報告。</span><span class="sxs-lookup"><span data-stu-id="89ed3-465">**Note** To verify that the version that was redeployed is the version intended, examine a difference report for the two versions.</span></span> <span data-ttu-id="89ed3-466">在 GPO 的 [歷程**記錄**] 視窗中，選取兩個版本，以滑鼠右鍵按一下這些版本，指向 [**差異**]，然後按一下 [ **HTML 報表**] 或 [ **XML 報表**]。</span><span class="sxs-lookup"><span data-stu-id="89ed3-466">In the **History** window for the GPO, select the two versions, right-click them, point to **Difference**, and then click either **HTML Report** or **XML Report**.</span></span>

     

 

 





