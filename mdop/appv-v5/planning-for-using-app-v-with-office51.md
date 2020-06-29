---
title: 為搭配 Office 使用 App-V 進行規劃
description: 為搭配 Office 使用 App-V 進行規劃
author: dansimp
ms.assetid: e7a19b43-1746-469f-bad6-8e75cf4b3f67
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 03/16/2017
ms.openlocfilehash: ae225db3c47faca5fba790fb9963bfd4dc2c66b0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800337"
---
# <span data-ttu-id="6371e-103">為搭配 Office 使用 App-V 進行規劃</span><span class="sxs-lookup"><span data-stu-id="6371e-103">Planning for Using App-V with Office</span></span>


<span data-ttu-id="6371e-104">使用下列資訊來規劃如何使用 Microsoft 應用程式虛擬化（App-v）5.1 部署 Office。</span><span class="sxs-lookup"><span data-stu-id="6371e-104">Use the following information to plan how to deploy Office by using Microsoft Application Virtualization (App-V) 5.1.</span></span> <span data-ttu-id="6371e-105">本文包括：</span><span class="sxs-lookup"><span data-stu-id="6371e-105">This article includes:</span></span>

-   [<span data-ttu-id="6371e-106">語言套件的 app-v 支援</span><span class="sxs-lookup"><span data-stu-id="6371e-106">App-V support for Language Packs</span></span>](#bkmk-lang-pack)

-   [<span data-ttu-id="6371e-107">支援的 Microsoft Office 版本</span><span class="sxs-lookup"><span data-stu-id="6371e-107">Supported versions of Microsoft Office</span></span>](#bkmk-office-vers-supp-appv)

-   [<span data-ttu-id="6371e-108">規劃與共存版本的 Office 一起使用 App-v</span><span class="sxs-lookup"><span data-stu-id="6371e-108">Planning for using App-V with coexisting versions of Office</span></span>](#bkmk-plan-coexisting)

-   [<span data-ttu-id="6371e-109">部署時，Office 與 Windows 整合的方式使用 App-v 部署 Office</span><span class="sxs-lookup"><span data-stu-id="6371e-109">How Office integrates with Windows when you deploy use App-V to deploy Office</span></span>](#bkmk-office-integration-win)

## <a href="" id="bkmk-lang-pack"></a><span data-ttu-id="6371e-110">語言套件的 app-v 支援</span><span class="sxs-lookup"><span data-stu-id="6371e-110">App-V support for Language Packs</span></span>


<span data-ttu-id="6371e-111">您可以使用 App-v 5.1 Sequencer 來建立語言套件、語言介面套件、校訂工具及工具提示語言的外掛程式套件。</span><span class="sxs-lookup"><span data-stu-id="6371e-111">You can use the App-V 5.1 Sequencer to create plug-in packages for Language Packs, Language Interface Packs, Proofing Tools and ScreenTip Languages.</span></span> <span data-ttu-id="6371e-112">接著，您可以在連線群組中包含外掛程式套件，以及使用 Office 部署工具組建立的 Office 2013 套件。</span><span class="sxs-lookup"><span data-stu-id="6371e-112">You can then include the plug-in packages in a Connection Group, along with the Office 2013 package that you create by using the Office Deployment Toolkit.</span></span> <span data-ttu-id="6371e-113">Office 應用程式和外掛程式語言套件在相同的連線群組中無縫互動，就像在連線群組中組成群組的任何其他套件一樣。</span><span class="sxs-lookup"><span data-stu-id="6371e-113">The Office applications and the plug-in Language Packs interact seamlessly in the same connection group, just like any other packages that are grouped together in a connection group.</span></span>

><span data-ttu-id="6371e-114">**記事** Microsoft Visio 與 Microsoft Project 不提供泰語語言套件支援。</span><span class="sxs-lookup"><span data-stu-id="6371e-114">**Note** Microsoft Visio and Microsoft Project do not provide support for the Thai Language Pack.</span></span>

 

## <a href="" id="bkmk-office-vers-supp-appv"></a><span data-ttu-id="6371e-115">支援的 Microsoft Office 版本</span><span class="sxs-lookup"><span data-stu-id="6371e-115">Supported versions of Microsoft Office</span></span>

<span data-ttu-id="6371e-116">請參閱 App-v 針對支援的 Office 產品清單[所支援的 Microsoft Office 產品識別碼](https://support.microsoft.com/help/2842297/product-ids-that-are-supported-by-the-office-deployment-tool-for-click)。</span><span class="sxs-lookup"><span data-stu-id="6371e-116">See [Microsoft Office Product IDs that App-V supports](https://support.microsoft.com/help/2842297/product-ids-that-are-supported-by-the-office-deployment-tool-for-click) for a list of supported Office products.</span></span>
><span data-ttu-id="6371e-117">**Note** &nbsp; 記事 &nbsp;您必須使用 Office 部署工具來為適用于企業的 Microsoft 365 應用程式建立 app-v 套件。</span><span class="sxs-lookup"><span data-stu-id="6371e-117">**Note**&nbsp;&nbsp;You must use the Office Deployment Tool to create App-V packages for Microsoft 365 Apps for enterprise.</span></span> <span data-ttu-id="6371e-118">不支援為大量授權版本的 Office 專業增強版或 Office Standard 建立套件。</span><span class="sxs-lookup"><span data-stu-id="6371e-118">Creating packages for the volume-licensed versions of Office Professional Plus or Office Standard is not supported.</span></span> <span data-ttu-id="6371e-119">您無法使用 App-v 排序器。</span><span class="sxs-lookup"><span data-stu-id="6371e-119">You cannot use the App-V Sequencer.</span></span>

 

## <a href="" id="bkmk-plan-coexisting"></a><span data-ttu-id="6371e-120">規劃與共存版本的 Office 一起使用 App-v</span><span class="sxs-lookup"><span data-stu-id="6371e-120">Planning for using App-V with coexisting versions of Office</span></span>


<span data-ttu-id="6371e-121">您可以在同一部電腦上使用「Microsoft Office 共存」，並排安裝多個版本的 Microsoft Office。</span><span class="sxs-lookup"><span data-stu-id="6371e-121">You can install more than one version of Microsoft Office side by side on the same computer by using “Microsoft Office coexistence.”</span></span> <span data-ttu-id="6371e-122">您可以使用 Windows Installer （MSi）版本的 Office、隨選即用，以及 App-v 5.1，來實現 Office 共存，以及所有主要版本的 Office 與安裝方法的組合（如果適用的話）。</span><span class="sxs-lookup"><span data-stu-id="6371e-122">You can implement Office coexistence with combinations of all major versions of Office and with installation methods, as applicable, by using the Windows Installer-based (MSi) version of Office, Click-to-Run, and App-V 5.1.</span></span> <span data-ttu-id="6371e-123">不過 Microsoft 不建議使用 Office 共存。</span><span class="sxs-lookup"><span data-stu-id="6371e-123">However, using Office coexistence is not recommended by Microsoft.</span></span>

<span data-ttu-id="6371e-124">Microsoft 的建議最佳做法是完全避免 Office 共存，以避免相容性問題。</span><span class="sxs-lookup"><span data-stu-id="6371e-124">Microsoft’s recommended best practice is to avoid Office coexistence completely to prevent compatibility issues.</span></span> <span data-ttu-id="6371e-125">不過，當您遷移至較新版本的 Office 時，偶爾會出現無法立即解決的問題，因此您可以暫時實現共存，協助您更快速地遷移到最新的產品版本。</span><span class="sxs-lookup"><span data-stu-id="6371e-125">However, when you are migrating to a newer version of Office, issues occasionally arise that can’t be resolved immediately, so you can temporarily implement coexistence to help facilitate a faster migration to the latest product version.</span></span> <span data-ttu-id="6371e-126">我們不建議使用長期基礎的 Office 共存，而且您的組織應該有一個計畫在立即進行。</span><span class="sxs-lookup"><span data-stu-id="6371e-126">Using Office coexistence on a long-term basis is never recommended, and your organization should have a plan to fully transition in the immediate future.</span></span>

### <span data-ttu-id="6371e-127">在您實現 Office 共存之前</span><span class="sxs-lookup"><span data-stu-id="6371e-127">Before you implement Office coexistence</span></span>

<span data-ttu-id="6371e-128">在執行 Office 共存之前，請先查看下列 Office 檔。</span><span class="sxs-lookup"><span data-stu-id="6371e-128">Before implementing Office coexistence, review the following Office documentation.</span></span> <span data-ttu-id="6371e-129">選擇對應到最新版本的 Office 的文章，您打算在該文章中實施共存。</span><span class="sxs-lookup"><span data-stu-id="6371e-129">Choose the article that corresponds to the newest version of Office for which you plan to implement coexistence.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6371e-130">Office 版本</span><span class="sxs-lookup"><span data-stu-id="6371e-130">Office version</span></span></th>
<th align="left"><span data-ttu-id="6371e-131">連結至指南</span><span class="sxs-lookup"><span data-stu-id="6371e-131">Link to guidance</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6371e-132">Office 2013</span><span class="sxs-lookup"><span data-stu-id="6371e-132">Office 2013</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2784668" data-raw-source="[Information about how to use Office 2013 suites and programs (MSI deployment) on a computer that is running another version of Office](https://support.microsoft.com/kb/2784668)"><span data-ttu-id="6371e-133">如何在執行其他 Office 版本的電腦上使用 Office 2013 套件與程式（MSI 部署）的相關資訊</span><span class="sxs-lookup"><span data-stu-id="6371e-133">Information about how to use Office 2013 suites and programs (MSI deployment) on a computer that is running another version of Office</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6371e-134">Office 2010</span><span class="sxs-lookup"><span data-stu-id="6371e-134">Office 2010</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2121447" data-raw-source="[Information about how to use Office 2010 suites and programs on a computer that is running another version of Office](https://support.microsoft.com/kb/2121447)"><span data-ttu-id="6371e-135">如何在執行其他 Office 版本的電腦上使用 Office 2010 套件與程式的相關資訊</span><span class="sxs-lookup"><span data-stu-id="6371e-135">Information about how to use Office 2010 suites and programs on a computer that is running another version of Office</span></span></a></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="6371e-136">Office 檔針對 Office 的 Windows 安裝程式（MSi）與隨選即用安裝，提供大量的共存指導方針。</span><span class="sxs-lookup"><span data-stu-id="6371e-136">The Office documentation provides extensive guidance on coexistence for Windows Installer-based (MSi) and Click-to-Run installations of Office.</span></span> <span data-ttu-id="6371e-137">此 App-v 主題的共存是對 Office 指南進行補充，其資訊更特定于 App-v 部署。</span><span class="sxs-lookup"><span data-stu-id="6371e-137">This App-V topic on coexistence supplements the Office guidance with information that is more specific to App-V deployments.</span></span>

### <span data-ttu-id="6371e-138">支援的 Office 共存案例</span><span class="sxs-lookup"><span data-stu-id="6371e-138">Supported Office coexistence scenarios</span></span>

<span data-ttu-id="6371e-139">下表摘要列出支援的共存案例。</span><span class="sxs-lookup"><span data-stu-id="6371e-139">The following tables summarize the supported coexistence scenarios.</span></span> <span data-ttu-id="6371e-140">根據您開始使用的版本和部署方法，以及您要遷移的版本和部署方法來組織它們。</span><span class="sxs-lookup"><span data-stu-id="6371e-140">They are organized according to the version and deployment method you’re starting with and the version and deployment method you are migrating to.</span></span> <span data-ttu-id="6371e-141">在將所有共存解決方案部署到成品物件之前，請務必先完整測試。</span><span class="sxs-lookup"><span data-stu-id="6371e-141">Be sure to fully test all coexistence solutions before deploying them to a production audience.</span></span>

><span data-ttu-id="6371e-142">**記事** Microsoft 不支援在已啟用遠端桌面工作階段主機角色服務的 Windows Server 環境中使用多個版本的 Office。</span><span class="sxs-lookup"><span data-stu-id="6371e-142">**Note** Microsoft does not support the use of multiple versions of Office in Windows Server environments that have the Remote Desktop Session Host role service enabled.</span></span> <span data-ttu-id="6371e-143">若要執行 Office 共存案例，您必須停用此角色服務。</span><span class="sxs-lookup"><span data-stu-id="6371e-143">To run Office coexistence scenarios, you must disable this role service.</span></span>

 

### <span data-ttu-id="6371e-144">Windows 集成 & 的 Office 共存</span><span class="sxs-lookup"><span data-stu-id="6371e-144">Windows integrations & Office coexistence</span></span>

<span data-ttu-id="6371e-145">Windows 安裝程式與隨選即用 Office 安裝方法會與基礎 Windows 作業系統的特定點整合。</span><span class="sxs-lookup"><span data-stu-id="6371e-145">The Windows Installer-based and Click-to-Run Office installation methods integrate with certain points of the underlying Windows operating system.</span></span> <span data-ttu-id="6371e-146">當您使用共存功能時，在兩個 Office 版本之間的一般作業系統整合可能會衝突，從而導致相容性與使用者體驗問題。</span><span class="sxs-lookup"><span data-stu-id="6371e-146">When you use coexistence, common operating system integrations between two Office versions can conflict, causing compatibility and user experience issues.</span></span> <span data-ttu-id="6371e-147">在 App-v 中，您可以將某些版本的 Office 排序，以排除整合，從而將它們「隔離」至作業系統。</span><span class="sxs-lookup"><span data-stu-id="6371e-147">With App-V, you can sequence certain versions of Office to exclude integrations, thereby “isolating” them from the operating system.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left"><span data-ttu-id="6371e-148">在此模式中，App-v 可將這個版本的 Office 排序</span><span class="sxs-lookup"><span data-stu-id="6371e-148">Mode in which App-V can sequence this version of Office</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6371e-149">Office 2007</span><span class="sxs-lookup"><span data-stu-id="6371e-149">Office 2007</span></span></p></td>
<td align="left"><p><span data-ttu-id="6371e-150">永遠不會整合。</span><span class="sxs-lookup"><span data-stu-id="6371e-150">Always non-integrated.</span></span> <span data-ttu-id="6371e-151">App-v 不會提供與虛擬化版本的 Office 2007 有關的任何作業系統整合。</span><span class="sxs-lookup"><span data-stu-id="6371e-151">App-V does not offer any operating system integrations with a virtualized version of Office 2007.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6371e-152">Office 2010</span><span class="sxs-lookup"><span data-stu-id="6371e-152">Office 2010</span></span></p></td>
<td align="left"><p><span data-ttu-id="6371e-153">整合和非整合模式。</span><span class="sxs-lookup"><span data-stu-id="6371e-153">Integrated and non-integrated mode.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6371e-154">Office 2013</span><span class="sxs-lookup"><span data-stu-id="6371e-154">Office 2013</span></span></p></td>
<td align="left"><p><span data-ttu-id="6371e-155">永遠整合。</span><span class="sxs-lookup"><span data-stu-id="6371e-155">Always integrated.</span></span> <span data-ttu-id="6371e-156">Windows 作業系統集成無法停用。</span><span class="sxs-lookup"><span data-stu-id="6371e-156">Windows operating system integrations cannot be disabled.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="6371e-157">Microsoft 建議您只使用一個整合的 Office 實例來部署 Office 共存。</span><span class="sxs-lookup"><span data-stu-id="6371e-157">Microsoft recommends that you deploy Office coexistence with only one integrated Office instance.</span></span> <span data-ttu-id="6371e-158">例如，如果您使用 App-v 來部署 Office 2010 和 Office 2013，您應該在非整合模式中順序排列 Office 2010。</span><span class="sxs-lookup"><span data-stu-id="6371e-158">For example, if you’re using App-V to deploy Office 2010 and Office 2013, you should sequence Office 2010 in non-integrated mode.</span></span> <span data-ttu-id="6371e-159">如需在非整合（獨立）模式中排序 Office 的詳細資訊，請參閱[如何在 Microsoft Application Virtualization 5.0 中排序 Microsoft Office 2010](https://support.microsoft.com/kb/2830069)。</span><span class="sxs-lookup"><span data-stu-id="6371e-159">For more information about sequencing Office in non-integration (isolated) mode, see [How to sequence Microsoft Office 2010 in Microsoft Application Virtualization 5.0](https://support.microsoft.com/kb/2830069).</span></span>

### <span data-ttu-id="6371e-160">Office 共存案例的已知限制</span><span class="sxs-lookup"><span data-stu-id="6371e-160">Known limitations of Office coexistence scenarios</span></span>

<span data-ttu-id="6371e-161">下列各節說明當您使用 App-v 來實現與 Office 的共存時，可能會遇到的一些問題。</span><span class="sxs-lookup"><span data-stu-id="6371e-161">The following sections describe some issues that you might encounter when using App-V to implement coexistence with Office.</span></span>

### <span data-ttu-id="6371e-162">Windows 安裝程式/隨選即用與 App-v Office 共存案例的常見限制</span><span class="sxs-lookup"><span data-stu-id="6371e-162">Limitations common to Windows Installer-based/Click-to-Run and App-V Office coexistence scenarios</span></span>

<span data-ttu-id="6371e-163">當您在同一部電腦上安裝下列版本的 Office 時，可能會發生下列限制：</span><span class="sxs-lookup"><span data-stu-id="6371e-163">The following limitations can occur when you install the following versions of Office on the same computer:</span></span>

-   <span data-ttu-id="6371e-164">使用 Windows 安裝程式的版本建立 Office 2010</span><span class="sxs-lookup"><span data-stu-id="6371e-164">Office 2010 by using the Windows Installer-based version</span></span>

-   <span data-ttu-id="6371e-165">使用 App-v 的 Office 2013</span><span class="sxs-lookup"><span data-stu-id="6371e-165">Office 2013 by using App-V</span></span>

<span data-ttu-id="6371e-166">在您使用 App-v 與舊版 Windows 安裝程式的 Office 2010 發佈 Office 2013 之後，也可能會造成 Windows 安裝程式啟動。</span><span class="sxs-lookup"><span data-stu-id="6371e-166">After you publish Office 2013 by using App-V side by side with an earlier version of the Windows Installer-based Office 2010 might also cause the Windows Installer to start.</span></span> <span data-ttu-id="6371e-167">這是因為 Windows 安裝程式或隨選即用版本的 Office 2010 嘗試自動將自己註冊到電腦。</span><span class="sxs-lookup"><span data-stu-id="6371e-167">This is because the Windows Installer-based or Click-to-Run version of Office 2010 is trying to automatically register itself to the computer.</span></span>

<span data-ttu-id="6371e-168">若要略過原生 Word 2010 的自動註冊作業，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="6371e-168">To bypass the auto-registration operation for native Word 2010, follow these steps:</span></span>

1.  <span data-ttu-id="6371e-169">退出 Word 2010。</span><span class="sxs-lookup"><span data-stu-id="6371e-169">Exit Word 2010.</span></span>

2.  <span data-ttu-id="6371e-170">執行下列動作，啟動 [登錄編輯程式]：</span><span class="sxs-lookup"><span data-stu-id="6371e-170">Start the Registry Editor by doing the following:</span></span>

    -   <span data-ttu-id="6371e-171">在 Windows 7 中：按一下 [**開始**]，在 [開始搜尋] 方塊中輸入**regedit** ，然後按 enter。</span><span class="sxs-lookup"><span data-stu-id="6371e-171">In Windows 7: Click **Start**, type **regedit** in the Start Search box, and then press Enter.</span></span>

    -   <span data-ttu-id="6371e-172">在 Windows 8.1 或 Windows 10 中輸入**regedit** ，然後按下 [開始] 頁面上的 [enter]，然後按 enter。</span><span class="sxs-lookup"><span data-stu-id="6371e-172">In Windows 8.1 or Windows 10, type **regedit** press Enter on the Start page and then press Enter.</span></span>

    <span data-ttu-id="6371e-173">如果系統提示您輸入系統管理員密碼或進行確認，請輸入密碼，或按一下 [**繼續**]。</span><span class="sxs-lookup"><span data-stu-id="6371e-173">If you are prompted for an administrator password or for a confirmation, type the password, or click **Continue**.</span></span>

3.  <span data-ttu-id="6371e-174">找出下列登錄子機碼，然後選取該子項：</span><span class="sxs-lookup"><span data-stu-id="6371e-174">Locate and then select the following registry subkey:</span></span>

    ``` syntax
    HKEY_CURRENT_USER\Software\Microsoft\Office\14.0\Word\Options
    ```

4.  <span data-ttu-id="6371e-175">在 [**編輯**] 功能表上，按一下 [**新增**]，然後按一下 [ **DWORD 值**]。</span><span class="sxs-lookup"><span data-stu-id="6371e-175">On the **Edit** menu, click **New**, and then click **DWORD Value**.</span></span>

5.  <span data-ttu-id="6371e-176">輸入**NoReReg**，然後按 enter。</span><span class="sxs-lookup"><span data-stu-id="6371e-176">Type **NoReReg**, and then press Enter.</span></span>

6.  <span data-ttu-id="6371e-177">以滑鼠右鍵按一下 [ **NoReReg** ]，然後按一下 [**修改**]。</span><span class="sxs-lookup"><span data-stu-id="6371e-177">Right-click **NoReReg** and then click **Modify**.</span></span>

7.  <span data-ttu-id="6371e-178">在 [ **Valuedata** ] 方塊中，輸入**1**，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="6371e-178">In the **Valuedata** box, type **1**, and then click **OK**.</span></span>

8.  <span data-ttu-id="6371e-179">在 [檔案] 功能表上 **，按一下 [** 結束] 來關閉 [登錄編輯程式]。</span><span class="sxs-lookup"><span data-stu-id="6371e-179">On the File menu, click **Exit** to close Registry Editor.</span></span>

## <a href="" id="bkmk-office-integration-win"></a><span data-ttu-id="6371e-180">使用 App-v 部署 Office 時，Office 與 Windows 整合的方式</span><span class="sxs-lookup"><span data-stu-id="6371e-180">How Office integrates with Windows when you use App-V to deploy Office</span></span>


<span data-ttu-id="6371e-181">當您使用 App-v 部署 Office 2013 時，Office 會與作業系統完全整合，這可讓使用者擁有的功能和功能與 Office 在部署但不含 App-v 時一樣。</span><span class="sxs-lookup"><span data-stu-id="6371e-181">When you deploy Office 2013 by using App-V, Office is fully integrated with the operating system, which provides end users with the same features and functionality as Office has when it is deployed without App-V.</span></span>

<span data-ttu-id="6371e-182">Office 2013 App-v 套件支援下列整合點與 Windows 作業系統：</span><span class="sxs-lookup"><span data-stu-id="6371e-182">The Office 2013 App-V package supports the following integration points with the Windows operating system:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6371e-183">延伸點</span><span class="sxs-lookup"><span data-stu-id="6371e-183">Extension Point</span></span></th>
<th align="left"><span data-ttu-id="6371e-184">描述</span><span class="sxs-lookup"><span data-stu-id="6371e-184">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6371e-185">適用于 Firefox 和 Chrome 的 Lync 會議加入外掛程式</span><span class="sxs-lookup"><span data-stu-id="6371e-185">Lync meeting Join Plug-in for Firefox and Chrome</span></span></p></td>
<td align="left"><p><span data-ttu-id="6371e-186">使用者可以從 Firefox 和 Chrome 加入 Lync 會議</span><span class="sxs-lookup"><span data-stu-id="6371e-186">User can join Lync meetings from Firefox and Chrome</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6371e-187">已傳送至 OneNote 列印驅動程式</span><span class="sxs-lookup"><span data-stu-id="6371e-187">Sent to OneNote Print Driver</span></span></p></td>
<td align="left"><p><span data-ttu-id="6371e-188">使用者可以列印至 OneNote</span><span class="sxs-lookup"><span data-stu-id="6371e-188">User can print to OneNote</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6371e-189">OneNote 連結筆記</span><span class="sxs-lookup"><span data-stu-id="6371e-189">OneNote Linked Notes</span></span></p></td>
<td align="left"><p><span data-ttu-id="6371e-190">OneNote 連結筆記</span><span class="sxs-lookup"><span data-stu-id="6371e-190">OneNote Linked Notes</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6371e-191">傳送至 OneNote Internet Explorer 增益集</span><span class="sxs-lookup"><span data-stu-id="6371e-191">Send to OneNote Internet Explorer Add-In</span></span></p></td>
<td align="left"><p><span data-ttu-id="6371e-192">使用者可以從 IE 傳送至 OneNote</span><span class="sxs-lookup"><span data-stu-id="6371e-192">User can send to OneNote from IE</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6371e-193">Lync 和 Outlook 的防火牆例外狀況</span><span class="sxs-lookup"><span data-stu-id="6371e-193">Firewall Exception for Lync and Outlook</span></span></p></td>
<td align="left"><p><span data-ttu-id="6371e-194">Lync 和 Outlook 的防火牆例外狀況</span><span class="sxs-lookup"><span data-stu-id="6371e-194">Firewall Exception for Lync and Outlook</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6371e-195">MAPI 用戶端</span><span class="sxs-lookup"><span data-stu-id="6371e-195">MAPI Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="6371e-196">原生應用程式和增益集可透過 MAPI 與虛擬 Outlook 互動</span><span class="sxs-lookup"><span data-stu-id="6371e-196">Native apps and add-ins can interact with virtual Outlook through MAPI</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6371e-197">適用于 Firefox 的 SharePoint 外掛程式</span><span class="sxs-lookup"><span data-stu-id="6371e-197">SharePoint Plug-in for Firefox</span></span></p></td>
<td align="left"><p><span data-ttu-id="6371e-198">使用者可以在 Firefox 中使用 SharePoint 功能</span><span class="sxs-lookup"><span data-stu-id="6371e-198">User can use SharePoint features in Firefox</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6371e-199">[郵件] 控制台小程式</span><span class="sxs-lookup"><span data-stu-id="6371e-199">Mail Control Panel Applet</span></span></p></td>
<td align="left"><p><span data-ttu-id="6371e-200">使用者在 Outlook 中取得 [郵件] 控制台小程式</span><span class="sxs-lookup"><span data-stu-id="6371e-200">User gets the mail control panel applet in Outlook</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6371e-201">主要 Interop 元件</span><span class="sxs-lookup"><span data-stu-id="6371e-201">Primary Interop Assemblies</span></span></p></td>
<td align="left"><p><span data-ttu-id="6371e-202">支援受管理的增益集</span><span class="sxs-lookup"><span data-stu-id="6371e-202">Support managed add-ins</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6371e-203">Office 檔快取處理常式</span><span class="sxs-lookup"><span data-stu-id="6371e-203">Office Document Cache Handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="6371e-204">允許 Office 應用程式的檔快取</span><span class="sxs-lookup"><span data-stu-id="6371e-204">Allows Document Cache for Office applications</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6371e-205">Outlook 通訊協定搜尋處理常式</span><span class="sxs-lookup"><span data-stu-id="6371e-205">Outlook Protocol Search handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="6371e-206">使用者可以在 outlook 中搜尋</span><span class="sxs-lookup"><span data-stu-id="6371e-206">User can search in outlook</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6371e-207">Active X 控制項：</span><span class="sxs-lookup"><span data-stu-id="6371e-207">Active X Controls:</span></span></p></td>
<td align="left"><p><span data-ttu-id="6371e-208">如需有關 ActiveX 控制項的詳細資訊，請參閱 <a href="https://go.microsoft.com/fwlink/p/?LinkId=331361" data-raw-source="[ActiveX Control API Reference](https://go.microsoft.com/fwlink/p/?LinkId=331361)"> Activex 控制項 API 參考 </a> 。</span><span class="sxs-lookup"><span data-stu-id="6371e-208">For more information on ActiveX controls, refer to <a href="https://go.microsoft.com/fwlink/p/?LinkId=331361" data-raw-source="[ActiveX Control API Reference](https://go.microsoft.com/fwlink/p/?LinkId=331361)">ActiveX Control API Reference</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="6371e-209">Groove. SiteClient</span><span class="sxs-lookup"><span data-stu-id="6371e-209">Groove.SiteClient</span></span></p></td>
<td align="left"><p><span data-ttu-id="6371e-210">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="6371e-210">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="6371e-211">PortalConnect.PersonalSite</span><span class="sxs-lookup"><span data-stu-id="6371e-211">PortalConnect.PersonalSite</span></span></p></td>
<td align="left"><p><span data-ttu-id="6371e-212">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="6371e-212">Active X Control</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="6371e-213">OpenDocuments</span><span class="sxs-lookup"><span data-stu-id="6371e-213">SharePoint.openDocuments</span></span></p></td>
<td align="left"><p><span data-ttu-id="6371e-214">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="6371e-214">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="6371e-215">ExportDatabase</span><span class="sxs-lookup"><span data-stu-id="6371e-215">SharePoint.ExportDatabase</span></span></p></td>
<td align="left"><p><span data-ttu-id="6371e-216">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="6371e-216">Active X Control</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="6371e-217">SpreadSheetLauncher</span><span class="sxs-lookup"><span data-stu-id="6371e-217">SharePoint.SpreadSheetLauncher</span></span></p></td>
<td align="left"><p><span data-ttu-id="6371e-218">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="6371e-218">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="6371e-219">StssyncHander</span><span class="sxs-lookup"><span data-stu-id="6371e-219">SharePoint.StssyncHander</span></span></p></td>
<td align="left"><p><span data-ttu-id="6371e-220">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="6371e-220">Active X Control</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="6371e-221">DragUploadCtl</span><span class="sxs-lookup"><span data-stu-id="6371e-221">SharePoint.DragUploadCtl</span></span></p></td>
<td align="left"><p><span data-ttu-id="6371e-222">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="6371e-222">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="6371e-223">DragDownloadCtl</span><span class="sxs-lookup"><span data-stu-id="6371e-223">SharePoint.DragDownloadCtl</span></span></p></td>
<td align="left"><p><span data-ttu-id="6371e-224">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="6371e-224">Active X Control</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="6371e-225">OpenXMLDocuments</span><span class="sxs-lookup"><span data-stu-id="6371e-225">Sharepoint.OpenXMLDocuments</span></span></p></td>
<td align="left"><p><span data-ttu-id="6371e-226">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="6371e-226">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="6371e-227">ClipboardCtl</span><span class="sxs-lookup"><span data-stu-id="6371e-227">Sharepoint.ClipboardCtl</span></span></p></td>
<td align="left"><p><span data-ttu-id="6371e-228">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="6371e-228">Active X control</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="6371e-229">WinProj Activator</span><span class="sxs-lookup"><span data-stu-id="6371e-229">WinProj.Activator</span></span></p></td>
<td align="left"><p><span data-ttu-id="6371e-230">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="6371e-230">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="6371e-231">NameCtrl</span><span class="sxs-lookup"><span data-stu-id="6371e-231">Name.NameCtrl</span></span></p></td>
<td align="left"><p><span data-ttu-id="6371e-232">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="6371e-232">Active X Control</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="6371e-233">STSUPld.CopyCtl</span><span class="sxs-lookup"><span data-stu-id="6371e-233">STSUPld.CopyCtl</span></span></p></td>
<td align="left"><p><span data-ttu-id="6371e-234">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="6371e-234">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="6371e-235">CommunicatorMeetingJoinAx.JoinManager</span><span class="sxs-lookup"><span data-stu-id="6371e-235">CommunicatorMeetingJoinAx.JoinManager</span></span></p></td>
<td align="left"><p><span data-ttu-id="6371e-236">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="6371e-236">Active X Control</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p>   <span data-ttu-id="6371e-237">LISTNET.Listnet</span><span class="sxs-lookup"><span data-stu-id="6371e-237">LISTNET.Listnet</span></span></p></td>
<td align="left"><p><span data-ttu-id="6371e-238">Active X 控制項</span><span class="sxs-lookup"><span data-stu-id="6371e-238">Active X Control</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p>   <span data-ttu-id="6371e-239">OneDrive 專業版瀏覽器協助程式</span><span class="sxs-lookup"><span data-stu-id="6371e-239">OneDrive Pro Browser Helper</span></span></p></td>
<td align="left"><p><span data-ttu-id="6371e-240">Active X 控制項]</span><span class="sxs-lookup"><span data-stu-id="6371e-240">Active X Control]</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6371e-241">OneDrive Pro 圖示重迭</span><span class="sxs-lookup"><span data-stu-id="6371e-241">OneDrive Pro Icon Overlays</span></span></p></td>
<td align="left"><p><span data-ttu-id="6371e-242">當使用者查看資料夾 OneDrive Pro 資料夾時，Windows Explorer shell 圖示會重迭</span><span class="sxs-lookup"><span data-stu-id="6371e-242">Windows Explorer shell icon overlays when users look at folders OneDrive Pro folders</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6371e-243">殼層延伸</span><span class="sxs-lookup"><span data-stu-id="6371e-243">Shell extensions</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6371e-244">方式</span><span class="sxs-lookup"><span data-stu-id="6371e-244">Shortcuts</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="6371e-245">Windows Search</span><span class="sxs-lookup"><span data-stu-id="6371e-245">Windows Search</span></span></p></td>
<td align="left"><p></p></td>
</tr>
</tbody>
</table>

 






 

 





