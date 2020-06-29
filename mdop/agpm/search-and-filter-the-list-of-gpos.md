---
title: 搜尋和篩選 GPO 清單
description: 搜尋和篩選 GPO 清單
author: dansimp
ms.assetid: 1bc58a38-033c-4aed-9eb4-c239827f5501
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5646a51a37a4ca9195fb9ef858e8c5920ca7738a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802546"
---
# 搜尋和篩選 GPO 清單


在 [高級群組原則管理（AGPM）] 中，您可以搜尋群組原則物件（Gpo）及其屬性的清單，以篩選顯示的 Gpo 清單。 例如，您可以搜尋具有特定名稱、狀態或批註的 Gpo。 您也可以搜尋由特定群組原則系統管理員或特定日期所變更的 Gpo。

## 執行複雜的搜尋


您可以使用 [格式化*GPO 屬性1：搜尋字串 1 GPO 屬性2：搜尋字串 2 ...] 來執行複雜搜尋。全欄搜尋字串*。 搜尋不區分大小寫。

-   **GPO 屬性：** 在 [**電腦版本**] 或 [**使用者版本**] 以外的 AGPM 之 gpo 清單中的任何欄標題。 GPO 屬性包含 GPO 名稱、狀態、最近變更 GPO 的使用者，以及 GPO 最近變更的日期和時間、批註、GPO 狀態，以及套用到 GPO 的 WMI 篩選器。

-   **搜尋字串：** 要在指定資料行中搜尋的文字。 如果字串包含空格，您必須以引號括住字串。

-   **全欄搜尋字串：** 要在 [**電腦版本**] 和 [**使用者版本**] 以外的 AGPM 之 gpo 清單中的所有欄中搜尋的文字。 您可以包含以空格分隔的多個字串。 如果字串包含空格，您必須以引號括住字串。

每個 GPO 屬性和搜尋字串配對，以及每個全欄搜尋字串都是使用邏輯 AND 運算結合。 結果是所有 Gpo 的清單，其中每個指定的屬性都包含指定的搜尋字串，而所有的全欄搜尋字串都出現在至少一欄中。 搜尋會傳回字串的任何部分相符，因此您可以輸入 GPO 名稱或使用者名稱的一部分，並查看其名稱中包含該文字的所有 Gpo 的清單。

下列是搜尋的範例：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">搜尋結果的描述</th>
<th align="left">搜尋查詢</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>名稱中包含文字安全性和北美的所有 Gpo <strong> </strong> <strong> </strong> 。</p></td>
<td align="left"><p><strong>名稱： </strong><strong> 安全性 </strong><strong> 名稱： </strong> &quot; <strong> 北美</strong>&quot;</p></td>
</tr>
<tr class="even">
<td align="left"><p>所有已取出的 Gpo。</p></td>
<td align="left"><p><strong>狀態： </strong> &quot; <strong> 已取出</strong>&quot;</p></td>
</tr>
<tr class="odd">
<td align="left"><p>使用者最近在 <strong> 前一個月變更的所有 gpo </strong> 。</p></td>
<td align="left"><p><strong>變更者： </strong><strong> 系統管理員 </strong><strong> 變更日期： </strong><strong> lastmonth</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>所有的 Gpo，其中的 word <strong> 防火牆 </strong> 都包含在最近的批註中，而 word <strong> 安全性則 </strong> 會出現在任何資料行中。</p></td>
<td align="left"><p><strong>批註： </strong><strong> 防火牆 </strong><strong> 安全性</strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p>已 <strong> 停用所有設定狀態的所有 gpo </strong> 。</p></td>
<td align="left"><p><strong>gpo 狀態： </strong><strong> 全部</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>已套用名為「我的 WMI 篩選」的 WMI 篩選器的所有 Gpo <strong> </strong> ，且已 <strong> 停用使用者配置設定的狀態 </strong> 。</p></td>
<td align="left"><p><strong>wmi 篩選： </strong> &quot; <strong> 我的 WMI 篩選 </strong> &quot; <strong> gpo 狀態： </strong><strong> 使用者</strong></p></td>
</tr>
</tbody>
</table>

 

## 指定日期


您可以在特定時間搜尋 Gpo 變更，或在一段時間內使用您在 Windows 中進行搜尋時所提供的特殊條件來搜尋。 如果輸入特定的日期或時間，您必須使用 [**變更日期] 資料**行中所用的格式。 下列是 [**變更日期] 資料**行的搜尋範例：

-   **變更日期：****10/10/2009**

-   **變更日期：****10/10/2009 9:00:00 AM**

-   **變更日期：****thisweek**

當您搜尋 [**變更日期] 資料**行時，您可以使用下列特殊字詞（不區分大小寫）：

-   **今天**

-   **昨天**

-   **ThisWeek**

-   **LastWeek**

-   **ThisMonth**

-   **LastMonth**

-   **TwoMonths**

-   **ThreeMonths**

-   **ThisYear**

-   **LastYear**

### 其他考量

-   根據預設，您必須是檢閱者、編輯者或 AGPM 管理員（完全控制），才能執行此程式。 具體說來，您必須擁有該網域的 [**清單內容**] 許可權。

-   如需有關 GPO 屬性的詳細資訊，請參閱 [[內容]](contents-tab-features-agpm40.md)索引標籤功能。

### 其他參考資料

-   [進階群組原則管理 4.0](advanced-group-policy-management-40.md)

 

 





