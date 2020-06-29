---
title: 網域委派索引標籤
description: 網域委派索引標籤
author: dansimp
ms.assetid: 15a9bfff-e25b-4b62-9ebc-521a5f4eae96
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d49083bcefe6c7edcb3a95dc63d2249826d50327
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801893"
---
# <span data-ttu-id="66a7c-103">網域委派索引標籤</span><span class="sxs-lookup"><span data-stu-id="66a7c-103">Domain Delegation Tab</span></span>


<span data-ttu-id="66a7c-104">[**變更控制**] 窗格上的 [**網域委派**] 索引標籤提供對封存擁有網域層級存取權的群群組原則管理員清單，並指出每個檔案的角色。</span><span class="sxs-lookup"><span data-stu-id="66a7c-104">The **Domain Delegation** tab on the **Change Control** pane provides a list of Group Policy administrators who have domain-level access to the archive and indicates the roles of each.</span></span> <span data-ttu-id="66a7c-105">此外，這個索引標籤可讓 [AGPM 管理員] （完全控制）為編輯者、核准者、檢閱者及其他 AGPM 管理員設定網域層級許可權。</span><span class="sxs-lookup"><span data-stu-id="66a7c-105">Additionally, this tab enables AGPM Administrators (Full Control) to configure domain-level permissions for Editors, Approvers, Reviewers, and other AGPM Administrators.</span></span> <span data-ttu-id="66a7c-106">[**網域委派**] 索引標籤上有兩個區段，即設定電子郵件通知，以及網域層級的 [高級群組原則管理（AGPM）] 的 [以角色為基礎] 委派。</span><span class="sxs-lookup"><span data-stu-id="66a7c-106">There are two sections on the **Domain Delegation** tab—configuration of e-mail notification and role-based delegation for Advanced Group Policy Management (AGPM) at the domain level.</span></span>

## <span data-ttu-id="66a7c-107">電子郵件通知的設定</span><span class="sxs-lookup"><span data-stu-id="66a7c-107">Configuration of e-mail notification</span></span>


<span data-ttu-id="66a7c-108">此索引標籤的 [電子郵件通知] 區段會識別將在 AGPM 中掛起作業時收到通知的核准者。</span><span class="sxs-lookup"><span data-stu-id="66a7c-108">The e-mail notification section of this tab identifies the Approvers that will receive notification when operations are pending in AGPM.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="66a7c-109">設定</span><span class="sxs-lookup"><span data-stu-id="66a7c-109">Setting</span></span></th>
<th align="left"><span data-ttu-id="66a7c-110">描述</span><span class="sxs-lookup"><span data-stu-id="66a7c-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="66a7c-111">從</span><span class="sxs-lookup"><span data-stu-id="66a7c-111">From</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="66a7c-112">將通知傳送給核准者的 AGPM 別名。</span><span class="sxs-lookup"><span data-stu-id="66a7c-112">The AGPM alias from which notification is sent to Approvers.</span></span> <span data-ttu-id="66a7c-113">在有多個網域的環境中，這可以是整個環境中的相同別名，或是每個網域的不同別名。</span><span class="sxs-lookup"><span data-stu-id="66a7c-113">In an environment with multiple domains, this can be the same alias throughout the environment or a different alias for each domain.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="66a7c-114">以</span><span class="sxs-lookup"><span data-stu-id="66a7c-114">To</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="66a7c-115">要傳送通知之核准者的電子郵件地址的逗號分隔清單</span><span class="sxs-lookup"><span data-stu-id="66a7c-115">A comma-delimited list of e-mail addresses of Approvers to whom notification is to be sent</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="66a7c-116">SMTP 伺服器</span><span class="sxs-lookup"><span data-stu-id="66a7c-116">SMTP server</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="66a7c-117">電子郵件伺服器的名稱，例如 mail.contoso.com</span><span class="sxs-lookup"><span data-stu-id="66a7c-117">The name of the e-mail server, such as mail.contoso.com</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="66a7c-118">使用者名稱</span><span class="sxs-lookup"><span data-stu-id="66a7c-118">User name</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="66a7c-119">擁有 SMTP 伺服器存取權的使用者</span><span class="sxs-lookup"><span data-stu-id="66a7c-119">A user with access to the SMTP server</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="66a7c-120">密碼</span><span class="sxs-lookup"><span data-stu-id="66a7c-120">Password</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="66a7c-121">SMTP 伺服器驗證的使用者密碼</span><span class="sxs-lookup"><span data-stu-id="66a7c-121">User's password for authentication to the SMTP server</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="66a7c-122">確認密碼</span><span class="sxs-lookup"><span data-stu-id="66a7c-122">Confirm password</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="66a7c-123">確認使用者的密碼</span><span class="sxs-lookup"><span data-stu-id="66a7c-123">Confirm user's password</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="66a7c-124">網域層級角色委派</span><span class="sxs-lookup"><span data-stu-id="66a7c-124">Domain-level role-based delegation</span></span>


<span data-ttu-id="66a7c-125">此索引標籤的 [以角色為基礎的委派] 區段會顯示，並讓 AGPM 管理員針對網域上的每個群組和使用者委派允許、拒絕和繼承的許可權，並可存取封存。</span><span class="sxs-lookup"><span data-stu-id="66a7c-125">The role-based delegation section of this tab displays and enables an AGPM Administrator to delegate allowed, denied, and inherited permissions for each group and user on the domain with access to the archive.</span></span> <span data-ttu-id="66a7c-126">AGPM 管理員可以使用標準的 AGPM 角色（[編輯者]、[核准者]、[審查員] 和 [AGPM 系統管理員]），或每個群組原則管理員的自訂許可權組合來設定全域許可權。</span><span class="sxs-lookup"><span data-stu-id="66a7c-126">An AGPM Administrator can configure domain-wide permissions using either standard AGPM roles (Editor, Approver, Reviewer, and AGPM Administrator) or a customized combination of permissions for each Group Policy administrator.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="66a7c-127">Button</span><span class="sxs-lookup"><span data-stu-id="66a7c-127">Button</span></span></th>
<th align="left"><span data-ttu-id="66a7c-128">效果</span><span class="sxs-lookup"><span data-stu-id="66a7c-128">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="66a7c-129">新增</span><span class="sxs-lookup"><span data-stu-id="66a7c-129">Add</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="66a7c-130">在安全性說明符中加入新專案。</span><span class="sxs-lookup"><span data-stu-id="66a7c-130">Add a new entry to the security descriptor.</span></span> <span data-ttu-id="66a7c-131">Active Directory 中的任何使用者或群組都可以新增為群組原則系統管理員。</span><span class="sxs-lookup"><span data-stu-id="66a7c-131">Any users or groups in Active Directory can be added as Group Policy administrators.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="66a7c-132">移除</span><span class="sxs-lookup"><span data-stu-id="66a7c-132">Remove</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="66a7c-133">從 [存取控制] 清單中移除選取的 [群組原則管理員]。</span><span class="sxs-lookup"><span data-stu-id="66a7c-133">Remove the selected Group Policy administrators from the Access Control List.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="66a7c-134">屬性</span><span class="sxs-lookup"><span data-stu-id="66a7c-134">Properties</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="66a7c-135">顯示所選群組原則系統管理員的屬性。</span><span class="sxs-lookup"><span data-stu-id="66a7c-135">Display the properties for the selected Group Policy administrators.</span></span> <span data-ttu-id="66a7c-136">[屬性] 頁面與 <strong> Active Directory 使用者和電腦中的物件所顯示的內容相同 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="66a7c-136">The properties page is the same one displayed for an object in <strong>Active Directory User and Computers</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="66a7c-137">進階</span><span class="sxs-lookup"><span data-stu-id="66a7c-137">Advanced</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="66a7c-138">開啟 [ <strong> 存取控制清單編輯器] </strong> 。</span><span class="sxs-lookup"><span data-stu-id="66a7c-138">Open the <strong>Access Control List Editor</strong>.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="66a7c-139">其他考量</span><span class="sxs-lookup"><span data-stu-id="66a7c-139">Additional considerations</span></span>

-   <span data-ttu-id="66a7c-140">如需有關特定工作的角色與許可權的相關資訊，請參閱[執行 AGPM 管理員](performing-agpm-administrator-tasks.md)工作、[執行編輯](performing-editor-tasks.md)程式工作、[執行核准者](performing-approver-tasks.md)工作及[執行審查員](performing-reviewer-tasks.md)工作中的工作。</span><span class="sxs-lookup"><span data-stu-id="66a7c-140">For information about roles and permissions related to specific tasks, see the tasks under [Performing AGPM Administrator Tasks](performing-agpm-administrator-tasks.md), [Performing Editor Tasks](performing-editor-tasks.md), [Performing Approver Tasks](performing-approver-tasks.md), and [Performing Reviewer Tasks](performing-reviewer-tasks.md).</span></span>

### <span data-ttu-id="66a7c-141">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="66a7c-141">Additional references</span></span>

-   [<span data-ttu-id="66a7c-142">使用者介面：進階群組原則管理</span><span class="sxs-lookup"><span data-stu-id="66a7c-142">User Interface: Advanced Group Policy Management</span></span>](user-interface-advanced-group-policy-management.md)

-   [<span data-ttu-id="66a7c-143">執行 AGPM 系統管理員工作</span><span class="sxs-lookup"><span data-stu-id="66a7c-143">Performing AGPM Administrator Tasks</span></span>](performing-agpm-administrator-tasks.md)

 

 





