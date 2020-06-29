---
title: MED-V 2.0 支援的組態
description: MED-V 2.0 支援的組態
author: dansimp
ms.assetid: 88f1d232-aa01-45ab-8da7-d086269250b5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0fed090ec04cf67a32b13533f4003c01ae167493
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811024"
---
# <span data-ttu-id="7f6e1-103">MED-V 2.0 支援的組態</span><span class="sxs-lookup"><span data-stu-id="7f6e1-103">MED-V 2.0 Supported Configurations</span></span>


<span data-ttu-id="7f6e1-104">您的環境可能已符合此處提供的設定需求，因此您可以安裝並執行 Microsoft 企業版桌面虛擬化（MED-V）2.0。</span><span class="sxs-lookup"><span data-stu-id="7f6e1-104">Your environment may already meet the configuration requirements provided here so that you can install and run Microsoft Enterprise Desktop Virtualization (MED-V) 2.0.</span></span> <span data-ttu-id="7f6e1-105">我們已納入需求，包括主機作業系統、磁碟空間和 MED-V 工作區需求。</span><span class="sxs-lookup"><span data-stu-id="7f6e1-105">We have included requirements including host operating system, disk space, and MED-V workspace requirements.</span></span>

## <span data-ttu-id="7f6e1-106">MED-V 2.0 主機電腦需求</span><span class="sxs-lookup"><span data-stu-id="7f6e1-106">MED-V2.0 Host Computer Requirements</span></span>


### <span data-ttu-id="7f6e1-107">MED-V 2.0 主機作業系統需求</span><span class="sxs-lookup"><span data-stu-id="7f6e1-107">MED-V 2.0 Host Operating System Requirements</span></span>

<span data-ttu-id="7f6e1-108">下表列出了主機電腦上的 MED-V 2.0 安裝支援的作業系統。</span><span class="sxs-lookup"><span data-stu-id="7f6e1-108">The following table lists the operating systems that are supported for MED-V 2.0 installation on the host computer.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="7f6e1-109">作業系統</span><span class="sxs-lookup"><span data-stu-id="7f6e1-109">Operating System</span></span></th>
<th align="left"><span data-ttu-id="7f6e1-110">版本</span><span class="sxs-lookup"><span data-stu-id="7f6e1-110">Edition</span></span></th>
<th align="left"><span data-ttu-id="7f6e1-111">Service Pack</span><span class="sxs-lookup"><span data-stu-id="7f6e1-111">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="7f6e1-112">系統架構</span><span class="sxs-lookup"><span data-stu-id="7f6e1-112">System Architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7f6e1-113">Windows7</span><span class="sxs-lookup"><span data-stu-id="7f6e1-113">Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="7f6e1-114">專業版、企業版或旗艦版</span><span class="sxs-lookup"><span data-stu-id="7f6e1-114">Professional, Enterprise, or Ultimate</span></span></p></td>
<td align="left"><p><span data-ttu-id="7f6e1-115">None 或 SP1</span><span class="sxs-lookup"><span data-stu-id="7f6e1-115">None or SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="7f6e1-116">x86 或 x64</span><span class="sxs-lookup"><span data-stu-id="7f6e1-116">x86 or x64</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="7f6e1-117">下表列出 MED-V 2.0 中支援的每個作業系統所需的最低 RAM。</span><span class="sxs-lookup"><span data-stu-id="7f6e1-117">The following table lists the minimal RAM required for each operating system supported in MED-V 2.0.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="7f6e1-118">作業系統</span><span class="sxs-lookup"><span data-stu-id="7f6e1-118">Operating System</span></span></th>
<th align="left"><span data-ttu-id="7f6e1-119">最低所需 RAM</span><span class="sxs-lookup"><span data-stu-id="7f6e1-119">Minimum Required RAM</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7f6e1-120">Windows7 x86</span><span class="sxs-lookup"><span data-stu-id="7f6e1-120">Windows7 x86</span></span></p></td>
<td align="left"><p><span data-ttu-id="7f6e1-121">超過</span><span class="sxs-lookup"><span data-stu-id="7f6e1-121">2GB</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="7f6e1-122">Windows7 x64</span><span class="sxs-lookup"><span data-stu-id="7f6e1-122">Windows7 x64</span></span></p></td>
<td align="left"><p><span data-ttu-id="7f6e1-123">超過</span><span class="sxs-lookup"><span data-stu-id="7f6e1-123">2GB</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="7f6e1-124">建議的磁碟空間最小值</span><span class="sxs-lookup"><span data-stu-id="7f6e1-124">Minimum Recommended Disk Space</span></span>

<span data-ttu-id="7f6e1-125">我們建議您至少10GB 可用儲存空間。</span><span class="sxs-lookup"><span data-stu-id="7f6e1-125">We recommend a minimum of 10GB of available storage.</span></span> <span data-ttu-id="7f6e1-126">不過，所需的磁碟空間會有很大的差異，視在 MED-V 工作區中發佈的應用程式數目而定。</span><span class="sxs-lookup"><span data-stu-id="7f6e1-126">However, the disk space that is required varies greatly and depends on the number of applications published in the MED-V workspace.</span></span>

### <a href="" id="med-v-2-0-host-configuration-"></a><span data-ttu-id="7f6e1-127">MED-V 2.0 主機設定</span><span class="sxs-lookup"><span data-stu-id="7f6e1-127">MED-V2.0 Host Configuration</span></span>

**<span data-ttu-id="7f6e1-128">.NET Framework 版本</span><span class="sxs-lookup"><span data-stu-id="7f6e1-128">.NET Framework Version</span></span>**

<span data-ttu-id="7f6e1-129">MED-V 2.0 需要 .NET Framework 3.5 SP1 版的 Microsoft .NET Framework。</span><span class="sxs-lookup"><span data-stu-id="7f6e1-129">The .NET Framework3.5 SP1 version of the Microsoft .NET Framework is required for MED-V 2.0.</span></span> <span data-ttu-id="7f6e1-130">不過，如果已安裝 .NET Framework 3.5，就可以安裝 .NET Framework 4 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="7f6e1-130">However, you can install the .NET Framework 4 or later version if the .NET Framework 3.5 is already installed.</span></span>

**<span data-ttu-id="7f6e1-131">虛擬化引擎</span><span class="sxs-lookup"><span data-stu-id="7f6e1-131">Virtualization Engine</span></span>**

<span data-ttu-id="7f6e1-132">Windows 虛擬 PCwith Microsoft 知識庫文章977206中所述的修復程式支援 MED-V 2.0。</span><span class="sxs-lookup"><span data-stu-id="7f6e1-132">Windows Virtual PCwith the hotfix that is described in Microsoft Knowledge Base article 977206 is supported for MED-V 2.0.</span></span>

**<span data-ttu-id="7f6e1-133">網際網路瀏覽器</span><span class="sxs-lookup"><span data-stu-id="7f6e1-133">Internet Browser</span></span>**

<span data-ttu-id="7f6e1-134">MED-V 2.0 支援 windows Internet Explorer8 和 Windows Internet Explorer 9。</span><span class="sxs-lookup"><span data-stu-id="7f6e1-134">Windows Internet Explorer8 and Windows Internet Explorer 9 are supported for MED-V 2.0.</span></span>

**<span data-ttu-id="7f6e1-135">Microsoft Server 環境</span><span class="sxs-lookup"><span data-stu-id="7f6e1-135">Microsoft Server Environments</span></span>**

<span data-ttu-id="7f6e1-136">在任何伺服器環境中，都不支援 MED-V 主機代理程式和 MED-V 工作區包裝程式。</span><span class="sxs-lookup"><span data-stu-id="7f6e1-136">The MED-V Host Agent and the MED-V Workspace Packager are not supported in any server environment.</span></span>

## <span data-ttu-id="7f6e1-137">MED-V 2.0 工作區需求</span><span class="sxs-lookup"><span data-stu-id="7f6e1-137">MED-V2.0 Workspace Requirements</span></span>


### <span data-ttu-id="7f6e1-138">MED-V 2.0 工作區作業系統需求</span><span class="sxs-lookup"><span data-stu-id="7f6e1-138">MED-V 2.0 Workspace Operating System Requirements</span></span>

<span data-ttu-id="7f6e1-139">下表列出 MED-V 2.0 工作區支援的作業系統。</span><span class="sxs-lookup"><span data-stu-id="7f6e1-139">The following table lists the operating systems supported for MED-V 2.0 workspaces.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="7f6e1-140">作業系統</span><span class="sxs-lookup"><span data-stu-id="7f6e1-140">Operating System</span></span></th>
<th align="left"><span data-ttu-id="7f6e1-141">版本</span><span class="sxs-lookup"><span data-stu-id="7f6e1-141">Edition</span></span></th>
<th align="left"><span data-ttu-id="7f6e1-142">Service Pack</span><span class="sxs-lookup"><span data-stu-id="7f6e1-142">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="7f6e1-143">系統架構</span><span class="sxs-lookup"><span data-stu-id="7f6e1-143">System Architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7f6e1-144">WindowsXP</span><span class="sxs-lookup"><span data-stu-id="7f6e1-144">WindowsXP</span></span></p></td>
<td align="left"><p><span data-ttu-id="7f6e1-145">專業版</span><span class="sxs-lookup"><span data-stu-id="7f6e1-145">Professional Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="7f6e1-146">SP3</span><span class="sxs-lookup"><span data-stu-id="7f6e1-146">SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="7f6e1-147">x86</span><span class="sxs-lookup"><span data-stu-id="7f6e1-147">x86</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="med-v-2-0-workspace-configuration-"></a><span data-ttu-id="7f6e1-148">MED-V 2.0 工作區配置</span><span class="sxs-lookup"><span data-stu-id="7f6e1-148">MED-V2.0 Workspace Configuration</span></span>

**<span data-ttu-id="7f6e1-149">.NET Framework 版本</span><span class="sxs-lookup"><span data-stu-id="7f6e1-149">.NET Framework Version</span></span>**

<span data-ttu-id="7f6e1-150">MED-V 2.0 工作區安裝只支援 .NET Framework 3.5 SP1 版的 Microsoft .NET Framework。</span><span class="sxs-lookup"><span data-stu-id="7f6e1-150">Only the .NET Framework3.5 SP1 version of the Microsoft .NET Framework is supported for MED-V 2.0 workspace installation.</span></span>

**<span data-ttu-id="7f6e1-151">網際網路瀏覽器</span><span class="sxs-lookup"><span data-stu-id="7f6e1-151">Internet Browser</span></span>**

<span data-ttu-id="7f6e1-152">MED-V 2.0 工作區安裝支援 windows Internet Explorer6、Windows Internet Explorer7、Windows Internet Explorer8 及 Windows Internet Explorer9。</span><span class="sxs-lookup"><span data-stu-id="7f6e1-152">Windows Internet Explorer6, Windows Internet Explorer7, Windows Internet Explorer8, and Windows Internet Explorer9 are supported for the MED-V 2.0 workspace installation.</span></span>

### <span data-ttu-id="7f6e1-153">MED-V 2.0 工作區建立</span><span class="sxs-lookup"><span data-stu-id="7f6e1-153">MED-V 2.0 Workspace Creation</span></span>

<span data-ttu-id="7f6e1-154">用來建立 MED-V 2.0 工作區套件的虛擬硬碟必須使用 Windows 虛擬電腦建立。</span><span class="sxs-lookup"><span data-stu-id="7f6e1-154">The virtual hard disk used to build a MED-V 2.0 workspace package must be created by using Windows Virtual PC.</span></span>

## <span data-ttu-id="7f6e1-155">MED-V 2.0 全球化資訊</span><span class="sxs-lookup"><span data-stu-id="7f6e1-155">MED-V 2.0 Globalization Information</span></span>


### <span data-ttu-id="7f6e1-156">MED-V 2.0 主機代理程式全球化資訊</span><span class="sxs-lookup"><span data-stu-id="7f6e1-156">MED-V 2.0 Host Agent Globalization Information</span></span>

<span data-ttu-id="7f6e1-157">MED-V 2.0 主機代理支援下列 Windows 作業系統語言版本：</span><span class="sxs-lookup"><span data-stu-id="7f6e1-157">The following Windows operating system language versions are supported for the MED-V 2.0 Host Agent:</span></span>

-   <span data-ttu-id="7f6e1-158">法文</span><span class="sxs-lookup"><span data-stu-id="7f6e1-158">French</span></span>

-   <span data-ttu-id="7f6e1-159">義大利文</span><span class="sxs-lookup"><span data-stu-id="7f6e1-159">Italian</span></span>

-   <span data-ttu-id="7f6e1-160">德文</span><span class="sxs-lookup"><span data-stu-id="7f6e1-160">German</span></span>

-   <span data-ttu-id="7f6e1-161">西班牙文</span><span class="sxs-lookup"><span data-stu-id="7f6e1-161">Spanish</span></span>

-   <span data-ttu-id="7f6e1-162">韓文</span><span class="sxs-lookup"><span data-stu-id="7f6e1-162">Korean</span></span>

-   <span data-ttu-id="7f6e1-163">日文</span><span class="sxs-lookup"><span data-stu-id="7f6e1-163">Japanese</span></span>

-   <span data-ttu-id="7f6e1-164">巴西葡萄牙文</span><span class="sxs-lookup"><span data-stu-id="7f6e1-164">Brazilian Portuguese</span></span>

-   <span data-ttu-id="7f6e1-165">俄文</span><span class="sxs-lookup"><span data-stu-id="7f6e1-165">Russian</span></span>

-   <span data-ttu-id="7f6e1-166">繁體中文</span><span class="sxs-lookup"><span data-stu-id="7f6e1-166">Chinese Traditional</span></span>

-   <span data-ttu-id="7f6e1-167">簡體中文</span><span class="sxs-lookup"><span data-stu-id="7f6e1-167">Chinese Simplified</span></span>

-   <span data-ttu-id="7f6e1-168">荷蘭文</span><span class="sxs-lookup"><span data-stu-id="7f6e1-168">Dutch</span></span>

-   <span data-ttu-id="7f6e1-169">瑞典文</span><span class="sxs-lookup"><span data-stu-id="7f6e1-169">Swedish</span></span>

-   <span data-ttu-id="7f6e1-170">丹麥文</span><span class="sxs-lookup"><span data-stu-id="7f6e1-170">Danish</span></span>

-   <span data-ttu-id="7f6e1-171">芬蘭文</span><span class="sxs-lookup"><span data-stu-id="7f6e1-171">Finnish</span></span>

-   <span data-ttu-id="7f6e1-172">葡萄牙文</span><span class="sxs-lookup"><span data-stu-id="7f6e1-172">Portuguese</span></span>

-   <span data-ttu-id="7f6e1-173">挪威文</span><span class="sxs-lookup"><span data-stu-id="7f6e1-173">Norwegian</span></span>

-   <span data-ttu-id="7f6e1-174">波蘭文</span><span class="sxs-lookup"><span data-stu-id="7f6e1-174">Polish</span></span>

-   <span data-ttu-id="7f6e1-175">土耳其文</span><span class="sxs-lookup"><span data-stu-id="7f6e1-175">Turkish</span></span>

-   <span data-ttu-id="7f6e1-176">匈牙利文</span><span class="sxs-lookup"><span data-stu-id="7f6e1-176">Hungarian</span></span>

-   <span data-ttu-id="7f6e1-177">捷克文</span><span class="sxs-lookup"><span data-stu-id="7f6e1-177">Czech</span></span>

-   <span data-ttu-id="7f6e1-178">希臘文</span><span class="sxs-lookup"><span data-stu-id="7f6e1-178">Greek</span></span>

-   <span data-ttu-id="7f6e1-179">斯洛伐克文</span><span class="sxs-lookup"><span data-stu-id="7f6e1-179">Slovak</span></span>

-   <span data-ttu-id="7f6e1-180">斯洛維尼亞文</span><span class="sxs-lookup"><span data-stu-id="7f6e1-180">Slovenian</span></span>

### <span data-ttu-id="7f6e1-181">MED-V 2.0 工作區包裝程式全球化資訊</span><span class="sxs-lookup"><span data-stu-id="7f6e1-181">MED-V 2.0 Workspace Packager Globalization Information</span></span>

<span data-ttu-id="7f6e1-182">MED-V 2.0 工作區包裝程式支援下列 Windows 作業系統語言版本：</span><span class="sxs-lookup"><span data-stu-id="7f6e1-182">The following Windows operating system language versions are supported for the MED-V 2.0 Workspace Packager:</span></span>

-   <span data-ttu-id="7f6e1-183">法文</span><span class="sxs-lookup"><span data-stu-id="7f6e1-183">French</span></span>

-   <span data-ttu-id="7f6e1-184">義大利文</span><span class="sxs-lookup"><span data-stu-id="7f6e1-184">Italian</span></span>

-   <span data-ttu-id="7f6e1-185">德文</span><span class="sxs-lookup"><span data-stu-id="7f6e1-185">German</span></span>

-   <span data-ttu-id="7f6e1-186">西班牙文</span><span class="sxs-lookup"><span data-stu-id="7f6e1-186">Spanish</span></span>

-   <span data-ttu-id="7f6e1-187">韓文</span><span class="sxs-lookup"><span data-stu-id="7f6e1-187">Korean</span></span>

-   <span data-ttu-id="7f6e1-188">日文</span><span class="sxs-lookup"><span data-stu-id="7f6e1-188">Japanese</span></span>

-   <span data-ttu-id="7f6e1-189">巴西葡萄牙文</span><span class="sxs-lookup"><span data-stu-id="7f6e1-189">Brazilian Portuguese</span></span>

-   <span data-ttu-id="7f6e1-190">俄文</span><span class="sxs-lookup"><span data-stu-id="7f6e1-190">Russian</span></span>

-   <span data-ttu-id="7f6e1-191">繁體中文</span><span class="sxs-lookup"><span data-stu-id="7f6e1-191">Chinese Traditional</span></span>

-   <span data-ttu-id="7f6e1-192">簡體中文</span><span class="sxs-lookup"><span data-stu-id="7f6e1-192">Chinese Simplified</span></span>

## <span data-ttu-id="7f6e1-193">相關主題</span><span class="sxs-lookup"><span data-stu-id="7f6e1-193">Related topics</span></span>


[<span data-ttu-id="7f6e1-194">MED-V 部署</span><span class="sxs-lookup"><span data-stu-id="7f6e1-194">Deployment of MED-V</span></span>](deployment-of-med-v.md)

 

 





