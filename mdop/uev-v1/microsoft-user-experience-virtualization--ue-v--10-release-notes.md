---
title: Microsoft User Experience Virtualization (UE-V) 1.0 版本資訊
description: Microsoft User Experience Virtualization (UE-V) 1.0 版本資訊
author: dansimp
ms.assetid: 920f3fae-e9b5-4b94-beda-32c19d31e94b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9f9942eef7ea84cf7010a0c0173427827a512216
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800106"
---
# <span data-ttu-id="bdbf3-103">Microsoft User Experience Virtualization (UE-V) 1.0 版本資訊</span><span class="sxs-lookup"><span data-stu-id="bdbf3-103">Microsoft User Experience Virtualization (UE-V) 1.0 Release Notes</span></span>


<span data-ttu-id="bdbf3-104">若要搜尋 Microsoft 使用者體驗虛擬化（UE-V）版本資訊，請按 Ctrl + F。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-104">To search Microsoft User Experience Virtualization (UE-V) release notes, press Ctrl+F.</span></span>

<span data-ttu-id="bdbf3-105">您必須先閱讀這些版本資訊，才能安裝 UE-V。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-105">You should read these release notes thoroughly before you install UE-V.</span></span> <span data-ttu-id="bdbf3-106">版本資訊包含成功安裝使用者體驗虛擬化所需的資訊，並包含產品檔中不提供的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-106">The release notes contain information that is required to successfully install User Experience Virtualization, and contain additional information that is not available in the product documentation.</span></span> <span data-ttu-id="bdbf3-107">如果這些版本資訊與其他 UE-V 檔之間有差異，最新的變更應該視為權威性。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-107">If there are differences between these release notes and other UE-V documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="bdbf3-108">這些版本資訊取代本產品隨附的內容。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-108">These release notes supersede the content that is included with this product.</span></span>

## <span data-ttu-id="bdbf3-109">提供意見反應</span><span class="sxs-lookup"><span data-stu-id="bdbf3-109">Providing feedback</span></span>


<span data-ttu-id="bdbf3-110">向我們提供您的意見反應與意見反應，告訴我們您對 MDOP 檔的想法。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-110">Tell us what you think about our documentation for MDOP by giving us your feedback and comments.</span></span> <span data-ttu-id="bdbf3-111">將您的檔意見反應傳送給[mdopdocs@microsoft.com](mailto:mdopdocs@microsoft.com?subject=UE-V%20Documentation)。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-111">Send your documentation feedback to [mdopdocs@microsoft.com](mailto:mdopdocs@microsoft.com?subject=UE-V%20Documentation).</span></span>

## <span data-ttu-id="bdbf3-112">UE-V 已知問題</span><span class="sxs-lookup"><span data-stu-id="bdbf3-112">UE-V known issues</span></span>


<span data-ttu-id="bdbf3-113">本節包含適用于使用者體驗虛擬化的版本資訊。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-113">This section contains release notes for User Experience Virtualization.</span></span>

### <span data-ttu-id="bdbf3-114">在同一部電腦上的 App-v 與原生應用程式之間，登錄設定無法同步處理</span><span class="sxs-lookup"><span data-stu-id="bdbf3-114">Registry settings fail to synchronize between App-V and native applications on the same computer</span></span>

<span data-ttu-id="bdbf3-115">當電腦擁有可透過應用程式虛擬化（App-v）應用程式及原生安裝應用程式（以 .msi 檔案安裝）的應用程式時，以註冊表為基礎的設定不會在技術之間同步處理。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-115">When a computer has an application that is available through both the Application Virtualization (App-V) application and a native installation application (installed with an .msi file), the registry-based settings do not synchronize between the technologies.</span></span>

<span data-ttu-id="bdbf3-116">因應措施：若要解決此問題，請選取其中一種技術來執行應用程式，但不能同時選取兩者。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-116">WORKAROUND: To resolve this problem, run the application by selecting one of the two technologies, but not both.</span></span>

### <span data-ttu-id="bdbf3-117">Windows 8 設定同步處理失敗，出現錯誤：「提升：： filesystem：：存在：：不正確的使用者名稱或密碼」</span><span class="sxs-lookup"><span data-stu-id="bdbf3-117">Windows 8 setting synchronization fails with error: "boost::filesystem::exists::Incorrect user name or password"</span></span>

<span data-ttu-id="bdbf3-118">Windows®8作業系統設定同步處理失敗，並出現下列錯誤訊息：**提升：： filesystem：：存在：：不正確的使用者名稱或密碼**。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-118">The Windows® 8 operating system settings synchronization fails with the following error message: **boost::filesystem::exists::Incorrect user name or password**.</span></span> <span data-ttu-id="bdbf3-119">若要檢查作業記錄事件，請開啟**事件檢視器**，然後流覽到**應用程式和服務記錄**  /  **Microsoft**  /  **使用者體驗虛擬化**  /  **記錄**作業  /  **運作**。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-119">To check for operational log events, open the **Event Viewer** and navigate to **Applications and Services Logs** / **Microsoft** / **User Experience Virtualization** / **Logging** / **Operational**.</span></span> <span data-ttu-id="bdbf3-120">UE-V 設定儲存位置所用的網路共用應該位於與使用者相同的 Active Directory 網域中。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-120">Network shares that are used for UE-V settings storage locations should reside in the same Active Directory domain as the user.</span></span> <span data-ttu-id="bdbf3-121">否則，可能會發生下列錯誤：「使用者名稱或密碼不正確」。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-121">Otherwise, the following error might occur: "Incorrect user name or password".</span></span>

<span data-ttu-id="bdbf3-122">因應措施：使用與使用者相同的 Active Directory 網域中的網路共用。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-122">WORKAROUND: Use network shares from the same Active Directory domain as the user.</span></span> <span data-ttu-id="bdbf3-123">.</span><span class="sxs-lookup"><span data-stu-id="bdbf3-123">.</span></span>

### <span data-ttu-id="bdbf3-124">Outlook 2010 的電子郵件簽名漫遊</span><span class="sxs-lookup"><span data-stu-id="bdbf3-124">Email signature roaming for Outlook 2010</span></span>

<span data-ttu-id="bdbf3-125">UE-V 會在裝置之間漫遊 Outlook 2010 簽名檔案。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-125">UE-V will roam the Outlook 2010 signature files between devices.</span></span> <span data-ttu-id="bdbf3-126">不過，新郵件和回復/轉寄的預設簽章選項都不行。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-126">However, the default signature options for new messages and replies/forwards are not.</span></span><span data-ttu-id="bdbf3-127">這兩個設定會儲存在 Outlook 設定檔中，Vdoes 不會漫遊。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-127"> These two settings are stored in the Outlook profile, which UE-Vdoes not roam.</span></span>

<span data-ttu-id="bdbf3-128">因應措施：無。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-128">WORKAROUND: None.</span></span>

### <span data-ttu-id="bdbf3-129">在低速連結模式下執行時，同步處理設定不會根據預期的間隔進行同步處理</span><span class="sxs-lookup"><span data-stu-id="bdbf3-129">Synchronization settings do not synchronize on expected interval when running in slow-link mode</span></span>

<span data-ttu-id="bdbf3-130">在 [標準條件] 下，設定儲存位置應該可在快速連結網路連線時使用。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-130">Under normal conditions, settings storage locations should be available over a fast link network connection.</span></span> <span data-ttu-id="bdbf3-131">在低速連結模式中，同步處理將只能定期進行。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-131">In slow-link mode, synchronization will only occur on a periodic basis.</span></span> <span data-ttu-id="bdbf3-132">根據預設，低速連結模式同步處理排程會設定為每360分鐘。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-132">By default, the slow-link mode synchronization schedule is set to every 360 minutes.</span></span>

<span data-ttu-id="bdbf3-133">因應措施：若要變更低速連結模式中電腦背景同步處理的頻率，您可以針對**離線**檔案設定背景同步處理原則的群組原則。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-133">WORKAROUND: To change the frequency of the background synchronization for computers in slow-link mode, you can configure the Group Policy for Background Sync policy for **Offline files**.</span></span>

### <span data-ttu-id="bdbf3-134">特殊字元不同步處理</span><span class="sxs-lookup"><span data-stu-id="bdbf3-134">Special characters do not synchronize</span></span>

<span data-ttu-id="bdbf3-135">某些字元（例如貨幣符號）不會在執行 UE-V agent 的 Windows 7 和 Windows 8 電腦之間進行同步處理。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-135">Certain characters, such as currency symbols, do not synchronize between Windows 7 and Windows 8 computers that run the UE-V agent.</span></span>

<span data-ttu-id="bdbf3-136">因應措施：無。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-136">WORKAROUND: None.</span></span>

### <span data-ttu-id="bdbf3-137">UE-V 不支援32位與64位版本的 Microsoft Office 之間的漫遊設定</span><span class="sxs-lookup"><span data-stu-id="bdbf3-137">UE-V does not support roaming settings between 32-bit and 64-bit versions of Microsoft Office</span></span>

<span data-ttu-id="bdbf3-138">我們建議您為32位和64位作業系統安裝32位版本的 Microsoft Office。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-138">We recommend that you install the 32-bit version of Microsoft Office for both 32-bit and 64-bit operating systems.</span></span> <span data-ttu-id="bdbf3-139">若要選擇您需要的 Microsoft Office 版本，請按一下這裡。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-139">To choose the Microsoft Office version that you need, click here.</span></span> <span data-ttu-id="bdbf3-140">([http://office.microsoft.com/word-help/choose-the-32-bit-or-64-bit-version-of-microsoft-office-HA010369476.aspx](https://go.microsoft.com/fwlink/?LinkID=247623)).</span><span class="sxs-lookup"><span data-stu-id="bdbf3-140">([http://office.microsoft.com/word-help/choose-the-32-bit-or-64-bit-version-of-microsoft-office-HA010369476.aspx](https://go.microsoft.com/fwlink/?LinkID=247623)).</span></span> <span data-ttu-id="bdbf3-141">UE-V 支援相同架構版本的 Office 間的漫遊設定。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-141">UE-V supports roaming settings between identical architecture versions of Office.</span></span> <span data-ttu-id="bdbf3-142">例如，32位的 Office 設定將會在所有32位的 Office 實例之間漫遊。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-142">For example, 32-bit Office settings will roam between all 32-bit Office instances.</span></span> <span data-ttu-id="bdbf3-143">UE-V 不支援32位與64位版本的 Office 之間的漫遊設定。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-143">UE-V does not support roaming settings between 32-bit and 64-bit versions of Office.</span></span>

<span data-ttu-id="bdbf3-144">因應措施：無</span><span class="sxs-lookup"><span data-stu-id="bdbf3-144">WORKAROUND: None</span></span>

### <span data-ttu-id="bdbf3-145">與設定儲存位置有關之共用的其他資料夾在慢速連線模式中無法使用</span><span class="sxs-lookup"><span data-stu-id="bdbf3-145">Other folders on the share with the setting storage location are unavailable in slow-connection mode</span></span>

<span data-ttu-id="bdbf3-146">[設定儲存區共用] 不應該位於用於其他必須使用之資料夾的網路共用位置。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-146">Settings store shares should not be located on a network share that is used for other folders that must always be available.</span></span> <span data-ttu-id="bdbf3-147">當承載設定儲存位置的網路共用移至慢速連線模式時，唯一可用的資料夾是 [設定儲存位置] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-147">When the network share that hosts the setting storage location goes into slow-connection mode, the only available folder is the settings storage location folder.</span></span> <span data-ttu-id="bdbf3-148">[共用] 上的其他資料夾無法在 [緩慢連接] 模式中使用。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-148">Other folders on the Share are not available in slow-connection mode.</span></span>

<span data-ttu-id="bdbf3-149">因應措施：無</span><span class="sxs-lookup"><span data-stu-id="bdbf3-149">Workaround: None</span></span>

### <span data-ttu-id="bdbf3-150">與 Internet Explorer 9 [我的最愛] 相關聯的 Favicons 不會漫遊</span><span class="sxs-lookup"><span data-stu-id="bdbf3-150">Favicons that are associated with Internet Explorer 9 favorites do not roam</span></span>

<span data-ttu-id="bdbf3-151">與 Internet Explorer 9 [我的最愛] 相關聯的 favicons 不會受到使用者體驗虛擬化的漫遊，而且在新電腦上出現 [我的最愛] 時不會出現。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-151">The favicons that are associated with Internet Explorer 9 favorites are not roamed by User Experience Virtualization and do not appear when the favorites first appear on a new computer.</span></span>

<span data-ttu-id="bdbf3-152">因應措施：當您使用書簽並將其放入 Internet Explorer 9 瀏覽器中後，就會顯示 Favicons 的相關連絡人。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-152">WORKAROUND: Favicons will appear with their associated favorites once the bookmark is used and cached in the Internet Explorer 9 browser.</span></span>

### <span data-ttu-id="bdbf3-153">檔案設定路徑儲存在註冊表中</span><span class="sxs-lookup"><span data-stu-id="bdbf3-153">File settings paths are stored in registry</span></span>

<span data-ttu-id="bdbf3-154">某些應用程式設定會將其設定和設定檔案的路徑儲存為註冊表中的值。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-154">Some application settings store the paths of their configuration and settings files as values in the registry.</span></span> <span data-ttu-id="bdbf3-155">當設定在電腦之間漫遊時，必須同步處理在登錄中作為路徑所參照的檔案。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-155">The files that are referenced as paths in the registry must be synchronized when settings are roamed between computers.</span></span>

<span data-ttu-id="bdbf3-156">因應措施：使用 [資料夾重新導向] 或其他技術，以確保任何被參照為檔案設定路徑的檔案都存在並放在 [設定] 漫遊之所有電腦上的相同位置。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-156">WORKAROUND: Use folder redirection or some other technology to ensure that any files that are referenced as file settings paths are present and placed in the same location on all computers where settings roam.</span></span>

### <span data-ttu-id="bdbf3-157">不支援超過260個字元的路徑</span><span class="sxs-lookup"><span data-stu-id="bdbf3-157">Paths longer than 260 characters are not supported</span></span>

<span data-ttu-id="bdbf3-158">不支援超過260個字元的設定儲存路徑。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-158">Settings storage paths that are longer than 260 characters are not supported.</span></span> <span data-ttu-id="bdbf3-159">將 UE-V 設定套件複製到設定儲存路徑超過260個字元後，將會失敗，並會在 UE-V 作業事件日誌中產生以下例外訊息： **\ [加強：： filesystem：：複製 \ _file：系統找不到指定的路徑 \]**。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-159">Copying the UE-V settings packages to settings storage paths that are longer than 260 characters will fail and generate the following exception message in the UE-V operational event log: **\[boost::filesystem::copy\_file: The system cannot find the path specified\]**.</span></span> <span data-ttu-id="bdbf3-160">若要檢查作業記錄事件，請開啟**事件檢視器**，然後流覽到**應用程式和服務記錄**  /  **Microsoft**  /  **使用者體驗虛擬化**  /  **記錄**作業  /  **運作**。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-160">To check for operational log events, open the **Event Viewer** and navigate to **Applications and Services Logs** / **Microsoft** / **User Experience Virtualization** / **Logging** / **Operational**.</span></span>

<span data-ttu-id="bdbf3-161">目前不支援超過260個字元的檔案設定路徑。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-161">File settings paths that are longer than 260 characters are not currently supported.</span></span> <span data-ttu-id="bdbf3-162">在 UE-V 設定位置範本中參照的檔案設定無法位於超過260個字元的目錄路徑中。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-162">File settings that are referenced in UE-V settings location templates cannot be located in a directory path that is longer than 260 characters.</span></span>

<span data-ttu-id="bdbf3-163">因應措施：無。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-163">WORKAROUND: None.</span></span>

### <span data-ttu-id="bdbf3-164">UE-V agent 在登入或登入時延遲</span><span class="sxs-lookup"><span data-stu-id="bdbf3-164">UE-V agent delays upon logout or login</span></span>

<span data-ttu-id="bdbf3-165">如果在離線檔案已確定低速連結已在適當位置之前登入或登出，可能會延遲登入或登入。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-165">If a logon or logout occurs before Offline Files has determined that a slow link is in place, logout or login might be delayed.</span></span> <span data-ttu-id="bdbf3-166">[離線檔案] 功能可能需要最多三分鐘的時間來偵測目前的網路狀態。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-166">The Offline Files feature may take up to three minutes to detect the current network state.</span></span> <span data-ttu-id="bdbf3-167">如果您在 [離線檔案] 確定電腦已連線至低速連結之後進行登入或關閉，則 UE-V 設定套件會傳送到伺服器而不是本機快取。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-167">If the logon or shutdown occurs before Offline Files has determined that the computer is connected to a slow link, the UE-V settings package will be sent to the server instead of the local cache.</span></span>

<span data-ttu-id="bdbf3-168">因應措施：無。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-168">WORKAROUND: None.</span></span>

### <span data-ttu-id="bdbf3-169">嘗試在 Windows 8 上漫遊作業系統設定時的設定衝突</span><span class="sxs-lookup"><span data-stu-id="bdbf3-169">Settings conflict when trying to roam operating system settings on Windows 8</span></span>

<span data-ttu-id="bdbf3-170">在 Windows 8 上，如果已啟用 Microsoft 帳戶同步處理，並在作業系統設定中使用 UE-V，則所套用的設定可能不一致。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-170">On Windows 8 if Microsoft Account Sync is enabled along with UE-V for operating system settings, the settings that are applied may be inconsistent.</span></span>

<span data-ttu-id="bdbf3-171">解決方法：執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="bdbf3-171">WORKAROUND: Do one of the following:</span></span>

-   <span data-ttu-id="bdbf3-172">如果您使用 UE-V 來漫遊作業系統設定，請停用 Microsoft 帳戶同步處理</span><span class="sxs-lookup"><span data-stu-id="bdbf3-172">Disable Microsoft Account Sync if you are using UE-V to roam operating system settings</span></span>

-   <span data-ttu-id="bdbf3-173">停用 UE-V 以進行作業系統設定</span><span class="sxs-lookup"><span data-stu-id="bdbf3-173">Disable UE-V for operating system settings</span></span>

### <span data-ttu-id="bdbf3-174">某些作業系統設定只會在相似的作業系統版本之間漫遊</span><span class="sxs-lookup"><span data-stu-id="bdbf3-174">Some operating system settings only roam between like operating system versions</span></span>

<span data-ttu-id="bdbf3-175">朗讀程式的作業系統設定和地區專用的貨幣字元將只會隨著作業系統版本的 Windows 進行漫遊。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-175">Operating system settings for Narrator and currency characters specific to the locale will only roam across like operating system versions of Windows.</span></span> <span data-ttu-id="bdbf3-176">例如，貨幣字元只會從 Windows 7 漫遊至 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-176">For example currency characters will only roam from Windows 7 to Windows 7.</span></span>

<span data-ttu-id="bdbf3-177">因應措施：無</span><span class="sxs-lookup"><span data-stu-id="bdbf3-177">WORKAROUND: None</span></span>

### <span data-ttu-id="bdbf3-178">Internet Explorer 書簽不會出現在 Internet Explorer smartbar</span><span class="sxs-lookup"><span data-stu-id="bdbf3-178">Internet Explorer bookmarks do not appear in the Internet Explorer smartbar</span></span>

<span data-ttu-id="bdbf3-179">當 Internet Explorer 書簽從一部電腦漫遊至另一部電腦時，第二部電腦上的索引無法更新，因此當您在網址列中輸入時，最愛在電腦2上的搜尋結果不會顯示。</span><span class="sxs-lookup"><span data-stu-id="bdbf3-179">When Internet Explorer bookmarks roam from one computer to another computer, the index on the second computer cannot update, so when typing in the address bar, the favorite will not appear as a possible search result on computer 2.</span></span>

<span data-ttu-id="bdbf3-180">因應措施：無</span><span class="sxs-lookup"><span data-stu-id="bdbf3-180">WORKAROUND: None</span></span>

 

 





