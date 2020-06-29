---
title: 如何在 Windows 控制台中隱藏預設 BitLocker 加密
description: 如何在 Windows 控制台中隱藏預設 BitLocker 加密
author: dansimp
ms.assetid: 6674aa51-2b5d-4e4a-8b43-2cc18d008285
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: eda8fafbd7b3ebf414520354eba6def2e97f6237
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810341"
---
# <span data-ttu-id="23bde-103">如何在 Windows 控制台中隱藏預設 BitLocker 加密</span><span class="sxs-lookup"><span data-stu-id="23bde-103">How to Hide Default BitLocker Encryption in the Windows Control Panel</span></span>


<span data-ttu-id="23bde-104">Microsoft BitLocker 管理與監控（MBAM）為 Microsoft BitLocker 管理和監視用戶端電腦（稱為 BitLocker 加密選項）提供自訂的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="23bde-104">Microsoft BitLocker Administration and Monitoring (MBAM) offers a customized control panel for Microsoft BitLocker Administration and Monitoring client computers, called BitLocker Encryption Options.</span></span> <span data-ttu-id="23bde-105">這個自訂的 [控制台] 可以取代預設的 Windows BitLocker [控制台]，該面板稱為 [BitLocker 磁片磁碟機加密]。</span><span class="sxs-lookup"><span data-stu-id="23bde-105">This customized control panel can replace the default Windows BitLocker control panel, which is called BitLocker Drive Encryption.</span></span> <span data-ttu-id="23bde-106">[控制台] 中的 [系統及安全性] 底下的 [自訂控制台] 可讓使用者管理其 PIN 及密碼，以及解除鎖定磁片磁碟機，以及隱藏可讓系統管理員解密磁片磁碟機或暫停或繼續 BitLocker 磁片磁碟機加密的介面。</span><span class="sxs-lookup"><span data-stu-id="23bde-106">The customized control panel, which is in Control Panel under System and Security, enables users to manage their PIN and passwords and to unlock drives, and hides the interface that enables administrators to decrypt a drive or to suspend or resume BitLocker drive encryption.</span></span>

**<span data-ttu-id="23bde-107">若要在 Windows [控制台] 中隱藏預設的 BitLocker 磁片磁碟機加密</span><span class="sxs-lookup"><span data-stu-id="23bde-107">To hide default BitLocker drive encryption in Windows Control Panel</span></span>**

1.  <span data-ttu-id="23bde-108">在 [群組原則管理主控台（GPMC）]、[高級] 群組原則管理（AGPM），或 [BitLocker 群組原則] 電腦上的 [本機組策略編輯器] 中，流覽至 [**使用者**設定]。</span><span class="sxs-lookup"><span data-stu-id="23bde-108">In the Group Policy Management Console (GPMC), the Advanced Group Policy Management (AGPM), or the Local Group Policy Editor on the BitLocker Group Policies computer, browse to **User configuration**.</span></span>

2.  <span data-ttu-id="23bde-109">接著，按一下 [**原則**]，選取 [系統**管理範本**]，然後按一下 [**控制台**]。</span><span class="sxs-lookup"><span data-stu-id="23bde-109">Next, click **Policies**, select **Administrative Templates**, and then click **Control Panel**.</span></span>

3.  <span data-ttu-id="23bde-110">按兩下 [**詳細資料**] 窗格中的 [**隱藏指定**的 [控制台專案]，然後選取 [**啟用**]。</span><span class="sxs-lookup"><span data-stu-id="23bde-110">Double-click **Hide specified Control Panel items** in the **Details** pane, and then select **Enabled**.</span></span>

4.  <span data-ttu-id="23bde-111">按一下 [**顯示**]，按一下 [**新增**]，然後輸入**BitLockerDriveEncryption**。</span><span class="sxs-lookup"><span data-stu-id="23bde-111">Click **Show**, click **Add**, and then type **Microsoft.BitLockerDriveEncryption**.</span></span> <span data-ttu-id="23bde-112">這個原則會從 Windows [控制台] 中隱藏預設的 Windows BitLocker 管理工具，並在 [控制台] 中，讓使用者開啟 [系統及安全性] 底下的 [更新的 MBAM BitLocker 加密選項] 工具。</span><span class="sxs-lookup"><span data-stu-id="23bde-112">This policy hides the default Windows BitLocker Management tool from the Windows Control Panel and, in Control Panel, lets the user open the updated MBAM BitLocker Encryption Options tool under System and Security.</span></span>

## <span data-ttu-id="23bde-113">相關主題</span><span class="sxs-lookup"><span data-stu-id="23bde-113">Related topics</span></span>


[<span data-ttu-id="23bde-114">部署 MBAM 2.0 群組原則物件</span><span class="sxs-lookup"><span data-stu-id="23bde-114">Deploying MBAM 2.0 Group Policy Objects</span></span>](deploying-mbam-20-group-policy-objects-mbam-2.md)

 

 





