---
title: CLEAR APP
description: CLEAR APP
author: dansimp
ms.assetid: c2e63031-5941-45e4-9863-127231cfa25b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 26f2363bf15bd33d0da3fee48319b215e6791db9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809087"
---
# <span data-ttu-id="9e136-103">CLEAR APP</span><span class="sxs-lookup"><span data-stu-id="9e136-103">CLEAR APP</span></span>


<span data-ttu-id="9e136-104">清除目前使用者的設定和應用程式的發佈設定。</span><span class="sxs-lookup"><span data-stu-id="9e136-104">Clears the current user's settings and publishing configurations for an application.</span></span>

`SFTMIME CLEAR APP:application [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9e136-105">參數</span><span class="sxs-lookup"><span data-stu-id="9e136-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="9e136-106">描述</span><span class="sxs-lookup"><span data-stu-id="9e136-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9e136-107">APP： &lt; 應用程式&gt;</span><span class="sxs-lookup"><span data-stu-id="9e136-107">APP:&lt;application&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="9e136-108">應用程式的名稱和版本（選用）。</span><span class="sxs-lookup"><span data-stu-id="9e136-108">The name and version (optional) of the application.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9e136-109">/LOG</span><span class="sxs-lookup"><span data-stu-id="9e136-109">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="9e136-110">如果已指定，輸出就會記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="9e136-110">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9e136-111">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="9e136-111">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="9e136-112">如果已指定，輸出就會顯示在 active 主控台視窗中（預設）。</span><span class="sxs-lookup"><span data-stu-id="9e136-112">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9e136-113">/GUI</span><span class="sxs-lookup"><span data-stu-id="9e136-113">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="9e136-114">如果已指定，輸出就會顯示在 Windows 對話方塊中。</span><span class="sxs-lookup"><span data-stu-id="9e136-114">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="9e136-115">針對版本4.6，新增了下列選項。</span><span class="sxs-lookup"><span data-stu-id="9e136-115">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9e136-116">/LOGU</span><span class="sxs-lookup"><span data-stu-id="9e136-116">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="9e136-117">如果已指定，輸出會以 UNICODE 格式記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="9e136-117">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="9e136-118">相關主題</span><span class="sxs-lookup"><span data-stu-id="9e136-118">Related topics</span></span>


[<span data-ttu-id="9e136-119">SFTMIME 命令參考</span><span class="sxs-lookup"><span data-stu-id="9e136-119">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





