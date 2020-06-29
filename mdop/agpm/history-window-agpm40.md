---
title: 歷程記錄視窗
description: 歷程記錄視窗
author: dansimp
ms.assetid: 5bea62e7-d267-40b2-a66d-fb1be7373a1c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 81f19e3834e945a45238856e23f6ee4a86407c4a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802758"
---
# <span data-ttu-id="d71a7-103">歷程記錄視窗</span><span class="sxs-lookup"><span data-stu-id="d71a7-103">History Window</span></span>


<span data-ttu-id="d71a7-104">您可以按兩下某個 GPO，或以滑鼠右鍵按一下某個 GPO，然後按一下 [歷程**記錄**]，以顯示該群群組原則物件（GPO）的歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="d71a7-104">The history of a Group Policy Object (GPO) can be displayed by double-clicking a GPO or by right-clicking a GPO and then clicking **History**.</span></span> <span data-ttu-id="d71a7-105">它也會顯示在群組原則管理主控台（GPMC）中作為每個 GPO 的索引標籤。</span><span class="sxs-lookup"><span data-stu-id="d71a7-105">It is also displayed in the Group Policy Management Console (GPMC) as a tab for each GPO.</span></span>

<span data-ttu-id="d71a7-106">[歷程記錄] 會在所選 GPO 的生命週期中提供事件記錄。</span><span class="sxs-lookup"><span data-stu-id="d71a7-106">The history provides a record of events in the lifetime of the selected GPO.</span></span> <span data-ttu-id="d71a7-107">您可以從 [歷程**記錄**] 視窗取得 gpo 版本中的設定報告、比較多個版本的 gpo，或回滾到舊版的 gpo。</span><span class="sxs-lookup"><span data-stu-id="d71a7-107">From the **History** window, you can obtain a report of the settings in a version of the GPO, compare multiple versions of a GPO, or roll back to an earlier version of a GPO.</span></span>

## <span data-ttu-id="d71a7-108">在 [歷程記錄] 視窗中篩選事件</span><span class="sxs-lookup"><span data-stu-id="d71a7-108">Filtering events in the History window</span></span>


<span data-ttu-id="d71a7-109">[歷程**記錄**] 視窗中的索引標籤會篩選 GPO 歷程記錄中的狀態。</span><span class="sxs-lookup"><span data-stu-id="d71a7-109">The tabs within the **History** window filter the states in the history of the GPO.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d71a7-110">索引標籤</span><span class="sxs-lookup"><span data-stu-id="d71a7-110">Tabs</span></span></th>
<th align="left"><span data-ttu-id="d71a7-111">篩選</span><span class="sxs-lookup"><span data-stu-id="d71a7-111">Filtering</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="d71a7-112">所有狀態</span><span class="sxs-lookup"><span data-stu-id="d71a7-112">All States</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="d71a7-113">顯示 GPO 歷程記錄中的所有狀態。</span><span class="sxs-lookup"><span data-stu-id="d71a7-113">Display all states in the history of the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="d71a7-114">唯一版本</span><span class="sxs-lookup"><span data-stu-id="d71a7-114">Unique Versions</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="d71a7-115">只顯示已核取到封存中之 GPO 的唯一版本。</span><span class="sxs-lookup"><span data-stu-id="d71a7-115">Display only unique versions of the GPO checked into the archive.</span></span> <span data-ttu-id="d71a7-116">此清單中省略了部署到生產環境的版本、唯一版本的快捷方式及資訊狀態。</span><span class="sxs-lookup"><span data-stu-id="d71a7-116">The version deployed to the production environment, shortcuts to unique versions, and informational states are omitted from this list.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="d71a7-117">事件資訊</span><span class="sxs-lookup"><span data-stu-id="d71a7-117">Event information</span></span>


<span data-ttu-id="d71a7-118">提供有關 GPO 歷程記錄中每個狀態的資訊。</span><span class="sxs-lookup"><span data-stu-id="d71a7-118">Information is provided for each state in the history of the GPO.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d71a7-119">GPO 屬性</span><span class="sxs-lookup"><span data-stu-id="d71a7-119">GPO attribute</span></span></th>
<th align="left"><span data-ttu-id="d71a7-120">描述</span><span class="sxs-lookup"><span data-stu-id="d71a7-120">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="d71a7-121">變更日期</span><span class="sxs-lookup"><span data-stu-id="d71a7-121">Change Date</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="d71a7-122">[ <strong> 省/市/自治區] 資料行中動作的時間戳記 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="d71a7-122">Time stamp of when the action in the <strong>State</strong> column was performed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="d71a7-123">狀態</span><span class="sxs-lookup"><span data-stu-id="d71a7-123">State</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="d71a7-124">GPO 歷程記錄中的狀態。</span><span class="sxs-lookup"><span data-stu-id="d71a7-124">A state in the history of the GPO.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="d71a7-125">變更者</span><span class="sxs-lookup"><span data-stu-id="d71a7-125">Changed By</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="d71a7-126">已檢入或部署 GPO 的人員。</span><span class="sxs-lookup"><span data-stu-id="d71a7-126">The person who checked in or deployed the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="d71a7-127">留言</span><span class="sxs-lookup"><span data-stu-id="d71a7-127">Comment</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="d71a7-128">在此版本變更時，由檢入或部署 GPO 的人員所輸入的批註，在需要回滾至較舊版本的情況下，這對於識別版本的詳細資訊很有用。</span><span class="sxs-lookup"><span data-stu-id="d71a7-128">A comment entered by the person who checked in or deployed a GPO at the time that this version was changed, useful for identifying the specifics of the version in case of the need to roll back to an earlier version.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="d71a7-129">已</span><span class="sxs-lookup"><span data-stu-id="d71a7-129">Deletable</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="d71a7-130">如果封存中保留的每個 GPO 的唯一版本數受到限制，是否可刪除此 GPO 版本。</span><span class="sxs-lookup"><span data-stu-id="d71a7-130">Whether this version of the GPO can be deleted if the number of unique versions of each GPO retained in the archive is limited.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="d71a7-131">注意</span><span class="sxs-lookup"><span data-stu-id="d71a7-131">Note</span></span></strong><br/><p><span data-ttu-id="d71a7-132">您可以在 GPO 上按一下滑鼠右鍵，然後按一下 [不 <strong> 允許刪除] </strong> 或 [ <strong> 允許刪除]，以變更 gpo 的版本是否可刪除 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="d71a7-132">You can change whether a version of a GPO can be deleted by right-clicking the GPO and then clicking <strong>Do Not Allow Deletion</strong> or <strong>Allow Deletion</strong>.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="d71a7-133">電腦版本</span><span class="sxs-lookup"><span data-stu-id="d71a7-133">Computer Version</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="d71a7-134">GPO 的 [電腦設定] 元件的自動產生版本。</span><span class="sxs-lookup"><span data-stu-id="d71a7-134">Automatically generated version of the Computer Configuration part of the GPO.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="d71a7-135">使用者版本</span><span class="sxs-lookup"><span data-stu-id="d71a7-135">User Version</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="d71a7-136">GPO 的使用者設定部分自動產生的版本。</span><span class="sxs-lookup"><span data-stu-id="d71a7-136">Automatically generated version of the User Configuration part of the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="d71a7-137">GPO 狀態</span><span class="sxs-lookup"><span data-stu-id="d71a7-137">GPO Status</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="d71a7-138">您可以彼此獨立管理電腦配置和使用者設定。</span><span class="sxs-lookup"><span data-stu-id="d71a7-138">The Computer Configuration and the User Configuration can be managed separately from each other.</span></span> <span data-ttu-id="d71a7-139">此狀態會顯示已啟用 GPO 的哪些部分。</span><span class="sxs-lookup"><span data-stu-id="d71a7-139">This status shows which portions of the GPO are enabled.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="d71a7-140">來源 GPO 資訊</span><span class="sxs-lookup"><span data-stu-id="d71a7-140">Source GPO Information</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="d71a7-141">如果 GPO 是從另一個目錄林匯入，則為與上次變更相關聯的原始 GPO 名稱、網域和使用者及日期。</span><span class="sxs-lookup"><span data-stu-id="d71a7-141">For a GPO that has been imported from another forest, the original GPO name, domain, and user and date associated with the last change.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="d71a7-142">報告</span><span class="sxs-lookup"><span data-stu-id="d71a7-142">Reports</span></span>


<span data-ttu-id="d71a7-143">[**設定**] 和 [**差異**] 按鈕會顯示所選 gpo 版本或版本的 gpo 設定報告。</span><span class="sxs-lookup"><span data-stu-id="d71a7-143">The **Settings** and **Differences** buttons display reports about GPO settings for the GPO version or versions selected.</span></span> <span data-ttu-id="d71a7-144">此外，您也可以用滑鼠右鍵按一下 GPO 版本或版本，提供顯示以 XML 為基礎的報表的選項。</span><span class="sxs-lookup"><span data-stu-id="d71a7-144">Also, right-clicking a GPO version or versions provides the option to display XML-based reports.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d71a7-145">Button</span><span class="sxs-lookup"><span data-stu-id="d71a7-145">Button</span></span></th>
<th align="left"><span data-ttu-id="d71a7-146">效果</span><span class="sxs-lookup"><span data-stu-id="d71a7-146">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="d71a7-147">設定</span><span class="sxs-lookup"><span data-stu-id="d71a7-147">Settings</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="d71a7-148">產生以 HTML 為基礎的報告，其中顯示所選版本之 GPO 中的設定。</span><span class="sxs-lookup"><span data-stu-id="d71a7-148">Generate an HTML-based report displaying the settings within the selected version of the GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="d71a7-149">多種</span><span class="sxs-lookup"><span data-stu-id="d71a7-149">Differences</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="d71a7-150">產生與多個選取版本之 GPO 中的設定比較的 HTML 報告。</span><span class="sxs-lookup"><span data-stu-id="d71a7-150">Generate an HTML-based report comparing the settings within multiple selected versions of the GPO.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="d71a7-151">差異報告的主要</span><span class="sxs-lookup"><span data-stu-id="d71a7-151">Key to difference reports</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d71a7-152">符號</span><span class="sxs-lookup"><span data-stu-id="d71a7-152">Symbol</span></span></th>
<th align="left"><span data-ttu-id="d71a7-153">意義</span><span class="sxs-lookup"><span data-stu-id="d71a7-153">Meaning</span></span></th>
<th align="left"><span data-ttu-id="d71a7-154">色彩</span><span class="sxs-lookup"><span data-stu-id="d71a7-154">Color</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d71a7-155">無</span><span class="sxs-lookup"><span data-stu-id="d71a7-155">None</span></span></p></td>
<td align="left"><p><span data-ttu-id="d71a7-156">在兩個 Gpo 中都存在具有相同設定的專案</span><span class="sxs-lookup"><span data-stu-id="d71a7-156">Item exists with identical settings in both GPOs</span></span></p></td>
<td align="left"><p><span data-ttu-id="d71a7-157">依層級而異</span><span class="sxs-lookup"><span data-stu-id="d71a7-157">Varies with level</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="d71a7-158">[#]</span><span class="sxs-lookup"><span data-stu-id="d71a7-158">[#]</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="d71a7-159">專案存在於兩個 Gpo 中，但具有已變更的設定</span><span class="sxs-lookup"><span data-stu-id="d71a7-159">Item exists in both GPOs, but with changed settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="d71a7-160">天藍色</span><span class="sxs-lookup"><span data-stu-id="d71a7-160">Blue</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="d71a7-161">[-]</span><span class="sxs-lookup"><span data-stu-id="d71a7-161">[-]</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="d71a7-162">只有在第一個 GPO 中存在專案</span><span class="sxs-lookup"><span data-stu-id="d71a7-162">Item exists only in the first GPO</span></span></p></td>
<td align="left"><p><span data-ttu-id="d71a7-163">紅色</span><span class="sxs-lookup"><span data-stu-id="d71a7-163">Red</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="d71a7-164">[+]</span><span class="sxs-lookup"><span data-stu-id="d71a7-164">[+]</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="d71a7-165">只有在第二個 GPO 中存在專案</span><span class="sxs-lookup"><span data-stu-id="d71a7-165">Item exists only in the second GPO</span></span></p></td>
<td align="left"><p><span data-ttu-id="d71a7-166">綠色</span><span class="sxs-lookup"><span data-stu-id="d71a7-166">Green</span></span></p></td>
</tr>
</tbody>
</table>



-   <span data-ttu-id="d71a7-167">針對具有已變更之設定的專案，已變更的設定會在專案展開時加以識別。</span><span class="sxs-lookup"><span data-stu-id="d71a7-167">For items with changed settings, the changed settings are identified when the item is expanded.</span></span> <span data-ttu-id="d71a7-168">每個 GPO 中屬性的值會以 Gpo 在報表中顯示的順序顯示。</span><span class="sxs-lookup"><span data-stu-id="d71a7-168">The value for the attribute in each GPO is displayed in the same order that the GPOs are displayed in the report.</span></span>

-   <span data-ttu-id="d71a7-169">設定的部分變更可能會導致將專案報告為兩個專案（只有在第一個 GPO 中有一個專案，第二個是在第二個 GPO 中提供，而另一個僅存在於第二個專案，</span><span class="sxs-lookup"><span data-stu-id="d71a7-169">Some changes to settings may cause an item to be reported as two items (one present only in the first GPO, one present only in the second), instead of one item that has changed.</span></span>

### <span data-ttu-id="d71a7-170">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="d71a7-170">Additional references</span></span>

-   [<span data-ttu-id="d71a7-171">內容索引標籤</span><span class="sxs-lookup"><span data-stu-id="d71a7-171">Contents Tab</span></span>](contents-tab-agpm40.md)









