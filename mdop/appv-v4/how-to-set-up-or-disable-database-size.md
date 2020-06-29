---
title: 如何設定或停用資料庫大小
description: 如何設定或停用資料庫大小
author: dansimp
ms.assetid: 4abaf349-132d-4186-8873-a0e515593b93
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cbb041920e2680d51b01926f144eba595fe28d05
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801066"
---
# <span data-ttu-id="2e14e-103">如何設定或停用資料庫大小</span><span class="sxs-lookup"><span data-stu-id="2e14e-103">How to Set Up or Disable Database Size</span></span>


<span data-ttu-id="2e14e-104">您可以在應用程式虛擬化伺服器管理主控台中使用下列程式，以指定您想要儲存在資料庫中的應用程式虛擬化系統使用量大小（以 MB 為單位）。</span><span class="sxs-lookup"><span data-stu-id="2e14e-104">You can use the following procedures in the Application Virtualization Server Management Console to specify the size (in MB) of Application Virtualization System usage that you want to store in the database.</span></span>

<span data-ttu-id="2e14e-105">當所儲存資料的大小達到指定限制的95% （高水位線）時，系統會刪除10% 的使用量資料，並將85% 的資料留在一起。</span><span class="sxs-lookup"><span data-stu-id="2e14e-105">When the size of the stored data reaches 95% (the high watermark) of the specified limit, the system will delete 10% of the usage data, leaving 85% of the data.</span></span> <span data-ttu-id="2e14e-106">隨即會刪除套件和應用程式的使用資料。</span><span class="sxs-lookup"><span data-stu-id="2e14e-106">Package and application usage data will be deleted.</span></span> <span data-ttu-id="2e14e-107">當資料庫增長足夠大且接近高水位線時，系統會傳送一則警告訊息給 SQL Server 記錄，通知您已達到此限制。</span><span class="sxs-lookup"><span data-stu-id="2e14e-107">When the database grows large enough and approaches the high watermark, a warning message is sent to the SQL Server log to inform you that this limit has been reached.</span></span> <span data-ttu-id="2e14e-108">此警告是必要的，因為清除動作可能會影響報表的輸出。</span><span class="sxs-lookup"><span data-stu-id="2e14e-108">This warning is necessary because the cleanup action can affect the output of the reports.</span></span> <span data-ttu-id="2e14e-109">它也可協助您決定是否要增加最大資料庫大小、減少要保留的使用資料月份數，或關閉記錄層級。</span><span class="sxs-lookup"><span data-stu-id="2e14e-109">It will also help you decide whether you need to increase the maximum database size, reduce the number of months of usage data to be kept, or turn down the logging level.</span></span>

<span data-ttu-id="2e14e-110">**記事** [**無大小限制**] 和 [**保留所有使用方式**] 選項，因此您可以停用使用方式報告和資料庫清理。</span><span class="sxs-lookup"><span data-stu-id="2e14e-110">**Note** The **No Size Limit** and **Keep All Usage** options are provided so that you can disable usage reporting and database cleanup.</span></span> <span data-ttu-id="2e14e-111">選取這些專案將會同時清除資料庫事務記錄記錄。</span><span class="sxs-lookup"><span data-stu-id="2e14e-111">Selecting these items will clean up the database transaction log as well.</span></span> <span data-ttu-id="2e14e-112">（所有已提交的 Microsoft SQL Server 事務將會從資料庫記錄中移除）。</span><span class="sxs-lookup"><span data-stu-id="2e14e-112">(All committed Microsoft SQL Server transactions will be removed from the database log.)</span></span>

 

**<span data-ttu-id="2e14e-113">設定資料庫大小</span><span class="sxs-lookup"><span data-stu-id="2e14e-113">To set up database size</span></span>**

1.  <span data-ttu-id="2e14e-114">以滑鼠右鍵按一下左窗格中的 [應用程式虛擬化系統] 節點，然後選取 [**系統選項**]。</span><span class="sxs-lookup"><span data-stu-id="2e14e-114">Right-click the Application Virtualization System node in the left pane, and select **System Options**.</span></span>

2.  <span data-ttu-id="2e14e-115">選取 [**資料庫**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="2e14e-115">Select the **Database** tab.</span></span>

3.  <span data-ttu-id="2e14e-116">選取 [**資料庫大小上限（MB）** ] 或 [**無大小限制**] 選項按鈕。</span><span class="sxs-lookup"><span data-stu-id="2e14e-116">Select the **Maximum Database Size (MB)** or **No Size Limit** radio button.</span></span>

4.  <span data-ttu-id="2e14e-117">如果您選擇指定資料庫大小，最佳做法建議您輸入介於512和 4096 MB 之間的數位。</span><span class="sxs-lookup"><span data-stu-id="2e14e-117">If you choose to specify a database size, best practices recommend that you enter a number between 512 and 4096 MB.</span></span> <span data-ttu-id="2e14e-118">預設大小為 1024 MB，如果您需要增加資料庫大小，您可以輸入的最大值為2147483647。</span><span class="sxs-lookup"><span data-stu-id="2e14e-118">The default size is 1024 MB and if you need to increase the database size, the maximum value you can enter is 2,147,483,647.</span></span> <span data-ttu-id="2e14e-119">如果您選取 [**無大小限制**]，資料庫將會增長，直到達到磁片大小限制為止。</span><span class="sxs-lookup"><span data-stu-id="2e14e-119">If you select **No Size Limit**, the database will grow until it reaches the disk size limit.</span></span>

5.  <span data-ttu-id="2e14e-120">按一下**Apply** [套用 **] 或 [確定]**。</span><span class="sxs-lookup"><span data-stu-id="2e14e-120">Click **Apply** or **OK**.</span></span>

**<span data-ttu-id="2e14e-121">若要停用資料庫大小限制</span><span class="sxs-lookup"><span data-stu-id="2e14e-121">To disable database size limits</span></span>**

1.  <span data-ttu-id="2e14e-122">以滑鼠右鍵按一下 [**範圍**] 窗格中的 [應用程式虛擬化系統] 節點，然後選取 [**系統選項**]。</span><span class="sxs-lookup"><span data-stu-id="2e14e-122">Right-click the Application Virtualization System node in the **Scope** pane, and select **System Options**.</span></span>

2.  <span data-ttu-id="2e14e-123">選取 [**資料庫**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="2e14e-123">Select the **Database** tab.</span></span>

3.  <span data-ttu-id="2e14e-124">選取 [**無大小限制**]，然後**保留 [所有使用方式**] 選項按鈕。</span><span class="sxs-lookup"><span data-stu-id="2e14e-124">Select the **No Size Limit** and **Keep All Usage** radio buttons.</span></span>

4.  <span data-ttu-id="2e14e-125">按一下**Apply** [套用 **] 或 [確定]**。</span><span class="sxs-lookup"><span data-stu-id="2e14e-125">Click **Apply** or **OK**.</span></span>

## <span data-ttu-id="2e14e-126">相關主題</span><span class="sxs-lookup"><span data-stu-id="2e14e-126">Related topics</span></span>


[<span data-ttu-id="2e14e-127">如何在伺服器管理主控台中自訂 Application Virtualization 系統</span><span class="sxs-lookup"><span data-stu-id="2e14e-127">How to Customize an Application Virtualization System in the Server Management Console</span></span>](how-to-customize-an-application-virtualization-system-in-the-server-management-console.md)

[<span data-ttu-id="2e14e-128">如何設定或停用使用量報告</span><span class="sxs-lookup"><span data-stu-id="2e14e-128">How to Set Up or Disable Usage Reporting</span></span>](how-to-set-up-or-disable-usage-reporting.md)

 

 





