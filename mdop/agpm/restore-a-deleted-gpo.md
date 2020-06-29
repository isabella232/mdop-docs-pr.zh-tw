---
title: 還原刪除的 GPO
description: 還原刪除的 GPO
author: dansimp
ms.assetid: e6953296-7b7d-4d1e-ad82-d4a23044cdd7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2cba097ecd651a91f828901d8115a7020d6da819
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801806"
---
# <span data-ttu-id="0c02e-103">還原刪除的 GPO</span><span class="sxs-lookup"><span data-stu-id="0c02e-103">Restore a Deleted GPO</span></span>


<span data-ttu-id="0c02e-104">[高級群組原則管理] （AGPM）可讓核准者從回收站還原已刪除的群組原則物件（GPO），並將其傳回封存。</span><span class="sxs-lookup"><span data-stu-id="0c02e-104">Advanced Group Policy Management (AGPM) enables Approvers to restore a deleted Group Policy object (GPO) from the Recycle Bin, returning it to the archive.</span></span>

<span data-ttu-id="0c02e-105">具有 [編輯者]、[核准者] 或 [AGPM 管理員（完全控制）] 角色或 [高級群組原則管理] 中的必要許可權的使用者帳戶必須完成此程式。</span><span class="sxs-lookup"><span data-stu-id="0c02e-105">A user account with the Editor, Approver, or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management is required to complete this procedure.</span></span> <span data-ttu-id="0c02e-106">請參閱本主題中的「其他注意事項」中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="0c02e-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="0c02e-107">還原已刪除的 GPO</span><span class="sxs-lookup"><span data-stu-id="0c02e-107">To restore a deleted GPO</span></span>**

1.  <span data-ttu-id="0c02e-108">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="0c02e-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="0c02e-109">在 [**內容**] 索引標籤上，按一下 [**回收站**] 索引標籤以顯示已刪除的 gpo。</span><span class="sxs-lookup"><span data-stu-id="0c02e-109">On the **Contents** tab, click the **Recycle Bin** tab to display the deleted GPOs.</span></span>

3.  <span data-ttu-id="0c02e-110">以滑鼠右鍵按一下要還原的 GPO，然後按一下 [**還原**]。</span><span class="sxs-lookup"><span data-stu-id="0c02e-110">Right-click the GPO to restore, and then click **Restore**.</span></span>

4.  <span data-ttu-id="0c02e-111">輸入要顯示在 GPO 歷程記錄中的批註，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="0c02e-111">Type a comment to be displayed in the history of the GPO, and then click **OK**.</span></span>

5.  <span data-ttu-id="0c02e-112">當**進度**視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="0c02e-112">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="0c02e-113">該 GPO 隨即會從 [**回收站**] 索引標籤中移除，並顯示在 [**受控**] 索引標籤上。</span><span class="sxs-lookup"><span data-stu-id="0c02e-113">The GPO is removed from the **Recycle Bin** tab and is displayed on the **Controlled** tab.</span></span>

<span data-ttu-id="0c02e-114">**記事** 如果 GPO 已從生產環境中刪除，則將其還原到封存後，就不會自動將它重新部署到生產環境。</span><span class="sxs-lookup"><span data-stu-id="0c02e-114">**Note** If a GPO was deleted from the production environment, restoring it to the archive will not automatically redeploy it to the production environment.</span></span> <span data-ttu-id="0c02e-115">若要將 GPO 傳回生產環境，請部署 GPO。</span><span class="sxs-lookup"><span data-stu-id="0c02e-115">To return the GPO to the production environment, deploy the GPO.</span></span> <span data-ttu-id="0c02e-116">如需詳細資訊，請參閱[部署 GPO](deploy-a-gpo.md)。</span><span class="sxs-lookup"><span data-stu-id="0c02e-116">For information, see [Deploy a GPO](deploy-a-gpo.md).</span></span>

 

### <span data-ttu-id="0c02e-117">其他考量</span><span class="sxs-lookup"><span data-stu-id="0c02e-117">Additional considerations</span></span>

-   <span data-ttu-id="0c02e-118">根據預設，您必須是編輯者、核准者或 AGPM 系統管理員（完全控制），才能執行此程式。</span><span class="sxs-lookup"><span data-stu-id="0c02e-118">By default, you must be an Editor, an Approver, or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="0c02e-119">具體說來，您必須擁有**清單內容**，並**編輯設定**、**部署 GPO**或刪除 gpo 的**gpo**許可權。</span><span class="sxs-lookup"><span data-stu-id="0c02e-119">Specifically, you must have **List Contents** and either **Edit Settings**, **Deploy GPO**, or **Delete GPO** permissions for the GPO.</span></span>

### <span data-ttu-id="0c02e-120">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="0c02e-120">Additional references</span></span>

-   [<span data-ttu-id="0c02e-121">刪除、還原或摧毀 GPO</span><span class="sxs-lookup"><span data-stu-id="0c02e-121">Deleting, Restoring, or Destroying a GPO</span></span>](deleting-restoring-or-destroying-a-gpo.md)

 

 





