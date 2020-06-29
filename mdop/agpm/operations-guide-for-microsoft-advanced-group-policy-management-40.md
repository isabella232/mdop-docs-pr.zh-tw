---
title: Microsoft 進階群組原則管理 4.0 操作指南
description: Microsoft 進階群組原則管理 4.0 操作指南
author: dansimp
ms.assetid: 0bafeba3-20a9-4360-be5d-03f786df11ee
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b51956c319f1b0a77e4a4bdf71090be4f322236e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802634"
---
# <span data-ttu-id="eea77-103">Microsoft 進階群組原則管理 4.0 操作指南</span><span class="sxs-lookup"><span data-stu-id="eea77-103">Operations Guide for Microsoft Advanced Group Policy Management 4.0</span></span>


<span data-ttu-id="eea77-104">您可以使用 Microsoft 高級群組原則管理（AGPM）來延伸群組原則管理主控台（GPMC）的功能。</span><span class="sxs-lookup"><span data-stu-id="eea77-104">You can use Microsoft Advanced Group Policy Management (AGPM) to extend the capabilities of the Group Policy Management Console (GPMC).</span></span> <span data-ttu-id="eea77-105">AGPM 可提供全面的變更控制及改良的群組原則物件（Gpo）管理。</span><span class="sxs-lookup"><span data-stu-id="eea77-105">AGPM provides comprehensive change control and improved management of Group Policy Objects (GPOs).</span></span>

<span data-ttu-id="eea77-106">使用 AGPM，您可以執行下列任務：</span><span class="sxs-lookup"><span data-stu-id="eea77-106">Using AGPM, you can do these tasks:</span></span>

-   <span data-ttu-id="eea77-107">離線編輯 Gpo，在將其部署到生產環境之前，您可以建立並測試這些 Gpo。</span><span class="sxs-lookup"><span data-stu-id="eea77-107">Perform offline editing of GPOs so that you can create and test them before you deploy them to a production environment.</span></span>

-   <span data-ttu-id="eea77-108">在中央封存中維護多個 GPO 版本，以便您可以在問題發生時回滾。</span><span class="sxs-lookup"><span data-stu-id="eea77-108">Maintain multiple versions of a GPO in a central archive so that you can roll back if a problem occurs.</span></span>

-   <span data-ttu-id="eea77-109">使用角色式委派，共同分擔在多個人員之間編輯、核准及審查 Gpo 的責任。</span><span class="sxs-lookup"><span data-stu-id="eea77-109">Share the responsibility for editing, approving, and reviewing GPOs among multiple people by using role-based delegation.</span></span>

-   <span data-ttu-id="eea77-110">利用 Gpo 的存回和取出功能，消除多個群組原則管理員覆寫另一個工作的危險。</span><span class="sxs-lookup"><span data-stu-id="eea77-110">Eliminate the danger of multiple Group Policy administrators overwriting one another's work by using the check-in and check-out capability for GPOs.</span></span>

-   <span data-ttu-id="eea77-111">使用差異報告分析 GPO 的變更，將變更與另一個 GPO 或同一個 GPO 的另一個版本進行比較。</span><span class="sxs-lookup"><span data-stu-id="eea77-111">Analyze changes to a GPO, comparing it to another GPO or another version of the same GPO by using difference reporting.</span></span>

-   <span data-ttu-id="eea77-112">使用 GPO 範本簡化建立新的 Gpo，儲存通用原則設定和喜好設定，以做為新 Gpo 的起點。</span><span class="sxs-lookup"><span data-stu-id="eea77-112">Simplify creating new GPOs by using GPO templates, storing common policy settings and preference settings to use as starting points for new GPOs.</span></span>

-   <span data-ttu-id="eea77-113">委派對生產環境的存取權。</span><span class="sxs-lookup"><span data-stu-id="eea77-113">Delegate access to the production environment.</span></span>

-   <span data-ttu-id="eea77-114">搜尋具有特定屬性的 Gpo，並篩選顯示的 Gpo 清單。</span><span class="sxs-lookup"><span data-stu-id="eea77-114">Search for GPOs with specific attributes and filter the list of GPOs displayed.</span></span>

-   <span data-ttu-id="eea77-115">將 GPO 匯出至檔案，讓您可以從測試林中的網域將它複製到生產目錄林中的網域。</span><span class="sxs-lookup"><span data-stu-id="eea77-115">Export a GPO to a file so that you can copy it from a domain in a test forest to a domain in a production forest.</span></span>

<span data-ttu-id="eea77-116">如果您在 gpmc 中顯示每個網域的 [歷程**記錄**] 索引標籤，則 AGPM 會新增 [**變更控制**] 資料夾，除了在 gpmc 中顯示的每個 GPO 和 [群群組原則] 連結。</span><span class="sxs-lookup"><span data-stu-id="eea77-116">AGPM adds a **Change Control** folder under each domain displayed in the GPMC, in addition to a **History** tab for each GPO and Group Policy link displayed in the GPMC.</span></span>

-   [<span data-ttu-id="eea77-117">進階群組原則管理概觀</span><span class="sxs-lookup"><span data-stu-id="eea77-117">Overview of Advanced Group Policy Management</span></span>](overview-of-advanced-group-policy-management-agpm40.md)

-   [<span data-ttu-id="eea77-118">版本控制最佳做法</span><span class="sxs-lookup"><span data-stu-id="eea77-118">Best Practices for Version Control</span></span>](best-practices-for-version-control-agpm40.md)

-   [<span data-ttu-id="eea77-119">檢查清單︰管理 AGPM 伺服器與封存</span><span class="sxs-lookup"><span data-stu-id="eea77-119">Checklist: Administer the AGPM Server and Archive</span></span>](checklist-administer-the-agpm-server-and-archive-agpm40.md)

-   [<span data-ttu-id="eea77-120">檢查清單︰建立、編輯及部署 GPO</span><span class="sxs-lookup"><span data-stu-id="eea77-120">Checklist: Create, Edit, and Deploy a GPO</span></span>](checklist-create-edit-and-deploy-a-gpo-agpm40.md)

-   [<span data-ttu-id="eea77-121">搜尋和篩選 GPO 清單</span><span class="sxs-lookup"><span data-stu-id="eea77-121">Search and Filter the List of GPOs</span></span>](search-and-filter-the-list-of-gpos.md)

-   [<span data-ttu-id="eea77-122">執行 AGPM 系統管理員工作</span><span class="sxs-lookup"><span data-stu-id="eea77-122">Performing AGPM Administrator Tasks</span></span>](performing-agpm-administrator-tasks-agpm40.md)

-   [<span data-ttu-id="eea77-123">執行編輯器工作</span><span class="sxs-lookup"><span data-stu-id="eea77-123">Performing Editor Tasks</span></span>](performing-editor-tasks-agpm40.md)

-   [<span data-ttu-id="eea77-124">執行核准者工作</span><span class="sxs-lookup"><span data-stu-id="eea77-124">Performing Approver Tasks</span></span>](performing-approver-tasks-agpm40.md)

-   [<span data-ttu-id="eea77-125">執行檢閱者工作</span><span class="sxs-lookup"><span data-stu-id="eea77-125">Performing Reviewer Tasks</span></span>](performing-reviewer-tasks-agpm40.md)

-   [<span data-ttu-id="eea77-126">疑難排解 AGPM</span><span class="sxs-lookup"><span data-stu-id="eea77-126">Troubleshooting AGPM</span></span>](troubleshooting-agpm-agpm40.md)

-   [<span data-ttu-id="eea77-127">使用者介面：進階群組原則管理</span><span class="sxs-lookup"><span data-stu-id="eea77-127">User Interface: Advanced Group Policy Management</span></span>](user-interface-advanced-group-policy-management-agpm40.md)

 

 





