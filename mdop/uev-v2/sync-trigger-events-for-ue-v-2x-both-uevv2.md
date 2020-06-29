---
title: UE-V 2.x 的同步觸發程序事件
description: UE-V 2.x 的同步觸發程序事件
author: dansimp
ms.assetid: 4ed71a13-6a4f-4376-996f-74b126536bbc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f3e89a0370790e7f462b2f469792128dba033460
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811972"
---
# <span data-ttu-id="ccdf8-103">UE-V 2.x 的同步觸發程序事件</span><span class="sxs-lookup"><span data-stu-id="ccdf8-103">Sync Trigger Events for UE-V 2.x</span></span>


<span data-ttu-id="ccdf8-104">Microsoft 使用者體驗虛擬化（UE-V）2.0、2.1 和 2.1 SP1 可讓您在所有網域加入的裝置上同步處理您的應用程式和 Windows 設定。</span><span class="sxs-lookup"><span data-stu-id="ccdf8-104">Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, and 2.1 SP1 lets you synchronize your application and Windows settings across all your domain-joined devices.</span></span> <span data-ttu-id="ccdf8-105">*同步處理觸發事件*可定義 ue-v agent 何時將這些設定與設定儲存位置進行同步處理。</span><span class="sxs-lookup"><span data-stu-id="ccdf8-105">*Sync trigger events* define when the UE-V Agent synchronizes those settings with the settings storage location.</span></span> <span data-ttu-id="ccdf8-106">UE-V 2 引入了稱為*SyncProvider*的新*同步處理方法*。</span><span class="sxs-lookup"><span data-stu-id="ccdf8-106">UE-V 2 introduces a new *Sync Method* called the *SyncProvider*.</span></span> <span data-ttu-id="ccdf8-107">如需同步處理方法設定的詳細資訊，請參閱[ue-v 2. x 的同步處理方法](sync-methods-for-ue-v-2x-both-uevv2.md)。</span><span class="sxs-lookup"><span data-stu-id="ccdf8-107">For more information about Sync Method configuration, see [Sync Methods for UE-V 2.x](sync-methods-for-ue-v-2x-both-uevv2.md).</span></span>

## <span data-ttu-id="ccdf8-108">UE-V 2 同步觸發事件</span><span class="sxs-lookup"><span data-stu-id="ccdf8-108">UE-V 2 Sync Trigger Events</span></span>


<span data-ttu-id="ccdf8-109">下表說明適用于傳統型應用程式和 Windows 設定的觸發事件。</span><span class="sxs-lookup"><span data-stu-id="ccdf8-109">The following table explains the trigger events for classic applications and Windows settings.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="ccdf8-110">UE-V 2 觸發事件</span><span class="sxs-lookup"><span data-stu-id="ccdf8-110">UE-V 2 Trigger Event</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="ccdf8-111">SyncMethod = SyncProvider</span><span class="sxs-lookup"><span data-stu-id="ccdf8-111">SyncMethod=SyncProvider</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="ccdf8-112">SyncMethod = None</span><span class="sxs-lookup"><span data-stu-id="ccdf8-112">SyncMethod=None</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="ccdf8-113">Windows 登入</span><span class="sxs-lookup"><span data-stu-id="ccdf8-113">Windows Logon</span></span></strong></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="ccdf8-114">您可以從 [設定] 儲存位置將應用程式和 Windows 設定匯入到本機快取。</span><span class="sxs-lookup"><span data-stu-id="ccdf8-114">Application and Windows settings are imported to the local cache from the settings storage location.</span></span></p></li>
<li><p><a href="https://technet.microsoft.com/library/dn458932.aspx#autosyncsettings2" data-raw-source="[Asynchronous Windows settings](https://technet.microsoft.com/library/dn458932.aspx#autosyncsettings2)"><span data-ttu-id="ccdf8-115">已套用非同步 Windows 設定 </a> 。</span><span class="sxs-lookup"><span data-stu-id="ccdf8-115">Asynchronous Windows settings</a> are applied.</span></span></p></li>
<li><p><span data-ttu-id="ccdf8-116">系統會在下一個 Windows 登入期間套用同步 Windows 設定。</span><span class="sxs-lookup"><span data-stu-id="ccdf8-116">Synchronous Windows settings will be applied during the next Windows logon.</span></span></p></li>
<li><p><span data-ttu-id="ccdf8-117">應用程式會在應用程式啟動時套用設定。</span><span class="sxs-lookup"><span data-stu-id="ccdf8-117">Application settings will be applied when the application starts.</span></span></p></li>
</ul></td>
<td align="left"><ul>
<li><p><span data-ttu-id="ccdf8-118">您可以直接從 [設定] 儲存位置讀取 [應用程式] 和 [Windows 設定]。</span><span class="sxs-lookup"><span data-stu-id="ccdf8-118">Application and Windows settings are read directly from the settings storage location.</span></span></p></li>
<li><p><span data-ttu-id="ccdf8-119">已套用非同步及同步 Windows 設定。</span><span class="sxs-lookup"><span data-stu-id="ccdf8-119">Asynchronous and synchronous Windows settings are applied.</span></span></p></li>
<li><p><span data-ttu-id="ccdf8-120">應用程式會在應用程式啟動時套用設定。</span><span class="sxs-lookup"><span data-stu-id="ccdf8-120">Application settings will be applied when the application starts.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="ccdf8-121">Windows 登出</span><span class="sxs-lookup"><span data-stu-id="ccdf8-121">Windows Logoff</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="ccdf8-122">將變更儲存在本機，並將非同步及同步 Windows 設定複製到 [設定儲存位置伺服器] （如果有的話）</span><span class="sxs-lookup"><span data-stu-id="ccdf8-122">Store changes locally and cache and copy asynchronous and synchronous Windows settings to the settings storage location server, if available</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccdf8-123">將變更儲存至非同步及同步 Windows 設定儲存位置</span><span class="sxs-lookup"><span data-stu-id="ccdf8-123">Store changes to asynchronous and synchronous Windows settings storage location</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="ccdf8-124">Windows Connect （RDP）/解除鎖定</span><span class="sxs-lookup"><span data-stu-id="ccdf8-124">Windows Connect (RDP) / Unlock</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="ccdf8-125">將任何非同步 Windows 設定從 [設定儲存位置] 同步處理到本機快取（如果有的話）。</span><span class="sxs-lookup"><span data-stu-id="ccdf8-125">Synchronize any asynchronous Windows settings from settings storage location to local cache, if available.</span></span></p>
<p><span data-ttu-id="ccdf8-126">套用快取的 Windows 設定</span><span class="sxs-lookup"><span data-stu-id="ccdf8-126">Apply cached Windows settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccdf8-127">從 [設定] 儲存位置下載並套用非同步 windows 設定</span><span class="sxs-lookup"><span data-stu-id="ccdf8-127">Download and apply asynchronous windows settings from settings storage location</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="ccdf8-128">Windows 中斷連線（RDP）/鎖</span><span class="sxs-lookup"><span data-stu-id="ccdf8-128">Windows Disconnect (RDP) / Lock</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="ccdf8-129">將非同步 Windows 設定變更儲存到本機快取。</span><span class="sxs-lookup"><span data-stu-id="ccdf8-129">Store asynchronous Windows settings changes to the local cache.</span></span></p>
<p><span data-ttu-id="ccdf8-130">將本機快取中的任何非同步 Windows 設定同步處理至 [設定] 儲存位置（如果有的話）</span><span class="sxs-lookup"><span data-stu-id="ccdf8-130">Synchronize any asynchronous Windows settings from the local cache to settings storage location, if available</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccdf8-131">將 [非同步 Windows 設定] 變更儲存至 [設定] 儲存位置</span><span class="sxs-lookup"><span data-stu-id="ccdf8-131">Store asynchronous Windows settings changes to the settings storage location</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="ccdf8-132">應用程式啟動</span><span class="sxs-lookup"><span data-stu-id="ccdf8-132">Application start</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="ccdf8-133">在應用程式啟動時從本機快取套用應用程式設定</span><span class="sxs-lookup"><span data-stu-id="ccdf8-133">Apply application settings from local cache as the application starts</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccdf8-134">應用程式啟動時從設定儲存位置套用應用程式設定</span><span class="sxs-lookup"><span data-stu-id="ccdf8-134">Apply application settings from settings storage location as the application starts</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="ccdf8-135">應用程式關閉</span><span class="sxs-lookup"><span data-stu-id="ccdf8-135">Application closes</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="ccdf8-136">將任何應用程式設定變更儲存至本機快取，並將設定複製到 [設定儲存位置] （如果有的話）</span><span class="sxs-lookup"><span data-stu-id="ccdf8-136">Store any application settings changes to the local cache and copy settings to settings storage location, if available</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccdf8-137">將任何應用程式設定變更儲存至 [設定儲存位置]</span><span class="sxs-lookup"><span data-stu-id="ccdf8-137">Store any application settings changes to settings storage location</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="ccdf8-138">已從公司設定中心執行同步處理控制器排程任務或「立即同步處理」</span><span class="sxs-lookup"><span data-stu-id="ccdf8-138">Sync Controller Scheduled Task or “Sync Now” is run from the Company Settings Center</span></span></strong></p>
<p></p></td>
<td align="left"><p><span data-ttu-id="ccdf8-139">應用程式和 Windows 設定會在設定儲存位置與本機快取之間同步處理。</span><span class="sxs-lookup"><span data-stu-id="ccdf8-139">Application and Windows settings are synchronized between the settings storage location and the local cache.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="ccdf8-140">注意</span><span class="sxs-lookup"><span data-stu-id="ccdf8-140">Note</span></span></strong><br/><p><span data-ttu-id="ccdf8-141">設定變更不會在本機進行緩衝，直到應用程式關閉為止。</span><span class="sxs-lookup"><span data-stu-id="ccdf8-141">Settings changes are not cached locally until an application closes.</span></span> <span data-ttu-id="ccdf8-142">這個觸發程式不會將變更匯出至目前執行的應用程式。</span><span class="sxs-lookup"><span data-stu-id="ccdf8-142">This trigger will not export changes made to a currently running application.</span></span></p>
<p><span data-ttu-id="ccdf8-143">在 Windows 設定中，這表示任何變更都不會在本機進行緩衝及匯出，直到下次鎖定（非同步）或登出（非同步與同步）為止。</span><span class="sxs-lookup"><span data-stu-id="ccdf8-143">For Windows settings, this means that any changes will not be cached locally and exported until the next Lock (Asynchronous) or Logoff (Asynchronous and Synchronous).</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="ccdf8-144">在這些情況下，會套用設定：</span><span class="sxs-lookup"><span data-stu-id="ccdf8-144">Settings are applied in these cases:</span></span></p>
<ul>
<li><p><span data-ttu-id="ccdf8-145">[非同步 Windows 設定] 是直接套用的。</span><span class="sxs-lookup"><span data-stu-id="ccdf8-145">Asynchronous Windows settings are applied directly.</span></span></p></li>
<li><p><span data-ttu-id="ccdf8-146">應用程式的設定會在應用程式啟動時套用。</span><span class="sxs-lookup"><span data-stu-id="ccdf8-146">Application settings are applied when the application starts.</span></span></p></li>
<li><p><span data-ttu-id="ccdf8-147">在下次 Windows 登入期間，會套用非同步與同步 Windows 設定。</span><span class="sxs-lookup"><span data-stu-id="ccdf8-147">Both asynchronous and synchronous Windows settings are applied during the next Windows logon.</span></span></p></li>
<li><p><span data-ttu-id="ccdf8-148">Windows 應用程式（AppX）設定會在下一次重新整理期間套用。</span><span class="sxs-lookup"><span data-stu-id="ccdf8-148">Windows app (AppX) settings are applied during the next refresh.</span></span> <span data-ttu-id="ccdf8-149"><a href="https://technet.microsoft.com/library/dn458944.aspx" data-raw-source="[Monitor Application Settings](https://technet.microsoft.com/library/dn458944.aspx)"> </a> 如需詳細資訊，請參閱監視應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="ccdf8-149">See <a href="https://technet.microsoft.com/library/dn458944.aspx" data-raw-source="[Monitor Application Settings](https://technet.microsoft.com/library/dn458944.aspx)">Monitor Application Settings</a> for more information.</span></span></p></li>
</ul></td>
<td align="left"><p><span data-ttu-id="ccdf8-150">NA</span><span class="sxs-lookup"><span data-stu-id="ccdf8-150">NA</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="ccdf8-151">在遠端存放區上更新的非同步設定 \*</span><span class="sxs-lookup"><span data-stu-id="ccdf8-151">Asynchronous Settings updated on remote store\*</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="ccdf8-152">從快取載入並套用新的非同步設定。</span><span class="sxs-lookup"><span data-stu-id="ccdf8-152">Load and apply new asynchronous settings from the cache.</span></span></p></td>
<td align="left"><p><span data-ttu-id="ccdf8-153">從中央伺服器載入及套用設定</span><span class="sxs-lookup"><span data-stu-id="ccdf8-153">Load and apply settings from central server</span></span></p></td>
</tr>
</tbody>
</table>








## <span data-ttu-id="ccdf8-154">相關主題</span><span class="sxs-lookup"><span data-stu-id="ccdf8-154">Related topics</span></span>


[<span data-ttu-id="ccdf8-155">UE-V 2.x 技術參考</span><span class="sxs-lookup"><span data-stu-id="ccdf8-155">Technical Reference for UE-V 2.x</span></span>](technical-reference-for-ue-v-2x-both-uevv2.md)

[<span data-ttu-id="ccdf8-156">變更 UE-V 2. x 排程任務的頻率</span><span class="sxs-lookup"><span data-stu-id="ccdf8-156">Changing the Frequency of UE-V 2.x Scheduled Tasks</span></span>](changing-the-frequency-of-ue-v-2x-scheduled-tasks-both-uevv2.md)

[<span data-ttu-id="ccdf8-157">選擇 UE-V 2 的配置方法。</span><span class="sxs-lookup"><span data-stu-id="ccdf8-157">Choose the Configuration Method for UE-V 2.x</span></span>](https://technet.microsoft.com/library/dn458891.aspx#config)









