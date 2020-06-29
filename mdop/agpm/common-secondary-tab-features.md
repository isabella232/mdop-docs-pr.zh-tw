---
title: 常見的次要索引標籤功能
description: 常見的次要索引標籤功能
author: dansimp
ms.assetid: 44a15c28-944c-49c1-8534-115ce1c362ed
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 546fd4c91e060a5595b6c848015290882de933b6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802077"
---
# <span data-ttu-id="3f8af-103">常見的次要索引標籤功能</span><span class="sxs-lookup"><span data-stu-id="3f8af-103">Common Secondary Tab Features</span></span>


<span data-ttu-id="3f8af-104">每個次要索引標籤有兩個區段： [**群組原則] 物件**與 [群組]**和 [使用者**</span><span class="sxs-lookup"><span data-stu-id="3f8af-104">Each secondary tab has two sections—**Group Policy objects** and **Groups and Users**.</span></span>

## <span data-ttu-id="3f8af-105">[群組原則物件] 區段</span><span class="sxs-lookup"><span data-stu-id="3f8af-105">Group Policy objects section</span></span>


<span data-ttu-id="3f8af-106">[**群組原則物件**] 區段會顯示群組原則物件（gpo）的篩選清單，並識別每個 GPO 的下列特性：</span><span class="sxs-lookup"><span data-stu-id="3f8af-106">The **Group Policy objects** section displays a filtered list of Group Policy objects (GPOs) and identifies the following characteristics for each GPO:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3f8af-107">GPO 特性</span><span class="sxs-lookup"><span data-stu-id="3f8af-107">GPO Characteristic</span></span></th>
<th align="left"><span data-ttu-id="3f8af-108">描述</span><span class="sxs-lookup"><span data-stu-id="3f8af-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="3f8af-109">Name</span><span class="sxs-lookup"><span data-stu-id="3f8af-109">Name</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3f8af-110">群組原則物件的名稱。</span><span class="sxs-lookup"><span data-stu-id="3f8af-110">Name of the Group Policy object.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="3f8af-111">電腦（Comp）</span><span class="sxs-lookup"><span data-stu-id="3f8af-111">Computer (Comp.)</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3f8af-112">GPO 的電腦設定部分自動產生的版本。</span><span class="sxs-lookup"><span data-stu-id="3f8af-112">Automatically generated version of the Computer Configuration portion of the GPO.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="3f8af-113">使用者</span><span class="sxs-lookup"><span data-stu-id="3f8af-113">User</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3f8af-114">GPO 的使用者設定部分的自動產生版本。</span><span class="sxs-lookup"><span data-stu-id="3f8af-114">Automatically generated version of the User Configuration portion of the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="3f8af-115">狀態</span><span class="sxs-lookup"><span data-stu-id="3f8af-115">State</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3f8af-116">所選 GPO 的狀態：</span><span class="sxs-lookup"><span data-stu-id="3f8af-116">The state of the selected GPO:</span></span></p>
<p><img src="images/36f6b687-f5cc-40d1-805f-b191d1fb1ace.gif" alt="Deployed GPO icon" /> <strong><span data-ttu-id="3f8af-117">無法控制： </strong> 不由 AGPM 管理。</span><span class="sxs-lookup"><span data-stu-id="3f8af-117">Uncontrolled:</strong> Not managed by AGPM.</span></span></p>
<p><img src="images/57b610a5-1c71-4d26-9173-d04abd495fcc.gif" alt="Checked in GPO icon" /> <strong><span data-ttu-id="3f8af-118">已檢入： </strong> 適用于授權編輯者取出編輯或供群組原則管理員部署。</span><span class="sxs-lookup"><span data-stu-id="3f8af-118">Checked In:</strong> Available for authorized Editors to check out for editing or for a Group Policy administrator to deploy.</span></span></p>
<p><img src="images/8e7a7c4e-809a-435a-8b29-30d797936210.gif" alt="Checked out GPO icon" /> <strong><span data-ttu-id="3f8af-119">已取出： </strong> 目前正在進行編輯。</span><span class="sxs-lookup"><span data-stu-id="3f8af-119">Checked Out:</strong> Currently being edited.</span></span> <span data-ttu-id="3f8af-120">無法供其他編輯工具取出，直到已取出的編輯者或 AGPM 系統管理員將其檢入為止。</span><span class="sxs-lookup"><span data-stu-id="3f8af-120">Unavailable for other Editors to check out until the Editor who checked it out or an AGPM Administrator checks it in.</span></span></p>
<p><img src="images/0840a6a3-54a6-4528-98a9-7b122243c1a5.gif" alt="Pending GPO icon" /> <strong><span data-ttu-id="3f8af-121">擱置：在 </strong> 建立、控制、部署或刪除群組原則管理員之前，請先等待該群群組原則管理員的核准。</span><span class="sxs-lookup"><span data-stu-id="3f8af-121">Pending:</strong> Awaiting approval from a Group Policy administrator before being created, controlled, deployed, or deleted.</span></span></p>
<p><img src="images/57b610a5-1c71-4d26-9173-d04abd495fcc.gif" alt="Checked in GPO icon" /> <strong><span data-ttu-id="3f8af-122">已刪除： </strong> 已從封存中刪除，但仍可還原。</span><span class="sxs-lookup"><span data-stu-id="3f8af-122">Deleted:</strong> Deleted from the archive, but still able to be restored.</span></span></p>
<p><img src="images/9b65829d-253c-4f30-9295-c816a6521ed2.gif" alt="Template icon" /> <strong><span data-ttu-id="3f8af-123">範本： </strong> GPO 的靜態版本，可在建立新 gpo 時做為起點使用。</span><span class="sxs-lookup"><span data-stu-id="3f8af-123">Template:</strong> A static version of a GPO for use as a starting point when creating new GPOs.</span></span></p>
<p><img src="images/cd349b8d-c4d8-45ff-b17f-7db882502c58.gif" alt="Default template icon" /> <strong><span data-ttu-id="3f8af-124">範本（預設）： </strong> 根據預設，此範本是建立新 GPO 時所使用的起始點。</span><span class="sxs-lookup"><span data-stu-id="3f8af-124">Template (default):</strong> By default, this template is the starting point used when creating a new GPO.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="3f8af-125">GPO 狀態</span><span class="sxs-lookup"><span data-stu-id="3f8af-125">GPO Status</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3f8af-126">您可以個別管理電腦配置和使用者設定。</span><span class="sxs-lookup"><span data-stu-id="3f8af-126">The Computer Configuration and the User Configuration can be managed separately.</span></span> <span data-ttu-id="3f8af-127">GPO 狀態表示已啟用 GPO 的哪些部分。</span><span class="sxs-lookup"><span data-stu-id="3f8af-127">The GPO Status indicates which portions of the GPO are enabled.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="3f8af-128">WMI 篩選器</span><span class="sxs-lookup"><span data-stu-id="3f8af-128">WMI Filter</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3f8af-129">顯示適用于此 GPO 的任何 WMI 篩選器。</span><span class="sxs-lookup"><span data-stu-id="3f8af-129">Display any WMI filters that are applied to this GPO.</span></span> <span data-ttu-id="3f8af-130">WMI 篩選是在 GPMC 的 [wmi 篩選器] 節點下管理，在 <strong> </strong> GPMC 的主控台樹中是在該網域。</span><span class="sxs-lookup"><span data-stu-id="3f8af-130">WMI filters are managed under the <strong>WMI Filters</strong> node for the domain in the console tree of the GPMC.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="3f8af-131">修改日期</span><span class="sxs-lookup"><span data-stu-id="3f8af-131">Modified</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3f8af-132">針對受控制的 GPO，是在修改或取出後將其簽核至修改之後的最近日期。</span><span class="sxs-lookup"><span data-stu-id="3f8af-132">For a controlled GPO, the most recent date when it was checked in after being modified or checked out to be modified.</span></span> <span data-ttu-id="3f8af-133">如果是不受控制的 GPO，就是上次修改的日期。</span><span class="sxs-lookup"><span data-stu-id="3f8af-133">For an uncontrolled GPO, the date when it was last modified.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="3f8af-134">擁有者</span><span class="sxs-lookup"><span data-stu-id="3f8af-134">Owner</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3f8af-135">已檢入或部署所選 GPO 之核准者的編輯者。</span><span class="sxs-lookup"><span data-stu-id="3f8af-135">The Editor who checked in or the Approver who deployed the selected GPO.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="3f8af-136">[群組與使用者] 區段</span><span class="sxs-lookup"><span data-stu-id="3f8af-136">Groups and Users section</span></span>


<span data-ttu-id="3f8af-137">選取 GPO 時，[**群組與使用者**] 區段會顯示群組和使用者有權存取該 gpo 的清單。</span><span class="sxs-lookup"><span data-stu-id="3f8af-137">When a GPO is selected, the **Groups and Users** section displays a list of the groups and users with access to that GPO.</span></span> <span data-ttu-id="3f8af-138">針對每個群組或使用者顯示允許的許可權和繼承。</span><span class="sxs-lookup"><span data-stu-id="3f8af-138">The allowed permissions and inheritance are displayed for each group or user.</span></span> <span data-ttu-id="3f8af-139">AGPM 管理員可以使用標準 AGPM 角色（[編輯者]、[核准者] 和 [審查員]）或自訂的許可權組合來設定許可權。</span><span class="sxs-lookup"><span data-stu-id="3f8af-139">An AGPM Administrator can configure permissions using either standard AGPM roles (Editor, Approver, and Reviewer) or a customized combination of permissions.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3f8af-140">Button</span><span class="sxs-lookup"><span data-stu-id="3f8af-140">Button</span></span></th>
<th align="left"><span data-ttu-id="3f8af-141">效果</span><span class="sxs-lookup"><span data-stu-id="3f8af-141">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="3f8af-142">新增</span><span class="sxs-lookup"><span data-stu-id="3f8af-142">Add</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3f8af-143">在安全性說明符中加入新專案。</span><span class="sxs-lookup"><span data-stu-id="3f8af-143">Add a new entry to the security descriptor.</span></span> <span data-ttu-id="3f8af-144">您可以新增 Active Directory 中的任何使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="3f8af-144">Any user or group in Active Directory can be added.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="3f8af-145">移除</span><span class="sxs-lookup"><span data-stu-id="3f8af-145">Remove</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3f8af-146">從 [存取控制] 清單中移除選取的專案。</span><span class="sxs-lookup"><span data-stu-id="3f8af-146">Remove the selected entry from the Access Control List.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="3f8af-147">屬性</span><span class="sxs-lookup"><span data-stu-id="3f8af-147">Properties</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3f8af-148">顯示所選物件的屬性。</span><span class="sxs-lookup"><span data-stu-id="3f8af-148">Display the properties for the selected object.</span></span> <span data-ttu-id="3f8af-149">[屬性] 頁面與 <strong> Active Directory 使用者和電腦中的物件所顯示的內容相同 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="3f8af-149">The properties page is the same one displayed for an object in <strong>Active Directory Users and Computers</strong>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="3f8af-150">進階</span><span class="sxs-lookup"><span data-stu-id="3f8af-150">Advanced</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="3f8af-151">開啟 [ <strong> 存取控制清單編輯器] </strong> 。</span><span class="sxs-lookup"><span data-stu-id="3f8af-151">Open the <strong>Access Control List Editor</strong>.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="3f8af-152">其他考量</span><span class="sxs-lookup"><span data-stu-id="3f8af-152">Additional considerations</span></span>

-   <span data-ttu-id="3f8af-153">如需有關特定工作的角色與許可權的相關資訊，請參閱[執行 AGPM 管理員](performing-agpm-administrator-tasks.md)工作、[執行編輯](performing-editor-tasks.md)程式工作、[執行核准者](performing-approver-tasks.md)工作及[執行審查員](performing-reviewer-tasks.md)工作中的工作。</span><span class="sxs-lookup"><span data-stu-id="3f8af-153">For information about roles and permissions related to specific tasks, see the tasks under [Performing AGPM Administrator Tasks](performing-agpm-administrator-tasks.md), [Performing Editor Tasks](performing-editor-tasks.md), [Performing Approver Tasks](performing-approver-tasks.md), and [Performing Reviewer Tasks](performing-reviewer-tasks.md).</span></span>

### <span data-ttu-id="3f8af-154">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="3f8af-154">Additional references</span></span>

-   [<span data-ttu-id="3f8af-155">內容索引標籤</span><span class="sxs-lookup"><span data-stu-id="3f8af-155">Contents Tab</span></span>](contents-tab.md)

 

 





