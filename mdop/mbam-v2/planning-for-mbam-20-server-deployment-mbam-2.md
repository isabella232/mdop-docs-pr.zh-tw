---
title: MBAM 2.0 伺服器部署規劃
description: MBAM 2.0 伺服器部署規劃
author: dansimp
ms.assetid: b57f1a42-134f-4997-8697-7fbed08e2fc4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 57e6510556522dce029c958172bd89a361e06b83
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800137"
---
# <span data-ttu-id="d0e92-103">MBAM 2.0 伺服器部署規劃</span><span class="sxs-lookup"><span data-stu-id="d0e92-103">Planning for MBAM 2.0 Server Deployment</span></span>


<span data-ttu-id="d0e92-104">Microsoft BitLocker 管理與監視（MBAM）伺服器基礎結構，視企業的需求而定，可以安裝在一或多台伺服器電腦上的一組伺服器功能。</span><span class="sxs-lookup"><span data-stu-id="d0e92-104">The Microsoft BitLocker Administration and Monitoring (MBAM) server infrastructure depends on a set of server features that can be installed on one or more server computers, based on the requirements of the enterprise.</span></span> <span data-ttu-id="d0e92-105">如果您是使用 Configuration Manager 拓撲進行 Microsoft BitLocker 管理和監視，請參閱[規劃使用 Configuration Manager 部署 MBAM](planning-to-deploy-mbam-with-configuration-manager-2.md)。</span><span class="sxs-lookup"><span data-stu-id="d0e92-105">If you are installing Microsoft BitLocker Administration and Monitoring with the Configuration Manager topology, see [Planning to Deploy MBAM with Configuration Manager](planning-to-deploy-mbam-with-configuration-manager-2.md).</span></span>

<span data-ttu-id="d0e92-106">**記事** 建議在單一伺服器上安裝 Microsoft BitLocker 管理和監控，只適用于測試環境。</span><span class="sxs-lookup"><span data-stu-id="d0e92-106">**Note** Installations of Microsoft BitLocker Administration and Monitoring on a single server are recommended only for test environments.</span></span>

 

## <span data-ttu-id="d0e92-107">規劃 MBAM Server 部署</span><span class="sxs-lookup"><span data-stu-id="d0e92-107">Planning for MBAM Server Deployment</span></span>


<span data-ttu-id="d0e92-108">MBAM 伺服器部署的基礎結構包括下列功能：</span><span class="sxs-lookup"><span data-stu-id="d0e92-108">The infrastructure for an MBAM Server deployment includes the following features:</span></span>

-   <span data-ttu-id="d0e92-109">復原資料庫</span><span class="sxs-lookup"><span data-stu-id="d0e92-109">Recovery Database</span></span>

-   <span data-ttu-id="d0e92-110">合規性和審核資料庫</span><span class="sxs-lookup"><span data-stu-id="d0e92-110">Compliance and Audit Database</span></span>

-   <span data-ttu-id="d0e92-111">合規性與審計報告</span><span class="sxs-lookup"><span data-stu-id="d0e92-111">Compliance and Audit Reports</span></span>

-   <span data-ttu-id="d0e92-112">自助服務入口網站</span><span class="sxs-lookup"><span data-stu-id="d0e92-112">Self-Service Portal</span></span>

-   <span data-ttu-id="d0e92-113">管理和監控伺服器</span><span class="sxs-lookup"><span data-stu-id="d0e92-113">Administration and Monitoring Server</span></span>

-   <span data-ttu-id="d0e92-114">MBAM 群組原則範本</span><span class="sxs-lookup"><span data-stu-id="d0e92-114">MBAM Group Policy Template</span></span>

<span data-ttu-id="d0e92-115">您可以根據您的可伸縮性需求，在不同的設定中安裝 MBAM 伺服器資料庫和功能。</span><span class="sxs-lookup"><span data-stu-id="d0e92-115">MBAM Server databases and features can be installed in different configurations, depending on your scalability requirements.</span></span> <span data-ttu-id="d0e92-116">所有的 MBAM 伺服器功能都可以安裝在單一伺服器上，或是分佈在多個伺服器上。</span><span class="sxs-lookup"><span data-stu-id="d0e92-116">All MBAM Server features can be installed on a single server or distributed across multiple servers.</span></span> <span data-ttu-id="d0e92-117">我們建議您在生產環境中使用雙伺服器設定，不過，您也可以根據自己的計算需求，使用兩個伺服器的配置。</span><span class="sxs-lookup"><span data-stu-id="d0e92-117">We recommend that you use a two-server configuration for production environments, although configurations of two to four servers can also be used, depending on your computing requirements.</span></span>

<span data-ttu-id="d0e92-118">每個 MBAM 功能都有特定的先決條件。</span><span class="sxs-lookup"><span data-stu-id="d0e92-118">Each MBAM feature has specific prerequisites.</span></span> <span data-ttu-id="d0e92-119">如需伺服器功能必備元件和硬體及軟體需求的完整清單，請參閱[MBAM 2.0 部署先決條件](mbam-20-deployment-prerequisites-mbam-2.md)和[MBAM 2.0 支援](mbam-20-supported-configurations-mbam-2.md)的設定。</span><span class="sxs-lookup"><span data-stu-id="d0e92-119">For a full list of server feature prerequisites and hardware and software requirements, see [MBAM 2.0 Deployment Prerequisites](mbam-20-deployment-prerequisites-mbam-2.md) and [MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md).</span></span>

<span data-ttu-id="d0e92-120">除了伺服器相關的 MBAM 功能之外，伺服器安裝應用程式還包含 MBAM 群組原則範本。</span><span class="sxs-lookup"><span data-stu-id="d0e92-120">In addition to the server-related MBAM features, the Server Setup application includes an MBAM Group Policy template.</span></span> <span data-ttu-id="d0e92-121">範本包含您設定的群群組原則物件（GPO）設定，以管理企業中的 BitLocker 磁碟機加密。</span><span class="sxs-lookup"><span data-stu-id="d0e92-121">The template contains Group Policy Object (GPO) settings that you configure to manage BitLocker Drive Encryption in the enterprise.</span></span> <span data-ttu-id="d0e92-122">您可以在任何可執行群組原則管理主控台（GPMC）或高級群組原則管理（AGPM）的電腦上安裝此範本。</span><span class="sxs-lookup"><span data-stu-id="d0e92-122">You can install this template on any computer that can run the Group Policy Management Console (GPMC) or Advanced Group Policy Management (AGPM).</span></span>

<span data-ttu-id="d0e92-123">在您規劃 MBAM 伺服器部署時，請考慮 MBAM 中的 BitLocker 復原金鑰僅供單一使用，在修復金鑰到期後。</span><span class="sxs-lookup"><span data-stu-id="d0e92-123">As you plan the MBAM Server deployment, consider that BitLocker recovery keys in MBAM are intended for single use only, after which recovery keys expire.</span></span> <span data-ttu-id="d0e92-124">若要讓金鑰在使用之後過期，必須透過服務台入口網站或自助入口網站進行檢索。</span><span class="sxs-lookup"><span data-stu-id="d0e92-124">In order for the keys to expire after use, they must be retrieved through the Help Desk Portal or the Self-Service Portal.</span></span>

## <span data-ttu-id="d0e92-125">部署 MBAM 伺服器功能的順序</span><span class="sxs-lookup"><span data-stu-id="d0e92-125">Order of Deployment of MBAM Server Features</span></span>


<span data-ttu-id="d0e92-126">若要在多個伺服器上部署 MBAM 功能，您必須以下列順序安裝這些功能：</span><span class="sxs-lookup"><span data-stu-id="d0e92-126">To deploy MBAM features on multiple servers, you have to install the features in the following order:</span></span>

1.  <span data-ttu-id="d0e92-127">復原資料庫</span><span class="sxs-lookup"><span data-stu-id="d0e92-127">Recovery Database</span></span>

2.  <span data-ttu-id="d0e92-128">合規性和審核資料庫</span><span class="sxs-lookup"><span data-stu-id="d0e92-128">Compliance and Audit Database</span></span>

3.  <span data-ttu-id="d0e92-129">合規性審核與報告</span><span class="sxs-lookup"><span data-stu-id="d0e92-129">Compliance Audit and Reports</span></span>

4.  <span data-ttu-id="d0e92-130">自助服務入口網站</span><span class="sxs-lookup"><span data-stu-id="d0e92-130">Self-Service Portal</span></span>

5.  <span data-ttu-id="d0e92-131">管理和監控伺服器</span><span class="sxs-lookup"><span data-stu-id="d0e92-131">Administration and Monitoring Server</span></span>

6.  <span data-ttu-id="d0e92-132">MBAM 群組原則範本</span><span class="sxs-lookup"><span data-stu-id="d0e92-132">MBAM Group Policy Template</span></span>

<span data-ttu-id="d0e92-133">**記事** 追蹤安裝每個功能的電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="d0e92-133">**Note** Keep track of the names of the computers on which you install each feature.</span></span> <span data-ttu-id="d0e92-134">您必須在整個安裝過程中使用此資訊。</span><span class="sxs-lookup"><span data-stu-id="d0e92-134">You have to use this information throughout the installation process.</span></span> <span data-ttu-id="d0e92-135">您可以列印並使用部署檢查清單來協助進行這項工作。</span><span class="sxs-lookup"><span data-stu-id="d0e92-135">You can print and use a deployment checklist to assist in this effort.</span></span> <span data-ttu-id="d0e92-136">如需 MBAM 部署檢查清單的詳細資訊，請參閱[MBAM 2.0 部署檢查清單](mbam-20-deployment-checklist-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="d0e92-136">For more information about the MBAM Deployment Checklist, see [MBAM 2.0 Deployment Checklist](mbam-20-deployment-checklist-mbam-2.md).</span></span>

 

## <span data-ttu-id="d0e92-137">相關主題</span><span class="sxs-lookup"><span data-stu-id="d0e92-137">Related topics</span></span>


[<span data-ttu-id="d0e92-138">規劃部署 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="d0e92-138">Planning to Deploy MBAM 2.0</span></span>](planning-to-deploy-mbam-20-mbam-2.md)

[<span data-ttu-id="d0e92-139">部署 MBAM 2.0 伺服器基礎結構</span><span class="sxs-lookup"><span data-stu-id="d0e92-139">Deploying the MBAM 2.0 Server Infrastructure</span></span>](deploying-the-mbam-20-server-infrastructure-mbam-2.md)

 

 





