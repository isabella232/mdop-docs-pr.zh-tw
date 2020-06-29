---
title: 使用 PowerShell 與 WMI 來管理 UE-V 1.0 設定位置範本
description: 使用 PowerShell 與 WMI 來管理 UE-V 1.0 設定位置範本
author: dansimp
ms.assetid: 4b911c78-a5e9-4199-bfeb-72ab764d47c1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d8dab0997cdfaf7c96862fcce4bc012c3edfe0c0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800107"
---
# <span data-ttu-id="ce5c0-103">使用 PowerShell 與 WMI 來管理 UE-V 1.0 設定位置範本</span><span class="sxs-lookup"><span data-stu-id="ce5c0-103">Managing UE-V 1.0 Settings Location Templates Using PowerShell and WMI</span></span>


<span data-ttu-id="ce5c0-104">Microsoft 使用者體驗虛擬化（UE-V）使用設定位置範本（XML 檔案），定義使用者體驗虛擬化所捕獲並套用的設定。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-104">Microsoft User Experience Virtualization (UE-V) uses settings location templates (XML files) that define the settings captured and applied by User Experience Virtualization.</span></span> <span data-ttu-id="ce5c0-105">UE-V 包含一組標準設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-105">UE-V includes a set of standard settings location templates.</span></span> <span data-ttu-id="ce5c0-106">它也包含 UE-V 發生器工具，可讓您建立自訂設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-106">It also includes the UE-V Generator tool that enables you to create custom settings location templates.</span></span> <span data-ttu-id="ce5c0-107">在您建立並部署設定位置範本之後，您可以使用 PowerShell 或 WMI 管理這些範本。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-107">After you create and deploy settings location templates you can manage those templates using PowerShell or WMI.</span></span>

## <span data-ttu-id="ce5c0-108">使用 WMI 和 PowerShell 管理設定位置範本</span><span class="sxs-lookup"><span data-stu-id="ce5c0-108">Manage settings location templates with WMI and PowerShell</span></span>


<span data-ttu-id="ce5c0-109">UE-V 的 WMI 和 PowerShell 功能包括啟用、停用、註冊、更新及登出設定位置範本的功能。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-109">The WMI and PowerShell features of UE-V include the ability to enable, disable, register, update, and unregister settings location templates.</span></span> <span data-ttu-id="ce5c0-110">您可以使用這些功能，透過 UE-V agent 程式來自動註冊、更新或登出範本。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-110">By using these features, you can automate the process of registering, updating, or unregistering templates with the UE-V agent.</span></span> <span data-ttu-id="ce5c0-111">您也可以使用 WMI 和 PowerShell 命令，手動註冊範本。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-111">You can also manually register templates using WMI and PowerShell commands.</span></span> <span data-ttu-id="ce5c0-112">透過將這些功能與電子軟體發佈方案、群組原則或其他自動部署方法（例如腳本）搭配使用，您就可以進一步自動化該程式。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-112">By using these features in conjunction with an electronic software distribution solution, Group Policy, or another automated deployment method such as a script, you can further automate that process.</span></span>

<span data-ttu-id="ce5c0-113">您必須具備系統管理員許可權，才能更新、註冊或登出設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-113">You must have administrator permissions to update, register, or unregister a settings location template.</span></span> <span data-ttu-id="ce5c0-114">啟用或停用範本不需要系統管理員許可權。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-114">Administrator permissions are not required to enable or disable templates.</span></span>

**<span data-ttu-id="ce5c0-115">使用 PowerShell 管理設定位置範本</span><span class="sxs-lookup"><span data-stu-id="ce5c0-115">To manage settings location templates with PowerShell</span></span>**

1.  <span data-ttu-id="ce5c0-116">使用具有系統管理員許可權的帳戶來開啟 Windows PowerShell 視窗。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-116">Use an account with administrator rights to open a Windows PowerShell window.</span></span> <span data-ttu-id="ce5c0-117">若要匯入**MICROSOFT Ue-v PowerShell**模組，請在 PowerShell 命令提示字元中輸入下列命令。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-117">To import the **Microsoft UE-V PowerShell** module, type the following command at the PowerShell command prompt.</span></span>

    ``` syntax
    Import-module UEV
    ```

2.  <span data-ttu-id="ce5c0-118">使用下列 PowerShell Cmdlet 來註冊及管理 UE-V 設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-118">Use the following PowerShell cmdlets to register and manage the UE-V settings location templates.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong><span data-ttu-id="ce5c0-119">PowerShell 命令</span><span class="sxs-lookup"><span data-stu-id="ce5c0-119">PowerShell command</span></span></strong></th>
    <th align="left"><strong><span data-ttu-id="ce5c0-120">描述</span><span class="sxs-lookup"><span data-stu-id="ce5c0-120">Description</span></span></strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="ce5c0-121">UevTemplate</span><span class="sxs-lookup"><span data-stu-id="ce5c0-121">Get-UevTemplate</span></span></p></td>
    <td align="left"><p><span data-ttu-id="ce5c0-122">列出電腦上已註冊的所有設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-122">Lists all the settings location templates registered on the computer.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="ce5c0-123">Register-UevTemplate</span><span class="sxs-lookup"><span data-stu-id="ce5c0-123">Register-UevTemplate</span></span></p></td>
    <td align="left"><p><span data-ttu-id="ce5c0-124">使用 UE-V 註冊設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-124">Registers a settings location template with UE-V.</span></span> <span data-ttu-id="ce5c0-125">範本註冊之後，UE-V 會同步處理在已註冊範本的電腦之間，在範本中定義的設定。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-125">Once a template is registered, UE-V will synchronize the settings that are defined in the template between computers that have the template registered.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="ce5c0-126">取消註冊-UevTemplate</span><span class="sxs-lookup"><span data-stu-id="ce5c0-126">Unregister-UevTemplate</span></span></p></td>
    <td align="left"><p><span data-ttu-id="ce5c0-127">使用 UE-V 登出 [設定位置] 範本。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-127">Unregisters a settings location template with UE-V.</span></span> <span data-ttu-id="ce5c0-128">範本取消註冊之後，UE-V 就不會再同步處理在電腦之間的範本中定義的設定。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-128">As soon as a template is unregistered, UE-V will no longer synchronize the settings that are defined in the template between computers.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="ce5c0-129">更新-UevTemplate</span><span class="sxs-lookup"><span data-stu-id="ce5c0-129">Update-UevTemplate</span></span></p></td>
    <td align="left"><p><span data-ttu-id="ce5c0-130">使用最新版本的範本更新設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-130">Updates a settings location template with a more recent version of the template.</span></span> <span data-ttu-id="ce5c0-131">新範本的版本必須晚于現有範本。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-131">The new template should have a version that is later than the existing one.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="ce5c0-132">Disable-UevTemplate</span><span class="sxs-lookup"><span data-stu-id="ce5c0-132">Disable-UevTemplate</span></span></p></td>
    <td align="left"><p><span data-ttu-id="ce5c0-133">停用電腦目前使用者的設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-133">Disables a settings location template for the current user of the computer.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="ce5c0-134">Enable-UevTemplate</span><span class="sxs-lookup"><span data-stu-id="ce5c0-134">Enable-UevTemplate</span></span></p></td>
    <td align="left"><p><span data-ttu-id="ce5c0-135">啟用電腦目前使用者的設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-135">Enables a settings location template for the current user of the computer.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="ce5c0-136">Test-UevTemplate</span><span class="sxs-lookup"><span data-stu-id="ce5c0-136">Test-UevTemplate</span></span></p></td>
    <td align="left"><p><span data-ttu-id="ce5c0-137">判斷指定設定位置範本是否符合其 XML 架構。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-137">Determines whether a given settings location template complies with its XML schema.</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

<span data-ttu-id="ce5c0-138">UE-V PowerShell 功能可讓您管理企業中部署的一組設定範本。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-138">The UE-V PowerShell features allow you to manage a group of settings templates deployed in your enterprise.</span></span> <span data-ttu-id="ce5c0-139">若要使用 PowerShell 管理範本群組，請執行下列動作。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-139">To manage a group of templates using PowerShell, do the following.</span></span>

**<span data-ttu-id="ce5c0-140">使用 PowerShell 管理設定位置範本群組</span><span class="sxs-lookup"><span data-stu-id="ce5c0-140">To manage a group of settings location templates with PowerShell</span></span>**

1.  <span data-ttu-id="ce5c0-141">修改或更新所需的設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-141">Modify or update the desired settings location templates.</span></span>

2.  <span data-ttu-id="ce5c0-142">將所需的設定位置範本部署到本機電腦可存取的資料夾。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-142">Deploy the desired settings location templates to a folder accessible to the local computer.</span></span>

3.  <span data-ttu-id="ce5c0-143">在本機電腦上，以系統管理員許可權開啟 Windows PowerShell 視窗。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-143">On the local computer, open a Windows PowerShell window with administrator rights.</span></span>

4.  <span data-ttu-id="ce5c0-144">若要匯入 Microsoft UE-V PowerShell 模組，請輸入下列命令。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-144">Import the Microsoft UE-V PowerShell module, by typing the following command.</span></span>

    ``` syntax
    Import-module UEV
    ```

5.  <span data-ttu-id="ce5c0-145">輸入下列命令，以取消註冊所有先前已註冊的範本版本。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-145">Unregister all the previously registered versions of the templates by typing the following command.</span></span>

    ``` syntax
    Get-UevTemplate | Unregister-UevTemplate
    ```

    <span data-ttu-id="ce5c0-146">這將會登出電腦上的所有活動範本。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-146">This will unregister all active templates on the computer.</span></span>

6.  <span data-ttu-id="ce5c0-147">輸入下列命令來註冊更新的範本。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-147">Register the updated templates by typing the following command.</span></span>

    ``` syntax
    Register-UevTemplate <path to template folder>\*.xml
    ```

    <span data-ttu-id="ce5c0-148">這會註冊位於指定範本資料夾中的所有設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-148">This will register all of the settings location templates located in the specified template folder.</span></span>

<span data-ttu-id="ce5c0-149">使用者體驗虛擬化提供下列一組 WMI 命令。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-149">User Experience Virtualization provides the following set of WMI commands.</span></span> <span data-ttu-id="ce5c0-150">系統管理員可以使用這些介面，從 Windows PowerShell 管理設定位置範本，並自動執行範本管理工作。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-150">Administrators can use these interfaces to manage settings location templates from Windows PowerShell and automate template administrative tasks.</span></span>

**<span data-ttu-id="ce5c0-151">使用 WMI 管理設定位置範本</span><span class="sxs-lookup"><span data-stu-id="ce5c0-151">To manage settings location templates with WMI</span></span>**

1.  <span data-ttu-id="ce5c0-152">使用具有系統管理員許可權的帳戶來開啟 Windows PowerShell 視窗。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-152">Use an account with administrator rights to open a Windows PowerShell window.</span></span>

2.  <span data-ttu-id="ce5c0-153">使用下列 WMI 命令來註冊及管理 UE-V 設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-153">Use the following WMI commands to register and manage the UE-V settings location templates.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong><span data-ttu-id="ce5c0-154">PowerShell 命令</span><span class="sxs-lookup"><span data-stu-id="ce5c0-154">PowerShell command</span></span></strong></p></td>
    <td align="left"><p><strong><span data-ttu-id="ce5c0-155">描述</span><span class="sxs-lookup"><span data-stu-id="ce5c0-155">Description</span></span></strong></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="ce5c0-156">WmiObject-Namespace root\Microsoft\UEV SettingsLocationTemplate |選取-Object TemplateId、TemplateName、TemplateVersion、Enabled |[格式]-[表格自動調整]</span><span class="sxs-lookup"><span data-stu-id="ce5c0-156">Get-WmiObject -Namespace root\Microsoft\UEV SettingsLocationTemplate | Select-Object TemplateId,TemplateName, TemplateVersion,Enabled | Format-Table -Autosize</span></span></p></td>
    <td align="left"><p><span data-ttu-id="ce5c0-157">列出電腦已註冊的所有設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-157">Lists all the settings location templates registered for the computer.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="ce5c0-158">WmiMethod-命名空間 root\Microsoft\UEV-Class SettingsLocationTemplate-Name Register-ArgumentList &lt; 範本路徑&gt;</span><span class="sxs-lookup"><span data-stu-id="ce5c0-158">Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name Register -ArgumentList &lt;template path &gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="ce5c0-159">使用 UE-V 註冊設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-159">Registers a settings location template with UE-V.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="ce5c0-160">WmiMethod-命名空間 root\Microsoft\UEV-Class SettingsLocationTemplate-Name UnregisterByTemplateId-ArgumentList &lt; 範本識別碼&gt;</span><span class="sxs-lookup"><span data-stu-id="ce5c0-160">Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name UnregisterByTemplateId -ArgumentList &lt;template ID&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="ce5c0-161">使用 UE-V 登出 [設定位置] 範本。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-161">Unregisters a settings location template with UE-V.</span></span> <span data-ttu-id="ce5c0-162">範本取消註冊之後，UE-V 就不會再同步處理在電腦之間的範本中定義的設定。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-162">As soon as a template is unregistered, UE-V will no longer synchronize the settings that are defined in the template between computers.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="ce5c0-163">WmiMethod-命名空間 root\Microsoft\UEV-Class SettingsLocationTemplate-Name EnableByTemplateId-ArgumentList &lt; 範本識別碼&gt;</span><span class="sxs-lookup"><span data-stu-id="ce5c0-163">Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name EnableByTemplateId -ArgumentList &lt;template ID&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="ce5c0-164">使用 UE-V 啟用設定位置範本</span><span class="sxs-lookup"><span data-stu-id="ce5c0-164">Enables a settings location template with UE-V</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="ce5c0-165">WmiMethod-命名空間 root\Microsoft\UEV-Class SettingsLocationTemplate-Name DisableByTemplateId-ArgumentList &lt; 範本識別碼&gt;</span><span class="sxs-lookup"><span data-stu-id="ce5c0-165">Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name DisableByTemplateId -ArgumentList &lt;template ID&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="ce5c0-166">使用 UE-V 停用設定位置範本</span><span class="sxs-lookup"><span data-stu-id="ce5c0-166">Disables a settings location template with UE-V</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="ce5c0-167">WmiMethod-命名空間 root\Microsoft\UEV-類別 SettingsLocationTemplate-名稱更新-ArgumentList &lt; 範本路徑&gt;</span><span class="sxs-lookup"><span data-stu-id="ce5c0-167">Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name Update -ArgumentList &lt;template path&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="ce5c0-168">使用 UE-V 更新設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-168">Updates a settings location template with UE-V.</span></span> <span data-ttu-id="ce5c0-169">新範本的版本必須高於現有範本。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-169">The new template should have a version that is higher than the existing one.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="ce5c0-170">WmiMethod-命名空間 root\Microsoft\UEV-Class SettingsLocationTemplate-Name 驗證-ArgumentList &lt; 範本路徑&gt;</span><span class="sxs-lookup"><span data-stu-id="ce5c0-170">Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name Validate -ArgumentList &lt;template path&gt;</span></span></p></td>
    <td align="left"><p><span data-ttu-id="ce5c0-171">判斷指定設定位置範本是否符合其 XML 架構。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-171">Determines whether a given settings location template complies with its XML schema.</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

**<span data-ttu-id="ce5c0-172">如何使用 PowerShell 部署 UE-V agent</span><span class="sxs-lookup"><span data-stu-id="ce5c0-172">How to deploy the UE-V agent with PowerShell</span></span>**

1.  <span data-ttu-id="ce5c0-173">在易於存取的網路共用中階段進行 UE-V 安裝程式檔案。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-173">Stage the UE-V installer file in an accessible network share.</span></span>

    <span data-ttu-id="ce5c0-174">**記事** 使用 AgentSetup.exe 來部署32位與64位的 UE-V Agent 版本。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-174">**Note** Use AgentSetup.exe to deploy both 32-bit and 64-bit versions of the UE-V Agent.</span></span> <span data-ttu-id="ce5c0-175">Windows Installer 檔案版本、AgentSetupx86.msi 和 AgentSetupx64.msi，都可供每個架構使用。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-175">Windows Installer Files versions, AgentSetupx86.msi and AgentSetupx64.msi, are available for each architecture.</span></span> <span data-ttu-id="ce5c0-176">若要在稍後使用安裝檔來卸載 UE-V Agent，您必須使用相同的檔案類型。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-176">To uninstall the UE-V Agent at a later time using the installation file, you must use the same file type.</span></span>

     

2.  <span data-ttu-id="ce5c0-177">使用下列其中一個 PowerShell 命令來安裝代理程式。</span><span class="sxs-lookup"><span data-stu-id="ce5c0-177">Use one of the following PowerShell commands to install the agent.</span></span>

    `& AgentSetup.exe /quiet /norestart /log "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

    `& msiexec.exe /i "<path to msi file>" /quiet /norestart /l*v "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

## <span data-ttu-id="ce5c0-178">相關主題</span><span class="sxs-lookup"><span data-stu-id="ce5c0-178">Related topics</span></span>


[<span data-ttu-id="ce5c0-179">使用 PowerShell 與 WMI 來管理 UE-V 1.0 Agent 與套件</span><span class="sxs-lookup"><span data-stu-id="ce5c0-179">Managing the UE-V 1.0 Agent and Packages with PowerShell and WMI</span></span>](managing-the-ue-v-10-agent-and-packages-with-powershell-and-wmi.md)

[<span data-ttu-id="ce5c0-180">管理 UE-V 1.0</span><span class="sxs-lookup"><span data-stu-id="ce5c0-180">Administering UE-V 1.0</span></span>](administering-ue-v-10.md)

[<span data-ttu-id="ce5c0-181">UE-V 1.0 作業</span><span class="sxs-lookup"><span data-stu-id="ce5c0-181">Operations for UE-V 1.0</span></span>](operations-for-ue-v-10.md)

 

 





