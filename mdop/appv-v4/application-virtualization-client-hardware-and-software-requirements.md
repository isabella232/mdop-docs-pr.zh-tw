---
title: Application Virtualization Client 硬體和軟體需求
description: Application Virtualization Client 硬體和軟體需求
author: dansimp
ms.assetid: 8b877a2c-5721-4b22-a47f-e2838d58ab12
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 5b828f59ba36099b4f6a545cd5bbcb3c72d24e3e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802334"
---
# Application Virtualization Client 硬體和軟體需求


本主題描述安裝應用程式虛擬化桌面用戶端的建議最低硬體和軟體配置，以及適用于遠端桌面服務的應用程式虛擬化用戶端（以前稱為 [終端服務]）。

## 應用程式虛擬化桌面用戶端


下列清單包含應用程式虛擬化桌面用戶端的建議最低硬體和軟體需求。 首先列出的是 Microsoft Application Virtualization （App-v） 4.6 SP2 的需求，後面接著是應用程式 V 4.6 SP2 之前的版本需求。

**記事** 應用程式虛擬化（App-v）桌面用戶端不需要任何額外的處理器或 RAM 資源，超出主機作業系統的需求。

 

### 硬體需求

所有版本都適用于硬體需求。

-   處理器-請參閱您所使用之作業系統的建議系統需求。

-   RAM —請參閱您所使用之作業系統的建議系統需求。

-   磁片：30MB 以進行安裝，並6GB 快取。

### App-v 4.6 SP2 的軟體需求

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
<th align="left">結構 SKU</th>
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
<td align="left"><p>企業版、企業版或旗艦版</p></td>
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

如果您使用的是 Setup.exe 方法，系統會自動安裝下列軟體必備元件。 如果您使用的是 Setup.msi 安裝程式，則必須先安裝下列產品。
- **Microsoft Visual c + + 2005 SP1 可再發行套件（x86）**-如需安裝 Microsoft Visual c + + 2005 SP1 可再發行套件（x86）的詳細資訊，請參閱[Microsoft Visual c + + 2005 SP1 可再發行套件（x86）](https://go.microsoft.com/fwlink/?LinkId=119961) https://go.microsoft.com/fwlink/?LinkId=119961) （ 針對 App-V 用戶端的版本 4.5 SP2，請從[Microsoft Visual c + + 2005 Service Pack 1 可再發行套件 [ATL Security Update](https://go.microsoft.com/fwlink/?LinkId=169360) （]）下載 Vcredist\_x86.exe https://go.microsoft.com/fwlink/?LinkId=169360) 。
  -   **Microsoft CORE Xml services （MSXML） 6.0 SP1 （x86）**：如需安裝 MICROSOFT Core xml SERVICES （msxml） 6.0 SP1 （x86）的詳細資訊，請參閱[Microsoft core XML services （MSXML） 6.0 SP1 （x86）](https://go.microsoft.com/fwlink/?LinkId=63266) （ https://go.microsoft.com/fwlink/?LinkId=63266) 。

針對應用程式虛擬化（App-v）4.6 桌面用戶端，如果您使用的是 Setup.exe 方法，則會自動安裝下列額外的軟體必備元件。 如果您使用的是 Setup.msi 的安裝程式，您也必須使用所列的其他先決條件進行安裝。

-   **Microsoft VisualC + + 2008SP1 可再發行套件（x86）**-如需安裝 Microsoft VisualC + + 2008 Sp1 可再發行套件（x86）的詳細資訊，請參閱[Microsoft VisualC + + 2008 Sp1](https://go.microsoft.com/fwlink/?LinkId=150700)可重新發佈套件（x86）（） https://go.microsoft.com/fwlink/?LinkId=150700) 。

### 應用程式 V 4.6 SP2 之前版本的軟體需求

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
<th align="left">結構 SKU</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>WindowsXP</p></td>
<td align="left"><p>專業版</p></td>
<td align="left"><p>SP2 或 SP3</p></td>
<td align="left"><p>x86 和 x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Vista</p></td>
<td align="left"><p>企業版、企業版或旗艦版</p></td>
<td align="left"><p>沒有 service pack、SP1 或 SP2</p></td>
<td align="left"><p>x86 和 x64</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows7 ¹</p></td>
<td align="left"><p>專業版、企業版或旗艦版</p></td>
<td align="left"><p>沒有 service pack 或 SP1</p></td>
<td align="left"><p>x86 和 x64</p></td>
</tr>
</tbody>
</table>
¹支援 app-v 4.5 SP1 和 SP2、App-v 4.6 和 4.6 SP1

應用程式虛擬化（App-v）4.6 桌面用戶端支援這些作業系統的 x86 和 x64 Sku。

如果您使用的是 Setup.exe 方法，系統會自動安裝下列軟體必備元件。 如果您使用的是 Setup.msi 安裝程式，則必須先安裝下列產品。

-   <strong>Microsoft Visual c + + 2005 SP1 可再發行套件（x86） </strong> -如需安裝 Microsoft Visual c + + 2005 SP1 可再發行套件（x86）的詳細資訊，請參閱 <a href="https://go.microsoft.com/fwlink/?LinkId=119961" data-raw-source="[Microsoft Visual C++ 2005 SP1 Redistributable Package (x86)](https://go.microsoft.com/fwlink/?LinkId=119961)"> Microsoft Visual c + + 2005 SP1 可再發行套件（x86） </a> （ <a href="https://go.microsoft.com/fwlink/?LinkId=119961" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=119961"> https://go.microsoft.com/fwlink/?LinkId=119961 </a> ）。 針對 App-V 用戶端的版本 4.5 SP2，請從 <a href="https://go.microsoft.com/fwlink/?LinkId=169360" data-raw-source="[Microsoft Visual C++ 2005 Service Pack 1 Redistributable Package ATL Security Update](https://go.microsoft.com/fwlink/?LinkId=169360)"> Microsoft Visual c + + 2005 Service Pack 1 可轉散發元件套件 ATL Security Update </a> （）下載 Vcredist_x86.exe <a href="https://go.microsoft.com/fwlink/?LinkId=169360" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=169360"> https://go.microsoft.com/fwlink/?LinkId=169360 </a> 。

-   <strong>Microsoft Core XML Services （MSXML） 6.0 SP1 （x86） </strong> ：如需安裝 Microsoft CORE Xml services （msxml） 6.0 SP1 （x86）的詳細資訊，請參閱 <a href="https://go.microsoft.com/fwlink/?LinkId=63266" data-raw-source="[Microsoft Core XML Services (MSXML) 6.0 SP1 (x86)](https://go.microsoft.com/fwlink/?LinkId=63266)"> MICROSOFT Core xml SERVICES （msxml） 6.0 SP1 （x86） </a> （ <a href="https://go.microsoft.com/fwlink/?LinkId=63266" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=63266"> https://go.microsoft.com/fwlink/?LinkId=63266 </a> ）。

-   <strong>Microsoft 應用程式錯誤報表 </strong> ：此軟體的安裝套裝程式含在 <strong> </strong> 自解壓封存檔案的 Support\Watson 資料夾中。

針對應用程式虛擬化（App-v）4.6 桌面用戶端，如果您使用的是 Setup.exe 方法，則會自動安裝下列額外的軟體必備元件。 如果您使用的是 Setup.msi 的安裝程式，您也必須使用所列的其他先決條件進行安裝。

-   <strong>Microsoft Visual c + + 2008 SP1 可再發行套件（x86） </strong> -如需安裝 Microsoft Visual c + + 2008 SP1 可再發行套件（x86）的詳細資訊，請參閱 <a href="https://go.microsoft.com/fwlink/?LinkId=150700" data-raw-source="[Microsoft Visual C++ 2008 SP1 Redistributable Package (x86)](https://go.microsoft.com/fwlink/?LinkId=150700)"> Microsoft Visual c + + 2008 SP1 可再發行套件（x86） </a> （ <a href="https://go.microsoft.com/fwlink/?LinkId=150700" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=150700"> https://go.microsoft.com/fwlink/?LinkId=150700 </a> ）。

## 遠端桌面服務的應用程式虛擬化用戶端

以下是適用于遠端桌面服務之應用程式虛擬化用戶端的建議硬體和軟體需求。 這些需求首先會列在 appv461_3，接著是前一個應用程式 V 4.6 SP2 版本的需求。

遠端桌面服務的 Application Virtualization （App-v）用戶端不需要任何額外的處理器或 RAM 資源，超出主機作業系統的需求。

### 硬體需求

所有版本都適用于硬體需求。

-   處理器-請參閱您所使用之作業系統的建議系統需求。

-   RAM —請參閱您所使用之作業系統的建議系統需求。 這些需求也取決於使用者和應用程式的數量。

-   磁片：30MB 以進行安裝，並6GB 快取。

### App-v 4.6 SP2 的軟體需求

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
<th align="left">結構 SKU</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows Server2003 R2</p></td>
<td align="left"><p>標準版、企業版或資料中心版本</p></td>
<td align="left"><p>SP2</p></td>
<td align="left"><p>x86 和 x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008</p></td>
<td align="left"><p>標準版、企業版或資料中心版本</p></td>
<td align="left"><p>SP2</p></td>
<td align="left"><p>x86 和 x64</p></td>
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
<td align="left"><p>x64</p></td>
</tr>
</tbody>
</table>

如果您使用的是 Setup.exe 方法，系統會自動安裝下列軟體必備元件。 如果您使用的是 Setup.msi 安裝程式，則必須先安裝下列產品。

-   **Microsoft VisualC + + 2005SP1 可再發行套件（x86）**-如需安裝 microsoft VisualC + + 2005 sp1 可再發行套件（x86）的詳細資訊，請參閱[Microsoft VisualC + + 2005 Sp1 可再發行套件（](https://go.microsoft.com/fwlink/?LinkId=119961) x86）（） https://go.microsoft.com/fwlink/?LinkId=119961) 。 針對應用程式 V 用戶端的4.5 版本 4.5 SP2，請從[Microsoft Visual c + + 2005 Service Pack 1 可再發行套件 [ATL Security Update](https://go.microsoft.com/fwlink/?LinkId=169360) （]）下載 Vcredist\_x86.exe https://go.microsoft.com/fwlink/?LinkId=169360) 。

-   **Microsoft CORE Xml services （MSXML） 6.0 sp1 （x86）**：如需安裝 MICROSOFT Core xml SERVICES （msxml） 6.0 sp1 （x86）的詳細資訊，請參閱[Microsoft core XML services （MSXML） 6.0 sp1 （x86）](https://go.microsoft.com/fwlink/?LinkId=63266) （ https://go.microsoft.com/fwlink/?LinkId=63266) 。

-   **Microsoft 應用程式錯誤報表**：此軟體的安裝套裝程式含在自解壓封存檔案的**Support\\Watson**資料夾中。

針對應用程式虛擬化（App-v）4.6 桌面用戶端，如果您使用的是 Setup.exe 方法，則會自動安裝下列額外的軟體必備元件。 如果您使用的是 Setup.msi 的安裝程式，您也必須使用所列的其他先決條件進行安裝。

-   **Microsoft VisualC + + 2008SP1 可再發行套件（x86）**-如需安裝 Microsoft VisualC + + 2008 Sp1 可再發行套件（x86）的詳細資訊，請參閱[Microsoft VisualC + + 2008 Sp1](https://go.microsoft.com/fwlink/?LinkId=150700)可重新發佈套件（x86）（） https://go.microsoft.com/fwlink/?LinkId=150700) 。

### 應用程式 V 4.6 SP2 之前版本的軟體需求

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
<th align="left">結構 SKU</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows Server2003</p></td>
<td align="left"><p>標準版、企業版或資料中心版本</p></td>
<td align="left"><p>SP1 或 SP2</p></td>
<td align="left"><p>x86 和 x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2003 R2</p></td>
<td align="left"><p>標準版、企業版或資料中心版本</p></td>
<td align="left"><p>沒有 service pack 或 SP2</p></td>
<td align="left"><p>x86 和 x64</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008</p></td>
<td align="left"><p>標準版、企業版或資料中心版本</p></td>
<td align="left"><p>SP1 或 SP2</p></td>
<td align="left"><p>x86 和 x64</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008 R2</p></td>
<td align="left"><p>標準版、企業版或資料中心版本</p></td>
<td align="left"><p>沒有 service pack 或 SP1</p></td>
<td align="left"><p>x64</p></td>
</tr>
</tbody>
</table>

適用于遠端桌面服務的應用程式虛擬化（App-v）4.6 用戶端支援這些作業系統的 x86 和 x64 Sku。

## 相關主題
- [Application Virtualization Sequencer 硬體和軟體需求](application-virtualization-sequencer-hardware-and-software-requirements.md)
- [Application Virtualization 系統需求](application-virtualization-system-requirements.md)
- [如何使用命令列安裝用戶端](how-to-install-the-client-by-using-the-command-line-new.md)
- [如何手動安裝 Application Virtualization Client](how-to-manually-install-the-application-virtualization-client.md)
- [如何升級 Application Virtualization Client](how-to-upgrade-the-application-virtualization-client.md)
