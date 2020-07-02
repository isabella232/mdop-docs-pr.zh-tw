---
title: Microsoft 使用者體驗虛擬化（UE-V） 2. x
description: Microsoft 使用者體驗虛擬化（UE-V） 2. x
author: dansimp
ms.assetid: b860fed0-b846-415d-bdd6-ba60231a64be
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 04/19/2017
ms.openlocfilehash: 573b8bb2027e5c7f117a8254005a43c656f047a9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10795566"
---
# <span data-ttu-id="7c8fe-103">Microsoft 使用者體驗虛擬化（UE-V） 2. x</span><span class="sxs-lookup"><span data-stu-id="7c8fe-103">Microsoft User Experience Virtualization (UE-V) 2.x</span></span>

>[!NOTE]
><span data-ttu-id="7c8fe-104">本檔是 Microsoft 桌面優化套件（MDOP）中包含的 UE-V 版本。</span><span class="sxs-lookup"><span data-stu-id="7c8fe-104">This documentation is a for version of UE-V that was included in the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="7c8fe-105">如需 Windows 10 企業版中包含的最新版本 UE-V 的相關資訊，請參閱[從 Ue-v 開始使用](https://docs.microsoft.com/windows/configuration/ue-v/uev-getting-started)。</span><span class="sxs-lookup"><span data-stu-id="7c8fe-105">For information about the latest version of UE-V which is included in Windows 10 Enterprise, see [Get Started with UE-V](https://docs.microsoft.com/windows/configuration/ue-v/uev-getting-started).</span></span>


<span data-ttu-id="7c8fe-106">透過執行 Microsoft 使用者體驗虛擬化（UE-V）2.0 或2.1，來捕獲並集中使用者的應用程式設定和 Windows 作業系統設定。</span><span class="sxs-lookup"><span data-stu-id="7c8fe-106">Capture and centralize your users’ application settings and Windows OS settings by implementing Microsoft User Experience Virtualization (UE-V) 2.0 or 2.1.</span></span> <span data-ttu-id="7c8fe-107">然後，將這些設定套用到企業中的使用者存取的裝置，例如桌上型電腦、膝上型電腦或虛擬桌面基礎結構（VDI）會話。</span><span class="sxs-lookup"><span data-stu-id="7c8fe-107">Then, apply these settings to the devices users access in your enterprise, like desktop computers, laptops, or virtual desktop infrastructure (VDI) sessions.</span></span>

**<span data-ttu-id="7c8fe-108">使用 UE-V，您可以 .。。</span><span class="sxs-lookup"><span data-stu-id="7c8fe-108">With UE-V you can…</span></span>**

-   <span data-ttu-id="7c8fe-109">指定要同步處理哪些應用程式和桌面設定</span><span class="sxs-lookup"><span data-stu-id="7c8fe-109">Specify which application and desktop settings synchronize</span></span>

-   <span data-ttu-id="7c8fe-110">為整個企業的使用者隨時隨地提供設定</span><span class="sxs-lookup"><span data-stu-id="7c8fe-110">Deliver the settings anytime and anywhere users work throughout the enterprise</span></span>

-   <span data-ttu-id="7c8fe-111">為協力廠商或企業營運應用程式建立自訂範本</span><span class="sxs-lookup"><span data-stu-id="7c8fe-111">Create custom templates for your third-party or line-of-business applications</span></span>

-   <span data-ttu-id="7c8fe-112">在硬體更換或升級之後或將虛擬機器重設為初始狀態之後復原設定</span><span class="sxs-lookup"><span data-stu-id="7c8fe-112">Recover settings after hardware replacement or upgrade, or after reimaging a virtual machine to its initial state</span></span>

## <span data-ttu-id="7c8fe-113">UE-V 2. x 的元件</span><span class="sxs-lookup"><span data-stu-id="7c8fe-113">Components of UE-V 2.x</span></span>


<span data-ttu-id="7c8fe-114">此圖表顯示部署的 UE-V 元件如何共同運作，以同步處理設定。</span><span class="sxs-lookup"><span data-stu-id="7c8fe-114">This diagram shows how deployed UE-V components work together to synchronize settings.</span></span>

![uev2 結構圖表](images/uev2archdiagram.gif)

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="7c8fe-116">元件</span><span class="sxs-lookup"><span data-stu-id="7c8fe-116">Component</span></span></th>
<th align="left"><span data-ttu-id="7c8fe-117">函式</span><span class="sxs-lookup"><span data-stu-id="7c8fe-117">Function</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="7c8fe-118">UE-V Agent</span><span class="sxs-lookup"><span data-stu-id="7c8fe-118">UE-V Agent</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-119">在需要同步處理設定的每台電腦上安裝， <strong> Ue-v agent 會 </strong> 監視已註冊的應用程式與作業系統的任何設定變更，然後在電腦之間同步處理這些設定。</span><span class="sxs-lookup"><span data-stu-id="7c8fe-119">Installed on every computer that needs to synchronize settings, the <strong>UE-V Agent</strong> monitors registered applications and the operating system for any settings changes, then synchronizes those settings between computers.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="7c8fe-120">設定套件</span><span class="sxs-lookup"><span data-stu-id="7c8fe-120">Settings packages</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-121">[應用程式設定] 和 [Windows 設定] 儲存在 <strong> </strong> 由 ue-v agent 建立的設定套件中。</span><span class="sxs-lookup"><span data-stu-id="7c8fe-121">Application settings and Windows settings are stored in <strong>settings packages</strong> created by the UE-V Agent.</span></span> <span data-ttu-id="7c8fe-122">設定套件建置後會儲存到本機，然後複製到設定儲存位置。</span><span class="sxs-lookup"><span data-stu-id="7c8fe-122">Settings packages are built, locally stored, and copied to the settings storage location.</span></span></p>
<ul>
<li><p><span data-ttu-id="7c8fe-123"><strong> </strong> 當使用者關閉應用程式時，會儲存桌面應用程式的設定值。</span><span class="sxs-lookup"><span data-stu-id="7c8fe-123">The setting values for <strong>desktop applications</strong> are stored when the user closes the application.</span></span></p></li>
<li><p><span data-ttu-id="7c8fe-124"><strong>Windows 設定的值 </strong> 會在使用者登出、電腦被鎖定時，或當使用者從電腦上遠端斷開時儲存。</span><span class="sxs-lookup"><span data-stu-id="7c8fe-124">Values for <strong>Windows settings</strong> are stored when the user logs off, when the computer is locked, or when the user disconnects remotely from a computer.</span></span></p></li>
</ul>
<p><span data-ttu-id="7c8fe-125">同步處理提供者會判斷何時從設定套件中讀取應用程式或作業系統的設定 <strong> </strong> ，並進行同步處理。</span><span class="sxs-lookup"><span data-stu-id="7c8fe-125">The sync provider determines when the application or operating system settings are read from the <strong>Settings Packages</strong> and synchronized.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="7c8fe-126">設定儲存位置</span><span class="sxs-lookup"><span data-stu-id="7c8fe-126">Settings storage location</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-127">這是您的使用者可以存取的標準網路共用。</span><span class="sxs-lookup"><span data-stu-id="7c8fe-127">This is a standard network share that your users can access.</span></span> <span data-ttu-id="7c8fe-128">UE-V Agent 會驗證位置，並建立隱藏的系統資料夾，以儲存及檢索使用者設定。</span><span class="sxs-lookup"><span data-stu-id="7c8fe-128">The UE-V Agent verifies the location and creates a hidden system folder in which to store and retrieve user settings.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="7c8fe-129">設定位置範本</span><span class="sxs-lookup"><span data-stu-id="7c8fe-129">Settings location templates</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-130">UE-V 使用 XML 檔案做為設定位置範本，在使用者電腦之間監視及同步處理桌面應用程式設定與 Windows 桌面設定。</span><span class="sxs-lookup"><span data-stu-id="7c8fe-130">UE-V uses XML files as settings location templates to monitor and synchronize desktop application settings and Windows desktop settings between user computers.</span></span> <span data-ttu-id="7c8fe-131">根據預設，在 UE-V 中包含一些設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="7c8fe-131">By default, some settings location templates are included in UE-V .</span></span> <span data-ttu-id="7c8fe-132">您也可以透過 <a href="#customapps" data-raw-source="[managing settings synchronization for custom applications](#customapps)"> 管理自訂應用程式的設定同步處理，來建立、編輯或驗證自訂設定位置範本 </a> 。</span><span class="sxs-lookup"><span data-stu-id="7c8fe-132">You can also create, edit, or validate custom settings location templates by <a href="#customapps" data-raw-source="[managing settings synchronization for custom applications](#customapps)">managing settings synchronization for custom applications</a>.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="7c8fe-133">注意</span><span class="sxs-lookup"><span data-stu-id="7c8fe-133">Note</span></span></strong><br/><p><span data-ttu-id="7c8fe-134">Windows 應用程式不需要設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="7c8fe-134">Settings location templates are not required for Windows apps.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="7c8fe-135">Windows 應用程式清單</span><span class="sxs-lookup"><span data-stu-id="7c8fe-135">Windows app list</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-136">Windows 應用程式的設定會被動態捕獲並套用。</span><span class="sxs-lookup"><span data-stu-id="7c8fe-136">Settings for Windows apps are captured and applied dynamically.</span></span> <span data-ttu-id="7c8fe-137">App 開發人員會為每個 app 指定同步處理的設定。</span><span class="sxs-lookup"><span data-stu-id="7c8fe-137">The app developer specifies the settings that are synchronized for each app.</span></span> <span data-ttu-id="7c8fe-138">UE-V 會判斷使用受管理的應用程式清單來啟用設定同步處理的 Windows 應用程式。</span><span class="sxs-lookup"><span data-stu-id="7c8fe-138">UE-V determines which Windows apps are enabled for settings synchronization using a managed list of apps.</span></span> <span data-ttu-id="7c8fe-139">根據預設，此清單包含大部分的 Windows 應用程式。</span><span class="sxs-lookup"><span data-stu-id="7c8fe-139">By default, this list includes most Windows apps.</span></span></p>
<p><span data-ttu-id="7c8fe-140">您可以按照此處所示的程式，在 Windows 應用程式清單中新增或移除應用程式 <a href="https://technet.microsoft.com/library/dn458925.aspx" data-raw-source="[here](https://technet.microsoft.com/library/dn458925.aspx)"> </a> 。</span><span class="sxs-lookup"><span data-stu-id="7c8fe-140">You can add or remove applications in the Windows app list by following the procedures shown <a href="https://technet.microsoft.com/library/dn458925.aspx" data-raw-source="[here](https://technet.microsoft.com/library/dn458925.aspx)">here</a>.</span></span></p></td>
</tr>
</tbody>
</table>



### <a href="" id="customapps"></a><span data-ttu-id="7c8fe-141">管理自訂應用程式的設定同步處理</span><span class="sxs-lookup"><span data-stu-id="7c8fe-141">Managing Settings Synchronization for Custom Applications</span></span>

<span data-ttu-id="7c8fe-142">使用這些 UE-V 元件來建立及管理協力廠商或商務用端應用程式的自訂範本。</span><span class="sxs-lookup"><span data-stu-id="7c8fe-142">Use these UE-V components to create and manage custom templates for your third-party or line-of-business applications.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="7c8fe-143">UE-V 發生器</span><span class="sxs-lookup"><span data-stu-id="7c8fe-143">UE-V Generator</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-144">使用 <strong> Ue-v 發生器 </strong> 來建立自訂設定位置範本，您可以將它發佈到使用者電腦。</span><span class="sxs-lookup"><span data-stu-id="7c8fe-144">Use the <strong>UE-V Generator</strong> to create custom settings location templates that you can then distribute to user computers.</span></span> <span data-ttu-id="7c8fe-145">UE-V 發生器也可讓您編輯現有的範本，或驗證使用其他 XML 編輯器所建立的範本。</span><span class="sxs-lookup"><span data-stu-id="7c8fe-145">The UE-V Generator also lets you edit an existing template or validate a template that was created by using another XML editor.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="7c8fe-146">設定範本目錄</span><span class="sxs-lookup"><span data-stu-id="7c8fe-146">Settings template catalog</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-147">[ <strong> 設定範本目錄] </strong> 是 ue-v 電腦或伺服器郵件區塊（SMB）網路共用上的資料夾路徑，可儲存自訂設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="7c8fe-147">The <strong>settings template catalog</strong> is a folder path on UE-V computers or a Server Message Block (SMB) network share that stores the custom settings location templates.</span></span> <span data-ttu-id="7c8fe-148">UE-V Agent 會一天檢查這個位置，檢索新的或更新的範本，並更新其同步處理行為。</span><span class="sxs-lookup"><span data-stu-id="7c8fe-148">The UE-V Agent checks this location once a day, retrieves new or updated templates, and updates its synchronization behavior.</span></span></p>
<p><span data-ttu-id="7c8fe-149">如果您只使用 UE-V 預設設定位置範本，則不需要設定範本目錄。</span><span class="sxs-lookup"><span data-stu-id="7c8fe-149">If you use only the UE-V default settings location templates, then a settings template catalog is unnecessary.</span></span> <span data-ttu-id="7c8fe-150">如需設定部署目錄的詳細資訊，請參閱 <a href="https://technet.microsoft.com/library/dn458942.aspx#deploycatalogue" data-raw-source="[Configure a UE-V settings template catalog](https://technet.microsoft.com/library/dn458942.aspx#deploycatalogue)"> 設定 ue-v 設定範本目錄 </a> 。</span><span class="sxs-lookup"><span data-stu-id="7c8fe-150">For more information about settings deployment catalogs, see <a href="https://technet.microsoft.com/library/dn458942.aspx#deploycatalogue" data-raw-source="[Configure a UE-V settings template catalog](https://technet.microsoft.com/library/dn458942.aspx#deploycatalogue)">Configure a UE-V settings template catalog</a>.</span></span></p></td>
</tr>
</tbody>
</table>



![ue-v 發生器程式](images/ue-vgeneratorprocess.gif)

## <span data-ttu-id="7c8fe-152">預設同步處理的設定</span><span class="sxs-lookup"><span data-stu-id="7c8fe-152">Settings Synchronized by Default</span></span>


<span data-ttu-id="7c8fe-153">UE-V 預設會同步處理這些應用程式的設定。</span><span class="sxs-lookup"><span data-stu-id="7c8fe-153">UE-V synchronizes settings for these applications by default.</span></span> <span data-ttu-id="7c8fe-154">如需完整清單及更詳細的資訊，請參閱[在 ue-v 部署中自動同步](https://technet.microsoft.com/library/dn458932.aspx#autosyncsettings)處理的設定。</span><span class="sxs-lookup"><span data-stu-id="7c8fe-154">For a complete list and more detailed information, see [Settings that are automatically synchronized in a UE-V deployment](https://technet.microsoft.com/library/dn458932.aspx#autosyncsettings).</span></span>

<span data-ttu-id="7c8fe-155">Microsoft Office 2013 應用程式（UE-V 2.1 SP1 及2.1）</span><span class="sxs-lookup"><span data-stu-id="7c8fe-155">Microsoft Office 2013 applications (UE-V 2.1 SP1 and 2.1)</span></span>

<span data-ttu-id="7c8fe-156">Microsoft Office 2010 應用程式（UE-V 2.1 SP1、2.1 和2.0）</span><span class="sxs-lookup"><span data-stu-id="7c8fe-156">Microsoft Office 2010 applications (UE-V 2.1 SP1, 2.1, and 2.0)</span></span>

<span data-ttu-id="7c8fe-157">Microsoft Office 2007 應用程式（僅限 UE-V 2.0）</span><span class="sxs-lookup"><span data-stu-id="7c8fe-157">Microsoft Office 2007 applications (UE-V 2.0 only)</span></span>

<span data-ttu-id="7c8fe-158">Internet Explorer 8、9和10</span><span class="sxs-lookup"><span data-stu-id="7c8fe-158">Internet Explorer 8, 9, and 10</span></span>

<span data-ttu-id="7c8fe-159">UE-V 2.1 SP1 和2.1 中的 Internet Explorer 11</span><span class="sxs-lookup"><span data-stu-id="7c8fe-159">Internet Explorer 11 in UE-V 2.1 SP1 and 2.1</span></span>

<span data-ttu-id="7c8fe-160">許多 Windows 應用程式，例如 Xbox</span><span class="sxs-lookup"><span data-stu-id="7c8fe-160">Many Windows applications, such as Xbox</span></span>

<span data-ttu-id="7c8fe-161">許多 Windows 桌面應用程式，例如記事本</span><span class="sxs-lookup"><span data-stu-id="7c8fe-161">Many Windows desktop applications, such as Notepad</span></span>

<span data-ttu-id="7c8fe-162">許多 Windows 設定（例如桌面背景或牆紙）</span><span class="sxs-lookup"><span data-stu-id="7c8fe-162">Many Windows settings, such as desktop background or wallpaper</span></span>

**<span data-ttu-id="7c8fe-163">注意</span><span class="sxs-lookup"><span data-stu-id="7c8fe-163">Note</span></span>**  
<span data-ttu-id="7c8fe-164">您也可以[自訂 ue-v，以同步處理](https://technet.microsoft.com/library/dn458942.aspx)除預設值以外的應用程式的設定。</span><span class="sxs-lookup"><span data-stu-id="7c8fe-164">You can also [customize UE-V to synchronize settings](https://technet.microsoft.com/library/dn458942.aspx) for applications other than those synchronized by default.</span></span>



## <span data-ttu-id="7c8fe-165">比較 UE-V 與其他 Microsoft 產品</span><span class="sxs-lookup"><span data-stu-id="7c8fe-165">Compare UE-V to other Microsoft products</span></span>


<span data-ttu-id="7c8fe-166">使用此表格比較 UE-V 以在 Windows 7 中同步處理設定檔、在 Windows 8 中同步處理設定檔，以及 Microsoft 帳戶的 [同步電腦設定] 功能。</span><span class="sxs-lookup"><span data-stu-id="7c8fe-166">Use this table to compare UE-V to Synchronize Profiles in Windows 7, Synchronize Profiles in Windows 8, and the Sync PC Settings feature of Microsoft account.</span></span>

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
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="7c8fe-167">功能</span><span class="sxs-lookup"><span data-stu-id="7c8fe-167">Feature</span></span></th>
<th align="left"><span data-ttu-id="7c8fe-168">使用 Windows 7 同步處理設定檔</span><span class="sxs-lookup"><span data-stu-id="7c8fe-168">Synchronize Profiles using Windows 7</span></span></th>
<th align="left"><span data-ttu-id="7c8fe-169">使用 Windows 8 同步處理設定檔</span><span class="sxs-lookup"><span data-stu-id="7c8fe-169">Synchronize Profiles using Windows 8</span></span></th>
<th align="left"><span data-ttu-id="7c8fe-170">使用 Windows 10 同步處理設定檔</span><span class="sxs-lookup"><span data-stu-id="7c8fe-170">Synchronize Profiles using Windows 10</span></span></th>
<th align="left"><span data-ttu-id="7c8fe-171">Microsoft 帳戶</span><span class="sxs-lookup"><span data-stu-id="7c8fe-171">Microsoft account</span></span></th>
<th align="left"><span data-ttu-id="7c8fe-172">UE-V 2。0</span><span class="sxs-lookup"><span data-stu-id="7c8fe-172">UE-V 2.0</span></span></th>
<th align="left"><span data-ttu-id="7c8fe-173">UE-V 2.1 和 2.1 SP1</span><span class="sxs-lookup"><span data-stu-id="7c8fe-173">UE-V 2.1 and 2.1 SP1</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7c8fe-174">同步處理多個電腦之間的設定</span><span class="sxs-lookup"><span data-stu-id="7c8fe-174">Synchronize settings between multiple computers</span></span></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-175">●</span><span class="sxs-lookup"><span data-stu-id="7c8fe-175">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-176">●</span><span class="sxs-lookup"><span data-stu-id="7c8fe-176">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-177">●</span><span class="sxs-lookup"><span data-stu-id="7c8fe-177">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-178">●</span><span class="sxs-lookup"><span data-stu-id="7c8fe-178">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-179">●</span><span class="sxs-lookup"><span data-stu-id="7c8fe-179">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-180">●</span><span class="sxs-lookup"><span data-stu-id="7c8fe-180">●</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="7c8fe-181">在物理與虛擬 app 之間同步處理設定</span><span class="sxs-lookup"><span data-stu-id="7c8fe-181">Synchronize settings between physical and virtual apps</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-182">●</span><span class="sxs-lookup"><span data-stu-id="7c8fe-182">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-183">●</span><span class="sxs-lookup"><span data-stu-id="7c8fe-183">●</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7c8fe-184">同步處理 Windows 應用程式設定</span><span class="sxs-lookup"><span data-stu-id="7c8fe-184">Synchronize Windows app settings</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-185">●</span><span class="sxs-lookup"><span data-stu-id="7c8fe-185">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-186">●</span><span class="sxs-lookup"><span data-stu-id="7c8fe-186">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-187">●</span><span class="sxs-lookup"><span data-stu-id="7c8fe-187">●</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="7c8fe-188">透過 WMI 管理</span><span class="sxs-lookup"><span data-stu-id="7c8fe-188">Manage via WMI</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-189">●</span><span class="sxs-lookup"><span data-stu-id="7c8fe-189">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-190">●</span><span class="sxs-lookup"><span data-stu-id="7c8fe-190">●</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-191">●</span><span class="sxs-lookup"><span data-stu-id="7c8fe-191">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-192">●</span><span class="sxs-lookup"><span data-stu-id="7c8fe-192">●</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7c8fe-193">定期同步處理設定變更</span><span class="sxs-lookup"><span data-stu-id="7c8fe-193">Synchronize settings changes on a regular basis</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-194">●</span><span class="sxs-lookup"><span data-stu-id="7c8fe-194">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-195">●</span><span class="sxs-lookup"><span data-stu-id="7c8fe-195">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-196">●</span><span class="sxs-lookup"><span data-stu-id="7c8fe-196">●</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="7c8fe-197">設定的最低配置</span><span class="sxs-lookup"><span data-stu-id="7c8fe-197">Minimal configuration for Setup</span></span></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-198">●</span><span class="sxs-lookup"><span data-stu-id="7c8fe-198">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-199">●</span><span class="sxs-lookup"><span data-stu-id="7c8fe-199">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-200">●</span><span class="sxs-lookup"><span data-stu-id="7c8fe-200">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-201">●</span><span class="sxs-lookup"><span data-stu-id="7c8fe-201">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-202">●</span><span class="sxs-lookup"><span data-stu-id="7c8fe-202">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-203">●</span><span class="sxs-lookup"><span data-stu-id="7c8fe-203">●</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7c8fe-204">在未加入網域的電腦上支援</span><span class="sxs-lookup"><span data-stu-id="7c8fe-204">Supported on non-domain joined computers</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-205">●</span><span class="sxs-lookup"><span data-stu-id="7c8fe-205">●</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="7c8fe-206">支援主要電腦 Active Directory 屬性</span><span class="sxs-lookup"><span data-stu-id="7c8fe-206">Supports Primary Computer Active Directory attribute</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-207">●</span><span class="sxs-lookup"><span data-stu-id="7c8fe-207">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-208">●</span><span class="sxs-lookup"><span data-stu-id="7c8fe-208">●</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7c8fe-209">在虛擬桌面基礎結構（VDI）/Remote 桌面服務（RDS）與胖桌面之間同步處理設定</span><span class="sxs-lookup"><span data-stu-id="7c8fe-209">Synchronizes settings between virtual desktop infrastructure (VDI)/Remote Desktop Services (RDS) and rich desktops</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-210">●</span><span class="sxs-lookup"><span data-stu-id="7c8fe-210">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-211">●</span><span class="sxs-lookup"><span data-stu-id="7c8fe-211">●</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="7c8fe-212">設定儲存空間無限制</span><span class="sxs-lookup"><span data-stu-id="7c8fe-212">Unlimited setting storage space</span></span></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-213">●</span><span class="sxs-lookup"><span data-stu-id="7c8fe-213">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-214">●</span><span class="sxs-lookup"><span data-stu-id="7c8fe-214">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-215">●</span><span class="sxs-lookup"><span data-stu-id="7c8fe-215">●</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-216">●</span><span class="sxs-lookup"><span data-stu-id="7c8fe-216">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-217">●</span><span class="sxs-lookup"><span data-stu-id="7c8fe-217">●</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7c8fe-218">您可以選擇要同步處理之應用程式設定的選項</span><span class="sxs-lookup"><span data-stu-id="7c8fe-218">Choice in which app settings to synchronize</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-219">●</span><span class="sxs-lookup"><span data-stu-id="7c8fe-219">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-220">●</span><span class="sxs-lookup"><span data-stu-id="7c8fe-220">●</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="7c8fe-221">IT 專業人員的備份/還原</span><span class="sxs-lookup"><span data-stu-id="7c8fe-221">Backup/Restore for IT Pro</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-222">●</span><span class="sxs-lookup"><span data-stu-id="7c8fe-222">●</span></span></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-223">部分</span><span class="sxs-lookup"><span data-stu-id="7c8fe-223">Partial</span></span></p></td>
<td align="left"><p><span data-ttu-id="7c8fe-224">●</span><span class="sxs-lookup"><span data-stu-id="7c8fe-224">●</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="7c8fe-225">UE-V 2. x 版本資訊</span><span class="sxs-lookup"><span data-stu-id="7c8fe-225">UE-V 2.x Release Notes</span></span>


<span data-ttu-id="7c8fe-226">如需詳細資訊，以及未在檔中顯示的最新消息，請參閱</span><span class="sxs-lookup"><span data-stu-id="7c8fe-226">For more information, and for late-breaking news that did not make it into the documentation, see</span></span>

-   [<span data-ttu-id="7c8fe-227">Microsoft User Experience Virtualization (UE-V) 2.1 SP1 版本資訊</span><span class="sxs-lookup"><span data-stu-id="7c8fe-227">Microsoft User Experience Virtualization (UE-V) 2.1 SP1 Release Notes</span></span>](microsoft-user-experience-virtualization--ue-v--21-sp1-release-notes.md)

-   [<span data-ttu-id="7c8fe-228">Microsoft User Experience Virtualization (UE-V) 2.1 版本資訊</span><span class="sxs-lookup"><span data-stu-id="7c8fe-228">Microsoft User Experience Virtualization (UE-V) 2.1 Release Notes</span></span>](microsoft-user-experience-virtualization--ue-v--21-release-notesuevv21.md)

-   [<span data-ttu-id="7c8fe-229">Microsoft User Experience Virtualization (UE-V) 2.0 版本資訊</span><span class="sxs-lookup"><span data-stu-id="7c8fe-229">Microsoft User Experience Virtualization (UE-V) 2.0 Release Notes</span></span>](microsoft-user-experience-virtualization--ue-v--20-release-notesuevv2.md)

## <span data-ttu-id="7c8fe-230">此產品的其他資源</span><span class="sxs-lookup"><span data-stu-id="7c8fe-230">Other resources for this product</span></span>


-   [<span data-ttu-id="7c8fe-231">UE-V 2.x 入門</span><span class="sxs-lookup"><span data-stu-id="7c8fe-231">Get Started with UE-V 2.x</span></span>](get-started-with-ue-v-2x-new-uevv2.md)

-   [<span data-ttu-id="7c8fe-232">準備 UE-V a.x 部署</span><span class="sxs-lookup"><span data-stu-id="7c8fe-232">Prepare a UE-V 2.x Deployment</span></span>](prepare-a-ue-v-2x-deployment-new-uevv2.md)

-   [<span data-ttu-id="7c8fe-233">管理 UE-V 2。</span><span class="sxs-lookup"><span data-stu-id="7c8fe-233">Administering UE-V 2.x</span></span>](administering-ue-v-2x-new-uevv2.md)

-   [<span data-ttu-id="7c8fe-234">疑難排解 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="7c8fe-234">Troubleshooting UE-V 2.x</span></span>](troubleshooting-ue-v-2x-both-uevv2.md)

-   [<span data-ttu-id="7c8fe-235">UE-V 2.x 技術參考</span><span class="sxs-lookup"><span data-stu-id="7c8fe-235">Technical Reference for UE-V 2.x</span></span>](technical-reference-for-ue-v-2x-both-uevv2.md)

### <span data-ttu-id="7c8fe-236">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="7c8fe-236">More information</span></span>

<a href="" id="mdop-techcenter-page"></a><span data-ttu-id="7c8fe-237">[MDOP 技術中心頁面](https://go.microsoft.com/fwlink/p/?LinkId=225286)瞭解最新的 MDOP 資訊和資源。</span><span class="sxs-lookup"><span data-stu-id="7c8fe-237">[MDOP TechCenter Page](https://go.microsoft.com/fwlink/p/?LinkId=225286) Learn about the latest MDOP information and resources.</span></span>

<a href="" id="mdop-information-experience"></a><span data-ttu-id="7c8fe-238">[MDOP 資訊體驗](https://go.microsoft.com/fwlink/p/?LinkId=236032)尋找您的 MDOP 技術的檔、影片及其他資源。</span><span class="sxs-lookup"><span data-stu-id="7c8fe-238">[MDOP Information Experience](https://go.microsoft.com/fwlink/p/?LinkId=236032) Find documentation, videos, and other resources for MDOP technologies.</span></span> <span data-ttu-id="7c8fe-239">您也可以在[Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445)或[Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447)上關注我們，以[傳送意見](mailto:MDOPDocs@microsoft.com)反應或瞭解更新。</span><span class="sxs-lookup"><span data-stu-id="7c8fe-239">You can also [send us feedback](mailto:MDOPDocs@microsoft.com) or learn about updates by following us on [Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445) or [Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447).</span></span>














