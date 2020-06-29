---
title: 檢查清單建立、編輯及部署 GPO
description: 檢查清單建立、編輯及部署 GPO
author: dansimp
ms.assetid: a7a17706-304a-4455-9ada-52508ec620f1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 35255926ba2384e2942900fc30eae06a30049a15
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802085"
---
# <span data-ttu-id="1123c-103">檢查清單︰建立、編輯及部署 GPO</span><span class="sxs-lookup"><span data-stu-id="1123c-103">Checklist: Create, Edit, and Deploy a GPO</span></span>


<span data-ttu-id="1123c-104">在有多人使用高級群組原則管理（AGPM）變更群組原則物件（Gpo）的環境中，AGPM 管理員（完全控制）會以群組或個人身分委派對編輯者、核准者和檢閱者的許可權。</span><span class="sxs-lookup"><span data-stu-id="1123c-104">In an environment where multiple people make changes to Group Policy Objects (GPOs) using Advanced Group Policy Management (AGPM), an AGPM Administrator (Full Control) delegates permission to Editors, Approvers, and Reviewers, either as groups or as individuals.</span></span> <span data-ttu-id="1123c-105">以下是針對編輯者和核准者的典型 GPO 開發程式。</span><span class="sxs-lookup"><span data-stu-id="1123c-105">The following is a typical GPO development process for an Editor and an Approver.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="1123c-106">工作</span><span class="sxs-lookup"><span data-stu-id="1123c-106">Task</span></span></th>
<th align="left"><span data-ttu-id="1123c-107">參考</span><span class="sxs-lookup"><span data-stu-id="1123c-107">Reference</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1123c-108">Editor 會要求建立新的 GPO，或核准者會建立新的 GPO。</span><span class="sxs-lookup"><span data-stu-id="1123c-108">Editor requests the creation of a new GPO or an Approver creates a new GPO.</span></span></p></td>
<td align="left"><p><a href="request-the-creation-of-a-new-controlled-gpo-agpm30ops.md" data-raw-source="[Request the Creation of a New Controlled GPO](request-the-creation-of-a-new-controlled-gpo-agpm30ops.md)"><span data-ttu-id="1123c-109">要求建立新的受控制 GPO</span><span class="sxs-lookup"><span data-stu-id="1123c-109">Request the Creation of a New Controlled GPO</span></span></a></p>
<p><a href="create-a-new-controlled-gpo-agpm30ops.md" data-raw-source="[Create a New Controlled GPO](create-a-new-controlled-gpo-agpm30ops.md)"><span data-ttu-id="1123c-110">建立新的受控制 GPO</span><span class="sxs-lookup"><span data-stu-id="1123c-110">Create a New Controlled GPO</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1123c-111">如果由編輯者要求，核准者會核准 GPO 的建立。</span><span class="sxs-lookup"><span data-stu-id="1123c-111">Approver approves the creation of the GPO if it was requested by an Editor.</span></span></p></td>
<td align="left"><p><a href="approve-or-reject-a-pending-action-agpm30ops.md" data-raw-source="[Approve or Reject a Pending Action](approve-or-reject-a-pending-action-agpm30ops.md)"><span data-ttu-id="1123c-112">核准或拒絕擱置動作</span><span class="sxs-lookup"><span data-stu-id="1123c-112">Approve or Reject a Pending Action</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1123c-113">[編輯工具] 會從封存中取出一個 GPO 複本，因此沒有其他人可以修改該 GPO。</span><span class="sxs-lookup"><span data-stu-id="1123c-113">Editor checks out a copy of the GPO from the archive, so no one else can modify the GPO.</span></span> <span data-ttu-id="1123c-114">編輯者會變更 GPO，然後將修改過的 GPO 檢查到封存中。</span><span class="sxs-lookup"><span data-stu-id="1123c-114">Editor makes changes to the GPO, and then checks the modified GPO into the archive.</span></span></p></td>
<td align="left"><p><a href="edit-a-gpo-offline-agpm30ops.md" data-raw-source="[Edit a GPO Offline](edit-a-gpo-offline-agpm30ops.md)"><span data-ttu-id="1123c-115">離線編輯 GPO</span><span class="sxs-lookup"><span data-stu-id="1123c-115">Edit a GPO Offline</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1123c-116">[編輯] 會要求將 GPO 部署到生產環境。</span><span class="sxs-lookup"><span data-stu-id="1123c-116">Editor requests deployment of the GPO to the production environment.</span></span></p></td>
<td align="left"><p><a href="request-deployment-of-a-gpo-agpm30ops.md" data-raw-source="[Request Deployment of a GPO](request-deployment-of-a-gpo-agpm30ops.md)"><span data-ttu-id="1123c-117">要求部署 GPO</span><span class="sxs-lookup"><span data-stu-id="1123c-117">Request Deployment of a GPO</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1123c-118">檢閱者（例如 [核准者] 或 [編輯]）會分析 GPO。</span><span class="sxs-lookup"><span data-stu-id="1123c-118">Reviewers, such as Approvers or Editors, analyze the GPO.</span></span></p></td>
<td align="left"><p><a href="performing-reviewer-tasks-agpm30ops.md" data-raw-source="[Performing Reviewer Tasks](performing-reviewer-tasks-agpm30ops.md)"><span data-ttu-id="1123c-119">執行檢閱者工作</span><span class="sxs-lookup"><span data-stu-id="1123c-119">Performing Reviewer Tasks</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1123c-120">核准者核准並將 GPO 部署到生產環境，或拒絕 GPO。</span><span class="sxs-lookup"><span data-stu-id="1123c-120">Approver approves and deploys the GPO to the production environment or rejects the GPO.</span></span></p></td>
<td align="left"><p><a href="approve-or-reject-a-pending-action-agpm30ops.md" data-raw-source="[Approve or Reject a Pending Action](approve-or-reject-a-pending-action-agpm30ops.md)"><span data-ttu-id="1123c-121">核准或拒絕擱置動作</span><span class="sxs-lookup"><span data-stu-id="1123c-121">Approve or Reject a Pending Action</span></span></a></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="1123c-122">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="1123c-122">Additional references</span></span>

[<span data-ttu-id="1123c-123">Microsoft 進階群組原則管理 3.0 操作指南</span><span class="sxs-lookup"><span data-stu-id="1123c-123">Operations Guide for Microsoft Advanced Group Policy Management 3.0</span></span>](operations-guide-for-microsoft-advanced-group-policy-management-30-agpm30ops.md)

 

 





