---
title: 安裝 APP-V 5.x Server 之前先查看登錄機碼
description: 安裝 APP-V 5.x Server 之前先查看登錄機碼
author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.openlocfilehash: 9fe5a1b37d0fb5208d138939bb2fc79c89171fb3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800661"
---
# <span data-ttu-id="c0887-103">安裝 APP-V 5.x Server 之前先查看登錄機碼</span><span class="sxs-lookup"><span data-stu-id="c0887-103">Check Registry Keys before installing App-V 5.x Server</span></span>

<span data-ttu-id="c0887-104">如果您要從 App-v 5.0 SP1 修復程式套件3或更新版本升級 app-v Server，請先完成本節中的步驟，再安裝應用程式-V 5 a.x 伺服器</span><span class="sxs-lookup"><span data-stu-id="c0887-104">If you are upgrading the App-V Server from App-V 5.0 SP1 Hotfix Package 3 or later, complete the steps in this section before installing the App-V 5.x Server</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="c0887-105">需要此步驟時</span><span class="sxs-lookup"><span data-stu-id="c0887-105">When this step is required</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="c0887-106">您要從 App-v 5.0 SP1 升級到您使用 .msp 檔案安裝的任何後續修復程式套件。</span><span class="sxs-lookup"><span data-stu-id="c0887-106">You are upgrading from App-V 5.0 SP1 with any subsequent Hotfix Packages that you installed by using an .msp file.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="c0887-107">哪些元件需要您執行此步驟</span><span class="sxs-lookup"><span data-stu-id="c0887-107">Which components require that you do this step</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="c0887-108">僅限您要升級的 App-v Server 元件。</span><span class="sxs-lookup"><span data-stu-id="c0887-108">Only the App-V Server components that you are upgrading.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="c0887-109">當您需要執行此步驟時</span><span class="sxs-lookup"><span data-stu-id="c0887-109">When you need to do this step</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="c0887-110">將 app-v Server 升級到 App 之前，請先將 App-v 伺服器升級至 App-v</span><span class="sxs-lookup"><span data-stu-id="c0887-110">Before you upgrade the App-V Server to App-V 5.x</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="c0887-111">您需要執行的動作</span><span class="sxs-lookup"><span data-stu-id="c0887-111">What you need to do</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="c0887-112">使用下清單格中的資訊， <code>HKLM\Software\Microsoft\AppV\Server</code> 以您在原始伺服器安裝中所提供的值來更新每個登錄項的值。</span><span class="sxs-lookup"><span data-stu-id="c0887-112">Using the information in the following tables, update each registry key value under <code>HKLM\Software\Microsoft\AppV\Server</code> with the value that you provided in your original server installation.</span></span> <span data-ttu-id="c0887-113">完成此步驟會還原在安裝 App-v 5.0 SP1 修復程式套件時可能已移除的註冊表值。</span><span class="sxs-lookup"><span data-stu-id="c0887-113">Completing this step restores registry values that may have been removed when App-V 5.0 SP1 Hotfix Packages were installed.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="c0887-114">ManagementDatabase 鍵</span><span class="sxs-lookup"><span data-stu-id="c0887-114">ManagementDatabase key</span></span>**

<span data-ttu-id="c0887-115">如果您要安裝管理資料庫，請在 [] 底下設定這些登錄機碼 `HKLM\Software\Microsoft\AppV\Server\ManagementDatabase` 。</span><span class="sxs-lookup"><span data-stu-id="c0887-115">If you are installing the Management database, set these registry keys under `HKLM\Software\Microsoft\AppV\Server\ManagementDatabase`.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c0887-116">索引鍵名稱</span><span class="sxs-lookup"><span data-stu-id="c0887-116">Key name</span></span></th>
<th align="left"><span data-ttu-id="c0887-117">描述</span><span class="sxs-lookup"><span data-stu-id="c0887-117">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c0887-118">IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="c0887-118">IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</span></span></p></td>
<td align="left"><p><span data-ttu-id="c0887-119">說明是否需要公用存取帳戶才能存取非本地管理資料庫。</span><span class="sxs-lookup"><span data-stu-id="c0887-119">Describes whether a public access account is required to access non-local management databases.</span></span> <span data-ttu-id="c0887-120">如果需要，值會設定為 "1"。</span><span class="sxs-lookup"><span data-stu-id="c0887-120">Value is set to “1” if it is required.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c0887-121">MANAGEMENT_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="c0887-121">MANAGEMENT_DB_NAME</span></span></p></td>
<td align="left"><p><span data-ttu-id="c0887-122">管理資料庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="c0887-122">Name of the Management database.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c0887-123">MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="c0887-123">MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="c0887-124">用於讀取（公開）管理資料庫存取權的帳戶。</span><span class="sxs-lookup"><span data-stu-id="c0887-124">Account used for read (public) access to the Management database.</span></span></p>
<p><span data-ttu-id="c0887-125">在 <code>IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> 設定為1時使用。</span><span class="sxs-lookup"><span data-stu-id="c0887-125">Used when <code>IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> is set to 1.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c0887-126">MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_SID</span><span class="sxs-lookup"><span data-stu-id="c0887-126">MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_SID</span></span></p></td>
<td align="left"><p><span data-ttu-id="c0887-127">用來讀取（公開）管理資料庫存取權的帳戶的安全識別碼（SID）。</span><span class="sxs-lookup"><span data-stu-id="c0887-127">Secure identifier (SID) of the account used for read (public) access to the Management database.</span></span></p>
<p><span data-ttu-id="c0887-128">在 <code>IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> 設定為1時使用。</span><span class="sxs-lookup"><span data-stu-id="c0887-128">Used when <code>IS_MANAGEMENT_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> is set to 1.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c0887-129">MANAGEMENT_DB_SQL_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="c0887-129">MANAGEMENT_DB_SQL_INSTANCE</span></span></p></td>
<td align="left"><p><span data-ttu-id="c0887-130">管理資料庫的 SQL Server 實例。</span><span class="sxs-lookup"><span data-stu-id="c0887-130">SQL Server instance for the Management database.</span></span></p>
<p><span data-ttu-id="c0887-131">如果該值為空白，則會使用預設的資料庫實例。</span><span class="sxs-lookup"><span data-stu-id="c0887-131">If the value is blank, the default database instance is used.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c0887-132">MANAGEMENT_DB_WRITE_ACCESS_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="c0887-132">MANAGEMENT_DB_WRITE_ACCESS_ACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="c0887-133">用於寫入管理資料庫（系統管理員）存取權的帳戶。</span><span class="sxs-lookup"><span data-stu-id="c0887-133">Account used for write (administrator) access to the Management database.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c0887-134">MANAGEMENT_DB_WRITE_ACCESS_ACCOUNT_SID</span><span class="sxs-lookup"><span data-stu-id="c0887-134">MANAGEMENT_DB_WRITE_ACCESS_ACCOUNT_SID</span></span></p></td>
<td align="left"><p><span data-ttu-id="c0887-135">用來撰寫（系統管理員）存取管理資料庫之帳戶的安全識別碼（SID）。</span><span class="sxs-lookup"><span data-stu-id="c0887-135">Secure identifier (SID) of the account used for write (administrator) access to the Management database.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c0887-136">MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="c0887-136">MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="c0887-137">管理伺服器遠端電腦帳戶（[域 \ 帳戶]）。</span><span class="sxs-lookup"><span data-stu-id="c0887-137">Management server remote computer account (domain\account).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c0887-138">MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="c0887-138">MANAGEMENT_SERVER_INSTALL_ADMIN_ACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="c0887-139">管理伺服器（域 \ 帳戶）的安裝管理員登入。</span><span class="sxs-lookup"><span data-stu-id="c0887-139">Installation administrator login for the Management server (domain\account).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c0887-140">MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="c0887-140">MANAGEMENT_SERVER_MACHINE_USE_LOCAL</span></span></p></td>
<td align="left"><p><span data-ttu-id="c0887-141">有效值如下：</span><span class="sxs-lookup"><span data-stu-id="c0887-141">Valid values are:</span></span></p>
<ul>
<li><p><strong><span data-ttu-id="c0887-142">1 </strong> -此管理服務是在本機電腦上，也就是 MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT 是空白的。</span><span class="sxs-lookup"><span data-stu-id="c0887-142">1</strong> – the Management service is on the local computer, that is, MANAGEMENT_REMOTE_SERVER_MACHINE_ACCOUNT is blank.</span></span></p></li>
<li><p><strong><span data-ttu-id="c0887-143">0 </strong> - 管理服務與本機電腦位於不同的電腦上。</span><span class="sxs-lookup"><span data-stu-id="c0887-143">0</strong> - the Management service is on a different computer from the local computer.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="c0887-144">ManagementService 鍵</span><span class="sxs-lookup"><span data-stu-id="c0887-144">ManagementService key</span></span>**

<span data-ttu-id="c0887-145">如果您要安裝管理伺服器，請在 [] 底下設定這些登錄機碼 `HKLM\Software\Microsoft\AppV\Server\ManagementService` 。</span><span class="sxs-lookup"><span data-stu-id="c0887-145">If you are installing the Management server, set these registry keys under `HKLM\Software\Microsoft\AppV\Server\ManagementService`.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c0887-146">索引鍵名稱</span><span class="sxs-lookup"><span data-stu-id="c0887-146">Key name</span></span></th>
<th align="left"><span data-ttu-id="c0887-147">描述</span><span class="sxs-lookup"><span data-stu-id="c0887-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c0887-148">MANAGEMENT_ADMINACCOUNT</span><span class="sxs-lookup"><span data-stu-id="c0887-148">MANAGEMENT_ADMINACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="c0887-149">已授權管理 App-v （網域 \ 帳戶）的 Active Directory 網域服務（AD DS）群組或帳戶。</span><span class="sxs-lookup"><span data-stu-id="c0887-149">Active Directory Domain Services (AD DS) group or account that is authorized to manage App-V (domain\account).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c0887-150">MANAGEMENT_DB_SQL_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="c0887-150">MANAGEMENT_DB_SQL_INSTANCE</span></span></p></td>
<td align="left"><p><span data-ttu-id="c0887-151">包含管理資料庫的 SQL server 實例。</span><span class="sxs-lookup"><span data-stu-id="c0887-151">SQL server instance that contains the Management database.</span></span></p>
<p><span data-ttu-id="c0887-152">如果該值為空白，則會使用預設的資料庫實例。</span><span class="sxs-lookup"><span data-stu-id="c0887-152">If the value is blank, the default database instance is used.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c0887-153">MANAGEMENT_DB_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="c0887-153">MANAGEMENT_DB_SQL_SERVER_NAME</span></span></p></td>
<td align="left"><p><span data-ttu-id="c0887-154">包含管理資料庫的遠端 SQL 伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="c0887-154">Name of the remote SQL server with the Management database.</span></span></p>
<p><span data-ttu-id="c0887-155">如果此值為空白，則會使用本機電腦。</span><span class="sxs-lookup"><span data-stu-id="c0887-155">If the value is blank, the local computer is used.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="c0887-156">ReportingDatabase 鍵</span><span class="sxs-lookup"><span data-stu-id="c0887-156">ReportingDatabase key</span></span>**

<span data-ttu-id="c0887-157">如果您要安裝報告資料庫，請在 [] 底下設定這些登錄機碼 `HKLM\Software\Microsoft\AppV\Server\ReportingDatabase` 。</span><span class="sxs-lookup"><span data-stu-id="c0887-157">If you are installing the Reporting database, set these registry keys under `HKLM\Software\Microsoft\AppV\Server\ReportingDatabase`.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c0887-158">索引鍵名稱</span><span class="sxs-lookup"><span data-stu-id="c0887-158">Key name</span></span></th>
<th align="left"><span data-ttu-id="c0887-159">描述</span><span class="sxs-lookup"><span data-stu-id="c0887-159">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c0887-160">IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</span><span class="sxs-lookup"><span data-stu-id="c0887-160">IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</span></span></p></td>
<td align="left"><p><span data-ttu-id="c0887-161">說明存取非本地報告資料庫是否需要公用存取帳戶。</span><span class="sxs-lookup"><span data-stu-id="c0887-161">Describes whether a public access account is required to access non-local reporting databases.</span></span> <span data-ttu-id="c0887-162">如果需要，值會設定為 "1"。</span><span class="sxs-lookup"><span data-stu-id="c0887-162">Value is set to “1” if it is required.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c0887-163">REPORTING_DB_NAME</span><span class="sxs-lookup"><span data-stu-id="c0887-163">REPORTING_DB_NAME</span></span></p></td>
<td align="left"><p><span data-ttu-id="c0887-164">報告資料庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="c0887-164">Name of the Reporting database.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c0887-165">REPORTING_DB_PUBLIC_ACCESS_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="c0887-165">REPORTING_DB_PUBLIC_ACCESS_ACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="c0887-166">用於讀取（公開）存取報表資料庫的帳戶。</span><span class="sxs-lookup"><span data-stu-id="c0887-166">Account used for read (public) access to the Reporting database.</span></span></p>
<p><span data-ttu-id="c0887-167">在 <code>IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> 設定為1時使用。</span><span class="sxs-lookup"><span data-stu-id="c0887-167">Used when <code>IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> is set to 1.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c0887-168">REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_SID</span><span class="sxs-lookup"><span data-stu-id="c0887-168">REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_SID</span></span></p></td>
<td align="left"><p><span data-ttu-id="c0887-169">帳戶的安全識別碼（SID），用於讀取（公開）的報表資料庫存取權。</span><span class="sxs-lookup"><span data-stu-id="c0887-169">Secure identifier (SID) of the account used for read (public) access to the Reporting database.</span></span></p>
<p><span data-ttu-id="c0887-170">在 <code>IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> 設定為1時使用。</span><span class="sxs-lookup"><span data-stu-id="c0887-170">Used when <code>IS_REPORTING_DB_PUBLIC_ACCESS_ACCOUNT_REQUIRED</code> is set to 1.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c0887-171">REPORTING_DB_SQL_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="c0887-171">REPORTING_DB_SQL_INSTANCE</span></span></p></td>
<td align="left"><p><span data-ttu-id="c0887-172">報表資料庫的 SQL Server 實例。</span><span class="sxs-lookup"><span data-stu-id="c0887-172">SQL Server instance for the Reporting database.</span></span></p>
<p><span data-ttu-id="c0887-173">如果該值為空白，則會使用預設的資料庫實例。</span><span class="sxs-lookup"><span data-stu-id="c0887-173">If the value is blank, the default database instance is used.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c0887-174">REPORTING_DB_WRITE_ACCESS_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="c0887-174">REPORTING_DB_WRITE_ACCESS_ACCOUNT</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c0887-175">REPORTING_DB_WRITE_ACCESS_ACCOUNT_SID</span><span class="sxs-lookup"><span data-stu-id="c0887-175">REPORTING_DB_WRITE_ACCESS_ACCOUNT_SID</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c0887-176">REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="c0887-176">REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="c0887-177">報表伺服器遠端電腦帳戶（[域 \ 帳戶]）。</span><span class="sxs-lookup"><span data-stu-id="c0887-177">Reporting server remote computer account (domain\account).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c0887-178">REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span><span class="sxs-lookup"><span data-stu-id="c0887-178">REPORTING_SERVER_INSTALL_ADMIN_ACCOUNT</span></span></p></td>
<td align="left"><p><span data-ttu-id="c0887-179">報表服務器（域 \ 帳戶）的安裝管理員登入。</span><span class="sxs-lookup"><span data-stu-id="c0887-179">Installation administrator login for the Reporting server (domain\account).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c0887-180">REPORTING_SERVER_MACHINE_USE_LOCAL</span><span class="sxs-lookup"><span data-stu-id="c0887-180">REPORTING_SERVER_MACHINE_USE_LOCAL</span></span></p></td>
<td align="left"><p><span data-ttu-id="c0887-181">有效值如下：</span><span class="sxs-lookup"><span data-stu-id="c0887-181">Valid values are:</span></span></p>
<ul>
<li><p><strong><span data-ttu-id="c0887-182">1 </strong> -報表服務位於本機電腦上，即 REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT 為空白。</span><span class="sxs-lookup"><span data-stu-id="c0887-182">1</strong> – the Reporting service is on the local computer, that is, REPORTING_REMOTE_SERVER_MACHINE_ACCOUNT is blank.</span></span></p></li>
<li><p><strong><span data-ttu-id="c0887-183">0 </strong> - 報表服務與本機電腦在不同的電腦上。</span><span class="sxs-lookup"><span data-stu-id="c0887-183">0</strong> - the Reporting service is on a different computer from the local computer.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="c0887-184">ReportingService 鍵</span><span class="sxs-lookup"><span data-stu-id="c0887-184">ReportingService key</span></span>**

<span data-ttu-id="c0887-185">如果您要安裝報表伺服器，請在中設定這些登錄機碼 `HKLM\Software\Microsoft\AppV\Server\ReportingService` 。</span><span class="sxs-lookup"><span data-stu-id="c0887-185">If you are installing the Reporting server, set these registry keys under `HKLM\Software\Microsoft\AppV\Server\ReportingService`.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c0887-186">索引鍵名稱</span><span class="sxs-lookup"><span data-stu-id="c0887-186">Key name</span></span></th>
<th align="left"><span data-ttu-id="c0887-187">描述</span><span class="sxs-lookup"><span data-stu-id="c0887-187">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c0887-188">REPORTING_DB_SQL_INSTANCE</span><span class="sxs-lookup"><span data-stu-id="c0887-188">REPORTING_DB_SQL_INSTANCE</span></span></p></td>
<td align="left"><p><span data-ttu-id="c0887-189">報表資料庫的 SQL Server 實例。</span><span class="sxs-lookup"><span data-stu-id="c0887-189">SQL Server instance for the Reporting database.</span></span></p>
<p><span data-ttu-id="c0887-190">如果該值為空白，則會使用預設的資料庫實例。</span><span class="sxs-lookup"><span data-stu-id="c0887-190">If the value is blank, the default database instance is used.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c0887-191">REPORTING_DB_SQL_SERVER_NAME</span><span class="sxs-lookup"><span data-stu-id="c0887-191">REPORTING_DB_SQL_SERVER_NAME</span></span></p></td>
<td align="left"><p><span data-ttu-id="c0887-192">具有報告資料庫之遠端 SQL 伺服器的名稱。</span><span class="sxs-lookup"><span data-stu-id="c0887-192">Name of the remote SQL server with the Reporting database.</span></span></p>
<p><span data-ttu-id="c0887-193">如果此值為空白，則會使用本機電腦。</span><span class="sxs-lookup"><span data-stu-id="c0887-193">If the value is blank, the local computer is used.</span></span></p></td>
</tr>
</tbody>
</table>

