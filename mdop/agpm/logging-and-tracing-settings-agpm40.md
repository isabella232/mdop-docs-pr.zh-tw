---
title: 記錄和追蹤設定
description: 記錄和追蹤設定
author: dansimp
ms.assetid: 66d03306-80d8-4132-bf71-2827157b1fc9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c58da00e7030c5e4cb3e4d5c4e5bbffa0c754233
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802681"
---
# 記錄和追蹤設定


[高級群組原則管理（AGPM）] 的 [管理範本] 設定可讓您集中設定適用于您的 AGPM 服務器和用戶端的記錄和追蹤選項，這些設定會套用至其中的群組原則物件（GPO）。

編輯 GPO 時，在 [電腦 Configuration\\Policies\\Administrative Templates\\Windows Components\\AGPM] 下提供下列設定。

**追蹤檔案位置**：

-   用戶端：%LocalAppData%\\Microsoft\\AGPM\\agpm.log

-   伺服器：%ProgramData%\\Microsoft\\AGPM\\agpmserv.log

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
<td align="left"><p><strong>AGPM：設定記錄</strong></p></td>
<td align="left"><p>此原則設定可讓您開啟和設定 AGPM 的記錄。 此設定會影響 AGPM 的用戶端和伺服器元件。</p></td>
</tr>
</tbody>
</table>

 

### 其他參考資料

-   [系統管理範本資料夾](administrative-templates-folder-agpm40.md)

 

 





