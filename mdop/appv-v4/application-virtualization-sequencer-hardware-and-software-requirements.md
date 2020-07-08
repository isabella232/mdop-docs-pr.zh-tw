---
title: Application Virtualization Sequencer 硬體和軟體需求
description: Application Virtualization Sequencer 硬體和軟體需求
author: dansimp
ms.assetid: c88a1b5b-23e1-4460-afa9-a5f37e32eb05
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d68afe4d4a3f6f301d38f2e86139d94319583467
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802290"
---
# Application Virtualization Sequencer 硬體和軟體需求


本主題描述執行 Microsoft Application Virtualization （App-v） Sequencer 的電腦所建議的最低硬體和軟體需求。

**重要** 您必須使用具有系統管理員許可權的帳戶來執行 App-v 排序器（**SFTSequencer.exe**），因為 sequencer 會對本機系統進行的變更。 這些變更可以包括將檔案寫入**C:\\program files files**目錄、進行登錄、啟動及停止服務、更新檔案的安全性描述項，以及變更許可權。

 

您必須先將乾淨的作業系統映射還原至順序電腦，然後才能安裝排序器並排序每個應用程式。 您可以使用下列其中一種方法來還原執行排序器的電腦：

-   重新格式化硬碟並重新安裝作業系統。

-   使用另一個磁片影像軟體，在執行 Sequencer 影像的電腦上還原硬碟。

-   還原虛擬作業系統映射，例如 Microsoft 虛擬電腦影像。 使用虛擬機器可讓清理的順序環境輕鬆地在最低的管理中重複使用。

下列清單概括了執行 App-v 排序器的建議硬體需求。

首先列出的是 Microsoft Application Virtualization （App-v） 4.6 SP2 的需求，後面接著是應用程式 V 4.6 SP2 之前的版本需求。

### <a href="" id="hardware-requirements-"></a>硬體需求

-   處理器-英特爾奔騰 III，1 GHz （32位或64位）。 排序流程是單一線程處理，不會利用雙處理器。

-   記憶體-1GB 或更新版本（建議使用2GB）。

-   硬碟-40 gb 硬碟空間，至少可提供 15 GB 的可用硬碟空間。 我們建議您至少有三倍您要排序之應用程式的硬碟空間需要。

    **記事** 排序需要大量的磁片使用量。 較快的磁片速度可能會減少排序時間。

     

### App-v 4.6 SP2 的軟體需求

下列清單列出執行 App-v 4.6 SP2 排序器所支援的作業系統。

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
<td align="left"><p>SP3</p></td>
<td align="left"><p>x86</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Vista</p></td>
<td align="left"><p>企業、企業或旗艦版</p></td>
<td align="left"><p>SP2</p></td>
<td align="left"><p>x86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows7</p></td>
<td align="left"><p>專業版、企業版或旗艦版</p></td>
<td align="left"><p>沒有 service pack 或 SP1</p></td>
<td align="left"><p>x86 和 x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows8</p></td>
<td align="left"><p>Pro 或 Enterprise Edition</p></td>
<td align="left"><p></p></td>
<td align="left"><p>x86 和 x64</p></td>
</tr>
</tbody>
</table>

 

**記事** 應用程式虛擬化（App-v） 4.6 SP2 排序器支援這些作業系統的32位與64位版本。

 

您應該將執行排序器的電腦設定為在目的電腦上安裝的相同應用程式。

### 應用程式 V 4.6 SP2 之前版本的軟體需求

下列清單概述針對應用程式 V 4.6 SP2 之前的版本執行 Sequencer 所支援的作業系統。

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

### App-v 4.6 SP2 的遠端桌面服務的軟體需求

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
<td align="left"><p>Windows Server2003 R2</p></td>
<td align="left"><p>標準版、企業版或資料中心版本</p></td>
<td align="left"><p>SP2</p></td>
<td align="left"><p>x86</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008</p></td>
<td align="left"><p>標準版、企業版或資料中心版本</p></td>
<td align="left"><p>SP2</p></td>
<td align="left"><p>x86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008 R2</p></td>
<td align="left"><p>標準版、企業版或資料中心版本</p></td>
<td align="left"><p>沒有 service pack 或 SP1</p></td>
<td align="left"><p>x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2012</p></td>
<td align="left"><p>標準版、企業版或資料中心版本</p></td>
<td align="left"><p></p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
</tbody>
</table>

 

**記事** 應用程式虛擬化（App-v）4.6 遠端桌面服務的 SP2 支援這些作業系統的32位與64位版本。

 

### 在 App-v 4.6 SP2 之前的版本的遠端桌面服務的軟體需求

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
<td align="left"><p>沒有 service pack 或 SP2</p></td>
<td align="left"><p>x86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008</p></td>
<td align="left"><p>標準版、企業版或資料中心版本</p></td>
<td align="left"><p>SP1 或 SP2</p></td>
<td align="left"><p>x86</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008 R2</p></td>
<td align="left"><p>標準版、企業版或資料中心版本</p></td>
<td align="left"><p>沒有 service pack 或 SP1</p></td>
<td align="left"><p>x64</p></td>
</tr>
</tbody>
</table>

 

**記事** 應用程式虛擬化（App-v）4.6 遠端桌面服務的 SP2 支援這些作業系統的32位與64位版本。

 

## 相關主題


[Application Virtualization Client 硬體和軟體需求](application-virtualization-client-hardware-and-software-requirements.md)

[Application Virtualization 系統需求](application-virtualization-system-requirements.md)

[如何安裝 Application Virtualization Sequencer](how-to-install-the-application-virtualization-sequencer.md)

[如何升級 Application Virtualization Sequencer](how-to-upgrade-the-application-virtualization-sequencer.md)

 

 





