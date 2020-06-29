---
title: 如何只允許系統管理員啟用連線群組
description: 如何只允許系統管理員啟用連線群組
author: dansimp
ms.assetid: 42ca3157-5d85-467b-a148-09404f8f737a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 083d6386f02996d35255f90958705798f2cd5fb9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800597"
---
# 如何只允許系統管理員啟用連線群組


您可以設定 App-v 用戶端，讓只有系統管理員（而非最終使用者）可以啟用或停用連線群組。 在舊版 App-v 中，您不能防止使用者執行這些工作。

**記事** 
**從 app-v 5.0 SP3 開始，支援這項功能。**

 

使用下列其中一種方法，只允許系統管理員啟用或停用連線群組。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">方法</th>
<th align="left">步驟</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>群組原則設定</p></td>
<td align="left"><p>啟用位於下列 [群群組原則物件] 節點中的 [必須發佈為系統管理員] 群組原則設定：</p>
<p><strong>[電腦設定 &gt; 原則] &gt; 管理範本 &gt; 系統 &gt; app-v &gt; 發佈</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p>PowerShell Cmdlet</p></td>
<td align="left"><p><strong> </strong> 使用 <strong> – RequirePublishAsAdmin 參數執行 AppvClientConfiguration Cmdlet </strong> 。</p>
<p>參數值：</p>
<ul>
<li><p>0-False</p></li>
<li><p>1-True</p></li>
</ul>
<p><strong>範例： </strong> ： Set-AppvClientConfiguration – RequirePublishAsAdmin1</p></td>
</tr>
</tbody>
</table>

 

您**有應用程式-V 的建議**嗎？ 在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。 **有應用程式-V 問題嗎？** 使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。

## 相關主題


[管理連線群組](managing-connection-groups51.md)

 

 





