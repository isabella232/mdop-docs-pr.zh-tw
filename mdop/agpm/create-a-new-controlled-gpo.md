---
title: 建立新的受控制 GPO
description: 建立新的受控制 GPO
author: dansimp
ms.assetid: b43ce0f4-4519-4278-83c4-c7d5163ddd11
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0a64e22036bfe99e1d5012d732e3f2e081acdcca
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802878"
---
# <span data-ttu-id="42dbc-103">建立新的受控制 GPO</span><span class="sxs-lookup"><span data-stu-id="42dbc-103">Create a New Controlled GPO</span></span>


<span data-ttu-id="42dbc-104">透過**變更控制**節點建立的新群組原則物件（gpo）會自動受到控制，讓您使用高級的群組原則管理（AGPM）來管理它們。</span><span class="sxs-lookup"><span data-stu-id="42dbc-104">New Group Policy objects (GPOs) created through the **Change Control** node will automatically be controlled, enabling you to manage them with Advanced Group Policy Management (AGPM).</span></span>

<span data-ttu-id="42dbc-105">使用者帳戶必須有核准者或 AGPM 系統管理員（完全控制）角色，或高級群組原則管理中的必要許可權，才能完成此程式。</span><span class="sxs-lookup"><span data-stu-id="42dbc-105">A user account with the Approver or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management is required to complete this procedure.</span></span> <span data-ttu-id="42dbc-106">請參閱本主題中的「其他注意事項」中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="42dbc-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="42dbc-107">若要建立透過 AGPM 管理變更控制的新 GPO</span><span class="sxs-lookup"><span data-stu-id="42dbc-107">To create a new GPO with change control managed through AGPM</span></span>**

1.  <span data-ttu-id="42dbc-108">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="42dbc-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="42dbc-109">以滑鼠右鍵按一下 [**變更控制**] 節點，然後按一下 [**新增受控制的 GPO**]。</span><span class="sxs-lookup"><span data-stu-id="42dbc-109">Right-click the **Change Control** node, and then click **New Controlled GPO**.</span></span>

3.  <span data-ttu-id="42dbc-110">在 [**新的受控 GPO** ] 對話方塊中：</span><span class="sxs-lookup"><span data-stu-id="42dbc-110">In the **New Controlled GPO** dialog box:</span></span>

    1.  <span data-ttu-id="42dbc-111">輸入新 GPO 的名稱。</span><span class="sxs-lookup"><span data-stu-id="42dbc-111">Type a name for the new GPO.</span></span>

    2.  <span data-ttu-id="42dbc-112">[選用]：輸入要在 GPO 的 [歷程**記錄**] 中顯示的新 GPO 的批註。</span><span class="sxs-lookup"><span data-stu-id="42dbc-112">Optional: Type a comment for the new GPO to be displayed in the **History** for the GPO.</span></span>

    3.  <span data-ttu-id="42dbc-113">若要將新的 GPO 立即部署到生產環境，請按一下 [**建立 live**]。</span><span class="sxs-lookup"><span data-stu-id="42dbc-113">To immediately deploy the new GPO to the production environment, click **Create live**.</span></span> <span data-ttu-id="42dbc-114">若要在不立即部署的情況下建立新的 GPO，請按一下 [**離線建立**]。</span><span class="sxs-lookup"><span data-stu-id="42dbc-114">To create the new GPO offline without immediately deploying it, click **Create offline**.</span></span>

    4.  <span data-ttu-id="42dbc-115">選取要用來做為新 GPO 起點的 GPO 範本。</span><span class="sxs-lookup"><span data-stu-id="42dbc-115">Select the GPO template to use as a starting point for the new GPO.</span></span>

    5.  <span data-ttu-id="42dbc-116">按一下 \[確定\] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="42dbc-116">Click **OK**.</span></span>

4.  <span data-ttu-id="42dbc-117">當**進度**視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="42dbc-117">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="42dbc-118">新的 GPO 會顯示在 [**受控**] 索引標籤的 [gpo] 清單中。</span><span class="sxs-lookup"><span data-stu-id="42dbc-118">The new GPO is displayed in the list of GPOs on the **Controlled** tab.</span></span>

### <span data-ttu-id="42dbc-119">其他考量</span><span class="sxs-lookup"><span data-stu-id="42dbc-119">Additional considerations</span></span>

-   <span data-ttu-id="42dbc-120">根據預設，您必須是 [核准者] 或 [AGPM 管理員（完全控制）]，才能執行此程式。</span><span class="sxs-lookup"><span data-stu-id="42dbc-120">By default, you must be an Approver or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="42dbc-121">具體說來，您必須擁有**清單內容**，並為網域**建立 GPO**許可權。</span><span class="sxs-lookup"><span data-stu-id="42dbc-121">Specifically, you must have **List Contents** and **Create GPO** permissions for the domain.</span></span>

### <span data-ttu-id="42dbc-122">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="42dbc-122">Additional references</span></span>

-   [<span data-ttu-id="42dbc-123">建立、控制或匯入 GPO</span><span class="sxs-lookup"><span data-stu-id="42dbc-123">Creating, Controlling, or Importing a GPO</span></span>](creating-controlling-or-importing-a-gpo-approver.md)

 

 





