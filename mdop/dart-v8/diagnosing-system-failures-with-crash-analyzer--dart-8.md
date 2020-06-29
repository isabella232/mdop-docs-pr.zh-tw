---
title: 使用損毀分析器來診斷系統失敗
description: 使用損毀分析器來診斷系統失敗
author: dansimp
ms.assetid: ce3d3186-54fb-45b2-b5ce-9bb7841db28f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: abb9d1ec99236199e0866a3b23219dd412bc9da6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810617"
---
# <span data-ttu-id="c347c-103">使用損毀分析器來診斷系統失敗</span><span class="sxs-lookup"><span data-stu-id="c347c-103">Diagnosing System Failures with Crash Analyzer</span></span>


<span data-ttu-id="c347c-104">Microsoft Diagnostics 與修復工具組（DaRT）8.0 中的 [**崩潰分析**程式] 可讓您在 Windows 電腦上調試記憶體傾印檔案，然後診斷任何相關的電腦錯誤。</span><span class="sxs-lookup"><span data-stu-id="c347c-104">The **Crash Analyzer** in Microsoft Diagnostics and Recovery Toolset (DaRT) 8.0 lets you debug a memory dump file on a Windows-based computer and then diagnose any related computer errors.</span></span> <span data-ttu-id="c347c-105">[**崩潰分析**程式] 使用 Windows 版 Microsoft 調試工具，來檢查導致電腦失敗之驅動程式的記憶體傾印檔案。</span><span class="sxs-lookup"><span data-stu-id="c347c-105">The **Crash Analyzer** uses the Microsoft Debugging Tools for Windows to examine a memory dump file for the driver that caused the computer to fail.</span></span> <span data-ttu-id="c347c-106">您可以在使用者電腦以外的電腦（而非使用者電腦）上，在最終使用者電腦或獨立模式中執行當機。</span><span class="sxs-lookup"><span data-stu-id="c347c-106">You can run the Crash Analyzer on an end-user computer or in stand-alone mode on a computer other than an end-user computer.</span></span>

## <span data-ttu-id="c347c-107">在最終使用者電腦上執行 [崩潰分析程式]</span><span class="sxs-lookup"><span data-stu-id="c347c-107">Run the Crash Analyzer on an end-user-computer</span></span>


<span data-ttu-id="c347c-108">通常，您會在遇到問題的最終使用者電腦上，從 [**診斷和修復工具**] 視窗中執行 [當機] 的 [**崩潰分析**程式]。</span><span class="sxs-lookup"><span data-stu-id="c347c-108">Typically, you run **Crash Analyzer** from the **Diagnostics and Recovery Toolset** window on an end-user computer that is experiencing the problem.</span></span> <span data-ttu-id="c347c-109">當**故障分析**程式在問題電腦上尋找 Windows 的調試工具。</span><span class="sxs-lookup"><span data-stu-id="c347c-109">The **Crash Analyzer** tries to locate the Debugging Tools for Windows on the problem computer.</span></span> <span data-ttu-id="c347c-110">如果 [目錄路徑] 對話方塊是空的，您必須輸入位置，或流覽至 Windows 調試工具的位置（您可以從 Microsoft 下載檔案）。</span><span class="sxs-lookup"><span data-stu-id="c347c-110">If the directory path dialog box is empty, you must enter the location, or browse to the location of the Debugging Tools for Windows (you can download the files from Microsoft).</span></span> <span data-ttu-id="c347c-111">您也必須提供符號檔案所在位置的路徑。</span><span class="sxs-lookup"><span data-stu-id="c347c-111">You must also provide a path to where the symbol files are located.</span></span>

<span data-ttu-id="c347c-112">如果您在建立 DaRT 8.0 復原影像時包含 Windows 版 Microsoft 調試工具和符號檔案，當您在有問題的**電腦上執行**[當機] 時，就應該能使用這些工具和符號檔案。</span><span class="sxs-lookup"><span data-stu-id="c347c-112">If you included the Microsoft Debugging Tools for Windows and the symbol files when you created the DaRT 8.0 recovery image, the Tools and symbol files should be available when you run the **Crash Analyzer** on the problem computer.</span></span> <span data-ttu-id="c347c-113">如果您未將其包含在 DaRT 復原影像中，或是磁片大小或網路連線問題無法取得它們，您也可以在非使用者電腦以外的電腦上以獨立模式執行該防故障分析程式，如下一節所述。</span><span class="sxs-lookup"><span data-stu-id="c347c-113">If you did not include them in the DaRT recovery image, or if disk size or network connectivity problems are preventing you from obtaining them, you can alternatively run the Crash Analyzer in stand-alone mode on a computer other than the end user’s computer, as described in the following section.</span></span>

[<span data-ttu-id="c347c-114">如何在使用者電腦上執行損毀分析器</span><span class="sxs-lookup"><span data-stu-id="c347c-114">How to Run the Crash Analyzer on an End-user Computer</span></span>](how-to-run-the-crash-analyzer-on-an-end-user-computer-dart-8.md)

## <a href="" id="run-the-crash-analyzer-in-stand-alone-mode-on-a-computer-other-than-an-end-user-s-computer"></a><span data-ttu-id="c347c-115">在使用者電腦以外的電腦上，以獨立模式執行故障分析程式</span><span class="sxs-lookup"><span data-stu-id="c347c-115">Run the Crash Analyzer in stand-alone mode on a computer other than an end user’s computer</span></span>


<span data-ttu-id="c347c-116">雖然您通常會**在遇到**問題的最終使用者電腦上執行當機，但是您也可以在獨立模式（而非使用者電腦）上執行故障分析程式。</span><span class="sxs-lookup"><span data-stu-id="c347c-116">Although you typically run **Crash Analyzer** on the end-user computer that is experiencing the problem, you can also run the Crash Analyzer in stand-alone mode, on a computer other than an end-user computer.</span></span> <span data-ttu-id="c347c-117">如果您沒有在 DaRT 復原影像中包含 Windows 調試工具，或是磁片大小或網路連線問題阻礙您取得調試工具，您就可以選擇這個選項。</span><span class="sxs-lookup"><span data-stu-id="c347c-117">You might choose this option if you did not include the Windows Debugging Tools in the DaRT recovery image, or if disk size or network connectivity problems are preventing you from obtaining the Debugging Tools.</span></span> <span data-ttu-id="c347c-118">在這種情況下，您可以從問題電腦複製轉儲檔案，並在裝有獨立版本的**故障分析**程式的電腦上進行分析，例如在服務台代理的電腦上。</span><span class="sxs-lookup"><span data-stu-id="c347c-118">In this case, you can copy the dump file from the problem computer and analyze it on a computer that has the stand-alone version of **Crash Analyzer** installed, such as on a help desk agent’s computer.</span></span>

[<span data-ttu-id="c347c-119">如何在使用者電腦以外的電腦上，以獨立模式執行損毀分析器</span><span class="sxs-lookup"><span data-stu-id="c347c-119">How to Run the Crash Analyzer in Stand-alone Mode on a Computer Other than an End-user Computer</span></span>](how-to-run-the-crash-analyzer-in-stand-alone-mode-on-a-computer-other-than-an-end-user-computer-dart-8.md)

## <span data-ttu-id="c347c-120">如何確保 [損毀分析器] 可以存取符號檔案</span><span class="sxs-lookup"><span data-stu-id="c347c-120">How to ensure that Crash Analyzer can access symbol files</span></span>


<span data-ttu-id="c347c-121">若要調試已停止回應的應用程式，您需要存取符號檔案，該檔與程式不同。</span><span class="sxs-lookup"><span data-stu-id="c347c-121">To debug applications that have stopped responding, you need access to the symbol file, which is separate from the program.</span></span> <span data-ttu-id="c347c-122">雖然當您執行當機時，會自動下載符號檔案，但有時問題電腦無法存取網際網路。</span><span class="sxs-lookup"><span data-stu-id="c347c-122">Although symbol files are automatically downloaded when you run Crash Analyzer, there might be times when the problem computer does not have access to the Internet.</span></span> <span data-ttu-id="c347c-123">有幾種方法可以確保您可以存取符號檔案。</span><span class="sxs-lookup"><span data-stu-id="c347c-123">There are several ways to ensure that you have guaranteed access to symbol files.</span></span>

[<span data-ttu-id="c347c-124">如何確保損毀分析器可以存取符號檔案</span><span class="sxs-lookup"><span data-stu-id="c347c-124">How to Ensure that Crash Analyzer Can Access Symbol Files</span></span>](how-to-ensure-that-crash-analyzer-can-access-symbol-files.md)

## <span data-ttu-id="c347c-125">使用故障分析程式診斷系統失敗的其他資源</span><span class="sxs-lookup"><span data-stu-id="c347c-125">Other resources for diagnosing system failures with Crash Analyzer</span></span>


[<span data-ttu-id="c347c-126">適用於 DaRT 8.0 的操作</span><span class="sxs-lookup"><span data-stu-id="c347c-126">Operations for DaRT 8.0</span></span>](operations-for-dart-80-dart-8.md)

 

 





