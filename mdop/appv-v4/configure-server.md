---
title: CONFIGURE SERVER
description: CONFIGURE SERVER
author: dansimp
ms.assetid: c916eddd-74f2-46e4-953d-120b23284e37
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7757f281ec57645d20367056ba0013ef476a91a1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809075"
---
# CONFIGURE SERVER


讓使用者能夠變更伺服器的設定;未指定的任何設定將不會被修改。

`SFTMIME CONFIGURE SERVER:server-name [/NAME display-name] [/HOST hostname]                 [/PORT port] [/PATH path] [/TYPE {HTTP|RTSP}]                 [/REFRESH {ON|OFF}] [/SECURE]                 [/LOG log-pathname | /CONSOLE | /GUI]`

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
<td align="left"><p>伺服器： &lt; 伺服器-名稱&gt;</p></td>
<td align="left"><p>發佈伺服器的顯示名稱。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/NAME &lt; 顯示名稱&gt;</p></td>
<td align="left"><p>伺服器的新顯示名稱。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/HOST &lt; 主機名稱&gt;</p></td>
<td align="left"><p>發佈伺服器的主機名稱或 IP 位址。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/PORT &lt; 埠&gt;</p></td>
<td align="left"><p>發佈伺服器所偵聽的埠。 預設值為80（適用于一般 HTTP 伺服器）、使用增強安全性的443（適用于一般應用程式虛擬化伺服器的554），以及使用增強安全性的伺服器322。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/PATH &lt; 路徑&gt;</p></td>
<td align="left"><p>發佈要求中使用之 URL 的路徑部分。 如果 TYPE 參數設定為 RTSP，則路徑是選擇性的且預設為 &quot; / &quot; 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/TYPE</p></td>
<td align="left"><p>指出發佈伺服器是 Web 服務器（ &quot; HTTP &quot; ）或應用程式虛擬化伺服器（ &quot; RTSP &quot; ）。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/REFRESH</p></td>
<td align="left"><p>如果設定為 [開啟]，則在使用者登入時，發佈資訊將會重新整理。 預設為 [開啟]。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/SECURE</p></td>
<td align="left"><p>如果存在，則表示應該建立與 [發佈伺服器] 的 [增強安全性] 的連線。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/LOG</p></td>
<td align="left"><p>如果已指定，輸出就會記錄到指定的路徑名稱。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/CONSOLE</p></td>
<td align="left"><p>如果已指定，輸出就會顯示在 active 主控台視窗中（預設）。</p></td>
</tr>
<tr class="odd">
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

 

 





