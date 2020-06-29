---
title: 委派管理網域層級存取權
description: 委派管理網域層級存取權
author: dansimp
ms.assetid: 64c8e773-38cc-4991-9ed2-5a801094d06e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7eb4c33e60b0d995e45fca6c9e91a26c30dd4a7f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802841"
---
# <span data-ttu-id="d136a-103">委派管理網域層級存取權</span><span class="sxs-lookup"><span data-stu-id="d136a-103">Delegate Domain-Level Access</span></span>


<span data-ttu-id="d136a-104">針對您的環境設定委派，讓群組原則管理員具備適當的存取權並控制群組原則物件（Gpo）。</span><span class="sxs-lookup"><span data-stu-id="d136a-104">Set up delegation for your environment so Group Policy administrators have the appropriate access to and control over Group Policy objects (GPOs).</span></span> <span data-ttu-id="d136a-105">您可以套用基本許可權來執行高級群組原則管理（AGPM）的工作效率。</span><span class="sxs-lookup"><span data-stu-id="d136a-105">There are baseline permissions you can apply to make the operation of Advanced Group Policy Management (AGPM) more efficient.</span></span> <span data-ttu-id="d136a-106">您可以以任何符合貴組織需求的方式，授與許可權。</span><span class="sxs-lookup"><span data-stu-id="d136a-106">You can grant permissions in any manner that meets the needs of your organization.</span></span>

<span data-ttu-id="d136a-107">具有 AGPM 系統管理員（完全控制）角色的使用者帳戶或高級群組原則管理中的必要許可權，才能完成此程式。</span><span class="sxs-lookup"><span data-stu-id="d136a-107">A user account with the AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management is required to complete this procedure.</span></span> <span data-ttu-id="d136a-108">請參閱本主題中的「其他注意事項」中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="d136a-108">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="d136a-109">若要委派存取權，讓使用者和群組對整個網域中的所有 Gpo 擁有適當的許可權</span><span class="sxs-lookup"><span data-stu-id="d136a-109">To delegate access so users and groups have appropriate permissions to all GPOs throughout a domain</span></span>**

1.  <span data-ttu-id="d136a-110">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="d136a-110">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="d136a-111">按一下 [**網域委派**] 索引標籤，然後按一下 [**高級**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="d136a-111">Click the **Domain Delegation** tab, then click the **Advanced** button.</span></span>

3.  <span data-ttu-id="d136a-112">在 [**許可權**] 對話方塊中，按一下要指派給某個人的每個角色的核取方塊，然後按一下 [**高級**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="d136a-112">In the **Permissions** dialog box, click the check box for each role to be assigned to an individual, and then click the **Advanced** button.</span></span>

    <span data-ttu-id="d136a-113">**記事** 編輯者和核准者都包含審查員許可權。</span><span class="sxs-lookup"><span data-stu-id="d136a-113">**Note** Editor and Approver include Reviewer permissions.</span></span>

     

4.  <span data-ttu-id="d136a-114">在 [**高級安全設定**] 對話方塊中，選取 [群組原則系統管理員]，然後按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="d136a-114">In the **Advanced Security Settings** dialog box, select a Group Policy administrator, and then click **Edit**.</span></span>

5.  <span data-ttu-id="d136a-115">若要套用**至**，請選取**這個物件及嵌套物件**，設定除標準 AGPM 角色以外的任何特殊許可權，然後在 **[許可權\*\*\*\*專案**] 對話方塊中按一下 **[確定**]。</span><span class="sxs-lookup"><span data-stu-id="d136a-115">For **Apply onto**, select **This object and nested objects**, configure any special permissions beyond the standard AGPM roles, then click **OK** in the **Permission** **Entry** dialog box.</span></span>

6.  <span data-ttu-id="d136a-116">在 [**高級安全設定**] 對話方塊中，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d136a-116">In the **Advanced Security Settings** dialog box, click **OK**.</span></span>

7.  <span data-ttu-id="d136a-117">在 [**許可權**] 對話方塊中，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d136a-117">In the **Permissions** dialog box, click **OK**.</span></span>

### <span data-ttu-id="d136a-118">其他考量</span><span class="sxs-lookup"><span data-stu-id="d136a-118">Additional considerations</span></span>

-   <span data-ttu-id="d136a-119">根據預設，您必須是 AGPM 系統管理員（完全控制）才能執行此程式。</span><span class="sxs-lookup"><span data-stu-id="d136a-119">By default, you must be an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="d136a-120">具體說來，您必須具有網域的 [**修改安全性**] 許可權。</span><span class="sxs-lookup"><span data-stu-id="d136a-120">Specifically, you must have **Modify Security** permission for the domain.</span></span>

-   <span data-ttu-id="d136a-121">若要委派使用 AGPM 的群組原則管理員的讀取存取權，您必須授與其**清單內容**，以及**讀取設定**許可權。</span><span class="sxs-lookup"><span data-stu-id="d136a-121">To delegate read access to Group Policy administrators who use AGPM, you must grant them **List Contents** as well as **Read Settings** permissions.</span></span> <span data-ttu-id="d136a-122">這可讓他們在 AGPM 的 [**目錄**] 索引標籤上查看 gpo。</span><span class="sxs-lookup"><span data-stu-id="d136a-122">This enables them to view GPOs on the **Contents** tab of AGPM.</span></span> <span data-ttu-id="d136a-123">設定要套用至**此物件及嵌套物件**的許可權。</span><span class="sxs-lookup"><span data-stu-id="d136a-123">Set the permission to apply to **This object and nested objects**.</span></span> <span data-ttu-id="d136a-124">其他許可權必須明確委派。</span><span class="sxs-lookup"><span data-stu-id="d136a-124">Other permissions must be explicitly delegated.</span></span>

-   <span data-ttu-id="d136a-125">針對已部署的 GPO 複本，**必須授與**編輯許可權，才能完整地使用 [群組原則軟體安裝]。</span><span class="sxs-lookup"><span data-stu-id="d136a-125">Editors must be granted **Read** permission for the deployed copy of a GPO to make full use of Group Policy Software Installation.</span></span>

-   <span data-ttu-id="d136a-126">[群組原則建立者擁有者] 群組中的成員資格應該受到限制，因此不會用來避開對 Gpo 存取的 AGPM 管理。</span><span class="sxs-lookup"><span data-stu-id="d136a-126">Membership in the Group Policy Creator Owners group should be restricted so that it is not used to circumvent AGPM management of access to GPOs.</span></span> <span data-ttu-id="d136a-127">（在 [**群組原則管理主控台**] 中，按一下要管理 gpo 的林和網域中的 [**群組原則物件**]，按一下 [**委派**]，然後設定設定以符合貴組織的需求。）</span><span class="sxs-lookup"><span data-stu-id="d136a-127">(In the **Group Policy Management Console**, click **Group Policy Objects** in the forest and domain in which you want to manage GPOs, click **Delegation**, and then configure the settings to meet the needs of your organization.)</span></span>

### <span data-ttu-id="d136a-128">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="d136a-128">Additional references</span></span>

-   [<span data-ttu-id="d136a-129">執行 AGPM 系統管理員工作</span><span class="sxs-lookup"><span data-stu-id="d136a-129">Performing AGPM Administrator Tasks</span></span>](performing-agpm-administrator-tasks.md)

 

 





