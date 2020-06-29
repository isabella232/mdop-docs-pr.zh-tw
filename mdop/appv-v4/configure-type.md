---
title: CONFIGURE TYPE
description: CONFIGURE TYPE
author: dansimp
ms.assetid: 2caf9433-5449-486f-ab94-83ee8e44d7f1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9b70cdd1b27eba0109183f1eb9cfb42f08b3f341
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809056"
---
# <span data-ttu-id="f360e-103">CONFIGURE TYPE</span><span class="sxs-lookup"><span data-stu-id="f360e-103">CONFIGURE TYPE</span></span>


<span data-ttu-id="f360e-104">讓使用者能夠變更檔案類型關聯的設定。</span><span class="sxs-lookup"><span data-stu-id="f360e-104">Enables the user to change settings for a file type association.</span></span>

`SFTMIME CONFIGURE TYPE:file-extension [/GLOBAL] [/APP application]                 [/ICON icon-pathname] [/DESCRIPTION type-desc]                 [/CONTENT-TYPE content-type] [/PERCEIVED-TYPE perceived-type]                 [/PROGID progid] [/CONFIRMOPEN {YES|NO}]                 [/SHOWEXT {YES|NO}] [/NEWMENU {YES|NO}]                 [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f360e-105">參數</span><span class="sxs-lookup"><span data-stu-id="f360e-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="f360e-106">描述</span><span class="sxs-lookup"><span data-stu-id="f360e-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f360e-107">類型：檔案 &lt; 副檔名&gt;</span><span class="sxs-lookup"><span data-stu-id="f360e-107">TYPE:&lt;file-extension&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="f360e-108">要設定的檔案名副檔名。</span><span class="sxs-lookup"><span data-stu-id="f360e-108">The file name extension to be configured.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f360e-109">/APP &lt; 應用程式&gt;</span><span class="sxs-lookup"><span data-stu-id="f360e-109">/APP &lt;application&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="f360e-110">要與此檔案類型相關聯的應用程式名稱與版本（選用）。</span><span class="sxs-lookup"><span data-stu-id="f360e-110">The name and version (optional) of the application to associate this file type with.</span></span> <span data-ttu-id="f360e-111">無法使用 PROGID 指定。</span><span class="sxs-lookup"><span data-stu-id="f360e-111">Cannot be specified with PROGID.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f360e-112">/ICON &lt; 圖示-pathname&gt;</span><span class="sxs-lookup"><span data-stu-id="f360e-112">/ICON &lt;icon-pathname&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="f360e-113">圖示檔案的路徑或 URL。</span><span class="sxs-lookup"><span data-stu-id="f360e-113">The path or URL for the icon file.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f360e-114">/DESCRIPTION &lt; 類型-desc&gt;</span><span class="sxs-lookup"><span data-stu-id="f360e-114">/DESCRIPTION &lt;type-desc&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="f360e-115">檔案類型的方便使用名稱。</span><span class="sxs-lookup"><span data-stu-id="f360e-115">The user-friendly name for the file type.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f360e-116">/CONTENT-TYPE &lt; 內容類型&gt;</span><span class="sxs-lookup"><span data-stu-id="f360e-116">/CONTENT-TYPE &lt;content-type&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="f360e-117">檔案的內容類型。</span><span class="sxs-lookup"><span data-stu-id="f360e-117">The content type of the file.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f360e-118">/GLOBAL</span><span class="sxs-lookup"><span data-stu-id="f360e-118">/GLOBAL</span></span></p></td>
<td align="left"><p><span data-ttu-id="f360e-119">如果存在，則表示您應該編輯適用于所有使用者的關聯，而不是使用者特定的關聯。</span><span class="sxs-lookup"><span data-stu-id="f360e-119">If present, indicates that the association that applies to all users should be edited, not the user-specific one.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f360e-120">/PERCEIVED-TYPE &lt; 感知-類型&gt;</span><span class="sxs-lookup"><span data-stu-id="f360e-120">/PERCEIVED-TYPE &lt;perceived-type&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="f360e-121">檔案的感知類型。</span><span class="sxs-lookup"><span data-stu-id="f360e-121">The perceived type of the file.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f360e-122">/PROGID &lt; PROGID&gt;</span><span class="sxs-lookup"><span data-stu-id="f360e-122">/PROGID &lt;progid&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="f360e-123">表示延伸應該與不同的檔案類型相關聯。</span><span class="sxs-lookup"><span data-stu-id="f360e-123">Indicates that the extension should be associated with a different file type.</span></span> <span data-ttu-id="f360e-124">先前的檔案類型不會被刪除。</span><span class="sxs-lookup"><span data-stu-id="f360e-124">The previous file type is not deleted.</span></span> <span data-ttu-id="f360e-125">無法使用 APP、ICON、DESCRIPTION、CONFIRMOPEN 或 SHOWEXT 加以指定。</span><span class="sxs-lookup"><span data-stu-id="f360e-125">Cannot be specified with APP, ICON, DESCRIPTION, CONFIRMOPEN, or SHOWEXT.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f360e-126">/CONFIRMOPEN</span><span class="sxs-lookup"><span data-stu-id="f360e-126">/CONFIRMOPEN</span></span></p></td>
<td align="left"><p><span data-ttu-id="f360e-127">指示使用者是否要下載此類型的檔案，是否應該詢問是否要開啟或儲存檔案。</span><span class="sxs-lookup"><span data-stu-id="f360e-127">Indicates whether users downloading a file of this type should be asked whether to open or save the file.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f360e-128">/SHOWEXT</span><span class="sxs-lookup"><span data-stu-id="f360e-128">/SHOWEXT</span></span></p></td>
<td align="left"><p><span data-ttu-id="f360e-129">指出是否應該顯示檔案的副檔名（即使使用者已要求隱藏所有副檔名）。</span><span class="sxs-lookup"><span data-stu-id="f360e-129">Indicates whether the file's extension should always be shown, even if the user has requested that all extensions be hidden.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f360e-130">/NEWMENU</span><span class="sxs-lookup"><span data-stu-id="f360e-130">/NEWMENU</span></span></p></td>
<td align="left"><p><span data-ttu-id="f360e-131">指出是否應該在 shell 的 [新增] 功能表中新增一個專案 <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="f360e-131">Indicates whether an entry should be added to the shell's <strong>New</strong> menu.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f360e-132">/LOG</span><span class="sxs-lookup"><span data-stu-id="f360e-132">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="f360e-133">如果已指定，輸出就會記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="f360e-133">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f360e-134">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="f360e-134">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="f360e-135">如果已指定，輸出就會顯示在 active 主控台視窗中（預設）。</span><span class="sxs-lookup"><span data-stu-id="f360e-135">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f360e-136">/GUI</span><span class="sxs-lookup"><span data-stu-id="f360e-136">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="f360e-137">如果已指定，輸出就會顯示在 Windows 對話方塊中。</span><span class="sxs-lookup"><span data-stu-id="f360e-137">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="f360e-138">針對版本4.6，新增了下列選項。</span><span class="sxs-lookup"><span data-stu-id="f360e-138">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f360e-139">/LOGU</span><span class="sxs-lookup"><span data-stu-id="f360e-139">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="f360e-140">如果已指定，輸出會以 UNICODE 格式記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="f360e-140">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="f360e-141">相關主題</span><span class="sxs-lookup"><span data-stu-id="f360e-141">Related topics</span></span>


[<span data-ttu-id="f360e-142">SFTMIME 命令參考</span><span class="sxs-lookup"><span data-stu-id="f360e-142">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





