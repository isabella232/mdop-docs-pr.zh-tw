---
title: ADD TYPE
description: ADD TYPE
author: dansimp
ms.assetid: 8f1d3978-9977-4851-9f46-fee6aefa3535
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4d2dcfb24a32dc733aa91b5534e0011090ef12b9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809321"
---
# <span data-ttu-id="fc12c-103">ADD TYPE</span><span class="sxs-lookup"><span data-stu-id="fc12c-103">ADD TYPE</span></span>


<span data-ttu-id="fc12c-104">新增指定的檔案類型關聯。</span><span class="sxs-lookup"><span data-stu-id="fc12c-104">Adds the specified file type association.</span></span>

`SFTMIME ADD TYPE:file-extension /APP application [/ICON icon-pathname]                 [/DESCRIPTION type-desc] [/CONTENT-TYPE content-type] [/GLOBAL]                 [/PERCEIVED-TYPE perceived-type] [/PROGID progid]                 [/CONFIRMOPEN {YES|NO}] [/SHOWEXT {YES|NO}]                 [/NEWMENU {YES|NO}]  [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="fc12c-105">參數</span><span class="sxs-lookup"><span data-stu-id="fc12c-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="fc12c-106">描述</span><span class="sxs-lookup"><span data-stu-id="fc12c-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="fc12c-107">類型：檔案 &lt; 副檔名&gt;</span><span class="sxs-lookup"><span data-stu-id="fc12c-107">TYPE:&lt;file-extension&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="fc12c-108">將與指定的應用程式相關聯的檔案名副檔名。</span><span class="sxs-lookup"><span data-stu-id="fc12c-108">The file name extension that will be associated with the application specified.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="fc12c-109">/APP &lt; 應用程式&gt;</span><span class="sxs-lookup"><span data-stu-id="fc12c-109">/APP &lt;application&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="fc12c-110">應用程式的名稱和版本（選用）。</span><span class="sxs-lookup"><span data-stu-id="fc12c-110">The name and version (optional) of the application.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="fc12c-111">/ICON &lt; 圖示-pathname&gt;</span><span class="sxs-lookup"><span data-stu-id="fc12c-111">/ICON &lt;icon-pathname&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="fc12c-112">圖示檔案的路徑或 URL。</span><span class="sxs-lookup"><span data-stu-id="fc12c-112">The path or URL for the icon file.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="fc12c-113">/DESCRIPTION &lt; 類型-desc&gt;</span><span class="sxs-lookup"><span data-stu-id="fc12c-113">/DESCRIPTION &lt;type-desc&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="fc12c-114">檔案類型的方便使用名稱。</span><span class="sxs-lookup"><span data-stu-id="fc12c-114">The user-friendly name for the file type.</span></span> <span data-ttu-id="fc12c-115">預設值為 [延伸檔案] &quot; 。&quot;</span><span class="sxs-lookup"><span data-stu-id="fc12c-115">Defaults to &quot;EXTENSION File.&quot;</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="fc12c-116">/CONTENT-TYPE &lt; 內容類型&gt;</span><span class="sxs-lookup"><span data-stu-id="fc12c-116">/CONTENT-TYPE &lt;content-type&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="fc12c-117">檔案的內容類型。</span><span class="sxs-lookup"><span data-stu-id="fc12c-117">The content type of the file.</span></span> <span data-ttu-id="fc12c-118">預設為 &quot; 應用程式/softricity 延伸。&quot;</span><span class="sxs-lookup"><span data-stu-id="fc12c-118">Defaults to &quot;application/softricity-extension.&quot;</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="fc12c-119">/GLOBAL</span><span class="sxs-lookup"><span data-stu-id="fc12c-119">/GLOBAL</span></span></p></td>
<td align="left"><p><span data-ttu-id="fc12c-120">如果有的話，此電腦上的所有使用者都可以使用套件。</span><span class="sxs-lookup"><span data-stu-id="fc12c-120">If present, the package will be available for all users on this computer.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="fc12c-121">/PERCEIVED-TYPE &lt; 感知-類型&gt;</span><span class="sxs-lookup"><span data-stu-id="fc12c-121">/PERCEIVED-TYPE &lt;perceived-type&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="fc12c-122">檔案的感知類型。</span><span class="sxs-lookup"><span data-stu-id="fc12c-122">The perceived type of the file.</span></span> <span data-ttu-id="fc12c-123">預設為 [無]。</span><span class="sxs-lookup"><span data-stu-id="fc12c-123">Defaults to nothing.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="fc12c-124">/PROGID &lt; PROGID&gt;</span><span class="sxs-lookup"><span data-stu-id="fc12c-124">/PROGID &lt;progid&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="fc12c-125">檔案類型的程式設計識別碼。</span><span class="sxs-lookup"><span data-stu-id="fc12c-125">The programmatic identifier for the file type.</span></span> <span data-ttu-id="fc12c-126">預設為應用程式 Virt. 檔案。</span><span class="sxs-lookup"><span data-stu-id="fc12c-126">Defaults to App Virt.extension.File.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="fc12c-127">/CONFIRMOPEN</span><span class="sxs-lookup"><span data-stu-id="fc12c-127">/CONFIRMOPEN</span></span></p></td>
<td align="left"><p><span data-ttu-id="fc12c-128">指示使用者是否要下載此類型的檔案，是否應該詢問是否要開啟或儲存檔案。</span><span class="sxs-lookup"><span data-stu-id="fc12c-128">Indicates whether users downloading a file of this type should be asked whether to open or save the file.</span></span> <span data-ttu-id="fc12c-129">預設為 [是]。</span><span class="sxs-lookup"><span data-stu-id="fc12c-129">Defaults to YES.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="fc12c-130">/SHOWEXT</span><span class="sxs-lookup"><span data-stu-id="fc12c-130">/SHOWEXT</span></span></p></td>
<td align="left"><p><span data-ttu-id="fc12c-131">指出是否應該顯示檔案的副檔名（即使使用者已要求隱藏所有副檔名）。</span><span class="sxs-lookup"><span data-stu-id="fc12c-131">Indicates whether the file's extension should always be shown, even if the user has requested that all extensions be hidden.</span></span> <span data-ttu-id="fc12c-132">預設值為 [否]。</span><span class="sxs-lookup"><span data-stu-id="fc12c-132">Defaults to NO.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="fc12c-133">/NEWMENU</span><span class="sxs-lookup"><span data-stu-id="fc12c-133">/NEWMENU</span></span></p></td>
<td align="left"><p><span data-ttu-id="fc12c-134">指出是否應該在 shell 的 [新增] 功能表中新增一個專案 <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="fc12c-134">Indicates whether an entry should be added to the shell's <strong>New</strong> menu.</span></span> <span data-ttu-id="fc12c-135">預設值為 [否]。</span><span class="sxs-lookup"><span data-stu-id="fc12c-135">Defaults to NO.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="fc12c-136">/LOG</span><span class="sxs-lookup"><span data-stu-id="fc12c-136">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="fc12c-137">如果已指定，輸出就會記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="fc12c-137">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="fc12c-138">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="fc12c-138">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="fc12c-139">如果已指定，輸出就會顯示在 active 主控台視窗中（預設）。</span><span class="sxs-lookup"><span data-stu-id="fc12c-139">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="fc12c-140">/GUI</span><span class="sxs-lookup"><span data-stu-id="fc12c-140">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="fc12c-141">如果已指定，輸出就會顯示在 Windows 對話方塊中。</span><span class="sxs-lookup"><span data-stu-id="fc12c-141">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="fc12c-142">針對版本4.6，新增了下列選項。</span><span class="sxs-lookup"><span data-stu-id="fc12c-142">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="fc12c-143">/LOGU</span><span class="sxs-lookup"><span data-stu-id="fc12c-143">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="fc12c-144">如果已指定，輸出會以 UNICODE 格式記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="fc12c-144">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="fc12c-145">相關主題</span><span class="sxs-lookup"><span data-stu-id="fc12c-145">Related topics</span></span>


[<span data-ttu-id="fc12c-146">SFTMIME 命令參考</span><span class="sxs-lookup"><span data-stu-id="fc12c-146">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





