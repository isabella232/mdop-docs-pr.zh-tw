---
title: 規劃使用設定管理員進行 MBAM 部署
description: 規劃使用設定管理員進行 MBAM 部署
author: dansimp
ms.assetid: fb768306-48c2-40b4-ac4e-c279db987391
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e8588ce03c86a8a5138d591327e5f95503dce5ad
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811270"
---
# <span data-ttu-id="02f10-103">規劃使用設定管理員進行 MBAM 部署</span><span class="sxs-lookup"><span data-stu-id="02f10-103">Planning to Deploy MBAM with Configuration Manager</span></span>


<span data-ttu-id="02f10-104">若要使用 Configuration Manager 拓撲部署 MBAM，建議使用支援200000用戶端的三台伺服器架構。</span><span class="sxs-lookup"><span data-stu-id="02f10-104">To deploy MBAM with the Configuration Manager topology, a three-server architecture, which supports 200,000 clients, is recommended.</span></span> <span data-ttu-id="02f10-105">使用個別的伺服器來執行 Configuration Manager，並在兩個伺服器上安裝基本的管理和監控功能，如快速入門中的架構影像所示[-搭配 Configuration Manager 使用 MBAM](getting-started---using-mbam-with-configuration-manager.md)。</span><span class="sxs-lookup"><span data-stu-id="02f10-105">Use a separate server to run Configuration Manager, and install the basic Administration and Monitoring features on two servers, as shown in the architecture image in [Getting Started - Using MBAM with Configuration Manager](getting-started---using-mbam-with-configuration-manager.md).</span></span>

**<span data-ttu-id="02f10-106">重要</span><span class="sxs-lookup"><span data-stu-id="02f10-106">Important</span></span>**  
<span data-ttu-id="02f10-107">當您安裝 MBAM 與 Configuration Manager 2007 的整合拓撲時，系統不支援 Windows To Go。</span><span class="sxs-lookup"><span data-stu-id="02f10-107">Windows To Go is not supported when you install the integrated topology of MBAM with Configuration Manager 2007.</span></span>



## <span data-ttu-id="02f10-108">使用 Configuration Manager 安裝 MBAM 的部署先決條件</span><span class="sxs-lookup"><span data-stu-id="02f10-108">Deployment Prerequisites for Installing MBAM with Configuration Manager</span></span>


<span data-ttu-id="02f10-109">在使用 Configuration Manager 安裝 MBAM 之前，請確定您已符合下列先決條件：</span><span class="sxs-lookup"><span data-stu-id="02f10-109">Ensure that you have met the following prerequisites before you install MBAM with Configuration Manager:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="02f10-110">必備</span><span class="sxs-lookup"><span data-stu-id="02f10-110">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="02f10-111">其他資訊</span><span class="sxs-lookup"><span data-stu-id="02f10-111">Additional Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="02f10-112">確定 Configuration Manager 伺服器是 Configuration Manager 系統中的主要網站。</span><span class="sxs-lookup"><span data-stu-id="02f10-112">Ensure that the Configuration Manager Server is a primary site in the Configuration Manager system.</span></span></p></td>
<td align="left"><p><span data-ttu-id="02f10-113">無</span><span class="sxs-lookup"><span data-stu-id="02f10-113">N/A</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="02f10-114">在 Configuration Manager 伺服器上啟用硬體清查用戶端代理程式。</span><span class="sxs-lookup"><span data-stu-id="02f10-114">Enable the Hardware Inventory Client Agent on the Configuration Manager Server.</span></span></p></td>
<td align="left"><p><span data-ttu-id="02f10-115">如需 Configuration Manager 2007 的詳細說明，請參閱 <a href="https://go.microsoft.com/fwlink/?LinkId=301656" data-raw-source="[How to Configure Hardware Inventory for a Site](https://go.microsoft.com/fwlink/?LinkId=301656)"> 如何設定網站的硬體清點 </a> 。</span><span class="sxs-lookup"><span data-stu-id="02f10-115">For Configuration Manager 2007, see <a href="https://go.microsoft.com/fwlink/?LinkId=301656" data-raw-source="[How to Configure Hardware Inventory for a Site](https://go.microsoft.com/fwlink/?LinkId=301656)">How to Configure Hardware Inventory for a Site</a>.</span></span></p>
<p><span data-ttu-id="02f10-116">針對 System Center 2012 Configuration Manager，請參閱 <a href="https://go.microsoft.com/fwlink/?LinkId=301685" data-raw-source="[How to Configure Hardware Inventory in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301685)"> 如何在 Configuration Manager 中設定硬體清查 </a> 。</span><span class="sxs-lookup"><span data-stu-id="02f10-116">For System Center 2012 Configuration Manager, see <a href="https://go.microsoft.com/fwlink/?LinkId=301685" data-raw-source="[How to Configure Hardware Inventory in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301685)">How to Configure Hardware Inventory in Configuration Manager</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="02f10-117">根據您所使用的 Configuration Manager 版本，啟用所需的設定管理（DCM）代理或合規性設定。</span><span class="sxs-lookup"><span data-stu-id="02f10-117">Enable the Desired Configuration Management (DCM) agent or the compliance settings, depending on the version of Configuration Manager that you are using.</span></span></p></td>
<td align="left"><p><span data-ttu-id="02f10-118">針對 Configuration Manager 2007，請啟用 [查看 <a href="https://go.microsoft.com/fwlink/?LinkId=301686" data-raw-source="[Desired Configuration Management Client Agent Properties](https://go.microsoft.com/fwlink/?LinkId=301686)"> 所需的建構管理用戶端代理程式屬性] </a> 。</span><span class="sxs-lookup"><span data-stu-id="02f10-118">For Configuration Manager 2007, enable the see <a href="https://go.microsoft.com/fwlink/?LinkId=301686" data-raw-source="[Desired Configuration Management Client Agent Properties](https://go.microsoft.com/fwlink/?LinkId=301686)">Desired Configuration Management Client Agent Properties</a>.</span></span></p>
<p><span data-ttu-id="02f10-119">針對 System Center 2012 Configuration Manager，請參閱 <a href="https://go.microsoft.com/fwlink/?LinkId=301687" data-raw-source="[Configuring Compliance Settings in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301687)"> 在 Configuration Manager 中設定合規性設定 </a> 。</span><span class="sxs-lookup"><span data-stu-id="02f10-119">For System Center 2012 Configuration Manager, see <a href="https://go.microsoft.com/fwlink/?LinkId=301687" data-raw-source="[Configuring Compliance Settings in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301687)">Configuring Compliance Settings in Configuration Manager</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="02f10-120">在 Configuration Manager 中定義報表服務點。</span><span class="sxs-lookup"><span data-stu-id="02f10-120">Define a reporting services point in Configuration Manager.</span></span> <span data-ttu-id="02f10-121">SQL Reporting Services 所需。</span><span class="sxs-lookup"><span data-stu-id="02f10-121">Required for SQL Reporting Services.</span></span></p></td>
<td align="left"><p><span data-ttu-id="02f10-122">如需 Configuration Manager 2007 的詳細說明，請參閱 <a href="https://go.microsoft.com/fwlink/?LinkId=301688" data-raw-source="[How to Create a Reporting Services Point for SQL Reporting Services](https://go.microsoft.com/fwlink/?LinkId=301688)"> 如何為 SQL Reporting Services 建立 Reporting Services 點 </a> 。</span><span class="sxs-lookup"><span data-stu-id="02f10-122">For Configuration Manager 2007, see <a href="https://go.microsoft.com/fwlink/?LinkId=301688" data-raw-source="[How to Create a Reporting Services Point for SQL Reporting Services](https://go.microsoft.com/fwlink/?LinkId=301688)">How to Create a Reporting Services Point for SQL Reporting Services</a>.</span></span></p>
<p><span data-ttu-id="02f10-123">針對 System Center 2012 Configuration Manager，請參閱 <a href="https://go.microsoft.com/fwlink/?LinkId=301689" data-raw-source="[Prerequisites for Reporting in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301689)"> Configuration manager 中的報告先決條件 </a> 。</span><span class="sxs-lookup"><span data-stu-id="02f10-123">For System Center 2012 Configuration Manager, see <a href="https://go.microsoft.com/fwlink/?LinkId=301689" data-raw-source="[Prerequisites for Reporting in Configuration Manager](https://go.microsoft.com/fwlink/?LinkId=301689)">Prerequisites for Reporting in Configuration Manager</a>.</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="---------configuration-manager-supported-versions"></a> <span data-ttu-id="02f10-124">Configuration Manager 支援的版本</span><span class="sxs-lookup"><span data-stu-id="02f10-124">Configuration Manager Supported Versions</span></span>


<span data-ttu-id="02f10-125">MBAM 支援下列版本的 Configuration Manager：</span><span class="sxs-lookup"><span data-stu-id="02f10-125">MBAM supports the following versions of Configuration Manager:</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="02f10-126">支援的版本</span><span class="sxs-lookup"><span data-stu-id="02f10-126">Supported version</span></span></th>
<th align="left"><span data-ttu-id="02f10-127">Service pack</span><span class="sxs-lookup"><span data-stu-id="02f10-127">Service pack</span></span></th>
<th align="left"><span data-ttu-id="02f10-128">系統架構</span><span class="sxs-lookup"><span data-stu-id="02f10-128">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="02f10-129">Microsoft System Center Configuration Manager 2007 R2</span><span class="sxs-lookup"><span data-stu-id="02f10-129">Microsoft System Center Configuration Manager 2007 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="02f10-130">SP1 或更新版本</span><span class="sxs-lookup"><span data-stu-id="02f10-130">SP1 or later</span></span></p></td>
<td align="left"><p><span data-ttu-id="02f10-131">64 位元</span><span class="sxs-lookup"><span data-stu-id="02f10-131">64-bit</span></span></p>
<div class="alert">
<strong><span data-ttu-id="02f10-132">注意</span><span class="sxs-lookup"><span data-stu-id="02f10-132">Note</span></span></strong><br/><p><span data-ttu-id="02f10-133">雖然 Configuration Manager 2007 是32位，您必須將它與 SQL Server 安裝在64位作業系統上，才能符合64位 MBAM 軟體。</span><span class="sxs-lookup"><span data-stu-id="02f10-133">Although Configuration Manager 2007 is 32 bit, you must install it and SQL Server on a 64-bit operating system in order to match the 64-bit MBAM software.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="02f10-134">Microsoft System Center 2012 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="02f10-134">Microsoft System Center 2012 Configuration Manager</span></span></p></td>
<td align="left"><p><span data-ttu-id="02f10-135">SP1</span><span class="sxs-lookup"><span data-stu-id="02f10-135">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="02f10-136">64 位元</span><span class="sxs-lookup"><span data-stu-id="02f10-136">64-bit</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="02f10-137">如需 Configuration Manager 伺服器支援的設定的清單，請參閱適用于您所使用之 Configuration Manager 版本的頁面。</span><span class="sxs-lookup"><span data-stu-id="02f10-137">For a list of supported configurations for the Configuration Manager Server, see the appropriate webpage for the version of Configuration Manager that you are using.</span></span> <span data-ttu-id="02f10-138">MBAM 對於 Configuration Manager 伺服器沒有額外的系統需求。</span><span class="sxs-lookup"><span data-stu-id="02f10-138">MBAM has no additional system requirements for the Configuration Manager Server.</span></span>

## <a href="" id="---------mbam-and-sql-server-system-requirements"></a> <span data-ttu-id="02f10-139">MBAM 與 SQL Server 系統需求</span><span class="sxs-lookup"><span data-stu-id="02f10-139">MBAM and SQL Server System Requirements</span></span>


<span data-ttu-id="02f10-140">MBAM 伺服器與 Configuration Manager 拓撲的 SQL Server 支援的設定和系統需求與獨立拓朴的配置和系統需求相同。</span><span class="sxs-lookup"><span data-stu-id="02f10-140">The supported configurations and system requirements for the MBAM servers and SQL Server for the Configuration Manager topology are the same as those for the Stand-alone topology.</span></span> <span data-ttu-id="02f10-141">如需獨立的系統需求，請參閱[MBAM 2.0 支援](mbam-20-supported-configurations-mbam-2.md)的設定。</span><span class="sxs-lookup"><span data-stu-id="02f10-141">For the Stand-alone system requirements, see [MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md).</span></span> <span data-ttu-id="02f10-142">如需 Configuration Manager 拓撲的 MBAM 伺服器與 SQL Server 處理器、RAM 及磁碟空間需求，請參閱下列各節。</span><span class="sxs-lookup"><span data-stu-id="02f10-142">For the MBAM Server and SQL Server processor, RAM, and disk space requirements for the Configuration Manager topology, see the following sections.</span></span>

## <span data-ttu-id="02f10-143">MBAM 伺服器處理器、RAM 與磁碟空間需求 MBAM</span><span class="sxs-lookup"><span data-stu-id="02f10-143">MBAM Server Processor, RAM, and Disk Space Requirements for MBAM</span></span>


<span data-ttu-id="02f10-144">下表列出當您使用 Configuration Manager 整合拓撲時，MBAM 伺服器的伺服器處理器、RAM 和磁碟空間需求。</span><span class="sxs-lookup"><span data-stu-id="02f10-144">The following table lists the server processor, RAM, and disk space requirements for MBAM servers when you are using the Configuration Manager Integration topology.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="02f10-145">硬體元件</span><span class="sxs-lookup"><span data-stu-id="02f10-145">Hardware Component</span></span></th>
<th align="left"><span data-ttu-id="02f10-146">最低需求</span><span class="sxs-lookup"><span data-stu-id="02f10-146">Minimum Requirement</span></span></th>
<th align="left"><span data-ttu-id="02f10-147">建議的需求</span><span class="sxs-lookup"><span data-stu-id="02f10-147">Recommended Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="02f10-148">處理者</span><span class="sxs-lookup"><span data-stu-id="02f10-148">Processor</span></span></p></td>
<td align="left"><p><span data-ttu-id="02f10-149">2.33 GHz</span><span class="sxs-lookup"><span data-stu-id="02f10-149">2.33 GHz</span></span></p></td>
<td align="left"><p><span data-ttu-id="02f10-150">2.33 GHz 或以上</span><span class="sxs-lookup"><span data-stu-id="02f10-150">2.33 GHz or greater</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="02f10-151">RAM</span><span class="sxs-lookup"><span data-stu-id="02f10-151">RAM</span></span></p></td>
<td align="left"><p><span data-ttu-id="02f10-152">4 GB</span><span class="sxs-lookup"><span data-stu-id="02f10-152">4 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="02f10-153">8 GB</span><span class="sxs-lookup"><span data-stu-id="02f10-153">8 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="02f10-154">可用磁碟空間</span><span class="sxs-lookup"><span data-stu-id="02f10-154">Free disk space</span></span></p></td>
<td align="left"><p><span data-ttu-id="02f10-155">1 GB</span><span class="sxs-lookup"><span data-stu-id="02f10-155">1 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="02f10-156">2 GB</span><span class="sxs-lookup"><span data-stu-id="02f10-156">2 GB</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="02f10-157">SQL Server 處理器、RAM 與磁碟空間需求</span><span class="sxs-lookup"><span data-stu-id="02f10-157">SQL Server Processor, RAM, and Disk Space Requirements</span></span>


<span data-ttu-id="02f10-158">下表列出當您使用 Configuration Manager 整合拓撲時，SQL Server 電腦的伺服器處理器、RAM 與磁碟空間需求。</span><span class="sxs-lookup"><span data-stu-id="02f10-158">The following table lists the server processor, RAM, and disk space requirements for the SQL Server computer when you are using the Configuration Manager Integration topology.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="02f10-159">硬體元件</span><span class="sxs-lookup"><span data-stu-id="02f10-159">Hardware Component</span></span></th>
<th align="left"><span data-ttu-id="02f10-160">最低需求</span><span class="sxs-lookup"><span data-stu-id="02f10-160">Minimum Requirement</span></span></th>
<th align="left"><span data-ttu-id="02f10-161">建議的需求</span><span class="sxs-lookup"><span data-stu-id="02f10-161">Recommended Requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="02f10-162">處理者</span><span class="sxs-lookup"><span data-stu-id="02f10-162">Processor</span></span></p></td>
<td align="left"><p><span data-ttu-id="02f10-163">2.33 GHz</span><span class="sxs-lookup"><span data-stu-id="02f10-163">2.33 GHz</span></span></p></td>
<td align="left"><p><span data-ttu-id="02f10-164">2.33 GHz 或以上</span><span class="sxs-lookup"><span data-stu-id="02f10-164">2.33 GHz or greater</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="02f10-165">RAM</span><span class="sxs-lookup"><span data-stu-id="02f10-165">RAM</span></span></p></td>
<td align="left"><p><span data-ttu-id="02f10-166">4 GB</span><span class="sxs-lookup"><span data-stu-id="02f10-166">4 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="02f10-167">8 GB</span><span class="sxs-lookup"><span data-stu-id="02f10-167">8 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="02f10-168">可用磁碟空間</span><span class="sxs-lookup"><span data-stu-id="02f10-168">Free disk space</span></span></p></td>
<td align="left"><p><span data-ttu-id="02f10-169">5 GB</span><span class="sxs-lookup"><span data-stu-id="02f10-169">5 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="02f10-170">5 GB 或以上</span><span class="sxs-lookup"><span data-stu-id="02f10-170">5 GB or greater</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="02f10-171">安裝 MBAM Server 所需的許可權</span><span class="sxs-lookup"><span data-stu-id="02f10-171">Required permissions to install the MBAM Server</span></span>


<span data-ttu-id="02f10-172">若要使用 Configuration Manager 安裝 MBAM，您必須在 Configuration Manager 中擁有具有下表所列許可權的安全性角色的系統管理使用者。</span><span class="sxs-lookup"><span data-stu-id="02f10-172">To install MBAM with Configuration Manager, you must have an administrative user in Configuration Manager who has a security role with the minimum permissions listed in the following table.</span></span> <span data-ttu-id="02f10-173">該表也會顯示您必須擁有的許可權（除了基本的電腦系統管理員許可權之外），才能安裝 MBAM 伺服器。</span><span class="sxs-lookup"><span data-stu-id="02f10-173">The table also shows the rights that you must have, beyond basic computer administrator rights, to install the MBAM Server.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="02f10-174">權限</span><span class="sxs-lookup"><span data-stu-id="02f10-174">Permissions</span></span></th>
<th align="left"><span data-ttu-id="02f10-175">MBAM Server 功能</span><span class="sxs-lookup"><span data-stu-id="02f10-175">MBAM Server Feature</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="02f10-176">SQL 實例登入伺服器角色：-dbcreator-processadmin</span><span class="sxs-lookup"><span data-stu-id="02f10-176">SQL instance Login Server Roles: - dbcreator- processadmin</span></span></p></td>
<td align="left"><p>- <span data-ttu-id="02f10-177">復原資料庫-審核資料庫</span><span class="sxs-lookup"><span data-stu-id="02f10-177">Recovery Database- Audit Database</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="02f10-178">SQL Server Reporting Services 實例許可權：-建立資料夾-發佈報表</span><span class="sxs-lookup"><span data-stu-id="02f10-178">SQL Server Reporting Services instance rights: - Create Folders- Publish Reports</span></span></p></td>
<td align="left"><p>- <span data-ttu-id="02f10-179">System Center Configuration Manager 整合</span><span class="sxs-lookup"><span data-stu-id="02f10-179">System Center Configuration Manager Integration</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="02f10-180">System Center 2012 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="02f10-180">System Center 2012 Configuration Manager</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="02f10-181">權限</span><span class="sxs-lookup"><span data-stu-id="02f10-181">Permissions</span></span></th>
<th align="left"><span data-ttu-id="02f10-182">Configuration Manager 伺服器功能</span><span class="sxs-lookup"><span data-stu-id="02f10-182">Configuration Manager Server Feature</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="02f10-183">Configuration Manager 網站許可權：-讀取</span><span class="sxs-lookup"><span data-stu-id="02f10-183">Configuration Manager site rights:- Read</span></span></p></td>
<td align="left"><p><span data-ttu-id="02f10-184">System Center Configuration Manager 整合</span><span class="sxs-lookup"><span data-stu-id="02f10-184">System Center Configuration Manager integration</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="02f10-185">Configuration Manager 集合許可權：-建立-刪除-已讀-修改-部署設定項目</span><span class="sxs-lookup"><span data-stu-id="02f10-185">Configuration Manager collection rights: - Create- Delete- Read- Modify- Deploy Configuration Items</span></span></p></td>
<td align="left"><p><span data-ttu-id="02f10-186">System Center Configuration Manager 整合</span><span class="sxs-lookup"><span data-stu-id="02f10-186">System Center Configuration Manager integration</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="02f10-187">Configuration Manager 設定專案許可權：-建立-刪除-已讀取</span><span class="sxs-lookup"><span data-stu-id="02f10-187">Configuration Manager configuration item rights: - Create- Delete- Read</span></span></p></td>
<td align="left"><p><span data-ttu-id="02f10-188">System Center Configuration Manager 整合</span><span class="sxs-lookup"><span data-stu-id="02f10-188">System Center Configuration Manager integration</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="02f10-189">Configuration Manager 2007</span><span class="sxs-lookup"><span data-stu-id="02f10-189">Configuration Manager 2007</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="02f10-190">權限</span><span class="sxs-lookup"><span data-stu-id="02f10-190">Permissions</span></span></th>
<th align="left"><span data-ttu-id="02f10-191">Configuration Manager 伺服器功能</span><span class="sxs-lookup"><span data-stu-id="02f10-191">Configuration Manager Server Feature</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="02f10-192">Configuration Manager 網站許可權：-讀取</span><span class="sxs-lookup"><span data-stu-id="02f10-192">Configuration Manager site rights:- Read</span></span></p></td>
<td align="left"><p><span data-ttu-id="02f10-193">System Center Configuration Manager 整合</span><span class="sxs-lookup"><span data-stu-id="02f10-193">System Center Configuration Manager integration</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="02f10-194">Configuration Manager 集合許可權：-建立-Delete-ReadResource</span><span class="sxs-lookup"><span data-stu-id="02f10-194">Configuration Manager collection rights: - Create- Delete- Read- ReadResource</span></span></p></td>
<td align="left"><p><span data-ttu-id="02f10-195">System Center Configuration Manager 整合</span><span class="sxs-lookup"><span data-stu-id="02f10-195">System Center Configuration Manager integration</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="02f10-196">Configuration Manager 設定項目許可權：-建立-刪除-已讀取-發佈</span><span class="sxs-lookup"><span data-stu-id="02f10-196">Configuration Manager configuration item rights: - Create- Delete- Read- Distribute</span></span></p></td>
<td align="left"><p><span data-ttu-id="02f10-197">System Center Configuration Manager 整合</span><span class="sxs-lookup"><span data-stu-id="02f10-197">System Center Configuration Manager integration</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="02f10-198">Configuration Manager 拓撲的 MBAM 功能部署順序</span><span class="sxs-lookup"><span data-stu-id="02f10-198">Order of Deployment of MBAM Features for the Configuration Manager Topology</span></span>


<span data-ttu-id="02f10-199">在 Configuration Manager 伺服器上部署 MBAM 時，您必須以下列順序完成部署工作：</span><span class="sxs-lookup"><span data-stu-id="02f10-199">When deploying MBAM on the Configuration Manager Server, you must complete the deployment tasks in the following order:</span></span>

1.  <span data-ttu-id="02f10-200">在 Configuration Manager 伺服器上編輯 configuration mof 檔案。</span><span class="sxs-lookup"><span data-stu-id="02f10-200">Edit the configuration.mof file on the Configuration Manager Server.</span></span>

2.  <span data-ttu-id="02f10-201">建立或編輯 sms \ _def. mof 檔案 Configuration Manager 伺服器。</span><span class="sxs-lookup"><span data-stu-id="02f10-201">Create or edit the sms\_def.mof file Configuration Manager Server.</span></span>

3.  <span data-ttu-id="02f10-202">在 Configuration Manager 伺服器上安裝 MBAM。</span><span class="sxs-lookup"><span data-stu-id="02f10-202">Install MBAM on the Configuration Manager Server.</span></span>

4.  <span data-ttu-id="02f10-203">在資料庫伺服器上安裝恢復資料庫和審核資料庫。</span><span class="sxs-lookup"><span data-stu-id="02f10-203">Install the Recovery Database and the Audit Database on the Database server.</span></span>

5.  <span data-ttu-id="02f10-204">在 [管理及監視伺服器] 上安裝 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="02f10-204">Install the MBAM features on the Administration and Monitoring Server.</span></span>

## <span data-ttu-id="02f10-205">使用 Configuration Manager 安裝 MBAM 的規劃檢查清單</span><span class="sxs-lookup"><span data-stu-id="02f10-205">Planning Checklist for Installing MBAM with Configuration Manager</span></span>


<span data-ttu-id="02f10-206">此檢查清單列出建議的步驟，以及在規劃使用 Configuration Manager 進行 Microsoft BitLocker 管理及監視部署時要考慮的最高層次專案清單。</span><span class="sxs-lookup"><span data-stu-id="02f10-206">This checklist outlines the recommended steps and a high-level list of items to consider when planning for an Microsoft BitLocker Administration and Monitoring deployment with Configuration Manager.</span></span> <span data-ttu-id="02f10-207">建議您將此檢查清單複製到試算表程式中，然後將它自訂為供您使用。</span><span class="sxs-lookup"><span data-stu-id="02f10-207">It is recommended that you copy this checklist into a spreadsheet program and customize it for your use.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left"><span data-ttu-id="02f10-208">工作</span><span class="sxs-lookup"><span data-stu-id="02f10-208">Task</span></span></th>
<th align="left"><span data-ttu-id="02f10-209">參考資料</span><span class="sxs-lookup"><span data-stu-id="02f10-209">References</span></span></th>
<th align="left"><span data-ttu-id="02f10-210">附註</span><span class="sxs-lookup"><span data-stu-id="02f10-210">Notes</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="02f10-211">請參閱快速入門資訊，這些資訊說明 Configuration Manager 如何與 MBAM 搭配運作，並顯示建議的高層次架構。</span><span class="sxs-lookup"><span data-stu-id="02f10-211">Review the getting started information, which describes how Configuration Manager works with MBAM and shows the recommended high-level architecture.</span></span></p></td>
<td align="left"><p><a href="getting-started---using-mbam-with-configuration-manager.md" data-raw-source="[Getting Started - Using MBAM with Configuration Manager](getting-started---using-mbam-with-configuration-manager.md)"><span data-ttu-id="02f10-212">開始使用 - 將 MBAM 與設定管理員搭配使用</span><span class="sxs-lookup"><span data-stu-id="02f10-212">Getting Started - Using MBAM with Configuration Manager</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="02f10-213">請查看規劃資訊，其中描述部署的先決條件、支援的設定、所需的許可權，以及每個功能的部署順序。</span><span class="sxs-lookup"><span data-stu-id="02f10-213">Review the planning information, which describes the deployment prerequisites, supported configurations, required permissions, and deployment order for each feature.</span></span></p></td>
<td align="left"><p><span data-ttu-id="02f10-214">規劃使用設定管理員進行 MBAM 部署</span><span class="sxs-lookup"><span data-stu-id="02f10-214">Planning to Deploy MBAM with Configuration Manager</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="02f10-215">規劃及設定 MBAM 群組原則需求。</span><span class="sxs-lookup"><span data-stu-id="02f10-215">Plan for and configure MBAM Group Policy requirements.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-20-group-policy-requirements-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Group Policy Requirements](planning-for-mbam-20-group-policy-requirements-mbam-2.md)"><span data-ttu-id="02f10-216">MBAM 2.0 群組原則需求規劃</span><span class="sxs-lookup"><span data-stu-id="02f10-216">Planning for MBAM 2.0 Group Policy Requirements</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="02f10-217">規劃及建立必要的 Active Directory 網域服務安全性群組，並規劃 MBAM 的本地安全性群組成員資格需求。</span><span class="sxs-lookup"><span data-stu-id="02f10-217">Plan for and create necessary Active Directory Domain Services security groups and plan for MBAM local security group membership requirements.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-20-administrator-roles-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Administrator Roles](planning-for-mbam-20-administrator-roles-mbam-2.md)"><span data-ttu-id="02f10-218">MBAM 2.0 系統管理員角色規劃</span><span class="sxs-lookup"><span data-stu-id="02f10-218">Planning for MBAM 2.0 Administrator Roles</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="02f10-219">規劃部署 MBAM 用戶端部署。</span><span class="sxs-lookup"><span data-stu-id="02f10-219">Plan for deploying MBAM Client deployment.</span></span></p></td>
<td align="left"><p><a href="planning-for-mbam-20-client-deployment-mbam-2.md" data-raw-source="[Planning for MBAM 2.0 Client Deployment](planning-for-mbam-20-client-deployment-mbam-2.md)"><span data-ttu-id="02f10-220">MBAM 2.0 用戶端部署規劃</span><span class="sxs-lookup"><span data-stu-id="02f10-220">Planning for MBAM 2.0 Client Deployment</span></span></a></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="02f10-221">相關主題</span><span class="sxs-lookup"><span data-stu-id="02f10-221">Related topics</span></span>


[<span data-ttu-id="02f10-222">使用 MBAM 搭配 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="02f10-222">Using MBAM with Configuration Manager</span></span>](using-mbam-with-configuration-manager.md)









