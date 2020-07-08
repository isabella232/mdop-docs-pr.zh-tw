---
title: PUBLISH APP
description: PUBLISH APP
author: dansimp
ms.assetid: f25f06a8-ca23-435b-a0c2-16a5f39b6b97
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b2ccb19255786ee47a8356feef14be1c4d9b4fb2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800895"
---
# PUBLISH APP


將應用程式快捷方式發佈至使用者的 [開始] 功能表、[桌面] 或其他指定位置。

`SFTMIME PUBLISH APP:application                 {/DESKTOP | /START | /TARGET target-path} [/ICON icon-pathname]                 [/DISPLAY display-name] [/ARGS command-args...]                 [/LOG log-pathname | /CONSOLE | /GUI]`

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
<td align="left"><p>應用程式： &lt; 應用程式&gt;</p></td>
<td align="left"><p>應用程式的名稱和版本（選用）。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/DESKTOP</p></td>
<td align="left"><p>發佈使用者桌面的快捷方式。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/START</p></td>
<td align="left"><p>發佈快捷方式至 [開始] 功能表的 [程式] 資料夾中的 [應用程式虛擬化應用程式] 資料夾。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/TARGET &lt; 目標-path&gt;</p></td>
<td align="left"><p>要發佈快捷方式的絕對路徑。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/ICON &lt; 圖示-pathname&gt;</p></td>
<td align="left"><p>圖示檔案的路徑或 URL。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/DISPLAY &lt; 顯示名稱&gt;</p></td>
<td align="left"><p>快捷方式的顯示名稱。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/ARGS &lt; command-ARGS&gt;</p></td>
<td align="left"><p>要傳遞給應用程式的參數。</p></td>
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

 

 





