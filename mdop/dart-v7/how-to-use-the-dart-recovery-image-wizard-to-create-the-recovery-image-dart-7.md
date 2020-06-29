---
title: 如何使用 DaRT 復原映像精靈來建立復原映像
description: 如何使用 DaRT 復原映像精靈來建立復原映像
author: dansimp
ms.assetid: 1b8ef983-fff9-4d75-a2f6-53120c5c00c9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 49253a8c0bf9c9073b57712acc773e4a57e31d72
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809645"
---
# <span data-ttu-id="fff59-103">如何使用 DaRT 復原映像精靈來建立復原映像</span><span class="sxs-lookup"><span data-stu-id="fff59-103">How to Use the DaRT Recovery Image Wizard to Create the Recovery Image</span></span>


<span data-ttu-id="fff59-104">Microsoft Diagnostics 與修復工具組（DaRT）7包含 Windows 中用來建立可引導的國際標準組織（ISO）影像的**DaRT 復原影像嚮導**。</span><span class="sxs-lookup"><span data-stu-id="fff59-104">Microsoft Diagnostics and Recovery Toolset (DaRT)7 includes the **DaRT Recovery Image Wizard** that is used in Windows to create a bootable International Organization for Standardization (ISO) image.</span></span> <span data-ttu-id="fff59-105">ISO 影像是代表 CD 原始內容的檔案。</span><span class="sxs-lookup"><span data-stu-id="fff59-105">An ISO image is a file that represents the raw contents of a CD.</span></span>

<span data-ttu-id="fff59-106">**DaRT 復原映像嚮導**需要下列資訊：</span><span class="sxs-lookup"><span data-stu-id="fff59-106">The **DaRT Recovery Image Wizard** requires the following information:</span></span>

-   <span data-ttu-id="fff59-107">[**啟動影像**]：您必須提供建立 DaRT 復原影像所需的 WINDOWS 7 DVD 或 windows 7 來源檔案的路徑。</span><span class="sxs-lookup"><span data-stu-id="fff59-107">**Boot Image**˚˚You must provide the path of a Windows 7 DVD or Windows 7 source files that are required to create the DaRT recovery image.</span></span>

-   <span data-ttu-id="fff59-108">**工具選取範圍**您可以選取要包含在 DaRT 復原影像中的工具。</span><span class="sxs-lookup"><span data-stu-id="fff59-108">**Tool Selection**˚˚You can select the tools to include on the DaRT recovery image.</span></span>

-   <span data-ttu-id="fff59-109">[**遠端**連線] 您可以選取是否要讓 DaRT 復原映像包含在技術支援人員與端使用者電腦之間建立遠端連線的能力。</span><span class="sxs-lookup"><span data-stu-id="fff59-109">**Remote Connections**˚˚You can select whether you want the DaRT recovery image to include the ability to establish a remote connection between the helpdesk and the end-user computer.</span></span>

-   <span data-ttu-id="fff59-110">**Windows 版調試工具的**要求您提供 Windows 調試工具的位置。</span><span class="sxs-lookup"><span data-stu-id="fff59-110">**Debugging Tools for Windows**˚˚You are asked to provide the location of the Debugging Tools for Windows.</span></span>

-   <span data-ttu-id="fff59-111">**獨立系統 Sweeper 的定義**：您可以決定是否要在建立恢復影像時下載最新定義，或稍後下載定義。</span><span class="sxs-lookup"><span data-stu-id="fff59-111">**Definitions for Standalone System Sweeper**˚˚You can decide whether to download the latest definitions at the time that you create the recovery image or download the definitions later.</span></span>

-   <span data-ttu-id="fff59-112">**驅動程式**？系統會詢問您是否要將驅動程式新增到 ISO 影像。</span><span class="sxs-lookup"><span data-stu-id="fff59-112">**Drivers**˚˚You are asked whether you want to add drivers to the ISO image.</span></span>

-   <span data-ttu-id="fff59-113">**其他**檔案：您可以將檔案新增到可協助診斷問題的 ISO 映像中。</span><span class="sxs-lookup"><span data-stu-id="fff59-113">**Additional Files**˚˚You can add files to the ISO image that might help diagnose problems.</span></span>

-   <span data-ttu-id="fff59-114">**Iso 圖像位置**：系統會要求您指定 iso 影像應該位於何處。</span><span class="sxs-lookup"><span data-stu-id="fff59-114">**ISO Image Location**˚˚You are asked to specify where the ISO image should be located.</span></span>

-   <span data-ttu-id="fff59-115">**Cd/DVD 磁片磁碟機**？系統會要求您指定是否要使用 CD 或 dvd 磁碟機來燒錄 CD 或 dvd。</span><span class="sxs-lookup"><span data-stu-id="fff59-115">**CD/DVD Drive**˚˚You are asked to specify whether the CD or DVD drive should be used to burn the CD or DVD.</span></span>

<span data-ttu-id="fff59-116">**記事** 根據在**DaRT 復原映像嚮導**中選取的工具，ISO 影像大小可能會有所不同。</span><span class="sxs-lookup"><span data-stu-id="fff59-116">**Note** The ISO image size can vary, depending on the tools that were selected in the **DaRT Recovery Image Wizard**.</span></span>

 

## <span data-ttu-id="fff59-117">使用 DaRT 復原影像嚮導建立復原影像</span><span class="sxs-lookup"><span data-stu-id="fff59-117">To create the recovery image using the DaRT Recovery Image Wizard</span></span>


<span data-ttu-id="fff59-118">請依照下列指示使用**dart 復原映射嚮導**來建立 DaRT 恢復影像。</span><span class="sxs-lookup"><span data-stu-id="fff59-118">Follow these instructions to use the **DaRT Recovery Image Wizard** to create the DaRT recovery image.</span></span>

### <span data-ttu-id="fff59-119">選取要納入 DaRT 復原影像的工具</span><span class="sxs-lookup"><span data-stu-id="fff59-119">To select the tools to include on the DaRT recovery image</span></span>

<span data-ttu-id="fff59-120">**DaRT 復原影像嚮導**會顯示一個**工具選取**對話方塊。</span><span class="sxs-lookup"><span data-stu-id="fff59-120">The **DaRT Recovery Image Wizard** presents a **Tool Selection** dialog box.</span></span> <span data-ttu-id="fff59-121">您可以透過醒目提示工具，然後按一下 [**啟用**] 或 [**停**用] 按鈕，從工具清單中選取或移除工具，以包含在 DaRT 復原影像中。</span><span class="sxs-lookup"><span data-stu-id="fff59-121">You can select or remove tools from the list of tools to be included on the DaRT recovery image by highlighting a tool and then clicking the **Enable** or **Disable** buttons.</span></span>

<span data-ttu-id="fff59-122">在您選取要納入復原影像的所有工具之後，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="fff59-122">After you have selected all the tools that you want to include on the recovery image, click **Next**.</span></span>

### <span data-ttu-id="fff59-123">新增允許遠端連線的選項</span><span class="sxs-lookup"><span data-stu-id="fff59-123">To add the option to allow remote connectivity</span></span>

<span data-ttu-id="fff59-124">您可以選取 [**允許遠端**連線] 核取方塊，在 [**診斷與修復工具集**] 視窗中提供選項，以便在技術支援者與使用者電腦之間建立遠端連線。</span><span class="sxs-lookup"><span data-stu-id="fff59-124">You can select the **Allow remote connections** check box to provide the option in the **Diagnostics and Recovery Toolset** window to establish a remote connection between the helpdesk agent and an end-user computer.</span></span> <span data-ttu-id="fff59-125">在説明台代理程式建立遠端連線之後，就可以從遠端位置，在最終使用者電腦上執行 DaRT 工具。</span><span class="sxs-lookup"><span data-stu-id="fff59-125">After a helpdesk agent establishes a remote connection, they can run the DaRT tools on the end-user computer from a remote location.</span></span>

<span data-ttu-id="fff59-126">您可以選取 [**指定埠號碼**] 核取方塊，以輸入建立遠端連線時所要使用的特定埠號碼。</span><span class="sxs-lookup"><span data-stu-id="fff59-126">You can select the **Specify the port number** check box to enter a specific port number that will be used when establishing a remote connection.</span></span> <span data-ttu-id="fff59-127">您可以指定1和65535之間的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="fff59-127">You can specify a port number between 1 and 65535.</span></span> <span data-ttu-id="fff59-128">建議將埠號碼設為1024或更高，以將衝突可能性降至最低。</span><span class="sxs-lookup"><span data-stu-id="fff59-128">We recommend that the port number be 1024 or higher to minimize the possibility of a conflict.</span></span>

<span data-ttu-id="fff59-129">您也可以建立使用者建立遠端連線時，會收到的自訂訊息。</span><span class="sxs-lookup"><span data-stu-id="fff59-129">You can also create a customized message that an end user will receive when they establish a remote connection.</span></span> <span data-ttu-id="fff59-130">訊息最多可以為2048個字元。</span><span class="sxs-lookup"><span data-stu-id="fff59-130">The message can be a maximum of 2048 characters.</span></span>

<span data-ttu-id="fff59-131">如需有關遠端執行 DaRT 工具的詳細資訊，請參閱[如何使用 Dart 恢復影像復原遠端電腦](how-to-recover-remote-computers-using-the-dart-recovery-image-dart-7.md)。</span><span class="sxs-lookup"><span data-stu-id="fff59-131">For more information about remotely running the DaRT tools, see [How to Recover Remote Computers Using the DaRT Recovery Image](how-to-recover-remote-computers-using-the-dart-recovery-image-dart-7.md).</span></span>

### <span data-ttu-id="fff59-132">若要將 Windows 的調試工具新增至 DaRT 恢復影像</span><span class="sxs-lookup"><span data-stu-id="fff59-132">To add the Debugging Tools for Windows to the DaRT recovery image</span></span>

<span data-ttu-id="fff59-133">在**DaRT [復原映像嚮導**] 的 [**崩潰分析**程式] 對話方塊中，系統會要求您指定 Windows 調試工具的位置。</span><span class="sxs-lookup"><span data-stu-id="fff59-133">In the **Crash Analyzer** dialog box of the **DaRT Recovery Image Wizard**, you are asked to specify the location of the Debugging Tools for Windows.</span></span> <span data-ttu-id="fff59-134">如果您沒有這些工具的複本，您可以從 Microsoft 下載它們。</span><span class="sxs-lookup"><span data-stu-id="fff59-134">If you do not have a copy of the tools, you can download them from Microsoft.</span></span> <span data-ttu-id="fff59-135">[下載] 頁面的下列連結是在 [嚮導] 中提供：[下載並安裝 Windows 的調試工具](https://go.microsoft.com/fwlink/?LinkId=99934)。</span><span class="sxs-lookup"><span data-stu-id="fff59-135">The following link to the download page is provided in the wizard: [Download and Install Debugging Tools for Windows](https://go.microsoft.com/fwlink/?LinkId=99934).</span></span>

<span data-ttu-id="fff59-136">您可以在執行**DaRT 復原映射嚮導**的電腦上指定調試工具的位置，也可以決定使用位於目的地電腦上的工具。</span><span class="sxs-lookup"><span data-stu-id="fff59-136">You can either specify the location of the debugging tools on the computer where you are running the **DaRT Recovery Image Wizard**, or you can decide to use the tools that are located on the destination computer.</span></span> <span data-ttu-id="fff59-137">如果您決定要在另一部電腦上使用複本，您必須確認在您要診斷系統崩潰的每一台電腦上都安裝了這些工具。</span><span class="sxs-lookup"><span data-stu-id="fff59-137">If you decide to use a copy on another computer, you must make sure that the tools are installed on each computer on which you are diagnosing a crash.</span></span>

<span data-ttu-id="fff59-138">**記事** 如果您在 ISO 映像中包含了 [當機]**故障分析器**，我們建議您同時包含 Windows 的調試工具。</span><span class="sxs-lookup"><span data-stu-id="fff59-138">**Note** If you include the **Crash Analyzer** in the ISO image, we recommend that you also include the Debugging Tools for Windows.</span></span>

 

<span data-ttu-id="fff59-139">請依照下列步驟來新增適用于 Windows 的調試工具：</span><span class="sxs-lookup"><span data-stu-id="fff59-139">Follow these steps to add the Debugging Tools for Windows:</span></span>

1.  <span data-ttu-id="fff59-140">可選按一下超連結以下載適用于 Windows 的調試工具。</span><span class="sxs-lookup"><span data-stu-id="fff59-140">(Optional) Click the hyperlink to download the Debugging Tools for Windows.</span></span>

2.  <span data-ttu-id="fff59-141">選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="fff59-141">Select one of the following options:</span></span>

    -   <span data-ttu-id="fff59-142">**在下列位置使用 Windows 版調試工具**。</span><span class="sxs-lookup"><span data-stu-id="fff59-142">**Use the Debugging Tools for Windows in the following location**.</span></span> <span data-ttu-id="fff59-143">如果您選取此選項，您可以流覽至工具的位置。</span><span class="sxs-lookup"><span data-stu-id="fff59-143">If you select this option, you can browse to the location of the tools.</span></span>

    -   <span data-ttu-id="fff59-144">在**您要修復的系統上，找到 [Windows 版調試工具**]。</span><span class="sxs-lookup"><span data-stu-id="fff59-144">**Locate the Debugging Tools for Windows on the system that you are repairing**.</span></span> <span data-ttu-id="fff59-145">如果您選取這個選項，在問題電腦上找不到 Windows 版調試工具時，系統會無法使用 [**崩潰分析**程式]。</span><span class="sxs-lookup"><span data-stu-id="fff59-145">If you select this option, the **Crash Analyzer** will not work if the Debugging Tools for Windows are not found on the problem computer.</span></span>

3.  <span data-ttu-id="fff59-146">完成之後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="fff59-146">After you have finished, click **Next**.</span></span>

### <span data-ttu-id="fff59-147">在 DaRT 恢復影像中新增獨立系統 Sweeper 的定義</span><span class="sxs-lookup"><span data-stu-id="fff59-147">To add definitions for Standalone System Sweeper to the DaRT recovery image</span></span>

<span data-ttu-id="fff59-148">[定義] 是已知惡意程式碼及其他可能不需要的軟體的儲存庫。</span><span class="sxs-lookup"><span data-stu-id="fff59-148">Definitions are a repository of known malware and other potentially unwanted software.</span></span> <span data-ttu-id="fff59-149">由於惡意程式碼正持續開發，所以**獨立系統 Sweeper**會根據目前的定義來判斷要在電腦上安裝、執行或變更電腦上的軟體是否可能有害或惡意軟體。</span><span class="sxs-lookup"><span data-stu-id="fff59-149">Because malware is being continually developed, **Standalone System Sweeper** relies on current definitions to determine whether software that is trying to install, run, or change settings on a computer is potentially unwanted or malicious software.</span></span>

<span data-ttu-id="fff59-150">若要在 DaRT 復原影像中包含最新定義（建議使用），請按一下 **[是，下載最新的定義]。**</span><span class="sxs-lookup"><span data-stu-id="fff59-150">To include the latest definitions in the DaRT recovery image (recommended), click **Yes, download the latest definitions.**</span></span> <span data-ttu-id="fff59-151">定義更新會自動啟動。</span><span class="sxs-lookup"><span data-stu-id="fff59-151">The definition update starts automatically.</span></span> <span data-ttu-id="fff59-152">您必須連線至網際網路，才能完成這個程式。</span><span class="sxs-lookup"><span data-stu-id="fff59-152">You must be connected to the Internet to complete this process.</span></span>

<span data-ttu-id="fff59-153">若要略過定義更新，請按一下 [**否，稍後手動下載定義**]。</span><span class="sxs-lookup"><span data-stu-id="fff59-153">To skip the definition update, click **No, manually download definitions later**.</span></span> <span data-ttu-id="fff59-154">在 DaRT 復原映像中不會包含定義。</span><span class="sxs-lookup"><span data-stu-id="fff59-154">Definitions will not be included in the DaRT recovery image.</span></span>

<span data-ttu-id="fff59-155">如果您決定不在復原映射中包含最新的定義，或者，如果您準備好要使用**獨立系統 Sweeper**，請在開始掃描前先按照**獨立系統 Sweeper**中提供的指示，取得最新的定義。</span><span class="sxs-lookup"><span data-stu-id="fff59-155">If you decide not to include the latest definitions on the recovery image, or if the definitions included on the recovery image are no longer current by the time that you are ready to use **Standalone System Sweeper**, obtain the latest definitions before you begin a scan by following the instructions that are provided in the **Standalone System Sweeper**.</span></span>

<span data-ttu-id="fff59-156">**重要** 如果沒有任何定義，您就無法進行掃描。</span><span class="sxs-lookup"><span data-stu-id="fff59-156">**Important** You cannot scan if there are no definitions.</span></span>

 

<span data-ttu-id="fff59-157">完成之後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="fff59-157">After you have finished, click **Next**.</span></span>

### <span data-ttu-id="fff59-158">在 DaRT 復原影像中新增驅動程式</span><span class="sxs-lookup"><span data-stu-id="fff59-158">To add drivers to the DaRT recovery image</span></span>

<span data-ttu-id="fff59-159">**小心** 根據預設，當您將驅動程式新增至 DaRT 復原影像時，位於該資料夾中的所有其他檔案和子資料夾都會新增到復原影像中。</span><span class="sxs-lookup"><span data-stu-id="fff59-159">**Caution** By default, when you add a driver to the DaRT recovery image, all additional files and subfolders that are located in that folder are added into the recovery image.</span></span> <span data-ttu-id="fff59-160">如需詳細資訊，請參閱[DaRT 7.0 疑難排解](troubleshooting-dart-70-new-ia.md)。</span><span class="sxs-lookup"><span data-stu-id="fff59-160">For more information, see [Troubleshooting DaRT 7.0](troubleshooting-dart-70-new-ia.md).</span></span>

 

<span data-ttu-id="fff59-161">您應該將其他驅動程式包含在修復電腦上可能需要的 DaRT7。</span><span class="sxs-lookup"><span data-stu-id="fff59-161">You should include additional drivers on the recovery image for DaRT7 that you may need when repairing a computer.</span></span> <span data-ttu-id="fff59-162">這些通常包括 Windows DVD 中不包含的儲存空間或網路控制器。</span><span class="sxs-lookup"><span data-stu-id="fff59-162">These may typically include storage or network controllers that are not included on the Windows DVD.</span></span>

<span data-ttu-id="fff59-163">**重要** 當您選取要包含的驅動程式時，請注意，DaRT 不支援無線連線（例如藍牙或 802.11 a/b/n）。</span><span class="sxs-lookup"><span data-stu-id="fff59-163">**Important** When you select drivers to include, be aware that wireless connectivity (such as Bluetooth or 802.11a/b/g/n) is not supported in DaRT.</span></span>

 

**<span data-ttu-id="fff59-164">在恢復影像中新增儲存空間或網路控制器驅動程式</span><span class="sxs-lookup"><span data-stu-id="fff59-164">To add a storage or network controller driver to the recovery image</span></span>**

1.  <span data-ttu-id="fff59-165">在**DaRT 復原映像嚮導**的 [**其他驅動程式**] 對話方塊中，按一下 [**新增裝置**]。</span><span class="sxs-lookup"><span data-stu-id="fff59-165">In the **Additional Drivers** dialog box of the **DaRT Recovery Image Wizard**, click **Add Device**.</span></span>

2.  <span data-ttu-id="fff59-166">流覽至要新增的驅動程式檔案，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="fff59-166">Browse to the file to be added for the driver, and then click **Open**.</span></span>

    <span data-ttu-id="fff59-167">**記事** **驅動程式**檔案是由儲存空間或網路控制器的製造商所提供。</span><span class="sxs-lookup"><span data-stu-id="fff59-167">**Note** The **driver** file is provided by the manufacturer of the storage or network controller.</span></span>

     

3.  <span data-ttu-id="fff59-168">針對您要加入的每個驅動程式，重複步驟1和2。</span><span class="sxs-lookup"><span data-stu-id="fff59-168">Repeat Steps 1 and 2 for every driver that you want to include.</span></span>

4.  <span data-ttu-id="fff59-169">完成之後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="fff59-169">After you have finished, click **Next**.</span></span>

### <span data-ttu-id="fff59-170">將檔案新增至 DaRT 恢復影像</span><span class="sxs-lookup"><span data-stu-id="fff59-170">To add files to the DaRT recovery image</span></span>

<span data-ttu-id="fff59-171">請依照這些步驟將檔案新增到復原影像，讓您可以使用這些檔案來診斷電腦問題。</span><span class="sxs-lookup"><span data-stu-id="fff59-171">Follow these steps to add files to the recovery image so that you can use them to diagnose computer problems.</span></span>

1.  <span data-ttu-id="fff59-172">在**DaRT 復原影像嚮導**的 [**其他**檔案] 對話方塊中，按一下 [**顯示**檔案]。</span><span class="sxs-lookup"><span data-stu-id="fff59-172">In the **Additional Files** dialog box of the **DaRT Recovery Image Wizard**, click **Show Files**.</span></span> <span data-ttu-id="fff59-173">這會開啟一個資源管理器視窗，其中會顯示存放共用檔案的資料夾。</span><span class="sxs-lookup"><span data-stu-id="fff59-173">This opens an Explorer window that displays the folder that holds the shared files.</span></span>

2.  <span data-ttu-id="fff59-174">在對話方塊中所列的資料夾中建立子資料夾。</span><span class="sxs-lookup"><span data-stu-id="fff59-174">Create a subfolder in the folder that is listed in the dialog box.</span></span>

3.  <span data-ttu-id="fff59-175">將您想要的檔案複製到新的子資料夾。</span><span class="sxs-lookup"><span data-stu-id="fff59-175">Copy the files that you want to the new subfolder.</span></span>

4.  <span data-ttu-id="fff59-176">完成之後，請按 **[下一步]。**</span><span class="sxs-lookup"><span data-stu-id="fff59-176">After you have finished, click **Next.**</span></span>

### <span data-ttu-id="fff59-177">若要選取包含 DaRT 復原影像之 ISO 的位置</span><span class="sxs-lookup"><span data-stu-id="fff59-177">To select a location for the ISO that contains the DaRT recovery image</span></span>

<span data-ttu-id="fff59-178">請依照下列步驟，指定建立 ISO 影像的位置：</span><span class="sxs-lookup"><span data-stu-id="fff59-178">Follow these steps to specify the location where the ISO image is created:</span></span>

1.  <span data-ttu-id="fff59-179">在**DaRT 復原映像嚮導**的 [**建立啟動影像**] 對話方塊中，按一下 **[流覽]**。</span><span class="sxs-lookup"><span data-stu-id="fff59-179">In the **Create Startup Image** dialog box of the **DaRT Recovery Image Wizard**, click **Browse**.</span></span>

2.  <span data-ttu-id="fff59-180">流覽至 [**另存**新檔] 視窗中的喜好位置，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="fff59-180">Browse to the preferred location in the **Save As** window, and then click **Save**.</span></span>

3.  <span data-ttu-id="fff59-181">完成之後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="fff59-181">After you have finished, click **Next**.</span></span>

<span data-ttu-id="fff59-182">根據您所選取的工具和您在嚮導中新增的檔案而定，ISO 影像的大小會有所不同。</span><span class="sxs-lookup"><span data-stu-id="fff59-182">The size of the ISO image will vary, depending on the tools that you select and the files that you add in the wizard.</span></span>

<span data-ttu-id="fff59-183">此嚮導需要 ISO 影像的副檔名為 **.iso** ，因為燒錄 CD 或 DVD 的大多數程式都需要該副檔名。</span><span class="sxs-lookup"><span data-stu-id="fff59-183">The wizard requires the ISO image to have an **.iso** file name extension because most programs that burn a CD or DVD require that extension.</span></span> <span data-ttu-id="fff59-184">如果您沒有指定其他位置，則會在您的桌上型電腦上使用名稱**DaRT70**建立 iso 影像。</span><span class="sxs-lookup"><span data-stu-id="fff59-184">If you do not specify a different location, the ISO image is created on your desktop with the name **DaRT70.ISO**.</span></span>

### <span data-ttu-id="fff59-185">將復原影像燒制到 CD 或 DVD</span><span class="sxs-lookup"><span data-stu-id="fff59-185">To burn the recovery image to a CD or DVD</span></span>

<span data-ttu-id="fff59-186">如果**DaRT 復原影像嚮導**在您的電腦上偵測到一個相容的 cd-rw 磁片磁碟機，就能讓您將 ISO 影像燒錄到光碟。</span><span class="sxs-lookup"><span data-stu-id="fff59-186">If the **DaRT Recovery Image Wizard** detects a compatible CD-RW drive on your computer, it offers to burn the ISO image to a disc for you.</span></span> <span data-ttu-id="fff59-187">如果您想要燒錄 CD 或 DVD，且嚮導無法辨識您的磁片磁碟機，您必須使用另一個程式，例如您的磁片磁碟機隨附的程式。</span><span class="sxs-lookup"><span data-stu-id="fff59-187">If you want to burn a CD or DVD and the wizard does not recognize your drive, you must use another program, such as the program that was included with your drive.</span></span> <span data-ttu-id="fff59-188">您可以使用 duplicator、複製服務或 CD 或 DVD 燒錄軟體來製作任何其他複本。</span><span class="sxs-lookup"><span data-stu-id="fff59-188">You can use a duplicator, a duplicating service, or CD or DVD-burning software to make any additional copies.</span></span>

1.  <span data-ttu-id="fff59-189">在 [**燒錄至可錄製的 cd/dvd** ] 對話方塊的 [ **DaRT 恢復影像] 嚮導**中，選取 [**將影像燒制至下列可錄製的 cd/dvd 磁碟機**]。</span><span class="sxs-lookup"><span data-stu-id="fff59-189">In the **Burn to a recordable CD/DVD** dialog box of the **DaRT Recovery Image Wizard**, select **Burn the image to the following recordable CD/DVD drive**.</span></span>

2.  <span data-ttu-id="fff59-190">選取 CD 或 DVD 磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="fff59-190">Select the CD or DVD drive.</span></span>

    <span data-ttu-id="fff59-191">**記事** 如果無法辨識某個磁片磁碟機，且您安裝了新的磁片磁碟機，您可以按一下 [重新整理**磁片磁碟機清單**]，強制嚮導更新可用磁片磁碟機清單。</span><span class="sxs-lookup"><span data-stu-id="fff59-191">**Note** If a drive is not recognized and you install a new drive, you can click **Refresh Drive List** to force the wizard to update the list of available drives.</span></span>

     

3.  <span data-ttu-id="fff59-192">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="fff59-192">Click **Next**.</span></span>

## <span data-ttu-id="fff59-193">相關主題</span><span class="sxs-lookup"><span data-stu-id="fff59-193">Related topics</span></span>


[<span data-ttu-id="fff59-194">建立 DaRT 7.0 復原映像</span><span class="sxs-lookup"><span data-stu-id="fff59-194">Creating the DaRT 7.0 Recovery Image</span></span>](creating-the-dart-70-recovery-image-dart-7.md)

 

 





