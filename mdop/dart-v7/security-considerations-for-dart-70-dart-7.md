---
title: DaRT 7.0 的安全性考量
description: DaRT 7.0 的安全性考量
author: dansimp
ms.assetid: 52ad7e6c-c169-4ba4-aa76-56335a585eb8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 739c0319195aeb26e38d55ffe01d14b623de7f43
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809531"
---
# <span data-ttu-id="4960b-103">DaRT 7.0 的安全性考量</span><span class="sxs-lookup"><span data-stu-id="4960b-103">Security Considerations for DaRT 7.0</span></span>


<span data-ttu-id="4960b-104">Microsoft Diagnostics 與修復工具組（DaRT）7包含可讓系統管理員以遠端方式執行 DaRT 工具，以解決最終使用者電腦上的問題的功能。</span><span class="sxs-lookup"><span data-stu-id="4960b-104">Microsoft Diagnostics and Recovery Toolset (DaRT)7 includes functionality that lets an administrator run the DaRT tools remotely to resolve problems on an end-user computer.</span></span> <span data-ttu-id="4960b-105">在舊版的 DaRT 中，技術支援人員或系統管理員必須在使用者電腦上實際使用，並使用包含 DaRT 復原影像的 CD 或 DVD 開機至 DaRT。</span><span class="sxs-lookup"><span data-stu-id="4960b-105">In earlier releases of DaRT, a help desk technician or administrator had to physically be at an end-user computer and boot into DaRT by using the CD or DVD that included the DaRT recovery image.</span></span> <span data-ttu-id="4960b-106">現在，技術支援人員或系統管理員可以遠端執行相同的程式。</span><span class="sxs-lookup"><span data-stu-id="4960b-106">Now, the help desk technician or administrator can perform the same procedures remotely.</span></span>

<span data-ttu-id="4960b-107">此外，在 DaRT7 中，您現在可以將國際標準組織（ISO）影像儲存到 USB 快閃記憶體磁片磁碟機上。</span><span class="sxs-lookup"><span data-stu-id="4960b-107">Also in DaRT7, in addition to burning a CD or DVD, you are now able to save the International Organization for Standardization (ISO) image to a USB flash drive.</span></span> <span data-ttu-id="4960b-108">您也可以將 ISO 影像放在網路上，或將其內容納入電腦硬碟上的復原分區。</span><span class="sxs-lookup"><span data-stu-id="4960b-108">You can also put the ISO image on a network or include its contents as a recovery partition on a computer hard disk.</span></span>

<span data-ttu-id="4960b-109">DaRT7 中的**遠端**連線功能可讓使用者使用下列其中一種新的部署方法存取 DaRT。</span><span class="sxs-lookup"><span data-stu-id="4960b-109">The **Remote Connection** feature in DaRT7 lets end users access DaRT by using one of these new deployment methods.</span></span> <span data-ttu-id="4960b-110">因此，他們可以更輕鬆地啟動 DaRT 並存取 DaRT 工具。</span><span class="sxs-lookup"><span data-stu-id="4960b-110">Therefore, they can more easily start DaRT and access the DaRT tools.</span></span>

<span data-ttu-id="4960b-111">DaRT7 中的新功能可在您的企業中使用 DaRT，提供更大的彈性。</span><span class="sxs-lookup"><span data-stu-id="4960b-111">The new functionalities in DaRT7 provide much more flexibility in how you use DaRT in your enterprise.</span></span> <span data-ttu-id="4960b-112">不過，它們也會建立自己的一組安全問題，必須加以解決。</span><span class="sxs-lookup"><span data-stu-id="4960b-112">However, they also create their own set of security issues that must be addressed.</span></span> <span data-ttu-id="4960b-113">我們建議您在設定 DaRT 時，考慮下列安全性秘訣。</span><span class="sxs-lookup"><span data-stu-id="4960b-113">We recommend that you consider the following security tips when you configure DaRT.</span></span>

## <span data-ttu-id="4960b-114">當您建立 DaRT 復原影像時，協助維護安全性</span><span class="sxs-lookup"><span data-stu-id="4960b-114">To help maintain security when you create the DaRT recovery image</span></span>


<span data-ttu-id="4960b-115">當您建立 DaRT 復原影像時，您可以選取要包含的工具。</span><span class="sxs-lookup"><span data-stu-id="4960b-115">When you are creating the DaRT recovery image, you can select the tools that you want to include.</span></span> <span data-ttu-id="4960b-116">出於安全性考慮，您可能會想要限制最終使用者存取更強大的 DaRT 工具，例如磁片擦除及 Locksmith。</span><span class="sxs-lookup"><span data-stu-id="4960b-116">For security reasons, you might want to restrict end-user access to the more powerful DaRT tools, such as Disk Wipe and Locksmith.</span></span> <span data-ttu-id="4960b-117">在 DaRT7 中，您可以在設定期間停用某些工具，當使用者啟動遠端連線功能時，仍能讓支援人員使用。</span><span class="sxs-lookup"><span data-stu-id="4960b-117">In DaRT7, you can disable certain tools during configuration and still make them available to helpdesk agents when the end user starts the Remote Connection feature.</span></span>

<span data-ttu-id="4960b-118">您甚至可以設定 DaRT 影像，讓 [啟動遠端連線會話] 選項成為最終使用者可以使用的唯一工具。</span><span class="sxs-lookup"><span data-stu-id="4960b-118">You can even configure the DaRT image so that the option to start a remote connection session is the only tool available to an end user.</span></span>

<span data-ttu-id="4960b-119">**重要** 在遠端連線建立之後，您在復原影像中所包含的所有工具，包括最終使用者無法使用的所有工具，都會提供給支援人員在使用者電腦上工作的狀態。</span><span class="sxs-lookup"><span data-stu-id="4960b-119">**Important** After the remote connection is established, all the tools that you included in the recovery image, including those unavailable to the end user, will become available to the helpdesk agent working on the end–user computer.</span></span>

 

<span data-ttu-id="4960b-120">如需在 DaRT 復原影像中加入工具的詳細資訊，請參閱[如何使用 dart 復原映射嚮導來建立恢復影像](how-to-use-the-dart-recovery-image-wizard-to-create-the-recovery-image-dart-7.md)。</span><span class="sxs-lookup"><span data-stu-id="4960b-120">For more information about including tools in the DaRT recovery image, see [How to Use the DaRT Recovery Image Wizard to Create the Recovery Image](how-to-use-the-dart-recovery-image-wizard-to-create-the-recovery-image-dart-7.md).</span></span>

## <span data-ttu-id="4960b-121">使用加密 DaRT 恢復影像來協助維護安全性</span><span class="sxs-lookup"><span data-stu-id="4960b-121">To help maintain security by encrypting the DaRT recovery image</span></span>


<span data-ttu-id="4960b-122">如果您使用 DaRT7 中的新部署選項（例如，儲存至 USB 快閃記憶體磁片磁碟機或建立遠端分區或復原分區），您可以在 ISO 上加入貴公司的首選磁片磁碟機加密方法。</span><span class="sxs-lookup"><span data-stu-id="4960b-122">If you use one of the deployment options new in DaRT7, for example, saving to a USB flash drive or creating a remote partition or a recovery partition, you can include your company’s preferred method of drive encryption on the ISO.</span></span> <span data-ttu-id="4960b-123">這將有助於確保使用者無法使用 DaRT 的功能，讓他們能夠存取恢復影像。</span><span class="sxs-lookup"><span data-stu-id="4960b-123">This will help make sure that an end user cannot use the functionality of DaRT should they gain access to the recovery image.</span></span> <span data-ttu-id="4960b-124">此外，也會確認未授權的使用者無法在屬於其他人的電腦上啟動到 DaRT。</span><span class="sxs-lookup"><span data-stu-id="4960b-124">And it will also make sure that unauthorized users cannot boot into DaRT on computers that belong to someone else.</span></span>

<span data-ttu-id="4960b-125">您應該在所有電腦中部署並啟用您的加密方法。</span><span class="sxs-lookup"><span data-stu-id="4960b-125">Your encryption method should be deployed and enabled in all computers.</span></span>

<span data-ttu-id="4960b-126">**記事** DaRT7 支援 BitLocker 本身。</span><span class="sxs-lookup"><span data-stu-id="4960b-126">**Note** DaRT7 supports BitLocker natively.</span></span>

 

## <span data-ttu-id="4960b-127">在遠端連線期間，協助維護兩台電腦之間的安全性</span><span class="sxs-lookup"><span data-stu-id="4960b-127">To help maintain security between two computers during Remote Connection</span></span>


<span data-ttu-id="4960b-128">根據預設，已建立**遠端**連線會話的兩台電腦之間的通訊可能不會被加密。</span><span class="sxs-lookup"><span data-stu-id="4960b-128">By default, the communication between two computers that have established a **Remote Connection** session may not be encrypted.</span></span> <span data-ttu-id="4960b-129">因此，為了協助維護兩個電腦之間的安全性，我們建議兩個電腦都是相同網路的一部分。</span><span class="sxs-lookup"><span data-stu-id="4960b-129">Therefore, to help maintain security between the two computers, we recommend that both computers are a part of the same network.</span></span>

## <span data-ttu-id="4960b-130">相關主題</span><span class="sxs-lookup"><span data-stu-id="4960b-130">Related topics</span></span>


[<span data-ttu-id="4960b-131">適用於 DaRT 7.0 的操作</span><span class="sxs-lookup"><span data-stu-id="4960b-131">Operations for DaRT 7.0</span></span>](operations-for-dart-70-new-ia.md)

 

 





