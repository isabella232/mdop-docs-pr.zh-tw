---
title: 檢查清單建立、編輯及部署 GPO
description: 檢查清單建立、編輯及部署 GPO
author: dansimp
ms.assetid: 44631bed-16d2-4b5a-af70-17a73fb5f6af
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7d8bea9109040aa81a20df62356ef1d307d5eac0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802082"
---
# <span data-ttu-id="812ad-103">檢查清單︰建立、編輯及部署 GPO</span><span class="sxs-lookup"><span data-stu-id="812ad-103">Checklist: Create, Edit, and Deploy a GPO</span></span>


<span data-ttu-id="812ad-104">在多人使用 [高級群組原則管理（AGPM）] 變更群組原則物件（Gpo）的環境中，AGPM 管理員（完全控制）會以群組或個人身分代表編輯者、核准者和檢閱者的許可權。</span><span class="sxs-lookup"><span data-stu-id="812ad-104">In an environment where multiple people change Group Policy Objects (GPOs) by using Advanced Group Policy Management (AGPM), an AGPM Administrator (Full Control) delegates permission to Editors, Approvers, and Reviewers either as groups or as individuals.</span></span> <span data-ttu-id="812ad-105">以下是針對編輯者和核准者的典型 GPO 開發程式。</span><span class="sxs-lookup"><span data-stu-id="812ad-105">The following is a typical GPO development process for an Editor and an Approver.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="812ad-106">工作</span><span class="sxs-lookup"><span data-stu-id="812ad-106">Task</span></span></th>
<th align="left"><span data-ttu-id="812ad-107">參考</span><span class="sxs-lookup"><span data-stu-id="812ad-107">Reference</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="812ad-108">[編輯] 會要求建立新的 GPO，或是核准者會建立新的 GPO。</span><span class="sxs-lookup"><span data-stu-id="812ad-108">Editor requests that a new GPO be created or an Approver creates a new GPO.</span></span></p></td>
<td align="left"><p><a href="request-the-creation-of-a-new-controlled-gpo-agpm40.md" data-raw-source="[Request the Creation of a New Controlled GPO](request-the-creation-of-a-new-controlled-gpo-agpm40.md)"><span data-ttu-id="812ad-109">要求建立新的受控制 GPO</span><span class="sxs-lookup"><span data-stu-id="812ad-109">Request the Creation of a New Controlled GPO</span></span></a></p>
<p><a href="create-a-new-controlled-gpo-agpm40.md" data-raw-source="[Create a New Controlled GPO](create-a-new-controlled-gpo-agpm40.md)"><span data-ttu-id="812ad-110">建立新的受控制 GPO</span><span class="sxs-lookup"><span data-stu-id="812ad-110">Create a New Controlled GPO</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="812ad-111">如果由編輯者要求，核准者會核准 GPO 的建立。</span><span class="sxs-lookup"><span data-stu-id="812ad-111">Approver approves the creation of the GPO if it was requested by an Editor.</span></span></p></td>
<td align="left"><p><a href="approve-or-reject-a-pending-action-agpm40.md" data-raw-source="[Approve or Reject a Pending Action](approve-or-reject-a-pending-action-agpm40.md)"><span data-ttu-id="812ad-112">核准或拒絕擱置動作</span><span class="sxs-lookup"><span data-stu-id="812ad-112">Approve or Reject a Pending Action</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="812ad-113">[編輯工具] 會從封存中取出一個 GPO 複本，以免任何人都能修改該 GPO。</span><span class="sxs-lookup"><span data-stu-id="812ad-113">Editor checks out a copy of the GPO from the archive so that no one else can modify the GPO.</span></span> <span data-ttu-id="812ad-114">編輯者會變更 GPO，然後將修改過的 GPO 檢查到封存中。</span><span class="sxs-lookup"><span data-stu-id="812ad-114">Editor makes changes to the GPO, and then checks the modified GPO into the archive.</span></span></p></td>
<td align="left"><p><a href="edit-a-gpo-offline-agpm40.md" data-raw-source="[Edit a GPO Offline](edit-a-gpo-offline-agpm40.md)"><span data-ttu-id="812ad-115">離線編輯 GPO</span><span class="sxs-lookup"><span data-stu-id="812ad-115">Edit a GPO Offline</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="812ad-116">如果是在測試林中進行開發，編輯器會將 GPO 匯出至檔案、將檔案傳輸到生產目錄林，然後匯入檔案。</span><span class="sxs-lookup"><span data-stu-id="812ad-116">If developing in a test forest, Editor exports the GPO to a file, transfers the file to the production forest, and imports the file.</span></span> <span data-ttu-id="812ad-117">此外，編輯工具也可以將 GPO 連結到包含測試電腦和使用者的組織單位。</span><span class="sxs-lookup"><span data-stu-id="812ad-117">Additionally, an Editor can link the GPO to an organizational unit that contains test computers and users.</span></span></p></td>
<td align="left"><p><a href="using-a-test-environment.md" data-raw-source="[Using a Test Environment](using-a-test-environment.md)"><span data-ttu-id="812ad-118">使用測試環境</span><span class="sxs-lookup"><span data-stu-id="812ad-118">Using a Test Environment</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="812ad-119">[編輯] 會要求將 GPO 部署到網域的生產環境。</span><span class="sxs-lookup"><span data-stu-id="812ad-119">Editor requests deployment of the GPO to the production environment of the domain.</span></span></p></td>
<td align="left"><p><a href="request-deployment-of-a-gpo-agpm40.md" data-raw-source="[Request Deployment of a GPO](request-deployment-of-a-gpo-agpm40.md)"><span data-ttu-id="812ad-120">要求部署 GPO</span><span class="sxs-lookup"><span data-stu-id="812ad-120">Request Deployment of a GPO</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="812ad-121">檢閱者（例如 [核准者] 或 [編輯]）會分析 GPO。</span><span class="sxs-lookup"><span data-stu-id="812ad-121">Reviewers, such as Approvers or Editors, analyze the GPO.</span></span></p></td>
<td align="left"><p><a href="performing-reviewer-tasks-agpm40.md" data-raw-source="[Performing Reviewer Tasks](performing-reviewer-tasks-agpm40.md)"><span data-ttu-id="812ad-122">執行檢閱者工作</span><span class="sxs-lookup"><span data-stu-id="812ad-122">Performing Reviewer Tasks</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="812ad-123">核准者核准並將 GPO 部署至網域的生產環境，或拒絕 GPO。</span><span class="sxs-lookup"><span data-stu-id="812ad-123">Approver approves and deploys the GPO to the production environment of the domain or rejects the GPO.</span></span></p></td>
<td align="left"><p><a href="approve-or-reject-a-pending-action-agpm40.md" data-raw-source="[Approve or Reject a Pending Action](approve-or-reject-a-pending-action-agpm40.md)"><span data-ttu-id="812ad-124">核准或拒絕擱置動作</span><span class="sxs-lookup"><span data-stu-id="812ad-124">Approve or Reject a Pending Action</span></span></a></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="812ad-125">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="812ad-125">Additional references</span></span>

[<span data-ttu-id="812ad-126">進階群組原則管理 4.0</span><span class="sxs-lookup"><span data-stu-id="812ad-126">Advanced Group Policy Management 4.0</span></span>](advanced-group-policy-management-40.md)

 

 





