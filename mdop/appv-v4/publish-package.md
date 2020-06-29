---
title: PUBLISH PACKAGE
description: PUBLISH PACKAGE
author: dansimp
ms.assetid: a33e72dd-194f-4283-8e99-4584ab13de53
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 00b63389986f495d9405939245a50575bae453f9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800894"
---
# PUBLISH PACKAGE


發佈整個套件的內容。

`SFTMIME PUBLISH PACKAGE:package-name /MANIFEST manifest-path [/GLOBAL]                 [/LOG log-pathname | /CONSOLE | /GUI]`

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

 

**重要** 套件必須已新增至應用程式虛擬化用戶端，且需要資訊清單檔案。

若要使用**GLOBAL**參數，必須以本機管理員身分執行 [發佈套件] 命令;否則，只需要**ManageTypes**和**PublishShortcut**許可權。

不使用**GLOBAL**參數的發佈可授予使用者對封裝中應用程式的存取權，並將資訊清單中列出的檔案類型和快速鍵發佈至使用者的設定檔。

使用**GLOBAL**參數發佈時，會將資訊清單中列出的檔案類型和快速鍵新增至 [所有使用者] 設定檔。

如果在通話之前不是全域套件，且使用了**全域**參數，則會將套件設為全域，且可供所有使用者使用。

 

## 相關主題


[SFTMIME 命令參考](sftmime--command-reference.md)

 

 





