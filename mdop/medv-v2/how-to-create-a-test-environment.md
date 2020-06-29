---
title: 如何建立測試環境
description: 如何建立測試環境
author: dansimp
ms.assetid: a0db2299-16f3-4516-8769-7d55ca4a1e98
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ee2ab131f6003b56cce7a60ffea1cd00b067fae3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812266"
---
# <span data-ttu-id="2398a-103">如何建立測試環境</span><span class="sxs-lookup"><span data-stu-id="2398a-103">How to Create a Test Environment</span></span>


<span data-ttu-id="2398a-104">以下是一些可協助您建立測試環境的步驟與指示，您可以用來在整個企業部署 MED-V 工作區套件之前先在本機進行測試。</span><span class="sxs-lookup"><span data-stu-id="2398a-104">The following are some steps and instructions to help you create a test environment that you can use to test your MED-V workspace package locally before deploying it throughout your enterprise.</span></span> <span data-ttu-id="2398a-105">本節提供如何手動或使用電子軟體發佈系統來建立測試環境的指導方針。</span><span class="sxs-lookup"><span data-stu-id="2398a-105">This section provides guidance about how to create a test environment, either manually or by using an electronic software distribution system.</span></span>

**<span data-ttu-id="2398a-106">使用 ESD 建立測試環境</span><span class="sxs-lookup"><span data-stu-id="2398a-106">To create a test environment by using an ESD</span></span>**

1.  <span data-ttu-id="2398a-107">使用貴公司在整個企業中部署軟體的方法，將下列必要元件部署到測試電腦。</span><span class="sxs-lookup"><span data-stu-id="2398a-107">Use your company’s method of deploying software throughout the enterprise to deploy the following necessary components to a test computer.</span></span> <span data-ttu-id="2398a-108">依下列順序安裝它們：</span><span class="sxs-lookup"><span data-stu-id="2398a-108">Install them in the following order:</span></span>

    -   <span data-ttu-id="2398a-109">**Windows 虛擬電腦**–如果尚未安裝。</span><span class="sxs-lookup"><span data-stu-id="2398a-109">**Windows Virtual PC** – if not already installed.</span></span> <span data-ttu-id="2398a-110">如需詳細資訊，請參閱[設定安裝必備元件](configure-installation-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="2398a-110">For more information, see [Configure Installation Prerequisites](configure-installation-prerequisites.md).</span></span>

    -   <span data-ttu-id="2398a-111">**Windows 虛擬電腦新增和更新**–如果尚未安裝。</span><span class="sxs-lookup"><span data-stu-id="2398a-111">**Windows Virtual PC Additions and Updates**– if not already installed.</span></span> <span data-ttu-id="2398a-112">如需詳細資訊，請參閱[設定安裝必備元件](configure-installation-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="2398a-112">For more information, see [Configure Installation Prerequisites](configure-installation-prerequisites.md).</span></span>

    -   <span data-ttu-id="2398a-113">**Med-v 主機代理安裝**檔案–安裝主機代理程式（med-v \ _HostAgent \ _Setup 安裝檔案）。</span><span class="sxs-lookup"><span data-stu-id="2398a-113">**MED-V Host Agent Installation File** – installs the Host Agent (MED-V\_HostAgent\_Setup installation file).</span></span> <span data-ttu-id="2398a-114">如需詳細資訊，請參閱[如何手動安裝 Med-v 主機代理程式](how-to-manually-install-the-med-v-host-agent.md)。</span><span class="sxs-lookup"><span data-stu-id="2398a-114">For more information, see [How to Manually Install the MED-V Host Agent](how-to-manually-install-the-med-v-host-agent.md).</span></span>

    -   <span data-ttu-id="2398a-115">**Med-v 工作區安裝程式、VHD 及安裝程式可執行檔**-在**Med-v 工作區包裝**程式中建立。</span><span class="sxs-lookup"><span data-stu-id="2398a-115">**MED-V Workspace Installer, VHD, and Setup Executable** – created in the **MED-V Workspace Packager**.</span></span> <span data-ttu-id="2398a-116">如需詳細資訊，請參閱[建立 Med-v 工作區套件](create-a-med-v-workspace-package.md)。</span><span class="sxs-lookup"><span data-stu-id="2398a-116">For more information, see [Create a MED-V Workspace Package](create-a-med-v-workspace-package.md).</span></span>

        <span data-ttu-id="2398a-117">**重要** VHD 與設定可執行程式必須與 MED-V 工作區安裝程式位於同一個資料夾中。</span><span class="sxs-lookup"><span data-stu-id="2398a-117">**Important** The VHD and Setup executable program must be in the same folder as the MED-V workspace installer.</span></span> <span data-ttu-id="2398a-118">然後，透過執行 setup.exe 來安裝 MED-V 工作區安裝程式。</span><span class="sxs-lookup"><span data-stu-id="2398a-118">Then, install the MED-V workspace installer by running setup.exe.</span></span>

         

2.  <span data-ttu-id="2398a-119">在測試電腦上安裝所有元件之後，請執行 MED-V 主機代理程式，以開始第一次設定。</span><span class="sxs-lookup"><span data-stu-id="2398a-119">After all of the components are installed on the test computer, run the MED-V Host Agent to start first time setup.</span></span>

    <span data-ttu-id="2398a-120">按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft 企業版桌面虛擬化**]，然後按一下 [ **med-v 主機代理程式**]。</span><span class="sxs-lookup"><span data-stu-id="2398a-120">Click **Start**, click **All Programs**, click **Microsoft Enterprise Desktop Virtualization**, and then click **MED-V Host Agent**.</span></span>

    <span data-ttu-id="2398a-121">**記事** 如果您無法在測試電腦上實際執行 MED-V 主機代理程式，第一次電腦重新開機時，系統會自動啟動。</span><span class="sxs-lookup"><span data-stu-id="2398a-121">**Note** If you cannot physically run the MED-V Host Agent on the test computer, first time setup starts automatically the next time that the computer restarts.</span></span>

     

<span data-ttu-id="2398a-122">第一次安裝開始，可能需要十分鐘以上的時間才能完成。</span><span class="sxs-lookup"><span data-stu-id="2398a-122">First time setup starts and can take ten minutes or more to finish.</span></span>

<span data-ttu-id="2398a-123">如需在第一次執行設定時測試設定設定的相關資訊，請參閱[如何驗證第一次設定](how-to-verify-first-time-setup-settings.md)設定。</span><span class="sxs-lookup"><span data-stu-id="2398a-123">For information about testing your configuration settings when first time setup is running, see [How to Verify First Time Setup Settings](how-to-verify-first-time-setup-settings.md).</span></span>

**<span data-ttu-id="2398a-124">手動建立測試環境</span><span class="sxs-lookup"><span data-stu-id="2398a-124">To create a test environment manually</span></span>**

1.  <span data-ttu-id="2398a-125">在本機測試環境中安裝 MED-V 主機代理程式，其中包含 MED-V 必備元件，例如包含新增和更新的 Windows 虛擬電腦。</span><span class="sxs-lookup"><span data-stu-id="2398a-125">Install the MED-V Host Agent in a local test environment that includes MED-V prerequisites, such as Windows Virtual PC with additions and updates.</span></span> <span data-ttu-id="2398a-126">如需詳細資訊，請參閱[如何手動安裝 Med-v 主機代理程式](how-to-manually-install-the-med-v-host-agent.md)。</span><span class="sxs-lookup"><span data-stu-id="2398a-126">For information, see [How to Manually Install the MED-V Host Agent](how-to-manually-install-the-med-v-host-agent.md).</span></span>

2.  <span data-ttu-id="2398a-127">將 MED-V 工作區檔案複製到您的測試環境。</span><span class="sxs-lookup"><span data-stu-id="2398a-127">Copy the MED-V workspace files to your test environment.</span></span> <span data-ttu-id="2398a-128">MED-V 工作區檔案位於您在**Med-v 工作區包裝**程式中指定的目的地資料夾。</span><span class="sxs-lookup"><span data-stu-id="2398a-128">The MED-V workspace files are located in the destination folder that you specified in the **MED-V Workspace Packager**.</span></span>

    <span data-ttu-id="2398a-129">**重要** 在您的測試環境中，VHD 和設定可執行程式必須與 MED-V 工作區安裝程式位於相同的資料夾中。</span><span class="sxs-lookup"><span data-stu-id="2398a-129">**Important** The VHD and Setup executable program must be in the same folder on your test environment as the MED-V workspace installer.</span></span>

     

3.  <span data-ttu-id="2398a-130">執行 setup.exe，即可安裝 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="2398a-130">Install the MED-V workspace by running setup.exe.</span></span>

4.  <span data-ttu-id="2398a-131">執行 MED-V 主機代理程式的第一次開始設定。</span><span class="sxs-lookup"><span data-stu-id="2398a-131">Start first time setup by running the MED-V Host Agent.</span></span>

    <span data-ttu-id="2398a-132">按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **Microsoft 企業版桌面虛擬化**]，然後按一下 [ **med-v 主機代理程式**]。</span><span class="sxs-lookup"><span data-stu-id="2398a-132">Click **Start**, click **All Programs**, click **Microsoft Enterprise Desktop Virtualization**, and then click **MED-V Host Agent**.</span></span>

<span data-ttu-id="2398a-133">第一次安裝開始，可能需要幾分鐘的時間才能完成，視指定的 VHD 大小而定。</span><span class="sxs-lookup"><span data-stu-id="2398a-133">First time setup starts and might take several minutes to complete, depending on the size of the VHD specified.</span></span>

<span data-ttu-id="2398a-134">您現在已準備好針對您針對 MED-V 工作區所指定的設定、應用程式發佈和 URL 重新導向來測試不同設定。</span><span class="sxs-lookup"><span data-stu-id="2398a-134">You are now ready to test the different settings for configuration, application publishing, and URL redirection that you specified for your MED-V workspace.</span></span>

<span data-ttu-id="2398a-135">**記事** 根據預設，MED-V 會覆寫來賓中的螢幕鎖定原則。</span><span class="sxs-lookup"><span data-stu-id="2398a-135">**Note** By default, MED-V overrides the screen lock policy in the guest.</span></span> <span data-ttu-id="2398a-136">不過，這不會造成安全性問題，因為主機電腦仍會採用螢幕鎖定原則。</span><span class="sxs-lookup"><span data-stu-id="2398a-136">However, this does not pose a security problem because the host computer still honors the screen lock policy.</span></span>

 

## <span data-ttu-id="2398a-137">相關主題</span><span class="sxs-lookup"><span data-stu-id="2398a-137">Related topics</span></span>


[<span data-ttu-id="2398a-138">如何驗證第一次安裝設定</span><span class="sxs-lookup"><span data-stu-id="2398a-138">How to Verify First Time Setup Settings</span></span>](how-to-verify-first-time-setup-settings.md)

[<span data-ttu-id="2398a-139">如何測試應用程式發佈</span><span class="sxs-lookup"><span data-stu-id="2398a-139">How to Test Application Publishing</span></span>](how-to-test-application-publishing.md)

[<span data-ttu-id="2398a-140">如何測試 URL 重新導向</span><span class="sxs-lookup"><span data-stu-id="2398a-140">How to Test URL Redirection</span></span>](how-to-test-url-redirection.md)

 

 





