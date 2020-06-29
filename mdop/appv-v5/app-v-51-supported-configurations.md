---
title: App-V 5.1 支援的組態
description: App-V 5.1 支援的組態
author: dansimp
ms.assetid: 8b8db63b-f71c-4ae9-80e7-a6752334e1f6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 04/02/2020
ms.openlocfilehash: fbda364de66b1f7b8730dca38f864a84f7848e58
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800665"
---
# <span data-ttu-id="99c5d-103">App-V 5.1 支援的組態</span><span class="sxs-lookup"><span data-stu-id="99c5d-103">App-V 5.1 Supported Configurations</span></span>

><span data-ttu-id="99c5d-104">適用于： Windows 10，版本 1607;Window Server 2019;Windows Server 2016;Windows Server 2012 R2;Windows Server 2012;Windows Server 2008 R2 （延長安全更新）</span><span class="sxs-lookup"><span data-stu-id="99c5d-104">Applies to: Windows 10, version 1607; Window Server 2019; Windows Server 2016; Windows Server 2012 R2; Windows Server 2012; Windows Server 2008 R2 (Extended Security Update)</span></span>

<span data-ttu-id="99c5d-105">本主題指定在您的環境中安裝並執行 Microsoft Application Virtualization （App-v）5.1 的需求。</span><span class="sxs-lookup"><span data-stu-id="99c5d-105">This topic specifies the requirements to install and run Microsoft Application Virtualization (App-V) 5.1 in your environment.</span></span>

## <span data-ttu-id="99c5d-106">App-v Server 系統需求</span><span class="sxs-lookup"><span data-stu-id="99c5d-106">App-V Server system requirements</span></span>

<span data-ttu-id="99c5d-107">本節列出所有應用程式 V 伺服器元件的作業系統和硬體需求。</span><span class="sxs-lookup"><span data-stu-id="99c5d-107">This section lists the operating system and hardware requirements for all of the App-V Server components.</span></span>

### <span data-ttu-id="99c5d-108">不受支援的 App-v 5.1 Server 案例</span><span class="sxs-lookup"><span data-stu-id="99c5d-108">Unsupported App-V 5.1 Server scenarios</span></span>

<span data-ttu-id="99c5d-109">App-v 5.1 Server 不支援下列案例：</span><span class="sxs-lookup"><span data-stu-id="99c5d-109">The App-V 5.1 Server does not support the following scenarios:</span></span>

-   <span data-ttu-id="99c5d-110">部署到執行 Microsoft Windows Server Core 的電腦。</span><span class="sxs-lookup"><span data-stu-id="99c5d-110">Deployment to a computer that runs Microsoft Windows Server Core.</span></span>

-   <span data-ttu-id="99c5d-111">部署到執行舊版 App-V 5.1 伺服器元件的電腦。</span><span class="sxs-lookup"><span data-stu-id="99c5d-111">Deployment to a computer that runs a previous version of App-V 5.1 Server components.</span></span> <span data-ttu-id="99c5d-112">您可以只使用 App-v 4.5 輕型流式處理伺服器（LWS）伺服器來安裝 app-v 5.1。</span><span class="sxs-lookup"><span data-stu-id="99c5d-112">You can install App-V 5.1 side by side with the App-V4.5 Lightweight Streaming Server (LWS) server only.</span></span> <span data-ttu-id="99c5d-113">不支援使用 app-v 4.5 應用程式虛擬化管理服務（HWS）伺服器並行部署 app-v。</span><span class="sxs-lookup"><span data-stu-id="99c5d-113">Deployment of App-V side by side with the App-V 4.5 Application Virtualization Management Service (HWS) server is not supported.</span></span>

-   <span data-ttu-id="99c5d-114">部署到執行 Microsoft SQL Server Express edition 的電腦。</span><span class="sxs-lookup"><span data-stu-id="99c5d-114">Deployment to a computer that runs Microsoft SQL Server Express edition.</span></span>

-   <span data-ttu-id="99c5d-115">部署到網網域控制站。</span><span class="sxs-lookup"><span data-stu-id="99c5d-115">Deployment to a domain controller.</span></span>

-   <span data-ttu-id="99c5d-116">短路徑。</span><span class="sxs-lookup"><span data-stu-id="99c5d-116">Short paths.</span></span> <span data-ttu-id="99c5d-117">如果您打算使用短路徑，您必須建立新的卷。</span><span class="sxs-lookup"><span data-stu-id="99c5d-117">If you plan to use a short path, you must create a new volume.</span></span>

### <span data-ttu-id="99c5d-118">管理伺服器作業系統需求</span><span class="sxs-lookup"><span data-stu-id="99c5d-118">Management server operating system requirements</span></span>

<span data-ttu-id="99c5d-119">下表列出 App-V 5.1 管理伺服器安裝支援的作業系統。</span><span class="sxs-lookup"><span data-stu-id="99c5d-119">The following table lists the operating systems that are supported for the App-V 5.1 Management server installation.</span></span>

> [!NOTE]
> <span data-ttu-id="99c5d-120">Microsoft 提供目前 service pack 的支援，在某些情況下，也是最前面的 service pack。</span><span class="sxs-lookup"><span data-stu-id="99c5d-120">Microsoft provides support for the current service pack and, in some cases, the immediately preceding service pack.</span></span> <span data-ttu-id="99c5d-121">若要尋找您產品的支援時程表，請參閱[支援的生命週期服務套件](https://go.microsoft.com/fwlink/p/?LinkId=31975)。</span><span class="sxs-lookup"><span data-stu-id="99c5d-121">To find the support timelines for your product, see the [Lifecycle Supported Service Packs](https://go.microsoft.com/fwlink/p/?LinkId=31975).</span></span> <span data-ttu-id="99c5d-122">如需詳細資訊，請參閱[Microsoft 支援週期支援原則的常見問題](https://go.microsoft.com/fwlink/p/?LinkId=31976)。</span><span class="sxs-lookup"><span data-stu-id="99c5d-122">See [Microsoft Support Lifecycle Support Policy FAQ](https://go.microsoft.com/fwlink/p/?LinkId=31976) for more information.</span></span>

 | <span data-ttu-id="99c5d-123">作業系統</span><span class="sxs-lookup"><span data-stu-id="99c5d-123">Operating System</span></span>                 | <span data-ttu-id="99c5d-124">Service Pack</span><span class="sxs-lookup"><span data-stu-id="99c5d-124">Service Pack</span></span> | <span data-ttu-id="99c5d-125">系統架構</span><span class="sxs-lookup"><span data-stu-id="99c5d-125">System Architecture</span></span> |
|----------------------------------|--------------|---------------------|
| <span data-ttu-id="99c5d-126">Microsoft Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="99c5d-126">Microsoft Windows Server 2019</span></span>    |              |        <span data-ttu-id="99c5d-127">64 位元</span><span class="sxs-lookup"><span data-stu-id="99c5d-127">64-bit</span></span>       |
| <span data-ttu-id="99c5d-128">Microsoft Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="99c5d-128">Microsoft Windows Server 2016</span></span>    |              |        <span data-ttu-id="99c5d-129">64 位元</span><span class="sxs-lookup"><span data-stu-id="99c5d-129">64-bit</span></span>       |
| <span data-ttu-id="99c5d-130">Microsoft Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="99c5d-130">Microsoft Windows Server 2012 R2</span></span> |              |        <span data-ttu-id="99c5d-131">64 位元</span><span class="sxs-lookup"><span data-stu-id="99c5d-131">64-bit</span></span>       |
| <span data-ttu-id="99c5d-132">Microsoft Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="99c5d-132">Microsoft Windows Server 2012</span></span>    |              |        <span data-ttu-id="99c5d-133">64 位元</span><span class="sxs-lookup"><span data-stu-id="99c5d-133">64-bit</span></span>       |
| <span data-ttu-id="99c5d-134">Microsoft Windows Server 2008 R2[外延安全更新](https://www.microsoft.com/windows-server/extended-security-updates)</span><span class="sxs-lookup"><span data-stu-id="99c5d-134">Microsoft Windows Server 2008 R2 [Extended Security Update](https://www.microsoft.com/windows-server/extended-security-updates)</span></span>|      <span data-ttu-id="99c5d-135">SP1</span><span class="sxs-lookup"><span data-stu-id="99c5d-135">SP1</span></span>     |        <span data-ttu-id="99c5d-136">64 位元</span><span class="sxs-lookup"><span data-stu-id="99c5d-136">64-bit</span></span>       |
 

<span data-ttu-id="99c5d-137">**重要** 不支援將管理伺服器角色部署到已啟用遠端桌面共用（RDS）的電腦。</span><span class="sxs-lookup"><span data-stu-id="99c5d-137">**Important** Deployment of the Management server role to a computer with Remote Desktop Sharing (RDS) enabled is not supported.</span></span>

 

### <a href="" id="management-server-hardware-requirements-"></a><span data-ttu-id="99c5d-138">管理伺服器硬體需求</span><span class="sxs-lookup"><span data-stu-id="99c5d-138">Management server hardware requirements</span></span>

-   <span data-ttu-id="99c5d-139">處理器-1.4 GHz 或更快的64位（x64）處理器</span><span class="sxs-lookup"><span data-stu-id="99c5d-139">Processor—1.4 GHz or faster, 64-bit (x64) processor</span></span>

-   <span data-ttu-id="99c5d-140">RAM-1 GB RAM （64位）</span><span class="sxs-lookup"><span data-stu-id="99c5d-140">RAM—1 GB RAM (64-bit)</span></span>

-   <span data-ttu-id="99c5d-141">磁碟空間-200 MB 可用硬碟空間，不含內容目錄</span><span class="sxs-lookup"><span data-stu-id="99c5d-141">Disk space—200 MB available hard disk space, not including the content directory</span></span>

### <span data-ttu-id="99c5d-142">管理伺服器資料庫需求</span><span class="sxs-lookup"><span data-stu-id="99c5d-142">Management server database requirements</span></span>

<span data-ttu-id="99c5d-143">下表列出應用程式 V 5.1 管理資料庫安裝所支援的 SQL Server 版本。</span><span class="sxs-lookup"><span data-stu-id="99c5d-143">The following table lists the SQL Server versions that are supported for the App-V 5.1 Management database installation.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="99c5d-144">SQL Server 版本</span><span class="sxs-lookup"><span data-stu-id="99c5d-144">SQL Server version</span></span></th>
<th align="left"><span data-ttu-id="99c5d-145">Service pack</span><span class="sxs-lookup"><span data-stu-id="99c5d-145">Service pack</span></span></th>
<th align="left"><span data-ttu-id="99c5d-146">系統架構</span><span class="sxs-lookup"><span data-stu-id="99c5d-146">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="even">
<td align="left"><p><span data-ttu-id="99c5d-147">Microsoft SQL Server 2019</span><span class="sxs-lookup"><span data-stu-id="99c5d-147">Microsoft SQL Server 2019</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="99c5d-148">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="99c5d-148">32-bit or 64-bit</span></span></p></td>
</tr>

<tr class="odd">
<td align="left"><p><span data-ttu-id="99c5d-149">Microsoft SQL Server 2017</span><span class="sxs-lookup"><span data-stu-id="99c5d-149">Microsoft SQL Server 2017</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="99c5d-150">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="99c5d-150">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="99c5d-151">Microsoft SQL Server 2016</span><span class="sxs-lookup"><span data-stu-id="99c5d-151">Microsoft SQL Server 2016</span></span></p></td>
<td align="left"><p><span data-ttu-id="99c5d-152">SP2</span><span class="sxs-lookup"><span data-stu-id="99c5d-152">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="99c5d-153">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="99c5d-153">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="99c5d-154">Microsoft SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="99c5d-154">Microsoft SQL Server 2014</span></span></p></td>
<td align="left"><p><span data-ttu-id="99c5d-155">SP2</span><span class="sxs-lookup"><span data-stu-id="99c5d-155">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="99c5d-156">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="99c5d-156">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="99c5d-157">Microsoft SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="99c5d-157">Microsoft SQL Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="99c5d-158">SP2</span><span class="sxs-lookup"><span data-stu-id="99c5d-158">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="99c5d-159">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="99c5d-159">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="99c5d-160">Microsoft SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="99c5d-160">Microsoft SQL Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="99c5d-161">SP3</span><span class="sxs-lookup"><span data-stu-id="99c5d-161">SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="99c5d-162">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="99c5d-162">32-bit or 64-bit</span></span></p></td>
</tr>
</tbody>
</table>

<span data-ttu-id="99c5d-163">如需有關 SQL server 2016 或更新版本的使用者設定檔的詳細資訊，請參閱[支援文章](https://support.microsoft.com/help/4548751/app-v-server-publishing-might-fail-when-you-apply-user-configuration-f)。</span><span class="sxs-lookup"><span data-stu-id="99c5d-163">For more information on user configuration files with SQL server 2016 or later, see the [support article](https://support.microsoft.com/help/4548751/app-v-server-publishing-might-fail-when-you-apply-user-configuration-f).</span></span>

### <span data-ttu-id="99c5d-164">發佈伺服器作業系統需求</span><span class="sxs-lookup"><span data-stu-id="99c5d-164">Publishing server operating system requirements</span></span>

<span data-ttu-id="99c5d-165">下表列出 App-V 5.1 發佈伺服器安裝所支援的作業系統。</span><span class="sxs-lookup"><span data-stu-id="99c5d-165">The following table lists the operating systems that are supported for the App-V 5.1 Publishing server installation.</span></span>

| <span data-ttu-id="99c5d-166">作業系統</span><span class="sxs-lookup"><span data-stu-id="99c5d-166">Operating System</span></span>                 | <span data-ttu-id="99c5d-167">Service Pack</span><span class="sxs-lookup"><span data-stu-id="99c5d-167">Service Pack</span></span> | <span data-ttu-id="99c5d-168">系統架構</span><span class="sxs-lookup"><span data-stu-id="99c5d-168">System Architecture</span></span> |
|----------------------------------|--------------|---------------------|
| <span data-ttu-id="99c5d-169">Microsoft Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="99c5d-169">Microsoft Windows Server 2019</span></span>    |              |        <span data-ttu-id="99c5d-170">64 位元</span><span class="sxs-lookup"><span data-stu-id="99c5d-170">64-bit</span></span>       |
| <span data-ttu-id="99c5d-171">Microsoft Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="99c5d-171">Microsoft Windows Server 2016</span></span>    |              |        <span data-ttu-id="99c5d-172">64 位元</span><span class="sxs-lookup"><span data-stu-id="99c5d-172">64-bit</span></span>       |
| <span data-ttu-id="99c5d-173">Microsoft Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="99c5d-173">Microsoft Windows Server 2012 R2</span></span> |              |        <span data-ttu-id="99c5d-174">64 位元</span><span class="sxs-lookup"><span data-stu-id="99c5d-174">64-bit</span></span>       |
| <span data-ttu-id="99c5d-175">Microsoft Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="99c5d-175">Microsoft Windows Server 2012</span></span>    |              |        <span data-ttu-id="99c5d-176">64 位元</span><span class="sxs-lookup"><span data-stu-id="99c5d-176">64-bit</span></span>       |
| <span data-ttu-id="99c5d-177">Microsoft Windows Server 2008 R2[外延安全更新](https://www.microsoft.com/windows-server/extended-security-updates)</span><span class="sxs-lookup"><span data-stu-id="99c5d-177">Microsoft Windows Server 2008 R2 [Extended Security Update](https://www.microsoft.com/windows-server/extended-security-updates)</span></span> |      <span data-ttu-id="99c5d-178">SP1</span><span class="sxs-lookup"><span data-stu-id="99c5d-178">SP1</span></span>     |        <span data-ttu-id="99c5d-179">64 位元</span><span class="sxs-lookup"><span data-stu-id="99c5d-179">64-bit</span></span>       |

### <a href="" id="publishing-server-hardware-requirements-"></a><span data-ttu-id="99c5d-180">發佈伺服器硬體需求</span><span class="sxs-lookup"><span data-stu-id="99c5d-180">Publishing server hardware requirements</span></span>

<span data-ttu-id="99c5d-181">App-V 不會在 Windows 伺服器以外的其他需求中新增其他需求。</span><span class="sxs-lookup"><span data-stu-id="99c5d-181">App-V adds no additional requirements beyond those of Windows Server.</span></span>

-   <span data-ttu-id="99c5d-182">處理器-1.4 GHz 或更快的64位（x64）處理器</span><span class="sxs-lookup"><span data-stu-id="99c5d-182">Processor—1.4 GHz or faster, 64-bit (x64) processor</span></span>

-   <span data-ttu-id="99c5d-183">RAM-2 GB RAM （64位）</span><span class="sxs-lookup"><span data-stu-id="99c5d-183">RAM—2 GB RAM (64-bit)</span></span>

-   <span data-ttu-id="99c5d-184">磁碟空間-200 MB 可用硬碟空間，不含內容目錄</span><span class="sxs-lookup"><span data-stu-id="99c5d-184">Disk space—200 MB available hard disk space, not including the content directory</span></span>

### <span data-ttu-id="99c5d-185">報表伺服器作業系統需求</span><span class="sxs-lookup"><span data-stu-id="99c5d-185">Reporting server operating system requirements</span></span>

<span data-ttu-id="99c5d-186">下表列出 App-V 5.1 報表服務器安裝支援的作業系統。</span><span class="sxs-lookup"><span data-stu-id="99c5d-186">The following table lists the operating systems that are supported for the App-V 5.1 Reporting server installation.</span></span>

| <span data-ttu-id="99c5d-187">作業系統</span><span class="sxs-lookup"><span data-stu-id="99c5d-187">Operating System</span></span>                 | <span data-ttu-id="99c5d-188">Service Pack</span><span class="sxs-lookup"><span data-stu-id="99c5d-188">Service Pack</span></span> | <span data-ttu-id="99c5d-189">系統架構</span><span class="sxs-lookup"><span data-stu-id="99c5d-189">System Architecture</span></span> |
|----------------------------------|--------------|---------------------|
| <span data-ttu-id="99c5d-190">Microsoft Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="99c5d-190">Microsoft Windows Server 2019</span></span>    |              |        <span data-ttu-id="99c5d-191">64 位元</span><span class="sxs-lookup"><span data-stu-id="99c5d-191">64-bit</span></span>       |
| <span data-ttu-id="99c5d-192">Microsoft Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="99c5d-192">Microsoft Windows Server 2016</span></span>    |              |        <span data-ttu-id="99c5d-193">64 位元</span><span class="sxs-lookup"><span data-stu-id="99c5d-193">64-bit</span></span>       |
| <span data-ttu-id="99c5d-194">Microsoft Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="99c5d-194">Microsoft Windows Server 2012 R2</span></span> |              |        <span data-ttu-id="99c5d-195">64 位元</span><span class="sxs-lookup"><span data-stu-id="99c5d-195">64-bit</span></span>       |
| <span data-ttu-id="99c5d-196">Microsoft Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="99c5d-196">Microsoft Windows Server 2012</span></span>    |              |        <span data-ttu-id="99c5d-197">64 位元</span><span class="sxs-lookup"><span data-stu-id="99c5d-197">64-bit</span></span>       |
| <span data-ttu-id="99c5d-198">Microsoft Windows Server 2008 R2[外延安全更新](https://www.microsoft.com/windows-server/extended-security-updates)</span><span class="sxs-lookup"><span data-stu-id="99c5d-198">Microsoft Windows Server 2008 R2 [Extended Security Update](https://www.microsoft.com/windows-server/extended-security-updates)</span></span> |      <span data-ttu-id="99c5d-199">SP1</span><span class="sxs-lookup"><span data-stu-id="99c5d-199">SP1</span></span>     |        <span data-ttu-id="99c5d-200">64 位元</span><span class="sxs-lookup"><span data-stu-id="99c5d-200">64-bit</span></span>       |

### <a href="" id="reporting-server-hardware-requirements-"></a><span data-ttu-id="99c5d-201">報表服務器硬體需求</span><span class="sxs-lookup"><span data-stu-id="99c5d-201">Reporting server hardware requirements</span></span>

<span data-ttu-id="99c5d-202">App-V 不會在 Windows 伺服器以外的其他需求中新增其他需求。</span><span class="sxs-lookup"><span data-stu-id="99c5d-202">App-V adds no additional requirements beyond those of Windows Server.</span></span>

-   <span data-ttu-id="99c5d-203">處理器-1.4 GHz 或更快的64位（x64）處理器</span><span class="sxs-lookup"><span data-stu-id="99c5d-203">Processor—1.4 GHz or faster, 64-bit (x64) processor</span></span>

-   <span data-ttu-id="99c5d-204">RAM-2 GB RAM （64位）</span><span class="sxs-lookup"><span data-stu-id="99c5d-204">RAM—2 GB RAM (64-bit)</span></span>

-   <span data-ttu-id="99c5d-205">磁碟空間-200 MB 可用硬碟空間</span><span class="sxs-lookup"><span data-stu-id="99c5d-205">Disk space—200 MB available hard disk space</span></span>

### <span data-ttu-id="99c5d-206">報表伺服器資料庫需求</span><span class="sxs-lookup"><span data-stu-id="99c5d-206">Reporting server database requirements</span></span>

<span data-ttu-id="99c5d-207">下表列出 App-V 5.1 報告資料庫安裝支援的 SQL Server 版本。</span><span class="sxs-lookup"><span data-stu-id="99c5d-207">The following table lists the SQL Server versions that are supported for the App-V 5.1 Reporting database installation.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="99c5d-208">SQL Server 版本</span><span class="sxs-lookup"><span data-stu-id="99c5d-208">SQL Server version</span></span></th>
<th align="left"><span data-ttu-id="99c5d-209">Service pack</span><span class="sxs-lookup"><span data-stu-id="99c5d-209">Service pack</span></span></th>
<th align="left"><span data-ttu-id="99c5d-210">系統架構</span><span class="sxs-lookup"><span data-stu-id="99c5d-210">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="99c5d-211">Microsoft SQL Server 2017</span><span class="sxs-lookup"><span data-stu-id="99c5d-211">Microsoft SQL Server 2017</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="99c5d-212">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="99c5d-212">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="99c5d-213">Microsoft SQL Server 2016</span><span class="sxs-lookup"><span data-stu-id="99c5d-213">Microsoft SQL Server 2016</span></span></p></td>
<td align="left"><p><span data-ttu-id="99c5d-214">SP2</span><span class="sxs-lookup"><span data-stu-id="99c5d-214">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="99c5d-215">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="99c5d-215">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="99c5d-216">Microsoft SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="99c5d-216">Microsoft SQL Server 2014</span></span></p></td>
<td align="left"><p><span data-ttu-id="99c5d-217">SP2</span><span class="sxs-lookup"><span data-stu-id="99c5d-217">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="99c5d-218">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="99c5d-218">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="99c5d-219">Microsoft SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="99c5d-219">Microsoft SQL Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="99c5d-220">SP2</span><span class="sxs-lookup"><span data-stu-id="99c5d-220">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="99c5d-221">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="99c5d-221">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="99c5d-222">Microsoft SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="99c5d-222">Microsoft SQL Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="99c5d-223">SP3</span><span class="sxs-lookup"><span data-stu-id="99c5d-223">SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="99c5d-224">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="99c5d-224">32-bit or 64-bit</span></span></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-client-supp-cfgs"></a><span data-ttu-id="99c5d-225">App-V 用戶端系統需求</span><span class="sxs-lookup"><span data-stu-id="99c5d-225">App-V client system requirements</span></span>

<span data-ttu-id="99c5d-226">下表列出 App-V 5.1 用戶端安裝支援的作業系統。</span><span class="sxs-lookup"><span data-stu-id="99c5d-226">The following table lists the operating systems that are supported for the App-V 5.1 client installation.</span></span>

> [!NOTE]
> <span data-ttu-id="99c5d-227">在 Windows 10 周年紀念版本（亦即1607版本）中，App-v 用戶端是內置的，將會封鎖任何舊版的 App-v 用戶端安裝</span><span class="sxs-lookup"><span data-stu-id="99c5d-227">With the Windows 10 Anniversary release (aka 1607 version), the App-V client is in-box and will block installation of any previous version of the App-V client</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="99c5d-228">作業系統</span><span class="sxs-lookup"><span data-stu-id="99c5d-228">Operating system</span></span></th>
<th align="left"><span data-ttu-id="99c5d-229">Service pack</span><span class="sxs-lookup"><span data-stu-id="99c5d-229">Service pack</span></span></th>
<th align="left"><span data-ttu-id="99c5d-230">系統架構</span><span class="sxs-lookup"><span data-stu-id="99c5d-230">System architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="99c5d-231">Microsoft Windows10 （預1607版）</span><span class="sxs-lookup"><span data-stu-id="99c5d-231">Microsoft Windows10 (pre-1607 version)</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="99c5d-232">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="99c5d-232">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="99c5d-233">Microsoft Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="99c5d-233">Microsoft Windows8.1</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="99c5d-234">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="99c5d-234">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="99c5d-235">Windows7</span><span class="sxs-lookup"><span data-stu-id="99c5d-235">Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="99c5d-236">SP1</span><span class="sxs-lookup"><span data-stu-id="99c5d-236">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="99c5d-237">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="99c5d-237">32-bit or 64-bit</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="99c5d-238">下列 App-V 用戶端安裝案例不受支援，但說明：</span><span class="sxs-lookup"><span data-stu-id="99c5d-238">The following App-V client installation scenarios are not supported, except as noted:</span></span>

-   <span data-ttu-id="99c5d-239">執行 Windows Server 的電腦</span><span class="sxs-lookup"><span data-stu-id="99c5d-239">Computers that run Windows Server</span></span>

-   <span data-ttu-id="99c5d-240">執行 App-V 4.6 SP1 或較舊版本的電腦</span><span class="sxs-lookup"><span data-stu-id="99c5d-240">Computers that run App-V4.6SP1 or earlier versions</span></span>

-   <span data-ttu-id="99c5d-241">只有啟用 RDS 的伺服器才支援 App-v 5.1 遠端桌面服務用戶端</span><span class="sxs-lookup"><span data-stu-id="99c5d-241">The App-V 5.1 Remote Desktop services client is supported only for RDS-enabled servers</span></span>

### <a href="" id="app-v-client-hardware-requirements-"></a><span data-ttu-id="99c5d-242">App-V 用戶端的硬體需求</span><span class="sxs-lookup"><span data-stu-id="99c5d-242">App-V client hardware requirements</span></span>

<span data-ttu-id="99c5d-243">下列清單顯示 App-V 5.1 用戶端安裝所支援的硬體設定。</span><span class="sxs-lookup"><span data-stu-id="99c5d-243">The following list displays the supported hardware configuration for the App-V 5.1 client installation.</span></span>

-   <span data-ttu-id="99c5d-244">處理器-1.4 GHz 或更快的32位（x86）或64位（x64）處理器</span><span class="sxs-lookup"><span data-stu-id="99c5d-244">Processor— 1.4 GHz or faster 32-bit (x86) or 64-bit (x64) processor</span></span>

-   <span data-ttu-id="99c5d-245">RAM-1 GB （32位）或 2 GB （64位）</span><span class="sxs-lookup"><span data-stu-id="99c5d-245">RAM— 1 GB (32-bit) or 2 GB (64-bit)</span></span>

-   <span data-ttu-id="99c5d-246">磁片：安裝 100 MB，不包括虛擬化應用程式所使用的磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="99c5d-246">Disk— 100 MB for installation, not including the disk space that is used by virtualized applications.</span></span>

## <span data-ttu-id="99c5d-247">遠端桌面服務用戶端的系統需求</span><span class="sxs-lookup"><span data-stu-id="99c5d-247">Remote Desktop Services client system requirements</span></span>


<span data-ttu-id="99c5d-248">下表列出 App-V 5.1 遠端桌面服務（RDS）用戶端安裝所支援的作業系統。</span><span class="sxs-lookup"><span data-stu-id="99c5d-248">The following table lists the operating systems that are supported for App-V 5.1 Remote Desktop Services (RDS) client installation.</span></span>

| <span data-ttu-id="99c5d-249">作業系統</span><span class="sxs-lookup"><span data-stu-id="99c5d-249">Operating System</span></span>                 | <span data-ttu-id="99c5d-250">Service Pack</span><span class="sxs-lookup"><span data-stu-id="99c5d-250">Service Pack</span></span> | <span data-ttu-id="99c5d-251">系統架構</span><span class="sxs-lookup"><span data-stu-id="99c5d-251">System Architecture</span></span> |
|----------------------------------|--------------|---------------------|
| <span data-ttu-id="99c5d-252">Microsoft Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="99c5d-252">Microsoft Windows Server 2019</span></span>    |              |        <span data-ttu-id="99c5d-253">64 位元</span><span class="sxs-lookup"><span data-stu-id="99c5d-253">64-bit</span></span>       |
| <span data-ttu-id="99c5d-254">Microsoft Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="99c5d-254">Microsoft Windows Server 2016</span></span>    |              |        <span data-ttu-id="99c5d-255">64 位元</span><span class="sxs-lookup"><span data-stu-id="99c5d-255">64-bit</span></span>       |
| <span data-ttu-id="99c5d-256">Microsoft Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="99c5d-256">Microsoft Windows Server 2012 R2</span></span> |              |        <span data-ttu-id="99c5d-257">64 位元</span><span class="sxs-lookup"><span data-stu-id="99c5d-257">64-bit</span></span>       |
| <span data-ttu-id="99c5d-258">Microsoft Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="99c5d-258">Microsoft Windows Server 2012</span></span>    |              |        <span data-ttu-id="99c5d-259">64 位元</span><span class="sxs-lookup"><span data-stu-id="99c5d-259">64-bit</span></span>       |
| <span data-ttu-id="99c5d-260">Microsoft Windows Server 2008 R2[外延安全更新](https://www.microsoft.com/windows-server/extended-security-updates)</span><span class="sxs-lookup"><span data-stu-id="99c5d-260">Microsoft Windows Server 2008 R2 [Extended Security Update](https://www.microsoft.com/windows-server/extended-security-updates)</span></span> |      <span data-ttu-id="99c5d-261">SP1</span><span class="sxs-lookup"><span data-stu-id="99c5d-261">SP1</span></span>     |        <span data-ttu-id="99c5d-262">64 位元</span><span class="sxs-lookup"><span data-stu-id="99c5d-262">64-bit</span></span>       |

### <span data-ttu-id="99c5d-263">遠端桌面服務用戶端的硬體需求</span><span class="sxs-lookup"><span data-stu-id="99c5d-263">Remote Desktop Services client hardware requirements</span></span>

<span data-ttu-id="99c5d-264">App-V 不會在 Windows 伺服器以外的其他需求中新增其他需求。</span><span class="sxs-lookup"><span data-stu-id="99c5d-264">App-V adds no additional requirements beyond those of Windows Server.</span></span>

-   <span data-ttu-id="99c5d-265">處理器-1.4 GHz 或更快的64位（x64）處理器</span><span class="sxs-lookup"><span data-stu-id="99c5d-265">Processor—1.4 GHz or faster, 64-bit (x64) processor</span></span>

-   <span data-ttu-id="99c5d-266">RAM-2 GB RAM （64位）</span><span class="sxs-lookup"><span data-stu-id="99c5d-266">RAM—2 GB RAM (64-bit)</span></span>

-   <span data-ttu-id="99c5d-267">磁碟空間-200 MB 可用硬碟空間</span><span class="sxs-lookup"><span data-stu-id="99c5d-267">Disk space—200 MB available hard disk space</span></span>

## <span data-ttu-id="99c5d-268">Sequencer 系統需求</span><span class="sxs-lookup"><span data-stu-id="99c5d-268">Sequencer system requirements</span></span>

<span data-ttu-id="99c5d-269">下表列出應用程式 V 5.1 排序器安裝所支援的作業系統。</span><span class="sxs-lookup"><span data-stu-id="99c5d-269">The following table lists the operating systems that are supported for the App-V 5.1 Sequencer installation.</span></span>

| <span data-ttu-id="99c5d-270">作業系統</span><span class="sxs-lookup"><span data-stu-id="99c5d-270">Operating System</span></span>                 | <span data-ttu-id="99c5d-271">Service Pack</span><span class="sxs-lookup"><span data-stu-id="99c5d-271">Service Pack</span></span> | <span data-ttu-id="99c5d-272">系統架構</span><span class="sxs-lookup"><span data-stu-id="99c5d-272">System Architecture</span></span> |
|----------------------------------|--------------|---------------------|
| <span data-ttu-id="99c5d-273">Microsoft Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="99c5d-273">Microsoft Windows Server 2019</span></span>    |              |        <span data-ttu-id="99c5d-274">64 位元</span><span class="sxs-lookup"><span data-stu-id="99c5d-274">64-bit</span></span>       |
| <span data-ttu-id="99c5d-275">Microsoft Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="99c5d-275">Microsoft Windows Server 2016</span></span>    |              |        <span data-ttu-id="99c5d-276">64 位元</span><span class="sxs-lookup"><span data-stu-id="99c5d-276">64-bit</span></span>       |
| <span data-ttu-id="99c5d-277">Microsoft Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="99c5d-277">Microsoft Windows Server 2012 R2</span></span> |              |        <span data-ttu-id="99c5d-278">64 位元</span><span class="sxs-lookup"><span data-stu-id="99c5d-278">64-bit</span></span>       |
| <span data-ttu-id="99c5d-279">Microsoft Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="99c5d-279">Microsoft Windows Server 2012</span></span>    |              |        <span data-ttu-id="99c5d-280">64 位元</span><span class="sxs-lookup"><span data-stu-id="99c5d-280">64-bit</span></span>       |
| <span data-ttu-id="99c5d-281">Microsoft Windows Server 2008 R2[外延安全更新](https://www.microsoft.com/windows-server/extended-security-updates)</span><span class="sxs-lookup"><span data-stu-id="99c5d-281">Microsoft Windows Server 2008 R2 [Extended Security Update](https://www.microsoft.com/windows-server/extended-security-updates)</span></span> |      <span data-ttu-id="99c5d-282">SP1</span><span class="sxs-lookup"><span data-stu-id="99c5d-282">SP1</span></span>     |        <span data-ttu-id="99c5d-283">64 位元</span><span class="sxs-lookup"><span data-stu-id="99c5d-283">64-bit</span></span>       |
| <span data-ttu-id="99c5d-284">Microsoft Windows 10</span><span class="sxs-lookup"><span data-stu-id="99c5d-284">Microsoft Windows 10</span></span>             |              | <span data-ttu-id="99c5d-285">32 位元與 64 位元</span><span class="sxs-lookup"><span data-stu-id="99c5d-285">32-bit and 64-bit</span></span>   |
| <span data-ttu-id="99c5d-286">Microsoft Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="99c5d-286">Microsoft Windows 8.1</span></span>            |              | <span data-ttu-id="99c5d-287">32 位元與 64 位元</span><span class="sxs-lookup"><span data-stu-id="99c5d-287">32-bit and 64-bit</span></span>   |
| <span data-ttu-id="99c5d-288">Microsoft Windows 7</span><span class="sxs-lookup"><span data-stu-id="99c5d-288">Microsoft Windows 7</span></span>              |      <span data-ttu-id="99c5d-289">SP1</span><span class="sxs-lookup"><span data-stu-id="99c5d-289">SP1</span></span>     | <span data-ttu-id="99c5d-290">32 位元與 64 位元</span><span class="sxs-lookup"><span data-stu-id="99c5d-290">32-bit and 64-bit</span></span>   |

### <span data-ttu-id="99c5d-291">Sequencer 硬體需求</span><span class="sxs-lookup"><span data-stu-id="99c5d-291">Sequencer hardware requirements</span></span>

<span data-ttu-id="99c5d-292">如需硬體需求，請參閱 Windows 或 Windows Server 檔。</span><span class="sxs-lookup"><span data-stu-id="99c5d-292">See the Windows or Windows Server documentation for the hardware requirements.</span></span> <span data-ttu-id="99c5d-293">App-v 不會增加任何額外的硬體需求。</span><span class="sxs-lookup"><span data-stu-id="99c5d-293">App-V adds no additional hardware requirements.</span></span>

## <a href="" id="bkmk-supp-ver-sccm"></a><span data-ttu-id="99c5d-294">系統中心 Configuration Manager 支援的版本</span><span class="sxs-lookup"><span data-stu-id="99c5d-294">Supported versions of System Center Configuration Manager</span></span>

<span data-ttu-id="99c5d-295">App-V 用戶端支援下列版本的 System Center Configuration Manager：</span><span class="sxs-lookup"><span data-stu-id="99c5d-295">The App-V client supports the following versions of System Center Configuration Manager:</span></span>

-   <span data-ttu-id="99c5d-296">MicrosoftSystemCenter2012 ConfigurationManager</span><span class="sxs-lookup"><span data-stu-id="99c5d-296">MicrosoftSystemCenter2012 ConfigurationManager</span></span>

-   <span data-ttu-id="99c5d-297">System Center 2012 R2 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="99c5d-297">System Center 2012 R2 Configuration Manager</span></span>

-   <span data-ttu-id="99c5d-298">System Center 2012 R2 Configuration Manager SP1</span><span class="sxs-lookup"><span data-stu-id="99c5d-298">System Center 2012 R2 Configuration Manager SP1</span></span>

<span data-ttu-id="99c5d-299">下列 App-V 和 System Center Configuration Manager 版本矩陣會顯示所有正式支援的 App-v 與 Configuration Manager 組合。</span><span class="sxs-lookup"><span data-stu-id="99c5d-299">The following App-V and System Center Configuration Manager version matrix shows all officially supported combinations of App-V and Configuration Manager.</span></span>

> [!NOTE]
> <span data-ttu-id="99c5d-300">App-v 4.5 和4.6 都已退出主流支援。</span><span class="sxs-lookup"><span data-stu-id="99c5d-300">Both App-V 4.5 and 4.6 have exited Mainstream support.</span></span>

<table>
<colgroup>
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
<col width="12%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="99c5d-301">App-V 版本</span><span class="sxs-lookup"><span data-stu-id="99c5d-301">App-V Version</span></span></th>
<th align="left"><span data-ttu-id="99c5d-302">System Center Configuration Manager 2007</span><span class="sxs-lookup"><span data-stu-id="99c5d-302">System Center Configuration Manager 2007</span></span></th>
<th align="left"><span data-ttu-id="99c5d-303">System Center 2012 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="99c5d-303">System Center 2012 Configuration Manager</span></span></th>
<th align="left"><span data-ttu-id="99c5d-304">System Center 2012 Configuration Manager SP1</span><span class="sxs-lookup"><span data-stu-id="99c5d-304">System Center 2012 Configuration Manager SP1</span></span></th>
<th align="left"><span data-ttu-id="99c5d-305">System Center 2012 R2 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="99c5d-305">System Center 2012 R2 Configuration Manager</span></span></th>
<th align="left"><span data-ttu-id="99c5d-306">System Center 2012 R2 Configuration Manager SP1</span><span class="sxs-lookup"><span data-stu-id="99c5d-306">System Center 2012 R2 Configuration Manager SP1</span></span></th>
<th align="left"><span data-ttu-id="99c5d-307">System Center 2012 Configuration Manager SP2</span><span class="sxs-lookup"><span data-stu-id="99c5d-307">System Center 2012 Configuration Manager SP2</span></span></th>
<th align="left"><span data-ttu-id="99c5d-308">System Center Configuration Manager 版本1511</span><span class="sxs-lookup"><span data-stu-id="99c5d-308">System Center Configuration Manager Version 1511</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="99c5d-309">App-V 5.0 SP3</span><span class="sxs-lookup"><span data-stu-id="99c5d-309">App-V 5.0 SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="99c5d-310">僅限 MSI-包裝</span><span class="sxs-lookup"><span data-stu-id="99c5d-310">MSI-Wrapper Only</span></span></p></td>
<td align="left"><p><span data-ttu-id="99c5d-311">否</span><span class="sxs-lookup"><span data-stu-id="99c5d-311">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="99c5d-312">2012 SP1 CU4</span><span class="sxs-lookup"><span data-stu-id="99c5d-312">2012 SP1 CU4</span></span></p></td>
<td align="left"><p><span data-ttu-id="99c5d-313">2012 R2 CU1</span><span class="sxs-lookup"><span data-stu-id="99c5d-313">2012 R2 CU1</span></span></p></td>
<td align="left"><p><span data-ttu-id="99c5d-314">是</span><span class="sxs-lookup"><span data-stu-id="99c5d-314">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="99c5d-315">是</span><span class="sxs-lookup"><span data-stu-id="99c5d-315">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="99c5d-316">是</span><span class="sxs-lookup"><span data-stu-id="99c5d-316">Yes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="99c5d-317">App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="99c5d-317">App-V 5.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="99c5d-318">僅限 MSI-包裝</span><span class="sxs-lookup"><span data-stu-id="99c5d-318">MSI-Wrapper Only</span></span></p></td>
<td align="left"><p><span data-ttu-id="99c5d-319">否</span><span class="sxs-lookup"><span data-stu-id="99c5d-319">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="99c5d-320">2012 SP1 CU4</span><span class="sxs-lookup"><span data-stu-id="99c5d-320">2012 SP1 CU4</span></span></p></td>
<td align="left"><p><span data-ttu-id="99c5d-321">2012 R2 CU1</span><span class="sxs-lookup"><span data-stu-id="99c5d-321">2012 R2 CU1</span></span></p></td>
<td align="left"><p><span data-ttu-id="99c5d-322">是</span><span class="sxs-lookup"><span data-stu-id="99c5d-322">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="99c5d-323">是</span><span class="sxs-lookup"><span data-stu-id="99c5d-323">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="99c5d-324">是</span><span class="sxs-lookup"><span data-stu-id="99c5d-324">Yes</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="99c5d-325">如需 Configuration Manager 與 App-v 整合的詳細資訊，請參閱[規劃 app-v 與 Configuration Manager 整合](https://technet.microsoft.com/library/jj822982.aspx)。</span><span class="sxs-lookup"><span data-stu-id="99c5d-325">For more information about how Configuration Manager integrates with App-V, see [Planning for App-V Integration with Configuration Manager](https://technet.microsoft.com/library/jj822982.aspx).</span></span>

## <span data-ttu-id="99c5d-326">相關主題</span><span class="sxs-lookup"><span data-stu-id="99c5d-326">Related topics</span></span>

[<span data-ttu-id="99c5d-327">規劃部署 App-V</span><span class="sxs-lookup"><span data-stu-id="99c5d-327">Planning to Deploy App-V</span></span>](planning-to-deploy-app-v51.md)

[<span data-ttu-id="99c5d-328">App-V 5.1 必要條件</span><span class="sxs-lookup"><span data-stu-id="99c5d-328">App-V 5.1 Prerequisites</span></span>](app-v-51-prerequisites.md)
