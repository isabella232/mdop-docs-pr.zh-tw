---
title: MED-V 1.0 支援的組態
description: MED-V 1.0 支援的組態
author: dansimp
ms.assetid: 74643de6-549e-4177-a559-6407e156ed3a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3b8ffdfb6e34fe7888ea5ace0ff7264bd978a548
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800136"
---
# <span data-ttu-id="e79ce-103">MED-V 1.0 支援的組態</span><span class="sxs-lookup"><span data-stu-id="e79ce-103">MED-V 1.0 Supported Configurations</span></span>


<span data-ttu-id="e79ce-104">本主題指定在您的環境中安裝並執行 Microsoft 企業桌面虛擬化（MED-V）1.0 所需的需求。</span><span class="sxs-lookup"><span data-stu-id="e79ce-104">This topic specifies the requirements necessary to install and run Microsoft Enterprise Desktop Virtualization (MED-V) 1.0 in your environment.</span></span>

## <span data-ttu-id="e79ce-105">MED-V 1.0 用戶端系統需求</span><span class="sxs-lookup"><span data-stu-id="e79ce-105">MED-V 1.0 Client System Requirements</span></span>


### <span data-ttu-id="e79ce-106">MED-V 用戶端的作業系統需求</span><span class="sxs-lookup"><span data-stu-id="e79ce-106">MED-V Client Operating System Requirements</span></span>

<span data-ttu-id="e79ce-107">下表列出 MED-V 1.0 用戶端安裝支援的作業系統。</span><span class="sxs-lookup"><span data-stu-id="e79ce-107">The following table lists the operating systems that are supported for MED-V 1.0 client installation.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e79ce-108">作業系統</span><span class="sxs-lookup"><span data-stu-id="e79ce-108">Operating System</span></span></th>
<th align="left"><span data-ttu-id="e79ce-109">版本</span><span class="sxs-lookup"><span data-stu-id="e79ce-109">Edition</span></span></th>
<th align="left"><span data-ttu-id="e79ce-110">Service Pack</span><span class="sxs-lookup"><span data-stu-id="e79ce-110">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="e79ce-111">系統架構</span><span class="sxs-lookup"><span data-stu-id="e79ce-111">System Architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e79ce-112">Windows XP</span><span class="sxs-lookup"><span data-stu-id="e79ce-112">Windows XP</span></span></p></td>
<td align="left"><p><span data-ttu-id="e79ce-113">專業版</span><span class="sxs-lookup"><span data-stu-id="e79ce-113">Professional Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="e79ce-114">SP2 或 SP3</span><span class="sxs-lookup"><span data-stu-id="e79ce-114">SP2 or SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="e79ce-115">x86</span><span class="sxs-lookup"><span data-stu-id="e79ce-115">x86</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e79ce-116">Windows Vista</span><span class="sxs-lookup"><span data-stu-id="e79ce-116">Windows Vista</span></span></p></td>
<td align="left"><p><span data-ttu-id="e79ce-117">企業版、企業版或旗艦版</span><span class="sxs-lookup"><span data-stu-id="e79ce-117">Business, Enterprise, or Ultimate Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="e79ce-118">SP1 或 SP2</span><span class="sxs-lookup"><span data-stu-id="e79ce-118">SP1 or SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="e79ce-119">x86</span><span class="sxs-lookup"><span data-stu-id="e79ce-119">x86</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="e79ce-120">注意</span><span class="sxs-lookup"><span data-stu-id="e79ce-120">Note</span></span>**  
<span data-ttu-id="e79ce-121">MED-V 用戶端不會在原生 x64 模式下執行。</span><span class="sxs-lookup"><span data-stu-id="e79ce-121">MED-V client does not run in native x64 mode.</span></span> <span data-ttu-id="e79ce-122">相反地，MED-V 會在64位電腦上的 Windows 64 位（WOW64）模式的 Windows 上執行。</span><span class="sxs-lookup"><span data-stu-id="e79ce-122">Instead, MED-V runs in Windows on Windows 64-bit (WOW64) mode on 64-bit computers.</span></span>



### <a href="" id="med-v-1-0-client-configuration-"></a><span data-ttu-id="e79ce-123">MED-V 1.0 用戶端設定</span><span class="sxs-lookup"><span data-stu-id="e79ce-123">MED-V 1.0 Client Configuration</span></span>

**<span data-ttu-id="e79ce-124">.NET Framework 版本</span><span class="sxs-lookup"><span data-stu-id="e79ce-124">.NET Framework Version</span></span>**

<span data-ttu-id="e79ce-125">MED-V 1.0 用戶端安裝支援下列版本的 Microsoft .NET Framework：</span><span class="sxs-lookup"><span data-stu-id="e79ce-125">The following versions of the Microsoft .NET Framework are supported for MED-V 1.0 client installation:</span></span>

-   <span data-ttu-id="e79ce-126">.NET Framework 2.0 或 .NET Framework 2.0 SP1</span><span class="sxs-lookup"><span data-stu-id="e79ce-126">.NET Framework 2.0 or .NET Framework 2.0 SP1</span></span>

-   <span data-ttu-id="e79ce-127">.NET Framework 3.0 或 .NET Framework 3.0 SP1</span><span class="sxs-lookup"><span data-stu-id="e79ce-127">.NET Framework 3.0 or .NET Framework 3.0 SP1</span></span>

-   <span data-ttu-id="e79ce-128">.NET Framework 3.5 或 .NET Framework 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="e79ce-128">.NET Framework 3.5 or .NET Framework 3.5 SP1</span></span>

**<span data-ttu-id="e79ce-129">虛擬化引擎</span><span class="sxs-lookup"><span data-stu-id="e79ce-129">Virtualization Engine</span></span>**

<span data-ttu-id="e79ce-130">Microsoft Virtual PC 2007 SP1，其中包含 Microsoft 知識庫文章974918中所述的修正程式，支援下列設定中的 MED-V 1.0 用戶端安裝：</span><span class="sxs-lookup"><span data-stu-id="e79ce-130">Microsoft Virtual PC 2007 SP1 with the hotfix that is described in Microsoft Knowledge Base article 974918 is supported for MED-V 1.0 client installation in the following configurations:</span></span>

-   <span data-ttu-id="e79ce-131">靜態虛擬硬碟（VHD）檔案</span><span class="sxs-lookup"><span data-stu-id="e79ce-131">Static Virtual Hard Disk (VHD) file</span></span>

-   <span data-ttu-id="e79ce-132">多個 VHD 檔案位於同一個目錄中</span><span class="sxs-lookup"><span data-stu-id="e79ce-132">Multiple VHD files located within the same directory</span></span>

-   <span data-ttu-id="e79ce-133">動態 VHD 檔案</span><span class="sxs-lookup"><span data-stu-id="e79ce-133">Dynamic VHD file</span></span>

**<span data-ttu-id="e79ce-134">網際網路瀏覽器</span><span class="sxs-lookup"><span data-stu-id="e79ce-134">Internet Browser</span></span>**

<span data-ttu-id="e79ce-135">Windows Internet Explorer 7 和 Windows Internet Explorer 8 支援 MED-V 1.0 用戶端安裝。</span><span class="sxs-lookup"><span data-stu-id="e79ce-135">Windows Internet Explorer 7 and Windows Internet Explorer 8 are supported for MED-V 1.0 client installation.</span></span>

**<span data-ttu-id="e79ce-136">Microsoft Hyper-V Server</span><span class="sxs-lookup"><span data-stu-id="e79ce-136">Microsoft Hyper-V Server</span></span>**

<span data-ttu-id="e79ce-137">Microsoft Hyper-v server 環境不支援 MED-V 用戶端。</span><span class="sxs-lookup"><span data-stu-id="e79ce-137">The MED-V client is not supported in a Microsoft Hyper-V server environment.</span></span>

## <span data-ttu-id="e79ce-138">MED-V 1.0 工作區系統需求</span><span class="sxs-lookup"><span data-stu-id="e79ce-138">MED-V 1.0 Workspace System Requirements</span></span>


### <span data-ttu-id="e79ce-139">MED-V 工作區作業系統需求</span><span class="sxs-lookup"><span data-stu-id="e79ce-139">MED-V Workspace Operating System Requirements</span></span>

<span data-ttu-id="e79ce-140">下表列出 MED-V 1.0 工作區支援的作業系統。</span><span class="sxs-lookup"><span data-stu-id="e79ce-140">The following table lists the operating systems supported for MED-V 1.0 workspaces.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e79ce-141">作業系統</span><span class="sxs-lookup"><span data-stu-id="e79ce-141">Operating System</span></span></th>
<th align="left"><span data-ttu-id="e79ce-142">版本</span><span class="sxs-lookup"><span data-stu-id="e79ce-142">Edition</span></span></th>
<th align="left"><span data-ttu-id="e79ce-143">Service Pack</span><span class="sxs-lookup"><span data-stu-id="e79ce-143">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="e79ce-144">系統架構</span><span class="sxs-lookup"><span data-stu-id="e79ce-144">System Architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e79ce-145">Windows 2000</span><span class="sxs-lookup"><span data-stu-id="e79ce-145">Windows 2000</span></span></p></td>
<td align="left"><p><span data-ttu-id="e79ce-146">專業版</span><span class="sxs-lookup"><span data-stu-id="e79ce-146">Professional</span></span></p></td>
<td align="left"><p><span data-ttu-id="e79ce-147">以後</span><span class="sxs-lookup"><span data-stu-id="e79ce-147">SP4</span></span></p></td>
<td align="left"><p><span data-ttu-id="e79ce-148">X86</span><span class="sxs-lookup"><span data-stu-id="e79ce-148">X86</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e79ce-149">Windows XP</span><span class="sxs-lookup"><span data-stu-id="e79ce-149">Windows XP</span></span></p></td>
<td align="left"><p><span data-ttu-id="e79ce-150">專業版</span><span class="sxs-lookup"><span data-stu-id="e79ce-150">Professional Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="e79ce-151">SP2 或 SP3</span><span class="sxs-lookup"><span data-stu-id="e79ce-151">SP2 or SP3</span></span></p>
<div class="alert">
<strong><span data-ttu-id="e79ce-152">注意</span><span class="sxs-lookup"><span data-stu-id="e79ce-152">Note</span></span></strong><br/><p><span data-ttu-id="e79ce-153">建議使用 SP3，以確保 MED-V 工作區將與未來版本的 MED-V 相容。</span><span class="sxs-lookup"><span data-stu-id="e79ce-153">SP3 is recommended to ensure that the MED-V workspace will be compatible with future versions of MED-V.</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="e79ce-154">x86</span><span class="sxs-lookup"><span data-stu-id="e79ce-154">x86</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="med-v-1-0-workspace-configuration-"></a><span data-ttu-id="e79ce-155">MED-V 1.0 工作區配置</span><span class="sxs-lookup"><span data-stu-id="e79ce-155">MED-V 1.0 Workspace Configuration</span></span>

**<span data-ttu-id="e79ce-156">.NET Framework 版本</span><span class="sxs-lookup"><span data-stu-id="e79ce-156">.NET Framework Version</span></span>**

<span data-ttu-id="e79ce-157">MED-V 需要下列其中一個支援的 Microsoft .NET Framework 版本，才能安裝 MED-V 1.0 工作區：</span><span class="sxs-lookup"><span data-stu-id="e79ce-157">MED-V requires one of the following supported versions of the Microsoft .NET Framework for MED-V 1.0 workspace installation:</span></span>

-   <span data-ttu-id="e79ce-158">.NET Framework 2.0 SP1</span><span class="sxs-lookup"><span data-stu-id="e79ce-158">.NET Framework 2.0 SP1</span></span>

-   <span data-ttu-id="e79ce-159">.NET Framework 3.0 SP1</span><span class="sxs-lookup"><span data-stu-id="e79ce-159">.NET Framework 3.0 SP1</span></span>

-   <span data-ttu-id="e79ce-160">.NET Framework 3.5 或 .NET Framework 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="e79ce-160">.NET Framework 3.5 or .NET Framework 3.5 SP1</span></span>

**<span data-ttu-id="e79ce-161">注意</span><span class="sxs-lookup"><span data-stu-id="e79ce-161">Note</span></span>**  
<span data-ttu-id="e79ce-162">建議使用 .NET Framework 3.5 SP1，以確保 MED-V 工作區將與未來的 MED-V 版本相容。</span><span class="sxs-lookup"><span data-stu-id="e79ce-162">.NET Framework 3.5 SP1 is recommended to ensure that the MED-V workspace will be compatible with future versions of MED-V.</span></span>



**<span data-ttu-id="e79ce-163">網際網路瀏覽器</span><span class="sxs-lookup"><span data-stu-id="e79ce-163">Internet Browser</span></span>**

<span data-ttu-id="e79ce-164">已支援 windows Internet Explorer 6 SP2 及 Windows Internet Explorer 7 （適用于 MED-V 1.0 工作區安裝）。</span><span class="sxs-lookup"><span data-stu-id="e79ce-164">Windows Internet Explorer 6 SP2 and Windows Internet Explorer 7 are supported for the MED-V 1.0 workspace installation.</span></span>

### <a href="" id="med-v-workspace-images-"></a><span data-ttu-id="e79ce-165">MED-V 工作區圖像</span><span class="sxs-lookup"><span data-stu-id="e79ce-165">MED-V Workspace Images</span></span>

<span data-ttu-id="e79ce-166">MED-V 工作區圖像必須使用 Virtual PC 2007 SP1 建立。</span><span class="sxs-lookup"><span data-stu-id="e79ce-166">MED-V workspace images must be created by using Virtual PC 2007 SP1.</span></span>

## <span data-ttu-id="e79ce-167">MED-V 1.0 伺服器系統需求</span><span class="sxs-lookup"><span data-stu-id="e79ce-167">MED-V 1.0 Server System Requirements</span></span>


### <span data-ttu-id="e79ce-168">MED-V 1.0 伺服器作業系統需求</span><span class="sxs-lookup"><span data-stu-id="e79ce-168">MED-V 1.0 Server Operating System Requirements</span></span>

<span data-ttu-id="e79ce-169">下表列出 MED-V 1.0 伺服器安裝支援的作業系統。</span><span class="sxs-lookup"><span data-stu-id="e79ce-169">The following table lists the operating systems supported for MED-V 1.0 server installations.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e79ce-170">作業系統</span><span class="sxs-lookup"><span data-stu-id="e79ce-170">Operating System</span></span></th>
<th align="left"><span data-ttu-id="e79ce-171">版本</span><span class="sxs-lookup"><span data-stu-id="e79ce-171">Edition</span></span></th>
<th align="left"><span data-ttu-id="e79ce-172">Service Pack</span><span class="sxs-lookup"><span data-stu-id="e79ce-172">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="e79ce-173">系統架構</span><span class="sxs-lookup"><span data-stu-id="e79ce-173">System Architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e79ce-174">Windows Server 2008</span><span class="sxs-lookup"><span data-stu-id="e79ce-174">Windows Server 2008</span></span></p></td>
<td align="left"><p><span data-ttu-id="e79ce-175">Standard 或 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e79ce-175">Standard or Enterprise</span></span></p></td>
<td align="left"><p><span data-ttu-id="e79ce-176">無</span><span class="sxs-lookup"><span data-stu-id="e79ce-176">None</span></span></p></td>
<td align="left"><p><span data-ttu-id="e79ce-177">X86 或 x64</span><span class="sxs-lookup"><span data-stu-id="e79ce-177">X86 or x64</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="med-v-1-0-server-configuration-"></a><span data-ttu-id="e79ce-178">MED-V 1.0 伺服器設定</span><span class="sxs-lookup"><span data-stu-id="e79ce-178">MED-V 1.0 Server Configuration</span></span>

**<span data-ttu-id="e79ce-179">.NET Framework 版本</span><span class="sxs-lookup"><span data-stu-id="e79ce-179">.NET Framework Version</span></span>**

<span data-ttu-id="e79ce-180">MED-V 需要下列其中一個支援的 Microsoft .NET Framework 版本，才能安裝 MED-V 1.0 工作區：</span><span class="sxs-lookup"><span data-stu-id="e79ce-180">MED-V requires one of the following supported versions of the Microsoft .NET Framework for MED-V 1.0 workspace installation:</span></span>

-   <span data-ttu-id="e79ce-181">.NET Framework 2.0 或 .NET Framework 2.0 SP1</span><span class="sxs-lookup"><span data-stu-id="e79ce-181">.NET Framework 2.0 or .NET Framework 2.0 SP1</span></span>

-   <span data-ttu-id="e79ce-182">.NET Framework 3.0 或 .NET Framework 3.0 SP1</span><span class="sxs-lookup"><span data-stu-id="e79ce-182">.NET Framework 3.0 or .NET Framework 3.0 SP1</span></span>

-   <span data-ttu-id="e79ce-183">.NET Framework 3.5 或 .NET Framework 3.5 SP1</span><span class="sxs-lookup"><span data-stu-id="e79ce-183">.NET Framework 3.5 or .NET Framework 3.5 SP1</span></span>

**<span data-ttu-id="e79ce-184">Microsoft SQL Server 版本</span><span class="sxs-lookup"><span data-stu-id="e79ce-184">Microsoft SQL Server Version</span></span>**

<span data-ttu-id="e79ce-185">在從 MED-V 1.0 伺服器進行本機或遠端安裝 SQL Server 時，MED-V 1.0 支援下列版本的 Microsoft SQL Server：</span><span class="sxs-lookup"><span data-stu-id="e79ce-185">The following versions of Microsoft SQL Server are supported for MED-V 1.0 when SQL Server is installed locally or remotely from the MED-V 1.0 Server:</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e79ce-186">SQL Server 版本</span><span class="sxs-lookup"><span data-stu-id="e79ce-186">SQL Server Version</span></span></th>
<th align="left"><span data-ttu-id="e79ce-187">版本</span><span class="sxs-lookup"><span data-stu-id="e79ce-187">Edition</span></span></th>
<th align="left"><span data-ttu-id="e79ce-188">Service Pack</span><span class="sxs-lookup"><span data-stu-id="e79ce-188">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="e79ce-189">系統架構</span><span class="sxs-lookup"><span data-stu-id="e79ce-189">System Architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e79ce-190">SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="e79ce-190">SQL Server 2005</span></span></p></td>
<td align="left"><p><span data-ttu-id="e79ce-191">Express、Standard 或 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="e79ce-191">Express, Standard, or Enterprise Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="e79ce-192">SP2</span><span class="sxs-lookup"><span data-stu-id="e79ce-192">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="e79ce-193">X86 或 x64</span><span class="sxs-lookup"><span data-stu-id="e79ce-193">X86 or x64</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e79ce-194">SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="e79ce-194">SQL Server 2008</span></span></p></td>
<td align="left"><p><span data-ttu-id="e79ce-195">Express、Standard 或 Enterprise</span><span class="sxs-lookup"><span data-stu-id="e79ce-195">Express, Standard, or Enterprise</span></span></p></td>
<td align="left"><p><span data-ttu-id="e79ce-196">無</span><span class="sxs-lookup"><span data-stu-id="e79ce-196">None</span></span></p></td>
<td align="left"><p><span data-ttu-id="e79ce-197">X86 或 x64</span><span class="sxs-lookup"><span data-stu-id="e79ce-197">X86 or x64</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="e79ce-198">Microsoft Hyper-V Server</span><span class="sxs-lookup"><span data-stu-id="e79ce-198">Microsoft Hyper-V Server</span></span>**

<span data-ttu-id="e79ce-199">在 Microsoft Hyper-v server 環境中支援 MED-V 伺服器。</span><span class="sxs-lookup"><span data-stu-id="e79ce-199">The MED-V server is supported in a Microsoft Hyper-V server environment.</span></span>

## <span data-ttu-id="e79ce-200">MED-V 1.0 全球化資訊</span><span class="sxs-lookup"><span data-stu-id="e79ce-200">MED-V 1.0 Globalization Information</span></span>


<span data-ttu-id="e79ce-201">雖然不是以英文以外的語言發行 MED-V，但是對於 MED-V 1.0 用戶端、工作區和伺服器安裝，支援下列 Windows 作業系統語言版本：</span><span class="sxs-lookup"><span data-stu-id="e79ce-201">Although MED-V is not released in languages other than English, the following Windows operating system language versions are supported for the MED-V 1.0 client, workspace, and server installations:</span></span>

-   <span data-ttu-id="e79ce-202">英文</span><span class="sxs-lookup"><span data-stu-id="e79ce-202">English</span></span>

-   <span data-ttu-id="e79ce-203">法文</span><span class="sxs-lookup"><span data-stu-id="e79ce-203">French</span></span>

-   <span data-ttu-id="e79ce-204">德文</span><span class="sxs-lookup"><span data-stu-id="e79ce-204">German</span></span>

-   <span data-ttu-id="e79ce-205">義大利文</span><span class="sxs-lookup"><span data-stu-id="e79ce-205">Italian</span></span>

-   <span data-ttu-id="e79ce-206">西班牙文</span><span class="sxs-lookup"><span data-stu-id="e79ce-206">Spanish</span></span>

-   <span data-ttu-id="e79ce-207">葡萄牙文 (巴西)</span><span class="sxs-lookup"><span data-stu-id="e79ce-207">Portuguese (Brazil)</span></span>









