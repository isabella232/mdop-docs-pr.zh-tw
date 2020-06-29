---
title: 管理 MED-V 工作區的自動更新
description: 管理 MED-V 工作區的自動更新
author: dansimp
ms.assetid: 306f28a2-d653-480d-b737-4b8b3132de5d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: b22d3250db806e740c1d62da4fed98d5956b0eeb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811067"
---
# <span data-ttu-id="2a7e3-103">管理 MED-V 工作區的自動更新</span><span class="sxs-lookup"><span data-stu-id="2a7e3-103">Managing Automatic Updates for MED-V Workspaces</span></span>


<span data-ttu-id="2a7e3-104">MED-V 工作區是一個虛擬電腦，其中包含獨立的作業系統，其自動軟體更新程式必須與企業中的物理電腦一樣加以管理。</span><span class="sxs-lookup"><span data-stu-id="2a7e3-104">The MED-V workspace is a virtual machine that contains a separate operating system, whose automatic software update process must be managed just like the physical computers in your enterprise.</span></span> <span data-ttu-id="2a7e3-105">因為在主機作業系統執行時，客體作業系統不一定要執行，所以您必須確認 MED-V 虛擬機器已設定為可根據需要將軟體更新套用至客體作業系統。</span><span class="sxs-lookup"><span data-stu-id="2a7e3-105">Because the guest operating system is not always necessarily running when the host operating system is running, you must ensure that the MED-V virtual machine is configured in such a way that software updates can be applied to the guest operating system as required.</span></span> <span data-ttu-id="2a7e3-106">Microsoft 企業版桌面虛擬化（MED-V）2.0 解決方案提供的功能可讓您判斷自動軟體更新在 MED-V 工作區中的處理方式。</span><span class="sxs-lookup"><span data-stu-id="2a7e3-106">The Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 solution provides the functionality that lets you determine how automatic software updates are processed in a MED-V workspace.</span></span>

## <span data-ttu-id="2a7e3-107">管理 MED-V-V 工作區喚醒原則</span><span class="sxs-lookup"><span data-stu-id="2a7e3-107">Managing MED-V Workspace Wake-Up Policy</span></span>


<span data-ttu-id="2a7e3-108">MED-V 工作區喚醒原則可保證在 MED-V 設定設定中所指定的時間，將 MED-V 虛擬機器提供給更新。</span><span class="sxs-lookup"><span data-stu-id="2a7e3-108">The MED-V workspace wake-up policy guarantees that the MED-V virtual machine is made available for updates for the time that you specify in your MED-V configuration settings.</span></span> <span data-ttu-id="2a7e3-109">這適用于從 Microsoft 透過 Windows Update 發佈的更新，以及由非 Microsoft 解決方案（例如防病毒應用程式）部署及控制的更新。</span><span class="sxs-lookup"><span data-stu-id="2a7e3-109">This applies to both updates that are published from Microsoft through Windows Update and updates deployed and controlled by non-Microsoft solutions, such as antivirus applications.</span></span>

<span data-ttu-id="2a7e3-110">**重要** MED-V 工作區喚醒原則已針對 Microsoft 更新基礎結構進行優化。</span><span class="sxs-lookup"><span data-stu-id="2a7e3-110">**Important** The MED-V workspace wake-up policy is optimized for the Microsoft Update infrastructure.</span></span> <span data-ttu-id="2a7e3-111">如果您使用 Microsoft System Center Configuration Manager 來部署非 Microsoft 更新，我們建議您同時使用 System Center 更新發行者，這會利用與 Microsoft Update 相同的基礎結構，因此可從 MED-V 工作區的喚醒原則獲益。</span><span class="sxs-lookup"><span data-stu-id="2a7e3-111">If you are using Microsoft System Center Configuration Manager to deploy non-Microsoft updates, we recommend that you also use the System Center Updates Publisher, which takes advantage of the same infrastructure as Microsoft Update and therefore benefits from the MED-V workspace wake-up policy.</span></span> <span data-ttu-id="2a7e3-112">如需詳細資訊，請參閱[系統中心更新發行者](https://go.microsoft.com/fwlink/?LinkId=200035)（ https://go.microsoft.com/fwlink/?LinkId=200035) 。</span><span class="sxs-lookup"><span data-stu-id="2a7e3-112">For more information, see [System Center Updates Publisher](https://go.microsoft.com/fwlink/?LinkId=200035) (https://go.microsoft.com/fwlink/?LinkId=200035).</span></span>

 

<span data-ttu-id="2a7e3-113">當您建立 MED-V 工作區套件時，您可以在使用者登入時（**快速啟動**），或當使用者第一次開啟發佈的應用程式（**正常啟動**）時，進行設定。</span><span class="sxs-lookup"><span data-stu-id="2a7e3-113">When you created your MED-V workspace package, you configured when and how it starts, either when the end user logs on (**Fast Start**) or when the end user first opens a published application (**Normal Start**).</span></span> <span data-ttu-id="2a7e3-114">或者，您可以設定讓使用者控制此設定的選項。</span><span class="sxs-lookup"><span data-stu-id="2a7e3-114">Or you set the option to let the end user control this setting.</span></span>

<span data-ttu-id="2a7e3-115">不論是哪一種方式，只要選取 [**快速啟動**] 選項，只要 med-v 主機以使用者身分登入，虛擬機器就會繼續執行。</span><span class="sxs-lookup"><span data-stu-id="2a7e3-115">Either way, whenever the **Fast Start** option is selected, the virtual machine continues to run as long as the MED-V host is logged on as User.</span></span> <span data-ttu-id="2a7e3-116">在這個設定中，因為主機在使用中時，MED-V 是作用中的，所以自動更新會在不需要從 MED-V 進行任何額外處理的情況下套用。</span><span class="sxs-lookup"><span data-stu-id="2a7e3-116">In this configuration, because MED-V is active when the host is active, automatic updates are applied without requiring any extra processing from MED-V.</span></span>

<span data-ttu-id="2a7e3-117">不過，對於未指定**快速啟動**或虛擬機器處於休眠或停止狀態的情況，med-v 會透過其 med-v 工作區喚醒原則（即使未定期使用 med-v），也能保證該客體作業系統會定期更新。</span><span class="sxs-lookup"><span data-stu-id="2a7e3-117">However, for those cases in which **Fast Start** is not specified or the virtual machine hibernates or stops, MED-V guarantees through its MED-V workspace wake-up policy that the guest operating system is being regularly updated even when MED-V is not used regularly.</span></span> <span data-ttu-id="2a7e3-118">MED-V 會根據您指定的設定設定，定期喚醒虛擬機器來執行此功能。</span><span class="sxs-lookup"><span data-stu-id="2a7e3-118">MED-V performs this function by regularly waking up the virtual machine based on the configuration settings that you specify.</span></span> <span data-ttu-id="2a7e3-119">這可讓虛擬機器中的自動更新用戶端根據其配置執行。</span><span class="sxs-lookup"><span data-stu-id="2a7e3-119">This enables the automatic update clients in the virtual machine to execute based on their configurations.</span></span><span data-ttu-id="2a7e3-120">在由 MED-V 設定設定所定義的時間週期過後，MED-V 會將虛擬機器傳回其先前的狀態。</span><span class="sxs-lookup"><span data-stu-id="2a7e3-120">After the time period defined by the MED-V configuration setting elapses, MED-V returns the virtual machine to its previous state.</span></span>

<span data-ttu-id="2a7e3-121">**記事** 如果使用者在更新期間開啟發佈的應用程式，則會套用所需的更新，但在更新期間結束後，MED-V 不會自動休眠或關閉。</span><span class="sxs-lookup"><span data-stu-id="2a7e3-121">**Note** If the end user opens a published application during the update period, the required updates are applied, but MED-V is not automatically hibernated or shut down after the update period ends.</span></span> <span data-ttu-id="2a7e3-122">相反地，MED-V 會繼續執行。</span><span class="sxs-lookup"><span data-stu-id="2a7e3-122">Instead, MED-V continues running.</span></span>

 

<span data-ttu-id="2a7e3-123">MED-V 工作區喚醒原則包含三個主要元件：</span><span class="sxs-lookup"><span data-stu-id="2a7e3-123">The MED-V workspace wake-up policy includes three main components:</span></span>

**<span data-ttu-id="2a7e3-124">來賓更新管理員</span><span class="sxs-lookup"><span data-stu-id="2a7e3-124">Guest Update Manager</span></span>**

<span data-ttu-id="2a7e3-125">這個獨立的可執行程式位於 MED-V 主機上，負責根據預先定義且可設定的排程來喚醒虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="2a7e3-125">Residing on the MED-V host, this stand-alone executable program is responsible for waking up the virtual machine according to a predefined, configurable schedule.</span></span> <span data-ttu-id="2a7e3-126">指定 [設定] 設定，以指出更新管理員每天要喚醒虛擬機器的時間，以及虛擬機器應保持在最新狀態（以分鐘為單位）以允許應用更新的時間。</span><span class="sxs-lookup"><span data-stu-id="2a7e3-126">Specify the configuration settings to indicate at what time the update manager should wake up the virtual machine every day, and how long the virtual machine should be kept awake (in minutes) to allow for updates to be applied.</span></span> <span data-ttu-id="2a7e3-127">在已達到指定的分鐘數之後，來賓更新管理員會將虛擬機器置於休眠，準備好供下次使用。</span><span class="sxs-lookup"><span data-stu-id="2a7e3-127">After the number of minutes specified has been reached, the guest update manager puts the virtual machine into hibernation, prepared for the next use.</span></span> <span data-ttu-id="2a7e3-128">您可以透過 Windows [工作管理員]，排程此可執行程式的執行。</span><span class="sxs-lookup"><span data-stu-id="2a7e3-128">You can schedule the execution of this executable program through the Windows Task Manager.</span></span>

**<span data-ttu-id="2a7e3-129">來賓重新開機管理服務</span><span class="sxs-lookup"><span data-stu-id="2a7e3-129">Guest Restart Management Service</span></span>**

<span data-ttu-id="2a7e3-130">此服務位於 MED-V 主機上，有三個主要職責。</span><span class="sxs-lookup"><span data-stu-id="2a7e3-130">Residing on the MED-V host, this service has three primary responsibilities.</span></span> <span data-ttu-id="2a7e3-131">隨著來賓更新管理員，它會在使用者登入時管理虛擬機器的重新開機（如果需要的話）。</span><span class="sxs-lookup"><span data-stu-id="2a7e3-131">Along with the Guest Update Manager, it manages the restart of the virtual machine at user logon, if it is required.</span></span> <span data-ttu-id="2a7e3-132">它會偵測到需要重新開機虛擬機器的情況，因為更新已安裝。</span><span class="sxs-lookup"><span data-stu-id="2a7e3-132">It detects when virtual machine restarts are required caused by updates being installed.</span></span> <span data-ttu-id="2a7e3-133">而且它可確保來賓更新管理員的工作會根據設定隨時排程。</span><span class="sxs-lookup"><span data-stu-id="2a7e3-133">And it ensures that the task for the Guest Update Manager is always scheduled according to configuration.</span></span>

**<span data-ttu-id="2a7e3-134">來賓更新服務</span><span class="sxs-lookup"><span data-stu-id="2a7e3-134">Guest Update Service</span></span>**

<span data-ttu-id="2a7e3-135">此 Windows 服務位於 MED-V 虛擬機器上，負責在已安裝更新需要重新開機時進行監視。</span><span class="sxs-lookup"><span data-stu-id="2a7e3-135">Residing on the MED-V virtual machine, this Windows service has the responsibility of monitoring when installed updates require a restart.</span></span> <span data-ttu-id="2a7e3-136">在服務意識到需要重新開機之後，它會通知主機上的來賓重新開機管理服務。</span><span class="sxs-lookup"><span data-stu-id="2a7e3-136">After the service becomes aware of the need for a restart, it notifies the guest restart management service on the host.</span></span>

### <span data-ttu-id="2a7e3-137">MED-V 工作區喚醒原則的配置設定</span><span class="sxs-lookup"><span data-stu-id="2a7e3-137">Configuration Settings for MED-V Workspace Wake-Up Policy</span></span>

<span data-ttu-id="2a7e3-138">您可以在登錄中定義下列兩個設定值，以控制虛擬機器 awakens 接收自動更新的時間和時間。</span><span class="sxs-lookup"><span data-stu-id="2a7e3-138">You control when and for how long the virtual machine awakens to receive automatic updates by defining the following two configuration values in the registry.</span></span> <span data-ttu-id="2a7e3-139">這兩個值都位於 HKLM\\Software\\Microsoft\\MEDV\\v2\\VM 索引鍵底下。</span><span class="sxs-lookup"><span data-stu-id="2a7e3-139">Both of these values are located under the HKLM\\Software\\Microsoft\\MEDV\\v2\\VM key.</span></span>

<span data-ttu-id="2a7e3-140">**GuestUpdateTime** –在 med-v 必須根據24小時制的時鐘標準來喚醒虛擬機器以進行更新，每日設定小時與分鐘數。</span><span class="sxs-lookup"><span data-stu-id="2a7e3-140">**GuestUpdateTime** – Configures the hour and minute each day when MED-V must wake up the virtual machine for updating, based on the 24-hour clock standard.</span></span> <span data-ttu-id="2a7e3-141">以 HH： MM 格式指定時間。</span><span class="sxs-lookup"><span data-stu-id="2a7e3-141">Specify the time in the format HH:MM.</span></span> <span data-ttu-id="2a7e3-142">預設值為00:00 （午夜）。</span><span class="sxs-lookup"><span data-stu-id="2a7e3-142">The default value is 00:00 (midnight).</span></span>

<span data-ttu-id="2a7e3-143">**GuestUpdateDuration** –設定 med-v 必須讓虛擬機器保持從喚醒來更新的分鐘數，從在 GuestUpdateTime 設定設定中指定的時間開始。</span><span class="sxs-lookup"><span data-stu-id="2a7e3-143">**GuestUpdateDuration** – Configures the number of minutes that MED-V must keep the virtual machine awake for updating, starting at the time specified in the GuestUpdateTime configuration setting.</span></span> <span data-ttu-id="2a7e3-144">預設值為240（4小時）。</span><span class="sxs-lookup"><span data-stu-id="2a7e3-144">The default value is 240 (4 hours).</span></span> <span data-ttu-id="2a7e3-145">將此值設定為零（0）會停用 MED-V 工作區喚醒原則。</span><span class="sxs-lookup"><span data-stu-id="2a7e3-145">Setting this value to zero (0) disables the MED-V workspace wake-up policy.</span></span>

<span data-ttu-id="2a7e3-146">如需如何定義 MED-V 設定值的詳細資訊，請參閱[管理 Med-v 工作區配置設定](managing-med-v-workspace-configuration-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="2a7e3-146">For more information about how to define your MED-V configuration values, see [Managing MED-V Workspace Configuration Settings](managing-med-v-workspace-configuration-settings.md).</span></span>

<span data-ttu-id="2a7e3-147">**記事** MED-V 最佳做法是設定您的喚醒間隔，以符合 MED-V 虛擬機器計畫定期更新的時間。</span><span class="sxs-lookup"><span data-stu-id="2a7e3-147">**Note** A MED-V best practice is to set your wake up interval to match the time when MED-V virtual machines are planned to be updated regularly.</span></span> <span data-ttu-id="2a7e3-148">此外，建議您將這些設定設定為類似主機電腦的行為。</span><span class="sxs-lookup"><span data-stu-id="2a7e3-148">In addition, we recommend that you configure these settings to resemble the host computer’s behavior.</span></span>

 

### <span data-ttu-id="2a7e3-149">使用 ESD 系統重新開機通知</span><span class="sxs-lookup"><span data-stu-id="2a7e3-149">Reboot Notification Using your ESD System</span></span>

<span data-ttu-id="2a7e3-150">您可以將您的 ESD 系統設定為在應用自動更新之後，在 MED-V 工作區需要重新開機時通知 MED-V。</span><span class="sxs-lookup"><span data-stu-id="2a7e3-150">You can configure your ESD system to notify MED-V whenever a restart is required for the MED-V workspace after automatic updates have been applied.</span></span> <span data-ttu-id="2a7e3-151">當您在您知道需要重新開機的 ESD 系統中套用自動更新時，您應該撰寫腳本以在 MED-V 工作區上通知下列全域事件：</span><span class="sxs-lookup"><span data-stu-id="2a7e3-151">When you apply automatic updates through your ESD system that you know require a restart, you should write a script to signal the following global event on the MED-V workspace:</span></span>

<span data-ttu-id="2a7e3-152">**重要** 您必須以 [只修改] 許可權開啟事件，然後向其發出通知。</span><span class="sxs-lookup"><span data-stu-id="2a7e3-152">**Important** You must open the event with Modify Only rights and then signal it.</span></span> <span data-ttu-id="2a7e3-153">如果您不是以正確的許可權開啟，就無法使用。</span><span class="sxs-lookup"><span data-stu-id="2a7e3-153">If you do not open it with the correct permissions, it does not work.</span></span>

 

``` syntax
/// <summary>
/// The guest is required to be restarted due to an ESD update.
/// </summary>
public const string MedvGuestRebootRequiredEventName = @"Global\MedvGuestRebootRequiredEvent";
using (EventWaitHandle notificationEvent = 
EventWaitHandle.OpenExisting(eventName, EventWaitHandleRights.Modify))
{
notificationEvent.Set();
}
```

<span data-ttu-id="2a7e3-154">當您發出這個事件的信號時，MED-V 會捕獲它，並通知虛擬機器需要重新開機。</span><span class="sxs-lookup"><span data-stu-id="2a7e3-154">When you signal this event, MED-V captures it and informs the virtual machine that a restart is required.</span></span>

## <span data-ttu-id="2a7e3-155">相關主題</span><span class="sxs-lookup"><span data-stu-id="2a7e3-155">Related topics</span></span>


[<span data-ttu-id="2a7e3-156">管理 MED-V 工作區的軟體更新</span><span class="sxs-lookup"><span data-stu-id="2a7e3-156">Managing Software Updates for MED-V Workspaces</span></span>](managing-software-updates-for-med-v-workspaces.md)

 

 





