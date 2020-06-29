---
title: 隱藏控制台中預設的 BitLocker 磁碟機加密項目
description: 隱藏控制台中預設的 BitLocker 磁碟機加密項目
author: dansimp
ms.assetid: 6e2a9a02-a809-43a1-80a3-1b03c7192c89
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: af395928ca8934bfea4eeb848bbd4ee377987293
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809752"
---
# <span data-ttu-id="d64f6-103">隱藏控制台中預設的 BitLocker 磁碟機加密項目</span><span class="sxs-lookup"><span data-stu-id="d64f6-103">Hiding the Default BitLocker Drive Encryption Item in Control Panel</span></span>


<span data-ttu-id="d64f6-104">本主題描述如何隱藏 [ **BitLocker 磁碟機加密**] 控制台專案，該專案預設會顯示在 [控制台] 中，成為 Windows 作業系統的一部分。</span><span class="sxs-lookup"><span data-stu-id="d64f6-104">This topic describes how to hide the **BitLocker Drive Encryption** Control Panel item, which appears by default on Control Panel as part of the Windows operating system.</span></span>

<span data-ttu-id="d64f6-105">**記事** Microsoft BitLocker 管理和監控（MBAM）會建立另一個自訂的 [控制台] 專案（稱為 [ **BitLocker 加密選項**]），讓使用者能夠管理其 PIN 與密碼、開啟磁片磁碟機的 BitLocker，以及檢查加密。</span><span class="sxs-lookup"><span data-stu-id="d64f6-105">**Note** Microsoft BitLocker Administration and Monitoring (MBAM) creates an additional, custom Control Panel item, called **BitLocker Encryption Options**, which enables end users to manage their PIN and password, turn on BitLocker for a drive, and check encryption.</span></span>

 

<span data-ttu-id="d64f6-106">請參閱[瞭解 [控制台] 中的 [Bitlocker 加密選項] 和 [Bitlocker 磁片磁碟機加密專案](understanding-the-bitlocker-encryption-options-and-bitlocker-drive-encryption-items-in-control-panel.md)]，瞭解：</span><span class="sxs-lookup"><span data-stu-id="d64f6-106">See [Understanding the BitLocker Encryption Options and BitLocker Drive Encryption Items in Control Panel](understanding-the-bitlocker-encryption-options-and-bitlocker-drive-encryption-items-in-control-panel.md) to read about:</span></span>

-   <span data-ttu-id="d64f6-107">MBAM 和預設 [控制台] 專案間的差異</span><span class="sxs-lookup"><span data-stu-id="d64f6-107">Differences between the MBAM and the default Control Panel items</span></span>

-   <span data-ttu-id="d64f6-108">**管理**當您以滑鼠右鍵按一下 Windows 資源管理器中的磁片磁碟機時所顯示的 BitLocker 快捷方式功能表</span><span class="sxs-lookup"><span data-stu-id="d64f6-108">**Manage BitLocker** shortcut menu that appears when you right-click a drive in Windows Explorer</span></span>

<span data-ttu-id="d64f6-109">**重要** 請勿變更**BitLocker 磁片磁碟機加密**節點中的群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="d64f6-109">**Important** Do not change the Group Policy settings in the **BitLocker Drive Encryption** node.</span></span> <span data-ttu-id="d64f6-110">如果您這樣做，MBAM 將無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="d64f6-110">If you do, MBAM will not work correctly.</span></span> <span data-ttu-id="d64f6-111">當您在**MDOP MBAM （BitLocker 管理）** 節點中設定群組原則設定時，MBAM 會自動為您設定**BitLocker 磁片磁碟機加密**設定。</span><span class="sxs-lookup"><span data-stu-id="d64f6-111">When you configure the Group Policy settings in the **MDOP MBAM (BitLocker Management)** node, MBAM automatically configures the **BitLocker Drive Encryption** settings for you.</span></span>

 

**<span data-ttu-id="d64f6-112">若要在 [控制台] 中隱藏預設的 BitLocker 磁片磁碟機加密專案</span><span class="sxs-lookup"><span data-stu-id="d64f6-112">To hide the default BitLocker Drive Encryption item in Control Panel</span></span>**

1.  <span data-ttu-id="d64f6-113">在 [群組原則管理主控台（GPMC）] 或 [高級群組原則管理] 中，流覽至 [**使用者**設定原則] 的 [系統 &gt; **Policies** &gt; **管理範本** &gt; **] 控制台**。</span><span class="sxs-lookup"><span data-stu-id="d64f6-113">In the Group Policy Management Console (GPMC) or in Advanced Group Policy Management, browse to **User configuration** &gt; **Policies** &gt; **Administrative Templates** &gt; **Control Panel**.</span></span>

2.  <span data-ttu-id="d64f6-114">在 [**詳細資料**] 窗格中，按兩下 [**隱藏指定**的 [控制台專案]，然後按一下 [**啟用**]。</span><span class="sxs-lookup"><span data-stu-id="d64f6-114">In the **Details** pane, double-click **Hide specified Control Panel items**, and then click **Enabled**.</span></span>

3.  <span data-ttu-id="d64f6-115">按一下 [**顯示**]，按一下 [**新增**]，然後輸入**BitLockerDriveEncryption**。</span><span class="sxs-lookup"><span data-stu-id="d64f6-115">Click **Show**, click **Add**, and then type **Microsoft.BitLockerDriveEncryption**.</span></span>



## <span data-ttu-id="d64f6-116">相關主題</span><span class="sxs-lookup"><span data-stu-id="d64f6-116">Related topics</span></span>


[<span data-ttu-id="d64f6-117">了解控制台中的 BitLocker 加密選項與 BitLocker 磁碟機加密項目</span><span class="sxs-lookup"><span data-stu-id="d64f6-117">Understanding the BitLocker Encryption Options and BitLocker Drive Encryption Items in Control Panel</span></span>](understanding-the-bitlocker-encryption-options-and-bitlocker-drive-encryption-items-in-control-panel.md)

[<span data-ttu-id="d64f6-118">部署 MBAM 2.5 群組原則物件</span><span class="sxs-lookup"><span data-stu-id="d64f6-118">Deploying MBAM 2.5 Group Policy Objects</span></span>](deploying-mbam-25-group-policy-objects.md)

 

## <span data-ttu-id="d64f6-119">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="d64f6-119">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="d64f6-120">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="d64f6-120">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="d64f6-121">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="d64f6-121">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





