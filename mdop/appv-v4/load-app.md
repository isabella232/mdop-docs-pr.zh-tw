---
title: LOAD APP
description: LOAD APP
author: dansimp
ms.assetid: 7b727d0c-5423-419d-92ef-7ebbc6343e79
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 02bd6e35da898f5b34f7efc21cbc01a72d555b8d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800981"
---
# <span data-ttu-id="d2f71-103">LOAD APP</span><span class="sxs-lookup"><span data-stu-id="d2f71-103">LOAD APP</span></span>


<span data-ttu-id="d2f71-104">將套件中指定的應用程式及所有其他應用程式載入至檔案系統快取。</span><span class="sxs-lookup"><span data-stu-id="d2f71-104">Loads the specified application and all other applications in the package into the file system cache.</span></span>

<span data-ttu-id="d2f71-105">**記事** **載入 APP**命令會開機載入程式，並在桌面通知區域中顯示進度列。</span><span class="sxs-lookup"><span data-stu-id="d2f71-105">**Note** The **LOAD APP** command starts the load process and a progress bar is displayed in the Desktop Notification Area.</span></span> <span data-ttu-id="d2f71-106">這個命令會在開始這個程式後立即結束，因此任何載入錯誤都會顯示在同一個位置。</span><span class="sxs-lookup"><span data-stu-id="d2f71-106">The command exits immediately after starting this process, so any load errors are displayed in the same location.</span></span> <span data-ttu-id="d2f71-107">如果您想要從命令列開始載入程式，而不需要使用桌面通知區域，請使用 [**載入套件**] 命令。</span><span class="sxs-lookup"><span data-stu-id="d2f71-107">Use the **LOAD PACKAGE** command if you want to start the load process from the command line without using the Desktop Notification Area.</span></span>

 

`SFTMIME LOAD APP:application [/LOG log-pathname | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d2f71-108">參數</span><span class="sxs-lookup"><span data-stu-id="d2f71-108">Parameter</span></span></th>
<th align="left"><span data-ttu-id="d2f71-109">描述</span><span class="sxs-lookup"><span data-stu-id="d2f71-109">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d2f71-110">APP： &lt; 應用程式&gt;</span><span class="sxs-lookup"><span data-stu-id="d2f71-110">APP:&lt;application&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="d2f71-111">要載入之應用程式的名稱和版本（選用）。</span><span class="sxs-lookup"><span data-stu-id="d2f71-111">The name and version (optional) of the application to load.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d2f71-112">/LOG</span><span class="sxs-lookup"><span data-stu-id="d2f71-112">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="d2f71-113">如果已指定，輸出就會記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="d2f71-113">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d2f71-114">/GUI</span><span class="sxs-lookup"><span data-stu-id="d2f71-114">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="d2f71-115">如果已指定，輸出就會顯示在 Windows 對話方塊中。</span><span class="sxs-lookup"><span data-stu-id="d2f71-115">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="d2f71-116">針對版本4.6，新增了下列選項。</span><span class="sxs-lookup"><span data-stu-id="d2f71-116">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d2f71-117">/LOGU</span><span class="sxs-lookup"><span data-stu-id="d2f71-117">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="d2f71-118">如果已指定，輸出會以 UNICODE 格式記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="d2f71-118">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="d2f71-119">相關主題</span><span class="sxs-lookup"><span data-stu-id="d2f71-119">Related topics</span></span>


[<span data-ttu-id="d2f71-120">SFTMIME 命令參考</span><span class="sxs-lookup"><span data-stu-id="d2f71-120">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





