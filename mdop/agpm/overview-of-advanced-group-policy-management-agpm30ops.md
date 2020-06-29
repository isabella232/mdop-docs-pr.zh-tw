---
title: 進階群組原則管理概觀
description: 進階群組原則管理概觀
author: dansimp
ms.assetid: 3a8d1e58-12b9-42bd-898f-6d57514dfbb9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: feb43972c78ed12501e372800c1f5ec19609477a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809387"
---
# <span data-ttu-id="e0af1-103">進階群組原則管理概觀</span><span class="sxs-lookup"><span data-stu-id="e0af1-103">Overview of Advanced Group Policy Management</span></span>


<span data-ttu-id="e0af1-104">您可以使用 [高級群組原則管理] （AGPM）來延伸群組原則管理主控台（GPMC）的功能，以提供完整的變更控制，以及改善群組原則物件（Gpo）的管理。</span><span class="sxs-lookup"><span data-stu-id="e0af1-104">You can use Advanced Group Policy Management (AGPM) to extend the capabilities of the Group Policy Management Console (GPMC) to provide comprehensive change control and improved management for Group Policy Objects (GPOs).</span></span>

## <span data-ttu-id="e0af1-105">含變更控制的群組原則物件開發</span><span class="sxs-lookup"><span data-stu-id="e0af1-105">Group Policy object development with change control</span></span>


<span data-ttu-id="e0af1-106">使用 AGPM，您可以將每個 GPO 的複本儲存在中央封存中，這樣群組原則管理員就可以在離線時查看並變更它，而不會立即影響已部署的 GPO 版本。</span><span class="sxs-lookup"><span data-stu-id="e0af1-106">With AGPM, you can store a copy of each GPO in a central archive so that Group Policy administrators can view and change it offline without immediately affecting the deployed version of the GPO.</span></span> <span data-ttu-id="e0af1-107">此外，AGPM 會在封存中儲存每個受控制 GPO 版本的複本，以便在必要時回滾到較舊的版本。</span><span class="sxs-lookup"><span data-stu-id="e0af1-107">Additionally, AGPM stores a copy of each version of each controlled GPO in the archive so that you can roll back to an earlier version if necessary.</span></span>

<span data-ttu-id="e0af1-108">「取出」和「取出」一詞，就如同在文件庫中（或在提供程式設計中提供變更控制、版本控制或來源控制）的應用程式中使用。</span><span class="sxs-lookup"><span data-stu-id="e0af1-108">The terms "check in" and "check out" are used just as in a library (or in applications that provide change control, version control, or source control for programming development).</span></span> <span data-ttu-id="e0af1-109">若要使用文件庫中的活頁簿，您可以從文件庫中取出該活頁簿。</span><span class="sxs-lookup"><span data-stu-id="e0af1-109">To use a book that is in a library, you check it out from the library.</span></span> <span data-ttu-id="e0af1-110">您已取出時，其他人都無法使用它。完成書籍之後，您可以將它存回文件庫，讓其他人可以使用。</span><span class="sxs-lookup"><span data-stu-id="e0af1-110">No one else can use it while you have it checked out. When you are finished with the book, you check it back into the library, so others can use it.</span></span>

<span data-ttu-id="e0af1-111">使用 AGPM 開發 Gpo 時：</span><span class="sxs-lookup"><span data-stu-id="e0af1-111">When you develop GPOs by using AGPM:</span></span>

1.  <span data-ttu-id="e0af1-112">建立新的受控 GPO 或控制先前不受管理的 GPO。</span><span class="sxs-lookup"><span data-stu-id="e0af1-112">Create a new controlled GPO or control a previously uncontrolled GPO.</span></span>

2.  <span data-ttu-id="e0af1-113">請取出該 GPO，讓您和您的使用者都能變更它。</span><span class="sxs-lookup"><span data-stu-id="e0af1-113">Check out the GPO, so that you and only you can change it.</span></span>

3.  <span data-ttu-id="e0af1-114">編輯 GPO。</span><span class="sxs-lookup"><span data-stu-id="e0af1-114">Edit the GPO.</span></span>

4.  <span data-ttu-id="e0af1-115">核取已編輯的 GPO，讓其他人可以變更，或進行部署。</span><span class="sxs-lookup"><span data-stu-id="e0af1-115">Check in the edited GPO, so that others can change it, or so that it can be deployed.</span></span>

5.  <span data-ttu-id="e0af1-116">審閱變更。</span><span class="sxs-lookup"><span data-stu-id="e0af1-116">Review the changes.</span></span>

6.  <span data-ttu-id="e0af1-117">將 GPO 部署到生產環境。</span><span class="sxs-lookup"><span data-stu-id="e0af1-117">Deploy the GPO to the production environment.</span></span>

## <span data-ttu-id="e0af1-118">以角色為基礎的委派</span><span class="sxs-lookup"><span data-stu-id="e0af1-118">Role-based delegation</span></span>


<span data-ttu-id="e0af1-119">AGPM 提供全面且便於使用的以角色為基礎的委派，可管理對封存中 Gpo 的存取權。</span><span class="sxs-lookup"><span data-stu-id="e0af1-119">AGPM provides comprehensive, easy-to-use role-based delegation for managing access to GPOs in the archive.</span></span> <span data-ttu-id="e0af1-120">網域層級許可權可讓 AGPM 管理員在不提供存取其他網域的情況下，提供個別網域的存取權。</span><span class="sxs-lookup"><span data-stu-id="e0af1-120">Domain-level permissions enable AGPM Administrators to provide access to individual domains without providing access to other domains.</span></span> <span data-ttu-id="e0af1-121">[GPO 式委派] 可讓 AGPM 管理員提供對特定 Gpo 的存取權，而不提供全域存取權。</span><span class="sxs-lookup"><span data-stu-id="e0af1-121">GPO-based delegation enables AGPM Administrators to provide access to specific GPOs without providing domain-wide access.</span></span>

<span data-ttu-id="e0af1-122">在 AGPM 中，有專門定義的角色： AGPM 系統管理員（完全控制）、審核者、編輯者和檢閱者。</span><span class="sxs-lookup"><span data-stu-id="e0af1-122">Within AGPM, there are specifically defined roles: AGPM Administrator (Full Control), Approver, Editor, and Reviewer.</span></span> <span data-ttu-id="e0af1-123">AGPM 系統管理員角色包含所有其他角色的許可權。</span><span class="sxs-lookup"><span data-stu-id="e0af1-123">The AGPM Administrator role includes the permissions for all other roles.</span></span> <span data-ttu-id="e0af1-124">根據預設，只有核准者具備將 Gpo 部署到生產環境的權力，保護環境不受較少經驗的編輯者所犯的錯誤。</span><span class="sxs-lookup"><span data-stu-id="e0af1-124">By default, only Approvers have the power to deploy GPOs to the production environment, protecting the environment from mistakes by less experienced Editors.</span></span> <span data-ttu-id="e0af1-125">而且根據預設，所有角色都包含檢閱者角色，因此能夠在報表中查看 GPO 設定。</span><span class="sxs-lookup"><span data-stu-id="e0af1-125">Also by default, all roles include the Reviewer role and therefore the ability to view GPO settings in reports.</span></span> <span data-ttu-id="e0af1-126">不過，AGPM 提供的 AGPM 系統管理員可以靈活地自訂 GPO 存取，以符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="e0af1-126">However, AGPM provides an AGPM Administrator with the flexibility to customize GPO access to fit the needs of your organization.</span></span>

## <span data-ttu-id="e0af1-127">多重群組原則系統管理員環境中的委派</span><span class="sxs-lookup"><span data-stu-id="e0af1-127">Delegation in a multiple Group Policy administrator environment</span></span>


<span data-ttu-id="e0af1-128">在多人變更 Gpo 的環境中，AGPM 管理員會以群組或個人身分委派編輯者、核准者和檢閱者的許可權。</span><span class="sxs-lookup"><span data-stu-id="e0af1-128">In an environment where multiple people change GPOs, an AGPM Administrator delegates permission to Editors, Approvers, and Reviewers, either as groups or as individuals.</span></span> <span data-ttu-id="e0af1-129">如需編輯者和核准者的一般 GPO 開發程式，請參閱[檢查清單：建立、編輯和部署 GPO](checklist-create-edit-and-deploy-a-gpo-agpm30ops.md)。</span><span class="sxs-lookup"><span data-stu-id="e0af1-129">For a typical GPO development process for an Editor and an Approver, see [Checklist: Create, Edit, and Deploy a GPO](checklist-create-edit-and-deploy-a-gpo-agpm30ops.md).</span></span>

### <span data-ttu-id="e0af1-130">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="e0af1-130">Additional references</span></span>

-   [<span data-ttu-id="e0af1-131">Microsoft 進階群組原則管理 3.0 操作指南</span><span class="sxs-lookup"><span data-stu-id="e0af1-131">Operations Guide for Microsoft Advanced Group Policy Management 3.0</span></span>](operations-guide-for-microsoft-advanced-group-policy-management-30-agpm30ops.md)

 

 





