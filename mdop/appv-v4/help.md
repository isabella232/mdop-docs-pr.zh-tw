---
title: HELP
description: HELP
author: dansimp
ms.assetid: 0ddb5f18-0c0a-45ea-b7c7-2d4749e3d35d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 395e6199529ccbe708aa7d1ac6673ea6f9494ae4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808769"
---
# <span data-ttu-id="cb147-103">HELP</span><span class="sxs-lookup"><span data-stu-id="cb147-103">HELP</span></span>


<span data-ttu-id="cb147-104">顯示可在應用程式虛擬化（App-v）中使用的各種 SFTMIME 命令的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="cb147-104">Displays information about the various SFTMIME commands that can be used in Application Virtualization (App-V).</span></span>

## <span data-ttu-id="cb147-105">HELP</span><span class="sxs-lookup"><span data-stu-id="cb147-105">HELP</span></span>


`SFTMIME [/? | /HELP [VERB:<verb>]]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="cb147-106">參數</span><span class="sxs-lookup"><span data-stu-id="cb147-106">Parameter</span></span></th>
<th align="left"><span data-ttu-id="cb147-107">描述</span><span class="sxs-lookup"><span data-stu-id="cb147-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cb147-108">/？、/HELP</span><span class="sxs-lookup"><span data-stu-id="cb147-108">/?, /HELP</span></span></p></td>
<td align="left"><p><span data-ttu-id="cb147-109">顯示使用量資訊。</span><span class="sxs-lookup"><span data-stu-id="cb147-109">Displays usage information.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="cb147-110">動作</span><span class="sxs-lookup"><span data-stu-id="cb147-110">verb</span></span></p></td>
<td align="left"><p><span data-ttu-id="cb147-111">要執行的命令，例如 [新增]、[重新整理]、[說明] 或 [移除]。</span><span class="sxs-lookup"><span data-stu-id="cb147-111">The command to run, such as ADD, REFRESH, HELP or REMOVE.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cb147-112">物件</span><span class="sxs-lookup"><span data-stu-id="cb147-112">object</span></span></p></td>
<td align="left"><p><span data-ttu-id="cb147-113">套用命令的用途，例如 APP： &quot; 預設應用程式。&quot;</span><span class="sxs-lookup"><span data-stu-id="cb147-113">What the command applies to, such as APP:&quot;Default Application.&quot;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="cb147-114">參數</span><span class="sxs-lookup"><span data-stu-id="cb147-114">parameters</span></span></p></td>
<td align="left"><p><span data-ttu-id="cb147-115">指定動詞和物件的選用參數。</span><span class="sxs-lookup"><span data-stu-id="cb147-115">Optional parameters for the specified verb and object.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cb147-116">/LOG</span><span class="sxs-lookup"><span data-stu-id="cb147-116">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="cb147-117">將輸出記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="cb147-117">Log output to the specified path name.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="cb147-118">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="cb147-118">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="cb147-119">在 active 主控台視窗中顯示輸出（預設）。</span><span class="sxs-lookup"><span data-stu-id="cb147-119">Displays output in the active console window (default).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cb147-120">/GUI</span><span class="sxs-lookup"><span data-stu-id="cb147-120">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="cb147-121">顯示對話方塊中的錯誤（不正確查詢）。</span><span class="sxs-lookup"><span data-stu-id="cb147-121">Displays errors in a dialog box (not valid for queries).</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="cb147-122">針對版本4.6，新增了下列選項。</span><span class="sxs-lookup"><span data-stu-id="cb147-122">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cb147-123">/LOGU</span><span class="sxs-lookup"><span data-stu-id="cb147-123">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="cb147-124">如果已指定，輸出會以 UNICODE 格式記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="cb147-124">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="cb147-125">支援下表所述的動詞。</span><span class="sxs-lookup"><span data-stu-id="cb147-125">The verbs described in the following table are supported.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cb147-126">ADD</span><span class="sxs-lookup"><span data-stu-id="cb147-126">ADD</span></span></p></td>
<td align="left"><p><span data-ttu-id="cb147-127">將新的應用程式、套件、檔案類型關聯或發佈伺服器新增至 App-v 用戶端。</span><span class="sxs-lookup"><span data-stu-id="cb147-127">Adds a new application, package, file type association, or publishing server to the App-V Client.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="cb147-128">設定</span><span class="sxs-lookup"><span data-stu-id="cb147-128">CONFIGURE</span></span></p></td>
<td align="left"><p><span data-ttu-id="cb147-129">變更應用程式、套件、檔案類型關聯或發佈伺服器的設定。</span><span class="sxs-lookup"><span data-stu-id="cb147-129">Changes the configuration of an application, a package, a file type association, or a publishing server.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cb147-130">DELETE</span><span class="sxs-lookup"><span data-stu-id="cb147-130">DELETE</span></span></p></td>
<td align="left"><p><span data-ttu-id="cb147-131">移除應用程式、套件、檔案類型關聯或伺服器。</span><span class="sxs-lookup"><span data-stu-id="cb147-131">Removes applications, packages, file type associations, or servers.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="cb147-132">裝載</span><span class="sxs-lookup"><span data-stu-id="cb147-132">LOAD</span></span></p></td>
<td align="left"><p><span data-ttu-id="cb147-133">將套件載入到檔案系統快取中。</span><span class="sxs-lookup"><span data-stu-id="cb147-133">Loads a package into the file system cache.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cb147-134">維修中心</span><span class="sxs-lookup"><span data-stu-id="cb147-134">REPAIR</span></span></p></td>
<td align="left"><p><span data-ttu-id="cb147-135">重設您的應用程式個人設定。</span><span class="sxs-lookup"><span data-stu-id="cb147-135">Resets your personal settings for an application.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="cb147-136">REFRESH</span><span class="sxs-lookup"><span data-stu-id="cb147-136">REFRESH</span></span></p></td>
<td align="left"><p><span data-ttu-id="cb147-137">觸發發佈伺服器更新。</span><span class="sxs-lookup"><span data-stu-id="cb147-137">Triggers a publishing server refresh.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cb147-138">出版</span><span class="sxs-lookup"><span data-stu-id="cb147-138">PUBLISH</span></span></p></td>
<td align="left"><p><span data-ttu-id="cb147-139">將應用程式快捷方式發佈至使用者的 [開始] 功能表、[桌面] 或其他指定位置，或可用於發佈整個套件的內容。</span><span class="sxs-lookup"><span data-stu-id="cb147-139">Publishes an application shortcut to the user's Start menu, desktop, or other specified location, or can be used to publish the contents of an entire package.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="cb147-140">解除發佈</span><span class="sxs-lookup"><span data-stu-id="cb147-140">UNPUBLISH</span></span></p></td>
<td align="left"><p><span data-ttu-id="cb147-141">移除整個套件的快速鍵和檔案類型。</span><span class="sxs-lookup"><span data-stu-id="cb147-141">Removes the shortcuts and file types for an entire package.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cb147-142">QUERY</span><span class="sxs-lookup"><span data-stu-id="cb147-142">QUERY</span></span></p></td>
<td align="left"><p><span data-ttu-id="cb147-143">取得目前的應用程式、套件、檔案類型關聯或發佈伺服器清單。</span><span class="sxs-lookup"><span data-stu-id="cb147-143">Gets a current list of applications, packages, file type associations, or publishing servers.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="cb147-144">清除</span><span class="sxs-lookup"><span data-stu-id="cb147-144">CLEAR</span></span></p></td>
<td align="left"><p><span data-ttu-id="cb147-145">移除一或多個應用程式的個人設定和桌面配置。</span><span class="sxs-lookup"><span data-stu-id="cb147-145">Removes your personal settings and desktop configurations for one or more applications.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cb147-146">卸載</span><span class="sxs-lookup"><span data-stu-id="cb147-146">UNLOAD</span></span></p></td>
<td align="left"><p><span data-ttu-id="cb147-147">從檔案系統快取中卸載套件。</span><span class="sxs-lookup"><span data-stu-id="cb147-147">Unloads a package from the file system cache.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="cb147-148">狀</span><span class="sxs-lookup"><span data-stu-id="cb147-148">LOCK</span></span></p></td>
<td align="left"><p><span data-ttu-id="cb147-149">鎖定檔案系統快取中指定的應用程式。</span><span class="sxs-lookup"><span data-stu-id="cb147-149">Locks the application specified in the file system cache.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cb147-150">鎖</span><span class="sxs-lookup"><span data-stu-id="cb147-150">UNLOCK</span></span></p></td>
<td align="left"><p><span data-ttu-id="cb147-151">解除鎖定檔案系統快取中指定的應用程式。</span><span class="sxs-lookup"><span data-stu-id="cb147-151">Unlocks the application specified in the file system cache.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="cb147-152">如需上述動作的詳細資訊，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="cb147-152">For more information about the preceding actions, use the following command:</span></span>

`SFTMIME /HELP VERB:verb`

<span data-ttu-id="cb147-153">例如，下列命令會顯示 ADD 動詞的資訊：</span><span class="sxs-lookup"><span data-stu-id="cb147-153">For example, the following command will display information for the ADD verb:</span></span>

`SFTMIME /HELP VERB:ADD`

## <span data-ttu-id="cb147-154">相關主題</span><span class="sxs-lookup"><span data-stu-id="cb147-154">Related topics</span></span>


[<span data-ttu-id="cb147-155">SFTMIME 命令參考</span><span class="sxs-lookup"><span data-stu-id="cb147-155">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





