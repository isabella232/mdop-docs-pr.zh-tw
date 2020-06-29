---
title: 搜尋和篩選 GPO 清單
description: 搜尋和篩選 GPO 清單
author: dansimp
ms.assetid: 1bc58a38-033c-4aed-9eb4-c239827f5501
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5646a51a37a4ca9195fb9ef858e8c5920ca7738a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802546"
---
# <span data-ttu-id="26437-103">搜尋和篩選 GPO 清單</span><span class="sxs-lookup"><span data-stu-id="26437-103">Search and Filter the List of GPOs</span></span>


<span data-ttu-id="26437-104">在 [高級群組原則管理（AGPM）] 中，您可以搜尋群組原則物件（Gpo）及其屬性的清單，以篩選顯示的 Gpo 清單。</span><span class="sxs-lookup"><span data-stu-id="26437-104">In Advanced Group Policy Management (AGPM), you can search the list of Group Policy Objects (GPOs) and their attributes to filter the list of GPOs displayed.</span></span> <span data-ttu-id="26437-105">例如，您可以搜尋具有特定名稱、狀態或批註的 Gpo。</span><span class="sxs-lookup"><span data-stu-id="26437-105">For example, you can search for GPOs with a particular name, state, or comment.</span></span> <span data-ttu-id="26437-106">您也可以搜尋由特定群組原則系統管理員或特定日期所變更的 Gpo。</span><span class="sxs-lookup"><span data-stu-id="26437-106">You can also search for GPOs that were last changed by a particular Group Policy administrator or on a particular date.</span></span>

## <span data-ttu-id="26437-107">執行複雜的搜尋</span><span class="sxs-lookup"><span data-stu-id="26437-107">Performing a complex search</span></span>


<span data-ttu-id="26437-108">您可以使用 [格式化*GPO 屬性1：搜尋字串 1 GPO 屬性2：搜尋字串 2 ...] 來執行複雜搜尋。全欄搜尋字串*。</span><span class="sxs-lookup"><span data-stu-id="26437-108">You can perform a complex search by using the format *GPO attribute 1: search string 1 GPO attribute 2: search string 2…all-column search strings*.</span></span> <span data-ttu-id="26437-109">搜尋不區分大小寫。</span><span class="sxs-lookup"><span data-stu-id="26437-109">The search is not case-sensitive.</span></span>

-   <span data-ttu-id="26437-110">**GPO 屬性：** 在 [**電腦版本**] 或 [**使用者版本**] 以外的 AGPM 之 gpo 清單中的任何欄標題。</span><span class="sxs-lookup"><span data-stu-id="26437-110">**GPO attribute:** Any column heading in the list of GPOs in AGPM other than **Computer Version** or **User Version**.</span></span> <span data-ttu-id="26437-111">GPO 屬性包含 GPO 名稱、狀態、最近變更 GPO 的使用者，以及 GPO 最近變更的日期和時間、批註、GPO 狀態，以及套用到 GPO 的 WMI 篩選器。</span><span class="sxs-lookup"><span data-stu-id="26437-111">GPO attributes include the GPO name, state, user who most recently changed the GPO, date and time when the GPO was most recently changed, comment, GPO status, and WMI filter applied to the GPO.</span></span>

-   <span data-ttu-id="26437-112">**搜尋字串：** 要在指定資料行中搜尋的文字。</span><span class="sxs-lookup"><span data-stu-id="26437-112">**Search string:** Text for which to search in the specified column.</span></span> <span data-ttu-id="26437-113">如果字串包含空格，您必須以引號括住字串。</span><span class="sxs-lookup"><span data-stu-id="26437-113">If a string includes spaces, you must enclose the string with quotation marks.</span></span>

-   <span data-ttu-id="26437-114">**全欄搜尋字串：** 要在 [**電腦版本**] 和 [**使用者版本**] 以外的 AGPM 之 gpo 清單中的所有欄中搜尋的文字。</span><span class="sxs-lookup"><span data-stu-id="26437-114">**All-column search strings:** Text for which to search in all columns in the list of GPOs in AGPM other than **Computer Version** and **User Version**.</span></span> <span data-ttu-id="26437-115">您可以包含以空格分隔的多個字串。</span><span class="sxs-lookup"><span data-stu-id="26437-115">You can include multiple strings separated by spaces.</span></span> <span data-ttu-id="26437-116">如果字串包含空格，您必須以引號括住字串。</span><span class="sxs-lookup"><span data-stu-id="26437-116">If a string includes spaces, you must enclose the string with quotation marks.</span></span>

<span data-ttu-id="26437-117">每個 GPO 屬性和搜尋字串配對，以及每個全欄搜尋字串都是使用邏輯 AND 運算結合。</span><span class="sxs-lookup"><span data-stu-id="26437-117">Each GPO attribute and search string pair and each all-column search string are combined by using a logical AND operation.</span></span> <span data-ttu-id="26437-118">結果是所有 Gpo 的清單，其中每個指定的屬性都包含指定的搜尋字串，而所有的全欄搜尋字串都出現在至少一欄中。</span><span class="sxs-lookup"><span data-stu-id="26437-118">The result is a list of all GPOs for which each specified attribute includes the specified search string and for which any all-column search strings appear in at least one column.</span></span> <span data-ttu-id="26437-119">搜尋會傳回字串的任何部分相符，因此您可以輸入 GPO 名稱或使用者名稱的一部分，並查看其名稱中包含該文字的所有 Gpo 的清單。</span><span class="sxs-lookup"><span data-stu-id="26437-119">The search returns any partial matches for strings so that you can enter part of a GPO name or user name and view a list of all GPOs that include that text in their name.</span></span>

<span data-ttu-id="26437-120">下列是搜尋的範例：</span><span class="sxs-lookup"><span data-stu-id="26437-120">The following are examples of searches:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="26437-121">搜尋結果的描述</span><span class="sxs-lookup"><span data-stu-id="26437-121">Description of search result</span></span></th>
<th align="left"><span data-ttu-id="26437-122">搜尋查詢</span><span class="sxs-lookup"><span data-stu-id="26437-122">Search query</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="26437-123">名稱中包含文字安全性和北美的所有 Gpo <strong> </strong> <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="26437-123">All GPOs with names that include the text <strong>security</strong> and <strong>North America</strong>.</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="26437-124">名稱： </strong><strong> 安全性 </strong><strong> 名稱： </strong> &quot; <strong> 北美</strong>&quot;</span><span class="sxs-lookup"><span data-stu-id="26437-124">name:</strong><strong>security</strong><strong>name:</strong>&quot;<strong>North America</strong>&quot;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="26437-125">所有已取出的 Gpo。</span><span class="sxs-lookup"><span data-stu-id="26437-125">All checked out GPOs.</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="26437-126">狀態： </strong> &quot; <strong> 已取出</strong>&quot;</span><span class="sxs-lookup"><span data-stu-id="26437-126">state:</strong>&quot;<strong>checked out</strong>&quot;</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="26437-127">使用者最近在 <strong> 前一個月變更的所有 gpo </strong> 。</span><span class="sxs-lookup"><span data-stu-id="26437-127">All GPOs most recently changed by the user named <strong>Administrator</strong> and most recently changed within the previous month.</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="26437-128">變更者： </strong><strong> 系統管理員 </strong><strong> 變更日期： </strong><strong> lastmonth</span><span class="sxs-lookup"><span data-stu-id="26437-128">changed by:</strong><strong>Administrator</strong><strong>change date:</strong><strong>lastmonth</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="26437-129">所有的 Gpo，其中的 word <strong> 防火牆 </strong> 都包含在最近的批註中，而 word <strong> 安全性則 </strong> 會出現在任何資料行中。</span><span class="sxs-lookup"><span data-stu-id="26437-129">All GPOs in which the word <strong>firewall</strong> is included in the most recent comment and in which the word <strong>security</strong> appears in any column.</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="26437-130">批註： </strong><strong> 防火牆 </strong><strong> 安全性</span><span class="sxs-lookup"><span data-stu-id="26437-130">comment:</strong><strong>firewall</strong><strong>security</span></span></strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="26437-131">已 <strong> 停用所有設定狀態的所有 gpo </strong> 。</span><span class="sxs-lookup"><span data-stu-id="26437-131">All GPOs that have a status of <strong>All Settings Disabled</strong>.</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="26437-132">gpo 狀態： </strong><strong> 全部</span><span class="sxs-lookup"><span data-stu-id="26437-132">gpo status:</strong><strong>all</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="26437-133">已套用名為「我的 WMI 篩選」的 WMI 篩選器的所有 Gpo <strong> </strong> ，且已 <strong> 停用使用者配置設定的狀態 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="26437-133">All GPOs that have a WMI filter named <strong>My WMI Filter</strong> applied and that have a status of <strong>User Configuration Settings Disabled</strong>.</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="26437-134">wmi 篩選： </strong> &quot; <strong> 我的 WMI 篩選 </strong> &quot; <strong> gpo 狀態： </strong><strong> 使用者</span><span class="sxs-lookup"><span data-stu-id="26437-134">wmi filter:</strong>&quot;<strong>My WMI Filter</strong>&quot;<strong>gpo status:</strong><strong>user</span></span></strong></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="26437-135">指定日期</span><span class="sxs-lookup"><span data-stu-id="26437-135">Specifying dates</span></span>


<span data-ttu-id="26437-136">您可以在特定時間搜尋 Gpo 變更，或在一段時間內使用您在 Windows 中進行搜尋時所提供的特殊條件來搜尋。</span><span class="sxs-lookup"><span data-stu-id="26437-136">You can search for GPOs changed on a specific date, at a specific time, or during a span of time by using the same special terms available when you search in Windows.</span></span> <span data-ttu-id="26437-137">如果輸入特定的日期或時間，您必須使用 [**變更日期] 資料**行中所用的格式。</span><span class="sxs-lookup"><span data-stu-id="26437-137">If entering a specific date or time, you must use the format that is used in the **Change Date** column.</span></span> <span data-ttu-id="26437-138">下列是 [**變更日期] 資料**行的搜尋範例：</span><span class="sxs-lookup"><span data-stu-id="26437-138">The following are examples of searches of the **Change Date** column:</span></span>

-   <span data-ttu-id="26437-139">**變更日期：\*\*\*\*10/10/2009**</span><span class="sxs-lookup"><span data-stu-id="26437-139">**change date:\*\*\*\*10/10/2009**</span></span>

-   <span data-ttu-id="26437-140">**變更日期：\*\*\*\*10/10/2009 9:00:00 AM**</span><span class="sxs-lookup"><span data-stu-id="26437-140">**change date:\*\*\*\*10/10/2009 9:00:00 AM**</span></span>

-   <span data-ttu-id="26437-141">**變更日期：\*\*\*\*thisweek**</span><span class="sxs-lookup"><span data-stu-id="26437-141">**change date:\*\*\*\*thisweek**</span></span>

<span data-ttu-id="26437-142">當您搜尋 [**變更日期] 資料**行時，您可以使用下列特殊字詞（不區分大小寫）：</span><span class="sxs-lookup"><span data-stu-id="26437-142">You can use the following special terms, which are not case-sensitive, when you search the **Change Date** column:</span></span>

-   **<span data-ttu-id="26437-143">今天</span><span class="sxs-lookup"><span data-stu-id="26437-143">Today</span></span>**

-   **<span data-ttu-id="26437-144">昨天</span><span class="sxs-lookup"><span data-stu-id="26437-144">Yesterday</span></span>**

-   **<span data-ttu-id="26437-145">ThisWeek</span><span class="sxs-lookup"><span data-stu-id="26437-145">ThisWeek</span></span>**

-   **<span data-ttu-id="26437-146">LastWeek</span><span class="sxs-lookup"><span data-stu-id="26437-146">LastWeek</span></span>**

-   **<span data-ttu-id="26437-147">ThisMonth</span><span class="sxs-lookup"><span data-stu-id="26437-147">ThisMonth</span></span>**

-   **<span data-ttu-id="26437-148">LastMonth</span><span class="sxs-lookup"><span data-stu-id="26437-148">LastMonth</span></span>**

-   **<span data-ttu-id="26437-149">TwoMonths</span><span class="sxs-lookup"><span data-stu-id="26437-149">TwoMonths</span></span>**

-   **<span data-ttu-id="26437-150">ThreeMonths</span><span class="sxs-lookup"><span data-stu-id="26437-150">ThreeMonths</span></span>**

-   **<span data-ttu-id="26437-151">ThisYear</span><span class="sxs-lookup"><span data-stu-id="26437-151">ThisYear</span></span>**

-   **<span data-ttu-id="26437-152">LastYear</span><span class="sxs-lookup"><span data-stu-id="26437-152">LastYear</span></span>**

### <span data-ttu-id="26437-153">其他考量</span><span class="sxs-lookup"><span data-stu-id="26437-153">Additional considerations</span></span>

-   <span data-ttu-id="26437-154">根據預設，您必須是檢閱者、編輯者或 AGPM 管理員（完全控制），才能執行此程式。</span><span class="sxs-lookup"><span data-stu-id="26437-154">By default, you must be a Reviewer, an Editor, an Approver, or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="26437-155">具體說來，您必須擁有該網域的 [**清單內容**] 許可權。</span><span class="sxs-lookup"><span data-stu-id="26437-155">Specifically, you must have **List Contents** permission for the domain.</span></span>

-   <span data-ttu-id="26437-156">如需有關 GPO 屬性的詳細資訊，請參閱 [[內容]](contents-tab-features-agpm40.md)索引標籤功能。</span><span class="sxs-lookup"><span data-stu-id="26437-156">For more information about GPO attributes, see [Contents Tab Features](contents-tab-features-agpm40.md).</span></span>

### <span data-ttu-id="26437-157">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="26437-157">Additional references</span></span>

-   [<span data-ttu-id="26437-158">進階群組原則管理 4.0</span><span class="sxs-lookup"><span data-stu-id="26437-158">Advanced Group Policy Management 4.0</span></span>](advanced-group-policy-management-40.md)

 

 





