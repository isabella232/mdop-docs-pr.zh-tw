---
ms.reviewer: ''
title: 如何從應用程式-V 5.0 應用程式使用 app-v 4.6 應用程式
description: 如何從應用程式-V 5.0 應用程式使用 app-v 4.6 應用程式
ms.assetid: 4e78cb32-9c8b-478e-ae8b-c474a7e42487
author: msfttracyp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/21/2016
ms.openlocfilehash: 8b29e861b97d18e427f6a8247a1f731be2dc0889
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800395"
---
# <span data-ttu-id="c8d1c-103">如何從應用程式-V 5.0 應用程式使用 app-v 4.6 應用程式</span><span class="sxs-lookup"><span data-stu-id="c8d1c-103">How to Use an App-V 4.6 Application From an App-V 5.0 Application</span></span>

<span data-ttu-id="c8d1c-104">*注意：*\* App-V 4.6 已退出主流支援。</span><span class="sxs-lookup"><span data-stu-id="c8d1c-104">*Note:*\* App-V 4.6 has exited Mainstream support.</span></span> <span data-ttu-id="c8d1c-105">下列適用于 App-v 4.6 SP3 套件。</span><span class="sxs-lookup"><span data-stu-id="c8d1c-105">The following applies to an App-V 4.6 SP3 package.</span></span>

<span data-ttu-id="c8d1c-106">在獨立用戶端上，使用下列程式來執行 app-v 4.6 應用程式與 App-v 5.0 應用程式。</span><span class="sxs-lookup"><span data-stu-id="c8d1c-106">Use the following procedure to run an App-V4.6 application with App-V 5.0 applications on a standalone client.</span></span>

**<span data-ttu-id="c8d1c-107">在獨立用戶端上執行應用程式</span><span class="sxs-lookup"><span data-stu-id="c8d1c-107">To run applications on a standalone client</span></span>**

1.  <span data-ttu-id="c8d1c-108">在您的環境中，選取兩個可以彼此開啟的應用程式。</span><span class="sxs-lookup"><span data-stu-id="c8d1c-108">Select two applications in your environment that can be opened from one another.</span></span> <span data-ttu-id="c8d1c-109">例如，Microsoft Outlook 和 Adobe Acrobat Reader。</span><span class="sxs-lookup"><span data-stu-id="c8d1c-109">For example, Microsoft Outlook and Adobe Acrobat Reader.</span></span> <span data-ttu-id="c8d1c-110">您可以存取使用 Adobe Acrobat 建立的電子郵件附件。</span><span class="sxs-lookup"><span data-stu-id="c8d1c-110">You can access an email attachment created using Adobe Acrobat.</span></span>

2.  <span data-ttu-id="c8d1c-111">轉換套件，或使用 App-v 5.0 格式，為其中一個應用程式建立新的套件。</span><span class="sxs-lookup"><span data-stu-id="c8d1c-111">Convert the packages, or create a new package for either of the applications using the App-V 5.0 format.</span></span> <span data-ttu-id="c8d1c-112">如需轉換套件的詳細資訊，請參閱[如何將應用程式 v 4.6 套件中的延伸點遷移到已轉換的應用程式-v 5.0 套件，以供特定電腦上的所有使用者使用](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-50-package-for-all-users-on-a-specific-computer.md)，或[如何將應用程式-v 4.6 套件中的延伸點遷移至特定使用者的 app-v 5.0](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-50-for-a-specific-user.md)。</span><span class="sxs-lookup"><span data-stu-id="c8d1c-112">For more information about converting packages see, [How to Migrate Extension Points From an App-V 4.6 Package to a Converted App-V 5.0 Package for All Users on a Specific Computer](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-50-package-for-all-users-on-a-specific-computer.md) or [How to Migrate Extension Points From an App-V 4.6 Package to App-V 5.0 for a Specific User](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-50-for-a-specific-user.md).</span></span>

3.  <span data-ttu-id="c8d1c-113">使用 App-v 5.0 管理主控台來新增和置備套件。</span><span class="sxs-lookup"><span data-stu-id="c8d1c-113">Add and provision the package using the App-V 5.0 management console.</span></span> <span data-ttu-id="c8d1c-114">如需新增及預配套件的詳細資訊，請參閱[如何使用管理主控台新增或升級套件](how-to-add-or-upgrade-packages-by-using-the-management-console-beta-gb18030.md)，以及[如何使用管理主控台設定對套件的存取權](how-to-configure-access-to-packages-by-using-the-management-console-50.md)。</span><span class="sxs-lookup"><span data-stu-id="c8d1c-114">For more information adding and provisioning packages see, [How to Add or Upgrade Packages by Using the Management Console](how-to-add-or-upgrade-packages-by-using-the-management-console-beta-gb18030.md) and [How to Configure Access to Packages by Using the Management Console](how-to-configure-access-to-packages-by-using-the-management-console-50.md).</span></span>

4.  <span data-ttu-id="c8d1c-115">已轉換的應用程式現在會使用 App-v 5.0 執行，您可以從另一個應用程式中開啟其中一個應用程式。</span><span class="sxs-lookup"><span data-stu-id="c8d1c-115">The converted application now runs using App-V 5.0 and you can open one application from the other.</span></span> <span data-ttu-id="c8d1c-116">例如，如果您已將 Microsoft Office 套件轉換成 App-v 5.0 套件，而 Adobe Acrobat 仍是以 App-v 4.6 套件的方式執行，您可以使用 Microsoft Outlook 開啟 Adobe Acrobat Reader 附件。</span><span class="sxs-lookup"><span data-stu-id="c8d1c-116">For example, if you converted a Microsoft Office package to an App-V 5.0 package and Adobe Acrobat is still running as an App-V4.6 package, you can open an Adobe Acrobat Reader attachment using Microsoft Outlook.</span></span>

    <span data-ttu-id="c8d1c-117">您**有應用程式-V 的建議**嗎？</span><span class="sxs-lookup"><span data-stu-id="c8d1c-117">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="c8d1c-118">在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="c8d1c-118">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="c8d1c-119">有應用程式-V 問題嗎？</span><span class="sxs-lookup"><span data-stu-id="c8d1c-119">Got an App-V issue?</span></span>** <span data-ttu-id="c8d1c-120">使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="c8d1c-120">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="c8d1c-121">相關主題</span><span class="sxs-lookup"><span data-stu-id="c8d1c-121">Related topics</span></span>


[<span data-ttu-id="c8d1c-122">App-V 5.0 作業</span><span class="sxs-lookup"><span data-stu-id="c8d1c-122">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

 

 








