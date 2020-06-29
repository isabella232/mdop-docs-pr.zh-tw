---
title: 受控制索引標籤
description: 受控制索引標籤
author: dansimp
ms.assetid: 8995a9e1-ace4-40b7-a47b-e1e9924541ba
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 71668555dd0b5d5ff42b5a4a49ecaaa5edec52e2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802893"
---
# 受控制索引標籤


[**受控**] 索引標籤：

-   顯示由 [高級群組原則管理（AGPM）] 管理的群組原則物件（Gpo）清單。

-   提供快捷方式功能表，其中包含管理 Gpo 及顯示 Gpo 的記錄和報告的命令。

-   顯示有許可權存取所選 GPO 的群組和使用者清單。

以滑鼠右鍵按一下這個索引標籤上的 [**群組原則物件**] 清單，就會顯示快捷方式功能表，包括下列任何一項適用的選項。

## 控制項與歷程記錄


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">命令</th>
<th align="left">效果</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>新的受控 GPO</strong></p></td>
<td align="left"><p>透過 AGPM 管理變更控制來建立新的 GPO，然後將它部署到生產環境。 如果您沒有建立 GPO 的許可權，系統會提示您提交要求。 （如果按一下滑鼠右鍵， <strong> 則會顯示此選項（如果沒有選取 GPO 的話）[群組原則物件] </strong> 清單。）</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>歷程記錄</strong></p></td>
<td align="left"><p>開啟一個視窗，列出已儲存在封存中的所有已選取 GPO 版本。 您可以從 [歷程記錄] 取得 GPO 中的設定報告、比較 GPO 的兩個版本、比較 GPO 與範本，或回滾到舊版的 GPO。</p></td>
</tr>
</tbody>
</table>

 

## 報告


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">命令</th>
<th align="left">效果</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>設定</strong></p></td>
<td align="left"><p>產生顯示所選 GPO 中設定的 HTML 或 XML 報告，或從組織單位顯示所選 GPO 的連結（如果 GPO 是最近控制、匯入或檢入）。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>多種</strong></p></td>
<td align="left"><p>產生與兩個選取 Gpo 或所選 GPO 及範本中的設定比較的 HTML 或 XML 式報告。</p></td>
</tr>
</tbody>
</table>

 

## 編輯


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">命令</th>
<th align="left">效果</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>編輯</strong></p></td>
<td align="left"><p>開啟 [ <strong> 群組原則物件編輯器] </strong> ，對選取的 GPO 進行變更。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>退房</strong></p></td>
<td align="left"><p>從封存中取得選取的 GPO 的複本以進行離線編輯，並禁止任何人編輯它，直到將它檢入回封存為止。 （您可以透過 AGPM 管理員（完全控制）來覆寫 [取出]。）</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>登記</strong></p></td>
<td align="left"><p>將所選 GPO 的已編輯版本檢查到封存中，讓其他授權的編輯者可以進行變更，或讓核准者將它部署到生產環境。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>復原取出</strong></p></td>
<td align="left"><p>將已取出的 GPO 傳回封存，且不做任何變更。</p></td>
</tr>
</tbody>
</table>

 

## 版本管理


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">命令</th>
<th align="left">效果</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>從生產匯入</strong></p></td>
<td align="left"><p>針對選取的 GPO，將生產環境中的版本複製到封存。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>刪除</strong></p></td>
<td align="left"><p>將選取的 GPO 移至 [回收站]，並指出是否要在生產中保留已部署的版本（如果有的話），或是將它刪除，以及封存中的版本。 如果您沒有刪除 GPO 的許可權，系統會提示您提交要求。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>部署</strong></p></td>
<td align="left"><p>將已存回封存的選取 GPO 移至生產環境。 這個動作會將它放在網路上，並覆寫先前作用中的 GPO （如果存在的話）。 如果您沒有部署 GPO 的許可權，系統會提示您提交要求。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Label</strong></p></td>
<td align="left"><p>以描述性標籤（例如 [ &quot; 已知完好] &quot; ）和 [保留記錄] 的批註標示選取的 GPO。 標籤會顯示在 [ <strong> </strong> 記錄] 視窗 [批註] 欄中的 [省/市/自治區] 欄和 [批註 <strong> ] 中 </strong> <strong> </strong> ，讓您可以輕鬆識別以特定標籤識別的舊版 GPO，以便在問題發生時回滾。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>重新命名</strong></p></td>
<td align="left"><p>變更所選 GPO 的名稱。 如果 GPO 已部署，重新部署 GPO 時，系統會在生產環境中更新名稱。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>另存為範本</strong></p></td>
<td align="left"><p>根據所選 GPO 的設定建立新範本。</p></td>
</tr>
</tbody>
</table>

 

## 其他


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">命令</th>
<th align="left">效果</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>重新整理</strong></p></td>
<td align="left"><p>更新群組原則管理主控台的顯示，以納入任何變更。 在重新整理顯示器之前，會看不到某些變更。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>說明</strong></p></td>
<td align="left"><p>顯示 AGPM 的說明。</p></td>
</tr>
</tbody>
</table>

 

### 其他參考資料

-   [內容索引標籤](contents-tab.md)

-   [執行編輯器工作](performing-editor-tasks.md)

-   [執行核准者工作](performing-approver-tasks.md)

-   [執行檢閱者工作](performing-reviewer-tasks.md)

 

 





