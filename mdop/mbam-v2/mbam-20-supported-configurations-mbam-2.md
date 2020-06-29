---
title: MBAM 2.0 支援的組態
description: MBAM 2.0 支援的組態
author: dansimp
ms.assetid: dca63391-39fe-4273-a570-76d0a2f8a0fd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 8f314adcf818c1bdb17b0b239a7469f97fa849e4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810238"
---
# MBAM 2.0 支援的組態


本主題透過使用獨立拓朴，指定在您的環境中安裝並執行 Microsoft BitLocker 管理和監控（MBAM）2.0 的需求。 如需適用于日後發行的支援設定，請參閱適用版本的檔。

如果您打算使用 Configuration Manager 拓撲來安裝 MBAM 2.0，並想要查看系統需求清單，請參閱[規劃使用 Configuration Manager 部署 MBAM](planning-to-deploy-mbam-with-configuration-manager-2.md)。

在生產環境中執行 MBAM 的建議設定是使用兩個伺服器（視您的可伸縮性需求而定）。 此設定最多可支援 200000 MBAM 用戶端。 如需獨立 MBAM 伺服器基礎結構的影像和描述，請參閱[適用于 MBAM 2.0 的高層次架構](high-level-architecture-for-mbam-20-mbam-2.md)。

**記事** Microsoft 提供目前 service pack 的支援，在某些情況下，也是最前面的 service pack。 若要尋找您產品的支援時程表，請參閱[支援的生命週期服務套件](https://go.microsoft.com/fwlink/p/?LinkId=31975)。 如需 Microsoft 支援週期原則的其他相關資訊，請參閱[Microsoft 支援週期支援原則常見問題](https://go.microsoft.com/fwlink/p/?LinkId=31976)。

 

## <a href="" id="---------mbam-server-system-requirements"></a> MBAM 伺服器系統需求


### 伺服器作業系統需求

下表列出 Microsoft BitLocker 系統管理和監視伺服器安裝支援的作業系統。

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
<th align="left">Service pack</th>
<th align="left">系統架構</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>WindowsServer2008 R2</p></td>
<td align="left"><p>標準版、企業版或資料中心版本</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 位元</p></td>
</tr>
<tr class="even">
<td align="left"><p>WindowsServer2012</p></td>
<td align="left"><p>標準版或資料中心版本</p></td>
<td align="left"></td>
<td align="left"><p>64 位元</p></td>
</tr>
</tbody>
</table>

 

**記事** 不支援在網網域控制站電腦上安裝 MBAM 服務、報表或資料庫。

 

### <a href="" id="server-processor--ram--and-disk-space-requirements-"></a>伺服器處理器、RAM 與磁碟空間需求

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
<td align="left"><p>8 GB</p></td>
<td align="left"><p>12 GB</p></td>
</tr>
<tr class="odd">
<td align="left"><p>可用磁碟空間</p></td>
<td align="left"><p>1 GB</p></td>
<td align="left"><p>2 GB</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="sql-server-database-requirements-"></a>SQLServer 資料庫需求

下表列出系統管理與監視伺服器功能安裝支援的 SQLServer 版本，其中包括復原資料庫、合規性和審核資料庫，以及合規性和審核報告。 資料庫還需要安裝 SQL Server 管理工具。

**記事** MBAM 本身不支援 SQL 群集、鏡像或可用性群組。 若要安裝資料庫，您必須在獨立的 SQL Server 上執行 MBAM 伺服器安裝。

 

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">SQL Server 版本</th>
<th align="left">版本</th>
<th align="left">Service pack</th>
<th align="left">系統架構</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>MicrosoftSQLServer2008 R2</p></td>
<td align="left"><p>標準版、企業版或資料中心版本</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 位元</p></td>
</tr>
<tr class="even">
<td align="left"><p>MicrosoftSQLServer2012</p></td>
<td align="left"><p>標準版、企業版或資料中心版本</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 位元</p></td>
</tr>
</tbody>
</table>

 

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
<td align="left"><p>8 GB</p></td>
<td align="left"><p>12 GB</p></td>
</tr>
<tr class="odd">
<td align="left"><p>可用磁碟空間</p></td>
<td align="left"><p>5 GB</p></td>
<td align="left"><p>5 GB 或以上</p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="---------mbam-client-system-requirements"></a> MBAM 用戶端系統需求


### 用戶端作業系統需求

下表列出 Microsoft BitLocker 系統管理和監視用戶端安裝支援的作業系統。

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
<th align="left">Service pack</th>
<th align="left">系統架構</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows7</p></td>
<td align="left"><p>企業版或旗艦版</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>32 位元或 64 位元</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows8</p></td>
<td align="left"><p>企業版</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 位元或 64 位元</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows To Go</p></td>
<td align="left"><p>Windows 8 企業版</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 位元或 64 位元</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="client-ram-requirements-"></a>用戶端 RAM 需求

Microsoft BitLocker 管理與監視用戶端安裝沒有任何 RAM 需求。

## <a href="" id="---------mbam-group-policy-system-requirements"></a> MBAM 群組原則系統需求


下表列出 Microsoft BitLocker 管理和監視群群組原則範本安裝所支援的作業系統。

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
<th align="left">Service pack</th>
<th align="left">系統架構</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows7</p></td>
<td align="left"><p>企業版或旗艦版</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>32 位元或 64 位元</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows8</p></td>
<td align="left"><p>企業版</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 位元或 64 位元</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2008 R2</p></td>
<td align="left"><p>標準版、企業版或資料中心版本</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 位元</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2012</p></td>
<td align="left"><p>標準版或資料中心版本</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 位元</p></td>
</tr>
</tbody>
</table>

 

## 相關主題


[規劃部署 MBAM 2.0](planning-to-deploy-mbam-20-mbam-2.md)

[MBAM 2.0 部署必要條件](mbam-20-deployment-prerequisites-mbam-2.md)

 

 





