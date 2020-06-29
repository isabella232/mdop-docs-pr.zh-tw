---
title: 內容索引標籤功能
description: 內容索引標籤功能
author: dansimp
ms.assetid: f1f4849d-bf94-47d5-ad81-0eee33abcaca
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 081cffb7c2871d0e49abd229ec06773726483f2b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801998"
---
# <span data-ttu-id="6aa41-103">內容索引標籤功能</span><span class="sxs-lookup"><span data-stu-id="6aa41-103">Contents Tab Features</span></span>


<span data-ttu-id="6aa41-104">[**內容**] 索引標籤內的每個次要索引標籤都有兩個區段： [**群組原則] 物件\*\*\*\*與 [群組**</span><span class="sxs-lookup"><span data-stu-id="6aa41-104">Each secondary tab within the **Contents** tab has two sections—**Group Policy objects** and **Groups and Users**.</span></span>

## <span data-ttu-id="6aa41-105">[群組原則物件] 區段</span><span class="sxs-lookup"><span data-stu-id="6aa41-105">Group Policy objects section</span></span>


<span data-ttu-id="6aa41-106">[**群組原則物件**] 區段會顯示群組原則物件（gpo）的篩選清單，並識別每個 GPO 的下列屬性。</span><span class="sxs-lookup"><span data-stu-id="6aa41-106">The **Group Policy objects** section displays a filtered list of Group Policy Objects (GPOs) and identifies the following attributes for each GPO.</span></span> <span data-ttu-id="6aa41-107">您可以使用**搜尋**方塊來搜尋具有特定屬性的 gpo。</span><span class="sxs-lookup"><span data-stu-id="6aa41-107">You can use the **Search** box to search for GPOs with specific attributes.</span></span> <span data-ttu-id="6aa41-108">如需詳細資訊，請參閱[搜尋及篩選 Gpo 清單](search-and-filter-the-list-of-gpos.md)。</span><span class="sxs-lookup"><span data-stu-id="6aa41-108">For more information, see [Search and Filter the List of GPOs](search-and-filter-the-list-of-gpos.md).</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6aa41-109">GPO 屬性</span><span class="sxs-lookup"><span data-stu-id="6aa41-109">GPO attribute</span></span></th>
<th align="left"><span data-ttu-id="6aa41-110">描述</span><span class="sxs-lookup"><span data-stu-id="6aa41-110">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="6aa41-111">Name</span><span class="sxs-lookup"><span data-stu-id="6aa41-111">Name</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="6aa41-112">GPO 的名稱。</span><span class="sxs-lookup"><span data-stu-id="6aa41-112">Name of the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="6aa41-113">狀態</span><span class="sxs-lookup"><span data-stu-id="6aa41-113">State</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="6aa41-114">所選 GPO 的狀態</span><span class="sxs-lookup"><span data-stu-id="6aa41-114">The state of the selected GPO</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="6aa41-115">變更者</span><span class="sxs-lookup"><span data-stu-id="6aa41-115">Changed By</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="6aa41-116">已檢入或部署所選 GPO 之核准者的編輯者。</span><span class="sxs-lookup"><span data-stu-id="6aa41-116">The Editor who checked in or the Approver who deployed the selected GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="6aa41-117">變更日期</span><span class="sxs-lookup"><span data-stu-id="6aa41-117">Change Date</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="6aa41-118">針對受控制的 GPO，在經過修改或取出後將其簽核至已修改的最近日期。</span><span class="sxs-lookup"><span data-stu-id="6aa41-118">For a controlled GPO, the most recent date it was checked in after being modified or checked out to be modified.</span></span> <span data-ttu-id="6aa41-119">如果是不受控制的 GPO，就是上次修改的日期。</span><span class="sxs-lookup"><span data-stu-id="6aa41-119">For an uncontrolled GPO, the date when it was last modified.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="6aa41-120">留言</span><span class="sxs-lookup"><span data-stu-id="6aa41-120">Comment</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="6aa41-121">在修改時，由檢入或部署 GPO 的人員輸入的留言。</span><span class="sxs-lookup"><span data-stu-id="6aa41-121">A comment entered by the person who checked in or deployed a GPO at the time that it was modified.</span></span> <span data-ttu-id="6aa41-122">在需要回滾至較舊版本的情況下，識別版本的詳細資訊時很有用。</span><span class="sxs-lookup"><span data-stu-id="6aa41-122">Useful for identifying the specifics of the version in case of the need to roll back to an earlier version.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="6aa41-123">電腦版本</span><span class="sxs-lookup"><span data-stu-id="6aa41-123">Computer Version</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="6aa41-124">GPO 的 [電腦設定] 元件的自動產生版本。</span><span class="sxs-lookup"><span data-stu-id="6aa41-124">Automatically generated version of the Computer Configuration part of the GPO.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="6aa41-125">使用者版本</span><span class="sxs-lookup"><span data-stu-id="6aa41-125">User Version</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="6aa41-126">GPO 的使用者設定部分自動產生的版本。</span><span class="sxs-lookup"><span data-stu-id="6aa41-126">Automatically generated version of the User Configuration part of the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="6aa41-127">GPO 狀態</span><span class="sxs-lookup"><span data-stu-id="6aa41-127">GPO Status</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="6aa41-128">您可以個別管理電腦配置和使用者設定。</span><span class="sxs-lookup"><span data-stu-id="6aa41-128">The Computer Configuration and the User Configuration can be managed separately.</span></span> <span data-ttu-id="6aa41-129">GPO 狀態表示已啟用 GPO 的哪些部分。</span><span class="sxs-lookup"><span data-stu-id="6aa41-129">The GPO Status indicates which portions of the GPO are enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="6aa41-130">WMI 篩選器</span><span class="sxs-lookup"><span data-stu-id="6aa41-130">WMI Filter</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="6aa41-131">顯示適用于此 GPO 的任何 WMI 篩選器。</span><span class="sxs-lookup"><span data-stu-id="6aa41-131">Display any WMI filters that are applied to this GPO.</span></span> <span data-ttu-id="6aa41-132">WMI 篩選是在 GPMC 的 [ <strong> Wmi 篩選] </strong> 資料夾中，在 GPMC 的主控台樹中針對該域進行管理。</span><span class="sxs-lookup"><span data-stu-id="6aa41-132">WMI filters are managed under the <strong>WMI Filters</strong> folder for the domain in the console tree of the GPMC.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="6aa41-133">[群組與使用者] 區段</span><span class="sxs-lookup"><span data-stu-id="6aa41-133">Groups and Users section</span></span>


<span data-ttu-id="6aa41-134">選取 GPO 時，[**群組與使用者**] 區段會顯示群組和使用者有權存取該 gpo 的清單。</span><span class="sxs-lookup"><span data-stu-id="6aa41-134">When a GPO is selected, the **Groups and Users** section displays a list of the groups and users with access to that GPO.</span></span> <span data-ttu-id="6aa41-135">針對每個群組或使用者顯示允許的許可權和繼承。</span><span class="sxs-lookup"><span data-stu-id="6aa41-135">The allowed permissions and inheritance are displayed for each group or user.</span></span> <span data-ttu-id="6aa41-136">AGPM 系統管理員可以使用標準 AGPM 角色（[編輯者]、[核准者]、[審查員] 和 [AGPM 管理員]）或自訂的許可權組合來設定許可權。</span><span class="sxs-lookup"><span data-stu-id="6aa41-136">An AGPM Administrator can configure permissions using either standard AGPM roles (Editor, Approver, Reviewer, and AGPM Administrator) or a customized combination of permissions.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6aa41-137">Button</span><span class="sxs-lookup"><span data-stu-id="6aa41-137">Button</span></span></th>
<th align="left"><span data-ttu-id="6aa41-138">效果</span><span class="sxs-lookup"><span data-stu-id="6aa41-138">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="6aa41-139">新增</span><span class="sxs-lookup"><span data-stu-id="6aa41-139">Add</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="6aa41-140">在安全性說明符中加入新專案。</span><span class="sxs-lookup"><span data-stu-id="6aa41-140">Add a new entry to the security descriptor.</span></span> <span data-ttu-id="6aa41-141">您可以新增 Active Directory 中的任何使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="6aa41-141">Any user or group in Active Directory can be added.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="6aa41-142">移除</span><span class="sxs-lookup"><span data-stu-id="6aa41-142">Remove</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="6aa41-143">從 [存取控制] 清單中移除選取的專案。</span><span class="sxs-lookup"><span data-stu-id="6aa41-143">Remove the selected entry from the Access Control List.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="6aa41-144">屬性</span><span class="sxs-lookup"><span data-stu-id="6aa41-144">Properties</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="6aa41-145">顯示所選物件的屬性。</span><span class="sxs-lookup"><span data-stu-id="6aa41-145">Display the properties for the selected object.</span></span> <span data-ttu-id="6aa41-146">[屬性] 頁面與 <strong> Active Directory 使用者和電腦中的物件所顯示的內容相同 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="6aa41-146">The properties page is the same one displayed for an object in <strong>Active Directory Users and Computers</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="6aa41-147">進階</span><span class="sxs-lookup"><span data-stu-id="6aa41-147">Advanced</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="6aa41-148">開啟 [ <strong> 存取控制清單編輯器] </strong> 。</span><span class="sxs-lookup"><span data-stu-id="6aa41-148">Open the <strong>Access Control List Editor</strong>.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="6aa41-149">其他考量</span><span class="sxs-lookup"><span data-stu-id="6aa41-149">Additional considerations</span></span>

-   <span data-ttu-id="6aa41-150">如需有關特定工作的角色與許可權的相關資訊，請參閱[執行 AGPM 管理員](performing-agpm-administrator-tasks-agpm40.md)工作、[執行編輯](performing-editor-tasks-agpm40.md)程式工作、[執行核准者](performing-approver-tasks-agpm40.md)工作及[執行審查員](performing-reviewer-tasks-agpm40.md)工作中的工作。</span><span class="sxs-lookup"><span data-stu-id="6aa41-150">For information about roles and permissions related to specific tasks, see the tasks under [Performing AGPM Administrator Tasks](performing-agpm-administrator-tasks-agpm40.md), [Performing Editor Tasks](performing-editor-tasks-agpm40.md), [Performing Approver Tasks](performing-approver-tasks-agpm40.md), and [Performing Reviewer Tasks](performing-reviewer-tasks-agpm40.md).</span></span>

### <span data-ttu-id="6aa41-151">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="6aa41-151">Additional references</span></span>

-   [<span data-ttu-id="6aa41-152">內容索引標籤</span><span class="sxs-lookup"><span data-stu-id="6aa41-152">Contents Tab</span></span>](contents-tab-agpm40.md)

 

 





