---
title: 建立 MED-V 的虛擬電腦映像
description: 建立 MED-V 的虛擬電腦映像
author: dansimp
ms.assetid: 5e02ea07-25b9-41a5-a803-d70c55eef586
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 84e45f9ff7213abdd6288bcd750238436d3ab68c
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810089"
---
# <span data-ttu-id="56268-103">建立 MED-V 的虛擬電腦映像</span><span class="sxs-lookup"><span data-stu-id="56268-103">Creating a Virtual PC Image for MED-V</span></span>


<span data-ttu-id="56268-104">若要建立 MED-V 的虛擬電腦（VPC）影像，您必須執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="56268-104">To create a Virtual PC (VPC) image for MED-V, you must perform the following:</span></span>

1.  <span data-ttu-id="56268-105">[建立 VPC 影像](#bkmk-creatingavirtualmachinebyusingmicrosoftvirtualpc)。</span><span class="sxs-lookup"><span data-stu-id="56268-105">[Create a VPC image](#bkmk-creatingavirtualmachinebyusingmicrosoftvirtualpc).</span></span>

2.  <span data-ttu-id="56268-106">[在 VPC 影像上安裝 med-v （msi）工作區。](#bkmk-howtoinstallthemedvworkspacemsipackage)</span><span class="sxs-lookup"><span data-stu-id="56268-106">[Install the MED-V workspace .msi package onto the VPC image](#bkmk-howtoinstallthemedvworkspacemsipackage).</span></span>

3.  <span data-ttu-id="56268-107">[在 VPC 影像上執行 med-v 虛擬機器必備工具](#bkmk-howtorunthevirtualmachineprerequisitestool)。</span><span class="sxs-lookup"><span data-stu-id="56268-107">[Run the MED-V virtual machine prerequisites tool on the VPC image](#bkmk-howtorunthevirtualmachineprerequisitestool).</span></span>

4.  <span data-ttu-id="56268-108">[在 VPC 影像上手動設定虛擬機器必備元件](#bkmk-howtoconfiguremedvvirtualmachinemanualinstallationprerequisites)。</span><span class="sxs-lookup"><span data-stu-id="56268-108">[Manually configure virtual machine prerequisites on the VPC image](#bkmk-howtoconfiguremedvvirtualmachinemanualinstallationprerequisites).</span></span>

5.  <span data-ttu-id="56268-109">[針對 med-v 影像設定 Sysprep](#bkmk-howtoconfiguresysprepformedvimages) （選用）。</span><span class="sxs-lookup"><span data-stu-id="56268-109">[Configure Sysprep for MED-V images](#bkmk-howtoconfiguresysprepformedvimages) (optional).</span></span>

6.  <span data-ttu-id="56268-110">[關閉 Microsoft VIRTUAL PC](#bkmk-turningoffmicrosoftvirtualpc)。</span><span class="sxs-lookup"><span data-stu-id="56268-110">[Turn off Microsoft Virtual PC](#bkmk-turningoffmicrosoftvirtualpc).</span></span>

## <a href="" id="bkmk-creatingavirtualmachinebyusingmicrosoftvirtualpc"></a><span data-ttu-id="56268-111">使用 Microsoft Virtual PC 建立虛擬電腦影像</span><span class="sxs-lookup"><span data-stu-id="56268-111">Creating a Virtual PC Image by Using Microsoft Virtual PC</span></span>


<span data-ttu-id="56268-112">若要使用 Microsoft 虛擬電腦建立虛擬電腦影像，請參閱虛擬電腦的檔。</span><span class="sxs-lookup"><span data-stu-id="56268-112">To create a Virtual PC image using Microsoft Virtual PC, refer to the Virtual PC documentation.</span></span>

<span data-ttu-id="56268-113">如需詳細資訊，請參閱下列各項：</span><span class="sxs-lookup"><span data-stu-id="56268-113">For more information, see the following:</span></span>

-   [<span data-ttu-id="56268-114">Windows 虛擬電腦說明</span><span class="sxs-lookup"><span data-stu-id="56268-114">Windows Virtual PC Help</span></span>](https://go.microsoft.com/fwlink/?LinkId=182378)

-   [<span data-ttu-id="56268-115">建立虛擬機器並安裝客體作業系統</span><span class="sxs-lookup"><span data-stu-id="56268-115">Create a virtual machine and install a guest operating system</span></span>](https://go.microsoft.com/fwlink/?LinkId=182379)

## <a href="" id="bkmk-howtoinstallthemedvworkspacemsipackage"></a><span data-ttu-id="56268-116">如何安裝 MED-V 工作區 .msi 套件</span><span class="sxs-lookup"><span data-stu-id="56268-116">How to Install the MED-V Workspace .msi Package</span></span>


<span data-ttu-id="56268-117">建立虛擬電腦影像之後，請在影像上安裝 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="56268-117">After the Virtual PC image is created, install the MED-V workspace .msi package onto the image.</span></span>

**<span data-ttu-id="56268-118">若要安裝 MED-V 工作區圖像</span><span class="sxs-lookup"><span data-stu-id="56268-118">To install the MED-V workspace image</span></span>**

1.  <span data-ttu-id="56268-119">啟動虛擬機器，然後將 MED-V 中的 .msi 套件複製到其中。</span><span class="sxs-lookup"><span data-stu-id="56268-119">Start the virtual machine, and copy the MED-V workspace .msi package inside.</span></span>

    <span data-ttu-id="56268-120">會呼叫 MED-V 工作區， *MED-V\_workspace\_x.msi*，其中*x*是版本號碼。</span><span class="sxs-lookup"><span data-stu-id="56268-120">The MED-V workspace .msi package is called *MED-V\_workspace\_x.msi*, where *x* is the version number.</span></span>

    <span data-ttu-id="56268-121">例如， *MED-V\_workspace\_1.0.65.msi*。</span><span class="sxs-lookup"><span data-stu-id="56268-121">For example, *MED-V\_workspace\_1.0.65.msi*.</span></span>

2.  <span data-ttu-id="56268-122">按兩下 [MED-V] 工作區 .msi 套件，然後依照安裝精靈指示進行。</span><span class="sxs-lookup"><span data-stu-id="56268-122">Double-click the MED-V workspace .msi package, and follow the installation wizard instructions.</span></span>

    **<span data-ttu-id="56268-123">注意</span><span class="sxs-lookup"><span data-stu-id="56268-123">Note</span></span>**  
    <span data-ttu-id="56268-124">當您釋放新的 MED-V 版本，且已更新現有的虛擬電腦影像時，請卸載現有的 MED-V 工作區。 msi 套件，重新開機電腦，然後安裝新的 MED-V 工作區 .msi 套件。</span><span class="sxs-lookup"><span data-stu-id="56268-124">When a new MED-V version is released, and an existing Virtual PC image is updated, uninstall the existing MED-V workspace .msi package, reboot the computer, and install the new MED-V workspace .msi package.</span></span>



~~~
**Note**  
After the MED-V workspace .msi package is installed, other products that replace GINA cannot be installed.
~~~



## <a href="" id="bkmk-howtorunthevirtualmachineprerequisitestool"></a><span data-ttu-id="56268-125">如何執行虛擬機器必備元件工具</span><span class="sxs-lookup"><span data-stu-id="56268-125">How to Run the Virtual Machine Prerequisites Tool</span></span>


<span data-ttu-id="56268-126">虛擬機器（VM）先決條件工具是一個可自動執行幾個必備元件的嚮導。</span><span class="sxs-lookup"><span data-stu-id="56268-126">The virtual machine (VM) prerequisites tool is a wizard that automates several of the prerequisites.</span></span>

**<span data-ttu-id="56268-127">注意</span><span class="sxs-lookup"><span data-stu-id="56268-127">Note</span></span>**  
<span data-ttu-id="56268-128">雖然在嚮導中有許多參數可設定，但 MED-V 的正常運作所需的屬性無法進行設定。</span><span class="sxs-lookup"><span data-stu-id="56268-128">Although many parameters are configurable in the wizard, the properties required for the proper functioning of MED-V are not configurable.</span></span>



**<span data-ttu-id="56268-129">執行虛擬機器必備元件工具</span><span class="sxs-lookup"><span data-stu-id="56268-129">To run the virtual machine prerequisites tool</span></span>**

1.  <span data-ttu-id="56268-130">安裝 MED-V 工作區後，請在 Windows [**開始**] 功能表上，選取 [**所有程式] &gt; med-v &gt; VM 必備工具**。</span><span class="sxs-lookup"><span data-stu-id="56268-130">After the MED-V workspace .msi package is installed, on the Windows **Start** menu, select **All Programs &gt; MED-V &gt; VM Prerequisites Tool**.</span></span>

    **<span data-ttu-id="56268-131">注意</span><span class="sxs-lookup"><span data-stu-id="56268-131">Note</span></span>**  
    <span data-ttu-id="56268-132">執行虛擬機器必備工具的使用者必須擁有本機系統管理員許可權，而且必須是唯一登入的使用者。</span><span class="sxs-lookup"><span data-stu-id="56268-132">The user running the virtual machine prerequisites tool must have local administrator rights and must be the only user logged in.</span></span>



~~~
The **MED-V VM Prerequisite Wizard Welcome** page appears.
~~~

2. <span data-ttu-id="56268-133">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="56268-133">Click **Next**.</span></span>

3. <span data-ttu-id="56268-134">在 [ **Windows 設定**] 頁面上，從下列可設定的屬性選取要設定的屬性：</span><span class="sxs-lookup"><span data-stu-id="56268-134">On the **Windows Settings** page, from the following configurable properties, select the ones to be configured:</span></span>

   -   **<span data-ttu-id="56268-135">清除使用者的個人歷程記錄資訊</span><span class="sxs-lookup"><span data-stu-id="56268-135">Clear users’ personal history information</span></span>**

   -   **<span data-ttu-id="56268-136">清除本機設定檔臨時目錄</span><span class="sxs-lookup"><span data-stu-id="56268-136">Clear local profiles temp directory</span></span>**

   -   **<span data-ttu-id="56268-137">在下列 Windows 事件上停用聲音：啟動、登入、登出</span><span class="sxs-lookup"><span data-stu-id="56268-137">Disable sounds on following Windows events: start, logon, logoff</span></span>**

   **<span data-ttu-id="56268-138">注意</span><span class="sxs-lookup"><span data-stu-id="56268-138">Note</span></span>**  
   <span data-ttu-id="56268-139">請勿在群組原則中啟用 Windows 頁面保護程式。</span><span class="sxs-lookup"><span data-stu-id="56268-139">Do not enable Windows page saver in a group policy.</span></span>



4. <span data-ttu-id="56268-140">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="56268-140">Click **Next**.</span></span>

5. <span data-ttu-id="56268-141">在**Internet Explorer [設定**] 頁面上，從下列可設定的屬性選取要設定的屬性：</span><span class="sxs-lookup"><span data-stu-id="56268-141">On the **Internet Explorer Settings** page, from the following configurable properties, select the ones to be configured:</span></span>

   -   **<span data-ttu-id="56268-142">不要使用自動完成功能</span><span class="sxs-lookup"><span data-stu-id="56268-142">Don't use auto complete features</span></span>**

   -   **<span data-ttu-id="56268-143">停用啟動快速鍵的 windows</span><span class="sxs-lookup"><span data-stu-id="56268-143">Disable reuse of windows for launching shortcuts</span></span>**

   -   **<span data-ttu-id="56268-144">清除瀏覽歷程記錄</span><span class="sxs-lookup"><span data-stu-id="56268-144">Clear browsing history</span></span>**

   -   **<span data-ttu-id="56268-145">在 Internet Explorer 7 中啟用分頁流覽</span><span class="sxs-lookup"><span data-stu-id="56268-145">Enable tabbed browsing in Internet Explorer 7</span></span>**

6. <span data-ttu-id="56268-146">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="56268-146">Click **Next**.</span></span>

7. <span data-ttu-id="56268-147">在 [ **Windows 服務**] 頁面上，從下列可設定的屬性選取要設定的屬性：</span><span class="sxs-lookup"><span data-stu-id="56268-147">On the **Windows Services** page, from the following configurable properties, select the ones to be configured:</span></span>

   -   **<span data-ttu-id="56268-148">安全性中心服務</span><span class="sxs-lookup"><span data-stu-id="56268-148">Security center service</span></span>**

   -   **<span data-ttu-id="56268-149">任務計畫程式服務</span><span class="sxs-lookup"><span data-stu-id="56268-149">Task scheduler service</span></span>**

   -   **<span data-ttu-id="56268-150">自動更新服務</span><span class="sxs-lookup"><span data-stu-id="56268-150">Automatic updates service</span></span>**

   -   **<span data-ttu-id="56268-151">系統還原服務</span><span class="sxs-lookup"><span data-stu-id="56268-151">System restore service</span></span>**

   -   **<span data-ttu-id="56268-152">索引服務</span><span class="sxs-lookup"><span data-stu-id="56268-152">Indexing service</span></span>**

   -   **<span data-ttu-id="56268-153">無線零設定</span><span class="sxs-lookup"><span data-stu-id="56268-153">Wireless Zero Configuration</span></span>**

   -   **<span data-ttu-id="56268-154">快速使用者切換相容性</span><span class="sxs-lookup"><span data-stu-id="56268-154">Fast User Switching Compatibility</span></span>**

8. <span data-ttu-id="56268-155">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="56268-155">Click **Next**.</span></span>

9. <span data-ttu-id="56268-156">在 [ **Windows 自動登**入] 頁面上，執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="56268-156">On the **Windows Auto Logon** page, do the following:</span></span>

   1.  <span data-ttu-id="56268-157">選取 [**啟用 Windows 自動登**入] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="56268-157">Select the **Enable Windows Auto Logon** check box.</span></span>

   2.  <span data-ttu-id="56268-158">指派**使用者名稱**和**密碼**。</span><span class="sxs-lookup"><span data-stu-id="56268-158">Assign a **User name** and **Password**.</span></span>

10. <span data-ttu-id="56268-159">按一下 **[** 套用]，然後在出現的確認方塊中，按一下 [**是]**。</span><span class="sxs-lookup"><span data-stu-id="56268-159">Click **Apply**, and in the confirmation box that appears, click **Yes**.</span></span>

11. <span data-ttu-id="56268-160">在 [**摘要**] 頁面上，按一下 **[完成] 結束**嚮導</span><span class="sxs-lookup"><span data-stu-id="56268-160">On the **Summary** page, click **Finish** to quit the wizard</span></span>

**<span data-ttu-id="56268-161">注意</span><span class="sxs-lookup"><span data-stu-id="56268-161">Note</span></span>**  
<span data-ttu-id="56268-162">確認 [群組原則] 不會覆寫 [先決條件工具] 中設定的強制設定。</span><span class="sxs-lookup"><span data-stu-id="56268-162">Verify that group policies do not overwrite the mandatory settings set in the prerequisites tool.</span></span>



## <a href="" id="bkmk-howtoconfiguremedvvirtualmachinemanualinstallationprerequisites"></a><span data-ttu-id="56268-163">如何設定 MED-V Virtual 電腦手動安裝先決條件</span><span class="sxs-lookup"><span data-stu-id="56268-163">How to Configure MED-V Virtual Machine Manual Installation Prerequisites</span></span>


<span data-ttu-id="56268-164">無法透過虛擬機器必備工具來設定數種設定，必須手動執行。</span><span class="sxs-lookup"><span data-stu-id="56268-164">Several of the configurations cannot be configured through the virtual machine prerequisites tool and must be performed manually.</span></span>

-   <span data-ttu-id="56268-165">虛擬機器設定</span><span class="sxs-lookup"><span data-stu-id="56268-165">Virtual Machine Settings</span></span>

    <span data-ttu-id="56268-166">建議您在 Microsoft Virtual PC 主控台中設定下列虛擬機器設定：</span><span class="sxs-lookup"><span data-stu-id="56268-166">It is recommended to configure the following virtual machine settings in the Microsoft Virtual PC console:</span></span>

    -   <span data-ttu-id="56268-167">停用軟碟磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="56268-167">Disable floppy disk drives.</span></span>

    -   <span data-ttu-id="56268-168">停用復原-磁片（**設定 &gt; 復原磁片**）。</span><span class="sxs-lookup"><span data-stu-id="56268-168">Disable undo-disks (**Settings &gt; undo-disks**).</span></span>

    -   <span data-ttu-id="56268-169">確定影像只有一個虛擬 CPU。</span><span class="sxs-lookup"><span data-stu-id="56268-169">Ensure that the image has only one virtual CPU.</span></span>

    -   <span data-ttu-id="56268-170">消除虛擬機器與使用者之間的互動，與已發佈的應用程式無關（例如需要使用者輸入的訊息）。</span><span class="sxs-lookup"><span data-stu-id="56268-170">Eliminate interactions between the virtual machine and the user, where they are not related to published applications (such as, messages requiring user input).</span></span>

-   <span data-ttu-id="56268-171">影像設定</span><span class="sxs-lookup"><span data-stu-id="56268-171">Image Settings</span></span>

    <span data-ttu-id="56268-172">在影像內設定下列手動設定：</span><span class="sxs-lookup"><span data-stu-id="56268-172">Configure the following manual settings inside the image:</span></span>

    1.  <span data-ttu-id="56268-173">在 [**電源選項屬性**] 視窗中，停用 [休眠] 和 [睡眠]。</span><span class="sxs-lookup"><span data-stu-id="56268-173">In the **Power Options Properties** window, disable hibernation and sleep.</span></span>

    2.  <span data-ttu-id="56268-174">套用最新的 Windows 更新。</span><span class="sxs-lookup"><span data-stu-id="56268-174">Apply the most recent Windows updates.</span></span>

    3.  <span data-ttu-id="56268-175">在 [ **Windows 啟動及損毀修復**] 對話方塊的 [**系統失敗**] 區段中，清除 [**自動重新開機**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="56268-175">In the **Windows Startup and Recovery** dialog box, in the **System Failure** section, clear the **Automatically restart** check box.</span></span>

    4.  <span data-ttu-id="56268-176">確定影像使用 VLK 授權金鑰。</span><span class="sxs-lookup"><span data-stu-id="56268-176">Ensure that the image uses a VLK license key.</span></span>

-   <span data-ttu-id="56268-177">安裝 VPC 新增功能</span><span class="sxs-lookup"><span data-stu-id="56268-177">Installing VPC Additions</span></span>

    <span data-ttu-id="56268-178">在 [**動作**] 功能表上，選取 [**安裝或更新虛擬機器新增**]。</span><span class="sxs-lookup"><span data-stu-id="56268-178">On the **Action** menu, select **Install or Update Virtual Machine Additions**.</span></span>

-   <span data-ttu-id="56268-179">設定列印</span><span class="sxs-lookup"><span data-stu-id="56268-179">Configuring Printing</span></span>

    <span data-ttu-id="56268-180">您可以透過下列其中一種方式，從 MED-V 工作區設定列印：</span><span class="sxs-lookup"><span data-stu-id="56268-180">You can configure printing from the MED-V workspace in either of the following ways:</span></span>

    -   <span data-ttu-id="56268-181">新增印表機至虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="56268-181">Add a printer to the virtual machine.</span></span>

    -   <span data-ttu-id="56268-182">允許使用主機電腦上設定的印表機進行列印。</span><span class="sxs-lookup"><span data-stu-id="56268-182">Allow printing with printers that are configured on the host computer.</span></span>

## <a href="" id="bkmk-howtoconfiguresysprepformedvimages"></a><span data-ttu-id="56268-183">如何針對 MED-V 影像設定 Sysprep</span><span class="sxs-lookup"><span data-stu-id="56268-183">How to Configure Sysprep for MED-V Images</span></span>


<span data-ttu-id="56268-184">在 MED-V 工作區中，您可以設定 Sysprep 來指派唯一的安全識別碼（SID），特別是在一部電腦上執行多個 MED-V 工作區時。</span><span class="sxs-lookup"><span data-stu-id="56268-184">In a MED-V workspace, Sysprep can be configured in order to assign unique security ID (SID), particularly when multiple MED-V workspaces are run on a single computer.</span></span> <span data-ttu-id="56268-185">建議您不要使用 Sysprep 來加入網域。請改為使用 MED-V join 網域腳本指令，如[如何設定腳本動作](how-to-set-up-script-actions.md)中所述。</span><span class="sxs-lookup"><span data-stu-id="56268-185">It is not recommended to use Sysprep to join a domain; instead, use the MED-V join domain script action as described in [How to Set Up Script Actions](how-to-set-up-script-actions.md).</span></span>

**<span data-ttu-id="56268-186">注意</span><span class="sxs-lookup"><span data-stu-id="56268-186">Note</span></span>**  
<span data-ttu-id="56268-187">Sysprep 是適用于 Windows 作業系統的 Microsoft 系統準備實用程式。</span><span class="sxs-lookup"><span data-stu-id="56268-187">Sysprep is Microsoft's system preparation utility for the Windows operating system.</span></span>



**<span data-ttu-id="56268-188">在 MED-V 工作區中設定 Sysprep</span><span class="sxs-lookup"><span data-stu-id="56268-188">To configure Sysprep in a MED-V workspace</span></span>**

1.  <span data-ttu-id="56268-189">在名為*Sysprep*的系統磁碟機根目錄中建立目錄。</span><span class="sxs-lookup"><span data-stu-id="56268-189">Create a directory in the root of the system drive named *Sysprep*.</span></span>

2.  <span data-ttu-id="56268-190">從 Windows 安裝 CD 中，將*deploy.cab*解壓至系統磁片磁碟機的根目錄，或從 Microsoft 網站下載最新的部署工具更新。</span><span class="sxs-lookup"><span data-stu-id="56268-190">From the Windows installation CD, extract *deploy.cab* to the root of the system drive, or download the latest Deployment Tools update from the Microsoft Web site.</span></span>

    -   <span data-ttu-id="56268-191">針對 Windows 2000，請參閱適用[于 windows 2000 的部署工具更新](https://go.microsoft.com/fwlink/?LinkId=143001)。</span><span class="sxs-lookup"><span data-stu-id="56268-191">For Windows 2000, see [Deployment Tools update for Windows 2000](https://go.microsoft.com/fwlink/?LinkId=143001).</span></span>

    -   <span data-ttu-id="56268-192">若是 Windows XP，請參閱適用[于 WINDOWS xp 的部署工具更新](https://go.microsoft.com/fwlink/?LinkId=143000)。</span><span class="sxs-lookup"><span data-stu-id="56268-192">For Windows XP, see [Deployment Tools update for Windows XP](https://go.microsoft.com/fwlink/?LinkId=143000).</span></span>

3.  <span data-ttu-id="56268-193">執行**安裝管理員**（setupmgr.exe）。</span><span class="sxs-lookup"><span data-stu-id="56268-193">Run **Setup Manager** (setupmgr.exe).</span></span>

4.  <span data-ttu-id="56268-194">遵循 [安裝管理員] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="56268-194">Follow the Setup Manager wizard.</span></span>

<span data-ttu-id="56268-195">在已設定 Sysprep 且已建立 MED-V 工作區之後，必須執行 Sysprep。</span><span class="sxs-lookup"><span data-stu-id="56268-195">After Sysprep is configured and the MED-V workspace is created, Sysprep must be executed.</span></span>

**<span data-ttu-id="56268-196">若要執行 Sysprep</span><span class="sxs-lookup"><span data-stu-id="56268-196">To run Sysprep</span></span>**

1.  <span data-ttu-id="56268-197">從位於系統磁碟機根目錄的 Sysprep 資料夾中，執行系統準備工具（Sysprep.exe）。</span><span class="sxs-lookup"><span data-stu-id="56268-197">From the Sysprep folder located in the root of the system drive, run the System Preparation Tool (Sysprep.exe).</span></span>

2.  <span data-ttu-id="56268-198">在出現的 [警告訊息] 方塊中，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="56268-198">In the warning message box that appears, click **OK**.</span></span>

3.  <span data-ttu-id="56268-199">在 [ **Sysprep 屬性**] 對話方塊中，選取 [**不要重設啟用的寬限期**]，然後**使用 [最小化設定**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="56268-199">In the **Sysprep Properties** dialog box, select the **Don't reset grace period for activation** and **Use Mini-Setup** check boxes.</span></span>

4.  <span data-ttu-id="56268-200">按一下 [重新**封裝**]。</span><span class="sxs-lookup"><span data-stu-id="56268-200">Click **Reseal**.</span></span>

5.  <span data-ttu-id="56268-201">如果您對 [確認訊息] 方塊中所列的資訊不滿意，請按一下 [**取消**] 並變更選取專案。</span><span class="sxs-lookup"><span data-stu-id="56268-201">If you are not satisfied with the information listed in the confirmation message box that appears, click **Cancel** and change the selections.</span></span>

6.  <span data-ttu-id="56268-202">按一下 **[確定]** 以完成系統準備程式。</span><span class="sxs-lookup"><span data-stu-id="56268-202">Click **OK** to complete the system preparation process.</span></span>

## <a href="" id="bkmk-turningoffmicrosoftvirtualpc"></a><span data-ttu-id="56268-203">關閉 Microsoft Virtual PC</span><span class="sxs-lookup"><span data-stu-id="56268-203">Turning Off Microsoft Virtual PC</span></span>


<span data-ttu-id="56268-204">安裝並設定所有元件之後，請關閉 Microsoft Virtual PC，然後選取 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="56268-204">After all the components are installed and configured, close Microsoft Virtual PC and select **Turn Off**.</span></span>

## <span data-ttu-id="56268-205">相關主題</span><span class="sxs-lookup"><span data-stu-id="56268-205">Related topics</span></span>


<span data-ttu-id="56268-206">建立 MED-V 影像[如何設定腳本動作](how-to-set-up-script-actions.md)</span><span class="sxs-lookup"><span data-stu-id="56268-206">Creating a MED-V Image [How to Set Up Script Actions](how-to-set-up-script-actions.md)</span></span>









