---
title: 資源回收筒命令
description: 資源回收筒命令
author: dansimp
ms.assetid: 347a101f-0ba0-4afc-bd59-752cc06bb904
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b05a5c25a59be751a062086f77daa009d7cb32f3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801858"
---
# <span data-ttu-id="49c78-103">資源回收筒命令</span><span class="sxs-lookup"><span data-stu-id="49c78-103">Recycle Bin Commands</span></span>


<span data-ttu-id="49c78-104">[**回收站**] 索引標籤：</span><span class="sxs-lookup"><span data-stu-id="49c78-104">The **Recycle Bin** tab:</span></span>

-   <span data-ttu-id="49c78-105">顯示已從封存中刪除的群組原則物件（Gpo）清單。</span><span class="sxs-lookup"><span data-stu-id="49c78-105">Displays a list of Group Policy Objects (GPOs) that have been deleted from the archive.</span></span>

-   <span data-ttu-id="49c78-106">提供快捷方式功能表，其中包含管理 Gpo 及顯示 Gpo 報告的命令。</span><span class="sxs-lookup"><span data-stu-id="49c78-106">Provides a shortcut menu with commands for managing GPOs and for displaying reports for GPOs.</span></span>

-   <span data-ttu-id="49c78-107">顯示有許可權存取所選 GPO 的群組和使用者清單。</span><span class="sxs-lookup"><span data-stu-id="49c78-107">Displays a list of the groups and users who have permission to access a selected GPO.</span></span>

<span data-ttu-id="49c78-108">以滑鼠右鍵按一下此索引標籤上的 [**群組原則物件**] 清單，即可顯示快捷方式功能表，包括下列任何一項適用的選項：</span><span class="sxs-lookup"><span data-stu-id="49c78-108">Right-clicking the **Group Policy Objects** list on this tab displays a shortcut menu, including whichever of the following options are applicable:</span></span>

## <span data-ttu-id="49c78-109">報告</span><span class="sxs-lookup"><span data-stu-id="49c78-109">Reports</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="49c78-110">命令</span><span class="sxs-lookup"><span data-stu-id="49c78-110">Command</span></span></th>
<th align="left"><span data-ttu-id="49c78-111">效果</span><span class="sxs-lookup"><span data-stu-id="49c78-111">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="49c78-112">設定</span><span class="sxs-lookup"><span data-stu-id="49c78-112">Settings</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="49c78-113">產生顯示所選 GPO 中設定的 HTML 或 XML 報告，或顯示從組織單位到 Gpo 最近控制、匯入或取出時的選取 Gpo 連結。</span><span class="sxs-lookup"><span data-stu-id="49c78-113">Generate an HTML-based or XML-based report displaying the settings within the selected GPO or display links to the selected GPOs from organizational units as of when the GPOs were most recently controlled, imported, or checked in.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="49c78-114">多種</span><span class="sxs-lookup"><span data-stu-id="49c78-114">Differences</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="49c78-115">產生與兩個選取 Gpo 或所選 GPO 及範本中的設定比較的 HTML 或 XML 式報告。</span><span class="sxs-lookup"><span data-stu-id="49c78-115">Generate an HTML-based or XML-based report comparing the settings within two selected GPOs or within the selected GPO and a template.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="49c78-116">版本管理</span><span class="sxs-lookup"><span data-stu-id="49c78-116">Version management</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="49c78-117">命令</span><span class="sxs-lookup"><span data-stu-id="49c78-117">Command</span></span></th>
<th align="left"><span data-ttu-id="49c78-118">效果</span><span class="sxs-lookup"><span data-stu-id="49c78-118">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="49c78-119">予以</span><span class="sxs-lookup"><span data-stu-id="49c78-119">Destroy</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="49c78-120">從 [回收站] 移除選取的 GPO <strong> </strong> ，使其無法再還原。</span><span class="sxs-lookup"><span data-stu-id="49c78-120">Remove the selected GPO from the <strong>Recycle Bin</strong>, so it can no longer be restored.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="49c78-121">還原</span><span class="sxs-lookup"><span data-stu-id="49c78-121">Restore</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="49c78-122">將選取的 GPO 從 [ <strong> 回收站 </strong> ] 移至 [ <strong> 受控 </strong> ] 索引標籤。這不會將 GPO 還原到生產環境。</span><span class="sxs-lookup"><span data-stu-id="49c78-122">Move the selected GPO from the <strong>Recycle Bin</strong> to the <strong>Controlled</strong> tab. This does not restore the GPO to the production environment.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="49c78-123">其他</span><span class="sxs-lookup"><span data-stu-id="49c78-123">Miscellaneous</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="49c78-124">命令</span><span class="sxs-lookup"><span data-stu-id="49c78-124">Command</span></span></th>
<th align="left"><span data-ttu-id="49c78-125">效果</span><span class="sxs-lookup"><span data-stu-id="49c78-125">Effect</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="49c78-126">重新整理</span><span class="sxs-lookup"><span data-stu-id="49c78-126">Refresh</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="49c78-127">更新 [群組原則管理主控台（GPMC）] 的顯示，以納入任何變更。</span><span class="sxs-lookup"><span data-stu-id="49c78-127">Update the display of the Group Policy Management Console (GPMC) to incorporate any changes.</span></span> <span data-ttu-id="49c78-128">在重新整理顯示器之前，會看不到某些變更。</span><span class="sxs-lookup"><span data-stu-id="49c78-128">Some changes are not visible until the display is refreshed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="49c78-129">說明</span><span class="sxs-lookup"><span data-stu-id="49c78-129">Help</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="49c78-130">顯示 [高級群組原則管理（AGPM）] 的說明。</span><span class="sxs-lookup"><span data-stu-id="49c78-130">Display help for Advanced Group Policy Management (AGPM).</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="49c78-131">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="49c78-131">Additional references</span></span>

-   [<span data-ttu-id="49c78-132">內容索引標籤</span><span class="sxs-lookup"><span data-stu-id="49c78-132">Contents Tab</span></span>](contents-tab-agpm40.md)

-   [<span data-ttu-id="49c78-133">執行核准者工作</span><span class="sxs-lookup"><span data-stu-id="49c78-133">Performing Approver Tasks</span></span>](performing-approver-tasks-agpm40.md)

-   [<span data-ttu-id="49c78-134">執行檢閱者工作</span><span class="sxs-lookup"><span data-stu-id="49c78-134">Performing Reviewer Tasks</span></span>](performing-reviewer-tasks-agpm40.md)

 

 





