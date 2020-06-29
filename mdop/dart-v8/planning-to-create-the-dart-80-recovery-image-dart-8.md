---
title: 規劃建立 DaRT 8.0 復原映像
description: 規劃建立 DaRT 8.0 復原映像
author: dansimp
ms.assetid: cfd0e1e2-c379-4460-b545-3f7be9f33583
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 1d1dc7dc5b3776638523a282d9216b80d4ce9ce1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810778"
---
# <span data-ttu-id="297b9-103">規劃建立 DaRT 8.0 復原映像</span><span class="sxs-lookup"><span data-stu-id="297b9-103">Planning to Create the DaRT 8.0 Recovery Image</span></span>


<span data-ttu-id="297b9-104">當您計畫建立 Microsoft Diagnostics 與復原工具庫（DaRT）8.0 復原影像時，請使用本節中的資訊。</span><span class="sxs-lookup"><span data-stu-id="297b9-104">Use the information in this section when you are planning to create the Microsoft Diagnostics and Recovery Toolset (DaRT) 8.0 recovery image.</span></span>

## <span data-ttu-id="297b9-105">規劃以建立 DaRT 8.0 恢復影像</span><span class="sxs-lookup"><span data-stu-id="297b9-105">Planning to create the DaRT 8.0 recovery image</span></span>


<span data-ttu-id="297b9-106">當您建立 DaRT 復原影像時，必須決定要在影像中包含哪些工具。</span><span class="sxs-lookup"><span data-stu-id="297b9-106">When you create the DaRT recovery image, you have to decide which tools to include on the image.</span></span> <span data-ttu-id="297b9-107">若要作出決定，請考慮最終使用者可以存取這些工具。</span><span class="sxs-lookup"><span data-stu-id="297b9-107">To make the decision, consider that end users may have access to those tools.</span></span> <span data-ttu-id="297b9-108">如果支援工程師會將復原影像媒體移至最終使用者的電腦，以診斷問題，您可能會想要在恢復影像上安裝所有工具。</span><span class="sxs-lookup"><span data-stu-id="297b9-108">If support engineers will take the recovery image media to end users’ computers to diagnose issues, you may want to install all of the tools on the recovery image.</span></span> <span data-ttu-id="297b9-109">如果您打算遠端診斷使用者的電腦，您可能會想要停用一些工具，例如 [磁片擦除] 和 [登錄編輯程式]，然後啟用其他工具，包括 [遠端連線]。</span><span class="sxs-lookup"><span data-stu-id="297b9-109">If you plan to diagnose end user’s computers remotely, you may want to disable some of the tools, such as Disk Wipe and Registry Editor, and then enable other tools, including Remote Connection.</span></span>

<span data-ttu-id="297b9-110">當您建立 DaRT 恢復影像時，您也會指定是否要包含其他驅動程式或檔案。</span><span class="sxs-lookup"><span data-stu-id="297b9-110">When you create the DaRT recovery image, you will also specify whether you want to include additional drivers or files.</span></span> <span data-ttu-id="297b9-111">決定您想要包含在 DaRT 復原影像中的任何其他驅動程式或檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="297b9-111">Determine the locations of any additional drivers or files that you want to include on the DaRT recovery image.</span></span>

<span data-ttu-id="297b9-112">如需有關 DaRT 工具的詳細資訊，請參閱[dart 8.0 中的工具概覽](overview-of-the-tools-in-dart-80-dart-8.md)。</span><span class="sxs-lookup"><span data-stu-id="297b9-112">For more information about the DaRT tools, see [Overview of the Tools in DaRT 8.0](overview-of-the-tools-in-dart-80-dart-8.md).</span></span> <span data-ttu-id="297b9-113">如需如何協助建立安全的復原影像的詳細資訊，請參閱[DaRT 8.0 的安全性考慮](security-considerations-for-dart-80--dart-8.md)。</span><span class="sxs-lookup"><span data-stu-id="297b9-113">For more information about how to help create a secure recovery image, see [Security Considerations for DaRT 8.0](security-considerations-for-dart-80--dart-8.md).</span></span>

## <span data-ttu-id="297b9-114">復原映像的先決條件</span><span class="sxs-lookup"><span data-stu-id="297b9-114">Prerequisites for the recovery image</span></span>


<span data-ttu-id="297b9-115">建立 DaRT 復原影像時，必須使用下列專案：</span><span class="sxs-lookup"><span data-stu-id="297b9-115">The following items are required or recommended for creating the DaRT recovery image:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="297b9-116">必備</span><span class="sxs-lookup"><span data-stu-id="297b9-116">Prerequisite</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="297b9-117">詳細資料</span><span class="sxs-lookup"><span data-stu-id="297b9-117">Details</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="297b9-118">Windows 8 來源檔案</span><span class="sxs-lookup"><span data-stu-id="297b9-118">Windows 8 source files</span></span></p></td>
<td align="left"><p><span data-ttu-id="297b9-119">建立 DaRT 復原影像所需。</span><span class="sxs-lookup"><span data-stu-id="297b9-119">Required to create the DaRT recovery image.</span></span> <span data-ttu-id="297b9-120">提供 Windows 8 DVD 或 Windows 8 來源檔案的路徑。</span><span class="sxs-lookup"><span data-stu-id="297b9-120">Provide the path of a Windows 8 DVD or of Windows 8 source files.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="297b9-121">適用于您平臺的 Windows 調試工具</span><span class="sxs-lookup"><span data-stu-id="297b9-121">Windows Debugging Tools for your platform</span></span></p></td>
<td align="left"><p><span data-ttu-id="297b9-122">當您執行 [當 <strong> 機] 分析程式 </strong> 來判斷電腦發生故障的原因時，必須使用此程式。</span><span class="sxs-lookup"><span data-stu-id="297b9-122">Required when you run the <strong>Crash Analyzer</strong> to determine the cause of a computer failure.</span></span> <span data-ttu-id="297b9-123">我們建議您在建立 DaRT 恢復影像時，指定 Windows 調試工具的路徑。</span><span class="sxs-lookup"><span data-stu-id="297b9-123">We recommend that you specify the path of the Windows Debugging Tools at the time that you create the DaRT recovery image.</span></span> <span data-ttu-id="297b9-124">您可以在這裡下載 Windows 調試工具： <a href="https://go.microsoft.com/fwlink/?LinkId=99934" data-raw-source="[Download and Install Debugging Tools for Windows](https://go.microsoft.com/fwlink/?LinkId=99934)"> 下載並安裝 windows 版調試工具 </a> 。</span><span class="sxs-lookup"><span data-stu-id="297b9-124">You can download the Windows Debugging Tools here: <a href="https://go.microsoft.com/fwlink/?LinkId=99934" data-raw-source="[Download and Install Debugging Tools for Windows](https://go.microsoft.com/fwlink/?LinkId=99934)">Download and Install Debugging Tools for Windows</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="297b9-125">選用： <strong> Defender </strong> 定義</span><span class="sxs-lookup"><span data-stu-id="297b9-125">Optional: <strong>Defender</strong> definitions</span></span></p></td>
<td align="left"><p><span data-ttu-id="297b9-126"><strong> </strong> 當您執行 defender 時，需要安裝最新的 defender 定義 <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="297b9-126">The latest definitions for <strong>Defender</strong> are required when you run <strong>Defender</strong>.</span></span> <span data-ttu-id="297b9-127">雖然您可以在執行 Defender 時下載定義 <strong> </strong> ，但我們建議您在建立 DaRT 復原影像時下載最新的定義，讓您仍可以使用最新的定義來執行工具，即使問題電腦沒有網路連線也一樣。</span><span class="sxs-lookup"><span data-stu-id="297b9-127">Although you can download the definitions when you run <strong>Defender</strong>, we recommend that you download the latest definitions at the time you create the DaRT recovery image so that you can still run the tool with the latest definitions even if the problem computer does not have network connectivity.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="297b9-128">[選用]： Windows 符號檔案以用於 <strong> 故障分析程式</span><span class="sxs-lookup"><span data-stu-id="297b9-128">Optional: Windows symbols files for use with <strong>Crash Analyzer</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="297b9-129">通常，調試資訊會儲存在與程式不同的符號檔案中。</span><span class="sxs-lookup"><span data-stu-id="297b9-129">Typically, debugging information is stored in a symbol file that is separate from the program.</span></span> <span data-ttu-id="297b9-130">當您調試的應用程式已停止回應（例如，如果它已停止運作），就必須具備符號資訊的存取權。</span><span class="sxs-lookup"><span data-stu-id="297b9-130">You must have access to the symbol information when you debug an application that has stopped responding, for example, if it stopped working.</span></span> <span data-ttu-id="297b9-131">如需詳細資訊，請參閱 <a href="diagnosing-system-failures-with-crash-analyzer--dart-8.md" data-raw-source="[Diagnosing System Failures with Crash Analyzer](diagnosing-system-failures-with-crash-analyzer--dart-8.md)"> 使用故障分析程式診斷系統失敗 </a> 。</span><span class="sxs-lookup"><span data-stu-id="297b9-131">For more information, see <a href="diagnosing-system-failures-with-crash-analyzer--dart-8.md" data-raw-source="[Diagnosing System Failures with Crash Analyzer](diagnosing-system-failures-with-crash-analyzer--dart-8.md)">Diagnosing System Failures with Crash Analyzer</a>.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="297b9-132">相關主題</span><span class="sxs-lookup"><span data-stu-id="297b9-132">Related topics</span></span>


[<span data-ttu-id="297b9-133">規劃部署 DaRT 8.0</span><span class="sxs-lookup"><span data-stu-id="297b9-133">Planning to Deploy DaRT 8.0</span></span>](planning-to-deploy-dart-80-dart-8.md)

 

 





