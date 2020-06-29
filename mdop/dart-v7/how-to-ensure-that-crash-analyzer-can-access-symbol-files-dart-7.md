---
title: 如何確保損毀分析器可以存取符號檔案
description: 如何確保損毀分析器可以存取符號檔案
author: dansimp
ms.assetid: 150a2f88-68a5-40eb-8471-e5008488ab6e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: db56bb21ad885d1e3aa73bcbd922a7e8bde77080
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809573"
---
# <span data-ttu-id="e1af5-103">如何確保損毀分析器可以存取符號檔案</span><span class="sxs-lookup"><span data-stu-id="e1af5-103">How to Ensure that Crash Analyzer Can Access Symbol Files</span></span>


<span data-ttu-id="e1af5-104">通常，調試資訊會儲存在符號檔案中，與可執行檔不同。</span><span class="sxs-lookup"><span data-stu-id="e1af5-104">Typically, debugging information is stored in a symbol file that is separate from the executable.</span></span> <span data-ttu-id="e1af5-105">調試已停止回應的應用程式時，您必須具備符號資訊的存取權（例如，如果它已損壞）。</span><span class="sxs-lookup"><span data-stu-id="e1af5-105">You must have access to the symbol information when you debug an application that has stopped responding, for example if it crashed.</span></span>

<span data-ttu-id="e1af5-106">當您執行 Microsoft 診斷和修復工具集（DaRT）7故障分析程式時，會自動下載符號檔案。</span><span class="sxs-lookup"><span data-stu-id="e1af5-106">Symbol files are automatically downloaded when you run the Microsoft Diagnostics and Recovery Toolset (DaRT)7 Crash Analyzer.</span></span> <span data-ttu-id="e1af5-107">如果電腦沒有網際網路連線，或網路需要電腦存取 HTTP proxy 伺服器，則無法下載符號檔案。</span><span class="sxs-lookup"><span data-stu-id="e1af5-107">If the computer does not have an Internet connection or the network requires the computer to access an HTTP proxy server, the symbol files cannot be downloaded.</span></span>

## <span data-ttu-id="e1af5-108">確定存取符號檔案</span><span class="sxs-lookup"><span data-stu-id="e1af5-108">Ensure access to symbol files</span></span>


<span data-ttu-id="e1af5-109">通常，調試資訊會儲存在符號檔案中，與可執行檔不同。</span><span class="sxs-lookup"><span data-stu-id="e1af5-109">Typically, debugging information is stored in a symbol file that is separate from the executable.</span></span> <span data-ttu-id="e1af5-110">調試已停止回應的應用程式時，您必須具備符號資訊的存取權（例如，如果它已損壞）。</span><span class="sxs-lookup"><span data-stu-id="e1af5-110">You must have access to the symbol information when you debug an application that has stopped responding, for example if it crashed.</span></span>

<span data-ttu-id="e1af5-111">當您執行 [損**毀分析**程式] 時，會自動下載符號檔案。</span><span class="sxs-lookup"><span data-stu-id="e1af5-111">Symbol files are automatically downloaded when you run **Crash Analyzer**.</span></span> <span data-ttu-id="e1af5-112">如果電腦沒有網際網路連線，或網路需要電腦存取 HTTP proxy 伺服器，則無法下載符號檔案。</span><span class="sxs-lookup"><span data-stu-id="e1af5-112">If the computer does not have an Internet connection or the network requires the computer to access an HTTP proxy server, the symbol files cannot be downloaded.</span></span>

<span data-ttu-id="e1af5-113">以下是可用於保證對符號檔案存取的選項清單：</span><span class="sxs-lookup"><span data-stu-id="e1af5-113">The following is a list of options that are available for guaranteeing access to symbol files:</span></span>

-   **<span data-ttu-id="e1af5-114">將轉儲檔案複製到另一部電腦。</span><span class="sxs-lookup"><span data-stu-id="e1af5-114">Copy the dump file to another computer.</span></span>** <span data-ttu-id="e1af5-115">如果無法下載符號是因為沒有網際網路連線，請將該損毀傾印檔案複製到有網際網路連線的電腦上，然後在該電腦上執行獨立的 [中斷式中斷**分析程式] 嚮導**。</span><span class="sxs-lookup"><span data-stu-id="e1af5-115">If the symbols cannot be downloaded because of a lack of an Internet connection, copy the crash dump file to a computer that does have an Internet connection and run the stand-alone **Crash Analyzer Wizard** on that computer.</span></span>

-   **<span data-ttu-id="e1af5-116">從另一部電腦存取符號檔案。</span><span class="sxs-lookup"><span data-stu-id="e1af5-116">Access the symbol files from another computer.</span></span>** <span data-ttu-id="e1af5-117">如果無法下載符號是因為沒有網際網路連線，您可以從有網際網路連線的電腦上下載符號，然後將其複製到沒有網際網路連線的電腦，或者您可以將網路磁碟機對應到本機網路上可用的符號位置。</span><span class="sxs-lookup"><span data-stu-id="e1af5-117">If the symbols cannot be downloaded because of a lack of an Internet connection, you can download the symbols from a computer that does have an Internet connection and then copy them to the computer that does not have an Internet connection, or you can map a network drive to a location where the symbols are available on the local network.</span></span> <span data-ttu-id="e1af5-118">如果您在 Windows 復原環境（WindowsRE）中執行 [**崩潰分析**程式]，您可以在 DaRT 復原影像上包含符號檔案。</span><span class="sxs-lookup"><span data-stu-id="e1af5-118">If you run the **Crash Analyzer** in a Windows Recovery Environment (WindowsRE), you can include the symbol files on the DaRT recovery image.</span></span> <span data-ttu-id="e1af5-119">如需有關如何建立復原影像的詳細資訊，請參閱[建立 DaRT 7.0 復原映像](creating-the-dart-70-recovery-image-dart-7.md)。</span><span class="sxs-lookup"><span data-stu-id="e1af5-119">For more information about how to create a recovery image, see [Creating the DaRT 7.0 Recovery Image](creating-the-dart-70-recovery-image-dart-7.md).</span></span>

-   **<span data-ttu-id="e1af5-120">透過 HTTP proxy 伺服器存取符號檔案。</span><span class="sxs-lookup"><span data-stu-id="e1af5-120">Access symbol files through an HTTP proxy server.</span></span>** <span data-ttu-id="e1af5-121">如果由於必須存取 HTTP proxy 伺服器而無法下載符號，請使用下列步驟來存取 HTTP proxy 伺服器。</span><span class="sxs-lookup"><span data-stu-id="e1af5-121">If the symbols cannot be downloaded because an HTTP proxy server must be accessed, use the following steps to access an HTTP proxy server.</span></span> <span data-ttu-id="e1af5-122">在 DaRT7 中，[**崩潰分析程式] 嚮導**在 [**指定符號檔案位置**] 對話方塊頁面上有可用的設定，並以標籤**Proxy 伺服器標示（選用的格式為 "server： port"）**。</span><span class="sxs-lookup"><span data-stu-id="e1af5-122">In DaRT7, the **Crash Analyzer Wizard** has a setting available on the **Specify Symbol Files Location** dialog page, marked with the label **Proxy server (optional, using the format "server:port")**.</span></span> <span data-ttu-id="e1af5-123">您可以使用這個文字方塊來指定 proxy 伺服器。</span><span class="sxs-lookup"><span data-stu-id="e1af5-123">You can use this text box to specify a proxy server.</span></span> <span data-ttu-id="e1af5-124">在 [ \*\* &lt; 主機名稱 &gt; ： &lt; 埠 &gt; \*\*] 中輸入 PROXY 位址， &lt; **主機**名 &gt; 是 DNS 名稱或 IP 位址，而 &lt; **埠** &gt; 則是 TCP 埠號碼（通常是80）。</span><span class="sxs-lookup"><span data-stu-id="e1af5-124">Enter the proxy address in the form **&lt;hostname&gt;:&lt;port&gt;**, where the &lt;**hostname**&gt; is a DNS name or IP address, and the &lt;**port**&gt; is a TCP port number, usually 80.</span></span> <span data-ttu-id="e1af5-125">有兩種模式可讓**崩潰分析**程式執行。</span><span class="sxs-lookup"><span data-stu-id="e1af5-125">There are two modes in which the **Crash Analyzer** can be run.</span></span> <span data-ttu-id="e1af5-126">以下是如何在其中每個模式中使用 proxy 設定的方法：</span><span class="sxs-lookup"><span data-stu-id="e1af5-126">Following is how you use the proxy setting in each of these modes:</span></span>

    -   <span data-ttu-id="e1af5-127">**線上模式：** 在此模式中，如果 [proxy 伺服器] 欄位留空，嚮導就會使用 [控制台] 中的 [網際網路選項] 的 [proxy 設定]。</span><span class="sxs-lookup"><span data-stu-id="e1af5-127">**Online mode:** In this mode, if the proxy server field is left blank, the wizard uses the proxy settings from Internet Options in Control Panel.</span></span> <span data-ttu-id="e1af5-128">如果您在提供的文字方塊中輸入 proxy 位址，就會使用該位址，並會覆寫 [網際網路選項] 中的設定。</span><span class="sxs-lookup"><span data-stu-id="e1af5-128">If you enter a proxy address in the text box which is provided, that address will be used, and it will override the setting in the Internet Options.</span></span>

    -   <span data-ttu-id="e1af5-129">**Windows 修復環境（WindowsRE）：** 當您從 [**診斷和修復工具**]**視窗執行 [** 當機] 時，沒有預設的 proxy 位址。</span><span class="sxs-lookup"><span data-stu-id="e1af5-129">**Windows Recovery Environment (WindowsRE):** When you run **Crash Analyzer** from the **Diagnostics and Recovery Toolset** window, there is no default proxy address.</span></span> <span data-ttu-id="e1af5-130">如果電腦直接連線至網際網路，則不需要 proxy 位址。</span><span class="sxs-lookup"><span data-stu-id="e1af5-130">If the computer is directly connected to the Internet, a proxy address is not required.</span></span> <span data-ttu-id="e1af5-131">因此，您可以在嚮導設定中將此欄位留白。</span><span class="sxs-lookup"><span data-stu-id="e1af5-131">Therefore, you can leave this field blank in the wizard setting.</span></span> <span data-ttu-id="e1af5-132">如果電腦未直接連線至網際網路，且位於擁有 proxy 伺服器的網路環境中，您必須在嚮導中設定 proxy 欄位，以存取符號存放區。</span><span class="sxs-lookup"><span data-stu-id="e1af5-132">If the computer is not directly connected to the Internet, and it is in a network environment that has a proxy server, you must set the proxy field in the wizard to access the symbol store.</span></span> <span data-ttu-id="e1af5-133">您可以從網路系統管理員取得 proxy 位址。</span><span class="sxs-lookup"><span data-stu-id="e1af5-133">The proxy address can be obtained from the network administrator.</span></span> <span data-ttu-id="e1af5-134">只有在公用符號存放區連線至網際網路時，才能設定 proxy 伺服器。</span><span class="sxs-lookup"><span data-stu-id="e1af5-134">Setting the proxy server is important only when the public symbol store is connected to the Internet.</span></span> <span data-ttu-id="e1af5-135">如果符號已在 DaRT 復原影像中，或在本機都可用，則不需要設定 proxy 伺服器。</span><span class="sxs-lookup"><span data-stu-id="e1af5-135">If the symbols are already on the DaRT recovery image, or if they are available locally, setting the proxy server is not required.</span></span>

## <span data-ttu-id="e1af5-136">相關主題</span><span class="sxs-lookup"><span data-stu-id="e1af5-136">Related topics</span></span>


[<span data-ttu-id="e1af5-137">使用損毀分析器來診斷系統失敗</span><span class="sxs-lookup"><span data-stu-id="e1af5-137">Diagnosing System Failures with Crash Analyzer</span></span>](diagnosing-system-failures-with-crash-analyzer--dart-7.md)

 

 





