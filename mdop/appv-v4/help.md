---
title: HELP
description: HELP
author: dansimp
ms.assetid: 0ddb5f18-0c0a-45ea-b7c7-2d4749e3d35d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 395e6199529ccbe708aa7d1ac6673ea6f9494ae4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808769"
---
# HELP


顯示可在應用程式虛擬化（App-v）中使用的各種 SFTMIME 命令的相關資訊。

## HELP


`SFTMIME [/? | /HELP [VERB:<verb>]]`

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
<td align="left"><p>/？、/HELP</p></td>
<td align="left"><p>顯示使用量資訊。</p></td>
</tr>
<tr class="even">
<td align="left"><p>動作</p></td>
<td align="left"><p>要執行的命令，例如 [新增]、[重新整理]、[說明] 或 [移除]。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>物件</p></td>
<td align="left"><p>套用命令的用途，例如 APP： &quot; 預設應用程式。&quot;</p></td>
</tr>
<tr class="even">
<td align="left"><p>參數</p></td>
<td align="left"><p>指定動詞和物件的選用參數。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/LOG</p></td>
<td align="left"><p>將輸出記錄到指定的路徑名稱。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/CONSOLE</p></td>
<td align="left"><p>在 active 主控台視窗中顯示輸出（預設）。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/GUI</p></td>
<td align="left"><p>顯示對話方塊中的錯誤（不正確查詢）。</p></td>
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

 

支援下表所述的動詞。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>ADD</p></td>
<td align="left"><p>將新的應用程式、套件、檔案類型關聯或發佈伺服器新增至 App-v 用戶端。</p></td>
</tr>
<tr class="even">
<td align="left"><p>設定</p></td>
<td align="left"><p>變更應用程式、套件、檔案類型關聯或發佈伺服器的設定。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>DELETE</p></td>
<td align="left"><p>移除應用程式、套件、檔案類型關聯或伺服器。</p></td>
</tr>
<tr class="even">
<td align="left"><p>裝載</p></td>
<td align="left"><p>將套件載入到檔案系統快取中。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>維修中心</p></td>
<td align="left"><p>重設您的應用程式個人設定。</p></td>
</tr>
<tr class="even">
<td align="left"><p>REFRESH</p></td>
<td align="left"><p>觸發發佈伺服器更新。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>出版</p></td>
<td align="left"><p>將應用程式快捷方式發佈至使用者的 [開始] 功能表、[桌面] 或其他指定位置，或可用於發佈整個套件的內容。</p></td>
</tr>
<tr class="even">
<td align="left"><p>解除發佈</p></td>
<td align="left"><p>移除整個套件的快速鍵和檔案類型。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>QUERY</p></td>
<td align="left"><p>取得目前的應用程式、套件、檔案類型關聯或發佈伺服器清單。</p></td>
</tr>
<tr class="even">
<td align="left"><p>清除</p></td>
<td align="left"><p>移除一或多個應用程式的個人設定和桌面配置。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>卸載</p></td>
<td align="left"><p>從檔案系統快取中卸載套件。</p></td>
</tr>
<tr class="even">
<td align="left"><p>狀</p></td>
<td align="left"><p>鎖定檔案系統快取中指定的應用程式。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>鎖</p></td>
<td align="left"><p>解除鎖定檔案系統快取中指定的應用程式。</p></td>
</tr>
</tbody>
</table>

 

如需上述動作的詳細資訊，請使用下列命令：

`SFTMIME /HELP VERB:verb`

例如，下列命令會顯示 ADD 動詞的資訊：

`SFTMIME /HELP VERB:ADD`

## 相關主題


[SFTMIME 命令參考](sftmime--command-reference.md)

 

 





