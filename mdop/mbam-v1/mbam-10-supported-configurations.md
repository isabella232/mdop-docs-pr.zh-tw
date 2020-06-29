---
title: MBAM 1.0 支援的組態
description: MBAM 1.0 支援的組態
author: dansimp
ms.assetid: 1f5ac58e-6a3f-47df-8a9b-4b57631ab9ee
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 2c72320379d1c9328a6b40537d37998402b1b38b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811456"
---
# <span data-ttu-id="bfabb-103">MBAM 1.0 支援的組態</span><span class="sxs-lookup"><span data-stu-id="bfabb-103">MBAM 1.0 Supported Configurations</span></span>


<span data-ttu-id="bfabb-104">本主題將說明在您的環境中安裝並執行 Microsoft BitLocker 管理和監控（MBAM）的必要需求。</span><span class="sxs-lookup"><span data-stu-id="bfabb-104">This topic specifies the necessary requirements to install and run Microsoft BitLocker Administration and Monitoring (MBAM) in your environment.</span></span>

## <a href="" id="---------mbam-server-system-requirements"></a> <span data-ttu-id="bfabb-105">MBAM 伺服器系統需求</span><span class="sxs-lookup"><span data-stu-id="bfabb-105">MBAM server system Requirements</span></span>


### <span data-ttu-id="bfabb-106">伺服器作業系統需求</span><span class="sxs-lookup"><span data-stu-id="bfabb-106">Server operating system requirements</span></span>

<span data-ttu-id="bfabb-107">下表列出 Microsoft BitLocker 系統管理和監視伺服器安裝支援的作業系統。</span><span class="sxs-lookup"><span data-stu-id="bfabb-107">The following table lists the operating systems that are supported for the Microsoft BitLocker Administration and Monitoring Server installation.</span></span>

**<span data-ttu-id="bfabb-108">注意</span><span class="sxs-lookup"><span data-stu-id="bfabb-108">Note</span></span>**  
<span data-ttu-id="bfabb-109">Microsoft 提供目前 service pack 的支援，在某些情況下，也是最前面的 service pack。</span><span class="sxs-lookup"><span data-stu-id="bfabb-109">Microsoft provides support for the current service pack and, in some cases, the immediately preceding service pack.</span></span> <span data-ttu-id="bfabb-110">若要尋找您產品的支援時程表，請參閱[支援的生命週期服務套件](https://go.microsoft.com/fwlink/p/?LinkId=31975)。</span><span class="sxs-lookup"><span data-stu-id="bfabb-110">To find the support timelines for your product, see the [Lifecycle Supported Service Packs](https://go.microsoft.com/fwlink/p/?LinkId=31975).</span></span> <span data-ttu-id="bfabb-111">如需 Microsoft 支援週期原則的其他相關資訊，請參閱[Microsoft 支援週期支援原則常見問題](https://go.microsoft.com/fwlink/p/?LinkId=31976)。</span><span class="sxs-lookup"><span data-stu-id="bfabb-111">For additional information about Microsoft Support Lifecycle Policy, see [Microsoft Support Lifecycle Support Policy FAQ](https://go.microsoft.com/fwlink/p/?LinkId=31976).</span></span>



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bfabb-112">作業系統</span><span class="sxs-lookup"><span data-stu-id="bfabb-112">Operating System</span></span></th>
<th align="left"><span data-ttu-id="bfabb-113">版本</span><span class="sxs-lookup"><span data-stu-id="bfabb-113">Edition</span></span></th>
<th align="left"><span data-ttu-id="bfabb-114">Service Pack</span><span class="sxs-lookup"><span data-stu-id="bfabb-114">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="bfabb-115">系統架構</span><span class="sxs-lookup"><span data-stu-id="bfabb-115">System Architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bfabb-116">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="bfabb-116">Windows Server 2008</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfabb-117">標準版、企業版、資料中心或 Web 服務器</span><span class="sxs-lookup"><span data-stu-id="bfabb-117">Standard, Enterprise, Datacenter, or Web Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfabb-118">僅限 SP2</span><span class="sxs-lookup"><span data-stu-id="bfabb-118">SP2 only</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfabb-119">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="bfabb-119">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bfabb-120">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="bfabb-120">Windows Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfabb-121">標準版、企業版、資料中心或 Web 服務器</span><span class="sxs-lookup"><span data-stu-id="bfabb-121">Standard, Enterprise, Datacenter, or Web Server</span></span></p></td>
<td align="left"></td>
<td align="left"><p><span data-ttu-id="bfabb-122">64 位元</span><span class="sxs-lookup"><span data-stu-id="bfabb-122">64-bit</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="bfabb-123">警告</span><span class="sxs-lookup"><span data-stu-id="bfabb-123">Warning</span></span>**  
<span data-ttu-id="bfabb-124">不支援在網網域控制站電腦上安裝 MBAM 服務、報表或資料庫。</span><span class="sxs-lookup"><span data-stu-id="bfabb-124">There is no support for installing MBAM services, reports, or databases on a domain controller computer.</span></span>



### <a href="" id="server-random-access-memory--ram--requirements-"></a><span data-ttu-id="bfabb-125">伺服器隨機存取記憶體（RAM）需求</span><span class="sxs-lookup"><span data-stu-id="bfabb-125">Server random access memory (RAM) requirements</span></span>

<span data-ttu-id="bfabb-126">沒有任何特定于 MBAM 伺服器安裝的 RAM 需求。</span><span class="sxs-lookup"><span data-stu-id="bfabb-126">There are no RAM requirements that are specific to MBAM Server installation.</span></span>

### <a href="" id="sql-server-database-requirements-"></a><span data-ttu-id="bfabb-127">SQL Server 資料庫需求</span><span class="sxs-lookup"><span data-stu-id="bfabb-127">SQL Server Database requirements</span></span>

<span data-ttu-id="bfabb-128">下表列出 MBAM 伺服器功能安裝支援的 SQL Server 版本。</span><span class="sxs-lookup"><span data-stu-id="bfabb-128">The following table lists the SQL Server versions that are supported for the MBAM Server feature installation.</span></span>

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
<th align="left"><span data-ttu-id="bfabb-129">MBAM Server 功能</span><span class="sxs-lookup"><span data-stu-id="bfabb-129">MBAM Server Feature</span></span></th>
<th align="left"><span data-ttu-id="bfabb-130">SQL Server 版本</span><span class="sxs-lookup"><span data-stu-id="bfabb-130">SQL Server Version</span></span></th>
<th align="left"><span data-ttu-id="bfabb-131">版本</span><span class="sxs-lookup"><span data-stu-id="bfabb-131">Edition</span></span></th>
<th align="left"><span data-ttu-id="bfabb-132">Service Pack</span><span class="sxs-lookup"><span data-stu-id="bfabb-132">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="bfabb-133">系統架構</span><span class="sxs-lookup"><span data-stu-id="bfabb-133">System Architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bfabb-134">合規性與審計報告</span><span class="sxs-lookup"><span data-stu-id="bfabb-134">Compliance and Audit Reports</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfabb-135">Microsoft SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="bfabb-135">Microsoft SQL Server 2008</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bfabb-136">R2、標準、企業、資料中心或開發人員版本</span><span class="sxs-lookup"><span data-stu-id="bfabb-136">R2, Standard, Enterprise, Datacenter, or Developer Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfabb-137">SP2</span><span class="sxs-lookup"><span data-stu-id="bfabb-137">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfabb-138">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="bfabb-138">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bfabb-139">恢復與硬體資料庫</span><span class="sxs-lookup"><span data-stu-id="bfabb-139">Recovery and Hardware Database</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfabb-140">Microsoft SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="bfabb-140">Microsoft SQL Server 2008</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bfabb-141">R2、企業版、資料中心或開發人員版本</span><span class="sxs-lookup"><span data-stu-id="bfabb-141">R2, Enterprise, Datacenter, or Developer Edition</span></span></p>
<div class="alert">
<strong><span data-ttu-id="bfabb-142">重要</span><span class="sxs-lookup"><span data-stu-id="bfabb-142">Important</span></span></strong><br/><p><span data-ttu-id="bfabb-143">MBAM 復原和硬體資料庫伺服器功能安裝不支援 SQL Server 標準版。</span><span class="sxs-lookup"><span data-stu-id="bfabb-143">SQL Server Standard Editions are not supported for MBAM Recovery and Hardware Database Server feature installation.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="bfabb-144">SP2</span><span class="sxs-lookup"><span data-stu-id="bfabb-144">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfabb-145">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="bfabb-145">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bfabb-146">合規性和審核資料庫</span><span class="sxs-lookup"><span data-stu-id="bfabb-146">Compliance and Audit Database</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfabb-147">Microsoft SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="bfabb-147">Microsoft SQL Server 2008</span></span> </p></td>
<td align="left"><p><span data-ttu-id="bfabb-148">R2、標準、企業、資料中心或開發人員版本</span><span class="sxs-lookup"><span data-stu-id="bfabb-148">R2, Standard, Enterprise, Datacenter, or Developer Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfabb-149">SP2</span><span class="sxs-lookup"><span data-stu-id="bfabb-149">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfabb-150">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="bfabb-150">32-bit or 64-bit</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="---------mbam-client-system-requirements"></a> <span data-ttu-id="bfabb-151">MBAM 用戶端系統需求</span><span class="sxs-lookup"><span data-stu-id="bfabb-151">MBAM Client system requirements</span></span>


### <span data-ttu-id="bfabb-152">用戶端作業系統需求</span><span class="sxs-lookup"><span data-stu-id="bfabb-152">Client operating system requirements</span></span>

<span data-ttu-id="bfabb-153">下表列出 MBAM 用戶端安裝支援的作業系統。</span><span class="sxs-lookup"><span data-stu-id="bfabb-153">The following table lists the operating systems that are supported for MBAM Client installation.</span></span>

**<span data-ttu-id="bfabb-154">注意</span><span class="sxs-lookup"><span data-stu-id="bfabb-154">Note</span></span>**  
<span data-ttu-id="bfabb-155">Microsoft 提供目前 service pack 的支援，在某些情況下，也是最前面的 service pack。</span><span class="sxs-lookup"><span data-stu-id="bfabb-155">Microsoft provides support for the current service pack and, in some cases, the immediately preceding service pack.</span></span> <span data-ttu-id="bfabb-156">若要尋找您產品的支援時程表，請參閱[支援的生命週期服務套件](https://go.microsoft.com/fwlink/p/?LinkId=31975)。</span><span class="sxs-lookup"><span data-stu-id="bfabb-156">To find the support timelines for your product, see the [Lifecycle Supported Service Packs](https://go.microsoft.com/fwlink/p/?LinkId=31975).</span></span> <span data-ttu-id="bfabb-157">如需 Microsoft 支援週期原則的其他相關資訊，請參閱[Microsoft 支援週期支援原則常見問題](https://go.microsoft.com/fwlink/p/?LinkId=31976)。</span><span class="sxs-lookup"><span data-stu-id="bfabb-157">For additional information about Microsoft Support Lifecycle Policy, see [Microsoft Support Lifecycle Support Policy FAQ](https://go.microsoft.com/fwlink/p/?LinkId=31976).</span></span>



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="bfabb-158">作業系統</span><span class="sxs-lookup"><span data-stu-id="bfabb-158">Operating System</span></span></th>
<th align="left"><span data-ttu-id="bfabb-159">版本</span><span class="sxs-lookup"><span data-stu-id="bfabb-159">Edition</span></span></th>
<th align="left"><span data-ttu-id="bfabb-160">Service Pack</span><span class="sxs-lookup"><span data-stu-id="bfabb-160">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="bfabb-161">系統架構</span><span class="sxs-lookup"><span data-stu-id="bfabb-161">System Architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="bfabb-162">Windows 7</span><span class="sxs-lookup"><span data-stu-id="bfabb-162">Windows 7</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfabb-163">企業版</span><span class="sxs-lookup"><span data-stu-id="bfabb-163">Enterprise Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfabb-164">無、SP1</span><span class="sxs-lookup"><span data-stu-id="bfabb-164">None, SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfabb-165">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="bfabb-165">32-bit or 64-bit</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="bfabb-166">Windows 7</span><span class="sxs-lookup"><span data-stu-id="bfabb-166">Windows 7</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfabb-167">旗艦版</span><span class="sxs-lookup"><span data-stu-id="bfabb-167">Ultimate Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfabb-168">無、SP1</span><span class="sxs-lookup"><span data-stu-id="bfabb-168">None, SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="bfabb-169">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="bfabb-169">32-bit or 64-bit</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="client-ram-requirements-"></a><span data-ttu-id="bfabb-170">用戶端 RAM 需求</span><span class="sxs-lookup"><span data-stu-id="bfabb-170">Client RAM requirements</span></span>

<span data-ttu-id="bfabb-171">不是 MBAM 用戶端安裝所特有的 RAM 需求。</span><span class="sxs-lookup"><span data-stu-id="bfabb-171">There are no RAM requirements that are specific to the MBAM Client installation.</span></span>

## <span data-ttu-id="bfabb-172">相關主題</span><span class="sxs-lookup"><span data-stu-id="bfabb-172">Related topics</span></span>


[<span data-ttu-id="bfabb-173">規劃部署 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="bfabb-173">Planning to Deploy MBAM 1.0</span></span>](planning-to-deploy-mbam-10.md)

[<span data-ttu-id="bfabb-174">MBAM 1.0 部署必要條件</span><span class="sxs-lookup"><span data-stu-id="bfabb-174">MBAM 1.0 Deployment Prerequisites</span></span>](mbam-10-deployment-prerequisites.md)









