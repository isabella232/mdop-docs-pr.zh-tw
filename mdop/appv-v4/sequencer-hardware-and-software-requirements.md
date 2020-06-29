---
title: 排序器硬體和軟體需求
description: 排序器硬體和軟體需求
author: dansimp
ms.assetid: 36084e12-831d-452f-a4a4-45f07f9ce471
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0d4e12a5803a3c9033513424826b49bc0bca5885
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800838"
---
# <span data-ttu-id="9d7af-103">排序器硬體和軟體需求</span><span class="sxs-lookup"><span data-stu-id="9d7af-103">Sequencer Hardware and Software Requirements</span></span>


<span data-ttu-id="9d7af-104">本主題描述執行 Microsoft Application Virtualization （App-v） Sequencer 的電腦所建議的最低硬體和軟體需求。</span><span class="sxs-lookup"><span data-stu-id="9d7af-104">This topic describes the minimum recommended hardware and software requirements for the computer running the Microsoft Application Virtualization (App-V) Sequencer.</span></span>

<span data-ttu-id="9d7af-105">您必須先將乾淨的作業系統映射還原至順序電腦，然後才能安裝排序器並排序每個應用程式。</span><span class="sxs-lookup"><span data-stu-id="9d7af-105">Before you install the Sequencer and after you sequence each application, you must restore a clean operating system image to the sequencing computer.</span></span> <span data-ttu-id="9d7af-106">您可以使用下列其中一種方法來還原執行排序器的電腦：</span><span class="sxs-lookup"><span data-stu-id="9d7af-106">You can use one of the following methods to restore the computer running the Sequencer:</span></span>

-   <span data-ttu-id="9d7af-107">重新格式化硬碟並重新安裝作業系統。</span><span class="sxs-lookup"><span data-stu-id="9d7af-107">Reformat the hard drive and reinstall the operating system.</span></span>

-   <span data-ttu-id="9d7af-108">使用另一個磁片影像軟體，在執行 Sequencer 影像的電腦上還原硬碟。</span><span class="sxs-lookup"><span data-stu-id="9d7af-108">Restore the hard drive on the computer running the Sequencer image by using another disk-imaging software.</span></span>

<span data-ttu-id="9d7af-109">下列清單概括了執行 App-v 排序器的建議硬體需求。</span><span class="sxs-lookup"><span data-stu-id="9d7af-109">The following list outlines the recommended hardware requirements for running the App-V Sequencer.</span></span>

### <a href="" id="hardware-requirements-"></a><span data-ttu-id="9d7af-110">硬體需求</span><span class="sxs-lookup"><span data-stu-id="9d7af-110">Hardware Requirements</span></span>

-   <span data-ttu-id="9d7af-111">處理器-英特爾奔騰 III，1 GHz （32位或64位）。</span><span class="sxs-lookup"><span data-stu-id="9d7af-111">Processor—Intel Pentium III, 1 GHz (32-bit or 64-bit).</span></span> <span data-ttu-id="9d7af-112">排序流程是單一線程處理，不會利用雙處理器。</span><span class="sxs-lookup"><span data-stu-id="9d7af-112">The sequencing process is a single-threaded process and does not take advantage of dual processors.</span></span>

-   <span data-ttu-id="9d7af-113">記憶體-1GB 或更新版本，建議 2 GB。</span><span class="sxs-lookup"><span data-stu-id="9d7af-113">Memory—1GB or above, 2 GB recommended.</span></span>

-   <span data-ttu-id="9d7af-114">硬碟-40 gb 硬碟空間，至少可提供 15 GB 的可用硬碟空間。</span><span class="sxs-lookup"><span data-stu-id="9d7af-114">Hard Disk—40 gigabyte (GB) hard disk space with a minimum of 15 GB available hard disk space.</span></span> <span data-ttu-id="9d7af-115">我們建議您至少有三倍您要排序之應用程式的硬碟空間需要。</span><span class="sxs-lookup"><span data-stu-id="9d7af-115">We recommend that you have at least three times the hard disk space that the application you are sequencing requires.</span></span>

    <span data-ttu-id="9d7af-116">**記事** 排序需要大量的磁片使用量。</span><span class="sxs-lookup"><span data-stu-id="9d7af-116">**Note** Sequencing requires heavy disk usage.</span></span> <span data-ttu-id="9d7af-117">較快的磁片速度可能會減少排序時間。</span><span class="sxs-lookup"><span data-stu-id="9d7af-117">A fast disk speed can decrease the sequencing time.</span></span>

     

### <span data-ttu-id="9d7af-118">軟體需求</span><span class="sxs-lookup"><span data-stu-id="9d7af-118">Software Requirements</span></span>

<span data-ttu-id="9d7af-119">下列清單列出執行排序器所支援的作業系統。</span><span class="sxs-lookup"><span data-stu-id="9d7af-119">The following list outlines the supported operating systems for running the Sequencer.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9d7af-120">作業系統</span><span class="sxs-lookup"><span data-stu-id="9d7af-120">Operating System</span></span></th>
<th align="left"><span data-ttu-id="9d7af-121">版本</span><span class="sxs-lookup"><span data-stu-id="9d7af-121">Edition</span></span></th>
<th align="left"><span data-ttu-id="9d7af-122">Service Pack</span><span class="sxs-lookup"><span data-stu-id="9d7af-122">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="9d7af-123">系統架構</span><span class="sxs-lookup"><span data-stu-id="9d7af-123">System Architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9d7af-124">WindowsXP</span><span class="sxs-lookup"><span data-stu-id="9d7af-124">WindowsXP</span></span></p></td>
<td align="left"><p><span data-ttu-id="9d7af-125">專業版</span><span class="sxs-lookup"><span data-stu-id="9d7af-125">Professional</span></span></p></td>
<td align="left"><p><span data-ttu-id="9d7af-126">SP2 或 SP3</span><span class="sxs-lookup"><span data-stu-id="9d7af-126">SP2 or SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="9d7af-127">x86</span><span class="sxs-lookup"><span data-stu-id="9d7af-127">x86</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9d7af-128">Windows Vista</span><span class="sxs-lookup"><span data-stu-id="9d7af-128">Windows Vista</span></span></p></td>
<td align="left"><p><span data-ttu-id="9d7af-129">企業、企業或旗艦版</span><span class="sxs-lookup"><span data-stu-id="9d7af-129">Business, Enterprise, or Ultimate</span></span></p></td>
<td align="left"><p><span data-ttu-id="9d7af-130">沒有 service pack、SP1 或 SP2</span><span class="sxs-lookup"><span data-stu-id="9d7af-130">No service pack, SP1, or SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="9d7af-131">x86</span><span class="sxs-lookup"><span data-stu-id="9d7af-131">x86</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9d7af-132">Windows7 ¹</span><span class="sxs-lookup"><span data-stu-id="9d7af-132">Windows7¹</span></span></p></td>
<td align="left"><p><span data-ttu-id="9d7af-133">專業版、企業版或旗艦版</span><span class="sxs-lookup"><span data-stu-id="9d7af-133">Professional, Enterprise, or Ultimate</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="9d7af-134">x86</span><span class="sxs-lookup"><span data-stu-id="9d7af-134">x86</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="9d7af-135">¹支援在 SP1 或 SP2 中使用 app-v 4.5，且僅限 App-v 4。6</span><span class="sxs-lookup"><span data-stu-id="9d7af-135">¹Supported for App-V 4.5 with SP1 or SP2, and App-V 4.6 only</span></span>

<span data-ttu-id="9d7af-136">**記事** 應用程式虛擬化（App-v） 4.6 Sequencer 支援這些作業系統的32位與64位版本。</span><span class="sxs-lookup"><span data-stu-id="9d7af-136">**Note** The Application Virtualization (App-V) 4.6 Sequencer supports 32-bit and 64-bit versions of these operating systems.</span></span>

 

<span data-ttu-id="9d7af-137">您應該將執行排序器的電腦設定為在目的電腦上安裝的相同應用程式。</span><span class="sxs-lookup"><span data-stu-id="9d7af-137">You should configure computers running the Sequencer with the same applications that are installed on target computers.</span></span>

### <span data-ttu-id="9d7af-138">遠端桌面服務的軟體需求</span><span class="sxs-lookup"><span data-stu-id="9d7af-138">Software Requirements for Remote Desktop Services</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9d7af-139">作業系統</span><span class="sxs-lookup"><span data-stu-id="9d7af-139">Operating System</span></span></th>
<th align="left"><span data-ttu-id="9d7af-140">版本</span><span class="sxs-lookup"><span data-stu-id="9d7af-140">Edition</span></span></th>
<th align="left"><span data-ttu-id="9d7af-141">Service Pack</span><span class="sxs-lookup"><span data-stu-id="9d7af-141">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="9d7af-142">系統架構</span><span class="sxs-lookup"><span data-stu-id="9d7af-142">System Architecture</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9d7af-143">Windows Server2003</span><span class="sxs-lookup"><span data-stu-id="9d7af-143">Windows Server2003</span></span></p></td>
<td align="left"><p><span data-ttu-id="9d7af-144">標準版、企業版或資料中心版本</span><span class="sxs-lookup"><span data-stu-id="9d7af-144">Standard Edition, Enterprise Edition, or Datacenter Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="9d7af-145">SP1 或 SP2</span><span class="sxs-lookup"><span data-stu-id="9d7af-145">SP1 or SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="9d7af-146">x86</span><span class="sxs-lookup"><span data-stu-id="9d7af-146">x86</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9d7af-147">Windows Server2003 R2</span><span class="sxs-lookup"><span data-stu-id="9d7af-147">Windows Server2003 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="9d7af-148">標準版、企業版或資料中心版本</span><span class="sxs-lookup"><span data-stu-id="9d7af-148">Standard Edition, Enterprise Edition, or Datacenter Edition</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="9d7af-149">x86</span><span class="sxs-lookup"><span data-stu-id="9d7af-149">x86</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9d7af-150">Windows Server2008</span><span class="sxs-lookup"><span data-stu-id="9d7af-150">Windows Server2008</span></span></p></td>
<td align="left"><p><span data-ttu-id="9d7af-151">標準版、企業版或資料中心</span><span class="sxs-lookup"><span data-stu-id="9d7af-151">Standard, Enterprise, or Datacenter</span></span></p></td>
<td align="left"><p><span data-ttu-id="9d7af-152">SP1 或 SP2</span><span class="sxs-lookup"><span data-stu-id="9d7af-152">SP1 or SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="9d7af-153">x86</span><span class="sxs-lookup"><span data-stu-id="9d7af-153">x86</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="9d7af-154">**記事** 適用于遠端桌面服務的 Application Virtualization （App-v）4.6 支援這些作業系統的32位與64位版本。</span><span class="sxs-lookup"><span data-stu-id="9d7af-154">**Note** Application Virtualization (App-V) 4.6 for Remote Desktop Services supports 32-bit and 64-bit versions of these operating systems.</span></span>

 

## <span data-ttu-id="9d7af-155">相關主題</span><span class="sxs-lookup"><span data-stu-id="9d7af-155">Related topics</span></span>


[<span data-ttu-id="9d7af-156">Application Virtualization Sequencer 概觀</span><span class="sxs-lookup"><span data-stu-id="9d7af-156">Application Virtualization Sequencer Overview</span></span>](application-virtualization-sequencer-overview.md)

 

 





