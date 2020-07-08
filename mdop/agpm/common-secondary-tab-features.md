---
title: 常見的次要索引標籤功能
description: 常見的次要索引標籤功能
author: dansimp
ms.assetid: 44a15c28-944c-49c1-8534-115ce1c362ed
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 546fd4c91e060a5595b6c848015290882de933b6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802077"
---
# 常見的次要索引標籤功能


每個次要索引標籤有兩個區段： [**群組原則] 物件**與 [群組]**和 [使用者**

## [群組原則物件] 區段


[**群組原則物件**] 區段會顯示群組原則物件（gpo）的篩選清單，並識別每個 GPO 的下列特性：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">GPO 特性</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>Name</strong></p></td>
<td align="left"><p>群組原則物件的名稱。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>電腦（Comp）</strong></p></td>
<td align="left"><p>GPO 的電腦設定部分自動產生的版本。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>使用者</strong></p></td>
<td align="left"><p>GPO 的使用者設定部分的自動產生版本。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>狀態</strong></p></td>
<td align="left"><p>所選 GPO 的狀態：</p>
<p><img src="images/36f6b687-f5cc-40d1-805f-b191d1fb1ace.gif" alt="Deployed GPO icon" /> <strong>無法控制： </strong> 不由 AGPM 管理。</p>
<p><img src="images/57b610a5-1c71-4d26-9173-d04abd495fcc.gif" alt="Checked in GPO icon" /> <strong>已檢入： </strong> 適用于授權編輯者取出編輯或供群組原則管理員部署。</p>
<p><img src="images/8e7a7c4e-809a-435a-8b29-30d797936210.gif" alt="Checked out GPO icon" /> <strong>已取出： </strong> 目前正在進行編輯。 無法供其他編輯工具取出，直到已取出的編輯者或 AGPM 系統管理員將其檢入為止。</p>
<p><img src="images/0840a6a3-54a6-4528-98a9-7b122243c1a5.gif" alt="Pending GPO icon" /> <strong>擱置：在 </strong> 建立、控制、部署或刪除群組原則管理員之前，請先等待該群群組原則管理員的核准。</p>
<p><img src="images/57b610a5-1c71-4d26-9173-d04abd495fcc.gif" alt="Checked in GPO icon" /> <strong>已刪除： </strong> 已從封存中刪除，但仍可還原。</p>
<p><img src="images/9b65829d-253c-4f30-9295-c816a6521ed2.gif" alt="Template icon" /> <strong>範本： </strong> GPO 的靜態版本，可在建立新 gpo 時做為起點使用。</p>
<p><img src="images/cd349b8d-c4d8-45ff-b17f-7db882502c58.gif" alt="Default template icon" /> <strong>範本（預設）： </strong> 根據預設，此範本是建立新 GPO 時所使用的起始點。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>GPO 狀態</strong></p></td>
<td align="left"><p>您可以個別管理電腦配置和使用者設定。 GPO 狀態表示已啟用 GPO 的哪些部分。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>WMI 篩選器</strong></p></td>
<td align="left"><p>顯示適用于此 GPO 的任何 WMI 篩選器。 WMI 篩選是在 GPMC 的 [wmi 篩選器] 節點下管理，在 <strong> </strong> GPMC 的主控台樹中是在該網域。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>修改日期</strong></p></td>
<td align="left"><p>針對受控制的 GPO，是在修改或取出後將其簽核至修改之後的最近日期。 如果是不受控制的 GPO，就是上次修改的日期。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>擁有者</strong></p></td>
<td align="left"><p>已檢入或部署所選 GPO 之核准者的編輯者。</p></td>
</tr>
</tbody>
</table>

 

## [群組與使用者] 區段


選取 GPO 時，[**群組與使用者**] 區段會顯示群組和使用者有權存取該 gpo 的清單。 針對每個群組或使用者顯示允許的許可權和繼承。 AGPM 管理員可以使用標準 AGPM 角色（[編輯者]、[核准者] 和 [審查員]）或自訂的許可權組合來設定許可權。

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
<td align="left"><p>在安全性說明符中加入新專案。 您可以新增 Active Directory 中的任何使用者或群組。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>移除</strong></p></td>
<td align="left"><p>從 [存取控制] 清單中移除選取的專案。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>屬性</strong></p></td>
<td align="left"><p>顯示所選物件的屬性。 [屬性] 頁面與 <strong> Active Directory 使用者和電腦中的物件所顯示的內容相同 </strong> 。</p></td>
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

-   [內容索引標籤](contents-tab.md)

 

 





