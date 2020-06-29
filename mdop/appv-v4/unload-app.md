---
title: UNLOAD APP
description: UNLOAD APP
author: dansimp
ms.assetid: f0d729ae-8772-498b-be11-1a4b35499c53
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f1ae30f5b8c788f8763c2c2b9d1c1956182750d3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800762"
---
# <span data-ttu-id="19719-103">UNLOAD APP</span><span class="sxs-lookup"><span data-stu-id="19719-103">UNLOAD APP</span></span>


<span data-ttu-id="19719-104">從檔案系統快取中卸載應用程式及套件中的所有其他應用程式。</span><span class="sxs-lookup"><span data-stu-id="19719-104">Unloads the application and all other applications in the package from the file system cache.</span></span>

`SFTMIME UNLOAD APP:application [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="19719-105">參數</span><span class="sxs-lookup"><span data-stu-id="19719-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="19719-106">描述</span><span class="sxs-lookup"><span data-stu-id="19719-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="19719-107">APP： &lt; 應用程式&gt;</span><span class="sxs-lookup"><span data-stu-id="19719-107">APP:&lt;application&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="19719-108">要卸載之應用程式的名稱和版本（選用）。</span><span class="sxs-lookup"><span data-stu-id="19719-108">The name and version (optional) of the application to unload.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="19719-109">/LOG</span><span class="sxs-lookup"><span data-stu-id="19719-109">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="19719-110">如果已指定，輸出就會記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="19719-110">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="19719-111">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="19719-111">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="19719-112">如果已指定，輸出就會顯示在 active 主控台視窗中（預設）。</span><span class="sxs-lookup"><span data-stu-id="19719-112">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="19719-113">/GUI</span><span class="sxs-lookup"><span data-stu-id="19719-113">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="19719-114">如果已指定，輸出就會顯示在 Windows 對話方塊中。</span><span class="sxs-lookup"><span data-stu-id="19719-114">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="19719-115">針對版本4.6，新增了下列選項。</span><span class="sxs-lookup"><span data-stu-id="19719-115">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="19719-116">/LOGU</span><span class="sxs-lookup"><span data-stu-id="19719-116">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="19719-117">如果已指定，輸出會以 UNICODE 格式記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="19719-117">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="19719-118">相關主題</span><span class="sxs-lookup"><span data-stu-id="19719-118">Related topics</span></span>


[<span data-ttu-id="19719-119">SFTMIME 命令參考</span><span class="sxs-lookup"><span data-stu-id="19719-119">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





