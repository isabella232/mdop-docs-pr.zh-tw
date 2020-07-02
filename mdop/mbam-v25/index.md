---
title: Microsoft BitLocker Administration and Monitoring 2.5
description: Microsoft BitLocker Administration and Monitoring 2.5
author: dansimp
ms.assetid: fd81d7de-b166-47e8-b6c7-d984830762b6
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 04/19/2017
ms.openlocfilehash: 2e5243131853207f0ed3cbb6d0cd8fb8e3d56108
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10795506"
---
# <span data-ttu-id="f2f4d-103">Microsoft BitLocker Administration and Monitoring 2.5</span><span class="sxs-lookup"><span data-stu-id="f2f4d-103">Microsoft BitLocker Administration and Monitoring 2.5</span></span>

<span data-ttu-id="f2f4d-104">Microsoft BitLocker 管理和監控（MBAM）2.5 提供簡化的管理介面，您可以用來管理 BitLocker 磁碟機加密。</span><span class="sxs-lookup"><span data-stu-id="f2f4d-104">Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 provides a simplified administrative interface that you can use to manage BitLocker Drive Encryption.</span></span> <span data-ttu-id="f2f4d-105">您可以設定 MBAM 群組原則範本，讓您設定適合您企業的 BitLocker 磁片磁碟機加密原則選項，然後使用這些範本來監視用戶端是否符合這些原則。</span><span class="sxs-lookup"><span data-stu-id="f2f4d-105">You configure MBAM Group Policy Templates that enable you to set BitLocker Drive Encryption policy options that are appropriate for your enterprise, and then use them to monitor client compliance with those policies.</span></span> <span data-ttu-id="f2f4d-106">您也可以針對個別電腦和企業整體，報告其加密狀態。</span><span class="sxs-lookup"><span data-stu-id="f2f4d-106">You can also report on the encryption status of an individual computer and on the enterprise as a whole.</span></span> <span data-ttu-id="f2f4d-107">此外，您也可以在使用者忘記 PIN 或密碼或其 BIOS 或開機記錄變更時，存取復原金鑰資訊。</span><span class="sxs-lookup"><span data-stu-id="f2f4d-107">In addition, you can access recovery key information when users forget their PIN or password or when their BIOS or boot record changes.</span></span> <span data-ttu-id="f2f4d-108">如需 MBAM 的詳細說明，請參閱[關於 MBAM 2.5](about-mbam-25.md)。</span><span class="sxs-lookup"><span data-stu-id="f2f4d-108">For a more detailed description of MBAM, see [About MBAM 2.5](about-mbam-25.md).</span></span>

<span data-ttu-id="f2f4d-109">若要取得 MBAM，請參閱[如何取得 MDOP](https://docs.microsoft.com/microsoft-desktop-optimization-pack/index#how-to-get-mdop)。</span><span class="sxs-lookup"><span data-stu-id="f2f4d-109">To obtain MBAM, see [How Do I Get MDOP](https://docs.microsoft.com/microsoft-desktop-optimization-pack/index#how-to-get-mdop).</span></span>

## <span data-ttu-id="f2f4d-110">大綱</span><span class="sxs-lookup"><span data-stu-id="f2f4d-110">Outline</span></span>

- <a href="" id="getting-started-with-mbam-2-5"></a>[<span data-ttu-id="f2f4d-111">開始使用 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="f2f4d-111">Getting Started with MBAM 2.5</span></span>](getting-started-with-mbam-25.md)
  - [<span data-ttu-id="f2f4d-112">關於 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="f2f4d-112">About MBAM 2.5</span></span>](about-mbam-25.md)
  - [<span data-ttu-id="f2f4d-113">MBAM 2.5 版本資訊</span><span class="sxs-lookup"><span data-stu-id="f2f4d-113">Release Notes for MBAM 2.5</span></span>](release-notes-for-mbam-25.md)
  - [<span data-ttu-id="f2f4d-114">關於 MBAM 2.5 SP1</span><span class="sxs-lookup"><span data-stu-id="f2f4d-114">About MBAM 2.5 SP1</span></span>](about-mbam-25-sp1.md)
  - [<span data-ttu-id="f2f4d-115">MBAM 2.5 SP1 版本資訊</span><span class="sxs-lookup"><span data-stu-id="f2f4d-115">Release Notes for MBAM 2.5 SP1</span></span>](release-notes-for-mbam-25-sp1.md)
  - [<span data-ttu-id="f2f4d-116">在測試環境中評估 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="f2f4d-116">Evaluating MBAM 2.5 in a Test Environment</span></span>](evaluating-mbam-25-in-a-test-environment.md)
  - [<span data-ttu-id="f2f4d-117">MBAM 2.5 的概要架構</span><span class="sxs-lookup"><span data-stu-id="f2f4d-117">High-Level Architecture for MBAM 2.5</span></span>](high-level-architecture-for-mbam-25.md)
  - [<span data-ttu-id="f2f4d-118">MBAM 2.5 的協助工具</span><span class="sxs-lookup"><span data-stu-id="f2f4d-118">Accessibility for MBAM 2.5</span></span>](accessibility-for-mbam-25.md)
- <a href="" id="planning-for-mbam-2-5"></a>[<span data-ttu-id="f2f4d-119">MBAM 2.5 規劃</span><span class="sxs-lookup"><span data-stu-id="f2f4d-119">Planning for MBAM 2.5</span></span>](planning-for-mbam-25.md)
  - [<span data-ttu-id="f2f4d-120">MBAM 2.5 的環境準備</span><span class="sxs-lookup"><span data-stu-id="f2f4d-120">Preparing your Environment for MBAM 2.5</span></span>](preparing-your-environment-for-mbam-25.md)
  - [<span data-ttu-id="f2f4d-121">MBAM 2.5 部署必要條件</span><span class="sxs-lookup"><span data-stu-id="f2f4d-121">MBAM 2.5 Deployment Prerequisites</span></span>](mbam-25-deployment-prerequisites.md)
  - [<span data-ttu-id="f2f4d-122">MBAM 2.5 群組原則需求規劃</span><span class="sxs-lookup"><span data-stu-id="f2f4d-122">Planning for MBAM 2.5 Group Policy Requirements</span></span>](planning-for-mbam-25-group-policy-requirements.md)
  - [<span data-ttu-id="f2f4d-123">MBAM 2.5 群組與帳戶規劃</span><span class="sxs-lookup"><span data-stu-id="f2f4d-123">Planning for MBAM 2.5 Groups and Accounts</span></span>](planning-for-mbam-25-groups-and-accounts.md)
  - [<span data-ttu-id="f2f4d-124">如何保護 MBAM 網站的規劃</span><span class="sxs-lookup"><span data-stu-id="f2f4d-124">Planning How to Secure the MBAM Websites</span></span>](planning-how-to-secure-the-mbam-websites.md)
  - [<span data-ttu-id="f2f4d-125">規劃部署 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="f2f4d-125">Planning to Deploy MBAM 2.5</span></span>](planning-to-deploy-mbam-25.md)
  - [<span data-ttu-id="f2f4d-126">MBAM 2.5 支援的組態</span><span class="sxs-lookup"><span data-stu-id="f2f4d-126">MBAM 2.5 Supported Configurations</span></span>](mbam-25-supported-configurations.md)
  - [<span data-ttu-id="f2f4d-127">MBAM 2.5 高可用性規劃</span><span class="sxs-lookup"><span data-stu-id="f2f4d-127">Planning for MBAM 2.5 High Availability</span></span>](planning-for-mbam-25-high-availability.md)
  - [<span data-ttu-id="f2f4d-128">MBAM 2.5 安全性考量</span><span class="sxs-lookup"><span data-stu-id="f2f4d-128">MBAM 2.5 Security Considerations</span></span>](mbam-25-security-considerations.md)
  - [<span data-ttu-id="f2f4d-129">MBAM 2.5 規劃檢查清單</span><span class="sxs-lookup"><span data-stu-id="f2f4d-129">MBAM 2.5 Planning Checklist</span></span>](mbam-25-planning-checklist.md)
- <a href="" id="deploying-mbam-2-5"></a>[<span data-ttu-id="f2f4d-130">部署 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="f2f4d-130">Deploying MBAM 2.5</span></span>](deploying-mbam-25.md)
  - [<span data-ttu-id="f2f4d-131">部署 MBAM 2.5 伺服器基礎結構</span><span class="sxs-lookup"><span data-stu-id="f2f4d-131">Deploying the MBAM 2.5 Server Infrastructure</span></span>](deploying-the-mbam-25-server-infrastructure.md)
  - [<span data-ttu-id="f2f4d-132">部署 MBAM 2.5 群組原則物件</span><span class="sxs-lookup"><span data-stu-id="f2f4d-132">Deploying MBAM 2.5 Group Policy Objects</span></span>](deploying-mbam-25-group-policy-objects.md)
  - [<span data-ttu-id="f2f4d-133">部署 MBAM 2.5 用戶端</span><span class="sxs-lookup"><span data-stu-id="f2f4d-133">Deploying the MBAM 2.5 Client</span></span>](deploying-the-mbam-25-client.md)
  - [<span data-ttu-id="f2f4d-134">MBAM 2.5 部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="f2f4d-134">MBAM 2.5 Deployment Checklist</span></span>](mbam-25-deployment-checklist.md)
  - [<span data-ttu-id="f2f4d-135">從舊版升級至 MBAM 2.5 或 MBAM 2.5 SP1</span><span class="sxs-lookup"><span data-stu-id="f2f4d-135">Upgrading to MBAM 2.5 or MBAM 2.5 SP1 from Previous Versions</span></span>](upgrading-to-mbam-25-or-mbam-25-sp1-from-previous-versions.md)
  - [<span data-ttu-id="f2f4d-136">移除 MBAM 伺服器功能或軟體</span><span class="sxs-lookup"><span data-stu-id="f2f4d-136">Removing MBAM Server Features or Software</span></span>](removing-mbam-server-features-or-software.md)
- <a href="" id="operations-for-mbam-2-5"></a>[<span data-ttu-id="f2f4d-137">適用於 MBAM 2.5 的操作</span><span class="sxs-lookup"><span data-stu-id="f2f4d-137">Operations for MBAM 2.5</span></span>](operations-for-mbam-25.md)
  - [<span data-ttu-id="f2f4d-138">管理 MBAM 2.5 功能</span><span class="sxs-lookup"><span data-stu-id="f2f4d-138">Administering MBAM 2.5 Features</span></span>](administering-mbam-25-features.md)
  - [<span data-ttu-id="f2f4d-139">使用 MBAM 2.5 監視與報告 BitLocker 符合性</span><span class="sxs-lookup"><span data-stu-id="f2f4d-139">Monitoring and Reporting BitLocker Compliance with MBAM 2.5</span></span>](monitoring-and-reporting-bitlocker-compliance-with-mbam-25.md)
  - [<span data-ttu-id="f2f4d-140">使用 MBAM 2.5 執行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="f2f4d-140">Performing BitLocker Management with MBAM 2.5</span></span>](performing-bitlocker-management-with-mbam-25.md)
  - [<span data-ttu-id="f2f4d-141">維護 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="f2f4d-141">Maintaining MBAM 2.5</span></span>](maintaining-mbam-25.md)
  - [<span data-ttu-id="f2f4d-142">使用 Windows PowerShell 管理 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="f2f4d-142">Using Windows PowerShell to Administer MBAM 2.5</span></span>](using-windows-powershell-to-administer-mbam-25.md)
- <a href="" id="troubleshooting-mbam-2-5"></a>[<span data-ttu-id="f2f4d-143">MBAM 2.5 疑難排解</span><span class="sxs-lookup"><span data-stu-id="f2f4d-143">Troubleshooting MBAM 2.5</span></span>](troubleshooting-mbam-25.md)
- <a href="" id="technical-reference-for-mbam-2-5"></a>[<span data-ttu-id="f2f4d-144">MBAM 2.5 技術參考資料</span><span class="sxs-lookup"><span data-stu-id="f2f4d-144">Technical Reference for MBAM 2.5</span></span>](technical-reference-for-mbam-25.md)
  - [<span data-ttu-id="f2f4d-145">用戶端事件記錄檔</span><span class="sxs-lookup"><span data-stu-id="f2f4d-145">Client Event Logs</span></span>](client-event-logs.md)
  - [<span data-ttu-id="f2f4d-146">伺服器事件記錄檔</span><span class="sxs-lookup"><span data-stu-id="f2f4d-146">Server Event Logs</span></span>](server-event-logs.md)

## <span data-ttu-id="f2f4d-147">其他資訊</span><span class="sxs-lookup"><span data-stu-id="f2f4d-147">More Information</span></span>

- [<span data-ttu-id="f2f4d-148">MDOP 資訊體驗</span><span class="sxs-lookup"><span data-stu-id="f2f4d-148">MDOP Information Experience</span></span>](index.md)

  <span data-ttu-id="f2f4d-149">尋找您的 MDOP 技術的檔、影片及其他資源。</span><span class="sxs-lookup"><span data-stu-id="f2f4d-149">Find documentation, videos, and other resources for MDOP technologies.</span></span>

- [<span data-ttu-id="f2f4d-150">MBAM 部署指南</span><span class="sxs-lookup"><span data-stu-id="f2f4d-150">MBAM Deployment Guide</span></span>](https://www.microsoft.com/download/details.aspx?id=38398)

  <span data-ttu-id="f2f4d-151">取得為 MBAM 選擇部署方法的說明，包括每個方法的逐步指示。</span><span class="sxs-lookup"><span data-stu-id="f2f4d-151">Get help in choosing a deployment method for MBAM, including step-by-step instructions for each method.</span></span>
    
- [<span data-ttu-id="f2f4d-152">在 MBAM 2.5 SP1 伺服器上套用熱修復程式</span><span class="sxs-lookup"><span data-stu-id="f2f4d-152">Apply Hotfixes on MBAM 2.5 SP1 Server</span></span>](apply-hotfix-for-mbam-25-sp1.md)

  <span data-ttu-id="f2f4d-153">如何套用 MBAM 2.5 SP1 Server 熱修復程式的指南</span><span class="sxs-lookup"><span data-stu-id="f2f4d-153">Guide of how to apply MBAM 2.5 SP1 Server hotfixes</span></span>
