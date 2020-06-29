---
title: MED-V 事件記錄檔訊息
description: MED-V 事件記錄檔訊息
author: dansimp
ms.assetid: 7ba7344d-153b-4cc4-a00a-5d42aee9986b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b5d8dcf1cce48d6c1e29d46b4db7ac1550aa9477
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809740"
---
# <span data-ttu-id="74800-103">MED-V 事件記錄檔訊息</span><span class="sxs-lookup"><span data-stu-id="74800-103">MED-V Event Log Messages</span></span>


<span data-ttu-id="74800-104">Microsoft 企業版桌面虛擬化（MED-V）2.0 的記錄檔提供有關如何在企業中部署和管理 MED-V 的詳細資訊，並協助驗證功能或協助您解決問題。</span><span class="sxs-lookup"><span data-stu-id="74800-104">The log files for Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 provide detailed information about how to deploy and manage MED-V in your enterprise and help verify functionality or help troubleshoot issues.</span></span>

## <span data-ttu-id="74800-105">事件識別碼</span><span class="sxs-lookup"><span data-stu-id="74800-105">Event IDs</span></span>


<span data-ttu-id="74800-106">以下是 MED-V 事件識別碼的清單，可協助您在部署或管理 MED-V 時所遇到的問題進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="74800-106">The following are a list of MED-V event IDs to help troubleshoot issues that you might encounter when you deploy or manage MED-V.</span></span>

### <span data-ttu-id="74800-107">Fts</span><span class="sxs-lookup"><span data-stu-id="74800-107">Fts</span></span>

<span data-ttu-id="74800-108">顯示第一次設定的 [事件識別碼]。</span><span class="sxs-lookup"><span data-stu-id="74800-108">Shows the event IDs for first time setup.</span></span>

### <span data-ttu-id="74800-109">事件 ID 3066</span><span class="sxs-lookup"><span data-stu-id="74800-109">Event ID 3066</span></span>

<span data-ttu-id="74800-110">啟動虛擬機器操作失敗。</span><span class="sxs-lookup"><span data-stu-id="74800-110">Start virtual machine operation failed.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="74800-111">描述</span><span class="sxs-lookup"><span data-stu-id="74800-111">Description</span></span>**  
<span data-ttu-id="74800-112">您用來建立 MED-V 工作區的虛擬硬碟（VHD）可能存在問題。</span><span class="sxs-lookup"><span data-stu-id="74800-112">A potential problem exists with the virtual hard disk (VHD) that you are using to create a MED-V workspace.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="74800-113">解決方案</span><span class="sxs-lookup"><span data-stu-id="74800-113">Solution</span></span>**  
<span data-ttu-id="74800-114">請確認您可以使用 med-v 進行 med-v，然後啟動該虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="74800-114">Verify that you can create a virtual machine with the VHD for MED-V and that it can be started.</span></span>

### <span data-ttu-id="74800-115">事件 ID 3071</span><span class="sxs-lookup"><span data-stu-id="74800-115">Event ID 3071</span></span>

<span data-ttu-id="74800-116">虛擬機器準備失敗。</span><span class="sxs-lookup"><span data-stu-id="74800-116">Virtual machine preparation failed.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="74800-117">描述</span><span class="sxs-lookup"><span data-stu-id="74800-117">Description</span></span>**  
<span data-ttu-id="74800-118">第一次設定可能是由許多不同的問題所造成的，因此發生問題。</span><span class="sxs-lookup"><span data-stu-id="74800-118">A problem occurred with first time setup that might have been caused by many different issues.</span></span> <span data-ttu-id="74800-119">這包括網路連線的問題。</span><span class="sxs-lookup"><span data-stu-id="74800-119">These include problems with network connectivity.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="74800-120">解決方案</span><span class="sxs-lookup"><span data-stu-id="74800-120">Solution</span></span>**  
<span data-ttu-id="74800-121">重新開機 MED-V 主機代理程式，以便在第一次安裝時重新執行。</span><span class="sxs-lookup"><span data-stu-id="74800-121">Restart the MED-V Host Agent to rerun first time setup.</span></span>

### <span data-ttu-id="74800-122">事件 ID 3078</span><span class="sxs-lookup"><span data-stu-id="74800-122">Event ID 3078</span></span>

<span data-ttu-id="74800-123">虛擬機器準備失敗。</span><span class="sxs-lookup"><span data-stu-id="74800-123">Virtual machine preparation failed.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="74800-124">描述</span><span class="sxs-lookup"><span data-stu-id="74800-124">Description</span></span>**  
<span data-ttu-id="74800-125">您用來建立 MED-V 工作區的 VHD 可能存在問題。</span><span class="sxs-lookup"><span data-stu-id="74800-125">A potential problem exists with the VHD that you are using to create a MED-V workspace.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="74800-126">解決方案</span><span class="sxs-lookup"><span data-stu-id="74800-126">Solution</span></span>**  
<span data-ttu-id="74800-127">請確認您可以使用 med-v 進行 med-v，然後啟動該虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="74800-127">Verify that you can create a virtual machine with the VHD for MED-V and that it can be started.</span></span>

### <span data-ttu-id="74800-128">事件 ID 3079</span><span class="sxs-lookup"><span data-stu-id="74800-128">Event ID 3079</span></span>

<span data-ttu-id="74800-129">正在重新嘗試虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="74800-129">Retrying virtual machine preparation.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="74800-130">描述</span><span class="sxs-lookup"><span data-stu-id="74800-130">Description</span></span>**  
<span data-ttu-id="74800-131">MED-V 正在嘗試準備虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="74800-131">MED-V is trying to prepare the virtual machine.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="74800-132">解決方案</span><span class="sxs-lookup"><span data-stu-id="74800-132">Solution</span></span>**  
<span data-ttu-id="74800-133">不需要執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="74800-133">No action is required.</span></span> <span data-ttu-id="74800-134">[第一次設定完成]。</span><span class="sxs-lookup"><span data-stu-id="74800-134">Let first time setup finish.</span></span>

### <span data-ttu-id="74800-135">事件 ID 3080</span><span class="sxs-lookup"><span data-stu-id="74800-135">Event ID 3080</span></span>

<span data-ttu-id="74800-136">用戶端在準備虛擬機器時已停止。</span><span class="sxs-lookup"><span data-stu-id="74800-136">The client was stopped when preparing the virtual machine.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="74800-137">描述</span><span class="sxs-lookup"><span data-stu-id="74800-137">Description</span></span>**  
<span data-ttu-id="74800-138">MED-V 在嘗試準備虛擬機器時，會意外停止。</span><span class="sxs-lookup"><span data-stu-id="74800-138">MED-V stops unexpectedly when it tries to prepare the virtual machine.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="74800-139">解決方案</span><span class="sxs-lookup"><span data-stu-id="74800-139">Solution</span></span>**  
<span data-ttu-id="74800-140">啟動 MED-V 主機代理程式，並讓第一次設定完成</span><span class="sxs-lookup"><span data-stu-id="74800-140">Start the MED-V Host Agent and let first time setup complete</span></span>

### <span data-ttu-id="74800-141">事件 ID 3084</span><span class="sxs-lookup"><span data-stu-id="74800-141">Event ID 3084</span></span>

<span data-ttu-id="74800-142">虛擬機器無效。</span><span class="sxs-lookup"><span data-stu-id="74800-142">Virtual machine is not valid.</span></span> <span data-ttu-id="74800-143">第一次需要重新執行設定。</span><span class="sxs-lookup"><span data-stu-id="74800-143">First time setup needs to be re-run.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="74800-144">描述</span><span class="sxs-lookup"><span data-stu-id="74800-144">Description</span></span>**  
<span data-ttu-id="74800-145">MED-V 主機代理程式偵測到虛擬機器的問題。</span><span class="sxs-lookup"><span data-stu-id="74800-145">The MED-V Host Agent detected a problem with the virtual machine.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="74800-146">解決方案</span><span class="sxs-lookup"><span data-stu-id="74800-146">Solution</span></span>**  
<span data-ttu-id="74800-147">不需要執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="74800-147">No action is required.</span></span> <span data-ttu-id="74800-148">[第一次設定完成]。</span><span class="sxs-lookup"><span data-stu-id="74800-148">Let first time setup finish.</span></span>

### <span data-ttu-id="74800-149">事件 ID 3099</span><span class="sxs-lookup"><span data-stu-id="74800-149">Event ID 3099</span></span>

<span data-ttu-id="74800-150">啟動虛擬機器的呼叫失敗。</span><span class="sxs-lookup"><span data-stu-id="74800-150">Call to start virtual machine failed.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="74800-151">描述</span><span class="sxs-lookup"><span data-stu-id="74800-151">Description</span></span>**  
<span data-ttu-id="74800-152">您用來建立 MED-V 工作區的 VHD 可能存在問題。</span><span class="sxs-lookup"><span data-stu-id="74800-152">A potential problem exists with the VHD you are using to create a MED-V workspace.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="74800-153">解決方案</span><span class="sxs-lookup"><span data-stu-id="74800-153">Solution</span></span>**  
<span data-ttu-id="74800-154">確認您可以使用 med-v 進行 med-v，然後才能開啟虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="74800-154">Verify that you can create a virtual machine with the VHD for MED-V and that it can be opened.</span></span>

### <span data-ttu-id="74800-155">VM 管理</span><span class="sxs-lookup"><span data-stu-id="74800-155">VM Management</span></span>

### <span data-ttu-id="74800-156">事件 ID 4022</span><span class="sxs-lookup"><span data-stu-id="74800-156">Event ID 4022</span></span>

<span data-ttu-id="74800-157">向 VM 發出命令時發生 VMManagerException 致命錯誤。</span><span class="sxs-lookup"><span data-stu-id="74800-157">VMManagerException Fatal error while issuing command to VM.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="74800-158">描述</span><span class="sxs-lookup"><span data-stu-id="74800-158">Description</span></span>**  
<span data-ttu-id="74800-159">最終使用者嘗試登入，或關閉 MED-V 主機來結束 MED-V，且超過 VMTaskTimeout 設定設定。</span><span class="sxs-lookup"><span data-stu-id="74800-159">The end user tried to exit MED-V by logging off or by shutting down the MED-V host, and the VMTaskTimeout configuration setting was exceeded.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="74800-160">解決方案</span><span class="sxs-lookup"><span data-stu-id="74800-160">Solution</span></span>**  
<span data-ttu-id="74800-161">重新開機 MED-V。</span><span class="sxs-lookup"><span data-stu-id="74800-161">Restart MED-V.</span></span>

### <span data-ttu-id="74800-162">事件 ID 4028</span><span class="sxs-lookup"><span data-stu-id="74800-162">Event ID 4028</span></span>

<span data-ttu-id="74800-163">VM 操作超時。</span><span class="sxs-lookup"><span data-stu-id="74800-163">VM Operation timed out.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="74800-164">描述</span><span class="sxs-lookup"><span data-stu-id="74800-164">Description</span></span>**  
<span data-ttu-id="74800-165">最終使用者嘗試登入，或關閉主機，並超過 VMTaskTimeout 設定設定，即可結束 MED-V。</span><span class="sxs-lookup"><span data-stu-id="74800-165">The end user tried to exit MED-V by logging off or by shutting down the host, and the VMTaskTimeout configuration setting was exceeded.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="74800-166">解決方案</span><span class="sxs-lookup"><span data-stu-id="74800-166">Solution</span></span>**  
<span data-ttu-id="74800-167">重新開機 MED-V。</span><span class="sxs-lookup"><span data-stu-id="74800-167">Restart MED-V.</span></span>

### <span data-ttu-id="74800-168">事件 ID 4038</span><span class="sxs-lookup"><span data-stu-id="74800-168">Event ID 4038</span></span>

<span data-ttu-id="74800-169">Vmsal 已將錯誤訊息張貼給使用者。</span><span class="sxs-lookup"><span data-stu-id="74800-169">Vmsal posted an error message to the user.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="74800-170">描述</span><span class="sxs-lookup"><span data-stu-id="74800-170">Description</span></span>**  
<span data-ttu-id="74800-171">系統會向最終使用者顯示錯誤訊息，指出 MED-V 無法啟動虛擬應用程式。</span><span class="sxs-lookup"><span data-stu-id="74800-171">An error message is displayed to the end user stating that MED-V could not start the virtual application.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="74800-172">解決方案</span><span class="sxs-lookup"><span data-stu-id="74800-172">Solution</span></span>**  
<span data-ttu-id="74800-173">如果錯誤是在一列中記錄兩次以上的時間，請停止 MED-V 並使用 Windows Virtual PC 主控台連線至虛擬機器，並嘗試以全螢幕啟動應用程式。</span><span class="sxs-lookup"><span data-stu-id="74800-173">If the error is logged two or more times in a row, stop MED-V and connect to the virtual machine by using Windows Virtual PC console and attempt to start the application in Full Screen.</span></span>

### <span data-ttu-id="74800-174">事件 ID 4040</span><span class="sxs-lookup"><span data-stu-id="74800-174">Event ID 4040</span></span>

<span data-ttu-id="74800-175">因為未在來賓中初始化 TerminalServices，所以回收新增功能。</span><span class="sxs-lookup"><span data-stu-id="74800-175">Recycling Additions because TerminalServices is not initialized in the guest.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="74800-176">描述</span><span class="sxs-lookup"><span data-stu-id="74800-176">Description</span></span>**  
<span data-ttu-id="74800-177">MED-V 已重新開機虛擬機器，因為遠端桌面服務未在虛擬機器上初始化。</span><span class="sxs-lookup"><span data-stu-id="74800-177">MED-V rebooted the virtual machine because Remote Desktop Services was not initialized on the virtual machine.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="74800-178">解決方案</span><span class="sxs-lookup"><span data-stu-id="74800-178">Solution</span></span>**  
<span data-ttu-id="74800-179">如果錯誤是在一列中記錄兩次以上的時間，請停止 MED-V 並使用 Windows Virtual PC 主控台連線至虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="74800-179">If the error is logged two or more times in a row, stop MED-V and connect to the virtual machine by using Windows Virtual PC console.</span></span>

### <span data-ttu-id="74800-180">事件 ID 4042</span><span class="sxs-lookup"><span data-stu-id="74800-180">Event ID 4042</span></span>

<span data-ttu-id="74800-181">無法回收來賓中的新增功能。</span><span class="sxs-lookup"><span data-stu-id="74800-181">Failed to recycle additions in the guest.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="74800-182">描述</span><span class="sxs-lookup"><span data-stu-id="74800-182">Description</span></span>**  
<span data-ttu-id="74800-183">MED-V 無法回收虛擬機器上的虛擬機器新增功能。</span><span class="sxs-lookup"><span data-stu-id="74800-183">MED-V failed to recycle virtual machine additions on the virtual machine.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="74800-184">解決方案</span><span class="sxs-lookup"><span data-stu-id="74800-184">Solution</span></span>**  
<span data-ttu-id="74800-185">如果錯誤是在一列中記錄兩次以上的時間，請停止 MED-V 並使用 Windows Virtual PC 主控台連線至虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="74800-185">If the error is logged two or more times in a row, stop MED-V and connect to the virtual machine by using Windows Virtual PC console.</span></span>

### <span data-ttu-id="74800-186">事件 ID 4043</span><span class="sxs-lookup"><span data-stu-id="74800-186">Event ID 4043</span></span>

<span data-ttu-id="74800-187">無法在虛擬機器中重設過期的密碼。</span><span class="sxs-lookup"><span data-stu-id="74800-187">Failed to reset expired password in the virtual machine.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="74800-188">描述</span><span class="sxs-lookup"><span data-stu-id="74800-188">Description</span></span>**  
<span data-ttu-id="74800-189">最終使用者未在虛擬機器中重設密碼，已過期。</span><span class="sxs-lookup"><span data-stu-id="74800-189">The end user did not reset the password in the virtual machine before it expired.</span></span> <span data-ttu-id="74800-190">因此，使用者可能無法存取網路資源或儲存工作。</span><span class="sxs-lookup"><span data-stu-id="74800-190">As a result, the user might not be able to access network resources or save work.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="74800-191">解決方案</span><span class="sxs-lookup"><span data-stu-id="74800-191">Solution</span></span>**  
<span data-ttu-id="74800-192">關閉 MED-V 來賓，然後重新開機它。</span><span class="sxs-lookup"><span data-stu-id="74800-192">Shut down the MED-V guest and restart it.</span></span>

### <span data-ttu-id="74800-193">URL 重新導向</span><span class="sxs-lookup"><span data-stu-id="74800-193">URL Redirection</span></span>

### <span data-ttu-id="74800-194">事件 ID 5005</span><span class="sxs-lookup"><span data-stu-id="74800-194">Event ID 5005</span></span>

<span data-ttu-id="74800-195">無法從配置取得 VM 名稱;無法啟動來賓瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="74800-195">Couldn’t get VM name from configuration; can’t launch guest browser.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="74800-196">描述</span><span class="sxs-lookup"><span data-stu-id="74800-196">Description</span></span>**  
<span data-ttu-id="74800-197">URL 重新導向無法從配置取得 MED-V 工作區名稱。</span><span class="sxs-lookup"><span data-stu-id="74800-197">URL Redirection could not obtain the MED-V workspace name from the configuration.</span></span> <span data-ttu-id="74800-198">因此，它無法通知 Windows 虛擬電腦在 MED-V 工作區瀏覽器中開啟重新導向的 URL。</span><span class="sxs-lookup"><span data-stu-id="74800-198">As a result, it cannot inform Windows Virtual PC to open the redirected URL in the MED-V workspace browser.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="74800-199">解決方案</span><span class="sxs-lookup"><span data-stu-id="74800-199">Solution</span></span>**  
<span data-ttu-id="74800-200">確定 MED-V 工作區名稱已設定，且與 C:\\Users\\ &lt; *使用者* &gt; \\Virtual 電腦目錄中的虛擬電腦名稱稱相符。</span><span class="sxs-lookup"><span data-stu-id="74800-200">Ensure that the MED-V workspace name is set and that it matches a virtual machine name in the C:\\Users\\&lt;*user*&gt;\\Virtual Machines directory.</span></span> <span data-ttu-id="74800-201">MED-V 工作區名稱位於 HKLM\\SOFTWARE\\Microsoft\\Medv\\v2\\VM\\Name。</span><span class="sxs-lookup"><span data-stu-id="74800-201">The MED-V workspace name is located at HKLM\\SOFTWARE\\Microsoft\\Medv\\v2\\VM\\Name.</span></span>

<span data-ttu-id="74800-202">例如，如果使用者是 "Matt"，而工作區名稱是 "mattsworkspace"，HKLM\\SOFTWARE\\Microsoft\\Medv\\v2\\VM\\Name 的值應該是 "mattsworkspace"，且應該有一個名為 C:\\Users\\Matt\\Virtual Machines\\mattsworkspace.vcmx. 的檔案。</span><span class="sxs-lookup"><span data-stu-id="74800-202">For example, if the user is "Matt" and the workspace name is "mattsworkspace", the value of HKLM\\SOFTWARE\\Microsoft\\Medv\\v2\\VM\\Name should be "mattsworkspace", and there should be a file that is named C:\\Users\\Matt\\Virtual Machines\\mattsworkspace.vcmx.</span></span>

### <span data-ttu-id="74800-203">事件 ID 5006</span><span class="sxs-lookup"><span data-stu-id="74800-203">Event ID 5006</span></span>

<span data-ttu-id="74800-204">無法建立管道伺服器。</span><span class="sxs-lookup"><span data-stu-id="74800-204">Failed to create pipe server.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="74800-205">描述</span><span class="sxs-lookup"><span data-stu-id="74800-205">Description</span></span>**  
<span data-ttu-id="74800-206">URL 重新導向服務無法建立管道伺服器來與 Internet Explorer 進行通訊。</span><span class="sxs-lookup"><span data-stu-id="74800-206">The URL Redirection service could not create the pipe server to communicate with Internet Explorer.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="74800-207">解決方案</span><span class="sxs-lookup"><span data-stu-id="74800-207">Solution</span></span>**  
<span data-ttu-id="74800-208">檢查系統事件記錄，以嘗試建立路徑開頭如下所示的檔案或資源： "\\\\.\\pipe\\MEDVUrlRedirectionPipe\_"，並以使用者的使用者名稱和功能變數名稱結束。</span><span class="sxs-lookup"><span data-stu-id="74800-208">Check system event logs for attempts to create a file or resource whose path begins similar to the following: "\\\\.\\pipe\\MEDVUrlRedirectionPipe\_" and ends with the user’s user name and domain name.</span></span> <span data-ttu-id="74800-209">如果事件記錄中不存在這項功能，請重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="74800-209">If this is not present in the event log, restart the computer.</span></span>

### <span data-ttu-id="74800-210">ConfigMgr （來賓）</span><span class="sxs-lookup"><span data-stu-id="74800-210">ConfigMgr (Guest)</span></span>

### <span data-ttu-id="74800-211">事件 ID 7001</span><span class="sxs-lookup"><span data-stu-id="74800-211">Event ID 7001</span></span>

<span data-ttu-id="74800-212">主機網路設定資料格式不正確。</span><span class="sxs-lookup"><span data-stu-id="74800-212">The host network configuration data is not properly formatted.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="74800-213">描述</span><span class="sxs-lookup"><span data-stu-id="74800-213">Description</span></span>**  
<span data-ttu-id="74800-214">從主機接收的網路設定是格式不正確的 XML 字串，或從主機傳回的網路資訊無法寫入 XML 檔。</span><span class="sxs-lookup"><span data-stu-id="74800-214">Either the network configuration received from the host is an incorrectly formatted XML string, or the network information returned from the host cannot be written to an XML document.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="74800-215">解決方案</span><span class="sxs-lookup"><span data-stu-id="74800-215">Solution</span></span>**  
<span data-ttu-id="74800-216">重新開機主機電腦和虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="74800-216">Restart the host computer and the virtual machine.</span></span>

### <span data-ttu-id="74800-217">事件 ID 7005</span><span class="sxs-lookup"><span data-stu-id="74800-217">Event ID 7005</span></span>

<span data-ttu-id="74800-218">已偵測到主機網路設定的變更，但由於主機網路設定資料格式不正確而無法套用。</span><span class="sxs-lookup"><span data-stu-id="74800-218">A change to the host network configuration was detected, but was not able to be applied because the host network configuration data was not properly formatted.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="74800-219">描述</span><span class="sxs-lookup"><span data-stu-id="74800-219">Description</span></span>**  
<span data-ttu-id="74800-220">主機網路設定的變更已傳送到虛擬機器，但無法在虛擬機器中處理，因為錯誤。</span><span class="sxs-lookup"><span data-stu-id="74800-220">A change to the host network configuration was communicated to the virtual machine, but could not be processed in the virtual machine because of an error.</span></span> <span data-ttu-id="74800-221">此錯誤可能是因為資料格式不正確，或無法將資訊設定成 Windows Management Instrumentation （WMI） CCMNetworkAdapter 實例。</span><span class="sxs-lookup"><span data-stu-id="74800-221">This error could be caused by incorrectly formatted data or the inability to set the information into the Windows Management Instrumentation (WMI) CCMNetworkAdapter instance.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="74800-222">解決方案</span><span class="sxs-lookup"><span data-stu-id="74800-222">Solution</span></span>**  
<span data-ttu-id="74800-223">重新開機主機和虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="74800-223">Restart the host and virtual machine.</span></span>

### <span data-ttu-id="74800-224">ConfigMgr （主機）</span><span class="sxs-lookup"><span data-stu-id="74800-224">ConfigMgr (Host)</span></span>

### <span data-ttu-id="74800-225">事件 ID 8006</span><span class="sxs-lookup"><span data-stu-id="74800-225">Event ID 8006</span></span>

<span data-ttu-id="74800-226">找不到虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="74800-226">The virtual machine cannot be found.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="74800-227">描述</span><span class="sxs-lookup"><span data-stu-id="74800-227">Description</span></span>**  
<span data-ttu-id="74800-228">Windows Virtual 電腦7找不到虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="74800-228">Windows Virtual PC 7 cannot locate the virtual machine.</span></span> <span data-ttu-id="74800-229">虛擬機器可能已被刪除、移動、移除或存取遭到拒絕。</span><span class="sxs-lookup"><span data-stu-id="74800-229">The virtual machine might have been deleted, moved, removed, or access was denied.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="74800-230">解決方案</span><span class="sxs-lookup"><span data-stu-id="74800-230">Solution</span></span>**  
<span data-ttu-id="74800-231">重新安裝虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="74800-231">Reinstall the virtual machine.</span></span>

### <span data-ttu-id="74800-232">事件 ID 8008</span><span class="sxs-lookup"><span data-stu-id="74800-232">Event ID 8008</span></span>

<span data-ttu-id="74800-233">無法檢索工作站的網路設定資訊。</span><span class="sxs-lookup"><span data-stu-id="74800-233">The workstation's network configuration information could not be retrieved.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="74800-234">描述</span><span class="sxs-lookup"><span data-stu-id="74800-234">Description</span></span>**  
<span data-ttu-id="74800-235">無法從 MED-V 主機收集網路設定資訊，很可能是因為 .NET Framework 中的系統呼叫失敗。</span><span class="sxs-lookup"><span data-stu-id="74800-235">Network configuration information could not be collected from the MED-V host, most likely because of a system call failure in the .NET Framework.</span></span> <span data-ttu-id="74800-236">如果從 MED-V 主機傳回的網路資訊無法寫入 XML 檔，也會發生此錯誤。</span><span class="sxs-lookup"><span data-stu-id="74800-236">This failure can also occur if the network information returned from the MED-V host cannot be written to an XML document.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="74800-237">解決方案</span><span class="sxs-lookup"><span data-stu-id="74800-237">Solution</span></span>**  
<span data-ttu-id="74800-238">重新開機主機工作站。</span><span class="sxs-lookup"><span data-stu-id="74800-238">Restart the host workstation.</span></span>

### <span data-ttu-id="74800-239">事件 ID 8010</span><span class="sxs-lookup"><span data-stu-id="74800-239">Event ID 8010</span></span>

<span data-ttu-id="74800-240">無法在虛擬機器中設定網路設定資料。</span><span class="sxs-lookup"><span data-stu-id="74800-240">The network configuration data could not be set in the virtual machine.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="74800-241">描述</span><span class="sxs-lookup"><span data-stu-id="74800-241">Description</span></span>**  
<span data-ttu-id="74800-242">MED-V hostnetwork 位址轉換（NAT）無法傳送到虛擬機器，很可能是因為虛擬機器處於錯誤的狀態，或未安裝或啟用 Windows 虛擬電腦的新增功能。</span><span class="sxs-lookup"><span data-stu-id="74800-242">The MED-V hostnetwork address translation (NAT) could not be communicated to the virtual machine, most likely because the virtual machine is in a bad state or the Windows Virtual PC Additions were not installed or enabled.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="74800-243">解決方案</span><span class="sxs-lookup"><span data-stu-id="74800-243">Solution</span></span>**  
<span data-ttu-id="74800-244">關閉並重新啟動虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="74800-244">Shut down and restart the virtual machine.</span></span> <span data-ttu-id="74800-245">此外，您可能還需要重新安裝虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="74800-245">In addition, you might have to reinstall the virtual machine.</span></span>

### <span data-ttu-id="74800-246">事件 ID 8011</span><span class="sxs-lookup"><span data-stu-id="74800-246">Event ID 8011</span></span>

<span data-ttu-id="74800-247">無法在虛擬機器中重設網路設定資料。</span><span class="sxs-lookup"><span data-stu-id="74800-247">The network configuration data could not be reset in the virtual machine.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="74800-248">描述</span><span class="sxs-lookup"><span data-stu-id="74800-248">Description</span></span>**  
<span data-ttu-id="74800-249">MED-V hostnetwork 設定（橋）無法傳送到虛擬機器，很可能是因為虛擬機器處於錯誤狀態，或未安裝或啟用 Windows 虛擬電腦的新增功能。</span><span class="sxs-lookup"><span data-stu-id="74800-249">The MED-V hostnetwork configuration (BRIDGED) could not be communicated to the virtual machine, most likely because the virtual machine is in a bad state or the Windows Virtual PC Additions were not installed or enabled.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="74800-250">解決方案</span><span class="sxs-lookup"><span data-stu-id="74800-250">Solution</span></span>**  
<span data-ttu-id="74800-251">關閉並重新啟動虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="74800-251">Shut down and restart the virtual machine.</span></span> <span data-ttu-id="74800-252">此外，您可能還需要重新安裝虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="74800-252">In addition, you might have to reinstall the virtual machine.</span></span>

### <span data-ttu-id="74800-253">印表機重新導向</span><span class="sxs-lookup"><span data-stu-id="74800-253">Printer Redirection</span></span>

### <span data-ttu-id="74800-254">事件 ID 9001</span><span class="sxs-lookup"><span data-stu-id="74800-254">Event ID 9001</span></span>

<span data-ttu-id="74800-255">檔案許可權錯誤。</span><span class="sxs-lookup"><span data-stu-id="74800-255">File Permission Error.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="74800-256">描述</span><span class="sxs-lookup"><span data-stu-id="74800-256">Description</span></span>**  
<span data-ttu-id="74800-257">使用者無權存取開啟或建立要讀取的 MED-V 印表機檔案所需的資料夾。</span><span class="sxs-lookup"><span data-stu-id="74800-257">The end user is not authorized to access the folder required to open or create the MED-V printer file for reading.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="74800-258">解決方案</span><span class="sxs-lookup"><span data-stu-id="74800-258">Solution</span></span>**  
<span data-ttu-id="74800-259">確認您可以存取 User\\AppData\\ 路徑，以及使用者有權讀取及寫入該路徑。</span><span class="sxs-lookup"><span data-stu-id="74800-259">Verify that the User\\AppData\\ path can be accessed and that the user has permission to read and write to it.</span></span> <span data-ttu-id="74800-260">例如，如果使用者是 "Matt"，則路徑 C:\\Users\\Matt\\AppData\\ 和其中的所有檔案都應該有讀取和寫入權限。</span><span class="sxs-lookup"><span data-stu-id="74800-260">For example, if the user is "Matt", the path C:\\Users\\Matt\\AppData\\, and all files therein should have Read and Write permissions.</span></span> <span data-ttu-id="74800-261">如果它存在，則路徑 C:\\Users\\Matt\\AppData\\Local\\Microsoft\\MEDV\\v2\\ 及其中的所有檔案，都應該擁有讀取和寫入權限。</span><span class="sxs-lookup"><span data-stu-id="74800-261">And if it exists, the path C:\\Users\\Matt\\AppData\\Local\\Microsoft\\MEDV\\v2\\ and all files therein should have Read and Write permissions.</span></span>

### <span data-ttu-id="74800-262">事件 ID 9002</span><span class="sxs-lookup"><span data-stu-id="74800-262">Event ID 9002</span></span>

<span data-ttu-id="74800-263">檔案許可權錯誤。</span><span class="sxs-lookup"><span data-stu-id="74800-263">File Permission Error.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="74800-264">描述</span><span class="sxs-lookup"><span data-stu-id="74800-264">Description</span></span>**  
<span data-ttu-id="74800-265">使用者無權存取開啟或建立要寫入的 MED-V 印表機檔案所需的資料夾。</span><span class="sxs-lookup"><span data-stu-id="74800-265">The end user is not authorized to access the folder required to open or create the MED-V printer file for writing.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="74800-266">解決方案</span><span class="sxs-lookup"><span data-stu-id="74800-266">Solution</span></span>**  
<span data-ttu-id="74800-267">確定可存取 User\\AppData\\ 路徑，且使用者有權讀取及寫入該路徑。</span><span class="sxs-lookup"><span data-stu-id="74800-267">Ensure that the User\\AppData\\ path can be accessed, and that the user has permission to read and write to it.</span></span> <span data-ttu-id="74800-268">例如，如果使用者是「Matt」，則路徑 C:\\Users\\Matt\\AppData\\ 及其中的所有檔案都應該有讀取和寫入權限。</span><span class="sxs-lookup"><span data-stu-id="74800-268">For example, if the user is "Matt", the path C:\\Users\\Matt\\AppData\\ and all files therein should have Read and Write permissions.</span></span> <span data-ttu-id="74800-269">如果它存在，則路徑 C:\\Users\\Matt\\AppData\\Local\\Microsoft\\MEDV\\v2\\ 及其中的所有檔案，都應該擁有讀取和寫入權限。</span><span class="sxs-lookup"><span data-stu-id="74800-269">And if it exists, the path C:\\Users\\Matt\\AppData\\Local\\Microsoft\\MEDV\\v2\\ and all files therein should have Read and Write permissions.</span></span>

### <span data-ttu-id="74800-270">事件 ID 9004</span><span class="sxs-lookup"><span data-stu-id="74800-270">Event ID 9004</span></span>

<span data-ttu-id="74800-271">無法建立儲存 MEDV 印表機檔案的路徑。</span><span class="sxs-lookup"><span data-stu-id="74800-271">Could not create path for storing MEDV printer files.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="74800-272">描述</span><span class="sxs-lookup"><span data-stu-id="74800-272">Description</span></span>**  
<span data-ttu-id="74800-273">印表機重新導向服務無法存取檔案，或無法建立儲存印表機資訊所需的目錄。</span><span class="sxs-lookup"><span data-stu-id="74800-273">The printer redirection service could not access files or create directories required for storing the printer information.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="74800-274">解決方案</span><span class="sxs-lookup"><span data-stu-id="74800-274">Solution</span></span>**  
<span data-ttu-id="74800-275">確認您可以存取 User\\AppData\\ 路徑，以及使用者有權讀取及寫入該路徑。</span><span class="sxs-lookup"><span data-stu-id="74800-275">Verify that the User\\AppData\\ path can be accessed and that the user has permission to read and write to it.</span></span> <span data-ttu-id="74800-276">例如，如果使用者是「Matt」，則路徑 C:\\Users\\Matt\\AppData\\ 及其中的所有檔案都應該有讀取和寫入權限。</span><span class="sxs-lookup"><span data-stu-id="74800-276">For example, if the user is "Matt", the path C:\\Users\\Matt\\AppData\\ and all files therein should have Read and Write permissions.</span></span> <span data-ttu-id="74800-277">如果它存在，則路徑 C:\\Users\\Matt\\AppData\\Local\\Microsoft\\MEDV\\v2\\ 及其中的所有檔案，都應該擁有讀取和寫入權限。</span><span class="sxs-lookup"><span data-stu-id="74800-277">And if it exists, the path C:\\Users\\Matt\\AppData\\Local\\Microsoft\\MEDV\\v2\\ and all files therein should have Read and Write permissions.</span></span>

### <span data-ttu-id="74800-278">事件 ID 9005</span><span class="sxs-lookup"><span data-stu-id="74800-278">Event ID 9005</span></span>

<span data-ttu-id="74800-279">無法從配置取得 VM 名稱;無法啟動來賓安裝程式。</span><span class="sxs-lookup"><span data-stu-id="74800-279">Couldn’t get VM name from configuration; cannot launch guest installer.</span></span> <span data-ttu-id="74800-280">無法更新 MED-V-未偵測到主機網路。</span><span class="sxs-lookup"><span data-stu-id="74800-280">Cannot update MED-V – No host network detected.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="74800-281">描述</span><span class="sxs-lookup"><span data-stu-id="74800-281">Description</span></span>**  
<span data-ttu-id="74800-282">印表機重新導向服務無法從 MED-V 設定取得 MED-V 工作區名稱，而且無法通知 Windows Virtual 電腦在 MED-V 來賓上啟動安裝程式。</span><span class="sxs-lookup"><span data-stu-id="74800-282">The printer redirection service was not able to obtain the MED-V workspace name from the MED-V configuration and cannot inform Windows Virtual PC to start the installer on the MED-V guest.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="74800-283">解決方案</span><span class="sxs-lookup"><span data-stu-id="74800-283">Solution</span></span>**  
<span data-ttu-id="74800-284">確定 MED-V 工作區名稱已設定，且與 C:\\Users\\ &lt; *使用者* &gt; \\Virtual 電腦目錄中的虛擬電腦名稱稱相符。</span><span class="sxs-lookup"><span data-stu-id="74800-284">Ensure that the MED-V workspace name is set and that it matches a virtual machine name in the C:\\Users\\&lt;*user*&gt;\\Virtual Machines directory.</span></span> <span data-ttu-id="74800-285">MED-V 工作區名稱位於 HKLM\\SOFTWARE\\Microsoft\\Medv\\v2\\VM\\Name。</span><span class="sxs-lookup"><span data-stu-id="74800-285">The MED-V workspace name is located at HKLM\\SOFTWARE\\Microsoft\\Medv\\v2\\VM\\Name.</span></span>

<span data-ttu-id="74800-286">例如，如果使用者是 "Matt"，而工作區名稱是 "mattsworkspace"，HKLM\\SOFTWARE\\Microsoft\\Medv\\v2\\VM\\Name 的值應該是 "mattsworkspace"，且應該有一個名為 C:\\Users\\Matt\\Virtual Machines\\mattsworkspace.vcmx. 的檔案。</span><span class="sxs-lookup"><span data-stu-id="74800-286">For example, if the user is "Matt" and the workspace name is "mattsworkspace", the value of HKLM\\SOFTWARE\\Microsoft\\Medv\\v2\\VM\\Name should be "mattsworkspace" and there should be a file that is named C:\\Users\\Matt\\Virtual Machines\\mattsworkspace.vcmx.</span></span>

### <span data-ttu-id="74800-287">應用程式發佈</span><span class="sxs-lookup"><span data-stu-id="74800-287">Application Publishing</span></span>

### <span data-ttu-id="74800-288">事件 ID 10015</span><span class="sxs-lookup"><span data-stu-id="74800-288">Event ID 10015</span></span>

<span data-ttu-id="74800-289">協調程式處理期間發生檔案系統錯誤。</span><span class="sxs-lookup"><span data-stu-id="74800-289">A file system error occurred during the reconcile process.</span></span> <span data-ttu-id="74800-290">[協調] 處理常式不會處理 &lt; *檔案名，* &gt; 但會繼續處理任何其他變更。</span><span class="sxs-lookup"><span data-stu-id="74800-290">The reconcile process will not process the file &lt;*filename*&gt; but will continue to process any other changes.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="74800-291">描述</span><span class="sxs-lookup"><span data-stu-id="74800-291">Description</span></span>**  
<span data-ttu-id="74800-292">在建立或刪除快捷方式時，發生未授權的存取或 i/o 錯誤。</span><span class="sxs-lookup"><span data-stu-id="74800-292">An unauthorized access or I/O error occurred when a shortcut was being created or deleted.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="74800-293">解決方案</span><span class="sxs-lookup"><span data-stu-id="74800-293">Solution</span></span>**  
<span data-ttu-id="74800-294">檢查檔案路徑是否可存取，以及使用者是否擁有建立或刪除指定檔案的許可權。</span><span class="sxs-lookup"><span data-stu-id="74800-294">Check that the file path can be accessed and that the user has permissions to create or delete the specified file.</span></span>

### <span data-ttu-id="74800-295">事件 ID 10021</span><span class="sxs-lookup"><span data-stu-id="74800-295">Event ID 10021</span></span>

<span data-ttu-id="74800-296">檔案 &lt; 的錯誤*\ _information*檔案作業 &gt; &lt; *操作 \ _name*檔案 &gt; &lt; *檔案名*上 &gt; 。</span><span class="sxs-lookup"><span data-stu-id="74800-296">Error &lt;*error\_information*&gt; for file operation &lt;*operation\_name*&gt; on file &lt;*filename*&gt;.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="74800-297">描述</span><span class="sxs-lookup"><span data-stu-id="74800-297">Description</span></span>**  
<span data-ttu-id="74800-298">在建立或刪除快捷方式時，發生未授權的存取或 i/o 錯誤。</span><span class="sxs-lookup"><span data-stu-id="74800-298">An unauthorized access or I/O error occurred when a shortcut was being created or deleted.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="74800-299">解決方案</span><span class="sxs-lookup"><span data-stu-id="74800-299">Solution</span></span>**  
<span data-ttu-id="74800-300">檢查檔案路徑是否可存取，以及使用者是否擁有建立或刪除指定檔案的許可權。</span><span class="sxs-lookup"><span data-stu-id="74800-300">Check that the file path can be accessed and that the user has permissions to create or delete the specified file.</span></span>

### <span data-ttu-id="74800-301">來賓修補</span><span class="sxs-lookup"><span data-stu-id="74800-301">Guest Patching</span></span>

### <span data-ttu-id="74800-302">事件 ID 11001</span><span class="sxs-lookup"><span data-stu-id="74800-302">Event ID 11001</span></span>

<span data-ttu-id="74800-303">來賓喚醒任務使用方式訊息。</span><span class="sxs-lookup"><span data-stu-id="74800-303">Guest wakeup task usage message.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="74800-304">描述</span><span class="sxs-lookup"><span data-stu-id="74800-304">Description</span></span>**  
<span data-ttu-id="74800-305">使用/GuestWakeup 選項的 MedvHost.exe 無法正確執行，或命令格式不正確。</span><span class="sxs-lookup"><span data-stu-id="74800-305">MedvHost.exe with the /GuestWakeup option was executed incorrectly, or the command is formatted incorrectly.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="74800-306">解決方案</span><span class="sxs-lookup"><span data-stu-id="74800-306">Solution</span></span>**  
<span data-ttu-id="74800-307">確定命令是以下列格式執行：</span><span class="sxs-lookup"><span data-stu-id="74800-307">Ensure that the command is executed with the following format:</span></span>

<span data-ttu-id="74800-308">Medvhost.exe/GuestWakeup/d： &lt; *duration \ _in \ _minutes* &gt; /v：「 &lt; *工作區 \ _name*」 &gt; 位置</span><span class="sxs-lookup"><span data-stu-id="74800-308">Medvhost.exe /GuestWakeup /d:&lt; *duration\_in\_minutes*&gt; /v:”&lt; *workspace\_name*&gt;” where</span></span>

<span data-ttu-id="74800-309">&lt;*duration \ _in \ _minutes* &gt;虛擬機器應保持在喚醒狀態的分鐘數（預設值為240）和</span><span class="sxs-lookup"><span data-stu-id="74800-309">&lt;*duration\_in\_minutes*&gt; is the number of minutes that the virtual machine should stay awake (default is 240) and</span></span>

<span data-ttu-id="74800-310">&lt;*工作區 \ _name* &gt;是應喚醒的虛擬機器名稱。</span><span class="sxs-lookup"><span data-stu-id="74800-310">&lt;*workspace\_name*&gt; is the name of the virtual machine that should be awakened.</span></span>

### <span data-ttu-id="74800-311">事件 ID 11002</span><span class="sxs-lookup"><span data-stu-id="74800-311">Event ID 11002</span></span>

<span data-ttu-id="74800-312">無法更新 MED-V-未偵測到主機網路。</span><span class="sxs-lookup"><span data-stu-id="74800-312">Cannot update MED-V – No host network detected.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="74800-313">描述</span><span class="sxs-lookup"><span data-stu-id="74800-313">Description</span></span>**  
<span data-ttu-id="74800-314">無法完成來賓修補，因為沒有探測到主機網路連線。</span><span class="sxs-lookup"><span data-stu-id="74800-314">Guest patching could not finish because no host network connection was detected.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="74800-315">解決方案</span><span class="sxs-lookup"><span data-stu-id="74800-315">Solution</span></span>**  
<span data-ttu-id="74800-316">在執行來賓修補程式之前，請先將 MED-V 主機連線至使用中的網路連線。</span><span class="sxs-lookup"><span data-stu-id="74800-316">Connect the MED-V host to an active network connection before you run guest patching.</span></span>

### <span data-ttu-id="74800-317">事件 ID 11003</span><span class="sxs-lookup"><span data-stu-id="74800-317">Event ID 11003</span></span>

<span data-ttu-id="74800-318">無法更新 MED-V-未在 A/C powerFailed 上執行的主機，無法建立管道伺服器。</span><span class="sxs-lookup"><span data-stu-id="74800-318">Cannot update MED-V – Host not running on A/C powerFailed to create pipe server.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="74800-319">描述</span><span class="sxs-lookup"><span data-stu-id="74800-319">Description</span></span>**  
<span data-ttu-id="74800-320">無法完成來賓修補，因為主機看起來好像是在電池電源執行，而不是從電源線執行。</span><span class="sxs-lookup"><span data-stu-id="74800-320">Guest patching could not finish because the host appears to be running on battery power instead of from a power cord.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="74800-321">解決方案</span><span class="sxs-lookup"><span data-stu-id="74800-321">Solution</span></span>**  
<span data-ttu-id="74800-322">在執行來賓修補之前，請先將主機電腦連接至電源線。</span><span class="sxs-lookup"><span data-stu-id="74800-322">Connect the host computer to a power cord before you run guest patching.</span></span>

### <span data-ttu-id="74800-323">用戶端 UX</span><span class="sxs-lookup"><span data-stu-id="74800-323">Client UX</span></span>

### <span data-ttu-id="74800-324">事件 ID 14003</span><span class="sxs-lookup"><span data-stu-id="74800-324">Event ID 14003</span></span>

<span data-ttu-id="74800-325">下列送紙器狀態訊息太長且無法顯示： &lt; *紙盒 \ _status \ _message*&gt;</span><span class="sxs-lookup"><span data-stu-id="74800-325">The following tray status message was too long and could not be displayed: &lt;*tray\_status\_message*&gt;</span></span>

<a href="" id="description"></a>**<span data-ttu-id="74800-326">描述</span><span class="sxs-lookup"><span data-stu-id="74800-326">Description</span></span>**  
<span data-ttu-id="74800-327">MED-V 針對工作列工具提示或氣球訊息所建立的意外字串太長。</span><span class="sxs-lookup"><span data-stu-id="74800-327">MED-V created an unanticipated string that was too long for the tray tooltip or balloon message.</span></span> <span data-ttu-id="74800-328">因此，顯示的郵件已被截斷。</span><span class="sxs-lookup"><span data-stu-id="74800-328">As a result, the displayed message was truncated.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="74800-329">解決方案</span><span class="sxs-lookup"><span data-stu-id="74800-329">Solution</span></span>**  
<span data-ttu-id="74800-330">在 MED-V 隨機建立工具提示文字時，可能會發生這種不常見的錯誤。</span><span class="sxs-lookup"><span data-stu-id="74800-330">This is a rare error that can occur when MED-V is randomly creating the tooltip text.</span></span> <span data-ttu-id="74800-331">沒有解決方法。</span><span class="sxs-lookup"><span data-stu-id="74800-331">There is no solution.</span></span>

### <span data-ttu-id="74800-332">事件 ID 14004</span><span class="sxs-lookup"><span data-stu-id="74800-332">Event ID 14004</span></span>

<span data-ttu-id="74800-333">由於未處理的例外狀況，MED-V 已停止。</span><span class="sxs-lookup"><span data-stu-id="74800-333">MED-V stopped due to an unhandled exception.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="74800-334">描述</span><span class="sxs-lookup"><span data-stu-id="74800-334">Description</span></span>**  
<span data-ttu-id="74800-335">未處理的例外導致 MED-V 停止意外停止。</span><span class="sxs-lookup"><span data-stu-id="74800-335">An unhandled exception caused MED-V to stop unexpectedly.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="74800-336">解決方案</span><span class="sxs-lookup"><span data-stu-id="74800-336">Solution</span></span>**  
<span data-ttu-id="74800-337">重新開機 MED-V。</span><span class="sxs-lookup"><span data-stu-id="74800-337">Restart MED-V.</span></span>

### <span data-ttu-id="74800-338">事件 ID 14005</span><span class="sxs-lookup"><span data-stu-id="74800-338">Event ID 14005</span></span>

<span data-ttu-id="74800-339">伺服器試圖建立 mutex，但已經存在。</span><span class="sxs-lookup"><span data-stu-id="74800-339">Server attempted to create mutex but it already existed.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="74800-340">描述</span><span class="sxs-lookup"><span data-stu-id="74800-340">Description</span></span>**  
<span data-ttu-id="74800-341">MedvHost.exe 的第二個實例停滯在記憶體中。</span><span class="sxs-lookup"><span data-stu-id="74800-341">A second instance of MedvHost.exe is stuck in memory.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="74800-342">解決方案</span><span class="sxs-lookup"><span data-stu-id="74800-342">Solution</span></span>**  
<span data-ttu-id="74800-343">開啟 TaskManager 並結束所有 MedvHost.exe 處理常式。</span><span class="sxs-lookup"><span data-stu-id="74800-343">Open TaskManager and end all MedvHost.exe processes.</span></span>

### <span data-ttu-id="74800-344">事件 ID 14006</span><span class="sxs-lookup"><span data-stu-id="74800-344">Event ID 14006</span></span>

<span data-ttu-id="74800-345">修改或刪除註冊表值 registry 時發生錯誤 &lt; *\ _value* &gt; 。</span><span class="sxs-lookup"><span data-stu-id="74800-345">Error modifying or deleting registry value &lt;*registry\_value*&gt;.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="74800-346">描述</span><span class="sxs-lookup"><span data-stu-id="74800-346">Description</span></span>**  
<span data-ttu-id="74800-347">MED-V 無法在註冊表中修改指定的專案。</span><span class="sxs-lookup"><span data-stu-id="74800-347">MED-V is unable to modify the specified entry in the registry.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="74800-348">解決方案</span><span class="sxs-lookup"><span data-stu-id="74800-348">Solution</span></span>**  
<span data-ttu-id="74800-349">確定您是使用系統管理認證來安裝或卸載 MED-V。</span><span class="sxs-lookup"><span data-stu-id="74800-349">Ensure that you install or uninstall MED-V with administrative credentials.</span></span>

### <span data-ttu-id="74800-350">事件 ID 14007</span><span class="sxs-lookup"><span data-stu-id="74800-350">Event ID 14007</span></span>

<span data-ttu-id="74800-351">指定的檔案（ &lt; *filename* &gt; ）無效。</span><span class="sxs-lookup"><span data-stu-id="74800-351">The file specified (&lt;*filename*&gt;) is not valid.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="74800-352">描述</span><span class="sxs-lookup"><span data-stu-id="74800-352">Description</span></span>**  
<span data-ttu-id="74800-353">在安裝或卸載期間，已將損毀的臨時檔案傳遞到 MED-V 主機。</span><span class="sxs-lookup"><span data-stu-id="74800-353">During install or uninstall, a corrupted temp file was passed to MED-V host.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="74800-354">解決方案</span><span class="sxs-lookup"><span data-stu-id="74800-354">Solution</span></span>**  
<span data-ttu-id="74800-355">刪除 Temp 資料夾中的所有檔案，然後重新安裝或卸載 MED-V。</span><span class="sxs-lookup"><span data-stu-id="74800-355">Delete all files in the Temp folder and reinstall or uninstall MED-V.</span></span>

### <span data-ttu-id="74800-356">事件 ID 14008</span><span class="sxs-lookup"><span data-stu-id="74800-356">Event ID 14008</span></span>

<span data-ttu-id="74800-357">找不到檔案： &lt; *檔案名* &gt; 。</span><span class="sxs-lookup"><span data-stu-id="74800-357">File not found: &lt;*filename*&gt;.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="74800-358">描述</span><span class="sxs-lookup"><span data-stu-id="74800-358">Description</span></span>**  
<span data-ttu-id="74800-359">在安裝或卸載期間，找不到所需 temp 檔案的路徑。</span><span class="sxs-lookup"><span data-stu-id="74800-359">During install or uninstall, a path of a required temp file was not found.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="74800-360">解決方案</span><span class="sxs-lookup"><span data-stu-id="74800-360">Solution</span></span>**  
<span data-ttu-id="74800-361">刪除 Temp 資料夾中的所有檔案，然後重新安裝或卸載 MED-V。</span><span class="sxs-lookup"><span data-stu-id="74800-361">Delete all files in the Temp folder and reinstall or uninstall MED-V.</span></span>

### <span data-ttu-id="74800-362">事件 ID 14009</span><span class="sxs-lookup"><span data-stu-id="74800-362">Event ID 14009</span></span>

<span data-ttu-id="74800-363">無法讀取參數檔 &lt; *檔案名* &gt; 。</span><span class="sxs-lookup"><span data-stu-id="74800-363">Unable to read parameter file &lt;*filename*&gt;.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="74800-364">描述</span><span class="sxs-lookup"><span data-stu-id="74800-364">Description</span></span>**  
<span data-ttu-id="74800-365">在安裝或卸載程式期間，MED-V 無法讀取 temp 檔案。</span><span class="sxs-lookup"><span data-stu-id="74800-365">During the install or uninstall process, MED-V was unable to read a temp file.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="74800-366">解決方案</span><span class="sxs-lookup"><span data-stu-id="74800-366">Solution</span></span>**  
<span data-ttu-id="74800-367">刪除 Temp 資料夾中的所有檔案，然後重新安裝或卸載 MED-V。</span><span class="sxs-lookup"><span data-stu-id="74800-367">Delete all files in the Temp folder and reinstall or uninstall MED-V.</span></span> <span data-ttu-id="74800-368">此外，請確認使用者擁有 Temp 資料夾的必要權利和許可權。</span><span class="sxs-lookup"><span data-stu-id="74800-368">In addition, verify that the user has the necessary rights and permissions to the Temp folder.</span></span>

### <span data-ttu-id="74800-369">事件 ID 14010</span><span class="sxs-lookup"><span data-stu-id="74800-369">Event ID 14010</span></span>

<span data-ttu-id="74800-370">反序列化參數 &lt; *檔案名* &gt; 的錯誤。</span><span class="sxs-lookup"><span data-stu-id="74800-370">Error deserializing parameter file &lt;*filename*&gt;.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="74800-371">描述</span><span class="sxs-lookup"><span data-stu-id="74800-371">Description</span></span>**  
<span data-ttu-id="74800-372">在安裝或卸載程式期間，MED-V 遇到損毀檔案。</span><span class="sxs-lookup"><span data-stu-id="74800-372">During the install or uninstall process, MED-V encountered a corrupted temp file.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="74800-373">解決方案</span><span class="sxs-lookup"><span data-stu-id="74800-373">Solution</span></span>**  
<span data-ttu-id="74800-374">刪除 Temp 資料夾中的所有檔案，然後重新安裝或卸載 MED-V。</span><span class="sxs-lookup"><span data-stu-id="74800-374">Delete all files in the Temp folder and reinstall or uninstall MED-V.</span></span> <span data-ttu-id="74800-375">此外，請確認使用者擁有 Temp 資料夾的必要權利和許可權。</span><span class="sxs-lookup"><span data-stu-id="74800-375">In addition, verify that the user has the necessary rights and permissions to the Temp folder.</span></span>

### <span data-ttu-id="74800-376">事件 ID 14011</span><span class="sxs-lookup"><span data-stu-id="74800-376">Event ID 14011</span></span>

<span data-ttu-id="74800-377">反序列化參數檔案名時產生意外 &lt; *filename* &gt; 的錯誤。</span><span class="sxs-lookup"><span data-stu-id="74800-377">Unexpected error deserializing parameter file &lt;*filename*&gt;.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="74800-378">描述</span><span class="sxs-lookup"><span data-stu-id="74800-378">Description</span></span>**  
<span data-ttu-id="74800-379">在安裝或卸載程式期間，MED-V 遇到損毀檔案。</span><span class="sxs-lookup"><span data-stu-id="74800-379">During the install or uninstall process, MED-V encountered a corrupted temp file.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="74800-380">解決方案</span><span class="sxs-lookup"><span data-stu-id="74800-380">Solution</span></span>**  
<span data-ttu-id="74800-381">刪除 Temp 資料夾中的所有檔案，然後重新安裝或卸載 MED-V。</span><span class="sxs-lookup"><span data-stu-id="74800-381">Delete all files in the Temp folder and reinstall or uninstall MED-V.</span></span> <span data-ttu-id="74800-382">此外，請確認使用者擁有 Temp 資料夾的必要權利和許可權。</span><span class="sxs-lookup"><span data-stu-id="74800-382">In addition, verify that the user has the necessary rights and permissions to the Temp folder.</span></span>

### <span data-ttu-id="74800-383">事件 ID 14012</span><span class="sxs-lookup"><span data-stu-id="74800-383">Event ID 14012</span></span>

<span data-ttu-id="74800-384">[資料夾 &lt; \*資料夾 \* ] 的設定權力為 [_name &gt; 使用者使用者 &lt; *名稱*] 時，發生意外 &gt; 的錯誤。</span><span class="sxs-lookup"><span data-stu-id="74800-384">Unexpected error when settings rights on folder &lt;*folder\_name*&gt; for user &lt;*username*&gt;.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="74800-385">描述</span><span class="sxs-lookup"><span data-stu-id="74800-385">Description</span></span>**  
<span data-ttu-id="74800-386">當 MED-V 無法在安裝期間設定特定資料夾的許可權和許可權時，就會發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="74800-386">An error occurs when MED-V is unable to set rights and permissions on certain folders during installation.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="74800-387">解決方案</span><span class="sxs-lookup"><span data-stu-id="74800-387">Solution</span></span>**  
<span data-ttu-id="74800-388">檢查下列資料夾的系統管理員許可權：</span><span class="sxs-lookup"><span data-stu-id="74800-388">Check the administrator rights to the following folders:</span></span>

<span data-ttu-id="74800-389">@"%ProgramData%\\Microsoft\\Medv\\AllUsers"</span><span class="sxs-lookup"><span data-stu-id="74800-389">@"%ProgramData%\\Microsoft\\Medv\\AllUsers"</span></span>

<span data-ttu-id="74800-390">@"%ProgramData%\\Microsoft\\Medv\\MedvLock"</span><span class="sxs-lookup"><span data-stu-id="74800-390">@"%ProgramData%\\Microsoft\\Medv\\MedvLock"</span></span>

<span data-ttu-id="74800-391">@"%ProgramData%\\Microsoft\\Medv\\Monitoring"</span><span class="sxs-lookup"><span data-stu-id="74800-391">@"%ProgramData%\\Microsoft\\Medv\\Monitoring"</span></span>

### <span data-ttu-id="74800-392">事件 ID 14013</span><span class="sxs-lookup"><span data-stu-id="74800-392">Event ID 14013</span></span>

<span data-ttu-id="74800-393">建立鎖定檔案時發生意外的錯誤。</span><span class="sxs-lookup"><span data-stu-id="74800-393">Unexpected error when creating lock file.</span></span>

<a href="" id="description"></a>**<span data-ttu-id="74800-394">描述</span><span class="sxs-lookup"><span data-stu-id="74800-394">Description</span></span>**  
<span data-ttu-id="74800-395">當 MED-V 無法在安裝期間在 @ "%ProgramData%\\Microsoft\\Medv\\MedvLock" 資料夾中建立檔案時，就會發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="74800-395">An error occurs when MED-V is unable to create a file in the @"%ProgramData%\\Microsoft\\Medv\\MedvLock" folder during installation.</span></span>

<a href="" id="solution"></a>**<span data-ttu-id="74800-396">解決方案</span><span class="sxs-lookup"><span data-stu-id="74800-396">Solution</span></span>**  
<span data-ttu-id="74800-397">檢查 [MedvLock] 資料夾的系統管理員許可權。</span><span class="sxs-lookup"><span data-stu-id="74800-397">Check the administrator rights to the MedvLock folder.</span></span>

## <span data-ttu-id="74800-398">相關主題</span><span class="sxs-lookup"><span data-stu-id="74800-398">Related topics</span></span>


[<span data-ttu-id="74800-399">疑難排解 MED-V</span><span class="sxs-lookup"><span data-stu-id="74800-399">Troubleshooting MED-V</span></span>](troubleshooting-med-vmedv2.md)

 

 





