---
title: 歷程記錄視窗
description: 歷程記錄視窗
author: dansimp
ms.assetid: 114f50a4-508d-4589-b006-6cd05cffe6b7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 81911b5103c76e267d806fb7cd8acf55811440c9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802761"
---
# <span data-ttu-id="74b98-103">歷程記錄視窗</span><span class="sxs-lookup"><span data-stu-id="74b98-103">History Window</span></span>


<span data-ttu-id="74b98-104">您可以按兩下某個 GPO，或以滑鼠右鍵按一下某個 GPO，然後按一下 [歷程**記錄**]，以顯示該群群組原則物件（GPO）的歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="74b98-104">The history of a Group Policy Object (GPO) can be displayed by double-clicking a GPO or by right-clicking a GPO and then clicking **History**.</span></span> <span data-ttu-id="74b98-105">它也會顯示在**群組原則管理主控台**（GPMC）中作為每個 GPO 的索引標籤。</span><span class="sxs-lookup"><span data-stu-id="74b98-105">It is also displayed in the **Group Policy Management Console** (GPMC) as a tab for each GPO.</span></span>

<span data-ttu-id="74b98-106">[歷程記錄] 會在所選 GPO 的生命週期中提供事件記錄。</span><span class="sxs-lookup"><span data-stu-id="74b98-106">The history provides a record of events in the lifetime of the selected GPO.</span></span> <span data-ttu-id="74b98-107">您可以從 [歷程**記錄**] 視窗取得 gpo 版本中的設定報告、比較多個版本的 gpo，或返回舊版的 gpo。</span><span class="sxs-lookup"><span data-stu-id="74b98-107">From the **History** window, you can obtain a report of the settings within a version of the GPO, compare multiple versions of a GPO, or roll back to a previous version of a GPO.</span></span>

## <span data-ttu-id="74b98-108">在 [歷程記錄] 視窗中篩選事件</span><span class="sxs-lookup"><span data-stu-id="74b98-108">Filtering events in the History window</span></span>


<span data-ttu-id="74b98-109">[歷程**記錄**] 視窗中的索引標籤會篩選 GPO 歷程記錄中的狀態。</span><span class="sxs-lookup"><span data-stu-id="74b98-109">The tabs within the **History** window filter the states in the history of the GPO.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="74b98-110">索引標籤</span><span class="sxs-lookup"><span data-stu-id="74b98-110">Tabs</span></span></th>
<th align="left"><span data-ttu-id="74b98-111">篩選</span><span class="sxs-lookup"><span data-stu-id="74b98-111">Filtering</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="74b98-112">所有狀態</span><span class="sxs-lookup"><span data-stu-id="74b98-112">All States</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="74b98-113">顯示 GPO 歷程記錄中的所有狀態。</span><span class="sxs-lookup"><span data-stu-id="74b98-113">Display all states in the history of the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="74b98-114">唯一版本</span><span class="sxs-lookup"><span data-stu-id="74b98-114">Unique Versions</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="74b98-115">只顯示已核取到封存中之 GPO 的唯一版本。</span><span class="sxs-lookup"><span data-stu-id="74b98-115">Display only unique versions of the GPO checked into the archive.</span></span> <span data-ttu-id="74b98-116">此清單中省略了部署到生產環境的版本、唯一版本的快捷方式及資訊狀態。</span><span class="sxs-lookup"><span data-stu-id="74b98-116">The version deployed to the production environment, shortcuts to unique versions, and informational states are omitted from this list.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="74b98-117">事件資訊</span><span class="sxs-lookup"><span data-stu-id="74b98-117">Event information</span></span>


<span data-ttu-id="74b98-118">提供有關 GPO 歷程記錄中每個狀態的資訊。</span><span class="sxs-lookup"><span data-stu-id="74b98-118">Information is provided for each state in the history of the GPO.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="74b98-119">GPO 屬性</span><span class="sxs-lookup"><span data-stu-id="74b98-119">GPO attribute</span></span></th>
<th align="left"><span data-ttu-id="74b98-120">描述</span><span class="sxs-lookup"><span data-stu-id="74b98-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="74b98-121">變更日期</span><span class="sxs-lookup"><span data-stu-id="74b98-121">Change Date</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="74b98-122">[ <strong> 省/市/自治區] 資料行中動作的時間戳記 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="74b98-122">Time stamp of when the action in the <strong>State</strong> column was performed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="74b98-123">狀態</span><span class="sxs-lookup"><span data-stu-id="74b98-123">State</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="74b98-124">GPO 歷程記錄中的狀態。</span><span class="sxs-lookup"><span data-stu-id="74b98-124">A state in the history of the GPO.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="74b98-125">變更者</span><span class="sxs-lookup"><span data-stu-id="74b98-125">Changed By</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="74b98-126">已檢入或部署 GPO 的人員。</span><span class="sxs-lookup"><span data-stu-id="74b98-126">The person who checked in or deployed the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="74b98-127">留言</span><span class="sxs-lookup"><span data-stu-id="74b98-127">Comment</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="74b98-128">在修改此版本時，由檢入或部署 GPO 的人員所輸入的留言。</span><span class="sxs-lookup"><span data-stu-id="74b98-128">A comment entered by the person who checked in or deployed a GPO at the time that this version was modified.</span></span> <span data-ttu-id="74b98-129">在需要回滾到前一個版本的情況下，識別版本的詳細資訊時很有用。</span><span class="sxs-lookup"><span data-stu-id="74b98-129">Useful for identifying the specifics of the version in case of the need to roll back to a previous version.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="74b98-130">已</span><span class="sxs-lookup"><span data-stu-id="74b98-130">Deletable</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="74b98-131">如果封存中保留的每個 GPO 的唯一版本數受到限制，是否可刪除此 GPO 版本。</span><span class="sxs-lookup"><span data-stu-id="74b98-131">Whether this version of the GPO can be deleted if the number of unique versions of each GPO retained in the archive is limited.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="74b98-132">注意</span><span class="sxs-lookup"><span data-stu-id="74b98-132">Note</span></span></strong><br/><p><span data-ttu-id="74b98-133">您可以透過在 GPO 中按一下滑鼠右鍵，然後按一下 [ <strong> 禁止刪除] </strong> 或 [ <strong> 允許刪除]，來修改該版本是否可供使用 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="74b98-133">You can modify whether a version of a GPO is deletable by right-clicking it and then clicking <strong>Do Not Allow Deletion</strong> or <strong>Allow Deletion</strong>.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="74b98-134">電腦版本</span><span class="sxs-lookup"><span data-stu-id="74b98-134">Computer Version</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="74b98-135">GPO 的電腦設定部分自動產生的版本。</span><span class="sxs-lookup"><span data-stu-id="74b98-135">Automatically generated version of the Computer Configuration portion of the GPO.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="74b98-136">使用者版本</span><span class="sxs-lookup"><span data-stu-id="74b98-136">User Version</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="74b98-137">GPO 的使用者設定部分的自動產生版本。</span><span class="sxs-lookup"><span data-stu-id="74b98-137">Automatically generated version of the User Configuration portion of the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="74b98-138">GPO 狀態</span><span class="sxs-lookup"><span data-stu-id="74b98-138">GPO Status</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="74b98-139">您可以彼此獨立管理電腦配置和使用者設定。</span><span class="sxs-lookup"><span data-stu-id="74b98-139">The Computer Configuration and the User Configuration can be managed separately from each other.</span></span> <span data-ttu-id="74b98-140">此狀態會顯示已啟用 GPO 的哪些部分。</span><span class="sxs-lookup"><span data-stu-id="74b98-140">This status shows which portions of the GPO are enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="74b98-141">WMI 篩選器</span><span class="sxs-lookup"><span data-stu-id="74b98-141">WMI Filter</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="74b98-142">顯示適用于此 GPO 的任何 WMI 篩選器。</span><span class="sxs-lookup"><span data-stu-id="74b98-142">Display any WMI filters that are applied to this GPO.</span></span> <span data-ttu-id="74b98-143">WMI 篩選是在 GPMC 的 [ <strong> Wmi 篩選] </strong> 資料夾中，在 GPMC 的主控台樹中針對該域進行管理。</span><span class="sxs-lookup"><span data-stu-id="74b98-143">WMI filters are managed under the <strong>WMI Filters</strong> folder for the domain in the console tree of the GPMC.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="74b98-144">報告</span><span class="sxs-lookup"><span data-stu-id="74b98-144">Reports</span></span>


<span data-ttu-id="74b98-145">[**設定**] 和 [**差異**] 按鈕會顯示所選 gpo 版本或版本的 gpo 設定報告。</span><span class="sxs-lookup"><span data-stu-id="74b98-145">The **Settings** and **Differences** buttons display reports about GPO settings for the GPO version or versions selected.</span></span> <span data-ttu-id="74b98-146">以滑鼠右鍵按一下 [GPO 版本]，也會提供顯示 XML 報表的選項。</span><span class="sxs-lookup"><span data-stu-id="74b98-146">Right-clicking GPO versions provides the option to display XML-based reports as well.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="74b98-147">Button</span><span class="sxs-lookup"><span data-stu-id="74b98-147">Button</span></span></th>
<th align="left"><span data-ttu-id="74b98-148">效果</span><span class="sxs-lookup"><span data-stu-id="74b98-148">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="74b98-149">設定</span><span class="sxs-lookup"><span data-stu-id="74b98-149">Settings</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="74b98-150">產生以 HTML 為基礎的報告，其中顯示所選版本之 GPO 中的設定。</span><span class="sxs-lookup"><span data-stu-id="74b98-150">Generate an HTML-based report displaying the settings within the selected version of the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="74b98-151">多種</span><span class="sxs-lookup"><span data-stu-id="74b98-151">Differences</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="74b98-152">產生與多個選取版本之 GPO 中的設定比較的 HTML 報告。</span><span class="sxs-lookup"><span data-stu-id="74b98-152">Generate an HTML-based report comparing the settings within multiple selected versions of the GPO.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="74b98-153">差異報告的主要</span><span class="sxs-lookup"><span data-stu-id="74b98-153">Key to difference reports</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="74b98-154">符號</span><span class="sxs-lookup"><span data-stu-id="74b98-154">Symbol</span></span></th>
<th align="left"><span data-ttu-id="74b98-155">意義</span><span class="sxs-lookup"><span data-stu-id="74b98-155">Meaning</span></span></th>
<th align="left"><span data-ttu-id="74b98-156">色彩</span><span class="sxs-lookup"><span data-stu-id="74b98-156">Color</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="74b98-157">無</span><span class="sxs-lookup"><span data-stu-id="74b98-157">None</span></span></p></td>
<td align="left"><p><span data-ttu-id="74b98-158">在兩個 Gpo 中都存在具有相同設定的專案</span><span class="sxs-lookup"><span data-stu-id="74b98-158">Item exists with identical settings in both GPOs</span></span></p></td>
<td align="left"><p><span data-ttu-id="74b98-159">依層級而異</span><span class="sxs-lookup"><span data-stu-id="74b98-159">Varies with level</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="74b98-160">[#]</span><span class="sxs-lookup"><span data-stu-id="74b98-160">[#]</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="74b98-161">專案存在於兩個 Gpo 中，但具有已變更的設定</span><span class="sxs-lookup"><span data-stu-id="74b98-161">Item exists in both GPOs, but with changed settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="74b98-162">天藍色</span><span class="sxs-lookup"><span data-stu-id="74b98-162">Blue</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="74b98-163">[-]</span><span class="sxs-lookup"><span data-stu-id="74b98-163">[-]</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="74b98-164">只有在第一個 GPO 中存在專案</span><span class="sxs-lookup"><span data-stu-id="74b98-164">Item exists only in the first GPO</span></span></p></td>
<td align="left"><p><span data-ttu-id="74b98-165">紅色</span><span class="sxs-lookup"><span data-stu-id="74b98-165">Red</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="74b98-166">[+]</span><span class="sxs-lookup"><span data-stu-id="74b98-166">[+]</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="74b98-167">只有在第二個 GPO 中存在專案</span><span class="sxs-lookup"><span data-stu-id="74b98-167">Item exists only in the second GPO</span></span></p></td>
<td align="left"><p><span data-ttu-id="74b98-168">綠色</span><span class="sxs-lookup"><span data-stu-id="74b98-168">Green</span></span></p></td>
</tr>
</tbody>
</table>



-   <span data-ttu-id="74b98-169">針對具有已變更之設定的專案，已變更的設定會在專案展開時加以識別。</span><span class="sxs-lookup"><span data-stu-id="74b98-169">For items with changed settings, the changed settings are identified when the item is expanded.</span></span> <span data-ttu-id="74b98-170">每個 GPO 中屬性的值會以 Gpo 在報表中顯示的順序顯示。</span><span class="sxs-lookup"><span data-stu-id="74b98-170">The value for the attribute in each GPO is displayed in the same order that the GPOs are displayed in the report.</span></span>

-   <span data-ttu-id="74b98-171">設定的部分變更可能會導致將專案報告成兩個不同的專案（只有在第一個 GPO 中有一個，而不是在第二個 GPO 中提供，而不是在一個已變更的專案中出現）。</span><span class="sxs-lookup"><span data-stu-id="74b98-171">Some changes to settings may cause an item to be reported as two different items (one present only in the first GPO, one present only in the second), rather than as one item that has changed.</span></span>

### <span data-ttu-id="74b98-172">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="74b98-172">Additional references</span></span>

-   [<span data-ttu-id="74b98-173">內容索引標籤</span><span class="sxs-lookup"><span data-stu-id="74b98-173">Contents Tab</span></span>](contents-tab-agpm30ops.md)









