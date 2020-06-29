---
title: 提供者原則節點
description: 提供者原則節點
author: dansimp
ms.assetid: 89b47076-7732-4128-93cc-8e6d5b671c8e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 221171b22471a4a8614b13023b24dd21fd571dd3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800898"
---
# <span data-ttu-id="de67b-103">提供者原則節點</span><span class="sxs-lookup"><span data-stu-id="de67b-103">Provider Policies Node</span></span>


<span data-ttu-id="de67b-104">[**提供者原則**] 節點是應用程式虛擬化伺服器管理主控台**範圍**窗格中 [應用程式虛擬化系統] 節點下方的一個層級。</span><span class="sxs-lookup"><span data-stu-id="de67b-104">The **Provider Policies** node is one level below the Application Virtualization System node in the **Scope** pane in the Application Virtualization Server Management Console.</span></span> <span data-ttu-id="de67b-105">當您選取此節點時，[**結果**] 窗格會顯示提供者原則的清單。</span><span class="sxs-lookup"><span data-stu-id="de67b-105">When you select this node, the **Results** pane displays a list of provider policies.</span></span> <span data-ttu-id="de67b-106">以滑鼠右鍵按一下 [**提供者原則**] 節點，以顯示包含下列元素的快顯功能表。</span><span class="sxs-lookup"><span data-stu-id="de67b-106">Right-click the **Provider Policies** node to display a pop-up menu that contains the following elements.</span></span>

<a href="" id="new-provider-policy"></a>**<span data-ttu-id="de67b-107">新的提供者原則</span><span class="sxs-lookup"><span data-stu-id="de67b-107">New Provider Policy</span></span>**  
<span data-ttu-id="de67b-108">顯示 [新增提供者原則] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="de67b-108">Displays the New Provider Policy Wizard.</span></span> <span data-ttu-id="de67b-109">此嚮導包含下列頁面：</span><span class="sxs-lookup"><span data-stu-id="de67b-109">This wizard consists of the following pages:</span></span>

1.  <span data-ttu-id="de67b-110">在 [**提供者原則名稱**] 欄位中輸入名稱。</span><span class="sxs-lookup"><span data-stu-id="de67b-110">Enter a name in the **Provider Policy Name** field.</span></span> <span data-ttu-id="de67b-111">如果您想要這項功能，請選取 [**使用管理主控台管理用戶端桌面**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="de67b-111">Select the **Manage client desktop using the Management Console** check box if you want that capability.</span></span> <span data-ttu-id="de67b-112">如果您想要相關聯的功能，請選取下列其中一項或兩項核取方塊：</span><span class="sxs-lookup"><span data-stu-id="de67b-112">Select one or both of the following check boxes if you want the associated functionality:</span></span>

    -   **<span data-ttu-id="de67b-113">在使用者登入時更新發佈設定</span><span class="sxs-lookup"><span data-stu-id="de67b-113">Refresh publishing configuration when a user logs in</span></span>**

    -   <span data-ttu-id="de67b-114">**每次更新**設定。</span><span class="sxs-lookup"><span data-stu-id="de67b-114">**Refresh configuration every**.</span></span> <span data-ttu-id="de67b-115">選取此選項後，請輸入數位，然後從下拉式功能表中選取單位。</span><span class="sxs-lookup"><span data-stu-id="de67b-115">After selecting this option, enter a number and select the unit from the drop-down menu.</span></span> <span data-ttu-id="de67b-116">有效的專案範圍是從最短**30 分鐘**到最大**999 天**。</span><span class="sxs-lookup"><span data-stu-id="de67b-116">Valid entries range from a minimum of **30 minutes** to a maximum of **999 days**.</span></span>

2.  <span data-ttu-id="de67b-117">按一下 [**新增**] 或 [**移除**] 以新增或移除群組作業。</span><span class="sxs-lookup"><span data-stu-id="de67b-117">Click **Add** or **Remove** to add or remove a group assignment.</span></span> <span data-ttu-id="de67b-118">使用標準的**Windows [流覽**] 對話方塊來尋找使用者群組。</span><span class="sxs-lookup"><span data-stu-id="de67b-118">Use the standard **Windows Browse** dialog box to find a user group.</span></span>

3.  <span data-ttu-id="de67b-119">在 [**提供者管道**設定] 對話方塊中選取下列其中一個核取方塊，以啟用相關聯的功能：</span><span class="sxs-lookup"><span data-stu-id="de67b-119">Select one of the following check boxes on the **Provider Pipeline Configuration** dialog box to enable the associated feature:</span></span>

    -   <span data-ttu-id="de67b-120">**驗證**-從下拉式清單中選取驗證類型。</span><span class="sxs-lookup"><span data-stu-id="de67b-120">**Authentication**—Select the type of authentication from the drop-down list.</span></span>

    -   **<span data-ttu-id="de67b-121">強制執行存取許可權設定</span><span class="sxs-lookup"><span data-stu-id="de67b-121">Enforce Access Permission Settings</span></span>**

    -   **<span data-ttu-id="de67b-122">記錄使用量資訊</span><span class="sxs-lookup"><span data-stu-id="de67b-122">Log Usage Information</span></span>**

    -   <span data-ttu-id="de67b-123">[**授權**]-從下拉式清單中選取 [強制配置]。</span><span class="sxs-lookup"><span data-stu-id="de67b-123">**Licensing**—Select an enforcement scheme from the drop-down list.</span></span>

4.  <span data-ttu-id="de67b-124">按一下 **[完成]** 以新增新的提供者原則。</span><span class="sxs-lookup"><span data-stu-id="de67b-124">Click **Finish** to add the new provider policy.</span></span>

<a href="" id="view"></a>**<span data-ttu-id="de67b-125">View</span><span class="sxs-lookup"><span data-stu-id="de67b-125">View</span></span>**  
<span data-ttu-id="de67b-126">變更 [**結果**] 窗格的外觀和內容。</span><span class="sxs-lookup"><span data-stu-id="de67b-126">Changes the appearance and content of the **Results** pane.</span></span>

<a href="" id="new-window-from-here"></a>**<span data-ttu-id="de67b-127">從這裡新增視窗</span><span class="sxs-lookup"><span data-stu-id="de67b-127">New Window from Here</span></span>**  
<span data-ttu-id="de67b-128">開啟新的管理主控台，並將選取的節點做為根節點。</span><span class="sxs-lookup"><span data-stu-id="de67b-128">Opens a new management console with the selected node as the root node.</span></span>

<a href="" id="refresh"></a>**<span data-ttu-id="de67b-129">重新整理</span><span class="sxs-lookup"><span data-stu-id="de67b-129">Refresh</span></span>**  
<span data-ttu-id="de67b-130">刷新伺服器的視圖。</span><span class="sxs-lookup"><span data-stu-id="de67b-130">Refreshes the view of the server.</span></span>

<a href="" id="export-list"></a>**<span data-ttu-id="de67b-131">匯出清單</span><span class="sxs-lookup"><span data-stu-id="de67b-131">Export List</span></span>**  
<span data-ttu-id="de67b-132">建立包含 [**結果**] 窗格內容的定位字元分隔文字檔。</span><span class="sxs-lookup"><span data-stu-id="de67b-132">Creates a tab-delimited text file that contains the contents of the **Results** pane.</span></span> <span data-ttu-id="de67b-133">此專案會顯示 [標準檔案**儲存**] 對話方塊，您可以在此指定您要建立之文字檔的位置。</span><span class="sxs-lookup"><span data-stu-id="de67b-133">This item displays a standard **File Save** dialog box where you specify the location for the text file you are creating.</span></span>

<a href="" id="help"></a>**<span data-ttu-id="de67b-134">說明</span><span class="sxs-lookup"><span data-stu-id="de67b-134">Help</span></span>**  
<span data-ttu-id="de67b-135">顯示應用程式虛擬化伺服器管理主控台的說明系統。</span><span class="sxs-lookup"><span data-stu-id="de67b-135">Displays the help system for the Application Virtualization Server Management Console.</span></span>

## <span data-ttu-id="de67b-136">相關主題</span><span class="sxs-lookup"><span data-stu-id="de67b-136">Related topics</span></span>


[<span data-ttu-id="de67b-137">伺服器管理主控台：提供者原則節點</span><span class="sxs-lookup"><span data-stu-id="de67b-137">Server Management Console: Provider Policies Node</span></span>](server-management-console-provider-policies-node.md)

 

 





