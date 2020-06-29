---
title: 歷程記錄視窗
description: 歷程記錄視窗
author: dansimp
ms.assetid: f11f9ad9-bffe-4c56-8c46-fe9c0a8e55c1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 02b4336409f33d6c1f2868bceb22cb95120f2198
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802757"
---
# <span data-ttu-id="7f7c9-103">歷程記錄視窗</span><span class="sxs-lookup"><span data-stu-id="7f7c9-103">History Window</span></span>


<span data-ttu-id="7f7c9-104">您可以按兩下某個 GPO，或以滑鼠右鍵按一下某個 GPO，然後按一下 [歷程**記錄**]，以顯示該群群組原則物件（GPO）的歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="7f7c9-104">The history of a Group Policy object (GPO) can be displayed by double-clicking a GPO or by right-clicking a GPO and then clicking **History**.</span></span> <span data-ttu-id="7f7c9-105">它也會顯示在**群組原則管理主控台**（GPMC）中作為每個 GPO 的索引標籤。</span><span class="sxs-lookup"><span data-stu-id="7f7c9-105">It is also displayed in the **Group Policy Management Console** (GPMC) as a tab for each GPO.</span></span>

<span data-ttu-id="7f7c9-106">[歷程記錄] 會提供儲存在封存中之所有已選取 GPO 版本的清單。</span><span class="sxs-lookup"><span data-stu-id="7f7c9-106">The history provides a list of all versions of the selected GPO saved within the archive.</span></span> <span data-ttu-id="7f7c9-107">您可以從 [歷程**記錄**] 視窗取得 gpo 中的設定報告、比較多個 gpo 版本，或回滾到舊版的 gpo。</span><span class="sxs-lookup"><span data-stu-id="7f7c9-107">From the **History** window, you can obtain a report of the settings within a GPO, compare multiple versions of a GPO, or roll back to a previous version of a GPO.</span></span>

## <span data-ttu-id="7f7c9-108">在 [歷程記錄] 視窗中篩選事件</span><span class="sxs-lookup"><span data-stu-id="7f7c9-108">Filtering events in the History window</span></span>


<span data-ttu-id="7f7c9-109">[歷程**記錄**] 視窗中的索引標籤會篩選顯示的事件。</span><span class="sxs-lookup"><span data-stu-id="7f7c9-109">The tabs within the **History** window filter the events displayed.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="7f7c9-110">索引標籤</span><span class="sxs-lookup"><span data-stu-id="7f7c9-110">Tabs</span></span></th>
<th align="left"><span data-ttu-id="7f7c9-111">篩選</span><span class="sxs-lookup"><span data-stu-id="7f7c9-111">Filtering</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="7f7c9-112">全部顯示</span><span class="sxs-lookup"><span data-stu-id="7f7c9-112">Show All</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="7f7c9-113">顯示所有版本的 GPO。</span><span class="sxs-lookup"><span data-stu-id="7f7c9-113">Display all versions of the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="7f7c9-114">已檢入</span><span class="sxs-lookup"><span data-stu-id="7f7c9-114">Checked In</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="7f7c9-115">只顯示 GPO 的簽入版本。</span><span class="sxs-lookup"><span data-stu-id="7f7c9-115">Display only checked-in versions of the GPO.</span></span> <span data-ttu-id="7f7c9-116">此清單中省略了已部署的版本。</span><span class="sxs-lookup"><span data-stu-id="7f7c9-116">The deployed version is omitted from this list.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="7f7c9-117">僅限標籤</span><span class="sxs-lookup"><span data-stu-id="7f7c9-117">Labels Only</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="7f7c9-118">只顯示有關聯標籤的 Gpo。</span><span class="sxs-lookup"><span data-stu-id="7f7c9-118">Display only GPOs that have labels associated with them.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="7f7c9-119">事件資訊</span><span class="sxs-lookup"><span data-stu-id="7f7c9-119">Event information</span></span>


<span data-ttu-id="7f7c9-120">針對所選 GPO 之歷程記錄中的每個事件提供資訊。</span><span class="sxs-lookup"><span data-stu-id="7f7c9-120">Information is provided for each event in the history of the selected GPO.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="7f7c9-121">GPO 特性</span><span class="sxs-lookup"><span data-stu-id="7f7c9-121">GPO Characteristic</span></span></th>
<th align="left"><span data-ttu-id="7f7c9-122">說明</span><span class="sxs-lookup"><span data-stu-id="7f7c9-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="7f7c9-123">電腦</span><span class="sxs-lookup"><span data-stu-id="7f7c9-123">Computer</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="7f7c9-124">GPO 的電腦設定部分自動產生的版本。</span><span class="sxs-lookup"><span data-stu-id="7f7c9-124">Automatically generated version of the Computer Configuration portion of the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="7f7c9-125">使用者</span><span class="sxs-lookup"><span data-stu-id="7f7c9-125">User</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="7f7c9-126">GPO 的使用者設定部分的自動產生版本。</span><span class="sxs-lookup"><span data-stu-id="7f7c9-126">Automatically generated version of the User Configuration portion of the GPO.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="7f7c9-127">時間</span><span class="sxs-lookup"><span data-stu-id="7f7c9-127">Time</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="7f7c9-128">在 [狀態] 欄位中執行動作時，GPO 版本的時間戳記。</span><span class="sxs-lookup"><span data-stu-id="7f7c9-128">Timestamp of the version of the GPO when the action in the status field was performed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="7f7c9-129">狀態</span><span class="sxs-lookup"><span data-stu-id="7f7c9-129">State</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="7f7c9-130">所選 GPO 版本的狀態：</span><span class="sxs-lookup"><span data-stu-id="7f7c9-130">The state of the selected version of the GPO:</span></span></p>
<p><img src="images/36f6b687-f5cc-40d1-805f-b191d1fb1ace.gif" alt="Deployed GPO icon" /> <strong><span data-ttu-id="7f7c9-131"></strong>已部署：此版本的 GPO 目前在生產環境中。</span><span class="sxs-lookup"><span data-stu-id="7f7c9-131">Deployed</strong>: This version of the GPO is currently live in the production environment.</span></span></p>
<p><img src="images/57b610a5-1c71-4d26-9173-d04abd495fcc.gif" alt="Checked in GPO icon" /> <strong><span data-ttu-id="7f7c9-132">已檢入 </strong> ：此版本的 GPO 可供授權的編輯者取出，以供您用來進行編輯或供群群組原則管理員部署。</span><span class="sxs-lookup"><span data-stu-id="7f7c9-132">Checked In</strong>: This version of the GPO is available for authorized Editors to check out for editing or for a Group Policy administrator to deploy.</span></span></p>
<p><img src="images/8e7a7c4e-809a-435a-8b29-30d797936210.gif" alt="Checked out GPO icon" /> <strong><span data-ttu-id="7f7c9-133">已取出 </strong> ：此版本的 GPO 目前已由編輯工具取出，不適用於其他編輯器。</span><span class="sxs-lookup"><span data-stu-id="7f7c9-133">Checked Out</strong>: This version of the GPO is currently checked out by an Editor and is unavailable for other Editors.</span></span> <span data-ttu-id="7f7c9-134">（取出狀態不會記錄在 <strong>[歷程記錄] </strong> ，除了指出 GPO 目前是否已取出。</span><span class="sxs-lookup"><span data-stu-id="7f7c9-134">(The checked out state is not recorded in the <strong>History</strong> except to indicate if a GPO is currently checked out.)</span></span></p>
<p><img src="images/327623bd-0842-4372-be1f-bdc4b8c3481c.gif" alt="Created GPO icon" /> <strong><span data-ttu-id="7f7c9-135">已建立 </strong> ：識別最初建立 GPO 的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="7f7c9-135">Created</strong>: Identifies the date and time of the initial creation of the GPO.</span></span></p>
<p><img src="images/8356fcdc-1279-425b-ab14-a23bcfe391da.gif" alt="Labeled GPO icon" /> <strong><span data-ttu-id="7f7c9-136">標示 </strong> ：識別 GPO 的標示版本。</span><span class="sxs-lookup"><span data-stu-id="7f7c9-136">Labeled</strong>: Identifies a labeled version of the GPO.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="7f7c9-137">GPO 狀態</span><span class="sxs-lookup"><span data-stu-id="7f7c9-137">GPO Status</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="7f7c9-138">您可以彼此獨立管理電腦配置和使用者設定。</span><span class="sxs-lookup"><span data-stu-id="7f7c9-138">The Computer Configuration and the User Configuration can be managed separately from each other.</span></span> <span data-ttu-id="7f7c9-139">此狀態會顯示已啟用 GPO 的哪些部分。</span><span class="sxs-lookup"><span data-stu-id="7f7c9-139">This status shows which portions of the GPO are enabled.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="7f7c9-140">擁有者</span><span class="sxs-lookup"><span data-stu-id="7f7c9-140">Owner</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="7f7c9-141">已檢入或部署 GPO 的人員。</span><span class="sxs-lookup"><span data-stu-id="7f7c9-141">The person who checked in or deployed the GPO.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="7f7c9-142">留言</span><span class="sxs-lookup"><span data-stu-id="7f7c9-142">Comment</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="7f7c9-143">在修改此版本時，由 GPO 擁有者輸入的留言。</span><span class="sxs-lookup"><span data-stu-id="7f7c9-143">A comment entered by the owner of a GPO at the time that this version was modified.</span></span> <span data-ttu-id="7f7c9-144">在需要回滾到前一個版本的情況下，識別版本的詳細資訊時很有用。</span><span class="sxs-lookup"><span data-stu-id="7f7c9-144">Useful for identifying the specifics of the version in case of the need to roll back to a previous version.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="7f7c9-145">報告</span><span class="sxs-lookup"><span data-stu-id="7f7c9-145">Reports</span></span>


<span data-ttu-id="7f7c9-146">根據是否已選取單一 GPO 版本或多個 GPO 版本，[**設定**] 和 [**差異**] 按鈕會顯示 GPO 設定的報告。</span><span class="sxs-lookup"><span data-stu-id="7f7c9-146">Depending on whether a single GPO version or multiple GPO versions are selected, the **Settings** and **Differences** buttons display reports on GPO settings.</span></span> <span data-ttu-id="7f7c9-147">以滑鼠右鍵按一下 [GPO 版本]，也會提供顯示 XML 報表的選項。</span><span class="sxs-lookup"><span data-stu-id="7f7c9-147">Right-clicking GPO versions provides the option to display XML-based reports as well.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="7f7c9-148">Button</span><span class="sxs-lookup"><span data-stu-id="7f7c9-148">Button</span></span></th>
<th align="left"><span data-ttu-id="7f7c9-149">效果</span><span class="sxs-lookup"><span data-stu-id="7f7c9-149">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="7f7c9-150">設定</span><span class="sxs-lookup"><span data-stu-id="7f7c9-150">Settings</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="7f7c9-151">產生以 HTML 為基礎的報告，其中顯示所選版本之 GPO 中的設定。</span><span class="sxs-lookup"><span data-stu-id="7f7c9-151">Generate an HTML-based report displaying the settings within the selected version of the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="7f7c9-152">多種</span><span class="sxs-lookup"><span data-stu-id="7f7c9-152">Differences</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="7f7c9-153">產生與多個選取版本之 GPO 中的設定比較的 HTML 報告。</span><span class="sxs-lookup"><span data-stu-id="7f7c9-153">Generate an HTML-based report comparing the settings within multiple selected versions of the GPO.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="7f7c9-154">差異報告的主要</span><span class="sxs-lookup"><span data-stu-id="7f7c9-154">Key to difference reports</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="7f7c9-155">符號</span><span class="sxs-lookup"><span data-stu-id="7f7c9-155">Symbol</span></span></th>
<th align="left"><span data-ttu-id="7f7c9-156">意義</span><span class="sxs-lookup"><span data-stu-id="7f7c9-156">Meaning</span></span></th>
<th align="left"><span data-ttu-id="7f7c9-157">色彩</span><span class="sxs-lookup"><span data-stu-id="7f7c9-157">Color</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7f7c9-158">無</span><span class="sxs-lookup"><span data-stu-id="7f7c9-158">None</span></span></p></td>
<td align="left"><p><span data-ttu-id="7f7c9-159">在兩個 Gpo 中都存在具有相同設定的專案</span><span class="sxs-lookup"><span data-stu-id="7f7c9-159">Item exists with identical settings in both GPOs</span></span></p></td>
<td align="left"><p><span data-ttu-id="7f7c9-160">依層級而異</span><span class="sxs-lookup"><span data-stu-id="7f7c9-160">Varies with level</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="7f7c9-161">[#]</span><span class="sxs-lookup"><span data-stu-id="7f7c9-161">[#]</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="7f7c9-162">專案存在於兩個 Gpo 中，但具有已變更的設定</span><span class="sxs-lookup"><span data-stu-id="7f7c9-162">Item exists in both GPOs, but with changed settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="7f7c9-163">天藍色</span><span class="sxs-lookup"><span data-stu-id="7f7c9-163">Blue</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="7f7c9-164">[-]</span><span class="sxs-lookup"><span data-stu-id="7f7c9-164">[-]</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="7f7c9-165">只有在第一個 GPO 中存在專案</span><span class="sxs-lookup"><span data-stu-id="7f7c9-165">Item exists only in the first GPO</span></span></p></td>
<td align="left"><p><span data-ttu-id="7f7c9-166">紅色</span><span class="sxs-lookup"><span data-stu-id="7f7c9-166">Red</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="7f7c9-167">[+]</span><span class="sxs-lookup"><span data-stu-id="7f7c9-167">[+]</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="7f7c9-168">只有在第二個 GPO 中存在專案</span><span class="sxs-lookup"><span data-stu-id="7f7c9-168">Item exists only in the second GPO</span></span></p></td>
<td align="left"><p><span data-ttu-id="7f7c9-169">綠色</span><span class="sxs-lookup"><span data-stu-id="7f7c9-169">Green</span></span></p></td>
</tr>
</tbody>
</table>

 

-   <span data-ttu-id="7f7c9-170">針對具有已變更之設定的專案，已變更的設定會在專案展開時加以識別。</span><span class="sxs-lookup"><span data-stu-id="7f7c9-170">For items with changed settings, the changed settings are identified when the item is expanded.</span></span> <span data-ttu-id="7f7c9-171">每個 GPO 中屬性的值會以 Gpo 在報表中顯示的順序顯示。</span><span class="sxs-lookup"><span data-stu-id="7f7c9-171">The value for the attribute in each GPO is displayed in the same order that the GPOs are displayed in the report.</span></span>

-   <span data-ttu-id="7f7c9-172">設定的部分變更可能會導致將專案報告成兩個不同的專案（只有在第一個 GPO 中有一個，而不是在第二個 GPO 中提供，而不是在一個已變更的專案中出現）。</span><span class="sxs-lookup"><span data-stu-id="7f7c9-172">Some changes to settings may cause an item to be reported as two different items (one present only in the first GPO, one present only in the second), rather than as one item that has changed.</span></span>

### <span data-ttu-id="7f7c9-173">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="7f7c9-173">Additional references</span></span>

-   [<span data-ttu-id="7f7c9-174">內容索引標籤</span><span class="sxs-lookup"><span data-stu-id="7f7c9-174">Contents Tab</span></span>](contents-tab.md)

 

 





