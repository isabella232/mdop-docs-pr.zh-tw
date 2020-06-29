---
title: 部署 MBAM 2.0 用戶端
description: 部署 MBAM 2.0 用戶端
author: dansimp
ms.assetid: 3dd584fe-2a54-40f0-9bab-13ea74040b01
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fa42c8ab3adc273f0e00ba56a59f487deba89c6f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809962"
---
# <span data-ttu-id="323da-103">部署 MBAM 2.0 用戶端</span><span class="sxs-lookup"><span data-stu-id="323da-103">Deploying the MBAM 2.0 Client</span></span>


<span data-ttu-id="323da-104">Microsoft BitLocker 管理和監控（MBAM）用戶端可讓系統管理員在企業中的電腦上強制執行及監視 BitLocker 磁片磁碟機加密。</span><span class="sxs-lookup"><span data-stu-id="323da-104">The Microsoft BitLocker Administration and Monitoring (MBAM) Client enables administrators to enforce and monitor BitLocker drive encryption on computers in the enterprise.</span></span> <span data-ttu-id="323da-105">您可以透過電子軟體發佈系統（例如 Active Directory 網域服務）部署用戶端，或直接加密用戶端電腦做為初始影像程式的一部分，將 BitLocker 用戶端整合到組織中。</span><span class="sxs-lookup"><span data-stu-id="323da-105">The BitLocker client can be integrated into an organization by deploying the client through an electronic software distribution system, such as Active Directory Domain Services, or by directly encrypting the client computers as part of the initial imaging process.</span></span>

<span data-ttu-id="323da-106">根據您部署 Microsoft BitLocker 管理和監視用戶端的時機，您可以在最終使用者接收電腦前，或透過使用企業軟體部署系統來部署 MBAM 用戶端軟體，在組織中的電腦上啟用 BitLocker 加密。</span><span class="sxs-lookup"><span data-stu-id="323da-106">Depending on when you deploy the Microsoft BitLocker Administration and Monitoring Client, you can enable BitLocker encryption on a computer in your organization either before the end user receives the computer or afterwards by configuring Group Policy and deploying the MBAM Client software by using an enterprise software deployment system.</span></span>

## <span data-ttu-id="323da-107">將 MBAM 用戶端部署到桌上型電腦或膝上型電腦</span><span class="sxs-lookup"><span data-stu-id="323da-107">Deploy the MBAM Client to Desktop or Laptop Computers</span></span>


<span data-ttu-id="323da-108">設定群組原則之後，您可以使用企業軟體部署系統產品（例如 Microsoft System Center Configuration Manager 2012 或 Active Directory 網域服務），將 MBAM 用戶端安裝 Windows 安裝程式檔案部署至目的電腦。</span><span class="sxs-lookup"><span data-stu-id="323da-108">After configuring Group Policy, you can use an enterprise software deployment system product like Microsoft System Center Configuration Manager 2012 or Active Directory Domain Services to deploy the MBAM Client installation Windows Installer files to target computers.</span></span> <span data-ttu-id="323da-109">您可以使用32位或64位 MbamClientSetup.exe 檔案，或是使用 MBAM 軟體提供的32位或 64 MBAMClient.msi 檔案來部署用戶端。</span><span class="sxs-lookup"><span data-stu-id="323da-109">You can deploy the client by using either the 32-bit or 64-bit MbamClientSetup.exe files, or the 32-bit or 64-bit MBAMClient.msi files, which are provided with the MBAM software.</span></span> <span data-ttu-id="323da-110">如需有關部署 MBAM 群組原則物件的詳細資訊，請參閱[部署 MBAM 2.0 群組原則物件](deploying-mbam-20-group-policy-objects-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="323da-110">For more information about deploying MBAM Group Policy Objects, see [Deploying MBAM 2.0 Group Policy Objects](deploying-mbam-20-group-policy-objects-mbam-2.md).</span></span>

[<span data-ttu-id="323da-111">如何將 MBAM 用戶端部署到桌上型電腦或膝上型電腦</span><span class="sxs-lookup"><span data-stu-id="323da-111">How to Deploy the MBAM Client to Desktop or Laptop Computers</span></span>](how-to-deploy-the-mbam-client-to-desktop-or-laptop-computers-mbam-2.md)

## <span data-ttu-id="323da-112">部署 MBAM 用戶端做為 Windows 部署的一部分</span><span class="sxs-lookup"><span data-stu-id="323da-112">Deploy the MBAM Client as Part of a Windows Deployment</span></span>


<span data-ttu-id="323da-113">在已集中接收和設定電腦的組織中，您可以安裝 MBAM 用戶端，在每個電腦上管理 BitLocker 加密，然後再寫入任何使用者資料。</span><span class="sxs-lookup"><span data-stu-id="323da-113">In organizations where computers are received and configured centrally, you can install the MBAM Client to manage BitLocker encryption on each computer before any user data is written to it.</span></span> <span data-ttu-id="323da-114">此程式的優點是，每個電腦都是相容的 BitLocker 加密。</span><span class="sxs-lookup"><span data-stu-id="323da-114">The benefit of this process is that every computer is then BitLocker encryption compliant.</span></span> <span data-ttu-id="323da-115">這個方法不依賴使用者的動作，因為系統管理員已經將電腦加密。</span><span class="sxs-lookup"><span data-stu-id="323da-115">This method does not rely on user action because the administrator has already encrypted the computer.</span></span> <span data-ttu-id="323da-116">這個案例的主要假設是，在電腦傳送給使用者之前，組織的原則會安裝公司的 Windows 影像。</span><span class="sxs-lookup"><span data-stu-id="323da-116">A key assumption for this scenario is that the policy of the organization installs a corporate Windows image before the computer is delivered to the user.</span></span> <span data-ttu-id="323da-117">如果已將群組原則設定為需要 PIN，則會在使用者收到群組原則之後提示使用者設定 PIN。</span><span class="sxs-lookup"><span data-stu-id="323da-117">If the Group Policy has been configured to require a PIN, users are prompted to set a PIN after they receive the Group Policy.</span></span>

[<span data-ttu-id="323da-118">如何將 MBAM 用戶端部署為 Windows 部署的一部分</span><span class="sxs-lookup"><span data-stu-id="323da-118">How to Deploy the MBAM Client as Part of a Windows Deployment</span></span>](how-to-deploy-the-mbam-client-as-part-of-a-windows-deployment-mbam-2.md)

## <span data-ttu-id="323da-119">如何使用命令列安裝 MBAM 用戶端</span><span class="sxs-lookup"><span data-stu-id="323da-119">How to Use a Command Line to Install the MBAM Client</span></span>


<span data-ttu-id="323da-120">本節說明如何使用命令列來安裝 MBAM 用戶端。</span><span class="sxs-lookup"><span data-stu-id="323da-120">This section explains how to install the MBAM Client by using a command line.</span></span>

[<span data-ttu-id="323da-121">如何使用命令列安裝 MBAM 用戶端</span><span class="sxs-lookup"><span data-stu-id="323da-121">How to Use a Command Line to Install the MBAM Client</span></span>](how-to-use-a-command-line-to-install-the-mbam-client.md)

## <span data-ttu-id="323da-122">部署 MBAM 用戶端的其他資源</span><span class="sxs-lookup"><span data-stu-id="323da-122">Other Resources for Deploying the MBAM Client</span></span>


<span data-ttu-id="323da-123">[部署](deploying-mbam-20-mbam-2.md)[MBAM 2.0 用戶端部署的](planning-for-mbam-20-client-deployment-mbam-2.md)MBAM 2.0 規劃</span><span class="sxs-lookup"><span data-stu-id="323da-123">[Deploying MBAM 2.0](deploying-mbam-20-mbam-2.md)[Planning for MBAM 2.0 Client Deployment](planning-for-mbam-20-client-deployment-mbam-2.md)</span></span>

 

 





