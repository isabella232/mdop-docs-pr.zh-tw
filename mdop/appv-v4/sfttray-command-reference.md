---
title: SFTTRAY 命令參考資料
description: SFTTRAY 命令參考資料
author: dansimp
ms.assetid: 6fa3a939-b047-4d6c-bd1d-dfb93e065eb2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 45a664b91ff7edd5f8536f035417cc3b0f52d7ca
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800802"
---
# <span data-ttu-id="7cbee-103">SFTTRAY 命令參考資料</span><span class="sxs-lookup"><span data-stu-id="7cbee-103">SFTTRAY Command Reference</span></span>


<span data-ttu-id="7cbee-104">Microsoft Application Virtualization （App-v）用戶端工作列應用程式 sfttray.exe，是使用者在正常使用期間將與其互動的 App V 用戶端主要使用者介面元素。</span><span class="sxs-lookup"><span data-stu-id="7cbee-104">The Microsoft Application Virtualization (App-V) Client Tray application, sfttray.exe, is the main user interface element of the App-V Client that users will interact with during normal use.</span></span> <span data-ttu-id="7cbee-105">這個程式會控制資料流程並開始所有的虛擬應用程式，並以滑鼠右鍵按一下顯示在通知區域中的圖示，以顯示用戶端函數的功能表，以進行存取。</span><span class="sxs-lookup"><span data-stu-id="7cbee-105">This program controls the streaming and starting of all virtual applications and is accessed by right-clicking the icon displayed in the notification area to display the menu of client functions.</span></span> <span data-ttu-id="7cbee-106">此功能表可讓使用者載入應用程式、啟動發佈重新整理、取消要求，或將用戶端變更為離線模式。</span><span class="sxs-lookup"><span data-stu-id="7cbee-106">The menu enables the user to load applications, start a publishing refresh, cancel a request, or change the client to offline mode.</span></span> <span data-ttu-id="7cbee-107">使用者也可以按一下 [結束]，關閉應用程式虛擬化用戶端工作列應用程式和所有**作用中的**應用程式。</span><span class="sxs-lookup"><span data-stu-id="7cbee-107">The user can also close the Application Virtualization Client Tray application and all active applications by clicking **Exit**.</span></span>

<span data-ttu-id="7cbee-108">雖然您可以使用 SFTTRAY 命令來控制此行為，但是預設會在虛擬應用程式啟動時顯示圖示。</span><span class="sxs-lookup"><span data-stu-id="7cbee-108">By default, the icon is displayed whenever a virtual application is started, although you can control this behavior by using SFTTRAY commands.</span></span> <span data-ttu-id="7cbee-109">應用程式虛擬化用戶端工作列應用程式也會針對每個已啟動的應用程式顯示進度列，以及有關作用中應用程式的狀態訊息。</span><span class="sxs-lookup"><span data-stu-id="7cbee-109">The Application Virtualization Client Tray application also displays a progress bar for each application that is started, as well as status messages about active applications.</span></span> <span data-ttu-id="7cbee-110">按一下進度列會顯示一則訊息，讓您取消載入或啟動應用程式。</span><span class="sxs-lookup"><span data-stu-id="7cbee-110">Clicking the progress bar displays a message that allows you to cancel the loading or starting of an application.</span></span>

## <span data-ttu-id="7cbee-111">SFTTRAY 命令</span><span class="sxs-lookup"><span data-stu-id="7cbee-111">SFTTRAY Commands</span></span>


<span data-ttu-id="7cbee-112">您可以從命令視窗執行下列命令，以顯示命令與命令列開關的清單。</span><span class="sxs-lookup"><span data-stu-id="7cbee-112">The list of commands and command-line switches can be displayed by running the following command from a command window.</span></span>

**<span data-ttu-id="7cbee-113">注意</span><span class="sxs-lookup"><span data-stu-id="7cbee-113">Note</span></span>**  
<span data-ttu-id="7cbee-114">每個使用者內容只有一個應用程式虛擬化用戶端工作列實例，所以如果您開始新的 SFTTRAY 命令，就會將它傳遞到已在執行中的程式。</span><span class="sxs-lookup"><span data-stu-id="7cbee-114">There is only one Application Virtualization Client Tray instance for each user context, so if you start a new SFTTRAY command, it will be passed to the program that is already running.</span></span>



`Sfttray.exe /?`

### <span data-ttu-id="7cbee-115">命令用法</span><span class="sxs-lookup"><span data-stu-id="7cbee-115">Command Usage</span></span>

`Sfttray.exe [/HIDE | /SHOW]`

`Sfttray.exe [/HIDE | /SHOW] [/QUIET] [/EXE alternate-exe] /LAUNCH app [args]`

`Sfttray.exe [/HIDE | /SHOW] [/QUIET] /LOAD app [/SFTFILE sft]`

`Sfttray.exe [/HIDE | /SHOW] [/QUIET] /LOADALL`

`Sfttray.exe [/HIDE | /SHOW] [/QUIET] /REFRESHALL`

`Sfttray.exe [/HIDE | /SHOW] [/QUIET] /LAUNCHRESULT <UNIQUE ID>  /LAUNCH app [args]`

`Sfttray.exe /EXIT`

### <span data-ttu-id="7cbee-116">命令列參數</span><span class="sxs-lookup"><span data-stu-id="7cbee-116">Command-Line Switches</span></span>

<span data-ttu-id="7cbee-117">下表說明 SFTTRAY 命令列參數。</span><span class="sxs-lookup"><span data-stu-id="7cbee-117">The SFTTRAY command-line switches are described in the following table.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="7cbee-118">切換</span><span class="sxs-lookup"><span data-stu-id="7cbee-118">Switch</span></span></th>
<th align="left"><span data-ttu-id="7cbee-119">描述</span><span class="sxs-lookup"><span data-stu-id="7cbee-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7cbee-120">/HIDE</span><span class="sxs-lookup"><span data-stu-id="7cbee-120">/HIDE</span></span></p></td>
<td align="left"><p><span data-ttu-id="7cbee-121">隱藏 Windows 通知區域中的 [SFTTRAY] 圖示。</span><span class="sxs-lookup"><span data-stu-id="7cbee-121">Hides the SFTTRAY icon in the Windows notification area.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="7cbee-122">/SHOW</span><span class="sxs-lookup"><span data-stu-id="7cbee-122">/SHOW</span></span></p></td>
<td align="left"><p><span data-ttu-id="7cbee-123">在 Windows 通知區域中顯示 [SFTTRAY] 圖示。</span><span class="sxs-lookup"><span data-stu-id="7cbee-123">Displays the SFTTRAY icon in the Windows notification area.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7cbee-124">/QUIET</span><span class="sxs-lookup"><span data-stu-id="7cbee-124">/QUIET</span></span></p></td>
<td align="left"><p><span data-ttu-id="7cbee-125">支援無人參與的使用方式，避免錯誤顯示需要使用者確認的訊息框。</span><span class="sxs-lookup"><span data-stu-id="7cbee-125">Supports unattended usage by preventing errors from displaying message boxes that require user acknowledgement.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="7cbee-126">/EXE &lt; 替代 EXE&gt;</span><span class="sxs-lookup"><span data-stu-id="7cbee-126">/EXE &lt;alternate-exe&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="7cbee-127">與/LAUNCH 搭配使用，以指定在啟動虛擬應用程式以取代 OSD 中指定的目標檔案時，會在虛擬環境中啟動一個可執行程式。</span><span class="sxs-lookup"><span data-stu-id="7cbee-127">Used with /LAUNCH to specify that an executable program is to be started in the virtual environment when a virtual application is started in place of the target file specified in the OSD.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="7cbee-128">注意</span><span class="sxs-lookup"><span data-stu-id="7cbee-128">Note</span></span></strong><br/><p><span data-ttu-id="7cbee-129">例如，使用「SFTTRAY.EXE/EXE REGEDIT.EXE/LAUNCH app」， &lt; &gt; 讓您檢查應用程式在其中執行之虛擬環境的註冊表。</span><span class="sxs-lookup"><span data-stu-id="7cbee-129">For example, use “SFTTRAY.EXE /EXE REGEDIT.EXE /LAUNCH &lt;app&gt;” to enable you to examine the registry of the virtual environment in which the application is running.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7cbee-130">/LAUNCH &lt; 應用程式 &gt; [ &lt; 參數 &gt; ]</span><span class="sxs-lookup"><span data-stu-id="7cbee-130">/LAUNCH &lt;app&gt; [&lt;args&gt;]</span></span></p></td>
<td align="left"><p><span data-ttu-id="7cbee-131">啟動虛擬應用程式。</span><span class="sxs-lookup"><span data-stu-id="7cbee-131">Starts a virtual application.</span></span> <span data-ttu-id="7cbee-132">指定應用程式的名稱和版本，或是 OSD 檔案的路徑。</span><span class="sxs-lookup"><span data-stu-id="7cbee-132">Specify the name and version of an application or the path to an OSD file.</span></span> <span data-ttu-id="7cbee-133">您也可以將命令列引數傳遞到虛擬應用程式。</span><span class="sxs-lookup"><span data-stu-id="7cbee-133">Optionally, command-line arguments can be passed to the virtual application.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="7cbee-134">注意</span><span class="sxs-lookup"><span data-stu-id="7cbee-134">Note</span></span></strong><br/><p><span data-ttu-id="7cbee-135">使用命令「SFTMIME.EXE/QUERY OBJ：應用程式/SHORT」取得可用虛擬應用程式的名稱和版本清單。</span><span class="sxs-lookup"><span data-stu-id="7cbee-135">Use the command “SFTMIME.EXE /QUERY OBJ:APP /SHORT” to obtain a list of the names and versions of available virtual applications.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="7cbee-136">/LOAD</span><span class="sxs-lookup"><span data-stu-id="7cbee-136">/LOAD</span></span></p></td>
<td align="left"><p><span data-ttu-id="7cbee-137">載入或匯入虛擬應用程式。</span><span class="sxs-lookup"><span data-stu-id="7cbee-137">Loads or imports a virtual application.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7cbee-138">/LOADALL</span><span class="sxs-lookup"><span data-stu-id="7cbee-138">/LOADALL</span></span></p></td>
<td align="left"><p><span data-ttu-id="7cbee-139">將所有應用程式載入到快取中。</span><span class="sxs-lookup"><span data-stu-id="7cbee-139">Loads all applications into cache.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="7cbee-140">/REFRESHALL</span><span class="sxs-lookup"><span data-stu-id="7cbee-140">/REFRESHALL</span></span></p></td>
<td align="left"><p><span data-ttu-id="7cbee-141">針對所有應用程式啟動 [發佈重新整理]。</span><span class="sxs-lookup"><span data-stu-id="7cbee-141">Starts a publishing refresh for all applications.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7cbee-142">/LAUNCHRESULT &lt; 唯一識別碼&gt;</span><span class="sxs-lookup"><span data-stu-id="7cbee-142">/LAUNCHRESULT &lt;UNIQUE ID&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="7cbee-143">將啟動結果代碼傳回啟動 sfttray.exe 的處理常式，方法是使用全域事件，以及根據指定的根名稱（針對唯一識別碼. ¹）的記憶體對應檔案。</span><span class="sxs-lookup"><span data-stu-id="7cbee-143">Returns the launch result code to the process that launches sfttray.exe by using a global event and a memory mapped file that are based on the specified root name for the UNIQUE ID.¹</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="7cbee-144">/SFTFILE &lt; sft&gt;</span><span class="sxs-lookup"><span data-stu-id="7cbee-144">/SFTFILE &lt;sft&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="7cbee-145">與/LOAD 搭配使用的選用開關，可指定應用程式 SFT 檔案的路徑。</span><span class="sxs-lookup"><span data-stu-id="7cbee-145">Optional switch used with /LOAD to specify the path to the application’s SFT file.</span></span> <span data-ttu-id="7cbee-146">如果已指定，就會匯入應用程式，而不是載入。</span><span class="sxs-lookup"><span data-stu-id="7cbee-146">If specified, the application is imported rather than loaded.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7cbee-147">/EXIT</span><span class="sxs-lookup"><span data-stu-id="7cbee-147">/EXIT</span></span></p></td>
<td align="left"><p><span data-ttu-id="7cbee-148">關閉 SFTTRAY 程式及所有作用中的虛擬應用程式，並移除 Windows 通知區域中的圖示。</span><span class="sxs-lookup"><span data-stu-id="7cbee-148">Closes the SFTTRAY program and all active virtual applications and removes the icon from the Windows notification area.</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="7cbee-149">注意</span><span class="sxs-lookup"><span data-stu-id="7cbee-149">Note</span></span>**  
<span data-ttu-id="7cbee-150">¹ */LAUNCHRESULT*命令列參數為啟動 sfttray.exe 的程式提供一種方式，以指定全域事件的根名稱，以及用來將啟動結果程式碼傳回處理常式的記憶體對應檔案。</span><span class="sxs-lookup"><span data-stu-id="7cbee-150">¹ The */LAUNCHRESULT* command line parameter provides a means for the process that launches sfttray.exe to specify the root name for a global event and a memory mapped file that are used to return the launch result code to the process.</span></span> <span data-ttu-id="7cbee-151">唯一識別碼名稱應該以 "SFT-" 開頭，以避免事件名稱在虛擬環境中呼叫啟動程式時得到虛擬化。</span><span class="sxs-lookup"><span data-stu-id="7cbee-151">The unique identifier name should start with “SFT-” to prevent the event name from getting virtualized when the launching process is invoked within a virtual environment.</span></span> <span data-ttu-id="7cbee-152">記憶體對應的區域將為64位大小。</span><span class="sxs-lookup"><span data-stu-id="7cbee-152">The memory mapped region will be 64 bits in size.</span></span>

<span data-ttu-id="7cbee-153">若要使用這個參數，啟動程式會建立一個名稱為 "unique ID-result \ _event" 的事件，該檔案的名稱為「 &lt; &gt; &lt; unique id &gt; -result \ _value」，並選擇性地 &lt; &gt; sfttray.exe 啟動處理 _event 程式，並等待事件發出信號，然後等待事件停止。</span><span class="sxs-lookup"><span data-stu-id="7cbee-153">To use this parameter, the launching process creates an event with the name “&lt;UNIQUE ID&gt;-result\_event”, a memory mapped file with the name “&lt;UNIQUE ID&gt;-result\_value”, and optionally an event with the name “&lt;UNIQUE ID&gt;-shutdown\_event”, and then the launching process launches sfttray.exe and waits on the event to be signaled.</span></span> <span data-ttu-id="7cbee-154">事件「 &lt; UNIQUE ID &gt; -result \ _event」超時之後，啟動程式會從記憶體對應區域中檢索64位傳回碼。</span><span class="sxs-lookup"><span data-stu-id="7cbee-154">After the event “&lt;UNIQUE ID&gt;-result\_event” is signaled, the launching process retrieves the 64-bit return code from the memory mapped region.</span></span>

<span data-ttu-id="7cbee-155">如果 &lt; &gt; 當虛擬應用程式退出時，會出現選擇性事件「唯一識別碼-shutdown \ _event」，sfttray.exe 會開啟併發出事件信號。</span><span class="sxs-lookup"><span data-stu-id="7cbee-155">If the optional event “&lt;UNIQUE ID&gt;-shutdown\_event” exists when the virtual application exits, sfttray.exe opens and signals the event.</span></span> <span data-ttu-id="7cbee-156">啟動程式會在此關閉事件時等待，如果它需要判斷虛擬應用程式何時退出。</span><span class="sxs-lookup"><span data-stu-id="7cbee-156">The launching process waits on this shutdown event if it needs to determine when the virtual application exits.</span></span>











