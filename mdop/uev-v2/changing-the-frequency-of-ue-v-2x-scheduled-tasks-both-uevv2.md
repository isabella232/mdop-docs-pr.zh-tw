---
title: 變更 UE-V 2. x 排程任務的頻率
description: 變更 UE-V 2. x 排程任務的頻率
author: dansimp
ms.assetid: ee486570-c6cf-4fd9-ba48-0059ba877c10
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 09/29/2016
ms.openlocfilehash: 1c1e3c091431dc56068dcd1fe0e849b0df1f6aa0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810550"
---
# <span data-ttu-id="6ffc2-103">變更 UE-V 2. x 排程任務的頻率</span><span class="sxs-lookup"><span data-stu-id="6ffc2-103">Changing the Frequency of UE-V 2.x Scheduled Tasks</span></span>


<span data-ttu-id="6ffc2-104">Microsoft 使用者體驗虛擬化（UE-V）2.0、2.1 或 2.1 SP1 代理安裝程式（AgentSetup.exe）會在 UE-V Agent 安裝期間建立下列排程的任務：</span><span class="sxs-lookup"><span data-stu-id="6ffc2-104">The Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, or 2.1 SP1 Agent installer, AgentSetup.exe, creates the following scheduled tasks during the UE-V Agent installation:</span></span>

-   **<span data-ttu-id="6ffc2-105">監視應用程式設定</span><span class="sxs-lookup"><span data-stu-id="6ffc2-105">Monitor Application Settings</span></span>**

-   **<span data-ttu-id="6ffc2-106">同步處理控制器應用程式</span><span class="sxs-lookup"><span data-stu-id="6ffc2-106">Sync Controller Application</span></span>**

-   **<span data-ttu-id="6ffc2-107">在登出時同步處理設定</span><span class="sxs-lookup"><span data-stu-id="6ffc2-107">Synchronize Settings at Logoff</span></span>**

-   **<span data-ttu-id="6ffc2-108">範本自動更新</span><span class="sxs-lookup"><span data-stu-id="6ffc2-108">Template Auto Update</span></span>**

-   **<span data-ttu-id="6ffc2-109">收集 CEIP 資料</span><span class="sxs-lookup"><span data-stu-id="6ffc2-109">Collect CEIP data</span></span>**

-   **<span data-ttu-id="6ffc2-110">上傳 CEIP 資料</span><span class="sxs-lookup"><span data-stu-id="6ffc2-110">Upload CEIP Data</span></span>**

<span data-ttu-id="6ffc2-111">**記事** 除收集 CEIP 資料以外，這些工作必須保持啟用，因為 UE-V 無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-111">**Note** With the exception of Collect CEIP Data, these tasks must remain enabled as UE-V cannot function without them.</span></span>

 

<span data-ttu-id="6ffc2-112">這些排程的任務無法使用 UE-V 工具進行設定。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-112">These scheduled tasks are not configurable with the UE-V tools.</span></span> <span data-ttu-id="6ffc2-113">如果系統管理員想要變更這些專案的排程任務，就可以建立使用 Schtasks.exe 命令列選項的腳本。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-113">Administrators who want to change the scheduled task for these items can create a script that uses the Schtasks.exe command-line options.</span></span>

<span data-ttu-id="6ffc2-114">如需 Schtasks.exe 的詳細資訊，請參閱[如何使用 Schtasks、exe 來排程 Windows Server 2003 中的任務](https://go.microsoft.com/fwlink/?LinkID=264854)。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-114">For more information about Schtasks.exe, see [How to use Schtasks,exe to Schedule Tasks in Windows Server 2003](https://go.microsoft.com/fwlink/?LinkID=264854).</span></span>

<span data-ttu-id="6ffc2-115">如需詳細資訊，請參閱</span><span class="sxs-lookup"><span data-stu-id="6ffc2-115">For more information about</span></span>

## <span data-ttu-id="6ffc2-116">UE-V 排程的任務</span><span class="sxs-lookup"><span data-stu-id="6ffc2-116">UE-V Scheduled Tasks</span></span>


<span data-ttu-id="6ffc2-117">下列排程的任務包含在 UE-V 2 中，並提供範例排程任務設定命令。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-117">The following scheduled tasks are included in UE-V 2 with sample scheduled task configuration commands.</span></span>

### <span data-ttu-id="6ffc2-118">收集 CEIP 資料</span><span class="sxs-lookup"><span data-stu-id="6ffc2-118">Collect CEIP Data</span></span>

<span data-ttu-id="6ffc2-119">如果您在安裝的使用者或系統管理員 choses 參與客戶經驗改進計畫（CEIP），UE-V 會收集資料，以協助改善未來版本中的產品。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-119">If upon installation the user or administrator choses to participate in the Customer Experience Improvement Program (CEIP), UE-V collects data to help improve the product in future releases.</span></span> <span data-ttu-id="6ffc2-120">只有在登入時，才會執行此排程的工作。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-120">This scheduled task only runs at logon.</span></span> <span data-ttu-id="6ffc2-121">[**收集 CEIP 資料**] 任務會執行 UevSqmSession.exe，該作業位於 ue-v agent 安裝目錄中。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-121">The **Collect CEIP Data** task runs the UevSqmSession.exe, which is located in the UE-V Agent installation directory.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6ffc2-122">任務名稱</span><span class="sxs-lookup"><span data-stu-id="6ffc2-122">Task name</span></span></th>
<th align="left"><span data-ttu-id="6ffc2-123">預設事件</span><span class="sxs-lookup"><span data-stu-id="6ffc2-123">Default event</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6ffc2-124">\Microsoft\UE-V\Collect CEIP 資料</span><span class="sxs-lookup"><span data-stu-id="6ffc2-124">\Microsoft\UE-V\Collect CEIP data</span></span></p></td>
<td align="left"><p><span data-ttu-id="6ffc2-125">標識</span><span class="sxs-lookup"><span data-stu-id="6ffc2-125">Logon</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="6ffc2-126">監視應用程式設定</span><span class="sxs-lookup"><span data-stu-id="6ffc2-126">Monitor Application Settings</span></span>

<span data-ttu-id="6ffc2-127">[**監視應用程式設定**] 工作是用來同步處理 Windows 應用程式的設定。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-127">The **Monitor Application Settings** task is used to synchronize settings for Windows apps.</span></span> <span data-ttu-id="6ffc2-128">它會在登入，但延遲為30秒，不會影響登入 detrimentally。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-128">It is run at logon but is delayed by 30 seconds to not affect the logon detrimentally.</span></span> <span data-ttu-id="6ffc2-129">[監視應用程式狀態] 任務會執行位於 UE-V Agent 安裝目錄中的 UevAppMonitor.exe 檔案。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-129">The Monitor Application Status task runs the UevAppMonitor.exe file, which is located in the UE-V Agent installation directory.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6ffc2-130">任務名稱</span><span class="sxs-lookup"><span data-stu-id="6ffc2-130">Task name</span></span></th>
<th align="left"><span data-ttu-id="6ffc2-131">預設事件</span><span class="sxs-lookup"><span data-stu-id="6ffc2-131">Default event</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6ffc2-132">\Microsoft\UE-V\Monitor 應用程式狀態</span><span class="sxs-lookup"><span data-stu-id="6ffc2-132">\Microsoft\UE-V\Monitor Application Status</span></span></p></td>
<td align="left"><p><span data-ttu-id="6ffc2-133">標識</span><span class="sxs-lookup"><span data-stu-id="6ffc2-133">Logon</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="6ffc2-134">同步處理控制器應用程式</span><span class="sxs-lookup"><span data-stu-id="6ffc2-134">Sync Controller Application</span></span>

<span data-ttu-id="6ffc2-135">**同步處理控制器應用程式**工作是用來啟動同步處理控制器，以便將電腦的設定同步處理到 [設定] 儲存位置。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-135">The **Sync Controller Application** task is used to start the Sync Controller to synchronize settings from the computer to the settings storage location.</span></span> <span data-ttu-id="6ffc2-136">根據預設，任務會每30分鐘執行一次。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-136">By default, the task runs every 30 minutes.</span></span> <span data-ttu-id="6ffc2-137">此時，本機設定會同步處理至 [設定] 儲存位置，而設定儲存位置上的更新設定會同步處理到電腦。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-137">At that time, local settings are synchronized to the settings storage location, and updated settings on the settings storage location are synchronized to the computer.</span></span> <span data-ttu-id="6ffc2-138">同步控制器應用程式會執行 Microsoft.Uev.SyncController.exe，該位於 UE-V Agent 安裝目錄中。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-138">The Sync Controller application runs the Microsoft.Uev.SyncController.exe, which is located in the UE-V Agent installation directory.</span></span>
<span data-ttu-id="6ffc2-139">**注意：** 根據 [**監視器應用程式設定**] 工作，此工作是在登入時執行，但延遲為30秒，不會影響登入 detrimentally。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-139">**Note:** As per the **Monitor Application Settings** task, this task is run at logon but is delayed by 30 seconds to not affect the logon detrimentally.</span></span>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6ffc2-140">任務名稱</span><span class="sxs-lookup"><span data-stu-id="6ffc2-140">Task name</span></span></th>
<th align="left"><span data-ttu-id="6ffc2-141">預設事件</span><span class="sxs-lookup"><span data-stu-id="6ffc2-141">Default event</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6ffc2-142">\Microsoft\UE-V\Sync 控制器應用程式</span><span class="sxs-lookup"><span data-stu-id="6ffc2-142">\Microsoft\UE-V\Sync Controller Application</span></span></p></td>
<td align="left"><p><span data-ttu-id="6ffc2-143">登入，此後每30分鐘</span><span class="sxs-lookup"><span data-stu-id="6ffc2-143">Logon, and every 30 minutes thereafter</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="6ffc2-144">例如，下列命令會將 agent 設定為每15分鐘同步處理設定，而不是預設的30分鐘。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-144">For example, the following command configures the agent to synchronize settings every 15 minutes instead of the default 30 minutes.</span></span>

``` syntax
Schtasks /change /tn “Microsoft\UE-V\Sync Controller Application” /ri 15
```

### <span data-ttu-id="6ffc2-145">在登出時同步處理設定</span><span class="sxs-lookup"><span data-stu-id="6ffc2-145">Synchronize Settings at Logoff</span></span>

<span data-ttu-id="6ffc2-146">[登出工作] 的 [**同步處理設定**] 是用來在登錄時啟動應用程式，以控制應用程式在 ue-v 登出時的同步處理。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-146">The **Synchronize Settings at Logoff** task is used to start an application at logon that controls the synchronization of applications at logoff for UE-V.</span></span> <span data-ttu-id="6ffc2-147">[登出] 工作的 [同步處理設定] 會執行 Microsoft.Uev.SyncController.exe 檔案，該檔案位於 UE-V Agent 安裝目錄中。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-147">The Synchronize Settings at Logoff task runs the Microsoft.Uev.SyncController.exe file, which is located in the UE-V Agent installation directory.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6ffc2-148">任務名稱</span><span class="sxs-lookup"><span data-stu-id="6ffc2-148">Task name</span></span></th>
<th align="left"><span data-ttu-id="6ffc2-149">預設事件</span><span class="sxs-lookup"><span data-stu-id="6ffc2-149">Default event</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6ffc2-150">登出時的 \Microsoft\UE-V\Synchronize 設定</span><span class="sxs-lookup"><span data-stu-id="6ffc2-150">\Microsoft\UE-V\Synchronize Settings at Logoff</span></span></p></td>
<td align="left"><p><span data-ttu-id="6ffc2-151">標識</span><span class="sxs-lookup"><span data-stu-id="6ffc2-151">Logon</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="6ffc2-152">範本自動更新</span><span class="sxs-lookup"><span data-stu-id="6ffc2-152">Template Auto Update</span></span>

<span data-ttu-id="6ffc2-153">**範本自動更新**工作會檢查 [設定] 範本目錄，以瞭解新的、更新或移除的範本。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-153">The **Template Auto Update** task checks the settings template catalog for new, updated, or removed templates.</span></span> <span data-ttu-id="6ffc2-154">只有在 SettingsTemplateCatalog 已設定的情況下，才會執行此工作。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-154">This task only runs if the SettingsTemplateCatalog is configured.</span></span> <span data-ttu-id="6ffc2-155">**範本自動更新**工作會執行 ApplySettingsCatalog.exe 檔案，該檔案位於 ue-v agent 安裝目錄中。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-155">The **Template Auto Update** task runs the ApplySettingsCatalog.exe file, which is located in the UE-V Agent installation directory.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6ffc2-156">任務名稱</span><span class="sxs-lookup"><span data-stu-id="6ffc2-156">Task name</span></span></th>
<th align="left"><span data-ttu-id="6ffc2-157">預設事件</span><span class="sxs-lookup"><span data-stu-id="6ffc2-157">Default event</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6ffc2-158">\Microsoft\UE-V\Template 自動更新</span><span class="sxs-lookup"><span data-stu-id="6ffc2-158">\Microsoft\UE-V\Template Auto Update</span></span></p></td>
<td align="left"><p><span data-ttu-id="6ffc2-159">在1小時視窗中的隨機時間內，于每日的系統啟動和每天3:30</span><span class="sxs-lookup"><span data-stu-id="6ffc2-159">System startup and at 3:30 AM every day, at a random time within a 1-hour window</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="6ffc2-160">**範例：** 下列命令會將 UE-V Agent 設定為每小時檢查設定範本的目錄存放區。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-160">**Example:** The following command configures the UE-V Agent to check the settings template catalog store every hour.</span></span>

``` syntax
schtasks /change /tn "Microsoft\UE-V\Template Auto Update" /ri 60
```

### <span data-ttu-id="6ffc2-161">上傳 CEIP 資料</span><span class="sxs-lookup"><span data-stu-id="6ffc2-161">Upload CEIP Data</span></span>

<span data-ttu-id="6ffc2-162">如果使用者或系統管理員選擇參與客戶經驗改進計畫（CEIP），則會在安裝期間，**上傳 CEIP 資料**工作會執行。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-162">The **Upload CEIP Data** task runs during the installation if the user or the administrator chose to participate in the Customer Experience Improvement Program (CEIP).</span></span> <span data-ttu-id="6ffc2-163">此工作會將資料上傳到您用來協助改善產品以供將來版本 UE-V 發行之 CEIP 伺服器。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-163">This task uploads the data to the CEIP servers where the data is used to help improve the product for future releases of UE-V.</span></span> <span data-ttu-id="6ffc2-164">此排程的任務會在登入之後每隔4小時執行一次。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-164">This scheduled task runs at logon and every 4 hours afterwards.</span></span> <span data-ttu-id="6ffc2-165">[**上傳 CEIP 資料**] 任務會執行 UevSqmUploader.exe 檔案，該檔案位於 ue-v agent 安裝目錄中。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-165">The **Upload CEIP data** task runs the UevSqmUploader.exe file, which is located in the UE-V Agent installation directory.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="6ffc2-166">任務名稱</span><span class="sxs-lookup"><span data-stu-id="6ffc2-166">Task name</span></span></th>
<th align="left"><span data-ttu-id="6ffc2-167">預設事件</span><span class="sxs-lookup"><span data-stu-id="6ffc2-167">Default event</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="6ffc2-168">\Microsoft\UE-V\Upload CEIP 資料</span><span class="sxs-lookup"><span data-stu-id="6ffc2-168">\Microsoft\UE-V\Upload CEIP data</span></span></p></td>
<td align="left"><p><span data-ttu-id="6ffc2-169">登入及每4小時</span><span class="sxs-lookup"><span data-stu-id="6ffc2-169">At logon and every 4 hours</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="6ffc2-170">UE-V 2 排程的任務詳細資料</span><span class="sxs-lookup"><span data-stu-id="6ffc2-170">UE-V 2 Scheduled Task Details</span></span>


<span data-ttu-id="6ffc2-171">下列圖表提供 UE-V 2 排程任務的其他相關資訊：</span><span class="sxs-lookup"><span data-stu-id="6ffc2-171">The following chart provides additional information about scheduled tasks for UE-V 2:</span></span>

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="6ffc2-172">任務名稱 </strong> （檔案名）</span><span class="sxs-lookup"><span data-stu-id="6ffc2-172">Task Name</strong> (file name)</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="6ffc2-173">預設頻率</span><span class="sxs-lookup"><span data-stu-id="6ffc2-173">Default Frequency</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="6ffc2-174">Power 開關</span><span class="sxs-lookup"><span data-stu-id="6ffc2-174">Power Toggle</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="6ffc2-175">僅空閒</span><span class="sxs-lookup"><span data-stu-id="6ffc2-175">Idle Only</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="6ffc2-176">網路連線</span><span class="sxs-lookup"><span data-stu-id="6ffc2-176">Network Connection</span></span></strong></p></td>
<td align="left"><p><strong><span data-ttu-id="6ffc2-177">描述</span><span class="sxs-lookup"><span data-stu-id="6ffc2-177">Description</span></span></strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="6ffc2-178">監視應用程式設定 </strong> （UevAppMonitor.exe）</span><span class="sxs-lookup"><span data-stu-id="6ffc2-178">Monitor Application Settings</strong> (UevAppMonitor.exe)</span></span></p></td>
<td align="left"><p><span data-ttu-id="6ffc2-179">登入後的30秒後開始，並持續至登出。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-179">Starts 30 seconds after logon and continues until logoff.</span></span></p></td>
<td align="left"><p><span data-ttu-id="6ffc2-180">不可以</span><span class="sxs-lookup"><span data-stu-id="6ffc2-180">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="6ffc2-181">是</span><span class="sxs-lookup"><span data-stu-id="6ffc2-181">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="6ffc2-182">無</span><span class="sxs-lookup"><span data-stu-id="6ffc2-182">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="6ffc2-183">同步處理 Windows （AppX）應用程式的設定。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-183">Synchronizes settings for Windows (AppX) apps.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="6ffc2-184">同步處理控制器應用程式 </strong> （Microsoft.Uev.SyncController.exe）</span><span class="sxs-lookup"><span data-stu-id="6ffc2-184">Sync Controller Application</strong> (Microsoft.Uev.SyncController.exe)</span></span></p></td>
<td align="left"><p><span data-ttu-id="6ffc2-185">登入及此後每30分鐘。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-185">At logon and every 30 min thereafter.</span></span></p></td>
<td align="left"><p><span data-ttu-id="6ffc2-186">是</span><span class="sxs-lookup"><span data-stu-id="6ffc2-186">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="6ffc2-187">是</span><span class="sxs-lookup"><span data-stu-id="6ffc2-187">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="6ffc2-188">僅在網路已連線的情況</span><span class="sxs-lookup"><span data-stu-id="6ffc2-188">Only if Network is connected</span></span></p></td>
<td align="left"><p><span data-ttu-id="6ffc2-189">啟動同步處理控制器，將本機設定與設定儲存位置同步處理。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-189">Starts the Sync Controller which synchronizes local settings with the settings storage location.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="6ffc2-190">在登出時同步處理設定 </strong> （Microsoft.Uev.SyncController.exe）</span><span class="sxs-lookup"><span data-stu-id="6ffc2-190">Synchronize Settings at Logoff</strong> (Microsoft.Uev.SyncController.exe)</span></span></p></td>
<td align="left"><p><span data-ttu-id="6ffc2-191">登入，然後等待登出同步處理設定。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-191">Runs at logon and then waits for Logoff to Synchronize settings.</span></span></p></td>
<td align="left"><p><span data-ttu-id="6ffc2-192">不可以</span><span class="sxs-lookup"><span data-stu-id="6ffc2-192">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="6ffc2-193">是</span><span class="sxs-lookup"><span data-stu-id="6ffc2-193">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="6ffc2-194">無</span><span class="sxs-lookup"><span data-stu-id="6ffc2-194">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="6ffc2-195">在登入時啟動應用程式，以控制應用程式在登出時的同步處理。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-195">Start an application at logon that controls the synchronization of applications at logoff.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="6ffc2-196">範本自動更新 </strong> （ApplySettingsCatalog.exe）</span><span class="sxs-lookup"><span data-stu-id="6ffc2-196">Template Auto Update</strong> (ApplySettingsCatalog.exe)</span></span></p></td>
<td align="left"><p><span data-ttu-id="6ffc2-197">在最初登入時執行，此後每天的3:30 會執行。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-197">Runs at initial logon and at 3:30 AM every day thereafter.</span></span></p></td>
<td align="left"><p><span data-ttu-id="6ffc2-198">是</span><span class="sxs-lookup"><span data-stu-id="6ffc2-198">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="6ffc2-199">否</span><span class="sxs-lookup"><span data-stu-id="6ffc2-199">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="6ffc2-200">無</span><span class="sxs-lookup"><span data-stu-id="6ffc2-200">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="6ffc2-201">針對新的、更新的或已移除的範本，檢查設定範本目錄。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-201">Checks the settings template catalog for new, updated, or removed templates.</span></span> <span data-ttu-id="6ffc2-202">只有在設定 SettingsTemplateCatalog 之後，才能執行此工作。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-202">This task only runs if SettingsTemplateCatalog is configured.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="6ffc2-203">收集 CEIP 資料 </strong> （UevSqmSession.exe）</span><span class="sxs-lookup"><span data-stu-id="6ffc2-203">Collect CEIP data</strong> (UevSqmSession.exe)</span></span></p></td>
<td align="left"><p><span data-ttu-id="6ffc2-204">登入後啟動服務</span><span class="sxs-lookup"><span data-stu-id="6ffc2-204">At logon launches service</span></span></p></td>
<td align="left"><p><span data-ttu-id="6ffc2-205">否</span><span class="sxs-lookup"><span data-stu-id="6ffc2-205">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="6ffc2-206">是</span><span class="sxs-lookup"><span data-stu-id="6ffc2-206">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="6ffc2-207">無</span><span class="sxs-lookup"><span data-stu-id="6ffc2-207">N/A</span></span></p></td>
<td align="left"><p><span data-ttu-id="6ffc2-208">如果使用者或系統管理員將您加入客戶經驗改進計畫（CEIP），此任務會收集可協助改善 UE-V 未來發行的資料。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-208">If the user or administrator opts in to the Customer Experience Improvement Program (CEIP), this task collects data that helps improve UE-V future releases.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="6ffc2-209">上傳 CEIP 資料 </strong> （UevSqmUploader.exe）</span><span class="sxs-lookup"><span data-stu-id="6ffc2-209">Upload CEIP Data</strong> (UevSqmUploader.exe)</span></span></p></td>
<td align="left"><p><span data-ttu-id="6ffc2-210">在登入之後，每一天的 4:00 AM 都會執行。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-210">Runs at logon and at 4:00 AM every day thereafter.</span></span></p></td>
<td align="left"><p><span data-ttu-id="6ffc2-211">否</span><span class="sxs-lookup"><span data-stu-id="6ffc2-211">No</span></span></p></td>
<td align="left"><p><span data-ttu-id="6ffc2-212">是</span><span class="sxs-lookup"><span data-stu-id="6ffc2-212">Yes</span></span></p></td>
<td align="left"><p><span data-ttu-id="6ffc2-213">僅在網路已連線的情況</span><span class="sxs-lookup"><span data-stu-id="6ffc2-213">Only if Network is connected</span></span></p></td>
<td align="left"><p><span data-ttu-id="6ffc2-214">如果使用者或系統管理員將您加入客戶經驗改進計畫（CEIP），此任務會將資料上傳到 CEIP 伺服器。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-214">If the user or administrator opts in to the Customer Experience Improvement Program (CEIP), this task uploads the data to the CEIP servers.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="6ffc2-215">說明</span><span class="sxs-lookup"><span data-stu-id="6ffc2-215">Legend</span></span>**

-   <span data-ttu-id="6ffc2-216">[**電源] 開關**– [任務排程器] 會在未連線到交流電源時，優化電源使用量。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-216">**Power Toggle** – Task Scheduler will optimize power consumption when not connected to AC power.</span></span> <span data-ttu-id="6ffc2-217">如果電腦切換至電池電源，工作可能會停止執行。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-217">The task might stop running if the computer switches to battery power.</span></span>

-   <span data-ttu-id="6ffc2-218">[**只有空閒**]-如果電腦停止閒置，工作就會停止執行。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-218">**Idle Only** – The task will stop running if the computer ceases to be idle.</span></span> <span data-ttu-id="6ffc2-219">根據預設，當電腦再次空閒時，任務不會重新開機。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-219">By default the task will not restart when the computer is idle again.</span></span> <span data-ttu-id="6ffc2-220">相反，任務會在下一個工作觸發程式再次開始。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-220">Instead the task will begin again on the next task trigger.</span></span>

-   <span data-ttu-id="6ffc2-221">**網路**連線–標示為「是」的工作只有在電腦有可用的網路連線時才會執行。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-221">**Network Connection** – Tasks marked “Yes” only run if the computer has a network connection available.</span></span> <span data-ttu-id="6ffc2-222">無論網路連通性為何，標示為「N/A」的工作。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-222">Tasks marked “N/A” run regardless of network connectivity.</span></span>

### <span data-ttu-id="6ffc2-223">如何管理排程任務</span><span class="sxs-lookup"><span data-stu-id="6ffc2-223">How to Manage Scheduled Tasks</span></span>

<span data-ttu-id="6ffc2-224">若要尋找排程的任務，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="6ffc2-224">To find Scheduled Tasks, perform the following:</span></span>

1.  <span data-ttu-id="6ffc2-225">在使用者電腦上開啟「排程任務」。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-225">Open “Schedule Tasks” on the user computer.</span></span>

2.  <span data-ttu-id="6ffc2-226">流覽至：任務排程器-工作排程器文檔 &gt; 庫- &gt; Microsoft- &gt; ue-v</span><span class="sxs-lookup"><span data-stu-id="6ffc2-226">Navigate to: Task Scheduler -&gt; Task Scheduler Library -&gt; Microsoft -&gt; UE-V</span></span>

3.  <span data-ttu-id="6ffc2-227">在 [詳細資料] 窗格中，選取您想要管理和設定的排程任務。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-227">Select the scheduled task you wish to manage and configure in the details pane.</span></span>

### <span data-ttu-id="6ffc2-228">其他資訊</span><span class="sxs-lookup"><span data-stu-id="6ffc2-228">Additional information</span></span>

<span data-ttu-id="6ffc2-229">下列額外資訊適用于 UE-V 排程的任務：</span><span class="sxs-lookup"><span data-stu-id="6ffc2-229">The following additional information applies to UE-V scheduled tasks:</span></span>

-   <span data-ttu-id="6ffc2-230">[ll] 任務序列程式是位於 UE-V Agent 安裝資料夾（ `%programFiles%\Microsoft User Experience Virtualization\Agent\[architecture]\` 依預設）。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-230">ll task sequence programs are located in the UE-V Agent installation folder, `%programFiles%\Microsoft User Experience Virtualization\Agent\[architecture]\`, by default.</span></span>

-   <span data-ttu-id="6ffc2-231">當 UE-V SyncMethod 設定為 "SyncProvider" （UE-V 2 預設設定）時，同步處理控制器應用程式排程任務是重要的元件。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-231">The Sync Controller Application Scheduled task is the crucial component when the UE-V SyncMethod is set to “SyncProvider” (UE-V 2 default configuration).</span></span> <span data-ttu-id="6ffc2-232">這個排程的工作會使 SettingsSToragePath 與本機快取設定套件檔案的版本保持同步。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-232">This scheduled task keeps the SettingsSToragePath synchronized with the locally cached versions of the settings package files.</span></span> <span data-ttu-id="6ffc2-233">如果使用者抱怨設定不會經常同步處理，則您可以將排程的任務設定減少為1分鐘。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-233">If users complain that settings do not synchronize often enough, then you can reduce the scheduled task setting to as little as 1 minute.</span></span><span data-ttu-id="6ffc2-234">如有需要，您也可以將30分鐘預設值增加至較高的金額。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-234"> You can also increase the 30 min default to a higher amount if necessary.</span></span> <span data-ttu-id="6ffc2-235">如果使用者抱怨在登入時設定的同步處理速度不夠快，您可以移除排程任務的 [延遲] 設定。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-235">If users complain that settings do not synchronize fast enough on logon, then you can remove the delay setting for the scheduled task.</span></span> <span data-ttu-id="6ffc2-236">（您可以在 [**編輯觸發**] 對話方塊中找到 [延遲] 設定</span><span class="sxs-lookup"><span data-stu-id="6ffc2-236">(You can find the delay setting in the **Edit Trigger** dialogue box)</span></span>

-   <span data-ttu-id="6ffc2-237">如果您使用其他方法讓用戶端的範本保持同步（亦即群組原則或 Configuration Manager 比較基準），就不需要停用範本自動更新排程的工作。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-237">You do not need to disable the Template Auto Update scheduled task if you use another method to keep the clients’ templates in sync (i.e. Group Policy or Configuration Manager Baselines).</span></span> <span data-ttu-id="6ffc2-238">保留 SettingsTemplateCatalog 屬性值為空白，可避免 UE-V 檢查自訂範本的設定目錄。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-238">Leaving the SettingsTemplateCatalog property value blank prevents UE-V from checking the settings catalog for custom templates.</span></span> <span data-ttu-id="6ffc2-239">這個排程的任務 ApplySettingsCatalog.exe 會執行，主要會立即返回。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-239">This scheduled task runs ApplySettingsCatalog.exe and will essentially return immediately.</span></span>

-   <span data-ttu-id="6ffc2-240">[監視應用程式設定排程的工作] 會即時更新 Windows 應用程式（AppX）設定，根據每個 app 內建的 Windows 應用程式設定觸發程式。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-240">The Monitor Application Settings scheduled task will update Windows app (AppX) settings in real time, based on Windows app program setting triggers built into each app.</span></span>






## <span data-ttu-id="6ffc2-241">相關主題</span><span class="sxs-lookup"><span data-stu-id="6ffc2-241">Related topics</span></span>


[<span data-ttu-id="6ffc2-242">管理 UE-V 2。</span><span class="sxs-lookup"><span data-stu-id="6ffc2-242">Administering UE-V 2.x</span></span>](administering-ue-v-2x-new-uevv2.md)

[<span data-ttu-id="6ffc2-243">部署自訂應用程式的 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="6ffc2-243">Deploy UE-V 2.x for Custom Applications</span></span>](deploy-ue-v-2x-for-custom-applications-new-uevv2.md#deploycatalogue)

 

 





