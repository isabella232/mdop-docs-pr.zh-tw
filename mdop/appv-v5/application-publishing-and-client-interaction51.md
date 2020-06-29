---
title: 應用程式發佈與用戶端互動
description: 應用程式發佈與用戶端互動
author: dansimp
ms.assetid: 36a4bf6f-a917-41a6-9856-6248686df352
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 69fcf119faaf35e53ae36f386bcb3480e2ee3b0e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800667"
---
# <span data-ttu-id="8b435-103">應用程式發佈與用戶端互動</span><span class="sxs-lookup"><span data-stu-id="8b435-103">Application Publishing and Client Interaction</span></span>


<span data-ttu-id="8b435-104">本文提供有關常見 App V 用戶端作業及其與本機作業系統整合的技術資訊。</span><span class="sxs-lookup"><span data-stu-id="8b435-104">This article provides technical information about common App-V client operations and their integration with the local operating system.</span></span>

-   [<span data-ttu-id="8b435-105">排序器所建立的 app-v 封裝檔案</span><span class="sxs-lookup"><span data-stu-id="8b435-105">App-V package files created by the Sequencer</span></span>](#bkmk-appv-pkg-files-list)

-   [<span data-ttu-id="8b435-106">Appv 檔案中有什麼？</span><span class="sxs-lookup"><span data-stu-id="8b435-106">What’s in the appv file?</span></span>](#bkmk-appv-file-contents)

-   [<span data-ttu-id="8b435-107">App-V 用戶端資料儲存位置</span><span class="sxs-lookup"><span data-stu-id="8b435-107">App-V client data storage locations</span></span>](#bkmk-files-data-storage)

-   [<span data-ttu-id="8b435-108">套件註冊</span><span class="sxs-lookup"><span data-stu-id="8b435-108">Package registry</span></span>](#bkmk-pkg-registry)

-   [<span data-ttu-id="8b435-109">App-v 套件儲存行為</span><span class="sxs-lookup"><span data-stu-id="8b435-109">App-V package store behavior</span></span>](#bkmk-pkg-store-behavior)

-   [<span data-ttu-id="8b435-110">漫遊登錄與資料</span><span class="sxs-lookup"><span data-stu-id="8b435-110">Roaming registry and data</span></span>](#bkmk-roaming-reg-data)

-   [<span data-ttu-id="8b435-111">App-V 用戶端應用程式週期管理</span><span class="sxs-lookup"><span data-stu-id="8b435-111">App-V client application lifecycle management</span></span>](#bkmk-clt-app-lifecycle)

-   [<span data-ttu-id="8b435-112">集成 App-v 套件</span><span class="sxs-lookup"><span data-stu-id="8b435-112">Integration of App-V packages</span></span>](#bkmk-integr-appv-pkgs)

-   [<span data-ttu-id="8b435-113">動態配置處理</span><span class="sxs-lookup"><span data-stu-id="8b435-113">Dynamic configuration processing</span></span>](#bkmk-dynamic-config)

-   [<span data-ttu-id="8b435-114">並列元件</span><span class="sxs-lookup"><span data-stu-id="8b435-114">Side-by-side assemblies</span></span>](#bkmk-sidebyside-assemblies)

-   [<span data-ttu-id="8b435-115">用戶端記錄</span><span class="sxs-lookup"><span data-stu-id="8b435-115">Client logging</span></span>](#bkmk-client-logging)

<span data-ttu-id="8b435-116">如需其他參考資訊，請參閱[Microsoft 應用程式虛擬化（app-v）檔資源下載頁面](https://www.microsoft.com/download/details.aspx?id=27760)。</span><span class="sxs-lookup"><span data-stu-id="8b435-116">For additional reference information, see [Microsoft Application Virtualization (App-V) Documentation Resources Download Page](https://www.microsoft.com/download/details.aspx?id=27760).</span></span>

## <a href="" id="bkmk-appv-pkg-files-list"></a><span data-ttu-id="8b435-117">排序器所建立的 app-v 封裝檔案</span><span class="sxs-lookup"><span data-stu-id="8b435-117">App-V package files created by the Sequencer</span></span>


<span data-ttu-id="8b435-118">排序器會建立 App-v 套件並產生虛擬化的應用程式。</span><span class="sxs-lookup"><span data-stu-id="8b435-118">The Sequencer creates App-V packages and produces a virtualized application.</span></span> <span data-ttu-id="8b435-119">排序過程會建立下列檔案：</span><span class="sxs-lookup"><span data-stu-id="8b435-119">The sequencing process creates the following files:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8b435-120">檔案</span><span class="sxs-lookup"><span data-stu-id="8b435-120">File</span></span></th>
<th align="left"><span data-ttu-id="8b435-121">說明</span><span class="sxs-lookup"><span data-stu-id="8b435-121">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b435-122">appv</span><span class="sxs-lookup"><span data-stu-id="8b435-122">.appv</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="8b435-123">主要套件檔案，其中包含從排序處理常式中捕獲的資產和狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="8b435-123">The primary package file, which contains the captured assets and state information from the sequencing process.</span></span></p></li>
<li><p><span data-ttu-id="8b435-124">封裝形式的套件檔案、發佈資訊和註冊表的架構，可以在傳送時，將它重新套用到電腦和特定使用者。</span><span class="sxs-lookup"><span data-stu-id="8b435-124">Architecture of the package file, publishing information, and registry in a tokenized form that can be reapplied to a machine and to a specific user upon delivery.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8b435-125">..MSI</span><span class="sxs-lookup"><span data-stu-id="8b435-125">.MSI</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-126">您可以用來手動部署 appv 檔案或使用協力廠商部署平臺的可執行部署包裝程式。</span><span class="sxs-lookup"><span data-stu-id="8b435-126">Executable deployment wrapper that you can use to deploy .appv files manually or by using a third-party deployment platform.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b435-127">_DeploymentConfig.XML</span><span class="sxs-lookup"><span data-stu-id="8b435-127">_DeploymentConfig.XML</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-128">此檔案可供您自訂套件中所有應用程式的預設發佈參數，這些元件會全域部署到執行 App-v 用戶端的電腦上的所有使用者。</span><span class="sxs-lookup"><span data-stu-id="8b435-128">File used to customize the default publishing parameters for all applications in a package that is deployed globally to all users on a computer that is running the App-V client.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8b435-129">_UserConfig.XML</span><span class="sxs-lookup"><span data-stu-id="8b435-129">_UserConfig.XML</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-130">此檔案用來針對在執行 App-v 用戶端之電腦上的特定使用者部署之套件中的所有應用程式，自訂發佈參數。</span><span class="sxs-lookup"><span data-stu-id="8b435-130">File used to customize the publishing parameters for all applications in a package that is a deployed to a specific user on a computer that is running the App-V client.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b435-131">Report.xml</span><span class="sxs-lookup"><span data-stu-id="8b435-131">Report.xml</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-132">排序進程所產生的訊息摘要，包括遺漏的驅動程式、檔案和註冊表位置。</span><span class="sxs-lookup"><span data-stu-id="8b435-132">Summary of messages resulting from the sequencing process, including omitted drivers, files, and registry locations.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8b435-133">.間</span><span class="sxs-lookup"><span data-stu-id="8b435-133">.CAB</span></span></p></td>
<td align="left"><p><em><span data-ttu-id="8b435-134">[選用]： </em> 套件加速器檔案，用來自動重建先前已排序的虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="8b435-134">Optional:</em> Package accelerator file used to automatically rebuild a previously sequenced virtual application package.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b435-135">.appvt</span><span class="sxs-lookup"><span data-stu-id="8b435-135">.appvt</span></span></p></td>
<td align="left"><p><em><span data-ttu-id="8b435-136">選用： </em> sequencer 範本檔案，用來保留常用的 Sequencer 設定。</span><span class="sxs-lookup"><span data-stu-id="8b435-136">Optional:</em> Sequencer template file used to retain commonly reused Sequencer settings.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="8b435-137">如需排序的相關資訊，請參閱[應用程式虛擬化順序指南](https://go.microsoft.com/fwlink/?LinkID=269810)。</span><span class="sxs-lookup"><span data-stu-id="8b435-137">For information about sequencing, see [Application Virtualization Sequencing Guide](https://go.microsoft.com/fwlink/?LinkID=269810).</span></span>

## <a href="" id="bkmk-appv-file-contents"></a><span data-ttu-id="8b435-138">Appv 檔案中有什麼？</span><span class="sxs-lookup"><span data-stu-id="8b435-138">What’s in the appv file?</span></span>


<span data-ttu-id="8b435-139">Appv 檔案是一個容器，可將 XML 和非 XML 檔案儲存在單一實體中。</span><span class="sxs-lookup"><span data-stu-id="8b435-139">The appv file is a container that stores XML and non-XML files together in a single entity.</span></span> <span data-ttu-id="8b435-140">此檔案是從 AppX 格式所建立，這是以開放式封裝慣例（OPC）標準為基礎。</span><span class="sxs-lookup"><span data-stu-id="8b435-140">This file is built from the AppX format, which is based on the Open Packaging Conventions (OPC) standard.</span></span>

<span data-ttu-id="8b435-141">若要查看 appv 檔案內容，請製作套件複本，然後將複製的檔案重新命名為 ZIP 延伸。</span><span class="sxs-lookup"><span data-stu-id="8b435-141">To view the appv file contents, make a copy of the package, and then rename the copied file to a ZIP extension.</span></span>

<span data-ttu-id="8b435-142">Appv 檔案包含下列資料夾及檔案，這些資料夾和檔案是在建立及發佈虛擬應用程式時使用：</span><span class="sxs-lookup"><span data-stu-id="8b435-142">The appv file contains the following folder and files, which are used when creating and publishing a virtual application:</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8b435-143">名稱</span><span class="sxs-lookup"><span data-stu-id="8b435-143">Name</span></span></th>
<th align="left"><span data-ttu-id="8b435-144">類型</span><span class="sxs-lookup"><span data-stu-id="8b435-144">Type</span></span></th>
<th align="left"><span data-ttu-id="8b435-145">描述</span><span class="sxs-lookup"><span data-stu-id="8b435-145">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b435-146">根目錄</span><span class="sxs-lookup"><span data-stu-id="8b435-146">Root</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-147">檔案資料夾</span><span class="sxs-lookup"><span data-stu-id="8b435-147">File folder</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-148">包含在排序期間捕獲之虛擬化應用程式之檔案系統的目錄。</span><span class="sxs-lookup"><span data-stu-id="8b435-148">Directory that contains the file system for the virtualized application that is captured during sequencing.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8b435-149">[Content_Types] .xml</span><span class="sxs-lookup"><span data-stu-id="8b435-149">[Content_Types].xml</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-150">XML 檔案</span><span class="sxs-lookup"><span data-stu-id="8b435-150">XML File</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-151">Appv 檔案（例如 DLL、EXE、BIN）中的核心內容類型清單。</span><span class="sxs-lookup"><span data-stu-id="8b435-151">List of the core content types in the appv file (e.g. DLL, EXE, BIN).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b435-152">AppxBlockMap.xml</span><span class="sxs-lookup"><span data-stu-id="8b435-152">AppxBlockMap.xml</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-153">XML 檔案</span><span class="sxs-lookup"><span data-stu-id="8b435-153">XML File</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-154">Appv 檔案的版面配置，該檔案使用檔案、區塊及 BlockMap 元素，可在 App-v 套件中啟用檔案位置及驗證。</span><span class="sxs-lookup"><span data-stu-id="8b435-154">Layout of the appv file, which uses File, Block, and BlockMap elements that enable location and validation of files in the App-V package.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8b435-155">AppxManifest.xml</span><span class="sxs-lookup"><span data-stu-id="8b435-155">AppxManifest.xml</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-156">XML 檔案</span><span class="sxs-lookup"><span data-stu-id="8b435-156">XML File</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-157">套件的中繼資料，其中包含新增、發佈及啟動套件所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="8b435-157">Metadata for the package that contains the required information for adding, publishing, and launching the package.</span></span> <span data-ttu-id="8b435-158">包括延伸點（檔案類型關聯和快速鍵），以及與套件關聯的名稱和 Guid。</span><span class="sxs-lookup"><span data-stu-id="8b435-158">Includes extension points (file type associations and shortcuts) and the names and GUIDs associated with the package.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b435-159">FilesystemMetadata.xml</span><span class="sxs-lookup"><span data-stu-id="8b435-159">FilesystemMetadata.xml</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-160">XML 檔案</span><span class="sxs-lookup"><span data-stu-id="8b435-160">XML File</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-161">在排序期間捕獲的檔案清單，包括屬性（例如目錄、檔案、不透明目錄、空目錄、長名稱和短名稱）。</span><span class="sxs-lookup"><span data-stu-id="8b435-161">List of the files captured during sequencing, including attributes (e.g., directories, files, opaque directories, empty directories,and long and short names).</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8b435-162">PackageHistory.xml</span><span class="sxs-lookup"><span data-stu-id="8b435-162">PackageHistory.xml</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-163">XML 檔案</span><span class="sxs-lookup"><span data-stu-id="8b435-163">XML File</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-164">有關先後順序電腦（作業系統版本、Internet Explorer 版本、.Net Framework 版本）與程式（升級、套件版本）的資訊。</span><span class="sxs-lookup"><span data-stu-id="8b435-164">Information about the sequencing computer (operating system version, Internet Explorer version, .Net Framework version) and process (upgrade, package version).</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b435-165">Registry （dat）</span><span class="sxs-lookup"><span data-stu-id="8b435-165">Registry.dat</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-166">DAT 檔案</span><span class="sxs-lookup"><span data-stu-id="8b435-166">DAT File</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-167">在封裝的排序程式期間捕獲的登錄機碼和值。</span><span class="sxs-lookup"><span data-stu-id="8b435-167">Registry keys and values captured during the sequencing process for the package.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8b435-168">StreamMap.xml</span><span class="sxs-lookup"><span data-stu-id="8b435-168">StreamMap.xml</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-169">XML 檔案</span><span class="sxs-lookup"><span data-stu-id="8b435-169">XML File</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-170">主要和發佈功能區塊的檔案清單。</span><span class="sxs-lookup"><span data-stu-id="8b435-170">List of files for the primary and publishing feature block.</span></span> <span data-ttu-id="8b435-171">發佈功能區塊包含用於發佈套件的 .ICO 檔案，以及檔案（EXE 和 DLL）的必要部分。</span><span class="sxs-lookup"><span data-stu-id="8b435-171">The publishing feature block contains the ICO files and required portions of files (EXE and DLL) for publishing the package.</span></span> <span data-ttu-id="8b435-172">當簡報時，主要的功能區塊會包含已針對排序程式在進行中進行流式處理的檔案。</span><span class="sxs-lookup"><span data-stu-id="8b435-172">When present, the primary feature block includes files that have been optimized for streaming during the sequencing process.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-files-data-storage"></a><span data-ttu-id="8b435-173">App-V 用戶端資料儲存位置</span><span class="sxs-lookup"><span data-stu-id="8b435-173">App-V client data storage locations</span></span>


<span data-ttu-id="8b435-174">App-v 用戶端會執行工作，以確保虛擬應用程式正常運作且能正常運作（例如本機安裝的應用程式）。</span><span class="sxs-lookup"><span data-stu-id="8b435-174">The App-V client performs tasks to ensure that virtual applications run properly and work like locally installed applications.</span></span> <span data-ttu-id="8b435-175">開啟及執行虛擬應用程式的程式需要從虛擬檔案系統和註冊表進行對應，以確保應用程式具有使用者預期的傳統應用程式所需的元件。</span><span class="sxs-lookup"><span data-stu-id="8b435-175">The process of opening and running virtual applications requires mapping from the virtual file system and registry to ensure the application has the required components of a traditional application expected by users.</span></span> <span data-ttu-id="8b435-176">本節將說明執行虛擬應用程式所需的資產，並列出 App V 儲存資產的位置。</span><span class="sxs-lookup"><span data-stu-id="8b435-176">This section describes the assets that are required to run virtual applications and lists the location where App-V stores the assets.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8b435-177">名稱</span><span class="sxs-lookup"><span data-stu-id="8b435-177">Name</span></span></th>
<th align="left"><span data-ttu-id="8b435-178">位置</span><span class="sxs-lookup"><span data-stu-id="8b435-178">Location</span></span></th>
<th align="left"><span data-ttu-id="8b435-179">說明</span><span class="sxs-lookup"><span data-stu-id="8b435-179">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b435-180">套件存放區</span><span class="sxs-lookup"><span data-stu-id="8b435-180">Package Store</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-181">%ProgramData%\App-V</span><span class="sxs-lookup"><span data-stu-id="8b435-181">%ProgramData%\App-V</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-182">唯讀套件檔案的預設位置</span><span class="sxs-lookup"><span data-stu-id="8b435-182">Default location for read only package files</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8b435-183">電腦目錄</span><span class="sxs-lookup"><span data-stu-id="8b435-183">Machine Catalog</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-184">%ProgramData%\Microsoft\AppV\Client\Catalog</span><span class="sxs-lookup"><span data-stu-id="8b435-184">%ProgramData%\Microsoft\AppV\Client\Catalog</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-185">包含每電腦設定檔</span><span class="sxs-lookup"><span data-stu-id="8b435-185">Contains per-machine configuration documents</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b435-186">使用者目錄</span><span class="sxs-lookup"><span data-stu-id="8b435-186">User Catalog</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-187">%AppData%\Microsoft\AppV\Client\Catalog</span><span class="sxs-lookup"><span data-stu-id="8b435-187">%AppData%\Microsoft\AppV\Client\Catalog</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-188">包含每個使用者的設定檔</span><span class="sxs-lookup"><span data-stu-id="8b435-188">Contains per-user configuration documents</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8b435-189">快捷方式備份</span><span class="sxs-lookup"><span data-stu-id="8b435-189">Shortcut Backups</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-190">%AppData%\Microsoft\AppV\Client\Integration\ShortCutBackups</span><span class="sxs-lookup"><span data-stu-id="8b435-190">%AppData%\Microsoft\AppV\Client\Integration\ShortCutBackups</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-191">儲存先前的整合點，以便在套件取消發佈時啟用還原</span><span class="sxs-lookup"><span data-stu-id="8b435-191">Stores previous integration points that enable restore on package unpublish</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b435-192">寫入時複製（牛）漫遊</span><span class="sxs-lookup"><span data-stu-id="8b435-192">Copy on Write (COW) Roaming</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-193">%AppData%\Microsoft\AppV\Client\VFS</span><span class="sxs-lookup"><span data-stu-id="8b435-193">%AppData%\Microsoft\AppV\Client\VFS</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-194">套件修改的可寫入漫遊位置</span><span class="sxs-lookup"><span data-stu-id="8b435-194">Writeable roaming location for package modification</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8b435-195">寫入時複製（牛）本機</span><span class="sxs-lookup"><span data-stu-id="8b435-195">Copy on Write (COW) Local</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-196">%LocalAppData%\Microsoft\AppV\Client\VFS</span><span class="sxs-lookup"><span data-stu-id="8b435-196">%LocalAppData%\Microsoft\AppV\Client\VFS</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-197">適用于套件修改的可寫入非漫遊位置</span><span class="sxs-lookup"><span data-stu-id="8b435-197">Writeable non-roaming location for package modification</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b435-198">電腦註冊表</span><span class="sxs-lookup"><span data-stu-id="8b435-198">Machine Registry</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-199">HKLM\Software\Microsoft\AppV</span><span class="sxs-lookup"><span data-stu-id="8b435-199">HKLM\Software\Microsoft\AppV</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-200">包含套件狀態資訊，包括電腦或全域發佈套件（電腦配置單元）的 VReg</span><span class="sxs-lookup"><span data-stu-id="8b435-200">Contains package state information, including VReg for machine or globally published packages (Machine hive)</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8b435-201">使用者註冊表</span><span class="sxs-lookup"><span data-stu-id="8b435-201">User Registry</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-202">HKCU\Software\Microsoft\AppV</span><span class="sxs-lookup"><span data-stu-id="8b435-202">HKCU\Software\Microsoft\AppV</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-203">包含使用者套件狀態資訊，包括 VReg</span><span class="sxs-lookup"><span data-stu-id="8b435-203">Contains user package state information including VReg</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b435-204">使用者註冊類別</span><span class="sxs-lookup"><span data-stu-id="8b435-204">User Registry Classes</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-205">HKCU\Software\Classes\AppV</span><span class="sxs-lookup"><span data-stu-id="8b435-205">HKCU\Software\Classes\AppV</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-206">包含其他使用者套件狀態資訊</span><span class="sxs-lookup"><span data-stu-id="8b435-206">Contains additional user package state information</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="8b435-207">表格的其他詳細資料會在下一節和整份檔中提供。</span><span class="sxs-lookup"><span data-stu-id="8b435-207">Additional details for the table are provided in the section below and throughout the document.</span></span>

### <span data-ttu-id="8b435-208">套件存放區</span><span class="sxs-lookup"><span data-stu-id="8b435-208">Package store</span></span>

<span data-ttu-id="8b435-209">App-V 用戶端會管理套件存放區中裝載的應用程式資產。</span><span class="sxs-lookup"><span data-stu-id="8b435-209">The App-V Client manages the applications assets mounted in the package store.</span></span> <span data-ttu-id="8b435-210">這個預設儲存位置是 `%ProgramData%\App-V` ，但您可以使用 PowerShell 命令在安裝期間或之後進行設定 `Set-AppVClientConfiguration` ，這會修改本機登錄（ `PackageInstallationRoot` 在金鑰底下的值 `HKLM\Software\Microsoft\AppV\Client\Streaming` ）。</span><span class="sxs-lookup"><span data-stu-id="8b435-210">This default storage location is `%ProgramData%\App-V`, but you can configure it during or after setup by using the `Set-AppVClientConfiguration` PowerShell command, which modifies the local registry (`PackageInstallationRoot` value under the `HKLM\Software\Microsoft\AppV\Client\Streaming` key).</span></span> <span data-ttu-id="8b435-211">套件存放區必須位於用戶端作業系統上的本機路徑中。</span><span class="sxs-lookup"><span data-stu-id="8b435-211">The package store must be located at a local path on the client operating system.</span></span> <span data-ttu-id="8b435-212">個別套件會儲存在套件 GUID 與版本 GUID 命名的子目錄中。</span><span class="sxs-lookup"><span data-stu-id="8b435-212">The individual packages are stored in the package store in subdirectories named for the Package GUID and Version GUID.</span></span>

<span data-ttu-id="8b435-213">特定應用程式路徑範例：</span><span class="sxs-lookup"><span data-stu-id="8b435-213">Example of a path to a specific application:</span></span>

``` syntax
C:\ProgramData\App-V\PackGUID\VersionGUID
```

<span data-ttu-id="8b435-214">若要在安裝期間變更套件存放區的預設位置，請參閱[如何部署 App-v 用戶端](how-to-deploy-the-app-v-client-51gb18030.md)。</span><span class="sxs-lookup"><span data-stu-id="8b435-214">To change the default location of the package store during setup, see [How to Deploy the App-V Client](how-to-deploy-the-app-v-client-51gb18030.md).</span></span>

### <span data-ttu-id="8b435-215">共用內容存放區</span><span class="sxs-lookup"><span data-stu-id="8b435-215">Shared Content Store</span></span>

<span data-ttu-id="8b435-216">如果 App-v 用戶端是在 [共用內容存放區] 模式中設定，則當出現資料流程錯誤時，就不會將資料寫入磁片，這表示套件需要最少的本機磁碟空間（發佈資料）。</span><span class="sxs-lookup"><span data-stu-id="8b435-216">If the App-V Client is configured in Shared Content Store mode, no data is written to disk when a stream fault occurs, which means that the packages require minimal local disk space (publishing data).</span></span> <span data-ttu-id="8b435-217">在 VDI 環境中使用較少的磁碟空間非常可取，在這種情況下，可以限制本機儲存空間，並以高效能網路位置（例如 SAN）來流式處理應用程式。</span><span class="sxs-lookup"><span data-stu-id="8b435-217">The use of less disk space is highly desirable in VDI environments, where local storage can be limited, and streaming the applications from a high performance network location (such as a SAN) is preferable.</span></span> <span data-ttu-id="8b435-218">如需共用內容存放區模式的詳細資訊，請參閱 <https://go.microsoft.com/fwlink/p/?LinkId=392750> 。</span><span class="sxs-lookup"><span data-stu-id="8b435-218">For more information on shared content store mode, see <https://go.microsoft.com/fwlink/p/?LinkId=392750>.</span></span>

<span data-ttu-id="8b435-219">**記事** 即使您使用的是 App-v 用戶端的共用內容存放區設定，電腦和套件存放區也必須位於本機磁片磁碟機上。</span><span class="sxs-lookup"><span data-stu-id="8b435-219">**Note** The machine and package store must be located on a local drive, even when you’re using Shared Content Store configurations for the App-V Client.</span></span>

 

### <span data-ttu-id="8b435-220">套件目錄</span><span class="sxs-lookup"><span data-stu-id="8b435-220">Package catalogs</span></span>

<span data-ttu-id="8b435-221">App-v 用戶端會管理下列兩個以檔案為基礎的位置：</span><span class="sxs-lookup"><span data-stu-id="8b435-221">The App-V Client manages the following two file-based locations:</span></span>

-   **<span data-ttu-id="8b435-222">[編目] （使用者與電腦）。</span><span class="sxs-lookup"><span data-stu-id="8b435-222">Catalogs (user and machine).</span></span>**

-   <span data-ttu-id="8b435-223">登錄**位置**-視套件的目標發佈方式而定。</span><span class="sxs-lookup"><span data-stu-id="8b435-223">**Registry locations** - depends on how the package is targeted for publishing.</span></span> <span data-ttu-id="8b435-224">該電腦有一個 [目錄（資料儲存區）]，以及每個個別使用者的目錄。</span><span class="sxs-lookup"><span data-stu-id="8b435-224">There is a Catalog (data store) for the computer, and a catalog for each individual user.</span></span> <span data-ttu-id="8b435-225">電腦目錄會儲存適用于所有使用者或任何使用者的全域資訊，而使用者目錄會儲存適用于特定使用者的資訊。</span><span class="sxs-lookup"><span data-stu-id="8b435-225">The Machine Catalog stores global information applicable to all users or any user, and the User Catalog stores information applicable to a specific user.</span></span> <span data-ttu-id="8b435-226">目錄是動態配置和資訊清單檔案的集合;每個套件版本的檔案和註冊表都有離散資料。</span><span class="sxs-lookup"><span data-stu-id="8b435-226">The Catalog is a collection of Dynamic Configurations and manifest files; there is discrete data for both file and registry per package version.</span></span> 

### <span data-ttu-id="8b435-227">電腦目錄</span><span class="sxs-lookup"><span data-stu-id="8b435-227">Machine catalog</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b435-228">說明</span><span class="sxs-lookup"><span data-stu-id="8b435-228">Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-229">在新增及發佈套件時，儲存可供電腦使用者使用的套件檔。</span><span class="sxs-lookup"><span data-stu-id="8b435-229">Stores package documents that are available to users on the machine, when packages are added and published.</span></span> <span data-ttu-id="8b435-230">不過，如果在發佈時套件是「全域」，則所有使用者都能使用這些整合。</span><span class="sxs-lookup"><span data-stu-id="8b435-230">However, if a package is “global” at publishing time, the integrations are available to all users.</span></span></p>
<p><span data-ttu-id="8b435-231">如果套件是非全域的，則只會針對特定使用者發佈整合，但用戶端電腦上的任何人都已修改且可見的全域資源（例如，套件目錄位於共用磁片位置）。</span><span class="sxs-lookup"><span data-stu-id="8b435-231">If a package is non-global, the integrations are published only for specific users, but there are still global resources that are modified and visible to anyone on the client computer (e.g., the package directory is in a shared disk location).</span></span></p>
<p><span data-ttu-id="8b435-232">如果電腦上的使用者可以使用套件（全域或非全域），資訊清單就會儲存在電腦目錄中。</span><span class="sxs-lookup"><span data-stu-id="8b435-232">If a package is available to a user on the computer (global or non-global), the manifest is stored in the Machine Catalog.</span></span> <span data-ttu-id="8b435-233">當套件是全域發佈時，就會有一個動態設定檔案，儲存在電腦目錄中;因此，根據電腦目錄中是否有原則檔案（UserDeploymentConfiguration 檔案），決定是否為全域套件。</span><span class="sxs-lookup"><span data-stu-id="8b435-233">When a package is published globally, there is a Dynamic Configuration file, stored in the Machine Catalog; therefore, the determination of whether a package is global is defined according to whether there is a policy file (UserDeploymentConfiguration file) in the Machine Catalog.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8b435-234">預設儲存位置</span><span class="sxs-lookup"><span data-stu-id="8b435-234">Default storage location</span></span></p></td>
<td align="left"><p><code>%programdata%\Microsoft\AppV\Client\Catalog&lt;/code&gt;</p>
<p><span data-ttu-id="8b435-235">這個位置與套件儲存位置不同。</span><span class="sxs-lookup"><span data-stu-id="8b435-235">This location is not the same as the Package Store location.</span></span> <span data-ttu-id="8b435-236">套件存放區是套件檔案的黃金或 pristine 複本。</span><span class="sxs-lookup"><span data-stu-id="8b435-236">The Package Store is the golden or pristine copy of the package files.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b435-237">電腦目錄中的檔案</span><span class="sxs-lookup"><span data-stu-id="8b435-237">Files in the machine catalog</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="8b435-238">Manifest.xml</span><span class="sxs-lookup"><span data-stu-id="8b435-238">Manifest.xml</span></span></p></li>
<li><p><span data-ttu-id="8b435-239">DeploymentConfiguration.xml</span><span class="sxs-lookup"><span data-stu-id="8b435-239">DeploymentConfiguration.xml</span></span></p></li>
<li><p><span data-ttu-id="8b435-240">UserManifest.xml （全域發佈的套件）</span><span class="sxs-lookup"><span data-stu-id="8b435-240">UserManifest.xml (Globally Published Package)</span></span></p></li>
<li><p><span data-ttu-id="8b435-241">UserDeploymentConfiguration.xml （全域發佈的套件）</span><span class="sxs-lookup"><span data-stu-id="8b435-241">UserDeploymentConfiguration.xml (Globally Published Package)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8b435-242">其他電腦目錄位置，在套件是連線群組的一部分時使用</span><span class="sxs-lookup"><span data-stu-id="8b435-242">Additional machine catalog location, used when the package is part of a connection group</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-243">下列位置除了上述所述的特定套件位置之外：</span><span class="sxs-lookup"><span data-stu-id="8b435-243">The following location is in addition to the specific package location mentioned above:</span></span></p>
<p><code>%programdata%\Microsoft\AppV\Client\Catalog\PackageGroups\ConGroupGUID\ConGroupVerGUID</code></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b435-244">當套件是連線群組的一部分時，電腦目錄中的其他檔案</span><span class="sxs-lookup"><span data-stu-id="8b435-244">Additional files in the machine catalog when the package is part of a connection group</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="8b435-245">PackageGroupDescriptor.xml</span><span class="sxs-lookup"><span data-stu-id="8b435-245">PackageGroupDescriptor.xml</span></span></p></li>
<li><p><span data-ttu-id="8b435-246">UserPackageGroupDescriptor.xml （全域發佈的連線群組）</span><span class="sxs-lookup"><span data-stu-id="8b435-246">UserPackageGroupDescriptor.xml (globally published Connection Group)</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="8b435-247">使用者目錄</span><span class="sxs-lookup"><span data-stu-id="8b435-247">User catalog</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b435-248">說明</span><span class="sxs-lookup"><span data-stu-id="8b435-248">Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-249">在發佈程式期間建立。</span><span class="sxs-lookup"><span data-stu-id="8b435-249">Created during the publishing process.</span></span> <span data-ttu-id="8b435-250">包含發佈套件所用的資訊，也可在啟動時使用，以確保將套件提供給特定的使用者。</span><span class="sxs-lookup"><span data-stu-id="8b435-250">Contains information used for publishing the package, and also used at launch to ensure that a package is provisioned to a specific user.</span></span> <span data-ttu-id="8b435-251">在漫遊位置建立，並包含使用者專用的發佈資訊。</span><span class="sxs-lookup"><span data-stu-id="8b435-251">Created in a roaming location and includes user-specific publishing information.</span></span></p>
<p><span data-ttu-id="8b435-252">當您為使用者發佈套件時，原則檔案會儲存在使用者目錄中。</span><span class="sxs-lookup"><span data-stu-id="8b435-252">When a package is published for a user, the policy file is stored in the User Catalog.</span></span> <span data-ttu-id="8b435-253">同時，也會將資訊清單複本儲存在使用者目錄中。</span><span class="sxs-lookup"><span data-stu-id="8b435-253">At the same time, a copy of the manifest is also stored in the User Catalog.</span></span> <span data-ttu-id="8b435-254">當使用者移除套件權利時，相關的套件檔案就會從使用者目錄中移除。</span><span class="sxs-lookup"><span data-stu-id="8b435-254">When a package entitlement is removed for a user, the relevant package files are removed from the User Catalog.</span></span> <span data-ttu-id="8b435-255">在查看使用者目錄時，系統管理員可以查看動態設定檔案是否存在，這表示該套件適用于該使用者。</span><span class="sxs-lookup"><span data-stu-id="8b435-255">Looking at the user catalog, an administrator can view the presence of a Dynamic Configuration file, which indicates that the package is entitled for that user.</span></span></p>
<p><span data-ttu-id="8b435-256">針對漫遊使用者，使用者目錄必須位於漫遊或共用位置，才能預設保留目標使用者的舊版 App-v 行為。</span><span class="sxs-lookup"><span data-stu-id="8b435-256">For roaming users, the User Catalog needs to be in a roaming or shared location to preserve the legacy App-V behavior of targeting users by default.</span></span> <span data-ttu-id="8b435-257">權利與原則會與使用者（而非電腦）相關聯，所以在使用者提供之後，就應該與使用者一起漫遊。</span><span class="sxs-lookup"><span data-stu-id="8b435-257">Entitlement and policy are tied to a user, not a computer, so they should roam with the user once they are provisioned.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8b435-258">預設儲存位置</span><span class="sxs-lookup"><span data-stu-id="8b435-258">Default storage location</span></span></p></td>
<td align="left"><p><code>appdata\roaming\Microsoft\AppV\Client\Catalog\Packages\PkgGUID\VerGUID</code></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b435-259">使用者目錄中的檔案</span><span class="sxs-lookup"><span data-stu-id="8b435-259">Files in the user catalog</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="8b435-260">UserManifest.xml</span><span class="sxs-lookup"><span data-stu-id="8b435-260">UserManifest.xml</span></span></p></li>
<li><p><span data-ttu-id="8b435-261">DynamicConfiguration.xml 或 UserDeploymentConfiguration.xml</span><span class="sxs-lookup"><span data-stu-id="8b435-261">DynamicConfiguration.xml or UserDeploymentConfiguration.xml</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8b435-262">其他使用者目錄位置，在套件是連線群組的一部分時使用</span><span class="sxs-lookup"><span data-stu-id="8b435-262">Additional user catalog location, used when the package is part of a connection group</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-263">下列位置除了上述所述的特定套件位置之外：</span><span class="sxs-lookup"><span data-stu-id="8b435-263">The following location is in addition to the specific package location mentioned above:</span></span></p>
<p><code>appdata\roaming\Microsoft\AppV\Client\Catalog\PackageGroups\PkgGroupGUID\PkgGroupVerGUID</code></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b435-264">當套件是連線群組的一部分時，電腦目錄中的其他檔案</span><span class="sxs-lookup"><span data-stu-id="8b435-264">Additional file in the machine catalog when the package is part of a connection group</span></span></p></td>
<td align="left"><p><code>UserPackageGroupDescriptor.xml</code></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="8b435-265">快捷方式備份</span><span class="sxs-lookup"><span data-stu-id="8b435-265">Shortcut backups</span></span>

<span data-ttu-id="8b435-266">在發佈程式期間，App-V 用戶端會備份任何快速鍵及整合點至 `%AppData%\Microsoft\AppV\Client\Integration\ShortCutBackups.` 此備份，在未發佈套件時，可將這些整合點還原到先前的版本。</span><span class="sxs-lookup"><span data-stu-id="8b435-266">During the publishing process, the App-V Client backs up any shortcuts and integration points to `%AppData%\Microsoft\AppV\Client\Integration\ShortCutBackups.` This backup enables the restoration of these integration points to the previous versions when the package is unpublished.</span></span>

### <span data-ttu-id="8b435-267">在寫入檔案時複製</span><span class="sxs-lookup"><span data-stu-id="8b435-267">Copy on Write files</span></span>

<span data-ttu-id="8b435-268">套件存放區包含已從發佈伺服器傳送資料流程的套件檔案 pristine 複本。</span><span class="sxs-lookup"><span data-stu-id="8b435-268">The Package Store contains a pristine copy of the package files that have been streamed from the publishing server.</span></span> <span data-ttu-id="8b435-269">在 App-V 應用程式的正常運作期間，使用者或服務可能需要變更檔案。</span><span class="sxs-lookup"><span data-stu-id="8b435-269">During normal operation of an App-V application, the user or service may require changes to the files.</span></span> <span data-ttu-id="8b435-270">在套件存放區中不會進行這些變更，以保留您修復應用程式的能力，這會移除這些變更。</span><span class="sxs-lookup"><span data-stu-id="8b435-270">These changes are not made in the package store in order to preserve your ability to repair the application, which removes these changes.</span></span> <span data-ttu-id="8b435-271">這些位置稱為 [寫入時複製（牛）]，支援漫遊和非漫遊位置。</span><span class="sxs-lookup"><span data-stu-id="8b435-271">These locations, called Copy on Write (COW), support both roaming and non-roaming locations.</span></span> <span data-ttu-id="8b435-272">儲存修改的位置，取決於應用程式在原生體驗中編寫變更的程式。</span><span class="sxs-lookup"><span data-stu-id="8b435-272">The location where the modifications are stored depends where the application has been programmed to write changes to in a native experience.</span></span>

### <span data-ttu-id="8b435-273">牛漫遊</span><span class="sxs-lookup"><span data-stu-id="8b435-273">COW roaming</span></span>

<span data-ttu-id="8b435-274">上面所述的 [牛漫遊位置] 會儲存針對典型% AppData% location 或 \\Users\\{username}\\AppData\\Roaming 位置的檔案和目錄所做的變更。</span><span class="sxs-lookup"><span data-stu-id="8b435-274">The COW Roaming location described above stores changes to files and directories that are targeted to the typical %AppData% location or \\Users\\{username}\\AppData\\Roaming location.</span></span> <span data-ttu-id="8b435-275">然後，這些目錄和檔案會根據作業系統設定進行漫遊。</span><span class="sxs-lookup"><span data-stu-id="8b435-275">These directories and files are then roamed based on the operating system settings.</span></span>

### <span data-ttu-id="8b435-276">牛 [本機]</span><span class="sxs-lookup"><span data-stu-id="8b435-276">COW local</span></span>

<span data-ttu-id="8b435-277">[牛本機位置] 與漫遊位置類似，但目錄和檔案不會漫遊至其他電腦，即使已設定漫遊支援也一樣。</span><span class="sxs-lookup"><span data-stu-id="8b435-277">The COW Local location is similar to the roaming location, but the directories and files are not roamed to other computers, even if roaming support has been configured.</span></span> <span data-ttu-id="8b435-278">上述的 [牛本機位置] 會儲存適用于一般視窗而不是% AppData% 位置的變更。</span><span class="sxs-lookup"><span data-stu-id="8b435-278">The COW Local location described above stores changes applicable to typical windows and not the %AppData% location.</span></span> <span data-ttu-id="8b435-279">列出的目錄會有差異，但在任何典型的 Windows 位置（例如一般 AppData 及常見的 AppDataS），都會有兩個位置。</span><span class="sxs-lookup"><span data-stu-id="8b435-279">The directories listed will vary but there will be two locations for any typical Windows locations (e.g. Common AppData and Common AppDataS).</span></span> <span data-ttu-id="8b435-280">**S**代表受限制的位置，在虛擬服務要求使用者從已登入的使用者進行變更時，會以不同的許可權傳送給使用者。</span><span class="sxs-lookup"><span data-stu-id="8b435-280">The **S** signifies the restricted location when the virtual service requests the change as a different elevated user from the logged on users.</span></span> <span data-ttu-id="8b435-281">非**S**位置會儲存以使用者為基礎的變更。</span><span class="sxs-lookup"><span data-stu-id="8b435-281">The non-**S** location stores user based changes.</span></span>

## <a href="" id="bkmk-pkg-registry"></a><span data-ttu-id="8b435-282">套件註冊</span><span class="sxs-lookup"><span data-stu-id="8b435-282">Package registry</span></span>


<span data-ttu-id="8b435-283">應用程式必須先將套件註冊資料提供給應用程式，才能讓應用程式存取套件註冊資料。</span><span class="sxs-lookup"><span data-stu-id="8b435-283">Before an application can access the package registry data, the App-V Client must make the package registry data available to the applications.</span></span> <span data-ttu-id="8b435-284">App-v 用戶端會針對所有登錄資料使用真實的登錄作為後備存放區。</span><span class="sxs-lookup"><span data-stu-id="8b435-284">The App-V Client uses the real registry as a backing store for all registry data.</span></span>

<span data-ttu-id="8b435-285">將新的套件新增到 App-v 用戶端時，就是一份複本。已建立來自套件的 DAT 檔案 `%ProgramData%\Microsoft\AppV\Client\VREG\{Version GUID}.dat` 。</span><span class="sxs-lookup"><span data-stu-id="8b435-285">When a new package is added to the App-V Client, a copy of the REGISTRY.DAT file from the package is created at `%ProgramData%\Microsoft\AppV\Client\VREG\{Version GUID}.dat`.</span></span> <span data-ttu-id="8b435-286">檔案的名稱是版本 GUID，且副檔名為。DAT 延伸。</span><span class="sxs-lookup"><span data-stu-id="8b435-286">The name of the file is the version GUID with the .DAT extension.</span></span> <span data-ttu-id="8b435-287">這份製作的原因是要確保套件中的實際設定檔檔案永遠不會被使用，從而避免日後移除套件。</span><span class="sxs-lookup"><span data-stu-id="8b435-287">The reason this copy is made is to ensure that the actual hive file in the package is never in use, which would prevent the removal of the package at a later time.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="8b435-288">[套件存放區] 的 [Registry] （dat）</span><span class="sxs-lookup"><span data-stu-id="8b435-288">Registry.dat from Package Store</span></span></strong></p></td>
<td align="left"><p><strong> &gt; </strong></p></td>
<td align="left"><p><strong><span data-ttu-id="8b435-289">%ProgramData%\Microsoft\AppV\Client\Vreg {VersionGuid} .dat</span><span class="sxs-lookup"><span data-stu-id="8b435-289">%ProgramData%\Microsoft\AppV\Client\Vreg{VersionGuid}.dat</span></span></strong></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="8b435-290">當在用戶端上啟動套件中的第一個應用程式時，用戶端階段或將內容複寫到 hive 檔案中，在備用位置重新建立套件註冊資料 `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\AppV\Client\Packages\PackageGuid\Versions\VersionGuid\REGISTRY` 。</span><span class="sxs-lookup"><span data-stu-id="8b435-290">When the first application from the package is launched on the client, the client stages or copies the contents out of the hive file, re-creating the package registry data in an alternate location `HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\AppV\Client\Packages\PackageGuid\Versions\VersionGuid\REGISTRY`.</span></span> <span data-ttu-id="8b435-291">分段登錄資料有兩種不同類型的電腦資料和使用者資料。</span><span class="sxs-lookup"><span data-stu-id="8b435-291">The staged registry data has two distinct types of machine data and user data.</span></span> <span data-ttu-id="8b435-292">機器資料會在電腦上的所有使用者之間共用。</span><span class="sxs-lookup"><span data-stu-id="8b435-292">Machine data is shared across all users on the machine.</span></span> <span data-ttu-id="8b435-293">針對每位使用者將使用者資料轉移至 userspecific 位置 `HKCU\Software\Microsoft\AppV\Client\Packages\PackageGuid\Registry\User` 。</span><span class="sxs-lookup"><span data-stu-id="8b435-293">User data is staged for each user to a userspecific location `HKCU\Software\Microsoft\AppV\Client\Packages\PackageGuid\Registry\User`.</span></span> <span data-ttu-id="8b435-294">在套件移除時，電腦資料最終會移除，而在使用者取消發佈作業時，就會移除使用者資料。</span><span class="sxs-lookup"><span data-stu-id="8b435-294">The machine data is ultimately removed at package removal time, and the user data is removed on a user unpublish operation.</span></span>

### <span data-ttu-id="8b435-295">套件註冊暫存與連接群組登錄</span><span class="sxs-lookup"><span data-stu-id="8b435-295">Package registry staging vs. connection group registry staging</span></span>

<span data-ttu-id="8b435-296">當連線群組存在時，前一次暫存登錄的程式會保留為 true，但不會有一個要處理的 hive 檔案。</span><span class="sxs-lookup"><span data-stu-id="8b435-296">When connection groups are present, the previous process of staging the registry holds true, but instead of having one hive file to process, there are more than one.</span></span> <span data-ttu-id="8b435-297">檔案會按照其在連線群組 XML 中出現的順序進行處理，第一個寫入程式入選任何衝突。</span><span class="sxs-lookup"><span data-stu-id="8b435-297">The files are processed in the order in which they appear in the connection group XML, with the first writer winning any conflicts.</span></span>

<span data-ttu-id="8b435-298">分段式登錄的保持方式與單一套件大小寫中相同。</span><span class="sxs-lookup"><span data-stu-id="8b435-298">The staged registry persists the same way as in the single package case.</span></span> <span data-ttu-id="8b435-299">分段的使用者登錄資料會保留在連線群組中，直到停用為止;在移除連線群組時，會移除分段式電腦登錄資料。</span><span class="sxs-lookup"><span data-stu-id="8b435-299">Staged user registry data remains for the connection group until it is disabled; staged machine registry data is removed on connection group removal.</span></span>

### <span data-ttu-id="8b435-300">虛擬註冊表</span><span class="sxs-lookup"><span data-stu-id="8b435-300">Virtual registry</span></span>

<span data-ttu-id="8b435-301">虛擬 registry （VREG）的用途是提供單一合併的套件註冊和原生登錄視圖給應用程式。</span><span class="sxs-lookup"><span data-stu-id="8b435-301">The purpose of the virtual registry (VREG) is to provide a single merged view of the package registry and the native registry to applications.</span></span> <span data-ttu-id="8b435-302">它也提供寫操作（牛）功能，即從虛擬程式內容對註冊表所做的任何變更，都是在個別的牛位置進行。</span><span class="sxs-lookup"><span data-stu-id="8b435-302">It also provides copy-on-write (COW) functionality – that is any changes made to the registry from the context of a virtual process are made to a separate COW location.</span></span> <span data-ttu-id="8b435-303">這表示 VREG 必須將最多三個不同的登錄位置合併成單一視圖，這是根據在註冊表的 [牛封裝-非本機] 中所填入的位置 &gt; &gt; 。</span><span class="sxs-lookup"><span data-stu-id="8b435-303">This means that the VREG must combine up to three separate registry locations into a single view based on the populated locations in the registry COW -&gt; package -&gt; native.</span></span> <span data-ttu-id="8b435-304">針對登錄資料進行要求時，系統會依順序找到該資料，直到找到所要求的資料為止。</span><span class="sxs-lookup"><span data-stu-id="8b435-304">When a request is made for a registry data it will locate in order until it finds the data it was requesting.</span></span> <span data-ttu-id="8b435-305">意義如果在牛位置儲存的值不會繼續進行其他位置，不過，如果您在 [牛位置] 中沒有任何資料，就會繼續進行，直到找到適當的資料為止。</span><span class="sxs-lookup"><span data-stu-id="8b435-305">Meaning if there is a value stored in a COW location it will not proceed to other locations, however, if there is no data in the COW location it will proceed to the Package and then Native location until it finds the appropriate data.</span></span>

### <span data-ttu-id="8b435-306">登錄位置</span><span class="sxs-lookup"><span data-stu-id="8b435-306">Registry locations</span></span>

<span data-ttu-id="8b435-307">應用程式-V 用戶端根據套件是個別發行或連線群組的一部分，有兩個套件登錄位置和兩個連線群組位置。</span><span class="sxs-lookup"><span data-stu-id="8b435-307">There are two package registry locations and two connection group locations where the App-V Client stores registry information, depending on whether the Package is published individually or as part of a connection group.</span></span> <span data-ttu-id="8b435-308">套件有三個牛位置，而連接群組則是3個，由 VREG 建立及管理。</span><span class="sxs-lookup"><span data-stu-id="8b435-308">There are three COW locations for packages and three for connection groups, which are created and managed by the VREG.</span></span> <span data-ttu-id="8b435-309">套件和連線群組的設定不會共用：</span><span class="sxs-lookup"><span data-stu-id="8b435-309">Settings for packages and connection groups are not shared:</span></span>

**<span data-ttu-id="8b435-310">單一套件 VReg：</span><span class="sxs-lookup"><span data-stu-id="8b435-310">Single Package VReg:</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="8b435-311">位置</span><span class="sxs-lookup"><span data-stu-id="8b435-311">Location</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="8b435-312">說明</span><span class="sxs-lookup"><span data-stu-id="8b435-312">Description</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="8b435-313">牛</span><span class="sxs-lookup"><span data-stu-id="8b435-313">COW</span></span></strong></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="8b435-314">電腦 Registry\Client\Packages\PkgGUID\REGISTRY （只有提升程式可以寫入）</span><span class="sxs-lookup"><span data-stu-id="8b435-314">Machine Registry\Client\Packages\PkgGUID\REGISTRY (Only elevate process can write)</span></span></p></li>
<li><p><span data-ttu-id="8b435-315">使用者 Registry\Client\Packages\PkgGUID\REGISTRY （除了 Software\Classes 外，在 HKCU 下寫入的任何內容）</span><span class="sxs-lookup"><span data-stu-id="8b435-315">User Registry\Client\Packages\PkgGUID\REGISTRY (User Roaming anything written under HKCU except Software\Classes</span></span></p></li>
<li><p><span data-ttu-id="8b435-316">使用者登錄 Classes\Client\Packages\PkgGUID\REGISTRY （針對非提升程式的 HKCU\Software\Classes 寫入和 HKLM\）</span><span class="sxs-lookup"><span data-stu-id="8b435-316">User Registry Classes\Client\Packages\PkgGUID\REGISTRY (HKCU\Software\Classes writes and HKLM for non elevated process)</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="8b435-317">套件</span><span class="sxs-lookup"><span data-stu-id="8b435-317">Package</span></span></strong></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="8b435-318">電腦 Registry\Client\Packages\PkgGUID\Versions\VerGuid\Registry\Machine</span><span class="sxs-lookup"><span data-stu-id="8b435-318">Machine Registry\Client\Packages\PkgGUID\Versions\VerGuid\Registry\Machine</span></span></p></li>
<li><p><span data-ttu-id="8b435-319">使用者註冊 Classes\Client\Packages\PkgGUID\Versions\VerGUID\Registry</span><span class="sxs-lookup"><span data-stu-id="8b435-319">User Registry Classes\Client\Packages\PkgGUID\Versions\VerGUID\Registry</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="8b435-320">原始</span><span class="sxs-lookup"><span data-stu-id="8b435-320">Native</span></span></strong></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="8b435-321">原生應用程式登錄位置</span><span class="sxs-lookup"><span data-stu-id="8b435-321">Native application registry location</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

 

**<span data-ttu-id="8b435-322">連接群組 VReg：</span><span class="sxs-lookup"><span data-stu-id="8b435-322">Connection Group VReg:</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="8b435-323">位置</span><span class="sxs-lookup"><span data-stu-id="8b435-323">Location</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="8b435-324">說明</span><span class="sxs-lookup"><span data-stu-id="8b435-324">Description</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="8b435-325">牛</span><span class="sxs-lookup"><span data-stu-id="8b435-325">COW</span></span></strong></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="8b435-326">電腦 Registry\Client\PackageGroups\GrpGUID\REGISTRY （只有提升程式可以寫入）</span><span class="sxs-lookup"><span data-stu-id="8b435-326">Machine Registry\Client\PackageGroups\GrpGUID\REGISTRY (only elevate process can write)</span></span></p></li>
<li><p><span data-ttu-id="8b435-327">使用者 Registry\Client\PackageGroups\GrpGUID\REGISTRY （除了 Software\Classes 之外，任何已寫入 HKCU 的專案</span><span class="sxs-lookup"><span data-stu-id="8b435-327">User Registry\Client\PackageGroups\GrpGUID\REGISTRY (Anything written to HKCU except Software\Classes</span></span></p></li>
<li><p><span data-ttu-id="8b435-328">使用者註冊 Classes\Client\PackageGroups\GrpGUID\REGISTRY</span><span class="sxs-lookup"><span data-stu-id="8b435-328">User Registry Classes\Client\PackageGroups\GrpGUID\REGISTRY</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="8b435-329">套件</span><span class="sxs-lookup"><span data-stu-id="8b435-329">Package</span></span></strong></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="8b435-330">電腦 Registry\Client\PackageGroups\GrpGUID\Versions\VerGUID\REGISTRY</span><span class="sxs-lookup"><span data-stu-id="8b435-330">Machine Registry\Client\PackageGroups\GrpGUID\Versions\VerGUID\REGISTRY</span></span></p></li>
<li><p><span data-ttu-id="8b435-331">使用者註冊 Classes\Client\PackageGroups\GrpGUID\Versions\VerGUID\REGISTRY</span><span class="sxs-lookup"><span data-stu-id="8b435-331">User Registry Classes\Client\PackageGroups\GrpGUID\Versions\VerGUID\REGISTRY</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="8b435-332">原始</span><span class="sxs-lookup"><span data-stu-id="8b435-332">Native</span></span></strong></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="8b435-333">原生應用程式登錄位置</span><span class="sxs-lookup"><span data-stu-id="8b435-333">Native application registry location</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

 

<span data-ttu-id="8b435-334">在 HKLM 中有兩個牛位置;已提升和未提升的程式。</span><span class="sxs-lookup"><span data-stu-id="8b435-334">There are two COW locations for HKLM; elevated and non-elevated processes.</span></span> <span data-ttu-id="8b435-335">已提升的處理常式永遠會將 HKLM 變更寫入在 HKLM 下的安全牛。</span><span class="sxs-lookup"><span data-stu-id="8b435-335">Elevated processes always write HKLM changes to the secure COW under HKLM.</span></span> <span data-ttu-id="8b435-336">未提升的處理常式在 HKCU\\Software\\Classes. 下，永遠會將 HKLM\ 變更寫入非安全的牛</span><span class="sxs-lookup"><span data-stu-id="8b435-336">Non-elevated processes always write HKLM changes to the non-secure COW under HKCU\\Software\\Classes.</span></span> <span data-ttu-id="8b435-337">當應用程式從 HKLM 讀取變更時，提升的進程會從 HKLM 下的安全牛讀取變更。</span><span class="sxs-lookup"><span data-stu-id="8b435-337">When an application reads changes from HKLM, elevated processes will read changes from the secure COW under HKLM.</span></span> <span data-ttu-id="8b435-338">非升高的讀取，請 favoring 在不安全的牛中進行的變更。</span><span class="sxs-lookup"><span data-stu-id="8b435-338">Non-elevated reads from both, favoring the changes made in the unsecure COW first.</span></span>

### <span data-ttu-id="8b435-339">傳遞按鍵</span><span class="sxs-lookup"><span data-stu-id="8b435-339">Pass-through keys</span></span>

<span data-ttu-id="8b435-340">[傳遞金鑰] 可讓系統管理員設定某些金鑰，讓其只能從原生登錄讀取，不需要封裝和牛位置。</span><span class="sxs-lookup"><span data-stu-id="8b435-340">Pass-through keys enable an administrator to configure certain keys so they can only be read from the native registry, bypassing the Package and COW locations.</span></span> <span data-ttu-id="8b435-341">直通位置是在電腦（而非套裝軟體專用）中全域使用，而且可以透過新增該金鑰的路徑加以設定，而這應該會被視為傳遞到 _MULTI**金鑰的** **_SZ**值 `HKLM\Software\Microsoft\AppV\Subsystem\VirtualRegistry` 。</span><span class="sxs-lookup"><span data-stu-id="8b435-341">Pass-through locations are global to the machine (not package specific) and can be configured by adding the path to the key, which should be treated as pass-through to the **REG\_MULTI\_SZ** value called **PassThroughPaths** of the key `HKLM\Software\Microsoft\AppV\Subsystem\VirtualRegistry`.</span></span> <span data-ttu-id="8b435-342">出現在這個多重字串值（及其子系）底下的任何索引鍵，都會被視為傳遞。</span><span class="sxs-lookup"><span data-stu-id="8b435-342">Any key that appears under this multi-string value (and their children) will be treated as pass-through.</span></span>

<span data-ttu-id="8b435-343">預設會將下列位置設定為傳遞位置：</span><span class="sxs-lookup"><span data-stu-id="8b435-343">The following locations are configured as pass-through locations by default:</span></span>

-   <span data-ttu-id="8b435-344">HKEY \ _CURRENT \ _USER \\SOFTWARE\\Classes\\Local Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\AppModel</span><span class="sxs-lookup"><span data-stu-id="8b435-344">HKEY\_CURRENT\_USER\\SOFTWARE\\Classes\\Local Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\AppModel</span></span>

-   <span data-ttu-id="8b435-345">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Classes\\Local Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\AppModel</span><span class="sxs-lookup"><span data-stu-id="8b435-345">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Classes\\Local Settings\\Software\\Microsoft\\Windows\\CurrentVersion\\AppModel</span></span>

-   <span data-ttu-id="8b435-346">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WINEVT</span><span class="sxs-lookup"><span data-stu-id="8b435-346">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\WINEVT</span></span>

-   <span data-ttu-id="8b435-347">HKEY \ _LOCAL \ _MACHINE \\SYSTEM\\CurrentControlSet\\services\\eventlog\\Application</span><span class="sxs-lookup"><span data-stu-id="8b435-347">HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\services\\eventlog\\Application</span></span>

-   <span data-ttu-id="8b435-348">HKEY \ _LOCAL \ _MACHINE \\SYSTEM\\CurrentControlSet\\Control\\WMI\\Autologger</span><span class="sxs-lookup"><span data-stu-id="8b435-348">HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\WMI\\Autologger</span></span>

-   <span data-ttu-id="8b435-349">HKEY \ _CURRENT \ _USER \\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet 設定</span><span class="sxs-lookup"><span data-stu-id="8b435-349">HKEY\_CURRENT\_USER\\SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\Internet Settings</span></span>

-   <span data-ttu-id="8b435-350">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Perflib</span><span class="sxs-lookup"><span data-stu-id="8b435-350">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Perflib</span></span>

-   <span data-ttu-id="8b435-351">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Policies</span><span class="sxs-lookup"><span data-stu-id="8b435-351">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Policies</span></span>

-   <span data-ttu-id="8b435-352">HKEY \ _CURRENT \ _USER \\SOFTWARE\\Policies</span><span class="sxs-lookup"><span data-stu-id="8b435-352">HKEY\_CURRENT\_USER\\SOFTWARE\\Policies</span></span>

<span data-ttu-id="8b435-353">傳遞金鑰的目的是確保虛擬應用程式不會在 VReg 中寫入非虛擬應用程式所需的登錄資料，以進行成功的操作或整合。</span><span class="sxs-lookup"><span data-stu-id="8b435-353">The purpose of Pass-through keys is to ensure that a virtual application does not write registry data in the VReg that is required for non-virtual applications for successful operation or integration.</span></span> <span data-ttu-id="8b435-354">原則金鑰可確保系統會利用管理員設定的 [群組原則] 設定，而不是 [每個套件] 設定。</span><span class="sxs-lookup"><span data-stu-id="8b435-354">The Policies key ensures that Group Policy based settings set by the administrator are utilized and not per package settings.</span></span> <span data-ttu-id="8b435-355">需要使用 AppModel 金鑰來與 Windows 新式 UI 應用程式整合。</span><span class="sxs-lookup"><span data-stu-id="8b435-355">The AppModel key is required for integration with Windows Modern UI based applications.</span></span> <span data-ttu-id="8b435-356">建議管理不要修改任何預設的傳遞金鑰，但在某些情況下，根據應用程式的行為，可能需要新增額外的傳遞按鍵。</span><span class="sxs-lookup"><span data-stu-id="8b435-356">It is recommend that administers do not modify any of the default pass-through keys, but in some instances, based on application behavior may require adding additional pass-through keys.</span></span>

## <a href="" id="bkmk-pkg-store-behavior"></a><span data-ttu-id="8b435-357">App-v 套件儲存行為</span><span class="sxs-lookup"><span data-stu-id="8b435-357">App-V package store behavior</span></span>


<span data-ttu-id="8b435-358">App-V 5 管理套件存放區，這是儲存 appv 檔案之擴充資產檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="8b435-358">App-V 5 manages the Package Store, which is the location where the expanded asset files from the appv file are stored.</span></span> <span data-ttu-id="8b435-359">根據預設，此位置會儲存在%ProgramData%\\App-V，而且只會根據可用磁碟空間來限制儲存功能。</span><span class="sxs-lookup"><span data-stu-id="8b435-359">By default, this location is stored at %ProgramData%\\App-V, and is limited in terms of storage capabilities only by free disk space.</span></span> <span data-ttu-id="8b435-360">套件存放區是按照上一節中提到的封裝與版本的 Guid 來組織。</span><span class="sxs-lookup"><span data-stu-id="8b435-360">The package store is organized by the GUIDs for the package and version as mentioned in the previous section.</span></span>

### <span data-ttu-id="8b435-361">新增套件</span><span class="sxs-lookup"><span data-stu-id="8b435-361">Add packages</span></span>

<span data-ttu-id="8b435-362">使用 App-v 用戶端加入電腦時，會暫存 app-v 套件。</span><span class="sxs-lookup"><span data-stu-id="8b435-362">App-V Packages are staged upon addition to the computer with the App-V Client.</span></span> <span data-ttu-id="8b435-363">App-v 用戶端提供隨選即用的轉移。</span><span class="sxs-lookup"><span data-stu-id="8b435-363">The App-V Client provides on-demand staging.</span></span> <span data-ttu-id="8b435-364">在發佈或手動載入 AppVClientPackage 期間，會在套件存放區（c:\\programdata\\App-V\\{PkgGUID}\\{VerGUID}）中建立資料結構。</span><span class="sxs-lookup"><span data-stu-id="8b435-364">During publishing or a manual Add-AppVClientPackage, the data structure is built in the package store (c:\\programdata\\App-V\\{PkgGUID}\\{VerGUID}).</span></span> <span data-ttu-id="8b435-365">在 StreamMap.xml 中定義的發佈區塊中所識別的套件檔案會新增至系統以及暫存頂層資料夾和子檔案，以確保啟動時有適當的應用程式資產。</span><span class="sxs-lookup"><span data-stu-id="8b435-365">The package files identified in the publishing block defined in the StreamMap.xml are added to the system and the top level folders and child files staged to ensure proper application assets exist at launch.</span></span>

### <span data-ttu-id="8b435-366">安裝套件</span><span class="sxs-lookup"><span data-stu-id="8b435-366">Mounting packages</span></span>

<span data-ttu-id="8b435-367">您可以使用 PowerShell 來顯式載入套件， `Mount-AppVClientPackage` 或使用**App-v 用戶端 UI**來下載套件。</span><span class="sxs-lookup"><span data-stu-id="8b435-367">Packages can be explicitly loaded using the PowerShell `Mount-AppVClientPackage` or by using the **App-V Client UI** to download a package.</span></span> <span data-ttu-id="8b435-368">這個作業會將整個套件完全載入到套件存放區中。</span><span class="sxs-lookup"><span data-stu-id="8b435-368">This operation completely loads the entire package into the package store.</span></span>

### <span data-ttu-id="8b435-369">流式套件</span><span class="sxs-lookup"><span data-stu-id="8b435-369">Streaming packages</span></span>

<span data-ttu-id="8b435-370">App-v 用戶端可以設定為變更資料流程的預設行為。</span><span class="sxs-lookup"><span data-stu-id="8b435-370">The App-V Client can be configured to change the default behavior of streaming.</span></span> <span data-ttu-id="8b435-371">所有的資料流程原則都儲存在下列登錄機碼下： `HKEY_LOCAL_MAcHINE\Software\Microsoft\AppV\Client\Streaming` 。</span><span class="sxs-lookup"><span data-stu-id="8b435-371">All streaming policies are stored under the following registry key: `HKEY_LOCAL_MAcHINE\Software\Microsoft\AppV\Client\Streaming`.</span></span> <span data-ttu-id="8b435-372">原則是使用 PowerShell Cmdlet 來設定 `Set-AppvClientConfiguration` 。</span><span class="sxs-lookup"><span data-stu-id="8b435-372">Policies are set using the PowerShell cmdlet `Set-AppvClientConfiguration`.</span></span> <span data-ttu-id="8b435-373">下列原則適用于流式處理：</span><span class="sxs-lookup"><span data-stu-id="8b435-373">The following policies apply to Streaming:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8b435-374">原則</span><span class="sxs-lookup"><span data-stu-id="8b435-374">Policy</span></span></th>
<th align="left"><span data-ttu-id="8b435-375">說明</span><span class="sxs-lookup"><span data-stu-id="8b435-375">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b435-376">AllowHighCostLaunch</span><span class="sxs-lookup"><span data-stu-id="8b435-376">AllowHighCostLaunch</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-377">在 Windows 8 和更新版本中，它可讓您在3G 與行動網路上傳輸</span><span class="sxs-lookup"><span data-stu-id="8b435-377">On Windows 8 and later, it allows streaming over 3G and cellular networks</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8b435-378">AutoLoad</span><span class="sxs-lookup"><span data-stu-id="8b435-378">AutoLoad</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-379">指定背景載入設定：</span><span class="sxs-lookup"><span data-stu-id="8b435-379">Specifies the Background Load setting:</span></span></p>
<p><strong><span data-ttu-id="8b435-380">0 </strong> - 停用</span><span class="sxs-lookup"><span data-stu-id="8b435-380">0</strong> - Disabled</span></span></p>
<p><strong><span data-ttu-id="8b435-381">1 </strong> -僅限先前使用的套件</span><span class="sxs-lookup"><span data-stu-id="8b435-381">1</strong> – Previously Used Packages only</span></span></p>
<p><strong><span data-ttu-id="8b435-382">2 </strong> -所有套件</span><span class="sxs-lookup"><span data-stu-id="8b435-382">2</strong> – All Packages</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b435-383">PackageInstallationRoot</span><span class="sxs-lookup"><span data-stu-id="8b435-383">PackageInstallationRoot</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-384">本機電腦中套件存放區的根資料夾</span><span class="sxs-lookup"><span data-stu-id="8b435-384">The root folder for the package store in the local machine</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8b435-385">PackageSourceRoot</span><span class="sxs-lookup"><span data-stu-id="8b435-385">PackageSourceRoot</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-386">應從哪個部分來流式處理套件的根覆寫</span><span class="sxs-lookup"><span data-stu-id="8b435-386">The root override where packages should be streamed from</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b435-387">SharedContentStoreMode</span><span class="sxs-lookup"><span data-stu-id="8b435-387">SharedContentStoreMode</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-388">啟用在 VDI 案例中使用共用內容存放區</span><span class="sxs-lookup"><span data-stu-id="8b435-388">Enables the use of Shared Content Store for VDI scenarios</span></span></p></td>
</tr>
</tbody>
</table>

 

 

<span data-ttu-id="8b435-389">這些設定會影響流式處理 app-v 套件資產與用戶端的行為。</span><span class="sxs-lookup"><span data-stu-id="8b435-389">These settings affect the behavior of streaming App-V package assets to the client.</span></span> <span data-ttu-id="8b435-390">根據預設，App-v 只會在下載初始發佈及主要功能區塊之後，下載所需的資產。</span><span class="sxs-lookup"><span data-stu-id="8b435-390">By default, App-V only downloads the assets required after downloading the initial publishing and primary feature blocks.</span></span> <span data-ttu-id="8b435-391">流式套件有三個具體的行為，必須加以說明：</span><span class="sxs-lookup"><span data-stu-id="8b435-391">There are three specific behaviors around streaming packages that must be explained:</span></span>

-   <span data-ttu-id="8b435-392">背景資料流程</span><span class="sxs-lookup"><span data-stu-id="8b435-392">Background Streaming</span></span>

-   <span data-ttu-id="8b435-393">優化的資料流程</span><span class="sxs-lookup"><span data-stu-id="8b435-393">Optimized Streaming</span></span>

-   <span data-ttu-id="8b435-394">資料流程錯誤</span><span class="sxs-lookup"><span data-stu-id="8b435-394">Stream Faults</span></span>

### <span data-ttu-id="8b435-395">背景資料流程</span><span class="sxs-lookup"><span data-stu-id="8b435-395">Background streaming</span></span>

<span data-ttu-id="8b435-396">您 `Get-AppvClientConfiguration` 可以使用 PowerShell Cmdlet 來判斷背景資料流程使用 AutoLoad 設定的目前模式，並使用 Cmdlet Set-AppvClientConfiguration 或從 registry （HKLM\\SOFTWARE\\Microsoft\\AppV\\ClientStreaming 金鑰）進行修改。</span><span class="sxs-lookup"><span data-stu-id="8b435-396">The PowerShell cmdlet `Get-AppvClientConfiguration` can be used to determine the current mode for background streaming with the AutoLoad setting and modified with the cmdlet Set-AppvClientConfiguration or from the registry (HKLM\\SOFTWARE\\Microsoft\\AppV\\ClientStreaming key).</span></span> <span data-ttu-id="8b435-397">[背景資料流程] 是預設設定，其中 [Autoload] 設定設為 [下載先前使用的套件]。</span><span class="sxs-lookup"><span data-stu-id="8b435-397">Background streaming is a default setting where the Autoload setting is set to download previously used packages.</span></span> <span data-ttu-id="8b435-398">根據預設設定（值 = 1）的行為會在應用程式啟動後，在背景下載 app-v 資料區塊。</span><span class="sxs-lookup"><span data-stu-id="8b435-398">The behavior based on default setting (value=1) downloads App-V data blocks in the background after the application has been launched.</span></span> <span data-ttu-id="8b435-399">不論是否已啟動，此設定都可以同時停用（值 = 0）或啟用所有套件（值 = 2）。</span><span class="sxs-lookup"><span data-stu-id="8b435-399">This setting can be disabled all together (value=0) or enabled for all packages (value=2), whether they have been launched.</span></span>

### <span data-ttu-id="8b435-400">優化的資料流程</span><span class="sxs-lookup"><span data-stu-id="8b435-400">Optimized streaming</span></span>

<span data-ttu-id="8b435-401">在排序期間，您可以使用主要功能區塊來設定 app-v 套件。</span><span class="sxs-lookup"><span data-stu-id="8b435-401">App-V packages can be configured with a primary feature block during sequencing.</span></span> <span data-ttu-id="8b435-402">這項設定可讓排序工程針對特定應用程式或應用程式監視啟動檔案，並在套件中第一次啟動應用程式時，將 App-v 套件中的資料區塊標示為流式處理。</span><span class="sxs-lookup"><span data-stu-id="8b435-402">This setting allows the sequencing engineer to monitor launch files for a specific application, or applications, and mark the blocks of data in the App-V package for streaming at first launch of any application in the package.</span></span>

### <span data-ttu-id="8b435-403">資料流程錯誤</span><span class="sxs-lookup"><span data-stu-id="8b435-403">Stream faults</span></span>

<span data-ttu-id="8b435-404">在任何發佈資料和主要功能區塊的初始資料流程之後，需要其他檔案的要求才能執行串流錯誤。</span><span class="sxs-lookup"><span data-stu-id="8b435-404">After the initial stream of any publishing data and the primary feature block, requests for additional files perform stream faults.</span></span> <span data-ttu-id="8b435-405">這些資料區塊會根據需要下載到套件存放區。</span><span class="sxs-lookup"><span data-stu-id="8b435-405">These blocks of data are downloaded to the package store on an as-needed basis.</span></span> <span data-ttu-id="8b435-406">這可讓使用者只下載套件的一小部分，通常是足以啟動套件並執行一般工作。</span><span class="sxs-lookup"><span data-stu-id="8b435-406">This allows a user to download only a small part of the package, typically enough to launch the package and run normal tasks.</span></span> <span data-ttu-id="8b435-407">當使用者啟動的作業需要目前不在套件存放區中的資料時，就會下載所有其他區塊。</span><span class="sxs-lookup"><span data-stu-id="8b435-407">All other blocks are downloaded when a user initiates an operation that requires data not currently in the package store.</span></span>

<span data-ttu-id="8b435-408">如需 App-V 套件流式處理就診的詳細資訊： <https://go.microsoft.com/fwlink/?LinkId=392770> 。</span><span class="sxs-lookup"><span data-stu-id="8b435-408">For more information on App-V Package streaming visit: <https://go.microsoft.com/fwlink/?LinkId=392770>.</span></span>

<span data-ttu-id="8b435-409">您可以在以下網址找到流式處理優化的順序： <https://go.microsoft.com/fwlink/?LinkId=392771> 。</span><span class="sxs-lookup"><span data-stu-id="8b435-409">Sequencing for streaming optimization is available at: <https://go.microsoft.com/fwlink/?LinkId=392771>.</span></span>

### <span data-ttu-id="8b435-410">套件升級</span><span class="sxs-lookup"><span data-stu-id="8b435-410">Package upgrades</span></span>

<span data-ttu-id="8b435-411">App-v 套件在整個應用程式週期中需要更新。</span><span class="sxs-lookup"><span data-stu-id="8b435-411">App-V Packages require updating throughout the lifecycle of the application.</span></span> <span data-ttu-id="8b435-412">App-v 套件升級與套件發佈作業類似，因為每個版本都會在自己的 PackageRoot 位置中建立： `%ProgramData%\App-V\{PkgGUID}\{newVerGUID}` 。</span><span class="sxs-lookup"><span data-stu-id="8b435-412">App-V Package upgrades are similar to the package publish operation, as each version will be created in its own PackageRoot location: `%ProgramData%\App-V\{PkgGUID}\{newVerGUID}`.</span></span> <span data-ttu-id="8b435-413">升級作業是透過從同一個套件的其他版本建立相同與流式處理檔案的硬連結來優化。</span><span class="sxs-lookup"><span data-stu-id="8b435-413">The upgrade operation is optimized by creating hard links to identical- and streamed-files from other versions of the same package.</span></span>

### <span data-ttu-id="8b435-414">套件移除</span><span class="sxs-lookup"><span data-stu-id="8b435-414">Package removal</span></span>

<span data-ttu-id="8b435-415">移除套件時，應用程式 V 用戶端的行為視用於移除的方法而定。</span><span class="sxs-lookup"><span data-stu-id="8b435-415">The behavior of the App-V Client when packages are removed depends on the method used for removal.</span></span> <span data-ttu-id="8b435-416">使用 App-v 完整基礎結構來取消發佈應用程式，會移除使用者目錄檔案（全域發佈的應用程式的電腦目錄），但會保留套件儲存位置和牛位置。</span><span class="sxs-lookup"><span data-stu-id="8b435-416">Using an App-V full infrastructure to unpublish the application, the user catalog files (machine catalog for globally published applications) are removed, but retains the package store location and COW locations.</span></span> <span data-ttu-id="8b435-417">使用 PowerShell Cmdlet `Remove-AppVClientPackge` 來移除 App-v 套件時，會清除套件儲存區位置。</span><span class="sxs-lookup"><span data-stu-id="8b435-417">When the PowerShell cmdlet `Remove-AppVClientPackge` is used to remove an App-V Package, the package store location is cleaned.</span></span> <span data-ttu-id="8b435-418">請記住，從管理伺服器取消發佈 App-v 套件並不會執行移除作業。</span><span class="sxs-lookup"><span data-stu-id="8b435-418">Remember that unpublishing an App-V Package from the Management Server does not perform a Remove operation.</span></span> <span data-ttu-id="8b435-419">這兩個操作都會移除套件儲存套件檔案。</span><span class="sxs-lookup"><span data-stu-id="8b435-419">Neither operation will remove the Package Store package files.</span></span>

## <a href="" id="bkmk-roaming-reg-data"></a><span data-ttu-id="8b435-420">漫遊登錄與資料</span><span class="sxs-lookup"><span data-stu-id="8b435-420">Roaming registry and data</span></span>


<span data-ttu-id="8b435-421">App-V 5 可以在漫遊時提供近乎原生的體驗，視使用的應用程式的撰寫方式而定。</span><span class="sxs-lookup"><span data-stu-id="8b435-421">App-V 5 is able to provide a near-native experience when roaming, depending on how the application being used is written.</span></span> <span data-ttu-id="8b435-422">根據預設，App-v 會根據作業系統的漫遊設定，將儲存在漫遊位置的 AppData 漫遊。</span><span class="sxs-lookup"><span data-stu-id="8b435-422">By default, App-V roams AppData that is stored in the roaming location, based on the roaming configuration of the operating system.</span></span> <span data-ttu-id="8b435-423">儲存檔案資料的其他位置並不會從電腦漫遊到電腦，因為它們位於不在漫遊的位置。</span><span class="sxs-lookup"><span data-stu-id="8b435-423">Other locations for storage of file-based data do not roam from computer to computer, since they are in locations that are not roamed.</span></span>

### <a href="" id="bkmk-clt-inter-roam-reqs"></a><span data-ttu-id="8b435-424">漫遊需求與使用者目錄資料儲存</span><span class="sxs-lookup"><span data-stu-id="8b435-424">Roaming requirements and user catalog data storage</span></span>

<span data-ttu-id="8b435-425">App-v 會儲存資料，代表使用者的目錄狀態，形式如下：</span><span class="sxs-lookup"><span data-stu-id="8b435-425">App-V stores data, which represents the state of the user’s catalog, in the form of:</span></span>

-   <span data-ttu-id="8b435-426">[%Appdata%\\Microsoft\\AppV\\Client\\Catalog] 下的檔案</span><span class="sxs-lookup"><span data-stu-id="8b435-426">Files under %appdata%\\Microsoft\\AppV\\Client\\Catalog</span></span>

-   <span data-ttu-id="8b435-427">中的 [登錄] 設定</span><span class="sxs-lookup"><span data-stu-id="8b435-427">Registry settings under</span></span> `HKEY_CURRENT_USER\Software\Microsoft\AppV\Client\Packages`

<span data-ttu-id="8b435-428">總之，這些檔案和登錄設定代表使用者的目錄，所以兩者都必須是漫遊，或者都不是特定使用者的漫遊。</span><span class="sxs-lookup"><span data-stu-id="8b435-428">Together, these files and registry settings represent the user’s catalog, so either both must be roamed, or neither must be roamed for a given user.</span></span> <span data-ttu-id="8b435-429">App-v 不支援漫遊% AppData%，但無法漫遊使用者的設定檔（registry），或相反的情況。</span><span class="sxs-lookup"><span data-stu-id="8b435-429">App-V does not support roaming %AppData%, but not roaming the user’s profile (registry), or vice versa.</span></span>

<span data-ttu-id="8b435-430">**記事** **AppvClientPackage** Cmdlet 不會修復套件的發佈狀態，即使用者的 app-v 狀態 `HKEY_CURRENT_USER` 缺失或與% appdata% 中的資料不匹配。</span><span class="sxs-lookup"><span data-stu-id="8b435-430">**Note** The **Repair-AppvClientPackage** cmdlet does not repair the publishing state of packages, where the user’s App-V state under `HKEY_CURRENT_USER` is missing or mismatched with the data in %appdata%.</span></span>

 

### <span data-ttu-id="8b435-431">以註冊表為基礎的資料</span><span class="sxs-lookup"><span data-stu-id="8b435-431">Registry-based data</span></span>

<span data-ttu-id="8b435-432">App-v registry 漫遊分為兩個案例，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="8b435-432">App-V registry roaming falls into two scenarios, as shown in the following table.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8b435-433">案例</span><span class="sxs-lookup"><span data-stu-id="8b435-433">Scenario</span></span></th>
<th align="left"><span data-ttu-id="8b435-434">描述</span><span class="sxs-lookup"><span data-stu-id="8b435-434">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b435-435">以標準使用者身分執行的應用程式</span><span class="sxs-lookup"><span data-stu-id="8b435-435">Applications that are run as standard users</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-436">當標準使用者啟動 App-v 應用程式時，應用程式 V 應用程式的 HKLM\ 和 HKCU 都儲存在電腦上的 HKCU hive 中。</span><span class="sxs-lookup"><span data-stu-id="8b435-436">When a standard user launches an App-V application, both HKLM and HKCU for App-V applications are stored in the HKCU hive on the machine.</span></span> <span data-ttu-id="8b435-437">這會顯示為兩個不同的路徑：</span><span class="sxs-lookup"><span data-stu-id="8b435-437">This presents as two distinct paths:</span></span></p>
<ul>
<li><p><span data-ttu-id="8b435-438">HKLM\： HKCU\SOFTWARE\Classes\AppV\Client\Packages {PkgGUID} \ REGISTRY\MACHINE\SOFTWARE</span><span class="sxs-lookup"><span data-stu-id="8b435-438">HKLM: HKCU\SOFTWARE\Classes\AppV\Client\Packages{PkgGUID}\REGISTRY\MACHINE\SOFTWARE</span></span></p></li>
<li><p><span data-ttu-id="8b435-439">HKCU： HKCU\SOFTWARE\Microsoft\AppV\Client\Packages {PkgGUID} \ REGISTRY\USER {UserSID} \ 軟體</span><span class="sxs-lookup"><span data-stu-id="8b435-439">HKCU: HKCU\SOFTWARE\Microsoft\AppV\Client\Packages{PkgGUID}\REGISTRY\USER{UserSID}\SOFTWARE</span></span></p></li>
</ul>
<p><span data-ttu-id="8b435-440">位置會根據作業系統設定而啟用漫遊。</span><span class="sxs-lookup"><span data-stu-id="8b435-440">The locations are enabled for roaming based on the operating system settings.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8b435-441">以提升方式執行的應用程式</span><span class="sxs-lookup"><span data-stu-id="8b435-441">Applications that are run with elevation</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-442">使用仰角啟動應用程式時：</span><span class="sxs-lookup"><span data-stu-id="8b435-442">When an application is launched with elevation:</span></span></p>
<ul>
<li><p><span data-ttu-id="8b435-443">HKLM 資料儲存在本機電腦上的 HKLM hive 中</span><span class="sxs-lookup"><span data-stu-id="8b435-443">HKLM data is stored in the HKLM hive on the local computer</span></span></p></li>
<li><p><span data-ttu-id="8b435-444">HKCU 資料會儲存在使用者的登錄位置</span><span class="sxs-lookup"><span data-stu-id="8b435-444">HKCU data is stored in the User Registry location</span></span></p></li>
</ul>
<p><span data-ttu-id="8b435-445">在這種情況下，這些設定不是使用標準作業系統漫遊配置進行漫遊，且產生的登錄機碼和值會儲存在下列位置：</span><span class="sxs-lookup"><span data-stu-id="8b435-445">In this scenario, these settings are not roamed with normal operating system roaming configurations, and the resulting registry keys and values are stored in the following location:</span></span></p>
<ul>
<li><p><span data-ttu-id="8b435-446">HKLM\SOFTWARE\Microsoft\AppV\Client\Packages{PkgGUID}{UserSID}\REGISTRY\MACHINE\SOFTWARE</span><span class="sxs-lookup"><span data-stu-id="8b435-446">HKLM\SOFTWARE\Microsoft\AppV\Client\Packages{PkgGUID}{UserSID}\REGISTRY\MACHINE\SOFTWARE</span></span></p></li>
<li><p><span data-ttu-id="8b435-447">HKCU\SOFTWARE\Microsoft\AppV\Client\Packages {PkgGUID} \ Registry\User {UserSID} \ 軟體</span><span class="sxs-lookup"><span data-stu-id="8b435-447">HKCU\SOFTWARE\Microsoft\AppV\Client\Packages{PkgGUID}\Registry\User{UserSID}\SOFTWARE</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="8b435-448">App-v 與資料夾重新導向</span><span class="sxs-lookup"><span data-stu-id="8b435-448">App-V and folder redirection</span></span>

<span data-ttu-id="8b435-449">App-V 5.1 支援漫遊 AppData 資料夾的資料夾重新導向（% AppData%）。</span><span class="sxs-lookup"><span data-stu-id="8b435-449">App-V 5.1 supports folder redirection of the roaming AppData folder (%AppData%).</span></span> <span data-ttu-id="8b435-450">啟動虛擬環境時，會將來自使用者的漫遊 AppData 目錄的漫遊 AppData 狀態複製到本機快取。</span><span class="sxs-lookup"><span data-stu-id="8b435-450">When the virtual environment is started, the roaming AppData state from the user’s roaming AppData directory is copied to the local cache.</span></span> <span data-ttu-id="8b435-451">相反地，當虛擬環境關閉時，會將與特定使用者的漫遊 AppData 相關聯的本機快取傳送到該使用者的 [漫遊 AppData] 目錄的實際位置。</span><span class="sxs-lookup"><span data-stu-id="8b435-451">Conversely, when the virtual environment is shut down, the local cache that is associated with a specific user’s roaming AppData is transferred to the actual location of that user’s roaming AppData directory.</span></span>

<span data-ttu-id="8b435-452">典型的封裝會在使用者的後備儲存體中對應數個位置，以取得 AppData\\Local 和 AppData\\Roaming. 中的設定。</span><span class="sxs-lookup"><span data-stu-id="8b435-452">A typical package has several locations mapped in the user’s backing store for settings in both AppData\\Local and AppData\\Roaming.</span></span> <span data-ttu-id="8b435-453">這些位置是儲存在使用者設定檔中每位使用者的寫位置上的複本，且用來儲存對套件 VFS 目錄所做的變更，以及保護預設套件 VFS。</span><span class="sxs-lookup"><span data-stu-id="8b435-453">These locations are the Copy on Write locations that are stored per user in the user’s profile, and that are used to store changes made to the package VFS directories and to protect the default package VFS.</span></span>

<span data-ttu-id="8b435-454">下表顯示在尚未實現資料夾重新導向時的本機和漫遊位置。</span><span class="sxs-lookup"><span data-stu-id="8b435-454">The following table shows local and roaming locations, when folder redirection has not been implemented.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8b435-455">套件中的 VFS 目錄</span><span class="sxs-lookup"><span data-stu-id="8b435-455">VFS directory in package</span></span></th>
<th align="left"><span data-ttu-id="8b435-456">後備存放區的對應位置</span><span class="sxs-lookup"><span data-stu-id="8b435-456">Mapped location of backing store</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b435-457">ProgramFilesX86</span><span class="sxs-lookup"><span data-stu-id="8b435-457">ProgramFilesX86</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-458">C:\users\jsmith\AppData &lt; 強勁的 &gt; Local </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \ProgramFilesX86</span><span class="sxs-lookup"><span data-stu-id="8b435-458">C:\users\jsmith\AppData&lt;strong&gt;Local</strong>\Microsoft\AppV\Client\VFS&amp;lt;GUID&gt;\ProgramFilesX86</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8b435-459">SystemX86</span><span class="sxs-lookup"><span data-stu-id="8b435-459">SystemX86</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-460">C:\users\jsmith\AppData &lt; 強勁的 &gt; Local </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \SystemX86</span><span class="sxs-lookup"><span data-stu-id="8b435-460">C:\users\jsmith\AppData&lt;strong&gt;Local</strong>\Microsoft\AppV\Client\VFS&amp;lt;GUID&gt;\SystemX86</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b435-461">Windows</span><span class="sxs-lookup"><span data-stu-id="8b435-461">Windows</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-462">C:\users\jsmith\AppData &lt; 強勁的 &gt; Local </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \windows</span><span class="sxs-lookup"><span data-stu-id="8b435-462">C:\users\jsmith\AppData&lt;strong&gt;Local</strong>\Microsoft\AppV\Client\VFS&amp;lt;GUID&gt;\Windows</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8b435-463">appv_ROOT</span><span class="sxs-lookup"><span data-stu-id="8b435-463">appv_ROOT</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-464">C:\users\jsmith\AppData &lt; 強勁的 &gt; Local </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \ appv_ROOT</span><span class="sxs-lookup"><span data-stu-id="8b435-464">C:\users\jsmith\AppData&lt;strong&gt;Local</strong>\Microsoft\AppV\Client\VFS&amp;lt;GUID&gt;\appv_ROOT</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b435-465">AppData</span><span class="sxs-lookup"><span data-stu-id="8b435-465">AppData</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-466">C:\users\jsmith\AppData &lt; 強 &gt; 漫遊 </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \AppData</span><span class="sxs-lookup"><span data-stu-id="8b435-466">C:\users\jsmith\AppData&lt;strong&gt;Roaming</strong>\Microsoft\AppV\Client\VFS&amp;lt;GUID&gt;\AppData</span></span></p></td>
</tr>
</tbody>
</table>

 

 

<span data-ttu-id="8b435-467">下表顯示本機和漫遊位置、已完成% AppData% 的資料夾重新導向，且位置已經重新導向（通常是網路位置）。</span><span class="sxs-lookup"><span data-stu-id="8b435-467">The following table shows local and roaming locations, when folder redirection has been implemented for %AppData%, and the location has been redirected (typically to a network location).</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8b435-468">套件中的 VFS 目錄</span><span class="sxs-lookup"><span data-stu-id="8b435-468">VFS directory in package</span></span></th>
<th align="left"><span data-ttu-id="8b435-469">後備存放區的對應位置</span><span class="sxs-lookup"><span data-stu-id="8b435-469">Mapped location of backing store</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b435-470">ProgramFilesX86</span><span class="sxs-lookup"><span data-stu-id="8b435-470">ProgramFilesX86</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-471">C:\users\jsmith\AppData &lt; 強勁的 &gt; Local </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \ProgramFilesX86</span><span class="sxs-lookup"><span data-stu-id="8b435-471">C:\users\jsmith\AppData&lt;strong&gt;Local</strong>\Microsoft\AppV\Client\VFS&amp;lt;GUID&gt;\ProgramFilesX86</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8b435-472">SystemX86</span><span class="sxs-lookup"><span data-stu-id="8b435-472">SystemX86</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-473">C:\users\jsmith\AppData &lt; 強勁的 &gt; Local </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \SystemX86</span><span class="sxs-lookup"><span data-stu-id="8b435-473">C:\users\jsmith\AppData&lt;strong&gt;Local</strong>\Microsoft\AppV\Client\VFS&amp;lt;GUID&gt;\SystemX86</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b435-474">Windows</span><span class="sxs-lookup"><span data-stu-id="8b435-474">Windows</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-475">C:\users\jsmith\AppData &lt; 強勁的 &gt; Local </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \windows</span><span class="sxs-lookup"><span data-stu-id="8b435-475">C:\users\jsmith\AppData&lt;strong&gt;Local</strong>\Microsoft\AppV\Client\VFS&amp;lt;GUID&gt;\Windows</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8b435-476">appv_ROOT</span><span class="sxs-lookup"><span data-stu-id="8b435-476">appv_ROOT</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-477">C:\users\jsmith\AppData &lt; 強勁的 &gt; Local </strong> \Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \ appv_ROOT</span><span class="sxs-lookup"><span data-stu-id="8b435-477">C:\users\jsmith\AppData&lt;strong&gt;Local</strong>\Microsoft\AppV\Client\VFS&amp;lt;GUID&gt;\appv_ROOT</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b435-478">AppData</span><span class="sxs-lookup"><span data-stu-id="8b435-478">AppData</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="8b435-479">\Fileserver </strong> \users\jsmith\roaming\Microsoft\AppV\Client\VFS &amp; lt;GUID &gt; \AppData</span><span class="sxs-lookup"><span data-stu-id="8b435-479">\Fileserver</strong>\users\jsmith\roaming\Microsoft\AppV\Client\VFS&amp;lt;GUID&gt;\AppData</span></span></p></td>
</tr>
</tbody>
</table>

 

 

<span data-ttu-id="8b435-480">目前的 App-V 用戶端 VFS 驅動程式無法寫入網路位置，因此 App-V 用戶端會偵測到資料夾重新導向的狀態，並在發行期間和虛擬環境啟動時，複製本機磁片磁碟機上的資料。</span><span class="sxs-lookup"><span data-stu-id="8b435-480">The current App-V Client VFS driver cannot write to network locations, so the App-V Client detects the presence of folder redirection and copies the data on the local drive during publishing and when the virtual environment starts.</span></span> <span data-ttu-id="8b435-481">在使用者關閉 App V 應用程式，且 App-v 用戶端關閉虛擬環境之後，會將 VFS AppData 的本地儲存空間複製回網路，並啟用其他電腦的漫遊，而這會重複處理常式。</span><span class="sxs-lookup"><span data-stu-id="8b435-481">After the user closes the App-V application and the App-V Client closes the virtual environment, the local storage of the VFS AppData is copied back to the network, enabling roaming to additional machines, where the process will be repeated.</span></span> <span data-ttu-id="8b435-482">處理常式的詳細步驟如下：</span><span class="sxs-lookup"><span data-stu-id="8b435-482">The detailed steps of the processes are:</span></span>

1.  <span data-ttu-id="8b435-483">在發佈或虛擬環境啟動期間，App-V 用戶端會偵測 AppData 目錄的位置。</span><span class="sxs-lookup"><span data-stu-id="8b435-483">During publishing or virtual environment startup, the App-V Client detects the location of the AppData directory.</span></span>

2.  <span data-ttu-id="8b435-484">如果漫遊 AppData 路徑是 [本機] 或 [.ino AppData\\Roaming 位置已對應]，則不會發生任何情況。</span><span class="sxs-lookup"><span data-stu-id="8b435-484">If the roaming AppData path is local or ino AppData\\Roaming location is mapped, nothing happens.</span></span>

3.  <span data-ttu-id="8b435-485">如果漫遊 AppData 路徑不是本機路徑，則 VFS AppData 目錄會對應到本機 AppData 目錄。</span><span class="sxs-lookup"><span data-stu-id="8b435-485">If the roaming AppData path is not local, the VFS AppData directory is mapped to the local AppData directory.</span></span>

<span data-ttu-id="8b435-486">這個處理常式可解決 App-v 用戶端用戶端 VFS 驅動程式不支援的非本機% AppData% 的問題。</span><span class="sxs-lookup"><span data-stu-id="8b435-486">This process solves the problem of a non-local %AppData% that is not supported by the App-V Client VFS driver.</span></span> <span data-ttu-id="8b435-487">不過，儲存在這個新位置的資料不會與 [資料夾重新導向] 漫遊。</span><span class="sxs-lookup"><span data-stu-id="8b435-487">However, the data stored in this new location is not roamed with folder redirection.</span></span> <span data-ttu-id="8b435-488">在應用程式執行期間的所有變更，都是在本機 AppData 位置進行，而且必須複製到重新導向的位置。</span><span class="sxs-lookup"><span data-stu-id="8b435-488">All changes during the running of the application happen to the local AppData location and must be copied to the redirected location.</span></span> <span data-ttu-id="8b435-489">此處理程式的詳細步驟如下：</span><span class="sxs-lookup"><span data-stu-id="8b435-489">The detailed steps of this process are:</span></span>

1.  <span data-ttu-id="8b435-490">App-v 應用程式會關閉，進而關閉虛擬環境。</span><span class="sxs-lookup"><span data-stu-id="8b435-490">App-V application is shut down, which shuts down the virtual environment.</span></span>

2.  <span data-ttu-id="8b435-491">漫遊 AppData 位置的本機快取會壓縮並儲存在 ZIP 檔案中。</span><span class="sxs-lookup"><span data-stu-id="8b435-491">The local cache of the roaming AppData location is compressed and stored in a ZIP file.</span></span>

3.  <span data-ttu-id="8b435-492">ZIP 封裝程式結尾的時間戳記是用來命名檔案。</span><span class="sxs-lookup"><span data-stu-id="8b435-492">A timestamp at the end of the ZIP packaging process is used to name the file.</span></span>

4.  <span data-ttu-id="8b435-493">時間戳記會記錄在註冊表中： HKEY \ _CURRENT \ _USER \\Software\\Microsoft\\AppV\\Client\\Packages\\ &lt; GUID &gt; \\AppDataTime 做為最近已知的 AppData 時間戳記。</span><span class="sxs-lookup"><span data-stu-id="8b435-493">The timestamp is recorded in the registry: HKEY\_CURRENT\_USER\\Software\\Microsoft\\AppV\\Client\\Packages\\&lt;GUID&gt;\\AppDataTime as the last known AppData timestamp.</span></span>

5.  <span data-ttu-id="8b435-494">呼叫資料夾重新導向程式是為了評估並啟動上傳到漫遊 AppData 目錄的 ZIP 檔案。</span><span class="sxs-lookup"><span data-stu-id="8b435-494">The folder redirection process is called to evaluate and initiate the ZIP file uploaded to the roaming AppData directory.</span></span>

<span data-ttu-id="8b435-495">如果發生衝突，則會使用時間戳來判斷「最後一個寫入程式入選」案例，並用於在發佈 app-v 應用程式或啟動虛擬環境時，優化下載資料。</span><span class="sxs-lookup"><span data-stu-id="8b435-495">The timestamp is used to determine a “last writer wins” scenario if there is a conflict and is used to optimize the download of the data when the App-V application is published or the virtual environment is started.</span></span> <span data-ttu-id="8b435-496">[資料夾重新導向] 會讓支援原則所涵蓋的任何其他用戶端提供該資料，並啟動將 AppData\\Roaming 資料儲存到用戶端上的本機 AppData 位置的程式。</span><span class="sxs-lookup"><span data-stu-id="8b435-496">Folder redirection will make the data available from any other clients covered by the supporting policy and will initiate the process of storing the AppData\\Roaming data to the local AppData location on the client.</span></span> <span data-ttu-id="8b435-497">詳細的程式如下：</span><span class="sxs-lookup"><span data-stu-id="8b435-497">The detailed processes are:</span></span>

1.  <span data-ttu-id="8b435-498">使用者啟動應用程式，即可啟動虛擬環境。</span><span class="sxs-lookup"><span data-stu-id="8b435-498">The user starts the virtual environment by starting an application.</span></span>

2.  <span data-ttu-id="8b435-499">應用程式的虛擬環境會檢查最近一時間戳的 ZIP 檔案（如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="8b435-499">The application’s virtual environment checks for the most recent time stamped ZIP file, if present.</span></span>

3.  <span data-ttu-id="8b435-500">針對最近已知上傳的時間戳記（如果有的話），就會選取該註冊表。</span><span class="sxs-lookup"><span data-stu-id="8b435-500">The registry is checked for the last known uploaded timestamp, if present.</span></span>

4.  <span data-ttu-id="8b435-501">除非當地的上一個已知上傳時間戳記大於或等於 ZIP 檔案中的時間戳記，否則會下載最新的 ZIP 檔案。</span><span class="sxs-lookup"><span data-stu-id="8b435-501">The most recent ZIP file is downloaded unless the local last known upload timestamp is greater than or equal to the timestamp from the ZIP file.</span></span>

5.  <span data-ttu-id="8b435-502">如果當地的上次已知上傳時間戳記早于漫遊 AppData 位置中的最新 ZIP 檔案，則會將 ZIP 檔案解壓縮至使用者設定檔中的本機 temp 目錄。</span><span class="sxs-lookup"><span data-stu-id="8b435-502">If the local last known upload timestamp is earlier than that of the most recent ZIP file in the roaming AppData location, the ZIP file is extracted to the local temp directory in the user’s profile.</span></span>

6.  <span data-ttu-id="8b435-503">在成功解壓縮 ZIP 檔案之後，就會重新命名漫遊 AppData 目錄的本機快取，並將新資料移至 [位置]。</span><span class="sxs-lookup"><span data-stu-id="8b435-503">After the ZIP file is successfully extracted, the local cache of the roaming AppData directory is renamed and the new data is moved into place.</span></span>

7.  <span data-ttu-id="8b435-504">已重新命名的目錄隨即刪除，且應用程式會開啟最近儲存的漫遊 AppData 資料。</span><span class="sxs-lookup"><span data-stu-id="8b435-504">The renamed directory is deleted and the application opens with the most recently saved roaming AppData data.</span></span>

<span data-ttu-id="8b435-505">這會完成 AppData\\Roaming 位置中存在的應用程式設定成功漫遊。</span><span class="sxs-lookup"><span data-stu-id="8b435-505">This completes the successful roaming of application settings that are present in AppData\\Roaming locations.</span></span> <span data-ttu-id="8b435-506">唯一必須解決的其他條件是套件修復操作。</span><span class="sxs-lookup"><span data-stu-id="8b435-506">The only other condition that must be addressed is a package repair operation.</span></span> <span data-ttu-id="8b435-507">處理常式的詳細資料如下：</span><span class="sxs-lookup"><span data-stu-id="8b435-507">The details of the process are:</span></span>

1.  <span data-ttu-id="8b435-508">在修復期間，偵測使用者的漫遊 AppData 目錄路徑是否不在本機。</span><span class="sxs-lookup"><span data-stu-id="8b435-508">During repair, detect if the path to the user’s roaming AppData directory is not local.</span></span>

2.  <span data-ttu-id="8b435-509">將非本機漫遊 AppData 路徑目標重新建立在預期的漫遊和本機 AppData 位置。</span><span class="sxs-lookup"><span data-stu-id="8b435-509">Map the non-local roaming AppData path targets are recreated the expected roaming and local AppData locations.</span></span>

3.  <span data-ttu-id="8b435-510">刪除儲存在註冊表中的時間戳記（如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="8b435-510">Delete the timestamp stored in the registry, if present.</span></span>

<span data-ttu-id="8b435-511">這個程式將會重新建立 AppData 的本機和網路位置，並移除時間戳記的註冊記錄。</span><span class="sxs-lookup"><span data-stu-id="8b435-511">This process will re-create both the local and network locations for AppData and remove the registry record of the timestamp.</span></span>

## <a href="" id="bkmk-clt-app-lifecycle"></a><span data-ttu-id="8b435-512">App-V 用戶端應用程式週期管理</span><span class="sxs-lookup"><span data-stu-id="8b435-512">App-V client application lifecycle management</span></span>


<span data-ttu-id="8b435-513">在 App-v 完整基礎結構中，將應用程式排序之後，會透過 App-v 管理和發佈伺服器來管理併發布至使用者或電腦。</span><span class="sxs-lookup"><span data-stu-id="8b435-513">In an App-V Full Infrastructure, after applications are sequenced they are managed and published to users or computers via the App-V Management and Publishing servers.</span></span> <span data-ttu-id="8b435-514">本節詳細說明常見 App-v 應用程式生命週期作業（新增、發佈、啟動、升級及移除）期間發生的作業，以及從 App-v 用戶端角度變更並修改的檔案和註冊表位置。</span><span class="sxs-lookup"><span data-stu-id="8b435-514">This section details the operations that occur during the common App-V application lifecycle operations (Add, publishing, launch, upgrade, and removal) and the file and registry locations that are changed and modified from the App-V Client perspective.</span></span> <span data-ttu-id="8b435-515">App-v 用戶端作業是以在執行 App-v 用戶端的電腦上啟動的一系列 PowerShell 命令來執行。</span><span class="sxs-lookup"><span data-stu-id="8b435-515">The App-V Client operations are performed as a series of PowerShell commands initiated on the computer running the App-V Client.</span></span>

<span data-ttu-id="8b435-516">本檔的重點是應用程式-V 完整基礎結構解決方案。</span><span class="sxs-lookup"><span data-stu-id="8b435-516">This document focuses on App-V Full Infrastructure solutions.</span></span> <span data-ttu-id="8b435-517">如需與 Configuration Manager 2012 進行 App-v 整合的特定資訊，請造訪： <https://go.microsoft.com/fwlink/?LinkId=392773> 。</span><span class="sxs-lookup"><span data-stu-id="8b435-517">For specific information on App-V Integration with Configuration Manager 2012 visit: <https://go.microsoft.com/fwlink/?LinkId=392773>.</span></span>

<span data-ttu-id="8b435-518">App-v 應用程式週期任務會在使用者登入（預設）、電腦啟動或背景定時作業時觸發。</span><span class="sxs-lookup"><span data-stu-id="8b435-518">The App-V application lifecycle tasks are triggered at user login (default), machine startup, or as background timed operations.</span></span> <span data-ttu-id="8b435-519">App-V 用戶端作業的設定，包括發佈伺服器、重新整理間隔、套件腳本啟用及其他，都是在設定用戶端或使用 PowerShell 命令進行安裝後設定。</span><span class="sxs-lookup"><span data-stu-id="8b435-519">The settings for the App-V Client operations, including Publishing Servers, refresh intervals, package script enablement, and others, are configured during setup of the client or post-setup with PowerShell commands.</span></span> <span data-ttu-id="8b435-520">請參閱 TechNet 上的 [如何部署用戶端] 區段，網址為：[如何部署 App-v 用戶端](how-to-deploy-the-app-v-client-51gb18030.md)或使用 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="8b435-520">See the How to Deploy the Client section on TechNet at: [How to Deploy the App-V Client](how-to-deploy-the-app-v-client-51gb18030.md) or utilize the PowerShell:</span></span>

```powershell
get-command *appv*
```

### <span data-ttu-id="8b435-521">發佈更新</span><span class="sxs-lookup"><span data-stu-id="8b435-521">Publishing refresh</span></span>

<span data-ttu-id="8b435-522">發佈重新整理程式是由在 App-V 用戶端上執行的數個較小的操作所組成。</span><span class="sxs-lookup"><span data-stu-id="8b435-522">The publishing refresh process is comprised of several smaller operations that are performed on the App-V Client.</span></span> <span data-ttu-id="8b435-523">因為 App-v 是應用程式虛擬化技術，而不是任務排程技術，所以使用 Windows 工作計畫程式在使用者登入、電腦啟動時，以及按排程的時間間隔啟用該處理常式。</span><span class="sxs-lookup"><span data-stu-id="8b435-523">Since App-V is an application virtualization technology and not a task scheduling technology, the Windows Task Scheduler is utilized to enable the process at user logon, machine startup, and at scheduled intervals.</span></span> <span data-ttu-id="8b435-524">當您將用戶端發佈至具有正確設定的大型電腦群組時，以上所列的設定是用戶端的設定。</span><span class="sxs-lookup"><span data-stu-id="8b435-524">The configuration of the client during setup listed above is the preferred method when distributing the client to a large group of computers with the correct settings.</span></span> <span data-ttu-id="8b435-525">您可以使用下列 PowerShell Cmdlet 來設定這些用戶端設定：</span><span class="sxs-lookup"><span data-stu-id="8b435-525">These client settings can be configured with the following PowerShell cmdlets:</span></span>

-   <span data-ttu-id="8b435-526">**載入 AppVPublishingServer：** 使用提供 App-v 套件的 App-v 發佈伺服器來設定用戶端。</span><span class="sxs-lookup"><span data-stu-id="8b435-526">**Add-AppVPublishingServer:** Configures the client with an App-V Publishing Server that provides App-V packages.</span></span>

-   <span data-ttu-id="8b435-527">**AppVPublishingServer：** 修改 App V 發佈伺服器的目前設定。</span><span class="sxs-lookup"><span data-stu-id="8b435-527">**Set-AppVPublishingServer:** Modifies the current settings for the App-V Publishing Server.</span></span>

-   <span data-ttu-id="8b435-528">**AppVClientConfiguration：** 修改 App-V 用戶端的電流設定。</span><span class="sxs-lookup"><span data-stu-id="8b435-528">**Set-AppVClientConfiguration:** Modifies the currents settings for the App-V Client.</span></span>

-   <span data-ttu-id="8b435-529">**同步處理-AppVPublishingServer：** 手動啟動 App-V 發佈重新整理程式。</span><span class="sxs-lookup"><span data-stu-id="8b435-529">**Sync-AppVPublishingServer:** Initiates an App-V Publishing Refresh process manually.</span></span> <span data-ttu-id="8b435-530">在配置發佈伺服器期間建立的排程任務中，也會使用此功能。</span><span class="sxs-lookup"><span data-stu-id="8b435-530">This is also utilized in the scheduled tasks created during configuration of the publishing server.</span></span>

<span data-ttu-id="8b435-531">下列各節的重點是詳細說明在 App-v 發佈重新整理的不同階段期間發生的操作。</span><span class="sxs-lookup"><span data-stu-id="8b435-531">The focus of the following sections is to detail the operations that occur during different phases of an App-V Publishing Refresh.</span></span> <span data-ttu-id="8b435-532">主題包括：</span><span class="sxs-lookup"><span data-stu-id="8b435-532">The topics include:</span></span>

-   <span data-ttu-id="8b435-533">新增 app-v 套件</span><span class="sxs-lookup"><span data-stu-id="8b435-533">Adding an App-V Package</span></span>

-   <span data-ttu-id="8b435-534">發佈 App-v 套件</span><span class="sxs-lookup"><span data-stu-id="8b435-534">Publishing an App-V Package</span></span>

### <span data-ttu-id="8b435-535">新增 app-v 套件</span><span class="sxs-lookup"><span data-stu-id="8b435-535">Adding an App-V package</span></span>

<span data-ttu-id="8b435-536">將 app-v 套件新增到用戶端是發佈重新整理程式的第一個步驟。</span><span class="sxs-lookup"><span data-stu-id="8b435-536">Adding an App-V package to the client is the first step of the publishing refresh process.</span></span> <span data-ttu-id="8b435-537">最終結果與 `Add-AppVClientPackage` PowerShell 中的 Cmdlet 相同，但在發佈重新整理 add 程式期間，已設定的發佈伺服器會取得聯繫，並將一個高層級的應用程式傳回到用戶端，以拉出更詳細的資訊，而不是單一套件新增作業。</span><span class="sxs-lookup"><span data-stu-id="8b435-537">The end result is the same as the `Add-AppVClientPackage` cmdlet in PowerShell, except during the publishing refresh add process, the configured publishing server is contacted and passes a high-level list of applications back to the client to pull more detailed information and not a single package add operation.</span></span> <span data-ttu-id="8b435-538">此程式會繼續設定封裝或連線群組的用戶端新增或更新，然後存取 appv 檔案。</span><span class="sxs-lookup"><span data-stu-id="8b435-538">The process continues by configuring the client for package or connection group additions or updates, then accesses the appv file.</span></span> <span data-ttu-id="8b435-539">接著，會將 appv 檔案的內容擴充並放在本機作業系統的適當位置。</span><span class="sxs-lookup"><span data-stu-id="8b435-539">Next, the contents of the appv file are expanded and placed on the local operating system in the appropriate locations.</span></span> <span data-ttu-id="8b435-540">下列是程式的詳細工作流程（假設套件已設定為可進行故障流式處理）。</span><span class="sxs-lookup"><span data-stu-id="8b435-540">The following is a detailed workflow of the process, assuming the package is configured for Fault Streaming.</span></span>

**<span data-ttu-id="8b435-541">如何新增 app-v 套件</span><span class="sxs-lookup"><span data-stu-id="8b435-541">How to add an App-V package</span></span>**

1.  <span data-ttu-id="8b435-542">透過 PowerShell 啟動手動啟動，或啟動發佈重新整理程式的任務順序。</span><span class="sxs-lookup"><span data-stu-id="8b435-542">Manual initiation via PowerShell or Task Sequence initiation of the Publishing Refresh process.</span></span>

    1.  <span data-ttu-id="8b435-543">App-V 用戶端會建立 HTTP 連線，並根據目標要求應用程式清單。</span><span class="sxs-lookup"><span data-stu-id="8b435-543">The App-V Client makes an HTTP connection and requests a list of applications based on the target.</span></span> <span data-ttu-id="8b435-544">發佈更新程式支援以電腦或使用者為目標。</span><span class="sxs-lookup"><span data-stu-id="8b435-544">The Publishing refresh process supports targeting machines or users.</span></span>

    2.  <span data-ttu-id="8b435-545">App-v 發佈伺服器會使用起始目標、使用者或電腦的身分識別，然後查詢資料庫以取得有資格的應用程式清單。</span><span class="sxs-lookup"><span data-stu-id="8b435-545">The App-V Publishing Server uses the identity of the initiating target, user or machine, and queries the database for a list of entitled applications.</span></span> <span data-ttu-id="8b435-546">應用程式清單是以 XML 回應形式提供，用戶端使用它來傳送其他要求給伺服器，以取得每個套件的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="8b435-546">The list of applications is provided as an XML response, which the client uses to send additional requests to the server for more information on a per package basis.</span></span>

2.  <span data-ttu-id="8b435-547">App-V 用戶端上的發佈代理程式會執行序列化下列所有動作。</span><span class="sxs-lookup"><span data-stu-id="8b435-547">The Publishing Agent on the App-V Client performs all actions below serialized.</span></span>

    <span data-ttu-id="8b435-548">評估已取消發佈或停用的任何連線群組，因為無法處理屬於連線群組的套件版本更新。</span><span class="sxs-lookup"><span data-stu-id="8b435-548">Evaluate any connection groups that are unpublished or disabled, since package version updates that are part of the connection group cannot be processed.</span></span>

3.  <span data-ttu-id="8b435-549">透過識別新增或更新作業來設定套件。</span><span class="sxs-lookup"><span data-stu-id="8b435-549">Configure the packages by identifying an Add or Update operations.</span></span>

    1.  <span data-ttu-id="8b435-550">App-V 用戶端利用來自 Windows 的 AppX API，並從發佈伺服器存取 appv 檔案。</span><span class="sxs-lookup"><span data-stu-id="8b435-550">The App-V Client utilizes the AppX API from Windows and accesses the appv file from the publishing server.</span></span>

    2.  <span data-ttu-id="8b435-551">隨即會開啟套件檔案，並將 AppXManifest.xml 和 StreamMap.xml 下載到套件存放區。</span><span class="sxs-lookup"><span data-stu-id="8b435-551">The package file is opened and the AppXManifest.xml and StreamMap.xml are downloaded to the Package Store.</span></span>

    3.  <span data-ttu-id="8b435-552">完整的資料流程發佈區塊資料 StreamMap.xml 中定義。</span><span class="sxs-lookup"><span data-stu-id="8b435-552">Completely stream publishing block data defined in the StreamMap.xml.</span></span> <span data-ttu-id="8b435-553">在套件 Store\\PkgGUID\\VerGUID\\Root. 中儲存發佈區塊資料</span><span class="sxs-lookup"><span data-stu-id="8b435-553">Stores the publishing block data in the Package Store\\PkgGUID\\VerGUID\\Root.</span></span>

        -   <span data-ttu-id="8b435-554">圖示：延伸點的目標。</span><span class="sxs-lookup"><span data-stu-id="8b435-554">Icons: Targets of extension points.</span></span>

        -   <span data-ttu-id="8b435-555">可移植的可執行檔頭（PE 標題）：延伸點的目標，包含有關影像的基本資訊需要磁片上、直接存取或透過檔案類型。</span><span class="sxs-lookup"><span data-stu-id="8b435-555">Portable Executable Headers (PE Headers): Targets of extension points that contain the base information about the image need on disk, directly accessed or via file types.</span></span>

        -   <span data-ttu-id="8b435-556">腳本：下載要在整個發佈程式中使用的腳本目錄。</span><span class="sxs-lookup"><span data-stu-id="8b435-556">Scripts: Download scripts directory for use throughout the publishing process.</span></span>

    4.  <span data-ttu-id="8b435-557">填入套件存放區：</span><span class="sxs-lookup"><span data-stu-id="8b435-557">Populate the Package store:</span></span>

        1.  <span data-ttu-id="8b435-558">在磁片上建立可代表所列之任何目錄的提取套件的稀疏檔案。</span><span class="sxs-lookup"><span data-stu-id="8b435-558">Create sparse files on disk that represent the extracted package for any directories listed.</span></span>

        2.  <span data-ttu-id="8b435-559">將頂層檔案和目錄階段放在 root 之下。</span><span class="sxs-lookup"><span data-stu-id="8b435-559">Stage top level files and directories under root.</span></span>

        3.  <span data-ttu-id="8b435-560">當目錄在磁片上列為稀疏，且依需求傳送時，就會建立所有其他檔案。</span><span class="sxs-lookup"><span data-stu-id="8b435-560">All other files are created when the directory is listed as sparse on disk and streamed on demand.</span></span>

    5.  <span data-ttu-id="8b435-561">建立電腦目錄專案。</span><span class="sxs-lookup"><span data-stu-id="8b435-561">Create the machine catalog entries.</span></span> <span data-ttu-id="8b435-562">從套件檔案建立 Manifest.xml 和 DeploymentConfiguration.xml （如果沒有建立預留位置的套件中有 DeploymentConfiguration.xml 檔案）。</span><span class="sxs-lookup"><span data-stu-id="8b435-562">Create the Manifest.xml and DeploymentConfiguration.xml from the package files (if no DeploymentConfiguration.xml file in the package a placeholder is created).</span></span>

    6.  <span data-ttu-id="8b435-563">在註冊表 HKLM\\Software\\Microsoft\\AppV\\Client\\Packages\\PkgGUID\\Versions\\VerGUID\\Catalog 中建立套件存放區的位置</span><span class="sxs-lookup"><span data-stu-id="8b435-563">Create location of the package store in the registry HKLM\\Software\\Microsoft\\AppV\\Client\\Packages\\PkgGUID\\Versions\\VerGUID\\Catalog</span></span>

    7.  <span data-ttu-id="8b435-564">建立從套件存放區到%ProgramData%\\Microsoft\\AppV\\Client\\VReg\\ {VersionGUID} .dat 的 Registry .dat 檔案。</span><span class="sxs-lookup"><span data-stu-id="8b435-564">Create the Registry.dat file from the package store to %ProgramData%\\Microsoft\\AppV\\Client\\VReg\\{VersionGUID}.dat</span></span>

    8.  <span data-ttu-id="8b435-565">使用 App-v 核心模式驅動程式 HKLM\\Microsoft\\Software\\AppV\\MAV 註冊套件</span><span class="sxs-lookup"><span data-stu-id="8b435-565">Register the package with the App-V Kernel Mode Driver HKLM\\Microsoft\\Software\\AppV\\MAV</span></span>

    9.  <span data-ttu-id="8b435-566">從 [AppxManifest.xml] 或 [DeploymentConfig.xml 檔案] 中為套件 [新增時間] 調用腳本。</span><span class="sxs-lookup"><span data-stu-id="8b435-566">Invoke scripting from the AppxManifest.xml or DeploymentConfig.xml file for Package Add timing.</span></span>

4.  <span data-ttu-id="8b435-567">透過新增及啟用或停用來設定連線群組。</span><span class="sxs-lookup"><span data-stu-id="8b435-567">Configure Connection Groups by adding and enabling or disabling.</span></span>

5.  <span data-ttu-id="8b435-568">移除未發佈至目標（使用者或電腦）的物件。</span><span class="sxs-lookup"><span data-stu-id="8b435-568">Remove objects that are not published to the target (user or machine).</span></span>

    <span data-ttu-id="8b435-569">**記事** 這將不會執行套件刪除，而是移除特定目標（使用者或電腦）的整合點，並移除使用者目錄檔案（適用于全域發佈的電腦目錄檔案）。</span><span class="sxs-lookup"><span data-stu-id="8b435-569">**Note** This will not perform a package deletion but rather remove integration points for the specific target (user or machine) and remove user catalog files (machine catalog files for globally published).</span></span>

     

6.  <span data-ttu-id="8b435-570">根據用戶端設定來喚醒呼叫背景載入。</span><span class="sxs-lookup"><span data-stu-id="8b435-570">Invoke background load mounting based on client configuration.</span></span>

7.  <span data-ttu-id="8b435-571">已立即還原已擁有電腦或使用者之發佈資訊的套件。</span><span class="sxs-lookup"><span data-stu-id="8b435-571">Packages that already have publishing information for the machine or user are immediately restored.</span></span>

    <span data-ttu-id="8b435-572">**記事** 這種情況是在未以背景新增套件的情況下，在移除的產品中發生。</span><span class="sxs-lookup"><span data-stu-id="8b435-572">**Note** This condition occurs as a product of removal without unpublishing with background addition of the package.</span></span>

     

<span data-ttu-id="8b435-573">這樣就完成了發佈重新整理程式的新增-V 套件。</span><span class="sxs-lookup"><span data-stu-id="8b435-573">This completes an App-V package add of the publishing refresh process.</span></span> <span data-ttu-id="8b435-574">下一個步驟是將套件發佈到特定的目標（電腦或使用者）。</span><span class="sxs-lookup"><span data-stu-id="8b435-574">The next step is publishing the package to the specific target (machine or user).</span></span>

![封裝新增檔案和登錄資料](images/packageaddfileandregistrydata.png)

### <span data-ttu-id="8b435-576">發佈 App-v 套件</span><span class="sxs-lookup"><span data-stu-id="8b435-576">Publishing an App-V package</span></span>

<span data-ttu-id="8b435-577">在發佈重新整理作業期間，特定的發佈作業（發佈 AppVClientPackage）會將專案新增至使用者目錄、將權利對應給使用者、識別本地書店，以及完成任何整合步驟完成。</span><span class="sxs-lookup"><span data-stu-id="8b435-577">During the Publishing Refresh operation, the specific publishing operation (Publish-AppVClientPackage) adds entries to the user catalog, maps entitlement to the user, identifies the local store, and finishes by completing any integration steps.</span></span> <span data-ttu-id="8b435-578">以下是詳細步驟。</span><span class="sxs-lookup"><span data-stu-id="8b435-578">The following are the detailed steps.</span></span>

**<span data-ttu-id="8b435-579">如何發佈和 App-v 套件</span><span class="sxs-lookup"><span data-stu-id="8b435-579">How to publish and App-V package</span></span>**

1.  <span data-ttu-id="8b435-580">套件專案會新增至使用者目錄</span><span class="sxs-lookup"><span data-stu-id="8b435-580">Package entries are added to the user catalog</span></span>

    1.  <span data-ttu-id="8b435-581">使用者目標套件： UserDeploymentConfiguration.xml 和 UserManifest.xml 都放在電腦上的使用者目錄中</span><span class="sxs-lookup"><span data-stu-id="8b435-581">User targeted packages: the UserDeploymentConfiguration.xml and UserManifest.xml are placed on the machine in the User Catalog</span></span>

    2.  <span data-ttu-id="8b435-582">電腦目標（全域）套件： UserDeploymentConfiguration.xml 位於 [電腦目錄] 中</span><span class="sxs-lookup"><span data-stu-id="8b435-582">Machine targeted (global) packages: the UserDeploymentConfiguration.xml is placed in the Machine Catalog</span></span>

2.  <span data-ttu-id="8b435-583">在 HKLM\\Software\\Microsoft\\AppV\\MAV 上使用使用者的核心模式驅動程式註冊套件</span><span class="sxs-lookup"><span data-stu-id="8b435-583">Register the package with the kernel mode driver for the user at HKLM\\Software\\Microsoft\\AppV\\MAV</span></span>

3.  <span data-ttu-id="8b435-584">執行整合作業。</span><span class="sxs-lookup"><span data-stu-id="8b435-584">Perform integration tasks.</span></span>

    1.  <span data-ttu-id="8b435-585">建立延伸點。</span><span class="sxs-lookup"><span data-stu-id="8b435-585">Create extension points.</span></span>

    2.  <span data-ttu-id="8b435-586">將備份資訊儲存在使用者的 [登錄] 和 [漫遊] 設定檔（快捷方式備份）中。</span><span class="sxs-lookup"><span data-stu-id="8b435-586">Store backup information in the user’s registry and roaming profile (Shortcut Backups).</span></span>

        <span data-ttu-id="8b435-587">**記事** 這可讓您在未發佈套件的情況下，還原延伸點。</span><span class="sxs-lookup"><span data-stu-id="8b435-587">**Note** This enables restore extension points if the package is unpublished.</span></span>

         

    3.  <span data-ttu-id="8b435-588">針對發佈時間執行腳本。</span><span class="sxs-lookup"><span data-stu-id="8b435-588">Run scripts targeted for publishing timing.</span></span>

<span data-ttu-id="8b435-589">發佈屬於連線群組的 app-v 套件與上述程式非常類似。</span><span class="sxs-lookup"><span data-stu-id="8b435-589">Publishing an App-V Package that is part of a Connection Group is very similar to the above process.</span></span> <span data-ttu-id="8b435-590">針對 [連線群組]，儲存特定目錄資訊的路徑，包括 [PackageGroups] 作為目錄目錄的子項。</span><span class="sxs-lookup"><span data-stu-id="8b435-590">For connection groups, the path that stores the specific catalog information includes PackageGroups as a child of the Catalog Directory.</span></span> <span data-ttu-id="8b435-591">如需詳細資訊，請查看上述電腦和使用者目錄資訊。</span><span class="sxs-lookup"><span data-stu-id="8b435-591">Review the machine and users catalog information above for details.</span></span>

![封裝新增檔案和註冊表資料-全域](images/packageaddfileandregistrydata-global.png)

### <span data-ttu-id="8b435-593">應用程式啟動</span><span class="sxs-lookup"><span data-stu-id="8b435-593">Application launch</span></span>

<span data-ttu-id="8b435-594">發佈重新整理程式之後，使用者會啟動並重新啟動 App-v 應用程式。</span><span class="sxs-lookup"><span data-stu-id="8b435-594">After the Publishing Refresh process, the user launches and subsequently re-launches an App-V application.</span></span> <span data-ttu-id="8b435-595">這個程式非常簡單且經過優化，可使用最少的網路流量快速啟動。</span><span class="sxs-lookup"><span data-stu-id="8b435-595">The process is very simple and optimized to launch quickly with a minimum of network traffic.</span></span> <span data-ttu-id="8b435-596">App-v 用戶端會針對發佈期間建立的檔案，檢查使用者目錄的路徑。</span><span class="sxs-lookup"><span data-stu-id="8b435-596">The App-V Client checks the path to the user catalog for files created during publishing.</span></span> <span data-ttu-id="8b435-597">已建立啟動套件的許可權之後，應用程式 V 用戶端會建立虛擬環境、開始流式處理任何必要的資料，以及在虛擬環境建立期間套用適當的資訊清單和部署設定檔。</span><span class="sxs-lookup"><span data-stu-id="8b435-597">After rights to launch the package are established, the App-V Client creates a virtual environment, begins streaming any necessary data, and applies the appropriate manifest and deployment configuration files during virtual environment creation.</span></span> <span data-ttu-id="8b435-598">在針對特定套件和應用程式建立並設定虛擬環境的情況下，應用程式就會啟動。</span><span class="sxs-lookup"><span data-stu-id="8b435-598">With the virtual environment created and configured for the specific package and application, the application starts.</span></span>

**<span data-ttu-id="8b435-599">如何啟動 App-v 應用程式</span><span class="sxs-lookup"><span data-stu-id="8b435-599">How to launch App-V applications</span></span>**

1.  <span data-ttu-id="8b435-600">使用者透過按一下快捷方式或檔案類型的調用來啟動應用程式。</span><span class="sxs-lookup"><span data-stu-id="8b435-600">User launches the application by clicking on a shortcut or file type invocation.</span></span>

2.  <span data-ttu-id="8b435-601">App-v 用戶端會驗證以下檔案在使用者目錄中是否存在</span><span class="sxs-lookup"><span data-stu-id="8b435-601">The App-V Client verifies existence in the User Catalog for the following files</span></span>

    -   <span data-ttu-id="8b435-602">UserDeploymentConfiguration.xml</span><span class="sxs-lookup"><span data-stu-id="8b435-602">UserDeploymentConfiguration.xml</span></span>

    -   <span data-ttu-id="8b435-603">UserManifest.xml</span><span class="sxs-lookup"><span data-stu-id="8b435-603">UserManifest.xml</span></span>

3.  <span data-ttu-id="8b435-604">如果檔案存在，應用程式就擁有該特定使用者的資格，而應用程式將會啟動啟動程式。</span><span class="sxs-lookup"><span data-stu-id="8b435-604">If the files are present, the application is entitled for that specific user and the application will start the process for launch.</span></span> <span data-ttu-id="8b435-605">此時沒有任何網路流量。</span><span class="sxs-lookup"><span data-stu-id="8b435-605">There is no network traffic at this point.</span></span>

4.  <span data-ttu-id="8b435-606">接著，應用程式-V 用戶端會檢查在登錄中找到的為 App-v 用戶端服務註冊的套件路徑。</span><span class="sxs-lookup"><span data-stu-id="8b435-606">Next, the App-V Client checks that the path for the package registered for the App-V Client service is found in the registry.</span></span>

5.  <span data-ttu-id="8b435-607">尋找套件存放區的路徑後，就會建立虛擬環境。</span><span class="sxs-lookup"><span data-stu-id="8b435-607">Upon finding the path to the package store, the virtual environment is created.</span></span> <span data-ttu-id="8b435-608">如果這是第一次啟動，主要功能會封鎖下載（如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="8b435-608">If this is the first launch, the Primary Feature Block downloads if present.</span></span>

6.  <span data-ttu-id="8b435-609">下載之後，應用程式 V 用戶端服務會使用資訊清單和部署設定檔來設定虛擬環境，並載入所有 App-v 子系統。</span><span class="sxs-lookup"><span data-stu-id="8b435-609">After downloading, the App-V Client service consumes the manifest and deployment configuration files to configure the virtual environment and all App-V subsystems are loaded.</span></span>

7.  <span data-ttu-id="8b435-610">應用程式啟動。</span><span class="sxs-lookup"><span data-stu-id="8b435-610">The Application launches.</span></span> <span data-ttu-id="8b435-611">針對套件存放區（稀疏檔案）中任何遺失的檔案，App-v 會視需要將檔案錯誤地資料流。</span><span class="sxs-lookup"><span data-stu-id="8b435-611">For any missing files in the package store (sparse files), App-V will stream fault the files on an as needed basis.</span></span>

    ![封裝新增檔案和登錄資料-資料流程](images/packageaddfileandregistrydata-stream.png)

### <span data-ttu-id="8b435-613">升級 app-v 套件</span><span class="sxs-lookup"><span data-stu-id="8b435-613">Upgrading an App-V package</span></span>

<span data-ttu-id="8b435-614">App-v 5 套件升級程式與較舊版本的 App-v 不同。</span><span class="sxs-lookup"><span data-stu-id="8b435-614">The App-V 5 package upgrade process differs from the older versions of App-V.</span></span> <span data-ttu-id="8b435-615">App-v 支援針對不同使用者的電腦上的多個版本。</span><span class="sxs-lookup"><span data-stu-id="8b435-615">App-V supports multiple versions of the same package on a machine entitled to different users.</span></span> <span data-ttu-id="8b435-616">您可以隨時新增套件版本，因為套件存放區和目錄是以新的資源更新。</span><span class="sxs-lookup"><span data-stu-id="8b435-616">Package versions can be added at any time as the package store and catalogs are updated with the new resources.</span></span> <span data-ttu-id="8b435-617">加入新的版本資源所專用的唯一程式是儲存優化。</span><span class="sxs-lookup"><span data-stu-id="8b435-617">The only process specific to the addition of new version resources is storage optimization.</span></span> <span data-ttu-id="8b435-618">在升級期間，只會將新檔案新增至新的版本存放位置，並為未改動的檔案建立硬連結。</span><span class="sxs-lookup"><span data-stu-id="8b435-618">During an upgrade, only the new files are added to the new version store location and hard links are created for unchanged files.</span></span> <span data-ttu-id="8b435-619">這會減少整個儲存空間，只要將檔案呈現在一個磁片位置，然後使用磁片上的 [檔案位置] 專案將它投影到所有資料夾中。</span><span class="sxs-lookup"><span data-stu-id="8b435-619">This reduces the overall storage by only presenting the file on one disk location and then projecting it into all folders with a file location entry on the disk.</span></span> <span data-ttu-id="8b435-620">升級 App-v 套件的特定詳細資料如下所示：</span><span class="sxs-lookup"><span data-stu-id="8b435-620">The specific details of upgrading an App-V Package are as follows:</span></span>

**<span data-ttu-id="8b435-621">如何升級 app-v 套件</span><span class="sxs-lookup"><span data-stu-id="8b435-621">How to upgrade an App-V package</span></span>**

1.  <span data-ttu-id="8b435-622">應用程式-V 用戶端會執行發佈重新整理並探索較新的 app-v 套件版本。</span><span class="sxs-lookup"><span data-stu-id="8b435-622">The App-V Client performs a Publishing Refresh and discovers a newer version of an App-V Package.</span></span>

2.  <span data-ttu-id="8b435-623">套件專案會新增至新版本的適當目錄</span><span class="sxs-lookup"><span data-stu-id="8b435-623">Package entries are added to the appropriate catalog for the new version</span></span>

    1.  <span data-ttu-id="8b435-624">使用者目標套件： UserDeploymentConfiguration.xml 和 UserManifest.xml 會放在電腦上的使用者目錄中 appdata\\roaming\\Microsoft\\AppV\\Client\\Catalog\\Packages\\PkgGUID\\VerGUID</span><span class="sxs-lookup"><span data-stu-id="8b435-624">User targeted packages: the UserDeploymentConfiguration.xml and UserManifest.xml are placed on the machine in the user catalog at appdata\\roaming\\Microsoft\\AppV\\Client\\Catalog\\Packages\\PkgGUID\\VerGUID</span></span>

    2.  <span data-ttu-id="8b435-625">電腦目標（全域）套件： UserDeploymentConfiguration.xml 位於電腦目錄中的%programdata%\\Microsoft\\AppV\\Client\\Catalog\\Packages\\PkgGUID\\VerGUID</span><span class="sxs-lookup"><span data-stu-id="8b435-625">Machine targeted (global) packages: the UserDeploymentConfiguration.xml is placed in the machine catalog at %programdata%\\Microsoft\\AppV\\Client\\Catalog\\Packages\\PkgGUID\\VerGUID</span></span>

3.  <span data-ttu-id="8b435-626">在 HKLM\\Software\\Microsoft\\AppV\\MAV 上使用使用者的核心模式驅動程式註冊套件</span><span class="sxs-lookup"><span data-stu-id="8b435-626">Register the package with the kernel mode driver for the user at HKLM\\Software\\Microsoft\\AppV\\MAV</span></span>

4.  <span data-ttu-id="8b435-627">執行整合作業。</span><span class="sxs-lookup"><span data-stu-id="8b435-627">Perform integration tasks.</span></span>

    -   <span data-ttu-id="8b435-628">整合資訊清單和動態配置檔案的延伸點（EP）。</span><span class="sxs-lookup"><span data-stu-id="8b435-628">Integrate extensions points (EP) from the Manifest and Dynamic Configuration files.</span></span>

    1.  <span data-ttu-id="8b435-629">以檔案為基礎的 EP 資料會儲存在利用套件存放區中連接點的 AppData 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="8b435-629">File based EP data is stored in the AppData folder utilizing Junction Points from the package store.</span></span>

    2.  <span data-ttu-id="8b435-630">新版本推出時，版本 1 EPs 已存在。</span><span class="sxs-lookup"><span data-stu-id="8b435-630">Version 1 EPs already exist when a new version becomes available.</span></span>

    3.  <span data-ttu-id="8b435-631">針對任何更新或更新的延伸點，將延伸點切換至電腦或使用者目錄中的版本2位置。</span><span class="sxs-lookup"><span data-stu-id="8b435-631">The extension points are switched to the Version 2 location in machine or user catalogs for any newer or updated extension points.</span></span>

5.  <span data-ttu-id="8b435-632">針對發佈時間執行腳本。</span><span class="sxs-lookup"><span data-stu-id="8b435-632">Run scripts targeted for publishing timing.</span></span>

6.  <span data-ttu-id="8b435-633">根據需要安裝並排的元件。</span><span class="sxs-lookup"><span data-stu-id="8b435-633">Install Side by Side assemblies as required.</span></span>

### <span data-ttu-id="8b435-634">升級使用中的 app-v 套件</span><span class="sxs-lookup"><span data-stu-id="8b435-634">Upgrading an in-use App-V package</span></span>

<span data-ttu-id="8b435-635">**從 app-v 5 SP2 開始**：如果您嘗試升級的套件是由最終使用者所使用，則升級工作會放在擱置中的狀態。</span><span class="sxs-lookup"><span data-stu-id="8b435-635">**Starting in App-V 5 SP2**: If you try to upgrade a package that is in use by an end user, the upgrade task is placed in a pending state.</span></span> <span data-ttu-id="8b435-636">稍後會根據下列規則來執行升級：</span><span class="sxs-lookup"><span data-stu-id="8b435-636">The upgrade will run later, according to the following rules:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8b435-637">任務類型</span><span class="sxs-lookup"><span data-stu-id="8b435-637">Task type</span></span></th>
<th align="left"><span data-ttu-id="8b435-638">適用的規則</span><span class="sxs-lookup"><span data-stu-id="8b435-638">Applicable rule</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b435-639">以使用者為基礎的工作，例如，將套件發佈給使用者</span><span class="sxs-lookup"><span data-stu-id="8b435-639">User-based task, e.g., publishing a package to a user</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-640">暫停的工作將會在使用者登出後執行，然後重新登入。</span><span class="sxs-lookup"><span data-stu-id="8b435-640">The pending task will be performed after the user logs off and then logs back on.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8b435-641">以全域為基礎的工作，例如，全域啟用連接群組</span><span class="sxs-lookup"><span data-stu-id="8b435-641">Globally based task, e.g., enabling a connection group globally</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-642">當電腦關閉後再重新開機時，會執行待處理的工作。</span><span class="sxs-lookup"><span data-stu-id="8b435-642">The pending task will be performed when the computer is shut down and then restarted.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="8b435-643">當任務放在擱置狀態時，App-v 用戶端也會產生未決工作的登錄機碼，如下所示：</span><span class="sxs-lookup"><span data-stu-id="8b435-643">When a task is placed in a pending state, the App-V client also generates a registry key for the pending task, as follows:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8b435-644">以使用者為基礎或以全域為基礎的工作</span><span class="sxs-lookup"><span data-stu-id="8b435-644">User-based or globally based task</span></span></th>
<th align="left"><span data-ttu-id="8b435-645">登錄機碼的產生位置</span><span class="sxs-lookup"><span data-stu-id="8b435-645">Where the registry key is generated</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b435-646">以使用者為基礎的工作</span><span class="sxs-lookup"><span data-stu-id="8b435-646">User-based tasks</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-647">KEY_CURRENT_USER \Software\Microsoft\AppV\Client\PendingTasks</span><span class="sxs-lookup"><span data-stu-id="8b435-647">KEY_CURRENT_USER\Software\Microsoft\AppV\Client\PendingTasks</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8b435-648">全域基礎任務</span><span class="sxs-lookup"><span data-stu-id="8b435-648">Globally based tasks</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-649">HKEY_LOCAL_MACHINE \Software\Microsoft\AppV\Client\PendingTasks</span><span class="sxs-lookup"><span data-stu-id="8b435-649">HKEY_LOCAL_MACHINE\Software\Microsoft\AppV\Client\PendingTasks</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="8b435-650">必須先完成下列作業，使用者才能使用較新版本的套件：</span><span class="sxs-lookup"><span data-stu-id="8b435-650">The following operations must be completed before users can use the newer version of the package:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8b435-651">工作</span><span class="sxs-lookup"><span data-stu-id="8b435-651">Task</span></span></th>
<th align="left"><span data-ttu-id="8b435-652">詳細資料</span><span class="sxs-lookup"><span data-stu-id="8b435-652">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b435-653">將套件新增到電腦</span><span class="sxs-lookup"><span data-stu-id="8b435-653">Add the package to the computer</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-654">這項工作是特定于電腦的，您可以透過完成上方 [封裝] 新增區段中的步驟，隨時執行此工作。</span><span class="sxs-lookup"><span data-stu-id="8b435-654">This task is computer specific and you can perform it at any time by completing the steps in the Package Add section above.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8b435-655">發佈套件</span><span class="sxs-lookup"><span data-stu-id="8b435-655">Publish the package</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-656">如需步驟，請參閱上述套件發佈區段。</span><span class="sxs-lookup"><span data-stu-id="8b435-656">See the Package Publishing section above for steps.</span></span> <span data-ttu-id="8b435-657">這個程式要求您更新系統上的延伸點。</span><span class="sxs-lookup"><span data-stu-id="8b435-657">This process requires that you update extension points on the system.</span></span> <span data-ttu-id="8b435-658">當您完成此工作時，使用者就無法使用該應用程式。</span><span class="sxs-lookup"><span data-stu-id="8b435-658">End users cannot be using the application when you complete this task.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="8b435-659">使用下列範例案例作為更新套件的指南。</span><span class="sxs-lookup"><span data-stu-id="8b435-659">Use the following example scenarios as a guide for updating packages.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8b435-660">案例</span><span class="sxs-lookup"><span data-stu-id="8b435-660">Scenario</span></span></th>
<th align="left"><span data-ttu-id="8b435-661">需求</span><span class="sxs-lookup"><span data-stu-id="8b435-661">Requirements</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b435-662">嘗試升級時，未使用 app-v 套件</span><span class="sxs-lookup"><span data-stu-id="8b435-662">App-V package is not in use when you try to upgrade</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-663">套件的下列元件都無法使用：虛擬應用程式、COM 伺服器或命令介面延伸。</span><span class="sxs-lookup"><span data-stu-id="8b435-663">None of the following components of the package can be in use: virtual application, COM server, or shell extensions.</span></span></p>
<p><span data-ttu-id="8b435-664">系統管理員會發佈較新版本的套件，且下次啟動套件中的元件或應用程式時，升級就會生效。</span><span class="sxs-lookup"><span data-stu-id="8b435-664">The administrator publishes a newer version of the package and the upgrade works the next time a component or application inside the package is launched.</span></span> <span data-ttu-id="8b435-665">新版本的套件會進行流式處理並執行。</span><span class="sxs-lookup"><span data-stu-id="8b435-665">The new version of the package is streamed and run.</span></span> <span data-ttu-id="8b435-666">在此案例中，從舊版 App-V 5 發行的 app-v 5 SP2 中沒有任何變更。</span><span class="sxs-lookup"><span data-stu-id="8b435-666">Nothing has changed in this scenario in App-V 5 SP2 from previous releases of App-V 5.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8b435-667">當系統管理員發佈更新版本的套件時，會使用 app-v 套件</span><span class="sxs-lookup"><span data-stu-id="8b435-667">App-V package is in use when the administrator publishes a newer version of the package</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-668">升級作業是由 App-v 用戶端設定為擱置，這表示該操作已排入佇列，稍後在套件未使用時執行。</span><span class="sxs-lookup"><span data-stu-id="8b435-668">The upgrade operation is set to pending by the App-V Client, which means that it is queued and carried out later when the package is not in use.</span></span></p>
<p><span data-ttu-id="8b435-669">如果封裝應用程式在使用中，使用者會關閉虛擬應用程式，之後就可以進行升級。</span><span class="sxs-lookup"><span data-stu-id="8b435-669">If the package application is in use, the user shuts down the virtual application, after which the upgrade can occur.</span></span></p>
<p><span data-ttu-id="8b435-670">如果套件有 shell 擴充功能（Office 2013），而這些副檔名是由 Windows Explorer 永久載入，使用者就無法登入。</span><span class="sxs-lookup"><span data-stu-id="8b435-670">If the package has shell extensions (Office 2013), which are permanently loaded by Windows Explorer, the user cannot be logged in.</span></span> <span data-ttu-id="8b435-671">使用者必須登出，然後再重新登入，以啟動 App-v 套件升級。</span><span class="sxs-lookup"><span data-stu-id="8b435-671">Users must log off and the log back in to initiate the App-V package upgrade.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="8b435-672">全域與使用者發佈</span><span class="sxs-lookup"><span data-stu-id="8b435-672">Global vs user publishing</span></span>

<span data-ttu-id="8b435-673">您可以使用兩種方法的其中一種來發佈 app-v 套件;使用者在特定使用者或一組使用者和全域群組中擁有 App V 套件的不足，該使用者可以在整個電腦上為電腦的所有使用者提供 App-v （機器翻譯）。</span><span class="sxs-lookup"><span data-stu-id="8b435-673">App-V Packages can be published in one of two ways; User which entitles an App-V package to a specific user or group of users and Global which entitles the App-V package to the entire machine for all users of the machine.</span></span> <span data-ttu-id="8b435-674">一旦已暫停套件升級且未使用 App-v 套件，請考慮兩種發佈類型：</span><span class="sxs-lookup"><span data-stu-id="8b435-674">Once a package upgrade has been pended and the App-V package is not in use, consider the two types of publishing:</span></span>

-   <span data-ttu-id="8b435-675">已**全域發佈**：應用程式已發佈至電腦;該電腦上的所有使用者都可以使用它。</span><span class="sxs-lookup"><span data-stu-id="8b435-675">**Globally published**: the application is published to a machine; all users on that machine can use it.</span></span> <span data-ttu-id="8b435-676">當 App-v 用戶端服務啟動時，就會發生升級，這會有效地表示電腦重新開機。</span><span class="sxs-lookup"><span data-stu-id="8b435-676">The upgrade will happen when the App-V Client Service starts, which effectively means a machine restart.</span></span>

-   <span data-ttu-id="8b435-677">**使用者已發佈**：應用程式已發佈給使用者。</span><span class="sxs-lookup"><span data-stu-id="8b435-677">**User published**: the application is published to a user.</span></span> <span data-ttu-id="8b435-678">如果電腦上有多個使用者，應用程式可以發佈到使用者的子集。</span><span class="sxs-lookup"><span data-stu-id="8b435-678">If there are multiple users on the machine, the application can be published to a subset of the users.</span></span> <span data-ttu-id="8b435-679">當使用者登入或再次發佈時（定期、ConfigMgr 原則重新整理和評估，或由 PowerShell 命令顯式進行 App-v 發佈/重新整理），就會發生升級。</span><span class="sxs-lookup"><span data-stu-id="8b435-679">The upgrade will happen when the user logs in or when it is published again (periodically, ConfigMgr Policy refresh and evaluation, or an App-V periodic publishing/refresh, or explicitly via PowerShell commands).</span></span>

### <span data-ttu-id="8b435-680">移除 App-v 套件</span><span class="sxs-lookup"><span data-stu-id="8b435-680">Removing an App-V package</span></span>

<span data-ttu-id="8b435-681">在完整基礎結構中移除 App-v 應用程式是取消發佈操作，不會執行套件移除。</span><span class="sxs-lookup"><span data-stu-id="8b435-681">Removing App-V applications in a Full Infrastructure is an unpublish operation, and does not perform a package removal.</span></span> <span data-ttu-id="8b435-682">該程式與上述發佈程式相同，但不是新增移除程式，而是顛倒對 App-v 套件所做的變更。</span><span class="sxs-lookup"><span data-stu-id="8b435-682">The process is the same as the publish process above, but instead of adding the removal process reverses the changes that have been made for App-V Packages.</span></span>

### <span data-ttu-id="8b435-683">修復 App-v 套件</span><span class="sxs-lookup"><span data-stu-id="8b435-683">Repairing an App-V package</span></span>

<span data-ttu-id="8b435-684">修復操作非常簡單，但可能會影響電腦上的許多位置。</span><span class="sxs-lookup"><span data-stu-id="8b435-684">The repair operation is very simple but may affect many locations on the machine.</span></span> <span data-ttu-id="8b435-685">先前提到的 [寫入時複製（牛）] 位置已移除，而延伸點則是解除整合，然後再重新整合。</span><span class="sxs-lookup"><span data-stu-id="8b435-685">The previously mentioned Copy on Write (COW) locations are removed, and extension points are de-integrated and then re-integrated.</span></span> <span data-ttu-id="8b435-686">請透過查看在註冊表中登錄的位置，查看牛資料放置位置。</span><span class="sxs-lookup"><span data-stu-id="8b435-686">Please review the COW data placement locations by reviewing where they are registered in the registry.</span></span> <span data-ttu-id="8b435-687">這個作業會自動完成，而且除了從 App-v 用戶端主控台或透過 PowerShell 啟動修復作業以外，沒有任何管理控制權。</span><span class="sxs-lookup"><span data-stu-id="8b435-687">This operation is done automatically and there is no administrative control other than initiating a Repair operation from the App-V Client Console or via PowerShell (Repair-AppVClientPackage).</span></span>

## <a href="" id="bkmk-integr-appv-pkgs"></a><span data-ttu-id="8b435-688">集成 App-v 套件</span><span class="sxs-lookup"><span data-stu-id="8b435-688">Integration of App-V packages</span></span>


<span data-ttu-id="8b435-689">App-V 用戶端與套件架構可在新增套件和發佈套件期間，提供與本機作業系統的特定整合。</span><span class="sxs-lookup"><span data-stu-id="8b435-689">The App-V Client and package architecture provides specific integration with the local operating system during the addition and publishing of packages.</span></span> <span data-ttu-id="8b435-690">三個檔案可為 App-v 套件定義整合或延伸點：</span><span class="sxs-lookup"><span data-stu-id="8b435-690">Three files define the integration or extension points for an App-V Package:</span></span>

-   <span data-ttu-id="8b435-691">AppXManifest.xml：儲存在套件內，並將回退複本儲存在套件存放區和使用者設定檔中。</span><span class="sxs-lookup"><span data-stu-id="8b435-691">AppXManifest.xml: Stored inside of the package with fallback copies stored in the package store and the user profile.</span></span> <span data-ttu-id="8b435-692">包含在排序程式期間建立的選項。</span><span class="sxs-lookup"><span data-stu-id="8b435-692">Contains the options created during the sequencing process.</span></span>

-   <span data-ttu-id="8b435-693">DeploymentConfig.xml：提供電腦和使用者的整合延伸點的配置資訊。</span><span class="sxs-lookup"><span data-stu-id="8b435-693">DeploymentConfig.xml: Provides configuration information of computer and user based integration extension points.</span></span>

-   <span data-ttu-id="8b435-694">UserConfig.xml： Deploymentconfig.xml 的子集，只提供使用者專用的設定，且僅限以使用者為基礎的延伸點。</span><span class="sxs-lookup"><span data-stu-id="8b435-694">UserConfig.xml: A subset of the Deploymentconfig.xml that only provides user- based configurations and only targets user-based extension points.</span></span>

### <span data-ttu-id="8b435-695">整合規則</span><span class="sxs-lookup"><span data-stu-id="8b435-695">Rules of integration</span></span>

<span data-ttu-id="8b435-696">使用 App-v 用戶端將 App-v 應用程式發佈到電腦時，以下清單中所述就會發生一些特定動作：</span><span class="sxs-lookup"><span data-stu-id="8b435-696">When App-V applications are published to a computer with the App-V Client, some specific actions take place as described in the list below:</span></span>

-   <span data-ttu-id="8b435-697">全域發佈：快速鍵會儲存在 [所有使用者] 設定檔位置，而其他延伸點則會儲存在 HKLM hive 中的 [檔案] 中。</span><span class="sxs-lookup"><span data-stu-id="8b435-697">Global Publishing: Shortcuts are stored in the All Users profile location and other extension points are stored in the registry in the HKLM hive.</span></span>

-   <span data-ttu-id="8b435-698">使用者發佈：快速鍵會儲存在目前的使用者帳戶設定檔中，而其他延伸點則會儲存在 HKCU 配置儲存格中的登錄。</span><span class="sxs-lookup"><span data-stu-id="8b435-698">User Publishing: Shortcuts are stored in the current user account profile and other extension points are stored in the registry in the HKCU hive.</span></span>

-   <span data-ttu-id="8b435-699">備份與還原：現有的原生應用程式資料和註冊表（例如 FTA 註冊）是在發佈期間進行備份。</span><span class="sxs-lookup"><span data-stu-id="8b435-699">Backup and Restore: Existing native application data and registry (such as FTA registrations) are backed up during publishing.</span></span>

    1.  <span data-ttu-id="8b435-700">根據上一個整合式套件，將擁有權傳遞到最新發佈的 app-v 應用程式，以提供對 app-v 套件的擁有權。</span><span class="sxs-lookup"><span data-stu-id="8b435-700">App-V packages are given ownership based on the last integrated package where the ownership is passed to the newest published App-V application.</span></span>

    2.  <span data-ttu-id="8b435-701">未發佈擁有的 app-v 套件時，擁有權從一個 App-v 套件轉移到另一個應用程式。</span><span class="sxs-lookup"><span data-stu-id="8b435-701">Ownership transfers from one App-V package to another when the owning App-V package is unpublished.</span></span> <span data-ttu-id="8b435-702">這不會啟動資料或註冊表的還原。</span><span class="sxs-lookup"><span data-stu-id="8b435-702">This will not initiate a restore of the data or registry.</span></span>

    3.  <span data-ttu-id="8b435-703">在針對每個延伸點取消發佈或移除最後一個套件時，還原已備份的資料。</span><span class="sxs-lookup"><span data-stu-id="8b435-703">Restore the backed up data when the last package is unpublished or removed on a per extension point basis.</span></span>

### <span data-ttu-id="8b435-704">延伸點</span><span class="sxs-lookup"><span data-stu-id="8b435-704">Extension points</span></span>

<span data-ttu-id="8b435-705">App-v 發佈檔案（資訊清單和動態配置）提供數個延伸點，讓應用程式能夠與本機作業系統整合。</span><span class="sxs-lookup"><span data-stu-id="8b435-705">The App-V publishing files (manifest and dynamic configuration) provide several extension points that enable the application to integrate with the local operating system.</span></span> <span data-ttu-id="8b435-706">這些延伸點會執行一般的應用程式安裝工作，例如放置快速鍵、建立檔案類型關聯，以及註冊元件。</span><span class="sxs-lookup"><span data-stu-id="8b435-706">These extension points perform typical application installation tasks, such as placing shortcuts, creating file type associations, and registering components.</span></span> <span data-ttu-id="8b435-707">因為這些程式是與傳統應用程式不同的方式來安裝的虛擬化應用程式，所以有一些差異。</span><span class="sxs-lookup"><span data-stu-id="8b435-707">As these are virtualized applications that are not installed in the same manner a traditional application, there are some differences.</span></span> <span data-ttu-id="8b435-708">以下是本節所涵蓋延伸點的清單：</span><span class="sxs-lookup"><span data-stu-id="8b435-708">The following is a list of extension points covered in this section:</span></span>

-   <span data-ttu-id="8b435-709">方式</span><span class="sxs-lookup"><span data-stu-id="8b435-709">Shortcuts</span></span>

-   <span data-ttu-id="8b435-710">檔案類型關聯</span><span class="sxs-lookup"><span data-stu-id="8b435-710">File Type Associations</span></span>

-   <span data-ttu-id="8b435-711">命令介面延伸</span><span class="sxs-lookup"><span data-stu-id="8b435-711">Shell Extensions</span></span>

-   <span data-ttu-id="8b435-712">COM</span><span class="sxs-lookup"><span data-stu-id="8b435-712">COM</span></span>

-   <span data-ttu-id="8b435-713">軟體用戶端</span><span class="sxs-lookup"><span data-stu-id="8b435-713">Software Clients</span></span>

-   <span data-ttu-id="8b435-714">應用程式功能</span><span class="sxs-lookup"><span data-stu-id="8b435-714">Application capabilities</span></span>

-   <span data-ttu-id="8b435-715">URL 通訊協定處理常式</span><span class="sxs-lookup"><span data-stu-id="8b435-715">URL Protocol Handler</span></span>

-   <span data-ttu-id="8b435-716">AppPath</span><span class="sxs-lookup"><span data-stu-id="8b435-716">AppPath</span></span>

-   <span data-ttu-id="8b435-717">虛擬應用程式</span><span class="sxs-lookup"><span data-stu-id="8b435-717">Virtual Application</span></span>

### <span data-ttu-id="8b435-718">方式</span><span class="sxs-lookup"><span data-stu-id="8b435-718">Shortcuts</span></span>

<span data-ttu-id="8b435-719">[簡短剪下] 是與作業系統整合的其中一個基本元素，也就是 [直接使用者啟動] App-v 應用程式的介面。</span><span class="sxs-lookup"><span data-stu-id="8b435-719">The short cut is one of the basic elements of integration with the OS and is the interface for direct user launch of an App-V application.</span></span> <span data-ttu-id="8b435-720">在發佈和取消發佈 App-v 應用程式期間。</span><span class="sxs-lookup"><span data-stu-id="8b435-720">During the publishing and unpublishing of App-V applications.</span></span>

<span data-ttu-id="8b435-721">從封裝資訊清單和動態配置 XML 檔案，您可以在類似下列的章節中找到特定應用程式可執行檔的路徑：</span><span class="sxs-lookup"><span data-stu-id="8b435-721">From the package manifest and dynamic configuration XML files, the path to a specific application executable can be found in a section similar to the following:</span></span>

```xml
<Extension Category="AppV.Shortcut">
          <Shortcut>
            <File>[{Common Desktop}]\Adobe Reader 9.lnk</File>
            <Target>[{AppVPackageRoot}]\Reader\AcroRd32.exe</Target>
            <Icon>[{Windows}]\Installer\{AC76BA86-7AD7-1033-7B44-A94000000001}\SC_Reader.ico</Icon>
            <Arguments />
            <WorkingDirectory />
            <ShowCommand>1</ShowCommand>
            <ApplicationId>[{AppVPackageRoot}]\Reader\AcroRd32.exe</ApplicationId>
          </Shortcut>
        </Extension>
```

<span data-ttu-id="8b435-722">如先前所述，在使用者的設定檔中根據重新整理的操作，預設會放置 App-v 快速鍵。</span><span class="sxs-lookup"><span data-stu-id="8b435-722">As mentioned previously, the App-V shortcuts are placed by default in the user’s profile based on the refresh operation.</span></span> <span data-ttu-id="8b435-723">全域重新整理會將 [所有使用者] 設定檔中的快速鍵放在一起，而 [使用者重新整理] 會將它們儲存在特定使用者</span><span class="sxs-lookup"><span data-stu-id="8b435-723">Global refresh places shortcuts in the All Users profile and user refresh stores them in the specific user’s profile.</span></span> <span data-ttu-id="8b435-724">實際的可執行檔會儲存在套件存放區中。</span><span class="sxs-lookup"><span data-stu-id="8b435-724">The actual executable is stored in the Package Store.</span></span> <span data-ttu-id="8b435-725">.ICO 檔案的位置是 App-v 封裝中的標記位置。</span><span class="sxs-lookup"><span data-stu-id="8b435-725">The location of the ICO file is a tokenized location in the App-V package.</span></span>

### <span data-ttu-id="8b435-726">檔案類型關聯</span><span class="sxs-lookup"><span data-stu-id="8b435-726">File type associations</span></span>

<span data-ttu-id="8b435-727">App-V 用戶端會在發佈期間管理本機作業系統的檔案類型關聯，這可讓使用者使用檔案類型調用，或使用特殊註冊副檔名（.docx）來開啟檔案，以啟動 App-v 應用程式。</span><span class="sxs-lookup"><span data-stu-id="8b435-727">The App-V Client manages the local operating system File Type Associations during publishing, which enables users to use file type invocations or to open a file with a specifically registered extension (.docx) to start an App-V application.</span></span> <span data-ttu-id="8b435-728">檔案類型關聯在資訊清單和動態配置檔案中存在，如下列範例所示：</span><span class="sxs-lookup"><span data-stu-id="8b435-728">File type associations are present in the manifest and dynamic configuration files as represented in the example below:</span></span>

```xml
<Extension Category="AppV.FileTypeAssociation">
          <FileTypeAssociation>
            <FileExtension MimeAssociation="true">
              <Name>.xdp</Name>
              <ProgId>AcroExch.XDPDoc</ProgId>
              <ContentType>application/vnd.adobe.xdp+xml</ContentType>
            </FileExtension>
            <ProgId>
              <Name>AcroExch.XDPDoc</Name>
              <Description>Adobe Acrobat XML Data Package File</Description>
              <EditFlags>65536</EditFlags>
              <DefaultIcon>[{Windows}]\Installer\{AC76BA86-7AD7-1033-7B44-A94000000001}\XDPFile_8.ico</DefaultIcon>
              <ShellCommands>
                <DefaultCommand>Read</DefaultCommand>
                <ShellCommand>
                  <ApplicationId>[{AppVPackageRoot}]\Reader\AcroRd32.exe</ApplicationId>
                  <Name>Open</Name>
                  <CommandLine>"[{AppVPackageRoot}]\Reader\AcroRd32.exe" "%1"</CommandLine>
                </ShellCommand>
                <ShellCommand>
                  <ApplicationId>[{AppVPackageRoot}]\Reader\AcroRd32.exe</ApplicationId>
                  <Name>Printto</Name>
                  <CommandLine>"[{AppVPackageRoot}]\Reader\AcroRd32.exe"  /t "%1" "%2" "%3" "%4"</CommandLine>
                </ShellCommand>
                <ShellCommand>
                  <ApplicationId>[{AppVPackageRoot}]\Reader\AcroRd32.exe</ApplicationId>
                  <Name>Read</Name>
                  <FriendlyName>Open with Adobe Reader 9</FriendlyName>
                  <CommandLine>"[{AppVPackageRoot}]\Reader\AcroRd32.exe" "%1"</CommandLine>
                </ShellCommand>
              </ShellCommands>
            </ProgId>
          </FileTypeAssociation>
        </Extension>
```

<span data-ttu-id="8b435-729">**記事** 在這個範例中：</span><span class="sxs-lookup"><span data-stu-id="8b435-729">**Note** In this example:</span></span>

-   `<Name>.xdp</Name>` <span data-ttu-id="8b435-730">是延伸</span><span class="sxs-lookup"><span data-stu-id="8b435-730">is the extension</span></span>

-   `<Name>AcroExch.XDPDoc</Name>` <span data-ttu-id="8b435-731">是 ProgId 值（指向連續的 ProgId）</span><span class="sxs-lookup"><span data-stu-id="8b435-731">is the ProgId value (which points to the adjoining ProgId)</span></span>

-   `<CommandLine>"[{AppVPackageRoot}]\Reader\AcroRd32.exe" "%1"</CommandLine>` <span data-ttu-id="8b435-732">是指向應用程式可執行檔的命令列</span><span class="sxs-lookup"><span data-stu-id="8b435-732">is the command line, which points to the application executable</span></span>

 

### <span data-ttu-id="8b435-733">殼層延伸</span><span class="sxs-lookup"><span data-stu-id="8b435-733">Shell extensions</span></span>

<span data-ttu-id="8b435-734">在排序過程中，會自動將 Shell 延伸內嵌在套件中。</span><span class="sxs-lookup"><span data-stu-id="8b435-734">Shell extensions are embedded in the package automatically during the sequencing process.</span></span> <span data-ttu-id="8b435-735">當套件是全域發行時，shell 延伸會提供與應用程式在本機安裝時相同的功能。</span><span class="sxs-lookup"><span data-stu-id="8b435-735">When the package is published globally, the shell extension gives users the same functionality as if the application were locally installed.</span></span> <span data-ttu-id="8b435-736">應用程式在用戶端上不需要任何額外的設定或配置，就能啟用 shell 擴充功能。</span><span class="sxs-lookup"><span data-stu-id="8b435-736">The application requires no additional setup or configuration on the client to enable the shell extension functionality.</span></span>

**<span data-ttu-id="8b435-737">使用命令介面延伸的需求：</span><span class="sxs-lookup"><span data-stu-id="8b435-737">Requirements for using shell extensions:</span></span>**

-   <span data-ttu-id="8b435-738">包含內嵌命令介面延伸的套件必須全域發佈。</span><span class="sxs-lookup"><span data-stu-id="8b435-738">Packages that contain embedded shell extensions must be published globally.</span></span>

-   <span data-ttu-id="8b435-739">應用程式、Sequencer 和 App-v 用戶端的 "位數" 必須相符，否則 shell 延伸將無法運作。</span><span class="sxs-lookup"><span data-stu-id="8b435-739">The “bitness” of the application, Sequencer, and App-V client must match, or the shell extensions won’t work.</span></span> <span data-ttu-id="8b435-740">例如：</span><span class="sxs-lookup"><span data-stu-id="8b435-740">For example:</span></span>

    -   <span data-ttu-id="8b435-741">應用程式的版本為64位。</span><span class="sxs-lookup"><span data-stu-id="8b435-741">The version of the application is 64-bit.</span></span>

    -   <span data-ttu-id="8b435-742">排序器正在64位電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="8b435-742">The Sequencer is running on a 64-bit computer.</span></span>

    -   <span data-ttu-id="8b435-743">套件正在傳送至64位的 App-v 用戶端電腦。</span><span class="sxs-lookup"><span data-stu-id="8b435-743">The package is being delivered to a 64-bit App-V client computer.</span></span>

<span data-ttu-id="8b435-744">下表顯示支援的命令介面延伸。</span><span class="sxs-lookup"><span data-stu-id="8b435-744">The following table displays the supported shell extensions.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8b435-745">處理</span><span class="sxs-lookup"><span data-stu-id="8b435-745">Handler</span></span></th>
<th align="left"><span data-ttu-id="8b435-746">說明</span><span class="sxs-lookup"><span data-stu-id="8b435-746">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b435-747">操作功能表處理常式</span><span class="sxs-lookup"><span data-stu-id="8b435-747">Context menu handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-748">將功能表項目新增至操作功能表。</span><span class="sxs-lookup"><span data-stu-id="8b435-748">Adds menu items to the context menu.</span></span> <span data-ttu-id="8b435-749">在顯示操作功能表前呼叫該內容。</span><span class="sxs-lookup"><span data-stu-id="8b435-749">It is called before the context menu is displayed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8b435-750">拖放處理常式</span><span class="sxs-lookup"><span data-stu-id="8b435-750">Drag-and-drop handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-751">在按住滑鼠右鍵按一下並修改所出現的操作功能表時，控制動作。</span><span class="sxs-lookup"><span data-stu-id="8b435-751">Controls the action upon right-click drag-and-drop and modifies the context menu that appears.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b435-752">拖放目標處理常式</span><span class="sxs-lookup"><span data-stu-id="8b435-752">Drop target handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-753">控制將資料物件拖曳至拖放目標（例如檔案）之後的動作。</span><span class="sxs-lookup"><span data-stu-id="8b435-753">Controls the action after a data object is dragged-and-dropped over a drop target such as a file.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8b435-754">資料物件處理常式</span><span class="sxs-lookup"><span data-stu-id="8b435-754">Data object handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-755">控制將檔案複製到 [剪貼簿] 或拖放至拖放目標之後的動作。</span><span class="sxs-lookup"><span data-stu-id="8b435-755">Controls the action after a file is copied to the clipboard or dragged-and-dropped over a drop target.</span></span> <span data-ttu-id="8b435-756">它可以提供其他剪貼簿格式至拖放目標。</span><span class="sxs-lookup"><span data-stu-id="8b435-756">It can provide additional clipboard formats to the drop target.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b435-757">屬性工作表處理常式</span><span class="sxs-lookup"><span data-stu-id="8b435-757">Property sheet handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-758">取代或新增頁面至物件的 [屬性工作表] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="8b435-758">Replaces or adds pages to the property sheet dialog box of an object.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8b435-759">提示處理常式</span><span class="sxs-lookup"><span data-stu-id="8b435-759">Infotip handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-760">允許您在滑鼠懸停時，為專案檢索標誌和資訊提示資訊，並在彈出工具提示中顯示。</span><span class="sxs-lookup"><span data-stu-id="8b435-760">Allows retrieving flags and infotip information for an item and displaying it inside a popup tooltip upon mouse- hover.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b435-761">欄處理常式</span><span class="sxs-lookup"><span data-stu-id="8b435-761">Column handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-762">可讓您在 Windows 資源管理器的詳細資料檢視中建立和顯示自訂欄 <em> </em> 。</span><span class="sxs-lookup"><span data-stu-id="8b435-762">Allows creating and displaying custom columns in Windows Explorer <em>Details view</em>.</span></span> <span data-ttu-id="8b435-763">它可以用來延伸排序與分組。</span><span class="sxs-lookup"><span data-stu-id="8b435-763">It can be used to extend sorting and grouping.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8b435-764">預覽處理常式</span><span class="sxs-lookup"><span data-stu-id="8b435-764">Preview handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-765">啟用要在 Windows 資源管理器預覽窗格中顯示的檔案預覽。</span><span class="sxs-lookup"><span data-stu-id="8b435-765">Enables a preview of a file to be displayed in the Windows Explorer Preview Pane.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="8b435-766">COM</span><span class="sxs-lookup"><span data-stu-id="8b435-766">COM</span></span>

<span data-ttu-id="8b435-767">App-V 用戶端支援支援 COM 整合與虛擬化的發佈應用程式。</span><span class="sxs-lookup"><span data-stu-id="8b435-767">The App-V Client supports publishing applications with support for COM integration and virtualization.</span></span> <span data-ttu-id="8b435-768">COM 整合可讓 App-v 用戶端在本機作業系統上註冊 COM 物件，以及物件的虛擬化。</span><span class="sxs-lookup"><span data-stu-id="8b435-768">COM integration allows the App-V Client to register COM objects on the local operating system and virtualization of the objects.</span></span> <span data-ttu-id="8b435-769">針對這份檔而言，COM 物件的整合需要額外的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="8b435-769">For the purposes of this document, the integration of COM objects requires additional detail.</span></span>

<span data-ttu-id="8b435-770">App-v 支援使用兩個處理常式類型，將 COM 物件從套件註冊到本機作業系統：不在處理常式中。</span><span class="sxs-lookup"><span data-stu-id="8b435-770">App-V supports registering COM objects from the package to the local operating system with two process types: Out-of-process and in-process.</span></span> <span data-ttu-id="8b435-771">註冊 COM 物件是使用一種或多種不同的應用程式-V 套件（包括關閉、隔離及整合）的方式來完成。</span><span class="sxs-lookup"><span data-stu-id="8b435-771">Registering COM objects is accomplished with one or a combination of multiple modes of operation for a specific App-V package that includes off, Isolated, and Integrated.</span></span> <span data-ttu-id="8b435-772">整合模式是針對進程外或進程內類型進行設定。</span><span class="sxs-lookup"><span data-stu-id="8b435-772">The integrated mode is configured for either the out-of-process or in-process type.</span></span> <span data-ttu-id="8b435-773">COM 模式與類型的設定是使用動態配置檔案（deploymentconfig.xml 或 userconfig.xml）來完成。</span><span class="sxs-lookup"><span data-stu-id="8b435-773">Configuration of COM modes and types is accomplished with dynamic configuration files (deploymentconfig.xml or userconfig.xml).</span></span>

<span data-ttu-id="8b435-774">您可以在以下網址取得 App V 整合的詳細資料： <https://go.microsoft.com/fwlink/?LinkId=392834> 。</span><span class="sxs-lookup"><span data-stu-id="8b435-774">Details on App-V integration are available at: <https://go.microsoft.com/fwlink/?LinkId=392834>.</span></span>

### <span data-ttu-id="8b435-775">軟體用戶端和應用程式功能</span><span class="sxs-lookup"><span data-stu-id="8b435-775">Software clients and application capabilities</span></span>

<span data-ttu-id="8b435-776">App-v 支援特定軟體用戶端和應用程式功能延伸點，可讓虛擬化的應用程式在作業系統的軟體用戶端註冊。</span><span class="sxs-lookup"><span data-stu-id="8b435-776">App-V supports specific software clients and application capabilities extension points that enable virtualized applications to be registered with the software client of the operating system.</span></span> <span data-ttu-id="8b435-777">這可讓使用者選取 [電子郵件]、[立即訊息] 和 [媒體播放機] 等作業的預設程式。</span><span class="sxs-lookup"><span data-stu-id="8b435-777">This enables users to select default programs for operations like email, instant messaging, and media player.</span></span> <span data-ttu-id="8b435-778">這個作業是在 [控制台] 中使用 [設定程式存取及電腦預設值] 執行，並在資訊清單或動態設定檔案的排序期間進行設定。</span><span class="sxs-lookup"><span data-stu-id="8b435-778">This operation is performed in the control panel with the Set Program Access and Computer Defaults, and configured during sequencing in the manifest or dynamic configuration files.</span></span> <span data-ttu-id="8b435-779">只有在全域發佈 App-v 應用程式時，才支援應用程式功能。</span><span class="sxs-lookup"><span data-stu-id="8b435-779">Application capabilities are only supported when the App-V applications are published globally.</span></span>

<span data-ttu-id="8b435-780">應用程式-以 V 為基礎的郵件用戶端註冊的軟體用戶端範例。</span><span class="sxs-lookup"><span data-stu-id="8b435-780">Example of software client registration of an App-V based mail client.</span></span>

```xml
    <SoftwareClients Enabled="true">
      <ClientConfiguration EmailEnabled="true" />
      <Extensions>
        <Extension Category="AppV.SoftwareClient">
          <SoftwareClients>
            <EMail MakeDefault="true">
              <Name>Mozilla Thunderbird</Name>
              <Description>Mozilla Thunderbird</Description>
              <DefaultIcon>[{ProgramFilesX86}]\Mozilla Thunderbird\thunderbird.exe,0</DefaultIcon>
              <InstallationInformation>
                <RegistrationCommands>
                  <Reinstall>"[{ProgramFilesX86}]\Mozilla Thunderbird\uninstall\helper.exe" /SetAsDefaultAppGlobal</Reinstall>
                  <HideIcons>"[{ProgramFilesX86}]\Mozilla Thunderbird\uninstall\helper.exe" /HideShortcuts</HideIcons>
                  <ShowIcons>"[{ProgramFilesX86}]\Mozilla Thunderbird\uninstall\helper.exe" /ShowShortcuts</ShowIcons>
                </RegistrationCommands>
                <IconsVisible>1</IconsVisible>
                <OEMSettings />
              </InstallationInformation>
              <ShellCommands>
                <ApplicationId>[{ProgramFilesX86}]\Mozilla Thunderbird\thunderbird.exe</ApplicationId>
                <Open>"[{ProgramFilesX86}]\Mozilla Thunderbird\thunderbird.exe" -mail</Open>
              </ShellCommands>
              <MAPILibrary>[{ProgramFilesX86}]\Mozilla Thunderbird\mozMapi32_InUse.dll</MAPILibrary>
              <MailToProtocol>
                <Description>Thunderbird URL</Description>
                <EditFlags>2</EditFlags>
                <DefaultIcon>[{ProgramFilesX86}]\Mozilla Thunderbird\thunderbird.exe,0</DefaultIcon>
                <ShellCommands>
                  <ApplicationId>[{ProgramFilesX86}]\Mozilla Thunderbird\thunderbird.exe</ApplicationId>
                  <Open>"[{ProgramFilesX86}]\Mozilla Thunderbird\thunderbird.exe" -osint -compose "%1"</Open>
                </ShellCommands>
              </MailToProtocol>
            </EMail>
          </SoftwareClients>
        </Extension>
      </Extensions>
    </SoftwareClients>
```

<span data-ttu-id="8b435-781">**記事** 在這個範例中：</span><span class="sxs-lookup"><span data-stu-id="8b435-781">**Note** In this example:</span></span>

-   `<ClientConfiguration EmailEnabled="true" />` <span data-ttu-id="8b435-782">是整合電子郵件用戶端的整體軟體用戶端設定</span><span class="sxs-lookup"><span data-stu-id="8b435-782">is the overall Software Clients setting to integrate Email clients</span></span>

-   `<EMail MakeDefault="true">` <span data-ttu-id="8b435-783">是將特定電子郵件客戶程式設定為預設電子郵件用戶端的標誌</span><span class="sxs-lookup"><span data-stu-id="8b435-783">is the flag to set a particular Email client as the default Email client</span></span>

-   `<MAPILibrary>[{ProgramFilesX86}]\Mozilla Thunderbird\mozMapi32_InUse.dll</MAPILibrary>` <span data-ttu-id="8b435-784">是 MAPI dll 註冊</span><span class="sxs-lookup"><span data-stu-id="8b435-784">is the MAPI dll registration</span></span>

 

### <span data-ttu-id="8b435-785">URL 通訊協定處理常式</span><span class="sxs-lookup"><span data-stu-id="8b435-785">URL Protocol handler</span></span>

<span data-ttu-id="8b435-786">應用程式不一定是使用檔案類型呼叫的虛擬化應用程式。</span><span class="sxs-lookup"><span data-stu-id="8b435-786">Applications do not always specifically called virtualized applications utilizing file type invocation.</span></span> <span data-ttu-id="8b435-787">舉例來說，在支援內嵌 mailto：的應用程式中，在檔或網頁內，使用者按一下 mailto：連結，並預期會取得他們已登錄的郵件用戶端。</span><span class="sxs-lookup"><span data-stu-id="8b435-787">For, example, in an application that supports embedding a mailto: link inside a document or web page, the user clicks on a mailto: link and expects to get their registered mail client.</span></span> <span data-ttu-id="8b435-788">App-v 支援 URL 協定處理常式，可以使用本機作業系統針對每個套件進行註冊。</span><span class="sxs-lookup"><span data-stu-id="8b435-788">App-V supports URL Protocol handlers that can be registered on a per-package basis with the local operating system.</span></span> <span data-ttu-id="8b435-789">在排序期間，URL 通訊協定處理常式會自動新增到套件中。</span><span class="sxs-lookup"><span data-stu-id="8b435-789">During sequencing, the URL protocol handlers are automatically added to the package.</span></span>

<span data-ttu-id="8b435-790">如果您有多個應用程式可以登錄特定的 URL 通訊協定處理常式，則可以利用動態配置檔案來修改行為，並針對不應啟動主要應用程式的應用程式，隱含或停用此功能。</span><span class="sxs-lookup"><span data-stu-id="8b435-790">For situations where there is more than one application that could register the specific URL Protocol handler, the dynamic configuration files can be utilized to modify the behavior and suppress or disable this feature for an application that should not be the primary application launched.</span></span>

### <span data-ttu-id="8b435-791">AppPath</span><span class="sxs-lookup"><span data-stu-id="8b435-791">AppPath</span></span>

<span data-ttu-id="8b435-792">AppPath 延伸點支援直接從作業系統呼叫 App V 應用程式。</span><span class="sxs-lookup"><span data-stu-id="8b435-792">The AppPath extension point supports calling App-V applications directly from the operating system.</span></span> <span data-ttu-id="8b435-793">這通常是從 Run 或 Start 畫面完成，視作業系統而定，這可讓系統管理員提供來自作業系統命令或腳本的 App-v 應用程式存取權，而不需呼叫可執行檔的特定路徑。</span><span class="sxs-lookup"><span data-stu-id="8b435-793">This is typically accomplished from the Run or Start Screen, depending on the operating system, which enables administrators to provide access to App-V applications from operating system commands or scripts without calling the specific path to the executable.</span></span> <span data-ttu-id="8b435-794">因此，它可以避免在所有系統中修改系統 path 環境變數，就像在發佈期間完成。</span><span class="sxs-lookup"><span data-stu-id="8b435-794">It therefore avoids modifying the system path environment variable on all systems, as it is accomplished during publishing.</span></span>

<span data-ttu-id="8b435-795">AppPath 延伸點是在資訊清單或動態配置檔案中設定，而且會儲存在本機電腦上的登錄中，以供使用者發佈時使用。</span><span class="sxs-lookup"><span data-stu-id="8b435-795">The AppPath extension point is configured either in the manifest or in the dynamic configuration files and is stored in the registry on the local machine during publishing for the user.</span></span> <span data-ttu-id="8b435-796">如需 AppPath 評論的其他資訊： <https://go.microsoft.com/fwlink/?LinkId=392835> 。</span><span class="sxs-lookup"><span data-stu-id="8b435-796">For additional information on AppPath review: <https://go.microsoft.com/fwlink/?LinkId=392835>.</span></span>

### <span data-ttu-id="8b435-797">虛擬應用程式</span><span class="sxs-lookup"><span data-stu-id="8b435-797">Virtual application</span></span>

<span data-ttu-id="8b435-798">此子系統提供在排序期間所捕獲的應用程式清單，這些應用程式通常是由其他 App-v 元件所使用。</span><span class="sxs-lookup"><span data-stu-id="8b435-798">This subsystem provides a list of applications captured during sequencing which is usually consumed by other App-V components.</span></span> <span data-ttu-id="8b435-799">您可以使用動態設定檔來停用屬於特定應用程式的延伸點整合。</span><span class="sxs-lookup"><span data-stu-id="8b435-799">Integration of extension points belonging to a particular application can be disabled using dynamic configuration files.</span></span> <span data-ttu-id="8b435-800">例如，如果套件包含兩個應用程式，則可以停用所有屬於某個應用程式的延伸點，以便只整合其他應用程式的延伸點。</span><span class="sxs-lookup"><span data-stu-id="8b435-800">For example, if a package contains two applications, it is possible to disable all extension points belonging to one application, in order to allow only integration of extension points of other application.</span></span>

### <span data-ttu-id="8b435-801">延伸點規則</span><span class="sxs-lookup"><span data-stu-id="8b435-801">Extension point rules</span></span>

<span data-ttu-id="8b435-802">上述延伸點會根據套件發佈的方式，融入作業系統。</span><span class="sxs-lookup"><span data-stu-id="8b435-802">The extension points described above are integrated into the operating system based on how the packages has been published.</span></span> <span data-ttu-id="8b435-803">[全域發佈] 會將延伸點放在公用電腦位置，使用者發佈會將延伸點放在使用者位置。</span><span class="sxs-lookup"><span data-stu-id="8b435-803">Global publishing places extension points in public machine locations, where user publishing places extension points in user locations.</span></span> <span data-ttu-id="8b435-804">例如，在桌面上建立並全域發佈的快捷方式，會產生快捷方式（%Public%\\Desktop）和登錄資料（HKLM\\Software\\Classes）的檔案資料。</span><span class="sxs-lookup"><span data-stu-id="8b435-804">For example a shortcut that is created on the desktop and published globally will result in the file data for the shortcut (%Public%\\Desktop) and the registry data (HKLM\\Software\\Classes).</span></span> <span data-ttu-id="8b435-805">相同的快捷方式就是檔案資料（%UserProfile%\\Desktop）和登錄資料（HKCU\\Software\\Classes）。</span><span class="sxs-lookup"><span data-stu-id="8b435-805">The same shortcut would have file data (%UserProfile%\\Desktop) and registry data (HKCU\\Software\\Classes).</span></span>

<span data-ttu-id="8b435-806">延伸點不會以相同的方式發佈，因為某些延伸點會需要全域發佈，而其他延伸點則需要在其提供的特定作業系統和架構上進行排序。</span><span class="sxs-lookup"><span data-stu-id="8b435-806">Extension points are not all published the same way, where some extension points will require global publishing and others require sequencing on the specific operating system and architecture where they are delivered.</span></span> <span data-ttu-id="8b435-807">以下是描述這兩個主要規則的表格。</span><span class="sxs-lookup"><span data-stu-id="8b435-807">Below is a table that describes these two key rules.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="8b435-808">虛擬延伸</span><span class="sxs-lookup"><span data-stu-id="8b435-808">Virtual Extension</span></span></th>
<th align="left"><span data-ttu-id="8b435-809">需要目標 OS 順序</span><span class="sxs-lookup"><span data-stu-id="8b435-809">Requires target OS Sequencing</span></span></th>
<th align="left"><span data-ttu-id="8b435-810">需要全域發佈</span><span class="sxs-lookup"><span data-stu-id="8b435-810">Requires Global Publishing</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b435-811">快捷</span><span class="sxs-lookup"><span data-stu-id="8b435-811">Shortcut</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8b435-812">檔案類型關聯</span><span class="sxs-lookup"><span data-stu-id="8b435-812">File Type Association</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b435-813">URL 協定</span><span class="sxs-lookup"><span data-stu-id="8b435-813">URL Protocols</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-814">X</span><span class="sxs-lookup"><span data-stu-id="8b435-814">X</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8b435-815">AppPaths</span><span class="sxs-lookup"><span data-stu-id="8b435-815">AppPaths</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-816">X</span><span class="sxs-lookup"><span data-stu-id="8b435-816">X</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b435-817">COM 模式</span><span class="sxs-lookup"><span data-stu-id="8b435-817">COM Mode</span></span></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8b435-818">軟體用戶端</span><span class="sxs-lookup"><span data-stu-id="8b435-818">Software Client</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-819">X</span><span class="sxs-lookup"><span data-stu-id="8b435-819">X</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b435-820">應用程式功能</span><span class="sxs-lookup"><span data-stu-id="8b435-820">Application Capabilities</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-821">X</span><span class="sxs-lookup"><span data-stu-id="8b435-821">X</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-822">X</span><span class="sxs-lookup"><span data-stu-id="8b435-822">X</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8b435-823">操作功能表處理常式</span><span class="sxs-lookup"><span data-stu-id="8b435-823">Context Menu Handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-824">X</span><span class="sxs-lookup"><span data-stu-id="8b435-824">X</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-825">X</span><span class="sxs-lookup"><span data-stu-id="8b435-825">X</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b435-826">拖放處理常式</span><span class="sxs-lookup"><span data-stu-id="8b435-826">Drag-and-drop Handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-827">X</span><span class="sxs-lookup"><span data-stu-id="8b435-827">X</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8b435-828">資料物件處理常式</span><span class="sxs-lookup"><span data-stu-id="8b435-828">Data Object Handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-829">X</span><span class="sxs-lookup"><span data-stu-id="8b435-829">X</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b435-830">屬性工作表處理常式</span><span class="sxs-lookup"><span data-stu-id="8b435-830">Property Sheet Handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-831">X</span><span class="sxs-lookup"><span data-stu-id="8b435-831">X</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8b435-832">提示處理常式</span><span class="sxs-lookup"><span data-stu-id="8b435-832">Infotip Handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-833">X</span><span class="sxs-lookup"><span data-stu-id="8b435-833">X</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b435-834">欄處理常式</span><span class="sxs-lookup"><span data-stu-id="8b435-834">Column Handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-835">X</span><span class="sxs-lookup"><span data-stu-id="8b435-835">X</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8b435-836">命令介面延伸</span><span class="sxs-lookup"><span data-stu-id="8b435-836">Shell Extensions</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-837">X</span><span class="sxs-lookup"><span data-stu-id="8b435-837">X</span></span></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="8b435-838">瀏覽器小幫手物件</span><span class="sxs-lookup"><span data-stu-id="8b435-838">Browser Helper Object</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-839">X</span><span class="sxs-lookup"><span data-stu-id="8b435-839">X</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-840">X</span><span class="sxs-lookup"><span data-stu-id="8b435-840">X</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="8b435-841">Active X 物件</span><span class="sxs-lookup"><span data-stu-id="8b435-841">Active X Object</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-842">X</span><span class="sxs-lookup"><span data-stu-id="8b435-842">X</span></span></p></td>
<td align="left"><p><span data-ttu-id="8b435-843">X</span><span class="sxs-lookup"><span data-stu-id="8b435-843">X</span></span></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-dynamic-config"></a><span data-ttu-id="8b435-844">動態配置處理</span><span class="sxs-lookup"><span data-stu-id="8b435-844">Dynamic configuration processing</span></span>


<span data-ttu-id="8b435-845">將 App-v 套件部署到一個電腦或使用者非常簡單。</span><span class="sxs-lookup"><span data-stu-id="8b435-845">Deploying App-V packages to one machine or user is very simple.</span></span> <span data-ttu-id="8b435-846">不過，隨著組織跨商業線與地理與政治界限部署 AppV 應用程式，只需一次將應用程式排序，就無法使用一組設定。</span><span class="sxs-lookup"><span data-stu-id="8b435-846">However, as organizations deploy AppV applications across business lines and geographic and political boundaries, the ability to sequence an application one time with one set of settings becomes impossible.</span></span> <span data-ttu-id="8b435-847">App-v 是針對此案例設計的，因為它會在資訊清單檔案中的排序期間捕獲特定設定和設定，但也支援使用動態設定檔進行修改。</span><span class="sxs-lookup"><span data-stu-id="8b435-847">App-V was designed for this scenario, as it captures specific settings and configurations during sequencing in the Manifest file, but also supports modification with Dynamic Configuration files.</span></span>

<span data-ttu-id="8b435-848">App-v 動態配置可讓您在電腦層級或使用者層級指定套件的原則。</span><span class="sxs-lookup"><span data-stu-id="8b435-848">App-V dynamic configuration allows for specifying a policy for a package either at the machine level or at the user level.</span></span> <span data-ttu-id="8b435-849">動態設定檔可讓排序工程師修改套件的設定、後續排序，以解決個別使用者群組或電腦的需求。</span><span class="sxs-lookup"><span data-stu-id="8b435-849">The Dynamic Configuration files enable sequencing engineers to modify the configuration of a package, post-sequencing, to address the needs of individual groups of users or machines.</span></span> <span data-ttu-id="8b435-850">在某些情況下，可能需要對應用程式進行修改，才能在 App-v 環境中提供適當的功能。</span><span class="sxs-lookup"><span data-stu-id="8b435-850">In some instances it may be necessary to make modifications to the application to provide proper functionality within the App-V environment.</span></span> <span data-ttu-id="8b435-851">例如，您可能需要對 \ _ \ \* config.xml 檔案進行修改，以便在應用程式執行期間，在指定的時間執行特定動作，例如停用 mailto 延伸，以避免虛擬化的應用程式覆寫其他應用程式的副檔名。</span><span class="sxs-lookup"><span data-stu-id="8b435-851">For example, it may be necessary to make modifications to the \_\*config.xml files to allow certain actions to be performed at a specified time during the execution of the application, like disabling a mailto extension to prevent a virtualized application from overwriting that extension from another application.</span></span>

<span data-ttu-id="8b435-852">App-v 套件包含在 appv 封裝檔案內的資訊清單檔案，它代表排序運算，而且是選擇原則，除非將動態設定檔指派給特定套件。</span><span class="sxs-lookup"><span data-stu-id="8b435-852">App-V Packages contain the Manifest file inside of the appv package file, which is representative of sequencing operations and is the policy of choice unless Dynamic Configuration files are assigned to a specific package.</span></span> <span data-ttu-id="8b435-853">排序後，可以修改動態配置檔案，以允許將應用程式發佈到不同的桌面或具有不同延伸點的使用者。</span><span class="sxs-lookup"><span data-stu-id="8b435-853">Post-sequencing, the Dynamic Configuration files can be modified to allow the publishing of an application to different desktops or users with different extension points.</span></span> <span data-ttu-id="8b435-854">這兩個動態配置檔案是動態部署配置（DDC）和動態使用者設定（DUC）檔案。</span><span class="sxs-lookup"><span data-stu-id="8b435-854">The two Dynamic Configuration Files are the Dynamic Deployment Configuration (DDC) and Dynamic User Configuration (DUC) files.</span></span> <span data-ttu-id="8b435-855">本節將重點放在資訊清單和動態設定檔案的組合中。</span><span class="sxs-lookup"><span data-stu-id="8b435-855">This section focuses on the combination of the manifest and dynamic configuration files.</span></span>

### <span data-ttu-id="8b435-856">動態設定檔範例</span><span class="sxs-lookup"><span data-stu-id="8b435-856">Example for dynamic configuration files</span></span>

<span data-ttu-id="8b435-857">下列範例顯示發佈之後及正常運作期間，資訊清單、部署配置和使用者設定檔的組合。</span><span class="sxs-lookup"><span data-stu-id="8b435-857">The example below shows the combination of the Manifest, Deployment Configuration and User Configuration files after publishing and during normal operation.</span></span> <span data-ttu-id="8b435-858">這些範例是每個檔案的縮寫範例。</span><span class="sxs-lookup"><span data-stu-id="8b435-858">These examples are abbreviated examples of each of the files.</span></span> <span data-ttu-id="8b435-859">用途只會顯示檔案的組合，而不是在每個檔案中所提供的特定類別的完整說明。</span><span class="sxs-lookup"><span data-stu-id="8b435-859">The purpose is show the combination of the files only and not to be a complete description of the specific categories available in each of the files.</span></span> <span data-ttu-id="8b435-860">如需詳細資訊，請參閱 App-V 5 排序指南，網址為：</span><span class="sxs-lookup"><span data-stu-id="8b435-860">For more information review the App-V 5 Sequencing Guide at:</span></span> <https://go.microsoft.com/fwlink/?LinkID=269810>

**<span data-ttu-id="8b435-861">Manifest</span><span class="sxs-lookup"><span data-stu-id="8b435-861">Manifest</span></span>**

```xml
<appv:Extension Category="AppV.Shortcut">
     <appv:Shortcut>
          <appv:File>[{Common Programs}]\7-Zip\7-Zip File Manager.lnk</appv:File>
          <appv:Target>[{AppVPackageRoot}]\7zFM.exe</appv:Target>
          <appv:Icon>[{AppVPackageRoot}]\7zFM exe.O.ico</appv:Icon>
     </appv:Shortcut>
</appv:Extension>
```

**<span data-ttu-id="8b435-862">部署設定</span><span class="sxs-lookup"><span data-stu-id="8b435-862">Deployment Configuration</span></span>**

```xml
<MachineConfiguration>
     <Subsystems>
          <Registry>
               <Include>
                    <Key Path= "\REGISTRY\Machine\Software\7zip">
                    <Value Type="REG_SZ" Name="Config" Data="1234"/>
                    </Key>
               </Include>
          </Registry>
     </Subsystems>
```

**<span data-ttu-id="8b435-863">使用者設定</span><span class="sxs-lookup"><span data-stu-id="8b435-863">User Configuration</span></span>**

```xml
<UserConfiguration>
     <Subsystems>
<appv:ExtensionCategory="AppV.Shortcut">
     <appv:Shortcut>
          <appv:File>[{Desktop}]\7-Zip\7-Zip File Manager.lnk</appv:File>
          <appv:Target>[{AppVPackageRoot}]\7zFM.exe</appv:Target>
          <appv:Icon>[{AppVPackageRoot}]\7zFM exe.O.ico</appv:Icon>
     </appv:Shortcut>
</appv:Extension>
     </Subsystems>
<UserConfiguration>
     <Subsystems>
<appv:Extension Category="AppV.Shortcut">
     <appv:Shortcut>
          <appv:Fìle>[{Desktop}]\7-Zip\7-Zip File Manager.lnk</appv:File>
          <appv:Target>[{AppVPackageRoot}]\7zFM.exe</appv:Target>
          <appv:Icon>[{AppVPackageRoot}]\7zFM.exe.O.ico</appv:Icon>
     </appv:Shortcut>
     <appv:Shortcut>
          <appv:File>[{Common Programs}]\7-Zip\7-Zip File Manager.Ink</appv:File>
          <appv:Target>[{AppVPackageRoot}]\7zFM.exe</appv:Target>
          <appv:Icon>[{AppVPackageRoot)]\7zFM.exe.O.ico</appv: Icon>
     </appv:Shortcut>
</appv:Extension>
     </Subsystems>
<MachineConfiguration>
     <Subsystems>
          <Registry>
               <Include>
                    <Key Path="\REGISTRY\Machine\Software\7zip">
                    <Value Type=”REG_SZ" Name="Config" Data="1234"/>
               </Include>
          </Registry>
     </Subsystems>
```

## <a href="" id="bkmk-sidebyside-assemblies"></a><span data-ttu-id="8b435-864">並列元件</span><span class="sxs-lookup"><span data-stu-id="8b435-864">Side-by-side assemblies</span></span>


<span data-ttu-id="8b435-865">App-v 支援在虛擬應用程式發佈期間，在用戶端排序和部署期間自動封裝並行（SxS）元件。</span><span class="sxs-lookup"><span data-stu-id="8b435-865">App-V supports the automatic packaging of side-by-side (SxS) assemblies during sequencing and deployment on the client during virtual application publishing.</span></span> <span data-ttu-id="8b435-866">在順序電腦上不存在的元件排序期間，app-v 5 SP2 支援捕獲 SxS 元件。</span><span class="sxs-lookup"><span data-stu-id="8b435-866">App-V 5 SP2 supports capturing SxS assemblies during sequencing for assemblies not present on the sequencing machine.</span></span> <span data-ttu-id="8b435-867">而且對於由 Visual c + + （版本8及更新版本）和/或 MSXML 執行時間組成的元件，Sequencer 會自動偵測並捕獲這些相依性，即使在監視期間未安裝這些相依性也一樣。</span><span class="sxs-lookup"><span data-stu-id="8b435-867">And for assemblies consisting of Visual C++ (Version 8 and newer) and/or MSXML run-time, the Sequencer will automatically detect and capture these dependencies even if they were not installed during monitoring.</span></span> <span data-ttu-id="8b435-868">[並列元件] 功能會移除舊版 App-v 的限制，其中 App-v 排序器並未捕獲排序工作站上已存在的元件，並 privatizing 每個套件的每位版本限制的元件。</span><span class="sxs-lookup"><span data-stu-id="8b435-868">The Side by Side assemblies feature removes the limitations of previous versions of App-V, where the App-V Sequencer did not capture assemblies already present on the sequencing workstation, and privatizing the assemblies which limited to one bit version per package.</span></span> <span data-ttu-id="8b435-869">此行為會導致已將 App-v 應用程式部署到用戶端缺少必要的 SxS 元件，從而導致應用程式啟動失敗。</span><span class="sxs-lookup"><span data-stu-id="8b435-869">This behavior resulted in deployed App-V applications to clients missing the required SxS assemblies, causing application launch failures.</span></span> <span data-ttu-id="8b435-870">這會強制進行封裝程式，然後確保套件所需的所有元件都已在本機安裝在使用者的用戶端作業系統上，以確保支援虛擬應用程式。</span><span class="sxs-lookup"><span data-stu-id="8b435-870">This forced the packaging process to document and then ensure that all assemblies required for packages were locally installed on the user’s client operating system to ensure support for the virtual applications.</span></span> <span data-ttu-id="8b435-871">根據元件的數目和缺少所需相依性的應用程式檔，這項工作既是管理又是實現挑戰。</span><span class="sxs-lookup"><span data-stu-id="8b435-871">Based on the number of assemblies and the lack of application documentation for the required dependencies, this task was both a management and implementation challenge.</span></span>

<span data-ttu-id="8b435-872">App-v 中的並行元件支援具有下列功能。</span><span class="sxs-lookup"><span data-stu-id="8b435-872">Side by Side Assembly support in App-V has the following features.</span></span>

-   <span data-ttu-id="8b435-873">在排序期間自動捕獲 SxS 元件，不論該元件是否已安裝在先後順序工作站上。</span><span class="sxs-lookup"><span data-stu-id="8b435-873">Automatic captures of SxS assembly during Sequencing, regardless of whether the assembly was already installed on the sequencing workstation.</span></span>

-   <span data-ttu-id="8b435-874">App-v 用戶端會在發佈期間，自動將必要的 SxS 元件安裝至用戶端電腦（如果它們不存在）。</span><span class="sxs-lookup"><span data-stu-id="8b435-874">The App-V Client automatically installs required SxS assemblies to the client computer at publishing time when they are not present.</span></span>

-   <span data-ttu-id="8b435-875">Sequencer 會在 Sequencer 報告機制中報告 VC 執行時間相依性。</span><span class="sxs-lookup"><span data-stu-id="8b435-875">The Sequencer reports the VC run-time dependency in Sequencer reporting mechanism.</span></span>

-   <span data-ttu-id="8b435-876">排序器可讓您選擇不封裝已安裝在 Sequencer 上的元件，以支援先前已在目的電腦上安裝元件的情況。</span><span class="sxs-lookup"><span data-stu-id="8b435-876">The Sequencer allows opting to not package the assemblies that are already installed on the Sequencer, supporting scenarios where the assemblies have previously been installed on the target computers.</span></span>

### <span data-ttu-id="8b435-877">自動發佈 SxS 元件</span><span class="sxs-lookup"><span data-stu-id="8b435-877">Automatic publishing of SxS assemblies</span></span>

<span data-ttu-id="8b435-878">在使用 SxS 元件發佈 app-v 套件期間，App-v 用戶端會檢查電腦上是否存在該元件。</span><span class="sxs-lookup"><span data-stu-id="8b435-878">During publishing of an App-V package with SxS assemblies the App-V Client will check for the presence of the assembly on the machine.</span></span> <span data-ttu-id="8b435-879">如果元件不存在，用戶端會將元件部署到電腦。</span><span class="sxs-lookup"><span data-stu-id="8b435-879">If the assembly does not exist, the client will deploy the assembly to the machine.</span></span> <span data-ttu-id="8b435-880">屬於連線群組的套件會依賴並行元件安裝（基本套件的一部分），因為連線群組不包含元件安裝的任何相關資訊。</span><span class="sxs-lookup"><span data-stu-id="8b435-880">Packages that are part of connection groups will rely on the Side by Side assembly installations that are part of the base packages, as the connection group does not contain any information about assembly installation.</span></span>

<span data-ttu-id="8b435-881">**記事** 在元件中取消發佈或移除套件時，並不會移除該套件的元件。</span><span class="sxs-lookup"><span data-stu-id="8b435-881">**Note** UnPublishing or removing a package with an assembly does not remove the assemblies for that package.</span></span>

 

## <a href="" id="bkmk-client-logging"></a><span data-ttu-id="8b435-882">用戶端記錄</span><span class="sxs-lookup"><span data-stu-id="8b435-882">Client logging</span></span>


<span data-ttu-id="8b435-883">App-v 用戶端會將資訊以標準 ETW 格式記錄到 Windows 事件記錄。</span><span class="sxs-lookup"><span data-stu-id="8b435-883">The App-V client logs information to the Windows Event log in standard ETW format.</span></span> <span data-ttu-id="8b435-884">您可以在事件檢視器中的 [應用程式和服務 Logs\\Microsoft\\AppV\\Client.] 底下找到特定的 App-v 事件</span><span class="sxs-lookup"><span data-stu-id="8b435-884">The specific App-V events can be found in the event viewer, under Applications and Services Logs\\Microsoft\\AppV\\Client.</span></span>

<span data-ttu-id="8b435-885">**記事** 在 App-v 5.0 SP3 中，部分記錄已整合並移到下列位置：</span><span class="sxs-lookup"><span data-stu-id="8b435-885">**Note** In App-V 5.0 SP3, some logs were consolidated and moved to the following location:</span></span>

`Event logs/Applications and Services Logs/Microsoft/AppV/ServiceLog`

<span data-ttu-id="8b435-886">如需已移動之記錄的清單，請參閱[關於 App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-event-logs-moved)。</span><span class="sxs-lookup"><span data-stu-id="8b435-886">For a list of the moved logs, see [About App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-event-logs-moved).</span></span>

 

<span data-ttu-id="8b435-887">以下所記錄的事件有三種特定類別。</span><span class="sxs-lookup"><span data-stu-id="8b435-887">There are three specific categories of events recorded described below.</span></span>

<span data-ttu-id="8b435-888">系統**管理員**：記錄應用到 App-v 用戶端之設定的事件，並包含主要警告和錯誤。</span><span class="sxs-lookup"><span data-stu-id="8b435-888">**Admin**: Logs events for configurations being applied to the App-V Client, and contains the primary warnings and errors.</span></span>

<span data-ttu-id="8b435-889">[作業 **]：記錄**個別元件的一般 App V 執行與使用方式，建立已在 App-v 用戶端上完成之 app-v 作業的審核記錄。</span><span class="sxs-lookup"><span data-stu-id="8b435-889">**Operational**: Logs the general App-V execution and usage of individual components creating an audit log of the App-V operations that have been completed on the App-V Client.</span></span>

<span data-ttu-id="8b435-890">**虛擬應用程式**：記錄虛擬應用程式啟動和使用虛擬化子系統的功能。</span><span class="sxs-lookup"><span data-stu-id="8b435-890">**Virtual Application**: Logs virtual application launches and use of virtualization subsystems.</span></span>






 

 





