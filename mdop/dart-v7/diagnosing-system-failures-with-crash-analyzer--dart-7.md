---
title: 使用損毀分析器來診斷系統失敗
description: 使用損毀分析器來診斷系統失敗
author: dansimp
ms.assetid: 170d40ef-4edb-4a32-a349-c285c0ea5e56
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3c5f8b7e189de024d7ceb84f8cfc151dc82d56ed
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809974"
---
# <span data-ttu-id="363d1-103">使用損毀分析器來診斷系統失敗</span><span class="sxs-lookup"><span data-stu-id="363d1-103">Diagnosing System Failures with Crash Analyzer</span></span>


<span data-ttu-id="363d1-104">Microsoft Diagnostics 與修復工具組（DaRT）7中的 [崩潰分析程式] 可讓您在 Windows 電腦上調試損毀轉儲檔案，然後診斷任何相關的電腦錯誤。</span><span class="sxs-lookup"><span data-stu-id="363d1-104">The Crash Analyzer in Microsoft Diagnostics and Recovery Toolset (DaRT)7 lets you debug a crash dump file on a Windows-based computer and then diagnose any related computer errors.</span></span> <span data-ttu-id="363d1-105">[崩潰分析程式] 使用 Windows 版 Microsoft 調試工具，來檢查導致電腦失敗之驅動程式的損毀盤案檔案。</span><span class="sxs-lookup"><span data-stu-id="363d1-105">The Crash Analyzer uses the Microsoft Debugging Tools for Windows to examine a crash dump file for the driver that caused the computer to fail.</span></span>

## <span data-ttu-id="363d1-106">在最終使用者電腦上執行 [崩潰分析程式]</span><span class="sxs-lookup"><span data-stu-id="363d1-106">Run the Crash Analyzer on an End-user Computer</span></span>


<span data-ttu-id="363d1-107">通常，您會在有問題的使用者電腦上，從 [診斷與修復工具] 視窗執行 [崩潰分析程式]。</span><span class="sxs-lookup"><span data-stu-id="363d1-107">Typically, you run Crash Analyzer from the Diagnostics and Recovery Toolset window on an end-user computer that has problems.</span></span> <span data-ttu-id="363d1-108">當故障分析程式在問題電腦上尋找 Windows 的調試工具。</span><span class="sxs-lookup"><span data-stu-id="363d1-108">The Crash Analyzer tries to locate the Debugging Tools for Windows on the problem computer.</span></span> <span data-ttu-id="363d1-109">如果 [目錄路徑] 對話方塊是空的，您必須輸入位置或流覽至 Windows 調試工具的位置（您可以從 Microsoft 下載檔案）。</span><span class="sxs-lookup"><span data-stu-id="363d1-109">If the directory path dialog box is empty, you must enter the location or browse to the location of the Debugging Tools for Windows (you can download the files from Microsoft).</span></span> <span data-ttu-id="363d1-110">您也必須提供符號檔案所在位置的路徑。</span><span class="sxs-lookup"><span data-stu-id="363d1-110">You must also provide a path to where the symbol files are located.</span></span>

<span data-ttu-id="363d1-111">如果您在建立 DaRT 復原影像時包含 Windows 版 Microsoft 調試工具和符號檔案，當您在有問題的電腦上執行 [當機] 時，就應該能使用這些檔案。</span><span class="sxs-lookup"><span data-stu-id="363d1-111">If you included the Microsoft Debugging Tools for Windows and the symbol files when you created the DaRT recovery image, they should be available when you run the Crash Analyzer on the problem computer.</span></span>

[<span data-ttu-id="363d1-112">如何在使用者電腦上執行損毀分析器</span><span class="sxs-lookup"><span data-stu-id="363d1-112">How to Run the Crash Analyzer on an End-user Computer</span></span>](how-to-run-the-crash-analyzer-on-an-end-user-computer-dart-7.md)

## <span data-ttu-id="363d1-113">在不是使用者電腦的電腦上，以獨立模式執行故障分析程式</span><span class="sxs-lookup"><span data-stu-id="363d1-113">Run the Crash Analyzer in stand-alone mode on a computer other than an end-user computer</span></span>


<span data-ttu-id="363d1-114">當故障分析程式在問題電腦上尋找 Windows 的調試工具。</span><span class="sxs-lookup"><span data-stu-id="363d1-114">The Crash Analyzer tries to locate the Debugging Tools for Windows on the problem computer.</span></span> <span data-ttu-id="363d1-115">如果 [目錄路徑] 對話方塊是空的，您必須輸入位置或流覽至 Windows 調試工具的位置（您可以從 Microsoft 下載檔案）。</span><span class="sxs-lookup"><span data-stu-id="363d1-115">If the directory path dialog box is empty, you must enter the location or browse to the location of the Debugging Tools for Windows (you can download the files from Microsoft).</span></span> <span data-ttu-id="363d1-116">您也必須提供符號檔案所在位置的路徑。</span><span class="sxs-lookup"><span data-stu-id="363d1-116">You must also provide a path to where the symbol files are located.</span></span>

<span data-ttu-id="363d1-117">如果您在建立 DaRT 復原影像時未包含 Windows 和符號檔案的 Microsoft 調試工具，或是磁片大小或網路連線問題無法取得它們，您可以從問題電腦複製轉儲檔案，並在已安裝獨立版本的故障分析程式的電腦上進行分析，例如 [支援者管理員的電腦]。</span><span class="sxs-lookup"><span data-stu-id="363d1-117">If you did not include the Microsoft Debugging Tools for Windows and the symbol files when you created the DaRT recovery image, or if disk size or network connectivity problems are preventing you from obtaining them, then you can copy the dump file from the problem computer and analyze it on a computer that has the stand-alone version of Crash Analyzer installed, such as a helpdesk administrator’s computer.</span></span>

[<span data-ttu-id="363d1-118">如何在使用者電腦以外的電腦上，以獨立模式執行損毀分析器</span><span class="sxs-lookup"><span data-stu-id="363d1-118">How to Run the Crash Analyzer in Stand-alone Mode on a Computer Other than an End-user Computer</span></span>](how-to-run-the-crash-analyzer-in-stand-alone-mode-on-a-computer-other-than-an-end-user-computer-dart-7.md)

## <span data-ttu-id="363d1-119">確定 [損毀分析器] 可以存取符號檔案</span><span class="sxs-lookup"><span data-stu-id="363d1-119">Ensure that Crash Analyzer can access symbol files</span></span>


<span data-ttu-id="363d1-120">通常，調試資訊會儲存在符號檔案中，與可執行檔不同。</span><span class="sxs-lookup"><span data-stu-id="363d1-120">Typically, debugging information is stored in a symbol file that is separate from the executable.</span></span> <span data-ttu-id="363d1-121">調試已停止回應的應用程式時，您必須具備符號資訊的存取權（例如，如果它已損壞）。</span><span class="sxs-lookup"><span data-stu-id="363d1-121">You must have access to the symbol information when you debug an application that has stopped responding, for example if it crashed.</span></span>

<span data-ttu-id="363d1-122">當您執行 [損毀分析程式] 時，會自動下載符號檔案。</span><span class="sxs-lookup"><span data-stu-id="363d1-122">Symbol files are automatically downloaded when you run Crash Analyzer.</span></span> <span data-ttu-id="363d1-123">如果電腦沒有網際網路連線，或網路需要電腦存取 HTTP proxy 伺服器，則無法下載符號檔案。</span><span class="sxs-lookup"><span data-stu-id="363d1-123">If the computer does not have an Internet connection or the network requires the computer to access an HTTP proxy server, the symbol files cannot be downloaded.</span></span>

[<span data-ttu-id="363d1-124">如何確保損毀分析器可以存取符號檔案</span><span class="sxs-lookup"><span data-stu-id="363d1-124">How to Ensure that Crash Analyzer Can Access Symbol Files</span></span>](how-to-ensure-that-crash-analyzer-can-access-symbol-files-dart-7.md)

## <span data-ttu-id="363d1-125">使用故障分析程式診斷系統失敗的其他資源</span><span class="sxs-lookup"><span data-stu-id="363d1-125">Other resources for diagnosing system failures with Crash Analyzer</span></span>


[<span data-ttu-id="363d1-126">適用於 DaRT 7.0 的操作</span><span class="sxs-lookup"><span data-stu-id="363d1-126">Operations for DaRT 7.0</span></span>](operations-for-dart-70-new-ia.md)

 

 





