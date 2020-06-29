---
title: 關於電腦 TPM 晶片
description: 關於電腦 TPM 晶片
author: dansimp
ms.assetid: 6f1cf18c-277a-4932-886d-14202ca8d175
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f6df54dc8085c398bacc508fdbbb79a30b0e4204
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810011"
---
# <span data-ttu-id="fa386-103">關於電腦 TPM 晶片</span><span class="sxs-lookup"><span data-stu-id="fa386-103">About the Computer TPM Chip</span></span>


<span data-ttu-id="fa386-104">BitLocker 在與受信任的平臺模組（TPM）晶片搭配使用時，提供額外的保護。</span><span class="sxs-lookup"><span data-stu-id="fa386-104">BitLocker provides additional protection when it is used with a Trusted Platform Module (TPM) chip.</span></span> <span data-ttu-id="fa386-105">TPM 晶片是電腦製造商在許多較新的電腦上安裝的硬體元件。</span><span class="sxs-lookup"><span data-stu-id="fa386-105">The TPM chip is a hardware component that is installed in many newer computers by the computer manufacturers.</span></span> <span data-ttu-id="fa386-106">Microsoft BitLocker 管理和監控（MBAM）除了 TPM 晶片之外，還會使用 BitLocker，以協助提供額外的資料保護，並確保您的電腦未被篡改。</span><span class="sxs-lookup"><span data-stu-id="fa386-106">Microsoft BitLocker Administration and Monitoring (MBAM) uses BitLocker, in addition to the TPM chip, to help provide additional protection of your data and to make sure that your computer has not been tampered with.</span></span>

## <span data-ttu-id="fa386-107">如何設定您的 TPM</span><span class="sxs-lookup"><span data-stu-id="fa386-107">How to Set Up Your TPM</span></span>


<span data-ttu-id="fa386-108">當您在電腦上啟動 BitLocker 磁片磁碟機加密嚮導時，如果您的組織已將 BitLocker 設定為使用 TPM 晶片，BitLocker 會檢查 TPM 晶片。</span><span class="sxs-lookup"><span data-stu-id="fa386-108">When you start the BitLocker Drive Encryption wizard on your computer, BitLocker checks for a TPM chip if your organization has configured BitLocker to use a TPM chip.</span></span> <span data-ttu-id="fa386-109">如果 BitLocker 找到相容的 TPM 晶片，系統可能會提示您重新開機電腦，以啟用 TPM 晶片以供使用。</span><span class="sxs-lookup"><span data-stu-id="fa386-109">If BitLocker finds a compatible TPM chip, you may be prompted to restart your computer to enable the TPM chip for use.</span></span> <span data-ttu-id="fa386-110">重新開機電腦之後，請依照指示在 BIOS 中設定 TPM 晶片（BIOS 是電腦軟體的 Windows 層）。</span><span class="sxs-lookup"><span data-stu-id="fa386-110">As soon as your computer has restarted, follow the instructions to configure the TPM chip in the BIOS (the BIOS is a pre-Windows layer of your computer software).</span></span>

<span data-ttu-id="fa386-111">設定 BitLocker 之後，您可以在 Windows [控制台] 中開啟 [BitLocker 加密選項] 工具，然後選取 [ **TPM 管理**]，以存取 TPM 晶片的其他相關資訊。</span><span class="sxs-lookup"><span data-stu-id="fa386-111">After BitLocker is configured, you can access additional information about the TPM chip by opening the BitLocker Encryption Options tool in the Windows Control Panel, and then selecting **TPM Administration**.</span></span>

<span data-ttu-id="fa386-112">**記事** 您必須具備電腦的系統管理認證，才能存取此工具。</span><span class="sxs-lookup"><span data-stu-id="fa386-112">**Note** You must have administrative credentials on your computer to access this tool.</span></span>

 

<span data-ttu-id="fa386-113">在 TPM 失敗、BIOS 中的變更或特定的 Windows 更新，BitLocker 會鎖定您的電腦，並要求您與技術支援人員解除鎖定電腦。</span><span class="sxs-lookup"><span data-stu-id="fa386-113">In a TPM failure, a change in the BIOS, or certain Windows Updates, BitLocker will lock your computer and require you to contact your Help Desk to unlock it.</span></span> <span data-ttu-id="fa386-114">您必須提供電腦的名稱以及電腦的網域。</span><span class="sxs-lookup"><span data-stu-id="fa386-114">You have to provide the name of your computer as well as your computer’s domain.</span></span> <span data-ttu-id="fa386-115">[技術支援中心] 可提供密碼檔案，可用於解除鎖定電腦。</span><span class="sxs-lookup"><span data-stu-id="fa386-115">Help Desk can give you a password file that can be used to unlock your computer.</span></span>

## <span data-ttu-id="fa386-116">疑難排解 TPM 問題</span><span class="sxs-lookup"><span data-stu-id="fa386-116">Troubleshooting TPM Issues</span></span>


<span data-ttu-id="fa386-117">如果 TPM 失敗、在 BIOS 中變更，或發生某些 Windows 更新，BitLocker 會鎖定您的電腦，並要求您與技術支援人員解除鎖定。</span><span class="sxs-lookup"><span data-stu-id="fa386-117">If a TPM failure, change in the BIOS, or certain Windows Updates occur, BitLocker will lock your computer and require you to contact your Help Desk to unlock it.</span></span> <span data-ttu-id="fa386-118">您必須提供電腦的名稱以及電腦的網域。</span><span class="sxs-lookup"><span data-stu-id="fa386-118">You have to provide the name of your computer as well as your computer’s domain.</span></span> <span data-ttu-id="fa386-119">技術支援中心可提供密碼檔案，您可以用來解除鎖定電腦。</span><span class="sxs-lookup"><span data-stu-id="fa386-119">The Help Desk can give you a password file that you can use to unlock your computer.</span></span>

## <span data-ttu-id="fa386-120">相關主題</span><span class="sxs-lookup"><span data-stu-id="fa386-120">Related topics</span></span>


[<span data-ttu-id="fa386-121">協助使用者管理 BitLocker</span><span class="sxs-lookup"><span data-stu-id="fa386-121">Helping End Users Manage BitLocker</span></span>](helping-end-users-manage-bitlocker.md)

[<span data-ttu-id="fa386-122">使用您的 PIN 碼或密碼</span><span class="sxs-lookup"><span data-stu-id="fa386-122">Using Your PIN or Password</span></span>](using-your-pin-or-password.md)

 

 





