---
title: 規劃建立 DaRT 7.0 復原映像
description: 規劃建立 DaRT 7.0 復原映像
author: dansimp
ms.assetid: e5d49bee-ae4e-467b-9976-c1203f6355f9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: c370d2a69ec8ccea217696045e64e9a0ae724815
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808691"
---
# <span data-ttu-id="6b837-103">規劃建立 DaRT 7.0 復原映像</span><span class="sxs-lookup"><span data-stu-id="6b837-103">Planning to Create the DaRT 7.0 Recovery Image</span></span>


<span data-ttu-id="6b837-104">當您規劃建立 Microsoft Diagnostics 與復原工具集（DaRT）7復原影像時，請使用本節中的資訊。</span><span class="sxs-lookup"><span data-stu-id="6b837-104">Use the information in this section when you plan for creating the Microsoft Diagnostics and Recovery Toolset (DaRT)7 recovery image.</span></span>

## <span data-ttu-id="6b837-105">規劃以建立 DaRT 7 恢復影像</span><span class="sxs-lookup"><span data-stu-id="6b837-105">Planning to Create the DaRT 7 Recovery Image</span></span>


<span data-ttu-id="6b837-106">當您建立 DaRT 復原影像時，必須決定要在影像中包含哪些工具。</span><span class="sxs-lookup"><span data-stu-id="6b837-106">When you create the DaRT recovery image, you have to decide which tools to include on the image.</span></span> <span data-ttu-id="6b837-107">當您作出決定時，請記住，最終使用者可能會偶爾存取各種 DaRT 工具。</span><span class="sxs-lookup"><span data-stu-id="6b837-107">When you make that decision, remember that end users might have access occasionally to the various DaRT tools.</span></span> <span data-ttu-id="6b837-108">如需有關 DaRT 工具的詳細資訊，請參閱[dart 7.0 中的工具概覽](overview-of-the-tools-in-dart-70-new-ia.md)。</span><span class="sxs-lookup"><span data-stu-id="6b837-108">For more information about the DaRT tools, see [Overview of the Tools in DaRT 7.0](overview-of-the-tools-in-dart-70-new-ia.md).</span></span> <span data-ttu-id="6b837-109">如需如何協助建立安全的復原影像的詳細資訊，請參閱[DaRT 7.0 的安全性考慮](security-considerations-for-dart-70-dart-7.md)。</span><span class="sxs-lookup"><span data-stu-id="6b837-109">For more information about how to help create a secure recovery image, see [Security Considerations for DaRT 7.0](security-considerations-for-dart-70-dart-7.md).</span></span>

<span data-ttu-id="6b837-110">當您建立 DaRT 恢復影像時，您也會指定是否要包含其他驅動程式或檔案。</span><span class="sxs-lookup"><span data-stu-id="6b837-110">When you create the DaRT recovery image, you will also specify whether you want to include additional drivers or files.</span></span> <span data-ttu-id="6b837-111">決定您想要包含在 DaRT 復原影像中的任何其他驅動程式或檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="6b837-111">Determine the locations of any additional drivers or files that you want to include on the DaRT recovery image.</span></span>

## <span data-ttu-id="6b837-112">必要條件</span><span class="sxs-lookup"><span data-stu-id="6b837-112">Prerequisites</span></span>


<span data-ttu-id="6b837-113">建立 DaRT 復原影像時，必須使用下列專案：</span><span class="sxs-lookup"><span data-stu-id="6b837-113">The following items are required or recommended for creating the DaRT recovery image:</span></span>

-   <span data-ttu-id="6b837-114">Windows 7 來源檔案</span><span class="sxs-lookup"><span data-stu-id="6b837-114">Windows 7 source files</span></span>

    <span data-ttu-id="6b837-115">您必須提供 Windows 7 DVD 或 Windows 7 來源檔案的路徑。</span><span class="sxs-lookup"><span data-stu-id="6b837-115">You must provide the path of a Windows 7 DVD or of Windows 7 source files.</span></span> <span data-ttu-id="6b837-116">Windows 7 來源檔案是建立 DaRT 復原影像所必需的。</span><span class="sxs-lookup"><span data-stu-id="6b837-116">Windows 7 source files are required to create the DaRT recovery image.</span></span>

-   <span data-ttu-id="6b837-117">適用于您平臺的 Windows 調試工具</span><span class="sxs-lookup"><span data-stu-id="6b837-117">Windows Debugging Tools for your platform</span></span>

    <span data-ttu-id="6b837-118">當您執行**系統崩潰分析**程式來判斷電腦當機的原因時，必須使用 Windows 調試工具。</span><span class="sxs-lookup"><span data-stu-id="6b837-118">Windows Debugging Tools are required when you run **Crash Analyzer** to determine the cause of a computer crash.</span></span> <span data-ttu-id="6b837-119">我們建議您在建立 DaRT 恢復影像時，指定 Windows 調試工具的路徑。</span><span class="sxs-lookup"><span data-stu-id="6b837-119">We recommend that you specify the path of the Windows Debugging Tools at the time that you create the DaRT recovery image.</span></span> <span data-ttu-id="6b837-120">如有需要，您可以在這裡下載 Windows 調試工具：[下載並安裝 windows 的調試工具](https://go.microsoft.com/fwlink/?LinkId=99934)。</span><span class="sxs-lookup"><span data-stu-id="6b837-120">If it is necessary, you can download the Windows Debugging Tools here: [Download and Install Debugging Tools for Windows](https://go.microsoft.com/fwlink/?LinkId=99934).</span></span>

-   <span data-ttu-id="6b837-121">選用：**獨立系統 Sweeper**定義</span><span class="sxs-lookup"><span data-stu-id="6b837-121">Optional: **Standalone System Sweeper** definitions</span></span>

    <span data-ttu-id="6b837-122">當您執行此工具時，會需要**獨立系統 Sweeper**的最新定義。</span><span class="sxs-lookup"><span data-stu-id="6b837-122">The latest definitions for the **Standalone System Sweeper** are required when you run this tool.</span></span> <span data-ttu-id="6b837-123">雖然您可以在執行**獨立系統 Sweeper**時下載定義，但我們建議您在建立 DaRT 恢復影像時，下載最新的定義。</span><span class="sxs-lookup"><span data-stu-id="6b837-123">Although you can download the definitions when you run **Standalone System Sweeper**, we recommend that you download the latest definitions at the time you create the DaRT recovery image.</span></span> <span data-ttu-id="6b837-124">如此一來，即使有問題的電腦沒有網路連線，您仍然可以使用最新的定義來執行工具。</span><span class="sxs-lookup"><span data-stu-id="6b837-124">In this manner, you can still run the tool with the latest definitions even if the problem computer does not have network connectivity.</span></span>

-   <span data-ttu-id="6b837-125">[選用]： Windows 符號檔案以用於**故障分析**程式</span><span class="sxs-lookup"><span data-stu-id="6b837-125">Optional: Windows symbols files for use with **Crash Analyzer**</span></span>

    <span data-ttu-id="6b837-126">通常，調試資訊會儲存在符號檔案中，與可執行檔不同。</span><span class="sxs-lookup"><span data-stu-id="6b837-126">Typically, debugging information is stored in a symbol file that is separate from the executable.</span></span> <span data-ttu-id="6b837-127">調試已停止回應的應用程式時，您必須具備符號資訊的存取權（例如，如果它已損壞）。</span><span class="sxs-lookup"><span data-stu-id="6b837-127">You must have access to the symbol information when you debug an application that has stopped responding, for example if it crashed.</span></span> <span data-ttu-id="6b837-128">如需詳細資訊，請參閱[使用故障分析程式診斷系統失敗](diagnosing-system-failures-with-crash-analyzer--dart-7.md)。</span><span class="sxs-lookup"><span data-stu-id="6b837-128">For more information, see [Diagnosing System Failures with Crash Analyzer](diagnosing-system-failures-with-crash-analyzer--dart-7.md).</span></span>

## <span data-ttu-id="6b837-129">相關主題</span><span class="sxs-lookup"><span data-stu-id="6b837-129">Related topics</span></span>


[<span data-ttu-id="6b837-130">規劃部署 DaRT 7.0</span><span class="sxs-lookup"><span data-stu-id="6b837-130">Planning to Deploy DaRT 7.0</span></span>](planning-to-deploy-dart-70.md)

 

 





