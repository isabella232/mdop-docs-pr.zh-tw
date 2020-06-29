---
title: 如何使用 Management Console 設定對套件的存取權
description: 如何使用 Management Console 設定對套件的存取權
author: dansimp
ms.assetid: 8f4c91e4-f4e6-48cf-aa94-6085a054e8f7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0e1f5b51b118dc7b783a4a550e19fd39a61a0ab4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800589"
---
# <span data-ttu-id="fe548-103">如何使用 Management Console 設定對套件的存取權</span><span class="sxs-lookup"><span data-stu-id="fe548-103">How to Configure Access to Packages by Using the Management Console</span></span>


<span data-ttu-id="fe548-104">您必須先設定 Active Directory 網域服務（AD DS）安全性群組（可存取並執行應用程式），才能部署 app-v 5.0 虛擬化套件。</span><span class="sxs-lookup"><span data-stu-id="fe548-104">Before you deploy an App-V 5.0 virtualized package, you must configure the Active Directory Domain Services (AD DS) security groups that will be allowed to access and run the applications.</span></span> <span data-ttu-id="fe548-105">安全性群組可能包含電腦或使用者。</span><span class="sxs-lookup"><span data-stu-id="fe548-105">The security groups may contain computers or users.</span></span> <span data-ttu-id="fe548-106">Entitling 套件至電腦群組會將套件全域發佈到群組中的所有電腦。</span><span class="sxs-lookup"><span data-stu-id="fe548-106">Entitling a package to a computer group publishes the package globally to all computers in the group.</span></span>

<span data-ttu-id="fe548-107">使用下列程式設定虛擬化套件的存取權。</span><span class="sxs-lookup"><span data-stu-id="fe548-107">Use the following procedure to configure access to virtualized packages.</span></span>

**<span data-ttu-id="fe548-108">若要授與 app-v 5.0 套件的存取權</span><span class="sxs-lookup"><span data-stu-id="fe548-108">To grant access to an App-V 5.0 package</span></span>**

1.  <span data-ttu-id="fe548-109">尋找您要設定的套件：</span><span class="sxs-lookup"><span data-stu-id="fe548-109">Find the package you want to configure:</span></span>

    1.  <span data-ttu-id="fe548-110">開啟 App-V 5.0 管理主控台。</span><span class="sxs-lookup"><span data-stu-id="fe548-110">Open the App-V 5.0 Management console.</span></span>

    2.  <span data-ttu-id="fe548-111">若要顯示 [**廣告存取**] 頁面，請以滑鼠右鍵按一下要設定的套件，然後選取 [**編輯 active directory 存取**]。</span><span class="sxs-lookup"><span data-stu-id="fe548-111">To display the **AD ACCESS** page, right-click the package to be configured, and select **Edit active directory access**.</span></span> <span data-ttu-id="fe548-112">或者，選取套件，然後按一下 [ **AD 存取**] 窗格中的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="fe548-112">Alternatively, select the package and click **EDIT** in the **AD ACCESS** pane.</span></span>

2.  <span data-ttu-id="fe548-113">為套件提供安全性群組：</span><span class="sxs-lookup"><span data-stu-id="fe548-113">Provision a security group for the package:</span></span>

    1.  <span data-ttu-id="fe548-114">移至 [**尋找有效的 ACTIVE DIRECTORY 名稱並授與存取權**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="fe548-114">Go to the **FIND VALID ACTIVE DIRECTORY NAMES AND GRANT ACCESS** page.</span></span>

    2.  <span data-ttu-id="fe548-115">使用 [格式化**mydomain**  \\  **groupname**組名]，輸入 Active Directory 群組物件的名稱或部分名稱，然後按一下 [**檢查**]。</span><span class="sxs-lookup"><span data-stu-id="fe548-115">Using the format **mydomain** \\ **groupname**, type the name or part of the name of an Active Directory group object, and click **Check**.</span></span>

        <span data-ttu-id="fe548-116">**記事** 請確定您為您要搜尋的群組提供相關聯的功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="fe548-116">**Note** Ensure that you provide an associated domain name for the group that you are searching for.</span></span>

         

3.  <span data-ttu-id="fe548-117">若要授與對套件的存取權，請選取想要的群組，然後按一下 **[准許存取**]。</span><span class="sxs-lookup"><span data-stu-id="fe548-117">To grant access to the package, select the desired group and click **Grant Access**.</span></span> <span data-ttu-id="fe548-118">新新增的群組會顯示在擁有 [存取] 窗格的 [ **AD 實體**] 中。</span><span class="sxs-lookup"><span data-stu-id="fe548-118">The newly added group is displayed in the **AD ENTITIES WITH ACCESS** pane.</span></span>

4.  

    <span data-ttu-id="fe548-119">若要接受預設設定並關閉 [**廣告存取**] 頁面，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="fe548-119">To accept the default configuration settings and close the **AD ACCESS** page, click **Close**.</span></span>

    <span data-ttu-id="fe548-120">若要自訂特定群組的設定，請按一下 [**指派**的設定] 下拉式清單，然後選取 [**自訂**]。</span><span class="sxs-lookup"><span data-stu-id="fe548-120">To customize configurations for a specific group, click the **ASSIGNED CONFIGURATIONS** drop-down and select **Custom**.</span></span> <span data-ttu-id="fe548-121">若要設定自訂設定，請按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="fe548-121">To configure the custom configurations, click **EDIT**.</span></span> <span data-ttu-id="fe548-122">在您授與存取權之後，按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="fe548-122">After you grant access, click **Close**.</span></span>

**<span data-ttu-id="fe548-123">移除 App-v 5.0 套件的存取權</span><span class="sxs-lookup"><span data-stu-id="fe548-123">To remove access to an App-V 5.0 package</span></span>**

1.  <span data-ttu-id="fe548-124">尋找您要設定的套件：</span><span class="sxs-lookup"><span data-stu-id="fe548-124">Find the package you want to configure:</span></span>

    1.  <span data-ttu-id="fe548-125">開啟 App-V 5.0 管理主控台。</span><span class="sxs-lookup"><span data-stu-id="fe548-125">Open the App-V 5.0 Management console.</span></span>

    2.  <span data-ttu-id="fe548-126">若要顯示 [**廣告存取**] 頁面，請以滑鼠右鍵按一下要設定的套件，然後選取 [**編輯 active directory 存取**]。</span><span class="sxs-lookup"><span data-stu-id="fe548-126">To display the **AD ACCESS** page, right-click the package to be configured, and select **Edit active directory access**.</span></span> <span data-ttu-id="fe548-127">或者，選取套件，然後按一下 [ **AD 存取**] 窗格中的 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="fe548-127">Alternatively, select the package and click **EDIT** in the **AD ACCESS** pane.</span></span>

2.  <span data-ttu-id="fe548-128">選取您要移除的群組，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="fe548-128">Select the group you want to remove, and click **DELETE**.</span></span>

3.  <span data-ttu-id="fe548-129">若要關閉 [**廣告存取**] 頁面，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="fe548-129">To close the **AD ACCESS** page, click **Close**.</span></span>

    <span data-ttu-id="fe548-130">您**有應用程式-V 的建議**嗎？</span><span class="sxs-lookup"><span data-stu-id="fe548-130">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="fe548-131">在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="fe548-131">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="fe548-132">有應用程式-V 問題嗎？</span><span class="sxs-lookup"><span data-stu-id="fe548-132">Got an App-V issue?</span></span>** <span data-ttu-id="fe548-133">使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="fe548-133">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="fe548-134">相關主題</span><span class="sxs-lookup"><span data-stu-id="fe548-134">Related topics</span></span>


[<span data-ttu-id="fe548-135">App-V 5.0 作業</span><span class="sxs-lookup"><span data-stu-id="fe548-135">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

 

 





