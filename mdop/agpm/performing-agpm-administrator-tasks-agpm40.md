---
title: 執行 AGPM 系統管理員工作
description: 執行 AGPM 系統管理員工作
author: dansimp
ms.assetid: bc746f39-bdc9-4e2a-bc48-c3c7905de098
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 609b5b8b27fe24ff93e86bea7113929b1e04984d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809344"
---
# <span data-ttu-id="64bfd-103">執行 AGPM 系統管理員工作</span><span class="sxs-lookup"><span data-stu-id="64bfd-103">Performing AGPM Administrator Tasks</span></span>


<span data-ttu-id="64bfd-104">[高級群組原則管理] （AGPM）可讓 AGPM 系統管理員（完全控制）設定全域性選項，以及委派核准者、編輯者、檢閱者和 AGPM 管理員的許可權。</span><span class="sxs-lookup"><span data-stu-id="64bfd-104">Advanced Group Policy Management (AGPM) lets an AGPM Administrator (Full Control) configure domain-wide options and delegate permissions to Approvers, Editors, Reviewers, and AGPM Administrators.</span></span> <span data-ttu-id="64bfd-105">根據預設，AGPM 管理員是擁有 [完全控制] 許可權的人員，也就是誰可以執行與任何角色相關聯的工作。</span><span class="sxs-lookup"><span data-stu-id="64bfd-105">By default, an AGPM Administrator is someone who has Full Control— all AGPM permissions—and who therefore can perform tasks associated with any role.</span></span>

<span data-ttu-id="64bfd-106">在有多位人員開發群組原則物件（Gpo）的環境中，您可以選擇讓所有群組原則管理員執行相同的工作，並擁有相同的存取權等級。</span><span class="sxs-lookup"><span data-stu-id="64bfd-106">In an environment in which multiple people develop Group Policy Objects (GPOs), you can choose to let all Group Policy administrators perform the same tasks and have the same level of access.</span></span> <span data-ttu-id="64bfd-107">或者，您也可以選擇讓 AGPM 管理員委派許可權來編輯可以變更 Gpo 的人員，以及將 Gpo 部署到生產環境的核准者。</span><span class="sxs-lookup"><span data-stu-id="64bfd-107">Or, you can choose to let AGPM Administrators delegate permissions to Editors who can change GPOs and to Approvers who deploy GPOs to the production environment.</span></span> <span data-ttu-id="64bfd-108">AGPM 管理員可以設定許可權，以符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="64bfd-108">AGPM Administrators can configure permissions to meet the needs of your organization.</span></span>

-   <span data-ttu-id="64bfd-109">設定[高級的群組原則管理](configuring-advanced-group-policy-management-agpm40.md)：設定 AGPM 服務器連線和電子郵件通知、委派在生產環境中 gpo 的存取權，以及設定記錄及追蹤以進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="64bfd-109">[Configuring Advanced Group Policy Management](configuring-advanced-group-policy-management-agpm40.md): Configure the AGPM Server Connection and e-mail notification, delegate access to GPOs in the production environment, and configure logging and tracing for troubleshooting.</span></span>

-   <span data-ttu-id="64bfd-110">[管理](managing-the-archive-agpm40.md)封存：委派對封存中 gpo 的存取權、限制儲存的每個 gpo 版本數、從其他網域匯入 GPO，以及備份及還原封存。</span><span class="sxs-lookup"><span data-stu-id="64bfd-110">[Managing the Archive](managing-the-archive-agpm40.md): Delegate access to GPOs in the archive, limit the number of versions of each GPO stored, import a GPO from another domain, and back up and restore the archive.</span></span>

-   <span data-ttu-id="64bfd-111">[管理 Agpm 服務](managing-the-agpm-service-agpm40.md)：停止並啟動 agpm 服務，或變更您的 [agpm 服務] 帳戶，或 [Agpm] 服務所偵聽的埠。</span><span class="sxs-lookup"><span data-stu-id="64bfd-111">[Managing the AGPM Service](managing-the-agpm-service-agpm40.md): Stop and start the AGPM Service or change the archive path, the AGPM Service Account, or the port on which the AGPM Service listens.</span></span>

-   <span data-ttu-id="64bfd-112">[移動 Agpm 伺服器與](move-the-agpm-server-and-the-archive-agpm40.md)封存：將 agpm 服務、封存或兩者移至不同的伺服器。</span><span class="sxs-lookup"><span data-stu-id="64bfd-112">[Move the AGPM Server and the Archive](move-the-agpm-server-and-the-archive-agpm40.md): Move the AGPM Service, the archive, or both to a different server.</span></span>

<span data-ttu-id="64bfd-113">**記事** 因為 AGPM 系統管理員角色包含所有其他角色的許可權，所以 AGPM 管理員可以執行通常與其他任何角色相關聯的工作。</span><span class="sxs-lookup"><span data-stu-id="64bfd-113">**Note** Because the AGPM Administrator role includes the permissions for all other roles, an AGPM Administrator can perform the tasks usually associated with any other role.</span></span>

<span data-ttu-id="64bfd-114">[執行核准者](performing-approver-tasks-agpm40.md)工作，例如建立、部署或刪除 gpo</span><span class="sxs-lookup"><span data-stu-id="64bfd-114">[Performing Approver Tasks](performing-approver-tasks-agpm40.md), such as creating, deploying, or deleting GPOs</span></span>

<span data-ttu-id="64bfd-115">[執行編輯器](performing-editor-tasks-agpm40.md)工作，例如編輯、重新命名、標記或匯入 gpo、建立範本或設定預設範本</span><span class="sxs-lookup"><span data-stu-id="64bfd-115">[Performing Editor Tasks](performing-editor-tasks-agpm40.md), such as editing, renaming, labeling, or importing GPOs, creating templates, or setting a default template</span></span>

<span data-ttu-id="64bfd-116">[執行檢閱者](performing-reviewer-tasks-agpm40.md)工作，例如審閱設定及比較 gpo</span><span class="sxs-lookup"><span data-stu-id="64bfd-116">[Performing Reviewer Tasks](performing-reviewer-tasks-agpm40.md), such as reviewing settings and comparing GPOs</span></span>

 

### <span data-ttu-id="64bfd-117">其他考量</span><span class="sxs-lookup"><span data-stu-id="64bfd-117">Additional considerations</span></span>

<span data-ttu-id="64bfd-118">根據預設，AGPM 系統管理員角色擁有 [完全控制] 許可權（所有 AGPM 許可權）：</span><span class="sxs-lookup"><span data-stu-id="64bfd-118">By default, the AGPM Administrator role has Full Control—all AGPM permissions:</span></span>

-   <span data-ttu-id="64bfd-119">清單內容</span><span class="sxs-lookup"><span data-stu-id="64bfd-119">List Contents</span></span>

-   <span data-ttu-id="64bfd-120">讀取設定</span><span class="sxs-lookup"><span data-stu-id="64bfd-120">Read Settings</span></span>

-   <span data-ttu-id="64bfd-121">編輯設定</span><span class="sxs-lookup"><span data-stu-id="64bfd-121">Edit Settings</span></span>

-   <span data-ttu-id="64bfd-122">建立 GPO</span><span class="sxs-lookup"><span data-stu-id="64bfd-122">Create GPO</span></span>

-   <span data-ttu-id="64bfd-123">部署 GPO</span><span class="sxs-lookup"><span data-stu-id="64bfd-123">Deploy GPO</span></span>

-   <span data-ttu-id="64bfd-124">刪除 GPO</span><span class="sxs-lookup"><span data-stu-id="64bfd-124">Delete GPO</span></span>

-   <span data-ttu-id="64bfd-125">匯出 GPO</span><span class="sxs-lookup"><span data-stu-id="64bfd-125">Export GPO</span></span>

-   <span data-ttu-id="64bfd-126">匯入 GPO</span><span class="sxs-lookup"><span data-stu-id="64bfd-126">Import GPO</span></span>

-   <span data-ttu-id="64bfd-127">建立範本</span><span class="sxs-lookup"><span data-stu-id="64bfd-127">Create Template</span></span>

-   <span data-ttu-id="64bfd-128">修改選項</span><span class="sxs-lookup"><span data-stu-id="64bfd-128">Modify Options</span></span>

-   <span data-ttu-id="64bfd-129">修改安全性</span><span class="sxs-lookup"><span data-stu-id="64bfd-129">Modify Security</span></span>

<span data-ttu-id="64bfd-130">[**修改選項**] 和 [**修改安全**許可權] 對於 [AGPM 管理員] 的角色而言是唯一的。</span><span class="sxs-lookup"><span data-stu-id="64bfd-130">The **Modify Options** and **Modify Security** permissions are unique to the role of AGPM Administrator.</span></span>

 

 





