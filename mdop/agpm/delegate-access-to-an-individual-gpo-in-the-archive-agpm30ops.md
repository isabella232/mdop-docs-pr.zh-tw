---
title: 委派管理封存中個別 GPO 的存取權
description: 委派管理封存中個別 GPO 的存取權
author: dansimp
ms.assetid: 7b37b188-2b6b-4e52-be97-8ef899e9893b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 592937a28b0e2556991b0c338b88b2cfa88ba83d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801949"
---
# <span data-ttu-id="880a1-103">委派管理封存中個別 GPO 的存取權</span><span class="sxs-lookup"><span data-stu-id="880a1-103">Delegate Access to an Individual GPO in the Archive</span></span>


<span data-ttu-id="880a1-104">在 AGPM 系統管理員（完全控制）中，您可以委派封存中受控制的群組原則物件（GPO）的管理，讓選取的群組和編輯者可以對其進行編輯、檢閱者可以進行審閱，且核准者可以核准。</span><span class="sxs-lookup"><span data-stu-id="880a1-104">As an AGPM Administrator (Full Control), you can delegate the management of a controlled Group Policy Object (GPO) in the archive so that selected groups and Editors can edit it, Reviewers can review it, and Approvers can approve it.</span></span>

<span data-ttu-id="880a1-105">使用 AGPM 系統管理員（完全控制）角色的使用者帳戶、建立 GPO 之核准者的使用者帳戶，或必須具備高級群組原則管理（AGPM）中所需許可權的使用者帳戶，才能完成此程式。</span><span class="sxs-lookup"><span data-stu-id="880a1-105">A user account with the AGPM Administrator (Full Control) role, the user account of the Approver who created the GPO, or a user account with the necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="880a1-106">請參閱本主題中的「其他注意事項」中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="880a1-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="880a1-107">委派受控 GPO 的管理</span><span class="sxs-lookup"><span data-stu-id="880a1-107">To delegate the management of a controlled GPO</span></span>**

1.  <span data-ttu-id="880a1-108">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="880a1-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="880a1-109">在 [詳細資料] 窗格的 [**內容**] 索引標籤上，按一下 [**受控**] 索引標籤以顯示 [受控 gpo]，然後按一下要委派的 gpo：</span><span class="sxs-lookup"><span data-stu-id="880a1-109">On the **Contents** tab in the details pane, click the **Controlled** tab to display controlled GPOs, and then click the GPO to delegate:</span></span>

    1.  <span data-ttu-id="880a1-110">若要新增使用者或群組的存取權，請按一下 [**新增**] 按鈕，選取使用者或群組，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="880a1-110">To add access for a user or group, click the **Add** button, select the user or group, and click **OK**.</span></span> <span data-ttu-id="880a1-111">在 [**新增群組或使用者**] 對話方塊中，選取一個角色，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="880a1-111">In the **Add Group or User** dialog box, select a role and click **OK**.</span></span>

    2.  <span data-ttu-id="880a1-112">若要移除使用者或群組的存取權，請選取使用者或群組，然後按一下 [**移除**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="880a1-112">To remove access for a user or group, select the user or group, and click the **Remove** button.</span></span>

        <span data-ttu-id="880a1-113">**記事** 如果使用者或群組繼承全域存取權，[**移除**] 按鈕就無法使用。</span><span class="sxs-lookup"><span data-stu-id="880a1-113">**Note** If a user or group inherits domain-wide access, the **Remove** button is unavailable.</span></span> <span data-ttu-id="880a1-114">您可以在 [**網域委派**] 索引標籤上修改全域性存取權。</span><span class="sxs-lookup"><span data-stu-id="880a1-114">You can modify domain-wide access on the **Domain Delegation** tab.</span></span>

         

    3.  <span data-ttu-id="880a1-115">若要修改委派給使用者或群組的角色和許可權，請按一下 [**高級**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="880a1-115">To modify the roles and permissions delegated to a user or group, click the **Advanced** button.</span></span> <span data-ttu-id="880a1-116">在 [**許可權**] 對話方塊中，選取使用者或群組，選取要指派給該使用者或群組的每個角色的核取方塊，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="880a1-116">In the **Permissions** dialog box, select the user or group, select the check box for each role to be assigned to that user or group, and click **OK**.</span></span>

        <span data-ttu-id="880a1-117">**記事** 編輯者和核准者都包含審查員許可權。</span><span class="sxs-lookup"><span data-stu-id="880a1-117">**Note** Editor and Approver include Reviewer permissions.</span></span>

         

### <span data-ttu-id="880a1-118">其他考量</span><span class="sxs-lookup"><span data-stu-id="880a1-118">Additional considerations</span></span>

-   <span data-ttu-id="880a1-119">根據預設，您必須是建立或控制 GPO 的核准者，或是 AGPM 系統管理員（完全控制）才能執行此程式。</span><span class="sxs-lookup"><span data-stu-id="880a1-119">By default, you must be the Approver who created or controlled the GPO or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="880a1-120">具體說來，您必須擁有網域的 [**清單內容**] 許可權，並修改 GPO 的**安全性**許可權。</span><span class="sxs-lookup"><span data-stu-id="880a1-120">Specifically, you must have **List Contents** permission for the domain and **Modify Security** permission for the GPO.</span></span>

-   <span data-ttu-id="880a1-121">若要委派使用 AGPM 的群組原則管理員的讀取存取權，您必須授與其**清單內容**，以及**讀取設定**許可權。</span><span class="sxs-lookup"><span data-stu-id="880a1-121">To delegate read access to Group Policy administrators who use AGPM, you must grant them **List Contents** as well as **Read Settings** permissions.</span></span> <span data-ttu-id="880a1-122">這可讓他們在 AGPM 的 [**目錄**] 索引標籤上查看 gpo。</span><span class="sxs-lookup"><span data-stu-id="880a1-122">This enables them to view GPOs on the **Contents** tab of AGPM.</span></span> <span data-ttu-id="880a1-123">其他許可權必須明確委派。</span><span class="sxs-lookup"><span data-stu-id="880a1-123">Other permissions must be explicitly delegated.</span></span>

-   <span data-ttu-id="880a1-124">編輯者必須擁有已部署之 GPO 複本的**讀取**許可權，才能完整地使用 [群組原則軟體安裝]。</span><span class="sxs-lookup"><span data-stu-id="880a1-124">Editors must have **Read** permission for the deployed copy of a GPO to make full use of Group Policy Software Installation.</span></span>

-   <span data-ttu-id="880a1-125">[群組原則建立人擁有者] 群組中的成員資格應該受到限制，不會使用 soit 來避開對 Gpo 存取的 AGPM 管理。</span><span class="sxs-lookup"><span data-stu-id="880a1-125">Membership in the Group Policy Creator Owners group should be restricted, soit is not used to circumvent AGPM management of access to GPOs.</span></span> <span data-ttu-id="880a1-126">（在 [**群組原則管理主控台**] 中，按一下要管理 gpo 的林和網域中的 [**群組原則物件**]，按一下 [**委派**]，然後設定設定以符合貴組織的需求。）</span><span class="sxs-lookup"><span data-stu-id="880a1-126">(In the **Group Policy Management Console**, click **Group Policy Objects** in the forest and domain in which you want to manage GPOs, click **Delegation**, and then configure the settings to meet the needs of your organization.)</span></span>

### <span data-ttu-id="880a1-127">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="880a1-127">Additional references</span></span>

-   [<span data-ttu-id="880a1-128">管理封存</span><span class="sxs-lookup"><span data-stu-id="880a1-128">Managing the Archive</span></span>](managing-the-archive.md)

 

 





