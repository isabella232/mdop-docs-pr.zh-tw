---
title: 如何使用 PowerShell 命令執行 DaRT 工作
description: 如何使用 PowerShell 命令執行 DaRT 工作
author: dansimp
ms.assetid: bc788b00-38c7-4f57-a832-916b68264d89
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f8ff87aa09555b93ca04a6ec7fa5dd4ba8504514
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810473"
---
# 如何使用 PowerShell 命令執行 DaRT 工作


Microsoft Diagnostics 與修復工具組（DaRT）8.0 提供下列所列的 Windows PowerShell Cmdlet 集合。 系統管理員可以使用這些 PowerShell Cmdlet，從命令提示字元執行各種 DaRT 8.0 伺服器工作，而不是從 DaRT 復原影像嚮導執行。

## 使用 PowerShell 命令來管理 DaRT


使用這裡所述的 PowerShell Cmdlet 來管理 DaRT。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名稱</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>複製 DartImage</p></td>
<td align="left"><p>在 CD、DVD 或 USB 磁片磁碟機上使用 ISO。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Export-DartImage</p></td>
<td align="left"><p>允許包含 DaRT 映射的來源 WIM 檔案轉換成 ISO 檔案。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>新-DartConfiguration</p></td>
<td align="left"><p>建立將 DaRT 工具組套用到 Windows 影像所需的 DaRT 設定物件。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Set-DartImage</p></td>
<td align="left"><p>將 DartConfiguration 物件套用至已安裝的 Windows 影像。 這包括新增所有檔案、配置及套件相依性。</p></td>
</tr>
</tbody>
</table>

 

## 相關主題


[使用 PowerShell 管理 DaRT 8.0](administering-dart-80-using-powershell-dart-8.md)

 

 





