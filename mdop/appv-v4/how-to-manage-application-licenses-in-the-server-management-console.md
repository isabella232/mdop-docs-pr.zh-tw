---
title: 如何在伺服器管理主控台中管理應用程式授權
description: 如何在伺服器管理主控台中管理應用程式授權
author: dansimp
ms.assetid: 48503b04-0de7-48de-98ee-4623a712a341
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ca9ab54c8b4cee06e0b17d8b5dee3d3ca7ce69c5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801330"
---
# <span data-ttu-id="9f9db-103">如何在伺服器管理主控台中管理應用程式授權</span><span class="sxs-lookup"><span data-stu-id="9f9db-103">How to Manage Application Licenses in the Server Management Console</span></span>


<span data-ttu-id="9f9db-104">應用程式虛擬化伺服器管理主控台是您用來管理應用程式虛擬化平臺的介面。</span><span class="sxs-lookup"><span data-stu-id="9f9db-104">The Application Virtualization Server Management Console is the interface you use to manage the Application Virtualization platform.</span></span> <span data-ttu-id="9f9db-105">從它來看，您可以新增、移除、設定及控制應用程式授權群組。</span><span class="sxs-lookup"><span data-stu-id="9f9db-105">From it, you can add, remove, configure, and control application license groups.</span></span>

<span data-ttu-id="9f9db-106">**重要** 如果應用程式-V 用戶端應用程式來源根（ASR）設定已設定為使用管理伺服器以外的任何資料流程來源類型（例如，流式伺服器、IIS 伺服器或檔案伺服器），則管理伺服器無法強制執行其授權原則。</span><span class="sxs-lookup"><span data-stu-id="9f9db-106">**Important** If the App-V client Application Source Root (ASR) setting is configured to use any type of streaming source other than the Management Server, for example a Streaming Server, an IIS server, or a File server, then the Management Server is unable to enforce its licensing policy.</span></span>

 

## <span data-ttu-id="9f9db-107">本節內容</span><span class="sxs-lookup"><span data-stu-id="9f9db-107">In This Section</span></span>


<a href="" id="how-to-create-an-application-license-group"></a>[<span data-ttu-id="9f9db-108">如何建立應用程式授權群組</span><span class="sxs-lookup"><span data-stu-id="9f9db-108">How to Create an Application License Group</span></span>](how-to-create-an-application-license-group.md)  
<span data-ttu-id="9f9db-109">提供在授權群組中建立新應用程式的程式。</span><span class="sxs-lookup"><span data-stu-id="9f9db-109">Provides a procedure for creating a new application in a license group.</span></span>

<a href="" id="how-to-associate-an-application-with-a-license-group"></a>[<span data-ttu-id="9f9db-110">如何建立應用程式與授權群組的關聯</span><span class="sxs-lookup"><span data-stu-id="9f9db-110">How to Associate an Application with a License Group</span></span>](how-to-associate-an-application-with-a-license-group.md)  
<span data-ttu-id="9f9db-111">提供將應用程式新增至授權群組的程式。</span><span class="sxs-lookup"><span data-stu-id="9f9db-111">Provides a procedure for adding an application to a license group.</span></span>

<a href="" id="how-to-remove-an-application-from-a-license-group"></a>[<span data-ttu-id="9f9db-112">如何從授權群組移除應用程式</span><span class="sxs-lookup"><span data-stu-id="9f9db-112">How to Remove an Application from a License Group</span></span>](how-to-remove-an-application-from-a-license-group.md)  
<span data-ttu-id="9f9db-113">提供從授權群組移除應用程式的程式。</span><span class="sxs-lookup"><span data-stu-id="9f9db-113">Provides a procedure for removing an application from a license group.</span></span>

<a href="" id="how-to-remove-an-application-license-group"></a>[<span data-ttu-id="9f9db-114">如何移除應用程式授權群組</span><span class="sxs-lookup"><span data-stu-id="9f9db-114">How to Remove an Application License Group</span></span>](how-to-remove-an-application-license-group.md)  
<span data-ttu-id="9f9db-115">本節包含刪除應用程式授權群組所需的步驟。</span><span class="sxs-lookup"><span data-stu-id="9f9db-115">This section includes the steps necessary to delete an application license group.</span></span>

<a href="" id="how-to-set-up-an-unlimited-license-group"></a>[<span data-ttu-id="9f9db-116">如何設定無限授權群組</span><span class="sxs-lookup"><span data-stu-id="9f9db-116">How to Set Up an Unlimited License Group</span></span>](how-to-set-up-an-unlimited-license-group.md)  
<span data-ttu-id="9f9db-117">提供建立新的無限制授權群組的程式，允許不限數量的使用者存取群組中的應用程式。</span><span class="sxs-lookup"><span data-stu-id="9f9db-117">Provides a procedure for creating a new unlimited license group, allowing an unlimited number of users to access the applications in the group.</span></span>

<a href="" id="how-to-set-up-a-concurrent-license-group"></a>[<span data-ttu-id="9f9db-118">如何設定並行授權群組</span><span class="sxs-lookup"><span data-stu-id="9f9db-118">How to Set Up a Concurrent License Group</span></span>](how-to-set-up-a-concurrent-license-group.md)  
<span data-ttu-id="9f9db-119">提供建立新的併發授權群組的程式，讓特定數量的併發使用者可以存取群組中的應用程式。</span><span class="sxs-lookup"><span data-stu-id="9f9db-119">Provides a procedure for creating a new concurrent license group, allowing a specific number of concurrent users to access the applications in the group.</span></span>

<a href="" id="how-to-set-up-a-named-license-group"></a>[<span data-ttu-id="9f9db-120">如何設定指定授權群組</span><span class="sxs-lookup"><span data-stu-id="9f9db-120">How to Set Up a Named License Group</span></span>](how-to-set-up-a-named-license-group.md)  
<span data-ttu-id="9f9db-121">提供建立新的無限制授權群組的程式，讓特定使用者可以存取群組中的應用程式。</span><span class="sxs-lookup"><span data-stu-id="9f9db-121">Provides a procedure for creating a new unlimited license group, allowing specific users to access the applications in the group.</span></span>

## <span data-ttu-id="9f9db-122">相關主題</span><span class="sxs-lookup"><span data-stu-id="9f9db-122">Related topics</span></span>


[<span data-ttu-id="9f9db-123">如何在 Application Virtualization 伺服器管理主控台中執行系統管理工作</span><span class="sxs-lookup"><span data-stu-id="9f9db-123">How to Perform Administrative Tasks in the Application Virtualization Server Management Console</span></span>](how-to-perform-administrative-tasks-in-the-application-virtualization-server-management-console.md)

 

 





