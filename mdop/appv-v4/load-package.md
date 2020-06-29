---
title: LOAD PACKAGE
description: LOAD PACKAGE
author: dansimp
ms.assetid: eb19116d-e5d0-445c-b2f0-3116a09384d7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 938aa92696c8530c91d9a7acaac42408de534edc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800979"
---
# <span data-ttu-id="7d01a-103">LOAD PACKAGE</span><span class="sxs-lookup"><span data-stu-id="7d01a-103">LOAD PACKAGE</span></span>


<span data-ttu-id="7d01a-104">將指定的套件載入到檔案系統快取中。</span><span class="sxs-lookup"><span data-stu-id="7d01a-104">Loads the specified package into the file system cache.</span></span>

`SFTMIME LOAD PACKAGE:package-name [/SFTPATH sft-pathname]                 [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="7d01a-105">參數</span><span class="sxs-lookup"><span data-stu-id="7d01a-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="7d01a-106">描述</span><span class="sxs-lookup"><span data-stu-id="7d01a-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7d01a-107">套件： &lt; 套件-名稱&gt;</span><span class="sxs-lookup"><span data-stu-id="7d01a-107">PACKAGE:&lt;package-name&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="7d01a-108">要載入之套件的名稱。</span><span class="sxs-lookup"><span data-stu-id="7d01a-108">The name of the package to load.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="7d01a-109">/SFTPATH &lt; sft-pathname&gt;</span><span class="sxs-lookup"><span data-stu-id="7d01a-109">/SFTPATH &lt;sft-pathname&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="7d01a-110">如果已指定，則是要從中載入的 SFT 檔案路徑。</span><span class="sxs-lookup"><span data-stu-id="7d01a-110">If specified, the path to an SFT file to load from.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7d01a-111">/LOG</span><span class="sxs-lookup"><span data-stu-id="7d01a-111">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="7d01a-112">如果已指定，輸出就會記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="7d01a-112">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="7d01a-113">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="7d01a-113">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="7d01a-114">如果已指定，輸出就會顯示在 active 主控台視窗中（預設）。</span><span class="sxs-lookup"><span data-stu-id="7d01a-114">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7d01a-115">/GUI</span><span class="sxs-lookup"><span data-stu-id="7d01a-115">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="7d01a-116">如果已指定，輸出就會顯示在 Windows 對話方塊中。</span><span class="sxs-lookup"><span data-stu-id="7d01a-116">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="7d01a-117">針對版本4.6，新增了下列選項。</span><span class="sxs-lookup"><span data-stu-id="7d01a-117">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="7d01a-118">/LOGU</span><span class="sxs-lookup"><span data-stu-id="7d01a-118">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="7d01a-119">如果已指定，輸出會以 UNICODE 格式記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="7d01a-119">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="7d01a-120">**記事** 如果未指定 SFTPATH，用戶端會使用根據 OSD 檔案、ApplicationSourceRoot 登錄項值或 OverrideURL 設定而設定的路徑來載入套件。</span><span class="sxs-lookup"><span data-stu-id="7d01a-120">**Note** If no SFTPATH is specified, the client will load the package by using the path it has been configured to use, based on the OSD file, the ApplicationSourceRoot registry key value, or the OverrideURL setting.</span></span>

<span data-ttu-id="7d01a-121">[**載入套件**] 命令會執行同步載入，在套件完全載入或遇到錯誤情況之前，將無法完成。</span><span class="sxs-lookup"><span data-stu-id="7d01a-121">The **LOAD PACKAGE** command performs a synchronous load and will not be complete until the package is fully loaded or until it encounters an error condition.</span></span>

 

## <span data-ttu-id="7d01a-122">相關主題</span><span class="sxs-lookup"><span data-stu-id="7d01a-122">Related topics</span></span>


[<span data-ttu-id="7d01a-123">SFTMIME 命令參考</span><span class="sxs-lookup"><span data-stu-id="7d01a-123">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





