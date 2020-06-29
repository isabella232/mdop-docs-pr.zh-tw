---
title: UE-V 2.1 的新功能
description: UE-V 2.1 的新功能
author: dansimp
ms.assetid: 7f385183-7d97-4602-b19a-baa710334ade
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7816fc8309a29347048172b2104750140c483587
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811649"
---
# <span data-ttu-id="4f7a6-103">UE-V 2.1 的新功能</span><span class="sxs-lookup"><span data-stu-id="4f7a6-103">What's New in UE-V 2.1</span></span>


<span data-ttu-id="4f7a6-104">使用者體驗虛擬化2.1 提供了與 UE-V 2.0 相比的這些新功能和功能。</span><span class="sxs-lookup"><span data-stu-id="4f7a6-104">User Experience Virtualization 2.1 provides these new features and functionality compared to UE-V 2.0.</span></span> <span data-ttu-id="4f7a6-105">[Microsoft 使用者體驗虛擬化（ue-v）2.1 版本資訊](microsoft-user-experience-virtualization--ue-v--21-release-notesuevv21.md)提供關於 ue-v 2.1 發行的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="4f7a6-105">The [Microsoft User Experience Virtualization (UE-V) 2.1 Release Notes](microsoft-user-experience-virtualization--ue-v--21-release-notesuevv21.md) provide more information about the UE-V 2.1 release.</span></span>

## <span data-ttu-id="4f7a6-106">Office 2013 設定位置範本</span><span class="sxs-lookup"><span data-stu-id="4f7a6-106">Office 2013 Settings Location Template</span></span>


<span data-ttu-id="4f7a6-107">UE-V 2.1 包含 Microsoft Office 2013 設定位置範本，改良了 Outlook 簽名支援。</span><span class="sxs-lookup"><span data-stu-id="4f7a6-107">UE-V 2.1 includes the Microsoft Office 2013 settings location template with improved Outlook signature support.</span></span> <span data-ttu-id="4f7a6-108">在 UE-V 2.1 中，簽名資料會在使用者裝置之間同步處理。</span><span class="sxs-lookup"><span data-stu-id="4f7a6-108">In UE-V 2.1, the signature data synchronizes between user devices.</span></span> <span data-ttu-id="4f7a6-109">我們已新增新、回復和轉寄電子郵件的預設簽名設定同步處理。</span><span class="sxs-lookup"><span data-stu-id="4f7a6-109">We’ve added synchronization of default signature settings for new, reply, and forwarded emails.</span></span> <span data-ttu-id="4f7a6-110">客戶不需要再選擇預設的簽名設定。</span><span class="sxs-lookup"><span data-stu-id="4f7a6-110">Customers no longer have to choose the default signature settings.</span></span>

<span data-ttu-id="4f7a6-111">**記事** 您必須為使用者要同步處理其 Outlook 簽名的任何裝置建立 Outlook 設定檔。</span><span class="sxs-lookup"><span data-stu-id="4f7a6-111">**Note** An Outlook profile must be created for any device on which a user wants to sync their Outlook signature.</span></span> <span data-ttu-id="4f7a6-112">如果尚未建立設定檔，使用者可以建立一個，然後重新開機該裝置上的 Outlook，以啟用簽名同步處理。</span><span class="sxs-lookup"><span data-stu-id="4f7a6-112">If the profile is not already created, the user can create one and then restart Outlook on that device to enable signature synchronization.</span></span>

 

<span data-ttu-id="4f7a6-113">先前的 UE-V 包含 Microsoft Office 2010 設定位置範本，這些範本是透過 UE-V Agent 自動分發及註冊。</span><span class="sxs-lookup"><span data-stu-id="4f7a6-113">Previously UE-V included Microsoft Office 2010 settings location templates that were automatically distributed and registered with the UE-V Agent.</span></span> <span data-ttu-id="4f7a6-114">UE-V 2.1 可與 Office 365 搭配使用，以判斷 office 2013 設定是否由 Office 365 所漫遊。</span><span class="sxs-lookup"><span data-stu-id="4f7a6-114">UE-V 2.1 works with Office 365 to determine whether Office 2013 settings are roamed by Office 365.</span></span> <span data-ttu-id="4f7a6-115">如果設定是由 Office 365 漫遊，就不會透過 UE-V 漫遊。</span><span class="sxs-lookup"><span data-stu-id="4f7a6-115">If settings are roamed by Office 365 they are not roamed by UE-V.</span></span> <span data-ttu-id="4f7a6-116">[Office 2013 的使用者和漫遊設定概覽](https://go.microsoft.com/fwlink/p/?LinkID=391220)提供詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="4f7a6-116">[Overview of user and roaming settings for Office 2013](https://go.microsoft.com/fwlink/p/?LinkID=391220) provides more information.</span></span>

<span data-ttu-id="4f7a6-117">若要使用 UE-V 2.1 啟用設定同步處理，請執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="4f7a6-117">To enable settings synchronization using UE-V 2.1, do one of the following:</span></span>

-   <span data-ttu-id="4f7a6-118">使用群組原則來停用 Office 365 同步處理</span><span class="sxs-lookup"><span data-stu-id="4f7a6-118">Use Group Policy to disable Office 365 synchronization</span></span>

-   <span data-ttu-id="4f7a6-119">在安裝 Office 2013 期間，請勿啟用 Office 365 同步處理體驗</span><span class="sxs-lookup"><span data-stu-id="4f7a6-119">Do not enable the Office 365 synchronization experience during Office 2013 installation</span></span>

<span data-ttu-id="4f7a6-120">UE-V 2.1 隨附[office 2013 和 office 2010 範本](https://technet.microsoft.com/library/dn458932.aspx#autosyncsettings)。</span><span class="sxs-lookup"><span data-stu-id="4f7a6-120">UE-V 2.1 ships [Office 2013 and Office 2010 templates](https://technet.microsoft.com/library/dn458932.aspx#autosyncsettings).</span></span> <span data-ttu-id="4f7a6-121">此版本會移除 Office 2007 範本。</span><span class="sxs-lookup"><span data-stu-id="4f7a6-121">This release removes the Office 2007 templates.</span></span> <span data-ttu-id="4f7a6-122">使用者仍然可以使用 UE-V 2.0 或較舊版本的 Office 2007 範本，但仍可在[此處](https://go.microsoft.com/fwlink/p/?LinkID=246589)取得 ue-v 範本庫的範本。</span><span class="sxs-lookup"><span data-stu-id="4f7a6-122">Users can still use Office 2007 templates from UE-V 2.0 or earlier and can still get the templates from the UE-V template gallery located [here](https://go.microsoft.com/fwlink/p/?LinkID=246589).</span></span>

## <span data-ttu-id="4f7a6-123">修正分散式檔案系統命名空間使用者</span><span class="sxs-lookup"><span data-stu-id="4f7a6-123">Fix for Distributed File System Namespace Users</span></span>


<span data-ttu-id="4f7a6-124">UE-V 已新增稱為 SyncProviderPingEnabled 的 UE-V 設定，以改善分散式檔案系統命名空間（DFSN）的支援。</span><span class="sxs-lookup"><span data-stu-id="4f7a6-124">UE-V has improved Distributed File System Namespace (DFSN) support by adding a UE-V configuration called SyncProviderPingEnabled.</span></span> <span data-ttu-id="4f7a6-125">使用 PowerShell 或 WMI 來停用此設定，可讓使用者停用 UE-V ping。</span><span class="sxs-lookup"><span data-stu-id="4f7a6-125">Disabling this configuration using PowerShell or WMI allows users to disable the UE-V ping.</span></span> <span data-ttu-id="4f7a6-126">在使用 DFSN 伺服器時，UE-V ping 會導致錯誤，因為這些伺服器不會回應 ping。</span><span class="sxs-lookup"><span data-stu-id="4f7a6-126">The UE-V ping causes an error when using DFSN servers because these servers do not respond to pings.</span></span> <span data-ttu-id="4f7a6-127">[非回應] 可防止 UE-V 同步處理設定。</span><span class="sxs-lookup"><span data-stu-id="4f7a6-127">The non-response prevents UE-V from synchronizing settings.</span></span> <span data-ttu-id="4f7a6-128">停用 UE-V ping 可讓 UE-V 同步處理正常運作。</span><span class="sxs-lookup"><span data-stu-id="4f7a6-128">Disabling the UE-V ping allows UE-V synchronization to work normally.</span></span>

<span data-ttu-id="4f7a6-129">若要停用 UE-V ping，請使用此 PowerShell Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="4f7a6-129">To disable UE-V ping, use this PowerShell cmdlet:</span></span>

``` syntax
Set-UevConfiguration -DisableSyncProviderPing
```

## <span data-ttu-id="4f7a6-130">針對認證進行同步處理</span><span class="sxs-lookup"><span data-stu-id="4f7a6-130">Synchronization for Credentials</span></span>


<span data-ttu-id="4f7a6-131">UE-V 2.1 可讓客戶同步處理儲存在 Windows 認證管理器中的認證與證書。</span><span class="sxs-lookup"><span data-stu-id="4f7a6-131">UE-V 2.1 gives customers the ability to synchronize credentials and certificates stored in the Windows Credential Manager.</span></span> <span data-ttu-id="4f7a6-132">此元件預設為停用。</span><span class="sxs-lookup"><span data-stu-id="4f7a6-132">This component is disabled by default.</span></span> <span data-ttu-id="4f7a6-133">啟用此元件可讓使用者保持其網域認證與憑證同步處理。使用者可以在裝置上一次登入，而這些認證將會在所有 UE-V 啟用的裝置上漫遊該使用者。</span><span class="sxs-lookup"><span data-stu-id="4f7a6-133">Enabling this component lets users keep their domain credentials and certificates in sync. Users can sign in one time on a device, and these credentials will roam for that user across all of their UE-V enabled devices.</span></span> <span data-ttu-id="4f7a6-134">[使用 ue-v 2.1 管理認證](https://technet.microsoft.com/library/dn458932.aspx#creds)提供詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="4f7a6-134">[Manage Credentials with UE-V 2.1](https://technet.microsoft.com/library/dn458932.aspx#creds) provides more information.</span></span>

<span data-ttu-id="4f7a6-135">**記事** 在 Windows 8 和更新版本中，認證管理員包含網頁認證。</span><span class="sxs-lookup"><span data-stu-id="4f7a6-135">**Note** In Windows 8 and later, Credential Manager contains web credentials.</span></span> <span data-ttu-id="4f7a6-136">這些認證不會在使用者的裝置之間同步處理。</span><span class="sxs-lookup"><span data-stu-id="4f7a6-136">These credentials are not synchronized between users’ devices.</span></span>

 

## <span data-ttu-id="4f7a6-137">UE-V 與 Microsoft 帳戶同步處理</span><span class="sxs-lookup"><span data-stu-id="4f7a6-137">UE-V and Microsoft Account Synchronization</span></span>


<span data-ttu-id="4f7a6-138">UE-V 會偵測到 [使用 OneDrive 同步處理設定] （也稱為 Microsoft 帳戶同步處理）是否已開啟。</span><span class="sxs-lookup"><span data-stu-id="4f7a6-138">UE-V detects if “Sync settings with OneDrive”, also known as Microsoft Account synchronization, is on.</span></span> <span data-ttu-id="4f7a6-139">如果未將 Microsoft 帳戶設定為同步處理設定，UE-V 會同步處理 Windows 應用程式、AppX 套件，以及裝置之間的 Windows 桌面設定。</span><span class="sxs-lookup"><span data-stu-id="4f7a6-139">If the Microsoft Account is not configured to synchronize settings, UE-V synchronizes Windows apps, AppX packages, and Windows desktop settings between devices.</span></span> <span data-ttu-id="4f7a6-140">這可讓使用者存取其 Microsoft Store app、音樂、圖片及其他支援 Microsoft 帳戶的應用程式，而不需要在企業防火牆以外進行同步處理。</span><span class="sxs-lookup"><span data-stu-id="4f7a6-140">This lets users access their Store apps, music, pictures and other Microsoft Account-enabled applications without syncing outside of the enterprise firewall.</span></span> <span data-ttu-id="4f7a6-141">UE-V 會檢查群組原則是否會停止同步處理設定與 OneDrive，或使用者是否在使用者控制項中停用**此電腦上**的 [同步處理您的設定]。</span><span class="sxs-lookup"><span data-stu-id="4f7a6-141">UE-V checks whether Group Policy will stop synchronizing settings with OneDrive or if the user disables **Sync your settings on this computer** in the user controls.</span></span>

## <span data-ttu-id="4f7a6-142">支援 SyncMethod 外部</span><span class="sxs-lookup"><span data-stu-id="4f7a6-142">Support for the SyncMethod External</span></span>


<span data-ttu-id="4f7a6-143">名為「**外部**」的新[SyncMethod](https://technet.microsoft.com/library/dn554321.aspx)設定會指定將 ue-v 設定寫入使用者電腦上的本機資料夾，而任何外部同步引擎（例如商務用 OneDrive、工作資料夾、Sharepoint 或 Dropbox）都可以用來將這些設定套用到使用者存取的不同電腦上。</span><span class="sxs-lookup"><span data-stu-id="4f7a6-143">A new [SyncMethod configuration](https://technet.microsoft.com/library/dn554321.aspx) called **External** specifies that if UE-V settings are written to a local folder on the user computer, then any external sync engine (such as OneDrive for Business, Work Folders, Sharepoint, or Dropbox) can be used to apply these settings to the different computers that users access.</span></span>

## <span data-ttu-id="4f7a6-144">VDI 模式的增強支援</span><span class="sxs-lookup"><span data-stu-id="4f7a6-144">Enhanced Support for VDI Mode</span></span>


<span data-ttu-id="4f7a6-145">UE-V 2.1 包含在最終使用者之間共用的[VDI 會話支援](https://technet.microsoft.com/library/dn458932.aspx#vdi)。</span><span class="sxs-lookup"><span data-stu-id="4f7a6-145">UE-V 2.1 includes [support for VDI sessions](https://technet.microsoft.com/library/dn458932.aspx#vdi) that are shared among end users.</span></span> <span data-ttu-id="4f7a6-146">作為系統管理員，您可以註冊和設定特殊的 VDI 範本，這可確保 UE-V 在非持續性的 VDI 會話中完整保留其所有功能。</span><span class="sxs-lookup"><span data-stu-id="4f7a6-146">As an administrator, you can register and configure a special VDI template, which ensures that UE-V keeps all of its functionality intact for non-persistent VDI sessions.</span></span>

<span data-ttu-id="4f7a6-147">**記事** 如果您沒有為非持久性 VDI 會話啟用 VDI 模式，則某些功能無法運作，例如備份/還原及 LKG。</span><span class="sxs-lookup"><span data-stu-id="4f7a6-147">**Note** If you do not enable VDI mode for non-persistent VDI sessions, certain features do not work, such as back-up/restore and LKG.</span></span>

 

## <span data-ttu-id="4f7a6-148">系統管理備份和還原</span><span class="sxs-lookup"><span data-stu-id="4f7a6-148">Administrative Backup and Restore</span></span>


<span data-ttu-id="4f7a6-149">您可以在使用 UevTemplateProfile PowerShell Cmdlet 的**備份**或**漫遊（預設）** 設定檔中，使用 [設定位置] 範本，在使用者採用新的裝置時，還原其他設定。</span><span class="sxs-lookup"><span data-stu-id="4f7a6-149">You can restore additional settings when a user adopts a new device by putting a settings location template in **backup** or **roam (default)** profile using the Set-UevTemplateProfile PowerShell cmdlet.</span></span> <span data-ttu-id="4f7a6-150">這可讓電腦設定與新電腦同步處理，以及使用者設定。</span><span class="sxs-lookup"><span data-stu-id="4f7a6-150">This lets computer settings sync to the new computer, in addition to user settings.</span></span> <span data-ttu-id="4f7a6-151">系統會針對該裝置備份指派給備份設定檔的範本，並針對每個裝置進行設定。</span><span class="sxs-lookup"><span data-stu-id="4f7a6-151">Templates assigned to the backup profile are backed up for that device and configured on a per-device basis.</span></span> <span data-ttu-id="4f7a6-152">[在 ue-v 2. x 中管理系統管理備份和還原](manage-administrative-backup-and-restore-in-ue-v-2x-new-topic-for-21.md)。</span><span class="sxs-lookup"><span data-stu-id="4f7a6-152">[Manage Administrative Backup and Restore in UE-V 2.x](manage-administrative-backup-and-restore-in-ue-v-2x-new-topic-for-21.md) provides more information.</span></span>

## <span data-ttu-id="4f7a6-153">其他 Windows 設定的同步處理</span><span class="sxs-lookup"><span data-stu-id="4f7a6-153">Synchronization for Additional Windows Settings</span></span>


<span data-ttu-id="4f7a6-154">UE-V 現在會同步處理觸控式鍵盤個人化設定、拼寫字典，並啟用應用程式切換以使用 [最近的 App] 和 [螢幕邊緣] 設定，在 Windows 8 和 Windows 8.1 裝置之間進行同步處理。</span><span class="sxs-lookup"><span data-stu-id="4f7a6-154">UE-V now synchronizes touch keyboard personalization, the spelling dictionary, and enables the App Switching for recent apps and screen edge settings to synchronize between Windows 8 and Windows 8.1 devices.</span></span>






## <span data-ttu-id="4f7a6-155">相關主題</span><span class="sxs-lookup"><span data-stu-id="4f7a6-155">Related topics</span></span>


[<span data-ttu-id="4f7a6-156">UE-V 2.x 入門</span><span class="sxs-lookup"><span data-stu-id="4f7a6-156">Get Started with UE-V 2.x</span></span>](get-started-with-ue-v-2x-new-uevv2.md)

[<span data-ttu-id="4f7a6-157">準備 UE-V a.x 部署</span><span class="sxs-lookup"><span data-stu-id="4f7a6-157">Prepare a UE-V 2.x Deployment</span></span>](prepare-a-ue-v-2x-deployment-new-uevv2.md)

[<span data-ttu-id="4f7a6-158">Microsoft User Experience Virtualization (UE-V) 2.1 版本資訊</span><span class="sxs-lookup"><span data-stu-id="4f7a6-158">Microsoft User Experience Virtualization (UE-V) 2.1 Release Notes</span></span>](microsoft-user-experience-virtualization--ue-v--21-release-notesuevv21.md)

 

 





