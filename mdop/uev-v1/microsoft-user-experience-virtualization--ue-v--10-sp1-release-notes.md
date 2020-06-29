---
title: Microsoft User Experience Virtualization (UE-V) 1.0 SP1 版本資訊
description: Microsoft User Experience Virtualization (UE-V) 1.0 SP1 版本資訊
author: dansimp
ms.assetid: 447fae0c-fe87-4d1c-b616-6f92fbdaf6d5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 8584999d9fdbdfccc3e9b2b1486cb97635475747
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800105"
---
# <span data-ttu-id="a3e6d-103">Microsoft User Experience Virtualization (UE-V) 1.0 SP1 版本資訊</span><span class="sxs-lookup"><span data-stu-id="a3e6d-103">Microsoft User Experience Virtualization (UE-V) 1.0 SP1 Release Notes</span></span>


<span data-ttu-id="a3e6d-104">若要搜尋 Microsoft 使用者體驗虛擬化（UE-V） 1.0 Service Pack 1 版本資訊，請按 Ctrl + F。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-104">To search Microsoft User Experience Virtualization (UE-V) 1.0 Service Pack 1 release notes, press Ctrl+F.</span></span>

<span data-ttu-id="a3e6d-105">您必須先閱讀這些版本資訊，才能安裝 UE-V。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-105">You should read these release notes thoroughly before you install UE-V.</span></span> <span data-ttu-id="a3e6d-106">版本資訊包含成功安裝使用者體驗虛擬化所需的資訊，並包含產品檔中不提供的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-106">The release notes contain information that is required to successfully install User Experience Virtualization, and contain additional information that is not available in the product documentation.</span></span> <span data-ttu-id="a3e6d-107">如果這些版本資訊與其他 UE-V 檔之間有差異，最新的變更應該視為權威性。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-107">If there are differences between these release notes and other UE-V documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="a3e6d-108">這些版本資訊取代本產品隨附的內容。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-108">These release notes supersede the content that is included with this product.</span></span>

## <span data-ttu-id="a3e6d-109">UE-V 已知問題</span><span class="sxs-lookup"><span data-stu-id="a3e6d-109">UE-V known issues</span></span>


<span data-ttu-id="a3e6d-110">本節包含適用于使用者體驗虛擬化 1.0 SP1 的版本資訊。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-110">This section contains release notes for User Experience Virtualization 1.0 SP1.</span></span>

### <span data-ttu-id="a3e6d-111">在同一部電腦上的 App-v 與原生應用程式之間，登錄設定無法同步處理</span><span class="sxs-lookup"><span data-stu-id="a3e6d-111">Registry settings fail to synchronize between App-V and native applications on the same computer</span></span>

<span data-ttu-id="a3e6d-112">當電腦中有應用程式可透過應用程式虛擬化（App-v）應用程式，以及使用 Windows 安裝程式（.msi 檔案）安裝的原生安裝應用程式時，將不會在技術之間同步處理。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-112">When a computer has an application that is available through both the Application Virtualization (App-V) application and a native installation application installed with a Windows Installer (.msi file), the registry-based settings do not synchronize between the technologies.</span></span>

<span data-ttu-id="a3e6d-113">因應措施：若要解決此問題，請選取其中一種技術來執行應用程式，但不能同時選取兩者。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-113">WORKAROUND: To resolve this problem, run the application by selecting one of the two technologies, but not both.</span></span>

### <a href="" id="windows-8-setting-synchronization-fails-when-network-share-is-outside-user-s-domain"></a><span data-ttu-id="a3e6d-114">當網路共用超出使用者網域時，Windows 8 設定同步處理失敗</span><span class="sxs-lookup"><span data-stu-id="a3e6d-114">Windows 8 setting synchronization fails when network share is outside user’s domain</span></span>

<span data-ttu-id="a3e6d-115">當 Windows®8嘗試作業系統設定同步處理時，synchrnization 失敗並出現下列錯誤訊息：**提升：： filesystem：：存在：：不正確的使用者名稱或密碼**。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-115">When Windows® 8 attempts operating system settings synchronization, the synchrnization fails with the following error message: **boost::filesystem::exists::Incorrect user name or password**.</span></span> <span data-ttu-id="a3e6d-116">此錯誤可能表示網路共用位於使用者網域外。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-116">This error can indicate that the network share is outside the user’s domain.</span></span> <span data-ttu-id="a3e6d-117">若要檢查作業記錄事件，請開啟**事件檢視器**，然後流覽到**應用程式和服務記錄**  /  **Microsoft**  /  **使用者體驗虛擬化**  /  **記錄**作業  /  **運作**。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-117">To check for operational log events, open the **Event Viewer** and navigate to **Applications and Services Logs** / **Microsoft** / **User Experience Virtualization** / **Logging** / **Operational**.</span></span> <span data-ttu-id="a3e6d-118">UE-V 設定儲存位置所用的網路共用應該位於與使用者相同的 Active Directory 網域中。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-118">Network shares that are used for UE-V settings storage locations should reside in the same Active Directory domain as the user.</span></span>

<span data-ttu-id="a3e6d-119">因應措施：使用與使用者相同的 Active Directory 網域中的網路共用。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-119">WORKAROUND: Use network shares from the same Active Directory domain as the user.</span></span> <span data-ttu-id="a3e6d-120">.</span><span class="sxs-lookup"><span data-stu-id="a3e6d-120">.</span></span>

### <span data-ttu-id="a3e6d-121">Outlook 2010 的電子郵件簽名漫遊</span><span class="sxs-lookup"><span data-stu-id="a3e6d-121">Email signature roaming for Outlook 2010</span></span>

<span data-ttu-id="a3e6d-122">UE-V 會在裝置之間漫遊 Outlook 2010 簽名檔案。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-122">UE-V will roam the Outlook 2010 signature files between devices.</span></span> <span data-ttu-id="a3e6d-123">不過，新郵件和回復/轉寄的預設簽章選項不會漫遊。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-123">However, the default signature options for new messages and replies/forwards are not roamed.</span></span> <span data-ttu-id="a3e6d-124">這兩個設定會儲存在 Outlook 設定檔中，而 UE-V 不會漫遊。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-124">These two settings are stored in the Outlook profile, which UE-V does not roam.</span></span>

<span data-ttu-id="a3e6d-125">因應措施：無。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-125">WORKAROUND: None.</span></span>

### <span data-ttu-id="a3e6d-126">在低速連結模式下執行時，同步處理設定不會根據預期的間隔進行同步處理</span><span class="sxs-lookup"><span data-stu-id="a3e6d-126">Synchronization settings do not synchronize on expected interval when running in slow-link mode</span></span>

<span data-ttu-id="a3e6d-127">在 [標準條件] 下，設定儲存位置應該可在快速連結網路連線時使用。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-127">Under normal conditions, settings storage locations should be available over a fast link network connection.</span></span> <span data-ttu-id="a3e6d-128">在低速連結模式中，同步處理將只能定期進行。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-128">In slow-link mode, synchronization will only occur on a periodic basis.</span></span> <span data-ttu-id="a3e6d-129">根據預設，低速連結模式同步處理排程會設定為每360分鐘。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-129">By default, the slow-link mode synchronization schedule is set to every 360 minutes.</span></span>

<span data-ttu-id="a3e6d-130">因應措施：若要變更低速連結模式中電腦背景同步處理的頻率，您可以針對**離線**檔案設定背景同步處理原則的群組原則。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-130">WORKAROUND: To change the frequency of the background synchronization for computers in slow-link mode, you can configure the Group Policy for Background Sync policy for **Offline files**.</span></span>

### <span data-ttu-id="a3e6d-131">特殊字元不同步處理</span><span class="sxs-lookup"><span data-stu-id="a3e6d-131">Special characters do not synchronize</span></span>

<span data-ttu-id="a3e6d-132">某些字元（例如貨幣符號）不會在執行 UE-V agent 的 Windows 7 和 Windows 8 電腦之間進行同步處理。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-132">Certain characters, such as currency symbols, do not synchronize between Windows 7 and Windows 8 computers that run the UE-V agent.</span></span>

<span data-ttu-id="a3e6d-133">因應措施：無。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-133">WORKAROUND: None.</span></span>

### <span data-ttu-id="a3e6d-134">UE-V 不支援32位與64位版本的 Microsoft Office 之間的漫遊設定</span><span class="sxs-lookup"><span data-stu-id="a3e6d-134">UE-V does not support roaming settings between 32-bit and 64-bit versions of Microsoft Office</span></span>

<span data-ttu-id="a3e6d-135">我們建議您為32位和64位作業系統安裝32位版本的 Microsoft Office。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-135">We recommend that you install the 32-bit version of Microsoft Office for both 32-bit and 64-bit operating systems.</span></span> <span data-ttu-id="a3e6d-136">若要選擇您需要的 Microsoft Office 版本，請按一下 [這兒] （ [http://office.microsoft.com/word-help/choose-the-32-bit-or-64-bit-version-of-microsoft-office-HA010369476.aspx](https://go.microsoft.com/fwlink/?LinkID=247623) ）。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-136">To choose the Microsoft Office version that you need, click here ([http://office.microsoft.com/word-help/choose-the-32-bit-or-64-bit-version-of-microsoft-office-HA010369476.aspx](https://go.microsoft.com/fwlink/?LinkID=247623)).</span></span> <span data-ttu-id="a3e6d-137">UE-V 支援相同架構版本的 Office 間的漫遊設定。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-137">UE-V supports roaming settings between identical architecture versions of Office.</span></span> <span data-ttu-id="a3e6d-138">例如，32位的 Office 設定將會在所有32位的 Office 實例之間漫遊。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-138">For example, 32-bit Office settings will roam between all 32-bit Office instances.</span></span> <span data-ttu-id="a3e6d-139">UE-V 不支援32位與64位版本的 Office 之間的漫遊設定。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-139">UE-V does not support roaming settings between 32-bit and 64-bit versions of Office.</span></span>

<span data-ttu-id="a3e6d-140">因應措施：無</span><span class="sxs-lookup"><span data-stu-id="a3e6d-140">WORKAROUND: None</span></span>

### <a href="" id="msi-s-are-not-localized"></a><span data-ttu-id="a3e6d-141">MSI 未當地語系化</span><span class="sxs-lookup"><span data-stu-id="a3e6d-141">MSI’s are not localized</span></span>

<span data-ttu-id="a3e6d-142">UE-V 1.0 SP1 包含 UE-V Agent 與 UE-V 發生器的當地語系化安裝程式。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-142">UE-V 1.0 SP1 includes a localized setup program for both the UE-V Agent and UE-V generator.</span></span> <span data-ttu-id="a3e6d-143">這些 MSI 檔案仍可供使用，但使用者介面已最小化，且 MSI 只顯示英文。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-143">These MSI files are still available but the user interface is minimized and the MSI’s only display in English.</span></span> <span data-ttu-id="a3e6d-144">雖然檔案是英文，但安裝程式會在安裝期間安裝所有支援的語言。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-144">Despite the file being in English, the setup program installs all supported languages during the installation.</span></span>

<span data-ttu-id="a3e6d-145">因應措施：無</span><span class="sxs-lookup"><span data-stu-id="a3e6d-145">WORKAROUND: None</span></span>

### <span data-ttu-id="a3e6d-146">與設定儲存位置有關之共用的其他資料夾在慢速連線模式中無法使用</span><span class="sxs-lookup"><span data-stu-id="a3e6d-146">Other folders on the share with the setting storage location are unavailable in slow-connection mode</span></span>

<span data-ttu-id="a3e6d-147">[設定儲存區共用] 不應該位於用於其他必須使用之資料夾的網路共用位置。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-147">Settings store shares should not be located on a network share that is used for other folders that must always be available.</span></span> <span data-ttu-id="a3e6d-148">當承載設定儲存位置的網路共用移至慢速連線模式時，唯一可用的資料夾是 [設定儲存位置] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-148">When the network share that hosts the setting storage location goes into slow-connection mode, the only available folder is the settings storage location folder.</span></span> <span data-ttu-id="a3e6d-149">[共用] 上的其他資料夾無法在 [緩慢連接] 模式中使用。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-149">Other folders on the Share are not available in slow-connection mode.</span></span>

<span data-ttu-id="a3e6d-150">因應措施：無</span><span class="sxs-lookup"><span data-stu-id="a3e6d-150">Workaround: None</span></span>

### <span data-ttu-id="a3e6d-151">與 Internet Explorer 9 [我的最愛] 相關聯的 Favicons 不會漫遊</span><span class="sxs-lookup"><span data-stu-id="a3e6d-151">Favicons that are associated with Internet Explorer 9 favorites do not roam</span></span>

<span data-ttu-id="a3e6d-152">與 Internet Explorer 9 [我的最愛] 相關聯的 favicons 不會受到使用者體驗虛擬化的漫遊，而且在新電腦上出現 [我的最愛] 時不會出現。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-152">The favicons that are associated with Internet Explorer 9 favorites are not roamed by User Experience Virtualization and do not appear when the favorites first appear on a new computer.</span></span>

<span data-ttu-id="a3e6d-153">因應措施：當您使用書簽並將其放入 Internet Explorer 9 瀏覽器中後，就會顯示 Favicons 的相關連絡人。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-153">WORKAROUND: Favicons will appear with their associated favorites once the bookmark is used and cached in the Internet Explorer 9 browser.</span></span>

### <span data-ttu-id="a3e6d-154">檔案設定路徑儲存在註冊表中</span><span class="sxs-lookup"><span data-stu-id="a3e6d-154">File settings paths are stored in registry</span></span>

<span data-ttu-id="a3e6d-155">某些應用程式設定會將其設定和設定檔案的路徑儲存為註冊表中的值。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-155">Some application settings store the paths of their configuration and settings files as values in the registry.</span></span> <span data-ttu-id="a3e6d-156">當設定在電腦之間漫遊時，必須同步處理在登錄中作為路徑所參照的檔案。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-156">The files that are referenced as paths in the registry must be synchronized when settings are roamed between computers.</span></span>

<span data-ttu-id="a3e6d-157">因應措施：使用 [資料夾重新導向] 或其他技術，以確保任何被參照為檔案設定路徑的檔案都存在並放在 [設定] 漫遊之所有電腦上的相同位置。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-157">WORKAROUND: Use folder redirection or some other technology to ensure that any files that are referenced as file settings paths are present and placed in the same location on all computers where settings roam.</span></span>

### <span data-ttu-id="a3e6d-158">較長的設定儲存路徑可能會導致錯誤</span><span class="sxs-lookup"><span data-stu-id="a3e6d-158">Long Settings Storage Paths could cause an error</span></span>

<span data-ttu-id="a3e6d-159">讓設定的儲存路徑盡可能簡短。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-159">Keep settings storage paths as short as possible.</span></span> <span data-ttu-id="a3e6d-160">長條路徑可以避免解析度或同步處理。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-160">Long paths could prevent resolution or synchronization.</span></span> <span data-ttu-id="a3e6d-161">UE-V 會使用設定儲存路徑作為儲存設定的計算路徑的一部分。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-161">UE-V uses the Settings storage path as part of the calculated path to store settings.</span></span> <span data-ttu-id="a3e6d-162">該路徑的計算方式如下：設定儲存路徑 + "settingspackages" + 套件目錄（範本識別碼） + 套件名稱（範本識別碼）。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-162">That path is calculated in the following way: settings storage path + “settingspackages” + package dir (template ID) + package name (template ID).</span></span> <span data-ttu-id="a3e6d-163">如果該計算路徑超過260字元，套件儲存將會失敗，並會在 UE-V 操作事件記錄中產生下列錯誤訊息：</span><span class="sxs-lookup"><span data-stu-id="a3e6d-163">If that calculated path exceeds 260 characters, package storage will fail and generate the following error message in the UE-V operational event log:</span></span>

`[boost::filesystem::copy_file: The system cannot find the path specified]`

<span data-ttu-id="a3e6d-164">若要檢查操作記錄事件，請開啟事件檢視器，然後流覽到應用程式和服務記錄/Microsoft/使用者體驗虛擬化/記錄/運作。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-164">To check the operational log events, open the Event Viewer and navigate to Applications and Services Logs / Microsoft / User Experience Virtualization / Logging / Operational.</span></span>

<span data-ttu-id="a3e6d-165">因應措施：無。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-165">WORKAROUND: None.</span></span>

### <span data-ttu-id="a3e6d-166">UE-V agent 在登入或登入時延遲</span><span class="sxs-lookup"><span data-stu-id="a3e6d-166">UE-V agent delays upon logout or login</span></span>

<span data-ttu-id="a3e6d-167">如果在離線檔案已確定低速連結已在適當位置之前登入或登出，可能會延遲登入或登入。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-167">If a logon or logout occurs before Offline Files has determined that a slow link is in place, logout or login might be delayed.</span></span> <span data-ttu-id="a3e6d-168">[離線檔案] 功能可能需要最多三分鐘的時間來偵測目前的網路狀態。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-168">The Offline Files feature may take up to three minutes to detect the current network state.</span></span> <span data-ttu-id="a3e6d-169">如果您在 [離線檔案] 確定電腦已連線至低速連結之後進行登入或關閉，則 UE-V 設定套件會傳送到伺服器而不是本機快取。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-169">If the logon or shutdown occurs before Offline Files has determined that the computer is connected to a slow link, the UE-V settings package will be sent to the server instead of the local cache.</span></span>

<span data-ttu-id="a3e6d-170">因應措施：無。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-170">WORKAROUND: None.</span></span>

### <span data-ttu-id="a3e6d-171">嘗試在 Windows 8 上漫遊作業系統設定時的設定衝突</span><span class="sxs-lookup"><span data-stu-id="a3e6d-171">Settings conflict when trying to roam operating system settings on Windows 8</span></span>

<span data-ttu-id="a3e6d-172">在 Windows 8 上，如果已啟用 Microsoft 帳戶同步處理，並在作業系統設定中使用 UE-V，則所套用的設定可能不一致。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-172">On Windows 8 if Microsoft Account Sync is enabled along with UE-V for operating system settings, the settings that are applied may be inconsistent.</span></span>

<span data-ttu-id="a3e6d-173">解決方法：執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="a3e6d-173">WORKAROUND: Do one of the following:</span></span>

-   <span data-ttu-id="a3e6d-174">如果您使用 UE-V 來漫遊作業系統設定，請停用 Microsoft 帳戶同步處理</span><span class="sxs-lookup"><span data-stu-id="a3e6d-174">Disable Microsoft Account Sync if you are using UE-V to roam operating system settings</span></span>

-   <span data-ttu-id="a3e6d-175">停用 UE-V 以進行作業系統設定</span><span class="sxs-lookup"><span data-stu-id="a3e6d-175">Disable UE-V for operating system settings</span></span>

### <span data-ttu-id="a3e6d-176">某些作業系統設定只會在相似的作業系統版本之間漫遊</span><span class="sxs-lookup"><span data-stu-id="a3e6d-176">Some operating system settings only roam between like operating system versions</span></span>

<span data-ttu-id="a3e6d-177">朗讀程式的作業系統設定和地區專用的貨幣字元將只會隨著作業系統版本的 Windows 進行漫遊。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-177">Operating system settings for Narrator and currency characters specific to the locale will only roam across like operating system versions of Windows.</span></span> <span data-ttu-id="a3e6d-178">例如，貨幣字元只會從 Windows 7 漫遊至 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="a3e6d-178">For example currency characters will only roam from Windows 7 to Windows 7.</span></span>

<span data-ttu-id="a3e6d-179">因應措施：無</span><span class="sxs-lookup"><span data-stu-id="a3e6d-179">WORKAROUND: None</span></span>

 

 





