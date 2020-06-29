---
title: 協助使用者管理 BitLocker
description: 協助使用者管理 BitLocker
author: dansimp
ms.assetid: 47776fb3-2d94-4970-b687-c35ec3dd6c64
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 26ef2bc33a75ff7773b75807ab0e10e5aa67b109
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810760"
---
# <span data-ttu-id="d51bb-103">協助使用者管理 BitLocker</span><span class="sxs-lookup"><span data-stu-id="d51bb-103">Helping End Users Manage BitLocker</span></span>


<span data-ttu-id="d51bb-104">遺失或被盜電腦上的內容容易受到未經授權的存取，這可能會給人員和公司帶來安全風險。</span><span class="sxs-lookup"><span data-stu-id="d51bb-104">Content on a lost or stolen computer is vulnerable to unauthorized access, which can present a security risk to both people and companies.</span></span> <span data-ttu-id="d51bb-105">Microsoft BitLocker 管理和監控（MBAM）使用 BitLocker 來封鎖您的電腦，協助保護機密資料免遭惡意使用者，以協助防止未經授權的存取。</span><span class="sxs-lookup"><span data-stu-id="d51bb-105">Microsoft BitLocker Administration and Monitoring (MBAM) uses BitLocker to help prevent unauthorized access by locking your computer to help protect sensitive data from malicious users.</span></span>

## <span data-ttu-id="d51bb-106">什麼是 BitLocker？</span><span class="sxs-lookup"><span data-stu-id="d51bb-106">What is BitLocker?</span></span>


<span data-ttu-id="d51bb-107">BitLocker 磁片磁碟機加密可為作業系統磁片磁碟機、資料磁碟機及抽取式磁碟磁碟機（例如 USB 拇指磁片磁碟機）提供保護，方法是加密磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="d51bb-107">BitLocker Drive Encryption can provide protection for operating system drives, data drives, and removable drives (such as a USB thumb drive) by encrypting the drives.</span></span> <span data-ttu-id="d51bb-108">根據 BitLocker 的設定方式而定，使用者可能需要提供金鑰（密碼或 PIN）來解除鎖定儲存在加密磁片磁碟機上的資訊。</span><span class="sxs-lookup"><span data-stu-id="d51bb-108">Depending on how BitLocker is configured, users may have to provide a key (a password or PIN) to unlock the information that is stored on the encrypted drives.</span></span>

<span data-ttu-id="d51bb-109">當您將新檔案新增至以 BitLocker 加密的磁片磁碟機時，BitLocker 會自動加密這些檔案。</span><span class="sxs-lookup"><span data-stu-id="d51bb-109">When you add new files to a drive that is encrypted with BitLocker, BitLocker encrypts them automatically.</span></span> <span data-ttu-id="d51bb-110">檔案只有在儲存在加密的磁碟機中時，才會保持加密。</span><span class="sxs-lookup"><span data-stu-id="d51bb-110">Files remain encrypted only while they are stored in the encrypted drive.</span></span> <span data-ttu-id="d51bb-111">複製到其他磁片磁碟機或電腦的檔案會解密。</span><span class="sxs-lookup"><span data-stu-id="d51bb-111">Files that are copied to another drive or computer are decrypted.</span></span> <span data-ttu-id="d51bb-112">如果您與其他使用者共用檔案（例如透過網路），這些檔案會在儲存在加密的磁片磁碟機上時加密，但授權使用者可以正常存取這些檔案。</span><span class="sxs-lookup"><span data-stu-id="d51bb-112">If you share files with other users, such as through a network, these files are encrypted while stored on the encrypted drive, but they can be accessed normally by authorized users.</span></span>

<span data-ttu-id="d51bb-113">如果您加密作業系統磁片磁碟機，BitLocker 會在啟動期間檢查可能代表安全性風險的任何情況（例如，BIOS 變更或對任何啟動檔案所做的變更）。</span><span class="sxs-lookup"><span data-stu-id="d51bb-113">If you encrypt the operating system drive, BitLocker checks the computer during startup for any conditions that could represent a security risk (for example, a change to the BIOS or changes to any startup files).</span></span> <span data-ttu-id="d51bb-114">如果偵測到潛在的安全性風險，BitLocker 會鎖定操作系統磁碟機，並需要特殊的 BitLocker 復原金鑰來解除鎖定。</span><span class="sxs-lookup"><span data-stu-id="d51bb-114">If a potential security risk is detected, BitLocker will lock the operating system drive and require a special BitLocker recovery key to unlock it.</span></span> <span data-ttu-id="d51bb-115">請務必在您第一次開啟 BitLocker 時建立此復原金鑰。</span><span class="sxs-lookup"><span data-stu-id="d51bb-115">Make sure that you create this recovery key when you turn on BitLocker for the first time.</span></span> <span data-ttu-id="d51bb-116">否則，您可能會永久無法存取您的檔案。</span><span class="sxs-lookup"><span data-stu-id="d51bb-116">Otherwise, you could permanently lose access to your files.</span></span>

<span data-ttu-id="d51bb-117">如果您加密資料磁碟機（固定或移除），您可以使用密碼或智慧卡解除封鎖加密的磁片磁碟機，或將磁碟機設定為在您登入電腦時自動解鎖。</span><span class="sxs-lookup"><span data-stu-id="d51bb-117">If you encrypt data drives (fixed or removable), you can unlock an encrypted drive with a password or a smart card, or set the drive to automatically unlock when you log on to the computer.</span></span>

<span data-ttu-id="d51bb-118">除了密碼及 Pin，BitLocker 還可以使用在許多較新的電腦中提供的信任平臺模組（TPM）晶片。</span><span class="sxs-lookup"><span data-stu-id="d51bb-118">In addition to passwords and PINs, BitLocker can use the Trusted Platform Module (TPM) chip that is provided in many newer computers.</span></span> <span data-ttu-id="d51bb-119">TPM 晶片會用來確保您的電腦在 BitLocker 解除鎖定作業系統磁片磁碟機之前，沒有被篡改。</span><span class="sxs-lookup"><span data-stu-id="d51bb-119">The TPM chip is used to ensure that your computer has not been tampered with before BitLocker will unlock the operating system drive.</span></span> <span data-ttu-id="d51bb-120">在加密過程中，您可能必須啟用 TPM 晶片。</span><span class="sxs-lookup"><span data-stu-id="d51bb-120">During the encryption process, you may have to enable the TPM chip.</span></span> <span data-ttu-id="d51bb-121">當您啟動電腦時，BitLocker 會要求 TPM 提供磁片磁碟機金鑰並將其解除鎖定。</span><span class="sxs-lookup"><span data-stu-id="d51bb-121">When you start your computer, BitLocker asks the TPM for the keys to the drive and unlocks it.</span></span> <span data-ttu-id="d51bb-122">若要啟用 TPM 晶片，您必須重新開機電腦，然後在 BIOS （電腦軟體的 Windows 層）中變更設定。</span><span class="sxs-lookup"><span data-stu-id="d51bb-122">To enable the TPM chip, you will have to restart your computer and then change a setting in the BIOS, a pre-Windows layer of your computer software.</span></span> <span data-ttu-id="d51bb-123">如需 TPM 的詳細資訊，請參閱[關於電腦 TPM 晶片](about-the-computer-tpm-chip.md)。</span><span class="sxs-lookup"><span data-stu-id="d51bb-123">For more information about the TPM, see [About the Computer TPM Chip](about-the-computer-tpm-chip.md).</span></span>

<span data-ttu-id="d51bb-124">一旦您的電腦受到 BitLocker 保護之後，您可能必須在電腦從休眠中醒來或啟動時，輸入 PIN 或密碼。</span><span class="sxs-lookup"><span data-stu-id="d51bb-124">Once your computer is protected by BitLocker, you may have to enter a PIN or password every time that the computer wakes from hibernation or starts.</span></span> <span data-ttu-id="d51bb-125">如果您忘記 PIN 或密碼，貴公司或組織的技術支援人員就可以協助您。</span><span class="sxs-lookup"><span data-stu-id="d51bb-125">The Help Desk for your company or organization can help if you ever forget your PIN or password.</span></span>

<span data-ttu-id="d51bb-126">您可以透過解密磁片磁碟機，暫時關閉 BitLocker，或將它永久封存。</span><span class="sxs-lookup"><span data-stu-id="d51bb-126">You can turn off BitLocker, either temporarily, by suspending it, or permanently, by decrypting the drive.</span></span>

<span data-ttu-id="d51bb-127">**記事** 因為 BitLocker 會加密整個磁片磁碟機，而不只是個別檔案本身，所以當您在磁碟機之間移動機密資料時，請務必小心。</span><span class="sxs-lookup"><span data-stu-id="d51bb-127">**Note** Because BitLocker encrypts the whole drive and not just the individual files themselves, be careful when you move sensitive data between drives.</span></span> <span data-ttu-id="d51bb-128">如果您將檔案從受 BitLocker 保護的磁碟機移至未加密的磁片磁碟機，就不會再加密該檔案。</span><span class="sxs-lookup"><span data-stu-id="d51bb-128">If you move a file from a BitLocker-protected drive to a nonencrypted drive, the file will no longer be encrypted.</span></span>

 

## <span data-ttu-id="d51bb-129">關於 BitLocker 加密選項應用程式</span><span class="sxs-lookup"><span data-stu-id="d51bb-129">About the BitLocker Encryption Options Application</span></span>


<span data-ttu-id="d51bb-130">若要在電腦上解除鎖定硬碟，以及管理 PIN 與密碼，請按照這裡所述的程式，使用 Windows [控制台] 中的 [BitLocker 加密選項] 應用程式。</span><span class="sxs-lookup"><span data-stu-id="d51bb-130">To unlock hard disk drives on your computer and to manage your PIN and passwords, use the BitLocker Encryption Options application in the Windows Control Panel by following the procedure outlined here.</span></span> <span data-ttu-id="d51bb-131">您可以輸入密碼來解除鎖定受保護的磁片磁碟機，並且可以使用此應用程式檢查附加的磁碟機的 BitLocker 狀態。</span><span class="sxs-lookup"><span data-stu-id="d51bb-131">You can enter passwords to unlock protected drives and can check the BitLocker status of attached drives by using this application.</span></span>

**<span data-ttu-id="d51bb-132">開啟 BitLocker 加密選項應用程式</span><span class="sxs-lookup"><span data-stu-id="d51bb-132">To open the BitLocker Encryption Options application</span></span>**

1.  <span data-ttu-id="d51bb-133">按一下 [**開始**]，然後選取 [**控制台**]。</span><span class="sxs-lookup"><span data-stu-id="d51bb-133">Click **Start**, and select **Control Panel**.</span></span> <span data-ttu-id="d51bb-134">[控制] 面板隨即會在新視窗中開啟。</span><span class="sxs-lookup"><span data-stu-id="d51bb-134">The Control Panel opens in a new window.</span></span>

2.  <span data-ttu-id="d51bb-135">在 [**控制台**] 中，選取 [**系統及安全性**]。</span><span class="sxs-lookup"><span data-stu-id="d51bb-135">In **Control Panel**, select **System and Security**.</span></span>

3.  <span data-ttu-id="d51bb-136">選取 [ **Bitlocker 加密選項**] 以開啟 Bitlocker 加密選項應用程式。</span><span class="sxs-lookup"><span data-stu-id="d51bb-136">Select **BitLocker Encryption Options** to open the BitLocker Encryption Options application.</span></span>

    <span data-ttu-id="d51bb-137">如需可用選項的說明，請參閱下一節。</span><span class="sxs-lookup"><span data-stu-id="d51bb-137">For a description of the available options, see the following section.</span></span>

## <span data-ttu-id="d51bb-138">BitLocker 加密選項應用程式上的選項</span><span class="sxs-lookup"><span data-stu-id="d51bb-138">Options on the BitLocker Encryption Options Application</span></span>


<span data-ttu-id="d51bb-139">[控制台] 上的 [BitLocker 加密選項] 應用程式可讓您管理 PIN 及密碼，以保護您的電腦。</span><span class="sxs-lookup"><span data-stu-id="d51bb-139">The BitLocker Encryption Options application on Control Panel lets you manage your PIN and passwords, which BitLocker uses to protect your computer.</span></span>

**<span data-ttu-id="d51bb-140">BitLocker 磁片磁碟機加密-固定磁片磁碟機：</span><span class="sxs-lookup"><span data-stu-id="d51bb-140">BitLocker Drive Encryption – Fixed Disk Drives:</span></span>**

<span data-ttu-id="d51bb-141">在此區段中，您可以查看連線至電腦的硬碟磁片磁碟機及其目前的 BitLocker 加密狀態的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="d51bb-141">In this section, you can view information about hard disk drives connected to your computer and their current BitLocker Encryption status.</span></span>

-   <span data-ttu-id="d51bb-142">**管理您的 PIN** -變更 BitLocker 所用的 pin 來解除作業系統磁片磁碟機的鎖定。</span><span class="sxs-lookup"><span data-stu-id="d51bb-142">**Manage your PIN** - changes the PIN used by BitLocker to unlock your operating system drive.</span></span>

-   <span data-ttu-id="d51bb-143">**管理您的密碼**-變更 BitLocker 所用的密碼，以解除鎖定其他內部磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="d51bb-143">**Manage your password** - changes the password that is used by BitLocker to unlock your other internal drives.</span></span>

**<span data-ttu-id="d51bb-144">BitLocker 磁片磁碟機加密-外部磁片磁碟機：</span><span class="sxs-lookup"><span data-stu-id="d51bb-144">BitLocker Drive Encryption - External Drives:</span></span>**

<span data-ttu-id="d51bb-145">在此區段中，您可以查看連線至電腦的外部磁片磁碟機（例如 USB 拇指磁片磁碟機），以及其目前的 BitLocker 加密狀態。</span><span class="sxs-lookup"><span data-stu-id="d51bb-145">In this section, you can view information about external drives (such as a USB thumb drive) connected to your computer, and their current BitLocker encryption status.</span></span>

-   <span data-ttu-id="d51bb-146">**管理您的密碼**-變更 BitLocker 所用的密碼，以解除鎖定其他內部磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="d51bb-146">**Manage your password** - changes the password that is used by BitLocker to unlock your other internal drives.</span></span>

**<span data-ttu-id="d51bb-147">進階</span><span class="sxs-lookup"><span data-stu-id="d51bb-147">Advanced:</span></span>**

-   <span data-ttu-id="d51bb-148">**Tpm 管理**-在個別視窗中開啟 TPM 管理工具。</span><span class="sxs-lookup"><span data-stu-id="d51bb-148">**TPM Administration** - opens the TPM Administration tool in a separate window.</span></span> <span data-ttu-id="d51bb-149">您可以從這裡設定常見的 TPM 工作，並取得 TPM 晶片集的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="d51bb-149">From here you can configure common TPM tasks and obtain information about the TPM chipset.</span></span> <span data-ttu-id="d51bb-150">您必須具備電腦的系統管理員許可權，才能存取此工具。</span><span class="sxs-lookup"><span data-stu-id="d51bb-150">You must have administrative permissions on your computer to access this tool.</span></span>

-   <span data-ttu-id="d51bb-151">**磁片管理**-開啟磁片管理工具。</span><span class="sxs-lookup"><span data-stu-id="d51bb-151">**Disk Management** -open the Disk Management tool.</span></span> <span data-ttu-id="d51bb-152">您可以從這裡查看連接至電腦的所有硬碟資訊，並設定分區和磁片磁碟機選項。</span><span class="sxs-lookup"><span data-stu-id="d51bb-152">From here you can view the information for all hard drives connected to the computer and configure partitions and drive options.</span></span> <span data-ttu-id="d51bb-153">您必須具備電腦的系統管理員許可權，才能存取此工具。</span><span class="sxs-lookup"><span data-stu-id="d51bb-153">You must have administrative rights on your computer to access this tool.</span></span>

 

 





