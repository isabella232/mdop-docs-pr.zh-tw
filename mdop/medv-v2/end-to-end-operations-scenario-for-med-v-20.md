---
title: MED-V 2.0 端對端操作案例
description: MED-V 2.0 端對端操作案例
author: dansimp
ms.assetid: 1d87f5f3-9fc5-4731-8bd1-c155714f34ee
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 90a7c2135ad27040ed87dac980b67321eb771574
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811594"
---
# <span data-ttu-id="db635-103">MED-V 2.0 端對端操作案例</span><span class="sxs-lookup"><span data-stu-id="db635-103">End-to-End Operations Scenario for MED-V 2.0</span></span>


<span data-ttu-id="db635-104">此範例案例 Microsoft 企業桌面虛擬化（MED-V）2.0 可協助您使用多個案例端對端部署和管理 MED-V。</span><span class="sxs-lookup"><span data-stu-id="db635-104">This sample scenario for Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 helps you deploy and manage MED-V by using multiple scenarios end-to-end.</span></span> <span data-ttu-id="db635-105">您可以將這個範例案例想像成案例研究，協助將個別案例和程式放在內容中。</span><span class="sxs-lookup"><span data-stu-id="db635-105">You can think of this sample scenario as a case study that helps put the individual scenarios and procedures in context.</span></span>

<span data-ttu-id="db635-106">本節提供在企業中建立、部署及管理 MED-V 工作區作為端對端方案的基本資訊與指示。</span><span class="sxs-lookup"><span data-stu-id="db635-106">This section provides basic information and directions for creating, deploying, and managing MED-V workspaces as an end-to-end solution in your enterprise.</span></span>

## <span data-ttu-id="db635-107">MED-V 運算逐步方案</span><span class="sxs-lookup"><span data-stu-id="db635-107">MED-V Operations Step-by-step Scenario</span></span>


<span data-ttu-id="db635-108">您在 MED-V 作業案例中遵循的逐步程式會包括下列專案：</span><span class="sxs-lookup"><span data-stu-id="db635-108">The step-by-step procedures that you follow in a MED-V operations scenario include the following:</span></span>

-   <span data-ttu-id="db635-109">[建立適用于 med-v 的 Windows 虛擬電腦影像](creating-a-windows-virtual-pc-image-for-med-v.md#bkmk-creatingavirtualmachinebyusingmicrosoftvirtualpc)，看看如何建立和設定 Med-v 的 WINDOWS 虛擬電腦影像。</span><span class="sxs-lookup"><span data-stu-id="db635-109">[Creating a Windows Virtual PC Image for MED-V](creating-a-windows-virtual-pc-image-for-med-v.md#bkmk-creatingavirtualmachinebyusingmicrosoftvirtualpc) reviews how to create and configure a Windows Virtual PC image for MED-V.</span></span> <span data-ttu-id="db635-110">您必須先準備一個虛擬硬碟（VHD），才能將 MED-V 工作區傳送給使用者，然後才能為 MED-V 建立 MED-V 工作區安裝程式套件。</span><span class="sxs-lookup"><span data-stu-id="db635-110">Before you can deliver a MED-V workspace to users, you must first prepare a virtual hard disk (VHD) that you use to build the MED-V workspace installer package for MED-V.</span></span>

-   <span data-ttu-id="db635-111">[建立適用于 med-v 的 Windows 虛擬電腦影像](creating-a-windows-virtual-pc-image-for-med-v.md#bkmk-installingwindowsxpontovpc)，看看如何在您的 WINDOWS 虛擬電腦影像上安裝 WINDOWS XP SP3 作業系統。</span><span class="sxs-lookup"><span data-stu-id="db635-111">[Creating a Windows Virtual PC Image for MED-V](creating-a-windows-virtual-pc-image-for-med-v.md#bkmk-installingwindowsxpontovpc) reviews how to install the Windows XP SP3 operating system on your Windows Virtual PC image.</span></span> <span data-ttu-id="db635-112">在建立 MED-V 工作區前，MED-V 需要在 Windows 虛擬電腦映射上安裝 Windows XP SP3。</span><span class="sxs-lookup"><span data-stu-id="db635-112">MED-V requires that Windows XP SP3 is installed on the Windows Virtual PC image before you build the MED-V workspace.</span></span>

-   <span data-ttu-id="db635-113">[建立適用于 med-v 的 Windows 虛擬電腦映射](creating-a-windows-virtual-pc-image-for-med-v.md#bkmk-installingnet)：如何將 .net FRAMEWORK 3.5 SP1 及更新 KB959209 手動安裝到您準備搭配 med-v 使用的 WINDOWS 虛擬電腦影像中。</span><span class="sxs-lookup"><span data-stu-id="db635-113">[Creating a Windows Virtual PC Image for MED-V](creating-a-windows-virtual-pc-image-for-med-v.md#bkmk-installingnet) reviews how to manually install the .NET Framework 3.5 SP1 and the update KB959209 into the Windows Virtual PC image that you prepare for use with MED-V.</span></span> <span data-ttu-id="db635-114">MED-V 需要 .NET Framework 3.5 SP1，而更新[KB959209](https://go.microsoft.com/fwlink/?LinkId=204950) （ https://go.microsoft.com/fwlink/?LinkId=204950) 解決數個已知的應用程式相容性問題。</span><span class="sxs-lookup"><span data-stu-id="db635-114">MED-V requires the .NET Framework 3.5 SP1, and the update [KB959209](https://go.microsoft.com/fwlink/?LinkId=204950) (https://go.microsoft.com/fwlink/?LinkId=204950) addresses several known application compatibility issues.</span></span>

-   <span data-ttu-id="db635-115">[建立適用于 med-v 的 Windows 虛擬電腦影像](creating-a-windows-virtual-pc-image-for-med-v.md#bkmk-applypatchestovpc)，瞭解如何使用最新的軟體更新及其他需要或重要的修補程式（對於執行 med-v）來更新您的 Windows XP 映射。</span><span class="sxs-lookup"><span data-stu-id="db635-115">[Creating a Windows Virtual PC Image for MED-V](creating-a-windows-virtual-pc-image-for-med-v.md#bkmk-applypatchestovpc) reviews how to update your Windows XP image with the latest software updates and other hotfixes necessary or important for running MED-V.</span></span>

-   <span data-ttu-id="db635-116">[建立適用于 med-v 的 Windows 虛擬電腦影像](creating-a-windows-virtual-pc-image-for-med-v.md#bkmk-installintegration)查看如何在您的 Windows XP 映射中安裝整合元件套件。</span><span class="sxs-lookup"><span data-stu-id="db635-116">[Creating a Windows Virtual PC Image for MED-V](creating-a-windows-virtual-pc-image-for-med-v.md#bkmk-installintegration) reviews how to install the integration components package in your Windows XP image.</span></span> <span data-ttu-id="db635-117">它們提供可改善虛擬環境與物理電腦之間互動的功能。</span><span class="sxs-lookup"><span data-stu-id="db635-117">These provide features that improve the interaction between the virtual environment and the physical computer.</span></span>

-   <span data-ttu-id="db635-118">[在 Windows 虛擬電腦影像上安裝應用程式](installing-applications-on-a-windows-virtual-pc-image.md)，可瞭解如何在您的 Windows XP 映射上安裝特定類型的軟體，這些軟體在您執行 med-v （例如電子軟體發佈系統和防毒軟體）時很有説明。</span><span class="sxs-lookup"><span data-stu-id="db635-118">[Installing Applications on a Windows Virtual PC Image](installing-applications-on-a-windows-virtual-pc-image.md) reviews how you can install certain kinds of software on your Windows XP image that are helpful when you are running MED-V, such as an electronic software distribution system and antivirus software.</span></span>

-   <span data-ttu-id="db635-119">[針對 med-v 設定 Windows VIRTUAL 電腦映射](configuring-a-windows-virtual-pc-image-for-med-v.md)，討論如何使用 Sysprep 來設定影像，以確保它已可搭配 med-v 使用。</span><span class="sxs-lookup"><span data-stu-id="db635-119">[Configuring a Windows Virtual PC Image for MED-V](configuring-a-windows-virtual-pc-image-for-med-v.md) discusses how to configure the image by using Sysprep to make sure that it is ready for use with MED-V.</span></span> <span data-ttu-id="db635-120">然後，就會使用準備的 MED-V 影像來建立 MED-V 工作區套件。</span><span class="sxs-lookup"><span data-stu-id="db635-120">The prepared MED-V image is then used to create your MED-V workspace package.</span></span>

-   <span data-ttu-id="db635-121">[建立 Med-v 工作區套件](create-a-med-v-workspace-package.md)審查如何建立您在整個企業中部署的 med-v 工作區套件。</span><span class="sxs-lookup"><span data-stu-id="db635-121">[Create a MED-V Workspace Package](create-a-med-v-workspace-package.md) reviews how to build the MED-V workspace package that you deploy throughout your enterprise.</span></span> <span data-ttu-id="db635-122">您可以部署 MED-V 工作區套件，在最終使用者的電腦上安裝 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="db635-122">You deploy the MED-V workspace package to install the MED-V workspace on end-user computers.</span></span> <span data-ttu-id="db635-123">MED-V 工作區是一種 Windows XP 桌上型電腦環境，使用者可在此環境中與 MED-V 提供的虛擬機器進行互動。</span><span class="sxs-lookup"><span data-stu-id="db635-123">A MED-V workspace is the Windows XP desktop environment from which end users interact with the virtual machine provided by MED-V.</span></span>

-   <span data-ttu-id="db635-124">[測試 Med-v 工作區套件](testing-the-med-v-workspace-package.md)討論如何建立測試環境，您可以在其中測試 med-v 工作區套件的功能，例如第一次設定設定和應用程式發佈。</span><span class="sxs-lookup"><span data-stu-id="db635-124">[Testing the MED-V Workspace Package](testing-the-med-v-workspace-package.md) discusses how to create a test environment in which you can test the functionality of the MED-V workspace package, such as first time setup settings and application publishing.</span></span> <span data-ttu-id="db635-125">完成您的 MED-V 工作區套件測試並確認它已正常運作之後，您就可以將它部署在整個企業中。</span><span class="sxs-lookup"><span data-stu-id="db635-125">After you have completed testing your MED-V workspace package and have verified that it is functioning as intended, you can deploy it throughout your enterprise.</span></span>

-   <span data-ttu-id="db635-126">[部署 Med-v 工作區套件](deploying-the-med-v-workspace-package.md)討論如何使用電子軟體發佈系統或 Windows 7 影像來部署 med-v 工作區。</span><span class="sxs-lookup"><span data-stu-id="db635-126">[Deploying the MED-V Workspace Package](deploying-the-med-v-workspace-package.md) discusses how to deploy the MED-V workspace either by using an electronic software distribution system or in a Windows 7 image.</span></span> <span data-ttu-id="db635-127">或者，如果您想要的話，此區段也會說明如何手動部署 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="db635-127">Or if you prefer, this section also shows you how you can deploy the MED-V workspace manually.</span></span>

-   <span data-ttu-id="db635-128">[監視 med-v-v 工作區](monitor-med-v-workspaces.md)會檢查如何監視 med-v 工作區的部署，以判斷第一次安裝程式是否已順利完成。</span><span class="sxs-lookup"><span data-stu-id="db635-128">[Monitor MED-V Workspaces](monitor-med-v-workspaces.md) reviews how to monitor the deployment of MED-V workspaces to determine whether first time setup completed successfully.</span></span> <span data-ttu-id="db635-129">監控第一次設定的成功與否，是因為 MED-V 在第一次成功完成之前並不是使用中的狀態。</span><span class="sxs-lookup"><span data-stu-id="db635-129">Monitoring the success of first time setup is important because MED-V is not in a usable state until first time setup has completed successfully.</span></span> <span data-ttu-id="db635-130">本節也說明您可以設定您的環境來偵測那些可能會影響 MED-V 的網路變更。</span><span class="sxs-lookup"><span data-stu-id="db635-130">This section also shows you can set up your environment to detect those network changes that can affect MED-V.</span></span>

-   <span data-ttu-id="db635-131">[管理 Med-v 工作區應用程式](manage-med-v-workspace-applications.md)查看如何在已部署的 med-v 工作區上安裝及移除或發佈及取消發佈應用程式。</span><span class="sxs-lookup"><span data-stu-id="db635-131">[Manage MED-V Workspace Applications](manage-med-v-workspace-applications.md) reviews how to install and remove or publish and unpublish applications on a deployed MED-V workspace.</span></span> <span data-ttu-id="db635-132">本節也說明如何在 MED-V 工作區中手動更新軟體，以及如何管理自動更新。</span><span class="sxs-lookup"><span data-stu-id="db635-132">This section also shows how to manually update software in a MED-V workspace and how to manage automatic updates.</span></span> <span data-ttu-id="db635-133">MED-V 工作區是包含獨立作業系統的虛擬機器，其自動軟體更新程式必須與企業中的物理電腦完全管理。</span><span class="sxs-lookup"><span data-stu-id="db635-133">The MED-V workspace is a virtual machine that contains a separate operating system whose automatic software update process must be managed exactly like the physical computers in your enterprise.</span></span>

-   <span data-ttu-id="db635-134">[管理 MED-V URL](manage-med-v-url-redirection.md)重新導向查看如何在已部署的 med-v 工作區上新增和移除網址重新導向設定。</span><span class="sxs-lookup"><span data-stu-id="db635-134">[Manage MED-V URL Redirection](manage-med-v-url-redirection.md) reviews how to add and remove web address redirection settings on the deployed MED-V workspace.</span></span> <span data-ttu-id="db635-135">您可以透過登錄來新增或移除 URL 重新導向資訊，或重建 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="db635-135">You can add or remove URL redirection information through the registry or by rebuilding the MED-V workspace.</span></span> <span data-ttu-id="db635-136">您也可以在 MED-V 工作區包裝程式上使用此嚮導來管理 web 位址重新導向。</span><span class="sxs-lookup"><span data-stu-id="db635-136">You can also use the wizard on the MED-V Workspace Packager to manage web address redirection.</span></span>

-   <span data-ttu-id="db635-137">[管理 Med-v 工作區設定](manage-med-v-workspace-settings.md)瞭解如何使用 Med-v-v 工作區包裝程式來查看及編輯 med-v 設定設定。</span><span class="sxs-lookup"><span data-stu-id="db635-137">[Manage MED-V Workspace Settings](manage-med-v-workspace-settings.md) reviews how to view and edit MED-V configuration settings by using the MED-V Workspace Packager.</span></span> <span data-ttu-id="db635-138">本節列出所有可設定的 MED-V 登錄機碼，並包含每個的「類型」、「預設」和「描述」。</span><span class="sxs-lookup"><span data-stu-id="db635-138">This section lists all the configurable MED-V registry keys and includes the type, default, and description of each.</span></span> <span data-ttu-id="db635-139">本節也包含如何在 MED-V 工作區中管理印表機的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="db635-139">This section also includes information about how to manage printers in MED-V workspaces.</span></span> <span data-ttu-id="db635-140">在 MED-V 2.0 中，印表機重新導向可以讓使用者在 MED-V 虛擬機器與主機電腦之間保持一致的列印體驗。</span><span class="sxs-lookup"><span data-stu-id="db635-140">In MED-V 2.0, printer redirection gives users a consistent printing experience between the MED-V virtual machine and the host computer.</span></span>

## <span data-ttu-id="db635-141">相關主題</span><span class="sxs-lookup"><span data-stu-id="db635-141">Related topics</span></span>


[<span data-ttu-id="db635-142">適用於 MED-V 的操作</span><span class="sxs-lookup"><span data-stu-id="db635-142">Operations for MED-V</span></span>](operations-for-med-v.md)

[<span data-ttu-id="db635-143">MED-V 2.0 端對端規劃案例</span><span class="sxs-lookup"><span data-stu-id="db635-143">End-to-End Planning Scenario for MED-V 2.0</span></span>](end-to-end-planning-scenario-for-med-v-20.md)

[<span data-ttu-id="db635-144">MED-V 2.0 端對端部署案例</span><span class="sxs-lookup"><span data-stu-id="db635-144">End-to-End Deployment Scenario for MED-V 2.0</span></span>](end-to-end-deployment-scenario-for-med-v-20.md)

 

 





