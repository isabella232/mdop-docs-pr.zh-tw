---
title: 建立 MED-V 工作區
description: 建立 MED-V 工作區
author: dansimp
ms.assetid: 9578bb99-8a09-44c1-b88f-538901f16ad3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 189da6b28515f0d234c8a258138a27be7a7375d2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810809"
---
# <span data-ttu-id="8d662-103">建立 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="8d662-103">Creating a MED-V Workspace</span></span>


<span data-ttu-id="8d662-104">MED-V 工作區是一種桌面環境，使用者可以在其中與 MED-V 提供的虛擬機器進行互動。</span><span class="sxs-lookup"><span data-stu-id="8d662-104">A MED-V workspace is the desktop environment in which end users interact with the virtual machine provided by MED-V.</span></span> <span data-ttu-id="8d662-105">系統管理員會建立並自訂 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="8d662-105">The MED-V workspace is created and customized by the administrator.</span></span> <span data-ttu-id="8d662-106">它是由影像和原則所組成，可定義 MED-V 工作區的規則和功能。</span><span class="sxs-lookup"><span data-stu-id="8d662-106">It consists of an image and the policy, which defines the rules and functionality of the MED-V workspace.</span></span> <span data-ttu-id="8d662-107">您可以建立多個 MED-V 工作區，每個都有自己的配置、設定及規則。</span><span class="sxs-lookup"><span data-stu-id="8d662-107">Multiple MED-V workspaces can be created, each customized with its own configuration, settings, and rules.</span></span> <span data-ttu-id="8d662-108">使用者、群組或多個使用者或群組可以與每個 MED-V 工作區建立關聯，因此，只有關聯使用者或群組的電腦能使用 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="8d662-108">A user, group, or multiple users or groups can be associated with each MED-V workspace, thereby making the MED-V workspace available only for the associated user's or group's computers.</span></span>

## <span data-ttu-id="8d662-109">如何新增 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="8d662-109">How to Add a MED-V Workspace</span></span>


**<span data-ttu-id="8d662-110">新增 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="8d662-110">To add a MED-V workspace</span></span>**

1.  <span data-ttu-id="8d662-111">按一下 [**原則**管理] 按鈕以開啟 [**原則**] 模組。</span><span class="sxs-lookup"><span data-stu-id="8d662-111">Click the **Policy** management button to open the **Policy** module.</span></span>

    <span data-ttu-id="8d662-112">**原則**模組是由左側的 [**工作區**] 功能表以及**一般**、**虛擬機器**、**部署**、**應用程式**、 **Web**、 **VM 設定**、**網路**和**效能**索引標籤組成。</span><span class="sxs-lookup"><span data-stu-id="8d662-112">The **Policy** module consists of the **Workspaces** menu on the left and the **General**, **Virtual Machine**, **Deployment**, **Applications**, **Web**, **VM Setup**, **Network**, and **Performance** tabs.</span></span>

2.  <span data-ttu-id="8d662-113">在 [**原則**] 功能表上，選取 [**新增工作區**]，或按一下 **[新增] 以建立**新的 med-v 工作區。</span><span class="sxs-lookup"><span data-stu-id="8d662-113">On the **Policy** menu, select **New Workspace**, or click **Add** to create a new MED-V workspace.</span></span>

3.  <span data-ttu-id="8d662-114">在 [**一般**] 索引標籤的 [**名稱**] 欄位中，輸入 med-v 工作區的名稱。</span><span class="sxs-lookup"><span data-stu-id="8d662-114">On the **General** tab, in the **Name** field, enter the name of the MED-V workspace.</span></span>

4.  <span data-ttu-id="8d662-115">在 [**描述**] 欄位中，輸入 med-v 工作區的描述。</span><span class="sxs-lookup"><span data-stu-id="8d662-115">In the **Description** field, enter a description for the MED-V workspace.</span></span>

5.  <span data-ttu-id="8d662-116">在 [**支援連絡人資訊**] 欄位中，輸入技術支援的連絡人資訊。</span><span class="sxs-lookup"><span data-stu-id="8d662-116">In the **Support contact info** field, enter the contact information for technical support.</span></span>

    <span data-ttu-id="8d662-117">如需有關設定 MED-V 工作區的詳細資訊，請參閱設定[Med-v 工作區原則](configuring-med-v-workspace-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="8d662-117">For more information about configuring a MED-V workspace, see [Configuring MED-V Workspace Policies](configuring-med-v-workspace-policies.md).</span></span>

## <span data-ttu-id="8d662-118">如何克隆 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="8d662-118">How to Clone a MED-V Workspace</span></span>


<span data-ttu-id="8d662-119">您可以將 MED-V 工作區克隆，以便建立與現有的 MED-V 工作區相同的 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="8d662-119">A MED-V workspace can be cloned so that you can create a MED-V workspace identical to an existing MED-V workspace.</span></span>

**<span data-ttu-id="8d662-120">若要克隆 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="8d662-120">To clone a MED-V workspace</span></span>**

1.  <span data-ttu-id="8d662-121">按一下要克隆的 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="8d662-121">Click the MED-V workspace to clone.</span></span>

2.  <span data-ttu-id="8d662-122">在 [**原則**] 功能表上，選取 [**克隆工作區**]。</span><span class="sxs-lookup"><span data-stu-id="8d662-122">On the **Policy** menu, select **Clone Workspace**.</span></span>

    <span data-ttu-id="8d662-123">即會建立新的 MED-V 工作區，並將其命名為「 &lt; 原始 med-v-V」工作區名稱 &gt; -2。</span><span class="sxs-lookup"><span data-stu-id="8d662-123">A new MED-V workspace is created with the name &lt;Original MED-V workspace name&gt; - 2.</span></span>

## <span data-ttu-id="8d662-124">如何刪除 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="8d662-124">How to Delete a MED-V Workspace</span></span>


**<span data-ttu-id="8d662-125">刪除 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="8d662-125">To delete a MED-V workspace</span></span>**

-   <span data-ttu-id="8d662-126">在**原則**模組中，在 [工作區] 窗格處於焦點時，按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="8d662-126">In the **Policy** module, while the workspace pane is in focus, click **Remove**.</span></span>

## <span data-ttu-id="8d662-127">相關主題</span><span class="sxs-lookup"><span data-stu-id="8d662-127">Related topics</span></span>


[<span data-ttu-id="8d662-128">使用 MED-V 管理主控台使用者介面</span><span class="sxs-lookup"><span data-stu-id="8d662-128">Using the MED-V Management Console User Interface</span></span>](using-the-med-v-management-console-user-interface.md)

 

 





