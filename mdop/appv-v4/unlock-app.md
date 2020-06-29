---
title: UNLOCK APP
description: UNLOCK APP
author: dansimp
ms.assetid: 91fc8ceb-b4f5-4a06-8193-05189f830943
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2ea47191450014856b4a9823728e3e275c7fb4cf
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800760"
---
# <span data-ttu-id="64d69-103">UNLOCK APP</span><span class="sxs-lookup"><span data-stu-id="64d69-103">UNLOCK APP</span></span>


<span data-ttu-id="64d69-104">解除鎖定檔案系統快取中指定的應用程式。</span><span class="sxs-lookup"><span data-stu-id="64d69-104">Unlocks the application specified in the file system cache.</span></span>

`SFTMIME UNLOCK APP:application [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="64d69-105">參數</span><span class="sxs-lookup"><span data-stu-id="64d69-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="64d69-106">描述</span><span class="sxs-lookup"><span data-stu-id="64d69-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64d69-107">APP： &lt; 應用程式&gt;</span><span class="sxs-lookup"><span data-stu-id="64d69-107">APP:&lt;application&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="64d69-108">要解除鎖定之應用程式的名稱和版本（選用）。</span><span class="sxs-lookup"><span data-stu-id="64d69-108">The name and version (optional) of the application to unlock.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="64d69-109">/LOG</span><span class="sxs-lookup"><span data-stu-id="64d69-109">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="64d69-110">如果已指定，輸出就會記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="64d69-110">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64d69-111">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="64d69-111">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="64d69-112">如果已指定，輸出就會顯示在 active 主控台視窗中（預設）。</span><span class="sxs-lookup"><span data-stu-id="64d69-112">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="64d69-113">/GUI</span><span class="sxs-lookup"><span data-stu-id="64d69-113">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="64d69-114">如果已指定，輸出就會顯示在 Windows 對話方塊中。</span><span class="sxs-lookup"><span data-stu-id="64d69-114">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="64d69-115">針對版本4.6，新增了下列選項。</span><span class="sxs-lookup"><span data-stu-id="64d69-115">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="64d69-116">/LOGU</span><span class="sxs-lookup"><span data-stu-id="64d69-116">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="64d69-117">如果已指定，輸出會以 UNICODE 格式記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="64d69-117">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="64d69-118">相關主題</span><span class="sxs-lookup"><span data-stu-id="64d69-118">Related topics</span></span>


[<span data-ttu-id="64d69-119">SFTMIME 命令參考</span><span class="sxs-lookup"><span data-stu-id="64d69-119">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





