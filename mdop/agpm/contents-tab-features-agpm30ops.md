---
title: 內容索引標籤功能
description: 內容索引標籤功能
author: dansimp
ms.assetid: 725f025a-c30a-4d07-add1-4e0ed9a1a5fd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f64aad16a3335d78641812121692f6d5f6436ee1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802005"
---
# <span data-ttu-id="9432c-103">內容索引標籤功能</span><span class="sxs-lookup"><span data-stu-id="9432c-103">Contents Tab Features</span></span>


<span data-ttu-id="9432c-104">[**內容**] 索引標籤內的每個次要索引標籤都有兩個區段： [**群組原則] 物件\*\*\*\*與 [群組**</span><span class="sxs-lookup"><span data-stu-id="9432c-104">Each secondary tab within the **Contents** tab has two sections—**Group Policy objects** and **Groups and Users**.</span></span>

## <span data-ttu-id="9432c-105">[群組原則物件] 區段</span><span class="sxs-lookup"><span data-stu-id="9432c-105">Group Policy objects section</span></span>


<span data-ttu-id="9432c-106">[**群組原則物件**] 區段會顯示群組原則物件（gpo）的篩選清單，並識別每個 GPO 的下列屬性：</span><span class="sxs-lookup"><span data-stu-id="9432c-106">The **Group Policy objects** section displays a filtered list of Group Policy Objects (GPOs) and identifies the following attributes for each GPO:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9432c-107">GPO 屬性</span><span class="sxs-lookup"><span data-stu-id="9432c-107">GPO attribute</span></span></th>
<th align="left"><span data-ttu-id="9432c-108">描述</span><span class="sxs-lookup"><span data-stu-id="9432c-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="9432c-109">Name</span><span class="sxs-lookup"><span data-stu-id="9432c-109">Name</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="9432c-110">GPO 的名稱。</span><span class="sxs-lookup"><span data-stu-id="9432c-110">Name of the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="9432c-111">狀態</span><span class="sxs-lookup"><span data-stu-id="9432c-111">State</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="9432c-112">所選 GPO 的狀態</span><span class="sxs-lookup"><span data-stu-id="9432c-112">The state of the selected GPO</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="9432c-113">變更者</span><span class="sxs-lookup"><span data-stu-id="9432c-113">Changed By</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="9432c-114">已檢入或部署所選 GPO 之核准者的編輯者。</span><span class="sxs-lookup"><span data-stu-id="9432c-114">The Editor who checked in or the Approver who deployed the selected GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="9432c-115">變更日期</span><span class="sxs-lookup"><span data-stu-id="9432c-115">Change Date</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="9432c-116">針對受控制的 GPO，在經過修改或取出後將其簽核至已修改的最近日期。</span><span class="sxs-lookup"><span data-stu-id="9432c-116">For a controlled GPO, the most recent date it was checked in after being modified or checked out to be modified.</span></span> <span data-ttu-id="9432c-117">如果是不受控制的 GPO，就是上次修改的日期。</span><span class="sxs-lookup"><span data-stu-id="9432c-117">For an uncontrolled GPO, the date when it was last modified.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="9432c-118">留言</span><span class="sxs-lookup"><span data-stu-id="9432c-118">Comment</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="9432c-119">在修改時，由檢入或部署 GPO 的人員輸入的留言。</span><span class="sxs-lookup"><span data-stu-id="9432c-119">A comment entered by the person who checked in or deployed a GPO at the time that it was modified.</span></span> <span data-ttu-id="9432c-120">在需要回滾到前一個版本的情況下，識別版本的詳細資訊時很有用。</span><span class="sxs-lookup"><span data-stu-id="9432c-120">Useful for identifying the specifics of the version in case of the need to roll back to a previous version.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="9432c-121">電腦版本</span><span class="sxs-lookup"><span data-stu-id="9432c-121">Computer Version</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="9432c-122">GPO 的電腦設定部分自動產生的版本。</span><span class="sxs-lookup"><span data-stu-id="9432c-122">Automatically generated version of the Computer Configuration portion of the GPO.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="9432c-123">使用者版本</span><span class="sxs-lookup"><span data-stu-id="9432c-123">User Version</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="9432c-124">GPO 的使用者設定部分的自動產生版本。</span><span class="sxs-lookup"><span data-stu-id="9432c-124">Automatically generated version of the User Configuration portion of the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="9432c-125">GPO 狀態</span><span class="sxs-lookup"><span data-stu-id="9432c-125">GPO Status</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="9432c-126">您可以個別管理電腦配置和使用者設定。</span><span class="sxs-lookup"><span data-stu-id="9432c-126">The Computer Configuration and the User Configuration can be managed separately.</span></span> <span data-ttu-id="9432c-127">GPO 狀態表示已啟用 GPO 的哪些部分。</span><span class="sxs-lookup"><span data-stu-id="9432c-127">The GPO Status indicates which portions of the GPO are enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="9432c-128">WMI 篩選器</span><span class="sxs-lookup"><span data-stu-id="9432c-128">WMI Filter</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="9432c-129">顯示適用于此 GPO 的任何 WMI 篩選器。</span><span class="sxs-lookup"><span data-stu-id="9432c-129">Display any WMI filters that are applied to this GPO.</span></span> <span data-ttu-id="9432c-130">WMI 篩選是在 GPMC 的 [ <strong> Wmi 篩選] </strong> 資料夾中，在 GPMC 的主控台樹中針對該域進行管理。</span><span class="sxs-lookup"><span data-stu-id="9432c-130">WMI filters are managed under the <strong>WMI Filters</strong> folder for the domain in the console tree of the GPMC.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="9432c-131">[群組與使用者] 區段</span><span class="sxs-lookup"><span data-stu-id="9432c-131">Groups and Users section</span></span>


<span data-ttu-id="9432c-132">選取 GPO 時，[**群組與使用者**] 區段會顯示群組和使用者有權存取該 gpo 的清單。</span><span class="sxs-lookup"><span data-stu-id="9432c-132">When a GPO is selected, the **Groups and Users** section displays a list of the groups and users with access to that GPO.</span></span> <span data-ttu-id="9432c-133">針對每個群組或使用者顯示允許的許可權和繼承。</span><span class="sxs-lookup"><span data-stu-id="9432c-133">The allowed permissions and inheritance are displayed for each group or user.</span></span> <span data-ttu-id="9432c-134">AGPM 系統管理員可以使用標準 AGPM 角色（[編輯者]、[核准者]、[審查員] 和 [AGPM 管理員]）或自訂的許可權組合來設定許可權。</span><span class="sxs-lookup"><span data-stu-id="9432c-134">An AGPM Administrator can configure permissions using either standard AGPM roles (Editor, Approver, Reviewer, and AGPM Administrator) or a customized combination of permissions.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9432c-135">Button</span><span class="sxs-lookup"><span data-stu-id="9432c-135">Button</span></span></th>
<th align="left"><span data-ttu-id="9432c-136">效果</span><span class="sxs-lookup"><span data-stu-id="9432c-136">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="9432c-137">新增</span><span class="sxs-lookup"><span data-stu-id="9432c-137">Add</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="9432c-138">在安全性說明符中加入新專案。</span><span class="sxs-lookup"><span data-stu-id="9432c-138">Add a new entry to the security descriptor.</span></span> <span data-ttu-id="9432c-139">您可以新增 Active Directory 中的任何使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="9432c-139">Any user or group in Active Directory can be added.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="9432c-140">移除</span><span class="sxs-lookup"><span data-stu-id="9432c-140">Remove</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="9432c-141">從 [存取控制] 清單中移除選取的專案。</span><span class="sxs-lookup"><span data-stu-id="9432c-141">Remove the selected entry from the Access Control List.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="9432c-142">屬性</span><span class="sxs-lookup"><span data-stu-id="9432c-142">Properties</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="9432c-143">顯示所選物件的屬性。</span><span class="sxs-lookup"><span data-stu-id="9432c-143">Display the properties for the selected object.</span></span> <span data-ttu-id="9432c-144">[屬性] 頁面與 <strong> Active Directory 使用者和電腦中的物件所顯示的內容相同 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="9432c-144">The properties page is the same one displayed for an object in <strong>Active Directory Users and Computers</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="9432c-145">進階</span><span class="sxs-lookup"><span data-stu-id="9432c-145">Advanced</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="9432c-146">開啟 [ <strong> 存取控制清單編輯器] </strong> 。</span><span class="sxs-lookup"><span data-stu-id="9432c-146">Open the <strong>Access Control List Editor</strong>.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="9432c-147">其他考量</span><span class="sxs-lookup"><span data-stu-id="9432c-147">Additional considerations</span></span>

-   <span data-ttu-id="9432c-148">如需有關特定工作的角色與許可權的相關資訊，請參閱[執行 AGPM 管理員](performing-agpm-administrator-tasks-agpm30ops.md)工作、[執行編輯](performing-editor-tasks-agpm30ops.md)程式工作、[執行核准者](performing-approver-tasks-agpm30ops.md)工作及[執行審查員](performing-reviewer-tasks-agpm30ops.md)工作中的工作。</span><span class="sxs-lookup"><span data-stu-id="9432c-148">For information about roles and permissions related to specific tasks, see the tasks under [Performing AGPM Administrator Tasks](performing-agpm-administrator-tasks-agpm30ops.md), [Performing Editor Tasks](performing-editor-tasks-agpm30ops.md), [Performing Approver Tasks](performing-approver-tasks-agpm30ops.md), and [Performing Reviewer Tasks](performing-reviewer-tasks-agpm30ops.md).</span></span>

### <span data-ttu-id="9432c-149">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="9432c-149">Additional references</span></span>

-   [<span data-ttu-id="9432c-150">內容索引標籤</span><span class="sxs-lookup"><span data-stu-id="9432c-150">Contents Tab</span></span>](contents-tab-agpm30ops.md)

 

 





