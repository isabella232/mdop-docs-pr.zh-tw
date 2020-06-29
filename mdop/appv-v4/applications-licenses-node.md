---
title: 應用程式授權節點
description: 應用程式授權節點
author: dansimp
ms.assetid: 2b8752ff-aa56-483e-b844-966941af2d94
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 720de1860e72ae2c71298f93e9b346afd66da569
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802246"
---
# <span data-ttu-id="4e0ae-103">應用程式授權節點</span><span class="sxs-lookup"><span data-stu-id="4e0ae-103">Applications Licenses Node</span></span>


<span data-ttu-id="4e0ae-104">應用程式**授權**節點是應用程式虛擬化伺服器管理主控台**範圍**窗格中 [應用程式虛擬化系統] 節點下方的一個層級。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-104">The **Applications Licenses** node is one level below the Application Virtualization System node in the **Scope** pane in the Application Virtualization Server Management Console.</span></span> <span data-ttu-id="4e0ae-105">當您選取這個節點時，[**結果**] 窗格會顯示授權和授權群組清單。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-105">When you select this node, the **Results** pane displays a list of licenses and license groups.</span></span> <span data-ttu-id="4e0ae-106">以下是可用的授權類型：</span><span class="sxs-lookup"><span data-stu-id="4e0ae-106">The following license types are available:</span></span>

-   <span data-ttu-id="4e0ae-107">[**無限制的授權**]-提供任意數量的同時使用者的存取權。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-107">**Unlimited License**—Provides access for any number of simultaneous users.</span></span> <span data-ttu-id="4e0ae-108">當您想要將企業範圍的授權與應用程式建立關聯時，此授權方法相當適合。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-108">This method of licensing is appropriate when you want to associate an enterprise-wide license with an application.</span></span>

-   <span data-ttu-id="4e0ae-109">**併發授權**-可讓您定義允許使用應用程式的併發使用者數目上限。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-109">**Concurrent License**—Enables you to define the maximum number of concurrent users who are allowed to use the application.</span></span>

-   <span data-ttu-id="4e0ae-110">[**署名授權**]：可讓您指派授權給個別使用者。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-110">**Named License**—Enables you to assign a license to an individual user.</span></span> <span data-ttu-id="4e0ae-111">已命名的授權可以用來確保特定的使用者永遠能夠執行該應用程式。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-111">A named license can be used to ensure that a particular user will always be able to run the application.</span></span>

<span data-ttu-id="4e0ae-112">**記事** 您可以將併發與命名的授權合併至同一個應用程式。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-112">**Note** You can combine concurrent and named licenses for the same application.</span></span>

 

<span data-ttu-id="4e0ae-113">以滑鼠右鍵按一下**應用程式授權**節點，以顯示包含下列元素的快顯功能表。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-113">Right-click the **Applications Licenses** node to display a pop-up menu that contains the following elements.</span></span>

<a href="" id="new-unlimited-license"></a>**<span data-ttu-id="4e0ae-114">新的無限制授權</span><span class="sxs-lookup"><span data-stu-id="4e0ae-114">New Unlimited License</span></span>**  
<span data-ttu-id="4e0ae-115">顯示 [新增無限制授權] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-115">Displays the New Unlimited License Wizard.</span></span> <span data-ttu-id="4e0ae-116">此嚮導包含下列頁面：</span><span class="sxs-lookup"><span data-stu-id="4e0ae-116">This wizard consists of the following pages:</span></span>

1.  <span data-ttu-id="4e0ae-117">在 [**應用程式授權] 群組**的 [名稱] 欄位中輸入授權群組的名稱，然後在 [**授權到期警告**] 欄位中輸入一個值（以分鐘為單位）。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-117">Enter the name of the license group in the **Applications License Group Name** field, and enter a value (in minutes) in the **License Expiration Warning** field.</span></span> <span data-ttu-id="4e0ae-118">（您可以輸入從0到100的任何值）。您也可以使用向上鍵和向下鍵來選取分鐘數。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-118">(You can enter any value from 0 through 100.) You can also use the up and down arrows to select the number of minutes.</span></span>

2.  <span data-ttu-id="4e0ae-119">在 [**授權描述**] 欄位中輸入簡短的描述文字，然後選取 [**已啟用**] 核取方塊以啟用授權。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-119">Enter brief descriptive text in the **License Description** field, and select the **Enabled** check box to enable the license.</span></span>

    <span data-ttu-id="4e0ae-120">您也可以使用 [**到期日**] 欄位來指定授權的到期日。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-120">Optionally, you can use the **Expiration Date** field to specify an expiration date for the license.</span></span> <span data-ttu-id="4e0ae-121">您可以選取核取方塊以使用顯示的到期日，或者您可以使用 [行事曆] 實用程式流覽至想要的到期日。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-121">You can select the check box to use the displayed expiration date, or you can use the calendar utility to browse to the desired expiration date.</span></span>

3.  <span data-ttu-id="4e0ae-122">按一下 **[完成]** 以新增新的授權。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-122">Click **Finish** to add the new license.</span></span>

<a href="" id="new-concurrent-license"></a>**<span data-ttu-id="4e0ae-123">新的並行授權</span><span class="sxs-lookup"><span data-stu-id="4e0ae-123">New Concurrent License</span></span>**  
<span data-ttu-id="4e0ae-124">顯示 [新增併發授權] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-124">Displays the New Concurrent License Wizard.</span></span> <span data-ttu-id="4e0ae-125">此嚮導包含下列三個頁面，且與新的 [無限制授權] 嚮導幾乎完全相同：</span><span class="sxs-lookup"><span data-stu-id="4e0ae-125">This wizard consists of the following three pages and is almost identical to the New Unlimited License Wizard:</span></span>

1.  <span data-ttu-id="4e0ae-126">在 [**應用程式授權] 群組**的 [名稱] 欄位中輸入授權群組的名稱，然後在 [**授權到期警告**] 欄位中輸入一個值（以分鐘為單位）。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-126">Enter the name of the license group in the **Applications License Group Name** field, and enter a value (in minutes) in the **License Expiration Warning** field.</span></span> <span data-ttu-id="4e0ae-127">（您可以輸入從0到100的任何值）。您也可以使用向上鍵和向下鍵來選取分鐘數。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-127">(You can enter any value from 0 through 100.) You can also use the up and down arrows to select the number of minutes.</span></span>

2.  <span data-ttu-id="4e0ae-128">在 [**授權描述**] 欄位中輸入簡短的描述文字，然後在 [**併發授權數量**] 欄位中輸入值。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-128">Enter brief descriptive text in the **License Description** field, and enter a value in the **Concurrent License Quantity** field.</span></span>

    <span data-ttu-id="4e0ae-129">您也可以使用向上鍵和向下鍵來指定併發授權的數量。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-129">You can also use the up and down arrows to specify the number of concurrent licenses.</span></span> <span data-ttu-id="4e0ae-130">選取 [**已啟用**] 核取方塊以啟用授權。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-130">Select the **Enabled** check box to enable the license.</span></span>

    <span data-ttu-id="4e0ae-131">您也可以使用 [**到期日**] 欄位來指定授權的到期日。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-131">Optionally, you can use the **Expiration Date** field to specify an expiration date for the license.</span></span> <span data-ttu-id="4e0ae-132">您可以選取核取方塊以使用顯示的到期日，或者您可以使用 [行事曆] 實用程式流覽至想要的到期日。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-132">You can select the check box to use the displayed expiration date, or you can use the calendar utility to browse to the desired expiration date.</span></span>

3.  <span data-ttu-id="4e0ae-133">按一下 **[完成]** 以新增新的授權。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-133">Click **Finish** to add the new licenses.</span></span>

<a href="" id="new-named-license"></a>**<span data-ttu-id="4e0ae-134">新的命名授權</span><span class="sxs-lookup"><span data-stu-id="4e0ae-134">New Named License</span></span>**  
<span data-ttu-id="4e0ae-135">顯示新的 [命名授權] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-135">Displays the New Named License Wizard.</span></span> <span data-ttu-id="4e0ae-136">此嚮導包含下列四個頁面：</span><span class="sxs-lookup"><span data-stu-id="4e0ae-136">This wizard consists of the following four pages:</span></span>

1.  <span data-ttu-id="4e0ae-137">在 [**應用程式授權] 群組**的 [名稱] 欄位中輸入授權群組的名稱，然後在 [**授權到期警告**] 欄位中輸入一個值（以分鐘為單位）。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-137">Enter the name of the license group in the **Applications License Group Name** field, and enter a value (in minutes) in the **License Expiration Warning** field.</span></span> <span data-ttu-id="4e0ae-138">（您可以輸入從0到100的任何值）。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-138">(You can enter any value from 0 through 100).</span></span> <span data-ttu-id="4e0ae-139">您也可以使用向上鍵和向下鍵來選取分鐘數。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-139">You can also use the up and down arrows to select the number of minutes.</span></span>

2.  <span data-ttu-id="4e0ae-140">在 [**授權描述**] 欄位中輸入簡短的描述文字，然後選取 [**已啟用**] 核取方塊以啟用授權。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-140">Enter brief descriptive text in the **License Description** field, and select the **Enabled** check box to enable the license.</span></span>

    <span data-ttu-id="4e0ae-141">您也可以使用 [**到期日**] 欄位來指定授權的到期日。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-141">Optionally, you can use the **Expiration Date** field to specify an expiration date for the license.</span></span> <span data-ttu-id="4e0ae-142">您可以選取核取方塊以使用顯示的到期日，或者您可以使用 [行事曆] 實用程式流覽至想要的到期日。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-142">You can select the check box to use the displayed expiration date, or you can use the calendar utility to browse to the desired expiration date.</span></span>

3.  <span data-ttu-id="4e0ae-143">按一下 [**新增**]、[**編輯**] 或 [**移除**已命名的使用者]。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-143">Click **Add**, **Edit**, or **Remove** named users.</span></span>

4.  <span data-ttu-id="4e0ae-144">按一下 **[完成]** 以新增新的授權。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-144">Click **Finish** to add the new license.</span></span>

<a href="" id="view"></a>**<span data-ttu-id="4e0ae-145">View</span><span class="sxs-lookup"><span data-stu-id="4e0ae-145">View</span></span>**  
<span data-ttu-id="4e0ae-146">變更 [**結果**] 窗格的外觀和內容。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-146">Changes the appearance and content of the **Results** pane.</span></span>

<a href="" id="new-window-from-here"></a>**<span data-ttu-id="4e0ae-147">從這裡新增視窗</span><span class="sxs-lookup"><span data-stu-id="4e0ae-147">New Window from Here</span></span>**  
<span data-ttu-id="4e0ae-148">開啟新的管理主控台，並將選取的節點做為根節點。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-148">Opens a new management console with the selected node as the root node.</span></span>

<a href="" id="refresh"></a>**<span data-ttu-id="4e0ae-149">重新整理</span><span class="sxs-lookup"><span data-stu-id="4e0ae-149">Refresh</span></span>**  
<span data-ttu-id="4e0ae-150">刷新伺服器的視圖。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-150">Refreshes the view of the server.</span></span>

<a href="" id="export-list"></a>**<span data-ttu-id="4e0ae-151">匯出清單</span><span class="sxs-lookup"><span data-stu-id="4e0ae-151">Export List</span></span>**  
<span data-ttu-id="4e0ae-152">建立包含 [**結果**] 窗格內容的定位字元分隔文字檔。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-152">Creates a tab-delimited text file that contains the contents of the **Results** pane.</span></span> <span data-ttu-id="4e0ae-153">此專案會顯示 [標準檔案**儲存**] 對話方塊，您可以在此指定您要建立之文字檔的位置。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-153">This item displays a standard **File Save** dialog box where you specify the location for the text file you are creating.</span></span>

<a href="" id="help"></a>**<span data-ttu-id="4e0ae-154">說明</span><span class="sxs-lookup"><span data-stu-id="4e0ae-154">Help</span></span>**  
<span data-ttu-id="4e0ae-155">顯示應用程式虛擬化伺服器管理主控台的說明系統。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-155">Displays the help system for the Application Virtualization Server Management Console.</span></span>

<span data-ttu-id="4e0ae-156">如果您在 [**範圍**] 窗格中按一下 [**應用程式授權**] 節點底下的授權群組或授權，就可以使用下列元素。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-156">If you click a license group or license that appears under the **Application Licenses** node in the **Scope** pane, the following elements are available.</span></span>

<a href="" id="view"></a>**<span data-ttu-id="4e0ae-157">View</span><span class="sxs-lookup"><span data-stu-id="4e0ae-157">View</span></span>**  
<span data-ttu-id="4e0ae-158">變更 [**結果**] 窗格的外觀和內容。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-158">Changes the appearance and content of the **Results** pane.</span></span>

<a href="" id="new-window-from-here"></a>**<span data-ttu-id="4e0ae-159">從這裡新增視窗</span><span class="sxs-lookup"><span data-stu-id="4e0ae-159">New Window from Here</span></span>**  
<span data-ttu-id="4e0ae-160">開啟新的管理主控台，並將選取的節點做為根節點。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-160">Opens a new management console with the selected node as the root node.</span></span>

<a href="" id="delete"></a>**<span data-ttu-id="4e0ae-161">刪除</span><span class="sxs-lookup"><span data-stu-id="4e0ae-161">Delete</span></span>**  
<span data-ttu-id="4e0ae-162">從 [**結果**] 窗格刪除套件。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-162">Deletes a package from the **Results** pane.</span></span>

<a href="" id="rename"></a>**<span data-ttu-id="4e0ae-163">重新命名</span><span class="sxs-lookup"><span data-stu-id="4e0ae-163">Rename</span></span>**  
<span data-ttu-id="4e0ae-164">變更 [**結果**] 窗格中套件的名稱。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-164">Changes the name of a package in the **Results** pane.</span></span>

<a href="" id="export-list"></a>**<span data-ttu-id="4e0ae-165">匯出清單</span><span class="sxs-lookup"><span data-stu-id="4e0ae-165">Export List</span></span>**  
<span data-ttu-id="4e0ae-166">建立包含 [**結果**] 窗格內容的定位字元分隔文字檔。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-166">Creates a tab-delimited text file that contains the contents of the **Results** pane.</span></span> <span data-ttu-id="4e0ae-167">此專案會顯示 [標準檔案**儲存**] 對話方塊，您可以在此指定您要建立之文字檔的位置。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-167">This item displays a standard **File Save** dialog box where you specify the location for the text file you are creating.</span></span>

<a href="" id="properties"></a>**<span data-ttu-id="4e0ae-168">屬性</span><span class="sxs-lookup"><span data-stu-id="4e0ae-168">Properties</span></span>**  
<span data-ttu-id="4e0ae-169">顯示所選授權群組的 [**屬性**] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-169">Displays the **Properties** dialog box for the selected license group.</span></span> <span data-ttu-id="4e0ae-170">[**屬性**] 對話方塊的 [**一般**] 索引標籤會顯示授權群組的相關資訊，並可讓您變更 [**授權到期警告**] 欄位中的時間值。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-170">The **General** tab of the **Properties** dialog box displays information about the license group and lets you change the time value in the **License Expiration Warning** field.</span></span> <span data-ttu-id="4e0ae-171">[**應用程式**] 索引標籤會顯示與授權群組相關聯的應用程式清單。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-171">The **Applications** tab displays the list of applications associated with the license group.</span></span>

<a href="" id="help"></a>**<span data-ttu-id="4e0ae-172">說明</span><span class="sxs-lookup"><span data-stu-id="4e0ae-172">Help</span></span>**  
<span data-ttu-id="4e0ae-173">顯示應用程式虛擬化伺服器管理主控台的說明系統。</span><span class="sxs-lookup"><span data-stu-id="4e0ae-173">Displays the help system for the Application Virtualization Server Management Console.</span></span>

## <span data-ttu-id="4e0ae-174">相關主題</span><span class="sxs-lookup"><span data-stu-id="4e0ae-174">Related topics</span></span>


[<span data-ttu-id="4e0ae-175">關於應用程式授權</span><span class="sxs-lookup"><span data-stu-id="4e0ae-175">About Application Licensing</span></span>](about-application-licensing.md)

[<span data-ttu-id="4e0ae-176">如何在伺服器管理主控台中管理應用程式授權</span><span class="sxs-lookup"><span data-stu-id="4e0ae-176">How to Manage Application Licenses in the Server Management Console</span></span>](how-to-manage-application-licenses-in-the-server-management-console.md)

[<span data-ttu-id="4e0ae-177">伺服器管理主控台：應用程式授權節點</span><span class="sxs-lookup"><span data-stu-id="4e0ae-177">Server Management Console: Application Licenses Node</span></span>](server-management-console-application-licenses-node.md)

 

 





