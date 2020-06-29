---
title: 如何測試應用程式發佈
description: 如何測試應用程式發佈
author: dansimp
ms.assetid: 17ba2e12-50a0-4f41-8300-f61f09db9f6c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: 8dffb4f79ac89c7d419b27640f4f05364bd69e5d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812039"
---
# <span data-ttu-id="7082e-103">如何測試應用程式發佈</span><span class="sxs-lookup"><span data-stu-id="7082e-103">How to Test Application Publishing</span></span>


<span data-ttu-id="7082e-104">在您第一次設定完成測試之後，您可以執行下列工作，以驗證應用程式發佈功能是否如期運作。</span><span class="sxs-lookup"><span data-stu-id="7082e-104">After your test of first time setup finishes, you can verify that the application publishing functionality is working as expected by performing the following tasks.</span></span>

<a href="" id="bkmk-apppub"></a>**<span data-ttu-id="7082e-105">測試應用程式發佈</span><span class="sxs-lookup"><span data-stu-id="7082e-105">To test application publishing</span></span>**

1.  <span data-ttu-id="7082e-106">確認您指定要發佈的應用程式是可見的。</span><span class="sxs-lookup"><span data-stu-id="7082e-106">Verify that the applications that you specified for publishing are visible.</span></span>

    <span data-ttu-id="7082e-107">按一下 [**開始**]，然後按一下 [**所有程式**]，然後搜尋指定的應用程式。</span><span class="sxs-lookup"><span data-stu-id="7082e-107">Click **Start** and then click **All Programs** and search for the specified applications.</span></span>

    <span data-ttu-id="7082e-108">在某些情況下，您可能會安裝兩次相同的應用程式，一次是在主機電腦上，一次是在訪客上。</span><span class="sxs-lookup"><span data-stu-id="7082e-108">In some cases, you might have the same application installed two times, one time on the host computer and one time on the guest.</span></span> <span data-ttu-id="7082e-109">如果發佈的應用程式具有相同的名稱，發佈到主機 [**開始**] 功能表上的同一個位置，則會將虛擬機器名稱新增至快捷方式名稱，以區別主機應用程式快捷方式。</span><span class="sxs-lookup"><span data-stu-id="7082e-109">If a published application that has the same name is published to the same location on the host **Start** menu, it is distinguished from the host application shortcut by adding the virtual machine name to the shortcut name.</span></span> <span data-ttu-id="7082e-110">例如，對於名為 "MEDVHost1" 的虛擬機器，主機應用程式可能會是 "Notepad"，而已發佈的應用程式可能是 "Notepad （MEDVHost1）"。</span><span class="sxs-lookup"><span data-stu-id="7082e-110">For example, for a virtual machine named “MEDVHost1”, a host application might be "Notepad" and a published application might be "Notepad (MEDVHost1)".</span></span>

2.  <span data-ttu-id="7082e-111">確認應用程式正常運作。</span><span class="sxs-lookup"><span data-stu-id="7082e-111">Verify that the applications function as intended.</span></span>

    <span data-ttu-id="7082e-112">在主機電腦上，啟動您發佈的應用程式，並確認它們已在來賓上的 Windows XP SP3 中開啟。</span><span class="sxs-lookup"><span data-stu-id="7082e-112">On the host computer, start the applications that you published and verify that they open in Windows XP SP3 on the guest.</span></span> <span data-ttu-id="7082e-113">應用程式必須出現在主機電腦桌面上的 Windows XP 樣式視窗中。</span><span class="sxs-lookup"><span data-stu-id="7082e-113">The application must appear in a Windows XP-style window on the host computer desktop.</span></span>

3.  <span data-ttu-id="7082e-114">如果適用，請確認檔重新導向正常運作。</span><span class="sxs-lookup"><span data-stu-id="7082e-114">If applicable, verify that document redirection functions as intended.</span></span>

    <span data-ttu-id="7082e-115">如果來賓上已發佈的應用程式必須開啟主機系統磁碟機上的資料夾，請確定它可以開啟指定的資料夾。</span><span class="sxs-lookup"><span data-stu-id="7082e-115">If a published application on the guest has to open a folder on the host system drive, ensure that it can open the specified folder.</span></span>

    <span data-ttu-id="7082e-116">**重要** 因為 Windows Virtual 電腦不支援從已共用的資料夾建立共用，所以從共用資料夾開啟的任何檔（例如位於網路上的 [我的文件] 資料夾），都不會發生重新導向。</span><span class="sxs-lookup"><span data-stu-id="7082e-116">**Important** Because Windows Virtual PC does not support creating a share from a folder that is already shared, redirection does not occur for any documents that open from a shared folder, such as a My Documents folder that is located on the network.</span></span> <span data-ttu-id="7082e-117">如需詳細資訊，請參閱[操作疑難排解](operations-troubleshooting-medv2.md)。</span><span class="sxs-lookup"><span data-stu-id="7082e-117">For more information, see [Operations Troubleshooting](operations-troubleshooting-medv2.md).</span></span>

<span data-ttu-id="7082e-118">確認已發佈的應用程式安裝正常且正常運作之後，您可以測試是否可以在 MED-V 工作區中新增或移除應用程式。</span><span class="sxs-lookup"><span data-stu-id="7082e-118">After you have verified that published applications are installed and functioning correctly, you can test whether applications can be added or removed from the MED-V workspace.</span></span>

**<span data-ttu-id="7082e-119">測試是否可以新增或移除應用程式</span><span class="sxs-lookup"><span data-stu-id="7082e-119">To test that an application can be added or removed</span></span>**

1.  <span data-ttu-id="7082e-120">從 MED-V 工作區新增或移除應用程式。</span><span class="sxs-lookup"><span data-stu-id="7082e-120">Add or remove an application from the MED-V workspace.</span></span>

    <span data-ttu-id="7082e-121">如需如何從 MED-V 工作區新增及移除應用程式的相關資訊，請參閱[管理部署至 Med-v 工作區的應用程式](managing-applications-deployed-to-med-v-workspaces.md)。</span><span class="sxs-lookup"><span data-stu-id="7082e-121">For information about how to add and remove applications from a MED-V workspace, see [Managing Applications Deployed to MED-V Workspaces](managing-applications-deployed-to-med-v-workspaces.md).</span></span>

2.  <span data-ttu-id="7082e-122">如果您新增了應用程式，請重複上述步驟，[以測試應用程式發佈](#bkmk-apppub)，以確認新的應用程式正常運作。</span><span class="sxs-lookup"><span data-stu-id="7082e-122">If you added an application, repeat the steps in [To Test Application Publishing](#bkmk-apppub) to verify that the new application functions as intended.</span></span>

3.  <span data-ttu-id="7082e-123">如果您移除應用程式，請按一下 [**開始**]，然後按一下 [**所有程式**]，確認您移除的任何應用程式都已不再列出。</span><span class="sxs-lookup"><span data-stu-id="7082e-123">If you removed an application, click **Start** and then click **All Programs** and verify that any applications that you removed are no longer listed.</span></span>

<span data-ttu-id="7082e-124">**記事** 如果您在驗證應用程式發佈設定時遇到任何問題，請參閱[操作疑難排解](operations-troubleshooting-medv2.md)。</span><span class="sxs-lookup"><span data-stu-id="7082e-124">**Note** If you encounter any problems when verifying your application publication settings, see [Operations Troubleshooting](operations-troubleshooting-medv2.md).</span></span>

<span data-ttu-id="7082e-125">測試完應用程式發佈之後，您可以測試其他的 MED-V 工作區設定，以確認其正常運作。</span><span class="sxs-lookup"><span data-stu-id="7082e-125">After you have completed testing application publishing, you can test other MED-V workspace configurations to verify that they function as intended.</span></span>

<span data-ttu-id="7082e-126">完成您的 MED-V 工作區套件測試並確認它已正常運作之後，您就可以將 MED-V 工作區部署到您的企業。</span><span class="sxs-lookup"><span data-stu-id="7082e-126">After you have completed testing your MED-V workspace package and have verified that it is functioning as intended, you can deploy the MED-V workspace to your enterprise.</span></span>

## <span data-ttu-id="7082e-127">相關主題</span><span class="sxs-lookup"><span data-stu-id="7082e-127">Related topics</span></span>

[<span data-ttu-id="7082e-128">如何測試 URL 重新導向</span><span class="sxs-lookup"><span data-stu-id="7082e-128">How to Test URL Redirection</span></span>](how-to-test-url-redirection.md)

[<span data-ttu-id="7082e-129">如何驗證第一次安裝設定</span><span class="sxs-lookup"><span data-stu-id="7082e-129">How to Verify First Time Setup Settings</span></span>](how-to-verify-first-time-setup-settings.md)

[<span data-ttu-id="7082e-130">部署 MED-V 工作區套件</span><span class="sxs-lookup"><span data-stu-id="7082e-130">Deploying the MED-V Workspace Package</span></span>](deploying-the-med-v-workspace-package.md)

 

 





