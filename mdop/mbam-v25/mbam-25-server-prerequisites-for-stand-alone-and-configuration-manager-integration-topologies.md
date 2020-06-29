---
title: 獨立拓撲與 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必要條件
description: 獨立拓撲與 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必要條件
author: dansimp
ms.assetid: 76a6047a-5c6e-42ff-af09-a6f382a69537
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: c9af551b1d867f61912bbf3b759574a840b0645c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811492"
---
# 獨立拓撲與 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必要條件


開始進行 Microsoft BitLocker 管理與監控（MBAM）安裝之前，您必須完成本主題中所列的先決條件。 這些先決條件適用于 MBAM 獨立拓朴與 System Center Configuration Manager 整合拓撲。

如果您是使用 System Center Configuration Manager 部署 MBAM，您必須完成其他先決條件，這些必備元件會列在[僅適用于 Configuration Manager 整合拓撲的 MBAM 2.5 伺服器必備元件](mbam-25-server-prerequisites-that-apply-only-to-the-configuration-manager-integration-topology.md)中。

如需 MBAM 支援的硬體與作業系統清單，請參閱[MBAM 2.5 支援](mbam-25-supported-configurations.md)的設定。

**重要**  
如果使用的是沒有 MBAM 的 BitLocker，您必須解密磁片磁碟機，然後使用 [雲端] 清除 TPM。 如果用戶端電腦已加密，且已建立 TPM 擁有者密碼，則 MBAM 無法取得 TPM 的擁有權。



## 必要的 MBAM 角色和帳戶


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
<td align="left"><p>在 Active Directory 網域服務（AD DS）中建立的群組</p></td>
<td align="left"><p><a href="planning-for-mbam-25-groups-and-accounts.md" data-raw-source="[Planning for MBAM 2.5 Groups and Accounts](planning-for-mbam-25-groups-and-accounts.md)"> </a> 如需這些群組和帳戶的描述，請參閱規劃 MBAM 2.5 群組和帳戶。</p></td>
</tr>
</tbody>
</table>



## 恢復資料庫的先決條件


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
<td align="left"><p>支援的 SQL Server 版本</p></td>
<td align="left"><p>使用 SQL_Latin1_General_CP1_CI_AS 的排序規則安裝 Microsoft SQL Server。</p>
<p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)">如需支援的版本，請參閱 MBAM 2.5 支援 </a> 的配置。</p></td>
</tr>
<tr class="even">
<td align="left"><p>必要的 SQL Server 許可權</p></td>
<td align="left"><p>所需的許可權：</p>
<ul>
<li><p>SQL Server 實例登入伺服器角色：</p>
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
<td align="left"><p>選用-安裝 SQL Server 提供的透明資料加密（TDE）功能</p></td>
<td align="left"><p>TDE SQL Server 功能可執行即時 i/o 加密及解密資料與記錄檔，這可以協助您遵守適用于各種行業的法律、規章及指導方針。</p>
<div class="alert">
<strong>注意</strong><br/><p>TDE 執行資料庫資訊的即時解密。 這表示如果您是在 SQL Server 資料庫中查看復原金鑰資訊，而且您是以擁有資料庫許可權的帳戶登入，則會看到 [復原金鑰資訊]。 若要深入瞭解 TDE，請參閱 <a href="mbam-25-security-considerations.md" data-raw-source="[MBAM 2.5 Security Considerations](mbam-25-security-considerations.md)"> MBAM 2.5 安全性考慮 </a> 。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>SQL Server 資料庫引擎服務</p></td>
<td align="left"><p>在安裝 MBAM 伺服器期間，必須安裝並執行 SQL Server 資料庫引擎服務。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows PowerShell 3.0 或更新版本</p></td>
<td align="left"><p>如果您使用 Windows PowerShell 從遠端電腦設定資料庫，就不需要在恢復資料庫伺服器上安裝 windows PowerShell。</p></td>
</tr>
</tbody>
</table>



## 合規性和審核資料庫的先決條件


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
<td align="left"><p>支援的 SQL Server 版本</p></td>
<td align="left"><p>安裝含有 SQL_Latin1_General_CP1_CI_AS 排序規則的 SQL Server。</p>
<p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)">如需支援的版本，請參閱 MBAM 2.5 支援 </a> 的配置。</p></td>
</tr>
<tr class="even">
<td align="left"><p>必要的 SQL Server 許可權</p></td>
<td align="left"><p>所需的許可權：</p>
<ul>
<li><p>SQL Server 實例登入伺服器角色：</p>
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
<td align="left"><p>選用-在 SQL Server 中安裝透明資料加密（TDE）功能</p></td>
<td align="left"><p>TDE SQL Server 功能可執行即時 i/o 加密及解密資料與記錄檔，這可以協助您遵守適用于各種行業的法律、規章及指導方針。</p>
<p>TDE 執行資料庫資訊的即時解密。 這表示如果您是在 SQL Server 資料庫中查看復原金鑰資訊，而且您是以擁有資料庫許可權的帳戶登入，則會看到 [復原金鑰資訊]。 若要深入瞭解 TDE，請參閱 <a href="mbam-25-security-considerations.md" data-raw-source="[MBAM 2.5 Security Considerations](mbam-25-security-considerations.md)"> MBAM 2.5 安全性考慮 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>SQL Server 資料庫引擎服務</p></td>
<td align="left"><p>在安裝 MBAM 伺服器期間，必須安裝並執行 SQL Server 資料庫引擎服務。 不過，您可以在遠端執行 SQL Server;它不一定要在您安裝 MBAM Server 軟體的同一個伺服器上。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows PowerShell 3.0 或更新版本</p></td>
<td align="left"><p>如果您使用 Windows PowerShell 從遠端電腦設定資料庫，就不需要在合規性和審核資料庫伺服器上安裝 windows PowerShell。</p></td>
</tr>
</tbody>
</table>



## 報表的先決條件


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
<td align="left"><p>支援的 SQL Server 版本</p></td>
<td align="left"><p>安裝含有 SQL_Latin1_General_CP1_CI_AS 排序規則的 SQL Server。</p>
<p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)">如需支援的版本，請參閱 MBAM 2.5 支援 </a> 的配置。</p></td>
</tr>
<tr class="even">
<td align="left"><p>SQL Server Reporting Services （SSRS）</p></td>
<td align="left"><p>在安裝 MBAM 伺服器期間，必須安裝並執行 SSRS。</p>
<p>在純模式中設定 SSRS &quot; &quot; ，而不是在未設定或 &quot; SharePoint 模式中進行 &quot; 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>SSRS 實例許可權–只有當您在已設定報表的伺服器上安裝資料庫時，才能配置報表。</p></td>
<td align="left"><p>所需的實例許可權：</p>
<ul>
<li><p>建立資料夾</p></li>
<li><p>發佈報表</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>Windows PowerShell 3.0 或更新版本</p></td>
<td align="left"><p>如果您使用 Windows PowerShell 從遠端電腦設定資料庫，就不需要在此資料庫伺服器上安裝 windows PowerShell。</p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-prereqsams"></a>管理和監視伺服器的先決條件


下表列出 MBAM 管理和監視伺服器的安裝先決條件。

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
<td align="left"><p>Windows Server Web Server 角色</p></td>
<td align="left"><p>這個角色必須新增至 [管理與監視伺服器] 功能支援的伺服器作業系統。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Web 服務器（IIS）管理工具</p></td>
<td align="left"><p>按一下 [ <strong> IIS 管理腳本與工具] </strong> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>SSL 憑證</strong></p></td>
<td align="left"><p>選用。 若要保護用戶端電腦與 web 服務之間的通訊，您必須取得並安裝受信任的安全機構已簽署的憑證。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Web 服務器角色服務</p></td>
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
<td align="left"><p>Windows Server 功能</p></td>
<td align="left"><p><strong>.NET Framework 4.5 功能：</strong></p>
<ul>
<li><p><strong>.NET Framework 4.5 或4。6</strong></p>
<ul>
<li><p><strong>Windows Server 2016 </strong> - .net Framework 4.6 已安裝在這些版本的 Windows Server 上，但您必須啟用它。</p></li>  
<li><p><strong>Windows server 2012 或 Windows Server 2012 R2 </strong> - .net Framework 4.5 已針對這些版本的 Windows Server 安裝，但您必須啟用它。</p></li>
<li><p><strong>Windows server </strong> - 2008 r2 不隨附 windows Server 2008 R2 .net framework 4.5，因此您必須 <a href="https://go.microsoft.com/fwlink/?LinkId=392318" data-raw-source="[download Microsoft .NET Framework 4.5](https://go.microsoft.com/fwlink/?LinkId=392318)"> 下載 Microsoft .net framework 4.5 </a> 並另行安裝。</p>
<div class="alert">
<strong>注意</strong><br/><p>如果您是從 MBAM 2.0 或 MBAM 2.0 SP1 升級，且需要安裝 .NET Framework 4.5，請參閱 MBAM 2.5 的版本資訊，以 <a href="release-notes-for-mbam-25.md" data-raw-source="[Release Notes for MBAM 2.5](release-notes-for-mbam-25.md)"> </a> 取得讓網站正常運作的其他必要步驟。</p>
</div>
<div>

</div></li>
</ul></li>
<li><p><strong>WCF 啟用</strong></p>
<ul>
<li><p>HTTP 啟用</p></li>
<li><p>非 HTTP 啟用（僅適用于 Windows Server 2008、2012和 2012 R2）</p>
<p></p></li>
</ul></li>
<li><p><strong>TCP 啟用</strong></p></li>
</ul>
<p><strong>Windows Process Activation Service：</strong></p>
<ul>
<li><p>處理模型</p></li>
<li><p>.NET Framework 環境</p></li>
<li><p>配置 Api</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>ASP.NET MVC 4。0</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=392271" data-raw-source="[ASP.NET MVC 4 download](https://go.microsoft.com/fwlink/?LinkId=392271)">ASP.NET MVC 4 下載</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>服務主體名稱（SPN）</p></td>
<td align="left"><p>Web 應用程式需要在您用於 web 應用程式池之網域帳戶下的虛擬主機名稱稱中使用 SPN。</p>
<p>如果您的系統管理許可權允許您在 Active Directory 網域服務中建立 Spn，MBAM 會為您建立 SPN。 請參閱 <a href="https://technet.microsoft.com/library/cc731241.aspx" data-raw-source="[Setspn](https://technet.microsoft.com/library/cc731241.aspx)"> Setspn </a> ，以取得建立 spn 所需許可權的相關資訊。</p>
<p>如果您沒有建立 Spn 的系統管理許可權，您必須使用下列命令要求貴組織中的 Active Directory 系統管理員為您建立 SPN。</p>
<pre class="syntax" space="preserve"><code>Setspn -s http/mbamvirtual contoso\mbamapppooluser
Setspn -s http/mbamvirtual.contoso.com contoso\mbamapppooluser</code></pre>
<p>在程式碼範例中，虛擬主機名稱是 mbamvirtual.contoso.com，而用於 web 應用程式池的網域帳戶是 contoso\mbamapppooluser。</p>
<div class="alert">
<strong>注意</strong><br/><p>如果您要設定負載平衡，請在所有伺服器上使用相同的應用程式池帳戶。</p>
</div>
<div>

</div>
<p>如需針對完整、NetBIOS 及自訂主機名稱登記 Spn 的詳細資訊，請參閱 <a href="planning-how-to-secure-the-mbam-websites.md" data-raw-source="[Planning How to Secure the MBAM Websites](planning-how-to-secure-the-mbam-websites.md)"> 規劃如何保護 MBAM 網站 </a> 。</p></td>
</tr>
</tbody>
</table>



## 自助服務入口網站的先決條件


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
<td align="left"><p>支援的 Windows Server 版本</p></td>
<td align="left"><p><a href="mbam-25-supported-configurations.md" data-raw-source="[MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md)">如需支援的版本，請參閱 MBAM 2.5 支援 </a> 的配置。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ASP.NET MVC 4。0</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=392271" data-raw-source="[ASP.NET MVC 4 download](https://go.microsoft.com/fwlink/?LinkId=392271)">ASP.NET MVC 4 下載</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>Web 服務 IIS 管理工具</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>服務主體名稱（SPN）</p></td>
<td align="left"><p>Web 應用程式需要在您用於 web 應用程式池之網域帳戶下的虛擬主機名稱稱中使用 SPN。</p>
<p>如果您的系統管理許可權允許您在 Active Directory 網域服務中建立 Spn，MBAM 會為您建立 SPN。 請參閱 <a href="https://technet.microsoft.com/library/cc731241.aspx" data-raw-source="[Setspn](https://technet.microsoft.com/library/cc731241.aspx)"> Setspn </a> ，以取得建立 spn 所需許可權的相關資訊。</p>
<p>如果您沒有建立 Spn 的系統管理許可權，您必須使用下列命令，要求貴組織中組織管理員的 Active Directory 系統管理員為您建立 SPN。</p>
<pre class="syntax" space="preserve"><code>Setspn -s http/mbamvirtual contoso\mbamapppooluser
Setspn -s http/mbamvirtual.contoso.com contoso\mbamapppooluser</code></pre>
<p>在程式碼範例中，虛擬主機名稱是 mbamvirtual.contoso.com，而用於 web 應用程式池的網域帳戶是 contoso\mbamapppooluser。</p>
<div class="alert">
<strong>注意</strong><br/><p>如果您要設定負載平衡，請在所有伺服器上使用相同的應用程式池帳戶。</p>
</div>
<div>

</div>
<p>如需針對完整、NetBIOS 及自訂主機名稱登記 Spn 的詳細資訊，請參閱 <a href="planning-how-to-secure-the-mbam-websites.md" data-raw-source="[Planning How to Secure the MBAM Websites](planning-how-to-secure-the-mbam-websites.md)"> 規劃如何保護 MBAM 網站 </a> 。</p></td>
</tr>
</tbody>
</table>



## 管理工作站的先決條件


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
<td align="left"><p>在安裝 MBAM 用戶端之前，請先從 <a href="https://go.microsoft.com/fwlink/p/?LinkId=393941" data-raw-source="[How to Get MDOP Group Policy (.admx) Templates](https://go.microsoft.com/fwlink/p/?LinkId=393941)"> 如何取得 MDOP 群組原則（admx）範本中下載 MBAM 群組原則範本 </a> ，並使用您要在企業中實現的設定（在您的 BitLocker 磁片磁碟機加密中）來設定它們。</p></td>
<td align="left"><p>在安裝 MBAM 用戶端之前，請執行下列動作：</p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">工作</th>
<th align="left">取得指示的位置</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>複製 MBAM 群組原則範本</p></td>
<td align="left"><p><a href="copying-the-mbam-25-group-policy-templates.md" data-raw-source="[Copying the MBAM 2.5 Group Policy Templates](copying-the-mbam-25-group-policy-templates.md)">複製 MBAM 2.5 群組原則範本</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>編輯群組原則設定</p></td>
<td align="left"><p><a href="editing-the-mbam-25-group-policy-settings.md" data-raw-source="[Editing the MBAM 2.5 Group Policy Settings](editing-the-mbam-25-group-policy-settings.md)">編輯 MBAM 2.5 群組原則設定</a></p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>





## 相關主題


[MBAM 2.5 的環境準備](preparing-your-environment-for-mbam-25.md)

[規劃部署 MBAM 2.5](planning-to-deploy-mbam-25.md)

[MBAM 2.5 支援的組態](mbam-25-supported-configurations.md)




## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。




