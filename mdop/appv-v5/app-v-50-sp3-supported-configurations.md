---
title: App-V 5.0 SP3 支援的組態
description: App-V 5.0 SP3 支援的組態
author: dansimp
ms.assetid: 08ced79a-0ed3-43c3-82e7-de01c1f33e81
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: b5a8858c703add3dc84c7eed4f62aa97e60ec9b0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800682"
---
# <span data-ttu-id="4a6a2-103">App-V 5.0 SP3 支援的組態</span><span class="sxs-lookup"><span data-stu-id="4a6a2-103">App-V 5.0 SP3 Supported Configurations</span></span>


<span data-ttu-id="4a6a2-104">本主題指定在您的環境中安裝並執行 Microsoft Application Virtualization （App-v） 5.0 SP3 的需求。</span><span class="sxs-lookup"><span data-stu-id="4a6a2-104">This topic specifies the requirements to install and run Microsoft Application Virtualization (App-V) 5.0 SP3 in your environment.</span></span>

## <span data-ttu-id="4a6a2-105">App-v Server 系統需求</span><span class="sxs-lookup"><span data-stu-id="4a6a2-105">App-V Server system requirements</span></span>


<span data-ttu-id="4a6a2-106">本節列出所有應用程式 V 伺服器元件的作業系統和硬體需求。</span><span class="sxs-lookup"><span data-stu-id="4a6a2-106">This section lists the operating system and hardware requirements for all of the App-V Server components.</span></span>

### <span data-ttu-id="4a6a2-107">不支援的 App-V 5.0 SP3 伺服器案例</span><span class="sxs-lookup"><span data-stu-id="4a6a2-107">Unsupported App-V 5.0 SP3 Server scenarios</span></span>

<span data-ttu-id="4a6a2-108">App-V 5.0 SP3 伺服器不支援下列案例：</span><span class="sxs-lookup"><span data-stu-id="4a6a2-108">The App-V 5.0 SP3 Server does not support the following scenarios:</span></span>

-   <span data-ttu-id="4a6a2-109">部署到執行 Microsoft Windows Server Core 的電腦。</span><span class="sxs-lookup"><span data-stu-id="4a6a2-109">Deployment to a computer that runs Microsoft Windows Server Core.</span></span>

-   <span data-ttu-id="4a6a2-110">部署到執行舊版 App-V 5.0 SP3 Server 元件的電腦。</span><span class="sxs-lookup"><span data-stu-id="4a6a2-110">Deployment to a computer that runs a previous version of App-V 5.0 SP3 Server components.</span></span> <span data-ttu-id="4a6a2-111">您可以只使用 App-v 4.5 輕型流式處理伺服器（LWS）伺服器來安裝 App-v 5.0 SP3。</span><span class="sxs-lookup"><span data-stu-id="4a6a2-111">You can install App-V 5.0 SP3 side by side with the App-V4.5 Lightweight Streaming Server (LWS) server only.</span></span> <span data-ttu-id="4a6a2-112">不支援使用 app-v 4.5 應用程式虛擬化管理服務（HWS）伺服器並行部署 app-v。</span><span class="sxs-lookup"><span data-stu-id="4a6a2-112">Deployment of App-V side by side with the App-V 4.5 Application Virtualization Management Service (HWS) server is not supported.</span></span>

-   <span data-ttu-id="4a6a2-113">部署到執行 Microsoft SQL Server Express edition 的電腦。</span><span class="sxs-lookup"><span data-stu-id="4a6a2-113">Deployment to a computer that runs Microsoft SQL Server Express edition.</span></span>

-   <span data-ttu-id="4a6a2-114">管理伺服器資料庫或報告資料庫的遠端部署。</span><span class="sxs-lookup"><span data-stu-id="4a6a2-114">Remote deployment of the management server database or the reporting database.</span></span> <span data-ttu-id="4a6a2-115">您必須直接在執行 Microsoft SQL Server 的電腦上執行安裝程式。</span><span class="sxs-lookup"><span data-stu-id="4a6a2-115">You must run the installer directly on the computer that is running Microsoft SQL Server.</span></span>

-   <span data-ttu-id="4a6a2-116">部署到網網域控制站。</span><span class="sxs-lookup"><span data-stu-id="4a6a2-116">Deployment to a domain controller.</span></span>

-   <span data-ttu-id="4a6a2-117">短路徑。</span><span class="sxs-lookup"><span data-stu-id="4a6a2-117">Short paths.</span></span> <span data-ttu-id="4a6a2-118">如果您打算使用短路徑，您必須建立新的卷。</span><span class="sxs-lookup"><span data-stu-id="4a6a2-118">If you plan to use a short path, you must create a new volume.</span></span>

### <span data-ttu-id="4a6a2-119">管理伺服器作業系統需求</span><span class="sxs-lookup"><span data-stu-id="4a6a2-119">Management server operating system requirements</span></span>

<span data-ttu-id="4a6a2-120">下表列出 App-V 5.0 SP3 管理伺服器安裝所支援的作業系統。</span><span class="sxs-lookup"><span data-stu-id="4a6a2-120">The following table lists the operating systems that are supported for the App-V 5.0 SP3 Management server installation.</span></span>

<span data-ttu-id="4a6a2-121">**記事** Microsoft 提供目前 service pack 的支援，在某些情況下，也是最前面的 service pack。</span><span class="sxs-lookup"><span data-stu-id="4a6a2-121">**Note** Microsoft provides support for the current service pack and, in some cases, the immediately preceding service pack.</span></span> <span data-ttu-id="4a6a2-122">若要尋找您產品的支援時程表，請參閱[支援的生命週期服務套件](https://go.microsoft.com/fwlink/p/?LinkId=31975)。</span><span class="sxs-lookup"><span data-stu-id="4a6a2-122">To find the support timelines for your product, see the [Lifecycle Supported Service Packs](https://go.microsoft.com/fwlink/p/?LinkId=31975).</span></span> <span data-ttu-id="4a6a2-123">如需詳細資訊，請參閱[Microsoft 支援週期支援原則的常見問題](https://go.microsoft.com/fwlink/p/?LinkId=31976)。</span><span class="sxs-lookup"><span data-stu-id="4a6a2-123">See [Microsoft Support Lifecycle Support Policy FAQ](https://go.microsoft.com/fwlink/p/?LinkId=31976) for more information.</span></span>

 

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4a6a2-124">作業系統</span><span class="sxs-lookup"><span data-stu-id="4a6a2-124">Operating system</span></span></th>
<th align="left"><span data-ttu-id="4a6a2-125">Service Pack</span><span class="sxs-lookup"><span data-stu-id="4a6a2-125">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="4a6a2-126">系統架構</span><span class="sxs-lookup"><span data-stu-id="4a6a2-126">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4a6a2-127">Microsoft Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="4a6a2-127">Microsoft Windows Server 2012 R2</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="4a6a2-128">64 位元</span><span class="sxs-lookup"><span data-stu-id="4a6a2-128">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4a6a2-129">Microsoft Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="4a6a2-129">Microsoft Windows Server 2012</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="4a6a2-130">64 位元</span><span class="sxs-lookup"><span data-stu-id="4a6a2-130">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4a6a2-131">Microsoft Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="4a6a2-131">Microsoft Windows Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="4a6a2-132">SP1</span><span class="sxs-lookup"><span data-stu-id="4a6a2-132">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="4a6a2-133">64 位元</span><span class="sxs-lookup"><span data-stu-id="4a6a2-133">64-bit</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="4a6a2-134">**重要** 不支援將管理伺服器角色部署到已啟用遠端桌面共用（RDS）的電腦。</span><span class="sxs-lookup"><span data-stu-id="4a6a2-134">**Important** Deployment of the Management server role to a computer with Remote Desktop Sharing (RDS) enabled is not supported.</span></span>

 

### <a href="" id="management-server-hardware-requirements-"></a><span data-ttu-id="4a6a2-135">管理伺服器硬體需求</span><span class="sxs-lookup"><span data-stu-id="4a6a2-135">Management server hardware requirements</span></span>

-   <span data-ttu-id="4a6a2-136">處理器-1.4 GHz 或更快的64位（x64）處理器</span><span class="sxs-lookup"><span data-stu-id="4a6a2-136">Processor—1.4 GHz or faster, 64-bit (x64) processor</span></span>

-   <span data-ttu-id="4a6a2-137">RAM-1 GB RAM （64位）</span><span class="sxs-lookup"><span data-stu-id="4a6a2-137">RAM—1 GB RAM (64-bit)</span></span>

-   <span data-ttu-id="4a6a2-138">磁碟空間-200 MB 可用硬碟空間，不含內容目錄</span><span class="sxs-lookup"><span data-stu-id="4a6a2-138">Disk space—200 MB available hard disk space, not including the content directory</span></span>

### <span data-ttu-id="4a6a2-139">管理伺服器資料庫需求</span><span class="sxs-lookup"><span data-stu-id="4a6a2-139">Management server database requirements</span></span>

<span data-ttu-id="4a6a2-140">下表列出 App-V 5.0 SP3 管理資料庫安裝所支援的 SQL Server 版本。</span><span class="sxs-lookup"><span data-stu-id="4a6a2-140">The following table lists the SQL Server versions that are supported for the App-V 5.0 SP3 Management database installation.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4a6a2-141">SQL Server 版本</span><span class="sxs-lookup"><span data-stu-id="4a6a2-141">SQL Server version</span></span></th>
<th align="left"><span data-ttu-id="4a6a2-142">Service pack</span><span class="sxs-lookup"><span data-stu-id="4a6a2-142">Service pack</span></span></th>
<th align="left"><span data-ttu-id="4a6a2-143">系統架構</span><span class="sxs-lookup"><span data-stu-id="4a6a2-143">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4a6a2-144">Microsoft SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="4a6a2-144">Microsoft SQL Server 2014</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="4a6a2-145">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="4a6a2-145">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4a6a2-146">Microsoft SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="4a6a2-146">Microsoft SQL Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="4a6a2-147">SP2</span><span class="sxs-lookup"><span data-stu-id="4a6a2-147">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="4a6a2-148">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="4a6a2-148">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4a6a2-149">Microsoft SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="4a6a2-149">Microsoft SQL Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="4a6a2-150">SP3</span><span class="sxs-lookup"><span data-stu-id="4a6a2-150">SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="4a6a2-151">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="4a6a2-151">32-bit or 64-bit</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="4a6a2-152">發佈伺服器作業系統需求</span><span class="sxs-lookup"><span data-stu-id="4a6a2-152">Publishing server operating system requirements</span></span>

<span data-ttu-id="4a6a2-153">下表列出 App-V 5.0 SP3 發佈伺服器安裝所支援的作業系統。</span><span class="sxs-lookup"><span data-stu-id="4a6a2-153">The following table lists the operating systems that are supported for the App-V 5.0 SP3 Publishing server installation.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4a6a2-154">作業系統</span><span class="sxs-lookup"><span data-stu-id="4a6a2-154">Operating system</span></span></th>
<th align="left"><span data-ttu-id="4a6a2-155">Service Pack</span><span class="sxs-lookup"><span data-stu-id="4a6a2-155">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="4a6a2-156">系統架構</span><span class="sxs-lookup"><span data-stu-id="4a6a2-156">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4a6a2-157">Microsoft Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="4a6a2-157">Microsoft Windows Server 2012 R2</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="4a6a2-158">64 位元</span><span class="sxs-lookup"><span data-stu-id="4a6a2-158">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4a6a2-159">Microsoft Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="4a6a2-159">Microsoft Windows Server 2012</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="4a6a2-160">64 位元</span><span class="sxs-lookup"><span data-stu-id="4a6a2-160">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4a6a2-161">Microsoft Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="4a6a2-161">Microsoft Windows Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="4a6a2-162">SP1</span><span class="sxs-lookup"><span data-stu-id="4a6a2-162">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="4a6a2-163">64 位元</span><span class="sxs-lookup"><span data-stu-id="4a6a2-163">64-bit</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="publishing-server-hardware-requirements-"></a><span data-ttu-id="4a6a2-164">發佈伺服器硬體需求</span><span class="sxs-lookup"><span data-stu-id="4a6a2-164">Publishing server hardware requirements</span></span>

<span data-ttu-id="4a6a2-165">App-V 不會在 Windows 伺服器以外的其他需求中新增其他需求。</span><span class="sxs-lookup"><span data-stu-id="4a6a2-165">App-V adds no additional requirements beyond those of Windows Server.</span></span>

-   <span data-ttu-id="4a6a2-166">處理器-1.4 GHz 或更快的64位（x64）處理器</span><span class="sxs-lookup"><span data-stu-id="4a6a2-166">Processor—1.4 GHz or faster, 64-bit (x64) processor</span></span>

-   <span data-ttu-id="4a6a2-167">RAM-2 GB RAM （64位）</span><span class="sxs-lookup"><span data-stu-id="4a6a2-167">RAM—2 GB RAM (64-bit)</span></span>

-   <span data-ttu-id="4a6a2-168">磁碟空間-200 MB 可用硬碟空間，不含內容目錄</span><span class="sxs-lookup"><span data-stu-id="4a6a2-168">Disk space—200 MB available hard disk space, not including the content directory</span></span>

### <span data-ttu-id="4a6a2-169">報表伺服器作業系統需求</span><span class="sxs-lookup"><span data-stu-id="4a6a2-169">Reporting server operating system requirements</span></span>

<span data-ttu-id="4a6a2-170">下表列出 App-V 5.0 SP3 報表服務器安裝所支援的作業系統。</span><span class="sxs-lookup"><span data-stu-id="4a6a2-170">The following table lists the operating systems that are supported for the App-V 5.0 SP3 Reporting server installation.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4a6a2-171">作業系統</span><span class="sxs-lookup"><span data-stu-id="4a6a2-171">Operating system</span></span></th>
<th align="left"><span data-ttu-id="4a6a2-172">Service Pack</span><span class="sxs-lookup"><span data-stu-id="4a6a2-172">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="4a6a2-173">系統架構</span><span class="sxs-lookup"><span data-stu-id="4a6a2-173">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4a6a2-174">Microsoft Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="4a6a2-174">Microsoft Windows Server 2012 R2</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="4a6a2-175">64 位元</span><span class="sxs-lookup"><span data-stu-id="4a6a2-175">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4a6a2-176">Microsoft Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="4a6a2-176">Microsoft Windows Server 2012</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="4a6a2-177">64 位元</span><span class="sxs-lookup"><span data-stu-id="4a6a2-177">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4a6a2-178">Microsoft Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="4a6a2-178">Microsoft Windows Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="4a6a2-179">SP1</span><span class="sxs-lookup"><span data-stu-id="4a6a2-179">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="4a6a2-180">64 位元</span><span class="sxs-lookup"><span data-stu-id="4a6a2-180">64-bit</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="reporting-server-hardware-requirements-"></a><span data-ttu-id="4a6a2-181">報表服務器硬體需求</span><span class="sxs-lookup"><span data-stu-id="4a6a2-181">Reporting server hardware requirements</span></span>

<span data-ttu-id="4a6a2-182">App-V 不會在 Windows 伺服器以外的其他需求中新增其他需求。</span><span class="sxs-lookup"><span data-stu-id="4a6a2-182">App-V adds no additional requirements beyond those of Windows Server.</span></span>

-   <span data-ttu-id="4a6a2-183">處理器-1.4 GHz 或更快的64位（x64）處理器</span><span class="sxs-lookup"><span data-stu-id="4a6a2-183">Processor—1.4 GHz or faster, 64-bit (x64) processor</span></span>

-   <span data-ttu-id="4a6a2-184">RAM-2 GB RAM （64位）</span><span class="sxs-lookup"><span data-stu-id="4a6a2-184">RAM—2 GB RAM (64-bit)</span></span>

-   <span data-ttu-id="4a6a2-185">磁碟空間-200 MB 可用硬碟空間</span><span class="sxs-lookup"><span data-stu-id="4a6a2-185">Disk space—200 MB available hard disk space</span></span>

### <span data-ttu-id="4a6a2-186">報表伺服器資料庫需求</span><span class="sxs-lookup"><span data-stu-id="4a6a2-186">Reporting server database requirements</span></span>

<span data-ttu-id="4a6a2-187">下表列出 App-V 5.0 SP3 報告資料庫安裝所支援的 SQL Server 版本。</span><span class="sxs-lookup"><span data-stu-id="4a6a2-187">The following table lists the SQL Server versions that are supported for the App-V 5.0 SP3 Reporting database installation.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4a6a2-188">SQL Server 版本</span><span class="sxs-lookup"><span data-stu-id="4a6a2-188">SQL Server version</span></span></th>
<th align="left"><span data-ttu-id="4a6a2-189">Service pack</span><span class="sxs-lookup"><span data-stu-id="4a6a2-189">Service pack</span></span></th>
<th align="left"><span data-ttu-id="4a6a2-190">系統架構</span><span class="sxs-lookup"><span data-stu-id="4a6a2-190">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4a6a2-191">Microsoft SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="4a6a2-191">Microsoft SQL Server 2014</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="4a6a2-192">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="4a6a2-192">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4a6a2-193">Microsoft SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="4a6a2-193">Microsoft SQL Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="4a6a2-194">SP2</span><span class="sxs-lookup"><span data-stu-id="4a6a2-194">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="4a6a2-195">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="4a6a2-195">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4a6a2-196">Microsoft SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="4a6a2-196">Microsoft SQL Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="4a6a2-197">SP3</span><span class="sxs-lookup"><span data-stu-id="4a6a2-197">SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="4a6a2-198">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="4a6a2-198">32-bit or 64-bit</span></span></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-client-supp-cfgs"></a><span data-ttu-id="4a6a2-199">App-V 用戶端系統需求</span><span class="sxs-lookup"><span data-stu-id="4a6a2-199">App-V client system requirements</span></span>


<span data-ttu-id="4a6a2-200">下表列出 App-V 5.0 SP3 用戶端安裝所支援的作業系統。</span><span class="sxs-lookup"><span data-stu-id="4a6a2-200">The following table lists the operating systems that are supported for the App-V 5.0 SP3 client installation.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4a6a2-201">作業系統</span><span class="sxs-lookup"><span data-stu-id="4a6a2-201">Operating system</span></span></th>
<th align="left"><span data-ttu-id="4a6a2-202">Service pack</span><span class="sxs-lookup"><span data-stu-id="4a6a2-202">Service pack</span></span></th>
<th align="left"><span data-ttu-id="4a6a2-203">系統架構</span><span class="sxs-lookup"><span data-stu-id="4a6a2-203">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4a6a2-204">Microsoft Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="4a6a2-204">Microsoft Windows8.1</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="4a6a2-205">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="4a6a2-205">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4a6a2-206">Microsoft Windows8</span><span class="sxs-lookup"><span data-stu-id="4a6a2-206">Microsoft Windows8</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="4a6a2-207">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="4a6a2-207">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4a6a2-208">Windows7</span><span class="sxs-lookup"><span data-stu-id="4a6a2-208">Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="4a6a2-209">SP1</span><span class="sxs-lookup"><span data-stu-id="4a6a2-209">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="4a6a2-210">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="4a6a2-210">32-bit or 64-bit</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="4a6a2-211">下列 App-V 用戶端安裝案例不受支援，但說明：</span><span class="sxs-lookup"><span data-stu-id="4a6a2-211">The following App-V client installation scenarios are not supported, except as noted:</span></span>

-   <span data-ttu-id="4a6a2-212">執行 Windows Server 的電腦</span><span class="sxs-lookup"><span data-stu-id="4a6a2-212">Computers that run Windows Server</span></span>

-   <span data-ttu-id="4a6a2-213">執行 App-V 4.6 SP1 或較舊版本的電腦</span><span class="sxs-lookup"><span data-stu-id="4a6a2-213">Computers that run App-V4.6SP1 or earlier versions</span></span>

-   <span data-ttu-id="4a6a2-214">只有啟用 RDS 的伺服器才支援 App-v 5.0 SP3 遠端桌面服務用戶端</span><span class="sxs-lookup"><span data-stu-id="4a6a2-214">The App-V 5.0 SP3 Remote Desktop services client is supported only for RDS-enabled servers</span></span>

### <a href="" id="app-v-client-hardware-requirements-"></a><span data-ttu-id="4a6a2-215">App-V 用戶端的硬體需求</span><span class="sxs-lookup"><span data-stu-id="4a6a2-215">App-V client hardware requirements</span></span>

<span data-ttu-id="4a6a2-216">下列清單顯示 App-V 5.0 SP3 用戶端安裝所支援的硬體設定。</span><span class="sxs-lookup"><span data-stu-id="4a6a2-216">The following list displays the supported hardware configuration for the App-V 5.0 SP3 client installation.</span></span>

-   <span data-ttu-id="4a6a2-217">處理器-1.4 GHz 或更快的32位（x86）或64位（x64）處理器</span><span class="sxs-lookup"><span data-stu-id="4a6a2-217">Processor— 1.4 GHz or faster 32-bit (x86) or 64-bit (x64) processor</span></span>

-   <span data-ttu-id="4a6a2-218">RAM-1 GB （32位）或 2 GB （64位）</span><span class="sxs-lookup"><span data-stu-id="4a6a2-218">RAM— 1 GB (32-bit) or 2 GB (64-bit)</span></span>

-   <span data-ttu-id="4a6a2-219">磁片：安裝 100 MB，不包括虛擬化應用程式所使用的磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="4a6a2-219">Disk— 100 MB for installation, not including the disk space that is used by virtualized applications.</span></span>

## <span data-ttu-id="4a6a2-220">遠端桌面服務用戶端的系統需求</span><span class="sxs-lookup"><span data-stu-id="4a6a2-220">Remote Desktop Services client system requirements</span></span>


<span data-ttu-id="4a6a2-221">下表列出 App-V 5.0 SP3 遠端桌面服務（RDS）用戶端安裝所支援的作業系統。</span><span class="sxs-lookup"><span data-stu-id="4a6a2-221">The following table lists the operating systems that are supported for App-V 5.0 SP3 Remote Desktop Services (RDS) client installation.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4a6a2-222">作業系統</span><span class="sxs-lookup"><span data-stu-id="4a6a2-222">Operating system</span></span></th>
<th align="left"><span data-ttu-id="4a6a2-223">Service Pack</span><span class="sxs-lookup"><span data-stu-id="4a6a2-223">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="4a6a2-224">系統架構</span><span class="sxs-lookup"><span data-stu-id="4a6a2-224">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4a6a2-225">Microsoft Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="4a6a2-225">Microsoft Windows Server 2012 R2</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="4a6a2-226">64 位元</span><span class="sxs-lookup"><span data-stu-id="4a6a2-226">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4a6a2-227">Microsoft Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="4a6a2-227">Microsoft Windows Server 2012</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="4a6a2-228">64 位元</span><span class="sxs-lookup"><span data-stu-id="4a6a2-228">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4a6a2-229">Microsoft Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="4a6a2-229">Microsoft Windows Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="4a6a2-230">SP1</span><span class="sxs-lookup"><span data-stu-id="4a6a2-230">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="4a6a2-231">64 位元</span><span class="sxs-lookup"><span data-stu-id="4a6a2-231">64-bit</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="4a6a2-232">遠端桌面服務用戶端的硬體需求</span><span class="sxs-lookup"><span data-stu-id="4a6a2-232">Remote Desktop Services client hardware requirements</span></span>

<span data-ttu-id="4a6a2-233">App-V 不會在 Windows 伺服器以外的其他需求中新增其他需求。</span><span class="sxs-lookup"><span data-stu-id="4a6a2-233">App-V adds no additional requirements beyond those of Windows Server.</span></span>

-   <span data-ttu-id="4a6a2-234">處理器-1.4 GHz 或更快的64位（x64）處理器</span><span class="sxs-lookup"><span data-stu-id="4a6a2-234">Processor—1.4 GHz or faster, 64-bit (x64) processor</span></span>

-   <span data-ttu-id="4a6a2-235">RAM-2 GB RAM （64位）</span><span class="sxs-lookup"><span data-stu-id="4a6a2-235">RAM—2 GB RAM (64-bit)</span></span>

-   <span data-ttu-id="4a6a2-236">磁碟空間-200 MB 可用硬碟空間</span><span class="sxs-lookup"><span data-stu-id="4a6a2-236">Disk space—200 MB available hard disk space</span></span>

## <span data-ttu-id="4a6a2-237">Sequencer 系統需求</span><span class="sxs-lookup"><span data-stu-id="4a6a2-237">Sequencer system requirements</span></span>


<span data-ttu-id="4a6a2-238">下表列出 App-V 5.0 SP3 排序器安裝所支援的作業系統。</span><span class="sxs-lookup"><span data-stu-id="4a6a2-238">The following table lists the operating systems that are supported for the App-V 5.0 SP3 Sequencer installation.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4a6a2-239">作業系統</span><span class="sxs-lookup"><span data-stu-id="4a6a2-239">Operating system</span></span></th>
<th align="left"><span data-ttu-id="4a6a2-240">Service pack</span><span class="sxs-lookup"><span data-stu-id="4a6a2-240">Service pack</span></span></th>
<th align="left"><span data-ttu-id="4a6a2-241">系統架構</span><span class="sxs-lookup"><span data-stu-id="4a6a2-241">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4a6a2-242">Microsoft Windows Server2012 R2</span><span class="sxs-lookup"><span data-stu-id="4a6a2-242">Microsoft Windows Server2012 R2</span></span></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="4a6a2-243">64 位元</span><span class="sxs-lookup"><span data-stu-id="4a6a2-243">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4a6a2-244">Microsoft Windows Server2012</span><span class="sxs-lookup"><span data-stu-id="4a6a2-244">Microsoft Windows Server2012</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="4a6a2-245">64 位元</span><span class="sxs-lookup"><span data-stu-id="4a6a2-245">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4a6a2-246">Microsoft Windows Server2008 R2</span><span class="sxs-lookup"><span data-stu-id="4a6a2-246">Microsoft Windows Server2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="4a6a2-247">SP1</span><span class="sxs-lookup"><span data-stu-id="4a6a2-247">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="4a6a2-248">64 位元</span><span class="sxs-lookup"><span data-stu-id="4a6a2-248">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4a6a2-249">Microsoft Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="4a6a2-249">Microsoft Windows8.1</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="4a6a2-250">32 位元與 64 位元</span><span class="sxs-lookup"><span data-stu-id="4a6a2-250">32-bit and 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4a6a2-251">Microsoft Windows8</span><span class="sxs-lookup"><span data-stu-id="4a6a2-251">Microsoft Windows8</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="4a6a2-252">32 位元與 64 位元</span><span class="sxs-lookup"><span data-stu-id="4a6a2-252">32-bit and 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4a6a2-253">Microsoft Windows7</span><span class="sxs-lookup"><span data-stu-id="4a6a2-253">Microsoft Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="4a6a2-254">SP1</span><span class="sxs-lookup"><span data-stu-id="4a6a2-254">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="4a6a2-255">32 位元與 64 位元</span><span class="sxs-lookup"><span data-stu-id="4a6a2-255">32-bit and 64-bit</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="4a6a2-256">Sequencer 硬體需求</span><span class="sxs-lookup"><span data-stu-id="4a6a2-256">Sequencer hardware requirements</span></span>

<span data-ttu-id="4a6a2-257">如需硬體需求，請參閱 Windows 或 Windows Server 檔。</span><span class="sxs-lookup"><span data-stu-id="4a6a2-257">See the Windows or Windows Server documentation for the hardware requirements.</span></span> <span data-ttu-id="4a6a2-258">App-v 不會增加任何額外的硬體需求。</span><span class="sxs-lookup"><span data-stu-id="4a6a2-258">App-V adds no additional hardware requirements.</span></span>

## <a href="" id="bkmk-supp-ver-sccm"></a><span data-ttu-id="4a6a2-259">系統中心 Configuration Manager 支援的版本</span><span class="sxs-lookup"><span data-stu-id="4a6a2-259">Supported versions of System Center Configuration Manager</span></span>


<span data-ttu-id="4a6a2-260">App-V 用戶端支援下列版本的 System Center Configuration Manager：</span><span class="sxs-lookup"><span data-stu-id="4a6a2-260">The App-V client supports the following versions of System Center Configuration Manager:</span></span>

-   <span data-ttu-id="4a6a2-261">MicrosoftSystemCenter2012 ConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="4a6a2-261">MicrosoftSystemCenter2012 ConfigurationManager</span></span>

-   <span data-ttu-id="4a6a2-262">System Center 2012 R2 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="4a6a2-262">System Center 2012 R2 Configuration Manager</span></span>

-   <span data-ttu-id="4a6a2-263">System Center 2012 R2 Configuration Manager SP1</span><span class="sxs-lookup"><span data-stu-id="4a6a2-263">System Center 2012 R2 Configuration Manager SP1</span></span>

<span data-ttu-id="4a6a2-264">如需 Configuration Manager 與 App-v 整合的詳細資訊，請參閱[規劃 app-v 與 Configuration Manager 整合](https://technet.microsoft.com/library/jj822982.aspx)。</span><span class="sxs-lookup"><span data-stu-id="4a6a2-264">For more information about how Configuration Manager integrates with App-V, see [Planning for App-V Integration with Configuration Manager](https://technet.microsoft.com/library/jj822982.aspx).</span></span>






## <span data-ttu-id="4a6a2-265">相關主題</span><span class="sxs-lookup"><span data-stu-id="4a6a2-265">Related topics</span></span>


[<span data-ttu-id="4a6a2-266">規劃部署 App-V</span><span class="sxs-lookup"><span data-stu-id="4a6a2-266">Planning to Deploy App-V</span></span>](planning-to-deploy-app-v.md)

[<span data-ttu-id="4a6a2-267">App-V 5.0 SP3 必要條件</span><span class="sxs-lookup"><span data-stu-id="4a6a2-267">App-V 5.0 SP3 Prerequisites</span></span>](app-v-50-sp3-prerequisites.md)

 

 





