---
title: QUERY OBJ
description: QUERY OBJ
author: dansimp
ms.assetid: 55abf0d1-c779-4172-8357-552ab010933b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 328e9feb96c70080531cbbc666d8ff1b86045ba5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800879"
---
# <span data-ttu-id="e7de3-103">QUERY OBJ</span><span class="sxs-lookup"><span data-stu-id="e7de3-103">QUERY OBJ</span></span>


<span data-ttu-id="e7de3-104">傳回目前應用程式、套件、檔案類型關聯或發佈伺服器的 tab 分隔清單。</span><span class="sxs-lookup"><span data-stu-id="e7de3-104">Returns a tab-delimited list of current applications, packages, file type associations, or publishing servers.</span></span>

`SFTMIME QUERY OBJ:{APP|PACKAGE|TYPE|SERVER} [/SHORT] [/GLOBAL]                 [/LOG log-pathname | /CONSOLE ]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e7de3-105">參數</span><span class="sxs-lookup"><span data-stu-id="e7de3-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="e7de3-106">描述</span><span class="sxs-lookup"><span data-stu-id="e7de3-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e7de3-107">適用</span><span class="sxs-lookup"><span data-stu-id="e7de3-107">APP</span></span></p></td>
<td align="left"><p><span data-ttu-id="e7de3-108">傳回應用程式的清單。</span><span class="sxs-lookup"><span data-stu-id="e7de3-108">Returns a list of applications.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e7de3-109">套件</span><span class="sxs-lookup"><span data-stu-id="e7de3-109">PACKAGE</span></span></p></td>
<td align="left"><p><span data-ttu-id="e7de3-110">傳回套件清單。</span><span class="sxs-lookup"><span data-stu-id="e7de3-110">Returns a list of packages.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e7de3-111">TYPE</span><span class="sxs-lookup"><span data-stu-id="e7de3-111">TYPE</span></span></p></td>
<td align="left"><p><span data-ttu-id="e7de3-112">傳回檔案類型關聯性清單。</span><span class="sxs-lookup"><span data-stu-id="e7de3-112">Returns a list of file type associations.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e7de3-113">伺服器</span><span class="sxs-lookup"><span data-stu-id="e7de3-113">SERVER</span></span></p></td>
<td align="left"><p><span data-ttu-id="e7de3-114">傳回發佈伺服器的清單。</span><span class="sxs-lookup"><span data-stu-id="e7de3-114">Returns a list of publishing servers.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e7de3-115">/SHORT</span><span class="sxs-lookup"><span data-stu-id="e7de3-115">/SHORT</span></span></p></td>
<td align="left"><p><span data-ttu-id="e7de3-116">若不顯示每個屬性的完整屬性，則會傳回應用程式名稱、套件、關聯或伺服器名稱的清單。</span><span class="sxs-lookup"><span data-stu-id="e7de3-116">Without displaying the full properties of each, returns a list of application names, packages, associations, or server names.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e7de3-117">/GLOBAL</span><span class="sxs-lookup"><span data-stu-id="e7de3-117">/GLOBAL</span></span></p></td>
<td align="left"><p><span data-ttu-id="e7de3-118">針對應用程式，傳回所有已知的應用程式，而不是目前使用者有權存取的那些應用程式。</span><span class="sxs-lookup"><span data-stu-id="e7de3-118">For applications, returns all known applications instead of only the ones the current user has access to.</span></span> <span data-ttu-id="e7de3-119">針對套件，傳回所有已知的套件，而不是目前使用者有權存取的套件。</span><span class="sxs-lookup"><span data-stu-id="e7de3-119">For packages, returns all known packages instead of only the ones the current user has access to.</span></span> <span data-ttu-id="e7de3-120">針對關聯，只會傳回適用于所有使用者的關聯，而不會傳回使用者特定的關聯。</span><span class="sxs-lookup"><span data-stu-id="e7de3-120">For associations, returns only associations that apply to all users, not user-specific ones.</span></span> <span data-ttu-id="e7de3-121">伺服器無效。</span><span class="sxs-lookup"><span data-stu-id="e7de3-121">Not valid for servers.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e7de3-122">/LOG</span><span class="sxs-lookup"><span data-stu-id="e7de3-122">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="e7de3-123">如果已指定，輸出就會記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="e7de3-123">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e7de3-124">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="e7de3-124">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="e7de3-125">如果已指定，輸出就會顯示在 active 主控台視窗中（預設）。</span><span class="sxs-lookup"><span data-stu-id="e7de3-125">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="e7de3-126">針對版本4.6，新增了下列選項。</span><span class="sxs-lookup"><span data-stu-id="e7de3-126">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e7de3-127">/LOGU</span><span class="sxs-lookup"><span data-stu-id="e7de3-127">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="e7de3-128">如果已指定，輸出會以 UNICODE 格式記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="e7de3-128">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="e7de3-129">**記事** 在版本4.6 中，已將新資料行新增至 SFTMIME 查詢 OBJ： APP \ [/GLOBAL\] 的輸出。</span><span class="sxs-lookup"><span data-stu-id="e7de3-129">**Note** In version 4.6, a new column has been added to the output of SFTMIME QUERY OBJ:APP \[/GLOBAL\].</span></span> <span data-ttu-id="e7de3-130">輸出的最後一欄是指示是否已發佈應用程式的數值。</span><span class="sxs-lookup"><span data-stu-id="e7de3-130">The last column of the output is a numeric value that indicates whether an application is published or not.</span></span>

<span data-ttu-id="e7de3-131">已發佈 = 1 表示應用程式是由發佈伺服器更新所發佈，方法是使用 Windows 安裝程式檔案（。MSI），或執行 SFTMIME [新增套件]，使用套件資訊清單設定套件或發佈套件命令。</span><span class="sxs-lookup"><span data-stu-id="e7de3-131">PUBLISHED=1 means the application was published by a Publishing Server refresh, by installing the application by using a Windows Installer file (.MSI), or by running an SFTMIME ADD PACKAGE, CONFIGURE PACKAGE or PUBLISH PACKAGE command by using a package manifest.</span></span>

<span data-ttu-id="e7de3-132">已發佈 = 0 表示應用程式尚未發佈，或是執行 [清除] 作業或執行 SFTMIME 取消發佈命令之後，就不會再發佈。</span><span class="sxs-lookup"><span data-stu-id="e7de3-132">PUBLISHED=0 means the application has not been published or it is no longer published as a result of performing a Clear operation or running an SFTMIME UNPUBLISH command.</span></span>

<span data-ttu-id="e7de3-133">如果您使用/GLOBAL 參數，發佈的狀態將為1，適用于全域發佈的應用程式，而在使用者上下文中發佈的應用程式則為0。</span><span class="sxs-lookup"><span data-stu-id="e7de3-133">If you use the /GLOBAL parameter, the PUBLISHED state will be 1 for applications that were published globally and 0 for those applications that were published under user contexts.</span></span> <span data-ttu-id="e7de3-134">如果沒有/GLOBAL 參數，則會針對執行命令之使用者的內容所發佈的應用程式傳回1的已發佈狀態，而針對全域發佈的應用程式傳回0的狀態。</span><span class="sxs-lookup"><span data-stu-id="e7de3-134">Without the /GLOBAL parameter, a PUBLISHED state of 1 is returned for applications published in the context of the user running the command, and a state of 0 is returned for those applications that are published globally.</span></span>

 

<span data-ttu-id="e7de3-135">SFTMIME 查詢 OBJ 命令可用來查詢上述所有物件（應用程式、套件、檔案類型關聯及伺服器）的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="e7de3-135">The SFTMIME QUERY OBJ command can be used to query for information on all of the objects shown above—applications, packages, file type associations, and servers.</span></span><span data-ttu-id="e7de3-136">若要示範您可以如何在一般作業工作中使用 SFTMIME QUERY OBJ 命令，下列範例會示範在您想要設定特定套件的 OVERRIDEURL 參數值來指定套件內容的新路徑時所遵循的處理常式。</span><span class="sxs-lookup"><span data-stu-id="e7de3-136">To show how you might use the SFTMIME QUERY OBJ command in your normal operations tasks, the following example demonstrates the process you would follow if you wanted to set the OVERRIDEURL parameter value for a specific package to specify a new path to the package content.</span></span> 

1.  <span data-ttu-id="e7de3-137">若要尋找您要設定的套件，請執行下列命令：</span><span class="sxs-lookup"><span data-stu-id="e7de3-137">To find the package that you want to configure, run the following command:</span></span>

    `SFTMIME QUERY OBJ:PACKAGE`

    <span data-ttu-id="e7de3-138">這個命令會將每個發現的套件名稱傳回為輸出第一欄中的 GUID （例如，{AF78ABE1-57D4-4297-89DE-C308684AEDD6}）。</span><span class="sxs-lookup"><span data-stu-id="e7de3-138">This command returns each discovered package name as a GUID in the first column of output—for example, {AF78ABE1-57D4-4297-89DE-C308684AEDD6}.</span></span>

2.  <span data-ttu-id="e7de3-139">若要設定 OVERRIDEURL 參數值，您可以使用 SFTMIME [[設定套件](configure-package.md)] 命令。</span><span class="sxs-lookup"><span data-stu-id="e7de3-139">To set the OVERRIDEURL parameter value, you use the SFTMIME [CONFIGURE PACKAGE](configure-package.md) command.</span></span> <span data-ttu-id="e7de3-140">例如，若要將這個套件的 OVERRIDEURL 值設為*\\\\server\\share\\mypackage.sft*的值，請使用 SFTMIME 的 [設定套件] 命令，然後從步驟1的 SFTMIME 查詢 OBJ 命令輸出中，為其指定套件 GUID，後面接著是 OVERRIDEURL 參數及其新值，如下所示：</span><span class="sxs-lookup"><span data-stu-id="e7de3-140">For example, to set the OVERRIDEURL value for this package to a value of *\\\\server\\share\\mypackage.sft*, use the SFTMIME CONFIGURE PACKAGE command and give it the selected package GUID from the output of the SFTMIME QUERY OBJ command in step 1, followed by the OVERRIDEURL parameter and its new value, as follows:</span></span>

    `SFTMIME CONFIGURE PACKAGE:"{AF78ABE1-57D4-4297-89DE-C308684AEDD6}" /OVERRIDEURL "\\\\server\\share\\mypackage.sft "`

<span data-ttu-id="e7de3-141">針對版本 4.6 SP2，新增了下列選項。</span><span class="sxs-lookup"><span data-stu-id="e7de3-141">For version4.6 SP2, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e7de3-142">/NO-UPDATE-FTA-SHORTCUT</span><span class="sxs-lookup"><span data-stu-id="e7de3-142">/NO-UPDATE-FTA-SHORTCUT</span></span></p></td>
<td align="left"><p><span data-ttu-id="e7de3-143">指示/NO-UPDATE-FTA-SHORTCUT 旗標的目前狀態。</span><span class="sxs-lookup"><span data-stu-id="e7de3-143">Indicates the current state of the /NO-UPDATE-FTA-SHORTCUT flag.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="e7de3-144">相關主題</span><span class="sxs-lookup"><span data-stu-id="e7de3-144">Related topics</span></span>


[<span data-ttu-id="e7de3-145">SFTMIME 命令參考</span><span class="sxs-lookup"><span data-stu-id="e7de3-145">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





