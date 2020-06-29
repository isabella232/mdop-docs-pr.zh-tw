---
title: 使用 App-V 部署 Microsoft Office 2010
description: 使用 App-V 部署 Microsoft Office 2010
author: dansimp
ms.assetid: 0a9e496e-82a1-4dc0-a496-7b21eaa00f53
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 303a44d921e40a411a4c4ea4622f06a76b8ed9c6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800643"
---
# <span data-ttu-id="4f2c3-103">使用 App-V 部署 Microsoft Office 2010</span><span class="sxs-lookup"><span data-stu-id="4f2c3-103">Deploying Microsoft Office 2010 by Using App-V</span></span>


<span data-ttu-id="4f2c3-104">您可以使用下列其中一種方法，為應用程式虛擬化5.0 建立 Office 2010 套件：</span><span class="sxs-lookup"><span data-stu-id="4f2c3-104">You can create Office 2010 packages for Application Virtualization 5.0 using one of the following methods:</span></span>

-   <span data-ttu-id="4f2c3-105">應用程式虛擬化（App-v） Sequencer</span><span class="sxs-lookup"><span data-stu-id="4f2c3-105">Application Virtualization (App-V) Sequencer</span></span>

-   <span data-ttu-id="4f2c3-106">應用程式虛擬化（App-v）套件加速器</span><span class="sxs-lookup"><span data-stu-id="4f2c3-106">Application Virtualization (App-V) Package Accelerator</span></span>

## <span data-ttu-id="4f2c3-107">Office 2010 的 app-v 支援</span><span class="sxs-lookup"><span data-stu-id="4f2c3-107">App-V support for Office 2010</span></span>


<span data-ttu-id="4f2c3-108">下表顯示 App-V 版本、Office 套件建立的方法、支援的授權，以及 Office 2010 支援的部署。</span><span class="sxs-lookup"><span data-stu-id="4f2c3-108">The following table shows the App-V versions, methods of Office package creation, supported licensing, and supported deployments for Office 2010.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4f2c3-109">支援的專案</span><span class="sxs-lookup"><span data-stu-id="4f2c3-109">Supported item</span></span></th>
<th align="left"><span data-ttu-id="4f2c3-110">支援層級</span><span class="sxs-lookup"><span data-stu-id="4f2c3-110">Level of support</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4f2c3-111">支援的 App-v 版本</span><span class="sxs-lookup"><span data-stu-id="4f2c3-111">Supported App-V versions</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="4f2c3-112">4.6</span><span class="sxs-lookup"><span data-stu-id="4f2c3-112">4.6</span></span></p></li>
<li><p><span data-ttu-id="4f2c3-113">5.0</span><span class="sxs-lookup"><span data-stu-id="4f2c3-113">5.0</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4f2c3-114">建立套件</span><span class="sxs-lookup"><span data-stu-id="4f2c3-114">Package creation</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="4f2c3-115">序列</span><span class="sxs-lookup"><span data-stu-id="4f2c3-115">Sequencing</span></span></p></li>
<li><p><span data-ttu-id="4f2c3-116">套件加速器</span><span class="sxs-lookup"><span data-stu-id="4f2c3-116">Package Accelerator</span></span></p></li>
<li><p><span data-ttu-id="4f2c3-117">Office 部署套件</span><span class="sxs-lookup"><span data-stu-id="4f2c3-117">Office Deployment Kit</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4f2c3-118">支援的授權</span><span class="sxs-lookup"><span data-stu-id="4f2c3-118">Supported licensing</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f2c3-119">大量授權</span><span class="sxs-lookup"><span data-stu-id="4f2c3-119">Volume Licensing</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4f2c3-120">支援的部署</span><span class="sxs-lookup"><span data-stu-id="4f2c3-120">Supported deployments</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="4f2c3-121">桌面</span><span class="sxs-lookup"><span data-stu-id="4f2c3-121">Desktop</span></span></p></li>
<li><p><span data-ttu-id="4f2c3-122">個人 VDI</span><span class="sxs-lookup"><span data-stu-id="4f2c3-122">Personal VDI</span></span></p></li>
<li><p><span data-ttu-id="4f2c3-123">句</span><span class="sxs-lookup"><span data-stu-id="4f2c3-123">RDS</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="4f2c3-124">使用排序器建立 Office 2010 App-V 5。0</span><span class="sxs-lookup"><span data-stu-id="4f2c3-124">Creating Office 2010 App-V 5.0 using the sequencer</span></span>


<span data-ttu-id="4f2c3-125">排序 Office 2010 是在應用程式 V 5.0 上建立 Office 2010 套件的主要方法之一。</span><span class="sxs-lookup"><span data-stu-id="4f2c3-125">Sequencing Office 2010 is one of the main methods for creating an Office 2010 package on App-V 5.0.</span></span> <span data-ttu-id="4f2c3-126">Microsoft 已透過知識庫文章提供詳細的食譜。</span><span class="sxs-lookup"><span data-stu-id="4f2c3-126">Microsoft has provided a detailed recipe through a Knowledge Base article.</span></span> <span data-ttu-id="4f2c3-127">若要在 App-V 5.0 上建立 Office 2010 套件，請參閱下列連結，以取得詳細指示：</span><span class="sxs-lookup"><span data-stu-id="4f2c3-127">To create an Office 2010 package on App-V 5.0, refer to the following link for detailed instructions:</span></span>

[<span data-ttu-id="4f2c3-128">如何在 Microsoft Application Virtualization 5.0 中排序 Microsoft Office 2010</span><span class="sxs-lookup"><span data-stu-id="4f2c3-128">How To Sequence Microsoft Office 2010 in Microsoft Application Virtualization 5.0</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330676)

## <span data-ttu-id="4f2c3-129">使用套件加速器建立 Office 2010 App-V 5.0 套件</span><span class="sxs-lookup"><span data-stu-id="4f2c3-129">Creating Office 2010 App-V 5.0 packages using package accelerators</span></span>


<span data-ttu-id="4f2c3-130">您可以透過套件加速器建立 Office 2010 App-V 5.0 套件。</span><span class="sxs-lookup"><span data-stu-id="4f2c3-130">Office 2010 App-V 5.0 packages can be created through package accelerators.</span></span> <span data-ttu-id="4f2c3-131">Microsoft 已提供在 Windows 8 和 Windows 7 上建立 Office 2010 的封裝加速器。</span><span class="sxs-lookup"><span data-stu-id="4f2c3-131">Microsoft has provided package accelerators for creating Office 2010 on Windows 8 and Windows 7.</span></span> <span data-ttu-id="4f2c3-132">若要使用套件加速器在 App-v 上建立 Office 2010 套件，請參閱下列頁面，以存取適當的套件加速器：</span><span class="sxs-lookup"><span data-stu-id="4f2c3-132">To create Office 2010 packages on App-V using Package accelerators, refer to the following pages to access the appropriate package accelerator:</span></span>

-   [<span data-ttu-id="4f2c3-133">適用于 Office 專業增強版2010– Windows 8 的 app-v 5.0 套件加速器</span><span class="sxs-lookup"><span data-stu-id="4f2c3-133">App-V 5.0 Package Accelerator for Office Professional Plus 2010 – Windows 8</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330677)

-   [<span data-ttu-id="4f2c3-134">適用于 Office 專業增強版2010的 app-v 5.0 套件加速器-Windows 7</span><span class="sxs-lookup"><span data-stu-id="4f2c3-134">App-V 5.0 Package Accelerator for Office Professional Plus 2010 – Windows 7</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330678)

<span data-ttu-id="4f2c3-135">如需如何使用 App-v 套件加速器建立虛擬應用程式套件的詳細指示，請參閱[如何使用 App-v 套件加速器建立虛擬應用程式套件](how-to-create-a-virtual-application-package-using-an-app-v-package-accelerator.md)。</span><span class="sxs-lookup"><span data-stu-id="4f2c3-135">For detailed instructions on how to create virtual application packages using App-V package accelerators, see [How to Create a Virtual Application Package Using an App-V Package Accelerator](how-to-create-a-virtual-application-package-using-an-app-v-package-accelerator.md).</span></span>

## <span data-ttu-id="4f2c3-136">部署應用程式的 Microsoft Office 套件-V 5。0</span><span class="sxs-lookup"><span data-stu-id="4f2c3-136">Deploying the Microsoft Office package for App-V 5.0</span></span>


<span data-ttu-id="4f2c3-137">您可以使用下列任何一種 App V 部署方法，部署 Office 2010 套件：</span><span class="sxs-lookup"><span data-stu-id="4f2c3-137">You can deploy Office 2010 packages by using any of the following App-V deployment methods:</span></span>

-   <span data-ttu-id="4f2c3-138">System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="4f2c3-138">System Center Configuration Manager</span></span>

-   <span data-ttu-id="4f2c3-139">App-v server</span><span class="sxs-lookup"><span data-stu-id="4f2c3-139">App-V server</span></span>

-   <span data-ttu-id="4f2c3-140">從 PowerShell 命令中獨立</span><span class="sxs-lookup"><span data-stu-id="4f2c3-140">Stand-alone through PowerShell commands</span></span>

## <span data-ttu-id="4f2c3-141">Office App-v 套件管理與自訂</span><span class="sxs-lookup"><span data-stu-id="4f2c3-141">Office App-V package management and customization</span></span>


<span data-ttu-id="4f2c3-142">您可以透過已知的套件管理機制，管理 Office 2010 套件，就像任何其他 App-V 5.0 套件一樣。</span><span class="sxs-lookup"><span data-stu-id="4f2c3-142">Office 2010 packages can be managed like any other App-V 5.0 packages through known package management mechanisms.</span></span> <span data-ttu-id="4f2c3-143">不需要任何特殊指示，例如新增、發佈、取消發佈或移除 Office 套件。</span><span class="sxs-lookup"><span data-stu-id="4f2c3-143">No special instructions are needed, for example, to add, publish, unpublish, or remove Office packages.</span></span>

## <span data-ttu-id="4f2c3-144">Microsoft Office 與 Windows 整合</span><span class="sxs-lookup"><span data-stu-id="4f2c3-144">Microsoft Office integration with Windows</span></span>


<span data-ttu-id="4f2c3-145">下表提供 Office 2010 支援整合點的完整清單。</span><span class="sxs-lookup"><span data-stu-id="4f2c3-145">The following table provides a full list of supported integration points for Office 2010.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4f2c3-146">延伸點</span><span class="sxs-lookup"><span data-stu-id="4f2c3-146">Extension Point</span></span></th>
<th align="left"><span data-ttu-id="4f2c3-147">描述</span><span class="sxs-lookup"><span data-stu-id="4f2c3-147">Description</span></span></th>
<th align="left"><span data-ttu-id="4f2c3-148">Office 2010</span><span class="sxs-lookup"><span data-stu-id="4f2c3-148">Office 2010</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4f2c3-149">適用于 Firefox 和 Chrome 的 Lync 會議加入外掛程式</span><span class="sxs-lookup"><span data-stu-id="4f2c3-149">Lync meeting Join Plug-in for Firefox and Chrome</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f2c3-150">使用者可以從 Firefox 和 Chrome 加入 Lync 會議</span><span class="sxs-lookup"><span data-stu-id="4f2c3-150">User can join Lync meetings from Firefox and Chrome</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4f2c3-151">已傳送至 OneNote 列印驅動程式</span><span class="sxs-lookup"><span data-stu-id="4f2c3-151">Sent to OneNote Print Driver</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f2c3-152">使用者可以列印至 OneNote</span><span class="sxs-lookup"><span data-stu-id="4f2c3-152">User can print to OneNote</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f2c3-153">是</span><span class="sxs-lookup"><span data-stu-id="4f2c3-153">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4f2c3-154">OneNote 連結筆記</span><span class="sxs-lookup"><span data-stu-id="4f2c3-154">OneNote Linked Notes</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f2c3-155">OneNote 連結筆記</span><span class="sxs-lookup"><span data-stu-id="4f2c3-155">OneNote Linked Notes</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4f2c3-156">傳送至 OneNote Internet Explorer 增益集</span><span class="sxs-lookup"><span data-stu-id="4f2c3-156">Send to OneNote Internet Explorer Add-In</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f2c3-157">使用者可以從 IE 傳送至 OneNote</span><span class="sxs-lookup"><span data-stu-id="4f2c3-157">User can send to OneNote from IE</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4f2c3-158">Lync 和 Outlook 的防火牆例外狀況</span><span class="sxs-lookup"><span data-stu-id="4f2c3-158">Firewall Exception for Lync and Outlook</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f2c3-159">Lync 和 Outlook 的防火牆例外狀況</span><span class="sxs-lookup"><span data-stu-id="4f2c3-159">Firewall Exception for Lync and Outlook</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4f2c3-160">MAPI 用戶端</span><span class="sxs-lookup"><span data-stu-id="4f2c3-160">MAPI Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f2c3-161">原生應用程式和增益集可透過 MAPI 與虛擬 Outlook 互動</span><span class="sxs-lookup"><span data-stu-id="4f2c3-161">Native apps and add-ins can interact with virtual Outlook through MAPI</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4f2c3-162">Firefox 適用的 SharePoint 外掛程式</span><span class="sxs-lookup"><span data-stu-id="4f2c3-162">SharePoint Plugin for Firefox</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f2c3-163">使用者可以在 Firefox 中使用 SharePoint 功能</span><span class="sxs-lookup"><span data-stu-id="4f2c3-163">User can use SharePoint features in Firefox</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4f2c3-164">[郵件] 控制台小程式</span><span class="sxs-lookup"><span data-stu-id="4f2c3-164">Mail Control Panel Applet</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f2c3-165">使用者在 Outlook 中取得 [郵件] 控制台小程式</span><span class="sxs-lookup"><span data-stu-id="4f2c3-165">User gets the mail control panel applet in Outlook</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f2c3-166">是</span><span class="sxs-lookup"><span data-stu-id="4f2c3-166">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4f2c3-167">主要 Interop 元件</span><span class="sxs-lookup"><span data-stu-id="4f2c3-167">Primary Interop Assemblies</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f2c3-168">支援受管理的增益集</span><span class="sxs-lookup"><span data-stu-id="4f2c3-168">Support managed add-ins</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4f2c3-169">Office 檔快取處理常式</span><span class="sxs-lookup"><span data-stu-id="4f2c3-169">Office Document Cache Handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f2c3-170">允許 Office 應用程式的檔快取</span><span class="sxs-lookup"><span data-stu-id="4f2c3-170">Allows Document Cache for Office applications</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4f2c3-171">Outlook 通訊協定搜尋處理常式</span><span class="sxs-lookup"><span data-stu-id="4f2c3-171">Outlook Protocol Search handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f2c3-172">使用者可以在 outlook 中搜尋</span><span class="sxs-lookup"><span data-stu-id="4f2c3-172">User can search in outlook</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f2c3-173">是</span><span class="sxs-lookup"><span data-stu-id="4f2c3-173">Yes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="4f2c3-174">Active X 控制項：</span><span class="sxs-lookup"><span data-stu-id="4f2c3-174">Active X Controls:</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f2c3-175">如需有關 ActiveX 控制項的詳細資訊，請參閱 <a href="https://go.microsoft.com/fwlink/p/?LinkId=331361" data-raw-source="[ActiveX Control API Reference](https://go.microsoft.com/fwlink/p/?LinkId=331361)"> Activex 控制項 API 參考 </a> 。</span><span class="sxs-lookup"><span data-stu-id="4f2c3-175">For more information on ActiveX controls, refer to <a href="https://go.microsoft.com/fwlink/p/?LinkId=331361" data-raw-source="[ActiveX Control API Reference](https://go.microsoft.com/fwlink/p/?LinkId=331361)">ActiveX Control API Reference</a>.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="4f2c3-176">Groove. SiteClient</span><span class="sxs-lookup"><span data-stu-id="4f2c3-176">Groove.SiteClient</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f2c3-177">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="4f2c3-177">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="4f2c3-178">PortalConnect.PersonalSite</span><span class="sxs-lookup"><span data-stu-id="4f2c3-178">PortalConnect.PersonalSite</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f2c3-179">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="4f2c3-179">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="4f2c3-180">OpenDocuments</span><span class="sxs-lookup"><span data-stu-id="4f2c3-180">SharePoint.openDocuments</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f2c3-181">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="4f2c3-181">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="4f2c3-182">ExportDatabase</span><span class="sxs-lookup"><span data-stu-id="4f2c3-182">SharePoint.ExportDatabase</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f2c3-183">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="4f2c3-183">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="4f2c3-184">SpreadSheetLauncher</span><span class="sxs-lookup"><span data-stu-id="4f2c3-184">SharePoint.SpreadSheetLauncher</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f2c3-185">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="4f2c3-185">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="4f2c3-186">StssyncHander</span><span class="sxs-lookup"><span data-stu-id="4f2c3-186">SharePoint.StssyncHander</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f2c3-187">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="4f2c3-187">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="4f2c3-188">DragUploadCtl</span><span class="sxs-lookup"><span data-stu-id="4f2c3-188">SharePoint.DragUploadCtl</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f2c3-189">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="4f2c3-189">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="4f2c3-190">DragDownloadCtl</span><span class="sxs-lookup"><span data-stu-id="4f2c3-190">SharePoint.DragDownloadCtl</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f2c3-191">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="4f2c3-191">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="4f2c3-192">Sharpoint.OpenXMLDocuments</span><span class="sxs-lookup"><span data-stu-id="4f2c3-192">Sharpoint.OpenXMLDocuments</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f2c3-193">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="4f2c3-193">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="4f2c3-194">ClipboardCtl</span><span class="sxs-lookup"><span data-stu-id="4f2c3-194">Sharepoint.ClipboardCtl</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f2c3-195">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="4f2c3-195">Active X control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="4f2c3-196">WinProj Activator</span><span class="sxs-lookup"><span data-stu-id="4f2c3-196">WinProj.Activator</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f2c3-197">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="4f2c3-197">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="4f2c3-198">NameCtrl</span><span class="sxs-lookup"><span data-stu-id="4f2c3-198">Name.NameCtrl</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f2c3-199">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="4f2c3-199">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="4f2c3-200">STSUPld.CopyCtl</span><span class="sxs-lookup"><span data-stu-id="4f2c3-200">STSUPld.CopyCtl</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f2c3-201">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="4f2c3-201">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="4f2c3-202">CommunicatorMeetingJoinAx.JoinManager</span><span class="sxs-lookup"><span data-stu-id="4f2c3-202">CommunicatorMeetingJoinAx.JoinManager</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f2c3-203">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="4f2c3-203">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="4f2c3-204">LISTNET.Listnet</span><span class="sxs-lookup"><span data-stu-id="4f2c3-204">LISTNET.Listnet</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f2c3-205">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="4f2c3-205">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="4f2c3-206">OneDrive 專業版瀏覽器協助程式</span><span class="sxs-lookup"><span data-stu-id="4f2c3-206">OneDrive Pro Browser Helper</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f2c3-207">Active X 控制項]</span><span class="sxs-lookup"><span data-stu-id="4f2c3-207">Active X Control]</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4f2c3-208">OneDrive Pro 圖示重迭</span><span class="sxs-lookup"><span data-stu-id="4f2c3-208">OneDrive Pro Icon Overlays</span></span></p></td>
<td align="left"><p><span data-ttu-id="4f2c3-209">當使用者查看資料夾 OneDrive Pro 資料夾時，Windows explorer shell 圖示會重迭</span><span class="sxs-lookup"><span data-stu-id="4f2c3-209">Windows explorer shell icon overlays when users look at folders OneDrive Pro folders</span></span></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="4f2c3-210">其他資源</span><span class="sxs-lookup"><span data-stu-id="4f2c3-210">Additional resources</span></span>


**<span data-ttu-id="4f2c3-211">Office 2013 App-V 5.0 套件5.0 其他資源</span><span class="sxs-lookup"><span data-stu-id="4f2c3-211">Office 2013 App-V 5.0 Packages 5.0 Additional Resources</span></span>**

[<span data-ttu-id="4f2c3-212">將 Microsoft Office 部署為已排序的 App-v 套件所支援的案例</span><span class="sxs-lookup"><span data-stu-id="4f2c3-212">Supported scenarios for deploying Microsoft Office as a sequenced App-V Package</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330680)

**<span data-ttu-id="4f2c3-213">Office 2010 App-V 5.0 套件</span><span class="sxs-lookup"><span data-stu-id="4f2c3-213">Office 2010 App-V 5.0 Packages</span></span>**

[<span data-ttu-id="4f2c3-214">Microsoft Application Virtualization 5.0 的 microsoft Office 2010 排序套件</span><span class="sxs-lookup"><span data-stu-id="4f2c3-214">Microsoft Office 2010 Sequencing Kit for Microsoft Application Virtualization 5.0</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330681)

[<span data-ttu-id="4f2c3-215">建立或使用 App-v 5.0 Office 2010 套件時的已知問題</span><span class="sxs-lookup"><span data-stu-id="4f2c3-215">Known issues when you create or use an App-V 5.0 Office 2010 package</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330682)

[<span data-ttu-id="4f2c3-216">如何在 Microsoft Application Virtualization 5.0 中排序 Microsoft Office 2010</span><span class="sxs-lookup"><span data-stu-id="4f2c3-216">How to sequence Microsoft Office 2010 in Microsoft Application Virtualization 5.0</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330676)

**<span data-ttu-id="4f2c3-217">連線群組</span><span class="sxs-lookup"><span data-stu-id="4f2c3-217">Connection Groups</span></span>**

[<span data-ttu-id="4f2c3-218">在 Microsoft App 中部署連線群組-V v5</span><span class="sxs-lookup"><span data-stu-id="4f2c3-218">Deploying Connection Groups in Microsoft App-V v5</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330683)

[<span data-ttu-id="4f2c3-219">管理連線群組</span><span class="sxs-lookup"><span data-stu-id="4f2c3-219">Managing Connection Groups</span></span>](managing-connection-groups.md)

**<span data-ttu-id="4f2c3-220">動態設定</span><span class="sxs-lookup"><span data-stu-id="4f2c3-220">Dynamic Configuration</span></span>**

[<span data-ttu-id="4f2c3-221">關於 App-V 5.0 動態組態</span><span class="sxs-lookup"><span data-stu-id="4f2c3-221">About App-V 5.0 Dynamic Configuration</span></span>](about-app-v-50-dynamic-configuration.md)






 

 





