---
title: 如何使用控制台管理 MBAM 用戶端 BitLocker 加密選項
description: 如何使用控制台管理 MBAM 用戶端 BitLocker 加密選項
author: dansimp
ms.assetid: e2ff153e-5770-4a12-b79d-cda998b8a8ab
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a42901ac9d8a1a3527712f4cf342b5c0ca9ffdfd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810958"
---
# <span data-ttu-id="403fa-103">如何使用控制台管理 MBAM 用戶端 BitLocker 加密選項</span><span class="sxs-lookup"><span data-stu-id="403fa-103">How to Manage MBAM Client BitLocker Encryption Options by Using the Control Panel</span></span>


<span data-ttu-id="403fa-104">安裝 Microsoft BitLocker 管理及監視用戶端時，會在 [**系統及安全性**] 下提供 [Microsoft bitlocker 管理與監視（MBAM）] 控制台應用程式（稱為 [Bitlocker 加密選項]）。</span><span class="sxs-lookup"><span data-stu-id="403fa-104">A Microsoft BitLocker Administration and Monitoring (MBAM) control panel application, called BitLocker Encryption Options, will be available under **System and Security** when the Microsoft BitLocker Administration and Monitoring Client is installed.</span></span> <span data-ttu-id="403fa-105">這個自訂 MBAM [控制台] 是一個額外的 [控制台]。</span><span class="sxs-lookup"><span data-stu-id="403fa-105">This custom MBAM control panel is an additional control panel.</span></span> <span data-ttu-id="403fa-106">它不會取代預設的 Windows BitLocker [控制台]。</span><span class="sxs-lookup"><span data-stu-id="403fa-106">It does not replace the default Windows BitLocker control panel.</span></span> <span data-ttu-id="403fa-107">MBAM [控制台] 可用來解除鎖定加密的固定和移除磁片磁碟機，也可管理 PIN 或密碼。</span><span class="sxs-lookup"><span data-stu-id="403fa-107">The MBAM control panel can be used to unlock encrypted fixed and removable drives, and also manage your PIN or password.</span></span> <span data-ttu-id="403fa-108">如需啟用 MBAM [控制台] 的詳細資訊，請參閱[如何在 Windows [控制台] 中隱藏預設的 BitLocker 加密](how-to-hide-default-bitlocker-encryption-in-the-windows-control-panel-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="403fa-108">For more information about enabling the MBAM control panel, see [How to Hide Default BitLocker Encryption in the Windows Control Panel](how-to-hide-default-bitlocker-encryption-in-the-windows-control-panel-mbam-2.md).</span></span>

**<span data-ttu-id="403fa-109">使用 MBAM 用戶端控制台</span><span class="sxs-lookup"><span data-stu-id="403fa-109">To use the MBAM Client Control Panel</span></span>**

1.  <span data-ttu-id="403fa-110">若要開啟 BitLocker 加密選項，請按一下 [**開始**]，然後選取 [**控制台**]。</span><span class="sxs-lookup"><span data-stu-id="403fa-110">To open BitLocker Encryption Options, click **Start** and then select **Control Panel**.</span></span> <span data-ttu-id="403fa-111">[**控制台**] 開啟時，選取 [**系統及安全性**]。</span><span class="sxs-lookup"><span data-stu-id="403fa-111">When **Control Panel** opens, select **System and Security**.</span></span>

2.  <span data-ttu-id="403fa-112">按兩下 [ **BitLocker 加密選項**] 以開啟自訂的 MBAM [控制台]。</span><span class="sxs-lookup"><span data-stu-id="403fa-112">Double-click **BitLocker Encryption Options** to open the customized MBAM control panel.</span></span> <span data-ttu-id="403fa-113">除了管理 PIN 或密碼的選項之外，您還會看到電腦上所有硬碟的清單及其加密狀態。</span><span class="sxs-lookup"><span data-stu-id="403fa-113">You will see a list of all the hard disk drives on the computer and their encryption status, in addition to an option to manage your PIN or passwords.</span></span>

    <span data-ttu-id="403fa-114">如果已部署使用者和電腦例外原則，電腦上的硬碟清單可以用來驗證加密狀態、解除鎖定磁片磁碟機，或要求提供 BitLocker 保護的免除。</span><span class="sxs-lookup"><span data-stu-id="403fa-114">The list of hard disk drives on the computer can be used to verify encryption status, unlock a drive, or request an exemption for BitLocker protection if the User and Computer Exemption policies have been deployed.</span></span>

    <span data-ttu-id="403fa-115">BitLocker 加密選項控制台也可讓非管理員使用者管理其 PIN 或密碼。</span><span class="sxs-lookup"><span data-stu-id="403fa-115">The BitLocker Encryption Options control panel also allows for non-administrator users to manage their PIN or passwords.</span></span> <span data-ttu-id="403fa-116">選取 [**管理 PIN**] 時，系統會提示使用者輸入目前的 pin 和新 pin （除了確認新 pin）。</span><span class="sxs-lookup"><span data-stu-id="403fa-116">By selecting **Manage PIN**, users are prompted to enter both a current PIN and a new PIN (in addition to confirming the new PIN).</span></span> <span data-ttu-id="403fa-117">選取 [**更新 pin** ] 會將 PIN 重設為使用者選取的新帳戶。</span><span class="sxs-lookup"><span data-stu-id="403fa-117">Selecting **Update PIN** will reset the PIN to the new one that the users selected.</span></span>

    <span data-ttu-id="403fa-118">若要管理您的密碼，請選取 [**解鎖磁片磁碟機**]，然後輸入您目前的密碼。</span><span class="sxs-lookup"><span data-stu-id="403fa-118">To manage your password, select **Unlock drive** and enter your current password.</span></span> <span data-ttu-id="403fa-119">一旦解除鎖定磁片磁碟機，請選取 [**重設密碼**] 變更您目前的密碼。</span><span class="sxs-lookup"><span data-stu-id="403fa-119">As soon as the drive is unlocked, select **Reset Password** to change your current password.</span></span>

## <span data-ttu-id="403fa-120">相關主題</span><span class="sxs-lookup"><span data-stu-id="403fa-120">Related topics</span></span>


[<span data-ttu-id="403fa-121">管理 MBAM 2.0 功能</span><span class="sxs-lookup"><span data-stu-id="403fa-121">Administering MBAM 2.0 Features</span></span>](administering-mbam-20-features-mbam-2.md)

 

 





