---
title: 如何在同一部電腦上部署 app-v 4.6 和 App-v 5.0 用戶端
description: 如何在同一部電腦上部署 app-v 4.6 和 App-v 5.0 用戶端
ms.assetid: 5b7e27e4-4360-464c-b832-f1c7939e5485
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
author: dansimp
ms.date: 06/21/2016
ms.openlocfilehash: 38e77ce6ce6c0dba7c67f6c0dfa5c9e263e07e20
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800529"
---
# <span data-ttu-id="f026b-103">如何在同一部電腦上部署 app-v 4.6 和 App-v 5.0 用戶端</span><span class="sxs-lookup"><span data-stu-id="f026b-103">How to Deploy the App-V 4.6 and the App-V 5.0 Client on the Same Computer</span></span>

<span data-ttu-id="f026b-104">**注意：** App-V 4.6 已退出主流支援。</span><span class="sxs-lookup"><span data-stu-id="f026b-104">**Note:** App-V 4.6 has exited Mainstream support.</span></span> <span data-ttu-id="f026b-105">下列假設已安裝 app-v 4.6 SP3 用戶端。</span><span class="sxs-lookup"><span data-stu-id="f026b-105">The following assumes that the App-V 4.6 SP3 client is already installed.</span></span>

<span data-ttu-id="f026b-106">使用下列資訊來安裝 App-v 5.0 用戶端（最好是使用最新的 Service Pack 和熱修復程式），並在同一部電腦上安裝 app-v 4.6 SP3 用戶端。</span><span class="sxs-lookup"><span data-stu-id="f026b-106">Use the following information to install the App-V 5.0 client (preferably, with the latest Service Packs and hotfixes) and the App-V 4.6SP3 client on the same computer.</span></span> <span data-ttu-id="f026b-107">如需支援的版本、需求及其他規劃資訊，請參閱[規劃從繼承應用程式遷移（V](planning-for-migrating-from-a-previous-version-of-app-v.md)）。</span><span class="sxs-lookup"><span data-stu-id="f026b-107">For supported versions, requirements, and other planning information, see [Planning for Migrating from a Previous Version of App-V](planning-for-migrating-from-a-previous-version-of-app-v.md).</span></span>

**<span data-ttu-id="f026b-108">在同一部電腦上部署 app-v 5.0 用戶端和 App-v 4.6 用戶端</span><span class="sxs-lookup"><span data-stu-id="f026b-108">To deploy the App-V 5.0 client and App-V 4.6 client on the same computer</span></span>**

1.  <span data-ttu-id="f026b-109">在執行 App-V 4.6 版的電腦上，安裝 app-v 5.0 SP3 用戶端。</span><span class="sxs-lookup"><span data-stu-id="f026b-109">Install the App-V 5.0 SP3 client on the computer that is running the App-V 4.6 version of the client.</span></span> <span data-ttu-id="f026b-110">為了獲得最佳結果，建議您將所有可用的更新安裝到 App-v 5.0 SP3 用戶端。</span><span class="sxs-lookup"><span data-stu-id="f026b-110">For best results, we recommend that you install all available updates to the App-V 5.0 SP3 client.</span></span>

2.  <span data-ttu-id="f026b-111">逐步轉換或重新排列套件。</span><span class="sxs-lookup"><span data-stu-id="f026b-111">Convert or re-sequence the packages gradually.</span></span>

    -   <span data-ttu-id="f026b-112">若要轉換套件，請使用 App-v 5.0 套件轉換器，並將所需的套件轉換成 App-v 5.0 （**appv**）檔案格式。</span><span class="sxs-lookup"><span data-stu-id="f026b-112">To convert the packages, use the App-V 5.0 package converter and convert the required packages to the App-V 5.0 (**.appv**) file format.</span></span>

    -   <span data-ttu-id="f026b-113">若要重新排列套件，請考慮使用最新版本的 Sequencer 來取得最佳結果。</span><span class="sxs-lookup"><span data-stu-id="f026b-113">To re-sequence the packages, consider using the latest version of the Sequencer for best results.</span></span>

    <span data-ttu-id="f026b-114">如需發佈套件的詳細資訊，請參閱[如何使用管理主控台發佈套件](how-to-publish-a-package-by-using-the-management-console-50.md)。</span><span class="sxs-lookup"><span data-stu-id="f026b-114">For more information about publishing packages, see [How to Publish a Package by Using the Management Console](how-to-publish-a-package-by-using-the-management-console-50.md).</span></span>

3.  <span data-ttu-id="f026b-115">將套件部署到用戶端電腦。</span><span class="sxs-lookup"><span data-stu-id="f026b-115">Deploy packages to the client computers.</span></span>

4.  <span data-ttu-id="f026b-116">視需要轉換延伸點。</span><span class="sxs-lookup"><span data-stu-id="f026b-116">Convert extension points, as needed.</span></span> <span data-ttu-id="f026b-117">如需詳細資訊，請參閱下列資源：</span><span class="sxs-lookup"><span data-stu-id="f026b-117">For more information, see the following resources:</span></span>

    -   [<span data-ttu-id="f026b-118">如何為特定電腦上的所有使用者，將擴充點從 App-V 4.6 封裝移轉至轉換的 App-V 5.0 封裝</span><span class="sxs-lookup"><span data-stu-id="f026b-118">How to Migrate Extension Points From an App-V 4.6 Package to a Converted App-V 5.0 Package for All Users on a Specific Computer</span></span>](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-50-package-for-all-users-on-a-specific-computer.md)

    -   [<span data-ttu-id="f026b-119">如何為特定使用者，將擴充點從 App-V 4.6 封裝移轉至 App-V 5.0</span><span class="sxs-lookup"><span data-stu-id="f026b-119">How to Migrate Extension Points From an App-V 4.6 Package to App-V 5.0 for a Specific User</span></span>](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-50-for-a-specific-user.md)

    -   [<span data-ttu-id="f026b-120">如何轉換在舊版 App-V 中建立的套件</span><span class="sxs-lookup"><span data-stu-id="f026b-120">How to Convert a Package Created in a Previous Version of App-V</span></span>](how-to-convert-a-package-created-in-a-previous-version-of-app-v.md)

5.  <span data-ttu-id="f026b-121">測試您的 App-v 5.0 套件是否成功，然後移除4.6 套件。</span><span class="sxs-lookup"><span data-stu-id="f026b-121">Test that your App-V 5.0 packages are successful, and then remove the 4.6 packages.</span></span> <span data-ttu-id="f026b-122">若要檢查用戶端電腦的使用者狀態，建議您使用[使用者體驗虛擬化](https://technet.microsoft.com/library/dn458947.aspx)或其他使用者環境管理工具。</span><span class="sxs-lookup"><span data-stu-id="f026b-122">To check the user state of your client computers, we recommend that you use [User Experience Virtualization](https://technet.microsoft.com/library/dn458947.aspx) or another user environment management tool.</span></span>

    <span data-ttu-id="f026b-123">您**有應用程式-V 的建議**嗎？</span><span class="sxs-lookup"><span data-stu-id="f026b-123">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="f026b-124">在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="f026b-124">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="f026b-125">有應用程式-V 問題嗎？</span><span class="sxs-lookup"><span data-stu-id="f026b-125">Got an App-V issue?</span></span>** <span data-ttu-id="f026b-126">使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="f026b-126">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="f026b-127">相關主題</span><span class="sxs-lookup"><span data-stu-id="f026b-127">Related topics</span></span>


[<span data-ttu-id="f026b-128">規劃從舊版 App-V 移轉</span><span class="sxs-lookup"><span data-stu-id="f026b-128">Planning for Migrating from a Previous Version of App-V</span></span>](planning-for-migrating-from-a-previous-version-of-app-v.md)

[<span data-ttu-id="f026b-129">部署 App-V 5.0 排序器和用戶端</span><span class="sxs-lookup"><span data-stu-id="f026b-129">Deploying the App-V 5.0 Sequencer and Client</span></span>](deploying-the-app-v-50-sequencer-and-client.md)

 

 





