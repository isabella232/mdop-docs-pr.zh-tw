---
title: 關於 DaRT 8.0
description: 關於 DaRT 8.0
author: dansimp
ms.assetid: ce91efd6-7d78-44cb-bb8f-1f43f768ebaa
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e70816425dc4775b11596b91d7b5c0045830c6ad
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808661"
---
# <span data-ttu-id="dd4d4-103">關於 DaRT 8.0</span><span class="sxs-lookup"><span data-stu-id="dd4d4-103">About DaRT 8.0</span></span>


<span data-ttu-id="dd4d4-104">Microsoft Diagnostics 與修復工具組（DaRT）8.0 可協助您疑難排解及修復 Windows 電腦。</span><span class="sxs-lookup"><span data-stu-id="dd4d4-104">Microsoft Diagnostics and Recovery Toolset (DaRT) 8.0 helps you troubleshoot and repair Windows-based computers.</span></span> <span data-ttu-id="dd4d4-105">這包括那些無法啟動的電腦。</span><span class="sxs-lookup"><span data-stu-id="dd4d4-105">This includes those computers that cannot be started.</span></span> <span data-ttu-id="dd4d4-106">DaRT 8.0 是一組功能強大的工具，可延伸 Windows 修復環境（WinRE）。</span><span class="sxs-lookup"><span data-stu-id="dd4d4-106">DaRT 8.0 is a powerful set of tools that extend the Windows Recovery Environment (WinRE).</span></span> <span data-ttu-id="dd4d4-107">您可以使用 DaRT 來分析問題，以判斷其原因，例如，檢查電腦的事件記錄或系統登錄。</span><span class="sxs-lookup"><span data-stu-id="dd4d4-107">By using DaRT, you can analyze an issue to determine its cause, for example, by inspecting the computer’s event log or system registry.</span></span> <span data-ttu-id="dd4d4-108">DaRT 支援恢復包含分區的基本硬碟（例如，主要分區及邏輯磁片磁碟機），並支援恢復卷。</span><span class="sxs-lookup"><span data-stu-id="dd4d4-108">DaRT supports the recovery of basic hard disks that contain partitions, for example, primary partitions and logical drives, and supports the recovery of volumes.</span></span>

<span data-ttu-id="dd4d4-109">**記事** DaRT 不支援恢復動態磁碟。</span><span class="sxs-lookup"><span data-stu-id="dd4d4-109">**Note** DaRT does not support the recovery of dynamic disks.</span></span>

 

<span data-ttu-id="dd4d4-110">DaRT 也提供工具，可協助您在判斷原因後立即修正問題。</span><span class="sxs-lookup"><span data-stu-id="dd4d4-110">DaRT also provides tools to help you fix a problem as soon as you determine the cause.</span></span> <span data-ttu-id="dd4d4-111">例如，您可以使用 DaRT 中的工具來停用有問題的裝置驅動程式、移除修補程式、還原已刪除的檔案，以及在電腦上掃描惡意程式碼，即使您無法或不應該啟動已安裝的 Windows 作業系統時也一樣。</span><span class="sxs-lookup"><span data-stu-id="dd4d4-111">For example, you can use the tools in DaRT to disable a faulty device driver, remove hotfixes, restore deleted files, and scan the computer for malware even when you cannot or should not start the installed Windows operating system.</span></span>

<span data-ttu-id="dd4d4-112">DaRT 可協助您快速復原執行32位或64位版本 Windows 8 的電腦，通常會比重新鏡像電腦所需的時間少。</span><span class="sxs-lookup"><span data-stu-id="dd4d4-112">DaRT can help you quickly recover computers that are running either 32-bit or 64-bit versions of Windows 8, typically in less time than it would take to reimage the computer.</span></span>

<span data-ttu-id="dd4d4-113">DaRT 中的功能可讓您建立恢復影像。</span><span class="sxs-lookup"><span data-stu-id="dd4d4-113">Functionality in DaRT lets you create a recovery image.</span></span> <span data-ttu-id="dd4d4-114">復原影像會啟動 Windows 修復環境（Windows RE），您可以從這裡啟動 [**診斷及修復工具集**] 視窗並存取 DaRT 工具。</span><span class="sxs-lookup"><span data-stu-id="dd4d4-114">The recovery image starts Windows Recovery Environment (Windows RE), from which you can start the **Diagnostics and Recovery Toolset** window and access the DaRT tools.</span></span>

<span data-ttu-id="dd4d4-115">使用**Dart 復原映像嚮導**來建立 DaRT 復原影像。</span><span class="sxs-lookup"><span data-stu-id="dd4d4-115">Use the **DaRT Recovery Image Wizard** to create the DaRT recovery image.</span></span> <span data-ttu-id="dd4d4-116">根據預設，此嚮導會建立國際標準化組織（ISO）圖像檔案和 Windows Imaging 格式（WIM）檔案，並讓您將影像燒錄至 CD、DVD 或 USB。</span><span class="sxs-lookup"><span data-stu-id="dd4d4-116">By default, the wizard creates an International Organization for Standardization (ISO) image file and a Windows Imaging Format (WIM) file and let you burn the image to a CD, DVD, or USB.</span></span> <span data-ttu-id="dd4d4-117">您可以在使用者的電腦上本機部署映射，或者您可以從遠端網路分區或本機硬碟上的復原分區進行部署。</span><span class="sxs-lookup"><span data-stu-id="dd4d4-117">You can deploy the image locally at end user’s computers, or you can deploy it from a remote network partition or a recovery partition on the local hard drive.</span></span>

## <a href="" id="what-s-new-in-dart-8-0"></a><span data-ttu-id="dd4d4-118">DaRT 8.0 的新功能</span><span class="sxs-lookup"><span data-stu-id="dd4d4-118">What’s new in DaRT 8.0</span></span>


<span data-ttu-id="dd4d4-119">DaRT 8.0 可協助您快速復原執行32位或64位版本的 Windows 8 的電腦，通常會比重新鏡像電腦所需的時間少。</span><span class="sxs-lookup"><span data-stu-id="dd4d4-119">DaRT 8.0 can help you quickly recover computers that are running either 32-bit or 64-bit versions of Windows 8, typically in less time than it would take to reimage the computer.</span></span> <span data-ttu-id="dd4d4-120">DaRT 8.0 具有下列新功能。</span><span class="sxs-lookup"><span data-stu-id="dd4d4-120">DaRT 8.0 has the following new features.</span></span>

### <span data-ttu-id="dd4d4-121">使用 Windows 8 或 Windows Server 2012 建立 DaRT 映射</span><span class="sxs-lookup"><span data-stu-id="dd4d4-121">Create DaRT images by using Windows 8 or Windows Server 2012</span></span>

<span data-ttu-id="dd4d4-122">DaRT 8.0 可讓您使用 Windows®8或 Windows Server®2012來建立 DaRT 影像。</span><span class="sxs-lookup"><span data-stu-id="dd4d4-122">DaRT 8.0 enables you to create DaRT images using either Windows® 8 or Windows Server® 2012.</span></span> <span data-ttu-id="dd4d4-123">針對 Windows 8 和 Windows Server 2012 之前版本的 Windows，客戶應繼續使用舊版的 DaRT。</span><span class="sxs-lookup"><span data-stu-id="dd4d4-123">For versions of Windows earlier than Windows 8 and Windows Server 2012, customers should continue to use earlier versions of DaRT.</span></span>

### <span data-ttu-id="dd4d4-124">從一部電腦產生32與64位的影像</span><span class="sxs-lookup"><span data-stu-id="dd4d4-124">Generate both 32- and 64-bit images from one computer</span></span>

<span data-ttu-id="dd4d4-125">DaRT 8.0 可讓您從執行 DaRT 的單一電腦（無論電腦是32或64電腦），同時產生32位和64位的影像。</span><span class="sxs-lookup"><span data-stu-id="dd4d4-125">DaRT 8.0 enables you to generate both 32-bit and 64-bit images from a single computer that is running DaRT, regardless of whether the computer is a 32-bit or 64-bit computer.</span></span> <span data-ttu-id="dd4d4-126">在 DaRT7 中，建立的影像必須是與執行 DaRT 的電腦相同、比對。</span><span class="sxs-lookup"><span data-stu-id="dd4d4-126">In DaRT7, the image that was created had to be the same, bit-wise, as the computer that was running DaRT.</span></span>

### <span data-ttu-id="dd4d4-127">建立一個支援具有 BIOS 或 UEFI 介面的電腦的影像</span><span class="sxs-lookup"><span data-stu-id="dd4d4-127">Create one image that supports computers that have either a BIOS or UEFI interface</span></span>

<span data-ttu-id="dd4d4-128">DaRT 8.0 支援整合的可延伸韌體介面（UEFI）和 BIOS 介面，可讓您只建立一個可搭配有任何介面的電腦使用的影像。</span><span class="sxs-lookup"><span data-stu-id="dd4d4-128">DaRT 8.0’s support for both the Unified Extensible Firmware Interface (UEFI) and BIOS interfaces enables you to create just one image that works with computers that have either interface.</span></span>

### <span data-ttu-id="dd4d4-129">使用 GUID 分區表（GPT）進行分區</span><span class="sxs-lookup"><span data-stu-id="dd4d4-129">Use a GUID partition table (GPT) for partitioning</span></span>

<span data-ttu-id="dd4d4-130">DaRT 8.0 工具現在支援 Windows 8 GPT 磁片，可提供比舊版主開機記錄（MBR）分區配置更具彈性的磁碟分割方案。</span><span class="sxs-lookup"><span data-stu-id="dd4d4-130">DaRT 8.0 tools now support Windows 8 GPT disks, which provide a more flexible mechanism for partitioning disks than the older master boot record (MBR) partitioning scheme.</span></span> <span data-ttu-id="dd4d4-131">DaRT 8.0 工具繼續支援 MBR 分區。</span><span class="sxs-lookup"><span data-stu-id="dd4d4-131">DaRT 8.0 tools continue to support MBR partitioning.</span></span>

### <span data-ttu-id="dd4d4-132">在本機硬碟上安裝 Windows 8 和 Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="dd4d4-132">Install Windows 8 and Windows Server 2012 on the local hard disk</span></span>

<span data-ttu-id="dd4d4-133">DaRT 8.0 工具只能在 Windows 8 和 Windows Server 2012 安裝在本機硬碟上時使用。</span><span class="sxs-lookup"><span data-stu-id="dd4d4-133">DaRT 8.0 tools can be used only when Windows 8 and Windows Server 2012 are installed on the local hard disk.</span></span> <span data-ttu-id="dd4d4-134">目前不支援 Windows 的功能。</span><span class="sxs-lookup"><span data-stu-id="dd4d4-134">Currently, there is no support for Windows To Go.</span></span>

### <a href="" id="-------------dart-8-0-release-notes"></a> <span data-ttu-id="dd4d4-135">DaRT 8.0 版本資訊</span><span class="sxs-lookup"><span data-stu-id="dd4d4-135">DaRT 8.0 release notes</span></span>

<span data-ttu-id="dd4d4-136">如需詳細資訊，以及未在檔中顯示的最新消息，請參閱[DaRT 8.0 的版本](release-notes-for-dart-80--dart-8.md)資訊。</span><span class="sxs-lookup"><span data-stu-id="dd4d4-136">For more information, and for late-breaking news that did not make it into the documentation, see the [Release Notes for DaRT 8.0](release-notes-for-dart-80--dart-8.md).</span></span>

## <span data-ttu-id="dd4d4-137">如何取得 DaRT 8。0</span><span class="sxs-lookup"><span data-stu-id="dd4d4-137">How to Get DaRT 8.0</span></span>


<span data-ttu-id="dd4d4-138">這項技術是 Microsoft 桌面優化套件（MDOP）的一部分。</span><span class="sxs-lookup"><span data-stu-id="dd4d4-138">This technology is a part of the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="dd4d4-139">MDOP 是 Microsoft 軟體保證的一部分。</span><span class="sxs-lookup"><span data-stu-id="dd4d4-139">MDOP is part of Microsoft Software Assurance.</span></span> <span data-ttu-id="dd4d4-140">如需 Microsoft 軟體保證及取得 MDOP 的詳細資訊，請參閱[如何取得 mdop](https://go.microsoft.com/fwlink/?LinkId=322049) （ https://go.microsoft.com/fwlink/?LinkId=322049) 。</span><span class="sxs-lookup"><span data-stu-id="dd4d4-140">For more information about Microsoft Software Assurance and acquiring MDOP, see [How Do I Get MDOP](https://go.microsoft.com/fwlink/?LinkId=322049) (https://go.microsoft.com/fwlink/?LinkId=322049).</span></span>

## <span data-ttu-id="dd4d4-141">相關主題</span><span class="sxs-lookup"><span data-stu-id="dd4d4-141">Related topics</span></span>


[<span data-ttu-id="dd4d4-142">開始使用 DaRT 8.0</span><span class="sxs-lookup"><span data-stu-id="dd4d4-142">Getting Started with DaRT 8.0</span></span>](getting-started-with-dart-80-dart-8.md)

[<span data-ttu-id="dd4d4-143">DaRT 8.0 版本資訊</span><span class="sxs-lookup"><span data-stu-id="dd4d4-143">Release Notes for DaRT 8.0</span></span>](release-notes-for-dart-80--dart-8.md)

 

 





