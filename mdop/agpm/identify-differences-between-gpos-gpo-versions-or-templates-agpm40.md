---
title: 找出 GPO、GPO 版本或範本之間的差異
description: 找出 GPO、GPO 版本或範本之間的差異
author: dansimp
ms.assetid: 3f03c368-162b-450f-be6c-2807c3e8d741
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bf5a7c71b431c787dcb2b16fe9a19f7ff9b06046
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802746"
---
# <span data-ttu-id="c0aeb-103">找出 GPO、GPO 版本或範本之間的差異</span><span class="sxs-lookup"><span data-stu-id="c0aeb-103">Identify Differences Between GPOs, GPO Versions, or Templates</span></span>


<span data-ttu-id="c0aeb-104">您可以產生以 HTML 為基礎或 XML 為基礎的差異報告，來分析群組原則物件（Gpo）、範本或不同版本的 GPO 間的差異。</span><span class="sxs-lookup"><span data-stu-id="c0aeb-104">You can generate HTML-based or XML-based difference reports to analyze the differences between Group Policy Objects (GPOs), templates, or different versions of a GPO.</span></span>

<span data-ttu-id="c0aeb-105">具有 [檢閱者]、[編輯者] 或 [AGPM 管理員] （完全控制）角色的使用者帳戶，或需要高級群組原則管理（AGPM）中的必要許可權，才能完成此程式。</span><span class="sxs-lookup"><span data-stu-id="c0aeb-105">A user account with the Reviewer, Editor, Approver, or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management (AGPM)is required to complete this procedure.</span></span> <span data-ttu-id="c0aeb-106">請參閱本主題中的「其他注意事項」中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="c0aeb-106">Review the details in "Additional considerations" in this topic.</span></span>

## <span data-ttu-id="c0aeb-107">識別 Gpo、GPO 版本或範本之間的差異</span><span class="sxs-lookup"><span data-stu-id="c0aeb-107">Identifying differences between GPOs, GPO versions, or templates</span></span>


-   [<span data-ttu-id="c0aeb-108">在兩個 Gpo 或範本之間</span><span class="sxs-lookup"><span data-stu-id="c0aeb-108">Between two GPOs or templates</span></span>](#bkmk-two-gpos)

-   [<span data-ttu-id="c0aeb-109">在 GPO 與範本之間</span><span class="sxs-lookup"><span data-stu-id="c0aeb-109">Between a GPO and a template</span></span>](#bkmk-gpo-and-template)

-   [<span data-ttu-id="c0aeb-110">在單一 GPO 的兩個版本之間</span><span class="sxs-lookup"><span data-stu-id="c0aeb-110">Between two versions of one GPO</span></span>](#bkmk-two-versions)

-   [<span data-ttu-id="c0aeb-111">GPO 版本與範本之間</span><span class="sxs-lookup"><span data-stu-id="c0aeb-111">Between a GPO version and a template</span></span>](#bkmk-gpo-version-and-template)

## <a href="" id="bkmk-two-gpos"></a>


**<span data-ttu-id="c0aeb-112">找出兩個 Gpo 或範本之間的差異</span><span class="sxs-lookup"><span data-stu-id="c0aeb-112">To identify differences between two GPOs or templates</span></span>**

1.  <span data-ttu-id="c0aeb-113">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="c0aeb-113">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="c0aeb-114">在 [詳細資料] 窗格的 [**內容**] 索引標籤上，按一下索引標籤以顯示 gpo （如果比較兩個範本，則則是範本）。</span><span class="sxs-lookup"><span data-stu-id="c0aeb-114">On the **Contents** tab in the details pane, click a tab to display GPOs (or templates, if comparing two templates).</span></span>

3.  <span data-ttu-id="c0aeb-115">選取兩個 Gpo 或範本。</span><span class="sxs-lookup"><span data-stu-id="c0aeb-115">Select the two GPOs or templates.</span></span>

4.  <span data-ttu-id="c0aeb-116">以滑鼠右鍵按一下其中一個 Gpo 或範本，按一下 [**差異**]，然後按一下 [ **HTML 報表**] 或 [ **XML 報表**]，以顯示匯總 gpo 或範本之設定的差異報告。</span><span class="sxs-lookup"><span data-stu-id="c0aeb-116">Right-click one of the GPOs or templates, click **Differences**, and then click **HTML Report** or **XML Report** to display a difference report summarizing the settings of the GPOs or templates.</span></span>

### <a href="" id="bkmk-gpo-and-template"></a>

**<span data-ttu-id="c0aeb-117">識別 GPO 與範本之間的差異</span><span class="sxs-lookup"><span data-stu-id="c0aeb-117">To identify differences between a GPO and a template</span></span>**

1.  <span data-ttu-id="c0aeb-118">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="c0aeb-118">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="c0aeb-119">在 [詳細資料] 窗格的 [**內容**] 索引標籤上，按一下索引標籤以顯示 gpo （如果比較兩個範本，則則是範本）。</span><span class="sxs-lookup"><span data-stu-id="c0aeb-119">On the **Contents** tab in the details pane, click a tab to display GPOs (or templates, if comparing two templates).</span></span>

3.  <span data-ttu-id="c0aeb-120">以滑鼠右鍵按一下該 GPO，按一下 [**差異**]，然後按一下 [**範本**]。</span><span class="sxs-lookup"><span data-stu-id="c0aeb-120">Right-click the GPO, click **Differences**, and then click **Template**.</span></span>

4.  <span data-ttu-id="c0aeb-121">選取 [範本] 和 [報告類型]，然後按一下 **[確定]** 以顯示摘要與範本設定的差異報告。</span><span class="sxs-lookup"><span data-stu-id="c0aeb-121">Select the template and type of report, and then click **OK** to display a difference report summarizing the settings of the GPO and template.</span></span>

### <a href="" id="bkmk-two-versions"></a>

**<span data-ttu-id="c0aeb-122">若要識別一個 GPO 的兩個版本之間的差異</span><span class="sxs-lookup"><span data-stu-id="c0aeb-122">To identify differences between two versions of one GPO</span></span>**

1.  <span data-ttu-id="c0aeb-123">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="c0aeb-123">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="c0aeb-124">在 [詳細資料] 窗格的 [**內容**] 索引標籤上，按一下索引標籤以顯示 gpo （如果比較兩個範本，則則是範本）。</span><span class="sxs-lookup"><span data-stu-id="c0aeb-124">On the **Contents** tab in the details pane, click a tab to display GPOs (or templates, if comparing two templates).</span></span>

3.  <span data-ttu-id="c0aeb-125">按兩下 GPO 以顯示其記錄，然後醒目提示要比較的版本。</span><span class="sxs-lookup"><span data-stu-id="c0aeb-125">Double-click the GPO to display its history, and then highlight the versions to be compared.</span></span>

4.  <span data-ttu-id="c0aeb-126">以滑鼠右鍵按一下其中一個版本，按一下 [**差異**]，然後按一下 [ **HTML 報表**] 或 [ **XML 報表**]，以顯示匯總 gpo 設定的差異報告。</span><span class="sxs-lookup"><span data-stu-id="c0aeb-126">Right-click one of the versions, click **Differences**, and then click **HTML Report** or **XML Report** to display a difference report summarizing the settings of the GPOs.</span></span>

### <a href="" id="bkmk-gpo-version-and-template"></a>

**<span data-ttu-id="c0aeb-127">若要識別 GPO 版本與範本之間的差異</span><span class="sxs-lookup"><span data-stu-id="c0aeb-127">To identify differences between a GPO version and a template</span></span>**

1.  <span data-ttu-id="c0aeb-128">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="c0aeb-128">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="c0aeb-129">在 [詳細資料] 窗格的 [**內容**] 索引標籤上，按一下索引標籤以顯示 gpo （如果比較兩個範本，則則是範本）。</span><span class="sxs-lookup"><span data-stu-id="c0aeb-129">On the **Contents** tab in the details pane, click a tab to display GPOs (or templates, if comparing two templates).</span></span>

3.  <span data-ttu-id="c0aeb-130">按兩下該 GPO 以顯示其歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="c0aeb-130">Double-click the GPO to display its history.</span></span>

4.  <span data-ttu-id="c0aeb-131">以滑鼠右鍵按一下感興趣的 GPO 版本，按一下 [**差異**]，然後按一下 [**範本**]。</span><span class="sxs-lookup"><span data-stu-id="c0aeb-131">Right-click the GPO version of interest, click **Differences**, and then click **Template**.</span></span>

5.  <span data-ttu-id="c0aeb-132">選取 [範本] 和 [報告類型]，然後按一下 **[確定]** 以顯示 [摘要] 與 [GPO 版本] 與 [範本] 設定的差異報告。</span><span class="sxs-lookup"><span data-stu-id="c0aeb-132">Select the template and type of report, and then click **OK** to display a difference report summarizing the settings of the GPO version and template.</span></span>

## <span data-ttu-id="c0aeb-133">差異報告的主要</span><span class="sxs-lookup"><span data-stu-id="c0aeb-133">Key to difference reports</span></span>


<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c0aeb-134">符號</span><span class="sxs-lookup"><span data-stu-id="c0aeb-134">Symbol</span></span></th>
<th align="left"><span data-ttu-id="c0aeb-135">意義</span><span class="sxs-lookup"><span data-stu-id="c0aeb-135">Meaning</span></span></th>
<th align="left"><span data-ttu-id="c0aeb-136">色彩</span><span class="sxs-lookup"><span data-stu-id="c0aeb-136">Color</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c0aeb-137">無</span><span class="sxs-lookup"><span data-stu-id="c0aeb-137">None</span></span></p></td>
<td align="left"><p><span data-ttu-id="c0aeb-138">在兩個 Gpo 中都存在具有相同設定的專案</span><span class="sxs-lookup"><span data-stu-id="c0aeb-138">Item exists with identical settings in both GPOs</span></span></p></td>
<td align="left"><p><span data-ttu-id="c0aeb-139">依層級而異</span><span class="sxs-lookup"><span data-stu-id="c0aeb-139">Varies with level</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="c0aeb-140">[#]</span><span class="sxs-lookup"><span data-stu-id="c0aeb-140">[#]</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="c0aeb-141">專案存在於兩個 Gpo 中，但具有已變更的設定</span><span class="sxs-lookup"><span data-stu-id="c0aeb-141">Item exists in both GPOs, but with changed settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="c0aeb-142">天藍色</span><span class="sxs-lookup"><span data-stu-id="c0aeb-142">Blue</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="c0aeb-143">[-]</span><span class="sxs-lookup"><span data-stu-id="c0aeb-143">[-]</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="c0aeb-144">只有在第一個 GPO 中存在專案</span><span class="sxs-lookup"><span data-stu-id="c0aeb-144">Item exists only in the first GPO</span></span></p></td>
<td align="left"><p><span data-ttu-id="c0aeb-145">紅色</span><span class="sxs-lookup"><span data-stu-id="c0aeb-145">Red</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="c0aeb-146">[+]</span><span class="sxs-lookup"><span data-stu-id="c0aeb-146">[+]</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="c0aeb-147">只有在第二個 GPO 中存在專案</span><span class="sxs-lookup"><span data-stu-id="c0aeb-147">Item exists only in the second GPO</span></span></p></td>
<td align="left"><p><span data-ttu-id="c0aeb-148">綠色</span><span class="sxs-lookup"><span data-stu-id="c0aeb-148">Green</span></span></p></td>
</tr>
</tbody>
</table>

 

-   <span data-ttu-id="c0aeb-149">針對具有已變更之設定的專案，已變更的設定會在專案展開時加以識別。</span><span class="sxs-lookup"><span data-stu-id="c0aeb-149">For items with changed settings, the changed settings are identified when the item is expanded.</span></span> <span data-ttu-id="c0aeb-150">每個 GPO 中屬性的值會以 Gpo 在報表中顯示的順序顯示。</span><span class="sxs-lookup"><span data-stu-id="c0aeb-150">The value for the attribute in each GPO is displayed in the same order that the GPOs are displayed in the report.</span></span>

-   <span data-ttu-id="c0aeb-151">設定的部分變更可能會導致將專案報告成兩個不同的專案（只有在第一個 GPO 中有一個，而只是在第二個 GPO 中存在，而另一個則只出現在第二個</span><span class="sxs-lookup"><span data-stu-id="c0aeb-151">Some changes to settings may cause an item to be reported as two different items (one present only in the first GPO, one present only in the second) rather than as one item that has changed.</span></span>

### <span data-ttu-id="c0aeb-152">其他考量</span><span class="sxs-lookup"><span data-stu-id="c0aeb-152">Additional considerations</span></span>

-   <span data-ttu-id="c0aeb-153">根據預設，您必須是檢閱者、編輯者或 AGPM 管理員（完全控制），才能執行此程式。</span><span class="sxs-lookup"><span data-stu-id="c0aeb-153">By default, you must be a Reviewer, an Editor, an Approver, or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="c0aeb-154">具體來說，您必須擁有 [**清單內容**] 和 [**讀取設定**] 許可權給 GPO。</span><span class="sxs-lookup"><span data-stu-id="c0aeb-154">Specifically, you must have **List Contents** and **Read Settings** permissions for the GPO.</span></span> <span data-ttu-id="c0aeb-155">此外，若要顯示 Gpo 清單，您必須擁有該網域的 [**清單內容**] 許可權。</span><span class="sxs-lookup"><span data-stu-id="c0aeb-155">Also, to display the list of GPOs, you must have **List Contents** permission for the domain.</span></span>

### <span data-ttu-id="c0aeb-156">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="c0aeb-156">Additional references</span></span>

-   [<span data-ttu-id="c0aeb-157">執行檢閱者工作</span><span class="sxs-lookup"><span data-stu-id="c0aeb-157">Performing Reviewer Tasks</span></span>](performing-reviewer-tasks-agpm40.md)

 

 





