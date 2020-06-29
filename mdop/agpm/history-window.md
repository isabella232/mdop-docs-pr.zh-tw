---
title: 歷程記錄視窗
description: 歷程記錄視窗
author: dansimp
ms.assetid: f11f9ad9-bffe-4c56-8c46-fe9c0a8e55c1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 02b4336409f33d6c1f2868bceb22cb95120f2198
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802757"
---
# 歷程記錄視窗


您可以按兩下某個 GPO，或以滑鼠右鍵按一下某個 GPO，然後按一下 [歷程**記錄**]，以顯示該群群組原則物件（GPO）的歷程記錄。 它也會顯示在**群組原則管理主控台**（GPMC）中作為每個 GPO 的索引標籤。

[歷程記錄] 會提供儲存在封存中之所有已選取 GPO 版本的清單。 您可以從 [歷程**記錄**] 視窗取得 gpo 中的設定報告、比較多個 gpo 版本，或回滾到舊版的 gpo。

## 在 [歷程記錄] 視窗中篩選事件


[歷程**記錄**] 視窗中的索引標籤會篩選顯示的事件。

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
<td align="left"><p><strong>全部顯示</strong></p></td>
<td align="left"><p>顯示所有版本的 GPO。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>已檢入</strong></p></td>
<td align="left"><p>只顯示 GPO 的簽入版本。 此清單中省略了已部署的版本。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>僅限標籤</strong></p></td>
<td align="left"><p>只顯示有關聯標籤的 Gpo。</p></td>
</tr>
</tbody>
</table>

 

## 事件資訊


針對所選 GPO 之歷程記錄中的每個事件提供資訊。

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
<td align="left"><p><strong>電腦</strong></p></td>
<td align="left"><p>GPO 的電腦設定部分自動產生的版本。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>使用者</strong></p></td>
<td align="left"><p>GPO 的使用者設定部分的自動產生版本。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>時間</strong></p></td>
<td align="left"><p>在 [狀態] 欄位中執行動作時，GPO 版本的時間戳記。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>狀態</strong></p></td>
<td align="left"><p>所選 GPO 版本的狀態：</p>
<p><img src="images/36f6b687-f5cc-40d1-805f-b191d1fb1ace.gif" alt="Deployed GPO icon" /> <strong></strong>已部署：此版本的 GPO 目前在生產環境中。</p>
<p><img src="images/57b610a5-1c71-4d26-9173-d04abd495fcc.gif" alt="Checked in GPO icon" /> <strong>已檢入 </strong> ：此版本的 GPO 可供授權的編輯者取出，以供您用來進行編輯或供群群組原則管理員部署。</p>
<p><img src="images/8e7a7c4e-809a-435a-8b29-30d797936210.gif" alt="Checked out GPO icon" /> <strong>已取出 </strong> ：此版本的 GPO 目前已由編輯工具取出，不適用於其他編輯器。 （取出狀態不會記錄在 <strong>[歷程記錄] </strong> ，除了指出 GPO 目前是否已取出。</p>
<p><img src="images/327623bd-0842-4372-be1f-bdc4b8c3481c.gif" alt="Created GPO icon" /> <strong>已建立 </strong> ：識別最初建立 GPO 的日期和時間。</p>
<p><img src="images/8356fcdc-1279-425b-ab14-a23bcfe391da.gif" alt="Labeled GPO icon" /> <strong>標示 </strong> ：識別 GPO 的標示版本。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>GPO 狀態</strong></p></td>
<td align="left"><p>您可以彼此獨立管理電腦配置和使用者設定。 此狀態會顯示已啟用 GPO 的哪些部分。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>擁有者</strong></p></td>
<td align="left"><p>已檢入或部署 GPO 的人員。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>留言</strong></p></td>
<td align="left"><p>在修改此版本時，由 GPO 擁有者輸入的留言。 在需要回滾到前一個版本的情況下，識別版本的詳細資訊時很有用。</p></td>
</tr>
</tbody>
</table>

 

## 報告


根據是否已選取單一 GPO 版本或多個 GPO 版本，[**設定**] 和 [**差異**] 按鈕會顯示 GPO 設定的報告。 以滑鼠右鍵按一下 [GPO 版本]，也會提供顯示 XML 報表的選項。

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

-   設定的部分變更可能會導致將專案報告成兩個不同的專案（只有在第一個 GPO 中有一個，而不是在第二個 GPO 中提供，而不是在一個已變更的專案中出現）。

### 其他參考資料

-   [內容索引標籤](contents-tab.md)

 

 





