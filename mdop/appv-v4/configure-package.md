---
title: CONFIGURE PACKAGE
description: CONFIGURE PACKAGE
author: dansimp
ms.assetid: acc7eaa8-6ada-47b9-a655-2ca2537605b9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dc8b315b68349cc9834316786b0bf15d4ac3c5cd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802181"
---
# CONFIGURE PACKAGE


讓使用者能夠變更封裝資訊清單檔案、套件來源、載入觸發程式類型，或針對套件載入目標。

`SFTMIME CONFIGURE PACKAGE:package-name [/MANIFEST manifest-path]                 [/OVERRIDEURL url] [/AUTOLOADNEVER] [/AUTOLOADONREFRESH]                 [/AUTOLOADONLOGIN] [/AUTOLOADONLAUNCH]                 [/AUTOLOADTARGET {NONE|ALL|PREVUSED}]                 [/LOG log-pathname | /CONSOLE | /GUI]                 [/NO-UPDATE-FTA-SHORTCUT {TRUE|FALSE} {/GLOBAL}]`

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
<td align="left"><p>列出套件中包含之應用程式的資訊清單檔案路徑或 URL，以及其所有發佈資訊。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/OVERRIDEURL &lt; URL&gt;</p></td>
<td align="left"><p>套件的 SFT 檔案位置。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/AUTOLOADNEVER</p></td>
<td align="left"><p>已針對套件關閉背景載入。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/AUTOLOADONREFRESH</p></td>
<td align="left"><p>在發佈重新整理之後，會執行背景載入。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/AUTOLOADONLOGIN</p></td>
<td align="left"><p>在使用者登入時，會執行背景載入。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/AUTOLOADONLAUNCH</p></td>
<td align="left"><p>使用者從套件啟動應用程式後，就會執行背景載入。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/AUTOLOADTARGET &lt; 目標&gt;</p></td>
<td align="left"><p>指示將會 autoloaded 套件中的哪些應用程式。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>所有</p></td>
<td align="left"><p>不論是否有任何/AUTOLOADONxxx 標誌，都不會執行任何 autoloading。</p></td>
</tr>
<tr class="even">
<td align="left"><p>同時</p></td>
<td align="left"><p>如果啟用 autoload 觸發程式，則無論是否已啟動，套件中的所有應用程式都會載入到快取中。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>PREVUSED</p></td>
<td align="left"><p>如果啟用 autoload 觸發程式，則在使用者先前已啟動此套件中的任何應用程式時，就會載入套件。</p></td>
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

 

針對版本 4.6 SP2，新增了下列選項。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>[/NO-UPDATE-FTA-SHORTCUT {TRUE |FALSE} {/GLOBAL}]</p></td>
<td align="left"><p>如果設為 TRUE，則會針對套件（每位使用者）或全域方式建立登錄值，如果已指定/GLOBAL 標誌。</p>
<p>如果設定為 FALSE，則會移除登錄值，並重新安裝套件的檔案類型關聯（FTA）。</p>
<p>如果未指定，就會發生標準 FTA 和快捷方式發佈行為。 如果您在 App-V 4.6 SP2 用戶端上執行任何後續的發佈重新整理作業，則不會變更已設定此登錄值之套件的快速鍵及 FTAs; 除非您重設旗標，否則就不會在系統啟動或使用者登入時註冊快速鍵及 FTAs。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/GLOBAL</p></td>
<td align="left"><p>與/NO-UPDATE-FTA-SHORTCUT 標誌搭配使用。 如果/GLOBAL 標誌存在，則表示將為所有使用者建立該套件的登錄值。 根據預設，只會針對此使用者建立登錄值。</p></td>
</tr>
</tbody>
</table>

 

## 相關主題


[SFTMIME 命令參考](sftmime--command-reference.md)

 

 





