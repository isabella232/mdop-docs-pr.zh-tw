---
title: CONFIGURE APP
description: CONFIGURE APP
author: dansimp
ms.assetid: fcfb4f86-8b7c-4208-bca3-955fd067079f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 42ff17e180df262deed3fe79674ad6fda6f0be4e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802193"
---
# <span data-ttu-id="ce2e6-103">CONFIGURE APP</span><span class="sxs-lookup"><span data-stu-id="ce2e6-103">CONFIGURE APP</span></span>


<span data-ttu-id="ce2e6-104">讓使用者變更與應用程式相關聯的圖示，但不會更新現有快速鍵或檔案類型關聯的圖示。</span><span class="sxs-lookup"><span data-stu-id="ce2e6-104">Enables the user to change the icon associated with an application but does not update the icon on existing shortcuts or file type associations.</span></span>

`SFTMIME CONFIGURE APP:application /ICON icon-pathname                 [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ce2e6-105">參數</span><span class="sxs-lookup"><span data-stu-id="ce2e6-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="ce2e6-106">描述</span><span class="sxs-lookup"><span data-stu-id="ce2e6-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ce2e6-107">APP： &lt; 應用程式&gt;</span><span class="sxs-lookup"><span data-stu-id="ce2e6-107">APP:&lt;application&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="ce2e6-108">應用程式的名稱和版本（選用）。</span><span class="sxs-lookup"><span data-stu-id="ce2e6-108">The name and version (optional) of the application.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ce2e6-109">/ICON &lt; 圖示-pathname&gt;</span><span class="sxs-lookup"><span data-stu-id="ce2e6-109">/ICON &lt;icon-pathname&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="ce2e6-110">圖示檔案的路徑或 URL。</span><span class="sxs-lookup"><span data-stu-id="ce2e6-110">The path or URL for the icon file.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ce2e6-111">/LOG</span><span class="sxs-lookup"><span data-stu-id="ce2e6-111">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="ce2e6-112">如果已指定，輸出就會記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="ce2e6-112">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ce2e6-113">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="ce2e6-113">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="ce2e6-114">如果已指定，輸出就會顯示在 active 主控台視窗中（預設）。</span><span class="sxs-lookup"><span data-stu-id="ce2e6-114">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ce2e6-115">/GUI</span><span class="sxs-lookup"><span data-stu-id="ce2e6-115">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="ce2e6-116">如果已指定，輸出就會顯示在 Windows 對話方塊中。</span><span class="sxs-lookup"><span data-stu-id="ce2e6-116">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="ce2e6-117">針對版本4.6，新增了下列選項。</span><span class="sxs-lookup"><span data-stu-id="ce2e6-117">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ce2e6-118">/LOGU</span><span class="sxs-lookup"><span data-stu-id="ce2e6-118">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="ce2e6-119">如果已指定，輸出會以 UNICODE 格式記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="ce2e6-119">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="ce2e6-120">相關主題</span><span class="sxs-lookup"><span data-stu-id="ce2e6-120">Related topics</span></span>


[<span data-ttu-id="ce2e6-121">SFTMIME 命令參考</span><span class="sxs-lookup"><span data-stu-id="ce2e6-121">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





