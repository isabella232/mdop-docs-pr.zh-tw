---
title: Configuration Manager 整合功能的必要條件
description: Configuration Manager 整合功能的必要條件
author: dansimp
ms.assetid: b318cbd3-b009-44b8-991b-f7364c1cae88
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: af7abd50f6218810dd6718f091512b48fee32652
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810899"
---
# Configuration Manager 整合功能的必要條件


如果您使用 System Center Configuration Manager 整合拓朴部署 MBAM，我們建議使用三個伺服器架構，如[MBAM 2.5 的高層架構與 Configuration Manager 整合拓撲](high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md)中所述。 這個架構可以支援500000用戶端電腦。

**重要**  
當您使用 Configuration Manager 2007 時，Configuration Manager 整合拓撲安裝不支援 Windows To Go。



## Configuration Manager 整合功能的一般先決條件


當您使用 Configuration Manager 安裝 MBAM 時，除了獨立拓朴的先決條件之外，還需要下列額外的先決條件。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">必備</th>
<th align="left">其他資訊</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Configuration Manager 伺服器是 Configuration Manager 系統中的主要網站。</p></td>
<td align="left"><p>無</p></td>
</tr>
<tr class="even">
<td align="left"><p>硬體清查用戶端代理程式位於 Configuration Manager 伺服器上。</p></td>
<td align="left"><p>針對 System Center 2012 Configuration Manager，請參閱 <a href="https://go.microsoft.com/fwlink/?LinkId=301685" data-raw-source="[How to Configure Hardware Inventory in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301685)"> 如何在 Configuration Manager 中設定硬體清查 </a> 。</p>
<p>如需 Configuration Manager 2007 的詳細說明，請參閱 <a href="https://go.microsoft.com/fwlink/?LinkId=301656" data-raw-source="[How to Configure Hardware Inventory for a Site](https://go.microsoft.com/fwlink/?LinkId=301656)"> 如何設定網站的硬體清點 </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>根據您所使用的 Configuration Manager 版本，會啟用下列其中一項：</p>
<ul>
<li><p>合規性設定-（系統中心 2012 Configuration Manager）</p></li>
<li><p>所需的建構管理（DCM）用戶端代理程式–（Configuration Manager 2007）</p></li>
</ul></td>
<td align="left"><p>針對 System Center 2012 Configuration Manager，請參閱 <a href="https://go.microsoft.com/fwlink/?LinkId=301687" data-raw-source="[Configuring Compliance Settings in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301687)"> 在 Configuration Manager 中設定合規性設定 </a> 。</p>
<p>針對 Configuration Manager 2007，請參閱 <a href="https://go.microsoft.com/fwlink/?LinkId=301686" data-raw-source="[Desired Configuration Management Client Agent Properties](https://go.microsoft.com/fwlink/?LinkId=301686)"> 所需的設定管理用戶端代理程式屬性 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>[Configuration Manager] 中定義了 [報表服務點]。 SQL Server Reporting Services （SSRS）所需。</p></td>
<td align="left"><p>針對 System Center 2012 Configuration Manager，請參閱 <a href="https://go.microsoft.com/fwlink/?LinkId=301689" data-raw-source="[Prerequisites for Reporting in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301689)"> Configuration manager 中的報告先決條件 </a> 。</p>
<p>如需 Configuration Manager 2007 的詳細說明，請參閱 <a href="https://go.microsoft.com/fwlink/?LinkId=301688" data-raw-source="[How to Create a Reporting Services Point for SQL Reporting Services](https://go.microsoft.com/fwlink/?LinkId=301688)"> 如何為 SQL Reporting Services 建立 Reporting Services 點 </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Configuration Manager 2007 需要 Microsoft .NET Framework 2。0</p></td>
<td align="left"><p>Configuration Manager 2007 中所需的建構管理（DCM）用戶端代理程式需要 .NET Framework 2.0 來報告合規性。</p>
<div class="alert">
<strong>注意</strong><br/><p>安裝 .NET Framework 3.5 時會自動安裝 .NET Framework 2.0。</p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



## 使用 Configuration Manager 安裝 MBAM 所需的許可權


若要使用 Configuration Manager 安裝 MBAM，您必須在 Configuration Manager 中擁有具有下表所列許可權的安全性角色的系統管理使用者。 該表也會顯示您必須擁有的許可權（除了基本的電腦系統管理員許可權之外），才能安裝 MBAM 伺服器。

**下表中的許可權適用于這兩個版本的 Configuration Manager。**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">權限</th>
<th align="left">MBAM Server 功能</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>SQL Server 實例登入伺服器角色：-dbcreator-processadmin</p></td>
<td align="left"><p>- 復原資料庫-審核資料庫</p></td>
</tr>
<tr class="even">
<td align="left"><p>SSRS 實例許可權：-建立資料夾-發佈報表</p></td>
<td align="left"><p>- System Center Configuration Manager 整合</p></td>
</tr>
</tbody>
</table>



**System Center 2012 Configuration Manager**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">權限</th>
<th align="left">Configuration Manager 伺服器功能</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Configuration Manager 網站許可權：-讀取</p></td>
<td align="left"><p>System Center Configuration Manager 整合</p></td>
</tr>
<tr class="even">
<td align="left"><p>Configuration Manager 集合許可權：-建立-刪除-已讀-修改-部署設定項目</p></td>
<td align="left"><p>System Center Configuration Manager 整合</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Configuration Manager 設定專案許可權：-建立-刪除-已讀取</p></td>
<td align="left"><p>System Center Configuration Manager 整合</p></td>
</tr>
</tbody>
</table>



**Configuration Manager 2007**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">權限</th>
<th align="left">Configuration Manager 伺服器功能</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Configuration Manager 網站許可權：-讀取</p></td>
<td align="left"><p>System Center Configuration Manager 整合</p></td>
</tr>
<tr class="even">
<td align="left"><p>Configuration Manager 集合許可權：-建立-Delete-ReadResource</p></td>
<td align="left"><p>System Center Configuration Manager 整合</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Configuration Manager 設定項目許可權：-建立-刪除-已讀取-發佈</p></td>
<td align="left"><p>System Center Configuration Manager 整合</p></td>
</tr>
</tbody>
</table>



## 對 mof 檔案所需的變更


若要讓用戶端電腦透過 MBAM Configuration Manager 報告來報告 BitLocker 合規性詳細資料，您必須編輯 System Center 2012 Configuration Manager 和 Microsoft System Center Configuration Manager 2007 的 Configuration mof 檔案和 Sms \ [_def 的 mof 檔。 如需相關指示，請參閱[僅適用于 Configuration Manager 整合拓朴的 MBAM 2.5 Server 先決條件](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)。



## 相關主題


[獨立拓撲與 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必要條件](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md)

[僅適用於 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必要條件](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)



## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





