---
title: DELETE APP
description: DELETE APP
author: dansimp
ms.assetid: 2f89c0c0-373b-4389-a26d-67b3f9712957
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c27c70ef3227ebaf6b16bcb1fbb4b4e65b7cb7f4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808924"
---
# <span data-ttu-id="41bed-103">DELETE APP</span><span class="sxs-lookup"><span data-stu-id="41bed-103">DELETE APP</span></span>


<span data-ttu-id="41bed-104">從檔案系統快取中移除應用程式記錄，讓它不再顯示。</span><span class="sxs-lookup"><span data-stu-id="41bed-104">Removes an application record from the file system cache to make it no longer visible.</span></span> <span data-ttu-id="41bed-105">使用者的快捷方式和檔案類型關聯是隱藏的，但不會被刪除。</span><span class="sxs-lookup"><span data-stu-id="41bed-105">Users’ shortcuts and file type associations are hidden but not deleted.</span></span> <span data-ttu-id="41bed-106">不會移除任何使用者設定。</span><span class="sxs-lookup"><span data-stu-id="41bed-106">No user settings are removed.</span></span>

`SFTMIME DELETE APP:application [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="41bed-107">參數</span><span class="sxs-lookup"><span data-stu-id="41bed-107">Parameter</span></span></th>
<th align="left"><span data-ttu-id="41bed-108">描述</span><span class="sxs-lookup"><span data-stu-id="41bed-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="41bed-109">APP： &lt; 應用程式&gt;</span><span class="sxs-lookup"><span data-stu-id="41bed-109">APP:&lt;application&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="41bed-110">要移除之應用程式的名稱與版本（選用）。</span><span class="sxs-lookup"><span data-stu-id="41bed-110">The name and version (optional) of the application to be removed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="41bed-111">/LOG</span><span class="sxs-lookup"><span data-stu-id="41bed-111">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="41bed-112">如果已指定，輸出就會記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="41bed-112">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="41bed-113">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="41bed-113">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="41bed-114">如果已指定，輸出就會顯示在 active 主控台視窗中（預設）。</span><span class="sxs-lookup"><span data-stu-id="41bed-114">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="41bed-115">/GUI</span><span class="sxs-lookup"><span data-stu-id="41bed-115">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="41bed-116">如果已指定，輸出就會顯示在 Windows 對話方塊中。</span><span class="sxs-lookup"><span data-stu-id="41bed-116">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="41bed-117">針對版本4.6，新增了下列選項。</span><span class="sxs-lookup"><span data-stu-id="41bed-117">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="41bed-118">/LOGU</span><span class="sxs-lookup"><span data-stu-id="41bed-118">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="41bed-119">如果已指定，輸出會以 UNICODE 格式記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="41bed-119">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="41bed-120">相關主題</span><span class="sxs-lookup"><span data-stu-id="41bed-120">Related topics</span></span>


[<span data-ttu-id="41bed-121">SFTMIME 命令參考</span><span class="sxs-lookup"><span data-stu-id="41bed-121">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





