---
title: 使用 MBAM 2.5 執行 BitLocker 管理
description: 使用 MBAM 2.5 執行 BitLocker 管理
author: dansimp
ms.assetid: 068f3ee0-300c-4083-ba18-7065eef997ad
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1a0ee5802f945176914c56659e0ff7e34e93a969
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811498"
---
# <span data-ttu-id="9cf27-103">使用 MBAM 2.5 執行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="9cf27-103">Performing BitLocker Management with MBAM 2.5</span></span>


<span data-ttu-id="9cf27-104">規劃並部署 Microsoft BitLocker 管理與監控（MBAM）之後，您可以設定並使用它來管理整個企業的 BitLocker 磁片磁碟機加密。</span><span class="sxs-lookup"><span data-stu-id="9cf27-104">After planning and then deploying Microsoft BitLocker Administration and Monitoring (MBAM), you can configure and use it to manage BitLocker Drive Encryption across your enterprise.</span></span> <span data-ttu-id="9cf27-105">本節中的資訊說明安裝後的 BitLocker 加密管理工作（使用 Microsoft BitLocker 管理和監控完成）。</span><span class="sxs-lookup"><span data-stu-id="9cf27-105">The information in this section describes post-installation, day-to-day BitLocker encryption management tasks that are accomplished by using Microsoft BitLocker Administration and Monitoring.</span></span>

## <span data-ttu-id="9cf27-106">重設 TPM 封鎖</span><span class="sxs-lookup"><span data-stu-id="9cf27-106">Reset a TPM lockout</span></span>


<span data-ttu-id="9cf27-107">受信任的平臺模組（TPM）是專門用來提供基本安全相關功能的微晶片，主要涉及加密金鑰。</span><span class="sxs-lookup"><span data-stu-id="9cf27-107">A Trusted Platform Module (TPM) is a microchip that is designed to provide basic security-related functions, primarily involving encryption keys.</span></span> <span data-ttu-id="9cf27-108">TPM 通常安裝在電腦的主機板上，而且它會使用主機匯流排配接器與系統的其餘部分進行通訊。</span><span class="sxs-lookup"><span data-stu-id="9cf27-108">The TPM is usually installed on the motherboard of a computer, and it communicates with the rest of the system by using a host bus adapter.</span></span> <span data-ttu-id="9cf27-109">在併入 TPM 的電腦上，您可以建立加密金鑰並加以加密，以便只可由 TPM 解密。</span><span class="sxs-lookup"><span data-stu-id="9cf27-109">On computers that incorporate a TPM, you can create cryptographic keys and encrypt them so that they can be decrypted only by the TPM.</span></span>

<span data-ttu-id="9cf27-110">如果使用者輸入錯誤的 PIN 太多次，可能會發生 TPM 封鎖。</span><span class="sxs-lookup"><span data-stu-id="9cf27-110">A TPM lockout can occur if a user enters the incorrect PIN too many times.</span></span> <span data-ttu-id="9cf27-111">在 TPM 鎖定之前，使用者可以輸入不正確 PIN 的次數，視製造商而定。</span><span class="sxs-lookup"><span data-stu-id="9cf27-111">The number of times that a user can enter an incorrect PIN before the TPM locks varies by manufacturer.</span></span> <span data-ttu-id="9cf27-112">您可以在 [管理與監控] 網站上使用 MBAM 來存取集中式金鑰復原資料系統，您可以在提供電腦識別碼及相關聯的使用者識別碼時，取得 TPM 擁有者密碼檔案。</span><span class="sxs-lookup"><span data-stu-id="9cf27-112">You can use MBAM to access the centralized key recovery data system on the Administration and Monitoring Website, where you can retrieve a TPM owner password file when you supply a computer ID and an associated user identifier.</span></span>

[<span data-ttu-id="9cf27-113">如何重設 TPM 鎖定</span><span class="sxs-lookup"><span data-stu-id="9cf27-113">How to Reset a TPM Lockout</span></span>](how-to-reset-a-tpm-lockout-mbam-25.md)

## <span data-ttu-id="9cf27-114">復原磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="9cf27-114">Recover drives</span></span>


<span data-ttu-id="9cf27-115">當您處理資料加密時（尤其是在企業環境中），請考慮在發生硬體故障、人員或其他可能會遺失加密金鑰的情況下，可以如何復原資料。</span><span class="sxs-lookup"><span data-stu-id="9cf27-115">When you are dealing with the encryption of data, especially in an enterprise environment, consider how that data can be recovered in the event of a hardware failure, changes in personnel, or other situations in which encryption keys can be lost.</span></span>

<span data-ttu-id="9cf27-116">MBAM 中的加密磁片磁碟機復原功能可確保在 BitLocker 進入復原模式、移動或損毀時，可以捕獲並儲存資料，以及使用必要的工具存取受 BitLocker 保護的磁片。</span><span class="sxs-lookup"><span data-stu-id="9cf27-116">The encrypted drive recovery features in MBAM ensure that data can be captured and stored and that the required tools are available to access a BitLocker-protected volume when BitLocker goes into recovery mode, is moved, or becomes corrupted.</span></span>

[<span data-ttu-id="9cf27-117">如何修復處於修復模式的磁碟機</span><span class="sxs-lookup"><span data-stu-id="9cf27-117">How to Recover a Drive in Recovery Mode</span></span>](how-to-recover-a-drive-in-recovery-mode-mbam-25.md)

[<span data-ttu-id="9cf27-118">如何修復已移動的磁碟機</span><span class="sxs-lookup"><span data-stu-id="9cf27-118">How to Recover a Moved Drive</span></span>](how-to-recover-a-moved-drive-mbam-25.md)

[<span data-ttu-id="9cf27-119">如何修復損毀的磁碟機</span><span class="sxs-lookup"><span data-stu-id="9cf27-119">How to Recover a Corrupted Drive</span></span>](how-to-recover-a-corrupted-drive-mbam-25.md)

## <span data-ttu-id="9cf27-120">判斷遺失的電腦的 BitLocker 加密狀態</span><span class="sxs-lookup"><span data-stu-id="9cf27-120">Determine BitLocker encryption state of lost computers</span></span>


<span data-ttu-id="9cf27-121">您可以使用 MBAM 來判斷已遺失或被盜電腦的最近已知 BitLocker 加密狀態。</span><span class="sxs-lookup"><span data-stu-id="9cf27-121">By using MBAM, you can determine the last known BitLocker encryption status of computers that were lost or stolen.</span></span>

[<span data-ttu-id="9cf27-122">如何判斷遺失的電腦之 BitLocker 加密狀態</span><span class="sxs-lookup"><span data-stu-id="9cf27-122">How to Determine BitLocker Encryption State of Lost Computers</span></span>](how-to-determine-bitlocker-encryption-state-of-lost-computers-mbam-25.md)

## <span data-ttu-id="9cf27-123">使用自助入口網站來重新取得電腦的存取權</span><span class="sxs-lookup"><span data-stu-id="9cf27-123">Use the Self-Service Portal to regain access to a computer</span></span>


<span data-ttu-id="9cf27-124">如果最終使用者從 BitLocker 封鎖 Windows，則可以使用本節中的指示來取得 BitLocker 復原金鑰，以重新取得其電腦的存取權。</span><span class="sxs-lookup"><span data-stu-id="9cf27-124">If end users get locked out of Windows by BitLocker, they can use the instructions in this section to get a BitLocker recovery key to regain access to their computer.</span></span>

[<span data-ttu-id="9cf27-125">如何使用自助入口網站重新取得電腦的存取權</span><span class="sxs-lookup"><span data-stu-id="9cf27-125">How to Use the Self-Service Portal to Regain Access to a Computer</span></span>](how-to-use-the-self-service-portal-to-regain-access-to-a-computer-mbam-25.md)



## <span data-ttu-id="9cf27-126">相關主題</span><span class="sxs-lookup"><span data-stu-id="9cf27-126">Related topics</span></span>


[<span data-ttu-id="9cf27-127">適用於 MBAM 2.5 的操作</span><span class="sxs-lookup"><span data-stu-id="9cf27-127">Operations for MBAM 2.5</span></span>](operations-for-mbam-25.md)

 

## <span data-ttu-id="9cf27-128">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="9cf27-128">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="9cf27-129">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="9cf27-129">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="9cf27-130">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="9cf27-130">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





