---
title: 摧毀 GPO
description: 摧毀 GPO
author: dansimp
ms.assetid: d74941a3-beef-46cd-a4ca-80a324dcfadf
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5545918c417fce16bfc2369ebc6fc2199390adc6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801901"
---
# <span data-ttu-id="940e8-103">摧毀 GPO</span><span class="sxs-lookup"><span data-stu-id="940e8-103">Destroy a GPO</span></span>


<span data-ttu-id="940e8-104">[高級群組原則管理] （AGPM）可讓核准者銷毀群組原則物件（GPO），並將它從 [回收站] 中移除，然後將它永久刪除，使其無法再還原。</span><span class="sxs-lookup"><span data-stu-id="940e8-104">Advanced Group Policy Management (AGPM) enables Approvers to destroy a Group Policy object (GPO), removing it from the Recycle Bin and permanently deleting it so that it can no longer be restored.</span></span>

<span data-ttu-id="940e8-105">使用者帳戶必須有核准者或 AGPM 系統管理員（完全控制）角色，或高級群組原則管理中的必要許可權，才能完成此程式。</span><span class="sxs-lookup"><span data-stu-id="940e8-105">A user account with the Approver or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management is required to complete this procedure.</span></span> <span data-ttu-id="940e8-106">請參閱本主題中的「其他注意事項」中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="940e8-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="940e8-107">若要永久刪除 GPO，使其無法再還原</span><span class="sxs-lookup"><span data-stu-id="940e8-107">To permanently delete a GPO so it can no longer be restored</span></span>**

1.  <span data-ttu-id="940e8-108">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="940e8-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="940e8-109">在 [**內容**] 索引標籤上，按一下 [**回收站**] 索引標籤以顯示已刪除的 gpo。</span><span class="sxs-lookup"><span data-stu-id="940e8-109">On the **Contents** tab, click the **Recycle Bin** tab to display the deleted GPOs.</span></span>

3.  <span data-ttu-id="940e8-110">以滑鼠右鍵按一下要銷毀的 GPO，然後按一下 [**銷毀**]。</span><span class="sxs-lookup"><span data-stu-id="940e8-110">Right-click the GPO to destroy, and then click **Destroy**.</span></span>

4.  <span data-ttu-id="940e8-111">按一下 **[是]** 以確認您要從封存永久刪除選取的 GPO 及所有備份。</span><span class="sxs-lookup"><span data-stu-id="940e8-111">Click **Yes** to confirm that you want to permanently delete the selected GPO and all backups from the archive.</span></span>

5.  <span data-ttu-id="940e8-112">當**進度**視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="940e8-112">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="940e8-113">該 GPO 隨即會從 [**回收站**] 索引標籤中移除，且會永久刪除。</span><span class="sxs-lookup"><span data-stu-id="940e8-113">The GPO is removed from the **Recycle Bin** tab and is permanently deleted.</span></span>

### <span data-ttu-id="940e8-114">其他考量</span><span class="sxs-lookup"><span data-stu-id="940e8-114">Additional considerations</span></span>

-   <span data-ttu-id="940e8-115">根據預設，您必須是 [核准者] 或 [AGPM 管理員（完全控制）]，才能執行此程式。</span><span class="sxs-lookup"><span data-stu-id="940e8-115">By default, you must be an Approver or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="940e8-116">具體說來，您必須擁有**清單內容**，並刪除 GPO 的**gpo**許可權。</span><span class="sxs-lookup"><span data-stu-id="940e8-116">Specifically, you must have **List Contents** and **Delete GPO** permissions for the GPO.</span></span>

### <span data-ttu-id="940e8-117">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="940e8-117">Additional references</span></span>

-   [<span data-ttu-id="940e8-118">刪除、還原或摧毀 GPO</span><span class="sxs-lookup"><span data-stu-id="940e8-118">Deleting, Restoring, or Destroying a GPO</span></span>](deleting-restoring-or-destroying-a-gpo.md)

 

 





