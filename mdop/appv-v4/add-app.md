---
title: ADD APP
description: ADD APP
author: dansimp
ms.assetid: 329fd0c8-a795-49be-b0fd-1367c5b4a34b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ac83c0cf130e8de1d34d42d74e946716e4503246
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802401"
---
# <span data-ttu-id="3305a-103">ADD APP</span><span class="sxs-lookup"><span data-stu-id="3305a-103">ADD APP</span></span>


<span data-ttu-id="3305a-104">新增應用程式記錄。</span><span class="sxs-lookup"><span data-stu-id="3305a-104">Adds an application record.</span></span>

`SFTMIME ADD APP:application /OSD osd-pathname [/ICON icon-pathname] [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="3305a-105">參數</span><span class="sxs-lookup"><span data-stu-id="3305a-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="3305a-106">描述</span><span class="sxs-lookup"><span data-stu-id="3305a-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3305a-107">APP： &lt; 應用程式&gt;</span><span class="sxs-lookup"><span data-stu-id="3305a-107">APP:&lt;application&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="3305a-108">應用程式的名稱和版本（選用）。</span><span class="sxs-lookup"><span data-stu-id="3305a-108">The name and version (optional) of the application.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3305a-109">/OSD &lt; OSD-pathname&gt;</span><span class="sxs-lookup"><span data-stu-id="3305a-109">/OSD &lt;osd-pathname&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="3305a-110">OSD 檔案的路徑或 URL。</span><span class="sxs-lookup"><span data-stu-id="3305a-110">The path or URL for the OSD file.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3305a-111">/ICON &lt; 圖示-pathname&gt;</span><span class="sxs-lookup"><span data-stu-id="3305a-111">/ICON &lt;icon-pathname&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="3305a-112">圖示檔案的路徑或 URL。</span><span class="sxs-lookup"><span data-stu-id="3305a-112">The path or URL for the icon file.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3305a-113">/LOG</span><span class="sxs-lookup"><span data-stu-id="3305a-113">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="3305a-114">如果已指定，輸出就會記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="3305a-114">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3305a-115">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="3305a-115">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="3305a-116">如果已指定，輸出就會顯示在 active 主控台視窗中（預設）。</span><span class="sxs-lookup"><span data-stu-id="3305a-116">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="3305a-117">/GUI</span><span class="sxs-lookup"><span data-stu-id="3305a-117">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="3305a-118">如果已指定，輸出就會顯示在 Windows 對話方塊中。</span><span class="sxs-lookup"><span data-stu-id="3305a-118">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="3305a-119">針對版本4.6，新增了下列選項。</span><span class="sxs-lookup"><span data-stu-id="3305a-119">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="3305a-120">/LOGU</span><span class="sxs-lookup"><span data-stu-id="3305a-120">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="3305a-121">如果已指定，輸出會以 UNICODE 格式記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="3305a-121">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="3305a-122">**記事** 應用程式的產生名稱將會從 OSD 檔案中取得，而不是從應用程式： application 中提供的名稱 &lt; &gt; 。</span><span class="sxs-lookup"><span data-stu-id="3305a-122">**Note** The resulting name of the application will be taken from the OSD file and not from the name provided in APP:&lt;application&gt;.</span></span>

 

## <span data-ttu-id="3305a-123">相關主題</span><span class="sxs-lookup"><span data-stu-id="3305a-123">Related topics</span></span>


[<span data-ttu-id="3305a-124">SFTMIME 命令參考</span><span class="sxs-lookup"><span data-stu-id="3305a-124">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





