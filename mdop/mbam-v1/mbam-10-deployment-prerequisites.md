---
title: MBAM 1.0 部署必要條件
description: MBAM 1.0 部署必要條件
author: dansimp
ms.assetid: bd9e1010-7d25-43e7-8dc6-b521226a659d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6ed14343d37a859364bcabbe6ca72c041502a23c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809489"
---
# MBAM 1.0 部署必要條件


開始進行 Microsoft BitLocker 管理與監視（MBAM）安裝之前，請確定您符合安裝產品所需的先決條件。 本節包含的資訊可協助您在部署 MBAM 用戶端和伺服器功能之前成功準備您的計算環境。

## MBAM Server 功能的安裝先決條件


每個 MBAM 伺服器功能都有特定的先決條件，必須先滿足才能成功安裝。 MBAM 安裝程式會在安裝開始前驗證是否已滿足所有先決條件。

### 管理和監視伺服器的安裝先決條件

下表包含 MBAM 管理和監視伺服器的安裝先決條件：

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
<td align="left"><p><strong>Windows ServerWeb 服務器角色</strong></p></td>
<td align="left"><p>這個角色必須新增至 mbam 系統管理和監視伺服器功能支援的伺服器作業系統。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>Web 服務器（IIS）管理工具</strong></p></td>
<td align="left"><p><strong>IIS 管理腳本與工具</strong></p></td>
</tr>
<tr class="odd">
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
<tr class="even">
<td align="left"><p><strong>Windows Server 功能</strong></p></td>
<td align="left"><p><strong>Microsoft .NET Framework 3.5.1 功能：</strong></p>
<ul>
<li><p>.NET Framework 3.5。1</p></li>
<li><p>WCF 啟用</p>
<ul>
<li><p>HTTP 啟用</p></li>
<li><p>非 HTTP 啟用</p></li>
</ul></li>
</ul>
<p><strong>Windows 處理序啟用服務</strong></p>
<ul>
<li><p>處理模型</p></li>
<li><p>.NET 環境</p></li>
<li><p>配置 Api</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

**記事** 如需支援的作業系統清單，請參閱[MBAM 1.0 支援](mbam-10-supported-configurations.md)的設定。

 

### 合規性和審核報告的安裝先決條件

合規性和審核報告必須安裝在支援的 SQLServer 版本上。 此功能的安裝先決條件包括 SQL Server Reporting Services （SSRS）。

在安裝 MBAM 伺服器期間，必須安裝並執行 SSRS。 SSRS 也應該設定為「原生」模式，而不是「未配置」或「SharePoint」模式。

**記事** 如需支援的作業系統和 SQLServer 版本的清單，請參閱[MBAM 1.0 支援](mbam-10-supported-configurations.md)的設定。

 

### 恢復與硬體資料庫的安裝先決條件

復原和硬體資料庫必須安裝在支援的 SQLServer 版本上。

SQL Server 在 MBAM 伺服器安裝期間，必須已安裝並執行資料庫引擎服務。 必須啟用 [透明資料加密（TDE）] 功能。

**記事** 如需支援的作業系統和 SQLServer 版本的清單，請參閱[MBAM 1.0 支援](mbam-10-supported-configurations.md)的設定。

 

TDE SQLServer 功能可執行即時輸入/輸出（i/o）對資料和記錄檔進行加密和解密。 TDE 會保護「存放中」的資料，其中包含資料和記錄檔。 它可讓您遵守許多行業中建立的各種法律、規章及指導方針。

**記事** 因為 TDE 會執行資料庫資訊的即時解密，所以如果您在 [登入] 下的帳戶有權在您查看 [復原金鑰資訊] SQL 資料表時，系統會看到該資料庫的許可權，就會顯示覆原金鑰資訊。

 

### 合規性和審核資料庫的安裝先決條件

合規性和審核資料庫必須安裝在支援的 SQLServer 版本上。

SQL Server 在 MBAM 伺服器安裝期間，必須已安裝並執行資料庫引擎服務。

**記事** 如需支援的作業系統和 SQLServer 版本的清單，請參閱[MBAM 1.0 支援](mbam-10-supported-configurations.md)的設定。

 

## MBAM 用戶端的安裝先決條件


開始 MBAM 用戶端安裝之前，您必須符合下列必要的先決條件：

-   受信任的平臺模組（TPM） v 1.2 功能

-   TPM 晶片必須在 BIOS 中開啟，而且必須從作業系統 resettable。 如需詳細資訊，請參閱 BIOS 檔。

**警告** 確定鍵盤、滑鼠和影片都直接連接到電腦，而不是鍵盤、影片、滑鼠（KVM）開關。 KVM 切換器可能會干擾電腦偵測硬體實際狀態的能力。

 

## 相關主題


[規劃部署 MBAM 1.0](planning-to-deploy-mbam-10.md)

[MBAM 1.0 支援的組態](mbam-10-supported-configurations.md)

 

 





