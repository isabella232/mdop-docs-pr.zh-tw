---
title: 受控制的 GPO 命令
description: 受控制的 GPO 命令
author: dansimp
ms.assetid: 82db4772-154a-4a8d-99cd-2c69e1738698
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8e537751107a2796727e5ed71511649b6bce953a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801993"
---
# <span data-ttu-id="ae5b9-103">受控制的 GPO 命令</span><span class="sxs-lookup"><span data-stu-id="ae5b9-103">Controlled GPO Commands</span></span>


<span data-ttu-id="ae5b9-104">[**受控**] 索引標籤：</span><span class="sxs-lookup"><span data-stu-id="ae5b9-104">The **Controlled** tab:</span></span>

-   <span data-ttu-id="ae5b9-105">顯示由 [高級群組原則管理（AGPM）] 管理的群組原則物件（Gpo）清單。</span><span class="sxs-lookup"><span data-stu-id="ae5b9-105">Displays a list of Group Policy Objects (GPOs) managed by Advanced Group Policy Management (AGPM).</span></span>

-   <span data-ttu-id="ae5b9-106">提供快捷方式功能表，其中包含管理 Gpo 及顯示 Gpo 的記錄和報告的命令。</span><span class="sxs-lookup"><span data-stu-id="ae5b9-106">Provides a shortcut menu with commands for managing GPOs and for displaying the history and reports for GPOs.</span></span>

-   <span data-ttu-id="ae5b9-107">顯示有許可權存取所選 GPO 的群組和使用者清單。</span><span class="sxs-lookup"><span data-stu-id="ae5b9-107">Displays a list of the groups and users who have permission to access a selected GPO.</span></span>

<span data-ttu-id="ae5b9-108">以滑鼠右鍵按一下這個索引標籤上的 [**群組原則物件**] 清單，就會顯示快捷方式功能表，包括下列任何一項適用的選項。</span><span class="sxs-lookup"><span data-stu-id="ae5b9-108">Right-clicking the **Group Policy Objects** list on this tab displays a shortcut menu, including whichever of the following options are applicable.</span></span>

## <span data-ttu-id="ae5b9-109">控制項與歷程記錄</span><span class="sxs-lookup"><span data-stu-id="ae5b9-109">Control and history</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ae5b9-110">命令</span><span class="sxs-lookup"><span data-stu-id="ae5b9-110">Command</span></span></th>
<th align="left"><span data-ttu-id="ae5b9-111">效果</span><span class="sxs-lookup"><span data-stu-id="ae5b9-111">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="ae5b9-112">新的受控 GPO</span><span class="sxs-lookup"><span data-stu-id="ae5b9-112">New Controlled GPO</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="ae5b9-113">透過 AGPM 管理變更控制來建立新的 GPO，然後將它部署到生產環境。</span><span class="sxs-lookup"><span data-stu-id="ae5b9-113">Create a new GPO with change control managed through AGPM and deploy it to the production environment.</span></span> <span data-ttu-id="ae5b9-114">如果您沒有建立 GPO 的許可權，系統會提示您提交要求。</span><span class="sxs-lookup"><span data-stu-id="ae5b9-114">If you do not have permission to create a GPO, you will be prompted to submit a request.</span></span> <span data-ttu-id="ae5b9-115">（如果按一下滑鼠右鍵， <strong> 則會顯示此選項（如果沒有選取 GPO 的話）[群組原則物件] </strong> 清單。）</span><span class="sxs-lookup"><span data-stu-id="ae5b9-115">(This option is displayed if no GPO is selected when right-clicking in the <strong>Group Policy Objects</strong> list.)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="ae5b9-116">歷程記錄</span><span class="sxs-lookup"><span data-stu-id="ae5b9-116">History</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="ae5b9-117">開啟一個視窗，列出已儲存在封存中的所有已選取 GPO 版本。</span><span class="sxs-lookup"><span data-stu-id="ae5b9-117">Open a window listing all versions of the selected GPO saved within the archive.</span></span> <span data-ttu-id="ae5b9-118">您可以從 [歷程記錄] 取得 GPO 中的設定報告、比較 GPO 的兩個版本、比較 GPO 與範本，或回滾到舊版的 GPO。</span><span class="sxs-lookup"><span data-stu-id="ae5b9-118">From the history, you can obtain a report of the settings within a GPO, compare two versions of a GPO, compare a GPO to a template, or roll back to a previous version of a GPO.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="ae5b9-119">報告</span><span class="sxs-lookup"><span data-stu-id="ae5b9-119">Reports</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ae5b9-120">命令</span><span class="sxs-lookup"><span data-stu-id="ae5b9-120">Command</span></span></th>
<th align="left"><span data-ttu-id="ae5b9-121">效果</span><span class="sxs-lookup"><span data-stu-id="ae5b9-121">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="ae5b9-122">設定</span><span class="sxs-lookup"><span data-stu-id="ae5b9-122">Settings</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="ae5b9-123">產生顯示所選 GPO 中設定的 HTML 或 XML 報告，或從組織單位顯示所選 GPO 的連結（如果 GPO 是最近控制、匯入或檢入）。</span><span class="sxs-lookup"><span data-stu-id="ae5b9-123">Generate an HTML-based or XML-based report displaying the settings within the selected GPO or display links to the selected GPO(s) from organizational units as of when the GPO(s) was most recently controlled, imported, or checked in.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="ae5b9-124">多種</span><span class="sxs-lookup"><span data-stu-id="ae5b9-124">Differences</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="ae5b9-125">產生與兩個選取 Gpo 或所選 GPO 及範本中的設定比較的 HTML 或 XML 式報告。</span><span class="sxs-lookup"><span data-stu-id="ae5b9-125">Generate an HTML-based or XML-based report comparing the settings within two selected GPOs or within the selected GPO and a template.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="ae5b9-126">編輯</span><span class="sxs-lookup"><span data-stu-id="ae5b9-126">Editing</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ae5b9-127">命令</span><span class="sxs-lookup"><span data-stu-id="ae5b9-127">Command</span></span></th>
<th align="left"><span data-ttu-id="ae5b9-128">效果</span><span class="sxs-lookup"><span data-stu-id="ae5b9-128">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="ae5b9-129">編輯</span><span class="sxs-lookup"><span data-stu-id="ae5b9-129">Edit</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="ae5b9-130">開啟 [ <strong> 群組原則管理編輯器 </strong> ] 視窗，變更選取的 GPO。</span><span class="sxs-lookup"><span data-stu-id="ae5b9-130">Open the <strong>Group Policy Management Editor</strong> window to make changes to the selected GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="ae5b9-131">退房</span><span class="sxs-lookup"><span data-stu-id="ae5b9-131">Check Out</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="ae5b9-132">從封存中取得選取的 GPO 的複本以進行離線編輯，並禁止任何人編輯它，直到將它檢入回封存為止。</span><span class="sxs-lookup"><span data-stu-id="ae5b9-132">Obtain a copy of the selected GPO from the archive for offline editing and prohibit anyone else from editing it until it is checked back into the archive.</span></span> <span data-ttu-id="ae5b9-133">（您可以透過 AGPM 管理員（完全控制）來覆寫 [取出]。）</span><span class="sxs-lookup"><span data-stu-id="ae5b9-133">(Check Out can be overridden by an AGPM Administrator (Full Control).)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="ae5b9-134">登記</span><span class="sxs-lookup"><span data-stu-id="ae5b9-134">Check In</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="ae5b9-135">將所選 GPO 的已編輯版本檢查到封存中，讓其他授權的編輯者可以進行變更，或讓核准者將它部署到生產環境。</span><span class="sxs-lookup"><span data-stu-id="ae5b9-135">Check the edited version of the selected GPO into the archive, so other authorized Editors can make changes or an Approver can deploy it to the production environment.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="ae5b9-136">復原取出</span><span class="sxs-lookup"><span data-stu-id="ae5b9-136">Undo Check Out</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="ae5b9-137">將已取出的 GPO 傳回封存，且不做任何變更。</span><span class="sxs-lookup"><span data-stu-id="ae5b9-137">Return a checked out GPO to the archive without any changes.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="ae5b9-138">版本管理</span><span class="sxs-lookup"><span data-stu-id="ae5b9-138">Version management</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ae5b9-139">命令</span><span class="sxs-lookup"><span data-stu-id="ae5b9-139">Command</span></span></th>
<th align="left"><span data-ttu-id="ae5b9-140">效果</span><span class="sxs-lookup"><span data-stu-id="ae5b9-140">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="ae5b9-141">從生產匯入</span><span class="sxs-lookup"><span data-stu-id="ae5b9-141">Import from Production</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="ae5b9-142">針對選取的 GPO，將生產環境中的版本複製到封存。</span><span class="sxs-lookup"><span data-stu-id="ae5b9-142">For the selected GPO, copy the version in the production environment to the archive.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="ae5b9-143">刪除</span><span class="sxs-lookup"><span data-stu-id="ae5b9-143">Delete</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="ae5b9-144">將選取的 GPO 移至 [回收站]，並指出是否要在生產中保留已部署的版本（如果有的話），或是將它刪除，以及封存中的版本。</span><span class="sxs-lookup"><span data-stu-id="ae5b9-144">Move the selected GPO to the Recycle Bin and indicate whether to leave the deployed version (if one exists) in production or to delete it as well as the version in the archive.</span></span> <span data-ttu-id="ae5b9-145">如果您沒有刪除 GPO 的許可權，系統會提示您提交要求。</span><span class="sxs-lookup"><span data-stu-id="ae5b9-145">If you do not have permission to delete a GPO, you will be prompted to submit a request.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="ae5b9-146">部署</span><span class="sxs-lookup"><span data-stu-id="ae5b9-146">Deploy</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="ae5b9-147">將已存回封存的選取 GPO 移至生產環境。</span><span class="sxs-lookup"><span data-stu-id="ae5b9-147">Move the selected GPO that is checked into the archive to the production environment.</span></span> <span data-ttu-id="ae5b9-148">這個動作會將它放在網路上，並覆寫先前作用中的 GPO （如果存在的話）。</span><span class="sxs-lookup"><span data-stu-id="ae5b9-148">This action makes it active on the network and overwrites the previously active version of the GPO if one existed.</span></span> <span data-ttu-id="ae5b9-149">如果您沒有部署 GPO 的許可權，系統會提示您提交要求。</span><span class="sxs-lookup"><span data-stu-id="ae5b9-149">If you do not have permission to deploy a GPO, you will be prompted to submit a request.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="ae5b9-150">Label</span><span class="sxs-lookup"><span data-stu-id="ae5b9-150">Label</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="ae5b9-151">以描述性標籤（例如 [ &quot; 已知完好] &quot; ）和 [保留記錄] 的批註標示選取的 GPO。</span><span class="sxs-lookup"><span data-stu-id="ae5b9-151">Mark the selected GPO with a descriptive label (such as &quot;Known good&quot;) and comment for record keeping.</span></span> <span data-ttu-id="ae5b9-152">標籤會顯示在 [ <strong> </strong> 記錄] 視窗 [批註] 欄中的 [省/市/自治區] 欄和 [批註 <strong> ] 中 </strong> <strong> </strong> ，讓您可以輕鬆識別以特定標籤識別的舊版 GPO，以便在問題發生時回滾。</span><span class="sxs-lookup"><span data-stu-id="ae5b9-152">Labels appear in the <strong>State</strong> column and comments in the <strong>Comment</strong> column of the <strong>History</strong> window, enabling you to easily identify previous versions of a GPO identified with a particular label, so you can roll back if a problem occurs.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="ae5b9-153">重新命名</span><span class="sxs-lookup"><span data-stu-id="ae5b9-153">Rename</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="ae5b9-154">變更所選 GPO 的名稱。</span><span class="sxs-lookup"><span data-stu-id="ae5b9-154">Change the name of the selected GPO.</span></span> <span data-ttu-id="ae5b9-155">如果 GPO 已部署，重新部署 GPO 時，系統會在生產環境中更新名稱。</span><span class="sxs-lookup"><span data-stu-id="ae5b9-155">If the GPO has already been deployed, the name will be updated in the production environment when the GPO is redeployed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="ae5b9-156">另存為範本</span><span class="sxs-lookup"><span data-stu-id="ae5b9-156">Save as Template</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="ae5b9-157">根據所選 GPO 的設定建立新範本。</span><span class="sxs-lookup"><span data-stu-id="ae5b9-157">Create a new template based on the settings of the selected GPO.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="ae5b9-158">其他</span><span class="sxs-lookup"><span data-stu-id="ae5b9-158">Miscellaneous</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ae5b9-159">命令</span><span class="sxs-lookup"><span data-stu-id="ae5b9-159">Command</span></span></th>
<th align="left"><span data-ttu-id="ae5b9-160">效果</span><span class="sxs-lookup"><span data-stu-id="ae5b9-160">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="ae5b9-161">重新整理</span><span class="sxs-lookup"><span data-stu-id="ae5b9-161">Refresh</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="ae5b9-162">更新 [群組原則管理主控台（GPMC）] 的顯示，以納入任何變更。</span><span class="sxs-lookup"><span data-stu-id="ae5b9-162">Update the display of the Group Policy Management Console (GPMC) to incorporate any changes.</span></span> <span data-ttu-id="ae5b9-163">在重新整理顯示器之前，會看不到某些變更。</span><span class="sxs-lookup"><span data-stu-id="ae5b9-163">Some changes are not visible until the display is refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="ae5b9-164">說明</span><span class="sxs-lookup"><span data-stu-id="ae5b9-164">Help</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="ae5b9-165">顯示 AGPM 的說明。</span><span class="sxs-lookup"><span data-stu-id="ae5b9-165">Display help for AGPM.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="ae5b9-166">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="ae5b9-166">Additional references</span></span>

-   [<span data-ttu-id="ae5b9-167">內容索引標籤</span><span class="sxs-lookup"><span data-stu-id="ae5b9-167">Contents Tab</span></span>](contents-tab-agpm30ops.md)

-   [<span data-ttu-id="ae5b9-168">執行編輯器工作</span><span class="sxs-lookup"><span data-stu-id="ae5b9-168">Performing Editor Tasks</span></span>](performing-editor-tasks-agpm30ops.md)

-   [<span data-ttu-id="ae5b9-169">執行核准者工作</span><span class="sxs-lookup"><span data-stu-id="ae5b9-169">Performing Approver Tasks</span></span>](performing-approver-tasks-agpm30ops.md)

-   [<span data-ttu-id="ae5b9-170">執行檢閱者工作</span><span class="sxs-lookup"><span data-stu-id="ae5b9-170">Performing Reviewer Tasks</span></span>](performing-reviewer-tasks-agpm30ops.md)

 

 





