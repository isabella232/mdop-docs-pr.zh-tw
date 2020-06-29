---
title: 部署 MBAM 1.0 用戶端
description: 部署 MBAM 1.0 用戶端
author: dansimp
ms.assetid: f7ca233f-5035-4ff9-ab3a-f2453b4929d1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dee8c2f4a9b398c9f0797ada35e4c36610c755b1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809633"
---
# <span data-ttu-id="0c75c-103">部署 MBAM 1.0 用戶端</span><span class="sxs-lookup"><span data-stu-id="0c75c-103">Deploying the MBAM 1.0 Client</span></span>


<span data-ttu-id="0c75c-104">Microsoft BitLocker 管理和監控（MBAM）用戶端可讓系統管理員在企業中的電腦上強制執行及監視 BitLocker 磁片磁碟機加密。</span><span class="sxs-lookup"><span data-stu-id="0c75c-104">The Microsoft BitLocker Administration and Monitoring (MBAM) Client enables administrators to enforce and monitor BitLocker drive encryption on computers in the enterprise.</span></span> <span data-ttu-id="0c75c-105">您可以透過使用 Active Directory 網域服務之類的工具部署用戶端，或直接加密用戶端電腦（作為初始影像處理常式的一部分），將 BitLocker 用戶端整合到組織中。</span><span class="sxs-lookup"><span data-stu-id="0c75c-105">The BitLocker client can be integrated into an organization by deploying the client through tools like Active Directory Domain Services or by directly encrypting the client computers as part of the initial imaging process.</span></span>

<span data-ttu-id="0c75c-106">根據您部署 MBAM 用戶端的時機，您可以在您組織中的電腦上或在最終使用者接收電腦之前或之後啟用 BitLocker 加密。</span><span class="sxs-lookup"><span data-stu-id="0c75c-106">Depending on when you deploy the MBAM Client, you can enable BitLocker encryption on a computer in your organization either before or after the end user receives the computer.</span></span> <span data-ttu-id="0c75c-107">若要控制此時間，您可以使用企業軟體部署系統來設定 [群組原則] 並部署 MBAM 用戶端軟體。</span><span class="sxs-lookup"><span data-stu-id="0c75c-107">To control this timing, you configure Group Policy and deploy the MBAM Client software by using an enterprise software deployment system.</span></span>

<span data-ttu-id="0c75c-108">您可以在組織中使用其中一種或兩種方法。</span><span class="sxs-lookup"><span data-stu-id="0c75c-108">You can use either or both of these methods in your organization.</span></span> <span data-ttu-id="0c75c-109">如果您同時使用這兩種方法，就可以改善合規性、報告和金鑰復原支援。</span><span class="sxs-lookup"><span data-stu-id="0c75c-109">If you use both methods, you can improve compliance, reporting, and key recovery support.</span></span>

## <span data-ttu-id="0c75c-110">將 MBAM 用戶端部署到桌上型電腦或膝上型電腦</span><span class="sxs-lookup"><span data-stu-id="0c75c-110">Deploy the MBAM Client to desktop or laptop computers</span></span>


<span data-ttu-id="0c75c-111">在您設定好群組原則之後，您可以將 MBAM 用戶端安裝 Windows 安裝程式檔案部署至目的電腦。</span><span class="sxs-lookup"><span data-stu-id="0c75c-111">After you have configured Group Policy, you can deploy the MBAM Client installation Windows Installer files to target computers.</span></span> <span data-ttu-id="0c75c-112">您可以使用企業軟體部署系統產品（例如 Microsoft System Center 2012 Configuration Manager 或 Active Directory 網域服務）來執行此操作。</span><span class="sxs-lookup"><span data-stu-id="0c75c-112">You can do this by use of an enterprise software deployment system product like Microsoft System Center 2012 Configuration Manager or Active Directory Domain Services.</span></span> <span data-ttu-id="0c75c-113">兩個可用的 MBAM 用戶端安裝 Windows 安裝程式檔案是 MBAMClient-64bit.msi 並 MBAMClient-32bit.msi。</span><span class="sxs-lookup"><span data-stu-id="0c75c-113">The two available MBAM Client installation Windows Installer files are MBAMClient-64bit.msi and MBAMClient-32bit.msi.</span></span> <span data-ttu-id="0c75c-114">這些檔案是由 MBAM 軟體提供。</span><span class="sxs-lookup"><span data-stu-id="0c75c-114">These files are provided with the MBAM software.</span></span> <span data-ttu-id="0c75c-115">如需如何部署 MBAM 群組原則物件的詳細資訊，請參閱[部署 MBAM 1.0 群組原則物件](deploying-mbam-10-group-policy-objects.md)。</span><span class="sxs-lookup"><span data-stu-id="0c75c-115">For more information about how to deploy MBAM Group Policy Objects, see [Deploying MBAM 1.0 Group Policy Objects](deploying-mbam-10-group-policy-objects.md).</span></span>

[<span data-ttu-id="0c75c-116">如何將 MBAM 用戶端部署到桌上型電腦或膝上型電腦</span><span class="sxs-lookup"><span data-stu-id="0c75c-116">How to Deploy the MBAM Client to Desktop or Laptop Computers</span></span>](how-to-deploy-the-mbam-client-to-desktop-or-laptop-computers-mbam-1.md)

## <span data-ttu-id="0c75c-117">部署 MBAM 用戶端做為 Windows 部署的一部分</span><span class="sxs-lookup"><span data-stu-id="0c75c-117">Deploy the MBAM Client as part of a Windows deployment</span></span>


<span data-ttu-id="0c75c-118">在某些組織中，新的電腦會集中接收並設定。</span><span class="sxs-lookup"><span data-stu-id="0c75c-118">In some organizations, new computers are received and configured centrally.</span></span> <span data-ttu-id="0c75c-119">這種情況可讓系統管理員在任何使用者資料寫入電腦之前，安裝 MBAM 用戶端來管理每個電腦上的 BitLocker 加密。</span><span class="sxs-lookup"><span data-stu-id="0c75c-119">This situation enables administrators to install the MBAM Client to manage BitLocker encryption on each computer before any user data is written to the computer.</span></span> <span data-ttu-id="0c75c-120">這個方法可協助確保電腦正確地加密，因為系統管理員會執行動作，而不需要依靠最終使用者的動作。</span><span class="sxs-lookup"><span data-stu-id="0c75c-120">This approach helps to ensure that computers are properly encrypted because the administrator performs the action without reliance on end-user action.</span></span> <span data-ttu-id="0c75c-121">這個案例的主要假設是，在電腦傳送給使用者之前，組織的原則會安裝公司的 Windows 影像。</span><span class="sxs-lookup"><span data-stu-id="0c75c-121">A key assumption for this scenario is that the policy of the organization installs a corporate Windows image before the computer is delivered to the user.</span></span>

[<span data-ttu-id="0c75c-122">如何將 MBAM 用戶端部署為 Windows 部署的一部分</span><span class="sxs-lookup"><span data-stu-id="0c75c-122">How to Deploy the MBAM Client as Part of a Windows Deployment</span></span>](how-to-deploy-the-mbam-client-as-part-of-a-windows-deployment-mbam-1.md)

## <span data-ttu-id="0c75c-123">部署 MBAM 用戶端的其他資源</span><span class="sxs-lookup"><span data-stu-id="0c75c-123">Other resources for deploying the MBAM Client</span></span>


[<span data-ttu-id="0c75c-124">部署 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="0c75c-124">Deploying MBAM 1.0</span></span>](deploying-mbam-10.md)

[<span data-ttu-id="0c75c-125">MBAM 1.0 用戶端部署規劃</span><span class="sxs-lookup"><span data-stu-id="0c75c-125">Planning for MBAM 1.0 Client Deployment</span></span>](planning-for-mbam-10-client-deployment.md)

 

 





