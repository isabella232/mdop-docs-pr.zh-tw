---
title: 提供者原則的結果窗格
description: 提供者原則的結果窗格
author: dansimp
ms.assetid: 17ea0836-bfb5-4966-8778-155444d81e64
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 97e7497617d19c09291104fce237b030a149e743
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800896"
---
# <span data-ttu-id="b41fc-103">提供者原則的結果窗格</span><span class="sxs-lookup"><span data-stu-id="b41fc-103">Provider Policies Results Pane</span></span>


<span data-ttu-id="b41fc-104">應用程式虛擬化伺服器管理主控台中的 [**提供者原則結果**] 窗格會顯示可用的提供者原則清單。</span><span class="sxs-lookup"><span data-stu-id="b41fc-104">The **Provider Policies Results** pane in the Application Virtualization Server Management Console displays a list of the available provider policies.</span></span>

<span data-ttu-id="b41fc-105">以滑鼠右鍵按一下任何提供者原則，以顯示下列元素。</span><span class="sxs-lookup"><span data-stu-id="b41fc-105">Right-click any provider policy to display the following elements.</span></span>

<a href="" id="delete"></a>**<span data-ttu-id="b41fc-106">刪除</span><span class="sxs-lookup"><span data-stu-id="b41fc-106">Delete</span></span>**  
<span data-ttu-id="b41fc-107">這個功能表項目可讓您從 [**結果**] 窗格刪除提供者原則。</span><span class="sxs-lookup"><span data-stu-id="b41fc-107">This menu item enables you to delete a provider policy from the **Results** pane.</span></span>

<a href="" id="rename"></a>**<span data-ttu-id="b41fc-108">重新命名</span><span class="sxs-lookup"><span data-stu-id="b41fc-108">Rename</span></span>**  
<span data-ttu-id="b41fc-109">這個功能表項目可讓您在 [**結果**] 窗格中變更提供者原則的名稱。</span><span class="sxs-lookup"><span data-stu-id="b41fc-109">This menu item enables you to change the name of a provider policy in the **Results** pane.</span></span>

<a href="" id="properties"></a>**<span data-ttu-id="b41fc-110">屬性</span><span class="sxs-lookup"><span data-stu-id="b41fc-110">Properties</span></span>**  
<span data-ttu-id="b41fc-111">此功能表項目會顯示所選提供者原則的 [**屬性**] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="b41fc-111">This menu item displays the **Properties** dialog box for the selected provider policy.</span></span> <span data-ttu-id="b41fc-112">[**屬性**] 對話方塊具有下列索引標籤：</span><span class="sxs-lookup"><span data-stu-id="b41fc-112">The **Properties** dialog box has the following tabs:</span></span>

-   <span data-ttu-id="b41fc-113">**[一般**]-如果您想要從應用程式虛擬化伺服器管理主控台集中管理用戶端桌面的快捷方式，請選取 [使用**管理主控台\*\*\*\*管理用戶端桌面**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b41fc-113">**General**—Enables you to select the **Manage client desktop using the** **Management Console** check box if you want to centrally manage shortcuts on the client desktops from the Application Virtualization Server Management Console.</span></span> <span data-ttu-id="b41fc-114">如果您選擇從主控台管理快速鍵，您可以選取核取方塊以在每次使用者登入時和指定的間隔時重新整理桌面。</span><span class="sxs-lookup"><span data-stu-id="b41fc-114">If you choose to manage shortcuts from the console, you can select check boxes to refresh the desktop every time a user logs in and at intervals you specify.</span></span>

-   <span data-ttu-id="b41fc-115">**群組作業**-可讓您新增及移除指派給提供者原則的使用者群組。</span><span class="sxs-lookup"><span data-stu-id="b41fc-115">**Group Assignment**—Enables you to add and remove user groups assigned to the provider policy.</span></span>

-   <span data-ttu-id="b41fc-116">**提供者管線**-可讓您指定所需的驗證。</span><span class="sxs-lookup"><span data-stu-id="b41fc-116">**Provider Pipeline**—Enables you to specify the authentication required.</span></span>

    -   <span data-ttu-id="b41fc-117">針對 [**強制存取許可權設定**]、[**記錄使用量資訊**] 和 [**授權**] 選取所需的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="b41fc-117">Select the desired check boxes for **Enforce Access Permission Settings**, **Log Usage Information**, and **Licensing**.</span></span> <span data-ttu-id="b41fc-118">如果您選取 [**授權**] 核取方塊，請從下拉式清單中選取 [**只審核授權使用**] 或 [**強制執行授權原則**]。</span><span class="sxs-lookup"><span data-stu-id="b41fc-118">If you select the **Licensing** check box, select **Audit License Usage Only** or **Enforce License Policies** from the drop-down list.</span></span> <span data-ttu-id="b41fc-119">第一個選項會監視授權的使用方式，而第二個選項則嚴格地強制執行您的授權原則。</span><span class="sxs-lookup"><span data-stu-id="b41fc-119">The first option monitors license usage, while the second option strictly enforces your licensing policy.</span></span> <span data-ttu-id="b41fc-120">按一下 **[完成]**，然後閱讀提示，然後按一下 **[確定]** 繼續。</span><span class="sxs-lookup"><span data-stu-id="b41fc-120">Click **Finish**, and then read the prompt and click **OK** to continue.</span></span>

<a href="" id="help"></a>**<span data-ttu-id="b41fc-121">說明</span><span class="sxs-lookup"><span data-stu-id="b41fc-121">Help</span></span>**  
<span data-ttu-id="b41fc-122">顯示應用程式虛擬化伺服器管理主控台的說明系統。</span><span class="sxs-lookup"><span data-stu-id="b41fc-122">Displays the help system for the Application Virtualization Server Management Console.</span></span>

<span data-ttu-id="b41fc-123">在 [**結果**] 窗格中的任何位置按一下滑鼠右鍵（除了提供者原則），以顯示包含下列元素的快顯功能表。</span><span class="sxs-lookup"><span data-stu-id="b41fc-123">Right-click anywhere in the **Results** pane, except on a provider policy, to display a pop-up menu that contains the following elements.</span></span>

<a href="" id="refresh"></a>**<span data-ttu-id="b41fc-124">重新整理</span><span class="sxs-lookup"><span data-stu-id="b41fc-124">Refresh</span></span>**  
<span data-ttu-id="b41fc-125">選取此功能表項目以重新整理提供者原則的視圖。</span><span class="sxs-lookup"><span data-stu-id="b41fc-125">Select this menu item to refresh the view of the provider policies.</span></span>

<a href="" id="export-list"></a>**<span data-ttu-id="b41fc-126">匯出清單</span><span class="sxs-lookup"><span data-stu-id="b41fc-126">Export List</span></span>**  
<span data-ttu-id="b41fc-127">使用此功能表項目，您可以建立一個包含 [**結果**] 窗格內容的 tab 分隔文字檔。</span><span class="sxs-lookup"><span data-stu-id="b41fc-127">With this menu item, you can create a tab-delimited text file that contains the contents of the **Results** pane.</span></span> <span data-ttu-id="b41fc-128">此專案會顯示 [標準檔案**儲存**] 對話方塊，您可以在此指定您要建立之文字檔的位置。</span><span class="sxs-lookup"><span data-stu-id="b41fc-128">This item displays a standard **File Save** dialog box where you specify the location for the text file you are creating.</span></span>

<a href="" id="view"></a>**<span data-ttu-id="b41fc-129">View</span><span class="sxs-lookup"><span data-stu-id="b41fc-129">View</span></span>**  
<span data-ttu-id="b41fc-130">這個功能表項目可以讓您變更 [**結果**] 窗格的外觀和內容。</span><span class="sxs-lookup"><span data-stu-id="b41fc-130">This menu item lets you change the appearance and content of the **Results** pane.</span></span>

<a href="" id="arrange-line-up-icons"></a>**<span data-ttu-id="b41fc-131">[排布]/[對齊] 圖示</span><span class="sxs-lookup"><span data-stu-id="b41fc-131">Arrange/Line Up Icons</span></span>**  
<span data-ttu-id="b41fc-132">這些功能表項目可用來變更圖示在 [**結果**] 窗格中的顯示方式。</span><span class="sxs-lookup"><span data-stu-id="b41fc-132">These menu items can be used to change how the icons are displayed in the **Results** pane.</span></span>

<a href="" id="help"></a>**<span data-ttu-id="b41fc-133">說明</span><span class="sxs-lookup"><span data-stu-id="b41fc-133">Help</span></span>**  
<span data-ttu-id="b41fc-134">顯示應用程式虛擬化伺服器管理主控台的說明系統。</span><span class="sxs-lookup"><span data-stu-id="b41fc-134">Displays the help system of the Application Virtualization Server Management Console.</span></span>

## <span data-ttu-id="b41fc-135">相關主題</span><span class="sxs-lookup"><span data-stu-id="b41fc-135">Related topics</span></span>


[<span data-ttu-id="b41fc-136">伺服器管理主控台：提供者原則節點</span><span class="sxs-lookup"><span data-stu-id="b41fc-136">Server Management Console: Provider Policies Node</span></span>](server-management-console-provider-policies-node.md)

 

 





