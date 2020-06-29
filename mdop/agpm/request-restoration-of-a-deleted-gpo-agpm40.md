---
title: 要求還原刪除的 GPO
description: 要求還原刪除的 GPO
author: dansimp
ms.assetid: bac5ca3b-be47-49b5-bf1b-96280625fda8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 606690554ca1f813e1c20787bca59cfe2de6432d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802590"
---
# <span data-ttu-id="bff3a-103">要求還原刪除的 GPO</span><span class="sxs-lookup"><span data-stu-id="bff3a-103">Request Restoration of a Deleted GPO</span></span>


<span data-ttu-id="bff3a-104">除非您是 [核准者] 或 [AGPM 管理員（完全控制）]，否則您必須從 [回收站] 中要求還原已刪除的群組原則物件（GPO），才能將其傳回封存。</span><span class="sxs-lookup"><span data-stu-id="bff3a-104">Unless you are an Approver or an AGPM Administrator (Full Control), you must request the restoration of a deleted Group Policy Object (GPO) from the Recycle Bin to return it to the archive.</span></span>

<span data-ttu-id="bff3a-105">必須具備高級群組原則管理（AGPM）中具有編輯者角色或必要許可權的使用者帳戶，才能完成此程式。</span><span class="sxs-lookup"><span data-stu-id="bff3a-105">A user account with the Editor role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="bff3a-106">請參閱本主題中的「其他注意事項」中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="bff3a-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="bff3a-107">要求還原已刪除的 GPO</span><span class="sxs-lookup"><span data-stu-id="bff3a-107">To request the restoration of a deleted GPO</span></span>**

1.  <span data-ttu-id="bff3a-108">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="bff3a-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="bff3a-109">在 [**內容**] 索引標籤上，按一下 [**回收站**] 索引標籤以顯示已刪除的 gpo。</span><span class="sxs-lookup"><span data-stu-id="bff3a-109">On the **Contents** tab, click the **Recycle Bin** tab to display the deleted GPOs.</span></span>

3.  <span data-ttu-id="bff3a-110">以滑鼠右鍵按一下您要還原的 GPO，然後按一下 [**還原**]。</span><span class="sxs-lookup"><span data-stu-id="bff3a-110">Right-click the GPO you want to restore, and then click **Restore**.</span></span>

4.  <span data-ttu-id="bff3a-111">除非您有還原 Gpo 的特殊許可權，否則您必須提交已刪除 GPO 的還原要求。</span><span class="sxs-lookup"><span data-stu-id="bff3a-111">Unless you have special permission to restore GPOs, you must submit a request for restoration of the deleted GPO.</span></span> <span data-ttu-id="bff3a-112">若要接收申請的複本，請在 [**抄送**] 欄位中輸入您的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="bff3a-112">To receive a copy of the request, type your e-mail address in the **Cc** field.</span></span> <span data-ttu-id="bff3a-113">輸入要顯示在 GPO 的審核追蹤中的批註，然後按一下 [**提交**]。</span><span class="sxs-lookup"><span data-stu-id="bff3a-113">Type a comment to be displayed in the audit trail for the GPO, and then click **Submit**.</span></span>

5.  <span data-ttu-id="bff3a-114">當**進度**視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="bff3a-114">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="bff3a-115">該 GPO 隨即會從 [**回收站**] 索引標籤中移除，並顯示在 [**受控**] 索引標籤上。</span><span class="sxs-lookup"><span data-stu-id="bff3a-115">The GPO is removed from the **Recycle Bin** tab and is displayed on the **Controlled** tab.</span></span>

<span data-ttu-id="bff3a-116">**記事** 如果 GPO 已從生產環境中刪除，則將其還原到封存後，就不會自動將它重新部署到生產環境。</span><span class="sxs-lookup"><span data-stu-id="bff3a-116">**Note** If a GPO was deleted from the production environment, restoring it to the archive will not automatically redeploy it to the production environment.</span></span> <span data-ttu-id="bff3a-117">若要將 GPO 傳回生產環境，請部署 GPO。</span><span class="sxs-lookup"><span data-stu-id="bff3a-117">To return the GPO to the production environment, deploy the GPO.</span></span> <span data-ttu-id="bff3a-118">如需詳細資訊，請參閱[要求部署 GPO](request-deployment-of-a-gpo-agpm40.md)。</span><span class="sxs-lookup"><span data-stu-id="bff3a-118">For information, see [Request Deployment of a GPO](request-deployment-of-a-gpo-agpm40.md).</span></span>

 

### <span data-ttu-id="bff3a-119">其他考量</span><span class="sxs-lookup"><span data-stu-id="bff3a-119">Additional considerations</span></span>

-   <span data-ttu-id="bff3a-120">根據預設，您必須是編輯器才能執行此程式。</span><span class="sxs-lookup"><span data-stu-id="bff3a-120">By default, you must be an Editor to perform this procedure.</span></span> <span data-ttu-id="bff3a-121">具體說來，您必須擁有該 GPO 的 [**清單內容**] 和 [**編輯設定**] 許可權。</span><span class="sxs-lookup"><span data-stu-id="bff3a-121">Specifically, you must have **List Contents** and **Edit Settings** permission for the GPO.</span></span>

-   <span data-ttu-id="bff3a-122">若要在獲核准前收回您的要求，請按一下 [**待定**] 索引標籤。以滑鼠右鍵按一下該 GPO，然後按一下 [**收回**]。</span><span class="sxs-lookup"><span data-stu-id="bff3a-122">To withdraw your request before it has been approved, click the **Pending** tab. Right-click the GPO, and then click **Withdraw**.</span></span> <span data-ttu-id="bff3a-123">GPO 將會傳回 [**回收站**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="bff3a-123">The GPO will be returned to the **Recycle Bin** tab.</span></span>

### <span data-ttu-id="bff3a-124">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="bff3a-124">Additional references</span></span>

-   [<span data-ttu-id="bff3a-125">刪除或還原 GPO</span><span class="sxs-lookup"><span data-stu-id="bff3a-125">Deleting or Restoring a GPO</span></span>](deleting-or-restoring-a-gpo-agpm40.md)

 

 





