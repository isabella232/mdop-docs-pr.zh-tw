---
title: 範本命令
description: 範本命令
author: dansimp
ms.assetid: 2ec11b3f-0c5c-4788-97bd-bd4bf64ba51a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7de90780caa1eb938f78597a760723f89e2e55ca
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802514"
---
# 範本命令


[**範本**] 索引標籤：

-   顯示可用範本的清單，您可以用來建立新的群組原則物件（Gpo）。

-   提供快捷方式功能表，其中的命令可根據選取的範本建立 GPO、管理範本，以及顯示範本的報表。

-   顯示有許可權存取選取範本的群組和使用者清單。

因為範本不能變更，所以範本沒有歷程記錄。 不過，與任何 GPO 版本一樣，範本的設定可以與 [設定] 報表一起顯示，或與另一個具有差異報告的 GPO 進行比較。

**記事** 範本是一個無法編輯且靜態的 GPO 版本，以做為建立新的可編輯 Gpo 的起點。

 

以滑鼠右鍵按一下這個索引標籤上的 [**群組原則物件**] 清單，就會顯示快捷方式功能表，包括下列任何一項適用的選項。

## 控制項


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
<td align="left"><p>根據選取的範本建立新的 GPO。 提供將新 GPO 部署到生產環境的選項。 如果您沒有建立 GPO 的許可權，系統會提示您提交要求。 （如果按一下滑鼠右鍵， <strong> 則會顯示此選項（如果沒有選取 GPO 的話）[群組原則物件] </strong> 清單。）</p></td>
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
<td align="left"><p>產生顯示所選 GPO 中設定的 HTML 式或以 XML 為基礎的報告。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>多種</strong></p></td>
<td align="left"><p>產生與兩個選取的 GPO 範本中的設定比較的 HTML 或以 XML 為基礎的報表。</p></td>
</tr>
</tbody>
</table>

 

## 範本管理


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
<td align="left"><p><strong>設為預設值</strong></p></td>
<td align="left"><p>將選取的範本設定為預設值，以便在建立新的 GPO 時自動使用。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>刪除</strong></p></td>
<td align="left"><p>將選取的範本移至 [ <strong> 回收站] </strong> 。 如果您沒有刪除 GPO 的許可權，系統會提示您提交要求。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>重新命名</strong></p></td>
<td align="left"><p>變更所選範本的名稱。</p></td>
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
<td align="left"><p>顯示 [高級群組原則管理（AGPM）] 的說明。</p></td>
</tr>
</tbody>
</table>

 

### 其他參考資料

-   [內容索引標籤](contents-tab-agpm30ops.md)

-   [執行編輯器工作](performing-editor-tasks-agpm30ops.md)

-   [執行檢閱者工作](performing-reviewer-tasks-agpm30ops.md)

 

 





