---
title: 委派管理實際執行環境的存取權
description: 委派管理實際執行環境的存取權
author: dansimp
ms.assetid: 4c670581-8c47-41ea-80eb-02846ff1ec1f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a3920a8ba5835cbbcb8a74f0af4e3ca1e1c5f43f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801933"
---
# <span data-ttu-id="8ce89-103">委派管理實際執行環境的存取權</span><span class="sxs-lookup"><span data-stu-id="8ce89-103">Delegate Access to the Production Environment</span></span>


<span data-ttu-id="8ce89-104">在 [高級群組原則管理（AGPM）] 中，您可以在網域的生產環境中變更群組原則物件（Gpo）的存取權，取代這些 Gpo 上任何現有的許可權。</span><span class="sxs-lookup"><span data-stu-id="8ce89-104">In Advanced Group Policy Management (AGPM), you can change access to Group Policy Objects (GPOs) in the production environment of the domain, replacing any existing permissions on those GPOs.</span></span> <span data-ttu-id="8ce89-105">您可以在網域層級設定許可權，在客戶不使用群組原則管理主控台（GPMC）中的 [**變更控制**] 資料夾時，允許或防止使用者編輯、刪除或修改生產環境中的 gpo 的安全性。</span><span class="sxs-lookup"><span data-stu-id="8ce89-105">You can configure permissions at the domain level to either allow or prevent users from editing, deleting, or modifying the security of GPOs in the production environment when they are not using the **Change Control** folder in the Group Policy Management Console (GPMC).</span></span>

**<span data-ttu-id="8ce89-106">注意</span><span class="sxs-lookup"><span data-stu-id="8ce89-106">Note</span></span>**  
-   <span data-ttu-id="8ce89-107">變更對生產環境的存取權委派的方式，不會影響使用者連結 Gpo 的能力。</span><span class="sxs-lookup"><span data-stu-id="8ce89-107">Changing how access to the production environment is delegated does not affect users' ability to link GPOs.</span></span>

-   <span data-ttu-id="8ce89-108">當 Gpo 受到控制或部署時，除了具有 [**讀取**] 和 [套用] 許可權的帳戶之外 **，還會**移除任何其他帳戶的存取權。</span><span class="sxs-lookup"><span data-stu-id="8ce89-108">When GPOs are controlled or deployed, access for any other accounts except those with **Read** and **Apply** permissions is removed.</span></span>

 

<span data-ttu-id="8ce89-109">具有 AGPM 系統管理員角色的使用者帳戶（完全控制），或需要高級群組原則管理（AGPM）中的必要許可權，才能完成此程式。</span><span class="sxs-lookup"><span data-stu-id="8ce89-109">A user account that has either the role of AGPM Administrator (Full Control) or the necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="8ce89-110">請參閱本主題中的「其他注意事項」中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="8ce89-110">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="8ce89-111">若要變更網域的生產環境中 Gpo 的存取權</span><span class="sxs-lookup"><span data-stu-id="8ce89-111">To change access to GPOs in the production environment of the domain</span></span>**

1.  <span data-ttu-id="8ce89-112">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="8ce89-112">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="8ce89-113">按一下 [**生產委託**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="8ce89-113">Click the **Production Delegation** tab.</span></span>

3.  <span data-ttu-id="8ce89-114">若要針對沒有生產環境存取權的使用者或群組新增許可權，或針對有存取權的使用者或群組取代許可權：</span><span class="sxs-lookup"><span data-stu-id="8ce89-114">To add permissions for a user or group that does not have access to the production environment, or to replace the permissions for a user or group that does have access:</span></span>

    1.  <span data-ttu-id="8ce89-115">按一下 [**新增**]，選取使用者或群組，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="8ce89-115">Click **Add**, select a user or group, and then click **OK**.</span></span>

    2.  <span data-ttu-id="8ce89-116">針對生產環境選取要委派給該使用者或群組的許可權，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="8ce89-116">Select permissions to delegate to that user or group for the production environment, and then click **OK**.</span></span>

4.  <span data-ttu-id="8ce89-117">若要移除使用者或群組對生產環境的擁有權限，請選取該使用者或群組，按一下 [**移除**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="8ce89-117">To remove all permissions to the production environment for a user or group, select the user or group, click **Remove**, and then click **OK**.</span></span>

### <span data-ttu-id="8ce89-118">其他考量</span><span class="sxs-lookup"><span data-stu-id="8ce89-118">Additional considerations</span></span>

-   <span data-ttu-id="8ce89-119">根據預設，您必須是 AGPM 系統管理員（完全控制）才能執行此程式。</span><span class="sxs-lookup"><span data-stu-id="8ce89-119">By default, you must be an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="8ce89-120">具體說來，您必須具有網域的 [**修改安全性**] 許可權。</span><span class="sxs-lookup"><span data-stu-id="8ce89-120">Specifically, you must have **Modify Security** permission for the domain.</span></span>

-   <span data-ttu-id="8ce89-121">無法在 [**生產委派**] 索引標籤上變更 AGPM 服務帳戶的許可權。</span><span class="sxs-lookup"><span data-stu-id="8ce89-121">Permissions for the AGPM Service Account cannot be changed on the **Production Delegation** tab.</span></span>

-   <span data-ttu-id="8ce89-122">根據預設，下列帳戶在生產環境中擁有 Gpo 的許可權：</span><span class="sxs-lookup"><span data-stu-id="8ce89-122">By default, the following accounts have permissions for GPOs in the production environment:</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="8ce89-123">帳戶</span><span class="sxs-lookup"><span data-stu-id="8ce89-123">Account</span></span></th>
    <th align="left"><span data-ttu-id="8ce89-124">Gpo 的預設許可權</span><span class="sxs-lookup"><span data-stu-id="8ce89-124">Default Permissions for GPOs</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="8ce89-125">&lt;AGPM 服務帳戶&gt;</span><span class="sxs-lookup"><span data-stu-id="8ce89-125">&lt;AGPM Service Account&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="8ce89-126">編輯設定、刪除、修改安全性</span><span class="sxs-lookup"><span data-stu-id="8ce89-126">Edit Settings, Delete, Modify Security</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="8ce89-127">已驗證使用者</span><span class="sxs-lookup"><span data-stu-id="8ce89-127">Authenticated Users</span></span></p></td>
    <td align="left"><p><span data-ttu-id="8ce89-128">讀取、套用</span><span class="sxs-lookup"><span data-stu-id="8ce89-128">Read, Apply</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="8ce89-129">網域管理員</span><span class="sxs-lookup"><span data-stu-id="8ce89-129">Domain Admins</span></span></p></td>
    <td align="left"><p><span data-ttu-id="8ce89-130">編輯設定、刪除、修改安全性</span><span class="sxs-lookup"><span data-stu-id="8ce89-130">Edit Settings, Delete, Modify Security</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="8ce89-131">企業系統管理員</span><span class="sxs-lookup"><span data-stu-id="8ce89-131">Enterprise Admins</span></span></p></td>
    <td align="left"><p><span data-ttu-id="8ce89-132">編輯設定、刪除、修改安全性</span><span class="sxs-lookup"><span data-stu-id="8ce89-132">Edit Settings, Delete, Modify Security</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="8ce89-133">企業網網域控制站</span><span class="sxs-lookup"><span data-stu-id="8ce89-133">Enterprise Domain Controllers</span></span></p></td>
    <td align="left"><p><span data-ttu-id="8ce89-134">讀取</span><span class="sxs-lookup"><span data-stu-id="8ce89-134">Read</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="8ce89-135">系統</span><span class="sxs-lookup"><span data-stu-id="8ce89-135">System</span></span></p></td>
    <td align="left"><p><span data-ttu-id="8ce89-136">編輯設定、刪除、修改安全性</span><span class="sxs-lookup"><span data-stu-id="8ce89-136">Edit Settings, Delete, Modify Security</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

-   <span data-ttu-id="8ce89-137">[群組原則建立人擁有者] 群組中的成員資格應該受到限制，不會使用 soit 來避開對 Gpo 存取的 AGPM 管理。</span><span class="sxs-lookup"><span data-stu-id="8ce89-137">Membership in the Group Policy Creator Owners group should be restricted, soit is not used to circumvent AGPM management of access to GPOs.</span></span> <span data-ttu-id="8ce89-138">（在 [**群組原則管理主控台**] 中，按一下要管理 gpo 的林和網域中的 [**群組原則物件**]，按一下 [**委派**]，然後設定設定以符合貴組織的需求。）</span><span class="sxs-lookup"><span data-stu-id="8ce89-138">(In the **Group Policy Management Console**, click **Group Policy Objects** in the forest and domain in which you want to manage GPOs, click **Delegation**, and then configure the settings to meet the needs of your organization.)</span></span>

### <span data-ttu-id="8ce89-139">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="8ce89-139">Additional references</span></span>

-   [<span data-ttu-id="8ce89-140">設定進階群組原則管理</span><span class="sxs-lookup"><span data-stu-id="8ce89-140">Configuring Advanced Group Policy Management</span></span>](configuring-advanced-group-policy-management-agpm40.md)

 

 





