---
title: UNLOAD PACKAGE
description: UNLOAD PACKAGE
author: dansimp
ms.assetid: a076eb5a-ce3d-49e4-ac7a-4d4df10e3477
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fbee040f97bf5675ace7e873741a4270a993a911
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800761"
---
# <span data-ttu-id="0663b-103">UNLOAD PACKAGE</span><span class="sxs-lookup"><span data-stu-id="0663b-103">UNLOAD PACKAGE</span></span>


<span data-ttu-id="0663b-104">從檔案系統快取中卸載套件。</span><span class="sxs-lookup"><span data-stu-id="0663b-104">Unloads the package from the file system cache.</span></span>

`SFTMIME UNLOAD PACKAGE:package-name [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="0663b-105">參數</span><span class="sxs-lookup"><span data-stu-id="0663b-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="0663b-106">描述</span><span class="sxs-lookup"><span data-stu-id="0663b-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0663b-107">套件： &lt; 套件-名稱&gt;</span><span class="sxs-lookup"><span data-stu-id="0663b-107">PACKAGE:&lt;package-name&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="0663b-108">要卸載之套件的名稱。</span><span class="sxs-lookup"><span data-stu-id="0663b-108">The name of the package to unload.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0663b-109">/LOG</span><span class="sxs-lookup"><span data-stu-id="0663b-109">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="0663b-110">如果已指定，輸出就會記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="0663b-110">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0663b-111">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="0663b-111">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="0663b-112">如果已指定，輸出就會顯示在 active 主控台視窗中（預設）。</span><span class="sxs-lookup"><span data-stu-id="0663b-112">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0663b-113">/GUI</span><span class="sxs-lookup"><span data-stu-id="0663b-113">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="0663b-114">如果已指定，輸出就會顯示在 Windows 對話方塊中。</span><span class="sxs-lookup"><span data-stu-id="0663b-114">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="0663b-115">針對版本4.6，新增了下列選項。</span><span class="sxs-lookup"><span data-stu-id="0663b-115">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0663b-116">/LOGU</span><span class="sxs-lookup"><span data-stu-id="0663b-116">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="0663b-117">如果已指定，輸出會以 UNICODE 格式記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="0663b-117">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="0663b-118">相關主題</span><span class="sxs-lookup"><span data-stu-id="0663b-118">Related topics</span></span>


[<span data-ttu-id="0663b-119">SFTMIME 命令參考</span><span class="sxs-lookup"><span data-stu-id="0663b-119">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





