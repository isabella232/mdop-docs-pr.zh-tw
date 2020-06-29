---
title: 應用程式授權結果窗格
description: 應用程式授權結果窗格
author: dansimp
ms.assetid: 8b519715-b2fe-451e-ad9b-e9b73f454961
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9e5a86c22e67e061ec873317c455958536fae75b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802245"
---
# <span data-ttu-id="e8827-103">應用程式授權結果窗格</span><span class="sxs-lookup"><span data-stu-id="e8827-103">Applications Licenses Results Pane</span></span>


<span data-ttu-id="e8827-104">應用程式虛擬化伺服器管理主控台中的 [**應用程式授權結果**] 窗格會顯示可用的應用程式授權群組和應用程式授權清單。</span><span class="sxs-lookup"><span data-stu-id="e8827-104">The **Applications Licenses Results** pane in the Application Virtualization Server Management Console displays a list of the available application license groups and application licenses.</span></span>

<span data-ttu-id="e8827-105">以滑鼠右鍵按一下任何應用程式授權群組，以顯示包含下列元素的快顯功能表。</span><span class="sxs-lookup"><span data-stu-id="e8827-105">Right-click any application license group to display a pop-up menu that contains the following elements.</span></span>

<a href="" id="new-unlimited-license"></a>**<span data-ttu-id="e8827-106">新的無限制授權</span><span class="sxs-lookup"><span data-stu-id="e8827-106">New Unlimited License</span></span>**  
<span data-ttu-id="e8827-107">顯示 [新增無限制授權] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="e8827-107">Displays the New Unlimited License Wizard.</span></span> <span data-ttu-id="e8827-108">只有在授權群組沒有授權時，才能使用此選項。</span><span class="sxs-lookup"><span data-stu-id="e8827-108">This option is available only when the license group has no licenses.</span></span> <span data-ttu-id="e8827-109">此嚮導包含三個頁面：</span><span class="sxs-lookup"><span data-stu-id="e8827-109">This wizard consists of three pages:</span></span>

1.  <span data-ttu-id="e8827-110">在 [**應用程式授權] 群組**的 [名稱] 欄位中輸入群組名稱，在 [**授權到期警告**] 欄位中輸入一個值（以分鐘為單位）。</span><span class="sxs-lookup"><span data-stu-id="e8827-110">Enter a group name in the **Applications License Group Name** field and a value (in minutes) in the **License Expiration Warning** field.</span></span> <span data-ttu-id="e8827-111">（您可以輸入從0到100的任何值）。您也可以使用向上鍵和向下鍵來選取分鐘數。</span><span class="sxs-lookup"><span data-stu-id="e8827-111">(You can enter any value from 0–100.) You can also use the up and down arrows to select the number of minutes.</span></span>

2.  <span data-ttu-id="e8827-112">在 [**授權描述**] 欄位中輸入簡短的描述文字，然後選取 [**啟用**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="e8827-112">Enter brief descriptive text in the **License Description** field, and select the **Enabled** check box.</span></span> <span data-ttu-id="e8827-113">您也可以使用 [**到期日**] 欄位來指定授權的到期日。</span><span class="sxs-lookup"><span data-stu-id="e8827-113">Optionally, you can use the **Expiration Date** field to specify an expiration date for the license.</span></span> <span data-ttu-id="e8827-114">您可以選取 [預設值] 核取方塊，或使用 [行事曆] 實用程式流覽至想要的到期日。</span><span class="sxs-lookup"><span data-stu-id="e8827-114">You can select the default check box or use the calendar utility to browse to the desired expiration date.</span></span>

3.  <span data-ttu-id="e8827-115">按一下 **[完成]** 以新增新的授權。</span><span class="sxs-lookup"><span data-stu-id="e8827-115">Click **Finish** to add the new license.</span></span>

<a href="" id="new-concurrent-license"></a>**<span data-ttu-id="e8827-116">新的並行授權</span><span class="sxs-lookup"><span data-stu-id="e8827-116">New Concurrent License</span></span>**  
<span data-ttu-id="e8827-117">顯示 [新增併發授權] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="e8827-117">Displays the New Concurrent License Wizard.</span></span> <span data-ttu-id="e8827-118">只有在授權群組沒有無限制的授權時，才能使用此選項。</span><span class="sxs-lookup"><span data-stu-id="e8827-118">This option is available only when the license group has no unlimited licenses.</span></span> <span data-ttu-id="e8827-119">此嚮導包含下列頁面，與新的 [無限制授權] 嚮導幾乎完全相同：</span><span class="sxs-lookup"><span data-stu-id="e8827-119">This wizard consists of the following pages and is almost identical to the New Unlimited License Wizard:</span></span>

1.  <span data-ttu-id="e8827-120">在 [**應用程式授權] 群組**的 [名稱] 欄位中輸入群組名稱，在 [**授權到期警告**] 欄位中輸入一個值（以分鐘為單位）。</span><span class="sxs-lookup"><span data-stu-id="e8827-120">Enter a group name in the **Applications License Group Name** field and a value (in minutes) in the **License Expiration Warning** field.</span></span> <span data-ttu-id="e8827-121">（您可以輸入從0到100的任何值）。您也可以使用向上鍵和向下鍵來選取分鐘數。</span><span class="sxs-lookup"><span data-stu-id="e8827-121">(You can enter any value from 0–100.) You can also use the up and down arrows to select the number of minutes.</span></span>

2.  <span data-ttu-id="e8827-122">在 [**授權描述**] 欄位中輸入簡短的描述文字，然後在 [**併發授權數量**] 欄位中輸入值。</span><span class="sxs-lookup"><span data-stu-id="e8827-122">Enter brief descriptive text in the **License Description** field, and enter a value in the **Concurrent License Quantity** field.</span></span> <span data-ttu-id="e8827-123">您也可以使用向上鍵和向下鍵來指定併發授權的數量。</span><span class="sxs-lookup"><span data-stu-id="e8827-123">You can also use the up and down arrows to specify the number of concurrent licenses.</span></span> <span data-ttu-id="e8827-124">選取 [**已啟用**] 核取方塊以啟用授權。</span><span class="sxs-lookup"><span data-stu-id="e8827-124">Select the **Enabled** check box to enable the license.</span></span> <span data-ttu-id="e8827-125">您也可以使用 [**到期日**] 欄位來選取授權的到期日。</span><span class="sxs-lookup"><span data-stu-id="e8827-125">Optionally, you can use the **Expiration Date** field to select an expiration date for the license.</span></span> <span data-ttu-id="e8827-126">您可以選取核取方塊以使用顯示的到期日，或者您可以使用 [行事曆] 實用程式流覽至想要的到期日。</span><span class="sxs-lookup"><span data-stu-id="e8827-126">You can select the check box to use the displayed expiration date, or you can use the calendar utility to browse to the desired expiration date.</span></span>

3.  <span data-ttu-id="e8827-127">按一下 **[完成]** 以新增新的授權。</span><span class="sxs-lookup"><span data-stu-id="e8827-127">Click **Finish** to add the new licenses.</span></span>

<a href="" id="new-named-license"></a>**<span data-ttu-id="e8827-128">新的命名授權</span><span class="sxs-lookup"><span data-stu-id="e8827-128">New Named License</span></span>**  
<span data-ttu-id="e8827-129">顯示新的 [命名授權] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="e8827-129">Displays the New Named License Wizard.</span></span> <span data-ttu-id="e8827-130">只有在授權群組沒有無限制的授權時，才能使用此選項。</span><span class="sxs-lookup"><span data-stu-id="e8827-130">This option is available only when the license group has no unlimited licenses.</span></span> <span data-ttu-id="e8827-131">此嚮導包含下列頁面：</span><span class="sxs-lookup"><span data-stu-id="e8827-131">This wizard consists of the following pages:</span></span>

1.  <span data-ttu-id="e8827-132">在 [**應用程式授權] 群組**的 [名稱] 欄位中輸入群組名稱，在 [**授權到期警告**] 欄位中輸入一個值（以分鐘為單位）。</span><span class="sxs-lookup"><span data-stu-id="e8827-132">Enter a group name in the **Applications License Group Name** field and a value (in minutes) in the **License Expiration Warning** field.</span></span> <span data-ttu-id="e8827-133">（您可以輸入從0到100的任何值）。您也可以使用向上鍵和向下鍵來選取分鐘數。</span><span class="sxs-lookup"><span data-stu-id="e8827-133">(You can enter any value from 0–100.) You can also use the up and down arrows to select the number of minutes.</span></span>

2.  <span data-ttu-id="e8827-134">在**授權描述**中輸入簡短的描述文字，然後選取 [**啟用**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="e8827-134">Enter brief descriptive text in the **License Description**, and select the **Enabled** check box.</span></span> <span data-ttu-id="e8827-135">您也可以使用 [**到期日**] 欄位來指定授權的到期日。</span><span class="sxs-lookup"><span data-stu-id="e8827-135">Optionally, you can use the **Expiration Date** field to specify an expiration date for the license.</span></span> <span data-ttu-id="e8827-136">您可以選取核取方塊以使用顯示的到期日，或使用行事曆實用程式流覽至想要的到期日。</span><span class="sxs-lookup"><span data-stu-id="e8827-136">You can select the check box to use the displayed expiration date, or use the calendar utility to browse to the desired expiration date.</span></span>

3.  <span data-ttu-id="e8827-137">按一下 [**新增**]、[**編輯**] 或 [**移除**已命名的使用者]。</span><span class="sxs-lookup"><span data-stu-id="e8827-137">Click **Add**, **Edit**, or **Remove** named users.</span></span>

4.  <span data-ttu-id="e8827-138">按一下 **[完成]** 以新增新的授權。</span><span class="sxs-lookup"><span data-stu-id="e8827-138">Click **Finish** to add the new license.</span></span>

<a href="" id="new-window-from-here"></a>**<span data-ttu-id="e8827-139">從這裡新增視窗</span><span class="sxs-lookup"><span data-stu-id="e8827-139">New Window from Here</span></span>**  
<span data-ttu-id="e8827-140">開啟新的管理主控台，並將選取的節點做為根節點。</span><span class="sxs-lookup"><span data-stu-id="e8827-140">Opens a new management console with the selected node as the root node.</span></span>

<a href="" id="delete"></a>**<span data-ttu-id="e8827-141">刪除</span><span class="sxs-lookup"><span data-stu-id="e8827-141">Delete</span></span>**  
<span data-ttu-id="e8827-142">從清單中刪除 [授權] 群組。</span><span class="sxs-lookup"><span data-stu-id="e8827-142">Deletes the license group from the list.</span></span>

<a href="" id="rename"></a>**<span data-ttu-id="e8827-143">重新命名</span><span class="sxs-lookup"><span data-stu-id="e8827-143">Rename</span></span>**  
<span data-ttu-id="e8827-144">變更應用程式授權群組的名稱。</span><span class="sxs-lookup"><span data-stu-id="e8827-144">Changes the name of the applications license group.</span></span>

<a href="" id="properties"></a>**<span data-ttu-id="e8827-145">屬性</span><span class="sxs-lookup"><span data-stu-id="e8827-145">Properties</span></span>**  
<span data-ttu-id="e8827-146">顯示所選應用程式授權群組的 [**屬性**] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="e8827-146">Displays the **Properties** dialog box for the selected application license groups.</span></span> <span data-ttu-id="e8827-147">此對話方塊具有下列索引標籤：</span><span class="sxs-lookup"><span data-stu-id="e8827-147">This dialog box has the following tabs:</span></span>

-   <span data-ttu-id="e8827-148">**[一般**] 索引標籤-顯示授權群組的一般資訊。</span><span class="sxs-lookup"><span data-stu-id="e8827-148">**General** tab—Displays general information about the license group.</span></span> <span data-ttu-id="e8827-149">在此索引標籤上，您可以變更 [**授權到期警告**] 欄位中的時間值（以分鐘為單位）。</span><span class="sxs-lookup"><span data-stu-id="e8827-149">From this tab, you can change the time value (in minutes) in the **License Expiration Warning** field.</span></span> <span data-ttu-id="e8827-150">您可以輸入0到100之間的任何值。</span><span class="sxs-lookup"><span data-stu-id="e8827-150">You can enter any value from 0–100.</span></span>

-   <span data-ttu-id="e8827-151">[**應用程式**] 索引標籤-顯示與授權群組相關聯的應用程式清單。</span><span class="sxs-lookup"><span data-stu-id="e8827-151">**Applications** tab—Displays the list of applications associated with the license group.</span></span>

<a href="" id="help"></a>**<span data-ttu-id="e8827-152">說明</span><span class="sxs-lookup"><span data-stu-id="e8827-152">Help</span></span>**  
<span data-ttu-id="e8827-153">顯示應用程式虛擬化伺服器管理主控台說明系統。</span><span class="sxs-lookup"><span data-stu-id="e8827-153">Displays the Application Virtualization Server Management Console help system.</span></span>

<span data-ttu-id="e8827-154">當 [**結果**] 窗格顯示應用程式授權群組時，請以滑鼠右鍵按一下 [**結果**] 窗格中的任何位置（除了授權群組之外），以顯示包含下列元素的快顯功能表。</span><span class="sxs-lookup"><span data-stu-id="e8827-154">When the **Results** pane displays application license groups, right-click anywhere in the **Results** pane, except on a license group, to display a pop-up menu that contains the following elements.</span></span>

<a href="" id="refresh"></a>**<span data-ttu-id="e8827-155">重新整理</span><span class="sxs-lookup"><span data-stu-id="e8827-155">Refresh</span></span>**  
<span data-ttu-id="e8827-156">刷新伺服器的視圖。</span><span class="sxs-lookup"><span data-stu-id="e8827-156">Refreshes the view of the server.</span></span>

<a href="" id="export-list"></a>**<span data-ttu-id="e8827-157">匯出清單</span><span class="sxs-lookup"><span data-stu-id="e8827-157">Export List</span></span>**  
<span data-ttu-id="e8827-158">建立包含 [**結果**] 窗格內容的定位字元分隔文字檔。</span><span class="sxs-lookup"><span data-stu-id="e8827-158">Creates a tab-delimited text file that contains the contents of the **Results** pane.</span></span> <span data-ttu-id="e8827-159">此專案會顯示 [標準檔案**儲存**] 對話方塊，您可以在此指定您要建立之文字檔的位置。</span><span class="sxs-lookup"><span data-stu-id="e8827-159">This item displays a standard **File Save** dialog box where you specify the location for the text file you are creating.</span></span>

<a href="" id="view"></a>**<span data-ttu-id="e8827-160">View</span><span class="sxs-lookup"><span data-stu-id="e8827-160">View</span></span>**  
<span data-ttu-id="e8827-161">變更 [**結果**] 窗格的外觀和內容。</span><span class="sxs-lookup"><span data-stu-id="e8827-161">Changes the appearance and content of the **Results** pane.</span></span>

<a href="" id="arrange-line-up-icons"></a>**<span data-ttu-id="e8827-162">[排布]/[對齊] 圖示</span><span class="sxs-lookup"><span data-stu-id="e8827-162">Arrange/Line Up Icons</span></span>**  
<span data-ttu-id="e8827-163">變更 [**結果**] 窗格中圖示的顯示方式。</span><span class="sxs-lookup"><span data-stu-id="e8827-163">Changes how the icons are displayed in the **Results** pane.</span></span>

<a href="" id="help"></a>**<span data-ttu-id="e8827-164">說明</span><span class="sxs-lookup"><span data-stu-id="e8827-164">Help</span></span>**  
<span data-ttu-id="e8827-165">顯示應用程式虛擬化伺服器管理主控台的說明系統。</span><span class="sxs-lookup"><span data-stu-id="e8827-165">Displays the help system for the Application Virtualization Server Management Console.</span></span>

<span data-ttu-id="e8827-166">當 [**結果**] 窗格顯示授權時，以滑鼠右鍵按一下任何應用程式授權，即可顯示包含下列元素的快顯功能表。</span><span class="sxs-lookup"><span data-stu-id="e8827-166">When the **Results** pane displays licenses, right-click any application license to display a pop-up menu that contains the following elements.</span></span>

<a href="" id="delete"></a>**<span data-ttu-id="e8827-167">刪除</span><span class="sxs-lookup"><span data-stu-id="e8827-167">Delete</span></span>**  
<span data-ttu-id="e8827-168">從清單中刪除授權。</span><span class="sxs-lookup"><span data-stu-id="e8827-168">Deletes the license from the list.</span></span>

<a href="" id="rename"></a>**<span data-ttu-id="e8827-169">重新命名</span><span class="sxs-lookup"><span data-stu-id="e8827-169">Rename</span></span>**  
<span data-ttu-id="e8827-170">變更授權的名稱。</span><span class="sxs-lookup"><span data-stu-id="e8827-170">Changes the name of the license.</span></span>

<a href="" id="properties"></a>**<span data-ttu-id="e8827-171">屬性</span><span class="sxs-lookup"><span data-stu-id="e8827-171">Properties</span></span>**  
<span data-ttu-id="e8827-172">顯示所選應用程式授權的 [**屬性**] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="e8827-172">Displays the **Properties** dialog box for the selected application license.</span></span>

<span data-ttu-id="e8827-173">[**屬性**] 對話方塊的 [**一般**] 索引標籤會顯示授權的相關資訊，並可讓您變更啟用狀態、授權到期日及授權金鑰資訊。</span><span class="sxs-lookup"><span data-stu-id="e8827-173">The **General** tab of the **Properties** dialog box displays information about the license and lets you change the enabled status, license expiration date, and license key information.</span></span>

<a href="" id="help"></a>**<span data-ttu-id="e8827-174">說明</span><span class="sxs-lookup"><span data-stu-id="e8827-174">Help</span></span>**  
<span data-ttu-id="e8827-175">顯示伺服器管理主控台說明系統。</span><span class="sxs-lookup"><span data-stu-id="e8827-175">Displays the server management console help system.</span></span>

<span data-ttu-id="e8827-176">當 [**結果**] 窗格顯示授權時，請以滑鼠右鍵按一下 [**結果**] 窗格中的任何位置（除了授權之外），以顯示包含下列元素的快顯功能表。</span><span class="sxs-lookup"><span data-stu-id="e8827-176">When the **Results** pane displays licenses, right-click anywhere in the **Results** pane, except on a license, to display a pop-up menu that contains the following elements.</span></span>

<a href="" id="export-list"></a>**<span data-ttu-id="e8827-177">匯出清單</span><span class="sxs-lookup"><span data-stu-id="e8827-177">Export List</span></span>**  
<span data-ttu-id="e8827-178">建立包含 [**結果**] 窗格內容的定位字元分隔文字檔。</span><span class="sxs-lookup"><span data-stu-id="e8827-178">Creates a tab-delimited text file that contains the contents of the **Results** pane.</span></span> <span data-ttu-id="e8827-179">此專案會顯示 [標準檔案**儲存**] 對話方塊，您可以在此指定您要建立之文字檔的位置。</span><span class="sxs-lookup"><span data-stu-id="e8827-179">This item displays a standard **File Save** dialog box where you specify the location for the text file you are creating.</span></span>

<a href="" id="view"></a>**<span data-ttu-id="e8827-180">View</span><span class="sxs-lookup"><span data-stu-id="e8827-180">View</span></span>**  
<span data-ttu-id="e8827-181">變更 [**結果**] 窗格的外觀和內容。</span><span class="sxs-lookup"><span data-stu-id="e8827-181">Changes the appearance and content of the **Results** pane.</span></span>

<a href="" id="arrange-line-up-icons"></a>**<span data-ttu-id="e8827-182">[排布]/[對齊] 圖示</span><span class="sxs-lookup"><span data-stu-id="e8827-182">Arrange/Line Up Icons</span></span>**  
<span data-ttu-id="e8827-183">變更 [**結果**] 窗格中圖示的顯示方式。</span><span class="sxs-lookup"><span data-stu-id="e8827-183">Changes how the icons are displayed in the **Results** pane.</span></span>

<a href="" id="properties"></a>**<span data-ttu-id="e8827-184">屬性</span><span class="sxs-lookup"><span data-stu-id="e8827-184">Properties</span></span>**  
<span data-ttu-id="e8827-185">顯示所選授權的 [**屬性**] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="e8827-185">Displays the **Properties** dialog box for the selected license.</span></span>

<span data-ttu-id="e8827-186">[**屬性**] 對話方塊的 [**一般**] 索引標籤會顯示授權的相關資訊，並可讓您變更啟用狀態、授權到期日及授權金鑰資訊。</span><span class="sxs-lookup"><span data-stu-id="e8827-186">The **General** tab of the **Properties** dialog box displays information about the license and lets you change the enabled status, license expiration date, and license key information.</span></span>

<a href="" id="help"></a>**<span data-ttu-id="e8827-187">說明</span><span class="sxs-lookup"><span data-stu-id="e8827-187">Help</span></span>**  
<span data-ttu-id="e8827-188">顯示應用程式虛擬化伺服器管理主控台的說明系統。</span><span class="sxs-lookup"><span data-stu-id="e8827-188">Displays the help system for the Application Virtualization Server Management Console.</span></span>

## <span data-ttu-id="e8827-189">相關主題</span><span class="sxs-lookup"><span data-stu-id="e8827-189">Related topics</span></span>


[<span data-ttu-id="e8827-190">關於應用程式授權</span><span class="sxs-lookup"><span data-stu-id="e8827-190">About Application Licensing</span></span>](about-application-licensing.md)

[<span data-ttu-id="e8827-191">如何在伺服器管理主控台中管理應用程式授權</span><span class="sxs-lookup"><span data-stu-id="e8827-191">How to Manage Application Licenses in the Server Management Console</span></span>](how-to-manage-application-licenses-in-the-server-management-console.md)

[<span data-ttu-id="e8827-192">伺服器管理主控台：應用程式授權節點</span><span class="sxs-lookup"><span data-stu-id="e8827-192">Server Management Console: Application Licenses Node</span></span>](server-management-console-application-licenses-node.md)

 

 





