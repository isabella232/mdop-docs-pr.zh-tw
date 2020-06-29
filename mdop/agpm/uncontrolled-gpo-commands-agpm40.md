---
title: 不受控制的 GPO 命令
description: 不受控制的 GPO 命令
author: dansimp
ms.assetid: 05a8050f-adc3-465b-8524-bbe95745165c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d8efd1c1d3005fd97b92d392140b92bae6a38681
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801738"
---
# <span data-ttu-id="c3a5e-103">不受控制的 GPO 命令</span><span class="sxs-lookup"><span data-stu-id="c3a5e-103">Uncontrolled GPO Commands</span></span>


<span data-ttu-id="c3a5e-104">[無法**控制**] 索引標籤：</span><span class="sxs-lookup"><span data-stu-id="c3a5e-104">The **Uncontrolled** tab:</span></span>

-   <span data-ttu-id="c3a5e-105">顯示由高級群組原則管理（AGPM）未管理的群組原則物件（Gpo）清單。</span><span class="sxs-lookup"><span data-stu-id="c3a5e-105">Displays a list of Group Policy Objects (GPOs) not managed by Advanced Group Policy Management (AGPM).</span></span>

-   <span data-ttu-id="c3a5e-106">提供快捷方式功能表，其中的命令會將不受管理的 Gpo 放在 AGPM 管理底下，以及顯示 Gpo 的記錄和報告。</span><span class="sxs-lookup"><span data-stu-id="c3a5e-106">Provides a shortcut menu with commands for bringing uncontrolled GPOs under the management of AGPM and for displaying the history and reports for GPOs.</span></span>

-   <span data-ttu-id="c3a5e-107">顯示有許可權存取所選 GPO 的群組和使用者清單。</span><span class="sxs-lookup"><span data-stu-id="c3a5e-107">Displays a list of the groups and users who have permission to access a selected GPO.</span></span>

<span data-ttu-id="c3a5e-108">以滑鼠右鍵按一下這個索引標籤上的 [**群組原則物件**] 清單，就會顯示快捷方式功能表，包括下列任何一項適用的選項。</span><span class="sxs-lookup"><span data-stu-id="c3a5e-108">Right-clicking the **Group Policy Objects** list on this tab displays a shortcut menu, including whichever of the following options are applicable.</span></span>

## <span data-ttu-id="c3a5e-109">控制項與歷程記錄</span><span class="sxs-lookup"><span data-stu-id="c3a5e-109">Control and history</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c3a5e-110">命令</span><span class="sxs-lookup"><span data-stu-id="c3a5e-110">Command</span></span></th>
<th align="left"><span data-ttu-id="c3a5e-111">效果</span><span class="sxs-lookup"><span data-stu-id="c3a5e-111">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="c3a5e-112">歷程記錄</span><span class="sxs-lookup"><span data-stu-id="c3a5e-112">History</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="c3a5e-113">開啟一個視窗，列出已儲存在封存中的所有已選取 GPO 版本。</span><span class="sxs-lookup"><span data-stu-id="c3a5e-113">Open a window listing all versions of the selected GPO saved within the archive.</span></span> <span data-ttu-id="c3a5e-114">您可以從 [歷程記錄] 取得 GPO 中的設定報告、比較 GPO 的兩個版本、比較 GPO 與範本，或回滾到舊版的 GPO。</span><span class="sxs-lookup"><span data-stu-id="c3a5e-114">From the history, you can obtain a report of the settings within a GPO, compare two versions of a GPO, compare a GPO to a template, or roll back to an earlier version of a GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="c3a5e-115">控制項</span><span class="sxs-lookup"><span data-stu-id="c3a5e-115">Control</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="c3a5e-116">在 AGPM 的 [變更控制管理] 底下，將所選取的非控制 GPO 移至。</span><span class="sxs-lookup"><span data-stu-id="c3a5e-116">Bring the selected uncontrolled GPO under the change control management of AGPM.</span></span> <span data-ttu-id="c3a5e-117">如果您沒有控制 GPO 的許可權，系統會提示您提交要求。</span><span class="sxs-lookup"><span data-stu-id="c3a5e-117">If you do not have permission to control a GPO, you will be prompted to submit a request.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="c3a5e-118">另存為範本</span><span class="sxs-lookup"><span data-stu-id="c3a5e-118">Save as Template</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="c3a5e-119">根據所選 GPO 的設定建立新範本。</span><span class="sxs-lookup"><span data-stu-id="c3a5e-119">Create a new template based on the settings of the selected GPO.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="c3a5e-120">報告</span><span class="sxs-lookup"><span data-stu-id="c3a5e-120">Reports</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c3a5e-121">命令</span><span class="sxs-lookup"><span data-stu-id="c3a5e-121">Command</span></span></th>
<th align="left"><span data-ttu-id="c3a5e-122">效果</span><span class="sxs-lookup"><span data-stu-id="c3a5e-122">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="c3a5e-123">設定</span><span class="sxs-lookup"><span data-stu-id="c3a5e-123">Settings</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="c3a5e-124">產生顯示所選 GPO 中設定的 HTML 式或以 XML 為基礎的報告。</span><span class="sxs-lookup"><span data-stu-id="c3a5e-124">Generate an HTML-based or XML-based report displaying the settings within the selected GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="c3a5e-125">多種</span><span class="sxs-lookup"><span data-stu-id="c3a5e-125">Differences</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="c3a5e-126">產生與兩個選取 Gpo 或所選 GPO 及範本中的設定比較的 HTML 或 XML 式報告。</span><span class="sxs-lookup"><span data-stu-id="c3a5e-126">Generate an HTML-based or XML-based report comparing the settings within two selected GPOs or within the selected GPO and a template.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="c3a5e-127">其他</span><span class="sxs-lookup"><span data-stu-id="c3a5e-127">Miscellaneous</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c3a5e-128">命令</span><span class="sxs-lookup"><span data-stu-id="c3a5e-128">Command</span></span></th>
<th align="left"><span data-ttu-id="c3a5e-129">效果</span><span class="sxs-lookup"><span data-stu-id="c3a5e-129">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="c3a5e-130">重新整理</span><span class="sxs-lookup"><span data-stu-id="c3a5e-130">Refresh</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="c3a5e-131">更新 [群組原則管理主控台（GPMC）] 的顯示，以納入任何變更。</span><span class="sxs-lookup"><span data-stu-id="c3a5e-131">Update the display of the Group Policy Management Console (GPMC) to incorporate any changes.</span></span> <span data-ttu-id="c3a5e-132">在重新整理顯示器之前，會看不到某些變更。</span><span class="sxs-lookup"><span data-stu-id="c3a5e-132">Some changes are not visible until the display is refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="c3a5e-133">說明</span><span class="sxs-lookup"><span data-stu-id="c3a5e-133">Help</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="c3a5e-134">顯示 AGPM 的說明。</span><span class="sxs-lookup"><span data-stu-id="c3a5e-134">Display help for AGPM.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="c3a5e-135">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="c3a5e-135">Additional references</span></span>

-   [<span data-ttu-id="c3a5e-136">內容索引標籤</span><span class="sxs-lookup"><span data-stu-id="c3a5e-136">Contents Tab</span></span>](contents-tab-agpm40.md)

-   [<span data-ttu-id="c3a5e-137">執行編輯器工作</span><span class="sxs-lookup"><span data-stu-id="c3a5e-137">Performing Editor Tasks</span></span>](performing-editor-tasks-agpm40.md)

-   [<span data-ttu-id="c3a5e-138">執行核准者工作</span><span class="sxs-lookup"><span data-stu-id="c3a5e-138">Performing Approver Tasks</span></span>](performing-approver-tasks-agpm40.md)

-   [<span data-ttu-id="c3a5e-139">執行檢閱者工作</span><span class="sxs-lookup"><span data-stu-id="c3a5e-139">Performing Reviewer Tasks</span></span>](performing-reviewer-tasks-agpm40.md)

 

 





