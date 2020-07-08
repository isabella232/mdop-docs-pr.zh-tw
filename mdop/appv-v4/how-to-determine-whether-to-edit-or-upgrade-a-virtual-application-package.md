---
title: 如何判斷是否要編輯或升級虛擬應用程式封裝
description: 如何判斷是否要編輯或升級虛擬應用程式封裝
author: dansimp
ms.assetid: 33dd5332-6802-46e0-9748-43fcc8f80aa3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b256a4927231613b6f2e688b5951adf57c9cb89a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801442"
---
# 如何判斷是否要編輯或升級虛擬應用程式封裝


您可以使用下表來協助判斷虛擬應用程式套件是否可開啟以供編輯，不論您是否需要建立新版本的套件，或是使用 App-v 排序器，是否有任何一個可用的選項。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">動作</th>
<th align="left">開啟以進行編輯</th>
<th align="left">開啟以進行升級</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>[查看套件屬性]。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="even">
<td align="left"><p>[查看套件變更歷程記錄]。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="odd">
<td align="left"><p>[查看關聯的套件檔案]。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="even">
<td align="left"><p>編輯註冊表設定。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="odd">
<td align="left"><p>查看其他套件設定（除了作業系統檔案屬性之外）。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="even">
<td align="left"><p>建立相關聯的 Windows Installer （MSI）。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="odd">
<td align="left"><p>[修改 OSD 檔案]。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="even">
<td align="left"><p>壓縮和解壓縮套件。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="odd">
<td align="left"><p>新增檔案類型關聯。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="even">
<td align="left"><p>重新命名快速鍵。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="odd">
<td align="left"><p>設定虛擬化登錄機碼的狀態（覆寫/合併）。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="even">
<td align="left"><p>設定虛擬化資料夾的狀態。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="odd">
<td align="left"><p>編輯虛擬檔案系統對應。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="even">
<td align="left"><p>查看套件的所有關聯作業系統檔案屬性。</p></td>
<td align="left"><p>否</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="odd">
<td align="left"><p>新增其他服務。</p></td>
<td align="left"><p>否</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="even">
<td align="left"><p>新增其他檔案。</p></td>
<td align="left"><p>否</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="odd">
<td align="left"><p>收集及設定關聯的安全性描述項。</p></td>
<td align="left"><p>否</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="even">
<td align="left"><p>套用安全性更新或升級至新版本。</p></td>
<td align="left"><p>否</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="odd">
<td align="left"><p>新增其他應用程式。</p></td>
<td align="left"><p>否</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="even">
<td align="left"><p>套用需要開啟應用程式的更新。</p></td>
<td align="left"><p>否</p></td>
<td align="left"><p>是</p></td>
</tr>
<tr class="odd">
<td align="left"><p>套用需要重新開機電腦的更新。</p></td>
<td align="left"><p>否</p></td>
<td align="left"><p>是</p></td>
</tr>
</tbody>
</table>

 

## 相關主題


[如何編輯現有的虛擬應用程式](how-to-edit-an-existing-virtual-application.md)

[如何升級現有的虛擬應用程式](how-to-upgrade-an-existing-virtual-application.md)

 

 





