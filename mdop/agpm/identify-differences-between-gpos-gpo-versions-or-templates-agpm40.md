---
title: 找出 GPO、GPO 版本或範本之間的差異
description: 找出 GPO、GPO 版本或範本之間的差異
author: dansimp
ms.assetid: 3f03c368-162b-450f-be6c-2807c3e8d741
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bf5a7c71b431c787dcb2b16fe9a19f7ff9b06046
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802746"
---
# 找出 GPO、GPO 版本或範本之間的差異


您可以產生以 HTML 為基礎或 XML 為基礎的差異報告，來分析群組原則物件（Gpo）、範本或不同版本的 GPO 間的差異。

具有 [檢閱者]、[編輯者] 或 [AGPM 管理員] （完全控制）角色的使用者帳戶，或需要高級群組原則管理（AGPM）中的必要許可權，才能完成此程式。 請參閱本主題中的「其他注意事項」中的詳細資料。

## 識別 Gpo、GPO 版本或範本之間的差異


-   [在兩個 Gpo 或範本之間](#bkmk-two-gpos)

-   [在 GPO 與範本之間](#bkmk-gpo-and-template)

-   [在單一 GPO 的兩個版本之間](#bkmk-two-versions)

-   [GPO 版本與範本之間](#bkmk-gpo-version-and-template)

## <a href="" id="bkmk-two-gpos"></a>


**找出兩個 Gpo 或範本之間的差異**

1.  在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。

2.  在 [詳細資料] 窗格的 [**內容**] 索引標籤上，按一下索引標籤以顯示 gpo （如果比較兩個範本，則則是範本）。

3.  選取兩個 Gpo 或範本。

4.  以滑鼠右鍵按一下其中一個 Gpo 或範本，按一下 [**差異**]，然後按一下 [ **HTML 報表**] 或 [ **XML 報表**]，以顯示匯總 gpo 或範本之設定的差異報告。

### <a href="" id="bkmk-gpo-and-template"></a>

**識別 GPO 與範本之間的差異**

1.  在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。

2.  在 [詳細資料] 窗格的 [**內容**] 索引標籤上，按一下索引標籤以顯示 gpo （如果比較兩個範本，則則是範本）。

3.  以滑鼠右鍵按一下該 GPO，按一下 [**差異**]，然後按一下 [**範本**]。

4.  選取 [範本] 和 [報告類型]，然後按一下 **[確定]** 以顯示摘要與範本設定的差異報告。

### <a href="" id="bkmk-two-versions"></a>

**若要識別一個 GPO 的兩個版本之間的差異**

1.  在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。

2.  在 [詳細資料] 窗格的 [**內容**] 索引標籤上，按一下索引標籤以顯示 gpo （如果比較兩個範本，則則是範本）。

3.  按兩下 GPO 以顯示其記錄，然後醒目提示要比較的版本。

4.  以滑鼠右鍵按一下其中一個版本，按一下 [**差異**]，然後按一下 [ **HTML 報表**] 或 [ **XML 報表**]，以顯示匯總 gpo 設定的差異報告。

### <a href="" id="bkmk-gpo-version-and-template"></a>

**若要識別 GPO 版本與範本之間的差異**

1.  在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。

2.  在 [詳細資料] 窗格的 [**內容**] 索引標籤上，按一下索引標籤以顯示 gpo （如果比較兩個範本，則則是範本）。

3.  按兩下該 GPO 以顯示其歷程記錄。

4.  以滑鼠右鍵按一下感興趣的 GPO 版本，按一下 [**差異**]，然後按一下 [**範本**]。

5.  選取 [範本] 和 [報告類型]，然後按一下 **[確定]** 以顯示 [摘要] 與 [GPO 版本] 與 [範本] 設定的差異報告。

## 差異報告的主要


<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">符號</th>
<th align="left">意義</th>
<th align="left">色彩</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>無</p></td>
<td align="left"><p>在兩個 Gpo 中都存在具有相同設定的專案</p></td>
<td align="left"><p>依層級而異</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>[#]</strong></p></td>
<td align="left"><p>專案存在於兩個 Gpo 中，但具有已變更的設定</p></td>
<td align="left"><p>天藍色</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>[-]</strong></p></td>
<td align="left"><p>只有在第一個 GPO 中存在專案</p></td>
<td align="left"><p>紅色</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>[+]</strong></p></td>
<td align="left"><p>只有在第二個 GPO 中存在專案</p></td>
<td align="left"><p>綠色</p></td>
</tr>
</tbody>
</table>

 

-   針對具有已變更之設定的專案，已變更的設定會在專案展開時加以識別。 每個 GPO 中屬性的值會以 Gpo 在報表中顯示的順序顯示。

-   設定的部分變更可能會導致將專案報告成兩個不同的專案（只有在第一個 GPO 中有一個，而只是在第二個 GPO 中存在，而另一個則只出現在第二個

### 其他考量

-   根據預設，您必須是檢閱者、編輯者或 AGPM 管理員（完全控制），才能執行此程式。 具體來說，您必須擁有 [**清單內容**] 和 [**讀取設定**] 許可權給 GPO。 此外，若要顯示 Gpo 清單，您必須擁有該網域的 [**清單內容**] 許可權。

### 其他參考資料

-   [執行檢閱者工作](performing-reviewer-tasks-agpm40.md)

 

 





