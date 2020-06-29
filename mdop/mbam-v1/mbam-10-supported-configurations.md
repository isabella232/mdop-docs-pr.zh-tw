---
title: MBAM 1.0 支援的組態
description: MBAM 1.0 支援的組態
author: dansimp
ms.assetid: 1f5ac58e-6a3f-47df-8a9b-4b57631ab9ee
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 2c72320379d1c9328a6b40537d37998402b1b38b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811456"
---
# MBAM 1.0 支援的組態


本主題將說明在您的環境中安裝並執行 Microsoft BitLocker 管理和監控（MBAM）的必要需求。

## <a href="" id="---------mbam-server-system-requirements"></a> MBAM 伺服器系統需求


### 伺服器作業系統需求

下表列出 Microsoft BitLocker 系統管理和監視伺服器安裝支援的作業系統。

**注意**  
Microsoft 提供目前 service pack 的支援，在某些情況下，也是最前面的 service pack。 若要尋找您產品的支援時程表，請參閱[支援的生命週期服務套件](https://go.microsoft.com/fwlink/p/?LinkId=31975)。 如需 Microsoft 支援週期原則的其他相關資訊，請參閱[Microsoft 支援週期支援原則常見問題](https://go.microsoft.com/fwlink/p/?LinkId=31976)。



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
<td align="left"><p>Windows Server 2008</p></td>
<td align="left"><p>標準版、企業版、資料中心或 Web 服務器</p></td>
<td align="left"><p>僅限 SP2</p></td>
<td align="left"><p>32 位元或 64 位元</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2008 R2</p></td>
<td align="left"><p>標準版、企業版、資料中心或 Web 服務器</p></td>
<td align="left"></td>
<td align="left"><p>64 位元</p></td>
</tr>
</tbody>
</table>



**警告**  
不支援在網網域控制站電腦上安裝 MBAM 服務、報表或資料庫。



### <a href="" id="server-random-access-memory--ram--requirements-"></a>伺服器隨機存取記憶體（RAM）需求

沒有任何特定于 MBAM 伺服器安裝的 RAM 需求。

### <a href="" id="sql-server-database-requirements-"></a>SQL Server 資料庫需求

下表列出 MBAM 伺服器功能安裝支援的 SQL Server 版本。

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">MBAM Server 功能</th>
<th align="left">SQL Server 版本</th>
<th align="left">版本</th>
<th align="left">Service Pack</th>
<th align="left">系統架構</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>合規性與審計報告</p></td>
<td align="left"><p>Microsoft SQL Server 2008 </p></td>
<td align="left"><p>R2、標準、企業、資料中心或開發人員版本</p></td>
<td align="left"><p>SP2</p></td>
<td align="left"><p>32 位元或 64 位元</p></td>
</tr>
<tr class="even">
<td align="left"><p>恢復與硬體資料庫</p></td>
<td align="left"><p>Microsoft SQL Server 2008 </p></td>
<td align="left"><p>R2、企業版、資料中心或開發人員版本</p>
<div class="alert">
<strong>重要</strong><br/><p>MBAM 復原和硬體資料庫伺服器功能安裝不支援 SQL Server 標準版。</p>
</div>
<div>

</div></td>
<td align="left"><p>SP2</p></td>
<td align="left"><p>32 位元或 64 位元</p></td>
</tr>
<tr class="odd">
<td align="left"><p>合規性和審核資料庫</p></td>
<td align="left"><p>Microsoft SQL Server 2008 </p></td>
<td align="left"><p>R2、標準、企業、資料中心或開發人員版本</p></td>
<td align="left"><p>SP2</p></td>
<td align="left"><p>32 位元或 64 位元</p></td>
</tr>
</tbody>
</table>



## <a href="" id="---------mbam-client-system-requirements"></a> MBAM 用戶端系統需求


### 用戶端作業系統需求

下表列出 MBAM 用戶端安裝支援的作業系統。

**注意**  
Microsoft 提供目前 service pack 的支援，在某些情況下，也是最前面的 service pack。 若要尋找您產品的支援時程表，請參閱[支援的生命週期服務套件](https://go.microsoft.com/fwlink/p/?LinkId=31975)。 如需 Microsoft 支援週期原則的其他相關資訊，請參閱[Microsoft 支援週期支援原則常見問題](https://go.microsoft.com/fwlink/p/?LinkId=31976)。



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
<td align="left"><p>Windows 7</p></td>
<td align="left"><p>企業版</p></td>
<td align="left"><p>無、SP1</p></td>
<td align="left"><p>32 位元或 64 位元</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 7</p></td>
<td align="left"><p>旗艦版</p></td>
<td align="left"><p>無、SP1</p></td>
<td align="left"><p>32 位元或 64 位元</p></td>
</tr>
</tbody>
</table>



### <a href="" id="client-ram-requirements-"></a>用戶端 RAM 需求

不是 MBAM 用戶端安裝所特有的 RAM 需求。

## 相關主題


[規劃部署 MBAM 1.0](planning-to-deploy-mbam-10.md)

[MBAM 1.0 部署必要條件](mbam-10-deployment-prerequisites.md)









