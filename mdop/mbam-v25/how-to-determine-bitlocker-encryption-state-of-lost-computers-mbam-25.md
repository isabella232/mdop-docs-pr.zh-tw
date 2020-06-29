---
title: 如何判斷遺失的電腦之 BitLocker 加密狀態
description: 如何判斷遺失的電腦之 BitLocker 加密狀態
author: dansimp
ms.assetid: 4f4bec1b-df3e-40ee-b431-291440268d64
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 95fb843b230804417e375946814a585d1d681634
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810575"
---
# <span data-ttu-id="e37e5-103">如何判斷遺失的電腦之 BitLocker 加密狀態</span><span class="sxs-lookup"><span data-stu-id="e37e5-103">How to Determine BitLocker Encryption State of Lost Computers</span></span>


<span data-ttu-id="e37e5-104">使用此程式與 [管理] 和 [監視] 網站來判斷下列事項：</span><span class="sxs-lookup"><span data-stu-id="e37e5-104">Use this procedure with the Administration and Monitoring Website to determine the following:</span></span>

-   <span data-ttu-id="e37e5-105">遺失或被盜電腦的上次已知 BitLocker 加密狀態</span><span class="sxs-lookup"><span data-stu-id="e37e5-105">The last known BitLocker encryption status of lost or stolen computers</span></span>

-   <span data-ttu-id="e37e5-106">是否已加密遺失或被盜電腦上的卷</span><span class="sxs-lookup"><span data-stu-id="e37e5-106">Whether the volumes on a lost or stolen computer were encrypted</span></span>

<span data-ttu-id="e37e5-107">若要完成這項工作，您需要存取 [管理] 和 [監視] 網站的 [**報告**] 區域。</span><span class="sxs-lookup"><span data-stu-id="e37e5-107">To complete this task, you need access to the **Reports** area of the Administration and Monitoring Website.</span></span> <span data-ttu-id="e37e5-108">若要取得此區域的存取權，您必須獲指派 MBAM Report 使用者角色。</span><span class="sxs-lookup"><span data-stu-id="e37e5-108">To get access to this area, you must be assigned the MBAM Report Users role.</span></span> <span data-ttu-id="e37e5-109">您可能會在建立這些角色時，為它們指定不同的名稱。</span><span class="sxs-lookup"><span data-stu-id="e37e5-109">You may have given these roles different names when you created them.</span></span> <span data-ttu-id="e37e5-110">如需詳細資訊，請參閱[規劃 MBAM 2.5 群組和帳戶](planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles)。</span><span class="sxs-lookup"><span data-stu-id="e37e5-110">For more information, see [Planning for MBAM 2.5 Groups and Accounts](planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles).</span></span>

<span data-ttu-id="e37e5-111">**記事** 裝置合規性是由您的企業已部署的 BitLocker 原則所決定。</span><span class="sxs-lookup"><span data-stu-id="e37e5-111">**Note** Device compliance is determined by the BitLocker policies that your enterprise has deployed.</span></span> <span data-ttu-id="e37e5-112">您可能會想要驗證已部署的原則，然後再嘗試判斷裝置的 BitLocker 加密狀態。</span><span class="sxs-lookup"><span data-stu-id="e37e5-112">You may want to verify your deployed policies before you try to determine the BitLocker encryption state of a device.</span></span>

 

**<span data-ttu-id="e37e5-113">若要判斷遺失的電腦的上次已知 BitLocker 加密狀態</span><span class="sxs-lookup"><span data-stu-id="e37e5-113">To determine the last known BitLocker encryption state of lost computers</span></span>**

1.  <span data-ttu-id="e37e5-114">開啟網頁瀏覽器，然後流覽至 [**管理] 和 [監視] 網站**。</span><span class="sxs-lookup"><span data-stu-id="e37e5-114">Open a web browser and navigate to the **Administration and Monitoring Website**.</span></span>

2.  <span data-ttu-id="e37e5-115">在左窗格中，選取 [**報告**] 以開啟 [報告] 頁面。</span><span class="sxs-lookup"><span data-stu-id="e37e5-115">In the left pane, select **Reports** to open the Reports page.</span></span>

3.  <span data-ttu-id="e37e5-116">選取 [**電腦合規性報告**]。</span><span class="sxs-lookup"><span data-stu-id="e37e5-116">Select the **Computer Compliance Report**.</span></span>

4.  <span data-ttu-id="e37e5-117">使用右窗格中的篩選欄位來縮小搜尋結果的範圍，然後按一下 [**搜尋**]。</span><span class="sxs-lookup"><span data-stu-id="e37e5-117">Use the filter fields in the right pane to narrow the search results, and then click **Search**.</span></span> <span data-ttu-id="e37e5-118">結果會顯示在您的搜尋查詢底下。</span><span class="sxs-lookup"><span data-stu-id="e37e5-118">Results are shown under your search query.</span></span>

5.  <span data-ttu-id="e37e5-119">採取適當的動作，由您的原則決定遺失的裝置。</span><span class="sxs-lookup"><span data-stu-id="e37e5-119">Take the appropriate action, as determined by your policy for lost devices.</span></span>



## <span data-ttu-id="e37e5-120">相關主題</span><span class="sxs-lookup"><span data-stu-id="e37e5-120">Related topics</span></span>


[<span data-ttu-id="e37e5-121">使用 MBAM 2.5 執行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="e37e5-121">Performing BitLocker Management with MBAM 2.5</span></span>](performing-bitlocker-management-with-mbam-25.md)

 
## <span data-ttu-id="e37e5-122">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="e37e5-122">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="e37e5-123">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="e37e5-123">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="e37e5-124">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="e37e5-124">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>
 





