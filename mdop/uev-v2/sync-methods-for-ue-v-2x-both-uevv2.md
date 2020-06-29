---
title: UE-V 2.x 的同步方法
description: UE-V 2.x 的同步方法
author: dansimp
ms.assetid: af0ae894-dfdc-41d2-927b-c2ab1b355ffe
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a163442e2ab3dbd777aca133b13b0086cdb8ae1a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810040"
---
# <span data-ttu-id="ef3df-103">UE-V 2.x 的同步方法</span><span class="sxs-lookup"><span data-stu-id="ef3df-103">Sync Methods for UE-V 2.x</span></span>


<span data-ttu-id="ef3df-104">Microsoft 使用者體驗虛擬化（UE-V）2.0、2.1 和 2.1 SP1 代理程式可讓您使用設定儲存位置來同步處理使用者的應用程式和 Windows 設定。</span><span class="sxs-lookup"><span data-stu-id="ef3df-104">The Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, and 2.1 SP1 Agent lets you synchronize users’ application and Windows settings with the settings storage location.</span></span> <span data-ttu-id="ef3df-105">*同步方法*設定會定義 ue-v agent 將這些設定傳到設定儲存位置，以及將這些設定下載到這些設定的方式。</span><span class="sxs-lookup"><span data-stu-id="ef3df-105">The *Sync Method* configuration defines how the UE-V Agent uploads and downloads those settings to the settings storage location.</span></span> <span data-ttu-id="ef3df-106">UE-V 2. x 引進了稱為*SyncProvider*的新 SyncMethod。</span><span class="sxs-lookup"><span data-stu-id="ef3df-106">UE-V 2.x introduces a new SyncMethod called the *SyncProvider*.</span></span> <span data-ttu-id="ef3df-107">如需觸發應用程式和 Windows 設定同步處理之觸發事件的詳細資訊，請參閱為[ue-v 2-D 同步處理觸發程式事件（x](sync-trigger-events-for-ue-v-2x-both-uevv2.md)）。</span><span class="sxs-lookup"><span data-stu-id="ef3df-107">For more information about trigger events that start the synchronization of application and Windows settings, see [Sync Trigger Events for UE-V 2.x](sync-trigger-events-for-ue-v-2x-both-uevv2.md).</span></span>

## <span data-ttu-id="ef3df-108">SyncMethod 設定</span><span class="sxs-lookup"><span data-stu-id="ef3df-108">SyncMethod Configuration</span></span>


<span data-ttu-id="ef3df-109">下表說明將 SyncMethod 從 UE-V v 1.0 變更為 v-v，以及每個設定的設定：</span><span class="sxs-lookup"><span data-stu-id="ef3df-109">This table explains the changes to SyncMethod from UE-V v1.0 to v2.0 to v2.1, as well as the settings for each configuration:</span></span>

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="ef3df-110">SyncMethod 設定</span><span class="sxs-lookup"><span data-stu-id="ef3df-110">SyncMethod Configuration</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="ef3df-111">V 1。0</span><span class="sxs-lookup"><span data-stu-id="ef3df-111">V1.0</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="ef3df-112">V 2。0</span><span class="sxs-lookup"><span data-stu-id="ef3df-112">V2.0</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="ef3df-113">V 2.1 和 V 2.1 SP1</span><span class="sxs-lookup"><span data-stu-id="ef3df-113">V2.1 and V2.1 SP1</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="ef3df-114">描述</span><span class="sxs-lookup"><span data-stu-id="ef3df-114">Description</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ef3df-115">SyncProvider</span><span class="sxs-lookup"><span data-stu-id="ef3df-115">SyncProvider</span></span></p></td>
<td align="left"><p><span data-ttu-id="ef3df-116">不適用</span><span class="sxs-lookup"><span data-stu-id="ef3df-116">n/a</span></span></p></td>
<td align="left"><p><span data-ttu-id="ef3df-117">預設值</span><span class="sxs-lookup"><span data-stu-id="ef3df-117">Default</span></span></p></td>
<td align="left"><p><span data-ttu-id="ef3df-118">預設值</span><span class="sxs-lookup"><span data-stu-id="ef3df-118">Default</span></span></p></td>
<td align="left"><p><span data-ttu-id="ef3df-119">特定應用程式或全域 Windows 桌面設定的設定變更會儲存在本機的快取資料夾中。</span><span class="sxs-lookup"><span data-stu-id="ef3df-119">Settings changes for a specific application or for global Windows desktop settings are saved locally to a cache folder.</span></span> <span data-ttu-id="ef3df-120">當同步處理觸發事件發生時，這些變更會與 [設定] 儲存位置進行同步處理。</span><span class="sxs-lookup"><span data-stu-id="ef3df-120">These changes are then synchronized with the settings storage location when a synchronization trigger event takes place.</span></span> <span data-ttu-id="ef3df-121">推送變更會將本機變更儲存至 [設定] 儲存路徑。</span><span class="sxs-lookup"><span data-stu-id="ef3df-121">Pushing out changes will save the local changes to the settings storage path.</span></span></p>
<p><span data-ttu-id="ef3df-122">此預設設定為電腦的黃金標準。</span><span class="sxs-lookup"><span data-stu-id="ef3df-122">This default setting is the gold standard for computers.</span></span> <span data-ttu-id="ef3df-123">這個選項會嘗試在短暫的延遲之後同步處理設定和超時，以確保應用程式或作業系統啟動不會在長時間內延遲。</span><span class="sxs-lookup"><span data-stu-id="ef3df-123">This option attempts to synchronize the setting and times out after a short delay to ensure that the application or operating system startup isn’t delayed for a long period of time.</span></span></p>
<p><span data-ttu-id="ef3df-124">此功能也會與 [排程的任務–同步處理控制器] 應用程式相關聯。</span><span class="sxs-lookup"><span data-stu-id="ef3df-124">This functionality is also tied to the Scheduled task – Sync Controller Application.</span></span> <span data-ttu-id="ef3df-125">系統管理員控制排程任務的頻率。</span><span class="sxs-lookup"><span data-stu-id="ef3df-125">The administrator controls the frequency of the Scheduled task.</span></span> <span data-ttu-id="ef3df-126">根據預設，電腦在登入後每30分鐘都會同步處理其設定。</span><span class="sxs-lookup"><span data-stu-id="ef3df-126">By default, computers synchronize their settings every 30 min after logging on.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ef3df-127">OfflineFiles</span><span class="sxs-lookup"><span data-stu-id="ef3df-127">OfflineFiles</span></span></p></td>
<td align="left"><p><span data-ttu-id="ef3df-128">預設值</span><span class="sxs-lookup"><span data-stu-id="ef3df-128">Default</span></span></p></td>
<td align="left"><p><span data-ttu-id="ef3df-129">已取代。</span><span class="sxs-lookup"><span data-stu-id="ef3df-129">Deprecated</span></span></p></td>
<td align="left"><p><span data-ttu-id="ef3df-130">已取代。</span><span class="sxs-lookup"><span data-stu-id="ef3df-130">Deprecated</span></span></p></td>
<td align="left"><p><span data-ttu-id="ef3df-131">在 V 2.0 中的行為與 SyncProvider 相同。</span><span class="sxs-lookup"><span data-stu-id="ef3df-131">Behaves the same as SyncProvider in V2.0.</span></span></p>
<p><span data-ttu-id="ef3df-132">如果啟用離線檔案並釘選資料夾，則 UE-V 會將此資料夾解除固定，並直接與中央 SMB 目錄同步處理。</span><span class="sxs-lookup"><span data-stu-id="ef3df-132">If Offline files are enabled and the folder is pinned then UE-V will unpin this folder and sync directly to the central SMB directory.</span></span></p>
<p><strong><span data-ttu-id="ef3df-133">注意： </strong> 在 V 1.0 中，如果您想要使用公司的斷開連接方式（亦即在膝上型電腦上傳送）來使用 ue-v，則指導方針是使用離線檔案來確保您的設定是漫遊。</span><span class="sxs-lookup"><span data-stu-id="ef3df-133">NOTE:</strong> In V1.0 if you wanted to use UE-V in a CorpNet disconnected manner (aka traveling with a Laptop), then the guidance is to use Offline Files to ensure that your settings roamed.</span></span><span data-ttu-id="ef3df-134">我們收到了足夠的客戶意見反應，讓您開啟 [離線檔案] 是不重要的企業封鎖。</span><span class="sxs-lookup"><span data-stu-id="ef3df-134"> We received sufficient customer feedback that turning on Offline files is a non-trivial enterprise blocker.</span></span> <span data-ttu-id="ef3df-135">所以在 UE-V 2 中，我們建立了一個緊密結合的同步引擎，以在本機緩存您的資料，並將設定同步處理到中央伺服器。</span><span class="sxs-lookup"><span data-stu-id="ef3df-135">So in UE-V 2, we created a tightly coupled synchronization engine to cache your data locally and synchronize the settings to the central server.</span></span> <span data-ttu-id="ef3df-136">此功能區域不會取代離線檔案或資料夾重新導向。</span><span class="sxs-lookup"><span data-stu-id="ef3df-136">This feature area does not replace Offline Files or Folder Redirection.</span></span></p>
<p><span data-ttu-id="ef3df-137">UE-V 2 在離線資料夾中無法正常運作，因此本指南不會將設定儲存路徑設定為釘選的 [已固定的離線] 或 [CSC] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="ef3df-137">UE-V 2 does not work well with Offline folders so the guidance is not to set the settings storage path to a pinned Offline or CSC folder.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ef3df-138">External</span><span class="sxs-lookup"><span data-stu-id="ef3df-138">External</span></span></p></td>
<td align="left"><p><span data-ttu-id="ef3df-139">不適用</span><span class="sxs-lookup"><span data-stu-id="ef3df-139">n/a</span></span></p></td>
<td align="left"><p><span data-ttu-id="ef3df-140">不適用</span><span class="sxs-lookup"><span data-stu-id="ef3df-140">n/a</span></span></p></td>
<td align="left"><p><span data-ttu-id="ef3df-141">支援</span><span class="sxs-lookup"><span data-stu-id="ef3df-141">Supported</span></span></p></td>
<td align="left"><p><span data-ttu-id="ef3df-142">UE-V 2.1 中的新功能，此設定方法會指定，如果 UE-V 設定是寫入使用者電腦上的本機資料夾，則任何外部同步處理引擎（例如商務用 OneDrive、工作資料夾、Sharepoint 或 Dropbox）都可以用來將這些設定套用到使用者存取的不同電腦上。</span><span class="sxs-lookup"><span data-stu-id="ef3df-142">New in UE-V 2.1, this configuration method specifies that if UE-V settings are written to a local folder on the user computer, then any external sync engine (such as OneDrive for Business, Work Folders, Sharepoint, or Dropbox) can be used to apply these settings to the different computers that users access.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ef3df-143">無</span><span class="sxs-lookup"><span data-stu-id="ef3df-143">None</span></span></p></td>
<td align="left"><p><span data-ttu-id="ef3df-144">是</span><span class="sxs-lookup"><span data-stu-id="ef3df-144">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="ef3df-145">是</span><span class="sxs-lookup"><span data-stu-id="ef3df-145">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="ef3df-146">是</span><span class="sxs-lookup"><span data-stu-id="ef3df-146">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="ef3df-147">此設定設定是針對虛擬桌面基礎結構（VDI）及流程式應用程式體驗而設計。</span><span class="sxs-lookup"><span data-stu-id="ef3df-147">This configuration setting is designed for the Virtual Desktop Infrastructure (VDI) and Streamed Application experience primarily.</span></span> <span data-ttu-id="ef3df-148">此設定應該用於資料中心中使用的 Windows Server 方塊，其中的連線將一直是可用的。</span><span class="sxs-lookup"><span data-stu-id="ef3df-148">This setting should be used on Windows Server boxes used in a datacenter, where the connection will always be available.</span></span></p>
<p><span data-ttu-id="ef3df-149">任何設定變更都會直接儲存到伺服器。</span><span class="sxs-lookup"><span data-stu-id="ef3df-149">Any settings changes are saved directly to the server.</span></span> <span data-ttu-id="ef3df-150">如果無法使用 [設定] 儲存路徑的網路連線，則會將設定變更放在裝置上，並在下次同步處理提供程式執行時進行同步處理。</span><span class="sxs-lookup"><span data-stu-id="ef3df-150">If the network connection to the settings storage path is not available, then the settings changes are cached on the device and are synchronized the next time that the Sync Provider runs.</span></span> <span data-ttu-id="ef3df-151">如果找不到設定儲存路徑，且在登出時從彙集的 VDI 環境中移除使用者設定檔，這些設定變更會遺失，而且使用者必須重新套用變更，才能讓電腦再次達到設定儲存路徑。</span><span class="sxs-lookup"><span data-stu-id="ef3df-151">If the settings storage path is not found and the user profile is removed from a pooled VDI environment on logoff, then these settings changes are lost, and the user must reapply the change when the computer can again reach the settings storage path.</span></span></p>
<p><span data-ttu-id="ef3df-152">App 與 OS 會無限期地等待存在該位置。</span><span class="sxs-lookup"><span data-stu-id="ef3df-152">Apps and OS will wait indefinitely for the location to be present.</span></span> <span data-ttu-id="ef3df-153">如果找不到該位置，這可能會導致 App 載入或 OS 登入時間大幅增加。</span><span class="sxs-lookup"><span data-stu-id="ef3df-153">This could cause App load or OS logon time to dramatically increase if the location is not found.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="ef3df-154">您可以透過下列方式設定同步處理方法：</span><span class="sxs-lookup"><span data-stu-id="ef3df-154">You can configure the sync method in these ways:</span></span>

-   <span data-ttu-id="ef3df-155">當您透過命令列參數或在批次腳本中[部署 Ue-v Agent](https://technet.microsoft.com/library/dn458891.aspx#agent)時</span><span class="sxs-lookup"><span data-stu-id="ef3df-155">When you [Deploy the UE-V Agent](https://technet.microsoft.com/library/dn458891.aspx#agent) through a command-line parameter or in a batch script</span></span>

-   <span data-ttu-id="ef3df-156">透過[群組原則](https://technet.microsoft.com/library/dn458893.aspx)設定</span><span class="sxs-lookup"><span data-stu-id="ef3df-156">Through [Group Policy](https://technet.microsoft.com/library/dn458893.aspx) settings</span></span>

-   <span data-ttu-id="ef3df-157">使用[System Center Configuration Pack](https://technet.microsoft.com/library/dn458917.aspx)進行 ue-v</span><span class="sxs-lookup"><span data-stu-id="ef3df-157">With the [System Center Configuration Pack](https://technet.microsoft.com/library/dn458917.aspx) for UE-V</span></span>

-   <span data-ttu-id="ef3df-158">使用[Windows PowerShell 或 Windows 管理工具（WMI）](https://technet.microsoft.com/library/dn458937.aspx)安裝 ue-v Agent 之後</span><span class="sxs-lookup"><span data-stu-id="ef3df-158">After installation of the UE-V Agent, by using [Windows PowerShell or Windows Management Instrumentation (WMI)](https://technet.microsoft.com/library/dn458937.aspx)</span></span>






## <span data-ttu-id="ef3df-159">相關主題</span><span class="sxs-lookup"><span data-stu-id="ef3df-159">Related topics</span></span>


[<span data-ttu-id="ef3df-160">部署 UE-V 2.x 的必要功能</span><span class="sxs-lookup"><span data-stu-id="ef3df-160">Deploy Required Features for UE-V 2.x</span></span>](deploy-required-features-for-ue-v-2x-new-uevv2.md#ssl)

[<span data-ttu-id="ef3df-161">部署 UE-V 2.x 的必要功能</span><span class="sxs-lookup"><span data-stu-id="ef3df-161">Deploy Required Features for UE-V 2.x</span></span>](deploy-required-features-for-ue-v-2x-new-uevv2.md#config)

[<span data-ttu-id="ef3df-162">UE-V 2.x 技術參考</span><span class="sxs-lookup"><span data-stu-id="ef3df-162">Technical Reference for UE-V 2.x</span></span>](technical-reference-for-ue-v-2x-both-uevv2.md)

 

 





