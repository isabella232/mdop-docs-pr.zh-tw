---
title: 發佈伺服器節點
description: 發佈伺服器節點
author: dansimp
ms.assetid: b5823c6c-15bc-4e8d-aeeb-acc366ffedd1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8c001e246c63919773d29a2317d5a43937c0813f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800891"
---
# <span data-ttu-id="0be9a-103">發佈伺服器節點</span><span class="sxs-lookup"><span data-stu-id="0be9a-103">Publishing Servers Node</span></span>


<span data-ttu-id="0be9a-104">[**發佈伺服器**] 節點是應用程式虛擬化用戶端管理主控台**範圍**窗格中 [**應用程式虛擬化**] 節點下方的一個層級。</span><span class="sxs-lookup"><span data-stu-id="0be9a-104">The **Publishing Servers** node is one level below the **Application Virtualization** node in the **Scope** pane of the Application Virtualization Client Management Console.</span></span> <span data-ttu-id="0be9a-105">當您選取這個節點時，[**結果**] 窗格會顯示發佈伺服器的清單。</span><span class="sxs-lookup"><span data-stu-id="0be9a-105">When you select this node, the **Results** pane displays a list of publishing servers.</span></span>

<span data-ttu-id="0be9a-106">以滑鼠右鍵按一下 [**發佈伺服器**] 節點，以顯示包含下列元素的快顯功能表。</span><span class="sxs-lookup"><span data-stu-id="0be9a-106">Right-click the **Publishing Servers** node to display a pop-up menu that contains the following elements.</span></span>

<a href="" id="new-server"></a>**<span data-ttu-id="0be9a-107">新伺服器</span><span class="sxs-lookup"><span data-stu-id="0be9a-107">New Server</span></span>**  
<span data-ttu-id="0be9a-108">此功能表項目會顯示 [新增伺服器] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="0be9a-108">This menu item displays the New Server Wizard.</span></span> <span data-ttu-id="0be9a-109">此嚮導包含兩個頁面：</span><span class="sxs-lookup"><span data-stu-id="0be9a-109">This wizard consists of two pages:</span></span>

1.  <span data-ttu-id="0be9a-110">輸入伺服器顯示名稱和伺服器類型：</span><span class="sxs-lookup"><span data-stu-id="0be9a-110">Enter a server display name and server type:</span></span>

    -   <span data-ttu-id="0be9a-111">[**顯示名稱**]-輸入您想要為伺服器顯示的名稱。</span><span class="sxs-lookup"><span data-stu-id="0be9a-111">**Display Name**—Enter a name that you want displayed for the server.</span></span> <span data-ttu-id="0be9a-112">此欄位預設為空白。</span><span class="sxs-lookup"><span data-stu-id="0be9a-112">This field is blank by default.</span></span>

    -   <span data-ttu-id="0be9a-113">**類型**—從伺服器類型的下拉式清單中，選擇 [伺服器類型]。</span><span class="sxs-lookup"><span data-stu-id="0be9a-113">**Type**—Choose the server type from the drop-down list of server types.</span></span>

2.  <span data-ttu-id="0be9a-114">指定伺服器的連線設定：</span><span class="sxs-lookup"><span data-stu-id="0be9a-114">Specify the connection settings for the server:</span></span>

    -   <span data-ttu-id="0be9a-115">[**主機名稱**]-輸入伺服器的名稱或 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="0be9a-115">**Host Name**—Enter the name or IP address for the server.</span></span>

    -   <span data-ttu-id="0be9a-116">**Port （埠**）-輸入與埠號碼相對應的數值。</span><span class="sxs-lookup"><span data-stu-id="0be9a-116">**Port**—Enter a numeric value that corresponds to the port number.</span></span> <span data-ttu-id="0be9a-117">如果伺服器類型是「應用程式虛擬化伺服器」，則預設值為 554; 如果伺服器類型是「標準 HTTP 伺服器」，則為80。</span><span class="sxs-lookup"><span data-stu-id="0be9a-117">The default value is 554 if the server type is "Application Virtualization Server" and 80 if the server type is "Standard HTTP Server."</span></span>

    -   <span data-ttu-id="0be9a-118">**路徑**：此欄位預設為 "/"，且在伺服器類型為「Application Virtualization server」或「增強的安全性應用程式虛擬化伺服器」時是唯讀的。</span><span class="sxs-lookup"><span data-stu-id="0be9a-118">**Path**—This field defaults to "/" and is read-only when the server type is "Application Virtualization Server" or “Enhanced Security Application Virtualization Server”.</span></span> <span data-ttu-id="0be9a-119">當伺服器類型是「標準 HTTP 伺服器」或「增強的安全性 HTTP 伺服器」時，**路徑**欄位也是可編輯的。</span><span class="sxs-lookup"><span data-stu-id="0be9a-119">When the server type is “Standard HTTP Server” or “Enhanced Security HTTP Server”, the **Path** field is also editable.</span></span>

<a href="" id="new-window-from-here"></a>**<span data-ttu-id="0be9a-120">從這裡新增視窗</span><span class="sxs-lookup"><span data-stu-id="0be9a-120">New Window from Here</span></span>**  
<span data-ttu-id="0be9a-121">選取此功能表項目以開啟新的管理主控台，並將選取的節點做為根節點。</span><span class="sxs-lookup"><span data-stu-id="0be9a-121">Select this menu item to open a new management console with the selected node as the root node.</span></span>

<a href="" id="export-list"></a>**<span data-ttu-id="0be9a-122">匯出清單</span><span class="sxs-lookup"><span data-stu-id="0be9a-122">Export List</span></span>**  
<span data-ttu-id="0be9a-123">您可以使用這個功能表項目來建立包含 [**結果**] 窗格內容的 tab 分隔文字檔。</span><span class="sxs-lookup"><span data-stu-id="0be9a-123">You can use this menu item to create a tab-delimited text file that contains the contents of the **Results** pane.</span></span> <span data-ttu-id="0be9a-124">此專案會顯示 [標準檔案**儲存**] 對話方塊，您可以在此指定您要建立之文字檔的位置。</span><span class="sxs-lookup"><span data-stu-id="0be9a-124">This item displays a standard **File Save** dialog box where you specify the location for the text file you are creating.</span></span>

<a href="" id="view"></a>**<span data-ttu-id="0be9a-125">View</span><span class="sxs-lookup"><span data-stu-id="0be9a-125">View</span></span>**  
<span data-ttu-id="0be9a-126">此快顯功能表專案清單可讓您變更 [**結果**] 窗格的外觀和內容。</span><span class="sxs-lookup"><span data-stu-id="0be9a-126">This pop-up list of menu items enables you to change the appearance and content of the **Results** pane.</span></span>

<a href="" id="refresh"></a>**<span data-ttu-id="0be9a-127">重新整理</span><span class="sxs-lookup"><span data-stu-id="0be9a-127">Refresh</span></span>**  
<span data-ttu-id="0be9a-128">選取此專案以重新整理管理主控台。</span><span class="sxs-lookup"><span data-stu-id="0be9a-128">Select this item to refresh the management console.</span></span>

<a href="" id="help"></a>**<span data-ttu-id="0be9a-129">說明</span><span class="sxs-lookup"><span data-stu-id="0be9a-129">Help</span></span>**  
<span data-ttu-id="0be9a-130">此專案會顯示管理主控台的說明系統。</span><span class="sxs-lookup"><span data-stu-id="0be9a-130">This item displays the help system for the management console.</span></span>

## <span data-ttu-id="0be9a-131">相關主題</span><span class="sxs-lookup"><span data-stu-id="0be9a-131">Related topics</span></span>


[<span data-ttu-id="0be9a-132">發佈伺服器的結果窗格</span><span class="sxs-lookup"><span data-stu-id="0be9a-132">Publishing Servers Results Pane</span></span>](publishing-servers-results-pane.md)

[<span data-ttu-id="0be9a-133">發佈伺服器的結果窗格欄</span><span class="sxs-lookup"><span data-stu-id="0be9a-133">Publishing Servers Results Pane Columns</span></span>](publishing-servers-results-pane-columns.md)

 

 





