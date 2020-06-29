---
title: 功能可見性設定
description: 功能可見性設定
author: dansimp
ms.assetid: 9db2ba03-fb75-4f95-9138-ec89b9fc8d01
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 26f19895d0a9163885779688ba7d89f6d16f2a17
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802765"
---
# 功能可見性設定


[高級群組原則管理（AGPM）] 的 [管理範本] 設定可讓您集中設定套用這些設定之群組原則物件（GPO）之 [**變更控制**] 節點與 [歷程**記錄**] 索引標籤的可見度。

在群群組原則管理主控台（GPMC）中編輯**GPO 時，在 [使用者**Configuration\\Administrative Templates\\Windows Components\\Microsoft 管理主控台 \ \ 受限制/允許的 Snap-ins\\Extension] 增益集中提供下列設定。 如果看不到此路徑，請以滑鼠右鍵按一下 [**管理範本**]，然後新增 [agpm. admx] 或 [agpm .adm] 範本。

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
<td align="left"><p><strong>AGPM 變更控制</strong></p></td>
<td align="left"><p>如果已啟用或未設定，則 <strong> 會在 GPMC 中看到 [變更控制] </strong> 節點。</p>
<p>如果停用，則 <strong> </strong> 會在 GPMC 中看不到 [變更控制] 節點。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>AGPM 連結延伸</strong></p></td>
<td align="left"><p>如果已啟用或未設定， <strong> 則 </strong> 會在 GPMC 中顯示每個連結 GPO 的 [歷程記錄] 索引標籤。</p>
<p>如果停用， <strong> 則 </strong> 連結的 gpo 看不到 [歷程記錄] 索引標籤。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>AGPM GPO 延伸</strong></p></td>
<td align="left"><p>如果已啟用或未設定， <strong> 則 </strong> 會在 GPMC 中顯示每個 GPO 的 [歷程記錄] 索引標籤。</p>
<p>如果停用，則 [History] 索引標籤 <strong> </strong> 不會顯示在 [gpo] 中。</p></td>
</tr>
</tbody>
</table>

 

### 其他參考資料

-   [系統管理範本設定](administrative-template-settings.md)

 

 





