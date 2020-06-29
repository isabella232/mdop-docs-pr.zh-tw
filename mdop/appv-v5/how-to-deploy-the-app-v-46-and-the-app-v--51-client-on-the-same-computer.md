---
title: 如何在同一部電腦上部署 app-v 4.6 和 App-v 5.1 用戶端
description: 如何在同一部電腦上部署 app-v 4.6 和 App-v 5.1 用戶端
ms.assetid: 498d50c7-f13d-4fbb-8ea1-b959ade26fdf
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: 354db96223e623a7cd0416cb49ad67eb4d8f7162
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800527"
---
# <span data-ttu-id="a927d-103">如何在同一部電腦上部署 app-v 4.6 和 App-v 5.1 用戶端</span><span class="sxs-lookup"><span data-stu-id="a927d-103">How to Deploy the App-V 4.6 and the App-V 5.1 Client on the Same Computer</span></span>

<span data-ttu-id="a927d-104">**注意：** App-V 4.6 已退出主流支援。</span><span class="sxs-lookup"><span data-stu-id="a927d-104">**Note:** App-V 4.6 has exited Mainstream support.</span></span>

<span data-ttu-id="a927d-105">使用下列資訊來安裝 Microsoft Application Virtualization （App-v）5.1 用戶端（最好是使用最新的 Service Pack 和熱修復程式），以及在同一部電腦上使用 app-v 4.6 SP2 用戶端或應用程式 V 4.6 S3 用戶端。</span><span class="sxs-lookup"><span data-stu-id="a927d-105">Use the following information to install the Microsoft Application Virtualization (App-V) 5.1 client (preferably, with the latest Service Packs and hotfixes) and the App-V 4.6SP2 client or the App-V 4.6S3 client on the same computer.</span></span> <span data-ttu-id="a927d-106">如需支援的版本、需求及其他規劃資訊，請參閱[規劃從繼承應用程式遷移（V](planning-for-migrating-from-a-previous-version-of-app-v51.md)）。</span><span class="sxs-lookup"><span data-stu-id="a927d-106">For supported versions, requirements, and other planning information, see [Planning for Migrating from a Previous Version of App-V](planning-for-migrating-from-a-previous-version-of-app-v51.md).</span></span>

**<span data-ttu-id="a927d-107">在同一部電腦上部署 app-v 5.1 用戶端和 App-v 4.6 用戶端</span><span class="sxs-lookup"><span data-stu-id="a927d-107">To deploy the App-V 5.1 client and App-V 4.6 client on the same computer</span></span>**

1.  <span data-ttu-id="a927d-108">在執行 App-v 4.6 的電腦上，安裝下列版本的 App-v 用戶端。</span><span class="sxs-lookup"><span data-stu-id="a927d-108">Install the following version of the App-V client on the computer that is running App-V 4.6.</span></span>

    -   [<span data-ttu-id="a927d-109">Microsoft Application Virtualization 4.6 Service Pack 3</span><span class="sxs-lookup"><span data-stu-id="a927d-109">Microsoft Application Virtualization 4.6 Service Pack 3</span></span>](https://www.microsoft.com/download/details.aspx?id=41187)

2.  <span data-ttu-id="a927d-110">在執行 App-V 4.6 SP3 版本用戶端的電腦上，安裝 app-v 5.1 用戶端。</span><span class="sxs-lookup"><span data-stu-id="a927d-110">Install the App-V 5.1 client on the computer that is running the App-V 4.6 SP3 version of the client.</span></span> <span data-ttu-id="a927d-111">為了獲得最佳結果，建議您將所有可用的更新安裝到 App-v 5.1 用戶端。</span><span class="sxs-lookup"><span data-stu-id="a927d-111">For best results, we recommend that you install all available updates to the App-V 5.1 client.</span></span>

3.  <span data-ttu-id="a927d-112">逐步轉換或重新排列套件。</span><span class="sxs-lookup"><span data-stu-id="a927d-112">Convert or re-sequence the packages gradually.</span></span>

    -   <span data-ttu-id="a927d-113">若要轉換套件，請使用 App-v 5.1 套件轉換器，並將所需的套件轉換成 App-v 5.1 （**appv**）檔案格式。</span><span class="sxs-lookup"><span data-stu-id="a927d-113">To convert the packages, use the App-V 5.1 package converter and convert the required packages to the App-V 5.1 (**.appv**) file format.</span></span>

    -   <span data-ttu-id="a927d-114">若要重新排列套件，請考慮使用最新版本的 Sequencer 來取得最佳結果。</span><span class="sxs-lookup"><span data-stu-id="a927d-114">To re-sequence the packages, consider using the latest version of the Sequencer for best results.</span></span>

    <span data-ttu-id="a927d-115">如需發佈套件的詳細資訊，請參閱[如何使用管理主控台發佈套件](how-to-publish-a-package-by-using-the-management-console-51.md)。</span><span class="sxs-lookup"><span data-stu-id="a927d-115">For more information about publishing packages, see [How to Publish a Package by Using the Management Console](how-to-publish-a-package-by-using-the-management-console-51.md).</span></span>

4.  <span data-ttu-id="a927d-116">將套件部署到用戶端電腦。</span><span class="sxs-lookup"><span data-stu-id="a927d-116">Deploy packages to the client computers.</span></span>

5.  <span data-ttu-id="a927d-117">視需要轉換延伸點。</span><span class="sxs-lookup"><span data-stu-id="a927d-117">Convert extension points, as needed.</span></span> <span data-ttu-id="a927d-118">如需詳細資訊，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="a927d-118">For more information, see the following resources:</span></span>

    -   [<span data-ttu-id="a927d-119">如何為特定電腦上的所有使用者，將擴充點從 App-V 4.6 封裝移轉至轉換的 App-V 5.1 封裝</span><span class="sxs-lookup"><span data-stu-id="a927d-119">How to Migrate Extension Points From an App-V 4.6 Package to a Converted App-V 5.1 Package for All Users on a Specific Computer</span></span>](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-51-package-for-all-users-on-a-specific-computer.md)

    -   [<span data-ttu-id="a927d-120">如何為特定使用者，將擴充點從 App-V 4.6 封裝移轉至 App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="a927d-120">How to Migrate Extension Points From an App-V 4.6 Package to App-V 5.1 for a Specific User</span></span>](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-51-for-a-specific-user.md)

    -   [<span data-ttu-id="a927d-121">如何轉換在舊版 App-V 中建立的套件</span><span class="sxs-lookup"><span data-stu-id="a927d-121">How to Convert a Package Created in a Previous Version of App-V</span></span>](how-to-convert-a-package-created-in-a-previous-version-of-app-v51.md)

6.  <span data-ttu-id="a927d-122">測試您的 App-v 5.1 套件是否成功，然後移除4.6 套件。</span><span class="sxs-lookup"><span data-stu-id="a927d-122">Test that your App-V 5.1 packages are successful, and then remove the 4.6 packages.</span></span> <span data-ttu-id="a927d-123">若要檢查用戶端電腦的使用者狀態，建議您使用[使用者體驗虛擬化](https://technet.microsoft.com/library/dn458947.aspx)或其他使用者環境管理工具。</span><span class="sxs-lookup"><span data-stu-id="a927d-123">To check the user state of your client computers, we recommend that you use [User Experience Virtualization](https://technet.microsoft.com/library/dn458947.aspx) or another user environment management tool.</span></span>

    <span data-ttu-id="a927d-124">您**有應用程式-V 的建議**嗎？</span><span class="sxs-lookup"><span data-stu-id="a927d-124">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="a927d-125">在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="a927d-125">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="a927d-126">有應用程式-V 問題嗎？</span><span class="sxs-lookup"><span data-stu-id="a927d-126">Got an App-V issue?</span></span>** <span data-ttu-id="a927d-127">使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="a927d-127">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="a927d-128">相關主題</span><span class="sxs-lookup"><span data-stu-id="a927d-128">Related topics</span></span>


[<span data-ttu-id="a927d-129">規劃從舊版 App-V 移轉</span><span class="sxs-lookup"><span data-stu-id="a927d-129">Planning for Migrating from a Previous Version of App-V</span></span>](planning-for-migrating-from-a-previous-version-of-app-v51.md)

[<span data-ttu-id="a927d-130">部署 App-V 5.1 排序器和用戶端</span><span class="sxs-lookup"><span data-stu-id="a927d-130">Deploying the App-V 5.1 Sequencer and Client</span></span>](deploying-the-app-v-51-sequencer-and-client.md)

 

 





