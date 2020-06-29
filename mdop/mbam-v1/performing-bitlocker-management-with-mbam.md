---
title: 使用 MBAM 執行 BitLocker 管理
description: 使用 MBAM 執行 BitLocker 管理
author: dansimp
ms.assetid: 2d24390a-87bf-48b3-96a9-3882d6f2a15c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8d0de3711d5b7c3696783a054ee7c7f8220b5356
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811427"
---
# <span data-ttu-id="728cf-103">使用 MBAM 執行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="728cf-103">Performing BitLocker Management with MBAM</span></span>


<span data-ttu-id="728cf-104">在您部署 Microsoft BitLocker 管理和監控（MBAM）之後，您可以設定及使用 MBAM 來管理企業 BitLocker 加密。</span><span class="sxs-lookup"><span data-stu-id="728cf-104">After you deploy Microsoft BitLocker Administration and Monitoring (MBAM), you can configure and use MBAM to manage enterprise BitLocker encryption.</span></span> <span data-ttu-id="728cf-105">本節說明安裝後的 BitLocker 加密管理工作（可以使用 MBAM 來完成）。</span><span class="sxs-lookup"><span data-stu-id="728cf-105">This section describes post-installation, day-to-day BitLocker encryption management tasks that can be accomplished by using MBAM.</span></span>

## <span data-ttu-id="728cf-106">使用 MBAM 重設 TPM 鎖定</span><span class="sxs-lookup"><span data-stu-id="728cf-106">Reset a TPM Lockout with MBAM</span></span>


<span data-ttu-id="728cf-107">受信任的平臺模組（TPM）微晶片提供基本的安全性相關功能。</span><span class="sxs-lookup"><span data-stu-id="728cf-107">A Trusted Platform Module (TPM) microchip provides basic security-related functions.</span></span> <span data-ttu-id="728cf-108">這些函數主要是由使用加密金鑰所完成。</span><span class="sxs-lookup"><span data-stu-id="728cf-108">These functions are accomplished primarily by the use of encryption keys.</span></span> <span data-ttu-id="728cf-109">TPM 通常是安裝在電腦或膝上型電腦的主機板上，並使用硬體匯流排與系統的其餘部分進行通訊。</span><span class="sxs-lookup"><span data-stu-id="728cf-109">The TPM is typically installed on the motherboard of a computer or laptop and communicates with the rest of the system by using a hardware bus.</span></span> <span data-ttu-id="728cf-110">加入 TPM 的電腦可以建立只能由 TPM 解密的加密金鑰。</span><span class="sxs-lookup"><span data-stu-id="728cf-110">Computers that incorporate a TPM can create cryptographic keys that can be decrypted only by the TPM.</span></span> <span data-ttu-id="728cf-111">如果使用者輸入錯誤的 PIN 太多次，可能會發生 TPM 封鎖。</span><span class="sxs-lookup"><span data-stu-id="728cf-111">A TPM lockout can occur if a user enters an incorrect PIN too many times.</span></span> <span data-ttu-id="728cf-112">在 TPM 鎖定前，使用者可以輸入不正確 PIN 的次數，會因製造商而異。</span><span class="sxs-lookup"><span data-stu-id="728cf-112">The number of times that a user can enter an incorrect PIN before the TPM locks varies from manufacturer to manufacturer.</span></span> <span data-ttu-id="728cf-113">MBAM 管理網站上的金鑰復原資料系統可讓您取得 reset TPM 擁有者密碼檔。</span><span class="sxs-lookup"><span data-stu-id="728cf-113">The Key Recovery data system on the MBAM administration website enables you to obtain a reset TPM owner password file.</span></span>

[<span data-ttu-id="728cf-114">如何重設 TPM 鎖定</span><span class="sxs-lookup"><span data-stu-id="728cf-114">How to Reset a TPM Lockout</span></span>](how-to-reset-a-tpm-lockout-mbam-1.md)

## <span data-ttu-id="728cf-115">使用 MBAM 復原磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="728cf-115">Recover drives with MBAM</span></span>


<span data-ttu-id="728cf-116">請確定您知道如何在硬體失敗、人員中的變更或加密金鑰遺失的其他情況下，嘗試從加密的磁片恢復資料。</span><span class="sxs-lookup"><span data-stu-id="728cf-116">Make sure that you know how to attempt data recovery from encrypted drives in the event of hardware failure, changes in personnel, or other situations in which encryption keys are lost.</span></span> <span data-ttu-id="728cf-117">MBAM 的加密磁片磁碟機復原功能提供了在大量移至 [恢復] 模式、移動或損毀時，可存取受 BitLocker 保護的卷所需的資料和可用性的捕獲與儲存。</span><span class="sxs-lookup"><span data-stu-id="728cf-117">The Encrypted Drive Recovery features of MBAM provide the capture and storage of data and availability of tools required to access a BitLocker-protected volume when the volume goes into recovery mode, is moved, or becomes corrupted.</span></span>

[<span data-ttu-id="728cf-118">如何修復處於修復模式的磁碟機</span><span class="sxs-lookup"><span data-stu-id="728cf-118">How to Recover a Drive in Recovery Mode</span></span>](how-to-recover-a-drive-in-recovery-mode-mbam-1.md)

[<span data-ttu-id="728cf-119">如何修復已移動的磁碟機</span><span class="sxs-lookup"><span data-stu-id="728cf-119">How to Recover a Moved Drive</span></span>](how-to-recover-a-moved-drive-mbam-1.md)

[<span data-ttu-id="728cf-120">如何修復損毀的磁碟機</span><span class="sxs-lookup"><span data-stu-id="728cf-120">How to Recover a Corrupted Drive</span></span>](how-to-recover-a-corrupted-drive-mbam-1.md)

## <span data-ttu-id="728cf-121">使用 MBAM 來判斷遺失的電腦的 BitLocker 加密狀態</span><span class="sxs-lookup"><span data-stu-id="728cf-121">Determine BitLocker Encryption State of lost computers by Using MBAM</span></span>


<span data-ttu-id="728cf-122">當您使用 MBAM 時，您可以判斷已遺失或被盜電腦的最近已知 BitLocker 加密狀態。</span><span class="sxs-lookup"><span data-stu-id="728cf-122">When you use MBAM, you can determine the last known BitLocker encryption status of computers that were lost or stolen.</span></span>

[<span data-ttu-id="728cf-123">如何判斷遺失的電腦的 BitLocker 加密狀態</span><span class="sxs-lookup"><span data-stu-id="728cf-123">How to Determine the BitLocker Encryption State of a Lost Computers</span></span>](how-to-determine-the-bitlocker-encryption-state-of-a-lost-computers-mbam-1.md)

## <span data-ttu-id="728cf-124">使用 MBAM 執行 BitLocker 管理的其他資源</span><span class="sxs-lookup"><span data-stu-id="728cf-124">Other resources for performing BitLocker Management with MBAM</span></span>


[<span data-ttu-id="728cf-125">適用於 MBAM 1.0 的操作</span><span class="sxs-lookup"><span data-stu-id="728cf-125">Operations for MBAM 1.0</span></span>](operations-for-mbam-10.md)

 

 





