---
title: CONFIGURE PACKAGE
description: CONFIGURE PACKAGE
author: dansimp
ms.assetid: acc7eaa8-6ada-47b9-a655-2ca2537605b9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dc8b315b68349cc9834316786b0bf15d4ac3c5cd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802181"
---
# <span data-ttu-id="c3683-103">CONFIGURE PACKAGE</span><span class="sxs-lookup"><span data-stu-id="c3683-103">CONFIGURE PACKAGE</span></span>


<span data-ttu-id="c3683-104">讓使用者能夠變更封裝資訊清單檔案、套件來源、載入觸發程式類型，或針對套件載入目標。</span><span class="sxs-lookup"><span data-stu-id="c3683-104">Enables the user to change a package manifest file, package source, load trigger types, or load target for a package.</span></span>

`SFTMIME CONFIGURE PACKAGE:package-name [/MANIFEST manifest-path]                 [/OVERRIDEURL url] [/AUTOLOADNEVER] [/AUTOLOADONREFRESH]                 [/AUTOLOADONLOGIN] [/AUTOLOADONLAUNCH]                 [/AUTOLOADTARGET {NONE|ALL|PREVUSED}]                 [/LOG log-pathname | /CONSOLE | /GUI]                 [/NO-UPDATE-FTA-SHORTCUT {TRUE|FALSE} {/GLOBAL}]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="c3683-105">參數</span><span class="sxs-lookup"><span data-stu-id="c3683-105">Parameter</span></span></th>
<th align="left"><span data-ttu-id="c3683-106">描述</span><span class="sxs-lookup"><span data-stu-id="c3683-106">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c3683-107">套件： &lt; 套件-名稱&gt;</span><span class="sxs-lookup"><span data-stu-id="c3683-107">PACKAGE:&lt;package-name&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="c3683-108">套件的使用者可見及方便使用名稱。</span><span class="sxs-lookup"><span data-stu-id="c3683-108">User-visible and user-friendly name for the package.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c3683-109">/MANIFEST &lt; 資訊清單-path&gt;</span><span class="sxs-lookup"><span data-stu-id="c3683-109">/MANIFEST &lt;manifest-path&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="c3683-110">列出套件中包含之應用程式的資訊清單檔案路徑或 URL，以及其所有發佈資訊。</span><span class="sxs-lookup"><span data-stu-id="c3683-110">The path or URL of the manifest file that lists the applications included in the package and all of their publishing information.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c3683-111">/OVERRIDEURL &lt; URL&gt;</span><span class="sxs-lookup"><span data-stu-id="c3683-111">/OVERRIDEURL &lt;URL&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="c3683-112">套件的 SFT 檔案位置。</span><span class="sxs-lookup"><span data-stu-id="c3683-112">The location of the package's SFT file.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c3683-113">/AUTOLOADNEVER</span><span class="sxs-lookup"><span data-stu-id="c3683-113">/AUTOLOADNEVER</span></span></p></td>
<td align="left"><p><span data-ttu-id="c3683-114">已針對套件關閉背景載入。</span><span class="sxs-lookup"><span data-stu-id="c3683-114">Background loading is turned off for the package.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c3683-115">/AUTOLOADONREFRESH</span><span class="sxs-lookup"><span data-stu-id="c3683-115">/AUTOLOADONREFRESH</span></span></p></td>
<td align="left"><p><span data-ttu-id="c3683-116">在發佈重新整理之後，會執行背景載入。</span><span class="sxs-lookup"><span data-stu-id="c3683-116">Background loading is performed after a publishing refresh.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c3683-117">/AUTOLOADONLOGIN</span><span class="sxs-lookup"><span data-stu-id="c3683-117">/AUTOLOADONLOGIN</span></span></p></td>
<td align="left"><p><span data-ttu-id="c3683-118">在使用者登入時，會執行背景載入。</span><span class="sxs-lookup"><span data-stu-id="c3683-118">Background loading is performed when a user logs in.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c3683-119">/AUTOLOADONLAUNCH</span><span class="sxs-lookup"><span data-stu-id="c3683-119">/AUTOLOADONLAUNCH</span></span></p></td>
<td align="left"><p><span data-ttu-id="c3683-120">使用者從套件啟動應用程式後，就會執行背景載入。</span><span class="sxs-lookup"><span data-stu-id="c3683-120">Background loading is performed after a user starts an application from the package.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c3683-121">/AUTOLOADTARGET &lt; 目標&gt;</span><span class="sxs-lookup"><span data-stu-id="c3683-121">/AUTOLOADTARGET &lt;target&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="c3683-122">指示將會 autoloaded 套件中的哪些應用程式。</span><span class="sxs-lookup"><span data-stu-id="c3683-122">Indicates which applications from the package will be autoloaded.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c3683-123">所有</span><span class="sxs-lookup"><span data-stu-id="c3683-123">NONE</span></span></p></td>
<td align="left"><p><span data-ttu-id="c3683-124">不論是否有任何/AUTOLOADONxxx 標誌，都不會執行任何 autoloading。</span><span class="sxs-lookup"><span data-stu-id="c3683-124">No autoloading will be performed despite the presence of any /AUTOLOADONxxx flags.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c3683-125">同時</span><span class="sxs-lookup"><span data-stu-id="c3683-125">ALL</span></span></p></td>
<td align="left"><p><span data-ttu-id="c3683-126">如果啟用 autoload 觸發程式，則無論是否已啟動，套件中的所有應用程式都會載入到快取中。</span><span class="sxs-lookup"><span data-stu-id="c3683-126">If an autoload trigger is enabled, all applications in the package will be loaded into cache regardless of whether they have ever been launched.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c3683-127">PREVUSED</span><span class="sxs-lookup"><span data-stu-id="c3683-127">PREVUSED</span></span></p></td>
<td align="left"><p><span data-ttu-id="c3683-128">如果啟用 autoload 觸發程式，則在使用者先前已啟動此套件中的任何應用程式時，就會載入套件。</span><span class="sxs-lookup"><span data-stu-id="c3683-128">If an autoload trigger is enabled, the package will load if any applications in this package have previously been started by a user.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c3683-129">/LOG</span><span class="sxs-lookup"><span data-stu-id="c3683-129">/LOG</span></span></p></td>
<td align="left"><p><span data-ttu-id="c3683-130">如果已指定，輸出就會記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="c3683-130">If specified, output is logged to the specified path name.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c3683-131">/CONSOLE</span><span class="sxs-lookup"><span data-stu-id="c3683-131">/CONSOLE</span></span></p></td>
<td align="left"><p><span data-ttu-id="c3683-132">如果已指定，輸出就會顯示在 active 主控台視窗中（預設）。</span><span class="sxs-lookup"><span data-stu-id="c3683-132">If specified, output is presented in the active console window (default).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c3683-133">/GUI</span><span class="sxs-lookup"><span data-stu-id="c3683-133">/GUI</span></span></p></td>
<td align="left"><p><span data-ttu-id="c3683-134">如果已指定，輸出就會顯示在 Windows 對話方塊中。</span><span class="sxs-lookup"><span data-stu-id="c3683-134">If specified, output is presented in a Windows dialog box.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="c3683-135">針對版本4.6，新增了下列選項。</span><span class="sxs-lookup"><span data-stu-id="c3683-135">For version4.6, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c3683-136">/LOGU</span><span class="sxs-lookup"><span data-stu-id="c3683-136">/LOGU</span></span></p></td>
<td align="left"><p><span data-ttu-id="c3683-137">如果已指定，輸出會以 UNICODE 格式記錄到指定的路徑名稱。</span><span class="sxs-lookup"><span data-stu-id="c3683-137">If specified, output is logged to the specified path name in UNICODE format.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="c3683-138">針對版本 4.6 SP2，新增了下列選項。</span><span class="sxs-lookup"><span data-stu-id="c3683-138">For version4.6 SP2, the following option has been added.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="c3683-139">[/NO-UPDATE-FTA-SHORTCUT {TRUE |FALSE} {/GLOBAL}]</span><span class="sxs-lookup"><span data-stu-id="c3683-139">[/NO-UPDATE-FTA-SHORTCUT {TRUE|FALSE} {/GLOBAL}]</span></span></p></td>
<td align="left"><p><span data-ttu-id="c3683-140">如果設為 TRUE，則會針對套件（每位使用者）或全域方式建立登錄值，如果已指定/GLOBAL 標誌。</span><span class="sxs-lookup"><span data-stu-id="c3683-140">If set to TRUE, a registry value is created for the package, either per user, or globally if the /GLOBAL flag is specified.</span></span></p>
<p><span data-ttu-id="c3683-141">如果設定為 FALSE，則會移除登錄值，並重新安裝套件的檔案類型關聯（FTA）。</span><span class="sxs-lookup"><span data-stu-id="c3683-141">If set to FALSE, the registry value is removed and the file type associations (FTA) for the package are reinstalled.</span></span></p>
<p><span data-ttu-id="c3683-142">如果未指定，就會發生標準 FTA 和快捷方式發佈行為。</span><span class="sxs-lookup"><span data-stu-id="c3683-142">If not specified, normal FTA and shortcut publishing behavior occurs.</span></span> <span data-ttu-id="c3683-143">如果您在 App-V 4.6 SP2 用戶端上執行任何後續的發佈重新整理作業，則不會變更已設定此登錄值之套件的快速鍵及 FTAs; 除非您重設旗標，否則就不會在系統啟動或使用者登入時註冊快速鍵及 FTAs。</span><span class="sxs-lookup"><span data-stu-id="c3683-143">If you perform any subsequent publishing refresh operations on the App-V 4.6 SP2 client, the shortcuts and FTAs for packages that have this registry value set will not be changed, and the shortcuts and FTAs will not be registered at system startup or user login unless you reset the flag.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="c3683-144">/GLOBAL</span><span class="sxs-lookup"><span data-stu-id="c3683-144">/GLOBAL</span></span></p></td>
<td align="left"><p><span data-ttu-id="c3683-145">與/NO-UPDATE-FTA-SHORTCUT 標誌搭配使用。</span><span class="sxs-lookup"><span data-stu-id="c3683-145">Works in conjunction with the /NO-UPDATE-FTA-SHORTCUT flag.</span></span> <span data-ttu-id="c3683-146">如果/GLOBAL 標誌存在，則表示將為所有使用者建立該套件的登錄值。</span><span class="sxs-lookup"><span data-stu-id="c3683-146">If the /GLOBAL flag is present, it indicates that a registry value will be created for that package for all users.</span></span> <span data-ttu-id="c3683-147">根據預設，只會針對此使用者建立登錄值。</span><span class="sxs-lookup"><span data-stu-id="c3683-147">By default, the registry value is created only for this user.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="c3683-148">相關主題</span><span class="sxs-lookup"><span data-stu-id="c3683-148">Related topics</span></span>


[<span data-ttu-id="c3683-149">SFTMIME 命令參考</span><span class="sxs-lookup"><span data-stu-id="c3683-149">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





