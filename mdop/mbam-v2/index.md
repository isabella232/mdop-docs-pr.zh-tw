---
title: Microsoft BitLocker 管理和監視2管理員指南
description: Microsoft BitLocker 管理和監視2管理員指南
author: dansimp
ms.assetid: fdb43f62-960a-4811-8802-50efdf04b4af
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 04/19/2017
ms.openlocfilehash: dd6deb6fb91c64ac8609b54114e0dd417497034a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10795534"
---
# <span data-ttu-id="e8f8c-103">Microsoft BitLocker 管理和監視2管理員指南</span><span class="sxs-lookup"><span data-stu-id="e8f8c-103">Microsoft BitLocker Administration and Monitoring 2 Administrator's Guide</span></span>

<span data-ttu-id="e8f8c-104">Microsoft BitLockerAdministration 和 Monitoring （MBAM）2.0 提供簡化的管理介面，您可以用來管理 BitLocker 磁碟機加密。</span><span class="sxs-lookup"><span data-stu-id="e8f8c-104">Microsoft BitLockerAdministration and Monitoring(MBAM)2.0 provides a simplified administrative interface that you can use to manage BitLocker drive encryption.</span></span> <span data-ttu-id="e8f8c-105">在 BitLockerAdministration 和監視2.0 中，您可以選取適合您企業的 BitLocker 磁片磁碟機加密原則選項，然後使用這些規則來監視用戶端是否符合這些原則。</span><span class="sxs-lookup"><span data-stu-id="e8f8c-105">In BitLockerAdministration and Monitoring2.0, you can select BitLocker drive encryption policy options that are appropriate for your enterprise, and then use them to monitor client compliance with those policies.</span></span> <span data-ttu-id="e8f8c-106">您也可以針對個別電腦和企業整體，報告其加密狀態。</span><span class="sxs-lookup"><span data-stu-id="e8f8c-106">You can also report on the encryption status of an individual computer and on the enterprise as a whole.</span></span> <span data-ttu-id="e8f8c-107">此外，您也可以在使用者忘記 PIN 或密碼或其 BIOS 或開機記錄變更時，存取復原金鑰資訊。</span><span class="sxs-lookup"><span data-stu-id="e8f8c-107">In addition, you can access recovery key information when users forget their PIN or password or when their BIOS or boot record changes.</span></span>

## <span data-ttu-id="e8f8c-108">大綱</span><span class="sxs-lookup"><span data-stu-id="e8f8c-108">Outline</span></span>

- [<span data-ttu-id="e8f8c-109">開始使用 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="e8f8c-109">Getting Started with MBAM 2.0</span></span>](getting-started-with-mbam-20-mbam-2.md)
  - [<span data-ttu-id="e8f8c-110">關於 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="e8f8c-110">About MBAM 2.0</span></span>](about-mbam-20-mbam-2.md)
  - [<span data-ttu-id="e8f8c-111">MBAM 2.0 版本資訊</span><span class="sxs-lookup"><span data-stu-id="e8f8c-111">Release Notes for MBAM 2.0</span></span>](release-notes-for-mbam-20-mbam-2.md)
  - [<span data-ttu-id="e8f8c-112">關於 MBAM 2.0 SP1</span><span class="sxs-lookup"><span data-stu-id="e8f8c-112">About MBAM 2.0 SP1</span></span>](about-mbam-20-sp1.md)
  - [<span data-ttu-id="e8f8c-113">MBAM 2.0 SP1 版本資訊</span><span class="sxs-lookup"><span data-stu-id="e8f8c-113">Release Notes for MBAM 2.0 SP1</span></span>](release-notes-for-mbam-20-sp1.md)
  - [<span data-ttu-id="e8f8c-114">評估 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="e8f8c-114">Evaluating MBAM 2.0</span></span>](evaluating-mbam-20-mbam-2.md)
  - [<span data-ttu-id="e8f8c-115">MBAM 2.0 的概要架構</span><span class="sxs-lookup"><span data-stu-id="e8f8c-115">High-Level Architecture for MBAM 2.0</span></span>](high-level-architecture-for-mbam-20-mbam-2.md)
  - [<span data-ttu-id="e8f8c-116">MBAM 2.0 的協助工具</span><span class="sxs-lookup"><span data-stu-id="e8f8c-116">Accessibility for MBAM 2.0</span></span>](accessibility-for-mbam-20-mbam-2.md)
- [<span data-ttu-id="e8f8c-117">MBAM 2.0 規劃</span><span class="sxs-lookup"><span data-stu-id="e8f8c-117">Planning for MBAM 2.0</span></span>](planning-for-mbam-20-mbam-2.md)
  - [<span data-ttu-id="e8f8c-118">MBAM 2.0 的環境準備</span><span class="sxs-lookup"><span data-stu-id="e8f8c-118">Preparing your Environment for MBAM 2.0</span></span>](preparing-your-environment-for-mbam-20-mbam-2.md)
  - [<span data-ttu-id="e8f8c-119">MBAM 2.0 部署必要條件</span><span class="sxs-lookup"><span data-stu-id="e8f8c-119">MBAM 2.0 Deployment Prerequisites</span></span>](mbam-20-deployment-prerequisites-mbam-2.md)
  - [<span data-ttu-id="e8f8c-120">規劃部署 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="e8f8c-120">Planning to Deploy MBAM 2.0</span></span>](planning-to-deploy-mbam-20-mbam-2.md)
  - [<span data-ttu-id="e8f8c-121">MBAM 2.0 支援的組態</span><span class="sxs-lookup"><span data-stu-id="e8f8c-121">MBAM 2.0 Supported Configurations</span></span>](mbam-20-supported-configurations-mbam-2.md)
  - [<span data-ttu-id="e8f8c-122">MBAM 2.0 規劃檢查清單</span><span class="sxs-lookup"><span data-stu-id="e8f8c-122">MBAM 2.0 Planning Checklist</span></span>](mbam-20-planning-checklist-mbam-2.md)
- [<span data-ttu-id="e8f8c-123">部署 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="e8f8c-123">Deploying MBAM 2.0</span></span>](deploying-mbam-20-mbam-2.md)
  - [<span data-ttu-id="e8f8c-124">部署 MBAM 2.0 伺服器基礎結構</span><span class="sxs-lookup"><span data-stu-id="e8f8c-124">Deploying the MBAM 2.0 Server Infrastructure</span></span>](deploying-the-mbam-20-server-infrastructure-mbam-2.md)
  - [<span data-ttu-id="e8f8c-125">部署 MBAM 2.0 群組原則物件</span><span class="sxs-lookup"><span data-stu-id="e8f8c-125">Deploying MBAM 2.0 Group Policy Objects</span></span>](deploying-mbam-20-group-policy-objects-mbam-2.md)
  - [<span data-ttu-id="e8f8c-126">部署 MBAM 2.0 用戶端</span><span class="sxs-lookup"><span data-stu-id="e8f8c-126">Deploying the MBAM 2.0 Client</span></span>](deploying-the-mbam-20-client-mbam-2.md)
  - [<span data-ttu-id="e8f8c-127">MBAM 2.0 部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="e8f8c-127">MBAM 2.0 Deployment Checklist</span></span>](mbam-20-deployment-checklist-mbam-2.md)
  - [<span data-ttu-id="e8f8c-128">從舊版 MBAM 升級</span><span class="sxs-lookup"><span data-stu-id="e8f8c-128">Upgrading from Previous Versions of MBAM</span></span>](upgrading-from-previous-versions-of-mbam.md)
- [<span data-ttu-id="e8f8c-129">適用於 MBAM 2.0 的操作</span><span class="sxs-lookup"><span data-stu-id="e8f8c-129">Operations for MBAM 2.0</span></span>](operations-for-mbam-20-mbam-2.md)
  - [<span data-ttu-id="e8f8c-130">使用 MBAM 搭配 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e8f8c-130">Using MBAM with Configuration Manager</span></span>](using-mbam-with-configuration-manager.md)
  - [<span data-ttu-id="e8f8c-131">管理 MBAM 2.0 功能</span><span class="sxs-lookup"><span data-stu-id="e8f8c-131">Administering MBAM 2.0 Features</span></span>](administering-mbam-20-features-mbam-2.md)
  - [<span data-ttu-id="e8f8c-132">使用 MBAM 2.0 監視與報告 BitLocker 符合性</span><span class="sxs-lookup"><span data-stu-id="e8f8c-132">Monitoring and Reporting BitLocker Compliance with MBAM 2.0</span></span>](monitoring-and-reporting-bitlocker-compliance-with-mbam-20-mbam-2.md)
  - [<span data-ttu-id="e8f8c-133">使用 MBAM 執行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="e8f8c-133">Performing BitLocker Management with MBAM</span></span>](performing-bitlocker-management-with-mbam-mbam-2.md)
  - [<span data-ttu-id="e8f8c-134">維護 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="e8f8c-134">Maintaining MBAM 2.0</span></span>](maintaining-mbam-20-mbam-2.md)
  - [<span data-ttu-id="e8f8c-135">MBAM 2.0 的安全性與隱私權</span><span class="sxs-lookup"><span data-stu-id="e8f8c-135">Security and Privacy for MBAM 2.0</span></span>](security-and-privacy-for-mbam-20-mbam-2.md)
  - [<span data-ttu-id="e8f8c-136">使用 PowerShell 管理 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="e8f8c-136">Administering MBAM 2.0 Using PowerShell</span></span>](administering-mbam-20-using-powershell-mbam-2.md)
- [<span data-ttu-id="e8f8c-137">MBAM 2.0 疑難排解</span><span class="sxs-lookup"><span data-stu-id="e8f8c-137">Troubleshooting MBAM 2.0</span></span>](troubleshooting-mbam-20-mbam-2.md)

## <span data-ttu-id="e8f8c-138">其他資訊</span><span class="sxs-lookup"><span data-stu-id="e8f8c-138">More Information</span></span>

- [<span data-ttu-id="e8f8c-139">MDOP 資訊體驗</span><span class="sxs-lookup"><span data-stu-id="e8f8c-139">MDOP Information Experience</span></span>](index.md)

  <span data-ttu-id="e8f8c-140">尋找您的 MDOP 技術的檔、影片及其他資源。</span><span class="sxs-lookup"><span data-stu-id="e8f8c-140">Find documentation, videos, and other resources for MDOP technologies.</span></span>

 

 





