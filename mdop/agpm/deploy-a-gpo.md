---
title: 部署 GPO
description: 部署 GPO
author: dansimp
ms.assetid: a0a3f292-e3ab-46ae-a0fd-d7b2b4ad8883
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a98bdd758937d86cf8c30c5abf0b49302d377360
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801921"
---
# <span data-ttu-id="155f2-103">部署 GPO</span><span class="sxs-lookup"><span data-stu-id="155f2-103">Deploy a GPO</span></span>


<span data-ttu-id="155f2-104">[高級群組原則管理（AGPM）] 可讓核准者將新的或已編輯的群組原則物件（GPO）部署到生產環境。</span><span class="sxs-lookup"><span data-stu-id="155f2-104">Advanced Group Policy Management (AGPM) enables an Approver to deploy a new or edited Group Policy object (GPO) to the production environment.</span></span> <span data-ttu-id="155f2-105">如需重新部署舊版 GPO 的相關資訊，請參閱[回滾到舊版的 gpo](roll-back-to-a-previous-version-of-a-gpo.md)。</span><span class="sxs-lookup"><span data-stu-id="155f2-105">For information about redeploying a previous version of a GPO, see [Roll Back to a Previous Version of a GPO](roll-back-to-a-previous-version-of-a-gpo.md).</span></span>

<span data-ttu-id="155f2-106">使用者帳戶必須有核准者或 AGPM 系統管理員（完全控制）角色，或高級群組原則管理中的必要許可權，才能完成此程式。</span><span class="sxs-lookup"><span data-stu-id="155f2-106">A user account with the Approver or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management is required to complete this procedure.</span></span> <span data-ttu-id="155f2-107">請參閱本主題中的「其他注意事項」中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="155f2-107">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="155f2-108">將 GPO 部署到生產環境</span><span class="sxs-lookup"><span data-stu-id="155f2-108">To deploy a GPO to the production environment</span></span>**

1.  <span data-ttu-id="155f2-109">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="155f2-109">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="155f2-110">在 [**內容**] 索引標籤上，按一下 [**受控**] 索引標籤以顯示受控制的 gpo。</span><span class="sxs-lookup"><span data-stu-id="155f2-110">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

3.  <span data-ttu-id="155f2-111">以滑鼠右鍵按一下要部署的 GPO，然後按一下 [**部署**]。</span><span class="sxs-lookup"><span data-stu-id="155f2-111">Right-click the GPO to be deployed and then click **Deploy**.</span></span>

4.  <span data-ttu-id="155f2-112">若要查看 GPO 的連結，請按一下 [**高級**]。</span><span class="sxs-lookup"><span data-stu-id="155f2-112">To review links to the GPO, click **Advanced**.</span></span> <span data-ttu-id="155f2-113">將滑鼠指標暫停在樹狀結構中的節點上，以顯示詳細資料。</span><span class="sxs-lookup"><span data-stu-id="155f2-113">Pause the mouse pointer on a node in the tree to display details.</span></span>

    -   <span data-ttu-id="155f2-114">根據預設，所有的 GPO 連結都會還原。</span><span class="sxs-lookup"><span data-stu-id="155f2-114">By default, all links to the GPO will be restored.</span></span>

    -   <span data-ttu-id="155f2-115">若要防止連結被還原，請清除該連結的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="155f2-115">To prevent a link from being restored, clear the check box for that link.</span></span>

    -   <span data-ttu-id="155f2-116">若要避免還原所有連結，請清除 [**部署 GPO** ] 對話方塊中的 [**還原連結**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="155f2-116">To prevent all links from being restored, clear the **Restore Links** check box in the **Deploy GPO** dialog box.</span></span>

5.  <span data-ttu-id="155f2-117">按一下 **\[是\]**。</span><span class="sxs-lookup"><span data-stu-id="155f2-117">Click **Yes**.</span></span> <span data-ttu-id="155f2-118">當**進度**視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="155f2-118">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span>

<span data-ttu-id="155f2-119">**記事** 若要確認是否已部署最新版本的 GPO，請在 [**受控**] 索引標籤上，按兩下該 gpo 以顯示其歷程**記錄**。</span><span class="sxs-lookup"><span data-stu-id="155f2-119">**Note** To verify whether the most recent version of a GPO has been deployed, on the **Controlled** tab, double-click the GPO to display its **History**.</span></span> <span data-ttu-id="155f2-120">在 GPO 的歷程**記錄**中，[ **State** ] （狀態）欄會指出 GPO 是否已部署。</span><span class="sxs-lookup"><span data-stu-id="155f2-120">In the **History** for the GPO, the **State** column indicates whether a GPO has been deployed.</span></span>

 

### <span data-ttu-id="155f2-121">其他考量</span><span class="sxs-lookup"><span data-stu-id="155f2-121">Additional considerations</span></span>

-   <span data-ttu-id="155f2-122">根據預設，您必須是 [核准者] 或 [AGPM 管理員（完全控制）]，才能執行此程式。</span><span class="sxs-lookup"><span data-stu-id="155f2-122">By default, you must be an Approver or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="155f2-123">具體說來，您必須擁有**清單內容**並**部署**gpo 的 gpo 許可權。</span><span class="sxs-lookup"><span data-stu-id="155f2-123">Specifically, you must have **List Contents** and **Deploy GPO** permissions for the GPO.</span></span>

### <span data-ttu-id="155f2-124">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="155f2-124">Additional references</span></span>

-   [<span data-ttu-id="155f2-125">執行核准者工作</span><span class="sxs-lookup"><span data-stu-id="155f2-125">Performing Approver Tasks</span></span>](performing-approver-tasks.md)

 

 





