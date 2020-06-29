---
title: 委派管理 GPO 的存取權
description: 委派管理 GPO 的存取權
author: dansimp
ms.assetid: f1d6bb6c-d5bf-4080-a6cb-32774689f804
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 57a71528120b65676d25d952d9f9392dc0250ae4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801954"
---
# <span data-ttu-id="2916c-103">委派管理 GPO 的存取權</span><span class="sxs-lookup"><span data-stu-id="2916c-103">Delegate Access to a GPO</span></span>


<span data-ttu-id="2916c-104">核准者可以委派**由該核准者所建立**的受控群組原則物件（GPO）的管理。</span><span class="sxs-lookup"><span data-stu-id="2916c-104">An Approver can delegate the management of a controlled Group Policy object (GPO) that was **created by that Approver**.</span></span> <span data-ttu-id="2916c-105">就像 AGPM 系統管理員（完全控制），核准者可以委派此類 GPO 的存取權，讓選取的編輯者可以進行編輯、檢閱者可以進行審閱，以及其他核准者可以核准。</span><span class="sxs-lookup"><span data-stu-id="2916c-105">Like an AGPM Administrator (Full Control), the Approver can delegate access to such a GPO, so selected Editors can edit it, Reviewers can review it, and other Approvers can approve it.</span></span> <span data-ttu-id="2916c-106">根據預設，核准者無法委派對其他群組原則系統管理員所建立之 Gpo 的存取權。</span><span class="sxs-lookup"><span data-stu-id="2916c-106">By default, an Approver cannot delegate access to GPOs created by another Group Policy administrator.</span></span>

<span data-ttu-id="2916c-107">具有 AGPM 系統管理員（完全控制）角色的使用者帳戶、建立 GPO 之核准者的使用者帳戶，或必須具備高級群組原則管理中所需許可權的使用者帳戶，才能完成此程式。</span><span class="sxs-lookup"><span data-stu-id="2916c-107">A user account with the AGPM Administrator (Full Control) role, the user account of the Approver who created the GPO, or a user account with the necessary permissions in Advanced Group Policy Management is required to complete this procedure.</span></span> <span data-ttu-id="2916c-108">請參閱本主題中的「其他注意事項」中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="2916c-108">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="2916c-109">委派受控 GPO 的管理</span><span class="sxs-lookup"><span data-stu-id="2916c-109">To delegate the management of a controlled GPO</span></span>**

1.  <span data-ttu-id="2916c-110">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="2916c-110">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="2916c-111">在 [詳細資料] 窗格的 [**內容**] 索引標籤上，按一下 [**受控**] 索引標籤以顯示 [受控 gpo]，然後按一下要委派的 gpo。</span><span class="sxs-lookup"><span data-stu-id="2916c-111">On the **Contents** tab in the details pane, click the **Controlled** tab to display controlled GPOs, and then click the GPO to delegate.</span></span>

3.  <span data-ttu-id="2916c-112">按一下 [**新增**] 按鈕，選取允許存取的使用者或群組，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="2916c-112">Click the **Add** button, select the users or groups to be permitted access, and then click **OK**.</span></span>

4.  <span data-ttu-id="2916c-113">若要自訂每個許可權，請按一下 [**內容**] 索引標籤上的 [**高級**] 按鈕，然後核取 [允許或拒絕] 的角色許可權。</span><span class="sxs-lookup"><span data-stu-id="2916c-113">To customize the permissions for each, click the **Advanced** button on the **Contents** tab and check role permissions to allow or deny.</span></span> <span data-ttu-id="2916c-114">（如需詳細控制，請按一下 [**許可權**] 對話方塊中的 [**高級**]。）</span><span class="sxs-lookup"><span data-stu-id="2916c-114">(For more detailed control, click **Advanced** in the **Permissions** dialog box.)</span></span>

5.  <span data-ttu-id="2916c-115">按一下 [套用]，**然後按一下 [\*\*\*\*許可權**] 對話方塊中的 **[確定]** 。</span><span class="sxs-lookup"><span data-stu-id="2916c-115">Click **Apply**, and then click **OK** in the **Permissions** dialog box.</span></span>

### <span data-ttu-id="2916c-116">其他考量</span><span class="sxs-lookup"><span data-stu-id="2916c-116">Additional considerations</span></span>

-   <span data-ttu-id="2916c-117">根據預設，您必須是建立或控制 GPO 的核准者，或是 AGPM 系統管理員（完全控制）才能執行此程式。</span><span class="sxs-lookup"><span data-stu-id="2916c-117">By default, you must be the Approver who created or controlled the GPO or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="2916c-118">具體說來，您必須擁有網域的 [**清單內容**] 許可權，並修改 GPO 的**安全性**許可權。</span><span class="sxs-lookup"><span data-stu-id="2916c-118">Specifically, you must have **List Contents** permission for the domain and **Modify Security** permission for the GPO.</span></span>

### <span data-ttu-id="2916c-119">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="2916c-119">Additional references</span></span>

-   [<span data-ttu-id="2916c-120">建立、控制或匯入 GPO</span><span class="sxs-lookup"><span data-stu-id="2916c-120">Creating, Controlling, or Importing a GPO</span></span>](creating-controlling-or-importing-a-gpo-approver.md)

 

 





