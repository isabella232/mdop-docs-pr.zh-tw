---
title: 關於 App-V 5.0 SP2
description: 關於 App-V 5.0 SP2
author: dansimp
ms.assetid: 16ca8452-cef2-464e-b4b5-c10d4630fa6a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9a476f3bf273717b5a85a4244c5796f893b0c617
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800729"
---
# <span data-ttu-id="fff17-103">關於 App-V 5.0 SP2</span><span class="sxs-lookup"><span data-stu-id="fff17-103">About App-V 5.0 SP2</span></span>


<span data-ttu-id="fff17-104">App-v 5.0 SP2 提供改良的整合平臺、更具彈性的虛擬化，以及適用于虛擬化應用程式的強大管理功能。</span><span class="sxs-lookup"><span data-stu-id="fff17-104">App-V 5.0SP2 provides an improved integrated platform, more flexible virtualization, and powerful management for virtualized applications.</span></span> <span data-ttu-id="fff17-105">如需詳細資訊，請參閱[app-v 5.0 概覽](https://go.microsoft.com/fwlink/p/?LinkId=325265)（ https://go.microsoft.com/fwlink/?LinkId=325265) 。</span><span class="sxs-lookup"><span data-stu-id="fff17-105">For more information see, [App-V 5.0 Overview](https://go.microsoft.com/fwlink/p/?LinkId=325265) (https://go.microsoft.com/fwlink/?LinkId=325265).</span></span>

## <span data-ttu-id="fff17-106">標準 App V 5.0 SP2 功能中的變更</span><span class="sxs-lookup"><span data-stu-id="fff17-106">Changes in Standard App-V 5.0SP2 Functionality</span></span>


<span data-ttu-id="fff17-107">下列各節包含應用程式 V 5.0 SP2 之標準功能變更的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="fff17-107">The following sections contain information about the changes in standard functionality for App-V 5.0SP2.</span></span>

### <a href="" id="bkmk-sp2-supported-cfg"></a><span data-ttu-id="fff17-108">Windows Server 2012 R2 和 Windows 8.1 的支援</span><span class="sxs-lookup"><span data-stu-id="fff17-108">Support for Windows Server 2012 R2 and Windows 8.1</span></span>

<span data-ttu-id="fff17-109">App-V 5.0 包含 Windows Server 2012 R2 和 Windows 8.1 的支援</span><span class="sxs-lookup"><span data-stu-id="fff17-109">App-V 5.0 includes support for Windows Server 2012 R2 and Windows 8.1</span></span>

### <a href="" id="-------------app-v-5-0-sp2-now-supports-folder-redirection-for-the-user-s-roaming-appdata-directory"></a> <span data-ttu-id="fff17-110">App-V 5.0 SP2 現在支援使用者的漫遊 AppData 目錄的資料夾重新導向</span><span class="sxs-lookup"><span data-stu-id="fff17-110">App-V 5.0SP2 now supports folder redirection for the user’s roaming AppData directory</span></span>

<span data-ttu-id="fff17-111">App V 5.0 SP2 支援漫遊 AppData （% AppData%）資料夾重新導向。</span><span class="sxs-lookup"><span data-stu-id="fff17-111">App-V 5.0SP2 supports roaming AppData (%AppData%) folder redirection.</span></span> <span data-ttu-id="fff17-112">如需詳細資訊，請參閱[規劃在 app-v 中使用資料夾](planning-to-use-folder-redirection-with-app-v.md)重新導向。</span><span class="sxs-lookup"><span data-stu-id="fff17-112">For more information, see the [Planning to Use Folder Redirection with App-V](planning-to-use-folder-redirection-with-app-v.md).</span></span>

### <a href="" id="bkmk-pkg-upgr-pendg-tasks"></a><span data-ttu-id="fff17-113">套件升級改進與擱置中的任務</span><span class="sxs-lookup"><span data-stu-id="fff17-113">Package upgrade improvements and pending tasks</span></span>

<span data-ttu-id="fff17-114">在 App-v 5.0 SP2 中，當發佈更新版本的套件或連線群組時，系統不會再提示您關閉正在執行的虛擬應用程式。</span><span class="sxs-lookup"><span data-stu-id="fff17-114">In App-V 5.0SP2, you are no longer prompted to close a running virtual application when a newer version of the package or connection group is published.</span></span> <span data-ttu-id="fff17-115">如果您嘗試執行相關工作時，封裝或連線群組處於使用中，則會顯示一則訊息，指出該物件已在使用中，且稍後會嘗試該操作。</span><span class="sxs-lookup"><span data-stu-id="fff17-115">If a package or connection group is in use when you try to perform a related task, a message displays to indicate that the object is in use, and that the operation will be attempted at a later time.</span></span>

<span data-ttu-id="fff17-116">根據下列規則，將會執行已置於擱置狀態的工作：</span><span class="sxs-lookup"><span data-stu-id="fff17-116">Tasks that have been placed in a pending state will be performed according to the following rules:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="fff17-117">任務類型</span><span class="sxs-lookup"><span data-stu-id="fff17-117">Task type</span></span></th>
<th align="left"><span data-ttu-id="fff17-118">適用的規則</span><span class="sxs-lookup"><span data-stu-id="fff17-118">Applicable rule</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="fff17-119">以使用者為基礎的工作，例如，將套件發佈給使用者</span><span class="sxs-lookup"><span data-stu-id="fff17-119">User-based task, e.g., publishing a package to a user</span></span></p></td>
<td align="left"><p><span data-ttu-id="fff17-120">暫停的工作將會在使用者登出後執行，然後重新登入。</span><span class="sxs-lookup"><span data-stu-id="fff17-120">The pending task will be performed after the user logs off and then logs back on.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="fff17-121">以全域為基礎的工作，例如，全域啟用連接群組</span><span class="sxs-lookup"><span data-stu-id="fff17-121">Globally based task, e.g., enabling a connection group globally</span></span></p></td>
<td align="left"><p><span data-ttu-id="fff17-122">當電腦關閉後再重新開機時，會執行待處理的工作。</span><span class="sxs-lookup"><span data-stu-id="fff17-122">The pending task will be performed when the computer is shut down and then restarted.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="fff17-123">當任務放在擱置狀態時，App-v 用戶端也會產生未決工作的登錄機碼，如下所示：</span><span class="sxs-lookup"><span data-stu-id="fff17-123">When a task is placed in a pending state, the App-V client also generates a registry key for the pending task, as follows:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="fff17-124">以使用者為基礎或以全域為基礎的工作</span><span class="sxs-lookup"><span data-stu-id="fff17-124">User-based or globally based task</span></span></th>
<th align="left"><span data-ttu-id="fff17-125">登錄機碼的產生位置</span><span class="sxs-lookup"><span data-stu-id="fff17-125">Where the registry key is generated</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="fff17-126">以使用者為基礎的工作</span><span class="sxs-lookup"><span data-stu-id="fff17-126">User-based tasks</span></span></p></td>
<td align="left"><p><span data-ttu-id="fff17-127">KEY_CURRENT_USER \Software\Microsoft\AppV\Client\PendingTasks</span><span class="sxs-lookup"><span data-stu-id="fff17-127">KEY_CURRENT_USER\Software\Microsoft\AppV\Client\PendingTasks</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="fff17-128">全域基礎任務</span><span class="sxs-lookup"><span data-stu-id="fff17-128">Globally based tasks</span></span></p></td>
<td align="left"><p><span data-ttu-id="fff17-129">HKEY_LOCAL_MACHINE \Software\Microsoft\AppV\Client\PendingTasks</span><span class="sxs-lookup"><span data-stu-id="fff17-129">HKEY_LOCAL_MACHINE\Software\Microsoft\AppV\Client\PendingTasks</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="fff17-130">使用 App-v 5.0 虛擬化 Microsoft Office 2013 和 Microsoft Office 2010</span><span class="sxs-lookup"><span data-stu-id="fff17-130">Virtualizing Microsoft Office 2013 and Microsoft Office 2010 using App-V 5.0</span></span>

<span data-ttu-id="fff17-131">如需 Microsoft Office 案例支援的 App-v 5.0 的詳細資訊，請使用下列連結。</span><span class="sxs-lookup"><span data-stu-id="fff17-131">Use the following link for more information about App-V 5.0 supported Microsoft Office scenarios.</span></span>

[<span data-ttu-id="fff17-132">為 Application Virtualization (APP-V) 5.0 虛擬化 Microsoft Office 2013</span><span class="sxs-lookup"><span data-stu-id="fff17-132">Virtualizing Microsoft Office 2013 for Application Virtualization (App-V) 5.0</span></span>](../solutions/virtualizing-microsoft-office-2013-for-application-virtualization--app-v--50-solutions.md)

<span data-ttu-id="fff17-133">**記事** 本檔的重點是建立 Microsoft Office 2013 App-v 5.0 套件。</span><span class="sxs-lookup"><span data-stu-id="fff17-133">**Note** This document focuses on creating a Microsoft Office 2013 App-V 5.0 Package.</span></span> <span data-ttu-id="fff17-134">不過，它也會提供 Microsoft Office 2010 應用程式與 App-v 5.0 相關案例的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="fff17-134">However, it also provides information about scenarios for Microsoft Office 2010 with App-V 5.0.</span></span>

 

### <a href="" id="-------------app-v-5-0-client-management-user-interface-application"></a> <span data-ttu-id="fff17-135">App-V 5.0 用戶端管理使用者介面應用程式</span><span class="sxs-lookup"><span data-stu-id="fff17-135">App-V 5.0 Client Management User Interface Application</span></span>

<span data-ttu-id="fff17-136">在舊版 App-V 5.0 中，由 app-v 5.0 用戶端安裝提供用戶端管理使用者介面（UI）。</span><span class="sxs-lookup"><span data-stu-id="fff17-136">In previous versions of App-V 5.0 the Client Management User Interface (UI) was provided with the App-V 5.0 Client installation.</span></span> <span data-ttu-id="fff17-137">如果使用 App-v 5.0 SP2，就不會再這麼做。</span><span class="sxs-lookup"><span data-stu-id="fff17-137">With App-V 5.0SP2 this is no longer the case.</span></span> <span data-ttu-id="fff17-138">系統管理員現在可以選擇將 App-V 5.0 用戶端 UI 部署為虛擬應用程式（使用所有受支援的 App-v 部署配置），或安裝為已安裝的應用程式。</span><span class="sxs-lookup"><span data-stu-id="fff17-138">Administrators now have the option to deploy the App-V 5.0 Client UI as a Virtual Application (using all supported App-V deployment configurations) or as an installed application.</span></span>

<span data-ttu-id="fff17-139">如需詳細資訊，請參閱[Microsoft Application Virtualization 5.0 用戶端 UI 應用程式](https://go.microsoft.com/fwlink/p/?LinkId=386345)（ https://go.microsoft.com/fwlink/?LinkId=386345) 。</span><span class="sxs-lookup"><span data-stu-id="fff17-139">For more information see [Microsoft Application Virtualization 5.0 Client UI Application](https://go.microsoft.com/fwlink/p/?LinkId=386345) (https://go.microsoft.com/fwlink/?LinkId=386345).</span></span>

### <span data-ttu-id="fff17-140">並列（SxS）元件自動封裝及部署</span><span class="sxs-lookup"><span data-stu-id="fff17-140">Side-by-Side (SxS) Assembly Automatic Packaging and Deployment</span></span>

<span data-ttu-id="fff17-141">App-V 5.0 SP2 現在會自動偵測並行（SxS）元件，以及在執行 App-v 5.0 SP2 用戶端的電腦上進行部署。</span><span class="sxs-lookup"><span data-stu-id="fff17-141">App-V 5.0SP2 now automatically detects side-by-side (SxS) assemblies, and deployment on the computer running the App-V 5.0SP2 client.</span></span> <span data-ttu-id="fff17-142">SxS 元件主要由 VC + + 執行時間相依性或 MSXML 所組成。</span><span class="sxs-lookup"><span data-stu-id="fff17-142">A SxS assembly primarily consists of VC++ run-time dependencies or MSXML.</span></span> <span data-ttu-id="fff17-143">在舊版 App-V 中，具有 VC 執行時間相依性的虛擬應用程式需要在執行 App-v 5.0 SP2 用戶端的電腦上本機使用這些相依性。</span><span class="sxs-lookup"><span data-stu-id="fff17-143">In previous versions of App-V, virtual applications that had dependencies on VC run-times required these dependencies to be locally on the computer running the App-V 5.0SP2 client.</span></span>

<span data-ttu-id="fff17-144">現在支援下列功能：</span><span class="sxs-lookup"><span data-stu-id="fff17-144">The following functionality is now supported:</span></span>

-   <span data-ttu-id="fff17-145">App-v 5.0 sequencer 會自動捕獲套件中的 SxS 元件，不論是否已在執行排序器的電腦上安裝 VC 執行時間。</span><span class="sxs-lookup"><span data-stu-id="fff17-145">The App-V 5.0 sequencer automatically captures the SxS assembly in the package regardless of whether the VC run-time has already been installed on the computer running the sequencer.</span></span>

-   <span data-ttu-id="fff17-146">App-V 5.0 用戶端會根據發佈時間所需的方式，自動將所需的 SxS 元件安裝到執行用戶端的電腦上。</span><span class="sxs-lookup"><span data-stu-id="fff17-146">The App-V 5.0 client automatically installs the required SxS assembly to the computer running the client as required at publishing time.</span></span>

-   <span data-ttu-id="fff17-147">App-v 5.0 sequencer 會使用 sequencer 報告機制來報告 VC 執行時間相依性。</span><span class="sxs-lookup"><span data-stu-id="fff17-147">The App-V 5.0 sequencer reports the VC run-time dependency using the sequencer reporting mechanism.</span></span>

-   <span data-ttu-id="fff17-148">App-v 5.0 sequencer 現在可讓您在執行排序器的電腦上已提供相依性的事件時，排除 VC 執行時間相依性。</span><span class="sxs-lookup"><span data-stu-id="fff17-148">The App-V 5.0 sequencer now allows you to exclude the VC run-time dependency in the event that the dependency is already available on the computer running the sequencer.</span></span>

### <span data-ttu-id="fff17-149">發佈更新改良功能</span><span class="sxs-lookup"><span data-stu-id="fff17-149">Publishing Refresh Improvements</span></span>

<span data-ttu-id="fff17-150">App-V 5.0 支援多個新增的功能，以改善針對特定使用者重新整理一組應用程式的整體體驗。</span><span class="sxs-lookup"><span data-stu-id="fff17-150">App-V 5.0 supports several features were added to improve the overall experience of refreshing a set of applications for a specific user.</span></span>

<span data-ttu-id="fff17-151">下列清單顯示 [發佈更新] 增強功能：</span><span class="sxs-lookup"><span data-stu-id="fff17-151">The following list displays the publishing refresh enhancements:</span></span>

<span data-ttu-id="fff17-152">下列清單包含有關如何啟用新的發佈重新整理改善的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="fff17-152">The following list contains more information about how to enable the new publishing refresh improvements.</span></span>

-   <span data-ttu-id="fff17-153">**EnablePublishingRefreshUI** -針對執行 App-v 5.0 用戶端的電腦啟用 [發佈更新進度] 列。</span><span class="sxs-lookup"><span data-stu-id="fff17-153">**EnablePublishingRefreshUI** - Enables the publishing refresh progress bar for the computer running the App-V 5.0 Client.</span></span>

-   <span data-ttu-id="fff17-154">**HideUI** -在手動同步處理期間隱藏發佈更新進度列。</span><span class="sxs-lookup"><span data-stu-id="fff17-154">**HideUI** - Hides the publishing refresh progress bar during a manual sync.</span></span>

### <span data-ttu-id="fff17-155">新的用戶端設定設定</span><span class="sxs-lookup"><span data-stu-id="fff17-155">New Client Configuration Setting</span></span>

<span data-ttu-id="fff17-156">App-v 5.0 SP2 提供下列新的用戶端配置設定：</span><span class="sxs-lookup"><span data-stu-id="fff17-156">The following new client configuration setting is available with App-V 5.0 SP2:</span></span>

<span data-ttu-id="fff17-157">**EnableDynamicVirtualization** -啟用支援的命令介面延伸、瀏覽器 Helper 物件，以及使用中 X 控制項來虛擬化並與虛擬應用程式一起執行。</span><span class="sxs-lookup"><span data-stu-id="fff17-157">**EnableDynamicVirtualization** - Enables supported Shell Extensions, Browser Helper Objects, and Active X controls to be virtualized and run with virtual applications.</span></span>

<span data-ttu-id="fff17-158">如需詳細資訊，請參閱[關於用戶端配置設定](about-client-configuration-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="fff17-158">For more information, see [About Client Configuration Settings](about-client-configuration-settings.md).</span></span>

### <a href="" id="-------------app-v-5-0-shell-extensions"></a> <span data-ttu-id="fff17-159">App-v 5.0 命令介面延伸</span><span class="sxs-lookup"><span data-stu-id="fff17-159">App-V 5.0 Shell extensions</span></span>

<span data-ttu-id="fff17-160">App-v 5.0 SP2 現在支援命令介面延伸。</span><span class="sxs-lookup"><span data-stu-id="fff17-160">App-V 5.0 SP2 now supports shell extensions.</span></span>

<span data-ttu-id="fff17-161">如需詳細資訊，請參閱[建立及管理 app-v 5.0 虛擬化應用程式](creating-and-managing-app-v-50-virtualized-applications.md)的**APP v 5.0 sp2 shell 擴充支援**區段。</span><span class="sxs-lookup"><span data-stu-id="fff17-161">For more information see the **App-V 5.0SP2 shell extension support** section of [Creating and Managing App-V 5.0 Virtualized Applications](creating-and-managing-app-v-50-virtualized-applications.md).</span></span>

## <a href="" id="---------app-v-5-0-documentation-updates"></a> <span data-ttu-id="fff17-162">App-v 5.0 檔更新</span><span class="sxs-lookup"><span data-stu-id="fff17-162">App-V 5.0 documentation updates</span></span>


<span data-ttu-id="fff17-163">App-V 5.0 SP2 提供下列案例的更新檔：</span><span class="sxs-lookup"><span data-stu-id="fff17-163">App-V 5.0 SP2 provides updated documentation for the following scenarios:</span></span>

-   [<span data-ttu-id="fff17-164">從舊版移轉</span><span class="sxs-lookup"><span data-stu-id="fff17-164">Migrating from a Previous Version</span></span>](migrating-from-a-previous-version-app-v-50.md)

-   [<span data-ttu-id="fff17-165">關於 App-V 5.0</span><span class="sxs-lookup"><span data-stu-id="fff17-165">About App-V 5.0</span></span>](about-app-v-50.md)

-   <span data-ttu-id="fff17-166">[關於 App-V 5.0 報告](about-app-v-50-reporting.md)（常見問題區段）</span><span class="sxs-lookup"><span data-stu-id="fff17-166">[About App-V 5.0 Reporting](about-app-v-50-reporting.md) (frequently asked questions section)</span></span>

## <span data-ttu-id="fff17-167">如何取得 MDOP 技術</span><span class="sxs-lookup"><span data-stu-id="fff17-167">How to Get MDOP Technologies</span></span>


<span data-ttu-id="fff17-168">App-v 5.0 是 Microsoft 桌面優化套件（MDOP）的一部分。</span><span class="sxs-lookup"><span data-stu-id="fff17-168">App-V 5.0 is a part of the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="fff17-169">MDOP 是 Microsoft 軟體保證的一部分。</span><span class="sxs-lookup"><span data-stu-id="fff17-169">MDOP is part of Microsoft Software Assurance.</span></span> <span data-ttu-id="fff17-170">如需 Microsoft 軟體保證及取得 MDOP 的詳細資訊，請參閱[如何取得 mdop](https://go.microsoft.com/fwlink/?LinkId=322049) （ https://go.microsoft.com/fwlink/?LinkId=322049) 。</span><span class="sxs-lookup"><span data-stu-id="fff17-170">For more information about Microsoft Software Assurance and acquiring MDOP, see [How Do I Get MDOP](https://go.microsoft.com/fwlink/?LinkId=322049) (https://go.microsoft.com/fwlink/?LinkId=322049).</span></span>






## <span data-ttu-id="fff17-171">相關主題</span><span class="sxs-lookup"><span data-stu-id="fff17-171">Related topics</span></span>


[<span data-ttu-id="fff17-172">App-V 5.0 SP2 版本資訊</span><span class="sxs-lookup"><span data-stu-id="fff17-172">Release Notes for App-V 5.0 SP2</span></span>](release-notes-for-app-v-50-sp2.md)

 

 





