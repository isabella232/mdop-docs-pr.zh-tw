---
title: App-V 5.0 SP3 必要條件
description: App-V 5.0 SP3 必要條件
author: dansimp
ms.assetid: fa8d5578-3a53-4e8a-95c7-e7a5f6e4a31c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d8e8318a71d2d3631b0ad47e3c3db3c569488790
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800684"
---
# <span data-ttu-id="75e2e-103">App-V 5.0 SP3 必要條件</span><span class="sxs-lookup"><span data-stu-id="75e2e-103">App-V 5.0 SP3 Prerequisites</span></span>


<span data-ttu-id="75e2e-104">在安裝 Microsoft Application Virtualization （App-v） 5.0 SP3 前，請確定您已安裝下列所有必要的軟體。</span><span class="sxs-lookup"><span data-stu-id="75e2e-104">Before installing Microsoft Application Virtualization (App-V) 5.0 SP3, ensure that you have installed all of the following required prerequisite software.</span></span>

<span data-ttu-id="75e2e-105">如需支援的作業系統及 app-v Server、Sequencer 及用戶端的硬體需求清單，請參閱[app-v 5.0 SP3 支援](app-v-50-sp3-supported-configurations.md)的設定。</span><span class="sxs-lookup"><span data-stu-id="75e2e-105">For a list of supported operating systems and hardware requirements for the App-V Server, Sequencer, and Client, see [App-V 5.0 SP3 Supported Configurations](app-v-50-sp3-supported-configurations.md).</span></span>

## <span data-ttu-id="75e2e-106">在每個作業系統上預先安裝的軟體摘要</span><span class="sxs-lookup"><span data-stu-id="75e2e-106">Summary of software preinstalled on each operating system</span></span>


<span data-ttu-id="75e2e-107">下表指出已針對不同作業系統安裝的軟體。</span><span class="sxs-lookup"><span data-stu-id="75e2e-107">The following table indicates the software that is already installed for different operating systems.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="75e2e-108">作業系統</span><span class="sxs-lookup"><span data-stu-id="75e2e-108">Operating system</span></span></th>
<th align="left"><span data-ttu-id="75e2e-109">先決條件描述</span><span class="sxs-lookup"><span data-stu-id="75e2e-109">Prerequisite description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="75e2e-110">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="75e2e-110">Windows 8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="75e2e-111">已安裝所有必備軟體。</span><span class="sxs-lookup"><span data-stu-id="75e2e-111">All of the prerequisite software is already installed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="75e2e-112">Windows8</span><span class="sxs-lookup"><span data-stu-id="75e2e-112">Windows 8</span></span></p>
<p><span data-ttu-id="75e2e-113">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="75e2e-113">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="75e2e-114">下列是已安裝的必備軟體：</span><span class="sxs-lookup"><span data-stu-id="75e2e-114">The following prerequisite software is already installed:</span></span></p>
<ul>
<li><p><span data-ttu-id="75e2e-115">Microsoft .NET Framework 4。5</span><span class="sxs-lookup"><span data-stu-id="75e2e-115">Microsoft .NET Framework 4.5</span></span></p></li>
<li><p><span data-ttu-id="75e2e-116">Windows PowerShell 3。0</span><span class="sxs-lookup"><span data-stu-id="75e2e-116">Windows PowerShell 3.0</span></span></p>
<div class="alert">
<strong><span data-ttu-id="75e2e-117">注意</span><span class="sxs-lookup"><span data-stu-id="75e2e-117">Note</span></span></strong><br/><p><span data-ttu-id="75e2e-118">安裝 PowerShell 3.0 需要重新開機。</span><span class="sxs-lookup"><span data-stu-id="75e2e-118">Installing PowerShell 3.0 requires a restart.</span></span></p>
</div>
<div>

</div></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="75e2e-119">Windows 7</span><span class="sxs-lookup"><span data-stu-id="75e2e-119">Windows 7</span></span></p></td>
<td align="left"><p><span data-ttu-id="75e2e-120">尚未安裝必備軟體。</span><span class="sxs-lookup"><span data-stu-id="75e2e-120">The prerequisite software is not already installed.</span></span> <span data-ttu-id="75e2e-121">您必須先安裝它，才能安裝 App-v。</span><span class="sxs-lookup"><span data-stu-id="75e2e-121">You must install it before you can install App-V.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="75e2e-122">App-v Server 必備軟體</span><span class="sxs-lookup"><span data-stu-id="75e2e-122">App-V Server prerequisite software</span></span>


<span data-ttu-id="75e2e-123">針對 App-V 5.0 SP3 伺服器元件安裝必要的必備軟體。</span><span class="sxs-lookup"><span data-stu-id="75e2e-123">Install the required prerequisite software for the App-V 5.0 SP3 Server components.</span></span>

### <span data-ttu-id="75e2e-124">開始前的須知</span><span class="sxs-lookup"><span data-stu-id="75e2e-124">What to know before you start</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="75e2e-125">安裝 App-v Server 的帳戶</span><span class="sxs-lookup"><span data-stu-id="75e2e-125">Account for installing the App-V Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="75e2e-126">您用來安裝 App-V 伺服器元件的帳戶必須具有：</span><span class="sxs-lookup"><span data-stu-id="75e2e-126">The account that you use to install the App-V Server components must have:</span></span></p>
<ul>
<li><p><span data-ttu-id="75e2e-127">您要安裝元件的電腦的系統管理許可權。</span><span class="sxs-lookup"><span data-stu-id="75e2e-127">Administrative rights on the computer on which you are installing the components.</span></span></p></li>
<li><p><span data-ttu-id="75e2e-128">查詢 Active Directory 網域服務的功能。</span><span class="sxs-lookup"><span data-stu-id="75e2e-128">The ability to query Active Directory Domain Services.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="75e2e-129">埠和防火牆</span><span class="sxs-lookup"><span data-stu-id="75e2e-129">Port and firewall</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="75e2e-130">指定將託管每個元件的埠。</span><span class="sxs-lookup"><span data-stu-id="75e2e-130">Specify a port where each component will be hosted.</span></span></p></li>
<li><p><span data-ttu-id="75e2e-131">新增關聯的防火牆規則，以允許傳入要求到指定的埠。</span><span class="sxs-lookup"><span data-stu-id="75e2e-131">Add the associated firewall rules to allow incoming requests to the specified ports.</span></span></p></li>
</ul>
<p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="75e2e-132">Web 分散式撰寫及版本設定（WebDAV）</span><span class="sxs-lookup"><span data-stu-id="75e2e-132">Web Distributed Authoring and Versioning (WebDAV)</span></span></p></td>
<td align="left"><p><span data-ttu-id="75e2e-133">系統會針對管理服務自動停用 WebDAV。</span><span class="sxs-lookup"><span data-stu-id="75e2e-133">WebDAV is automatically disabled for the Management Service.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="75e2e-134">支援的部署案例</span><span class="sxs-lookup"><span data-stu-id="75e2e-134">Supported deployment scenarios</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="75e2e-135">獨立部署，其中所有元件都部署在同一個伺服器上。</span><span class="sxs-lookup"><span data-stu-id="75e2e-135">A stand-alone deployment, where all components are deployed on the same server.</span></span></p></li>
<li><p><span data-ttu-id="75e2e-136">分散式部署。</span><span class="sxs-lookup"><span data-stu-id="75e2e-136">A distributed deployment.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="75e2e-137">不支援的部署案例</span><span class="sxs-lookup"><span data-stu-id="75e2e-137">Unsupported deployment scenarios</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="75e2e-138">在執行 App-V 任何舊版或元件的電腦上安裝 App-v 伺服器。</span><span class="sxs-lookup"><span data-stu-id="75e2e-138">Installing the App-V Server on a computer that runs any previous version or component of App-V.</span></span></p></li>
<li><p><span data-ttu-id="75e2e-139">在執行伺服器核心或網網域控制站的電腦上安裝 app-v server 元件。</span><span class="sxs-lookup"><span data-stu-id="75e2e-139">Installing the App-V server components on a computer that runs server core or domain controller.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="75e2e-140">管理伺服器必備的軟體</span><span class="sxs-lookup"><span data-stu-id="75e2e-140">Management server prerequisite software</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="75e2e-141">先決條件及必要設定</span><span class="sxs-lookup"><span data-stu-id="75e2e-141">Prerequisites and required settings</span></span></th>
<th align="left"><span data-ttu-id="75e2e-142">詳細資料</span><span class="sxs-lookup"><span data-stu-id="75e2e-142">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="75e2e-143">支援的 SQL Server 版本</span><span class="sxs-lookup"><span data-stu-id="75e2e-143">Supported version of SQL Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="75e2e-144">如需支援的版本，請參閱 <a href="app-v-50-sp3-supported-configurations.md" data-raw-source="[App-V 5.0 SP3 Supported Configurations](app-v-50-sp3-supported-configurations.md)"> App-V 5.0 SP3 支援 </a> 的配置。</span><span class="sxs-lookup"><span data-stu-id="75e2e-144">For supported versions, see <a href="app-v-50-sp3-supported-configurations.md" data-raw-source="[App-V 5.0 SP3 Supported Configurations](app-v-50-sp3-supported-configurations.md)">App-V 5.0 SP3 Supported Configurations</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com//download/details.aspx?id=40773" data-raw-source="[Microsoft .NET Framework 4.5.1 (Web Installer)](https://www.microsoft.com//download/details.aspx?id=40773)"><span data-ttu-id="75e2e-145">Microsoft .NET Framework 4.5.1 （Web 安裝程式）</span><span class="sxs-lookup"><span data-stu-id="75e2e-145">Microsoft .NET Framework 4.5.1 (Web Installer)</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=34595" data-raw-source="[Windows PowerShell 3.0](https://www.microsoft.com/download/details.aspx?id=34595)"><span data-ttu-id="75e2e-146">Windows PowerShell 3。0</span><span class="sxs-lookup"><span data-stu-id="75e2e-146">Windows PowerShell 3.0</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="75e2e-147">安裝 PowerShell 3.0 需要重新開機。</span><span class="sxs-lookup"><span data-stu-id="75e2e-147">Installing PowerShell 3.0 requires a restart.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="75e2e-148">下載並安裝 <a href="https://support.microsoft.com/kb/2533623" data-raw-source="[KB2533623](https://support.microsoft.com/kb/2533623)"> KB2533623</span><span class="sxs-lookup"><span data-stu-id="75e2e-148">Download and install <a href="https://support.microsoft.com/kb/2533623" data-raw-source="[KB2533623](https://support.microsoft.com/kb/2533623)">KB2533623</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="75e2e-149">僅適用于 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="75e2e-149">Applies to Windows 7 only.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)"><span data-ttu-id="75e2e-150">Visual Studio 2013 的 visual c + + 可再發行套件</span><span class="sxs-lookup"><span data-stu-id="75e2e-150">Visual C++ Redistributable Packages for Visual Studio 2013</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="75e2e-151">64位 ASP.NET 註冊</span><span class="sxs-lookup"><span data-stu-id="75e2e-151">64-bit ASP.NET registration</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="75e2e-152">Windows Server Web Server 角色</span><span class="sxs-lookup"><span data-stu-id="75e2e-152">Windows Server Web Server Role</span></span></p></td>
<td align="left"><p><span data-ttu-id="75e2e-153">這個角色必須新增至管理伺服器支援的伺服器作業系統。</span><span class="sxs-lookup"><span data-stu-id="75e2e-153">This role must be added to a server operating system that is supported for the Management server.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="75e2e-154">Web 服務器（IIS）管理工具</span><span class="sxs-lookup"><span data-stu-id="75e2e-154">Web Server (IIS) Management Tools</span></span></p></td>
<td align="left"><p><span data-ttu-id="75e2e-155">按一下 [ <strong> IIS 管理腳本與工具] </strong> 。</span><span class="sxs-lookup"><span data-stu-id="75e2e-155">Click <strong>IIS Management Scripts and Tools</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="75e2e-156">Web 服務器角色服務</span><span class="sxs-lookup"><span data-stu-id="75e2e-156">Web Server Role Services</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="75e2e-157">常見的 HTTP 功能：</span><span class="sxs-lookup"><span data-stu-id="75e2e-157">Common HTTP Features:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="75e2e-158">靜態內容</span><span class="sxs-lookup"><span data-stu-id="75e2e-158">Static Content</span></span></p></li>
<li><p><span data-ttu-id="75e2e-159">預設檔</span><span class="sxs-lookup"><span data-stu-id="75e2e-159">Default Document</span></span></p></li>
</ul>
<p><strong><span data-ttu-id="75e2e-160">應用程式開發：</span><span class="sxs-lookup"><span data-stu-id="75e2e-160">Application Development:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="75e2e-161">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="75e2e-161">ASP.NET</span></span></p></li>
<li><p><span data-ttu-id="75e2e-162">.NET 擴充性</span><span class="sxs-lookup"><span data-stu-id="75e2e-162">.NET Extensibility</span></span></p></li>
<li><p><span data-ttu-id="75e2e-163">ISAPI 延伸</span><span class="sxs-lookup"><span data-stu-id="75e2e-163">ISAPI Extensions</span></span></p></li>
<li><p><span data-ttu-id="75e2e-164">ISAPI 篩選</span><span class="sxs-lookup"><span data-stu-id="75e2e-164">ISAPI Filters</span></span></p></li>
</ul>
<p><strong><span data-ttu-id="75e2e-165">安全性</span><span class="sxs-lookup"><span data-stu-id="75e2e-165">Security:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="75e2e-166">Windows 驗證</span><span class="sxs-lookup"><span data-stu-id="75e2e-166">Windows Authentication</span></span></p></li>
<li><p><span data-ttu-id="75e2e-167">要求篩選</span><span class="sxs-lookup"><span data-stu-id="75e2e-167">Request Filtering</span></span></p></li>
</ul>
<p><strong><span data-ttu-id="75e2e-168">管理工具：</span><span class="sxs-lookup"><span data-stu-id="75e2e-168">Management Tools:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="75e2e-169">IIS 管理主控台</span><span class="sxs-lookup"><span data-stu-id="75e2e-169">IIS Management Console</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="75e2e-170">預設安裝位置</span><span class="sxs-lookup"><span data-stu-id="75e2e-170">Default installation location</span></span></p></td>
<td align="left"><p><span data-ttu-id="75e2e-171">%PROGRAMFILES%\Microsoft 應用程式虛擬化伺服器</span><span class="sxs-lookup"><span data-stu-id="75e2e-171">%PROGRAMFILES%\Microsoft Application Virtualization Server</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="75e2e-172">管理資料庫的位置</span><span class="sxs-lookup"><span data-stu-id="75e2e-172">Location of the Management database</span></span></p></td>
<td align="left"><p><span data-ttu-id="75e2e-173">[SQL Server 資料庫名稱]、[SQL Server 資料庫實例名稱] 和 [資料庫名稱]。</span><span class="sxs-lookup"><span data-stu-id="75e2e-173">SQL Server database name, SQL Server database instance name, and database name.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="75e2e-174">管理主控台與管理資料庫許可權</span><span class="sxs-lookup"><span data-stu-id="75e2e-174">Management console and Management database permissions</span></span></p></td>
<td align="left"><p><span data-ttu-id="75e2e-175">部署完成後可以存取管理主控台和資料庫的使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="75e2e-175">A user or group that can access the Management console and database after the deployment is complete.</span></span> <span data-ttu-id="75e2e-176">除非使用管理主控台新增其他管理員，否則只有這些使用者或群組才能存取管理主控台和資料庫。</span><span class="sxs-lookup"><span data-stu-id="75e2e-176">Only these users or groups will have access to the Management console and database unless additional administrators are added by using the Management console.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="75e2e-177">管理服務網站名稱</span><span class="sxs-lookup"><span data-stu-id="75e2e-177">Management service website name</span></span></p></td>
<td align="left"><p><span data-ttu-id="75e2e-178">管理主控台網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="75e2e-178">Name for the Management console website.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="75e2e-179">管理服務埠系結</span><span class="sxs-lookup"><span data-stu-id="75e2e-179">Management service port binding</span></span></p></td>
<td align="left"><p><span data-ttu-id="75e2e-180">管理服務的唯一端口號碼。</span><span class="sxs-lookup"><span data-stu-id="75e2e-180">Unique port number for the Management service.</span></span> <span data-ttu-id="75e2e-181">此埠無法由電腦上的另一個處理常式使用。</span><span class="sxs-lookup"><span data-stu-id="75e2e-181">This port cannot be used by another process on the computer.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="75e2e-182">Microsoft Silverlight 5</span><span class="sxs-lookup"><span data-stu-id="75e2e-182">Microsoft Silverlight 5</span></span></p></td>
<td align="left"><p><span data-ttu-id="75e2e-183">只有安裝 Silverlight，才能使用管理主控台。</span><span class="sxs-lookup"><span data-stu-id="75e2e-183">The Management console is available only if Silverlight is installed.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="75e2e-184">管理伺服器資料庫必備軟體</span><span class="sxs-lookup"><span data-stu-id="75e2e-184">Management server database prerequisite software</span></span>

<span data-ttu-id="75e2e-185">只有在您使用 App-v 5.0 SP3 管理伺服器時，才需要管理資料庫。</span><span class="sxs-lookup"><span data-stu-id="75e2e-185">The Management database is required only if you are using the App-V 5.0 SP3 Management server.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="75e2e-186">先決條件及必要設定</span><span class="sxs-lookup"><span data-stu-id="75e2e-186">Prerequisites and required settings</span></span></th>
<th align="left"><span data-ttu-id="75e2e-187">詳細資料</span><span class="sxs-lookup"><span data-stu-id="75e2e-187">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="https://www.microsoft.com//download/details.aspx?id=40773" data-raw-source="[Microsoft .NET Framework 4.5.1 (Web Installer)](https://www.microsoft.com//download/details.aspx?id=40773)"><span data-ttu-id="75e2e-188">Microsoft .NET Framework 4.5.1 （Web 安裝程式）</span><span class="sxs-lookup"><span data-stu-id="75e2e-188">Microsoft .NET Framework 4.5.1 (Web Installer)</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)"><span data-ttu-id="75e2e-189">Visual Studio 2013 的 visual c + + 可再發行套件</span><span class="sxs-lookup"><span data-stu-id="75e2e-189">Visual C++ Redistributable Packages for Visual Studio 2013</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="75e2e-190">預設安裝位置</span><span class="sxs-lookup"><span data-stu-id="75e2e-190">Default installation location</span></span></p></td>
<td align="left"><p><span data-ttu-id="75e2e-191">%PROGRAMFILES%\Microsoft 應用程式虛擬化伺服器</span><span class="sxs-lookup"><span data-stu-id="75e2e-191">%PROGRAMFILES%\Microsoft Application Virtualization Server</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="75e2e-192">自訂 SQL Server 實例名稱（如果適用的話）</span><span class="sxs-lookup"><span data-stu-id="75e2e-192">Custom SQL Server instance name (if applicable)</span></span></p></td>
<td align="left"><p><span data-ttu-id="75e2e-193">要使用的格式： <strong> INSTANCENAME</span><span class="sxs-lookup"><span data-stu-id="75e2e-193">Format to use: <strong>INSTANCENAME</span></span></strong></p>
<p><span data-ttu-id="75e2e-194">此格式是根據安裝在本機電腦上的假設所得到的。</span><span class="sxs-lookup"><span data-stu-id="75e2e-194">This format is based on the assumption that the installation is on the local computer.</span></span></p>
<p><span data-ttu-id="75e2e-195">如果您使用 [SVR\INSTANCE] 格式指定 <strong> 名稱 </strong> ，安裝將會失敗。</span><span class="sxs-lookup"><span data-stu-id="75e2e-195">If you specify the name with the format <strong>SVR\INSTANCE</strong>, the installation will fail.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="75e2e-196">自訂資料庫名稱（如果適用的話）</span><span class="sxs-lookup"><span data-stu-id="75e2e-196">Custom database name (if applicable)</span></span></p></td>
<td align="left"><p><span data-ttu-id="75e2e-197">唯一的資料庫名稱。</span><span class="sxs-lookup"><span data-stu-id="75e2e-197">Unique database name.</span></span></p>
<p><span data-ttu-id="75e2e-198">預設值： AppVManagement</span><span class="sxs-lookup"><span data-stu-id="75e2e-198">Default: AppVManagement</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="75e2e-199">管理伺服器位置</span><span class="sxs-lookup"><span data-stu-id="75e2e-199">Management server location</span></span></p></td>
<td align="left"><p><span data-ttu-id="75e2e-200">部署管理伺服器的電腦帳戶。</span><span class="sxs-lookup"><span data-stu-id="75e2e-200">Machine account on which the Management server is deployed.</span></span></p>
<p><span data-ttu-id="75e2e-201">使用格式： Domain\MachineAccount</span><span class="sxs-lookup"><span data-stu-id="75e2e-201">Format to use: Domain\MachineAccount</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="75e2e-202">管理伺服器安裝系統管理員</span><span class="sxs-lookup"><span data-stu-id="75e2e-202">Management server installation administrator</span></span></p></td>
<td align="left"><p><span data-ttu-id="75e2e-203">用於安裝管理伺服器的帳戶。</span><span class="sxs-lookup"><span data-stu-id="75e2e-203">Account used to install the Management server.</span></span></p>
<p><span data-ttu-id="75e2e-204">使用格式： Domain\AdministratorLoginName</span><span class="sxs-lookup"><span data-stu-id="75e2e-204">Format to use: Domain\AdministratorLoginName</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="75e2e-205">Microsoft SQL Server 服務代理程式</span><span class="sxs-lookup"><span data-stu-id="75e2e-205">Microsoft SQL Server Service Agent</span></span></p></td>
<td align="left"><p><span data-ttu-id="75e2e-206">設定管理資料庫電腦，讓 Microsoft SQL Server Agent 服務自動重新開機。</span><span class="sxs-lookup"><span data-stu-id="75e2e-206">Configure the Management database computer so that the Microsoft SQL Server Agent service is restarted automatically.</span></span> <span data-ttu-id="75e2e-207">如需相關指示，請參閱 <a href="https://technet.microsoft.com/magazine/gg313742.aspx" data-raw-source="[Configure SQL Server Agent to Restart Services Automatically](https://technet.microsoft.com/magazine/gg313742.aspx)"> 設定 SQL Server 代理程式來自動重新開機服務 </a> 。</span><span class="sxs-lookup"><span data-stu-id="75e2e-207">For instructions, see <a href="https://technet.microsoft.com/magazine/gg313742.aspx" data-raw-source="[Configure SQL Server Agent to Restart Services Automatically](https://technet.microsoft.com/magazine/gg313742.aspx)">Configure SQL Server Agent to Restart Services Automatically</a>.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="75e2e-208">發佈伺服器必備軟體</span><span class="sxs-lookup"><span data-stu-id="75e2e-208">Publishing server prerequisite software</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="75e2e-209">先決條件及必要設定</span><span class="sxs-lookup"><span data-stu-id="75e2e-209">Prerequisites and required settings</span></span></th>
<th align="left"><span data-ttu-id="75e2e-210">詳細資料</span><span class="sxs-lookup"><span data-stu-id="75e2e-210">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="https://www.microsoft.com//download/details.aspx?id=40773" data-raw-source="[Microsoft .NET Framework 4.5.1 (Web Installer)](https://www.microsoft.com//download/details.aspx?id=40773)"><span data-ttu-id="75e2e-211">Microsoft .NET Framework 4.5.1 （Web 安裝程式）</span><span class="sxs-lookup"><span data-stu-id="75e2e-211">Microsoft .NET Framework 4.5.1 (Web Installer)</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)"><span data-ttu-id="75e2e-212">Visual Studio 2013 的 visual c + + 可再發行套件</span><span class="sxs-lookup"><span data-stu-id="75e2e-212">Visual C++ Redistributable Packages for Visual Studio 2013</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="75e2e-213">64位 ASP.NET 註冊</span><span class="sxs-lookup"><span data-stu-id="75e2e-213">64-bit ASP.NET registration</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="75e2e-214">Windows Server Web Server 角色</span><span class="sxs-lookup"><span data-stu-id="75e2e-214">Windows Server Web Server Role</span></span></p></td>
<td align="left"><p><span data-ttu-id="75e2e-215">這個角色必須新增至管理伺服器支援的伺服器作業系統。</span><span class="sxs-lookup"><span data-stu-id="75e2e-215">This role must be added to a server operating system that is supported for the Management server.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="75e2e-216">Web 服務器（IIS）管理工具</span><span class="sxs-lookup"><span data-stu-id="75e2e-216">Web Server (IIS) Management Tools</span></span></p></td>
<td align="left"><p><span data-ttu-id="75e2e-217">按一下 [ <strong> IIS 管理腳本與工具] </strong> 。</span><span class="sxs-lookup"><span data-stu-id="75e2e-217">Click <strong>IIS Management Scripts and Tools</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="75e2e-218">Web 服務器角色服務</span><span class="sxs-lookup"><span data-stu-id="75e2e-218">Web Server Role Services</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="75e2e-219">常見的 HTTP 功能：</span><span class="sxs-lookup"><span data-stu-id="75e2e-219">Common HTTP Features:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="75e2e-220">靜態內容</span><span class="sxs-lookup"><span data-stu-id="75e2e-220">Static Content</span></span></p></li>
<li><p><span data-ttu-id="75e2e-221">預設檔</span><span class="sxs-lookup"><span data-stu-id="75e2e-221">Default Document</span></span></p></li>
</ul>
<p><strong><span data-ttu-id="75e2e-222">應用程式開發：</span><span class="sxs-lookup"><span data-stu-id="75e2e-222">Application Development:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="75e2e-223">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="75e2e-223">ASP.NET</span></span></p></li>
<li><p><span data-ttu-id="75e2e-224">.NET 擴充性</span><span class="sxs-lookup"><span data-stu-id="75e2e-224">.NET Extensibility</span></span></p></li>
<li><p><span data-ttu-id="75e2e-225">ISAPI 延伸</span><span class="sxs-lookup"><span data-stu-id="75e2e-225">ISAPI Extensions</span></span></p></li>
<li><p><span data-ttu-id="75e2e-226">ISAPI 篩選</span><span class="sxs-lookup"><span data-stu-id="75e2e-226">ISAPI Filters</span></span></p></li>
</ul>
<p><strong><span data-ttu-id="75e2e-227">安全性</span><span class="sxs-lookup"><span data-stu-id="75e2e-227">Security:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="75e2e-228">Windows 驗證</span><span class="sxs-lookup"><span data-stu-id="75e2e-228">Windows Authentication</span></span></p></li>
<li><p><span data-ttu-id="75e2e-229">要求篩選</span><span class="sxs-lookup"><span data-stu-id="75e2e-229">Request Filtering</span></span></p></li>
</ul>
<p><strong><span data-ttu-id="75e2e-230">管理工具：</span><span class="sxs-lookup"><span data-stu-id="75e2e-230">Management Tools:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="75e2e-231">IIS 管理主控台</span><span class="sxs-lookup"><span data-stu-id="75e2e-231">IIS Management Console</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="75e2e-232">預設安裝位置</span><span class="sxs-lookup"><span data-stu-id="75e2e-232">Default installation location</span></span></p></td>
<td align="left"><p><span data-ttu-id="75e2e-233">%PROGRAMFILES%\Microsoft 應用程式虛擬化伺服器</span><span class="sxs-lookup"><span data-stu-id="75e2e-233">%PROGRAMFILES%\Microsoft Application Virtualization Server</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="75e2e-234">管理服務 URL</span><span class="sxs-lookup"><span data-stu-id="75e2e-234">Management service URL</span></span></p></td>
<td align="left"><p><span data-ttu-id="75e2e-235">App-v 管理服務的 URL。</span><span class="sxs-lookup"><span data-stu-id="75e2e-235">URL of the App-V Management service.</span></span> <span data-ttu-id="75e2e-236">這是發佈伺服器要與之通訊的埠。</span><span class="sxs-lookup"><span data-stu-id="75e2e-236">This is the port with which the Publishing server communicates.</span></span></p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="75e2e-237">安裝架構</span><span class="sxs-lookup"><span data-stu-id="75e2e-237">Installation architecture</span></span></th>
<th align="left"><span data-ttu-id="75e2e-238">URL 要使用的格式</span><span class="sxs-lookup"><span data-stu-id="75e2e-238">Format to use for the URL</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="75e2e-239">管理伺服器和發佈伺服器都安裝在相同的伺服器上</span><span class="sxs-lookup"><span data-stu-id="75e2e-239">Management server and Publishing server are installed on the same server</span></span></p></td>
<td align="left"><p><a href="http://localhost:12345" data-raw-source="http://localhost:12345">http://localhost:12345</a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="75e2e-240">管理伺服器和發佈伺服器都安裝在不同的伺服器上</span><span class="sxs-lookup"><span data-stu-id="75e2e-240">Management server and Publishing server are installed on different servers</span></span></p></td>
<td align="left"><p><a href="http://MyAppvServer.MyDomain.com" data-raw-source="http://MyAppvServer.MyDomain.com">http://MyAppvServer.MyDomain.com</a></p></td>
</tr>
</tbody>
</table>
<p> </p>
<p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="75e2e-241">發佈服務網站名稱</span><span class="sxs-lookup"><span data-stu-id="75e2e-241">Publishing service website name</span></span></p></td>
<td align="left"><p><span data-ttu-id="75e2e-242">發佈網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="75e2e-242">Name for the Publishing website.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="75e2e-243">發佈服務埠系結</span><span class="sxs-lookup"><span data-stu-id="75e2e-243">Publishing service port binding</span></span></p></td>
<td align="left"><p><span data-ttu-id="75e2e-244">發佈服務的唯一端口號碼。</span><span class="sxs-lookup"><span data-stu-id="75e2e-244">Unique port number for the Publishing service.</span></span> <span data-ttu-id="75e2e-245">此埠無法由電腦上的另一個處理常式使用。</span><span class="sxs-lookup"><span data-stu-id="75e2e-245">This port cannot be used by another process on the computer.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="75e2e-246">報表伺服器必備軟體</span><span class="sxs-lookup"><span data-stu-id="75e2e-246">Reporting server prerequisite software</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="75e2e-247">先決條件及必要設定</span><span class="sxs-lookup"><span data-stu-id="75e2e-247">Prerequisites and required settings</span></span></th>
<th align="left"><span data-ttu-id="75e2e-248">詳細資料</span><span class="sxs-lookup"><span data-stu-id="75e2e-248">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="75e2e-249">支援的 SQL Server 版本</span><span class="sxs-lookup"><span data-stu-id="75e2e-249">Supported version of SQL Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="75e2e-250">如需支援的版本，請參閱 <a href="app-v-50-sp3-supported-configurations.md" data-raw-source="[App-V 5.0 SP3 Supported Configurations](app-v-50-sp3-supported-configurations.md)"> App-V 5.0 SP3 支援 </a> 的配置。</span><span class="sxs-lookup"><span data-stu-id="75e2e-250">For supported versions, see <a href="app-v-50-sp3-supported-configurations.md" data-raw-source="[App-V 5.0 SP3 Supported Configurations](app-v-50-sp3-supported-configurations.md)">App-V 5.0 SP3 Supported Configurations</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com//download/details.aspx?id=40773" data-raw-source="[Microsoft .NET Framework 4.5.1 (Web Installer)](https://www.microsoft.com//download/details.aspx?id=40773)"><span data-ttu-id="75e2e-251">Microsoft .NET Framework 4.5.1 （Web 安裝程式）</span><span class="sxs-lookup"><span data-stu-id="75e2e-251">Microsoft .NET Framework 4.5.1 (Web Installer)</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)"><span data-ttu-id="75e2e-252">Visual Studio 2013 的 visual c + + 可再發行套件</span><span class="sxs-lookup"><span data-stu-id="75e2e-252">Visual C++ Redistributable Packages for Visual Studio 2013</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="75e2e-253">64位 ASP.NET 註冊</span><span class="sxs-lookup"><span data-stu-id="75e2e-253">64-bit ASP.NET registration</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="75e2e-254">Windows Server Web Server 角色</span><span class="sxs-lookup"><span data-stu-id="75e2e-254">Windows Server Web Server Role</span></span></p></td>
<td align="left"><p><span data-ttu-id="75e2e-255">這個角色必須新增至管理伺服器支援的伺服器作業系統。</span><span class="sxs-lookup"><span data-stu-id="75e2e-255">This role must be added to a server operating system that is supported for the Management server.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="75e2e-256">Web 服務器（IIS）管理工具</span><span class="sxs-lookup"><span data-stu-id="75e2e-256">Web Server (IIS) Management Tools</span></span></p></td>
<td align="left"><p><span data-ttu-id="75e2e-257">按一下 [ <strong> IIS 管理腳本與工具] </strong> 。</span><span class="sxs-lookup"><span data-stu-id="75e2e-257">Click <strong>IIS Management Scripts and Tools</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="75e2e-258">Web 服務器角色服務</span><span class="sxs-lookup"><span data-stu-id="75e2e-258">Web Server Role Services</span></span></p></td>
<td align="left"><p><span data-ttu-id="75e2e-259">若要降低將有害或惡意資料傳送至報表伺服器的風險，您應該限制每個公司安全性原則存取報表 Web 服務。</span><span class="sxs-lookup"><span data-stu-id="75e2e-259">To reduce the risk of unwanted or malicious data being sent to the Reporting server, you should restrict access to the Reporting Web Service per your corporate security policy.</span></span></p>
<p><strong><span data-ttu-id="75e2e-260">常見的 HTTP 功能：</span><span class="sxs-lookup"><span data-stu-id="75e2e-260">Common HTTP Features:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="75e2e-261">靜態內容</span><span class="sxs-lookup"><span data-stu-id="75e2e-261">Static Content</span></span></p></li>
<li><p><span data-ttu-id="75e2e-262">預設檔</span><span class="sxs-lookup"><span data-stu-id="75e2e-262">Default Document</span></span></p></li>
</ul>
<p><strong><span data-ttu-id="75e2e-263">應用程式開發：</span><span class="sxs-lookup"><span data-stu-id="75e2e-263">Application Development:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="75e2e-264">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="75e2e-264">ASP.NET</span></span></p></li>
<li><p><span data-ttu-id="75e2e-265">.NET 擴充性</span><span class="sxs-lookup"><span data-stu-id="75e2e-265">.NET Extensibility</span></span></p></li>
<li><p><span data-ttu-id="75e2e-266">ISAPI 延伸</span><span class="sxs-lookup"><span data-stu-id="75e2e-266">ISAPI Extensions</span></span></p></li>
<li><p><span data-ttu-id="75e2e-267">ISAPI 篩選</span><span class="sxs-lookup"><span data-stu-id="75e2e-267">ISAPI Filters</span></span></p></li>
</ul>
<p><strong><span data-ttu-id="75e2e-268">安全性</span><span class="sxs-lookup"><span data-stu-id="75e2e-268">Security:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="75e2e-269">Windows 驗證</span><span class="sxs-lookup"><span data-stu-id="75e2e-269">Windows Authentication</span></span></p></li>
<li><p><span data-ttu-id="75e2e-270">要求篩選</span><span class="sxs-lookup"><span data-stu-id="75e2e-270">Request Filtering</span></span></p></li>
</ul>
<p><strong><span data-ttu-id="75e2e-271">管理工具：</span><span class="sxs-lookup"><span data-stu-id="75e2e-271">Management Tools:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="75e2e-272">IIS 管理主控台</span><span class="sxs-lookup"><span data-stu-id="75e2e-272">IIS Management Console</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="75e2e-273">預設安裝位置</span><span class="sxs-lookup"><span data-stu-id="75e2e-273">Default installation location</span></span></p></td>
<td align="left"><p><span data-ttu-id="75e2e-274">%PROGRAMFILES%\Microsoft 應用程式虛擬化伺服器</span><span class="sxs-lookup"><span data-stu-id="75e2e-274">%PROGRAMFILES%\Microsoft Application Virtualization Server</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="75e2e-275">Reporting services 網站名稱</span><span class="sxs-lookup"><span data-stu-id="75e2e-275">Reporting service website name</span></span></p></td>
<td align="left"><p><span data-ttu-id="75e2e-276">報告網站的名稱。</span><span class="sxs-lookup"><span data-stu-id="75e2e-276">Name for the Reporting website.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="75e2e-277">報表服務埠系結</span><span class="sxs-lookup"><span data-stu-id="75e2e-277">Reporting service port binding</span></span></p></td>
<td align="left"><p><span data-ttu-id="75e2e-278">報表服務的唯一端口號碼。</span><span class="sxs-lookup"><span data-stu-id="75e2e-278">Unique port number for the Reporting service.</span></span> <span data-ttu-id="75e2e-279">此埠無法由電腦上的另一個處理常式使用。</span><span class="sxs-lookup"><span data-stu-id="75e2e-279">This port cannot be used by another process on the computer.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="75e2e-280">報表資料庫必備軟體</span><span class="sxs-lookup"><span data-stu-id="75e2e-280">Reporting database prerequisite software</span></span>

<span data-ttu-id="75e2e-281">只有在您使用 App-v 5.0 SP3 報表服務器時，才需要報告資料庫。</span><span class="sxs-lookup"><span data-stu-id="75e2e-281">The Reporting database is required only if you are using the App-V 5.0 SP3 Reporting server.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="75e2e-282">先決條件及必要設定</span><span class="sxs-lookup"><span data-stu-id="75e2e-282">Prerequisites and required settings</span></span></th>
<th align="left"><span data-ttu-id="75e2e-283">詳細資料</span><span class="sxs-lookup"><span data-stu-id="75e2e-283">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="https://www.microsoft.com//download/details.aspx?id=40773" data-raw-source="[Microsoft .NET Framework 4.5.1 (Web Installer)](https://www.microsoft.com//download/details.aspx?id=40773)"><span data-ttu-id="75e2e-284">Microsoft .NET Framework 4.5.1 （Web 安裝程式）</span><span class="sxs-lookup"><span data-stu-id="75e2e-284">Microsoft .NET Framework 4.5.1 (Web Installer)</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)"><span data-ttu-id="75e2e-285">Visual Studio 2013 的 visual c + + 可再發行套件</span><span class="sxs-lookup"><span data-stu-id="75e2e-285">Visual C++ Redistributable Packages for Visual Studio 2013</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="75e2e-286">預設安裝位置</span><span class="sxs-lookup"><span data-stu-id="75e2e-286">Default installation location</span></span></p></td>
<td align="left"><p><span data-ttu-id="75e2e-287">%PROGRAMFILES%\Microsoft 應用程式虛擬化伺服器</span><span class="sxs-lookup"><span data-stu-id="75e2e-287">%PROGRAMFILES%\Microsoft Application Virtualization Server</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="75e2e-288">自訂 SQL Server 實例名稱（如果適用的話）</span><span class="sxs-lookup"><span data-stu-id="75e2e-288">Custom SQL Server instance name (if applicable)</span></span></p></td>
<td align="left"><p><span data-ttu-id="75e2e-289">要使用的格式： <strong> INSTANCENAME</span><span class="sxs-lookup"><span data-stu-id="75e2e-289">Format to use: <strong>INSTANCENAME</span></span></strong></p>
<p><span data-ttu-id="75e2e-290">此格式是根據安裝在本機電腦上的假設所得到的。</span><span class="sxs-lookup"><span data-stu-id="75e2e-290">This format is based on the assumption that the installation is on the local computer.</span></span></p>
<p><span data-ttu-id="75e2e-291">如果您使用 [SVR\INSTANCE] 格式指定 <strong> 名稱 </strong> ，安裝將會失敗。</span><span class="sxs-lookup"><span data-stu-id="75e2e-291">If you specify the name with the format <strong>SVR\INSTANCE</strong>, the installation will fail.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="75e2e-292">自訂資料庫名稱（如果適用的話）</span><span class="sxs-lookup"><span data-stu-id="75e2e-292">Custom database name (if applicable)</span></span></p></td>
<td align="left"><p><span data-ttu-id="75e2e-293">唯一的資料庫名稱。</span><span class="sxs-lookup"><span data-stu-id="75e2e-293">Unique database name.</span></span></p>
<p><span data-ttu-id="75e2e-294">預設值： AppVReporting</span><span class="sxs-lookup"><span data-stu-id="75e2e-294">Default: AppVReporting</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="75e2e-295">報表伺服器位置</span><span class="sxs-lookup"><span data-stu-id="75e2e-295">Reporting server location</span></span></p></td>
<td align="left"><p><span data-ttu-id="75e2e-296">部署報表伺服器的電腦帳戶。</span><span class="sxs-lookup"><span data-stu-id="75e2e-296">Machine account on which the Reporting server is deployed.</span></span></p>
<p><span data-ttu-id="75e2e-297">使用格式： Domain\MachineAccount</span><span class="sxs-lookup"><span data-stu-id="75e2e-297">Format to use: Domain\MachineAccount</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="75e2e-298">報表伺服器安裝系統管理員</span><span class="sxs-lookup"><span data-stu-id="75e2e-298">Reporting server installation administrator</span></span></p></td>
<td align="left"><p><span data-ttu-id="75e2e-299">用於安裝報表伺服器的帳戶。</span><span class="sxs-lookup"><span data-stu-id="75e2e-299">Account used to install the Reporting server.</span></span></p>
<p><span data-ttu-id="75e2e-300">使用格式： Domain\AdministratorLoginName</span><span class="sxs-lookup"><span data-stu-id="75e2e-300">Format to use: Domain\AdministratorLoginName</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="75e2e-301">Microsoft SQL Server 服務與 Microsoft SQL Server Service 代理</span><span class="sxs-lookup"><span data-stu-id="75e2e-301">Microsoft SQL Server Service and Microsoft SQL Server Service Agent</span></span></p></td>
<td align="left"><p><span data-ttu-id="75e2e-302">將這些服務設定為與具有查詢 AD DS 存取權的使用者帳戶相關聯。</span><span class="sxs-lookup"><span data-stu-id="75e2e-302">Configure these services to be associated with user accounts that have access to query AD DS.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="75e2e-303">App-V 用戶端必備軟體</span><span class="sxs-lookup"><span data-stu-id="75e2e-303">App-V client prerequisite software</span></span>


<span data-ttu-id="75e2e-304">針對 App-V 用戶端安裝下列必備軟體。</span><span class="sxs-lookup"><span data-stu-id="75e2e-304">Install the following prerequisite software for the App-V client.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="75e2e-305">必備</span><span class="sxs-lookup"><span data-stu-id="75e2e-305">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="75e2e-306">詳細資料</span><span class="sxs-lookup"><span data-stu-id="75e2e-306">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="https://www.microsoft.com//download/details.aspx?id=40773" data-raw-source="[Microsoft .NET Framework 4.5.1 (Web Installer)](https://www.microsoft.com//download/details.aspx?id=40773)"><span data-ttu-id="75e2e-307">Microsoft .NET Framework 4.5.1 （Web 安裝程式）</span><span class="sxs-lookup"><span data-stu-id="75e2e-307">Microsoft .NET Framework 4.5.1 (Web Installer)</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=34595" data-raw-source="[Windows PowerShell 3.0](https://www.microsoft.com/download/details.aspx?id=34595)"><span data-ttu-id="75e2e-308">Windows PowerShell 3。0</span><span class="sxs-lookup"><span data-stu-id="75e2e-308">Windows PowerShell 3.0</span></span></a></p>
<p></p></td>
<td align="left"><p><span data-ttu-id="75e2e-309">安裝 PowerShell 3.0 需要重新開機。</span><span class="sxs-lookup"><span data-stu-id="75e2e-309">Installing PowerShell 3.0 requires a restart.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="https://support.microsoft.com/kb/2533623" data-raw-source="[KB2533623](https://support.microsoft.com/kb/2533623)"><span data-ttu-id="75e2e-310">KB2533623</span><span class="sxs-lookup"><span data-stu-id="75e2e-310">KB2533623</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="75e2e-311">僅適用于 Windows 7：下載並安裝 KB。</span><span class="sxs-lookup"><span data-stu-id="75e2e-311">Applies to Windows 7 only: Download and install the KB.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)"><span data-ttu-id="75e2e-312">Visual Studio 2013 的 visual c + + 可再發行套件</span><span class="sxs-lookup"><span data-stu-id="75e2e-312">Visual C++ Redistributable Packages for Visual Studio 2013</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="75e2e-313">遠端桌面服務用戶端必備軟體</span><span class="sxs-lookup"><span data-stu-id="75e2e-313">Remote Desktop Services client prerequisite software</span></span>


<span data-ttu-id="75e2e-314">安裝 App-v 遠端桌面服務用戶端的下列必備軟體。</span><span class="sxs-lookup"><span data-stu-id="75e2e-314">Install the following prerequisite software for the App-V Remote Desktop Services client.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="75e2e-315">必備</span><span class="sxs-lookup"><span data-stu-id="75e2e-315">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="75e2e-316">詳細資料</span><span class="sxs-lookup"><span data-stu-id="75e2e-316">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="https://www.microsoft.com//download/details.aspx?id=40773" data-raw-source="[Microsoft .NET Framework 4.5.1 (Web Installer)](https://www.microsoft.com//download/details.aspx?id=40773)"><span data-ttu-id="75e2e-317">Microsoft .NET Framework 4.5.1 （Web 安裝程式）</span><span class="sxs-lookup"><span data-stu-id="75e2e-317">Microsoft .NET Framework 4.5.1 (Web Installer)</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=34595" data-raw-source="[Windows PowerShell 3.0](https://www.microsoft.com/download/details.aspx?id=34595)"><span data-ttu-id="75e2e-318">Windows PowerShell 3。0</span><span class="sxs-lookup"><span data-stu-id="75e2e-318">Windows PowerShell 3.0</span></span></a></p>
<p></p></td>
<td align="left"><p><span data-ttu-id="75e2e-319">安裝 PowerShell 3.0 需要重新開機。</span><span class="sxs-lookup"><span data-stu-id="75e2e-319">Installing PowerShell 3.0 requires a restart.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="https://support.microsoft.com/kb/2533623" data-raw-source="[KB2533623](https://support.microsoft.com/kb/2533623)"><span data-ttu-id="75e2e-320">KB2533623</span><span class="sxs-lookup"><span data-stu-id="75e2e-320">KB2533623</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="75e2e-321">僅適用于 Windows 7：下載並安裝 KB。</span><span class="sxs-lookup"><span data-stu-id="75e2e-321">Applies to Windows 7 only: Download and install the KB.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)"><span data-ttu-id="75e2e-322">Visual Studio 2013 的 visual c + + 可再發行套件</span><span class="sxs-lookup"><span data-stu-id="75e2e-322">Visual C++ Redistributable Packages for Visual Studio 2013</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="75e2e-323">Sequencer 必備軟體</span><span class="sxs-lookup"><span data-stu-id="75e2e-323">Sequencer prerequisite software</span></span>


**<span data-ttu-id="75e2e-324">安裝先決條件前的須知事項：</span><span class="sxs-lookup"><span data-stu-id="75e2e-324">What to know before installing the prerequisites:</span></span>**

-   <span data-ttu-id="75e2e-325">最佳做法：執行排序器的電腦應該擁有與將執行虛擬應用程式的電腦相同的硬體和軟體配置。</span><span class="sxs-lookup"><span data-stu-id="75e2e-325">Best practice: The computer that runs the Sequencer should have the same hardware and software configurations as the computers that will run the virtual applications.</span></span>

-   <span data-ttu-id="75e2e-326">排序程式需要大量的資源，因此請確定執行排序器的電腦有大量的記憶體、快速的處理器，以及快速硬碟。</span><span class="sxs-lookup"><span data-stu-id="75e2e-326">The sequencing process is resource intensive, so make sure that the computer that runs the Sequencer has plenty of memory, a fast processor, and a fast hard drive.</span></span> <span data-ttu-id="75e2e-327">本機安裝的應用程式的系統需求不能超過排序器的要求。</span><span class="sxs-lookup"><span data-stu-id="75e2e-327">The system requirements of locally installed applications cannot exceed those of the Sequencer.</span></span> <span data-ttu-id="75e2e-328">如需詳細資訊，請參閱[App-V 5.0 支援的](app-v-50-supported-configurations.md)設定。</span><span class="sxs-lookup"><span data-stu-id="75e2e-328">For more information, see [App-V 5.0 Supported Configurations](app-v-50-supported-configurations.md).</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="75e2e-329">必備</span><span class="sxs-lookup"><span data-stu-id="75e2e-329">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="75e2e-330">詳細資料</span><span class="sxs-lookup"><span data-stu-id="75e2e-330">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="https://www.microsoft.com//download/details.aspx?id=40773" data-raw-source="[Microsoft .NET Framework 4.5.1 (Web Installer)](https://www.microsoft.com//download/details.aspx?id=40773)"><span data-ttu-id="75e2e-331">Microsoft .NET Framework 4.5.1 （Web 安裝程式）</span><span class="sxs-lookup"><span data-stu-id="75e2e-331">Microsoft .NET Framework 4.5.1 (Web Installer)</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=34595" data-raw-source="[Windows PowerShell 3.0](https://www.microsoft.com/download/details.aspx?id=34595)"><span data-ttu-id="75e2e-332">Windows PowerShell 3。0</span><span class="sxs-lookup"><span data-stu-id="75e2e-332">Windows PowerShell 3.0</span></span></a></p>
<p></p></td>
<td align="left"><p><span data-ttu-id="75e2e-333">安裝 PowerShell 3.0 需要重新開機。</span><span class="sxs-lookup"><span data-stu-id="75e2e-333">Installing PowerShell 3.0 requires a restart.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="https://support.microsoft.com/kb/2533623" data-raw-source="[KB2533623](https://support.microsoft.com/kb/2533623)"><span data-ttu-id="75e2e-334">KB2533623</span><span class="sxs-lookup"><span data-stu-id="75e2e-334">KB2533623</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="75e2e-335">僅適用于 Windows 7：下載並安裝 KB。</span><span class="sxs-lookup"><span data-stu-id="75e2e-335">Applies to Windows 7 only: Download and install the KB.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="https://www.microsoft.com/download/details.aspx?id=40784" data-raw-source="[Visual C++ Redistributable Packages for Visual Studio 2013](https://www.microsoft.com/download/details.aspx?id=40784)"><span data-ttu-id="75e2e-336">Visual Studio 2013 的 visual c + + 可再發行套件</span><span class="sxs-lookup"><span data-stu-id="75e2e-336">Visual C++ Redistributable Packages for Visual Studio 2013</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>








## <span data-ttu-id="75e2e-337">相關主題</span><span class="sxs-lookup"><span data-stu-id="75e2e-337">Related topics</span></span>


[<span data-ttu-id="75e2e-338">為 App-V 5.0 進行規劃</span><span class="sxs-lookup"><span data-stu-id="75e2e-338">Planning for App-V 5.0</span></span>](planning-for-app-v-50-rc.md)

[<span data-ttu-id="75e2e-339">App-V 5.0 SP3 支援的組態</span><span class="sxs-lookup"><span data-stu-id="75e2e-339">App-V 5.0 SP3 Supported Configurations</span></span>](app-v-50-sp3-supported-configurations.md)









