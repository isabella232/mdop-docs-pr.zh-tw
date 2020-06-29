---
title: MED-V 2.0 最佳做法
description: MED-V 2.0 最佳做法
author: dansimp
ms.assetid: 47ba2dd1-6c6e-4d6e-8e18-b42291f8e02a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7b664d33b403b821ce6bc9c045d937380ab4f91b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811559"
---
# <span data-ttu-id="f94a6-103">MED-V 2.0 最佳做法</span><span class="sxs-lookup"><span data-stu-id="f94a6-103">MED-V 2.0 Best Practices</span></span>


<span data-ttu-id="f94a6-104">當您在企業中規劃、部署及管理 MED-V 時，您可能會發現最佳做法建議非常有用。</span><span class="sxs-lookup"><span data-stu-id="f94a6-104">When you are planning, deploying, and managing MED-V in your enterprise, you may find the best practice recommendations to be useful.</span></span>

### <span data-ttu-id="f94a6-105">將第一次設定設定為以無人值守的方式執行</span><span class="sxs-lookup"><span data-stu-id="f94a6-105">Configure first time setup to run unattended</span></span>

<span data-ttu-id="f94a6-106">雖然您可以指定任何您想要的設定，但 MED-V 是建立 Sysprep.inf 檔案，讓第一次設定可以在**無人參與**模式下執行。</span><span class="sxs-lookup"><span data-stu-id="f94a6-106">Although you can specify any settings that you prefer, a MED-V best practice is that you create the Sysprep.inf file so that first time setup can be run in **Unattended** mode.</span></span> <span data-ttu-id="f94a6-107">這需要您在繼續執行 [**安裝管理員**] 嚮導時提供所有必要的設定資訊。</span><span class="sxs-lookup"><span data-stu-id="f94a6-107">This requires you to provide all the required settings information as you continue through the **Setup Manager** wizard.</span></span> <span data-ttu-id="f94a6-108">如需如何設定 MED-V 影像的詳細資訊，請參閱設定[med-v 的 Windows 虛擬電腦影像](configuring-a-windows-virtual-pc-image-for-med-v.md)。</span><span class="sxs-lookup"><span data-stu-id="f94a6-108">For more information about how to configure the MED-V image, see [Configuring a Windows Virtual PC Image for MED-V](configuring-a-windows-virtual-pc-image-for-med-v.md).</span></span>

### <span data-ttu-id="f94a6-109">停用虛擬機器上的還原點</span><span class="sxs-lookup"><span data-stu-id="f94a6-109">Disable restore points on the virtual machine</span></span>

<span data-ttu-id="f94a6-110">在您建立 MED-V 工作區套件之前，我們建議您停用虛擬機器上的還原點，以避免差異磁片無限增加。</span><span class="sxs-lookup"><span data-stu-id="f94a6-110">Before you create the MED-V workspace package, we recommend that you disable restore points on the virtual machine to prevent the differencing disk from growing unbounded.</span></span> <span data-ttu-id="f94a6-111">如需詳細資訊，請參閱[如何在 WINDOWS XP 中關閉及開啟系統還原](https://go.microsoft.com/fwlink/?LinkId=195927)（ https://go.microsoft.com/fwlink/?LinkId=195927) 。</span><span class="sxs-lookup"><span data-stu-id="f94a6-111">For more information, see [How to turn off and turn on System Restore in Windows XP](https://go.microsoft.com/fwlink/?LinkId=195927) (https://go.microsoft.com/fwlink/?LinkId=195927).</span></span>

### <span data-ttu-id="f94a6-112">將 MED-V 影像設定為使用本機設定檔</span><span class="sxs-lookup"><span data-stu-id="f94a6-112">Configure MED-V image to use local profiles</span></span>

<span data-ttu-id="f94a6-113">我們建議您只在適用于 Windows XP 的應用程式相容性環境中，套用那些對您有意義的原則。</span><span class="sxs-lookup"><span data-stu-id="f94a6-113">We recommend that you apply only those policies that make sense in an application compatibility environment for Windows XP.</span></span> <span data-ttu-id="f94a6-114">例如，桌面自訂原則通常不需要套用，而且應該停用。</span><span class="sxs-lookup"><span data-stu-id="f94a6-114">For example, desktop customization policies do not typically have to be applied and should be disabled.</span></span> <span data-ttu-id="f94a6-115">如需如何只允許使用本機設定檔的詳細資訊，請參閱[漫遊使用者設定檔的群組原則設定](https://go.microsoft.com/fwlink/?LinkId=205072)（ https://go.microsoft.com/fwlink/?LinkId=205072) 。</span><span class="sxs-lookup"><span data-stu-id="f94a6-115">For more information about how to allow only local profiles, see [Group Policy Settings for Roaming User Profiles](https://go.microsoft.com/fwlink/?LinkId=205072) (https://go.microsoft.com/fwlink/?LinkId=205072).</span></span>

### <span data-ttu-id="f94a6-116">設定群組原則效能更新</span><span class="sxs-lookup"><span data-stu-id="f94a6-116">Configure a Group Policy performance update</span></span>

<span data-ttu-id="f94a6-117">根據預設，群群組原則一次會下載到電腦一個位元組。</span><span class="sxs-lookup"><span data-stu-id="f94a6-117">By default, Group Policy is downloaded to a computer one byte at a time.</span></span> <span data-ttu-id="f94a6-118">當 MED-V 加入網域時，這會造成延遲。</span><span class="sxs-lookup"><span data-stu-id="f94a6-118">This causes delays when MED-V is being joined to the domain.</span></span> <span data-ttu-id="f94a6-119">若要提高群組原則的效能，建議您將下列登錄機碼值設定為 registry：</span><span class="sxs-lookup"><span data-stu-id="f94a6-119">To increase the performance of Group Policy, we recommend that you set the following registry key value to the registry:</span></span>

<span data-ttu-id="f94a6-120">登錄子機碼： HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon</span><span class="sxs-lookup"><span data-stu-id="f94a6-120">Registry subkey: HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\Winlogon</span></span>

<span data-ttu-id="f94a6-121">專案： BufferPolicyReads</span><span class="sxs-lookup"><span data-stu-id="f94a6-121">Entry: BufferPolicyReads</span></span>

<span data-ttu-id="f94a6-122">類型： DWORD</span><span class="sxs-lookup"><span data-stu-id="f94a6-122">Type: DWORD</span></span>

<span data-ttu-id="f94a6-123">值：1</span><span class="sxs-lookup"><span data-stu-id="f94a6-123">Value: 1</span></span>

### <span data-ttu-id="f94a6-124">透過群組原則（而非 MED-V）來散佈法律通知</span><span class="sxs-lookup"><span data-stu-id="f94a6-124">Distribute legal notice through Group Policy instead of in the MED-V image</span></span>

<span data-ttu-id="f94a6-125">如果您想要讓使用者在存取 MED-V 之前看到服務等級協定（SLA），建議您稍後透過群組原則強制執行 SLA，以便在第一次完成設定之後向最終使用者顯示 SLA。</span><span class="sxs-lookup"><span data-stu-id="f94a6-125">If you want end users to see a service level agreement (SLA) before they access MED-V, we recommend that you enforce the SLA through Group Policy later so that the SLA is displayed to the end user after the first time setup is finished.</span></span>

<span data-ttu-id="f94a6-126">**小心** 雖然最佳做法是在**無人參與**模式下執行第一次安裝，但如果您決定要將本機原則或登錄專案設定為在您的影像（虛擬硬碟）中包含 SLA，您也必須指定第一次安裝程式在**有人參與**的模式下執行，或第一次設定可能失敗。</span><span class="sxs-lookup"><span data-stu-id="f94a6-126">**Caution** Even though a best practice is to run first time setup in **Unattended** mode, if you decide to set the local policy or registry entry to include an SLA in your image (virtual hard disk), you must also specify that first time setup is run in **Attended** mode, or first time setup can fail.</span></span>

 

### <span data-ttu-id="f94a6-127">壓縮虛擬硬碟</span><span class="sxs-lookup"><span data-stu-id="f94a6-127">Compact the virtual hard disk</span></span>

<span data-ttu-id="f94a6-128">我們建議您壓縮虛擬硬碟以回收空白磁碟空間，並減少虛擬硬碟的大小。</span><span class="sxs-lookup"><span data-stu-id="f94a6-128">We recommend that you compact your virtual hard disk to reclaim empty disk space and reduce the size of the virtual hard disk.</span></span> <span data-ttu-id="f94a6-129">如需如何壓縮虛擬硬碟的詳細資訊，請參閱[壓縮 Med-v 虛擬硬碟](compacting-the-med-v-virtual-hard-disk.md)。</span><span class="sxs-lookup"><span data-stu-id="f94a6-129">For more information about how to compact your virtual hard disk, see [Compacting the MED-V Virtual Hard Disk](compacting-the-med-v-virtual-hard-disk.md).</span></span>

### <span data-ttu-id="f94a6-130">將虛擬機器設定為在藍屏系統崩潰時重新開機</span><span class="sxs-lookup"><span data-stu-id="f94a6-130">Configure virtual machine to restart on blue screen crash</span></span>

<span data-ttu-id="f94a6-131">我們建議您將 MED-V 工作區虛擬機器設定為在遇到藍色螢幕損毀時自動重新開機。</span><span class="sxs-lookup"><span data-stu-id="f94a6-131">We recommend that you configure the MED-V workspace virtual machine to automatically restart when it encounters a blue screen crash.</span></span> <span data-ttu-id="f94a6-132">若要在來賓中設定此設定，請將 HKEY \ _LOCAL \ _MACHINE \\SYSTEM\\CurrentControlSet\\Control\\CrashControl 鍵中的 AutoReboot 值設為 "1"。</span><span class="sxs-lookup"><span data-stu-id="f94a6-132">To configure this setting in the guest, set the AutoReboot value in the HKEY\_LOCAL\_MACHINE\\SYSTEM\\CurrentControlSet\\Control\\CrashControl key to “1”.</span></span>

<span data-ttu-id="f94a6-133">您也可以按一下 [**開始**]，按一下 [**控制台**]，然後按一下 [**系統**]，來設定此設定。</span><span class="sxs-lookup"><span data-stu-id="f94a6-133">You can also configure this setting by clicking **Start**, clicking **Control Panel**, and then clicking **System**.</span></span> <span data-ttu-id="f94a6-134">接著，在 [**高級**] 索引標籤的 [**啟動及修復**] 區域中，按一下 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="f94a6-134">Then, in the **Startup and Recovery** area of the **Advanced** tab, click **Settings**.</span></span> <span data-ttu-id="f94a6-135">選取 [**自動重新開機**] 核取方塊，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="f94a6-135">Select the **Automatically restart** check box and click **OK**.</span></span>

### <span data-ttu-id="f94a6-136">在封裝 MED-V 圖像之前先進行備份</span><span class="sxs-lookup"><span data-stu-id="f94a6-136">Back up MED-V image before sealing it</span></span>

<span data-ttu-id="f94a6-137">我們建議您先建立 MED-V 影像的備份複本，然後再將其密封。</span><span class="sxs-lookup"><span data-stu-id="f94a6-137">We recommend that you create a backup copy of the MED-V image before you seal it.</span></span> <span data-ttu-id="f94a6-138">如需有關密封 MED-V 影像的詳細資訊，請參閱設定[med-v 的 Windows 虛擬電腦影像](configuring-a-windows-virtual-pc-image-for-med-v.md)。</span><span class="sxs-lookup"><span data-stu-id="f94a6-138">For more information about sealing your MED-V image, see [Configuring a Windows Virtual PC Image for MED-V](configuring-a-windows-virtual-pc-image-for-med-v.md).</span></span>

### <span data-ttu-id="f94a6-139">從批次檔案安裝時，最後安裝 Windows Virtual 電腦</span><span class="sxs-lookup"><span data-stu-id="f94a6-139">Install Windows Virtual PC last when installing from a batch file</span></span>

<span data-ttu-id="f94a6-140">當您使用批次檔案安裝 MED-V 元件時，請指定是在 MED-V 主機代理程式和 MED-V 工作區套件檔案之後，再安裝 Windows 虛擬電腦和 Windows 虛擬電腦熱修復程式。</span><span class="sxs-lookup"><span data-stu-id="f94a6-140">When you install the MED-V components by using a batch file, specify that Windows Virtual PC and the Windows Virtual PC hotfix are installed after the MED-V Host Agent and the MED-V workspace package files.</span></span> <span data-ttu-id="f94a6-141">這可確保 Windows 更新不會因需要重新開機而對安裝程式造成任何干擾。</span><span class="sxs-lookup"><span data-stu-id="f94a6-141">This ensures that Windows Update will not cause any interference with the installation process by requiring a restart.</span></span>

### <span data-ttu-id="f94a6-142">從本機資料夾安裝 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="f94a6-142">Install MED-V workspace from local folder</span></span>

<span data-ttu-id="f94a6-143">由於您從網路位置安裝 MED-V 時可能會發生的問題，因此建議您在本機複製 MED-V 工作區設定檔案，然後執行 setup.exe。</span><span class="sxs-lookup"><span data-stu-id="f94a6-143">Because of problems that can occur when you install MED-V from a network location, we recommend that you copy the MED-V workspace setup files locally and then run setup.exe.</span></span>

### <a href="" id="manage-printer-redirection-in-one-manner-only-"></a><span data-ttu-id="f94a6-144">僅以一種方式管理印表機重定向</span><span class="sxs-lookup"><span data-stu-id="f94a6-144">Manage printer redirection in one manner only</span></span>

<span data-ttu-id="f94a6-145">如果您在 MED-V 來賓虛擬機器上手動安裝印表機，且在主機電腦上安裝相同的印表機，則結果是在來賓中安裝了兩次。</span><span class="sxs-lookup"><span data-stu-id="f94a6-145">If a printer is manually installed on the MED-V guest virtual machine, and the same printer is later installed on the host computer, the result is that it is installed two times in the guest.</span></span> <span data-ttu-id="f94a6-146">為了避免這種情況，我們建議您以單一方式管理印表機重新導向的 MED-V 最佳做法：停用來賓的重新導向及手動安裝印表機，或啟用重新導向，並不要在來賓上手動安裝印表機。</span><span class="sxs-lookup"><span data-stu-id="f94a6-146">To avoid this situation, we recommend as MED-V best practice that you manage printer redirection in one manner only: either disable redirection and install printers manually on the guest, or enable redirection and do not install printers manually on the guest.</span></span>

### <a href="" id="configure-settings-for-med-v-guest-patching-"></a><span data-ttu-id="f94a6-147">設定 MED-V 訪客修補程式的設定</span><span class="sxs-lookup"><span data-stu-id="f94a6-147">Configure settings for MED-V guest patching</span></span>

<span data-ttu-id="f94a6-148">您可以在 registry 中定義相關的設定值，以控制 MED-V 虛擬機器 awakens 接收自動更新的時間和時間。</span><span class="sxs-lookup"><span data-stu-id="f94a6-148">You can control when and for how long the MED-V virtual machine awakens to receive automatic updates by defining the relevant configuration values in the registry.</span></span> <span data-ttu-id="f94a6-149">MED-V 最佳做法是設定喚醒間隔，以符合您針對 MED-V 虛擬機器排程定期更新的時間。</span><span class="sxs-lookup"><span data-stu-id="f94a6-149">A MED-V best practice is to set your wake-up interval to match the time when you have scheduled regular updates for MED-V virtual machines.</span></span> <span data-ttu-id="f94a6-150">此外，建議您將這些設定設定為類似主機電腦的行為。</span><span class="sxs-lookup"><span data-stu-id="f94a6-150">In addition, we recommend that you configure these settings to resemble the host computer’s behavior.</span></span>

<span data-ttu-id="f94a6-151">如需有關如何設定 MED-V 訪客修補程式設定的詳細資訊，請參閱[管理 Med-v 工作區的自動更新](managing-automatic-updates-for-med-v-workspaces.md)。</span><span class="sxs-lookup"><span data-stu-id="f94a6-151">For more information about how to configure settings for MED-V guest patching, see [Managing Automatic Updates for MED-V Workspaces](managing-automatic-updates-for-med-v-workspaces.md).</span></span>

### <span data-ttu-id="f94a6-152">設定防毒軟體/備份軟體</span><span class="sxs-lookup"><span data-stu-id="f94a6-152">Configure antivirus/backup software</span></span>

<span data-ttu-id="f94a6-153">若要防止防病毒活動影響虛擬桌面的效能，建議您在可以時將下列虛擬機器檔案類型排除在由 MED-V 主機電腦上執行的任何防毒軟體或備份程式中：</span><span class="sxs-lookup"><span data-stu-id="f94a6-153">To prevent antivirus activity from affecting the performance of the virtual desktop, we recommend that when you can, you exclude the following virtual machine file types from any antivirus or backup process that is running on the MED-V host computer:</span></span>

-   <span data-ttu-id="f94a6-154">\*.VMC</span><span class="sxs-lookup"><span data-stu-id="f94a6-154">\*.VMC</span></span>

-   <span data-ttu-id="f94a6-155">\*.VUD</span><span class="sxs-lookup"><span data-stu-id="f94a6-155">\*.VUD</span></span>

-   <span data-ttu-id="f94a6-156">\*.VSV</span><span class="sxs-lookup"><span data-stu-id="f94a6-156">\*.VSV</span></span>

-   <span data-ttu-id="f94a6-157">\*.VHD</span><span class="sxs-lookup"><span data-stu-id="f94a6-157">\*.VHD</span></span>

## <span data-ttu-id="f94a6-158">相關主題</span><span class="sxs-lookup"><span data-stu-id="f94a6-158">Related topics</span></span>


[<span data-ttu-id="f94a6-159">MED-V 的安全性與保護</span><span class="sxs-lookup"><span data-stu-id="f94a6-159">Security and Protection for MED-V</span></span>](security-and-protection-for-med-v.md)

 

 





