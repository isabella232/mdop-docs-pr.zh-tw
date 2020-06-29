---
title: 使用 Windows PowerShell 和 WMI 管理 UE-V a.x 設定位置範本
description: 使用 Windows PowerShell 和 WMI 管理 UE-V a.x 設定位置範本
author: dansimp
ms.assetid: b5253050-acc3-4274-90d0-1fa4c480331d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9788ff1a11f1c70e52b75dd2187a198f5472f77f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800204"
---
# <span data-ttu-id="463fd-103">使用 Windows PowerShell 和 WMI 管理 UE-V a.x 設定位置範本</span><span class="sxs-lookup"><span data-stu-id="463fd-103">Managing UE-V 2.x Settings Location Templates Using Windows PowerShell and WMI</span></span>


<span data-ttu-id="463fd-104">Microsoft 使用者體驗虛擬化（UE-V）2.0、2.1 和 2.1 SP1 使用 XML 設定位置範本來定義使用者體驗虛擬化捕獲並套用的設定。</span><span class="sxs-lookup"><span data-stu-id="463fd-104">Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, and 2.1 SP1 use XML settings location templates to define the settings that User Experience Virtualization captures and applies.</span></span> <span data-ttu-id="463fd-105">UE-V 包含一組標準設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="463fd-105">UE-V includes a set of standard settings location templates.</span></span> <span data-ttu-id="463fd-106">它也包含 UE-V 發生器工具，可讓您建立自訂設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="463fd-106">It also includes the UE-V Generator tool that enables you to create custom settings location templates.</span></span> <span data-ttu-id="463fd-107">在您建立並部署設定位置範本之後，您可以使用 Windows PowerShell 和 Windows 管理工具（WMI）管理這些範本。</span><span class="sxs-lookup"><span data-stu-id="463fd-107">After you create and deploy settings location templates, you can manage those templates by using Windows PowerShell and the Windows Management Instrumentation (WMI).</span></span> <span data-ttu-id="463fd-108">如需 UE-V PowerShell Cmdlet 的完整清單，請參閱[ue-v 2 Cmdlet 參考](https://go.microsoft.com/fwlink/p/?LinkId=393495)（ https://go.microsoft.com/fwlink/p/?LinkId=393495) 。</span><span class="sxs-lookup"><span data-stu-id="463fd-108">For a complete list of UE-V PowerShell cmdlets, see [UE-V 2 Cmdlet Reference](https://go.microsoft.com/fwlink/p/?LinkId=393495) (https://go.microsoft.com/fwlink/p/?LinkId=393495).</span></span>

## <span data-ttu-id="463fd-109">使用 Windows PowerShell 管理 UE-V 2 設定位置範本</span><span class="sxs-lookup"><span data-stu-id="463fd-109">Manage UE-V 2 settings location templates by using Windows PowerShell</span></span>


<span data-ttu-id="463fd-110">UE-V 的 WMI 和 Windows PowerShell 功能包括啟用、停用、註冊、更新及登出設定位置範本的功能。</span><span class="sxs-lookup"><span data-stu-id="463fd-110">The WMI and Windows PowerShell features of UE-V include the ability to enable, disable, register, update, and unregister settings location templates.</span></span> <span data-ttu-id="463fd-111">您可以使用這些功能，透過 UE-V Agent 程式來自動註冊、更新或登出範本。</span><span class="sxs-lookup"><span data-stu-id="463fd-111">By using these features, you can automate the process of registering, updating, or unregistering templates with the UE-V Agent.</span></span> <span data-ttu-id="463fd-112">您也可以使用 WMI 和 Windows PowerShell 命令，手動註冊範本。</span><span class="sxs-lookup"><span data-stu-id="463fd-112">You can also manually register templates by using WMI and Windows PowerShell commands.</span></span> <span data-ttu-id="463fd-113">透過將這些功能與電子軟體發佈方案、群組原則或其他自動部署方法（例如腳本）搭配使用，您就可以進一步自動化該程式。</span><span class="sxs-lookup"><span data-stu-id="463fd-113">By using these features in conjunction with an electronic software distribution solution, Group Policy, or another automated deployment method such as a script, you can further automate that process.</span></span>

<span data-ttu-id="463fd-114">您必須具備系統管理員許可權，才能更新、註冊或登出設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="463fd-114">You must have administrator permissions to update, register, or unregister a settings location template.</span></span> <span data-ttu-id="463fd-115">[啟用]、[停用] 或 [清單] 範本不需要系統管理員許可權。</span><span class="sxs-lookup"><span data-stu-id="463fd-115">Administrator permissions are not required to enable, disable, or list templates.</span></span>

***<em><span data-ttu-id="463fd-116">使用 Windows PowerShell 管理設定位置範本</span><span class="sxs-lookup"><span data-stu-id="463fd-116">To manage settings location templates by using Windows PowerShell</span></span>ell</em>***

1.  <span data-ttu-id="463fd-117">使用具有系統管理員許可權的帳戶來開啟 Windows PowerShell 命令提示字元。</span><span class="sxs-lookup"><span data-stu-id="463fd-117">Use an account with administrator rights to open a Windows PowerShell command prompt.</span></span>

2.  <span data-ttu-id="463fd-118">使用下列 Windows PowerShell Cmdlet 來註冊及管理 UE-V 設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="463fd-118">Use the following Windows PowerShell cmdlets to register and manage the UE-V settings location templates.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="463fd-119">Windows PowerShell 命令</span><span class="sxs-lookup"><span data-stu-id="463fd-119">Windows PowerShell command</span></span></th>
    <th align="left"><span data-ttu-id="463fd-120">描述</span><span class="sxs-lookup"><span data-stu-id="463fd-120">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><code>Get-UevTemplate</code></p></td>
    <td align="left"><p><span data-ttu-id="463fd-121">列出電腦上已註冊的所有設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="463fd-121">Lists all the settings location templates that are registered on the computer.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Get-UevTemplate –Application &lt;string&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="463fd-122">列出電腦上已登錄且應用程式名稱或範本名稱包含字串的所有設定位置範本 &lt; &gt; 。</span><span class="sxs-lookup"><span data-stu-id="463fd-122">Lists all the settings location templates that are registered on the computer where the application name or template name contains &lt;string&gt;.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Get-UevTemplate –TemplateID &lt;string&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="463fd-123">列出已在電腦上登錄且範本識別碼包含字串的所有設定位置範本 &lt; &gt; 。</span><span class="sxs-lookup"><span data-stu-id="463fd-123">Lists all the settings location templates that are registered on the computer where the template ID contains &lt;string&gt;.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Get-UevTemplate [-ApplicationOrTemplateID] &lt;string&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="463fd-124">列出在電腦上註冊的所有設定位置範本，或範本識別碼包含字串的電腦 &lt; &gt; 。</span><span class="sxs-lookup"><span data-stu-id="463fd-124">Lists all the settings location templates that are registered on the computer where the application or template name, or template ID contains &lt;string&gt;.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Get-UevTemplateProgram [-ID] &lt;template ID&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="463fd-125">取得程式與版本資訊的名稱，這取決於範本識別碼。</span><span class="sxs-lookup"><span data-stu-id="463fd-125">Gets the name of the program and version information, which depend on the template ID.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Get-UevAppXPackage</code></p></td>
    <td align="left"><p><span data-ttu-id="463fd-126">取得有效的 Windows app 清單。</span><span class="sxs-lookup"><span data-stu-id="463fd-126">Gets the effective list of Windows apps.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Get-UevAppXPackage -Computer</code></p></td>
    <td align="left"><p><span data-ttu-id="463fd-127">取得為電腦設定的 Windows app 清單。</span><span class="sxs-lookup"><span data-stu-id="463fd-127">Gets the list of Windows apps that are configured for the computer.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Get-UevAppXPackage -CurrentComputerUser</code></p></td>
    <td align="left"><p><span data-ttu-id="463fd-128">取得為目前使用者設定的 Windows app 清單。</span><span class="sxs-lookup"><span data-stu-id="463fd-128">Gets the list of Windows apps that are configured for the current user.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Register-UevTemplate [-Path] &lt;template file path&gt;[,&lt;template file path&gt;]</code></p></td>
    <td align="left"><p><span data-ttu-id="463fd-129">在檔路徑中使用相對路徑和/或萬用字元，以 UE-V 註冊一或多個設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="463fd-129">Registers one or more settings location template with UE-V by using relative paths and/or wildcard characters in file paths.</span></span> <span data-ttu-id="463fd-130">範本註冊之後，UE-V 會同步處理範本中定義的設定，這些設定是在已註冊範本的電腦之間進行。</span><span class="sxs-lookup"><span data-stu-id="463fd-130">After a template is registered, UE-V synchronizes the settings that are defined in the template between computers that have the template registered.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Register-UevTemplate –LiteralPath &lt;template file path&gt;[,&lt;template file path&gt;]</code></p></td>
    <td align="left"><p><span data-ttu-id="463fd-131">使用文字路徑登錄一個或多個設定位置範本，其中不能將任何字元轉譯成萬用字元字元。</span><span class="sxs-lookup"><span data-stu-id="463fd-131">Registers one or more settings location template with UE-V by using literal paths, where no characters can be interpreted as wildcard characters.</span></span> <span data-ttu-id="463fd-132">範本註冊之後，UE-V 會同步處理範本中定義的設定，這些設定是在已註冊範本的電腦之間進行。</span><span class="sxs-lookup"><span data-stu-id="463fd-132">After a template is registered, UE-V synchronizes the settings that are defined in the template between computers that have the template registered.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Unregister-UevTemplate [-ID] &lt;template ID&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="463fd-133">使用 UE-V 登出 [設定位置] 範本。</span><span class="sxs-lookup"><span data-stu-id="463fd-133">Unregisters a settings location template with UE-V.</span></span> <span data-ttu-id="463fd-134">取消註冊範本後，UE-V 就不會再同步處理在電腦之間的範本中定義的設定。</span><span class="sxs-lookup"><span data-stu-id="463fd-134">When a template is unregistered, UE-V no longer synchronizes the settings that are defined in the template between computers.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Unregister-UevTemplate -All</code></p></td>
    <td align="left"><p><span data-ttu-id="463fd-135">使用 UE-V 登出所有設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="463fd-135">Unregisters all settings location templates with UE-V.</span></span> <span data-ttu-id="463fd-136">取消註冊範本後，UE-V 就不會再同步處理在電腦之間的範本中定義的設定。</span><span class="sxs-lookup"><span data-stu-id="463fd-136">When a template is unregistered, UE-V no longer synchronizes the settings that are defined in the template between computers.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Update-UevTemplate [-Path] &lt;template file path&gt;[,&lt;template file path&gt;]</code></p></td>
    <td align="left"><p><span data-ttu-id="463fd-137">使用最新版本的範本更新一或多個設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="463fd-137">Updates one or more settings location templates with a more recent version of the template.</span></span> <span data-ttu-id="463fd-138">在檔路徑中使用相對路徑和/或萬用字元。</span><span class="sxs-lookup"><span data-stu-id="463fd-138">Use relative paths and/or wildcard characters in the file paths.</span></span> <span data-ttu-id="463fd-139">新範本的版本必須比現有範本更新。</span><span class="sxs-lookup"><span data-stu-id="463fd-139">The new template should be a newer version than the existing template.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Update-UevTemplate –LiteralPath &lt;template file path&gt;[,&lt;template file path&gt;]</code></p></td>
    <td align="left"><p><span data-ttu-id="463fd-140">使用最新版本的範本更新一或多個設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="463fd-140">Updates one or more settings location templates with a more recent version of the template.</span></span> <span data-ttu-id="463fd-141">使用完整路徑至範本檔案，其中不能將任何字元轉譯成萬用字元字元。</span><span class="sxs-lookup"><span data-stu-id="463fd-141">Use full paths to template files, where no characters can be interpreted as wildcard characters.</span></span> <span data-ttu-id="463fd-142">新範本的版本必須比現有範本更新。</span><span class="sxs-lookup"><span data-stu-id="463fd-142">The new template should be a newer version than the existing template.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Clear-UevAppXPackage –Computer [-PackageFamilyName] &lt;package family name&gt;[,&lt;package family name&gt;]</code></p></td>
    <td align="left"><p><span data-ttu-id="463fd-143">從電腦 Windows app 清單移除一或多個 Windows 應用程式。</span><span class="sxs-lookup"><span data-stu-id="463fd-143">Removes one or more Windows apps from the computer Windows app list.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Clear-UevAppXPackage -CurrentComputerUser</code></p></td>
    <td align="left"><p><span data-ttu-id="463fd-144">從目前使用者的 Windows 應用程式清單移除 Windows 應用程式。</span><span class="sxs-lookup"><span data-stu-id="463fd-144">Removes Windows app from the current user Windows app list.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Clear-UevAppXPackage –Computer -All</code></p></td>
    <td align="left"><p><span data-ttu-id="463fd-145">從電腦 Windows app 清單移除所有 Windows 應用程式。</span><span class="sxs-lookup"><span data-stu-id="463fd-145">Removes all Windows apps from the computer Windows app list.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Clear-UevAppXPackage [–CurrentComputerUser] [-PackageFamilyName] &lt;package family name&gt;[,&lt;package family name&gt;]</code></p></td>
    <td align="left"><p><span data-ttu-id="463fd-146">從目前使用者的 Windows 應用程式清單移除一或多個 Windows 應用程式。</span><span class="sxs-lookup"><span data-stu-id="463fd-146">Removes one or more Windows apps from the current user Windows app list.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Clear-UevAppXPackage [–CurrentComputerUser] -All</code></p></td>
    <td align="left"><p><span data-ttu-id="463fd-147">從目前使用者的 Windows 應用程式清單移除所有 Windows 應用程式。</span><span class="sxs-lookup"><span data-stu-id="463fd-147">Removes all Windows apps from the current user Windows app list.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Disable-UevTemplate [-ID] &lt;template ID&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="463fd-148">停用電腦目前使用者的設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="463fd-148">Disables a settings location template for the current user of the computer.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Disable-UevAppXPackage –Computer [-PackageFamilyName] &lt;package family name&gt;[,&lt;package family name&gt;]</code></p></td>
    <td align="left"><p><span data-ttu-id="463fd-149">停用電腦視窗 app 清單中的一個或多個 Windows 應用程式。</span><span class="sxs-lookup"><span data-stu-id="463fd-149">Disables one or more Windows apps in the computer Windows app list.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Disable-UevAppXPackage [–CurrentComputerUser] [-PackageFamilyName] &lt;package family name&gt;[,&lt;package family name&gt;]</code></p></td>
    <td align="left"><p><span data-ttu-id="463fd-150">停用目前使用者 Windows 應用程式清單中的一個或多個 Windows 應用程式。</span><span class="sxs-lookup"><span data-stu-id="463fd-150">Disables one or more Windows apps in the current user Windows app list.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Enable-UevTemplate [-ID] &lt;template ID&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="463fd-151">啟用電腦目前使用者的設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="463fd-151">Enables a settings location template for the current user of the computer.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Enable-UevAppXPackage –Computer [-PackageFamilyName] &lt;package family name&gt;[,&lt;package family name&gt;]</code></p></td>
    <td align="left"><p><span data-ttu-id="463fd-152">啟用電腦 Windows 應用程式清單中的一個或多個 Windows 應用程式。</span><span class="sxs-lookup"><span data-stu-id="463fd-152">Enables one or more Windows apps in the computer Windows app list.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Enable-UevAppXPackage [–CurrentComputerUser] [-PackageFamilyName] &lt;package family name&gt;[,&lt;package family name&gt;]</code></p></td>
    <td align="left"><p><span data-ttu-id="463fd-153">在目前的使用者 Windows 應用程式清單中啟用一個或多個 Windows 應用程式。</span><span class="sxs-lookup"><span data-stu-id="463fd-153">Enables one or more Windows apps in the current user Windows app list.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Test-UevTemplate [-Path] &lt;template file path&gt;[,&lt;template file path&gt;]</code></p></td>
    <td align="left"><p><span data-ttu-id="463fd-154">判斷一個或多個設定位置範本是否符合其 XML 架構。</span><span class="sxs-lookup"><span data-stu-id="463fd-154">Determines whether one or more settings location templates comply with its XML schema.</span></span> <span data-ttu-id="463fd-155">可以使用相對路徑和萬用字元。</span><span class="sxs-lookup"><span data-stu-id="463fd-155">Can use relative paths and wildcard characters.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Test-UevTemplate –LiteralPath &lt;template file path&gt;[,&lt;template file path&gt;]</code></p></td>
    <td align="left"><p><span data-ttu-id="463fd-156">判斷一個或多個設定位置範本是否符合其 XML 架構。</span><span class="sxs-lookup"><span data-stu-id="463fd-156">Determines whether one or more settings location templates comply with its XML schema.</span></span> <span data-ttu-id="463fd-157">路徑必須是範本檔案的完整路徑，但不會包含萬用字元字元。</span><span class="sxs-lookup"><span data-stu-id="463fd-157">The path must be a full path to the template file, but does not include wildcard characters.</span></span></p></td>
    </tr>
    </tbody>
    </table>



<span data-ttu-id="463fd-158">UE-V Windows PowerShell 功能可讓您管理企業中部署的一組設定範本。</span><span class="sxs-lookup"><span data-stu-id="463fd-158">The UE-V Windows PowerShell features enable you to manage a group of settings templates that are deployed in your enterprise.</span></span> <span data-ttu-id="463fd-159">使用下列程式，使用 Windows PowerShell 來管理一組範本。</span><span class="sxs-lookup"><span data-stu-id="463fd-159">Use the following procedure to manage a group of templates by using Windows PowerShell.</span></span>

**<span data-ttu-id="463fd-160">使用 Windows PowerShell 管理設定位置範本群組</span><span class="sxs-lookup"><span data-stu-id="463fd-160">To manage a group of settings location templates by using Windows PowerShell</span></span>**

1.  <span data-ttu-id="463fd-161">修改或更新所需的設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="463fd-161">Modify or update the desired settings location templates.</span></span>

2.  <span data-ttu-id="463fd-162">如果您想要修改或更新設定位置範本，請將這些設定位置範本部署到本機電腦無法存取的資料夾中。</span><span class="sxs-lookup"><span data-stu-id="463fd-162">If you want to modify or update the settings location templates, deploy those settings location templates to a folder that is accessible to the local computer.</span></span>

3.  <span data-ttu-id="463fd-163">在本機電腦上，以系統管理員許可權開啟 Windows PowerShell 視窗。</span><span class="sxs-lookup"><span data-stu-id="463fd-163">On the local computer, open a Windows PowerShell window with administrator rights.</span></span>

4.  <span data-ttu-id="463fd-164">輸入下列命令，以取消註冊所有先前已註冊的範本版本。</span><span class="sxs-lookup"><span data-stu-id="463fd-164">Unregister all the previously registered versions of the templates by typing the following command.</span></span>

    ``` syntax
    Unregister-UevTemplate -All
    ```

    <span data-ttu-id="463fd-165">這個命令會登出電腦上所有的活動範本。</span><span class="sxs-lookup"><span data-stu-id="463fd-165">This command unregisters all active templates on the computer.</span></span>

5.  <span data-ttu-id="463fd-166">輸入下列命令來註冊更新的範本。</span><span class="sxs-lookup"><span data-stu-id="463fd-166">Register the updated templates by typing the following command.</span></span>

    ``` syntax
    Register-UevTemplate <path to template folder>\*.xml
    ```

    <span data-ttu-id="463fd-167">這個命令會註冊位於指定範本資料夾中的所有設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="463fd-167">This command registers all of the settings location templates that are located in the specified template folder.</span></span>

### <a href="" id="win8applist"></a><span data-ttu-id="463fd-168">Windows 應用程式清單</span><span class="sxs-lookup"><span data-stu-id="463fd-168">Windows app list</span></span>

<span data-ttu-id="463fd-169">在 Windows 應用程式清單中列出 Windows 應用程式，即可指定是否已啟用或停用應用程式的設定同步處理。</span><span class="sxs-lookup"><span data-stu-id="463fd-169">By listing a Windows app in the Windows app list, you specify whether that app is enabled or disabled for settings synchronization.</span></span> <span data-ttu-id="463fd-170">應用程式會依其套件系列名稱在清單中加以識別，以及該 app 是否應該啟用或停用設定同步處理。</span><span class="sxs-lookup"><span data-stu-id="463fd-170">Apps are identified in the list by their Package Family name and whether settings synchronization should be enabled or disabled for that app.</span></span> <span data-ttu-id="463fd-171">當您使用這些設定以及未列出的預設同步處理行為設定時，您可以控制是否已同步處理 Windows 應用程式。</span><span class="sxs-lookup"><span data-stu-id="463fd-171">When you use these settings along with the Unlisted Default Sync Behavior setting, you can control whether Windows apps are synchronized.</span></span>

<span data-ttu-id="463fd-172">若要顯示已安裝的 Windows 應用程式套件系列名稱，請在 Windows PowerShell 命令提示字元輸入：</span><span class="sxs-lookup"><span data-stu-id="463fd-172">To display the Package Family Name of installed Windows apps, at a Windows PowerShell command prompt, enter:</span></span>

``` syntax
Get-AppxPackage | Sort-Object PackageFamilyName | Format-Table PackageFamilyName
```

<span data-ttu-id="463fd-173">若要在 Windows PowerShell 命令提示字元上顯示可同步處理電腦設定的 Windows app 清單，以及其套件系列名稱、啟用狀態，以及已啟用的來源，請輸入：</span><span class="sxs-lookup"><span data-stu-id="463fd-173">To display a list of Windows apps that can synchronize settings on a computer with their package family name, enabled status, and enabled source, at a Windows PowerShell command prompt, enter:</span></span> `Get-UevAppxPackage`

**<span data-ttu-id="463fd-174">UevAppxPackage 屬性的定義</span><span class="sxs-lookup"><span data-stu-id="463fd-174">Definitions of Get-UevAppxPackage properties</span></span>**

<a href="" id="displayname"></a>**<span data-ttu-id="463fd-175">DisplayName</span><span class="sxs-lookup"><span data-stu-id="463fd-175">DisplayName</span></span>**  
<span data-ttu-id="463fd-176">在 [公司設定中心] 應用程式中顯示給使用者的名稱。</span><span class="sxs-lookup"><span data-stu-id="463fd-176">The name that is displayed to the user in the Company Settings Center application.</span></span> <span data-ttu-id="463fd-177">`DisplayName`屬性衍生自 `PackageFamilyName` 屬性。</span><span class="sxs-lookup"><span data-stu-id="463fd-177">The `DisplayName` property is derived from the `PackageFamilyName` property.</span></span>

<a href="" id="packagefamilyname"></a>**<span data-ttu-id="463fd-178">PackageFamilyName</span><span class="sxs-lookup"><span data-stu-id="463fd-178">PackageFamilyName</span></span>**  
<span data-ttu-id="463fd-179">為目前使用者安裝的套件名稱。</span><span class="sxs-lookup"><span data-stu-id="463fd-179">The name of the package that is installed for the current user.</span></span>

<a href="" id="enabled"></a>**<span data-ttu-id="463fd-180">啟用</span><span class="sxs-lookup"><span data-stu-id="463fd-180">Enabled</span></span>**  
<span data-ttu-id="463fd-181">定義應用程式的設定是否設定為同步處理。</span><span class="sxs-lookup"><span data-stu-id="463fd-181">Defines whether the settings for the app are configured to synchronize.</span></span>

<a href="" id="enabledsource"></a>**<span data-ttu-id="463fd-182">EnabledSource</span><span class="sxs-lookup"><span data-stu-id="463fd-182">EnabledSource</span></span>**  
<span data-ttu-id="463fd-183">啟用或停用 app 之設定的位置。</span><span class="sxs-lookup"><span data-stu-id="463fd-183">The location where the configuration that enables or disables the app is set.</span></span> <span data-ttu-id="463fd-184">可能的值為： *NotSet*、 *LocalMachine*、 *LocalUser*、 *PolicyMachine*和*PolicyUser*。</span><span class="sxs-lookup"><span data-stu-id="463fd-184">Possible values are: *NotSet*, *LocalMachine*, *LocalUser*, *PolicyMachine*, and *PolicyUser*.</span></span>

<a href="" id="notset"></a>**<span data-ttu-id="463fd-185">NotSet</span><span class="sxs-lookup"><span data-stu-id="463fd-185">NotSet</span></span>**  
<span data-ttu-id="463fd-186">未將原則設定為同步處理此應用程式。</span><span class="sxs-lookup"><span data-stu-id="463fd-186">The policy is not configured to synchronize this app.</span></span>

<a href="" id="localmachine"></a>**<span data-ttu-id="463fd-187">My</span><span class="sxs-lookup"><span data-stu-id="463fd-187">LocalMachine</span></span>**  
<span data-ttu-id="463fd-188">[啟用] 狀態是在註冊表的 [本機電腦] 區段中設定。</span><span class="sxs-lookup"><span data-stu-id="463fd-188">The enabled state is set in the local computer section of the registry.</span></span>

<a href="" id="localuser"></a>**<span data-ttu-id="463fd-189">LocalUser</span><span class="sxs-lookup"><span data-stu-id="463fd-189">LocalUser</span></span>**  
<span data-ttu-id="463fd-190">[啟用] 狀態是在登錄的 [目前使用者] 區段中設定。</span><span class="sxs-lookup"><span data-stu-id="463fd-190">The enabled state is set in the current user section of the registry.</span></span>

<a href="" id="policymachine"></a>**<span data-ttu-id="463fd-191">PolicyMachine</span><span class="sxs-lookup"><span data-stu-id="463fd-191">PolicyMachine</span></span>**  
<span data-ttu-id="463fd-192">[啟用] 狀態是在註冊表的 [本機電腦] 區段的 [原則] 區段中設定。</span><span class="sxs-lookup"><span data-stu-id="463fd-192">The enabled state is set in the policy section of the local computer section of the registry.</span></span>

<span data-ttu-id="463fd-193">若要取得使用者設定的 Windows 應用程式清單，請在 Windows PowerShell 命令提示字元輸入：</span><span class="sxs-lookup"><span data-stu-id="463fd-193">To get the user-configured list of Windows apps, at the Windows PowerShell command prompt, enter:</span></span> `Get-UevAppxPackage –CurrentComputerUser`

<span data-ttu-id="463fd-194">若要取得電腦設定的 Windows 應用程式清單，請在 Windows PowerShell 命令提示字元輸入：</span><span class="sxs-lookup"><span data-stu-id="463fd-194">To get the computer-configured list of Windows apps, at the Windows PowerShell command prompt, enter:</span></span> `Get-UevAppxPackage –Computer`

<span data-ttu-id="463fd-195">無論是參數、CurrentComputerUser 或電腦，此 Cmdlet 都會傳回在使用者或電腦層級設定的 Windows app 清單。</span><span class="sxs-lookup"><span data-stu-id="463fd-195">For either parameter, CurrentComputerUser or Computer, the cmdlet returns a list of the Windows apps that are configured at the user or at the computer level.</span></span>

**<span data-ttu-id="463fd-196">屬性的定義</span><span class="sxs-lookup"><span data-stu-id="463fd-196">Definitions of properties</span></span>**

<a href="" id="displayname"></a>**<span data-ttu-id="463fd-197">DisplayName</span><span class="sxs-lookup"><span data-stu-id="463fd-197">DisplayName</span></span>**  
<span data-ttu-id="463fd-198">在 [公司設定中心] 應用程式中顯示給使用者的名稱。</span><span class="sxs-lookup"><span data-stu-id="463fd-198">The name that is displayed to the user in the Company Settings Center application.</span></span> <span data-ttu-id="463fd-199">`DisplayName`屬性衍生自 `PackageFamilyName` 屬性。</span><span class="sxs-lookup"><span data-stu-id="463fd-199">The `DisplayName` property is derived from the `PackageFamilyName` property.</span></span>

<a href="" id="packagefamilyname"></a>**<span data-ttu-id="463fd-200">PackageFamilyName</span><span class="sxs-lookup"><span data-stu-id="463fd-200">PackageFamilyName</span></span>**  
<span data-ttu-id="463fd-201">為目前使用者安裝的套件名稱。</span><span class="sxs-lookup"><span data-stu-id="463fd-201">The name of the package that is installed for the current user.</span></span>

<a href="" id="enabled"></a>**<span data-ttu-id="463fd-202">啟用</span><span class="sxs-lookup"><span data-stu-id="463fd-202">Enabled</span></span>**  
<span data-ttu-id="463fd-203">定義應用程式的設定是否已設定為針對指定的交換器（也就是**使用者**或**電腦**）進行同步處理。</span><span class="sxs-lookup"><span data-stu-id="463fd-203">Defines whether the settings for the app are configured to synchronize for the specified switch, that is, **user** or **computer**.</span></span>

<a href="" id="installed"></a>**<span data-ttu-id="463fd-204">已安裝</span><span class="sxs-lookup"><span data-stu-id="463fd-204">Installed</span></span>**  
<span data-ttu-id="463fd-205">如果應用程式是針對目前的使用者安裝 PackageFamilyName，則為 True。</span><span class="sxs-lookup"><span data-stu-id="463fd-205">True if the app, that is, the PackageFamilyName is installed for the current user.</span></span>

### <span data-ttu-id="463fd-206">使用 WMI 管理 UE-V 2 設定位置範本</span><span class="sxs-lookup"><span data-stu-id="463fd-206">Manage UE-V 2 settings location templates by using WMI</span></span>

<span data-ttu-id="463fd-207">使用者體驗虛擬化提供下列一組 WMI 命令。</span><span class="sxs-lookup"><span data-stu-id="463fd-207">User Experience Virtualization provides the following set of WMI commands.</span></span> <span data-ttu-id="463fd-208">系統管理員可以使用這些介面，從 Windows PowerShell 管理設定位置範本，並自動執行範本管理工作。</span><span class="sxs-lookup"><span data-stu-id="463fd-208">Administrators can use these interfaces to manage settings location templates from Windows PowerShell and automate template administrative tasks.</span></span>

**<span data-ttu-id="463fd-209">使用 WMI 管理設定位置範本</span><span class="sxs-lookup"><span data-stu-id="463fd-209">To manage settings location templates by using WMI</span></span>**

1.  <span data-ttu-id="463fd-210">使用具有系統管理員許可權的帳戶來開啟 Windows PowerShell 視窗。</span><span class="sxs-lookup"><span data-stu-id="463fd-210">Use an account with administrator rights to open a Windows PowerShell window.</span></span>

2.  <span data-ttu-id="463fd-211">使用下列 WMI 命令來註冊及管理 UE-V 設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="463fd-211">Use the following WMI commands to register and manage the UE-V settings location templates.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><code>                         Windows PowerShell command</code></th>
    <th align="left"><span data-ttu-id="463fd-212">描述</span><span class="sxs-lookup"><span data-stu-id="463fd-212">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><code>Get-WmiObject -Namespace root\Microsoft\UEV SettingsLocationTemplate | Select-Object TemplateId,TemplateName, TemplateVersion,Enabled | Format-Table -Autosize</code></p></td>
    <td align="left"><p><span data-ttu-id="463fd-213">列出已針對電腦註冊的所有設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="463fd-213">Lists all the settings location templates that are registered for the computer.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod –Namespace root\Microsoft\UEV –Class SettingsLocationTemplate –Name GetProcessInfoByTemplateId &lt;template Id&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="463fd-214">取得程式與版本資訊的名稱，這取決於範本名稱。</span><span class="sxs-lookup"><span data-stu-id="463fd-214">Gets the name of the program and version information, which depends on the template name.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Get-WmiObject -Namespace root\Microsoft\UEV EffectiveWindows8App</code></p></td>
    <td align="left"><p><span data-ttu-id="463fd-215">取得有效的 Windows app 清單。</span><span class="sxs-lookup"><span data-stu-id="463fd-215">Gets the effective list of Windows apps.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="463fd-216">WmiObject-Namespace root\Microsoft\UEV MachineConfiguredWindows8App</span><span class="sxs-lookup"><span data-stu-id="463fd-216">Get-WmiObject -Namespace root\Microsoft\UEV MachineConfiguredWindows8App</span></span></p></td>
    <td align="left"><p><span data-ttu-id="463fd-217">取得為電腦設定的 Windows app 清單。</span><span class="sxs-lookup"><span data-stu-id="463fd-217">Gets the list of Windows apps that are configured for the computer.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Get-WmiObject -Namespace root\Microsoft\UEV UserConfiguredWindows8App</code></p></td>
    <td align="left"><p><span data-ttu-id="463fd-218">取得為目前使用者設定的 Windows app 清單。</span><span class="sxs-lookup"><span data-stu-id="463fd-218">Gets the list of Windows apps that are configured for the current user.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name Register -ArgumentList &lt;template path &gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="463fd-219">使用 UE-V 註冊設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="463fd-219">Registers a settings location template with UE-V.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name UnregisterByTemplateId -ArgumentList &lt;template ID&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="463fd-220">使用 UE-V 登出 [設定位置] 範本。</span><span class="sxs-lookup"><span data-stu-id="463fd-220">Unregisters a settings location template with UE-V.</span></span> <span data-ttu-id="463fd-221">範本取消註冊之後，UE-V 就不會再同步處理在電腦之間的範本中定義的設定。</span><span class="sxs-lookup"><span data-stu-id="463fd-221">As soon as a template is unregistered, UE-V no longer synchronizes the settings that are defined in the template between computers.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name Update -ArgumentList &lt;template path&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="463fd-222">使用 UE-V 更新設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="463fd-222">Updates a settings location template with UE-V.</span></span> <span data-ttu-id="463fd-223">新範本的版本必須比現有範本更新。</span><span class="sxs-lookup"><span data-stu-id="463fd-223">The new template should be a newer version than the existing one.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class MachineConfiguredWindows8App -Name RemoveApp -ArgumentList &lt;package family name | package family name&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="463fd-224">從電腦 Windows app 清單移除一或多個 Windows 應用程式。</span><span class="sxs-lookup"><span data-stu-id="463fd-224">Removes one or more Windows apps from the computer Windows app list.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class UserConfiguredWindows8App -Name RemoveApp -ArgumentList &lt;package family name | package family name&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="463fd-225">從目前使用者的 Windows 應用程式清單移除一或多個 Windows 應用程式。</span><span class="sxs-lookup"><span data-stu-id="463fd-225">Removes one or more Windows apps from the current user Windows app list.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name DisableByTemplateId -ArgumentList &lt;template ID&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="463fd-226">使用 UE-V 停用一或多個設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="463fd-226">Disables one or more settings location templates with UE-V.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class MachineConfiguredWindows8App -Name DisableApp -ArgumentList &lt;package family name | package family name&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="463fd-227">停用電腦視窗 app 清單中的一個或多個 Windows 應用程式。</span><span class="sxs-lookup"><span data-stu-id="463fd-227">Disables one or more Windows apps in the computer Windows app list.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class UserConfiguredWindows8App -Name DisableApp -ArgumentList &lt;package family name | package family name&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="463fd-228">停用目前使用者 Windows 應用程式清單中的一個或多個 Windows 應用程式。</span><span class="sxs-lookup"><span data-stu-id="463fd-228">Disables one or more Windows apps in the current user Windows app list.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name EnableByTemplateId -ArgumentList &lt;template ID&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="463fd-229">使用 UE-V 啟用 [設定位置] 範本。</span><span class="sxs-lookup"><span data-stu-id="463fd-229">Enables a settings location template with UE-V.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class MachineConfiguredWindows8App -Name EnableApp -ArgumentList &lt;package family name | package family name&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="463fd-230">啟用電腦 Windows 應用程式清單中的 Windows 應用程式。</span><span class="sxs-lookup"><span data-stu-id="463fd-230">Enables Windows apps in the computer Windows app list.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class UserConfiguredWindows8App -Name EnableApp -ArgumentList &lt;package family name | package family name&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="463fd-231">啟用目前使用者的 windows 應用程式清單中的 Windows 應用程式。</span><span class="sxs-lookup"><span data-stu-id="463fd-231">Enables Windows apps in the current user Windows app list.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name Validate -ArgumentList &lt;template path&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="463fd-232">判斷指定設定位置範本是否符合其 XML 架構。</span><span class="sxs-lookup"><span data-stu-id="463fd-232">Determines whether a given settings location template complies with its XML schema.</span></span></p></td>
    </tr>
    </tbody>
    </table>



~~~
**Note**  
Where a list of Package Family Names is called by the WMI command, the list must be in quotes and separated by a pipe symbol, for example, `"<package family name | package family name>"`.
~~~



### <span data-ttu-id="463fd-233">使用 Windows PowerShell 部署 UE-V Agent</span><span class="sxs-lookup"><span data-stu-id="463fd-233">Deploying the UE-V Agent using Windows PowerShell</span></span>

**<span data-ttu-id="463fd-234">如何使用 Windows PowerShell 部署 UE-V Agent</span><span class="sxs-lookup"><span data-stu-id="463fd-234">How to deploy the UE-V Agent by using Windows PowerShell</span></span>**

1.  <span data-ttu-id="463fd-235">在易存取的網路共用中暫存 UE-V Agent 安裝套件。</span><span class="sxs-lookup"><span data-stu-id="463fd-235">Stage the UE-V Agent installation package in an accessible network share.</span></span>

    **<span data-ttu-id="463fd-236">注意</span><span class="sxs-lookup"><span data-stu-id="463fd-236">Note</span></span>**  
    <span data-ttu-id="463fd-237">使用 AgentSetup.exe 來部署32位與64位的 UE-V Agent 版本。</span><span class="sxs-lookup"><span data-stu-id="463fd-237">Use AgentSetup.exe to deploy both 32-bit and 64-bit versions of the UE-V Agent.</span></span> <span data-ttu-id="463fd-238">Windows Installer 套件、AgentSetupx86.msi 和 AgentSetupx64.msi，都可供每個架構使用。</span><span class="sxs-lookup"><span data-stu-id="463fd-238">The Windows Installer packages, AgentSetupx86.msi and AgentSetupx64.msi, are available for each architecture.</span></span> <span data-ttu-id="463fd-239">若要在稍後使用安裝檔案卸載 UE-V Agent，您必須使用相同的檔案類型。</span><span class="sxs-lookup"><span data-stu-id="463fd-239">To uninstall the UE-V Agent at a later time by using the installation file, you must use the same file type.</span></span>



2.  <span data-ttu-id="463fd-240">使用下列其中一個 Windows PowerShell 命令來安裝 UE-V Agent。</span><span class="sxs-lookup"><span data-stu-id="463fd-240">Use one of the following Windows PowerShell commands to install the UE-V Agent.</span></span>

    -   `& AgentSetup.exe /quiet /norestart /log "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

    -   `& msiexec.exe /i "<path to msi file>" /quiet /norestart /l*v "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

<span data-ttu-id="463fd-241">**為 ue-v 提供建議**嗎？</span><span class="sxs-lookup"><span data-stu-id="463fd-241">**Got a suggestion for UE-V**?</span></span> <span data-ttu-id="463fd-242">在[此](http://uev.uservoice.com/forums/280428-microsoft-user-experience-virtualization)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="463fd-242">Add or vote on suggestions [here](http://uev.uservoice.com/forums/280428-microsoft-user-experience-virtualization).</span></span> <span data-ttu-id="463fd-243">是否**有 ue-v 問題**？</span><span class="sxs-lookup"><span data-stu-id="463fd-243">**Got a UE-V issue**?</span></span> <span data-ttu-id="463fd-244">使用[Ue-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopuev)。</span><span class="sxs-lookup"><span data-stu-id="463fd-244">Use the [UE-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopuev).</span></span>

## <span data-ttu-id="463fd-245">相關主題</span><span class="sxs-lookup"><span data-stu-id="463fd-245">Related topics</span></span>


[<span data-ttu-id="463fd-246">使用 Windows PowerShell 和 WMI 管理 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="463fd-246">Administering UE-V 2.x with Windows PowerShell and WMI</span></span>](administering-ue-v-2x-with-windows-powershell-and-wmi-both-uevv2.md)

[<span data-ttu-id="463fd-247">管理 UE-V 2。</span><span class="sxs-lookup"><span data-stu-id="463fd-247">Administering UE-V 2.x</span></span>](administering-ue-v-2x-new-uevv2.md)









