---
title: Microsoft User Experience Virtualization (UE-V) 2.0 版本資訊
description: Microsoft User Experience Virtualization (UE-V) 2.0 版本資訊
author: dansimp
ms.assetid: 5ef66cd1-ba2b-4383-9f45-e7cde41f1ba1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ad3deffa5cd567a70711e5447197e630f04ea254
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811061"
---
# <span data-ttu-id="c4ef1-103">Microsoft User Experience Virtualization (UE-V) 2.0 版本資訊</span><span class="sxs-lookup"><span data-stu-id="c4ef1-103">Microsoft User Experience Virtualization (UE-V) 2.0 Release Notes</span></span>


<span data-ttu-id="c4ef1-104">若要搜尋 Microsoft 使用者體驗虛擬化（UE-V）2.0 版本資訊，請按 Ctrl + F。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-104">To search Microsoft User Experience Virtualization (UE-V) 2.0 release notes, press Ctrl+F.</span></span>

<span data-ttu-id="c4ef1-105">您必須先閱讀這些版本資訊，才能安裝 UE-V。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-105">You should read these release notes thoroughly before you install UE-V.</span></span> <span data-ttu-id="c4ef1-106">版本資訊包含成功安裝使用者體驗虛擬化所需的資訊，並包含產品檔中不提供的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-106">The release notes contain information that is required to successfully install User Experience Virtualization, and contain additional information that is not available in the product documentation.</span></span> <span data-ttu-id="c4ef1-107">如果這些版本資訊與其他 UE-V 檔之間有差異，最新的變更應該視為權威性。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-107">If there are differences between these release notes and other UE-V documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="c4ef1-108">這些版本資訊取代本產品隨附的內容。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-108">These release notes supersede the content that is included with this product.</span></span>

## <span data-ttu-id="c4ef1-109">提供意見反應</span><span class="sxs-lookup"><span data-stu-id="c4ef1-109">Providing feedback</span></span>


<span data-ttu-id="c4ef1-110">向我們提供您的意見反應與意見反應，告訴我們您對 MDOP 檔的想法。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-110">Tell us what you think about our documentation for MDOP by giving us your feedback and comments.</span></span> <span data-ttu-id="c4ef1-111">將您的檔意見反應傳送給[mdopdocs@microsoft.com](mailto:mdopdocs@microsoft.com?subject=UE-V%20Documentation)。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-111">Send your documentation feedback to [mdopdocs@microsoft.com](mailto:mdopdocs@microsoft.com?subject=UE-V%20Documentation).</span></span>

## <span data-ttu-id="c4ef1-112">UE-V 已知問題</span><span class="sxs-lookup"><span data-stu-id="c4ef1-112">UE-V known issues</span></span>


<span data-ttu-id="c4ef1-113">本節包含適用于使用者體驗虛擬化的版本資訊。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-113">This section contains release notes for User Experience Virtualization.</span></span>

### <span data-ttu-id="c4ef1-114">在同一部電腦上的 App-v 與原生應用程式之間的登錄設定無法同步處理</span><span class="sxs-lookup"><span data-stu-id="c4ef1-114">Registry settings do not synchronize between App-V and native applications on the same computer</span></span>

<span data-ttu-id="c4ef1-115">當電腦的應用程式是透過應用程式虛擬化（App-v）安裝並在本機使用 Windows Installer （.msi）檔案時，以註冊表為基礎的設定不會在技術之間同步處理。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-115">When a computer has an application that is installed through both Application Virtualization (App-V) and a locally with a Windows Installer (.msi) file, the registry-based settings do not synchronize between the technologies.</span></span>

<span data-ttu-id="c4ef1-116">因應措施 **：** 若要解決此問題，請選取其中一種技術來執行應用程式，但不能同時選取這兩者。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-116">**WORKAROUND:** To resolve this problem, run the application by selecting one of the two technologies, but not both.</span></span>

### <a href="" id="settings-do-not-synchronization-when-network-share-is-outside-user-s-domain"></a><span data-ttu-id="c4ef1-117">當網路共用超出使用者網域時，設定不會同步處理</span><span class="sxs-lookup"><span data-stu-id="c4ef1-117">Settings do not synchronization when network share is outside user’s domain</span></span>

<span data-ttu-id="c4ef1-118">當 Windows®8嘗試作業系統設定同步處理時，同步處理失敗，並出現下列錯誤訊息：**提升：： filesystem：：存在：：不正確的使用者名稱或密碼**。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-118">When Windows® 8 attempts operating system settings synchronization, the synchronization fails with the following error message: **boost::filesystem::exists::Incorrect user name or password**.</span></span> <span data-ttu-id="c4ef1-119">這個錯誤可能表示網路共用是在使用者網域以外，或是具有該網域之信任關係的網域。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-119">This error can indicate that the network share is outside the user’s domain or a domain with a trust relationship to that domain.</span></span> <span data-ttu-id="c4ef1-120">若要檢查作業記錄事件，請開啟**事件檢視器**，然後流覽到**應用程式和服務記錄**  /  **Microsoft**  /  **使用者體驗虛擬化**  /  **記錄**作業  /  **運作**。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-120">To check for operational log events, open the **Event Viewer** and navigate to **Applications and Services Logs** / **Microsoft** / **User Experience Virtualization** / **Logging** / **Operational**.</span></span> <span data-ttu-id="c4ef1-121">UE-V 設定儲存位置所用的網路共用，應該位於同一個 Active Directory 網域中，作為使用者或使用者網域的信任網域。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-121">Network shares that are used for UE-V settings storage locations should reside in the same Active Directory domain as the user or a trusted domain of the user’s domain.</span></span>

<span data-ttu-id="c4ef1-122">因應措施 **：** 使用與使用者相同 Active Directory 網域的網路共用。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-122">**WORKAROUND:** Use network shares from the same Active Directory domain as the user.</span></span>

### <span data-ttu-id="c4ef1-123">已安裝 Office 2010 和 Office 2013 時無法預料的結果</span><span class="sxs-lookup"><span data-stu-id="c4ef1-123">Unpredictable results with both Office 2010 and Office 2013 installed</span></span>

<span data-ttu-id="c4ef1-124">當使用者同時安裝 Office 2010 和 Office 2013 時，兩個版本的 Office 之間的任何常見設定都是由 UE-V 漫遊。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-124">When a user has both Office 2010 and Office 2013 installed, any common settings between the two versions of Office are roamed by UE-V.</span></span> <span data-ttu-id="c4ef1-125">這可能會導致 Office 2010 套件大小太大，或導致無法預知的2013衝突，特別是在使用 Office 365 的情況下。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-125">This could cause the Office 2010 package size to be quite large or result in unpredictable conflicts with 2013, particularly if Office 365 is used.</span></span>

<span data-ttu-id="c4ef1-126">因應措施 **：** 只安裝一個 Office 版本或限制哪些設定是由 UE-V 同步處理。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-126">**WORKAROUND:** Install only one version of Office or limit which settings are synchronized by UE-V.</span></span>

### <span data-ttu-id="c4ef1-127">卸載並重新安裝 Windows 8 應用程式會將設定還原成初始狀態</span><span class="sxs-lookup"><span data-stu-id="c4ef1-127">Uninstall and re-install of Windows 8 app reverts settings to initial state</span></span>

<span data-ttu-id="c4ef1-128">在 Windows 8 應用程式使用 UE-V 設定同步處理時，如果使用者卸載應用程式，然後重新安裝應用程式，應用程式的設定就會還原為預設值。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-128">While using UE-V settings synchronization for a Windows 8 app, if the user uninstalls the app and then reinstalls the app, the app’s settings revert to their default values.</span></span><span data-ttu-id="c4ef1-129">發生這種情況是因為卸載會移除 app 設定的本機（快取）複本，但不會移除本機 UE-V 設定套件。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-129"> This happens because the uninstall removes the local (cached) copy of the app’s settings but does not remove the local UE-V settings package.</span></span><span data-ttu-id="c4ef1-130">當應用程式重新安裝並啟動時，UE-V 會收集重設為 app 預設值的 app 設定，然後將預設設定上傳到中央儲存位置。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-130"> When the app is reinstalled and launched, UE-V gather the app settings that were reset to the app defaults and then uploads the default settings to the central storage location.</span></span><span data-ttu-id="c4ef1-131">其他執行 app 的電腦，然後下載預設設定。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-131"> Other computers running the app then download the default settings.</span></span><span data-ttu-id="c4ef1-132">這種行為與桌面應用程式的行為完全相同。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-132"> This behavior is identical to the behavior of desktop applications.</span></span>

<span data-ttu-id="c4ef1-133">因應措施 **：** 所有.</span><span class="sxs-lookup"><span data-stu-id="c4ef1-133">**WORKAROUND:** None.</span></span>

### <span data-ttu-id="c4ef1-134">Outlook 2010 的電子郵件簽名漫遊</span><span class="sxs-lookup"><span data-stu-id="c4ef1-134">Email signature roaming for Outlook 2010</span></span>

<span data-ttu-id="c4ef1-135">UE-V 會在裝置之間漫遊 Outlook 2010 簽名檔案。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-135">UE-V will roam the Outlook 2010 signature files between devices.</span></span> <span data-ttu-id="c4ef1-136">不過，新郵件和回復或轉寄的預設簽章選項不會同步處理。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-136">However, the default signature options for new messages and replies or forwards are not synchronized.</span></span> <span data-ttu-id="c4ef1-137">這兩個設定會儲存在 Outlook 設定檔中，而 UE-V 不會漫遊。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-137">These two settings are stored in the Outlook profile, which UE-V does not roam.</span></span>

<span data-ttu-id="c4ef1-138">因應措施 **：** 所有.</span><span class="sxs-lookup"><span data-stu-id="c4ef1-138">**WORKAROUND:** None.</span></span>

### <span data-ttu-id="c4ef1-139">UE-V 不支援32位與64位版本的 Microsoft Office 之間的漫遊設定</span><span class="sxs-lookup"><span data-stu-id="c4ef1-139">UE-V does not support roaming settings between 32-bit and 64-bit versions of Microsoft Office</span></span>

<span data-ttu-id="c4ef1-140">我們建議您安裝適用于新式電腦的64位版本的 Microsoft Office。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-140">We recommend that you install the 64-bit version of Microsoft Office for modern computers.</span></span> <span data-ttu-id="c4ef1-141">若要判斷您需要哪個版本，請[按一下這裡](https://support.office.com/article/choose-between-the-64-bit-or-32-bit-version-of-office-2dee7807-8f95-4d0c-b5fe-6c6f49b8d261?ui=en-US&rs=en-US&ad=US#32or64Bit=Newer_Versions)。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-141">To determine which version you need, [click here](https://support.office.com/article/choose-between-the-64-bit-or-32-bit-version-of-office-2dee7807-8f95-4d0c-b5fe-6c6f49b8d261?ui=en-US&rs=en-US&ad=US#32or64Bit=Newer_Versions).</span></span> <span data-ttu-id="c4ef1-142">UE-V 支援相同架構版本的 Office 間的漫遊設定。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-142">UE-V supports roaming settings between identical architecture versions of Office.</span></span> <span data-ttu-id="c4ef1-143">例如，32位的 Office 設定將會在所有32位的 Office 實例之間漫遊。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-143">For example, 32-bit Office settings will roam between all 32-bit Office instances.</span></span> <span data-ttu-id="c4ef1-144">UE-V 不支援32位與64位版本的 Office 之間的漫遊設定。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-144">UE-V does not support roaming settings between 32-bit and 64-bit versions of Office.</span></span>

<span data-ttu-id="c4ef1-145">因應措施 **：** 所有</span><span class="sxs-lookup"><span data-stu-id="c4ef1-145">**WORKAROUND:** None</span></span>

### <a href="" id="msi-s-are-not-localized"></a><span data-ttu-id="c4ef1-146">MSI 未當地語系化</span><span class="sxs-lookup"><span data-stu-id="c4ef1-146">MSI’s are not localized</span></span>

<span data-ttu-id="c4ef1-147">UE-V 2.0 包含 UE-V Agent 與 UE-V 發生器的當地語系化安裝程式。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-147">UE-V 2.0 includes a localized setup program for both the UE-V Agent and UE-V generator.</span></span> <span data-ttu-id="c4ef1-148">這些 MSI 檔案仍可供使用，但使用者介面已最小化，且 MSI 只顯示英文。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-148">These MSI files are still available but the user interface is minimized and the MSI’s only display in English.</span></span> <span data-ttu-id="c4ef1-149">雖然檔案是英文，但安裝程式會在安裝期間安裝所有支援的語言。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-149">Despite the file being in English, the setup program installs all supported languages during the installation.</span></span>

<span data-ttu-id="c4ef1-150">因應措施 **：** 所有</span><span class="sxs-lookup"><span data-stu-id="c4ef1-150">**WORKAROUND:** None</span></span>

### <span data-ttu-id="c4ef1-151">與 Internet Explorer 9 [我的最愛] 相關聯的 Favicons 不會漫遊</span><span class="sxs-lookup"><span data-stu-id="c4ef1-151">Favicons that are associated with Internet Explorer 9 favorites do not roam</span></span>

<span data-ttu-id="c4ef1-152">與 Internet Explorer 9 [我的最愛] 相關聯的 favicons 不會受到使用者體驗虛擬化的漫遊，而且在新電腦上出現 [我的最愛] 時不會出現。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-152">The favicons that are associated with Internet Explorer 9 favorites are not roamed by User Experience Virtualization and do not appear when the favorites first appear on a new computer.</span></span>

<span data-ttu-id="c4ef1-153">因應措施 **：** 在 Internet Explorer 9 瀏覽器中使用書簽並將其放入後，Favicons 就會顯示關聯的 [我的最愛]。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-153">**WORKAROUND:** Favicons will appear with their associated favorites once the bookmark is used and cached in the Internet Explorer 9 browser.</span></span>

### <span data-ttu-id="c4ef1-154">檔案設定路徑儲存在註冊表中</span><span class="sxs-lookup"><span data-stu-id="c4ef1-154">File settings paths are stored in registry</span></span>

<span data-ttu-id="c4ef1-155">某些應用程式設定會將其設定和設定檔案的路徑儲存為註冊表中的值。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-155">Some application settings store the paths of their configuration and settings files as values in the registry.</span></span> <span data-ttu-id="c4ef1-156">當設定在電腦之間漫遊時，必須同步處理在登錄中作為路徑所參照的檔案。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-156">The files that are referenced as paths in the registry must be synchronized when settings are roamed between computers.</span></span>

<span data-ttu-id="c4ef1-157">因應措施 **：** 使用 [資料夾重新導向] 或其他一些技術，以確保任何被參照為檔案設定路徑的檔案，都存在並放在 [設定] 漫遊之所有電腦上的相同位置。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-157">**WORKAROUND:** Use folder redirection or some other technology to ensure that any files that are referenced as file settings paths are present and placed in the same location on all computers where settings roam.</span></span>

### <span data-ttu-id="c4ef1-158">較長的設定儲存路徑可能會導致錯誤</span><span class="sxs-lookup"><span data-stu-id="c4ef1-158">Long Settings Storage Paths could cause an error</span></span>

<span data-ttu-id="c4ef1-159">讓設定的儲存路徑盡可能簡短。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-159">Keep settings storage paths as short as possible.</span></span> <span data-ttu-id="c4ef1-160">長條路徑可以避免解析度或同步處理。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-160">Long paths could prevent resolution or synchronization.</span></span> <span data-ttu-id="c4ef1-161">UE-V 會使用設定儲存路徑作為儲存設定的計算路徑的一部分。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-161">UE-V uses the Settings storage path as part of the calculated path to store settings.</span></span> <span data-ttu-id="c4ef1-162">該路徑的計算方式如下：設定儲存路徑 + "settingspackages" + 套件 dir （template ID） + 套件名稱（範本識別碼） +. pkgx。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-162">That path is calculated in the following way: settings storage path + “settingspackages” + package dir (template ID) + package name (template ID) + .pkgx.</span></span> <span data-ttu-id="c4ef1-163">如果該計算路徑超過260字元，套件儲存將會失敗，並會在 UE-V 操作事件記錄中產生下列錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="c4ef1-163">If that calculated path exceeds 260 characters, package storage will fail and generate the following error message in the UE-V operational event log:</span></span>

`[boost::filesystem::copy_file: The system cannot find the path specified]`

<span data-ttu-id="c4ef1-164">若要檢查操作記錄事件，請開啟事件檢視器，然後流覽到應用程式和服務記錄/Microsoft/使用者體驗虛擬化/記錄/運作。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-164">To check the operational log events, open the Event Viewer and navigate to Applications and Services Logs / Microsoft / User Experience Virtualization / Logging / Operational.</span></span>

<span data-ttu-id="c4ef1-165">因應措施 **：** 所有.</span><span class="sxs-lookup"><span data-stu-id="c4ef1-165">**WORKAROUND:** None.</span></span>

### <span data-ttu-id="c4ef1-166">某些作業系統設定只會在相似的作業系統版本之間漫遊</span><span class="sxs-lookup"><span data-stu-id="c4ef1-166">Some operating system settings only roam between like operating system versions</span></span>

<span data-ttu-id="c4ef1-167">[朗讀程式] 的作業系統設定和地區專用的貨幣字元（例如 [語言] 和 [地區設定]）只能在 Windows 等作業系統版本中漫遊。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-167">Operating system settings for Narrator and currency characters specific to the locale (i.e. language and regional settings) will only roam across like operating system versions of Windows.</span></span> <span data-ttu-id="c4ef1-168">例如，貨幣字元將無法在 Windows 7 和 Windows 8 之間漫遊。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-168">For example, currency characters will not roam between Windows 7 and Windows 8.</span></span>

<span data-ttu-id="c4ef1-169">因應措施 **：** 所有</span><span class="sxs-lookup"><span data-stu-id="c4ef1-169">**WORKAROUND:** None</span></span>

### <span data-ttu-id="c4ef1-170">當應用程式在意外關閉後重新開機時，Windows 8 應用程式不會同步處理設定</span><span class="sxs-lookup"><span data-stu-id="c4ef1-170">Windows 8 apps do not sync settings when the app restarts after closing unexpectedly</span></span>

<span data-ttu-id="c4ef1-171">如果 Windows 8 應用程式在啟動後意外關閉，則重新開機應用程式時，可能無法同步處理應用程式的設定。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-171">If a Windows 8 app closes unexpectedly soon after startup, settings for the application may not be synchronized when the application is restarted.</span></span>

<span data-ttu-id="c4ef1-172">因應措施 **：** 關閉 Windows 8 應用程式，關閉並重新啟動 UevAppMonitor.exe 應用程式（可以使用 TaskManager），然後重新開機 Windows 8 應用程式。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-172">**WORKAROUND:** Close the Windows 8 app, close and restart the UevAppMonitor.exe application (can use TaskManager), and then restart the Windows 8 app.</span></span>

### <a href="" id="ue-v-1-agent-generates-errors-when-running-ue-v-2-templates-"></a><span data-ttu-id="c4ef1-173">UE-V 1 agent 在執行 UE-V 2 範本時會產生錯誤</span><span class="sxs-lookup"><span data-stu-id="c4ef1-173">UE-V 1 agent generates errors when running UE-V 2 templates</span></span>

<span data-ttu-id="c4ef1-174">如果將 UE-V 2 設定位置範本發佈到與 UE-V 1 agent 一起安裝的電腦，部分設定將無法在電腦之間同步處理，以及在事件記錄檔中報告錯誤。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-174">If a UE-V 2 settings location template is distributed to a computer installed with a UE-V 1 agent, some settings fail to synchronize between computers and the agent reports errors in the event log.</span></span>

<span data-ttu-id="c4ef1-175">因應措施 **：** 從 UE-V 1 遷移到 UE-V 2 時，您可能會有電腦在執行舊版的代理程式，建立個別的 UE-V 2.0 目錄來支援 UE-V 2.0 代理程式和範本。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-175">**WORKAROUND:** When migrating from UE-V 1 to UE-V 2 and it is likely you’ll have computers running the previous version of the agent, create a separate UE-V 2.0 catalog to support the UE-V 2.0 Agent and templates.</span></span>

## <span data-ttu-id="c4ef1-176">UE-V 2.0 的修補程式和知識庫文章</span><span class="sxs-lookup"><span data-stu-id="c4ef1-176">Hotfixes and Knowledge Base articles for UE-V 2.0</span></span>


<span data-ttu-id="c4ef1-177">本節包含適用于 UE-V 2.0 的修補程式和知識庫文章。</span><span class="sxs-lookup"><span data-stu-id="c4ef1-177">This section contains hotfixes and KB articles for UE-V 2.0.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="c4ef1-178">知識庫文章</span><span class="sxs-lookup"><span data-stu-id="c4ef1-178">KB Article</span></span></strong></th>
<th align="left"><span data-ttu-id="c4ef1-179">Title</span><span class="sxs-lookup"><span data-stu-id="c4ef1-179">Title</span></span></th>
<th align="left"><strong><span data-ttu-id="c4ef1-180">連結</span><span class="sxs-lookup"><span data-stu-id="c4ef1-180">Link</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c4ef1-181">2927019</span><span class="sxs-lookup"><span data-stu-id="c4ef1-181">2927019</span></span></p></td>
<td align="left"><p><span data-ttu-id="c4ef1-182">Microsoft 使用者體驗虛擬化2.0 的修補程式套件1</span><span class="sxs-lookup"><span data-stu-id="c4ef1-182">Hotfix Package 1 for Microsoft User Experience Virtualization 2.0</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2927019" data-raw-source="[support.microsoft.com/kb/2927019](https://support.microsoft.com/kb/2927019)"><span data-ttu-id="c4ef1-183">support.microsoft.com/kb/2927019</span><span class="sxs-lookup"><span data-stu-id="c4ef1-183">support.microsoft.com/kb/2927019</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c4ef1-184">2903501</span><span class="sxs-lookup"><span data-stu-id="c4ef1-184">2903501</span></span></p></td>
<td align="left"><p><span data-ttu-id="c4ef1-185">UE-V：使用者體驗虛擬化（UE-V）與使用者設定檔的相容性</span><span class="sxs-lookup"><span data-stu-id="c4ef1-185">UE-V: User Experience Virtualization (UE-V) compatibility with user profiles</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2903501/EN-US" data-raw-source="[support.microsoft.com/kb/2903501/EN-US](https://support.microsoft.com/kb/2903501/EN-US)"><span data-ttu-id="c4ef1-186">support.microsoft.com/kb/2903501/EN-US</span><span class="sxs-lookup"><span data-stu-id="c4ef1-186">support.microsoft.com/kb/2903501/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c4ef1-187">2770042</span><span class="sxs-lookup"><span data-stu-id="c4ef1-187">2770042</span></span></p></td>
<td align="left"><p><span data-ttu-id="c4ef1-188">UE-V 註冊表設定</span><span class="sxs-lookup"><span data-stu-id="c4ef1-188">UE-V Registry Settings</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2770042/EN-US" data-raw-source="[support.microsoft.com/kb/2770042/EN-US](https://support.microsoft.com/kb/2770042/EN-US)"><span data-ttu-id="c4ef1-189">support.microsoft.com/kb/2770042/EN-US</span><span class="sxs-lookup"><span data-stu-id="c4ef1-189">support.microsoft.com/kb/2770042/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c4ef1-190">2847017</span><span class="sxs-lookup"><span data-stu-id="c4ef1-190">2847017</span></span></p></td>
<td align="left"><p><span data-ttu-id="c4ef1-191">由 Internet Explorer 複製的 UE-V 設定</span><span class="sxs-lookup"><span data-stu-id="c4ef1-191">UE-V settings replicated by Internet Explorer</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2847017/EN-US" data-raw-source="[support.microsoft.com/kb/2847017/EN-US](https://support.microsoft.com/kb/2847017/EN-US)"><span data-ttu-id="c4ef1-192">support.microsoft.com/kb/2847017/EN-US</span><span class="sxs-lookup"><span data-stu-id="c4ef1-192">support.microsoft.com/kb/2847017/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c4ef1-193">2930271</span><span class="sxs-lookup"><span data-stu-id="c4ef1-193">2930271</span></span></p></td>
<td align="left"><p><span data-ttu-id="c4ef1-194">瞭解 Microsoft UE-V 中的漫遊 Outlook 簽名限制</span><span class="sxs-lookup"><span data-stu-id="c4ef1-194">Understanding the limitations of roaming Outlook signatures in Microsoft UE-V</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2930271/EN-US" data-raw-source="[support.microsoft.com/kb/2930271/EN-US](https://support.microsoft.com/kb/2930271/EN-US)"><span data-ttu-id="c4ef1-195">support.microsoft.com/kb/2930271/EN-US</span><span class="sxs-lookup"><span data-stu-id="c4ef1-195">support.microsoft.com/kb/2930271/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c4ef1-196">2769631</span><span class="sxs-lookup"><span data-stu-id="c4ef1-196">2769631</span></span></p></td>
<td align="left"><p><span data-ttu-id="c4ef1-197">如何修復損毀的 UE-V 安裝</span><span class="sxs-lookup"><span data-stu-id="c4ef1-197">How to repair a corrupted UE-V install</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2769631/EN-US" data-raw-source="[support.microsoft.com/kb/2769631/EN-US](https://support.microsoft.com/kb/2769631/EN-US)"><span data-ttu-id="c4ef1-198">support.microsoft.com/kb/2769631/EN-US</span><span class="sxs-lookup"><span data-stu-id="c4ef1-198">support.microsoft.com/kb/2769631/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c4ef1-199">2850989</span><span class="sxs-lookup"><span data-stu-id="c4ef1-199">2850989</span></span></p></td>
<td align="left"><p><span data-ttu-id="c4ef1-200">不支援使用 Microsoft UE-V 遷移 MAPI 設定檔</span><span class="sxs-lookup"><span data-stu-id="c4ef1-200">Migrating MAPI profiles with Microsoft UE-V is not supported</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2850989/EN-US" data-raw-source="[support.microsoft.com/kb/2850989/EN-US](https://support.microsoft.com/kb/2850989/EN-US)"><span data-ttu-id="c4ef1-201">support.microsoft.com/kb/2850989/EN-US</span><span class="sxs-lookup"><span data-stu-id="c4ef1-201">support.microsoft.com/kb/2850989/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c4ef1-202">2769586</span><span class="sxs-lookup"><span data-stu-id="c4ef1-202">2769586</span></span></p></td>
<td align="left"><p><span data-ttu-id="c4ef1-203">UE-V 會漫遊空白資料夾和登錄機碼</span><span class="sxs-lookup"><span data-stu-id="c4ef1-203">UE-V roams empty folders and registry keys</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2769586/EN-US" data-raw-source="[support.microsoft.com/kb/2769586/EN-US](https://support.microsoft.com/kb/2769586/EN-US)"><span data-ttu-id="c4ef1-204">support.microsoft.com/kb/2769586/EN-US</span><span class="sxs-lookup"><span data-stu-id="c4ef1-204">support.microsoft.com/kb/2769586/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c4ef1-205">2782997</span><span class="sxs-lookup"><span data-stu-id="c4ef1-205">2782997</span></span></p></td>
<td align="left"><p><span data-ttu-id="c4ef1-206">如何在 Microsoft 使用者體驗虛擬化（UE-V）中啟用調試記錄</span><span class="sxs-lookup"><span data-stu-id="c4ef1-206">How To Enable Debug Logging in Microsoft User Experience Virtualization (UE-V)</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2782997/EN-US" data-raw-source="[support.microsoft.com/kb/2782997/EN-US](https://support.microsoft.com/kb/2782997/EN-US)"><span data-ttu-id="c4ef1-207">support.microsoft.com/kb/2782997/EN-US</span><span class="sxs-lookup"><span data-stu-id="c4ef1-207">support.microsoft.com/kb/2782997/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c4ef1-208">2769570</span><span class="sxs-lookup"><span data-stu-id="c4ef1-208">2769570</span></span></p></td>
<td align="left"><p><span data-ttu-id="c4ef1-209">UE-V 不會在 RDS 或 VDI 會話上更新主題</span><span class="sxs-lookup"><span data-stu-id="c4ef1-209">UE-V does not update the theme on RDS or VDI sessions</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2769570/EN-US" data-raw-source="[support.microsoft.com/kb/2769570/EN-US](https://support.microsoft.com/kb/2769570/EN-US)"><span data-ttu-id="c4ef1-210">support.microsoft.com/kb/2769570/EN-US</span><span class="sxs-lookup"><span data-stu-id="c4ef1-210">support.microsoft.com/kb/2769570/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c4ef1-211">2901856</span><span class="sxs-lookup"><span data-stu-id="c4ef1-211">2901856</span></span></p></td>
<td align="left"><p><span data-ttu-id="c4ef1-212">在啟用 UE-V 的電腦上強制重新開機後，應用程式設定不會同步處理</span><span class="sxs-lookup"><span data-stu-id="c4ef1-212">Application settings do not sync after you force a restart on a UE-V-enabled computer</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2901856/EN-US" data-raw-source="[support.microsoft.com/kb/2901856/EN-US](https://support.microsoft.com/kb/2901856/EN-US)"><span data-ttu-id="c4ef1-213">support.microsoft.com/kb/2901856/EN-US</span><span class="sxs-lookup"><span data-stu-id="c4ef1-213">support.microsoft.com/kb/2901856/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c4ef1-214">2850582</span><span class="sxs-lookup"><span data-stu-id="c4ef1-214">2850582</span></span></p></td>
<td align="left"><p><span data-ttu-id="c4ef1-215">如何在 App V 應用程式中使用 Microsoft 使用者體驗虛擬化</span><span class="sxs-lookup"><span data-stu-id="c4ef1-215">How To Use Microsoft User Experience Virtualization With App-V Applications</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2850582/EN-US" data-raw-source="[support.microsoft.com/kb/2850582/EN-US](https://support.microsoft.com/kb/2850582/EN-US)"><span data-ttu-id="c4ef1-216">support.microsoft.com/kb/2850582/EN-US</span><span class="sxs-lookup"><span data-stu-id="c4ef1-216">support.microsoft.com/kb/2850582/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c4ef1-217">3041879</span><span class="sxs-lookup"><span data-stu-id="c4ef1-217">3041879</span></span></p></td>
<td align="left"><p><span data-ttu-id="c4ef1-218">Microsoft 使用者體驗虛擬化的目前檔版本</span><span class="sxs-lookup"><span data-stu-id="c4ef1-218">Current file versions for Microsoft User Experience Virtualization</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/3041879/EN-US" data-raw-source="[support.microsoft.com/kb/3041879/EN-US](https://support.microsoft.com/kb/3041879/EN-US)"><span data-ttu-id="c4ef1-219">support.microsoft.com/kb/3041879/EN-US</span><span class="sxs-lookup"><span data-stu-id="c4ef1-219">support.microsoft.com/kb/3041879/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c4ef1-220">2843592</span><span class="sxs-lookup"><span data-stu-id="c4ef1-220">2843592</span></span></p></td>
<td align="left"><p><span data-ttu-id="c4ef1-221">使用者體驗虛擬化與高可用性的相關資訊</span><span class="sxs-lookup"><span data-stu-id="c4ef1-221">Information on User Experience Virtualization and High Availability</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2843592/EN-US" data-raw-source="[support.microsoft.com/kb/2843592/EN-US](https://support.microsoft.com/kb/2843592/EN-US)"><span data-ttu-id="c4ef1-222">support.microsoft.com/kb/2843592/EN-US</span><span class="sxs-lookup"><span data-stu-id="c4ef1-222">support.microsoft.com/kb/2843592/EN-US</span></span></a></p></td>
</tr>
</tbody>
</table>

 

 

 





