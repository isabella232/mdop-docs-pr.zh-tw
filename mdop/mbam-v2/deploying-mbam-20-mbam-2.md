---
title: 部署 MBAM 2.0
description: 部署 MBAM 2.0
author: dansimp
ms.assetid: 4b0eaf10-81b4-427e-9d43-eb833de935a3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ba4423de5306e1ca204ef3b9fd31424bb8f2630f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809975"
---
# <span data-ttu-id="dba55-103">部署 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="dba55-103">Deploying MBAM 2.0</span></span>


<span data-ttu-id="dba55-104">Microsoft BitLocker 管理與監控（MBAM）支援多種不同的部署配置。</span><span class="sxs-lookup"><span data-stu-id="dba55-104">Microsoft BitLocker Administration and Monitoring (MBAM) supports a number of different deployment configurations.</span></span> <span data-ttu-id="dba55-105">本節包含您應該考慮的資訊，讓您瞭解如何部署 MBAM 和逐步程式，以協助您成功執行必須在部署的不同階段完成的工作。</span><span class="sxs-lookup"><span data-stu-id="dba55-105">This section includes information that you should consider about the deployment of MBAM and step-by-step procedures to help you successfully perform the tasks that you must complete at different stages of your deployment.</span></span>

<span data-ttu-id="dba55-106">您可以在獨立拓朴中部署 MBAM，或使用與 Microsoft System Center Configuration Manager 2007 或 MicrosoftSystemCenter2012 ConfigurationManager 整合 MBAM 的拓撲。</span><span class="sxs-lookup"><span data-stu-id="dba55-106">You can deploy MBAM either in a Stand-alone topology, or with a topology that integrates MBAM with Microsoft System Center Configuration Manager 2007 or MicrosoftSystemCenter2012 ConfigurationManager.</span></span> <span data-ttu-id="dba55-107">如需使用 Configuration Manager 整合拓朴安裝 MBAM 的相關資訊，請參閱[使用 MBAM 與 Configuration manager](using-mbam-with-configuration-manager.md)。</span><span class="sxs-lookup"><span data-stu-id="dba55-107">For information about installing MBAM with the Configuration Manager integrated topology, see [Using MBAM with Configuration Manager](using-mbam-with-configuration-manager.md).</span></span>

## <span data-ttu-id="dba55-108">部署資訊</span><span class="sxs-lookup"><span data-stu-id="dba55-108">Deployment Information</span></span>


-   [<span data-ttu-id="dba55-109">部署 MBAM 2.0 伺服器基礎結構</span><span class="sxs-lookup"><span data-stu-id="dba55-109">Deploying the MBAM 2.0 Server Infrastructure</span></span>](deploying-the-mbam-20-server-infrastructure-mbam-2.md)

    <span data-ttu-id="dba55-110">本節說明不同的 MBAM 部署拓朴選項，以及如何使用 MBAM 安裝程式部署 MBAM 伺服器功能。</span><span class="sxs-lookup"><span data-stu-id="dba55-110">This section describes the different MBAM deployment topology options and how to use MBAM Setup to deploy MBAM Server features.</span></span>

-   [<span data-ttu-id="dba55-111">部署 MBAM 2.0 群組原則物件</span><span class="sxs-lookup"><span data-stu-id="dba55-111">Deploying MBAM 2.0 Group Policy Objects</span></span>](deploying-mbam-20-group-policy-objects-mbam-2.md)

    <span data-ttu-id="dba55-112">本節說明如何建立及部署 MBAM 群組原則物件，這些物件是在整個企業中管理 MBAM 用戶端和 BitLocker 加密原則所需的。</span><span class="sxs-lookup"><span data-stu-id="dba55-112">This section describes how to create and deploy MBAM Group Policy Objects that are required for managing MBAM Clients and BitLocker encryption policies throughout the enterprise.</span></span>

-   [<span data-ttu-id="dba55-113">部署 MBAM 2.0 用戶端</span><span class="sxs-lookup"><span data-stu-id="dba55-113">Deploying the MBAM 2.0 Client</span></span>](deploying-the-mbam-20-client-mbam-2.md)

    <span data-ttu-id="dba55-114">本節說明如何使用 MBAM 用戶端安裝程式檔案來部署 MBAM 用戶端軟體。</span><span class="sxs-lookup"><span data-stu-id="dba55-114">This section describes how to use the MBAM Client Installer files to deploy the MBAM Client software.</span></span>

-   [<span data-ttu-id="dba55-115">MBAM 2.0 部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="dba55-115">MBAM 2.0 Deployment Checklist</span></span>](mbam-20-deployment-checklist-mbam-2.md)

    <span data-ttu-id="dba55-116">本節提供可用於協助 MBAM 伺服器功能與 MBAM 用戶端部署的部署檢查清單。</span><span class="sxs-lookup"><span data-stu-id="dba55-116">This section provides a deployment checklist that can be used to assist in MBAM Server feature and MBAM Client deployment.</span></span>

-   [<span data-ttu-id="dba55-117">從舊版 MBAM 升級</span><span class="sxs-lookup"><span data-stu-id="dba55-117">Upgrading from Previous Versions of MBAM</span></span>](upgrading-from-previous-versions-of-mbam.md)

    <span data-ttu-id="dba55-118">本節提供從舊版升級 MBAM 的指示。</span><span class="sxs-lookup"><span data-stu-id="dba55-118">This section provides instructions for upgrading MBAM from previous versions.</span></span>

## <span data-ttu-id="dba55-119">部署 MBAM 的其他資源</span><span class="sxs-lookup"><span data-stu-id="dba55-119">Other Resources for Deploying MBAM</span></span>


[<span data-ttu-id="dba55-120">Microsoft BitLocker 管理和監視2管理員指南</span><span class="sxs-lookup"><span data-stu-id="dba55-120">Microsoft BitLocker Administration and Monitoring 2 Administrator's Guide</span></span>](index.md)

[<span data-ttu-id="dba55-121">開始使用 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="dba55-121">Getting Started with MBAM 2.0</span></span>](getting-started-with-mbam-20-mbam-2.md)

[<span data-ttu-id="dba55-122">MBAM 2.0 規劃</span><span class="sxs-lookup"><span data-stu-id="dba55-122">Planning for MBAM 2.0</span></span>](planning-for-mbam-20-mbam-2.md)

[<span data-ttu-id="dba55-123">適用於 MBAM 2.0 的操作</span><span class="sxs-lookup"><span data-stu-id="dba55-123">Operations for MBAM 2.0</span></span>](operations-for-mbam-20-mbam-2.md)

[<span data-ttu-id="dba55-124">MBAM 2.0 疑難排解</span><span class="sxs-lookup"><span data-stu-id="dba55-124">Troubleshooting MBAM 2.0</span></span>](troubleshooting-mbam-20-mbam-2.md)

 

 





