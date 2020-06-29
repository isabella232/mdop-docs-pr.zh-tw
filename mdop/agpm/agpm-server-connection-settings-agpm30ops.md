---
title: AGPM 伺服器連線設定
description: AGPM 伺服器連線設定
author: dansimp
ms.assetid: 5f03e397-b868-4c49-9cbf-a5f5d0ddcc39
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d9ee1e67eb2c565bcf833314d82cdf611e2caa85
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800231"
---
# AGPM 伺服器連線設定


您可以使用 [系統管理範本] 設定來針對高級群組原則管理（AGPM），集中設定適用于群組原則物件（GPO）的 [群組原則管理員] 的 [AGPM 服務器連線]。

編輯 GPO 時，[User Configuration\\Policies\\Administrative Templates\\Windows Components\\AGPM] 下提供下列設定。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">設定</th>
<th align="left">效果</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>AGPM：指定預設的 AGPM 服務器（所有網域）</strong></p></td>
<td align="left"><p>此原則設定可讓您為所有網域指定預設的 AGPM 服務器。 此功能僅供 AGPM 用戶端使用，且限制群組原則管理員連線到另一個封存。 您可以使用 <strong> AGPM： [指定 Agpm 伺服器] 設定來覆寫個別網域的此預設值 </strong> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>AGPM：指定 AGPM 服務器</strong></p></td>
<td align="left"><p>此原則設定可讓您指定個別網域的 AGPM 服務器。 此功能僅供 AGPM 用戶端使用，且限制群組原則管理員連線到指定網域的其他封存。 若要指定預設的 AGPM 服務器，請使用 <strong> AGPM： [指定預設的 Agpm 伺服器（所有網域）] </strong> 設定，並使用此原則設定來覆寫每個網域的預設值。</p></td>
</tr>
</tbody>
</table>

 

### 其他參考資料

-   [系統管理範本資料夾](administrative-templates-folder-agpm30ops.md)

-   [執行 AGPM 系統管理員工作](performing-agpm-administrator-tasks-agpm30ops.md)

 

 





