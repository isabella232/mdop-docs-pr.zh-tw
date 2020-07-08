---
title: 內容索引標籤功能
description: 內容索引標籤功能
author: dansimp
ms.assetid: 725f025a-c30a-4d07-add1-4e0ed9a1a5fd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f64aad16a3335d78641812121692f6d5f6436ee1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802005"
---
# 內容索引標籤功能


[**內容**] 索引標籤內的每個次要索引標籤都有兩個區段： [**群組原則] 物件****與 [群組**

## [群組原則物件] 區段


[**群組原則物件**] 區段會顯示群組原則物件（gpo）的篩選清單，並識別每個 GPO 的下列屬性：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">GPO 屬性</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>Name</strong></p></td>
<td align="left"><p>GPO 的名稱。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>狀態</strong></p></td>
<td align="left"><p>所選 GPO 的狀態</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>變更者</strong></p></td>
<td align="left"><p>已檢入或部署所選 GPO 之核准者的編輯者。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>變更日期</strong></p></td>
<td align="left"><p>針對受控制的 GPO，在經過修改或取出後將其簽核至已修改的最近日期。 如果是不受控制的 GPO，就是上次修改的日期。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>留言</strong></p></td>
<td align="left"><p>在修改時，由檢入或部署 GPO 的人員輸入的留言。 在需要回滾到前一個版本的情況下，識別版本的詳細資訊時很有用。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>電腦版本</strong></p></td>
<td align="left"><p>GPO 的電腦設定部分自動產生的版本。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>使用者版本</strong></p></td>
<td align="left"><p>GPO 的使用者設定部分的自動產生版本。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>GPO 狀態</strong></p></td>
<td align="left"><p>您可以個別管理電腦配置和使用者設定。 GPO 狀態表示已啟用 GPO 的哪些部分。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>WMI 篩選器</strong></p></td>
<td align="left"><p>顯示適用于此 GPO 的任何 WMI 篩選器。 WMI 篩選是在 GPMC 的 [ <strong> Wmi 篩選] </strong> 資料夾中，在 GPMC 的主控台樹中針對該域進行管理。</p></td>
</tr>
</tbody>
</table>

 

## [群組與使用者] 區段


選取 GPO 時，[**群組與使用者**] 區段會顯示群組和使用者有權存取該 gpo 的清單。 針對每個群組或使用者顯示允許的許可權和繼承。 AGPM 系統管理員可以使用標準 AGPM 角色（[編輯者]、[核准者]、[審查員] 和 [AGPM 管理員]）或自訂的許可權組合來設定許可權。

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

-   如需有關特定工作的角色與許可權的相關資訊，請參閱[執行 AGPM 管理員](performing-agpm-administrator-tasks-agpm30ops.md)工作、[執行編輯](performing-editor-tasks-agpm30ops.md)程式工作、[執行核准者](performing-approver-tasks-agpm30ops.md)工作及[執行審查員](performing-reviewer-tasks-agpm30ops.md)工作中的工作。

### 其他參考資料

-   [內容索引標籤](contents-tab-agpm30ops.md)

 

 





