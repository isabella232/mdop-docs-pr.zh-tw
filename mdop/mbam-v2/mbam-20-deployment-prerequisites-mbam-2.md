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
# <span data-ttu-id="80e3f-103">MBAM 2.0 部署必要條件</span><span class="sxs-lookup"><span data-stu-id="80e3f-103">MBAM 2.0 Deployment Prerequisites</span></span>


<span data-ttu-id="80e3f-104">在您開始進行 Microsoft BitLocker 管理與監控（MBAM）安裝之前，您應該確定您已滿足安裝產品的先決條件。</span><span class="sxs-lookup"><span data-stu-id="80e3f-104">Before you start Microsoft BitLocker Administration and Monitoring (MBAM) Setup, you should ensure that you have met the prerequisites to install the product.</span></span> <span data-ttu-id="80e3f-105">本節包含的資訊可協助您在部署 Microsoft BitLocker 管理與監視伺服器功能與用戶端之前，先成功規劃您的計算環境。</span><span class="sxs-lookup"><span data-stu-id="80e3f-105">This section contains information to help you successfully plan your computing environment before you deploy Microsoft BitLocker Administration and Monitoring Server features and Clients.</span></span> <span data-ttu-id="80e3f-106">如果您是使用 Configuration Manager 安裝 MBAM，請參閱[規劃使用 Configuration Manager 部署 MBAM](planning-to-deploy-mbam-with-configuration-manager-2.md)以取得其他先決條件。</span><span class="sxs-lookup"><span data-stu-id="80e3f-106">If you are installing MBAM with Configuration Manager, see [Planning to Deploy MBAM with Configuration Manager](planning-to-deploy-mbam-with-configuration-manager-2.md) for additional prerequisites.</span></span>

## <span data-ttu-id="80e3f-107">MBAM Server 功能的安裝先決條件</span><span class="sxs-lookup"><span data-stu-id="80e3f-107">Installation Prerequisites for MBAM Server Features</span></span>


<span data-ttu-id="80e3f-108">每個 MBAM 伺服器功能都有特定的先決條件，您必須先滿足這些先決條件，才能成功安裝 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="80e3f-108">Each of the MBAM Server features has specific prerequisites that must be met before the MBAM features can be successfully installed.</span></span> <span data-ttu-id="80e3f-109">MBAM 安裝程式會檢查在安裝開始前是否已滿足所有先決條件。</span><span class="sxs-lookup"><span data-stu-id="80e3f-109">MBAM Setup checks that all prerequisites are met before the installation starts.</span></span>

### <span data-ttu-id="80e3f-110">管理和監視伺服器的先決條件</span><span class="sxs-lookup"><span data-stu-id="80e3f-110">Prerequisites for Administration and Monitoring Server</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="80e3f-111">必備</span><span class="sxs-lookup"><span data-stu-id="80e3f-111">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="80e3f-112">詳細資料</span><span class="sxs-lookup"><span data-stu-id="80e3f-112">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="80e3f-113">Windows Server Web Server 角色</span><span class="sxs-lookup"><span data-stu-id="80e3f-113">Windows Server Web Server Role</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="80e3f-114">這個角色必須新增至 [管理與監視伺服器] 功能支援的伺服器作業系統。</span><span class="sxs-lookup"><span data-stu-id="80e3f-114">This role must be added to a server operating system that is supported for the Administration and Monitoring Server feature.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="80e3f-115">Web 服務器（IIS）管理工具</span><span class="sxs-lookup"><span data-stu-id="80e3f-115">Web Server (IIS) Management Tools</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="80e3f-116">選取 [ <strong> IIS 管理腳本與工具] </strong> 。</span><span class="sxs-lookup"><span data-stu-id="80e3f-116">Select <strong>IIS Management Scripts and Tools</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="80e3f-117">SSL 憑證</span><span class="sxs-lookup"><span data-stu-id="80e3f-117">SSL Certificate</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="80e3f-118">選用。</span><span class="sxs-lookup"><span data-stu-id="80e3f-118">Optional.</span></span> <span data-ttu-id="80e3f-119">若要保護用戶端與 web 服務之間的通訊，您必須取得並安裝受信任的安全機構已簽署的憑證。</span><span class="sxs-lookup"><span data-stu-id="80e3f-119">To secure communication between the clients and the web services, you have to obtain and install a certificate that a trusted security authority signed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="80e3f-120">Web 服務器角色服務</span><span class="sxs-lookup"><span data-stu-id="80e3f-120">Web Server Role Services</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="80e3f-121">常見的 HTTP 功能：</span><span class="sxs-lookup"><span data-stu-id="80e3f-121">Common HTTP Features:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="80e3f-122">靜態內容</span><span class="sxs-lookup"><span data-stu-id="80e3f-122">Static Content</span></span></p></li>
<li><p><span data-ttu-id="80e3f-123">預設檔</span><span class="sxs-lookup"><span data-stu-id="80e3f-123">Default Document</span></span></p></li>
</ul>
<p><strong><span data-ttu-id="80e3f-124">應用程式開發：</span><span class="sxs-lookup"><span data-stu-id="80e3f-124">Application Development:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="80e3f-125">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="80e3f-125">ASP.NET</span></span></p></li>
<li><p><span data-ttu-id="80e3f-126">.NET 擴充性</span><span class="sxs-lookup"><span data-stu-id="80e3f-126">.NET Extensibility</span></span></p></li>
<li><p><span data-ttu-id="80e3f-127">ISAPI 延伸</span><span class="sxs-lookup"><span data-stu-id="80e3f-127">ISAPI Extensions</span></span></p></li>
<li><p><span data-ttu-id="80e3f-128">ISAPI 篩選</span><span class="sxs-lookup"><span data-stu-id="80e3f-128">ISAPI Filters</span></span></p></li>
</ul>
<p><strong><span data-ttu-id="80e3f-129">安全性</span><span class="sxs-lookup"><span data-stu-id="80e3f-129">Security:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="80e3f-130">Windows 驗證</span><span class="sxs-lookup"><span data-stu-id="80e3f-130">Windows Authentication</span></span></p></li>
<li><p><span data-ttu-id="80e3f-131">要求篩選</span><span class="sxs-lookup"><span data-stu-id="80e3f-131">Request Filtering</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="80e3f-132">Windows Server 功能</span><span class="sxs-lookup"><span data-stu-id="80e3f-132">Windows Server Features</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="80e3f-133">.NET Framework 3.5.1 功能：</span><span class="sxs-lookup"><span data-stu-id="80e3f-133">.NET Framework 3.5.1 features:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="80e3f-134">.NET Framework 3.5。1</span><span class="sxs-lookup"><span data-stu-id="80e3f-134">.NET Framework 3.5.1</span></span></p></li>
<li><p><span data-ttu-id="80e3f-135">WCF 啟用</span><span class="sxs-lookup"><span data-stu-id="80e3f-135">WCF Activation</span></span></p>
<ul>
<li><p><span data-ttu-id="80e3f-136">HTTP 啟用</span><span class="sxs-lookup"><span data-stu-id="80e3f-136">HTTP Activation</span></span></p></li>
<li><p><span data-ttu-id="80e3f-137">非 HTTP 啟用</span><span class="sxs-lookup"><span data-stu-id="80e3f-137">Non-HTTP Activation</span></span></p></li>
</ul></li>
</ul>
<p><strong><span data-ttu-id="80e3f-138">Windows Process Activation Service：</span><span class="sxs-lookup"><span data-stu-id="80e3f-138">Windows Process Activation Service:</span></span></strong></p>
<ul>
<li><p><span data-ttu-id="80e3f-139">處理模型</span><span class="sxs-lookup"><span data-stu-id="80e3f-139">Process Model</span></span></p></li>
<li><p><span data-ttu-id="80e3f-140">.NET 環境</span><span class="sxs-lookup"><span data-stu-id="80e3f-140">.NET Environment</span></span></p></li>
<li><p><span data-ttu-id="80e3f-141">配置 Api</span><span class="sxs-lookup"><span data-stu-id="80e3f-141">Configuration APIs</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="80e3f-142">注意</span><span class="sxs-lookup"><span data-stu-id="80e3f-142">Note</span></span>**  
<span data-ttu-id="80e3f-143">如需支援的作業系統清單，請參閱[MBAM 2.0 支援](mbam-20-supported-configurations-mbam-2.md)的設定。</span><span class="sxs-lookup"><span data-stu-id="80e3f-143">For a list of supported operating systems, see [MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md).</span></span>



### <span data-ttu-id="80e3f-144">合規性和審核報告的先決條件</span><span class="sxs-lookup"><span data-stu-id="80e3f-144">Prerequisites for the Compliance and Audit Reports</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="80e3f-145">必備</span><span class="sxs-lookup"><span data-stu-id="80e3f-145">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="80e3f-146">詳細資料</span><span class="sxs-lookup"><span data-stu-id="80e3f-146">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="80e3f-147">支援的 SQL Server 版本</span><span class="sxs-lookup"><span data-stu-id="80e3f-147">Supported version of SQL Server</span></span></p>
<p><span data-ttu-id="80e3f-148"><a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)">如需支援的版本，請參閱 MBAM 2.0 支援 </a> 的配置。</span><span class="sxs-lookup"><span data-stu-id="80e3f-148">See <a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)">MBAM 2.0 Supported Configurations</a> for supported versions.</span></span></p></td>
<td align="left"><p><span data-ttu-id="80e3f-149">安裝 SQL Server 的方式如下：</span><span class="sxs-lookup"><span data-stu-id="80e3f-149">Install SQL Server with:</span></span></p>
<ul>
<li><p><span data-ttu-id="80e3f-150">SQL_Latin1_General_CP1_CI_AS 排序</span><span class="sxs-lookup"><span data-stu-id="80e3f-150">SQL_Latin1_General_CP1_CI_AS collation</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="80e3f-151">SQL Server Reporting Services （SSRS）</span><span class="sxs-lookup"><span data-stu-id="80e3f-151">SQL Server Reporting Services (SSRS)</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="80e3f-152">SSRS 實例權利–只有當您在不同的伺服器上安裝資料庫時，才能安裝報表。</span><span class="sxs-lookup"><span data-stu-id="80e3f-152">SSRS instance rights – required for installing reports only if you are installing databases on a separate server from the reports.</span></span></p></td>
<td align="left"><p><span data-ttu-id="80e3f-153">所需的實例許可權：</span><span class="sxs-lookup"><span data-stu-id="80e3f-153">Required instance rights:</span></span></p>
<ul>
<li><p><span data-ttu-id="80e3f-154">建立資料夾</span><span class="sxs-lookup"><span data-stu-id="80e3f-154">Create Folders</span></span></p></li>
<li><p><span data-ttu-id="80e3f-155">發佈報表</span><span class="sxs-lookup"><span data-stu-id="80e3f-155">Publish Reports</span></span></p></li>
</ul>
<p><span data-ttu-id="80e3f-156">在安裝 MBAM 伺服器期間，必須安裝並執行 SSRS。</span><span class="sxs-lookup"><span data-stu-id="80e3f-156">SSRS must be installed and running during the MBAM Server installation.</span></span> <span data-ttu-id="80e3f-157">將 SSRS 設定為「原生」模式，而不是在未設定或「SharePoint」模式中。</span><span class="sxs-lookup"><span data-stu-id="80e3f-157">Configure SSRS in “native” mode and not in unconfigured or “SharePoint” mode.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="80e3f-158">恢復資料庫的先決條件</span><span class="sxs-lookup"><span data-stu-id="80e3f-158">Prerequisites for the Recovery Database</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="80e3f-159">必備</span><span class="sxs-lookup"><span data-stu-id="80e3f-159">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="80e3f-160">詳細資料</span><span class="sxs-lookup"><span data-stu-id="80e3f-160">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="80e3f-161">支援的 SQL Server 版本</span><span class="sxs-lookup"><span data-stu-id="80e3f-161">Supported version of SQL Server</span></span></p>
<p><span data-ttu-id="80e3f-162"><a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)">如需支援的版本，請參閱 MBAM 2.0 支援 </a> 的配置。</span><span class="sxs-lookup"><span data-stu-id="80e3f-162">See <a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)">MBAM 2.0 Supported Configurations</a> for supported versions.</span></span></p></td>
<td align="left"><p><span data-ttu-id="80e3f-163">安裝 SQL Server 的方式如下：</span><span class="sxs-lookup"><span data-stu-id="80e3f-163">Install SQL Server with:</span></span></p>
<ul>
<li><p><span data-ttu-id="80e3f-164">SQL_Latin1_General_CP1_CI_AS 排序</span><span class="sxs-lookup"><span data-stu-id="80e3f-164">SQL_Latin1_General_CP1_CI_AS collation</span></span></p></li>
<li><p><span data-ttu-id="80e3f-165">SQL Server 管理工具</span><span class="sxs-lookup"><span data-stu-id="80e3f-165">SQL Server Management Tools</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="80e3f-166">必要的 SQL Server 許可權</span><span class="sxs-lookup"><span data-stu-id="80e3f-166">Required SQL Server permissions</span></span></p></td>
<td align="left"><p><span data-ttu-id="80e3f-167">所需的許可權：</span><span class="sxs-lookup"><span data-stu-id="80e3f-167">Required permissions:</span></span></p>
<ul>
<li><p><span data-ttu-id="80e3f-168">SQL 實例登入伺服器角色：</span><span class="sxs-lookup"><span data-stu-id="80e3f-168">SQL instance Login Server roles:</span></span></p>
<ul>
<li><p><span data-ttu-id="80e3f-169">dbcreator</span><span class="sxs-lookup"><span data-stu-id="80e3f-169">dbcreator</span></span></p></li>
<li><p><span data-ttu-id="80e3f-170">processadmin</span><span class="sxs-lookup"><span data-stu-id="80e3f-170">processadmin</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="80e3f-171">SQL Server Reporting Services 實例許可權：</span><span class="sxs-lookup"><span data-stu-id="80e3f-171">SQL Server Reporting Services instance rights:</span></span></p>
<ul>
<li><p><span data-ttu-id="80e3f-172">建立資料夾</span><span class="sxs-lookup"><span data-stu-id="80e3f-172">Create Folders</span></span></p></li>
<li><p><span data-ttu-id="80e3f-173">發佈報表</span><span class="sxs-lookup"><span data-stu-id="80e3f-173">Publish Reports</span></span></p></li>
</ul></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="80e3f-174">SQL Server 中提供的 [選擇性安裝透明資料加密（TDE）] 功能</span><span class="sxs-lookup"><span data-stu-id="80e3f-174">Optional - Install Transparent Data Encryption (TDE) feature available in SQL Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="80e3f-175">TDE SQL Server 功能可執行即時 i/o 加密及解密資料與記錄檔，這可以協助您遵守各種行業所確立的許多法律、法規和指導方針。</span><span class="sxs-lookup"><span data-stu-id="80e3f-175">The TDE SQL Server feature performs real-time I/O encryption and decryption of the data and log files, which can help you to comply with many laws, regulations, and guidelines established in various industries.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="80e3f-176">注意</span><span class="sxs-lookup"><span data-stu-id="80e3f-176">Note</span></span></strong><br/><p><span data-ttu-id="80e3f-177">TDE 會執行資料庫資訊的即時解密，這表示如果您在 SQL Server 資料表中查看復原金鑰資訊時，您登入的帳戶會擁有資料庫的許可權，則會顯示覆原金鑰資訊。</span><span class="sxs-lookup"><span data-stu-id="80e3f-177">TDE performs real-time decryption of database information, which means that, if the account under which you are logged on has permissions to the database while you are viewing the recovery key information in the SQL Server tables, the recovery key information is visible.</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="80e3f-178">深入瞭解 TDE： <a href="mbam-20-security-considerations-mbam-2.md" data-raw-source="[MBAM 2.0 Security Considerations](mbam-20-security-considerations-mbam-2.md)"> MBAM 2.0 安全考慮 </a> 。</span><span class="sxs-lookup"><span data-stu-id="80e3f-178">More about TDE: <a href="mbam-20-security-considerations-mbam-2.md" data-raw-source="[MBAM 2.0 Security Considerations](mbam-20-security-considerations-mbam-2.md)">MBAM 2.0 Security Considerations</a>.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="80e3f-179">合規性和審核資料庫的先決條件</span><span class="sxs-lookup"><span data-stu-id="80e3f-179">Prerequisites for the Compliance and Audit Database</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="80e3f-180">必備</span><span class="sxs-lookup"><span data-stu-id="80e3f-180">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="80e3f-181">詳細資料</span><span class="sxs-lookup"><span data-stu-id="80e3f-181">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="80e3f-182">支援的 SQL Server 版本</span><span class="sxs-lookup"><span data-stu-id="80e3f-182">Supported version of SQL Server</span></span></p>
<p><span data-ttu-id="80e3f-183"><a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)">如需支援的版本，請參閱 MBAM 2.0 支援 </a> 的配置。</span><span class="sxs-lookup"><span data-stu-id="80e3f-183">See <a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)">MBAM 2.0 Supported Configurations</a> for supported versions.</span></span></p></td>
<td align="left"><p><span data-ttu-id="80e3f-184">安裝 SQL Server 的方式如下：</span><span class="sxs-lookup"><span data-stu-id="80e3f-184">Install SQL Server with:</span></span></p>
<ul>
<li><p><span data-ttu-id="80e3f-185">SQL_Latin1_General_CP1_CI_AS 排序</span><span class="sxs-lookup"><span data-stu-id="80e3f-185">SQL_Latin1_General_CP1_CI_AS collation</span></span></p></li>
<li><p><span data-ttu-id="80e3f-186">SQL Server 管理工具</span><span class="sxs-lookup"><span data-stu-id="80e3f-186">SQL Server Management Tools</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="80e3f-187">必要的 SQL Server 許可權</span><span class="sxs-lookup"><span data-stu-id="80e3f-187">Required SQL Server permissions</span></span></p></td>
<td align="left"><p><span data-ttu-id="80e3f-188">所需的許可權：</span><span class="sxs-lookup"><span data-stu-id="80e3f-188">Required permissions:</span></span></p>
<ul>
<li><p><span data-ttu-id="80e3f-189">SQL 實例登入伺服器角色：</span><span class="sxs-lookup"><span data-stu-id="80e3f-189">SQL instance Login Server roles:</span></span></p>
<ul>
<li><p><span data-ttu-id="80e3f-190">dbcreator</span><span class="sxs-lookup"><span data-stu-id="80e3f-190">dbcreator</span></span></p></li>
<li><p><span data-ttu-id="80e3f-191">processadmin</span><span class="sxs-lookup"><span data-stu-id="80e3f-191">processadmin</span></span></p></li>
</ul></li>
<li><p><span data-ttu-id="80e3f-192">SQL Server Reporting Services 實例許可權：</span><span class="sxs-lookup"><span data-stu-id="80e3f-192">SQL Server Reporting Services instance rights:</span></span></p>
<ul>
<li><p><span data-ttu-id="80e3f-193">建立資料夾</span><span class="sxs-lookup"><span data-stu-id="80e3f-193">Create Folders</span></span></p></li>
<li><p><span data-ttu-id="80e3f-194">發佈報表</span><span class="sxs-lookup"><span data-stu-id="80e3f-194">Publish Reports</span></span></p></li>
</ul></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="80e3f-195">SQL Server 中的 [選擇性安裝透明資料加密（TDE）] 功能。</span><span class="sxs-lookup"><span data-stu-id="80e3f-195">Optional - Install Transparent Data Encryption (TDE) feature in SQL Server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="80e3f-196">TDE SQL Server 功能可執行即時 i/o 加密及解密資料與記錄檔，這可以協助您遵守各種行業所確立的許多法律、法規和指導方針。</span><span class="sxs-lookup"><span data-stu-id="80e3f-196">The TDE SQL Server feature performs real-time I/O encryption and decryption of the data and log files, which can help you to comply with many laws, regulations, and guidelines established in various industries.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="80e3f-197">注意</span><span class="sxs-lookup"><span data-stu-id="80e3f-197">Note</span></span></strong><br/><p><span data-ttu-id="80e3f-198">TDE 會執行資料庫資訊的即時解密，這表示如果您在 SQL Server 資料表中查看復原金鑰資訊時，您登入的帳戶會擁有資料庫的許可權，則會顯示覆原金鑰資訊。</span><span class="sxs-lookup"><span data-stu-id="80e3f-198">TDE performs real-time decryption of database information, which means that, if the account under which you are logged on has permissions to the database while you are viewing the recovery key information in the SQL Server tables, the recovery key information is visible.</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="80e3f-199">深入瞭解 TDE： <a href="mbam-20-security-considerations-mbam-2.md" data-raw-source="[MBAM 2.0 Security Considerations](mbam-20-security-considerations-mbam-2.md)"> MBAM 2.0 安全性考慮</span><span class="sxs-lookup"><span data-stu-id="80e3f-199">More about TDE: <a href="mbam-20-security-considerations-mbam-2.md" data-raw-source="[MBAM 2.0 Security Considerations](mbam-20-security-considerations-mbam-2.md)">MBAM 2.0 Security Considerations</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="80e3f-200">SQL Server 在 MBAM 伺服器安裝期間，必須已安裝並執行資料庫引擎服務。</span><span class="sxs-lookup"><span data-stu-id="80e3f-200">SQL Server must have Database Engine Services installed and running during MBAM Server installation.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="80e3f-201">SQL Server 代理程式服務必須在選取的 SQL Server 實例上執行並設定為自動啟動。</span><span class="sxs-lookup"><span data-stu-id="80e3f-201">The SQL Server Agent service must be running and set to auto-start on the selected instances of SQL Server.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="80e3f-202">自助服務入口網站的先決條件</span><span class="sxs-lookup"><span data-stu-id="80e3f-202">Prerequisites for the Self-Service Portal</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="80e3f-203">必備</span><span class="sxs-lookup"><span data-stu-id="80e3f-203">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="80e3f-204">詳細資料</span><span class="sxs-lookup"><span data-stu-id="80e3f-204">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="80e3f-205">支援的 Windows Server 版本</span><span class="sxs-lookup"><span data-stu-id="80e3f-205">Supported version of Windows Server</span></span></p>
<p><span data-ttu-id="80e3f-206"><a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)">如需支援的版本，請參閱 MBAM 2.0 支援 </a> 的配置。</span><span class="sxs-lookup"><span data-stu-id="80e3f-206">See <a href="mbam-20-supported-configurations-mbam-2.md" data-raw-source="[MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md)">MBAM 2.0 Supported Configurations</a> for supported versions.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="80e3f-207">ASP.NET MVC 2。0</span><span class="sxs-lookup"><span data-stu-id="80e3f-207">ASP.NET MVC 2.0</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=392270" data-raw-source="[ASP.NET MVC 2 download](https://go.microsoft.com/fwlink/?LinkId=392270)"><span data-ttu-id="80e3f-208">ASP.NET MVC 2 下載</span><span class="sxs-lookup"><span data-stu-id="80e3f-208">ASP.NET MVC 2 download</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="80e3f-209">Web 服務 IIS 管理工具</span><span class="sxs-lookup"><span data-stu-id="80e3f-209">Web Service IIS Management Tools</span></span></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="80e3f-210">MBAM 用戶端的先決條件</span><span class="sxs-lookup"><span data-stu-id="80e3f-210">Prerequisites for MBAM Clients</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="80e3f-211">必備</span><span class="sxs-lookup"><span data-stu-id="80e3f-211">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="80e3f-212">詳細資料</span><span class="sxs-lookup"><span data-stu-id="80e3f-212">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="80e3f-213">Windows 7 用戶端只 </strong> - 必須擁有信任的平臺模組（TPM）功能。</span><span class="sxs-lookup"><span data-stu-id="80e3f-213">Windows 7 clients only</strong> - must have Trusted Platform Module (TPM) capability.</span></span></p></td>
<td align="left"><p><span data-ttu-id="80e3f-214">TPM 版本必須是1.2 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="80e3f-214">TPM version must be 1.2 or later.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="80e3f-215">您必須在 BIOS 中開啟 TPM 晶片，然後從作業系統 resettable。</span><span class="sxs-lookup"><span data-stu-id="80e3f-215">The TPM chip must be turned on in the BIOS and be resettable from the operating system.</span></span></p></td>
<td align="left"><p><span data-ttu-id="80e3f-216">如需詳細資訊，請參閱 BIOS 檔。</span><span class="sxs-lookup"><span data-stu-id="80e3f-216">For more information, see the BIOS documentation.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="80e3f-217">僅限 Windows 8 用戶端 </strong> ：若要讓 MBAM 儲存及管理 tpm 復原金鑰：必須先關閉 TPM 自動供給，然後再將 MBAM 設定為 TPM 擁有者，才能部署 MBAM。</span><span class="sxs-lookup"><span data-stu-id="80e3f-217">Windows 8 clients only</strong>: To have MBAM store and manage the TPM recovery keys: TPM auto-provisioning must be turned off, and MBAM must be set as the owner of the TPM before you deploy MBAM.</span></span> <span data-ttu-id="80e3f-218">若要關閉 TPM 自動供給，請參閱 <a href="https://go.microsoft.com/fwlink/?LinkId=286468" data-raw-source="[Disable-TpmAutoProvisioning](https://go.microsoft.com/fwlink/?LinkId=286468)"> Disable-TpmAutoProvisioning </a> 。</span><span class="sxs-lookup"><span data-stu-id="80e3f-218">To turn off TPM auto-provisioning, see <a href="https://go.microsoft.com/fwlink/?LinkId=286468" data-raw-source="[Disable-TpmAutoProvisioning](https://go.microsoft.com/fwlink/?LinkId=286468)">Disable-TpmAutoProvisioning</a>.</span></span></p>
<ul>
<li><p><span data-ttu-id="80e3f-219">TPM 自動預配必須關閉。</span><span class="sxs-lookup"><span data-stu-id="80e3f-219">TPM auto-provisioning must be turned off.</span></span></p></li>
<li><p><span data-ttu-id="80e3f-220">您必須先將 MBAM 設為 TPM 擁有者，然後才能部署 MBAM。</span><span class="sxs-lookup"><span data-stu-id="80e3f-220">MBAM must be set as the owner of the TPM before you deploy MBAM.</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="80e3f-221">若要關閉 TPM 自動供給，請參閱 <a href="https://go.microsoft.com/fwlink/?LinkId=286468" data-raw-source="[Disable-TpmAutoProvisioning](https://go.microsoft.com/fwlink/?LinkId=286468)"> Disable-TpmAutoProvisioning </a> 。</span><span class="sxs-lookup"><span data-stu-id="80e3f-221">To turn off TPM auto-provisioning, see <a href="https://go.microsoft.com/fwlink/?LinkId=286468" data-raw-source="[Disable-TpmAutoProvisioning](https://go.microsoft.com/fwlink/?LinkId=286468)">Disable-TpmAutoProvisioning</a>.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="80e3f-222">注意</span><span class="sxs-lookup"><span data-stu-id="80e3f-222">Note</span></span></strong><br/><p><span data-ttu-id="80e3f-223">確定鍵盤、影片或滑鼠已直接連接，且未透過鍵盤、影片或滑鼠（KVM）開關進行管理。</span><span class="sxs-lookup"><span data-stu-id="80e3f-223">Ensure that the keyboard, video, or mouse are directly connected and not managed through a keyboard, video, or mouse (KVM) switch.</span></span> <span data-ttu-id="80e3f-224">KVM 切換器可能會干擾電腦偵測硬體實際狀態的能力。</span><span class="sxs-lookup"><span data-stu-id="80e3f-224">A KVM switch can interfere with the ability of the computer to detect the physical presence of hardware.</span></span></p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="80e3f-225">相關主題</span><span class="sxs-lookup"><span data-stu-id="80e3f-225">Related topics</span></span>


[<span data-ttu-id="80e3f-226">規劃部署 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="80e3f-226">Planning to Deploy MBAM 2.0</span></span>](planning-to-deploy-mbam-20-mbam-2.md)

[<span data-ttu-id="80e3f-227">MBAM 2.0 支援的組態</span><span class="sxs-lookup"><span data-stu-id="80e3f-227">MBAM 2.0 Supported Configurations</span></span>](mbam-20-supported-configurations-mbam-2.md)









