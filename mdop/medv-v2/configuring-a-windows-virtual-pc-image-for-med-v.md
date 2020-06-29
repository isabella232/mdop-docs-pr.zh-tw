---
title: 設定 MED-V 的 Windows 虛擬電腦映像
description: 設定 MED-V 的 Windows 虛擬電腦映像
author: dansimp
ms.assetid: d87a0df8-9e08-4d1e-bfb0-9dc3cebf0d28
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: 340754b33576651c8ba89c85f369c48c0a0ab957
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811984"
---
# <span data-ttu-id="89619-103">設定 MED-V 的 Windows 虛擬電腦映像</span><span class="sxs-lookup"><span data-stu-id="89619-103">Configuring a Windows Virtual PC Image for MED-V</span></span>


<span data-ttu-id="89619-104">在您已安裝想要包含在 MED-V 影像中的所有內容之後，您可以設定在 Microsoft 企業桌面虛擬化（MED-V）2.0 中使用的影像。</span><span class="sxs-lookup"><span data-stu-id="89619-104">After you have installed everything that you want to include in your MED-V image, you can configure the image for use in Microsoft Enterprise Desktop Virtualization (MED-V) 2.0.</span></span> <span data-ttu-id="89619-105">本節中的主題提供在建立 MED-V 工作區套件之前，先設定您的 MED-V 影像以執行第一次安裝程式的指導方針。</span><span class="sxs-lookup"><span data-stu-id="89619-105">The topics in this section provide guidance for configuring your MED-V image to run first time setup before you create your MED-V workspace package.</span></span>

<span data-ttu-id="89619-106">第一次設定為最終使用者準備 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="89619-106">First time setup prepares the MED-V workspace for an end user.</span></span> <span data-ttu-id="89619-107">此程式會從在 MED-V 工作區封裝的影像建立虛擬機器，然後在虛擬機器上執行 Windows 迷你設定。</span><span class="sxs-lookup"><span data-stu-id="89619-107">The process creates a virtual machine from the image packaged in the MED-V workspace and then runs Windows Mini-Setup on the virtual machine.</span></span> <span data-ttu-id="89619-108">這包括執行自訂安裝程式腳本和第一次安裝完成應用程式時，FtsCompletion.exe。</span><span class="sxs-lookup"><span data-stu-id="89619-108">This includes the running of both custom setup scripts and the first time setup completion application, FtsCompletion.exe.</span></span>

<span data-ttu-id="89619-109">請依照下列步驟來設定您的 MED-V 影像，以便在第一次執行安裝：</span><span class="sxs-lookup"><span data-stu-id="89619-109">Follow these steps to configure your MED-V image for running first time setup:</span></span>

1. <span data-ttu-id="89619-110">作為選項，您可以壓縮虛擬硬碟（VHD）來回收空白磁碟空間，並減少 VHD 大小，然後再繼續設定 Windows 虛擬電腦影像。</span><span class="sxs-lookup"><span data-stu-id="89619-110">As an option, you can compact the virtual hard disk (VHD) to reclaim empty disk space and reduce the size of the VHD before you continue with configuring the Windows Virtual PC image.</span></span> <span data-ttu-id="89619-111">如需詳細資訊，請參閱[壓縮 Med-v 虛擬硬碟](compacting-the-med-v-virtual-hard-disk.md)。</span><span class="sxs-lookup"><span data-stu-id="89619-111">For more information, see [Compacting the MED-V Virtual Hard Disk](compacting-the-med-v-virtual-hard-disk.md).</span></span>

2. <span data-ttu-id="89619-112">自訂虛擬機器設定處理常式。</span><span class="sxs-lookup"><span data-stu-id="89619-112">Customize the virtual machine setup process.</span></span>

3. <span data-ttu-id="89619-113">使用 Sysprep 來密封 MED-V 影像。</span><span class="sxs-lookup"><span data-stu-id="89619-113">Seal the MED-V image by using Sysprep.</span></span>

   **<span data-ttu-id="89619-114">自訂虛擬機器設定處理常式</span><span class="sxs-lookup"><span data-stu-id="89619-114">Customizing the Virtual Machine Setup Process</span></span>**

4. <span data-ttu-id="89619-115">在使用 MED-V 準備您的影像時，您可以設定虛擬機器上的各種設定，例如指定執行 Windows Update 的設定。</span><span class="sxs-lookup"><span data-stu-id="89619-115">As part of preparing your image for use with MED-V, you can configure various settings on the virtual machine, such as specifying the settings for running Windows Update.</span></span> <span data-ttu-id="89619-116">在建立 MED-V 工作區套件之前，請先指定所有必要的虛擬機器設定。</span><span class="sxs-lookup"><span data-stu-id="89619-116">Specify all the necessary virtual machine settings before you create the MED-V workspace package.</span></span>

5. <span data-ttu-id="89619-117">在您建立 MED-V 工作區套件之前，我們建議您停用虛擬機器上的還原點，以避免差異磁片無限增加。</span><span class="sxs-lookup"><span data-stu-id="89619-117">Before you create the MED-V workspace package, we recommend that you disable restore points on the virtual machine to prevent the differencing disk from growing unbounded.</span></span> <span data-ttu-id="89619-118">如需詳細資訊，請參閱[如何在 WINDOWS XP 中關閉及開啟系統還原](https://go.microsoft.com/fwlink/?LinkId=195927)（ https://go.microsoft.com/fwlink/?LinkId=195927) 。</span><span class="sxs-lookup"><span data-stu-id="89619-118">For more information, see [How to turn off and turn on System Restore in Windows XP](https://go.microsoft.com/fwlink/?LinkId=195927) (https://go.microsoft.com/fwlink/?LinkId=195927).</span></span>

   **<span data-ttu-id="89619-119">注意</span><span class="sxs-lookup"><span data-stu-id="89619-119">Note</span></span>**  
   <span data-ttu-id="89619-120">您可以設定您的 Sysprep.inf 檔案，以便在第一次執行設定時停用還原點。</span><span class="sxs-lookup"><span data-stu-id="89619-120">You can set up your Sysprep.inf file to disable restore points when first time setup is run.</span></span> <span data-ttu-id="89619-121">如需設定此 GuiRunOnce 金鑰的範例，請參閱本節稍後的範例 Sysprep.inf 檔案範例。</span><span class="sxs-lookup"><span data-stu-id="89619-121">For an example of setting this GuiRunOnce key, see the sample Sysprep.inf file later in this section.</span></span>



6. <span data-ttu-id="89619-122">將安裝程式設定為執行 [最小化安裝]，而不是預設的 [Windows 歡迎畫面]。</span><span class="sxs-lookup"><span data-stu-id="89619-122">Configure the setup process to run Mini-Setup instead of the default Windows Welcome.</span></span> <span data-ttu-id="89619-123">您必須使用 **-迷你**開關執行 Sysprep 工具，或選取圖形使用者介面中的 [ **MiniSetup** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="89619-123">You must either run the Sysprep tool by using the **-mini** switch, or select the **MiniSetup** check box in the graphical user interface.</span></span> <span data-ttu-id="89619-124">如需詳細資訊，請參閱[如何使用 Sysprep 來密封影像](#bkmk-seal)。</span><span class="sxs-lookup"><span data-stu-id="89619-124">For more information, see [How to Seal the Image with Sysprep](#bkmk-seal).</span></span>

   **<span data-ttu-id="89619-125">第一次設定完成檔案時呼叫</span><span class="sxs-lookup"><span data-stu-id="89619-125">Calling the First time setup Completion File</span></span>**

   1.  <span data-ttu-id="89619-126">在安裝 MED-V 來賓代理程式的過程中，會包含稱為 FtsCompletion.exe 的可執行檔。</span><span class="sxs-lookup"><span data-stu-id="89619-126">An executable called FtsCompletion.exe is included as part of the installation of the MED-V Guest Agent.</span></span> <span data-ttu-id="89619-127">根據預設，它位於 [程式檔] 下的 MED-V 影像系統磁碟機中 **-Microsoft 企業桌面虛擬化**。</span><span class="sxs-lookup"><span data-stu-id="89619-127">By default, it is located in the system drive of your MED-V image under **Program Files – Microsoft Enterprise Desktop Virtualization**.</span></span>

       **<span data-ttu-id="89619-128">重要</span><span class="sxs-lookup"><span data-stu-id="89619-128">Important</span></span>**  
       <span data-ttu-id="89619-129">當您第一次設定處理常式中的最後一個步驟，您必須執行這個可執行程式。</span><span class="sxs-lookup"><span data-stu-id="89619-129">As the final step in the first time setup process, you must run this executable program.</span></span> <span data-ttu-id="89619-130">要呼叫的可執行程式的使用者必須是來賓的本機系統管理員群組的成員。</span><span class="sxs-lookup"><span data-stu-id="89619-130">The user for whom the executable program is being called must be a member of the guest’s local administrator group.</span></span>



   2.  <span data-ttu-id="89619-131">您可以決定您要如何呼叫此可執行程式，例如，透過使用 MED-V 工作區部署的腳本進行。</span><span class="sxs-lookup"><span data-stu-id="89619-131">You can decide how you want to call this executable program, for example, through a script that is deployed with the MED-V workspace.</span></span> <span data-ttu-id="89619-132">您可以呼叫此可執行檔做為 Sysprep.inf 檔案的最後一行。</span><span class="sxs-lookup"><span data-stu-id="89619-132">You can call this executable as the last line of your Sysprep.inf file.</span></span> <span data-ttu-id="89619-133">如需如何在您的 Sysprep.inf 檔案中呼叫此可執行程式的範例，請參閱本節稍後的範例檔案。</span><span class="sxs-lookup"><span data-stu-id="89619-133">For an example of how to call this executable program in your Sysprep.inf file, see the sample file later in this section.</span></span>

<span data-ttu-id="89619-134">在您完成 MED-V 影像的自訂之後，您就可以使用 Sysprep 來密封影像。</span><span class="sxs-lookup"><span data-stu-id="89619-134">After you have completed customization of your MED-V image, you are ready to seal the image by using Sysprep.</span></span>

<a href="" id="bkmk-seal"></a>**<span data-ttu-id="89619-135">使用 Sysprep 來密封 MED-V 影像</span><span class="sxs-lookup"><span data-stu-id="89619-135">Sealing the MED-V Image by Using Sysprep</span></span>**

1.  <span data-ttu-id="89619-136">系統準備工具（Sysprep）是一種技術，您可以用來在整個網路中執行以影像為基礎的安裝，只要由管理員或 IT 專業人員來干預就能輕鬆。</span><span class="sxs-lookup"><span data-stu-id="89619-136">The System Preparation tool (Sysprep) is a technology that you can use to perform image-based installations throughout the network with minimal intervention by an administrator or IT-Professional.</span></span>

2.  <span data-ttu-id="89619-137">在 MED-V 環境中，您可以使用 Sysprep，在第一次啟動時，將唯一的安全識別碼（SID）及其他設定指派給每個 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="89619-137">In a MED-V environment, you can use Sysprep to assign unique security IDs (SID) and other settings to each MED-V workspace the first time that they are started.</span></span>

    **<span data-ttu-id="89619-138">注意</span><span class="sxs-lookup"><span data-stu-id="89619-138">Note</span></span>**  
    <span data-ttu-id="89619-139">如需如何使用 Sysprep 的詳細資訊，請參閱[Sysprep 技術參考](https://go.microsoft.com/fwlink/?LinkId=195930)（ https://go.microsoft.com/fwlink/?LinkId=195930) 。</span><span class="sxs-lookup"><span data-stu-id="89619-139">For more information about how to use Sysprep, see [Sysprep Technical Reference](https://go.microsoft.com/fwlink/?LinkId=195930) (https://go.microsoft.com/fwlink/?LinkId=195930).</span></span>



~~~
**Caution**  
When you use non-ASCII characters in the Sysprep.inf file, you must save the file by using the encoding appropriate for the characters entered. Windows XP expects the Sysprep.inf file to be encoded by using the code page for the language that you are targeting.

You must also make sure that the System Locale of the computers to which the MED-V workspace is deployed is set to handle the language specific characters that might be present in the Sysprep.inf file. To change the settings for the System Locale, follow these steps:

1.  To open Region and Language, click **Start**, click **Control Panel**, and then click **Region and Language**.

2.  Click the **Administrative** tab, and then click **Change System Locale** under **Language for non-Unicode programs**.

    If you are prompted for an administrator password or confirmation, type the administrator password or provide confirmation.

3.  Select your preferred language and then click **OK**.



**To configure Sysprep on the MED-V Guest Computer**

1.  Create a folder named *Sysprep* in the root of the MED-V image system drive.

2.  Download the deploy.cab file. For more information, see [Windows XP Service Pack 3 Deployment Tools](https://go.microsoft.com/fwlink/?LinkId=195928) From the Microsoft Download Center (https://go.microsoft.com/fwlink/?LinkId=195928).

3.  From the deploy.cab file, copy or extract the Setupmgr.exe, Sysprep.exe, and Setupcl.exe files to the Sysprep folder.

4.  In the Sysprep folder, run **Setup Manager** (Setupmgr.exe) to create a Sysprep.inf answer file.

    Or, you can create this file manually or use your company’s existing file. For more information, see [How to use the Sysprep tool to automate successful deployment of Windows XP](https://go.microsoft.com/fwlink/?LinkId=195929) (https://go.microsoft.com/fwlink/?LinkId=195929).

5.  Follow the **Setup Manager** wizard.

    **Important**  
    You must configure the MED-V guest to join a domain that lets users log on by using the credentials that they use to log on to the MED-V host.



    **Caution**  
    When you configure a proxy account for joining virtual machines to the domain, know that it is possible for an end user to obtain the proxy account credentials. Take all the necessary security precautions to minimize risk, such as limiting account user rights. For more information about security concerns when you configure a Windows Virtual PC image for MED-V, see [Security Best Practices for MED-V Operations](security-best-practices-for-med-v-operations.md).



    If end users must provide information during the first time setup process based on the parameters specified in the Sysprep.inf file, you must also specify that first time setup is run in **Attended** mode when you are creating your MED-V workspace package. If no information will be required from the end user, you can specify that first time setup is run in **Unattended** mode when you are creating your MED-V workspace package. For more information, see [Create a MED-V Workspace Package](create-a-med-v-workspace-package.md).

    Although you can specify any settings that you prefer, a MED-V best practice is that you create the Sysprep.inf file so that first time setup can be run in **Unattended** mode. This requires that you provide all of the required settings information as you continue through the **Setup Manager** wizard.

    **Caution**  
    If you have set a local policy or registry entry to include a service level agreement (SLA) in your image (VHD), you must specify that first time setup is run in **Attended** mode or first time setup will fail. Or, a MED-V best practice is to enforce the SLA through Group Policy later so that the SLA is displayed to the end user after first time setup is finished.



    **Note**  
    You can configure the MED-V workspace to set certain Sysprep.inf settings based on the configuration of the host and the identity of the end user. For more information, see [Create a MED-V Workspace Package](create-a-med-v-workspace-package.md).



6.  Seal the MED-V image.

    **Important**  
    We recommend that you make a backup copy of the MED-V image before sealing it.



    After you have completed all the steps in the **Setup Manager** wizard, you are ready to run Sysprep to seal the MED-V image.

**To run Sysprep**

1.  Run the System Preparation Tool (Sysprep.exe) from the *Sysprep* folder that you created when you configured Sysprep in the MED-V virtual machine.

2.  In the warning message box that appears, click **OK**.

3.  In the **Options** dialog box, select the **Don't reset grace period for activation** and **Use Mini-Setup** check boxes. Also, make sure that the **Shutdown mode** box is set to **Shut down**.

4.  Click **Reseal**. This removes identity information and clears event logs to prepare for first time setup.

5.  If you are not satisfied with the information listed in the confirmation message box that appears, click **Cancel** and then change the selections.

6.  Click **OK** to complete the system preparation process.

After you have run Sysprep on your MED-V image, the virtual machine shuts down and is ready for use in creating a MED-V workspace.
~~~

## <span data-ttu-id="89619-140">範例</span><span class="sxs-lookup"><span data-stu-id="89619-140">Example</span></span>


<span data-ttu-id="89619-141">以下是 Sysprep.inf 檔案的範例。</span><span class="sxs-lookup"><span data-stu-id="89619-141">Here is an example of a Sysprep.inf file.</span></span>

``` syntax
;SetupMgrTag
[GuiUnattended]
    EncryptedAdminPassword=NO
    TimeZone=10
    OEMDuplicatorstring="MED_V v2 Host"
    AdminPassword="administrator"
    AutoLogon=Yes
    AutoLogonCount=1
    OEMSkipRegional=1
    OemSkipWelcome=1

[UserData]
    ProductKey=
    FullName="MED-V User"
    OrgName="Contoso"
    ComputerName=*

[Identification]
    JoinDomain=domain.corp.contoso.com
    DomainAdmin=UserName
    DomainAdminPassword=Password

[Networking]
    InstallDefaultComponents=Yes

[Branding]
    BrandIEUsingUnattended=Yes

[Proxy]
    Proxy_Enable=0
    Use_Same_Proxy=0

[Unattended]
    InstallFilesPath=C:\sysprep\i386
    TargetPath=\WINDOWS
    UpdateServerProfileDirectory=1
    OemSkipEula=Yes

[RegionalSettings]
    LanguageGroup=1
    Language=00000409

[GuiRunOnce]
    Command0="wmic /namespace:\\root\default path SystemRestore call Disable %SystemDrive%\"
    Command1="c:\Program Files\Microsoft Enterprise Desktop Virtualization\FtsCompletion.exe"

[sysprepcleanup]
```

## <span data-ttu-id="89619-142">相關主題</span><span class="sxs-lookup"><span data-stu-id="89619-142">Related topics</span></span>


[<span data-ttu-id="89619-143">建立 MED-V 工作區套件</span><span class="sxs-lookup"><span data-stu-id="89619-143">Create a MED-V Workspace Package</span></span>](create-a-med-v-workspace-package.md)

[<span data-ttu-id="89619-144">準備 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="89619-144">Prepare a MED-V Image</span></span>](prepare-a-med-v-image.md)









