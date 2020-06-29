---
title: 如何在 Windows 控制台中隱藏預設 BitLocker 加密
description: 如何在 Windows 控制台中隱藏預設 BitLocker 加密
author: dansimp
ms.assetid: c8503743-220c-497c-9785-e2feeca484d6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 67a61763e556f8c3b93825220dbbd61a14b7d6f4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810598"
---
# <span data-ttu-id="29bad-103">如何在 Windows 控制台中隱藏預設 BitLocker 加密</span><span class="sxs-lookup"><span data-stu-id="29bad-103">How to Hide Default BitLocker Encryption in The Windows Control Panel</span></span>


<span data-ttu-id="29bad-104">Microsoft BitLocker 管理與監控（MBAM）為名為「BitLocker 加密選項」的 MBAM 用戶端電腦提供自訂的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="29bad-104">Microsoft BitLocker Administration and Monitoring (MBAM) offers a customized control panel for MBAM client computers that is named called BitLocker Encryption Options.</span></span> <span data-ttu-id="29bad-105">這個自訂的 [控制台] 可以取代名為 [BitLocker 磁碟機加密] 的預設 Windows BitLocker [控制台]。</span><span class="sxs-lookup"><span data-stu-id="29bad-105">This customized control panel can replace the default Windows BitLocker control panel that is named BitLocker Drive Encryption.</span></span> <span data-ttu-id="29bad-106">在 Windows [控制台] 中的 [系統及安全性] 底下的 [BitLocker 加密選項] 控制台，可讓使用者管理其 PIN 及密碼、解除鎖定磁片磁碟機，以及隱藏允許系統管理員解密磁片磁碟機或暫停或繼續 BitLocker 加密的介面。</span><span class="sxs-lookup"><span data-stu-id="29bad-106">The BitLocker Encryption Options control panel, located under System and Security in the Windows control panel, enables users to manage their PIN and passwords, unlock drives, and hides the interface that allows administrators to decrypt a drive or to suspend or resume BitLocker encryption.</span></span>

**<span data-ttu-id="29bad-107">若要在 Windows [控制台] 中隱藏預設的 BitLocker 加密</span><span class="sxs-lookup"><span data-stu-id="29bad-107">To hide default BitLocker Encryption in the Windows Control Panel</span></span>**

1.  <span data-ttu-id="29bad-108">使用群組原則管理主控台（GPMC）、高級群組原則管理（AGPM），或 BitLocker 群組原則電腦上的本機組策略編輯器，流覽至**使用者**設定。</span><span class="sxs-lookup"><span data-stu-id="29bad-108">Browse to **User configuration** by using the Group Policy Management Console (GPMC), the Advanced Group Policy Management (AGPM), or the Local Group Policy Editor on the BitLocker Group Policies computer.</span></span>

2.  <span data-ttu-id="29bad-109">按一下 [**原則**]，選取 [系統**管理範本**]，然後按一下 [**控制台**]。</span><span class="sxs-lookup"><span data-stu-id="29bad-109">Click **Policies**, select **Administrative Templates**, and then click **Control Panel**.</span></span>

3.  <span data-ttu-id="29bad-110">在 [**詳細資料**] 窗格中，按兩下 [**隱藏指定**的 [控制台專案]，然後選取 [**啟用**]。</span><span class="sxs-lookup"><span data-stu-id="29bad-110">In the **Details** pane, double-click **Hide specified Control Panel items**, and then select **Enabled**.</span></span>

4.  <span data-ttu-id="29bad-111">按一下 [**顯示**]，**按一下 [新增 ...**]，然後輸入 BitLockerDriveEncryption。</span><span class="sxs-lookup"><span data-stu-id="29bad-111">Click **Show**, **click Add…**, and then type Microsoft.BitLockerDriveEncryption.</span></span> <span data-ttu-id="29bad-112">此原則會從 Windows [控制台] 中隱藏預設的 Windows BitLocker 管理工具，並允許使用者從 Windows [控制台] 開啟 [更新的 MBAM BitLocker 加密選項] 工具。</span><span class="sxs-lookup"><span data-stu-id="29bad-112">This policy hides the default Windows BitLocker Management tool from the Windows Control Panel and allows the user to open the updated MBAM BitLocker Encryption Options tool from the Windows Control Panel.</span></span>

## <span data-ttu-id="29bad-113">相關主題</span><span class="sxs-lookup"><span data-stu-id="29bad-113">Related topics</span></span>


[<span data-ttu-id="29bad-114">部署 MBAM 1.0 群組原則物件</span><span class="sxs-lookup"><span data-stu-id="29bad-114">Deploying MBAM 1.0 Group Policy Objects</span></span>](deploying-mbam-10-group-policy-objects.md)

 

 





