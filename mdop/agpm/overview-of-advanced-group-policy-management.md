---
title: 進階群組原則管理概觀
description: 進階群組原則管理概觀
author: dansimp
ms.assetid: 028de9dd-848b-42bc-a982-65ba5c433772
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 38396de6bd8bdace72d3add1bba09769ae26de32
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809381"
---
# <span data-ttu-id="2762a-103">進階群組原則管理概觀</span><span class="sxs-lookup"><span data-stu-id="2762a-103">Overview of Advanced Group Policy Management</span></span>


<span data-ttu-id="2762a-104">您可以使用高級群組原則管理（AGPM）來延伸群組原則管理主控台（GPMC）的功能，為群組原則物件（Gpo）提供全面的變更控制與增強的管理。</span><span class="sxs-lookup"><span data-stu-id="2762a-104">You can use Advanced Group Policy Management (AGPM) to extend the capabilities of the Group Policy Management Console (GPMC), providing comprehensive change control and enhanced management for Group Policy objects (GPOs).</span></span>

## <span data-ttu-id="2762a-105">含變更控制的群組原則物件開發</span><span class="sxs-lookup"><span data-stu-id="2762a-105">Group Policy object development with change control</span></span>


<span data-ttu-id="2762a-106">使用 AGPM，您可以將每個 GPO 的複本儲存在中央封存中，這樣群組原則管理員就可以在離線時查看及修改它，而不會立即影響已部署的 GPO 版本。</span><span class="sxs-lookup"><span data-stu-id="2762a-106">With AGPM, you can store a copy of each GPO in a central archive, so Group Policy administrators can view and modify it offline without immediately impacting the deployed version of the GPO.</span></span> <span data-ttu-id="2762a-107">此外，AGPM 會在封存中儲存每個受控制 GPO 版本的複本，以便在需要時回滾到較舊的版本。</span><span class="sxs-lookup"><span data-stu-id="2762a-107">Additionally, AGPM stores a copy of each version of each controlled GPO in the archive so that you can roll back to an earlier version if needed.</span></span>

<span data-ttu-id="2762a-108">「取出」和「取出」一詞的用法與文件庫（或提供以程式設計開發的原始程式碼控制、版本控制或原始程式碼管理）中的方式幾乎相同。</span><span class="sxs-lookup"><span data-stu-id="2762a-108">The terms "check in" and "check out" are used in much the same way as in a library (or in applications that provide change control, version control, or source code control for programming development).</span></span> <span data-ttu-id="2762a-109">若要使用文件庫中的活頁簿，您可以從文件庫中取出該活頁簿。</span><span class="sxs-lookup"><span data-stu-id="2762a-109">To use a book that is in a library, you check it out from the library.</span></span> <span data-ttu-id="2762a-110">您已取出時，其他人都無法使用它。完成書籍之後，您可以將它存回文件庫，讓其他人可以使用。</span><span class="sxs-lookup"><span data-stu-id="2762a-110">No one else can use it while you have it checked out. When you are finished with the book, you check it back into the library, so others can use it.</span></span>

<span data-ttu-id="2762a-111">使用 AGPM 開發 Gpo 時：</span><span class="sxs-lookup"><span data-stu-id="2762a-111">When developing GPOs using AGPM:</span></span>

1.  <span data-ttu-id="2762a-112">建立新的受控 GPO 或控制先前不受管理的 GPO。</span><span class="sxs-lookup"><span data-stu-id="2762a-112">Create a new controlled GPO or control a previously uncontrolled GPO.</span></span>

2.  <span data-ttu-id="2762a-113">請取出該 GPO，讓您和您只能進行修改。</span><span class="sxs-lookup"><span data-stu-id="2762a-113">Check out the GPO, so you and only you can modify it.</span></span>

3.  <span data-ttu-id="2762a-114">編輯 GPO。</span><span class="sxs-lookup"><span data-stu-id="2762a-114">Edit the GPO.</span></span>

4.  <span data-ttu-id="2762a-115">核取已編輯的 GPO，讓其他人可以修改，或部署它。</span><span class="sxs-lookup"><span data-stu-id="2762a-115">Check in the edited GPO, so others can modify it, or so it can be deployed.</span></span>

5.  <span data-ttu-id="2762a-116">審閱變更。</span><span class="sxs-lookup"><span data-stu-id="2762a-116">Review the changes.</span></span>

6.  <span data-ttu-id="2762a-117">將 GPO 部署到生產環境。</span><span class="sxs-lookup"><span data-stu-id="2762a-117">Deploy the GPO to the production environment.</span></span>

## <span data-ttu-id="2762a-118">以角色為基礎的委派</span><span class="sxs-lookup"><span data-stu-id="2762a-118">Role-based delegation</span></span>


<span data-ttu-id="2762a-119">AGPM 提供全面且便於使用的以角色為基礎的委派。</span><span class="sxs-lookup"><span data-stu-id="2762a-119">AGPM provides comprehensive, easy-to-use role-based delegation.</span></span> <span data-ttu-id="2762a-120">網域層級許可權可讓 AGPM 管理員在不提供存取其他網域的情況下，提供個別網域的存取權。</span><span class="sxs-lookup"><span data-stu-id="2762a-120">Domain-level permissions allow AGPM Administrators to provide access to individual domains without providing access to other domains.</span></span> <span data-ttu-id="2762a-121">[GPO 式委派] 可讓 AGPM 系統管理員只允許存取特定的 Gpo。</span><span class="sxs-lookup"><span data-stu-id="2762a-121">GPO-based delegation enables AGPM Administrators to allow access only to specific GPOs.</span></span>

<span data-ttu-id="2762a-122">在 AGPM 中，有專門定義的角色： AGPM 系統管理員（完全控制）、審核者、編輯者和檢閱者。</span><span class="sxs-lookup"><span data-stu-id="2762a-122">Within AGPM, there are specifically defined roles: AGPM Administrator (Full Control), Approver, Editor, and Reviewer.</span></span> <span data-ttu-id="2762a-123">AGPM 系統管理員角色包含所有其他角色的許可權。</span><span class="sxs-lookup"><span data-stu-id="2762a-123">The AGPM Administrator role includes the permissions for all other roles.</span></span> <span data-ttu-id="2762a-124">根據預設，只有核准者具備將 Gpo 部署到生產環境的權力，保護環境不受較少經驗的編輯者無意間失誤的錯誤。</span><span class="sxs-lookup"><span data-stu-id="2762a-124">By default, only Approvers have the power to deploy GPOs to the production environment, protecting the environment from inadvertent mistakes by less experienced Editors.</span></span> <span data-ttu-id="2762a-125">而且根據預設，所有角色都包含檢閱者角色，因此能夠在報表中查看 GPO 設定。</span><span class="sxs-lookup"><span data-stu-id="2762a-125">Also by default, all roles include the Reviewer role and therefore the ability to view GPO settings in reports.</span></span> <span data-ttu-id="2762a-126">不過，AGPM 提供的 AGPM 系統管理員可以靈活地自訂 GPO 存取，以符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="2762a-126">However, AGPM provides an AGPM Administrator with the flexibility to customize GPO access to fit the needs of your organization.</span></span>

## <span data-ttu-id="2762a-127">多重群組原則系統管理員環境中的委派</span><span class="sxs-lookup"><span data-stu-id="2762a-127">Delegation in a multiple Group Policy administrator environment</span></span>


<span data-ttu-id="2762a-128">在多人對 Gpo 進行變更的環境中，AGPM 管理員會以群組或個人身分委派編輯者、核准者和檢閱者的許可權。</span><span class="sxs-lookup"><span data-stu-id="2762a-128">In an environment where multiple people make changes to GPOs, an AGPM Administrator delegates permission to Editors, Approvers, and Reviewers, either as groups or as individuals.</span></span> <span data-ttu-id="2762a-129">如需編輯者和核准者的一般 GPO 開發程式，請參閱[檢查清單：建立、編輯和部署 GPO](checklist-create-edit-and-deploy-a-gpo.md)。</span><span class="sxs-lookup"><span data-stu-id="2762a-129">For a typical GPO development process for an Editor and an Approver, see [Checklist: Create, Edit, and Deploy a GPO](checklist-create-edit-and-deploy-a-gpo.md).</span></span>

### <span data-ttu-id="2762a-130">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="2762a-130">Additional references</span></span>

-   [<span data-ttu-id="2762a-131">檢查清單︰建立、編輯及部署 GPO</span><span class="sxs-lookup"><span data-stu-id="2762a-131">Checklist: Create, Edit, and Deploy a GPO</span></span>](checklist-create-edit-and-deploy-a-gpo.md)

-   [<span data-ttu-id="2762a-132">執行 AGPM 系統管理員工作</span><span class="sxs-lookup"><span data-stu-id="2762a-132">Performing AGPM Administrator Tasks</span></span>](performing-agpm-administrator-tasks.md)

-   [<span data-ttu-id="2762a-133">執行編輯器工作</span><span class="sxs-lookup"><span data-stu-id="2762a-133">Performing Editor Tasks</span></span>](performing-editor-tasks.md)

-   [<span data-ttu-id="2762a-134">執行核准者工作</span><span class="sxs-lookup"><span data-stu-id="2762a-134">Performing Approver Tasks</span></span>](performing-approver-tasks.md)

-   [<span data-ttu-id="2762a-135">執行檢閱者工作</span><span class="sxs-lookup"><span data-stu-id="2762a-135">Performing Reviewer Tasks</span></span>](performing-reviewer-tasks.md)

-   [<span data-ttu-id="2762a-136">疑難排解進階群組原則管理</span><span class="sxs-lookup"><span data-stu-id="2762a-136">Troubleshooting Advanced Group Policy Management</span></span>](troubleshooting-advanced-group-policy-management.md)

-   [<span data-ttu-id="2762a-137">使用者介面：進階群組原則管理</span><span class="sxs-lookup"><span data-stu-id="2762a-137">User Interface: Advanced Group Policy Management</span></span>](user-interface-advanced-group-policy-management.md)

 

 





