---
title: App-V 5.0 支援的組態
description: App-V 5.0 支援的組態
author: dansimp
ms.assetid: 3787ff63-7ce7-45a8-8f01-81b4b6dced34
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 60236743d2a6b418ca7f4705168a7bf064b82156
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800681"
---
# App-V 5.0 支援的組態


本主題指定在您的環境中安裝並執行 Microsoft Application Virtualization （App-v）5.0 所需的需求。

**重要**  
**本文支援的設定僅適用于 app-v 5.0**。 如需適用于 App-v 5.0 Service Pack 的支援設定，請參閱下列網頁：

-   [App-V 5.0 SP1 的新功能](whats-new-in-app-v-50-sp1.md)

-   [關於 App-V 5.0 SP2](about-app-v-50-sp2.md)

-   [App-V 5.0 SP3 支援的組態](app-v-50-sp3-supported-configurations.md)



## <a href="" id="---------app-v-5-0-server-system-requirements"></a> App-V 5.0 伺服器系統需求


**重要**  
App-v 5.0 server 不支援下列案例：



-   部署到執行 Microsoft Windows Server Core 的電腦。

-   部署到執行舊版 App-V 5.0 伺服器元件的電腦。

    **注意**  
    您可以使用 app-v 4.5 輕型流式處理伺服器（LWS）伺服器，並行安裝 app-v 5.0。 不支援使用 app-v 4.5 應用程式虛擬化管理服務（HWS）伺服器並行部署 app-v 5.0。



-   部署到執行 Microsoft SQL Server Express edition 的電腦。

-   管理伺服器資料庫或報告資料庫的遠端部署。 安裝程式必須直接在執行 Microsoft SQL 的電腦上執行，才能成功進行資料庫安裝。

-   部署到網網域控制站。

-   不支援短路徑。 如果您打算使用短路徑，您必須建立新的卷。

### 管理伺服器作業系統需求

下表列出 App-V 5.0 管理伺服器安裝支援的作業系統。

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
<th align="left">Service pack</th>
<th align="left">系統架構</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server 2008 （標準版、企業版、Datacenter 或 Web 服務器）</p></td>
<td align="left"><p>R2</p></td>
<td align="left"><p>SP1 及更新版本</p></td>
<td align="left"><p>64 位元</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Windows Server 2012 （標準版、資料中心）</p></td>
<td align="left"><p></p></td>
<td align="left"></td>
<td align="left"><p>64 位元</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server 2012 （標準版、資料中心）</p></td>
<td align="left"><p>R2</p></td>
<td align="left"></td>
<td align="left"><p>64 位元</p></td>
</tr>
</tbody>
</table>



**重要**  
不支援將管理伺服器角色部署到已啟用遠端桌面共用（RDS）的電腦。



### <a href="" id="management-server-hardware-requirements-"></a>管理伺服器硬體需求

-   處理器-1.4 GHz 或更快的64位（x64）處理器

-   RAM-1 GB RAM （64位）

-   磁碟空間-200 MB 可用的硬碟空間，不含內容目錄。

### 發佈伺服器作業系統需求

下表列出 App-V 5.0 發佈伺服器安裝所支援的作業系統。

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
<th align="left">Service pack</th>
<th align="left">系統架構</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server 2008 （標準版、企業版、Datacenter 或 Web 服務器）</p></td>
<td align="left"><p>R2</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 位元</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Windows Server 2012 （標準版、資料中心）</p></td>
<td align="left"><p></p></td>
<td align="left"></td>
<td align="left"><p>64 位元</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server 2012 （標準版、資料中心）</p></td>
<td align="left"><p>R2</p></td>
<td align="left"></td>
<td align="left"><p>64 位元</p></td>
</tr>
</tbody>
</table>



### <a href="" id="publishing-server-hardware-requirements-"></a>發佈伺服器硬體需求

-   處理器-1.4 GHz 或更快。 64位（x64）處理器

-   RAM-2 GB RAM （64位）

-   磁碟空間-200 MB 可用硬碟空間。 不含內容目錄

### 報表伺服器作業系統需求

下表列出 App-V 5.0 報表服務器安裝支援的作業系統。

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
<td align="left"><p>Microsoft Windows Server 2008 （標準版、企業版、Datacenter 或 Web 服務器）</p></td>
<td align="left"><p>R2</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 位元</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Windows Server 2012 （標準版、資料中心）</p></td>
<td align="left"><p></p></td>
<td align="left"></td>
<td align="left"><p>64 位元</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server 2012 （標準版、資料中心）</p></td>
<td align="left"><p>R2</p></td>
<td align="left"></td>
<td align="left"><p>64 位元</p></td>
</tr>
</tbody>
</table>



### <a href="" id="reporting-server-hardware-requirements-"></a>報表服務器硬體需求

-   處理器-1.4 GHz 或更快。 64位（x64）處理器

-   RAM-2 GB RAM （64位）

-   磁碟空間-200 MB 可用硬碟空間

### <a href="" id="sql-server-database-requirements-"></a>SQL Server 資料庫需求

下表列出 App-V 5.0 資料庫和伺服器安裝支援的 SQL Server 版本。

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
<th align="left">App-v 5.0 伺服器類型</th>
<th align="left">SQL Server 版本</th>
<th align="left">版本</th>
<th align="left">Service pack</th>
<th align="left">系統架構</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>管理/報告</p></td>
<td align="left"><p>Microsoft SQL Server 2008</p>
<p>（標準版、企業版、資料中心或開發人員版本，具有下列功能： <strong>資料庫引擎服務 </strong> 。）</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 位元或 64 位元</p></td>
</tr>
<tr class="even">
<td align="left"><p>管理/報告</p></td>
<td align="left"><p>Microsoft SQL Server 2008 </p>
<p>（標準版、企業版、資料中心或開發人員版本，具有下列功能： <strong>資料庫引擎服務 </strong> 。）</p></td>
<td align="left"><p>R2</p></td>
<td align="left"><p>SP2</p></td>
<td align="left"><p>32 位元或 64 位元</p></td>
</tr>
<tr class="odd">
<td align="left"><p>管理/報告</p></td>
<td align="left"><p>Microsoft SQL Server 2012</p>
<p>（標準版、企業版、資料中心或開發人員版本，具有下列功能： <strong>資料庫引擎服務 </strong> 。）</p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 位元或 64 位元</p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-client-supp-cfgs"></a> App-V 5.0 用戶端系統需求


下表列出 App-V 5.0 用戶端安裝支援的作業系統。

**注意**  
Microsoft 提供目前 service pack 的支援，在某些情況下，也是最前面的 service pack。 若要尋找您產品的支援時程表，請參閱[支援的生命週期服務套件](https://go.microsoft.com/fwlink/p/?LinkId=31975)。 如需 Microsoft 支援週期原則的其他相關資訊，請參閱[Microsoft 支援週期支援原則常見問題](https://go.microsoft.com/fwlink/p/?LinkId=31976)。



<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">作業系統</th>
<th align="left">Service pack</th>
<th align="left">系統架構</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft Windows 7</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>32 位元或 64 位元</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Windows 8</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 位元或 64 位元</p></td>
</tr>
<tr class="odd">
<td align="left"><div class="alert">
<strong>重要</strong><br/><p>Windows 8.1 僅支援 App-v 5.0 SP2</p>
</div>
<div>

</div>
<p>Windows 8.1</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 位元或 64 位元</p></td>
</tr>
</tbody>
</table>



下列 App-V 用戶端安裝案例不受支援，但說明：

-   執行 Windows Server 的電腦

-   執行 App-v 4.6 SP1 或較舊版本的電腦

-   只有啟用 RDS 的伺服器才支援 App-v 5.0 遠端桌面服務用戶端

### <a href="" id="client-hardware-requirements-"></a>用戶端硬體需求

下列清單顯示 App-V 5.0 用戶端安裝所支援的硬體設定。

-   處理器-1.4 GHz 或更快的32位（x86）或64位（x64）處理器

-   RAM-1 GB （32位）或 2 GB （64位）

-   磁片：安裝 100 MB，不包括虛擬化應用程式所使用的磁碟空間。

## <a href="" id="---------app-v-5-0-remote-desktop-client-system-requirements"></a> App-v 5.0 遠端桌面用戶端系統需求


下表列出 App-V 5.0 遠端桌面用戶端安裝所支援的作業系統。

**注意**  
Microsoft 提供目前 service pack 的支援，在某些情況下，也是最前面的 service pack。 若要尋找您產品的支援時程表，請參閱[支援的生命週期服務套件](https://go.microsoft.com/fwlink/p/?LinkId=31975)。 如需 Microsoft 支援週期原則的其他相關資訊，請參閱[Microsoft 支援週期支援原則常見問題](https://go.microsoft.com/fwlink/p/?LinkId=31976)。



作業系統版本 Service pack Microsoft Windows Server 2008

R2

SP1

Microsoft Windows Server 2012

**重要**  
Windows Server 2012 R2 僅支援 App-v 5.0 SP2



Microsoft Windows Server 2012 （標準版、資料中心）

R2

64 位元



### <a href="" id="remote-desktop-client-hardware-requirements-"></a>遠端桌面用戶端的硬體需求

下列清單顯示 App-V 5.0 用戶端安裝所支援的硬體設定。

-   處理器-1.4 GHz 或更快的32位（x86）或64位（x64）處理器

-   RAM-1 GB （32位）或 2 GB （64位）

-   磁片：安裝 100 MB，不包括虛擬化應用程式所使用的磁碟空間。

## <a href="" id="---------app-v-5-0-sequencer-system-requirements"></a> App-v 5.0 Sequencer 系統需求


下表列出應用程式 V 5.0 排序器安裝支援的作業系統。

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
<th align="left">Service pack</th>
<th align="left">系統架構</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft Windows 7</p></td>
<td align="left"></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>32 位元與 64 位元</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Windows 8</p></td>
<td align="left"></td>
<td align="left"><p></p></td>
<td align="left"><p>32 位元與 64 位元</p></td>
</tr>
<tr class="odd">
<td align="left"><div class="alert">
<strong>重要</strong><br/><p>Windows 8.1 僅支援 App-v 5.0 SP2</p>
</div>
<div>

</div>
<p>Windows 8.1</p></td>
<td align="left"></td>
<td align="left"><p></p></td>
<td align="left"><p>32 位元或 64 位元</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Windows Server 2008</p></td>
<td align="left"><p>R2</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>32 位元與 64 位元</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server 2012</p></td>
<td align="left"></td>
<td align="left"><p></p></td>
<td align="left"><p>32 位元與 64 位元</p></td>
</tr>
<tr class="even">
<td align="left"><div class="alert">
<strong>重要</strong><br/><p>Windows Server 2012 R2 僅支援 App-v 5.0 SP2</p>
</div>
<div>

</div>
<p>Microsoft Windows Server 2012</p></td>
<td align="left"><p>R2</p></td>
<td align="left"></td>
<td align="left"><p>64 位元</p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-supp-ver-sccm"></a>系統中心 Configuration Manager 支援的版本


您可以使用 Microsoft System Center 2012 Configuration Manager 或 System Center 2012 R2 Configuration Manager 來管理 App-v virtual 應用程式、報告及其他功能。 下表列出每個適用版本 App-v 的 Configuration Manager 支援版本。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">支援的 Configuration Manager 版本</th>
<th align="left">App-V 版本</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft System Center 2012 Configuration Manager</p></td>
<td align="left"><ul>
<li><p>App-V 5。0</p></li>
<li><p>App-V 5.0 SP1</p></li>
<li><p>App-v 5.0 SP2</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>System Center 2012 R2 Configuration Manager</p></td>
<td align="left"><ul>
<li><p>App-V 5。0</p></li>
<li><p>App-V 5.0 SP1</p></li>
<li><p>App-v 5.0 SP2</p></li>
</ul></td>
</tr>
</tbody>
</table>



如需 Configuration Manager 與 App-v 整合的詳細資訊，請參閱[規劃 app-v 與 Configuration Manager 整合](https://technet.microsoft.com/library/jj822982.aspx)。






## 相關主題


[規劃部署 App-V](planning-to-deploy-app-v.md)

[App-V 5.0 必要條件](app-v-50-prerequisites.md)









