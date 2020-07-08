---
title: 規劃使用設定管理員進行 MBAM 部署
description: 規劃使用設定管理員進行 MBAM 部署
author: dansimp
ms.assetid: fb768306-48c2-40b4-ac4e-c279db987391
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e8588ce03c86a8a5138d591327e5f95503dce5ad
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811270"
---
# 規劃使用設定管理員進行 MBAM 部署


若要使用 Configuration Manager 拓撲部署 MBAM，建議使用支援200000用戶端的三台伺服器架構。 使用個別的伺服器來執行 Configuration Manager，並在兩個伺服器上安裝基本的管理和監控功能，如快速入門中的架構影像所示[-搭配 Configuration Manager 使用 MBAM](getting-started---using-mbam-with-configuration-manager.md)。

**重要**  
當您安裝 MBAM 與 Configuration Manager 2007 的整合拓撲時，系統不支援 Windows To Go。



## 使用 Configuration Manager 安裝 MBAM 的部署先決條件


在使用 Configuration Manager 安裝 MBAM 之前，請確定您已符合下列先決條件：

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
<td align="left"><p>確定 Configuration Manager 伺服器是 Configuration Manager 系統中的主要網站。</p></td>
<td align="left"><p>無</p></td>
</tr>
<tr class="even">
<td align="left"><p>在 Configuration Manager 伺服器上啟用硬體清查用戶端代理程式。</p></td>
<td align="left"><p>如需 Configuration Manager 2007 的詳細說明，請參閱 <a href="https://go.microsoft.com/fwlink/?LinkId=301656" data-raw-source="[How to Configure Hardware Inventory for a Site](https://go.microsoft.com/fwlink/?LinkId=301656)"> 如何設定網站的硬體清點 </a> 。</p>
<p>針對 System Center 2012 Configuration Manager，請參閱 <a href="https://go.microsoft.com/fwlink/?LinkId=301685" data-raw-source="[How to Configure Hardware Inventory in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301685)"> 如何在 Configuration Manager 中設定硬體清查 </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>根據您所使用的 Configuration Manager 版本，啟用所需的設定管理（DCM）代理或合規性設定。</p></td>
<td align="left"><p>針對 Configuration Manager 2007，請啟用 [查看 <a href="https://go.microsoft.com/fwlink/?LinkId=301686" data-raw-source="[Desired Configuration Management Client Agent Properties](https://go.microsoft.com/fwlink/?LinkId=301686)"> 所需的建構管理用戶端代理程式屬性] </a> 。</p>
<p>針對 System Center 2012 Configuration Manager，請參閱 <a href="https://go.microsoft.com/fwlink/?LinkId=301687" data-raw-source="[Configuring Compliance Settings in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301687)"> 在 Configuration Manager 中設定合規性設定 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>在 Configuration Manager 中定義報表服務點。 SQL Reporting Services 所需。</p></td>
<td align="left"><p>如需 Configuration Manager 2007 的詳細說明，請參閱 <a href="https://go.microsoft.com/fwlink/?LinkId=301688" data-raw-source="[How to Create a Reporting Services Point for SQL Reporting Services](https://go.microsoft.com/fwlink/?LinkId=301688)"> 如何為 SQL Reporting Services 建立 Reporting Services 點 </a> 。</p>
<p>針對 System Center 2012 Configuration Manager，請參閱 <a href="https://go.microsoft.com/fwlink/?LinkId=301689" data-raw-source="[Prerequisites for Reporting in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301689)"> Configuration manager 中的報告先決條件 </a> 。</p></td>
</tr>
</tbody>
</table>



## <a href="" id="---------configuration-manager-supported-versions"></a> Configuration Manager 支援的版本


MBAM 支援下列版本的 Configuration Manager：

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">支援的版本</th>
<th align="left">Service pack</th>
<th align="left">系統架構</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft System Center Configuration Manager 2007 R2</p></td>
<td align="left"><p>SP1 或更新版本</p></td>
<td align="left"><p>64 位元</p>
<div class="alert">
<strong>注意</strong><br/><p>雖然 Configuration Manager 2007 是32位，您必須將它與 SQL Server 安裝在64位作業系統上，才能符合64位 MBAM 軟體。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft System Center 2012 Configuration Manager</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 位元</p></td>
</tr>
</tbody>
</table>



如需 Configuration Manager 伺服器支援的設定的清單，請參閱適用于您所使用之 Configuration Manager 版本的頁面。 MBAM 對於 Configuration Manager 伺服器沒有額外的系統需求。

## <a href="" id="---------mbam-and-sql-server-system-requirements"></a> MBAM 與 SQL Server 系統需求


MBAM 伺服器與 Configuration Manager 拓撲的 SQL Server 支援的設定和系統需求與獨立拓朴的配置和系統需求相同。 如需獨立的系統需求，請參閱[MBAM 2.0 支援](mbam-20-supported-configurations-mbam-2.md)的設定。 如需 Configuration Manager 拓撲的 MBAM 伺服器與 SQL Server 處理器、RAM 及磁碟空間需求，請參閱下列各節。

## MBAM 伺服器處理器、RAM 與磁碟空間需求 MBAM


下表列出當您使用 Configuration Manager 整合拓撲時，MBAM 伺服器的伺服器處理器、RAM 和磁碟空間需求。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">硬體元件</th>
<th align="left">最低需求</th>
<th align="left">建議的需求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>處理者</p></td>
<td align="left"><p>2.33 GHz</p></td>
<td align="left"><p>2.33 GHz 或以上</p></td>
</tr>
<tr class="even">
<td align="left"><p>RAM</p></td>
<td align="left"><p>4 GB</p></td>
<td align="left"><p>8 GB</p></td>
</tr>
<tr class="odd">
<td align="left"><p>可用磁碟空間</p></td>
<td align="left"><p>1 GB</p></td>
<td align="left"><p>2 GB</p></td>
</tr>
</tbody>
</table>



## SQL Server 處理器、RAM 與磁碟空間需求


下表列出當您使用 Configuration Manager 整合拓撲時，SQL Server 電腦的伺服器處理器、RAM 與磁碟空間需求。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">硬體元件</th>
<th align="left">最低需求</th>
<th align="left">建議的需求</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>處理者</p></td>
<td align="left"><p>2.33 GHz</p></td>
<td align="left"><p>2.33 GHz 或以上</p></td>
</tr>
<tr class="even">
<td align="left"><p>RAM</p></td>
<td align="left"><p>4 GB</p></td>
<td align="left"><p>8 GB</p></td>
</tr>
<tr class="odd">
<td align="left"><p>可用磁碟空間</p></td>
<td align="left"><p>5 GB</p></td>
<td align="left"><p>5 GB 或以上</p></td>
</tr>
</tbody>
</table>



## 安裝 MBAM Server 所需的許可權


若要使用 Configuration Manager 安裝 MBAM，您必須在 Configuration Manager 中擁有具有下表所列許可權的安全性角色的系統管理使用者。 該表也會顯示您必須擁有的許可權（除了基本的電腦系統管理員許可權之外），才能安裝 MBAM 伺服器。

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
<td align="left"><p>SQL 實例登入伺服器角色：-dbcreator-processadmin</p></td>
<td align="left"><p>- 復原資料庫-審核資料庫</p></td>
</tr>
<tr class="even">
<td align="left"><p>SQL Server Reporting Services 實例許可權：-建立資料夾-發佈報表</p></td>
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



## Configuration Manager 拓撲的 MBAM 功能部署順序


在 Configuration Manager 伺服器上部署 MBAM 時，您必須以下列順序完成部署工作：

1.  在 Configuration Manager 伺服器上編輯 configuration mof 檔案。

2.  建立或編輯 sms \ _def. mof 檔案 Configuration Manager 伺服器。

3.  在 Configuration Manager 伺服器上安裝 MBAM。

4.  在資料庫伺服器上安裝恢復資料庫和審核資料庫。

5.  在 [管理及監視伺服器] 上安裝 MBAM 功能。

## 使用 Configuration Manager 安裝 MBAM 的規劃檢查清單


此檢查清單列出建議的步驟，以及在規劃使用 Configuration Manager 進行 Microsoft BitLocker 管理及監視部署時要考慮的最高層次專案清單。 建議您將此檢查清單複製到試算表程式中，然後將它自訂為供您使用。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left">工作</th>
<th align="left">參考資料</th>
<th align="left">附註</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>請參閱快速入門資訊，這些資訊說明 Configuration Manager 如何與 MBAM 搭配運作，並顯示建議的高層次架構。</p></td>
<td align="left"><p><a href="getting-started---using-mbam-with-configuration-manager.md" data-raw-source="[Getting Started - Using MBAM with Configuration Manager](getting-started---using-mbam-with-configuration-manager.md)">開始使用 - 將 MBAM 與設定管理員搭配使用</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>請查看規劃資訊，其中描述部署的先決條件、支援的設定、所需的許可權，以及每個功能的部署順序。</p></td>
<td align="left"><p>規劃使用設定管理員進行 MBAM 部署</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>規劃及設定 MBAM 群組原則需求。</p></td>
<td align="left"><p><a href="planning-for-mbam-20-group-policy-requirements-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Group Policy Requirements](planning-for-mbam-20-group-policy-requirements-mbam-2.md)">MBAM 2.0 群組原則需求規劃</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>規劃及建立必要的 Active Directory 網域服務安全性群組，並規劃 MBAM 的本地安全性群組成員資格需求。</p></td>
<td align="left"><p><a href="planning-for-mbam-20-administrator-roles-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Administrator Roles](planning-for-mbam-20-administrator-roles-mbam-2.md)">MBAM 2.0 系統管理員角色規劃</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p>規劃部署 MBAM 用戶端部署。</p></td>
<td align="left"><p><a href="planning-for-mbam-20-client-deployment-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Client Deployment](planning-for-mbam-20-client-deployment-mbam-2.md)">MBAM 2.0 用戶端部署規劃</a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



## 相關主題


[使用 MBAM 搭配 Configuration Manager](using-mbam-with-configuration-manager.md)









