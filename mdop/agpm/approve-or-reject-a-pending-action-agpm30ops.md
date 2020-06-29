---
title: 核准或拒絕擱置動作
description: 核准或拒絕擱置動作
author: dansimp
ms.assetid: 6d78989a-b600-4876-9dd9-bc6207ff2ce7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5a787e032a441a8b33a48667afecfc98ec2a3642
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802141"
---
# <span data-ttu-id="5531d-103">核准或拒絕擱置動作</span><span class="sxs-lookup"><span data-stu-id="5531d-103">Approve or Reject a Pending Action</span></span>


<span data-ttu-id="5531d-104">核准者的核心職責是評估並核准或拒絕從編輯者或不具備完成這些動作許可權的檢閱者中，針對群組原則物件（GPO）建立、部署及刪除的要求。</span><span class="sxs-lookup"><span data-stu-id="5531d-104">The core responsibility of an Approver is to evaluate and then approve or reject requests for Group Policy Object (GPO) creation, deployment, and deletion from Editors or Reviewers who do not have permission to complete those actions.</span></span> <span data-ttu-id="5531d-105">報告可協助擁有者評估新版本的 GPO。</span><span class="sxs-lookup"><span data-stu-id="5531d-105">Reports can assist an Approver with evaluating a new version of a GPO.</span></span>

<span data-ttu-id="5531d-106">使用者帳戶必須有核准者或 AGPM 管理員（完全控制）角色或高級群組原則管理（AGPM）中的必要許可權，才能完成此程式。</span><span class="sxs-lookup"><span data-stu-id="5531d-106">A user account with the Approver or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="5531d-107">請參閱本主題中的「其他注意事項」中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="5531d-107">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="5531d-108">核准或拒絕擱置的要求</span><span class="sxs-lookup"><span data-stu-id="5531d-108">To approve or reject a pending request</span></span>**

1.  <span data-ttu-id="5531d-109">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="5531d-109">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="5531d-110">在 [**內容**] 索引標籤上，按一下 [**未決**] 索引標籤以顯示擱置中的 gpo。</span><span class="sxs-lookup"><span data-stu-id="5531d-110">On the **Contents** tab, click the **Pending** tab to display the pending GPOs.</span></span>

3.  <span data-ttu-id="5531d-111">以滑鼠右鍵按一下未決的 GPO，然後按一下 [**核准**] 或 [**拒絕**]。</span><span class="sxs-lookup"><span data-stu-id="5531d-111">Right-click a pending GPO, and then click either **Approve** or **Reject**.</span></span>

4.  <span data-ttu-id="5531d-112">如果是核准部署，請按一下 [**核准未決**作業] 對話方塊中的 [**高級**]，以查看 GPO 的連結。</span><span class="sxs-lookup"><span data-stu-id="5531d-112">If approving deployment, click **Advanced** in the **Approve Pending Operation** dialog box to review links to the GPO.</span></span> <span data-ttu-id="5531d-113">將滑鼠指標暫停在樹狀結構中的專案上，以顯示詳細資料。</span><span class="sxs-lookup"><span data-stu-id="5531d-113">Pause the mouse pointer on an item in the tree to display details.</span></span>

    -   <span data-ttu-id="5531d-114">根據預設，所有的 GPO 連結都會還原。</span><span class="sxs-lookup"><span data-stu-id="5531d-114">By default, all links to the GPO will be restored.</span></span>

    -   <span data-ttu-id="5531d-115">若要防止連結被還原，請清除該連結的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="5531d-115">To prevent a link from being restored, clear the check box for that link.</span></span>

    -   <span data-ttu-id="5531d-116">若要避免還原所有連結，請清除 [**部署 GPO** ] 對話方塊中的 [**還原連結**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="5531d-116">To prevent all links from being restored, clear the **Restore Links** check box in the **Deploy GPO** dialog box.</span></span>

5.  <span data-ttu-id="5531d-117">按一下 **[是**] 或 **[確定]** 以確認 [核准] 或 [拒絕] 待定的動作。</span><span class="sxs-lookup"><span data-stu-id="5531d-117">Click **Yes** or **OK** to confirm approval or rejection of the pending action.</span></span> <span data-ttu-id="5531d-118">如果您已核准要求，GPO 會移至適當的索引標籤，以執行動作。</span><span class="sxs-lookup"><span data-stu-id="5531d-118">If you have approved the request, the GPO is moved to the appropriate tab for the action performed.</span></span>

    <span data-ttu-id="5531d-119">**記事** 如果核准者的電子郵件地址包含在 [**網域\*\*\*\*委派**] 索引標籤上的 [收**件者電子郵件地址**] 欄位中，則當編輯者或檢閱者提交要求時，核准者會收到來自 AGPM 別名的電子郵件。</span><span class="sxs-lookup"><span data-stu-id="5531d-119">**Note** If an Approver's e-mail address is included in the **To e-mail address** field on the **Domain** **Delegation** tab, the Approver will receive e-mail from the AGPM alias when an Editor or Reviewer submits a request.</span></span>

     

### <span data-ttu-id="5531d-120">其他考量</span><span class="sxs-lookup"><span data-stu-id="5531d-120">Additional considerations</span></span>

-   <span data-ttu-id="5531d-121">根據預設，您必須是 [核准者] 或 [AGPM 管理員（完全控制）]，才能執行此程式。</span><span class="sxs-lookup"><span data-stu-id="5531d-121">By default, you must be an Approver or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="5531d-122">具體說來，您必須具備執行您要核准之要求所需的許可權。</span><span class="sxs-lookup"><span data-stu-id="5531d-122">Specifically, you must have the permissions required to perform the request that you are approving.</span></span>

### <span data-ttu-id="5531d-123">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="5531d-123">Additional references</span></span>

-   [<span data-ttu-id="5531d-124">執行核准者工作</span><span class="sxs-lookup"><span data-stu-id="5531d-124">Performing Approver Tasks</span></span>](performing-approver-tasks-agpm30ops.md)

 

 





