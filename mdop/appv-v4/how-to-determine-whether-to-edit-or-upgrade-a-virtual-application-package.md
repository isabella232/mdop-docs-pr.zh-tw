---
title: 如何判斷是否要編輯或升級虛擬應用程式封裝
description: 如何判斷是否要編輯或升級虛擬應用程式封裝
author: dansimp
ms.assetid: 33dd5332-6802-46e0-9748-43fcc8f80aa3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b256a4927231613b6f2e688b5951adf57c9cb89a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801442"
---
# <span data-ttu-id="4fac4-103">如何判斷是否要編輯或升級虛擬應用程式封裝</span><span class="sxs-lookup"><span data-stu-id="4fac4-103">How to Determine Whether to Edit or Upgrade a Virtual Application Package</span></span>


<span data-ttu-id="4fac4-104">您可以使用下表來協助判斷虛擬應用程式套件是否可開啟以供編輯，不論您是否需要建立新版本的套件，或是使用 App-v 排序器，是否有任何一個可用的選項。</span><span class="sxs-lookup"><span data-stu-id="4fac4-104">Use the following table to help determine whether a virtual application package can be opened for edit, whether you need to create a new version of the package, or whether either option is available, using the App-V Sequencer.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4fac4-105">動作</span><span class="sxs-lookup"><span data-stu-id="4fac4-105">Action</span></span></th>
<th align="left"><span data-ttu-id="4fac4-106">開啟以進行編輯</span><span class="sxs-lookup"><span data-stu-id="4fac4-106">Open for edit</span></span></th>
<th align="left"><span data-ttu-id="4fac4-107">開啟以進行升級</span><span class="sxs-lookup"><span data-stu-id="4fac4-107">Open for upgrade</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4fac4-108">[查看套件屬性]。</span><span class="sxs-lookup"><span data-stu-id="4fac4-108">View package properties.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fac4-109">是</span><span class="sxs-lookup"><span data-stu-id="4fac4-109">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fac4-110">是</span><span class="sxs-lookup"><span data-stu-id="4fac4-110">Yes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4fac4-111">[查看套件變更歷程記錄]。</span><span class="sxs-lookup"><span data-stu-id="4fac4-111">View package change history.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fac4-112">是</span><span class="sxs-lookup"><span data-stu-id="4fac4-112">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fac4-113">是</span><span class="sxs-lookup"><span data-stu-id="4fac4-113">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4fac4-114">[查看關聯的套件檔案]。</span><span class="sxs-lookup"><span data-stu-id="4fac4-114">View associated package files.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fac4-115">是</span><span class="sxs-lookup"><span data-stu-id="4fac4-115">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fac4-116">是</span><span class="sxs-lookup"><span data-stu-id="4fac4-116">Yes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4fac4-117">編輯註冊表設定。</span><span class="sxs-lookup"><span data-stu-id="4fac4-117">Edit registry settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fac4-118">是</span><span class="sxs-lookup"><span data-stu-id="4fac4-118">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fac4-119">是</span><span class="sxs-lookup"><span data-stu-id="4fac4-119">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4fac4-120">查看其他套件設定（除了作業系統檔案屬性之外）。</span><span class="sxs-lookup"><span data-stu-id="4fac4-120">Review additional package settings (except operating system file properties).</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fac4-121">是</span><span class="sxs-lookup"><span data-stu-id="4fac4-121">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fac4-122">是</span><span class="sxs-lookup"><span data-stu-id="4fac4-122">Yes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4fac4-123">建立相關聯的 Windows Installer （MSI）。</span><span class="sxs-lookup"><span data-stu-id="4fac4-123">Create associated Windows Installer (MSI).</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fac4-124">是</span><span class="sxs-lookup"><span data-stu-id="4fac4-124">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fac4-125">是</span><span class="sxs-lookup"><span data-stu-id="4fac4-125">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4fac4-126">[修改 OSD 檔案]。</span><span class="sxs-lookup"><span data-stu-id="4fac4-126">Modify OSD file.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fac4-127">是</span><span class="sxs-lookup"><span data-stu-id="4fac4-127">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fac4-128">是</span><span class="sxs-lookup"><span data-stu-id="4fac4-128">Yes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4fac4-129">壓縮和解壓縮套件。</span><span class="sxs-lookup"><span data-stu-id="4fac4-129">Compress and uncompress package.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fac4-130">是</span><span class="sxs-lookup"><span data-stu-id="4fac4-130">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fac4-131">是</span><span class="sxs-lookup"><span data-stu-id="4fac4-131">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4fac4-132">新增檔案類型關聯。</span><span class="sxs-lookup"><span data-stu-id="4fac4-132">Add file type associations.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fac4-133">是</span><span class="sxs-lookup"><span data-stu-id="4fac4-133">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fac4-134">是</span><span class="sxs-lookup"><span data-stu-id="4fac4-134">Yes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4fac4-135">重新命名快速鍵。</span><span class="sxs-lookup"><span data-stu-id="4fac4-135">Rename shortcuts.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fac4-136">是</span><span class="sxs-lookup"><span data-stu-id="4fac4-136">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fac4-137">是</span><span class="sxs-lookup"><span data-stu-id="4fac4-137">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4fac4-138">設定虛擬化登錄機碼的狀態（覆寫/合併）。</span><span class="sxs-lookup"><span data-stu-id="4fac4-138">Set virtualized registry key state (override / merge).</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fac4-139">是</span><span class="sxs-lookup"><span data-stu-id="4fac4-139">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fac4-140">是</span><span class="sxs-lookup"><span data-stu-id="4fac4-140">Yes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4fac4-141">設定虛擬化資料夾的狀態。</span><span class="sxs-lookup"><span data-stu-id="4fac4-141">Set virtualized folder state.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fac4-142">是</span><span class="sxs-lookup"><span data-stu-id="4fac4-142">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fac4-143">是</span><span class="sxs-lookup"><span data-stu-id="4fac4-143">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4fac4-144">編輯虛擬檔案系統對應。</span><span class="sxs-lookup"><span data-stu-id="4fac4-144">Edit virtual file system mappings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fac4-145">是</span><span class="sxs-lookup"><span data-stu-id="4fac4-145">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fac4-146">是</span><span class="sxs-lookup"><span data-stu-id="4fac4-146">Yes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4fac4-147">查看套件的所有關聯作業系統檔案屬性。</span><span class="sxs-lookup"><span data-stu-id="4fac4-147">Review all associated operating system file properties for a package.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fac4-148">否</span><span class="sxs-lookup"><span data-stu-id="4fac4-148">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fac4-149">是</span><span class="sxs-lookup"><span data-stu-id="4fac4-149">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4fac4-150">新增其他服務。</span><span class="sxs-lookup"><span data-stu-id="4fac4-150">Add additional services.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fac4-151">否</span><span class="sxs-lookup"><span data-stu-id="4fac4-151">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fac4-152">是</span><span class="sxs-lookup"><span data-stu-id="4fac4-152">Yes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4fac4-153">新增其他檔案。</span><span class="sxs-lookup"><span data-stu-id="4fac4-153">Add additional files.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fac4-154">否</span><span class="sxs-lookup"><span data-stu-id="4fac4-154">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fac4-155">是</span><span class="sxs-lookup"><span data-stu-id="4fac4-155">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4fac4-156">收集及設定關聯的安全性描述項。</span><span class="sxs-lookup"><span data-stu-id="4fac4-156">Collect and configure associated security descriptors.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fac4-157">否</span><span class="sxs-lookup"><span data-stu-id="4fac4-157">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fac4-158">是</span><span class="sxs-lookup"><span data-stu-id="4fac4-158">Yes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4fac4-159">套用安全性更新或升級至新版本。</span><span class="sxs-lookup"><span data-stu-id="4fac4-159">Apply security updates or upgrade to a new version.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fac4-160">否</span><span class="sxs-lookup"><span data-stu-id="4fac4-160">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fac4-161">是</span><span class="sxs-lookup"><span data-stu-id="4fac4-161">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4fac4-162">新增其他應用程式。</span><span class="sxs-lookup"><span data-stu-id="4fac4-162">Add an additional application.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fac4-163">否</span><span class="sxs-lookup"><span data-stu-id="4fac4-163">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fac4-164">是</span><span class="sxs-lookup"><span data-stu-id="4fac4-164">Yes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4fac4-165">套用需要開啟應用程式的更新。</span><span class="sxs-lookup"><span data-stu-id="4fac4-165">Apply updates that require the application to open.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fac4-166">否</span><span class="sxs-lookup"><span data-stu-id="4fac4-166">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fac4-167">是</span><span class="sxs-lookup"><span data-stu-id="4fac4-167">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4fac4-168">套用需要重新開機電腦的更新。</span><span class="sxs-lookup"><span data-stu-id="4fac4-168">Apply updates that require the computer to restart.</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fac4-169">否</span><span class="sxs-lookup"><span data-stu-id="4fac4-169">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="4fac4-170">是</span><span class="sxs-lookup"><span data-stu-id="4fac4-170">Yes</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="4fac4-171">相關主題</span><span class="sxs-lookup"><span data-stu-id="4fac4-171">Related topics</span></span>


[<span data-ttu-id="4fac4-172">如何編輯現有的虛擬應用程式</span><span class="sxs-lookup"><span data-stu-id="4fac4-172">How to Edit an Existing Virtual Application</span></span>](how-to-edit-an-existing-virtual-application.md)

[<span data-ttu-id="4fac4-173">如何升級現有的虛擬應用程式</span><span class="sxs-lookup"><span data-stu-id="4fac4-173">How to Upgrade an Existing Virtual Application</span></span>](how-to-upgrade-an-existing-virtual-application.md)

 

 





