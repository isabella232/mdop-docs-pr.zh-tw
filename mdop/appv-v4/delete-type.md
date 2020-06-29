---
title: DELETE TYPE
description: DELETE TYPE
author: dansimp
ms.assetid: f2852723-c894-49f3-a3c5-56f9648bb9ca
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0df68c0a0efcd0e269410d1580f7b0a82301c46d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808906"
---
# <span data-ttu-id="2dab3-103">DELETE TYPE</span><span class="sxs-lookup"><span data-stu-id="2dab3-103">DELETE TYPE</span></span>


<span data-ttu-id="2dab3-104">移除指定的檔案類型關聯。</span><span class="sxs-lookup"><span data-stu-id="2dab3-104">Removes the specified file type association.</span></span>

`SFTMIME DELETE TYPE:file-extension [/GLOBAL]                 [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2dab3-105">參數</span><span class="sxs-lookup"><span data-stu-id="2dab3-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="2dab3-106">描述</span><span class="sxs-lookup"><span data-stu-id="2dab3-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2dab3-107">類型：檔案 &lt; 副檔名&gt;</span><span class="sxs-lookup"><span data-stu-id="2dab3-107">TYPE:&lt;file-extension&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="2dab3-108">要移除的檔案名副檔名。</span><span class="sxs-lookup"><span data-stu-id="2dab3-108">The file name extension to be removed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2dab3-109">/GLOBAL</span><span class="sxs-lookup"><span data-stu-id="2dab3-109">/GLOBAL</span></span></p></td>
<td align="left"><p><span data-ttu-id="2dab3-110">如果已指定，則表示應該移除檔案名副檔名的全域關聯。</span><span class="sxs-lookup"><span data-stu-id="2dab3-110">If specified, indicates that the global association for the file name extension should be removed.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2dab3-111">/LOG</span><span class="sxs-lookup"><span data-stu-id="2dab3-111">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="2dab3-112">如果已指定，輸出就會記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="2dab3-112">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2dab3-113">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="2dab3-113">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="2dab3-114">如果已指定，輸出就會顯示在 active 主控台視窗中（預設）。</span><span class="sxs-lookup"><span data-stu-id="2dab3-114">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2dab3-115">/GUI</span><span class="sxs-lookup"><span data-stu-id="2dab3-115">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="2dab3-116">如果已指定，輸出就會顯示在 Windows 對話方塊中。</span><span class="sxs-lookup"><span data-stu-id="2dab3-116">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="2dab3-117">針對版本4.6，新增了下列選項。</span><span class="sxs-lookup"><span data-stu-id="2dab3-117">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2dab3-118">/LOGU</span><span class="sxs-lookup"><span data-stu-id="2dab3-118">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="2dab3-119">如果已指定，輸出會以 UNICODE 格式記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="2dab3-119">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="2dab3-120">相關主題</span><span class="sxs-lookup"><span data-stu-id="2dab3-120">Related topics</span></span>


[<span data-ttu-id="2dab3-121">SFTMIME 命令參考</span><span class="sxs-lookup"><span data-stu-id="2dab3-121">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





