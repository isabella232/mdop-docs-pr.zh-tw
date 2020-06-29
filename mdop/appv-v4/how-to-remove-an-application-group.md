---
title: 如何移除應用程式群組
description: 如何移除應用程式群組
author: dansimp
ms.assetid: 3016b373-f5a0-4c82-96e8-e5e7960f0cc4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b392fe84f4318cf7f355de0c07e4d6f1f5108ed7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801154"
---
# <span data-ttu-id="ee60c-103">如何移除應用程式群組</span><span class="sxs-lookup"><span data-stu-id="ee60c-103">How to Remove an Application Group</span></span>


<span data-ttu-id="ee60c-104">您可以使用下列程式，以兩種方法的其中一種方式，在應用程式虛擬化伺服器管理主控台中移除應用程式群組：</span><span class="sxs-lookup"><span data-stu-id="ee60c-104">You can use the following procedures to remove an application group in the Application Virtualization Server Management Console in one of two ways:</span></span>

<span data-ttu-id="ee60c-105">**小心** 刪除擁有應用程式的群組會從應用程式虛擬化管理伺服器刪除那些應用程式。</span><span class="sxs-lookup"><span data-stu-id="ee60c-105">**Caution** Deleting a group with its applications deletes those applications from the Application Virtualization Management Server.</span></span> <span data-ttu-id="ee60c-106">當您嘗試這樣做時，您必須在快顯視窗中確認刪除。</span><span class="sxs-lookup"><span data-stu-id="ee60c-106">When you try to do this, you must confirm the deletion in a pop-up window.</span></span>

 

**<span data-ttu-id="ee60c-107">清空然後刪除應用程式群組</span><span class="sxs-lookup"><span data-stu-id="ee60c-107">To empty and then delete an application group</span></span>**

1.  <span data-ttu-id="ee60c-108">在應用程式虛擬化伺服器管理主控台中，展開左窗格中的 [**應用程式**]，然後選取您要移除的**應用程式**群組。</span><span class="sxs-lookup"><span data-stu-id="ee60c-108">In the Application Virtualization Server Management Console, expand **Applications** in the left pane and select the **Application** group you want to remove.</span></span>

2.  <span data-ttu-id="ee60c-109">在右窗格中，選取您想要保留的應用程式和應用程式群組。</span><span class="sxs-lookup"><span data-stu-id="ee60c-109">In the right pane, select the applications and application groups you want to keep.</span></span> <span data-ttu-id="ee60c-110">您可以使用**CTRL**和**Shift**鍵來選取多個應用程式和應用程式群組。</span><span class="sxs-lookup"><span data-stu-id="ee60c-110">You can use the **CTRL** and **Shift** keys to select multiple applications and application groups.</span></span>

3.  <span data-ttu-id="ee60c-111">以滑鼠右鍵按一下選取的應用程式，然後選擇 [**移動**]。</span><span class="sxs-lookup"><span data-stu-id="ee60c-111">Right-click the selected applications, and choose **Move**.</span></span>

4.  <span data-ttu-id="ee60c-112">在 [**選取目標**] 視窗中，流覽至新的位置，然後按一下 **[確定**]。</span><span class="sxs-lookup"><span data-stu-id="ee60c-112">In the **Select Target** window, navigate to the new location and click **OK**.</span></span> <span data-ttu-id="ee60c-113">如果您想要將不同的應用程式移至多個群組，請重複此步驟。</span><span class="sxs-lookup"><span data-stu-id="ee60c-113">Repeat this step if you want to move different applications to more than one group.</span></span>

5.  <span data-ttu-id="ee60c-114">當您移動完您想要保留的應用程式後，請以滑鼠右鍵按一下應用程式群組，然後選擇 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="ee60c-114">When you finish moving the applications you want to keep, right-click the application group and choose **Delete**.</span></span>

6.  <span data-ttu-id="ee60c-115">按一下 **[是]** 以進行確認。</span><span class="sxs-lookup"><span data-stu-id="ee60c-115">Click **Yes** to confirm.</span></span>

**<span data-ttu-id="ee60c-116">若要刪除群組及其所有子群組及其應用程式</span><span class="sxs-lookup"><span data-stu-id="ee60c-116">To delete the group, with all its child groups and its applications</span></span>**

1.  <span data-ttu-id="ee60c-117">在應用程式虛擬化伺服器管理主控台中，展開左窗格中的 [**應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="ee60c-117">In the Application Virtualization Server Management Console, expand **Applications** in the left pane.</span></span>

2.  <span data-ttu-id="ee60c-118">以滑鼠右鍵按一下您要移除的應用程式群組，然後選擇 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="ee60c-118">Right-click the application group you want to remove, and choose **Delete**.</span></span>

3.  <span data-ttu-id="ee60c-119">按一下 **[是]** 以進行確認。</span><span class="sxs-lookup"><span data-stu-id="ee60c-119">Click **Yes** to confirm.</span></span>

    <span data-ttu-id="ee60c-120">**記事** 您可以同時選取及移除多個應用程式群組。</span><span class="sxs-lookup"><span data-stu-id="ee60c-120">**Note** You can select and remove multiple application groups simultaneously.</span></span> <span data-ttu-id="ee60c-121">在右窗格中，使用**CTRL**按一下或**按住 Shift**鍵按一下按鍵組合來選取多個群組。</span><span class="sxs-lookup"><span data-stu-id="ee60c-121">In the right pane, use the **CTRL**-click or **Shift**-click key combinations to select more than one group.</span></span>

     

## <span data-ttu-id="ee60c-122">相關主題</span><span class="sxs-lookup"><span data-stu-id="ee60c-122">Related topics</span></span>


[<span data-ttu-id="ee60c-123">如何在伺服器管理主控台中管理應用程式群組</span><span class="sxs-lookup"><span data-stu-id="ee60c-123">How to Manage Application Groups in the Server Management Console</span></span>](how-to-manage-application-groups-in-the-server-management-console.md)

[<span data-ttu-id="ee60c-124">如何在伺服器管理主控台中管理應用程式</span><span class="sxs-lookup"><span data-stu-id="ee60c-124">How to Manage Applications in the Server Management Console</span></span>](how-to-manage-applications-in-the-server-management-console.md)

 

 





