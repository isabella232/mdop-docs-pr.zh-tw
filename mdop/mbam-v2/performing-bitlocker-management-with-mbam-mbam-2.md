---
title: 使用 MBAM 執行 BitLocker 管理
description: 使用 MBAM 執行 BitLocker 管理
author: dansimp
ms.assetid: 9bfc6c67-f12c-4daa-8f08-5884fb47443c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d261ec4fa789cd331209afe1c2f1858d627209a3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811792"
---
# <span data-ttu-id="48fc2-103">使用 MBAM 執行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="48fc2-103">Performing BitLocker Management with MBAM</span></span>


<span data-ttu-id="48fc2-104">規劃並部署 Microsoft BitLocker 管理與監控（MBAM）之後，您可以設定並使用它來管理企業 BitLocker 加密。</span><span class="sxs-lookup"><span data-stu-id="48fc2-104">After planning and then deploying Microsoft BitLocker Administration and Monitoring (MBAM), you can configure and use it to manage enterprise BitLocker encryption.</span></span> <span data-ttu-id="48fc2-105">本節中的資訊說明安裝後的每日 BitLocker 加密管理工作，這些工作是使用 Microsoft BitLocker 管理和監控完成的。</span><span class="sxs-lookup"><span data-stu-id="48fc2-105">The information in this section describes post-installation day-to-day BitLocker encryption management tasks that are accomplished by using Microsoft BitLocker Administration and Monitoring.</span></span>

## <span data-ttu-id="48fc2-106">使用 MBAM 重設 TPM 封鎖</span><span class="sxs-lookup"><span data-stu-id="48fc2-106">Reset a TPM Lockout by Using MBAM</span></span>


<span data-ttu-id="48fc2-107">受信任的平臺模組（TPM）是專門用來提供基本安全相關功能的微晶片，主要涉及加密金鑰。</span><span class="sxs-lookup"><span data-stu-id="48fc2-107">A Trusted Platform Module (TPM) is a microchip that is designed to provide basic security-related functions, primarily involving encryption keys.</span></span> <span data-ttu-id="48fc2-108">TPM 通常是安裝在電腦或膝上型電腦的主機板上，並使用硬體匯流排與系統的其餘部分進行通訊。</span><span class="sxs-lookup"><span data-stu-id="48fc2-108">The TPM is usually installed on the motherboard of a computer or laptop, and communicates with the rest of the system by using a hardware bus.</span></span> <span data-ttu-id="48fc2-109">加入 TPM 的電腦能夠建立加密金鑰並對其進行加密，使其只能由 TPM 解密。</span><span class="sxs-lookup"><span data-stu-id="48fc2-109">Computers that incorporate a TPM have the ability to create cryptographic keys and encrypt them so that they can be decrypted only by the TPM.</span></span>

<span data-ttu-id="48fc2-110">如果使用者輸入錯誤的 PIN 太多次，可能會發生 TPM 封鎖。</span><span class="sxs-lookup"><span data-stu-id="48fc2-110">A TPM lockout can occur if a user enters the incorrect PIN too many times.</span></span> <span data-ttu-id="48fc2-111">在 TPM 鎖定前，使用者可以輸入不正確 PIN 的次數，會因製造商而異。</span><span class="sxs-lookup"><span data-stu-id="48fc2-111">The number of times that a user can enter an incorrect PIN before the TPM locks varies from manufacturer to manufacturer.</span></span> <span data-ttu-id="48fc2-112">您可以在 [管理和監控] 網站中使用 MBAM 來存取集中式金鑰復原資料系統，在此您可以在提供電腦識別碼及相關的使用者識別碼時，取得 TPM 擁有者密碼檔。</span><span class="sxs-lookup"><span data-stu-id="48fc2-112">You can use MBAM to access the centralized Key Recovery data system in the Administration and Monitoring website, where you can retrieve a TPM owner password file when you supply a computer ID and associated user identifier.</span></span>

[<span data-ttu-id="48fc2-113">如何重設 TPM 鎖定</span><span class="sxs-lookup"><span data-stu-id="48fc2-113">How to Reset a TPM Lockout</span></span>](how-to-reset-a-tpm-lockout-mbam-2.md)

## <span data-ttu-id="48fc2-114">使用 MBAM 復原磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="48fc2-114">Recover Drives with MBAM</span></span>


<span data-ttu-id="48fc2-115">當您處理資料加密時（尤其是在企業環境中），請考慮在發生硬體故障、人員或其他可能會遺失加密金鑰的情況下，可以如何復原資料。</span><span class="sxs-lookup"><span data-stu-id="48fc2-115">When you are dealing with the encryption of data, especially in an enterprise environment, consider how that data can be recovered in the event of a hardware failure, changes in personnel, or other situations in which encryption keys can be lost.</span></span>

<span data-ttu-id="48fc2-116">MBAM 的加密磁片磁碟機復原功能可確保您可以捕獲並儲存資料，以及在 BitLocker 進入 [恢復] 模式時，可使用所需的工具存取受 BitLocker 保護的磁片卷，或遭到損毀。</span><span class="sxs-lookup"><span data-stu-id="48fc2-116">The encrypted drive recovery features of MBAM ensure that data can be captured and stored and that the required tools are available to access a BitLocker-protected volume when BitLocker goes into recovery mode, is moved, or becomes corrupted.</span></span>

[<span data-ttu-id="48fc2-117">如何修復處於修復模式的磁碟機</span><span class="sxs-lookup"><span data-stu-id="48fc2-117">How to Recover a Drive in Recovery Mode</span></span>](how-to-recover-a-drive-in-recovery-mode-mbam-2.md)

[<span data-ttu-id="48fc2-118">如何修復已移動的磁碟機</span><span class="sxs-lookup"><span data-stu-id="48fc2-118">How to Recover a Moved Drive</span></span>](how-to-recover-a-moved-drive-mbam-2.md)

[<span data-ttu-id="48fc2-119">如何修復損毀的磁碟機</span><span class="sxs-lookup"><span data-stu-id="48fc2-119">How to Recover a Corrupted Drive</span></span>](how-to-recover-a-corrupted-drive-mbam-2.md)

## <span data-ttu-id="48fc2-120">使用 MBAM 來判斷遺失的電腦的 BitLocker 加密狀態</span><span class="sxs-lookup"><span data-stu-id="48fc2-120">Determine BitLocker Encryption State of Lost Computers by Using MBAM</span></span>


<span data-ttu-id="48fc2-121">您可以使用 MBAM 來判斷已遺失或被盜電腦的最近已知 BitLocker 加密狀態。</span><span class="sxs-lookup"><span data-stu-id="48fc2-121">Using MBAM, you can determine the last known BitLocker encryption status of computers that were lost or stolen.</span></span>

[<span data-ttu-id="48fc2-122">如何判斷遺失的電腦之 BitLocker 加密狀態</span><span class="sxs-lookup"><span data-stu-id="48fc2-122">How to Determine BitLocker Encryption State of Lost Computers</span></span>](how-to-determine-bitlocker-encryption-state-of-lost-computers-mbam-2.md)

## <span data-ttu-id="48fc2-123">使用自助入口網站來重新取得電腦的存取權</span><span class="sxs-lookup"><span data-stu-id="48fc2-123">Use the Self-Service Portal to Regain Access to a Computer</span></span>


<span data-ttu-id="48fc2-124">如果最終使用者從 BitLocker 封鎖 Windows，則可以使用本節中的指示來取得 BitLocker 復原金鑰，以重新取得其電腦的存取權。</span><span class="sxs-lookup"><span data-stu-id="48fc2-124">If end users get locked out of Windows by BitLocker, they can use the instructions in this section to get a BitLocker recovery key to regain access to their computer.</span></span>

[<span data-ttu-id="48fc2-125">如何使用自助入口網站重新取得電腦的存取權</span><span class="sxs-lookup"><span data-stu-id="48fc2-125">How to Use the Self-Service Portal to Regain Access to a Computer</span></span>](how-to-use-the-self-service-portal-to-regain-access-to-a-computer.md)

## <span data-ttu-id="48fc2-126">使用 MBAM 執行 BitLocker 管理的其他資源</span><span class="sxs-lookup"><span data-stu-id="48fc2-126">Other Resources for Performing BitLocker Management with MBAM</span></span>


[<span data-ttu-id="48fc2-127">適用於 MBAM 2.0 的操作</span><span class="sxs-lookup"><span data-stu-id="48fc2-127">Operations for MBAM 2.0</span></span>](operations-for-mbam-20-mbam-2.md)

 

 





