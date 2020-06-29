---
title: 委派管理個別 GPO 的存取權
description: 委派管理個別 GPO 的存取權
author: dansimp
ms.assetid: b2a7d550-14bf-4b41-b6e4-2cc091eedd2d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9e5d2ae8c6ef52eae39feb67b9df42e84f523300
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801934"
---
# <span data-ttu-id="cf21f-103">委派管理個別 GPO 的存取權</span><span class="sxs-lookup"><span data-stu-id="cf21f-103">Delegate Access to an Individual GPO</span></span>


<span data-ttu-id="cf21f-104">在 AGPM 系統管理員（完全控制）中，您可以委派受控制的群組原則物件（GPO）的管理，讓選取的群組和編輯者可以進行編輯、檢閱者可以進行審閱，且核准者可以核准。</span><span class="sxs-lookup"><span data-stu-id="cf21f-104">As an AGPM Administrator (Full Control), you can delegate the management of a controlled Group Policy object (GPO), so selected groups and Editors can edit it, Reviewers can review it, and Approvers can approve it.</span></span>

<span data-ttu-id="cf21f-105">具有 AGPM 系統管理員（完全控制）角色的使用者帳戶、建立 GPO 之核准者的使用者帳戶，或必須具備高級群組原則管理中所需許可權的使用者帳戶，才能完成此程式。</span><span class="sxs-lookup"><span data-stu-id="cf21f-105">A user account with the AGPM Administrator (Full Control) role, the user account of the Approver who created the GPO, or a user account with the necessary permissions in Advanced Group Policy Management is required to complete this procedure.</span></span> <span data-ttu-id="cf21f-106">請參閱本主題中的「其他注意事項」中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="cf21f-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="cf21f-107">委派受控 GPO 的管理</span><span class="sxs-lookup"><span data-stu-id="cf21f-107">To delegate the management of a controlled GPO</span></span>**

1.  <span data-ttu-id="cf21f-108">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="cf21f-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="cf21f-109">在 [詳細資料] 窗格的 [**內容**] 索引標籤上，按一下 [**受控**] 索引標籤以顯示 [受控 gpo]，然後按一下要委派的 gpo。</span><span class="sxs-lookup"><span data-stu-id="cf21f-109">On the **Contents** tab in the details pane, click the **Controlled** tab to display controlled GPOs, and then click the GPO to delegate.</span></span>

3.  <span data-ttu-id="cf21f-110">按一下 [**新增**] 按鈕，選取允許存取的使用者或群組，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="cf21f-110">Click the **Add** button, select the users or groups to be permitted access, and then click **OK**.</span></span>

4.  <span data-ttu-id="cf21f-111">若要自訂每個使用者或群組的許可權，請按一下 [**內容**] 索引標籤上的 [**高級**] 按鈕，然後核取 [允許] 或 [拒絕]。</span><span class="sxs-lookup"><span data-stu-id="cf21f-111">To customize the permissions for each user or group, click the **Advanced** button on the **Contents** tab and check role permissions to allow or deny.</span></span> <span data-ttu-id="cf21f-112">（如需詳細控制，請按一下 [**許可權**] 對話方塊中的 [**高級**]。）</span><span class="sxs-lookup"><span data-stu-id="cf21f-112">(For more detailed control, click **Advanced** in the **Permissions** dialog box.)</span></span>

5.  <span data-ttu-id="cf21f-113">按一下 [套用]，**然後按一下 [\*\*\*\*許可權**] 對話方塊中的 **[確定]** 。</span><span class="sxs-lookup"><span data-stu-id="cf21f-113">Click **Apply**, and then click **OK** in the **Permissions** dialog box.</span></span>

### <span data-ttu-id="cf21f-114">其他考量</span><span class="sxs-lookup"><span data-stu-id="cf21f-114">Additional considerations</span></span>

-   <span data-ttu-id="cf21f-115">根據預設，您必須是建立或控制 GPO 的核准者，或是 AGPM 系統管理員（完全控制）才能執行此程式。</span><span class="sxs-lookup"><span data-stu-id="cf21f-115">By default, you must be the Approver who created or controlled the GPO or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="cf21f-116">具體說來，您必須擁有網域的 [**清單內容**] 許可權，並修改 GPO 的**安全性**許可權。</span><span class="sxs-lookup"><span data-stu-id="cf21f-116">Specifically, you must have **List Contents** permission for the domain and **Modify Security** permission for the GPO.</span></span>

-   <span data-ttu-id="cf21f-117">若要委派使用 AGPM 的群組原則管理員的讀取存取權，您必須授與其**清單內容**，以及**讀取設定**許可權。</span><span class="sxs-lookup"><span data-stu-id="cf21f-117">To delegate read access to Group Policy administrators who use AGPM, you must grant them **List Contents** as well as **Read Settings** permissions.</span></span> <span data-ttu-id="cf21f-118">這可讓他們在 AGPM 的 [**目錄**] 索引標籤上查看 gpo。</span><span class="sxs-lookup"><span data-stu-id="cf21f-118">This enables them to view GPOs on the **Contents** tab of AGPM.</span></span> <span data-ttu-id="cf21f-119">設定要套用至**此物件及嵌套物件**的許可權。</span><span class="sxs-lookup"><span data-stu-id="cf21f-119">Set the permission to apply to **This object and nested objects**.</span></span> <span data-ttu-id="cf21f-120">其他許可權必須明確委派。</span><span class="sxs-lookup"><span data-stu-id="cf21f-120">Other permissions must be explicitly delegated.</span></span>

-   <span data-ttu-id="cf21f-121">編輯者必須擁有已部署之 GPO 複本的**讀取**許可權，才能完整地使用 [群組原則軟體安裝]。</span><span class="sxs-lookup"><span data-stu-id="cf21f-121">Editors must have **Read** permission for the deployed copy of a GPO to make full use of Group Policy Software Installation.</span></span>

-   <span data-ttu-id="cf21f-122">[群組原則建立者擁有者] 群組中的成員資格應該受到限制，因此不會用來避開對 Gpo 存取的 AGPM 管理。</span><span class="sxs-lookup"><span data-stu-id="cf21f-122">Membership in the Group Policy Creator Owners group should be restricted so that it is not used to circumvent AGPM management of access to GPOs.</span></span> <span data-ttu-id="cf21f-123">（在 [**群組原則管理主控台**] 中，按一下要管理 gpo 的林和網域中的 [**群組原則物件**]，按一下 [**委派**]，然後設定設定以符合貴組織的需求。）</span><span class="sxs-lookup"><span data-stu-id="cf21f-123">(In the **Group Policy Management Console**, click **Group Policy Objects** in the forest and domain in which you want to manage GPOs, click **Delegation**, and then configure the settings to meet the needs of your organization.)</span></span>

### <span data-ttu-id="cf21f-124">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="cf21f-124">Additional references</span></span>

-   [<span data-ttu-id="cf21f-125">執行 AGPM 系統管理員工作</span><span class="sxs-lookup"><span data-stu-id="cf21f-125">Performing AGPM Administrator Tasks</span></span>](performing-agpm-administrator-tasks.md)

 

 





