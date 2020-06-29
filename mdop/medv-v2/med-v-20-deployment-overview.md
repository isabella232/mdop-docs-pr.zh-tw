---
title: MED-V 2.0 部署概觀
description: MED-V 2.0 部署概觀
author: dansimp
ms.assetid: 0b8998ea-c46f-4c81-a304-f380b2ed7cf8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ec2a5f86ac7d63295bd7c550bcb0a90004987e42
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811558"
---
# <span data-ttu-id="80554-103">MED-V 2.0 部署概觀</span><span class="sxs-lookup"><span data-stu-id="80554-103">MED-V 2.0 Deployment Overview</span></span>


<span data-ttu-id="80554-104">本節提供有關如何安裝及部署 Microsoft Enterprise 桌面虛擬化（MED-V）2.0 的一般資訊與指示。</span><span class="sxs-lookup"><span data-stu-id="80554-104">This section provides general information and instructions about how to install and deploy Microsoft Enterprise Desktop Virtualization (MED-V) 2.0.</span></span>

## <span data-ttu-id="80554-105">概觀</span><span class="sxs-lookup"><span data-stu-id="80554-105">Overview</span></span>


<span data-ttu-id="80554-106">MED-V 2.0 是以應用程式模型為基礎，您用來部署應用程式的方法可以用來部署和管理 MED-V。</span><span class="sxs-lookup"><span data-stu-id="80554-106">MED-V 2.0 is based on an application model, where the same methods that you use to deploy applications can be used to deploy and manage MED-V.</span></span> <span data-ttu-id="80554-107">已部署的 MED-V 解決方案包含兩個元件： MED-V 主機代理程式和來賓代理程式。</span><span class="sxs-lookup"><span data-stu-id="80554-107">A deployed MED-V solution includes two components: the MED-V Host Agent and Guest Agent.</span></span> <span data-ttu-id="80554-108">MED-V 主機代理程式已安裝在 Windows 7 電腦版，而 MED-V 來賓代理程式則安裝在 MED-V 工作區內的 Windows XP 中。</span><span class="sxs-lookup"><span data-stu-id="80554-108">The MED-V Host Agent is installed on the Windows 7 desktop and the MED-V Guest Agent is installed on Windows XP inside the MED-V workspace.</span></span> <span data-ttu-id="80554-109">MED-V 也包含 MED-V 工作區包裝程式，可提供建立及設定 MED-V 工作區所需的資訊和工具。</span><span class="sxs-lookup"><span data-stu-id="80554-109">MED-V also includes a MED-V Workspace Packager that provides the information and tools necessary for creating and configuring MED-V workspaces.</span></span>

**<span data-ttu-id="80554-110">重要</span><span class="sxs-lookup"><span data-stu-id="80554-110">Important</span></span>**  
<span data-ttu-id="80554-111">MED-V 只支援安裝 MED-V 工作區包裝程式、MED-V 主機代理程式，以及所有使用者的 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="80554-111">MED-V only supports the installation of the MED-V Workspace Packager, the MED-V Host Agent, and the MED-V workspace for all users.</span></span> <span data-ttu-id="80554-112">只有選取**ALLUSERS = ""** ，才能為目前的使用者安裝 med-v，導致安裝元件與安裝 med-v 工作區時失敗。</span><span class="sxs-lookup"><span data-stu-id="80554-112">Installing MED-V for the current user only by selecting **ALLUSERS=””** causes failures in the installation of the components and in the setup of the MED-V workspace.</span></span>



### <span data-ttu-id="80554-113">MED-V 安裝檔案</span><span class="sxs-lookup"><span data-stu-id="80554-113">The MED-V Installation Files</span></span>

<span data-ttu-id="80554-114">MED-V 包含執行 MED-V 所需的下列安裝檔：</span><span class="sxs-lookup"><span data-stu-id="80554-114">MED-V includes the following installation files, required for running MED-V:</span></span>

**<span data-ttu-id="80554-115">MED-V 主機代理程式安裝檔</span><span class="sxs-lookup"><span data-stu-id="80554-115">The MED-V Host Agent Installation File</span></span>**

<span data-ttu-id="80554-116">主機代理程式安裝檔案命名為 [MED-V\_HostAgent\_Setup.exe]。</span><span class="sxs-lookup"><span data-stu-id="80554-116">The Host Agent installation file is named MED-V\_HostAgent\_Setup.exe.</span></span> <span data-ttu-id="80554-117">此檔案是在與企業範圍內的 MED-V 部署中，在每個相關的最終使用者電腦上發佈並安裝。</span><span class="sxs-lookup"><span data-stu-id="80554-117">This file is distributed and installed on each relevant end-user computer as part of your enterprise-wide deployment of MED-V.</span></span>

**<span data-ttu-id="80554-118">MED-V 工作區包裝程式安裝檔</span><span class="sxs-lookup"><span data-stu-id="80554-118">The MED-V Workspace Packager Installation File</span></span>**

<span data-ttu-id="80554-119">MED-V 工作區包裝程式安裝檔命名為 MED-V\_WorkspacePackager\_Setup.exe。</span><span class="sxs-lookup"><span data-stu-id="80554-119">The MED-V Workspace Packager installation file is named MED-V\_WorkspacePackager\_Setup.exe.</span></span> <span data-ttu-id="80554-120">使用此檔案在您擁有管理員許可權和許可權的電腦上安裝 MED-V 工作區包裝程式。</span><span class="sxs-lookup"><span data-stu-id="80554-120">Use this file to install the MED-V Workspace Packager on a computer where you have administrator rights and permissions.</span></span> <span data-ttu-id="80554-121">桌面系統管理員使用 MED-V 工作區包裝程式來建立及管理 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="80554-121">The desktop administrator uses the MED-V Workspace Packager to create and manage MED-V workspaces.</span></span>

**<span data-ttu-id="80554-122">注意</span><span class="sxs-lookup"><span data-stu-id="80554-122">Note</span></span>**  
<span data-ttu-id="80554-123">MED-V 來賓代理程式會在第一次設定期間自動安裝。</span><span class="sxs-lookup"><span data-stu-id="80554-123">The MED-V Guest Agent is installed automatically during first time setup.</span></span>



### <span data-ttu-id="80554-124">MED-V 部署程式</span><span class="sxs-lookup"><span data-stu-id="80554-124">The MED-V Deployment Process</span></span>

<span data-ttu-id="80554-125">以下是 MED-V 安裝與部署程式的高層概覽：</span><span class="sxs-lookup"><span data-stu-id="80554-125">The following is a high-level overview of the MED-V installation and deployment process:</span></span>

1.  <span data-ttu-id="80554-126">在您擁有管理認證且將用來建立 MED-V 工作區套件的電腦上安裝 MED-V 工作區包裝程式。</span><span class="sxs-lookup"><span data-stu-id="80554-126">Install the MED-V Workspace Packager on the computer where you have administrative credentials and that you will be using to build the MED-V workspace packages.</span></span> <span data-ttu-id="80554-127">如需詳細資訊，請參閱[如何安裝 Med-v 工作區包裝程式](how-to-install-the-med-v-workspace-packager.md)。</span><span class="sxs-lookup"><span data-stu-id="80554-127">For more information, see [How to Install the MED-V Workspace Packager](how-to-install-the-med-v-workspace-packager.md).</span></span>

2.  <span data-ttu-id="80554-128">使用 MED-V 工作區包裝程式來準備 MED-V 影像，並建立 MED-V 工作區套件。</span><span class="sxs-lookup"><span data-stu-id="80554-128">Prepare your MED-V image and create your MED-V workspace packages by using the MED-V Workspace Packager.</span></span> <span data-ttu-id="80554-129">如需詳細資訊，請參閱[med-v 的操作](operations-for-med-v.md)。</span><span class="sxs-lookup"><span data-stu-id="80554-129">For more information, see [Operations for MED-V](operations-for-med-v.md).</span></span>

3.  <span data-ttu-id="80554-130">在整個企業中部署所需的 MED-V 元件。</span><span class="sxs-lookup"><span data-stu-id="80554-130">Deploy the required MED-V components throughout your enterprise.</span></span> <span data-ttu-id="80554-131">MED-V 的必要元件是 Windows Virtual PC、MED-V 主機代理程式，以及 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="80554-131">The required components of MED-V are Windows Virtual PC, the MED-V Host Agent, and the MED-V workspace.</span></span>

**<span data-ttu-id="80554-132">重要</span><span class="sxs-lookup"><span data-stu-id="80554-132">Important</span></span>**  
<span data-ttu-id="80554-133">安裝 MED-V 元件需要管理認證。</span><span class="sxs-lookup"><span data-stu-id="80554-133">Installation of the MED-V components requires administrative credentials.</span></span> <span data-ttu-id="80554-134">如果使用者正在安裝 MED-V，系統會提示他們輸入管理認證。</span><span class="sxs-lookup"><span data-stu-id="80554-134">If an end user is installing MED-V, they are prompted to enter administrative credentials.</span></span> <span data-ttu-id="80554-135">或者，如果您是使用電子軟體發佈（ESD）系統進行安裝，就可以在內容中提供管理認證。</span><span class="sxs-lookup"><span data-stu-id="80554-135">Alternately, administrative credentials can be provided in context if you are installing by using an electronic software distribution (ESD) system.</span></span>



### <span data-ttu-id="80554-136">MED-V 元件</span><span class="sxs-lookup"><span data-stu-id="80554-136">The MED-V Components</span></span>

<span data-ttu-id="80554-137">您在整個企業部署的 MED-V 元件包含下列各項：</span><span class="sxs-lookup"><span data-stu-id="80554-137">The MED-V components that you deploy throughout your enterprise consist of the following:</span></span>

**<span data-ttu-id="80554-138">Windows 虛擬電腦</span><span class="sxs-lookup"><span data-stu-id="80554-138">Windows Virtual PC</span></span>**

<span data-ttu-id="80554-139">Windows 虛擬電腦影像內的 MED-V 函數用於相容性方案。</span><span class="sxs-lookup"><span data-stu-id="80554-139">MED-V functions inside Windows Virtual PC images for its compatibility solution.</span></span> <span data-ttu-id="80554-140">Windows 虛擬電腦和 Windows 7 的更新（KB977206）是必要的。</span><span class="sxs-lookup"><span data-stu-id="80554-140">Windows Virtual PC and the update for Windows 7 (KB977206) are required.</span></span> <span data-ttu-id="80554-141">如需詳細資訊，請參閱[設定安裝必備元件](configure-installation-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="80554-141">For more information, see [Configure Installation Prerequisites](configure-installation-prerequisites.md).</span></span>

**<span data-ttu-id="80554-142">MED-V 主機代理程式安裝檔</span><span class="sxs-lookup"><span data-stu-id="80554-142">The MED-V Host Agent Installation File</span></span>**

<span data-ttu-id="80554-143">MED-V\_HostAgent\_Setup.exe]。</span><span class="sxs-lookup"><span data-stu-id="80554-143">MED-V\_HostAgent\_Setup.exe.</span></span>

**<span data-ttu-id="80554-144">MED-V 工作區安裝檔案</span><span class="sxs-lookup"><span data-stu-id="80554-144">The MED-V Workspace Installation Files</span></span>**

<span data-ttu-id="80554-145">當您建立由下列專案組成的 MED-V 工作區套件時，就會建立 MED-V 工作區安裝檔案：</span><span class="sxs-lookup"><span data-stu-id="80554-145">The MED-V workspace installation files are created when you build your MED-V workspace package that consists of the following:</span></span>

<span data-ttu-id="80554-146">執行 MED-V 工作區安裝的 setup.exe 可執行程式</span><span class="sxs-lookup"><span data-stu-id="80554-146">A setup.exe executable program that executes the MED-V workspace installation</span></span>

<span data-ttu-id="80554-147">&lt;Med-v \ _workspace \ _name &gt; .msi 安裝程式</span><span class="sxs-lookup"><span data-stu-id="80554-147">A &lt;MED-V\_workspace\_name&gt;.msi installer</span></span>

<span data-ttu-id="80554-148">&lt;VHD \ _filename &gt; medv 檔案，該檔案是壓縮的虛擬硬碟</span><span class="sxs-lookup"><span data-stu-id="80554-148">A &lt;VHD\_filename&gt;.medv file, which is the compressed virtual hard disk</span></span>

<span data-ttu-id="80554-149">[配置設定] 的檔案（ &lt; 工作區 \ _name &gt; .reg 和 &lt; 工作區 \ _name &gt; ps1）</span><span class="sxs-lookup"><span data-stu-id="80554-149">The files for configuration settings (&lt;workspace\_name&gt;.reg and &lt;workspace\_name&gt;.ps1)</span></span>

<span data-ttu-id="80554-150">若要部署 MED-V，請將所有所需的安裝檔案複製到主機電腦或主機電腦可存取的共用位置。</span><span class="sxs-lookup"><span data-stu-id="80554-150">To deploy MED-V, copy all the required installation files to the host computer or to a share that can be accessed by the host computer.</span></span> <span data-ttu-id="80554-151">針對 Windows Virtual PC、MED-V 主機代理程式和 MED-V 工作區執行元件安裝檔案。</span><span class="sxs-lookup"><span data-stu-id="80554-151">Run the component installation files for Windows Virtual PC, the MED-V Host Agent, and the MED-V workspace.</span></span> <span data-ttu-id="80554-152">然後啟動 MED-V 主機代理程式，以在第一次安裝 MED-V 時完成。</span><span class="sxs-lookup"><span data-stu-id="80554-152">Then start the MED-V Host Agent to complete the first time setup of MED-V.</span></span>

<span data-ttu-id="80554-153">您可以手動執行安裝。</span><span class="sxs-lookup"><span data-stu-id="80554-153">You can perform the installation manually.</span></span> <span data-ttu-id="80554-154">不過，我們建議您使用電子軟體發佈方法來自動部署元件。</span><span class="sxs-lookup"><span data-stu-id="80554-154">However, we recommend that you use an electronic software distribution method to automate the deployment of the components.</span></span> <span data-ttu-id="80554-155">如需詳細資訊，請參閱[如何透過電子軟體發佈系統部署 Med-v 工作區](how-to-deploy-a-med-v-workspace-through-an-electronic-software-distribution-system.md)。</span><span class="sxs-lookup"><span data-stu-id="80554-155">For more information, see [How to Deploy a MED-V Workspace Through an Electronic Software Distribution System](how-to-deploy-a-med-v-workspace-through-an-electronic-software-distribution-system.md).</span></span>

**<span data-ttu-id="80554-156">注意</span><span class="sxs-lookup"><span data-stu-id="80554-156">Note</span></span>**  
<span data-ttu-id="80554-157">如需控制安裝選項之可用命令列引數的相關資訊，請參閱[Med-v 安裝檔的命令列選項](command-line-options-for-med-v-installation-files.md)。</span><span class="sxs-lookup"><span data-stu-id="80554-157">For information about available command-line arguments to control install options, see [Command-Line Options for MED-V Installation Files](command-line-options-for-med-v-installation-files.md).</span></span>



## <span data-ttu-id="80554-158">部署步驟</span><span class="sxs-lookup"><span data-stu-id="80554-158">Deployment Steps</span></span>


<span data-ttu-id="80554-159">當您在整個企業中部署 MED-V 時，主要需要考慮的事項：安裝與第一次設定。</span><span class="sxs-lookup"><span data-stu-id="80554-159">When you deploy MED-V throughout your enterprise, there are two main considerations: installation and first time setup.</span></span>

### <span data-ttu-id="80554-160">安裝</span><span class="sxs-lookup"><span data-stu-id="80554-160">Installation</span></span>

1.  <span data-ttu-id="80554-161">**Windows 虛擬電腦**-在安裝期間，Med-v 檢查 WINDOWS 虛擬電腦及其必要的 windows 7 更新（KB977206）。</span><span class="sxs-lookup"><span data-stu-id="80554-161">**Windows Virtual PC** - During installation, MED-V checks for Windows Virtual PC and its required update for Windows 7 (KB977206).</span></span> <span data-ttu-id="80554-162">如需詳細資訊，請參閱[設定安裝必備元件](configure-installation-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="80554-162">For more information, see [Configure Installation Prerequisites](configure-installation-prerequisites.md).</span></span>

    <span data-ttu-id="80554-163">在安裝 MED-V 之前，您可以將它們安裝為 Windows 7 安裝的一部分，或者您可以將它們安裝為 MED-V 發佈的一部分。</span><span class="sxs-lookup"><span data-stu-id="80554-163">You can install these as part of the Windows 7 installations before you install MED-V, or you can install them as part of the MED-V distribution.</span></span> <span data-ttu-id="80554-164">不過，MED-V 不包含適用于其部署的機制;必須使用電子軟體發佈（ESD）系統或 Windows 7 影像的一部分來部署它們。</span><span class="sxs-lookup"><span data-stu-id="80554-164">However, MED-V does not include a mechanism for their deployment; they must be deployed by using an electronic software distribution (ESD) system or as part of the Windows 7 image.</span></span>

    **<span data-ttu-id="80554-165">重要</span><span class="sxs-lookup"><span data-stu-id="80554-165">Important</span></span>**  
    <span data-ttu-id="80554-166">當您使用批次檔案安裝 MED-V 元件時，最佳做法是在 MED-V 主機代理和 MED-V 工作區套件檔案之後，指定 Windows 虛擬電腦和 Windows 虛擬電腦熱修復程式已安裝。</span><span class="sxs-lookup"><span data-stu-id="80554-166">When you install the MED-V components by using a batch file, a best practice is to specify that Windows Virtual PC and the Windows Virtual PC hotfix are installed after the MED-V Host Agent and the MED-V workspace package files.</span></span> <span data-ttu-id="80554-167">這表示 Windows 更新不會對安裝程式造成任何干擾，只要需要重新開機即可。</span><span class="sxs-lookup"><span data-stu-id="80554-167">This means that Windows Update will not cause any interference with the installation process by requiring a restart.</span></span>



~~~
**Note**  
After you install Windows Virtual PC, the computer must be restarted.
~~~



2. <span data-ttu-id="80554-168">**Med-v 主機代理程式**-在將執行 Med-v 的 Windows 7 電腦上安裝 Med-v 主機代理程式。</span><span class="sxs-lookup"><span data-stu-id="80554-168">**MED-V Host Agent** – Install the MED-V Host Agent on the Windows 7 computer where MED-V will be run.</span></span> <span data-ttu-id="80554-169">在安裝 MED-V 工作區之前，必須先安裝此功能，然後檢查以確認已安裝 Windows 虛擬電腦。</span><span class="sxs-lookup"><span data-stu-id="80554-169">This must be installed before installing the MED-V workspace and checks to make sure that Windows Virtual PC is installed.</span></span>

3. <span data-ttu-id="80554-170">**Med-v 工作區**-您可以使用 Med-v 工作區包裝程式來建立此安裝所需的檔案： setup.exe、medv 和 .msi 檔案。</span><span class="sxs-lookup"><span data-stu-id="80554-170">**MED-V workspace** – You create the files that are required in this installation by using the MED-V Workspace Packager: the setup.exe, .medv, and .msi files.</span></span> <span data-ttu-id="80554-171">若要安裝 MED-V 工作區，請執行 setup.exe;這會根據需要觸發其他檔案。</span><span class="sxs-lookup"><span data-stu-id="80554-171">To install the MED-V workspace, run setup.exe; this triggers the other files as required.</span></span> <span data-ttu-id="80554-172">安裝會將登錄中的專案放在本機電腦執行機碼底下，以啟動 MED-V 主機代理程式（在 Windows 啟動時，這會一直執行 MED-V）。</span><span class="sxs-lookup"><span data-stu-id="80554-172">The installation places an entry in the registry under the local machine run key to start the MED-V Host Agent, which always runs MED-V when Windows is started.</span></span>

   **<span data-ttu-id="80554-173">重要</span><span class="sxs-lookup"><span data-stu-id="80554-173">Important</span></span>**  
   <span data-ttu-id="80554-174">MED-V 工作區的安裝可由最終使用者以互動方式執行，或透過電子軟體發佈系統以無提示的方式執行。</span><span class="sxs-lookup"><span data-stu-id="80554-174">The installation of the MED-V workspace can be run interactively by the end user or silently through an electronic software distribution system.</span></span> <span data-ttu-id="80554-175">安裝 MED-V 工作區需要管理認證，因此使用者必須是其電腦的系統管理員，才能安裝 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="80554-175">Installation of the MED-V workspace requires administrative credentials, so end users must be administrators of their computers to install the MED-V workspace.</span></span> <span data-ttu-id="80554-176">或者，電子軟體發佈系統通常會在系統內容中執行，且具有足夠的許可權。</span><span class="sxs-lookup"><span data-stu-id="80554-176">Alternately, an electronic software distribution system typically runs in the system context and has sufficient permissions.</span></span>



~~~
**Tip**  
Because of problems that can occur when you install MED-V from a network location, we recommend that you copy the MED-V workspace setup files locally and then run setup.exe.
~~~



### <span data-ttu-id="80554-177">第一次設定</span><span class="sxs-lookup"><span data-stu-id="80554-177">First Time Setup</span></span>

<span data-ttu-id="80554-178">安裝 MED-V 並安裝其必備元件之後，就必須對 MED-V 進行設定。</span><span class="sxs-lookup"><span data-stu-id="80554-178">After MED-V and its required components are installed, MED-V must be configured.</span></span> <span data-ttu-id="80554-179">MED-V 的配置稱為第一次設定。</span><span class="sxs-lookup"><span data-stu-id="80554-179">The configuration of MED-V is known as first time setup.</span></span> <span data-ttu-id="80554-180">透過使用**Med-v 工作區包裝**程式，您可以將第一次設定設定為以安靜或互動方式執行。</span><span class="sxs-lookup"><span data-stu-id="80554-180">By using the **MED-V Workspace Packager**, you can configure first time setup to run silently or interactively.</span></span> <span data-ttu-id="80554-181">第一次安裝 MED-V 需要使用者輸入其密碼才能向 MED-V 工作區驗證，但對使用者幾乎看不到。</span><span class="sxs-lookup"><span data-stu-id="80554-181">First time setup of MED-V requires end users to enter their password to authenticate to the MED-V workspace, but otherwise can be almost invisible to the user.</span></span> <span data-ttu-id="80554-182">通知會顯示在通知區域中，例如當您第一次設定完成且應用程式準備就緒時。</span><span class="sxs-lookup"><span data-stu-id="80554-182">Notifications are shown in the notification area, such as when first time setup is complete and applications are ready.</span></span> <span data-ttu-id="80554-183">下列是第一次設定 MED-V 時所發生的動作：</span><span class="sxs-lookup"><span data-stu-id="80554-183">The following are the actions that occur during first time setup of MED-V:</span></span>

1.  <span data-ttu-id="80554-184">必須設定虛擬硬碟。</span><span class="sxs-lookup"><span data-stu-id="80554-184">The virtual hard disk must be configured.</span></span> <span data-ttu-id="80554-185">[最小化安裝] 會執行，並展開 Windows XP 影像。</span><span class="sxs-lookup"><span data-stu-id="80554-185">Mini-Setup runs and expands the Windows XP image.</span></span> <span data-ttu-id="80554-186">這個問題通常會發生在隱藏視窗中，但 MED-V 可以設定為在此設定期間顯示。</span><span class="sxs-lookup"><span data-stu-id="80554-186">Typically, this occurs in a hidden window, but MED-V can be configured to display during this configuration.</span></span>

2.  <span data-ttu-id="80554-187">[最小化安裝] 完成後，您可以執行其他設定所需的命令，例如安裝 ESD 軟體或其他應用程式，或配置影像。</span><span class="sxs-lookup"><span data-stu-id="80554-187">After Mini-Setup finishes, you can run commands that you must have for additional configuration, such as installing ESD software or other applications, or configuring the image.</span></span> <span data-ttu-id="80554-188">這些可以在 Sysprep.inf 檔案中呼叫，但在此不是必要的。</span><span class="sxs-lookup"><span data-stu-id="80554-188">These can be called in the Sysprep.inf file, but are not required there.</span></span> <span data-ttu-id="80554-189">如需詳細資訊，請參閱設定[med-v 的 Windows 虛擬電腦影像](configuring-a-windows-virtual-pc-image-for-med-v.md)。</span><span class="sxs-lookup"><span data-stu-id="80554-189">For more information, see [Configuring a Windows Virtual PC Image for MED-V](configuring-a-windows-virtual-pc-image-for-med-v.md).</span></span>

3.  <span data-ttu-id="80554-190">Ftscompletion.exe 是作為 [設定] 中的最後一個步驟執行。</span><span class="sxs-lookup"><span data-stu-id="80554-190">Ftscompletion.exe is run as the last step in configuration.</span></span> <span data-ttu-id="80554-191">這個程式會完成 MED-V 設定，將使用者新增至 RDP 群組，讓其存取 MED-V 工作區、複製記錄、通知 MED-V-v 工作區已就緒，然後重新開機 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="80554-191">This process completes the MED-V configuration, adds the user to the RDP group to let them access the MED-V workspace, copies logs, signals MED-V that the MED-V workspace is ready, and then restarts the MED-V workspace.</span></span> <span data-ttu-id="80554-192">此程式也可以將使用者新增為 MED-V 工作區的管理員（如果這是在建立 MED-V 工作區時設定的）。</span><span class="sxs-lookup"><span data-stu-id="80554-192">This process can also add the user as an administrator of the MED-V workspace if this was configured when the MED-V workspace was created.</span></span> <span data-ttu-id="80554-193">Ftscompletion.exe 通常是透過 Sysprep、inf 檔案呼叫，但是也可以透過另一個方法（例如腳本）執行。</span><span class="sxs-lookup"><span data-stu-id="80554-193">Ftscompletion.exe is typically called through the Sysprep,inf file but can also be run through another method, such as a script.</span></span> <span data-ttu-id="80554-194">不過，Ftscompletion.exe 必須是設定工作站時所執行的最後一個動作。</span><span class="sxs-lookup"><span data-stu-id="80554-194">However, Ftscompletion.exe must be the last action that is performed when the workstation is configured.</span></span> <span data-ttu-id="80554-195">如需詳細資訊，請參閱設定[med-v 的 Windows 虛擬電腦影像](configuring-a-windows-virtual-pc-image-for-med-v.md)。</span><span class="sxs-lookup"><span data-stu-id="80554-195">For more information, see [Configuring a Windows Virtual PC Image for MED-V](configuring-a-windows-virtual-pc-image-for-med-v.md).</span></span>

4.  <span data-ttu-id="80554-196">Ftscompletion.exe 將 MED-V 工作區重新開機之後，使用者就會登入。</span><span class="sxs-lookup"><span data-stu-id="80554-196">After the MED-V workspace is restarted by Ftscompletion.exe, the end user is logged on.</span></span> <span data-ttu-id="80554-197">如果他們在第一次設定期間未儲存其密碼，系統會再次提示他們。</span><span class="sxs-lookup"><span data-stu-id="80554-197">If they did not save their password during first time setup, they are prompted for it again.</span></span> <span data-ttu-id="80554-198">接著啟動並設定使用者的 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="80554-198">The MED-V workspace is then started and configured for the user.</span></span> <span data-ttu-id="80554-199">配置包括套用群組原則。</span><span class="sxs-lookup"><span data-stu-id="80554-199">Configuration includes applying Group Policy.</span></span>

    <span data-ttu-id="80554-200">我們建議您只在適用于 Windows XP 的應用程式相容性環境中，套用那些對您有意義的原則。</span><span class="sxs-lookup"><span data-stu-id="80554-200">We recommend that you apply only those policies that make sense in an application compatibility environment for Windows XP.</span></span> <span data-ttu-id="80554-201">例如，桌面個人化原則通常不需要套用，而且應該停用。</span><span class="sxs-lookup"><span data-stu-id="80554-201">For example, desktop personalization policies do not typically need to be applied and should be disabled.</span></span> <span data-ttu-id="80554-202">如需如何只允許使用本機設定檔的詳細資訊，請參閱[漫遊使用者設定檔的群組原則設定](https://go.microsoft.com/fwlink/?LinkId=205072)（ https://go.microsoft.com/fwlink/?LinkId=205072) 。</span><span class="sxs-lookup"><span data-stu-id="80554-202">For more information about how to allow only local profiles, see [Group Policy Settings for Roaming User Profiles](https://go.microsoft.com/fwlink/?LinkId=205072) (https://go.microsoft.com/fwlink/?LinkId=205072).</span></span>

<span data-ttu-id="80554-203">第一次設定完成後，系統會通知使用者已發佈的應用程式已就緒。</span><span class="sxs-lookup"><span data-stu-id="80554-203">After first time setup is complete, the end user is notified that the published applications are ready.</span></span> <span data-ttu-id="80554-204">接著他們就能從其 [**開始**] 功能表存取在 med-v 工作區所安裝的應用程式。</span><span class="sxs-lookup"><span data-stu-id="80554-204">They are then able to access the applications installed in the MED-V workspace from their **Start** menu.</span></span>

## <span data-ttu-id="80554-205">相關主題</span><span class="sxs-lookup"><span data-stu-id="80554-205">Related topics</span></span>


[<span data-ttu-id="80554-206">準備 MED-V 的部署環境</span><span class="sxs-lookup"><span data-stu-id="80554-206">Prepare the Deployment Environment for MED-V</span></span>](prepare-the-deployment-environment-for-med-v.md)

[<span data-ttu-id="80554-207">MED-V 部署</span><span class="sxs-lookup"><span data-stu-id="80554-207">Deployment of MED-V</span></span>](deployment-of-med-v.md)









