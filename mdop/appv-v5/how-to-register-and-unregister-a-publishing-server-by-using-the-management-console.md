---
title: 如何使用 Management Console 註冊及取消註冊發佈伺服器
description: 如何使用 Management Console 註冊及取消註冊發佈伺服器
author: dansimp
ms.assetid: c24f3b43-4888-41a9-9a39-973657f2b917
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5241af748029b7976c49b6474e5ef7c050699dd7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800425"
---
# <span data-ttu-id="d6d29-103">如何使用 Management Console 註冊及取消註冊發佈伺服器</span><span class="sxs-lookup"><span data-stu-id="d6d29-103">How to Register and Unregister a Publishing Server by Using the Management Console</span></span>


<span data-ttu-id="d6d29-104">您可以登錄並取消註冊將與 App-v 5.0 管理伺服器同步處理的發佈伺服器。</span><span class="sxs-lookup"><span data-stu-id="d6d29-104">You can register and unregister publishing servers that will synchronize with the App-V 5.0 management server.</span></span> <span data-ttu-id="d6d29-105">您也可以看到發佈伺服器進行的最後一次嘗試將資訊與管理伺服器同步處理的時間。</span><span class="sxs-lookup"><span data-stu-id="d6d29-105">You can also see the last attempt that the publishing server made to synchronize the information with the management server.</span></span>

<span data-ttu-id="d6d29-106">使用下列程式來註冊或登出發佈伺服器。</span><span class="sxs-lookup"><span data-stu-id="d6d29-106">Use the following procedure to register or unregister a publishing server.</span></span>

**<span data-ttu-id="d6d29-107">使用管理主控台註冊發佈伺服器</span><span class="sxs-lookup"><span data-stu-id="d6d29-107">To register a publishing server using the Management Console</span></span>**

1.  <span data-ttu-id="d6d29-108">連線至 [管理] 主控台，然後選取 [**伺服器**]。</span><span class="sxs-lookup"><span data-stu-id="d6d29-108">Connect to the Management Console and select **Servers**.</span></span> <span data-ttu-id="d6d29-109">如需如何連線至管理主控台的詳細資訊，請參閱[如何連線至管理主控台](how-to-connect-to-the-management-console-beta.md)。</span><span class="sxs-lookup"><span data-stu-id="d6d29-109">For more information about how to connect to the Management Console, see [How to Connect to the Management Console](how-to-connect-to-the-management-console-beta.md).</span></span>

2.  <span data-ttu-id="d6d29-110">隨即會顯示已與管理伺服器同步處理的發佈伺服器清單。</span><span class="sxs-lookup"><span data-stu-id="d6d29-110">A list of publishing servers that already synchronize with the management server is displayed.</span></span> <span data-ttu-id="d6d29-111">按一下 [註冊新伺服器]，註冊新的伺服器。</span><span class="sxs-lookup"><span data-stu-id="d6d29-111">Click Register New Server to register a new server.</span></span>

3.  <span data-ttu-id="d6d29-112">在 [**伺服器名稱**] 行輸入加入網域的電腦名稱稱，以指定伺服器的名稱。</span><span class="sxs-lookup"><span data-stu-id="d6d29-112">Type a computer name of a domain joined computer on the **Server Name** line, to specify a name for the server.</span></span> <span data-ttu-id="d6d29-113">您也應該包含功能變數名稱，例如**MyDomain\\TestServer**。</span><span class="sxs-lookup"><span data-stu-id="d6d29-113">You should also include a domain name, for example, **MyDomain\\TestServer**.</span></span> <span data-ttu-id="d6d29-114">按一下 [**檢查**]。</span><span class="sxs-lookup"><span data-stu-id="d6d29-114">Click **Check**.</span></span>

4.  <span data-ttu-id="d6d29-115">選取電腦，然後按一下 [**新增**]，將電腦新增到伺服器清單中。</span><span class="sxs-lookup"><span data-stu-id="d6d29-115">Select the computer and click **Add** to add the computer to the list of servers.</span></span> <span data-ttu-id="d6d29-116">新的伺服器會顯示在清單中。</span><span class="sxs-lookup"><span data-stu-id="d6d29-116">The new server will be displayed in the list.</span></span>

**<span data-ttu-id="d6d29-117">使用管理主控台登出發佈伺服器</span><span class="sxs-lookup"><span data-stu-id="d6d29-117">To unregister a publishing server using the Management Console</span></span>**

1.  <span data-ttu-id="d6d29-118">連線至 [管理] 主控台，然後選取 [**伺服器**]。</span><span class="sxs-lookup"><span data-stu-id="d6d29-118">Connect to the Management Console and select **Servers**.</span></span> <span data-ttu-id="d6d29-119">如需如何連線至管理主控台的詳細資訊，請參閱[如何連線至管理主控台](how-to-connect-to-the-management-console-beta.md)。</span><span class="sxs-lookup"><span data-stu-id="d6d29-119">For more information about how to connect to the Management Console, see [How to Connect to the Management Console](how-to-connect-to-the-management-console-beta.md).</span></span>

2.  <span data-ttu-id="d6d29-120">隨即會顯示與管理伺服器同步處理的發佈伺服器清單。</span><span class="sxs-lookup"><span data-stu-id="d6d29-120">A list of publishing servers that synchronize with the management server is displayed.</span></span>

3.  <span data-ttu-id="d6d29-121">若要登出伺服器，請以滑鼠右鍵按一下電腦名稱稱，然後選取電腦名稱稱，然後選取 [**登出伺服器**]。</span><span class="sxs-lookup"><span data-stu-id="d6d29-121">To unregister the server, right-click the computer name and select the computer name and select **unregister server**.</span></span>

    <span data-ttu-id="d6d29-122">您**有應用程式-V 的建議**嗎？</span><span class="sxs-lookup"><span data-stu-id="d6d29-122">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="d6d29-123">在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="d6d29-123">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="d6d29-124">有應用程式-V 問題嗎？</span><span class="sxs-lookup"><span data-stu-id="d6d29-124">Got an App-V issue?</span></span>** <span data-ttu-id="d6d29-125">使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="d6d29-125">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="d6d29-126">相關主題</span><span class="sxs-lookup"><span data-stu-id="d6d29-126">Related topics</span></span>


[<span data-ttu-id="d6d29-127">App-V 5.0 作業</span><span class="sxs-lookup"><span data-stu-id="d6d29-127">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

 

 





