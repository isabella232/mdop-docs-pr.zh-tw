---
title: 刪除受控制的 GPO
description: 刪除受控制的 GPO
author: dansimp
ms.assetid: f51c1737-c116-4faf-a6f6-c72303f60a3b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 365554d90ac13d749508edbc84dacd432ac4ceec
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801926"
---
# <span data-ttu-id="e16b3-103">刪除受控制的 GPO</span><span class="sxs-lookup"><span data-stu-id="e16b3-103">Delete a Controlled GPO</span></span>


<span data-ttu-id="e16b3-104">核准者可以刪除受控制的群組原則物件（GPO），將其移至 [回收站]。</span><span class="sxs-lookup"><span data-stu-id="e16b3-104">Approvers can delete a controlled Group Policy Object (GPO), moving it to the Recycle Bin.</span></span>

<span data-ttu-id="e16b3-105">使用者帳戶必須有核准者或 AGPM 管理員（完全控制）角色或高級群組原則管理（AGPM）中的必要許可權，才能完成此程式。</span><span class="sxs-lookup"><span data-stu-id="e16b3-105">A user account with the Approver or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="e16b3-106">請參閱本主題中的「其他注意事項」中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="e16b3-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="e16b3-107">刪除受控制的 GPO</span><span class="sxs-lookup"><span data-stu-id="e16b3-107">To delete a controlled GPO</span></span>**

1.  <span data-ttu-id="e16b3-108">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="e16b3-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="e16b3-109">在 [**內容**] 索引標籤上，按一下 [**受控**] 索引標籤以顯示受控制的 gpo。</span><span class="sxs-lookup"><span data-stu-id="e16b3-109">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

3.  <span data-ttu-id="e16b3-110">以滑鼠右鍵按一下您要刪除的 GPO，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="e16b3-110">Right-click the GPO you want to delete, and then click **Delete**.</span></span>

    -   <span data-ttu-id="e16b3-111">若要將 GPO 從封存中刪除，但在生產環境中保持不變的 GPO 部署版本，請按一下 [**僅從封存刪除 gpo**]。</span><span class="sxs-lookup"><span data-stu-id="e16b3-111">To delete the GPO from the archive while leaving the deployed version of the GPO untouched in the production environment, click **Delete GPO from archive only**.</span></span>

    -   <span data-ttu-id="e16b3-112">若要從封存與生產環境中刪除 GPO，請按一下 [**從封存及生產刪除 gpo**]。</span><span class="sxs-lookup"><span data-stu-id="e16b3-112">To delete the GPO from both the archive and production environment, click **Delete GPO from archive and production**.</span></span>

4.  <span data-ttu-id="e16b3-113">輸入要顯示在 GPO 的審核追蹤中的批註，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="e16b3-113">Type a comment to be displayed in the audit trail for the GPO, and then click **OK**.</span></span>

5.  <span data-ttu-id="e16b3-114">當**進度**視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="e16b3-114">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="e16b3-115">該 GPO 隨即會從 [**受控**] 索引標籤中移除，並顯示在 [**回收站**] 索引標籤上，可供您還原或銷毀。</span><span class="sxs-lookup"><span data-stu-id="e16b3-115">The GPO is removed from the **Controlled** tab and is displayed on the **Recycle Bin** tab, where it can be restored or destroyed.</span></span> <span data-ttu-id="e16b3-116">如果 GPO 只是從封存中刪除，它也會顯示在 [無法**控制**] 索引標籤上。</span><span class="sxs-lookup"><span data-stu-id="e16b3-116">If the GPO was deleted only from the archive, it is also displayed on the **Uncontrolled** tab.</span></span>

### <span data-ttu-id="e16b3-117">其他考量</span><span class="sxs-lookup"><span data-stu-id="e16b3-117">Additional considerations</span></span>

-   <span data-ttu-id="e16b3-118">根據預設，您必須是 [核准者] 或 [AGPM 管理員（完全控制）]，才能執行此程式。</span><span class="sxs-lookup"><span data-stu-id="e16b3-118">By default, you must be an Approver or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="e16b3-119">具體說來，您必須擁有**清單內容**，並刪除 GPO 的**gpo**許可權。</span><span class="sxs-lookup"><span data-stu-id="e16b3-119">Specifically, you must have **List Contents** and **Delete GPO** permissions for the GPO.</span></span>

-   <span data-ttu-id="e16b3-120">若要從生產環境刪除不受管理的 GPO，而不需先進行控制，請在 [**群組原則管理] 主控台**中，按一下 [**樹林**]，按一下 [**網域**]，按一下 [ \*\* &lt; MyDomain &gt; **]，然後按一下 [**群群組原則物件\*\*</span><span class="sxs-lookup"><span data-stu-id="e16b3-120">To delete an uncontrolled GPO from the production environment without first controlling it, in the **Group Policy Management Console**, click **Forest**, click **Domains**, click **&lt;MyDomain&gt;**, and then click **Group Policy Objects**.</span></span> <span data-ttu-id="e16b3-121">以滑鼠右鍵按一下無法控制的 GPO，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="e16b3-121">Right-click the uncontrolled GPO, and then click **Delete**.</span></span>

### <span data-ttu-id="e16b3-122">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="e16b3-122">Additional references</span></span>

-   [<span data-ttu-id="e16b3-123">刪除、還原或摧毀 GPO</span><span class="sxs-lookup"><span data-stu-id="e16b3-123">Deleting, Restoring, or Destroying a GPO</span></span>](deleting-restoring-or-destroying-a-gpo-agpm30ops.md)

 

 





