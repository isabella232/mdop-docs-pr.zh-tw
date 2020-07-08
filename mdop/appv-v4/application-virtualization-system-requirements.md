---
title: Application Virtualization 系統需求
description: Application Virtualization 系統需求
author: dansimp
ms.assetid: a2798dd9-168e-45eb-8103-e12e128fae7c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c160a7532b521bb41570b419b22b9e7daaec2987
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802249"
---
# Application Virtualization 系統需求


本主題描述 Microsoft Application Virtualization （App-v）管理伺服器與流式處理伺服器的最低硬體和軟體需求。

## 應用程式虛擬化管理與流式處理伺服器


下列清單包含 App V 管理伺服器與 App-v 流式處理伺服器的最低建議硬體和軟體需求。

### 硬體需求

-   處理器-英特爾奔騰 III，1 GHz

-   RAM-512 MB

-   磁碟空間-200 MB 可用硬碟空間，不含內容目錄

### 軟體需求

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
<td align="left"><p>標準版</p></td>
<td align="left"><p>SP1 或 SP2</p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2003</p></td>
<td align="left"><p>企業版或資料中心版本</p></td>
<td align="left"><p>SP1 或 SP2</p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2003 R2</p></td>
<td align="left"><p>標準版</p></td>
<td align="left"><p>沒有 service pack 或 SP2</p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2003 R2</p></td>
<td align="left"><p>企業版或資料中心版本</p></td>
<td align="left"><p>沒有 service pack 或 SP2</p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008</p></td>
<td align="left"><p>標準版、企業版或資料中心版本</p></td>
<td align="left"><p>SP1 或 SP2</p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008 R2 ¹</p></td>
<td align="left"><p>標準版、企業版或資料中心版本</p></td>
<td align="left"><p></p></td>
<td align="left"><p>x64</p></td>
</tr>
</tbody>
</table>

 

¹僅適用于 App-v 4.5 SP1 和 SP2。

## 資料存放區


下列清單包含在個別伺服器上安裝資料儲存區時所使用之電腦的最低建議硬體和軟體需求。 資料儲存區只有應用程式虛擬化管理伺服器需要。

### 硬體需求

-   處理器-英特爾奔騰 III，850 MHz

-   RAM-512 MB

-   磁碟空間-200 MB 可用硬碟空間

### 軟體需求

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
<td align="left"><p>標準版</p></td>
<td align="left"><p>SP1 或 SP2</p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2003</p></td>
<td align="left"><p>企業版或資料中心版本</p></td>
<td align="left"><p>SP1 或 SP2</p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2003 R2</p></td>
<td align="left"><p>標準版</p></td>
<td align="left"><p>沒有 service pack 或 SP2</p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2003 R2</p></td>
<td align="left"><p>企業版或資料中心版本</p></td>
<td align="left"><p>沒有 service pack 或 SP2</p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008</p></td>
<td align="left"><p>標準版、企業版或資料中心版本</p></td>
<td align="left"><p>SP1 或 SP2</p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008 R2 ¹</p></td>
<td align="left"><p>標準版、企業版或資料中心版本</p></td>
<td align="left"><p></p></td>
<td align="left"><p>x64</p></td>
</tr>
</tbody>
</table>

 

¹僅適用于 App-v 4.5 SP1 和 SP2。

-   資料庫-Microsoft SQL Server2000 SP3a 或 SP4，SQL Server2005 SP1，SP2，或 SP3，或 SQL Server2008，沒有 service pack 或 SP1 或 SQL Server2008 R2 （32位或64位）

-   Microsoft 資料存取元件-MDAC 2。7

-   網網域控制站-以中央驗證機構為基礎的 Active Directory 網域服務或 Windows NT 4.0 的主要網網域控制站（PDC）

## 管理 Web 服務


下列清單包含在不同的電腦上安裝應用程式虛擬化管理 Web 服務時建議的最低硬體和軟體需求。

### 硬體需求

-   處理器-英特爾奔騰 III，800 MHz

-   RAM-256 MB

-   磁碟空間-50 MB 可用硬碟空間

### 軟體需求

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
<td align="left"><p>標準版</p></td>
<td align="left"><p>SP1 或 SP2</p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2003</p></td>
<td align="left"><p>企業版或資料中心版本</p></td>
<td align="left"><p>SP1 或 SP2</p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2003 R2</p></td>
<td align="left"><p>標準版</p></td>
<td align="left"><p>沒有 service pack 或 SP2</p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2003 R2</p></td>
<td align="left"><p>企業版或資料中心版本</p></td>
<td align="left"><p>沒有 service pack 或 SP2</p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008</p></td>
<td align="left"><p>標準版、企業版或資料中心版本</p></td>
<td align="left"><p>SP1 或 SP2</p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008 R2 ¹</p></td>
<td align="left"><p>標準版、企業版或資料中心版本</p></td>
<td align="left"><p></p></td>
<td align="left"><p>x64</p></td>
</tr>
</tbody>
</table>

 

¹僅適用于 App-v 4.5 SP1 和 SP2。

-   網際網路資訊服務-已使用 Microsoft ASP.NET （IIS 7）設定的網際網路 information Services （IIS）6。0

-   Microsoft .NET Framework 2。0

## 管理主控台


下列清單包含在另一部電腦上安裝應用程式虛擬化管理主控台時所建議的最低硬體和軟體需求。

### 硬體需求

-   處理器-英特爾奔騰 III，450 MHz

-   RAM-256 MB

-   磁碟空間-200 MB 可用硬碟空間

### 軟體需求

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
<td align="left"><p>x86 或 x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Vista</p></td>
<td align="left"><p>企業版、企業版或旗艦版</p></td>
<td align="left"><p>沒有 service pack、SP1 或 SP2</p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows7</p></td>
<td align="left"><p>專業版、企業版或旗艦版</p></td>
<td align="left"><p></p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2003</p></td>
<td align="left"><p>標準版、企業版或資料中心版本</p></td>
<td align="left"><p>SP1 或 SP2</p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2003 R2</p></td>
<td align="left"><p>標準版、企業版或資料中心版本</p></td>
<td align="left"><p>沒有 service pack 或 SP2</p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008</p></td>
<td align="left"><p>標準版、企業版或資料中心版本</p></td>
<td align="left"><p>SP1 或 SP2</p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008 R2 ¹</p></td>
<td align="left"><p>標準版、企業版或資料中心版本</p></td>
<td align="left"><p></p></td>
<td align="left"><p>x64</p></td>
</tr>
</tbody>
</table>

 

¹僅適用于 App-v 4.5 SP1 和 SP2。

-   Microsoft 管理主控台-MMC 3.0 或更新版本

-   Microsoft .NET Framework 2.0 SP2 （最小值）

    **重要** 最小需求是 .NET Framework 2.0 SP2，如果您必須在執行 App-v 管理主控台的電腦上安裝 App-v 熱修復程式 KB980850 或後續的 App-v 熱修復程式。

     

## 相關主題


[Application Virtualization Client 硬體和軟體需求](application-virtualization-client-hardware-and-software-requirements.md)

[Application Virtualization Sequencer 硬體和軟體需求](application-virtualization-sequencer-hardware-and-software-requirements.md)

[如何針對以伺服器為基礎的部署設定伺服器](how-to-configure-servers-for-server-based-deployment.md)

[如何安裝伺服器和系統元件](how-to-install-the-servers-and-system-components.md)

[如何升級伺服器和系統元件](how-to-upgrade-the-servers-and-system-components.md)

 

 





