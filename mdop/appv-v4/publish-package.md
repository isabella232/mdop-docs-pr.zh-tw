---
title: PUBLISH PACKAGE
description: PUBLISH PACKAGE
author: dansimp
ms.assetid: a33e72dd-194f-4283-8e99-4584ab13de53
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 00b63389986f495d9405939245a50575bae453f9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800894"
---
# <span data-ttu-id="1f744-103">PUBLISH PACKAGE</span><span class="sxs-lookup"><span data-stu-id="1f744-103">PUBLISH PACKAGE</span></span>


<span data-ttu-id="1f744-104">發佈整個套件的內容。</span><span class="sxs-lookup"><span data-stu-id="1f744-104">Publishes the contents of an entire package.</span></span>

`SFTMIME PUBLISH PACKAGE:package-name /MANIFEST manifest-path [/GLOBAL]                 [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="1f744-105">參數</span><span class="sxs-lookup"><span data-stu-id="1f744-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="1f744-106">描述</span><span class="sxs-lookup"><span data-stu-id="1f744-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1f744-107">套件： &lt; 套件-名稱&gt;</span><span class="sxs-lookup"><span data-stu-id="1f744-107">PACKAGE:&lt;package-name&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="1f744-108">套件的使用者可見及方便使用名稱。</span><span class="sxs-lookup"><span data-stu-id="1f744-108">User-visible and user-friendly name for the package.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1f744-109">/MANIFEST &lt; 資訊清單-path&gt;</span><span class="sxs-lookup"><span data-stu-id="1f744-109">/MANIFEST &lt;manifest-path&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="1f744-110">列出套件中包含之應用程式的資訊清單檔案路徑或 URL，以及其所有發佈資訊。</span><span class="sxs-lookup"><span data-stu-id="1f744-110">The path or URL of the manifest file that lists the applications included in the package and all of their publishing information.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1f744-111">/GLOBAL</span><span class="sxs-lookup"><span data-stu-id="1f744-111">/GLOBAL</span></span></p></td>
<td align="left"><p><span data-ttu-id="1f744-112">如果有的話，此電腦上的所有使用者都可以使用套件。</span><span class="sxs-lookup"><span data-stu-id="1f744-112">If present, the package will be available for all users on this computer.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1f744-113">/LOG</span><span class="sxs-lookup"><span data-stu-id="1f744-113">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="1f744-114">如果已指定，輸出就會記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="1f744-114">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1f744-115">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="1f744-115">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="1f744-116">如果已指定，輸出就會顯示在 active 主控台視窗中（預設）。</span><span class="sxs-lookup"><span data-stu-id="1f744-116">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="1f744-117">/GUI</span><span class="sxs-lookup"><span data-stu-id="1f744-117">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="1f744-118">如果已指定，輸出就會顯示在 Windows 對話方塊中。</span><span class="sxs-lookup"><span data-stu-id="1f744-118">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="1f744-119">針對版本4.6，新增了下列選項。</span><span class="sxs-lookup"><span data-stu-id="1f744-119">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="1f744-120">/LOGU</span><span class="sxs-lookup"><span data-stu-id="1f744-120">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="1f744-121">如果已指定，輸出會以 UNICODE 格式記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="1f744-121">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="1f744-122">**重要** 套件必須已新增至應用程式虛擬化用戶端，且需要資訊清單檔案。</span><span class="sxs-lookup"><span data-stu-id="1f744-122">**Important** The package must already have been added to the Application Virtualization Client, and the manifest file is required.</span></span>

<span data-ttu-id="1f744-123">若要使用**GLOBAL**參數，必須以本機管理員身分執行 [發佈套件] 命令;否則，只需要**ManageTypes**和**PublishShortcut**許可權。</span><span class="sxs-lookup"><span data-stu-id="1f744-123">To use the **GLOBAL** parameter, the PUBLISH PACKAGE command must be run as local Administrator; otherwise, only **ManageTypes** and **PublishShortcut** permissions are needed.</span></span>

<span data-ttu-id="1f744-124">不使用**GLOBAL**參數的發佈可授予使用者對封裝中應用程式的存取權，並將資訊清單中列出的檔案類型和快速鍵發佈至使用者的設定檔。</span><span class="sxs-lookup"><span data-stu-id="1f744-124">Publishing without the **GLOBAL** parameter grants the user access to the applications in the package and publishes the file types and shortcuts listed in the manifest to the user’s profile.</span></span>

<span data-ttu-id="1f744-125">使用**GLOBAL**參數發佈時，會將資訊清單中列出的檔案類型和快速鍵新增至 [所有使用者] 設定檔。</span><span class="sxs-lookup"><span data-stu-id="1f744-125">Publishing with the **GLOBAL** parameter adds the file types and shortcuts listed in the manifest to the “All Users” profile.</span></span>

<span data-ttu-id="1f744-126">如果在通話之前不是全域套件，且使用了**全域**參數，則會將套件設為全域，且可供所有使用者使用。</span><span class="sxs-lookup"><span data-stu-id="1f744-126">If the package is not global before the call and the **GLOBAL** parameter is used, the package is made global and available to all users.</span></span>

 

## <span data-ttu-id="1f744-127">相關主題</span><span class="sxs-lookup"><span data-stu-id="1f744-127">Related topics</span></span>


[<span data-ttu-id="1f744-128">SFTMIME 命令參考</span><span class="sxs-lookup"><span data-stu-id="1f744-128">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





