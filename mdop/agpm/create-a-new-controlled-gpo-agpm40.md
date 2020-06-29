---
title: 建立新的受控制 GPO
description: 建立新的受控制 GPO
author: dansimp
ms.assetid: 5ce760f6-9f05-42b4-b787-7835ab8e324e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 67c6af686b9ba7254cdaf93bd2d294b2d5bbb681
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802881"
---
# <span data-ttu-id="2f22e-103">建立新的受控制 GPO</span><span class="sxs-lookup"><span data-stu-id="2f22e-103">Create a New Controlled GPO</span></span>


<span data-ttu-id="2f22e-104">透過**變更控制**資料夾建立的新群組原則物件（gpo）會自動受到控制，讓您可以管理它們。</span><span class="sxs-lookup"><span data-stu-id="2f22e-104">New Group Policy Objects (GPOs) created through the **Change Control** folder will automatically be controlled, enabling you to manage them.</span></span>

<span data-ttu-id="2f22e-105">使用者帳戶必須有核准者或 AGPM 管理員（完全控制）角色或高級群組原則管理（AGPM）中的必要許可權，才能完成此程式。</span><span class="sxs-lookup"><span data-stu-id="2f22e-105">A user account with the Approver or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="2f22e-106">請參閱本主題中的「其他注意事項」中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="2f22e-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="2f22e-107">若要建立透過 AGPM 管理變更控制的新 GPO</span><span class="sxs-lookup"><span data-stu-id="2f22e-107">To create a new GPO with change control managed through AGPM</span></span>**

1.  <span data-ttu-id="2f22e-108">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="2f22e-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="2f22e-109">以滑鼠右鍵按一下 [**變更控制**]，然後按一下 [**新增受控制的 GPO**]。</span><span class="sxs-lookup"><span data-stu-id="2f22e-109">Right-click **Change Control**, and then click **New Controlled GPO**.</span></span>

3.  <span data-ttu-id="2f22e-110">在 [**新的受控 GPO** ] 對話方塊中：</span><span class="sxs-lookup"><span data-stu-id="2f22e-110">In the **New Controlled GPO** dialog box:</span></span>

    1.  <span data-ttu-id="2f22e-111">輸入新 GPO 的名稱。</span><span class="sxs-lookup"><span data-stu-id="2f22e-111">Type a name for the new GPO.</span></span>

    2.  <span data-ttu-id="2f22e-112">[選用]：輸入要在 GPO 的 [歷程**記錄**] 中顯示的新 GPO 的批註。</span><span class="sxs-lookup"><span data-stu-id="2f22e-112">Optional: Type a comment for the new GPO to be displayed in the **History** for the GPO.</span></span>

    3.  <span data-ttu-id="2f22e-113">若要將新的 GPO 立即部署到網域的生產環境中，請按一下 [**建立 live**]。</span><span class="sxs-lookup"><span data-stu-id="2f22e-113">To immediately deploy the new GPO to the production environment of the domain, click **Create live**.</span></span> <span data-ttu-id="2f22e-114">若要在不立即部署的情況下建立新的 GPO，請按一下 [**離線建立**]。</span><span class="sxs-lookup"><span data-stu-id="2f22e-114">To create the new GPO offline without immediately deploying it, click **Create offline**.</span></span>

    4.  <span data-ttu-id="2f22e-115">選取要用來做為新 GPO 起點的 GPO 範本，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="2f22e-115">Select the GPO template to use as a starting point for the new GPO, and then click **OK**.</span></span>

4.  <span data-ttu-id="2f22e-116">當**進度**視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="2f22e-116">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="2f22e-117">新的 GPO 會顯示在 [**受控**] 索引標籤的 [gpo] 清單中。</span><span class="sxs-lookup"><span data-stu-id="2f22e-117">The new GPO is displayed in the list of GPOs on the **Controlled** tab.</span></span>

### <span data-ttu-id="2f22e-118">其他考量</span><span class="sxs-lookup"><span data-stu-id="2f22e-118">Additional considerations</span></span>

-   <span data-ttu-id="2f22e-119">根據預設，您必須是 [核准者] 或 [AGPM 管理員（完全控制）]，才能執行此程式。</span><span class="sxs-lookup"><span data-stu-id="2f22e-119">By default, you must be an Approver or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="2f22e-120">具體說來，您必須擁有**清單內容**，並為網域**建立 GPO**許可權。</span><span class="sxs-lookup"><span data-stu-id="2f22e-120">Specifically, you must have **List Contents** and **Create GPO** permissions for the domain.</span></span>

### <span data-ttu-id="2f22e-121">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="2f22e-121">Additional references</span></span>

-   [<span data-ttu-id="2f22e-122">建立或控制 GPO</span><span class="sxs-lookup"><span data-stu-id="2f22e-122">Creating or Controlling a GPO</span></span>](creating-or-controlling-a-gpo-agpm40-app.md)

 

 





