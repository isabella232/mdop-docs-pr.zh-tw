---
title: UNPUBLISH PACKAGE
description: UNPUBLISH PACKAGE
author: dansimp
ms.assetid: 1651427c-72a5-4701-bb57-71e14a7a3803
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7704fb3ed03be4864a837767d9e890d28b63f175
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800758"
---
# UNPUBLISH PACKAGE


可讓您移除整個套件的快速鍵和檔案類型。

`SFTMIME UNPUBLISH PACKAGE:package-name [/CLEAR] [/GLOBAL]                 [/LOG log-pathname | /CONSOLE | /GUI]`

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
<td align="left"><p>套件的名稱。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/CLEAR</p></td>
<td align="left"><p>如果有的話，也會移除使用者設定。 （如需詳細資訊，請參閱本主題稍後的重要記事。）</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/GLOBAL</p></td>
<td align="left"><p>如果有，則會針對此電腦上的所有使用者取消發佈套件。</p></td>
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

 

**重要** 您必須先將套件新增至應用程式虛擬化用戶端，才能執行 [**取消發佈套件**] 命令。

若要使用**全域**，**取消發佈套件**必須以本機管理員身分執行;否則，只需要**ClearApp**許可權。

使用具有**全域**的**取消發佈套件**會移除套件的任何通用檔案類型和快速鍵。 [**清除**] 不適用。

使用不含**全域**的**取消發佈套件**會移除套件的使用者快速鍵和檔案類型，如果已設定**CLEAR** ，也會在使用者的內容底下移除使用者設定並停止背景載入。

**取消發佈套件**適用于使用作為**新增**、**編輯**及**發佈套件**之來源 ID 之相同套件名稱或 GUID 的應用程式。

無論使用/CLEAR 開關為何，**取消發佈套件**都會清除所有的使用者設定、快速鍵和檔案類型。

 

## 相關主題


[SFTMIME 命令參考](sftmime--command-reference.md)

 

 





