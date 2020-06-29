---
title: 建立 DaRT 8.0 復原映像
description: 建立 DaRT 8.0 復原映像
author: dansimp
ms.assetid: 39001b8e-86c0-45ef-8f34-2d6199f9922d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/21/2017
ms.openlocfilehash: 79ce5859e7d0eacf95124c2a7409ff6c21890d65
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800122"
---
# <span data-ttu-id="fcd72-103">建立 DaRT 8.0 復原映像</span><span class="sxs-lookup"><span data-stu-id="fcd72-103">Creating the DaRT 8.0 Recovery Image</span></span>


<span data-ttu-id="fcd72-104">安裝 Microsoft Diagnostics 和恢復工具組（DaRT）8.0 之後，您會建立一個 DaRT 8.0 復原影像。</span><span class="sxs-lookup"><span data-stu-id="fcd72-104">After installing Microsoft Diagnostics and Recovery Toolset (DaRT) 8.0, you create a DaRT 8.0 recovery image.</span></span> <span data-ttu-id="fcd72-105">[恢復] 影像會啟動 Windows RE，您可以從這裡啟動 DaRT 工具。</span><span class="sxs-lookup"><span data-stu-id="fcd72-105">The recovery image starts Windows RE, from which you can then start the DaRT tools.</span></span> <span data-ttu-id="fcd72-106">您可以產生國際標準組織（ISO）檔案和 Windows Imaging 格式（WIM）影像。</span><span class="sxs-lookup"><span data-stu-id="fcd72-106">You can generate International Organization for Standardization (ISO) files and Windows Imaging Format (WIM) images.</span></span> <span data-ttu-id="fcd72-107">此外，您可以使用 PowerShell 來產生使用您在 DaRT 復原映像嚮導中所選取之設定的腳本。</span><span class="sxs-lookup"><span data-stu-id="fcd72-107">In addition, you can use PowerShell to generate scripts that use the settings you select in the DaRT Recovery Image wizard.</span></span> <span data-ttu-id="fcd72-108">您可以稍後使用此腳本，透過使用相同的設定來重建復原影像。</span><span class="sxs-lookup"><span data-stu-id="fcd72-108">You can use the script later to rebuild recovery images by using the same settings.</span></span> <span data-ttu-id="fcd72-109">復原影像提供各種不同的恢復工具。</span><span class="sxs-lookup"><span data-stu-id="fcd72-109">The recovery image provides a variety of recovery tools.</span></span> <span data-ttu-id="fcd72-110">如需工具的描述，請參閱[DaRT 8.0 中的工具概覽](overview-of-the-tools-in-dart-80-dart-8.md)。</span><span class="sxs-lookup"><span data-stu-id="fcd72-110">For a description of the tools, see [Overview of the Tools in DaRT 8.0](overview-of-the-tools-in-dart-80-dart-8.md).</span></span>

<span data-ttu-id="fcd72-111">將電腦引導至 DaRT 之後，您可以執行不同的 DaRT 工具來嘗試診斷並修復電腦。</span><span class="sxs-lookup"><span data-stu-id="fcd72-111">After you boot the computer into DaRT, you can run the different DaRT tools to try to diagnose and repair the computer.</span></span> <span data-ttu-id="fcd72-112">本節將引導您逐步完成建立 DaRT 復原影像的程式，並讓您選取要納入影像中的工具和功能。</span><span class="sxs-lookup"><span data-stu-id="fcd72-112">This section walks you through the process of creating the DaRT recovery image and lets you select the tools and features that you want to include as part of the image.</span></span>

<span data-ttu-id="fcd72-113">您可以使用下列兩種方法的其中一種來建立 DaRT 復原影像：</span><span class="sxs-lookup"><span data-stu-id="fcd72-113">You can create the DaRT recovery image by using either of two methods:</span></span>

-   <span data-ttu-id="fcd72-114">使用 DaRT 復原映射嚮導（在 Windows 環境中執行）。</span><span class="sxs-lookup"><span data-stu-id="fcd72-114">Use the DaRT Recovery Image wizard, which runs in a Windows environment.</span></span>

-   <span data-ttu-id="fcd72-115">使用您想要的值修改範例 PowerShell 腳本。</span><span class="sxs-lookup"><span data-stu-id="fcd72-115">Modify an example PowerShell script with the values you want.</span></span> <span data-ttu-id="fcd72-116">如需詳細資訊，請參閱[如何使用 PowerShell 腳本來建立恢復影像](how-to-use-a-powershell-script-to-create-the-recovery-image-dart-8.md)。</span><span class="sxs-lookup"><span data-stu-id="fcd72-116">For more information, see [How to Use a PowerShell Script to Create the Recovery Image](how-to-use-a-powershell-script-to-create-the-recovery-image-dart-8.md).</span></span>

<span data-ttu-id="fcd72-117">您可以將 ISO 寫入可錄製的 CD 或 DVD、將其儲存至 USB 快閃磁片磁碟機，或將它儲存為可從遠端分區或從復原分區引導至 DaRT 的格式。</span><span class="sxs-lookup"><span data-stu-id="fcd72-117">You can write the ISO to a recordable CD or DVD, save it to a USB flash drive, or save it in a format that you can use to boot into DaRT from a remote partition or from a recovery partition.</span></span>

<span data-ttu-id="fcd72-118">建立 ISO 影像之後，您可以將它燒錄到空白的 CD 或 DVD （如果您的電腦有 CD 或 DVD 磁片磁碟機）。</span><span class="sxs-lookup"><span data-stu-id="fcd72-118">Once you have created the ISO image, you can burn it onto a blank CD or DVD (if your computer has a CD or DVD drive).</span></span> <span data-ttu-id="fcd72-119">如果您的電腦沒有用於這種用途的磁片磁碟機，您可以使用大多數用來燒錄 Cd 或 Dvd 的一般程式。</span><span class="sxs-lookup"><span data-stu-id="fcd72-119">If your computer does not have a drive for this purpose, you can use most generic programs that are used to burn CDs or DVDs.</span></span>

## <span data-ttu-id="fcd72-120">選取影像架構並指定路徑</span><span class="sxs-lookup"><span data-stu-id="fcd72-120">Select the image architecture and specify the path</span></span>


<span data-ttu-id="fcd72-121">在 [Windows 8 媒體] 頁面上，您可以選取是否要建立32或64位的 DaRT 恢復影像。</span><span class="sxs-lookup"><span data-stu-id="fcd72-121">On the Windows 8 Media page, you select whether to create a 32-bit or 64-bit DaRT recovery image.</span></span> <span data-ttu-id="fcd72-122">使用32位 Windows 來建立32位的 DaRT 復原影像，以及64位的 Windows 來建立 64-位 DaRT 恢復影像。</span><span class="sxs-lookup"><span data-stu-id="fcd72-122">Use the 32-bit Windows to build 32-bit DaRT recovery images, and 64-bit Windows to build 64-bit DaRT recovery images.</span></span> <span data-ttu-id="fcd72-123">您可以使用單一電腦來為這兩種架構類型建立復原影像，但無法建立一個在32位與64位架構上都能運作的影像。</span><span class="sxs-lookup"><span data-stu-id="fcd72-123">You can use a single computer to create recovery images for both architecture types, but you cannot create one image that works on both 32-bit and 64-bit architectures.</span></span> <span data-ttu-id="fcd72-124">您也會指出 Windows 8 安裝媒體的路徑。</span><span class="sxs-lookup"><span data-stu-id="fcd72-124">You also indicate the path of the Windows 8 installation media.</span></span> <span data-ttu-id="fcd72-125">選擇與您要建立之其中一個恢復影像相符的架構。</span><span class="sxs-lookup"><span data-stu-id="fcd72-125">Choose the architecture that matches the one of the recovery image that you are creating.</span></span>

**<span data-ttu-id="fcd72-126">選取影像架構並指定路徑</span><span class="sxs-lookup"><span data-stu-id="fcd72-126">To select the image architecture and specify the path</span></span>**

1.  <span data-ttu-id="fcd72-127">在 [ **Windows 8 媒體**] 頁面上，選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="fcd72-127">On the **Windows 8 Media** page, select one of the following:</span></span>

    -   <span data-ttu-id="fcd72-128">如果您要建立64位電腦的復原影像，請選取 **[建立 x64 （64位） DaRT 影像**]。</span><span class="sxs-lookup"><span data-stu-id="fcd72-128">If you are creating a recovery image for 64-bit computers, select **Create x64 (64-bit) DaRT image**.</span></span>

    -   <span data-ttu-id="fcd72-129">如果您要建立32位電腦的復原影像，請選取 **[建立 x86 （32位） DaRT 影像**]。</span><span class="sxs-lookup"><span data-stu-id="fcd72-129">If you are creating a recovery image for 32-bit computers, select **Create x86 (32-bit) DaRT image**.</span></span>

2.  <span data-ttu-id="fcd72-130">在 [**指定 windows 8 &lt; 64 位或32位 &gt; 安裝媒體的根路徑**] 方塊中，輸入 Windows 8 安裝檔的路徑。</span><span class="sxs-lookup"><span data-stu-id="fcd72-130">In the **Specify the root path of the Windows 8 &lt;64-bit or 32-bit&gt; install media** box, type the path of the Windows 8 installation files.</span></span> <span data-ttu-id="fcd72-131">使用與您要建立之復原影像之體系結構相符的路徑。</span><span class="sxs-lookup"><span data-stu-id="fcd72-131">Use a path that matches the architecture of the recovery image that you are creating.</span></span>

3.  <span data-ttu-id="fcd72-132">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="fcd72-132">Click **Next**.</span></span>

## <span data-ttu-id="fcd72-133">選取要納入恢復影像的工具</span><span class="sxs-lookup"><span data-stu-id="fcd72-133">Select the tools to include on the recovery image</span></span>


<span data-ttu-id="fcd72-134">在 [工具] 頁面上，您可以選取要包含在復原影像上的多個工具。</span><span class="sxs-lookup"><span data-stu-id="fcd72-134">On the Tools page, you can select numerous tools to include on the recovery image.</span></span> <span data-ttu-id="fcd72-135">當使用者引導進入 DaRT 影像時，這些工具就會提供給使用者使用。</span><span class="sxs-lookup"><span data-stu-id="fcd72-135">These tools will be available to end users when they boot into the DaRT image.</span></span> <span data-ttu-id="fcd72-136">不過，如果您在建立 DaRT 影像時啟用遠端連線，不論您選擇要在影像中包含哪些工具，都能在支援中心工作人員連線至最終使用者的電腦時，提供所有工具。</span><span class="sxs-lookup"><span data-stu-id="fcd72-136">However, if you enable remote connectivity when creating the DaRT image, all of the tools will be available when a help desk worker connects to the end user’s computer, regardless of which tools you chose to include on the image.</span></span>

<span data-ttu-id="fcd72-137">若要限制使用者存取這些工具，但仍保留透過遠端連線檢視器對工具的完整存取權，請不要在 [工具] 頁面上選取這些工具。</span><span class="sxs-lookup"><span data-stu-id="fcd72-137">To restrict end-user access to these tools, but still retain full access to the tools through the Remote Connection Viewer, do not select those tools on the Tools page.</span></span> <span data-ttu-id="fcd72-138">最終使用者將只能使用遠端連線，而且將能夠看到您從復原影像排除的任何工具，但無法存取。</span><span class="sxs-lookup"><span data-stu-id="fcd72-138">End users will be able to use only Remote Connection and will be able to see, but not access, any tools that you exclude from the recovery image.</span></span>

**<span data-ttu-id="fcd72-139">選取要納入恢復影像的工具</span><span class="sxs-lookup"><span data-stu-id="fcd72-139">To select the tools to include on the recovery image</span></span>**

1.  <span data-ttu-id="fcd72-140">在 [**工具**] 頁面上，選取您要包含在影像中的每個工具旁的核取方塊。</span><span class="sxs-lookup"><span data-stu-id="fcd72-140">On the **Tools** page, select the check box beside each tool that you want to include on the image.</span></span>

2.  <span data-ttu-id="fcd72-141">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="fcd72-141">Click **Next**.</span></span>

## <span data-ttu-id="fcd72-142">選擇是否允許由技術支援人員進行遠端連線</span><span class="sxs-lookup"><span data-stu-id="fcd72-142">Choose whether to allow remote connectivity by a help desk</span></span>


<span data-ttu-id="fcd72-143">在 [遠端連線] 頁面上，您可以選擇讓技術支援人員在最終使用者的電腦上遠端連線到並執行 DaRT 工具。</span><span class="sxs-lookup"><span data-stu-id="fcd72-143">On the Remote Connection page, you can choose to enable a help desk worker to remotely connect to and run the DaRT tools on an end user’s computer.</span></span> <span data-ttu-id="fcd72-144">[遠端連線] 選項會在 [診斷與修復工具組] 視窗中顯示為可用的選項。</span><span class="sxs-lookup"><span data-stu-id="fcd72-144">The remote connectivity option is then shown as an available option in the Diagnostics and Recovery Toolset window.</span></span> <span data-ttu-id="fcd72-145">技術支援人員建立遠端連線之後，就可以從遠端位置，在最終使用者電腦上執行 DaRT 工具。</span><span class="sxs-lookup"><span data-stu-id="fcd72-145">After help desk workers establish a remote connection, they can run the DaRT tools on the end-user computer from a remote location.</span></span>

**<span data-ttu-id="fcd72-146">若要選擇是否允許由技術支援人員進行遠端連線</span><span class="sxs-lookup"><span data-stu-id="fcd72-146">To choose whether to allow remote connectivity by help desk workers</span></span>**

1.  <span data-ttu-id="fcd72-147">在 [**遠端**連線] 頁面上，選取 [**允許遠端**連線] 核取方塊以允許遠端連線，或清除該核取方塊以防止遠端連線。</span><span class="sxs-lookup"><span data-stu-id="fcd72-147">On the **Remote Connection** page, select the **Allow remote connections** check box to allow remote connections, or clear the check box to prevent remote connections.</span></span>

2.  <span data-ttu-id="fcd72-148">如果您已清除 [**允許遠端**連線] 核取方塊，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="fcd72-148">If you cleared the **Allow remote connections** check box, click **Next**.</span></span> <span data-ttu-id="fcd72-149">否則，請移至下一個步驟，繼續設定遠端連線。</span><span class="sxs-lookup"><span data-stu-id="fcd72-149">Otherwise, go to the next step to continue configuring remote connectivity.</span></span>

3.  <span data-ttu-id="fcd72-150">選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="fcd72-150">Select one of the following:</span></span>

    -   <span data-ttu-id="fcd72-151">讓 Windows 選擇開啟的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="fcd72-151">Let Windows choose an open port number.</span></span>

    -   <span data-ttu-id="fcd72-152">指定埠號碼。</span><span class="sxs-lookup"><span data-stu-id="fcd72-152">Specify the port number.</span></span> <span data-ttu-id="fcd72-153">如果您選取此選項，請在選項下方的欄位中輸入1到65535之間的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="fcd72-153">If you select this option, enter a port number between 1 and 65535 in the field beneath the option.</span></span> <span data-ttu-id="fcd72-154">建立遠端連線時，會用到這個埠號碼。</span><span class="sxs-lookup"><span data-stu-id="fcd72-154">This port number will be used when establishing a remote connection.</span></span> <span data-ttu-id="fcd72-155">建議將埠號碼設為1024或更高，以將衝突可能性降至最低。</span><span class="sxs-lookup"><span data-stu-id="fcd72-155">We recommend that the port number be 1024 or higher to minimize the possibility of a conflict.</span></span>

4.  <span data-ttu-id="fcd72-156">（選擇性）在 [**遠端連線歡迎**訊息] 方塊中，建立最終使用者建立遠端連線時接收的自訂訊息。</span><span class="sxs-lookup"><span data-stu-id="fcd72-156">(Optional) in the **Remote connection welcome** message box, create a customized message that end users receive when they establish a remote connection.</span></span> <span data-ttu-id="fcd72-157">訊息最多可以為2048個字元。</span><span class="sxs-lookup"><span data-stu-id="fcd72-157">The message can be a maximum of 2048 characters.</span></span>

5.  <span data-ttu-id="fcd72-158">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="fcd72-158">Click **Next**.</span></span>

    <span data-ttu-id="fcd72-159">如需遠端執行 DaRT 工具的詳細資訊，請參閱[如何使用 DaRT 復原影像來復原遠端電腦](how-to-recover-remote-computers-by-using-the-dart-recovery-image-dart-8.md)。</span><span class="sxs-lookup"><span data-stu-id="fcd72-159">For more information about running the DaRT tools remotely, see [How to Recover Remote Computers by Using the DaRT Recovery Image](how-to-recover-remote-computers-by-using-the-dart-recovery-image-dart-8.md).</span></span>

## <span data-ttu-id="fcd72-160">在恢復影像中新增驅動程式</span><span class="sxs-lookup"><span data-stu-id="fcd72-160">Add drivers to the recovery image</span></span>


<span data-ttu-id="fcd72-161">在 [高級選項] 頁面的 [驅動程式] 索引標籤上，您可以新增修復電腦時可能需要的其他裝置驅動程式。</span><span class="sxs-lookup"><span data-stu-id="fcd72-161">On the Drivers tab of the Advanced Options page, you can add additional device drivers that you may need when repairing a computer.</span></span> <span data-ttu-id="fcd72-162">這些通常會包含 Windows 8 不提供的儲存空間或網路控制器。</span><span class="sxs-lookup"><span data-stu-id="fcd72-162">These may typically include storage or network controllers that Windows 8 does not provide.</span></span> <span data-ttu-id="fcd72-163">在建立影像時會安裝驅動程式。</span><span class="sxs-lookup"><span data-stu-id="fcd72-163">Drivers are installed when the image is created.</span></span>

<span data-ttu-id="fcd72-164">**重要** 當您選取要包含的驅動程式時，請注意，DaRT 不支援無線連線（例如藍牙或 802.11 a/b/n）。</span><span class="sxs-lookup"><span data-stu-id="fcd72-164">**Important** When you select drivers to include, be aware that wireless connectivity (such as Bluetooth or 802.11a/b/g/n) is not supported in DaRT.</span></span>

 

**<span data-ttu-id="fcd72-165">在恢復影像中新增驅動程式</span><span class="sxs-lookup"><span data-stu-id="fcd72-165">To add drivers to the recovery image</span></span>**

1.  <span data-ttu-id="fcd72-166">在 [**高級選項**] 頁面上，按一下 [**驅動程式**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="fcd72-166">On the **Advanced Options** page, click the **Drivers** tab.</span></span>

2.  <span data-ttu-id="fcd72-167">按一下**新增**。</span><span class="sxs-lookup"><span data-stu-id="fcd72-167">Click **Add**.</span></span>

3.  <span data-ttu-id="fcd72-168">流覽至要新增的驅動程式檔案，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="fcd72-168">Browse to the file to be added for the driver, and then click **Open**.</span></span>

    <span data-ttu-id="fcd72-169">**記事** 驅動程式檔案是由儲存空間或網路控制器的製造商所提供。</span><span class="sxs-lookup"><span data-stu-id="fcd72-169">**Note** The driver file is provided by the manufacturer of the storage or network controller.</span></span>

     

4.  <span data-ttu-id="fcd72-170">針對您要加入的每個驅動程式，重複步驟2和3。</span><span class="sxs-lookup"><span data-stu-id="fcd72-170">Repeat Steps 2 and 3 for every driver that you want to include.</span></span>

5.  <span data-ttu-id="fcd72-171">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="fcd72-171">Click **Next**.</span></span>

## <span data-ttu-id="fcd72-172">將 WinPE 選用套件新增到復原影像</span><span class="sxs-lookup"><span data-stu-id="fcd72-172">Add WinPE optional packages to the recovery image</span></span>


<span data-ttu-id="fcd72-173">在 [高級選項] 頁面的 [WinPE] 索引標籤上，您可以將 WinPE 選用套件新增至 DaRT 映射。</span><span class="sxs-lookup"><span data-stu-id="fcd72-173">On the WinPE tab of the Advanced Options page, you can add WinPE optional packages to the DaRT image.</span></span> <span data-ttu-id="fcd72-174">這些套件是 Windows ADK 的一部分，這是 DaRT 復原映像嚮導的安裝先決條件。</span><span class="sxs-lookup"><span data-stu-id="fcd72-174">These packages are part of the Windows ADK, which is an installation prerequisite for the DaRT Recovery Image wizard.</span></span> <span data-ttu-id="fcd72-175">您可以選取的工具全都是選用的。</span><span class="sxs-lookup"><span data-stu-id="fcd72-175">The tools that you can select are all optional.</span></span> <span data-ttu-id="fcd72-176">系統會根據您在 [工具] 頁面上選取的工具，自動新增任何所需的套件。</span><span class="sxs-lookup"><span data-stu-id="fcd72-176">Any required packages are added automatically, based on the tools you selected on the Tools page.</span></span>

<span data-ttu-id="fcd72-177">您也可以指定暫存空間的大小。</span><span class="sxs-lookup"><span data-stu-id="fcd72-177">You can also specify the size of the scratch space.</span></span> <span data-ttu-id="fcd72-178">[暫存空間] 是指為執行 DaRT 所設定的 RAM 磁碟空間量。</span><span class="sxs-lookup"><span data-stu-id="fcd72-178">Scratch space is the amount of RAM disk space that is set aside for DaRT to run.</span></span> <span data-ttu-id="fcd72-179">如果使用者無法使用使用者的硬碟，暫存空間就很有用。</span><span class="sxs-lookup"><span data-stu-id="fcd72-179">The scratch space is useful in case the end user’s hard disk is not available.</span></span> <span data-ttu-id="fcd72-180">如果您正在執行其他工具和驅動程式，您可能會想要增加暫存空間。</span><span class="sxs-lookup"><span data-stu-id="fcd72-180">If you are running additional tools and drivers, you may want to increase the scratch space.</span></span>

**<span data-ttu-id="fcd72-181">將 WinPE 選用套件新增到復原影像</span><span class="sxs-lookup"><span data-stu-id="fcd72-181">To add WinPE optional packages to the recovery image</span></span>**

1.  <span data-ttu-id="fcd72-182">在 [**高級選項**] 頁面上，按一下 [ **WinPE** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="fcd72-182">On the **Advanced Options** page, click the **WinPE** tab.</span></span>

2.  <span data-ttu-id="fcd72-183">選取您要包含在影像中的每個套件旁的核取方塊，或按一下 [**名稱**] 核取方塊以選取所有套件。</span><span class="sxs-lookup"><span data-stu-id="fcd72-183">Select the check box beside each package that you want to include on the image, or click the **Name** check box to select all of the packages.</span></span>

3.  <span data-ttu-id="fcd72-184">在 [**暫存空間**] 欄位中，選取要為執行 DaRT 指派的 RAM 磁碟空間量（如果最終使用者的硬碟無法使用）。</span><span class="sxs-lookup"><span data-stu-id="fcd72-184">In the **Scratch Space** field, select the amount of RAM disk space to allocate for running DaRT in case the end user’s hard disk is not available.</span></span>

4.  <span data-ttu-id="fcd72-185">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="fcd72-185">Click **Next**.</span></span>

## <span data-ttu-id="fcd72-186">新增故障分析程式的調試工具</span><span class="sxs-lookup"><span data-stu-id="fcd72-186">Add the debugging tools for Crash Analyzer</span></span>


<span data-ttu-id="fcd72-187">如果您在 ISO 映像中包含 [崩潰分析程式] 工具，您也必須包含適用于 Windows 的調試工具。</span><span class="sxs-lookup"><span data-stu-id="fcd72-187">If you include the Crash Analyzer tool in the ISO image, you must also include the Debugging Tools for Windows.</span></span> <span data-ttu-id="fcd72-188">在 [高級選項] 頁面的 [崩潰分析器] 索引標籤上，您可以輸入 Windows 8 調試工具的路徑，這些工具會讓 Analyzer 用來分析記憶體傾印檔案。</span><span class="sxs-lookup"><span data-stu-id="fcd72-188">On the Crash Analyzer tab of the Advanced Options page, you enter the path of the Windows 8 Debugging Tools, which Crash Analyzer uses to analyze memory dump files.</span></span> <span data-ttu-id="fcd72-189">您可以使用執行 DaRT 復原映射嚮導之電腦上的工具，或者您可以使用終端使用者電腦上的工具。</span><span class="sxs-lookup"><span data-stu-id="fcd72-189">You can use the tools that are on the computer where you are running the DaRT Recovery Image wizard, or you can use the tools that are on the end-user computer.</span></span> <span data-ttu-id="fcd72-190">如果您決定在最終使用者電腦上使用這些工具，請記住，您診斷的每個電腦都必須安裝調試工具。</span><span class="sxs-lookup"><span data-stu-id="fcd72-190">If you decide to use the tools on the end-user computer, remember that every computer that you diagnose must have the Debugging Tools installed.</span></span>

<span data-ttu-id="fcd72-191">如果您已安裝 Microsoft Windows 軟體發展工具組（SDK）或 Microsoft Windows 開發套件（WDK），則預設會將 Windows 8 調試工具新增到復原影像，且會自動填入調試工具的路徑。</span><span class="sxs-lookup"><span data-stu-id="fcd72-191">If you installed the Microsoft Windows Software Development Kit (SDK) or the Microsoft Windows Development Kit (WDK), the Windows 8 Debugging Tools are added to the recovery image by default, and the path to the Debugging Tools is automatically filled in.</span></span> <span data-ttu-id="fcd72-192">如果檔案位於預設檔路徑所指示的位置以外的位置，您可以變更 Windows 8 調試工具的路徑。</span><span class="sxs-lookup"><span data-stu-id="fcd72-192">You can change the path of the Windows 8 Debugging Tools if the files are located somewhere other than the location indicated by the default file path.</span></span> <span data-ttu-id="fcd72-193">嚮導中的連結可讓您下載並安裝 Windows 版調試工具（如果尚未安裝）。</span><span class="sxs-lookup"><span data-stu-id="fcd72-193">A link in the wizard lets you download and install debugging tools for Windows if they are not already installed.</span></span>

<span data-ttu-id="fcd72-194">若要下載 Windows 調試工具，請參閱[windows 版調試工具](https://go.microsoft.com/fwlink/?LinkId=266248)。</span><span class="sxs-lookup"><span data-stu-id="fcd72-194">To download the Windows Debugging Tools, see [Debugging Tools for Windows](https://go.microsoft.com/fwlink/?LinkId=266248).</span></span> <span data-ttu-id="fcd72-195">將調試工具安裝到預設位置。</span><span class="sxs-lookup"><span data-stu-id="fcd72-195">Install the Debugging Tools to the default location.</span></span>

<span data-ttu-id="fcd72-196">**記事** DaRT 嚮導會檢查登錄機碼中的工具 `HKLM\Software\Microsoft\Windows Kits\Installed Roots\WindowsDebuggersRoot` 。</span><span class="sxs-lookup"><span data-stu-id="fcd72-196">**Note** The DaRT wizard checks for the tools in the `HKLM\Software\Microsoft\Windows Kits\Installed Roots\WindowsDebuggersRoot` registry key.</span></span> <span data-ttu-id="fcd72-197">如果沒有登錄值，嚮導會根據您的系統架構來尋找下列其中一個位置：</span><span class="sxs-lookup"><span data-stu-id="fcd72-197">If the registry value is not there, the wizard looks in one of the following locations, depending on your system architecture:</span></span>

`%ProgramFilesX86%\Windows Kits\8.0\Debuggers\x64`

`%ProgramFilesX86%\Windows Kits\8.0\Debuggers\x86`

 

**<span data-ttu-id="fcd72-198">新增故障分析程式的調試工具</span><span class="sxs-lookup"><span data-stu-id="fcd72-198">To add the debugging tools for Crash Analyzer</span></span>**

1.  <span data-ttu-id="fcd72-199">按一下 [**高級選項**] 頁面上的 [**崩潰分析**程式] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="fcd72-199">On the **Advanced Options** page, click the **Crash Analyzer** tab.</span></span>

2.  <span data-ttu-id="fcd72-200">可選按一下 **[下載調試工具**]，下載適用于 Windows 的調試工具。</span><span class="sxs-lookup"><span data-stu-id="fcd72-200">(Optional) Click **Download the Debugging Tools** to download the Debugging Tools for Windows.</span></span>

3.  <span data-ttu-id="fcd72-201">選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="fcd72-201">Select one of the following options:</span></span>

    -   <span data-ttu-id="fcd72-202">**包含 Windows 8 &lt; 64 位或32位 &gt; 調試工具**。</span><span class="sxs-lookup"><span data-stu-id="fcd72-202">**Include the Windows 8 &lt;64-bit or 32-bit&gt; Debugging Tools**.</span></span> <span data-ttu-id="fcd72-203">如果您選取此選項，請流覽並選取工具的位置（如果路徑尚未顯示）。</span><span class="sxs-lookup"><span data-stu-id="fcd72-203">If you select this option, browse to and select the location of the tools if the path is not already displaying.</span></span>

    -   <span data-ttu-id="fcd72-204">**使用系統中正在調試的調試工具**。</span><span class="sxs-lookup"><span data-stu-id="fcd72-204">**Use the Debugging Tools from the system that is being debugged**.</span></span> <span data-ttu-id="fcd72-205">如果您選取這個選項，在問題電腦上找不到 Windows 版調試工具時，系統會無法使用 [崩潰分析程式]。</span><span class="sxs-lookup"><span data-stu-id="fcd72-205">If you select this option, the Crash Analyzer will not work if the Debugging Tools for Windows are not found on the problem computer.</span></span>

4.  <span data-ttu-id="fcd72-206">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="fcd72-206">Click **Next**.</span></span>

## <span data-ttu-id="fcd72-207">新增 Defender 工具的定義</span><span class="sxs-lookup"><span data-stu-id="fcd72-207">Add definitions for the Defender tool</span></span>


<span data-ttu-id="fcd72-208">在 [高級選項] 頁面的 [Defender] 索引標籤上，您可以新增定義，即由 Defender 工具用來判斷要在電腦上安裝、執行或變更電腦上的軟體是否為不需要或惡意的軟體。</span><span class="sxs-lookup"><span data-stu-id="fcd72-208">On the Defender tab of the Advanced Options page, you add definitions, which are used by the Defender tool to determine whether software that is trying to install, run, or change settings on a computer is unwanted or malicious software.</span></span>

**<span data-ttu-id="fcd72-209">新增 Defender 工具的定義</span><span class="sxs-lookup"><span data-stu-id="fcd72-209">To add definitions for the Defender tool</span></span>**

1.  <span data-ttu-id="fcd72-210">在 [**高級選項**] 頁面上，按一下 [ **Defender** ] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="fcd72-210">On the **Advanced Options** page, click the **Defender** tab.</span></span>

2.  <span data-ttu-id="fcd72-211">選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="fcd72-211">Select one of the following options:</span></span>

    -   <span data-ttu-id="fcd72-212">**下載最新的定義（建議使用）** -定義更新會自動開始，且定義會新增至 DaRT 復原影像。</span><span class="sxs-lookup"><span data-stu-id="fcd72-212">**Download the latest definitions (Recommended)** – The definition update starts automatically, and the definitions are added to the DaRT recovery image.</span></span> <span data-ttu-id="fcd72-213">建議使用此選項，以協助您避免定義可能無法使用的情況。</span><span class="sxs-lookup"><span data-stu-id="fcd72-213">This option is recommended to help you avoid cases where the definitions might not be available.</span></span> <span data-ttu-id="fcd72-214">您必須連線至網際網路，才能下載定義。</span><span class="sxs-lookup"><span data-stu-id="fcd72-214">You must be connected to the Internet to download the definitions.</span></span>

    -   <span data-ttu-id="fcd72-215">**稍後下載定義**-定義將不會包含在 dart 復原影像中，您將需要從執行 DaRT 的電腦下載定義。</span><span class="sxs-lookup"><span data-stu-id="fcd72-215">**Download the definitions later** – Definitions will not be included in the DaRT recovery image, and you will need to download the definitions from the computer that is running DaRT.</span></span>

        <span data-ttu-id="fcd72-216">如果您決定不在復原映射中包含最新定義，或者，如果您準備好要使用 Defender，請在開始掃描前先按照在 Defender 中提供的指示，取得最新的定義。</span><span class="sxs-lookup"><span data-stu-id="fcd72-216">If you decide not to include the latest definitions on the recovery image, or if the definitions included on the recovery image are no longer current by the time that you are ready to use Defender, obtain the latest definitions before you begin a scan by following the instructions that are provided in Defender.</span></span>

        <span data-ttu-id="fcd72-217">**重要** 如果沒有任何定義，您就無法進行掃描。</span><span class="sxs-lookup"><span data-stu-id="fcd72-217">**Important** You cannot scan if there are no definitions.</span></span>

         

3.  <span data-ttu-id="fcd72-218">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="fcd72-218">Click **Next**.</span></span>

## <span data-ttu-id="fcd72-219">選取要建立的復原圖像檔案類型</span><span class="sxs-lookup"><span data-stu-id="fcd72-219">Select the types of recovery image files to create</span></span>


<span data-ttu-id="fcd72-220">在 [建立影像] 頁面上，您可以為復原影像選擇輸出檔案夾，輸入影像名稱，然後選取要建立的 DaRT 復原影像檔案類型。</span><span class="sxs-lookup"><span data-stu-id="fcd72-220">On the Create Image page, you choose an output folder for the recovery image, enter an image name, and select the types of DaRT recovery image files to create.</span></span> <span data-ttu-id="fcd72-221">在恢復影像建立程式期間，會將 Windows 來源檔案解包、將 DaRT 檔案複製到該檔案，然後再將影像「重新封包」成您在此頁面上選取的檔案格式。</span><span class="sxs-lookup"><span data-stu-id="fcd72-221">During the recovery image creation process, Windows source files are unpacked, DaRT files are copied to it, and the image is then “re-packed” into the file formats that you select on this page.</span></span>

<span data-ttu-id="fcd72-222">可用的圖像檔案類型有：</span><span class="sxs-lookup"><span data-stu-id="fcd72-222">The available image file types are:</span></span>

-   <span data-ttu-id="fcd72-223">**Windows Imaging 檔案（WIM）** -用於將 DaRT 部署到開機前執行環境（PXE）或本機分區）。</span><span class="sxs-lookup"><span data-stu-id="fcd72-223">**Windows Imaging File (WIM)** - used to deploy DaRT to a preboot execution environment (PXE) or local partition).</span></span>

-   <span data-ttu-id="fcd72-224">**ISO 映像檔**-用來部署到 CD 或 DVD，或用於虛擬電腦（VM） s）。</span><span class="sxs-lookup"><span data-stu-id="fcd72-224">**ISO image file** – used to deploy to CD or DVD, or for use in virtual machines (VM)s).</span></span> <span data-ttu-id="fcd72-225">此嚮導要求 ISO 影像的副檔名為 .iso，因為燒錄 CD 或 DVD 的大多數程式都需要該副檔名。</span><span class="sxs-lookup"><span data-stu-id="fcd72-225">The wizard requires that the ISO image have an .iso file name extension because most programs that burn a CD or DVD require that extension.</span></span> <span data-ttu-id="fcd72-226">如果您沒有指定其他位置，則會在您的桌上型電腦上使用名稱 DaRT8 建立 ISO 影像。</span><span class="sxs-lookup"><span data-stu-id="fcd72-226">If you do not specify a different location, the ISO image is created on your desktop with the name DaRT8.ISO.</span></span>

-   <span data-ttu-id="fcd72-227">**PowerShell 腳本**–建立 dart 復原影像，其命令主要提供與您可以使用 DaRT 復原影像嚮導選取的選項。</span><span class="sxs-lookup"><span data-stu-id="fcd72-227">**PowerShell script** – creates a DaRT recovery image with commands that provide essentially the same options that you can select by using the DaRT Recovery Image wizard.</span></span> <span data-ttu-id="fcd72-228">此腳本也可讓您在 DaRT 恢復影像中新增或變更檔案。</span><span class="sxs-lookup"><span data-stu-id="fcd72-228">The script also enables you to add or changes files in the DaRT recovery image.</span></span>

<span data-ttu-id="fcd72-229">如果您在此頁面上選取 [編輯影像] 核取方塊，您可以在影像建立過程中自訂復原影像。</span><span class="sxs-lookup"><span data-stu-id="fcd72-229">If you select the Edit Image check box on this page, you can customize the recovery image during the image creation process.</span></span> <span data-ttu-id="fcd72-230">例如，您可以變更「winpeshl.ini」檔案以建立自訂啟動順序或新增協力廠商工具。</span><span class="sxs-lookup"><span data-stu-id="fcd72-230">For example, you can change the “winpeshl.ini” file to create a custom startup order or to add third-party tools.</span></span>

**<span data-ttu-id="fcd72-231">選取要建立的復原圖像檔案類型</span><span class="sxs-lookup"><span data-stu-id="fcd72-231">To select the types of recovery image files to create</span></span>**

1.  <span data-ttu-id="fcd72-232">在 [**建立影像**] 頁面上，按一下 **[流覽]** ，選擇影像檔的輸出檔案夾。</span><span class="sxs-lookup"><span data-stu-id="fcd72-232">On the **Create Image** page, click **Browse** to choose the output folder for the image file.</span></span>

    <span data-ttu-id="fcd72-233">**記事** 根據您所選取的工具和您在嚮導中新增的檔案而定，影像的大小會有所不同。</span><span class="sxs-lookup"><span data-stu-id="fcd72-233">**Note** The size of the image will vary, depending on the tools that you select and the files that you add in the wizard.</span></span>

     

2.  <span data-ttu-id="fcd72-234">在 [**影像名稱**] 方塊中，輸入 DaRT 復原影像的名稱，或接受預設名稱（DaRT8）。</span><span class="sxs-lookup"><span data-stu-id="fcd72-234">In the **Image name** box, enter a name for the DaRT recovery image, or accept the default name, which is DaRT8.</span></span>

    <span data-ttu-id="fcd72-235">嚮導會以這個名稱在輸出路徑中建立子資料夾。</span><span class="sxs-lookup"><span data-stu-id="fcd72-235">The wizard creates a subfolder in the output path by this name.</span></span>

3.  <span data-ttu-id="fcd72-236">選取您要建立的圖像檔案類型。</span><span class="sxs-lookup"><span data-stu-id="fcd72-236">Select the types of image files that you want to create.</span></span>

4.  <span data-ttu-id="fcd72-237">選擇下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="fcd72-237">Choose one of the following:</span></span>

    -   <span data-ttu-id="fcd72-238">若要在建立影像檔案之前變更復原影像中的檔案，請選取 [**編輯影像**] 核取方塊，然後按一下 [**準備**]。</span><span class="sxs-lookup"><span data-stu-id="fcd72-238">To change the files in the recovery image before you create the image files, select the **Edit Image** check box, and then click **Prepare**.</span></span>

    -   <span data-ttu-id="fcd72-239">若要在不變更檔案的情況下建立恢復影像，請按一下 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="fcd72-239">To create the recovery image without changing the files, click **Create**.</span></span>

5.  

    <span data-ttu-id="fcd72-240">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="fcd72-240">Click **Next**.</span></span>

## <span data-ttu-id="fcd72-241">編輯復原影像檔</span><span class="sxs-lookup"><span data-stu-id="fcd72-241">Edit the recovery image files</span></span>


<span data-ttu-id="fcd72-242">您可以在 [建立影像] 頁面上選取 [編輯影像] 核取方塊，以編輯復原影像。</span><span class="sxs-lookup"><span data-stu-id="fcd72-242">You can edit the recovery image only if you selected the Edit Image check box on the Create Image page.</span></span> <span data-ttu-id="fcd72-243">在恢復影像準備好進行編輯之後，您就可以在建立可啟動的媒體前新增及修改復原映射檔。</span><span class="sxs-lookup"><span data-stu-id="fcd72-243">After the recovery image has been prepared for editing, you can add and modify the recovery image files before creating the bootable media.</span></span> <span data-ttu-id="fcd72-244">例如，您可以建立啟動的自訂訂單，新增各種協力廠商工具等等。</span><span class="sxs-lookup"><span data-stu-id="fcd72-244">For example, you can create a custom order for startup, add various third-party tools, and so on.</span></span>

**<span data-ttu-id="fcd72-245">若要編輯復原映像檔</span><span class="sxs-lookup"><span data-stu-id="fcd72-245">To edit the recovery image files</span></span>**

1.  <span data-ttu-id="fcd72-246">在 [**編輯影像**] 頁面上，按一下 [在 Windows 資源管理器中**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="fcd72-246">On the **Edit Image** page, click **Open** in Windows Explorer.</span></span>

2.  <span data-ttu-id="fcd72-247">在對話方塊中所列的資料夾中建立子資料夾。</span><span class="sxs-lookup"><span data-stu-id="fcd72-247">Create a subfolder in the folder that is listed in the dialog box.</span></span>

3.  <span data-ttu-id="fcd72-248">將您想要的檔案複製到新的子資料夾，或移除您不想要的檔案。</span><span class="sxs-lookup"><span data-stu-id="fcd72-248">Copy the files that you want to the new subfolder, or remove files that you don’t want.</span></span>

4.  <span data-ttu-id="fcd72-249">按一下 [**建立**]，開始建立恢復影像。</span><span class="sxs-lookup"><span data-stu-id="fcd72-249">Click **Create** to start creating the recovery image.</span></span>

## <span data-ttu-id="fcd72-250">產生復原映像檔</span><span class="sxs-lookup"><span data-stu-id="fcd72-250">Generate the recovery image files</span></span>


<span data-ttu-id="fcd72-251">在 [產生檔案] 頁面上，系統會針對您在 [建立影像] 頁面上選取的檔案類型產生 DaRT 恢復影像。</span><span class="sxs-lookup"><span data-stu-id="fcd72-251">On the Generate Files page, the DaRT recovery image is generated for the file types that you selected on the Create Image page.</span></span>

**<span data-ttu-id="fcd72-252">產生復原映像檔</span><span class="sxs-lookup"><span data-stu-id="fcd72-252">To generate the recovery image files</span></span>**

-   <span data-ttu-id="fcd72-253">在 [**產生**檔案] 頁面上，按一下 **[下一步]** 來產生復原圖像檔案。</span><span class="sxs-lookup"><span data-stu-id="fcd72-253">On the **Generate Files** page, click **Next** to generate the recovery image files.</span></span>

## <span data-ttu-id="fcd72-254">將恢復影像複製到 CD、DVD 或 USB</span><span class="sxs-lookup"><span data-stu-id="fcd72-254">Copy the recovery image to a CD, DVD, or USB</span></span>


<span data-ttu-id="fcd72-255">在 [建立可引導媒體] 頁面上，您可以選擇性地將圖像檔案複製到 CD、DVD 或 USB 快閃記憶體磁片磁碟機（UFD）。</span><span class="sxs-lookup"><span data-stu-id="fcd72-255">On the Create Bootable Media page, you can optionally copy the image file to a CD, DVD, or USB flash drive (UFD).</span></span> <span data-ttu-id="fcd72-256">您也可以重新開機嚮導，從這個頁面建立其他可引導媒體。</span><span class="sxs-lookup"><span data-stu-id="fcd72-256">You can also create additional bootable media from this page by restarting the wizard.</span></span>

<span data-ttu-id="fcd72-257">**記事** 此工具本身不支援開機前執行環境（PXE）和本機映射部署，因為它們需要其他企業工具，例如 System Center Configuration Manager 伺服器和 Microsoft 開發工具套件。</span><span class="sxs-lookup"><span data-stu-id="fcd72-257">**Note** The Preboot execution environment (PXE) and local image deployment are not supported natively by this tool since they require additional enterprise tools, such as System Center Configuration Manager server and Microsoft Development Toolkit.</span></span>

 

**<span data-ttu-id="fcd72-258">若要將恢復影像複製到 CD、DVD 或 USB</span><span class="sxs-lookup"><span data-stu-id="fcd72-258">To copy the recovery image to a CD, DVD, or USB</span></span>**

1.  <span data-ttu-id="fcd72-259">在 [**建立可引導媒體**] 頁面上，選取您要複製的 iso 檔案。</span><span class="sxs-lookup"><span data-stu-id="fcd72-259">On the **Create Bootable Media** page, select the iso file that you want to copy.</span></span>

2.  <span data-ttu-id="fcd72-260">插入 CD、DVD 或 USB，然後選取磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="fcd72-260">Insert a CD, DVD, or USB, and then select the drive.</span></span>

    <span data-ttu-id="fcd72-261">**記事** 如果無法辨識某個磁片磁碟機，且您安裝了新的磁片磁碟機，您可以按一下 [重新整理 **]，強迫**嚮導更新可用的磁片磁碟機清單。</span><span class="sxs-lookup"><span data-stu-id="fcd72-261">**Note** If a drive is not recognized and you install a new drive, you can click **Refresh** to force the wizard to update the list of available drives.</span></span>

     

3.  <span data-ttu-id="fcd72-262">按一下 [**建立可引導媒體**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="fcd72-262">Click the **Create Bootable Media** button.</span></span>

4.  <span data-ttu-id="fcd72-263">若要建立另一個復原影像，請按一下 [重新開機]，如果您已完成建立您想要的所有媒體，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="fcd72-263">To create another recovery image, click Restart, or click **Close** if you have finished creating all of the media that you want.</span></span>

## <span data-ttu-id="fcd72-264">相關主題</span><span class="sxs-lookup"><span data-stu-id="fcd72-264">Related topics</span></span>


[<span data-ttu-id="fcd72-265">DaRT 8.0 中的工具簡介</span><span class="sxs-lookup"><span data-stu-id="fcd72-265">Overview of the Tools in DaRT 8.0</span></span>](overview-of-the-tools-in-dart-80-dart-8.md)

[<span data-ttu-id="fcd72-266">部署 DaRT 8.0</span><span class="sxs-lookup"><span data-stu-id="fcd72-266">Deploying DaRT 8.0</span></span>](deploying-dart-80-dart-8.md)

 

 





