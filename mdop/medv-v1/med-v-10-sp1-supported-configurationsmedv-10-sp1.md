---
title: MED-V 1.0 SP1 支援的組態
description: MED-V 1.0 SP1 支援的組態
author: dansimp
ms.assetid: 4dcf37c4-a061-43d2-878c-28efc87c3cdd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 5a707e8a3d59a423308f9f735ff38df9e235fbf5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810394"
---
# MED-V 1.0 SP1 支援的組態


本主題將說明在您的環境中安裝並執行 Microsoft 企業桌面虛擬化（MED-V） 1.0 Service Pack 1 （SP1）所需的需求。

## MED-V 1.0 SP1 用戶端系統需求


### MED-V 用戶端的作業系統需求

下表列出 MED-V 1.0 SP1 用戶端安裝支援的作業系統。

**注意**  
Microsoft 提供目前 service pack 的支援，在某些情況下，也是最前面的 service pack。 若要尋找您產品的支援時程表，請參閱[支援的生命週期 Service pack](https://go.microsoft.com/fwlink/?LinkId=31975) （ https://go.microsoft.com/fwlink/?LinkId=31975) 。 如需 Microsoft 支援週期原則的其他相關資訊，請參閱[Microsoft 支援週期支援原則常見問題](https://go.microsoft.com/fwlink/?LinkId=31976)（ https://go.microsoft.com/fwlink/?LinkId=31976) 。



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
<td align="left"><p>Windows XP</p></td>
<td align="left"><p>專業版</p></td>
<td align="left"><p>SP2 或 SP3</p></td>
<td align="left"><p>x86</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Vista</p></td>
<td align="left"><p>企業、企業或旗艦版</p></td>
<td align="left"><p>SP1 或 SP2</p></td>
<td align="left"><p>x86</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows 7</p></td>
<td align="left"><p>專業版、企業版或旗艦版</p></td>
<td align="left"><p>無</p></td>
<td align="left"><p>x86 或 x64</p></td>
</tr>
</tbody>
</table>



**注意**  
MED-V 用戶端不會在原生 x64 模式下執行。 相反地，MED-V 會在64位電腦上的 Windows 64 位（WOW64）模式的 Windows 上執行。



下表列出 MED-V 1.0 SP1 中支援的每個作業系統所需的最低 RAM。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">作業系統</th>
<th align="left">最低需要的 RAM</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows XP 專業版</p></td>
<td align="left"><p>1 GB</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Vista</p></td>
<td align="left"><p>2 GB</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows 7 x86</p></td>
<td align="left"><p>2 GB</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 7 x64</p></td>
<td align="left"><p>3 GB</p></td>
</tr>
</tbody>
</table>



### <a href="" id="med-v-1-0-sp1-client-configuration-"></a>MED-V 1.0 SP1 用戶端設定

**.NET Framework 版本**

MED-V 1.0 SP1 用戶端安裝支援下列版本的 Microsoft .NET Framework：

-   .NET Framework 2.0 或 .NET Framework 2.0 SP1

-   .NET Framework 3.0 或 .NET Framework 3.0 SP1

-   .NET Framework 3.5 或 .NET Framework 3.5 SP1

**虛擬化引擎**

Microsoft Virtual PC 2007 SP1 中，Microsoft 知識庫文章974918中所述的修正程式支援下列設定中的 MED-V 1.0 SP1 用戶端安裝：

-   靜態虛擬硬碟（VHD）檔案

-   多個 VHD 檔案位於同一個目錄中

-   動態 VHD 檔案

**網際網路瀏覽器**

Windows Internet Explorer 7 和 Windows Internet Explorer 8 支援 MED-V 1.0 SP1 用戶端安裝。

**Microsoft Hyper-V Server**

Microsoft Hyper-v Server 環境不支援 MED-V 用戶端。

## MED-V 1.0 SP1 工作區系統需求


MED-V 1.0 SP1 會從 MED-V 1.0 提供對系統需求的變更。

### MED-V 工作區作業系統需求

下表列出 MED-V 1.0 SP1 工作區支援的作業系統。

**注意**  
Microsoft 提供目前 service pack 的支援，在某些情況下，也是最前面的 service pack。 若要尋找您產品的支援時程表，請參閱[支援的生命週期 Service pack](https://go.microsoft.com/fwlink/?LinkId=31975) （ https://go.microsoft.com/fwlink/?LinkId=31975) 。 如需 Microsoft 支援週期原則的其他相關資訊，請參閱[Microsoft 支援週期支援原則常見問題](https://go.microsoft.com/fwlink/?LinkId=31976)（ https://go.microsoft.com/fwlink/?LinkId=31976) 。



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
<td align="left"><p>Windows 2000</p></td>
<td align="left"><p>專業版</p></td>
<td align="left"><p>以後</p></td>
<td align="left"><p>X86</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows XP</p></td>
<td align="left"><p>專業版</p></td>
<td align="left"><p>SP2 或 SP3</p>
<div class="alert">
<strong>注意</strong><br/><p>建議使用 SP3，以確保 MED-V 工作區將與未來版本的 MED-V 相容。</p>
</div>
<div>

</div></td>
<td align="left"><p>x86</p></td>
</tr>
</tbody>
</table>



### <a href="" id="med-v-1-0-sp1-workspace-configuration-"></a>MED-V 1.0 SP1 工作區配置

**.NET Framework 版本**

MED-V 需要下列其中一個支援的 Microsoft .NET Framework 版本，才能安裝 MED-V 1.0 SP1 工作區：

-   .NET Framework 2.0 SP1

-   .NET Framework 3.0 SP1

-   .NET Framework 3.5 或 .NET Framework 3.5 SP1

**注意**  
我們建議使用 .NET Framework 3.5 SP1，以確保 MED-V-V 工作區與未來的 MED-V 版本相容。



**網際網路瀏覽器**

已支援 windows Internet Explorer 6 SP2 及 Windows Internet Explorer 7 （適用于 MED-V 1.0 SP1 工作區安裝）。

### <a href="" id="med-v-workspace-images-"></a>MED-V 工作區圖像

MED-V 工作區圖像必須使用 Virtual PC 2007 SP1 建立。

## MED-V 1.0 SP1 伺服器系統需求


MED-V 1.0 SP1 會從 MED-V 1.0 提供對系統需求的變更。

### MED-V 1.0 伺服器作業系統需求

下表列出 MED-V 1.0 SP1 伺服器安裝支援的作業系統。

**注意**  
Microsoft 提供目前 service pack 的支援，在某些情況下，也是最前面的 service pack。 若要尋找您產品的支援時程表，請參閱[支援的生命週期 Service pack](https://go.microsoft.com/fwlink/?LinkId=31975) （ https://go.microsoft.com/fwlink/?LinkId=31975) 。 如需 Microsoft 支援週期原則的其他相關資訊，請參閱[Microsoft 支援週期支援原則常見問題](https://go.microsoft.com/fwlink/?LinkId=31976)（ https://go.microsoft.com/fwlink/?LinkId=31976) 。



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
<td align="left"><p>Standard 或 Enterprise</p></td>
<td align="left"><p>SP1 或 SP2</p></td>
<td align="left"><p>X86 或 x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2008 R2</p></td>
<td align="left"><p>Standard 或 Enterprise</p></td>
<td align="left"><p>無</p></td>
<td align="left"><p>x64</p></td>
</tr>
</tbody>
</table>



### <a href="" id="med-v-1-0-sp1-server-configuration-"></a>MED-V 1.0 SP1 伺服器設定

**.NET Framework 版本**

MED-V 需要下列其中一個支援的 Microsoft .NET Framework 版本，才能安裝 MED-V 1.0 SP1 工作區：

-   .NET Framework 2.0 或 .NET Framework 2.0 SP1

-   .NET Framework 3.0 或 .NET Framework 3.0 SP1

-   .NET Framework 3.5 或 .NET Framework 3.5 SP1

**Microsoft SQL Server 版本**

如果 SQL Server 是從 MED-V 1.0 SP1 SP1 中的本機或遠端安裝，則在 MED-V 1.0 SP1 支援下列版本的 Microsoft SQL Server：

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
<th align="left">Service Pack</th>
<th align="left">系統架構</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>SQL Server 2005</p></td>
<td align="left"><p>Express、Standard 或 Enterprise Edition</p></td>
<td align="left"><p>SP2</p></td>
<td align="left"><p>X86 或 x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>SQL Server 2008</p></td>
<td align="left"><p>Express、Standard 或 Enterprise</p></td>
<td align="left"><p>無</p></td>
<td align="left"><p>X86 或 x64</p></td>
</tr>
</tbody>
</table>



**Microsoft Hyper-V Server**

在 Microsoft Hyper-v server 環境中支援 MED-V 伺服器。

## MED-V 1.0 SP1 全球化資訊


雖然不是以英文以外的語言發行 MED-V，但是對於 MED-V 1.0 SP1 用戶端、工作區和伺服器安裝，支援下列 Windows 作業系統語言版本：

-   英文

-   法文

-   德文

-   義大利文

-   西班牙文

-   葡萄牙文 (巴西)

-   荷蘭文 (荷蘭)

-   日文









