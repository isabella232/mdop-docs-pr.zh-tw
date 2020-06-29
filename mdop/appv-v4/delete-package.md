---
title: DELETE PACKAGE
description: DELETE PACKAGE
author: dansimp
ms.assetid: 8f7a4598-610d-490e-a224-426acce01a9f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a0051967ca308e88d143b8116330f5d770d6086d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808912"
---
# <span data-ttu-id="b925c-103">DELETE PACKAGE</span><span class="sxs-lookup"><span data-stu-id="b925c-103">DELETE PACKAGE</span></span>


<span data-ttu-id="b925c-104">移除套件記錄以及與它相關聯的應用程式。</span><span class="sxs-lookup"><span data-stu-id="b925c-104">Removes a package record and the applications associated with it.</span></span>

`SFTMIME DELETE PACKAGE:package-name                 [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b925c-105">參數</span><span class="sxs-lookup"><span data-stu-id="b925c-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="b925c-106">描述</span><span class="sxs-lookup"><span data-stu-id="b925c-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b925c-107">套件： &lt; 套件-名稱&gt;</span><span class="sxs-lookup"><span data-stu-id="b925c-107">PACKAGE:&lt;package-name&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="b925c-108">要移除之套件的名稱。</span><span class="sxs-lookup"><span data-stu-id="b925c-108">The name of the package to be removed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b925c-109">/LOG</span><span class="sxs-lookup"><span data-stu-id="b925c-109">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="b925c-110">如果已指定，輸出就會記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="b925c-110">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b925c-111">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="b925c-111">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="b925c-112">如果已指定，輸出就會顯示在 active 主控台視窗中（預設）。</span><span class="sxs-lookup"><span data-stu-id="b925c-112">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b925c-113">/GUI</span><span class="sxs-lookup"><span data-stu-id="b925c-113">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="b925c-114">如果已指定，輸出就會顯示在 Windows 對話方塊中。</span><span class="sxs-lookup"><span data-stu-id="b925c-114">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="b925c-115">針對版本4.6，新增了下列選項。</span><span class="sxs-lookup"><span data-stu-id="b925c-115">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b925c-116">/LOGU</span><span class="sxs-lookup"><span data-stu-id="b925c-116">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="b925c-117">如果已指定，輸出會以 UNICODE 格式記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="b925c-117">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="b925c-118">**重要** [刪除套件] 命令會始終執行套件的全域刪除，且只會刪除通用檔案類型和快速鍵。</span><span class="sxs-lookup"><span data-stu-id="b925c-118">**Important** The DELETE PACKAGE command always performs a global delete of the package and deletes only global file types and shortcuts.</span></span>

<span data-ttu-id="b925c-119">如果套件是全域性的，必須以本機管理員身分執行此命令;否則，只需要**DeleteApp**許可權。</span><span class="sxs-lookup"><span data-stu-id="b925c-119">If the package is global, this command must be run as local Administrator; otherwise, only **DeleteApp** permission is needed.</span></span>

 

## <span data-ttu-id="b925c-120">相關主題</span><span class="sxs-lookup"><span data-stu-id="b925c-120">Related topics</span></span>


[<span data-ttu-id="b925c-121">SFTMIME 命令參考</span><span class="sxs-lookup"><span data-stu-id="b925c-121">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





