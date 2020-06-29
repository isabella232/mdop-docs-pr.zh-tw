---
title: 設定 MBAM 2.5 伺服器功能
description: 設定 MBAM 2.5 伺服器功能
author: dansimp
ms.assetid: 894d1080-5f13-48f7-8fde-82f8d440a4ed
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e6ba2fc49086acf698f61b9997505c8fa884c0eb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809728"
---
# 設定 MBAM 2.5 伺服器功能


在[安裝 MBAM 2.5 伺服器軟體](installing-the-mbam-25-server-software.md)之後，請使用此資訊做為設定 Microsoft BitLocker 管理和監控（MBAM）2.5 伺服器功能的開始位置。 您可以使用兩種方法來設定 MBAM：

-   MBAM Server 設定精靈

-   Windows PowerShell Cmdlet

## 開始設定 MBAM 伺服器功能之前


開始設定 MBAM 伺服器功能之前，請先複習並完成下列步驟：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">步驟</th>
<th align="left">取得指示的位置</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>針對 MBAM 查看建議的架構。</p></td>
<td align="left"><p><a href="high-level-architecture-for-mbam-25.md" data-raw-source="[High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md)">MBAM 2.5 的概要架構</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>查看 MBAM 支援的設定。</p></td>
<td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)">MBAM 2.5 支援的組態</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>在每個伺服器上完成必要的先決條件。</p></td>
<td align="left"><ul>
<li><p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)">獨立拓撲與 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必要條件</a></p></li>
<li><p><a href="mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md" data-raw-source="[MBAM 2.5 Server Prerequisites that Apply Only to the Configuration Manager Integration Topology](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)">僅適用於 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必要條件</a></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>在您要設定 MBAM 伺服器功能的每個伺服器上安裝 MBAM Server 軟體。</p></td>
<td align="left"><p><a href="installing-the-mbam-25-server-software.md" data-raw-source="[Installing the MBAM 2.5 Server Software](installing-the-mbam-25-server-software.md)">安裝 MBAM 2.5 伺服器軟體</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>查看使用 Windows PowerShell 來設定 MBAM 伺服器功能的先決條件（如果您使用此方法來設定 MBAM 伺服器功能）。</p></td>
<td align="left"><p><a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)">使用 Windows PowerShell 設定 MBAM 2.5 伺服器功能</a></p></td>
</tr>
</tbody>
</table>

 

## 配置 MBAM Server 功能的步驟


下表中的每個資料列描述您將根據[針對 MBAM 2.5 建議的高層次架構](high-level-architecture-for-mbam-25.md)，在個別伺服器上設定的功能。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">要安裝的功能</th>
<th align="left">取得指示的位置</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>設定資料庫。</p></td>
<td align="left"><p><a href="how-to-configure-the-mbam-25-databases.md" data-raw-source="[How to Configure the MBAM 2.5 Databases](how-to-configure-the-mbam-25-databases.md)">如何設定 MBAM 2.5 資料庫</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>設定報告。</p></td>
<td align="left"><p><a href="how-to-configure-the-mbam-25-reports.md" data-raw-source="[How to Configure the MBAM 2.5 Reports](how-to-configure-the-mbam-25-reports.md)">如何設定 MBAM 2.5 報告</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>設定 web 應用程式。</p></td>
<td align="left"><p><a href="how-to-configure-the-mbam-25-web-applications.md" data-raw-source="[How to Configure the MBAM 2.5 Web Applications](how-to-configure-the-mbam-25-web-applications.md)">如何設定 MBAM 2.5 Web 應用程式</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>設定 System Center Configuration Manager 整合（如果適用的話）。</p></td>
<td align="left"><p><a href="how-to-configure-the-mbam-25-system-center-configuration-manager-integration.md" data-raw-source="[How to Configure the MBAM 2.5 System Center Configuration Manager Integration](how-to-configure-the-mbam-25-system-center-configuration-manager-integration.md)">如何設定 MBAM 2.5 System Center Configuration Manager 整合</a></p></td>
</tr>
</tbody>
</table>

 

如需 MBAM Server 功能設定的事件清單，請參閱[伺服器事件記錄](server-event-logs.md)。



## 相關主題


設定 MBAM 2.5 伺服器功能
 

 
## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。




