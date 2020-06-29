---
title: 為 UE-V 組態方法進行規劃
description: 為 UE-V 組態方法進行規劃
author: dansimp
ms.assetid: 57bce7ab-1be5-434b-9ee5-c96026bbe010
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4894644d72392ae984d0de290bf634e137d5b85e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812147"
---
# <span data-ttu-id="1a19c-103">為 UE-V 組態方法進行規劃</span><span class="sxs-lookup"><span data-stu-id="1a19c-103">Planning for UE-V Configuration Methods</span></span>


<span data-ttu-id="1a19c-104">Microsoft 使用者體驗虛擬化（UE-V）設定決定如何在整個企業中同步處理設定。</span><span class="sxs-lookup"><span data-stu-id="1a19c-104">Microsoft User Experience Virtualization (UE-V) configurations determine how settings are synchronized throughout the enterprise.</span></span> <span data-ttu-id="1a19c-105">本主題描述如何建立 UE-V 設定，以協助您表述最符合您的業務需求的設定方案。</span><span class="sxs-lookup"><span data-stu-id="1a19c-105">This topic describes how UE-V configurations are created to help you formulate a configuration plan that best meets your business requirements.</span></span>

## <span data-ttu-id="1a19c-106">UE-V 的配置方法</span><span class="sxs-lookup"><span data-stu-id="1a19c-106">Configuration methods for UE-V</span></span>


<span data-ttu-id="1a19c-107">您可以在安裝代理程式之前、期間或之後設定 UE-V，視您使用的配置方法而定。</span><span class="sxs-lookup"><span data-stu-id="1a19c-107">You can configure UE-V before, during, or after agent installation, depending on the configuration method that you use.</span></span>

<span data-ttu-id="1a19c-108">**群組原則：** 現有的群組原則基礎結構可以用來設定 ue-v agent 部署之前或之後的 ue-v。</span><span class="sxs-lookup"><span data-stu-id="1a19c-108">**Group Policy:** existing Group Policy infrastructure can be used to configure UE-V before or after UE-V Agent deployment.</span></span> <span data-ttu-id="1a19c-109">UE-V ADMX 範本可提供通用 UE-V Agent 設定選項的集中管理，並包含設定 UE-V 同步處理的設定。</span><span class="sxs-lookup"><span data-stu-id="1a19c-109">The UE-V ADMX template enables the central management of common UE-V Agent configuration options, and it includes settings to configure UE-V synchronization.</span></span> <span data-ttu-id="1a19c-110">使用群組原則的網路環境可以預先配置 UE-V，以預期的代理部署。</span><span class="sxs-lookup"><span data-stu-id="1a19c-110">Network environments that use Group Policy can preconfigure UE-V in anticipation of agent deployment.</span></span>

[<span data-ttu-id="1a19c-111">使用群組原則物件來設定 UE-V</span><span class="sxs-lookup"><span data-stu-id="1a19c-111">Configuring UE-V with Group Policy Objects</span></span>](configuring-ue-v-with-group-policy-objects.md)

[<span data-ttu-id="1a19c-112">安裝 UE-V 群組原則 ADMX 範本</span><span class="sxs-lookup"><span data-stu-id="1a19c-112">Installing the UE-V Group Policy ADMX Templates</span></span>](installing-the-ue-v-group-policy-admx-templates.md)

<span data-ttu-id="1a19c-113">**命令列或批次腳本安裝：** 與 ue-v Agent 部署搭配使用的參數，可讓您設定多個 ue-v 設定。</span><span class="sxs-lookup"><span data-stu-id="1a19c-113">**Command-line or Batch Script Installation:** parameters that are used with the deployment of the UE-V Agent allow the configuration of many UE-V settings.</span></span> <span data-ttu-id="1a19c-114">電子軟體發佈系統（例如系統中心建構管理員），在部署並安裝 UE-V Agent 軟體時，請使用這些參數來設定用戶端。</span><span class="sxs-lookup"><span data-stu-id="1a19c-114">Electronic software distribution systems, such as System Center Configuration Manager, use these parameters to configure their clients when deploying and installing the UE-V Agent software.</span></span> <span data-ttu-id="1a19c-115">如需安裝參數及範例安裝腳本的清單，請參閱[部署 Ue-v Agent](deploying-the-ue-v-agent.md)。</span><span class="sxs-lookup"><span data-stu-id="1a19c-115">For a list of installation parameters and sample installation scripts, see [Deploying the UE-V Agent](deploying-the-ue-v-agent.md).</span></span>

<span data-ttu-id="1a19c-116">**PowerShell 與 wmi：** 使用 POWERSHELL 或 wmi 的腳本式命令可在已安裝 ue-v agent 之後，用來修改設定。</span><span class="sxs-lookup"><span data-stu-id="1a19c-116">**PowerShell and WMI:** scripted commands using PowerShell or WMI can be used to modify configurations after the UE-V Agent has been installed.</span></span> <span data-ttu-id="1a19c-117">如需 PowerShell 與 WMI 命令的清單，請參閱[使用 PowerShell 和 Wmi 管理 ue-v 1.0 Agent 和套件](managing-the-ue-v-10-agent-and-packages-with-powershell-and-wmi.md)。</span><span class="sxs-lookup"><span data-stu-id="1a19c-117">For a list of PowerShell and WMI commands, see [Managing the UE-V 1.0 Agent and Packages with PowerShell and WMI](managing-the-ue-v-10-agent-and-packages-with-powershell-and-wmi.md).</span></span>

<span data-ttu-id="1a19c-118">**編輯註冊表設定：** UE-V 設定會儲存在登錄中，而且可以使用任何可修改註冊表設定的工具（例如 RegEdit）來修改。</span><span class="sxs-lookup"><span data-stu-id="1a19c-118">**Edit Registry Settings:** UE-V settings are stored in the registry and can be modified by using any tool that can modify registry settings, such as RegEdit.</span></span>

<span data-ttu-id="1a19c-119">**記事** 註冊表修改可能導致資料遺失或電腦變慢。</span><span class="sxs-lookup"><span data-stu-id="1a19c-119">**Note** Registry modification can result in data loss or the computer becoming unresponsive.</span></span> <span data-ttu-id="1a19c-120">建議您使用其他配置方法。</span><span class="sxs-lookup"><span data-stu-id="1a19c-120">We recommend that you use other configuration methods.</span></span>

 

### <span data-ttu-id="1a19c-121">UE-V 設定</span><span class="sxs-lookup"><span data-stu-id="1a19c-121">UE-V configuration settings</span></span>

<span data-ttu-id="1a19c-122">下列是 UE-V 設定的範例：</span><span class="sxs-lookup"><span data-stu-id="1a19c-122">The following are examples of UE-V configuration settings:</span></span>

-   <span data-ttu-id="1a19c-123">**設定儲存路徑：** 指定儲存 ue-v 設定的檔案共用位置。</span><span class="sxs-lookup"><span data-stu-id="1a19c-123">**Setting Storage Path:** specifies the location of the file share that stores the UE-V settings.</span></span>

-   <span data-ttu-id="1a19c-124">**設定範本目錄路徑：** 指定通用命名慣例（UNC）路徑，該路徑定義已針對新設定位置範本檢查的位置。</span><span class="sxs-lookup"><span data-stu-id="1a19c-124">**Settings Template Catalog Path:** specifies the Universal Naming Convention (UNC) path that defines the location that was checked for new settings location templates.</span></span>

-   <span data-ttu-id="1a19c-125">**註冊 Microsoft 範本：** 指定是否應在安裝期間註冊預設的 Microsoft 範本。</span><span class="sxs-lookup"><span data-stu-id="1a19c-125">**Register Microsoft Templates:** specifies whether the default Microsoft templates should be registered during installation.</span></span>

-   <span data-ttu-id="1a19c-126">**同步處理方法：** 指定是否要使用 Windows 離線檔案功能來進行離線支援。</span><span class="sxs-lookup"><span data-stu-id="1a19c-126">**Synchronization Method:** specifies whether the Windows Offline Files feature is used for offline support.</span></span>

-   <span data-ttu-id="1a19c-127">**同步處理超時：** 指定從 [設定] 儲存位置中檢索使用者設定時，電腦在超時前等待的毫秒數。</span><span class="sxs-lookup"><span data-stu-id="1a19c-127">**Synchronization Timeout:** specifies the number of milliseconds that the computer waits before timeout when retrieving the user settings from the settings storage location.</span></span>

-   <span data-ttu-id="1a19c-128">**啟用同步處理：** 指定是否已啟用或停用 ue-v 設定同步處理。</span><span class="sxs-lookup"><span data-stu-id="1a19c-128">**Synchronization Enable:** specifies whether the UE-V settings synchronization is enabled or disabled.</span></span>

-   <span data-ttu-id="1a19c-129">**最大套件大小：** 指定 ue-v agent 報告警告的設定套件檔閾值大小（以位元組為單位）。</span><span class="sxs-lookup"><span data-stu-id="1a19c-129">**Maximum Package Size:** specifies a settings package file threshold size in bytes at which the UE-V Agent reports a warning.</span></span>

## <span data-ttu-id="1a19c-130">相關主題</span><span class="sxs-lookup"><span data-stu-id="1a19c-130">Related topics</span></span>


[<span data-ttu-id="1a19c-131">為 UE-V 1.0 進行規劃</span><span class="sxs-lookup"><span data-stu-id="1a19c-131">Planning for UE-V 1.0</span></span>](planning-for-ue-v-10.md)

[<span data-ttu-id="1a19c-132">為 UE-V 組態進行規劃</span><span class="sxs-lookup"><span data-stu-id="1a19c-132">Planning for UE-V Configuration</span></span>](planning-for-ue-v-configuration.md)

 

 





