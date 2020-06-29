---
title: 規劃 UE-V 1.0 的自訂範本部署
description: 規劃 UE-V 1.0 的自訂範本部署
author: dansimp
ms.assetid: be76fc9a-31ca-4290-af11-7640dcb87d50
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5d17f058bff452f88003ab4488daa7afa846f688
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802918"
---
# <span data-ttu-id="4dda6-103">規劃 UE-V 1.0 的自訂範本部署</span><span class="sxs-lookup"><span data-stu-id="4dda6-103">Planning for Custom Template Deployment for UE-V 1.0</span></span>


<span data-ttu-id="4dda6-104">Microsoft 使用者體驗虛擬化（UE-V）使用設定位置範本（XML 檔案）來定義由 UE-V 捕獲並套用的設定。</span><span class="sxs-lookup"><span data-stu-id="4dda6-104">Microsoft User Experience Virtualization (UE-V) uses settings location templates (XML files) that define the settings that are captured and applied by UE-V.</span></span> <span data-ttu-id="4dda6-105">您可以使用 UE-V 發生器來建立自訂設定位置範本，讓使用者可以漫遊除預設 UE-V 範本中所包含的應用程式以外的應用程式設定。</span><span class="sxs-lookup"><span data-stu-id="4dda6-105">You can use the UE-V Generator to create custom settings location templates that let users roam the settings of applications other than those that are included in the default UE-V templates.</span></span> <span data-ttu-id="4dda6-106">在您測試自訂範本以確保應用程式設定在測試環境中正確漫遊之後，您就可以將這些設定位置範本部署到企業中的電腦。</span><span class="sxs-lookup"><span data-stu-id="4dda6-106">After you test the custom template to ensure that the application settings roam correctly in a test environment, you can deploy these settings location templates to computers in the enterprise.</span></span>

<span data-ttu-id="4dda6-107">您可以使用現有的部署基礎結構（例如企業軟體發佈（ESD）、群組原則喜好設定或設定 UE-V 設定範本目錄，來部署您的自訂設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="4dda6-107">You can deploy your custom settings location templates with an existing deployment infrastructure, such as Enterprise Software Distribution (ESD), with Group Policy preferences, or by configuring a UE-V settings template catalog.</span></span> <span data-ttu-id="4dda6-108">使用 ESD 或群組原則部署的範本，必須使用 UE-V WMI 或 PowerShell 註冊。</span><span class="sxs-lookup"><span data-stu-id="4dda6-108">Templates that are deployed by using ESD or Group Policy must be registered with UE-V WMI or PowerShell.</span></span>

## <span data-ttu-id="4dda6-109">設定範本目錄</span><span class="sxs-lookup"><span data-stu-id="4dda6-109">Settings template catalog</span></span>


<span data-ttu-id="4dda6-110">使用者體驗虛擬化設定範本目錄是 UE-V 電腦或伺服器郵件區塊（SMB）網路共用上的資料夾路徑，可儲存所有的自訂設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="4dda6-110">The User Experience Virtualization settings template catalog is a folder path on UE-V computers or a Server Message Block (SMB) network share that stores all the custom settings location templates.</span></span> <span data-ttu-id="4dda6-111">UE-V agent 會從這個位置中檢索新的或更新的範本。</span><span class="sxs-lookup"><span data-stu-id="4dda6-111">The UE-V agent retrieves new or updated templates from this location.</span></span> <span data-ttu-id="4dda6-112">UE-V agent 每天都會檢查這個位置，並根據此資料夾中的範本更新其同步處理行為。</span><span class="sxs-lookup"><span data-stu-id="4dda6-112">The UE-V agent checks this location once each day and updates its synchronization behavior based on the templates in this folder.</span></span> <span data-ttu-id="4dda6-113">在資料夾最後一次檢查之後，在此資料夾中新增或更新的範本是由 UE-V agent 註冊。</span><span class="sxs-lookup"><span data-stu-id="4dda6-113">Templates that were added or updated in this folder since the last time that the folder was checked are registered by the UE-V agent.</span></span> <span data-ttu-id="4dda6-114">從這個資料夾移除的 UE-V agent deregisters 範本。</span><span class="sxs-lookup"><span data-stu-id="4dda6-114">The UE-V agent deregisters templates that are removed from this folder.</span></span> <span data-ttu-id="4dda6-115">根據預設，範本是在每天淩晨3:30 登錄並取消註冊一次。</span><span class="sxs-lookup"><span data-stu-id="4dda6-115">By default, templates are registered and unregistered one time per day at 3:30 A.M.</span></span> <span data-ttu-id="4dda6-116">[任務排程者] 的當地時間。</span><span class="sxs-lookup"><span data-stu-id="4dda6-116">local time by the task scheduler.</span></span> <span data-ttu-id="4dda6-117">如需 UE-V 任務的詳細資訊，請參閱[變更 Ue-v 排程任務的頻率](changing-the-frequency-of-ue-v-scheduled-tasks.md)。</span><span class="sxs-lookup"><span data-stu-id="4dda6-117">For more information about the UE-V tasks, see [Changing the Frequency of UE-V Scheduled Tasks](changing-the-frequency-of-ue-v-scheduled-tasks.md).</span></span>

<span data-ttu-id="4dda6-118">您可以使用 [安裝] 命令列選項、[群組原則]、[WMI] 或 [PowerShell] 來設定設定範本的目錄路徑。</span><span class="sxs-lookup"><span data-stu-id="4dda6-118">You can configure the settings template catalog path by using the install command-line options, Group Policy, WMI, or PowerShell.</span></span> <span data-ttu-id="4dda6-119">儲存在設定範本目錄路徑的範本會自動由排程的工作進行註冊和取消註冊。</span><span class="sxs-lookup"><span data-stu-id="4dda6-119">Templates that are stored at the settings template catalog path are automatically registered and unregistered by a scheduled task.</span></span> <span data-ttu-id="4dda6-120">您可以視需要自訂此排程任務。</span><span class="sxs-lookup"><span data-stu-id="4dda6-120">You can customize this scheduled task as needed.</span></span>

## <span data-ttu-id="4dda6-121">取代預設的 Microsoft 範本</span><span class="sxs-lookup"><span data-stu-id="4dda6-121">Replace the default Microsoft templates</span></span>


<span data-ttu-id="4dda6-122">UE-V agent 會安裝適用于常見 Microsoft 應用程式和 Windows 設定的預設設定位置範本組。</span><span class="sxs-lookup"><span data-stu-id="4dda6-122">The UE-V agent installs a default group of settings location templates for common Microsoft applications and Windows settings.</span></span> <span data-ttu-id="4dda6-123">如果您的企業需要這些範本的自訂版本，則可以將 UE-V agent 設定為使用設定範本目錄，然後您應該取代預設的 Microsoft 範本。</span><span class="sxs-lookup"><span data-stu-id="4dda6-123">If your enterprise needs customized versions of these templates, the UE-V agent can be configured to use a settings template catalog and you should then replace the default Microsoft templates.</span></span>

<span data-ttu-id="4dda6-124">在安裝 UE-V agent 期間，命令列參數， `RegisterMSTemplates` 可以用來停用預設 Microsoft 範本的註冊。</span><span class="sxs-lookup"><span data-stu-id="4dda6-124">During the installation of the UE-V agent, the command-line parameter, `RegisterMSTemplates`, can be used to disable the registration of the default Microsoft templates.</span></span> <span data-ttu-id="4dda6-125">如需如何設定 UE-V 參數的詳細資訊，請參閱[規劃 Ue-v 配置方法](planning-for-ue-v-configuration-methods.md)。</span><span class="sxs-lookup"><span data-stu-id="4dda6-125">For more information about how to set the UE-V parameters, see [Planning for UE-V Configuration Methods](planning-for-ue-v-configuration-methods.md).</span></span>

<span data-ttu-id="4dda6-126">當您使用群組原則來設定設定範本目錄路徑時，您可以選擇取代預設的 Microsoft 範本。</span><span class="sxs-lookup"><span data-stu-id="4dda6-126">When you use Group Policy to configure the settings template catalog path, you can choose to replace the default Microsoft templates.</span></span> <span data-ttu-id="4dda6-127">如果您將原則設定設定為取代預設的 Microsoft 範本，則會從電腦中刪除由 UE-V agent 所安裝的所有預設 Microsoft 範本，而且只會使用位於設定範本目錄中的範本。</span><span class="sxs-lookup"><span data-stu-id="4dda6-127">If you configure the policy settings to replace the default Microsoft templates, all of the default Microsoft templates that are installed by the UE-V agent will be deleted from the computer, and only the templates that are located in the settings template catalog will be used.</span></span> <span data-ttu-id="4dda6-128">UE-V Agent 設定設定 `RegisterMSTemplates` 必須設定為 true，才能覆寫預設的 Microsoft 範本。</span><span class="sxs-lookup"><span data-stu-id="4dda6-128">The UE-V Agent configuration setting `RegisterMSTemplates` must be set to true in order to override the default Microsoft template.</span></span>

<span data-ttu-id="4dda6-129">**記事** 如果您在啟用此原則設定後停用它，UE-V agent 將無法還原預設的 Microsoft 範本。</span><span class="sxs-lookup"><span data-stu-id="4dda6-129">**Note** If you disable this policy setting after it has been enabled, the UE-V agent will not restore the default Microsoft templates.</span></span>

 

<span data-ttu-id="4dda6-130">如果設定範本目錄中有使用與預設 Microsoft 範本相同的識別碼的自訂範本，而 UE-V agent 並未設定為取代預設的 Microsoft 範本，則會忽略目錄中的 Microsoft 範本。</span><span class="sxs-lookup"><span data-stu-id="4dda6-130">If there are customized templates in the settings template catalog that use the same ID as the default Microsoft templates, and the UE-V agent is not configured to replace the default Microsoft templates, the Microsoft templates in the catalog will be ignored.</span></span>

<span data-ttu-id="4dda6-131">您也可以使用 UE-V PowerShell 功能取代預設範本。</span><span class="sxs-lookup"><span data-stu-id="4dda6-131">You can also replace the default templates by using the UE-V PowerShell features.</span></span> <span data-ttu-id="4dda6-132">若要將預設的 Microsoft 範本替換成 PowerShell，請登出所有預設的 Microsoft 範本，然後註冊自訂範本。</span><span class="sxs-lookup"><span data-stu-id="4dda6-132">To replace the default Microsoft Template with PowerShell, unregister all of the default Microsoft templates, and then register the customized templates.</span></span>

<span data-ttu-id="4dda6-133">**記事** 即使為應用程式部署新的設定範本，仍會保留在 [設定] 儲存位置中的舊設定套件。</span><span class="sxs-lookup"><span data-stu-id="4dda6-133">**Note** Old settings packages remain in the settings storage location even if new settings templates are deployed for an application.</span></span> <span data-ttu-id="4dda6-134">這些套件不會由代理程式讀取，但它們不會自動刪除。</span><span class="sxs-lookup"><span data-stu-id="4dda6-134">These packages are not read by the agent, but neither are they automatically deleted.</span></span>

 

## <span data-ttu-id="4dda6-135">相關主題</span><span class="sxs-lookup"><span data-stu-id="4dda6-135">Related topics</span></span>


[<span data-ttu-id="4dda6-136">為 UE-V 1.0 進行規劃</span><span class="sxs-lookup"><span data-stu-id="4dda6-136">Planning for UE-V 1.0</span></span>](planning-for-ue-v-10.md)

[<span data-ttu-id="4dda6-137">規劃要與 UE-V 1.0 同步處理的應用程式</span><span class="sxs-lookup"><span data-stu-id="4dda6-137">Planning Which Applications to Synchronize with UE-V 1.0</span></span>](planning-which-applications-to-synchronize-with-ue-v-10.md)

[<span data-ttu-id="4dda6-138">為 UE-V 組態方法進行規劃</span><span class="sxs-lookup"><span data-stu-id="4dda6-138">Planning for UE-V Configuration Methods</span></span>](planning-for-ue-v-configuration-methods.md)

<span data-ttu-id="4dda6-139">規劃自訂範本部署</span><span class="sxs-lookup"><span data-stu-id="4dda6-139">Planning for Custom Template Deployment</span></span>
 

 





