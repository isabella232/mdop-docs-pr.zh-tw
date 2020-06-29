---
title: 排序器硬體和軟體需求
description: 排序器硬體和軟體需求
author: dansimp
ms.assetid: 36084e12-831d-452f-a4a4-45f07f9ce471
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0d4e12a5803a3c9033513424826b49bc0bca5885
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800838"
---
# 排序器硬體和軟體需求


本主題描述執行 Microsoft Application Virtualization （App-v） Sequencer 的電腦所建議的最低硬體和軟體需求。

您必須先將乾淨的作業系統映射還原至順序電腦，然後才能安裝排序器並排序每個應用程式。 您可以使用下列其中一種方法來還原執行排序器的電腦：

-   重新格式化硬碟並重新安裝作業系統。

-   使用另一個磁片影像軟體，在執行 Sequencer 影像的電腦上還原硬碟。

下列清單概括了執行 App-v 排序器的建議硬體需求。

### <a href="" id="hardware-requirements-"></a>硬體需求

-   處理器-英特爾奔騰 III，1 GHz （32位或64位）。 排序流程是單一線程處理，不會利用雙處理器。

-   記憶體-1GB 或更新版本，建議 2 GB。

-   硬碟-40 gb 硬碟空間，至少可提供 15 GB 的可用硬碟空間。 我們建議您至少有三倍您要排序之應用程式的硬碟空間需要。

    **記事** 排序需要大量的磁片使用量。 較快的磁片速度可能會減少排序時間。

     

### 軟體需求

下列清單列出執行排序器所支援的作業系統。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">作業系統</th>
<th align="left">版本</th>
<th align="left">Service Pack</th>
<th align="left">系統架構</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>WindowsXP</p></td>
<td align="left"><p>專業版</p></td>
<td align="left"><p>SP2 或 SP3</p></td>
<td align="left"><p>x86</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Vista</p></td>
<td align="left"><p>企業、企業或旗艦版</p></td>
<td align="left"><p>沒有 service pack、SP1 或 SP2</p></td>
<td align="left"><p>x86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows7 ¹</p></td>
<td align="left"><p>專業版、企業版或旗艦版</p></td>
<td align="left"><p></p></td>
<td align="left"><p>x86</p></td>
</tr>
</tbody>
</table>

 

¹支援在 SP1 或 SP2 中使用 app-v 4.5，且僅限 App-v 4。6

**記事** 應用程式虛擬化（App-v） 4.6 Sequencer 支援這些作業系統的32位與64位版本。

 

您應該將執行排序器的電腦設定為在目的電腦上安裝的相同應用程式。

### 遠端桌面服務的軟體需求

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">作業系統</th>
<th align="left">版本</th>
<th align="left">Service Pack</th>
<th align="left">系統架構</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows Server2003</p></td>
<td align="left"><p>標準版、企業版或資料中心版本</p></td>
<td align="left"><p>SP1 或 SP2</p></td>
<td align="left"><p>x86</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2003 R2</p></td>
<td align="left"><p>標準版、企業版或資料中心版本</p></td>
<td align="left"><p></p></td>
<td align="left"><p>x86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008</p></td>
<td align="left"><p>標準版、企業版或資料中心</p></td>
<td align="left"><p>SP1 或 SP2</p></td>
<td align="left"><p>x86</p></td>
</tr>
</tbody>
</table>

 

**記事** 適用于遠端桌面服務的 Application Virtualization （App-v）4.6 支援這些作業系統的32位與64位版本。

 

## 相關主題


[Application Virtualization Sequencer 概觀](application-virtualization-sequencer-overview.md)

 

 





