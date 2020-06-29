---
title: 變更 UE-V 排程工作的頻率
description: 變更 UE-V 排程工作的頻率
author: dansimp
ms.assetid: 33c2674e-0df4-4717-9c3d-820a90b16e19
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ced608608ffae82a29fb5ca84cfca281082b8127
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809506"
---
# <span data-ttu-id="17077-103">變更 UE-V 排程工作的頻率</span><span class="sxs-lookup"><span data-stu-id="17077-103">Changing the Frequency of UE-V Scheduled Tasks</span></span>


<span data-ttu-id="17077-104">Microsoft User Experience Virtualization （UE-V） Agent 安裝程式（AgentSetup.exe）會在 UE-V Agent 安裝期間建立兩個排程的任務。</span><span class="sxs-lookup"><span data-stu-id="17077-104">The Microsoft User Experience Virtualization (UE-V) Agent installer, AgentSetup.exe, creates two scheduled tasks during the UE-V Agent installation.</span></span> <span data-ttu-id="17077-105">這兩個工作為 [**範本自動更新**] 工作，以及 [**設定儲存位置狀態**] 任務。</span><span class="sxs-lookup"><span data-stu-id="17077-105">The two tasks are the **Template Auto Update** task and the **Setting Storage Location Status** task.</span></span> <span data-ttu-id="17077-106">這些排程的任務無法使用 UE-V 工具進行設定。</span><span class="sxs-lookup"><span data-stu-id="17077-106">These scheduled tasks are not configurable with the UE-V tools.</span></span> <span data-ttu-id="17077-107">如果系統管理員想要變更這些專案的排程任務，就可以建立使用 Schtasks.exe 命令列選項的腳本。</span><span class="sxs-lookup"><span data-stu-id="17077-107">Administrators who wish to change the scheduled task for these items can create a script that uses the Schtasks.exe command-line options.</span></span>

<span data-ttu-id="17077-108">如需 Schtasks.exe 的詳細資訊，請參閱[如何使用 Schtasks、exe 來排程 Windows Server 2003 中的任務](https://go.microsoft.com/fwlink/?LinkID=264854)。</span><span class="sxs-lookup"><span data-stu-id="17077-108">For more information about Schtasks.exe, see [How to use Schtasks,exe to Schedule Tasks in Windows Server 2003](https://go.microsoft.com/fwlink/?LinkID=264854).</span></span>

## <span data-ttu-id="17077-109">範本自動更新</span><span class="sxs-lookup"><span data-stu-id="17077-109">Template Auto-Update</span></span>


<span data-ttu-id="17077-110">**範本自動更新**工作會檢查 [設定] 範本目錄，以瞭解新的、更新或移除的範本。</span><span class="sxs-lookup"><span data-stu-id="17077-110">The **Template Auto Update** task checks the settings template catalog for new, updated, or removed templates.</span></span> <span data-ttu-id="17077-111">只有在 SettingsTemplateCatalog 已設定的情況下，才會執行此工作。</span><span class="sxs-lookup"><span data-stu-id="17077-111">This task only runs if the SettingsTemplateCatalog is configured.</span></span> <span data-ttu-id="17077-112">**範本自動更新**工作會執行 ApplySettingsCatalog.exe 檔案，該檔案位於 ue-v agent 安裝目錄中。</span><span class="sxs-lookup"><span data-stu-id="17077-112">The **Template Auto Update** task runs the ApplySettingsCatalog.exe file, which is located in the UE-V Agent install directory.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="17077-113">任務名稱</span><span class="sxs-lookup"><span data-stu-id="17077-113">Task name</span></span></th>
<th align="left"><span data-ttu-id="17077-114">預設觸發程式</span><span class="sxs-lookup"><span data-stu-id="17077-114">Default trigger</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="17077-115">\Microsoft\UE-V\Template 自動更新</span><span class="sxs-lookup"><span data-stu-id="17077-115">\Microsoft\UE-V\Template Auto Update</span></span></p></td>
<td align="left"><p><span data-ttu-id="17077-116">每天3:30</span><span class="sxs-lookup"><span data-stu-id="17077-116">3:30 AM every day</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="17077-117">**範例：** 下列命令會將代理程式設定為每小時檢查設定範本的目錄存放區。</span><span class="sxs-lookup"><span data-stu-id="17077-117">**Example:** The following command configures the agent to check the settings template catalog store every hour.</span></span>

``` syntax
schtasks /change /tn "Microsoft\UE-V\Template Auto Update" /ri 60
```

## <span data-ttu-id="17077-118">設定儲存位置狀態</span><span class="sxs-lookup"><span data-stu-id="17077-118">Settings Storage Location Status</span></span>


<span data-ttu-id="17077-119">**設定儲存位置狀態**任務會執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="17077-119">The **Setting Storage Location Status** task performs the following actions:</span></span>

1.  <span data-ttu-id="17077-120">檢查以確認 UE-V 資料夾仍受到固定或使用 [離線檔案] 功能進行註冊。</span><span class="sxs-lookup"><span data-stu-id="17077-120">Checks to make sure the UE-V folders are still pinned or registered with the offline files feature.</span></span>

2.  <span data-ttu-id="17077-121">檢查設定儲存位置是否為 [離線] 或 [線上]。</span><span class="sxs-lookup"><span data-stu-id="17077-121">Checks whether the settings storage location is offline or online.</span></span>

3.  <span data-ttu-id="17077-122">根據指定的間隔強行進行同步處理，而不是離線檔案的預設間隔。</span><span class="sxs-lookup"><span data-stu-id="17077-122">Forces a synchronization on the specified interval instead of the default interval for offline files.</span></span>

4.  <span data-ttu-id="17077-123">同步處理所有設定為預回遷的設定套件。</span><span class="sxs-lookup"><span data-stu-id="17077-123">Synchronizes any settings packages that are configured to be pre-fetched.</span></span>

5.  <span data-ttu-id="17077-124">檢查 Active Directory 主目錄路徑是否已變更。</span><span class="sxs-lookup"><span data-stu-id="17077-124">Checks if the Active Directory home directory path has changed.</span></span>

6.  <span data-ttu-id="17077-125">將目前的設定儲存空間配置寫入下列位置</span><span class="sxs-lookup"><span data-stu-id="17077-125">Writes the current settings storage configuration under the following location</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="17077-126">任務名稱</span><span class="sxs-lookup"><span data-stu-id="17077-126">Task name</span></span></th>
    <th align="left"><span data-ttu-id="17077-127">預設觸發程式</span><span class="sxs-lookup"><span data-stu-id="17077-127">Default trigger</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="17077-128">\Microsoft\UE-V\Settings 儲存位置狀態</span><span class="sxs-lookup"><span data-stu-id="17077-128">\Microsoft\UE-V\Settings Storage Location Status</span></span></p></td>
    <td align="left"><p><span data-ttu-id="17077-129">在任何使用者登入之後，每隔30分鐘重複一次。</span><span class="sxs-lookup"><span data-stu-id="17077-129">At logon of any user – After triggered, repeat every 30 minutes indefinitely.</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

<span data-ttu-id="17077-130">**範例：** 下列命令會將代理程式設定為在每小時執行上述動作。</span><span class="sxs-lookup"><span data-stu-id="17077-130">**Example:** The following command configures the agent to run the action above every hour.</span></span>

``` syntax
schtasks /change /tn "\Microsoft\UE-V\Settings Storage Location Status" /ri 60
```

## <span data-ttu-id="17077-131">相關主題</span><span class="sxs-lookup"><span data-stu-id="17077-131">Related topics</span></span>


[<span data-ttu-id="17077-132">管理 UE-V 1.0</span><span class="sxs-lookup"><span data-stu-id="17077-132">Administering UE-V 1.0</span></span>](administering-ue-v-10.md)

[<span data-ttu-id="17077-133">UE-V 1.0 作業</span><span class="sxs-lookup"><span data-stu-id="17077-133">Operations for UE-V 1.0</span></span>](operations-for-ue-v-10.md)

 

 





