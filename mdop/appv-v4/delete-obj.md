---
title: DELETE OBJ
description: DELETE OBJ
author: dansimp
ms.assetid: fb17a261-f378-4ce6-a538-ab2f0ada0f2d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4d74fc1ac098d7dc4dd2f28633e9ca58d4211d74
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808913"
---
# <span data-ttu-id="0af73-103">DELETE OBJ</span><span class="sxs-lookup"><span data-stu-id="0af73-103">DELETE OBJ</span></span>


<span data-ttu-id="0af73-104">移除所有的應用程式記錄。</span><span class="sxs-lookup"><span data-stu-id="0af73-104">Removes all of your application records.</span></span>

`SFTMIME DELETE OBJ:APP [/GLOBAL] [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="0af73-105">參數</span><span class="sxs-lookup"><span data-stu-id="0af73-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="0af73-106">描述</span><span class="sxs-lookup"><span data-stu-id="0af73-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0af73-107">/GLOBAL</span><span class="sxs-lookup"><span data-stu-id="0af73-107">/GLOBAL</span></span></p></td>
<td align="left"><p><span data-ttu-id="0af73-108">如果已指定，所有應用程式都會被移除。</span><span class="sxs-lookup"><span data-stu-id="0af73-108">If specified, all applications are removed.</span></span> <span data-ttu-id="0af73-109">根據預設，只有目前使用者有權存取的應用程式才會被移除。</span><span class="sxs-lookup"><span data-stu-id="0af73-109">By default, only applications the current user has access to are removed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0af73-110">/LOG</span><span class="sxs-lookup"><span data-stu-id="0af73-110">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="0af73-111">如果已指定，輸出就會記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="0af73-111">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0af73-112">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="0af73-112">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="0af73-113">如果已指定，輸出就會顯示在 active 主控台視窗中（預設）。</span><span class="sxs-lookup"><span data-stu-id="0af73-113">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0af73-114">/GUI</span><span class="sxs-lookup"><span data-stu-id="0af73-114">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="0af73-115">如果已指定，輸出就會顯示在 Windows 對話方塊中。</span><span class="sxs-lookup"><span data-stu-id="0af73-115">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="0af73-116">針對版本4.6，新增了下列選項。</span><span class="sxs-lookup"><span data-stu-id="0af73-116">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0af73-117">/LOGU</span><span class="sxs-lookup"><span data-stu-id="0af73-117">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="0af73-118">如果已指定，輸出會以 UNICODE 格式記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="0af73-118">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="0af73-119">相關主題</span><span class="sxs-lookup"><span data-stu-id="0af73-119">Related topics</span></span>


[<span data-ttu-id="0af73-120">SFTMIME 命令參考</span><span class="sxs-lookup"><span data-stu-id="0af73-120">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





