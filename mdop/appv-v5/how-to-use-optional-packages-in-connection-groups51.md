---
title: 如何在連線群組中使用選用套件
description: 如何在連線群組中使用選用套件
author: dansimp
ms.assetid: 67666f18-b704-4852-a1e4-d13633bd2baf
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ffa29f5d62e57a60423b2041cb71787d2c96bd66
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800391"
---
# <span data-ttu-id="aee65-103">如何在連線群組中使用選用套件</span><span class="sxs-lookup"><span data-stu-id="aee65-103">How to Use Optional Packages in Connection Groups</span></span>


<span data-ttu-id="aee65-104">從 Microsoft Application Virtualization （App-v） 5.0 SP3 中開始，您可以在連線群組中新增選用套件，以簡化連接群組管理。</span><span class="sxs-lookup"><span data-stu-id="aee65-104">Starting in Microsoft Application Virtualization (App-V) 5.0 SP3, you can add optional packages to your connection groups to simplify connection group management.</span></span> <span data-ttu-id="aee65-105">下表摘要列出您可以使用選用套件輕鬆完成的工作，並提供每個任務的相關指示連結。</span><span class="sxs-lookup"><span data-stu-id="aee65-105">The following table summarizes the tasks that you can complete more easily by using optional packages, and provides links to instructions for each task.</span></span>

<span data-ttu-id="aee65-106">**記事** 
**在 app-v 5.0 SP3 之前的版本中不支援選用套件。**</span><span class="sxs-lookup"><span data-stu-id="aee65-106">**Note**
**Optional packages are not supported in releases prior to App-V 5.0 SP3.**</span></span>

 

<span data-ttu-id="aee65-107">使用選用的套件之前，請參閱[在連線群組中使用選用套件的需求](#bkmk-reqs-using-cg)。</span><span class="sxs-lookup"><span data-stu-id="aee65-107">Before using optional packages, see [Requirements for using optional packages in connection groups](#bkmk-reqs-using-cg).</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="aee65-108">連結至指示</span><span class="sxs-lookup"><span data-stu-id="aee65-108">Link to instructions</span></span></th>
<th align="left"><span data-ttu-id="aee65-109">工作</span><span class="sxs-lookup"><span data-stu-id="aee65-109">Task</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><a href="#bkmk-apps-plugs-optional" data-raw-source="[Use one connection group, with optional packages, for multiple users who have different packages entitled to them](#bkmk-apps-plugs-optional)"><span data-ttu-id="aee65-110">針對有不同套件的多個使用者使用一個連線群組（含選用套件）</span><span class="sxs-lookup"><span data-stu-id="aee65-110">Use one connection group, with optional packages, for multiple users who have different packages entitled to them</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="aee65-111">使用單一連線群組讓不同的應用程式和外掛程式可供不同的使用者使用。</span><span class="sxs-lookup"><span data-stu-id="aee65-111">Use a single connection group to make different groups of applications and plug-ins available to different end users.</span></span></p>
<p><span data-ttu-id="aee65-112">例如，您想要將 Microsoft Office 發佈給所有的最終使用者，但將不同的外掛程式發佈到不同的使用者子集。</span><span class="sxs-lookup"><span data-stu-id="aee65-112">For example, you want to distribute Microsoft Office to all end users, but distribute different plug-ins to different subsets of users.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="#bkmk-unpub-del-optl-pkg" data-raw-source="[Unpublish or delete an optional package, or unpublish an optional package and republish it later, without changing the connection group](#bkmk-unpub-del-optl-pkg)"><span data-ttu-id="aee65-113">取消發佈或刪除選用的套件，或取消發佈選用的套件，稍後再重新發佈，而不需變更連接群組</span><span class="sxs-lookup"><span data-stu-id="aee65-113">Unpublish or delete an optional package, or unpublish an optional package and republish it later, without changing the connection group</span></span></a></p></td>
<td align="left"><p><span data-ttu-id="aee65-114">取消發佈、刪除或重新發佈選用的套件，而不需要停用、移除、編輯、新增及重新啟用 App-v 用戶端上的連線群組。</span><span class="sxs-lookup"><span data-stu-id="aee65-114">Unpublish, delete, or republish an optional package without having to disable, remove, edit, add, and re-enable the connection group on the App-V Client.</span></span></p>
<p><span data-ttu-id="aee65-115">您也可以取消發佈選用的套件，稍後再重新發佈，而不需要停用或重新發佈連線群組。</span><span class="sxs-lookup"><span data-stu-id="aee65-115">You can also unpublish the optional package and republish it later without having to disable or republish the connection group.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-apps-plugs-optional"></a><span data-ttu-id="aee65-116">將一個連接群組與選用的套件搭配使用，可供多位使用者使用不同套件</span><span class="sxs-lookup"><span data-stu-id="aee65-116">Use one connection group, with optional packages, for multiple users with different packages entitled to them</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="aee65-117">任務描述</span><span class="sxs-lookup"><span data-stu-id="aee65-117">Task description</span></span></th>
<th align="left"><span data-ttu-id="aee65-118">如何執行任務</span><span class="sxs-lookup"><span data-stu-id="aee65-118">How to perform the task</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="aee65-119">App-V 5.0 SP3 和 App-v 5。1</span><span class="sxs-lookup"><span data-stu-id="aee65-119">With App-V 5.0 SP3 and App-V 5.1</span></span></strong></p>
<p><span data-ttu-id="aee65-120">您可以在連線群組中新增選擇性套件，這可讓您提供不同的應用程式和外掛程式組合給不同的使用者。</span><span class="sxs-lookup"><span data-stu-id="aee65-120">You can add optional packages to connection groups, which enables you to provide different combinations of applications and plug-ins to different end users.</span></span></p>
<p><strong><span data-ttu-id="aee65-121">範例 </strong> ：您想要將 Microsoft Office 發佈給您的使用者，但只為使用者子集啟用特定外掛程式。</span><span class="sxs-lookup"><span data-stu-id="aee65-121">Example</strong>: You want to distribute Microsoft Office to your end users, but enable a certain plug-in for only a subset of users.</span></span></p>
<p><span data-ttu-id="aee65-122">若要這樣做，請建立包含 Office 套件的連線群組，以及另一個隨附 Office 外掛程式的套件，然後將外掛程式封裝為選用。</span><span class="sxs-lookup"><span data-stu-id="aee65-122">To do this, create a connection group that contains a package with Office, and another package with Office plug-ins, and then make the plug-ins package optional.</span></span></p>
<p><span data-ttu-id="aee65-123">不具備外掛程式套件資格的使用者仍然可以執行 Office。</span><span class="sxs-lookup"><span data-stu-id="aee65-123">End users who are not entitled to the plug-in package will still be able to run Office.</span></span></p></td>
<td align="left"><table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="aee65-124">方法</span><span class="sxs-lookup"><span data-stu-id="aee65-124">Method</span></span></th>
<th align="left"><span data-ttu-id="aee65-125">步驟</span><span class="sxs-lookup"><span data-stu-id="aee65-125">Steps</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="aee65-126">App-v Server –管理主控台</span><span class="sxs-lookup"><span data-stu-id="aee65-126">App-V Server – Management Console</span></span></p></td>
<td align="left"><ol>
<li><p><span data-ttu-id="aee65-127">在管理主控台中，選取 [連線 <strong> 群組] </strong> 以顯示 [連線群組] 程式庫。</span><span class="sxs-lookup"><span data-stu-id="aee65-127">In the Management Console, select <strong>CONNECTION GROUPS</strong> to display the Connection Groups library.</span></span></p></li>
<li><p><span data-ttu-id="aee65-128">從連線群組程式庫中選取正確的連線群組。</span><span class="sxs-lookup"><span data-stu-id="aee65-128">Select the correct connection group from the Connection Groups library.</span></span></p></li>
<li><p><span data-ttu-id="aee65-129">按一下 <strong> </strong> [連線的套件] 窗格中的 [編輯]。</span><span class="sxs-lookup"><span data-stu-id="aee65-129">Click <strong>EDIT</strong> in the CONNECTED PACKAGES pane.</span></span></p></li>
<li><p><span data-ttu-id="aee65-130">選取 <strong> </strong> 套件名稱旁的 [選擇性]。</span><span class="sxs-lookup"><span data-stu-id="aee65-130">Select <strong>Optional</strong> next to the package name.</span></span></p></li>
<li><p><span data-ttu-id="aee65-131">選取 [ <strong> 新增套件對群組的存取權] </strong> 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="aee65-131">Select the <strong>ADD PACKAGE ACCESS TO GROUP ACCESS</strong> check box.</span></span> <span data-ttu-id="aee65-132">此必要步驟會將您在指派套件至 Active Directory 群組時所設定的套件權利新增至 [連線] 群組。</span><span class="sxs-lookup"><span data-stu-id="aee65-132">This required step adds to the connection group the package entitlements that you configured earlier when you assigned packages to Active Directory groups.</span></span></p></li>
</ol></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="aee65-133">App-v Server-PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="aee65-133">App-V Server - PowerShell cmdlet</span></span></p></td>
<td align="left"><p><span data-ttu-id="aee65-134">使用下列 Cmdlet，並指定 <strong> -Optional </strong> 參數：</span><span class="sxs-lookup"><span data-stu-id="aee65-134">Use the following cmdlet, and specify the <strong>-Optional</strong> parameter:</span></span></p>
<p><strong><span data-ttu-id="aee65-135">附加 AppvServerConnectionGroupPackage</span><span class="sxs-lookup"><span data-stu-id="aee65-135">Add-AppvServerConnectionGroupPackage</span></span></strong></p>
<p><strong><span data-ttu-id="aee65-136">句法</span><span class="sxs-lookup"><span data-stu-id="aee65-136">Syntax:</span></span></strong></p>
<p><code>Add-AppvServerConnectionGroupPackage [-AppvServerConnectionGroup] &lt;SerializableConnectionGroup&gt; [[-AppvServerPackage] &lt;PackageVersion&gt;] [-Optional] [-Order &lt;int&gt;] [-UseAnyPackageVersion]</code></p>
<p><strong><span data-ttu-id="aee65-137">範例：</span><span class="sxs-lookup"><span data-stu-id="aee65-137">Example:</span></span></strong></p>
<p><code>Add-AppvServerConnectionGroupPackage -Name &quot;Connection Group 1&quot; -PackageName &quot;Package 1&quot; -Optional</code></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="aee65-138">在獨立電腦上使用 app-v 用戶端</span><span class="sxs-lookup"><span data-stu-id="aee65-138">App-V Client on a Stand-alone computer</span></span></p></td>
<td align="left"><ol>
<li><p><span data-ttu-id="aee65-139">建立連線群組 XML 檔，並將套件卷 <strong> 標 </strong> 屬性 <strong> IsOptional 設定 </strong> 為 <strong> "true"。</span><span class="sxs-lookup"><span data-stu-id="aee65-139">Create the connection group XML document, and set the <strong>Package</strong> tag attribute <strong>IsOptional</strong> to <strong>“true”.</span></span></strong></p></li>
<li><p><span data-ttu-id="aee65-140">使用下列 Cmdlet 來新增和啟用 [連線] 群組：</span><span class="sxs-lookup"><span data-stu-id="aee65-140">Use the following cmdlets to add and enable the connection group:</span></span></p>
<ul>
<li><p><span data-ttu-id="aee65-141">附加 AppvClientConnectionGroup</span><span class="sxs-lookup"><span data-stu-id="aee65-141">Add-AppvClientConnectionGroup</span></span></p></li>
<li><p><span data-ttu-id="aee65-142">Enable-AppvClientConnectionGroup</span><span class="sxs-lookup"><span data-stu-id="aee65-142">Enable-AppvClientConnectionGroup</span></span></p></li>
</ul></li>
</ol>
<p><strong><span data-ttu-id="aee65-143">含選用套件的連線群組 XML 檔範例：</span><span class="sxs-lookup"><span data-stu-id="aee65-143">Example connection group XML document with optional packages:</span></span></strong></p>
<pre class="syntax" space="preserve"><code>&lt;?xml version=&quot;1.0&quot; ?&gt;
&lt;AppConnectionGroup
   xmlns=&quot;<a href="https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup&amp;quot" data-raw-source="https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup&amp;quot">https://schemas.microsoft.com/appv/2014/virtualapplicationconnectiongroup&quot</a>;
   AppConnectionGroupId=&quot;8105CCD5-244B-4BA1-8888-E321E688D2CB&quot;
   VersionId=&quot;84CE3797-F1CB-4475-A223-757918929EB4&quot;
   DisplayName=&quot;Contoso Software Connection Group&quot; &gt;
&lt;Packages&gt;
&lt;Package
   PackageId=&quot;7735d1a8-5ef9-4df9-a1cf-3aa92ef54fe7&quot;
   VersionId=&quot;ec560d6f-e62e-48eb-a9e5-7c52a8c2e149&quot;
   DisplayName=&quot;Contoso Business Manager&quot;
/&gt;

&lt;Package
   PackageId=&quot;fc6fe0f7-be3d-4643-b37d-fc3f62d4dd5c&quot;
   VersionId=&quot;c67a71cd-3542-4a48-93e8-20c643c50970&quot;
   DisplayName=&quot;Contoso Forms&quot;
   IsOptional=&quot;false&quot;
/&gt;

&lt;Package
   PackageId=&quot;8f6301a5-4348-4039-9560-b27a5bb72711&quot;
   VersionId=&quot;6c694b45-3e19-46c6-a327-d159aa39e1d2&quot;
   DisplayName=&quot;Contoso Tax&quot;
   IsOptional=&quot;true&quot;
/&gt;

&lt;Package
   PackageId=&quot;89d701bc-d507-4299-b6b6-000000003472&quot;
   VersionId=&quot;*&quot;
   DisplayName=&quot;Contoso Accounts&quot;
   IsOptional=&quot;true&quot;
/&gt;

&lt;/Packages&gt;
&lt;/AppConnectionGroup&gt;</code></pre></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="aee65-144">使用 app-v 5.0 SP3 之前的版本</span><span class="sxs-lookup"><span data-stu-id="aee65-144">With versions earlier than App-V 5.0 SP3</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="aee65-145">您必須建立許多連線群組，才能讓特定的使用者使用特定的應用程式和外掛程式組合。</span><span class="sxs-lookup"><span data-stu-id="aee65-145">You had to create many connection groups to make specific application and plug-in combinations available to specific users.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-unpub-del-optl-pkg"></a><span data-ttu-id="aee65-146">取消發佈或刪除選用的套件，或取消發佈選用的套件，稍後再重新發佈，而不需變更連接群組</span><span class="sxs-lookup"><span data-stu-id="aee65-146">Unpublish or delete an optional package, or unpublish an optional package and republish it later, without changing the connection group</span></span>


<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="aee65-147">任務描述</span><span class="sxs-lookup"><span data-stu-id="aee65-147">Task description</span></span></th>
<th align="left"><span data-ttu-id="aee65-148">如何執行任務</span><span class="sxs-lookup"><span data-stu-id="aee65-148">How to perform the task</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="aee65-149">App-V 5.0 SP3 和 App-v 5。1</span><span class="sxs-lookup"><span data-stu-id="aee65-149">With App-V 5.0 SP3 and App-V 5.1</span></span></strong></p>
<p><span data-ttu-id="aee65-150">您可以取消發佈、刪除或重新發佈位於連線群組中的選擇性套件，而不需要停用或重新啟用 App-v 用戶端的連線群組。</span><span class="sxs-lookup"><span data-stu-id="aee65-150">You can unpublish, delete, or republish an optional package, which is in a connection group, without having to disable or re-enable the connection group on the App-V Client.</span></span></p>
<p><span data-ttu-id="aee65-151">您也可以取消發佈選用的套件，稍後再重新發佈，而不需要停用或重新發佈連線群組。</span><span class="sxs-lookup"><span data-stu-id="aee65-151">You can also unpublish an optional package and republish it later without having to disable or republish the connection group.</span></span></p>
<p><strong><span data-ttu-id="aee65-152">範例 </strong> ：如果您發佈的是包含 Microsoft Office 外掛程式的選用套件，而您想要移除該外掛程式，您可以取消發佈套件，而不需要停用連線群組。</span><span class="sxs-lookup"><span data-stu-id="aee65-152">Example</strong>: If you publish an optional package that contains a Microsoft Office plug-in, and you want to remove the plug-in, you can unpublish the package without having to disable the connection group.</span></span></p></td>
<td align="left"><table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="aee65-153">方法</span><span class="sxs-lookup"><span data-stu-id="aee65-153">Method</span></span></th>
<th align="left"><span data-ttu-id="aee65-154">步驟</span><span class="sxs-lookup"><span data-stu-id="aee65-154">Steps</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="aee65-155">App-v Server –管理主控台</span><span class="sxs-lookup"><span data-stu-id="aee65-155">App-V Server – Management Console</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="aee65-156">若要取消發佈套件：請在管理主控台中，選取 [選擇 <strong> 套件] </strong> 頁面，按一下或以滑鼠右鍵按一下您要取消發佈的套件，然後按一下 [ <strong> 取消發佈] </strong> 。</span><span class="sxs-lookup"><span data-stu-id="aee65-156">To unpublish the package: In the Management Console, select elect the <strong>PACKAGES</strong> page, click or right-click the package that you want to unpublish, and click <strong>Unpublish</strong>.</span></span></p></li>
<li><p><span data-ttu-id="aee65-157">若要從連線群組中移除選用套件：請在 [連線 <strong> 群組 </strong> ] 頁面上，選取您要移除的套件，然後按一下向右箭號，從左下角的 [連線] 群組窗格中移除套件。</span><span class="sxs-lookup"><span data-stu-id="aee65-157">To remove an optional package from a connection group: On the <strong>CONNECTION GROUPS</strong> page, select the package that you want to remove, and click the right arrow to remove the package from the connection group pane on the bottom left.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="aee65-158">在獨立電腦上使用 app-v 用戶端</span><span class="sxs-lookup"><span data-stu-id="aee65-158">App-V Client on a Stand-alone computer</span></span></p></td>
<td align="left"><p><span data-ttu-id="aee65-159">使用下列現有的 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="aee65-159">Use the following existing cmdlets:</span></span></p>
<ul>
<li><p><span data-ttu-id="aee65-160">取消發佈-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="aee65-160">Unpublish-AppvClientPackage</span></span></p></li>
<li><p><span data-ttu-id="aee65-161">移除-AppvClientPackage</span><span class="sxs-lookup"><span data-stu-id="aee65-161">Remove-AppvClientPackage</span></span></p></li>
</ul>
<p><span data-ttu-id="aee65-162">如需詳細資訊，請參閱 <a href="how-to-manage-app-v-51-packages-running-on-a-stand-alone-computer-by-using-powershell.md" data-raw-source="[How to Manage App-V 5.1 Packages Running on a Stand-Alone Computer by Using PowerShell](how-to-manage-app-v-51-packages-running-on-a-stand-alone-computer-by-using-powershell.md)"> 如何使用 PowerShell 管理在獨立電腦上執行的 app-v 5.1 套件 </a> 。</span><span class="sxs-lookup"><span data-stu-id="aee65-162">For more information, see <a href="how-to-manage-app-v-51-packages-running-on-a-stand-alone-computer-by-using-powershell.md" data-raw-source="[How to Manage App-V 5.1 Packages Running on a Stand-Alone Computer by Using PowerShell](how-to-manage-app-v-51-packages-running-on-a-stand-alone-computer-by-using-powershell.md)">How to Manage App-V 5.1 Packages Running on a Stand-Alone Computer by Using PowerShell</a>.</span></span></p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="aee65-163">使用 app-v 5.0 SP3 之前的版本</span><span class="sxs-lookup"><span data-stu-id="aee65-163">With versions earlier than App-V 5.0 SP3</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="aee65-164">您必須：</span><span class="sxs-lookup"><span data-stu-id="aee65-164">You had to:</span></span></p>
<ol>
<li><p><span data-ttu-id="aee65-165">從每個啟用的 App-v 用戶端電腦中移除連線群組。</span><span class="sxs-lookup"><span data-stu-id="aee65-165">Remove the connection group from each App-V Client computer where it was enabled.</span></span></p></li>
<li><p><span data-ttu-id="aee65-166">取消發佈套件。</span><span class="sxs-lookup"><span data-stu-id="aee65-166">Unpublish the package.</span></span></p></li>
<li><p><span data-ttu-id="aee65-167">從連線群組的定義中移除套件。</span><span class="sxs-lookup"><span data-stu-id="aee65-167">Remove the package from the connection group’s definition.</span></span></p></li>
<li><p><span data-ttu-id="aee65-168">重新發佈連線群組。</span><span class="sxs-lookup"><span data-stu-id="aee65-168">Republish the connection group.</span></span></p></li>
</ol></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-reqs-using-cg"></a><span data-ttu-id="aee65-169">在連線群組中使用選用套件的需求</span><span class="sxs-lookup"><span data-stu-id="aee65-169">Requirements for using optional packages in connection groups</span></span>


<span data-ttu-id="aee65-170">在連接群組中使用選用套件之前，請先檢查下列需求：</span><span class="sxs-lookup"><span data-stu-id="aee65-170">Review the following requirements before using optional packages in connection groups:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="aee65-171">需求</span><span class="sxs-lookup"><span data-stu-id="aee65-171">Requirement</span></span></th>
<th align="left"><span data-ttu-id="aee65-172">詳細資料</span><span class="sxs-lookup"><span data-stu-id="aee65-172">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="aee65-173">[連線群組] 必須至少包含一個非選用的套件。</span><span class="sxs-lookup"><span data-stu-id="aee65-173">Connection groups must contain at least one non-optional package.</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="aee65-174">請仔細檢查您是否符合這個需求，因為 App-v Server 和 PowerShell Cmdlet 不會驗證是否已滿足需求。</span><span class="sxs-lookup"><span data-stu-id="aee65-174">Check carefully that you meet this requirement, as the App-V Server and the PowerShell cmdlet don’t validate that the requirement has been met.</span></span></p></li>
<li><p><span data-ttu-id="aee65-175">如果您不小心建立一個不包含至少一個非選用套件的連線群組，而使用者嘗試在該連線群組中開啟封裝的應用程式，則連接群組會失敗。</span><span class="sxs-lookup"><span data-stu-id="aee65-175">If you accidentally create a connection group that does not contain at least one non-optional package, and the end user tries to open a packaged application in that connection group, the connection group will fail.</span></span></p></li>
</ul>
<p></p></td>
</tr>
<tr class="even">
<td align="left"><ul>
<li><p><span data-ttu-id="aee65-176">使用者發佈的連線群組可以包含全域發佈或使用者的套件。</span><span class="sxs-lookup"><span data-stu-id="aee65-176">User-published connection groups can contain packages that are published globally or to the user.</span></span></p></li>
<li><p><span data-ttu-id="aee65-177">全域發佈的連線群組必須只包含全域發佈的套件。</span><span class="sxs-lookup"><span data-stu-id="aee65-177">Globally published connection groups must contain only globally published packages.</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="aee65-178">[全域發佈的連線群組] 必須包含全域發行的套件，以確保啟動連線群組的虛擬環境時，套件可供使用。</span><span class="sxs-lookup"><span data-stu-id="aee65-178">Globally published connection groups must contain packages that are published globally to ensure that the packages will be available when starting the connection group’s virtual environment.</span></span></p>
<p><span data-ttu-id="aee65-179">如果您嘗試新增或啟用全域發佈的連線群組（包含使用者發佈的套件），連線群組將會失敗。</span><span class="sxs-lookup"><span data-stu-id="aee65-179">If you try to add or enable globally published connection groups that contain user-published packages, the connection group will fail.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="aee65-180">發佈包含這些套件的連線群組之前，您必須發佈所有非選用套件。</span><span class="sxs-lookup"><span data-stu-id="aee65-180">You must publish all non-optional packages before publishing the connection group that contains those packages.</span></span></p></td>
<td align="left"><p><span data-ttu-id="aee65-181">如果沒有任何非選用的套件，則無法啟動連線群組的虛擬環境。</span><span class="sxs-lookup"><span data-stu-id="aee65-181">A connection group’s virtual environment cannot start if any non-optional packages are missing.</span></span></p>
<p><span data-ttu-id="aee65-182">如果沒有發佈任何非選用套件，App-v 用戶端將無法新增或啟用連接群組。</span><span class="sxs-lookup"><span data-stu-id="aee65-182">The App-V Client fails to add or enable a connection group if any non-optional packages have not been published.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="aee65-183">在您取消發佈全域發佈的套件之前，請確定擁有該電腦上所有使用者的 [連線群組] 不再需要套件。</span><span class="sxs-lookup"><span data-stu-id="aee65-183">Before you unpublish a globally published package, ensure that the connection groups that are entitled to all the users on that computer no longer require the package.</span></span></p></td>
<td align="left"><p><span data-ttu-id="aee65-184">系統不會檢查套件是否為其他使用者的連線群組的一部分。</span><span class="sxs-lookup"><span data-stu-id="aee65-184">The system does not check whether the package is part of another user’s connection group.</span></span> <span data-ttu-id="aee65-185">取消發佈全域套件將使該電腦上的每個使用者都無法使用它，因此請確定每個使用者的連線群組已不包含套件，或者將套件設為選用。</span><span class="sxs-lookup"><span data-stu-id="aee65-185">Unpublishing a global package will make it unavailable to every user on that computer, so make sure that each user’s connection groups no longer contain the package, or alternatively make the package optional.</span></span></p></td>
</tr>
</tbody>
</table>

 






## <span data-ttu-id="aee65-186">相關主題</span><span class="sxs-lookup"><span data-stu-id="aee65-186">Related topics</span></span>


[<span data-ttu-id="aee65-187">管理連線群組</span><span class="sxs-lookup"><span data-stu-id="aee65-187">Managing Connection Groups</span></span>](managing-connection-groups51.md)

 

 





