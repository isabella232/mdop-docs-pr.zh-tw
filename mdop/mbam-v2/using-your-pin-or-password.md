---
title: 使用您的 PIN 碼或密碼
description: 使用您的 PIN 碼或密碼
author: dansimp
ms.assetid: 7fe2aef4-d3e0-49c8-877d-7fee13dc5b7b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b8c4b894b8f3e14d2a5cfb39e744fa43874c6753
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810167"
---
# <span data-ttu-id="528a4-103">使用您的 PIN 碼或密碼</span><span class="sxs-lookup"><span data-stu-id="528a4-103">Using Your PIN or Password</span></span>


<span data-ttu-id="528a4-104">BitLocker 會要求個人識別碼（PIN）或密碼來解除儲存在您電腦上的資訊，以協助保護您的電腦。</span><span class="sxs-lookup"><span data-stu-id="528a4-104">BitLocker helps secure your computer by requiring a personal identification number (PIN) or password to unlock the information that is stored on your computer.</span></span> <span data-ttu-id="528a4-105">PIN 或密碼需求是由您的組織所設定，並取決於要加密的磁片類型。</span><span class="sxs-lookup"><span data-stu-id="528a4-105">The PIN or password requirements are set by your organization and depend on the kind of drive being encrypted.</span></span> <span data-ttu-id="528a4-106">在未輸入 PIN 或密碼的情況下，無法查看加密磁碟機上的資料。</span><span class="sxs-lookup"><span data-stu-id="528a4-106">Data on the encrypted drives cannot be viewed without entering the PIN or password.</span></span> <span data-ttu-id="528a4-107">如果您的電腦硬體包含已啟用的可信平臺模組（TPM），則在您的電腦上啟動 Windows 之前，TPM 晶片會提示您輸入 PIN。</span><span class="sxs-lookup"><span data-stu-id="528a4-107">If your computer hardware includes an enabled Trusted Platform Module (TPM), the TPM chip prompts you for your PIN before Windows starts on your computer.</span></span>

## <span data-ttu-id="528a4-108">關於您的 BitLocker PIN 及密碼</span><span class="sxs-lookup"><span data-stu-id="528a4-108">About Your BitLocker PIN and Passwords</span></span>


<span data-ttu-id="528a4-109">貴公司指定 PIN 或密碼所需的複雜性。</span><span class="sxs-lookup"><span data-stu-id="528a4-109">Your company specifies the complexity required for your PIN or password.</span></span> <span data-ttu-id="528a4-110">這些對 PIN 或密碼的需求將在 BitLocker 設定程式期間說明。</span><span class="sxs-lookup"><span data-stu-id="528a4-110">These requirements for your PIN or password are explained during the BitLocker setup process.</span></span>

<span data-ttu-id="528a4-111">密碼是用來解除鎖定電腦上不含作業系統的磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="528a4-111">The password is used to unlock drives on your computer that do not contain the operating system.</span></span> <span data-ttu-id="528a4-112">當您在啟動期間要求 PIN 之後，BitLocker 會要求您輸入密碼。</span><span class="sxs-lookup"><span data-stu-id="528a4-112">BitLocker will ask for your password after the PIN is requested during startup.</span></span> <span data-ttu-id="528a4-113">您電腦上的每個受 BitLocker 保護的硬碟都有自己唯一的密碼。</span><span class="sxs-lookup"><span data-stu-id="528a4-113">Each BitLocker protected hard disk on your computer has its own unique password.</span></span> <span data-ttu-id="528a4-114">您必須先提供密碼，才能解除鎖定受 BitLocker 保護的磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="528a4-114">You cannot unlock a BitLocker protected drive until you provide your password.</span></span>

<span data-ttu-id="528a4-115">**記事** 您的技術支援人員可能會將 [磁片磁碟機] 設定為自動解鎖。</span><span class="sxs-lookup"><span data-stu-id="528a4-115">**Note** Your Help Desk may set drives to unlock automatically.</span></span> <span data-ttu-id="528a4-116">這樣就不需要提供 PIN 或密碼就能查看磁片磁碟機上的資訊。</span><span class="sxs-lookup"><span data-stu-id="528a4-116">This eliminates the need to provide a PIN or password to view the information on the drives.</span></span>

 

## <span data-ttu-id="528a4-117">如果您忘記 PIN 或密碼，請將電腦解鎖</span><span class="sxs-lookup"><span data-stu-id="528a4-117">Unlocking Your Computer if You Forget Your PIN or Password</span></span>


<span data-ttu-id="528a4-118">如果您忘記 PIN 或密碼，您的技術支援人員可以協助您解除鎖定受 BitLocker 保護的磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="528a4-118">If you forget your PIN or password, your Help Desk can help you unlock BitLocker protected drives.</span></span> <span data-ttu-id="528a4-119">若要解除鎖定使用 BitLocker 保護的磁片磁碟機，請與您的技術支援人員聯繫（如果您需要協助）。</span><span class="sxs-lookup"><span data-stu-id="528a4-119">To unlock a drive protected with BitLocker, contact your Help Desk if you need help.</span></span>

**<span data-ttu-id="528a4-120">如果您忘記 PIN 或密碼，如何解除鎖定您的電腦</span><span class="sxs-lookup"><span data-stu-id="528a4-120">How to unlock your computer if you forget your PIN or password</span></span>**

1.  <span data-ttu-id="528a4-121">當您與您的技術支援人員聯繫時，您必須提供下列資訊：</span><span class="sxs-lookup"><span data-stu-id="528a4-121">When you contact your Help Desk, you will need to provide them with the following information:</span></span>

    -   <span data-ttu-id="528a4-122">您的使用者名稱</span><span class="sxs-lookup"><span data-stu-id="528a4-122">Your user name</span></span>

    -   <span data-ttu-id="528a4-123">您的網域</span><span class="sxs-lookup"><span data-stu-id="528a4-123">Your domain</span></span>

    -   <span data-ttu-id="528a4-124">您的復原金鑰識別碼的前八位數位。</span><span class="sxs-lookup"><span data-stu-id="528a4-124">The first eight digits of your recovery key ID.</span></span> <span data-ttu-id="528a4-125">這是32位數的代碼，如果您忘記 PIN 或密碼，就會顯示 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="528a4-125">This is a 32-digit code that BitLocker will display if you forget your PIN or password.</span></span>

        -   <span data-ttu-id="528a4-126">如果您忘記 PIN，您必須輸入將會出現在 BitLocker 損毀修復主機中的復原金鑰識別碼的前八位數。</span><span class="sxs-lookup"><span data-stu-id="528a4-126">If you forget your PIN, you will have to enter the first eight digits of the recovery key ID, which will appear in the BitLocker Recovery console.</span></span> <span data-ttu-id="528a4-127">BitLocker 損毀修復主控台是一個 Windows 中的螢幕畫面，如果您沒有輸入正確的 PIN 碼，就會顯示。</span><span class="sxs-lookup"><span data-stu-id="528a4-127">The BitLocker Recovery console is a pre-Windows screen that will be displayed if you do not enter the correct PIN.</span></span>

        -   <span data-ttu-id="528a4-128">如果您忘記密碼，請在 BitLocker 加密選項 [控制台] 應用程式中尋找復原金鑰識別碼。</span><span class="sxs-lookup"><span data-stu-id="528a4-128">If you forget your password, look for the recovery key ID in the BitLocker Encryption Options Control Panel application.</span></span> <span data-ttu-id="528a4-129">選取 [**解除鎖定磁片磁碟機**]，然後按一下 [**我無法記住我的密碼**]。</span><span class="sxs-lookup"><span data-stu-id="528a4-129">Select **Unlock Drive** and then click **I cannot remember my password**.</span></span> <span data-ttu-id="528a4-130">BitLocker [加密選項] 應用程式接著會顯示您提供給協助台的復原金鑰識別碼。</span><span class="sxs-lookup"><span data-stu-id="528a4-130">The BitLocker Encryption Options application will then display a recovery key ID that you provide to Help Desk.</span></span>

2.  <span data-ttu-id="528a4-131">當技術支援人員收到所需的資訊後，就會透過電話或電子郵件提供復原金鑰。</span><span class="sxs-lookup"><span data-stu-id="528a4-131">Once your Help Desk receives the necessary information, it will provide you with a recovery key over the phone or through e-mail.</span></span>

    -   <span data-ttu-id="528a4-132">如果您忘記 PIN，請在 BitLocker 復原主控台中輸入復原金鑰來解除鎖定電腦。</span><span class="sxs-lookup"><span data-stu-id="528a4-132">If you forgot your PIN, enter the recovery key in the BitLocker Recovery console to unlock your computer.</span></span>

    -   <span data-ttu-id="528a4-133">如果您忘記密碼，請在 BitLocker 加密選項控制台應用程式中，輸入您先前找到復原金鑰識別碼的相同位置中的復原金鑰。</span><span class="sxs-lookup"><span data-stu-id="528a4-133">If you forgot your password, enter the recovery key in the BitLocker Encryption Options Control Panel application, in the same location where you found the recovery key ID earlier.</span></span> <span data-ttu-id="528a4-134">這將會解除鎖定受保護的硬碟。</span><span class="sxs-lookup"><span data-stu-id="528a4-134">This will unlock the protected hard drive.</span></span>

## <span data-ttu-id="528a4-135">變更您的 PIN 或密碼</span><span class="sxs-lookup"><span data-stu-id="528a4-135">Changing your PIN or Password</span></span>


<span data-ttu-id="528a4-136">您必須先解除鎖定磁片磁碟機，才能在 BitLocker 受保護的磁片磁碟機上變更密碼。</span><span class="sxs-lookup"><span data-stu-id="528a4-136">Before you can change the password on a BitLocker protected drive, you must unlock the drive.</span></span> <span data-ttu-id="528a4-137">如果未解除鎖定磁片磁碟機，請選取 [**解除鎖定磁片磁碟機**]，然後輸入您目前的密碼。</span><span class="sxs-lookup"><span data-stu-id="528a4-137">If the drive is not unlocked, select **Unlock Drive**, and then enter your current password.</span></span> <span data-ttu-id="528a4-138">解除鎖定磁片磁碟機之後，您就可以選取 [**管理您的密碼**] 來變更目前的密碼。</span><span class="sxs-lookup"><span data-stu-id="528a4-138">As soon as the drive is unlocked, you can select **Manage your Password** to change your current password.</span></span>

**<span data-ttu-id="528a4-139">如何變更 PIN 或密碼</span><span class="sxs-lookup"><span data-stu-id="528a4-139">How to Change your PIN or password</span></span>**

1.  <span data-ttu-id="528a4-140">按一下 [**開始**]，然後選取 [**控制台**]。</span><span class="sxs-lookup"><span data-stu-id="528a4-140">Click **Start**, and then select **Control Panel**.</span></span> <span data-ttu-id="528a4-141">[控制] 面板隨即會在新視窗中開啟。</span><span class="sxs-lookup"><span data-stu-id="528a4-141">Control Panel opens in a new window.</span></span>

2.  <span data-ttu-id="528a4-142">選取 [**系統及安全性**]，然後選取 [ **BitLocker 加密選項**]。</span><span class="sxs-lookup"><span data-stu-id="528a4-142">Select **System and Security**, and then select **BitLocker Encryption Options**.</span></span>

    -   <span data-ttu-id="528a4-143">若要變更您的 PIN，請選取 [**管理您的 pin**]。</span><span class="sxs-lookup"><span data-stu-id="528a4-143">To change your PIN, select **Manage Your PIN**.</span></span> <span data-ttu-id="528a4-144">在這兩個欄位中輸入新的 PIN，然後選取 [**重設 pin**]。</span><span class="sxs-lookup"><span data-stu-id="528a4-144">Type your new PIN into both fields and select **Reset PIN**.</span></span>

    -   <span data-ttu-id="528a4-145">若要變更您的密碼，請選取 [**管理您的密碼**]。</span><span class="sxs-lookup"><span data-stu-id="528a4-145">To change your password, select **Manage Your Password**.</span></span> <span data-ttu-id="528a4-146">在這兩個欄位中輸入新密碼，然後選取 [**重設密碼**]。</span><span class="sxs-lookup"><span data-stu-id="528a4-146">Enter your new password into both fields and select **Reset Password**.</span></span>

 

 





