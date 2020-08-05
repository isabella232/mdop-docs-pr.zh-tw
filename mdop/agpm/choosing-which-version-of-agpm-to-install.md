---
title: 選擇要安裝的 AGPM 版本
description: 選擇要安裝的 AGPM 版本
author: dansimp
ms.assetid: 31357d2a-bc23-4e15-93f4-0beda8ab7a7b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 04/05/2017
ms.openlocfilehash: f8a69fb323d9f47c5b906ac3abc6ec59376ee6f7
ms.sourcegitcommit: 0a7dee11289780336d9c24ebbf27c5c1ffee441c
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 08/04/2020
ms.locfileid: "10905600"
---
# <span data-ttu-id="f5a93-103">選擇要安裝的 AGPM 版本</span><span class="sxs-lookup"><span data-stu-id="f5a93-103">Choosing Which Version of AGPM to Install</span></span>


<span data-ttu-id="f5a93-104">每個版本的 MicrosoftAdvanced 群組原則管理 (AGPM) 都支援特定版本的 Windows 作業系統。</span><span class="sxs-lookup"><span data-stu-id="f5a93-104">Each release of MicrosoftAdvanced Group Policy Management (AGPM) supports specific versions of the Windows operating system.</span></span> <span data-ttu-id="f5a93-105">我們強烈建議您在相同的作業系統行上執行 AGPM 用戶端和 AGPM 服務器。</span><span class="sxs-lookup"><span data-stu-id="f5a93-105">We strongly recommend that you run the AGPM Client and AGPM Server on the same line of operating systems.</span></span> <span data-ttu-id="f5a93-106">例如，windows 10 與 Windows Server 2016、Windows 8.1 （含 Windows Server2012 R2）等等。</span><span class="sxs-lookup"><span data-stu-id="f5a93-106">For example, Windows 10 with Windows Server 2016, Windows8.1 with Windows Server2012 R2, and so on.</span></span>

<span data-ttu-id="f5a93-107">我們建議您在網域中的最新版本的作業系統上安裝 AGPM 服務器。</span><span class="sxs-lookup"><span data-stu-id="f5a93-107">We recommend that you install the AGPM Server on the most recent version of the operating system in the domain.</span></span> <span data-ttu-id="f5a93-108">AGPM 使用群組原則管理主控台 (GPMC) 來備份及還原 (Gpo) 的群組原則物件。</span><span class="sxs-lookup"><span data-stu-id="f5a93-108">AGPM uses the Group Policy Management Console (GPMC) to back up and restore Group Policy Objects (GPOs).</span></span> <span data-ttu-id="f5a93-109">因為更新版本的 GPMC 提供其他不在舊版中提供的原則設定，您可以使用最新版本的作業系統來管理更多原則設定。</span><span class="sxs-lookup"><span data-stu-id="f5a93-109">Because newer versions of the GPMC provide additional policy settings that are not available in earlier versions, you can manage more policy settings by using the most recent version of the operating system.</span></span>

<span data-ttu-id="f5a93-110">所有版本的 AGPM 只能管理在運行 AGPM 的相同版本或舊版作業系統中所引進的原則設定。</span><span class="sxs-lookup"><span data-stu-id="f5a93-110">All versions of AGPM can manage only the policy settings that were introduced in the same version or an earlier version of the operating system on which AGPM is running.</span></span> <span data-ttu-id="f5a93-111">例如，如果您在 Windows Server 2012 上安裝了 AGPM 4.0 SP2，您可以管理在 Windows Server 2012 或較舊版本中推出的原則設定，但您無法管理稍後在 Windows 8.1 或 Windows Server2012 R2 中推出的原則設定。</span><span class="sxs-lookup"><span data-stu-id="f5a93-111">For example, if you install AGPM4.0 SP2 on Windows Server 2012, you can manage policy settings that were introduced in Windows Server 2012 or earlier, but you cannot manage policy settings that were introduced later, in Windows8.1 or Windows Server2012 R2.</span></span>

<span data-ttu-id="f5a93-112">如果您的 AGPM 服務器上的 GPMC 版本比管理員用來管理群組原則之電腦上的版本舊，則 AGPM 服務器將無法儲存不在舊版 GPMC 中的任何原則設定。</span><span class="sxs-lookup"><span data-stu-id="f5a93-112">If the version of the GPMC on your AGPM Server is older than the version on the computers that administrators use to manage Group Policy, the AGPM Server will be unable to store any policy settings that are not available in the older version of the GPMC.</span></span> <span data-ttu-id="f5a93-113">如需 Windows 中隨附的群組原則設定試算表，請參閱[適用於 Windows 和 Windows Server 的群組原則設定參考](https://go.microsoft.com/fwlink/p/?LinkId=613627)。</span><span class="sxs-lookup"><span data-stu-id="f5a93-113">For a spreadsheet of Group Policy settings included in Windows, see [Group Policy Settings Reference for Windows and Windows Server](https://go.microsoft.com/fwlink/p/?LinkId=613627).</span></span>

## <span data-ttu-id="f5a93-114">AGPM 4.0 SP3</span><span class="sxs-lookup"><span data-stu-id="f5a93-114">AGPM4.0 SP3</span></span>


<span data-ttu-id="f5a93-115">如果您使用執行 Windows 10 的電腦來管理 Gpo，您必須使用 AGPM 4.0 SP3。</span><span class="sxs-lookup"><span data-stu-id="f5a93-115">If you are using computers that are running Windows 10 to manage GPOs, you must use AGPM 4.0 SP3.</span></span> <span data-ttu-id="f5a93-116">您無法在執行 Windows 10 作業系統的電腦上安裝舊版的 AGPM。</span><span class="sxs-lookup"><span data-stu-id="f5a93-116">You cannot install earlier versions of AGPM on computers that are running the Windows 10 operating system.</span></span>

<span data-ttu-id="f5a93-117">表格1列出您可以安裝 AGPM 4.0 SP3 的作業系統，以及您可以使用 AGPM 4.0 SP3 管理的原則設定。</span><span class="sxs-lookup"><span data-stu-id="f5a93-117">Table 1 lists the operating systems on which you can install AGPM4.0 SP3, and the policy settings that you can manage by using AGPM4.0 SP3.</span></span>

**<span data-ttu-id="f5a93-118">表格1： AGPM 4.0 SP3 支援的作業系統與原則設定</span><span class="sxs-lookup"><span data-stu-id="f5a93-118">Table 1: AGPM 4.0 SP3 supported operating systems and policy settings</span></span>**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="f5a93-119">AGPM 服務器支援的設定</span><span class="sxs-lookup"><span data-stu-id="f5a93-119">Supported configurations for the AGPM Server</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="f5a93-120">適用于 AGPM 用戶端的支援設定</span><span class="sxs-lookup"><span data-stu-id="f5a93-120">Supported configurations for the AGPM Client</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="f5a93-121">AGPM 支援</span><span class="sxs-lookup"><span data-stu-id="f5a93-121">AGPM Support</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f5a93-122">Windows Server 2019 或 Windows 10</span><span class="sxs-lookup"><span data-stu-id="f5a93-122">Windows Server 2019 or Windows 10</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-123">Windows Server 2019 或 Windows 10</span><span class="sxs-lookup"><span data-stu-id="f5a93-123">Windows Server 2019 or Windows 10</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-124">支援</span><span class="sxs-lookup"><span data-stu-id="f5a93-124">Supported</span></span></p></td>
</tr>
 <tr class="even">
<td align="left"><p><span data-ttu-id="f5a93-125">Windows Server 2019 或 Windows 10</span><span class="sxs-lookup"><span data-stu-id="f5a93-125">Windows Server 2019 or Windows 10</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-126">Windows Server 2019 或 Windows 10</span><span class="sxs-lookup"><span data-stu-id="f5a93-126">Windows Server 2019 or Windows 10</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-127">支援</span><span class="sxs-lookup"><span data-stu-id="f5a93-127">Supported</span></span></p></td>
</tr>
<tr class="edd">
<td align="left"><p><span data-ttu-id="f5a93-128">Windows Server2012 R2</span><span class="sxs-lookup"><span data-stu-id="f5a93-128">Windows Server2012 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-129">Windows 10</span><span class="sxs-lookup"><span data-stu-id="f5a93-129">Windows 10</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-130">支援 KB 4015786 中所述的注意事項 <a href="https://support.microsoft.com/help/4015786/known-issues-managing-a-windows-10-group-policy-client-in-windows-serv" data-raw-source="[KB 4015786](https://support.microsoft.com/help/4015786/known-issues-managing-a-windows-10-group-policy-client-in-windows-serv)"></span><span class="sxs-lookup"><span data-stu-id="f5a93-130">Supported with the caveats outlined in <a href="https://support.microsoft.com/help/4015786/known-issues-managing-a-windows-10-group-policy-client-in-windows-serv" data-raw-source="[KB 4015786](https://support.microsoft.com/help/4015786/known-issues-managing-a-windows-10-group-policy-client-in-windows-serv)">KB 4015786</span></span></a>
</p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f5a93-131">Windows Server2012 R2 或 Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="f5a93-131">Windows Server2012 R2 or Windows8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-132">Windows Server2012 R2 或 Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="f5a93-132">Windows Server2012 R2 or Windows8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-133">支援</span><span class="sxs-lookup"><span data-stu-id="f5a93-133">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f5a93-134">Windows Server2012 R2、Windows Server 2012 或 Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="f5a93-134">Windows Server2012 R2, Windows Server 2012, or Windows8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-135">Windows Server 2012 或 Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="f5a93-135">Windows Server 2012 or Windows 8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-136">支援，但無法編輯僅存在於 Windows 8.1 中的原則設定或喜好設定專案</span><span class="sxs-lookup"><span data-stu-id="f5a93-136">Supported, but cannot edit policy settings or preference items that exist only in Windows8.1</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f5a93-137">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="f5a93-137">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-138">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="f5a93-138">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-139">支援，但無法編輯僅存在於 Windows 8.1 中的原則設定或喜好設定專案</span><span class="sxs-lookup"><span data-stu-id="f5a93-139">Supported, but cannot edit policy settings or preference items that exist only in Windows8.1</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f5a93-140">Windows Server 2012、Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="f5a93-140">Windows Server 2012, Windows Server2008R2, or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-141">Windows Server2008 或 WindowsVista Service Pack 1 (SP1) </span><span class="sxs-lookup"><span data-stu-id="f5a93-141">Windows Server2008 or WindowsVista with Service Pack 1 (SP1)</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-142">支援，但無法編輯僅存在於 Windows Server2012 R2、windows Server 2012、Windows Server2008R2、Windows 8.1 或 Windows7 中的原則設定或喜好設定專案</span><span class="sxs-lookup"><span data-stu-id="f5a93-142">Supported, but cannot edit policy settings or preference items that exist only in Windows Server2012 R2, Windows Server 2012, Windows Server2008R2, Windows8.1, or Windows7</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f5a93-143">Windows Server2008 或 Windows Vista （含 SP1）</span><span class="sxs-lookup"><span data-stu-id="f5a93-143">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-144">Windows Server 2012、Windows Server2008R2、Windows 8 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="f5a93-144">Windows Server 2012, Windows Server2008R2, Windows 8, or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-145">不支援</span><span class="sxs-lookup"><span data-stu-id="f5a93-145">Not supported</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f5a93-146">Windows Server2008 或 Windows Vista （含 SP1）</span><span class="sxs-lookup"><span data-stu-id="f5a93-146">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-147">Windows Server2008 或 Windows Vista （含 SP1）</span><span class="sxs-lookup"><span data-stu-id="f5a93-147">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-148">支援，但無法報告或編輯僅存在於 Windows Server2012 R2、windows Server 2012、Windows Server2008R2、Windows 8.1 或 Windows7 中的原則設定或喜好設定專案</span><span class="sxs-lookup"><span data-stu-id="f5a93-148">Supported, but cannot report or edit policy settings or preference items that exist only in Windows Server2012 R2, Windows Server 2012, Windows Server2008R2, Windows8.1, or Windows7</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="f5a93-149">AGPM 4.0 SP2</span><span class="sxs-lookup"><span data-stu-id="f5a93-149">AGPM4.0 SP2</span></span>


<span data-ttu-id="f5a93-150">如果您使用的電腦執行的是 Windows Server2012 R2 或 Windows 8.1 來管理 Gpo，您必須使用 AGPM 4.0 SP2。</span><span class="sxs-lookup"><span data-stu-id="f5a93-150">If you are using computers that are running Windows Server2012 R2 or Windows8.1 to manage GPOs, you must use AGPM4.0 SP2.</span></span> <span data-ttu-id="f5a93-151">您無法在執行這些作業系統的電腦上安裝舊版的 AGPM。</span><span class="sxs-lookup"><span data-stu-id="f5a93-151">You cannot install earlier versions of AGPM on computers that are running those operating systems.</span></span>

<span data-ttu-id="f5a93-152">表格1列出您可以安裝 AGPM 4.0 SP2 的作業系統，以及您可以使用 AGPM 4.0 SP2 管理的原則設定。</span><span class="sxs-lookup"><span data-stu-id="f5a93-152">Table 1 lists the operating systems on which you can install AGPM4.0 SP2, and the policy settings that you can manage by using AGPM4.0 SP2.</span></span>

**<span data-ttu-id="f5a93-153">表格2： AGPM 4.0 SP2 支援的作業系統與原則設定</span><span class="sxs-lookup"><span data-stu-id="f5a93-153">Table 2: AGPM4.0 SP2 supported operating systems and policy settings</span></span>**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="f5a93-154">AGPM 服務器支援的設定</span><span class="sxs-lookup"><span data-stu-id="f5a93-154">Supported configurations for the AGPM Server</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="f5a93-155">適用于 AGPM 用戶端的支援設定</span><span class="sxs-lookup"><span data-stu-id="f5a93-155">Supported configurations for the AGPM Client</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="f5a93-156">AGPM 支援</span><span class="sxs-lookup"><span data-stu-id="f5a93-156">AGPM Support</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f5a93-157">Windows Server2012 R2 或 Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="f5a93-157">Windows Server2012 R2 or Windows8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-158">Windows Server2012 R2 或 Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="f5a93-158">Windows Server2012 R2 or Windows8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-159">支援</span><span class="sxs-lookup"><span data-stu-id="f5a93-159">Supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f5a93-160">Windows Server2012 R2、Windows Server 2012 或 Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="f5a93-160">Windows Server2012 R2, Windows Server 2012, or Windows8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-161">Windows Server 2012 或 Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="f5a93-161">Windows Server 2012 or Windows 8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-162">支援，但無法編輯僅存在於 Windows 8.1 中的原則設定或喜好設定專案</span><span class="sxs-lookup"><span data-stu-id="f5a93-162">Supported, but cannot edit policy settings or preference items that exist only in Windows8.1</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f5a93-163">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="f5a93-163">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-164">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="f5a93-164">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-165">支援，但無法編輯僅存在於 Windows 8.1 中的原則設定或喜好設定專案</span><span class="sxs-lookup"><span data-stu-id="f5a93-165">Supported, but cannot edit policy settings or preference items that exist only in Windows8.1</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f5a93-166">Windows Server 2012、Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="f5a93-166">Windows Server 2012, Windows Server2008R2, or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-167">Windows Server2008 或 WindowsVista Service Pack 1 (SP1) </span><span class="sxs-lookup"><span data-stu-id="f5a93-167">Windows Server2008 or WindowsVista with Service Pack 1 (SP1)</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-168">支援，但無法編輯僅存在於 Windows Server2012 R2、windows Server 2012、Windows Server2008R2、Windows 8.1 或 Windows7 中的原則設定或喜好設定專案</span><span class="sxs-lookup"><span data-stu-id="f5a93-168">Supported, but cannot edit policy settings or preference items that exist only in Windows Server2012 R2, Windows Server 2012, Windows Server2008R2, Windows8.1, or Windows7</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f5a93-169">Windows Server2008 或 Windows Vista （含 SP1）</span><span class="sxs-lookup"><span data-stu-id="f5a93-169">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-170">Windows Server 2012、Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="f5a93-170">Windows Server 2012, Windows Server2008R2, or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-171">不支援</span><span class="sxs-lookup"><span data-stu-id="f5a93-171">Not supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f5a93-172">Windows Server2008 或 Windows Vista （含 SP1）</span><span class="sxs-lookup"><span data-stu-id="f5a93-172">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-173">Windows Server2008 或 Windows Vista （含 SP1）</span><span class="sxs-lookup"><span data-stu-id="f5a93-173">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-174">支援，但無法報告或編輯僅存在於 Windows Server2012 R2、windows Server 2012、Windows Server2008R2、Windows 8.1 或 Windows7 中的原則設定或喜好設定專案</span><span class="sxs-lookup"><span data-stu-id="f5a93-174">Supported, but cannot report or edit policy settings or preference items that exist only in Windows Server2012 R2, Windows Server 2012, Windows Server2008R2, Windows8.1, or Windows7</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="f5a93-175">AGPM 4.0 SP1</span><span class="sxs-lookup"><span data-stu-id="f5a93-175">AGPM4.0 SP1</span></span>


<span data-ttu-id="f5a93-176">表格2列出您可以安裝 AGPM 4.0 SP1 的作業系統，以及可使用 AGPM 4.0 SP1 管理的原則設定。</span><span class="sxs-lookup"><span data-stu-id="f5a93-176">Table 2 lists the operating systems on which you can install AGPM 4.0 SP1, and the policy settings that you can manage by using AGPM4.0 SP1.</span></span>

**<span data-ttu-id="f5a93-177">表格3： AGPM 4.0 SP1 支援的作業系統與原則設定</span><span class="sxs-lookup"><span data-stu-id="f5a93-177">Table 3: AGPM4.0 SP1 supported operating systems and policy settings</span></span>**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="f5a93-178">AGPM 服務器支援的設定</span><span class="sxs-lookup"><span data-stu-id="f5a93-178">Supported configurations for the AGPM Server</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="f5a93-179">適用于 AGPM 用戶端的支援設定</span><span class="sxs-lookup"><span data-stu-id="f5a93-179">Supported configurations for the AGPM Client</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="f5a93-180">AGPM 支援</span><span class="sxs-lookup"><span data-stu-id="f5a93-180">AGPM Support</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f5a93-181">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="f5a93-181">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-182">Windows Server 2012</span><span class="sxs-lookup"><span data-stu-id="f5a93-182">Windows Server 2012</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-183">支援</span><span class="sxs-lookup"><span data-stu-id="f5a93-183">Supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f5a93-184">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="f5a93-184">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-185">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="f5a93-185">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-186">支援，但無法編輯僅存在於 Windows 8.1 的原則設定或喜好設定專案</span><span class="sxs-lookup"><span data-stu-id="f5a93-186">Supported, but cannot edit policy settings or preference items that exist only in Windows 8.1</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f5a93-187">Windows Server 2012、Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="f5a93-187">Windows Server 2012, Windows Server2008R2, or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-188">Windows Server2008 或 Windows Vista （含 SP1）</span><span class="sxs-lookup"><span data-stu-id="f5a93-188">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-189">支援，但無法編輯只有在 Windows Server2008R2 或 Windows7 中存在的原則設定或喜好設定專案</span><span class="sxs-lookup"><span data-stu-id="f5a93-189">Supported, but cannot edit policy settings or preference items that exist only in Windows Server2008R2, or Windows7</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f5a93-190">Windows Server2008 或 Windows Vista （含 SP1）</span><span class="sxs-lookup"><span data-stu-id="f5a93-190">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-191">Windows Server 2012、Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="f5a93-191">Windows Server 2012, Windows Server2008R2, or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-192">支援</span><span class="sxs-lookup"><span data-stu-id="f5a93-192">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f5a93-193">Windows Server2008 或 Windows Vista （含 SP1）</span><span class="sxs-lookup"><span data-stu-id="f5a93-193">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-194">Windows Server2008 或 Windows Vista （含 SP1）</span><span class="sxs-lookup"><span data-stu-id="f5a93-194">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-195">支援，但無法報告或編輯僅存在於 Windows Server2008R2 或 Windows7 的原則設定或喜好設定專案</span><span class="sxs-lookup"><span data-stu-id="f5a93-195">Supported, but cannot report or edit policy settings or preference items that exist only in Windows Server2008R2, or Windows7</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="f5a93-196">AGPM 4。0</span><span class="sxs-lookup"><span data-stu-id="f5a93-196">AGPM4.0</span></span>


<span data-ttu-id="f5a93-197">表格3列出您可以安裝 AGPM 4.0 的作業系統，以及可使用 AGPM 4.0 管理的原則設定。</span><span class="sxs-lookup"><span data-stu-id="f5a93-197">Table 3 lists the operating systems on which you can install AGPM 4.0, and the policy settings that you can manage by using AGPM4.0.</span></span>

**<span data-ttu-id="f5a93-198">資料表4： AGPM 4.0 支援的作業系統與原則設定</span><span class="sxs-lookup"><span data-stu-id="f5a93-198">Table 4: AGPM4.0 supported operating systems and policy settings</span></span>**

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f5a93-199">AGPM 服務器支援的作業系統</span><span class="sxs-lookup"><span data-stu-id="f5a93-199">Supported operating systems for the AGPM Server</span></span></th>
<th align="left"><span data-ttu-id="f5a93-200">適用于 AGPM 用戶端的支援作業系統</span><span class="sxs-lookup"><span data-stu-id="f5a93-200">Supported operating systems for the AGPM Client</span></span></th>
<th align="left"><span data-ttu-id="f5a93-201">AGPM 支援</span><span class="sxs-lookup"><span data-stu-id="f5a93-201">AGPM Support</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f5a93-202">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="f5a93-202">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-203">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="f5a93-203">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-204">支援</span><span class="sxs-lookup"><span data-stu-id="f5a93-204">Supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f5a93-205">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="f5a93-205">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-206">Windows Server2008 或 Windows Vista （含 SP1）</span><span class="sxs-lookup"><span data-stu-id="f5a93-206">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-207">支援，但無法編輯僅存在於 Windows Server2008R2 或 Windows7 的原則設定或喜好設定專案</span><span class="sxs-lookup"><span data-stu-id="f5a93-207">Supported, but cannot edit policy settings or preference items that exist only in Windows Server2008R2 or Windows7</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f5a93-208">Windows Server2008 或 Windows Vista （含 SP1）</span><span class="sxs-lookup"><span data-stu-id="f5a93-208">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-209">Windows Server2008R2 或 Windows7</span><span class="sxs-lookup"><span data-stu-id="f5a93-209">Windows Server2008R2 or Windows7</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-210">不支援</span><span class="sxs-lookup"><span data-stu-id="f5a93-210">Not supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f5a93-211">Windows Server2008 或 Windows Vista （含 SP1）</span><span class="sxs-lookup"><span data-stu-id="f5a93-211">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-212">Windows Server2008 或 Windows Vista （含 SP1）</span><span class="sxs-lookup"><span data-stu-id="f5a93-212">Windows Server2008 or Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-213">支援，但無法報告或編輯僅存在於 Windows Server2008R2 或 Windows7 的原則設定或喜好設定專案</span><span class="sxs-lookup"><span data-stu-id="f5a93-213">Supported, but cannot report or edit policy settings or preference items that exist only in Windows Server2008R2 or Windows7</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="f5a93-214">在 AGPM 4.0 之前的 AGPM 版本</span><span class="sxs-lookup"><span data-stu-id="f5a93-214">Versions of AGPM that precede AGPM4.0</span></span>


<span data-ttu-id="f5a93-215">資料表4列出您可以在其中安裝 agpm 4.0 之前的 AGPM 版本的作業系統。</span><span class="sxs-lookup"><span data-stu-id="f5a93-215">Table 4 lists the operating systems on which you can install the versions of AGPM that precede AGPM4.0.</span></span> <span data-ttu-id="f5a93-216">如果沒有列出作業系統，您就無法在該作業系統上安裝 AGPM。</span><span class="sxs-lookup"><span data-stu-id="f5a93-216">If an operating system is not listed, you cannot install AGPM on that operating system.</span></span>

**<span data-ttu-id="f5a93-217">表5：在 AGPM 4.0 之前的 AGPM 版本支援的作業系統</span><span class="sxs-lookup"><span data-stu-id="f5a93-217">Table 5: Supported operating systems for versions of AGPM that precede AGPM4.0</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f5a93-218">作業系統</span><span class="sxs-lookup"><span data-stu-id="f5a93-218">Operating system</span></span></th>
<th align="left"><span data-ttu-id="f5a93-219">可安裝的 AGPM 版本</span><span class="sxs-lookup"><span data-stu-id="f5a93-219">Version of AGPM that can be installed</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f5a93-220">Windows Server2008</span><span class="sxs-lookup"><span data-stu-id="f5a93-220">Windows Server2008</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-221">3.0</span><span class="sxs-lookup"><span data-stu-id="f5a93-221">3.0</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f5a93-222">Windows Vista （含 SP1）</span><span class="sxs-lookup"><span data-stu-id="f5a93-222">Windows Vista with SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-223">3.0</span><span class="sxs-lookup"><span data-stu-id="f5a93-223">3.0</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f5a93-224">WindowsVista 沒有安裝 service pack (32 位) </span><span class="sxs-lookup"><span data-stu-id="f5a93-224">WindowsVista with no service pack installed (32-bit)</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-225">2.5</span><span class="sxs-lookup"><span data-stu-id="f5a93-225">2.5</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f5a93-226">Windows Server2003 (32 位) </span><span class="sxs-lookup"><span data-stu-id="f5a93-226">Windows Server2003 (32-bit)</span></span></p></td>
<td align="left"><p><span data-ttu-id="f5a93-227">2.5</span><span class="sxs-lookup"><span data-stu-id="f5a93-227">2.5</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="f5a93-228">如何取得 MDOP 技術</span><span class="sxs-lookup"><span data-stu-id="f5a93-228">How to Get MDOP Technologies</span></span>


<span data-ttu-id="f5a93-229">AGPM 4.0 SP2 是 Microsoft 桌面優化套件 (MDOP) 的一部分。</span><span class="sxs-lookup"><span data-stu-id="f5a93-229">AGPM 4.0 SP2 is a part of the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="f5a93-230">MDOP 是 Microsoft 軟體保證的一部分。</span><span class="sxs-lookup"><span data-stu-id="f5a93-230">MDOP is part of Microsoft Software Assurance.</span></span> <span data-ttu-id="f5a93-231">如需 Microsoft 軟體保證及取得 MDOP 的詳細資訊，請參閱[如何取得 mdop](https://go.microsoft.com/fwlink/?LinkId=322049) (https://go.microsoft.com/fwlink/?LinkId=322049) 。</span><span class="sxs-lookup"><span data-stu-id="f5a93-231">For more information about Microsoft Software Assurance and acquiring MDOP, see [How Do I Get MDOP](https://go.microsoft.com/fwlink/?LinkId=322049) (https://go.microsoft.com/fwlink/?LinkId=322049).</span></span>

## <span data-ttu-id="f5a93-232">相關主題</span><span class="sxs-lookup"><span data-stu-id="f5a93-232">Related topics</span></span>


[<span data-ttu-id="f5a93-233">進階群組原則管理</span><span class="sxs-lookup"><span data-stu-id="f5a93-233">Advanced Group Policy Management</span></span>](index.md)

 

 





