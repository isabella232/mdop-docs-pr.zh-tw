---
title: 部署 MBAM 1.0 伺服器基礎結構
description: 部署 MBAM 1.0 伺服器基礎結構
author: dansimp
ms.assetid: 90529379-b70e-4c92-b188-3d7aaf1844af
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: de136db557233a097d95f47ef0a1bba5996798c5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811000"
---
# <span data-ttu-id="92fe3-103">部署 MBAM 1.0 伺服器基礎結構</span><span class="sxs-lookup"><span data-stu-id="92fe3-103">Deploying the MBAM 1.0 Server Infrastructure</span></span>


<span data-ttu-id="92fe3-104">您可以使用一到五台伺服器，在不同的設定中安裝 Microsoft BitLocker 管理和監控（MBAM）伺服器功能。</span><span class="sxs-lookup"><span data-stu-id="92fe3-104">You can install Microsoft BitLocker Administration and Monitoring (MBAM) Server features in different configurations by using one to five servers.</span></span> <span data-ttu-id="92fe3-105">一般來說，您應該針對生產環境使用三到五台伺服器的配置，視您的可伸縮性需求而定。</span><span class="sxs-lookup"><span data-stu-id="92fe3-105">Generally, you should use a configuration of three to five servers for production environments, depending on your scalability needs.</span></span> <span data-ttu-id="92fe3-106">如需 MBAM 和建議部署拓撲的效能伸縮性的詳細資訊，請參閱[MBAM 可伸縮性及高可用性指南白皮書](https://go.microsoft.com/fwlink/p/?LinkId=258314)。</span><span class="sxs-lookup"><span data-stu-id="92fe3-106">For more information about performance scalability of MBAM and recommended deployment topologies, see the [MBAM Scalability and High-Availability Guide White Paper](https://go.microsoft.com/fwlink/p/?LinkId=258314).</span></span>

## <span data-ttu-id="92fe3-107">在單一伺服器上部署所有 MBAM 1。0</span><span class="sxs-lookup"><span data-stu-id="92fe3-107">Deploy all MBAM 1.0 on a single server</span></span>


<span data-ttu-id="92fe3-108">在這個設定中，所有的 MBAM 功能都安裝在單一伺服器上。</span><span class="sxs-lookup"><span data-stu-id="92fe3-108">In this configuration, all MBAM features are installed on a single server.</span></span> <span data-ttu-id="92fe3-109">此 MBAM server 基礎結構的部署拓朴會支援最多 21000 MBAM 用戶端電腦。</span><span class="sxs-lookup"><span data-stu-id="92fe3-109">This deployment topology for MBAM server infrastructure will support up to 21,000 MBAM client computers.</span></span>

<span data-ttu-id="92fe3-110">**重要** 這個設定是受支援的，但我們建議僅供測試。</span><span class="sxs-lookup"><span data-stu-id="92fe3-110">**Important** This configuration is supported, but we recommend it for testing only.</span></span>

 

<span data-ttu-id="92fe3-111">本節中的程式說明在單一伺服器上完整安裝 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="92fe3-111">The procedures in this section describe the full installation of the MBAM features on a single server.</span></span>

[<span data-ttu-id="92fe3-112">如何在單一伺服器上安裝及設定 MBAM</span><span class="sxs-lookup"><span data-stu-id="92fe3-112">How to Install and Configure MBAM on a Single Server</span></span>](how-to-install-and-configure-mbam-on-a-single-server-mbam-1.md)

## <span data-ttu-id="92fe3-113">在分散式伺服器上部署 MBAM 1。0</span><span class="sxs-lookup"><span data-stu-id="92fe3-113">Deploy MBAM 1.0 on distributed servers</span></span>


<span data-ttu-id="92fe3-114">根據您的可伸縮性需求，MBAM 功能可以安裝在不同的設定中。</span><span class="sxs-lookup"><span data-stu-id="92fe3-114">MBAM features can be installed in different configurations, depending on your scalability needs.</span></span> <span data-ttu-id="92fe3-115">如需如何規劃 MBAM server 功能部署的詳細資訊，請參閱[規劃 MBAM 1.0 Server 部署](planning-for-mbam-10-server-deployment.md)。</span><span class="sxs-lookup"><span data-stu-id="92fe3-115">For more information about how to plan for MBAM server feature deployment, see [Planning for MBAM 1.0 Server Deployment](planning-for-mbam-10-server-deployment.md).</span></span>

<span data-ttu-id="92fe3-116">本節中的程式說明分散式伺服器上的 MBAM 功能完整安裝。</span><span class="sxs-lookup"><span data-stu-id="92fe3-116">The procedures in this section describe the full installation of the MBAM features on distributed servers.</span></span>

### <span data-ttu-id="92fe3-117">三台電腦配置</span><span class="sxs-lookup"><span data-stu-id="92fe3-117">Three-computer configuration</span></span>

<span data-ttu-id="92fe3-118">下圖顯示適用于 MBAM 的三台電腦部署拓撲。</span><span class="sxs-lookup"><span data-stu-id="92fe3-118">The following diagram displays the three-computer deployment topology for MBAM.</span></span> <span data-ttu-id="92fe3-119">我們建議在支援最多 55000 MBAM 用戶端的生產環境中，進行這種拓撲。</span><span class="sxs-lookup"><span data-stu-id="92fe3-119">We recommend this topology for production environments that support up to 55,000 MBAM Clients.</span></span>

![mbam 三台電腦部署拓朴](images/mbam-3-server.jpg)

<span data-ttu-id="92fe3-121">在此設定中，MBAM 功能安裝在下列配置中：</span><span class="sxs-lookup"><span data-stu-id="92fe3-121">In this configuration, MBAM features are installed in the following configuration:</span></span>

1.  <span data-ttu-id="92fe3-122">在伺服器上安裝了復原與硬體資料庫、合規性和審核資料庫，以及合規性和審核報告。</span><span class="sxs-lookup"><span data-stu-id="92fe3-122">Recovery and Hardware Database, Compliance and Audit Database, and Compliance and Audit Reports are installed on a server.</span></span>

2.  <span data-ttu-id="92fe3-123">系統會在伺服器上安裝 [管理和監控伺服器] 功能。</span><span class="sxs-lookup"><span data-stu-id="92fe3-123">Administration and Monitoring Server feature is installed on a server.</span></span>

3.  <span data-ttu-id="92fe3-124">MBAM 群組原則範本已安裝在能夠修改群群組原則物件（GPO）的電腦上。</span><span class="sxs-lookup"><span data-stu-id="92fe3-124">MBAM Group Policy template is installed on a computer that is capable of modifying Group Policy Objects (GPO).</span></span>

### <span data-ttu-id="92fe3-125">四電腦配置</span><span class="sxs-lookup"><span data-stu-id="92fe3-125">Four-computer configuration</span></span>

<span data-ttu-id="92fe3-126">下圖顯示適用于 MBAM 的四電腦部署拓撲。</span><span class="sxs-lookup"><span data-stu-id="92fe3-126">The following diagram displays the four-computer deployment topology for MBAM.</span></span> <span data-ttu-id="92fe3-127">我們建議在支援最多 110000 MBAM 用戶端的生產環境中，使用此拓朴。</span><span class="sxs-lookup"><span data-stu-id="92fe3-127">We recommended this topology for production environments that support up to 110,000 MBAM Clients.</span></span>

![mbam 四個電腦部署拓撲。](images/mbam-4-computer.jpg)

<span data-ttu-id="92fe3-129">在此設定中，MBAM 功能安裝在下列配置中：</span><span class="sxs-lookup"><span data-stu-id="92fe3-129">In this configuration, MBAM features are installed in the following configuration:</span></span>

1.  <span data-ttu-id="92fe3-130">在伺服器上安裝了復原與硬體資料庫、合規性和審核資料庫，以及合規性和審核報告。</span><span class="sxs-lookup"><span data-stu-id="92fe3-130">Recovery and Hardware Database, Compliance and Audit Database, and Compliance and Audit Reports are installed on a server.</span></span>

2.  <span data-ttu-id="92fe3-131">系統會在網路負載平衡（NLB）伺服器叢集中設定的伺服器上安裝 [管理和監控伺服器] 功能。</span><span class="sxs-lookup"><span data-stu-id="92fe3-131">Administration and Monitoring Server feature is installed on a server that is configured in a Network Load Balancing (NLB) Server Cluster.</span></span>

3.  <span data-ttu-id="92fe3-132">MBAM 群組原則範本是安裝在能夠修改群組原則物件的電腦上。</span><span class="sxs-lookup"><span data-stu-id="92fe3-132">MBAM Group Policy template is installed on a computer that is capable of modifying the Group Policy Objects.</span></span>

### <span data-ttu-id="92fe3-133">五台電腦配置</span><span class="sxs-lookup"><span data-stu-id="92fe3-133">Five-computer configuration</span></span>

<span data-ttu-id="92fe3-134">下圖顯示適用于 MBAM 的五台電腦部署拓撲。</span><span class="sxs-lookup"><span data-stu-id="92fe3-134">The following diagram displays the five-computer deployment topology for MBAM.</span></span> <span data-ttu-id="92fe3-135">我們建議在支援最多 135000 MBAM 用戶端的生產環境中，進行這種拓撲。</span><span class="sxs-lookup"><span data-stu-id="92fe3-135">We recommend this topology for production environments that support up to 135,000 MBAM Clients.</span></span>

![mbam 五台電腦部署拓撲。](images/mbam-5-computer.jpg)

<span data-ttu-id="92fe3-137">在此設定中，MBAM 功能安裝在下列配置中：</span><span class="sxs-lookup"><span data-stu-id="92fe3-137">In this configuration, MBAM features are installed in the following configuration:</span></span>

1.  <span data-ttu-id="92fe3-138">在伺服器上安裝復原和硬體資料庫。</span><span class="sxs-lookup"><span data-stu-id="92fe3-138">Recovery and Hardware Database is installed on a server.</span></span>

2.  <span data-ttu-id="92fe3-139">相容性與審計資料庫及合規性與審計報告都安裝在伺服器上。</span><span class="sxs-lookup"><span data-stu-id="92fe3-139">The Compliance and Audit Database and Compliance and Audit Reports are installed on a server.</span></span>

3.  <span data-ttu-id="92fe3-140">系統會在網路負載平衡（NLB）伺服器叢集中設定的伺服器上安裝 [管理和監控伺服器] 功能。</span><span class="sxs-lookup"><span data-stu-id="92fe3-140">Administration and Monitoring Server feature is installed on a server that is configured in a Network Load Balancing (NLB) Server Cluster.</span></span>

4.  <span data-ttu-id="92fe3-141">MBAM 群組原則範本已安裝在能夠修改群組原則物件的電腦上。</span><span class="sxs-lookup"><span data-stu-id="92fe3-141">MBAM Group Policy template is installed on a computer that is capable of modifying Group Policy Objects.</span></span>

[<span data-ttu-id="92fe3-142">如何在分散式伺服器上安裝及設定 MBAM</span><span class="sxs-lookup"><span data-stu-id="92fe3-142">How to Install and Configure MBAM on Distributed Servers</span></span>](how-to-install-and-configure-mbam-on-distributed-servers-mbam-1.md)

[<span data-ttu-id="92fe3-143">如何針對 MBAM 設定網路負載平衡</span><span class="sxs-lookup"><span data-stu-id="92fe3-143">How to Configure Network Load Balancing for MBAM</span></span>](how-to-configure-network-load-balancing-for-mbam.md)

## <span data-ttu-id="92fe3-144">MBAM 1.0 Server 功能部署的其他資源</span><span class="sxs-lookup"><span data-stu-id="92fe3-144">Other resources for MBAM 1.0 Server features deployment</span></span>


[<span data-ttu-id="92fe3-145">部署 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="92fe3-145">Deploying MBAM 1.0</span></span>](deploying-mbam-10.md)

 

 





