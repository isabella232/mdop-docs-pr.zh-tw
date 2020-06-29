---
title: 執行 AGPM 系統管理員工作
description: 執行 AGPM 系統管理員工作
author: dansimp
ms.assetid: 9678b0f4-70a5-411e-a896-afa4dc9ea6c4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 26b412e5b22e46af938d127751fdca1da722a8c6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809345"
---
# <span data-ttu-id="f116d-103">執行 AGPM 系統管理員工作</span><span class="sxs-lookup"><span data-stu-id="f116d-103">Performing AGPM Administrator Tasks</span></span>


<span data-ttu-id="f116d-104">在 [高級群組原則管理] （AGPM）中，AGPM 系統管理員（完全控制）會設定全域性選項，並將許可權委派給核准者、編輯人員、檢閱者及其他 AGPM 管理員。</span><span class="sxs-lookup"><span data-stu-id="f116d-104">In Advanced Group Policy Management (AGPM), an AGPM Administrator (Full Control) configures domain-wide options and delegates permissions to Approvers, Editors, Reviewers, and other AGPM Administrators.</span></span> <span data-ttu-id="f116d-105">根據預設，AGPM 管理員是完全控制的個體（所有的 AGPM 許可權），因此誰可以執行與任何角色相關聯的工作。</span><span class="sxs-lookup"><span data-stu-id="f116d-105">By default, an AGPM Administrator is an individual with Full Control—all AGPM permissions—and who therefore can perform tasks associated with any role.</span></span>

<span data-ttu-id="f116d-106">在有多位人員開發群組原則物件（Gpo）的環境中，您可以選擇是否所有的 AGPM 使用者都執行相同的工作，以及是否擁有相同的存取層級，或者是否要讓 AGPM 系統管理員委派許可權來變更 Gpo，以及將 Gpo 部署到生產環境的核准者。</span><span class="sxs-lookup"><span data-stu-id="f116d-106">In an environment in which multiple people develop Group Policy Objects (GPOs), you can choose whether all AGPM users perform the same tasks and have the same level of access or whether AGPM Administrators delegate permissions to Editors who make changes to GPOs and to Approvers who deploy GPOs to the production environment.</span></span> <span data-ttu-id="f116d-107">AGPM 管理員可以設定許可權，以符合貴組織的需求。</span><span class="sxs-lookup"><span data-stu-id="f116d-107">AGPM Administrators can configure permissions to meet the needs of your organization.</span></span>

-   <span data-ttu-id="f116d-108">設定[高級的群組原則管理](configuring-advanced-group-policy-management.md)：設定 AGPM 服務器連線和電子郵件通知、委派在生產環境中 gpo 的存取權，以及設定記錄及追蹤以進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="f116d-108">[Configuring Advanced Group Policy Management](configuring-advanced-group-policy-management.md): Configure the AGPM Server Connection and e-mail notification, delegate access to GPOs in the production environment, and configure logging and tracing for troubleshooting.</span></span>

-   <span data-ttu-id="f116d-109">[管理](managing-the-archive.md)封存：委派對封存中 gpo 的存取權，並限制儲存的每個 GPO 版本數。</span><span class="sxs-lookup"><span data-stu-id="f116d-109">[Managing the Archive](managing-the-archive.md): Delegate access to GPOs in the archive and limit the number of versions of each GPO stored.</span></span>

-   <span data-ttu-id="f116d-110">[管理 Agpm 服務](managing-the-agpm-service-agpm30ops.md)：停止並啟動 agpm 服務，或變更您的 [agpm 服務] 帳戶，或 [Agpm] 服務所偵聽的埠。</span><span class="sxs-lookup"><span data-stu-id="f116d-110">[Managing the AGPM Service](managing-the-agpm-service-agpm30ops.md): Stop and start the AGPM Service or change the archive path, the AGPM Service Account, or the port on which the AGPM Service listens.</span></span>

-   <span data-ttu-id="f116d-111">[移動 Agpm 伺服器與](move-the-agpm-server-and-the-archive.md)封存：將 agpm 服務、封存或兩者移至不同的伺服器。</span><span class="sxs-lookup"><span data-stu-id="f116d-111">[Move the AGPM Server and the Archive](move-the-agpm-server-and-the-archive.md): Move the AGPM Service, the archive, or both to a different server.</span></span>

<span data-ttu-id="f116d-112">此外，因為 AGPM 系統管理員角色包含所有其他角色的許可權，所以 AGPM 管理員可以執行與其他任何角色相關聯的一般工作。</span><span class="sxs-lookup"><span data-stu-id="f116d-112">Also, because the AGPM Administrator role includes the permissions for all other roles, an AGPM Administrator can perform the tasks normally associated with any other role.</span></span>

-   <span data-ttu-id="f116d-113">[執行核准者](performing-approver-tasks-agpm30ops.md)工作，例如建立、部署或刪除 gpo</span><span class="sxs-lookup"><span data-stu-id="f116d-113">[Performing Approver Tasks](performing-approver-tasks-agpm30ops.md), such as creating, deploying, or deleting GPOs</span></span>

-   <span data-ttu-id="f116d-114">[執行編輯器](performing-editor-tasks-agpm30ops.md)工作，例如編輯、重新命名、標記或匯入 gpo、建立範本或設定預設範本</span><span class="sxs-lookup"><span data-stu-id="f116d-114">[Performing Editor Tasks](performing-editor-tasks-agpm30ops.md), such as editing, renaming, labeling, or importing GPOs, creating templates, or setting a default template</span></span>

-   <span data-ttu-id="f116d-115">[執行檢閱者](performing-reviewer-tasks-agpm30ops.md)工作，例如審閱設定及比較 gpo</span><span class="sxs-lookup"><span data-stu-id="f116d-115">[Performing Reviewer Tasks](performing-reviewer-tasks-agpm30ops.md), such as reviewing settings and comparing GPOs</span></span>

### <span data-ttu-id="f116d-116">其他考量</span><span class="sxs-lookup"><span data-stu-id="f116d-116">Additional considerations</span></span>

<span data-ttu-id="f116d-117">根據預設，AGPM 系統管理員角色擁有 [完全控制] 許可權（所有 AGPM 許可權）：</span><span class="sxs-lookup"><span data-stu-id="f116d-117">By default, the AGPM Administrator role has Full Control—all AGPM permissions:</span></span>

-   <span data-ttu-id="f116d-118">清單內容</span><span class="sxs-lookup"><span data-stu-id="f116d-118">List Contents</span></span>

-   <span data-ttu-id="f116d-119">讀取設定</span><span class="sxs-lookup"><span data-stu-id="f116d-119">Read Settings</span></span>

-   <span data-ttu-id="f116d-120">編輯設定</span><span class="sxs-lookup"><span data-stu-id="f116d-120">Edit Settings</span></span>

-   <span data-ttu-id="f116d-121">建立 GPO</span><span class="sxs-lookup"><span data-stu-id="f116d-121">Create GPO</span></span>

-   <span data-ttu-id="f116d-122">部署 GPO</span><span class="sxs-lookup"><span data-stu-id="f116d-122">Deploy GPO</span></span>

-   <span data-ttu-id="f116d-123">刪除 GPO</span><span class="sxs-lookup"><span data-stu-id="f116d-123">Delete GPO</span></span>

-   <span data-ttu-id="f116d-124">修改選項</span><span class="sxs-lookup"><span data-stu-id="f116d-124">Modify Options</span></span>

-   <span data-ttu-id="f116d-125">修改安全性</span><span class="sxs-lookup"><span data-stu-id="f116d-125">Modify Security</span></span>

-   <span data-ttu-id="f116d-126">建立範本</span><span class="sxs-lookup"><span data-stu-id="f116d-126">Create Template</span></span>

<span data-ttu-id="f116d-127">[**修改選項**] 和 [**修改安全**許可權] 對於 [AGPM 管理員] 的角色而言是唯一的。</span><span class="sxs-lookup"><span data-stu-id="f116d-127">The **Modify Options** and **Modify Security** permissions are unique to the role of AGPM Administrator.</span></span>

 

 





