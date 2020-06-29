---
title: ADD PACKAGE
description: ADD PACKAGE
author: dansimp
ms.assetid: aa83928d-a234-4395-831e-2a7ef786ff53
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 925349ce5bdf041b6a8768b5413692966e1cfc1e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809332"
---
# <span data-ttu-id="d30d3-103">ADD PACKAGE</span><span class="sxs-lookup"><span data-stu-id="d30d3-103">ADD PACKAGE</span></span>


<span data-ttu-id="d30d3-104">新增套件記錄。</span><span class="sxs-lookup"><span data-stu-id="d30d3-104">Adds a package record.</span></span> <span data-ttu-id="d30d3-105">如果套件已存在，此命令會更新現有套件的設定。</span><span class="sxs-lookup"><span data-stu-id="d30d3-105">If the package already exists, this command will update the configuration of the existing package.</span></span>

`SFTMIME ADD PACKAGE:package-name /MANIFEST manifest-path                 [/OVERRIDEURL url [/AUTOLOADONREFRESH] [/AUTOLOADONLOGIN]                 [/AUTOLOADONLAUNCH] [/AUTOLOADTARGET {NONE|ALL|PREVUSED}]                 [/GLOBAL] [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d30d3-106">參數</span><span class="sxs-lookup"><span data-stu-id="d30d3-106">Parameter</span></span></th>
<th align="left"><span data-ttu-id="d30d3-107">描述</span><span class="sxs-lookup"><span data-stu-id="d30d3-107">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d30d3-108">套件： &lt; 套件-名稱&gt;</span><span class="sxs-lookup"><span data-stu-id="d30d3-108">PACKAGE:&lt;package-name&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="d30d3-109">套件的使用者可見及方便使用名稱。</span><span class="sxs-lookup"><span data-stu-id="d30d3-109">User-visible and user-friendly name for the package.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d30d3-110">/MANIFEST &lt; 資訊清單-path&gt;</span><span class="sxs-lookup"><span data-stu-id="d30d3-110">/MANIFEST &lt;manifest-path&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="d30d3-111">列出套件中包含之應用程式的資訊清單檔案路徑，以及其所有發佈資訊。</span><span class="sxs-lookup"><span data-stu-id="d30d3-111">The path of the manifest file that lists the applications included in the package and all of their publishing information.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d30d3-112">/OVERRIDEURL &lt; URL&gt;</span><span class="sxs-lookup"><span data-stu-id="d30d3-112">/OVERRIDEURL &lt;URL&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="d30d3-113">套件的 SFT 檔案位置。</span><span class="sxs-lookup"><span data-stu-id="d30d3-113">The location of the package's SFT file.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d30d3-114">/AUTOLOADONREFRESH</span><span class="sxs-lookup"><span data-stu-id="d30d3-114">/AUTOLOADONREFRESH</span></span></p></td>
<td align="left"><p><span data-ttu-id="d30d3-115">在發佈重新整理之後，會執行背景載入。</span><span class="sxs-lookup"><span data-stu-id="d30d3-115">Background loading is performed after a publishing refresh.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d30d3-116">/AUTOLOADONLOGIN</span><span class="sxs-lookup"><span data-stu-id="d30d3-116">/AUTOLOADONLOGIN</span></span></p></td>
<td align="left"><p><span data-ttu-id="d30d3-117">在使用者登入時，會執行背景載入。</span><span class="sxs-lookup"><span data-stu-id="d30d3-117">Background loading is performed when a user logs in.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d30d3-118">/AUTOLOADONLAUNCH</span><span class="sxs-lookup"><span data-stu-id="d30d3-118">/AUTOLOADONLAUNCH</span></span></p></td>
<td align="left"><p><span data-ttu-id="d30d3-119">使用者從套件啟動應用程式後，就會執行背景載入。</span><span class="sxs-lookup"><span data-stu-id="d30d3-119">Background loading is performed after a user starts an application from the package.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d30d3-120">/AUTOLOADTARGET 目標</span><span class="sxs-lookup"><span data-stu-id="d30d3-120">/AUTOLOADTARGET target</span></span></p></td>
<td align="left"><p><span data-ttu-id="d30d3-121">指示將會 autoloaded 套件中的哪些應用程式。</span><span class="sxs-lookup"><span data-stu-id="d30d3-121">Indicates which applications from the package will be autoloaded.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d30d3-122">所有</span><span class="sxs-lookup"><span data-stu-id="d30d3-122">NONE</span></span></p></td>
<td align="left"><p><span data-ttu-id="d30d3-123">不論是否有任何/AUTOLOADONxxx 標誌，都不會執行任何 autoloading。</span><span class="sxs-lookup"><span data-stu-id="d30d3-123">No autoloading will be performed, despite the presence of any /AUTOLOADONxxx flags.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d30d3-124">同時</span><span class="sxs-lookup"><span data-stu-id="d30d3-124">ALL</span></span></p></td>
<td align="left"><p><span data-ttu-id="d30d3-125">如果啟用 autoload 觸發程式，則會將套件中的所有應用程式載入到 [快取] 中，不論它們先前是否已啟動。</span><span class="sxs-lookup"><span data-stu-id="d30d3-125">If an autoload trigger is enabled, all applications in the package will be loaded into cache whether or not they have been previously started.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d30d3-126">PREVUSED</span><span class="sxs-lookup"><span data-stu-id="d30d3-126">PREVUSED</span></span></p></td>
<td align="left"><p><span data-ttu-id="d30d3-127">如果啟用 autoload 觸發程式，則在使用者先前已啟動此套件中的任何應用程式時，就會載入套件。</span><span class="sxs-lookup"><span data-stu-id="d30d3-127">If an autoload trigger is enabled, the package will load if any applications in this package have previously been started by a user.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d30d3-128">/GLOBAL</span><span class="sxs-lookup"><span data-stu-id="d30d3-128">/GLOBAL</span></span></p></td>
<td align="left"><p><span data-ttu-id="d30d3-129">如果有的話，此電腦上的所有使用者都可以使用套件。</span><span class="sxs-lookup"><span data-stu-id="d30d3-129">If present, the package will be available for all users on this computer.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d30d3-130">/LOG</span><span class="sxs-lookup"><span data-stu-id="d30d3-130">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="d30d3-131">如果已指定，輸出就會記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="d30d3-131">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d30d3-132">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="d30d3-132">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="d30d3-133">如果已指定，輸出就會顯示在 active 主控台視窗中（預設）。</span><span class="sxs-lookup"><span data-stu-id="d30d3-133">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d30d3-134">/GUI</span><span class="sxs-lookup"><span data-stu-id="d30d3-134">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="d30d3-135">如果已指定，輸出就會顯示在 Windows 對話方塊中。</span><span class="sxs-lookup"><span data-stu-id="d30d3-135">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="d30d3-136">針對版本4.6，新增了下列選項。</span><span class="sxs-lookup"><span data-stu-id="d30d3-136">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d30d3-137">/LOGU</span><span class="sxs-lookup"><span data-stu-id="d30d3-137">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="d30d3-138">如果已指定，輸出會以 UNICODE 格式記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="d30d3-138">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="d30d3-139">相關主題</span><span class="sxs-lookup"><span data-stu-id="d30d3-139">Related topics</span></span>


[<span data-ttu-id="d30d3-140">SFTMIME 命令參考</span><span class="sxs-lookup"><span data-stu-id="d30d3-140">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





