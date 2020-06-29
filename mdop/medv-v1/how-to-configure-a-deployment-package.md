---
title: 如何設定部署套件
description: 如何設定部署套件
author: dansimp
ms.assetid: 748272a1-6af2-476e-a3f1-87435b8e94b1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: aba5e91a4da92f9e51a5ccc70502658ae724d76f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811462"
---
# <span data-ttu-id="c0627-103">如何設定部署套件</span><span class="sxs-lookup"><span data-stu-id="c0627-103">How to Configure a Deployment Package</span></span>


<span data-ttu-id="c0627-104">打包嚮導會在您的本機電腦上建立資料夾，並將所有必要的安裝檔案傳輸到單一資料夾，以引導您完成套件的建立。</span><span class="sxs-lookup"><span data-stu-id="c0627-104">The Packaging wizard walks you through the creation of a package by creating a folder on your local computer and transferring all the required installation files to the single folder.</span></span> <span data-ttu-id="c0627-105">然後，您可以將資料夾的內容移至多個卸除式媒體磁碟機以進行發佈。</span><span class="sxs-lookup"><span data-stu-id="c0627-105">The contents of the folder can then be moved to multiple removable media drives for distribution.</span></span>

**<span data-ttu-id="c0627-106">注意</span><span class="sxs-lookup"><span data-stu-id="c0627-106">Note</span></span>**  
<span data-ttu-id="c0627-107">單一套件不能包含 x86 和 x64 系統的安裝檔。</span><span class="sxs-lookup"><span data-stu-id="c0627-107">A single package cannot contain installation files for both x86 and x64 systems.</span></span>



## <span data-ttu-id="c0627-108">如何建立部署套件</span><span class="sxs-lookup"><span data-stu-id="c0627-108">How to Create a Deployment Package</span></span>


**<span data-ttu-id="c0627-109">建立部署套件</span><span class="sxs-lookup"><span data-stu-id="c0627-109">To create a deployment package</span></span>**

1. <span data-ttu-id="c0627-110">在**影像**模組中確認您已建立至少一個本機打包的影像。</span><span class="sxs-lookup"><span data-stu-id="c0627-110">Verify in the **Images** module that you have created at least one local packed image.</span></span>

2. <span data-ttu-id="c0627-111">在 [**工具**] 功能表上，選取 [**打包嚮導]**。</span><span class="sxs-lookup"><span data-stu-id="c0627-111">On the **Tools** menu, select **Packaging wizard**.</span></span>

3. <span data-ttu-id="c0627-112">在 [**打包嚮導]** 歡迎頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="c0627-112">On the **Packaging wizard** welcome page, click **Next**.</span></span>

4. <span data-ttu-id="c0627-113">在 [**工作區圖像**] 頁面上，選取 [在**套件中包含影像**] 核取方塊，以在套件中包含影像。</span><span class="sxs-lookup"><span data-stu-id="c0627-113">On the **Workspace Image** page, select the **Include image in the package** check box to include an image in the package.</span></span>

   <span data-ttu-id="c0627-114">[**影像**] 欄位已啟用。</span><span class="sxs-lookup"><span data-stu-id="c0627-114">The **Image** field is enabled.</span></span>

   **<span data-ttu-id="c0627-115">注意</span><span class="sxs-lookup"><span data-stu-id="c0627-115">Note</span></span>**  
   <span data-ttu-id="c0627-116">在 MED-V 套件中不需要影像;您可以建立不含影像的套件。</span><span class="sxs-lookup"><span data-stu-id="c0627-116">An image is not required in a MED-V package; the package can be created without an image.</span></span> <span data-ttu-id="c0627-117">在這種情況下，應該將影像上傳到伺服器，以便稍後透過網路將它下載到用戶端，或是將它推入影像的暫存資料夾。</span><span class="sxs-lookup"><span data-stu-id="c0627-117">In such a case, the image should be uploaded to the server so that it can later be downloaded over the network to the client, or pushed to an image pre-stage folder.</span></span>



5. <span data-ttu-id="c0627-118">按一下**影像**清單，即可查看所有可用的影像。</span><span class="sxs-lookup"><span data-stu-id="c0627-118">Click the **Image** list to view all available images.</span></span> <span data-ttu-id="c0627-119">選取要複製到套件的影像。</span><span class="sxs-lookup"><span data-stu-id="c0627-119">Select the image to be copied to the package.</span></span> <span data-ttu-id="c0627-120">按一下 **[** 重新整理] 以重新整理可用影像的清單。</span><span class="sxs-lookup"><span data-stu-id="c0627-120">Click **Refresh** to refresh the list of available images.</span></span>

6. <span data-ttu-id="c0627-121">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="c0627-121">Click **Next**.</span></span>

7. <span data-ttu-id="c0627-122">在 [ **Med-v 安裝設定**] 頁面上，執行下列其中一項來選取 med-v 安裝檔：</span><span class="sxs-lookup"><span data-stu-id="c0627-122">On the **MED-V Installation Settings** page, select the MED-V installation file by doing one of the following:</span></span>

   -   <span data-ttu-id="c0627-123">在 [ **med-v 安裝**檔案] 欄位中，輸入安裝檔案所在目錄的完整路徑。</span><span class="sxs-lookup"><span data-stu-id="c0627-123">In the **MED-V installation file** field, type the full path to the directory where the installation file is located.</span></span>

   -   <span data-ttu-id="c0627-124">按一下 [ **...** ] 以流覽至安裝檔案所在的目錄。</span><span class="sxs-lookup"><span data-stu-id="c0627-124">Click **...** to browse to the directory where the installation file is located.</span></span>

   **<span data-ttu-id="c0627-125">注意</span><span class="sxs-lookup"><span data-stu-id="c0627-125">Note</span></span>**  
   <span data-ttu-id="c0627-126">此欄位是強制性的，而且在沒有有效檔案名的情況下，嚮導將無法繼續。</span><span class="sxs-lookup"><span data-stu-id="c0627-126">This field is mandatory, and the wizard will not continue without a valid file name.</span></span>



8. <span data-ttu-id="c0627-127">在 [ **server address] （伺服器位址**）欄位中，輸入伺服器名稱或 IP 位址。</span><span class="sxs-lookup"><span data-stu-id="c0627-127">In the **Server address** field, type the server name or IP address.</span></span>

9. <span data-ttu-id="c0627-128">在 [ **server port] （伺服器埠**）欄位中，輸入伺服器埠。</span><span class="sxs-lookup"><span data-stu-id="c0627-128">In the **Server port** field, type the server port.</span></span>

10. <span data-ttu-id="c0627-129">選取 [**使用 HTTPs 存取伺服器**] 核取方塊，即可需要 HTTPs 連線才能連線到伺服器。</span><span class="sxs-lookup"><span data-stu-id="c0627-129">Select the **Server is accessed using https** check box to require an https connection to connect to the server.</span></span>

11. <span data-ttu-id="c0627-130">執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="c0627-130">Do one of the following:</span></span>

    -   <span data-ttu-id="c0627-131">按一下 [**預設安裝設定**]，然後按一下 **[下一步]** 繼續並保留預設設定。</span><span class="sxs-lookup"><span data-stu-id="c0627-131">Click **Default installation settings**, and then click **Next** to continue and leave the default settings.</span></span>

    -   <span data-ttu-id="c0627-132">按一下 [**自訂安裝設定**]，然後按一下 **[下一步]** 以自訂安裝設定。</span><span class="sxs-lookup"><span data-stu-id="c0627-132">Click **Custom installation settings**, and then click **Next** to customize the installation settings.</span></span>

        1.  <span data-ttu-id="c0627-133">在 [ **Med-v 安裝自訂設定**] 頁面上的 [**安裝資料夾**] 欄位中，輸入將在主機電腦上安裝 med-v 檔案的資料夾路徑。</span><span class="sxs-lookup"><span data-stu-id="c0627-133">On the **MED-V Installation Custom Settings** page, in the **Installation folder** field, type the path of the folder where the MED-V files will be installed on the host computer.</span></span>

            **<span data-ttu-id="c0627-134">注意</span><span class="sxs-lookup"><span data-stu-id="c0627-134">Note</span></span>**  
            <span data-ttu-id="c0627-135">建議您在路徑中使用變數，而不是常數，這可能會與電腦有所不同。</span><span class="sxs-lookup"><span data-stu-id="c0627-135">It is recommended to use variables in the path rather than constants, which might vary from computer to computer.</span></span>

            <span data-ttu-id="c0627-136">例如，使用 *%ProgramFiles%\\MED-V*而不是*c:\\MED-V*。</span><span class="sxs-lookup"><span data-stu-id="c0627-136">For example, use *%ProgramFiles%\\MED-V* instead of *c:\\MED-V*.</span></span>



    ~~~
    2.  In the **Virtual machines images folder** field, type the path of the folder where the virtual images files will be installed on the host computer.

        **Note**  
        If you are using image pre-staging, this is the image pre-stage folder where the image is located.



    3.  In the **Minimal required RAM** field, enter the RAM required to install a MED-V package. If the user installing the MED-V package does not have the minimal required RAM, the installation will fail.

    4.  Select the **Install the MED-V management application** check box to include the MED-V management console application in the installation.

    5.  Select the **Create a shortcut to MED-V on the desktop** check box to create a shortcut to MED-V on the host's desktop.

    6.  Select the **Start automatically on computer startup** check box to start MED-V automatically on startup.

    7.  Click **Next**.
    ~~~

12. <span data-ttu-id="c0627-137">在 [**其他安裝**] 頁面上，選取 [**包括虛擬化軟體的安裝**] 核取方塊，以包含套件中的虛擬電腦安裝。</span><span class="sxs-lookup"><span data-stu-id="c0627-137">On the **Additional Installations** page, select the **Include installation of virtualization software** check box to include the Virtual PC installation in the package.</span></span>

    <span data-ttu-id="c0627-138">[**安裝檔**] 欄位已啟用。</span><span class="sxs-lookup"><span data-stu-id="c0627-138">The **Installation file** field is enabled.</span></span> <span data-ttu-id="c0627-139">輸入虛擬化軟體安裝檔案的完整路徑，或按一下 [ **...** ] 以流覽至該目錄。</span><span class="sxs-lookup"><span data-stu-id="c0627-139">Type the full path of the virtualization software installation file, or click **...** to browse to the directory.</span></span>

13. <span data-ttu-id="c0627-140">選取 [**包括虛擬電腦 QFE 的安裝**] 核取方塊，以包含套件中的虛擬電腦更新安裝。</span><span class="sxs-lookup"><span data-stu-id="c0627-140">Select the **Include installation of Virtual PC QFE** check box to include Virtual PC update installation in the package.</span></span>

    <span data-ttu-id="c0627-141">[**安裝檔**] 欄位已啟用。</span><span class="sxs-lookup"><span data-stu-id="c0627-141">The **Installation file** field is enabled.</span></span> <span data-ttu-id="c0627-142">輸入虛擬電腦更新安裝檔案的完整路徑，或按一下 [ **...** ] 以流覽至該目錄。</span><span class="sxs-lookup"><span data-stu-id="c0627-142">Type the full path of the Virtual PC update installation file, or click **...** to browse to the directory.</span></span>

14. <span data-ttu-id="c0627-143">選取 [**包括安裝 microsoft .Net framework 2.0** ] 核取方塊，以將 Microsoft .net framework 2.0 安裝包含在套件中。</span><span class="sxs-lookup"><span data-stu-id="c0627-143">Select the **Include installation of Microsoft .NET Framework 2.0** check box to include the Microsoft .NET Framework 2.0 installation in the package.</span></span>

    <span data-ttu-id="c0627-144">[**安裝檔**] 欄位已啟用。</span><span class="sxs-lookup"><span data-stu-id="c0627-144">The **Installation file** field is enabled.</span></span> <span data-ttu-id="c0627-145">輸入 Microsoft .NET Framework 2.0 安裝檔案的完整路徑，或按一下 [ **...** ] 以流覽至該目錄。</span><span class="sxs-lookup"><span data-stu-id="c0627-145">Type the full path of the Microsoft .NET Framework 2.0 installation file, or click **...** to browse to the directory.</span></span>

15. <span data-ttu-id="c0627-146">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="c0627-146">Click **Next**.</span></span>

16. <span data-ttu-id="c0627-147">在 [**完成**] 頁面上，請執行下列其中一項動作，選取要儲存套件的位置：</span><span class="sxs-lookup"><span data-stu-id="c0627-147">On the **Finalize** page, select the location where the package should be saved by doing one of the following:</span></span>

    -   <span data-ttu-id="c0627-148">在 [**套件目的地**] 欄位中，輸入要儲存套件的目錄完整路徑。</span><span class="sxs-lookup"><span data-stu-id="c0627-148">In the **Package destination** field, type the full path to the directory where the package should be saved.</span></span>

    -   <span data-ttu-id="c0627-149">按一下 [ **...** ] 以流覽至要儲存安裝盤案的目錄。</span><span class="sxs-lookup"><span data-stu-id="c0627-149">Click **...** to browse to the directory where the installation files should be saved.</span></span>

    **<span data-ttu-id="c0627-150">注意</span><span class="sxs-lookup"><span data-stu-id="c0627-150">Note</span></span>**  
    <span data-ttu-id="c0627-151">建立套件可能會佔用比實際套件大小更多的空間。</span><span class="sxs-lookup"><span data-stu-id="c0627-151">Building the package might consume more space than the actual package size.</span></span> <span data-ttu-id="c0627-152">因此，建議您在硬碟上建立套件。</span><span class="sxs-lookup"><span data-stu-id="c0627-152">It is therefore recommended to build the package on the hard drive.</span></span> <span data-ttu-id="c0627-153">建立套件之後，就可以將它複製到 USB。</span><span class="sxs-lookup"><span data-stu-id="c0627-153">After the package is created, it can then be copied to the USB.</span></span>



17. <span data-ttu-id="c0627-154">在 [**套件名稱**] 欄位中，輸入套件的名稱。</span><span class="sxs-lookup"><span data-stu-id="c0627-154">In the **Package name** field, enter a name for the package.</span></span>

18. <span data-ttu-id="c0627-155">按一下 **[完成]** 來建立套件。</span><span class="sxs-lookup"><span data-stu-id="c0627-155">Click **Finish** to create the package.</span></span>

    <span data-ttu-id="c0627-156">套件即建立完畢。</span><span class="sxs-lookup"><span data-stu-id="c0627-156">The package is created.</span></span> <span data-ttu-id="c0627-157">這可能需要幾分鐘的時間。</span><span class="sxs-lookup"><span data-stu-id="c0627-157">This might take several minutes.</span></span>

    <span data-ttu-id="c0627-158">建立套件之後，會出現一則訊息，通知您已成功完成。</span><span class="sxs-lookup"><span data-stu-id="c0627-158">After the package is created, a message appears notifying you that it has been completed successfully.</span></span>

**<span data-ttu-id="c0627-159">注意</span><span class="sxs-lookup"><span data-stu-id="c0627-159">Note</span></span>**  
<span data-ttu-id="c0627-160">如果您在本機儲存了所有檔案，而不是直接在移除的媒體上儲存，請確定您只將資料夾內容（而非資料夾本身）複製到卸除式媒體中。</span><span class="sxs-lookup"><span data-stu-id="c0627-160">If you saved all the files locally, and not directly on the removable media, ensure that you copy only the contents of the folder and not the folder itself to the removable media.</span></span>



**<span data-ttu-id="c0627-161">注意</span><span class="sxs-lookup"><span data-stu-id="c0627-161">Note</span></span>**  
<span data-ttu-id="c0627-162">卸除式媒體的大小必須足夠大，才能讓套件內容只佔用最多三個季度的卸除式媒體記憶體。</span><span class="sxs-lookup"><span data-stu-id="c0627-162">The removable media must be large enough so that the package contents consume a maximum of only three-quarters of the removable media's memory.</span></span>



**<span data-ttu-id="c0627-163">注意</span><span class="sxs-lookup"><span data-stu-id="c0627-163">Note</span></span>**  
<span data-ttu-id="c0627-164">建立套件時，在完成組建後，可能需要最多兩倍的實際套件大小。</span><span class="sxs-lookup"><span data-stu-id="c0627-164">When creating the package, up to double the size of the actual package size might be required when the build is complete.</span></span>



## <span data-ttu-id="c0627-165">相關主題</span><span class="sxs-lookup"><span data-stu-id="c0627-165">Related topics</span></span>


[<span data-ttu-id="c0627-166">建立 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="c0627-166">Creating a MED-V Image</span></span>](creating-a-med-v-image.md)









