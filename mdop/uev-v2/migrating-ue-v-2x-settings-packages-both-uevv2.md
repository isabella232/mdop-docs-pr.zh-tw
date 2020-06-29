---
title: 遷移 UE-V a.x 設定套件
description: 遷移 UE-V a.x 設定套件
author: dansimp
ms.assetid: f79381f4-e142-405c-b728-5c048502aa70
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0aa1f1c36594d69de40306dfa70a4a0cf5c86dbb
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811204"
---
# <span data-ttu-id="1ecc6-103">遷移 UE-V a.x 設定套件</span><span class="sxs-lookup"><span data-stu-id="1ecc6-103">Migrating UE-V 2.x Settings Packages</span></span>


<span data-ttu-id="1ecc6-104">在 Microsoft 使用者體驗虛擬化（UE-V）2.0、2.1 或 2.1 SP1 部署的生命週期中，您可能必須在您遷移至新伺服器或執行備份時，重新置放使用者設定套件。</span><span class="sxs-lookup"><span data-stu-id="1ecc6-104">In the lifecycle of a Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, or 2.1 SP1 deployment, you might have to relocate the user settings packages either when you migrate to a new server or when you perform backups.</span></span> <span data-ttu-id="1ecc6-105">在下列情況下，可能需要遷移設定套件：</span><span class="sxs-lookup"><span data-stu-id="1ecc6-105">Settings packages might have to be migrated in the following scenarios:</span></span>

-   <span data-ttu-id="1ecc6-106">將現有的伺服器硬體升級至更先進的伺服器。</span><span class="sxs-lookup"><span data-stu-id="1ecc6-106">Upgrade of existing server hardware to a more modern server.</span></span>

-   <span data-ttu-id="1ecc6-107">從測試伺服器到生產伺服器的設定儲存位置共用的遷移。</span><span class="sxs-lookup"><span data-stu-id="1ecc6-107">Migration of a settings storage location share from a test server to a production server.</span></span>

<span data-ttu-id="1ecc6-108">只要複製檔案和資料夾，就不會保留安全性設定和許可權。</span><span class="sxs-lookup"><span data-stu-id="1ecc6-108">Simply copying the files and folders does not preserve the security settings and permissions.</span></span> <span data-ttu-id="1ecc6-109">下列步驟說明如何將設定套件及其 NTFS 檔案系統許可權正確地複製到新的共用位置。</span><span class="sxs-lookup"><span data-stu-id="1ecc6-109">The following steps describe how to correctly copy the settings package along with their NTFS file system permissions to a new share.</span></span>

**<span data-ttu-id="1ecc6-110">若要在遷移到新伺服器時保留 UE-V 2 設定套件</span><span class="sxs-lookup"><span data-stu-id="1ecc6-110">To preserve UE-V 2 settings packages when you migrate to a new server</span></span>**

1.  <span data-ttu-id="1ecc6-111">在其他伺服器上的新位置中，建立新的資料夾，例如 MySettings。</span><span class="sxs-lookup"><span data-stu-id="1ecc6-111">In a new location on a different server, create a new folder, for example, MySettings.</span></span>

2.  <span data-ttu-id="1ecc6-112">停用舊伺服器上舊資料夾共用的共用。</span><span class="sxs-lookup"><span data-stu-id="1ecc6-112">Disable sharing for the old folder share on the old server.</span></span>

3.  <span data-ttu-id="1ecc6-113">使用 Robocopy 將現有的設定套件複製到新伺服器</span><span class="sxs-lookup"><span data-stu-id="1ecc6-113">To copy the existing settings packages to the new server with Robocopy</span></span>

    ``` syntax
    C:\start robocopy "\\servername\E$\MySettings" "\\servername\E$\MySettings" /b /sec /secfix /e /LOG:D:\Robocopylogs\MySettings.txt
    ```

    <span data-ttu-id="1ecc6-114">**記事** 若要監視複製進度，請使用記錄檢視器（例如 Trace32）開啟 MySettings.txt。</span><span class="sxs-lookup"><span data-stu-id="1ecc6-114">**Note** To monitor the copy progress, open MySettings.txt with a log viewer such as Trace32.</span></span>

     

4.  <span data-ttu-id="1ecc6-115">授與新共用的共用層許可權。</span><span class="sxs-lookup"><span data-stu-id="1ecc6-115">Grant share-level permissions to the new share.</span></span> <span data-ttu-id="1ecc6-116">保留由 Robocopy 設定的 NTFS 檔案系統許可權。</span><span class="sxs-lookup"><span data-stu-id="1ecc6-116">Leave the NTFS file system permissions as they were set by Robocopy.</span></span>

    <span data-ttu-id="1ecc6-117">在執行 UE-V Agent 的電腦上，將**SettingsStoragePath**設定設定更新為新共用的通用命名慣例（UNC）路徑。</span><span class="sxs-lookup"><span data-stu-id="1ecc6-117">On computers that run the UE-V Agent, update the **SettingsStoragePath** configuration setting to the Universal Naming Convention (UNC) path of the new share.</span></span>

    <span data-ttu-id="1ecc6-118">**為 ue-v 提供建議**嗎？</span><span class="sxs-lookup"><span data-stu-id="1ecc6-118">**Got a suggestion for UE-V**?</span></span> <span data-ttu-id="1ecc6-119">在[此](http://uev.uservoice.com/forums/280428-microsoft-user-experience-virtualization)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="1ecc6-119">Add or vote on suggestions [here](http://uev.uservoice.com/forums/280428-microsoft-user-experience-virtualization).</span></span> <span data-ttu-id="1ecc6-120">是否**有 ue-v 問題**？</span><span class="sxs-lookup"><span data-stu-id="1ecc6-120">**Got a UE-V issue**?</span></span> <span data-ttu-id="1ecc6-121">使用[Ue-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopuev)。</span><span class="sxs-lookup"><span data-stu-id="1ecc6-121">Use the [UE-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopuev).</span></span>

## <span data-ttu-id="1ecc6-122">相關主題</span><span class="sxs-lookup"><span data-stu-id="1ecc6-122">Related topics</span></span>


[<span data-ttu-id="1ecc6-123">管理 UE-V 2。</span><span class="sxs-lookup"><span data-stu-id="1ecc6-123">Administering UE-V 2.x</span></span>](administering-ue-v-2x-new-uevv2.md)

 

 





