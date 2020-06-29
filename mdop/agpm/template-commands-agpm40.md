---
title: 範本命令
description: 範本命令
author: dansimp
ms.assetid: 243a9b18-bf3f-44fa-94d7-5c793f7322da
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2c540bf87462f501a4db5596faca43ef66ee8558
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801757"
---
# <span data-ttu-id="774ef-103">範本命令</span><span class="sxs-lookup"><span data-stu-id="774ef-103">Template Commands</span></span>


<span data-ttu-id="774ef-104">[**範本**] 索引標籤：</span><span class="sxs-lookup"><span data-stu-id="774ef-104">The **Templates** tab:</span></span>

-   <span data-ttu-id="774ef-105">顯示可用範本的清單，您可以用來建立新的群組原則物件（Gpo）。</span><span class="sxs-lookup"><span data-stu-id="774ef-105">Displays a list of available templates that you can use to create new Group Policy Objects (GPOs).</span></span>

-   <span data-ttu-id="774ef-106">提供快捷方式功能表，其中的命令可根據選取的範本建立 GPO、管理範本，以及顯示範本的報表。</span><span class="sxs-lookup"><span data-stu-id="774ef-106">Provides a shortcut menu with commands for creating a GPO based on a selected template, managing templates, and displaying reports for templates.</span></span>

-   <span data-ttu-id="774ef-107">顯示有許可權存取選取範本的群組和使用者清單。</span><span class="sxs-lookup"><span data-stu-id="774ef-107">Displays a list of the groups and users who have permission to access a selected template.</span></span>

<span data-ttu-id="774ef-108">因為範本不能變更，所以範本沒有歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="774ef-108">Because a template cannot be altered, templates have no history.</span></span> <span data-ttu-id="774ef-109">不過，與任何 GPO 版本一樣，範本的設定可以與 [設定] 報表一起顯示，或與另一個具有差異報告的 GPO 進行比較。</span><span class="sxs-lookup"><span data-stu-id="774ef-109">However, like any GPO version, the settings of a template can be displayed with a settings report or compared to another GPO with a difference report.</span></span>

<span data-ttu-id="774ef-110">**記事** 範本是一個無法編輯且靜態的 GPO 版本，以做為建立新的可編輯 Gpo 的起點。</span><span class="sxs-lookup"><span data-stu-id="774ef-110">**Note** A template is an uneditable, static version of a GPO for use as a starting point for creating new, editable GPOs.</span></span>

 

<span data-ttu-id="774ef-111">以滑鼠右鍵按一下這個索引標籤上的 [**群組原則物件**] 清單，就會顯示快捷方式功能表，包括下列任何一項適用的選項。</span><span class="sxs-lookup"><span data-stu-id="774ef-111">Right-clicking the **Group Policy Objects** list on this tab displays a shortcut menu, including whichever of the following options are applicable.</span></span>

## <span data-ttu-id="774ef-112">控制項</span><span class="sxs-lookup"><span data-stu-id="774ef-112">Control</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="774ef-113">命令</span><span class="sxs-lookup"><span data-stu-id="774ef-113">Command</span></span></th>
<th align="left"><span data-ttu-id="774ef-114">效果</span><span class="sxs-lookup"><span data-stu-id="774ef-114">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="774ef-115">新的受控 GPO</span><span class="sxs-lookup"><span data-stu-id="774ef-115">New Controlled GPO</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="774ef-116">根據選取的範本建立新的 GPO。</span><span class="sxs-lookup"><span data-stu-id="774ef-116">Create a new GPO based on the selected template.</span></span> <span data-ttu-id="774ef-117">提供將新 GPO 部署到網域的生產環境的選項。</span><span class="sxs-lookup"><span data-stu-id="774ef-117">The option to deploy the new GPO to the production environment of the domain is provided.</span></span> <span data-ttu-id="774ef-118">如果您沒有建立 GPO 的許可權，系統會提示您提交要求。</span><span class="sxs-lookup"><span data-stu-id="774ef-118">If you do not have permission to create a GPO, you will be prompted to submit a request.</span></span> <span data-ttu-id="774ef-119">（如果按一下滑鼠右鍵， <strong> 則會顯示此選項（如果沒有選取 GPO 的話）[群組原則物件] </strong> 清單。）</span><span class="sxs-lookup"><span data-stu-id="774ef-119">(This option is displayed if no GPO is selected when right-clicking in the <strong>Group Policy Objects</strong> list.)</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="774ef-120">報告</span><span class="sxs-lookup"><span data-stu-id="774ef-120">Reports</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="774ef-121">命令</span><span class="sxs-lookup"><span data-stu-id="774ef-121">Command</span></span></th>
<th align="left"><span data-ttu-id="774ef-122">效果</span><span class="sxs-lookup"><span data-stu-id="774ef-122">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="774ef-123">設定</span><span class="sxs-lookup"><span data-stu-id="774ef-123">Settings</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="774ef-124">產生顯示所選 GPO 中設定的 HTML 式或以 XML 為基礎的報告。</span><span class="sxs-lookup"><span data-stu-id="774ef-124">Generate an HTML-based or XML-based report displaying the settings within the selected GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="774ef-125">多種</span><span class="sxs-lookup"><span data-stu-id="774ef-125">Differences</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="774ef-126">產生與兩個選取的 GPO 範本中的設定比較的 HTML 或以 XML 為基礎的報表。</span><span class="sxs-lookup"><span data-stu-id="774ef-126">Generate an HTML-based or XML-based report comparing the settings within two selected GPO templates.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="774ef-127">範本管理</span><span class="sxs-lookup"><span data-stu-id="774ef-127">Template management</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="774ef-128">命令</span><span class="sxs-lookup"><span data-stu-id="774ef-128">Command</span></span></th>
<th align="left"><span data-ttu-id="774ef-129">效果</span><span class="sxs-lookup"><span data-stu-id="774ef-129">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="774ef-130">設為預設值</span><span class="sxs-lookup"><span data-stu-id="774ef-130">Set as Default</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="774ef-131">將選取的範本設定為預設值，以便在建立新的 GPO 時自動使用。</span><span class="sxs-lookup"><span data-stu-id="774ef-131">Set the selected template as the default to be used automatically when creating a new GPO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="774ef-132">刪除</span><span class="sxs-lookup"><span data-stu-id="774ef-132">Delete</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="774ef-133">將選取的範本移至 [ <strong> 回收站] </strong> 。</span><span class="sxs-lookup"><span data-stu-id="774ef-133">Move the selected template to the <strong>Recycle Bin</strong>.</span></span> <span data-ttu-id="774ef-134">如果您沒有刪除 GPO 的許可權，系統會提示您提交要求。</span><span class="sxs-lookup"><span data-stu-id="774ef-134">If you do not have permission to delete a GPO, you will be prompted to submit a request.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="774ef-135">重新命名</span><span class="sxs-lookup"><span data-stu-id="774ef-135">Rename</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="774ef-136">變更所選範本的名稱。</span><span class="sxs-lookup"><span data-stu-id="774ef-136">Change the name of the selected template.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="774ef-137">其他</span><span class="sxs-lookup"><span data-stu-id="774ef-137">Miscellaneous</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="774ef-138">命令</span><span class="sxs-lookup"><span data-stu-id="774ef-138">Command</span></span></th>
<th align="left"><span data-ttu-id="774ef-139">效果</span><span class="sxs-lookup"><span data-stu-id="774ef-139">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="774ef-140">重新整理</span><span class="sxs-lookup"><span data-stu-id="774ef-140">Refresh</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="774ef-141">更新群組原則管理主控台的顯示，以納入任何變更。</span><span class="sxs-lookup"><span data-stu-id="774ef-141">Update the display of the Group Policy Management Console to incorporate any changes.</span></span> <span data-ttu-id="774ef-142">在重新整理顯示器之前，會看不到某些變更。</span><span class="sxs-lookup"><span data-stu-id="774ef-142">Some changes are not visible until the display is refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="774ef-143">說明</span><span class="sxs-lookup"><span data-stu-id="774ef-143">Help</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="774ef-144">顯示 [高級群組原則管理（AGPM）] 的說明。</span><span class="sxs-lookup"><span data-stu-id="774ef-144">Display help for Advanced Group Policy Management (AGPM).</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="774ef-145">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="774ef-145">Additional references</span></span>

-   [<span data-ttu-id="774ef-146">內容索引標籤</span><span class="sxs-lookup"><span data-stu-id="774ef-146">Contents Tab</span></span>](contents-tab-agpm40.md)

-   [<span data-ttu-id="774ef-147">執行編輯器工作</span><span class="sxs-lookup"><span data-stu-id="774ef-147">Performing Editor Tasks</span></span>](performing-editor-tasks-agpm40.md)

-   [<span data-ttu-id="774ef-148">執行檢閱者工作</span><span class="sxs-lookup"><span data-stu-id="774ef-148">Performing Reviewer Tasks</span></span>](performing-reviewer-tasks-agpm40.md)

 

 





