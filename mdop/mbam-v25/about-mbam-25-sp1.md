---
title: 關於 MBAM 2.5 SP1
description: 關於 MBAM 2.5 SP1
author: dansimp
ms.assetid: 6f12e605-44e6-4646-9c20-aee89c8ff0b7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 09/27/2016
ms.openlocfilehash: 41e47e1561629c00d30b45ad2dcd94f37753af5b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810161"
---
# <span data-ttu-id="af7e8-103">關於 MBAM 2.5 SP1</span><span class="sxs-lookup"><span data-stu-id="af7e8-103">About MBAM 2.5 SP1</span></span>


<span data-ttu-id="af7e8-104">MBAM 2.5 SP1 為 BitLocker 磁片磁碟機加密提供簡化的管理介面。</span><span class="sxs-lookup"><span data-stu-id="af7e8-104">MBAM 2.5 SP1 provides a simplified administrative interface for BitLocker Drive Encryption.</span></span> <span data-ttu-id="af7e8-105">BitLocker 針對遺失或被盜電腦的資料竊取或資料暴露提供增強型保護。</span><span class="sxs-lookup"><span data-stu-id="af7e8-105">BitLocker offers enhanced protection against data theft or data exposure for computers that are lost or stolen.</span></span> <span data-ttu-id="af7e8-106">BitLocker 會加密儲存在 Windows 作業系統上的所有資料，以及磁片磁碟機和已設定的資料硬碟。</span><span class="sxs-lookup"><span data-stu-id="af7e8-106">BitLocker encrypts all data that is stored on the Windows operating system and drives and configured data drives.</span></span>

## <span data-ttu-id="af7e8-107">MBAM 概覽</span><span class="sxs-lookup"><span data-stu-id="af7e8-107">Overview of MBAM</span></span>


<span data-ttu-id="af7e8-108">MBAM 2.5 SP1 具有下列功能：</span><span class="sxs-lookup"><span data-stu-id="af7e8-108">MBAM 2.5 SP1 has the following features:</span></span>

-   <span data-ttu-id="af7e8-109">可讓系統管理員自動處理整個企業用戶端電腦上的加密量。</span><span class="sxs-lookup"><span data-stu-id="af7e8-109">Enables administrators to automate the process of encrypting volumes on client computers across the enterprise.</span></span>

-   <span data-ttu-id="af7e8-110">可讓安全性監察官快速判斷個別電腦或甚至企業本身的合規性狀態。</span><span class="sxs-lookup"><span data-stu-id="af7e8-110">Enables security officers to quickly determine the compliance state of individual computers or even of the enterprise itself.</span></span>

-   <span data-ttu-id="af7e8-111">使用 Microsoft System Center Configuration Manager 提供集中式報告及硬體管理。</span><span class="sxs-lookup"><span data-stu-id="af7e8-111">Provides centralized reporting and hardware management with Microsoft System Center Configuration Manager.</span></span>

-   <span data-ttu-id="af7e8-112">減少支援中心的工作負荷，協助最終使用者使用 BitLocker PIN 和復原金鑰要求。</span><span class="sxs-lookup"><span data-stu-id="af7e8-112">Reduces the workload on the Help Desk to assist end users with BitLocker PIN and recovery key requests.</span></span>

-   <span data-ttu-id="af7e8-113">讓使用者能夠使用自助入口網站，獨立地復原加密的裝置。</span><span class="sxs-lookup"><span data-stu-id="af7e8-113">Enables end users to recover encrypted devices independently by using the Self-Service Portal.</span></span>

-   <span data-ttu-id="af7e8-114">讓安全官員能夠輕鬆地審核存取權，以復原金鑰資訊。</span><span class="sxs-lookup"><span data-stu-id="af7e8-114">Enables security officers to easily audit access to recover key information.</span></span>

-   <span data-ttu-id="af7e8-115">讓 Windows 企業使用者能在任何地方繼續運作，保證公司資料受到保護。</span><span class="sxs-lookup"><span data-stu-id="af7e8-115">Empowers Windows Enterprise users to continue working anywhere with the assurance that their corporate data is protected.</span></span>

<span data-ttu-id="af7e8-116">MBAM 會強制執行您針對企業所設定的 BitLocker 加密原則選項、監控用戶端電腦與這些原則的合規性，以及企業及個人電腦的加密狀態報表。</span><span class="sxs-lookup"><span data-stu-id="af7e8-116">MBAM enforces the BitLocker encryption policy options that you set for your enterprise, monitors the compliance of client computers with those policies, and reports on the encryption status of the enterprise’s and individual’s computers.</span></span> <span data-ttu-id="af7e8-117">此外，MBAM 可讓您在使用者忘記其 PIN 或密碼時，或當他們的 BIOS 或開機記錄變更時，存取復原金鑰資訊。</span><span class="sxs-lookup"><span data-stu-id="af7e8-117">In addition, MBAM lets you access the recovery key information when users forget their PIN or password, or when their BIOS or boot records change.</span></span>

<span data-ttu-id="af7e8-118">下列群組可能會對使用 MBAM 來管理 BitLocker 感興趣：</span><span class="sxs-lookup"><span data-stu-id="af7e8-118">The following groups might be interested in using MBAM to manage BitLocker:</span></span>

-   <span data-ttu-id="af7e8-119">管理員、IT 安全性專業人員，以及負責確保機密資料在未授權的情況下公開的合規性官員</span><span class="sxs-lookup"><span data-stu-id="af7e8-119">Administrators, IT security professionals, and compliance officers who are responsible for ensuring that confidential data is not disclosed without authorization</span></span>

-   <span data-ttu-id="af7e8-120">負責遠端或分支辦公室中電腦安全性性的管理員</span><span class="sxs-lookup"><span data-stu-id="af7e8-120">Administrators who are responsible for computer security in remote or branch offices</span></span>

-   <span data-ttu-id="af7e8-121">負責執行 Windows 之用戶端電腦的系統管理員</span><span class="sxs-lookup"><span data-stu-id="af7e8-121">Administrators who are responsible for client computers that are running Windows</span></span>

<span data-ttu-id="af7e8-122">**記事** 在本 MBAM 檔中不詳細說明 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="af7e8-122">**Note** BitLocker is not explained in detail in this MBAM documentation.</span></span> <span data-ttu-id="af7e8-123">如需詳細資訊，請參閱[BitLocker 磁片磁碟機加密概述](https://go.microsoft.com/fwlink/p/?LinkId=225013)。</span><span class="sxs-lookup"><span data-stu-id="af7e8-123">For more information, see [BitLocker Drive Encryption Overview](https://go.microsoft.com/fwlink/p/?LinkId=225013).</span></span>

 

## <a href="" id="what-s-new-in-mbam-2-5-sp1"></a><span data-ttu-id="af7e8-124">MBAM 2.5 SP1 的新功能</span><span class="sxs-lookup"><span data-stu-id="af7e8-124">What’s new in MBAM 2.5 SP1</span></span>


<span data-ttu-id="af7e8-125">本節說明 MBAM 2.5 SP1 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="af7e8-125">This section describes the new features in MBAM 2.5 SP1.</span></span>

### <span data-ttu-id="af7e8-126">MBAM 2.5 SP1 用戶端的新支援語言</span><span class="sxs-lookup"><span data-stu-id="af7e8-126">Newly Supported Languages for the MBAM 2.5 SP1 Client</span></span>

<span data-ttu-id="af7e8-127">目前僅支援 MBAM 用戶端的 MBAM 2.5 SP1 中的下列其他語言，包括自助入口網站：</span><span class="sxs-lookup"><span data-stu-id="af7e8-127">The following additional languages are now supported in MBAM 2.5 SP1 for the MBAM Client only, including the Self-Service Portal:</span></span>

<span data-ttu-id="af7e8-128">捷克文（捷克共和國） cs-CZ</span><span class="sxs-lookup"><span data-stu-id="af7e8-128">Czech (Czech Republic) cs-CZ</span></span>

<span data-ttu-id="af7e8-129">丹麥文（丹麥） da-深色</span><span class="sxs-lookup"><span data-stu-id="af7e8-129">Danish (Denmark) da-DK</span></span>

<span data-ttu-id="af7e8-130">荷蘭文（荷蘭） nl-nl&platform-NL-NL&PLATFORM</span><span class="sxs-lookup"><span data-stu-id="af7e8-130">Dutch (Netherlands) nl-NL</span></span>

<span data-ttu-id="af7e8-131">芬蘭文（芬蘭） fi</span><span class="sxs-lookup"><span data-stu-id="af7e8-131">Finnish (Finland) fi-FI</span></span>

<span data-ttu-id="af7e8-132">希臘文（希臘） el-GR</span><span class="sxs-lookup"><span data-stu-id="af7e8-132">Greek (Greece) el-GR</span></span>

<span data-ttu-id="af7e8-133">匈牙利文（匈牙利） hu</span><span class="sxs-lookup"><span data-stu-id="af7e8-133">Hungarian (Hungary) hu-HU</span></span>

<span data-ttu-id="af7e8-134">挪威文、博克瑪律文（挪威） nb-否</span><span class="sxs-lookup"><span data-stu-id="af7e8-134">Norwegian, Bokmål (Norway) nb-NO</span></span>

<span data-ttu-id="af7e8-135">波蘭文（波蘭） pl-PL</span><span class="sxs-lookup"><span data-stu-id="af7e8-135">Polish (Poland) pl-PL</span></span>

<span data-ttu-id="af7e8-136">葡萄牙文（葡萄牙） pt</span><span class="sxs-lookup"><span data-stu-id="af7e8-136">Portuguese (Portugal) pt-PT</span></span>

<span data-ttu-id="af7e8-137">斯洛伐克文（斯洛伐克） sk-SK</span><span class="sxs-lookup"><span data-stu-id="af7e8-137">Slovak (Slovakia) sk-SK</span></span>

<span data-ttu-id="af7e8-138">斯洛維尼亞文（斯洛維尼亞） sl-SI</span><span class="sxs-lookup"><span data-stu-id="af7e8-138">Slovenian (Slovenia) sl-SI</span></span>

<span data-ttu-id="af7e8-139">瑞典文（瑞典） sv-SE</span><span class="sxs-lookup"><span data-stu-id="af7e8-139">Swedish (Sweden) sv-SE</span></span>

<span data-ttu-id="af7e8-140">土耳其文（土耳其） tr-TR</span><span class="sxs-lookup"><span data-stu-id="af7e8-140">Turkish (Turkey) tr-TR</span></span>

<span data-ttu-id="af7e8-141">如需 MBAM 2.5 和 MBAM 2.5 SP1 中用戶端和伺服器支援的所有語言清單，請參閱[MBAM 2.5 支援](mbam-25-supported-configurations.md)的設定。</span><span class="sxs-lookup"><span data-stu-id="af7e8-141">For a list of all languages supported for client and server in MBAM 2.5 and MBAM 2.5 SP1, see [MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md).</span></span>

### <span data-ttu-id="af7e8-142">Windows 10 支援</span><span class="sxs-lookup"><span data-stu-id="af7e8-142">Support for Windows 10</span></span>

<span data-ttu-id="af7e8-143">MBAM 2.5 SP1 除了與舊版 MBAM 中支援的相同軟體之外，還會新增 Windows 10 和 Windows Server 2016 支援。</span><span class="sxs-lookup"><span data-stu-id="af7e8-143">MBAM 2.5 SP1 adds support for Windows 10 and Windows Server 2016, in addition to the same software that is supported in earlier versions of MBAM.</span></span>

<span data-ttu-id="af7e8-144">Windows 10 在 MBAM 2.5 和 MBAM 2.5 SP1 中都有支援。</span><span class="sxs-lookup"><span data-stu-id="af7e8-144">Windows 10 is supported in both MBAM 2.5 and MBAM 2.5 SP1.</span></span>

### <span data-ttu-id="af7e8-145">Microsoft SQL Server 2014 SP1 的支援</span><span class="sxs-lookup"><span data-stu-id="af7e8-145">Support for Microsoft SQL Server 2014 SP1</span></span>

<span data-ttu-id="af7e8-146">MBAM 2.5 SP1 會新增 Microsoft SQL Server 2014 SP1 的支援，以及舊版 MBAM 中支援的相同軟體。</span><span class="sxs-lookup"><span data-stu-id="af7e8-146">MBAM 2.5 SP1 adds support for Microsoft SQL Server 2014 SP1, in addition to the same software that is supported in earlier versions of MBAM.</span></span>

### <span data-ttu-id="af7e8-147">MBAM 不會再隨附個別的 MSI</span><span class="sxs-lookup"><span data-stu-id="af7e8-147">MBAM no longer ships with separate MSI</span></span>

<span data-ttu-id="af7e8-148">從 MBAM 2.5 SP1 開始，MBAM 產品不再隨附個別的 MSI。</span><span class="sxs-lookup"><span data-stu-id="af7e8-148">Beginning in MBAM 2.5 SP1, a separate MSI is no longer included with the MBAM product.</span></span> <span data-ttu-id="af7e8-149">不過，您可以從隨附于產品的可執行檔（.exe）中解壓縮 MSI。</span><span class="sxs-lookup"><span data-stu-id="af7e8-149">However, you can extract the MSI from the executable file (.exe) that is included with the product.</span></span>

### <span data-ttu-id="af7e8-150">MBAM 可以在不擁有 TPM 的情況下保管 OwnerAuth 密碼</span><span class="sxs-lookup"><span data-stu-id="af7e8-150">MBAM can escrow OwnerAuth passwords without owning the TPM</span></span>

<span data-ttu-id="af7e8-151">之前，如果 MBAM 不擁有 TPM，TPM OwnerAuth 無法 escrowed 至 MBAM 資料庫。</span><span class="sxs-lookup"><span data-stu-id="af7e8-151">Previously, if MBAM did not own the TPM, the TPM OwnerAuth could not be escrowed to the MBAM database.</span></span> <span data-ttu-id="af7e8-152">若要設定 MBAM 擁有 TPM 並儲存密碼，您必須停用 TPM 自動供給，並在用戶端電腦上清除 TPM。</span><span class="sxs-lookup"><span data-stu-id="af7e8-152">To configure MBAM to own the TPM and to store the passwords, you had to disable TPM auto-provisioning and clear the TPM on the client computer.</span></span>

<span data-ttu-id="af7e8-153">在 Windows 8 及更高版本中，MBAM 2.5 SP1 現在可以在不擁有 TPM 的情況下，來保管 OwnerAuth 密碼。</span><span class="sxs-lookup"><span data-stu-id="af7e8-153">In Windows 8 and higher, MBAM 2.5 SP1 can now escrow the OwnerAuth passwords without owning the TPM.</span></span> <span data-ttu-id="af7e8-154">在服務啟動期間，MBAM 查詢以查看 TPM 是否已擁有，如果是，它會要求作業系統的密碼。</span><span class="sxs-lookup"><span data-stu-id="af7e8-154">During service startup, MBAM queries to see if the TPM is already owned and if so, it requests the passwords from the operating system.</span></span> <span data-ttu-id="af7e8-155">然後將密碼 escrowed 到 MBAM 資料庫。</span><span class="sxs-lookup"><span data-stu-id="af7e8-155">The passwords are then escrowed to the MBAM database.</span></span> <span data-ttu-id="af7e8-156">此外，必須將群組原則設定為防止在本機刪除 OwnerAuth。</span><span class="sxs-lookup"><span data-stu-id="af7e8-156">In addition, Group Policy must be set to prevent the OwnerAuth from being deleted locally.</span></span>

<span data-ttu-id="af7e8-157">在 Windows 7 中，MBAM 必須擁有 TPM，才能在 MBAM 資料庫中自動委託 TPM OwnerAuth 資訊。</span><span class="sxs-lookup"><span data-stu-id="af7e8-157">In Windows 7, MBAM must own the TPM to automatically escrow TPM OwnerAuth information in the MBAM database.</span></span> <span data-ttu-id="af7e8-158">如果 MBAM 不擁有 TPM，且已透過群組原則設定 TPM 的 Active Directory （AD）備份，您必須使用**MBAM Active Directory （ad）資料匯入 Cmdlet** ，才能將 TPM OWNERAUTH 從 AD 複製到 MBAM 資料庫。</span><span class="sxs-lookup"><span data-stu-id="af7e8-158">If MBAM does not own the TPM and Active Directory (AD) backup of the TPM is configured through Group Policy, you must use the **MBAM Active Directory (AD) Data Import cmdlets** to copy TPM OwnerAuth from AD into the MBAM database.</span></span> <span data-ttu-id="af7e8-159">這些是五個新的 PowerShell Cmdlet，這些 Cmdlet 會使用儲存在 Active Directory 中的大量復原及 TPM 擁有者資訊預先填入 MBAM 資料庫。</span><span class="sxs-lookup"><span data-stu-id="af7e8-159">These are five new PowerShell cmdlets that pre-populate MBAM databases with the Volume recovery and TPM owner information stored in Active Directory.</span></span>

<span data-ttu-id="af7e8-160">如需詳細資訊，請參閱[MBAM 2.5 安全性考慮](mbam-25-security-considerations.md#bkmk-tpm)。</span><span class="sxs-lookup"><span data-stu-id="af7e8-160">For more information, see [MBAM 2.5 Security Considerations](mbam-25-security-considerations.md#bkmk-tpm).</span></span>

### <span data-ttu-id="af7e8-161">MBAM 可以在封鎖之後自動解除鎖定 TPM</span><span class="sxs-lookup"><span data-stu-id="af7e8-161">MBAM can automatically unlock the TPM after a lockout</span></span>

<span data-ttu-id="af7e8-162">在執行 TPM 1.2 的電腦上，您現在可以將 MBAM 設定為在封鎖時自動解除鎖定 TPM。</span><span class="sxs-lookup"><span data-stu-id="af7e8-162">On computers running TPM 1.2, you can now configure MBAM to automatically unlock the TPM in case of a lockout.</span></span> <span data-ttu-id="af7e8-163">如果已啟用 TPM 封鎖自動重設功能，MBAM 會偵測到使用者已被封鎖，然後從 MBAM 資料庫取得 OwnerAuth 密碼，以便自動解除鎖定使用者的 TPM。</span><span class="sxs-lookup"><span data-stu-id="af7e8-163">If the TPM lockout auto reset feature is enabled, MBAM can detect that a user is locked out and then get the OwnerAuth password from the MBAM database to automatically unlock the TPM for the user.</span></span>

<span data-ttu-id="af7e8-164">在伺服器端和用戶端的群組原則中，都必須啟用這項功能。</span><span class="sxs-lookup"><span data-stu-id="af7e8-164">This feature must be enabled on both the server side and in Group Policy on the client side.</span></span> <span data-ttu-id="af7e8-165">如需詳細資訊，請參閱[MBAM 2.5 安全性考慮](mbam-25-security-considerations.md#bkmk-autounlock)。</span><span class="sxs-lookup"><span data-stu-id="af7e8-165">For more information, see [MBAM 2.5 Security Considerations](mbam-25-security-considerations.md#bkmk-autounlock).</span></span>

### <span data-ttu-id="af7e8-166">支援 FIPS 相容的 BitLocker 數位密碼保護器</span><span class="sxs-lookup"><span data-stu-id="af7e8-166">Support for FIPS-compliant BitLocker numerical password protectors</span></span>

<span data-ttu-id="af7e8-167">在 MBAM 2.5 中，在執行 Windows 8.1 作業系統的裝置上，為聯邦資訊處理標準（FIPS）相容的 BitLocker 復原金鑰新增支援。</span><span class="sxs-lookup"><span data-stu-id="af7e8-167">In MBAM2.5, support was added for Federal Information Processing Standard (FIPS)-compliant BitLocker recovery keys on devices running the Windows 8.1 operating system.</span></span> <span data-ttu-id="af7e8-168">不過，Windows 沒有在 Windows 7 中實現 FIPS 相容的復原金鑰。</span><span class="sxs-lookup"><span data-stu-id="af7e8-168">However, Windows did not implement FIPS-compliant recovery keys in Windows 7.</span></span> <span data-ttu-id="af7e8-169">因此，Windows 7 和 Windows 8 裝置仍需要資料復原代理程式（DRA）保護器來進行恢復。</span><span class="sxs-lookup"><span data-stu-id="af7e8-169">Therefore, Windows 7 and Windows 8 devices still required a Data Recovery Agent (DRA) protector for recovery.</span></span>

<span data-ttu-id="af7e8-170">Windows 小組擁有與熱修復程式 backported FIPS 相容的復原金鑰，而 MBAM 2.5 SP1 也已新增支援。</span><span class="sxs-lookup"><span data-stu-id="af7e8-170">The Windows team has backported FIPS-compliant recovery keys with a hotfix, and MBAM 2.5 SP1 has added support for them as well.</span></span>

<span data-ttu-id="af7e8-171">**記事** 執行 Windows8 作業系統的用戶端電腦仍需要 DRA 保護器，因為修復程式未 backported 至該作業系統。</span><span class="sxs-lookup"><span data-stu-id="af7e8-171">**Note** Client computers that are running the Windows8 operating system still require a DRA protector since the hotfix was not backported to that OS.</span></span> <span data-ttu-id="af7e8-172">若要下載並安裝適用于 Windows 7 和 Windows 8 電腦的 BitLocker 修復程式，請參閱[BitLocker 管理和監視2.5 的修補程式套件 2](https://support.microsoft.com/kb/3015477) 。</span><span class="sxs-lookup"><span data-stu-id="af7e8-172">See [Hotfix Package 2 for BitLocker Administration and Monitoring 2.5](https://support.microsoft.com/kb/3015477) to download and install the BitLocker hotfix for Windows 7 and Windows 8 computers.</span></span> <span data-ttu-id="af7e8-173">如需 DRA 的相關資訊，請參閱將[資料修復代理程式與 BitLocker 配合使用](https://go.microsoft.com/fwlink/?LinkId=393557)。</span><span class="sxs-lookup"><span data-stu-id="af7e8-173">For information about DRA, see [Using Data Recovery Agents with BitLocker](https://go.microsoft.com/fwlink/?LinkId=393557).</span></span>

 

<span data-ttu-id="af7e8-174">若要在貴組織中啟用 FIPS 相容性，您必須設定聯邦資訊處理標準（FIPS）群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="af7e8-174">To enable FIPS compliance in your organization, you must configure the Federal Information Processing Standard (FIPS) Group Policy settings.</span></span> <span data-ttu-id="af7e8-175">如需配置指示，請參閱[BitLocker 群組原則設定](https://go.microsoft.com/fwlink/?LinkId=393560)。</span><span class="sxs-lookup"><span data-stu-id="af7e8-175">For configuration instructions, see [BitLocker Group Policy Settings](https://go.microsoft.com/fwlink/?LinkId=393560).</span></span>

### <span data-ttu-id="af7e8-176">使用新的群組原則設定自訂啟動前恢復訊息和 URL</span><span class="sxs-lookup"><span data-stu-id="af7e8-176">Customize pre-boot recovery message and URL with new Group Policy setting</span></span>

<span data-ttu-id="af7e8-177">新的群組原則設定、**設定預先啟動的復原訊息和 URL**，可讓您設定自訂的復原訊息，或指定一個 URL，當作業系統磁片磁碟機鎖定時，就會顯示在預啟動的 BitLocker 恢復畫面上。</span><span class="sxs-lookup"><span data-stu-id="af7e8-177">A new Group Policy setting, **Configure pre-boot recovery message and URL**, lets you configure a custom recovery message or specify a URL that is then displayed on the pre-boot BitLocker recovery screen when the OS drive is locked.</span></span> <span data-ttu-id="af7e8-178">這個設定只能在執行 Windows 10 的用戶端電腦上使用。</span><span class="sxs-lookup"><span data-stu-id="af7e8-178">This setting is only available on client computers running Windows 10.</span></span>

<span data-ttu-id="af7e8-179">如果您啟用此原則設定，您可以針對預啟動還原訊息選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="af7e8-179">If you enable this policy setting, you can you can select one of these options for the pre-boot recovery message:</span></span>

-   <span data-ttu-id="af7e8-180">**使用自訂**的復原訊息：選取這個選項，即可在 [預啟動 BitLocker 恢復] 畫面中包含自訂訊息。</span><span class="sxs-lookup"><span data-stu-id="af7e8-180">**Use custom recovery message**: Select this option to include a custom message in the pre-boot BitLocker recovery screen.</span></span>

-   <span data-ttu-id="af7e8-181">**使用自訂**的復原 URL：選取這個選項，以取代 [預啟動 BitLocker 恢復] 畫面中顯示的預設 URL。</span><span class="sxs-lookup"><span data-stu-id="af7e8-181">**Use custom recovery URL**: Select this option to replace the default URL that is displayed in the pre-boot BitLocker recovery screen.</span></span>

-   <span data-ttu-id="af7e8-182">**使用預設的復原訊息和 URL**：選取這個選項，即可在 [啟動前的 bitlocker 恢復] 畫面中顯示預設的 BitLocker 復原訊息和 URL。</span><span class="sxs-lookup"><span data-stu-id="af7e8-182">**Use default recovery message and URL**: Select this option to display the default BitLocker recovery message and URL in the pre-boot BitLocker recovery screen.</span></span> <span data-ttu-id="af7e8-183">如果您先前已設定自訂的復原訊息或 URL，且想要還原為預設訊息，您必須啟用此原則，然後選取此選項。</span><span class="sxs-lookup"><span data-stu-id="af7e8-183">If you previously configured a custom recovery message or URL and want to revert to the default message, you must enable this policy and select this option.</span></span>

<span data-ttu-id="af7e8-184">新的群組原則設定位於下列 GPO 節點： [電腦設定**Computer Configuration** &gt; **策略**] &gt; **管理範本** &gt; **Windows 元件** &gt; **MDOP MBAM （BitLocker 管理）** &gt; **作業系統磁片磁碟機**。</span><span class="sxs-lookup"><span data-stu-id="af7e8-184">The new Group Policy setting is located in the following GPO node: **Computer Configuration** &gt; **Policies** &gt; **Administrative Templates** &gt; **Windows Components** &gt; **MDOP MBAM (BitLocker Management)** &gt; **Operating System Drive**.</span></span> <span data-ttu-id="af7e8-185">如需詳細資訊，請參閱[規劃 MBAM 2.5 群組原則需求](planning-for-mbam-25-group-policy-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="af7e8-185">For more information, see [Planning for MBAM 2.5 Group Policy Requirements](planning-for-mbam-25-group-policy-requirements.md).</span></span>

### <span data-ttu-id="af7e8-186">MBAM 已新增對已使用空間加密的支援</span><span class="sxs-lookup"><span data-stu-id="af7e8-186">MBAM added support for Used Space Encryption</span></span>

<span data-ttu-id="af7e8-187">在 MBAM 2.5 SP1 中，如果您透過 BitLocker 群組原則啟用 [使用空間加密]，MBAM 用戶端就會接受這項功能。</span><span class="sxs-lookup"><span data-stu-id="af7e8-187">In MBAM 2.5 SP1, if you enable Used Space Encryption via BitLocker Group Policy, the MBAM Client honors it.</span></span>

<span data-ttu-id="af7e8-188">這個群組原則設定稱為**在操作系統磁碟機上強制執行磁片磁碟機加密類型**，且位於下列 GPO 節點： [**電腦設定] 系統** &gt; **管理範本** &gt; **Windows 元件**（ &gt; **BitLocker 磁片磁碟機加密** &gt; **操作系統磁碟機**）。</span><span class="sxs-lookup"><span data-stu-id="af7e8-188">This Group Policy setting is called **Enforce drive encryption type on operating system drives** and is located in the following GPO node: **Computer Configuration** &gt; **Administrative Templates** &gt; **Windows Components** &gt; **BitLocker Drive Encryption** &gt; **Operating System Drives**.</span></span> <span data-ttu-id="af7e8-189">如果您啟用此原則，並選取 [**僅限已使用的空間**] 加密的加密類型，MBAM 將會服從原則，而 BitLocker 將只會將在該卷上使用的磁碟空間加密。</span><span class="sxs-lookup"><span data-stu-id="af7e8-189">If you enable this policy and select the encryption type as **Used Space Only encryption**, MBAM will honor the policy and BitLocker will only encrypt disk space that is used on the volume.</span></span>

<span data-ttu-id="af7e8-190">如需詳細資訊，請參閱[規劃 MBAM 2.5 群組原則需求](planning-for-mbam-25-group-policy-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="af7e8-190">For more information, see [Planning for MBAM 2.5 Group Policy Requirements](planning-for-mbam-25-group-policy-requirements.md).</span></span>

### <span data-ttu-id="af7e8-191">MBAM 加密硬碟的用戶端支援</span><span class="sxs-lookup"><span data-stu-id="af7e8-191">MBAM Client support for Encrypted Hard Drives</span></span>

<span data-ttu-id="af7e8-192">MBAM 支援針對 Opal 和 IEEE 1667 標準提供 TCG 規格需求的加密硬碟磁碟機上的 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="af7e8-192">MBAM supports BitLocker on Encrypted Hard Drives that meet TCG specification requirements for Opal as well as IEEE 1667 standards.</span></span> <span data-ttu-id="af7e8-193">在這些裝置上啟用 BitLocker 時，它會在加密的磁片磁碟機上產生金鑰並執行管理功能。</span><span class="sxs-lookup"><span data-stu-id="af7e8-193">When BitLocker is enabled on these devices, it will generate keys and perform management functions on the encrypted drive.</span></span> <span data-ttu-id="af7e8-194">如需詳細資訊，請參閱[加密的硬碟](https://technet.microsoft.com/library/hh831627.aspx)。</span><span class="sxs-lookup"><span data-stu-id="af7e8-194">See [Encrypted Hard Drive](https://technet.microsoft.com/library/hh831627.aspx) for more information.</span></span>

### <span data-ttu-id="af7e8-195">註冊 Spn 時不再需要委派設定</span><span class="sxs-lookup"><span data-stu-id="af7e8-195">Delegation configuration no longer required when registering SPNs</span></span>

<span data-ttu-id="af7e8-196">在 MBAM 2.5 SP1 中，您不再需要針對您為應用程式池帳戶所註冊的 Spn 設定受限制委派的需求。</span><span class="sxs-lookup"><span data-stu-id="af7e8-196">The requirement to configure constrained delegation for SPNs that you register for the application pool account is no longer necessary in MBAM 2.5 SP1.</span></span> <span data-ttu-id="af7e8-197">不過，它仍是 MBAM 2.5 的必要條件。</span><span class="sxs-lookup"><span data-stu-id="af7e8-197">However, it is still a requirement for MBAM 2.5.</span></span>

### <span data-ttu-id="af7e8-198">使用 MBAM 做為 Windows 部署的一部分來啟用 BitLocker</span><span class="sxs-lookup"><span data-stu-id="af7e8-198">Enable BitLocker using MBAM as Part of a Windows Deployment</span></span>

<span data-ttu-id="af7e8-199">在 MBAM 2.5 SP1 中，您可以使用 PowerShell 腳本，將 BitLocker 磁碟機加密和保管中的修復金鑰設定為 MBAM 伺服器。</span><span class="sxs-lookup"><span data-stu-id="af7e8-199">In MBAM 2.5 SP1, you can use a PowerShell script to configure BitLocker drive encryption and escrow recovery keys to the MBAM Server.</span></span>

<span data-ttu-id="af7e8-200">如需詳細資訊，請參閱[如何使用 MBAM 做為 Windows 部署的一部分來啟用 BitLocker](how-to-enable-bitlocker-by-using-mbam-as-part-of-a-windows-deploymentmbam-25.md)</span><span class="sxs-lookup"><span data-stu-id="af7e8-200">For more information, see [How to Enable BitLocker by Using MBAM as Part of a Windows Deployment](how-to-enable-bitlocker-by-using-mbam-as-part-of-a-windows-deploymentmbam-25.md)</span></span>

### <span data-ttu-id="af7e8-201">自助式入口網站可以使用 PowerShell 或 SSP 自訂嚮導來自訂</span><span class="sxs-lookup"><span data-stu-id="af7e8-201">Self-Service Portal can be customized by using either PowerShell or the SSP customization wizard</span></span>

<span data-ttu-id="af7e8-202">從 MBAM 2.5 SP1，自助式入口網站可以使用 [自訂嚮導] 以及 [使用 PowerShell] 進行設定。</span><span class="sxs-lookup"><span data-stu-id="af7e8-202">As of MBAM 2.5 SP1, the Self-Service Portal can be configured by using the customization wizard as well as by using PowerShell.</span></span> <span data-ttu-id="af7e8-203">瞭解[如何設定 MBAM 2.5 Web 應用程式](how-to-configure-the-mbam-25-web-applications.md)。</span><span class="sxs-lookup"><span data-stu-id="af7e8-203">See [How to Configure the MBAM 2.5 Web Applications](how-to-configure-the-mbam-25-web-applications.md).</span></span>

### <span data-ttu-id="af7e8-204">網頁瀏覽器不會再以系統管理員身分執行</span><span class="sxs-lookup"><span data-stu-id="af7e8-204">Web browser no longer unintentionally runs as administrator</span></span>

<span data-ttu-id="af7e8-205">MBAM 2.5 中的問題導致伺服器設定工具中的 [說明] 連結導致瀏覽器視窗以系統管理員許可權開啟。</span><span class="sxs-lookup"><span data-stu-id="af7e8-205">An issue in MBAM 2.5 caused help links in the Server Configuration tool to cause browser windows to open with administrator rights.</span></span> <span data-ttu-id="af7e8-206">這個問題已在 MBAM 2.5 SP1 中修正。</span><span class="sxs-lookup"><span data-stu-id="af7e8-206">This issue is fixed in MBAM 2.5 SP1.</span></span>

### <span data-ttu-id="af7e8-207">當 CDN 無法存取時，不再需要下載 JavaScript 檔案以設定自助入口網站</span><span class="sxs-lookup"><span data-stu-id="af7e8-207">No longer need to download the JavaScript files to configure the Self-Service Portal when the CDN is inaccessible</span></span>

<span data-ttu-id="af7e8-208">在 MBAM 2.5 及較舊版本中，如果用戶端存取自助入口網站沒有網際網路存取權，就必須預先從 CDN 下載用於自助處理的 jQuery 檔案。</span><span class="sxs-lookup"><span data-stu-id="af7e8-208">In MBAM 2.5 and earlier, the jQuery files used for configuration of the Self-Service Portal had to be downloaded from the CDN in advance if clients accessing the Self-Service Portal did not have internet access.</span></span> <span data-ttu-id="af7e8-209">在 MBAM 2.5 SP1 中，所有的 JavaScript 檔案都包含在產品中，因此不需要下載這些檔案。</span><span class="sxs-lookup"><span data-stu-id="af7e8-209">In MBAM 2.5 SP1, all JavaScript files are included in the product, so downloading them is unnecessary.</span></span>

### <span data-ttu-id="af7e8-210">報表可在報表建立器3.0 中開啟</span><span class="sxs-lookup"><span data-stu-id="af7e8-210">Reports can be opened in Report Builder 3.0</span></span>

<span data-ttu-id="af7e8-211">在 MBAM 2.5 SP1 中，報表已更新為最新的報表定義語言架構，讓使用者能夠在報表建立器3.0 中開啟及自訂報表，並立即儲存，而不會損壞報表檔案。</span><span class="sxs-lookup"><span data-stu-id="af7e8-211">In MBAM 2.5 SP1, the reports have been updated to the latest report definition language schema, allowing users to open and customize the reports in Report Builder 3.0 and save them immediately without corrupting the report file.</span></span>

### <span data-ttu-id="af7e8-212">新的 PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="af7e8-212">New PowerShell cmdlets</span></span>

<span data-ttu-id="af7e8-213">新的 MBAM 2.5 SP1 的 PowerShell Cmdlet 可讓您設定及管理不同的 MBAM 功能，包括資料庫、報告和 web 應用程式。</span><span class="sxs-lookup"><span data-stu-id="af7e8-213">New PowerShell cmdlets for MBAM 2.5 SP1 enable you to configure and manage different MBAM features, including databases, reports, and web applications.</span></span> <span data-ttu-id="af7e8-214">每個功能都有對應的 PowerShell Cmdlet，您可以用來啟用或停用功能，或是取得該功能的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="af7e8-214">Each feature has a corresponding PowerShell cmdlet that you can use to enable or disable features, or to get information about the feature.</span></span>

<span data-ttu-id="af7e8-215">已針對 MBAM 2.5 SP1 執行下列 Cmdlet：</span><span class="sxs-lookup"><span data-stu-id="af7e8-215">The following cmdlets have been implemented for MBAM 2.5 SP1:</span></span>

-   <span data-ttu-id="af7e8-216">寫入 MbamTpmInformation</span><span class="sxs-lookup"><span data-stu-id="af7e8-216">Write-MbamTpmInformation</span></span>

-   <span data-ttu-id="af7e8-217">寫入 MbamRecoveryInformation</span><span class="sxs-lookup"><span data-stu-id="af7e8-217">Write-MbamRecoveryInformation</span></span>

-   <span data-ttu-id="af7e8-218">讀取 ADTpmInformation</span><span class="sxs-lookup"><span data-stu-id="af7e8-218">Read-ADTpmInformation</span></span>

-   <span data-ttu-id="af7e8-219">讀取 ADRecoveryInformation</span><span class="sxs-lookup"><span data-stu-id="af7e8-219">Read-ADRecoveryInformation</span></span>

-   <span data-ttu-id="af7e8-220">寫入 MbamComputerUser</span><span class="sxs-lookup"><span data-stu-id="af7e8-220">Write-MbamComputerUser</span></span>

<span data-ttu-id="af7e8-221">下列參數已在 MBAM 2.5 SP1 的 Enable-MbamWebApplication 和 Test MbamWebApplication Cmdlet 中實現：</span><span class="sxs-lookup"><span data-stu-id="af7e8-221">The following parameters have been implemented in the Enable-MbamWebApplication and Test-MbamWebApplication cmdlets for MBAM 2.5 SP1:</span></span>

-   <span data-ttu-id="af7e8-222">DataMigrationAccessGroup</span><span class="sxs-lookup"><span data-stu-id="af7e8-222">DataMigrationAccessGroup</span></span>

-   <span data-ttu-id="af7e8-223">TpmAutoUnlock</span><span class="sxs-lookup"><span data-stu-id="af7e8-223">TpmAutoUnlock</span></span>

<span data-ttu-id="af7e8-224">如需有關 Cmdlet 的詳細資訊，請參閱[MBAM 2.5 安全考慮](mbam-25-security-considerations.md)及[Microsoft Bitlocker 管理與監視 Cmdlet](https://technet.microsoft.com/library/dn720418.aspx)說明。</span><span class="sxs-lookup"><span data-stu-id="af7e8-224">For information about the cmdlets, see [MBAM 2.5 Security Considerations](mbam-25-security-considerations.md) and [Microsoft Bitlocker Administration and Monitoring Cmdlet Help](https://technet.microsoft.com/library/dn720418.aspx).</span></span>

### <span data-ttu-id="af7e8-225">MBAM 代理程式偵測簡報模式</span><span class="sxs-lookup"><span data-stu-id="af7e8-225">MBAM agent detects presentation mode</span></span>

<span data-ttu-id="af7e8-226">MBAM agent 可以偵測到電腦處於簡報模式時，避免在該時間喚醒調用 MBAM UI。</span><span class="sxs-lookup"><span data-stu-id="af7e8-226">The MBAM agent can detect when the computer is in presentation mode and avoid invoking the MBAM UI at that time.</span></span>

### <span data-ttu-id="af7e8-227">MBAM agent 服務現已設定為使用延遲啟動</span><span class="sxs-lookup"><span data-stu-id="af7e8-227">MBAM agent service now configured to use delayed start</span></span>

<span data-ttu-id="af7e8-228">安裝之後，服務現在會將 MBAM agent 服務設定為使用延遲啟動，減少啟動 Windows 所需的時間長度。</span><span class="sxs-lookup"><span data-stu-id="af7e8-228">After installation, the service will now set the MBAM agent service to use delayed start, decreasing the amount of time it takes to start Windows.</span></span>

### <span data-ttu-id="af7e8-229">已鎖定的固定資料量現已完工合規</span><span class="sxs-lookup"><span data-stu-id="af7e8-229">Locked Fixed Data volumes now report as Compliant</span></span>

<span data-ttu-id="af7e8-230">「已鎖定的固定資料」磁片的合規性計算邏輯已變更為將磁片報告為「合規」，但保護性狀態和加密狀態為「未知」，且符合「大量已鎖定」的相容性狀態詳細資料。</span><span class="sxs-lookup"><span data-stu-id="af7e8-230">The compliance calculation logic for "Locked Fixed Data" volumes has been changed to report the volumes as "Compliant," but with a Protector State and Encryption State of "Unknown" and with a Compliance Status Detail of "Volume is locked".</span></span> <span data-ttu-id="af7e8-231">先前，鎖定的卷已報告為「不相容」、「已加密」的保護程式狀態、「未知」的加密狀態，以及「未知錯誤」的規範狀態詳細資料。</span><span class="sxs-lookup"><span data-stu-id="af7e8-231">Previously, locked volumes were reported as “Non-Compliant”, a Protector State of "Encrypted", an Encryption State of "Unknown", and a Compliance Status Detail of "An unknown error".</span></span>


## <span data-ttu-id="af7e8-232">如何取得 MDOP 技術</span><span class="sxs-lookup"><span data-stu-id="af7e8-232">How to Get MDOP Technologies</span></span>


<span data-ttu-id="af7e8-233">MBAM 是 Microsoft Desktop 優化套件（MDOP）的一部分。</span><span class="sxs-lookup"><span data-stu-id="af7e8-233">MBAM is a part of the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="af7e8-234">MDOP 是 Microsoft 軟體保證程式的一部分。</span><span class="sxs-lookup"><span data-stu-id="af7e8-234">MDOP is part of the Microsoft Software Assurance program.</span></span> <span data-ttu-id="af7e8-235">如需 Microsoft 軟體保證計畫的詳細資訊，以及如何取得 MDOP，請參閱[如何取得 mdop？](https://go.microsoft.com/fwlink/?LinkId=322049)。</span><span class="sxs-lookup"><span data-stu-id="af7e8-235">For more information about the Microsoft Software Assurance program and how to acquire the MDOP, see [How Do I Get MDOP?](https://go.microsoft.com/fwlink/?LinkId=322049).</span></span>

## <span data-ttu-id="af7e8-236">MBAM 2.5 SP1 版本資訊</span><span class="sxs-lookup"><span data-stu-id="af7e8-236">MBAM 2.5 SP1 Release Notes</span></span>


<span data-ttu-id="af7e8-237">如需本檔中未包含的詳細資訊及最新資訊，請參閱[MBAM 2.5 SP1 的版本](release-notes-for-mbam-25-sp1.md)資訊。</span><span class="sxs-lookup"><span data-stu-id="af7e8-237">For more information and late-breaking news that is not included in this documentation, see [Release Notes for MBAM 2.5 SP1](release-notes-for-mbam-25-sp1.md).</span></span>

## <span data-ttu-id="af7e8-238">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="af7e8-238">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="af7e8-239">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="af7e8-239">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="af7e8-240">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="af7e8-240">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>

## <span data-ttu-id="af7e8-241">相關主題</span><span class="sxs-lookup"><span data-stu-id="af7e8-241">Related topics</span></span>


[<span data-ttu-id="af7e8-242">Microsoft BitLocker Administration and Monitoring 2.5</span><span class="sxs-lookup"><span data-stu-id="af7e8-242">Microsoft BitLocker Administration and Monitoring 2.5</span></span>](index.md)

[<span data-ttu-id="af7e8-243">開始使用 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="af7e8-243">Getting Started with MBAM 2.5</span></span>](getting-started-with-mbam-25.md)

 

 





