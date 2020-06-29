---
title: 應用程式的結果窗格欄
description: 應用程式的結果窗格欄
author: dansimp
ms.assetid: abae5ce2-40df-4f47-8062-f5eb6295c88c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c0138e40647a6a7d131a08aa03a9c9c1fcb071b3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802241"
---
# <span data-ttu-id="4e9bd-103">應用程式的結果窗格欄</span><span class="sxs-lookup"><span data-stu-id="4e9bd-103">Applications Results Pane Columns</span></span>


<span data-ttu-id="4e9bd-104">應用程式虛擬化用戶端管理主控台中 [**應用程式**] 節點的 [**結果**] 窗格可以顯示各種資料行。</span><span class="sxs-lookup"><span data-stu-id="4e9bd-104">The **Results** pane of the **Applications** node in the Application Virtualization Client Management Console can display a variety of columns.</span></span> <span data-ttu-id="4e9bd-105">預設會顯示 [**應用程式** **]、[執行]、[\*\*\*\*鎖定**] 和 [**封裝狀態**]。</span><span class="sxs-lookup"><span data-stu-id="4e9bd-105">**Application**, **Running**, **Locked**, and **Package Status** are shown by default.</span></span>

<span data-ttu-id="4e9bd-106">**記事** 您可以在 [**結果**] 窗格中按一下滑鼠右鍵，選取 [**視圖**]，然後選取 [**新增/移除欄**]，以新增或移除欄。</span><span class="sxs-lookup"><span data-stu-id="4e9bd-106">**Note** You can add or remove columns by right-clicking in the **Results** pane, selecting **View**, and then selecting **Add/Remove Columns**.</span></span>

 

<span data-ttu-id="4e9bd-107">清單可以依據任何資料行來排序。</span><span class="sxs-lookup"><span data-stu-id="4e9bd-107">The list can be sorted by any column.</span></span> <span data-ttu-id="4e9bd-108">包含日期和時間的欄會依時間順序排序，而不是字母。</span><span class="sxs-lookup"><span data-stu-id="4e9bd-108">Columns that contain dates and times are sorted in chronological order, not alphabetical.</span></span> <span data-ttu-id="4e9bd-109">對於包含日期與時間及文字混合的欄，日期和時間會被視為位於任何其他文字之前。</span><span class="sxs-lookup"><span data-stu-id="4e9bd-109">For columns that contain a mix of dates and times and text, dates and times are considered to come before any other text.</span></span>

<span data-ttu-id="4e9bd-110">下列欄可供使用。</span><span class="sxs-lookup"><span data-stu-id="4e9bd-110">The following columns are available.</span></span>

<a href="" id="application"></a>**<span data-ttu-id="4e9bd-111">應用程式</span><span class="sxs-lookup"><span data-stu-id="4e9bd-111">Application</span></span>**  
<span data-ttu-id="4e9bd-112">應用程式名稱與版本（以空格分隔）。</span><span class="sxs-lookup"><span data-stu-id="4e9bd-112">The application name and version, separated by a space.</span></span>

<a href="" id="application-in-use"></a>**<span data-ttu-id="4e9bd-113">使用中的應用程式</span><span class="sxs-lookup"><span data-stu-id="4e9bd-113">Application In Use</span></span>**  
<span data-ttu-id="4e9bd-114">根據任何使用者是否使用該應用程式（也就是執行或載入），顯示 **[是] 或 [** **否**]。</span><span class="sxs-lookup"><span data-stu-id="4e9bd-114">Displays **Yes** or **No** depending on whether any user is using the application (that is, running it or loading it).</span></span>

<a href="" id="app-virt-server"></a>**<span data-ttu-id="4e9bd-115">App Virt Server</span><span class="sxs-lookup"><span data-stu-id="4e9bd-115">App Virt Server</span></span>**  
<span data-ttu-id="4e9bd-116">從哪個應用程式虛擬化伺服器流入套件。</span><span class="sxs-lookup"><span data-stu-id="4e9bd-116">The Application Virtualization server from which the package was streamed.</span></span>

<a href="" id="cached-icon-file"></a>**<span data-ttu-id="4e9bd-117">已緩存的圖示檔</span><span class="sxs-lookup"><span data-stu-id="4e9bd-117">Cached Icon File</span></span>**  
<span data-ttu-id="4e9bd-118">[快取] 中圖示檔案的名稱（目前實現中的 GUID）。</span><span class="sxs-lookup"><span data-stu-id="4e9bd-118">The name of the icon files in cache (a GUID in the current implementation).</span></span>

<a href="" id="cached-icon-path"></a>**<span data-ttu-id="4e9bd-119">已緩存的圖示路徑</span><span class="sxs-lookup"><span data-stu-id="4e9bd-119">Cached Icon Path</span></span>**  
<span data-ttu-id="4e9bd-120">快取中圖示檔案的完整路徑。</span><span class="sxs-lookup"><span data-stu-id="4e9bd-120">The full path to the icon files in cache.</span></span>

<a href="" id="cached-launch-percent"></a>**<span data-ttu-id="4e9bd-121">緩衝啟動百分比</span><span class="sxs-lookup"><span data-stu-id="4e9bd-121">Cached Launch Percent</span></span>**  
<span data-ttu-id="4e9bd-122">應用程式的啟動資料在快取中的百分比。</span><span class="sxs-lookup"><span data-stu-id="4e9bd-122">The percentage of the application’s launch data currently in cache.</span></span>

<a href="" id="cached-launch-size--mb-"></a>**<span data-ttu-id="4e9bd-123">緩衝啟動大小（MB）</span><span class="sxs-lookup"><span data-stu-id="4e9bd-123">Cached Launch Size (MB)</span></span>**  
<span data-ttu-id="4e9bd-124">應用程式在快取中目前的啟動資料量。</span><span class="sxs-lookup"><span data-stu-id="4e9bd-124">The amount of the application’s launch data currently in cache.</span></span>

<a href="" id="cached-osd-file"></a>**<span data-ttu-id="4e9bd-125">已緩存的 OSD 檔案</span><span class="sxs-lookup"><span data-stu-id="4e9bd-125">Cached OSD File</span></span>**  
<span data-ttu-id="4e9bd-126">快取中的 OSD 檔案名稱（這是目前實現中的 GUID）。</span><span class="sxs-lookup"><span data-stu-id="4e9bd-126">The name of the OSD file in the cache (which is a GUID in the current implementation).</span></span>

<a href="" id="cached-osd-path"></a>**<span data-ttu-id="4e9bd-127">快取的 OSD 路徑</span><span class="sxs-lookup"><span data-stu-id="4e9bd-127">Cached OSD Path</span></span>**  
<span data-ttu-id="4e9bd-128">快取中 OSD 檔案的完整路徑。</span><span class="sxs-lookup"><span data-stu-id="4e9bd-128">The full path to the OSD file in the cache.</span></span>

<a href="" id="cached-package-percent"></a>**<span data-ttu-id="4e9bd-129">緩衝套件百分比</span><span class="sxs-lookup"><span data-stu-id="4e9bd-129">Cached Package Percent</span></span>**  
<span data-ttu-id="4e9bd-130">目前在快取中之套件的百分比。</span><span class="sxs-lookup"><span data-stu-id="4e9bd-130">The percentage of the package currently in cache.</span></span>

<a href="" id="cached-package-size--mb-"></a>**<span data-ttu-id="4e9bd-131">緩衝套件大小（MB）</span><span class="sxs-lookup"><span data-stu-id="4e9bd-131">Cached Package Size (MB)</span></span>**  
<span data-ttu-id="4e9bd-132">目前在快取中的套件部分大小。</span><span class="sxs-lookup"><span data-stu-id="4e9bd-132">The size of the portion of the package currently in cache.</span></span>

<a href="" id="icon-file"></a>**<span data-ttu-id="4e9bd-133">圖示檔</span><span class="sxs-lookup"><span data-stu-id="4e9bd-133">Icon File</span></span>**  
<span data-ttu-id="4e9bd-134">圖示檔案的原始名稱。</span><span class="sxs-lookup"><span data-stu-id="4e9bd-134">The original name of the icon file.</span></span>

<a href="" id="icon-path"></a>**<span data-ttu-id="4e9bd-135">圖示路徑</span><span class="sxs-lookup"><span data-stu-id="4e9bd-135">Icon Path</span></span>**  
<span data-ttu-id="4e9bd-136">圖示檔案的原始路徑或 URL。</span><span class="sxs-lookup"><span data-stu-id="4e9bd-136">The original path or URL for the icon file.</span></span>

<a href="" id="last-system-launch"></a>**<span data-ttu-id="4e9bd-137">上次系統啟動</span><span class="sxs-lookup"><span data-stu-id="4e9bd-137">Last System Launch</span></span>**  
<span data-ttu-id="4e9bd-138">上次由系統啟動應用程式的時間。</span><span class="sxs-lookup"><span data-stu-id="4e9bd-138">The last time the application was launched by the system.</span></span>

<a href="" id="last-user-launch"></a>**<span data-ttu-id="4e9bd-139">上次使用者啟動</span><span class="sxs-lookup"><span data-stu-id="4e9bd-139">Last User Launch</span></span>**  
<span data-ttu-id="4e9bd-140">使用者最後一次啟動應用程式的時間。</span><span class="sxs-lookup"><span data-stu-id="4e9bd-140">The last time the application was launched by the user.</span></span>

<a href="" id="launch-size--mb-"></a>**<span data-ttu-id="4e9bd-141">啟動大小（MB）</span><span class="sxs-lookup"><span data-stu-id="4e9bd-141">Launch Size (MB)</span></span>**  
<span data-ttu-id="4e9bd-142">啟動應用程式所需之套件資料的未壓縮大小。</span><span class="sxs-lookup"><span data-stu-id="4e9bd-142">The uncompressed size of the package data needed to launch the application.</span></span>

<a href="" id="locked"></a>**<span data-ttu-id="4e9bd-143">已鎖定</span><span class="sxs-lookup"><span data-stu-id="4e9bd-143">Locked</span></span>**  
<span data-ttu-id="4e9bd-144">顯示 [**是] 或 [** **否**]，視應用程式的套件是否已在快取中鎖定而定。</span><span class="sxs-lookup"><span data-stu-id="4e9bd-144">Displays **Yes** or **No** depending on whether the application’s package is locked in the cache.</span></span>

<a href="" id="name"></a>**<span data-ttu-id="4e9bd-145">名稱</span><span class="sxs-lookup"><span data-stu-id="4e9bd-145">Name</span></span>**  
<span data-ttu-id="4e9bd-146">應用程式名稱。</span><span class="sxs-lookup"><span data-stu-id="4e9bd-146">The application name.</span></span>

<a href="" id="osd-file"></a>**<span data-ttu-id="4e9bd-147">OSD 檔案</span><span class="sxs-lookup"><span data-stu-id="4e9bd-147">OSD File</span></span>**  
<span data-ttu-id="4e9bd-148">已開啟軟體描述項（OSD）檔案的原始名稱。</span><span class="sxs-lookup"><span data-stu-id="4e9bd-148">The original name of the Open Software Descriptor (OSD) file.</span></span>

<a href="" id="osd-path"></a>**<span data-ttu-id="4e9bd-149">OSD 路徑</span><span class="sxs-lookup"><span data-stu-id="4e9bd-149">OSD Path</span></span>**  
<span data-ttu-id="4e9bd-150">OSD 檔案的完整原始路徑或 URL。</span><span class="sxs-lookup"><span data-stu-id="4e9bd-150">The full original path or URL to the OSD file.</span></span>

<a href="" id="package-name"></a>**<span data-ttu-id="4e9bd-151">套件名稱</span><span class="sxs-lookup"><span data-stu-id="4e9bd-151">Package Name</span></span>**  
<span data-ttu-id="4e9bd-152">套件的名稱。</span><span class="sxs-lookup"><span data-stu-id="4e9bd-152">The name of the package.</span></span>

<a href="" id="package-guid"></a>**<span data-ttu-id="4e9bd-153">封裝 GUID</span><span class="sxs-lookup"><span data-stu-id="4e9bd-153">Package GUID</span></span>**  
<span data-ttu-id="4e9bd-154">套件的 GUID。</span><span class="sxs-lookup"><span data-stu-id="4e9bd-154">The GUID for the package.</span></span>

<a href="" id="package-size--mb-"></a>**<span data-ttu-id="4e9bd-155">套件大小（MB）</span><span class="sxs-lookup"><span data-stu-id="4e9bd-155">Package Size (MB)</span></span>**  
<span data-ttu-id="4e9bd-156">套件中未壓縮資料的總大小。</span><span class="sxs-lookup"><span data-stu-id="4e9bd-156">The total size of the uncompressed data in the package.</span></span>

<a href="" id="package-status"></a>**<span data-ttu-id="4e9bd-157">封裝狀態</span><span class="sxs-lookup"><span data-stu-id="4e9bd-157">Package Status</span></span>**  
<span data-ttu-id="4e9bd-158">套件的目前操作狀態。</span><span class="sxs-lookup"><span data-stu-id="4e9bd-158">The current operational status of the package.</span></span>

<a href="" id="package-url"></a>**<span data-ttu-id="4e9bd-159">封裝 URL</span><span class="sxs-lookup"><span data-stu-id="4e9bd-159">Package URL</span></span>**  
<span data-ttu-id="4e9bd-160">套件的 URL。</span><span class="sxs-lookup"><span data-stu-id="4e9bd-160">The URL for the package.</span></span>

<a href="" id="package-version"></a>**<span data-ttu-id="4e9bd-161">套件版本</span><span class="sxs-lookup"><span data-stu-id="4e9bd-161">Package Version</span></span>**  
<span data-ttu-id="4e9bd-162">套件的版本。</span><span class="sxs-lookup"><span data-stu-id="4e9bd-162">The version for the package.</span></span>

<a href="" id="package-version-guid"></a>**<span data-ttu-id="4e9bd-163">套件版本 GUID</span><span class="sxs-lookup"><span data-stu-id="4e9bd-163">Package Version GUID</span></span>**  
<span data-ttu-id="4e9bd-164">套件版本的 GUID。</span><span class="sxs-lookup"><span data-stu-id="4e9bd-164">The GUID for the package version.</span></span>

<a href="" id="running"></a>**<span data-ttu-id="4e9bd-165">Running</span><span class="sxs-lookup"><span data-stu-id="4e9bd-165">Running</span></span>**  
<span data-ttu-id="4e9bd-166">根據目前的使用者是否正在執行應用程式，顯示 **[是] 或 [** **否**]。</span><span class="sxs-lookup"><span data-stu-id="4e9bd-166">Displays **Yes** or **No** depending on whether the current user is running the application.</span></span>

<a href="" id="source"></a>**<span data-ttu-id="4e9bd-167">Source</span><span class="sxs-lookup"><span data-stu-id="4e9bd-167">Source</span></span>**  
<span data-ttu-id="4e9bd-168">應用程式的來源：應用程式發佈伺服器的名稱，或是直接從 OSD 檔案新增的應用程式的「本機」。</span><span class="sxs-lookup"><span data-stu-id="4e9bd-168">Where the application came from—either the name of an application publishing server or "Local" for applications added from OSD files directly.</span></span>

<a href="" id="version"></a>**<span data-ttu-id="4e9bd-169">版本</span><span class="sxs-lookup"><span data-stu-id="4e9bd-169">Version</span></span>**  
<span data-ttu-id="4e9bd-170">應用程式版本。</span><span class="sxs-lookup"><span data-stu-id="4e9bd-170">The application version.</span></span>

## <span data-ttu-id="4e9bd-171">相關主題</span><span class="sxs-lookup"><span data-stu-id="4e9bd-171">Related topics</span></span>


[<span data-ttu-id="4e9bd-172">應用程式節點</span><span class="sxs-lookup"><span data-stu-id="4e9bd-172">Applications Node</span></span>](applications-node.md)

[<span data-ttu-id="4e9bd-173">應用程式的結果窗格</span><span class="sxs-lookup"><span data-stu-id="4e9bd-173">Applications Results Pane</span></span>](applications-results-pane.md)

[<span data-ttu-id="4e9bd-174">Application Virtualization Client 管理主控台參考資料</span><span class="sxs-lookup"><span data-stu-id="4e9bd-174">Application Virtualization Client Management Console Reference</span></span>](application-virtualization-client-management-console-reference.md)

 

 





