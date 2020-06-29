---
title: 如何在使用者電腦上執行損毀分析器
description: 如何在使用者電腦上執行損毀分析器
author: dansimp
ms.assetid: 40af4ead-6588-4a81-8eaa-3dc00c397e1d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 943e3956609ae7e24deaca4313036445802a8f7f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810196"
---
# <span data-ttu-id="612b1-103">如何在使用者電腦上執行損毀分析器</span><span class="sxs-lookup"><span data-stu-id="612b1-103">How to Run the Crash Analyzer on an End-user Computer</span></span>


<span data-ttu-id="612b1-104">通常，您會在有問題的最終使用者電腦上，從 [診斷與修復工具] 視窗中執行 Microsoft Diagnostics 和復原工具集（DaRT）7故障分析程式。</span><span class="sxs-lookup"><span data-stu-id="612b1-104">Typically, you run Microsoft Diagnostics and Recovery Toolset (DaRT)7 Crash Analyzer from the Diagnostics and Recovery Toolset window on an end-user computer that has problems.</span></span> <span data-ttu-id="612b1-105">當故障分析程式在問題電腦上尋找 Windows 的調試工具。</span><span class="sxs-lookup"><span data-stu-id="612b1-105">The Crash Analyzer tries to locate the Debugging Tools for Windows on the problem computer.</span></span> <span data-ttu-id="612b1-106">如果 [目錄路徑] 對話方塊是空的，您必須輸入位置或流覽至 Windows 調試工具的位置（您可以從 Microsoft 下載檔案）。</span><span class="sxs-lookup"><span data-stu-id="612b1-106">If the directory path dialog box is empty, you must enter the location or browse to the location of the Debugging Tools for Windows (you can download the files from Microsoft).</span></span> <span data-ttu-id="612b1-107">您也必須提供符號檔案所在位置的路徑。</span><span class="sxs-lookup"><span data-stu-id="612b1-107">You must also provide a path to where the symbol files are located.</span></span>

**<span data-ttu-id="612b1-108">在最終使用者電腦上開啟並執行 [損毀分析器]</span><span class="sxs-lookup"><span data-stu-id="612b1-108">To open and run the Crash Analyzer on an end-user computer</span></span>**

1.  <span data-ttu-id="612b1-109">在最終使用者電腦上的 [**診斷與修復工具**] 視窗中，按一下 [**崩潰分析**程式]。</span><span class="sxs-lookup"><span data-stu-id="612b1-109">On the **Diagnostics and Recovery Toolset** window on an end-user computer, click **Crash Analyzer**.</span></span>

2.  <span data-ttu-id="612b1-110">提供下列所需的資訊：</span><span class="sxs-lookup"><span data-stu-id="612b1-110">Provide the required information for the following:</span></span>

    -   <span data-ttu-id="612b1-111">Windows 版 Microsoft 調試工具</span><span class="sxs-lookup"><span data-stu-id="612b1-111">Microsoft Debugging Tools for Windows</span></span>

    -   <span data-ttu-id="612b1-112">符號檔案</span><span class="sxs-lookup"><span data-stu-id="612b1-112">Symbol files</span></span>

        <span data-ttu-id="612b1-113">如需有關符號檔案的詳細資訊，請參閱[如何確保系統崩潰分析程式可以存取符號](how-to-ensure-that-crash-analyzer-can-access-symbol-files-dart-7.md)檔案。</span><span class="sxs-lookup"><span data-stu-id="612b1-113">For more information about symbol files, see, [How to Ensure that Crash Analyzer Can Access Symbol Files](how-to-ensure-that-crash-analyzer-can-access-symbol-files-dart-7.md).</span></span>

    -   <span data-ttu-id="612b1-114">損毀傾印檔案</span><span class="sxs-lookup"><span data-stu-id="612b1-114">A crash dump file</span></span>

        <span data-ttu-id="612b1-115">請依照下列步驟來判斷損毀傾印檔案的位置：</span><span class="sxs-lookup"><span data-stu-id="612b1-115">Follow these steps to determine the location of the crash dump file:</span></span>

        1.  <span data-ttu-id="612b1-116">開啟 [**系統屬性**] 視窗。</span><span class="sxs-lookup"><span data-stu-id="612b1-116">Open the **System Properties** window.</span></span>

            <span data-ttu-id="612b1-117">按一下 [**開始**]，輸入 sysdm.cpl，然後按 enter。</span><span class="sxs-lookup"><span data-stu-id="612b1-117">Click **Start**, type sysdm.cpl, and then press Enter.</span></span>

        2.  <span data-ttu-id="612b1-118">按一下 **\[進階\]** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="612b1-118">Click the **Advanced** tab.</span></span>

        3.  <span data-ttu-id="612b1-119">在 [**啟動及修復**] 區域中，按一下 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="612b1-119">In the **Startup and Recovery** area, click **Settings**.</span></span>

        <span data-ttu-id="612b1-120">**記事** 如果您無法存取 [**系統屬性**] 視窗，您可以使用 DaRT 中的 [**搜尋**] 工具，在最終使用者電腦上搜尋轉儲檔案。</span><span class="sxs-lookup"><span data-stu-id="612b1-120">**Note** If you do not have access to the **System Properties** window, you can search for dump files on the end-user computer by using the **Search** tool in DaRT.</span></span>

         

3.  <span data-ttu-id="612b1-121">[**崩潰分析**程式] 會掃描損毀盤案檔案，並報告可能造成當機的問題。</span><span class="sxs-lookup"><span data-stu-id="612b1-121">The **Crash Analyzer** scans the crash dump file and reports a probable cause of the crash.</span></span> <span data-ttu-id="612b1-122">您可以查看關於該損毀的詳細資訊，例如特定的故障訊息和描述、當機時載入的驅動程式，以及分析的完整輸出。</span><span class="sxs-lookup"><span data-stu-id="612b1-122">You can view more information about the crash, such as the specific crash message and description, the drivers loaded at the time of the crash, and the full output of the analysis.</span></span>

4.  <span data-ttu-id="612b1-123">根據適當的策略來判斷問題的解決方法。</span><span class="sxs-lookup"><span data-stu-id="612b1-123">Decide upon an appropriate strategy to resolve the problem.</span></span> <span data-ttu-id="612b1-124">這可能需要停用或更新使用 DaRT**電腦管理**工具之 [**服務與驅動程式**] 節點的裝置驅動程式。</span><span class="sxs-lookup"><span data-stu-id="612b1-124">This may require disabling or updating the device driver that caused the crash by using the **Services and Drivers** node of the **Computer Management** tool in DaRT.</span></span>

## <span data-ttu-id="612b1-125">相關主題</span><span class="sxs-lookup"><span data-stu-id="612b1-125">Related topics</span></span>


[<span data-ttu-id="612b1-126">使用損毀分析器來診斷系統失敗</span><span class="sxs-lookup"><span data-stu-id="612b1-126">Diagnosing System Failures with Crash Analyzer</span></span>](diagnosing-system-failures-with-crash-analyzer--dart-7.md)

 

 





