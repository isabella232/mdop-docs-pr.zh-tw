---
title: 建立 DaRT 7.0 復原映像
description: 建立 DaRT 7.0 復原映像
author: dansimp
ms.assetid: ebb2ec58-0349-469d-a23f-3f944fe4c1fa
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f19ff144cac61ca7ea5a8498f67caf8a99229d77
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809861"
---
# <span data-ttu-id="ac753-103">建立 DaRT 7.0 復原映像</span><span class="sxs-lookup"><span data-stu-id="ac753-103">Creating the DaRT 7.0 Recovery Image</span></span>


<span data-ttu-id="ac753-104">Microsoft Diagnostics 與修復工具組（DaRT）7包含 Windows 中用來建立可引導的國際標準組織（ISO）影像的**DaRT 復原影像嚮導**。</span><span class="sxs-lookup"><span data-stu-id="ac753-104">Microsoft Diagnostics and Recovery Toolset (DaRT)7 includes the **DaRT Recovery Image Wizard** that is used in Windows to create a bootable International Organization for Standardization (ISO) image.</span></span> <span data-ttu-id="ac753-105">ISO 影像是代表 CD 原始內容的檔案。</span><span class="sxs-lookup"><span data-stu-id="ac753-105">An ISO image is a file that represents the raw contents of a CD.</span></span>

## <span data-ttu-id="ac753-106">使用 DaRT 復原映像嚮導來建立恢復影像</span><span class="sxs-lookup"><span data-stu-id="ac753-106">Use the DaRT Recovery Image Wizard to Create the Recovery Image</span></span>


<span data-ttu-id="ac753-107">由 DaRT 復原映射嚮導建立的 ISO 包含可讓您啟動至有問題電腦的 DaRT 復原影像，即使它可能不會啟動也一樣。</span><span class="sxs-lookup"><span data-stu-id="ac753-107">The ISO created by the DaRT Recovery Image Wizard contains the DaRT recovery image that lets you boot into a problem computer, even if it might otherwise not start.</span></span> <span data-ttu-id="ac753-108">將電腦引導至 DaRT 之後，您可以執行不同的 DaRT 工具來嘗試診斷並修復電腦。</span><span class="sxs-lookup"><span data-stu-id="ac753-108">After you boot the computer into DaRT, you can run the different DaRT tools to try to diagnose and repair the computer.</span></span>

<span data-ttu-id="ac753-109">您可以將 ISO 寫入可錄製的 CD 或 DVD、將其儲存至 USB 快閃磁片磁碟機，或將它儲存為可從遠端分區或從復原分區引導至 DaRT 的格式。</span><span class="sxs-lookup"><span data-stu-id="ac753-109">You can write the ISO to a recordable CD or DVD, save it to a USB flash drive, or save it in a format that you can use to boot into DaRT from a remote partition or from a recovery partition.</span></span> <span data-ttu-id="ac753-110">如需詳細資訊，請參閱[部署 DaRT 7.0 恢復影像](deploying-the-dart-70-recovery-image-dart-7.md)。</span><span class="sxs-lookup"><span data-stu-id="ac753-110">For more information, see [Deploying the DaRT 7.0 Recovery Image](deploying-the-dart-70-recovery-image-dart-7.md).</span></span>

<span data-ttu-id="ac753-111">**記事** 如果您的電腦包含 cd-rw 磁片磁碟機，此嚮導會提供將 ISO 影像燒錄至空白的 CD 或 DVD。</span><span class="sxs-lookup"><span data-stu-id="ac753-111">**Note** If your computer includes a CD-RW drive, the wizard offers to burn the ISO image to a blank CD or DVD.</span></span> <span data-ttu-id="ac753-112">如果您的電腦不包含嚮導所支援的磁片磁碟機，您可以使用大多數可以燒錄 CD 或 DVD 的程式，將 ISO 影像燒制到 CD 或 DVD 上。</span><span class="sxs-lookup"><span data-stu-id="ac753-112">If your computer does not include a drive that is supported by the wizard, you can burn the ISO image onto a CD or DVD by using most programs that can burn a CD or DVD.</span></span>

 

<span data-ttu-id="ac753-113">若要從 ISO 影像建立可啟動的 CD 或 DVD，您必須具備：</span><span class="sxs-lookup"><span data-stu-id="ac753-113">To create a bootable CD or DVD from the ISO image, you must have:</span></span>

-   <span data-ttu-id="ac753-114">CD-RW 磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="ac753-114">A CD-RW drive.</span></span>

-   <span data-ttu-id="ac753-115">可錄製的 CD 或 DVD （採用可燒錄磁片磁碟機支援的格式）。</span><span class="sxs-lookup"><span data-stu-id="ac753-115">A recordable CD or DVD (in a format supported by the recordable drive).</span></span>

-   <span data-ttu-id="ac753-116">支援可燒錄磁片磁碟機並支援將 ISO 影像直接燒錄至 CD 或 DVD 的軟體。</span><span class="sxs-lookup"><span data-stu-id="ac753-116">Software that supports the recordable drive and supports burning an ISO image directly to CD or DVD.</span></span>

    <span data-ttu-id="ac753-117">**重要** 在您想要支援的所有不同電腦上，測試您所建立的 CD 或 DVD，因為部分電腦無法從所有類型的可錄製媒體啟動。</span><span class="sxs-lookup"><span data-stu-id="ac753-117">**Important** Test the CD or DVD that you create on all the different kinds of computers that you intend to support because some computers cannot start from all kinds of recordable media.</span></span>

     

<span data-ttu-id="ac753-118">若要將 ISO 影像儲存至 USB 快閃記憶體磁片磁碟機（UFD），您必須具備：</span><span class="sxs-lookup"><span data-stu-id="ac753-118">To save the ISO image to a USB flash drive (UFD), you must have:</span></span>

-   <span data-ttu-id="ac753-119">格式正確的 UFD。</span><span class="sxs-lookup"><span data-stu-id="ac753-119">A correctly formatted UFD.</span></span>

-   <span data-ttu-id="ac753-120">您可以用來裝載 ISO 映像的程式。</span><span class="sxs-lookup"><span data-stu-id="ac753-120">A program that you can use to mount the ISO image.</span></span>

[<span data-ttu-id="ac753-121">如何使用 DaRT 復原映像精靈來建立復原映像</span><span class="sxs-lookup"><span data-stu-id="ac753-121">How to Use the DaRT Recovery Image Wizard to Create the Recovery Image</span></span>](how-to-use-the-dart-recovery-image-wizard-to-create-the-recovery-image-dart-7.md)

## <span data-ttu-id="ac753-122">建立限制時間的復原影像</span><span class="sxs-lookup"><span data-stu-id="ac753-122">Create a Time Limited Recovery Image</span></span>


<span data-ttu-id="ac753-123">您可以建立一個只能在產生特定天數後使用的 DaRT 恢復影像。</span><span class="sxs-lookup"><span data-stu-id="ac753-123">You can create a DaRT recovery image that can only be used for a certain number of days after it is generated.</span></span> <span data-ttu-id="ac753-124">若要這樣做，您必須在命令提示字元執行**DaRT 復原映射嚮導**，並指定天數。</span><span class="sxs-lookup"><span data-stu-id="ac753-124">To do this, you must run the **DaRT Recovery Image Wizard** at a command prompt and specify the number of days.</span></span>

[<span data-ttu-id="ac753-125">如何建立限時復原映像</span><span class="sxs-lookup"><span data-stu-id="ac753-125">How to Create a Time Limited Recovery Image</span></span>](how-to-create-a-time-limited-recovery-image-dart-7.md)

## <span data-ttu-id="ac753-126">建立 DaRT7 復原影像的其他資源</span><span class="sxs-lookup"><span data-stu-id="ac753-126">Other resources for creating the DaRT7 recovery image</span></span>


-   [<span data-ttu-id="ac753-127">部署 DaRT 7.0</span><span class="sxs-lookup"><span data-stu-id="ac753-127">Deploying DaRT 7.0</span></span>](deploying-dart-70-new-ia.md)

 

 





