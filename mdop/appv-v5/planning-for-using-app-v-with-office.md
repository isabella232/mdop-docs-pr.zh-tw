---
title: 為搭配 Office 使用 App-V 進行規劃
description: 為搭配 Office 使用 App-V 進行規劃
author: dansimp
ms.assetid: c4371869-4bfc-4d13-9198-ef19f99fc192
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ff523c8f8827e295c8fb9a2d9fd0e02d5b019aa8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800340"
---
# <span data-ttu-id="93808-103">為搭配 Office 使用 App-V 進行規劃</span><span class="sxs-lookup"><span data-stu-id="93808-103">Planning for Using App-V with Office</span></span>


<span data-ttu-id="93808-104">使用下列資訊來規劃如何使用 App-v 來部署 Office。</span><span class="sxs-lookup"><span data-stu-id="93808-104">Use the following information to plan how to deploy Office by using App-V.</span></span> <span data-ttu-id="93808-105">本文包括：</span><span class="sxs-lookup"><span data-stu-id="93808-105">This article includes:</span></span>

-   [<span data-ttu-id="93808-106">語言套件的 app-v 支援</span><span class="sxs-lookup"><span data-stu-id="93808-106">App-V support for Language Packs</span></span>](#bkmk-lang-pack)

-   [<span data-ttu-id="93808-107">支援的 Microsoft Office 版本</span><span class="sxs-lookup"><span data-stu-id="93808-107">Supported versions of Microsoft Office</span></span>](#bkmk-office-vers-supp-appv)

-   [<span data-ttu-id="93808-108">規劃與共存版本的 Office 一起使用 App-v</span><span class="sxs-lookup"><span data-stu-id="93808-108">Planning for using App-V with coexisting versions of Office</span></span>](#bkmk-plan-coexisting)

-   [<span data-ttu-id="93808-109">部署時，Office 與 Windows 整合的方式使用 App-v 部署 Office</span><span class="sxs-lookup"><span data-stu-id="93808-109">How Office integrates with Windows when you deploy use App-V to deploy Office</span></span>](#bkmk-office-integration-win)

## <a href="" id="bkmk-lang-pack"></a><span data-ttu-id="93808-110">語言套件的 app-v 支援</span><span class="sxs-lookup"><span data-stu-id="93808-110">App-V support for Language Packs</span></span>


<span data-ttu-id="93808-111">您可以使用 App-v 5.0 Sequencer 來建立語言套件、語言介面套件、校訂工具及工具提示語言的外掛程式套件。</span><span class="sxs-lookup"><span data-stu-id="93808-111">You can use the App-V 5.0 Sequencer to create plug-in packages for Language Packs, Language Interface Packs, Proofing Tools and ScreenTip Languages.</span></span> <span data-ttu-id="93808-112">接著，您可以在連線群組中包含外掛程式套件，以及使用 Office 部署工具組建立的 Office 2013 套件。</span><span class="sxs-lookup"><span data-stu-id="93808-112">You can then include the plug-in packages in a Connection Group, along with the Office 2013 package that you create by using the Office Deployment Toolkit.</span></span> <span data-ttu-id="93808-113">Office 應用程式和外掛程式語言套件在相同的連線群組中無縫互動，就像在連線群組中組成群組的任何其他套件一樣。</span><span class="sxs-lookup"><span data-stu-id="93808-113">The Office applications and the plug-in Language Packs interact seamlessly in the same connection group, just like any other packages that are grouped together in a connection group.</span></span>

<span data-ttu-id="93808-114">**記事** Microsoft Visio 與 Microsoft Project 不提供泰語語言套件支援。</span><span class="sxs-lookup"><span data-stu-id="93808-114">**Note** Microsoft Visio and Microsoft Project do not provide support for the Thai Language Pack.</span></span>

 

## <a href="" id="bkmk-office-vers-supp-appv"></a><span data-ttu-id="93808-115">支援的 Microsoft Office 版本</span><span class="sxs-lookup"><span data-stu-id="93808-115">Supported versions of Microsoft Office</span></span>


<span data-ttu-id="93808-116">下表列出 App-v 所支援的 Microsoft Office 版本、Office 套件建立的方法、支援的授權，以及支援的部署。</span><span class="sxs-lookup"><span data-stu-id="93808-116">The following table lists the versions of Microsoft Office that App-V supports, methods of Office package creation, supported licensing, and supported deployments.</span></span>

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
<th align="left"><span data-ttu-id="93808-117">支援的 Office 版本</span><span class="sxs-lookup"><span data-stu-id="93808-117">Supported Office Version</span></span></th>
<th align="left"><span data-ttu-id="93808-118">支援的 App-v 版本</span><span class="sxs-lookup"><span data-stu-id="93808-118">Supported App-V Versions</span></span></th>
<th align="left"><span data-ttu-id="93808-119">建立套件</span><span class="sxs-lookup"><span data-stu-id="93808-119">Package Creation</span></span></th>
<th align="left"><span data-ttu-id="93808-120">支援的授權</span><span class="sxs-lookup"><span data-stu-id="93808-120">Supported Licensing</span></span></th>
<th align="left"><span data-ttu-id="93808-121">支援的部署</span><span class="sxs-lookup"><span data-stu-id="93808-121">Supported Deployments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93808-122">適用于企業的 Microsoft 365 應用程式</span><span class="sxs-lookup"><span data-stu-id="93808-122">Microsoft 365 Apps for enterprise</span></span></p>
<p><span data-ttu-id="93808-123">還支援：</span><span class="sxs-lookup"><span data-stu-id="93808-123">Also supported:</span></span></p>
<ul>
<li><p><span data-ttu-id="93808-124">Visio Pro for Office 365</span><span class="sxs-lookup"><span data-stu-id="93808-124">Visio Pro for Office 365</span></span></p></li>
<li><p><span data-ttu-id="93808-125">Project Pro for Office 365</span><span class="sxs-lookup"><span data-stu-id="93808-125">Project Pro for Office 365</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="93808-126">App-V 5。0</span><span class="sxs-lookup"><span data-stu-id="93808-126">App-V 5.0</span></span></p></li>
<li><p><span data-ttu-id="93808-127">App-V 5.0 SP1</span><span class="sxs-lookup"><span data-stu-id="93808-127">App-V 5.0 SP1</span></span></p></li>
<li><p><span data-ttu-id="93808-128">App-v 5.0 SP2</span><span class="sxs-lookup"><span data-stu-id="93808-128">App-V 5.0 SP2</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="93808-129">Office 部署工具</span><span class="sxs-lookup"><span data-stu-id="93808-129">Office Deployment Tool</span></span></p></td>
<td align="left"><p><span data-ttu-id="93808-130">訂閱</span><span class="sxs-lookup"><span data-stu-id="93808-130">Subscription</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="93808-131">桌面</span><span class="sxs-lookup"><span data-stu-id="93808-131">Desktop</span></span></p></li>
<li><p><span data-ttu-id="93808-132">個人 VDI</span><span class="sxs-lookup"><span data-stu-id="93808-132">Personal VDI</span></span></p></li>
<li><p><span data-ttu-id="93808-133">[彙集] VDI</span><span class="sxs-lookup"><span data-stu-id="93808-133">Pooled VDI</span></span></p></li>
<li><p><span data-ttu-id="93808-134">句</span><span class="sxs-lookup"><span data-stu-id="93808-134">RDS</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="93808-135">Office 專業增強版2013</span><span class="sxs-lookup"><span data-stu-id="93808-135">Office Professional Plus 2013</span></span></p>
<p><span data-ttu-id="93808-136">還支援：</span><span class="sxs-lookup"><span data-stu-id="93808-136">Also supported:</span></span></p>
<ul>
<li><p><span data-ttu-id="93808-137">Visio 專業版2013</span><span class="sxs-lookup"><span data-stu-id="93808-137">Visio Professional 2013</span></span></p></li>
<li><p><span data-ttu-id="93808-138">Project 專業版2013</span><span class="sxs-lookup"><span data-stu-id="93808-138">Project Professional 2013</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="93808-139">App-V 5。0</span><span class="sxs-lookup"><span data-stu-id="93808-139">App-V 5.0</span></span></p></li>
<li><p><span data-ttu-id="93808-140">App-V 5.0 SP1</span><span class="sxs-lookup"><span data-stu-id="93808-140">App-V 5.0 SP1</span></span></p></li>
<li><p><span data-ttu-id="93808-141">App-v 5.0 SP2</span><span class="sxs-lookup"><span data-stu-id="93808-141">App-V 5.0 SP2</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="93808-142">Office 部署工具</span><span class="sxs-lookup"><span data-stu-id="93808-142">Office Deployment Tool</span></span></p></td>
<td align="left"><p><span data-ttu-id="93808-143">大量授權</span><span class="sxs-lookup"><span data-stu-id="93808-143">Volume Licensing</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="93808-144">桌面</span><span class="sxs-lookup"><span data-stu-id="93808-144">Desktop</span></span></p></li>
<li><p><span data-ttu-id="93808-145">個人 VDI</span><span class="sxs-lookup"><span data-stu-id="93808-145">Personal VDI</span></span></p></li>
<li><p><span data-ttu-id="93808-146">[彙集] VDI</span><span class="sxs-lookup"><span data-stu-id="93808-146">Pooled VDI</span></span></p></li>
<li><p><span data-ttu-id="93808-147">句</span><span class="sxs-lookup"><span data-stu-id="93808-147">RDS</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-plan-coexisting"></a><span data-ttu-id="93808-148">規劃與共存版本的 Office 一起使用 App-v</span><span class="sxs-lookup"><span data-stu-id="93808-148">Planning for using App-V with coexisting versions of Office</span></span>


<span data-ttu-id="93808-149">您可以在同一部電腦上使用「Microsoft Office 共存」，並排安裝多個版本的 Microsoft Office。</span><span class="sxs-lookup"><span data-stu-id="93808-149">You can install more than one version of Microsoft Office side by side on the same computer by using “Microsoft Office coexistence.”</span></span> <span data-ttu-id="93808-150">您可以使用 Windows Installer （MSi）版本的 Office、隨選即用，以及 App-v 5.0 SP2，來實現 Office 共存，以及所有主要版本的 Office 與安裝方法的結合。</span><span class="sxs-lookup"><span data-stu-id="93808-150">You can implement Office coexistence with combinations of all major versions of Office and with installation methods, as applicable, by using the Windows Installer-based (MSi) version of Office, Click-to-Run, and App-V 5.0 SP2.</span></span> <span data-ttu-id="93808-151">不過 Microsoft 不建議使用 Office 共存。</span><span class="sxs-lookup"><span data-stu-id="93808-151">However, using Office coexistence is not recommended by Microsoft.</span></span>

<span data-ttu-id="93808-152">Microsoft 的建議最佳做法是完全避免 Office 共存，以避免相容性問題。</span><span class="sxs-lookup"><span data-stu-id="93808-152">Microsoft’s recommended best practice is to avoid Office coexistence completely to prevent compatibility issues.</span></span> <span data-ttu-id="93808-153">不過，當您遷移至較新版本的 Office 時，偶爾會出現無法立即解決的問題，因此您可以暫時實現共存，協助您更快速地遷移到最新的產品版本。</span><span class="sxs-lookup"><span data-stu-id="93808-153">However, when you are migrating to a newer version of Office, issues occasionally arise that can’t be resolved immediately, so you can temporarily implement coexistence to help facilitate a faster migration to the latest product version.</span></span> <span data-ttu-id="93808-154">我們不建議使用長期基礎的 Office 共存，而且您的組織應該有一個計畫在立即進行。</span><span class="sxs-lookup"><span data-stu-id="93808-154">Using Office coexistence on a long-term basis is never recommended, and your organization should have a plan to fully transition in the immediate future.</span></span>

### <span data-ttu-id="93808-155">在您實現 Office 共存之前</span><span class="sxs-lookup"><span data-stu-id="93808-155">Before you implement Office coexistence</span></span>

<span data-ttu-id="93808-156">在執行 Office 共存之前，請先查看下列 Office 檔。</span><span class="sxs-lookup"><span data-stu-id="93808-156">Before implementing Office coexistence, review the following Office documentation.</span></span> <span data-ttu-id="93808-157">選擇對應到最新版本的 Office 的文章，您打算在該文章中實施共存。</span><span class="sxs-lookup"><span data-stu-id="93808-157">Choose the article that corresponds to the newest version of Office for which you plan to implement coexistence.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="93808-158">Office 版本</span><span class="sxs-lookup"><span data-stu-id="93808-158">Office version</span></span></th>
<th align="left"><span data-ttu-id="93808-159">連結至指南</span><span class="sxs-lookup"><span data-stu-id="93808-159">Link to guidance</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93808-160">Office 2013</span><span class="sxs-lookup"><span data-stu-id="93808-160">Office 2013</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2784668" data-raw-source="[Information about how to use Office 2013 suites and programs (MSI deployment) on a computer that is running another version of Office](https://support.microsoft.com/kb/2784668)"><span data-ttu-id="93808-161">如何在執行其他 Office 版本的電腦上使用 Office 2013 套件與程式（MSI 部署）的相關資訊</span><span class="sxs-lookup"><span data-stu-id="93808-161">Information about how to use Office 2013 suites and programs (MSI deployment) on a computer that is running another version of Office</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="93808-162">Office 2010</span><span class="sxs-lookup"><span data-stu-id="93808-162">Office 2010</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2121447" data-raw-source="[Information about how to use Office 2010 suites and programs on a computer that is running another version of Office](https://support.microsoft.com/kb/2121447)"><span data-ttu-id="93808-163">如何在執行其他 Office 版本的電腦上使用 Office 2010 套件與程式的相關資訊</span><span class="sxs-lookup"><span data-stu-id="93808-163">Information about how to use Office 2010 suites and programs on a computer that is running another version of Office</span></span></a></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="93808-164">Office 檔針對 Office 的 Windows 安裝程式（MSi）與隨選即用安裝，提供大量的共存指導方針。</span><span class="sxs-lookup"><span data-stu-id="93808-164">The Office documentation provides extensive guidance on coexistence for Windows Installer-based (MSi) and Click-to-Run installations of Office.</span></span> <span data-ttu-id="93808-165">此 App-v 主題的共存是對 Office 指南進行補充，其資訊更特定于 App-v 部署。</span><span class="sxs-lookup"><span data-stu-id="93808-165">This App-V topic on coexistence supplements the Office guidance with information that is more specific to App-V deployments.</span></span>

### <span data-ttu-id="93808-166">支援的 Office 共存案例</span><span class="sxs-lookup"><span data-stu-id="93808-166">Supported Office coexistence scenarios</span></span>

<span data-ttu-id="93808-167">下表摘要列出支援的共存案例。</span><span class="sxs-lookup"><span data-stu-id="93808-167">The following tables summarize the supported coexistence scenarios.</span></span> <span data-ttu-id="93808-168">根據您開始使用的版本和部署方法，以及您要遷移的版本和部署方法來組織它們。</span><span class="sxs-lookup"><span data-stu-id="93808-168">They are organized according to the version and deployment method you’re starting with and the version and deployment method you are migrating to.</span></span> <span data-ttu-id="93808-169">在將所有共存解決方案部署到成品物件之前，請務必先完整測試。</span><span class="sxs-lookup"><span data-stu-id="93808-169">Be sure to fully test all coexistence solutions before deploying them to a production audience.</span></span>

<span data-ttu-id="93808-170">**記事** Microsoft 不支援在已啟用遠端桌面工作階段主機角色服務的 Windows Server 環境中使用多個版本的 Office。</span><span class="sxs-lookup"><span data-stu-id="93808-170">**Note** Microsoft does not support the use of multiple versions of Office in Windows Server environments that have the Remote Desktop Session Host role service enabled.</span></span> <span data-ttu-id="93808-171">若要執行 Office 共存案例，您必須停用此角色服務。</span><span class="sxs-lookup"><span data-stu-id="93808-171">To run Office coexistence scenarios, you must disable this role service.</span></span>

 

### <span data-ttu-id="93808-172">Windows 集成 & 的 Office 共存</span><span class="sxs-lookup"><span data-stu-id="93808-172">Windows integrations & Office coexistence</span></span>

<span data-ttu-id="93808-173">Windows 安裝程式與隨選即用 Office 安裝方法會與基礎 Windows 作業系統的特定點整合。</span><span class="sxs-lookup"><span data-stu-id="93808-173">The Windows Installer-based and Click-to-Run Office installation methods integrate with certain points of the underlying Windows operating system.</span></span> <span data-ttu-id="93808-174">當您使用共存功能時，在兩個 Office 版本之間的一般作業系統整合可能會衝突，從而導致相容性與使用者體驗問題。</span><span class="sxs-lookup"><span data-stu-id="93808-174">When you use coexistence, common operating system integrations between two Office versions can conflict, causing compatibility and user experience issues.</span></span> <span data-ttu-id="93808-175">在 App-v 中，您可以將某些版本的 Office 排序，以排除整合，從而將它們「隔離」至作業系統。</span><span class="sxs-lookup"><span data-stu-id="93808-175">With App-V, you can sequence certain versions of Office to exclude integrations, thereby “isolating” them from the operating system.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left"><span data-ttu-id="93808-176">在此模式中，App-v 可將這個版本的 Office 排序</span><span class="sxs-lookup"><span data-stu-id="93808-176">Mode in which App-V can sequence this version of Office</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93808-177">Office 2007</span><span class="sxs-lookup"><span data-stu-id="93808-177">Office 2007</span></span></p></td>
<td align="left"><p><span data-ttu-id="93808-178">永遠不會整合。</span><span class="sxs-lookup"><span data-stu-id="93808-178">Always non-integrated.</span></span> <span data-ttu-id="93808-179">App-v 不會提供與虛擬化版本的 Office 2007 有關的任何作業系統整合。</span><span class="sxs-lookup"><span data-stu-id="93808-179">App-V does not offer any operating system integrations with a virtualized version of Office 2007.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="93808-180">Office 2010</span><span class="sxs-lookup"><span data-stu-id="93808-180">Office 2010</span></span></p></td>
<td align="left"><p><span data-ttu-id="93808-181">整合和非整合模式。</span><span class="sxs-lookup"><span data-stu-id="93808-181">Integrated and non-integrated mode.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93808-182">Office 2013</span><span class="sxs-lookup"><span data-stu-id="93808-182">Office 2013</span></span></p></td>
<td align="left"><p><span data-ttu-id="93808-183">永遠整合。</span><span class="sxs-lookup"><span data-stu-id="93808-183">Always integrated.</span></span> <span data-ttu-id="93808-184">Windows 作業系統集成無法停用。</span><span class="sxs-lookup"><span data-stu-id="93808-184">Windows operating system integrations cannot be disabled.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="93808-185">Microsoft 建議您只使用一個整合的 Office 實例來部署 Office 共存。</span><span class="sxs-lookup"><span data-stu-id="93808-185">Microsoft recommends that you deploy Office coexistence with only one integrated Office instance.</span></span> <span data-ttu-id="93808-186">例如，如果您使用 App-v 來部署 Office 2010 和 Office 2013，您應該在非整合模式中順序排列 Office 2010。</span><span class="sxs-lookup"><span data-stu-id="93808-186">For example, if you’re using App-V to deploy Office 2010 and Office 2013, you should sequence Office 2010 in non-integrated mode.</span></span> <span data-ttu-id="93808-187">如需在非整合（獨立）模式中排序 Office 的詳細資訊，請參閱[如何在 Microsoft Application Virtualization 5.0 中排序 Microsoft Office 2010](https://support.microsoft.com/kb/2830069)。</span><span class="sxs-lookup"><span data-stu-id="93808-187">For more information about sequencing Office in non-integration (isolated) mode, see [How to sequence Microsoft Office 2010 in Microsoft Application Virtualization 5.0](https://support.microsoft.com/kb/2830069).</span></span>

### <span data-ttu-id="93808-188">Office 共存案例的已知限制</span><span class="sxs-lookup"><span data-stu-id="93808-188">Known limitations of Office coexistence scenarios</span></span>

<span data-ttu-id="93808-189">下列各節說明當您使用 App-v 來實現與 Office 的共存時，可能會遇到的一些問題。</span><span class="sxs-lookup"><span data-stu-id="93808-189">The following sections describe some issues that you might encounter when using App-V to implement coexistence with Office.</span></span>

### <span data-ttu-id="93808-190">Windows 安裝程式/隨選即用與 App-v Office 共存案例的常見限制</span><span class="sxs-lookup"><span data-stu-id="93808-190">Limitations common to Windows Installer-based/Click-to-Run and App-V Office coexistence scenarios</span></span>

<span data-ttu-id="93808-191">當您在同一部電腦上安裝下列版本的 Office 時，可能會發生下列限制：</span><span class="sxs-lookup"><span data-stu-id="93808-191">The following limitations can occur when you install the following versions of Office on the same computer:</span></span>

-   <span data-ttu-id="93808-192">使用 Windows 安裝程式的版本建立 Office 2010</span><span class="sxs-lookup"><span data-stu-id="93808-192">Office 2010 by using the Windows Installer-based version</span></span>

-   <span data-ttu-id="93808-193">使用 App-v 的 Office 2013</span><span class="sxs-lookup"><span data-stu-id="93808-193">Office 2013 by using App-V</span></span>

<span data-ttu-id="93808-194">在您使用 App-v 與舊版 Windows 安裝程式的 Office 2010 發佈 Office 2013 之後，也可能會造成 Windows 安裝程式啟動。</span><span class="sxs-lookup"><span data-stu-id="93808-194">After you publish Office 2013 by using App-V side by side with an earlier version of the Windows Installer-based Office 2010 might also cause the Windows Installer to start.</span></span> <span data-ttu-id="93808-195">這是因為 Windows 安裝程式或隨選即用版本的 Office 2010 嘗試自動將自己註冊到電腦。</span><span class="sxs-lookup"><span data-stu-id="93808-195">This is because the Windows Installer-based or Click-to-Run version of Office 2010 is trying to automatically register itself to the computer.</span></span>

<span data-ttu-id="93808-196">若要略過原生 Word 2010 的自動註冊作業，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="93808-196">To bypass the auto-registration operation for native Word 2010, follow these steps:</span></span>

1.  <span data-ttu-id="93808-197">退出 Word 2010。</span><span class="sxs-lookup"><span data-stu-id="93808-197">Exit Word 2010.</span></span>

2.  <span data-ttu-id="93808-198">執行下列動作，啟動 [登錄編輯程式]：</span><span class="sxs-lookup"><span data-stu-id="93808-198">Start the Registry Editor by doing the following:</span></span>

    -   <span data-ttu-id="93808-199">在 Windows 7 中：按一下 [**開始**]，在 [開始搜尋] 方塊中輸入**regedit** ，然後按 enter。</span><span class="sxs-lookup"><span data-stu-id="93808-199">In Windows 7: Click **Start**, type **regedit** in the Start Search box, and then press Enter.</span></span>

    -   <span data-ttu-id="93808-200">在 Windows 8 中，輸入**regedit** ，在起始頁面上按 enter，然後按 enter。</span><span class="sxs-lookup"><span data-stu-id="93808-200">In Windows 8, type **regedit** press Enter on the Start page and then press Enter.</span></span>

    <span data-ttu-id="93808-201">如果系統提示您輸入系統管理員密碼或進行確認，請輸入密碼，或按一下 [**繼續**]。</span><span class="sxs-lookup"><span data-stu-id="93808-201">If you are prompted for an administrator password or for a confirmation, type the password, or click **Continue**.</span></span>

3.  <span data-ttu-id="93808-202">找出下列登錄子機碼，然後選取該子項：</span><span class="sxs-lookup"><span data-stu-id="93808-202">Locate and then select the following registry subkey:</span></span>

    ``` syntax
    HKEY_CURRENT_USER\Software\Microsoft\Office\14.0\Word\Options
    ```

4.  <span data-ttu-id="93808-203">在 [**編輯**] 功能表上，按一下 [**新增**]，然後按一下 [ **DWORD 值**]。</span><span class="sxs-lookup"><span data-stu-id="93808-203">On the **Edit** menu, click **New**, and then click **DWORD Value**.</span></span>

5.  <span data-ttu-id="93808-204">輸入**NoReReg**，然後按 enter。</span><span class="sxs-lookup"><span data-stu-id="93808-204">Type **NoReReg**, and then press Enter.</span></span>

6.  <span data-ttu-id="93808-205">以滑鼠右鍵按一下 [ **NoReReg** ]，然後按一下 [**修改**]。</span><span class="sxs-lookup"><span data-stu-id="93808-205">Right-click **NoReReg** and then click **Modify**.</span></span>

7.  <span data-ttu-id="93808-206">在 [ **Valuedata** ] 方塊中，輸入**1**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="93808-206">In the **Valuedata** box, type **1**, and then click **OK**.</span></span>

8.  <span data-ttu-id="93808-207">在 [檔案] 功能表上 **，按一下 [** 結束] 來關閉 [登錄編輯程式]。</span><span class="sxs-lookup"><span data-stu-id="93808-207">On the File menu, click **Exit** to close Registry Editor.</span></span>

## <a href="" id="bkmk-office-integration-win"></a><span data-ttu-id="93808-208">使用 App-v 部署 Office 時，Office 與 Windows 整合的方式</span><span class="sxs-lookup"><span data-stu-id="93808-208">How Office integrates with Windows when you use App-V to deploy Office</span></span>


<span data-ttu-id="93808-209">當您使用 App-v 部署 Office 2013 時，Office 會與作業系統完全整合，這可讓使用者擁有的功能和功能與 Office 在部署但不含 App-v 時一樣。</span><span class="sxs-lookup"><span data-stu-id="93808-209">When you deploy Office 2013 by using App-V, Office is fully integrated with the operating system, which provides end users with the same features and functionality as Office has when it is deployed without App-V.</span></span>

<span data-ttu-id="93808-210">Office 2013 App-v 套件支援下列整合點與 Windows 作業系統：</span><span class="sxs-lookup"><span data-stu-id="93808-210">The Office 2013 App-V package supports the following integration points with the Windows operating system:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="93808-211">延伸點</span><span class="sxs-lookup"><span data-stu-id="93808-211">Extension Point</span></span></th>
<th align="left"><span data-ttu-id="93808-212">描述</span><span class="sxs-lookup"><span data-stu-id="93808-212">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93808-213">適用于 Firefox 和 Chrome 的 Lync 會議加入外掛程式</span><span class="sxs-lookup"><span data-stu-id="93808-213">Lync meeting Join Plug-in for Firefox and Chrome</span></span></p></td>
<td align="left"><p><span data-ttu-id="93808-214">使用者可以從 Firefox 和 Chrome 加入 Lync 會議</span><span class="sxs-lookup"><span data-stu-id="93808-214">User can join Lync meetings from Firefox and Chrome</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="93808-215">已傳送至 OneNote 列印驅動程式</span><span class="sxs-lookup"><span data-stu-id="93808-215">Sent to OneNote Print Driver</span></span></p></td>
<td align="left"><p><span data-ttu-id="93808-216">使用者可以列印至 OneNote</span><span class="sxs-lookup"><span data-stu-id="93808-216">User can print to OneNote</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93808-217">OneNote 連結筆記</span><span class="sxs-lookup"><span data-stu-id="93808-217">OneNote Linked Notes</span></span></p></td>
<td align="left"><p><span data-ttu-id="93808-218">OneNote 連結筆記</span><span class="sxs-lookup"><span data-stu-id="93808-218">OneNote Linked Notes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="93808-219">傳送至 OneNote Internet Explorer 增益集</span><span class="sxs-lookup"><span data-stu-id="93808-219">Send to OneNote Internet Explorer Add-In</span></span></p></td>
<td align="left"><p><span data-ttu-id="93808-220">使用者可以從 IE 傳送至 OneNote</span><span class="sxs-lookup"><span data-stu-id="93808-220">User can send to OneNote from IE</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93808-221">Lync 和 Outlook 的防火牆例外狀況</span><span class="sxs-lookup"><span data-stu-id="93808-221">Firewall Exception for Lync and Outlook</span></span></p></td>
<td align="left"><p><span data-ttu-id="93808-222">Lync 和 Outlook 的防火牆例外狀況</span><span class="sxs-lookup"><span data-stu-id="93808-222">Firewall Exception for Lync and Outlook</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="93808-223">MAPI 用戶端</span><span class="sxs-lookup"><span data-stu-id="93808-223">MAPI Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="93808-224">原生應用程式和增益集可透過 MAPI 與虛擬 Outlook 互動</span><span class="sxs-lookup"><span data-stu-id="93808-224">Native apps and add-ins can interact with virtual Outlook through MAPI</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93808-225">適用于 Firefox 的 SharePoint 外掛程式</span><span class="sxs-lookup"><span data-stu-id="93808-225">SharePoint Plug-in for Firefox</span></span></p></td>
<td align="left"><p><span data-ttu-id="93808-226">使用者可以在 Firefox 中使用 SharePoint 功能</span><span class="sxs-lookup"><span data-stu-id="93808-226">User can use SharePoint features in Firefox</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="93808-227">[郵件] 控制台小程式</span><span class="sxs-lookup"><span data-stu-id="93808-227">Mail Control Panel Applet</span></span></p></td>
<td align="left"><p><span data-ttu-id="93808-228">使用者在 Outlook 中取得 [郵件] 控制台小程式</span><span class="sxs-lookup"><span data-stu-id="93808-228">User gets the mail control panel applet in Outlook</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93808-229">主要 Interop 元件</span><span class="sxs-lookup"><span data-stu-id="93808-229">Primary Interop Assemblies</span></span></p></td>
<td align="left"><p><span data-ttu-id="93808-230">支援受管理的增益集</span><span class="sxs-lookup"><span data-stu-id="93808-230">Support managed add-ins</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="93808-231">Office 檔快取處理常式</span><span class="sxs-lookup"><span data-stu-id="93808-231">Office Document Cache Handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="93808-232">允許 Office 應用程式的檔快取</span><span class="sxs-lookup"><span data-stu-id="93808-232">Allows Document Cache for Office applications</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93808-233">Outlook 通訊協定搜尋處理常式</span><span class="sxs-lookup"><span data-stu-id="93808-233">Outlook Protocol Search handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="93808-234">使用者可以在 outlook 中搜尋</span><span class="sxs-lookup"><span data-stu-id="93808-234">User can search in outlook</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="93808-235">Active X 控制項：</span><span class="sxs-lookup"><span data-stu-id="93808-235">Active X Controls:</span></span></p></td>
<td align="left"><p><span data-ttu-id="93808-236">如需有關 ActiveX 控制項的詳細資訊，請參閱 <a href="https://go.microsoft.com/fwlink/p/?LinkId=331361" data-raw-source="[ActiveX Control API Reference](https://go.microsoft.com/fwlink/p/?LinkId=331361)"> Activex 控制項 API 參考 </a> 。</span><span class="sxs-lookup"><span data-stu-id="93808-236">For more information on ActiveX controls, refer to <a href="https://go.microsoft.com/fwlink/p/?LinkId=331361" data-raw-source="[ActiveX Control API Reference](https://go.microsoft.com/fwlink/p/?LinkId=331361)">ActiveX Control API Reference</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="93808-237">Groove. SiteClient</span><span class="sxs-lookup"><span data-stu-id="93808-237">Groove.SiteClient</span></span></p></td>
<td align="left"><p><span data-ttu-id="93808-238">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="93808-238">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="93808-239">PortalConnect.PersonalSite</span><span class="sxs-lookup"><span data-stu-id="93808-239">PortalConnect.PersonalSite</span></span></p></td>
<td align="left"><p><span data-ttu-id="93808-240">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="93808-240">Active X Control</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="93808-241">OpenDocuments</span><span class="sxs-lookup"><span data-stu-id="93808-241">SharePoint.openDocuments</span></span></p></td>
<td align="left"><p><span data-ttu-id="93808-242">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="93808-242">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="93808-243">ExportDatabase</span><span class="sxs-lookup"><span data-stu-id="93808-243">SharePoint.ExportDatabase</span></span></p></td>
<td align="left"><p><span data-ttu-id="93808-244">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="93808-244">Active X Control</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="93808-245">SpreadSheetLauncher</span><span class="sxs-lookup"><span data-stu-id="93808-245">SharePoint.SpreadSheetLauncher</span></span></p></td>
<td align="left"><p><span data-ttu-id="93808-246">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="93808-246">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="93808-247">StssyncHander</span><span class="sxs-lookup"><span data-stu-id="93808-247">SharePoint.StssyncHander</span></span></p></td>
<td align="left"><p><span data-ttu-id="93808-248">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="93808-248">Active X Control</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="93808-249">DragUploadCtl</span><span class="sxs-lookup"><span data-stu-id="93808-249">SharePoint.DragUploadCtl</span></span></p></td>
<td align="left"><p><span data-ttu-id="93808-250">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="93808-250">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="93808-251">DragDownloadCtl</span><span class="sxs-lookup"><span data-stu-id="93808-251">SharePoint.DragDownloadCtl</span></span></p></td>
<td align="left"><p><span data-ttu-id="93808-252">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="93808-252">Active X Control</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="93808-253">OpenXMLDocuments</span><span class="sxs-lookup"><span data-stu-id="93808-253">Sharepoint.OpenXMLDocuments</span></span></p></td>
<td align="left"><p><span data-ttu-id="93808-254">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="93808-254">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="93808-255">ClipboardCtl</span><span class="sxs-lookup"><span data-stu-id="93808-255">Sharepoint.ClipboardCtl</span></span></p></td>
<td align="left"><p><span data-ttu-id="93808-256">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="93808-256">Active X control</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="93808-257">WinProj Activator</span><span class="sxs-lookup"><span data-stu-id="93808-257">WinProj.Activator</span></span></p></td>
<td align="left"><p><span data-ttu-id="93808-258">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="93808-258">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="93808-259">NameCtrl</span><span class="sxs-lookup"><span data-stu-id="93808-259">Name.NameCtrl</span></span></p></td>
<td align="left"><p><span data-ttu-id="93808-260">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="93808-260">Active X Control</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="93808-261">STSUPld.CopyCtl</span><span class="sxs-lookup"><span data-stu-id="93808-261">STSUPld.CopyCtl</span></span></p></td>
<td align="left"><p><span data-ttu-id="93808-262">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="93808-262">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="93808-263">CommunicatorMeetingJoinAx.JoinManager</span><span class="sxs-lookup"><span data-stu-id="93808-263">CommunicatorMeetingJoinAx.JoinManager</span></span></p></td>
<td align="left"><p><span data-ttu-id="93808-264">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="93808-264">Active X Control</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="93808-265">LISTNET.Listnet</span><span class="sxs-lookup"><span data-stu-id="93808-265">LISTNET.Listnet</span></span></p></td>
<td align="left"><p><span data-ttu-id="93808-266">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="93808-266">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="93808-267">OneDrive 專業版瀏覽器協助程式</span><span class="sxs-lookup"><span data-stu-id="93808-267">OneDrive Pro Browser Helper</span></span></p></td>
<td align="left"><p><span data-ttu-id="93808-268">Active X 控制項]</span><span class="sxs-lookup"><span data-stu-id="93808-268">Active X Control]</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93808-269">OneDrive Pro 圖示重迭</span><span class="sxs-lookup"><span data-stu-id="93808-269">OneDrive Pro Icon Overlays</span></span></p></td>
<td align="left"><p><span data-ttu-id="93808-270">當使用者查看資料夾 OneDrive Pro 資料夾時，Windows Explorer shell 圖示會重迭</span><span class="sxs-lookup"><span data-stu-id="93808-270">Windows Explorer shell icon overlays when users look at folders OneDrive Pro folders</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="93808-271">殼層延伸</span><span class="sxs-lookup"><span data-stu-id="93808-271">Shell extensions</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="93808-272">方式</span><span class="sxs-lookup"><span data-stu-id="93808-272">Shortcuts</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="93808-273">Windows Search</span><span class="sxs-lookup"><span data-stu-id="93808-273">Windows Search</span></span></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 






 

 





