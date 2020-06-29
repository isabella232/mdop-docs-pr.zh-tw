---
title: 使用 App-V 部署 Microsoft Office 2010
description: 使用 App-V 部署 Microsoft Office 2010
author: dansimp
ms.assetid: ae0b0459-c0d6-4946-b62d-ff153f52d1fb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 90454373e9a1c894eba8cbf1b8642656b986bc94
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800640"
---
# <span data-ttu-id="66249-103">使用 App-V 部署 Microsoft Office 2010</span><span class="sxs-lookup"><span data-stu-id="66249-103">Deploying Microsoft Office 2010 by Using App-V</span></span>


<span data-ttu-id="66249-104">您可以使用下列其中一種方法，為 Microsoft 應用程式虛擬化（App-v）5.1 建立 Office 2010 套件：</span><span class="sxs-lookup"><span data-stu-id="66249-104">You can create Office 2010 packages for Microsoft Application Virtualization (App-V) 5.1 using one of the following methods:</span></span>

-   <span data-ttu-id="66249-105">應用程式虛擬化（App-v） Sequencer</span><span class="sxs-lookup"><span data-stu-id="66249-105">Application Virtualization (App-V) Sequencer</span></span>

-   <span data-ttu-id="66249-106">應用程式虛擬化（App-v）套件加速器</span><span class="sxs-lookup"><span data-stu-id="66249-106">Application Virtualization (App-V) Package Accelerator</span></span>

## <span data-ttu-id="66249-107">Office 2010 的 app-v 支援</span><span class="sxs-lookup"><span data-stu-id="66249-107">App-V support for Office 2010</span></span>


<span data-ttu-id="66249-108">下表顯示 App-V 版本、Office 套件建立的方法、支援的授權，以及 Office 2010 支援的部署。</span><span class="sxs-lookup"><span data-stu-id="66249-108">The following table shows the App-V versions, methods of Office package creation, supported licensing, and supported deployments for Office 2010.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="66249-109">支援的專案</span><span class="sxs-lookup"><span data-stu-id="66249-109">Supported item</span></span></th>
<th align="left"><span data-ttu-id="66249-110">支援層級</span><span class="sxs-lookup"><span data-stu-id="66249-110">Level of support</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="66249-111">支援的 App-v 版本</span><span class="sxs-lookup"><span data-stu-id="66249-111">Supported App-V versions</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="66249-112">4.6</span><span class="sxs-lookup"><span data-stu-id="66249-112">4.6</span></span></p></li>
<li><p><span data-ttu-id="66249-113">5.0</span><span class="sxs-lookup"><span data-stu-id="66249-113">5.0</span></span></p></li>
<li><p><span data-ttu-id="66249-114">5.1</span><span class="sxs-lookup"><span data-stu-id="66249-114">5.1</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="66249-115">建立套件</span><span class="sxs-lookup"><span data-stu-id="66249-115">Package creation</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="66249-116">序列</span><span class="sxs-lookup"><span data-stu-id="66249-116">Sequencing</span></span></p></li>
<li><p><span data-ttu-id="66249-117">套件加速器</span><span class="sxs-lookup"><span data-stu-id="66249-117">Package Accelerator</span></span></p></li>
<li><p><span data-ttu-id="66249-118">Office 部署套件</span><span class="sxs-lookup"><span data-stu-id="66249-118">Office Deployment Kit</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="66249-119">支援的授權</span><span class="sxs-lookup"><span data-stu-id="66249-119">Supported licensing</span></span></p></td>
<td align="left"><p><span data-ttu-id="66249-120">大量授權</span><span class="sxs-lookup"><span data-stu-id="66249-120">Volume Licensing</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="66249-121">支援的部署</span><span class="sxs-lookup"><span data-stu-id="66249-121">Supported deployments</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="66249-122">桌面</span><span class="sxs-lookup"><span data-stu-id="66249-122">Desktop</span></span></p></li>
<li><p><span data-ttu-id="66249-123">個人 VDI</span><span class="sxs-lookup"><span data-stu-id="66249-123">Personal VDI</span></span></p></li>
<li><p><span data-ttu-id="66249-124">句</span><span class="sxs-lookup"><span data-stu-id="66249-124">RDS</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="66249-125">使用排序器建立 Office 2010 App-V 5。1</span><span class="sxs-lookup"><span data-stu-id="66249-125">Creating Office 2010 App-V 5.1 using the sequencer</span></span>


<span data-ttu-id="66249-126">排序 Office 2010 是在應用程式 V 5.1 上建立 Office 2010 套件的主要方法之一。</span><span class="sxs-lookup"><span data-stu-id="66249-126">Sequencing Office 2010 is one of the main methods for creating an Office 2010 package on App-V 5.1.</span></span> <span data-ttu-id="66249-127">Microsoft 已透過知識庫文章提供詳細的食譜。</span><span class="sxs-lookup"><span data-stu-id="66249-127">Microsoft has provided a detailed recipe through a Knowledge Base article.</span></span> <span data-ttu-id="66249-128">若要在 App-V 5.1 上建立 Office 2010 套件，請參閱下列連結，以取得詳細指示：</span><span class="sxs-lookup"><span data-stu-id="66249-128">To create an Office 2010 package on App-V 5.1, refer to the following link for detailed instructions:</span></span>

[<span data-ttu-id="66249-129">如何在 Microsoft Application Virtualization 5.0 中排序 Microsoft Office 2010</span><span class="sxs-lookup"><span data-stu-id="66249-129">How To Sequence Microsoft Office 2010 in Microsoft Application Virtualization 5.0</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330676)

## <span data-ttu-id="66249-130">使用套件加速器建立 Office 2010 App-V 5.1 套件</span><span class="sxs-lookup"><span data-stu-id="66249-130">Creating Office 2010 App-V 5.1 packages using package accelerators</span></span>


<span data-ttu-id="66249-131">您可以透過套件加速器建立 Office 2010 App-V 5.1 套件。</span><span class="sxs-lookup"><span data-stu-id="66249-131">Office 2010 App-V 5.1 packages can be created through package accelerators.</span></span> <span data-ttu-id="66249-132">Microsoft 已提供套件加速器，可在 Windows 10、Windows 8 和 Windows 7 上建立 Office 2010。</span><span class="sxs-lookup"><span data-stu-id="66249-132">Microsoft has provided package accelerators for creating Office 2010 on Windows 10, Windows 8 and Windows 7.</span></span> <span data-ttu-id="66249-133">若要使用套件加速器在 App-v 上建立 Office 2010 套件，請參閱下列頁面，以存取適當的套件加速器：</span><span class="sxs-lookup"><span data-stu-id="66249-133">To create Office 2010 packages on App-V using Package accelerators, refer to the following pages to access the appropriate package accelerator:</span></span>

-   [<span data-ttu-id="66249-134">適用于 Office 專業增強版2010– Windows 8 的 app-v 5.0 套件加速器</span><span class="sxs-lookup"><span data-stu-id="66249-134">App-V 5.0 Package Accelerator for Office Professional Plus 2010 – Windows 8</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330677)

-   [<span data-ttu-id="66249-135">適用于 Office 專業增強版2010的 app-v 5.0 套件加速器-Windows 7</span><span class="sxs-lookup"><span data-stu-id="66249-135">App-V 5.0 Package Accelerator for Office Professional Plus 2010 – Windows 7</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330678)

<span data-ttu-id="66249-136">如需如何使用 App-v 套件加速器建立虛擬應用程式套件的詳細指示，請參閱[如何使用 App-v 套件加速器建立虛擬應用程式套件](how-to-create-a-virtual-application-package-using-an-app-v-package-accelerator51.md)。</span><span class="sxs-lookup"><span data-stu-id="66249-136">For detailed instructions on how to create virtual application packages using App-V package accelerators, see [How to Create a Virtual Application Package Using an App-V Package Accelerator](how-to-create-a-virtual-application-package-using-an-app-v-package-accelerator51.md).</span></span>

## <span data-ttu-id="66249-137">部署應用程式的 Microsoft Office 套件-V 5。1</span><span class="sxs-lookup"><span data-stu-id="66249-137">Deploying the Microsoft Office package for App-V 5.1</span></span>


<span data-ttu-id="66249-138">您可以使用下列任何一種 App V 部署方法，部署 Office 2010 套件：</span><span class="sxs-lookup"><span data-stu-id="66249-138">You can deploy Office 2010 packages by using any of the following App-V deployment methods:</span></span>

-   <span data-ttu-id="66249-139">System Center Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="66249-139">System Center Configuration Manager</span></span>

-   <span data-ttu-id="66249-140">App-v server</span><span class="sxs-lookup"><span data-stu-id="66249-140">App-V server</span></span>

-   <span data-ttu-id="66249-141">從 PowerShell 命令中獨立</span><span class="sxs-lookup"><span data-stu-id="66249-141">Stand-alone through PowerShell commands</span></span>

## <span data-ttu-id="66249-142">Office App-v 套件管理與自訂</span><span class="sxs-lookup"><span data-stu-id="66249-142">Office App-V package management and customization</span></span>


<span data-ttu-id="66249-143">您可以透過已知的套件管理機制，管理 Office 2010 套件，就像任何其他 App-V 5.1 套件一樣。</span><span class="sxs-lookup"><span data-stu-id="66249-143">Office 2010 packages can be managed like any other App-V 5.1 packages through known package management mechanisms.</span></span> <span data-ttu-id="66249-144">不需要任何特殊指示，例如新增、發佈、取消發佈或移除 Office 套件。</span><span class="sxs-lookup"><span data-stu-id="66249-144">No special instructions are needed, for example, to add, publish, unpublish, or remove Office packages.</span></span>

## <span data-ttu-id="66249-145">Microsoft Office 與 Windows 整合</span><span class="sxs-lookup"><span data-stu-id="66249-145">Microsoft Office integration with Windows</span></span>


<span data-ttu-id="66249-146">下表提供 Office 2010 支援整合點的完整清單。</span><span class="sxs-lookup"><span data-stu-id="66249-146">The following table provides a full list of supported integration points for Office 2010.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="66249-147">延伸點</span><span class="sxs-lookup"><span data-stu-id="66249-147">Extension Point</span></span></th>
<th align="left"><span data-ttu-id="66249-148">描述</span><span class="sxs-lookup"><span data-stu-id="66249-148">Description</span></span></th>
<th align="left"><span data-ttu-id="66249-149">Office 2010</span><span class="sxs-lookup"><span data-stu-id="66249-149">Office 2010</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="66249-150">適用于 Firefox 和 Chrome 的 Lync 會議加入外掛程式</span><span class="sxs-lookup"><span data-stu-id="66249-150">Lync meeting Join Plug-in for Firefox and Chrome</span></span></p></td>
<td align="left"><p><span data-ttu-id="66249-151">使用者可以從 Firefox 和 Chrome 加入 Lync 會議</span><span class="sxs-lookup"><span data-stu-id="66249-151">User can join Lync meetings from Firefox and Chrome</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="66249-152">已傳送至 OneNote 列印驅動程式</span><span class="sxs-lookup"><span data-stu-id="66249-152">Sent to OneNote Print Driver</span></span></p></td>
<td align="left"><p><span data-ttu-id="66249-153">使用者可以列印至 OneNote</span><span class="sxs-lookup"><span data-stu-id="66249-153">User can print to OneNote</span></span></p></td>
<td align="left"><p><span data-ttu-id="66249-154">是</span><span class="sxs-lookup"><span data-stu-id="66249-154">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="66249-155">OneNote 連結筆記</span><span class="sxs-lookup"><span data-stu-id="66249-155">OneNote Linked Notes</span></span></p></td>
<td align="left"><p><span data-ttu-id="66249-156">OneNote 連結筆記</span><span class="sxs-lookup"><span data-stu-id="66249-156">OneNote Linked Notes</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="66249-157">傳送至 OneNote Internet Explorer 增益集</span><span class="sxs-lookup"><span data-stu-id="66249-157">Send to OneNote Internet Explorer Add-In</span></span></p></td>
<td align="left"><p><span data-ttu-id="66249-158">使用者可以從 IE 傳送至 OneNote</span><span class="sxs-lookup"><span data-stu-id="66249-158">User can send to OneNote from IE</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="66249-159">Lync 和 Outlook 的防火牆例外狀況</span><span class="sxs-lookup"><span data-stu-id="66249-159">Firewall Exception for Lync and Outlook</span></span></p></td>
<td align="left"><p><span data-ttu-id="66249-160">Lync 和 Outlook 的防火牆例外狀況</span><span class="sxs-lookup"><span data-stu-id="66249-160">Firewall Exception for Lync and Outlook</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="66249-161">MAPI 用戶端</span><span class="sxs-lookup"><span data-stu-id="66249-161">MAPI Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="66249-162">原生應用程式和增益集可透過 MAPI 與虛擬 Outlook 互動</span><span class="sxs-lookup"><span data-stu-id="66249-162">Native apps and add-ins can interact with virtual Outlook through MAPI</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="66249-163">Firefox 適用的 SharePoint 外掛程式</span><span class="sxs-lookup"><span data-stu-id="66249-163">SharePoint Plugin for Firefox</span></span></p></td>
<td align="left"><p><span data-ttu-id="66249-164">使用者可以在 Firefox 中使用 SharePoint 功能</span><span class="sxs-lookup"><span data-stu-id="66249-164">User can use SharePoint features in Firefox</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="66249-165">[郵件] 控制台小程式</span><span class="sxs-lookup"><span data-stu-id="66249-165">Mail Control Panel Applet</span></span></p></td>
<td align="left"><p><span data-ttu-id="66249-166">使用者在 Outlook 中取得 [郵件] 控制台小程式</span><span class="sxs-lookup"><span data-stu-id="66249-166">User gets the mail control panel applet in Outlook</span></span></p></td>
<td align="left"><p><span data-ttu-id="66249-167">是</span><span class="sxs-lookup"><span data-stu-id="66249-167">Yes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="66249-168">主要 Interop 元件</span><span class="sxs-lookup"><span data-stu-id="66249-168">Primary Interop Assemblies</span></span></p></td>
<td align="left"><p><span data-ttu-id="66249-169">支援受管理的增益集</span><span class="sxs-lookup"><span data-stu-id="66249-169">Support managed add-ins</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="66249-170">Office 檔快取處理常式</span><span class="sxs-lookup"><span data-stu-id="66249-170">Office Document Cache Handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="66249-171">允許 Office 應用程式的檔快取</span><span class="sxs-lookup"><span data-stu-id="66249-171">Allows Document Cache for Office applications</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="66249-172">Outlook 通訊協定搜尋處理常式</span><span class="sxs-lookup"><span data-stu-id="66249-172">Outlook Protocol Search handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="66249-173">使用者可以在 outlook 中搜尋</span><span class="sxs-lookup"><span data-stu-id="66249-173">User can search in outlook</span></span></p></td>
<td align="left"><p><span data-ttu-id="66249-174">是</span><span class="sxs-lookup"><span data-stu-id="66249-174">Yes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="66249-175">Active X 控制項：</span><span class="sxs-lookup"><span data-stu-id="66249-175">Active X Controls:</span></span></p></td>
<td align="left"><p><span data-ttu-id="66249-176">如需有關 ActiveX 控制項的詳細資訊，請參閱 <a href="https://go.microsoft.com/fwlink/p/?LinkId=331361" data-raw-source="[ActiveX Control API Reference](https://go.microsoft.com/fwlink/p/?LinkId=331361)"> Activex 控制項 API 參考 </a> 。</span><span class="sxs-lookup"><span data-stu-id="66249-176">For more information on ActiveX controls, refer to <a href="https://go.microsoft.com/fwlink/p/?LinkId=331361" data-raw-source="[ActiveX Control API Reference](https://go.microsoft.com/fwlink/p/?LinkId=331361)">ActiveX Control API Reference</a>.</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="66249-177">Groove. SiteClient</span><span class="sxs-lookup"><span data-stu-id="66249-177">Groove.SiteClient</span></span></p></td>
<td align="left"><p><span data-ttu-id="66249-178">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="66249-178">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="66249-179">PortalConnect.PersonalSite</span><span class="sxs-lookup"><span data-stu-id="66249-179">PortalConnect.PersonalSite</span></span></p></td>
<td align="left"><p><span data-ttu-id="66249-180">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="66249-180">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="66249-181">OpenDocuments</span><span class="sxs-lookup"><span data-stu-id="66249-181">SharePoint.openDocuments</span></span></p></td>
<td align="left"><p><span data-ttu-id="66249-182">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="66249-182">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="66249-183">ExportDatabase</span><span class="sxs-lookup"><span data-stu-id="66249-183">SharePoint.ExportDatabase</span></span></p></td>
<td align="left"><p><span data-ttu-id="66249-184">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="66249-184">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="66249-185">SpreadSheetLauncher</span><span class="sxs-lookup"><span data-stu-id="66249-185">SharePoint.SpreadSheetLauncher</span></span></p></td>
<td align="left"><p><span data-ttu-id="66249-186">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="66249-186">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="66249-187">StssyncHander</span><span class="sxs-lookup"><span data-stu-id="66249-187">SharePoint.StssyncHander</span></span></p></td>
<td align="left"><p><span data-ttu-id="66249-188">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="66249-188">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="66249-189">DragUploadCtl</span><span class="sxs-lookup"><span data-stu-id="66249-189">SharePoint.DragUploadCtl</span></span></p></td>
<td align="left"><p><span data-ttu-id="66249-190">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="66249-190">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="66249-191">DragDownloadCtl</span><span class="sxs-lookup"><span data-stu-id="66249-191">SharePoint.DragDownloadCtl</span></span></p></td>
<td align="left"><p><span data-ttu-id="66249-192">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="66249-192">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="66249-193">Sharpoint.OpenXMLDocuments</span><span class="sxs-lookup"><span data-stu-id="66249-193">Sharpoint.OpenXMLDocuments</span></span></p></td>
<td align="left"><p><span data-ttu-id="66249-194">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="66249-194">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="66249-195">ClipboardCtl</span><span class="sxs-lookup"><span data-stu-id="66249-195">Sharepoint.ClipboardCtl</span></span></p></td>
<td align="left"><p><span data-ttu-id="66249-196">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="66249-196">Active X control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="66249-197">WinProj Activator</span><span class="sxs-lookup"><span data-stu-id="66249-197">WinProj.Activator</span></span></p></td>
<td align="left"><p><span data-ttu-id="66249-198">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="66249-198">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="66249-199">NameCtrl</span><span class="sxs-lookup"><span data-stu-id="66249-199">Name.NameCtrl</span></span></p></td>
<td align="left"><p><span data-ttu-id="66249-200">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="66249-200">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="66249-201">STSUPld.CopyCtl</span><span class="sxs-lookup"><span data-stu-id="66249-201">STSUPld.CopyCtl</span></span></p></td>
<td align="left"><p><span data-ttu-id="66249-202">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="66249-202">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="66249-203">CommunicatorMeetingJoinAx.JoinManager</span><span class="sxs-lookup"><span data-stu-id="66249-203">CommunicatorMeetingJoinAx.JoinManager</span></span></p></td>
<td align="left"><p><span data-ttu-id="66249-204">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="66249-204">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="66249-205">LISTNET.Listnet</span><span class="sxs-lookup"><span data-stu-id="66249-205">LISTNET.Listnet</span></span></p></td>
<td align="left"><p><span data-ttu-id="66249-206">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="66249-206">Active X Control</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="66249-207">OneDrive 專業版瀏覽器協助程式</span><span class="sxs-lookup"><span data-stu-id="66249-207">OneDrive Pro Browser Helper</span></span></p></td>
<td align="left"><p><span data-ttu-id="66249-208">Active X 控制項]</span><span class="sxs-lookup"><span data-stu-id="66249-208">Active X Control]</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="66249-209">OneDrive Pro 圖示重迭</span><span class="sxs-lookup"><span data-stu-id="66249-209">OneDrive Pro Icon Overlays</span></span></p></td>
<td align="left"><p><span data-ttu-id="66249-210">當使用者查看資料夾 OneDrive Pro 資料夾時，Windows explorer shell 圖示會重迭</span><span class="sxs-lookup"><span data-stu-id="66249-210">Windows explorer shell icon overlays when users look at folders OneDrive Pro folders</span></span></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="66249-211">其他資源</span><span class="sxs-lookup"><span data-stu-id="66249-211">Additional resources</span></span>


**<span data-ttu-id="66249-212">Office 2013 App-V 封裝其他資源</span><span class="sxs-lookup"><span data-stu-id="66249-212">Office 2013 App-V Packages Additional Resources</span></span>**

[<span data-ttu-id="66249-213">將 Microsoft Office 部署為已排序的 App-v 套件所支援的案例</span><span class="sxs-lookup"><span data-stu-id="66249-213">Supported scenarios for deploying Microsoft Office as a sequenced App-V Package</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330680)

**<span data-ttu-id="66249-214">Office 2010 App-v 套件</span><span class="sxs-lookup"><span data-stu-id="66249-214">Office 2010 App-V Packages</span></span>**

[<span data-ttu-id="66249-215">Microsoft Application Virtualization 5.0 的 microsoft Office 2010 排序套件</span><span class="sxs-lookup"><span data-stu-id="66249-215">Microsoft Office 2010 Sequencing Kit for Microsoft Application Virtualization 5.0</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330681)

[<span data-ttu-id="66249-216">建立或使用 App-v 5.0 Office 2010 套件時的已知問題</span><span class="sxs-lookup"><span data-stu-id="66249-216">Known issues when you create or use an App-V 5.0 Office 2010 package</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330682)

[<span data-ttu-id="66249-217">如何在 Microsoft Application Virtualization 5.0 中排序 Microsoft Office 2010</span><span class="sxs-lookup"><span data-stu-id="66249-217">How to sequence Microsoft Office 2010 in Microsoft Application Virtualization 5.0</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330676)

**<span data-ttu-id="66249-218">連線群組</span><span class="sxs-lookup"><span data-stu-id="66249-218">Connection Groups</span></span>**

[<span data-ttu-id="66249-219">在 Microsoft App 中部署連線群組-V v5</span><span class="sxs-lookup"><span data-stu-id="66249-219">Deploying Connection Groups in Microsoft App-V v5</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=330683)

[<span data-ttu-id="66249-220">管理連線群組</span><span class="sxs-lookup"><span data-stu-id="66249-220">Managing Connection Groups</span></span>](managing-connection-groups51.md)

**<span data-ttu-id="66249-221">動態設定</span><span class="sxs-lookup"><span data-stu-id="66249-221">Dynamic Configuration</span></span>**

[<span data-ttu-id="66249-222">關於 App-V 5.1 動態組態</span><span class="sxs-lookup"><span data-stu-id="66249-222">About App-V 5.1 Dynamic Configuration</span></span>](about-app-v-51-dynamic-configuration.md)






 

 





