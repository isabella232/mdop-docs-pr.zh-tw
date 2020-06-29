---
title: UE-V 2.0 的新功能
description: UE-V 2.0 的新功能
author: dansimp
ms.assetid: 5d852beb-f293-4e3a-a33b-c40df59a7515
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a7566bd82432dcf7e4c46e1fa3e66e55d1515b79
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810869"
---
# <span data-ttu-id="aafbb-103">UE-V 2.0 的新功能</span><span class="sxs-lookup"><span data-stu-id="aafbb-103">What's New in UE-V 2.0</span></span>


<span data-ttu-id="aafbb-104">Microsoft 使用者體驗虛擬化（UE-V）2.0 提供與 UE-V 1.0 相比的這些新功能和功能。</span><span class="sxs-lookup"><span data-stu-id="aafbb-104">Microsoft User Experience Virtualization (UE-V) 2.0 provides these new features and functionality compared to UE-V 1.0.</span></span> <span data-ttu-id="aafbb-105">[Microsoft 使用者體驗虛擬化（ue-v）2.0 版本資訊](microsoft-user-experience-virtualization--ue-v--20-release-notesuevv2.md)提供關於 ue-v 2.0 發行的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="aafbb-105">The [Microsoft User Experience Virtualization (UE-V) 2.0 Release Notes](microsoft-user-experience-virtualization--ue-v--20-release-notesuevv2.md) provide more information about the UE-V 2.0 release.</span></span>

## <span data-ttu-id="aafbb-106">不再需要用戶端快取（CSC）</span><span class="sxs-lookup"><span data-stu-id="aafbb-106">Client-side cache (CSC) no longer required</span></span>


<span data-ttu-id="aafbb-107">這個版本的 UE-V 引入**同步處理提供程式**，它會取代 Windows 離線檔案功能的需求，以支援用戶端的設定快取。</span><span class="sxs-lookup"><span data-stu-id="aafbb-107">This version of UE-V introduces the **sync provider**, which replaces the requirement for the Windows Offline Files feature to support a client-side cache of settings.</span></span>

<span data-ttu-id="aafbb-108">雖然 UE-V 只會在應用程式開啟、關閉或 Windows 鎖定或解除鎖定時，或在登入或登出時同步處理設定，但同步處理提供者也會使用 .。。</span><span class="sxs-lookup"><span data-stu-id="aafbb-108">Whereas UE-V used to synchronize settings only when an application opened, closed, or when Windows locked or unlocked, or at logon or logoff, the sync provider also …</span></span>

-   <span data-ttu-id="aafbb-109">使用「**觸發事件**」同步處理本機應用程式和 Windows 設定</span><span class="sxs-lookup"><span data-stu-id="aafbb-109">Synchronizes local application and Windows settings out-of-band using "**trigger events**"</span></span>

-   <span data-ttu-id="aafbb-110">使用**排程任務**，以您針對企業需求所選擇的任何間隔來同步處理設定儲存套件（預設為每30分鐘一次）</span><span class="sxs-lookup"><span data-stu-id="aafbb-110">Uses a **scheduled task** to sync the settings storage package in any interval you choose for your enterprise requirements (every 30 minutes by default)</span></span>

<span data-ttu-id="aafbb-111">某些條件可提供更頻繁的同步處理。</span><span class="sxs-lookup"><span data-stu-id="aafbb-111">Certain conditions provide more frequent synchronization.</span></span>

-   <span data-ttu-id="aafbb-112">當使用者按一下新的公司設定中心應用程式中的 [**立即同步**處理] 按鈕時，設定就會同步處理。</span><span class="sxs-lookup"><span data-stu-id="aafbb-112">Settings synchronize when the user clicks the **Sync Now** button in the new Company Settings Center application.</span></span>

-   <span data-ttu-id="aafbb-113">同步處理提供者也可以在單一應用程式中開始，而不需要等候排程的同步處理工作。</span><span class="sxs-lookup"><span data-stu-id="aafbb-113">The sync provider can also start for a single application without waiting for the scheduled synchronization task.</span></span> <span data-ttu-id="aafbb-114">例如，當應用程式關閉時，任何設定變更都會寫入本機快取，同步處理提供程式進程會以非同步方式執行，以將這些新的設定變更移至設定儲存位置。</span><span class="sxs-lookup"><span data-stu-id="aafbb-114">For example, when an application is closed, any settings changes are written to the local cache, and the sync provider process runs asynchronously to move those new settings changes to the settings storage location.</span></span>

## <span data-ttu-id="aafbb-115">Windows 應用程式同步處理</span><span class="sxs-lookup"><span data-stu-id="aafbb-115">Windows app synchronization</span></span>


<span data-ttu-id="aafbb-116">Windows 應用程式的開發人員可以定義要同步處理的設定（如果有的話），而這些設定現在可以使用 UE-V 捕獲並同步處理。</span><span class="sxs-lookup"><span data-stu-id="aafbb-116">The developer of a Windows app can define which settings, if any, are to be synchronized, and these settings can now be captured and synchronized with UE-V.</span></span>

<span data-ttu-id="aafbb-117">根據預設，UE-V 會同步處理 Windows 8 和 Windows 8.1 中包含的許多 Windows 應用程式的設定。</span><span class="sxs-lookup"><span data-stu-id="aafbb-117">By default, UE-V synchronizes the settings of many of the Windows apps included in Windows 8 and Windows 8.1.</span></span> <span data-ttu-id="aafbb-118">您可以使用 Windows PowerShell、Windows 管理工具（WMI）或群組原則來修改已同步處理應用程式的清單。</span><span class="sxs-lookup"><span data-stu-id="aafbb-118">You can modify the list of synchronized apps with Windows PowerShell, Windows Management Instrumentation (WMI), or Group Policy.</span></span>

<span data-ttu-id="aafbb-119">**記事** 如果網域使用者將登入認證連結到其 Microsoft 帳戶，UE-V 就不會同步處理 Windows 應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="aafbb-119">**Note** UE-V does not synchronize Windows app settings if the domain users link their sign-in credentials to their Microsoft account.</span></span> <span data-ttu-id="aafbb-120">此連結會同步處理設定至 Microsoft OneDrive，因此 UE-V 只會同步處理桌面應用程式。</span><span class="sxs-lookup"><span data-stu-id="aafbb-120">This linking synchronizes settings to Microsoft OneDrive so UE-V only synchronizes the desktop applications.</span></span>

 

## <span data-ttu-id="aafbb-121">Microsoft 帳戶連結</span><span class="sxs-lookup"><span data-stu-id="aafbb-121">Microsoft account linking</span></span>


<span data-ttu-id="aafbb-122">如果您是使用 Microsoft 帳戶登入，或是將您的 Microsoft 帳戶連結至網域帳戶，則在 Windows 8 上進行的 [設定同步處理] 就是 Windows 8 的新功能。</span><span class="sxs-lookup"><span data-stu-id="aafbb-122">Settings synchronization via OneDrive is new to Windows 8 when you are signed in with a Microsoft account or if you link your Microsoft account to your domain account.</span></span> <span data-ttu-id="aafbb-123">如果網域使用者使用 UE-V，且已登入 Microsoft 帳戶，請 .。。</span><span class="sxs-lookup"><span data-stu-id="aafbb-123">If a domain user uses UE-V and has signed in to a Microsoft account, then…</span></span>

-   <span data-ttu-id="aafbb-124">UE-V 只同步處理桌面應用程式的設定</span><span class="sxs-lookup"><span data-stu-id="aafbb-124">UE-V only synchronizes settings for desktop applications</span></span>

-   <span data-ttu-id="aafbb-125">Microsoft 帳戶處理 Windows 應用程式設定和 Windows 桌面設定</span><span class="sxs-lookup"><span data-stu-id="aafbb-125">Microsoft account handles Windows app settings and Windows desktop settings</span></span>

## <span data-ttu-id="aafbb-126">公司設定中心</span><span class="sxs-lookup"><span data-stu-id="aafbb-126">Company Settings Center</span></span>


<span data-ttu-id="aafbb-127">您可以為使用者提供一些控制哪些設定會透過 UE-V 2 （稱為「公司設定中心」）中的應用程式進行同步處理。</span><span class="sxs-lookup"><span data-stu-id="aafbb-127">You can provide your users with some control over which settings are synchronized through an application in UE-V 2 called Company Settings Center.</span></span> <span data-ttu-id="aafbb-128">[公司設定中心] 與 UE-V Agent 一起安裝，使用者可以從 [控制台]、[**開始**] 功能表或 [**開始**] 畫面，以及從 ue-v 通知區域圖示存取。</span><span class="sxs-lookup"><span data-stu-id="aafbb-128">Company Settings Center is installed along with the UE-V Agent, and users can access it from Control Panel, the **Start** menu or **Start** screen, and from the UE-V notification area icon.</span></span>

<span data-ttu-id="aafbb-129">[公司設定中心] 會顯示已同步處理的設定，並讓使用者看到 UE-V 的同步處理狀態。</span><span class="sxs-lookup"><span data-stu-id="aafbb-129">Company Settings Center displays which settings are synchronized and lets users see the synchronization status of UE-V.</span></span> <span data-ttu-id="aafbb-130">如果您允許，使用者可以使用 [公司設定中心] 來選取要同步處理的設定。</span><span class="sxs-lookup"><span data-stu-id="aafbb-130">If you let them, users can use Company Settings Center to select which settings to synchronize.</span></span> <span data-ttu-id="aafbb-131">他們也可以按一下 [**立即同步**處理] 按鈕，立即同步處理所有設定。</span><span class="sxs-lookup"><span data-stu-id="aafbb-131">They can also click the **Sync Now** button to synchronize all settings immediately.</span></span>






## <span data-ttu-id="aafbb-132">相關主題</span><span class="sxs-lookup"><span data-stu-id="aafbb-132">Related topics</span></span>


[<span data-ttu-id="aafbb-133">UE-V 2.x 入門</span><span class="sxs-lookup"><span data-stu-id="aafbb-133">Get Started with UE-V 2.x</span></span>](get-started-with-ue-v-2x-new-uevv2.md)

[<span data-ttu-id="aafbb-134">準備 UE-V a.x 部署</span><span class="sxs-lookup"><span data-stu-id="aafbb-134">Prepare a UE-V 2.x Deployment</span></span>](prepare-a-ue-v-2x-deployment-new-uevv2.md)

[<span data-ttu-id="aafbb-135">Microsoft User Experience Virtualization (UE-V) 2.0 版本資訊</span><span class="sxs-lookup"><span data-stu-id="aafbb-135">Microsoft User Experience Virtualization (UE-V) 2.0 Release Notes</span></span>](microsoft-user-experience-virtualization--ue-v--20-release-notesuevv2.md)

 

 





