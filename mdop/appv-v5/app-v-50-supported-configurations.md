---
title: App-V 5.0 支援的組態
description: App-V 5.0 支援的組態
author: dansimp
ms.assetid: 3787ff63-7ce7-45a8-8f01-81b4b6dced34
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 60236743d2a6b418ca7f4705168a7bf064b82156
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800681"
---
# <span data-ttu-id="93291-103">App-V 5.0 支援的組態</span><span class="sxs-lookup"><span data-stu-id="93291-103">App-V 5.0 Supported Configurations</span></span>


<span data-ttu-id="93291-104">本主題指定在您的環境中安裝並執行 Microsoft Application Virtualization （App-v）5.0 所需的需求。</span><span class="sxs-lookup"><span data-stu-id="93291-104">This topic specifies the requirements that are necessary to install and run Microsoft Application Virtualization (App-V) 5.0 in your environment.</span></span>

**<span data-ttu-id="93291-105">重要</span><span class="sxs-lookup"><span data-stu-id="93291-105">Important</span></span>**  
<span data-ttu-id="93291-106">**本文支援的設定僅適用于 app-v 5.0**。</span><span class="sxs-lookup"><span data-stu-id="93291-106">**The supported configurations in this article apply only to App-V 5.0**.</span></span> <span data-ttu-id="93291-107">如需適用于 App-v 5.0 Service Pack 的支援設定，請參閱下列網頁：</span><span class="sxs-lookup"><span data-stu-id="93291-107">For supported configurations that apply to App-V 5.0 Service Packs, see the following web pages:</span></span>

-   [<span data-ttu-id="93291-108">App-V 5.0 SP1 的新功能</span><span class="sxs-lookup"><span data-stu-id="93291-108">What's new in App-V 5.0 SP1</span></span>](whats-new-in-app-v-50-sp1.md)

-   [<span data-ttu-id="93291-109">關於 App-V 5.0 SP2</span><span class="sxs-lookup"><span data-stu-id="93291-109">About App-V 5.0 SP2</span></span>](about-app-v-50-sp2.md)

-   [<span data-ttu-id="93291-110">App-V 5.0 SP3 支援的組態</span><span class="sxs-lookup"><span data-stu-id="93291-110">App-V 5.0 SP3 Supported Configurations</span></span>](app-v-50-sp3-supported-configurations.md)



## <a href="" id="---------app-v-5-0-server-system-requirements"></a> <span data-ttu-id="93291-111">App-V 5.0 伺服器系統需求</span><span class="sxs-lookup"><span data-stu-id="93291-111">App-V 5.0 server system requirements</span></span>


**<span data-ttu-id="93291-112">重要</span><span class="sxs-lookup"><span data-stu-id="93291-112">Important</span></span>**  
<span data-ttu-id="93291-113">App-v 5.0 server 不支援下列案例：</span><span class="sxs-lookup"><span data-stu-id="93291-113">The App-V 5.0 server does not support the following scenarios:</span></span>



-   <span data-ttu-id="93291-114">部署到執行 Microsoft Windows Server Core 的電腦。</span><span class="sxs-lookup"><span data-stu-id="93291-114">Deployment to a computer that runs Microsoft Windows Server Core.</span></span>

-   <span data-ttu-id="93291-115">部署到執行舊版 App-V 5.0 伺服器元件的電腦。</span><span class="sxs-lookup"><span data-stu-id="93291-115">Deployment to a computer that runs a previous version of App-V 5.0 server components.</span></span>

    **<span data-ttu-id="93291-116">注意</span><span class="sxs-lookup"><span data-stu-id="93291-116">Note</span></span>**  
    <span data-ttu-id="93291-117">您可以使用 app-v 4.5 輕型流式處理伺服器（LWS）伺服器，並行安裝 app-v 5.0。</span><span class="sxs-lookup"><span data-stu-id="93291-117">You can install App-V 5.0 side-by-side with the App-V 4.5 Lightweight Streaming Server (LWS) server only.</span></span> <span data-ttu-id="93291-118">不支援使用 app-v 4.5 應用程式虛擬化管理服務（HWS）伺服器並行部署 app-v 5.0。</span><span class="sxs-lookup"><span data-stu-id="93291-118">Deployment of App-V 5.0 side-by-side with the App-V 4.5 Application Virtualization Management Service (HWS) server is not supported.</span></span>



-   <span data-ttu-id="93291-119">部署到執行 Microsoft SQL Server Express edition 的電腦。</span><span class="sxs-lookup"><span data-stu-id="93291-119">Deployment to a computer that runs Microsoft SQL Server Express edition.</span></span>

-   <span data-ttu-id="93291-120">管理伺服器資料庫或報告資料庫的遠端部署。</span><span class="sxs-lookup"><span data-stu-id="93291-120">Remote deployment of the management server database or the reporting database.</span></span> <span data-ttu-id="93291-121">安裝程式必須直接在執行 Microsoft SQL 的電腦上執行，才能成功進行資料庫安裝。</span><span class="sxs-lookup"><span data-stu-id="93291-121">The installer must be run directly on the computer running Microsoft SQL for the database installation to succeed.</span></span>

-   <span data-ttu-id="93291-122">部署到網網域控制站。</span><span class="sxs-lookup"><span data-stu-id="93291-122">Deployment to a domain controller.</span></span>

-   <span data-ttu-id="93291-123">不支援短路徑。</span><span class="sxs-lookup"><span data-stu-id="93291-123">Short paths are not supported.</span></span> <span data-ttu-id="93291-124">如果您打算使用短路徑，您必須建立新的卷。</span><span class="sxs-lookup"><span data-stu-id="93291-124">If you plan to use a short path you must create a new volume.</span></span>

### <span data-ttu-id="93291-125">管理伺服器作業系統需求</span><span class="sxs-lookup"><span data-stu-id="93291-125">Management Server operating system requirements</span></span>

<span data-ttu-id="93291-126">下表列出 App-V 5.0 管理伺服器安裝支援的作業系統。</span><span class="sxs-lookup"><span data-stu-id="93291-126">The following table lists the operating systems that are supported for the App-V 5.0 management server installation.</span></span>

**<span data-ttu-id="93291-127">注意</span><span class="sxs-lookup"><span data-stu-id="93291-127">Note</span></span>**  
<span data-ttu-id="93291-128">Microsoft 提供目前 service pack 的支援，在某些情況下，也是最前面的 service pack。</span><span class="sxs-lookup"><span data-stu-id="93291-128">Microsoft provides support for the current service pack and, in some cases, the immediately preceding service pack.</span></span> <span data-ttu-id="93291-129">若要尋找您產品的支援時程表，請參閱[支援的生命週期服務套件](https://go.microsoft.com/fwlink/p/?LinkId=31975)。</span><span class="sxs-lookup"><span data-stu-id="93291-129">To find the support timelines for your product, see the [Lifecycle Supported Service Packs](https://go.microsoft.com/fwlink/p/?LinkId=31975).</span></span> <span data-ttu-id="93291-130">如需 Microsoft 支援週期原則的其他相關資訊，請參閱[Microsoft 支援週期支援原則常見問題](https://go.microsoft.com/fwlink/p/?LinkId=31976)。</span><span class="sxs-lookup"><span data-stu-id="93291-130">For additional information about Microsoft Support Lifecycle Policy, see [Microsoft Support Lifecycle Support Policy FAQ](https://go.microsoft.com/fwlink/p/?LinkId=31976).</span></span>



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="93291-131">作業系統</span><span class="sxs-lookup"><span data-stu-id="93291-131">Operating system</span></span></th>
<th align="left"><span data-ttu-id="93291-132">版本</span><span class="sxs-lookup"><span data-stu-id="93291-132">Edition</span></span></th>
<th align="left"><span data-ttu-id="93291-133">Service pack</span><span class="sxs-lookup"><span data-stu-id="93291-133">Service pack</span></span></th>
<th align="left"><span data-ttu-id="93291-134">系統架構</span><span class="sxs-lookup"><span data-stu-id="93291-134">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93291-135">Microsoft Windows Server 2008 （標準版、企業版、Datacenter 或 Web 服務器）</span><span class="sxs-lookup"><span data-stu-id="93291-135">Microsoft Windows Server 2008 (Standard, Enterprise, Datacenter, or Web Server)</span></span></p></td>
<td align="left"><p><span data-ttu-id="93291-136">R2</span><span class="sxs-lookup"><span data-stu-id="93291-136">R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="93291-137">SP1 及更新版本</span><span class="sxs-lookup"><span data-stu-id="93291-137">SP1 and higher</span></span></p></td>
<td align="left"><p><span data-ttu-id="93291-138">64 位元</span><span class="sxs-lookup"><span data-stu-id="93291-138">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="93291-139">Microsoft Windows Server 2012 （標準版、資料中心）</span><span class="sxs-lookup"><span data-stu-id="93291-139">Microsoft Windows Server 2012 (Standard, Datacenter)</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="93291-140">64 位元</span><span class="sxs-lookup"><span data-stu-id="93291-140">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93291-141">Microsoft Windows Server 2012 （標準版、資料中心）</span><span class="sxs-lookup"><span data-stu-id="93291-141">Microsoft Windows Server 2012 (Standard, Datacenter)</span></span></p></td>
<td align="left"><p><span data-ttu-id="93291-142">R2</span><span class="sxs-lookup"><span data-stu-id="93291-142">R2</span></span></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="93291-143">64 位元</span><span class="sxs-lookup"><span data-stu-id="93291-143">64-bit</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="93291-144">重要</span><span class="sxs-lookup"><span data-stu-id="93291-144">Important</span></span>**  
<span data-ttu-id="93291-145">不支援將管理伺服器角色部署到已啟用遠端桌面共用（RDS）的電腦。</span><span class="sxs-lookup"><span data-stu-id="93291-145">Deployment of the management server role to a computer with Remote Desktop Sharing (RDS) enabled is not supported.</span></span>



### <a href="" id="management-server-hardware-requirements-"></a><span data-ttu-id="93291-146">管理伺服器硬體需求</span><span class="sxs-lookup"><span data-stu-id="93291-146">Management Server hardware requirements</span></span>

-   <span data-ttu-id="93291-147">處理器-1.4 GHz 或更快的64位（x64）處理器</span><span class="sxs-lookup"><span data-stu-id="93291-147">Processor—1.4 GHz or faster, 64-bit (x64) processor</span></span>

-   <span data-ttu-id="93291-148">RAM-1 GB RAM （64位）</span><span class="sxs-lookup"><span data-stu-id="93291-148">RAM— 1 GB RAM (64-bit)</span></span>

-   <span data-ttu-id="93291-149">磁碟空間-200 MB 可用的硬碟空間，不含內容目錄。</span><span class="sxs-lookup"><span data-stu-id="93291-149">Disk space—200 MB available hard disk space, not including the content directory.</span></span>

### <span data-ttu-id="93291-150">發佈伺服器作業系統需求</span><span class="sxs-lookup"><span data-stu-id="93291-150">Publishing Server operating system requirements</span></span>

<span data-ttu-id="93291-151">下表列出 App-V 5.0 發佈伺服器安裝所支援的作業系統。</span><span class="sxs-lookup"><span data-stu-id="93291-151">The following table lists the operating systems that are supported for the App-V 5.0 publishing server installation.</span></span>

**<span data-ttu-id="93291-152">注意</span><span class="sxs-lookup"><span data-stu-id="93291-152">Note</span></span>**  
<span data-ttu-id="93291-153">Microsoft 提供目前 service pack 的支援，在某些情況下，也是最前面的 service pack。</span><span class="sxs-lookup"><span data-stu-id="93291-153">Microsoft provides support for the current service pack and, in some cases, the immediately preceding service pack.</span></span> <span data-ttu-id="93291-154">若要尋找您產品的支援時程表，請參閱[支援的生命週期服務套件](https://go.microsoft.com/fwlink/p/?LinkId=31975)。</span><span class="sxs-lookup"><span data-stu-id="93291-154">To find the support timelines for your product, see the [Lifecycle Supported Service Packs](https://go.microsoft.com/fwlink/p/?LinkId=31975).</span></span> <span data-ttu-id="93291-155">如需 Microsoft 支援週期原則的其他相關資訊，請參閱[Microsoft 支援週期支援原則常見問題](https://go.microsoft.com/fwlink/p/?LinkId=31976)。</span><span class="sxs-lookup"><span data-stu-id="93291-155">For additional information about Microsoft Support Lifecycle Policy, see [Microsoft Support Lifecycle Support Policy FAQ](https://go.microsoft.com/fwlink/p/?LinkId=31976).</span></span>



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="93291-156">作業系統</span><span class="sxs-lookup"><span data-stu-id="93291-156">Operating system</span></span></th>
<th align="left"><span data-ttu-id="93291-157">版本</span><span class="sxs-lookup"><span data-stu-id="93291-157">Edition</span></span></th>
<th align="left"><span data-ttu-id="93291-158">Service pack</span><span class="sxs-lookup"><span data-stu-id="93291-158">Service pack</span></span></th>
<th align="left"><span data-ttu-id="93291-159">系統架構</span><span class="sxs-lookup"><span data-stu-id="93291-159">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93291-160">Microsoft Windows Server 2008 （標準版、企業版、Datacenter 或 Web 服務器）</span><span class="sxs-lookup"><span data-stu-id="93291-160">Microsoft Windows Server 2008 (Standard, Enterprise, Datacenter, or Web Server)</span></span></p></td>
<td align="left"><p><span data-ttu-id="93291-161">R2</span><span class="sxs-lookup"><span data-stu-id="93291-161">R2</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="93291-162">64 位元</span><span class="sxs-lookup"><span data-stu-id="93291-162">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="93291-163">Microsoft Windows Server 2012 （標準版、資料中心）</span><span class="sxs-lookup"><span data-stu-id="93291-163">Microsoft Windows Server 2012 (Standard, Datacenter)</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="93291-164">64 位元</span><span class="sxs-lookup"><span data-stu-id="93291-164">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93291-165">Microsoft Windows Server 2012 （標準版、資料中心）</span><span class="sxs-lookup"><span data-stu-id="93291-165">Microsoft Windows Server 2012 (Standard, Datacenter)</span></span></p></td>
<td align="left"><p><span data-ttu-id="93291-166">R2</span><span class="sxs-lookup"><span data-stu-id="93291-166">R2</span></span></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="93291-167">64 位元</span><span class="sxs-lookup"><span data-stu-id="93291-167">64-bit</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="publishing-server-hardware-requirements-"></a><span data-ttu-id="93291-168">發佈伺服器硬體需求</span><span class="sxs-lookup"><span data-stu-id="93291-168">Publishing Server hardware requirements</span></span>

-   <span data-ttu-id="93291-169">處理器-1.4 GHz 或更快。</span><span class="sxs-lookup"><span data-stu-id="93291-169">Processor—1.4 GHz or faster.</span></span> <span data-ttu-id="93291-170">64位（x64）處理器</span><span class="sxs-lookup"><span data-stu-id="93291-170">64-bit (x64) processor</span></span>

-   <span data-ttu-id="93291-171">RAM-2 GB RAM （64位）</span><span class="sxs-lookup"><span data-stu-id="93291-171">RAM— 2 GB RAM (64-bit)</span></span>

-   <span data-ttu-id="93291-172">磁碟空間-200 MB 可用硬碟空間。</span><span class="sxs-lookup"><span data-stu-id="93291-172">Disk space—200 MB available hard disk space.</span></span> <span data-ttu-id="93291-173">不含內容目錄</span><span class="sxs-lookup"><span data-stu-id="93291-173">not including content directory</span></span>

### <span data-ttu-id="93291-174">報表伺服器作業系統需求</span><span class="sxs-lookup"><span data-stu-id="93291-174">Reporting Server operating system requirements</span></span>

<span data-ttu-id="93291-175">下表列出 App-V 5.0 報表服務器安裝支援的作業系統。</span><span class="sxs-lookup"><span data-stu-id="93291-175">The following table lists the operating systems that are supported for the App-V 5.0 reporting server installation.</span></span>

**<span data-ttu-id="93291-176">注意</span><span class="sxs-lookup"><span data-stu-id="93291-176">Note</span></span>**  
<span data-ttu-id="93291-177">Microsoft 提供目前 service pack 的支援，在某些情況下，也是最前面的 service pack。</span><span class="sxs-lookup"><span data-stu-id="93291-177">Microsoft provides support for the current service pack and, in some cases, the immediately preceding service pack.</span></span> <span data-ttu-id="93291-178">若要尋找您產品的支援時程表，請參閱[支援的生命週期服務套件](https://go.microsoft.com/fwlink/p/?LinkId=31975)。</span><span class="sxs-lookup"><span data-stu-id="93291-178">To find the support timelines for your product, see the [Lifecycle Supported Service Packs](https://go.microsoft.com/fwlink/p/?LinkId=31975).</span></span> <span data-ttu-id="93291-179">如需 Microsoft 支援週期原則的其他相關資訊，請參閱[Microsoft 支援週期支援原則常見問題](https://go.microsoft.com/fwlink/p/?LinkId=31976)。</span><span class="sxs-lookup"><span data-stu-id="93291-179">For additional information about Microsoft Support Lifecycle Policy, see [Microsoft Support Lifecycle Support Policy FAQ](https://go.microsoft.com/fwlink/p/?LinkId=31976).</span></span>



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="93291-180">作業系統</span><span class="sxs-lookup"><span data-stu-id="93291-180">Operating system</span></span></th>
<th align="left"><span data-ttu-id="93291-181">版本</span><span class="sxs-lookup"><span data-stu-id="93291-181">Edition</span></span></th>
<th align="left"><span data-ttu-id="93291-182">Service Pack</span><span class="sxs-lookup"><span data-stu-id="93291-182">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="93291-183">系統架構</span><span class="sxs-lookup"><span data-stu-id="93291-183">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93291-184">Microsoft Windows Server 2008 （標準版、企業版、Datacenter 或 Web 服務器）</span><span class="sxs-lookup"><span data-stu-id="93291-184">Microsoft Windows Server 2008 (Standard, Enterprise, Datacenter, or Web Server)</span></span></p></td>
<td align="left"><p><span data-ttu-id="93291-185">R2</span><span class="sxs-lookup"><span data-stu-id="93291-185">R2</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="93291-186">64 位元</span><span class="sxs-lookup"><span data-stu-id="93291-186">64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="93291-187">Microsoft Windows Server 2012 （標準版、資料中心）</span><span class="sxs-lookup"><span data-stu-id="93291-187">Microsoft Windows Server 2012 (Standard, Datacenter)</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="93291-188">64 位元</span><span class="sxs-lookup"><span data-stu-id="93291-188">64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93291-189">Microsoft Windows Server 2012 （標準版、資料中心）</span><span class="sxs-lookup"><span data-stu-id="93291-189">Microsoft Windows Server 2012 (Standard, Datacenter)</span></span></p></td>
<td align="left"><p><span data-ttu-id="93291-190">R2</span><span class="sxs-lookup"><span data-stu-id="93291-190">R2</span></span></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="93291-191">64 位元</span><span class="sxs-lookup"><span data-stu-id="93291-191">64-bit</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="reporting-server-hardware-requirements-"></a><span data-ttu-id="93291-192">報表服務器硬體需求</span><span class="sxs-lookup"><span data-stu-id="93291-192">Reporting Server hardware requirements</span></span>

-   <span data-ttu-id="93291-193">處理器-1.4 GHz 或更快。</span><span class="sxs-lookup"><span data-stu-id="93291-193">Processor—1.4 GHz or faster.</span></span> <span data-ttu-id="93291-194">64位（x64）處理器</span><span class="sxs-lookup"><span data-stu-id="93291-194">64-bit (x64) processor</span></span>

-   <span data-ttu-id="93291-195">RAM-2 GB RAM （64位）</span><span class="sxs-lookup"><span data-stu-id="93291-195">RAM—2 GB RAM (64-bit)</span></span>

-   <span data-ttu-id="93291-196">磁碟空間-200 MB 可用硬碟空間</span><span class="sxs-lookup"><span data-stu-id="93291-196">Disk space—200 MB available hard disk space</span></span>

### <a href="" id="sql-server-database-requirements-"></a><span data-ttu-id="93291-197">SQL Server 資料庫需求</span><span class="sxs-lookup"><span data-stu-id="93291-197">SQL Server database requirements</span></span>

<span data-ttu-id="93291-198">下表列出 App-V 5.0 資料庫和伺服器安裝支援的 SQL Server 版本。</span><span class="sxs-lookup"><span data-stu-id="93291-198">The following table lists the SQL Server versions that are supported for the App-V 5.0 database and server installation.</span></span>

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="93291-199">App-v 5.0 伺服器類型</span><span class="sxs-lookup"><span data-stu-id="93291-199">App-V 5.0 server type</span></span></th>
<th align="left"><span data-ttu-id="93291-200">SQL Server 版本</span><span class="sxs-lookup"><span data-stu-id="93291-200">SQL Server version</span></span></th>
<th align="left"><span data-ttu-id="93291-201">版本</span><span class="sxs-lookup"><span data-stu-id="93291-201">Edition</span></span></th>
<th align="left"><span data-ttu-id="93291-202">Service pack</span><span class="sxs-lookup"><span data-stu-id="93291-202">Service pack</span></span></th>
<th align="left"><span data-ttu-id="93291-203">系統架構</span><span class="sxs-lookup"><span data-stu-id="93291-203">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93291-204">管理/報告</span><span class="sxs-lookup"><span data-stu-id="93291-204">Management / Reporting</span></span></p></td>
<td align="left"><p><span data-ttu-id="93291-205">Microsoft SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="93291-205">Microsoft SQL Server 2008</span></span></p>
<p><span data-ttu-id="93291-206">（標準版、企業版、資料中心或開發人員版本，具有下列功能： <strong>資料庫引擎服務 </strong> 。）</span><span class="sxs-lookup"><span data-stu-id="93291-206">(Standard, Enterprise, Datacenter, or the Developer Edition with the following feature: <strong>Database Engine Services</strong>.)</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="93291-207">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="93291-207">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="93291-208">管理/報告</span><span class="sxs-lookup"><span data-stu-id="93291-208">Management / Reporting</span></span></p></td>
<td align="left"><p><span data-ttu-id="93291-209">Microsoft SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="93291-209">Microsoft SQL Server 2008</span></span> </p>
<p><span data-ttu-id="93291-210">（標準版、企業版、資料中心或開發人員版本，具有下列功能： <strong>資料庫引擎服務 </strong> 。）</span><span class="sxs-lookup"><span data-stu-id="93291-210">(Standard, Enterprise, Datacenter, or the Developer Edition with the following feature: <strong>Database Engine Services</strong>.)</span></span></p></td>
<td align="left"><p><span data-ttu-id="93291-211">R2</span><span class="sxs-lookup"><span data-stu-id="93291-211">R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="93291-212">SP2</span><span class="sxs-lookup"><span data-stu-id="93291-212">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="93291-213">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="93291-213">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93291-214">管理/報告</span><span class="sxs-lookup"><span data-stu-id="93291-214">Management / Reporting</span></span></p></td>
<td align="left"><p><span data-ttu-id="93291-215">Microsoft SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="93291-215">Microsoft SQL Server 2012</span></span></p>
<p><span data-ttu-id="93291-216">（標準版、企業版、資料中心或開發人員版本，具有下列功能： <strong>資料庫引擎服務 </strong> 。）</span><span class="sxs-lookup"><span data-stu-id="93291-216">(Standard, Enterprise, Datacenter, or the Developer Edition with the following feature: <strong>Database Engine Services</strong>.)</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="93291-217">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="93291-217">32-bit or 64-bit</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-client-supp-cfgs"></a> <span data-ttu-id="93291-218">App-V 5.0 用戶端系統需求</span><span class="sxs-lookup"><span data-stu-id="93291-218">App-V 5.0 client system requirements</span></span>


<span data-ttu-id="93291-219">下表列出 App-V 5.0 用戶端安裝支援的作業系統。</span><span class="sxs-lookup"><span data-stu-id="93291-219">The following table lists the operating systems that are supported for the App-V 5.0 client installation.</span></span>

**<span data-ttu-id="93291-220">注意</span><span class="sxs-lookup"><span data-stu-id="93291-220">Note</span></span>**  
<span data-ttu-id="93291-221">Microsoft 提供目前 service pack 的支援，在某些情況下，也是最前面的 service pack。</span><span class="sxs-lookup"><span data-stu-id="93291-221">Microsoft provides support for the current service pack and, in some cases, the immediately preceding service pack.</span></span> <span data-ttu-id="93291-222">若要尋找您產品的支援時程表，請參閱[支援的生命週期服務套件](https://go.microsoft.com/fwlink/p/?LinkId=31975)。</span><span class="sxs-lookup"><span data-stu-id="93291-222">To find the support timelines for your product, see the [Lifecycle Supported Service Packs](https://go.microsoft.com/fwlink/p/?LinkId=31975).</span></span> <span data-ttu-id="93291-223">如需 Microsoft 支援週期原則的其他相關資訊，請參閱[Microsoft 支援週期支援原則常見問題](https://go.microsoft.com/fwlink/p/?LinkId=31976)。</span><span class="sxs-lookup"><span data-stu-id="93291-223">For additional information about Microsoft Support Lifecycle Policy, see [Microsoft Support Lifecycle Support Policy FAQ](https://go.microsoft.com/fwlink/p/?LinkId=31976).</span></span>



<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="93291-224">作業系統</span><span class="sxs-lookup"><span data-stu-id="93291-224">Operating system</span></span></th>
<th align="left"><span data-ttu-id="93291-225">Service pack</span><span class="sxs-lookup"><span data-stu-id="93291-225">Service pack</span></span></th>
<th align="left"><span data-ttu-id="93291-226">系統架構</span><span class="sxs-lookup"><span data-stu-id="93291-226">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93291-227">Microsoft Windows 7</span><span class="sxs-lookup"><span data-stu-id="93291-227">Microsoft Windows 7</span></span></p></td>
<td align="left"><p><span data-ttu-id="93291-228">SP1</span><span class="sxs-lookup"><span data-stu-id="93291-228">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="93291-229">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="93291-229">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="93291-230">Microsoft Windows 8</span><span class="sxs-lookup"><span data-stu-id="93291-230">Microsoft Windows 8</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="93291-231">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="93291-231">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><div class="alert">
<strong><span data-ttu-id="93291-232">重要</span><span class="sxs-lookup"><span data-stu-id="93291-232">Important</span></span></strong><br/><p><span data-ttu-id="93291-233">Windows 8.1 僅支援 App-v 5.0 SP2</span><span class="sxs-lookup"><span data-stu-id="93291-233">Windows 8.1 is only supported by App-V 5.0 SP2</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="93291-234">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="93291-234">Windows 8.1</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="93291-235">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="93291-235">32-bit or 64-bit</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="93291-236">下列 App-V 用戶端安裝案例不受支援，但說明：</span><span class="sxs-lookup"><span data-stu-id="93291-236">The following App-V client installation scenarios are not supported, except as noted:</span></span>

-   <span data-ttu-id="93291-237">執行 Windows Server 的電腦</span><span class="sxs-lookup"><span data-stu-id="93291-237">Computers that run Windows Server</span></span>

-   <span data-ttu-id="93291-238">執行 App-v 4.6 SP1 或較舊版本的電腦</span><span class="sxs-lookup"><span data-stu-id="93291-238">Computers that run App-V 4.6 SP1 or earlier versions</span></span>

-   <span data-ttu-id="93291-239">只有啟用 RDS 的伺服器才支援 App-v 5.0 遠端桌面服務用戶端</span><span class="sxs-lookup"><span data-stu-id="93291-239">The App-V 5.0 Remote Desktop services client is supported only for RDS-enabled servers</span></span>

### <a href="" id="client-hardware-requirements-"></a><span data-ttu-id="93291-240">用戶端硬體需求</span><span class="sxs-lookup"><span data-stu-id="93291-240">Client hardware requirements</span></span>

<span data-ttu-id="93291-241">下列清單顯示 App-V 5.0 用戶端安裝所支援的硬體設定。</span><span class="sxs-lookup"><span data-stu-id="93291-241">The following list displays the supported hardware configuration for the App-V 5.0 client installation.</span></span>

-   <span data-ttu-id="93291-242">處理器-1.4 GHz 或更快的32位（x86）或64位（x64）處理器</span><span class="sxs-lookup"><span data-stu-id="93291-242">Processor— 1.4 GHz or faster 32-bit (x86) or 64-bit (x64) processor</span></span>

-   <span data-ttu-id="93291-243">RAM-1 GB （32位）或 2 GB （64位）</span><span class="sxs-lookup"><span data-stu-id="93291-243">RAM— 1 GB (32-bit) or 2 GB (64-bit)</span></span>

-   <span data-ttu-id="93291-244">磁片：安裝 100 MB，不包括虛擬化應用程式所使用的磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="93291-244">Disk— 100 MB for installation, not including the disk space that is used by virtualized applications.</span></span>

## <a href="" id="---------app-v-5-0-remote-desktop-client-system-requirements"></a> <span data-ttu-id="93291-245">App-v 5.0 遠端桌面用戶端系統需求</span><span class="sxs-lookup"><span data-stu-id="93291-245">App-V 5.0 Remote Desktop client system requirements</span></span>


<span data-ttu-id="93291-246">下表列出 App-V 5.0 遠端桌面用戶端安裝所支援的作業系統。</span><span class="sxs-lookup"><span data-stu-id="93291-246">The following table lists the operating systems that are supported for App-V 5.0 Remote Desktop client installation.</span></span>

**<span data-ttu-id="93291-247">注意</span><span class="sxs-lookup"><span data-stu-id="93291-247">Note</span></span>**  
<span data-ttu-id="93291-248">Microsoft 提供目前 service pack 的支援，在某些情況下，也是最前面的 service pack。</span><span class="sxs-lookup"><span data-stu-id="93291-248">Microsoft provides support for the current service pack and, in some cases, the immediately preceding service pack.</span></span> <span data-ttu-id="93291-249">若要尋找您產品的支援時程表，請參閱[支援的生命週期服務套件](https://go.microsoft.com/fwlink/p/?LinkId=31975)。</span><span class="sxs-lookup"><span data-stu-id="93291-249">To find the support timelines for your product, see the [Lifecycle Supported Service Packs](https://go.microsoft.com/fwlink/p/?LinkId=31975).</span></span> <span data-ttu-id="93291-250">如需 Microsoft 支援週期原則的其他相關資訊，請參閱[Microsoft 支援週期支援原則常見問題](https://go.microsoft.com/fwlink/p/?LinkId=31976)。</span><span class="sxs-lookup"><span data-stu-id="93291-250">For additional information about Microsoft Support Lifecycle Policy, see [Microsoft Support Lifecycle Support Policy FAQ](https://go.microsoft.com/fwlink/p/?LinkId=31976).</span></span>



<span data-ttu-id="93291-251">作業系統版本 Service pack Microsoft Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="93291-251">Operating system Edition Service pack Microsoft Windows Server 2008</span></span>

<span data-ttu-id="93291-252">R2</span><span class="sxs-lookup"><span data-stu-id="93291-252">R2</span></span>

<span data-ttu-id="93291-253">SP1</span><span class="sxs-lookup"><span data-stu-id="93291-253">SP1</span></span>

<span data-ttu-id="93291-254">Microsoft Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="93291-254">Microsoft Windows Server 2012</span></span>

**<span data-ttu-id="93291-255">重要</span><span class="sxs-lookup"><span data-stu-id="93291-255">Important</span></span>**  
<span data-ttu-id="93291-256">Windows Server 2012 R2 僅支援 App-v 5.0 SP2</span><span class="sxs-lookup"><span data-stu-id="93291-256">Windows Server 2012 R2 is only supported by App-V 5.0 SP2</span></span>



<span data-ttu-id="93291-257">Microsoft Windows Server 2012 （標準版、資料中心）</span><span class="sxs-lookup"><span data-stu-id="93291-257">Microsoft Windows Server 2012 (Standard, Datacenter)</span></span>

<span data-ttu-id="93291-258">R2</span><span class="sxs-lookup"><span data-stu-id="93291-258">R2</span></span>

<span data-ttu-id="93291-259">64 位元</span><span class="sxs-lookup"><span data-stu-id="93291-259">64-bit</span></span>



### <a href="" id="remote-desktop-client-hardware-requirements-"></a><span data-ttu-id="93291-260">遠端桌面用戶端的硬體需求</span><span class="sxs-lookup"><span data-stu-id="93291-260">Remote Desktop client hardware requirements</span></span>

<span data-ttu-id="93291-261">下列清單顯示 App-V 5.0 用戶端安裝所支援的硬體設定。</span><span class="sxs-lookup"><span data-stu-id="93291-261">The following list displays the supported hardware configuration for the App-V 5.0 client installation.</span></span>

-   <span data-ttu-id="93291-262">處理器-1.4 GHz 或更快的32位（x86）或64位（x64）處理器</span><span class="sxs-lookup"><span data-stu-id="93291-262">Processor— 1.4 GHz or faster 32-bit (x86) or 64-bit (x64) processor</span></span>

-   <span data-ttu-id="93291-263">RAM-1 GB （32位）或 2 GB （64位）</span><span class="sxs-lookup"><span data-stu-id="93291-263">RAM— 1 GB (32-bit) or 2 GB (64-bit)</span></span>

-   <span data-ttu-id="93291-264">磁片：安裝 100 MB，不包括虛擬化應用程式所使用的磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="93291-264">Disk— 100 MB for installation, not including the disk space that is used by virtualized applications.</span></span>

## <a href="" id="---------app-v-5-0-sequencer-system-requirements"></a> <span data-ttu-id="93291-265">App-v 5.0 Sequencer 系統需求</span><span class="sxs-lookup"><span data-stu-id="93291-265">App-V 5.0 Sequencer system requirements</span></span>


<span data-ttu-id="93291-266">下表列出應用程式 V 5.0 排序器安裝支援的作業系統。</span><span class="sxs-lookup"><span data-stu-id="93291-266">The following table lists the operating systems that are supported for App-V 5.0 Sequencer installation.</span></span>

**<span data-ttu-id="93291-267">注意</span><span class="sxs-lookup"><span data-stu-id="93291-267">Note</span></span>**  
<span data-ttu-id="93291-268">Microsoft 提供目前 service pack 的支援，在某些情況下，也是最前面的 service pack。</span><span class="sxs-lookup"><span data-stu-id="93291-268">Microsoft provides support for the current service pack and, in some cases, the immediately preceding service pack.</span></span> <span data-ttu-id="93291-269">若要尋找您產品的支援時程表，請參閱[支援的生命週期服務套件](https://go.microsoft.com/fwlink/p/?LinkId=31975)。</span><span class="sxs-lookup"><span data-stu-id="93291-269">To find the support timelines for your product, see the [Lifecycle Supported Service Packs](https://go.microsoft.com/fwlink/p/?LinkId=31975).</span></span> <span data-ttu-id="93291-270">如需 Microsoft 支援週期原則的其他相關資訊，請參閱[Microsoft 支援週期支援原則常見問題](https://go.microsoft.com/fwlink/p/?LinkId=31976)。</span><span class="sxs-lookup"><span data-stu-id="93291-270">For additional information about Microsoft Support Lifecycle Policy, see [Microsoft Support Lifecycle Support Policy FAQ](https://go.microsoft.com/fwlink/p/?LinkId=31976).</span></span>



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="93291-271">作業系統</span><span class="sxs-lookup"><span data-stu-id="93291-271">Operating system</span></span></th>
<th align="left"><span data-ttu-id="93291-272">版本</span><span class="sxs-lookup"><span data-stu-id="93291-272">Edition</span></span></th>
<th align="left"><span data-ttu-id="93291-273">Service pack</span><span class="sxs-lookup"><span data-stu-id="93291-273">Service pack</span></span></th>
<th align="left"><span data-ttu-id="93291-274">系統架構</span><span class="sxs-lookup"><span data-stu-id="93291-274">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93291-275">Microsoft Windows 7</span><span class="sxs-lookup"><span data-stu-id="93291-275">Microsoft Windows 7</span></span></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="93291-276">SP1</span><span class="sxs-lookup"><span data-stu-id="93291-276">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="93291-277">32 位元與 64 位元</span><span class="sxs-lookup"><span data-stu-id="93291-277">32-bit and 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="93291-278">Microsoft Windows 8</span><span class="sxs-lookup"><span data-stu-id="93291-278">Microsoft Windows 8</span></span></p></td>
<td align="left"></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="93291-279">32 位元與 64 位元</span><span class="sxs-lookup"><span data-stu-id="93291-279">32-bit and 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><div class="alert">
<strong><span data-ttu-id="93291-280">重要</span><span class="sxs-lookup"><span data-stu-id="93291-280">Important</span></span></strong><br/><p><span data-ttu-id="93291-281">Windows 8.1 僅支援 App-v 5.0 SP2</span><span class="sxs-lookup"><span data-stu-id="93291-281">Windows 8.1 is only supported by App-V 5.0 SP2</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="93291-282">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="93291-282">Windows 8.1</span></span></p></td>
<td align="left"></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="93291-283">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="93291-283">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="93291-284">Microsoft Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="93291-284">Microsoft Windows Server 2008</span></span></p></td>
<td align="left"><p><span data-ttu-id="93291-285">R2</span><span class="sxs-lookup"><span data-stu-id="93291-285">R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="93291-286">SP1</span><span class="sxs-lookup"><span data-stu-id="93291-286">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="93291-287">32 位元與 64 位元</span><span class="sxs-lookup"><span data-stu-id="93291-287">32-bit and 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93291-288">Microsoft Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="93291-288">Microsoft Windows Server 2012</span></span></p></td>
<td align="left"></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="93291-289">32 位元與 64 位元</span><span class="sxs-lookup"><span data-stu-id="93291-289">32-bit and 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><div class="alert">
<strong><span data-ttu-id="93291-290">重要</span><span class="sxs-lookup"><span data-stu-id="93291-290">Important</span></span></strong><br/><p><span data-ttu-id="93291-291">Windows Server 2012 R2 僅支援 App-v 5.0 SP2</span><span class="sxs-lookup"><span data-stu-id="93291-291">Windows Server 2012 R2 is only supported by App-V 5.0 SP2</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="93291-292">Microsoft Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="93291-292">Microsoft Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="93291-293">R2</span><span class="sxs-lookup"><span data-stu-id="93291-293">R2</span></span></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="93291-294">64 位元</span><span class="sxs-lookup"><span data-stu-id="93291-294">64-bit</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-supp-ver-sccm"></a><span data-ttu-id="93291-295">系統中心 Configuration Manager 支援的版本</span><span class="sxs-lookup"><span data-stu-id="93291-295">Supported versions of System Center Configuration Manager</span></span>


<span data-ttu-id="93291-296">您可以使用 Microsoft System Center 2012 Configuration Manager 或 System Center 2012 R2 Configuration Manager 來管理 App-v virtual 應用程式、報告及其他功能。</span><span class="sxs-lookup"><span data-stu-id="93291-296">You can use Microsoft System Center 2012 Configuration Manager or System Center 2012 R2 Configuration Manager to manage App-V virtual applications, reporting, and other functions.</span></span> <span data-ttu-id="93291-297">下表列出每個適用版本 App-v 的 Configuration Manager 支援版本。</span><span class="sxs-lookup"><span data-stu-id="93291-297">The following table lists the supported versions of Configuration Manager for each applicable version of App-V.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="93291-298">支援的 Configuration Manager 版本</span><span class="sxs-lookup"><span data-stu-id="93291-298">Supported Configuration Manager version</span></span></th>
<th align="left"><span data-ttu-id="93291-299">App-V 版本</span><span class="sxs-lookup"><span data-stu-id="93291-299">App-V version</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93291-300">Microsoft System Center 2012 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="93291-300">Microsoft System Center 2012 Configuration Manager</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="93291-301">App-V 5。0</span><span class="sxs-lookup"><span data-stu-id="93291-301">App-V 5.0</span></span></p></li>
<li><p><span data-ttu-id="93291-302">App-V 5.0 SP1</span><span class="sxs-lookup"><span data-stu-id="93291-302">App-V 5.0 SP1</span></span></p></li>
<li><p><span data-ttu-id="93291-303">App-v 5.0 SP2</span><span class="sxs-lookup"><span data-stu-id="93291-303">App-V 5.0 SP2</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="93291-304">System Center 2012 R2 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="93291-304">System Center 2012 R2 Configuration Manager</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="93291-305">App-V 5。0</span><span class="sxs-lookup"><span data-stu-id="93291-305">App-V 5.0</span></span></p></li>
<li><p><span data-ttu-id="93291-306">App-V 5.0 SP1</span><span class="sxs-lookup"><span data-stu-id="93291-306">App-V 5.0 SP1</span></span></p></li>
<li><p><span data-ttu-id="93291-307">App-v 5.0 SP2</span><span class="sxs-lookup"><span data-stu-id="93291-307">App-V 5.0 SP2</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



<span data-ttu-id="93291-308">如需 Configuration Manager 與 App-v 整合的詳細資訊，請參閱[規劃 app-v 與 Configuration Manager 整合](https://technet.microsoft.com/library/jj822982.aspx)。</span><span class="sxs-lookup"><span data-stu-id="93291-308">For more information about how Configuration Manager integrates with App-V, see [Planning for App-V Integration with Configuration Manager](https://technet.microsoft.com/library/jj822982.aspx).</span></span>






## <span data-ttu-id="93291-309">相關主題</span><span class="sxs-lookup"><span data-stu-id="93291-309">Related topics</span></span>


[<span data-ttu-id="93291-310">規劃部署 App-V</span><span class="sxs-lookup"><span data-stu-id="93291-310">Planning to Deploy App-V</span></span>](planning-to-deploy-app-v.md)

[<span data-ttu-id="93291-311">App-V 5.0 必要條件</span><span class="sxs-lookup"><span data-stu-id="93291-311">App-V 5.0 Prerequisites</span></span>](app-v-50-prerequisites.md)









