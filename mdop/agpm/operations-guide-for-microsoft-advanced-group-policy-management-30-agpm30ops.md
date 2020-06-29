---
title: Microsoft 進階群組原則管理 3.0 操作指南
description: Microsoft 進階群組原則管理 3.0 操作指南
author: dansimp
ms.assetid: aaefe6d1-a9e5-43eb-b4d8-85880798cb8b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4958609444a62560060a565fb8626bcc9680fd9e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809398"
---
# <span data-ttu-id="5cf56-103">Microsoft 進階群組原則管理 3.0 操作指南</span><span class="sxs-lookup"><span data-stu-id="5cf56-103">Operations Guide for Microsoft Advanced Group Policy Management 3.0</span></span>


<span data-ttu-id="5cf56-104">您可以使用 Microsoft 高級群組原則管理（AGPM）來延伸群組原則管理主控台（GPMC）的功能，為群組原則物件（Gpo）提供全面的變更控制與增強的管理。</span><span class="sxs-lookup"><span data-stu-id="5cf56-104">You can use Microsoft Advanced Group Policy Management (AGPM) to extend the capabilities of the Group Policy Management Console (GPMC), providing comprehensive change control and enhanced management for Group Policy Objects (GPOs).</span></span>

<span data-ttu-id="5cf56-105">有了 AGPM，您就可以：</span><span class="sxs-lookup"><span data-stu-id="5cf56-105">With AGPM you can:</span></span>

-   <span data-ttu-id="5cf56-106">離線編輯 Gpo，因此您可以在部署到生產環境之前建立並測試 Gpo。</span><span class="sxs-lookup"><span data-stu-id="5cf56-106">Perform offline editing of GPOs, so you can create and test them before deploying to a production environment.</span></span>

-   <span data-ttu-id="5cf56-107">在中央封存中保留多個 GPO 版本，因此您可以在問題發生時回滾。</span><span class="sxs-lookup"><span data-stu-id="5cf56-107">Retain multiple versions of a GPO in a central archive, so you can roll back if a problem occurs.</span></span>

-   <span data-ttu-id="5cf56-108">使用角色委派，分享在多個人員之間編輯、核准及審查 Gpo 的責任。</span><span class="sxs-lookup"><span data-stu-id="5cf56-108">Share the responsibility for editing, approving, and reviewing GPOs among multiple people using role-based delegation.</span></span>

-   <span data-ttu-id="5cf56-109">利用 Gpo 的存回/取出功能，消除多個群組原則管理員覆寫對方工作的危險。</span><span class="sxs-lookup"><span data-stu-id="5cf56-109">Eliminate the danger of multiple Group Policy administrators overwriting each other's work by using a check-in/check-out capability for GPOs.</span></span>

-   <span data-ttu-id="5cf56-110">分析對 GPO 所做的變更，並將它與另一個 GPO 或同一個 GPO 的另一個版本（使用差異報告）進行比較。</span><span class="sxs-lookup"><span data-stu-id="5cf56-110">Analyze changes to a GPO, comparing it to another GPO or another version of the same GPO using difference reporting.</span></span>

-   <span data-ttu-id="5cf56-111">透過使用 GPO 範本來簡化新 Gpo 的建立，儲存要做為新 Gpo 起點的標準設定。</span><span class="sxs-lookup"><span data-stu-id="5cf56-111">Simplify the creation of new GPOs by using GPO templates, storing standard settings to use as starting points for new GPOs.</span></span>

<span data-ttu-id="5cf56-112">AGPM 會在 GPMC 中顯示的每個網域下，新增**變更控制**資料夾，以及在 gpmc 中顯示的每個 GPO 與 [群組原則] 連結的 [歷程**記錄**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="5cf56-112">AGPM adds a **Change Control** folder under each domain displayed in the GPMC, as well as a **History** tab for each GPO and Group Policy link displayed in the GPMC.</span></span>

-   [<span data-ttu-id="5cf56-113">進階群組原則管理概觀</span><span class="sxs-lookup"><span data-stu-id="5cf56-113">Overview of Advanced Group Policy Management</span></span>](overview-of-advanced-group-policy-management-agpm30ops.md)

-   [<span data-ttu-id="5cf56-114">版本控制最佳做法</span><span class="sxs-lookup"><span data-stu-id="5cf56-114">Best Practices for Version Control</span></span>](best-practices-for-version-control.md)

-   [<span data-ttu-id="5cf56-115">檢查清單︰管理 AGPM 伺服器與封存</span><span class="sxs-lookup"><span data-stu-id="5cf56-115">Checklist: Administer the AGPM Server and Archive</span></span>](checklist-administer-the-agpm-server-and-archive.md)

-   [<span data-ttu-id="5cf56-116">檢查清單︰建立、編輯及部署 GPO</span><span class="sxs-lookup"><span data-stu-id="5cf56-116">Checklist: Create, Edit, and Deploy a GPO</span></span>](checklist-create-edit-and-deploy-a-gpo-agpm30ops.md)

-   [<span data-ttu-id="5cf56-117">執行 AGPM 系統管理員工作</span><span class="sxs-lookup"><span data-stu-id="5cf56-117">Performing AGPM Administrator Tasks</span></span>](performing-agpm-administrator-tasks-agpm30ops.md)

-   [<span data-ttu-id="5cf56-118">執行編輯器工作</span><span class="sxs-lookup"><span data-stu-id="5cf56-118">Performing Editor Tasks</span></span>](performing-editor-tasks-agpm30ops.md)

-   [<span data-ttu-id="5cf56-119">執行核准者工作</span><span class="sxs-lookup"><span data-stu-id="5cf56-119">Performing Approver Tasks</span></span>](performing-approver-tasks-agpm30ops.md)

-   [<span data-ttu-id="5cf56-120">執行檢閱者工作</span><span class="sxs-lookup"><span data-stu-id="5cf56-120">Performing Reviewer Tasks</span></span>](performing-reviewer-tasks-agpm30ops.md)

-   [<span data-ttu-id="5cf56-121">疑難排解進階群組原則管理</span><span class="sxs-lookup"><span data-stu-id="5cf56-121">Troubleshooting Advanced Group Policy Management</span></span>](troubleshooting-advanced-group-policy-management-agpm30ops.md)

-   [<span data-ttu-id="5cf56-122">使用者介面：進階群組原則管理</span><span class="sxs-lookup"><span data-stu-id="5cf56-122">User Interface: Advanced Group Policy Management</span></span>](user-interface-advanced-group-policy-management-agpm30ops.md)

 

 





