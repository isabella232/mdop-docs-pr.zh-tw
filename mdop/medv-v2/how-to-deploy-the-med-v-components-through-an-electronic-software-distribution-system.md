---
title: 如何透過電子軟體發佈系統來部署 MED-V 元件
description: 如何透過電子軟體發佈系統來部署 MED-V 元件
author: dansimp
ms.assetid: 8a800bdf-6fa4-47b4-b417-df053289d4e8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: d772702c770340796fe770273146bd0308617a69
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810803"
---
# <span data-ttu-id="b8b81-103">如何透過電子軟體發佈系統來部署 MED-V 元件</span><span class="sxs-lookup"><span data-stu-id="b8b81-103">How to Deploy the MED-V Components Through an Electronic Software Distribution System</span></span>


<span data-ttu-id="b8b81-104">電子軟體發佈系統可協助您透過慢速或快速網路連線將軟體快速移至多部電腦。</span><span class="sxs-lookup"><span data-stu-id="b8b81-104">An electronic software distribution system can help you efficiently move software to many computers over slow or fast network connections.</span></span> <span data-ttu-id="b8b81-105">下列章節提供資訊與指示，以協助您使用軟體發佈系統在整個企業中部署 Microsoft 企業版桌面虛擬化（MED-V）2.0 元件。</span><span class="sxs-lookup"><span data-stu-id="b8b81-105">The following section provides information and instructions to help you deploy the Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 components throughout your enterprise by using a software distribution system.</span></span>

**<span data-ttu-id="b8b81-106">注意</span><span class="sxs-lookup"><span data-stu-id="b8b81-106">Note</span></span>**  
<span data-ttu-id="b8b81-107">無論您使用哪一個軟體發佈方案，您都必須熟悉特定解決方案的需求。</span><span class="sxs-lookup"><span data-stu-id="b8b81-107">Whichever software distribution solution that you use, you must be familiar with the requirements of your particular solution.</span></span> <span data-ttu-id="b8b81-108">如果您使用的是 System Center Configuration Manager 2007 R2 或更新版本，請參閱 Microsoft 技術文件庫中的[Configuration Manager 檔庫](https://go.microsoft.com/fwlink/?LinkId=66999)（ https://go.microsoft.com/fwlink/?LinkId=66999) 。</span><span class="sxs-lookup"><span data-stu-id="b8b81-108">If you are using System Center Configuration Manager 2007 R2 or a later version, see the [Configuration Manager Documentation Library](https://go.microsoft.com/fwlink/?LinkId=66999) in the Microsoft Technical Library (https://go.microsoft.com/fwlink/?LinkId=66999).</span></span>



**<span data-ttu-id="b8b81-109">重要</span><span class="sxs-lookup"><span data-stu-id="b8b81-109">Important</span></span>**  
<span data-ttu-id="b8b81-110">如果您使用 System Center Configuration Manager 2007 SP2，而您的 MED-V 工作區已設定為在**NAT**模式下運作，則虛擬機器會分類為網際網路用戶端，而且找不到最接近要下載內容的發佈點。</span><span class="sxs-lookup"><span data-stu-id="b8b81-110">If you are using System Center Configuration Manager 2007 SP2 and your MED-V workspaces are configured to operate in **NAT** mode, the virtual machines are classified as Internet-based clients and cannot find the closest distribution points from which to download content.</span></span>

<span data-ttu-id="b8b81-111">此[熱修復程式可改善由 med-v 管理的 vm 功能（針對](https://go.microsoft.com/fwlink/?LinkId=201088) https://go.microsoft.com/fwlink/?LinkId=201088) 由 med-v 管理且已設定為在**NAT**模式下運作的虛擬機器），增加新功能。</span><span class="sxs-lookup"><span data-stu-id="b8b81-111">The [hotfix to improve the functionality for VMs that are managed by MED-V](https://go.microsoft.com/fwlink/?LinkId=201088) (https://go.microsoft.com/fwlink/?LinkId=201088) adds new functionality to virtual machines that are managed by MED-V and that are configured to operate in **NAT** mode.</span></span> <span data-ttu-id="b8b81-112">新功能可讓虛擬機器存取最接近的發佈點。</span><span class="sxs-lookup"><span data-stu-id="b8b81-112">The new functionality lets virtual machines access the closest distribution points.</span></span> <span data-ttu-id="b8b81-113">因此，系統管理員可以以相同的方式管理虛擬機器與主機電腦。</span><span class="sxs-lookup"><span data-stu-id="b8b81-113">Therefore, the administrator can manage the virtual machine and the host computer in the same manner.</span></span> <span data-ttu-id="b8b81-114">此熱修復程式必須先安裝在網站伺服器上，然後再安裝在用戶端。</span><span class="sxs-lookup"><span data-stu-id="b8b81-114">This hotfix must be installed first on the site server and then on the client.</span></span>

<span data-ttu-id="b8b81-115">此更新公開提供。</span><span class="sxs-lookup"><span data-stu-id="b8b81-115">The update is publicly available.</span></span> <span data-ttu-id="b8b81-116">不過，系統可能會提示您接受 Microsoft 服務的合約。</span><span class="sxs-lookup"><span data-stu-id="b8b81-116">However, you might be prompted to accept an agreement for Microsoft Services.</span></span> <span data-ttu-id="b8b81-117">依照後續網頁上的提示進行，以取得此熱修復程式。</span><span class="sxs-lookup"><span data-stu-id="b8b81-117">Follow the prompts on the successive webpages to retrieve this hotfix.</span></span>



**<span data-ttu-id="b8b81-118">注意</span><span class="sxs-lookup"><span data-stu-id="b8b81-118">Note</span></span>**  
<span data-ttu-id="b8b81-119">您必須先安裝 MED-V 工作區包裝程式，然後建立您的 MED-V 工作區，才能透過您的軟體發佈系統部署 MED-V 元件。</span><span class="sxs-lookup"><span data-stu-id="b8b81-119">You must install the MED-V workspace packager and build your MED-V workspaces before you can deploy the MED-V components through your software distribution system.</span></span> <span data-ttu-id="b8b81-120">如需如何準備影像及建立 MED-V 工作區的詳細資訊，請參閱[med-v 的操作](operations-for-med-v.md)。</span><span class="sxs-lookup"><span data-stu-id="b8b81-120">For more information about how to prepare an image and to build your MED-V workspaces, see [Operations for MED-V](operations-for-med-v.md).</span></span>



**<span data-ttu-id="b8b81-121">使用軟體發佈系統部署 MED-V 元件</span><span class="sxs-lookup"><span data-stu-id="b8b81-121">To deploy the MED-V components by using a software distribution system</span></span>**

1.  <span data-ttu-id="b8b81-122">在電子軟體發佈系統中定義一組電腦和使用者作為電腦/使用者的目標群組。</span><span class="sxs-lookup"><span data-stu-id="b8b81-122">Define a group of computers and users in the electronic software distribution system as the target set of computers/users.</span></span>

2.  <span data-ttu-id="b8b81-123">針對每個需要發佈的 Microsoft 安裝檔建立套件。</span><span class="sxs-lookup"><span data-stu-id="b8b81-123">Create packages for each Microsoft installation file that needs to be distributed.</span></span> <span data-ttu-id="b8b81-124">下列是所需的檔案，以及它們必須安裝的順序：</span><span class="sxs-lookup"><span data-stu-id="b8b81-124">The following are the required files and the order in which they must be installed:</span></span>

    1.  <span data-ttu-id="b8b81-125">**Windows 虛擬電腦**–如果尚未安裝（需要重新開機電腦）。</span><span class="sxs-lookup"><span data-stu-id="b8b81-125">**Windows Virtual PC** – if not already installed (a computer restart is required).</span></span> <span data-ttu-id="b8b81-126">如需詳細資訊，請參閱[設定安裝必備元件](configure-installation-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="b8b81-126">For more information, see [Configure Installation Prerequisites](configure-installation-prerequisites.md).</span></span>

    2.  <span data-ttu-id="b8b81-127">**Windows 虛擬電腦新增和更新**–如果尚未安裝。</span><span class="sxs-lookup"><span data-stu-id="b8b81-127">**Windows Virtual PC Additions and Updates** – if not already installed.</span></span> <span data-ttu-id="b8b81-128">如需詳細資訊，請參閱[設定安裝必備元件](configure-installation-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="b8b81-128">For more information, see [Configure Installation Prerequisites](configure-installation-prerequisites.md).</span></span>

    3.  <span data-ttu-id="b8b81-129">**Med-v 主機代理安裝**檔案–安裝主機代理程式（med-v \ _HostAgent \ _Setup 安裝檔案）。</span><span class="sxs-lookup"><span data-stu-id="b8b81-129">**MED-V Host Agent Installation File** – installs the Host Agent (MED-V\_HostAgent\_Setup installation file).</span></span> <span data-ttu-id="b8b81-130">如需詳細資訊，請參閱[如何手動安裝 Med-v 主機代理程式](how-to-manually-install-the-med-v-host-agent.md)。</span><span class="sxs-lookup"><span data-stu-id="b8b81-130">For more information, see [How to Manually Install the MED-V Host Agent](how-to-manually-install-the-med-v-host-agent.md).</span></span>

        **<span data-ttu-id="b8b81-131">警告</span><span class="sxs-lookup"><span data-stu-id="b8b81-131">Warning</span></span>**  
        <span data-ttu-id="b8b81-132">在安裝 MED-V 主機代理程式前關閉 Internet Explorer，否則可能會在 URL 重新導向之後發生衝突。</span><span class="sxs-lookup"><span data-stu-id="b8b81-132">Close Internet Explorer before you install the MED-V Host Agent, otherwise conflicts can occur later with URL redirection.</span></span> <span data-ttu-id="b8b81-133">您也可以在發佈期間指定電腦重新開機來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="b8b81-133">You can also do this by specifying a computer restart during a distribution.</span></span>   

    4.  <span data-ttu-id="b8b81-134">**Med-v 工作區安裝程式、VHD 及安裝程式可執行檔**-在**Med-v 工作區包裝**程式中建立。</span><span class="sxs-lookup"><span data-stu-id="b8b81-134">**MED-V Workspace Installer, VHD, and Setup Executable** – created in the **MED-V Workspace Packager**.</span></span> <span data-ttu-id="b8b81-135">如需詳細資訊，請參閱[建立 Med-v 工作區套件](create-a-med-v-workspace-package.md)。</span><span class="sxs-lookup"><span data-stu-id="b8b81-135">For more information, see [Create a MED-V Workspace Package](create-a-med-v-workspace-package.md).</span></span>

        **<span data-ttu-id="b8b81-136">重要</span><span class="sxs-lookup"><span data-stu-id="b8b81-136">Important</span></span>**  
        <span data-ttu-id="b8b81-137">壓縮的虛擬硬碟檔案（medv）和 Setup executable 程式（setup.exe）必須與 MED-V 工作區安裝程式位於同一個資料夾中。</span><span class="sxs-lookup"><span data-stu-id="b8b81-137">The compressed virtual hard disk file (.medv) and the Setup executable program (setup.exe) must be in the same folder as the MED-V workspace installer.</span></span> <span data-ttu-id="b8b81-138">然後，透過執行 setup.exe 來安裝 MED-V 工作區安裝程式。</span><span class="sxs-lookup"><span data-stu-id="b8b81-138">Then, install the MED-V workspace installer by running setup.exe.</span></span>

        **<span data-ttu-id="b8b81-139">提示</span><span class="sxs-lookup"><span data-stu-id="b8b81-139">Tip</span></span>**  
        <span data-ttu-id="b8b81-140">因為從網路位置安裝 MED-V 時會發生問題，所以建議您在本機複製 MED-V 工作區安裝程式檔案，然後執行 setup.exe。</span><span class="sxs-lookup"><span data-stu-id="b8b81-140">Because problems that can occur when you install MED-V from a network location, we recommend that you copy the MED-V workspace setup files locally and then run setup.exe.</span></span>       

3.  <span data-ttu-id="b8b81-141">將套件設定為在安靜模式中執行（不需要使用者互動）。</span><span class="sxs-lookup"><span data-stu-id="b8b81-141">Configure the packages to run in silent mode (no user interaction is required).</span></span>

    <span data-ttu-id="b8b81-142">在安靜模式下執行時，不會提示您關閉 Internet Explorer （如果它正在執行），並提示您啟動 MED-V 主機代理程式。</span><span class="sxs-lookup"><span data-stu-id="b8b81-142">Running in silent mode eliminates the prompt to close Internet Explorer if it is running and the prompt to start the MED-V Host Agent.</span></span> <span data-ttu-id="b8b81-143">重新開機電腦時，會執行這兩個動作。</span><span class="sxs-lookup"><span data-stu-id="b8b81-143">Both actions are performed when the computer is restarted.</span></span>

    **<span data-ttu-id="b8b81-144">注意</span><span class="sxs-lookup"><span data-stu-id="b8b81-144">Note</span></span>**  
    <span data-ttu-id="b8b81-145">安裝 Windows Virtual 電腦時，必須重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="b8b81-145">Installation of Windows Virtual PC requires you to restart the computer.</span></span> <span data-ttu-id="b8b81-146">如果您隱含重新開機並忽略 MED-V 安裝所需的先決條件，您就可以建立單一安裝程式並同時安裝所有元件。</span><span class="sxs-lookup"><span data-stu-id="b8b81-146">You can create a single installation process and install all the components at the same time if you suppress the restart and ignore the prerequisites necessary for MED-V to install.</span></span> <span data-ttu-id="b8b81-147">您也可以使用命令列引數來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="b8b81-147">You can also do this by using command-line arguments.</span></span> <span data-ttu-id="b8b81-148">如需這些引數的範例，請參閱[使用批次檔案安裝 med-v 元件](#bkmk-batch)。</span><span class="sxs-lookup"><span data-stu-id="b8b81-148">For an example of these arguments, see [To install the MED-V components by using a batch file](#bkmk-batch).</span></span> <span data-ttu-id="b8b81-149">在電腦重新開機時，MED-V 會自動啟動。</span><span class="sxs-lookup"><span data-stu-id="b8b81-149">MED-V automatically starts when the computer is restarted.</span></span>

4.  <span data-ttu-id="b8b81-150">安裝 Windows 虛擬電腦之前，請先安裝 MED-V 及其元件。</span><span class="sxs-lookup"><span data-stu-id="b8b81-150">Install MED-V and its components before installing Windows Virtual PC.</span></span> <span data-ttu-id="b8b81-151">請參閱本主題稍後的範例批次檔案。</span><span class="sxs-lookup"><span data-stu-id="b8b81-151">See the example batch file later in this topic.</span></span>

    **<span data-ttu-id="b8b81-152">重要</span><span class="sxs-lookup"><span data-stu-id="b8b81-152">Important</span></span>**  
    <span data-ttu-id="b8b81-153">選取 [**忽略 \ _PREREQUISITES** ] 選項（如範例批次檔案所示），以便在所需的 VPC 元件之前安裝 med-v 元件。</span><span class="sxs-lookup"><span data-stu-id="b8b81-153">Select the **IGNORE\_PREREQUISITES** option as shown in the example batch file so that the MED-V components can be installed prior to the required VPC components.</span></span> <span data-ttu-id="b8b81-154">安裝 MED-V 元件，以允許單一重新開機。</span><span class="sxs-lookup"><span data-stu-id="b8b81-154">Install the MED-V components in this order to allow for the single restart.</span></span>

5.  <span data-ttu-id="b8b81-155">找出安裝所需的任何其他需求，以及軟體發佈系統（例如目標平臺和可用磁碟空間）。</span><span class="sxs-lookup"><span data-stu-id="b8b81-155">Identify any other requirements necessary for the installation and for your software distribution system, such as target platforms and the free disk space.</span></span>

6.  <span data-ttu-id="b8b81-156">將套件指派給電腦/使用者的目標群組。</span><span class="sxs-lookup"><span data-stu-id="b8b81-156">Assign the packages to the target set of computers/users.</span></span>

    <span data-ttu-id="b8b81-157">當電腦執行時，軟體發佈系統用戶端會辨識新套件可用，並開始根據定義和需求來安裝套件。</span><span class="sxs-lookup"><span data-stu-id="b8b81-157">As computers are running, the software distribution system client recognizes that new packages are available and begins to install the packages per the definition and requirements.</span></span> <span data-ttu-id="b8b81-158">安裝應以緘默模式循序執行。</span><span class="sxs-lookup"><span data-stu-id="b8b81-158">The installations should run sequentially in silent mode.</span></span> <span data-ttu-id="b8b81-159">我們建議您將它做為單一處理程式，而不需要重新開機，直到安裝完所有套件為止。</span><span class="sxs-lookup"><span data-stu-id="b8b81-159">We recommend that this is performed as a single process that does not require a restart until all the packages are installed.</span></span>

7.  <span data-ttu-id="b8b81-160">安裝完成後，請重新開機更新的電腦。</span><span class="sxs-lookup"><span data-stu-id="b8b81-160">After the installations are complete, restart the updated computers.</span></span>

    <span data-ttu-id="b8b81-161">根據軟體發佈系統，您可以排程重新開機電腦，或最終使用者可以在正常運作期間手動重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="b8b81-161">Depending on the software distribution system, you can schedule a restart of the computer or the end users can restart the computers manually during their regular work.</span></span> <span data-ttu-id="b8b81-162">重新開機電腦之後，MED-V 會在使用者登入時自動啟動。</span><span class="sxs-lookup"><span data-stu-id="b8b81-162">After the computer is restarted, MED-V automatically starts after an end user logs on.</span></span> <span data-ttu-id="b8b81-163">當 MED-V 第一次啟動時，會第一次執行安裝程式。</span><span class="sxs-lookup"><span data-stu-id="b8b81-163">When MED-V starts for the first time, it runs first time setup.</span></span>

<span data-ttu-id="b8b81-164">第一次安裝開始，可能需要幾分鐘的時間完成，視您指定的虛擬硬碟大小以及啟動時所套用到 MED-V 工作區的原則數而定。</span><span class="sxs-lookup"><span data-stu-id="b8b81-164">First time setup starts and might take several minutes to finish, depending on the size of the virtual hard disk that you specified and the number of policies applied to the MED-V workspace on startup.</span></span> <span data-ttu-id="b8b81-165">使用者可以透過在通知區域中觀察 MED-V 圖示來追蹤進度。</span><span class="sxs-lookup"><span data-stu-id="b8b81-165">The end user can track the progress by watching the MED-V icon in the notification area.</span></span> <span data-ttu-id="b8b81-166">如需第一次設定的詳細資訊，請參閱[med-v 2.0 部署概覽](med-v-20-deployment-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="b8b81-166">For more information about first time setup, see [MED-V 2.0 Deployment Overview](med-v-20-deployment-overview.md).</span></span>

<a href="" id="bkmk-batch"></a>**<span data-ttu-id="b8b81-167">使用批次處理檔案安裝 MED-V 元件</span><span class="sxs-lookup"><span data-stu-id="b8b81-167">To install the MED-V components by using a batch file</span></span>**

1.  <span data-ttu-id="b8b81-168">使用系統管理認證在命令提示字元執行安裝。</span><span class="sxs-lookup"><span data-stu-id="b8b81-168">Run the installation at a command prompt with administrative credentials.</span></span>

2.  <span data-ttu-id="b8b81-169">將每個元件部署到單一目錄。</span><span class="sxs-lookup"><span data-stu-id="b8b81-169">Deploy each component to a single directory.</span></span> <span data-ttu-id="b8b81-170">如果從網路共用執行，則需要較長的時間來解壓縮 medv 檔案。</span><span class="sxs-lookup"><span data-stu-id="b8b81-170">If run from a network share, a longer time is required to decompress the .medv file.</span></span>

3.  <span data-ttu-id="b8b81-171">最佳做法是指定在 MED-V 主機代理程式和 MED-V 工作區套件檔案之後，安裝 Windows 虛擬電腦和 Windows 虛擬電腦熱修復程式。</span><span class="sxs-lookup"><span data-stu-id="b8b81-171">As a best practice, specify that Windows Virtual PC and the Windows Virtual PC hotfix are installed after the MED-V Host Agent and the MED-V workspace package files.</span></span> <span data-ttu-id="b8b81-172">這表示 Windows 更新不會對安裝程式造成任何干擾，只要需要重新開機即可。</span><span class="sxs-lookup"><span data-stu-id="b8b81-172">This means that Windows Update will not cause any interference with the installation process by requiring a restart.</span></span>

4.  <span data-ttu-id="b8b81-173">批次處理檔案完成後，請重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="b8b81-173">Restart the computer after the batch file is finished.</span></span>

<span data-ttu-id="b8b81-174">重新開機之後，系統會提示使用者第一次執行安裝並完成 MED-V 的設定。</span><span class="sxs-lookup"><span data-stu-id="b8b81-174">After the restart, the user is prompted to run first time setup and complete the configuration of MED-V.</span></span>

<span data-ttu-id="b8b81-175">下列含有指定引數的範例說明如何在單一程式中安裝64位 MED-V 元件：</span><span class="sxs-lookup"><span data-stu-id="b8b81-175">The following example, with the specified arguments, shows how to install 64-bit MED-V components in a single process:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b8b81-176">引數</span><span class="sxs-lookup"><span data-stu-id="b8b81-176">Argument</span></span></th>
<th align="left"><span data-ttu-id="b8b81-177">描述</span><span class="sxs-lookup"><span data-stu-id="b8b81-177">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b8b81-178">/norestart</span><span class="sxs-lookup"><span data-stu-id="b8b81-178">/norestart</span></span></p></td>
<td align="left"><p><span data-ttu-id="b8b81-179">防止安裝 Windows Virtual PC 和 Windows Virtual PC 更新，因為重新開機主機電腦。</span><span class="sxs-lookup"><span data-stu-id="b8b81-179">Prevents the installation of Windows Virtual PC and the Windows Virtual PC update from restarting the host computer.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b8b81-180">/quiet</span><span class="sxs-lookup"><span data-stu-id="b8b81-180">/quiet</span></span></p></td>
<td align="left"><p><span data-ttu-id="b8b81-181">在沒有使用者互動的安靜模式中安裝 MED-V 元件。</span><span class="sxs-lookup"><span data-stu-id="b8b81-181">Installs the MED-V components in quiet mode without user interaction.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b8b81-182">/qn</span><span class="sxs-lookup"><span data-stu-id="b8b81-182">/qn</span></span></p></td>
<td align="left"><p><span data-ttu-id="b8b81-183">安裝 MED-V 元件（不含使用者介面）。</span><span class="sxs-lookup"><span data-stu-id="b8b81-183">Installs the MED-V components without a user interface.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b8b81-184">IGNORE_PREREQUISITES</span><span class="sxs-lookup"><span data-stu-id="b8b81-184">IGNORE_PREREQUISITES</span></span></p></td>
<td align="left"><p><span data-ttu-id="b8b81-185">安裝而不檢查 Windows 虛擬電腦。</span><span class="sxs-lookup"><span data-stu-id="b8b81-185">Installs without checking for Windows Virtual PC.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="b8b81-186">注意</span><span class="sxs-lookup"><span data-stu-id="b8b81-186">Note</span></span></strong><br/><p><span data-ttu-id="b8b81-187">如果您是在此安裝中安裝 Windows 虛擬電腦，請只指定此引數。</span><span class="sxs-lookup"><span data-stu-id="b8b81-187">Only specify this argument if you are installing Windows Virtual PC as part of this installation.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b8b81-188">OVERWRITEVHD</span><span class="sxs-lookup"><span data-stu-id="b8b81-188">OVERWRITEVHD</span></span></p></td>
<td align="left"><p><span data-ttu-id="b8b81-189">強制安裝 MED-V 工作區，並防止它可能產生的任何提示。</span><span class="sxs-lookup"><span data-stu-id="b8b81-189">Forces the installation of the MED-V workspace and prevents any prompts that it might generate.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="b8b81-190">範例</span><span class="sxs-lookup"><span data-stu-id="b8b81-190">Example</span></span>


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

## <span data-ttu-id="b8b81-191">相關主題</span><span class="sxs-lookup"><span data-stu-id="b8b81-191">Related topics</span></span>


[<span data-ttu-id="b8b81-192">MED-V 2.0 部署概觀</span><span class="sxs-lookup"><span data-stu-id="b8b81-192">MED-V 2.0 Deployment Overview</span></span>](med-v-20-deployment-overview.md)

[<span data-ttu-id="b8b81-193">部署 MED-V 元件</span><span class="sxs-lookup"><span data-stu-id="b8b81-193">Deploy the MED-V Components</span></span>](deploy-the-med-v-components.md)









