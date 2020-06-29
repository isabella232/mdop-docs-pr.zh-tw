---
title: 規劃部署 MBAM 1.0
description: 規劃部署 MBAM 1.0
author: dansimp
ms.assetid: 30ad4304-45c6-427d-8e33-ebe8053c7871
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c2ff25e705717db5086150ed08a5640335bbacb8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809806"
---
# <span data-ttu-id="f0b69-103">規劃部署 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="f0b69-103">Planning to Deploy MBAM 1.0</span></span>


<span data-ttu-id="f0b69-104">在建立 Microsoft BitLocker 管理與監控（MBAM）1.0 部署方案之前，您應該先考慮幾個不同的部署設定和先決條件。</span><span class="sxs-lookup"><span data-stu-id="f0b69-104">You should consider a number of different deployment configurations and prerequisites before you create your Microsoft BitLocker Administration and Monitoring (MBAM) 1.0 deployment plan.</span></span> <span data-ttu-id="f0b69-105">本節包含可協助您收集資訊的資訊，這些資訊可協助您收集最符合您的業務需求的部署方案。</span><span class="sxs-lookup"><span data-stu-id="f0b69-105">This section includes information that can help you gather the information that you must have to formulate a deployment plan that best meets your business requirements.</span></span>

## <span data-ttu-id="f0b69-106">查看 MBAM 1.0 支援的設定</span><span class="sxs-lookup"><span data-stu-id="f0b69-106">Review the MBAM 1.0 supported configurations</span></span>


<span data-ttu-id="f0b69-107">在您為 MBAM 用戶端和伺服器功能安裝準備好計算環境之後，請務必查看 MBAM 支援的設定資訊，以確認您安裝 MBAM 的電腦符合最低硬體及作業系統需求。</span><span class="sxs-lookup"><span data-stu-id="f0b69-107">After you prepare your computing environment for the MBAM Client and Server feature installation, make sure that you review the Supported Configurations information for MBAM to confirm that the computers on which you install MBAM meet the minimum hardware and operating system requirements.</span></span> <span data-ttu-id="f0b69-108">如需 MBAM 部署必備元件的詳細資訊，請參閱[MBAM 1.0 部署必備元件](mbam-10-deployment-prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="f0b69-108">For more information about MBAM deployment prerequisites, see [MBAM 1.0 Deployment Prerequisites](mbam-10-deployment-prerequisites.md).</span></span>

[<span data-ttu-id="f0b69-109">MBAM 1.0 支援的組態</span><span class="sxs-lookup"><span data-stu-id="f0b69-109">MBAM 1.0 Supported Configurations</span></span>](mbam-10-supported-configurations.md)

## <span data-ttu-id="f0b69-110">規劃 MBAM 1.0 Server 和用戶端部署</span><span class="sxs-lookup"><span data-stu-id="f0b69-110">Plan for MBAM 1.0 Server and Client deployment</span></span>


<span data-ttu-id="f0b69-111">MBAM 伺服器基礎結構視企業的需求而定，可以安裝在一或多台伺服器電腦上的一組伺服器功能上。</span><span class="sxs-lookup"><span data-stu-id="f0b69-111">The MBAM server infrastructure depends on a set of server features that can be installed on one or more server computers, based on the requirements of the enterprise.</span></span> <span data-ttu-id="f0b69-112">這些功能可以安裝在單一伺服器上，或分佈在多個伺服器上。</span><span class="sxs-lookup"><span data-stu-id="f0b69-112">These features can be installed on a single server or distributed across multiple servers.</span></span>

<span data-ttu-id="f0b69-113">MBAM 用戶端可讓系統管理員在企業中的電腦上強制執行並監視 BitLocker 磁片磁碟機加密。</span><span class="sxs-lookup"><span data-stu-id="f0b69-113">The MBAM Client enables administrators to enforce and monitor the BitLocker drive encryption on computers in the enterprise.</span></span> <span data-ttu-id="f0b69-114">您可以透過使用 Active Directory 網域服務之類的工具部署用戶端，或直接加密用戶端電腦（作為初始影像處理常式的一部分），將 BitLocker 用戶端整合到組織中。</span><span class="sxs-lookup"><span data-stu-id="f0b69-114">The BitLocker client can be integrated into an organization by deploying the client through tools like Active Directory Domain Services or by directly encrypting the client computers as part of the initial imaging process.</span></span>

<span data-ttu-id="f0b69-115">有了 MBAM，您就可以使用群組原則，在最終使用者接收電腦之前或之後，在您的組織中加密電腦。</span><span class="sxs-lookup"><span data-stu-id="f0b69-115">With MBAM, you can encrypt a computer in your organization either before the end user receives the computer or afterwards, by using Group Policy.</span></span> <span data-ttu-id="f0b69-116">您可以在組織中使用一或兩個方法。</span><span class="sxs-lookup"><span data-stu-id="f0b69-116">You can use one or both methods in your organization.</span></span> <span data-ttu-id="f0b69-117">如果您選擇使用這兩種方法，就可以改善合規性、報告和金鑰復原支援。</span><span class="sxs-lookup"><span data-stu-id="f0b69-117">If you choose to use both methods, you can improve compliance, reporting, and key recovery support.</span></span>

[<span data-ttu-id="f0b69-118">MBAM 1.0 伺服器部署規劃</span><span class="sxs-lookup"><span data-stu-id="f0b69-118">Planning for MBAM 1.0 Server Deployment</span></span>](planning-for-mbam-10-server-deployment.md)

[<span data-ttu-id="f0b69-119">MBAM 1.0 用戶端部署規劃</span><span class="sxs-lookup"><span data-stu-id="f0b69-119">Planning for MBAM 1.0 Client Deployment</span></span>](planning-for-mbam-10-client-deployment.md)

## <a href="" id="other-resources-for-mbam-planning-"></a><span data-ttu-id="f0b69-120">MBAM 規劃的其他資源</span><span class="sxs-lookup"><span data-stu-id="f0b69-120">Other resources for MBAM planning</span></span>


-   [<span data-ttu-id="f0b69-121">MBAM 1.0 規劃</span><span class="sxs-lookup"><span data-stu-id="f0b69-121">Planning for MBAM 1.0</span></span>](planning-for-mbam-10.md)

 

 





