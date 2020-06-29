---
title: Microsoft User Experience Virtualization (UE-V) 2.1 SP1 版本資訊
description: Microsoft User Experience Virtualization (UE-V) 2.1 SP1 版本資訊
author: dansimp
ms.assetid: 561988c4-cc5c-4e15-970b-16e942c8f2ef
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 03/30/2017
ms.openlocfilehash: 974914421c61c829b5a32e336bddf8ea1addf514
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811211"
---
# <span data-ttu-id="1ac03-103">Microsoft User Experience Virtualization (UE-V) 2.1 SP1 版本資訊</span><span class="sxs-lookup"><span data-stu-id="1ac03-103">Microsoft User Experience Virtualization (UE-V) 2.1 SP1 Release Notes</span></span>


<span data-ttu-id="1ac03-104">若要搜尋 Microsoft 使用者體驗虛擬化 2.1 SP1 版本資訊，請按 Ctrl + F。</span><span class="sxs-lookup"><span data-stu-id="1ac03-104">To search Microsoft User Experience Virtualization 2.1 SP1 release notes, press Ctrl+F.</span></span>

<span data-ttu-id="1ac03-105">您必須先閱讀這些版本資訊，才能安裝 UE-V。</span><span class="sxs-lookup"><span data-stu-id="1ac03-105">You should read these release notes thoroughly before you install UE-V.</span></span> <span data-ttu-id="1ac03-106">版本資訊包含成功安裝使用者體驗虛擬化所需的資訊，並包含產品檔中不提供的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="1ac03-106">The release notes contain information that is required to successfully install User Experience Virtualization, and contain additional information that is not available in the product documentation.</span></span> <span data-ttu-id="1ac03-107">如果這些版本資訊與其他 UE-V 檔之間有差異，最新的變更應該視為權威性。</span><span class="sxs-lookup"><span data-stu-id="1ac03-107">If there are differences between these release notes and other UE-V documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="1ac03-108">這些版本資訊取代本產品隨附的內容。</span><span class="sxs-lookup"><span data-stu-id="1ac03-108">These release notes supersede the content that is included with this product.</span></span>

## <span data-ttu-id="1ac03-109">提供意見反應</span><span class="sxs-lookup"><span data-stu-id="1ac03-109">Providing feedback</span></span>


<span data-ttu-id="1ac03-110">向我們提供您的意見反應與意見反應，告訴我們您對 MDOP 檔的想法。</span><span class="sxs-lookup"><span data-stu-id="1ac03-110">Tell us what you think about our documentation for MDOP by giving us your feedback and comments.</span></span> <span data-ttu-id="1ac03-111">將您的檔意見反應傳送給[mdopdocs@microsoft.com](mailto:mdopdocs@microsoft.com?subject=UE-V%20Documentation)。</span><span class="sxs-lookup"><span data-stu-id="1ac03-111">Send your documentation feedback to [mdopdocs@microsoft.com](mailto:mdopdocs@microsoft.com?subject=UE-V%20Documentation).</span></span>

## <span data-ttu-id="1ac03-112">UE-V 已知問題</span><span class="sxs-lookup"><span data-stu-id="1ac03-112">UE-V known issues</span></span>


<span data-ttu-id="1ac03-113">本節包含適用于使用者體驗虛擬化 2.1 SP1 的版本資訊。</span><span class="sxs-lookup"><span data-stu-id="1ac03-113">This section contains release notes for User Experience Virtualization 2.1 SP1.</span></span>

### <span data-ttu-id="1ac03-114">用於 Skype 的 UE-V 設定位置範本會造成 Skype 損毀</span><span class="sxs-lookup"><span data-stu-id="1ac03-114">UE-V settings location templates for Skype cause Skype to crash</span></span>

<span data-ttu-id="1ac03-115">當使用者為 Skype 傳統型應用程式產生有效的設定位置範本時，會進行註冊，然後啟動 Skype 桌面應用程式，Skype 會當機。</span><span class="sxs-lookup"><span data-stu-id="1ac03-115">When a user generates a valid settings location template for the Skype desktop application, registers it, and then launches the Skype desktop application, Skype crashes.</span></span> <span data-ttu-id="1ac03-116">會在應用程式事件記錄檔中記錄 [存取 \ _VIOLATION]。</span><span class="sxs-lookup"><span data-stu-id="1ac03-116">An ACCESS\_VIOLATION is recorded in the Application Event Log.</span></span>

<span data-ttu-id="1ac03-117">因應措施：移除或取消註冊 Skype 範本，以允許 Skype 再次運作。</span><span class="sxs-lookup"><span data-stu-id="1ac03-117">WORKAROUND: Remove or unregister the Skype template to allow Skype to work again.</span></span>

### <span data-ttu-id="1ac03-118">自行安裝 UE-V 的現有腳本可能失敗</span><span class="sxs-lookup"><span data-stu-id="1ac03-118">Existing scripts for silent installations of UE-V may fail</span></span>

<span data-ttu-id="1ac03-119">在安裝 UE-V 2.1 SP1 時，對 UE-V 安裝程式所做的兩項變更可能會造成在舊版 UE-V 中使用的緘默安裝腳本無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="1ac03-119">Two changes made to the UE-V installer can cause silent installation scripts that worked for previous versions of UE-V to fail when installing UE-V 2.1 SP1.</span></span> <span data-ttu-id="1ac03-120">第一項是使用者必須接受授權條款並同意或拒絕參與客戶經驗改進計畫（CEIP）的新需求（即使是在緘默安裝期間也一樣）。</span><span class="sxs-lookup"><span data-stu-id="1ac03-120">The first is a new requirement that users must accept the license terms and agree to or decline participation in the Customer Experience Improvement Program (CEIP), even during a silent installation.</span></span> <span data-ttu-id="1ac03-121">使用/q 參數已不再足夠，以表示接受授權條款與合約參與 CEIP。</span><span class="sxs-lookup"><span data-stu-id="1ac03-121">Using the /q parameter is no longer sufficient to indicate acceptance of the license terms and agreement to participate in CEIP.</span></span>

<span data-ttu-id="1ac03-122">其次，安裝程式現在會在安裝 UE-V Agent 之後強制重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="1ac03-122">Second, the installer now forces a computer restart after installing the UE-V Agent.</span></span> <span data-ttu-id="1ac03-123">這可能會導致安裝腳本在不需要重新開機時失敗（例如，它會先安裝 UE-V Agent，然後立即安裝發生器）。</span><span class="sxs-lookup"><span data-stu-id="1ac03-123">This can cause an install script to fail if it is not expecting the restart (for example, it installs the UE-V Agent first and then immediately installs the generator).</span></span>

<span data-ttu-id="1ac03-124">解決方法： UE-V 安裝程式（.msi）有兩個支援緘默安裝的新命令列參數。</span><span class="sxs-lookup"><span data-stu-id="1ac03-124">WORKAROUND: The UE-V installer (.msi) has two new command-line parameters that support silent installations.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="1ac03-125">參數</span><span class="sxs-lookup"><span data-stu-id="1ac03-125">Parameter</span></span></th>
<th align="left"><span data-ttu-id="1ac03-126">描述</span><span class="sxs-lookup"><span data-stu-id="1ac03-126">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="1ac03-127">/ACCEPTLICENSETERMS = True</span><span class="sxs-lookup"><span data-stu-id="1ac03-127">/ACCEPTLICENSETERMS=True</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="1ac03-128">將此參數設定為 <strong> True </strong> 以自行安裝 ue-v。</span><span class="sxs-lookup"><span data-stu-id="1ac03-128">Set this parameter to <strong>True</strong> to install UE-V silently.</span></span> <span data-ttu-id="1ac03-129">新增此參數表示使用者接受在這裡找到（預設為）的 UE-V 授權條款：%ProgramFiles%\Microsoft 使用者體驗 Virtualization\Agent</span><span class="sxs-lookup"><span data-stu-id="1ac03-129">Adding this parameter implies that the user accepts the UE-V license terms, which are found (by default) here: %ProgramFiles%\Microsoft User Experience Virtualization\Agent</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="1ac03-130">/NORESTART</span><span class="sxs-lookup"><span data-stu-id="1ac03-130">/NORESTART</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="1ac03-131">此參數可避免在安裝 UE-V agent 之後強制重新開機。</span><span class="sxs-lookup"><span data-stu-id="1ac03-131">This parameter prevents the mandatory restart after the UE-V agent is installed.</span></span> <span data-ttu-id="1ac03-132">3010的傳回代碼表示在使用 UE-V 之前需要重新開機。</span><span class="sxs-lookup"><span data-stu-id="1ac03-132">A return code of 3010 indicates that a restart is required prior to using UE-V.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="1ac03-133">在同一部電腦上的 App-v 與原生應用程式之間的登錄設定無法同步處理</span><span class="sxs-lookup"><span data-stu-id="1ac03-133">Registry settings do not synchronize between App-V and native applications on the same computer</span></span>

<span data-ttu-id="1ac03-134">當電腦的應用程式是透過應用程式虛擬化（App-v）安裝並在本機使用 Windows Installer （.msi）檔案時，以註冊表為基礎的設定不會在技術之間同步處理。</span><span class="sxs-lookup"><span data-stu-id="1ac03-134">When a computer has an application that is installed through both Application Virtualization (App-V) and locally with a Windows Installer (.msi) file, the registry-based settings do not synchronize between the technologies.</span></span>

<span data-ttu-id="1ac03-135">因應措施：若要解決此問題，請選取其中一種技術來執行應用程式，但不能同時選取兩者。</span><span class="sxs-lookup"><span data-stu-id="1ac03-135">WORKAROUND: To resolve this problem, run the application by selecting one of the two technologies, but not both.</span></span>

### <span data-ttu-id="1ac03-136">已安裝 Office 2010 和 Office 2013 時無法預料的結果</span><span class="sxs-lookup"><span data-stu-id="1ac03-136">Unpredictable results with both Office 2010 and Office 2013 installed</span></span>

<span data-ttu-id="1ac03-137">當使用者同時安裝 Office 2010 和 Office 2013 時，兩個版本的 Office 之間的任何常見設定都是由 UE-V 漫遊。</span><span class="sxs-lookup"><span data-stu-id="1ac03-137">When a user has both Office 2010 and Office 2013 installed, any common settings between the two versions of Office are roamed by UE-V.</span></span> <span data-ttu-id="1ac03-138">這可能會導致 Office 2010 套件大小太大，或導致無法預知的2013衝突，特別是在使用 Office 365 的情況下。</span><span class="sxs-lookup"><span data-stu-id="1ac03-138">This could cause the Office 2010 package size to be quite large or result in unpredictable conflicts with 2013, particularly if Office 365 is used.</span></span>

<span data-ttu-id="1ac03-139">因應措施：只安裝一個 Office 版本，或限制由 UE-V 同步處理哪些設定。</span><span class="sxs-lookup"><span data-stu-id="1ac03-139">WORKAROUND: Install only one version of Office or limit which settings are synchronized by UE-V.</span></span>

### <span data-ttu-id="1ac03-140">卸載並重新安裝 Windows 8 應用程式會將設定還原成初始狀態</span><span class="sxs-lookup"><span data-stu-id="1ac03-140">Uninstall and re-install of Windows 8 app reverts settings to initial state</span></span>

<span data-ttu-id="1ac03-141">在 Windows 8 應用程式使用 UE-V 設定同步處理時，如果使用者卸載應用程式，然後重新安裝應用程式，應用程式的設定就會還原為預設值。</span><span class="sxs-lookup"><span data-stu-id="1ac03-141">While using UE-V settings synchronization for a Windows 8 app, if the user uninstalls the app and then reinstalls the app, the app’s settings revert to their default values.</span></span><span data-ttu-id="1ac03-142">發生這種情況是因為卸載會移除 app 設定的本機（快取）複本，但不會移除本機 UE-V 設定套件。</span><span class="sxs-lookup"><span data-stu-id="1ac03-142"> This happens because the uninstall removes the local (cached) copy of the app’s settings but does not remove the local UE-V settings package.</span></span><span data-ttu-id="1ac03-143">當應用程式重新安裝並啟動時，UE-V 會收集重設為 app 預設值的 app 設定，然後將預設設定上傳到中央儲存位置。</span><span class="sxs-lookup"><span data-stu-id="1ac03-143"> When the app is reinstalled and launched, UE-V gather the app settings that were reset to the app defaults and then uploads the default settings to the central storage location.</span></span><span data-ttu-id="1ac03-144">其他執行 app 的電腦，然後下載預設設定。</span><span class="sxs-lookup"><span data-stu-id="1ac03-144"> Other computers running the app then download the default settings.</span></span><span data-ttu-id="1ac03-145">這種行為與桌面應用程式的行為完全相同。</span><span class="sxs-lookup"><span data-stu-id="1ac03-145"> This behavior is identical to the behavior of desktop applications.</span></span>

<span data-ttu-id="1ac03-146">因應措施：無。</span><span class="sxs-lookup"><span data-stu-id="1ac03-146">WORKAROUND: None.</span></span>

### <span data-ttu-id="1ac03-147">UE-V 不支援32位與64位版本的 Microsoft Office 之間的漫遊設定</span><span class="sxs-lookup"><span data-stu-id="1ac03-147">UE-V does not support roaming settings between 32-bit and 64-bit versions of Microsoft Office</span></span>

<span data-ttu-id="1ac03-148">我們建議您為32位和64位作業系統安裝32位版本的 Microsoft Office。</span><span class="sxs-lookup"><span data-stu-id="1ac03-148">We recommend that you install the 32-bit version of Microsoft Office for both 32-bit and 64-bit operating systems.</span></span> <span data-ttu-id="1ac03-149">若要選擇您需要的 Microsoft Office 版本，請按一下這裡。</span><span class="sxs-lookup"><span data-stu-id="1ac03-149">To choose the Microsoft Office version that you need, click here.</span></span> <span data-ttu-id="1ac03-150">([http://office.microsoft.com/word-help/choose-the-32-bit-or-64-bit-version-of-microsoft-office-HA010369476.aspx](https://go.microsoft.com/fwlink/?LinkID=247623)).</span><span class="sxs-lookup"><span data-stu-id="1ac03-150">([http://office.microsoft.com/word-help/choose-the-32-bit-or-64-bit-version-of-microsoft-office-HA010369476.aspx](https://go.microsoft.com/fwlink/?LinkID=247623)).</span></span> <span data-ttu-id="1ac03-151">UE-V 支援相同架構版本的 Office 間的漫遊設定。</span><span class="sxs-lookup"><span data-stu-id="1ac03-151">UE-V supports roaming settings between identical architecture versions of Office.</span></span> <span data-ttu-id="1ac03-152">例如，32位的 Office 設定將會在所有32位的 Office 實例之間漫遊。</span><span class="sxs-lookup"><span data-stu-id="1ac03-152">For example, 32-bit Office settings will roam between all 32-bit Office instances.</span></span> <span data-ttu-id="1ac03-153">UE-V 不支援32位與64位版本的 Office 之間的漫遊設定。</span><span class="sxs-lookup"><span data-stu-id="1ac03-153">UE-V does not support roaming settings between 32-bit and 64-bit versions of Office.</span></span>

<span data-ttu-id="1ac03-154">因應措施：無</span><span class="sxs-lookup"><span data-stu-id="1ac03-154">WORKAROUND: None</span></span>

### <a href="" id="msi-s-are-not-localized"></a><span data-ttu-id="1ac03-155">MSI 未當地語系化</span><span class="sxs-lookup"><span data-stu-id="1ac03-155">MSI’s are not localized</span></span>

<span data-ttu-id="1ac03-156">UE-V 包含針對 UE-V Agent 和 UE-V 發生器的當地語系化安裝程式。</span><span class="sxs-lookup"><span data-stu-id="1ac03-156">UE-V includes a localized setup program for both the UE-V Agent and UE-V generator.</span></span> <span data-ttu-id="1ac03-157">這些 MSI 檔案仍可供使用，但使用者介面已最小化，且 MSI 只顯示英文。</span><span class="sxs-lookup"><span data-stu-id="1ac03-157">These MSI files are still available but the user interface is minimized and the MSI’s only display in English.</span></span> <span data-ttu-id="1ac03-158">雖然檔案是英文，但安裝程式會在安裝期間安裝所有支援的語言。</span><span class="sxs-lookup"><span data-stu-id="1ac03-158">Despite the file being in English, the setup program installs all supported languages during the installation.</span></span>

<span data-ttu-id="1ac03-159">因應措施：無</span><span class="sxs-lookup"><span data-stu-id="1ac03-159">WORKAROUND: None</span></span>

### <span data-ttu-id="1ac03-160">與 Internet Explorer 9 [我的最愛] 相關聯的 Favicons 不會漫遊</span><span class="sxs-lookup"><span data-stu-id="1ac03-160">Favicons that are associated with Internet Explorer 9 favorites do not roam</span></span>

<span data-ttu-id="1ac03-161">與 Internet Explorer 9 [我的最愛] 相關聯的 favicons 不會受到使用者體驗虛擬化的漫遊，而且在新電腦上出現 [我的最愛] 時不會出現。</span><span class="sxs-lookup"><span data-stu-id="1ac03-161">The favicons that are associated with Internet Explorer 9 favorites are not roamed by User Experience Virtualization and do not appear when the favorites first appear on a new computer.</span></span>

<span data-ttu-id="1ac03-162">因應措施：當您使用書簽並將其放入 Internet Explorer 9 瀏覽器中後，就會顯示 Favicons 的相關連絡人。</span><span class="sxs-lookup"><span data-stu-id="1ac03-162">WORKAROUND: Favicons will appear with their associated favorites once the bookmark is used and cached in the Internet Explorer 9 browser.</span></span>

### <span data-ttu-id="1ac03-163">檔案設定路徑儲存在註冊表中</span><span class="sxs-lookup"><span data-stu-id="1ac03-163">File settings paths are stored in registry</span></span>

<span data-ttu-id="1ac03-164">某些應用程式設定會將其設定和設定檔案的路徑儲存為註冊表中的值。</span><span class="sxs-lookup"><span data-stu-id="1ac03-164">Some application settings store the paths of their configuration and settings files as values in the registry.</span></span> <span data-ttu-id="1ac03-165">當設定在電腦之間漫遊時，必須同步處理在登錄中作為路徑所參照的檔案。</span><span class="sxs-lookup"><span data-stu-id="1ac03-165">The files that are referenced as paths in the registry must be synchronized when settings are roamed between computers.</span></span>

<span data-ttu-id="1ac03-166">因應措施：使用 [資料夾重新導向] 或其他技術，以確保任何被參照為檔案設定路徑的檔案都存在並放在 [設定] 漫遊之所有電腦上的相同位置。</span><span class="sxs-lookup"><span data-stu-id="1ac03-166">WORKAROUND: Use folder redirection or some other technology to ensure that any files that are referenced as file settings paths are present and placed in the same location on all computers where settings roam.</span></span>

### <span data-ttu-id="1ac03-167">較長的設定儲存路徑可能會導致錯誤</span><span class="sxs-lookup"><span data-stu-id="1ac03-167">Long Settings Storage Paths could cause an error</span></span>

<span data-ttu-id="1ac03-168">讓設定的儲存路徑盡可能簡短。</span><span class="sxs-lookup"><span data-stu-id="1ac03-168">Keep settings storage paths as short as possible.</span></span> <span data-ttu-id="1ac03-169">長條路徑可以避免解析度或同步處理。</span><span class="sxs-lookup"><span data-stu-id="1ac03-169">Long paths could prevent resolution or synchronization.</span></span> <span data-ttu-id="1ac03-170">UE-V 會使用設定儲存路徑作為儲存設定的計算路徑的一部分。</span><span class="sxs-lookup"><span data-stu-id="1ac03-170">UE-V uses the Settings storage path as part of the calculated path to store settings.</span></span> <span data-ttu-id="1ac03-171">該路徑的計算方式如下：設定儲存路徑 + "settingspackages" + 套件 dir （template ID） + 套件名稱（範本識別碼） +. pkgx。</span><span class="sxs-lookup"><span data-stu-id="1ac03-171">That path is calculated in the following way: settings storage path + “settingspackages” + package dir (template ID) + package name (template ID) + .pkgx.</span></span> <span data-ttu-id="1ac03-172">如果該計算路徑超過260字元，套件儲存將會失敗，並會在 UE-V 操作事件記錄中產生下列錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="1ac03-172">If that calculated path exceeds 260 characters, package storage will fail and generate the following error message in the UE-V operational event log:</span></span>

`[boost::filesystem::copy_file: The system cannot find the path specified]`

<span data-ttu-id="1ac03-173">若要檢查操作記錄事件，請開啟事件檢視器，然後流覽到應用程式和服務記錄/Microsoft/使用者體驗虛擬化/記錄/運作。</span><span class="sxs-lookup"><span data-stu-id="1ac03-173">To check the operational log events, open the Event Viewer and navigate to Applications and Services Logs / Microsoft / User Experience Virtualization / Logging / Operational.</span></span>

<span data-ttu-id="1ac03-174">因應措施：無。</span><span class="sxs-lookup"><span data-stu-id="1ac03-174">WORKAROUND: None.</span></span>

### <span data-ttu-id="1ac03-175">某些作業系統設定只會在相似的作業系統版本之間漫遊</span><span class="sxs-lookup"><span data-stu-id="1ac03-175">Some operating system settings only roam between like operating system versions</span></span>

<span data-ttu-id="1ac03-176">[朗讀程式] 的作業系統設定和地區專用的貨幣字元（例如 [語言] 和 [地區設定]）只能在 Windows 等作業系統版本中漫遊。</span><span class="sxs-lookup"><span data-stu-id="1ac03-176">Operating system settings for Narrator and currency characters specific to the locale (i.e. language and regional settings) will only roam across like operating system versions of Windows.</span></span> <span data-ttu-id="1ac03-177">例如，貨幣字元將無法在 Windows 7 和 Windows 8 之間漫遊。</span><span class="sxs-lookup"><span data-stu-id="1ac03-177">For example, currency characters will not roam between Windows 7 and Windows 8.</span></span>

<span data-ttu-id="1ac03-178">因應措施：無</span><span class="sxs-lookup"><span data-stu-id="1ac03-178">WORKAROUND: None</span></span>

### <a href="" id="ue-v-1-agent-generates-errors-when-running-ue-v-2-templates-"></a><span data-ttu-id="1ac03-179">UE-V 1 agent 在執行 UE-V 2 範本時會產生錯誤</span><span class="sxs-lookup"><span data-stu-id="1ac03-179">UE-V 1 agent generates errors when running UE-V 2 templates</span></span>

<span data-ttu-id="1ac03-180">如果將 UE-V 2 設定位置範本發佈到與 UE-V 1 agent 一起安裝的電腦，部分設定將無法在電腦之間同步處理，以及在事件記錄檔中報告錯誤。</span><span class="sxs-lookup"><span data-stu-id="1ac03-180">If a UE-V 2 settings location template is distributed to a computer installed with a UE-V 1 agent, some settings fail to synchronize between computers and the agent reports errors in the event log.</span></span>

<span data-ttu-id="1ac03-181">因應措施：從 UE-V 1 遷移到 UE-V 2 時，您可能會在電腦上執行舊版的代理程式，建立個別的 UE-V 2. 編目，以支援 UE-V a.x Agent 和範本。</span><span class="sxs-lookup"><span data-stu-id="1ac03-181">WORKAROUND: When migrating from UE-V 1 to UE-V 2 and it is likely you’ll have computers running the previous version of the agent, create a separate UE-V 2.x catalog to support the UE-V 2.x Agent and templates.</span></span>

### <span data-ttu-id="1ac03-182">UE-V 登出延遲</span><span class="sxs-lookup"><span data-stu-id="1ac03-182">UE-V logoff delay</span></span>

<span data-ttu-id="1ac03-183">在登出時，UE-V 會花很長的時間同步處理設定。</span><span class="sxs-lookup"><span data-stu-id="1ac03-183">Occasionally on logoff, UE-V takes a long time to sync settings.</span></span> <span data-ttu-id="1ac03-184">這通常是由於高延遲網路或不正確使用 Distrubuted 檔案系統（DFS）所造成。</span><span class="sxs-lookup"><span data-stu-id="1ac03-184">Typically, this is due to a high latency network or incorrect use of Distrubuted File System (DFS).</span></span>
<span data-ttu-id="1ac03-185">如需 DFS 支援，請參閱關於[複製的使用者設定檔資料的 Microsoft 支援聲明](https://support.microsoft.com/kb/2533009)，以取得進一步的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="1ac03-185">For DFS support, see [Microsoft’s Support Statement Around Replicated User Profile Data](https://support.microsoft.com/kb/2533009) for further details.</span></span>

<span data-ttu-id="1ac03-186">因應措施：從 HF03 開始，新的登錄機碼已引進下列登錄機碼提供一種機制，讓您可以指定最大的登出延遲 \\Software\\Microsoft\\UEV\\Agent\\Configuration\\LogOffWaitInterval</span><span class="sxs-lookup"><span data-stu-id="1ac03-186">WORKAROUND: Starting with HF03, a new registry key has been introduced The following registry key provides a mechanism by which the maximum logoff delay can be specified \\Software\\Microsoft\\UEV\\Agent\\Configuration\\LogOffWaitInterval</span></span>

<span data-ttu-id="1ac03-187">如需詳細資訊，請參閱[ue-v 註冊表設定](https://support.microsoft.com/kb/2770042)</span><span class="sxs-lookup"><span data-stu-id="1ac03-187">See [UE-V registry settings](https://support.microsoft.com/kb/2770042) for further details</span></span>

## <span data-ttu-id="1ac03-188">UE-V 2.1 SP1 的修補程式和知識庫文章</span><span class="sxs-lookup"><span data-stu-id="1ac03-188">Hotfixes and Knowledge Base articles for UE-V 2.1 SP1</span></span>


<span data-ttu-id="1ac03-189">本節包含適用于 UE-V 2.1 SP1 的修補程式和知識庫文章。</span><span class="sxs-lookup"><span data-stu-id="1ac03-189">This section contains hotfixes and KB articles for UE-V 2.1 SP1.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="1ac03-190">知識庫文章</span><span class="sxs-lookup"><span data-stu-id="1ac03-190">KB Article</span></span></strong></th>
<th align="left"><span data-ttu-id="1ac03-191">Title</span><span class="sxs-lookup"><span data-stu-id="1ac03-191">Title</span></span></th>
<th align="left"><strong><span data-ttu-id="1ac03-192">連結</span><span class="sxs-lookup"><span data-stu-id="1ac03-192">Link</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1ac03-193">3018608</span><span class="sxs-lookup"><span data-stu-id="1ac03-193">3018608</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ac03-194">UE-V 2.1-當缺少 UE-V WMI 類別時，TemplateConsole.exe 會當機</span><span class="sxs-lookup"><span data-stu-id="1ac03-194">UE-V 2.1 - TemplateConsole.exe crashes when UE-V WMI classes are missing</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/3018608/EN-US" data-raw-source="[support.microsoft.com/kb/3018608/EN-US](https://support.microsoft.com/kb/3018608/EN-US)"><span data-ttu-id="1ac03-195">support.microsoft.com/kb/3018608/EN-US</span><span class="sxs-lookup"><span data-stu-id="1ac03-195">support.microsoft.com/kb/3018608/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1ac03-196">2903501</span><span class="sxs-lookup"><span data-stu-id="1ac03-196">2903501</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ac03-197">UE-V：使用者體驗虛擬化（UE-V）與使用者設定檔的相容性</span><span class="sxs-lookup"><span data-stu-id="1ac03-197">UE-V: User Experience Virtualization (UE-V) compatibility with user profiles</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2903501/EN-US" data-raw-source="[support.microsoft.com/kb/2903501/EN-US](https://support.microsoft.com/kb/2903501/EN-US)"><span data-ttu-id="1ac03-198">support.microsoft.com/kb/2903501/EN-US</span><span class="sxs-lookup"><span data-stu-id="1ac03-198">support.microsoft.com/kb/2903501/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1ac03-199">2770042</span><span class="sxs-lookup"><span data-stu-id="1ac03-199">2770042</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ac03-200">UE-V 註冊表設定</span><span class="sxs-lookup"><span data-stu-id="1ac03-200">UE-V Registry Settings</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2770042/EN-US" data-raw-source="[support.microsoft.com/kb/2770042/EN-US](https://support.microsoft.com/kb/2770042/EN-US)"><span data-ttu-id="1ac03-201">support.microsoft.com/kb/2770042/EN-US</span><span class="sxs-lookup"><span data-stu-id="1ac03-201">support.microsoft.com/kb/2770042/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1ac03-202">2847017</span><span class="sxs-lookup"><span data-stu-id="1ac03-202">2847017</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ac03-203">由 Internet Explorer 複製的 UE-V 設定</span><span class="sxs-lookup"><span data-stu-id="1ac03-203">UE-V settings replicated by Internet Explorer</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2847017/EN-US" data-raw-source="[support.microsoft.com/kb/2847017/EN-US](https://support.microsoft.com/kb/2847017/EN-US)"><span data-ttu-id="1ac03-204">support.microsoft.com/kb/2847017/EN-US</span><span class="sxs-lookup"><span data-stu-id="1ac03-204">support.microsoft.com/kb/2847017/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1ac03-205">2769631</span><span class="sxs-lookup"><span data-stu-id="1ac03-205">2769631</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ac03-206">如何修復損毀的 UE-V 安裝</span><span class="sxs-lookup"><span data-stu-id="1ac03-206">How to repair a corrupted UE-V install</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2769631/EN-US" data-raw-source="[support.microsoft.com/kb/2769631/EN-US](https://support.microsoft.com/kb/2769631/EN-US)"><span data-ttu-id="1ac03-207">support.microsoft.com/kb/2769631/EN-US</span><span class="sxs-lookup"><span data-stu-id="1ac03-207">support.microsoft.com/kb/2769631/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1ac03-208">2850989</span><span class="sxs-lookup"><span data-stu-id="1ac03-208">2850989</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ac03-209">不支援使用 Microsoft UE-V 遷移 MAPI 設定檔</span><span class="sxs-lookup"><span data-stu-id="1ac03-209">Migrating MAPI profiles with Microsoft UE-V is not supported</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2850989/EN-US" data-raw-source="[support.microsoft.com/kb/2850989/EN-US](https://support.microsoft.com/kb/2850989/EN-US)"><span data-ttu-id="1ac03-210">support.microsoft.com/kb/2850989/EN-US</span><span class="sxs-lookup"><span data-stu-id="1ac03-210">support.microsoft.com/kb/2850989/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1ac03-211">2769586</span><span class="sxs-lookup"><span data-stu-id="1ac03-211">2769586</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ac03-212">UE-V 會漫遊空白資料夾和登錄機碼</span><span class="sxs-lookup"><span data-stu-id="1ac03-212">UE-V roams empty folders and registry keys</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2769586/EN-US" data-raw-source="[support.microsoft.com/kb/2769586/EN-US](https://support.microsoft.com/kb/2769586/EN-US)"><span data-ttu-id="1ac03-213">support.microsoft.com/kb/2769586/EN-US</span><span class="sxs-lookup"><span data-stu-id="1ac03-213">support.microsoft.com/kb/2769586/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1ac03-214">2782997</span><span class="sxs-lookup"><span data-stu-id="1ac03-214">2782997</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ac03-215">如何在 Microsoft 使用者體驗虛擬化（UE-V）中啟用調試記錄</span><span class="sxs-lookup"><span data-stu-id="1ac03-215">How To Enable Debug Logging in Microsoft User Experience Virtualization (UE-V)</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2782997/EN-US" data-raw-source="[support.microsoft.com/kb/2782997/EN-US](https://support.microsoft.com/kb/2782997/EN-US)"><span data-ttu-id="1ac03-216">support.microsoft.com/kb/2782997/EN-US</span><span class="sxs-lookup"><span data-stu-id="1ac03-216">support.microsoft.com/kb/2782997/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1ac03-217">2769570</span><span class="sxs-lookup"><span data-stu-id="1ac03-217">2769570</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ac03-218">UE-V 不會在 RDS 或 VDI 會話上更新主題</span><span class="sxs-lookup"><span data-stu-id="1ac03-218">UE-V does not update the theme on RDS or VDI sessions</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2769570/EN-US" data-raw-source="[support.microsoft.com/kb/2769570/EN-US](https://support.microsoft.com/kb/2769570/EN-US)"><span data-ttu-id="1ac03-219">support.microsoft.com/kb/2769570/EN-US</span><span class="sxs-lookup"><span data-stu-id="1ac03-219">support.microsoft.com/kb/2769570/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1ac03-220">2850582</span><span class="sxs-lookup"><span data-stu-id="1ac03-220">2850582</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ac03-221">如何在 App V 應用程式中使用 Microsoft 使用者體驗虛擬化</span><span class="sxs-lookup"><span data-stu-id="1ac03-221">How To Use Microsoft User Experience Virtualization With App-V Applications</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2850582/EN-US" data-raw-source="[support.microsoft.com/kb/2850582/EN-US](https://support.microsoft.com/kb/2850582/EN-US)"><span data-ttu-id="1ac03-222">support.microsoft.com/kb/2850582/EN-US</span><span class="sxs-lookup"><span data-stu-id="1ac03-222">support.microsoft.com/kb/2850582/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1ac03-223">3041879</span><span class="sxs-lookup"><span data-stu-id="1ac03-223">3041879</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ac03-224">Microsoft 使用者體驗虛擬化的目前檔版本</span><span class="sxs-lookup"><span data-stu-id="1ac03-224">Current file versions for Microsoft User Experience Virtualization</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/3041879/EN-US" data-raw-source="[support.microsoft.com/kb/3041879/EN-US](https://support.microsoft.com/kb/3041879/EN-US)"><span data-ttu-id="1ac03-225">support.microsoft.com/kb/3041879/EN-US</span><span class="sxs-lookup"><span data-stu-id="1ac03-225">support.microsoft.com/kb/3041879/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1ac03-226">2843592</span><span class="sxs-lookup"><span data-stu-id="1ac03-226">2843592</span></span></p></td>
<td align="left"><p><span data-ttu-id="1ac03-227">使用者體驗虛擬化與高可用性的相關資訊</span><span class="sxs-lookup"><span data-stu-id="1ac03-227">Information on User Experience Virtualization and High Availability</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2843592/EN-US" data-raw-source="[support.microsoft.com/kb/2843592/EN-US](https://support.microsoft.com/kb/2843592/EN-US)"><span data-ttu-id="1ac03-228">support.microsoft.com/kb/2843592/EN-US</span><span class="sxs-lookup"><span data-stu-id="1ac03-228">support.microsoft.com/kb/2843592/EN-US</span></span></a></p></td>
</tr>
</tbody>
</table>

 






 

 





