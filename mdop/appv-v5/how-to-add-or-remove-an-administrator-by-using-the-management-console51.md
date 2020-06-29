---
title: 如何使用 Management Console 新增或移除系統管理員
description: 如何使用 Management Console 新增或移除系統管理員
author: dansimp
ms.assetid: 7ff8c436-9d2e-446a-9ea2-bbab7e25bf21
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8fbc1a532a39c8688b99c28a2e23b713b348967c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800607"
---
# <span data-ttu-id="c9f74-103">如何使用 Management Console 新增或移除系統管理員</span><span class="sxs-lookup"><span data-stu-id="c9f74-103">How to Add or Remove an Administrator by Using the Management Console</span></span>


<span data-ttu-id="c9f74-104">使用下列程式在 Microsoft Application Virtualization （App-v） 5.1 server 上新增或移除系統管理員。</span><span class="sxs-lookup"><span data-stu-id="c9f74-104">Use the following procedures to add or remove an administrator on the Microsoft Application Virtualization (App-V) 5.1 server.</span></span>

**<span data-ttu-id="c9f74-105">使用管理主控台新增管理員</span><span class="sxs-lookup"><span data-stu-id="c9f74-105">To add an administrator using the Management Console</span></span>**

1.  <span data-ttu-id="c9f74-106">開啟 Microsoft Application Virtualization （App-v）5.1 管理主控台，然後在 [功能窗格] 中按一下 [系統**管理員**]。</span><span class="sxs-lookup"><span data-stu-id="c9f74-106">Open the Microsoft Application Virtualization (App-V) 5.1 Management Console and click **Administrators** in the navigation pane.</span></span> <span data-ttu-id="c9f74-107">[功能窗格] 會顯示目前擁有 Microsoft Application Virtualization （App-v） 5.1 server 管理存取權的 Access 目錄（AD）使用者和群組清單。</span><span class="sxs-lookup"><span data-stu-id="c9f74-107">The navigation pane displays a list of Access Directory (AD) users and groups that currently have administrative access to the Microsoft Application Virtualization (App-V) 5.1 server.</span></span>

2.  <span data-ttu-id="c9f74-108">若要新增系統管理員，請按一下 [**新增管理員**]，輸入您要在 [ **Active Directory 名稱**] 欄位中新增的系統管理員名稱。</span><span class="sxs-lookup"><span data-stu-id="c9f74-108">To add a new administrator, click **Add Administrator** Type the name of the administrator that you want to add in the **Active Directory Name** field.</span></span> <span data-ttu-id="c9f74-109">請確定您提供相關聯的使用者帳戶網功能變數名稱稱。</span><span class="sxs-lookup"><span data-stu-id="c9f74-109">Ensure you provide the associated user account domain name.</span></span> <span data-ttu-id="c9f74-110">例如，**網域**的使用者  \\  **名稱**。</span><span class="sxs-lookup"><span data-stu-id="c9f74-110">For example, **Domain** \\ **UserName**.</span></span>

3.  <span data-ttu-id="c9f74-111">選取您要新增的帳戶，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="c9f74-111">Select the account that you want to add and click **Add**.</span></span> <span data-ttu-id="c9f74-112">新帳戶會顯示在伺服器管理員清單中。</span><span class="sxs-lookup"><span data-stu-id="c9f74-112">The new account is displayed in the list of server administrators.</span></span>

**<span data-ttu-id="c9f74-113">使用管理主控台移除管理員</span><span class="sxs-lookup"><span data-stu-id="c9f74-113">To remove an administrator using the Management Console</span></span>**

1.  <span data-ttu-id="c9f74-114">開啟 Microsoft Application Virtualization （App-v）5.1 管理主控台，然後在 [功能窗格] 中按一下 [系統**管理員**]。</span><span class="sxs-lookup"><span data-stu-id="c9f74-114">Open the Microsoft Application Virtualization (App-V) 5.1 Management Console and click **Administrators** in the navigation pane.</span></span> <span data-ttu-id="c9f74-115">[功能窗格] 會顯示目前擁有 Microsoft Application Virtualization （App-v） 5.1 server 管理存取權的 AD 使用者和群組清單。</span><span class="sxs-lookup"><span data-stu-id="c9f74-115">The navigation pane displays a list of AD users and groups that currently have administrative access to the Microsoft Application Virtualization (App-V) 5.1 server.</span></span>

2.  <span data-ttu-id="c9f74-116">以滑鼠右鍵按一下要從系統管理員清單中移除的帳戶，然後選取 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="c9f74-116">Right-click the account to be removed from the list of administrators and select **Remove**.</span></span>

    <span data-ttu-id="c9f74-117">您**有應用程式-V 的建議**嗎？</span><span class="sxs-lookup"><span data-stu-id="c9f74-117">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="c9f74-118">在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="c9f74-118">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="c9f74-119">有應用程式-V 問題嗎？</span><span class="sxs-lookup"><span data-stu-id="c9f74-119">Got an App-V issue?</span></span>** <span data-ttu-id="c9f74-120">使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="c9f74-120">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="c9f74-121">相關主題</span><span class="sxs-lookup"><span data-stu-id="c9f74-121">Related topics</span></span>


[<span data-ttu-id="c9f74-122">App-V 5.1 作業</span><span class="sxs-lookup"><span data-stu-id="c9f74-122">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

 

 





