---
title: DaRT 8.0 支援的組態
description: DaRT 8.0 支援的組態
author: dansimp
ms.assetid: 95d68e5c-d202-4f4a-adef-d2098328172e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 02c891555992652bf2a9b2b674ab8377536ef9d6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810250"
---
# <span data-ttu-id="db9f0-103">DaRT 8.0 支援的組態</span><span class="sxs-lookup"><span data-stu-id="db9f0-103">DaRT 8.0 Supported Configurations</span></span>


<span data-ttu-id="db9f0-104">本主題指定安裝並在您的環境中執行 Microsoft Diagnostics 和復原工具集（DaRT）8.0 所需的必備軟體和支援的設定需求。</span><span class="sxs-lookup"><span data-stu-id="db9f0-104">This topic specifies the prerequisite software and supported configurations requirements that are necessary to install and run Microsoft Diagnostics and Recovery Toolset (DaRT) 8.0 in your environment.</span></span> <span data-ttu-id="db9f0-105">系統會指定執行 DaRT 8.0 所需的作業系統需求與系統需求。</span><span class="sxs-lookup"><span data-stu-id="db9f0-105">Both the operating system requirements and the system requirements that are required to run DaRT 8.0 are specified.</span></span> <span data-ttu-id="db9f0-106">如需考慮建立 DaRT 復原影像所需考慮的先決條件資訊，請參閱[規劃以建立 dart 8.0 恢復影像](planning-to-create-the-dart-80-recovery-image-dart-8.md)。</span><span class="sxs-lookup"><span data-stu-id="db9f0-106">For information about prerequisites that you need to consider to create the DaRT recovery image, see [Planning to Create the DaRT 8.0 Recovery Image](planning-to-create-the-dart-80-recovery-image-dart-8.md).</span></span>

<span data-ttu-id="db9f0-107">如需適用于日後發行的支援設定，請參閱適用版本的檔。</span><span class="sxs-lookup"><span data-stu-id="db9f0-107">For supported configurations that apply to later releases, see the documentation for the applicable release.</span></span>

<span data-ttu-id="db9f0-108">您可以透過兩種方式之一來安裝 DaRT。</span><span class="sxs-lookup"><span data-stu-id="db9f0-108">You can install DaRT in one of two ways.</span></span> <span data-ttu-id="db9f0-109">您可以在 IT 系統管理員電腦上安裝所有功能，您將會執行所有與執行的 DaRT 相關聯的工作。</span><span class="sxs-lookup"><span data-stu-id="db9f0-109">You can install all functionality on an IT administrator computer, where you will perform all the tasks associated with running DaRT.</span></span> <span data-ttu-id="db9f0-110">或者，您也可以在系統管理員電腦上，只安裝建立復原影像的 DaRT 功能，然後在技術支援部電腦上安裝用於執行 DaRT （也就是 DaRT 遠端連線檢視器）的功能。</span><span class="sxs-lookup"><span data-stu-id="db9f0-110">Alternatively, you can install, on the administrator computer, only the DaRT functionality that creates the recovery image, and then install the functionality used to run DaRT (that is, the DaRT Remote Connection Viewer) on a help desk computer.</span></span>

## <a href="" id="---------dart-8-0-prerequisite-software"></a> <span data-ttu-id="db9f0-111">DaRT 8.0 必備軟體</span><span class="sxs-lookup"><span data-stu-id="db9f0-111">DaRT 8.0 prerequisite software</span></span>


<span data-ttu-id="db9f0-112">在安裝 DaRT 之前，請務必符合下列先決條件。</span><span class="sxs-lookup"><span data-stu-id="db9f0-112">Make sure that the following prerequisites are met before you install DaRT.</span></span>

### <span data-ttu-id="db9f0-113">系統管理員電腦的先決條件</span><span class="sxs-lookup"><span data-stu-id="db9f0-113">Administrator computer prerequisites</span></span>

<span data-ttu-id="db9f0-114">下表列出安裝 DaRT 8.0 和所有 DaRT 工具時系統管理員電腦的安裝先決條件。</span><span class="sxs-lookup"><span data-stu-id="db9f0-114">The following table lists the installation prerequisites for the administrator computer when you are installing DaRT 8.0 and all of the DaRT tools.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="db9f0-115">必備</span><span class="sxs-lookup"><span data-stu-id="db9f0-115">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="db9f0-116">詳細資料</span><span class="sxs-lookup"><span data-stu-id="db9f0-116">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="db9f0-117">Windows 評估與開發套件（ADK）</span><span class="sxs-lookup"><span data-stu-id="db9f0-117">Windows Assessment and Development Kit (ADK)</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="db9f0-118">DaRT 復原映射嚮導所需。</span><span class="sxs-lookup"><span data-stu-id="db9f0-118">Required for the DaRT Recovery Image wizard.</span></span> <span data-ttu-id="db9f0-119">包含部署工具，可用於自訂、部署及服務 Windows 影像，以及包含 Windows 預先安裝環境（Windows PE）。</span><span class="sxs-lookup"><span data-stu-id="db9f0-119">Contains the Deployment Tools, which are used to customize, deploy, and service Windows images, and contains the Windows Preinstallation Environment (Windows PE).</span></span> <span data-ttu-id="db9f0-120">如果您只安裝遠端連線檢視器和/或故障分析程式，則不需要 ADK。</span><span class="sxs-lookup"><span data-stu-id="db9f0-120">The ADK is not required if you are installing only the Remote Connection Viewer and/or Crash Analyzer.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="db9f0-121">.NET Framework 4。5</span><span class="sxs-lookup"><span data-stu-id="db9f0-121">.NET Framework 4.5</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="db9f0-122">DaRT 復原映射嚮導所需。</span><span class="sxs-lookup"><span data-stu-id="db9f0-122">Required by the DaRT Recovery Image wizard.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="db9f0-123">Windows 開發套件或軟體發展套件（選用）</span><span class="sxs-lookup"><span data-stu-id="db9f0-123">Windows Development Kit OR Software Development Kit (optional)</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="db9f0-124">故障分析程式需要 Windows 驅動程式套件的 Windows 8 調試工具來分析記憶體傾印檔案。</span><span class="sxs-lookup"><span data-stu-id="db9f0-124">Crash Analyzer requires the Windows 8 Debugging Tools from the Windows Driver Kit to analyze memory dump files.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="db9f0-125">Windows 8 64 位 ISO 影像</span><span class="sxs-lookup"><span data-stu-id="db9f0-125">Windows 8 64-bit ISO image</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="db9f0-126">DaRT 需要 Windows 8 媒體的 Windows 復原環境（Windows RE）影像。</span><span class="sxs-lookup"><span data-stu-id="db9f0-126">DaRT requires the Windows Recovery Environment (Windows RE) image from the Windows 8 media.</span></span> <span data-ttu-id="db9f0-127">根據您想要建立的 DaRT 復原影像類型，下載32位或64位版本的 Windows 8。</span><span class="sxs-lookup"><span data-stu-id="db9f0-127">Download the 32-bit or 64-bit version of Windows 8, depending on the type of DaRT recovery image you want to create.</span></span> <span data-ttu-id="db9f0-128">如果您在您的環境中同時支援這兩種系統類型，請下載這兩個版本的 Windows 8。</span><span class="sxs-lookup"><span data-stu-id="db9f0-128">If you support both system types in your environment, download both versions of Windows 8.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="db9f0-129">協助桌上型電腦必備元件</span><span class="sxs-lookup"><span data-stu-id="db9f0-129">Help desk computer prerequisites</span></span>

<span data-ttu-id="db9f0-130">下表列出執行 DaRT 8.0 遠端連線檢視器時，支援中心電腦的安裝先決條件。</span><span class="sxs-lookup"><span data-stu-id="db9f0-130">The following table lists the installation prerequisites for the help desk computer when you are running the DaRT 8.0 Remote Connection Viewer.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="db9f0-131">必備</span><span class="sxs-lookup"><span data-stu-id="db9f0-131">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="db9f0-132">詳細資料</span><span class="sxs-lookup"><span data-stu-id="db9f0-132">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="db9f0-133">DaRT 8.0 遠端連線檢視器</span><span class="sxs-lookup"><span data-stu-id="db9f0-133">DaRT 8.0 Remote Connection Viewer</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="db9f0-134">必須安裝在 Windows 8 作業系統上。</span><span class="sxs-lookup"><span data-stu-id="db9f0-134">Must be installed on a Windows 8 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="db9f0-135">NET Framework 4。5</span><span class="sxs-lookup"><span data-stu-id="db9f0-135">NET Framework 4.5</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="db9f0-136">DaRT 復原映像嚮導所需</span><span class="sxs-lookup"><span data-stu-id="db9f0-136">Required by the DaRT Recovery Image wizard</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="db9f0-137">Windows 版調試工具</span><span class="sxs-lookup"><span data-stu-id="db9f0-137">Debugging Tools for Windows</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="db9f0-138">只有在安裝 [損毀分析程式] 工具時才需要</span><span class="sxs-lookup"><span data-stu-id="db9f0-138">Required only if you are installing the Crash Analyzer tool</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="db9f0-139">最終使用者電腦必備元件</span><span class="sxs-lookup"><span data-stu-id="db9f0-139">End-user computer prerequisites</span></span>

<span data-ttu-id="db9f0-140">除了 Windows 8 作業系統之外，不需要在最終使用者電腦上安裝任何必備軟體。</span><span class="sxs-lookup"><span data-stu-id="db9f0-140">There is no prerequisite software that must be installed on end-user computers, other than the Windows 8 operating system.</span></span>

## <a href="" id="---------dart-operating-system-requirements"></a> <span data-ttu-id="db9f0-141">DaRT 作業系統需求</span><span class="sxs-lookup"><span data-stu-id="db9f0-141">DaRT operating system requirements</span></span>


### <span data-ttu-id="db9f0-142">管理員電腦系統需求</span><span class="sxs-lookup"><span data-stu-id="db9f0-142">Administrator computer system requirements</span></span>

<span data-ttu-id="db9f0-143">下表列出 DaRT 系統管理員電腦安裝支援的作業系統。</span><span class="sxs-lookup"><span data-stu-id="db9f0-143">The following table lists the operating systems that are supported for the DaRT administrator computer installation.</span></span>

<span data-ttu-id="db9f0-144">**記事** 針對您想要在系統管理員電腦上安裝的任何其他工具，請務必為您分配足夠的空間。</span><span class="sxs-lookup"><span data-stu-id="db9f0-144">**Note** Make sure that you allocate enough space for any additional tools that you want to install on the administrator computer.</span></span>

 

<span data-ttu-id="db9f0-145">**記事** Microsoft 提供目前 service pack 的支援，在某些情況下，也是最前面的 service pack。</span><span class="sxs-lookup"><span data-stu-id="db9f0-145">**Note** Microsoft provides support for the current service pack and, in some cases, the immediately preceding service pack.</span></span> <span data-ttu-id="db9f0-146">若要尋找您產品的支援時程表，請參閱[支援的生命週期服務套件](https://go.microsoft.com/fwlink/p/?LinkId=31975)。</span><span class="sxs-lookup"><span data-stu-id="db9f0-146">To find the support timelines for your product, see the [Lifecycle Supported Service Packs](https://go.microsoft.com/fwlink/p/?LinkId=31975).</span></span> <span data-ttu-id="db9f0-147">如需 Microsoft 支援週期原則的其他相關資訊，請參閱[Microsoft 支援週期支援原則常見問題](https://go.microsoft.com/fwlink/p/?LinkId=31976)。</span><span class="sxs-lookup"><span data-stu-id="db9f0-147">For additional information about Microsoft Support Lifecycle Policy, see [Microsoft Support Lifecycle Support Policy FAQ](https://go.microsoft.com/fwlink/p/?LinkId=31976).</span></span>

 

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="db9f0-148">作業系統</span><span class="sxs-lookup"><span data-stu-id="db9f0-148">Operating System</span></span></th>
<th align="left"><span data-ttu-id="db9f0-149">版本</span><span class="sxs-lookup"><span data-stu-id="db9f0-149">Edition</span></span></th>
<th align="left"><span data-ttu-id="db9f0-150">Service Pack</span><span class="sxs-lookup"><span data-stu-id="db9f0-150">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="db9f0-151">系統架構</span><span class="sxs-lookup"><span data-stu-id="db9f0-151">System Architecture</span></span></th>
<th align="left"><span data-ttu-id="db9f0-152">作業系統需求</span><span class="sxs-lookup"><span data-stu-id="db9f0-152">Operating System Requirements</span></span></th>
<th align="left"><span data-ttu-id="db9f0-153">執行 DaRT 所需的 RAM 需求</span><span class="sxs-lookup"><span data-stu-id="db9f0-153">RAM Requirement for Running DaRT</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="db9f0-154">Windows8</span><span class="sxs-lookup"><span data-stu-id="db9f0-154">Windows8</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-155">所有版本</span><span class="sxs-lookup"><span data-stu-id="db9f0-155">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-156">無</span><span class="sxs-lookup"><span data-stu-id="db9f0-156">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-157">64 位元</span><span class="sxs-lookup"><span data-stu-id="db9f0-157">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-158">2 GB</span><span class="sxs-lookup"><span data-stu-id="db9f0-158">2 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-159">2.5 GB</span><span class="sxs-lookup"><span data-stu-id="db9f0-159">2.5 GB</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="db9f0-160">Windows8</span><span class="sxs-lookup"><span data-stu-id="db9f0-160">Windows8</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-161">所有版本</span><span class="sxs-lookup"><span data-stu-id="db9f0-161">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-162">無</span><span class="sxs-lookup"><span data-stu-id="db9f0-162">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-163">32 位元</span><span class="sxs-lookup"><span data-stu-id="db9f0-163">32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-164">1 GB</span><span class="sxs-lookup"><span data-stu-id="db9f0-164">1 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-165">1.5 GB</span><span class="sxs-lookup"><span data-stu-id="db9f0-165">1.5 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="db9f0-166">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="db9f0-166">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-167">標準，企業，資料中心</span><span class="sxs-lookup"><span data-stu-id="db9f0-167">Standard, Enterprise, Data Center</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-168">無</span><span class="sxs-lookup"><span data-stu-id="db9f0-168">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-169">64 位元</span><span class="sxs-lookup"><span data-stu-id="db9f0-169">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-170">512 MB</span><span class="sxs-lookup"><span data-stu-id="db9f0-170">512 MB</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-171">1. 0 GB</span><span class="sxs-lookup"><span data-stu-id="db9f0-171">1 .0 GB</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="-------------dart-help-desk-computer-system-requirements"></a> <span data-ttu-id="db9f0-172">DaRT 問訊台電腦系統需求</span><span class="sxs-lookup"><span data-stu-id="db9f0-172">DaRT help desk computer system requirements</span></span>

<span data-ttu-id="db9f0-173">如果您允許服務台遠端對電腦進行疑難排解，您必須在技術支援部電腦上安裝遠端連線檢視器。</span><span class="sxs-lookup"><span data-stu-id="db9f0-173">If you allow a help desk to remotely troubleshoot computers, you must have the Remote Connection Viewer installed on the help desk computer.</span></span> <span data-ttu-id="db9f0-174">您可以選擇性地在技術支援部電腦上安裝 [崩潰分析工具]。</span><span class="sxs-lookup"><span data-stu-id="db9f0-174">You can optionally install the Crash Analyzer tool on the help desk computer.</span></span>

<span data-ttu-id="db9f0-175">DaRT 8.0 可讓技術支援人員使用 DaRT 7.0 或 DaRT 8.0 遠端連線檢視器連線至 DaRT 8.0 電腦。</span><span class="sxs-lookup"><span data-stu-id="db9f0-175">DaRT 8.0 enables a help desk worker to connect to a DaRT 8.0 computer by using either the DaRT 7.0 or DaRT 8.0 Remote Connection Viewer.</span></span> <span data-ttu-id="db9f0-176">DaRT 7.0 遠端連線檢視器需要 Windows 7 作業系統，而 DaRT 8.0 遠端連線檢視器需要 Windows 8。</span><span class="sxs-lookup"><span data-stu-id="db9f0-176">The DaRT 7.0 Remote Connection Viewer requires a Windows 7 operating system, while the DaRT 8.0 Remote Connection Viewer requires Windows 8.</span></span> <span data-ttu-id="db9f0-177">DaRT 8.0 遠端連線檢視器和所有其他的 DaRT 8.0 工具只能安裝在執行 Windows 8 的電腦上。</span><span class="sxs-lookup"><span data-stu-id="db9f0-177">The DaRT 8.0 Remote Connection Viewer and all other DaRT 8.0 tools can be installed only on a computer running Windows 8.</span></span>

<span data-ttu-id="db9f0-178">下表列出 DaRT 問訊台電腦安裝支援的作業系統。</span><span class="sxs-lookup"><span data-stu-id="db9f0-178">The following table lists the operating systems that are supported for the DaRT help desk computer installation.</span></span>

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="db9f0-179">作業系統</span><span class="sxs-lookup"><span data-stu-id="db9f0-179">Operating System</span></span></th>
<th align="left"><span data-ttu-id="db9f0-180">版本</span><span class="sxs-lookup"><span data-stu-id="db9f0-180">Edition</span></span></th>
<th align="left"><span data-ttu-id="db9f0-181">Service Pack</span><span class="sxs-lookup"><span data-stu-id="db9f0-181">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="db9f0-182">系統架構</span><span class="sxs-lookup"><span data-stu-id="db9f0-182">System Architecture</span></span></th>
<th align="left"><span data-ttu-id="db9f0-183">作業系統需求</span><span class="sxs-lookup"><span data-stu-id="db9f0-183">Operating System Requirements</span></span></th>
<th align="left"><span data-ttu-id="db9f0-184">運行 DaRT 的記憶體需求</span><span class="sxs-lookup"><span data-stu-id="db9f0-184">RAM Requirements for Running DaRT</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="db9f0-185">Windows8</span><span class="sxs-lookup"><span data-stu-id="db9f0-185">Windows8</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-186">所有版本</span><span class="sxs-lookup"><span data-stu-id="db9f0-186">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-187">無</span><span class="sxs-lookup"><span data-stu-id="db9f0-187">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-188">64 位元</span><span class="sxs-lookup"><span data-stu-id="db9f0-188">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-189">2 GB</span><span class="sxs-lookup"><span data-stu-id="db9f0-189">2 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-190">2.5 GB</span><span class="sxs-lookup"><span data-stu-id="db9f0-190">2.5 GB</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="db9f0-191">Windows8 （僅適用于遠端連線檢視器8.0）</span><span class="sxs-lookup"><span data-stu-id="db9f0-191">Windows8 (with Remote Connection Viewer 8.0 only)</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-192">所有版本</span><span class="sxs-lookup"><span data-stu-id="db9f0-192">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-193">無</span><span class="sxs-lookup"><span data-stu-id="db9f0-193">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-194">32 位元</span><span class="sxs-lookup"><span data-stu-id="db9f0-194">32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-195">1 GB</span><span class="sxs-lookup"><span data-stu-id="db9f0-195">1 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-196">1.5 GB</span><span class="sxs-lookup"><span data-stu-id="db9f0-196">1.5 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="db9f0-197">Windows 7 （僅適用于遠端連線檢視器7.0）</span><span class="sxs-lookup"><span data-stu-id="db9f0-197">Windows 7 (with Remote Connection Viewer 7.0 only)</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-198">所有版本</span><span class="sxs-lookup"><span data-stu-id="db9f0-198">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-199">SP1、SP2</span><span class="sxs-lookup"><span data-stu-id="db9f0-199">SP1, SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-200">64位或32位</span><span class="sxs-lookup"><span data-stu-id="db9f0-200">64-bit or 32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-201">1 GB</span><span class="sxs-lookup"><span data-stu-id="db9f0-201">1 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-202">無</span><span class="sxs-lookup"><span data-stu-id="db9f0-202">N/A</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="db9f0-203">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="db9f0-203">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-204">標準，企業，資料中心</span><span class="sxs-lookup"><span data-stu-id="db9f0-204">Standard, Enterprise, Data Center</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-205">無</span><span class="sxs-lookup"><span data-stu-id="db9f0-205">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-206">64 位元</span><span class="sxs-lookup"><span data-stu-id="db9f0-206">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-207">51</span><span class="sxs-lookup"><span data-stu-id="db9f0-207">51</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-208">1.0 GB</span><span class="sxs-lookup"><span data-stu-id="db9f0-208">1.0 GB</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="db9f0-209">DaRT 在最終使用者電腦中也有下列最低硬體需求：</span><span class="sxs-lookup"><span data-stu-id="db9f0-209">DaRT also has the following minimum hardware requirements for the end-user computer:</span></span>

<span data-ttu-id="db9f0-210">CD 或 DVD 光碟機或 USB 埠-只有當您在企業中使用 CD、DVD 或 USB 部署 DaRT 時才需要。</span><span class="sxs-lookup"><span data-stu-id="db9f0-210">A CD or DVD drive or a USB port - required only if you are deploying DaRT in your enterprise by using a CD, DVD, or USB.</span></span>

<span data-ttu-id="db9f0-211">從 CD 或 DVD、USB 快閃記憶體磁片磁碟機或從遠端或復原分區啟動電腦的 BIOS 支援。</span><span class="sxs-lookup"><span data-stu-id="db9f0-211">BIOS support for starting the computer from a CD or DVD, a USB flash drive, or from a remote or recovery partition.</span></span>

### <a href="" id="-------------dart-end-user-computer-system-requirements"></a> <span data-ttu-id="db9f0-212">DaRT 最終使用者電腦系統需求</span><span class="sxs-lookup"><span data-stu-id="db9f0-212">DaRT end-user computer system requirements</span></span>

<span data-ttu-id="db9f0-213">DaRT 中的 [診斷與修復工具集] 視窗要求最終使用者電腦使用下列其中一個作業系統，以及適用于 DaRT 的指定系統記憶體數量：</span><span class="sxs-lookup"><span data-stu-id="db9f0-213">The Diagnostics and Recovery Toolset window in DaRT requires that the end-user computer use one of the following operating systems together with the specified amount of system memory available for DaRT:</span></span>

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="db9f0-214">作業系統</span><span class="sxs-lookup"><span data-stu-id="db9f0-214">Operating System</span></span></th>
<th align="left"><span data-ttu-id="db9f0-215">版本</span><span class="sxs-lookup"><span data-stu-id="db9f0-215">Edition</span></span></th>
<th align="left"><span data-ttu-id="db9f0-216">Service Pack</span><span class="sxs-lookup"><span data-stu-id="db9f0-216">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="db9f0-217">系統架構</span><span class="sxs-lookup"><span data-stu-id="db9f0-217">System Architecture</span></span></th>
<th align="left"><span data-ttu-id="db9f0-218">作業系統需求</span><span class="sxs-lookup"><span data-stu-id="db9f0-218">Operating System Requirements</span></span></th>
<th align="left"><span data-ttu-id="db9f0-219">RAM 需求</span><span class="sxs-lookup"><span data-stu-id="db9f0-219">RAM Requirements</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="db9f0-220">Windows8</span><span class="sxs-lookup"><span data-stu-id="db9f0-220">Windows8</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-221">所有版本</span><span class="sxs-lookup"><span data-stu-id="db9f0-221">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-222">無</span><span class="sxs-lookup"><span data-stu-id="db9f0-222">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-223">64 位元</span><span class="sxs-lookup"><span data-stu-id="db9f0-223">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-224">2 GB</span><span class="sxs-lookup"><span data-stu-id="db9f0-224">2 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-225">2.5 GB</span><span class="sxs-lookup"><span data-stu-id="db9f0-225">2.5 GB</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="db9f0-226">Windows8</span><span class="sxs-lookup"><span data-stu-id="db9f0-226">Windows8</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-227">所有版本</span><span class="sxs-lookup"><span data-stu-id="db9f0-227">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-228">無</span><span class="sxs-lookup"><span data-stu-id="db9f0-228">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-229">32 位元</span><span class="sxs-lookup"><span data-stu-id="db9f0-229">32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-230">1 GB</span><span class="sxs-lookup"><span data-stu-id="db9f0-230">1 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-231">1.5 GB</span><span class="sxs-lookup"><span data-stu-id="db9f0-231">1.5 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="db9f0-232">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="db9f0-232">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-233">標準，企業，資料中心</span><span class="sxs-lookup"><span data-stu-id="db9f0-233">Standard, Enterprise, Data Center</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-234">無</span><span class="sxs-lookup"><span data-stu-id="db9f0-234">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-235">64 位元</span><span class="sxs-lookup"><span data-stu-id="db9f0-235">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-236">512 MB</span><span class="sxs-lookup"><span data-stu-id="db9f0-236">512 MB</span></span></p></td>
<td align="left"><p><span data-ttu-id="db9f0-237">1.0 GB</span><span class="sxs-lookup"><span data-stu-id="db9f0-237">1.0 GB</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="db9f0-238">相關主題</span><span class="sxs-lookup"><span data-stu-id="db9f0-238">Related topics</span></span>


[<span data-ttu-id="db9f0-239">規劃部署 DaRT 8.0</span><span class="sxs-lookup"><span data-stu-id="db9f0-239">Planning to Deploy DaRT 8.0</span></span>](planning-to-deploy-dart-80-dart-8.md)

 

 





