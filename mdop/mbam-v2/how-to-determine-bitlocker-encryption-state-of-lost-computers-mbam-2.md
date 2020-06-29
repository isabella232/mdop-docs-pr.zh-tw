---
title: 如何判斷遺失的電腦之 BitLocker 加密狀態
description: 如何判斷遺失的電腦之 BitLocker 加密狀態
author: dansimp
ms.assetid: dbd23b64-dff3-4913-9acd-affe67b9462e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b9ea4afd6dd08f2040b9e2bd1e1a8998181d1e60
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810659"
---
# <span data-ttu-id="19330-103">如何判斷遺失的電腦之 BitLocker 加密狀態</span><span class="sxs-lookup"><span data-stu-id="19330-103">How to Determine BitLocker Encryption State of Lost Computers</span></span>


<span data-ttu-id="19330-104">您可以使用 Microsoft BitLocker 管理和監控（MBAM）來判斷遺失或被盜電腦的最近已知 BitLocker 加密狀態。</span><span class="sxs-lookup"><span data-stu-id="19330-104">You can use Microsoft BitLocker Administration and Monitoring (MBAM) to determine the last known BitLocker encryption status of computers that were lost or stolen.</span></span> <span data-ttu-id="19330-105">下列程式說明如何在發生遺失或失竊情況時，判斷電腦上的卷是否已加密。</span><span class="sxs-lookup"><span data-stu-id="19330-105">The following procedure explains how to determine whether the volumes on a computer are encrypted if there is a loss or theft.</span></span>

**<span data-ttu-id="19330-106">若要判斷遺失的電腦的上次已知 BitLocker 加密狀態</span><span class="sxs-lookup"><span data-stu-id="19330-106">To determine the last known BitLocker encryption state of lost computers</span></span>**

1.  <span data-ttu-id="19330-107">開啟網頁瀏覽器，然後流覽至 [管理] 和 [監視] 網站。</span><span class="sxs-lookup"><span data-stu-id="19330-107">Open a web browser and navigate to the Administration and Monitoring website.</span></span>

    <span data-ttu-id="19330-108">**記事** 注意： [管理] 和 [監視] 網站的預設位址是 HTTP://\* &lt; computername &gt; \*。</span><span class="sxs-lookup"><span data-stu-id="19330-108">**Note** Note: The default address for the Administration and Monitoring website is http://*&lt;computername&gt;*.</span></span> <span data-ttu-id="19330-109">使用完全限定的伺服器名稱將會產生更快的流覽結果。</span><span class="sxs-lookup"><span data-stu-id="19330-109">Using the fully qualified server name will yield faster browsing results.</span></span>

     

2.  <span data-ttu-id="19330-110">從 [功能窗格] 中選取 [**報表**] 節點，然後選取 [**電腦合規性報告**]。</span><span class="sxs-lookup"><span data-stu-id="19330-110">Selects the **Report** node from the navigation pane, and select the **Computer Compliance Report**.</span></span>

3.  <span data-ttu-id="19330-111">使用右窗格中的篩選欄位來縮小搜尋結果的範圍，然後按一下 [**搜尋**]。</span><span class="sxs-lookup"><span data-stu-id="19330-111">Use the filter fields in the right pane to narrow the search results, and then click **Search**.</span></span> <span data-ttu-id="19330-112">結果會顯示在您的搜尋查詢下方。</span><span class="sxs-lookup"><span data-stu-id="19330-112">Results are shown below your search query.</span></span>

4.  <span data-ttu-id="19330-113">採取適當的動作，由您的原則決定遺失的裝置。</span><span class="sxs-lookup"><span data-stu-id="19330-113">Take the appropriate action, as determined by your policy for lost devices.</span></span>

    <span data-ttu-id="19330-114">**記事** 裝置合規性是由您的企業已部署的 BitLocker 原則所決定。</span><span class="sxs-lookup"><span data-stu-id="19330-114">**Note** Device compliance is determined by the BitLocker policies that your enterprise has deployed.</span></span> <span data-ttu-id="19330-115">您可能會想要驗證已部署的原則，然後再嘗試判斷裝置的 BitLocker 加密狀態。</span><span class="sxs-lookup"><span data-stu-id="19330-115">You may want to verify your deployed policies before you try to determine the BitLocker encryption state of a device.</span></span>

     

## <span data-ttu-id="19330-116">相關主題</span><span class="sxs-lookup"><span data-stu-id="19330-116">Related topics</span></span>


[<span data-ttu-id="19330-117">使用 MBAM 執行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="19330-117">Performing BitLocker Management with MBAM</span></span>](performing-bitlocker-management-with-mbam-mbam-2.md)

 

 





