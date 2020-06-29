---
title: 如何驗證第一次安裝設定
description: 如何驗證第一次安裝設定
author: dansimp
ms.assetid: e8a07d4c-5786-4455-ac43-2deac4042efd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d859d627ec90fbc26d18019062d5e316f907cec6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800240"
---
# <span data-ttu-id="1dd79-103">如何驗證第一次安裝設定</span><span class="sxs-lookup"><span data-stu-id="1dd79-103">How to Verify First Time Setup Settings</span></span>


<span data-ttu-id="1dd79-104">在您第一次安裝測試開始或完成之後，您可以執行下列工作，以驗證您在 MED-V 工作區中所設定的設定。</span><span class="sxs-lookup"><span data-stu-id="1dd79-104">While your test of first time setup is running or after it finishes, you can verify the settings that you configured in your MED-V workspace by performing the following tasks.</span></span>

<span data-ttu-id="1dd79-105">**記事** 如需有關如何在部署後監視整個企業中第一次設定成功完成的相關資訊，請參閱[監視 Med-v 工作區部署](monitoring-med-v-workspace-deployments.md)。</span><span class="sxs-lookup"><span data-stu-id="1dd79-105">**Note** For information about how to monitor the successful completion of first time setup throughout your enterprise after deployment, see [Monitoring MED-V Workspace Deployments](monitoring-med-v-workspace-deployments.md).</span></span>

 

**<span data-ttu-id="1dd79-106">在第一次設定期間驗證設定</span><span class="sxs-lookup"><span data-stu-id="1dd79-106">To verify settings during first time setup</span></span>**

1.  <span data-ttu-id="1dd79-107">第一次執行安裝程式時，請確認下列事項：</span><span class="sxs-lookup"><span data-stu-id="1dd79-107">While first time setup is running, verify the following:</span></span>

    <span data-ttu-id="1dd79-108">如果您指定的是**無人參與**模式，請確認第一次執行安裝程式時不會顯示虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="1dd79-108">If you specified **Unattended** mode, verify that the virtual machine does not appear when first time setup is running.</span></span>

    <span data-ttu-id="1dd79-109">如果您指定的是「有人值守」模式，請確認虛擬機器出現，而且會顯示所有需要使用者輸入的欄位。</span><span class="sxs-lookup"><span data-stu-id="1dd79-109">If you specified attended mode, verify that the virtual machine appears and that all fields that require user input are displayed.</span></span>

2.  <span data-ttu-id="1dd79-110">您也可以在第一次安裝程式執行時，透過查看虛擬機器來監視完整的第一次設定處理常式。</span><span class="sxs-lookup"><span data-stu-id="1dd79-110">You can also monitor the complete first time setup process by viewing the virtual machine when first time setup is running.</span></span> <span data-ttu-id="1dd79-111">若要這樣做，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="1dd79-111">To do this, follow these steps:</span></span>

    1.  <span data-ttu-id="1dd79-112">開啟 Windows 虛擬電腦主控台。</span><span class="sxs-lookup"><span data-stu-id="1dd79-112">Open the Windows Virtual PC Console.</span></span>

        <span data-ttu-id="1dd79-113">按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **windows 虛擬電腦**]，然後按一下 [ **windows 虛擬電腦**]。</span><span class="sxs-lookup"><span data-stu-id="1dd79-113">Click **Start**, click **All Programs**, click **Windows Virtual PC**, and then click **Windows Virtual PC**.</span></span>

    2.  <span data-ttu-id="1dd79-114">如果沒有執行，請啟動 MED-V-V。</span><span class="sxs-lookup"><span data-stu-id="1dd79-114">Start MED-V if it is not already running.</span></span>

        <span data-ttu-id="1dd79-115">如果您在虛擬機器清單中顯示已部署 MED-V 工作區的名稱，則不會在短期內出現。</span><span class="sxs-lookup"><span data-stu-id="1dd79-115">If not already present, in a short time, a virtual machine with the name of the deployed MED-V workspace appears in the list of virtual machines.</span></span>

    3.  <span data-ttu-id="1dd79-116">按兩下 MED-V 虛擬機器將它開啟。</span><span class="sxs-lookup"><span data-stu-id="1dd79-116">Double-click the MED-V virtual machine to open it.</span></span>

        <span data-ttu-id="1dd79-117">在進行設定時，您可以觀察 MED-V 虛擬機器，而且您可以針對最小化安裝程式進行疑難排解。</span><span class="sxs-lookup"><span data-stu-id="1dd79-117">You can observe the MED-V virtual machine when it is being set up, and you can troubleshoot the Mini-Setup procedure.</span></span> <span data-ttu-id="1dd79-118">在其他螢幕上驗證資訊，例如設定網路設定、電腦網域加入資訊、設定來賓代理程式、設定個人設定及關閉。</span><span class="sxs-lookup"><span data-stu-id="1dd79-118">Verify the information in the different screens as they go by, such as configuring networking settings, computer domain join information, configuring of the Guest Agent, set up of personal settings, and shutdown.</span></span>

    4.  <span data-ttu-id="1dd79-119">在第一次設定完成時，虛擬機器會自動關閉。</span><span class="sxs-lookup"><span data-stu-id="1dd79-119">The virtual machine closes automatically when first time setup finishes.</span></span>

        <span data-ttu-id="1dd79-120">**記事** 您可以隨時關閉虛擬機器視窗，並在第一次設定繼續時關閉。</span><span class="sxs-lookup"><span data-stu-id="1dd79-120">**Note** You can close the virtual machine window at any time and first time setup continues.</span></span>

         

**<span data-ttu-id="1dd79-121">在第一次設定完成後驗證設定</span><span class="sxs-lookup"><span data-stu-id="1dd79-121">To verify settings after first time setup finishes</span></span>**

1.  <span data-ttu-id="1dd79-122">確定第一次安裝成功完成。</span><span class="sxs-lookup"><span data-stu-id="1dd79-122">Ensure that first time setup finished successfully.</span></span>

2.  <span data-ttu-id="1dd79-123">確認 MED-V 工作區已正確設定。</span><span class="sxs-lookup"><span data-stu-id="1dd79-123">Verify that the MED-V workspace is set up correctly.</span></span>

    1.  <span data-ttu-id="1dd79-124">開啟 Windows 虛擬電腦主控台。</span><span class="sxs-lookup"><span data-stu-id="1dd79-124">Open the Windows Virtual PC Console.</span></span>

        <span data-ttu-id="1dd79-125">按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **windows 虛擬電腦**]，然後按一下 [ **windows 虛擬電腦**]。</span><span class="sxs-lookup"><span data-stu-id="1dd79-125">Click **Start**, click **All Programs**, click **Windows Virtual PC**, and then click **Windows Virtual PC**.</span></span>

    2.  <span data-ttu-id="1dd79-126">按兩下已安裝的 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="1dd79-126">Double-click your installed MED-V workspace.</span></span>

        <span data-ttu-id="1dd79-127">如果 MED-V 工作區已執行虛擬應用程式，系統可能會提示您關閉應用程式，然後才能開啟虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="1dd79-127">If the MED-V workspace is already running a virtual application, you might be prompted to close the application before you can open the virtual machine.</span></span>

    3.  <span data-ttu-id="1dd79-128">在 MED-V 工作區中，以滑鼠右鍵按一下 [**我的電腦**]，然後按一下 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="1dd79-128">In the MED-V workspace, right-click **My Computer**, and then click **Properties**.</span></span>

    4.  <span data-ttu-id="1dd79-129">確認 MED-V 工作區已加入正確的網域。</span><span class="sxs-lookup"><span data-stu-id="1dd79-129">Verify that the MED-V workspace joined the correct domain.</span></span> <span data-ttu-id="1dd79-130">如果適用于您的組織，請指定兩個不同的網域來測試網域加入，以確認由主機網域覆寫來賓網域。</span><span class="sxs-lookup"><span data-stu-id="1dd79-130">If applicable to your organization, test domain joining by specifying two different domains to verify that the guest domain is overridden by the host domain.</span></span>

    5.  <span data-ttu-id="1dd79-131">確認 MED-V 工作區已加入您指定的網域組織單位。</span><span class="sxs-lookup"><span data-stu-id="1dd79-131">Verify that the MED-V workspace joined the domain organizational unit that you specified.</span></span>

    6.  <span data-ttu-id="1dd79-132">如果您已指定電腦名稱稱遮罩，請確認新電腦名稱稱符合指定的名稱。</span><span class="sxs-lookup"><span data-stu-id="1dd79-132">If you specified the computer name mask, verify that the new computer name matches what was specified.</span></span>

3.  <span data-ttu-id="1dd79-133">確認您指定的地區設定正確無誤。</span><span class="sxs-lookup"><span data-stu-id="1dd79-133">Verify that the locale settings that you specified are correct.</span></span>

    1.  <span data-ttu-id="1dd79-134">在 MED-V 工作區中，按一下 [**開始**]，然後按一下 [**控制台**]。</span><span class="sxs-lookup"><span data-stu-id="1dd79-134">In the MED-V workspace, click **Start** and then click **Control Panel**.</span></span>

    2.  <span data-ttu-id="1dd79-135">驗證您指定的設定，例如**日期和時間**，以及**地區及語言**。</span><span class="sxs-lookup"><span data-stu-id="1dd79-135">Verify your specified configuration settings, for example, **Date and Time** and **Regional and Language**.</span></span>

<span data-ttu-id="1dd79-136">**記事** 如果您在驗證第一次設定設定時遇到任何問題，請參閱[操作疑難排解](operations-troubleshooting-medv2.md)。</span><span class="sxs-lookup"><span data-stu-id="1dd79-136">**Note** If you encounter any problems when verifying your first time setup settings, see [Operations Troubleshooting](operations-troubleshooting-medv2.md).</span></span>

 

<span data-ttu-id="1dd79-137">確認您的第一次設定設定正確之後，您可以測試其他的 MED-V 工作區設定，以確認其正常運作，例如應用程式發佈和 URL 重新導向。</span><span class="sxs-lookup"><span data-stu-id="1dd79-137">After you have verified that your first time setup settings are correct, you can test other MED-V workspace configurations to verify that they function as intended, such as application publishing and URL redirection.</span></span>

<span data-ttu-id="1dd79-138">在您完成所有的 MED-V 工作區套件測試並確認它已正常運作之後，您就可以將 MED-V 工作區部署到您的企業。</span><span class="sxs-lookup"><span data-stu-id="1dd79-138">After you have completed all testing of your MED-V workspace package and have verified that it is functioning as intended, you can deploy the MED-V workspace to your enterprise.</span></span>

## <span data-ttu-id="1dd79-139">相關主題</span><span class="sxs-lookup"><span data-stu-id="1dd79-139">Related topics</span></span>


[<span data-ttu-id="1dd79-140">如何測試應用程式發佈</span><span class="sxs-lookup"><span data-stu-id="1dd79-140">How to Test Application Publishing</span></span>](how-to-test-application-publishing.md)

[<span data-ttu-id="1dd79-141">如何測試 URL 重新導向</span><span class="sxs-lookup"><span data-stu-id="1dd79-141">How to Test URL Redirection</span></span>](how-to-test-url-redirection.md)

[<span data-ttu-id="1dd79-142">部署 MED-V 工作區套件</span><span class="sxs-lookup"><span data-stu-id="1dd79-142">Deploying the MED-V Workspace Package</span></span>](deploying-the-med-v-workspace-package.md)

[<span data-ttu-id="1dd79-143">管理 MED-V 工作區設定</span><span class="sxs-lookup"><span data-stu-id="1dd79-143">Manage MED-V Workspace Settings</span></span>](manage-med-v-workspace-settings.md)

 

 





