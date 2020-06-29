---
title: 如何從應用程式-V 5.1 應用程式使用 app-v 4.6 應用程式
description: 如何從應用程式-V 5.1 應用程式使用 app-v 4.6 應用程式
author: dansimp
ms.assetid: 909b4391-762b-4988-b0cf-32b67f1fcf0e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: c0d308dcae33b02c089c101ffcd5041b2e665f59
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800393"
---
# <span data-ttu-id="aa1b4-103">如何從應用程式-V 5.1 應用程式使用 app-v 4.6 應用程式</span><span class="sxs-lookup"><span data-stu-id="aa1b4-103">How to Use an App-V 4.6 Application From an App-V 5.1 Application</span></span>

<span data-ttu-id="aa1b4-104">*注意：*\* App-V 4.6 已退出主流支援。</span><span class="sxs-lookup"><span data-stu-id="aa1b4-104">*Note:*\* App-V 4.6 has exited Mainstream support.</span></span> <span data-ttu-id="aa1b4-105">下列適用于 App-v 4.6 SP3 套件。</span><span class="sxs-lookup"><span data-stu-id="aa1b4-105">The following applies to an App-V 4.6 SP3 package.</span></span>

<span data-ttu-id="aa1b4-106">在獨立用戶端上，使用下列程式來執行 app-v 4.6 應用程式與 App-v 5.1 應用程式。</span><span class="sxs-lookup"><span data-stu-id="aa1b4-106">Use the following procedure to run an App-V4.6 application with App-V 5.1 applications on a standalone client.</span></span>

<span data-ttu-id="aa1b4-107">**記事** 這個程式假設您執行的是最新版本的 App-V 4.6。</span><span class="sxs-lookup"><span data-stu-id="aa1b4-107">**Note** This procedure assumes that you are running the latest version of App-V 4.6.</span></span>

**<span data-ttu-id="aa1b4-108">在獨立用戶端上執行應用程式</span><span class="sxs-lookup"><span data-stu-id="aa1b4-108">To run applications on a standalone client</span></span>**

1.  <span data-ttu-id="aa1b4-109">在您的環境中，選取兩個可以彼此開啟的應用程式。</span><span class="sxs-lookup"><span data-stu-id="aa1b4-109">Select two applications in your environment that can be opened from one another.</span></span> <span data-ttu-id="aa1b4-110">例如，Microsoft Outlook 和 Adobe Acrobat Reader。</span><span class="sxs-lookup"><span data-stu-id="aa1b4-110">For example, Microsoft Outlook and Adobe Acrobat Reader.</span></span> <span data-ttu-id="aa1b4-111">您可以存取使用 Adobe Acrobat 建立的電子郵件附件。</span><span class="sxs-lookup"><span data-stu-id="aa1b4-111">You can access an email attachment created using Adobe Acrobat.</span></span>

2.  <span data-ttu-id="aa1b4-112">轉換套件，或使用 App-v 5.1 格式，為其中一個應用程式建立新的套件。</span><span class="sxs-lookup"><span data-stu-id="aa1b4-112">Convert the packages, or create a new package for either of the applications using the App-V 5.1 format.</span></span> <span data-ttu-id="aa1b4-113">如需轉換套件的詳細資訊，請參閱[如何將應用程式 v 4.6 套件中的延伸點遷移到已轉換的應用程式-v 5.1 套件，以供特定電腦上的所有使用者使用](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-51-package-for-all-users-on-a-specific-computer.md)，或[如何將應用程式-v 4.6 套件中的延伸點遷移至特定使用者的 app-v 5.1](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-51-for-a-specific-user.md)。</span><span class="sxs-lookup"><span data-stu-id="aa1b4-113">For more information about converting packages see, [How to Migrate Extension Points From an App-V 4.6 Package to a Converted App-V 5.1 Package for All Users on a Specific Computer](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-51-package-for-all-users-on-a-specific-computer.md) or [How to Migrate Extension Points From an App-V 4.6 Package to App-V 5.1 for a Specific User](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-51-for-a-specific-user.md).</span></span>

3.  <span data-ttu-id="aa1b4-114">使用 App-v 5.1 管理主控台來新增和置備套件。</span><span class="sxs-lookup"><span data-stu-id="aa1b4-114">Add and provision the package using the App-V 5.1 management console.</span></span> <span data-ttu-id="aa1b4-115">如需新增及預配套件的詳細資訊，請參閱[如何使用管理主控台新增或升級套件](how-to-add-or-upgrade-packages-by-using-the-management-console-51-gb18030.md)，以及[如何使用管理主控台設定對套件的存取權](how-to-configure-access-to-packages-by-using-the-management-console-51.md)。</span><span class="sxs-lookup"><span data-stu-id="aa1b4-115">For more information adding and provisioning packages see, [How to Add or Upgrade Packages by Using the Management Console](how-to-add-or-upgrade-packages-by-using-the-management-console-51-gb18030.md) and [How to Configure Access to Packages by Using the Management Console](how-to-configure-access-to-packages-by-using-the-management-console-51.md).</span></span>

4.  <span data-ttu-id="aa1b4-116">已轉換的應用程式現在會使用 App-v 5.1 執行，您可以從另一個應用程式中開啟其中一個應用程式。</span><span class="sxs-lookup"><span data-stu-id="aa1b4-116">The converted application now runs using App-V 5.1 and you can open one application from the other.</span></span> <span data-ttu-id="aa1b4-117">例如，如果您已將 Microsoft Office 套件轉換成 App-v 5.1 套件，而 Adobe Acrobat 仍是以 App-v 4.6 套件的方式執行，您可以使用 Microsoft Outlook 開啟 Adobe Acrobat Reader 附件。</span><span class="sxs-lookup"><span data-stu-id="aa1b4-117">For example, if you converted a Microsoft Office package to an App-V 5.1 package and Adobe Acrobat is still running as an App-V4.6 package, you can open an Adobe Acrobat Reader attachment using Microsoft Outlook.</span></span>

    <span data-ttu-id="aa1b4-118">您**有應用程式-V 的建議**嗎？</span><span class="sxs-lookup"><span data-stu-id="aa1b4-118">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="aa1b4-119">在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="aa1b4-119">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="aa1b4-120">有應用程式-V 問題嗎？</span><span class="sxs-lookup"><span data-stu-id="aa1b4-120">Got an App-V issue?</span></span>** <span data-ttu-id="aa1b4-121">使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="aa1b4-121">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="aa1b4-122">相關主題</span><span class="sxs-lookup"><span data-stu-id="aa1b4-122">Related topics</span></span>


[<span data-ttu-id="aa1b4-123">App-V 5.1 作業</span><span class="sxs-lookup"><span data-stu-id="aa1b4-123">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

 

 





