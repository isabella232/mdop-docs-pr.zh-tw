---
title: 如何使用 Management Console 自訂特定 AD 群組的虛擬應用程式延伸模組
description: 如何使用 Management Console 自訂特定 AD 群組的虛擬應用程式延伸模組
author: dansimp
ms.assetid: dd71df05-512f-4eb4-a55f-e5b93601323d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3bf086da3fbb6938a4fc602af5ab63adb1621532
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800548"
---
# <span data-ttu-id="e5ce6-103">如何使用 Management Console 自訂特定 AD 群組的虛擬應用程式延伸模組</span><span class="sxs-lookup"><span data-stu-id="e5ce6-103">How to Customize Virtual Applications Extensions for a Specific AD Group by Using the Management Console</span></span>


<span data-ttu-id="e5ce6-104">使用下列程式來自訂 Active Directory （AD）群組的虛擬應用程式擴充功能。</span><span class="sxs-lookup"><span data-stu-id="e5ce6-104">Use the following procedure to customize the virtual application extensions for an Active Directory (AD) group.</span></span>

**<span data-ttu-id="e5ce6-105">自訂 AD 群組的虛擬應用程式擴充功能</span><span class="sxs-lookup"><span data-stu-id="e5ce6-105">To customize virtual applications extensions for an AD group</span></span>**

1.  <span data-ttu-id="e5ce6-106">若要查看您要設定的套件，請開啟 App-V 5.1 管理主控台。</span><span class="sxs-lookup"><span data-stu-id="e5ce6-106">To view the package that you want to configure, open the App-V 5.1 Management Console.</span></span> <span data-ttu-id="e5ce6-107">若要查看指派給特定使用者群組的設定，請選取該套件，然後以滑鼠右鍵按一下套件名稱，然後選取 [**編輯 active directory 存取**]。</span><span class="sxs-lookup"><span data-stu-id="e5ce6-107">To view the configuration that is assigned to a given user group, select the package, and right-click the package name and select **Edit active directory access**.</span></span> <span data-ttu-id="e5ce6-108">或者，選取套件，然後按一下 [ **AD 存取**] 窗格中的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="e5ce6-108">Alternatively, select the package and click **EDIT** in the **AD ACCESS** pane.</span></span>

2.  <span data-ttu-id="e5ce6-109">若要自訂 AD 群組，您可以在**擁有 Access 的 AD 實體**清單中找到該群組。</span><span class="sxs-lookup"><span data-stu-id="e5ce6-109">To customize an AD group, you can find the group from the list of **AD Entities with Access**.</span></span> <span data-ttu-id="e5ce6-110">接著，使用 [**指派**的設定] 窗格中的下拉式方塊，選取 [**自訂**]，然後按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="e5ce6-110">Then, using the drop-down box in the **Assigned Configuration** pane, select **Custom**, and then click **EDIT**.</span></span>

3.  <span data-ttu-id="e5ce6-111">若要停用指定應用程式的所有延伸，請清除 [**啟用**]。</span><span class="sxs-lookup"><span data-stu-id="e5ce6-111">To disable all extensions for a given application, clear **ENABLE**.</span></span>

    <span data-ttu-id="e5ce6-112">若要為選取的應用程式新增快捷方式，請在 [**快捷方式**] 窗格中以滑鼠右鍵按一下該應用程式，然後選取 [**新增快捷方式**]。</span><span class="sxs-lookup"><span data-stu-id="e5ce6-112">To add a new shortcut for the selected application, right-click the application in the **SHORTCUTS** pane, and select **Add new shortcut**.</span></span> <span data-ttu-id="e5ce6-113">若要移除快速鍵，請在 [**快捷方式**] 窗格中以滑鼠右鍵按一下應用程式，然後選取 [**移除快捷方式**]。</span><span class="sxs-lookup"><span data-stu-id="e5ce6-113">To remove a shortcut, right-click the application in the **SHORTCUTS** pane, and select **Remove Shortcut**.</span></span> <span data-ttu-id="e5ce6-114">若要編輯現有的快捷方式，請以滑鼠右鍵按一下該應用程式，然後選取 [**編輯快捷方式**]。</span><span class="sxs-lookup"><span data-stu-id="e5ce6-114">To edit an existing shortcut, right-click the application, and select **Edit Shortcut**.</span></span>

4.  <span data-ttu-id="e5ce6-115">若要查看任何其他應用程式延伸，請按一下 [**高級**]，然後按一下 [**匯出配置**]。</span><span class="sxs-lookup"><span data-stu-id="e5ce6-115">To view any other application extensions, click **Advanced**, and click **Export Configuration**.</span></span> <span data-ttu-id="e5ce6-116">輸入檔案名，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="e5ce6-116">Type in a filename and click **Save**.</span></span> <span data-ttu-id="e5ce6-117">您可以使用設定檔來查看與套件關聯的所有應用程式延伸。</span><span class="sxs-lookup"><span data-stu-id="e5ce6-117">You can view all application extensions that are associated with the package using the configuration file.</span></span>

5.  <span data-ttu-id="e5ce6-118">若要編輯其他應用程式擴充功能，請修改設定檔，然後按一下 [匯**入並覆寫此**設定]。</span><span class="sxs-lookup"><span data-stu-id="e5ce6-118">To edit additional application extensions, modify the configuration file and click **Import and Overwrite this Configuration**.</span></span> <span data-ttu-id="e5ce6-119">選取已修改的檔案，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="e5ce6-119">Select the modified file and click **Open**.</span></span> <span data-ttu-id="e5ce6-120">在對話方塊中，按一下 [**覆寫**] 以完成處理常式。</span><span class="sxs-lookup"><span data-stu-id="e5ce6-120">In the dialog, click **Overwrite** to complete the process.</span></span>

    <span data-ttu-id="e5ce6-121">您**有應用程式-V 的建議**嗎？</span><span class="sxs-lookup"><span data-stu-id="e5ce6-121">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="e5ce6-122">在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="e5ce6-122">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="e5ce6-123">有應用程式-V 問題嗎？</span><span class="sxs-lookup"><span data-stu-id="e5ce6-123">Got an App-V issue?</span></span>** <span data-ttu-id="e5ce6-124">使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="e5ce6-124">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="e5ce6-125">相關主題</span><span class="sxs-lookup"><span data-stu-id="e5ce6-125">Related topics</span></span>


[<span data-ttu-id="e5ce6-126">App-V 5.1 作業</span><span class="sxs-lookup"><span data-stu-id="e5ce6-126">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

 

 





