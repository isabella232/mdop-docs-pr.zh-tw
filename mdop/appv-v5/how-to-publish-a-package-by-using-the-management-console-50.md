---
title: 如何使用 Management Console 發佈套件
description: 如何使用 Management Console 發佈套件
author: dansimp
ms.assetid: 7c6930fc-5c89-4519-a901-512dae155fd2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 832dd95edbb0f4cd6b6ae242a81859141ebcb279
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800430"
---
# <span data-ttu-id="b2cf9-103">如何使用 Management Console 發佈套件</span><span class="sxs-lookup"><span data-stu-id="b2cf9-103">How to Publish a Package by Using the Management Console</span></span>


<span data-ttu-id="b2cf9-104">使用下列程式發佈 App-v 5.0 套件。</span><span class="sxs-lookup"><span data-stu-id="b2cf9-104">Use the following procedure to publish an App-V 5.0 package.</span></span> <span data-ttu-id="b2cf9-105">發佈套件後，執行 App-V 5.0 用戶端的電腦就可以存取並執行該套件中的應用程式。</span><span class="sxs-lookup"><span data-stu-id="b2cf9-105">Once you publish a package, computers that are running the App-V 5.0 client can access and run the applications in that package.</span></span>

<span data-ttu-id="b2cf9-106">**記事** 從 App-v 5.0 SP3 開始，只支援將系統管理員發佈或取消發佈套件（如下所述）的功能。</span><span class="sxs-lookup"><span data-stu-id="b2cf9-106">**Note** The ability to enable only administrators to publish or unpublish packages (described below) is supported starting in App-V 5.0 SP3.</span></span>

 

**<span data-ttu-id="b2cf9-107">發佈 app-v 5.0 套件</span><span class="sxs-lookup"><span data-stu-id="b2cf9-107">To publish an App-V 5.0 package</span></span>**

1.  <span data-ttu-id="b2cf9-108">在 App-V 5.0 管理主控台中。</span><span class="sxs-lookup"><span data-stu-id="b2cf9-108">In the App-V 5.0 Management console.</span></span> <span data-ttu-id="b2cf9-109">以滑鼠右鍵按一下要發佈的套件名稱，然後選取 [**發佈**]。</span><span class="sxs-lookup"><span data-stu-id="b2cf9-109">right-click the name of the package to be published, and select **Publish**.</span></span>

2.  <span data-ttu-id="b2cf9-110">請查看 [**狀態**] 欄，確認套件已發佈且現已推出。</span><span class="sxs-lookup"><span data-stu-id="b2cf9-110">Review the **Status** column to verify that the package has been published and is now available.</span></span> <span data-ttu-id="b2cf9-111">如果套件可用，就會顯示 [**已發佈**] 狀態。</span><span class="sxs-lookup"><span data-stu-id="b2cf9-111">If the package is available, the status **published** is displayed.</span></span>

    <span data-ttu-id="b2cf9-112">如果套件未順利發佈，就會顯示**未發佈**狀態，以及解釋套件無法使用之原因的錯誤文字。</span><span class="sxs-lookup"><span data-stu-id="b2cf9-112">If the package is not published successfully, the status **unpublished** is displayed, along with error text that explains why the package is not available.</span></span>

**<span data-ttu-id="b2cf9-113">僅允許系統管理員發佈或取消發佈套件</span><span class="sxs-lookup"><span data-stu-id="b2cf9-113">To enable only administrators to publish or unpublish packages</span></span>**

1.  <span data-ttu-id="b2cf9-114">流覽至下列群群組原則物件節點：</span><span class="sxs-lookup"><span data-stu-id="b2cf9-114">Navigate to the following Group Policy Object node:</span></span>

    <span data-ttu-id="b2cf9-115">**電腦配置 &gt;原則 &gt; 管理範本 &gt; 系統 &gt; app-v &gt; 發佈**。</span><span class="sxs-lookup"><span data-stu-id="b2cf9-115">**Computer Configuration &gt; Policies &gt; Administrative Templates &gt; System &gt; App-V &gt; Publishing**.</span></span>

2.  <span data-ttu-id="b2cf9-116">啟用 [**需要發佈為系統管理員**] 群群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="b2cf9-116">Enable the **Require publish as administrator** Group Policy setting.</span></span>

    <span data-ttu-id="b2cf9-117">若要使用 PowerShell 來設定此專案，請參閱[如何使用 Powershell 管理在獨立電腦上](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admins-pub-pkgs)執行的 App-v 5.0 套件。</span><span class="sxs-lookup"><span data-stu-id="b2cf9-117">To alternatively use PowerShell to set this item, see [How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md#bkmk-admins-pub-pkgs).</span></span>

    <span data-ttu-id="b2cf9-118">您**有應用程式-V 的建議**嗎？</span><span class="sxs-lookup"><span data-stu-id="b2cf9-118">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="b2cf9-119">在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="b2cf9-119">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="b2cf9-120">有應用程式-V 問題嗎？</span><span class="sxs-lookup"><span data-stu-id="b2cf9-120">Got an App-V issue?</span></span>** <span data-ttu-id="b2cf9-121">使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="b2cf9-121">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="b2cf9-122">相關主題</span><span class="sxs-lookup"><span data-stu-id="b2cf9-122">Related topics</span></span>


[<span data-ttu-id="b2cf9-123">App-V 5.0 作業</span><span class="sxs-lookup"><span data-stu-id="b2cf9-123">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

[<span data-ttu-id="b2cf9-124">如何使用 Management Console 設定對套件的存取權</span><span class="sxs-lookup"><span data-stu-id="b2cf9-124">How to Configure Access to Packages by Using the Management Console</span></span>](how-to-configure-access-to-packages-by-using-the-management-console-50.md)

 

 





