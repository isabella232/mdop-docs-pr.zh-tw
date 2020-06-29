---
title: MBAM 2.0 用戶端部署規劃
description: MBAM 2.0 用戶端部署規劃
author: dansimp
ms.assetid: 3a92cf29-092f-4cad-bdfa-d5f6aafe554b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c3a7383188d4064247d8e493c8e6125fc24a1d2b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800139"
---
# <span data-ttu-id="c94af-103">MBAM 2.0 用戶端部署規劃</span><span class="sxs-lookup"><span data-stu-id="c94af-103">Planning for MBAM 2.0 Client Deployment</span></span>


<span data-ttu-id="c94af-104">根據您部署 Microsoft BitLocker 管理與監視（MBAM）用戶端的時間，您可以在您組織中的電腦上啟用 BitLocker 磁碟機加密，您必須先在使用者接收到電腦或之後進行。</span><span class="sxs-lookup"><span data-stu-id="c94af-104">Depending on when you deploy the Microsoft BitLocker Administration and Monitoring (MBAM) Client, you can enable BitLocker drive encryption on a computer in your organization either before the end user receives the computer or afterwards.</span></span> <span data-ttu-id="c94af-105">針對 MBAM 獨立版與 Configuration Manager 拓撲結構，您必須設定 MBAM 的群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="c94af-105">For both the MBAM Stand-alone and the Configuration Manager topologies, you have to configure Group Policy settings for MBAM.</span></span>

<span data-ttu-id="c94af-106">如果您使用的是 MBAM 獨立拓朴，建議您使用企業軟體部署系統，將 MBAM 用戶端軟體部署到終端使用者電腦。</span><span class="sxs-lookup"><span data-stu-id="c94af-106">If you are using the MBAM Stand-alone topology, it is recommended that you use an enterprise software deployment system to deploy the MBAM Client software to end-user computers.</span></span>

<span data-ttu-id="c94af-107">如果您使用 Configuration Manager 拓撲部署 MBAM，您可以使用 Configuration Manager 將 MBAM 用戶端軟體部署到終端使用者電腦。</span><span class="sxs-lookup"><span data-stu-id="c94af-107">If you deploy MBAM with the Configuration Manager topology, you can use Configuration Manager to deploy the MBAM Client software to end-user computers.</span></span> <span data-ttu-id="c94af-108">在 Configuration Manager 中，MBAM 安裝會建立 MBAM 可管理的電腦集合。</span><span class="sxs-lookup"><span data-stu-id="c94af-108">In Configuration Manager, the MBAM installation creates a collection of computers that MBAM can manage.</span></span> <span data-ttu-id="c94af-109">此集合包含的工作站和裝置沒有受信任的平臺模組（TPM），但執行的是 Windows 8。</span><span class="sxs-lookup"><span data-stu-id="c94af-109">This collection includes workstations and devices that do not have a Trusted Platform Module (TPM), but that are running Windows 8.</span></span>

<span data-ttu-id="c94af-110">**記事** 如果您使用的是 Configuration Manager 2007，則 MBAM 整合式 Configuration Manager 安裝不支援 Windows To Go。</span><span class="sxs-lookup"><span data-stu-id="c94af-110">**Note** Windows To Go is not supported for integrated Configuration Manager installations of MBAM if you are using Configuration Manager 2007.</span></span>

 

## <span data-ttu-id="c94af-111">部署 MBAM 用戶端以在電腦發佈至最終使用者之後啟用 BitLocker 加密</span><span class="sxs-lookup"><span data-stu-id="c94af-111">Deploying the MBAM Client to Enable BitLocker Encryption After Computer Distribution to End Users</span></span>


<span data-ttu-id="c94af-112">在您設定群組原則之後，您可以使用企業軟體部署系統產品（例如 Microsoft System Center Configuration Manager 或 Active Directory 網域服務（AD DS）），將 MBAM 用戶端安裝的 Windows Installer 檔案部署至目的電腦。</span><span class="sxs-lookup"><span data-stu-id="c94af-112">After you configure Group Policy, you can use an enterprise software deployment system product like Microsoft System Center Configuration Manager or Active Directory Domain Services (AD DS) to deploy the Windows Installer files of the MBAM Client installation to target computers.</span></span> <span data-ttu-id="c94af-113">若要部署 MBAM 用戶端，您可以使用32位或64位 MbamClientSetup.exe 檔案或 MBAMClient.msi 檔案（隨附于 MBAM 軟體）。</span><span class="sxs-lookup"><span data-stu-id="c94af-113">To deploy the MBAM Client, you can use either the 32-bit or 64-bit MbamClientSetup.exe files or MBAMClient.msi files, which are provided with the MBAM software.</span></span>

<span data-ttu-id="c94af-114">當您在將電腦發佈到用戶端電腦之後部署 MBAM 用戶端時，系統會提示使用者將電腦加密。</span><span class="sxs-lookup"><span data-stu-id="c94af-114">When you deploy the MBAM Client after you distribute computers to client computers, end users are prompted to encrypt their computer.</span></span> <span data-ttu-id="c94af-115">這可讓 MBAM 收集資料（包括 PIN 和密碼），然後開始加密程式。</span><span class="sxs-lookup"><span data-stu-id="c94af-115">This enables MBAM to collect the data, which includes the PIN and password, and then to begin the encryption process.</span></span>

<span data-ttu-id="c94af-116">**記事** 在這個方法中，電腦擁有 TPM 晶片的使用者會收到啟動並初始化 TPM 晶片（如果此晶片尚未啟用）。</span><span class="sxs-lookup"><span data-stu-id="c94af-116">**Note** In this approach, users who have computers with a TPM chip are prompted to activate and initialize the TPM chip if the chip has not been previously activated.</span></span>

 

## <span data-ttu-id="c94af-117">使用 MBAM 用戶端在電腦發佈至最終使用者之前啟用 BitLocker 加密</span><span class="sxs-lookup"><span data-stu-id="c94af-117">Using the MBAM Client to Enable BitLocker Encryption Before Computer Distribution to End Users</span></span>


<span data-ttu-id="c94af-118">在已集中接收和設定電腦的組織中，以及電腦擁有相容的 TPM 晶片的位置，您可以安裝 MBAM 用戶端，在每個電腦上管理 BitLocker 加密，然後再寫入任何使用者資料。</span><span class="sxs-lookup"><span data-stu-id="c94af-118">In organizations where computers are received and configured centrally, and where computers have a compliant TPM chip, you can install the MBAM Client to manage BitLocker encryption on each computer before any user data is written to it.</span></span> <span data-ttu-id="c94af-119">此程式的優點是，每個電腦都會成為符合 BitLocker 加密規範的功能。</span><span class="sxs-lookup"><span data-stu-id="c94af-119">The benefit of this process is that every computer will then be BitLocker encryption-compliant.</span></span> <span data-ttu-id="c94af-120">這個方法不依賴使用者的動作，因為系統管理員已經將電腦加密。</span><span class="sxs-lookup"><span data-stu-id="c94af-120">This method does not rely on user action because the administrator has already encrypted the computer.</span></span> <span data-ttu-id="c94af-121">這個案例的主要假設是，在電腦傳送給使用者之前，組織的原則會安裝公司的 Windows 影像。</span><span class="sxs-lookup"><span data-stu-id="c94af-121">A key assumption for this scenario is that the policy of the organization installs a corporate Windows image before the computer is delivered to the user.</span></span>

<span data-ttu-id="c94af-122">如果您的組織想要使用 TPM 晶片來加密電腦，系統管理員會新增 TPM 保護程式來加密電腦的作業系統磁片。</span><span class="sxs-lookup"><span data-stu-id="c94af-122">If your organization wants to use the TPM chip to encrypt computers, the administrator adds the TPM protector to encrypt the operating system volume of the computer.</span></span> <span data-ttu-id="c94af-123">如果您的組織想要使用 TPM 晶片及 PIN 保護器，系統管理員會使用 TPM 保護程式來加密作業系統的磁片，然後在使用者第一次登入時選取 PIN。</span><span class="sxs-lookup"><span data-stu-id="c94af-123">If your organization wants to use the TPM chip and a PIN protector, the administrator encrypts the operating system volume with the TPM protector, and then users select a PIN when they log on for the first time.</span></span> <span data-ttu-id="c94af-124">如果您的組織決定只使用 PIN 保護器，系統管理員就不需要先加密標籤。</span><span class="sxs-lookup"><span data-stu-id="c94af-124">If your organization decides to use only the PIN protector, the administrator does not have to encrypt the volume first.</span></span> <span data-ttu-id="c94af-125">當使用者登入時，Microsoft BitLocker 管理和監控會提示他們提供 PIN，或在稍後的電腦重新開機時要使用的 PIN 與密碼。</span><span class="sxs-lookup"><span data-stu-id="c94af-125">When users log on, Microsoft BitLocker Administration and Monitoring prompts them to provide a PIN, or a PIN and password to be used on later computer restarts.</span></span>

<span data-ttu-id="c94af-126">**記事** TPM 保護器選項需要系統管理員在將電腦傳送給使用者之前，先接受 BIOS 提示，才能啟動並初始化 TPM。</span><span class="sxs-lookup"><span data-stu-id="c94af-126">**Note** The TPM protector option requires the administrator to accept the BIOS prompt to activate and initialize the TPM before the computer is delivered to the user.</span></span>

 

## <span data-ttu-id="c94af-127">相關主題</span><span class="sxs-lookup"><span data-stu-id="c94af-127">Related topics</span></span>


[<span data-ttu-id="c94af-128">規劃部署 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="c94af-128">Planning to Deploy MBAM 2.0</span></span>](planning-to-deploy-mbam-20-mbam-2.md)

[<span data-ttu-id="c94af-129">部署 MBAM 2.0 用戶端</span><span class="sxs-lookup"><span data-stu-id="c94af-129">Deploying the MBAM 2.0 Client</span></span>](deploying-the-mbam-20-client-mbam-2.md)

 

 





