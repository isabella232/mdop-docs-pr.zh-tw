---
title: 如何使用控制台管理 MBAM 用戶端 BitLocker 加密選項
description: 如何使用控制台管理 MBAM 用戶端 BitLocker 加密選項
author: dansimp
ms.assetid: c08077e1-5529-468f-9370-c3b33fc258f3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 271147d0e5581f6ce49fe0b46aa83dae6ae4556b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800223"
---
# <span data-ttu-id="10318-103">如何使用控制台管理 MBAM 用戶端 BitLocker 加密選項</span><span class="sxs-lookup"><span data-stu-id="10318-103">How to Manage MBAM Client BitLocker Encryption Options by Using the Control Panel</span></span>


<span data-ttu-id="10318-104">在安裝 MBAM 用戶端時，**系統和安全性**下會提供 Microsoft BitLocker 管理與監視（MBAM）控制台應用程式（稱為 BitLocker 加密選項）。</span><span class="sxs-lookup"><span data-stu-id="10318-104">A Microsoft BitLocker Administration and Monitoring (MBAM) control panel application, called BitLocker Encryption Options, will be available under **System and Security** when the MBAM Client is installed.</span></span> <span data-ttu-id="10318-105">這個自訂的 MBAM [控制台] 會取代預設的 Windows BitLocker [控制台]。</span><span class="sxs-lookup"><span data-stu-id="10318-105">This customized MBAM control panel replaces the default Windows BitLocker control panel.</span></span> <span data-ttu-id="10318-106">[MBAM 控制台] 可讓您解除鎖定加密的磁碟機（固定和移除），也可協助您管理 PIN 或密碼。</span><span class="sxs-lookup"><span data-stu-id="10318-106">The MBAM control panel enables you to unlock encrypted drives (fixed and removable), and also helps you manage your PIN or password.</span></span> <span data-ttu-id="10318-107">如需啟用 MBAM [控制台] 的詳細資訊，請參閱[如何在 Windows [控制台] 中隱藏預設的 BitLocker 加密](how-to-hide-default-bitlocker-encryption-in-the-windows-control-panel.md)。</span><span class="sxs-lookup"><span data-stu-id="10318-107">For more information about enabling the MBAM control panel, see [How to Hide Default BitLocker Encryption in The Windows Control Panel](how-to-hide-default-bitlocker-encryption-in-the-windows-control-panel.md).</span></span>

<span data-ttu-id="10318-108">**記事** 對於 BitLocker 用戶端，系統會在 [事件檢視器] 中的 [**應用程式和服務記錄**  /  **Microsoft**  /  **Windows**  /  **BitLockerManagement**] 底下找到 [管理員] 和 [操作記錄] 檔案。</span><span class="sxs-lookup"><span data-stu-id="10318-108">**Note** For the BitLocker client, the Admin and Operational log files are located in Event Viewer, under **Application and Services Logs** / **Microsoft** / **Windows** / **BitLockerManagement**.</span></span>

 

**<span data-ttu-id="10318-109">使用 MBAM 用戶端控制台</span><span class="sxs-lookup"><span data-stu-id="10318-109">To use the MBAM Client Control Panel</span></span>**

1.  <span data-ttu-id="10318-110">若要開啟 BitLocker 加密選項，請按一下 [**開始**]，然後選取 [**控制台**]。</span><span class="sxs-lookup"><span data-stu-id="10318-110">To open BitLocker Encryption Options, click **Start**, and then select **Control Panel**.</span></span> <span data-ttu-id="10318-111">[**控制台**] 開啟時，選取 [**系統及安全性**]。</span><span class="sxs-lookup"><span data-stu-id="10318-111">When **Control Panel** opens, select **System and Security**.</span></span>

2.  <span data-ttu-id="10318-112">按兩下 [ **BitLocker 加密選項**] 以開啟自訂的 MBAM [控制台]。</span><span class="sxs-lookup"><span data-stu-id="10318-112">Double-click **BitLocker Encryption Options** to open the customized MBAM control panel.</span></span> <span data-ttu-id="10318-113">您將會看到電腦上所有硬碟磁碟機及其加密狀態的清單。</span><span class="sxs-lookup"><span data-stu-id="10318-113">You will see a list of all the hard disk drives on the computer and their encryption status.</span></span> <span data-ttu-id="10318-114">您也會看到管理 PIN 或密碼的選項。</span><span class="sxs-lookup"><span data-stu-id="10318-114">You will also see an option to manage your PIN or passwords.</span></span>

3.  <span data-ttu-id="10318-115">如果使用者和電腦免除原則已部署，請使用電腦上的硬碟清單來驗證加密狀態、解除鎖定磁片磁碟機，或要求提供 BitLocker 保護的免除。</span><span class="sxs-lookup"><span data-stu-id="10318-115">Use the list of hard disk drives on the computer to verify the encryption status, unlock a drive, or request an exemption for BitLocker protection if the User and Computer Exemption policies have been deployed.</span></span>

4.  <span data-ttu-id="10318-116">非系統管理員可以使用 BitLocker 加密選項控制台來管理 Pin 或密碼。</span><span class="sxs-lookup"><span data-stu-id="10318-116">Non-administrators can use the BitLocker Encryption Options control panel to manage PINs or passwords.</span></span> <span data-ttu-id="10318-117">使用者可以選取 [**管理 PIN]，** 然後輸入目前的 pin 和新的 pin。</span><span class="sxs-lookup"><span data-stu-id="10318-117">A user can select **Manage PIN,** and then enter both a current PIN and a new PIN.</span></span> <span data-ttu-id="10318-118">使用者也可以確認其新的 PIN。</span><span class="sxs-lookup"><span data-stu-id="10318-118">Users can also confirm their new PIN.</span></span> <span data-ttu-id="10318-119">**更新 pin**函數會將 PIN 重設為使用者選取的新帳戶。</span><span class="sxs-lookup"><span data-stu-id="10318-119">The **Update PIN** function will reset the PIN to the new one that the user selects.</span></span>

5.  <span data-ttu-id="10318-120">若要管理您的密碼，請選取 [**解鎖磁片磁碟機**]，然後輸入您目前的密碼。</span><span class="sxs-lookup"><span data-stu-id="10318-120">To manage your password, select **Unlock drive** and enter your current password.</span></span> <span data-ttu-id="10318-121">一旦解除鎖定磁片磁碟機，請選取 [**重設密碼**] 變更您目前的密碼。</span><span class="sxs-lookup"><span data-stu-id="10318-121">As soon as the drive is unlocked, select **Reset Password** to change your current password.</span></span>

## <span data-ttu-id="10318-122">相關主題</span><span class="sxs-lookup"><span data-stu-id="10318-122">Related topics</span></span>


[<span data-ttu-id="10318-123">管理 MBAM 1.0 功能</span><span class="sxs-lookup"><span data-stu-id="10318-123">Administering MBAM 1.0 Features</span></span>](administering-mbam-10-features.md)

 

 





