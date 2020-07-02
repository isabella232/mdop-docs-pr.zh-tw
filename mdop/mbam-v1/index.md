---
title: Microsoft BitLocker 管理和監視1管理員指南
description: Microsoft BitLocker 管理和監視1管理員指南
author: dansimp
ms.assetid: 4086e721-db24-4439-bdcd-ac5ef901811f
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 04/19/2017
ms.openlocfilehash: 5336108e12738a21441df8062fbcd8bd98933945
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10795538"
---
# <span data-ttu-id="931c3-103">Microsoft BitLocker 管理和監視1管理員指南</span><span class="sxs-lookup"><span data-stu-id="931c3-103">Microsoft BitLocker Administration and Monitoring 1 Administrator's Guide</span></span>

<span data-ttu-id="931c3-104">Microsoft BitLocker 管理與監控（MBAM）提供簡化的管理介面，您可以用來管理 BitLocker 磁碟機加密。</span><span class="sxs-lookup"><span data-stu-id="931c3-104">Microsoft BitLocker Administration and Monitoring (MBAM) provides a simplified administrative interface that you can use to manage BitLocker drive encryption.</span></span> <span data-ttu-id="931c3-105">有了 MBAM，您就可以選取適合您企業的 BitLocker 加密原則選項，然後使用這些策略來監視用戶端是否符合這些原則。</span><span class="sxs-lookup"><span data-stu-id="931c3-105">With MBAM, you can select BitLocker encryption policy options that are appropriate to your enterprise and then use them to monitor client compliance with those policies.</span></span> <span data-ttu-id="931c3-106">您也可以報告個別電腦與整個企業的加密狀態。</span><span class="sxs-lookup"><span data-stu-id="931c3-106">You can also report on the encryption status of an individual computer and on the entire enterprise.</span></span> <span data-ttu-id="931c3-107">此外，您也可以在使用者忘記其 PIN 或密碼時，或當他們的 BIOS 或開機記錄變更時，存取復原金鑰資訊。</span><span class="sxs-lookup"><span data-stu-id="931c3-107">In addition, you can access recovery key information when users forget their PIN or password, or when their BIOS or boot record changes.</span></span>

- [<span data-ttu-id="931c3-108">開始使用 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="931c3-108">Getting Started with MBAM 1.0</span></span>](getting-started-with-mbam-10.md)  
  - [<span data-ttu-id="931c3-109">關於 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="931c3-109">About MBAM 1.0</span></span>](about-mbam-10.md)
  - [<span data-ttu-id="931c3-110">MBAM 1.0 版本資訊</span><span class="sxs-lookup"><span data-stu-id="931c3-110">Release Notes for MBAM 1.0</span></span>](release-notes-for-mbam-10.md)
  - [<span data-ttu-id="931c3-111">評估 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="931c3-111">Evaluating MBAM 1.0</span></span>](evaluating-mbam-10.md)
  - [<span data-ttu-id="931c3-112">MBAM 1.0 的高階架構</span><span class="sxs-lookup"><span data-stu-id="931c3-112">High Level Architecture for MBAM 1.0</span></span>](high-level-architecture-for-mbam-10.md)
  - [<span data-ttu-id="931c3-113">MBAM 1.0 的協助工具</span><span class="sxs-lookup"><span data-stu-id="931c3-113">Accessibility for MBAM 1.0</span></span>](accessibility-for-mbam-10.md)
  - [<span data-ttu-id="931c3-114">MBAM 1.0 隱私權聲明</span><span class="sxs-lookup"><span data-stu-id="931c3-114">Privacy Statement for MBAM 1.0</span></span>](privacy-statement-for-mbam-10.md)
- [<span data-ttu-id="931c3-115">MBAM 1.0 規劃</span><span class="sxs-lookup"><span data-stu-id="931c3-115">Planning for MBAM 1.0</span></span>](planning-for-mbam-10.md)  
  - [<span data-ttu-id="931c3-116">MBAM 1.0 的環境準備</span><span class="sxs-lookup"><span data-stu-id="931c3-116">Preparing your Environment for MBAM 1.0</span></span>](preparing-your-environment-for-mbam-10.md)
  - [<span data-ttu-id="931c3-117">MBAM 1.0 部署必要條件</span><span class="sxs-lookup"><span data-stu-id="931c3-117">MBAM 1.0 Deployment Prerequisites</span></span>](mbam-10-deployment-prerequisites.md)
  - [<span data-ttu-id="931c3-118">規劃部署 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="931c3-118">Planning to Deploy MBAM 1.0</span></span>](planning-to-deploy-mbam-10.md)
  - [<span data-ttu-id="931c3-119">MBAM 1.0 支援的組態</span><span class="sxs-lookup"><span data-stu-id="931c3-119">MBAM 1.0 Supported Configurations</span></span>](mbam-10-supported-configurations.md)
  - [<span data-ttu-id="931c3-120">MBAM 1.0 規劃檢查清單</span><span class="sxs-lookup"><span data-stu-id="931c3-120">MBAM 1.0 Planning Checklist</span></span>](mbam-10-planning-checklist.md)
- [<span data-ttu-id="931c3-121">部署 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="931c3-121">Deploying MBAM 1.0</span></span>](deploying-mbam-10.md)  
  - [<span data-ttu-id="931c3-122">部署 MBAM 1.0 伺服器基礎結構</span><span class="sxs-lookup"><span data-stu-id="931c3-122">Deploying the MBAM 1.0 Server Infrastructure</span></span>](deploying-the-mbam-10-server-infrastructure.md)
  - [<span data-ttu-id="931c3-123">部署 MBAM 1.0 群組原則物件</span><span class="sxs-lookup"><span data-stu-id="931c3-123">Deploying MBAM 1.0 Group Policy Objects</span></span>](deploying-mbam-10-group-policy-objects.md)
  - [<span data-ttu-id="931c3-124">部署 MBAM 1.0 用戶端</span><span class="sxs-lookup"><span data-stu-id="931c3-124">Deploying the MBAM 1.0 Client</span></span>](deploying-the-mbam-10-client.md)
  - [<span data-ttu-id="931c3-125">部署 MBAM 1.0 語言版本更新</span><span class="sxs-lookup"><span data-stu-id="931c3-125">Deploying the MBAM 1.0 Language Release Update</span></span>](deploying-the-mbam-10-language-release-update.md)
  - [<span data-ttu-id="931c3-126">MBAM 1.0 部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="931c3-126">MBAM 1.0 Deployment Checklist</span></span>](mbam-10-deployment-checklist.md)
- [<span data-ttu-id="931c3-127">適用於 MBAM 1.0 的操作</span><span class="sxs-lookup"><span data-stu-id="931c3-127">Operations for MBAM 1.0</span></span>](operations-for-mbam-10.md)  
  - [<span data-ttu-id="931c3-128">管理 MBAM 1.0 功能</span><span class="sxs-lookup"><span data-stu-id="931c3-128">Administering MBAM 1.0 Features</span></span>](administering-mbam-10-features.md)
  - [<span data-ttu-id="931c3-129">使用 MBAM 1.0 監視與報告 BitLocker 符合性</span><span class="sxs-lookup"><span data-stu-id="931c3-129">Monitoring and Reporting BitLocker Compliance with MBAM 1.0</span></span>](monitoring-and-reporting-bitlocker-compliance-with-mbam-10.md)
  - [<span data-ttu-id="931c3-130">使用 MBAM 執行 BitLocker 管理</span><span class="sxs-lookup"><span data-stu-id="931c3-130">Performing BitLocker Management with MBAM</span></span>](performing-bitlocker-management-with-mbam.md)
  - [<span data-ttu-id="931c3-131">使用 PowerShell 管理 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="931c3-131">Administering MBAM 1.0 by Using PowerShell</span></span>](administering-mbam-10-by-using-powershell.md)
- [<span data-ttu-id="931c3-132">MBAM 1.0 疑難排解</span><span class="sxs-lookup"><span data-stu-id="931c3-132">Troubleshooting MBAM 1.0</span></span>](troubleshooting-mbam-10.md)  

## <span data-ttu-id="931c3-133">其他資訊</span><span class="sxs-lookup"><span data-stu-id="931c3-133">More Information</span></span>
- [<span data-ttu-id="931c3-134">MDOP 資訊體驗</span><span class="sxs-lookup"><span data-stu-id="931c3-134">MDOP Information Experience</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=236032)  
  <span data-ttu-id="931c3-135">尋找您的 MDOP 技術的檔、影片及其他資源。</span><span class="sxs-lookup"><span data-stu-id="931c3-135">Find documentation, videos, and other resources for MDOP technologies.</span></span>
