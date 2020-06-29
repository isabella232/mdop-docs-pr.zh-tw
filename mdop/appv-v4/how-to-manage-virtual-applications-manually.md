---
title: 如何手動管理虛擬應用程式
description: 如何手動管理虛擬應用程式
author: dansimp
ms.assetid: 583c5255-d3f4-4197-85cd-2a59868d85de
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e8dd5bb9d62950ac1a03ad0ec14802d9e0ff56e8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801286"
---
# <span data-ttu-id="bcc66-103">如何手動管理虛擬應用程式</span><span class="sxs-lookup"><span data-stu-id="bcc66-103">How to Manage Virtual Applications Manually</span></span>


<span data-ttu-id="bcc66-104">您可以使用應用程式虛擬化（App-v）用戶端管理主控台來管理 App-v Desktop 用戶端中的虛擬應用程式，或遠端桌面服務的 App-v 用戶端（以前稱為 [終端服務]）。</span><span class="sxs-lookup"><span data-stu-id="bcc66-104">You can use the Application Virtualization (App-V) Client Management Console to manage virtual applications in the App-V Desktop Client or the App-V Client for Remote Desktop Services (formerly Terminal Services).</span></span> <span data-ttu-id="bcc66-105">App-v 管理員可以使用執行下列任務：</span><span class="sxs-lookup"><span data-stu-id="bcc66-105">App-V administrators can use perform the following tasks:</span></span>

## <span data-ttu-id="bcc66-106">如何載入或卸載 App-v 應用程式</span><span class="sxs-lookup"><span data-stu-id="bcc66-106">How to Load or Unload an App-V Application</span></span>


<span data-ttu-id="bcc66-107">您可以使用下列程式，直接從應用程式虛擬化用戶端管理主控台中**應用程式**節點的**結果**窗格載入或卸載應用程式。</span><span class="sxs-lookup"><span data-stu-id="bcc66-107">You can use the following procedures to load or unload an application from the cache, directly from the **Results** pane of the **Application** node in the Application Virtualization Client Management Console.</span></span> <span data-ttu-id="bcc66-108">當您選取這個節點時，[**結果**] 窗格會顯示應用程式清單。</span><span class="sxs-lookup"><span data-stu-id="bcc66-108">When you select this node, the **Results** pane displays a list of applications.</span></span>

<span data-ttu-id="bcc66-109">**記事** 當您載入或卸載套件時，套件中的所有應用程式都會載入或從快取中移除。</span><span class="sxs-lookup"><span data-stu-id="bcc66-109">**Note** When you load or unload a package, all the applications in the package are loaded into or removed from cache.</span></span> <span data-ttu-id="bcc66-110">載入套件時，如果您在快取中沒有足夠的空間來載入應用程式，請增加您的快取大小。</span><span class="sxs-lookup"><span data-stu-id="bcc66-110">When loading a package, if you do not have adequate space in cache to load the applications, increase your cache size.</span></span> <span data-ttu-id="bcc66-111">如需快取大小的詳細資訊，請參閱[如何變更快取大小與磁片磁碟機字母指定](how-to-change-the-cache-size-and-the-drive-letter-designation.md)。</span><span class="sxs-lookup"><span data-stu-id="bcc66-111">For more information about cache size, see [How to Change the Cache Size and the Drive Letter Designation](how-to-change-the-cache-size-and-the-drive-letter-designation.md).</span></span>

 

**<span data-ttu-id="bcc66-112">載入 App-v 應用程式</span><span class="sxs-lookup"><span data-stu-id="bcc66-112">To load an App-V application</span></span>**

1.  <span data-ttu-id="bcc66-113">將游標移至 [**結果**] 窗格，以滑鼠右鍵按一下所需的應用程式，然後從快顯功能表中選取 [**載入**]。</span><span class="sxs-lookup"><span data-stu-id="bcc66-113">Move the cursor to the **Results** pane, right-click the desired application, and select **Load** from the pop-up menu.</span></span>

2.  <span data-ttu-id="bcc66-114">應用程式會自動載入。</span><span class="sxs-lookup"><span data-stu-id="bcc66-114">The application is automatically loaded.</span></span> <span data-ttu-id="bcc66-115">在標示為 [**封裝狀態**] 的欄中追蹤進度。</span><span class="sxs-lookup"><span data-stu-id="bcc66-115">The progress is tracked in the column labeled **Package Status**.</span></span> <span data-ttu-id="bcc66-116">您必須重新整理視圖，才能查看載入已完成或查看進度。</span><span class="sxs-lookup"><span data-stu-id="bcc66-116">You must refresh the view to see that the load is complete or to see the progress.</span></span>

**<span data-ttu-id="bcc66-117">若要卸載 App-v 應用程式</span><span class="sxs-lookup"><span data-stu-id="bcc66-117">To unload an App-V application</span></span>**

1.  <span data-ttu-id="bcc66-118">將游標移至 [**結果**] 窗格，以滑鼠右鍵按一下所需的應用程式，然後從快顯功能表中選取 **[卸載**]。</span><span class="sxs-lookup"><span data-stu-id="bcc66-118">Move the cursor to the **Results** pane, right-click the desired application, and select **Unload** from the pop-up menu.</span></span>

2.  <span data-ttu-id="bcc66-119">應用程式會自動卸載，且 [**套件狀態**] 欄會更新，以反映所做的變更。</span><span class="sxs-lookup"><span data-stu-id="bcc66-119">The application is automatically unloaded, and the **Package Status** column is updated to reflect the change.</span></span>

## <span data-ttu-id="bcc66-120">如何清除 App-v 應用程式</span><span class="sxs-lookup"><span data-stu-id="bcc66-120">How to clear an App-V application</span></span>


<span data-ttu-id="bcc66-121">您可以直接從應用程式虛擬化用戶端管理主控台中**應用程式**節點的 [**結果**] 窗格中，清除該應用程式。</span><span class="sxs-lookup"><span data-stu-id="bcc66-121">You can clear an application from the console directly from the **Results** pane of the **Application** node in the Application Virtualization Client Management Console.</span></span> <span data-ttu-id="bcc66-122">當您清除應用程式時，系統會移除與應用程式相對應的設定、快速鍵及檔案類型關聯，同時也會從使用者的應用程式清單中移除應用程式。</span><span class="sxs-lookup"><span data-stu-id="bcc66-122">When you clear an application, the system removes the settings, shortcuts, and file type associations that correspond to the application and also removes the application from the user’s list of applications.</span></span>

<span data-ttu-id="bcc66-123">**記事** 當您從主控台清除應用程式時，您將無法再使用該應用程式。</span><span class="sxs-lookup"><span data-stu-id="bcc66-123">**Note** When you clear an application from the console, you can no longer use that application.</span></span> <span data-ttu-id="bcc66-124">不過，應用程式仍會保留在快取中，而且在同一系統上仍可供其他使用者使用。</span><span class="sxs-lookup"><span data-stu-id="bcc66-124">However, the application remains in cache and is still available to other users on the same system.</span></span> <span data-ttu-id="bcc66-125">在發佈重新整理之後，清除的應用程式就會再次提供給您使用。</span><span class="sxs-lookup"><span data-stu-id="bcc66-125">After a publishing refresh, the cleared applications will again become available to you.</span></span> <span data-ttu-id="bcc66-126">如果套件中有多個應用程式，則在清除所有應用程式之前，不會移除使用者的設定。</span><span class="sxs-lookup"><span data-stu-id="bcc66-126">If there are multiple applications in a package, the user's settings are not removed until all of the applications are cleared.</span></span>

 

**<span data-ttu-id="bcc66-127">從主控台清除應用程式</span><span class="sxs-lookup"><span data-stu-id="bcc66-127">To clear an application from the console</span></span>**

1.  <span data-ttu-id="bcc66-128">將游標移至 [**結果**] 窗格，以滑鼠右鍵按一下所需的應用程式，然後從快顯功能表中選取 [**清除**]。</span><span class="sxs-lookup"><span data-stu-id="bcc66-128">Move the cursor to the **Results** pane, right-click the desired application, and select **Clear** from the pop-up menu.</span></span>

2.  <span data-ttu-id="bcc66-129">在確認提示時，按一下 **[是]** 以移除應用程式，或按一下 [**否**] 取消操作。</span><span class="sxs-lookup"><span data-stu-id="bcc66-129">At the confirmation prompt, click **Yes** to remove the application or click **No** to cancel the operation.</span></span>

## <span data-ttu-id="bcc66-130">如何修復 App V 應用程式</span><span class="sxs-lookup"><span data-stu-id="bcc66-130">How to Repair an App-V application</span></span>


<span data-ttu-id="bcc66-131">若要修復選取的應用程式，您可以直接從應用程式虛擬化用戶端管理主控台中的 [**應用程式**] 節點的 [**結果**] 窗格執行下列程式。</span><span class="sxs-lookup"><span data-stu-id="bcc66-131">To repair a selected application, you can perform the following procedure directly from the **Results** pane of the **Application** node in the Application Virtualization Client Management Console.</span></span> <span data-ttu-id="bcc66-132">當您修復應用程式時，您會移除任何自訂的使用者設定，並還原預設設定。</span><span class="sxs-lookup"><span data-stu-id="bcc66-132">When you repair an application, you remove any custom user settings and restore the default settings.</span></span> <span data-ttu-id="bcc66-133">這個動作不會變更或刪除快速鍵或檔案類型關聯，也不會從快取中移除應用程式。</span><span class="sxs-lookup"><span data-stu-id="bcc66-133">This action does not change or delete shortcuts or file type associations, and it does not remove the application from cache.</span></span>

**<span data-ttu-id="bcc66-134">修復 App-v 應用程式</span><span class="sxs-lookup"><span data-stu-id="bcc66-134">To repair an App-V application</span></span>**

1.  <span data-ttu-id="bcc66-135">將游標移至 [**結果**] 窗格。</span><span class="sxs-lookup"><span data-stu-id="bcc66-135">Move the cursor to the **Results** pane.</span></span>

2.  <span data-ttu-id="bcc66-136">以滑鼠右鍵按一下所需的應用程式，然後從快顯功能表中選取 [**修復**]。</span><span class="sxs-lookup"><span data-stu-id="bcc66-136">Right-click the desired application, and select **Repair** from the pop-up menu.</span></span>

3.  <span data-ttu-id="bcc66-137">在確認提示時，按一下 **[是]** 以修復應用程式，或按一下 [**否**] 取消。</span><span class="sxs-lookup"><span data-stu-id="bcc66-137">At the confirmation prompt, click **Yes** to repair the application or **No** to cancel.</span></span>

## <span data-ttu-id="bcc66-138">如何匯入 App-v 應用程式</span><span class="sxs-lookup"><span data-stu-id="bcc66-138">How to import an App-V application</span></span>


<span data-ttu-id="bcc66-139">您可以使用下列程式，直接從應用程式虛擬化用戶端管理主控台中**應用**程式節點的 [**結果**] 窗格，將應用程式匯入快取。</span><span class="sxs-lookup"><span data-stu-id="bcc66-139">You can use the following procedure to import an application into the cache directly from the **Results** pane of the **Application** node in the Application Virtualization Client Management Console.</span></span>

**<span data-ttu-id="bcc66-140">匯入 App-v 應用程式</span><span class="sxs-lookup"><span data-stu-id="bcc66-140">To import an App-V application</span></span>**

1.  <span data-ttu-id="bcc66-141">將游標移至 [**結果**] 窗格，以滑鼠右鍵按一下所需的應用程式，然後從快顯功能表中選取 [匯**入**]。</span><span class="sxs-lookup"><span data-stu-id="bcc66-141">Move the cursor to the **Results** pane, right-click the desired application, and select **Import** from the pop-up menu.</span></span>

2.  <span data-ttu-id="bcc66-142">從 [**流覽**] 視窗，流覽至所需應用程式的套件檔案位置，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="bcc66-142">From the **Browse** window, navigate to the location of the package file for the desired application, and then click **OK**.</span></span>

    <span data-ttu-id="bcc66-143">**記事** 如果您已設定匯入搜尋路徑，或 SFT 檔案與上一個成功匯入的路徑相同，則不需要步驟2。</span><span class="sxs-lookup"><span data-stu-id="bcc66-143">**Note** If you have already configured an import search path or if the SFT file is in the same path as the last successful import, step 2 is not required.</span></span>

     

## <span data-ttu-id="bcc66-144">如何鎖定或解除鎖定應用程式 V 應用程式</span><span class="sxs-lookup"><span data-stu-id="bcc66-144">How to lock or unlock an App-V application</span></span>


<span data-ttu-id="bcc66-145">您可以使用下列程式來鎖定或解除鎖定應用程式虛擬化桌面用戶端快取或遠端桌面服務（舊稱終端服務）快取的用戶端中的任何應用程式。</span><span class="sxs-lookup"><span data-stu-id="bcc66-145">You can use the following procedures to lock or unlock any application in the Application Virtualization Desktop Client cache or the Client for Remote Desktop Services (formerly Terminal Services) cache.</span></span> <span data-ttu-id="bcc66-146">無法從快取中移除鎖定的應用程式，為新的應用程式騰出空間。</span><span class="sxs-lookup"><span data-stu-id="bcc66-146">A locked application cannot be removed from the cache to make room for new applications.</span></span> <span data-ttu-id="bcc66-147">若要從應用程式虛擬化桌面用戶端快取或遠端桌面服務快取的用戶端移除鎖定的應用程式，您必須先將其解除鎖定。</span><span class="sxs-lookup"><span data-stu-id="bcc66-147">To remove a locked application from the Application Virtualization Desktop Client cache or the Client for Remote Desktop Services cache, you must first unlock it.</span></span>

**<span data-ttu-id="bcc66-148">鎖定應用程式</span><span class="sxs-lookup"><span data-stu-id="bcc66-148">To lock an application</span></span>**

1.  <span data-ttu-id="bcc66-149">將游標移至 [**結果**] 窗格。</span><span class="sxs-lookup"><span data-stu-id="bcc66-149">Move the cursor to the **Results** pane.</span></span>

2.  <span data-ttu-id="bcc66-150">以滑鼠右鍵按一下所需的應用程式，然後從快顯功能表中選取 [**鎖定**]。</span><span class="sxs-lookup"><span data-stu-id="bcc66-150">Right-click the desired application, and select **Lock** from the pop-up menu.</span></span> <span data-ttu-id="bcc66-151">所選取的應用程式已鎖定在快取中。</span><span class="sxs-lookup"><span data-stu-id="bcc66-151">The selected application is locked in the cache.</span></span>

**<span data-ttu-id="bcc66-152">解除鎖定應用程式</span><span class="sxs-lookup"><span data-stu-id="bcc66-152">To unlock an application</span></span>**

1.  <span data-ttu-id="bcc66-153">將游標移至 [**結果**] 窗格。</span><span class="sxs-lookup"><span data-stu-id="bcc66-153">Move the cursor to the **Results** pane.</span></span>

2.  <span data-ttu-id="bcc66-154">以滑鼠右鍵按一下所需的應用程式，然後從快顯功能表中選取 [**解除鎖定**]。</span><span class="sxs-lookup"><span data-stu-id="bcc66-154">Right-click the desired application, and select **Unlock** from the pop-up menu.</span></span> <span data-ttu-id="bcc66-155">所選取的應用程式會在快取中解除鎖定，而且可以移除。</span><span class="sxs-lookup"><span data-stu-id="bcc66-155">The selected application is unlocked in the cache and can be removed.</span></span>

## <span data-ttu-id="bcc66-156">如何刪除 App-v 應用程式</span><span class="sxs-lookup"><span data-stu-id="bcc66-156">How to delete an App-V application</span></span>


<span data-ttu-id="bcc66-157">當您在應用程式虛擬化用戶端管理主控台中選取**應用程式**節點時，[**結果**] 窗格會顯示應用程式的清單。</span><span class="sxs-lookup"><span data-stu-id="bcc66-157">When you select the **Application** node in the Application Virtualization Client Management Console, the **Results** pane displays a list of applications.</span></span> <span data-ttu-id="bcc66-158">您可以使用下列程式，從 [**結果**] 窗格中刪除應用程式，這也會從快取中移除應用程式。</span><span class="sxs-lookup"><span data-stu-id="bcc66-158">You can use the following procedure to delete an application from the **Results** pane, which also removes the application from the cache.</span></span>

<span data-ttu-id="bcc66-159">**記事** 當您刪除應用程式時，所選的應用程式將無法再供該用戶端上的任何使用者使用。</span><span class="sxs-lookup"><span data-stu-id="bcc66-159">**Note** When you delete an application, the selected application will no longer be available to any users on that client.</span></span> <span data-ttu-id="bcc66-160">快捷方式和檔案類型關聯已隱藏，且應用程式已從快取中刪除。</span><span class="sxs-lookup"><span data-stu-id="bcc66-160">Shortcuts and file type associations are hidden, and the application is deleted from cache.</span></span> <span data-ttu-id="bcc66-161">不過，如果另一個應用程式參照所選應用程式檔案系統快取資料中的資料，這些專案就不會被刪除。</span><span class="sxs-lookup"><span data-stu-id="bcc66-161">However, if another application refers to data in the file system cache data for the selected application, these items will not be deleted.</span></span>

<span data-ttu-id="bcc66-162">更新發佈之後，已刪除的應用程式就會再次提供給您使用。</span><span class="sxs-lookup"><span data-stu-id="bcc66-162">After a publishing refresh, the deleted applications will again become available to you.</span></span>

 

**<span data-ttu-id="bcc66-163">刪除應用程式</span><span class="sxs-lookup"><span data-stu-id="bcc66-163">To delete an application</span></span>**

1.  <span data-ttu-id="bcc66-164">將游標移至 [**結果**] 窗格，以滑鼠右鍵按一下所需的應用程式，然後從快顯功能表中選取 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="bcc66-164">Move the cursor to the **Results** pane, right-click the desired application, and select **Delete** from the pop-up menu.</span></span>

2.  <span data-ttu-id="bcc66-165">在確認提示時，按一下 **[是]** 以移除應用程式，或按一下 [**否**] 取消操作。</span><span class="sxs-lookup"><span data-stu-id="bcc66-165">At the confirmation prompt, click **Yes** to remove the application or click **No** to cancel the operation.</span></span>

## <span data-ttu-id="bcc66-166">如何變更 app-v 應用程式圖示</span><span class="sxs-lookup"><span data-stu-id="bcc66-166">How to change an App-V application icon</span></span>


<span data-ttu-id="bcc66-167">您可以使用下列程式，直接從應用程式虛擬化用戶端管理主控台的 [**應用**程式] 節點的 [**結果**] 窗格中，變更與所選應用程式相關聯的圖示。</span><span class="sxs-lookup"><span data-stu-id="bcc66-167">You can use the following procedure to change an icon associated with the selected application directly from the **Results** pane of the **Application** node in the Application Virtualization Client Management Console.</span></span>

**<span data-ttu-id="bcc66-168">變更應用程式圖示</span><span class="sxs-lookup"><span data-stu-id="bcc66-168">To change an application icon</span></span>**

1.  <span data-ttu-id="bcc66-169">將游標移至 [**結果**] 窗格，然後以滑鼠右鍵按一下所需的應用程式。</span><span class="sxs-lookup"><span data-stu-id="bcc66-169">Move the cursor to the **Results** pane, and right-click the desired application.</span></span>

2.  <span data-ttu-id="bcc66-170">選取 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="bcc66-170">Select **Properties**.</span></span>

3.  <span data-ttu-id="bcc66-171">按一下 [**一般**] 索引標籤上的 [**變更] 圖示**。</span><span class="sxs-lookup"><span data-stu-id="bcc66-171">On the **General** tab, click **Change Icon**.</span></span>

4.  <span data-ttu-id="bcc66-172">選取所要的圖示，或流覽至其他位置以選取該圖示。</span><span class="sxs-lookup"><span data-stu-id="bcc66-172">Select the desired icon, or browse to another location to select the icon.</span></span> <span data-ttu-id="bcc66-173">選取圖示之後，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="bcc66-173">After you've selected the icon, click **OK**.</span></span> <span data-ttu-id="bcc66-174">新圖示會出現在 [**結果**] 窗格中。</span><span class="sxs-lookup"><span data-stu-id="bcc66-174">The new icon appears in the **Results** pane.</span></span>

## <span data-ttu-id="bcc66-175">如何新增 app-v 應用程式</span><span class="sxs-lookup"><span data-stu-id="bcc66-175">How to add an App-V application</span></span>


<span data-ttu-id="bcc66-176">您可以使用下列程式，直接從應用程式虛擬化用戶端管理主控台的 [**應用**程式] 節點的 [**結果**] 窗格中新增應用程式。</span><span class="sxs-lookup"><span data-stu-id="bcc66-176">You can use the following procedure to add an application directly from the **Results** pane of the **Application** node in the Application Virtualization Client Management Console.</span></span>

**<span data-ttu-id="bcc66-177">若要新增應用程式</span><span class="sxs-lookup"><span data-stu-id="bcc66-177">To add an application</span></span>**

1.  <span data-ttu-id="bcc66-178">在 [**結果**] 窗格中，以滑鼠右鍵按一下，然後從快顯功能表中選取 [**新增應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="bcc66-178">In the **Results** pane, right-click and select **New Application** from the pop-up menu.</span></span>

2.  <span data-ttu-id="bcc66-179">您可以在 [嚮導] 頁面上執行下列任務：</span><span class="sxs-lookup"><span data-stu-id="bcc66-179">On the wizard page, you can perform the following tasks:</span></span>

    1.  <span data-ttu-id="bcc66-180">[**變更] 圖示**-顯示標準的 Windows 圖示瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="bcc66-180">**Change Icon**—Displays a standard Windows icon browser.</span></span> <span data-ttu-id="bcc66-181">流覽並選取所要的圖示。</span><span class="sxs-lookup"><span data-stu-id="bcc66-181">Browse to and select the desired icon.</span></span>

    2.  <span data-ttu-id="bcc66-182">**OSD 檔案路徑或 URL**-輸入本機絕對路徑、完整 UNC 路徑（網路上的共用檔案或目錄），或是 HTTP URL。</span><span class="sxs-lookup"><span data-stu-id="bcc66-182">**OSD File Path or URL**—Enter a local absolute path, a full UNC path (shared file or directory on a network), or an HTTP URL.</span></span>

    3.  <span data-ttu-id="bcc66-183">**（OSD [流覽] 按鈕）**-顯示標準的 Windows [**開啟**檔案] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="bcc66-183">**(OSD browse button)**—Displays the standard Windows **Open File** dialog box.</span></span> <span data-ttu-id="bcc66-184">流覽以尋找想要的檔案。</span><span class="sxs-lookup"><span data-stu-id="bcc66-184">Browse to find the desired file.</span></span>

3.  <span data-ttu-id="bcc66-185">按一下 **[完成]** ，將應用程式新增至 [**結果**] 窗格。</span><span class="sxs-lookup"><span data-stu-id="bcc66-185">Click **Finish** to add the application to the **Results** pane.</span></span>

## <span data-ttu-id="bcc66-186">如何公佈 App-v 應用程式快捷方式</span><span class="sxs-lookup"><span data-stu-id="bcc66-186">How to publish an App-V application shortcut</span></span>


<span data-ttu-id="bcc66-187">您可以使用下列程式，直接從應用程式虛擬化用戶端管理主控台中 [**應用程式**] 節點的 [**結果**] 窗格發佈應用程式的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="bcc66-187">You can use the following procedure to publish shortcuts to an application directly from the **Results** pane of the **Application** node in the Application Virtualization Client Management Console.</span></span>

**<span data-ttu-id="bcc66-188">發佈應用程式快速鍵</span><span class="sxs-lookup"><span data-stu-id="bcc66-188">To publish application shortcuts</span></span>**

1.  <span data-ttu-id="bcc66-189">將游標移至 [**結果**] 窗格，以滑鼠右鍵按一下所需的應用程式，然後從快顯功能表中選取 [**新增快速鍵**]，以顯示 [新增快速鍵] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="bcc66-189">Move the cursor to the **Results** pane, right-click the desired application, and select **New Shortcut** from the pop-up menu to display the New Shortcut Wizard.</span></span>

2.  <span data-ttu-id="bcc66-190">在 [新增快捷方式] 嚮導的第一頁上，選取一個圖示，然後指定快捷方式的名稱。</span><span class="sxs-lookup"><span data-stu-id="bcc66-190">On the first page of the New Shortcut Wizard, select an icon and specify a name for the shortcut.</span></span>

    1.  <span data-ttu-id="bcc66-191">[**變更] 圖示**-顯示標準的 Windows 圖示瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="bcc66-191">**Change Icon**—Displays a standard Windows icon browser.</span></span> <span data-ttu-id="bcc66-192">流覽並選取所要的圖示。</span><span class="sxs-lookup"><span data-stu-id="bcc66-192">Browse to and select the desired icon.</span></span>

    2.  <span data-ttu-id="bcc66-193">[**快捷方式標題**]：輸入要賦予快速鍵的名稱。</span><span class="sxs-lookup"><span data-stu-id="bcc66-193">**Shortcut Title**—Enter the name you want to give the shortcut.</span></span> <span data-ttu-id="bcc66-194">這個欄位預設為應用程式現有的名稱和版本。</span><span class="sxs-lookup"><span data-stu-id="bcc66-194">This field defaults to the existing name and version of the application.</span></span>

3.  <span data-ttu-id="bcc66-195">在嚮導的第二個頁面上，決定已發佈快捷方式的位置。</span><span class="sxs-lookup"><span data-stu-id="bcc66-195">On the second page of the wizard, determine the location of the published shortcut.</span></span>

    1.  <span data-ttu-id="bcc66-196">**桌面**-選取此核取方塊即可將快捷方式發佈至桌面。</span><span class="sxs-lookup"><span data-stu-id="bcc66-196">**The Desktop**—Select this check box to publish the shortcut to the desktop.</span></span>

    2.  <span data-ttu-id="bcc66-197">**[快速啟動] 工具列**-選取此核取方塊即可將快捷方式發佈至 [快速啟動] 工具列。</span><span class="sxs-lookup"><span data-stu-id="bcc66-197">**The Quick Launch Toolbar**—Select this check box to publish the shortcut to the Quick Launch toolbar.</span></span>

    3.  <span data-ttu-id="bcc66-198">**[傳送至] 功能表**：選取此核取方塊，即可將快捷方式發佈至 [**傳送至**] 功能表。</span><span class="sxs-lookup"><span data-stu-id="bcc66-198">**The Send To Menu**—Select this check box to publish the shortcut to the **Send To** menu.</span></span>

    4.  <span data-ttu-id="bcc66-199">**[開始] 功能表中的程式**：當您選取 [**開始] 功能表**核取方塊時，這個欄位就會變成作用中。</span><span class="sxs-lookup"><span data-stu-id="bcc66-199">**Programs in the Start Menu**—When you select the **Start Menu** check box, this field becomes active.</span></span> <span data-ttu-id="bcc66-200">將此欄位保留空白，即可將快捷方式直接發佈至 [程式] 資料夾的根目錄，或輸入資料夾名稱或階層（例如，「我的 _Computer \\Office 應用程式」）。</span><span class="sxs-lookup"><span data-stu-id="bcc66-200">Leave this field blank to publish the shortcut directly to the root of the Programs folder, or enter a folder name or hierarchy—for example, "My\_Computer\\Office Applications."</span></span> <span data-ttu-id="bcc66-201">以這種方式建立的快速鍵只適用于目前的使用者。</span><span class="sxs-lookup"><span data-stu-id="bcc66-201">Shortcuts created this way are available only for the current user.</span></span>

    5.  <span data-ttu-id="bcc66-202">[**其他位置** **] 和 [流覽]** 按鈕：當您選取 [**其他位置**] 核取方塊時，此欄位就會變成作用中。</span><span class="sxs-lookup"><span data-stu-id="bcc66-202">**Another location** and **Browse** button—When you select the **Another location** check box, this field becomes active.</span></span> <span data-ttu-id="bcc66-203">輸入電腦上的任何有效位置或任何可用的 UNC 路徑（網路上的共用檔案或目錄）。</span><span class="sxs-lookup"><span data-stu-id="bcc66-203">Enter any valid location on the computer or any available UNC path (shared file or directory on a network).</span></span> <span data-ttu-id="bcc66-204">[**流覽]** 按鈕會顯示標準的 Windows 檔案 [**開啟**舊檔] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="bcc66-204">The **Browse** button displays a standard Windows **File Open** dialog box.</span></span>

4.  <span data-ttu-id="bcc66-205">在嚮導的第三個頁面上，輸入所需的命令列參數。</span><span class="sxs-lookup"><span data-stu-id="bcc66-205">On the third page of the wizard, enter desired command-line parameters.</span></span>

5.  <span data-ttu-id="bcc66-206">按一下 **[完成]** ，發佈快捷方式並移至 [**結果**] 窗格。</span><span class="sxs-lookup"><span data-stu-id="bcc66-206">Click **Finish** to publish the shortcuts and exit to the **Results** pane.</span></span>

## <span data-ttu-id="bcc66-207">如何新增 App-v 應用程式的檔案類型關聯</span><span class="sxs-lookup"><span data-stu-id="bcc66-207">How to add a file type association for an App-V application</span></span>


<span data-ttu-id="bcc66-208">您可以使用下列程式，使用應用程式虛擬化用戶端管理主控台中的 [**檔案類型關聯**] 節點來新增檔案類型關聯。</span><span class="sxs-lookup"><span data-stu-id="bcc66-208">You can use the following procedure to add a file type association, using the **File Type Associations** node in the Application Virtualization Client Management Console.</span></span>

**<span data-ttu-id="bcc66-209">新增檔案類型關聯</span><span class="sxs-lookup"><span data-stu-id="bcc66-209">To add a file type association</span></span>**

1.  <span data-ttu-id="bcc66-210">以滑鼠右鍵按一下 [**檔案類型關聯**] 節點，然後從快顯功能表中選取 [**新增關聯**]。</span><span class="sxs-lookup"><span data-stu-id="bcc66-210">Right-click the **File Type Associations** node, and select **New Association** from the pop-up menu.</span></span>

2.  <span data-ttu-id="bcc66-211">完成下列資訊，完成對話方塊的第一個步驟，然後按 **[下一步]**：</span><span class="sxs-lookup"><span data-stu-id="bcc66-211">Complete the first step of the dialog box by completing the following information, and then click **Next**:</span></span>

    1.  <span data-ttu-id="bcc66-212">[**延伸**]-輸入新的副檔名。</span><span class="sxs-lookup"><span data-stu-id="bcc66-212">**Extension**—Enter a new file name extension.</span></span> <span data-ttu-id="bcc66-213">此欄位預設為空白。</span><span class="sxs-lookup"><span data-stu-id="bcc66-213">This field is blank by default.</span></span>

    2.  <span data-ttu-id="bcc66-214">**使用此描述建立新的檔案類型**-選取此選項按鈕，即可在作用中欄位中輸入新的檔案類型描述。</span><span class="sxs-lookup"><span data-stu-id="bcc66-214">**Create a new file type with this description**—Select this radio button to enter a new file type description in the active field.</span></span> <span data-ttu-id="bcc66-215">此按鈕預設為選取狀態，且作用中欄位為空白。</span><span class="sxs-lookup"><span data-stu-id="bcc66-215">This button is selected by default, and the active field is blank.</span></span>

    3.  <span data-ttu-id="bcc66-216">**將此檔案類型套用至所有使用者**：如果您希望所有使用者都能全域關聯，請選取此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="bcc66-216">**Apply this file type to all users**—Select this check box when you want this association to be global for all users.</span></span> <span data-ttu-id="bcc66-217">根據預設，此方塊是清除的。</span><span class="sxs-lookup"><span data-stu-id="bcc66-217">By default, this box is cleared.</span></span>

    4.  <span data-ttu-id="bcc66-218">[**與現有的檔案類型連結此延伸**]：選取此選項按鈕，即可將延伸與現有的檔案類型建立關聯。</span><span class="sxs-lookup"><span data-stu-id="bcc66-218">**Link this extension with an existing file type**—Select this radio button to associate the extension with an existing file type.</span></span> <span data-ttu-id="bcc66-219">從下拉式清單中挑選檔案類型。</span><span class="sxs-lookup"><span data-stu-id="bcc66-219">Pick a file type from the drop-down list.</span></span> <span data-ttu-id="bcc66-220">當您選擇此選項時， **[下一步**] 會改為 **[完成**]。</span><span class="sxs-lookup"><span data-stu-id="bcc66-220">When you choose this option, **Next** is changed to **Finish**.</span></span>

3.  <span data-ttu-id="bcc66-221">完成下列資訊，然後按一下 **[完成**] 以返回用戶端管理主控台，以完成對話方塊的第二個步驟：</span><span class="sxs-lookup"><span data-stu-id="bcc66-221">Complete the second step of the dialog box by completing the following information, and then click **Finish** to return to the Client Management Console:</span></span>

    1.  <span data-ttu-id="bcc66-222">[**變更] 圖示**：按一下此按鈕即可變更應用程式圖示。</span><span class="sxs-lookup"><span data-stu-id="bcc66-222">**Change Icon**—Click this button to change the application icon.</span></span> <span data-ttu-id="bcc66-223">選取其中一個可用的圖示，或流覽至新位置，然後選取一個圖示。</span><span class="sxs-lookup"><span data-stu-id="bcc66-223">Select one of the available icons, or browse to a new location and select an icon.</span></span>

    2.  <span data-ttu-id="bcc66-224">**使用選取的應用程式開啟**檔案—選取此選項按鈕，以現有的應用程式開啟檔案。</span><span class="sxs-lookup"><span data-stu-id="bcc66-224">**Open files with the selected application**—Select this radio button to open the file with an existing application.</span></span> <span data-ttu-id="bcc66-225">從可用應用程式的下拉式清單中選擇應用程式。</span><span class="sxs-lookup"><span data-stu-id="bcc66-225">Choose an application from the drop-down list of available applications.</span></span>

    3.  <span data-ttu-id="bcc66-226">**使用此 OSD 檔案中描述的關聯開啟**檔案-選取此選項按鈕，指定開啟的軟體描述項（OSD）檔案，該檔案會決定用來開啟檔案的應用程式。</span><span class="sxs-lookup"><span data-stu-id="bcc66-226">**Open file with the association described in this OSD file**—Select this radio button to specify an Open Software Descriptor (OSD) file that determines the application used to open the file.</span></span> <span data-ttu-id="bcc66-227">使用 [流覽] 按鈕來選取現有的位置，或是在這個欄位中輸入路徑或 HTTP 格式 URL。</span><span class="sxs-lookup"><span data-stu-id="bcc66-227">Use the browse button to select an existing location, or enter a path or HTTP-formatted URL in this field.</span></span>

## <span data-ttu-id="bcc66-228">如何刪除應用程式 V 應用程式的檔案類型關聯</span><span class="sxs-lookup"><span data-stu-id="bcc66-228">How to delete a file type association for an App-V application</span></span>


<span data-ttu-id="bcc66-229">您可以使用下列程式來刪除檔案類型關聯。</span><span class="sxs-lookup"><span data-stu-id="bcc66-229">You can use the following procedure to delete a file type association.</span></span> <span data-ttu-id="bcc66-230">[**檔案類型關聯**] 節點是 [**範圍**] 窗格中 [**應用程式虛擬化**] 節點下方的一個層級。</span><span class="sxs-lookup"><span data-stu-id="bcc66-230">The **File Type Associations** node is one level below the **Application Virtualization** node in the **Scope** pane.</span></span> <span data-ttu-id="bcc66-231">當您選取這個節點時，[**結果**] 窗格會顯示一份檔案類型關聯性清單。</span><span class="sxs-lookup"><span data-stu-id="bcc66-231">When you select this node, the **Results** pane displays a list of file type associations.</span></span>

**<span data-ttu-id="bcc66-232">移除檔案類型關聯</span><span class="sxs-lookup"><span data-stu-id="bcc66-232">To remove a file type association</span></span>**

1.  <span data-ttu-id="bcc66-233">在 [**結果**] 窗格中，以滑鼠右鍵按一下您要刪除的檔案類型關聯副檔名。</span><span class="sxs-lookup"><span data-stu-id="bcc66-233">In the **Results** pane, right-click the extension of the file type association you want to delete.</span></span>

2.  <span data-ttu-id="bcc66-234">從快顯功能表中選取 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="bcc66-234">Select **Delete** from the pop-up menu.</span></span>

3.  <span data-ttu-id="bcc66-235">按一下 **[是]** 以刪除關聯，或按一下 [**否**]，返回 [**結果**] 窗格。</span><span class="sxs-lookup"><span data-stu-id="bcc66-235">Click **Yes** to delete the association, or click **No** to return to the **Results** pane.</span></span>

## <span data-ttu-id="bcc66-236">相關主題</span><span class="sxs-lookup"><span data-stu-id="bcc66-236">Related topics</span></span>


[<span data-ttu-id="bcc66-237">Application Virtualization Client</span><span class="sxs-lookup"><span data-stu-id="bcc66-237">Application Virtualization Client</span></span>](application-virtualization-client.md)

 

 





