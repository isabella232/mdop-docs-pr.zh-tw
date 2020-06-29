---
title: 準備 UE-V a.x 部署
description: 準備 UE-V a.x 部署
author: dansimp
ms.assetid: c429fd06-13ff-48c5-b9c9-fa1ec01ab800
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 04/19/2017
ms.openlocfilehash: e6b2de407990536e1a08532632dcea19ea0d0ee9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811745"
---
# <span data-ttu-id="6e138-103">準備 UE-V a.x 部署</span><span class="sxs-lookup"><span data-stu-id="6e138-103">Prepare a UE-V 2.x Deployment</span></span>


<span data-ttu-id="6e138-104">在將 Microsoft 使用者體驗虛擬化（UE-V）2.0 或2.1 部署為可在使用者在企業中存取的裝置之間同步處理設定的方案之前，必須先進行一些規劃及準備。</span><span class="sxs-lookup"><span data-stu-id="6e138-104">There is some planning and preparation to do before you deploy Microsoft User Experience Virtualization (UE-V) 2.0 or 2.1 as a solution for synchronizing settings between devices that users access in your enterprise.</span></span> <span data-ttu-id="6e138-105">本主題可協助您判斷您要執行的部署類型，以及您可以提前進行的準備，以便順利進行部署。</span><span class="sxs-lookup"><span data-stu-id="6e138-105">This topic helps you determine what type of deployment you'll be doing and what preparation you can make beforehand so that your deployment is successful.</span></span>

<span data-ttu-id="6e138-106">首先，讓我們來看看部署 UE-V 要執行的工作：</span><span class="sxs-lookup"><span data-stu-id="6e138-106">First, let’s look at the tasks you’ll do to deploy UE-V:</span></span>

-   <span data-ttu-id="6e138-107">規劃您的 UE-V 部署</span><span class="sxs-lookup"><span data-stu-id="6e138-107">Plan your UE-V Deployment</span></span>

    <span data-ttu-id="6e138-108">在您部署任何專案之前，最好先進行一些規劃，讓您可以判斷您要部署哪些 UE-V 功能。</span><span class="sxs-lookup"><span data-stu-id="6e138-108">Before you deploy anything, a good first step is to do a little bit of planning so that you can determine which UE-V features you’ll deploy.</span></span> <span data-ttu-id="6e138-109">因此，如果您離開此頁面，請務必返回並閱讀下面的規劃資訊。</span><span class="sxs-lookup"><span data-stu-id="6e138-109">So if you leave this page, make sure you come back and read through the planning information below.</span></span>

-   [<span data-ttu-id="6e138-110">部署 UE-V 2.x 的必要功能</span><span class="sxs-lookup"><span data-stu-id="6e138-110">Deploy Required Features for UE-V 2.x</span></span>](deploy-required-features-for-ue-v-2x-new-uevv2.md)

    <span data-ttu-id="6e138-111">每個 UE-V 部署都需要下列活動：</span><span class="sxs-lookup"><span data-stu-id="6e138-111">Every UE-V deployment requires these activities:</span></span>

    -   [<span data-ttu-id="6e138-112">定義設定儲存位置</span><span class="sxs-lookup"><span data-stu-id="6e138-112">Define a settings storage location</span></span>](https://technet.microsoft.com/library/dn458891.aspx#ssl)

    -   [<span data-ttu-id="6e138-113">決定如何部署 UE-V Agent 及管理 UE-V 設定</span><span class="sxs-lookup"><span data-stu-id="6e138-113">Decide how to deploy the UE-V Agent and manage UE-V configurations</span></span>](https://technet.microsoft.com/library/dn458891.aspx#config)

    -   <span data-ttu-id="6e138-114">在每個需要同步處理設定的使用者電腦上[安裝 Ue-v Agent](https://technet.microsoft.com/library/dn458891.aspx#agent)</span><span class="sxs-lookup"><span data-stu-id="6e138-114">[Install the UE-V Agent](https://technet.microsoft.com/library/dn458891.aspx#agent) on every user computer that needs settings synchronized</span></span>

-   <span data-ttu-id="6e138-115">或者，您也可以[為自訂應用程式部署 ue-v 2. x](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)</span><span class="sxs-lookup"><span data-stu-id="6e138-115">Optionally, you can [Deploy UE-V 2.x for Custom Applications](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)</span></span>

    <span data-ttu-id="6e138-116">規劃將可協助您判斷是否希望 UE-V 支援針對自訂應用程式（協力廠商或商務線）的設定同步處理，而這需要下列 UE-V 功能：</span><span class="sxs-lookup"><span data-stu-id="6e138-116">Planning will help you figure out whether you want UE-V to support the synchronization of settings for custom applications (third-party or line-of-business), which requires these UE-V features:</span></span>

    -   <span data-ttu-id="6e138-117">[安裝 UEV 發生器](https://technet.microsoft.com/library/dn458942.aspx#uevgen)，讓您可以建立、編輯及驗證同步處理自訂應用程式設定所需的自訂設定位置範本</span><span class="sxs-lookup"><span data-stu-id="6e138-117">[Install the UEV Generator](https://technet.microsoft.com/library/dn458942.aspx#uevgen) so you can create, edit, and validate the custom settings location templates required to synchronize custom application settings</span></span>

    -   <span data-ttu-id="6e138-118">使用 UE-V 發生器[建立自訂設定位置範本](https://technet.microsoft.com/library/dn458942.aspx#createcustomtemplates)</span><span class="sxs-lookup"><span data-stu-id="6e138-118">[Create custom settings location templates](https://technet.microsoft.com/library/dn458942.aspx#createcustomtemplates) by using the UE-V Generator</span></span>

    -   <span data-ttu-id="6e138-119">部署您用來儲存您的自訂設定位置範本的[ue-v 設定範本目錄](https://technet.microsoft.com/library/dn458942.aspx#deploycatalogue)</span><span class="sxs-lookup"><span data-stu-id="6e138-119">[Deploy a UE-V settings template catalog](https://technet.microsoft.com/library/dn458942.aspx#deploycatalogue) that you use to store your custom settings location templates</span></span>

<span data-ttu-id="6e138-120">此工作流程圖表可讓您深入瞭解 UE-V 部署，以及決定如何在企業中部署 UE-V 的決定。</span><span class="sxs-lookup"><span data-stu-id="6e138-120">This workflow diagram provides a high-level understanding of a UE-V deployment and the decisions that determine how you deploy UE-V in your enterprise.</span></span>

![deploymentworkflow](images/deploymentworkflow.png)

<span data-ttu-id="6e138-122">**規劃 ue-v 部署：** 首先，您想要執行一些規劃，讓您可以判斷要部署哪些 UE-V 元件。</span><span class="sxs-lookup"><span data-stu-id="6e138-122">**Planning a UE-V deployment:** First, you want to do a little bit of planning so that you can determine which UE-V components you’ll be deploying.</span></span> <span data-ttu-id="6e138-123">規劃 UE-V 部署包括下列專案：</span><span class="sxs-lookup"><span data-stu-id="6e138-123">Planning a UE-V deployment involves these things:</span></span>

-   [<span data-ttu-id="6e138-124">決定是否要同步處理自訂應用程式的設定</span><span class="sxs-lookup"><span data-stu-id="6e138-124">Decide whether to synchronize settings for custom applications</span></span>](#deciding)

    <span data-ttu-id="6e138-125">這會判斷您是否要在部署期間安裝 UE-V 發生器，這可讓您建立自訂設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="6e138-125">This determines whether you will install the UE-V Generator during deployment, which lets you create custom settings location templates.</span></span> <span data-ttu-id="6e138-126">它包含下列專案：</span><span class="sxs-lookup"><span data-stu-id="6e138-126">It involves the following:</span></span>

    <span data-ttu-id="6e138-127">查看[在 ue-v 部署中自動同步](#autosyncsettings)處理的設定。</span><span class="sxs-lookup"><span data-stu-id="6e138-127">Review the [settings that are synchronized automatically in a UE-V deployment](#autosyncsettings).</span></span>

    <span data-ttu-id="6e138-128">[判斷您是否需要同步處理其他應用程式的設定](#determinesettingssync)。</span><span class="sxs-lookup"><span data-stu-id="6e138-128">[Determine whether you need settings synchronized for other applications](#determinesettingssync).</span></span>

-   <span data-ttu-id="6e138-129">查看[部署 ue-v 的其他考慮](#considerations)（例如高可用性和容量規劃）。</span><span class="sxs-lookup"><span data-stu-id="6e138-129">Review [other considerations for deploying UE-V](#considerations), such as high availability and capacity planning.</span></span>

-   [<span data-ttu-id="6e138-130">確認 UE-V 的先決條件和支援的設定</span><span class="sxs-lookup"><span data-stu-id="6e138-130">Confirm prerequisites and supported configurations for UE-V</span></span>](#prereqs)

## <a href="" id="deciding"></a><span data-ttu-id="6e138-131">決定是否要同步處理自訂應用程式的設定</span><span class="sxs-lookup"><span data-stu-id="6e138-131">Decide Whether to Synchronize Settings for Custom Applications</span></span>


<span data-ttu-id="6e138-132">在 UE-V 部署中，許多設定會自動同步處理。</span><span class="sxs-lookup"><span data-stu-id="6e138-132">In a UE-V deployment, many settings are automatically synchronized.</span></span> <span data-ttu-id="6e138-133">但您也可以自訂 UE-V，以同步處理其他應用程式的設定，例如企業與協力廠商應用程式。</span><span class="sxs-lookup"><span data-stu-id="6e138-133">But you can also customize UE-V to synchronize settings for other applications, such as line-of-business and third-party apps.</span></span>

<span data-ttu-id="6e138-134">決定是否要讓 UE-V 同步處理自訂應用程式的設定，這可能是規劃 UE-V 部署最重要的部分。</span><span class="sxs-lookup"><span data-stu-id="6e138-134">Deciding if you want UE-V to synchronize settings for custom applications is probably the most important part of planning your UE-V deployment.</span></span> <span data-ttu-id="6e138-135">本節中的主題將協助您做出這項決策。</span><span class="sxs-lookup"><span data-stu-id="6e138-135">The topics in this section will help you make that decision.</span></span>

### <a href="" id="autosyncsettings"></a><span data-ttu-id="6e138-136">在 UE-V 部署中自動同步處理的設定</span><span class="sxs-lookup"><span data-stu-id="6e138-136">Settings that are automatically synchronized in a UE-V deployment</span></span>

<span data-ttu-id="6e138-137">本節提供與 UE-V 預設同步處理之設定的相關資訊，包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="6e138-137">This section provides information about the settings that are synchronized by default in UE-V, including the following:</span></span>

<span data-ttu-id="6e138-138">預設會同步處理設定的桌面應用程式</span><span class="sxs-lookup"><span data-stu-id="6e138-138">Desktop applications whose settings are synchronized by default</span></span>

<span data-ttu-id="6e138-139">預設會同步處理的 Windows 桌面設定</span><span class="sxs-lookup"><span data-stu-id="6e138-139">Windows desktop settings that are synchronized by default</span></span>

<span data-ttu-id="6e138-140">Windows 應用程式設定同步處理的支援語句</span><span class="sxs-lookup"><span data-stu-id="6e138-140">A statement of support for Windows app setting synchronization</span></span>

<span data-ttu-id="6e138-141">請參閱[適用于 Microsoft Office 的使用者體驗虛擬化（ue-v）設定範本](https://www.microsoft.com/download/details.aspx?id=46367)，下載已由 ue-v 同步處理的特定 Microsoft office 2013、microsoft office 2010 及 Microsoft office 2007 設定的完整清單。</span><span class="sxs-lookup"><span data-stu-id="6e138-141">See [User Experience Virtualization (UE-V) settings templates for Microsoft Office](https://www.microsoft.com/download/details.aspx?id=46367) to download a complete list of the specific Microsoft Office 2013, Microsoft Office 2010, and Microsoft Office 2007 settings that are synchronized by UE-V.</span></span>

### <span data-ttu-id="6e138-142">UE-V 2.1 和 UE-V 2.1 SP1 中的預設同步處理桌面應用程式</span><span class="sxs-lookup"><span data-stu-id="6e138-142">Desktop applications synchronized by default in UE-V 2.1 and UE-V 2.1 SP1</span></span>

<span data-ttu-id="6e138-143">當您安裝 UE-V 2.1 或 2.1 SP1 代理程式時，它會註冊一個預設的設定位置範本群組，以捕獲這些常見 Microsoft 應用程式的設定值。</span><span class="sxs-lookup"><span data-stu-id="6e138-143">When you install the UE-V 2.1 or 2.1 SP1 Agent, it registers a default group of settings location templates that capture settings values for these common Microsoft applications.</span></span>

**<span data-ttu-id="6e138-144">提示</span><span class="sxs-lookup"><span data-stu-id="6e138-144">Tip</span></span>**  
<span data-ttu-id="6e138-145">**Microsoft office 2007 設定同步**處理-在 ue-v 2.1 和 2.1 SP1 中，Office 2007 應用程式預設不再包含設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="6e138-145">**Microsoft Office 2007 Settings Synchronization** – In UE-V 2.1 and 2.1 SP1, a settings location template is no longer included by default for Office 2007 applications.</span></span> <span data-ttu-id="6e138-146">不過，您仍然可以使用 UE-V 2.0 或較舊版本的 Office 2007 範本，並可從[ue-v 範本庫](https://go.microsoft.com/fwlink/p/?LinkID=246589)取得範本。</span><span class="sxs-lookup"><span data-stu-id="6e138-146">However, you can still use Office 2007 templates from UE-V 2.0 or earlier and can get the templates from the [UE-V template gallery](https://go.microsoft.com/fwlink/p/?LinkID=246589).</span></span>



<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="6e138-147">應用程式類別</span><span class="sxs-lookup"><span data-stu-id="6e138-147">Application category</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="6e138-148">描述</span><span class="sxs-lookup"><span data-stu-id="6e138-148">Description</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6e138-149">Microsoft Office 2010 應用程式</span><span class="sxs-lookup"><span data-stu-id="6e138-149">Microsoft Office 2010 applications</span></span></p>
<p><span data-ttu-id="6e138-150">（ <a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)"> 下載所有設定已同步處理的清單 </a> ）</span><span class="sxs-lookup"><span data-stu-id="6e138-150">(<a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)">Download a list of all settings synced</a>)</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-151">Microsoft Word 2010</span><span class="sxs-lookup"><span data-stu-id="6e138-151">Microsoft Word 2010</span></span></p>
<p><span data-ttu-id="6e138-152">Microsoft Excel 2010</span><span class="sxs-lookup"><span data-stu-id="6e138-152">Microsoft Excel 2010</span></span></p>
<p><span data-ttu-id="6e138-153">Microsoft Outlook 2010</span><span class="sxs-lookup"><span data-stu-id="6e138-153">Microsoft Outlook 2010</span></span></p>
<p><span data-ttu-id="6e138-154">Microsoft Access 2010</span><span class="sxs-lookup"><span data-stu-id="6e138-154">Microsoft Access 2010</span></span></p>
<p><span data-ttu-id="6e138-155">Microsoft Project 2010</span><span class="sxs-lookup"><span data-stu-id="6e138-155">Microsoft Project 2010</span></span></p>
<p><span data-ttu-id="6e138-156">Microsoft PowerPoint 2010</span><span class="sxs-lookup"><span data-stu-id="6e138-156">Microsoft PowerPoint 2010</span></span></p>
<p><span data-ttu-id="6e138-157">Microsoft Publisher 2010</span><span class="sxs-lookup"><span data-stu-id="6e138-157">Microsoft Publisher 2010</span></span></p>
<p><span data-ttu-id="6e138-158">Microsoft Visio 2010</span><span class="sxs-lookup"><span data-stu-id="6e138-158">Microsoft Visio 2010</span></span></p>
<p><span data-ttu-id="6e138-159">Microsoft SharePoint Workspace 2010</span><span class="sxs-lookup"><span data-stu-id="6e138-159">Microsoft SharePoint Workspace 2010</span></span></p>
<p><span data-ttu-id="6e138-160">Microsoft InfoPath 2010</span><span class="sxs-lookup"><span data-stu-id="6e138-160">Microsoft InfoPath 2010</span></span></p>
<p><span data-ttu-id="6e138-161">Microsoft Lync 2010</span><span class="sxs-lookup"><span data-stu-id="6e138-161">Microsoft Lync 2010</span></span></p>
<p><span data-ttu-id="6e138-162">Microsoft OneNote 2010</span><span class="sxs-lookup"><span data-stu-id="6e138-162">Microsoft OneNote 2010</span></span></p>
<p><span data-ttu-id="6e138-163">Microsoft SharePoint Designer 2010</span><span class="sxs-lookup"><span data-stu-id="6e138-163">Microsoft SharePoint Designer 2010</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6e138-164">Microsoft Office 2013 應用程式</span><span class="sxs-lookup"><span data-stu-id="6e138-164">Microsoft Office 2013 applications</span></span></p>
<p><span data-ttu-id="6e138-165">（ <a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)"> 下載所有設定已同步處理的清單 </a> ）</span><span class="sxs-lookup"><span data-stu-id="6e138-165">(<a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)">Download a list of all settings synced</a>)</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-166">Microsoft Word 2013</span><span class="sxs-lookup"><span data-stu-id="6e138-166">Microsoft Word 2013</span></span></p>
<p><span data-ttu-id="6e138-167">Microsoft Excel 2013</span><span class="sxs-lookup"><span data-stu-id="6e138-167">Microsoft Excel 2013</span></span></p>
<p><span data-ttu-id="6e138-168">Microsoft Outlook 2013</span><span class="sxs-lookup"><span data-stu-id="6e138-168">Microsoft Outlook 2013</span></span></p>
<p><span data-ttu-id="6e138-169">Microsoft Access 2013</span><span class="sxs-lookup"><span data-stu-id="6e138-169">Microsoft Access 2013</span></span></p>
<p><span data-ttu-id="6e138-170">Microsoft Project 2013</span><span class="sxs-lookup"><span data-stu-id="6e138-170">Microsoft Project 2013</span></span></p>
<p><span data-ttu-id="6e138-171">Microsoft PowerPoint 2013</span><span class="sxs-lookup"><span data-stu-id="6e138-171">Microsoft PowerPoint 2013</span></span></p>
<p><span data-ttu-id="6e138-172">Microsoft Publisher 2013</span><span class="sxs-lookup"><span data-stu-id="6e138-172">Microsoft Publisher 2013</span></span></p>
<p><span data-ttu-id="6e138-173">Microsoft Visio 2013</span><span class="sxs-lookup"><span data-stu-id="6e138-173">Microsoft Visio 2013</span></span></p>
<p><span data-ttu-id="6e138-174">Microsoft InfoPath 2013</span><span class="sxs-lookup"><span data-stu-id="6e138-174">Microsoft InfoPath 2013</span></span></p>
<p><span data-ttu-id="6e138-175">Microsoft Lync 2013</span><span class="sxs-lookup"><span data-stu-id="6e138-175">Microsoft Lync 2013</span></span></p>
<p><span data-ttu-id="6e138-176">Microsoft OneNote 2013</span><span class="sxs-lookup"><span data-stu-id="6e138-176">Microsoft OneNote 2013</span></span></p>
<p><span data-ttu-id="6e138-177">Microsoft SharePoint Designer 2013</span><span class="sxs-lookup"><span data-stu-id="6e138-177">Microsoft SharePoint Designer 2013</span></span></p>
<p><span data-ttu-id="6e138-178">Microsoft Office 2013 上傳中心</span><span class="sxs-lookup"><span data-stu-id="6e138-178">Microsoft Office 2013 Upload Center</span></span></p>
<p><span data-ttu-id="6e138-179">Microsoft 商務用 OneDrive 2013</span><span class="sxs-lookup"><span data-stu-id="6e138-179">Microsoft OneDrive for Business 2013</span></span></p>
<p><span data-ttu-id="6e138-180">UE-V 2.1 和 2.1 SP1 Microsoft Office 2013 設定位置範本包括改良的 Outlook 簽名支援。</span><span class="sxs-lookup"><span data-stu-id="6e138-180">The UE-V 2.1 and 2.1 SP1 Microsoft Office 2013 settings location templates include improved Outlook signature support.</span></span> <span data-ttu-id="6e138-181">我們已新增新、回復和轉寄電子郵件的預設簽名設定同步處理。</span><span class="sxs-lookup"><span data-stu-id="6e138-181">We’ve added synchronization of default signature settings for new, reply, and forwarded emails.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="6e138-182">注意</span><span class="sxs-lookup"><span data-stu-id="6e138-182">Note</span></span></strong><br/><p><span data-ttu-id="6e138-183">您必須為使用者要同步處理其 Outlook 簽名的任何裝置建立 Outlook 設定檔。</span><span class="sxs-lookup"><span data-stu-id="6e138-183">An Outlook profile must be created for any device on which a user wants to sync their Outlook signature.</span></span> <span data-ttu-id="6e138-184">如果尚未建立設定檔，使用者可以建立一個，然後重新開機該裝置上的 Outlook，以啟用簽名同步處理。</span><span class="sxs-lookup"><span data-stu-id="6e138-184">If the profile is not already created, the user can create one and then restart Outlook on that device to enable signature synchronization.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6e138-185">瀏覽器選項： Internet Explorer 8、Internet Explorer 9、Internet Explorer 10 和 Internet Explorer 11</span><span class="sxs-lookup"><span data-stu-id="6e138-185">Browser options: Internet Explorer 8, Internet Explorer 9, Internet Explorer 10, and Internet Explorer 11</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-186">[我的最愛]、[首頁]、[定位點] 和工具列</span><span class="sxs-lookup"><span data-stu-id="6e138-186">Favorites, home page, tabs, and toolbars.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="6e138-187">注意</span><span class="sxs-lookup"><span data-stu-id="6e138-187">Note</span></span></strong><br/><p><span data-ttu-id="6e138-188">UE-V 不會漫遊 Internet Explorer cookie 的設定。</span><span class="sxs-lookup"><span data-stu-id="6e138-188">UE-V does not roam settings for Internet Explorer cookies.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6e138-189">Windows 附件</span><span class="sxs-lookup"><span data-stu-id="6e138-189">Windows accessories</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-190">Microsoft 計算機、記事本、寫字板。</span><span class="sxs-lookup"><span data-stu-id="6e138-190">Microsoft Calculator, Notepad, WordPad.</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="6e138-191">注意</span><span class="sxs-lookup"><span data-stu-id="6e138-191">Note</span></span>**  
<span data-ttu-id="6e138-192">UE-V 2.1 SP1 不會同步處理 Windows 10 中的 Microsoft 計算機與舊版作業系統中的 Microsoft 計算機之間的設定。</span><span class="sxs-lookup"><span data-stu-id="6e138-192">UE-V 2.1 SP1 does not synchronize settings between the Microsoft Calculator in Windows 10 and the Microsoft Calculator in previous operating systems.</span></span>



### <span data-ttu-id="6e138-193">UE-V 2.0 中預設同步處理的桌面應用程式</span><span class="sxs-lookup"><span data-stu-id="6e138-193">Desktop applications synchronized by default in UE-V 2.0</span></span>

<span data-ttu-id="6e138-194">當您安裝 UE-V 2.0 Agent 時，它會註冊一個預設的設定位置範本群組，以捕獲這些常見 Microsoft 應用程式的設定值。</span><span class="sxs-lookup"><span data-stu-id="6e138-194">When you install the UE-V 2.0 Agent, it registers a default group of settings location templates that capture settings values for these common Microsoft applications.</span></span>

**<span data-ttu-id="6e138-195">提示</span><span class="sxs-lookup"><span data-stu-id="6e138-195">Tip</span></span>**  
<span data-ttu-id="6e138-196">**Microsoft office 2013 設定同步**處理-在 Ue-v 2.0 中，預設不會包含 Office 2013 應用程式的設定位置範本，但可從[ue-v 範本庫](https://go.microsoft.com/fwlink/p/?LinkID=246589)下載。</span><span class="sxs-lookup"><span data-stu-id="6e138-196">**Microsoft Office 2013 Settings Synchronization** – In UE-V 2.0, a settings location template is not included by default for Office 2013 applications, but is available for download from the [UE-V template gallery](https://go.microsoft.com/fwlink/p/?LinkID=246589).</span></span> <span data-ttu-id="6e138-197">將[office 2013 與 ue-v 2.0 同步](synchronizing-office-2013-with-ue-v-20-both-uevv2.md)處理可提供同步處理 office 2013 設定之支援範本的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="6e138-197">[Synchronizing Office 2013 with UE-V 2.0](synchronizing-office-2013-with-ue-v-20-both-uevv2.md) provides details about the supported templates that synchronize Office 2013 settings.</span></span>



<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="6e138-198">應用程式類別</span><span class="sxs-lookup"><span data-stu-id="6e138-198">Application category</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="6e138-199">描述</span><span class="sxs-lookup"><span data-stu-id="6e138-199">Description</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6e138-200">Microsoft Office 2007 應用程式</span><span class="sxs-lookup"><span data-stu-id="6e138-200">Microsoft Office 2007 applications</span></span></p>
<p><span data-ttu-id="6e138-201">（ <a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)"> 下載所有設定已同步處理的清單 </a> ）</span><span class="sxs-lookup"><span data-stu-id="6e138-201">(<a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)">Download a list of all settings synced</a>)</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-202">Microsoft Access 2007</span><span class="sxs-lookup"><span data-stu-id="6e138-202">Microsoft Access 2007</span></span></p>
<p><span data-ttu-id="6e138-203">Microsoft Communicator 2007</span><span class="sxs-lookup"><span data-stu-id="6e138-203">Microsoft Communicator 2007</span></span></p>
<p><span data-ttu-id="6e138-204">Microsoft Excel 2007</span><span class="sxs-lookup"><span data-stu-id="6e138-204">Microsoft Excel 2007</span></span></p>
<p><span data-ttu-id="6e138-205">Microsoft InfoPath 2007</span><span class="sxs-lookup"><span data-stu-id="6e138-205">Microsoft InfoPath 2007</span></span></p>
<p><span data-ttu-id="6e138-206">Microsoft OneNote 2007</span><span class="sxs-lookup"><span data-stu-id="6e138-206">Microsoft OneNote 2007</span></span></p>
<p><span data-ttu-id="6e138-207">Microsoft Outlook 2007</span><span class="sxs-lookup"><span data-stu-id="6e138-207">Microsoft Outlook 2007</span></span></p>
<p><span data-ttu-id="6e138-208">Microsoft PowerPoint 2007</span><span class="sxs-lookup"><span data-stu-id="6e138-208">Microsoft PowerPoint 2007</span></span></p>
<p><span data-ttu-id="6e138-209">Microsoft Project 2007</span><span class="sxs-lookup"><span data-stu-id="6e138-209">Microsoft Project 2007</span></span></p>
<p><span data-ttu-id="6e138-210">Microsoft Publisher 2007</span><span class="sxs-lookup"><span data-stu-id="6e138-210">Microsoft Publisher 2007</span></span></p>
<p><span data-ttu-id="6e138-211">Microsoft SharePoint Designer 2007</span><span class="sxs-lookup"><span data-stu-id="6e138-211">Microsoft SharePoint Designer 2007</span></span></p>
<p><span data-ttu-id="6e138-212">Microsoft Visio 2007</span><span class="sxs-lookup"><span data-stu-id="6e138-212">Microsoft Visio 2007</span></span></p>
<p><span data-ttu-id="6e138-213">Microsoft Word 2007</span><span class="sxs-lookup"><span data-stu-id="6e138-213">Microsoft Word 2007</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6e138-214">Microsoft Office 2010 應用程式</span><span class="sxs-lookup"><span data-stu-id="6e138-214">Microsoft Office 2010 applications</span></span></p>
<p><span data-ttu-id="6e138-215">（ <a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)"> 下載所有設定已同步處理的清單 </a> ）</span><span class="sxs-lookup"><span data-stu-id="6e138-215">(<a href="https://www.microsoft.com/download/details.aspx?id=46367" data-raw-source="[Download a list of all settings synced](https://www.microsoft.com/download/details.aspx?id=46367)">Download a list of all settings synced</a>)</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-216">Microsoft Word 2010</span><span class="sxs-lookup"><span data-stu-id="6e138-216">Microsoft Word 2010</span></span></p>
<p><span data-ttu-id="6e138-217">Microsoft Excel 2010</span><span class="sxs-lookup"><span data-stu-id="6e138-217">Microsoft Excel 2010</span></span></p>
<p><span data-ttu-id="6e138-218">Microsoft Outlook 2010</span><span class="sxs-lookup"><span data-stu-id="6e138-218">Microsoft Outlook 2010</span></span></p>
<p><span data-ttu-id="6e138-219">Microsoft Access 2010</span><span class="sxs-lookup"><span data-stu-id="6e138-219">Microsoft Access 2010</span></span></p>
<p><span data-ttu-id="6e138-220">Microsoft Project 2010</span><span class="sxs-lookup"><span data-stu-id="6e138-220">Microsoft Project 2010</span></span></p>
<p><span data-ttu-id="6e138-221">Microsoft PowerPoint 2010</span><span class="sxs-lookup"><span data-stu-id="6e138-221">Microsoft PowerPoint 2010</span></span></p>
<p><span data-ttu-id="6e138-222">Microsoft Publisher 2010</span><span class="sxs-lookup"><span data-stu-id="6e138-222">Microsoft Publisher 2010</span></span></p>
<p><span data-ttu-id="6e138-223">Microsoft Visio 2010</span><span class="sxs-lookup"><span data-stu-id="6e138-223">Microsoft Visio 2010</span></span></p>
<p><span data-ttu-id="6e138-224">Microsoft SharePoint Workspace 2010</span><span class="sxs-lookup"><span data-stu-id="6e138-224">Microsoft SharePoint Workspace 2010</span></span></p>
<p><span data-ttu-id="6e138-225">Microsoft InfoPath 2010</span><span class="sxs-lookup"><span data-stu-id="6e138-225">Microsoft InfoPath 2010</span></span></p>
<p><span data-ttu-id="6e138-226">Microsoft Lync 2010</span><span class="sxs-lookup"><span data-stu-id="6e138-226">Microsoft Lync 2010</span></span></p>
<p><span data-ttu-id="6e138-227">Microsoft OneNote 2010</span><span class="sxs-lookup"><span data-stu-id="6e138-227">Microsoft OneNote 2010</span></span></p>
<p><span data-ttu-id="6e138-228">Microsoft SharePoint Designer 2010</span><span class="sxs-lookup"><span data-stu-id="6e138-228">Microsoft SharePoint Designer 2010</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6e138-229">瀏覽器選項： Internet Explorer 8、Internet Explorer 9 和 Internet Explorer 10</span><span class="sxs-lookup"><span data-stu-id="6e138-229">Browser options: Internet Explorer 8, Internet Explorer 9, and Internet Explorer 10</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-230">[我的最愛]、[首頁]、[定位點] 和工具列</span><span class="sxs-lookup"><span data-stu-id="6e138-230">Favorites, home page, tabs, and toolbars.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="6e138-231">注意</span><span class="sxs-lookup"><span data-stu-id="6e138-231">Note</span></span></strong><br/><p><span data-ttu-id="6e138-232">UE-V 不會漫遊 Internet Explorer cookie 的設定。</span><span class="sxs-lookup"><span data-stu-id="6e138-232">UE-V does not roam settings for Internet Explorer cookies.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6e138-233">Windows 附件</span><span class="sxs-lookup"><span data-stu-id="6e138-233">Windows accessories</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-234">Microsoft 計算機、記事本、寫字板。</span><span class="sxs-lookup"><span data-stu-id="6e138-234">Microsoft Calculator, Notepad, WordPad.</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="autosyncsettings2"></a><span data-ttu-id="6e138-235">Windows 設定預設會同步處理</span><span class="sxs-lookup"><span data-stu-id="6e138-235">Windows settings synchronized by default</span></span>

<span data-ttu-id="6e138-236">UE-V 包含設定位置範本，可捕獲這些 Windows 設定的設定值。</span><span class="sxs-lookup"><span data-stu-id="6e138-236">UE-V includes settings location templates that capture settings values for these Windows settings.</span></span>

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6e138-237">Windows 設定</span><span class="sxs-lookup"><span data-stu-id="6e138-237">Windows settings</span></span></th>
<th align="left"><span data-ttu-id="6e138-238">描述</span><span class="sxs-lookup"><span data-stu-id="6e138-238">Description</span></span></th>
<th align="left"><span data-ttu-id="6e138-239">適用</span><span class="sxs-lookup"><span data-stu-id="6e138-239">Apply on</span></span></th>
<th align="left"><span data-ttu-id="6e138-240">匯出開啟</span><span class="sxs-lookup"><span data-stu-id="6e138-240">Export on</span></span></th>
<th align="left"><span data-ttu-id="6e138-241">預設狀態</span><span class="sxs-lookup"><span data-stu-id="6e138-241">Default state</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6e138-242">桌面背景</span><span class="sxs-lookup"><span data-stu-id="6e138-242">Desktop background</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-243">目前使用中的桌面背景或牆紙。</span><span class="sxs-lookup"><span data-stu-id="6e138-243">Currently active desktop background or wallpaper.</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-244">登入、解除鎖定、遠端連線、排程任務事件。</span><span class="sxs-lookup"><span data-stu-id="6e138-244">Logon, unlock, remote connect, Scheduled Task events.</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-245">登出、鎖定、遠端中斷、使用者 <strong> 在 [公司設定中心] 中按一下 [立即同步處理] </strong> 或 [排程的任務間隔]</span><span class="sxs-lookup"><span data-stu-id="6e138-245">Logoff, lock, remote disconnect, user clicking <strong>Sync Now</strong> in Company Settings Center, or scheduled task interval</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-246">啟用</span><span class="sxs-lookup"><span data-stu-id="6e138-246">Enabled</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6e138-247">輕鬆存取</span><span class="sxs-lookup"><span data-stu-id="6e138-247">Ease of Access</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-248">協助工具和輸入設定、Microsoft 放大鏡、朗讀程式及螢幕小鍵盤。</span><span class="sxs-lookup"><span data-stu-id="6e138-248">Accessibility and input settings, Microsoft Magnifier, Narrator, and on-Screen Keyboard.</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-249">僅限登入。</span><span class="sxs-lookup"><span data-stu-id="6e138-249">Logon only.</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-250">登出、使用者按一下 [ <strong> 公司設定中心] 中的 [立即同步處理] </strong> 或 [排程的任務間隔]</span><span class="sxs-lookup"><span data-stu-id="6e138-250">Logoff, user clicking <strong>Sync Now</strong> in Company Settings Center, or scheduled task interval</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-251">啟用</span><span class="sxs-lookup"><span data-stu-id="6e138-251">Enabled</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6e138-252">桌面設定</span><span class="sxs-lookup"><span data-stu-id="6e138-252">Desktop settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-253">[開始] 功能表和工作列設定、[資料夾選項]、[預設桌面圖示]、[其他時鐘] 和 [地區及語言設定]。</span><span class="sxs-lookup"><span data-stu-id="6e138-253">Start menu and Taskbar settings, Folder options, Default desktop icons, Additional clocks, and Region and Language settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-254">僅限登入。</span><span class="sxs-lookup"><span data-stu-id="6e138-254">Logon only.</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-255">登出，使用者按一下 [ <strong> 公司設定中心] 中的 [立即同步處理] </strong> ，或 [排程] 任務</span><span class="sxs-lookup"><span data-stu-id="6e138-255">Logoff, user clicking <strong>Sync Now</strong> in Company Settings Center, or scheduled task</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-256">啟用</span><span class="sxs-lookup"><span data-stu-id="6e138-256">Enabled</span></span></p></td>
</tr>
</tbody>
</table>



**<span data-ttu-id="6e138-257">注意</span><span class="sxs-lookup"><span data-stu-id="6e138-257">Note</span></span>**  
<span data-ttu-id="6e138-258">從 Windows 8 開始，UE-V 不會漫遊與 [開始] 畫面相關的設定，例如 [專案] 和 [位置]。</span><span class="sxs-lookup"><span data-stu-id="6e138-258">Starting in Windows 8, UE-V does not roam settings related to the Start screen, such as items and locations.</span></span> <span data-ttu-id="6e138-259">此外，UE-V 不支援同步處理固定的工作列專案或 Windows 檔案快速鍵。</span><span class="sxs-lookup"><span data-stu-id="6e138-259">In addition, UE-V does not support synchronization of pinned taskbar items or Windows file shortcuts.</span></span>



**<span data-ttu-id="6e138-260">重要</span><span class="sxs-lookup"><span data-stu-id="6e138-260">Important</span></span>**  
<span data-ttu-id="6e138-261">UE-V 2.1 SP1 會在 Windows 10 裝置之間漫遊工作列設定。</span><span class="sxs-lookup"><span data-stu-id="6e138-261">UE-V 2.1 SP1 roams taskbar settings between Windows 10 devices.</span></span> <span data-ttu-id="6e138-262">不過，UE-V 不會在執行舊版作業系統的 Windows 10 裝置與裝置之間同步處理工作列設定。</span><span class="sxs-lookup"><span data-stu-id="6e138-262">However, UE-V does not synchronize taskbar settings between Windows 10 devices and devices running previous operating systems.</span></span>



<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6e138-263">設定群組</span><span class="sxs-lookup"><span data-stu-id="6e138-263">Settings group</span></span></th>
<th align="left"><span data-ttu-id="6e138-264">類別</span><span class="sxs-lookup"><span data-stu-id="6e138-264">Category</span></span></th>
<th align="left"><span data-ttu-id="6e138-265">奪取</span><span class="sxs-lookup"><span data-stu-id="6e138-265">Capture</span></span></th>
<th align="left"><span data-ttu-id="6e138-266">[套用]</span><span class="sxs-lookup"><span data-stu-id="6e138-266">Apply</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="6e138-267">應用程式設定</span><span class="sxs-lookup"><span data-stu-id="6e138-267">Application Settings</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="6e138-268">Windows 應用程式</span><span class="sxs-lookup"><span data-stu-id="6e138-268">Windows apps</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-269">關閉應用程式</span><span class="sxs-lookup"><span data-stu-id="6e138-269">Close app</span></span></p>
<p><span data-ttu-id="6e138-270">Windows 應用程式設定變更事件</span><span class="sxs-lookup"><span data-stu-id="6e138-270">Windows app settings change event</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-271">啟動時啟動 UE-V 應用程式監視器</span><span class="sxs-lookup"><span data-stu-id="6e138-271">Start the UE-V App Monitor at startup</span></span></p>
<p><span data-ttu-id="6e138-272">開啟 app</span><span class="sxs-lookup"><span data-stu-id="6e138-272">Open app</span></span></p>
<p><span data-ttu-id="6e138-273">Windows 應用程式設定變更事件</span><span class="sxs-lookup"><span data-stu-id="6e138-273">Windows App Settings change event</span></span></p>
<p><span data-ttu-id="6e138-274">已到達設定套件</span><span class="sxs-lookup"><span data-stu-id="6e138-274">Arrival of a settings package</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="6e138-275">傳統型應用程式</span><span class="sxs-lookup"><span data-stu-id="6e138-275">Desktop applications</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-276">應用程式關閉</span><span class="sxs-lookup"><span data-stu-id="6e138-276">Application closes</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-277">應用程式隨即開啟和關閉</span><span class="sxs-lookup"><span data-stu-id="6e138-277">Application opens and closes</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="6e138-278">桌面設定</span><span class="sxs-lookup"><span data-stu-id="6e138-278">Desktop settings</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="6e138-279">桌面背景</span><span class="sxs-lookup"><span data-stu-id="6e138-279">Desktop background</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-280">鎖定或登出</span><span class="sxs-lookup"><span data-stu-id="6e138-280">Lock or logoff</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-281">[登入]、[解除鎖定]、[遠端連線]、[新套件到貨] 的通知、[ <strong> </strong> 在公司設定中心立即同步處理] 或 [排程的工作]</span><span class="sxs-lookup"><span data-stu-id="6e138-281">Logon, unlock, remote connect, notification of new package arrival, user clicks <strong>Sync Now</strong> in Company Settings Center, or scheduled task runs.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="6e138-282">輕鬆存取（一般-協助工具、朗讀程式、放大鏡、螢幕小鍵盤）</span><span class="sxs-lookup"><span data-stu-id="6e138-282">Ease of Access (Common – Accessibility, Narrator, Magnifier, On-Screen-Keyboard)</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-283">鎖定或登出</span><span class="sxs-lookup"><span data-stu-id="6e138-283">Lock or Logoff</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-284">標識</span><span class="sxs-lookup"><span data-stu-id="6e138-284">Logon</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="6e138-285">輕鬆存取（Shell-音訊、協助工具、鍵盤、滑鼠）</span><span class="sxs-lookup"><span data-stu-id="6e138-285">Ease of Access (Shell - Audio, Accessibility, Keyboard, Mouse)</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-286">鎖定或登出</span><span class="sxs-lookup"><span data-stu-id="6e138-286">Lock or logoff</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-287">登入、解除鎖定、遠端連線、新套件到貨的通知、使用者按一下 [ <strong> 公司設定中心] 中的 [立即同步處理] </strong> 或 [排程任務執行]</span><span class="sxs-lookup"><span data-stu-id="6e138-287">Logon, unlock, remote connect, notification of new package arrival, user clicks <strong>Sync Now</strong> in Company Settings Center, or scheduled task runs</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="6e138-288">桌面設定</span><span class="sxs-lookup"><span data-stu-id="6e138-288">Desktop settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-289">鎖定或登出</span><span class="sxs-lookup"><span data-stu-id="6e138-289">Lock or logoff</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-290">標識</span><span class="sxs-lookup"><span data-stu-id="6e138-290">Logon</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="6e138-291">UE-V-對 Windows 應用程式的支援</span><span class="sxs-lookup"><span data-stu-id="6e138-291">UE-V-support for Windows Apps</span></span>

<span data-ttu-id="6e138-292">如果是 Windows 應用程式，應用程式開發人員會指定同步處理的設定。</span><span class="sxs-lookup"><span data-stu-id="6e138-292">For Windows apps, the app developer specifies the settings that are synchronized.</span></span> <span data-ttu-id="6e138-293">您可以指定哪些 Windows 應用程式已啟用設定同步處理。</span><span class="sxs-lookup"><span data-stu-id="6e138-293">You can specify which Windows apps are enabled for settings synchronization.</span></span>

<span data-ttu-id="6e138-294">若要在 Windows PowerShell 命令提示字元上顯示可同步處理電腦設定的 Windows app 清單，以及其套件系列名稱、啟用狀態，以及已啟用的來源，請輸入：</span><span class="sxs-lookup"><span data-stu-id="6e138-294">To display a list of Windows apps that can synchronize settings on a computer with their package family name, enabled status, and enabled source, at a Windows PowerShell command prompt, enter:</span></span> `Get-UevAppxPackage`

**<span data-ttu-id="6e138-295">注意</span><span class="sxs-lookup"><span data-stu-id="6e138-295">Note</span></span>**  
<span data-ttu-id="6e138-296">從 Windows 8 開始，如果網域使用者將登入認證連結到其 Microsoft 帳戶，UE-V 就不會同步處理 Windows 應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="6e138-296">As of Windows 8, UE-V does not synchronize Windows app settings if the domain user links their sign-in credentials to their Microsoft Account.</span></span> <span data-ttu-id="6e138-297">此連結會將設定同步處理到 Microsoft OneDrive，以讓 UE-V 停用 Windows 應用程式設定的同步處理。</span><span class="sxs-lookup"><span data-stu-id="6e138-297">This linking synchronizes settings to Microsoft OneDrive so UE-V, which disables synchronization of Windows app settings.</span></span>



### <span data-ttu-id="6e138-298">UE-V-對漫遊印表機的支援</span><span class="sxs-lookup"><span data-stu-id="6e138-298">UE-V-support for Roaming Printers</span></span>

<span data-ttu-id="6e138-299">UE-V 2.1 SP1 可讓網路印表機在裝置之間漫遊，讓使用者在登入網路上的任何裝置時都能存取其網路印表機。</span><span class="sxs-lookup"><span data-stu-id="6e138-299">UE-V 2.1 SP1 lets network printers roam between devices so that a user has access to their network printers when logged on to any device on the network.</span></span> <span data-ttu-id="6e138-300">這包括將其設為預設值的印表機漫遊。</span><span class="sxs-lookup"><span data-stu-id="6e138-300">This includes roaming the printer that they set as the default.</span></span>

<span data-ttu-id="6e138-301">UE-V 中的印表機漫遊需要下列其中一種情況：</span><span class="sxs-lookup"><span data-stu-id="6e138-301">Printer roaming in UE-V requires one of these scenarios:</span></span>

-   <span data-ttu-id="6e138-302">列印伺服器可以在漫遊至新裝置時下載所需的驅動程式。</span><span class="sxs-lookup"><span data-stu-id="6e138-302">The print server can download the required driver when it roams to a new device.</span></span>

-   <span data-ttu-id="6e138-303">漫遊網路印表機的驅動程式已預先安裝在任何需要存取該網路印表機的裝置上。</span><span class="sxs-lookup"><span data-stu-id="6e138-303">The driver for the roaming network printer is pre-installed on any device that needs to access that network printer.</span></span>

-   <span data-ttu-id="6e138-304">您可以從 Windows Update 取得印表機驅動程式。</span><span class="sxs-lookup"><span data-stu-id="6e138-304">The printer driver can be obtained from Windows Update.</span></span>

**<span data-ttu-id="6e138-305">注意</span><span class="sxs-lookup"><span data-stu-id="6e138-305">Note</span></span>**  
<span data-ttu-id="6e138-306">UE-V 印表機漫遊**功能不會漫遊印表機**設定或喜好設定，例如雙面列印。</span><span class="sxs-lookup"><span data-stu-id="6e138-306">The UE-V printer roaming feature does **not** roam printer settings or preferences, such as printing double-sided.</span></span>



### <a href="" id="determinesettingssync"></a><span data-ttu-id="6e138-307">判斷您是否需要同步處理其他應用程式的設定</span><span class="sxs-lookup"><span data-stu-id="6e138-307">Determine whether you need settings synchronized for other applications</span></span>

<span data-ttu-id="6e138-308">在您已複習在 UE-V 部署中自動同步處理的設定之後，您想要決定是否要同步處理其他應用程式的設定，因為這會決定您在整個企業中部署 UE-V 的方式。</span><span class="sxs-lookup"><span data-stu-id="6e138-308">After you have reviewed the settings that are synchronized automatically in a UE-V deployment, you want to decide whether you will synchronize settings for other applications since this determines how you deploy UE-V throughout your enterprise.</span></span>

<span data-ttu-id="6e138-309">如果您是系統管理員，當您認為要在 UE-V 解決方案中包含哪些桌面應用程式時，請考慮哪些設定可由使用者自訂，以及應用程式儲存其設定的方式和位置。</span><span class="sxs-lookup"><span data-stu-id="6e138-309">As an administrator, when you consider which desktop applications to include in your UE-V solution, consider which settings can be customized by users, and how and where the application stores its settings.</span></span> <span data-ttu-id="6e138-310">並非所有的桌面應用程式都有可自訂或經常由使用者自訂的設定。</span><span class="sxs-lookup"><span data-stu-id="6e138-310">Not all desktop applications have settings that can be customized or that are routinely customized by users.</span></span> <span data-ttu-id="6e138-311">此外，並非所有桌面應用程式設定都能安全地跨多個電腦或環境進行同步處理。</span><span class="sxs-lookup"><span data-stu-id="6e138-311">In addition, not all desktop applications settings can safely be synchronized across multiple computers or environments.</span></span>

<span data-ttu-id="6e138-312">一般來說，您可以同步處理符合下列準則的設定：</span><span class="sxs-lookup"><span data-stu-id="6e138-312">In general, you can synchronize settings that meet the following criteria:</span></span>

-   <span data-ttu-id="6e138-313">儲存在使用者可存取位置的設定。</span><span class="sxs-lookup"><span data-stu-id="6e138-313">Settings that are stored in user-accessible locations.</span></span> <span data-ttu-id="6e138-314">例如，請勿同步處理儲存在 System32 或 HKEY \ _CURRENT \ _USER （HKCU）區段的設定。</span><span class="sxs-lookup"><span data-stu-id="6e138-314">For example, do not synchronize settings that are stored in System32 or outside the HKEY\_CURRENT\_USER (HKCU) section of the registry.</span></span>

-   <span data-ttu-id="6e138-315">特定電腦不專用的設定。</span><span class="sxs-lookup"><span data-stu-id="6e138-315">Settings that are not specific to the particular computer.</span></span> <span data-ttu-id="6e138-316">例如，排除網路或硬體設定。</span><span class="sxs-lookup"><span data-stu-id="6e138-316">For example, exclude network or hardware configurations.</span></span>

-   <span data-ttu-id="6e138-317">可以在電腦之間同步處理的設定，不會造成資料損毀的風險。</span><span class="sxs-lookup"><span data-stu-id="6e138-317">Settings that can be synchronized between computers without risk of corrupted data.</span></span> <span data-ttu-id="6e138-318">例如，請勿使用儲存在資料庫檔案中的設定。</span><span class="sxs-lookup"><span data-stu-id="6e138-318">For example, do not use settings that are stored in a database file.</span></span>

### <a href="" id="checklistsettingssync"></a><span data-ttu-id="6e138-319">評估自訂應用程式的檢查清單</span><span class="sxs-lookup"><span data-stu-id="6e138-319">Checklist for evaluating custom applications</span></span>

<span data-ttu-id="6e138-320">如果您已決定您需要同步處理其他應用程式的設定，您可以使用這個檢查清單來協助找出您要包含哪些應用程式。</span><span class="sxs-lookup"><span data-stu-id="6e138-320">If you’ve decided that you need settings synchronized for other applications, you can use this checklist to help figure out which applications you’ll include.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left"><span data-ttu-id="6e138-321">描述</span><span class="sxs-lookup"><span data-stu-id="6e138-321">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="6e138-322">此應用程式是否包含使用者可自訂的設定？</span><span class="sxs-lookup"><span data-stu-id="6e138-322">Does this application contain settings that the user can customize?</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="6e138-323">對使用者來說，這些設定是否已同步處理是很重要的？</span><span class="sxs-lookup"><span data-stu-id="6e138-323">Is it important for the user that these settings are synchronized?</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="6e138-324">這些使用者設定已經由應用程式管理或設定原則方案所管理嗎？</span><span class="sxs-lookup"><span data-stu-id="6e138-324">Are these user settings already managed by an application management or settings policy solution?</span></span> <span data-ttu-id="6e138-325">在登入、解除鎖定或遠端連線事件時，UE-V 會在應用程式啟動和 Windows 設定中套用應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="6e138-325">UE-V applies application settings at application startup and Windows settings at logon, unlock, or remote connect events.</span></span> <span data-ttu-id="6e138-326">如果您將 UE-V 與其他設定共用解決方案搭配使用，使用者可能會在同步處理設定中遇到不一致的問題。</span><span class="sxs-lookup"><span data-stu-id="6e138-326">If you use UE-V with other settings sharing solutions, users might experience inconsistency across synchronized settings.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="6e138-327">電腦是否有特定的應用程式設定？</span><span class="sxs-lookup"><span data-stu-id="6e138-327">Are the application settings specific to the computer?</span></span> <span data-ttu-id="6e138-328">與硬體或特定電腦設定相關聯的應用程式喜好設定和自訂，不會持續同步處理多個會話，而且可能會造成應用程式經驗不佳。</span><span class="sxs-lookup"><span data-stu-id="6e138-328">Application preferences and customizations that are associated with hardware or specific computer configurations do not consistently synchronize across sessions and can cause a poor application experience.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="6e138-329">[應用程式檔案] 目錄或位於 [使用者名稱] 的檔案目錄中的 [應用程式 <strong> 儲存 </strong> ] 設定 [ &lt; 強 &gt; AppData </strong> &lt; 強 &gt; LocalLow] </strong> 目錄？</span><span class="sxs-lookup"><span data-stu-id="6e138-329">Does the application store settings in the Program Files directory or in the file directory that is located in the <strong>Users</strong>[User name]&lt;strong&gt;AppData</strong>&lt;strong&gt;LocalLow</strong> directory?</span></span> <span data-ttu-id="6e138-330">儲存在上述任一位置的應用程式資料通常不應與使用者進行同步處理，因為這項資料是針對電腦所特有的，或因為資料太大而無法進行同步處理。</span><span class="sxs-lookup"><span data-stu-id="6e138-330">Application data that is stored in either of these locations usually should not synchronize with the user, because this data is specific to the computer or because the data is too large to synchronize.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="6e138-331">應用程式會將任何設定儲存在檔案中，包含不應該同步處理的其他應用程式資料？</span><span class="sxs-lookup"><span data-stu-id="6e138-331">Does the application store any settings in a file that contains other application data that should not synchronize?</span></span> <span data-ttu-id="6e138-332">UE-V 會將檔案同步處理為單一單元。</span><span class="sxs-lookup"><span data-stu-id="6e138-332">UE-V synchronizes files as a single unit.</span></span> <span data-ttu-id="6e138-333">如果設定儲存在包括 [設定] 以外的應用程式資料的檔案中，則同步處理這項額外的資料可能會造成不佳的應用程式體驗。</span><span class="sxs-lookup"><span data-stu-id="6e138-333">If settings are stored in files that include application data other than settings, then synchronizing this additional data can cause a poor application experience.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><img src="images/checklistbox.gif" alt="Checklist box" /></td>
<td align="left"><p><span data-ttu-id="6e138-334">包含這些設定的檔案有多大？</span><span class="sxs-lookup"><span data-stu-id="6e138-334">How large are the files that contain the settings?</span></span> <span data-ttu-id="6e138-335">較大的檔案可能會影響設定同步處理的效能。</span><span class="sxs-lookup"><span data-stu-id="6e138-335">The performance of the settings synchronization can be affected by large files.</span></span> <span data-ttu-id="6e138-336">包括大型檔案會影響設定同步處理的效能。</span><span class="sxs-lookup"><span data-stu-id="6e138-336">Including large files can affect the performance of settings synchronization.</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="considerations"></a><span data-ttu-id="6e138-337">準備 UE-V 部署時的其他考慮事項</span><span class="sxs-lookup"><span data-stu-id="6e138-337">Other Considerations when Preparing a UE-V Deployment</span></span>


<span data-ttu-id="6e138-338">當您準備好要部署 UE-V 時，您也應該考慮下列事項：</span><span class="sxs-lookup"><span data-stu-id="6e138-338">You should also consider these things when you are preparing to deploy UE-V:</span></span>

-   [<span data-ttu-id="6e138-339">管理認證同步處理</span><span class="sxs-lookup"><span data-stu-id="6e138-339">Managing credentials synchronization</span></span>](#creds)

-   [<span data-ttu-id="6e138-340">Windows 應用程式設定同步處理</span><span class="sxs-lookup"><span data-stu-id="6e138-340">Windows app settings synchronization</span></span>](#appxsettings)

-   [<span data-ttu-id="6e138-341">自訂 UE-V 設定位置範本</span><span class="sxs-lookup"><span data-stu-id="6e138-341">Custom UE-V settings location templates</span></span>](#custom)

-   [<span data-ttu-id="6e138-342">無意間的使用者設定設定</span><span class="sxs-lookup"><span data-stu-id="6e138-342">Unintentional user settings configurations</span></span>](#prevent)

-   [<span data-ttu-id="6e138-343">效能與容量</span><span class="sxs-lookup"><span data-stu-id="6e138-343">Performance and capacity</span></span>](#capacity)

-   [<span data-ttu-id="6e138-344">高可用性</span><span class="sxs-lookup"><span data-stu-id="6e138-344">High availability</span></span>](#high)

-   [<span data-ttu-id="6e138-345">電腦時鐘同步處理</span><span class="sxs-lookup"><span data-stu-id="6e138-345">Computer clock synchronization</span></span>](#clocksync)

### <a href="" id="creds"></a><span data-ttu-id="6e138-346">在 UE-V 2.1 和 UE-V 2.1 SP1 中管理認證同步處理</span><span class="sxs-lookup"><span data-stu-id="6e138-346">Managing credentials synchronization in UE-V 2.1 and UE-V 2.1 SP1</span></span>

<span data-ttu-id="6e138-347">許多企業應用程式（包括 Microsoft Outlook 和 Lync）會在登入時提示使用者輸入其網域認證。</span><span class="sxs-lookup"><span data-stu-id="6e138-347">Many enterprise applications, including Microsoft Outlook and Lync, prompt users for their domain credentials at login.</span></span> <span data-ttu-id="6e138-348">使用者可以選擇將其認證儲存至磁片，避免在每次開啟這些應用程式時都必須輸入它們。</span><span class="sxs-lookup"><span data-stu-id="6e138-348">Users have the option of saving their credentials to disk to prevent having to enter them every time they open these applications.</span></span> <span data-ttu-id="6e138-349">啟用漫遊認證同步處理可讓使用者在一部電腦上儲存其認證，避免在他們在其環境中所使用的每一部電腦上重新輸入。</span><span class="sxs-lookup"><span data-stu-id="6e138-349">Enabling roaming credentials synchronization lets users save their credentials on one computer and avoid re-entering them on every computer they use in their environment.</span></span> <span data-ttu-id="6e138-350">使用者可以將部分網域認證與 UE-V 2.1 和 2.1 SP1 同步處理。</span><span class="sxs-lookup"><span data-stu-id="6e138-350">Users can synchronize some domain credentials with UE-V 2.1 and 2.1 SP1.</span></span>

**<span data-ttu-id="6e138-351">重要</span><span class="sxs-lookup"><span data-stu-id="6e138-351">Important</span></span>**  
<span data-ttu-id="6e138-352">認證同步處理預設為停用。</span><span class="sxs-lookup"><span data-stu-id="6e138-352">Credentials synchronization is disabled by default.</span></span> <span data-ttu-id="6e138-353">在部署期間，您必須明確啟用認證同步處理，才能執行這項功能。</span><span class="sxs-lookup"><span data-stu-id="6e138-353">You must explicitly enable credentials synchronization during deployment to implement this feature.</span></span>



<span data-ttu-id="6e138-354">UE-V 2.1 和 2.1 SP1 可以同步處理企業認證，但不會漫遊認證僅供在本機電腦上使用。</span><span class="sxs-lookup"><span data-stu-id="6e138-354">UE-V 2.1 and 2.1 SP1 can synchronize enterprise credentials, but do not roam credentials intended only for use on the local computer.</span></span>

<span data-ttu-id="6e138-355">認證是同步處理設定，這表示在 UE-V 同步處理之後，第一次登入您的電腦時，會將它們套用到您的個人檔案。</span><span class="sxs-lookup"><span data-stu-id="6e138-355">Credentials are synchronous settings, meaning they are applied to your profile the first time you log in to your computer after UE-V synchronizes.</span></span>

<span data-ttu-id="6e138-356">認證同步處理是由它自己的設定位置範本所管理，預設為停用。</span><span class="sxs-lookup"><span data-stu-id="6e138-356">Credentials synchronization is managed by its own settings location template, which is disabled by default.</span></span> <span data-ttu-id="6e138-357">您可以透過其他範本所用的相同方法來啟用或停用此範本。</span><span class="sxs-lookup"><span data-stu-id="6e138-357">You can enable or disable this template through the same methods used for other templates.</span></span> <span data-ttu-id="6e138-358">此功能的範本識別碼是 RoamingCredentialSettings。</span><span class="sxs-lookup"><span data-stu-id="6e138-358">The template identifier for this feature is RoamingCredentialSettings.</span></span>

**<span data-ttu-id="6e138-359">重要</span><span class="sxs-lookup"><span data-stu-id="6e138-359">Important</span></span>**  
<span data-ttu-id="6e138-360">如果您在您的環境中使用 Active Directory 認證漫遊，我們建議您不要啟用 UE-V 認證漫遊範本。</span><span class="sxs-lookup"><span data-stu-id="6e138-360">If you are using Active Directory Credential Roaming in your environment, we recommend that you don’t enable the UE-V credential roaming template.</span></span>



<span data-ttu-id="6e138-361">使用下列其中一種方法來啟用認證同步處理：</span><span class="sxs-lookup"><span data-stu-id="6e138-361">Use one of these methods to enable credentials synchronization:</span></span>

-   <span data-ttu-id="6e138-362">公司設定中心</span><span class="sxs-lookup"><span data-stu-id="6e138-362">Company Settings Center</span></span>

-   <span data-ttu-id="6e138-363">PowerShell</span><span class="sxs-lookup"><span data-stu-id="6e138-363">PowerShell</span></span>

-   <span data-ttu-id="6e138-364">群組原則</span><span class="sxs-lookup"><span data-stu-id="6e138-364">Group Policy</span></span>

**<span data-ttu-id="6e138-365">注意</span><span class="sxs-lookup"><span data-stu-id="6e138-365">Note</span></span>**  
<span data-ttu-id="6e138-366">認證會在同步處理期間進行加密。</span><span class="sxs-lookup"><span data-stu-id="6e138-366">Credentials are encrypted during synchronization.</span></span>



<span data-ttu-id="6e138-367">[[公司設定中心](https://technet.microsoft.com/library/dn458903.aspx)]**：** 核取 [Windows 設定] 下的 [漫遊認證設定] 核取方塊，以啟用認證同步處理。</span><span class="sxs-lookup"><span data-stu-id="6e138-367">[Company Settings Center](https://technet.microsoft.com/library/dn458903.aspx)**:** Check the Roaming Credential Settings check box under Windows Settings to enable credential synchronization.</span></span> <span data-ttu-id="6e138-368">取消核取核取方塊以停用它。</span><span class="sxs-lookup"><span data-stu-id="6e138-368">Uncheck the box to disable it.</span></span> <span data-ttu-id="6e138-369">如果您的帳戶未設定為使用 Microsoft 帳戶同步處理設定，此核取方塊只會出現在 [公司設定中心] 中。</span><span class="sxs-lookup"><span data-stu-id="6e138-369">This check box only appears in Company Settings Center if your account is not configured to synchronize settings using a Microsoft Account.</span></span>

<span data-ttu-id="6e138-370">[Powershell](https://technet.microsoft.com/library/dn458937.aspx)**：** 此 PowerShell Cmdlet 可啟用認證同步處理：</span><span class="sxs-lookup"><span data-stu-id="6e138-370">[PowerShell](https://technet.microsoft.com/library/dn458937.aspx)**:** This PowerShell cmdlet enables credential synchronization:</span></span>

``` syntax
Enable-UevTemplate RoamingCredentialSettings
```

<span data-ttu-id="6e138-371">此 PowerShell Cmdlet 會停用認證同步處理：</span><span class="sxs-lookup"><span data-stu-id="6e138-371">This PowerShell cmdlet disables credential synchronization:</span></span>

``` syntax
Disable-UevTemplate RoamingCredentialSettings
```

<span data-ttu-id="6e138-372">[群組原則](https://technet.microsoft.com/library/dn458893.aspx)**：** 您必須[部署最新的 MDOP ADMX 範本](https://go.microsoft.com/fwlink/p/?LinkId=393944)，才能透過群組原則啟用憑證同步處理。</span><span class="sxs-lookup"><span data-stu-id="6e138-372">[Group Policy](https://technet.microsoft.com/library/dn458893.aspx)**:** You must [deploy the latest MDOP ADMX template](https://go.microsoft.com/fwlink/p/?LinkId=393944) to enable credential synchronization through group policy.</span></span> <span data-ttu-id="6e138-373">認證同步處理是使用 Windows 設定來管理。</span><span class="sxs-lookup"><span data-stu-id="6e138-373">Credentials synchronization is managed with the Windows settings.</span></span> <span data-ttu-id="6e138-374">若要使用群組原則管理這項功能，請啟用 [同步處理 Windows 設定] 原則。</span><span class="sxs-lookup"><span data-stu-id="6e138-374">To manage this feature with Group Policy, enable the Synchronize Windows settings policy.</span></span>

1.  <span data-ttu-id="6e138-375">開啟 [群組原則編輯器]，然後流覽至 [使用者設定]-[系統**管理範本]-Windows 元件-Microsoft 使用者體驗虛擬化**。</span><span class="sxs-lookup"><span data-stu-id="6e138-375">Open Group Policy Editor and navigate to **User Configuration – Administrative Templates – Windows Components – Microsoft User Experience Virtualization**.</span></span>

2.  <span data-ttu-id="6e138-376">按兩下 [**同步處理 Windows 設定**]。</span><span class="sxs-lookup"><span data-stu-id="6e138-376">Double-click on **Synchronize Windows settings**.</span></span>

3.  <span data-ttu-id="6e138-377">如果啟用此原則，您可以核取 [**漫遊認證**] 核取方塊，或 [停用認證同步處理] 來啟用認證同步處理。</span><span class="sxs-lookup"><span data-stu-id="6e138-377">If this policy is enabled, you can enable credentials synchronization by checking the **Roaming Credentials** check box, or disable credentials synchronization by unchecking it.</span></span>

4.  <span data-ttu-id="6e138-378">按一下 \[確定\] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="6e138-378">Click **OK**.</span></span>

### <span data-ttu-id="6e138-379">由 UE-V 同步處理認證位置</span><span class="sxs-lookup"><span data-stu-id="6e138-379">Credential locations synchronized by UE-V</span></span>

<span data-ttu-id="6e138-380">應用程式儲存在下列位置的認證檔案是已同步處理：</span><span class="sxs-lookup"><span data-stu-id="6e138-380">Credential files saved by applications into the following locations are synchronized:</span></span>

-   <span data-ttu-id="6e138-381">%UserProfile%\\AppData\\Roaming\\Microsoft\\Credentials</span><span class="sxs-lookup"><span data-stu-id="6e138-381">%UserProfile%\\AppData\\Roaming\\Microsoft\\Credentials</span></span>\\

-   <span data-ttu-id="6e138-382">%UserProfile%\\AppData\\Roaming\\Microsoft\\Crypto</span><span class="sxs-lookup"><span data-stu-id="6e138-382">%UserProfile%\\AppData\\Roaming\\Microsoft\\Crypto</span></span>\\

-   <span data-ttu-id="6e138-383">%UserProfile%\\AppData\\Roaming\\Microsoft\\Protect</span><span class="sxs-lookup"><span data-stu-id="6e138-383">%UserProfile%\\AppData\\Roaming\\Microsoft\\Protect</span></span>\\

-   <span data-ttu-id="6e138-384">%UserProfile%\\AppData\\Roaming\\Microsoft\\SystemCertificates</span><span class="sxs-lookup"><span data-stu-id="6e138-384">%UserProfile%\\AppData\\Roaming\\Microsoft\\SystemCertificates</span></span>\\

<span data-ttu-id="6e138-385">儲存在其他位置的認證不會透過 UE-V 進行同步處理。</span><span class="sxs-lookup"><span data-stu-id="6e138-385">Credentials saved to other locations are not synchronized by UE-V.</span></span>

### <a href="" id="appxsettings"></a><span data-ttu-id="6e138-386">Windows 應用程式設定同步處理</span><span class="sxs-lookup"><span data-stu-id="6e138-386">Windows app settings synchronization</span></span>

<span data-ttu-id="6e138-387">UE-V 會以三種方式管理 Windows 應用程式設定同步處理：</span><span class="sxs-lookup"><span data-stu-id="6e138-387">UE-V manages Windows app settings synchronization in three ways:</span></span>

-   <span data-ttu-id="6e138-388">**同步處理 Windows 應用程式：** 允許或拒絕任何 Windows 應用程式同步處理</span><span class="sxs-lookup"><span data-stu-id="6e138-388">**Sync Windows Apps:** Allow or deny any Windows app synchronization</span></span>

-   <span data-ttu-id="6e138-389">**Windows 應用程式清單：** 同步處理 Windows 應用程式清單</span><span class="sxs-lookup"><span data-stu-id="6e138-389">**Windows App List:** Synchronize a list of Windows apps</span></span>

-   <span data-ttu-id="6e138-390">未**列出的預設同步處理行為：** 判斷 windows 應用程式清單以外的 Windows 應用程式的同步處理行為。</span><span class="sxs-lookup"><span data-stu-id="6e138-390">**Unlisted Default Sync Behavior:** Determine the synchronization behavior of Windows apps that are not in the Windows app list.</span></span>

<span data-ttu-id="6e138-391">如需詳細資訊，請參閱[Windows 應用程式清單](https://technet.microsoft.com/library/dn458925.aspx#win8applist)。</span><span class="sxs-lookup"><span data-stu-id="6e138-391">For more information, see the [Windows App List](https://technet.microsoft.com/library/dn458925.aspx#win8applist).</span></span>

### <a href="" id="custom"></a><span data-ttu-id="6e138-392">自訂 UE-V 設定位置範本</span><span class="sxs-lookup"><span data-stu-id="6e138-392">Custom UE-V settings location templates</span></span>

<span data-ttu-id="6e138-393">如果您要部署 UE-V 來同步處理自訂應用程式的設定，您將會使用 UE-V 發生器來為這些桌面應用程式建立自訂設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="6e138-393">If you are deploying UE-V to synchronize settings for custom applications, you will use the UE-V Generator to create custom settings location templates for those desktop applications.</span></span> <span data-ttu-id="6e138-394">在測試環境中建立並測試自訂設定位置範本之後，您可以將設定位置範本部署到企業中的電腦。</span><span class="sxs-lookup"><span data-stu-id="6e138-394">After you create and test a custom settings location template in a test environment, you can deploy the settings location templates to computers in the enterprise.</span></span>

<span data-ttu-id="6e138-395">自訂設定位置範本必須使用現有的部署基礎結構（例如系統中心建構管理員、含喜好設定，或設定 UE-V 設定範本目錄）來部署。</span><span class="sxs-lookup"><span data-stu-id="6e138-395">Custom settings location templates must be deployed with an existing deployment infrastructure, like an enterprise software distribution (ESD) method such as System Center Configuration Manager, with preferences, or by configuring an UE-V settings template catalog.</span></span> <span data-ttu-id="6e138-396">您必須使用 UE-V WMI 或 Windows PowerShell 來註冊使用 Configuration Manager 或群組原則部署的範本。</span><span class="sxs-lookup"><span data-stu-id="6e138-396">Templates that are deployed with Configuration Manager or Group Policy must be registered by using UE-V WMI or Windows PowerShell.</span></span>

<span data-ttu-id="6e138-397">如需自訂設定位置範本的詳細資訊，請參閱[針對自訂應用程式部署 ue-v 2.](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)</span><span class="sxs-lookup"><span data-stu-id="6e138-397">For more information about custom settings location templates, see [Deploy UE-V 2.x for Custom Applications](deploy-ue-v-2x-for-custom-applications-new-uevv2.md).</span></span> <span data-ttu-id="6e138-398">如需使用 UE-V 與 Configuration Manager 的詳細資訊，請參閱[使用 System Center Configuration manager 2012 設定 ue-v 2. x](configuring-ue-v-2x-with-system-center-configuration-manager-2012-both-uevv2.md)。</span><span class="sxs-lookup"><span data-stu-id="6e138-398">For more information about using UE-V with Configuration Manager, see [Configuring UE-V 2.x with System Center Configuration Manager 2012](configuring-ue-v-2x-with-system-center-configuration-manager-2012-both-uevv2.md).</span></span>

### <a href="" id="prevent"></a><span data-ttu-id="6e138-399">防止無意間的使用者設定設定</span><span class="sxs-lookup"><span data-stu-id="6e138-399">Prevent unintentional user settings configuration</span></span>

<span data-ttu-id="6e138-400">UE-V 會從設定儲存位置下載新的使用者設定資訊，並將設定套用到本機電腦的下列情況：</span><span class="sxs-lookup"><span data-stu-id="6e138-400">UE-V downloads new user settings information from a settings storage location and applies the settings to the local computer in these instances:</span></span>

-   <span data-ttu-id="6e138-401">每次啟動應用程式時，都會有已註冊的 UE-V 範本。</span><span class="sxs-lookup"><span data-stu-id="6e138-401">Every time an application is started that has a registered UE-V template.</span></span>

-   <span data-ttu-id="6e138-402">當使用者登入電腦時。</span><span class="sxs-lookup"><span data-stu-id="6e138-402">When a user logs on to a computer.</span></span>

-   <span data-ttu-id="6e138-403">當使用者解除鎖定電腦時。</span><span class="sxs-lookup"><span data-stu-id="6e138-403">When a user unlocks a computer.</span></span>

-   <span data-ttu-id="6e138-404">在已安裝 UE-V 的遠端桌面電腦建立連線時。</span><span class="sxs-lookup"><span data-stu-id="6e138-404">When a connection is made to a remote desktop computer that has UE-V installed.</span></span>

-   <span data-ttu-id="6e138-405">當同步處理控制器應用程式排程任務執行時。</span><span class="sxs-lookup"><span data-stu-id="6e138-405">When the Sync Controller Application scheduled task is run.</span></span>

<span data-ttu-id="6e138-406">如果 UE-V 是安裝在電腦 A 和電腦 B 上，而您想要用於應用程式的設定是在電腦 A 上，那麼電腦 A 應該先開啟並關閉應用程式。</span><span class="sxs-lookup"><span data-stu-id="6e138-406">If UE-V is installed on computer A and computer B, and the settings that you want for the application are on computer A, then computer A should open and close the application first.</span></span> <span data-ttu-id="6e138-407">如果應用程式先于電腦 B 開啟和關閉，則電腦 A 上的應用程式設定會設定為電腦 B 上的應用程式設定。每個應用程式都要在電腦之間同步處理設定。</span><span class="sxs-lookup"><span data-stu-id="6e138-407">If the application is opened and closed on computer B first, then the application settings on computer A are configured to the application settings on computer B. Settings are synchronized between computers on per-application basis.</span></span> <span data-ttu-id="6e138-408">隨著時間的推移，在電腦開啟和關閉時，這些設定會隨著喜好設定而持續保持不變。</span><span class="sxs-lookup"><span data-stu-id="6e138-408">Over time, settings become consistent between computers as they are opened and closed with preferred settings.</span></span>

<span data-ttu-id="6e138-409">此案例也適用于 Windows 設定。</span><span class="sxs-lookup"><span data-stu-id="6e138-409">This scenario also applies to Windows settings.</span></span> <span data-ttu-id="6e138-410">如果電腦 B 上的 Windows 設定應該與電腦 A 上的 Windows 設定相同，則使用者應該先登入電腦，然後再登入電腦 A。</span><span class="sxs-lookup"><span data-stu-id="6e138-410">If the Windows settings on computer B should be the same as the Windows settings on computer A, then the user should log on and log off computer A first.</span></span>

<span data-ttu-id="6e138-411">如果使用者所要套用的使用者設定的順序不正確，則可以在重寫設定的電腦上針對特定應用程式或 Windows 設定執行還原作業來復原這些設定。</span><span class="sxs-lookup"><span data-stu-id="6e138-411">If the user settings that the user wants are applied in the wrong order, they can be recovered by performing a restore operation for the specific application or Windows configuration on the computer on which the settings were overwritten.</span></span> <span data-ttu-id="6e138-412">如需詳細資訊，請參閱[管理 ue-v 2-d 中的系統管理備份和還原](manage-administrative-backup-and-restore-in-ue-v-2x-new-topic-for-21.md)。</span><span class="sxs-lookup"><span data-stu-id="6e138-412">For more information, see [Manage Administrative Backup and Restore in UE-V 2.x](manage-administrative-backup-and-restore-in-ue-v-2x-new-topic-for-21.md).</span></span>

### <a href="" id="capacity"></a><span data-ttu-id="6e138-413">效能與容量規劃</span><span class="sxs-lookup"><span data-stu-id="6e138-413">Performance and capacity planning</span></span>

<span data-ttu-id="6e138-414">針對標準磁片容量和網路狀況監視，指定您對 UE-V 的需求。</span><span class="sxs-lookup"><span data-stu-id="6e138-414">Specify your requirements for UE-V with standard disk capacity and network health monitoring.</span></span>

<span data-ttu-id="6e138-415">UE-V 使用伺服器訊息區塊（SMB）共用來儲存設定套件。</span><span class="sxs-lookup"><span data-stu-id="6e138-415">UE-V uses a Server Message Block (SMB) share for the storage of settings packages.</span></span> <span data-ttu-id="6e138-416">[設定] 套件的大小會根據每個應用程式的設定資訊而有所不同。</span><span class="sxs-lookup"><span data-stu-id="6e138-416">The size of settings packages varies depending on the settings information for each application.</span></span> <span data-ttu-id="6e138-417">雖然大部分的設定套件都很小，但同步處理可能較大的檔案（例如桌面影像），可能會導致效能較差，特別是在較慢的網路上。</span><span class="sxs-lookup"><span data-stu-id="6e138-417">While most settings packages are small, the synchronization of potentially large files, such as desktop images, can result in poor performance, particularly on slower networks.</span></span>

<span data-ttu-id="6e138-418">若要減少網路延遲的問題，請在使用者電腦所在的同一個本機網路上建立設定儲存位置。</span><span class="sxs-lookup"><span data-stu-id="6e138-418">To reduce problems with network latency, create settings storage locations on the same local networks where the users’ computers reside.</span></span> <span data-ttu-id="6e138-419">針對設定儲存位置，我們建議每個使用者有 20 MB 的磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="6e138-419">We recommend 20 MB of disk space per user for the settings storage location.</span></span>

<span data-ttu-id="6e138-420">根據預設，UE-V 同步處理會在2秒後超時，以避免由於大型設定套件而造成過多的延遲。</span><span class="sxs-lookup"><span data-stu-id="6e138-420">By default, UE-V synchronization times out after 2 seconds to prevent excessive lag due to a large settings package.</span></span> <span data-ttu-id="6e138-421">您可以使用[群組原則物件](https://technet.microsoft.com/library/dn458893.aspx)來設定 SyncMethod = SyncProvider 設定。</span><span class="sxs-lookup"><span data-stu-id="6e138-421">You can configure the SyncMethod=SyncProvider setting by using [Group Policy Objects](https://technet.microsoft.com/library/dn458893.aspx).</span></span>

### <a href="" id="high"></a><span data-ttu-id="6e138-422">UE-V 的高可用性</span><span class="sxs-lookup"><span data-stu-id="6e138-422">High Availability for UE-V</span></span>

<span data-ttu-id="6e138-423">UE-V 設定儲存位置和設定範本目錄支援將使用者資料儲存在任何可寫入的共用上。</span><span class="sxs-lookup"><span data-stu-id="6e138-423">The UE-V settings storage location and settings template catalog support storing user data on any writable share.</span></span> <span data-ttu-id="6e138-424">若要確保高可用性，請遵循下列準則：</span><span class="sxs-lookup"><span data-stu-id="6e138-424">To ensure high availability, follow these criteria:</span></span>

-   <span data-ttu-id="6e138-425">使用 NTFS 檔案系統格式化儲存空間。</span><span class="sxs-lookup"><span data-stu-id="6e138-425">Format the storage volume with an NTFS file system.</span></span>

-   <span data-ttu-id="6e138-426">共用可以使用分散式檔案系統（DFS），但有一些限制。</span><span class="sxs-lookup"><span data-stu-id="6e138-426">The share can use Distributed File System (DFS) but there are restrictions.</span></span>
<span data-ttu-id="6e138-427">具體來說，會支援分散式檔案系統複製（DFS-R）單一目標設定或不含分散式檔案系統命名空間（DFS-N）。</span><span class="sxs-lookup"><span data-stu-id="6e138-427">Specifically, Distributed File System Replication (DFS-R) single target configuration with or without a Distributed File System Namespace (DFS-N) is supported.</span></span>
<span data-ttu-id="6e138-428">同樣地，DFS-N 只支援單一目標設定。</span><span class="sxs-lookup"><span data-stu-id="6e138-428">Likewise, only single target configuration is supported with DFS-N.</span></span>
<span data-ttu-id="6e138-429">如需詳細資訊，請參閱有關[複製的使用者設定檔資料的 Microsoft 支援聲明](https://go.microsoft.com/fwlink/p/?LinkId=313991)，以及[適用于 DFS R 和 dfs N 部署案例的 microsoft 支援原則的相關資訊](https://support.microsoft.com/kb/2533009)。</span><span class="sxs-lookup"><span data-stu-id="6e138-429">For detailed information, see [Microsoft’s Support Statement Around Replicated User Profile Data](https://go.microsoft.com/fwlink/p/?LinkId=313991) and also [Information about Microsoft support policy for a DFS-R and DFS-N deployment scenario](https://support.microsoft.com/kb/2533009).</span></span>

    <span data-ttu-id="6e138-430">此外，因為 SYSVOL 使用 DFS 進行複製，所以無法將 SYSVOL 用於 UE-V 資料檔案複製。</span><span class="sxs-lookup"><span data-stu-id="6e138-430">In addition, because SYSVOL uses DFS-R for replication, SYSVOL cannot be used for UE-V data file replication.</span></span>

-   <span data-ttu-id="6e138-431">根據[部署 ue-v 2-d 的設定儲存位置](https://technet.microsoft.com/library/dn458891.aspx#ssl)中所指定的共用許可權和 NTFS 存取控制清單（acl）來設定。</span><span class="sxs-lookup"><span data-stu-id="6e138-431">Configure the share permissions and NTFS access control lists (ACLs) as specified in [Deploying the Settings Storage Location for UE-V 2.x](https://technet.microsoft.com/library/dn458891.aspx#ssl).</span></span>

-   <span data-ttu-id="6e138-432">使用檔案伺服器叢集與 UE-V Agent，在通訊發生故障時提供使用者狀態資料複本的存取權。</span><span class="sxs-lookup"><span data-stu-id="6e138-432">Use file server clustering along with the UE-V Agent to provide access to copies of user state data in the event of communications failures.</span></span>

-   <span data-ttu-id="6e138-433">您可以將設定儲存路徑資料（使用者資料）及設定範本目錄範本儲存在群集共用、DFS-N 共用或兩者上。</span><span class="sxs-lookup"><span data-stu-id="6e138-433">You can store the settings storage path data (user data) and settings template catalog templates on clustered shares, on DFS-N shares, or on both.</span></span>

### <a href="" id="clocksync"></a><span data-ttu-id="6e138-434">同步處理 UE-V 設定同步處理電腦的時鐘</span><span class="sxs-lookup"><span data-stu-id="6e138-434">Synchronize computer clocks for UE-V settings synchronization</span></span>

<span data-ttu-id="6e138-435">執行 UE-V Agent 的電腦必須使用時間伺服器來維持一致的設定體驗。</span><span class="sxs-lookup"><span data-stu-id="6e138-435">Computers that run the UE-V Agent must use a time server to maintain a consistent settings experience.</span></span> <span data-ttu-id="6e138-436">UE-V 使用時間戳來判斷設定是否必須從設定儲存位置進行同步處理。</span><span class="sxs-lookup"><span data-stu-id="6e138-436">UE-V uses time stamps to determine if settings must be synchronized from the settings storage location.</span></span> <span data-ttu-id="6e138-437">如果電腦時鐘不准確，較舊的設定會覆寫較新的設定，或者新設定可能不會儲存到設定儲存位置。</span><span class="sxs-lookup"><span data-stu-id="6e138-437">If the computer clock is inaccurate, older settings can overwrite newer settings, or the new settings might not be saved to the settings storage location.</span></span>

## <a href="" id="prereqs"></a><span data-ttu-id="6e138-438">確認 UE-V 的先決條件和支援的設定</span><span class="sxs-lookup"><span data-stu-id="6e138-438">Confirm Prerequisites and Supported Configurations for UE-V</span></span>


<span data-ttu-id="6e138-439">在您繼續進行之前，請確定您的環境包含執行 UE-V 的這些需求。</span><span class="sxs-lookup"><span data-stu-id="6e138-439">Before you proceed, make sure your environment includes these requirements for running UE-V.</span></span>

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
<th align="left"><strong><span data-ttu-id="6e138-440">作業系統</span><span class="sxs-lookup"><span data-stu-id="6e138-440">Operating system</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="6e138-441">版本</span><span class="sxs-lookup"><span data-stu-id="6e138-441">Edition</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="6e138-442">Service pack</span><span class="sxs-lookup"><span data-stu-id="6e138-442">Service pack</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="6e138-443">系統架構</span><span class="sxs-lookup"><span data-stu-id="6e138-443">System architecture</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="6e138-444">Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="6e138-444">Windows PowerShell</span></span></strong></th>
<th align="left"><strong><span data-ttu-id="6e138-445">Microsoft .NET Framework</span><span class="sxs-lookup"><span data-stu-id="6e138-445">Microsoft .NET Framework</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6e138-446">Windows 7</span><span class="sxs-lookup"><span data-stu-id="6e138-446">Windows 7</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-447">旗艦版、企業版或專業版</span><span class="sxs-lookup"><span data-stu-id="6e138-447">Ultimate, Enterprise, or Professional Edition</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-448">SP1</span><span class="sxs-lookup"><span data-stu-id="6e138-448">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-449">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="6e138-449">32-bit or 64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-450">Windows PowerShell 3.0 或更新版本</span><span class="sxs-lookup"><span data-stu-id="6e138-450">Windows PowerShell 3.0 or higher</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-451">針對 UE-V 2.1 的 .NET Framework 4.5 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="6e138-451">.NET Framework 4.5 or higher for UE-V 2.1.</span></span></p>
<p><span data-ttu-id="6e138-452">UE-V 2.0 的 .NET Framework 4 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="6e138-452">.NET Framework 4 or higher for UE-V 2.0.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6e138-453">Windows Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="6e138-453">Windows Server 2008 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-454">標準版、企業版、資料中心或 Web 服務器</span><span class="sxs-lookup"><span data-stu-id="6e138-454">Standard, Enterprise, Datacenter, or Web Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-455">SP1</span><span class="sxs-lookup"><span data-stu-id="6e138-455">SP1</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-456">64 位元</span><span class="sxs-lookup"><span data-stu-id="6e138-456">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-457">Windows PowerShell 3.0 或更新版本</span><span class="sxs-lookup"><span data-stu-id="6e138-457">Windows PowerShell 3.0 or higher</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-458">針對 UE-V 2.1 的 .NET Framework 4.5 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="6e138-458">.NET Framework 4.5 or higher for UE-V 2.1.</span></span></p>
<p><span data-ttu-id="6e138-459">UE-V 2.0 的 .NET Framework 4 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="6e138-459">.NET Framework 4 or higher for UE-V 2.0.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6e138-460">Windows 8 和 Windows 8。1</span><span class="sxs-lookup"><span data-stu-id="6e138-460">Windows 8 and Windows 8.1</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-461">企業或專業版</span><span class="sxs-lookup"><span data-stu-id="6e138-461">Enterprise or Pro</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-462">無</span><span class="sxs-lookup"><span data-stu-id="6e138-462">None</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-463">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="6e138-463">32-bit or 64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-464">Windows PowerShell 3.0 或更新版本</span><span class="sxs-lookup"><span data-stu-id="6e138-464">Windows PowerShell 3.0 or higher</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-465">.NET Framework 4.5 或更新版本</span><span class="sxs-lookup"><span data-stu-id="6e138-465">.NET Framework 4.5 or higher</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6e138-466">Windows 10 （預1607版）</span><span class="sxs-lookup"><span data-stu-id="6e138-466">Windows 10, pre-1607 version</span></span></p>
<div class="alert">
<strong><span data-ttu-id="6e138-467">注意</span><span class="sxs-lookup"><span data-stu-id="6e138-467">Note</span></span></strong><br/><p><span data-ttu-id="6e138-468">只有 UE-V 2.1 SP1 支援 Windows 10 （預1607版本）</span><span class="sxs-lookup"><span data-stu-id="6e138-468">Only UE-V 2.1 SP1 supports Windows 10, pre-1607 version</span></span></p>
</div>
<div>

</div></td>
<td align="left"><p><span data-ttu-id="6e138-469">企業或專業版</span><span class="sxs-lookup"><span data-stu-id="6e138-469">Enterprise or Pro</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-470">無</span><span class="sxs-lookup"><span data-stu-id="6e138-470">None</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-471">32 位元或 64 位元</span><span class="sxs-lookup"><span data-stu-id="6e138-471">32-bit or 64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-472">Windows PowerShell 3.0 或更新版本</span><span class="sxs-lookup"><span data-stu-id="6e138-472">Windows PowerShell 3.0 or higher</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-473">.NET Framework 4.6</span><span class="sxs-lookup"><span data-stu-id="6e138-473">.NET Framework 4.6</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6e138-474">Windows Server 2012 和 Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="6e138-474">Windows Server 2012 and Windows Server 2012 R2</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-475">標準或資料中心</span><span class="sxs-lookup"><span data-stu-id="6e138-475">Standard or Datacenter</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-476">無</span><span class="sxs-lookup"><span data-stu-id="6e138-476">None</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-477">64 位元</span><span class="sxs-lookup"><span data-stu-id="6e138-477">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-478">Windows PowerShell 3.0 或更新版本</span><span class="sxs-lookup"><span data-stu-id="6e138-478">Windows PowerShell 3.0 or higher</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-479">.NET Framework 4.5 或更新版本</span><span class="sxs-lookup"><span data-stu-id="6e138-479">.NET Framework 4.5 or higher</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6e138-480">Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="6e138-480">Windows Server 2016</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-481">標準或資料中心</span><span class="sxs-lookup"><span data-stu-id="6e138-481">Standard or Datacenter</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-482">無</span><span class="sxs-lookup"><span data-stu-id="6e138-482">None</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-483">64 位元</span><span class="sxs-lookup"><span data-stu-id="6e138-483">64-bit</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-484">Windows PowerShell 3.0 或更新版本</span><span class="sxs-lookup"><span data-stu-id="6e138-484">Windows PowerShell 3.0 or higher</span></span></p></td>
<td align="left"><p><span data-ttu-id="6e138-485">.NET Framework 4.6 或更新版本</span><span class="sxs-lookup"><span data-stu-id="6e138-485">.NET Framework 4.6 or higher</span></span></p></td>
</tr>
</tbody>
</table>



<span data-ttu-id="6e138-486">另外 .。。</span><span class="sxs-lookup"><span data-stu-id="6e138-486">Also…</span></span>

-   <span data-ttu-id="6e138-487">**MDOP 授權：** 這項技術是 Microsoft 桌面優化套件（MDOP）的一部分。</span><span class="sxs-lookup"><span data-stu-id="6e138-487">**MDOP License:** This technology is a part of the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="6e138-488">企業客戶可以使用 Microsoft 軟體保證進行 MDOP。</span><span class="sxs-lookup"><span data-stu-id="6e138-488">Enterprise customers can get MDOP with Microsoft Software Assurance.</span></span> <span data-ttu-id="6e138-489">如需 Microsoft 軟體保證及取得 MDOP 的詳細資訊，請參閱如何取得 MDOP （ https://go.microsoft.com/fwlink/p/?LinkId=322049) 。</span><span class="sxs-lookup"><span data-stu-id="6e138-489">For more information about Microsoft Software Assurance and acquiring MDOP, see How Do I Get MDOP (https://go.microsoft.com/fwlink/p/?LinkId=322049).</span></span>

-   <span data-ttu-id="6e138-490">您要安裝之任何電腦的系統**管理認證**</span><span class="sxs-lookup"><span data-stu-id="6e138-490">**Administrative Credentials** for any computer on which you’ll be installing</span></span>

**<span data-ttu-id="6e138-491">注意</span><span class="sxs-lookup"><span data-stu-id="6e138-491">Note</span></span>**  

-   <span data-ttu-id="6e138-492">從 WIndows 10 版本1607開始，UE-V 已包含在[企業版 windows 10](https://www.microsoft.com/WindowsForBusiness/windows-for-enterprise)中，而且不再是 Microsoft 桌面優化套件的一部分。</span><span class="sxs-lookup"><span data-stu-id="6e138-492">Starting with WIndows 10, version 1607, UE-V is included with [Windows 10 for Enterprise](https://www.microsoft.com/WindowsForBusiness/windows-for-enterprise) and is no longer part of the Microsoft Desktop Optimization Pack.</span></span>

-   <span data-ttu-id="6e138-493">UE-V Agent 的 UE-V Windows PowerShell 功能需要 .NET Framework 4 或更新版本，以及啟用 Windows PowerShell 3.0 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="6e138-493">The UE-V Windows PowerShell feature of the UE-V Agent requires .NET Framework 4 or higher and Windows PowerShell 3.0 or higher to be enabled.</span></span> <span data-ttu-id="6e138-494">請[在此](https://go.microsoft.com/fwlink/?LinkId=309609)下載 Windows PowerShell 3.0。</span><span class="sxs-lookup"><span data-stu-id="6e138-494">Download Windows PowerShell 3.0 [here](https://go.microsoft.com/fwlink/?LinkId=309609).</span></span>

-   <span data-ttu-id="6e138-495">在執行 Windows 7 或 Windows Server 2008 R2 作業系統的電腦上安裝 .NET Framework 4 或 .NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="6e138-495">Install .NET Framework 4 or .NET Framework 4.5 on computers that run the Windows 7 or the Windows Server 2008 R2 operating system.</span></span> <span data-ttu-id="6e138-496">Windows 8、Windows 8.1 和 Windows Server 2012 作業系統隨附 .NET Framework 4.5 安裝。</span><span class="sxs-lookup"><span data-stu-id="6e138-496">The Windows 8, Windows 8.1, and Windows Server 2012 operating systems come with .NET Framework 4.5 installed.</span></span> <span data-ttu-id="6e138-497">Windows 10 作業系統隨附安裝 .NET Framework 4.6。</span><span class="sxs-lookup"><span data-stu-id="6e138-497">The Windows 10 operating system comes with .NET Framework 4.6 installed.</span></span>
-   <span data-ttu-id="6e138-498">UE-V 不支援強制設定檔的 [刪除漫遊快取] 原則，因此不應使用此功能。</span><span class="sxs-lookup"><span data-stu-id="6e138-498">The “Delete Roaming Cache” policy for Mandatory profiles is not supported with UE-V and should not be used.</span></span>



<span data-ttu-id="6e138-499">UE-V 沒有專用的隨機存取記憶體（RAM）需求。</span><span class="sxs-lookup"><span data-stu-id="6e138-499">There are no special random access memory (RAM) requirements specific to UE-V.</span></span>

### <span data-ttu-id="6e138-500">透過同步處理提供者同步處理設定</span><span class="sxs-lookup"><span data-stu-id="6e138-500">Synchronization of Settings through the Sync Provider</span></span>

<span data-ttu-id="6e138-501">同步處理提供者是使用者的預設設定，會將本機快取與這些實例中的設定儲存位置同步處理：</span><span class="sxs-lookup"><span data-stu-id="6e138-501">Sync Provider is the default setting for users, which synchronizes a local cache with the settings storage location in these instances:</span></span>

-   <span data-ttu-id="6e138-502">登入/登出</span><span class="sxs-lookup"><span data-stu-id="6e138-502">Logon/logoff</span></span>

-   <span data-ttu-id="6e138-503">鎖定/解除鎖定</span><span class="sxs-lookup"><span data-stu-id="6e138-503">Lock/unlock</span></span>

-   <span data-ttu-id="6e138-504">遠端桌面連線/中斷連接</span><span class="sxs-lookup"><span data-stu-id="6e138-504">Remote desktop connect/disconnect</span></span>

-   <span data-ttu-id="6e138-505">開啟/關閉應用程式</span><span class="sxs-lookup"><span data-stu-id="6e138-505">Application open/close</span></span>

<span data-ttu-id="6e138-506">[排程工作] 會每30分鐘或透過特定應用程式的觸發事件，來管理這個設定的同步處理。</span><span class="sxs-lookup"><span data-stu-id="6e138-506">A scheduled task manages this synchronization of settings every 30 minutes or through certain trigger events for certain applications.</span></span> <span data-ttu-id="6e138-507">如需詳細資訊，請參閱[變更 ue-v 2. x 排程任務的頻率](changing-the-frequency-of-ue-v-2x-scheduled-tasks-both-uevv2.md)。</span><span class="sxs-lookup"><span data-stu-id="6e138-507">For more information, see [Changing the Frequency of UE-V 2.x Scheduled Tasks](changing-the-frequency-of-ue-v-2x-scheduled-tasks-both-uevv2.md).</span></span>

<span data-ttu-id="6e138-508">UE-V Agent 會同步處理並非一直連線至商業網路（遠端電腦和膝上型電腦）的電腦的使用者設定，以及永遠連線至網路的電腦（執行 Windows Server 及主機虛擬桌面介面（VDI）會話的電腦）。</span><span class="sxs-lookup"><span data-stu-id="6e138-508">The UE-V Agent synchronizes user settings for computers that are not always connected to the enterprise network (remote computers and laptops) and computers that are always connected to the network (computers that run Windows Server and host virtual desktop interface (VDI) sessions).</span></span>

<span data-ttu-id="6e138-509">**同步處理具有永遠可用連線的電腦：** 當您在一直連線到網路的電腦上使用 UE-V 時，您必須設定 UE-V Agent，以使用*SyncMethod = None*參數來同步處理設定，這會將設定儲存伺服器視為標準網路共用。</span><span class="sxs-lookup"><span data-stu-id="6e138-509">**Synchronization for computers with always-available connections:** When you use UE-V on computers that are always connected to the network, you must configure the UE-V Agent to synchronize settings by using the *SyncMethod=None* parameter, which treats the settings storage server as a standard network share.</span></span> <span data-ttu-id="6e138-510">在此設定中，UE-V Agent 可以設定為在應用程式設定匯入延遲時通知您。</span><span class="sxs-lookup"><span data-stu-id="6e138-510">In this configuration, the UE-V Agent can be configured to notify if the import of the application settings is delayed.</span></span>

<span data-ttu-id="6e138-511">透過下列其中一種方法來啟用此設定：</span><span class="sxs-lookup"><span data-stu-id="6e138-511">Enable this configuration through one of these methods:</span></span>

-   <span data-ttu-id="6e138-512">在 UE-V 安裝期間，請在命令提示字元或批次處理檔案中，將 AgentSetup.exe 參數*SyncMethod = None*。</span><span class="sxs-lookup"><span data-stu-id="6e138-512">During UE-V installation, at the command prompt or in a batch file, set the AgentSetup.exe parameter *SyncMethod = None*.</span></span> <span data-ttu-id="6e138-513">[部署 ue-v 2. x 代理程式](https://technet.microsoft.com/library/dn458891.aspx#agent)會提供更多詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="6e138-513">[Deploying the UE-V 2.x Agent](https://technet.microsoft.com/library/dn458891.aspx#agent) provides more information.</span></span>

-   <span data-ttu-id="6e138-514">UE-V 安裝之後，請使用 System Center 2012 Configuration Manager 或 MDOP ADMX 範本中的設定管理功能來推*SyncMethod = None*設定。</span><span class="sxs-lookup"><span data-stu-id="6e138-514">After the UE-V installation, use the Settings Management feature in System Center 2012 Configuration Manager or the MDOP ADMX templates to push the *SyncMethod = None* configuration.</span></span>

-   <span data-ttu-id="6e138-515">使用 Windows PowerShell 或 Windows 管理工具（WMI）來設定*SyncMethod = None*配置。</span><span class="sxs-lookup"><span data-stu-id="6e138-515">Use Windows PowerShell or Windows Management Instrumentation (WMI) to set the *SyncMethod = None* configuration.</span></span>

    **<span data-ttu-id="6e138-516">注意</span><span class="sxs-lookup"><span data-stu-id="6e138-516">Note</span></span>**  
    <span data-ttu-id="6e138-517">這最後兩個方法不適用於虛擬桌面基礎結構（VDI）環境。</span><span class="sxs-lookup"><span data-stu-id="6e138-517">These last two methods do not work for pooled virtual desktop infrastructure (VDI) environments.</span></span>



<span data-ttu-id="6e138-518">您必須先重新開機電腦，設定才會開始同步處理。</span><span class="sxs-lookup"><span data-stu-id="6e138-518">You must restart the computer before the settings start to synchronize.</span></span>

**<span data-ttu-id="6e138-519">注意</span><span class="sxs-lookup"><span data-stu-id="6e138-519">Note</span></span>**  
<span data-ttu-id="6e138-520">如果您將 [ *SyncMethod = 無*] 設定為 [無]，任何設定變更都會直接儲存到伺服器。</span><span class="sxs-lookup"><span data-stu-id="6e138-520">If you set *SyncMethod = None*, any settings changes are saved directly to the server.</span></span> <span data-ttu-id="6e138-521">如果找不到設定儲存路徑的網路連線，則會將設定變更放在裝置上，並在下次同步處理提供者執行時進行同步處理。</span><span class="sxs-lookup"><span data-stu-id="6e138-521">If the network connection to the settings storage path is not found, then the settings changes are cached on the device and are synchronized the next time that the sync provider runs.</span></span> <span data-ttu-id="6e138-522">如果找不到設定儲存路徑，且在登出時從彙集的 VDI 環境中移除使用者設定檔，則會遺失設定變更，而且當電腦重新連線至設定儲存路徑時，使用者必須重新套用變更。</span><span class="sxs-lookup"><span data-stu-id="6e138-522">If the settings storage path is not found and the user profile is removed from a pooled VDI environment on logoff, settings changes are lost and the user must reapply the change when the computer is reconnected to the settings storage path.</span></span>



<span data-ttu-id="6e138-523">\**外部同步處理引擎的同步處理：\*\*\*SyncMethod = External*參數指定如果 ue-v 設定是寫入使用者電腦上的本機資料夾，則任何外部同步處理引擎（例如商務用 OneDrive、工作資料夾、Sharepoint 或 Dropbox）都可以用來將這些設定套用到使用者存取的不同電腦上。</span><span class="sxs-lookup"><span data-stu-id="6e138-523">**Synchronization for external sync engines:** The *SyncMethod=External* parameter specifies that if UE-V settings are written to a local folder on the user computer, then any external sync engine (such as OneDrive for Business, Work Folders, Sharepoint, or Dropbox) can be used to apply these settings to the different computers that users access.</span></span>

<span data-ttu-id="6e138-524">**支援共用的 VDI 會話：** UE-V 2.1 和 2.1 SP1 為在使用者之間共用的 VDI 會話提供支援。</span><span class="sxs-lookup"><span data-stu-id="6e138-524">**Support for shared VDI sessions:** UE-V 2.1 and 2.1 SP1 provide support for VDI sessions that are shared among end users.</span></span> <span data-ttu-id="6e138-525">您可以登錄並設定特殊的 VDI 範本，這可確保 UE-V 在非持久性 VDI 會話中完整保留其所有功能。</span><span class="sxs-lookup"><span data-stu-id="6e138-525">You can register and configure a special VDI template, which ensures that UE-V keeps all of its functionality intact for non-persistent VDI sessions.</span></span>

**<span data-ttu-id="6e138-526">注意</span><span class="sxs-lookup"><span data-stu-id="6e138-526">Note</span></span>**  
<span data-ttu-id="6e138-527">如果您沒有為非持久性 VDI 會話啟用 VDI 模式，則某些功能無法運作，例如[備份/還原和上次已知良好（LKG）](https://technet.microsoft.com/library/dn878331.aspx)。</span><span class="sxs-lookup"><span data-stu-id="6e138-527">If you do not enable VDI mode for non-persistent VDI sessions, certain features do not work, such as [back-up/restore and last known good (LKG)](https://technet.microsoft.com/library/dn878331.aspx).</span></span>



<span data-ttu-id="6e138-528">VDI 範本是由 UE-V 2.1 和 2.1 SP1 提供，在安裝之後，通常可在這裡取得： C:\\program files Files\\Microsoft 使用者體驗 Virtualization\\Templates\\VdiState.xml</span><span class="sxs-lookup"><span data-stu-id="6e138-528">The VDI template is provided with UE-V 2.1 and 2.1 SP1 and is typically available here after installation: C:\\Program Files\\Microsoft User Experience Virtualization\\Templates\\VdiState.xml</span></span>

### <span data-ttu-id="6e138-529">UE-V 發生器支援的先決條件</span><span class="sxs-lookup"><span data-stu-id="6e138-529">Prerequisites for UE-V Generator support</span></span>

<span data-ttu-id="6e138-530">在用來建立自訂設定位置範本的電腦上安裝 UE-V 發生器。</span><span class="sxs-lookup"><span data-stu-id="6e138-530">Install the UE-V Generator on the computer that is used to create custom settings location templates.</span></span> <span data-ttu-id="6e138-531">此電腦應該能夠執行其設定已同步處理的應用程式。</span><span class="sxs-lookup"><span data-stu-id="6e138-531">This computer should be able to run the applications whose settings are synchronized.</span></span> <span data-ttu-id="6e138-532">您必須是執行 UE-V 發生器軟體之電腦上系統管理員群組的成員。</span><span class="sxs-lookup"><span data-stu-id="6e138-532">You must be a member of the Administrators group on the computer that runs the UE-V Generator software.</span></span>

<span data-ttu-id="6e138-533">UE-V 發生器必須安裝在使用 NTFS 檔案系統的電腦上。</span><span class="sxs-lookup"><span data-stu-id="6e138-533">The UE-V Generator must be installed on a computer that uses an NTFS file system.</span></span> <span data-ttu-id="6e138-534">UE-V 發生器軟體需要 .NET Framework 4。</span><span class="sxs-lookup"><span data-stu-id="6e138-534">The UE-V Generator software requires .NET Framework 4.</span></span> <span data-ttu-id="6e138-535">如需詳細資訊，請參閱[部署自訂應用程式的 ue-v 2.](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)</span><span class="sxs-lookup"><span data-stu-id="6e138-535">For more information, see [Deploy UE-V 2.x for Custom Applications](deploy-ue-v-2x-for-custom-applications-new-uevv2.md).</span></span>

## <span data-ttu-id="6e138-536">此產品的其他資源</span><span class="sxs-lookup"><span data-stu-id="6e138-536">Other resources for this product</span></span>


-   [<span data-ttu-id="6e138-537">Microsoft 使用者體驗虛擬化（UE-V） 2. x</span><span class="sxs-lookup"><span data-stu-id="6e138-537">Microsoft User Experience Virtualization (UE-V) 2.x</span></span>](index.md)

-   [<span data-ttu-id="6e138-538">UE-V 2.x 入門</span><span class="sxs-lookup"><span data-stu-id="6e138-538">Get Started with UE-V 2.x</span></span>](get-started-with-ue-v-2x-new-uevv2.md)

-   [<span data-ttu-id="6e138-539">管理 UE-V 2。</span><span class="sxs-lookup"><span data-stu-id="6e138-539">Administering UE-V 2.x</span></span>](administering-ue-v-2x-new-uevv2.md)

-   [<span data-ttu-id="6e138-540">疑難排解 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="6e138-540">Troubleshooting UE-V 2.x</span></span>](troubleshooting-ue-v-2x-both-uevv2.md)

-   [<span data-ttu-id="6e138-541">UE-V 2.x 技術參考</span><span class="sxs-lookup"><span data-stu-id="6e138-541">Technical Reference for UE-V 2.x</span></span>](technical-reference-for-ue-v-2x-both-uevv2.md)














