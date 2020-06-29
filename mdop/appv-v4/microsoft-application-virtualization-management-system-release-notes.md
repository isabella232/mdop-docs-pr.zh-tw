---
title: Microsoft Application Virtualization 管理系統版本資訊
description: Microsoft Application Virtualization 管理系統版本資訊
author: dansimp
ms.assetid: e1a4d5ee-53c7-4b48-814c-a34ce0e698dc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: c34abab9a49bd69f760a9b531d0950cc581253c1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800964"
---
# <span data-ttu-id="95eb2-103">Microsoft Application Virtualization 管理系統版本資訊</span><span class="sxs-lookup"><span data-stu-id="95eb2-103">Microsoft Application Virtualization Management System Release Notes</span></span>


<span data-ttu-id="95eb2-104">若要搜尋這些版本筆記，請按 CTRL + F。</span><span class="sxs-lookup"><span data-stu-id="95eb2-104">To search these Release Notes, press CTRL+F.</span></span>

<span data-ttu-id="95eb2-105">**重要** 在安裝應用程式虛擬化管理系統之前，請先閱讀這些版本資訊。</span><span class="sxs-lookup"><span data-stu-id="95eb2-105">**Important** Read these Release Notes thoroughly before you install the Application Virtualization Management System.</span></span> <span data-ttu-id="95eb2-106">這些版本資訊包含成功安裝應用程式虛擬化管理系統所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="95eb2-106">These Release Notes contain information that you need to successfully install the Application Virtualization Management System.</span></span> <span data-ttu-id="95eb2-107">此檔包含產品檔中不提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="95eb2-107">This document contains information that is not available in the product documentation.</span></span> <span data-ttu-id="95eb2-108">如果這些版本資訊與其他應用程式虛擬化管理系統檔的差異不一樣，最新的變更應該視為權威性。</span><span class="sxs-lookup"><span data-stu-id="95eb2-108">If there is a discrepancy between these Release Notes and other Application Virtualization Management System documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="95eb2-109">這些版本資訊取代本產品隨附的內容。</span><span class="sxs-lookup"><span data-stu-id="95eb2-109">These Release Notes supersede the content included with this product.</span></span>

 

<span data-ttu-id="95eb2-110">如需已知問題的更新資訊，請流覽 Microsoft TechNet 文件庫 <https://go.microsoft.com/fwlink/?LinkId=122918> 。</span><span class="sxs-lookup"><span data-stu-id="95eb2-110">For updated information about known issues, please visit the Microsoft TechNet Library at <https://go.microsoft.com/fwlink/?LinkId=122918>.</span></span>

## <span data-ttu-id="95eb2-111">關於 Microsoft Application Virtualization 4.5 累計更新1</span><span class="sxs-lookup"><span data-stu-id="95eb2-111">About Microsoft Application Virtualization 4.5 Cumulative Update 1</span></span>


<span data-ttu-id="95eb2-112">這些版本資訊已更新，以反映 Microsoft Application Virtualization 4.5 累加 Update1 （App-v 4.5 CU1）所引進的變更，這些變更提供應用程式虛擬化（app-v）4.5 的最新更新。</span><span class="sxs-lookup"><span data-stu-id="95eb2-112">These Release Notes have been updated to reflect the changes introduced with Microsoft Application Virtualization4.5 Cumulative Update1 (App-V4.5 CU1), which provides the latest updates to Application Virtualization (App-V)4.5.</span></span> <span data-ttu-id="95eb2-113">此累積更新包含下列變更：</span><span class="sxs-lookup"><span data-stu-id="95eb2-113">This cumulative update contains the following changes:</span></span>

-   <span data-ttu-id="95eb2-114">支援 Windows7 Beta 版和 Windows Server2008R2 Beta： App-v 4.5 CU1 解決 Windows7 Beta 與 Windows Server2008R2 Beta 版的相容性問題。</span><span class="sxs-lookup"><span data-stu-id="95eb2-114">Support for Windows7 Beta and Windows Server2008R2 Beta: App-V4.5 CU1 addresses compatibility issues with Windows7 Beta and Windows Server2008R2 Beta.</span></span> <span data-ttu-id="95eb2-115">支援將提供給封鎖問題，避免在 RTM 版本的 Windows7 中在測試環境中執行 App-v 4.5 CU1。</span><span class="sxs-lookup"><span data-stu-id="95eb2-115">Support will be provided for blocking issues that prevent App-V4.5 CU1 running in a test environment on pre-RTM versions of Windows7.</span></span> <span data-ttu-id="95eb2-116">這將有助於確保您的虛擬應用程式能在測試環境中順利執行，在此情況下，需要 App-v 4.5 用戶端與 Windows7 Beta 之間的相容性。</span><span class="sxs-lookup"><span data-stu-id="95eb2-116">This will help ensure that your virtual applications can run successfully in a test environment where compatibility between App-V4.5 Client and Windows7 Beta is required.</span></span>

    <span data-ttu-id="95eb2-117">**重要** 不支援在即時操作環境中的任何 Windows7 或 Windows Server2008R2 上執行 App-v 4.5 CU1。</span><span class="sxs-lookup"><span data-stu-id="95eb2-117">**Important** Running App-V4.5 CU1 on any version of Windows7 or Windows Server2008R2 in a live operating environment is not supported.</span></span>

     

-   <span data-ttu-id="95eb2-118">改良對 .NET Framework 排序的支援： App-v 4.5 CU1 解決先前在 WindowsXP （SP2 或更新版本）中排序 .NET Framework 3.5 及更舊版本的問題。</span><span class="sxs-lookup"><span data-stu-id="95eb2-118">Improved support for sequencing the .NET Framework: App-V4.5 CU1 addresses previous issues with sequencing the .NET Framework3.5 and earlier on WindowsXP (SP2 or later).</span></span> <span data-ttu-id="95eb2-119">如需新功能的詳細資訊，請參閱 TechNet 文章 <https://go.microsoft.com/fwlink/?LinkId=123412> 。</span><span class="sxs-lookup"><span data-stu-id="95eb2-119">For more information about the new capabilities, see the TechNet article at <https://go.microsoft.com/fwlink/?LinkId=123412>.</span></span>

-   <span data-ttu-id="95eb2-120">客戶意見反應與修復程式匯總： App-v 4.5 CU1 也包含自 App-v 4.5 RTM 版本以來發現問題的修正程式。</span><span class="sxs-lookup"><span data-stu-id="95eb2-120">Customer Feedback and Hotfix Rollup: App-V4.5 CU1 also includes a rollup up of fixes to address issues found since the App-V4.5 RTM release.</span></span> <span data-ttu-id="95eb2-121">這包括由我們內部團隊、合作夥伴和使用 App-v 4.5 的客戶提供的已知問題與客戶意見反應的結合。</span><span class="sxs-lookup"><span data-stu-id="95eb2-121">This includes a combination of known issues and customer feedback from our internal teams, partners, and customers who are using App-V4.5.</span></span> <span data-ttu-id="95eb2-122">如需隨附更新的完整清單，請參閱中的知識庫文章 <https://go.microsoft.com/fwlink/?LinkId=141258> 。</span><span class="sxs-lookup"><span data-stu-id="95eb2-122">For a full list of the included updates, see the KB article at <https://go.microsoft.com/fwlink/?LinkId=141258>.</span></span>

## <span data-ttu-id="95eb2-123">關於產品檔</span><span class="sxs-lookup"><span data-stu-id="95eb2-123">About the Product Documentation</span></span>


<span data-ttu-id="95eb2-124">應用程式虛擬化（app-v）的綜合檔可在應用程式虛擬化（app-v）技術中心的 Microsoft TechNet 上取得 <https://go.microsoft.com/fwlink/?LinkId=122939> 。</span><span class="sxs-lookup"><span data-stu-id="95eb2-124">Comprehensive documentation for Application Virtualization (App-V) is available on Microsoft TechNet in the Application Virtualization (App-V) TechCenter at <https://go.microsoft.com/fwlink/?LinkId=122939>.</span></span> <span data-ttu-id="95eb2-125">TechNet 檔包含應用程式虛擬化排序器、應用程式虛擬化用戶端和應用程式虛擬化伺服器的線上說明。</span><span class="sxs-lookup"><span data-stu-id="95eb2-125">The TechNet documentation includes the online Help for the Application Virtualization Sequencer, the Application Virtualization Client, and the Application Virtualization Server.</span></span> <span data-ttu-id="95eb2-126">它也包含應用程式虛擬化規劃與部署指南，以及應用程式虛擬化操作指南。</span><span class="sxs-lookup"><span data-stu-id="95eb2-126">It also includes the Application Virtualization Planning and Deployment Guide and the Application Virtualization Operations Guide.</span></span>

## <span data-ttu-id="95eb2-127">防範安全性漏洞與病毒</span><span class="sxs-lookup"><span data-stu-id="95eb2-127">Protect Against Security Vulnerabilities and Viruses</span></span>


<span data-ttu-id="95eb2-128">若要協助防範安全性漏洞和病毒，請務必為任何要安裝的新軟體安裝最新的可用安全更新。</span><span class="sxs-lookup"><span data-stu-id="95eb2-128">To help protect against security vulnerabilities and viruses, it is important to install the latest available security updates for any new software being installed.</span></span> <span data-ttu-id="95eb2-129">如需詳細資訊，請參閱 Microsoft 安全性網站 <https://go.microsoft.com/fwlink/?LinkId=3482> 。</span><span class="sxs-lookup"><span data-stu-id="95eb2-129">For more information, see the Microsoft Security Web site at <https://go.microsoft.com/fwlink/?LinkId=3482>.</span></span>

## <span data-ttu-id="95eb2-130">提供意見反應</span><span class="sxs-lookup"><span data-stu-id="95eb2-130">Providing Feedback</span></span>


<span data-ttu-id="95eb2-131">您可以透過 Microsoft Application Virtualization 技術中心（）上的社區論壇，提供意見反應，提出建議，或報告 Microsoft Application Virtualization （App-v）管理系統的問題 <https://go.microsoft.com/fwlink/?LinkId=122917> 。</span><span class="sxs-lookup"><span data-stu-id="95eb2-131">You can provide feedback, make a suggestion, or report an issue with the Microsoft Application Virtualization (App-V) Management System via a community forum on the Microsoft Application Virtualization TechCenter (<https://go.microsoft.com/fwlink/?LinkId=122917>).</span></span>

<span data-ttu-id="95eb2-132">您也可以將檔的意見反應直接提供給 App-v 檔小組。</span><span class="sxs-lookup"><span data-stu-id="95eb2-132">You can also provide your feedback on the documentation directly to the App-V documentation team.</span></span> <span data-ttu-id="95eb2-133">將您的檔意見反應傳送給 appvdocs@microsoft.com。</span><span class="sxs-lookup"><span data-stu-id="95eb2-133">Send your documentation feedback to appvdocs@microsoft.com.</span></span>

## <span data-ttu-id="95eb2-134">Application Virtualization 4.5 CU1 的已知問題</span><span class="sxs-lookup"><span data-stu-id="95eb2-134">Known Issues with Application Virtualization4.5 CU1</span></span>


<span data-ttu-id="95eb2-135">本節提供有關 Microsoft Application Virtualization （App-v） 4.5 CU1 問題的最新資訊。</span><span class="sxs-lookup"><span data-stu-id="95eb2-135">This section provides the most up-to-date information about issues with Microsoft Application Virtualization (App-V)4.5 CU1.</span></span> <span data-ttu-id="95eb2-136">這些問題不會出現在產品檔中，某些情況下，可能會矛盾現有的產品檔。</span><span class="sxs-lookup"><span data-stu-id="95eb2-136">These issues do not appear in the product documentation and in some cases might contradict existing product documentation.</span></span> <span data-ttu-id="95eb2-137">只要有可能，這些問題就會在後續版本中解決。</span><span class="sxs-lookup"><span data-stu-id="95eb2-137">Whenever possible, these issues will be addressed in later releases.</span></span>

### <span data-ttu-id="95eb2-138">使用 setup.msi 將用戶端安裝或升級至 App-v 4.5 CU1 的指導方針</span><span class="sxs-lookup"><span data-stu-id="95eb2-138">Guidance for installing or upgrading clients to App-V4.5 CU1 using setup.msi</span></span>

<span data-ttu-id="95eb2-139">當您使用 setup.msi 將 App-V 用戶端安裝或升級到 App V 4.5 CU1 時，系統不會自動安裝先決條件。</span><span class="sxs-lookup"><span data-stu-id="95eb2-139">When installing or upgrading your App-V clients to App-V4.5 CU1 by using setup.msi, the prerequisites are not installed automatically.</span></span>

<span data-ttu-id="95eb2-140">WORKAROUNDYou 必須先手動安裝必備元件，才能安裝或將 App-v 用戶端升級到 4.5 CU1。</span><span class="sxs-lookup"><span data-stu-id="95eb2-140">WORKAROUNDYou must manually install the prerequisites before installing or upgrading the App-V client to4.5 CU1.</span></span> <span data-ttu-id="95eb2-141">如需安裝系統必備與 App-v 用戶端的詳細程式，請參閱 <https://go.microsoft.com/fwlink/?LinkId=144106> 。</span><span class="sxs-lookup"><span data-stu-id="95eb2-141">For detailed procedures for installing the prerequisites and the App-V client, see <https://go.microsoft.com/fwlink/?LinkId=144106>.</span></span>

<span data-ttu-id="95eb2-142">完成此操作後，請使用具有提升許可權的 setup.msi 來安裝 App-v 4.5 CU1 用戶端。</span><span class="sxs-lookup"><span data-stu-id="95eb2-142">When this has been completed, install the App-V4.5 CU1 client by using setup.msi with elevated privileges.</span></span> <span data-ttu-id="95eb2-143">此檔案可在 Installers\\Client 資料夾中的 App-V 4.5 CU1 發行媒體中取得。</span><span class="sxs-lookup"><span data-stu-id="95eb2-143">This file is available on the App-V4.5 CU1 release media in the Installers\\Client folder.</span></span>

<span data-ttu-id="95eb2-144">安裝 Microsoft 應用程式錯誤報表時，如果您要安裝或升級至 App-v 4.5 CU1 桌面用戶端，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="95eb2-144">When installing Microsoft Application Error Reporting, use the following command if you are installing or upgrading to the App-V4.5 CU1 Desktop client:</span></span>

    msiexec /i dw20shared.msi APPGUID={FE495DBC-6D42-4698-B61F-86E655E0796D}  allusers=1 reboot=suppress REINSTALL=all REINSTALLMODE=vomus

<span data-ttu-id="95eb2-145">或者，如果您要安裝或升級至 App-v 4.5 CU1 終端服務用戶端，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="95eb2-145">Alternatively, if you are installing or upgrading to the App-V 4.5 CU1 Terminal Services client, use the following command:</span></span>

    msiexec /i dw20shared.msi APPGUID={8A97C241-D92A-47DC-B360-E716C1AAA929} allusers=1 reboot=suppress REINSTALL=all REINSTALLMODE=vomus

<span data-ttu-id="95eb2-146">**記事** APPGUID 參數會參照您安裝或升級的 App-v 用戶端的產品代碼。</span><span class="sxs-lookup"><span data-stu-id="95eb2-146">**Note** The APPGUID parameter references the product code of the App-V client that you install or upgrade to.</span></span> <span data-ttu-id="95eb2-147">每個 setup.msi 的產品代碼都是唯一的。</span><span class="sxs-lookup"><span data-stu-id="95eb2-147">The product code is unique for each setup.msi.</span></span> <span data-ttu-id="95eb2-148">您可以使用 Orca 資料庫編輯器或類似的工具來檢查 Windows 安裝程式檔案，並判斷產品代碼。</span><span class="sxs-lookup"><span data-stu-id="95eb2-148">You can use the Orca database editor or similar tool to examine Windows Installer files and determine the product code.</span></span> <span data-ttu-id="95eb2-149">此步驟是 App-V 4.5 CU1 的所有安裝或升級所需的步驟。</span><span class="sxs-lookup"><span data-stu-id="95eb2-149">This step is required for all installs or upgrades to App-V4.5 CU1.</span></span>

 

### <a href="" id="some-applications-might-fail-to-install-during-the-monitoring-phase-when-sequencing-on-windows-7-beta--"></a><span data-ttu-id="95eb2-150">當您在 Windows7 Beta 上排序時，某些應用程式可能無法在監視階段進行安裝</span><span class="sxs-lookup"><span data-stu-id="95eb2-150">Some applications might fail to install during the monitoring phase when sequencing on Windows7 Beta</span></span>

<span data-ttu-id="95eb2-151">當您在 Windows7 Beta 或 Windows 安裝程式5.0 電腦上進行排序時，某些應用程式可能無法在監視階段進行安裝。</span><span class="sxs-lookup"><span data-stu-id="95eb2-151">When sequencing on Windows7 Beta or on a computer with Windows Installer5.0, some applications might fail to install during the monitoring phase.</span></span>

<span data-ttu-id="95eb2-152">WORKAROUNDYou 必須手動將 [所有人] 群組的 [完全控制] 許可權授與下列登錄機碼：</span><span class="sxs-lookup"><span data-stu-id="95eb2-152">WORKAROUNDYou must manually grant the Everyone group Full Control permissions to the following registry key:</span></span>

    HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\SystemGuard

<span data-ttu-id="95eb2-153">**重要** 您必須使用 [**高級**] 按鈕來設定「包括從該物件的父項繼承的許可權」選項。</span><span class="sxs-lookup"><span data-stu-id="95eb2-153">**Important** You must use the **Advanced** button to set the “Include inheritable permissions from this object’s parent” option.</span></span>

 

### <span data-ttu-id="95eb2-154">在 Windows7 Beta 上排序時無法儲存套件</span><span class="sxs-lookup"><span data-stu-id="95eb2-154">Unable to save packages when sequencing on Windows7 Beta</span></span>

<span data-ttu-id="95eb2-155">當排序 Windows7 Beta 版時，您可能無法儲存已排序的套件，因為發生共用衝突。</span><span class="sxs-lookup"><span data-stu-id="95eb2-155">When sequencing on Windows7 Beta, you might be unable to save your sequenced package because of a sharing violation.</span></span>

<span data-ttu-id="95eb2-156">WORKAROUNDAs 指定于 Microsoft Application Virtualization 4.5 排序指南（請參閱）的 [最佳做法] 區段中 <https://go.microsoft.com/fwlink/?LinkId=144108> ，您必須先關閉並停用下列軟體程式，然後再開始進行排序：</span><span class="sxs-lookup"><span data-stu-id="95eb2-156">WORKAROUNDAs specified in the best practices section of the Microsoft Application Virtualization4.5 Sequencing Guide (see <https://go.microsoft.com/fwlink/?LinkId=144108>), you must shutdown and disable the following software programs before you begin sequencing:</span></span>

-   <span data-ttu-id="95eb2-157">Windows Defender</span><span class="sxs-lookup"><span data-stu-id="95eb2-157">Windows Defender</span></span>

-   <span data-ttu-id="95eb2-158">防毒軟體</span><span class="sxs-lookup"><span data-stu-id="95eb2-158">Antivirus software</span></span>

-   <span data-ttu-id="95eb2-159">磁片磁碟重組軟體</span><span class="sxs-lookup"><span data-stu-id="95eb2-159">Disk defragmentation software</span></span>

-   <span data-ttu-id="95eb2-160">Windows Search</span><span class="sxs-lookup"><span data-stu-id="95eb2-160">Windows Search</span></span>

-   <span data-ttu-id="95eb2-161">任何開啟的 Windows 資源管理器會話</span><span class="sxs-lookup"><span data-stu-id="95eb2-161">Any open Windows Explorer session</span></span>

<span data-ttu-id="95eb2-162">此外，如果您在順序站上執行 Microsoft 更新，以便在套件更新程式期間捕獲更新，您必須在開始排序前，在 VFS 排除中新增「C:\\Windows\\SoftwareDistribution」。</span><span class="sxs-lookup"><span data-stu-id="95eb2-162">In addition, if you have Microsoft Update running on the sequencing station to capture updates during the package update process, you will need to add “C:\\Windows\\SoftwareDistribution” as a VFS exclusion before you start sequencing.</span></span>

### <span data-ttu-id="95eb2-163">改善排序 .NET 架構時的效能</span><span class="sxs-lookup"><span data-stu-id="95eb2-163">Improving performance when sequencing the .NET Framework</span></span>

<span data-ttu-id="95eb2-164">當您將 .NET Framework 排序時，您可能會遇到較低的系統效能，因為 Microsoft .NET Framework NGEN 服務會嘗試將程式集預編譯為背景工作。</span><span class="sxs-lookup"><span data-stu-id="95eb2-164">When sequencing the .NET Framework, you might experience reduced system performance because the Microsoft .NET Framework NGEN service attempts to precompile assemblies as a background task.</span></span>

<span data-ttu-id="95eb2-165">WORKAROUNDWhen 排序 .NET Framework 時，請在完成監視階段後停用 Microsoft .NET Framework NGEN 服務（mscorsvw.exe）。</span><span class="sxs-lookup"><span data-stu-id="95eb2-165">WORKAROUNDWhen sequencing the .NET Framework, disable the Microsoft .NET Framework NGEN service (mscorsvw.exe) after completing the monitoring phase.</span></span> <span data-ttu-id="95eb2-166">您必須使用 Sequencer 中的 [**虛擬服務**] 索引標籤，並將 [啟動類型] 變更為 [停用]。</span><span class="sxs-lookup"><span data-stu-id="95eb2-166">You must use the **Virtual Services** tab in the Sequencer and change the startup type to disabled.</span></span>

### <span data-ttu-id="95eb2-167">Windows7 工作列的互通性問題</span><span class="sxs-lookup"><span data-stu-id="95eb2-167">Interoperability issues with the Windows7 Taskbar</span></span>

<span data-ttu-id="95eb2-168">當您在 Windows7 上執行應用程式虛擬化用戶端時，Windows7 工作列不會將虛擬應用程式的多個實例折迭到單一工作列按鈕。</span><span class="sxs-lookup"><span data-stu-id="95eb2-168">When you run the Application Virtualization Client on Windows7, the Windows7 taskbar does not collapse multiple instances of a virtual application into a single taskbar button.</span></span> <span data-ttu-id="95eb2-169">此外，當您以滑鼠右鍵按一下虛擬應用程式的工作列按鈕時，不會顯示 [跳轉清單]，除非應用程式已釘選到 Windows7 工作列。</span><span class="sxs-lookup"><span data-stu-id="95eb2-169">In addition, jump Lists do not appear when you right-click a taskbar button of a virtual application, unless the application has been pinned to the Windows7 taskbar.</span></span>

### <span data-ttu-id="95eb2-170">當您卸載 Microsoft Application Virtualization 用戶端時，會刪除與執行卸載之使用者相關聯的使用者設定</span><span class="sxs-lookup"><span data-stu-id="95eb2-170">When you uninstall the Microsoft Application Virtualization Client, user settings associated with the user performing the uninstall will be deleted</span></span>

<span data-ttu-id="95eb2-171">當您卸載 Microsoft Application Virtualization 用戶端時，Windows 安裝程式會從目前使用者的設定檔中移除應用程式虛擬化設定。</span><span class="sxs-lookup"><span data-stu-id="95eb2-171">When you uninstall the Microsoft Application Virtualization Client, the Windows Installer will remove Application Virtualization settings from the current user's profile.</span></span> <span data-ttu-id="95eb2-172">如果您的電腦使用漫遊設定檔，請不要使用您的個人網路帳戶來卸載用戶端，因為它會移除您所有電腦上的虛擬應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="95eb2-172">If your computer uses roaming profiles, do not use your personal network account to uninstall the client because it will remove settings for your virtual applications on all of your computers.</span></span>

<span data-ttu-id="95eb2-173">WORKAROUNDYou 應該使用不是用來執行虛擬應用程式的系統管理帳戶來執行 App-v 用戶端卸載。</span><span class="sxs-lookup"><span data-stu-id="95eb2-173">WORKAROUNDYou should perform the App-V Client uninstall with an administrative account that is not used for running virtual applications.</span></span>

### <span data-ttu-id="95eb2-174">在虛擬檔案系統和虛擬機器索引標籤上所做的編輯，必須在執行順序嚮導時儲存</span><span class="sxs-lookup"><span data-stu-id="95eb2-174">Edits made on the virtual file system and virtual registry tabs must be saved while running the Sequencing wizard</span></span>

<span data-ttu-id="95eb2-175">如果您開啟套件以執行升級，或已執行排序嚮導（含新的套件），且您在虛擬檔案系統或虛擬機器索引標籤中變更了套件，則這些變更不會自動儲存。</span><span class="sxs-lookup"><span data-stu-id="95eb2-175">If you open a package to perform an upgrade or have already run the Sequencing wizard with a new package and you make changes to the package in the virtual file system or virtual registry tabs, those changes are not automatically saved.</span></span>

<span data-ttu-id="95eb2-176">在重新執行嚮導前 WORKAROUNDSave 變更，以確保它們反映在嚮導的虛擬環境中。</span><span class="sxs-lookup"><span data-stu-id="95eb2-176">WORKAROUNDSave the changes before re-running the wizard, to ensure that they are reflected inside the wizard’s virtual environment.</span></span>

### <span data-ttu-id="95eb2-177">必須從提升許可權的命令提示字元執行命令列排序器</span><span class="sxs-lookup"><span data-stu-id="95eb2-177">Command-line Sequencer must be run from an elevated command prompt</span></span>

<span data-ttu-id="95eb2-178">當您使用命令列排序器時，它不會提示提升。</span><span class="sxs-lookup"><span data-stu-id="95eb2-178">When you use the command-line Sequencer, it does not prompt for elevation.</span></span>

<span data-ttu-id="95eb2-179">使用提升許可權的命令提示字元 WORKAROUNDRun 命令列排序器。</span><span class="sxs-lookup"><span data-stu-id="95eb2-179">WORKAROUNDRun the command-line Sequencer using an elevated command prompt.</span></span>

### <span data-ttu-id="95eb2-180">分散式環境中的伺服器管理主控台設定</span><span class="sxs-lookup"><span data-stu-id="95eb2-180">Server Management Console configuration in distributed environments</span></span>

<span data-ttu-id="95eb2-181">如果您需要將管理元件安裝在主應用程式虛擬化發行與流式處理伺服器以外的系統上，伺服器安裝支援在不同的伺服器上安裝管理主控台和 Web 服務（在您設定適當的主應用程式虛擬化伺服器時）。</span><span class="sxs-lookup"><span data-stu-id="95eb2-181">If you need to install management components onto systems other than the primary Application Virtualization publishing and streaming server, the server install supports installing our management console and Web service on separate servers from the primary Application Virtualization Server when properly configured.</span></span>

<span data-ttu-id="95eb2-182">若要在多個伺服器上散佈管理元件，必須在安裝 Web 服務的伺服器上啟用 Kerberos 委派。</span><span class="sxs-lookup"><span data-stu-id="95eb2-182">To distribute the management components across multiple servers, Kerberos delegation must be enabled on the server where the Web service is installed.</span></span>

### <span data-ttu-id="95eb2-183">OSD 檔案中的短路徑變數名稱可能會導致錯誤</span><span class="sxs-lookup"><span data-stu-id="95eb2-183">Short path variable names in OSD files can cause errors</span></span>

<span data-ttu-id="95eb2-184">如果您收到錯誤 450478-1F702339-0000010B 在用戶端啟動虛擬應用程式時，「目錄名無效」，可能是 OSD 中的變數設定不正確。</span><span class="sxs-lookup"><span data-stu-id="95eb2-184">If you receive error 450478-1F702339-0000010B “The directory name is invalid” when starting a virtual application on the client, it is possible that the variable in the OSD is set incorrectly.</span></span> <span data-ttu-id="95eb2-185">如果應用程式的安裝程式在排序期間設定短路徑名稱，可能會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="95eb2-185">This can happen if the application’s installer sets a short path name during sequencing.</span></span>

<span data-ttu-id="95eb2-186">WORKAROUNDRemove 位於 OSD 檔案中的任何 CSIDL 變數的尾部波形符。</span><span class="sxs-lookup"><span data-stu-id="95eb2-186">WORKAROUNDRemove the trailing tilde from any CSIDL variable that exists in the OSD file.</span></span>

### <a href="" id="correct-syntax-for-decodepath-parameter-for-command-line-sequencer-"></a><span data-ttu-id="95eb2-187">命令列排序器的 DECODEPATH 參數的正確語法</span><span class="sxs-lookup"><span data-stu-id="95eb2-187">Correct syntax for DECODEPATH parameter for command-line Sequencer</span></span>

<span data-ttu-id="95eb2-188">在命令列排序器中，開啟要升級的套件並將它解碼至 Q 磁片磁碟機根目錄時， *DECODEPATH*參數的語法不應該包含尾部斜線。</span><span class="sxs-lookup"><span data-stu-id="95eb2-188">In the command-line Sequencer, when opening a package for upgrade and decoding it to the root of the Q drive, the syntax for the *DECODEPATH* parameter should not include a trailing slash.</span></span>

<span data-ttu-id="95eb2-189">WORKAROUNDYou 可以使用**Q：** 而不是**Q:\\** （省略尾部 "\ \" 字元）。</span><span class="sxs-lookup"><span data-stu-id="95eb2-189">WORKAROUNDYou can use **Q:** rather than **Q:\\** (omitting the trailing “\\” character).</span></span>

### <a href="" id="when-upgrading-4-2-packages--you-encounter-problems-caused-by-windows-installer-files-in-the-virtual-file-system-"></a><span data-ttu-id="95eb2-190">升級4.2 個套件時，您會遇到 Windows 安裝程式檔案在虛擬檔案系統中造成的問題</span><span class="sxs-lookup"><span data-stu-id="95eb2-190">When upgrading4.2 packages, you encounter problems caused by Windows Installer files in the Virtual File System</span></span>

<span data-ttu-id="95eb2-191">從4.2 升級套件時，您可能會遇到與 Windows 安裝程式系統檔案不相符的問題，這些檔案預設是4.2 中所包含的 windows Installer 系統檔案，以及本機安裝在您順序工作站上的 Windows 安裝程式文件庫。</span><span class="sxs-lookup"><span data-stu-id="95eb2-191">When upgrading a package from4.2, you might experience issues relating to a mismatch of Windows Installer system files that were included by default in4.2 and the Windows Installer libraries locally installed on your Sequencing workstation.</span></span> <span data-ttu-id="95eb2-192">下列檔案位於 CSIDL \ _SYSTEM \\：</span><span class="sxs-lookup"><span data-stu-id="95eb2-192">The following files are located in CSIDL\_SYSTEM\\:</span></span>

<span data-ttu-id="95eb2-193">cabinet.dll</span><span class="sxs-lookup"><span data-stu-id="95eb2-193">cabinet.dll</span></span>

<span data-ttu-id="95eb2-194">msi.dll</span><span class="sxs-lookup"><span data-stu-id="95eb2-194">msi.dll</span></span>

<span data-ttu-id="95eb2-195">msiexec.exe</span><span class="sxs-lookup"><span data-stu-id="95eb2-195">msiexec.exe</span></span>

<span data-ttu-id="95eb2-196">msihnd.dll</span><span class="sxs-lookup"><span data-stu-id="95eb2-196">msihnd.dll</span></span>

<span data-ttu-id="95eb2-197">msimsg.dlll</span><span class="sxs-lookup"><span data-stu-id="95eb2-197">msimsg.dlll</span></span>

<span data-ttu-id="95eb2-198">從套件中 WORKAROUNDDelete 前面的所有檔案。</span><span class="sxs-lookup"><span data-stu-id="95eb2-198">WORKAROUNDDelete all of the preceding files from the package.</span></span> <span data-ttu-id="95eb2-199">刪除 [ **VFS** ] 索引標籤上的對應，以及您解碼路徑中 CSIDL \ _SYSTEM 資料夾中的實際檔案。</span><span class="sxs-lookup"><span data-stu-id="95eb2-199">Delete the mappings on the **VFS** tab as well as the actual files in the CSIDL\_SYSTEM folder in your decode path.</span></span>

### <a href="" id="on-windows-xp--client-install-logging-is-not-enabled-by-default-"></a><span data-ttu-id="95eb2-200">在 WindowsXP 上，預設不會啟用用戶端安裝記錄</span><span class="sxs-lookup"><span data-stu-id="95eb2-200">On WindowsXP, client install logging is not enabled by default</span></span>

<span data-ttu-id="95eb2-201">安裝用戶端時，若要確保捕獲任何安裝錯誤以進行疑難排解，您應該使用命令列來啟用記錄。</span><span class="sxs-lookup"><span data-stu-id="95eb2-201">When installing the client, to ensure that any install errors are captured for troubleshooting purposes, you should enable logging by using the command line.</span></span>

<span data-ttu-id="95eb2-202">WORKAROUNDAdd 參數 */l\ \* vx！ log.txt*到命令列，如下列範例所示：</span><span class="sxs-lookup"><span data-stu-id="95eb2-202">WORKAROUNDAdd the parameter */l\*vx! log.txt* to the command line, as shown in the following example:</span></span>

<span data-ttu-id="95eb2-203">setup.exe/s/v "/qn/l\ \* vx！</span><span class="sxs-lookup"><span data-stu-id="95eb2-203">setup.exe /s /v”/qn /l\*vx!</span></span> <span data-ttu-id="95eb2-204">log.txt "</span><span class="sxs-lookup"><span data-stu-id="95eb2-204">log.txt”</span></span>

<span data-ttu-id="95eb2-205">msiexec.exe/i setup.msi/qn/l\ \* vx！</span><span class="sxs-lookup"><span data-stu-id="95eb2-205">msiexec.exe /i setup.msi /qn /l\*vx!</span></span> <span data-ttu-id="95eb2-206">log.txt</span><span class="sxs-lookup"><span data-stu-id="95eb2-206">log.txt</span></span>

<span data-ttu-id="95eb2-207">或者，您也可以將登錄機碼設定為下列值：</span><span class="sxs-lookup"><span data-stu-id="95eb2-207">Alternatively, you can set the registry key to the following value:</span></span>

<span data-ttu-id="95eb2-208">\ [HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Policies\\Microsoft\\Windows\\Installer\] 「記錄」 = "voicewarmupx！"</span><span class="sxs-lookup"><span data-stu-id="95eb2-208">\[HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Policies\\Microsoft\\Windows\\Installer\] "Logging"="voicewarmupx!"</span></span>

### <span data-ttu-id="95eb2-209">若要讓 Kerberos 驗證正常運作，必須為 IIS 註冊服務主體名稱（Spn）</span><span class="sxs-lookup"><span data-stu-id="95eb2-209">For Kerberos authentication to work, Service Principal Names (SPNs) must be registered for IIS</span></span>

<span data-ttu-id="95eb2-210">針對圖示或 OSD 檔案檢索及套件資料流程使用 IIS 6.0 或7.0 時，必須先將 Spn 登記如下：</span><span class="sxs-lookup"><span data-stu-id="95eb2-210">When using IIS6.0 or7.0 for icon or OSD file retrieval and streaming of packages, for Kerberos authentication to be enabled, the SPNs must be registered as follows:</span></span>

-   <span data-ttu-id="95eb2-211">在 IIS 伺服器上，使用 SETSPN.EXE 資源套件工具] 執行下列命令。</span><span class="sxs-lookup"><span data-stu-id="95eb2-211">On the IIS server, run the following commands by using the SETSPN.EXE Resource Kit tool.</span></span> <span data-ttu-id="95eb2-212">必須使用伺服器完全合格的功能變數名稱（FQDN）。</span><span class="sxs-lookup"><span data-stu-id="95eb2-212">The server fully qualified domain name (FQDN) must be used.</span></span>

    <span data-ttu-id="95eb2-213">Setspn-r SOFTGRID/ &lt; 伺服器 FQDN&gt;</span><span class="sxs-lookup"><span data-stu-id="95eb2-213">Setspn -r SOFTGRID/&lt;Server FQDN&gt;</span></span>

    <span data-ttu-id="95eb2-214">Setspn-r HTTP/ &lt; 伺服器 FQDN&gt;</span><span class="sxs-lookup"><span data-stu-id="95eb2-214">Setspn -r HTTP/&lt;Server FQDN&gt;</span></span>

<span data-ttu-id="95eb2-215">如需詳細資訊，請參閱 <https://go.microsoft.com/fwlink/?LinkId=131407>。</span><span class="sxs-lookup"><span data-stu-id="95eb2-215">For more information, see <https://go.microsoft.com/fwlink/?LinkId=131407>.</span></span>

### <span data-ttu-id="95eb2-216">從 RC 升級時，用戶端記錄上的預設許可權不允許非系統管理員使用者存取記錄以進行疑難排解及支援</span><span class="sxs-lookup"><span data-stu-id="95eb2-216">On upgrade from RC, the default permissions on client logs do not allow for non-admin users to access the logs for troubleshooting and support</span></span>

<span data-ttu-id="95eb2-217">應用程式 VirtualizationRC 用戶端的用戶端記錄上的預設許可權不允許對記錄檔進行非系統管理員存取，而且當用戶端重新開機時，這些記錄許可權的手動變更就會還原。</span><span class="sxs-lookup"><span data-stu-id="95eb2-217">The default permissions on client logs for the Application VirtualizationRC client did not allow for non-admin access to log files, and manual changes to these log permissions were reverted when clients were restarted.</span></span> <span data-ttu-id="95eb2-218">此功能已在 RTM 版本中針對新的用戶端安裝修正，但在從 RC 升級之後，不會重設現有記錄檔上的自訂許可權。</span><span class="sxs-lookup"><span data-stu-id="95eb2-218">This has been corrected in the RTM release for new client installs, but on upgrade from RC, the custom permissions on existing log files are not reset.</span></span> <span data-ttu-id="95eb2-219">不過，當您建立任何新的記錄或重新設定記錄之後，這些檔案將會有新的預設許可權。</span><span class="sxs-lookup"><span data-stu-id="95eb2-219">However, when any new logs are created or after a log reset, the files will have the new default permissions.</span></span>

<span data-ttu-id="95eb2-220">WORKAROUNDAfter [升級]、[重設現有的用戶端記錄] 或 [手動變更其許可權]。</span><span class="sxs-lookup"><span data-stu-id="95eb2-220">WORKAROUNDAfter the upgrade, reset existing client logs or manually change their permissions.</span></span>

### <span data-ttu-id="95eb2-221">.NET 相容性變更</span><span class="sxs-lookup"><span data-stu-id="95eb2-221">.NET compatibility changes</span></span>

<span data-ttu-id="95eb2-222">Microsoft Application Virtualization 累加 Update1 支援在 WindowsXP （SP2 或更新版本）上排序 .NET Framework。</span><span class="sxs-lookup"><span data-stu-id="95eb2-222">Microsoft Application Virtualization Cumulative Update1 supports sequencing the .NET Framework on WindowsXP (SP2 or later).</span></span> <span data-ttu-id="95eb2-223">針對在 SoftGrid 4.2 寫入的 .NET 應用程式的排序常式，可能需要在與 App-v 4.5 排序器搭配使用時進行更新。</span><span class="sxs-lookup"><span data-stu-id="95eb2-223">Sequencing routines for .NET applications that were written for SoftGrid4.2 might need to be updated when used with the App-V4.5 Sequencer.</span></span> <span data-ttu-id="95eb2-224">如需詳細資訊及因應措施，請參閱知識庫文章 <https://go.microsoft.com/fwlink/?LinkId=123412> 。</span><span class="sxs-lookup"><span data-stu-id="95eb2-224">For details and workarounds, please refer to the Knowledge Base article at <https://go.microsoft.com/fwlink/?LinkId=123412>.</span></span>

### <a href="" id="after-client-upgrade-from-app-v-4-2--some-applications-are-not-shown-"></a><span data-ttu-id="95eb2-225">用戶端從 App-v 4.2 升級之後，某些應用程式不會顯示</span><span class="sxs-lookup"><span data-stu-id="95eb2-225">After client upgrade from App-V4.2, some applications are not shown</span></span>

<span data-ttu-id="95eb2-226">在記錄中檢查下列錯誤：「應用程式虛擬化用戶端無法分析 OSD 檔案」。</span><span class="sxs-lookup"><span data-stu-id="95eb2-226">Check for the following error in the log: ”The Application Virtualization Client could not parse the OSD file”.</span></span> <span data-ttu-id="95eb2-227">Microsoft Application Virtualization 4.5 用戶端會篩選出內含包含空白 OS 標記（ &lt; os &gt; &lt; /OS）的 OSD 檔案的應用程式 &gt; 。</span><span class="sxs-lookup"><span data-stu-id="95eb2-227">The Microsoft Application Virtualization4.5 client filters out applications that have an OSD file containing an empty OS tag (&lt;OS&gt;&lt;/OS&gt;).</span></span>

<span data-ttu-id="95eb2-228">WORKAROUNDDelete OSD 檔案中的空白 OS 標籤。</span><span class="sxs-lookup"><span data-stu-id="95eb2-228">WORKAROUNDDelete the empty OS tag from the OSD file.</span></span>

### <span data-ttu-id="95eb2-229">App-v server 在其防火牆中需要免除特定進程的免除</span><span class="sxs-lookup"><span data-stu-id="95eb2-229">The App-V server requires exemptions in its firewall for certain processes</span></span>

<span data-ttu-id="95eb2-230">若要讓伺服器正確地流式處理應用程式，伺服器的核心程式（包括 dispatcher）需要透過防火牆存取。</span><span class="sxs-lookup"><span data-stu-id="95eb2-230">For the server to stream applications correctly, the server's core processes, including the dispatcher, need access through the firewall.</span></span>

<span data-ttu-id="95eb2-231">針對下列進程，在伺服器防火牆中 WORKAROUNDSet [免除]： sghwsvr.exe 和 sghwdsptr.exe。</span><span class="sxs-lookup"><span data-stu-id="95eb2-231">WORKAROUNDSet exemptions in the server's firewall for the following processes: sghwsvr.exe and sghwdsptr.exe.</span></span> <span data-ttu-id="95eb2-232">這適用于 App-v Management Server 和 App-v 流式處理伺服器。</span><span class="sxs-lookup"><span data-stu-id="95eb2-232">This applies to the App-V Management Server and App-V Streaming Server.</span></span>

### <span data-ttu-id="95eb2-233">需要新 Visual Basic 執行時間的排序套件可能失敗</span><span class="sxs-lookup"><span data-stu-id="95eb2-233">Sequencing packages that require new Visual Basic runtimes might fail</span></span>

<span data-ttu-id="95eb2-234">如果您在已安裝舊版 VBruntime 的系統上將使用新版 Visual Basic （VB）執行時間的套件排序，當您嘗試使用您的套件時，可能會看到當機或其他意外的行為。</span><span class="sxs-lookup"><span data-stu-id="95eb2-234">If you sequence a package that uses a newer version of a Visual Basic (VB) runtime on a system where an older version of the VBruntime is installed, you might see a crash or other unexpected behavior when you try to use your package.</span></span> <span data-ttu-id="95eb2-235">例如，如果您嘗試將 Microsoft Money2007 （使用 VBruntime 的版本6.00.9782）用於6.00.9690 版本 VBruntime 的 WindowsXP 系統，您可能會在發票設計工具中看到當您嘗試在另一個有該舊版 WindowsXP 的 VBruntime 系統上執行該工具時發生當機。</span><span class="sxs-lookup"><span data-stu-id="95eb2-235">For example, if you try to sequence Microsoft Money2007, which uses version6.00.9782 of the VBruntime, on a WindowsXP system with version6.00.9690 of the VBruntime, you might see a crash in the Invoice Designer when you try to run it on another WindowsXP system with that older VBruntime.</span></span>

<span data-ttu-id="95eb2-236">WORKAROUNDAfter 在先後順序的電腦上安裝應用程式，但仍在監視時，將正確（較新的） VBruntime 複製到套件中從可執行檔開始的目錄。</span><span class="sxs-lookup"><span data-stu-id="95eb2-236">WORKAROUNDAfter installing the application on the sequencing computer, while still monitoring, copy the correct (newer) VBruntime to the directory in the package from where the executable is started.</span></span> <span data-ttu-id="95eb2-237">這可讓已排序的應用程式在啟動時找到預期版本的 VBruntime。</span><span class="sxs-lookup"><span data-stu-id="95eb2-237">This allows the sequenced application to find the expected version of the VBruntime when it is started.</span></span>

<span data-ttu-id="95eb2-238">**重要** 這個問題已于 Microsoft Application Virtualization 4.5 累加 Update1 中修正。</span><span class="sxs-lookup"><span data-stu-id="95eb2-238">**Important** This issue has been fixed in Microsoft Application Virtualization4.5 Cumulative Update1.</span></span>

 

### <span data-ttu-id="95eb2-239">當伺服器安裝程式在安靜模式下執行時，它不會正確檢查 MSXML6</span><span class="sxs-lookup"><span data-stu-id="95eb2-239">When the server installer is run in silent mode, it does not correctly check for MSXML6</span></span>

<span data-ttu-id="95eb2-240">App-v 管理伺服器會依 MSXML6 而定。</span><span class="sxs-lookup"><span data-stu-id="95eb2-240">The App-V Management Server depends on MSXML6.</span></span> <span data-ttu-id="95eb2-241">不過，如果您在安靜模式下執行安裝程式，例如，在尚未安裝 MSXML6 的系統上使用「msiexec-i setup.msi/qn」命令，安裝程式就不會注意到缺少的相依性，也不會安裝。</span><span class="sxs-lookup"><span data-stu-id="95eb2-241">However, if you run the installer in silent mode—for example, by using the command “msiexec -i setup.msi /qn” on a system where MSXML6 is not already installed—the installer does not notice the missing dependency and installs anyway.</span></span> <span data-ttu-id="95eb2-242">最常見的結果是當用戶端嘗試從 App-v 管理伺服器重新整理髮布資訊時，會看到失敗。</span><span class="sxs-lookup"><span data-stu-id="95eb2-242">The most common result is that when clients attempt to refresh publishing information from the App-V Management Server, they will see failures.</span></span>

<span data-ttu-id="95eb2-243">WORKAROUNDVerify 該 MSXML6 已安裝在系統上，然後嘗試安裝 App-v 管理伺服器。</span><span class="sxs-lookup"><span data-stu-id="95eb2-243">WORKAROUNDVerify that MSXML6 is installed on the system before attempting a silent install of the App-V Management Server.</span></span>

### <span data-ttu-id="95eb2-244">嘗試連線到應用程式虛擬化管理主控台時的錯誤碼000C800</span><span class="sxs-lookup"><span data-stu-id="95eb2-244">Error code 000C800 when attempting to connect to the Application Virtualization Management Console</span></span>

<span data-ttu-id="95eb2-245">應用程式虛擬化管理服務伺服器上不是本機系統管理員的 Application Virtualization 管理員在嘗試連線到應用程式虛擬化管理主控台時，會收到錯誤（錯誤碼：000C800），而 sftmmc 專案會指出對 SftMgmt 的存取權遭到拒絕。</span><span class="sxs-lookup"><span data-stu-id="95eb2-245">An Application Virtualization administrator who is not a local admin on the Application Virtualization Management Service server will receive an error (Error code: 000C800) when attempting to connect to the Application Virtualization Management Console, and the sftmmc.log entry will indicate that access to SftMgmt.udl is denied.</span></span> <span data-ttu-id="95eb2-246">若要成功連線到應用程式虛擬化管理主控台，在應用程式虛擬化管理服務伺服器上不是本機管理員的應用程式虛擬化管理員，必須至少具備 SftMgmt 檔案的讀取和執行存取權。</span><span class="sxs-lookup"><span data-stu-id="95eb2-246">To successfully connect to the Application Virtualization Management Console, an Application Virtualization administrator who is not a local admin on the Application Virtualization Management Service server must have at least read and execute access to the SftMgmt.udl file.</span></span>

<span data-ttu-id="95eb2-247">應用程式虛擬化管理員必須在 [%systemdrive%\\Program Files\\Microsoft System Center] App Virt 管理 Server\\App Virt 管理服務的 SftMgmt 檔案中，提供讀取和執行許可權。</span><span class="sxs-lookup"><span data-stu-id="95eb2-247">The Application Virtualization administrators must be given read and execute permissions to the SftMgmt.UDL file under %systemdrive%\\Program Files\\Microsoft System Center App Virt Management Server\\App Virt Management Service.</span></span>

### <span data-ttu-id="95eb2-248">與 KEEPCURRENTSETTINGS = 1 搭配使用時，會忽略用戶端安裝程式命令列參數</span><span class="sxs-lookup"><span data-stu-id="95eb2-248">Client installer command-line parameters are ignored when used in conjunction with KEEPCURRENTSETTINGS=1</span></span>

<span data-ttu-id="95eb2-249">與 KEEPCURRENTSETTINGS = 1 搭配使用時，系統會忽略下列用戶端安裝程式命令列參數： SWICACHESIZE、MINFREESPACEMB、ALLOWINDEPENDENTFILESTREAMING、APPLICATIONSOURCEROOT、ICONSOURCEROOT、OSDSOURCEROOT、SYSTEMEVENTLOGLEVEL、SWIGLOBALDATA、DOTIMEOUTMINUTES、SWIFSDRIVE、AUTOLOADTARGET、AUTOLOADTRIGGERS、SWIUSERDATA、REQUIRESECURECONNECTION、、、、、、、、</span><span class="sxs-lookup"><span data-stu-id="95eb2-249">When used in conjunction with KEEPCURRENTSETTINGS=1, the following client installer command-line parameters are ignored: SWICACHESIZE, MINFREESPACEMB, ALLOWINDEPENDENTFILESTREAMING, APPLICATIONSOURCEROOT, ICONSOURCEROOT, OSDSOURCEROOT, SYSTEMEVENTLOGLEVEL, SWIGLOBALDATA, DOTIMEOUTMINUTES, SWIFSDRIVE, AUTOLOADTARGET, AUTOLOADTRIGGERS, SWIUSERDATA, and REQUIRESECURECONNECTION.</span></span>

<span data-ttu-id="95eb2-250">WORKAROUNDIf 您有想要保留的設定，請使用 KEEPCURRENTSETTINGS = 1，然後在部署之後設定其他參數。</span><span class="sxs-lookup"><span data-stu-id="95eb2-250">WORKAROUNDIf you have settings you want to retain, use KEEPCURRENTSETTINGS=1 and then set the other parameters after deployment.</span></span> <span data-ttu-id="95eb2-251">App-v ADM 範本可用於設定下列用戶端設定： APPLICATIONSOURCEROOT、ICONSOURCEROOT、OSDSOURCEROOT、AUTOLOADTARGET、AUTOLOADTRIGGERS、DOTIMEOUTMINUTES 和 ALLOWINDEPENDENTFILESTREAMING。</span><span class="sxs-lookup"><span data-stu-id="95eb2-251">The App-V ADM Template can be used to set the following client settings: APPLICATIONSOURCEROOT, ICONSOURCEROOT, OSDSOURCEROOT, AUTOLOADTARGET, AUTOLOADTRIGGERS, DOTIMEOUTMINUTES, and ALLOWINDEPENDENTFILESTREAMING.</span></span> <span data-ttu-id="95eb2-252">您可以在此找到 ADM 範本 <https://go.microsoft.com/fwlink/?LinkId=121835> 。</span><span class="sxs-lookup"><span data-stu-id="95eb2-252">The ADM Template can be found at <https://go.microsoft.com/fwlink/?LinkId=121835>.</span></span>

### <span data-ttu-id="95eb2-253">使用 Symantec Endpoint Protection 初始化虛擬應用程式時發生錯誤</span><span class="sxs-lookup"><span data-stu-id="95eb2-253">Error initializing virtual applications with Symantec Endpoint Protection</span></span>

<span data-ttu-id="95eb2-254">在啟用應用程式和裝置控制功能的情況下使用 Symantec Endpoint Protection 時，虛擬應用程式可能無法啟動，並出現「應用程式無法正確初始化（0xc000007b）」錯誤。</span><span class="sxs-lookup"><span data-stu-id="95eb2-254">When using Symantec Endpoint Protection with the Application and Device Control feature enabled, virtual applications might fail to start, with the error “The application failed to initialize properly (0xc000007b)”.</span></span> <span data-ttu-id="95eb2-255">如需詳細資訊及因應措施，請參閱知識庫文章 <https://go.microsoft.com/fwlink/?LinkId=125851> 。</span><span class="sxs-lookup"><span data-stu-id="95eb2-255">For details and workarounds, please refer to the Knowledge Base article at <https://go.microsoft.com/fwlink/?LinkId=125851>.</span></span>

<span data-ttu-id="95eb2-256">**重要** 這個問題已于 Microsoft Application Virtualization 4.5 累加 Update1 中修正。</span><span class="sxs-lookup"><span data-stu-id="95eb2-256">**Important** This issue has been fixed in Microsoft Application Virtualization4.5 Cumulative Update1.</span></span>

 

## <span data-ttu-id="95eb2-257">版本資訊版權資訊</span><span class="sxs-lookup"><span data-stu-id="95eb2-257">Release Notes Copyright Information</span></span>


<span data-ttu-id="95eb2-258">本檔中的資訊（包括 URL 及其他網際網路網站參考）可能會變更，恕不另行通知，且僅提供提供資訊的資訊。</span><span class="sxs-lookup"><span data-stu-id="95eb2-258">Information in this document, including URL and other Internet Web site references, is subject to change without notice, and is provided for informational purposes only.</span></span> <span data-ttu-id="95eb2-259">本檔的使用或後果的全部風險，由使用者自行提供，而且 Microsoft Corporation 不提供任何明示或暗示的保證。</span><span class="sxs-lookup"><span data-stu-id="95eb2-259">The entire risk of the use or results of the use of this document remains with the user, and Microsoft Corporation makes no warranties, either express or implied.</span></span> <span data-ttu-id="95eb2-260">本文中所述的範例公司、組織、產品、人員和事件純屬虛構。</span><span class="sxs-lookup"><span data-stu-id="95eb2-260">The example companies, organizations, products, people and events depicted herein are fictitious.</span></span> <span data-ttu-id="95eb2-261">決不意指任何真實的公司、組織、產品、人員或事件。</span><span class="sxs-lookup"><span data-stu-id="95eb2-261">No association with any real company, organization, product, person or event is intended or should be inferred.</span></span> <span data-ttu-id="95eb2-262">遵守所有適用的著作權法是使用者的責任。</span><span class="sxs-lookup"><span data-stu-id="95eb2-262">Complying with all applicable copyright laws is the responsibility of the user.</span></span> <span data-ttu-id="95eb2-263">在不限制版權所依據的權利的情況下，本檔的任何部分都不會以任何形式或任何方式（電子、機械、複製、錄製或其他）來複製、儲存或引進至檢索系統，或以任何形式傳送（無論是出於 Microsoft Corporation 的明確書面許可權）。</span><span class="sxs-lookup"><span data-stu-id="95eb2-263">Without limiting the rights under copyright, no part of this document may be reproduced, stored in or introduced into a retrieval system, or transmitted in any form or by any means (electronic, mechanical, photocopying, recording, or otherwise), or for any purpose, without the express written permission of Microsoft Corporation.</span></span>

<span data-ttu-id="95eb2-264">Microsoft 可能具有專利、專利申請、商標、版權或其他智慧財產權，涵蓋本檔中的相關主題。</span><span class="sxs-lookup"><span data-stu-id="95eb2-264">Microsoft may have patents, patent applications, trademarks, copyrights, or other intellectual property rights covering subject matter in this document.</span></span> <span data-ttu-id="95eb2-265">除了 Microsoft 的任何書面授權合約中明確提供之外，提供這份檔並不代表擁有這些專利、商標、版權或其他智慧財產權的授權。</span><span class="sxs-lookup"><span data-stu-id="95eb2-265">Except as expressly provided in any written license agreement from Microsoft, the furnishing of this document does not give you any license to these patents, trademarks, copyrights, or other intellectual property.</span></span>



<span data-ttu-id="95eb2-266">Microsoft、MS-DOS、Windows、WindowsServer、Windows Vista、Active Directory 和 ActiveSync 是 U.S.A. 和/或其他國家或地區的 MicrosoftCorporation 注冊商標或商標。</span><span class="sxs-lookup"><span data-stu-id="95eb2-266">Microsoft, MS-DOS, Windows, WindowsServer, Windows Vista, Active Directory, and ActiveSync are either registered trademarks or trademarks of MicrosoftCorporation in the U.S.A. and/or other countries.</span></span>

<span data-ttu-id="95eb2-267">此處所提及之實際公司和產品的名稱可能是其各自擁有者的商標。</span><span class="sxs-lookup"><span data-stu-id="95eb2-267">The names of actual companies and products mentioned herein may be the trademarks of their respective owners.</span></span>

 

 





