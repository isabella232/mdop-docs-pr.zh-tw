---
title: App-V 5.0 SP3 支援的組態
description: App-V 5.0 SP3 支援的組態
author: dansimp
ms.assetid: 08ced79a-0ed3-43c3-82e7-de01c1f33e81
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: b5a8858c703add3dc84c7eed4f62aa97e60ec9b0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800682"
---
# App-V 5.0 SP3 支援的組態


本主題指定在您的環境中安裝並執行 Microsoft Application Virtualization （App-v） 5.0 SP3 的需求。

## App-v Server 系統需求


本節列出所有應用程式 V 伺服器元件的作業系統和硬體需求。

### 不支援的 App-V 5.0 SP3 伺服器案例

App-V 5.0 SP3 伺服器不支援下列案例：

-   部署到執行 Microsoft Windows Server Core 的電腦。

-   部署到執行舊版 App-V 5.0 SP3 Server 元件的電腦。 您可以只使用 App-v 4.5 輕型流式處理伺服器（LWS）伺服器來安裝 App-v 5.0 SP3。 不支援使用 app-v 4.5 應用程式虛擬化管理服務（HWS）伺服器並行部署 app-v。

-   部署到執行 Microsoft SQL Server Express edition 的電腦。

-   管理伺服器資料庫或報告資料庫的遠端部署。 您必須直接在執行 Microsoft SQL Server 的電腦上執行安裝程式。

-   部署到網網域控制站。

-   短路徑。 如果您打算使用短路徑，您必須建立新的卷。

### 管理伺服器作業系統需求

下表列出 App-V 5.0 SP3 管理伺服器安裝所支援的作業系統。

**記事** Microsoft 提供目前 service pack 的支援，在某些情況下，也是最前面的 service pack。 若要尋找您產品的支援時程表，請參閱[支援的生命週期服務套件](https://go.microsoft.com/fwlink/p/?LinkId=31975)。 如需詳細資訊，請參閱[Microsoft 支援週期支援原則的常見問題](https://go.microsoft.com/fwlink/p/?LinkId=31976)。

 

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">作業系統</th>
<th align="left">Service Pack</th>
<th align="left">系統架構</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server 2012 R2</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 位元</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Windows Server 2012</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 位元</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server 2008 R2</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 位元</p></td>
</tr>
</tbody>
</table>

 

**重要** 不支援將管理伺服器角色部署到已啟用遠端桌面共用（RDS）的電腦。

 

### <a href="" id="management-server-hardware-requirements-"></a>管理伺服器硬體需求

-   處理器-1.4 GHz 或更快的64位（x64）處理器

-   RAM-1 GB RAM （64位）

-   磁碟空間-200 MB 可用硬碟空間，不含內容目錄

### 管理伺服器資料庫需求

下表列出 App-V 5.0 SP3 管理資料庫安裝所支援的 SQL Server 版本。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">SQL Server 版本</th>
<th align="left">Service pack</th>
<th align="left">系統架構</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft SQL Server 2014</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 位元或 64 位元</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft SQL Server 2012</p></td>
<td align="left"><p>SP2</p></td>
<td align="left"><p>32 位元或 64 位元</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft SQL Server 2008 R2</p></td>
<td align="left"><p>SP3</p></td>
<td align="left"><p>32 位元或 64 位元</p></td>
</tr>
</tbody>
</table>

 

### 發佈伺服器作業系統需求

下表列出 App-V 5.0 SP3 發佈伺服器安裝所支援的作業系統。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">作業系統</th>
<th align="left">Service Pack</th>
<th align="left">系統架構</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server 2012 R2</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 位元</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Windows Server 2012</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 位元</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server 2008 R2</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 位元</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="publishing-server-hardware-requirements-"></a>發佈伺服器硬體需求

App-V 不會在 Windows 伺服器以外的其他需求中新增其他需求。

-   處理器-1.4 GHz 或更快的64位（x64）處理器

-   RAM-2 GB RAM （64位）

-   磁碟空間-200 MB 可用硬碟空間，不含內容目錄

### 報表伺服器作業系統需求

下表列出 App-V 5.0 SP3 報表服務器安裝所支援的作業系統。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">作業系統</th>
<th align="left">Service Pack</th>
<th align="left">系統架構</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server 2012 R2</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 位元</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Windows Server 2012</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 位元</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server 2008 R2</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 位元</p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="reporting-server-hardware-requirements-"></a>報表服務器硬體需求

App-V 不會在 Windows 伺服器以外的其他需求中新增其他需求。

-   處理器-1.4 GHz 或更快的64位（x64）處理器

-   RAM-2 GB RAM （64位）

-   磁碟空間-200 MB 可用硬碟空間

### 報表伺服器資料庫需求

下表列出 App-V 5.0 SP3 報告資料庫安裝所支援的 SQL Server 版本。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">SQL Server 版本</th>
<th align="left">Service pack</th>
<th align="left">系統架構</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft SQL Server 2014</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 位元或 64 位元</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft SQL Server 2012</p></td>
<td align="left"><p>SP2</p></td>
<td align="left"><p>32 位元或 64 位元</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft SQL Server 2008 R2</p></td>
<td align="left"><p>SP3</p></td>
<td align="left"><p>32 位元或 64 位元</p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-client-supp-cfgs"></a>App-V 用戶端系統需求


下表列出 App-V 5.0 SP3 用戶端安裝所支援的作業系統。

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
<td align="left"><p>Microsoft Windows 8。1</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 位元或 64 位元</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Windows8</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 位元或 64 位元</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows7</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>32 位元或 64 位元</p></td>
</tr>
</tbody>
</table>

 

下列 App-V 用戶端安裝案例不受支援，但說明：

-   執行 Windows Server 的電腦

-   執行 App-V 4.6 SP1 或較舊版本的電腦

-   只有啟用 RDS 的伺服器才支援 App-v 5.0 SP3 遠端桌面服務用戶端

### <a href="" id="app-v-client-hardware-requirements-"></a>App-V 用戶端的硬體需求

下列清單顯示 App-V 5.0 SP3 用戶端安裝所支援的硬體設定。

-   處理器-1.4 GHz 或更快的32位（x86）或64位（x64）處理器

-   RAM-1 GB （32位）或 2 GB （64位）

-   磁片：安裝 100 MB，不包括虛擬化應用程式所使用的磁碟空間。

## 遠端桌面服務用戶端的系統需求


下表列出 App-V 5.0 SP3 遠端桌面服務（RDS）用戶端安裝所支援的作業系統。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">作業系統</th>
<th align="left">Service Pack</th>
<th align="left">系統架構</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server 2012 R2</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 位元</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Windows Server 2012</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 位元</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server 2008 R2</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 位元</p></td>
</tr>
</tbody>
</table>

 

### 遠端桌面服務用戶端的硬體需求

App-V 不會在 Windows 伺服器以外的其他需求中新增其他需求。

-   處理器-1.4 GHz 或更快的64位（x64）處理器

-   RAM-2 GB RAM （64位）

-   磁碟空間-200 MB 可用硬碟空間

## Sequencer 系統需求


下表列出 App-V 5.0 SP3 排序器安裝所支援的作業系統。

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
<td align="left"><p>Microsoft Windows Server2012 R2</p></td>
<td align="left"></td>
<td align="left"><p>64 位元</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Windows Server2012</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 位元</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Windows Server2008 R2</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 位元</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Windows 8。1</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 位元與 64 位元</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft Windows8</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 位元與 64 位元</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft Windows7</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>32 位元與 64 位元</p></td>
</tr>
</tbody>
</table>

 

### Sequencer 硬體需求

如需硬體需求，請參閱 Windows 或 Windows Server 檔。 App-v 不會增加任何額外的硬體需求。

## <a href="" id="bkmk-supp-ver-sccm"></a>系統中心 Configuration Manager 支援的版本


App-V 用戶端支援下列版本的 System Center Configuration Manager：

-   MicrosoftSystemCenter2012 ConfigurationManager

-   System Center 2012 R2 Configuration Manager

-   System Center 2012 R2 Configuration Manager SP1

如需 Configuration Manager 與 App-v 整合的詳細資訊，請參閱[規劃 app-v 與 Configuration Manager 整合](https://technet.microsoft.com/library/jj822982.aspx)。






## 相關主題


[規劃部署 App-V](planning-to-deploy-app-v.md)

[App-V 5.0 SP3 必要條件](app-v-50-sp3-prerequisites.md)

 

 





