---
title: MBAM 2.0 部署必要條件
description: MBAM 2.0 部署必要條件
author: dansimp
ms.assetid: 57d1c2bb-5ea3-457e-badd-dd9206ff0f20
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ef7ee64a3661009f18e0963d738c57a59885cb20
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811499"
---
# MBAM 2.0 部署必要條件


在您開始進行 Microsoft BitLocker 管理與監控（MBAM）安裝之前，您應該確定您已滿足安裝產品的先決條件。 本節包含的資訊可協助您在部署 Microsoft BitLocker 管理與監視伺服器功能與用戶端之前，先成功規劃您的計算環境。 如果您是使用 Configuration Manager 安裝 MBAM，請參閱[規劃使用 Configuration Manager 部署 MBAM](planning-to-deploy-mbam-with-configuration-manager-2.md)以取得其他先決條件。

## MBAM Server 功能的安裝先決條件


每個 MBAM 伺服器功能都有特定的先決條件，您必須先滿足這些先決條件，才能成功安裝 MBAM 功能。 MBAM 安裝程式會檢查在安裝開始前是否已滿足所有先決條件。

### 管理和監視伺服器的先決條件

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">必備</th>
<th align="left">詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>Windows Server Web Server 角色</strong></p></td>
<td align="left"><p>這個角色必須新增至 [管理與監視伺服器] 功能支援的伺服器作業系統。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Web 服務器（IIS）管理工具</strong></p></td>
<td align="left"><p>選取 [ <strong> IIS 管理腳本與工具] </strong> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>SSL 憑證</strong></p></td>
<td align="left"><p>選用。 若要保護用戶端與 web 服務之間的通訊，您必須取得並安裝受信任的安全機構已簽署的憑證。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Web 服務器角色服務</strong></p></td>
<td align="left"><p><strong>常見的 HTTP 功能：</strong></p>
<ul>
<li><p>靜態內容</p></li>
<li><p>預設檔</p></li>
</ul>
<p><strong>應用程式開發：</strong></p>
<ul>
<li><p>ASP.NET</p></li>
<li><p>.NET 擴充性</p></li>
<li><p>ISAPI 延伸</p></li>
<li><p>ISAPI 篩選</p></li>
</ul>
<p><strong>安全性</strong></p>
<ul>
<li><p>Windows 驗證</p></li>
<li><p>要求篩選</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>Windows Server 功能</strong></p></td>
<td align="left"><p><strong>.NET Framework 3.5.1 功能：</strong></p>
<ul>
<li><p>.NET Framework 3.5。1</p></li>
<li><p>WCF 啟用</p>
<ul>
<li><p>HTTP 啟用</p></li>
<li><p>非 HTTP 啟用</p></li>
</ul></li>
</ul>
<p><strong>Windows Process Activation Service：</strong></p>
<ul>
<li><p>處理模型</p></li>
<li><p>.NET 環境</p></li>
<li><p>配置 Api</p></li>
</ul></td>
</tr>
</tbody>
</table>



**注意**  
如需支援的作業系統清單，請參閱[MBAM 2.0 支援](mbam-20-supported-configurations-mbam-2.md)的設定。



### 合規性和審核報告的先決條件

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">必備</th>
<th align="left">詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>支援的 SQL Server 版本</p>
<p><a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)">如需支援的版本，請參閱 MBAM 2.0 支援 </a> 的配置。</p></td>
<td align="left"><p>安裝 SQL Server 的方式如下：</p>
<ul>
<li><p>SQL_Latin1_General_CP1_CI_AS 排序</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>SQL Server Reporting Services （SSRS）</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>SSRS 實例權利–只有當您在不同的伺服器上安裝資料庫時，才能安裝報表。</p></td>
<td align="left"><p>所需的實例許可權：</p>
<ul>
<li><p>建立資料夾</p></li>
<li><p>發佈報表</p></li>
</ul>
<p>在安裝 MBAM 伺服器期間，必須安裝並執行 SSRS。 將 SSRS 設定為「原生」模式，而不是在未設定或「SharePoint」模式中。</p></td>
</tr>
</tbody>
</table>



### 恢復資料庫的先決條件

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">必備</th>
<th align="left">詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>支援的 SQL Server 版本</p>
<p><a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)">如需支援的版本，請參閱 MBAM 2.0 支援 </a> 的配置。</p></td>
<td align="left"><p>安裝 SQL Server 的方式如下：</p>
<ul>
<li><p>SQL_Latin1_General_CP1_CI_AS 排序</p></li>
<li><p>SQL Server 管理工具</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>必要的 SQL Server 許可權</p></td>
<td align="left"><p>所需的許可權：</p>
<ul>
<li><p>SQL 實例登入伺服器角色：</p>
<ul>
<li><p>dbcreator</p></li>
<li><p>processadmin</p></li>
</ul></li>
<li><p>SQL Server Reporting Services 實例許可權：</p>
<ul>
<li><p>建立資料夾</p></li>
<li><p>發佈報表</p></li>
</ul></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>SQL Server 中提供的 [選擇性安裝透明資料加密（TDE）] 功能</p></td>
<td align="left"><p>TDE SQL Server 功能可執行即時 i/o 加密及解密資料與記錄檔，這可以協助您遵守各種行業所確立的許多法律、法規和指導方針。</p>
<div class="alert">
<strong>注意</strong><br/><p>TDE 會執行資料庫資訊的即時解密，這表示如果您在 SQL Server 資料表中查看復原金鑰資訊時，您登入的帳戶會擁有資料庫的許可權，則會顯示覆原金鑰資訊。</p>
</div>
<div>

</div>
<p>深入瞭解 TDE： <a href="mbam-20-security-considerations-mbam-2.md" data-raw-source="[MBAM 2.0 Security Considerations](mbam-20-security-considerations-mbam-2.md)"> MBAM 2.0 安全考慮 </a> 。</p></td>
</tr>
</tbody>
</table>



### 合規性和審核資料庫的先決條件

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">必備</th>
<th align="left">詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>支援的 SQL Server 版本</p>
<p><a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)">如需支援的版本，請參閱 MBAM 2.0 支援 </a> 的配置。</p></td>
<td align="left"><p>安裝 SQL Server 的方式如下：</p>
<ul>
<li><p>SQL_Latin1_General_CP1_CI_AS 排序</p></li>
<li><p>SQL Server 管理工具</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>必要的 SQL Server 許可權</p></td>
<td align="left"><p>所需的許可權：</p>
<ul>
<li><p>SQL 實例登入伺服器角色：</p>
<ul>
<li><p>dbcreator</p></li>
<li><p>processadmin</p></li>
</ul></li>
<li><p>SQL Server Reporting Services 實例許可權：</p>
<ul>
<li><p>建立資料夾</p></li>
<li><p>發佈報表</p></li>
</ul></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>SQL Server 中的 [選擇性安裝透明資料加密（TDE）] 功能。</p></td>
<td align="left"><p>TDE SQL Server 功能可執行即時 i/o 加密及解密資料與記錄檔，這可以協助您遵守各種行業所確立的許多法律、法規和指導方針。</p>
<div class="alert">
<strong>注意</strong><br/><p>TDE 會執行資料庫資訊的即時解密，這表示如果您在 SQL Server 資料表中查看復原金鑰資訊時，您登入的帳戶會擁有資料庫的許可權，則會顯示覆原金鑰資訊。</p>
</div>
<div>

</div>
<p>深入瞭解 TDE： <a href="mbam-20-security-considerations-mbam-2.md" data-raw-source="[MBAM 2.0 Security Considerations](mbam-20-security-considerations-mbam-2.md)"> MBAM 2.0 安全性考慮</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>SQL Server 在 MBAM 伺服器安裝期間，必須已安裝並執行資料庫引擎服務。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>SQL Server 代理程式服務必須在選取的 SQL Server 實例上執行並設定為自動啟動。</p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



### 自助服務入口網站的先決條件

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">必備</th>
<th align="left">詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>支援的 Windows Server 版本</p>
<p><a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)">如需支援的版本，請參閱 MBAM 2.0 支援 </a> 的配置。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>ASP.NET MVC 2。0</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=392270" data-raw-source="[ASP.NET MVC 2 download](https://go.microsoft.com/fwlink/?LinkId=392270)">ASP.NET MVC 2 下載</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>Web 服務 IIS 管理工具</p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



## MBAM 用戶端的先決條件


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">必備</th>
<th align="left">詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>Windows 7 用戶端只 </strong> - 必須擁有信任的平臺模組（TPM）功能。</p></td>
<td align="left"><p>TPM 版本必須是1.2 或更新版本。</p></td>
</tr>
<tr class="even">
<td align="left"><p>您必須在 BIOS 中開啟 TPM 晶片，然後從作業系統 resettable。</p></td>
<td align="left"><p>如需詳細資訊，請參閱 BIOS 檔。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>僅限 Windows 8 用戶端 </strong> ：若要讓 MBAM 儲存及管理 tpm 復原金鑰：必須先關閉 TPM 自動供給，然後再將 MBAM 設定為 TPM 擁有者，才能部署 MBAM。 若要關閉 TPM 自動供給，請參閱 <a href="https://go.microsoft.com/fwlink/?LinkId=286468" data-raw-source="[Disable-TpmAutoProvisioning](https://go.microsoft.com/fwlink/?LinkId=286468)"> Disable-TpmAutoProvisioning </a> 。</p>
<ul>
<li><p>TPM 自動預配必須關閉。</p></li>
<li><p>您必須先將 MBAM 設為 TPM 擁有者，然後才能部署 MBAM。</p></li>
</ul></td>
<td align="left"><p>若要關閉 TPM 自動供給，請參閱 <a href="https://go.microsoft.com/fwlink/?LinkId=286468" data-raw-source="[Disable-TpmAutoProvisioning](https://go.microsoft.com/fwlink/?LinkId=286468)"> Disable-TpmAutoProvisioning </a> 。</p>
<div class="alert">
<strong>注意</strong><br/><p>確定鍵盤、影片或滑鼠已直接連接，且未透過鍵盤、影片或滑鼠（KVM）開關進行管理。 KVM 切換器可能會干擾電腦偵測硬體實際狀態的能力。</p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



## 相關主題


[規劃部署 MBAM 2.0](planning-to-deploy-mbam-20-mbam-2.md)

[MBAM 2.0 支援的組態](mbam-20-supported-configurations-mbam-2.md)









