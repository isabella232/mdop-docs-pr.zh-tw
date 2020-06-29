---
title: 如何透過電子軟體發佈系統來部署 MED-V 工作區
description: 如何透過電子軟體發佈系統來部署 MED-V 工作區
author: dansimp
ms.assetid: b5134c35-e1de-470c-93f8-ead6218d9dce
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 56d21b0c2f010f63c04056d9fadd7763531bd9d5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800232"
---
# <span data-ttu-id="a938c-103">如何透過電子軟體發佈系統來部署 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="a938c-103">How to Deploy a MED-V Workspace Through an Electronic Software Distribution System</span></span>


<span data-ttu-id="a938c-104">電子軟體發佈系統的設計目的是，透過慢速或快速網路連線將軟體快速移至許多不同的電腦。</span><span class="sxs-lookup"><span data-stu-id="a938c-104">An electronic software distribution system is designed to efficiently move software to many different computers over slow or fast network connections.</span></span> <span data-ttu-id="a938c-105">下列章節提供資訊與指示，以協助您使用軟體發佈系統在整個企業中部署 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="a938c-105">The following section provides information and instructions to help you deploy your MED-V workspace throughout your enterprise by using a software distribution system.</span></span>

**<span data-ttu-id="a938c-106">注意</span><span class="sxs-lookup"><span data-stu-id="a938c-106">Note</span></span>**  
<span data-ttu-id="a938c-107">無論您使用哪一個軟體發佈方案，您都必須熟悉特定解決方案的需求。</span><span class="sxs-lookup"><span data-stu-id="a938c-107">Whichever software distribution solution that you use, you must be familiar with the requirements of your particular solution.</span></span> <span data-ttu-id="a938c-108">如果您使用的是 System Center Configuration Manager 2007 R2 或更新版本，請參閱 Microsoft 技術文件庫中的[Configuration Manager 檔庫](https://go.microsoft.com/fwlink/?LinkId=66999)（ https://go.microsoft.com/fwlink/?LinkId=66999) 。</span><span class="sxs-lookup"><span data-stu-id="a938c-108">If you are using System Center Configuration Manager 2007 R2 or a later version, see the [Configuration Manager Documentation Library](https://go.microsoft.com/fwlink/?LinkId=66999) in the Microsoft Technical Library (https://go.microsoft.com/fwlink/?LinkId=66999).</span></span>



**<span data-ttu-id="a938c-109">重要</span><span class="sxs-lookup"><span data-stu-id="a938c-109">Important</span></span>**  
<span data-ttu-id="a938c-110">如果您使用 System Center Configuration Manager 2007 SP2，而您的 MED-V 工作區已設定為在**NAT**模式下運作，則虛擬機器會分類為網際網路用戶端，而且找不到最接近要下載內容的發佈點。</span><span class="sxs-lookup"><span data-stu-id="a938c-110">If you are using System Center Configuration Manager 2007 SP2 and your MED-V workspaces are configured to operate in **NAT** mode, the virtual machines are classified as Internet-based clients and cannot find the closest distribution points from which to download content.</span></span>

<span data-ttu-id="a938c-111">此[熱修復程式可改善由 med-v 管理的 vm 功能（針對](https://go.microsoft.com/fwlink/?LinkId=201088) https://go.microsoft.com/fwlink/?LinkId=201088) 由 med-v 管理且已設定為在**NAT**模式下運作的虛擬機器），增加新功能。</span><span class="sxs-lookup"><span data-stu-id="a938c-111">The [hotfix to improve the functionality for VMs that are managed by MED-V](https://go.microsoft.com/fwlink/?LinkId=201088) (https://go.microsoft.com/fwlink/?LinkId=201088) adds new functionality to virtual machines that are managed by MED-V and that are configured to operate in **NAT** mode.</span></span> <span data-ttu-id="a938c-112">新功能可讓虛擬機器存取最接近的發佈點。</span><span class="sxs-lookup"><span data-stu-id="a938c-112">The new functionality lets virtual machines access the closest distribution points.</span></span> <span data-ttu-id="a938c-113">因此，系統管理員可以以相同的方式管理虛擬機器與主機電腦。</span><span class="sxs-lookup"><span data-stu-id="a938c-113">Therefore, the administrator can manage the virtual machine and the host computer in the same manner.</span></span> <span data-ttu-id="a938c-114">此熱修復程式必須先安裝在網站伺服器上，然後再安裝在用戶端。</span><span class="sxs-lookup"><span data-stu-id="a938c-114">This hotfix must be installed first on the site server and then on the client.</span></span>

<span data-ttu-id="a938c-115">此更新公開提供。</span><span class="sxs-lookup"><span data-stu-id="a938c-115">The update is publicly available.</span></span> <span data-ttu-id="a938c-116">不過，系統可能會提示您接受 Microsoft 服務的合約。</span><span class="sxs-lookup"><span data-stu-id="a938c-116">However, you might be prompted to accept an agreement for Microsoft Services.</span></span> <span data-ttu-id="a938c-117">依照後續網頁上的提示進行，以取得此熱修復程式。</span><span class="sxs-lookup"><span data-stu-id="a938c-117">Follow the prompts on the successive webpages to retrieve this hotfix.</span></span>



<span data-ttu-id="a938c-118">您也可以使用批次檔案將 MED-V 元件部署在一起，但這需要在安裝 Windows Virtual PC 之後重新開機。</span><span class="sxs-lookup"><span data-stu-id="a938c-118">You can also deploy the MED-V components together by using a batch file, but this requires a restart after the installation of Windows Virtual PC.</span></span> <span data-ttu-id="a938c-119">若要略過這項需求，您可以在安裝所有元件之後指定單一重新開機。</span><span class="sxs-lookup"><span data-stu-id="a938c-119">To bypass this requirement, you can specify a single restart after all of the components are installed.</span></span> <span data-ttu-id="a938c-120">單一重新開機也會自動啟動 MED-V-V，因為 MED-V 工作區安裝會在 RUNKEY 中放置一個專案。</span><span class="sxs-lookup"><span data-stu-id="a938c-120">The single restart also automatically starts MED-V because the MED-V workspace installation places an entry in the RUNKEY.</span></span>

**<span data-ttu-id="a938c-121">使用軟體發佈系統來部署 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="a938c-121">To deploy a MED-V workspace by using a software distribution system</span></span>**

1.  <span data-ttu-id="a938c-122">在電子軟體發佈系統中定義一組電腦和使用者作為電腦/使用者的目標群組。</span><span class="sxs-lookup"><span data-stu-id="a938c-122">Define a group of computers and users in the electronic software distribution system as the target set of computers/users.</span></span>

2.  <span data-ttu-id="a938c-123">針對每個需要發佈的 Microsoft 安裝檔建立套件。</span><span class="sxs-lookup"><span data-stu-id="a938c-123">Create packages for each Microsoft installation file that needs to be distributed.</span></span> <span data-ttu-id="a938c-124">下列是所需的檔案，以及它們必須安裝的順序：</span><span class="sxs-lookup"><span data-stu-id="a938c-124">The following are the required files and the order in which they must be installed:</span></span>

    1.  <span data-ttu-id="a938c-125">**Windows 虛擬電腦**–如果尚未安裝（需要重新開機電腦）。</span><span class="sxs-lookup"><span data-stu-id="a938c-125">**Windows Virtual PC** – if not already installed (a computer restart is required).</span></span> <span data-ttu-id="a938c-126">如需詳細資訊，請參閱[設定安裝必備元件](configure-installation-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="a938c-126">For more information, see [Configure Installation Prerequisites](configure-installation-prerequisites.md).</span></span>

    2.  <span data-ttu-id="a938c-127">**Windows 虛擬電腦新增和更新**–如果尚未安裝。</span><span class="sxs-lookup"><span data-stu-id="a938c-127">**Windows Virtual PC Additions and Updates** – if not already installed.</span></span> <span data-ttu-id="a938c-128">如需詳細資訊，請參閱[設定安裝必備元件](configure-installation-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="a938c-128">For more information, see [Configure Installation Prerequisites](configure-installation-prerequisites.md).</span></span>

    3.  <span data-ttu-id="a938c-129">**Med-v 主機代理安裝**檔案–安裝主機代理程式（med-v \ _HostAgent \ _Setup 安裝檔案）。</span><span class="sxs-lookup"><span data-stu-id="a938c-129">**MED-V Host Agent Installation File** – installs the Host Agent (MED-V\_HostAgent\_Setup installation file).</span></span> <span data-ttu-id="a938c-130">如需詳細資訊，請參閱[如何手動安裝 Med-v 主機代理程式](how-to-manually-install-the-med-v-host-agent.md)。</span><span class="sxs-lookup"><span data-stu-id="a938c-130">For more information, see [How to Manually Install the MED-V Host Agent](how-to-manually-install-the-med-v-host-agent.md).</span></span>

        **<span data-ttu-id="a938c-131">警告</span><span class="sxs-lookup"><span data-stu-id="a938c-131">Warning</span></span>**  
        <span data-ttu-id="a938c-132">在安裝 MED-V 主機代理程式前關閉 Internet Explorer，否則可能會在 URL 重新導向之後發生衝突。</span><span class="sxs-lookup"><span data-stu-id="a938c-132">Close Internet Explorer before you install the MED-V Host Agent, otherwise conflicts can occur later with URL redirection.</span></span> <span data-ttu-id="a938c-133">您也可以在發佈期間指定電腦重新開機來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="a938c-133">You can also do this by specifying a computer restart during a distribution.</span></span>



    4.  <span data-ttu-id="a938c-134">**Med-v 工作區安裝程式、VHD 及安裝程式可執行檔**-在**Med-v 工作區包裝**程式中建立。</span><span class="sxs-lookup"><span data-stu-id="a938c-134">**MED-V Workspace Installer, VHD, and Setup Executable** – created in the **MED-V Workspace Packager**.</span></span> <span data-ttu-id="a938c-135">如需詳細資訊，請參閱[建立 Med-v 工作區套件](create-a-med-v-workspace-package.md)。</span><span class="sxs-lookup"><span data-stu-id="a938c-135">For more information, see [Create a MED-V Workspace Package](create-a-med-v-workspace-package.md).</span></span>

        **<span data-ttu-id="a938c-136">重要</span><span class="sxs-lookup"><span data-stu-id="a938c-136">Important</span></span>**  
        <span data-ttu-id="a938c-137">壓縮的虛擬硬碟檔案（medv）和 Setup executable 程式（setup.exe）必須與 MED-V 工作區安裝程式位於同一個資料夾中。</span><span class="sxs-lookup"><span data-stu-id="a938c-137">The compressed virtual hard disk file (.medv) and the Setup executable program (setup.exe) must be in the same folder as the MED-V workspace installer.</span></span> <span data-ttu-id="a938c-138">然後，透過執行 setup.exe 來安裝 MED-V 工作區安裝程式。</span><span class="sxs-lookup"><span data-stu-id="a938c-138">Then, install the MED-V workspace installer by running setup.exe.</span></span>



~~~
    **Tip**  
    Because problems can occur when you install MED-V from a network location, we recommend that you copy the MED-V workspace setup files locally and then run setup.exe.
~~~



3. <span data-ttu-id="a938c-139">將套件設定為在安靜模式中執行（不需要使用者互動）。</span><span class="sxs-lookup"><span data-stu-id="a938c-139">Configure the packages to run in silent mode (no user interaction is required).</span></span>

   <span data-ttu-id="a938c-140">在安靜模式下執行時，不會提示您關閉 Internet Explorer （如果它正在執行），並提示您啟動 MED-V 主機代理程式。</span><span class="sxs-lookup"><span data-stu-id="a938c-140">Running in silent mode eliminates the prompt to close Internet Explorer if it is running and the prompt to start the MED-V Host Agent.</span></span> <span data-ttu-id="a938c-141">重新開機電腦時，會執行這兩個動作。</span><span class="sxs-lookup"><span data-stu-id="a938c-141">Both actions are performed when the computer is restarted.</span></span>

   **<span data-ttu-id="a938c-142">注意</span><span class="sxs-lookup"><span data-stu-id="a938c-142">Note</span></span>**  
   <span data-ttu-id="a938c-143">安裝 Windows Virtual 電腦時，必須重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="a938c-143">Installation of Windows Virtual PC requires you to restart the computer.</span></span> <span data-ttu-id="a938c-144">如果您隱含重新開機並忽略 MED-V 安裝所需的先決條件，您就可以建立單一安裝程式並同時安裝所有元件。</span><span class="sxs-lookup"><span data-stu-id="a938c-144">You can create a single installation process and install all the components at the same time if you suppress the restart and ignore the prerequisites necessary for MED-V to install.</span></span> <span data-ttu-id="a938c-145">您也可以使用命令列引數來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="a938c-145">You can also do this by using command-line arguments.</span></span> <span data-ttu-id="a938c-146">如需這些引數的範例，請參閱[如何透過電子軟體發佈系統部署 Med-v 元件](how-to-deploy-the-med-v-components-through-an-electronic-software-distribution-system.md#bkmk-batch)。</span><span class="sxs-lookup"><span data-stu-id="a938c-146">For an example of these arguments, see [How to Deploy the MED-V Components Through an Electronic Software Distribution System](how-to-deploy-the-med-v-components-through-an-electronic-software-distribution-system.md#bkmk-batch).</span></span> <span data-ttu-id="a938c-147">在電腦重新開機時，MED-V 會自動啟動。</span><span class="sxs-lookup"><span data-stu-id="a938c-147">MED-V automatically starts when the computer is restarted.</span></span>



4. <span data-ttu-id="a938c-148">安裝 Windows 虛擬電腦之前，請先安裝 MED-V 及其元件。</span><span class="sxs-lookup"><span data-stu-id="a938c-148">Install MED-V and its components before installing Windows Virtual PC.</span></span> <span data-ttu-id="a938c-149">請參閱本主題稍後的範例批次檔案。</span><span class="sxs-lookup"><span data-stu-id="a938c-149">See the example batch file later in this topic.</span></span>

   **<span data-ttu-id="a938c-150">重要</span><span class="sxs-lookup"><span data-stu-id="a938c-150">Important</span></span>**  
   <span data-ttu-id="a938c-151">選取 [**忽略 \ _PREREQUISITES** ] 選項（如範例批次檔案所示），以便在所需的 VPC 元件之前安裝 med-v 元件。</span><span class="sxs-lookup"><span data-stu-id="a938c-151">Select the **IGNORE\_PREREQUISITES** option as shown in the example batch file so that the MED-V components can be installed prior to the required VPC components.</span></span> <span data-ttu-id="a938c-152">安裝 MED-V 元件，以允許單一重新開機。</span><span class="sxs-lookup"><span data-stu-id="a938c-152">Install the MED-V components in this order to allow for the single restart.</span></span>



5. <span data-ttu-id="a938c-153">找出安裝所需的任何其他需求，以及軟體發佈系統（例如目標平臺和可用磁碟空間）。</span><span class="sxs-lookup"><span data-stu-id="a938c-153">Identify any other requirements necessary for the installation and for your software distribution system, such as target platforms and the free disk space.</span></span>

6. <span data-ttu-id="a938c-154">將套件指派給電腦/使用者的目標群組。</span><span class="sxs-lookup"><span data-stu-id="a938c-154">Assign the packages to the target set of computers/users.</span></span>

   <span data-ttu-id="a938c-155">當電腦執行時，軟體發佈系統用戶端會辨識新套件可用，並開始根據定義和需求來安裝套件。</span><span class="sxs-lookup"><span data-stu-id="a938c-155">As computers are running, the software distribution system client recognizes that new packages are available and begins to install the packages per the definition and requirements.</span></span> <span data-ttu-id="a938c-156">安裝應以無提示循序執行。</span><span class="sxs-lookup"><span data-stu-id="a938c-156">The installations should run sequentially in silent.</span></span> <span data-ttu-id="a938c-157">我們建議您將它做為單一處理程式，而不需要重新開機，直到安裝完所有套件為止。</span><span class="sxs-lookup"><span data-stu-id="a938c-157">We recommend that this is performed as a single process that does not require a restart until all the packages are installed.</span></span>

7. <span data-ttu-id="a938c-158">安裝完成後，請重新開機更新的電腦。</span><span class="sxs-lookup"><span data-stu-id="a938c-158">After the installations are complete, restart the updated computers.</span></span>

   <span data-ttu-id="a938c-159">根據軟體發佈系統，您可以排程重新開機電腦，或最終使用者可以在正常運作期間手動重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="a938c-159">Depending on the software distribution system, you can schedule a restart of the computer or the end users can restart the computers manually during their regular work.</span></span> <span data-ttu-id="a938c-160">重新開機電腦之後，MED-V 會在使用者登入時自動啟動。</span><span class="sxs-lookup"><span data-stu-id="a938c-160">After the computer is restarted, MED-V automatically starts after an end user logs on.</span></span> <span data-ttu-id="a938c-161">當 MED-V 第一次啟動時，會第一次執行安裝程式。</span><span class="sxs-lookup"><span data-stu-id="a938c-161">When MED-V starts for the first time, it runs first time setup.</span></span>

<span data-ttu-id="a938c-162">第一次安裝開始，可能需要幾分鐘的時間完成，視您指定的虛擬硬碟大小以及啟動時所套用到 MED-V 工作區的原則數而定。</span><span class="sxs-lookup"><span data-stu-id="a938c-162">First time setup starts and might take several minutes to finish, depending on the size of the virtual hard disk that you specified and the number of policies applied to the MED-V workspace on startup.</span></span> <span data-ttu-id="a938c-163">使用者可以透過在通知區域中觀察 MED-V 圖示來追蹤進度。</span><span class="sxs-lookup"><span data-stu-id="a938c-163">The end user can track the progress by watching the MED-V icon in the notification area.</span></span> <span data-ttu-id="a938c-164">如需第一次設定的詳細資訊，請參閱[med-v 2.0 部署概覽](med-v-20-deployment-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="a938c-164">For more information about first time setup, see [MED-V 2.0 Deployment Overview](med-v-20-deployment-overview.md).</span></span>

**<span data-ttu-id="a938c-165">使用批次處理檔案安裝 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="a938c-165">To install the MED-V workspace by using a batch file</span></span>**

1.  <span data-ttu-id="a938c-166">使用系統管理認證在命令提示字元執行安裝。</span><span class="sxs-lookup"><span data-stu-id="a938c-166">Run the installation at a command prompt with administrative credentials.</span></span>

2.  <span data-ttu-id="a938c-167">將每個元件部署到單一目錄。</span><span class="sxs-lookup"><span data-stu-id="a938c-167">Deploy each component to a single directory.</span></span> <span data-ttu-id="a938c-168">如果從網路共用執行，則需要較長的時間來解壓縮 medv 檔案。</span><span class="sxs-lookup"><span data-stu-id="a938c-168">If run from a network share, a longer time is required to decompress the .medv file.</span></span>

3.  <span data-ttu-id="a938c-169">最佳做法是指定在 MED-V 主機代理程式和 MED-V 工作區套件檔案之後，安裝 Windows 虛擬電腦和 Windows 虛擬電腦熱修復程式。</span><span class="sxs-lookup"><span data-stu-id="a938c-169">As a best practice, specify that Windows Virtual PC and the Windows Virtual PC hotfix are installed after the MED-V Host Agent and the MED-V workspace package files.</span></span> <span data-ttu-id="a938c-170">這表示 Windows 更新不會對安裝程式造成任何干擾，只要需要重新開機即可。</span><span class="sxs-lookup"><span data-stu-id="a938c-170">This means that Windows Update will not cause any interference with the installation process by requiring a restart.</span></span>

4.  <span data-ttu-id="a938c-171">批次處理檔案完成後，請重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="a938c-171">Restart the computer after the batch file is finished.</span></span>

<span data-ttu-id="a938c-172">重新開機之後，系統會提示使用者第一次執行安裝並完成 MED-V 的設定。</span><span class="sxs-lookup"><span data-stu-id="a938c-172">After the restart, the user is prompted to run first time setup and complete the configuration of MED-V.</span></span>

<span data-ttu-id="a938c-173">下列含有指定引數的範例說明如何在單一程式中安裝64位 MED-V 元件：</span><span class="sxs-lookup"><span data-stu-id="a938c-173">The following example, with the specified arguments, shows how to install 64-bit MED-V components in a single process:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a938c-174">引數</span><span class="sxs-lookup"><span data-stu-id="a938c-174">Argument</span></span></th>
<th align="left"><span data-ttu-id="a938c-175">描述</span><span class="sxs-lookup"><span data-stu-id="a938c-175">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a938c-176">/norestart</span><span class="sxs-lookup"><span data-stu-id="a938c-176">/norestart</span></span></p></td>
<td align="left"><p><span data-ttu-id="a938c-177">防止安裝 Windows Virtual PC 和 Windows Virtual PC 更新，因為重新開機主機電腦。</span><span class="sxs-lookup"><span data-stu-id="a938c-177">Prevents the installation of Windows Virtual PC and the Windows Virtual PC update from restarting the host computer.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a938c-178">/quiet</span><span class="sxs-lookup"><span data-stu-id="a938c-178">/quiet</span></span></p></td>
<td align="left"><p><span data-ttu-id="a938c-179">在沒有使用者互動的安靜模式中安裝 MED-V 元件。</span><span class="sxs-lookup"><span data-stu-id="a938c-179">Installs the MED-V components in quiet mode without user interaction.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a938c-180">/qn</span><span class="sxs-lookup"><span data-stu-id="a938c-180">/qn</span></span></p></td>
<td align="left"><p><span data-ttu-id="a938c-181">安裝 MED-V 元件（不含使用者介面）。</span><span class="sxs-lookup"><span data-stu-id="a938c-181">Installs the MED-V components without a user interface.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a938c-182">IGNORE_PREREQUISITES</span><span class="sxs-lookup"><span data-stu-id="a938c-182">IGNORE_PREREQUISITES</span></span></p></td>
<td align="left"><p><span data-ttu-id="a938c-183">安裝而不檢查 Windows 虛擬電腦。</span><span class="sxs-lookup"><span data-stu-id="a938c-183">Installs without checking for Windows Virtual PC.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="a938c-184">注意</span><span class="sxs-lookup"><span data-stu-id="a938c-184">Note</span></span></strong><br/><p><span data-ttu-id="a938c-185">如果您是在此安裝中安裝 Windows 虛擬電腦，請只指定此引數。</span><span class="sxs-lookup"><span data-stu-id="a938c-185">Only specify this argument if you are installing Windows Virtual PC as part of this installation.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a938c-186">OVERWRITEVHD</span><span class="sxs-lookup"><span data-stu-id="a938c-186">OVERWRITEVHD</span></span></p></td>
<td align="left"><p><span data-ttu-id="a938c-187">強制安裝 MED-V 工作區，並防止它可能產生的任何提示。</span><span class="sxs-lookup"><span data-stu-id="a938c-187">Forces the installation of the MED-V workspace and prevents any prompts that it might generate.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="a938c-188">範例</span><span class="sxs-lookup"><span data-stu-id="a938c-188">Example</span></span>


``` syntax
:: Install MED-V and the Pre-requisites

:: Install the MED-V Host Agent: install in quiet mode, ignore that Windows Virtual PC is not installed completely, and log results
start /WAIT .\MED-V_HostAgent_Setup.exe /qn IGNORE_PREREQUISITES=1 /l* %TEMP%\MEDVhost.log

:: Install the MED-V Workspace: install in quiet mode, Overwrite the VHD if it already exists, and log results
start /WAIT .\setup.exe /qn OVERWRITEVHD=1 /l* %TEMP%\MEDVworkspace.log

:: Install Windows Virtual PC: install in quiet mode and do not reboot
start /WAIT wusa.exe Windows6.1-KB958559-x64.msu /norestart /quiet

:: Install Windows Virtual PC patch to support non-HAV: install in quiet mode and do not reboot
wusa.exe Windows6.1-KB977206-x64.msu /norestart /quiet

:: After successful installation of the above components, a reboot of the host computer is required to complete installation.
```

## <span data-ttu-id="a938c-189">相關主題</span><span class="sxs-lookup"><span data-stu-id="a938c-189">Related topics</span></span>


[<span data-ttu-id="a938c-190">MED-V 2.0 部署概觀</span><span class="sxs-lookup"><span data-stu-id="a938c-190">MED-V 2.0 Deployment Overview</span></span>](med-v-20-deployment-overview.md)

[<span data-ttu-id="a938c-191">如何在 Windows 7 映像中部署 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="a938c-191">How to Deploy a MED-V Workspace in a Windows 7 Image</span></span>](how-to-deploy-a-med-v-workspace-in-a-windows-7-image.md)









