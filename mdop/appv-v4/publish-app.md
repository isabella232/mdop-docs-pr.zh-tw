---
title: PUBLISH APP
description: PUBLISH APP
author: dansimp
ms.assetid: f25f06a8-ca23-435b-a0c2-16a5f39b6b97
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b2ccb19255786ee47a8356feef14be1c4d9b4fb2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800895"
---
# <span data-ttu-id="50d9b-103">PUBLISH APP</span><span class="sxs-lookup"><span data-stu-id="50d9b-103">PUBLISH APP</span></span>


<span data-ttu-id="50d9b-104">將應用程式快捷方式發佈至使用者的 [開始] 功能表、[桌面] 或其他指定位置。</span><span class="sxs-lookup"><span data-stu-id="50d9b-104">Publishes an application shortcut to the user's Start menu, desktop, or other specified location.</span></span>

`SFTMIME PUBLISH APP:application                 {/DESKTOP | /START | /TARGET target-path} [/ICON icon-pathname]                 [/DISPLAY display-name] [/ARGS command-args...]                 [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="50d9b-105">參數</span><span class="sxs-lookup"><span data-stu-id="50d9b-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="50d9b-106">描述</span><span class="sxs-lookup"><span data-stu-id="50d9b-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="50d9b-107">應用程式： &lt; 應用程式&gt;</span><span class="sxs-lookup"><span data-stu-id="50d9b-107">APPLICATION:&lt;application&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="50d9b-108">應用程式的名稱和版本（選用）。</span><span class="sxs-lookup"><span data-stu-id="50d9b-108">The name and version (optional) of the application.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="50d9b-109">/DESKTOP</span><span class="sxs-lookup"><span data-stu-id="50d9b-109">/DESKTOP</span></span></p></td>
<td align="left"><p><span data-ttu-id="50d9b-110">發佈使用者桌面的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="50d9b-110">Publishes a shortcut to the user's desktop.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="50d9b-111">/START</span><span class="sxs-lookup"><span data-stu-id="50d9b-111">/START</span></span></p></td>
<td align="left"><p><span data-ttu-id="50d9b-112">發佈快捷方式至 [開始] 功能表的 [程式] 資料夾中的 [應用程式虛擬化應用程式] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="50d9b-112">Publishes a shortcut to the Application Virtualization Applications folder in the Programs folder of the Start menu.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="50d9b-113">/TARGET &lt; 目標-path&gt;</span><span class="sxs-lookup"><span data-stu-id="50d9b-113">/TARGET &lt;target-path&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="50d9b-114">要發佈快捷方式的絕對路徑。</span><span class="sxs-lookup"><span data-stu-id="50d9b-114">The absolute path where the shortcut should be published.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="50d9b-115">/ICON &lt; 圖示-pathname&gt;</span><span class="sxs-lookup"><span data-stu-id="50d9b-115">/ICON &lt;icon-pathname&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="50d9b-116">圖示檔案的路徑或 URL。</span><span class="sxs-lookup"><span data-stu-id="50d9b-116">The path or URL for the icon file.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="50d9b-117">/DISPLAY &lt; 顯示名稱&gt;</span><span class="sxs-lookup"><span data-stu-id="50d9b-117">/DISPLAY &lt;display-name&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="50d9b-118">快捷方式的顯示名稱。</span><span class="sxs-lookup"><span data-stu-id="50d9b-118">The display name for the shortcut.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="50d9b-119">/ARGS &lt; command-ARGS&gt;</span><span class="sxs-lookup"><span data-stu-id="50d9b-119">/ARGS &lt;command-args&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="50d9b-120">要傳遞給應用程式的參數。</span><span class="sxs-lookup"><span data-stu-id="50d9b-120">Parameters to be passed to the application.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="50d9b-121">/LOG</span><span class="sxs-lookup"><span data-stu-id="50d9b-121">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="50d9b-122">如果已指定，輸出就會記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="50d9b-122">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="50d9b-123">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="50d9b-123">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="50d9b-124">如果已指定，輸出就會顯示在 active 主控台視窗中（預設）。</span><span class="sxs-lookup"><span data-stu-id="50d9b-124">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="50d9b-125">/GUI</span><span class="sxs-lookup"><span data-stu-id="50d9b-125">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="50d9b-126">如果已指定，輸出就會顯示在 Windows 對話方塊中。</span><span class="sxs-lookup"><span data-stu-id="50d9b-126">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="50d9b-127">針對版本4.6，新增了下列選項。</span><span class="sxs-lookup"><span data-stu-id="50d9b-127">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="50d9b-128">/LOGU</span><span class="sxs-lookup"><span data-stu-id="50d9b-128">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="50d9b-129">如果已指定，輸出會以 UNICODE 格式記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="50d9b-129">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="50d9b-130">相關主題</span><span class="sxs-lookup"><span data-stu-id="50d9b-130">Related topics</span></span>


[<span data-ttu-id="50d9b-131">SFTMIME 命令參考</span><span class="sxs-lookup"><span data-stu-id="50d9b-131">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





