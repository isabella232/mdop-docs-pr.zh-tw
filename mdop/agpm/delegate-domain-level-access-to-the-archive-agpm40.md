---
title: 委派管理封存的網域層級存取權
description: 委派管理封存的網域層級存取權
author: dansimp
ms.assetid: 11ca1d40-4b5c-496e-8922-d01412717858
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b33c0ec8821248ab4eddc051e67e7f0e6c073a9e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801930"
---
# <span data-ttu-id="048b9-103">委派管理封存的網域層級存取權</span><span class="sxs-lookup"><span data-stu-id="048b9-103">Delegate Domain-Level Access to the Archive</span></span>


<span data-ttu-id="048b9-104">針對您的環境設定委派，讓群組原則管理員具備適當的存取權，並控制封存中的群組原則物件（Gpo）。</span><span class="sxs-lookup"><span data-stu-id="048b9-104">Set up delegation for your environment so that Group Policy administrators have the appropriate access to and control over Group Policy Objects (GPOs) in the archive.</span></span> <span data-ttu-id="048b9-105">您可以套用基本許可權來讓作業更有效率。</span><span class="sxs-lookup"><span data-stu-id="048b9-105">There are baseline permissions you can apply to make operation more efficient.</span></span> <span data-ttu-id="048b9-106">您可以以任何符合貴組織需求的方式，授與許可權。</span><span class="sxs-lookup"><span data-stu-id="048b9-106">You can grant permissions in any manner that meets the needs of your organization.</span></span>

<span data-ttu-id="048b9-107">您必須具備高級群組原則管理（AGPM）中具有 AGPM 系統管理員（完全控制）角色或必要許可權的使用者帳戶，才能完成此程式。</span><span class="sxs-lookup"><span data-stu-id="048b9-107">A user account with the AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="048b9-108">請參閱本主題中的「其他注意事項」中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="048b9-108">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="048b9-109">委派存取權，讓使用者和群組對整個網域中的所有 Gpo 擁有適當的許可權</span><span class="sxs-lookup"><span data-stu-id="048b9-109">To delegate access so that users and groups have appropriate permissions to all GPOs throughout a domain</span></span>**

1.  <span data-ttu-id="048b9-110">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="048b9-110">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="048b9-111">按一下 [**網域委派**] 索引標籤，然後設定網域中所有 gpo 的存取權：</span><span class="sxs-lookup"><span data-stu-id="048b9-111">Click the **Domain Delegation** tab, and configure access to all GPOs in the domain:</span></span>

    1.  <span data-ttu-id="048b9-112">若要新增使用者或群組的存取權，請按一下 [**新增**] 按鈕，選取使用者或群組，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="048b9-112">To add access for a user or group, click the **Add** button, select the user or group, and click **OK**.</span></span> <span data-ttu-id="048b9-113">在 [**新增群組或使用者**] 對話方塊中，選取一個角色，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="048b9-113">In the **Add Group or User** dialog box, select a role and click **OK**.</span></span>

    2.  <span data-ttu-id="048b9-114">若要移除使用者或群組的存取權，請選取使用者或群組，然後按一下 [**移除**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="048b9-114">To remove access for a user or group, select the user or group, and click the **Remove** button.</span></span>

    3.  <span data-ttu-id="048b9-115">若要修改委派給使用者或群組的角色和許可權，請選取按一下 [**高級**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="048b9-115">To modify the roles and permissions delegated to a user or group, select click the **Advanced** button.</span></span> <span data-ttu-id="048b9-116">在 [**許可權**] 對話方塊中，選取使用者或群組，選取要指派給該使用者或群組的每個角色的核取方塊，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="048b9-116">In the **Permissions** dialog box, select the user or group, select the check box for each role to be assigned to that user or group, and then click **OK**.</span></span>

        <span data-ttu-id="048b9-117">**記事** 編輯者和核准者都包含審查員許可權。</span><span class="sxs-lookup"><span data-stu-id="048b9-117">**Note** Editor and Approver include Reviewer permissions.</span></span>

         

### <span data-ttu-id="048b9-118">其他考量</span><span class="sxs-lookup"><span data-stu-id="048b9-118">Additional considerations</span></span>

-   <span data-ttu-id="048b9-119">根據預設，您必須是 AGPM 系統管理員（完全控制）才能執行此程式。</span><span class="sxs-lookup"><span data-stu-id="048b9-119">By default, you must be an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="048b9-120">具體說來，您必須具有網域的 [**修改安全性**] 許可權。</span><span class="sxs-lookup"><span data-stu-id="048b9-120">Specifically, you must have **Modify Security** permission for the domain.</span></span>

-   <span data-ttu-id="048b9-121">若要委派使用 AGPM 的群組原則管理員的讀取存取權，您必須授與其**清單內容**，以及**讀取設定**許可權。</span><span class="sxs-lookup"><span data-stu-id="048b9-121">To delegate read access to Group Policy administrators who use AGPM, you must grant them **List Contents** as well as **Read Settings** permissions.</span></span> <span data-ttu-id="048b9-122">這可讓他們在 AGPM 的 [**目錄**] 索引標籤上查看 gpo。</span><span class="sxs-lookup"><span data-stu-id="048b9-122">This enables them to view GPOs on the **Contents** tab of AGPM.</span></span> <span data-ttu-id="048b9-123">其他許可權必須明確委派。</span><span class="sxs-lookup"><span data-stu-id="048b9-123">Other permissions must be explicitly delegated.</span></span>

-   <span data-ttu-id="048b9-124">針對已部署的 GPO 複本，**必須授與**編輯許可權，才能完整地使用 [群組原則軟體安裝]。</span><span class="sxs-lookup"><span data-stu-id="048b9-124">Editors must be granted **Read** permission for the deployed copy of a GPO to make full use of Group Policy Software Installation.</span></span>

-   <span data-ttu-id="048b9-125">[群組原則建立人擁有者] 群組中的成員資格應該受到限制，不會使用 soit 來避開對 Gpo 存取的 AGPM 管理。</span><span class="sxs-lookup"><span data-stu-id="048b9-125">Membership in the Group Policy Creator Owners group should be restricted, soit is not used to circumvent AGPM management of access to GPOs.</span></span> <span data-ttu-id="048b9-126">（在 [**群組原則管理主控台**] 中，按一下要管理 gpo 的林和網域中的 [**群組原則物件**]，按一下 [**委派**]，然後設定設定以符合貴組織的需求。）</span><span class="sxs-lookup"><span data-stu-id="048b9-126">(In the **Group Policy Management Console**, click **Group Policy Objects** in the forest and domain in which you want to manage GPOs, click **Delegation**, and then configure the settings to meet the needs of your organization.)</span></span>

### <span data-ttu-id="048b9-127">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="048b9-127">Additional references</span></span>

-   [<span data-ttu-id="048b9-128">管理封存</span><span class="sxs-lookup"><span data-stu-id="048b9-128">Managing the Archive</span></span>](managing-the-archive-agpm40.md)

 

 





