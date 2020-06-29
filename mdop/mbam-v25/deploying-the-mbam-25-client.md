---
title: 部署 MBAM 2.5 用戶端
description: 部署 MBAM 2.5 用戶端
author: dansimp
ms.assetid: 0a96a0ee-f280-49d9-a244-88f4147fe9fd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 375af8966c8e66a58baec5065d065891187899fc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811660"
---
# <span data-ttu-id="3c908-103">部署 MBAM 2.5 用戶端</span><span class="sxs-lookup"><span data-stu-id="3c908-103">Deploying the MBAM 2.5 Client</span></span>


<span data-ttu-id="3c908-104">Microsoft BitLocker 管理和監控（MBAM）用戶端軟體可讓系統管理員在企業中的電腦上強制執行及監視 BitLocker 磁片磁碟機加密。</span><span class="sxs-lookup"><span data-stu-id="3c908-104">The Microsoft BitLocker Administration and Monitoring (MBAM) Client software enables administrators to enforce and monitor BitLocker Drive Encryption on computers in the enterprise.</span></span> <span data-ttu-id="3c908-105">您可以透過電子軟體發佈系統（例如 Active Directory 網域服務）部署用戶端，或直接加密用戶端電腦做為初始影像程式的一部分，將 BitLocker 用戶端整合到組織中。</span><span class="sxs-lookup"><span data-stu-id="3c908-105">The BitLocker client can be integrated into an organization by deploying the client through an electronic software distribution system, such as Active Directory Domain Services, or by directly encrypting the client computers as part of the initial imaging process.</span></span>

<span data-ttu-id="3c908-106">根據您部署 Microsoft BitLocker 管理和監視用戶端軟體的時間，您可以在最終使用者接收電腦之前，或透過使用企業軟體部署系統來部署 MBAM 用戶端軟體，在組織中的電腦上啟用 BitLocker 磁碟機加密。</span><span class="sxs-lookup"><span data-stu-id="3c908-106">Depending on when you deploy the Microsoft BitLocker Administration and Monitoring Client software, you can enable BitLocker Drive Encryption on a computer in your organization either before the end user receives the computer or afterwards by configuring Group Policy and deploying the MBAM Client software by using an enterprise software deployment system.</span></span>

## <span data-ttu-id="3c908-107">將 MBAM 用戶端部署到桌上型電腦或膝上型電腦</span><span class="sxs-lookup"><span data-stu-id="3c908-107">Deploy the MBAM Client to desktop or laptop computers</span></span>


<span data-ttu-id="3c908-108">在設定群組原則設定之後，您可以使用企業軟體部署系統產品（例如 MicrosoftSystemCenter2012 ConfigurationManager 或 Active Directory 網域服務），將 MBAM 用戶端安裝 Windows 安裝程式檔案部署至目的電腦。</span><span class="sxs-lookup"><span data-stu-id="3c908-108">After configuring Group Policy settings, you can use an enterprise software deployment system product like MicrosoftSystemCenter2012 ConfigurationManager or Active Directory Domain Services to deploy the MBAM Client installation Windows Installer files to target computers.</span></span> <span data-ttu-id="3c908-109">您可以使用32位或64位 MbamClientSetup.exe 檔案，或是32或 64 MBAMClient.msi 位的檔案，這些檔案是由 MBAM 用戶端軟體所提供。</span><span class="sxs-lookup"><span data-stu-id="3c908-109">You can use either the 32-bit or 64-bit MbamClientSetup.exe files or the 32-bit or 64-bit MBAMClient.msi files, which are provided with the MBAM Client software.</span></span> <span data-ttu-id="3c908-110">如需有關部署 MBAM 群組原則設定的詳細資訊，請參閱[部署 MBAM 2.5 群組原則物件](deploying-mbam-25-group-policy-objects.md)。</span><span class="sxs-lookup"><span data-stu-id="3c908-110">For more information about deploying MBAM Group Policy settings, see [Deploying MBAM 2.5 Group Policy Objects](deploying-mbam-25-group-policy-objects.md).</span></span>

<span data-ttu-id="3c908-111">**記事** 從 MBAM 2.5 SP1 開始，MBAM 產品不再隨附個別的 MSI。</span><span class="sxs-lookup"><span data-stu-id="3c908-111">**Note** Beginning in MBAM 2.5 SP1, a separate MSI is no longer included with the MBAM product.</span></span> <span data-ttu-id="3c908-112">不過，您可以從隨附于產品的可執行檔（.exe）中解壓縮 MSI。</span><span class="sxs-lookup"><span data-stu-id="3c908-112">However, you can extract the MSI from the executable file (.exe) that is included with the product.</span></span>

 

[<span data-ttu-id="3c908-113">如何將 MBAM 用戶端部署到桌上型電腦或膝上型電腦</span><span class="sxs-lookup"><span data-stu-id="3c908-113">How to Deploy the MBAM Client to Desktop or Laptop Computers</span></span>](how-to-deploy-the-mbam-client-to-desktop-or-laptop-computers-mbam-25.md)

## <span data-ttu-id="3c908-114">部署 MBAM 用戶端做為 Windows 部署的一部分</span><span class="sxs-lookup"><span data-stu-id="3c908-114">Deploy the MBAM Client as part of a Windows deployment</span></span>


<span data-ttu-id="3c908-115">在已集中接收和設定電腦的組織中，您可以安裝 MBAM 用戶端，在每個電腦上管理 BitLocker 磁碟機加密，然後再寫入任何使用者資料。</span><span class="sxs-lookup"><span data-stu-id="3c908-115">In organizations where computers are received and configured centrally, you can install the MBAM Client to manage BitLocker Drive Encryption on each computer before any user data is written to it.</span></span> <span data-ttu-id="3c908-116">此程式的優點是，每個電腦都是符合 BitLocker 磁片磁碟機加密規範的。</span><span class="sxs-lookup"><span data-stu-id="3c908-116">The benefit of this process is that every computer is then BitLocker Drive Encryption-compliant.</span></span> <span data-ttu-id="3c908-117">這個方法不依賴使用者的動作，因為系統管理員已經將電腦加密。</span><span class="sxs-lookup"><span data-stu-id="3c908-117">This method does not rely on user action because the administrator has already encrypted the computer.</span></span> <span data-ttu-id="3c908-118">這個案例的主要假設是，在電腦傳送給使用者之前，組織的原則會安裝公司的 Windows 影像。</span><span class="sxs-lookup"><span data-stu-id="3c908-118">A key assumption for this scenario is that the policy of the organization installs a corporate Windows image before the computer is delivered to the user.</span></span> <span data-ttu-id="3c908-119">如果已將群組原則設定設定為 [需要 PIN]，系統會在收到原則之後提示使用者設定 PIN。</span><span class="sxs-lookup"><span data-stu-id="3c908-119">If the Group Policy settings has been configured to require a PIN, users are prompted to set a PIN after they receive the policy.</span></span>

[<span data-ttu-id="3c908-120">如何使用 MBAM 做為 Windows 部署的一部分來啟用 BitLocker</span><span class="sxs-lookup"><span data-stu-id="3c908-120">How to Enable BitLocker by Using MBAM as Part of a Windows Deployment</span></span>](how-to-enable-bitlocker-by-using-mbam-as-part-of-a-windows-deploymentmbam-25.md)

## <span data-ttu-id="3c908-121">如何使用命令列部署 MBAM 用戶端</span><span class="sxs-lookup"><span data-stu-id="3c908-121">How to deploy the MBAM Client by using a command line</span></span>


<span data-ttu-id="3c908-122">本節說明如何使用命令列來安裝 MBAM 用戶端。</span><span class="sxs-lookup"><span data-stu-id="3c908-122">This section explains how to install the MBAM Client by using a command line.</span></span>

[<span data-ttu-id="3c908-123">如何使用命令列部署 MBAM 用戶端</span><span class="sxs-lookup"><span data-stu-id="3c908-123">How to Deploy the MBAM Client by Using a Command Line</span></span>](how-to-deploy-the-mbam-client-by-using-a-command-line.md)

## <span data-ttu-id="3c908-124">部署 MBAM 用戶端的其他資源</span><span class="sxs-lookup"><span data-stu-id="3c908-124">Other resources for deploying the MBAM Client</span></span>


[<span data-ttu-id="3c908-125">部署 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="3c908-125">Deploying MBAM 2.5</span></span>](deploying-mbam-25.md)



## <span data-ttu-id="3c908-126">相關主題</span><span class="sxs-lookup"><span data-stu-id="3c908-126">Related topics</span></span>


[<span data-ttu-id="3c908-127">部署 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="3c908-127">Deploying MBAM 2.5</span></span>](deploying-mbam-25.md)

[<span data-ttu-id="3c908-128">MBAM 2.5 規劃</span><span class="sxs-lookup"><span data-stu-id="3c908-128">Planning for MBAM 2.5</span></span>](planning-for-mbam-25.md)

 
## <span data-ttu-id="3c908-129">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="3c908-129">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="3c908-130">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="3c908-130">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="3c908-131">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="3c908-131">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>
 





