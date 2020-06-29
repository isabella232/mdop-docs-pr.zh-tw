---
title: 網域委派索引標籤
description: 網域委派索引標籤
author: dansimp
ms.assetid: 15a9bfff-e25b-4b62-9ebc-521a5f4eae96
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d49083bcefe6c7edcb3a95dc63d2249826d50327
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801893"
---
# 網域委派索引標籤


[**變更控制**] 窗格上的 [**網域委派**] 索引標籤提供對封存擁有網域層級存取權的群群組原則管理員清單，並指出每個檔案的角色。 此外，這個索引標籤可讓 [AGPM 管理員] （完全控制）為編輯者、核准者、檢閱者及其他 AGPM 管理員設定網域層級許可權。 [**網域委派**] 索引標籤上有兩個區段，即設定電子郵件通知，以及網域層級的 [高級群組原則管理（AGPM）] 的 [以角色為基礎] 委派。

## 電子郵件通知的設定


此索引標籤的 [電子郵件通知] 區段會識別將在 AGPM 中掛起作業時收到通知的核准者。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">設定</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>從</strong></p></td>
<td align="left"><p>將通知傳送給核准者的 AGPM 別名。 在有多個網域的環境中，這可以是整個環境中的相同別名，或是每個網域的不同別名。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>以</strong></p></td>
<td align="left"><p>要傳送通知之核准者的電子郵件地址的逗號分隔清單</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>SMTP 伺服器</strong></p></td>
<td align="left"><p>電子郵件伺服器的名稱，例如 mail.contoso.com</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>使用者名稱</strong></p></td>
<td align="left"><p>擁有 SMTP 伺服器存取權的使用者</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>密碼</strong></p></td>
<td align="left"><p>SMTP 伺服器驗證的使用者密碼</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>確認密碼</strong></p></td>
<td align="left"><p>確認使用者的密碼</p></td>
</tr>
</tbody>
</table>

 

## 網域層級角色委派


此索引標籤的 [以角色為基礎的委派] 區段會顯示，並讓 AGPM 管理員針對網域上的每個群組和使用者委派允許、拒絕和繼承的許可權，並可存取封存。 AGPM 管理員可以使用標準的 AGPM 角色（[編輯者]、[核准者]、[審查員] 和 [AGPM 系統管理員]），或每個群組原則管理員的自訂許可權組合來設定全域許可權。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Button</th>
<th align="left">效果</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>新增</strong></p></td>
<td align="left"><p>在安全性說明符中加入新專案。 Active Directory 中的任何使用者或群組都可以新增為群組原則系統管理員。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>移除</strong></p></td>
<td align="left"><p>從 [存取控制] 清單中移除選取的 [群組原則管理員]。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>屬性</strong></p></td>
<td align="left"><p>顯示所選群組原則系統管理員的屬性。 [屬性] 頁面與 <strong> Active Directory 使用者和電腦中的物件所顯示的內容相同 </strong> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>進階</strong></p></td>
<td align="left"><p>開啟 [ <strong> 存取控制清單編輯器] </strong> 。</p></td>
</tr>
</tbody>
</table>

 

### 其他考量

-   如需有關特定工作的角色與許可權的相關資訊，請參閱[執行 AGPM 管理員](performing-agpm-administrator-tasks.md)工作、[執行編輯](performing-editor-tasks.md)程式工作、[執行核准者](performing-approver-tasks.md)工作及[執行審查員](performing-reviewer-tasks.md)工作中的工作。

### 其他參考資料

-   [使用者介面：進階群組原則管理](user-interface-advanced-group-policy-management.md)

-   [執行 AGPM 系統管理員工作](performing-agpm-administrator-tasks.md)

 

 





