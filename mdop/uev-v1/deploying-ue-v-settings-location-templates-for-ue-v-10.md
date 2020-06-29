---
title: 部署適用於 UE-V 1.0 的 UE-V 設定位置範本
description: 部署適用於 UE-V 1.0 的 UE-V 設定位置範本
author: dansimp
ms.assetid: 7e0cc553-14f7-40fa-828a-281c8d2d1934
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b276fb9d6c0b3749f9818483869dfe98bbc147c7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812165"
---
# <span data-ttu-id="16a70-103">部署適用於 UE-V 1.0 的 UE-V 設定位置範本</span><span class="sxs-lookup"><span data-stu-id="16a70-103">Deploying UE-V Settings Location Templates for UE-V 1.0</span></span>


<span data-ttu-id="16a70-104">Microsoft 使用者體驗虛擬化（UE-V）使用設定位置範本（XML 檔案），定義使用者體驗虛擬化所捕獲並套用的設定。</span><span class="sxs-lookup"><span data-stu-id="16a70-104">Microsoft User Experience Virtualization (UE-V) uses settings location templates (XML files) that define the settings that are captured and applied by User Experience Virtualization.</span></span> <span data-ttu-id="16a70-105">UE-V 包含一組標準範本，以及一個工具（即 UE-V 發生器），可讓您建立自訂設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="16a70-105">UE-V includes a set of standard templates, as well as a tool, the UE-V Generator, which allows you to create custom settings location templates.</span></span> <span data-ttu-id="16a70-106">在您建立設定位置範本之後，您應該對其進行測試，以確保應用程式設定能在測試環境中正確漫遊。</span><span class="sxs-lookup"><span data-stu-id="16a70-106">After you create a settings location template, you should test it to ensure that the application settings roam correctly in a test environment.</span></span> <span data-ttu-id="16a70-107">然後，您就可以將設定位置範本安全地部署到企業中的電腦上。</span><span class="sxs-lookup"><span data-stu-id="16a70-107">You can then safely deploy the settings location template to computers in the enterprise.</span></span>

<span data-ttu-id="16a70-108">您可以使用企業軟體發佈（ESD）、群組原則喜好設定或設定 UE-V 設定範本目錄來部署設定位置範本。</span><span class="sxs-lookup"><span data-stu-id="16a70-108">Settings location templates can be deployed by using enterprise software distribution (ESD), Group Policy preferences, or by configuring a UE-V settings template catalog.</span></span> <span data-ttu-id="16a70-109">使用 ESD 或群組原則部署的範本，必須透過 UE-V WMI 或 PowerShell 註冊。</span><span class="sxs-lookup"><span data-stu-id="16a70-109">Templates that are deployed by using an ESD or Group Policy must be registered through UE-V WMI or PowerShell.</span></span> <span data-ttu-id="16a70-110">儲存在設定範本目錄位置的範本會自動由 UE-V agent 進行註冊。</span><span class="sxs-lookup"><span data-stu-id="16a70-110">Templates that are stored in the settings template catalog location are automatically registered by the UE-V agent.</span></span>

## <span data-ttu-id="16a70-111">使用設定範本目錄路徑部署設定位置範本</span><span class="sxs-lookup"><span data-stu-id="16a70-111">Deploy the settings location templates with a settings template catalog path</span></span>


<span data-ttu-id="16a70-112">UE-V 設定位置範本目錄路徑可以使用下列方法來定義：群組原則、代理安裝命令列參數、WMI 或 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="16a70-112">The UE-V settings location template catalog path can be defined by using the following methods: Group Policy, the agent install command-line parameters, WMI, or PowerShell.</span></span> <span data-ttu-id="16a70-113">在定義範本目錄路徑之後，UE-V agent 就會從這個位置檢索新的或更新的範本。</span><span class="sxs-lookup"><span data-stu-id="16a70-113">After the template catalog path has been defined, the UE-V agent retrieves the new or updated templates from this location.</span></span> <span data-ttu-id="16a70-114">UE-V agent 每天都會檢查這個位置，然後根據在這個資料夾中找到的範本，更新其同步處理行為。</span><span class="sxs-lookup"><span data-stu-id="16a70-114">The UE-V agent checks this location once each day and updates its synchronization behavior based on the templates found in this folder.</span></span> <span data-ttu-id="16a70-115">在此資料夾中新增或更新的範本，自上次檢查之後，由 UE-V agent 註冊。</span><span class="sxs-lookup"><span data-stu-id="16a70-115">Templates that have been added or updated in this folder since the last check are registered by the UE-V agent.</span></span> <span data-ttu-id="16a70-116">UE-V agent 也會登出已從該資料夾移除的範本。</span><span class="sxs-lookup"><span data-stu-id="16a70-116">The UE-V agent also unregisters templates that have been removed from this folder.</span></span> <span data-ttu-id="16a70-117">範本是由任務排程器每日登錄並取消註冊一次。</span><span class="sxs-lookup"><span data-stu-id="16a70-117">Templates are registered and unregistered one time per day by the task scheduler.</span></span>

**<span data-ttu-id="16a70-118">若要使用設定範本目錄路徑來部署 UE-V 設定位置範本</span><span class="sxs-lookup"><span data-stu-id="16a70-118">To use settings template catalog path to deploy UE-V settings location templates</span></span>**

1.  <span data-ttu-id="16a70-119">流覽至定義為 [設定] 範本目錄的網路共用資料夾。</span><span class="sxs-lookup"><span data-stu-id="16a70-119">Navigate to the network share folder that is defined as the settings template catalog.</span></span>

2.  <span data-ttu-id="16a70-120">在設定範本目錄中新增、移除或更新設定位置範本，以反映 UE-V 電腦的所需 UE-V agent 範本配置。</span><span class="sxs-lookup"><span data-stu-id="16a70-120">Add, remove, or update settings location templates in the settings template catalog to reflect the desired UE-V agent template configuration for UE-V computers.</span></span>

3.  <span data-ttu-id="16a70-121">電腦上的範本會根據設定範本目錄的變更，每日更新一次。</span><span class="sxs-lookup"><span data-stu-id="16a70-121">Templates on computers are updated daily based on changes to the settings template catalog.</span></span>

4.  <span data-ttu-id="16a70-122">開啟提升許可權的命令提示字元，然後流覽到 **% program files%\\Microsoft 使用者體驗虛擬化 \\ agent \\ &lt; x86 &gt; 或 x64 **，然後執行**ApplySettingsTemplateCatalog.exe** ，在執行 ue-v agent 的電腦上手動更新範本。</span><span class="sxs-lookup"><span data-stu-id="16a70-122">Open an elevated command prompt and navigate to **%program files%\\Microsoft user Experience Virtualization \\ Agent \\ &lt;x86 or x64 &gt;**, and then run **ApplySettingsTemplateCatalog.exe** to manually update templates on a computer that runs the UE-V agent.</span></span>

## <span data-ttu-id="16a70-123">相關主題</span><span class="sxs-lookup"><span data-stu-id="16a70-123">Related topics</span></span>


[<span data-ttu-id="16a70-124">Microsoft User Experience Virtualization (UE-V) 1.0</span><span class="sxs-lookup"><span data-stu-id="16a70-124">Microsoft User Experience Virtualization (UE-V) 1.0</span></span>](index.md)

[<span data-ttu-id="16a70-125">部署 UE-V 1.0</span><span class="sxs-lookup"><span data-stu-id="16a70-125">Deploying UE-V 1.0</span></span>](deploying-ue-v-10.md)

[<span data-ttu-id="16a70-126">規劃要與 UE-V 1.0 同步處理的應用程式</span><span class="sxs-lookup"><span data-stu-id="16a70-126">Planning Which Applications to Synchronize with UE-V 1.0</span></span>](planning-which-applications-to-synchronize-with-ue-v-10.md)

 

 





