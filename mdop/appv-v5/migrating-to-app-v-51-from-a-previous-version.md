---
title: 從舊版移轉到 App-V 5.1
description: 從舊版移轉到 App-V 5.1
author: dansimp
ms.assetid: e7ee0edc-7544-4c0a-aaca-d922a33bc1bb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7fb6ddbfed4f6fd1ae9613d2ee86361a51918a65
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800372"
---
# <span data-ttu-id="ef270-103">從舊版移轉到 App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="ef270-103">Migrating to App-V 5.1 from a Previous Version</span></span>


<span data-ttu-id="ef270-104">使用 Microsoft Application Virtualization （App-v）5.1，您可以將現有的 App-v 4.6 或 App-v 5.0 基礎結構遷移至更具彈性、整合且更輕鬆管理的 App-v 5.1 基礎結構。</span><span class="sxs-lookup"><span data-stu-id="ef270-104">With Microsoft Application Virtualization (App-V) 5.1, you can migrate your existing App-V 4.6 or App-V 5.0 infrastructure to the more flexible, integrated, and easier to manage App-V 5.1 infrastructure.</span></span>
<span data-ttu-id="ef270-105">不過，您無法直接從 App-v-V 到 App-v 5.1 的遷移，您必須先將 App 遷移至 app-v 5.0。</span><span class="sxs-lookup"><span data-stu-id="ef270-105">However, you cannot migrate directly from App-V 4.x to App-V 5.1, you must migrate to App-V 5.0 first.</span></span> <span data-ttu-id="ef270-106">如需從 App-v-V 到 App-v 5.0 的遷移的詳細資訊，請參閱[從舊版進行遷移](migrating-from-a-previous-version-app-v-50.md)</span><span class="sxs-lookup"><span data-stu-id="ef270-106">For more information on migrating from App-V 4.x to App-V 5.0, see [Migrating from a Previous Version](migrating-from-a-previous-version-app-v-50.md)</span></span>  

<span data-ttu-id="ef270-107">**記事** App-v 5.1 套件與 App-v 5.0 套件完全相同。</span><span class="sxs-lookup"><span data-stu-id="ef270-107">**Note** App-V 5.1 packages are exactly the same as App-V 5.0 packages.</span></span> <span data-ttu-id="ef270-108">版本之間沒有任何套件格式的變更，因此不需要將 App-v 5.0 套件轉換成 App-v 5.1 套件。</span><span class="sxs-lookup"><span data-stu-id="ef270-108">There has been no change in the package format between the versions and therefore, there is no need to convert App-V 5.0 packages to App-V 5.1 packages.</span></span>

<span data-ttu-id="ef270-109">如需 App-v 4.6 與 App-v 5.1 之間差異的詳細資訊，請參閱[關於 app-v 5.0](about-app-v-50.md)的**app-v 4.6 與 app-v 5.0 區段之間的差異**。</span><span class="sxs-lookup"><span data-stu-id="ef270-109">For more information about the differences between App-V 4.6 and App-V 5.1, see the **Differences between App-V 4.6 and App-V 5.0 section** of [About App-V 5.0](about-app-v-50.md).</span></span>

 

## <a href="" id="bkmk-pkgconvimprove"></a><span data-ttu-id="ef270-110">應用程式-V 5.1 套件轉換器的改良功能</span><span class="sxs-lookup"><span data-stu-id="ef270-110">Improvements to the App-V 5.1 Package Converter</span></span>


<span data-ttu-id="ef270-111">您現在可以使用套件轉換器來轉換內含腳本的 App-v 4.6 套件，而來源 .osd 檔案的登錄資訊和腳本現在已包含在套件轉換程式輸出中。</span><span class="sxs-lookup"><span data-stu-id="ef270-111">You can now use the package converter to convert App-V 4.6 packages that contain scripts, and registry information and scripts from source .osd files are now included in package converter output.</span></span>

<span data-ttu-id="ef270-112">您也可以在 `–OSDsToIncludeInPackage` Cmdlet 中使用參數， `ConvertFrom-AppvLegacyPackage` 指定哪些 osd 檔案的資訊已轉換並放在新套件中。</span><span class="sxs-lookup"><span data-stu-id="ef270-112">You can also use the `–OSDsToIncludeInPackage` parameter with the `ConvertFrom-AppvLegacyPackage` cmdlet to specify which .osd files’ information is converted and placed within the new package.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ef270-113">App-v 5.1 中的新功能</span><span class="sxs-lookup"><span data-stu-id="ef270-113">New in App-V 5.1</span></span></th>
<th align="left"><span data-ttu-id="ef270-114">App-v 5.1 之前</span><span class="sxs-lookup"><span data-stu-id="ef270-114">Prior to App-V 5.1</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ef270-115">新的 .xml 檔案是與與套件相關聯的 .osd 檔案建立的。這些檔案包括下列資訊：</span><span class="sxs-lookup"><span data-stu-id="ef270-115">New .xml files are created corresponding to the .osd files associated with a package; these files include the following information:</span></span></p>
<ul>
<li><p><span data-ttu-id="ef270-116">環境變數</span><span class="sxs-lookup"><span data-stu-id="ef270-116">environment variables</span></span></p></li>
<li><p><span data-ttu-id="ef270-117">方式</span><span class="sxs-lookup"><span data-stu-id="ef270-117">shortcuts</span></span></p></li>
<li><p><span data-ttu-id="ef270-118">檔案類型關聯</span><span class="sxs-lookup"><span data-stu-id="ef270-118">file type associations</span></span></p></li>
<li><p><span data-ttu-id="ef270-119">註冊資訊</span><span class="sxs-lookup"><span data-stu-id="ef270-119">registry information</span></span></p></li>
<li><p><span data-ttu-id="ef270-120">上下</span><span class="sxs-lookup"><span data-stu-id="ef270-120">scripts</span></span></p></li>
</ul>
<p><span data-ttu-id="ef270-121">您現在可以選擇從來原始目錄將來自 osd 檔案子集的資訊新增到使用參數的套件中 <code>-OSDsToIncludeInPackage</code> 。</span><span class="sxs-lookup"><span data-stu-id="ef270-121">You can now choose to add information from a subset of the .osd files in the source directory to the package using the <code>-OSDsToIncludeInPackage</code> parameter.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ef270-122">與套件相關聯的 .osd 檔案中所包含的登錄資訊與腳本並不包含在套件轉換器輸出中。</span><span class="sxs-lookup"><span data-stu-id="ef270-122">Registry information and scripts included in .osd files associated with a package were not included in package converter output.</span></span></p>
<p><span data-ttu-id="ef270-123">套件轉換器會使用來原始目錄中所有 .osd 檔案的資訊來填入新套件。</span><span class="sxs-lookup"><span data-stu-id="ef270-123">The package converter would populate the new package with information from all of the .osd files in the source directory.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="ef270-124">轉換語句範例</span><span class="sxs-lookup"><span data-stu-id="ef270-124">Example conversion statement</span></span>

<span data-ttu-id="ef270-125">若要瞭解新程式，請參閱下列範例 `ConvertFrom-AppvLegacyPackage` 封裝轉換器語句。</span><span class="sxs-lookup"><span data-stu-id="ef270-125">To understand the new process, review the following example `ConvertFrom-AppvLegacyPackage` package converter statement.</span></span>

**<span data-ttu-id="ef270-126">如果來原始目錄（\\\\OldPkgStore\\ContosoApp）包含下列專案：</span><span class="sxs-lookup"><span data-stu-id="ef270-126">If the source directory (\\\\OldPkgStore\\ContosoApp) includes the following:</span></span>**

-   <span data-ttu-id="ef270-127">ContosoApp</span><span class="sxs-lookup"><span data-stu-id="ef270-127">ContosoApp.sft</span></span>

-   <span data-ttu-id="ef270-128">ContosoApp.msi</span><span class="sxs-lookup"><span data-stu-id="ef270-128">ContosoApp.msi</span></span>

-   <span data-ttu-id="ef270-129">ContosoApp.sprj</span><span class="sxs-lookup"><span data-stu-id="ef270-129">ContosoApp.sprj</span></span>

-   <span data-ttu-id="ef270-130">ContosoApp\_manifest.xml</span><span class="sxs-lookup"><span data-stu-id="ef270-130">ContosoApp\_manifest.xml</span></span>

-   <span data-ttu-id="ef270-131">X.x.x。x</span><span class="sxs-lookup"><span data-stu-id="ef270-131">X.osd</span></span>

-   <span data-ttu-id="ef270-132">.Osd</span><span class="sxs-lookup"><span data-stu-id="ef270-132">Y.osd</span></span>

-   <span data-ttu-id="ef270-133">Z. osd</span><span class="sxs-lookup"><span data-stu-id="ef270-133">Z.osd</span></span>

**<span data-ttu-id="ef270-134">然後執行此命令：</span><span class="sxs-lookup"><span data-stu-id="ef270-134">And you run this command:</span></span>**

``` syntax
ConvertFrom-AppvLegacyPackage –SourcePath \\OldPkgStore\ContosoApp\ 
-DestinationPath \\NewPkgStore\ContosoApp\
-OSDsToIncludeInPackage X.osd,Y.osd
```

**<span data-ttu-id="ef270-135">在目的地目錄（\\\\NewPkgStore\\ContosoApp）中會建立下列專案：</span><span class="sxs-lookup"><span data-stu-id="ef270-135">The following is created in the destination directory (\\\\NewPkgStore\\ContosoApp):</span></span>**

-   <span data-ttu-id="ef270-136">ContosoApp appv</span><span class="sxs-lookup"><span data-stu-id="ef270-136">ContosoApp.appv</span></span>

-   <span data-ttu-id="ef270-137">ContosoApp.msi</span><span class="sxs-lookup"><span data-stu-id="ef270-137">ContosoApp.msi</span></span>

-   <span data-ttu-id="ef270-138">ContosoApp\_DeploymentConfig.xml</span><span class="sxs-lookup"><span data-stu-id="ef270-138">ContosoApp\_DeploymentConfig.xml</span></span>

-   <span data-ttu-id="ef270-139">ContosoApp\_UserConfig.xml</span><span class="sxs-lookup"><span data-stu-id="ef270-139">ContosoApp\_UserConfig.xml</span></span>

-   <span data-ttu-id="ef270-140">X\_Config.xml</span><span class="sxs-lookup"><span data-stu-id="ef270-140">X\_Config.xml</span></span>

-   <span data-ttu-id="ef270-141">Y\_Config.xml</span><span class="sxs-lookup"><span data-stu-id="ef270-141">Y\_Config.xml</span></span>

-   <span data-ttu-id="ef270-142">Z\_Config.xml</span><span class="sxs-lookup"><span data-stu-id="ef270-142">Z\_Config.xml</span></span>

**<span data-ttu-id="ef270-143">在上述範例中：</span><span class="sxs-lookup"><span data-stu-id="ef270-143">In the above example:</span></span>**

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ef270-144">這些來原始目錄檔案 .。。</span><span class="sxs-lookup"><span data-stu-id="ef270-144">These Source directory files…</span></span></th>
<th align="left"><span data-ttu-id="ef270-145">...會轉換成這些目的地目錄檔案 .。。</span><span class="sxs-lookup"><span data-stu-id="ef270-145">…are converted to these Destination directory files…</span></span></th>
<th align="left"><span data-ttu-id="ef270-146">...並且將包含這些專案</span><span class="sxs-lookup"><span data-stu-id="ef270-146">…and will contain these items</span></span></th>
<th align="left"><span data-ttu-id="ef270-147">描述</span><span class="sxs-lookup"><span data-stu-id="ef270-147">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><ul>
<li><p><span data-ttu-id="ef270-148">X.x.x。x</span><span class="sxs-lookup"><span data-stu-id="ef270-148">X.osd</span></span></p></li>
<li><p><span data-ttu-id="ef270-149">.Osd</span><span class="sxs-lookup"><span data-stu-id="ef270-149">Y.osd</span></span></p></li>
<li><p><span data-ttu-id="ef270-150">Z. osd</span><span class="sxs-lookup"><span data-stu-id="ef270-150">Z.osd</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="ef270-151">X_Config.xml</span><span class="sxs-lookup"><span data-stu-id="ef270-151">X_Config.xml</span></span></p></li>
<li><p><span data-ttu-id="ef270-152">Y_Config.xml</span><span class="sxs-lookup"><span data-stu-id="ef270-152">Y_Config.xml</span></span></p></li>
<li><p><span data-ttu-id="ef270-153">Z_Config.xml</span><span class="sxs-lookup"><span data-stu-id="ef270-153">Z_Config.xml</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="ef270-154">環境變數</span><span class="sxs-lookup"><span data-stu-id="ef270-154">Environment variables</span></span></p></li>
<li><p><span data-ttu-id="ef270-155">方式</span><span class="sxs-lookup"><span data-stu-id="ef270-155">Shortcuts</span></span></p></li>
<li><p><span data-ttu-id="ef270-156">檔案類型關聯</span><span class="sxs-lookup"><span data-stu-id="ef270-156">File type associations</span></span></p></li>
<li><p><span data-ttu-id="ef270-157">註冊資訊</span><span class="sxs-lookup"><span data-stu-id="ef270-157">Registry information</span></span></p></li>
<li><p><span data-ttu-id="ef270-158">指令碼</span><span class="sxs-lookup"><span data-stu-id="ef270-158">Scripts</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="ef270-159">每個 .osd 檔案都會轉換成個別的對應 .xml 檔案，其中包含此處在 App-v 5.1 部署設定格式中所列的專案。</span><span class="sxs-lookup"><span data-stu-id="ef270-159">Each .osd file is converted to a separate, corresponding .xml file that contains the items listed here in App-V 5.1 deployment configuration format.</span></span> <span data-ttu-id="ef270-160">然後，您就可以從這些 .xml 檔案複製這些專案，並視需要將它們放在部署配置或使用者設定檔中。</span><span class="sxs-lookup"><span data-stu-id="ef270-160">These items can then be copied from these .xml files and placed in the deployment configuration or user configuration files as desired.</span></span></p>
<p><span data-ttu-id="ef270-161">在這個範例中，有三個 .xml 檔案，對應至來原始目錄中的三個 .osd 檔案。</span><span class="sxs-lookup"><span data-stu-id="ef270-161">In this example, there are three .xml files, corresponding with the three .osd files in the source directory.</span></span> <span data-ttu-id="ef270-162">每個 .xml 檔案都包含其對應的 .osd 檔案中的環境變數、快速鍵、檔案類型關聯、登錄資訊和腳本。</span><span class="sxs-lookup"><span data-stu-id="ef270-162">Each .xml file contains the environment variables, shortcuts, file type associations, registry information, and scripts in its corresponding .osd file.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><ul>
<li><p><span data-ttu-id="ef270-163">X.x.x。x</span><span class="sxs-lookup"><span data-stu-id="ef270-163">X.osd</span></span></p></li>
<li><p><span data-ttu-id="ef270-164">.Osd</span><span class="sxs-lookup"><span data-stu-id="ef270-164">Y.osd</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="ef270-165">ContosoApp appv</span><span class="sxs-lookup"><span data-stu-id="ef270-165">ContosoApp.appv</span></span></p></li>
<li><p><span data-ttu-id="ef270-166">ContosoApp_DeploymentConfig.xml</span><span class="sxs-lookup"><span data-stu-id="ef270-166">ContosoApp_DeploymentConfig.xml</span></span></p></li>
<li><p><span data-ttu-id="ef270-167">ContosoApp_UserConfig.xml</span><span class="sxs-lookup"><span data-stu-id="ef270-167">ContosoApp_UserConfig.xml</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="ef270-168">環境變數</span><span class="sxs-lookup"><span data-stu-id="ef270-168">Environment variables</span></span></p></li>
<li><p><span data-ttu-id="ef270-169">方式</span><span class="sxs-lookup"><span data-stu-id="ef270-169">Shortcuts</span></span></p></li>
<li><p><span data-ttu-id="ef270-170">檔案類型關聯</span><span class="sxs-lookup"><span data-stu-id="ef270-170">File type associations</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="ef270-171">在參數中指定的 .osd 檔案中的資訊 <code>-OSDsToIncludeInPackage</code> 會轉換並放在套件內。</span><span class="sxs-lookup"><span data-stu-id="ef270-171">The information from the .osd files specified in the <code>-OSDsToIncludeInPackage</code> parameter are converted and placed inside the package.</span></span> <span data-ttu-id="ef270-172">接著，轉換器會使用套件內容填入部署設定檔和使用者配置檔案，就像在排序新套件時，App-v 排序器所做的一樣。</span><span class="sxs-lookup"><span data-stu-id="ef270-172">The converter then populates the deployment configuration file and the user configuration file with the contents of the package, just as App-V Sequencer does when sequencing a new package.</span></span></p>
<p><span data-ttu-id="ef270-173">在這個範例中，在 X-blade 和 Y 中包含的環境變數、快捷方式和檔案類型關聯，都已轉換並放在應用程式 V 套件中，而其中一些資訊也包含在部署設定和使用者設定檔中。</span><span class="sxs-lookup"><span data-stu-id="ef270-173">In this example, environment variables, shortcuts, and file type associations included in X.osd and Y.osd were converted and placed in the App-V package, and some of this information was also included in the deployment configuration and user configuration files.</span></span> <span data-ttu-id="ef270-174">之所以使用 x.x 和 a.x，是因為它們是作為引數包含在參數中 <code>-OSDsToIncludeInPackage</code> 。</span><span class="sxs-lookup"><span data-stu-id="ef270-174">X.osd and Y.osd were used because they were included as arguments to the <code>-OSDsToIncludeInPackage</code> parameter.</span></span> <span data-ttu-id="ef270-175">不包含來自 Z 的任何資訊，因為它不是包含在其中一個引數中。</span><span class="sxs-lookup"><span data-stu-id="ef270-175">No information from Z.osd was included in the package, because it was not included as one of these arguments.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="ef270-176">轉換使用舊版 App-v （V）建立的套件</span><span class="sxs-lookup"><span data-stu-id="ef270-176">Converting packages created using a prior version of App-V</span></span>


<span data-ttu-id="ef270-177">使用套件轉換器實用程式來升級在 App-v 5.0 之前使用 app-v 版本建立的虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="ef270-177">Use the package converter utility to upgrade virtual application packages created using versions of App-V prior to App-V 5.0.</span></span> <span data-ttu-id="ef270-178">套件轉換器使用 PowerShell 來轉換套件，如果您有多個需要轉換的套件，就能協助自動處理常式。</span><span class="sxs-lookup"><span data-stu-id="ef270-178">The package converter uses PowerShell to convert packages and can help automate the process if you have many packages that require conversion.</span></span>

<span data-ttu-id="ef270-179">**重要** 在您轉換現有的套件之後，您應該先測試套件，然後再部署套件，以確保轉換程式已成功完成。</span><span class="sxs-lookup"><span data-stu-id="ef270-179">**Important** After you convert an existing package you should test the package prior to deploying the package to ensure the conversion process was successful.</span></span>

 

**<span data-ttu-id="ef270-180">轉換現有套件前的須知事項</span><span class="sxs-lookup"><span data-stu-id="ef270-180">What to know before you convert existing packages</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ef270-181">問題</span><span class="sxs-lookup"><span data-stu-id="ef270-181">Issue</span></span></th>
<th align="left"><span data-ttu-id="ef270-182">因應措施</span><span class="sxs-lookup"><span data-stu-id="ef270-182">Workaround</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ef270-183">在轉換之後，使用 DSC 的虛擬套件不會連結。</span><span class="sxs-lookup"><span data-stu-id="ef270-183">Virtual packages using DSC are not linked after conversion.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ef270-184">使用連線群組連結封裝。</span><span class="sxs-lookup"><span data-stu-id="ef270-184">Link the packages using connection groups.</span></span> <span data-ttu-id="ef270-185">請參閱 <a href="managing-connection-groups51.md" data-raw-source="[Managing Connection Groups](managing-connection-groups51.md)"> 管理連線群組 </a> 。</span><span class="sxs-lookup"><span data-stu-id="ef270-185">See <a href="managing-connection-groups51.md" data-raw-source="[Managing Connection Groups](managing-connection-groups51.md)">Managing Connection Groups</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ef270-186">在轉換期間偵測到環境變數衝突。</span><span class="sxs-lookup"><span data-stu-id="ef270-186">Environment variable conflicts are detected during conversion.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ef270-187">解決相關的 .osd 檔案中的任何衝突 <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="ef270-187">Resolve any conflicts in the associated <strong>.osd</strong> file.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ef270-188">在轉換期間檢測到硬編碼路徑。</span><span class="sxs-lookup"><span data-stu-id="ef270-188">Hard-coded paths are detected during conversion.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ef270-189">硬編碼路徑難以正確轉換。</span><span class="sxs-lookup"><span data-stu-id="ef270-189">Hard-coded paths are difficult to convert correctly.</span></span> <span data-ttu-id="ef270-190">套件轉換器會檢測並傳回內含硬編碼路徑之檔案的套件。</span><span class="sxs-lookup"><span data-stu-id="ef270-190">The package converter will detect and return packages with files that contain hard-coded paths.</span></span> <span data-ttu-id="ef270-191">使用硬編碼路徑來查看檔案，並判斷套件是否需要該檔案。</span><span class="sxs-lookup"><span data-stu-id="ef270-191">View the file with the hard-coded path, and determine whether the package requires the file.</span></span> <span data-ttu-id="ef270-192">如果是，建議您重新排列套件。</span><span class="sxs-lookup"><span data-stu-id="ef270-192">If so, it is recommended to re-sequence the package.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="ef270-193">轉換套件時，請檢查是否有失敗的檔案或快速鍵。</span><span class="sxs-lookup"><span data-stu-id="ef270-193">When converting a package check for failing files or shortcuts.</span></span> <span data-ttu-id="ef270-194">在 App-v 4.6 套件中找出該專案。</span><span class="sxs-lookup"><span data-stu-id="ef270-194">Locate the item in App-V 4.6 package.</span></span> <span data-ttu-id="ef270-195">它可能是硬式編碼路徑。</span><span class="sxs-lookup"><span data-stu-id="ef270-195">It could possibly be a hard-coded path.</span></span> <span data-ttu-id="ef270-196">轉換路徑。</span><span class="sxs-lookup"><span data-stu-id="ef270-196">Convert the path.</span></span>

<span data-ttu-id="ef270-197">**記事** 建議您使用 App-v 5.1 sequencer 來轉換需要利用功能的重要應用程式或應用程式。</span><span class="sxs-lookup"><span data-stu-id="ef270-197">**Note** It is recommended that you use the App-V 5.1 sequencer for converting critical applications or applications that need to take advantage of features.</span></span> <span data-ttu-id="ef270-198">請參閱[如何使用 app-v 5.1 來排序新的應用程式](how-to-sequence-a-new-application-with-app-v-51-beta-gb18030.md)。</span><span class="sxs-lookup"><span data-stu-id="ef270-198">See, [How to Sequence a New Application with App-V 5.1](how-to-sequence-a-new-application-with-app-v-51-beta-gb18030.md).</span></span>

<span data-ttu-id="ef270-199">如果轉換後的套件未在轉換後開啟，建議您使用 App-v 5.1 排序器重新排序應用程式。</span><span class="sxs-lookup"><span data-stu-id="ef270-199">If a converted package does not open after you convert it, it is also recommended that you re-sequence the application using the App-V 5.1 sequencer.</span></span>

 

[<span data-ttu-id="ef270-200">如何轉換在舊版 App-V 中建立的套件</span><span class="sxs-lookup"><span data-stu-id="ef270-200">How to Convert a Package Created in a Previous Version of App-V</span></span>](how-to-convert-a-package-created-in-a-previous-version-of-app-v51.md)

## <span data-ttu-id="ef270-201">遷移用戶端</span><span class="sxs-lookup"><span data-stu-id="ef270-201">Migrating Clients</span></span>


<span data-ttu-id="ef270-202">下表顯示升級用戶端的建議方法。</span><span class="sxs-lookup"><span data-stu-id="ef270-202">The following table displays the recommended method for upgrading clients.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ef270-203">工作</span><span class="sxs-lookup"><span data-stu-id="ef270-203">Task</span></span></th>
<th align="left"><span data-ttu-id="ef270-204">其他資訊</span><span class="sxs-lookup"><span data-stu-id="ef270-204">More Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ef270-205">將您的環境升級至最新版本的 App-V 4。6</span><span class="sxs-lookup"><span data-stu-id="ef270-205">Upgrade your environment to the latest version of App-V4.6</span></span></p></td>
<td align="left"><p><a href="../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md" data-raw-source="[Application Virtualization Deployment and Upgrade Considerations](../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md)"><span data-ttu-id="ef270-206">應用程式虛擬化部署和升級考慮 </a> 。</span><span class="sxs-lookup"><span data-stu-id="ef270-206">Application Virtualization Deployment and Upgrade Considerations</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ef270-207">安裝 App-V 5.1 用戶端（含共存功能）。</span><span class="sxs-lookup"><span data-stu-id="ef270-207">Install the App-V 5.1 client with co-existence enabled.</span></span></p></td>
<td align="left"><p><a href="how-to-deploy-the-app-v-46-and-the-app-v--51-client-on-the-same-computer.md" data-raw-source="[How to Deploy the App-V 4.6 and the App-V 5.1 Client on the Same Computer](how-to-deploy-the-app-v-46-and-the-app-v--51-client-on-the-same-computer.md)"><span data-ttu-id="ef270-208">如何在同一部電腦上部署 app-v 4.6 和 App-v 5.1 用戶端 </a> 。</span><span class="sxs-lookup"><span data-stu-id="ef270-208">How to Deploy the App-V 4.6 and the App-V 5.1 Client on the Same Computer</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ef270-209">順序及推出 app-v 5.1 套件。</span><span class="sxs-lookup"><span data-stu-id="ef270-209">Sequence and roll out App-V 5.1 packages.</span></span> <span data-ttu-id="ef270-210">視需要，取消發佈 App-v 4.6 套件。</span><span class="sxs-lookup"><span data-stu-id="ef270-210">As needed, unpublish App-V 4.6 packages.</span></span></p></td>
<td align="left"><p><a href="how-to-sequence-a-new-application-with-app-v-51-beta-gb18030.md" data-raw-source="[How to Sequence a New Application with App-V 5.1](how-to-sequence-a-new-application-with-app-v-51-beta-gb18030.md)"><span data-ttu-id="ef270-211">如何使用 App-v 5.1 來排序新的應用程式 </a> 。</span><span class="sxs-lookup"><span data-stu-id="ef270-211">How to Sequence a New Application with App-V 5.1</a>.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="ef270-212">**重要** 您必須執行最新版 App-V 4.6 才能使用共存模式。</span><span class="sxs-lookup"><span data-stu-id="ef270-212">**Important** You must be running the latest version of App-V4.6 to use coexistence mode.</span></span> <span data-ttu-id="ef270-213">此外，當您排列套件時，您必須設定 [管理機構] 設定（位於 **[使用者設定**] 中的 [**使用者**設定] 區段中）。</span><span class="sxs-lookup"><span data-stu-id="ef270-213">Additionally, when you sequence a package, you must configure the Managing Authority setting, which is in the **User Configuration** is located in the **User Configuration** section.</span></span>

 

## <span data-ttu-id="ef270-214">遷移 app-v 5.1 Server 的完整基礎結構</span><span class="sxs-lookup"><span data-stu-id="ef270-214">Migrating the App-V 5.1 Server Full Infrastructure</span></span>


<span data-ttu-id="ef270-215">沒有直接的方法可升級至完整的 App-v 5.1 基礎結構。</span><span class="sxs-lookup"><span data-stu-id="ef270-215">There is no direct method to upgrade to a full App-V 5.1 infrastructure.</span></span> <span data-ttu-id="ef270-216">請使用下一節中的資訊，以取得有關升級 App-v 伺服器的資訊。</span><span class="sxs-lookup"><span data-stu-id="ef270-216">Use the information in the following section for information about upgrading the App-V server.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="ef270-217">工作</span><span class="sxs-lookup"><span data-stu-id="ef270-217">Task</span></span></th>
<th align="left"><span data-ttu-id="ef270-218">其他資訊</span><span class="sxs-lookup"><span data-stu-id="ef270-218">More Information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ef270-219">將您的環境升級至最新版的 App-V 4.6。</span><span class="sxs-lookup"><span data-stu-id="ef270-219">Upgrade your environment to the latest version of App-V4.6.</span></span></p></td>
<td align="left"><p><a href="../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md" data-raw-source="[Application Virtualization Deployment and Upgrade Considerations](../appv-v4/application-virtualization-deployment-and-upgrade-considerations-copy.md)"><span data-ttu-id="ef270-220">應用程式虛擬化部署和升級考慮 </a> 。</span><span class="sxs-lookup"><span data-stu-id="ef270-220">Application Virtualization Deployment and Upgrade Considerations</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ef270-221">部署 app-v 5.1 版本的用戶端。</span><span class="sxs-lookup"><span data-stu-id="ef270-221">Deploy App-V 5.1 version of the client.</span></span></p></td>
<td align="left"><p><a href="how-to-deploy-the-app-v-client-51gb18030.md" data-raw-source="[How to Deploy the App-V Client](how-to-deploy-the-app-v-client-51gb18030.md)"><span data-ttu-id="ef270-222">如何部署 App-v 用戶端 </a> 。</span><span class="sxs-lookup"><span data-stu-id="ef270-222">How to Deploy the App-V Client</a>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ef270-223">安裝 App-V 5.1 server。</span><span class="sxs-lookup"><span data-stu-id="ef270-223">Install App-V 5.1 server.</span></span></p></td>
<td align="left"><p><a href="how-to-deploy-the-app-v-51-server.md" data-raw-source="[How to Deploy the App-V 5.1 Server](how-to-deploy-the-app-v-51-server.md)"><span data-ttu-id="ef270-224">如何部署 app-v 5.1 伺服器 </a> 。</span><span class="sxs-lookup"><span data-stu-id="ef270-224">How to Deploy the App-V 5.1 Server</a>.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ef270-225">[遷移現有的套件]。</span><span class="sxs-lookup"><span data-stu-id="ef270-225">Migrate existing packages.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ef270-226">請參閱本文中的 [ <strong> 使用先前版本的 app-v 建立的套件] </strong> 區段。</span><span class="sxs-lookup"><span data-stu-id="ef270-226">See the <strong>Converting packages created using a prior version of App-V</strong> section of this article.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="ef270-227">其他遷移任務</span><span class="sxs-lookup"><span data-stu-id="ef270-227">Additional Migration tasks</span></span>


<span data-ttu-id="ef270-228">您也可以執行額外的遷移工作，例如重新配置端點，以及開啟在執行 App-v 5.1 用戶端的電腦上使用先前版本建立的套件。</span><span class="sxs-lookup"><span data-stu-id="ef270-228">You can also perform additional migration tasks such as reconfiguring end points as well as opening a package created using a prior version on a computer running the App-V 5.1 client.</span></span> <span data-ttu-id="ef270-229">下列連結提供執行這些工作的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="ef270-229">The following links provide more information about performing these tasks.</span></span>

[<span data-ttu-id="ef270-230">如何為特定電腦上的所有使用者，將擴充點從 App-V 4.6 封裝移轉至轉換的 App-V 5.1 封裝</span><span class="sxs-lookup"><span data-stu-id="ef270-230">How to Migrate Extension Points From an App-V 4.6 Package to a Converted App-V 5.1 Package for All Users on a Specific Computer</span></span>](how-to-migrate-extension-points-from-an-app-v-46-package-to-a-converted-app-v-51-package-for-all-users-on-a-specific-computer.md)

[<span data-ttu-id="ef270-231">如何為特定使用者，將擴充點從 App-V 4.6 封裝移轉至 App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="ef270-231">How to Migrate Extension Points From an App-V 4.6 Package to App-V 5.1 for a Specific User</span></span>](how-to-migrate-extension-points-from-an-app-v-46-package-to-app-v-51-for-a-specific-user.md)

[<span data-ttu-id="ef270-232">如何為特定電腦上的所有使用者，將擴充點從 App-V 5.1 封裝移轉至 App-V 4.6 封裝</span><span class="sxs-lookup"><span data-stu-id="ef270-232">How to Revert Extension Points from an App-V 5.1 Package to an App-V 4.6 Package For All Users on a Specific Computer</span></span>](how-to-revert-extension-points-from-an-app-v-51-package-to-an-app-v-46-package-for-all-users-on-a-specific-computer.md)

[<span data-ttu-id="ef270-233">如何為特定使用者，將擴充點從 App-V 5.1 封裝移轉至 App-V 4.6 封裝</span><span class="sxs-lookup"><span data-stu-id="ef270-233">How to Revert Extension Points From an App-V 5.1 Package to an App-V 4.6 Package for a Specific User</span></span>](how-to-revert-extension-points-from-an-app-v-51-package-to-an-app-v-46-package-for-a-specific-user.md)







## <span data-ttu-id="ef270-234">執行 App-v 遷移任務的其他資源</span><span class="sxs-lookup"><span data-stu-id="ef270-234">Other resources for performing App-V migration tasks</span></span>


[<span data-ttu-id="ef270-235">App-V 5.1 作業</span><span class="sxs-lookup"><span data-stu-id="ef270-235">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

[<span data-ttu-id="ef270-236">簡化的 Microsoft App-v 5.1 管理伺服器升級程式</span><span class="sxs-lookup"><span data-stu-id="ef270-236">A simplified Microsoft App-V 5.1 Management Server upgrade procedure</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=786330)

 

 





