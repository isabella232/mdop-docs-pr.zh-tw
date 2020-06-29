---
title: 如何確保損毀分析器可以存取符號檔案
description: 如何確保損毀分析器可以存取符號檔案
author: dansimp
ms.assetid: 39e307bd-5d21-4e44-bed6-bf532f580775
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8e0ba2fa777039e1c6ffb91dd997438d8ea50616
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809458"
---
# <span data-ttu-id="86dfe-103">如何確保損毀分析器可以存取符號檔案</span><span class="sxs-lookup"><span data-stu-id="86dfe-103">How to Ensure that Crash Analyzer Can Access Symbol Files</span></span>


<span data-ttu-id="86dfe-104">通常，調試資訊會儲存在與程式不同的符號檔案中。</span><span class="sxs-lookup"><span data-stu-id="86dfe-104">Typically, debugging information is stored in a symbol file that is separate from the program.</span></span> <span data-ttu-id="86dfe-105">當您調試已停止回應的應用程式時，您必須具備符號資訊的存取權。</span><span class="sxs-lookup"><span data-stu-id="86dfe-105">You must have access to the symbol information when you debug an application that has stopped responding.</span></span>

<span data-ttu-id="86dfe-106">當您執行 [損**毀分析**程式] 時，會自動下載符號檔案。</span><span class="sxs-lookup"><span data-stu-id="86dfe-106">Symbol files are automatically downloaded when you run **Crash Analyzer**.</span></span> <span data-ttu-id="86dfe-107">如果電腦沒有網際網路連線，或網路需要電腦存取 HTTP proxy 伺服器，則無法下載符號檔案。</span><span class="sxs-lookup"><span data-stu-id="86dfe-107">If the computer does not have an Internet connection or the network requires the computer to access an HTTP proxy server, the symbol files cannot be downloaded.</span></span>

**<span data-ttu-id="86dfe-108">確保故障分析程式可以存取符號檔案</span><span class="sxs-lookup"><span data-stu-id="86dfe-108">To ensure that Crash Analyzer can access symbol files</span></span>**

1.  **<span data-ttu-id="86dfe-109">將轉儲檔案複製到另一部電腦。</span><span class="sxs-lookup"><span data-stu-id="86dfe-109">Copy the dump file to another computer.</span></span>** <span data-ttu-id="86dfe-110">如果由於缺少網際網路連線而無法下載符號，請將儲存體轉儲檔案複製到有網際網路連線的電腦，然後在該電腦上執行獨立的 [中斷式中斷**分析程式] 嚮導**。</span><span class="sxs-lookup"><span data-stu-id="86dfe-110">If the symbols cannot be downloaded because of a lack of an Internet connection, copy the memory dump file to a computer that does have an Internet connection and run the stand-alone **Crash Analyzer Wizard** on that computer.</span></span>

2.  **<span data-ttu-id="86dfe-111">從另一部電腦存取符號檔案。</span><span class="sxs-lookup"><span data-stu-id="86dfe-111">Access the symbol files from another computer.</span></span>** <span data-ttu-id="86dfe-112">如果無法下載符號是因為沒有網際網路連線，您可以從有網際網路連線的電腦上下載符號，然後將其複製到沒有網際網路連線的電腦，或者您可以將網路磁碟機對應到本機網路上可用的符號位置。</span><span class="sxs-lookup"><span data-stu-id="86dfe-112">If the symbols cannot be downloaded because of a lack of an Internet connection, you can download the symbols from a computer that does have an Internet connection and then copy them to the computer that does not have an Internet connection, or you can map a network drive to a location where the symbols are available on the local network.</span></span> <span data-ttu-id="86dfe-113">如果您在 Windows 復原環境（WindowsRE）中執行 [當機]，您**可以在 Microsoft** Diagnostics 和復原工具集（DaRT）10復原影像中包含符號檔案。</span><span class="sxs-lookup"><span data-stu-id="86dfe-113">If you run the **Crash Analyzer** in a Windows Recovery Environment (WindowsRE), you can include the symbol files on the Microsoft Diagnostics and Recovery Toolset (DaRT) 10 recovery image.</span></span>

3.  **<span data-ttu-id="86dfe-114">透過 HTTP proxy 伺服器存取符號檔案。</span><span class="sxs-lookup"><span data-stu-id="86dfe-114">Access symbol files through an HTTP proxy server.</span></span>** <span data-ttu-id="86dfe-115">如果由於必須存取 HTTP proxy 伺服器而無法下載符號，請使用下列步驟來存取 HTTP proxy 伺服器。</span><span class="sxs-lookup"><span data-stu-id="86dfe-115">If the symbols cannot be downloaded because an HTTP proxy server must be accessed, use the following steps to access an HTTP proxy server.</span></span> <span data-ttu-id="86dfe-116">在 DaRT 10 中，當您在 [指定符號檔案位置] 對話方塊頁面（**選用 [server： port "格式）** 標示時，[**崩潰分析工具]** 的設定會顯示在 [**指定符號檔案位置**] 對話方塊頁面上。</span><span class="sxs-lookup"><span data-stu-id="86dfe-116">In DaRT 10, the **Crash Analyzer Wizard** has a setting available on the **Specify Symbol Files Location** dialog page, marked with the label **Proxy server (optional, using the format "server:port")**.</span></span> <span data-ttu-id="86dfe-117">您可以使用這個文字方塊來指定 proxy 伺服器。</span><span class="sxs-lookup"><span data-stu-id="86dfe-117">You can use this text box to specify a proxy server.</span></span> <span data-ttu-id="86dfe-118">在表單\*\* &lt; 主機名稱 &gt; ： &lt; port &gt; \*\*中輸入 proxy 位址，其中 &lt; **主機名稱** &gt; 是 DNS 名稱或 IP 位址，而 &lt; **埠** &gt; 則是 TCP 埠號碼。</span><span class="sxs-lookup"><span data-stu-id="86dfe-118">Enter the proxy address in the form **&lt;hostname&gt;:&lt;port&gt;**, where the &lt;**hostname**&gt; is a DNS name or IP address, and the &lt;**port**&gt; is a TCP port number.</span></span> <span data-ttu-id="86dfe-119">有兩種模式可讓**崩潰分析**程式執行。</span><span class="sxs-lookup"><span data-stu-id="86dfe-119">There are two modes in which the **Crash Analyzer** can be run.</span></span> <span data-ttu-id="86dfe-120">以下是如何在其中每個模式中使用 proxy 設定的方法：</span><span class="sxs-lookup"><span data-stu-id="86dfe-120">Following is how you use the proxy setting in each of these modes:</span></span>

    -   <span data-ttu-id="86dfe-121">**線上模式：** 在此模式中，如果 [proxy 伺服器] 欄位留空，嚮導就會使用 [控制台] 中的 [網際網路選項] 的 [proxy 設定]。</span><span class="sxs-lookup"><span data-stu-id="86dfe-121">**Online mode:** In this mode, if the proxy server field is left blank, the wizard uses the proxy settings from Internet Options in Control Panel.</span></span> <span data-ttu-id="86dfe-122">如果您在提供的文字方塊中輸入 proxy 位址，就會使用該位址，並會覆寫 [網際網路選項] 中的設定。</span><span class="sxs-lookup"><span data-stu-id="86dfe-122">If you enter a proxy address in the text box which is provided, that address will be used, and it will override the setting in the Internet Options.</span></span>

    -   <span data-ttu-id="86dfe-123">Windows 復原環境（WindowsRE）：當您從 [**診斷及修復工具**]**視窗執行 [** 當機] 時，沒有預設的 proxy 位址。</span><span class="sxs-lookup"><span data-stu-id="86dfe-123">Windows Recovery Environment (WindowsRE): When you run **Crash Analyzer** from the **Diagnostics and Recovery Toolset** window, there is no default proxy address.</span></span> <span data-ttu-id="86dfe-124">如果電腦直接連線至網際網路，則不需要 proxy 位址。</span><span class="sxs-lookup"><span data-stu-id="86dfe-124">If the computer is directly connected to the Internet, a proxy address is not required.</span></span> <span data-ttu-id="86dfe-125">因此，您可以在嚮導設定中將此欄位留白。</span><span class="sxs-lookup"><span data-stu-id="86dfe-125">Therefore, you can leave this field blank in the wizard setting.</span></span> <span data-ttu-id="86dfe-126">如果電腦未直接連線至網際網路，且位於擁有 proxy 伺服器的網路環境中，您必須在嚮導中設定 proxy 欄位，以存取符號存放區。</span><span class="sxs-lookup"><span data-stu-id="86dfe-126">If the computer is not directly connected to the Internet, and it is in a network environment that has a proxy server, you must set the proxy field in the wizard to access the symbol store.</span></span> <span data-ttu-id="86dfe-127">您可以從網路系統管理員取得 proxy 位址。</span><span class="sxs-lookup"><span data-stu-id="86dfe-127">The proxy address can be obtained from the network administrator.</span></span> <span data-ttu-id="86dfe-128">只有在公用符號存放區連線至網際網路時，才能設定 proxy 伺服器。</span><span class="sxs-lookup"><span data-stu-id="86dfe-128">Setting the proxy server is important only when the public symbol store is connected to the Internet.</span></span> <span data-ttu-id="86dfe-129">如果符號已在 DaRT 復原影像中，或在本機都可用，則不需要設定 proxy 伺服器。</span><span class="sxs-lookup"><span data-stu-id="86dfe-129">If the symbols are already on the DaRT recovery image, or if they are available locally, setting the proxy server is not required.</span></span>

## <span data-ttu-id="86dfe-130">相關主題</span><span class="sxs-lookup"><span data-stu-id="86dfe-130">Related topics</span></span>


[<span data-ttu-id="86dfe-131">使用損毀分析器來診斷系統失敗</span><span class="sxs-lookup"><span data-stu-id="86dfe-131">Diagnosing System Failures with Crash Analyzer</span></span>](diagnosing-system-failures-with-crash-analyzer-dart-10.md)

[<span data-ttu-id="86dfe-132">適用於 DaRT 10 的操作</span><span class="sxs-lookup"><span data-stu-id="86dfe-132">Operations for DaRT 10</span></span>](operations-for-dart-10.md)

 

 





