---
title: 規劃部署 MBAM 2.0
description: 規劃部署 MBAM 2.0
author: dansimp
ms.assetid: 2dc05fcd-aed9-4315-aeaf-92aaa9e0e955
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c7f065e52655212261dfe8b6b3f081f697142473
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811271"
---
# <span data-ttu-id="44ac3-103">規劃部署 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="44ac3-103">Planning to Deploy MBAM 2.0</span></span>


<span data-ttu-id="44ac3-104">在建立 Microsoft BitLocker 管理與監控（MBAM）的部署方案之前，您應該先考慮幾個不同的部署設定和先決條件。</span><span class="sxs-lookup"><span data-stu-id="44ac3-104">You should consider a number of different deployment configurations and prerequisites before you create your deployment plan for Microsoft BitLocker Administration and Monitoring (MBAM).</span></span> <span data-ttu-id="44ac3-105">本節包含可協助您收集必要資訊的資訊，以闡明最符合您的業務需求的部署方案。</span><span class="sxs-lookup"><span data-stu-id="44ac3-105">This section includes information that can help you gather the necessary information to formulate a deployment plan that best meets your business requirements.</span></span> <span data-ttu-id="44ac3-106">如果您是使用 Configuration Manager 拓撲安裝 MBAM，請參閱[規劃使用 Configuration Manager 部署 MBAM](planning-to-deploy-mbam-with-configuration-manager-2.md) ，以取得額外的規劃資訊。</span><span class="sxs-lookup"><span data-stu-id="44ac3-106">If you are installing MBAM with the Configuration Manager topology, see [Planning to Deploy MBAM with Configuration Manager](planning-to-deploy-mbam-with-configuration-manager-2.md) for additional planning information.</span></span>

## <span data-ttu-id="44ac3-107">查看 MBAM 2.0 支援的設定</span><span class="sxs-lookup"><span data-stu-id="44ac3-107">Review the MBAM 2.0 Supported Configurations</span></span>


<span data-ttu-id="44ac3-108">為 MBAM Server 和用戶端功能安裝準備好您的計算環境之後，請務必查看支援的設定，以確認您要安裝 MBAM 的電腦符合最低硬體與作業系統需求。</span><span class="sxs-lookup"><span data-stu-id="44ac3-108">After preparing your computing environment for the MBAM Server and Client feature installation, make sure that you review the Supported Configurations to confirm that the computers on which you are installing MBAM meet the minimum hardware and operating system requirements.</span></span> <span data-ttu-id="44ac3-109">如需 MBAM 部署必備元件的詳細資訊，請參閱[MBAM 2.0 部署必備元件](mbam-20-deployment-prerequisites-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="44ac3-109">For more information about MBAM deployment prerequisites, see [MBAM 2.0 Deployment Prerequisites](mbam-20-deployment-prerequisites-mbam-2.md).</span></span>

[<span data-ttu-id="44ac3-110">MBAM 2.0 支援的組態</span><span class="sxs-lookup"><span data-stu-id="44ac3-110">MBAM 2.0 Supported Configurations</span></span>](mbam-20-supported-configurations-mbam-2.md)

## <span data-ttu-id="44ac3-111">規劃 MBAM 2.0 Server 和用戶端部署</span><span class="sxs-lookup"><span data-stu-id="44ac3-111">Plan for MBAM 2.0 Server and Client Deployment</span></span>


<span data-ttu-id="44ac3-112">MBAM 伺服器基礎結構視企業的需求而定，可以安裝在一或多台伺服器電腦上的一組伺服器功能上。</span><span class="sxs-lookup"><span data-stu-id="44ac3-112">The MBAM Server infrastructure depends on a set of server features that can be installed on one or more server computers, based on the requirements of the enterprise.</span></span> <span data-ttu-id="44ac3-113">您可以在多個伺服器上以分散式配置來安裝這些功能。</span><span class="sxs-lookup"><span data-stu-id="44ac3-113">These features can be installed in a distributed configuration across multiple servers.</span></span>

<span data-ttu-id="44ac3-114">**記事** 只有在實驗室環境中，才建議在單一伺服器上進行 MBAM 安裝。</span><span class="sxs-lookup"><span data-stu-id="44ac3-114">**Note** An MBAM installation on a single server is recommended only for lab environments.</span></span>

 

<span data-ttu-id="44ac3-115">MBAM 用戶端可讓系統管理員在企業中的電腦上強制執行及監視 BitLocker 磁片磁碟機加密。</span><span class="sxs-lookup"><span data-stu-id="44ac3-115">The MBAM Client enables administrators to enforce and monitor BitLocker drive encryption on computers in the enterprise.</span></span> <span data-ttu-id="44ac3-116">您可以透過企業軟體傳送系統部署用戶端，或在用戶端電腦上安裝用戶端代理程式（作為初始影像處理常式的一部分），來將 BitLocker 用戶端整合到組織中。</span><span class="sxs-lookup"><span data-stu-id="44ac3-116">The BitLocker client can be integrated into an organization by deploying the client through an enterprise software delivery system or by installing the client agent on client computers as part of the initial imaging process.</span></span>

<span data-ttu-id="44ac3-117">有了 MBAM，您就可以在最終使用者接收電腦之前或使用 [群組原則] 之後，在您組織中的電腦上加密。</span><span class="sxs-lookup"><span data-stu-id="44ac3-117">With MBAM, you can encrypt a computer in your organization either before the end user receives the computer, or afterwards by using Group Policy.</span></span>

[<span data-ttu-id="44ac3-118">MBAM 2.0 伺服器部署規劃</span><span class="sxs-lookup"><span data-stu-id="44ac3-118">Planning for MBAM 2.0 Server Deployment</span></span>](planning-for-mbam-20-server-deployment-mbam-2.md)

[<span data-ttu-id="44ac3-119">MBAM 2.0 用戶端部署規劃</span><span class="sxs-lookup"><span data-stu-id="44ac3-119">Planning for MBAM 2.0 Client Deployment</span></span>](planning-for-mbam-20-client-deployment-mbam-2.md)

## <a href="" id="other-resources-for-mbam-planning-"></a><span data-ttu-id="44ac3-120">MBAM 規劃的其他資源</span><span class="sxs-lookup"><span data-stu-id="44ac3-120">Other Resources for MBAM Planning</span></span>


[<span data-ttu-id="44ac3-121">MBAM 2.0 規劃</span><span class="sxs-lookup"><span data-stu-id="44ac3-121">Planning for MBAM 2.0</span></span>](planning-for-mbam-20-mbam-2.md)

 

 





