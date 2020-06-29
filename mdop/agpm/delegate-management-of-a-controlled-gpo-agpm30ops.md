---
title: 委派管理受控制的 GPO
description: 委派管理受控制的 GPO
author: dansimp
ms.assetid: 509b02e7-ce0b-4919-b58a-c3a33051152e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9d34231f25c172951cd0176b3e490dab84b98f1d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801929"
---
# <span data-ttu-id="d629d-103">委派管理受控制的 GPO</span><span class="sxs-lookup"><span data-stu-id="d629d-103">Delegate Management of a Controlled GPO</span></span>


<span data-ttu-id="d629d-104">核准者可以委派由該核准者所建立的受控群組原則物件（GPO）的管理。</span><span class="sxs-lookup"><span data-stu-id="d629d-104">An Approver can delegate the management of a controlled Group Policy Object (GPO) that was created by that Approver.</span></span> <span data-ttu-id="d629d-105">就像 AGPM 系統管理員（完全控制），核准者可以委派此類 GPO 的存取權，讓選取的編輯者可以對其進行編輯、檢閱者可以進行審閱，以及其他核准者可以核准。</span><span class="sxs-lookup"><span data-stu-id="d629d-105">Like an AGPM Administrator (Full Control), the Approver can delegate access to such a GPO so that selected Editors can edit it, Reviewers can review it, and other Approvers can approve it.</span></span> <span data-ttu-id="d629d-106">根據預設，核准者無法委派對其他群組原則系統管理員所建立之 Gpo 的存取權。</span><span class="sxs-lookup"><span data-stu-id="d629d-106">By default, an Approver cannot delegate access to GPOs created by another Group Policy administrator.</span></span>

<span data-ttu-id="d629d-107">使用 AGPM 系統管理員（完全控制）角色的使用者帳戶、建立 GPO 之核准者的使用者帳戶，或必須具備高級群組原則管理（AGPM）中所需許可權的使用者帳戶，才能完成此程式。</span><span class="sxs-lookup"><span data-stu-id="d629d-107">A user account with the AGPM Administrator (Full Control) role, the user account of the Approver who created the GPO, or a user account with the necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="d629d-108">請參閱本主題中的「其他注意事項」中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d629d-108">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="d629d-109">委派受控 GPO 的管理</span><span class="sxs-lookup"><span data-stu-id="d629d-109">To delegate the management of a controlled GPO</span></span>**

1.  <span data-ttu-id="d629d-110">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="d629d-110">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="d629d-111">在 [詳細資料] 窗格的 [**內容**] 索引標籤上，按一下 [**受控**] 索引標籤以顯示 [受控 gpo]，然後按一下要委派的 gpo：</span><span class="sxs-lookup"><span data-stu-id="d629d-111">On the **Contents** tab in the details pane, click the **Controlled** tab to display controlled GPOs, and then click the GPO to delegate:</span></span>

    1.  <span data-ttu-id="d629d-112">若要新增使用者或群組的存取權，請按一下 [**新增**] 按鈕，選取使用者或群組，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d629d-112">To add access for a user or group, click the **Add** button, select the user or group, and click **OK**.</span></span> <span data-ttu-id="d629d-113">在 [**新增群組或使用者**] 對話方塊中，選取一個角色，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d629d-113">In the **Add Group or User** dialog box, select a role and click **OK**.</span></span>

    2.  <span data-ttu-id="d629d-114">若要移除使用者或群組的存取權，請選取使用者或群組，然後按一下 [**移除**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="d629d-114">To remove access for a user or group, select the user or group, and then click the **Remove** button.</span></span>

        <span data-ttu-id="d629d-115">**記事** 如果使用者或群組繼承全域存取權，[**移除**] 按鈕就無法使用。</span><span class="sxs-lookup"><span data-stu-id="d629d-115">**Note** If a user or group inherits domain-wide access, the **Remove** button is unavailable.</span></span> <span data-ttu-id="d629d-116">您可以在 [**網域委派**] 索引標籤上修改全域性存取權。</span><span class="sxs-lookup"><span data-stu-id="d629d-116">You can modify domain-wide access on the **Domain Delegation** tab.</span></span>

         

    3.  <span data-ttu-id="d629d-117">若要修改委派給使用者或群組的角色和許可權，請按一下 [**高級**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="d629d-117">To modify the roles and permissions delegated to a user or group, click the **Advanced** button.</span></span> <span data-ttu-id="d629d-118">在 [**許可權**] 對話方塊中，選取使用者或群組，選取要指派給該使用者或群組的每個角色的核取方塊，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d629d-118">In the **Permissions** dialog box, select the user or group, select the check box for each role to be assigned to that user or group, and then click **OK**.</span></span>

        <span data-ttu-id="d629d-119">**記事** 編輯者和核准者都包含審查員許可權。</span><span class="sxs-lookup"><span data-stu-id="d629d-119">**Note** Editor and Approver include Reviewer permissions.</span></span>

         

### <span data-ttu-id="d629d-120">其他考量</span><span class="sxs-lookup"><span data-stu-id="d629d-120">Additional considerations</span></span>

-   <span data-ttu-id="d629d-121">根據預設，您必須是建立或控制 GPO 的核准者，或是 AGPM 系統管理員（完全控制）才能執行此程式。</span><span class="sxs-lookup"><span data-stu-id="d629d-121">By default, you must be the Approver who created or controlled the GPO or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="d629d-122">具體說來，您必須擁有網域的 [**清單內容**] 許可權，並修改 GPO 的**安全性**許可權。</span><span class="sxs-lookup"><span data-stu-id="d629d-122">Specifically, you must have **List Contents** permission for the domain and **Modify Security** permission for the GPO.</span></span>

-   <span data-ttu-id="d629d-123">若要委派使用 AGPM 的群組原則管理員的讀取存取權，您必須授與其**清單內容**，以及**讀取設定**許可權。</span><span class="sxs-lookup"><span data-stu-id="d629d-123">To delegate read access to Group Policy administrators who use AGPM, you must grant them **List Contents** as well as **Read Settings** permissions.</span></span> <span data-ttu-id="d629d-124">這可讓他們在 AGPM 的 [**目錄**] 索引標籤上查看 gpo。</span><span class="sxs-lookup"><span data-stu-id="d629d-124">This enables them to view GPOs on the **Contents** tab of AGPM.</span></span> <span data-ttu-id="d629d-125">其他許可權必須明確委派。</span><span class="sxs-lookup"><span data-stu-id="d629d-125">Other permissions must be explicitly delegated.</span></span>

-   <span data-ttu-id="d629d-126">編輯者必須擁有已部署之 GPO 複本的**讀取**許可權，才能完整地使用 [群組原則軟體安裝]。</span><span class="sxs-lookup"><span data-stu-id="d629d-126">Editors must have **Read** permission for the deployed copy of a GPO to make full use of Group Policy Software Installation.</span></span>

### <span data-ttu-id="d629d-127">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="d629d-127">Additional references</span></span>

-   [<span data-ttu-id="d629d-128">建立、控制或匯入 GPO</span><span class="sxs-lookup"><span data-stu-id="d629d-128">Creating, Controlling, or Importing a GPO</span></span>](creating-controlling-or-importing-a-gpo-editor-agpm30ops.md)

 

 





