---
title: AGPM 伺服器連線設定
description: AGPM 伺服器連線設定
author: dansimp
ms.assetid: faf78e5b-2b0d-4069-9b8c-910add892200
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d63163de0a1adf744e6d442b8073e5b32352ed67
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800239"
---
# AGPM 伺服器連線設定


您可以使用 [系統管理範本] 設定來針對高級群組原則管理（AGPM），集中設定適用于群組原則物件（GPO）的 [群組原則管理員] 的 [AGPM 服務器連線]。

編輯 GPO 時，[User Configuration\\Administrative Templates\\Windows Components\\AGPM] 下提供下列設定。 如果看不到此路徑，請以滑鼠右鍵按一下 [**管理範本**]，然後新增 [agpm. admx] 或 [agpm .adm] 範本。

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
<td align="left"><p><strong>AGPM 服務器（所有網域）</strong></p></td>
<td align="left"><p>如果啟用，此設定會集中設定一個 AGPM 服務器連線供所有網域使用，並停用 <strong> 群組原則管理員的 [AGPM 服務器] 索引標籤上的設定 </strong> 。 針對多個 AGPM 服務器，請使用預設的伺服器設定此設定，然後 <strong> </strong> 在 [系統管理範本] 中設定 [AGPM 服務器] 設定，以覆寫其他網域的此伺服器。</p>
<p>如果停用或未設定，每個群組原則管理員都必須在 AGPM 的 [ <strong> Agpm 伺服器] 索引標籤上，選取要顯示每個網域的 AGPM 服務器 </strong> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>AGPM 服務器</strong></p></td>
<td align="left"><p>如果啟用，此設定會集中設定多個網域專用的 AGPM 服務器，並覆寫 <strong> 管理範本中的 [AGPM 服務器（所有網域）] </strong> 設定。 如果您的環境只需要單一的 AGPM 服務器，請 <strong> 在 [系統管理範本] 中只使用 [AGPM 服務器（所有網域）] </strong> 設定。</p>
<p>如果停用或未設定，系統會在系統 <strong> 管理範本中的 [AGPM server （所有網域）] </strong> 設定設定 AGPM 服務器連線。</p></td>
</tr>
</tbody>
</table>

 

### 其他參考資料

-   [系統管理範本設定](administrative-template-settings.md)

-   [執行 AGPM 系統管理員工作](performing-agpm-administrator-tasks.md)

 

 





