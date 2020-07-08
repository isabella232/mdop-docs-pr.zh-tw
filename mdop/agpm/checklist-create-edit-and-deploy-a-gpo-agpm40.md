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
# 檢查清單︰建立、編輯及部署 GPO


在多人使用 [高級群組原則管理（AGPM）] 變更群組原則物件（Gpo）的環境中，AGPM 管理員（完全控制）會以群組或個人身分代表編輯者、核准者和檢閱者的許可權。 以下是針對編輯者和核准者的典型 GPO 開發程式。

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
<td align="left"><p>[編輯] 會要求建立新的 GPO，或是核准者會建立新的 GPO。</p></td>
<td align="left"><p><a href="request-the-creation-of-a-new-controlled-gpo-agpm40.md" data-raw-source="[Request the Creation of a New Controlled GPO](request-the-creation-of-a-new-controlled-gpo-agpm40.md)">要求建立新的受控制 GPO</a></p>
<p><a href="create-a-new-controlled-gpo-agpm40.md" data-raw-source="[Create a New Controlled GPO](create-a-new-controlled-gpo-agpm40.md)">建立新的受控制 GPO</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>如果由編輯者要求，核准者會核准 GPO 的建立。</p></td>
<td align="left"><p><a href="approve-or-reject-a-pending-action-agpm40.md" data-raw-source="[Approve or Reject a Pending Action](approve-or-reject-a-pending-action-agpm40.md)">核准或拒絕擱置動作</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>[編輯工具] 會從封存中取出一個 GPO 複本，以免任何人都能修改該 GPO。 編輯者會變更 GPO，然後將修改過的 GPO 檢查到封存中。</p></td>
<td align="left"><p><a href="edit-a-gpo-offline-agpm40.md" data-raw-source="[Edit a GPO Offline](edit-a-gpo-offline-agpm40.md)">離線編輯 GPO</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>如果是在測試林中進行開發，編輯器會將 GPO 匯出至檔案、將檔案傳輸到生產目錄林，然後匯入檔案。 此外，編輯工具也可以將 GPO 連結到包含測試電腦和使用者的組織單位。</p></td>
<td align="left"><p><a href="using-a-test-environment.md" data-raw-source="[Using a Test Environment](using-a-test-environment.md)">使用測試環境</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>[編輯] 會要求將 GPO 部署到網域的生產環境。</p></td>
<td align="left"><p><a href="request-deployment-of-a-gpo-agpm40.md" data-raw-source="[Request Deployment of a GPO](request-deployment-of-a-gpo-agpm40.md)">要求部署 GPO</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>檢閱者（例如 [核准者] 或 [編輯]）會分析 GPO。</p></td>
<td align="left"><p><a href="performing-reviewer-tasks-agpm40.md" data-raw-source="[Performing Reviewer Tasks](performing-reviewer-tasks-agpm40.md)">執行檢閱者工作</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>核准者核准並將 GPO 部署至網域的生產環境，或拒絕 GPO。</p></td>
<td align="left"><p><a href="approve-or-reject-a-pending-action-agpm40.md" data-raw-source="[Approve or Reject a Pending Action](approve-or-reject-a-pending-action-agpm40.md)">核准或拒絕擱置動作</a></p></td>
</tr>
</tbody>
</table>

 

### 其他參考資料

[進階群組原則管理 4.0](advanced-group-policy-management-40.md)

 

 





