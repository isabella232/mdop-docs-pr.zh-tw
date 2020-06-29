---
title: MBAM 2.5 用戶端部署規劃
description: MBAM 2.5 用戶端部署規劃
author: dansimp
ms.assetid: 23c89976-af24-4753-9412-ce0ea42d1964
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ff03b58da0985b2f57308c99a9bc15f4a0554623
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811487"
---
# <span data-ttu-id="dc6c8-103">MBAM 2.5 用戶端部署規劃</span><span class="sxs-lookup"><span data-stu-id="dc6c8-103">Planning for MBAM 2.5 Client Deployment</span></span>


<span data-ttu-id="dc6c8-104">根據您部署 Microsoft BitLocker 管理和監視（MBAM）用戶端軟體的時間，您可以在使用者接收電腦之前或之後，在組織中的電腦上啟用 BitLocker 磁碟機加密。</span><span class="sxs-lookup"><span data-stu-id="dc6c8-104">Depending on when you deploy the Microsoft BitLocker Administration and Monitoring (MBAM) Client software, you can enable BitLocker Drive Encryption on a computer in your organization either before the end user receives the computer or afterwards.</span></span> <span data-ttu-id="dc6c8-105">針對 MBAM 獨立版和 System Center Configuration Manager 整合拓朴，您必須設定 MBAM 的群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="dc6c8-105">For both the MBAM Stand-alone and the System Center Configuration Manager Integration topologies, you have to configure Group Policy settings for MBAM.</span></span>

<span data-ttu-id="dc6c8-106">如果您使用的是 MBAM 獨立拓朴，建議您使用企業軟體部署系統，將 MBAM 用戶端軟體部署到終端使用者電腦。</span><span class="sxs-lookup"><span data-stu-id="dc6c8-106">If you are using the MBAM Stand-alone topology, we recommend that you use an enterprise software deployment system to deploy the MBAM Client software to end-user computers.</span></span>

<span data-ttu-id="dc6c8-107">如果您使用 Configuration Manager 整合拓朴來部署 MBAM，您可以使用 Configuration Manager 將 MBAM 用戶端軟體部署到最終使用者的電腦。</span><span class="sxs-lookup"><span data-stu-id="dc6c8-107">If you deploy MBAM with the Configuration Manager Integration topology, you can use Configuration Manager to deploy the MBAM Client software to end-user computers.</span></span> <span data-ttu-id="dc6c8-108">在 Configuration Manager 中，MBAM 安裝會建立 MBAM 可管理的電腦集合。</span><span class="sxs-lookup"><span data-stu-id="dc6c8-108">In Configuration Manager, the MBAM installation creates a collection of computers that MBAM can manage.</span></span> <span data-ttu-id="dc6c8-109">此集合包含的工作站和裝置沒有受信任的平臺模組（TPM），但執行的是 Windows 8、Windows 8.1 或 Windows 10。</span><span class="sxs-lookup"><span data-stu-id="dc6c8-109">This collection includes workstations and devices that do not have a Trusted Platform Module (TPM), but that are running Windows 8, Windows 8.1, or Windows 10.</span></span>

<span data-ttu-id="dc6c8-110">**記事** 當您使用 Configuration Manager 2007 時，Configuration Manager 整合拓撲安裝不支援 Windows To Go。</span><span class="sxs-lookup"><span data-stu-id="dc6c8-110">**Note** Windows To Go is not supported for the Configuration Manager Integration topology installation when you are using Configuration Manager 2007.</span></span>

 

## <span data-ttu-id="dc6c8-111">部署 MBAM 用戶端以在電腦發佈至最終使用者之後啟用 BitLocker 磁碟機加密</span><span class="sxs-lookup"><span data-stu-id="dc6c8-111">Deploying the MBAM Client to enable BitLocker Drive Encryption after computer distribution to end users</span></span>


<span data-ttu-id="dc6c8-112">在您設定群組原則之後，您可以使用企業軟體部署系統產品（例如 Microsoft System Center Configuration Manager 或 Active Directory 網域服務（AD DS）），將 MBAM 用戶端安裝的 Windows Installer 檔案部署至目的電腦。</span><span class="sxs-lookup"><span data-stu-id="dc6c8-112">After you configure Group Policy, you can use an enterprise software deployment system product like Microsoft System Center Configuration Manager or Active Directory Domain Services (AD DS) to deploy the Windows Installer files of the MBAM Client installation to target computers.</span></span> <span data-ttu-id="dc6c8-113">若要部署 MBAM 用戶端，您可以使用32位或64位 MbamClientSetup.exe 檔案或 MBAMClient.msi 檔案，這些檔案是由 MBAM 用戶端軟體所提供。</span><span class="sxs-lookup"><span data-stu-id="dc6c8-113">To deploy the MBAM Client, you can use either the 32-bit or 64-bit MbamClientSetup.exe files or MBAMClient.msi files, which are provided with the MBAM Client software.</span></span>

<span data-ttu-id="dc6c8-114">**記事** 從 MBAM 2.5 SP1 開始，MBAM 產品不再隨附個別的 MSI。</span><span class="sxs-lookup"><span data-stu-id="dc6c8-114">**Note** Beginning in MBAM 2.5 SP1, a separate MSI is no longer included with the MBAM product.</span></span> <span data-ttu-id="dc6c8-115">不過，您可以從隨附于產品的可執行檔（.exe）中解壓縮 MSI。</span><span class="sxs-lookup"><span data-stu-id="dc6c8-115">However, you can extract the MSI from the executable file (.exe) that is included with the product.</span></span>

 

<span data-ttu-id="dc6c8-116">當您在將電腦發佈到用戶端電腦之後部署 MBAM 用戶端時，系統會提示使用者將電腦加密。</span><span class="sxs-lookup"><span data-stu-id="dc6c8-116">When you deploy the MBAM Client after you distribute computers to client computers, end users are prompted to encrypt their computer.</span></span> <span data-ttu-id="dc6c8-117">此動作可讓 MBAM 收集資料，其中包含 PIN 及密碼（如果原則需要的話），然後開始加密程式。</span><span class="sxs-lookup"><span data-stu-id="dc6c8-117">This action enables MBAM to collect the data, which includes the PIN and password (if required by policy), and then to begin the encryption process.</span></span>

<span data-ttu-id="dc6c8-118">**記事** 在這個方法中，電腦擁有 TPM 晶片的使用者會在尚未啟用晶片的情況下，提示您啟用並初始化 TPM 晶片。</span><span class="sxs-lookup"><span data-stu-id="dc6c8-118">**Note** In this approach, end users who have computers with a TPM chip are prompted to activate and initialize the TPM chip if the chip has not been previously activated.</span></span>

 

## <span data-ttu-id="dc6c8-119">使用 MBAM 用戶端在電腦發佈至最終使用者之前啟用 BitLocker 磁碟機加密</span><span class="sxs-lookup"><span data-stu-id="dc6c8-119">Using the MBAM Client to enable BitLocker Drive Encryption before computer distribution to end users</span></span>


<span data-ttu-id="dc6c8-120">在已集中接收和設定電腦的組織中，以及電腦擁有相容的 TPM 晶片的位置，您可以使用 MBAM 用戶端在每個電腦上管理 BitLocker 磁碟機加密，然後再寫入任何使用者資料。</span><span class="sxs-lookup"><span data-stu-id="dc6c8-120">In organizations where computers are received and configured centrally, and where computers have a compliant TPM chip, you can use the MBAM Client to manage BitLocker Drive Encryption on each computer before any user data is written to it.</span></span> <span data-ttu-id="dc6c8-121">此程式的優點是，每個電腦都符合規範。</span><span class="sxs-lookup"><span data-stu-id="dc6c8-121">The benefit of this process is that every computer is then compliant.</span></span> <span data-ttu-id="dc6c8-122">這個方法不依賴使用者的使用者動作，因為系統管理員已經將電腦加密。</span><span class="sxs-lookup"><span data-stu-id="dc6c8-122">This method does not rely on end-user action because the administrator has already encrypted the computer.</span></span> <span data-ttu-id="dc6c8-123">這個案例的主要假設是，在將電腦傳送給使用者之前，組織的原則會安裝公司的 Windows 影像。</span><span class="sxs-lookup"><span data-stu-id="dc6c8-123">A key assumption for this scenario is that the policy of the organization installs a corporate Windows image before the computer is delivered to the end user.</span></span>

<span data-ttu-id="dc6c8-124">如果您的組織想要使用 TPM 晶片來加密電腦，系統管理員會新增 TPM 保護程式來加密電腦的作業系統磁片。</span><span class="sxs-lookup"><span data-stu-id="dc6c8-124">If your organization wants to use the TPM chip to encrypt computers, the administrator adds the TPM protector to encrypt the operating system volume of the computer.</span></span> <span data-ttu-id="dc6c8-125">如果您的組織想要使用 TPM 晶片及 PIN 保護器，系統管理員會使用 TPM 保護程式來加密作業系統的磁片，然後在使用者第一次登入時選取 PIN。</span><span class="sxs-lookup"><span data-stu-id="dc6c8-125">If your organization wants to use the TPM chip and a PIN protector, the administrator encrypts the operating system volume with the TPM protector, and then end users select a PIN when they log on for the first time.</span></span> <span data-ttu-id="dc6c8-126">如果您的組織決定只使用 PIN 保護器，系統管理員就不需要先加密標籤。</span><span class="sxs-lookup"><span data-stu-id="dc6c8-126">If your organization decides to use only the PIN protector, the administrator does not have to encrypt the volume first.</span></span> <span data-ttu-id="dc6c8-127">當使用者登入時，Microsoft BitLocker 管理和監控會提示他們提供 PIN，或在稍後的電腦重新開機時要使用的 PIN 與密碼。</span><span class="sxs-lookup"><span data-stu-id="dc6c8-127">When end users log on, Microsoft BitLocker Administration and Monitoring prompts them to provide a PIN, or a PIN and password to be used on later computer restarts.</span></span>

<span data-ttu-id="dc6c8-128">**記事** TPM 保護器選項需要系統管理員在將電腦傳送給最終使用者之前，先接受 BIOS 提示，才能啟動並初始化 TPM。</span><span class="sxs-lookup"><span data-stu-id="dc6c8-128">**Note** The TPM protector option requires the administrator to accept the BIOS prompt to activate and initialize the TPM before the computer is delivered to the end user.</span></span>

 

## <span data-ttu-id="dc6c8-129">MBAM 加密硬碟的用戶端支援</span><span class="sxs-lookup"><span data-stu-id="dc6c8-129">MBAM Client support for Encrypted Hard Drives</span></span>


<span data-ttu-id="dc6c8-130">MBAM 支援針對 Opal 和 IEEE 1667 標準提供 TCG 規格需求的加密硬碟磁碟機上的 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="dc6c8-130">MBAM supports BitLocker on Encrypted Hard Drives that meet TCG specification requirements for Opal as well as IEEE 1667 standards.</span></span> <span data-ttu-id="dc6c8-131">在這些裝置上啟用 BitLocker 時，它會在加密的磁片磁碟機上產生金鑰並執行管理功能。</span><span class="sxs-lookup"><span data-stu-id="dc6c8-131">When BitLocker is enabled on these devices, it will generate keys and perform management functions on the encrypted drive.</span></span> <span data-ttu-id="dc6c8-132">如需詳細資訊，請參閱[加密的硬碟](https://technet.microsoft.com/library/hh831627.aspx)。</span><span class="sxs-lookup"><span data-stu-id="dc6c8-132">See [Encrypted Hard Drive](https://technet.microsoft.com/library/hh831627.aspx) for more information.</span></span>


## <span data-ttu-id="dc6c8-133">相關主題</span><span class="sxs-lookup"><span data-stu-id="dc6c8-133">Related topics</span></span>


[<span data-ttu-id="dc6c8-134">規劃部署 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="dc6c8-134">Planning to Deploy MBAM 2.5</span></span>](planning-to-deploy-mbam-25.md)

[<span data-ttu-id="dc6c8-135">部署 MBAM 2.5 用戶端</span><span class="sxs-lookup"><span data-stu-id="dc6c8-135">Deploying the MBAM 2.5 Client</span></span>](deploying-the-mbam-25-client.md)

 

 
## <span data-ttu-id="dc6c8-136">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="dc6c8-136">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="dc6c8-137">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="dc6c8-137">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="dc6c8-138">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="dc6c8-138">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>




