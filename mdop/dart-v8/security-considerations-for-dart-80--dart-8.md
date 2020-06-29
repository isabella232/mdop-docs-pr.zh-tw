---
title: DaRT 8.0 的安全性考量
description: DaRT 8.0 的安全性考量
author: dansimp
ms.assetid: 45ef8164-fee7-41a1-9a36-de4e3264e7a8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 02d32d926c0def7d33bebd399cd380eed4e8385e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800158"
---
# <span data-ttu-id="91c1c-103">DaRT 8.0 的安全性考量</span><span class="sxs-lookup"><span data-stu-id="91c1c-103">Security Considerations for DaRT 8.0</span></span>


<span data-ttu-id="91c1c-104">本主題包含帳戶和群組、記錄檔案，以及 Microsoft Diagnostics 與恢復工具組（DaRT）8.0 的其他安全相關注意事項的簡短概述。</span><span class="sxs-lookup"><span data-stu-id="91c1c-104">This topic contains a brief overview about the accounts and groups, log files, and other security-related considerations for Microsoft Diagnostics and Recovery Toolset (DaRT) 8.0.</span></span> <span data-ttu-id="91c1c-105">如需詳細資訊，請參閱本文中的連結。</span><span class="sxs-lookup"><span data-stu-id="91c1c-105">For more information, follow the links within this article.</span></span>

## <span data-ttu-id="91c1c-106">一般安全性考慮</span><span class="sxs-lookup"><span data-stu-id="91c1c-106">General security considerations</span></span>


<span data-ttu-id="91c1c-107">**瞭解安全性風險**。</span><span class="sxs-lookup"><span data-stu-id="91c1c-107">**Understand the security risks**.</span></span> <span data-ttu-id="91c1c-108">DaRT 8.0 包含的功能可讓系統管理員或技術支援人員遠端執行 DaRT 工具，以解決最終使用者電腦上的問題。</span><span class="sxs-lookup"><span data-stu-id="91c1c-108">DaRT 8.0 includes functionality that lets an administrator or a help desk worker run the DaRT tools remotely to resolve problems on an end-user computer.</span></span> <span data-ttu-id="91c1c-109">此外，您可以將國際標準組織（ISO）影像儲存至 USB 快閃記憶體磁片磁碟機，或將 ISO 影像放在網路上，將其內容納入電腦硬碟上的復原分區。</span><span class="sxs-lookup"><span data-stu-id="91c1c-109">In addition, you can save the International Organization for Standardization (ISO) image to a USB flash drive or put the ISO image on a network to include its contents as a recovery partition on a computer’s hard disk.</span></span> <span data-ttu-id="91c1c-110">這些功能提供靈活性，但也會產生您在設定 DaRT 時應考慮的潛在安全風險。</span><span class="sxs-lookup"><span data-stu-id="91c1c-110">These capabilities provide flexibility, but also create potential security risks that you should consider when configuring DaRT.</span></span>

<span data-ttu-id="91c1c-111">**在物理上保護您的電腦**。</span><span class="sxs-lookup"><span data-stu-id="91c1c-111">**Physically secure your computers**.</span></span> <span data-ttu-id="91c1c-112">當系統管理員與技術支援人員在電腦上實際不在電腦上時，他們應該鎖定其電腦，並使用安全的螢幕保護裝置程式。</span><span class="sxs-lookup"><span data-stu-id="91c1c-112">When administrators and help desk workers are not physically at their computers, they should lock their computers and use a secured screen saver.</span></span>

<span data-ttu-id="91c1c-113">**將最新的安全性更新套用至所有電腦**。</span><span class="sxs-lookup"><span data-stu-id="91c1c-113">**Apply the most recent security updates to all computers**.</span></span> <span data-ttu-id="91c1c-114">訂閱安全性通知服務（），隨時掌握新的作業系統更新通知 <https://go.microsoft.com/fwlink/?LinkId=28819> 。</span><span class="sxs-lookup"><span data-stu-id="91c1c-114">Stay informed about new updates for operating systems by subscribing to the Security Notification service (<https://go.microsoft.com/fwlink/?LinkId=28819>).</span></span>

## <span data-ttu-id="91c1c-115">限制最終使用者存取 DaRT 工具</span><span class="sxs-lookup"><span data-stu-id="91c1c-115">Limit end-user access to DaRT tools</span></span>


<span data-ttu-id="91c1c-116">當您建立 DaRT 復原影像時，您可以選取要包含的工具。</span><span class="sxs-lookup"><span data-stu-id="91c1c-116">When you are creating the DaRT recovery image, you can select the tools that you want to include.</span></span> <span data-ttu-id="91c1c-117">出於安全性考慮，您可能會想要限制最終使用者存取更強大的 DaRT 工具，例如磁片擦除及 Locksmith。</span><span class="sxs-lookup"><span data-stu-id="91c1c-117">For security reasons, you might want to restrict end-user access to the more powerful DaRT tools, such as Disk Wipe and Locksmith.</span></span> <span data-ttu-id="91c1c-118">在 DaRT 8.0 中，您可以在設定期間停用某些工具，並讓使用者在使用者啟動遠端連線功能時，仍能使用技術支援人員。</span><span class="sxs-lookup"><span data-stu-id="91c1c-118">In DaRT 8.0, you can disable certain tools during configuration and still make them available to help desk workers when the end user starts the Remote Connection feature.</span></span>

<span data-ttu-id="91c1c-119">您甚至可以設定 DaRT 影像，讓 [啟動遠端連線會話] 選項成為最終使用者可以使用的唯一工具。</span><span class="sxs-lookup"><span data-stu-id="91c1c-119">You can even configure the DaRT image so that the option to start a remote connection session is the only tool available to an end user.</span></span>

<span data-ttu-id="91c1c-120">**重要** 在遠端連線建立之後，您在復原影像中所包含的所有工具，包括最終使用者無法使用的所有工具，都會提供給在最終使用者電腦上工作的任何技術支援人員。</span><span class="sxs-lookup"><span data-stu-id="91c1c-120">**Important** After the remote connection is established, all the tools that you included in the recovery image, including those unavailable to the end user, will become available to any help desk worker who is working on the end–user computer.</span></span>

 

<span data-ttu-id="91c1c-121">如需在 DaRT 復原影像中加入工具的詳細資訊，請參閱[dart 8.0 中的工具概覽](overview-of-the-tools-in-dart-80-dart-8.md)。</span><span class="sxs-lookup"><span data-stu-id="91c1c-121">For more information about including tools in the DaRT recovery image, see [Overview of the Tools in DaRT 8.0](overview-of-the-tools-in-dart-80-dart-8.md).</span></span>

## <span data-ttu-id="91c1c-122">保護 DaRT 恢復影像</span><span class="sxs-lookup"><span data-stu-id="91c1c-122">Secure the DaRT recovery image</span></span>


<span data-ttu-id="91c1c-123">如果您是將 DaRT 復原影像儲存至 USB 快閃記憶體磁片磁碟機，或建立遠端分區或復原分區，您可能會想要在 ISO 上加入貴公司的首選磁片磁碟機加密方法。</span><span class="sxs-lookup"><span data-stu-id="91c1c-123">If you deploy the DaRT recovery image by saving it to a USB flash drive or by creating a remote partition or a recovery partition, you might want to include your company’s preferred method of drive encryption on the ISO.</span></span> <span data-ttu-id="91c1c-124">加密 ISO 可協助確保使用者無法使用 DaRT 功能取得對復原影像的存取權，並確保未經授權的使用者無法在屬於其他人的電腦上啟動到 DaRT。</span><span class="sxs-lookup"><span data-stu-id="91c1c-124">Encrypting the ISO helps to ensure that end users cannot use DaRT functionality if they were to gain access to the recovery image, and it ensures that unauthorized users cannot boot into DaRT on computers that belong to someone else.</span></span> <span data-ttu-id="91c1c-125">如果您使用加密方法，請務必在所有電腦中部署並啟用該方法。</span><span class="sxs-lookup"><span data-stu-id="91c1c-125">If you use an encryption method, be sure to deploy and enable it in all computers.</span></span>

<span data-ttu-id="91c1c-126">**記事** DaRT 8.0 本身支援 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="91c1c-126">**Note** DaRT 8.0 supports BitLocker natively.</span></span>

 

<span data-ttu-id="91c1c-127">若要納入磁片磁碟機加密，請在建立復原影像時新增加密方案檔案。</span><span class="sxs-lookup"><span data-stu-id="91c1c-127">To include drive encryption, add the encryption solution files when you create the recovery image.</span></span> <span data-ttu-id="91c1c-128">您的加密解決方案必須能夠在 WinPE 上執行。</span><span class="sxs-lookup"><span data-stu-id="91c1c-128">Your encryption solution must be able to run on WinPE.</span></span> <span data-ttu-id="91c1c-129">從 ISO 啟動的最終使用者可以存取該加密解決方案並解除封鎖磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="91c1c-129">End users who boot from the ISO are then able to access that encryption solution and unblock the drive.</span></span>

## <span data-ttu-id="91c1c-130">當您使用遠端連線時，在兩部電腦之間維持安全性</span><span class="sxs-lookup"><span data-stu-id="91c1c-130">Maintain security between two computers when you use Remote Connection</span></span>


<span data-ttu-id="91c1c-131">根據預設，已建立**遠端**連線會話的兩台電腦之間的通訊可能不會被加密。</span><span class="sxs-lookup"><span data-stu-id="91c1c-131">By default, the communication between two computers that have established a **Remote Connection** session may not be encrypted.</span></span> <span data-ttu-id="91c1c-132">因此，為了協助維護兩個電腦之間的安全性，我們建議兩個電腦都是相同網路的一部分。</span><span class="sxs-lookup"><span data-stu-id="91c1c-132">Therefore, to help maintain security between the two computers, we recommend that both computers are a part of the same network.</span></span>

## <span data-ttu-id="91c1c-133">相關主題</span><span class="sxs-lookup"><span data-stu-id="91c1c-133">Related topics</span></span>


[<span data-ttu-id="91c1c-134">DaRT 8.0 的安全性與隱私權</span><span class="sxs-lookup"><span data-stu-id="91c1c-134">Security and Privacy for DaRT 8.0</span></span>](security-and-privacy-for-dart-80-dart-8.md)

 

 





