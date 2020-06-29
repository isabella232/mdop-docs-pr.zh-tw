---
title: 如何在使用者電腦上執行損毀分析器
description: 如何在使用者電腦上執行損毀分析器
author: dansimp
ms.assetid: 10334800-ff8e-43ac-a9c2-d28807473ec2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 4abf1ba2ae1a0cb1dfb129c1f5a26e11f5045290
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809494"
---
# <span data-ttu-id="b4523-103">如何在使用者電腦上執行損毀分析器</span><span class="sxs-lookup"><span data-stu-id="b4523-103">How to Run the Crash Analyzer on an End-user Computer</span></span>


<span data-ttu-id="b4523-104">若要從遇到問題的最終使用者電腦上的 [**診斷及修復工具集**]**視窗執行當**機，您必須具備 Windows 版 Microsoft 調試工具及已安裝的符號檔案。</span><span class="sxs-lookup"><span data-stu-id="b4523-104">To run **Crash Analyzer** from the **Diagnostics and Recovery Toolset** window on an end-user computer that is experiencing problems, you must have the Microsoft Debugging Tools for Windows and the symbol files installed.</span></span> <span data-ttu-id="b4523-105">若要下載 Windows 調試工具，請參閱[windows 版調試工具](https://go.microsoft.com/fwlink/?LinkId=266248)。</span><span class="sxs-lookup"><span data-stu-id="b4523-105">To download the Windows Debugging Tools, see [Debugging Tools for Windows](https://go.microsoft.com/fwlink/?LinkId=266248).</span></span>

**<span data-ttu-id="b4523-106">在最終使用者電腦上執行 [崩潰分析程式]</span><span class="sxs-lookup"><span data-stu-id="b4523-106">To run the Crash Analyzer on an end-user computer</span></span>**

1.  <span data-ttu-id="b4523-107">在最終使用者電腦上的 [**診斷與修復工具**] 視窗中，按一下 [**崩潰分析**程式]。</span><span class="sxs-lookup"><span data-stu-id="b4523-107">On the **Diagnostics and Recovery Toolset** window on an end-user computer, click **Crash Analyzer**.</span></span>

2.  <span data-ttu-id="b4523-108">針對 Windows 版 Microsoft 調試工具提供所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="b4523-108">Provide the required information for the Microsoft Debugging Tools for Windows.</span></span>

3.  <span data-ttu-id="b4523-109">提供符號檔案所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="b4523-109">Provide the required information for the symbol files.</span></span> <span data-ttu-id="b4523-110">如需符號檔案的詳細資訊，請參閱[如何確保當機分析器可以存取符號](how-to-ensure-that-crash-analyzer-can-access-symbol-files-dart-10.md)檔案。</span><span class="sxs-lookup"><span data-stu-id="b4523-110">For more information about symbol files, see [How to Ensure that Crash Analyzer Can Access Symbol Files](how-to-ensure-that-crash-analyzer-can-access-symbol-files-dart-10.md).</span></span>

4.  <span data-ttu-id="b4523-111">提供記憶體傾印檔案所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="b4523-111">Provide the required information for a memory dump file.</span></span> <span data-ttu-id="b4523-112">若要判斷記憶體傾印檔案的位置：</span><span class="sxs-lookup"><span data-stu-id="b4523-112">To determine the location of the memory dump file:</span></span>

    1.  <span data-ttu-id="b4523-113">開啟 [**系統屬性**] 視窗。</span><span class="sxs-lookup"><span data-stu-id="b4523-113">Open the **System Properties** window.</span></span>

    2.  <span data-ttu-id="b4523-114">按一下 [**開始**]，輸入**sysdm.cpl**，然後按**enter**。</span><span class="sxs-lookup"><span data-stu-id="b4523-114">Click **Start**, type **sysdm.cpl**, and then press **Enter**.</span></span>

    3.  <span data-ttu-id="b4523-115">按一下 **\[進階\]** 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="b4523-115">Click the **Advanced** tab.</span></span>

    4.  <span data-ttu-id="b4523-116">在 [**啟動及修復**] 區域中，按一下 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="b4523-116">In the **Startup and Recovery** area, click **Settings**.</span></span>

        <span data-ttu-id="b4523-117">如果您無法存取 [**系統屬性**] 視窗，您可以使用 Microsoft Diagnostics 和恢復工具組（DaRT）10中的 [**搜尋**] 工具，在最終使用者電腦上搜尋轉儲檔案。</span><span class="sxs-lookup"><span data-stu-id="b4523-117">If you do not have access to the **System Properties** window, you can search for dump files on the end-user computer by using the **Search** tool in Microsoft Diagnostics and Recovery Toolset (DaRT) 10.</span></span>

    <span data-ttu-id="b4523-118">[**崩潰分析**程式] 會掃描記憶體傾印檔案，並報告問題的可能原因。</span><span class="sxs-lookup"><span data-stu-id="b4523-118">The **Crash Analyzer** scans the memory dump file and reports a probable cause of the problem.</span></span> <span data-ttu-id="b4523-119">您可以查看關於失敗的詳細資訊，例如特定記憶體傾印訊息和描述、在失敗時載入的驅動程式，以及分析的完整輸出。</span><span class="sxs-lookup"><span data-stu-id="b4523-119">You can view more information about the failure, such as the specific memory dump message and description, the drivers loaded at the time of the failure, and the full output of the analysis.</span></span>

5.  <span data-ttu-id="b4523-120">找出適當的戰略來解決問題。</span><span class="sxs-lookup"><span data-stu-id="b4523-120">Identify the appropriate strategy to resolve the problem.</span></span> <span data-ttu-id="b4523-121">策略可能需要停用或更新導致失敗的裝置驅動程式，方法是使用 DaRT 10 中的 [**電腦管理**] 工具的 [**服務和驅動程式**] 節點。</span><span class="sxs-lookup"><span data-stu-id="b4523-121">The strategy may require disabling or updating the device driver that caused the failure by using the **Services and Drivers** node of the **Computer Management** tool in DaRT 10.</span></span>

## <span data-ttu-id="b4523-122">相關主題</span><span class="sxs-lookup"><span data-stu-id="b4523-122">Related topics</span></span>


[<span data-ttu-id="b4523-123">使用損毀分析器來診斷系統失敗</span><span class="sxs-lookup"><span data-stu-id="b4523-123">Diagnosing System Failures with Crash Analyzer</span></span>](diagnosing-system-failures-with-crash-analyzer-dart-10.md)

[<span data-ttu-id="b4523-124">適用於 DaRT 10 的操作</span><span class="sxs-lookup"><span data-stu-id="b4523-124">Operations for DaRT 10</span></span>](operations-for-dart-10.md)

 

 





