---
title: 設定 UE-V 2. x 的公司設定中心
description: 設定 UE-V 2. x 的公司設定中心
author: dansimp
ms.assetid: 48fadb0a-c0dc-4287-9474-f94ce1417003
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 0226b3c156a6d6ca39b0214de8acf0c5990db349
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809867"
---
# <span data-ttu-id="9212c-103">設定 UE-V 2. x 的公司設定中心</span><span class="sxs-lookup"><span data-stu-id="9212c-103">Configuring the Company Settings Center for UE-V 2.x</span></span>


<span data-ttu-id="9212c-104">Microsoft 使用者體驗虛擬化（UE-V）2.0、2.1 和 2.1 SP1 包含新的應用程式，即 [公司設定中心]，可協助使用者管理同步處理的設定。</span><span class="sxs-lookup"><span data-stu-id="9212c-104">Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, and 2.1 SP1 include a new application, the Company Settings Center, which helps users manage settings to synchronize.</span></span> <span data-ttu-id="9212c-105">[公司設定中心] 是使用 UE-V Agent 來安裝的。</span><span class="sxs-lookup"><span data-stu-id="9212c-105">The Company Settings Center is installed by using the UE-V Agent.</span></span> <span data-ttu-id="9212c-106">使用者存取 [控制台] 中的 [公司設定中心]、[**開始**] 功能表或 [**開始**] 畫面，以及透過 ue-v 通知區域圖示。</span><span class="sxs-lookup"><span data-stu-id="9212c-106">Users access the Company Settings Center in Control Panel, in the **Start** menu or on the **Start** screen, and via the UE-V notification area icon.</span></span> <span data-ttu-id="9212c-107">[公司設定中心] 會顯示已同步處理的設定，並可協助使用者查看 UE-V 的同步處理狀態。</span><span class="sxs-lookup"><span data-stu-id="9212c-107">Company Settings Center displays which settings are synchronized and helps users see the synchronization status of UE-V.</span></span> <span data-ttu-id="9212c-108">使用者可以使用公司設定中心來選取哪些應用程式或 Windows 功能在電腦之間同步處理其設定。</span><span class="sxs-lookup"><span data-stu-id="9212c-108">Users can use the Company Settings Center to select which applications or Windows features synchronize their settings between computers.</span></span> <span data-ttu-id="9212c-109">他們也可以按一下 [**立即同步**處理] 按鈕，立即同步處理所有設定。</span><span class="sxs-lookup"><span data-stu-id="9212c-109">They can also click the **Sync Now** button to synchronize all settings immediately.</span></span> <span data-ttu-id="9212c-110">系統管理員也可以在 [公司設定中心] 中包含支援連結。</span><span class="sxs-lookup"><span data-stu-id="9212c-110">The administrator can also include a link for support in the Company Settings Center.</span></span>

## <span data-ttu-id="9212c-111">關於公司設定中心</span><span class="sxs-lookup"><span data-stu-id="9212c-111">About the Company Settings Center</span></span>


<span data-ttu-id="9212c-112">[公司設定中心] 桌面應用程式會為使用者提供 UE-V 設定同步處理的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="9212c-112">The Company Settings Center desktop application provides users with information about UE-V settings synchronization.</span></span> <span data-ttu-id="9212c-113">[公司設定中心] 有幾種不同的方式可供存取：</span><span class="sxs-lookup"><span data-stu-id="9212c-113">The Company Settings Center is accessible in several different ways:</span></span>

-   <span data-ttu-id="9212c-114">通知區域圖示：啟用**工作列圖示**群組原則設定或 Windows PowerShell 設定之後，就會在通知區域中出現 ue-v 圖示。</span><span class="sxs-lookup"><span data-stu-id="9212c-114">Notification area icon – With the **Tray Icon** Group Policy setting or Windows PowerShell configuration enabled, the UE-V icon appears in the notification area.</span></span> <span data-ttu-id="9212c-115">按一下 UE-V 圖示以開啟 [公司設定中心]。</span><span class="sxs-lookup"><span data-stu-id="9212c-115">Click the UE-V icon to open the Company Settings Center.</span></span>

    <span data-ttu-id="9212c-116">**記事** 您可以使用下列設定停用通知區域圖示：</span><span class="sxs-lookup"><span data-stu-id="9212c-116">**Note** The notification area icon can be disabled by using the following settings:</span></span>

    -   <span data-ttu-id="9212c-117">群組原則設定：</span><span class="sxs-lookup"><span data-stu-id="9212c-117">Group Policy setting:</span></span> `Policy Tray Icon`

    -   <span data-ttu-id="9212c-118">Windows PowerShell Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="9212c-118">Windows PowerShell cmdlet:</span></span> `TrayIconEnabled`

    -   <span data-ttu-id="9212c-119">SystemCenter2012 ConfigurationManager 的 UE-V Configuration Pack 中的 [設定] 專案：</span><span class="sxs-lookup"><span data-stu-id="9212c-119">Configuration item in the UE-V Configuration Pack for SystemCenter2012 ConfigurationManager:</span></span> `Tray icon enabled`

     

-   <span data-ttu-id="9212c-120">[控制台] 應用程式-在 [控制台] 中，流覽至 [**外觀及個人**化]，然後按一下 [**公司設定中心**]。</span><span class="sxs-lookup"><span data-stu-id="9212c-120">Control Panel application – In Control Panel, browse to **Appearance and Personalization**, and then click **Company Settings Center**.</span></span>

-   <span data-ttu-id="9212c-121">第一次使用通知–除非停用，否則 UE-V Agent 會提醒使用者，在電腦第一次執行 UE-V agent 時，這些設定會立即同步處理。</span><span class="sxs-lookup"><span data-stu-id="9212c-121">First use notification – Unless disabled, the UE-V Agent alerts the user that settings are now synchronized when the UE-V agent runs for the first time on a computer.</span></span> <span data-ttu-id="9212c-122">按一下 [通知] 對話方塊以開啟 [公司設定中心]。</span><span class="sxs-lookup"><span data-stu-id="9212c-122">Click the notification dialog box to open the Company Settings Center.</span></span>

-   <span data-ttu-id="9212c-123">[**開始**] 畫面或 [**開始**] 功能表包含 [公司設定中心] 的連結。</span><span class="sxs-lookup"><span data-stu-id="9212c-123">The **Start** screen or **Start** menu includes a link to the Company Settings Center.</span></span> <span data-ttu-id="9212c-124">[在公司設定中心搜尋] 會找到應用程式。</span><span class="sxs-lookup"><span data-stu-id="9212c-124">A search for Company Settings Center finds the application.</span></span>

## <span data-ttu-id="9212c-125">在公司設定中心設定支援連結</span><span class="sxs-lookup"><span data-stu-id="9212c-125">Configuring the support link in the Company Settings Center</span></span>


<span data-ttu-id="9212c-126">[公司設定中心] 可以加入超連結，讓使用者按一下即可取得與 UE-V 設定同步處理問題的支援。</span><span class="sxs-lookup"><span data-stu-id="9212c-126">The Company Settings Center can include a hyperlink that users can click to get support with UE-V settings synchronization problems.</span></span> <span data-ttu-id="9212c-127">此連結可以開啟任何有效的 URL 通訊協定，例如網頁的 HTTP://或電子郵件的 mailto://。</span><span class="sxs-lookup"><span data-stu-id="9212c-127">This link can open any valid URL protocol, such as http:// for a webpage or mailto:// for an email.</span></span> <span data-ttu-id="9212c-128">支援連結可以使用 [群組原則]、[Windows PowerShell] 或 [System Center 2012 Configuration Manager UE-V Configuration Pack] 進行設定。</span><span class="sxs-lookup"><span data-stu-id="9212c-128">The support link can be configured by using Group Policy, Windows PowerShell, or the System Center 2012 Configuration Manager UE-V Configuration Pack.</span></span>

**<span data-ttu-id="9212c-129">如何設定公司設定中心支援連結</span><span class="sxs-lookup"><span data-stu-id="9212c-129">How to configure the Company Settings Center support link</span></span>**

1.  <span data-ttu-id="9212c-130">開啟您慣用的管理工具：</span><span class="sxs-lookup"><span data-stu-id="9212c-130">Open your preferred management tool:</span></span>

    -   <span data-ttu-id="9212c-131">**群組原則**-如果您尚未這麼做，請從[MDOP 管理範本](https://go.microsoft.com/fwlink/p/?LinkId=393941)下載 ue-v 2 的 ADMX 範本。</span><span class="sxs-lookup"><span data-stu-id="9212c-131">**Group Policy** - If you have not already done so, download the ADMX template for UE-V 2 from [MDOP Administrative Templates](https://go.microsoft.com/fwlink/p/?LinkId=393941).</span></span>

    -   <span data-ttu-id="9212c-132">**Windows powershell** -在已安裝 ue-v agent 的電腦上，開啟**Windows PowerShell**。</span><span class="sxs-lookup"><span data-stu-id="9212c-132">**Windows PowerShell** – On a computer with the UE-V Agent installed, open **Windows PowerShell**.</span></span> <span data-ttu-id="9212c-133">如需使用 Windows PowerShell 管理 UE-V 的詳細資訊，請參閱[使用 Windows powershell 和 WMI 管理 ue-v 2.](administering-ue-v-2x-with-windows-powershell-and-wmi-both-uevv2.md)</span><span class="sxs-lookup"><span data-stu-id="9212c-133">For more information about administering UE-V by using Windows PowerShell, see [Administering UE-V 2.x with Windows PowerShell and WMI](administering-ue-v-2x-with-windows-powershell-and-wmi-both-uevv2.md).</span></span>

    -   <span data-ttu-id="9212c-134">**適用于 Microsoft 使用者體驗虛擬化（ue-v）的 System Center 2012 Configuration pack** -匯入 Ue-v 設定套件，然後遵循配置套件檔來建立設定項目。</span><span class="sxs-lookup"><span data-stu-id="9212c-134">**System Center 2012 Configuration Pack for Microsoft User Experience Virtualization (UE-V)** – Import the UE-V Configuration Pack and follow the Configuration Pack documentation to create configuration items.</span></span> <span data-ttu-id="9212c-135">如需 UE-V Configuration Pack 的詳細資訊，請參閱[使用 System Center Configuration Manager 2012 設定 ue-v 2. x](configuring-ue-v-2x-with-system-center-configuration-manager-2012-both-uevv2.md)。</span><span class="sxs-lookup"><span data-stu-id="9212c-135">For more information about the UE-V Configuration Pack, see [Configuring UE-V 2.x with System Center Configuration Manager 2012](configuring-ue-v-2x-with-system-center-configuration-manager-2012-both-uevv2.md).</span></span>

2.  <span data-ttu-id="9212c-136">編輯下列原則的設定：</span><span class="sxs-lookup"><span data-stu-id="9212c-136">Edit the settings for the following policies:</span></span>

    -   <span data-ttu-id="9212c-137">**連絡人連結文字**-此設定會指定公司設定中心中的 [連絡人 IT URL] 超連結的文字。</span><span class="sxs-lookup"><span data-stu-id="9212c-137">**Contact IT Link Text** - This setting specifies the text of the Contact IT URL hyperlink in the Company Settings Center.</span></span> <span data-ttu-id="9212c-138">如果您啟用這項設定，[公司設定中心] 會在連結中顯示特定的文字給連絡人的 URL。</span><span class="sxs-lookup"><span data-stu-id="9212c-138">If you enable this setting, the Company Settings Center displays the specified text in the link to the Contact IT URL.</span></span>

        -   <span data-ttu-id="9212c-139">群組原則設定：</span><span class="sxs-lookup"><span data-stu-id="9212c-139">Group Policy settings:</span></span> `Contact IT Link Text`

        -   <span data-ttu-id="9212c-140">Windows PowerShell Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="9212c-140">Windows PowerShell cmdlet:</span></span> `ContactITDescription`

        -   <span data-ttu-id="9212c-141">配置包設定專案：</span><span class="sxs-lookup"><span data-stu-id="9212c-141">Configuration Pack configuration item:</span></span> `IT contact descriptive text`

    -   <span data-ttu-id="9212c-142">[聯絡人] **url** -此設定會以有效的 URL 通訊協定（例如網頁的 HTTP://或電子郵件的 mailto://），指定 [公司設定] 中的 [連絡人] 連結的 URL。</span><span class="sxs-lookup"><span data-stu-id="9212c-142">**Contact IT URL** - This setting specifies the URL for the Contact IT link in the Company Settings Center in a valid URL protocol, such as http:// for a webpage or mailto:// for an email.</span></span>

        -   <span data-ttu-id="9212c-143">群組原則設定：</span><span class="sxs-lookup"><span data-stu-id="9212c-143">Group Policy settings:</span></span> `Contact IT URL`

        -   <span data-ttu-id="9212c-144">Windows PowerShell Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="9212c-144">Windows PowerShell cmdlet:</span></span> `ContactITUrl`

        -   <span data-ttu-id="9212c-145">配置包設定專案：</span><span class="sxs-lookup"><span data-stu-id="9212c-145">Configuration Pack configuration item:</span></span> `IT contact URL`

3.  <span data-ttu-id="9212c-146">使用管理工具將設定部署至使用者的電腦。</span><span class="sxs-lookup"><span data-stu-id="9212c-146">Deploy settings to users’ computers by using the management tool.</span></span>






 

 





