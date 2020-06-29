---
title: MBAM 2.0 支援的組態
description: MBAM 2.0 支援的組態
author: dansimp
ms.assetid: dca63391-39fe-4273-a570-76d0a2f8a0fd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 8f314adcf818c1bdb17b0b239a7469f97fa849e4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810238"
---
# <span data-ttu-id="23c70-103">MBAM 2.0 支援的組態</span><span class="sxs-lookup"><span data-stu-id="23c70-103">MBAM 2.0 Supported Configurations</span></span>


<span data-ttu-id="23c70-104">本主題透過使用獨立拓朴，指定在您的環境中安裝並執行 Microsoft BitLocker 管理和監控（MBAM）2.0 的需求。</span><span class="sxs-lookup"><span data-stu-id="23c70-104">This topic specifies the requirements to install and run Microsoft BitLocker Administration and Monitoring (MBAM) 2.0 in your environment by using the Stand-alone topology.</span></span> <span data-ttu-id="23c70-105">如需適用于日後發行的支援設定，請參閱適用版本的檔。</span><span class="sxs-lookup"><span data-stu-id="23c70-105">For supported configurations that apply to later releases, see the documentation for the applicable release.</span></span>

<span data-ttu-id="23c70-106">如果您打算使用 Configuration Manager 拓撲來安裝 MBAM 2.0，並想要查看系統需求清單，請參閱[規劃使用 Configuration Manager 部署 MBAM](planning-to-deploy-mbam-with-configuration-manager-2.md)。</span><span class="sxs-lookup"><span data-stu-id="23c70-106">If you plan to install MBAM 2.0 by using the Configuration Manager topology and want to review a list of the system requirements, see [Planning to Deploy MBAM with Configuration Manager](planning-to-deploy-mbam-with-configuration-manager-2.md).</span></span>

<span data-ttu-id="23c70-107">在生產環境中執行 MBAM 的建議設定是使用兩個伺服器（視您的可伸縮性需求而定）。</span><span class="sxs-lookup"><span data-stu-id="23c70-107">The recommended configuration for running MBAM in a production environment is with two servers, depending on your scalability requirements.</span></span> <span data-ttu-id="23c70-108">此設定最多可支援 200000 MBAM 用戶端。</span><span class="sxs-lookup"><span data-stu-id="23c70-108">This configuration supports up to 200,000 MBAM clients.</span></span> <span data-ttu-id="23c70-109">如需獨立 MBAM 伺服器基礎結構的影像和描述，請參閱[適用于 MBAM 2.0 的高層次架構](high-level-architecture-for-mbam-20-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="23c70-109">For an image and descriptions of the Stand-alone MBAM server infrastructure, see [High-Level Architecture for MBAM 2.0](high-level-architecture-for-mbam-20-mbam-2.md).</span></span>

<span data-ttu-id="23c70-110">**記事** Microsoft 提供目前 service pack 的支援，在某些情況下，也是最前面的 service pack。</span><span class="sxs-lookup"><span data-stu-id="23c70-110">**Note** Microsoft provides support for the current service pack and, in some cases, the immediately preceding service pack.</span></span> <span data-ttu-id="23c70-111">若要尋找您產品的支援時程表，請參閱[支援的生命週期服務套件](https://go.microsoft.com/fwlink/p/?LinkId=31975)。</span><span class="sxs-lookup"><span data-stu-id="23c70-111">To find the support timelines for your product, see the [Lifecycle Supported Service Packs](https://go.microsoft.com/fwlink/p/?LinkId=31975).</span></span> <span data-ttu-id="23c70-112">如需 Microsoft 支援週期原則的其他相關資訊，請參閱[Microsoft 支援週期支援原則常見問題](https://go.microsoft.com/fwlink/p/?LinkId=31976)。</span><span class="sxs-lookup"><span data-stu-id="23c70-112">For additional information about Microsoft Support Lifecycle Policy, see [Microsoft Support Lifecycle Support Policy FAQ](https://go.microsoft.com/fwlink/p/?LinkId=31976).</span></span>

 

## <a href="" id="---------mbam-server-system-requirements"></a> <span data-ttu-id="23c70-113">MBAM 伺服器系統需求</span><span class="sxs-lookup"><span data-stu-id="23c70-113">MBAM Server System Requirements</span></span>


### <span data-ttu-id="23c70-114">伺服器作業系統需求</span><span class="sxs-lookup"><span data-stu-id="23c70-114">Server Operating System Requirements</span></span>

<span data-ttu-id="23c70-115">下表列出 Microsoft BitLocker 系統管理和監視伺服器安裝支援的作業系統。</span><span class="sxs-lookup"><span data-stu-id="23c70-115">The following table lists the operating systems that are supported for the Microsoft BitLocker Administration and Monitoring Server installation.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="23c70-116">作業系統</span><span class="sxs-lookup"><span data-stu-id="23c70-116">Operating system</span></span></th>
<th align="left"><span data-ttu-id="23c70-117">版本</span><span class="sxs-lookup"><span data-stu-id="23c70-117">Edition</span></span></th>
<th align="left"><span data-ttu-id="23c70-118">Service pack</span><span class="sxs-lookup"><span data-stu-id="23c70-118">Service pack</span></span></th>
<th align="left"><span data-ttu-id="23c70-119">系統架構</span><span class="sxs-lookup"><span data-stu-id="23c70-119">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="23c70-120">WindowsServer2008 R2</span><span class="sxs-lookup"><span data-stu-id="23c70-120">WindowsServer2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="23c70-121">標準版、企業版或資料中心版本</span><span class="sxs-lookup"><span data-stu-id="23c70-121">Standard, Enterprise, or Datacenter Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="23c70-122">SP1</span><span class="sxs-lookup"><span data-stu-id="23c70-122">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="23c70-123">64 位元</span><span class="sxs-lookup"><span data-stu-id="23c70-123">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="23c70-124">WindowsServer2012</span><span class="sxs-lookup"><span data-stu-id="23c70-124">WindowsServer2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="23c70-125">標準版或資料中心版本</span><span class="sxs-lookup"><span data-stu-id="23c70-125">Standard or Datacenter Edition</span></span></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="23c70-126">64 位元</span><span class="sxs-lookup"><span data-stu-id="23c70-126">64-bit</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="23c70-127">**記事** 不支援在網網域控制站電腦上安裝 MBAM 服務、報表或資料庫。</span><span class="sxs-lookup"><span data-stu-id="23c70-127">**Note** There is no support for installing MBAM services, reports, or databases on a domain controller computer.</span></span>

 

### <a href="" id="server-processor--ram--and-disk-space-requirements-"></a><span data-ttu-id="23c70-128">伺服器處理器、RAM 與磁碟空間需求</span><span class="sxs-lookup"><span data-stu-id="23c70-128">Server Processor, RAM, and Disk Space Requirements</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="23c70-129">硬體元件</span><span class="sxs-lookup"><span data-stu-id="23c70-129">Hardware component</span></span></th>
<th align="left"><span data-ttu-id="23c70-130">最低需求</span><span class="sxs-lookup"><span data-stu-id="23c70-130">Minimum requirement</span></span></th>
<th align="left"><span data-ttu-id="23c70-131">建議的需求</span><span class="sxs-lookup"><span data-stu-id="23c70-131">Recommended requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="23c70-132">處理者</span><span class="sxs-lookup"><span data-stu-id="23c70-132">Processor</span></span></p></td>
<td align="left"><p><span data-ttu-id="23c70-133">2.33 GHz</span><span class="sxs-lookup"><span data-stu-id="23c70-133">2.33 GHz</span></span></p></td>
<td align="left"><p><span data-ttu-id="23c70-134">2.33 GHz 或以上</span><span class="sxs-lookup"><span data-stu-id="23c70-134">2.33 GHz or greater</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="23c70-135">RAM</span><span class="sxs-lookup"><span data-stu-id="23c70-135">RAM</span></span></p></td>
<td align="left"><p><span data-ttu-id="23c70-136">8 GB</span><span class="sxs-lookup"><span data-stu-id="23c70-136">8 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="23c70-137">12 GB</span><span class="sxs-lookup"><span data-stu-id="23c70-137">12 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="23c70-138">可用磁碟空間</span><span class="sxs-lookup"><span data-stu-id="23c70-138">Free disk space</span></span></p></td>
<td align="left"><p><span data-ttu-id="23c70-139">1 GB</span><span class="sxs-lookup"><span data-stu-id="23c70-139">1 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="23c70-140">2 GB</span><span class="sxs-lookup"><span data-stu-id="23c70-140">2 GB</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="sql-server-database-requirements-"></a><span data-ttu-id="23c70-141">SQLServer 資料庫需求</span><span class="sxs-lookup"><span data-stu-id="23c70-141">SQLServer Database Requirements</span></span>

<span data-ttu-id="23c70-142">下表列出系統管理與監視伺服器功能安裝支援的 SQLServer 版本，其中包括復原資料庫、合規性和審核資料庫，以及合規性和審核報告。</span><span class="sxs-lookup"><span data-stu-id="23c70-142">The following table lists the SQLServer versions that are supported for the Administration and Monitoring Server feature installation, which includes the Recovery Database, Compliance and Audit Database, and Compliance and Audit Reports.</span></span> <span data-ttu-id="23c70-143">資料庫還需要安裝 SQL Server 管理工具。</span><span class="sxs-lookup"><span data-stu-id="23c70-143">The databases additionally require the installation of SQL Server Management Tools.</span></span>

<span data-ttu-id="23c70-144">**記事** MBAM 本身不支援 SQL 群集、鏡像或可用性群組。</span><span class="sxs-lookup"><span data-stu-id="23c70-144">**Note** MBAM does not natively support SQL clustering, mirroring, or Availability Groups.</span></span> <span data-ttu-id="23c70-145">若要安裝資料庫，您必須在獨立的 SQL Server 上執行 MBAM 伺服器安裝。</span><span class="sxs-lookup"><span data-stu-id="23c70-145">To install the databases, you must run the MBAM Server installation on a stand-alone SQL server.</span></span>

 

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="23c70-146">SQL Server 版本</span><span class="sxs-lookup"><span data-stu-id="23c70-146">SQL Server version</span></span></th>
<th align="left"><span data-ttu-id="23c70-147">版本</span><span class="sxs-lookup"><span data-stu-id="23c70-147">Edition</span></span></th>
<th align="left"><span data-ttu-id="23c70-148">Service pack</span><span class="sxs-lookup"><span data-stu-id="23c70-148">Service pack</span></span></th>
<th align="left"><span data-ttu-id="23c70-149">系統架構</span><span class="sxs-lookup"><span data-stu-id="23c70-149">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="23c70-150">MicrosoftSQLServer2008 R2</span><span class="sxs-lookup"><span data-stu-id="23c70-150">MicrosoftSQLServer2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="23c70-151">標準版、企業版或資料中心版本</span><span class="sxs-lookup"><span data-stu-id="23c70-151">Standard, Enterprise, or Datacenter Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="23c70-152">SP1</span><span class="sxs-lookup"><span data-stu-id="23c70-152">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="23c70-153">64 位元</span><span class="sxs-lookup"><span data-stu-id="23c70-153">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="23c70-154">MicrosoftSQLServer2012</span><span class="sxs-lookup"><span data-stu-id="23c70-154">MicrosoftSQLServer2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="23c70-155">標準版、企業版或資料中心版本</span><span class="sxs-lookup"><span data-stu-id="23c70-155">Standard, Enterprise, or Datacenter Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="23c70-156">SP1</span><span class="sxs-lookup"><span data-stu-id="23c70-156">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="23c70-157">64 位元</span><span class="sxs-lookup"><span data-stu-id="23c70-157">64-bit</span></span></p></td>
</tr>
</tbody>
</table>

 

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="23c70-158">硬體元件</span><span class="sxs-lookup"><span data-stu-id="23c70-158">Hardware component</span></span></th>
<th align="left"><span data-ttu-id="23c70-159">最低需求</span><span class="sxs-lookup"><span data-stu-id="23c70-159">Minimum requirement</span></span></th>
<th align="left"><span data-ttu-id="23c70-160">建議的需求</span><span class="sxs-lookup"><span data-stu-id="23c70-160">Recommended requirement</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="23c70-161">處理者</span><span class="sxs-lookup"><span data-stu-id="23c70-161">Processor</span></span></p></td>
<td align="left"><p><span data-ttu-id="23c70-162">2.33 GHz</span><span class="sxs-lookup"><span data-stu-id="23c70-162">2.33 GHz</span></span></p></td>
<td align="left"><p><span data-ttu-id="23c70-163">2.33 GHz 或以上</span><span class="sxs-lookup"><span data-stu-id="23c70-163">2.33 GHz or greater</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="23c70-164">RAM</span><span class="sxs-lookup"><span data-stu-id="23c70-164">RAM</span></span></p></td>
<td align="left"><p><span data-ttu-id="23c70-165">8 GB</span><span class="sxs-lookup"><span data-stu-id="23c70-165">8 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="23c70-166">12 GB</span><span class="sxs-lookup"><span data-stu-id="23c70-166">12 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="23c70-167">可用磁碟空間</span><span class="sxs-lookup"><span data-stu-id="23c70-167">Free disk space</span></span></p></td>
<td align="left"><p><span data-ttu-id="23c70-168">5 GB</span><span class="sxs-lookup"><span data-stu-id="23c70-168">5 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="23c70-169">5 GB 或以上</span><span class="sxs-lookup"><span data-stu-id="23c70-169">5 GB or greater</span></span></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="---------mbam-client-system-requirements"></a> <span data-ttu-id="23c70-170">MBAM 用戶端系統需求</span><span class="sxs-lookup"><span data-stu-id="23c70-170">MBAM Client System Requirements</span></span>


### <span data-ttu-id="23c70-171">用戶端作業系統需求</span><span class="sxs-lookup"><span data-stu-id="23c70-171">Client Operating System Requirements</span></span>

<span data-ttu-id="23c70-172">下表列出 Microsoft BitLocker 系統管理和監視用戶端安裝支援的作業系統。</span><span class="sxs-lookup"><span data-stu-id="23c70-172">The following table lists the operating systems that are supported for Microsoft BitLocker Administration and Monitoring Client installation.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="23c70-173">作業系統</span><span class="sxs-lookup"><span data-stu-id="23c70-173">Operating system</span></span></th>
<th align="left"><span data-ttu-id="23c70-174">版本</span><span class="sxs-lookup"><span data-stu-id="23c70-174">Edition</span></span></th>
<th align="left"><span data-ttu-id="23c70-175">Service pack</span><span class="sxs-lookup"><span data-stu-id="23c70-175">Service pack</span></span></th>
<th align="left"><span data-ttu-id="23c70-176">系統架構</span><span class="sxs-lookup"><span data-stu-id="23c70-176">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="23c70-177">Windows7</span><span class="sxs-lookup"><span data-stu-id="23c70-177">Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="23c70-178">企業版或旗艦版</span><span class="sxs-lookup"><span data-stu-id="23c70-178">Enterprise or Ultimate Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="23c70-179">SP1</span><span class="sxs-lookup"><span data-stu-id="23c70-179">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="23c70-180">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="23c70-180">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="23c70-181">Windows8</span><span class="sxs-lookup"><span data-stu-id="23c70-181">Windows 8</span></span></p></td>
<td align="left"><p><span data-ttu-id="23c70-182">企業版</span><span class="sxs-lookup"><span data-stu-id="23c70-182">Enterprise Edition</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="23c70-183">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="23c70-183">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="23c70-184">Windows To Go</span><span class="sxs-lookup"><span data-stu-id="23c70-184">Windows To Go</span></span></p></td>
<td align="left"><p><span data-ttu-id="23c70-185">Windows 8 企業版</span><span class="sxs-lookup"><span data-stu-id="23c70-185">Windows 8 Enterprise Edition</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="23c70-186">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="23c70-186">32-bit or 64-bit</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="client-ram-requirements-"></a><span data-ttu-id="23c70-187">用戶端 RAM 需求</span><span class="sxs-lookup"><span data-stu-id="23c70-187">Client RAM Requirements</span></span>

<span data-ttu-id="23c70-188">Microsoft BitLocker 管理與監視用戶端安裝沒有任何 RAM 需求。</span><span class="sxs-lookup"><span data-stu-id="23c70-188">There are no RAM requirements that are specific to the Microsoft BitLocker Administration and Monitoring Client installation.</span></span>

## <a href="" id="---------mbam-group-policy-system-requirements"></a> <span data-ttu-id="23c70-189">MBAM 群組原則系統需求</span><span class="sxs-lookup"><span data-stu-id="23c70-189">MBAM Group Policy System Requirements</span></span>


<span data-ttu-id="23c70-190">下表列出 Microsoft BitLocker 管理和監視群群組原則範本安裝所支援的作業系統。</span><span class="sxs-lookup"><span data-stu-id="23c70-190">The following table lists the operating systems that are supported for Microsoft BitLocker Administration and Monitoring Group Policy template installation.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="23c70-191">作業系統</span><span class="sxs-lookup"><span data-stu-id="23c70-191">Operating system</span></span></th>
<th align="left"><span data-ttu-id="23c70-192">版本</span><span class="sxs-lookup"><span data-stu-id="23c70-192">Edition</span></span></th>
<th align="left"><span data-ttu-id="23c70-193">Service pack</span><span class="sxs-lookup"><span data-stu-id="23c70-193">Service pack</span></span></th>
<th align="left"><span data-ttu-id="23c70-194">系統架構</span><span class="sxs-lookup"><span data-stu-id="23c70-194">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="23c70-195">Windows7</span><span class="sxs-lookup"><span data-stu-id="23c70-195">Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="23c70-196">企業版或旗艦版</span><span class="sxs-lookup"><span data-stu-id="23c70-196">Enterprise, or Ultimate Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="23c70-197">SP1</span><span class="sxs-lookup"><span data-stu-id="23c70-197">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="23c70-198">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="23c70-198">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="23c70-199">Windows8</span><span class="sxs-lookup"><span data-stu-id="23c70-199">Windows 8</span></span></p></td>
<td align="left"><p><span data-ttu-id="23c70-200">企業版</span><span class="sxs-lookup"><span data-stu-id="23c70-200">Enterprise Edition</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="23c70-201">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="23c70-201">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="23c70-202">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="23c70-202">Windows Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="23c70-203">標準版、企業版或資料中心版本</span><span class="sxs-lookup"><span data-stu-id="23c70-203">Standard, Enterprise, or Datacenter Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="23c70-204">SP1</span><span class="sxs-lookup"><span data-stu-id="23c70-204">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="23c70-205">64 位元</span><span class="sxs-lookup"><span data-stu-id="23c70-205">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="23c70-206">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="23c70-206">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="23c70-207">標準版或資料中心版本</span><span class="sxs-lookup"><span data-stu-id="23c70-207">Standard or Datacenter Edition</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="23c70-208">64 位元</span><span class="sxs-lookup"><span data-stu-id="23c70-208">64-bit</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="23c70-209">相關主題</span><span class="sxs-lookup"><span data-stu-id="23c70-209">Related topics</span></span>


[<span data-ttu-id="23c70-210">規劃部署 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="23c70-210">Planning to Deploy MBAM 2.0</span></span>](planning-to-deploy-mbam-20-mbam-2.md)

[<span data-ttu-id="23c70-211">MBAM 2.0 部署必要條件</span><span class="sxs-lookup"><span data-stu-id="23c70-211">MBAM 2.0 Deployment Prerequisites</span></span>](mbam-20-deployment-prerequisites-mbam-2.md)

 

 





