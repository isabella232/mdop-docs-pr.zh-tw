---
title: 移轉 UE-V 設定套件
description: 移轉 UE-V 設定套件
author: dansimp
ms.assetid: 93d99254-3e17-4e96-92ad-87059d8554a7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d0087f334e916c06e7611d2671d0b50e7d1dd916
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809818"
---
# <span data-ttu-id="616ab-103">移轉 UE-V 設定套件</span><span class="sxs-lookup"><span data-stu-id="616ab-103">Migrating UE-V Settings Packages</span></span>


<span data-ttu-id="616ab-104">在 Microsoft 使用者體驗虛擬化（UE-V）部署的生命週期中，您可能需要在遷移到新的伺服器或進行備份時，重新置放使用者設定套件。</span><span class="sxs-lookup"><span data-stu-id="616ab-104">In the lifecycle of a Microsoft User Experience Virtualization (UE-V) deployment, you might need to relocate the user settings packages either when migrating to a new server or for backup purposes.</span></span> <span data-ttu-id="616ab-105">在下列案例中可能需要遷移設定套件：</span><span class="sxs-lookup"><span data-stu-id="616ab-105">Migration of settings packages might be needed in the following scenarios:</span></span>

-   <span data-ttu-id="616ab-106">將現有的伺服器硬體升級至更先進的伺服器。</span><span class="sxs-lookup"><span data-stu-id="616ab-106">Upgrade of existing server hardware to a more modern server.</span></span>

-   <span data-ttu-id="616ab-107">將設定儲存位置從實驗室遷移到成品伺服器。</span><span class="sxs-lookup"><span data-stu-id="616ab-107">Migration of a settings storage location share from a lab to a production server.</span></span>

<span data-ttu-id="616ab-108">只要複製檔案和資料夾，就不會保留安全性設定和許可權。</span><span class="sxs-lookup"><span data-stu-id="616ab-108">Simply copying the files and folders will not preserve the security settings and permissions.</span></span> <span data-ttu-id="616ab-109">下列描述的步驟會將設定套件檔案以 NTFS 許可權正確地複製到新的共用位置。</span><span class="sxs-lookup"><span data-stu-id="616ab-109">The following described steps will properly copy the settings package files with their NTFS permissions to a new share.</span></span>

**<span data-ttu-id="616ab-110">如何在遷移到新伺服器時保留 UE-V 設定套件</span><span class="sxs-lookup"><span data-stu-id="616ab-110">How to preserve UE-V settings packages when migrating to a new server</span></span>**

1.  <span data-ttu-id="616ab-111">在其他伺服器上的新位置中，建立新資料夾;例如，MySettings。</span><span class="sxs-lookup"><span data-stu-id="616ab-111">In a new location on a different server, create a new folder; for example, MySettings.</span></span>

2.  <span data-ttu-id="616ab-112">停用舊伺服器上舊資料夾共用的共用。</span><span class="sxs-lookup"><span data-stu-id="616ab-112">Disable sharing for the old folder share on the old server.</span></span>

3.  <span data-ttu-id="616ab-113">從命令列將現有的設定套件從 Robocopy 移至新的伺服器。</span><span class="sxs-lookup"><span data-stu-id="616ab-113">Move the existing settings packages to the new server with Robocopy from the command line.</span></span> <span data-ttu-id="616ab-114">例如：</span><span class="sxs-lookup"><span data-stu-id="616ab-114">For example:</span></span>

    ``` syntax
    c:\start robocopy "\\servername\E$\MySettings" "\\servername\E$\MySettings" /b /sec /secfix /e /LOG:D:\Robocopylogs\MySettings.txt
    ```

    <span data-ttu-id="616ab-115">**記事** 若要監視複製進度，請使用記錄檔案讀取器（例如 Trace32）開啟 MySettings.txt。</span><span class="sxs-lookup"><span data-stu-id="616ab-115">**Note** To monitor the copy progress, open MySettings.txt with a log file reader such as Trace32.</span></span>

     

4.  <span data-ttu-id="616ab-116">授與新共用的共用層許可權。</span><span class="sxs-lookup"><span data-stu-id="616ab-116">Grant share-level permissions to the new share.</span></span> <span data-ttu-id="616ab-117">離開由 Robocopy 設定的 NTFS 許可權。</span><span class="sxs-lookup"><span data-stu-id="616ab-117">Leave the NTFS permissions as they were set by Robocopy.</span></span>

    <span data-ttu-id="616ab-118">在執行 UE-V agent 的電腦上，更新 SettingsStoragePath 設定為新共用的 UNC 路徑。</span><span class="sxs-lookup"><span data-stu-id="616ab-118">On computers that run the UE-V agent, update the SettingsStoragePath configuration setting to the UNC path of the new share.</span></span>

## <span data-ttu-id="616ab-119">相關主題</span><span class="sxs-lookup"><span data-stu-id="616ab-119">Related topics</span></span>


[<span data-ttu-id="616ab-120">管理 UE-V 1.0</span><span class="sxs-lookup"><span data-stu-id="616ab-120">Administering UE-V 1.0</span></span>](administering-ue-v-10.md)

[<span data-ttu-id="616ab-121">UE-V 1.0 作業</span><span class="sxs-lookup"><span data-stu-id="616ab-121">Operations for UE-V 1.0</span></span>](operations-for-ue-v-10.md)

 

 





