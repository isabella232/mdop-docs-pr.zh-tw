---
title: MBAM 2.5 支援的組態
description: MBAM 2.5 支援的組態
author: dansimp
ms.assetid: ce689aff-9a55-4ae7-a968-23c7bda9b4d6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 10/24/2018
ms.openlocfilehash: 262cd8c259dc37b291cdaf02caf0e20b7515d38b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810227"
---
# MBAM 2.5 支援的組態


您可以在獨立拓朴中，或在與 System Center Configuration Manager 整合 MBAM 的 Configuration Manager 整合拓撲中執行 Microsoft BitLocker 管理與監控（MBAM）2.5。 如果您在生產環境中針對其中一個拓撲使用建議的設定，MBAM 最多可支援 500000 MBAM 用戶端。 如需每個伺服器上針對每個拓朴設定的建議架構與功能的相關資訊，請參閱[MBAM 2.5 的高層次架構](high-level-architecture-for-mbam-25.md)。

如需 Configuration Manager 整合拓朴專用的其他設定，請參閱[MBAM 支援的 Configuration Manager 版本](#bkmk-cm-ramreqs)。

**注意**  
Microsoft 提供目前 service pack 的支援，在某些情況下，也是最前面的 service pack。 若要尋找您產品的支援時程表，請參閱[支援的生命週期服務套件](https://go.microsoft.com/fwlink/p/?LinkId=31975)。 如需 Microsoft 支援週期原則的其他相關資訊，請參閱[Microsoft 支援週期支援原則常見問題](https://go.microsoft.com/fwlink/p/?LinkId=31976)。



## MBAM 支援的語言


下表顯示 MBAM 用戶端支援的語言（包括自助式入口網站）和 MBAM 2.5 中的 MBAM 伺服器以及 MBAM 2.5 SP1。

**MBAM 2.5 SP1 中支援的語言：**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">用戶端語言</th>
<th align="left">伺服器語言</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>捷克文（捷克共和國） cs-CZ</p>
<p>丹麥文（丹麥） da-深色</p>
<p>荷蘭文（荷蘭） nl-nl&platform-NL-NL&PLATFORM</p>
<p>英文（美國） en</p>
<p>芬蘭文（芬蘭） fi</p>
<p>法文（法國） fr-fr</p>
<p>德國（德國） de</p>
<p>希臘文（希臘） el-GR</p>
<p>匈牙利文（匈牙利） hu</p>
<p>義大利文（義大利） it</p>
<p>日文（日本） ja-jp</p>
<p>韓文（韓國） ko-KR</p>
<p>挪威文、博克瑪律文（挪威） nb-否</p>
<p>波蘭文（波蘭） pl-PL</p>
<p>葡萄牙文（巴西） pt-BR</p>
<p>葡萄牙文（葡萄牙） pt</p>
<p>俄文（俄羅斯） ru-RU</p>
<p>斯洛伐克文（斯洛伐克） sk-SK</p>
<p>西班牙文（西班牙） es</p>
<p>瑞典文（瑞典） sv-SE</p>
<p>土耳其文（土耳其） tr-TR</p>
<p>斯洛維尼亞文（斯洛維尼亞） sl-SI</p>
<p>簡體中文（PRC） zh-cn&platform-CN</p>
<p>繁體中文（臺灣） zh-cn&platform-幼圓</p></td>
<td align="left"><ul>
<li><p>英文（美國） en</p></li>
<li><p>法文（法國） fr-fr</p></li>
<li><p>德國（德國） de</p></li>
<li><p>義大利文（義大利） it</p></li>
<li><p>日文（日本） ja-jp</p></li>
<li><p>韓文（韓國） ko-KR</p></li>
<li><p>葡萄牙文（巴西） pt-BR</p></li>
<li><p>俄文（俄羅斯） ru-RU</p></li>
<li><p>西班牙文（西班牙） es</p></li>
<li><p>簡體中文（PRC） zh-cn&platform-CN</p></li>
<li><p>繁體中文（臺灣） zh-cn&platform-幼圓</p></li>
</ul></td>
</tr>
</tbody>
</table>



**MBAM 2.5 中支援的語言：**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">用戶端語言</th>
<th align="left">伺服器語言</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><ul>
<li><p>英文（美國） en</p></li>
<li><p>法文（法國） fr-fr</p></li>
<li><p>德國（德國） de</p></li>
<li><p>義大利文（義大利） it</p></li>
<li><p>日文（日本） ja-jp</p></li>
<li><p>韓文（韓國） ko-KR</p></li>
<li><p>葡萄牙文（巴西） pt-BR</p></li>
<li><p>俄文（俄羅斯） ru-RU</p></li>
<li><p>西班牙文（西班牙） es</p></li>
<li><p>簡體中文（PRC） zh-cn&platform-CN</p></li>
<li><p>繁體中文（臺灣） zh-cn&platform-幼圓</p></li>
</ul></td>
<td align="left"><ul>
<li><p>英文（美國） en</p></li>
<li><p>法文（法國） fr-fr</p></li>
<li><p>德國（德國） de</p></li>
<li><p>義大利文（義大利） it</p></li>
<li><p>日文（日本） ja-jp</p></li>
<li><p>韓文（韓國） ko-KR</p></li>
<li><p>葡萄牙文（巴西） pt-BR</p></li>
<li><p>俄文（俄羅斯） ru-RU</p></li>
<li><p>西班牙文（西班牙） es</p></li>
<li><p>簡體中文（PRC） zh-cn&platform-CN</p></li>
<li><p>繁體中文（臺灣） zh-cn&platform-幼圓</p></li>
</ul></td>
</tr>
</tbody>
</table>



## <a href="" id="---------mbam-server-system-requirements"></a> MBAM 伺服器系統需求


### MBAM 伺服器作業系統需求

我們強烈建議您在相同的作業系統上執行 MBAM 用戶端和 MBAM 伺服器。 例如，windows 10 與 Windows Server 2016、Windows 8.1 （具備 Windows Server 2012 R2 等）。

下表列出 MBAM 伺服器安裝支援的作業系統。

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
<td align="left"><p>Windows Server 2016</p></td>
<td align="left"><p>標準或資料中心</p></td>
<td align="left"></td>
<td align="left"><p>64 位元</p></td>
</tr>
<tr class="even">
<td align="left"><p>WindowsServer 2012 R2</p></td>
<td align="left"><p>標準或資料中心</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 位元</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2012</p></td>
<td align="left"><p>標準或資料中心</p></td>
<td align="left"></td>
<td align="left"><p>64 位元</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2008 R2</p></td>
<td align="left"><p>標準版、企業版或資料中心</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 位元</p></td>
</tr>
</tbody>
</table>



企業網域必須包含至少一個 Windows Server 2008 （或更新版本）網網域控制站。

### <a href="" id="bkmk-stand-alone-ramreqs"></a>MBAM 伺服器處理器、RAM 與磁碟空間需求-獨立拓朴

這些需求適用于 MBAM 獨立拓撲。 如需 Configuration Manager 整合拓朴的需求，請參閱[MBAM 伺服器處理器、RAM 和磁碟空間需求-Configuration Manager 整合拓撲](#bkmk-cm-ramreqs)。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">硬體專案</th>
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



### <a href="" id="bkmk-cm-ramreqs"></a>MBAM 伺服器處理器、RAM 與磁碟空間需求-Configuration Manager 整合拓撲

下表列出當您使用 Configuration Manager 整合拓撲時，MBAM 伺服器的伺服器處理器、RAM 和磁碟空間需求。 如需獨立拓朴的需求，請參閱[MBAM 伺服器處理器、RAM 和磁碟空間需求-獨立拓朴](#bkmk-stand-alone-ramreqs)。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">硬體專案</th>
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



### <a href="" id="bkmk-cmversions"></a>MBAM 支援的 Configuration Manager 版本

MBAM 支援下列 Configuration Manager 版本。

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
<tr class="even">
<td align="left"><p>Microsoft System Center Configuration Manager （目前分支），最高版本1902</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 位元</p></td>
</tr>

<tr class="odd">
<td align="left"><p>Microsoft System Center Configuration Manager 1806</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 位元</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft System Center Configuration Manager （LTSB-版本1606）</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 位元</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Microsoft System Center 2012 Configuration Manager</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 位元</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft System Center Configuration Manager 2007 R2 或更新版本</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 位元</p>

&gt;<strong>注意 </strong> 雖然 Configuration Manager 2007 R2 是32位，您必須將它與 SQL Server 安裝在64位作業系統上，才能符合64位 MBAM 軟體。
</td>
</tr>
</tbody>
</table>



如需 Configuration Manager 伺服器支援的設定的清單，請參閱適用于您所使用之 Configuration Manager 版本的相關 TechNet 檔。 MBAM 對於 Configuration Manager 伺服器沒有額外的系統需求。

### <a href="" id="sql-server-database-requirements-"></a>SQL Server 資料庫需求

下表列出 MBAM 伺服器功能支援的 Microsoft SQL Server 版本，其中包含復原資料庫、合規性和審核資料庫，以及 [報告] 功能。 所需版本適用于獨立版或 Configuration Manager 整合拓撲。

您必須安裝 sql Server，並使用**sql \ _Latin1 \ _General \ _CP1 \ _CI \ _AS**排序。

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
<td align="left"><p>Microsoft SQL Server 2017</p></td>
<td align="left"><p>標準版、企業版或資料中心</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 位元</p></td><br/><tr class="even">
<td align="left"><p>Microsoft SQL Server 2016</p></td>
<td align="left"><p>標準版、企業版或資料中心</p></td>
<td align="left"><p>SP1</p></td>
<a href="https://www.microsoft.com/download/details.aspx?id=54967" data-raw-source="https://www.microsoft.com/download/details.aspx?id=54967">https://www.microsoft.com/download/details.aspx?id=54967</a><td align="left"><p>64 位元</p></td>
<tr class="odd">
<td align="left"><p>Microsoft SQL Server 2014</p></td>
<td align="left"><p>標準版、企業版或資料中心</p></td>
<td align="left"><p>SP1、SP2</p></td>
<td align="left"><p>64 位元</p></td>
<tr class="odd">
<td align="left"><p>Microsoft SQL Server 2012</p></td>
<td align="left"><p>標準版、企業版或資料中心</p></td>
<td align="left"><p>SP3</p></td>
<td align="left"><p>64 位元</p></td>
<tr class="even">
<td align="left"><p>Microsoft SQL Server 2008 R2</p></td>
<td align="left"><p>Standard 或 Enterprise</p></td>
<td align="left"><p>SP3</p></td>
<td align="left"><p>64 位元</p></td>
</tr>
</tbody>
</table>

**注意**  
為了支援 SQL 2016，您必須安裝 MDOP 年 3 2017 月的服務版本 https://www.microsoft.com/download/details.aspx?id=54967 ，並支援 sql 2017 您必須安裝2017年 7 2018 月的服務發行 https://www.microsoft.com/download/details.aspx?id=57157 。 一般來說，只要使用最新的服務更新，就能一直保持在最新狀態，因為它也包含所有 bugfixes 和新功能。


### <a href="" id="bkmk-sql-stand-alone-ramreqs"></a>SQL Server 處理器、RAM 與磁碟空間需求–獨立拓朴

下表列出當您使用獨立拓撲時，在 SQL Server 電腦上建議的伺服器處理器、RAM 和磁碟空間需求。 使用這些需求做為指南。 您的特定需求會根據您在企業中支援的用戶端電腦數量而有所不同。 若要查看 Configuration Manager 整合拓撲的需求，請參閱[SQL Server 處理器、RAM 與磁碟空間需求-Configuration Manager 整合拓撲](#bkmk-cm-sql-ramreqs)。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">硬體專案</th>
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



### <a href="" id="bkmk-cm-sql-ramreqs"></a>SQL Server 處理器、RAM 與磁碟空間需求-Configuration Manager 整合拓撲

下表列出當您使用 Configuration Manager 整合拓撲時，Microsoft SQL Server 電腦的伺服器處理器、RAM 與磁碟空間需求，請參閱[SQL Server 處理器、RAM 和磁碟空間需求–獨立拓撲](#bkmk-sql-stand-alone-ramreqs)。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">硬體專案</th>
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
<td align="left"><p>5 GB</p></td>
</tr>
</tbody>
</table>



## <a href="" id="---------mbam-client-system-requirements"></a> MBAM 用戶端系統需求


### 用戶端作業系統需求

我們強烈建議您在相同的作業系統上執行 MBAM 用戶端和 MBAM 伺服器。 例如，windows 10 與 Windows Server 2016、Windows 8.1 （具備 Windows Server 2012 R2 等）。

下表列出 MBAM 用戶端安裝支援的作業系統。 在獨立與 Configuration Manager 整合拓朴中，相同的需求同樣適用。

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
<tr class="even">
    <td align="left"><p>Windows 10 IoT</p></td>
    <td align="left"><p>企業</p></td>
    <td align="left"><p></p></td>
    <td align="left"><p>32 位元或 64 位元</p></td>
</tr><br/><tr class="odd">
<td align="left"><p>Windows 10</p></td>
<td align="left"><p>企業</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 位元或 64 位元</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 8.1</p></td>
<td align="left"><p>企業</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 位元或 64 位元</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows 7</p></td>
<td align="left"><p>企業版或旗艦版</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>32 位元或 64 位元</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows To Go</p></td>
<td align="left"><p>Windows 8.1 和 Windows 10 企業版</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 位元或 64 位元</p></td>
</tr>
</tbody>
</table>



### <a href="" id="client-ram-requirements-"></a>用戶端 RAM 需求

不是 MBAM 用戶端安裝所特有的 RAM 需求。

## <a href="" id="---------mbam-group-policy-system-requirements"></a> MBAM 群組原則系統需求


下表列出 MBAM 群組原則範本安裝所支援的作業系統。

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
 <tr class="even">
      <td align="left"><p>Windows 10 IoT</p></td>
      <td align="left"><p>企業</p></td>
      <td align="left"><p></p></td>
      <td align="left"><p>32 位元或 64 位元</p></td>
 </tr>
<tr class="odd">
<td align="left"><p>Windows 10</p></td>
<td align="left"><p>企業</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 位元或 64 位元</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 8.1</p></td>
<td align="left"><p>企業</p></td>
<td align="left"><p></p></td>
<td align="left"><p>32 位元或 64 位元</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows 7</p></td>
<td align="left"><p>企業版或旗艦版</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>32 位元或 64 位元</p></td>
</tr>
<tr class="even">
<td align="left"><p>WindowsServer 2012 R2</p></td>
<td align="left"><p>標準或資料中心</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 位元</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2012</p></td>
<td align="left"><p>標準或資料中心</p></td>
<td align="left"><p></p></td>
<td align="left"><p>64 位元</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server 2008 R2</p></td>
<td align="left"><p>標準版、企業版或資料中心</p></td>
<td align="left"><p>SP1</p></td>
<td align="left"><p>64 位元</p></td>
</tr>
</tbody>
</table>

## Azure IaaS 中的 MBAM

在上述任何支援的作業系統版本上，您可以將 MBAM 伺服器部署在 Azure 基礎結構中（IaaS），連線到託管于內部部署的 Active Directory，或是託管在 Azure IaaS 中的 Active Directory。  在 Azure IaaS 上設定和設定 Active Directory 的檔在[這裡](https://msdn.microsoft.com/library/azure/jj156090.aspx)。

虛擬機器不支援 MBAM 用戶端，但在 Azure IaaS 上也不支援此功能。


## 服務版本 

- [2016年4月的修補程式](https://support.microsoft.com/help/3144445/april-2016-hotfix-rollup-for-microsoft-desktop-optimization-pack)
- [2016年9月](https://support.microsoft.com/ms-my/help/3168628/september-2016-servicing-release-for-microsoft-desktop-optimization-pa)
- [2016 年 12 月](https://support.microsoft.com/help/3198158/december-2016-servicing-release-for-microsoft-desktop-optimization-pac)
- [2017 年 3 月](https://support.microsoft.com/en-ie/help/4014009/march-2017-servicing-release-for-microsoft-desktop-optimization-pack) 
- [2017 年 6 月](https://support.microsoft.com/af-za/help/4018510/june-2017-servicing-release-for-microsoft-desktop-optimization-pack)
- [2017 年 9 月](https://support.microsoft.com/en-ie/help/4041137/september-2017-servicing-release-for-microsoft-desktop-optimization)
- [2018 年 3 月](https://support.microsoft.com/help/4074878/march-2018-servicing-release-for-microsoft-desktop-optimization-pack)
- [2018年7月](https://support.microsoft.com/help/4340040/july-2018-servicing-release-for-microsoft-desktop-optimization-pack)
- [2019年5月](https://support.microsoft.com/help/4505175/may-2019-servicing-release-for-microsoft-desktop-optimization-pack)

## 相關主題


[規劃部署 MBAM 2.5](planning-to-deploy-mbam-25.md)

[MBAM 2.5 的環境準備](preparing-your-environment-for-mbam-25.md)




## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。




