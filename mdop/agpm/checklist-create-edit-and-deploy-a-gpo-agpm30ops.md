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
# 檢查清單︰建立、編輯及部署 GPO


在有多人使用高級群組原則管理（AGPM）變更群組原則物件（Gpo）的環境中，AGPM 管理員（完全控制）會以群組或個人身分委派對編輯者、核准者和檢閱者的許可權。 以下是針對編輯者和核准者的典型 GPO 開發程式。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">工作</th>
<th align="left">參考</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Editor 會要求建立新的 GPO，或核准者會建立新的 GPO。</p></td>
<td align="left"><p><a href="request-the-creation-of-a-new-controlled-gpo-agpm30ops.md" data-raw-source="[Request the Creation of a New Controlled GPO](request-the-creation-of-a-new-controlled-gpo-agpm30ops.md)">要求建立新的受控制 GPO</a></p>
<p><a href="create-a-new-controlled-gpo-agpm30ops.md" data-raw-source="[Create a New Controlled GPO](create-a-new-controlled-gpo-agpm30ops.md)">建立新的受控制 GPO</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>如果由編輯者要求，核准者會核准 GPO 的建立。</p></td>
<td align="left"><p><a href="approve-or-reject-a-pending-action-agpm30ops.md" data-raw-source="[Approve or Reject a Pending Action](approve-or-reject-a-pending-action-agpm30ops.md)">核准或拒絕擱置動作</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>[編輯工具] 會從封存中取出一個 GPO 複本，因此沒有其他人可以修改該 GPO。 編輯者會變更 GPO，然後將修改過的 GPO 檢查到封存中。</p></td>
<td align="left"><p><a href="edit-a-gpo-offline-agpm30ops.md" data-raw-source="[Edit a GPO Offline](edit-a-gpo-offline-agpm30ops.md)">離線編輯 GPO</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>[編輯] 會要求將 GPO 部署到生產環境。</p></td>
<td align="left"><p><a href="request-deployment-of-a-gpo-agpm30ops.md" data-raw-source="[Request Deployment of a GPO](request-deployment-of-a-gpo-agpm30ops.md)">要求部署 GPO</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>檢閱者（例如 [核准者] 或 [編輯]）會分析 GPO。</p></td>
<td align="left"><p><a href="performing-reviewer-tasks-agpm30ops.md" data-raw-source="[Performing Reviewer Tasks](performing-reviewer-tasks-agpm30ops.md)">執行檢閱者工作</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>核准者核准並將 GPO 部署到生產環境，或拒絕 GPO。</p></td>
<td align="left"><p><a href="approve-or-reject-a-pending-action-agpm30ops.md" data-raw-source="[Approve or Reject a Pending Action](approve-or-reject-a-pending-action-agpm30ops.md)">核准或拒絕擱置動作</a></p></td>
</tr>
</tbody>
</table>

 

### 其他參考資料

[Microsoft 進階群組原則管理 3.0 操作指南](operations-guide-for-microsoft-advanced-group-policy-management-30-agpm30ops.md)

 

 





