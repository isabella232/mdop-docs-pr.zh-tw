---
title: DaRT 10 支援的組態
description: DaRT 10 支援的組態
author: dansimp
ms.assetid: a07d6562-1fa9-499f-829c-9cc487ede0b7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 414b9d5cb7bf78dcfeda3fafc1c476e367709446
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800268"
---
# <span data-ttu-id="3eb26-103">DaRT 10 支援的組態</span><span class="sxs-lookup"><span data-stu-id="3eb26-103">DaRT 10 Supported Configurations</span></span>


<span data-ttu-id="3eb26-104">本主題指定在您的環境中安裝並執行 Microsoft Diagnostics 和復原工具集（DaRT）10所需的必備軟體和支援的設定需求。</span><span class="sxs-lookup"><span data-stu-id="3eb26-104">This topic specifies the prerequisite software and supported configurations requirements that are necessary to install and run Microsoft Diagnostics and Recovery Toolset (DaRT) 10 in your environment.</span></span> <span data-ttu-id="3eb26-105">系統會指定執行 DaRT 10 所需的作業系統需求與系統需求。</span><span class="sxs-lookup"><span data-stu-id="3eb26-105">Both the operating system requirements and the system requirements that are required to run DaRT 10 are specified.</span></span> <span data-ttu-id="3eb26-106">如需需要考慮建立 DaRT 復原影像的先決條件資訊，請參閱[規劃以建立 dart 10 復原影像](planning-to-create-the-dart-10-recovery-image.md)。</span><span class="sxs-lookup"><span data-stu-id="3eb26-106">For information about prerequisites that you need to consider to create the DaRT recovery image, see [Planning to Create the DaRT 10 Recovery Image](planning-to-create-the-dart-10-recovery-image.md).</span></span>

<span data-ttu-id="3eb26-107">如需適用于日後發行的支援設定，請參閱適用版本的檔。</span><span class="sxs-lookup"><span data-stu-id="3eb26-107">For supported configurations that apply to later releases, see the documentation for the applicable release.</span></span>

<span data-ttu-id="3eb26-108">您可以透過兩種方式之一來安裝 DaRT。</span><span class="sxs-lookup"><span data-stu-id="3eb26-108">You can install DaRT in one of two ways.</span></span> <span data-ttu-id="3eb26-109">您可以在 IT 系統管理員電腦上安裝所有功能，您將會執行所有與執行的 DaRT 相關聯的工作。</span><span class="sxs-lookup"><span data-stu-id="3eb26-109">You can install all functionality on an IT administrator computer, where you will perform all the tasks associated with running DaRT.</span></span> <span data-ttu-id="3eb26-110">或者，您也可以在系統管理員電腦上，只安裝建立復原影像的 DaRT 功能，然後在技術支援部電腦上安裝用於執行 DaRT （也就是 DaRT 遠端連線檢視器）的功能。</span><span class="sxs-lookup"><span data-stu-id="3eb26-110">Alternatively, you can install, on the administrator computer, only the DaRT functionality that creates the recovery image, and then install the functionality used to run DaRT (that is, the DaRT Remote Connection Viewer) on a help desk computer.</span></span>

## <span data-ttu-id="3eb26-111">DaRT 10 必備軟體</span><span class="sxs-lookup"><span data-stu-id="3eb26-111">DaRT 10 prerequisite software</span></span>


<span data-ttu-id="3eb26-112">在安裝 DaRT 之前，請務必符合下列先決條件。</span><span class="sxs-lookup"><span data-stu-id="3eb26-112">Make sure that the following prerequisites are met before you install DaRT.</span></span>

### <span data-ttu-id="3eb26-113">系統管理員電腦的先決條件</span><span class="sxs-lookup"><span data-stu-id="3eb26-113">Administrator computer prerequisites</span></span>

<span data-ttu-id="3eb26-114">下表列出安裝 DaRT 10 和所有 DaRT 工具時系統管理員電腦的安裝先決條件。</span><span class="sxs-lookup"><span data-stu-id="3eb26-114">The following table lists the installation prerequisites for the administrator computer when you are installing DaRT 10 and all of the DaRT tools.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3eb26-115">必備</span><span class="sxs-lookup"><span data-stu-id="3eb26-115">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="3eb26-116">詳細資料</span><span class="sxs-lookup"><span data-stu-id="3eb26-116">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="3eb26-117">Windows 評估與開發套件（ADK）</span><span class="sxs-lookup"><span data-stu-id="3eb26-117">Windows Assessment and Development Kit (ADK)</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3eb26-118">DaRT 復原映射嚮導所需。</span><span class="sxs-lookup"><span data-stu-id="3eb26-118">Required for the DaRT Recovery Image wizard.</span></span> <span data-ttu-id="3eb26-119">包含部署工具，可用於自訂、部署及服務 Windows 影像，以及包含 Windows 預先安裝環境（Windows PE）。</span><span class="sxs-lookup"><span data-stu-id="3eb26-119">Contains the Deployment Tools, which are used to customize, deploy, and service Windows images, and contains the Windows Preinstallation Environment (Windows PE).</span></span> <span data-ttu-id="3eb26-120">如果您只安裝遠端連線檢視器和/或故障分析程式，則不需要 ADK。</span><span class="sxs-lookup"><span data-stu-id="3eb26-120">The ADK is not required if you are installing only the Remote Connection Viewer and/or Crash Analyzer.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="3eb26-121">Windows 開發套件或軟體發展套件（選用）</span><span class="sxs-lookup"><span data-stu-id="3eb26-121">Windows Development Kit OR Software Development Kit (optional)</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3eb26-122">故障分析程式需要來自 Windows 驅動程式套件的 Windows 10 調試工具來分析記憶體傾印檔案。</span><span class="sxs-lookup"><span data-stu-id="3eb26-122">Crash Analyzer requires the Windows 10 Debugging Tools from the Windows Driver Kit to analyze memory dump files.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="3eb26-123">Windows 10 64 位或32位 ISO 影像</span><span class="sxs-lookup"><span data-stu-id="3eb26-123">Windows 10 64-bit or 32-bit ISO image</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3eb26-124">DaRT 需要 windows 10 媒體的 Windows 復原環境（Windows RE）影像。</span><span class="sxs-lookup"><span data-stu-id="3eb26-124">DaRT requires the Windows Recovery Environment (Windows RE) image from the Windows 10 media.</span></span> <span data-ttu-id="3eb26-125">根據您想要建立的 DaRT 復原影像類型，下載32位或64位版本的 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="3eb26-125">Download the 32-bit or 64-bit version of Windows 10, depending on the type of DaRT recovery image you want to create.</span></span> <span data-ttu-id="3eb26-126">如果您在您的環境中同時支援這兩種系統類型，請下載這兩個版本的 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="3eb26-126">If you support both system types in your environment, download both versions of Windows 10.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="3eb26-127">協助桌上型電腦必備元件</span><span class="sxs-lookup"><span data-stu-id="3eb26-127">Help desk computer prerequisites</span></span>

<span data-ttu-id="3eb26-128">下表列出執行 DaRT 10 遠端連線檢視器時，協助台電腦的安裝先決條件。</span><span class="sxs-lookup"><span data-stu-id="3eb26-128">The following table lists the installation prerequisites for the help desk computer when you are running the DaRT 10 Remote Connection Viewer.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3eb26-129">必備</span><span class="sxs-lookup"><span data-stu-id="3eb26-129">Prerequisite</span></span></th>
<th align="left"><span data-ttu-id="3eb26-130">詳細資料</span><span class="sxs-lookup"><span data-stu-id="3eb26-130">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="3eb26-131">DaRT 10 遠端連線檢視器</span><span class="sxs-lookup"><span data-stu-id="3eb26-131">DaRT 10 Remote Connection Viewer</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3eb26-132">必須安裝在 Windows 10 作業系統上。</span><span class="sxs-lookup"><span data-stu-id="3eb26-132">Must be installed on a Windows 10 operating system.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="3eb26-133">Windows 版調試工具</span><span class="sxs-lookup"><span data-stu-id="3eb26-133">Debugging Tools for Windows</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3eb26-134">只有在安裝 [損毀分析程式] 工具時才需要</span><span class="sxs-lookup"><span data-stu-id="3eb26-134">Required only if you are installing the Crash Analyzer tool</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="3eb26-135">最終使用者電腦必備元件</span><span class="sxs-lookup"><span data-stu-id="3eb26-135">End-user computer prerequisites</span></span>

<span data-ttu-id="3eb26-136">除了 Windows 10 作業系統之外，不需要在最終使用者電腦上安裝任何必備軟體。</span><span class="sxs-lookup"><span data-stu-id="3eb26-136">There is no prerequisite software that must be installed on end-user computers, other than the Windows 10 operating system.</span></span>

## <a href="" id="---------dart-10-operating-system-requirements"></a> <span data-ttu-id="3eb26-137">DaRT 10 作業系統需求</span><span class="sxs-lookup"><span data-stu-id="3eb26-137">DaRT 10 operating system requirements</span></span>


### <span data-ttu-id="3eb26-138">管理員電腦系統需求</span><span class="sxs-lookup"><span data-stu-id="3eb26-138">Administrator computer system requirements</span></span>

<span data-ttu-id="3eb26-139">下表列出 DaRT 10 系統管理員電腦安裝支援的作業系統。</span><span class="sxs-lookup"><span data-stu-id="3eb26-139">The following table lists the operating systems that are supported for the DaRT 10 administrator computer installation.</span></span>

<span data-ttu-id="3eb26-140">**記事** 針對您想要在系統管理員電腦上安裝的任何其他工具，請務必為您分配足夠的空間。</span><span class="sxs-lookup"><span data-stu-id="3eb26-140">**Note** Make sure that you allocate enough space for any additional tools that you want to install on the administrator computer.</span></span>

 

<span data-ttu-id="3eb26-141">**記事** Microsoft 提供目前 service pack 的支援，在某些情況下，也是最前面的 service pack。</span><span class="sxs-lookup"><span data-stu-id="3eb26-141">**Note** Microsoft provides support for the current service pack and, in some cases, the immediately preceding service pack.</span></span> <span data-ttu-id="3eb26-142">若要尋找您產品的支援時程表，請參閱[支援的生命週期服務套件](https://go.microsoft.com/fwlink/p/?LinkId=31975)。</span><span class="sxs-lookup"><span data-stu-id="3eb26-142">To find the support timelines for your product, see the [Lifecycle Supported Service Packs](https://go.microsoft.com/fwlink/p/?LinkId=31975).</span></span> <span data-ttu-id="3eb26-143">如需 Microsoft 支援週期原則的其他相關資訊，請參閱[Microsoft 支援週期支援原則常見問題](https://go.microsoft.com/fwlink/p/?LinkId=31976)。</span><span class="sxs-lookup"><span data-stu-id="3eb26-143">For additional information about Microsoft Support Lifecycle Policy, see [Microsoft Support Lifecycle Support Policy FAQ](https://go.microsoft.com/fwlink/p/?LinkId=31976).</span></span>

 

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
<th align="left"><span data-ttu-id="3eb26-144">作業系統</span><span class="sxs-lookup"><span data-stu-id="3eb26-144">Operating System</span></span></th>
<th align="left"><span data-ttu-id="3eb26-145">版本</span><span class="sxs-lookup"><span data-stu-id="3eb26-145">Edition</span></span></th>
<th align="left"><span data-ttu-id="3eb26-146">Service Pack</span><span class="sxs-lookup"><span data-stu-id="3eb26-146">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="3eb26-147">系統架構</span><span class="sxs-lookup"><span data-stu-id="3eb26-147">System Architecture</span></span></th>
<th align="left"><span data-ttu-id="3eb26-148">作業系統需求</span><span class="sxs-lookup"><span data-stu-id="3eb26-148">Operating System Requirements</span></span></th>
<th align="left"><span data-ttu-id="3eb26-149">執行 DaRT 所需的 RAM 需求</span><span class="sxs-lookup"><span data-stu-id="3eb26-149">RAM Requirement for Running DaRT</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3eb26-150">Windows 10</span><span class="sxs-lookup"><span data-stu-id="3eb26-150">Windows10</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-151">所有版本</span><span class="sxs-lookup"><span data-stu-id="3eb26-151">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-152">無</span><span class="sxs-lookup"><span data-stu-id="3eb26-152">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-153">64 位元</span><span class="sxs-lookup"><span data-stu-id="3eb26-153">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-154">2 GB</span><span class="sxs-lookup"><span data-stu-id="3eb26-154">2 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-155">2.5 GB</span><span class="sxs-lookup"><span data-stu-id="3eb26-155">2.5 GB</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3eb26-156">Windows 10</span><span class="sxs-lookup"><span data-stu-id="3eb26-156">Windows10</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-157">所有版本</span><span class="sxs-lookup"><span data-stu-id="3eb26-157">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-158">無</span><span class="sxs-lookup"><span data-stu-id="3eb26-158">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-159">32 位元</span><span class="sxs-lookup"><span data-stu-id="3eb26-159">32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-160">1 GB</span><span class="sxs-lookup"><span data-stu-id="3eb26-160">1 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-161">1.5 GB</span><span class="sxs-lookup"><span data-stu-id="3eb26-161">1.5 GB</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="-------------dart-help-desk-computer-system-requirements"></a> <span data-ttu-id="3eb26-162">DaRT 問訊台電腦系統需求</span><span class="sxs-lookup"><span data-stu-id="3eb26-162">DaRT help desk computer system requirements</span></span>

<span data-ttu-id="3eb26-163">如果您允許服務台遠端對電腦進行疑難排解，您必須在技術支援部電腦上安裝遠端連線檢視器。</span><span class="sxs-lookup"><span data-stu-id="3eb26-163">If you allow a help desk to remotely troubleshoot computers, you must have the Remote Connection Viewer installed on the help desk computer.</span></span> <span data-ttu-id="3eb26-164">您可以選擇性地在技術支援部電腦上安裝 [崩潰分析工具]。</span><span class="sxs-lookup"><span data-stu-id="3eb26-164">You can optionally install the Crash Analyzer tool on the help desk computer.</span></span>

<span data-ttu-id="3eb26-165">DaRT 10 可讓技術支援人員使用 DaRT 7.0、DaRT 8.0、DaRt 8.1 或 DaRT 10 遠端連線檢視器，連線至 DaRT 10 電腦。</span><span class="sxs-lookup"><span data-stu-id="3eb26-165">DaRT 10 enables a help desk worker to connect to a DaRT 10 computer by using either the DaRT 7.0, DaRT 8.0, DaRt 8.1, or DaRT 10 Remote Connection Viewer.</span></span> <span data-ttu-id="3eb26-166">DaRT 7.0、DaRT 8.0 和 DaRt 8.1、遠端連線檢視器分別需要 Windows 7、Windows 8 或 Windows 8.1 作業系統，而 DaRT 10 遠端連線檢視器需要 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="3eb26-166">The DaRT 7.0, DaRT 8.0 and DaRt 8.1, Remote Connection Viewers require Windows 7, Windows 8, or Windows 8.1 operating systems respectively, while the DaRT 10 Remote Connection Viewer requires Windows 10.</span></span> <span data-ttu-id="3eb26-167">DaRT 10 遠端連線檢視器和所有其他 DaRT 10 工具只能安裝在執行 Windows 10 的電腦上。</span><span class="sxs-lookup"><span data-stu-id="3eb26-167">The DaRT 10 Remote Connection Viewer and all other DaRT 10 tools can be installed only on a computer running Windows 10.</span></span>

<span data-ttu-id="3eb26-168">下表列出 DaRT 問訊台電腦安裝支援的作業系統。</span><span class="sxs-lookup"><span data-stu-id="3eb26-168">The following table lists the operating systems that are supported for the DaRT help desk computer installation.</span></span>

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
<th align="left"><span data-ttu-id="3eb26-169">作業系統</span><span class="sxs-lookup"><span data-stu-id="3eb26-169">Operating System</span></span></th>
<th align="left"><span data-ttu-id="3eb26-170">版本</span><span class="sxs-lookup"><span data-stu-id="3eb26-170">Edition</span></span></th>
<th align="left"><span data-ttu-id="3eb26-171">Service Pack</span><span class="sxs-lookup"><span data-stu-id="3eb26-171">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="3eb26-172">系統架構</span><span class="sxs-lookup"><span data-stu-id="3eb26-172">System Architecture</span></span></th>
<th align="left"><span data-ttu-id="3eb26-173">作業系統需求</span><span class="sxs-lookup"><span data-stu-id="3eb26-173">Operating System Requirements</span></span></th>
<th align="left"><span data-ttu-id="3eb26-174">運行 DaRT 的記憶體需求</span><span class="sxs-lookup"><span data-stu-id="3eb26-174">RAM Requirements for Running DaRT</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3eb26-175">Windows 10</span><span class="sxs-lookup"><span data-stu-id="3eb26-175">Windows10</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-176">所有版本</span><span class="sxs-lookup"><span data-stu-id="3eb26-176">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-177">無</span><span class="sxs-lookup"><span data-stu-id="3eb26-177">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-178">64 位元</span><span class="sxs-lookup"><span data-stu-id="3eb26-178">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-179">2 GB</span><span class="sxs-lookup"><span data-stu-id="3eb26-179">2 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-180">2.5 GB</span><span class="sxs-lookup"><span data-stu-id="3eb26-180">2.5 GB</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3eb26-181">Windows10 （僅適用于遠端連線檢視器10.0）</span><span class="sxs-lookup"><span data-stu-id="3eb26-181">Windows10 (with Remote Connection Viewer 10.0 only)</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-182">所有版本</span><span class="sxs-lookup"><span data-stu-id="3eb26-182">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-183">無</span><span class="sxs-lookup"><span data-stu-id="3eb26-183">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-184">32 位元</span><span class="sxs-lookup"><span data-stu-id="3eb26-184">32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-185">1 GB</span><span class="sxs-lookup"><span data-stu-id="3eb26-185">1 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-186">1.5 GB</span><span class="sxs-lookup"><span data-stu-id="3eb26-186">1.5 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3eb26-187">Windows8</span><span class="sxs-lookup"><span data-stu-id="3eb26-187">Windows8</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-188">所有版本</span><span class="sxs-lookup"><span data-stu-id="3eb26-188">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-189">無</span><span class="sxs-lookup"><span data-stu-id="3eb26-189">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-190">64 位元</span><span class="sxs-lookup"><span data-stu-id="3eb26-190">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-191">2 GB</span><span class="sxs-lookup"><span data-stu-id="3eb26-191">2 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-192">2.5 GB</span><span class="sxs-lookup"><span data-stu-id="3eb26-192">2.5 GB</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3eb26-193">Windows8 （僅適用于遠端連線檢視器8.0）</span><span class="sxs-lookup"><span data-stu-id="3eb26-193">Windows8 (with Remote Connection Viewer 8.0 only)</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-194">所有版本</span><span class="sxs-lookup"><span data-stu-id="3eb26-194">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-195">無</span><span class="sxs-lookup"><span data-stu-id="3eb26-195">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-196">32 位元</span><span class="sxs-lookup"><span data-stu-id="3eb26-196">32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-197">1 GB</span><span class="sxs-lookup"><span data-stu-id="3eb26-197">1 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-198">1.5 GB</span><span class="sxs-lookup"><span data-stu-id="3eb26-198">1.5 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3eb26-199">Windows 7 （僅適用于遠端連線檢視器7.0）</span><span class="sxs-lookup"><span data-stu-id="3eb26-199">Windows 7 (with Remote Connection Viewer 7.0 only)</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-200">所有版本</span><span class="sxs-lookup"><span data-stu-id="3eb26-200">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-201">SP1、SP2</span><span class="sxs-lookup"><span data-stu-id="3eb26-201">SP1, SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-202">64位或32位</span><span class="sxs-lookup"><span data-stu-id="3eb26-202">64-bit or 32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-203">1 GB</span><span class="sxs-lookup"><span data-stu-id="3eb26-203">1 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-204">無</span><span class="sxs-lookup"><span data-stu-id="3eb26-204">N/A</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3eb26-205">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="3eb26-205">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-206">標準，企業，資料中心</span><span class="sxs-lookup"><span data-stu-id="3eb26-206">Standard, Enterprise, Data Center</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-207">無</span><span class="sxs-lookup"><span data-stu-id="3eb26-207">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-208">64 位元</span><span class="sxs-lookup"><span data-stu-id="3eb26-208">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-209">2 GB</span><span class="sxs-lookup"><span data-stu-id="3eb26-209">2 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-210">1.0 GB</span><span class="sxs-lookup"><span data-stu-id="3eb26-210">1.0 GB</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3eb26-211">WindowsServer 2012 R2</span><span class="sxs-lookup"><span data-stu-id="3eb26-211">Windows Server 2012 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-212">標準，企業，資料中心</span><span class="sxs-lookup"><span data-stu-id="3eb26-212">Standard, Enterprise, Data Center</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-213">無</span><span class="sxs-lookup"><span data-stu-id="3eb26-213">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-214">64 位元</span><span class="sxs-lookup"><span data-stu-id="3eb26-214">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-215">2 GB</span><span class="sxs-lookup"><span data-stu-id="3eb26-215">2 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-216">1.0 GB</span><span class="sxs-lookup"><span data-stu-id="3eb26-216">1.0 GB</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="3eb26-217">DaRT 在最終使用者電腦中也有下列最低硬體需求：</span><span class="sxs-lookup"><span data-stu-id="3eb26-217">DaRT also has the following minimum hardware requirements for the end-user computer:</span></span>

<span data-ttu-id="3eb26-218">CD 或 DVD 光碟機或 USB 埠-只有當您在企業中使用 CD、DVD 或 USB 部署 DaRT 時才需要。</span><span class="sxs-lookup"><span data-stu-id="3eb26-218">A CD or DVD drive or a USB port - required only if you are deploying DaRT in your enterprise by using a CD, DVD, or USB.</span></span>

<span data-ttu-id="3eb26-219">從 CD 或 DVD、USB 快閃記憶體磁片磁碟機或從遠端或復原分區啟動電腦的 BIOS 支援。</span><span class="sxs-lookup"><span data-stu-id="3eb26-219">BIOS support for starting the computer from a CD or DVD, a USB flash drive, or from a remote or recovery partition.</span></span>

### <a href="" id="-------------dart-10-end-user-computer-system-requirements"></a> <span data-ttu-id="3eb26-220">DaRT 10 端使用者電腦系統需求</span><span class="sxs-lookup"><span data-stu-id="3eb26-220">DaRT 10 end-user computer system requirements</span></span>

<span data-ttu-id="3eb26-221">DaRT 10 中的 [診斷與修復工具組] 視窗要求最終使用者電腦使用下列其中一個作業系統，以及適用于 DaRT 的指定系統記憶體數量：</span><span class="sxs-lookup"><span data-stu-id="3eb26-221">The Diagnostics and Recovery Toolset window in DaRT 10 requires that the end-user computer use one of the following operating systems together with the specified amount of system memory available for DaRT:</span></span>

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
<th align="left"><span data-ttu-id="3eb26-222">作業系統</span><span class="sxs-lookup"><span data-stu-id="3eb26-222">Operating System</span></span></th>
<th align="left"><span data-ttu-id="3eb26-223">版本</span><span class="sxs-lookup"><span data-stu-id="3eb26-223">Edition</span></span></th>
<th align="left"><span data-ttu-id="3eb26-224">Service Pack</span><span class="sxs-lookup"><span data-stu-id="3eb26-224">Service Pack</span></span></th>
<th align="left"><span data-ttu-id="3eb26-225">系統架構</span><span class="sxs-lookup"><span data-stu-id="3eb26-225">System Architecture</span></span></th>
<th align="left"><span data-ttu-id="3eb26-226">作業系統需求</span><span class="sxs-lookup"><span data-stu-id="3eb26-226">Operating System Requirements</span></span></th>
<th align="left"><span data-ttu-id="3eb26-227">RAM 需求</span><span class="sxs-lookup"><span data-stu-id="3eb26-227">RAM Requirements</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3eb26-228">Windows 10</span><span class="sxs-lookup"><span data-stu-id="3eb26-228">Windows10</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-229">所有版本</span><span class="sxs-lookup"><span data-stu-id="3eb26-229">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-230">無</span><span class="sxs-lookup"><span data-stu-id="3eb26-230">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-231">64 位元</span><span class="sxs-lookup"><span data-stu-id="3eb26-231">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-232">2 GB</span><span class="sxs-lookup"><span data-stu-id="3eb26-232">2 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-233">2.5 GB</span><span class="sxs-lookup"><span data-stu-id="3eb26-233">2.5 GB</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3eb26-234">Windows 10</span><span class="sxs-lookup"><span data-stu-id="3eb26-234">Windows10</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-235">所有版本</span><span class="sxs-lookup"><span data-stu-id="3eb26-235">All editions</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-236">無</span><span class="sxs-lookup"><span data-stu-id="3eb26-236">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-237">32 位元</span><span class="sxs-lookup"><span data-stu-id="3eb26-237">32-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-238">1 GB</span><span class="sxs-lookup"><span data-stu-id="3eb26-238">1 GB</span></span></p></td>
<td align="left"><p><span data-ttu-id="3eb26-239">1.5 GB</span><span class="sxs-lookup"><span data-stu-id="3eb26-239">1.5 GB</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="3eb26-240">相關主題</span><span class="sxs-lookup"><span data-stu-id="3eb26-240">Related topics</span></span>


[<span data-ttu-id="3eb26-241">規劃部署 DaRT 10</span><span class="sxs-lookup"><span data-stu-id="3eb26-241">Planning to Deploy DaRT 10</span></span>](planning-to-deploy-dart-10.md)

 

 





