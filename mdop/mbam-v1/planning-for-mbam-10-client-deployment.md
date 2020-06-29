---
title: MBAM 1.0 用戶端部署規劃
description: MBAM 1.0 用戶端部署規劃
author: dansimp
ms.assetid: 3af2e7f3-134b-4ab9-9847-b07474ca6ac3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d58d6420febd2da9ee9cd4074fc8b5870285b0b4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811420"
---
# <span data-ttu-id="b8546-103">MBAM 1.0 用戶端部署規劃</span><span class="sxs-lookup"><span data-stu-id="b8546-103">Planning for MBAM 1.0 Client Deployment</span></span>


<span data-ttu-id="b8546-104">根據您部署 Microsoft BitLocker 管理與監視（MBAM）用戶端的時間，您可以在組織中的電腦上啟用 BitLocker 加密，就像在最終使用者接收電腦或之後。</span><span class="sxs-lookup"><span data-stu-id="b8546-104">Depending on when you deploy the Microsoft BitLocker Administration and Monitoring (MBAM) Client, you can enable BitLocker encryption on a computer in your organization either before the end user receives the computer or afterwards.</span></span> <span data-ttu-id="b8546-105">若要在最終使用者收到電腦之後啟用 BitLocker 加密，請設定 [群組原則]。</span><span class="sxs-lookup"><span data-stu-id="b8546-105">To enable BitLocker encryption after the end user receives the computer, configure Group Policy.</span></span> <span data-ttu-id="b8546-106">若要在最終使用者收到電腦之前啟用 BitLocker 加密，請使用企業軟體部署系統來部署 MBAM 用戶端軟體。</span><span class="sxs-lookup"><span data-stu-id="b8546-106">To enable BitLocker encryption before the end user receives the computer, deploy the MBAM Client software by using an enterprise software deployment system.</span></span>

<span data-ttu-id="b8546-107">您可以在組織中使用一或兩個方法。</span><span class="sxs-lookup"><span data-stu-id="b8546-107">You can use one or both methods in your organization.</span></span> <span data-ttu-id="b8546-108">如果您同時使用這兩種方法，就可以改善合規性、報告和金鑰復原支援。</span><span class="sxs-lookup"><span data-stu-id="b8546-108">If you use both methods, you can improve compliance, reporting, and key recovery support.</span></span>

<span data-ttu-id="b8546-109">**記事** 若要查看 MBAM 用戶端系統需求，請參閱[MBAM 1.0 支援](mbam-10-supported-configurations.md)的設定。</span><span class="sxs-lookup"><span data-stu-id="b8546-109">**Note** To review the MBAM Client system requirements, see [MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md).</span></span>

 

## <span data-ttu-id="b8546-110">部署 MBAM 用戶端以在電腦發佈至最終使用者之後啟用 BitLocker 加密</span><span class="sxs-lookup"><span data-stu-id="b8546-110">Deploying the MBAM Client to enable BitLocker encryption after computer distribution to end users</span></span>


<span data-ttu-id="b8546-111">在您設定群組原則之後，您可以使用企業軟體部署系統產品（例如 Microsoft System Center Configuration Manager 2012 或 Active Directory 網域服務），將 MBAM 用戶端安裝 Windows 安裝程式檔案部署到目的電腦。</span><span class="sxs-lookup"><span data-stu-id="b8546-111">After you configure the Group Policy, you can use an enterprise software deployment system product, such as Microsoft System Center Configuration Manager 2012 or Active Directory Domain Services, to deploy the MBAM Client installation Windows Installer files to the target computers.</span></span> <span data-ttu-id="b8546-112">兩個 MBAM 用戶端安裝 Windows 安裝程式檔案是 MBAMClient-64bit.msi 並 MBAMClient-32bit.msi，這些檔案是與 MBAM 軟體一起提供的。</span><span class="sxs-lookup"><span data-stu-id="b8546-112">The two MBAM Client installation Windows Installer files are MBAMClient-64bit.msi and MBAMClient-32bit.msi, which are provided with the MBAM software.</span></span> <span data-ttu-id="b8546-113">如需如何部署 MBAM 群組原則物件的詳細資訊，請參閱[部署 MBAM 1.0 群組原則物件](deploying-mbam-10-group-policy-objects.md)。</span><span class="sxs-lookup"><span data-stu-id="b8546-113">For more information about how to deploy MBAM Group Policy Objects, see [Deploying MBAM 1.0 Group Policy Objects](deploying-mbam-10-group-policy-objects.md).</span></span>

<span data-ttu-id="b8546-114">當您部署 MBAM 用戶端時，將電腦發佈給最終使用者之後，系統會提示使用者將其電腦加密。</span><span class="sxs-lookup"><span data-stu-id="b8546-114">When you deploy the MBAM Client, after you distribute the computers to end users, the end users are prompted to encrypt their computers.</span></span> <span data-ttu-id="b8546-115">這可讓 MBAM 收集資料、包含 PIN 和密碼，然後開始加密程式。</span><span class="sxs-lookup"><span data-stu-id="b8546-115">This lets MBAM collect the data, to include the PIN and password, and then begin the encryption process.</span></span>

<span data-ttu-id="b8546-116">**記事** 在這個方法中，系統會提示使用者啟用並初始化受信任的平臺模組（TPM）晶片（如果先前沒有啟用的話）。</span><span class="sxs-lookup"><span data-stu-id="b8546-116">**Note** In this approach, users are prompted to activate and initialize the Trusted Platform Module (TPM) chip, if it has not been previously activated.</span></span>

 

## <span data-ttu-id="b8546-117">使用 MBAM 用戶端在電腦發佈至最終使用者之前啟用 BitLocker 加密</span><span class="sxs-lookup"><span data-stu-id="b8546-117">Using the MBAM Client to enable BitLocker encryption before computer distribution to end users</span></span>


<span data-ttu-id="b8546-118">在已集中接收和設定電腦的組織中，您可以安裝 MBAM 用戶端，在每個電腦上都能管理 BitLocker 加密，然後再寫入任何使用者資料。</span><span class="sxs-lookup"><span data-stu-id="b8546-118">In organizations where computers are received and configured centrally, you can install the MBAM Client to manage BitLocker encryption on each computer before any user data is written on it.</span></span> <span data-ttu-id="b8546-119">此程式的優點是，每個電腦都會符合 BitLocker 加密的規範。</span><span class="sxs-lookup"><span data-stu-id="b8546-119">The benefit of this process is that every computer will then be compliant with the BitLocker encryption.</span></span> <span data-ttu-id="b8546-120">這個方法不依賴使用者的動作，因為系統管理員已經將電腦加密。</span><span class="sxs-lookup"><span data-stu-id="b8546-120">This method does not rely on user action because the administrator has already encrypted the computer.</span></span> <span data-ttu-id="b8546-121">這個案例的主要假設是，在電腦傳送給使用者之前，組織的原則會安裝公司的 Windows 影像。</span><span class="sxs-lookup"><span data-stu-id="b8546-121">A key assumption for this scenario is that the policy of the organization installs a corporate Windows image before the computer is delivered to the user.</span></span>

<span data-ttu-id="b8546-122">如果您的組織想要使用（TPM）來加密電腦，系統管理員必須使用 TPM 保護程式來加密電腦的作業系統磁片。</span><span class="sxs-lookup"><span data-stu-id="b8546-122">If your organization wants to use (TPM) to encrypt computers, the administrator must encrypt the operating system volume of the computer with TPM protector.</span></span> <span data-ttu-id="b8546-123">如果您的組織想要使用 TPM 晶片及 PIN 保護器，系統管理員必須使用 TPM 保護程式來加密系統磁碟區標，然後在使用者第一次登入時選取 PIN。</span><span class="sxs-lookup"><span data-stu-id="b8546-123">If your organization wants to use the TPM chip and a PIN protector, the administrator must encrypt the system volume with the TPM protector, and then the users select a PIN the first time they log on.</span></span> <span data-ttu-id="b8546-124">如果您的組織決定只使用 PIN 保護器，系統管理員就不需要先加密標籤。</span><span class="sxs-lookup"><span data-stu-id="b8546-124">If your organization decides to use only the PIN protector, the administrator does not have to encrypt the volume first.</span></span> <span data-ttu-id="b8546-125">當使用者登入其電腦時，MBAM 會提示他們提供 PIN 或 PIN，以及它們在稍後重新開機電腦時所使用的密碼。</span><span class="sxs-lookup"><span data-stu-id="b8546-125">When users log on their computers, MBAM prompts them to provide a PIN or a PIN and a password that they will use when they restart their computer later.</span></span>

<span data-ttu-id="b8546-126">**記事** TPM 保護器選項要求管理員在將電腦傳送給使用者之前，接受 BIOS 提示來啟用並初始化 TPM。</span><span class="sxs-lookup"><span data-stu-id="b8546-126">**Note** The TPM protector option requires for the administrator to accept the BIOS prompt to activate and initialize the TPM before delivering the computer to the user.</span></span>

 

## <span data-ttu-id="b8546-127">相關主題</span><span class="sxs-lookup"><span data-stu-id="b8546-127">Related topics</span></span>


[<span data-ttu-id="b8546-128">規劃部署 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="b8546-128">Planning to Deploy MBAM 1.0</span></span>](planning-to-deploy-mbam-10.md)

[<span data-ttu-id="b8546-129">部署 MBAM 1.0 用戶端</span><span class="sxs-lookup"><span data-stu-id="b8546-129">Deploying the MBAM 1.0 Client</span></span>](deploying-the-mbam-10-client.md)

 

 





