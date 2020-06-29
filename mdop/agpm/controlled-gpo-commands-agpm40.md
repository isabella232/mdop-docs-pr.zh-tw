---
title: 受控制的 GPO 命令
description: 受控制的 GPO 命令
author: dansimp
ms.assetid: 370d3db9-4efc-4799-983d-e29ba5f32b07
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 65e9d06beb4c36762e845e452bab497a8d3da747
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802889"
---
# <span data-ttu-id="c86e6-103">受控制的 GPO 命令</span><span class="sxs-lookup"><span data-stu-id="c86e6-103">Controlled GPO Commands</span></span>


<span data-ttu-id="c86e6-104">[**受控**] 索引標籤：</span><span class="sxs-lookup"><span data-stu-id="c86e6-104">The **Controlled** tab:</span></span>

-   <span data-ttu-id="c86e6-105">顯示由 [高級群組原則管理（AGPM）] 管理的群組原則物件（Gpo）清單。</span><span class="sxs-lookup"><span data-stu-id="c86e6-105">Displays a list of Group Policy Objects (GPOs) managed by Advanced Group Policy Management (AGPM).</span></span>

-   <span data-ttu-id="c86e6-106">提供快捷方式功能表，其中包含管理 Gpo 及顯示 Gpo 的記錄和報告的命令。</span><span class="sxs-lookup"><span data-stu-id="c86e6-106">Provides a shortcut menu with commands for managing GPOs and for displaying the history and reports for GPOs.</span></span>

-   <span data-ttu-id="c86e6-107">顯示有許可權存取所選 GPO 的群組和使用者清單。</span><span class="sxs-lookup"><span data-stu-id="c86e6-107">Displays a list of the groups and users who have permission to access a selected GPO.</span></span>

<span data-ttu-id="c86e6-108">以滑鼠右鍵按一下此索引標籤上的 [**群組原則物件**] 清單，會顯示快捷方式功能表。</span><span class="sxs-lookup"><span data-stu-id="c86e6-108">Right-clicking the **Group Policy Objects** list on this tab displays a shortcut menu.</span></span> <span data-ttu-id="c86e6-109">這個功能表包含下列任何一項適用的選項。</span><span class="sxs-lookup"><span data-stu-id="c86e6-109">This menu includes whichever of the following options are applicable.</span></span>

## <span data-ttu-id="c86e6-110">控制項與歷程記錄</span><span class="sxs-lookup"><span data-stu-id="c86e6-110">Control and history</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c86e6-111">命令</span><span class="sxs-lookup"><span data-stu-id="c86e6-111">Command</span></span></th>
<th align="left"><span data-ttu-id="c86e6-112">效果</span><span class="sxs-lookup"><span data-stu-id="c86e6-112">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="c86e6-113">新的受控 GPO</span><span class="sxs-lookup"><span data-stu-id="c86e6-113">New Controlled GPO</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="c86e6-114">透過 AGPM 管理變更控制來建立新的 GPO，並將它部署到網域的生產環境。</span><span class="sxs-lookup"><span data-stu-id="c86e6-114">Create a new GPO with change control managed through AGPM and deploy it to the production environment of the domain.</span></span> <span data-ttu-id="c86e6-115">如果您沒有建立 GPO 的許可權，系統會提示您提交要求。</span><span class="sxs-lookup"><span data-stu-id="c86e6-115">If you do not have permission to create a GPO, you are prompted to submit a request.</span></span> <span data-ttu-id="c86e6-116">（如果按一下滑鼠右鍵， <strong> 則會顯示此選項（如果沒有選取 GPO 的話）[群組原則物件] </strong> 清單。）</span><span class="sxs-lookup"><span data-stu-id="c86e6-116">(This option is displayed if no GPO is selected when right-clicking in the <strong>Group Policy Objects</strong> list.)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="c86e6-117">歷程記錄</span><span class="sxs-lookup"><span data-stu-id="c86e6-117">History</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="c86e6-118">開啟一個視窗，列出已儲存在封存中的所有已選取 GPO 版本。</span><span class="sxs-lookup"><span data-stu-id="c86e6-118">Open a window listing all versions of the selected GPO saved within the archive.</span></span> <span data-ttu-id="c86e6-119">您可以從 [歷程記錄] 取得 GPO 中的設定報告、比較 GPO 的兩個版本、比較 GPO 與範本，或回滾到舊版的 GPO。</span><span class="sxs-lookup"><span data-stu-id="c86e6-119">From the history, you can obtain a report of the settings within a GPO, compare two versions of a GPO, compare a GPO to a template, or roll back to an earlier version of a GPO.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="c86e6-120">報告</span><span class="sxs-lookup"><span data-stu-id="c86e6-120">Reports</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c86e6-121">命令</span><span class="sxs-lookup"><span data-stu-id="c86e6-121">Command</span></span></th>
<th align="left"><span data-ttu-id="c86e6-122">效果</span><span class="sxs-lookup"><span data-stu-id="c86e6-122">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="c86e6-123">設定</span><span class="sxs-lookup"><span data-stu-id="c86e6-123">Settings</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="c86e6-124">產生顯示所選 GPO 中設定的 HTML 或 XML 報告，或從組織單位顯示所選 GPO 的連結（如果 GPO 是最近控制、匯入或檢入）。</span><span class="sxs-lookup"><span data-stu-id="c86e6-124">Generate an HTML-based or XML-based report displaying the settings within the selected GPO or display links to the selected GPO(s) from organizational units as of when the GPO(s) was most recently controlled, imported, or checked in.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="c86e6-125">多種</span><span class="sxs-lookup"><span data-stu-id="c86e6-125">Differences</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="c86e6-126">產生與兩個選取 Gpo 或所選 GPO 及範本中的設定比較的 HTML 或 XML 式報告。</span><span class="sxs-lookup"><span data-stu-id="c86e6-126">Generate an HTML-based or XML-based report comparing the settings within two selected GPOs or within the selected GPO and a template.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="c86e6-127">編輯</span><span class="sxs-lookup"><span data-stu-id="c86e6-127">Editing</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c86e6-128">命令</span><span class="sxs-lookup"><span data-stu-id="c86e6-128">Command</span></span></th>
<th align="left"><span data-ttu-id="c86e6-129">效果</span><span class="sxs-lookup"><span data-stu-id="c86e6-129">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="c86e6-130">編輯</span><span class="sxs-lookup"><span data-stu-id="c86e6-130">Edit</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="c86e6-131">開啟 [ <strong> 群組原則管理編輯器 </strong> ] 視窗，變更選取的 GPO。</span><span class="sxs-lookup"><span data-stu-id="c86e6-131">Open the <strong>Group Policy Management Editor</strong> window to change the selected GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="c86e6-132">退房</span><span class="sxs-lookup"><span data-stu-id="c86e6-132">Check Out</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="c86e6-133">從封存中取得選取的 GPO 的複本以進行離線編輯，並禁止任何人編輯該 GPO，直到將其檢入回封存為止。</span><span class="sxs-lookup"><span data-stu-id="c86e6-133">Obtain a copy of the selected GPO from the archive for offline editing and prohibit anyone else from editing the GPO until it is checked back into the archive.</span></span> <span data-ttu-id="c86e6-134">您可以透過 AGPM 管理員（完全控制）來取代取出。</span><span class="sxs-lookup"><span data-stu-id="c86e6-134">Check Out can be overridden by an AGPM Administrator (Full Control).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="c86e6-135">登記</span><span class="sxs-lookup"><span data-stu-id="c86e6-135">Check In</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="c86e6-136">將所選 GPO 的已編輯版本檢查到封存中，讓其他授權編輯者可以進行變更，或將該 GPO 部署到網域的生產環境。</span><span class="sxs-lookup"><span data-stu-id="c86e6-136">Check the edited version of the selected GPO into the archive, so other authorized Editors can make changes or an Approver can deploy the GPO to the production environment of the domain.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="c86e6-137">復原取出</span><span class="sxs-lookup"><span data-stu-id="c86e6-137">Undo Check Out</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="c86e6-138">將已取出的 GPO 傳回封存，且不做任何變更。</span><span class="sxs-lookup"><span data-stu-id="c86e6-138">Return a checked out GPO to the archive without any changes.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="c86e6-139">版本管理</span><span class="sxs-lookup"><span data-stu-id="c86e6-139">Version management</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c86e6-140">命令</span><span class="sxs-lookup"><span data-stu-id="c86e6-140">Command</span></span></th>
<th align="left"><span data-ttu-id="c86e6-141">效果</span><span class="sxs-lookup"><span data-stu-id="c86e6-141">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="c86e6-142">從生產匯入</span><span class="sxs-lookup"><span data-stu-id="c86e6-142">Import from Production</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="c86e6-143">針對選取的 GPO，將網域生產環境中的版本複製到封存。</span><span class="sxs-lookup"><span data-stu-id="c86e6-143">For the selected GPO, copy the version in the production environment of the domain to the archive.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="c86e6-144">從檔案匯入</span><span class="sxs-lookup"><span data-stu-id="c86e6-144">Import from File</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="c86e6-145">將所選、取出的 GPO 的原則設定取代成來自 GPO 備份檔案的 GPO。</span><span class="sxs-lookup"><span data-stu-id="c86e6-145">Replace the policy settings of the selected, checked-out GPO with those from a GPO backup file.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="c86e6-146">刪除</span><span class="sxs-lookup"><span data-stu-id="c86e6-146">Delete</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="c86e6-147">將選取的 GPO 移至 [回收站]，並指出是否要在生產中保留已部署版本（如果有的話），或刪除已部署的版本（除了封存中的版本之外）。</span><span class="sxs-lookup"><span data-stu-id="c86e6-147">Move the selected GPO to the Recycle Bin and indicate whether to leave the deployed version (if one exists) in production or to delete the deployed version in addition to the version in the archive.</span></span> <span data-ttu-id="c86e6-148">如果您沒有刪除 GPO 的許可權，系統會提示您提交要求。</span><span class="sxs-lookup"><span data-stu-id="c86e6-148">If you do not have permission to delete a GPO, you are prompted to submit a request.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="c86e6-149">部署</span><span class="sxs-lookup"><span data-stu-id="c86e6-149">Deploy</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="c86e6-150">將已存回封存的選取 GPO 移至網域的生產環境。</span><span class="sxs-lookup"><span data-stu-id="c86e6-150">Move the selected GPO that is checked into the archive to the production environment of the domain.</span></span> <span data-ttu-id="c86e6-151">這個動作會將它放在網路上，並覆寫先前作用中的 GPO （如果存在的話）。</span><span class="sxs-lookup"><span data-stu-id="c86e6-151">This action makes it active on the network and overwrites the previously active version of the GPO if one existed.</span></span> <span data-ttu-id="c86e6-152">如果您沒有部署 GPO 的許可權，系統會提示您提交要求。</span><span class="sxs-lookup"><span data-stu-id="c86e6-152">If you do not have permission to deploy a GPO, you will be prompted to submit a request.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="c86e6-153">匯出至</span><span class="sxs-lookup"><span data-stu-id="c86e6-153">Export to</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="c86e6-154">將選取的 GPO 儲存至備份檔案，以便將它複製到其他網域。</span><span class="sxs-lookup"><span data-stu-id="c86e6-154">Save the selected GPO to a backup file so that you can copy it to another domain.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="c86e6-155">Label</span><span class="sxs-lookup"><span data-stu-id="c86e6-155">Label</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="c86e6-156">以描述性標籤（例如 [ &quot; 已知完好] &quot; ）和 [保留記錄] 的批註標示選取的 GPO。</span><span class="sxs-lookup"><span data-stu-id="c86e6-156">Mark the selected GPO with a descriptive label (such as &quot;Known good&quot;) and comment for record keeping.</span></span> <span data-ttu-id="c86e6-157">標籤會顯示在 [ <strong> 狀態 </strong> ] 欄中，以及 [歷程 <strong> </strong> <strong> 記錄 </strong> ] 視窗的 [批註] 欄中的批註。</span><span class="sxs-lookup"><span data-stu-id="c86e6-157">Labels appear in the <strong>State</strong> column and comments in the <strong>Comment</strong> column of the <strong>History</strong> window.</span></span> <span data-ttu-id="c86e6-158">它們可協助您識別 GPO 的舊版版本，以便您可以在問題發生時回滾。</span><span class="sxs-lookup"><span data-stu-id="c86e6-158">They help you identify earlier versions of a GPO so that you can roll back if a problem occurs.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="c86e6-159">重新命名</span><span class="sxs-lookup"><span data-stu-id="c86e6-159">Rename</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="c86e6-160">變更所選 GPO 的名稱。</span><span class="sxs-lookup"><span data-stu-id="c86e6-160">Change the name of the selected GPO.</span></span> <span data-ttu-id="c86e6-161">如果 GPO 已部署，重新部署 GPO 時，系統會在網域的生產環境中更新名稱。</span><span class="sxs-lookup"><span data-stu-id="c86e6-161">If the GPO has already been deployed, the name will be updated in the production environment of the domain when the GPO is redeployed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="c86e6-162">另存為範本</span><span class="sxs-lookup"><span data-stu-id="c86e6-162">Save as Template</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="c86e6-163">根據所選 GPO 的設定建立新範本。</span><span class="sxs-lookup"><span data-stu-id="c86e6-163">Create a new template based on the settings of the selected GPO.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="c86e6-164">其他</span><span class="sxs-lookup"><span data-stu-id="c86e6-164">Miscellaneous</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c86e6-165">命令</span><span class="sxs-lookup"><span data-stu-id="c86e6-165">Command</span></span></th>
<th align="left"><span data-ttu-id="c86e6-166">效果</span><span class="sxs-lookup"><span data-stu-id="c86e6-166">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="c86e6-167">重新整理</span><span class="sxs-lookup"><span data-stu-id="c86e6-167">Refresh</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="c86e6-168">更新 [群組原則管理主控台（GPMC）] 的顯示，以納入任何變更。</span><span class="sxs-lookup"><span data-stu-id="c86e6-168">Update the display of the Group Policy Management Console (GPMC) to incorporate any changes.</span></span> <span data-ttu-id="c86e6-169">在重新整理顯示器之前，會看不到某些變更。</span><span class="sxs-lookup"><span data-stu-id="c86e6-169">Some changes are not visible until the display is refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="c86e6-170">說明</span><span class="sxs-lookup"><span data-stu-id="c86e6-170">Help</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="c86e6-171">顯示 AGPM 的說明。</span><span class="sxs-lookup"><span data-stu-id="c86e6-171">Display help for AGPM.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="c86e6-172">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="c86e6-172">Additional references</span></span>

-   [<span data-ttu-id="c86e6-173">內容索引標籤</span><span class="sxs-lookup"><span data-stu-id="c86e6-173">Contents Tab</span></span>](contents-tab-agpm40.md)

-   [<span data-ttu-id="c86e6-174">執行編輯器工作</span><span class="sxs-lookup"><span data-stu-id="c86e6-174">Performing Editor Tasks</span></span>](performing-editor-tasks-agpm40.md)

-   [<span data-ttu-id="c86e6-175">執行核准者工作</span><span class="sxs-lookup"><span data-stu-id="c86e6-175">Performing Approver Tasks</span></span>](performing-approver-tasks-agpm40.md)

-   [<span data-ttu-id="c86e6-176">執行檢閱者工作</span><span class="sxs-lookup"><span data-stu-id="c86e6-176">Performing Reviewer Tasks</span></span>](performing-reviewer-tasks-agpm40.md)

 

 





