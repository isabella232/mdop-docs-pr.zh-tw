---
title: 管理由 UE-V 2. x 的系統管理備份和還原
description: 管理由 UE-V 2. x 的系統管理備份和還原
author: dansimp
ms.assetid: 2eb5ae75-65e5-4afc-adb6-4e83cf4364ae
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 11c168b54b71731c51417b2b7c4737c85f42035a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812326"
---
# <span data-ttu-id="09685-103">管理由 UE-V 2. x 的系統管理備份和還原</span><span class="sxs-lookup"><span data-stu-id="09685-103">Manage Administrative Backup and Restore in UE-V 2.x</span></span>


<span data-ttu-id="09685-104">如果您是 Microsoft 使用者體驗虛擬化（UE-V）2.0、2.1 或 2.1 SP1 的管理員，您可以將應用程式和 Windows 設定還原至其原始狀態。</span><span class="sxs-lookup"><span data-stu-id="09685-104">As an administrator of Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, or 2.1 SP1, you can restore application and Windows settings to their original state.</span></span> <span data-ttu-id="09685-105">此外，UE-V 2.1 中的新功能，您也可以在使用者採用新的裝置時還原其他設定。</span><span class="sxs-lookup"><span data-stu-id="09685-105">And new in UE-V 2.1, you can also restore additional settings when a user adopts a new device.</span></span>

## <span data-ttu-id="09685-106">當使用者採用新的裝置時，在 UE-V 2.1 或 UE-V 2.1 SP1 中還原設定</span><span class="sxs-lookup"><span data-stu-id="09685-106">Restore Settings in UE-V 2.1 or UE-V 2.1 SP1 when a User Adopts a New Device</span></span>


<span data-ttu-id="09685-107">若要在使用者採用新的裝置時還原設定，您可以使用 UevTemplateProfile PowerShell Cmdlet，將 [設定位置] 範本放在**備份**或**漫遊（預設）** 設定檔中。</span><span class="sxs-lookup"><span data-stu-id="09685-107">To restore settings when a user adopts a new device, you can put a settings location template in **backup** or **roam (default)** profile using the Set-UevTemplateProfile PowerShell cmdlet.</span></span> <span data-ttu-id="09685-108">這可讓電腦設定與新電腦同步處理，以及使用者設定。</span><span class="sxs-lookup"><span data-stu-id="09685-108">This lets computer settings sync to the new computer, in addition to user settings.</span></span> <span data-ttu-id="09685-109">系統會針對該裝置備份指派給備份設定檔的範本，並針對每個裝置進行設定。</span><span class="sxs-lookup"><span data-stu-id="09685-109">Templates assigned to the backup profile are backed up for that device and configured on a per-device basis.</span></span> <span data-ttu-id="09685-110">若要備份範本的設定，請在 Windows PowerShell 中使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="09685-110">To backup settings for a template, use the following cmdlet in Windows PowerShell:</span></span>

``` syntax
Set-UevTemplateProfile -ID <TemplateID> -Profile <backup>
```

-   <span data-ttu-id="09685-111">&lt;TemplateID &gt; 是 Ue-v 範本識別碼</span><span class="sxs-lookup"><span data-stu-id="09685-111">&lt;TemplateID&gt; is the UE-V Template ID</span></span>

-   <span data-ttu-id="09685-112">&lt;備份 &gt; 可以是 [備份] 或 [漫遊]</span><span class="sxs-lookup"><span data-stu-id="09685-112">&lt;backup&gt; can either be Backup or Roaming</span></span>

<span data-ttu-id="09685-113">如果使用者的網域、使用者名稱和裝置名稱全部相符，當您取代使用者的裝置 UE-V 時，系統會自動還原設定。</span><span class="sxs-lookup"><span data-stu-id="09685-113">When replacing a user’s device UE-V automatically restores settings if the user’s domain, username, and device name all match.</span></span> <span data-ttu-id="09685-114">所有已同步處理，且所有備份資料都會自動在裝置上還原。</span><span class="sxs-lookup"><span data-stu-id="09685-114">All synchronized and any backup data is restored on the device automatically.</span></span>

<span data-ttu-id="09685-115">您也可以使用新的 PowerShell Cmdlet （還原-UevBackup）來還原不同裝置上的設定。</span><span class="sxs-lookup"><span data-stu-id="09685-115">You can also use the new PowerShell cmdlet, Restore-UevBackup, to restore settings from a different device.</span></span> <span data-ttu-id="09685-116">若要克隆新裝置的設定套件，請在 Windows PowerShell 中使用下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="09685-116">To clone the settings packages for the new device, use the following cmdlet in Windows PowerShell:</span></span>

``` syntax
Restore-UevBackup –Machine <MachineName>
```

<span data-ttu-id="09685-117">其中， &lt; MachineName &gt; 是裝置的電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="09685-117">where &lt;MachineName&gt; is the computer name of the device.</span></span>

<span data-ttu-id="09685-118">包括許多應用程式的 Office 2013 範本等範本，都可以全部包含在漫遊（預設）或備份設定檔中。</span><span class="sxs-lookup"><span data-stu-id="09685-118">Templates such as the Office 2013 template that include many applications can either all be included in the roamed (default) or backed up profile.</span></span> <span data-ttu-id="09685-119">範本套件中的個別應用程式會跟隨群組。</span><span class="sxs-lookup"><span data-stu-id="09685-119">Individual apps in a template suite follow the group.</span></span> <span data-ttu-id="09685-120">Office 2013 的內框範本包括漫遊和只備份設定。</span><span class="sxs-lookup"><span data-stu-id="09685-120">Office 2013 in-box templates include both roaming and backup-only settings.</span></span> <span data-ttu-id="09685-121">[僅限備份] 設定不能包含在漫遊設定檔中。</span><span class="sxs-lookup"><span data-stu-id="09685-121">Backup-only settings cannot be included in a roaming profile.</span></span>

<span data-ttu-id="09685-122">在 [備份/還原] 功能中，UE-V 將 [**上一個已知的良好（LKG）** ] 新增到 [回滾至設定] 的選項。</span><span class="sxs-lookup"><span data-stu-id="09685-122">As part of the Backup/Restore feature, UE-V added **last known good (LKG)** to the options for rolling back to settings.</span></span> <span data-ttu-id="09685-123">在這個版本中，您可以返回原始設定或 LKG 設定。</span><span class="sxs-lookup"><span data-stu-id="09685-123">In this release, you can roll back to either the original settings or LKG settings.</span></span> <span data-ttu-id="09685-124">[LKG] 設定可讓使用者回滾到設定的 UE-V 之前的中間與穩定點。</span><span class="sxs-lookup"><span data-stu-id="09685-124">The LKG settings let users roll back to an intermediate and stable point ahead of the pre-UE-V state of the settings.</span></span>

### <span data-ttu-id="09685-125">如何使用 UE-V 備份/還原範本</span><span class="sxs-lookup"><span data-stu-id="09685-125">How to Backup/Restore Templates with UE-V</span></span>

<span data-ttu-id="09685-126">以下是 UE-V 的主要備份和還原元件：</span><span class="sxs-lookup"><span data-stu-id="09685-126">These are the key backup and restore components of UE-V:</span></span>

-   <span data-ttu-id="09685-127">範本設定檔</span><span class="sxs-lookup"><span data-stu-id="09685-127">Template profiles</span></span>

-   <span data-ttu-id="09685-128">[設定] 儲存位置範本中的 [設定套件] 位置</span><span class="sxs-lookup"><span data-stu-id="09685-128">Settings packages location within the Settings Storage Location template</span></span>

-   <span data-ttu-id="09685-129">備份觸發程式</span><span class="sxs-lookup"><span data-stu-id="09685-129">Backup trigger</span></span>

-   <span data-ttu-id="09685-130">如何還原設定</span><span class="sxs-lookup"><span data-stu-id="09685-130">How settings are restored</span></span>

**<span data-ttu-id="09685-131">範本設定檔</span><span class="sxs-lookup"><span data-stu-id="09685-131">Template Profiles</span></span>**

<span data-ttu-id="09685-132">UE-V 範本設定檔是在您在裝置上註冊範本，或是透過 PowerShell/WMI 配置實用程式進行發佈時定義。</span><span class="sxs-lookup"><span data-stu-id="09685-132">A UE-V template profile is defined when the template is registered on the device or post registration through the PowerShell/WMI configuration utility.</span></span> <span data-ttu-id="09685-133">配置檔案類型包括：</span><span class="sxs-lookup"><span data-stu-id="09685-133">The profile types include:</span></span>

-   <span data-ttu-id="09685-134">漫遊（預設）</span><span class="sxs-lookup"><span data-stu-id="09685-134">Roaming (default)</span></span>

-   <span data-ttu-id="09685-135">備份</span><span class="sxs-lookup"><span data-stu-id="09685-135">Backup</span></span>

-   <span data-ttu-id="09685-136">BackupOnly</span><span class="sxs-lookup"><span data-stu-id="09685-136">BackupOnly</span></span>

<span data-ttu-id="09685-137">除非另外指定，否則在註冊前，所有範本都包含在漫遊設定檔中。</span><span class="sxs-lookup"><span data-stu-id="09685-137">All templates are included in the roaming profile when registered unless otherwise specified.</span></span> <span data-ttu-id="09685-138">這些範本會將設定同步處理到已啟用對應範本的所有 UE-V 啟用裝置。</span><span class="sxs-lookup"><span data-stu-id="09685-138">These templates synchronize settings to all UE-V enabled devices with the corresponding template enabled.</span></span>

<span data-ttu-id="09685-139">您可以使用 UevTemplateProfile Cmdlet，在擁有 PowerShell 或 WMI 的備份設定檔中新增範本。</span><span class="sxs-lookup"><span data-stu-id="09685-139">Templates can be added to the Backup Profile with PowerShell or WMI using the Set-UevTemplateProfile cmdlet.</span></span> <span data-ttu-id="09685-140">備份設定檔中的範本將這些設定備份到特殊裝置名稱目錄中的 [設定] 儲存位置。</span><span class="sxs-lookup"><span data-stu-id="09685-140">Templates in the Backup Profile back up these settings to the Settings Storage Location in a special Device name directory.</span></span> <span data-ttu-id="09685-141">指定的設定會備份到此位置。</span><span class="sxs-lookup"><span data-stu-id="09685-141">Specified settings are backed up to this location.</span></span>

<span data-ttu-id="09685-142">指定 BackupOnly 的範本包含該裝置專用的設定，除非明確還原，否則不應進行同步處理。</span><span class="sxs-lookup"><span data-stu-id="09685-142">Templates designated BackupOnly include settings specific to that device that should not be synchronized unless explicitly restored.</span></span> <span data-ttu-id="09685-143">這些設定會儲存在設定儲存位置上與 [Backedup 設定] 中相同的裝置特定設定套件位置。</span><span class="sxs-lookup"><span data-stu-id="09685-143">These settings are stored in the same device-specific settings package location on the settings storage location as the Backedup Settings.</span></span> <span data-ttu-id="09685-144">這些範本有一個特殊的識別碼內嵌在範本中，指定它們應該是此設定檔的一部分。</span><span class="sxs-lookup"><span data-stu-id="09685-144">These templates have a special identifier embedded in the template that specifies they should be part of this profile.</span></span>

**<span data-ttu-id="09685-145">[設定] 儲存位置範本中的 [設定套件] 位置</span><span class="sxs-lookup"><span data-stu-id="09685-145">Settings packages location within the Settings Storage Location template</span></span>**

<span data-ttu-id="09685-146">漫遊設定檔設定會儲存在設定儲存位置。</span><span class="sxs-lookup"><span data-stu-id="09685-146">Roaming Profile settings are stored on the settings storage location.</span></span> <span data-ttu-id="09685-147">指派給備份或 BackupOnly 設定檔的範本會將其設定儲存到特殊裝置名稱目錄中的 [設定] 儲存位置。</span><span class="sxs-lookup"><span data-stu-id="09685-147">Templates assigned to the Backup or the BackupOnly profile store their settings to the Settings Storage Location in a special Device name directory.</span></span> <span data-ttu-id="09685-148">每個裝置都有在這些設定檔中擁有範本，都有自己的裝置名稱。</span><span class="sxs-lookup"><span data-stu-id="09685-148">Each device with templates in these profiles has its own device name.</span></span> <span data-ttu-id="09685-149">UE-V 不會清除這些目錄。</span><span class="sxs-lookup"><span data-stu-id="09685-149">UE-V does not clean up these directories.</span></span>

**<span data-ttu-id="09685-150">備份觸發程式</span><span class="sxs-lookup"><span data-stu-id="09685-150">Backup trigger</span></span>**

<span data-ttu-id="09685-151">備份是由觸發 UE-V 同步處理的相同事件觸發。</span><span class="sxs-lookup"><span data-stu-id="09685-151">Backup is triggered by the same events that trigger a UE-V synchronization.</span></span>

**<span data-ttu-id="09685-152">如何還原設定</span><span class="sxs-lookup"><span data-stu-id="09685-152">How settings are restored</span></span>**

<span data-ttu-id="09685-153">還原使用者的裝置會將目前已註冊範本的設定從另一個裝置的 [備份] 資料夾及所有已同步處理的設定還原至目前的電腦。</span><span class="sxs-lookup"><span data-stu-id="09685-153">Restoring a user’s device restores the currently registered Template’s settings from another device’s backup folder and all synchronized settings to the current machine.</span></span> <span data-ttu-id="09685-154">您可以透過以下兩種方式還原設定：</span><span class="sxs-lookup"><span data-stu-id="09685-154">Settings are restored in these two ways:</span></span>

-   **<span data-ttu-id="09685-155">自動還原</span><span class="sxs-lookup"><span data-stu-id="09685-155">Automatic restore</span></span>**

    <span data-ttu-id="09685-156">如果使用者的 UE-V 設定 [儲存路徑]、[網域] 和 [電腦名稱稱] 與目前使用者相符，就表示該使用者的所有設定都已同步處理，只會套用最新設定。</span><span class="sxs-lookup"><span data-stu-id="09685-156">If the user’s UE-V settings storage path, domain, and Computer name match the current user then all of the settings for that user are synchronized, with only the latest settings applied.</span></span> <span data-ttu-id="09685-157">如果使用者第一次登入新的裝置，且符合這些準則，設定資料就會套用到該裝置。</span><span class="sxs-lookup"><span data-stu-id="09685-157">If a user logs on to a new device for the first time and these criteria are met, the settings data is applied to that device.</span></span>

    **<span data-ttu-id="09685-158">注意</span><span class="sxs-lookup"><span data-stu-id="09685-158">Note</span></span>**  
    <span data-ttu-id="09685-159">[協助工具] 和 [Windows 桌面設定] 需要使用者重新登入 Windows 才能套用。</span><span class="sxs-lookup"><span data-stu-id="09685-159">Accessibility and Windows Desktop settings require the user to re-logon to Windows to be applied.</span></span>



-   **<span data-ttu-id="09685-160">手動還原</span><span class="sxs-lookup"><span data-stu-id="09685-160">Manual Restore</span></span>**

    <span data-ttu-id="09685-161">如果您想要在更新期間透過還原裝置來協助使用者，您可以選擇使用 UevBackup Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="09685-161">If you want to assist users by restoring a device during a refresh, you can choose to use the Restore-UevBackup cmdlet.</span></span> <span data-ttu-id="09685-162">這個命令會從 [設定] 儲存位置下載使用者的設定。</span><span class="sxs-lookup"><span data-stu-id="09685-162">This command causes the user’s settings to be downloaded from the Settings Storage Location.</span></span>

## <span data-ttu-id="09685-163">將應用程式和 Windows 設定還原成原始狀態</span><span class="sxs-lookup"><span data-stu-id="09685-163">Restore Application and Windows Settings to Original State</span></span>


<span data-ttu-id="09685-164">在安裝 UE-V Agent 之後，當應用程式第一次啟動時，WMI 和 Windows PowerShell 命令可讓您將應用程式和 Windows 設定還原至電腦上的設定值。</span><span class="sxs-lookup"><span data-stu-id="09685-164">WMI and Windows PowerShell commands let you restore application and Windows settings to the settings values that were on the computer the first time that the application started after the UE-V Agent was installed.</span></span> <span data-ttu-id="09685-165">此還原動作是在每個應用程式或 Windows 設定基礎上執行。</span><span class="sxs-lookup"><span data-stu-id="09685-165">This restoring action is performed on a per-application or Windows settings basis.</span></span> <span data-ttu-id="09685-166">這些設定會在應用程式下次執行時還原，或在使用者登入作業系統時還原設定。</span><span class="sxs-lookup"><span data-stu-id="09685-166">The settings are restored the next time that the application runs, or the settings are restored when the user logs on to the operating system.</span></span>

**<span data-ttu-id="09685-167">若要使用 Windows PowerShell （即 UE-V 2）還原應用程式設定和 Windows 設定。</span><span class="sxs-lookup"><span data-stu-id="09685-167">To restore application settings and Windows settings with Windows PowerShell for UE-V 2.x</span></span>**

1.  <span data-ttu-id="09685-168">開啟 [Windows PowerShell] 視窗。</span><span class="sxs-lookup"><span data-stu-id="09685-168">Open the Windows PowerShell window.</span></span>

2.  <span data-ttu-id="09685-169">輸入下列 Windows PowerShell Cmdlet 來還原應用程式設定和 Windows 設定。</span><span class="sxs-lookup"><span data-stu-id="09685-169">Enter the following Windows PowerShell cmdlet to restore the application settings and Windows settings.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong><span data-ttu-id="09685-170">Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="09685-170">Windows PowerShell cmdlet</span></span></strong></th>
    <th align="left"><strong><span data-ttu-id="09685-171">描述</span><span class="sxs-lookup"><span data-stu-id="09685-171">Description</span></span></strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><code>Restore-UevUserSetting -&lt;TemplateID&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="09685-172">還原應用程式的使用者設定或還原一組 Windows 設定。</span><span class="sxs-lookup"><span data-stu-id="09685-172">Restores the user settings for an application or restores a group of Windows settings.</span></span></p></td>
    </tr>
    </tbody>
    </table>



**<span data-ttu-id="09685-173">使用 WMI 來還原應用程式設定和 Windows 設定</span><span class="sxs-lookup"><span data-stu-id="09685-173">To restore application settings and Windows settings with WMI</span></span>**

1.  <span data-ttu-id="09685-174">開啟 Windows PowerShell 視窗。</span><span class="sxs-lookup"><span data-stu-id="09685-174">Open a Windows PowerShell window.</span></span>

2.  <span data-ttu-id="09685-175">輸入下列 WMI 命令來還原應用程式設定和 Windows 設定。</span><span class="sxs-lookup"><span data-stu-id="09685-175">Enter the following WMI command to restore application settings and Windows settings.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong><span data-ttu-id="09685-176">WMI 命令</span><span class="sxs-lookup"><span data-stu-id="09685-176">WMI command</span></span></strong></th>
    <th align="left"><strong><span data-ttu-id="09685-177">描述</span><span class="sxs-lookup"><span data-stu-id="09685-177">Description</span></span></strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class UserSettings -Name RestoreByTemplateId -ArgumentList &lt;template_ID&gt;</code></p></td>
    <td align="left"><p><span data-ttu-id="09685-178">還原應用程式的使用者設定或還原一組 Windows 設定。</span><span class="sxs-lookup"><span data-stu-id="09685-178">Restores the user settings for an application or restores a group of Windows settings.</span></span></p></td>
    </tr>
    </tbody>
    </table>



~~~
**Note**  
UE-V does not provide a settings rollback for Windows apps.
~~~








## <span data-ttu-id="09685-179">相關主題</span><span class="sxs-lookup"><span data-stu-id="09685-179">Related topics</span></span>


[<span data-ttu-id="09685-180">使用 Windows PowerShell 和 WMI 管理 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="09685-180">Administering UE-V 2.x with Windows PowerShell and WMI</span></span>](administering-ue-v-2x-with-windows-powershell-and-wmi-both-uevv2.md)

[<span data-ttu-id="09685-181">管理 UE-V 2。</span><span class="sxs-lookup"><span data-stu-id="09685-181">Administering UE-V 2.x</span></span>](administering-ue-v-2x-new-uevv2.md)









