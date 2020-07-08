---
title: 記錄和追蹤設定
description: 記錄和追蹤設定
author: dansimp
ms.assetid: db6b43c7-fdde-4d11-b5ab-a81346e56940
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bef0f8367647aad688c2aec7586ecdaae2e22143
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802677"
---
# 記錄和追蹤設定


[高級群組原則管理（AGPM）] 的 [管理範本] 設定可讓您集中設定適用于您的 AGPM 服務器和用戶端的記錄和追蹤選項，這些設定會套用至其中的群組原則物件（GPO）。

在群群組原則管理主控台（GPMC）中編輯 GPO 時，在 [**群群組原則物件編輯器**] 中的 [電腦 Configuration\\Administrative Templates\\Windows Components\\AGPM] 下提供下列設定。 如果看不到此路徑，請以滑鼠右鍵按一下 [**管理範本**]，然後新增 [agpm. admx] 或 [agpm .adm] 範本。

**追蹤檔案位置**：

-   用戶端：%LocalAppData%\\Microsoft\\AGPM\\agpm.log

-   伺服器：%CommonAppData%\\Microsoft\\AGPM\\agpmserv.log

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
<td align="left"><p><strong>AGPM 記錄</strong></p></td>
<td align="left"><p>如果已啟用，此設定會配置是否已開啟追蹤，以及詳細資料的層級。 此設定會影響 AGPM 的用戶端和伺服器元件。</p>
<p>如果停用或未設定，此設定就不會有任何效果。</p></td>
</tr>
</tbody>
</table>

 

### 其他參考資料

-   [系統管理範本設定](administrative-template-settings.md)

 

 





