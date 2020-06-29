---
title: 如何使用 PowerShell 來管理獨立電腦上執行的 App-V 5.1 封裝
description: 如何使用 PowerShell 來管理獨立電腦上執行的 App-V 5.1 封裝
author: dansimp
ms.assetid: c3fd06f6-102f-43d1-a577-d5ced6ac537d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: b454014da4e5f349af913d3fea8ea3837598a039
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800463"
---
# <span data-ttu-id="51948-103">如何使用 PowerShell 來管理獨立電腦上執行的 App-V 5.1 封裝</span><span class="sxs-lookup"><span data-stu-id="51948-103">How to Manage App-V 5.1 Packages Running on a Stand-Alone Computer by Using PowerShell</span></span>


<span data-ttu-id="51948-104">下列各節說明如何使用 PowerShell 在獨立用戶端電腦上執行各種管理工作：</span><span class="sxs-lookup"><span data-stu-id="51948-104">The following sections explain how to perform various management tasks on a stand-alone client computer by using PowerShell:</span></span>

-   [<span data-ttu-id="51948-105">若要傳回套件清單</span><span class="sxs-lookup"><span data-stu-id="51948-105">To return a list of packages</span></span>](#bkmk-return-pkgs-standalone-posh)

-   [<span data-ttu-id="51948-106">若要新增套件</span><span class="sxs-lookup"><span data-stu-id="51948-106">To add a package</span></span>](#bkmk-add-pkgs-standalone-posh)

-   [<span data-ttu-id="51948-107">發佈套件</span><span class="sxs-lookup"><span data-stu-id="51948-107">To publish a package</span></span>](#bkmk-pub-pkg-standalone-posh)

-   [<span data-ttu-id="51948-108">將套件發佈至特定使用者</span><span class="sxs-lookup"><span data-stu-id="51948-108">To publish a package to a specific user</span></span>](#bkmk-pub-pkg-a-user-standalone-posh)

-   [<span data-ttu-id="51948-109">新增及發佈套件</span><span class="sxs-lookup"><span data-stu-id="51948-109">To add and publish a package</span></span>](#bkmk-add-pub-pkg-standalone-posh)

-   [<span data-ttu-id="51948-110">取消發佈現有的套件</span><span class="sxs-lookup"><span data-stu-id="51948-110">To unpublish an existing package</span></span>](#bkmk-unpub-pkg-standalone-posh)

-   [<span data-ttu-id="51948-111">針對特定使用者取消發佈套件</span><span class="sxs-lookup"><span data-stu-id="51948-111">To unpublish a package for a specific user</span></span>](#bkmk-unpub-pkg-specfc-use)

-   [<span data-ttu-id="51948-112">移除現有的套件</span><span class="sxs-lookup"><span data-stu-id="51948-112">To remove an existing package</span></span>](#bkmk-remove-pkg-standalone-posh)

-   [<span data-ttu-id="51948-113">僅允許系統管理員發佈或取消發佈套件</span><span class="sxs-lookup"><span data-stu-id="51948-113">To enable only administrators to publish or unpublish packages</span></span>](#bkmk-admins-pub-pkgs)

-   [<span data-ttu-id="51948-114">瞭解擱置的套件（UserPending 和 GlobalPending）</span><span class="sxs-lookup"><span data-stu-id="51948-114">Understanding pending packages (UserPending and GlobalPending)</span></span>](#bkmk-understd-pend-pkgs)

## <a href="" id="bkmk-return-pkgs-standalone-posh"></a><span data-ttu-id="51948-115">若要傳回套件清單</span><span class="sxs-lookup"><span data-stu-id="51948-115">To return a list of packages</span></span>


<span data-ttu-id="51948-116">使用下列資訊傳回有資格給特定使用者的套件清單：</span><span class="sxs-lookup"><span data-stu-id="51948-116">Use the following information to return a list of packages that are entitled to a specific user:</span></span>

<span data-ttu-id="51948-117">**Cmdlet**： AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="51948-117">**Cmdlet**: Get-AppvClientPackage</span></span>

<span data-ttu-id="51948-118">**參數**：-Name-Version-PackageID-VersionID</span><span class="sxs-lookup"><span data-stu-id="51948-118">**Parameters**: -Name -Version -PackageID -VersionID</span></span>

<span data-ttu-id="51948-119">**範例**： AppvClientPackage – Name "ContosoApplication"-版本2</span><span class="sxs-lookup"><span data-stu-id="51948-119">**Example**: Get-AppvClientPackage –Name “ContosoApplication” -Version 2</span></span>

## <a href="" id="bkmk-add-pkgs-standalone-posh"></a><span data-ttu-id="51948-120">若要新增套件</span><span class="sxs-lookup"><span data-stu-id="51948-120">To add a package</span></span>


<span data-ttu-id="51948-121">使用下列資訊將套件新增到電腦。</span><span class="sxs-lookup"><span data-stu-id="51948-121">Use the following information to add a package to a computer.</span></span>

<span data-ttu-id="51948-122">**重要** 這個範例只會新增套件。</span><span class="sxs-lookup"><span data-stu-id="51948-122">**Important** This example only adds a package.</span></span> <span data-ttu-id="51948-123">它不會將套件發佈至使用者或電腦。</span><span class="sxs-lookup"><span data-stu-id="51948-123">It does not publish the package to the user or the computer.</span></span>

 

<span data-ttu-id="51948-124">**Cmdlet**： Add-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="51948-124">**Cmdlet**: Add-AppvClientPackage</span></span>

<span data-ttu-id="51948-125">**範例**： $Contoso = Add-AppvClientPackage \\\\path\\to\\appv\\package.appv</span><span class="sxs-lookup"><span data-stu-id="51948-125">**Example**: $Contoso = Add-AppvClientPackage \\\\path\\to\\appv\\package.appv</span></span>

## <a href="" id="bkmk-pub-pkg-standalone-posh"></a><span data-ttu-id="51948-126">發佈套件</span><span class="sxs-lookup"><span data-stu-id="51948-126">To publish a package</span></span>


<span data-ttu-id="51948-127">使用下列資訊發佈已新增至特定使用者或全域至電腦上任何使用者的套件。</span><span class="sxs-lookup"><span data-stu-id="51948-127">Use the following information to publish a package that has been added to a specific user or globally to any user on the computer.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="51948-128">發佈方法</span><span class="sxs-lookup"><span data-stu-id="51948-128">Publishing method</span></span></th>
<th align="left"><span data-ttu-id="51948-129">Cmdlet 與範例</span><span class="sxs-lookup"><span data-stu-id="51948-129">Cmdlet and example</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="51948-130">發佈至使用者</span><span class="sxs-lookup"><span data-stu-id="51948-130">Publishing to the user</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="51948-131">Cmdlet </strong> ： Publish-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="51948-131">Cmdlet</strong>: Publish-AppvClientPackage</span></span></p>
<p><strong><span data-ttu-id="51948-132">範例 </strong> ： Publish-AppvClientPackage "ContosoApplication"</span><span class="sxs-lookup"><span data-stu-id="51948-132">Example</strong>: Publish-AppvClientPackage “ContosoApplication”</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="51948-133">全域發佈</span><span class="sxs-lookup"><span data-stu-id="51948-133">Publishing globally</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="51948-134">Cmdlet </strong> ： Publish-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="51948-134">Cmdlet</strong>: Publish-AppvClientPackage</span></span></p>
<p><strong><span data-ttu-id="51948-135">範例 </strong> ： Publish-AppvClientPackage "ContosoApplication"-全域</span><span class="sxs-lookup"><span data-stu-id="51948-135">Example</strong>: Publish-AppvClientPackage “ContosoApplication” -Global</span></span></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-pub-pkg-a-user-standalone-posh"></a><span data-ttu-id="51948-136">將套件發佈至特定使用者</span><span class="sxs-lookup"><span data-stu-id="51948-136">To publish a package to a specific user</span></span>


<span data-ttu-id="51948-137">**記事** 您必須使用 App-v 5.0 SP2 修補程式套件5或更新版本，才能使用這個參數。</span><span class="sxs-lookup"><span data-stu-id="51948-137">**Note** You must use App-V 5.0 SP2 Hotfix Package 5 or later to use this parameter.</span></span>

 

<span data-ttu-id="51948-138">系統管理員可以將套件發佈至特定的使用者，方法是使用**publish-AppvClientPackage** Cmdlet 指定 Optional （ **UserSID** ）參數，其中 **-UserSID**代表使用者的安全性識別碼（SID）。</span><span class="sxs-lookup"><span data-stu-id="51948-138">An administrator can publish a package to a specific user by specifying the optional **–UserSID** parameter with the **Publish-AppvClientPackage** cmdlet, where **-UserSID** represents the end user’s security identifier (SID).</span></span>

<span data-ttu-id="51948-139">若要使用此參數：</span><span class="sxs-lookup"><span data-stu-id="51948-139">To use this parameter:</span></span>

-   <span data-ttu-id="51948-140">您可以從使用者或系統管理員會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="51948-140">You can run this cmdlet from the user or administrator session.</span></span>

-   <span data-ttu-id="51948-141">您必須以管理認證登入，才能使用此參數。</span><span class="sxs-lookup"><span data-stu-id="51948-141">You must be logged in with administrative credentials to use the parameter.</span></span>

-   <span data-ttu-id="51948-142">最終使用者必須登入。</span><span class="sxs-lookup"><span data-stu-id="51948-142">The end user must be logged in.</span></span>

-   <span data-ttu-id="51948-143">您必須提供最終使用者的安全識別碼（SID）。</span><span class="sxs-lookup"><span data-stu-id="51948-143">You must provide the end user’s security identifier (SID).</span></span>

<span data-ttu-id="51948-144">**Cmdlet**： Publish-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="51948-144">**Cmdlet**: Publish-AppvClientPackage</span></span>

<span data-ttu-id="51948-145">**範例**： Publish-AppvClientPackage "ContosoApplication"-UserSID S-1-2-34-56789012-3456789012-345678901-2345</span><span class="sxs-lookup"><span data-stu-id="51948-145">**Example**: Publish-AppvClientPackage “ContosoApplication” -UserSID S-1-2-34-56789012-3456789012-345678901-2345</span></span>

## <a href="" id="bkmk-add-pub-pkg-standalone-posh"></a><span data-ttu-id="51948-146">新增及發佈套件</span><span class="sxs-lookup"><span data-stu-id="51948-146">To add and publish a package</span></span>


<span data-ttu-id="51948-147">使用下列資訊將套件新增到電腦，並將其發佈給使用者。</span><span class="sxs-lookup"><span data-stu-id="51948-147">Use the following information to add a package to a computer and publish it to the user.</span></span>

<span data-ttu-id="51948-148">**Cmdlet**： Add-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="51948-148">**Cmdlet**: Add-AppvClientPackage</span></span>

<span data-ttu-id="51948-149">**範例**： Add-AppvClientPackage \\\\path\\to\\appv\\package.appv |發佈-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="51948-149">**Example**: Add-AppvClientPackage \\\\path\\to\\appv\\package.appv | Publish-AppvClientPackage</span></span>

## <a href="" id="bkmk-unpub-pkg-standalone-posh"></a><span data-ttu-id="51948-150">取消發佈現有的套件</span><span class="sxs-lookup"><span data-stu-id="51948-150">To unpublish an existing package</span></span>


<span data-ttu-id="51948-151">使用下列資訊來取消發佈已有資格給使用者但無法從電腦移除套件的套件。</span><span class="sxs-lookup"><span data-stu-id="51948-151">Use the following information to unpublish a package which has been entitled to a user but not remove the package from the computer.</span></span>

<span data-ttu-id="51948-152">**Cmdlet**：取消發佈-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="51948-152">**Cmdlet**: Unpublish-AppvClientPackage</span></span>

<span data-ttu-id="51948-153">**範例**：取消發佈-AppvClientPackage "ContosoApplication"</span><span class="sxs-lookup"><span data-stu-id="51948-153">**Example**: Unpublish-AppvClientPackage “ContosoApplication”</span></span>

## <a href="" id="bkmk-unpub-pkg-specfc-use"></a><span data-ttu-id="51948-154">針對特定使用者取消發佈套件</span><span class="sxs-lookup"><span data-stu-id="51948-154">To unpublish a package for a specific user</span></span>


<span data-ttu-id="51948-155">**記事** 您必須使用 App-v 5.0 SP2 修補程式套件5或更新版本，才能使用這個參數。</span><span class="sxs-lookup"><span data-stu-id="51948-155">**Note** You must use App-V 5.0 SP2 Hotfix Package 5 or later to use this parameter.</span></span>

 

<span data-ttu-id="51948-156">系統管理員可以使用選擇性的 **– UserSID**參數和**AppvClientPackage** Cmdlet 來取消發佈特定使用者的套件，其中 **-UserSID**代表使用者的安全性識別碼（SID）。</span><span class="sxs-lookup"><span data-stu-id="51948-156">An administrator can unpublish a package for a specific user by using the optional **–UserSID** parameter with the **Unpublish-AppvClientPackage** cmdlet, where **-UserSID** represents the end user’s security identifier (SID).</span></span>

<span data-ttu-id="51948-157">若要使用此參數：</span><span class="sxs-lookup"><span data-stu-id="51948-157">To use this parameter:</span></span>

-   <span data-ttu-id="51948-158">您可以從使用者或系統管理員會話執行此 Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="51948-158">You can run this cmdlet from the user or administrator session.</span></span>

-   <span data-ttu-id="51948-159">您必須以管理認證登入，才能使用此參數。</span><span class="sxs-lookup"><span data-stu-id="51948-159">You must be logged in with administrative credentials to use the parameter.</span></span>

-   <span data-ttu-id="51948-160">最終使用者必須登入。</span><span class="sxs-lookup"><span data-stu-id="51948-160">The end user must be logged in.</span></span>

-   <span data-ttu-id="51948-161">您必須提供最終使用者的安全識別碼（SID）。</span><span class="sxs-lookup"><span data-stu-id="51948-161">You must provide the end user’s security identifier (SID).</span></span>

<span data-ttu-id="51948-162">**Cmdlet**：取消發佈-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="51948-162">**Cmdlet**: Unpublish-AppvClientPackage</span></span>

<span data-ttu-id="51948-163">**範例**：取消發佈-AppvClientPackage "ContosoApplication"-UserSID S-1-2-34-56789012-3456789012-345678901-2345</span><span class="sxs-lookup"><span data-stu-id="51948-163">**Example**: Unpublish-AppvClientPackage “ContosoApplication” -UserSID S-1-2-34-56789012-3456789012-345678901-2345</span></span>

## <a href="" id="bkmk-remove-pkg-standalone-posh"></a><span data-ttu-id="51948-164">移除現有的套件</span><span class="sxs-lookup"><span data-stu-id="51948-164">To remove an existing package</span></span>


<span data-ttu-id="51948-165">使用下列資訊從電腦中移除套件。</span><span class="sxs-lookup"><span data-stu-id="51948-165">Use the following information to remove a package from the computer.</span></span>

<span data-ttu-id="51948-166">**Cmdlet**： Remove-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="51948-166">**Cmdlet**: Remove-AppvClientPackage</span></span>

<span data-ttu-id="51948-167">**範例**： Remove-AppvClientPackage "ContosoApplication"</span><span class="sxs-lookup"><span data-stu-id="51948-167">**Example**: Remove-AppvClientPackage “ContosoApplication”</span></span>

<span data-ttu-id="51948-168">**記事** 出於明確起見，前幾個範例的 App-V Cmdlet 已指派給變數;不需要作業。</span><span class="sxs-lookup"><span data-stu-id="51948-168">**Note** App-V cmdlets have been assigned to variables for the previous examples for clarity only; assignment is not a requirement.</span></span> <span data-ttu-id="51948-169">大多數的 Cmdlet 可以結合顯示在中，[以新增及發佈套件](#bkmk-add-pub-pkg-standalone-posh)。</span><span class="sxs-lookup"><span data-stu-id="51948-169">Most cmdlets can be combined as displayed in [To add and publish a package](#bkmk-add-pub-pkg-standalone-posh).</span></span> <span data-ttu-id="51948-170">如需詳細教學課程，請參閱[app-v 5.0 Client PowerShell 深入探索](https://go.microsoft.com/fwlink/?LinkId=324466)。</span><span class="sxs-lookup"><span data-stu-id="51948-170">For a detailed tutorial, see [App-V 5.0 Client PowerShell Deep Dive](https://go.microsoft.com/fwlink/?LinkId=324466).</span></span>

 

## <a href="" id="bkmk-admins-pub-pkgs"></a><span data-ttu-id="51948-171">僅允許系統管理員發佈或取消發佈套件</span><span class="sxs-lookup"><span data-stu-id="51948-171">To enable only administrators to publish or unpublish packages</span></span>


<span data-ttu-id="51948-172">**記事** 
**從 app-v 5.0 SP3 開始，支援這項功能。**</span><span class="sxs-lookup"><span data-stu-id="51948-172">**Note**
**This feature is supported starting in App-V 5.0 SP3.**</span></span>

 

<span data-ttu-id="51948-173">使用下列 Cmdlet 和參數，僅允許系統管理員（而非最終使用者）發佈或取消發佈套件：</span><span class="sxs-lookup"><span data-stu-id="51948-173">Use the following cmdlet and parameter to enable only administrators (not end users) to publish or unpublish packages:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="51948-174">Cmdlet</span><span class="sxs-lookup"><span data-stu-id="51948-174">Cmdlet</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="51948-175">Set-AppvClientConfiguration</span><span class="sxs-lookup"><span data-stu-id="51948-175">Set-AppvClientConfiguration</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="51948-176">參數</span><span class="sxs-lookup"><span data-stu-id="51948-176">Parameter</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="51948-177">-RequirePublishAsAdmin</span><span class="sxs-lookup"><span data-stu-id="51948-177">-RequirePublishAsAdmin</span></span></p>
<p><span data-ttu-id="51948-178">參數值：</span><span class="sxs-lookup"><span data-stu-id="51948-178">Parameter values:</span></span></p>
<ul>
<li><p><span data-ttu-id="51948-179">0-False</span><span class="sxs-lookup"><span data-stu-id="51948-179">0 - False</span></span></p></li>
<li><p><span data-ttu-id="51948-180">1-True</span><span class="sxs-lookup"><span data-stu-id="51948-180">1 - True</span></span></p></li>
</ul>
<p><strong><span data-ttu-id="51948-181">範例： </strong> ： Set-AppvClientConfiguration – RequirePublishAsAdmin1</span><span class="sxs-lookup"><span data-stu-id="51948-181">Example:</strong>: Set-AppvClientConfiguration –RequirePublishAsAdmin1</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="51948-182">若要使用應用程式 V 管理主控台來設定此設定，請參閱[如何使用管理主控台發佈套件](how-to-publish-a-package-by-using-the-management-console-51.md)。</span><span class="sxs-lookup"><span data-stu-id="51948-182">To use the App-V Management console to set this configuration, see [How to Publish a Package by Using the Management Console](how-to-publish-a-package-by-using-the-management-console-51.md).</span></span>

## <a href="" id="bkmk-understd-pend-pkgs"></a><span data-ttu-id="51948-183">瞭解擱置的套件（UserPending 和 GlobalPending）</span><span class="sxs-lookup"><span data-stu-id="51948-183">Understanding pending packages (UserPending and GlobalPending)</span></span>


<span data-ttu-id="51948-184">**從 app-v 5.0 SP2 開始**：如果您執行的 PowerShell Cmdlet 會影響目前正在使用的套件，您嘗試執行的工作會放在擱置中的狀態。</span><span class="sxs-lookup"><span data-stu-id="51948-184">**Starting in App-V 5.0 SP2**: If you run a PowerShell cmdlet that affects a package that is currently in use, the task that you are trying to perform is placed in a pending state.</span></span> <span data-ttu-id="51948-185">例如，如果您嘗試在使用該套件中的應用程式時發佈套件，然後執行**AppvClientPackage**，則會在 Cmdlet 輸出中顯示擱置狀態，如下所示：</span><span class="sxs-lookup"><span data-stu-id="51948-185">For example, if you try to publish a package when an application in that package is being used, and then run **Get-AppvClientPackage**, the pending status appears in the cmdlet output as follows:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="51948-186">Cmdlet 輸出專案</span><span class="sxs-lookup"><span data-stu-id="51948-186">Cmdlet output item</span></span></th>
<th align="left"><span data-ttu-id="51948-187">描述</span><span class="sxs-lookup"><span data-stu-id="51948-187">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="51948-188">UserPending</span><span class="sxs-lookup"><span data-stu-id="51948-188">UserPending</span></span></p></td>
<td align="left"><p><span data-ttu-id="51948-189">指出列出的套件是否有正在套用至使用者的待執行工作：</span><span class="sxs-lookup"><span data-stu-id="51948-189">Indicates whether the listed package has a pending task that is being applied to the user:</span></span></p>
<ul>
<li><p><span data-ttu-id="51948-190">True</span><span class="sxs-lookup"><span data-stu-id="51948-190">True</span></span></p></li>
<li><p><span data-ttu-id="51948-191">False</span><span class="sxs-lookup"><span data-stu-id="51948-191">False</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="51948-192">GlobalPending</span><span class="sxs-lookup"><span data-stu-id="51948-192">GlobalPending</span></span></p></td>
<td align="left"><p><span data-ttu-id="51948-193">指出列出的套件是否有全域套用到電腦的未決工作：</span><span class="sxs-lookup"><span data-stu-id="51948-193">Indicates whether the listed package has a pending task that is being applied globally to the computer:</span></span></p>
<ul>
<li><p><span data-ttu-id="51948-194">True</span><span class="sxs-lookup"><span data-stu-id="51948-194">True</span></span></p></li>
<li><p><span data-ttu-id="51948-195">False</span><span class="sxs-lookup"><span data-stu-id="51948-195">False</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="51948-196">根據下列規則，待定的工作將會在稍後執行：</span><span class="sxs-lookup"><span data-stu-id="51948-196">The pending task will run later, according to the following rules:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="51948-197">任務類型</span><span class="sxs-lookup"><span data-stu-id="51948-197">Task type</span></span></th>
<th align="left"><span data-ttu-id="51948-198">適用的規則</span><span class="sxs-lookup"><span data-stu-id="51948-198">Applicable rule</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="51948-199">以使用者為基礎的工作，例如，將套件發佈給使用者</span><span class="sxs-lookup"><span data-stu-id="51948-199">User-based task, e.g., publishing a package to a user</span></span></p></td>
<td align="left"><p><span data-ttu-id="51948-200">暫停的工作將會在使用者登出後執行，然後重新登入。</span><span class="sxs-lookup"><span data-stu-id="51948-200">The pending task will be performed after the user logs off and then logs back on.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="51948-201">以全域為基礎的工作，例如，全域啟用連接群組</span><span class="sxs-lookup"><span data-stu-id="51948-201">Globally based task, e.g., enabling a connection group globally</span></span></p></td>
<td align="left"><p><span data-ttu-id="51948-202">當電腦關閉後再重新開機時，會執行待處理的工作。</span><span class="sxs-lookup"><span data-stu-id="51948-202">The pending task will be performed when the computer is shut down and then restarted.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="51948-203">如需未決工作的詳細資訊，請參閱[關於 App-V 5.0 SP2](about-app-v-50-sp2.md#bkmk-pkg-upgr-pendg-tasks)。</span><span class="sxs-lookup"><span data-stu-id="51948-203">For more information about pending tasks, see [About App-V 5.0 SP2](about-app-v-50-sp2.md#bkmk-pkg-upgr-pendg-tasks).</span></span>

<span data-ttu-id="51948-204">您**有應用程式-V 的建議**嗎？</span><span class="sxs-lookup"><span data-stu-id="51948-204">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="51948-205">在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="51948-205">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="51948-206">有應用程式-V 問題嗎？</span><span class="sxs-lookup"><span data-stu-id="51948-206">Got an App-V issue?</span></span>** <span data-ttu-id="51948-207">使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="51948-207">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="51948-208">相關主題</span><span class="sxs-lookup"><span data-stu-id="51948-208">Related topics</span></span>


[<span data-ttu-id="51948-209">App-V 5.1 作業</span><span class="sxs-lookup"><span data-stu-id="51948-209">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

[<span data-ttu-id="51948-210">使用 PowerShell 管理 App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="51948-210">Administering App-V 5.1 by Using PowerShell</span></span>](administering-app-v-51-by-using-powershell.md)

 

 





