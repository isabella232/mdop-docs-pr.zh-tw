---
title: 如何建立連線群組
description: 如何建立連線群組
author: dansimp
ms.assetid: 221e2eed-7ebb-42e3-b3d6-11c37c0578e6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7f20b3e71c7c0b72d66700bbad945860112ffd03
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800567"
---
# <span data-ttu-id="b3f0f-103">如何建立連線群組</span><span class="sxs-lookup"><span data-stu-id="b3f0f-103">How to Create a Connection Group</span></span>


<span data-ttu-id="b3f0f-104">使用這些步驟來建立使用 App-v 管理主控台的連線群組。</span><span class="sxs-lookup"><span data-stu-id="b3f0f-104">Use these steps to create a connection group by using the App-V Management Console.</span></span> <span data-ttu-id="b3f0f-105">若要使用 PowerShell 來建立連線群組，請參閱[如何使用 powershell 在獨立電腦上管理連線群組](how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell51.md)。</span><span class="sxs-lookup"><span data-stu-id="b3f0f-105">To use PowerShell to create connection groups, see [How to Manage Connection Groups on a Stand-alone Computer by Using PowerShell](how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell51.md).</span></span>

<span data-ttu-id="b3f0f-106">當您將套件放在連線群組中時，其套件根路徑會合並在一起。</span><span class="sxs-lookup"><span data-stu-id="b3f0f-106">When you place packages in a connection group, their package root paths are merged.</span></span> <span data-ttu-id="b3f0f-107">如果您移除套件，則只有其餘的套件會維持合併的根。</span><span class="sxs-lookup"><span data-stu-id="b3f0f-107">If you remove packages, only the remaining packages maintain the merged root.</span></span>

**<span data-ttu-id="b3f0f-108">建立連線群組</span><span class="sxs-lookup"><span data-stu-id="b3f0f-108">To create a connection group</span></span>**

1.  <span data-ttu-id="b3f0f-109">在 App-V 5.1 管理主控台中，選取 [連線**群組**] 以顯示 [連線群組] 程式庫。</span><span class="sxs-lookup"><span data-stu-id="b3f0f-109">In the App-V 5.1 Management Console, select **CONNECTION GROUPS** to display the Connection Groups library.</span></span>

2.  <span data-ttu-id="b3f0f-110">選取 [**新增連接群組**] 來建立新的連線群組。</span><span class="sxs-lookup"><span data-stu-id="b3f0f-110">Select **ADD CONNECTION GROUP** to create a new connection group.</span></span>

3.  <span data-ttu-id="b3f0f-111">在 [**新增**連線] 群組窗格中，輸入群組的描述。</span><span class="sxs-lookup"><span data-stu-id="b3f0f-111">In the **New Connection Group** pane, type a description for the group.</span></span>

4.  <span data-ttu-id="b3f0f-112">按一下 [連結的**套件**] 窗格中的 [**編輯**]，將新的應用程式新增至連線群組。</span><span class="sxs-lookup"><span data-stu-id="b3f0f-112">Click **EDIT** in the **CONNECTED PACKAGES** pane to add a new application to the connection group.</span></span>

5.  <span data-ttu-id="b3f0f-113">在 [**封裝整個文件庫**] 窗格中，選取要新增的應用程式，然後按一下箭號以新增應用程式。</span><span class="sxs-lookup"><span data-stu-id="b3f0f-113">In the **PACKAGES Entire Library** pane, select the application to be added, and click the arrow to add the application.</span></span>

    <span data-ttu-id="b3f0f-114">若要移除應用程式，請在 [**套件**] 窗格中選取要移除的應用程式，然後按一下箭號。</span><span class="sxs-lookup"><span data-stu-id="b3f0f-114">To remove an application, select the application to be removed in the **PACKAGES IN** pane and click the arrow.</span></span>

    <span data-ttu-id="b3f0f-115">若要重設連線群組中的應用程式的優先順序，請使用 [**套件**] 窗格中的箭號。</span><span class="sxs-lookup"><span data-stu-id="b3f0f-115">To reprioritize the applications in your connection group, use the arrows in the **PACKAGES IN** pane.</span></span>

    <span data-ttu-id="b3f0f-116">**重要** 根據預設，與特定應用程式相關聯的 Active Directory 網域服務存取設定並不會新增到連線群組中。</span><span class="sxs-lookup"><span data-stu-id="b3f0f-116">**Important** By default, the Active Directory Domain Services access configurations that are associated with a specific application are not added to the connection group.</span></span> <span data-ttu-id="b3f0f-117">若要轉移 Active Directory 存取設定，請選取 [**新增套件存取權至群組存取**]，該群組位於 [套件] 窗格**中**。</span><span class="sxs-lookup"><span data-stu-id="b3f0f-117">To transfer the Active Directory access configuration, select **ADD PACKAGE ACCESS TO GROUP ACCESS**, which is located in the **PACKAGES IN** pane.</span></span>

     

6.  <span data-ttu-id="b3f0f-118">在新增所有應用程式並設定 Active Directory 存取之後，**按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="b3f0f-118">After adding all the applications and configuring Active Directory access, click **Apply**.</span></span>

    <span data-ttu-id="b3f0f-119">您**有應用程式-V 的建議**嗎？</span><span class="sxs-lookup"><span data-stu-id="b3f0f-119">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="b3f0f-120">在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="b3f0f-120">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="b3f0f-121">有應用程式-V 問題嗎？</span><span class="sxs-lookup"><span data-stu-id="b3f0f-121">Got an App-V issue?</span></span>** <span data-ttu-id="b3f0f-122">使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="b3f0f-122">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="b3f0f-123">相關主題</span><span class="sxs-lookup"><span data-stu-id="b3f0f-123">Related topics</span></span>


[<span data-ttu-id="b3f0f-124">App-V 5.1 作業</span><span class="sxs-lookup"><span data-stu-id="b3f0f-124">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

[<span data-ttu-id="b3f0f-125">管理連線群組</span><span class="sxs-lookup"><span data-stu-id="b3f0f-125">Managing Connection Groups</span></span>](managing-connection-groups51.md)

 

 





