---
title: DELETE SERVER
description: DELETE SERVER
author: dansimp
ms.assetid: 4c929639-1c1d-47c3-9225-cc4d7a8736f0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 92af31a818174fb4b0e82a11c918af2484ac2bce
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808907"
---
# <span data-ttu-id="cf732-103">DELETE SERVER</span><span class="sxs-lookup"><span data-stu-id="cf732-103">DELETE SERVER</span></span>


<span data-ttu-id="cf732-104">移除發佈伺服器。</span><span class="sxs-lookup"><span data-stu-id="cf732-104">Removes a publishing server.</span></span>

<span data-ttu-id="cf732-105">**記事** 這個命令不會移除伺服器發佈至用戶端的任何應用程式或套件。</span><span class="sxs-lookup"><span data-stu-id="cf732-105">**Note** This command does not remove any applications or packages published to the client by the server.</span></span> <span data-ttu-id="cf732-106">針對每個應用程式，使用 SFTMIME **CLEAR APP**命令，後面接著 [**刪除套件**] 命令，將這些應用程式和套件從用戶端中完全移除。</span><span class="sxs-lookup"><span data-stu-id="cf732-106">For each application, use the SFTMIME **CLEAR APP** command followed by the **DELETE PACKAGE** command to completely remove those applications and packages from the client.</span></span>

 

`SFTMIME DELETE SERVER:server-name [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="cf732-107">參數</span><span class="sxs-lookup"><span data-stu-id="cf732-107">Parameter</span></span></th>
<th align="left"><span data-ttu-id="cf732-108">描述</span><span class="sxs-lookup"><span data-stu-id="cf732-108">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cf732-109">伺服器： &lt; 伺服器-名稱&gt;</span><span class="sxs-lookup"><span data-stu-id="cf732-109">SERVER:&lt;server-name&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="cf732-110">發佈伺服器的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="cf732-110">The display name of the publishing server.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="cf732-111">/LOG</span><span class="sxs-lookup"><span data-stu-id="cf732-111">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="cf732-112">如果已指定，輸出就會記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="cf732-112">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cf732-113">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="cf732-113">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="cf732-114">如果已指定，輸出就會顯示在 active 主控台視窗中（預設）。</span><span class="sxs-lookup"><span data-stu-id="cf732-114">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="cf732-115">/GUI</span><span class="sxs-lookup"><span data-stu-id="cf732-115">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="cf732-116">如果已指定，輸出就會顯示在 Windows 對話方塊中。</span><span class="sxs-lookup"><span data-stu-id="cf732-116">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="cf732-117">針對版本4.6，新增了下列選項。</span><span class="sxs-lookup"><span data-stu-id="cf732-117">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="cf732-118">/LOGU</span><span class="sxs-lookup"><span data-stu-id="cf732-118">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="cf732-119">如果已指定，輸出會以 UNICODE 格式記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="cf732-119">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="cf732-120">相關主題</span><span class="sxs-lookup"><span data-stu-id="cf732-120">Related topics</span></span>


[<span data-ttu-id="cf732-121">SFTMIME 命令參考</span><span class="sxs-lookup"><span data-stu-id="cf732-121">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





