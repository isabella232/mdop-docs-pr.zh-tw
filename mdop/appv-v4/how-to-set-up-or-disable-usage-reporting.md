---
title: 如何設定或停用使用量報告
description: 如何設定或停用使用量報告
author: dansimp
ms.assetid: 8587003a-128d-4b5d-ac70-5b9eddddd3dc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3f8f6c44d4060581f1ebe435875bc2f105cb93d6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801061"
---
# <span data-ttu-id="750f9-103">如何設定或停用使用量報告</span><span class="sxs-lookup"><span data-stu-id="750f9-103">How to Set Up or Disable Usage Reporting</span></span>


<span data-ttu-id="750f9-104">您可以在應用程式虛擬化伺服器管理主控台中使用下列程式，以指定您想要儲存在資料庫中之應用程式虛擬化系統使用量資訊的持續時間（以月為單位）。</span><span class="sxs-lookup"><span data-stu-id="750f9-104">You can use the following procedures in the Application Virtualization Server Management Console to specify the duration (in months) of Application Virtualization System usage information you want to store in the database.</span></span>

<span data-ttu-id="750f9-105">**記事** 若要儲存使用資訊，您必須在 [**提供者管道**] 索引標籤上選取 [**記錄使用量資訊**] 核取方塊。若要顯示此索引標籤，請以滑鼠右鍵按一下 [**提供者原則結果**] 窗格中的提供者原則，然後選取 [**屬性**]</span><span class="sxs-lookup"><span data-stu-id="750f9-105">**Note** To store usage information, you must select the **Log Usage Information** check box on the **Provider Pipeline** tab. To display this tab, right-click the provider policy in the **Provider Policies Results** pane and select **Properties**.</span></span>

 

**<span data-ttu-id="750f9-106">設定使用狀況報告</span><span class="sxs-lookup"><span data-stu-id="750f9-106">To set up usage reporting</span></span>**

1.  <span data-ttu-id="750f9-107">以滑鼠右鍵按一下左窗格中的 [應用程式虛擬化系統] 節點，然後選取 [**系統選項**]。</span><span class="sxs-lookup"><span data-stu-id="750f9-107">Right-click the Application Virtualization System node in the left pane, and select **System Options**.</span></span>

2.  <span data-ttu-id="750f9-108">選取 [**資料庫**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="750f9-108">Select the **Database** tab.</span></span>

3.  <span data-ttu-id="750f9-109">選取 [**保留使用時間（月）** ] 或 [**保留所有使用方式**] 選項按鈕。</span><span class="sxs-lookup"><span data-stu-id="750f9-109">Select the **Keep Usage For (Months)** or **Keep All Usage** radio button.</span></span>

4.  <span data-ttu-id="750f9-110">如果您選擇指定使用時間（以月為單位），請輸入1到120之間的數位（預設值是6個月）。</span><span class="sxs-lookup"><span data-stu-id="750f9-110">If you choose to specify usage duration in months, enter a number from 1 to 120 (default value is 6 months).</span></span> <span data-ttu-id="750f9-111">如果您選取 [**保留所有使用方式**]，資料庫將會持續增長，直到達到指定的大小限制為止。</span><span class="sxs-lookup"><span data-stu-id="750f9-111">If you select **Keep All Usage**, the database will grow until it reaches the specified size limit.</span></span>

5.  <span data-ttu-id="750f9-112">按一下**Apply** [套用 **] 或 [確定]**。</span><span class="sxs-lookup"><span data-stu-id="750f9-112">Click **Apply** or **OK**.</span></span>

**<span data-ttu-id="750f9-113">停用使用方式報告</span><span class="sxs-lookup"><span data-stu-id="750f9-113">To disable usage reporting</span></span>**

1.  <span data-ttu-id="750f9-114">按一下 [**提供者原則**] 節點。</span><span class="sxs-lookup"><span data-stu-id="750f9-114">Click the **Provider Policies** node.</span></span>

2.  <span data-ttu-id="750f9-115">以滑鼠右鍵按一下 [**提供者原則**]，然後選取 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="750f9-115">Right-click **Provider Policy** and select **Properties**.</span></span>

3.  <span data-ttu-id="750f9-116">選取 [**提供者管線**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="750f9-116">Select the **Provider Pipeline** tab.</span></span>

4.  <span data-ttu-id="750f9-117">清除 [**記錄使用量資訊**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="750f9-117">Clear the **Log Usage Information** check box.</span></span>

5.  <span data-ttu-id="750f9-118">按一下**Apply** [套用 **] 或 [確定]**。</span><span class="sxs-lookup"><span data-stu-id="750f9-118">Click **Apply** or **OK**.</span></span>

## <span data-ttu-id="750f9-119">相關主題</span><span class="sxs-lookup"><span data-stu-id="750f9-119">Related topics</span></span>


[<span data-ttu-id="750f9-120">如何在伺服器管理主控台中自訂 Application Virtualization 系統</span><span class="sxs-lookup"><span data-stu-id="750f9-120">How to Customize an Application Virtualization System in the Server Management Console</span></span>](how-to-customize-an-application-virtualization-system-in-the-server-management-console.md)

[<span data-ttu-id="750f9-121">如何設定或停用資料庫大小</span><span class="sxs-lookup"><span data-stu-id="750f9-121">How to Set Up or Disable Database Size</span></span>](how-to-set-up-or-disable-database-size.md)

 

 





