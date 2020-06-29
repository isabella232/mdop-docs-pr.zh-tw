---
title: 部署 App-V 5.1 排序器和用戶端
description: 部署 App-V 5.1 排序器和用戶端
author: dansimp
ms.assetid: 74f32794-4c76-436f-a542-f9e95d89063d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: 3b78059e5005f563bb99d7e6f4b5fe0af2eae8d5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800626"
---
# <span data-ttu-id="e67af-103">部署 App-V 5.1 排序器和用戶端</span><span class="sxs-lookup"><span data-stu-id="e67af-103">Deploying the App-V 5.1 Sequencer and Client</span></span>


<span data-ttu-id="e67af-104">Microsoft Application Virtualization （App-v） 5.1 Sequencer 與用戶端可讓系統管理員虛擬化及執行虛擬化應用程式。</span><span class="sxs-lookup"><span data-stu-id="e67af-104">The Microsoft Application Virtualization (App-V) 5.1 Sequencer and client enable administrators to virtualize and run virtualized applications.</span></span>

## <span data-ttu-id="e67af-105">部署用戶端</span><span class="sxs-lookup"><span data-stu-id="e67af-105">Deploy the client</span></span>


<span data-ttu-id="e67af-106">App-V 5.1 用戶端是在目的電腦上執行虛擬化應用程式的元件。</span><span class="sxs-lookup"><span data-stu-id="e67af-106">The App-V 5.1 client is the component that runs a virtualized application on a target computer.</span></span> <span data-ttu-id="e67af-107">用戶端可讓使用者與圖示互動，並按兩下檔案類型，讓他們可以啟動虛擬化的應用程式。</span><span class="sxs-lookup"><span data-stu-id="e67af-107">The client enables users to interact with icons and to double-click file types, so that they can start a virtualized application.</span></span> <span data-ttu-id="e67af-108">用戶端也可以從管理伺服器取得虛擬應用程式內容。</span><span class="sxs-lookup"><span data-stu-id="e67af-108">The client can also obtain the virtual application content from the management server.</span></span>

[<span data-ttu-id="e67af-109">如何部署 App-V 用戶端</span><span class="sxs-lookup"><span data-stu-id="e67af-109">How to Deploy the App-V Client</span></span>](how-to-deploy-the-app-v-client-51gb18030.md)

[<span data-ttu-id="e67af-110">如何解除安裝 App-V 5.1 Client</span><span class="sxs-lookup"><span data-stu-id="e67af-110">How to Uninstall the App-V 5.1 Client</span></span>](how-to-uninstall-the-app-v-51-client.md)

[<span data-ttu-id="e67af-111">如何在同一部電腦上部署 app-v 4.6 和 App-v 5.1 用戶端</span><span class="sxs-lookup"><span data-stu-id="e67af-111">How to Deploy the App-V 4.6 and the App-V 5.1 Client on the Same Computer</span></span>](how-to-deploy-the-app-v-46-and-the-app-v--51-client-on-the-same-computer.md)

## <span data-ttu-id="e67af-112">用戶端配置設定</span><span class="sxs-lookup"><span data-stu-id="e67af-112">Client Configuration Settings</span></span>


<span data-ttu-id="e67af-113">App-v 5.1 用戶端將其設定儲存在註冊表中。</span><span class="sxs-lookup"><span data-stu-id="e67af-113">The App-V 5.1 client stores its configuration in the registry.</span></span> <span data-ttu-id="e67af-114">如果您瞭解註冊表中的資料格式，就可以收集一些有關用戶端的有用資訊。</span><span class="sxs-lookup"><span data-stu-id="e67af-114">You can gather some useful information about the client if you understand the format of data in the registry.</span></span> <span data-ttu-id="e67af-115">您也可以透過變更登錄專案來設定多個用戶端動作。</span><span class="sxs-lookup"><span data-stu-id="e67af-115">You can also configure many client actions by changing registry entries.</span></span>

[<span data-ttu-id="e67af-116">關於 Client 組態設定</span><span class="sxs-lookup"><span data-stu-id="e67af-116">About Client Configuration Settings</span></span>](about-client-configuration-settings51.md)

## <span data-ttu-id="e67af-117">使用 ADMX 範本和群組原則設定用戶端</span><span class="sxs-lookup"><span data-stu-id="e67af-117">Configure the client by using the ADMX template and Group Policy</span></span>


<span data-ttu-id="e67af-118">您可以使用 Microsoft ADMX 範本來設定 App-V 5.1 用戶端和遠端桌面服務用戶端的用戶端設定。</span><span class="sxs-lookup"><span data-stu-id="e67af-118">You can use the Microsoft ADMX template to configure the client settings for the App-V 5.1 client and the Remote Desktop Services client.</span></span> <span data-ttu-id="e67af-119">ADMX 範本利用現有的群組原則基礎結構管理常見的用戶端設定，其中包含 App-v 5.1 用戶端設定的設定。</span><span class="sxs-lookup"><span data-stu-id="e67af-119">The ADMX template manages common client configurations by using an existing Group Policy infrastructure and it includes settings for the App-V 5.1 client configuration.</span></span>

<span data-ttu-id="e67af-120">**重要** 您可以從 Microsoft 下載中心取得 App-v 5.1 ADMX 範本。</span><span class="sxs-lookup"><span data-stu-id="e67af-120">**Important** You can obtain the App-V 5.1 ADMX template from the Microsoft Download Center.</span></span>

 

<span data-ttu-id="e67af-121">下載並安裝 ADMX 範本之後，請在您將用來管理群組原則的電腦上執行下列步驟。</span><span class="sxs-lookup"><span data-stu-id="e67af-121">After you download and install the ADMX template, perform the following steps on the computer that you will use to manage Group Policy.</span></span> <span data-ttu-id="e67af-122">這通常是網網域控制站。</span><span class="sxs-lookup"><span data-stu-id="e67af-122">This is typically the Domain Controller.</span></span>

1.  <span data-ttu-id="e67af-123">將**admx**檔案儲存到下列目錄： **Windows \\ PolicyDefinitions**</span><span class="sxs-lookup"><span data-stu-id="e67af-123">Save the **.admx** file to the following directory: **Windows \\ PolicyDefinitions**</span></span>

2.  <span data-ttu-id="e67af-124">將**adml**檔案儲存到下列目錄： **Windows \\ PolicyDefinitions \\ &lt; &gt; 語言目錄**</span><span class="sxs-lookup"><span data-stu-id="e67af-124">Save the **.adml** file to the following directory: **Windows \\ PolicyDefinitions \\ &lt;Language Directory&gt;**</span></span>

<span data-ttu-id="e67af-125">完成上述步驟之後，您可以使用**群組原則管理**主控台來管理 app-v 5.1 用戶端配置設定。</span><span class="sxs-lookup"><span data-stu-id="e67af-125">After you have completed the preceding steps, you can manage the App-V 5.1 client configuration settings with the **Group Policy Management** console.</span></span>

<span data-ttu-id="e67af-126">App-v 5.1 用戶端也會將其設定儲存在註冊表中。</span><span class="sxs-lookup"><span data-stu-id="e67af-126">The App-V 5.1 client also stores its configuration in the registry.</span></span> <span data-ttu-id="e67af-127">如果您瞭解註冊表中的資料格式，就可以收集一些有關用戶端的有用資訊。</span><span class="sxs-lookup"><span data-stu-id="e67af-127">You can gather some useful information about the client if you understand the format of the data in the registry.</span></span> <span data-ttu-id="e67af-128">您也可以透過變更登錄專案來設定多個用戶端動作。</span><span class="sxs-lookup"><span data-stu-id="e67af-128">You can also configure many client actions by changing registry entries.</span></span>

[<span data-ttu-id="e67af-129">如何使用 ADMX 範本和群組原則來修改 App-V 5.1 用戶端組態</span><span class="sxs-lookup"><span data-stu-id="e67af-129">How to Modify App-V 5.1 Client Configuration Using the ADMX Template and Group Policy</span></span>](how-to-modify-app-v-51-client-configuration-using-the-admx-template-and-group-policy.md)

## <span data-ttu-id="e67af-130">使用 [共用內容存放區模式] 部署用戶端</span><span class="sxs-lookup"><span data-stu-id="e67af-130">Deploy the client by using the Shared Content Store mode</span></span>


<span data-ttu-id="e67af-131">App-V 5.1 共用內容存儲區（SCS）模式可讓 SCS App-V 5.1 用戶端執行虛擬化的應用程式，而不會在本機儲存任何相關聯的套件資料。</span><span class="sxs-lookup"><span data-stu-id="e67af-131">The App-V 5.1 Shared Content Store (SCS) mode enables the SCS App-V 5.1 clients to run virtualized applications without saving any of the associated package data locally.</span></span> <span data-ttu-id="e67af-132">所有必要的虛擬化套件資料都是透過網路傳輸;因此，您應該只在具有快速連接的環境中使用 SCS 模式。</span><span class="sxs-lookup"><span data-stu-id="e67af-132">All required virtualized package data is transmitted across the network; therefore, you should only use the SCS mode in environments with a fast connection.</span></span> <span data-ttu-id="e67af-133">[SCS] 模式支援遠端桌面服務（RDS）和標準版的 App-v 5.1 用戶端。</span><span class="sxs-lookup"><span data-stu-id="e67af-133">Both the Remote Desktop Services (RDS) and the standard version of the App-V 5.1 client are supported with SCS mode.</span></span>

<span data-ttu-id="e67af-134">**重要** 如果 App-v 5.1 用戶端設定為在 SCS 模式中執行，則必須提供 App-v 5.1 套件從哪個位置進行流式處理，否則虛擬化套件將會失敗。</span><span class="sxs-lookup"><span data-stu-id="e67af-134">**Important** If the App-V 5.1 client is configured to run in the SCS mode, the location where the App-V 5.1 packages are streamed from must be available, otherwise, the virtualized package will fail.</span></span> <span data-ttu-id="e67af-135">此外，我們不建議您將虛擬化的應用程式部署到透過網際網路的 SCS 模式中執行 App-V 5.1 用戶端的電腦上。</span><span class="sxs-lookup"><span data-stu-id="e67af-135">Additionally, we do not recommend deployment of virtualized applications to computers that run the App-V 5.1 client in the SCS mode across the internet.</span></span>

 

<span data-ttu-id="e67af-136">此外，SCS 不是包含虛擬化套件的實體位置。</span><span class="sxs-lookup"><span data-stu-id="e67af-136">Additionally, the SCS is not a physical location that contains virtualized packages.</span></span> <span data-ttu-id="e67af-137">它是一種允許 App-v 5.1 用戶端在網路上傳輸所需虛擬化套件資料的模式。</span><span class="sxs-lookup"><span data-stu-id="e67af-137">It is a mode that allows the App-V 5.1 client to stream the required virtualized package data across the network.</span></span>

<span data-ttu-id="e67af-138">SCS 模式在下列案例中很有用：</span><span class="sxs-lookup"><span data-stu-id="e67af-138">The SCS mode is helpful in the following scenarios:</span></span>

-   <span data-ttu-id="e67af-139">虛擬桌面基礎結構（VDI）部署</span><span class="sxs-lookup"><span data-stu-id="e67af-139">Virtual desktop infrastructure (VDI) deployments</span></span>

-   <span data-ttu-id="e67af-140">遠端桌面服務（RDS）部署</span><span class="sxs-lookup"><span data-stu-id="e67af-140">Remote desktop services (RDS) deployments</span></span>

<span data-ttu-id="e67af-141">若要在您的環境中使用 SCS，您必須啟用 App-v 5.1 用戶端，才能在 SCS 模式中執行。</span><span class="sxs-lookup"><span data-stu-id="e67af-141">To use SCS in your environment, you must enable the App-V 5.1 client to run in SCS mode.</span></span> <span data-ttu-id="e67af-142">安裝期間應指定此設定。</span><span class="sxs-lookup"><span data-stu-id="e67af-142">This setting should be specified during installation.</span></span> <span data-ttu-id="e67af-143">根據預設，用戶端未設定為使用 SCS 模式。</span><span class="sxs-lookup"><span data-stu-id="e67af-143">By default, the client is not configured to use SCS mode.</span></span> <span data-ttu-id="e67af-144">如果您打算使用 SCS，您應該使用建議的程式來安裝用戶端。</span><span class="sxs-lookup"><span data-stu-id="e67af-144">You should install the client by using the suggested procedure if you plan to use SCS.</span></span> <span data-ttu-id="e67af-145">不過，您可以在執行 App-v 5.1 用戶端的電腦上輸入下列 PowerShell 命令，來設定現有的 App-v 5.1 用戶端在 SCS 模式中執行：</span><span class="sxs-lookup"><span data-stu-id="e67af-145">However, you can configure an existing App-V 5.1 client to run in SCS mode by entering the following PowerShell command on the computer that runs the App-V 5.1 client:</span></span>

**<span data-ttu-id="e67af-146">AppvClientConfiguration-SharedContentStoreMode 1</span><span class="sxs-lookup"><span data-stu-id="e67af-146">set-AppvClientConfiguration -SharedContentStoreMode 1</span></span>**

<span data-ttu-id="e67af-147">在 SCS 模式中，可能會有系統管理員預先載入一些在執行 App-v 5.1 用戶端的電腦上的虛擬應用程式。</span><span class="sxs-lookup"><span data-stu-id="e67af-147">There might be cases when the administrator pre-loads some virtual applications on the computer that runs the App-V 5.1 client in SCS mode.</span></span> <span data-ttu-id="e67af-148">您可以使用 PowerShell 命令來新增、發佈及裝載套件來完成此工作。</span><span class="sxs-lookup"><span data-stu-id="e67af-148">This can be accomplished with PowerShell commands to add, publish, and mount the package.</span></span> <span data-ttu-id="e67af-149">例如，如果您已在所有電腦上預載入套件，系統管理員可以使用 PowerShell 命令來新增、發佈及裝載套件。</span><span class="sxs-lookup"><span data-stu-id="e67af-149">For example, if a package is pre-loaded on all computers, the administrator could add, publish, and mount the package by using PowerShell commands.</span></span> <span data-ttu-id="e67af-150">套件不會在網路上傳輸，因為它會在本機儲存。</span><span class="sxs-lookup"><span data-stu-id="e67af-150">The package would not stream across the network because it would be locally stored.</span></span>

[<span data-ttu-id="e67af-151">如何安裝 App-V 5.1 用戶端以使用共用內容存放區模式</span><span class="sxs-lookup"><span data-stu-id="e67af-151">How to Install the App-V 5.1 Client for Shared Content Store Mode</span></span>](how-to-install-the-app-v-51-client-for-shared-content-store-mode.md)

## <span data-ttu-id="e67af-152">部署排序器</span><span class="sxs-lookup"><span data-stu-id="e67af-152">Deploy the Sequencer</span></span>


<span data-ttu-id="e67af-153">Sequencer 是一個工具，可用於將標準應用程式轉換成虛擬套件，以便部署到執行 App-v 5.1 用戶端的電腦。</span><span class="sxs-lookup"><span data-stu-id="e67af-153">The Sequencer is a tool that is used to convert standard applications into virtual packages for deployment to computers that run the App-V 5.1 client.</span></span> <span data-ttu-id="e67af-154">排序器可提供簡單且可預測的轉換程式，並將對預先排序工作流程所做的變更降至最低。</span><span class="sxs-lookup"><span data-stu-id="e67af-154">The Sequencer helps provide a simple and predictable conversion process with minimal changes to prior sequencing workflows.</span></span> <span data-ttu-id="e67af-155">此外，排序器還能讓使用者更輕鬆地設定應用程式，以啟用虛擬化應用程式的連線。</span><span class="sxs-lookup"><span data-stu-id="e67af-155">In addition, the Sequencer allows users to more easily configure applications to enable connections of virtualized applications.</span></span>

<span data-ttu-id="e67af-156">如需 App-v 5.1 Sequencer 中的變更清單，請參閱[關於 app-v 5.1](about-app-v-51.md)。</span><span class="sxs-lookup"><span data-stu-id="e67af-156">For a list of changes in the App-V 5.1 Sequencer, see [About App-V 5.1](about-app-v-51.md).</span></span>

[<span data-ttu-id="e67af-157">如何安裝 Sequencer</span><span class="sxs-lookup"><span data-stu-id="e67af-157">How to Install the Sequencer</span></span>](how-to-install-the-sequencer-51beta-gb18030.md)

## <a href="" id="---------app-v-5-1-client-and-sequencer-logs"></a> <span data-ttu-id="e67af-158">App-v 5.1 用戶端和 Sequencer 記錄</span><span class="sxs-lookup"><span data-stu-id="e67af-158">App-V 5.1 Client and Sequencer logs</span></span>


<span data-ttu-id="e67af-159">您可以使用 App-v 5.1 Sequencer 記錄資訊，協助您使用 App-v 5.1 來疑難排解排序程式安裝和操作事件。</span><span class="sxs-lookup"><span data-stu-id="e67af-159">You can use the App-V 5.1 Sequencer log information to help troubleshoot the Sequencer installation and operational events while using App-V 5.1.</span></span> <span data-ttu-id="e67af-160">使用**事件檢視器**，可以檢查與 Sequencer 相關的記錄資訊。</span><span class="sxs-lookup"><span data-stu-id="e67af-160">The Sequencer-related log information can be reviewed with the **Event Viewer**.</span></span> <span data-ttu-id="e67af-161">下列行顯示與 Sequencer 相關事件的特定路徑：</span><span class="sxs-lookup"><span data-stu-id="e67af-161">The following line displays the specific path for Sequencer-related events:</span></span>

<span data-ttu-id="e67af-162">**事件檢視器 \\ 應用程式和服務記錄 \\ Microsoft \\ App V**。使用**AppV \ _Sequencer**預置與 Sequencer 相關的事件。</span><span class="sxs-lookup"><span data-stu-id="e67af-162">**Event Viewer \\ Applications and Services Logs \\ Microsoft \\ App V**. Sequencer-related events are prepended with **AppV\_Sequencer**.</span></span> <span data-ttu-id="e67af-163">用戶端相關事件會預先加上**AppV \ _Client**。</span><span class="sxs-lookup"><span data-stu-id="e67af-163">Client-related events are prepended with **AppV\_Client**.</span></span>

## <span data-ttu-id="e67af-164">部署排序器和用戶端的其他資源</span><span class="sxs-lookup"><span data-stu-id="e67af-164">Other resources for deploying the Sequencer and client</span></span>


[<span data-ttu-id="e67af-165">部署 App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="e67af-165">Deploying App-V 5.1</span></span>](deploying-app-v-51.md)

[<span data-ttu-id="e67af-166">為 App-V 5.1 進行規劃</span><span class="sxs-lookup"><span data-stu-id="e67af-166">Planning for App-V 5.1</span></span>](planning-for-app-v-51.md)






 

 





