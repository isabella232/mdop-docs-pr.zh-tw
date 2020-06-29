---
title: 執行 AGPM 系統管理員工作
description: 執行 AGPM 系統管理員工作
author: dansimp
ms.assetid: 32e694a7-be64-4943-bce2-2a3a15e5341f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0daa8df93a88ed155e9f894011d4dd835761948b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802633"
---
# <span data-ttu-id="ec683-103">執行 AGPM 系統管理員工作</span><span class="sxs-lookup"><span data-stu-id="ec683-103">Performing AGPM Administrator Tasks</span></span>


<span data-ttu-id="ec683-104">AGPM 系統管理員（完全控制）可設定全域性選項，並將許可權委派給核准者、編輯人員、檢閱者及其他 AGPM 系統管理員。</span><span class="sxs-lookup"><span data-stu-id="ec683-104">An AGPM Administrator (Full Control) configures domain-wide options and delegates permissions to Approvers, Editors, Reviewers, and other AGPM Administrators.</span></span> <span data-ttu-id="ec683-105">根據預設，AGPM 管理員是完全控制的個體（所有高級群組原則管理 \ [AGPM \] 許可權），因此也可以執行與任何角色相關聯的工作。</span><span class="sxs-lookup"><span data-stu-id="ec683-105">By default, an AGPM Administrator is an individual with Full Control (all Advanced Group Policy Management \[AGPM\] permissions) and therefore can also perform tasks associated with any role.</span></span>

<span data-ttu-id="ec683-106">在有多位人員開發群組原則物件（Gpo）的環境中，您可以選擇所有高級群組原則管理（AGPM）使用者是否執行相同的工作，以及是否具有相同的存取權，或是 AGPM 管理員委派許可權給編輯者，以及將 Gpo 部署到生產環境的核准者。</span><span class="sxs-lookup"><span data-stu-id="ec683-106">In an environment in which multiple people develop Group Policy objects (GPOs), you can choose whether all Advanced Group Policy Management (AGPM) users perform the same tasks and have the same level of access or whether AGPM Administrators delegate permissions to Editors who make changes to GPOs and to Approvers who deploy GPOs to the production environment.</span></span> <span data-ttu-id="ec683-107">AGPM 管理員可以設定許可權，以符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="ec683-107">AGPM Administrators can configure permissions to meet the needs of your organization.</span></span>

-   [<span data-ttu-id="ec683-108">設定 AGPM 伺服器連線</span><span class="sxs-lookup"><span data-stu-id="ec683-108">Configure the AGPM Server Connection</span></span>](configure-the-agpm-server-connection.md)

-   [<span data-ttu-id="ec683-109">設定電子郵件通知</span><span class="sxs-lookup"><span data-stu-id="ec683-109">Configure E-Mail Notification</span></span>](configure-e-mail-notification.md)

-   [<span data-ttu-id="ec683-110">委派管理網域層級存取權</span><span class="sxs-lookup"><span data-stu-id="ec683-110">Delegate Domain-Level Access</span></span>](delegate-domain-level-access.md)

-   [<span data-ttu-id="ec683-111">委派管理個別 GPO 的存取權</span><span class="sxs-lookup"><span data-stu-id="ec683-111">Delegate Access to an Individual GPO</span></span>](delegate-access-to-an-individual-gpo.md)

-   [<span data-ttu-id="ec683-112">設定記錄和追蹤</span><span class="sxs-lookup"><span data-stu-id="ec683-112">Configure Logging and Tracing</span></span>](configure-logging-and-tracing.md)

-   [<span data-ttu-id="ec683-113">管理 AGPM 服務</span><span class="sxs-lookup"><span data-stu-id="ec683-113">Managing the AGPM Service</span></span>](managing-the-agpm-service.md)

    -   [<span data-ttu-id="ec683-114">啟動和停止 AGPM 服務</span><span class="sxs-lookup"><span data-stu-id="ec683-114">Start and Stop the AGPM Service</span></span>](start-and-stop-the-agpm-service.md)

    -   [<span data-ttu-id="ec683-115">修改封存路徑</span><span class="sxs-lookup"><span data-stu-id="ec683-115">Modify the Archive Path</span></span>](modify-the-archive-path.md)

    -   [<span data-ttu-id="ec683-116">修改 AGPM 服務帳戶</span><span class="sxs-lookup"><span data-stu-id="ec683-116">Modify the AGPM Service Account</span></span>](modify-the-agpm-service-account.md)

    -   [<span data-ttu-id="ec683-117">修改 AGPM 服務接聽的連接埠</span><span class="sxs-lookup"><span data-stu-id="ec683-117">Modify the Port on Which the AGPM Service Listens</span></span>](modify-the-port-on-which-the-agpm-service-listens.md)

<span data-ttu-id="ec683-118">此外，因為 AGPM 系統管理員角色包含所有其他角色的許可權，所以 AGPM 管理員可以執行與其他任何角色相關聯的一般工作。</span><span class="sxs-lookup"><span data-stu-id="ec683-118">Also, because the AGPM Administrator role includes the permissions for all other roles, an AGPM Administrator can perform the tasks normally associated with any other role.</span></span>

-   <span data-ttu-id="ec683-119">[執行核准者](performing-approver-tasks.md)工作，例如建立、部署或刪除 gpo</span><span class="sxs-lookup"><span data-stu-id="ec683-119">[Performing Approver Tasks](performing-approver-tasks.md), such as creating, deploying, or deleting GPOs</span></span>

-   <span data-ttu-id="ec683-120">[執行編輯器](performing-editor-tasks.md)工作，例如編輯、重新命名、標記或匯入 gpo、建立範本或設定預設範本</span><span class="sxs-lookup"><span data-stu-id="ec683-120">[Performing Editor Tasks](performing-editor-tasks.md), such as editing, renaming, labeling, or importing GPOs, creating templates, or setting a default template</span></span>

-   <span data-ttu-id="ec683-121">[執行檢閱者](performing-reviewer-tasks.md)工作，例如審閱設定及比較 gpo</span><span class="sxs-lookup"><span data-stu-id="ec683-121">[Performing Reviewer Tasks](performing-reviewer-tasks.md), such as reviewing settings and comparing GPOs</span></span>

### <span data-ttu-id="ec683-122">其他考量</span><span class="sxs-lookup"><span data-stu-id="ec683-122">Additional considerations</span></span>

<span data-ttu-id="ec683-123">根據預設，AGPM 系統管理員角色擁有 [完全控制] 許可權（所有 AGPM 許可權）：</span><span class="sxs-lookup"><span data-stu-id="ec683-123">By default, the AGPM Administrator role has Full Control—all AGPM permissions:</span></span>

-   <span data-ttu-id="ec683-124">清單內容</span><span class="sxs-lookup"><span data-stu-id="ec683-124">List Contents</span></span>

-   <span data-ttu-id="ec683-125">讀取設定</span><span class="sxs-lookup"><span data-stu-id="ec683-125">Read Settings</span></span>

-   <span data-ttu-id="ec683-126">編輯設定</span><span class="sxs-lookup"><span data-stu-id="ec683-126">Edit Settings</span></span>

-   <span data-ttu-id="ec683-127">建立 GPO</span><span class="sxs-lookup"><span data-stu-id="ec683-127">Create GPO</span></span>

-   <span data-ttu-id="ec683-128">部署 GPO</span><span class="sxs-lookup"><span data-stu-id="ec683-128">Deploy GPO</span></span>

-   <span data-ttu-id="ec683-129">刪除 GPO</span><span class="sxs-lookup"><span data-stu-id="ec683-129">Delete GPO</span></span>

-   <span data-ttu-id="ec683-130">修改選項</span><span class="sxs-lookup"><span data-stu-id="ec683-130">Modify Options</span></span>

-   <span data-ttu-id="ec683-131">修改安全性</span><span class="sxs-lookup"><span data-stu-id="ec683-131">Modify Security</span></span>

-   <span data-ttu-id="ec683-132">建立範本</span><span class="sxs-lookup"><span data-stu-id="ec683-132">Create Template</span></span>

<span data-ttu-id="ec683-133">[**修改選項**] 和 [**修改安全**許可權] 對於 [AGPM 管理員] 的角色而言是唯一的。</span><span class="sxs-lookup"><span data-stu-id="ec683-133">The **Modify Options** and **Modify Security** permissions are unique to the role of AGPM Administrator.</span></span>

 

 





