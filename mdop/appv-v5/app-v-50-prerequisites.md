---
title: App-V 5.0 必要條件
description: App-V 5.0 必要條件
author: dansimp
ms.assetid: 9756b571-c785-4ce6-a95c-d4e134e89429
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 176c9729d8c909325c6d6694e024938d9ce9df53
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800687"
---
# App-V 5.0 必要條件

在您開始使用 Microsoft Application Virtualization （App-v）5.0 安裝程式之前，請務必確定您已滿足安裝產品的先決條件。 本主題包含的資訊可協助您成功地規劃如何在部署 app-v 5.0 功能前準備您的計算環境。

> [!Important]
> **本文中的先決條件只適用于 app-v 5.0**。 如需適用于 App-v 5.0 Service Pack 的其他先決條件，請參閱下列網頁：

-   [App-V 5.0 SP1 的新功能](whats-new-in-app-v-50-sp1.md)

-   [關於 App-V 5.0 SP2](about-app-v-50-sp2.md)

-   [App-V 5.0 SP3 必要條件](app-v-50-sp3-prerequisites.md)

下表列出適用于特定作業系統的先決條件資訊。

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
<td align="left"><p>正在執行的電腦：</p>
<ul>
<li><p>Windows8</p></li>
<li><p>Windows Server 2012</p></li>
</ul></td>
<td align="left"><p>已安裝下列先決條件：</p>
<ul>
<li><p>Microsoft .NET Framework 4.5 –您不需要 Microsoft .NET Framework 4</p></li>
<li><p>Windows PowerShell 3。0</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>正在執行的電腦：</p>
<ul>
<li><p>Windows 7</p></li>
<li><p>Windows Server 2008</p></li>
</ul></td>
<td align="left"><p>您可能會想要下載下列 KB：</p>
<p><a href="https://support.microsoft.com/kb/2533623" data-raw-source="[Microsoft Security Advisory: Insecure library loading could allow remote code execution](https://support.microsoft.com/kb/2533623)">Microsoft 安全通報：不安全的文件庫載入可能允許遠端執行程式碼</a></p>
<p>請務必檢查是否有已取代的後續 KBs，並請注意，某些 KBs 可能需要您卸載先前的更新。</p></td>
</tr>
</tbody>
</table>

## App-v 5.0 的安裝先決條件

> [!Note]  
> 已針對執行 Windows 8 的電腦安裝下列先決條件。

每個 App-v 5.0 功能都有特定的先決條件，您必須先滿足這些先決條件，才能成功安裝 App-v 5.0 功能。

### App-V 5.0 用戶端的先決條件

下表列出 App-V 5.0 用戶端的安裝先決條件：

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
<td align="left"><p><strong>軟體需求</strong></p></td>
<td align="left"><ul>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=17718" data-raw-source="[Microsoft .NET Framework 4 (Full Package)](https://www.microsoft.com/download/details.aspx?id=17718)">Microsoft .NET Framework 4 （完整套件）</p></li>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=34595" data-raw-source="[Windows PowerShell 3.0](https://www.microsoft.com/download/details.aspx?id=34595)">Windows PowerShell 3。0</a></p>
<p></p>
<div class="alert">
<strong>注意</strong><br/><p>安裝 PowerShell 3.0 需要重新開機。</p>
</div>
<div>

</div></li>
<li><p>下載並安裝 <a href="https://support.microsoft.com/kb/2533623" data-raw-source="[KB2533623](https://support.microsoft.com/kb/2533623)"> KB2533623</a></p>
<p></p>
<div class="alert">
<strong>重要</strong><br/><p>您可以下載並安裝舊版的知識庫文章。 不過，它可能已由較新的版本取代。</p>
</div>
<div>

</div></li>
<li><p>用戶端安裝程式（.exe）會偵測到是否需要安裝下列先決條件，這將會如此操作：</p>
<p></p>
<ul>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)">Visual Studio 2013 的 visual c + + 可再發行套件</a></p>
<p>只有當您已安裝應用程式虛擬化 5.0 SP2 或更新版本的修補程式套件4時，才能使用此先決條件。</p>
<p></p></li>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=26999" data-raw-source="[The Microsoft Visual C++ 2010 Redistributable](https://www.microsoft.com/download/details.aspx?id=26999)">Microsoft Visual c + + 2010 可轉散發元件</a></p>
<p></p></li>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=5638" data-raw-source="[Microsoft Visual C++ 2005 SP1 Redistributable Package (x86)](https://www.microsoft.com/download/details.aspx?id=5638)">Microsoft Visual c + + 2005 SP1 可再發行套件（x86）</a></p></li>
</ul></li>
</ul></td>
</tr>
</tbody>
</table>

### App-V 5.0 遠端桌面服務用戶端的先決條件

> [!Note]  
> 已針對執行 Windows Server 2012 的電腦安裝下列先決條件。

下表列出 App-V 5.0 遠端桌面服務用戶端的安裝先決條件：

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
<td align="left"><p><strong>軟體需求</strong></p></td>
<td align="left"><ul>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=17718" data-raw-source="[Microsoft.NET Framework 4 (Full Package)](https://www.microsoft.com/download/details.aspx?id=17718)">Microsoft.NET Framework 4 （完整套件）</a></p></li>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=34595" data-raw-source="[Windows PowerShell 3.0](https://www.microsoft.com/download/details.aspx?id=34595)">Windows PowerShell 3。0</a></p>
<p></p>
<div class="alert">
<strong>注意</strong><br/><p>安裝 PowerShell 3.0 需要重新開機。</p>
</div>
<div>

</div></li>
<li><p>下載並安裝 <a href="https://go.microsoft.com/fwlink/?LinkId=286102" data-raw-source="[KB2533623](https://go.microsoft.com/fwlink/?LinkId=286102 )"> KB2533623</a></p>
<p></p>
<div class="alert">
<strong>重要</strong><br/><p>您可以下載並安裝舊版的知識庫文章。 不過，它可能已由較新的版本取代。</p>
</div>
<div>

</div></li>
<li><p>用戶端（.exe）安裝程式會偵測到是否需要安裝下列先決條件，這將會如此進行：</p>
<p></p>
<ul>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)">Visual Studio 2013 的 visual c + + 可再發行套件</a></p>
<p>只有當您已安裝應用程式虛擬化 5.0 SP2 或更新版本的修補程式套件4時，才需要此先決條件。</p>
<p></p></li>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=26999" data-raw-source="[The Microsoft Visual C++ 2010 Redistributable](https://www.microsoft.com/download/details.aspx?id=26999)">Microsoft Visual c + + 2010 可轉散發元件</a></p>
<p></p></li>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=5638" data-raw-source="[Microsoft Visual C++ 2005 SP1 Redistributable Package (x86)](https://www.microsoft.com/download/details.aspx?id=5638)">Microsoft Visual c + + 2005 SP1 可再發行套件（x86）</a></p></li>
</ul></li>
</ul></td>
</tr>
</tbody>
</table>

### App-v 5.0 排序器的先決條件

> [!Note]
> 已針對執行 Windows 8 和 Windows Server 2012 的電腦安裝下列先決條件。

下表列出應用程式 V 5.0 排序器的安裝先決條件。 如果可能的話，執行排序器的電腦應該擁有與將執行虛擬應用程式的電腦相同的硬體和軟體配置。

> [!Note]  
> 如果本機安裝應用程式的系統需求超過排序器的需求，您必須符合該應用程式的需求。 此外，由於先後連續處理程式是佔用大量的系統資源，因此建議執行排序器的電腦具有大量的記憶體、快速的處理器，以及快速硬碟。 如需詳細資訊，請參閱[app-v 5.0 支援的](app-v-50-supported-configurations.md)設定。

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
<td align="left"><p><strong>軟體需求</strong></p></td>
<td align="left"><ul>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)">Visual Studio 2013 的 visual c + + 可再發行套件</a></p>
<p>只有當您已安裝應用程式虛擬化 5.0 SP2 的修補程式套件4時，才需要此先決條件。</p>
<p></p></li>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=17718" data-raw-source="[Microsoft .NET Framework 4 (Full Package)](https://www.microsoft.com/download/details.aspx?id=17718)">Microsoft .NET Framework 4 （完整套件）</a></p>
<p></p></li>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=34595" data-raw-source="[Windows PowerShell 3.0](https://www.microsoft.com/download/details.aspx?id=34595)">Windows PowerShell 3。0</a></p>
<p></p></li>
<li><p>下載並安裝 <a href="https://support.microsoft.com/kb/2533623" data-raw-source="[KB2533623](https://support.microsoft.com/kb/2533623)"> KB2533623</a></p>
<p></p></li>
<li><p>針對執行 Microsoft Windows Server 2008 R2 SP1 的電腦，請下載並安裝 <a href="https://go.microsoft.com/fwlink/?LinkId=286102" data-raw-source="[KB2533623](https://go.microsoft.com/fwlink/?LinkId=286102 )"> KB2533623</a></p>
<p></p>
<div class="alert">
<strong>重要</strong><br/><p>您可以下載並安裝先前的其中一個知識庫文章。 不過，它們可能已由較新的版本取代。</p>
</div>
<div>

</div></li>
</ul></td>
</tr>
</tbody>
</table>

### App-v 5.0 server 的先決條件

> [!Note]
> 已針對執行 Windows Server 2012 的電腦安裝下列先決條件：

-   Microsoft .NET Framework 4.5。 這會消除 Microsoft .NET Framework 4 的需求。

-   Windows PowerShell 3。0

-   下載並安裝[KB2533623](https://support.microsoft.com/kb/2533623) （https://support.microsoft.com/kb/2533623)

    > [!Important]
    > 您仍然可以下載 [安裝前一個 KB]。 不過，它可能已由較新的版本取代。

下表列出 App-V 5.0 伺服器的安裝先決條件。 您用來安裝伺服器元件的帳戶，必須在您要安裝的電腦上擁有系統管理許可權。 這個帳戶也必須具備查詢 Active Directory 目錄服務的功能。 在您安裝並設定 App-v 5.0 伺服器之前，您必須指定將託管每個元件的埠。 您也必須新增相關聯的防火牆規則，以允許傳入要求到指定的埠。

> [!Note]
> 系統會自動停用管理服務的 Web 分散式撰寫及版本設定（WebDAV）。

針對獨立部署支援 App-v 5.0 伺服器，且所有元件都部署在同一台伺服器上，以及分散式部署。 根據您用來部署 app-v 5.0 server 的拓撲，您需要的每個元件資料都會稍有變更。

> [!Important]
> 在執行任何舊版或 App-v 元件的電腦上安裝 app-v 5.0 server 不受支援。 此外，也不支援在執行伺服器核心或網網域控制站的電腦上安裝伺服器元件。

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
<td align="left"><p><strong>管理伺服器</strong></p></td>
<td align="left"><ul>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=17718" data-raw-source="[Microsoft .NET Framework 4 (Full Package)](https://www.microsoft.com/download/details.aspx?id=17718)">Microsoft .NET Framework 4 （完整套件）</a></p></li>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=34595" data-raw-source="[Windows PowerShell 3.0](https://www.microsoft.com/download/details.aspx?id=34595)">Windows PowerShell 3。0</a></p>
<div class="alert">
<strong>注意</strong><br/><p>安裝 PowerShell 3.0 需要重新開機。</p>
</div>
<div>

</div></li>
<li><p>啟用 IIS 角色且具有下列功能的 Windows Web 服務器： <strong> 常見的 HTTP 功能 </strong> （靜態內容和預設檔）、 <strong> 應用程式開發 </strong> （ASP.NET、.Net 擴充性、ISAPI 延伸及 ISAPI 篩選）、 <strong> 安全性 </strong> （Windows 驗證、要求篩選）、 <strong> 管理工具 </strong> （IIS 管理主控台）。</p></li>
<li><p>下載並安裝 <a href="https://support.microsoft.com/kb/2533623" data-raw-source="[KB2533623](https://support.microsoft.com/kb/2533623)"> KB2533623</a></p>
<p></p>
<div class="alert">
<strong>重要</strong><br/><p>您仍然可以下載 [安裝前一個 KB]。 不過，它可能已由較新的版本取代。</p>
</div>
<div>

</div></li>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=13523" data-raw-source="[Microsoft Visual C++ 2010 SP1 Redistributable Package (x64)](https://www.microsoft.com/download/details.aspx?id=13523)">Microsoft Visual c + + 2010 SP1 可再發行套件（x64）</a></p></li>
<li><p><a href="https://go.microsoft.com/fwlink/?LinkId=267110" data-raw-source="[Microsoft Visual C++ 2010 SP1 Redistributable Package (x86)](https://go.microsoft.com/fwlink/?LinkId=267110)">Microsoft Visual c + + 2010 SP1 可再發行套件（x86）</a></p></li>
<li><p>64位 ASP.NET 註冊</p></li>
</ul>
<p>App-v 5.0 伺服器元件是相依的，但它們必須要部署的需求和安裝選項不同。 使用下列資訊來準備您的環境，以執行 App-v 5.0 管理伺服器。</p>
<ul>
<li><p>安裝位置-預設會將此元件安裝至： <strong> %PROGRAMFILES%\Microsoft Application Virtualization 伺服器 </strong> 。</p></li>
<li><p>App-V 5.0 管理資料庫-SQL Server 名稱、SQL 實例名稱、資料庫名稱的位置。</p></li>
<li><p>App-V 5.0 管理主控台的存取許可權-這是在部署結束時應該獲准存取管理主控台的使用者或群組。 部署之後，只有這些使用者才能存取管理主控台，直到透過管理主控台新增其他系統管理員為止。</p>
<div class="alert">
<strong>注意</strong><br/><p>不支援安全性群組與單一使用者。 您必須指定 AD DS 群組。</p>
</div>
<div>

</div></li>
<li><p>App-v 5.0 管理服務網站名稱–指定網站的名稱或使用預設名稱。</p></li>
<li><p>App-V 5.0 管理服務埠系結-這應該是電腦上其他網站不使用的唯一端口號碼。</p></li>
<li><p>必須先安裝 Microsoft silverlight 的支援，才能使用管理主控台。 雖然這不是部署的必要條件，但伺服器必須能夠支援 Microsoft Silverlight。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><strong>管理資料庫</strong></p></td>
<td align="left"><p></p>
<div class="alert">
<strong>注意</strong><br/><p>只有在使用 App-v 5.0 管理伺服器時，才需要資料庫。</p>
</div>
<div>

</div>
<ul>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=17718" data-raw-source="[Microsoft .NET Framework 4 (Full Package)](https://www.microsoft.com/download/details.aspx?id=17718)">Microsoft .NET Framework 4 （完整套件）</a></p></li>
<li><p><a href="https://go.microsoft.com/fwlink/?LinkId=267110" data-raw-source="[Microsoft Visual C++ 2010 SP1 Redistributable Package (x86)](https://go.microsoft.com/fwlink/?LinkId=267110)">Microsoft Visual c + + 2010 SP1 可再發行套件（x86）</a></p></li>
</ul>
<p>App-v 5.0 伺服器元件是相依的，但它們必須要部署的需求和安裝選項不同。 使用下列資訊來準備您的環境，以執行 App-v 5.0 管理資料庫。</p>
<ul>
<li><p>安裝位置-預設會將此元件安裝至 <strong> %PROGRAMFILES%\Microsoft Application Virtualization 伺服器 </strong> 。</p></li>
<li><p>自訂 SQL Server 實例名稱（如果適用的話）-格式應該是 <strong> INSTANCENAME </strong> ，因為安裝假設它位於本機電腦上。 如果您使用下列格式指定名稱， <strong> SVR\INSTANCE 將會 </strong> 失敗。</p></li>
<li><p>自訂 App-v 5.0 資料庫名稱（如果適用的話）–您必須指定唯一的資料庫名稱。 管理資料庫的預設值為 [ <strong> AppVManagement] </strong> 。</p></li>
<li><p>App-V 5.0 管理伺服器位置–指定部署管理伺服器的電腦帳戶。 此選項應以下列格式指定 <strong> Domain\MachineAccount </strong> 。</p></li>
<li><p>App-V 5.0 管理伺服器安裝系統管理員-指定將用來安裝 App-v 5.0 管理伺服器的帳戶。 您應該使用下列格式： <strong> Domain\AdministratorLoginName </strong> 。</p></li>
<li><p>Microsoft SQL Server 服務代理程式-將執行 App-v 5.0 管理資料庫的電腦設定為自動重新開機 Microsoft SQL Server 代理服務。 如需詳細資訊，請參閱 <a href="https://go.microsoft.com/fwlink/?LinkId=273725" data-raw-source="[Configure SQL Server Agent to Restart Services Automatically](https://go.microsoft.com/fwlink/?LinkId=273725)"> 設定 SQL Server 代理程式來自動重新開機服務</a></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>報表伺服器</strong></p></td>
<td align="left"><ul>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=17718" data-raw-source="[Microsoft .NET Framework 4 (Full Package)](https://www.microsoft.com/download/details.aspx?id=17718)">Microsoft .NET Framework 4 （完整套件）</a></p></li>
<li><p><a href="https://go.microsoft.com/fwlink/?LinkId=267110" data-raw-source="[Microsoft Visual C++ 2010 SP1 Redistributable Package (x86)](https://go.microsoft.com/fwlink/?LinkId=267110)">Microsoft Visual c + + 2010 SP1 可再發行套件（x86）</a></p></li>
<li><div class="alert">
<strong>注意</strong><br/><p>若要協助降低傳送至報表伺服器的有害或惡意資料的風險，您應該針對每個公司安全原則，限制對報表 Web 服務的存取權。</p>
</div>
<div>

</div>
<p>具有下列功能之 IIS 角色的 Windows Web 服務器： <strong> 常見 HTTP 功能 </strong> （靜態內容和預設檔）、 <strong> 應用程式開發 </strong> （ASP.NET、.Net 擴充性、ISAPI 延伸及 ISAPI 篩選）、安全性（windows 驗證、要求篩選）、 <strong> </strong> <strong> 安全性 </strong> （Windows 驗證、要求篩選）、 <strong> 管理工具 </strong> （IIS 管理主控台）</p></li>
<li><p>64位 ASP.NET 註冊</p></li>
<li><p>安裝位置-預設會將此元件安裝至 <strong> %PROGRAMFILES%\Microsoft Application Virtualization 伺服器 </strong> 。</p></li>
<li><p>App-v 5.0 reporting services 網站名稱–指定要使用的網站名稱或預設名稱。</p></li>
<li><p>App-v 5.0 報表服務埠系結-這應該是在電腦上執行的其他網站尚未使用的唯一端口號碼。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><strong>報表資料庫</strong></p></td>
<td align="left"><p></p>
<div class="alert">
<strong>注意</strong><br/><p>只有在使用 App-v 5.0 報表伺服器時，才需要資料庫。</p>
</div>
<div>

</div>
<ul>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=17718" data-raw-source="[Microsoft .NET Framework 4 (Full Package)](https://www.microsoft.com/download/details.aspx?id=17718)">Microsoft .NET Framework 4 （完整套件）</a></p></li>
<li><p><a href="https://go.microsoft.com/fwlink/?LinkId=267110" data-raw-source="[Microsoft Visual C++ 2010 SP1 Redistributable Package (x86)](https://go.microsoft.com/fwlink/?LinkId=267110)">Microsoft Visual c + + 2010 SP1 可再發行套件（x86）</a></p></li>
</ul>
<p>App-v 5.0 伺服器元件是相依的，但它們必須要部署的需求和安裝選項不同。 請使用下列資訊來準備您的環境，以執行 App-v 5.0 報告資料庫。</p>
<ul>
<li><p>安裝位置-預設會將此元件安裝至 <strong> %PROGRAMFILES%\Microsoft Application Virtualization 伺服器 </strong> 。</p></li>
<li><p>自訂 SQL Server 實例名稱（如果適用的話）-格式應該是 <strong> INSTANCENAME </strong> ，因為安裝假設它位於本機電腦上。 如果您使用下列格式指定名稱， <strong> SVR\INSTANCE 將會 </strong> 失敗。</p></li>
<li><p>自訂 App-v 5.0 資料庫名稱（如果適用的話）–您必須指定唯一的資料庫名稱。 報告資料庫的預設值為 [ <strong> AppVReporting] </strong> 。</p></li>
<li><p>App-v 5.0 報表伺服器位置–指定部署報表伺服器的電腦帳戶。 此選項應以下列格式指定 <strong> Domain\MachineAccount </strong> 。</p></li>
<li><p>App-V 5.0 報表伺服器安裝系統管理員-指定將用來安裝 App-v 5.0 報表服務器的帳戶。 您應該使用下列格式： <strong> Domain\AdministratorLoginName </strong> 。</p></li>
<li><p>Microsoft SQL Server 服務及 Microsoft SQL server 代理服務–這些服務必須與有權存取查詢廣告的使用者帳戶相關聯。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>發佈伺服器</strong></p></td>
<td align="left"><ul>
<li><p><a href="https://www.microsoft.com/download/details.aspx?id=17718" data-raw-source="[Microsoft .NET Framework 4 (Full Package)](https://www.microsoft.com/download/details.aspx?id=17718)">Microsoft .NET Framework 4 （完整套件）</a></p></li>
<li><p><a href="https://go.microsoft.com/fwlink/?LinkId=267110" data-raw-source="[Microsoft Visual C++ 2010 SP1 Redistributable Package (x86)](https://go.microsoft.com/fwlink/?LinkId=267110)">Microsoft Visual c + + 2010 SP1 可再發行套件（x86）</a></p></li>
<li><p>具有下列功能之 IIS 角色的 Windows Web 服務器： <strong> 常見 HTTP 功能 </strong> （靜態內容和預設檔）、 <strong> 應用程式開發 </strong> （ASP.NET、.Net 擴充性、ISAPI 延伸及 ISAPI 篩選）、安全性（windows 驗證、要求篩選）、 <strong> </strong> <strong> 安全性 </strong> （Windows 驗證、要求篩選）、 <strong> 管理工具 </strong> （IIS 管理主控台）</p></li>
<li><p>64位 ASP.NET 註冊</p></li>
</ul>
<p>App-v 5.0 伺服器元件是相依的，但它們必須要部署的需求和安裝選項不同。 請使用下列資訊來準備您的環境，以執行 App-v 5.0 發佈伺服器。</p>
<ul>
<li><p>安裝位置-預設會將此元件安裝至 <strong> %PROGRAMFILES%\Microsoft Application Virtualization 伺服器 </strong> 。</p></li>
<li><p>App-V 5.0 管理服務 URL-指定 App-v 5.0 管理服務的 URL。 這是發佈伺服器與之通訊的埠，應使用下列格式加以指定： <strong><a href="http://localhost:12345" data-raw-source="http://localhost:12345"> http://localhost:12345 </a></strong> 。</p></li>
<li><p>App-V 5.0 發佈服務網站名稱–指定要使用的網站名稱或預設名稱。</p></li>
<li><p>App-V 5.0 發佈服務埠系結-這應該是在電腦上執行的其他網站尚未使用的唯一端口號碼。</p></li>
</ul></td>
</tr>
</tbody>
</table>

## 相關主題

[規劃部署 App-V](planning-to-deploy-app-v.md)

[App-V 5.0 支援的組態](app-v-50-supported-configurations.md)
