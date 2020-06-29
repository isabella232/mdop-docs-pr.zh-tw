---
title: 規劃部署 MBAM 2.5
description: 規劃部署 MBAM 2.5
author: dansimp
ms.assetid: 1343b80c-d87a-42e7-b912-e84ba997d7e3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2e955b426b00539aa2a4ef0b7c3a6650b05633a5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811907"
---
# <span data-ttu-id="e2b76-103">規劃部署 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="e2b76-103">Planning to Deploy MBAM 2.5</span></span>


<span data-ttu-id="e2b76-104">在建立 Microsoft BitLocker 管理與監控（MBAM）的部署方案之前，您應該先考慮幾個不同的部署設定和先決條件。</span><span class="sxs-lookup"><span data-stu-id="e2b76-104">You should consider a number of different deployment configurations and prerequisites before you create your deployment plan for Microsoft BitLocker Administration and Monitoring (MBAM).</span></span> <span data-ttu-id="e2b76-105">本節包含可協助您收集必要資訊的資訊，以闡明最符合您的業務需求的部署方案。</span><span class="sxs-lookup"><span data-stu-id="e2b76-105">This section includes information that can help you gather the necessary information to formulate a deployment plan that best meets your business requirements.</span></span>

## <span data-ttu-id="e2b76-106">查看 MBAM 2.5 支援的設定</span><span class="sxs-lookup"><span data-stu-id="e2b76-106">Review the MBAM 2.5 supported configurations</span></span>


<span data-ttu-id="e2b76-107">針對 MBAM Server 和用戶端功能部署準備好您的計算環境之後，請務必查看支援的設定，以確認您要安裝 MBAM 的電腦符合最低硬體與作業系統需求。</span><span class="sxs-lookup"><span data-stu-id="e2b76-107">After preparing your computing environment for the MBAM Server and Client feature deployment, make sure that you review the Supported Configurations to confirm that the computers on which you are installing MBAM meet the minimum hardware and operating system requirements.</span></span> <span data-ttu-id="e2b76-108">如需 MBAM 部署必備元件的詳細資訊，請參閱[MBAM 2.5 部署必備元件](mbam-25-deployment-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="e2b76-108">For more information about MBAM deployment prerequisites, see [MBAM 2.5 Deployment Prerequisites](mbam-25-deployment-prerequisites.md).</span></span>

[<span data-ttu-id="e2b76-109">MBAM 2.5 支援的組態</span><span class="sxs-lookup"><span data-stu-id="e2b76-109">MBAM 2.5 Supported Configurations</span></span>](mbam-25-supported-configurations.md)

## <span data-ttu-id="e2b76-110">規劃 MBAM 2.5 Server 和用戶端部署</span><span class="sxs-lookup"><span data-stu-id="e2b76-110">Plan for MBAM 2.5 Server and Client deployment</span></span>


<span data-ttu-id="e2b76-111">MBAM 伺服器基礎結構依賴一組伺服器功能，可根據企業的需求，在一或多台伺服器電腦上進行設定。</span><span class="sxs-lookup"><span data-stu-id="e2b76-111">The MBAM Server infrastructure depends on a set of server features that can be configured on one or more server computers, based on the requirements of the enterprise.</span></span> <span data-ttu-id="e2b76-112">您可以在多個伺服器的分散式配置中設定這些功能。</span><span class="sxs-lookup"><span data-stu-id="e2b76-112">These features can be configured in a distributed configuration across multiple servers.</span></span>

<span data-ttu-id="e2b76-113">**記事** 只有在實驗室環境中，才建議在單一伺服器上進行 MBAM 安裝。</span><span class="sxs-lookup"><span data-stu-id="e2b76-113">**Note** An MBAM installation on a single server is recommended only for lab environments.</span></span>

 

<span data-ttu-id="e2b76-114">MBAM 用戶端可讓系統管理員在企業中的電腦上強制執行及監視 BitLocker 磁片磁碟機加密。</span><span class="sxs-lookup"><span data-stu-id="e2b76-114">The MBAM Client enables administrators to enforce and monitor BitLocker drive encryption on computers in the enterprise.</span></span> <span data-ttu-id="e2b76-115">您可以透過企業軟體傳送系統部署用戶端，或在用戶端電腦上將用戶端安裝為初始影像處理常式的一部分，將 BitLocker 用戶端整合到組織中。</span><span class="sxs-lookup"><span data-stu-id="e2b76-115">The BitLocker client can be integrated into an organization by deploying the client through an enterprise software delivery system or by installing the Client on client computers as part of the initial imaging process.</span></span>

<span data-ttu-id="e2b76-116">有了 MBAM，您就可以在最終使用者接收電腦之前或使用 [群組原則] 之後，在您組織中的電腦上加密。</span><span class="sxs-lookup"><span data-stu-id="e2b76-116">With MBAM, you can encrypt a computer in your organization either before the end user receives the computer, or afterwards by using Group Policy.</span></span>

[<span data-ttu-id="e2b76-117">MBAM 2.5 伺服器部署規劃</span><span class="sxs-lookup"><span data-stu-id="e2b76-117">Planning for MBAM 2.5 Server Deployment</span></span>](planning-for-mbam-25-server-deployment.md)

[<span data-ttu-id="e2b76-118">MBAM 2.5 用戶端部署規劃</span><span class="sxs-lookup"><span data-stu-id="e2b76-118">Planning for MBAM 2.5 Client Deployment</span></span>](planning-for-mbam-25-client-deployment.md)

## <a href="" id="other-resources-for-mbam-planning-"></a><span data-ttu-id="e2b76-119">MBAM 規劃的其他資源</span><span class="sxs-lookup"><span data-stu-id="e2b76-119">Other resources for MBAM planning</span></span>


[<span data-ttu-id="e2b76-120">MBAM 2.5 規劃</span><span class="sxs-lookup"><span data-stu-id="e2b76-120">Planning for MBAM 2.5</span></span>](planning-for-mbam-25.md)

## <span data-ttu-id="e2b76-121">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="e2b76-121">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="e2b76-122">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="e2b76-122">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="e2b76-123">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="e2b76-123">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>

 

 





