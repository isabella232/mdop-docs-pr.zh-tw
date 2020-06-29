---
title: 如何在伺服器管理主控台中管理應用程式群組
description: 如何在伺服器管理主控台中管理應用程式群組
author: dansimp
ms.assetid: 46997971-bdc8-4565-aefd-f47e90d6d7a6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 59a357d93ea63cc728f59a0633b7a5b9953aad14
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801322"
---
# <span data-ttu-id="0071c-103">如何在伺服器管理主控台中管理應用程式群組</span><span class="sxs-lookup"><span data-stu-id="0071c-103">How to Manage Application Groups in the Server Management Console</span></span>


<span data-ttu-id="0071c-104">您可以在應用程式虛擬化伺服器管理主控台的應用程式群組中顯示和管理一或多個應用程式。</span><span class="sxs-lookup"><span data-stu-id="0071c-104">You can display and manage one or more applications in application groups in the Application Virtualization Server Management Console.</span></span> <span data-ttu-id="0071c-105">當您想要執行下列動作時，這會很有用：</span><span class="sxs-lookup"><span data-stu-id="0071c-105">This can be useful when you want to do the following:</span></span>

-   <span data-ttu-id="0071c-106">將許多應用程式組織成更易於管理的子群組。</span><span class="sxs-lookup"><span data-stu-id="0071c-106">Organize many applications into more manageable subgroups.</span></span>

-   <span data-ttu-id="0071c-107">建立部門或其他公司分部專用的應用程式群組。</span><span class="sxs-lookup"><span data-stu-id="0071c-107">Create groups of applications specific to a department or other company division.</span></span>

-   <span data-ttu-id="0071c-108">群組相似的應用程式類型，例如財務軟體。</span><span class="sxs-lookup"><span data-stu-id="0071c-108">Group similar types of applications, such as financial software.</span></span>

-   <span data-ttu-id="0071c-109">依群組簡化存取許可權或授權管理。</span><span class="sxs-lookup"><span data-stu-id="0071c-109">Simplify access permissions or license management by group.</span></span>

-   <span data-ttu-id="0071c-110">同時變更群組中應用程式和應用程式群組的屬性。</span><span class="sxs-lookup"><span data-stu-id="0071c-110">Change the properties of applications and application groups within a group simultaneously.</span></span>

<span data-ttu-id="0071c-111">您可以建立群組，將它放在您要在主控台**應用程式**樹狀結構中的位置，然後將應用程式匯入到群組中。</span><span class="sxs-lookup"><span data-stu-id="0071c-111">You can create a group, place it where you would like in the console's **Applications** tree, and import applications to the group.</span></span> <span data-ttu-id="0071c-112">接著，您可以設定及管理群組的屬性，以影響其所有應用程式。</span><span class="sxs-lookup"><span data-stu-id="0071c-112">Then you can configure and manage the group's properties to affect all of its applications.</span></span> <span data-ttu-id="0071c-113">您也可以在群組間移動應用程式。</span><span class="sxs-lookup"><span data-stu-id="0071c-113">You can also move applications among groups.</span></span>

<span data-ttu-id="0071c-114">**記事** 將應用程式移到群組中並不會影響其檔案（SFT、OSD 或 SPRJ）在伺服器檔案系統上的位置。</span><span class="sxs-lookup"><span data-stu-id="0071c-114">**Note** Moving applications into groups does not affect the locations of their files (SFT, OSD, or SPRJ) on the server's file system.</span></span>

 

## <span data-ttu-id="0071c-115">本節內容</span><span class="sxs-lookup"><span data-stu-id="0071c-115">In This Section</span></span>


<a href="" id="how-to-create-an-application-group"></a>[<span data-ttu-id="0071c-116">如何建立應用程式群組</span><span class="sxs-lookup"><span data-stu-id="0071c-116">How to Create an Application Group</span></span>](how-to-create-an-application-group.md)  
<span data-ttu-id="0071c-117">提供建立應用程式群組的逐步指示。</span><span class="sxs-lookup"><span data-stu-id="0071c-117">Provides step-by-step instructions for creating an application group.</span></span>

<a href="" id="how-to-move-an-application-group"></a>[<span data-ttu-id="0071c-118">如何移動應用程式群組</span><span class="sxs-lookup"><span data-stu-id="0071c-118">How to Move an Application Group</span></span>](how-to-move-an-application-group.md)  
<span data-ttu-id="0071c-119">提供移動應用程式群組的逐步指示。</span><span class="sxs-lookup"><span data-stu-id="0071c-119">Provides step-by-step instructions for moving an application group.</span></span>

<a href="" id="how-to-rename-an-application-group"></a>[<span data-ttu-id="0071c-120">如何重新命名應用程式群組</span><span class="sxs-lookup"><span data-stu-id="0071c-120">How to Rename an Application Group</span></span>](how-to-rename-an-application-group.md)  
<span data-ttu-id="0071c-121">提供重新命名應用程式群組的逐步指示。</span><span class="sxs-lookup"><span data-stu-id="0071c-121">Provides step-by-step instructions for renaming an application group.</span></span>

<a href="" id="how-to-remove-an-application-group"></a>[<span data-ttu-id="0071c-122">如何移除應用程式群組</span><span class="sxs-lookup"><span data-stu-id="0071c-122">How to Remove an Application Group</span></span>](how-to-remove-an-application-group.md)  
<span data-ttu-id="0071c-123">提供移除或刪除應用程式群組的逐步指示。</span><span class="sxs-lookup"><span data-stu-id="0071c-123">Provides step-by-step instructions for removing or deleting an application group.</span></span>

## <span data-ttu-id="0071c-124">相關主題</span><span class="sxs-lookup"><span data-stu-id="0071c-124">Related topics</span></span>


[<span data-ttu-id="0071c-125">如何在伺服器管理主控台中管理應用程式</span><span class="sxs-lookup"><span data-stu-id="0071c-125">How to Manage Applications in the Server Management Console</span></span>](how-to-manage-applications-in-the-server-management-console.md)

[<span data-ttu-id="0071c-126">如何在 Application Virtualization 伺服器管理主控台中執行系統管理工作</span><span class="sxs-lookup"><span data-stu-id="0071c-126">How to Perform Administrative Tasks in the Application Virtualization Server Management Console</span></span>](how-to-perform-administrative-tasks-in-the-application-virtualization-server-management-console.md)

 

 





