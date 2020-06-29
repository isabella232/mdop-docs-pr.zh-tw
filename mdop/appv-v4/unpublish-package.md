---
title: UNPUBLISH PACKAGE
description: UNPUBLISH PACKAGE
author: dansimp
ms.assetid: 1651427c-72a5-4701-bb57-71e14a7a3803
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7704fb3ed03be4864a837767d9e890d28b63f175
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800758"
---
# <span data-ttu-id="5451e-103">UNPUBLISH PACKAGE</span><span class="sxs-lookup"><span data-stu-id="5451e-103">UNPUBLISH PACKAGE</span></span>


<span data-ttu-id="5451e-104">可讓您移除整個套件的快速鍵和檔案類型。</span><span class="sxs-lookup"><span data-stu-id="5451e-104">Enables you to remove the shortcuts and file types for an entire package.</span></span>

`SFTMIME UNPUBLISH PACKAGE:package-name [/CLEAR] [/GLOBAL]                 [/LOG log-pathname | /CONSOLE | /GUI]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5451e-105">參數</span><span class="sxs-lookup"><span data-stu-id="5451e-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="5451e-106">描述</span><span class="sxs-lookup"><span data-stu-id="5451e-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5451e-107">套件： &lt; 套件-名稱&gt;</span><span class="sxs-lookup"><span data-stu-id="5451e-107">PACKAGE:&lt;package-name&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="5451e-108">套件的名稱。</span><span class="sxs-lookup"><span data-stu-id="5451e-108">The name of the package.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5451e-109">/CLEAR</span><span class="sxs-lookup"><span data-stu-id="5451e-109">/CLEAR</span></span></p></td>
<td align="left"><p><span data-ttu-id="5451e-110">如果有的話，也會移除使用者設定。</span><span class="sxs-lookup"><span data-stu-id="5451e-110">If present, user settings will also be removed.</span></span> <span data-ttu-id="5451e-111">（如需詳細資訊，請參閱本主題稍後的重要記事。）</span><span class="sxs-lookup"><span data-stu-id="5451e-111">(For more information, see the Important note later in this topic.)</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5451e-112">/GLOBAL</span><span class="sxs-lookup"><span data-stu-id="5451e-112">/GLOBAL</span></span></p></td>
<td align="left"><p><span data-ttu-id="5451e-113">如果有，則會針對此電腦上的所有使用者取消發佈套件。</span><span class="sxs-lookup"><span data-stu-id="5451e-113">If present, the package will be unpublished for all users on this computer.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5451e-114">/LOG</span><span class="sxs-lookup"><span data-stu-id="5451e-114">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="5451e-115">如果已指定，輸出就會記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="5451e-115">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5451e-116">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="5451e-116">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="5451e-117">如果已指定，輸出就會顯示在 active 主控台視窗中（預設）。</span><span class="sxs-lookup"><span data-stu-id="5451e-117">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5451e-118">/GUI</span><span class="sxs-lookup"><span data-stu-id="5451e-118">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="5451e-119">如果已指定，輸出就會顯示在 Windows 對話方塊中。</span><span class="sxs-lookup"><span data-stu-id="5451e-119">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="5451e-120">針對版本4.6，新增了下列選項。</span><span class="sxs-lookup"><span data-stu-id="5451e-120">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5451e-121">/LOGU</span><span class="sxs-lookup"><span data-stu-id="5451e-121">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="5451e-122">如果已指定，輸出會以 UNICODE 格式記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="5451e-122">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="5451e-123">**重要** 您必須先將套件新增至應用程式虛擬化用戶端，才能執行 [**取消發佈套件**] 命令。</span><span class="sxs-lookup"><span data-stu-id="5451e-123">**Important** Before you can run the **UNPUBLISH PACKAGE** command, the package must already have been added to the Application Virtualization Client.</span></span>

<span data-ttu-id="5451e-124">若要使用**全域**，**取消發佈套件**必須以本機管理員身分執行;否則，只需要**ClearApp**許可權。</span><span class="sxs-lookup"><span data-stu-id="5451e-124">To use **GLOBAL**, **UNPUBLISH PACKAGE** must be run as local Administrator; otherwise, only **ClearApp** permission is needed.</span></span>

<span data-ttu-id="5451e-125">使用具有**全域**的**取消發佈套件**會移除套件的任何通用檔案類型和快速鍵。</span><span class="sxs-lookup"><span data-stu-id="5451e-125">Using **UNPUBLISH PACKAGE** with **GLOBAL** removes any global file types and shortcuts for the package.</span></span> <span data-ttu-id="5451e-126">[**清除**] 不適用。</span><span class="sxs-lookup"><span data-stu-id="5451e-126">**CLEAR** is not applicable.</span></span>

<span data-ttu-id="5451e-127">使用不含**全域**的**取消發佈套件**會移除套件的使用者快速鍵和檔案類型，如果已設定**CLEAR** ，也會在使用者的內容底下移除使用者設定並停止背景載入。</span><span class="sxs-lookup"><span data-stu-id="5451e-127">Using **UNPUBLISH PACKAGE** without **GLOBAL** removes the user shortcuts and file types for the package and, if **CLEAR** is set, also removes user settings and stops background loads under the user’s context.</span></span>

<span data-ttu-id="5451e-128">**取消發佈套件**適用于使用作為**新增**、**編輯**及**發佈套件**之來源 ID 之相同套件名稱或 GUID 的應用程式。</span><span class="sxs-lookup"><span data-stu-id="5451e-128">**UNPUBLISH PACKAGE** works on applications from the same package name or GUID that was used as the source ID for **ADD**, **EDIT**, and **PUBLISH PACKAGE**.</span></span>

<span data-ttu-id="5451e-129">無論使用/CLEAR 開關為何，**取消發佈套件**都會清除所有的使用者設定、快速鍵和檔案類型。</span><span class="sxs-lookup"><span data-stu-id="5451e-129">**UNPUBLISH PACKAGE** always clears all the user settings, shortcuts, and file types regardless of the use of the /CLEAR switch.</span></span>

 

## <span data-ttu-id="5451e-130">相關主題</span><span class="sxs-lookup"><span data-stu-id="5451e-130">Related topics</span></span>


[<span data-ttu-id="5451e-131">SFTMIME 命令參考</span><span class="sxs-lookup"><span data-stu-id="5451e-131">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





