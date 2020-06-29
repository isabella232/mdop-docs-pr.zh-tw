---
title: 管理 UE-V 2.x 的設定
description: 管理 UE-V 2.x 的設定
author: dansimp
ms.assetid: e2332eca-a9cd-4446-8f7c-d17058b03466
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 20d5d2942dbd805a4054a9431b237c821cbb70fe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812321"
---
# <span data-ttu-id="c8077-103">管理 UE-V 2.x 的設定</span><span class="sxs-lookup"><span data-stu-id="c8077-103">Manage Configurations for UE-V 2.x</span></span>


<span data-ttu-id="c8077-104">在 Microsoft 使用者體驗虛擬化（UE-V）2.0、2.1 或 2.1 SP1 週期中，您必須管理 UE-V Agent 的設定，也可以管理資源的儲存位置，例如設定套件檔案。</span><span class="sxs-lookup"><span data-stu-id="c8077-104">In the course of the Microsoft User Experience Virtualization (UE-V) 2.0, 2.1, or 2.1 SP1 lifecycle, you have to manage the configuration of the UE-V Agent and also manage storage locations for resources such as settings package files.</span></span> <span data-ttu-id="c8077-105">您可能需要執行其他工作，例如設定公司設定中心來定義使用者與 UE-V 互動的方式。</span><span class="sxs-lookup"><span data-stu-id="c8077-105">You might have to perform other tasks, for example, configuring the Company Settings Center to define how users interact with UE-V.</span></span> <span data-ttu-id="c8077-106">下列主題提供管理這些 UE-V 資源的指導方針。</span><span class="sxs-lookup"><span data-stu-id="c8077-106">The following topics provide guidance for managing these UE-V resources.</span></span>

## <span data-ttu-id="c8077-107">使用群組原則物件來設定 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="c8077-107">Configuring UE-V 2.x by using Group Policy Objects</span></span>


<span data-ttu-id="c8077-108">您可以使用群組原則物件來修改定義 UE-V 如何在電腦上同步處理設定的設定。</span><span class="sxs-lookup"><span data-stu-id="c8077-108">You can use Group Policy Objects to modify the settings that define how UE-V synchronizes settings on computers.</span></span>

[<span data-ttu-id="c8077-109">使用群組原則物件設定 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="c8077-109">Configuring UE-V 2.x with Group Policy Objects</span></span>](configuring-ue-v-2x-with-group-policy-objects-both-uevv2.md)

## <span data-ttu-id="c8077-110">使用 System Center Configuration Manager 2012 設定 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="c8077-110">Configuring UE-V 2.x with System Center Configuration Manager 2012</span></span>


<span data-ttu-id="c8077-111">您可以使用 SystemCenter2012 ConfigurationManager 來管理 ue-v Agent，方法是使用 UE-V 2 配置包。</span><span class="sxs-lookup"><span data-stu-id="c8077-111">You can use SystemCenter2012 ConfigurationManager to manage the UE-V Agent by using the UE-V 2 Configuration Pack.</span></span>

[<span data-ttu-id="c8077-112">使用 System Center Configuration Manager 2012 設定 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="c8077-112">Configuring UE-V 2.x with System Center Configuration Manager 2012</span></span>](configuring-ue-v-2x-with-system-center-configuration-manager-2012-both-uevv2.md)

## <span data-ttu-id="c8077-113">使用 PowerShell 和 WMI 管理 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="c8077-113">Administering UE-V 2.x with PowerShell and WMI</span></span>


<span data-ttu-id="c8077-114">UE-V 提供 Windows PowerShell Cmdlet，可協助管理員執行各種 UE-V 工作。</span><span class="sxs-lookup"><span data-stu-id="c8077-114">UE-V provides Windows PowerShell cmdlets, which can help administrators perform various UE-V tasks.</span></span>

[<span data-ttu-id="c8077-115">使用 Windows PowerShell 和 WMI 管理 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="c8077-115">Administering UE-V 2.x with Windows PowerShell and WMI</span></span>](administering-ue-v-2x-with-windows-powershell-and-wmi-both-uevv2.md)

## <span data-ttu-id="c8077-116">設定 UE-V 2. x 的公司設定中心</span><span class="sxs-lookup"><span data-stu-id="c8077-116">Configuring the Company Settings Center for UE-V 2.x</span></span>


<span data-ttu-id="c8077-117">您可以設定使用 UE-V Agent 所安裝的公司設定中心，以定義使用者與 UE-V 互動的方式。</span><span class="sxs-lookup"><span data-stu-id="c8077-117">You can configure the Company Settings Center that is installed by using the UE-V Agent to define how users interact with UE-V.</span></span>

[<span data-ttu-id="c8077-118">設定 UE-V 2. x 的公司設定中心</span><span class="sxs-lookup"><span data-stu-id="c8077-118">Configuring the Company Settings Center for UE-V 2.x</span></span>](configuring-the-company-settings-center-for-ue-v-2x-both-uevv2.md)

## <span data-ttu-id="c8077-119">UE-V 2. x 的配置設定範例</span><span class="sxs-lookup"><span data-stu-id="c8077-119">Examples of configuration settings for UE-V 2.x</span></span>


<span data-ttu-id="c8077-120">以下是 UE-V 設定設定的一些範例：</span><span class="sxs-lookup"><span data-stu-id="c8077-120">Here are some examples of UE-V configuration settings:</span></span>

-   <span data-ttu-id="c8077-121">**設定儲存路徑：** 指定儲存 UE-V 設定的檔案共用位置。</span><span class="sxs-lookup"><span data-stu-id="c8077-121">**Settings Storage Path:** Specifies the location of the file share that stores the UE-V settings.</span></span>

-   <span data-ttu-id="c8077-122">**設定範本目錄路徑：** 指定通用命名慣例（UNC）路徑，該路徑定義已針對新設定位置範本檢查的位置。</span><span class="sxs-lookup"><span data-stu-id="c8077-122">**Settings Template Catalog Path:** Specifies the Universal Naming Convention (UNC) path that defines the location that was checked for new settings location templates.</span></span>

-   <span data-ttu-id="c8077-123">**註冊 Microsoft 範本：** 指定是否應在安裝期間註冊預設的 Microsoft 範本。</span><span class="sxs-lookup"><span data-stu-id="c8077-123">**Register Microsoft Templates:** Specifies whether the default Microsoft templates should be registered during installation.</span></span>

-   <span data-ttu-id="c8077-124">**同步處理方法：** 指定 UE-V 是使用同步處理提供者或 "none"。</span><span class="sxs-lookup"><span data-stu-id="c8077-124">**Synchronization Method:** Specifies whether UE-V uses the sync provider or "none".</span></span> <span data-ttu-id="c8077-125">"SyncProvider" 支援的電腦已從網路中斷連線。</span><span class="sxs-lookup"><span data-stu-id="c8077-125">The "SyncProvider" supports computers that are disconnected from the network.</span></span> <span data-ttu-id="c8077-126">當電腦永遠連線至網路時，就會套用「無」。</span><span class="sxs-lookup"><span data-stu-id="c8077-126">"None" applies when the computer is always connected to the network.</span></span> <span data-ttu-id="c8077-127">如需同步處理方法的詳細資訊，請參閱[ue-v 2. x 的同步處理方法](sync-methods-for-ue-v-2x-both-uevv2.md)。</span><span class="sxs-lookup"><span data-stu-id="c8077-127">For more information about the Sync Method, see [Sync Methods for UE-V 2.x](sync-methods-for-ue-v-2x-both-uevv2.md).</span></span>

-   <span data-ttu-id="c8077-128">**同步處理超時：** 指定當它從 [設定] 儲存位置中檢索使用者設定時，電腦在超時前等待的毫秒數。</span><span class="sxs-lookup"><span data-stu-id="c8077-128">**Synchronization Timeout:** Specifies the number of milliseconds that the computer waits before time-out when it retrieves the user settings from the settings storage location.</span></span>

-   <span data-ttu-id="c8077-129">**啟用同步處理：** 指定是否已啟用或停用 UE-V 設定同步處理。</span><span class="sxs-lookup"><span data-stu-id="c8077-129">**Synchronization Enable:** Specifies whether the UE-V settings synchronization is enabled or disabled.</span></span>

-   <span data-ttu-id="c8077-130">**套件最大大小：** 指定 UE-V Agent 報告警告的設定套件檔閾值大小（以位元組為單位）。</span><span class="sxs-lookup"><span data-stu-id="c8077-130">**Maximum Package Size:** Specifies a settings package file threshold size in bytes at which the UE-V Agent reports a warning.</span></span>

-   <span data-ttu-id="c8077-131">**不要同步處理 Windows 應用程式設定：** 指定 UE-V 不應同步處理 Windows 應用程式。</span><span class="sxs-lookup"><span data-stu-id="c8077-131">**Don’t Sync Windows App Settings:** Specifies that UE-V should not synchronize Windows apps.</span></span>

-   <span data-ttu-id="c8077-132">**啟用/停用第一次使用通知：** 指定在第一次 UE-V Agent 在使用者的電腦上執行時，UE-V 是否會顯示一個對話方塊。</span><span class="sxs-lookup"><span data-stu-id="c8077-132">**Enable/Disable First Use Notification:** Specifies whether UE-V displays a dialog box the first time that the UE-V Agent runs on a user’s computer.</span></span>

-   <span data-ttu-id="c8077-133">**啟用/停用託盤圖示：** 指定 UE-V 是否在通知區域中顯示圖示，以及與它相關聯的任何通知。</span><span class="sxs-lookup"><span data-stu-id="c8077-133">**Enable/Disable Tray Icon:** Specifies whether UE-V displays an icon in the notification area and any notifications associated with it.</span></span> <span data-ttu-id="c8077-134">此圖示提供 [公司設定中心] 的連結。</span><span class="sxs-lookup"><span data-stu-id="c8077-134">The icon provides a link to the Company Settings Center.</span></span>

-   <span data-ttu-id="c8077-135">**自訂連絡人它的超連結：** 在 [公司設定中心] 中定義 [**連絡人 IT** ] 超連結的路徑、文字及描述。</span><span class="sxs-lookup"><span data-stu-id="c8077-135">**Custom Contact IT Hyperlink:** Defines the path, text, and description for the **Contact IT** hyperlink in the Company Settings Center.</span></span>






## <span data-ttu-id="c8077-136">相關主題</span><span class="sxs-lookup"><span data-stu-id="c8077-136">Related topics</span></span>


[<span data-ttu-id="c8077-137">管理 UE-V 2。</span><span class="sxs-lookup"><span data-stu-id="c8077-137">Administering UE-V 2.x</span></span>](administering-ue-v-2x-new-uevv2.md)

[<span data-ttu-id="c8077-138">部署 UE-V 2.x 的必要功能</span><span class="sxs-lookup"><span data-stu-id="c8077-138">Deploy Required Features for UE-V 2.x</span></span>](deploy-required-features-for-ue-v-2x-new-uevv2.md)

[<span data-ttu-id="c8077-139">部署自訂應用程式的 UE-V 2. x</span><span class="sxs-lookup"><span data-stu-id="c8077-139">Deploy UE-V 2.x for Custom Applications</span></span>](deploy-ue-v-2x-for-custom-applications-new-uevv2.md)

 

 





