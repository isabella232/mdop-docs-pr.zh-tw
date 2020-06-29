---
title: 關於 DaRT 7.0
description: 關於 DaRT 7.0
author: dansimp
ms.assetid: 217ffafc-6d73-4b80-88d9-71870460d4ab
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cd647b2f596ce88ce38580f08422ff8f92b35c06
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809855"
---
# <span data-ttu-id="a69ef-103">關於 DaRT 7.0</span><span class="sxs-lookup"><span data-stu-id="a69ef-103">About DaRT 7.0</span></span>


<span data-ttu-id="a69ef-104">Microsoft 診斷和修復工具組（DaRT）7可協助您疑難排解及修復 Windows 桌上型電腦。</span><span class="sxs-lookup"><span data-stu-id="a69ef-104">Microsoft Diagnostics and Recovery Toolset (DaRT)7 helps you troubleshoot and repair Windows-based desktops.</span></span> <span data-ttu-id="a69ef-105">這包含那些無法啟動的桌面。</span><span class="sxs-lookup"><span data-stu-id="a69ef-105">This includes those desktops that cannot be started.</span></span> <span data-ttu-id="a69ef-106">DaRT 是一組可延伸 Windows 復原環境（WinRE）的強大工具。</span><span class="sxs-lookup"><span data-stu-id="a69ef-106">DaRT is a powerful set of tools that extend the Windows Recovery Environment (WinRE).</span></span> <span data-ttu-id="a69ef-107">您可以使用 DaRT 來分析問題，以判斷其原因，例如，檢查電腦的事件記錄或系統登錄。</span><span class="sxs-lookup"><span data-stu-id="a69ef-107">By using DaRT, you can analyze an issue to determine its cause, for example, by inspecting the computer’s event log or system registry.</span></span>

<span data-ttu-id="a69ef-108">DaRT 也提供工具，可協助您在判斷原因後立即修正問題。</span><span class="sxs-lookup"><span data-stu-id="a69ef-108">DaRT also provides tools to help you fix a problem as soon as you determine the cause.</span></span> <span data-ttu-id="a69ef-109">例如，您可以使用 DaRT 中的工具來停用有問題的裝置驅動程式、移除修補程式、還原已刪除的檔案，以及在電腦上掃描惡意程式碼，即使您無法或不應該啟動已安裝的 Windows 作業系統時也一樣。</span><span class="sxs-lookup"><span data-stu-id="a69ef-109">For example, you can use the tools in DaRT to disable a faulty device driver, remove hotfixes, restore deleted files, and scan the computer for malware even when you cannot or should not start the installed Windows operating system.</span></span>

<span data-ttu-id="a69ef-110">DaRT 可協助您快速復原執行32位或64位版本 Windows 7 的電腦，通常會比重新鏡像電腦所需的時間少。</span><span class="sxs-lookup"><span data-stu-id="a69ef-110">DaRT can help you quickly recover computers that are running either 32-bit or 64-bit versions of Windows 7, typically in less time than it would take to reimage the computer.</span></span>

## <span data-ttu-id="a69ef-111">關於 DaRT 7 恢復影像</span><span class="sxs-lookup"><span data-stu-id="a69ef-111">About the DaRT 7 Recovery Image</span></span>


<span data-ttu-id="a69ef-112">DaRT 中的功能可讓您建立根據 WinRE 結合 DaRT 所提供之工具的 [恢復] 影像。</span><span class="sxs-lookup"><span data-stu-id="a69ef-112">Functionality in DaRT lets you create a recovery image that is based on WinRE combined with a set of tools that DaRT provides.</span></span> <span data-ttu-id="a69ef-113">DaRT 復原影像會利用 WinRE，您可以在其中存取 [**診斷與修復工具**組] 視窗。</span><span class="sxs-lookup"><span data-stu-id="a69ef-113">The DaRT recovery image takes advantage of WinRE, from which you can access the **Diagnostics and Recovery Toolset** window.</span></span>

<span data-ttu-id="a69ef-114">使用**Dart 復原映像嚮導**來建立 DaRT 復原影像。</span><span class="sxs-lookup"><span data-stu-id="a69ef-114">Use the **DaRT Recovery Image Wizard** to create the DaRT recovery image.</span></span> <span data-ttu-id="a69ef-115">根據預設，此嚮導會在桌面上建立名為 DaRT70 的國際組織結構檔案，不過您可以指定不同的位置和檔案名。</span><span class="sxs-lookup"><span data-stu-id="a69ef-115">By default, the wizard creates an International Organization for Standardization (ISO) image file on your desktop that is named DaRT70.iso, although you can specify a different location and file name.</span></span> <span data-ttu-id="a69ef-116">此嚮導也可讓您將影像燒制到 CD 或 DVD。</span><span class="sxs-lookup"><span data-stu-id="a69ef-116">The wizard also lets you burn the image to a CD or DVD.</span></span> <span data-ttu-id="a69ef-117">完成嚮導之後，您可以將復原影像儲存至 USB 快閃磁碟機，或將它儲存為您可以用來建立遠端分區或復原分區的格式。</span><span class="sxs-lookup"><span data-stu-id="a69ef-117">After you have finished the wizard, you can save the recovery image to a USB flash drive or save it in a format that you can use to create a remote partition or a recovery partition.</span></span>

<span data-ttu-id="a69ef-118">當您必須使用 DaRT 啟動無法啟動的終端使用者電腦時，您可以按照指示[使用 Dart 復原影像來復原本機電腦](how-to-recover-local-computers-using-the-dart-recovery-image-dart-7.md)。</span><span class="sxs-lookup"><span data-stu-id="a69ef-118">When you have to use DaRT to startup an end-user computer that will not start, you can follow the instructions at [How to Recover Local Computers Using the DaRT Recovery Image](how-to-recover-local-computers-using-the-dart-recovery-image-dart-7.md).</span></span>

<span data-ttu-id="a69ef-119">如需有關 DaRT 工具的詳細資訊，請參閱[dart 7.0 中的工具概覽](overview-of-the-tools-in-dart-70-new-ia.md)。</span><span class="sxs-lookup"><span data-stu-id="a69ef-119">For detailed information about the tools in DaRT, see [Overview of the Tools in DaRT 7.0](overview-of-the-tools-in-dart-70-new-ia.md).</span></span>

## <a href="" id="what-s-new-in-dart-7"></a><span data-ttu-id="a69ef-120">DaRT 7 的新功能</span><span class="sxs-lookup"><span data-stu-id="a69ef-120">What’s New in DaRT 7</span></span>


<span data-ttu-id="a69ef-121">DaRT7 會繼續支援先前版本中包含的所有案例，而且除了三種新的部署選項之外，它還會新增新的遠端連線功能。</span><span class="sxs-lookup"><span data-stu-id="a69ef-121">DaRT7 continues to support all the scenarios included in previous versions and it adds a new Remote Connection feature in addition to three new deployment options.</span></span>

### <span data-ttu-id="a69ef-122">DaRT 7 影像建立</span><span class="sxs-lookup"><span data-stu-id="a69ef-122">DaRT 7 Image Creation</span></span>

<span data-ttu-id="a69ef-123">您用來建立 DaRT ISO 映像的嚮導現在稱為 DaRT 復原**影像**，現在支援啟用或停用新的遠端連線功能的選項。</span><span class="sxs-lookup"><span data-stu-id="a69ef-123">The wizard that you use to create DaRT ISO images is now called **DaRT Recovery Image** and it now supports an option to enable or disable the new Remote Connection feature.</span></span> <span data-ttu-id="a69ef-124">[遠端連線] 可讓支援人員代理程式從遠端位置執行 DaRT 工具。</span><span class="sxs-lookup"><span data-stu-id="a69ef-124">Remote Connection lets a helpdesk agent run the DaRT tools from a remote location.</span></span> <span data-ttu-id="a69ef-125">在先前的版本中，服務台代理程式必須在最終使用者電腦上實際出現，才能執行 DaRT 工具。</span><span class="sxs-lookup"><span data-stu-id="a69ef-125">In previous releases, the helpdesk agent had to be physically present at the end-user computer to run the DaRT tools.</span></span>

<span data-ttu-id="a69ef-126">此嚮導也可讓您自訂遠端連線功能的歡迎訊息（當使用者執行遠端連線工具時，就會顯示訊息）。</span><span class="sxs-lookup"><span data-stu-id="a69ef-126">The wizard also lets you customize the Welcome message for the Remote Connection feature (the message is shown when end users run the Remote Connection tool).</span></span> <span data-ttu-id="a69ef-127">IT 管理員也可以設定遠端連線應使用哪個埠號。</span><span class="sxs-lookup"><span data-stu-id="a69ef-127">IT Admins can also configure which Port Number should be used by Remote Connection.</span></span>

<span data-ttu-id="a69ef-128">如需**DaRT 復原映射嚮導**或遠端連線的詳細資訊，請參閱[建立 DaRT 7.0 復原影像](creating-the-dart-70-recovery-image-dart-7.md)。</span><span class="sxs-lookup"><span data-stu-id="a69ef-128">For more information about the **DaRT Recovery Image Wizard** or Remote Connection, see [Creating the DaRT 7.0 Recovery Image](creating-the-dart-70-recovery-image-dart-7.md).</span></span>

### <span data-ttu-id="a69ef-129">DaRT 7 部署</span><span class="sxs-lookup"><span data-stu-id="a69ef-129">DaRT 7 ISO Deployment</span></span>

<span data-ttu-id="a69ef-130">除了燒錄至 CD 或 DVD 之外，DaRT7 會在您部署包含 DaRT 復原影像的 ISO 時新增三個新選項：</span><span class="sxs-lookup"><span data-stu-id="a69ef-130">In addition to burning to a CD or DVD, DaRT7 adds three new options when you deploy the ISO that contains the DaRT recovery image:</span></span>

-   <span data-ttu-id="a69ef-131">USB 快閃記憶體磁片磁碟機部署</span><span class="sxs-lookup"><span data-stu-id="a69ef-131">USB flash drive deployment</span></span>

-   <span data-ttu-id="a69ef-132">遠端分區部署</span><span class="sxs-lookup"><span data-stu-id="a69ef-132">Remote partition deployment</span></span>

-   <span data-ttu-id="a69ef-133">恢復分區部署</span><span class="sxs-lookup"><span data-stu-id="a69ef-133">Recovery partition deployment</span></span>

<span data-ttu-id="a69ef-134">USB 快閃記憶體磁片磁碟機部署選項可讓公司在未提供 CD 或 DVD 光碟機的電腦上使用 DaRT。</span><span class="sxs-lookup"><span data-stu-id="a69ef-134">The USB flash drive deployment option lets a company use DaRT on computers that do not have CD or DVD drives available.</span></span> <span data-ttu-id="a69ef-135">[恢復] 和 [遠端分區] 選項可讓使用者輕鬆存取 DaRT 映射，並啟用遠端連線功能。</span><span class="sxs-lookup"><span data-stu-id="a69ef-135">The recovery and remote partition options let end users have easy access to the DaRT image and to enable the Remote Connection functionality.</span></span>

<span data-ttu-id="a69ef-136">如需有關如何部署 DaRT 復原影像的詳細資訊，請參閱[部署 dart 7.0 復原映像](deploying-the-dart-70-recovery-image-dart-7.md)。</span><span class="sxs-lookup"><span data-stu-id="a69ef-136">For more information about how to deploy DaRT recovery images, see [Deploying the DaRT 7.0 Recovery Image](deploying-the-dart-70-recovery-image-dart-7.md).</span></span>

## <span data-ttu-id="a69ef-137">相關主題</span><span class="sxs-lookup"><span data-stu-id="a69ef-137">Related topics</span></span>


[<span data-ttu-id="a69ef-138">開始使用 DaRT 7.0</span><span class="sxs-lookup"><span data-stu-id="a69ef-138">Getting Started with DaRT 7.0</span></span>](getting-started-with-dart-70-new-ia.md)

[<span data-ttu-id="a69ef-139">DaRT 7.0 版本資訊</span><span class="sxs-lookup"><span data-stu-id="a69ef-139">Release Notes for DaRT 7.0</span></span>](release-notes-for-dart-70-new-ia.md)

 

 





