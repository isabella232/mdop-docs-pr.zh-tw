---
title: App-V 5.1 必要條件
description: App-V 5.1 必要條件
author: dansimp
ms.assetid: 1bfa03c1-a4ae-45ec-8a2b-b10c2b94bfb0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 24a74d8f8d7148cdb6c32bcafa87f479d24305af
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800669"
---
# App-V 5.1 必要條件


在安裝 Microsoft Application Virtualization （App-v）5.1 之前，請確定您已安裝下列所有必要的必備軟體。

如需支援的作業系統及 app-v Server、Sequencer 及用戶端的硬體需求清單，請參閱[app-v 5.1 支援](app-v-51-supported-configurations.md)的設定。

## 在每個作業系統上預先安裝的軟體摘要


下表指出已針對不同作業系統安裝的軟體。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">作業系統</th>
<th align="left">先決條件描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows 10</p></td>
<td align="left"><p>已安裝所有必備軟體。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 8.1</p></td>
<td align="left"><p>已安裝所有必備軟體。</p>
<div class="alert">
<strong>注意</strong><br/><p>如果您執行的是 Windows 8，請先升級至 Windows 8.1，然後再使用 App-v 5.1。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server 2012</p></td>
<td align="left"><p>下列是已安裝的必備軟體：</p>
<ul>
<li><p>Microsoft .NET Framework 4。5</p></li>
<li><p>Windows PowerShell 3。0</p>
<div class="alert">
<strong>注意</strong><br/><p>安裝 PowerShell 3.0 需要重新開機。</p>
</div>
<div>

</div></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>Windows 7</p></td>
<td align="left"><p>尚未安裝必備軟體。 您必須先安裝它，才能安裝 App-v。</p></td>
</tr>
</tbody>
</table>



## App-v Server 必備軟體


安裝 App-v 5.1 Server 元件所需的必備軟體。

### 開始前的須知

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>安裝 App-v Server 的帳戶</p></td>
<td align="left"><p>您用來安裝 App-V 伺服器元件的帳戶必須具有：</p>
<ul>
<li><p>您要安裝元件的電腦的系統管理許可權。</p></li>
<li><p>查詢 Active Directory 網域服務的功能。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>埠和防火牆</p></td>
<td align="left"><ul>
<li><p>指定將託管每個元件的埠。</p></li>
<li><p>新增關聯的防火牆規則，以允許傳入要求到指定的埠。</p></li>
</ul>
<p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>Web 分散式撰寫及版本設定（WebDAV）</p></td>
<td align="left"><p>系統會針對管理服務自動停用 WebDAV。</p></td>
</tr>
<tr class="even">
<td align="left"><p>支援的部署案例</p></td>
<td align="left"><ul>
<li><p>獨立部署，其中所有元件都部署在同一個伺服器上。</p></li>
<li><p>分散式部署。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>不支援的部署案例</p></td>
<td align="left"><ul>
<li><p>在同一台伺服器上安裝多個 App-v Server 版本的並排實例。</p></li>
<li><p>在執行伺服器核心或網網域控制站的電腦上安裝 app-v server 元件。</p></li>
</ul></td>
</tr>
</tbody>
</table>



### 管理伺服器必備的軟體

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">先決條件及必要設定</th>
<th align="left">詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>支援的 SQL Server 版本</p></td>
<td align="left"><p>如需支援的版本，請參閱 <a href="app-v-51-supported-configurations.md" data-raw-source="[App-V 5.1 Supported Configurations](app-v-51-supported-configurations.md)"> app-v 5.1 支援的設定 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com//download/details.aspx?id=40773" data-raw-source="[Microsoft .NET Framework 4.5.1 (Web Installer)](https://www.microsoft.com//download/details.aspx?id=40773)">Microsoft .NET Framework 4.5.1 （Web 安裝程式）</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=34595" data-raw-source="[Windows PowerShell 3.0](https://www.microsoft.com/download/details.aspx?id=34595)">Windows PowerShell 3。0</a></p></td>
<td align="left"><p>安裝 PowerShell 3.0 需要重新開機。</p></td>
</tr>
<tr class="even">
<td align="left"><p>下載並安裝 <a href="https://support.microsoft.com/kb/2533623" data-raw-source="[KB2533623](https://support.microsoft.com/kb/2533623)"> KB2533623</a></p></td>
<td align="left"><p>僅適用于 Windows 7。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)">Visual Studio 2013 的 visual c + + 可再發行套件</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>64位 ASP.NET 註冊</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server Web Server 角色</p></td>
<td align="left"><p>這個角色必須新增至管理伺服器支援的伺服器作業系統。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Web 服務器（IIS）管理工具</p></td>
<td align="left"><p>按一下 [ <strong> IIS 管理腳本與工具] </strong> 。</p></td>
</tr>
<tr class="odd">
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
</ul>
<p><strong>管理工具：</strong></p>
<ul>
<li><p>IIS 管理主控台</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>預設安裝位置</p></td>
<td align="left"><p>%PROGRAMFILES%\Microsoft 應用程式虛擬化伺服器</p></td>
</tr>
<tr class="odd">
<td align="left"><p>管理資料庫的位置</p></td>
<td align="left"><p>[SQL Server 資料庫名稱]、[SQL Server 資料庫實例名稱] 和 [資料庫名稱]。</p></td>
</tr>
<tr class="even">
<td align="left"><p>管理主控台與管理資料庫許可權</p></td>
<td align="left"><p>部署完成後可以存取管理主控台和資料庫的使用者或群組。 除非使用管理主控台新增其他管理員，否則只有這些使用者或群組才能存取管理主控台和資料庫。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>管理服務網站名稱</p></td>
<td align="left"><p>管理主控台網站的名稱。</p></td>
</tr>
<tr class="even">
<td align="left"><p>管理服務埠系結</p></td>
<td align="left"><p>管理服務的唯一端口號碼。 此埠無法由電腦上的另一個處理常式使用。</p></td>
</tr>
</tbody>
</table>



**重要**  
您必須在開啟 Web 管理主控台的瀏覽器上啟用 JavaScript。



### 管理伺服器資料庫必備軟體

只有在您使用 App-v 5.1 管理伺服器時，才需要管理資料庫。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">先決條件及必要設定</th>
<th align="left">詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="https://www.microsoft.com//download/details.aspx?id=40773" data-raw-source="[Microsoft .NET Framework 4.5.1 (Web Installer)](https://www.microsoft.com//download/details.aspx?id=40773)">Microsoft .NET Framework 4.5.1 （Web 安裝程式）</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)">Visual Studio 2013 的 visual c + + 可再發行套件</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>預設安裝位置</p></td>
<td align="left"><p>%PROGRAMFILES%\Microsoft 應用程式虛擬化伺服器</p></td>
</tr>
<tr class="even">
<td align="left"><p>自訂 SQL Server 實例名稱（如果適用的話）</p></td>
<td align="left"><p>要使用的格式： <strong> INSTANCENAME</strong></p>
<p>此格式是根據安裝在本機電腦上的假設所得到的。</p>
<p>如果您使用 [SVR\INSTANCE] 格式指定 <strong> 名稱 </strong> ，安裝將會失敗。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>自訂資料庫名稱（如果適用的話）</p></td>
<td align="left"><p>唯一的資料庫名稱。</p>
<p>預設值： AppVManagement</p></td>
</tr>
<tr class="even">
<td align="left"><p>管理伺服器位置</p></td>
<td align="left"><p>部署管理伺服器的電腦帳戶。</p>
<p>使用格式： Domain\MachineAccount</p></td>
</tr>
<tr class="odd">
<td align="left"><p>管理伺服器安裝系統管理員</p></td>
<td align="left"><p>用於安裝管理伺服器的帳戶。</p>
<p>使用格式： Domain\AdministratorLoginName</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft SQL Server 服務代理程式</p></td>
<td align="left"><p>設定管理資料庫電腦，讓 Microsoft SQL Server Agent 服務自動重新開機。 如需相關指示，請參閱 <a href="https://technet.microsoft.com/magazine/gg313742.aspx" data-raw-source="[Configure SQL Server Agent to Restart Services Automatically](https://technet.microsoft.com/magazine/gg313742.aspx)"> 設定 SQL Server 代理程式來自動重新開機服務 </a> 。</p></td>
</tr>
</tbody>
</table>



### 發佈伺服器必備軟體

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">先決條件及必要設定</th>
<th align="left">詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="https://www.microsoft.com//download/details.aspx?id=40773" data-raw-source="[Microsoft .NET Framework 4.5.1 (Web Installer)](https://www.microsoft.com//download/details.aspx?id=40773)">Microsoft .NET Framework 4.5.1 （Web 安裝程式）</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)">Visual Studio 2013 的 visual c + + 可再發行套件</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>64位 ASP.NET 註冊</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server Web Server 角色</p></td>
<td align="left"><p>這個角色必須新增至管理伺服器支援的伺服器作業系統。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Web 服務器（IIS）管理工具</p></td>
<td align="left"><p>按一下 [ <strong> IIS 管理腳本與工具] </strong> 。</p></td>
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
</ul>
<p><strong>管理工具：</strong></p>
<ul>
<li><p>IIS 管理主控台</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>預設安裝位置</p></td>
<td align="left"><p>%PROGRAMFILES%\Microsoft 應用程式虛擬化伺服器</p></td>
</tr>
<tr class="even">
<td align="left"><p>管理服務 URL</p></td>
<td align="left"><p>App-v 管理服務的 URL。 這是發佈伺服器要與之通訊的埠。</p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">安裝架構</th>
<th align="left">URL 要使用的格式</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>管理伺服器和發佈伺服器都安裝在相同的伺服器上</p></td>
<td align="left"><p><a href="http://localhost:12345" data-raw-source="http://localhost:12345">http://localhost:12345</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>管理伺服器和發佈伺服器都安裝在不同的伺服器上</p></td>
<td align="left"><p><a href="http://MyAppvServer.MyDomain.com" data-raw-source="http://MyAppvServer.MyDomain.com">http://MyAppvServer.MyDomain.com</a></p></td>
</tr>
</tbody>
</table>
<p> </p>
<p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>發佈服務網站名稱</p></td>
<td align="left"><p>發佈網站的名稱。</p></td>
</tr>
<tr class="even">
<td align="left"><p>發佈服務埠系結</p></td>
<td align="left"><p>發佈服務的唯一端口號碼。 此埠無法由電腦上的另一個處理常式使用。</p></td>
</tr>
</tbody>
</table>



### 報表伺服器必備軟體

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">先決條件及必要設定</th>
<th align="left">詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>支援的 SQL Server 版本</p></td>
<td align="left"><p>如需支援的版本，請參閱 <a href="app-v-51-supported-configurations.md" data-raw-source="[App-V 5.1 Supported Configurations](app-v-51-supported-configurations.md)"> app-v 5.1 支援的設定 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com//download/details.aspx?id=40773" data-raw-source="[Microsoft .NET Framework 4.5.1 (Web Installer)](https://www.microsoft.com//download/details.aspx?id=40773)">Microsoft .NET Framework 4.5.1 （Web 安裝程式）</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)">Visual Studio 2013 的 visual c + + 可再發行套件</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>64位 ASP.NET 註冊</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server Web Server 角色</p></td>
<td align="left"><p>這個角色必須新增至管理伺服器支援的伺服器作業系統。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Web 服務器（IIS）管理工具</p></td>
<td align="left"><p>按一下 [ <strong> IIS 管理腳本與工具] </strong> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Web 服務器角色服務</p></td>
<td align="left"><p>若要降低將有害或惡意資料傳送至報表伺服器的風險，您應該限制每個公司安全性原則存取報表 Web 服務。</p>
<p><strong>常見的 HTTP 功能：</strong></p>
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
</ul>
<p><strong>管理工具：</strong></p>
<ul>
<li><p>IIS 管理主控台</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>預設安裝位置</p></td>
<td align="left"><p>%PROGRAMFILES%\Microsoft 應用程式虛擬化伺服器</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Reporting services 網站名稱</p></td>
<td align="left"><p>報告網站的名稱。</p></td>
</tr>
<tr class="even">
<td align="left"><p>報表服務埠系結</p></td>
<td align="left"><p>報表服務的唯一端口號碼。 此埠無法由電腦上的另一個處理常式使用。</p></td>
</tr>
</tbody>
</table>



### 報表資料庫必備軟體

只有在您使用 App-v 5.1 報表伺服器時，才需要報告資料庫。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">先決條件及必要設定</th>
<th align="left">詳細資料</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="https://www.microsoft.com//download/details.aspx?id=40773" data-raw-source="[Microsoft .NET Framework 4.5.1 (Web Installer)](https://www.microsoft.com//download/details.aspx?id=40773)">Microsoft .NET Framework 4.5.1 （Web 安裝程式）</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)">Visual Studio 2013 的 visual c + + 可再發行套件</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>預設安裝位置</p></td>
<td align="left"><p>%PROGRAMFILES%\Microsoft 應用程式虛擬化伺服器</p></td>
</tr>
<tr class="even">
<td align="left"><p>自訂 SQL Server 實例名稱（如果適用的話）</p></td>
<td align="left"><p>要使用的格式： <strong> INSTANCENAME</strong></p>
<p>此格式是根據安裝在本機電腦上的假設所得到的。</p>
<p>如果您使用 [SVR\INSTANCE] 格式指定 <strong> 名稱 </strong> ，安裝將會失敗。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>自訂資料庫名稱（如果適用的話）</p></td>
<td align="left"><p>唯一的資料庫名稱。</p>
<p>預設值： AppVReporting</p></td>
</tr>
<tr class="even">
<td align="left"><p>報表伺服器位置</p></td>
<td align="left"><p>部署報表伺服器的電腦帳戶。</p>
<p>使用格式： Domain\MachineAccount</p></td>
</tr>
<tr class="odd">
<td align="left"><p>報表伺服器安裝系統管理員</p></td>
<td align="left"><p>用於安裝報表伺服器的帳戶。</p>
<p>使用格式： Domain\AdministratorLoginName</p></td>
</tr>
<tr class="even">
<td align="left"><p>Microsoft SQL Server 服務與 Microsoft SQL Server Service 代理</p></td>
<td align="left"><p>將這些服務設定為與具有查詢 AD DS 存取權的使用者帳戶相關聯。</p></td>
</tr>
</tbody>
</table>



## App-V 用戶端必備軟體


針對 App-V 用戶端安裝下列必備軟體。

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
<td align="left"><p><a href="https://www.microsoft.com//download/details.aspx?id=40773" data-raw-source="[Microsoft .NET Framework 4.5.1 (Web Installer)](https://www.microsoft.com//download/details.aspx?id=40773)">Microsoft .NET Framework 4.5.1 （Web 安裝程式）</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=34595" data-raw-source="[Windows PowerShell 3.0](https://www.microsoft.com/download/details.aspx?id=34595)">Windows PowerShell 3。0</a></p>
<p></p></td>
<td align="left"><p>安裝 PowerShell 3.0 需要重新開機。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="https://support.microsoft.com/kb/2533623" data-raw-source="[KB2533623](https://support.microsoft.com/kb/2533623)">KB2533623</a></p></td>
<td align="left"><p>僅適用于 Windows 7：下載並安裝 KB。</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)">Visual Studio 2013 的 visual c + + 可再發行套件</a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



## 遠端桌面服務用戶端必備軟體


安裝 App-v 遠端桌面服務用戶端的下列必備軟體。

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
<td align="left"><p><a href="https://www.microsoft.com//download/details.aspx?id=40773" data-raw-source="[Microsoft .NET Framework 4.5.1 (Web Installer)](https://www.microsoft.com//download/details.aspx?id=40773)">Microsoft .NET Framework 4.5.1 （Web 安裝程式）</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=34595" data-raw-source="[Windows PowerShell 3.0](https://www.microsoft.com/download/details.aspx?id=34595)">Windows PowerShell 3。0</a></p>
<p></p></td>
<td align="left"><p>安裝 PowerShell 3.0 需要重新開機。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="https://support.microsoft.com/kb/2533623" data-raw-source="[KB2533623](https://support.microsoft.com/kb/2533623)">KB2533623</a></p></td>
<td align="left"><p>僅適用于 Windows 7：下載並安裝 KB。</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)">Visual Studio 2013 的 visual c + + 可再發行套件</a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



## Sequencer 必備軟體


**安裝先決條件前的須知事項：**

-   最佳做法：執行排序器的電腦應該擁有與將執行虛擬應用程式的電腦相同的硬體和軟體配置。

-   排序程式需要大量的資源，因此請確定執行排序器的電腦有大量的記憶體、快速的處理器，以及快速硬碟。 本機安裝的應用程式的系統需求不能超過排序器的要求。 如需詳細資訊，請參閱[App-V 5.1 支援的](app-v-51-supported-configurations.md)設定。

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
<td align="left"><p><a href="https://www.microsoft.com//download/details.aspx?id=40773" data-raw-source="[Microsoft .NET Framework 4.5.1 (Web Installer)](https://www.microsoft.com//download/details.aspx?id=40773)">Microsoft .NET Framework 4.5.1 （Web 安裝程式）</a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=34595" data-raw-source="[Windows PowerShell 3.0](https://www.microsoft.com/download/details.aspx?id=34595)">Windows PowerShell 3。0</a></p>
<p></p></td>
<td align="left"><p>安裝 PowerShell 3.0 需要重新開機。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="https://support.microsoft.com/kb/2533623" data-raw-source="[KB2533623](https://support.microsoft.com/kb/2533623)">KB2533623</a></p></td>
<td align="left"><p>僅適用于 Windows 7：下載並安裝 KB。</p></td>
</tr>
</tbody>
</table>








## 相關主題


[為 App-V 5.1 進行規劃](planning-for-app-v-51.md)

[App-V 5.1 支援的組態](app-v-51-supported-configurations.md)









