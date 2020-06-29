---
title: 如何使用自助入口網站重新取得電腦的存取權
description: 如何使用自助入口網站重新取得電腦的存取權
author: dansimp
ms.assetid: bcf095de-0237-4bb0-b450-da8fb6d6f3d0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4abcffcf35e09bd5e24f4715a38dca74518ba29e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811540"
---
# <span data-ttu-id="1bdf5-103">如何使用自助入口網站重新取得電腦的存取權</span><span class="sxs-lookup"><span data-stu-id="1bdf5-103">How to Use the Self-Service Portal to Regain Access to a Computer</span></span>


<span data-ttu-id="1bdf5-104">如果最終使用者忘記了自己的密碼或 PIN，或是變更了作業系統檔案，或是變更了 BIOS 或受信任的平臺模組（TPM），他們就可以使用自助入口網站來重新取得 Windows 的存取權，而不需向其技術支援人員尋求協助。</span><span class="sxs-lookup"><span data-stu-id="1bdf5-104">If end users get locked out of Windows by BitLocker because they forgot their password or PIN, or because they changed operating system files or changed the BIOS or the Trusted Platform Module (TPM), they can use the Self-Service Portal to regain access to Windows without having to ask their Help Desk for assistance.</span></span>

<span data-ttu-id="1bdf5-105">**記事** 如果 IT 系統管理員設定了 IIS 會話狀態超時，則會在超時前60秒顯示一則訊息。</span><span class="sxs-lookup"><span data-stu-id="1bdf5-105">**Note** If the IT administrator configured an IIS Session State time-out, a message is displayed 60 seconds prior to the time-out.</span></span>

 

<span data-ttu-id="1bdf5-106">**記事** 這些指示是針對最終使用者的觀點來撰寫和。</span><span class="sxs-lookup"><span data-stu-id="1bdf5-106">**Note** These instructions are written for and from the perspective of end users.</span></span>

 

**<span data-ttu-id="1bdf5-107">使用自助入口網站來重新取得電腦的存取權</span><span class="sxs-lookup"><span data-stu-id="1bdf5-107">To use the Self-Service Portal to regain access to a computer</span></span>**

1.  <span data-ttu-id="1bdf5-108">在 [復原金鑰 **] 欄位中**，輸入您電腦的 BitLocker 復原畫面上所顯示的32位數 BITLOCKER 金鑰識別碼中至少有八個。</span><span class="sxs-lookup"><span data-stu-id="1bdf5-108">In the **Recovery KeyId** field, enter a minimum of eight of the 32-digit BitLocker Key ID that is displayed on the BitLocker recovery screen of your computer.</span></span>

    <span data-ttu-id="1bdf5-109">**記事** 如果前八位數符合多個按鍵，則會顯示一則訊息，要求您輸入所有32位數的復原金鑰識別碼。</span><span class="sxs-lookup"><span data-stu-id="1bdf5-109">**Note** If the first eight digits match multiple keys, a message displays that requires you to enter all 32 digits of the recovery key ID.</span></span>

     

2.  <span data-ttu-id="1bdf5-110">在 [**原因**] 欄位中，選取您要求的復原金鑰原因。</span><span class="sxs-lookup"><span data-stu-id="1bdf5-110">In the **Reason** field, select a reason for your request for the recovery key.</span></span>

3.  <span data-ttu-id="1bdf5-111">按一下 [**取得金鑰**]。</span><span class="sxs-lookup"><span data-stu-id="1bdf5-111">Click **Get Key**.</span></span> <span data-ttu-id="1bdf5-112">您的 BitLocker 復原金鑰會顯示在 [您的 BitLocker 復原金鑰] 欄位中。</span><span class="sxs-lookup"><span data-stu-id="1bdf5-112">Your BitLocker recovery key is displayed in the “Your BitLocker Recovery Key” field.</span></span>

4.  <span data-ttu-id="1bdf5-113">在電腦上的 BitLocker 恢復畫面中輸入48位數的代碼，以重新取得電腦的存取權。</span><span class="sxs-lookup"><span data-stu-id="1bdf5-113">Enter the 48-digit code into the BitLocker recovery screen on your computer to regain access to the computer.</span></span>

## <span data-ttu-id="1bdf5-114">相關主題</span><span class="sxs-lookup"><span data-stu-id="1bdf5-114">Related topics</span></span>


[<span data-ttu-id="1bdf5-115">使用 MBAM 執行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="1bdf5-115">Performing BitLocker Management with MBAM</span></span>](performing-bitlocker-management-with-mbam-mbam-2.md)

 

 





