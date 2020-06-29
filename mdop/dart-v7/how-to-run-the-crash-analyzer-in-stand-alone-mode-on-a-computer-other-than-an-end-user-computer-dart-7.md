---
title: 如何在使用者電腦以外的電腦上，以獨立模式執行損毀分析器
description: 如何在使用者電腦以外的電腦上，以獨立模式執行損毀分析器
author: dansimp
ms.assetid: 881d573f-2f18-4c5f-838e-2f5320179f94
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6f398c56b7c631145388541b71229d69c16bf6f3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809566"
---
# <span data-ttu-id="82cd8-103">如何在使用者電腦以外的電腦上，以獨立模式執行損毀分析器</span><span class="sxs-lookup"><span data-stu-id="82cd8-103">How to Run the Crash Analyzer in Stand-alone Mode on a Computer Other than an End-user Computer</span></span>


<span data-ttu-id="82cd8-104">如果您無法存取 Windows 版 Microsoft 調試工具或終端使用者電腦上的符號檔案，您可以從問題電腦複製轉儲檔案，並在裝有獨立版本的崩潰分析程式的電腦（例如支援者管理員的電腦）上進行分析。</span><span class="sxs-lookup"><span data-stu-id="82cd8-104">If you cannot access the Microsoft Debugging Tools for Windows or the symbol files on the end-user computer, you can copy the dump file from the problem computer and analyze it on a computer that has the stand-alone version of Crash Analyzer installed, such as a helpdesk administrator’s computer.</span></span>

**<span data-ttu-id="82cd8-105">在獨立模式下執行故障分析程式</span><span class="sxs-lookup"><span data-stu-id="82cd8-105">To run the Crash Analyzer in stand-alone mode</span></span>**

1.  <span data-ttu-id="82cd8-106">在已安裝 DaRT7 的電腦上，按一下 [**開始**使用  /  **All Programs**  /  **Microsoft DaRT 7**] 中的 [所有程式]。</span><span class="sxs-lookup"><span data-stu-id="82cd8-106">On a computer with DaRT7 installed, click **Start** / **All Programs** / **Microsoft DaRT 7**.</span></span>

2.  <span data-ttu-id="82cd8-107">提供下列所需的資訊：</span><span class="sxs-lookup"><span data-stu-id="82cd8-107">Provide the required information for the following:</span></span>

    -   <span data-ttu-id="82cd8-108">Windows 版 Microsoft 調試工具</span><span class="sxs-lookup"><span data-stu-id="82cd8-108">Microsoft Debugging Tools for Windows</span></span>

    -   <span data-ttu-id="82cd8-109">符號檔案</span><span class="sxs-lookup"><span data-stu-id="82cd8-109">Symbol files</span></span>

        <span data-ttu-id="82cd8-110">如需有關符號檔案的詳細資訊，請參閱[如何確保系統崩潰分析程式可以存取符號](how-to-ensure-that-crash-analyzer-can-access-symbol-files-dart-7.md)檔案。</span><span class="sxs-lookup"><span data-stu-id="82cd8-110">For more information about symbol files, see, [How to Ensure that Crash Analyzer Can Access Symbol Files](how-to-ensure-that-crash-analyzer-can-access-symbol-files-dart-7.md).</span></span>

    -   <span data-ttu-id="82cd8-111">損毀傾印檔案</span><span class="sxs-lookup"><span data-stu-id="82cd8-111">A crash dump file</span></span>

        <span data-ttu-id="82cd8-112">**記事** 使用 DaRT7 中的 [搜尋] 工具，找出複製的損毀盤案檔案。</span><span class="sxs-lookup"><span data-stu-id="82cd8-112">**Note** Use the Search tool in DaRT7 to locate the copied crash dump file.</span></span>

         

3.  <span data-ttu-id="82cd8-113">[**崩潰分析**程式] 會掃描損毀盤案檔案，並報告可能造成當機的問題。</span><span class="sxs-lookup"><span data-stu-id="82cd8-113">The **Crash Analyzer** scans the crash dump file and reports a probable cause of the crash.</span></span> <span data-ttu-id="82cd8-114">您可以查看關於該損毀的詳細資訊，例如特定的故障訊息和描述、當機時載入的驅動程式，以及分析的完整輸出。</span><span class="sxs-lookup"><span data-stu-id="82cd8-114">You can view more information about the crash, such as the specific crash message and description, the drivers loaded at the time of the crash, and the full output of the analysis.</span></span>

4.  <span data-ttu-id="82cd8-115">根據適當的策略來判斷問題的解決方法。</span><span class="sxs-lookup"><span data-stu-id="82cd8-115">Decide upon an appropriate strategy to resolve the problem.</span></span> <span data-ttu-id="82cd8-116">這可能需要停用或更新使用 DaRT**電腦管理**工具之 [**服務與驅動程式**] 節點的裝置驅動程式。</span><span class="sxs-lookup"><span data-stu-id="82cd8-116">This may require disabling or updating the device driver that caused the crash by using the **Services and Drivers** node of the **Computer Management** tool in DaRT.</span></span>

## <span data-ttu-id="82cd8-117">相關主題</span><span class="sxs-lookup"><span data-stu-id="82cd8-117">Related topics</span></span>


[<span data-ttu-id="82cd8-118">使用損毀分析器來診斷系統失敗</span><span class="sxs-lookup"><span data-stu-id="82cd8-118">Diagnosing System Failures with Crash Analyzer</span></span>](diagnosing-system-failures-with-crash-analyzer--dart-7.md)

 

 





