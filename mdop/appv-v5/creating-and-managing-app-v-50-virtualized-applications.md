---
title: 建立和管理 App-V 5.0 虛擬化應用程式
description: 建立和管理 App-V 5.0 虛擬化應用程式
author: dansimp
ms.assetid: 66bab403-d7e0-4e7b-bc8f-a29a98a7160a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 86332c7753b70abbaaf289fc1ba046bf59d1dd89
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800659"
---
# <span data-ttu-id="18ec7-103">建立和管理 App-V 5.0 虛擬化應用程式</span><span class="sxs-lookup"><span data-stu-id="18ec7-103">Creating and Managing App-V 5.0 Virtualized Applications</span></span>


<span data-ttu-id="18ec7-104">在您正確部署 Microsoft Application Virtualization （App-v） 5.0 sequencer 之後，您可以使用它來監視及記錄應用程式作為虛擬化應用程式執行的安裝與設定程式。</span><span class="sxs-lookup"><span data-stu-id="18ec7-104">After you have properly deployed the Microsoft Application Virtualization (App-V) 5.0 sequencer, you can use it to monitor and record the installation and setup process for an application to be run as a virtualized application.</span></span>

<span data-ttu-id="18ec7-105">**記事** 如需有關設定 Microsoft Application Virtualization （App-v） 5.0 sequencer、排序最佳做法，以及建立和更新虛擬應用程式的範例的詳細資訊，請參閱[Microsoft Application virtualization 5.0 排序指南](https://download.microsoft.com/download/F/7/8/F784A197-73BE-48FF-83DA-4102C05A6D44/App-V 5.0 Sequencing Guide.docx)（ https://download.microsoft.com/download/F/7/8/F784A197-73BE-48FF-83DA-4102C05A6D44/App-V 5.0 排序 Guide.docx）。</span><span class="sxs-lookup"><span data-stu-id="18ec7-105">**Note** For more information about configuring the Microsoft Application Virtualization (App-V) 5.0 sequencer, sequencing best practices, and an example of creating and updating a virtual application, see the [Microsoft Application Virtualization 5.0 Sequencing Guide](https://download.microsoft.com/download/F/7/8/F784A197-73BE-48FF-83DA-4102C05A6D44/App-V 5.0 Sequencing Guide.docx) (https://download.microsoft.com/download/F/7/8/F784A197-73BE-48FF-83DA-4102C05A6D44/App-V 5.0 Sequencing Guide.docx).</span></span>

 

## <span data-ttu-id="18ec7-106">為應用程式排序</span><span class="sxs-lookup"><span data-stu-id="18ec7-106">Sequencing an application</span></span>


<span data-ttu-id="18ec7-107">您可以使用 App-v 5.0 Sequencer 來執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="18ec7-107">You can use the App-V 5.0 Sequencer to perform the following tasks:</span></span>

-   <span data-ttu-id="18ec7-108">建立可部署到執行 App-v 5.0 用戶端之電腦的虛擬套件。</span><span class="sxs-lookup"><span data-stu-id="18ec7-108">Create virtual packages that can be deployed to computers running the App-V 5.0 client.</span></span>

-   <span data-ttu-id="18ec7-109">升級現有的套件。</span><span class="sxs-lookup"><span data-stu-id="18ec7-109">Upgrade existing packages.</span></span> <span data-ttu-id="18ec7-110">您可以將現有的套件展開到執行排序器的電腦上，然後升級應用程式以建立較新的版本。</span><span class="sxs-lookup"><span data-stu-id="18ec7-110">You can expand an existing package onto the computer running the sequencer and then upgrade the application to create a newer version.</span></span>

-   <span data-ttu-id="18ec7-111">編輯與現有套件相關聯的配置資訊。</span><span class="sxs-lookup"><span data-stu-id="18ec7-111">Edit configuration information associated with an existing package.</span></span> <span data-ttu-id="18ec7-112">例如，您可以新增快捷方式或修改檔案類型關聯。</span><span class="sxs-lookup"><span data-stu-id="18ec7-112">For example, you can add a shortcut or modify a file type association.</span></span>

    <span data-ttu-id="18ec7-113">**記事** 您必須建立快速鍵，並將其儲存到可用的網路位置，才能允許漫遊。</span><span class="sxs-lookup"><span data-stu-id="18ec7-113">**Note** You must create shortcuts and save them to an available network location to allow roaming.</span></span> <span data-ttu-id="18ec7-114">如果在私人位置建立並儲存快捷方式，套件必須在本機發佈至執行 App-v 5.0 用戶端的電腦上。</span><span class="sxs-lookup"><span data-stu-id="18ec7-114">If a shortcut is created and saved in a private location, the package must be published locally to the computer running the App-V 5.0 client.</span></span>

     

-   <span data-ttu-id="18ec7-115">[轉換現有的虛擬套件]。</span><span class="sxs-lookup"><span data-stu-id="18ec7-115">Convert existing virtual packages.</span></span>

<span data-ttu-id="18ec7-116">排序器使用 **% TMP% \ [暫存**] 或 **% TEMP% \\ 暫存**目錄，而**temp**目錄則是在排序期間儲存臨時檔案。</span><span class="sxs-lookup"><span data-stu-id="18ec7-116">The sequencer uses the **%TMP% \\ Scratch** or **%TEMP% \\ Scratch** directory and the **Temp** directory to store temporary files during sequencing.</span></span> <span data-ttu-id="18ec7-117">在執行排序器的電腦上，您應該使用相當於估計應用程式安裝需求的可用磁碟空間來設定這些目錄。</span><span class="sxs-lookup"><span data-stu-id="18ec7-117">On the computer that runs the sequencer, you should configure these directories with free disk space equivalent to the estimated application installation requirements.</span></span> <span data-ttu-id="18ec7-118">在不同的硬碟分區上設定 temp 目錄和 Temp 目錄，可以在排序期間改善效能。</span><span class="sxs-lookup"><span data-stu-id="18ec7-118">Configuring the temp directories and the Temp directory on different hard drive partitions can help improve performance during sequencing.</span></span>

<span data-ttu-id="18ec7-119">當您使用排序器建立新的虛擬應用程式時，會建立下列列出的檔案。</span><span class="sxs-lookup"><span data-stu-id="18ec7-119">When you use the sequencer to create a new virtual application, the following listed files are created.</span></span> <span data-ttu-id="18ec7-120">這些檔案是由 App-v 5.0 套件組成。</span><span class="sxs-lookup"><span data-stu-id="18ec7-120">These files comprise the App-V 5.0 package.</span></span>

-   <span data-ttu-id="18ec7-121">.msi 檔案。</span><span class="sxs-lookup"><span data-stu-id="18ec7-121">.msi file.</span></span> <span data-ttu-id="18ec7-122">此 Windows Installer （.msi）檔案是由排序器所建立，並用於在目的電腦上安裝虛擬套件。</span><span class="sxs-lookup"><span data-stu-id="18ec7-122">This Windows Installer (.msi) file is created by the sequencer and is used to install the virtual package on target computers.</span></span>

-   <span data-ttu-id="18ec7-123">Report.xml 檔案]。</span><span class="sxs-lookup"><span data-stu-id="18ec7-123">Report.xml file.</span></span> <span data-ttu-id="18ec7-124">在此檔案中，sequencer 會儲存在排序期間發現的所有問題、警告及錯誤。</span><span class="sxs-lookup"><span data-stu-id="18ec7-124">In this file, the sequencer saves all issues, warnings, and errors that were discovered during sequencing.</span></span> <span data-ttu-id="18ec7-125">建立套件後，就會顯示資訊。</span><span class="sxs-lookup"><span data-stu-id="18ec7-125">It displays the information after the package has been created.</span></span> <span data-ttu-id="18ec7-126">您可以在此報告進行診斷和疑難排解。</span><span class="sxs-lookup"><span data-stu-id="18ec7-126">You can us this report for diagnosing and troubleshooting.</span></span>

-   <span data-ttu-id="18ec7-127">appv 檔案。</span><span class="sxs-lookup"><span data-stu-id="18ec7-127">.appv file.</span></span> <span data-ttu-id="18ec7-128">這是虛擬應用程式檔。</span><span class="sxs-lookup"><span data-stu-id="18ec7-128">This is the virtual application file.</span></span>

-   <span data-ttu-id="18ec7-129">部署設定檔。</span><span class="sxs-lookup"><span data-stu-id="18ec7-129">Deployment configuration file.</span></span> <span data-ttu-id="18ec7-130">部署設定檔會決定虛擬應用程式將如何部署至目的電腦。</span><span class="sxs-lookup"><span data-stu-id="18ec7-130">The deployment configuration file determines how the virtual application will be deployed to target computers.</span></span>

-   <span data-ttu-id="18ec7-131">使用者設定檔。</span><span class="sxs-lookup"><span data-stu-id="18ec7-131">User configuration file.</span></span> <span data-ttu-id="18ec7-132">使用者設定檔會決定虛擬應用程式在目的電腦上的執行方式。</span><span class="sxs-lookup"><span data-stu-id="18ec7-132">The user configuration file determines how the virtual application will run on target computers.</span></span>

<span data-ttu-id="18ec7-133">**重要** 您必須設定套件轉換器所使用的% TMP% 與% TEMP% 資料夾，才能成為安全的位置和目錄。</span><span class="sxs-lookup"><span data-stu-id="18ec7-133">**Important** You must configure the %TMP% and %TEMP% folders that the package converter uses to be a secure location and directory.</span></span> <span data-ttu-id="18ec7-134">只有系統管理員可以存取安全的位置。</span><span class="sxs-lookup"><span data-stu-id="18ec7-134">A secure location is only accessible by an administrator.</span></span> <span data-ttu-id="18ec7-135">此外，當您排列套件時，您應該將套件儲存至安全的位置，或是確定在轉換與監控程式期間不允許登入任何其他使用者。</span><span class="sxs-lookup"><span data-stu-id="18ec7-135">Additionally, when you sequence the package you should save the package to a location that is secure, or make sure that no other user is allowed to be logged in during the conversion and monitoring process.</span></span>

 

<span data-ttu-id="18ec7-136">排序器主控台中的 [**選項**] 對話方塊包含下列索引標籤：</span><span class="sxs-lookup"><span data-stu-id="18ec7-136">The **Options** dialog box in the sequencer console contains the following tabs:</span></span>

-   <span data-ttu-id="18ec7-137">**[一般**]。</span><span class="sxs-lookup"><span data-stu-id="18ec7-137">**General**.</span></span> <span data-ttu-id="18ec7-138">使用此索引標籤可讓 Microsoft 更新在進行排序期間執行。</span><span class="sxs-lookup"><span data-stu-id="18ec7-138">Use this tab to enable Microsoft Updates to run during sequencing.</span></span> <span data-ttu-id="18ec7-139">選取 [**附加套件版本至 Filename** ] 來設定序列，以將版本號碼新增到已排序的虛擬化套件中。</span><span class="sxs-lookup"><span data-stu-id="18ec7-139">Select **Append Package Version to Filename** to configure the sequence to add a version number to the virtualized package that is being sequenced.</span></span> <span data-ttu-id="18ec7-140">選取 [**永遠信任套件加速器的來源**]，以使用套件加速器建立虛擬化套件，而不會提示您授權。</span><span class="sxs-lookup"><span data-stu-id="18ec7-140">Select **Always trust the source of Package Accelerators** to create virtualized packages using a package accelerator without being prompted for authorization.</span></span>

    <span data-ttu-id="18ec7-141">**重要** App-V 5.0 不支援使用 App-v 4.6 建立的套件加速器。</span><span class="sxs-lookup"><span data-stu-id="18ec7-141">**Important** Package Accelerators created using App-V4.6 are not supported by App-V 5.0.</span></span>

     

-   <span data-ttu-id="18ec7-142">**分析專案**。</span><span class="sxs-lookup"><span data-stu-id="18ec7-142">**Parse Items**.</span></span> <span data-ttu-id="18ec7-143">這個索引標籤會顯示將在虛擬環境中分析或自動標記的相關檔案路徑位置。</span><span class="sxs-lookup"><span data-stu-id="18ec7-143">This tab displays the associated file path locations that will be parsed or tokenized into in the virtual environment.</span></span> <span data-ttu-id="18ec7-144">在使用 [**高級編輯**] 中的 [**套件**檔案] 索引標籤新增檔案時，可以使用標記。</span><span class="sxs-lookup"><span data-stu-id="18ec7-144">Tokens are useful for adding files using the **Package Files** tab in **Advanced Editing**.</span></span>

-   <span data-ttu-id="18ec7-145">**排除專案**。</span><span class="sxs-lookup"><span data-stu-id="18ec7-145">**Exclusion Items**.</span></span> <span data-ttu-id="18ec7-146">使用此索引標籤，以指定在排序期間不應監視哪些資料夾和目錄。</span><span class="sxs-lookup"><span data-stu-id="18ec7-146">Use this tab to specify which folders and directories should not be monitored during sequencing.</span></span> <span data-ttu-id="18ec7-147">若要新增儲存在套件中本機應用程式資料檔案夾中的本機應用程式資料，請按一下 [**新增**]，然後指定位置及相關聯的**對應類型**。</span><span class="sxs-lookup"><span data-stu-id="18ec7-147">To add local application data that is saved in the Local App Data folder in the package, click **New** and specify the location and the associated **Mapping Type**.</span></span> <span data-ttu-id="18ec7-148">某些套件必須有這個選項。</span><span class="sxs-lookup"><span data-stu-id="18ec7-148">This option is required for some packages.</span></span>

<span data-ttu-id="18ec7-149">App-v 5.0 支援包含 Microsoft Windows 服務的應用程式。</span><span class="sxs-lookup"><span data-stu-id="18ec7-149">App-V 5.0 supports applications that include Microsoft Windows Services.</span></span> <span data-ttu-id="18ec7-150">如果應用程式包含 Windows 服務，則服務會包含在已排序的虛擬套件中，只要由排序器監控，就會包含在已排序的虛擬套件中。</span><span class="sxs-lookup"><span data-stu-id="18ec7-150">If an application includes a Windows service, the Service will be included in the sequenced virtual package as long as it is installed while being monitored by the sequencer.</span></span> <span data-ttu-id="18ec7-151">如果虛擬應用程式在初次執行時建立 Windows 服務，然後在安裝之後，應用程式必須在排序器監視時執行，以便將 Windows 服務新增到套件中。</span><span class="sxs-lookup"><span data-stu-id="18ec7-151">If a virtual application creates a Windows service when it initially runs, then later, after installation, the application must be run while the sequencer is monitoring so that the Windows Service will be added to the package.</span></span> <span data-ttu-id="18ec7-152">只有在本機系統帳戶下執行的服務才受支援。</span><span class="sxs-lookup"><span data-stu-id="18ec7-152">Only Services that run under the Local System account are supported.</span></span> <span data-ttu-id="18ec7-153">針對自動啟動或延遲自動啟動所設定的服務會在套件中的第一個虛擬應用程式在套件的虛擬環境內執行之前先啟動。</span><span class="sxs-lookup"><span data-stu-id="18ec7-153">Services that are configured for AutoStart or Delayed AutoStart are started before the first virtual application in a package runs inside the package’s Virtual Environment.</span></span> <span data-ttu-id="18ec7-154">當套件內的虛擬應用程式透過 API 呼叫啟動服務時，系統會啟動已設定為按需由應用程式啟動的 Windows 服務。</span><span class="sxs-lookup"><span data-stu-id="18ec7-154">Windows Services that are configured to be started on demand by an application are started when the virtual application inside the package starts the Service via API call.</span></span>

[<span data-ttu-id="18ec7-155">如何使用 App-V 5.0 為新應用程式進行序列化</span><span class="sxs-lookup"><span data-stu-id="18ec7-155">How to Sequence a New Application with App-V 5.0</span></span>](how-to-sequence-a-new-application-with-app-v-50-beta-gb18030.md)

## <a href="" id="---------app-v-5-0-sp2-shell-extension-support"></a> <span data-ttu-id="18ec7-156">App-v 5.0 SP2 命令介面延伸支援</span><span class="sxs-lookup"><span data-stu-id="18ec7-156">App-V 5.0SP2 shell extension support</span></span>


<span data-ttu-id="18ec7-157">App V 5.0 SP2 支援命令介面延伸。</span><span class="sxs-lookup"><span data-stu-id="18ec7-157">App-V 5.0SP2 supports shell extensions.</span></span> <span data-ttu-id="18ec7-158">在排序期間，系統會在套件中檢測並內嵌 Shell 延伸。</span><span class="sxs-lookup"><span data-stu-id="18ec7-158">Shell extensions will be detected and embedded in the package during sequencing.</span></span>

<span data-ttu-id="18ec7-159">在排序過程中，會自動將 Shell 延伸內嵌在套件中。</span><span class="sxs-lookup"><span data-stu-id="18ec7-159">Shell extensions are embedded in the package automatically during the sequencing process.</span></span> <span data-ttu-id="18ec7-160">套件發佈之後，命令介面延伸提供使用者的功能，就如同已在本機安裝應用程式一樣。</span><span class="sxs-lookup"><span data-stu-id="18ec7-160">When the package is published, the shell extension gives users the same functionality as if the application were locally installed.</span></span>

**<span data-ttu-id="18ec7-161">使用命令介面延伸的需求：</span><span class="sxs-lookup"><span data-stu-id="18ec7-161">Requirements for using shell extensions:</span></span>**

-   <span data-ttu-id="18ec7-162">包含內嵌命令介面延伸的套件必須全域發佈。</span><span class="sxs-lookup"><span data-stu-id="18ec7-162">Packages that contain embedded shell extensions must be published globally.</span></span> <span data-ttu-id="18ec7-163">應用程式在用戶端上不需要任何額外的設定或配置，就能啟用 shell 擴充功能。</span><span class="sxs-lookup"><span data-stu-id="18ec7-163">The application requires no additional setup or configuration on the client to enable the shell extension functionality.</span></span>

-   <span data-ttu-id="18ec7-164">應用程式、Sequencer 和 App-v 用戶端的 "位數" 必須相符，否則 shell 延伸將無法運作。</span><span class="sxs-lookup"><span data-stu-id="18ec7-164">The “bitness” of the application, Sequencer, and App-V client must match, or the shell extensions won’t work.</span></span> <span data-ttu-id="18ec7-165">例如：</span><span class="sxs-lookup"><span data-stu-id="18ec7-165">For example:</span></span>

    -   <span data-ttu-id="18ec7-166">應用程式的版本為64位。</span><span class="sxs-lookup"><span data-stu-id="18ec7-166">The version of the application is 64-bit.</span></span>

    -   <span data-ttu-id="18ec7-167">排序器正在64位電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="18ec7-167">The Sequencer is running on a 64-bit computer.</span></span>

    -   <span data-ttu-id="18ec7-168">套件正在傳送至64位的 App-v 用戶端電腦。</span><span class="sxs-lookup"><span data-stu-id="18ec7-168">The package is being delivered to a 64-bit App-V client computer.</span></span>

<span data-ttu-id="18ec7-169">下表列出支援的命令介面延伸：</span><span class="sxs-lookup"><span data-stu-id="18ec7-169">The following table lists the supported shell extensions:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="18ec7-170">處理</span><span class="sxs-lookup"><span data-stu-id="18ec7-170">Handler</span></span></th>
<th align="left"><span data-ttu-id="18ec7-171">描述</span><span class="sxs-lookup"><span data-stu-id="18ec7-171">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="18ec7-172">操作功能表處理常式</span><span class="sxs-lookup"><span data-stu-id="18ec7-172">Context menu handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="18ec7-173">將功能表項目新增至操作功能表。</span><span class="sxs-lookup"><span data-stu-id="18ec7-173">Adds menu items to the context menu.</span></span> <span data-ttu-id="18ec7-174">在顯示操作功能表前呼叫該內容。</span><span class="sxs-lookup"><span data-stu-id="18ec7-174">It is called before the context menu is displayed.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="18ec7-175">拖放處理常式</span><span class="sxs-lookup"><span data-stu-id="18ec7-175">Drag-and-drop handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="18ec7-176">控制動作在按一下滑鼠右鍵時，拖放並修改所出現的操作功能表。</span><span class="sxs-lookup"><span data-stu-id="18ec7-176">Controls the action where right-click, drag and drop and modifies the context menu that appears.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="18ec7-177">拖放目標處理常式</span><span class="sxs-lookup"><span data-stu-id="18ec7-177">Drop target handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="18ec7-178">控制將資料物件拖曳到拖放目標（例如檔案）之後的動作。</span><span class="sxs-lookup"><span data-stu-id="18ec7-178">Controls the action after a data object is dragged and dropped over a drop target such as a file.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="18ec7-179">資料物件處理常式</span><span class="sxs-lookup"><span data-stu-id="18ec7-179">Data object handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="18ec7-180">控制將檔案複製到剪貼簿，或將檔案拖放到拖放目標上之後的動作。</span><span class="sxs-lookup"><span data-stu-id="18ec7-180">Controls the action after a file is copied to the clipboard or dragged and dropped over a drop target.</span></span> <span data-ttu-id="18ec7-181">它可以提供其他剪貼簿格式至拖放目標。</span><span class="sxs-lookup"><span data-stu-id="18ec7-181">It can provide additional clipboard formats to the drop target.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="18ec7-182">屬性工作表處理常式</span><span class="sxs-lookup"><span data-stu-id="18ec7-182">Property sheet handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="18ec7-183">取代或新增頁面至物件的 [屬性工作表] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="18ec7-183">Replaces or adds pages to the property sheet dialog box of an object.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="18ec7-184">提示處理常式</span><span class="sxs-lookup"><span data-stu-id="18ec7-184">Infotip handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="18ec7-185">允許您檢索專案的標誌和資訊提示資訊，並在滑鼠懸停時將它顯示在彈出工具提示內。</span><span class="sxs-lookup"><span data-stu-id="18ec7-185">Allows retrieving flags and infotip information for an item and displaying it inside a pop-up tooltip upon mouse hover.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="18ec7-186">欄處理常式</span><span class="sxs-lookup"><span data-stu-id="18ec7-186">Column handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="18ec7-187">可讓您在 <strong> Windows 資源管理器的詳細資料檢視中建立和顯示自訂欄 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="18ec7-187">Allows creating and displaying custom columns in <strong>Windows Explorer Details view</strong>.</span></span> <span data-ttu-id="18ec7-188">它可以用來延伸排序與分組。</span><span class="sxs-lookup"><span data-stu-id="18ec7-188">It can be used to extend sorting and grouping.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="18ec7-189">預覽處理常式</span><span class="sxs-lookup"><span data-stu-id="18ec7-189">Preview handler</span></span></p></td>
<td align="left"><p><span data-ttu-id="18ec7-190">啟用要在 Windows 資源管理器預覽窗格中顯示的檔案預覽。</span><span class="sxs-lookup"><span data-stu-id="18ec7-190">Enables a preview of a file to be displayed in the Windows Explorer Preview pane.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="18ec7-191">寫入時拷貝（牛）副檔名支援</span><span class="sxs-lookup"><span data-stu-id="18ec7-191">Copy on Write (CoW) file extension support</span></span>


<span data-ttu-id="18ec7-192">[寫入時拷貝（牛）] 檔案延伸功能可讓 App-v 5.0 動態寫入到所使用的虛擬套件中所包含的特定位置。</span><span class="sxs-lookup"><span data-stu-id="18ec7-192">Copy on write (CoW) file extensions allow App-V 5.0 to dynamically write to specific locations contained in the virtual package while it is being used.</span></span>

<span data-ttu-id="18ec7-193">下表顯示可在 VFS 目錄下的虛擬套件中存在的檔案類型，但無法在執行 App-v 5.0 用戶端的電腦上更新。</span><span class="sxs-lookup"><span data-stu-id="18ec7-193">The following table displays the file types that can exist in a virtual package under the VFS directory, but cannot be updated on the computer running the App-V 5.0 client.</span></span> <span data-ttu-id="18ec7-194">所有其他的檔案和目錄都可以修改。</span><span class="sxs-lookup"><span data-stu-id="18ec7-194">All other files and directories can be modified.</span></span>

<span data-ttu-id="18ec7-195">。</span><span class="sxs-lookup"><span data-stu-id="18ec7-195">.acm</span></span>

<span data-ttu-id="18ec7-196">. asa</span><span class="sxs-lookup"><span data-stu-id="18ec7-196">.asa</span></span>

<span data-ttu-id="18ec7-197">.asp</span><span class="sxs-lookup"><span data-stu-id="18ec7-197">.asp</span></span>

<span data-ttu-id="18ec7-198">.aspx</span><span class="sxs-lookup"><span data-stu-id="18ec7-198">.aspx</span></span>

<span data-ttu-id="18ec7-199">. ax</span><span class="sxs-lookup"><span data-stu-id="18ec7-199">.ax</span></span>

<span data-ttu-id="18ec7-200">.bat</span><span class="sxs-lookup"><span data-stu-id="18ec7-200">.bat</span></span>

<span data-ttu-id="18ec7-201">.cer</span><span class="sxs-lookup"><span data-stu-id="18ec7-201">.cer</span></span>

<span data-ttu-id="18ec7-202">.chm</span><span class="sxs-lookup"><span data-stu-id="18ec7-202">.chm</span></span>

<span data-ttu-id="18ec7-203">clb</span><span class="sxs-lookup"><span data-stu-id="18ec7-203">.clb</span></span>

<span data-ttu-id="18ec7-204">.cmd</span><span class="sxs-lookup"><span data-stu-id="18ec7-204">.cmd</span></span>

<span data-ttu-id="18ec7-205">.cnt</span><span class="sxs-lookup"><span data-stu-id="18ec7-205">.cnt</span></span>

<span data-ttu-id="18ec7-206">.cnv</span><span class="sxs-lookup"><span data-stu-id="18ec7-206">.cnv</span></span>

<span data-ttu-id="18ec7-207">.com</span><span class="sxs-lookup"><span data-stu-id="18ec7-207">.com</span></span>

<span data-ttu-id="18ec7-208">.cpl</span><span class="sxs-lookup"><span data-stu-id="18ec7-208">.cpl</span></span>

<span data-ttu-id="18ec7-209">.cpx</span><span class="sxs-lookup"><span data-stu-id="18ec7-209">.cpx</span></span>

<span data-ttu-id="18ec7-210">.crt</span><span class="sxs-lookup"><span data-stu-id="18ec7-210">.crt</span></span>

<span data-ttu-id="18ec7-211">.dll</span><span class="sxs-lookup"><span data-stu-id="18ec7-211">.dll</span></span>

<span data-ttu-id="18ec7-212">.drv</span><span class="sxs-lookup"><span data-stu-id="18ec7-212">.drv</span></span>

<span data-ttu-id="18ec7-213">.exe</span><span class="sxs-lookup"><span data-stu-id="18ec7-213">.exe</span></span>

<span data-ttu-id="18ec7-214">.fon</span><span class="sxs-lookup"><span data-stu-id="18ec7-214">.fon</span></span>

<span data-ttu-id="18ec7-215">.grp</span><span class="sxs-lookup"><span data-stu-id="18ec7-215">.grp</span></span>

<span data-ttu-id="18ec7-216">.hlp</span><span class="sxs-lookup"><span data-stu-id="18ec7-216">.hlp</span></span>

<span data-ttu-id="18ec7-217">.hta</span><span class="sxs-lookup"><span data-stu-id="18ec7-217">.hta</span></span>

<span data-ttu-id="18ec7-218">. ime</span><span class="sxs-lookup"><span data-stu-id="18ec7-218">.ime</span></span>

<span data-ttu-id="18ec7-219">.inf</span><span class="sxs-lookup"><span data-stu-id="18ec7-219">.inf</span></span>

<span data-ttu-id="18ec7-220">.ins</span><span class="sxs-lookup"><span data-stu-id="18ec7-220">.ins</span></span>

<span data-ttu-id="18ec7-221">.isp</span><span class="sxs-lookup"><span data-stu-id="18ec7-221">.isp</span></span>

<span data-ttu-id="18ec7-222">。它的</span><span class="sxs-lookup"><span data-stu-id="18ec7-222">.its</span></span>

<span data-ttu-id="18ec7-223">.js</span><span class="sxs-lookup"><span data-stu-id="18ec7-223">.js</span></span>

<span data-ttu-id="18ec7-224">.jse</span><span class="sxs-lookup"><span data-stu-id="18ec7-224">.jse</span></span>

<span data-ttu-id="18ec7-225">.lnk</span><span class="sxs-lookup"><span data-stu-id="18ec7-225">.lnk</span></span>

<span data-ttu-id="18ec7-226">.msc</span><span class="sxs-lookup"><span data-stu-id="18ec7-226">.msc</span></span>

<span data-ttu-id="18ec7-227">.msi</span><span class="sxs-lookup"><span data-stu-id="18ec7-227">.msi</span></span>

<span data-ttu-id="18ec7-228">.msp</span><span class="sxs-lookup"><span data-stu-id="18ec7-228">.msp</span></span>

<span data-ttu-id="18ec7-229">.mst</span><span class="sxs-lookup"><span data-stu-id="18ec7-229">.mst</span></span>

<span data-ttu-id="18ec7-230">mui</span><span class="sxs-lookup"><span data-stu-id="18ec7-230">.mui</span></span>

<span data-ttu-id="18ec7-231">. nls</span><span class="sxs-lookup"><span data-stu-id="18ec7-231">.nls</span></span>

<span data-ttu-id="18ec7-232">.ocx</span><span class="sxs-lookup"><span data-stu-id="18ec7-232">.ocx</span></span>

<span data-ttu-id="18ec7-233">pal</span><span class="sxs-lookup"><span data-stu-id="18ec7-233">.pal</span></span>

<span data-ttu-id="18ec7-234">.pcd</span><span class="sxs-lookup"><span data-stu-id="18ec7-234">.pcd</span></span>

<span data-ttu-id="18ec7-235">.pif</span><span class="sxs-lookup"><span data-stu-id="18ec7-235">.pif</span></span>

<span data-ttu-id="18ec7-236">.reg</span><span class="sxs-lookup"><span data-stu-id="18ec7-236">.reg</span></span>

<span data-ttu-id="18ec7-237">.scf</span><span class="sxs-lookup"><span data-stu-id="18ec7-237">.scf</span></span>

<span data-ttu-id="18ec7-238">.scr</span><span class="sxs-lookup"><span data-stu-id="18ec7-238">.scr</span></span>

<span data-ttu-id="18ec7-239">. sct</span><span class="sxs-lookup"><span data-stu-id="18ec7-239">.sct</span></span>

<span data-ttu-id="18ec7-240">.shb</span><span class="sxs-lookup"><span data-stu-id="18ec7-240">.shb</span></span>

<span data-ttu-id="18ec7-241">.shs</span><span class="sxs-lookup"><span data-stu-id="18ec7-241">.shs</span></span>

<span data-ttu-id="18ec7-242">.sys</span><span class="sxs-lookup"><span data-stu-id="18ec7-242">.sys</span></span>

<span data-ttu-id="18ec7-243">.tlb</span><span class="sxs-lookup"><span data-stu-id="18ec7-243">.tlb</span></span>

<span data-ttu-id="18ec7-244">. tsp</span><span class="sxs-lookup"><span data-stu-id="18ec7-244">.tsp</span></span>

<span data-ttu-id="18ec7-245">.url</span><span class="sxs-lookup"><span data-stu-id="18ec7-245">.url</span></span>

<span data-ttu-id="18ec7-246">.vb</span><span class="sxs-lookup"><span data-stu-id="18ec7-246">.vb</span></span>

<span data-ttu-id="18ec7-247">.vbe</span><span class="sxs-lookup"><span data-stu-id="18ec7-247">.vbe</span></span>

<span data-ttu-id="18ec7-248">.vbs</span><span class="sxs-lookup"><span data-stu-id="18ec7-248">.vbs</span></span>

<span data-ttu-id="18ec7-249">.vsmacros</span><span class="sxs-lookup"><span data-stu-id="18ec7-249">.vsmacros</span></span>

<span data-ttu-id="18ec7-250">.ws</span><span class="sxs-lookup"><span data-stu-id="18ec7-250">.ws</span></span>

<span data-ttu-id="18ec7-251">。 esc</span><span class="sxs-lookup"><span data-stu-id="18ec7-251">.esc</span></span>

<span data-ttu-id="18ec7-252">.wsf</span><span class="sxs-lookup"><span data-stu-id="18ec7-252">.wsf</span></span>

<span data-ttu-id="18ec7-253">.wsh</span><span class="sxs-lookup"><span data-stu-id="18ec7-253">.wsh</span></span>

 

## <span data-ttu-id="18ec7-254">修改現有的虛擬應用程式套件</span><span class="sxs-lookup"><span data-stu-id="18ec7-254">Modifying an existing virtual application package</span></span>


<span data-ttu-id="18ec7-255">您可以使用 sequencer 來修改現有的套件。</span><span class="sxs-lookup"><span data-stu-id="18ec7-255">You can use the sequencer to modify an existing package.</span></span> <span data-ttu-id="18ec7-256">您在其上執行這項作業的電腦應該與您用來建立應用程式的電腦的晶片架構相符。</span><span class="sxs-lookup"><span data-stu-id="18ec7-256">The computer on which you do this should match the chip architecture of the computer you used to create the application.</span></span> <span data-ttu-id="18ec7-257">例如，如果您最初是使用執行64位作業系統的電腦將套件排序列化，您應該使用執行64位作業系統的電腦來修改套件。</span><span class="sxs-lookup"><span data-stu-id="18ec7-257">For example, if you initially sequenced a package using a computer running a 64-bit operating system, you should modify the package using a computer running a 64-bit operating system.</span></span>

[<span data-ttu-id="18ec7-258">如何修改現有的虛擬應用程式套件</span><span class="sxs-lookup"><span data-stu-id="18ec7-258">How to Modify an Existing Virtual Application Package</span></span>](how-to-modify-an-existing-virtual-application-package-beta.md)

## <span data-ttu-id="18ec7-259">建立專案範本</span><span class="sxs-lookup"><span data-stu-id="18ec7-259">Creating a project template</span></span>


<span data-ttu-id="18ec7-260">Appvt 檔案是一個專案範本，可用於儲存常用的自訂設定。</span><span class="sxs-lookup"><span data-stu-id="18ec7-260">A .appvt file is a project template that can be used to save commonly applied, customized settings.</span></span> <span data-ttu-id="18ec7-261">然後，您就可以更輕鬆地使用這些設定來進行未來的 sequencings。</span><span class="sxs-lookup"><span data-stu-id="18ec7-261">You can then more easily use these settings for future sequencings.</span></span>

<span data-ttu-id="18ec7-262">App-v 5.0 專案範本與 App-v 5.0 應用程式加速器不同，因為 App-v 5.0 應用程式加速器是應用程式專用的，而 App-v 5.0 專案範本可以套用到多個應用程式。</span><span class="sxs-lookup"><span data-stu-id="18ec7-262">App-V 5.0 project templates differ from App-V 5.0 Application Accelerators because App-V 5.0 Application Accelerators are application-specific, and App-V 5.0 project templates can be applied to multiple applications.</span></span> <span data-ttu-id="18ec7-263">此外，當您使用套件加速器建立虛擬應用程式套件時，您無法使用專案範本。</span><span class="sxs-lookup"><span data-stu-id="18ec7-263">Additionally, you cannot use a project template when you use a Package Accelerator to create a virtual application package.</span></span> <span data-ttu-id="18ec7-264">下列一般設定會儲存在 App-v 5.0 專案範本：</span><span class="sxs-lookup"><span data-stu-id="18ec7-264">The following general settings are saved with an App-V 5.0 project template:</span></span>

<span data-ttu-id="18ec7-265">範本可以指定及儲存多個設定，如下所示：</span><span class="sxs-lookup"><span data-stu-id="18ec7-265">A template can specify and store multiple settings as follows:</span></span>

-   <span data-ttu-id="18ec7-266">[**高級監視] 選項**。</span><span class="sxs-lookup"><span data-stu-id="18ec7-266">**Advanced Monitoring Options**.</span></span> <span data-ttu-id="18ec7-267">可讓 Microsoft 更新在監視期間執行。</span><span class="sxs-lookup"><span data-stu-id="18ec7-267">Enables Microsoft Update to run during monitoring.</span></span> <span data-ttu-id="18ec7-268">儲存 [允許本機互動] 選項設定</span><span class="sxs-lookup"><span data-stu-id="18ec7-268">Saves allow local interaction option settings</span></span>

-   <span data-ttu-id="18ec7-269">**一般選項**。</span><span class="sxs-lookup"><span data-stu-id="18ec7-269">**General Options**.</span></span> <span data-ttu-id="18ec7-270">啟用**Windows 安裝程式**，並將**套件版本附加至 Filename**。</span><span class="sxs-lookup"><span data-stu-id="18ec7-270">Enables the use of **Windows Installer**, **Append Package Version to Filename**.</span></span>

-   **<span data-ttu-id="18ec7-271">排除專案。</span><span class="sxs-lookup"><span data-stu-id="18ec7-271">Exclusion Items.</span></span>** <span data-ttu-id="18ec7-272">包含 [排除] 模式清單。</span><span class="sxs-lookup"><span data-stu-id="18ec7-272">Contains the Exclusion pattern list.</span></span>

[<span data-ttu-id="18ec7-273">如何建立及使用專案範本</span><span class="sxs-lookup"><span data-stu-id="18ec7-273">How to Create and Use a Project Template</span></span>](how-to-create-and-use-a-project-template.md)

## <span data-ttu-id="18ec7-274">建立套件加速器</span><span class="sxs-lookup"><span data-stu-id="18ec7-274">Creating a package accelerator</span></span>


<span data-ttu-id="18ec7-275">**記事** 您必須使用 App-v 5.0 來重新建立使用舊版 App-v 建立的套件加速器。</span><span class="sxs-lookup"><span data-stu-id="18ec7-275">**Note** Package accelerators created using a previous version of App-V must be recreated using App-V 5.0.</span></span>

 

<span data-ttu-id="18ec7-276">您可以使用 App-v 5.0 封裝加速器來自動產生新的虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="18ec7-276">You can use App-V 5.0 package accelerators to automatically generate a new virtual application packages.</span></span> <span data-ttu-id="18ec7-277">成功建立套件加速器之後，您可以重複使用並共用套件加速器。</span><span class="sxs-lookup"><span data-stu-id="18ec7-277">After you have successfully created a package accelerator, you can reuse and share the package accelerator.</span></span>

<span data-ttu-id="18ec7-278">在某些情況下，若要建立套件加速器，您可能必須在執行排序器的電腦上本機安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="18ec7-278">In some situations, to create the package accelerator, you might have to install the application locally on the computer that runs the sequencer.</span></span> <span data-ttu-id="18ec7-279">在這種情況下，您應該先嘗試使用安裝媒體建立套件加速器。</span><span class="sxs-lookup"><span data-stu-id="18ec7-279">In such cases, you should first try to create the package accelerator with the installation media.</span></span> <span data-ttu-id="18ec7-280">如果需要多個遺失的檔案，您應該在執行排序器的電腦上本機安裝應用程式，然後建立套件加速器。</span><span class="sxs-lookup"><span data-stu-id="18ec7-280">If multiple missing files are required, you should install the application locally to the computer that runs the sequencer, and then create the package accelerator.</span></span>

<span data-ttu-id="18ec7-281">成功建立套件加速器之後，您可以重複使用並共用套件加速器。</span><span class="sxs-lookup"><span data-stu-id="18ec7-281">After you have successfully created a Package Accelerator, you can reuse and share the Package Accelerator.</span></span> <span data-ttu-id="18ec7-282">建立 App-v 5.0 套件加速器是一個高級任務。</span><span class="sxs-lookup"><span data-stu-id="18ec7-282">Creating App-V 5.0 Package Accelerators is an advanced task.</span></span> <span data-ttu-id="18ec7-283">套件加速器可以包含密碼和使用者專用的資訊。</span><span class="sxs-lookup"><span data-stu-id="18ec7-283">Package Accelerators can contain password and user-specific information.</span></span> <span data-ttu-id="18ec7-284">因此，您必須將套件加速器與關聯安裝媒體儲存在安全的位置，而且您應該在建立套件加速器之後進行數位簽章，以便在套用 app-v 5.0 套件加速器時驗證發行者。</span><span class="sxs-lookup"><span data-stu-id="18ec7-284">Therefore you must save Package Accelerators and the associated installation media in a secure location, and you should digitally sign the Package Accelerator after you create it so that the publisher can be verified when the App-V 5.0 Package Accelerator is applied.</span></span>

[<span data-ttu-id="18ec7-285">如何建立封裝加速器</span><span class="sxs-lookup"><span data-stu-id="18ec7-285">How to Create a Package Accelerator</span></span>](how-to-create-a-package-accelerator.md)

[<span data-ttu-id="18ec7-286">如何使用 App-V 封裝加速器建立虛擬應用程式套件</span><span class="sxs-lookup"><span data-stu-id="18ec7-286">How to Create a Virtual Application Package Using an App-V Package Accelerator</span></span>](how-to-create-a-virtual-application-package-using-an-app-v-package-accelerator.md)

## <span data-ttu-id="18ec7-287">Sequencer 錯誤報表</span><span class="sxs-lookup"><span data-stu-id="18ec7-287">Sequencer error reporting</span></span>


<span data-ttu-id="18ec7-288">App-v 5.0 排序器可以在排序期間檢測一般的順序問題。</span><span class="sxs-lookup"><span data-stu-id="18ec7-288">The App-V 5.0 Sequencer can detect common sequencing issues during sequencing.</span></span> <span data-ttu-id="18ec7-289">[順序] 嚮導末端的 [**安裝報告**] 頁面會根據問題的嚴重性，顯示分類為**錯誤**、**警告**及**資訊**的診斷訊息。</span><span class="sxs-lookup"><span data-stu-id="18ec7-289">The **Installation Report** page at the end of the sequencing wizard displays diagnostic messages categorized into **Errors**, **Warnings**, and **Info** depending on the severity of the issue.</span></span>

<span data-ttu-id="18ec7-290">您也可以使用 Windows 事件檢視器，找到有關順序錯誤的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="18ec7-290">You can also find additional information about sequencing errors using the Windows Event Viewer.</span></span>






## <a href="" id="other-resources-for-the-app-v-5-0-sequencer-"></a><span data-ttu-id="18ec7-291">App-v 5.0 排序器的其他資源</span><span class="sxs-lookup"><span data-stu-id="18ec7-291">Other resources for the App-V 5.0 sequencer</span></span>


-   [<span data-ttu-id="18ec7-292">App-V 5.0 作業</span><span class="sxs-lookup"><span data-stu-id="18ec7-292">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

 

 





