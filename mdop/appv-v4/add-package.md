---
title: ADD PACKAGE
description: ADD PACKAGE
author: dansimp
ms.assetid: aa83928d-a234-4395-831e-2a7ef786ff53
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 925349ce5bdf041b6a8768b5413692966e1cfc1e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809332"
---
# ADD PACKAGE


新增套件記錄。 如果套件已存在，此命令會更新現有套件的設定。

`SFTMIME ADD PACKAGE:package-name /MANIFEST manifest-path                 [/OVERRIDEURL url [/AUTOLOADONREFRESH] [/AUTOLOADONLOGIN]                 [/AUTOLOADONLAUNCH] [/AUTOLOADTARGET {NONE|ALL|PREVUSED}]                 [/GLOBAL] [/LOG log-pathname | /CONSOLE | /GUI]`

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
<td align="left"><p>套件： &lt; 套件-名稱&gt;</p></td>
<td align="left"><p>套件的使用者可見及方便使用名稱。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/MANIFEST &lt; 資訊清單-path&gt;</p></td>
<td align="left"><p>列出套件中包含之應用程式的資訊清單檔案路徑，以及其所有發佈資訊。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/OVERRIDEURL &lt; URL&gt;</p></td>
<td align="left"><p>套件的 SFT 檔案位置。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/AUTOLOADONREFRESH</p></td>
<td align="left"><p>在發佈重新整理之後，會執行背景載入。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/AUTOLOADONLOGIN</p></td>
<td align="left"><p>在使用者登入時，會執行背景載入。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/AUTOLOADONLAUNCH</p></td>
<td align="left"><p>使用者從套件啟動應用程式後，就會執行背景載入。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/AUTOLOADTARGET 目標</p></td>
<td align="left"><p>指示將會 autoloaded 套件中的哪些應用程式。</p></td>
</tr>
<tr class="even">
<td align="left"><p>所有</p></td>
<td align="left"><p>不論是否有任何/AUTOLOADONxxx 標誌，都不會執行任何 autoloading。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>同時</p></td>
<td align="left"><p>如果啟用 autoload 觸發程式，則會將套件中的所有應用程式載入到 [快取] 中，不論它們先前是否已啟動。</p></td>
</tr>
<tr class="even">
<td align="left"><p>PREVUSED</p></td>
<td align="left"><p>如果啟用 autoload 觸發程式，則在使用者先前已啟動此套件中的任何應用程式時，就會載入套件。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/GLOBAL</p></td>
<td align="left"><p>如果有的話，此電腦上的所有使用者都可以使用套件。</p></td>
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

 

 





