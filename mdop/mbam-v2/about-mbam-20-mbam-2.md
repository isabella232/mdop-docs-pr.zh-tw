---
title: 關於 MBAM 2.0
description: 關於 MBAM 2.0
author: dansimp
ms.assetid: b43a0ba9-1c83-4854-a2c5-14eea0070e36
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7bdf24d1f375dd1fa8b18ac90c2fc49d2887c6c5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810484"
---
# <span data-ttu-id="570de-103">關於 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="570de-103">About MBAM 2.0</span></span>


<span data-ttu-id="570de-104">Microsoft BitLockerAdministration 和 Monitoring （MBAM）2.0 提供簡化的管理介面以進行 BitLocker 磁碟機加密。</span><span class="sxs-lookup"><span data-stu-id="570de-104">Microsoft BitLockerAdministration and Monitoring(MBAM)2.0 provides a simplified administrative interface to BitLocker drive encryption.</span></span> <span data-ttu-id="570de-105">BitLocker 針對遺失或被盜電腦的資料竊取或資料暴露提供增強型保護。</span><span class="sxs-lookup"><span data-stu-id="570de-105">BitLocker offers enhanced protection against data theft or data exposure for computers that are lost or stolen.</span></span> <span data-ttu-id="570de-106">BitLocker 會加密儲存在 Windows 作業系統卷和已設定資料量的所有資料。</span><span class="sxs-lookup"><span data-stu-id="570de-106">BitLocker encrypts all data that is stored on the Windows operating system volume and configured data volumes.</span></span>

## <span data-ttu-id="570de-107">關於 MBAM 2。0</span><span class="sxs-lookup"><span data-stu-id="570de-107">About MBAM2.0</span></span>


<span data-ttu-id="570de-108">BitLockerAdministration 和 Monitoring 2.0 會強制您為企業設定的 BitLocker 加密原則選項，監視用戶端電腦與這些原則的合規性，以及企業和個別電腦的加密狀態。</span><span class="sxs-lookup"><span data-stu-id="570de-108">BitLockerAdministration and Monitoring2.0 enforces the BitLocker encryption policy options that you set for your enterprise, monitors the compliance of client computers with those policies, and reports on the encryption status of both the enterprise and the individual computers.</span></span> <span data-ttu-id="570de-109">此外，MBAM 可讓您在使用者忘記其 PIN 或密碼時，或當他們的 BIOS 或開機記錄變更時，存取復原金鑰資訊。</span><span class="sxs-lookup"><span data-stu-id="570de-109">In addition, MBAM lets you access the recovery key information when users forget their PIN or password, or when their BIOS or boot record changes.</span></span>

<span data-ttu-id="570de-110">**記事** 本指南未涵蓋 BitLocker 的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="570de-110">**Note** BitLocker is not covered in detail in this guide.</span></span> <span data-ttu-id="570de-111">如需 BitLocker 的概覽，請參閱[Bitlocker 磁片磁碟機加密概述](https://go.microsoft.com/fwlink/p/?LinkId=225013)。</span><span class="sxs-lookup"><span data-stu-id="570de-111">For an overview of BitLocker, see [BitLocker Drive Encryption Overview](https://go.microsoft.com/fwlink/p/?LinkId=225013).</span></span>

 

<span data-ttu-id="570de-112">下列群組可能會對使用 MBAM 來管理 BitLocker 感興趣：</span><span class="sxs-lookup"><span data-stu-id="570de-112">The following groups might be interested in using MBAM to manage BitLocker:</span></span>

-   <span data-ttu-id="570de-113">管理員、IT 安全性專業人員，以及負責確保機密資料在未授權的情況下公開的合規性官員</span><span class="sxs-lookup"><span data-stu-id="570de-113">Administrators, IT security professionals, and compliance officers who are responsible for ensuring that confidential data is not disclosed without authorization</span></span>

-   <span data-ttu-id="570de-114">負責遠端或分支辦公室中電腦安全性性的管理員</span><span class="sxs-lookup"><span data-stu-id="570de-114">Administrators who are responsible for computer security in remote or branch offices</span></span>

-   <span data-ttu-id="570de-115">負責執行 Windows 之用戶端電腦的系統管理員</span><span class="sxs-lookup"><span data-stu-id="570de-115">Administrators who are responsible for client computers that are running Windows</span></span>

## <a href="" id="what-s-new-in-mbam-2-0"></a><span data-ttu-id="570de-116">MBAM 2.0 的新功能</span><span class="sxs-lookup"><span data-stu-id="570de-116">What’s New in MBAM2.0</span></span>


<span data-ttu-id="570de-117">MBAM 2.0 提供下列新功能和功能。</span><span class="sxs-lookup"><span data-stu-id="570de-117">MBAM2.0 provides the following new features and functionality.</span></span>

### <span data-ttu-id="570de-118">將 System Center Configuration Manager 與 MBAM 整合</span><span class="sxs-lookup"><span data-stu-id="570de-118">Integration of System Center Configuration Manager with MBAM</span></span>

<span data-ttu-id="570de-119">MBAM 現在支援與 System Center Configuration Manager 整合。</span><span class="sxs-lookup"><span data-stu-id="570de-119">MBAM now supports integration with System Center Configuration Manager.</span></span> <span data-ttu-id="570de-120">此整合將 MBAM 合規性基礎結構移至 Configuration Manager 的原生環境。</span><span class="sxs-lookup"><span data-stu-id="570de-120">This integration moves the MBAM compliance infrastructure into the native environment of Configuration Manager.</span></span> <span data-ttu-id="570de-121">在企業中使用 Configuration Manager 的 IT 系統管理員現在可以在 Microsoft 管理主控台中查看其企業的合規性狀態，並深入探索報表來查看個別電腦。</span><span class="sxs-lookup"><span data-stu-id="570de-121">IT administrators who use Configuration Manager in their enterprise can now view the compliance status of their enterprise in the Microsoft Management Console and drill into reports to view individual computers.</span></span>

### <span data-ttu-id="570de-122">硬體相容性僅適用于 Configuration Manager 整合拓撲</span><span class="sxs-lookup"><span data-stu-id="570de-122">Hardware Compatibility is Available Only in the Configuration Manager Integration Topology</span></span>

<span data-ttu-id="570de-123">將 Configuration Manager 與 MBAM 整合可啟用 Configuration Manager 功能，允許或禁止搭配 MBAM 使用特定的硬體類型，並提供比 MBAM 1.0 中提供的硬體相容性更大的彈性。</span><span class="sxs-lookup"><span data-stu-id="570de-123">Integrating Configuration Manager with MBAM enables Configuration Manager capabilities that allow or prohibit the use of certain hardware types with MBAM and provides more flexibility than the hardware compatibility that was available in MBAM 1.0.</span></span> <span data-ttu-id="570de-124">IT 管理員可以建立自己的集合來限制硬體，並可將 MBAM 配置基線部署到這些集合。</span><span class="sxs-lookup"><span data-stu-id="570de-124">IT administrators can create their own collections to limit hardware and can deploy the MBAM configuration baseline to those collections.</span></span> <span data-ttu-id="570de-125">MBAM 1.0 中目前的 MBAM 硬體相容性現在僅提供 MBAM Configuration Manager 拓撲，且是從 Configuration Manager 管理的。</span><span class="sxs-lookup"><span data-stu-id="570de-125">The MBAM hardware compatibility that was present in MBAM 1.0 is now available only in the MBAM Configuration Manager topology and is administered from Configuration Manager.</span></span>

### <span data-ttu-id="570de-126">保護彈性原則</span><span class="sxs-lookup"><span data-stu-id="570de-126">Protectors Flexible Policy</span></span>

<span data-ttu-id="570de-127">已使用保護器加密的電腦（例如，TPM + PIN 或自動解鎖及密碼），而且會收到需要該加密子集的 MBAM 原則（例如，TPM 或自動解鎖）。</span><span class="sxs-lookup"><span data-stu-id="570de-127">Computers that are already encrypted with a protector (for example, TPM + PIN or Auto-Unlock and password) and that receive an MBAM policy that requires a subset of that encryption (for example, TPM or Auto-Unlock) are considered compliant.</span></span> <span data-ttu-id="570de-128">在上述範例中，不會自動移除 PIN 及密碼，除非 IT 系統管理員明確定義這些功能，否則不允許。</span><span class="sxs-lookup"><span data-stu-id="570de-128">In the example above, PIN and password would not be removed automatically unless the IT administrator specifically defines these features as no longer allowed.</span></span>

<span data-ttu-id="570de-129">未加密且接收 MBAM 原則的電腦（例如，TPM 或自動解鎖）會據此加密。</span><span class="sxs-lookup"><span data-stu-id="570de-129">Computers that are not encrypted and that receive an MBAM policy (for example, TPM or Auto-Unlock) are encrypted accordingly.</span></span> <span data-ttu-id="570de-130">擁有本機管理員的使用者可以使用 BitLocker 工具（[控制台專案-BitLocker 磁片磁碟機加密或 manage-bde）] 來新增或修改現有的保護器（例如，TPM + PIN 或自動解鎖及密碼）。</span><span class="sxs-lookup"><span data-stu-id="570de-130">Users who are local administrators are allowed to use the BitLocker tools (Control Panel item BitLocker Drive Encryption or Manage-bde) to add or modify the existing protectors (for example, TPM + PIN or Auto-Unlock and password).</span></span> <span data-ttu-id="570de-131">除非 MBAM 原則明確定義，否則它們會維持合規性。</span><span class="sxs-lookup"><span data-stu-id="570de-131">They remain compliant unless MBAM policies specifically define them.</span></span>

### <span data-ttu-id="570de-132">升級 MBAM 用戶端的能力</span><span class="sxs-lookup"><span data-stu-id="570de-132">Ability to Upgrade the MBAM Client</span></span>

<span data-ttu-id="570de-133">MBAM 2.0 用戶端 Windows 安裝程式會偵測現有用戶端的版本，並執行必要步驟，以升級到舊版的 MBAM 2.0 用戶端。</span><span class="sxs-lookup"><span data-stu-id="570de-133">The MBAM2.0 Client Windows Installer detects the version of the existing client and performs the required steps to upgrade to the MBAM2.0 Client from previous versions.</span></span>

### <span data-ttu-id="570de-134">從舊版升級 MBAM 伺服器的能力</span><span class="sxs-lookup"><span data-stu-id="570de-134">Ability to Upgrade the MBAM Server from Previous Versions</span></span>

<span data-ttu-id="570de-135">您可以從舊版 MBAM 升級 MBAM 2.0 Server 基礎結構，如下所示：</span><span class="sxs-lookup"><span data-stu-id="570de-135">You can upgrade the MBAM2.0 Server infrastructure from previous versions of MBAM as follows:</span></span>

<span data-ttu-id="570de-136">**手動就地伺服器取代**-您必須手動卸載現有的 MBAM 伺服器基礎結構，然後再安裝 MBAM 2.0 server 基礎結構。</span><span class="sxs-lookup"><span data-stu-id="570de-136">**Manual in-place server replacement** – You must manually uninstall the existing MBAM server infrastructure, and then install the MBAM 2.0 Server infrastructure.</span></span> <span data-ttu-id="570de-137">您不需要移除資料庫即可進行升級。</span><span class="sxs-lookup"><span data-stu-id="570de-137">You do not have to remove the databases to do the upgrade.</span></span> <span data-ttu-id="570de-138">相反地，您會選取先前版本的 MBAM 用戶端所建立的現有資料庫。</span><span class="sxs-lookup"><span data-stu-id="570de-138">Instead, you select the existing databases, which the previous version of the MBAM Client created.</span></span> <span data-ttu-id="570de-139">MBAM 2.0 升級安裝接著會將現有的資料庫移轉至 MBAM 2.0。</span><span class="sxs-lookup"><span data-stu-id="570de-139">The MBAM2.0 upgrade installation then migrates the existing databases to MBAM 2.0.</span></span>

<span data-ttu-id="570de-140">**分散式用戶端升級**：如果您使用的是獨立 MBAM 拓朴，您可以在安裝 MBAM 2.0 伺服器基礎結構之後，逐漸升級 MBAM 用戶端。</span><span class="sxs-lookup"><span data-stu-id="570de-140">**Distributed client upgrade** – If you are using the Stand-alone MBAM topology, you can upgrade the MBAM Clients gradually after you install the MBAM 2.0 Server infrastructure.</span></span> <span data-ttu-id="570de-141">MBAM 2.0 伺服器會偵測現有用戶端的版本，並執行所需的步驟以升級至2.0 用戶端。</span><span class="sxs-lookup"><span data-stu-id="570de-141">The MBAM 2.0 Server detects the version of the existing Client and performs the required steps to upgrade to the 2.0 Client.</span></span>

<span data-ttu-id="570de-142">在您升級 MBAM 2.0 伺服器基礎結構之後，MBAM 1.0 用戶端會繼續成功向 MBAM 2.0 伺服器報告，escrowing 復原資料，但合規性將根據 MBAM 1.0 中的原則而定。</span><span class="sxs-lookup"><span data-stu-id="570de-142">After you upgrade the MBAM 2.0 Server infrastructure, MBAM 1.0 Clients continue to report to the MBAM 2.0 Server successfully, escrowing recovery data, but compliance will be based on the policies in MBAM 1.0.</span></span> <span data-ttu-id="570de-143">您必須將用戶端升級至 MBAM 2.0，讓用戶端電腦能根據 MBAM 2.0 原則精確地報告合規性。</span><span class="sxs-lookup"><span data-stu-id="570de-143">You must upgrade clients to MBAM 2.0 to have client computers accurately report compliance against the MBAM 2.0 policies.</span></span> <span data-ttu-id="570de-144">您可以將用戶端升級至 MBAM 2.0 用戶端，而不卸載先前的用戶端，用戶端就會開始套用並報告 MBAM 2.0 原則。</span><span class="sxs-lookup"><span data-stu-id="570de-144">You can upgrade the clients to the MBAM 2.0 Client without uninstalling the previous client, and the client will start to apply and report MBAM 2.0 policies.</span></span>

<span data-ttu-id="570de-145">如果您是使用 MBAM 與 Configuration Manager，您必須將 MBAM 1.0 用戶端升級至 MBAM 2.0。</span><span class="sxs-lookup"><span data-stu-id="570de-145">If you are using MBAM with Configuration Manager, you must upgrade the MBAM 1.0 clients to MBAM 2.0.</span></span>

### <a href="" id="mbam-support-for-bitlocker-s-enterprise-scenarios-on-the-windows-8-platform"></a><span data-ttu-id="570de-146">在 Windows 8 平臺上 MBAM BitLocker 企業案例的支援</span><span class="sxs-lookup"><span data-stu-id="570de-146">MBAM Support for BitLocker’s Enterprise Scenarios on the Windows 8 Platform</span></span>

<span data-ttu-id="570de-147">MBAM 支援 Windows 8 作業系統做為 MBAM 用戶端安裝的目標平臺。</span><span class="sxs-lookup"><span data-stu-id="570de-147">MBAM supports the Windows 8 operating system as a target platform for the MBAM Client installation.</span></span> <span data-ttu-id="570de-148">此支援可讓 IT 系統管理員安裝 MBAM agent、加密 Windows 8 作業系統磁片磁碟機，以及報告電腦合規性。</span><span class="sxs-lookup"><span data-stu-id="570de-148">This support enables IT administrators to install the MBAM agent, to encrypt Windows 8 operating system drives, and to report on the compliance of the computers.</span></span> <span data-ttu-id="570de-149">MBAM 利用 TPM 和 TPM + PIN 保護器來管理 Windows 8 作業系統，就像在 Windows 7 作業系統中一樣。</span><span class="sxs-lookup"><span data-stu-id="570de-149">MBAM leverages the TPM and TPM+PIN protectors to manage the Windows 8 operating system just as it does the Windows 7 operating system.</span></span> <span data-ttu-id="570de-150">MBAM 2.0 也會新增加密 Windows 的支援以取得用戶端。</span><span class="sxs-lookup"><span data-stu-id="570de-150">MBAM2.0 also adds support for encrypting Windows To Go clients.</span></span>

### <span data-ttu-id="570de-151">自助服務入口網站的新增</span><span class="sxs-lookup"><span data-stu-id="570de-151">Addition of the Self-Service Portal</span></span>

<span data-ttu-id="570de-152">最終使用者現在可以使用自助入口網站來復原其修復金鑰。</span><span class="sxs-lookup"><span data-stu-id="570de-152">End users can now use the Self-Service Portal to recover their recovery keys.</span></span> <span data-ttu-id="570de-153">自助式入口網站可以使用其他 MBAM 功能部署在單一伺服器上，或在獨立的伺服器上，讓 IT 系統管理員能根據需要將自助式入口網站公開給使用者。</span><span class="sxs-lookup"><span data-stu-id="570de-153">The Self-Service Portal can be deployed on a single server with the other MBAM features, or on a separate server that gives IT administrators the flexibility to expose the Self-Server Portal to users, as required.</span></span> <span data-ttu-id="570de-154">在自助入口網站驗證使用者之後，使用者只需要輸入復原金鑰識別碼的前八位數，即可接收其修復金鑰。</span><span class="sxs-lookup"><span data-stu-id="570de-154">After the Self-Service Portal authenticates users, users have to enter only the first eight digits of the recovery key ID to receive their recovery key.</span></span>

<span data-ttu-id="570de-155">MBAM 也可以讓使用者只針對使用者的電腦復原金鑰來保護金鑰，這會減少其他使用者獲得未經授權存取的風險。</span><span class="sxs-lookup"><span data-stu-id="570de-155">MBAM also secures the key by allowing users to recover keys only for those computers on which they are users, which reduces the risk that other users gain unauthorized access.</span></span>

### <span data-ttu-id="570de-156">自動從暫停狀態繼續 BitLocker 保護的功能</span><span class="sxs-lookup"><span data-stu-id="570de-156">Ability to Automatically Resume BitLocker Protection from a Suspended State</span></span>

<span data-ttu-id="570de-157">MBAM 不允許 IT 系統管理員將 BitLocker 保持暫停狀態，並在長時間內受到保護。</span><span class="sxs-lookup"><span data-stu-id="570de-157">MBAM no longer allows IT administrators to keep BitLocker suspended and unprotected for prolonged periods of time.</span></span> <span data-ttu-id="570de-158">如果 IT 系統管理員暫停 BitLocker，MBAM 會在電腦重新開機時自動重新啟用，這會降低電腦可能受到攻擊的風險。</span><span class="sxs-lookup"><span data-stu-id="570de-158">If an IT administrator suspends BitLocker, MBAM re-enables it automatically when the computer is rebooted, which reduces the risk that the computer can be attacked.</span></span>

### <span data-ttu-id="570de-159">固定資料磁碟機可以設定為自動解除鎖定而不需要密碼</span><span class="sxs-lookup"><span data-stu-id="570de-159">Fixed Data Drives Can Be Configured to Automatically Unlock Without a Password</span></span>

<span data-ttu-id="570de-160">您現在可以將固定資料磁碟機（FDD）原則設定為允許自動解鎖磁片磁碟機（不需密碼）。</span><span class="sxs-lookup"><span data-stu-id="570de-160">A Fixed Data Drive (FDD) policy can now be configured to allow automatic unlocking of the drive without a password.</span></span> <span data-ttu-id="570de-161">在加密 FDD 之前，系統不會提示使用者輸入密碼，而且 FDD 會受到保護，並自動解除鎖定作業系統磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="570de-161">Users are not prompted for a password before the FDD is encrypted, and the FDD will be secured and auto-unlocked with the operating system drive.</span></span>

## <a href="" id="---------mbam-2-0-release-notes"></a> <span data-ttu-id="570de-162">MBAM 2.0 版本資訊</span><span class="sxs-lookup"><span data-stu-id="570de-162">MBAM2.0 Release Notes</span></span>


<span data-ttu-id="570de-163">如需詳細資訊，以及不包含在檔中的最新新聞，請參閱[MBAM 2.0 的版本](release-notes-for-mbam-20-mbam-2.md)資訊。</span><span class="sxs-lookup"><span data-stu-id="570de-163">For more information, and for late-breaking news that is not included in the documentation, see the [Release Notes for MBAM 2.0](release-notes-for-mbam-20-mbam-2.md).</span></span>

## <span data-ttu-id="570de-164">如何取得 MBAM 2。0</span><span class="sxs-lookup"><span data-stu-id="570de-164">How to Get MBAM2.0</span></span>


<span data-ttu-id="570de-165">這項技術是 Microsoft 桌面優化套件（MDOP）的一部分。</span><span class="sxs-lookup"><span data-stu-id="570de-165">This technology is a part of the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="570de-166">企業客戶可以使用 Microsoft 軟體保證進行 MDOP。</span><span class="sxs-lookup"><span data-stu-id="570de-166">Enterprise customers can get MDOP with Microsoft Software Assurance.</span></span> <span data-ttu-id="570de-167">如需 Microsoft 軟體保證及取得 MDOP 的詳細資訊，請參閱[如何取得 mdop？](https://go.microsoft.com/fwlink/p/?LinkId=322049)</span><span class="sxs-lookup"><span data-stu-id="570de-167">For more information about Microsoft Software Assurance and acquiring MDOP, see [How Do I Get MDOP?](https://go.microsoft.com/fwlink/p/?LinkId=322049)</span></span>

## <span data-ttu-id="570de-168">相關主題</span><span class="sxs-lookup"><span data-stu-id="570de-168">Related topics</span></span>


[<span data-ttu-id="570de-169">開始使用 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="570de-169">Getting Started with MBAM 2.0</span></span>](getting-started-with-mbam-20-mbam-2.md)

 

 





