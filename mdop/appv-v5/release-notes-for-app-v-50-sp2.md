---
title: App-V 5.0 SP2 版本資訊
description: App-V 5.0 SP2 版本資訊
author: dansimp
ms.assetid: fe73139d-240c-4ed5-8e59-6ae76ee8e80c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 5e885e67023d0e5c1e36aeb340933c64ae92610e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800316"
---
# <span data-ttu-id="5bff4-103">App-V 5.0 SP2 版本資訊</span><span class="sxs-lookup"><span data-stu-id="5bff4-103">Release Notes for App-V 5.0 SP2</span></span>


**<span data-ttu-id="5bff4-104">若要在這些版本筆記中搜尋特定問題，請按 CTRL + F。</span><span class="sxs-lookup"><span data-stu-id="5bff4-104">To search for a specific issue in these release notes, press CTRL+F.</span></span>**

<span data-ttu-id="5bff4-105">安裝 App-v 5.0 SP2 之前，請先通讀這些版本資訊。</span><span class="sxs-lookup"><span data-stu-id="5bff4-105">Read these release notes thoroughly before you install App-V 5.0 SP2.</span></span>

<span data-ttu-id="5bff4-106">這些版本資訊包含成功安裝 App-v 5.0 SP2 所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="5bff4-106">These release notes contain information that is required to successfully install App-V 5.0 SP2.</span></span> <span data-ttu-id="5bff4-107">版本資訊中也包含產品檔中不提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="5bff4-107">The release notes also contain information that is not available in the product documentation.</span></span> <span data-ttu-id="5bff4-108">如果這些版本資訊與其他 App-v 5.0 檔之間有差異，最新的變更應該視為權威性。</span><span class="sxs-lookup"><span data-stu-id="5bff4-108">If there are differences between these release notes and other App-V 5.0 documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="5bff4-109">這些版本資訊取代本產品隨附的內容。</span><span class="sxs-lookup"><span data-stu-id="5bff4-109">These release notes supersede the content that is included with this product.</span></span>

## <span data-ttu-id="5bff4-110">關於產品檔</span><span class="sxs-lookup"><span data-stu-id="5bff4-110">About the Product Documentation</span></span>


<span data-ttu-id="5bff4-111">如需 App-V 5.0 檔的相關資訊，請參閱 Microsoft TechNet 上的 app-v 5.0 首頁。</span><span class="sxs-lookup"><span data-stu-id="5bff4-111">For information about App-V 5.0 documentation, see the App-V 5.0 home page on Microsoft TechNet.</span></span>

## <span data-ttu-id="5bff4-112">提供意見反應</span><span class="sxs-lookup"><span data-stu-id="5bff4-112">Provide Feedback</span></span>


<span data-ttu-id="5bff4-113">我們對 App-v 5.0 的意見反應感興趣。</span><span class="sxs-lookup"><span data-stu-id="5bff4-113">We are interested in your feedback on App-V 5.0.</span></span> <span data-ttu-id="5bff4-114">您可以將意見反應傳送給您 <mdopdocs@microsoft.com> 。</span><span class="sxs-lookup"><span data-stu-id="5bff4-114">You can send your feedback to <mdopdocs@microsoft.com>.</span></span>

<span data-ttu-id="5bff4-115">**記事** 此電子郵件地址不是支援頻道，但您的意見反應將協助我們規劃我們的檔和產品版本中的未來變更。</span><span class="sxs-lookup"><span data-stu-id="5bff4-115">**Note** This email address is not a support channel, but your feedback will help us to plan for future changes in our documentation and product releases.</span></span>

 

<span data-ttu-id="5bff4-116">如需 MDOP 及其他學習資源的最新資訊，請參閱[Mdop 資訊體驗](https://go.microsoft.com/fwlink/p/?LinkId=236032)頁面。</span><span class="sxs-lookup"><span data-stu-id="5bff4-116">For the latest information about MDOP and additional learning resources, see the [MDOP Information Experience](https://go.microsoft.com/fwlink/p/?LinkId=236032) page.</span></span>

<span data-ttu-id="5bff4-117">如需新更新或提供意見反應的詳細資訊，請在[Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445)或[Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447)上關注我們。</span><span class="sxs-lookup"><span data-stu-id="5bff4-117">For more information about new updates or to provide feedback, follow us on [Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445) or [Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447).</span></span>

## <span data-ttu-id="5bff4-118">應用程式虛擬化 5.0 SP2 的修補程式套件4已知問題</span><span class="sxs-lookup"><span data-stu-id="5bff4-118">Known Issues with Hotfix Package 4 for Application Virtualization 5.0 SP2</span></span>


### <span data-ttu-id="5bff4-119">卸載應用程式虛擬化 5.0 SP2 的修復程式套件4之後，套件停止運作</span><span class="sxs-lookup"><span data-stu-id="5bff4-119">Packages stop working after you uninstall Hotfix Package 4 for Application Virtualization 5.0 SP2</span></span>

<span data-ttu-id="5bff4-120">當應用程式虛擬化 5.0 SP2 的修補程式套件4已移除5.0 時，發佈的套件會停止運作。</span><span class="sxs-lookup"><span data-stu-id="5bff4-120">Packages published when Hotfix Package 4 for Application Virtualization 5.0 SP2 is applied stop working when Hotfix Package 4 for Application Virtualization 5.0 SP2 is removed.</span></span>

<span data-ttu-id="5bff4-121">避免</span><span class="sxs-lookup"><span data-stu-id="5bff4-121">WORKAROUND:</span></span>

<span data-ttu-id="5bff4-122">如果下列資料夾存在，則必須將它刪除：</span><span class="sxs-lookup"><span data-stu-id="5bff4-122">If the following folder exists, then you must delete it:</span></span>

<span data-ttu-id="5bff4-123">**% localappdata%**  \\ **Microsoft**  \\ **AppV**  \\ **用戶端**  \\ **VFS**  \\ 已發佈的每個套件的\*\* &lt; 封裝識別碼 &gt; \*\* 。</span><span class="sxs-lookup"><span data-stu-id="5bff4-123">**%localappdata%** \\ **Microsoft** \\ **AppV** \\ **Client** \\ **VFS** \\ **&lt;package ID&gt;** for each package that was published.</span></span>

<span data-ttu-id="5bff4-124">**記事** 您必須具備較高的許可權才能刪除此資料夾。</span><span class="sxs-lookup"><span data-stu-id="5bff4-124">**Note** You must have elevated privileges to delete this folder.</span></span>

 

<span data-ttu-id="5bff4-125">若要使用腳本，針對電腦上的每個使用者帳戶，以及在安裝應用程式虛擬化 5.0 SP2 的修復程式套件4之後所發佈的每個套件識別碼：</span><span class="sxs-lookup"><span data-stu-id="5bff4-125">To use a script, for each user account on the computer and for each package id that was published after installing Hotfix Package 4 for Application Virtualization 5.0 SP2:</span></span>

`Rd /s /q “%systemdrive%\users\[UserName]\AppData\Local\Microsoft\AppV\Client\VFS\[Package ID]`

-   <span data-ttu-id="5bff4-126">即使從上一節的目錄刪除資料夾後，快速鍵仍會保留在使用者會話中，因此您可以按一下快捷方式來再次執行應用程式。</span><span class="sxs-lookup"><span data-stu-id="5bff4-126">The shortcuts will remain with the user sessions even after deleting the folder from the directory in the previous section, so you can click on the shortcut to run the application again.</span></span> <span data-ttu-id="5bff4-127">您不需要重新發佈應用程式。</span><span class="sxs-lookup"><span data-stu-id="5bff4-127">There is no need to re-publish the application.</span></span>

-   <span data-ttu-id="5bff4-128">對於使用者發佈的封裝及全域發佈套件（例如 Microsoft Office2013），會發生這個問題。</span><span class="sxs-lookup"><span data-stu-id="5bff4-128">This issue happens for both user published packaged and globally published packages for example, Microsoft Office2013.</span></span> <span data-ttu-id="5bff4-129">在這兩種類型的套件中都必須刪除該資料夾。</span><span class="sxs-lookup"><span data-stu-id="5bff4-129">The folder must be deleted for both types of packages.</span></span>

-   <span data-ttu-id="5bff4-130">您不需要刪除漫遊應用程式資料中的 VFS 資料夾（**% appdata%**）。</span><span class="sxs-lookup"><span data-stu-id="5bff4-130">You do not need to delete the VFS folder in the Roaming app data (**%appdata%**).</span></span> <span data-ttu-id="5bff4-131">只有 **% localappdata%** 必須刪除。</span><span class="sxs-lookup"><span data-stu-id="5bff4-131">Only the **%localappdata%** must be deleted.</span></span>

### <span data-ttu-id="5bff4-132">Microsoft Office 整合指向錯誤的檔案系統位置</span><span class="sxs-lookup"><span data-stu-id="5bff4-132">Microsoft Office integration points to wrong file system location</span></span>

<span data-ttu-id="5bff4-133">Microsoft Office 整合指向錯誤的檔案系統位置（Groove.exe 錯誤訊息）。</span><span class="sxs-lookup"><span data-stu-id="5bff4-133">Microsoft Office integration points to wrong file system location (Groove.exe error message).</span></span>

<span data-ttu-id="5bff4-134">避免</span><span class="sxs-lookup"><span data-stu-id="5bff4-134">WORKAROUND:</span></span>

<span data-ttu-id="5bff4-135">使用下列其中一種方法：</span><span class="sxs-lookup"><span data-stu-id="5bff4-135">Use one of the following methods:</span></span>

1.  <span data-ttu-id="5bff4-136">升級後刪除開機檔案夾中的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="5bff4-136">Delete the shortcut in the start-up folder after upgrade.</span></span>

2.  <span data-ttu-id="5bff4-137">使用腳本變更開機檔案夾中的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="5bff4-137">Change the shortcut in the start-up folder using a script.</span></span>

3.  <span data-ttu-id="5bff4-138">使用部署設定檔，指定整合根的快捷方式目標。</span><span class="sxs-lookup"><span data-stu-id="5bff4-138">Use the deployment configuration file to specify the shortcut target to the integration root.</span></span>

### <a href="" id="-------------hotfix-package-4-for-application-virtualization-5-0-sp2-installer-can-take-a-long-time"></a> <span data-ttu-id="5bff4-139">應用程式虛擬化5.0 的修補程式套件 4 SP2 安裝程式可能需要花費很長的時間</span><span class="sxs-lookup"><span data-stu-id="5bff4-139">Hotfix Package 4 for Application Virtualization 5.0 SP2 installer can take a long time</span></span>

<span data-ttu-id="5bff4-140">應用程式虛擬化 5.0 SP2 安裝程式的修復程式套件4可能需要花很長的時間，這取決於現有套件快取中所儲存的檔案數目。</span><span class="sxs-lookup"><span data-stu-id="5bff4-140">The Hotfix Package 4 for Application Virtualization 5.0 SP2 installer can potentially take a long time depending on how many files are stored in the existing package cache.</span></span>

<span data-ttu-id="5bff4-141">在針對應用程式虛擬化 5.0 SP2 安裝的修復程式套件4中更新關聯的套件安全性描述項，會對安裝所需的時間產生很大的影響。</span><span class="sxs-lookup"><span data-stu-id="5bff4-141">Updating associated package security descriptors during the Hotfix Package 4 for Application Virtualization 5.0 SP2 installation has a significant impact on how long it takes the installation will take.</span></span> <span data-ttu-id="5bff4-142">在先前，安裝安裝為 [持續時間] 的標準。</span><span class="sxs-lookup"><span data-stu-id="5bff4-142">Previously, the installation install was standard in duration.</span></span> <span data-ttu-id="5bff4-143">不過，它現在依賴您在套件快取中暫存的檔案數目。</span><span class="sxs-lookup"><span data-stu-id="5bff4-143">However, it now depends on how many files you have staged in the package cache.</span></span>

<span data-ttu-id="5bff4-144">因應措施：無</span><span class="sxs-lookup"><span data-stu-id="5bff4-144">WORKAROUND: None</span></span>

### <span data-ttu-id="5bff4-145">卸載應用程式虛擬化5.0 的修復程式套件4如果使用的是 JIT V 套件，SP2 會失敗</span><span class="sxs-lookup"><span data-stu-id="5bff4-145">Uninstalling Hotfix Package 4 for Application Virtualization 5.0 SP2 fails if JIT-V package is in use</span></span>

<span data-ttu-id="5bff4-146">如果您安裝應用程式虛擬化 5.0 SP2 的修補程式套件4，然後嘗試在使用即時虛擬化（JIT-V）時卸載此熱修復程式，則在下列所有條件成立時，該作業將會失敗：</span><span class="sxs-lookup"><span data-stu-id="5bff4-146">If you install Hotfix Package 4 for Application Virtualization 5.0 SP2 and then try to uninstall the hotfix when just-in-time virtualization (JIT-V) is being used, the operation will fail if all of the following conditions are true:</span></span>

-   <span data-ttu-id="5bff4-147">您是使用 Windows 安裝程式檔案（.msi）安裝，然後使用 Microsoft Installer 修補程式檔案（.msp）來套用更新。</span><span class="sxs-lookup"><span data-stu-id="5bff4-147">You installed by using a Windows Installer file (.msi), and then you apply updates by using a Microsoft Installer Patch File (.msp).</span></span>

-   <span data-ttu-id="5bff4-148">您嘗試使用 [控制台] 中的 [新增或移除程式] 專案來卸載更新。</span><span class="sxs-lookup"><span data-stu-id="5bff4-148">You try to uninstall an update by using the Add or Remove Programs item in Control Panel.</span></span>

-   <span data-ttu-id="5bff4-149">電腦上正在執行 JIT 啟用的套件。</span><span class="sxs-lookup"><span data-stu-id="5bff4-149">A JIT-V-enabled package is running on the computer.</span></span>

<span data-ttu-id="5bff4-150">解決方法：完成下列步驟：</span><span class="sxs-lookup"><span data-stu-id="5bff4-150">WORKAROUND: Complete the following steps:</span></span>

1.  <span data-ttu-id="5bff4-151">開啟 Windows PowerShell，然後執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="5bff4-151">Open Windows PowerShell and run the following commands:</span></span>

    -   **<span data-ttu-id="5bff4-152">匯入-模組 appvclient</span><span class="sxs-lookup"><span data-stu-id="5bff4-152">Import-module appvclient</span></span>**

    -   **<span data-ttu-id="5bff4-153">AppvClientPackage |停止 AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="5bff4-153">Get-AppvClientPackage | Stop-AppvClientPackage</span></span>**

2.  <span data-ttu-id="5bff4-154">使用 [新增或移除程式] 卸載更新。</span><span class="sxs-lookup"><span data-stu-id="5bff4-154">Uninstall the update using Add or Remove Programs.</span></span>

## <span data-ttu-id="5bff4-155">App-v 5.0 SP2 的已知問題</span><span class="sxs-lookup"><span data-stu-id="5bff4-155">Known Issues with App-V 5.0 SP2</span></span>


### <a href="" id="bkmk-folderredirection"></a><span data-ttu-id="5bff4-156">App-V 用戶端資料夾重新導向有時無法將檔案從% AppData% 移至% LocalAppData%</span><span class="sxs-lookup"><span data-stu-id="5bff4-156">App-V client folder redirection sometimes fails to move files from %AppData% to %LocalAppData%</span></span>

<span data-ttu-id="5bff4-157">當% AppData% 是您針對資料夾重新導向所設定的共用網路資料夾時，當使用者切換電腦時，或當他們的本地 AppData 在登出後再重新登入時，可能會遺失最終使用者對 AppData （漫遊）所做的變更。</span><span class="sxs-lookup"><span data-stu-id="5bff4-157">When %AppData% is a shared network folder that you have configured for folder redirection, the changes that end users make to AppData (Roaming) can be lost when they switch computers or when their local AppData is cleared when they log off and then log back on.</span></span> <span data-ttu-id="5bff4-158">發生此錯誤的原因是登錄機碼（AppDataTime）會指出最近已知上傳的與本機快取 AppData 的同步處理。</span><span class="sxs-lookup"><span data-stu-id="5bff4-158">This error occurs because the registry key (AppDataTime), which indicates the last known upload, gets out of synchronization with the local cached AppData.</span></span>

<span data-ttu-id="5bff4-159">解決方法：當使用者登入或關閉時，手動刪除每個相關套件的下列登錄機碼：</span><span class="sxs-lookup"><span data-stu-id="5bff4-159">WORKAROUND: Manually delete the following registry key for each relevant package when an end user logs on or off:</span></span>

``` syntax
HKCU\Software\Microsoft\AppV\Client\Packages\<PACKAGE_GUID>\AppDataTime
```

<span data-ttu-id="5bff4-160">當使用者登入後第一次在套件中啟動應用程式時，App-v 會強制下載 zipped% AppData%，即使% LocalAppData% 已經是最新的。</span><span class="sxs-lookup"><span data-stu-id="5bff4-160">The first time that end users start an application in the package after they log in, App-V forces a download of the zipped %AppData%, even if %LocalAppData% is already up to date.</span></span>

### <a href="" id="-------------app-v-5-0-service-pack-2--app-v-5-0-sp2--does-not-include-a-new-version-of-the-app-v-server"></a> <span data-ttu-id="5bff4-161">App-v 5.0 Service Pack 2 （App-v 5.0 SP2）不包含新版本的 App-v Server</span><span class="sxs-lookup"><span data-stu-id="5bff4-161">App-V 5.0 Service Pack 2 (App-V 5.0 SP2) does not include a new version of the App-V Server</span></span>

<span data-ttu-id="5bff4-162">App-V 5.0 SP2 不包含新版的 App-v 伺服器。</span><span class="sxs-lookup"><span data-stu-id="5bff4-162">App-V 5.0SP2 does not include a new version of the App-V Server.</span></span> <span data-ttu-id="5bff4-163">如果您要部署在您的環境中執行 Windows 8.1 的 App-v 5.0 SP2 用戶端，並規劃使用 App-v 基礎結構管理用戶端，您必須安裝[Microsoft Application Virtualization 5.0 Service Pack 1 的修補程式套件 2](https://go.microsoft.com/fwlink/?LinkId=386634)。</span><span class="sxs-lookup"><span data-stu-id="5bff4-163">If you deploy App-V 5.0 SP2 clients running Windows 8.1 in your environment and plan to manage the clients using the App-V infrastructure, you must install [Hotfix Package 2 for Microsoft Application Virtualization 5.0 Service Pack 1](https://go.microsoft.com/fwlink/?LinkId=386634).</span></span> <span data-ttu-id="5bff4-164">(https://go.microsoft.com/fwlink/?LinkId=386634)</span><span class="sxs-lookup"><span data-stu-id="5bff4-164">(https://go.microsoft.com/fwlink/?LinkId=386634)</span></span>

<span data-ttu-id="5bff4-165">如果您正在執行和管理 App-v 5.0 SP2 用戶端使用下列任何一種方法，則不需要用戶端更新程式：</span><span class="sxs-lookup"><span data-stu-id="5bff4-165">If you are running and managing App-V 5.0 SP2 clients using any of the following methods no client update is required:</span></span>

-   <span data-ttu-id="5bff4-166">獨立模式。</span><span class="sxs-lookup"><span data-stu-id="5bff4-166">Standalone mode.</span></span>

-   <span data-ttu-id="5bff4-167">Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="5bff4-167">Configuration Manager.</span></span>

-   <span data-ttu-id="5bff4-168">協力廠商 ESD。</span><span class="sxs-lookup"><span data-stu-id="5bff4-168">Third party ESD.</span></span>

<span data-ttu-id="5bff4-169">App-v 5.0 SP2 用戶端與 Windows 8.1 完全相容</span><span class="sxs-lookup"><span data-stu-id="5bff4-169">The App-V 5.0 SP2 client is fully compatible with Windows 8.1</span></span>

<span data-ttu-id="5bff4-170">因應措施：無。</span><span class="sxs-lookup"><span data-stu-id="5bff4-170">WORKAROUND: None.</span></span>

## <span data-ttu-id="5bff4-171">版本資訊版權資訊</span><span class="sxs-lookup"><span data-stu-id="5bff4-171">Release Notes Copyright Information</span></span>


<span data-ttu-id="5bff4-172">Microsoft、Active Directory、ActiveX、Bing、Excel、Silverlight、SQLServer、Windows、MicrosoftIntune 和 WindowsPowerShell 是 Microsoft 公司群組的商標。</span><span class="sxs-lookup"><span data-stu-id="5bff4-172">Microsoft, Active Directory, ActiveX, Bing, Excel, Silverlight, SQLServer, Windows, MicrosoftIntune, and WindowsPowerShell are trademarks of the Microsoft group of companies.</span></span> <span data-ttu-id="5bff4-173">所有其他商標都是其各自擁有者的財產。</span><span class="sxs-lookup"><span data-stu-id="5bff4-173">All other trademarks are property of their respective owners.</span></span>








## <span data-ttu-id="5bff4-174">相關主題</span><span class="sxs-lookup"><span data-stu-id="5bff4-174">Related topics</span></span>


[<span data-ttu-id="5bff4-175">關於 App-V 5.0 SP2</span><span class="sxs-lookup"><span data-stu-id="5bff4-175">About App-V 5.0 SP2</span></span>](about-app-v-50-sp2.md)

 

 





