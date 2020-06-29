---
title: AGPM 4.0 SP3 的新功能
description: AGPM 4.0 SP3 的新功能
author: dansimp
ms.assetid: df495d55-9fbf-4f7e-a7af-3905f4f8790e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 09/27/2016
ms.openlocfilehash: a98bda82fab561113522382b4de6539a9dc23d0c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802489"
---
# <span data-ttu-id="05e4d-103">AGPM 4.0 SP3 的新功能</span><span class="sxs-lookup"><span data-stu-id="05e4d-103">What's New in AGPM 4.0 SP3</span></span>


<span data-ttu-id="05e4d-104">此內容說明 Microsoft Advanced 群組原則管理（AGPM）4.0 服務 Pack3 （SP3）的增強功能和支援的設定。</span><span class="sxs-lookup"><span data-stu-id="05e4d-104">This content describes enhancements and supported configurations for Microsoft Advanced Group Policy Management (AGPM)4.0 Service Pack3 (SP3).</span></span> <span data-ttu-id="05e4d-105">如果此內容與其他 AGPM 檔之間有差異，請考慮此內容的權威性，並假設它取代其他檔。</span><span class="sxs-lookup"><span data-stu-id="05e4d-105">If there is a difference between this content and other AGPM documentation, consider this content authoritative and assume that it supersedes the other documentation.</span></span>

## <a href="" id="what-s-new"></a><span data-ttu-id="05e4d-106">新功能</span><span class="sxs-lookup"><span data-stu-id="05e4d-106">What’s new</span></span>


<span data-ttu-id="05e4d-107">AGPM 4.0 SP3 支援下列功能和功能。</span><span class="sxs-lookup"><span data-stu-id="05e4d-107">AGPM4.0 SP3 supports the following features and functionality.</span></span>

### <span data-ttu-id="05e4d-108">支援 Windows10</span><span class="sxs-lookup"><span data-stu-id="05e4d-108">Support for Windows10</span></span>

<span data-ttu-id="05e4d-109">AGPM 4.0 SP3 會新增 Windows10 和 Windows Server 2016 作業系統的支援。</span><span class="sxs-lookup"><span data-stu-id="05e4d-109">AGPM4.0 SP3 adds support for the Windows10 and Windows Server 2016 operating systems.</span></span>

### <span data-ttu-id="05e4d-110">PowerShell 支援</span><span class="sxs-lookup"><span data-stu-id="05e4d-110">Support for PowerShell</span></span>

<span data-ttu-id="05e4d-111">AGPM 4.0 SP3 新增 PowerShell Cmdlet 的支援。</span><span class="sxs-lookup"><span data-stu-id="05e4d-111">AGPM4.0 SP3 adds support for PowerShell cmdlets.</span></span> <span data-ttu-id="05e4d-112">如需在 AGPM 4.0 SP3 中提供的 Cmdlet 清單，包括描述及語法，請參閱[使用 Windows PowerShell 的 Microsoft 桌面優化套件自動化](https://docs.microsoft.com/powershell/mdop/get-started?view=win-mdop2-ps)。</span><span class="sxs-lookup"><span data-stu-id="05e4d-112">For a list of the cmdlets available in AGPM4.0 SP3, including descriptions and syntax, see [Microsoft Desktop Optimization Pack Automation with Windows PowerShell](https://docs.microsoft.com/powershell/mdop/get-started?view=win-mdop2-ps).</span></span>

### <span data-ttu-id="05e4d-113">客戶意見反應與修補程式匯總</span><span class="sxs-lookup"><span data-stu-id="05e4d-113">Customer feedback and hotfix rollup</span></span>

<span data-ttu-id="05e4d-114">AGPM 4.0 SP3 包括所有修正的匯總，包括 Microsoft 高級群組原則管理 4.0 SP2，以及自 AGPM 4.0 SP2 之後發現問題的修正程式。</span><span class="sxs-lookup"><span data-stu-id="05e4d-114">AGPM 4.0 SP3 includes a rollup of all fixes up to and including Microsoft Advanced Group Policy Management 4.0 SP2 and any fixes for issues found since AGPM 4.0 SP2.</span></span>

### <span data-ttu-id="05e4d-115">能夠升級至 AGPM 4.0 SP3，而不需重新輸入配置參數</span><span class="sxs-lookup"><span data-stu-id="05e4d-115">Ability to upgrade to AGPM4.0 SP3 without re-entering configuration parameters</span></span>

<span data-ttu-id="05e4d-116">您可以將 AGPM 用戶端或 AGPM 服務器升級至 AGPM 4.0 SP3，而不會提示您重新輸入來自 AGPM 4.0 和更新版本的設定參數（稱為 [智慧升級]），如下表所示。</span><span class="sxs-lookup"><span data-stu-id="05e4d-116">You can upgrade the AGPM Client or AGPM Server to AGPM4.0 SP3 without being prompted to re-enter configuration parameters (called the Smart Upgrade) only from AGPM4.0 and later, as shown in the following table.</span></span> <span data-ttu-id="05e4d-117">如果您要從其他版本的 AGPM 升級到 AGPM 4.0 SP3 （如下表所示），您必須使用 [傳統升級]，這需要您重新輸入配置參數。</span><span class="sxs-lookup"><span data-stu-id="05e4d-117">If you are upgrading to AGPM4.0 SP3 from other versions of AGPM, as shown in the table, you must use the Classic Upgrade, which requires you to re-enter the configuration parameters.</span></span> <span data-ttu-id="05e4d-118">由於每個版本的 AGPM 都與特定的作業系統相關聯，請參閱[選擇要安裝的 Agpm 版本](https://go.microsoft.com/fwlink/?LinkId=254350)，並確認您在升級 AGPM 之前，請先升級您的作業系統。</span><span class="sxs-lookup"><span data-stu-id="05e4d-118">Because each version of AGPM is associated with a particular operating system, see [Choosing Which Version of AGPM to Install](https://go.microsoft.com/fwlink/?LinkId=254350) and make sure that you upgrade your operating system as appropriate before you upgrade AGPM.</span></span>

**<span data-ttu-id="05e4d-119">AGPM 4.0 SP3 支援的升級</span><span class="sxs-lookup"><span data-stu-id="05e4d-119">AGPM 4.0 SP3 supported upgrades</span></span>**

<table style="width:100%;">
<colgroup>
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
<col width="14%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="05e4d-120">您可以升級的 AGPM 版本</span><span class="sxs-lookup"><span data-stu-id="05e4d-120">AGPM version from which you can upgrade</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="05e4d-121">2.5</span><span class="sxs-lookup"><span data-stu-id="05e4d-121">2.5</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="05e4d-122">3.0</span><span class="sxs-lookup"><span data-stu-id="05e4d-122">3.0</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="05e4d-123">4.0</span><span class="sxs-lookup"><span data-stu-id="05e4d-123">4.0</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="05e4d-124">4.0 SP1</span><span class="sxs-lookup"><span data-stu-id="05e4d-124">4.0 SP1</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="05e4d-125">4.0 SP2</span><span class="sxs-lookup"><span data-stu-id="05e4d-125">4.0 SP2</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="05e4d-126">4.0 SP3</span><span class="sxs-lookup"><span data-stu-id="05e4d-126">4.0 SP3</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="05e4d-127">2.5</span><span class="sxs-lookup"><span data-stu-id="05e4d-127">2.5</span></span></p></td>
<td align="left"><p><span data-ttu-id="05e4d-128">不適用</span><span class="sxs-lookup"><span data-stu-id="05e4d-128">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="05e4d-129">傳統升級</span><span class="sxs-lookup"><span data-stu-id="05e4d-129">Classic Upgrade</span></span></p></td>
<td align="left"><p><span data-ttu-id="05e4d-130">傳統升級</span><span class="sxs-lookup"><span data-stu-id="05e4d-130">Classic Upgrade</span></span></p></td>
<td align="left"><p><span data-ttu-id="05e4d-131">安裝遭到封鎖</span><span class="sxs-lookup"><span data-stu-id="05e4d-131">Installation is blocked</span></span></p></td>
<td align="left"><p><span data-ttu-id="05e4d-132">安裝遭到封鎖</span><span class="sxs-lookup"><span data-stu-id="05e4d-132">Installation is blocked</span></span></p></td>
<td align="left"><p><span data-ttu-id="05e4d-133">安裝遭到封鎖</span><span class="sxs-lookup"><span data-stu-id="05e4d-133">Installation is blocked</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="05e4d-134">3.0</span><span class="sxs-lookup"><span data-stu-id="05e4d-134">3.0</span></span></p></td>
<td align="left"><p><span data-ttu-id="05e4d-135">不適用</span><span class="sxs-lookup"><span data-stu-id="05e4d-135">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="05e4d-136">不適用</span><span class="sxs-lookup"><span data-stu-id="05e4d-136">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="05e4d-137">傳統升級</span><span class="sxs-lookup"><span data-stu-id="05e4d-137">Classic Upgrade</span></span></p></td>
<td align="left"><p><span data-ttu-id="05e4d-138">安裝遭到封鎖</span><span class="sxs-lookup"><span data-stu-id="05e4d-138">Installation is blocked</span></span></p></td>
<td align="left"><p><span data-ttu-id="05e4d-139">安裝遭到封鎖</span><span class="sxs-lookup"><span data-stu-id="05e4d-139">Installation is blocked</span></span></p></td>
<td align="left"><p><span data-ttu-id="05e4d-140">安裝遭到封鎖</span><span class="sxs-lookup"><span data-stu-id="05e4d-140">Installation is blocked</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="05e4d-141">4.0</span><span class="sxs-lookup"><span data-stu-id="05e4d-141">4.0</span></span></p></td>
<td align="left"><p><span data-ttu-id="05e4d-142">不適用</span><span class="sxs-lookup"><span data-stu-id="05e4d-142">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="05e4d-143">不適用</span><span class="sxs-lookup"><span data-stu-id="05e4d-143">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="05e4d-144">不適用</span><span class="sxs-lookup"><span data-stu-id="05e4d-144">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="05e4d-145">智慧升級</span><span class="sxs-lookup"><span data-stu-id="05e4d-145">Smart Upgrade</span></span></p></td>
<td align="left"><p><span data-ttu-id="05e4d-146">智慧升級</span><span class="sxs-lookup"><span data-stu-id="05e4d-146">Smart Upgrade</span></span></p></td>
<td align="left"><p><span data-ttu-id="05e4d-147">智慧升級</span><span class="sxs-lookup"><span data-stu-id="05e4d-147">Smart Upgrade</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="05e4d-148">4.0 SP1</span><span class="sxs-lookup"><span data-stu-id="05e4d-148">4.0 SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="05e4d-149">不適用</span><span class="sxs-lookup"><span data-stu-id="05e4d-149">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="05e4d-150">不適用</span><span class="sxs-lookup"><span data-stu-id="05e4d-150">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="05e4d-151">不適用</span><span class="sxs-lookup"><span data-stu-id="05e4d-151">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="05e4d-152">不適用</span><span class="sxs-lookup"><span data-stu-id="05e4d-152">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="05e4d-153">智慧升級</span><span class="sxs-lookup"><span data-stu-id="05e4d-153">Smart Upgrade</span></span></p></td>
<td align="left"><p><span data-ttu-id="05e4d-154">智慧升級</span><span class="sxs-lookup"><span data-stu-id="05e4d-154">Smart Upgrade</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="05e4d-155">4.0 SP2</span><span class="sxs-lookup"><span data-stu-id="05e4d-155">4.0 SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="05e4d-156">不適用</span><span class="sxs-lookup"><span data-stu-id="05e4d-156">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="05e4d-157">不適用</span><span class="sxs-lookup"><span data-stu-id="05e4d-157">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="05e4d-158">不適用</span><span class="sxs-lookup"><span data-stu-id="05e4d-158">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="05e4d-159">不適用</span><span class="sxs-lookup"><span data-stu-id="05e4d-159">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="05e4d-160">不適用</span><span class="sxs-lookup"><span data-stu-id="05e4d-160">Not applicable</span></span></p></td>
<td align="left"><p><span data-ttu-id="05e4d-161">智慧升級</span><span class="sxs-lookup"><span data-stu-id="05e4d-161">Smart Upgrade</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="05e4d-162">支援的設定</span><span class="sxs-lookup"><span data-stu-id="05e4d-162">Supported configurations</span></span>


<span data-ttu-id="05e4d-163">AGPM 4.0 SP3 支援下表中的配置。</span><span class="sxs-lookup"><span data-stu-id="05e4d-163">AGPM4.0 SP3 supports the configurations in the following table.</span></span> <span data-ttu-id="05e4d-164">雖然 AGPM 支援混合式設定，但我們強烈建議您在相同的作業系統線路上執行 AGPM 用戶端和 AGPM 服務器，例如，Windows10 Windows Server 2016、Windows 8.1 Server 2012 R2 等。</span><span class="sxs-lookup"><span data-stu-id="05e4d-164">Although AGPM supports mixed configurations, we strongly recommend that you run the AGPM Client and AGPM Server on the same operating system line—for example, Windows10 with Windows Server 2016, Windows 8.1 with Windows Server 2012 R2, and so on.</span></span>

**<span data-ttu-id="05e4d-165">AGPM 4.0 SP3 支援的作業系統與原則設定</span><span class="sxs-lookup"><span data-stu-id="05e4d-165">AGPM4.0 SP3 supported operating systems and policy settings</span></span>**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="05e4d-166">AGPM 服務器支援的設定</span><span class="sxs-lookup"><span data-stu-id="05e4d-166">Supported configurations for the AGPM Server</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="05e4d-167">適用于 AGPM 用戶端的支援設定</span><span class="sxs-lookup"><span data-stu-id="05e4d-167">Supported configurations for the AGPM Client</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="05e4d-168">AGPM 支援</span><span class="sxs-lookup"><span data-stu-id="05e4d-168">AGPM Support</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="05e4d-169">Windows Server 2016 或 Windows 10</span><span class="sxs-lookup"><span data-stu-id="05e4d-169">Windows Server 2016 or Windows 10</span></span></p></td>
<td align="left"><p><span data-ttu-id="05e4d-170">Windows 10</span><span class="sxs-lookup"><span data-stu-id="05e4d-170">Windows 10</span></span></p></td>
<td align="left"><p><span data-ttu-id="05e4d-171">支援</span><span class="sxs-lookup"><span data-stu-id="05e4d-171">Supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="05e4d-172">Windows Server2012 R2 或 Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="05e4d-172">Windows Server2012 R2 or Windows8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="05e4d-173">Windows Server2012 R2 或 Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="05e4d-173">Windows Server2012 R2 or Windows8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="05e4d-174">支援</span><span class="sxs-lookup"><span data-stu-id="05e4d-174">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="05e4d-175">Windows Server2012 R2、Windows Server 2012 或 Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="05e4d-175">Windows Server2012 R2, Windows Server 2012, or Windows8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="05e4d-176">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="05e4d-176">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="05e4d-177">支援，但無法編輯僅存在於 Windows 8.1 中的原則設定或喜好設定專案</span><span class="sxs-lookup"><span data-stu-id="05e4d-177">Supported, but cannot edit policy settings or preference items that exist only in Windows8.1</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="05e4d-178">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="05e4d-178">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="05e4d-179">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="05e4d-179">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="05e4d-180">支援，但無法編輯僅存在於 Windows 8.1 中的原則設定或喜好設定專案</span><span class="sxs-lookup"><span data-stu-id="05e4d-180">Supported, but cannot edit policy settings or preference items that exist only in Windows8.1</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="05e4d-181">Windows Server 2012、Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="05e4d-181">Windows Server 2012, Windows Server2008R2, or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="05e4d-182">Windows Server2008 或 WindowsVista Service Pack 1 （SP1）</span><span class="sxs-lookup"><span data-stu-id="05e4d-182">Windows Server2008 or WindowsVista with Service Pack 1 (SP1)</span></span></p></td>
<td align="left"><p><span data-ttu-id="05e4d-183">支援，但無法編輯僅存在於 Windows Server2012 R2、windows Server 2012、Windows Server2008R2、Windows 8.1 或 Windows7 中的原則設定或喜好設定專案</span><span class="sxs-lookup"><span data-stu-id="05e4d-183">Supported, but cannot edit policy settings or preference items that exist only in Windows Server2012 R2, Windows Server 2012, Windows Server2008R2, Windows8.1, or Windows7</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="05e4d-184">Windows Server2008 或 Windows Vista （含 SP1）</span><span class="sxs-lookup"><span data-stu-id="05e4d-184">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="05e4d-185">Windows Server 2012、Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="05e4d-185">Windows Server 2012, Windows Server2008R2, or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="05e4d-186">不支援</span><span class="sxs-lookup"><span data-stu-id="05e4d-186">Not supported</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="05e4d-187">Windows Server2008 或 Windows Vista （含 SP1）</span><span class="sxs-lookup"><span data-stu-id="05e4d-187">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="05e4d-188">Windows Server2008 或 Windows Vista （含 SP1）</span><span class="sxs-lookup"><span data-stu-id="05e4d-188">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="05e4d-189">支援，但無法報告或編輯僅存在於 Windows Server2012 R2、windows Server 2012、Windows Server2008R2、Windows 8.1 或 Windows7 中的原則設定或喜好設定專案</span><span class="sxs-lookup"><span data-stu-id="05e4d-189">Supported, but cannot report or edit policy settings or preference items that exist only in Windows Server2012 R2, Windows Server 2012, Windows Server2008R2, Windows8.1, or Windows7</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="05e4d-190">安裝 AGPM 4.0 SP3 的先決條件</span><span class="sxs-lookup"><span data-stu-id="05e4d-190">Prerequisites for installing AGPM4.0 SP3</span></span>

<span data-ttu-id="05e4d-191">下表說明當 .NET Framework 4.5.1、PowerShell 3.0 或遠端伺服器管理工具中的 GPMC 遺失時，AGPM 4.0 SP3 用戶端和伺服器安裝程式的行為。</span><span class="sxs-lookup"><span data-stu-id="05e4d-191">The following table describes the behavior of AGPM4.0 SP3 Client and Server installers when the .NET Framework4.5.1, PowerShell 3.0, or the GPMC in the Remote Server Administration Tools is missing.</span></span>

| <span data-ttu-id="05e4d-192">AGPM 用戶端</span><span class="sxs-lookup"><span data-stu-id="05e4d-192">AGPM Client</span></span>            |                                                                                                 |                                                                            | <span data-ttu-id="05e4d-193">AGPM 服務器</span><span class="sxs-lookup"><span data-stu-id="05e4d-193">AGPM Server</span></span>                                                                     |                                                                                                 |                                                                                 |
|------------------------|-------------------------------------------------------------------------------------------------|----------------------------------------------------------------------------|---------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------------|---------------------------------------------------------------------------------|
| <span data-ttu-id="05e4d-194">作業系統</span><span class="sxs-lookup"><span data-stu-id="05e4d-194">Operating system</span></span>       | <span data-ttu-id="05e4d-195">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="05e4d-195">.NET Framework</span></span>                                                                                  | <span data-ttu-id="05e4d-196">PowerShell</span><span class="sxs-lookup"><span data-stu-id="05e4d-196">PowerShell</span></span>                                                                 | <span data-ttu-id="05e4d-197">遠端伺服器管理工具</span><span class="sxs-lookup"><span data-stu-id="05e4d-197">Remote Server Administration Tools</span></span>                                              | <span data-ttu-id="05e4d-198">.NET Framework</span><span class="sxs-lookup"><span data-stu-id="05e4d-198">.NET Framework</span></span>                                                                                  | <span data-ttu-id="05e4d-199">遠端伺服器管理工具</span><span class="sxs-lookup"><span data-stu-id="05e4d-199">Remote Server Administration Tools</span></span>                                              |
| <span data-ttu-id="05e4d-200">Windows 10</span><span class="sxs-lookup"><span data-stu-id="05e4d-200">Windows 10</span></span>             | <span data-ttu-id="05e4d-201">如果尚未啟用或未安裝 .NET Framework 4.5.1，安裝程式會封鎖安裝。</span><span class="sxs-lookup"><span data-stu-id="05e4d-201">If the .NET Framework 4.5.1 is not enabled or installed, the installer blocks the installation.</span></span> | <span data-ttu-id="05e4d-202">如果未安裝 Powershell 3.0，安裝程式會封鎖安裝。</span><span class="sxs-lookup"><span data-stu-id="05e4d-202">If Powershell 3.0 is not installed, the installer blocks the installation.</span></span> | <span data-ttu-id="05e4d-203">如果未啟用或安裝 GPMC，安裝程式會封鎖安裝。</span><span class="sxs-lookup"><span data-stu-id="05e4d-203">If the GPMC is not enabled or installed, the installer blocks the installation.</span></span> | <span data-ttu-id="05e4d-204">如果尚未啟用或未安裝 .NET Framework 4.5.1，安裝程式會封鎖安裝。</span><span class="sxs-lookup"><span data-stu-id="05e4d-204">If the .NET Framework 4.5.1 is not enabled or installed, the installer blocks the installation.</span></span> | <span data-ttu-id="05e4d-205">如果未啟用或安裝 GPMC，安裝程式會封鎖安裝。</span><span class="sxs-lookup"><span data-stu-id="05e4d-205">If the GPMC is not enabled or installed, the installer blocks the installation.</span></span> |
| <span data-ttu-id="05e4d-206">Windows 8.1</span><span class="sxs-lookup"><span data-stu-id="05e4d-206">Windows 8.1</span></span>            | <span data-ttu-id="05e4d-207">如果尚未啟用或未安裝 .NET Framework 4.5.1，安裝程式會封鎖安裝。</span><span class="sxs-lookup"><span data-stu-id="05e4d-207">If the .NET Framework 4.5.1 is not enabled or installed, the installer blocks the installation.</span></span> | <span data-ttu-id="05e4d-208">如果未安裝 Powershell 3.0，安裝程式會封鎖安裝。</span><span class="sxs-lookup"><span data-stu-id="05e4d-208">If Powershell 3.0 is not installed, the installer blocks the installation.</span></span> | <span data-ttu-id="05e4d-209">如果未啟用或安裝 GPMC，安裝程式會封鎖安裝。</span><span class="sxs-lookup"><span data-stu-id="05e4d-209">If the GPMC is not enabled or installed, the installer blocks the installation.</span></span> | <span data-ttu-id="05e4d-210">如果尚未啟用或未安裝 .NET Framework 4.5.1，安裝程式會封鎖安裝。</span><span class="sxs-lookup"><span data-stu-id="05e4d-210">If the .NET Framework 4.5.1 is not enabled or installed, the installer blocks the installation.</span></span> | <span data-ttu-id="05e4d-211">如果未啟用或安裝 GPMC，安裝程式會封鎖安裝。</span><span class="sxs-lookup"><span data-stu-id="05e4d-211">If the GPMC is not enabled or installed, the installer blocks the installation.</span></span> |
| <span data-ttu-id="05e4d-212">WindowsServer 2012 R2</span><span class="sxs-lookup"><span data-stu-id="05e4d-212">Windows Server 2012 R2</span></span> | <span data-ttu-id="05e4d-213">如果尚未啟用或未安裝 .NET Framework 4.5.1，安裝程式會封鎖安裝。</span><span class="sxs-lookup"><span data-stu-id="05e4d-213">If the .NET Framework 4.5.1 is not enabled or installed, the installer blocks the installation.</span></span> | <span data-ttu-id="05e4d-214">如果未安裝 Powershell 3.0，安裝程式會封鎖安裝。</span><span class="sxs-lookup"><span data-stu-id="05e4d-214">If Powershell 3.0 is not installed, the installer blocks the installation.</span></span> | <span data-ttu-id="05e4d-215">如果未啟用 GPMC，安裝程式會在安裝期間啟用它。</span><span class="sxs-lookup"><span data-stu-id="05e4d-215">If the GPMC is not enabled, the installer enables it during the installation.</span></span>   | <span data-ttu-id="05e4d-216">如果尚未啟用或未安裝 .NET Framework 4.5.1，安裝程式會封鎖安裝。</span><span class="sxs-lookup"><span data-stu-id="05e4d-216">If the .NET Framework 4.5.1 is not enabled or installed, the installer blocks the installation.</span></span> | <span data-ttu-id="05e4d-217">如果未啟用 GPMC，安裝程式會在安裝期間啟用它。</span><span class="sxs-lookup"><span data-stu-id="05e4d-217">If the GPMC is not enabled, the installer enables it during the installation.</span></span>   |

 

## <span data-ttu-id="05e4d-218">如何取得 MDOP 技術</span><span class="sxs-lookup"><span data-stu-id="05e4d-218">How to Get MDOP Technologies</span></span>


<span data-ttu-id="05e4d-219">AGPM 4.0 SP3 是您自 MDOP 2015 之後的 Microsoft 桌面優化套件（MDOP）的一部分。</span><span class="sxs-lookup"><span data-stu-id="05e4d-219">AGPM 4.0 SP3 is a part of the Microsoft Desktop Optimization Pack (MDOP) since MDOP 2015.</span></span> <span data-ttu-id="05e4d-220">MDOP 是 Microsoft 軟體保證的一部分。</span><span class="sxs-lookup"><span data-stu-id="05e4d-220">MDOP is part of Microsoft Software Assurance.</span></span> <span data-ttu-id="05e4d-221">如需 Microsoft 軟體保證及取得 MDOP 的詳細資訊，請參閱[如何取得 mdop](https://go.microsoft.com/fwlink/?LinkId=322049) （ https://go.microsoft.com/fwlink/?LinkId=322049) 。</span><span class="sxs-lookup"><span data-stu-id="05e4d-221">For more information about Microsoft Software Assurance and acquiring MDOP, see [How Do I Get MDOP](https://go.microsoft.com/fwlink/?LinkId=322049) (https://go.microsoft.com/fwlink/?LinkId=322049).</span></span>

## <span data-ttu-id="05e4d-222">相關主題</span><span class="sxs-lookup"><span data-stu-id="05e4d-222">Related topics</span></span>


[<span data-ttu-id="05e4d-223">進階群組原則管理</span><span class="sxs-lookup"><span data-stu-id="05e4d-223">Advanced Group Policy Management</span></span>](index.md)

[<span data-ttu-id="05e4d-224">Microsoft 進階群組原則管理 4.0 SP3 版本資訊</span><span class="sxs-lookup"><span data-stu-id="05e4d-224">Release Notes for Microsoft Advanced Group Policy Management 4.0 SP3</span></span>](release-notes-for-microsoft-advanced-group-policy-management-40-sp3.md)

[<span data-ttu-id="05e4d-225">選擇要安裝的 AGPM 版本</span><span class="sxs-lookup"><span data-stu-id="05e4d-225">Choosing Which Version of AGPM to Install</span></span>](choosing-which-version-of-agpm-to-install.md)

 

 





