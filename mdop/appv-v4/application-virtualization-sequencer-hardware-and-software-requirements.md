---
title: Application Virtualization Sequencer 硬體和軟體需求
description: Application Virtualization Sequencer 硬體和軟體需求
author: dansimp
ms.assetid: c88a1b5b-23e1-4460-afa9-a5f37e32eb05
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d68afe4d4a3f6f301d38f2e86139d94319583467
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802290"
---
# <span data-ttu-id="2c66f-103">Application Virtualization Sequencer 硬體和軟體需求</span><span class="sxs-lookup"><span data-stu-id="2c66f-103">Application Virtualization Sequencer Hardware and Software Requirements</span></span>


<span data-ttu-id="2c66f-104">本主題描述執行 Microsoft Application Virtualization （App-v） Sequencer 的電腦所建議的最低硬體和軟體需求。</span><span class="sxs-lookup"><span data-stu-id="2c66f-104">This topic describes the minimum recommended hardware and software requirements for the computer running the Microsoft Application Virtualization (App-V) Sequencer.</span></span>

<span data-ttu-id="2c66f-105">**重要** 您必須使用具有系統管理員許可權的帳戶來執行 App-v 排序器（**SFTSequencer.exe**），因為 sequencer 會對本機系統進行的變更。</span><span class="sxs-lookup"><span data-stu-id="2c66f-105">**Important** You must run the App-V sequencer (**SFTSequencer.exe**) using an account that has administrator privileges because of the changes the sequencer makes to the local system.</span></span> <span data-ttu-id="2c66f-106">這些變更可以包括將檔案寫入**C:\\program files files**目錄、進行登錄、啟動及停止服務、更新檔案的安全性描述項，以及變更許可權。</span><span class="sxs-lookup"><span data-stu-id="2c66f-106">These changes can include writing files to the **C:\\Program Files** directory, making registry changes, starting and stopping services, updating security descriptors for files, and changing permissions.</span></span>

 

<span data-ttu-id="2c66f-107">您必須先將乾淨的作業系統映射還原至順序電腦，然後才能安裝排序器並排序每個應用程式。</span><span class="sxs-lookup"><span data-stu-id="2c66f-107">Before you install the Sequencer and after you sequence each application, you must restore a clean operating system image to the sequencing computer.</span></span> <span data-ttu-id="2c66f-108">您可以使用下列其中一種方法來還原執行排序器的電腦：</span><span class="sxs-lookup"><span data-stu-id="2c66f-108">You can use one of the following methods to restore the computer running the Sequencer:</span></span>

-   <span data-ttu-id="2c66f-109">重新格式化硬碟並重新安裝作業系統。</span><span class="sxs-lookup"><span data-stu-id="2c66f-109">Reformat the hard drive and reinstall the operating system.</span></span>

-   <span data-ttu-id="2c66f-110">使用另一個磁片影像軟體，在執行 Sequencer 影像的電腦上還原硬碟。</span><span class="sxs-lookup"><span data-stu-id="2c66f-110">Restore the hard drive on the computer running the Sequencer image by using another disk-imaging software.</span></span>

-   <span data-ttu-id="2c66f-111">還原虛擬作業系統映射，例如 Microsoft 虛擬電腦影像。</span><span class="sxs-lookup"><span data-stu-id="2c66f-111">Revert a virtual operating system image such as a Microsoft Virtual PC image.</span></span> <span data-ttu-id="2c66f-112">使用虛擬機器可讓清理的順序環境輕鬆地在最低的管理中重複使用。</span><span class="sxs-lookup"><span data-stu-id="2c66f-112">Using a virtual machine allows for clean sequencing environments to be easily reused with minimal administration.</span></span>

<span data-ttu-id="2c66f-113">下列清單概括了執行 App-v 排序器的建議硬體需求。</span><span class="sxs-lookup"><span data-stu-id="2c66f-113">The following list outlines the recommended hardware requirements for running the App-V Sequencer.</span></span>

<span data-ttu-id="2c66f-114">首先列出的是 Microsoft Application Virtualization （App-v） 4.6 SP2 的需求，後面接著是應用程式 V 4.6 SP2 之前的版本需求。</span><span class="sxs-lookup"><span data-stu-id="2c66f-114">The requirements are listed first for Microsoft Application Virtualization (App-V)4.6 SP2, followed by the requirements for versions that preceded App-V4.6SP2.</span></span>

### <a href="" id="hardware-requirements-"></a><span data-ttu-id="2c66f-115">硬體需求</span><span class="sxs-lookup"><span data-stu-id="2c66f-115">Hardware Requirements</span></span>

-   <span data-ttu-id="2c66f-116">處理器-英特爾奔騰 III，1 GHz （32位或64位）。</span><span class="sxs-lookup"><span data-stu-id="2c66f-116">Processor—Intel Pentium III, 1 GHz (32-bit or 64-bit).</span></span> <span data-ttu-id="2c66f-117">排序流程是單一線程處理，不會利用雙處理器。</span><span class="sxs-lookup"><span data-stu-id="2c66f-117">The sequencing process is a single-threaded process and does not take advantage of dual processors.</span></span>

-   <span data-ttu-id="2c66f-118">記憶體-1GB 或更新版本（建議使用2GB）。</span><span class="sxs-lookup"><span data-stu-id="2c66f-118">Memory—1GB or above, 2GB recommended.</span></span>

-   <span data-ttu-id="2c66f-119">硬碟-40 gb 硬碟空間，至少可提供 15 GB 的可用硬碟空間。</span><span class="sxs-lookup"><span data-stu-id="2c66f-119">Hard disk—40 gigabyte (GB) hard disk space with a minimum of 15 GB available hard disk space.</span></span> <span data-ttu-id="2c66f-120">我們建議您至少有三倍您要排序之應用程式的硬碟空間需要。</span><span class="sxs-lookup"><span data-stu-id="2c66f-120">We recommend that you have at least three times the hard disk space that the application you are sequencing requires.</span></span>

    <span data-ttu-id="2c66f-121">**記事** 排序需要大量的磁片使用量。</span><span class="sxs-lookup"><span data-stu-id="2c66f-121">**Note** Sequencing requires heavy disk usage.</span></span> <span data-ttu-id="2c66f-122">較快的磁片速度可能會減少排序時間。</span><span class="sxs-lookup"><span data-stu-id="2c66f-122">A fast disk speed can decrease the sequencing time.</span></span>

     

### <span data-ttu-id="2c66f-123">App-v 4.6 SP2 的軟體需求</span><span class="sxs-lookup"><span data-stu-id="2c66f-123">Software Requirements for App-V 4.6 SP2</span></span>

<span data-ttu-id="2c66f-124">下列清單列出執行 App-v 4.6 SP2 排序器所支援的作業系統。</span><span class="sxs-lookup"><span data-stu-id="2c66f-124">The following list outlines the supported operating systems for running the App-V 4.6 SP2 Sequencer.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2c66f-125">作業系統</span><span class="sxs-lookup"><span data-stu-id="2c66f-125">Operating System</span></span></th>
<th align="left"><span data-ttu-id="2c66f-126">版本</span><span class="sxs-lookup"><span data-stu-id="2c66f-126">Edition</span></span></th>
<th align="left"><span data-ttu-id="2c66f-127">Service Pack</span><span class="sxs-lookup"><span data-stu-id="2c66f-127">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="2c66f-128">系統架構</span><span class="sxs-lookup"><span data-stu-id="2c66f-128">System Architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2c66f-129">WindowsXP</span><span class="sxs-lookup"><span data-stu-id="2c66f-129">WindowsXP</span></span></p></td>
<td align="left"><p><span data-ttu-id="2c66f-130">專業版</span><span class="sxs-lookup"><span data-stu-id="2c66f-130">Professional</span></span></p></td>
<td align="left"><p><span data-ttu-id="2c66f-131">SP3</span><span class="sxs-lookup"><span data-stu-id="2c66f-131">SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="2c66f-132">x86</span><span class="sxs-lookup"><span data-stu-id="2c66f-132">x86</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2c66f-133">Windows Vista</span><span class="sxs-lookup"><span data-stu-id="2c66f-133">Windows Vista</span></span></p></td>
<td align="left"><p><span data-ttu-id="2c66f-134">企業、企業或旗艦版</span><span class="sxs-lookup"><span data-stu-id="2c66f-134">Business, Enterprise, or Ultimate</span></span></p></td>
<td align="left"><p><span data-ttu-id="2c66f-135">SP2</span><span class="sxs-lookup"><span data-stu-id="2c66f-135">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="2c66f-136">x86</span><span class="sxs-lookup"><span data-stu-id="2c66f-136">x86</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2c66f-137">Windows7</span><span class="sxs-lookup"><span data-stu-id="2c66f-137">Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="2c66f-138">專業版、企業版或旗艦版</span><span class="sxs-lookup"><span data-stu-id="2c66f-138">Professional, Enterprise, or Ultimate</span></span></p></td>
<td align="left"><p><span data-ttu-id="2c66f-139">沒有 service pack 或 SP1</span><span class="sxs-lookup"><span data-stu-id="2c66f-139">No service pack or SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="2c66f-140">x86 和 x64</span><span class="sxs-lookup"><span data-stu-id="2c66f-140">x86 and x64</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2c66f-141">Windows8</span><span class="sxs-lookup"><span data-stu-id="2c66f-141">Windows 8</span></span></p></td>
<td align="left"><p><span data-ttu-id="2c66f-142">Pro 或 Enterprise Edition</span><span class="sxs-lookup"><span data-stu-id="2c66f-142">Pro or Enterprise Edition</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="2c66f-143">x86 和 x64</span><span class="sxs-lookup"><span data-stu-id="2c66f-143">x86 and x64</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="2c66f-144">**記事** 應用程式虛擬化（App-v） 4.6 SP2 排序器支援這些作業系統的32位與64位版本。</span><span class="sxs-lookup"><span data-stu-id="2c66f-144">**Note** The Application Virtualization (App-V) 4.6 SP2 Sequencer supports 32-bit and 64-bit versions of these operating systems.</span></span>

 

<span data-ttu-id="2c66f-145">您應該將執行排序器的電腦設定為在目的電腦上安裝的相同應用程式。</span><span class="sxs-lookup"><span data-stu-id="2c66f-145">You should configure computers running the Sequencer with the same applications that are installed on targeted computers.</span></span>

### <span data-ttu-id="2c66f-146">應用程式 V 4.6 SP2 之前版本的軟體需求</span><span class="sxs-lookup"><span data-stu-id="2c66f-146">Software Requirements for Versions that Precede App-V 4.6 SP2</span></span>

<span data-ttu-id="2c66f-147">下列清單概述針對應用程式 V 4.6 SP2 之前的版本執行 Sequencer 所支援的作業系統。</span><span class="sxs-lookup"><span data-stu-id="2c66f-147">The following list outlines the supported operating systems for running the Sequencer for versions that precede App-V 4.6 SP2.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2c66f-148">作業系統</span><span class="sxs-lookup"><span data-stu-id="2c66f-148">Operating System</span></span></th>
<th align="left"><span data-ttu-id="2c66f-149">版本</span><span class="sxs-lookup"><span data-stu-id="2c66f-149">Edition</span></span></th>
<th align="left"><span data-ttu-id="2c66f-150">Service Pack</span><span class="sxs-lookup"><span data-stu-id="2c66f-150">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="2c66f-151">系統架構</span><span class="sxs-lookup"><span data-stu-id="2c66f-151">System Architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2c66f-152">WindowsXP</span><span class="sxs-lookup"><span data-stu-id="2c66f-152">WindowsXP</span></span></p></td>
<td align="left"><p><span data-ttu-id="2c66f-153">專業版</span><span class="sxs-lookup"><span data-stu-id="2c66f-153">Professional</span></span></p></td>
<td align="left"><p><span data-ttu-id="2c66f-154">SP2 或 SP3</span><span class="sxs-lookup"><span data-stu-id="2c66f-154">SP2 or SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="2c66f-155">x86</span><span class="sxs-lookup"><span data-stu-id="2c66f-155">x86</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2c66f-156">Windows Vista</span><span class="sxs-lookup"><span data-stu-id="2c66f-156">Windows Vista</span></span></p></td>
<td align="left"><p><span data-ttu-id="2c66f-157">企業、企業或旗艦版</span><span class="sxs-lookup"><span data-stu-id="2c66f-157">Business, Enterprise, or Ultimate</span></span></p></td>
<td align="left"><p><span data-ttu-id="2c66f-158">沒有 service pack、SP1 或 SP2</span><span class="sxs-lookup"><span data-stu-id="2c66f-158">No service pack, SP1, or SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="2c66f-159">x86</span><span class="sxs-lookup"><span data-stu-id="2c66f-159">x86</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2c66f-160">Windows7 ¹</span><span class="sxs-lookup"><span data-stu-id="2c66f-160">Windows7¹</span></span></p></td>
<td align="left"><p><span data-ttu-id="2c66f-161">專業版、企業版或旗艦版</span><span class="sxs-lookup"><span data-stu-id="2c66f-161">Professional, Enterprise, or Ultimate</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="2c66f-162">x86</span><span class="sxs-lookup"><span data-stu-id="2c66f-162">x86</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="2c66f-163">¹支援在 SP1 或 SP2 中使用 app-v 4.5，且僅限 App-v 4。6</span><span class="sxs-lookup"><span data-stu-id="2c66f-163">¹Supported for App-V 4.5 with SP1 or SP2, and App-V 4.6 only</span></span>

<span data-ttu-id="2c66f-164">**記事** 應用程式虛擬化（App-v） 4.6 Sequencer 支援這些作業系統的32位與64位版本。</span><span class="sxs-lookup"><span data-stu-id="2c66f-164">**Note** The Application Virtualization (App-V) 4.6 Sequencer supports 32-bit and 64-bit versions of these operating systems.</span></span>

 

<span data-ttu-id="2c66f-165">您應該將執行排序器的電腦設定為在目的電腦上安裝的相同應用程式。</span><span class="sxs-lookup"><span data-stu-id="2c66f-165">You should configure computers running the Sequencer with the same applications that are installed on targeted computers.</span></span>

### <span data-ttu-id="2c66f-166">App-v 4.6 SP2 的遠端桌面服務的軟體需求</span><span class="sxs-lookup"><span data-stu-id="2c66f-166">Software Requirements for Remote Desktop Services for App-V 4.6 SP2</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2c66f-167">作業系統</span><span class="sxs-lookup"><span data-stu-id="2c66f-167">Operating System</span></span></th>
<th align="left"><span data-ttu-id="2c66f-168">版本</span><span class="sxs-lookup"><span data-stu-id="2c66f-168">Edition</span></span></th>
<th align="left"><span data-ttu-id="2c66f-169">Service Pack</span><span class="sxs-lookup"><span data-stu-id="2c66f-169">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="2c66f-170">系統架構</span><span class="sxs-lookup"><span data-stu-id="2c66f-170">System Architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2c66f-171">Windows Server2003 R2</span><span class="sxs-lookup"><span data-stu-id="2c66f-171">Windows Server2003 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="2c66f-172">標準版、企業版或資料中心版本</span><span class="sxs-lookup"><span data-stu-id="2c66f-172">Standard Edition, Enterprise Edition, or Datacenter Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="2c66f-173">SP2</span><span class="sxs-lookup"><span data-stu-id="2c66f-173">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="2c66f-174">x86</span><span class="sxs-lookup"><span data-stu-id="2c66f-174">x86</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2c66f-175">Windows Server2008</span><span class="sxs-lookup"><span data-stu-id="2c66f-175">Windows Server2008</span></span></p></td>
<td align="left"><p><span data-ttu-id="2c66f-176">標準版、企業版或資料中心版本</span><span class="sxs-lookup"><span data-stu-id="2c66f-176">Standard, Enterprise, or Datacenter Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="2c66f-177">SP2</span><span class="sxs-lookup"><span data-stu-id="2c66f-177">SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="2c66f-178">x86</span><span class="sxs-lookup"><span data-stu-id="2c66f-178">x86</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2c66f-179">Windows Server2008 R2</span><span class="sxs-lookup"><span data-stu-id="2c66f-179">Windows Server2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="2c66f-180">標準版、企業版或資料中心版本</span><span class="sxs-lookup"><span data-stu-id="2c66f-180">Standard, Enterprise, or Datacenter Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="2c66f-181">沒有 service pack 或 SP1</span><span class="sxs-lookup"><span data-stu-id="2c66f-181">No service pack or SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="2c66f-182">x64</span><span class="sxs-lookup"><span data-stu-id="2c66f-182">x64</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2c66f-183">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="2c66f-183">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="2c66f-184">標準版、企業版或資料中心版本</span><span class="sxs-lookup"><span data-stu-id="2c66f-184">Standard, Enterprise, or Datacenter Edition</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="2c66f-185">x86 或 x64</span><span class="sxs-lookup"><span data-stu-id="2c66f-185">x86 or x64</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="2c66f-186">**記事** 應用程式虛擬化（App-v）4.6 遠端桌面服務的 SP2 支援這些作業系統的32位與64位版本。</span><span class="sxs-lookup"><span data-stu-id="2c66f-186">**Note** Application Virtualization (App-V) 4.6 SP2 for Remote Desktop Services supports 32-bit and 64-bit versions of these operating systems.</span></span>

 

### <span data-ttu-id="2c66f-187">在 App-v 4.6 SP2 之前的版本的遠端桌面服務的軟體需求</span><span class="sxs-lookup"><span data-stu-id="2c66f-187">Software Requirements for Remote Desktop Services for Versions that Precede App-V 4.6 SP2</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2c66f-188">作業系統</span><span class="sxs-lookup"><span data-stu-id="2c66f-188">Operating System</span></span></th>
<th align="left"><span data-ttu-id="2c66f-189">版本</span><span class="sxs-lookup"><span data-stu-id="2c66f-189">Edition</span></span></th>
<th align="left"><span data-ttu-id="2c66f-190">Service Pack</span><span class="sxs-lookup"><span data-stu-id="2c66f-190">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="2c66f-191">系統架構</span><span class="sxs-lookup"><span data-stu-id="2c66f-191">System Architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2c66f-192">Windows Server2003</span><span class="sxs-lookup"><span data-stu-id="2c66f-192">Windows Server2003</span></span></p></td>
<td align="left"><p><span data-ttu-id="2c66f-193">標準版、企業版或資料中心版本</span><span class="sxs-lookup"><span data-stu-id="2c66f-193">Standard Edition, Enterprise Edition, or Datacenter Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="2c66f-194">SP1 或 SP2</span><span class="sxs-lookup"><span data-stu-id="2c66f-194">SP1 or SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="2c66f-195">x86</span><span class="sxs-lookup"><span data-stu-id="2c66f-195">x86</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2c66f-196">Windows Server2003 R2</span><span class="sxs-lookup"><span data-stu-id="2c66f-196">Windows Server2003 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="2c66f-197">標準版、企業版或資料中心版本</span><span class="sxs-lookup"><span data-stu-id="2c66f-197">Standard Edition, Enterprise Edition, or Datacenter Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="2c66f-198">沒有 service pack 或 SP2</span><span class="sxs-lookup"><span data-stu-id="2c66f-198">No service pack or SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="2c66f-199">x86</span><span class="sxs-lookup"><span data-stu-id="2c66f-199">x86</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2c66f-200">Windows Server2008</span><span class="sxs-lookup"><span data-stu-id="2c66f-200">Windows Server2008</span></span></p></td>
<td align="left"><p><span data-ttu-id="2c66f-201">標準版、企業版或資料中心版本</span><span class="sxs-lookup"><span data-stu-id="2c66f-201">Standard, Enterprise, or Datacenter Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="2c66f-202">SP1 或 SP2</span><span class="sxs-lookup"><span data-stu-id="2c66f-202">SP1 or SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="2c66f-203">x86</span><span class="sxs-lookup"><span data-stu-id="2c66f-203">x86</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2c66f-204">Windows Server2008 R2</span><span class="sxs-lookup"><span data-stu-id="2c66f-204">Windows Server2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="2c66f-205">標準版、企業版或資料中心版本</span><span class="sxs-lookup"><span data-stu-id="2c66f-205">Standard, Enterprise, or Datacenter Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="2c66f-206">沒有 service pack 或 SP1</span><span class="sxs-lookup"><span data-stu-id="2c66f-206">No service pack or SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="2c66f-207">x64</span><span class="sxs-lookup"><span data-stu-id="2c66f-207">x64</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="2c66f-208">**記事** 應用程式虛擬化（App-v）4.6 遠端桌面服務的 SP2 支援這些作業系統的32位與64位版本。</span><span class="sxs-lookup"><span data-stu-id="2c66f-208">**Note** Application Virtualization (App-V) 4.6 SP2 for Remote Desktop Services supports 32-bit and 64-bit versions of these operating systems.</span></span>

 

## <span data-ttu-id="2c66f-209">相關主題</span><span class="sxs-lookup"><span data-stu-id="2c66f-209">Related topics</span></span>


[<span data-ttu-id="2c66f-210">Application Virtualization Client 硬體和軟體需求</span><span class="sxs-lookup"><span data-stu-id="2c66f-210">Application Virtualization Client Hardware and Software Requirements</span></span>](application-virtualization-client-hardware-and-software-requirements.md)

[<span data-ttu-id="2c66f-211">Application Virtualization 系統需求</span><span class="sxs-lookup"><span data-stu-id="2c66f-211">Application Virtualization System Requirements</span></span>](application-virtualization-system-requirements.md)

[<span data-ttu-id="2c66f-212">如何安裝 Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="2c66f-212">How to Install the Application Virtualization Sequencer</span></span>](how-to-install-the-application-virtualization-sequencer.md)

[<span data-ttu-id="2c66f-213">如何升級 Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="2c66f-213">How to Upgrade the Application Virtualization Sequencer</span></span>](how-to-upgrade-the-application-virtualization-sequencer.md)

 

 





