---
title: 如何修復已移動的磁碟機
description: 如何修復已移動的磁碟機
author: dansimp
ms.assetid: 0d38ce7e-bc64-473e-ae85-99b7099ca758
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: 9e7e03846e0a94902b699377043237c651939a07
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809897"
---
# <span data-ttu-id="1a01f-103">如何修復已移動的磁碟機</span><span class="sxs-lookup"><span data-stu-id="1a01f-103">How to Recover a Moved Drive</span></span>
<span data-ttu-id="1a01f-104">本主題說明如何使用管理和監控網站（也稱為說明服務台）來復原在由 Microsoft BitLocker 管理和監控（MBAM）加密之後所移動的作業系統磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="1a01f-104">This topic explains how to use the Administration and Monitoring Website (also referred to as the Help Desk) to recover an operating system drive that was moved after being encrypted by Microsoft BitLocker Administration and Monitoring (MBAM).</span></span> <span data-ttu-id="1a01f-105">移動磁碟機後，就不會再接受先前電腦上所用的 PIN，因為受信任的平臺模組（TPM）晶片已變更。</span><span class="sxs-lookup"><span data-stu-id="1a01f-105">When a drive is moved, it no longer accepts the PIN that was used in the previous computer because the Trusted Platform Module (TPM) chip has changed.</span></span> <span data-ttu-id="1a01f-106">若要復原移動的磁片磁碟機，您必須取得修復金鑰識別碼，才能取得恢復密碼。</span><span class="sxs-lookup"><span data-stu-id="1a01f-106">To recover the moved drive, you must obtain the recovery key ID to retrieve the recovery password.</span></span>

<span data-ttu-id="1a01f-107">若要復原移動的磁片磁碟機，您必須使用 [管理] 和 [監視] 網站的 [**磁碟機恢復**] 區域。</span><span class="sxs-lookup"><span data-stu-id="1a01f-107">To recover a moved drive, you must use the **Drive Recovery** area of the Administration and Monitoring Website.</span></span> <span data-ttu-id="1a01f-108">若要存取**磁片磁碟機**復原區域，您必須獲指派 MBAM [支援人員] 的使用者角色或 MBAM [高級支援人員] 使用者角色。</span><span class="sxs-lookup"><span data-stu-id="1a01f-108">To access the **Drive Recovery** area, you must be assigned the MBAM Helpdesk Users role or the MBAM Advanced Helpdesk Users role.</span></span> <span data-ttu-id="1a01f-109">如需有關這些角色的詳細資訊，請參閱[規劃 MBAM 2.5 群組和帳戶](planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles)。</span><span class="sxs-lookup"><span data-stu-id="1a01f-109">For more information about these roles, see [Planning for MBAM 2.5 Groups and Accounts](planning-for-mbam-25-groups-and-accounts.md#bkmk-helpdesk-roles).</span></span>

**<span data-ttu-id="1a01f-110">若要復原移動的磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="1a01f-110">To recover a moved drive</span></span>**
1.  <span data-ttu-id="1a01f-111">在包含已移動的磁片磁碟機的電腦上，在 Windows 復原環境（WinRE）模式中啟動電腦，或使用 Microsoft 診斷與修復工具組（DaRT）啟動電腦。</span><span class="sxs-lookup"><span data-stu-id="1a01f-111">On the computer that contains the moved drive, start the computer in Windows Recovery Environment (WinRE) mode, or start the computer by using the Microsoft Diagnostic and Recovery Toolset (DaRT).</span></span>

2.  <span data-ttu-id="1a01f-112">電腦開始使用 WinRE 或 DaRT 之後，MBAM 會將移動的作業系統磁片磁碟機視為固定的資料磁碟機。</span><span class="sxs-lookup"><span data-stu-id="1a01f-112">After the computer has been started with WinRE or DaRT, MBAM will treat the moved operating system drive as a fixed data drive.</span></span> <span data-ttu-id="1a01f-113">MBAM 接著會顯示磁碟機的復原密碼識別碼，並要求您提供復原密碼。</span><span class="sxs-lookup"><span data-stu-id="1a01f-113">MBAM will then display the drive’s recovery password ID and ask for the recovery password.</span></span>

    <span data-ttu-id="1a01f-114">**記事** 在某些情況下，您可能可以在啟動期間按一下 [**我忘記 PIN** ]，然後輸入 [恢復] 模式來顯示覆原金鑰識別碼。</span><span class="sxs-lookup"><span data-stu-id="1a01f-114">**Note** In some cases, you may be able to click **I forgot the PIN** during the startup process, and then enter the recovery mode to display the recovery key ID.</span></span>

     

3.  <span data-ttu-id="1a01f-115">使用復原金鑰識別碼來檢索復原密碼，然後從管理和監控網站解除鎖定磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="1a01f-115">Use the recovery key ID to retrieve the recovery password and unlock the drive from the Administration and Monitoring Website.</span></span> <span data-ttu-id="1a01f-116">如需相關指示，請參閱[如何在復原模式中復原磁片磁碟機](how-to-recover-a-drive-in-recovery-mode-mbam-25.md)。</span><span class="sxs-lookup"><span data-stu-id="1a01f-116">For instructions, see [How to Recover a Drive in Recovery Mode](how-to-recover-a-drive-in-recovery-mode-mbam-25.md).</span></span>

    <span data-ttu-id="1a01f-117">如果移動的磁片磁碟機已設定為在原始電腦上使用 TPM 晶片，請完成下列其他步驟。</span><span class="sxs-lookup"><span data-stu-id="1a01f-117">If the moved drive was configured to use a TPM chip on the original computer, complete the following additional steps.</span></span> <span data-ttu-id="1a01f-118">否則，恢復程式就完成了。</span><span class="sxs-lookup"><span data-stu-id="1a01f-118">Otherwise, the recovery process is complete.</span></span>

4.  <span data-ttu-id="1a01f-119">解除鎖定磁片磁碟機並完成開始程式後，請以 WinRE 模式開啟命令提示字元，並使用 `manage-bde` 命令來解密磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="1a01f-119">After unlocking the drive and completing the start process, open a command prompt in WinRE mode and use the `manage-bde` command to decrypt the drive.</span></span> <span data-ttu-id="1a01f-120">使用這個工具是移除 TPM 的唯一方法，以及不含原始 TPM 晶片的 PIN 保護器。</span><span class="sxs-lookup"><span data-stu-id="1a01f-120">Using this tool is the only way to remove the TPM plus the PIN protector without the original TPM chip.</span></span> <span data-ttu-id="1a01f-121">如需有關命令的資訊 `manage-bde` ，請參閱[manage-bde](https://go.microsoft.com/fwlink/?LinkId=393567)。</span><span class="sxs-lookup"><span data-stu-id="1a01f-121">For information about the `manage-bde` command, see [Manage-bde](https://go.microsoft.com/fwlink/?LinkId=393567).</span></span>

5.  <span data-ttu-id="1a01f-122">完成移除後，請正常啟動電腦。</span><span class="sxs-lookup"><span data-stu-id="1a01f-122">When the removal is completed, start the computer normally.</span></span> <span data-ttu-id="1a01f-123">MBAM agent 現在將強制執行原則，以使用新電腦的 TPM 加上 PIN 來加密磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="1a01f-123">The MBAM agent will now enforce the policy to encrypt the drive with the new computer’s TPM plus the PIN.</span></span>



## <span data-ttu-id="1a01f-124">相關主題</span><span class="sxs-lookup"><span data-stu-id="1a01f-124">Related topics</span></span>


[<span data-ttu-id="1a01f-125">使用 MBAM 2.5 執行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="1a01f-125">Performing BitLocker Management with MBAM 2.5</span></span>](performing-bitlocker-management-with-mbam-25.md)

 

## <span data-ttu-id="1a01f-126">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="1a01f-126">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="1a01f-127">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="1a01f-127">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="1a01f-128">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="1a01f-128">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





