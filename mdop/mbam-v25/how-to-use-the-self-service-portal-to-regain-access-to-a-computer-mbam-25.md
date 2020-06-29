---
title: 如何使用自助入口網站重新取得電腦的存取權
description: 如何使用自助入口網站重新取得電腦的存取權
author: dansimp
ms.assetid: 3c24b13a-d1b1-4763-8ac0-0b2db46267e3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cde9c71a957a5270d69aa8388455895f1cb2432b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811913"
---
# <span data-ttu-id="19c1d-103">如何使用自助入口網站重新取得電腦的存取權</span><span class="sxs-lookup"><span data-stu-id="19c1d-103">How to Use the Self-Service Portal to Regain Access to a Computer</span></span>


<span data-ttu-id="19c1d-104">自助服務入口網站是 IT 系統管理員設定為其 Microsoft BitLocker 管理與監控（MBAM）2.5 部署的一部分的網站。</span><span class="sxs-lookup"><span data-stu-id="19c1d-104">The Self-Service Portal is a website that IT administrators configure as part of their Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 deployment.</span></span> <span data-ttu-id="19c1d-105">如果使用者被封鎖在 Windows 之外，該網站可讓使用者獨立地重新取得其電腦的存取權。</span><span class="sxs-lookup"><span data-stu-id="19c1d-105">The website enables end users to independently regain access to their computers if they get locked out of Windows.</span></span> <span data-ttu-id="19c1d-106">自助服務入口網站不需要技術支援人員的協助。</span><span class="sxs-lookup"><span data-stu-id="19c1d-106">The Self-Service Portal requires no assistance from Help Desk staff.</span></span>

<span data-ttu-id="19c1d-107">下列指示是從使用者的角度來撰寫，但資訊對 IT 系統管理員而言可能很有説明。</span><span class="sxs-lookup"><span data-stu-id="19c1d-107">The following instructions are written from the perspective of end users, but the information may be useful for IT administrators to understand.</span></span>

<span data-ttu-id="19c1d-108">**重要** 使用者至少必須以自助入口網站的方式，才能以實際登入電腦（而非遠端登入）一次來復原其金鑰。</span><span class="sxs-lookup"><span data-stu-id="19c1d-108">**Important** An end user must have physically logged on to the computer (not remotely) at least one time successfully to be able to recover their key using the Self-Service Portal.</span></span> <span data-ttu-id="19c1d-109">否則，他們必須使用支援人員入口網站進行金鑰復原。</span><span class="sxs-lookup"><span data-stu-id="19c1d-109">Otherwise, they must use the Helpdesk Portal for key recovery.</span></span>

 

<span data-ttu-id="19c1d-110">如果最終使用者遇到下列情況，可能會發生鎖定：</span><span class="sxs-lookup"><span data-stu-id="19c1d-110">End users may experience lockouts if they:</span></span>

-   <span data-ttu-id="19c1d-111">忘記其密碼或 PIN</span><span class="sxs-lookup"><span data-stu-id="19c1d-111">Forget their password or PIN</span></span>

-   <span data-ttu-id="19c1d-112">變更作業系統檔案、BIOS 或受信任的平臺模組（TPM）</span><span class="sxs-lookup"><span data-stu-id="19c1d-112">Change operating system files, the BIOS, or the Trusted Platform Module (TPM)</span></span>

<span data-ttu-id="19c1d-113">**記事** 如果 IT 系統管理員設定了 IIS 會話狀態超時，就會在自助服務入口網站的超時前60秒顯示一則訊息。</span><span class="sxs-lookup"><span data-stu-id="19c1d-113">**Note** If the IT administrator configured an IIS Session State time-out, a message is displayed in the Self-Service Portal 60 seconds prior to the time-out.</span></span>

 

**<span data-ttu-id="19c1d-114">使用自助入口網站來重新取得電腦的存取權</span><span class="sxs-lookup"><span data-stu-id="19c1d-114">To use the Self-Service Portal to regain access to a computer</span></span>**

1.  <span data-ttu-id="19c1d-115">在 [復原金鑰 **] 欄位中**，輸入您電腦的 BitLocker 復原畫面上所顯示的32位數 BITLOCKER 金鑰識別碼中至少有八個。</span><span class="sxs-lookup"><span data-stu-id="19c1d-115">In the **Recovery KeyId** field, enter a minimum of eight of the 32-digit BitLocker Key ID that is displayed on the BitLocker recovery screen of your computer.</span></span> <span data-ttu-id="19c1d-116">如果前八位數符合多個按鍵，則會顯示一則訊息，要求您輸入所有32位數的復原金鑰識別碼。</span><span class="sxs-lookup"><span data-stu-id="19c1d-116">If the first eight digits match multiple keys, a message displays that requires you to enter all 32 digits of the recovery key ID.</span></span>

2.  <span data-ttu-id="19c1d-117">在 [**原因**] 欄位中，選取您要求的復原金鑰原因。</span><span class="sxs-lookup"><span data-stu-id="19c1d-117">In the **Reason** field, select a reason for your request for the recovery key.</span></span>

3.  <span data-ttu-id="19c1d-118">按一下 [**取得金鑰**]。</span><span class="sxs-lookup"><span data-stu-id="19c1d-118">Click **Get Key**.</span></span> <span data-ttu-id="19c1d-119">您的 BitLocker 復原金鑰會顯示在 [**您的 bitlocker 復原金鑰**] 欄位中。</span><span class="sxs-lookup"><span data-stu-id="19c1d-119">Your BitLocker recovery key is displayed in the **Your BitLocker Recovery Key** field.</span></span>

4.  <span data-ttu-id="19c1d-120">在電腦上的 BitLocker 恢復畫面中輸入48位數的代碼，以重新取得電腦的存取權。</span><span class="sxs-lookup"><span data-stu-id="19c1d-120">Enter the 48-digit code into the BitLocker recovery screen on your computer to regain access to the computer.</span></span>



## <span data-ttu-id="19c1d-121">相關主題</span><span class="sxs-lookup"><span data-stu-id="19c1d-121">Related topics</span></span>


[<span data-ttu-id="19c1d-122">使用 MBAM 2.5 執行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="19c1d-122">Performing BitLocker Management with MBAM 2.5</span></span>](performing-bitlocker-management-with-mbam-25.md)

 
## <span data-ttu-id="19c1d-123">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="19c1d-123">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="19c1d-124">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="19c1d-124">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="19c1d-125">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="19c1d-125">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>
 





