---
title: 搭配虛擬化應用程式在虛擬環境內執行本機安裝的應用程式
description: 搭配虛擬化應用程式在虛擬環境內執行本機安裝的應用程式
author: dansimp
ms.assetid: a8affa46-f1f7-416c-8125-9595cfbfdbc7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 10c0f3f3c8a1b88cf1a98fd64fe8f7f49b597a91
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800312"
---
# <span data-ttu-id="e0f1f-103">搭配虛擬化應用程式在虛擬環境內執行本機安裝的應用程式</span><span class="sxs-lookup"><span data-stu-id="e0f1f-103">Running a Locally Installed Application Inside a Virtual Environment with Virtualized Applications</span></span>


<span data-ttu-id="e0f1f-104">您可以在虛擬環境中執行本機安裝的應用程式，以及使用 Microsoft 應用程式虛擬化（App-v）虛擬化的應用程式。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-104">You can run a locally installed application in a virtual environment, alongside applications that have been virtualized by using Microsoft Application Virtualization (App-V).</span></span> <span data-ttu-id="e0f1f-105">如果您執行下列動作，您可能會想要這樣做：</span><span class="sxs-lookup"><span data-stu-id="e0f1f-105">You might want to do this if you:</span></span>

-   <span data-ttu-id="e0f1f-106">想要在用戶端電腦上本機安裝並執行應用程式，但想要虛擬化並執行與該本機應用程式搭配使用的特定外掛程式。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-106">Want to install and run an application locally on client computers, but want to virtualize and run specific plug-ins that work with that local application.</span></span>

-   <span data-ttu-id="e0f1f-107">正在針對 App-v 用戶端套件進行疑難排解，並想要在 App V 虛擬環境中開啟本機應用程式。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-107">Are troubleshooting an App-V client package and want to open a local application within the App-V virtual environment.</span></span>

<span data-ttu-id="e0f1f-108">使用下列任何一種方法，在 App-v 虛擬環境內開啟本機應用程式：</span><span class="sxs-lookup"><span data-stu-id="e0f1f-108">Use any of the following methods to open a local application inside the App-V virtual environment:</span></span>

-   [<span data-ttu-id="e0f1f-109">RunVirtual 登錄機碼</span><span class="sxs-lookup"><span data-stu-id="e0f1f-109">RunVirtual registry key</span></span>](#bkmk-runvirtual-regkey)

-   [<span data-ttu-id="e0f1f-110">AppvClientPackage PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="e0f1f-110">Get-AppvClientPackage PowerShell cmdlet</span></span>](#bkmk-get-appvclientpackage-posh)

-   [<span data-ttu-id="e0f1f-111">命令列開關/appvpid： &lt; PID&gt;</span><span class="sxs-lookup"><span data-stu-id="e0f1f-111">Command line switch /appvpid:&lt;PID&gt;</span></span>](#bkmk-cl-switch-appvpid)

-   [<span data-ttu-id="e0f1f-112">命令列掛鉤開關/appvve： &lt; GUID&gt;</span><span class="sxs-lookup"><span data-stu-id="e0f1f-112">Command line hook switch /appvve:&lt;GUID&gt;</span></span>](#bkmk-cl-hook-switch-appvve)

<span data-ttu-id="e0f1f-113">每個方法實質上都是相同的工作，但是根據虛擬化應用程式是否已在執行中，某些方法可能比其他應用程式更適合一些。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-113">Each method accomplishes essentially the same task, but some methods may be better suited for some applications than others, depending on whether the virtualized application is already running.</span></span>

## <a href="" id="bkmk-runvirtual-regkey"></a><span data-ttu-id="e0f1f-114">RunVirtual 登錄機碼</span><span class="sxs-lookup"><span data-stu-id="e0f1f-114">RunVirtual registry key</span></span>


<span data-ttu-id="e0f1f-115">若要將本機安裝的應用程式新增到套件或連線群組的虛擬環境中，您可以 `RunVirtual` 在 [登錄編輯程式] 中新增子機碼，如下列各節所述。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-115">To add a locally installed application to a package or to a connection group’s virtual environment, you add a subkey to the `RunVirtual` registry key in the Registry Editor, as described in the following sections.</span></span>

<span data-ttu-id="e0f1f-116">沒有可用來管理此登錄機碼的群組原則設定，因此您必須使用 System Center Configuration Manager 或其他電子軟體發佈（ESD）系統，或手動編輯註冊表。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-116">There is no Group Policy setting available to manage this registry key, so you have to use System Center Configuration Manager or another electronic software distribution (ESD) system, or manually edit the registry.</span></span>

### <a href="" id="bkmk-"></a><span data-ttu-id="e0f1f-117">使用 RunVirtual 時的發佈套件支援的方法</span><span class="sxs-lookup"><span data-stu-id="e0f1f-117">Supported methods of publishing packages when using RunVirtual</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="e0f1f-118">App-V 版本</span><span class="sxs-lookup"><span data-stu-id="e0f1f-118">App-V version</span></span></th>
<th align="left"><span data-ttu-id="e0f1f-119">支援的發佈方法</span><span class="sxs-lookup"><span data-stu-id="e0f1f-119">Supported publishing methods</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="e0f1f-120">App-V 5.0 SP3</span><span class="sxs-lookup"><span data-stu-id="e0f1f-120">App-V 5.0 SP3</span></span></p></td>
<td align="left"><p><span data-ttu-id="e0f1f-121">全域發佈或供使用者使用</span><span class="sxs-lookup"><span data-stu-id="e0f1f-121">Published globally or to the user</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="e0f1f-122">App-v 5.0 透過 App-v 5.0 SP2</span><span class="sxs-lookup"><span data-stu-id="e0f1f-122">App-V 5.0 through App-V 5.0 SP2</span></span></p></td>
<td align="left"><p><span data-ttu-id="e0f1f-123">僅限全域發佈</span><span class="sxs-lookup"><span data-stu-id="e0f1f-123">Published globally only</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="e0f1f-124">建立子機碼的步驟</span><span class="sxs-lookup"><span data-stu-id="e0f1f-124">Steps to create the subkey</span></span>

1.  <span data-ttu-id="e0f1f-125">使用下表中的資訊，以可執行檔名稱（例如**MyApp.exe**）建立新的登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-125">Using the information in the following table, create a new registry key using the name of the executable file, for example, **MyApp.exe**.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="e0f1f-126">套件發佈方法</span><span class="sxs-lookup"><span data-stu-id="e0f1f-126">Package publishing method</span></span></th>
    <th align="left"><span data-ttu-id="e0f1f-127">建立登錄機碼的位置</span><span class="sxs-lookup"><span data-stu-id="e0f1f-127">Where to create the registry key</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="e0f1f-128">全域發佈</span><span class="sxs-lookup"><span data-stu-id="e0f1f-128">Published globally</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e0f1f-129">HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\AppV\Client\RunVirtual</span><span class="sxs-lookup"><span data-stu-id="e0f1f-129">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\AppV\Client\RunVirtual</span></span></p>
    <p><strong><span data-ttu-id="e0f1f-130">範例 </strong> ： HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\AppV\Client\RunVirtual\MyApp.exe</span><span class="sxs-lookup"><span data-stu-id="e0f1f-130">Example</strong>: HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\AppV\Client\RunVirtual\MyApp.exe</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="e0f1f-131">發佈給使用者</span><span class="sxs-lookup"><span data-stu-id="e0f1f-131">Published to the user</span></span></p></td>
    <td align="left"><p><span data-ttu-id="e0f1f-132">HKEY_CURRENT_USER \SOFTWARE\Microsoft\AppV\Client\RunVirtual</span><span class="sxs-lookup"><span data-stu-id="e0f1f-132">HKEY_CURRENT_USER\SOFTWARE\Microsoft\AppV\Client\RunVirtual</span></span></p>
    <p><strong><span data-ttu-id="e0f1f-133">範例 </strong> ： HKEY_CURRENT_USER \SOFTWARE\Microsoft\AppV\Client\RunVirtual\MyApp.exe</span><span class="sxs-lookup"><span data-stu-id="e0f1f-133">Example</strong>: HKEY_CURRENT_USER \SOFTWARE\Microsoft\AppV\Client\RunVirtual\MyApp.exe</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="e0f1f-134">[連接] 群組可以包含：</span><span class="sxs-lookup"><span data-stu-id="e0f1f-134">Connection group can contain:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="e0f1f-135">僅限全域發行或僅發佈給使用者的套件</span><span class="sxs-lookup"><span data-stu-id="e0f1f-135">Packages that are published just globally or just to the user</span></span></p></li>
    <li><p><span data-ttu-id="e0f1f-136">全域發佈及使用者的套件</span><span class="sxs-lookup"><span data-stu-id="e0f1f-136">Packages that are published globally and to the user</span></span></p></li>
    </ul></td>
    <td align="left"><p><span data-ttu-id="e0f1f-137">HKEY_LOCAL_MACHINE 或 HKEY_CURRENT_USER 金鑰，但下列所有專案都必須成立：</span><span class="sxs-lookup"><span data-stu-id="e0f1f-137">Either HKEY_LOCAL_MACHINE or HKEY_CURRENT_USER key, but all of the following must be true:</span></span></p>
    <ul>
    <li><p><span data-ttu-id="e0f1f-138">如果您想要在虛擬環境中包含多個套件，您必須將它們包含在已啟用的連線群組中。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-138">If you want to include multiple packages in the virtual environment, you must include them in an enabled connection group.</span></span></p></li>
    <li><p><span data-ttu-id="e0f1f-139">針對連線群組中的其中一個套件，只建立一個子機碼。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-139">Create only one subkey for one of the packages in the connection group.</span></span> <span data-ttu-id="e0f1f-140">例如，如果您有一個全域發佈的套件，以及另一個發佈給使用者的套件，您就會為其中一個套件建立子機碼，但不能同時為這兩者。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-140">If, for example, you have one package that is published globally, and another package that is published to the user, you create a subkey for either of these packages, but not both.</span></span> <span data-ttu-id="e0f1f-141">雖然您只為其中一個套件建立子機，但是連線群組中的所有套件，加上本機應用程式，都可在虛擬環境中使用。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-141">Although you create a subkey for only one of the packages, all of the packages in the connection group, plus the local application, will be available in the virtual environment.</span></span></p></li>
    <li><p><span data-ttu-id="e0f1f-142">您要在其中建立子機碼的索引鍵必須符合您用於套件的發佈方法。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-142">The key under which you create the subkey must match the publishing method you used for the package.</span></span></p>
    <p><span data-ttu-id="e0f1f-143">例如，如果您已將套件發佈給使用者，您必須在下建立子機 <code>HKEY_CURRENT_USER\SOFTWARE\Microsoft\AppV\Client\RunVirtual</code> 。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-143">For example, if you published the package to the user, you must create the subkey under <code>HKEY_CURRENT_USER\SOFTWARE\Microsoft\AppV\Client\RunVirtual</code>.</span></span></p></li>
    </ul></td>
    </tr>
    </tbody>
    </table>

     

2.  <span data-ttu-id="e0f1f-144">將新的登錄子機碼的值設定為套件的 PackageId 和 VersionId，並以底線分隔值。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-144">Set the new registry subkey’s value to the PackageId and VersionId of the package, separating the values with an underscore.</span></span>

    <span data-ttu-id="e0f1f-145">**語法**： &lt; PackageId &gt; \ _ &lt; VersionId&gt;</span><span class="sxs-lookup"><span data-stu-id="e0f1f-145">**Syntax**: &lt;PackageId&gt;\_&lt;VersionId&gt;</span></span>

    <span data-ttu-id="e0f1f-146">**範例**： 4c909996-afc9-4352-b606-0b74542a09c1 \ _Be463724-Oct1-48f1-8604-c4bd7ca92fa</span><span class="sxs-lookup"><span data-stu-id="e0f1f-146">**Example**: 4c909996-afc9-4352-b606-0b74542a09c1\_be463724-Oct1-48f1-8604-c4bd7ca92fa</span></span>

    <span data-ttu-id="e0f1f-147">上一個範例中的應用程式會產生如下所示的註冊表匯出檔案（.reg 檔案）：</span><span class="sxs-lookup"><span data-stu-id="e0f1f-147">The application in the previous example would produce a registry export file (.reg file) like the following:</span></span>

    ``` syntax
    Windows Registry Editor Version 5.00 
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\AppV\Client\RunVirtual] 
    @="" 
    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\AppV\Client\RunVirtual\MyApp.exe] 
    @="aaaaaaaa-bbbb-cccc-dddd-eeeeeeee_11111111-2222-3333-4444-555555555
    ```

## <a href="" id="bkmk-get-appvclientpackage-posh"></a><span data-ttu-id="e0f1f-148">AppvClientPackage PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="e0f1f-148">Get-AppvClientPackage PowerShell cmdlet</span></span>


<span data-ttu-id="e0f1f-149">您可以使用**AppVVirtualProcess** Cmdlet 來檢索套件名稱，然後在指定套件的虛擬環境中啟動處理常式。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-149">You can use the **Start-AppVVirtualProcess** cmdlet to retrieve the package name and then start a process within the specified package's virtual environment.</span></span> <span data-ttu-id="e0f1f-150">這個方法可讓您在 App-v 套件的內容中啟動任何命令，不論套件目前是否正在執行。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-150">This method lets you launch any command within the context of an App-V package, regardless of whether the package is currently running.</span></span>

<span data-ttu-id="e0f1f-151">使用下列範例語法，並將套件的名稱取代為\*\* &lt; 套件 &gt; \*\*：</span><span class="sxs-lookup"><span data-stu-id="e0f1f-151">Use the following example syntax, and substitute the name of your package for **&lt;Package&gt;**:</span></span>

`$AppVName = Get-AppvClientPackage <Package>`

`Start-AppvVirtualProcess -AppvClientObject $AppVName cmd.exe`

<span data-ttu-id="e0f1f-152">如果您不知道套件的確切名稱，您可以使用命令列**AppvClientPackage \ \* executable\\** <em> ，其中 \*\*可執行檔 </em> \*是應用程式的名稱，例如： AppvClientPackage \ \* Word \ \*。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-152">If you don’t know the exact name of your package, you can use the command line **Get-AppvClientPackage \*executable\\**<em>, where \**executable</em>* is the name of the application, for example: Get-AppvClientPackage \*Word\*.</span></span>

## <a href="" id="bkmk-cl-switch-appvpid"></a><span data-ttu-id="e0f1f-153">命令列開關/appvpid： &lt; PID&gt;</span><span class="sxs-lookup"><span data-stu-id="e0f1f-153">Command line switch /appvpid:&lt;PID&gt;</span></span>


<span data-ttu-id="e0f1f-154">您可以將 \*\*/appvpid： &lt; PID &gt; \*\*開關套用到任何命令，讓您在選取的虛擬進程內執行該命令，方法是指定其進程識別碼（PID）。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-154">You can apply the **/appvpid:&lt;PID&gt;** switch to any command, which enables that command to run within a virtual process that you select by specifying its process ID (PID).</span></span> <span data-ttu-id="e0f1f-155">使用這個方法會在與已執行的可執行檔相同的 App-v 環境中啟動新的可執行檔。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-155">Using this method launches the new executable in the same App-V environment as an executable that is already running.</span></span>

<span data-ttu-id="e0f1f-156">範例：</span><span class="sxs-lookup"><span data-stu-id="e0f1f-156">Example:</span></span> `cmd.exe /appvpid:8108`

<span data-ttu-id="e0f1f-157">若要尋找 App-v 進程的進程識別碼（PID），請從提升許可權的命令提示字元執行命令**tasklist.exe** 。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-157">To find the process ID (PID) of your App-V process, run the command **tasklist.exe** from an elevated command prompt.</span></span>

## <a href="" id="bkmk-cl-hook-switch-appvve"></a><span data-ttu-id="e0f1f-158">命令列掛鉤開關/appvve： &lt; GUID&gt;</span><span class="sxs-lookup"><span data-stu-id="e0f1f-158">Command line hook switch /appvve:&lt;GUID&gt;</span></span>


<span data-ttu-id="e0f1f-159">這個選項可讓您在 App-v 套件的虛擬環境中執行本機命令。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-159">This switch lets you run a local command within the virtual environment of an App-V package.</span></span> <span data-ttu-id="e0f1f-160">與 **/appvid**切換（虛擬環境必須已執行）不同，此切換可讓您啟動虛擬環境。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-160">Unlike the **/appvid** switch, where the virtual environment must already be running, this switch enables you to start the virtual environment.</span></span>

<span data-ttu-id="e0f1f-161">句法</span><span class="sxs-lookup"><span data-stu-id="e0f1f-161">Syntax:</span></span> `cmd.exe /appvve:<PACKAGEGUID_VERSIONGUID>`

<span data-ttu-id="e0f1f-162">範例：</span><span class="sxs-lookup"><span data-stu-id="e0f1f-162">Example:</span></span> `cmd.exe /appvve:aaaaaaaa-bbbb-cccc-dddd-eeeeeeee_11111111-2222-3333-4444-55555555`

<span data-ttu-id="e0f1f-163">若要取得應用程式的套件 GUID 與版本 GUID，請執行**AppvClientPackage** Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-163">To get the package GUID and version GUID of your application, run the **Get-AppvClientPackage** cmdlet.</span></span> <span data-ttu-id="e0f1f-164">將 **/appvve**開關串連成下列：</span><span class="sxs-lookup"><span data-stu-id="e0f1f-164">Concatenate the **/appvve** switch with the following:</span></span>

-   <span data-ttu-id="e0f1f-165">冒號</span><span class="sxs-lookup"><span data-stu-id="e0f1f-165">A colon</span></span>

-   <span data-ttu-id="e0f1f-166">所需套件的封裝 GUID</span><span class="sxs-lookup"><span data-stu-id="e0f1f-166">Package GUID of the desired package</span></span>

-   <span data-ttu-id="e0f1f-167">底線</span><span class="sxs-lookup"><span data-stu-id="e0f1f-167">An underscore</span></span>

-   <span data-ttu-id="e0f1f-168">所需套件的版本識別碼</span><span class="sxs-lookup"><span data-stu-id="e0f1f-168">Version ID of the desired package</span></span>

<span data-ttu-id="e0f1f-169">如果您不知道套件的確切名稱，請使用命令列**AppvClientPackage \ \* executable\\** <em> ，其中 \*\*可執行檔 </em> \*是應用程式的名稱，例如： AppvClientPackage \ \* Word \ \*。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-169">If you don’t know the exact name of your package, use the command line **Get-AppvClientPackage \*executable\\**<em>, where \**executable</em>* is the name of the application, for example: Get-AppvClientPackage \*Word\*.</span></span>

<span data-ttu-id="e0f1f-170">這個方法可讓您在 App-v 套件的內容中啟動任何命令，不論套件目前是否正在執行。</span><span class="sxs-lookup"><span data-stu-id="e0f1f-170">This method lets you launch any command within the context of an App-V package, regardless of whether the package is currently running.</span></span>






## <span data-ttu-id="e0f1f-171">相關主題</span><span class="sxs-lookup"><span data-stu-id="e0f1f-171">Related topics</span></span>


[<span data-ttu-id="e0f1f-172">App-V 5.0 技術參考資訊</span><span class="sxs-lookup"><span data-stu-id="e0f1f-172">Technical Reference for App-V 5.0</span></span>](technical-reference-for-app-v-50.md)

 

 





