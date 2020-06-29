---
title: MED-V 2.0 的新功能
description: MED-V 2.0 的新功能
author: dansimp
ms.assetid: 53b10bff-2b6f-463b-bdc2-5edc56526792
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 78dba25fec7ae2bb41da00902b59dcd15030f2b6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810113"
---
# <span data-ttu-id="eea2e-103">MED-V 2.0 的新功能</span><span class="sxs-lookup"><span data-stu-id="eea2e-103">What's New in MED-V 2.0</span></span>


<span data-ttu-id="eea2e-104">Microsoft 企業版桌面虛擬化（MED-V）2.0 已演化了 Windows 7 的應用程式相容性支援，以及此案例不需要的已移除功能。</span><span class="sxs-lookup"><span data-stu-id="eea2e-104">Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 has evolved the application compatibility support for Windows 7 and removed functionality that is not required for this scenario.</span></span> <span data-ttu-id="eea2e-105">例如，諸如在 MED-V 工作區中加密、集中的 MED-V 伺服器以及 MED-V 工作區修剪傳輸等功能都已移除。</span><span class="sxs-lookup"><span data-stu-id="eea2e-105">For example, features such as encryption of the MED-V workspace, the centralized MED-V server, and MED-V workspace trim transfer have been removed.</span></span>

## <span data-ttu-id="eea2e-106">標準功能的變更</span><span class="sxs-lookup"><span data-stu-id="eea2e-106">Changes in Standard Functionality</span></span>


<span data-ttu-id="eea2e-107">本節討論 MED-V 2.0 功能變更的主要區域。</span><span class="sxs-lookup"><span data-stu-id="eea2e-107">This section discusses the key areas where MED-V 2.0 functionality has changed.</span></span>

### <span data-ttu-id="eea2e-108">MED-V-V 工作區建立</span><span class="sxs-lookup"><span data-stu-id="eea2e-108">MED-V Workspace Creation</span></span>

<span data-ttu-id="eea2e-109">MED-V 工作區所用的虛擬硬碟現已在 Windows 虛擬電腦中建立。</span><span class="sxs-lookup"><span data-stu-id="eea2e-109">The virtual hard disk used for the MED-V workspace is now created in Windows Virtual PC.</span></span> <span data-ttu-id="eea2e-110">用來建立 MED-V 工作區的方法包括安裝 Windows XP SP3、更新作業系統，並準備要透過軟體管理基礎結構加以管理。</span><span class="sxs-lookup"><span data-stu-id="eea2e-110">The methods that are used to create the MED-V workspace include installing Windows XP SP3, updating the operating system, and preparing it to be managed through software management infrastructure.</span></span>

<span data-ttu-id="eea2e-111">除了專有的 MED-V 工作區加密和壓縮功能之外，還會移除離線管理和修剪傳送功能。</span><span class="sxs-lookup"><span data-stu-id="eea2e-111">The offline management and trim transfer functionality were removed, in addition to the proprietary MED-V workspace encryption and compression functionality.</span></span> <span data-ttu-id="eea2e-112">當您建立 MED-V 工作區時，系統管理員應該在影像中準備並設定適當的應用程式和管理工具，而不是使用 MED-V 1.0 中提供的虛擬機器準備工具。</span><span class="sxs-lookup"><span data-stu-id="eea2e-112">When you create a MED-V workspace, an administrator should prepare and configure appropriate applications and management tools in the image instead of using the virtual machine preparation tool that is provided in MED-V 1.0.</span></span>

<span data-ttu-id="eea2e-113">在您的 MED-V 工作區封裝期間，現在需要並驗證在 MED-V 影像上執行 Sysprep。</span><span class="sxs-lookup"><span data-stu-id="eea2e-113">Running Sysprep on the MED-V image is now required and validated during the packaging of the MED-V workspace.</span></span> <span data-ttu-id="eea2e-114">MED-V 工作區包裝程式提供圖形使用者介面（GUI），可引導管理員完成封裝程式。</span><span class="sxs-lookup"><span data-stu-id="eea2e-114">The MED-V Workspace Packager provides a graphical user interface (GUI) that guides the administrator through the packaging process.</span></span> <span data-ttu-id="eea2e-115">從 MED-V 1.0 的主控台已與管理影像、管理 MED-V 工作區設定檔，以及暫存和加密 MED-V 工作區的需求搭配使用。</span><span class="sxs-lookup"><span data-stu-id="eea2e-115">The console from MED-V 1.0 was removed together with the functionality of managing images, managing MED-V workspace profiles, and the requirement to stage and encrypt MED-V workspaces.</span></span>

### <span data-ttu-id="eea2e-116">MED-V 工作區部署</span><span class="sxs-lookup"><span data-stu-id="eea2e-116">MED-V Workspace Deployment</span></span>

<span data-ttu-id="eea2e-117">若要部署 MED-V 工作區，管理員現在可以充分利用其電子軟體發佈工具。</span><span class="sxs-lookup"><span data-stu-id="eea2e-117">To deploy a MED-V workspace, an administrator is now able to take advantage of their electronic software distribution tools.</span></span> <span data-ttu-id="eea2e-118">已移除 MED-V 1.0 中提供的用戶端 pull 方法，現已使用 MED-V 外的方法來傳送 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="eea2e-118">The client-pull method available in MED-V 1.0 was removed and the MED-V workspace is now delivered by using methods outside MED-V.</span></span> <span data-ttu-id="eea2e-119">系統管理員可以像對待任何其他應用程式套件一樣，處理 MED-V 工作區，而且可以使用現有的工具和程式來排程 MED-V 的部署和安裝。</span><span class="sxs-lookup"><span data-stu-id="eea2e-119">Administrators can treat MED-V workspaces as they would any other application package and can schedule deployments and installations of MED-V by using their existing tools and processes.</span></span> <span data-ttu-id="eea2e-120">MED-V 安裝可以悄悄地部署，而且可以在現有的軟體發佈基礎結構中輕鬆管理。</span><span class="sxs-lookup"><span data-stu-id="eea2e-120">MED-V installations can be deployed silently and can easily be managed inside an existing software distribution infrastructure.</span></span>

### <span data-ttu-id="eea2e-121">MED-V 工作區管理</span><span class="sxs-lookup"><span data-stu-id="eea2e-121">MED-V Workspace Management</span></span>

<span data-ttu-id="eea2e-122">MED-V 2.0 中的 MED-V 工作區是以 Windows 虛擬電腦虛擬硬碟為基礎。</span><span class="sxs-lookup"><span data-stu-id="eea2e-122">The MED-V workspace in MED-V 2.0 is based on a Windows Virtual PC virtual hard disk.</span></span> <span data-ttu-id="eea2e-123">MED-V 已延伸 Windows 虛擬電腦提供的功能，不需要使用加密或特殊工具存取 MED-V 工作區，即可改善無縫體驗。</span><span class="sxs-lookup"><span data-stu-id="eea2e-123">MED-V has extended the capabilities that Windows Virtual PC provides by improving the seamless experience without requiring encryption or special tools to access the MED-V workspace.</span></span>

<span data-ttu-id="eea2e-124">將 MED-V 部署到工作站之後，就可以使用 Windows 虛擬電腦以全螢幕模式開啟 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="eea2e-124">After MED-V is deployed to a workstation, the MED-V workspace can be opened in full-screen mode by using Windows Virtual PC.</span></span> <span data-ttu-id="eea2e-125">這項新功能已移除針對無縫或全螢幕模式設定喜好設定的原則需求，同時還移除了需要強制全螢幕以進行診斷和疑難排解的需求。</span><span class="sxs-lookup"><span data-stu-id="eea2e-125">This new functionality removed the requirement for policies that set a preference for seamless or full-screen modes and also removed the need to force full-screen for diagnostics and troubleshooting.</span></span>

<span data-ttu-id="eea2e-126">將應用程式發佈到 MED-V 工作區後，就不會再使用設定檔來執行，而是手動輸入應用程式的路徑。</span><span class="sxs-lookup"><span data-stu-id="eea2e-126">Publishing applications to the MED-V workspace is no longer performed with profiles and by manually entering the path to applications.</span></span> <span data-ttu-id="eea2e-127">相反地，它會在來賓上安裝應用程式時自動執行。</span><span class="sxs-lookup"><span data-stu-id="eea2e-127">Instead, it occurs automatically as applications are installed on the guest.</span></span> <span data-ttu-id="eea2e-128">已移除包含透過修剪傳輸傳送之影像版本的中央影像儲存庫。</span><span class="sxs-lookup"><span data-stu-id="eea2e-128">The central image repository that included versions of the images that were delivered through trim transfer is removed.</span></span> <span data-ttu-id="eea2e-129">相反地，MED-V 可讓系統管理員管理實際電腦等 MED-V 工作區，只要在沒有專用的 MED-V 基礎結構的複雜性的情況下，就能散佈應用程式和更新。</span><span class="sxs-lookup"><span data-stu-id="eea2e-129">Instead, MED-V enables administrators to manage the MED-V workspace as they would a physical computer, by letting applications and updates be distributed without the complexity of a dedicated MED-V infrastructure.</span></span>

## <span data-ttu-id="eea2e-130">MED-V 功能中的變更</span><span class="sxs-lookup"><span data-stu-id="eea2e-130">Changes in MED-V Features</span></span>


<span data-ttu-id="eea2e-131">MED-V 2.0 的幾個重要區域反映了下列功能的改善或新增功能。</span><span class="sxs-lookup"><span data-stu-id="eea2e-131">Several key areas of MED-V 2.0 reflect improvements or additions to the following features.</span></span>

### <span data-ttu-id="eea2e-132">MED-V-V 工作區建立</span><span class="sxs-lookup"><span data-stu-id="eea2e-132">MED-V Workspace Creation</span></span>

<span data-ttu-id="eea2e-133">必須使用 Windows 虛擬電腦建立 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="eea2e-133">MED-V workspaces must be created by using Windows Virtual PC.</span></span> <span data-ttu-id="eea2e-134">您必須先遷移現有的虛擬 PC 2007 影像。</span><span class="sxs-lookup"><span data-stu-id="eea2e-134">Existing Virtual PC 2007 images must be migrated.</span></span> <span data-ttu-id="eea2e-135">在 MED-V 2.0 中不包含「虛擬機器準備」工具，管理員應該根據 MED-V 2.0 說明檔案來設定、更新及優化其影像。</span><span class="sxs-lookup"><span data-stu-id="eea2e-135">The virtual machine Prep tool is not included in MED-V 2.0 and administrators should configure, update, and optimize their images according to the MED-V 2.0 Help file.</span></span> <span data-ttu-id="eea2e-136">在 MED-V 影像上執行 Sysprep 是必要的步驟，必須在封裝之前執行。</span><span class="sxs-lookup"><span data-stu-id="eea2e-136">Running Sysprep on the MED-V image is a required step and must be performed before packaging.</span></span>

### <span data-ttu-id="eea2e-137">MED-V 工作區封裝</span><span class="sxs-lookup"><span data-stu-id="eea2e-137">MED-V Workspace Packaging</span></span>

<span data-ttu-id="eea2e-138">Windows PowerShell 是 MED-V 工作區包裝程式的基礎。</span><span class="sxs-lookup"><span data-stu-id="eea2e-138">Windows PowerShell is the foundation of the MED-V Workspace Packager.</span></span> <span data-ttu-id="eea2e-139">此功能取代了一些舊版的主機功能，也就是 MED-V 中受管理的集中式功能。</span><span class="sxs-lookup"><span data-stu-id="eea2e-139">This functionality replaces some former console abilities and functionality that managed centralized functions of MED-V.</span></span> <span data-ttu-id="eea2e-140">MED-V 工作區包裝程式只會將具有適當設定和影像的虛擬硬碟封裝在一起，以便由系統管理員輕鬆部署。</span><span class="sxs-lookup"><span data-stu-id="eea2e-140">The MED-V Workspace Packager merely packages the virtual hard disk with the appropriate settings and image so that it can be easily deployed by administrators.</span></span> <span data-ttu-id="eea2e-141">您可以使用 Windows PowerShell 來提供高級功能。</span><span class="sxs-lookup"><span data-stu-id="eea2e-141">Advanced features are provided by using Windows PowerShell.</span></span>

### <span data-ttu-id="eea2e-142">MED-V 工作區分配</span><span class="sxs-lookup"><span data-stu-id="eea2e-142">MED-V Workspace Distribution</span></span>

<span data-ttu-id="eea2e-143">MED-V 2.0 不再需要專用伺服器基礎結構，且已移除部署 MED-V 工作區的用戶端 pull 方法。</span><span class="sxs-lookup"><span data-stu-id="eea2e-143">Dedicated server infrastructure is no longer required for MED-V 2.0 and the client pull method to deploy MED-V workspaces was removed.</span></span> <span data-ttu-id="eea2e-144">MED-V 工作區現在是使用您的電子軟體發佈基礎結構來部署，而且可以儲存在其他安裝套件所用的常見共用上。</span><span class="sxs-lookup"><span data-stu-id="eea2e-144">MED-V workspaces are now deployed using your electronic software distribution infrastructure and can be stored on common shares that are used for other installation packages.</span></span>

### <span data-ttu-id="eea2e-145">第一次設定</span><span class="sxs-lookup"><span data-stu-id="eea2e-145">First Time Setup</span></span>

<span data-ttu-id="eea2e-146">第一次設定程式現已與 Sysprep 的標準成像慣例整合。</span><span class="sxs-lookup"><span data-stu-id="eea2e-146">The first time setup process is now integrated with the standard imaging convention of Sysprep.</span></span> <span data-ttu-id="eea2e-147">使用 MED-V 工作區第一次時，設定處理常式可以動態地將在 MED-V 工作區包裝程式中指定的設定動態套用至影像，因為它會開始迷你設定。</span><span class="sxs-lookup"><span data-stu-id="eea2e-147">The MED-V workspace first time setup process can dynamically apply settings specified in the MED-V Workspace Packager to the image as it begins Mini-Setup.</span></span> <span data-ttu-id="eea2e-148">已移除主機中的 [腳本工具]，第一次安裝程式會根據管理員在 MED-V 工作區中設定的選項來進行。</span><span class="sxs-lookup"><span data-stu-id="eea2e-148">The scripting tool in the console was removed and the first time setup process is now based on options that are configured in the MED-V Workspace Packager by the administrator.</span></span>

### <span data-ttu-id="eea2e-149">應用程式發佈</span><span class="sxs-lookup"><span data-stu-id="eea2e-149">Application Publishing</span></span>

<span data-ttu-id="eea2e-150">在部署 MED-V 工作區之後，系統管理員可以在 MED-V 影像上安裝應用程式，或同時使用兩者結合。</span><span class="sxs-lookup"><span data-stu-id="eea2e-150">Administrators can install applications on the MED-V image either before packaging, after the MED-V workspace is deployed, or by using a combination of both.</span></span> <span data-ttu-id="eea2e-151">MED-V 不會再檢查 MED-V 工作區原則以發佈應用程式，而是參照來賓上實際安裝的元件。</span><span class="sxs-lookup"><span data-stu-id="eea2e-151">MED-V no longer examines MED-V workspace policy to publish applications, but instead refers to what is actually installed on the guest.</span></span> <span data-ttu-id="eea2e-152">當應用程式安裝在來賓上時，系統會自動偵測併發布至主機 [**開始**] 功能表，且已準備好由最終使用者開始。</span><span class="sxs-lookup"><span data-stu-id="eea2e-152">As applications are installed on the guest, they are automatically detected and published to the host **Start** menu and are ready to be started by the end user.</span></span>

### <span data-ttu-id="eea2e-153">URL 重新導向</span><span class="sxs-lookup"><span data-stu-id="eea2e-153">URL Redirection</span></span>

<span data-ttu-id="eea2e-154">MED-V 2.0 根據系統管理員設定和管理的原則，提供無縫的主機對訪客網址重新導向。</span><span class="sxs-lookup"><span data-stu-id="eea2e-154">MED-V 2.0 provides seamless host-to-guest web address redirection based on the policies configured and managed by the administrator.</span></span> <span data-ttu-id="eea2e-155">將 URL 重新導向至來賓瀏覽器之後，預設的體驗是嘗試將使用者限制在該重新導向的網站上。</span><span class="sxs-lookup"><span data-stu-id="eea2e-155">After a URL is redirected to the guest browser, the default experience is to attempt to limit the user to that redirected site.</span></span> <span data-ttu-id="eea2e-156">這會將使用者所能執行的流覽活動最小化，而不是由系統管理員所設計。</span><span class="sxs-lookup"><span data-stu-id="eea2e-156">This minimizes the browsing activities that a user can perform that are not intended by the administrator.</span></span> <span data-ttu-id="eea2e-157">已移除來賓對主機瀏覽器的重新導向。</span><span class="sxs-lookup"><span data-stu-id="eea2e-157">Guest-to-host browser redirection was removed.</span></span>

### <span data-ttu-id="eea2e-158">疑難排解</span><span class="sxs-lookup"><span data-stu-id="eea2e-158">Troubleshooting</span></span>

<span data-ttu-id="eea2e-159">MED-V 現在會利用標準主機程式來進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="eea2e-159">MED-V now takes advantage of standard host-based processes for troubleshooting.</span></span> <span data-ttu-id="eea2e-160">因為 MED-V 工作區已不再加密，所以它可以在 Windows 虛擬電腦主控台內以全螢幕模式開啟，您可以在此以標準工作站的形式查看和使用它。</span><span class="sxs-lookup"><span data-stu-id="eea2e-160">Because the MED-V workspace is no longer encrypted, it can be opened in full-screen mode within the Windows Virtual PC console, where it can be viewed and worked with as a standard workstation.</span></span> <span data-ttu-id="eea2e-161">此外，記錄不會在本機進行加密，也不會集中記錄。</span><span class="sxs-lookup"><span data-stu-id="eea2e-161">In addition, the logs are no longer encrypted locally and logged centrally.</span></span> <span data-ttu-id="eea2e-162">MED-V 現在會大量使用本機事件記錄，而輸出的記錄層級（從資訊到調試層級）就能輕鬆設定。</span><span class="sxs-lookup"><span data-stu-id="eea2e-162">MED-V now makes extensive use of the local event logs, and the logging level of the output, from informational to debug levels, can be easily configured.</span></span> <span data-ttu-id="eea2e-163">最後，我們已提供疑難排解工具，讓管理員與技術支援人員都能以圖形、匯總的方式顯示所有疑難排解選項，而且他們可以輕鬆地選取最符合其需求的活動。</span><span class="sxs-lookup"><span data-stu-id="eea2e-163">Finally, a troubleshooting toolkit is now provided so administrators and helpdesk personnel can have a graphical, aggregated view of all the troubleshooting options, and they can effortlessly select the activities that most suit their needs.</span></span>

<span data-ttu-id="eea2e-164">MED-V 已不再以系統服務的方式執行。</span><span class="sxs-lookup"><span data-stu-id="eea2e-164">MED-V is no longer run as a system service.</span></span> <span data-ttu-id="eea2e-165">相反地，它是以使用者擁有的程式的方式執行，而且只有在使用者登入時才會執行。</span><span class="sxs-lookup"><span data-stu-id="eea2e-165">Instead, it is run as user-owned processes, and it only runs when a user is logged on.</span></span><span data-ttu-id="eea2e-166">先前由由系統擁有的服務所提供的功能，現在已在使用者端程式中提供。</span><span class="sxs-lookup"><span data-stu-id="eea2e-166">Functionality that was formerly provided by the system-owned service is now provided in the user-side processes.</span></span>

## <span data-ttu-id="eea2e-167">相關主題</span><span class="sxs-lookup"><span data-stu-id="eea2e-167">Related topics</span></span>


[<span data-ttu-id="eea2e-168">MED-V 部署</span><span class="sxs-lookup"><span data-stu-id="eea2e-168">Deployment of MED-V</span></span>](deployment-of-med-v.md)

[<span data-ttu-id="eea2e-169">適用於 MED-V 的操作</span><span class="sxs-lookup"><span data-stu-id="eea2e-169">Operations for MED-V</span></span>](operations-for-med-v.md)

 

 





