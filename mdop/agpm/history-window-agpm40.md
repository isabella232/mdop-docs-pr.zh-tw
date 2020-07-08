---
title: 歷程記錄視窗
description: 歷程記錄視窗
author: dansimp
ms.assetid: 5bea62e7-d267-40b2-a66d-fb1be7373a1c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 81f19e3834e945a45238856e23f6ee4a86407c4a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802758"
---
# 歷程記錄視窗


您可以按兩下某個 GPO，或以滑鼠右鍵按一下某個 GPO，然後按一下 [歷程**記錄**]，以顯示該群群組原則物件（GPO）的歷程記錄。 它也會顯示在群組原則管理主控台（GPMC）中作為每個 GPO 的索引標籤。

[歷程記錄] 會在所選 GPO 的生命週期中提供事件記錄。 您可以從 [歷程**記錄**] 視窗取得 gpo 版本中的設定報告、比較多個版本的 gpo，或回滾到舊版的 gpo。

## 在 [歷程記錄] 視窗中篩選事件


[歷程**記錄**] 視窗中的索引標籤會篩選 GPO 歷程記錄中的狀態。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">索引標籤</th>
<th align="left">篩選</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>所有狀態</strong></p></td>
<td align="left"><p>顯示 GPO 歷程記錄中的所有狀態。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>唯一版本</strong></p></td>
<td align="left"><p>只顯示已核取到封存中之 GPO 的唯一版本。 此清單中省略了部署到生產環境的版本、唯一版本的快捷方式及資訊狀態。</p></td>
</tr>
</tbody>
</table>



## 事件資訊


提供有關 GPO 歷程記錄中每個狀態的資訊。

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
<td align="left"><p><strong>變更日期</strong></p></td>
<td align="left"><p>[ <strong> 省/市/自治區] 資料行中動作的時間戳記 </strong> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>狀態</strong></p></td>
<td align="left"><p>GPO 歷程記錄中的狀態。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>變更者</strong></p></td>
<td align="left"><p>已檢入或部署 GPO 的人員。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>留言</strong></p></td>
<td align="left"><p>在此版本變更時，由檢入或部署 GPO 的人員所輸入的批註，在需要回滾至較舊版本的情況下，這對於識別版本的詳細資訊很有用。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>已</strong></p></td>
<td align="left"><p>如果封存中保留的每個 GPO 的唯一版本數受到限制，是否可刪除此 GPO 版本。</p>
<div class="alert">
<strong>注意</strong><br/><p>您可以在 GPO 上按一下滑鼠右鍵，然後按一下 [不 <strong> 允許刪除] </strong> 或 [ <strong> 允許刪除]，以變更 gpo 的版本是否可刪除 </strong> 。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><strong>電腦版本</strong></p></td>
<td align="left"><p>GPO 的 [電腦設定] 元件的自動產生版本。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>使用者版本</strong></p></td>
<td align="left"><p>GPO 的使用者設定部分自動產生的版本。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>GPO 狀態</strong></p></td>
<td align="left"><p>您可以彼此獨立管理電腦配置和使用者設定。 此狀態會顯示已啟用 GPO 的哪些部分。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>來源 GPO 資訊</strong></p></td>
<td align="left"><p>如果 GPO 是從另一個目錄林匯入，則為與上次變更相關聯的原始 GPO 名稱、網域和使用者及日期。</p></td>
</tr>
</tbody>
</table>



## 報告


[**設定**] 和 [**差異**] 按鈕會顯示所選 gpo 版本或版本的 gpo 設定報告。 此外，您也可以用滑鼠右鍵按一下 GPO 版本或版本，提供顯示以 XML 為基礎的報表的選項。

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
<td align="left"><p><strong>設定</strong></p></td>
<td align="left"><p>產生以 HTML 為基礎的報告，其中顯示所選版本之 GPO 中的設定。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>多種</strong></p></td>
<td align="left"><p>產生與多個選取版本之 GPO 中的設定比較的 HTML 報告。</p></td>
</tr>
</tbody>
</table>



### 差異報告的主要

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

-   設定的部分變更可能會導致將專案報告為兩個專案（只有在第一個 GPO 中有一個專案，第二個是在第二個 GPO 中提供，而另一個僅存在於第二個專案，

### 其他參考資料

-   [內容索引標籤](contents-tab-agpm40.md)









