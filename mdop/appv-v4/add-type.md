---
title: ADD TYPE
description: ADD TYPE
author: dansimp
ms.assetid: 8f1d3978-9977-4851-9f46-fee6aefa3535
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4d2dcfb24a32dc733aa91b5534e0011090ef12b9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809321"
---
# ADD TYPE


新增指定的檔案類型關聯。

`SFTMIME ADD TYPE:file-extension /APP application [/ICON icon-pathname]                 [/DESCRIPTION type-desc] [/CONTENT-TYPE content-type] [/GLOBAL]                 [/PERCEIVED-TYPE perceived-type] [/PROGID progid]                 [/CONFIRMOPEN {YES|NO}] [/SHOWEXT {YES|NO}]                 [/NEWMENU {YES|NO}]  [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">參數</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>類型：檔案 &lt; 副檔名&gt;</p></td>
<td align="left"><p>將與指定的應用程式相關聯的檔案名副檔名。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/APP &lt; 應用程式&gt;</p></td>
<td align="left"><p>應用程式的名稱和版本（選用）。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/ICON &lt; 圖示-pathname&gt;</p></td>
<td align="left"><p>圖示檔案的路徑或 URL。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/DESCRIPTION &lt; 類型-desc&gt;</p></td>
<td align="left"><p>檔案類型的方便使用名稱。 預設值為 [延伸檔案] &quot; 。&quot;</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/CONTENT-TYPE &lt; 內容類型&gt;</p></td>
<td align="left"><p>檔案的內容類型。 預設為 &quot; 應用程式/softricity 延伸。&quot;</p></td>
</tr>
<tr class="even">
<td align="left"><p>/GLOBAL</p></td>
<td align="left"><p>如果有的話，此電腦上的所有使用者都可以使用套件。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/PERCEIVED-TYPE &lt; 感知-類型&gt;</p></td>
<td align="left"><p>檔案的感知類型。 預設為 [無]。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/PROGID &lt; PROGID&gt;</p></td>
<td align="left"><p>檔案類型的程式設計識別碼。 預設為應用程式 Virt. 檔案。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/CONFIRMOPEN</p></td>
<td align="left"><p>指示使用者是否要下載此類型的檔案，是否應該詢問是否要開啟或儲存檔案。 預設為 [是]。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/SHOWEXT</p></td>
<td align="left"><p>指出是否應該顯示檔案的副檔名（即使使用者已要求隱藏所有副檔名）。 預設值為 [否]。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/NEWMENU</p></td>
<td align="left"><p>指出是否應該在 shell 的 [新增] 功能表中新增一個專案 <strong> </strong> 。 預設值為 [否]。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/LOG</p></td>
<td align="left"><p>如果已指定，輸出就會記錄到指定的路徑名稱。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/CONSOLE</p></td>
<td align="left"><p>如果已指定，輸出就會顯示在 active 主控台視窗中（預設）。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/GUI</p></td>
<td align="left"><p>如果已指定，輸出就會顯示在 Windows 對話方塊中。</p></td>
</tr>
</tbody>
</table>

 

針對版本4.6，新增了下列選項。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>/LOGU</p></td>
<td align="left"><p>如果已指定，輸出會以 UNICODE 格式記錄到指定的路徑名稱。</p></td>
</tr>
</tbody>
</table>

 

## 相關主題


[SFTMIME 命令參考](sftmime--command-reference.md)

 

 





