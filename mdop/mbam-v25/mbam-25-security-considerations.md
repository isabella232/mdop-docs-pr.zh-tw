---
title: MBAM 2.5 安全性考量
description: MBAM 2.5 安全性考量
author: dansimp
ms.assetid: f6613c63-b32b-45fb-a6e8-673d6dae7d16
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 04/23/2017
ms.openlocfilehash: 86a756ab6f983fa1f22de6835b5993e1215d1dbe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811996"
---
# <span data-ttu-id="794af-103">MBAM 2.5 安全性考量</span><span class="sxs-lookup"><span data-stu-id="794af-103">MBAM 2.5 Security Considerations</span></span>


<span data-ttu-id="794af-104">本主題包含有關如何保護 Microsoft BitLocker 管理與監視（MBAM）的下列相關資訊：</span><span class="sxs-lookup"><span data-stu-id="794af-104">This topic contains the following information about how to secure Microsoft BitLocker Administration and Monitoring (MBAM):</span></span>

-   [<span data-ttu-id="794af-105">設定 MBAM 以保管 TPM 並儲存 OwnerAuth 密碼</span><span class="sxs-lookup"><span data-stu-id="794af-105">Configure MBAM to escrow the TPM and store OwnerAuth passwords</span></span>](#bkmk-tpm)

-   [<span data-ttu-id="794af-106">設定 MBAM 在封鎖之後自動解除鎖定 TPM</span><span class="sxs-lookup"><span data-stu-id="794af-106">Configure MBAM to automatically unlock the TPM after a lockout</span></span>](#bkmk-autounlock)

-   [<span data-ttu-id="794af-107">安全連線至 SQL Server</span><span class="sxs-lookup"><span data-stu-id="794af-107">Secure connections to SQL Server</span></span>](#bkmk-secure-databases)

-   [<span data-ttu-id="794af-108">建立帳戶和群組</span><span class="sxs-lookup"><span data-stu-id="794af-108">Create accounts and groups</span></span>](#bkmk-accts-groups)

-   [<span data-ttu-id="794af-109">使用 MBAM 記錄檔</span><span class="sxs-lookup"><span data-stu-id="794af-109">Use MBAM log files</span></span>](#bkmk-logfiles)

-   [<span data-ttu-id="794af-110">審閱 MBAM 資料庫 TDE 考慮</span><span class="sxs-lookup"><span data-stu-id="794af-110">Review MBAM database TDE considerations</span></span>](#bkmk-tde)

-   [<span data-ttu-id="794af-111">瞭解一般的安全性考慮</span><span class="sxs-lookup"><span data-stu-id="794af-111">Understand general security considerations</span></span>](#bkmk-general-security)

## <a href="" id="bkmk-tpm"></a><span data-ttu-id="794af-112">設定 MBAM 以保管 TPM 並儲存 OwnerAuth 密碼</span><span class="sxs-lookup"><span data-stu-id="794af-112">Configure MBAM to escrow the TPM and store OwnerAuth passwords</span></span>

<span data-ttu-id="794af-113">**記事**如果您使用的是 Windows 10 版本1607或更新版本，則只有 Windows 可以取得 TPM 擁有權。</span><span class="sxs-lookup"><span data-stu-id="794af-113">**Note** For Windows 10, version 1607 or later, only Windows can take ownership of the TPM.</span></span> <span data-ttu-id="794af-114">此外，Windows 不會在預配 TPM 時保留 TPM 擁有者密碼。</span><span class="sxs-lookup"><span data-stu-id="794af-114">In addition, Windows will not retain the TPM owner password when provisioning the TPM.</span></span> <span data-ttu-id="794af-115">如需詳細資訊，請參閱[TPM 擁有者密碼](https://docs.microsoft.com/windows/security/information-protection/tpm/change-the-tpm-owner-password)。</span><span class="sxs-lookup"><span data-stu-id="794af-115">See [TPM owner password](https://docs.microsoft.com/windows/security/information-protection/tpm/change-the-tpm-owner-password) for further details.</span></span>

<span data-ttu-id="794af-116">根據它的設定而定，受信任的平臺模組（TPM）會在某些情況下（例如當輸入了太多不正確的密碼），並在一段時間內保持鎖定。</span><span class="sxs-lookup"><span data-stu-id="794af-116">Depending on its configuration, the Trusted Platform Module (TPM) will lock itself in certain situations ─ such as when too many incorrect passwords are entered ─ and can remain locked for a period of time.</span></span> <span data-ttu-id="794af-117">在 TPM 封鎖期間，BitLocker 無法存取加密金鑰來執行解除鎖定或解密作業，要求使用者輸入其 BitLocker 復原金鑰來存取作業系統磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="794af-117">During TPM lockout, BitLocker cannot access the encryption keys to perform unlock or decryption operations, requiring the user to enter their BitLocker recovery key to access the operating system drive.</span></span> <span data-ttu-id="794af-118">若要重設 TPM 封鎖，您必須提供 TPM OwnerAuth 密碼。</span><span class="sxs-lookup"><span data-stu-id="794af-118">To reset TPM lockout, you must provide the TPM OwnerAuth password.</span></span>

<span data-ttu-id="794af-119">如果 MBAM 擁有 TPM，或如果它 escrows 密碼，則可以將 TPM OwnerAuth 密碼儲存在 MBAM 資料庫中。</span><span class="sxs-lookup"><span data-stu-id="794af-119">MBAM can store the TPM OwnerAuth password in the MBAM database if it owns the TPM or if it escrows the password.</span></span> <span data-ttu-id="794af-120">當您必須從 TPM 封鎖中復原時，可以在 [管理] 和 [監視] 網站上輕鬆存取 OwnerAuth 密碼，不需要等到鎖定自行自行解決。</span><span class="sxs-lookup"><span data-stu-id="794af-120">OwnerAuth passwords are then easily accessible on the Administration and Monitoring Website when you must recover from a TPM lockout, eliminating the need to wait for the lockout to resolve on its own.</span></span>

### <span data-ttu-id="794af-121">Escrowing 在 Windows 8 及更高版本中的 TPM OwnerAuth</span><span class="sxs-lookup"><span data-stu-id="794af-121">Escrowing TPM OwnerAuth in Windows 8 and higher</span></span>

<span data-ttu-id="794af-122">**記事**如果您使用的是 Windows 10 版本1607或更新版本，則只有 Windows 可以取得 TPM 擁有權。</span><span class="sxs-lookup"><span data-stu-id="794af-122">**Note** For Windows 10, version 1607 or later, only Windows can take ownership of the TPM.</span></span> <span data-ttu-id="794af-123">在 addiiton 中，Windows 將不會在預配 TPM 時保留 TPM 擁有者密碼。</span><span class="sxs-lookup"><span data-stu-id="794af-123">In addiiton, Windows will not retain the TPM owner password when provisioning the TPM.</span></span> <span data-ttu-id="794af-124">如需詳細資訊，請參閱[TPM 擁有者密碼](https://docs.microsoft.com/windows/security/information-protection/tpm/change-the-tpm-owner-password)。</span><span class="sxs-lookup"><span data-stu-id="794af-124">See [TPM owner password](https://docs.microsoft.com/windows/security/information-protection/tpm/change-the-tpm-owner-password) for further details.</span></span>

<span data-ttu-id="794af-125">在 Windows 8 或更高版本中，MBAM 不必須擁有 TPM，就能儲存 OwnerAuth 密碼（只要本機電腦上提供 OwnerAuth 即可）。</span><span class="sxs-lookup"><span data-stu-id="794af-125">In Windows 8 or higher, MBAM no longer must own the TPM to store the OwnerAuth password, as long as the OwnerAuth is available on the local machine.</span></span>

<span data-ttu-id="794af-126">若要讓 MBAM 能夠進行保管，然後儲存 TPM OwnerAuth 密碼，您必須設定這些群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="794af-126">To enable MBAM to escrow and then store TPM OwnerAuth passwords, you must configure these Group Policy settings.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="794af-127">群組原則設定</span><span class="sxs-lookup"><span data-stu-id="794af-127">Group Policy Setting</span></span></th>
<th align="left"><span data-ttu-id="794af-128">設定</span><span class="sxs-lookup"><span data-stu-id="794af-128">Configuration</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="794af-129">開啟 TPM 備份至 Active Directory 網域服務</span><span class="sxs-lookup"><span data-stu-id="794af-129">Turn on TPM backup to Active Directory Domain Services</span></span></p></td>
<td align="left"><p><span data-ttu-id="794af-130">停用或未設定</span><span class="sxs-lookup"><span data-stu-id="794af-130">Disabled or Not Configured</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="794af-131">設定作業系統可用的 TPM 擁有者授權資訊層級</span><span class="sxs-lookup"><span data-stu-id="794af-131">Configure the level of TPM owner authorization information available to the operating system</span></span></p></td>
<td align="left"><p><span data-ttu-id="794af-132">已委派/無或未設定</span><span class="sxs-lookup"><span data-stu-id="794af-132">Delegated/None or Not Configured</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="794af-133">這些群組原則設定的位置是 [**電腦**設定] &gt; 系統**管理範本** &gt; **系統** &gt; **受信任的平臺模組服務**。</span><span class="sxs-lookup"><span data-stu-id="794af-133">The location of these Group Policy settings is **Computer Configuration** &gt; **Administrative Templates** &gt; **System** &gt; **Trusted Platform Module Services**.</span></span>

<span data-ttu-id="794af-134">**記事** 在 MBAM 成功 escrows 使用這些設定之後，Windows 會移除在本機的 OwnerAuth。</span><span class="sxs-lookup"><span data-stu-id="794af-134">**Note** Windows removes the OwnerAuth locally after MBAM successfully escrows it with these settings.</span></span>

 

### <span data-ttu-id="794af-135">在 Windows 7 中 Escrowing TPM OwnerAuth</span><span class="sxs-lookup"><span data-stu-id="794af-135">Escrowing TPM OwnerAuth in Windows 7</span></span>

<span data-ttu-id="794af-136">在 Windows 7 中，MBAM 必須擁有 TPM，才能在 MBAM 資料庫中自動委託 TPM OwnerAuth 資訊。</span><span class="sxs-lookup"><span data-stu-id="794af-136">In Windows 7, MBAM must own the TPM to automatically escrow TPM OwnerAuth information in the MBAM database.</span></span> <span data-ttu-id="794af-137">如果 MBAM 不擁有 TPM，您必須使用 MBAM Active Directory （AD）資料匯入 Cmdlet，將 TPM OwnerAuth 從 Active Directory 複製到 MBAM 資料庫。</span><span class="sxs-lookup"><span data-stu-id="794af-137">If MBAM does not own the TPM, you must use the MBAM Active Directory (AD) Data Import cmdlets to copy TPM OwnerAuth from Active Directory into the MBAM database.</span></span>

### <span data-ttu-id="794af-138">MBAM Active Directory 資料匯入 Cmdlet</span><span class="sxs-lookup"><span data-stu-id="794af-138">MBAM Active Directory Data Import cmdlets</span></span>

<span data-ttu-id="794af-139">MBAM Active Directory 資料匯入 Cmdlet 可讓您檢索儲存在 Active Directory 中的復原金鑰套件和 OwnerAuth 密碼。</span><span class="sxs-lookup"><span data-stu-id="794af-139">The MBAM Active Directory Data Import cmdlets let you retrieve recovery key packages and OwnerAuth passwords that are stored in Active Directory.</span></span>

<span data-ttu-id="794af-140">MBAM 2.5 SP1 伺服器隨附四個 PowerShell Cmdlet，這些 Cmdlet 會使用儲存在 Active Directory 中的大量復原及 TPM 擁有者資訊預先填入 MBAM 資料庫。</span><span class="sxs-lookup"><span data-stu-id="794af-140">The MBAM 2.5 SP1 server ships with four PowerShell cmdlets that pre-populate MBAM databases with the Volume recovery and TPM owner information stored in Active Directory.</span></span>

<span data-ttu-id="794af-141">針對批量復原金鑰和套件：</span><span class="sxs-lookup"><span data-stu-id="794af-141">For Volume Recovery keys and packages:</span></span>

-   <span data-ttu-id="794af-142">讀取 ADRecoveryInformation</span><span class="sxs-lookup"><span data-stu-id="794af-142">Read-ADRecoveryInformation</span></span>

-   <span data-ttu-id="794af-143">寫入 MbamRecoveryInformation</span><span class="sxs-lookup"><span data-stu-id="794af-143">Write-MbamRecoveryInformation</span></span>

<span data-ttu-id="794af-144">針對 TPM 擁有者資訊：</span><span class="sxs-lookup"><span data-stu-id="794af-144">For TPM Owner Information:</span></span>

-   <span data-ttu-id="794af-145">讀取 ADTpmInformation</span><span class="sxs-lookup"><span data-stu-id="794af-145">Read-ADTpmInformation</span></span>

-   <span data-ttu-id="794af-146">寫入 MbamTpmInformation</span><span class="sxs-lookup"><span data-stu-id="794af-146">Write-MbamTpmInformation</span></span>

<span data-ttu-id="794af-147">若要將使用者與電腦建立關聯：</span><span class="sxs-lookup"><span data-stu-id="794af-147">For Associating Users to Computers:</span></span>

-   <span data-ttu-id="794af-148">寫入 MbamComputerUser</span><span class="sxs-lookup"><span data-stu-id="794af-148">Write-MbamComputerUser</span></span>

<span data-ttu-id="794af-149">Read AD \ \* Cmdlet 會讀取 Active Directory 中的資訊。</span><span class="sxs-lookup"><span data-stu-id="794af-149">The Read-AD\* cmdlets read information from Active Directory.</span></span> <span data-ttu-id="794af-150">Write Mbam \ \* Cmdlet 會將資料推入 MBAM 資料庫。</span><span class="sxs-lookup"><span data-stu-id="794af-150">The Write-Mbam\* cmdlets push the data into the MBAM databases.</span></span> <span data-ttu-id="794af-151">如需這些 Cmdlet 的詳細資訊（包括語法、參數及範例），請參閱[Microsoft Bitlocker 管理和監視2.5 的 Cmdlet 參考](https://technet.microsoft.com/library/dn459018.aspx)。</span><span class="sxs-lookup"><span data-stu-id="794af-151">See [Cmdlet Reference for Microsoft Bitlocker Administration and Monitoring 2.5](https://technet.microsoft.com/library/dn459018.aspx) for detailed information about these cmdlets, including syntax, parameters, and examples.</span></span>

<span data-ttu-id="794af-152">**建立使用者對電腦的關聯：** MBAM Active Directory 資料匯入 Cmdlet 會收集 Active Directory 中的資訊，並將資料插入 MBAM 資料庫中。</span><span class="sxs-lookup"><span data-stu-id="794af-152">**Create user-to-computer associations:** The MBAM Active Directory Data Import cmdlets gather information from Active Directory and insert the data into MBAM database.</span></span> <span data-ttu-id="794af-153">不過，它們不會將使用者與卷建立關聯。</span><span class="sxs-lookup"><span data-stu-id="794af-153">However, they do not associate users to volumes.</span></span> <span data-ttu-id="794af-154">您可以下載 Add-ComputerUser.ps1 PowerShell 腳本來建立使用者對電腦的關聯，這可讓使用者透過管理和監控網站或使用自助入口網站進行復原來重新取得電腦的存取權。</span><span class="sxs-lookup"><span data-stu-id="794af-154">You can download the Add-ComputerUser.ps1 PowerShell script to create user-to-machine associations, which let users regain access to a computer through the Administration and Monitoring Website or by using the Self-Service Portal for recovery.</span></span> <span data-ttu-id="794af-155">Add-ComputerUser.ps1 腳本會從 Active Directory （AD）、AD 中的物件擁有者，或從自訂的 CSV 檔案，收集**由受管理的 By**屬性所管理的資料。</span><span class="sxs-lookup"><span data-stu-id="794af-155">The Add-ComputerUser.ps1 script gathers data from the **Managed By** attribute in Active Directory (AD), the object owner in AD, or from a custom CSV file.</span></span> <span data-ttu-id="794af-156">然後，腳本會將已發現的使用者新增到復原資訊管道物件，必須傳遞到寫 MbamRecoveryInformation，才能將資料插入到損毀修復資料庫中。</span><span class="sxs-lookup"><span data-stu-id="794af-156">The script then adds the discovered users to the recovery information pipeline object, which must be passed to Write-MbamRecoveryInformation to insert the data into the recovery database.</span></span>

<span data-ttu-id="794af-157">從[Microsoft 下載中心](https://go.microsoft.com/fwlink/?LinkId=613122)下載 Add-ComputerUser.ps1 PowerShell 腳本。</span><span class="sxs-lookup"><span data-stu-id="794af-157">Download the Add-ComputerUser.ps1 PowerShell script from the [Microsoft Download Center](https://go.microsoft.com/fwlink/?LinkId=613122).</span></span>

<span data-ttu-id="794af-158">您可以指定 [說明] **Add-ComputerUser.ps1**以取得腳本的說明，包括如何使用 Cmdlet 與腳本的範例。</span><span class="sxs-lookup"><span data-stu-id="794af-158">You can specify **help Add-ComputerUser.ps1** to get help for the script, including examples of how to use the cmdlets and the script.</span></span>

<span data-ttu-id="794af-159">若要在安裝 MBAM 伺服器之後建立使用者對電腦的關聯，請使用 MbamComputerUser PowerShell Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="794af-159">To create user-to-computer associations after you have installed the MBAM server, use the Write-MbamComputerUser PowerShell cmdlet.</span></span> <span data-ttu-id="794af-160">與 Add-ComputerUser.ps1 PowerShell 腳本類似，此 Cmdlet 可讓您指定可使用自助入口網站來取得特定電腦的 TPM OwnerAuth 資訊或大量復原密碼的使用者。</span><span class="sxs-lookup"><span data-stu-id="794af-160">Similar to the Add-ComputerUser.ps1 PowerShell script, this cmdlet lets you specify users that can use the Self-Service Portal to get TPM OwnerAuth information or volume recovery passwords for the specified computer.</span></span>

<span data-ttu-id="794af-161">**記事** 當該電腦開始向伺服器進行報告時，MBAM 代理程式將會覆寫使用者對電腦的關聯。</span><span class="sxs-lookup"><span data-stu-id="794af-161">**Note** The MBAM agent will override user-to-computer associations when that computer begins reporting up to the server.</span></span>

 

<span data-ttu-id="794af-162">**先決條件：** 只有當您以高許可權的使用者帳戶（例如網域系統管理員）執行，或以帳戶在已獲授權讀取資訊存取權的自訂安全性群組中時，Read AD \ \* Cmdlet 才能從 AD 中檢索資訊（建議使用）。</span><span class="sxs-lookup"><span data-stu-id="794af-162">**Prerequisites:** The Read-AD\* cmdlets can retrieve information from AD only if they are either run as a highly privileged user account, such as a Domain Administrator, or run as an account in a custom security group granted read access to the information (recommended).</span></span>

<span data-ttu-id="794af-163">[BitLocker 磁片磁碟機加密操作指南：使用 AD DS 復原加密的磁片](https://technet.microsoft.com/library/cc771778(WS.10).aspx)，提供建立自訂安全性群組（或多個群組）的詳細資料，並提供廣告資訊的讀取存取權。</span><span class="sxs-lookup"><span data-stu-id="794af-163">[BitLocker Drive Encryption Operations Guide: Recovering Encrypted Volumes with AD DS](https://technet.microsoft.com/library/cc771778(WS.10).aspx) provides details about creating a custom security group (or multiple groups) with read access to the AD information.</span></span>

<span data-ttu-id="794af-164">**MBAM 復原與硬體 Web 服務寫入權限：** Mbam \ \* Cmdlet 會接受 MBAM 復原與硬體服務的 URL，用來發佈復原或 TPM 資訊。</span><span class="sxs-lookup"><span data-stu-id="794af-164">**MBAM Recovery and Hardware Web Service Write Permissions:** The Write-Mbam\* cmdlets accept the URL of the MBAM Recovery and Hardware Service, used to publish the recovery or TPM information.</span></span> <span data-ttu-id="794af-165">通常只有網域電腦服務帳戶可以與 MBAM 復原與硬體服務進行通訊。</span><span class="sxs-lookup"><span data-stu-id="794af-165">Typically, only a domain computer service account can communicate with the MBAM Recovery and Hardware Service.</span></span> <span data-ttu-id="794af-166">在 MBAM 2.5 SP1 中，您可以使用名為 DataMigrationAccessGroup 的安全性群組來設定 MBAM 復原與硬體服務，其成員可以略過網域電腦服務帳戶檢查。</span><span class="sxs-lookup"><span data-stu-id="794af-166">In MBAM 2.5 SP1, you can configure the MBAM Recovery and Hardware Service with a security group called DataMigrationAccessGroup whose members are allowed to bypass the domain computer service account check.</span></span> <span data-ttu-id="794af-167">Write Mbam \ \* Cmdlet 必須以屬於此設定群組的使用者身分執行。</span><span class="sxs-lookup"><span data-stu-id="794af-167">The Write-Mbam\* cmdlets must be run as a user belonging to this configured group.</span></span> <span data-ttu-id="794af-168">（或者，您可以使用 Mbam \ \* Cmdlet 中的– Credential 參數，指定已設定群組中個別使用者的認證。）</span><span class="sxs-lookup"><span data-stu-id="794af-168">(Alternatively, the credentials of an individual user in the configured group can be specified by using the –Credential parameter in the Write-Mbam\* cmdlets.)</span></span>

<span data-ttu-id="794af-169">您可以使用下列其中一種方式，將 MBAM 復原與硬體服務設定為此安全群組的名稱：</span><span class="sxs-lookup"><span data-stu-id="794af-169">You can configure the MBAM Recovery and Hardware Service with the name of this security group in one of these ways:</span></span>

-   <span data-ttu-id="794af-170">在 Enable-MbamWebApplication – AgentService Powershell Cmdlet 的-DataMigrationAccessGroup 參數中，提供安全性群組（或個別）的名稱。</span><span class="sxs-lookup"><span data-stu-id="794af-170">Provide the name of the security group (or individual) in the -DataMigrationAccessGroup parameter of the Enable-MbamWebApplication –AgentService Powershell cmdlet.</span></span>

-   <span data-ttu-id="794af-171">在 &lt; inetpub &gt; \\Microsoft Bitlocker 管理 Solution\\Recovery 和硬體 Service\\ 資料夾中編輯 web.config 檔案，以設定 MBAM 復原和硬體服務安裝之後的群組。</span><span class="sxs-lookup"><span data-stu-id="794af-171">Configure the group after the MBAM Recovery and Hardware Service has been installed by editing the web.config file in the &lt;inetpub&gt;\\Microsoft Bitlocker Management Solution\\Recovery and Hardware Service\\ folder.</span></span>

    ```xml
    <add key="DataMigrationUsersGroupName" value="<groupName>|<empty>" />
    ```

    <span data-ttu-id="794af-172">在 &lt; 其中 &gt; 使用的網域和群組名稱（或個別使用者）取代將其設為允許從 Active Directory 進行資料移轉的位置。</span><span class="sxs-lookup"><span data-stu-id="794af-172">where &lt;groupName&gt; is replaced with the domain and the group name (or the individual user) that will be used to allow data migration from Active Directory.</span></span>

-   <span data-ttu-id="794af-173">使用 IIS 管理器中的 [設定編輯器] 來編輯此 appSetting。</span><span class="sxs-lookup"><span data-stu-id="794af-173">Use the Configuration Editor in IIS Manager to edit this appSetting.</span></span>

<span data-ttu-id="794af-174">在下列範例中，當您以 ADRecoveryInformation 群組和 [資料移轉使用者] 群組的成員身分執行時，會從 contoso.com 網域中的工作站組織單位（OU）中的電腦提取大量復原資訊，並使用在 mbam.contoso.com 伺服器上執行的 MBAM 復原與硬體服務，將它們寫入 MBAM 中。</span><span class="sxs-lookup"><span data-stu-id="794af-174">In the following example, the command, when run as a member of both the ADRecoveryInformation group and the Data Migration Users group, will pull the volume recovery information from computers in the WORKSTATIONS organizational unit (OU) in the contoso.com domain and write them to MBAM by using the MBAM Recovery and Hardware Service running on the mbam.contoso.com server.</span></span>

``` syntax
PS C:\> Read-ADRecoveryInformation -Server contoso.com -SearchBase "OU=WORKSTATIONS,DC=CONTOSO,DC=COM" | Write-MbamRecoveryInformation -RecoveryServiceEndPoint "https://mbam.contoso.com/MBAMRecoveryAndHardwareService/CoreService.svc"
```

<span data-ttu-id="794af-175">[已**讀-AD \ \* Cmdlet** ] 接受託管伺服器電腦的 Active Directory 名稱或 IP 位址，以查詢復原或 TPM 資訊。</span><span class="sxs-lookup"><span data-stu-id="794af-175">**Read-AD\* cmdlets** accept the name or IP address of an Active Directory hosting server machine to query for recovery or TPM information.</span></span> <span data-ttu-id="794af-176">我們建議您提供將電腦物件作為 SearchBase 參數值駐留的廣告容器的可分辨名稱。</span><span class="sxs-lookup"><span data-stu-id="794af-176">We recommend providing the distinguished names of the AD containers in which the computer object resides as the value of the SearchBase parameter.</span></span> <span data-ttu-id="794af-177">如果電腦儲存在多個 Ou 中，則 Cmdlet 可以接受每個容器執行一次的管線輸入。</span><span class="sxs-lookup"><span data-stu-id="794af-177">If computers are stored across several OUs, the cmdlets can accept pipeline input to run once for each container.</span></span> <span data-ttu-id="794af-178">AD 容器的辨識名稱看起來會像 OU = 機器、DC = contoso、DC = com。</span><span class="sxs-lookup"><span data-stu-id="794af-178">The distinguished name of an AD container will look similar to OU=Machines,DC=contoso,DC=com.</span></span> <span data-ttu-id="794af-179">針對特定容器執行搜尋會提供下列好處：</span><span class="sxs-lookup"><span data-stu-id="794af-179">Performing a search targeted to specific containers provides the following benefits:</span></span>

-   <span data-ttu-id="794af-180">減少查詢大型 AD 資料集的電腦物件時，超時風險。</span><span class="sxs-lookup"><span data-stu-id="794af-180">Reduces the risk of timeout while querying a large AD dataset for computer objects.</span></span>

-   <span data-ttu-id="794af-181">可以省略包含資料中心伺服器或其他可能不需要備份之電腦類別的 Ou。</span><span class="sxs-lookup"><span data-stu-id="794af-181">Can omit OUs containing datacenter servers or other classes of computers for which the backup might not be desired or necessary.</span></span>

<span data-ttu-id="794af-182">另一個選項是提供包含或不使用選擇性 SearchBase 的 [遞迴] 旗標，在指定 SearchBase 或整個網域下的所有容器中分別搜尋電腦物件。</span><span class="sxs-lookup"><span data-stu-id="794af-182">Another option is to provide the –Recurse flag with or without the optional SearchBase to search for computer objects across all containers under the specified SearchBase or the entire domain respectively.</span></span> <span data-ttu-id="794af-183">當您使用遞迴式旗標時，您也可以使用-MaxPageSize 參數來控制服務查詢所需的本機和遠端記憶體量。</span><span class="sxs-lookup"><span data-stu-id="794af-183">When you use the -Recurse flag, you can also use the -MaxPageSize parameter to control the amount of local and remote memory required to service the query.</span></span>

<span data-ttu-id="794af-184">這些 Cmdlet 會寫入類型 PsObject 的管道物件。</span><span class="sxs-lookup"><span data-stu-id="794af-184">These cmdlets write to the pipeline objects of type PsObject.</span></span> <span data-ttu-id="794af-185">每個 PsObject 實例都包含單一的批量復原金鑰或 TPM 擁有者字串，並將其與電腦名稱稱、時間戳記及其他資訊發佈至 MBAM 資料存放區所需。</span><span class="sxs-lookup"><span data-stu-id="794af-185">Each PsObject instance contains a single volume recovery key or TPM owner string with its associated computer name, timestamp, and other information required to publish it to the MBAM data store.</span></span>

<span data-ttu-id="794af-186">**寫入 Mbam \ \* Cmdlet**會依屬性名稱從管線接受復原資訊參數值。</span><span class="sxs-lookup"><span data-stu-id="794af-186">**Write-Mbam\* cmdlets** accept recovery information parameter values from the pipeline by property name.</span></span> <span data-ttu-id="794af-187">這可讓 Write Mbam \ \* Cmdlet 接受 Read AD \ \* Cmdlet 的管線輸出（例如，讀取-ADRecoveryInformation –伺服器 contoso.com-遞迴 |MbamRecoveryInformation – RecoveryServiceEndpoint mbam.contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="794af-187">This allows the Write-Mbam\* cmdlets to accept the pipeline output of the Read-AD\* cmdlets (for example, Read-ADRecoveryInformation –Server contoso.com –Recurse | Write-MbamRecoveryInformation –RecoveryServiceEndpoint mbam.contoso.com).</span></span>

<span data-ttu-id="794af-188">**Write Mbam \ \* Cmdlet**包含可提供容錯、詳細記錄及 WhatIf 和確認選項的選用參數。</span><span class="sxs-lookup"><span data-stu-id="794af-188">The **Write-Mbam\* cmdlets** include optional parameters that provide options for fault tolerance, verbose logging, and preferences for WhatIf and Confirm.</span></span>

<span data-ttu-id="794af-189">**Write Mbam \ \* Cmdlet**也會包含值為**DateTime**物件的可選*時間*參數。</span><span class="sxs-lookup"><span data-stu-id="794af-189">The **Write-Mbam\* cmdlets** also include an optional *Time* parameter whose value is a **DateTime** object.</span></span> <span data-ttu-id="794af-190">此物件包含可設定為、或的*Kind*屬性 `Local` `UTC` `Unspecified` 。</span><span class="sxs-lookup"><span data-stu-id="794af-190">This object includes a *Kind* attribute that can be set to `Local`, `UTC`, or `Unspecified`.</span></span> <span data-ttu-id="794af-191">從 Active Directory 取得的資料填入*時間*參數時，時間會轉換為 UTC，且會自動將此*Kind*屬性設定為 `UTC` 。</span><span class="sxs-lookup"><span data-stu-id="794af-191">When the *Time* parameter is populated from data taken from the Active Directory, the time is converted to UTC and this *Kind* attribute is set automatically to `UTC`.</span></span> <span data-ttu-id="794af-192">不過，使用其他來源（例如文字檔）來填充*Time*參數時，您必須明確地將*Kind*屬性設定為適當的值。</span><span class="sxs-lookup"><span data-stu-id="794af-192">However, when populating the *Time* parameter using another source, such as a text file, you must explicitly set the *Kind* attribute to its appropriate value.</span></span>

<span data-ttu-id="794af-193">**記事** Read AD \ \* Cmdlet 不能探索代表電腦使用者的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="794af-193">**Note** The Read-AD\* cmdlets do not have the ability to discover the user accounts that represent the computer users.</span></span> <span data-ttu-id="794af-194">下列情況需要使用者帳戶關聯：</span><span class="sxs-lookup"><span data-stu-id="794af-194">User account associations are needed for the following:</span></span>

-   <span data-ttu-id="794af-195">使用自助入口網站來復原大量密碼/套件的使用者</span><span class="sxs-lookup"><span data-stu-id="794af-195">Users to recover volume passwords/packages by using the Self-Service portal</span></span>

-   <span data-ttu-id="794af-196">在安裝期間未在 MBAM 高級支援人員使用者安全性群組中定義的使用者，代表其他使用者復原</span><span class="sxs-lookup"><span data-stu-id="794af-196">Users who are not in the MBAM Advanced Helpdesk Users security group as defined during installation, recovering on behalf of other users</span></span>

 

## <a href="" id="bkmk-autounlock"></a><span data-ttu-id="794af-197">設定 MBAM 在封鎖之後自動解除鎖定 TPM</span><span class="sxs-lookup"><span data-stu-id="794af-197">Configure MBAM to automatically unlock the TPM after a lockout</span></span>


<span data-ttu-id="794af-198">您可以設定 MBAM 2.5 SP1，在鎖定時自動解除鎖定 TPM。</span><span class="sxs-lookup"><span data-stu-id="794af-198">You can configure MBAM 2.5 SP1 to automatically unlock the TPM in case of a lockout.</span></span> <span data-ttu-id="794af-199">如果啟用 TPM 封鎖自動重設，MBAM 會偵測到使用者已被封鎖，然後從 MBAM 資料庫取得 OwnerAuth 密碼，以便自動解除鎖定使用者的 TPM。</span><span class="sxs-lookup"><span data-stu-id="794af-199">If TPM lockout auto reset is enabled, MBAM can detect that a user is locked out and then get the OwnerAuth password from the MBAM database to automatically unlock the TPM for the user.</span></span> <span data-ttu-id="794af-200">只有當您使用自助服務入口網站或 [管理及監視] 網站來檢索該電腦的作業系統復原金鑰時，才能使用 TPM 封鎖自動重設。</span><span class="sxs-lookup"><span data-stu-id="794af-200">TPM lockout auto reset is only available if the OS recovery key for that computer was retrieved by using the Self Service Portal or the Administration and Monitoring Website.</span></span>

<span data-ttu-id="794af-201">**重要** 若要啟用 TPM 封鎖自動重設，您必須在伺服器端和用戶端的 [群群組原則] 中設定此功能。</span><span class="sxs-lookup"><span data-stu-id="794af-201">**Important** To enable TPM lockout auto reset, you must configure this feature on both the server side and in Group Policy on the client side.</span></span>

 

-   <span data-ttu-id="794af-202">若要在用戶端啟用 TPM 封鎖自動重設，請設定位於 [電腦設定] 中的 [設定 TPM 封鎖自動重設] 群組原則設定**系統** &gt; **管理範本** &gt; **Windows 元件** &gt; **MDOP MBAM** &gt; **用戶端管理**。</span><span class="sxs-lookup"><span data-stu-id="794af-202">To enable TPM lockout auto reset on the client side, configure the Group Policy setting "Configure TPM lockout auto reset" located at **Computer Configuration** &gt; **Administrative Templates** &gt; **Windows Components** &gt; **MDOP MBAM** &gt; **Client Management**.</span></span>

-   <span data-ttu-id="794af-203">若要在伺服器端啟用 TPM 封鎖自動重設，您可以在安裝期間的 MBAM 伺服器設定向導中，選取 [啟用 TPM 封鎖自動重設]。</span><span class="sxs-lookup"><span data-stu-id="794af-203">To enable TPM lockout auto reset on the server side, you can check "Enable TPM lockout auto reset" in the MBAM Server Configuration wizard during setup.</span></span>

    <span data-ttu-id="794af-204">您也可以在啟用代理服務網頁元件時，指定「-TPM 封鎖自動重設」開關，在 PowerShell 中啟用 TPM 封鎖自動重設。</span><span class="sxs-lookup"><span data-stu-id="794af-204">You can also enable TPM lockout auto reset in PowerShell by specifying the "-TPM lockout auto reset" switch while enabling the agent service web component.</span></span>

<span data-ttu-id="794af-205">使用者從自助服務入口網站或 [管理及監視] 網站輸入所取得的 BitLocker 復原金鑰之後，MBAM 代理程式會判斷 TPM 是否已鎖定。如果已鎖定，則會嘗試從 MBAM 資料庫檢索電腦的 TPM OwnerAuth。</span><span class="sxs-lookup"><span data-stu-id="794af-205">After a user enters the BitLocker recovery key they obtained from the Self Service Portal or the Administration and Monitoring Website, the MBAM agent will determine if the TPM is locked out. If it is locked out, it will attempt to retrieve the TPM OwnerAuth for the computer from the MBAM database.</span></span> <span data-ttu-id="794af-206">如果 TPM OwnerAuth 已成功檢索，就會用來解除鎖定 TPM。</span><span class="sxs-lookup"><span data-stu-id="794af-206">If the TPM OwnerAuth is successfully retrieved, it will be used to unlock the TPM.</span></span> <span data-ttu-id="794af-207">解鎖 TPM 會使 TPM 完全正常運作，且不會強制使用者在後續從 TPM 封鎖重新開機期間輸入恢復密碼。</span><span class="sxs-lookup"><span data-stu-id="794af-207">Unlocking the TPM makes the TPM fully functional and the user will not be forced to enter the recovery password during subsequent reboots from a TPM lockout.</span></span>

<span data-ttu-id="794af-208">預設會停用 TPM 封鎖自動重設。</span><span class="sxs-lookup"><span data-stu-id="794af-208">TPM lockout auto reset is disabled by default.</span></span>

<span data-ttu-id="794af-209">**記事** 只有運行 TPM 版本1.2 的電腦才支援 TPM 封鎖自動重設。</span><span class="sxs-lookup"><span data-stu-id="794af-209">**Note** TPM lockout auto reset is only supported on computers running TPM version 1.2.</span></span> <span data-ttu-id="794af-210">TPM 2.0 提供內建的封鎖自動重設功能。</span><span class="sxs-lookup"><span data-stu-id="794af-210">TPM 2.0 provides built-in lockout auto reset functionality.</span></span>

 

<span data-ttu-id="794af-211">復原**審核報告**包含與 TPM 封鎖自動重設相關的事件。</span><span class="sxs-lookup"><span data-stu-id="794af-211">**The Recovery Audit Report** includes events related to TPM lockout auto reset.</span></span> <span data-ttu-id="794af-212">如果從 MBAM 用戶端發出要求來檢索 TPM OwnerAuth 密碼，則會記錄事件以指示覆原。</span><span class="sxs-lookup"><span data-stu-id="794af-212">If a request is made from the MBAM client to retrieve a TPM OwnerAuth password, an event is logged to indicate recovery.</span></span> <span data-ttu-id="794af-213">審核專案會包含下列事件：</span><span class="sxs-lookup"><span data-stu-id="794af-213">Audit entries will include the following events:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="794af-214">級</span><span class="sxs-lookup"><span data-stu-id="794af-214">Entry</span></span></th>
<th align="left"><span data-ttu-id="794af-215">值</span><span class="sxs-lookup"><span data-stu-id="794af-215">Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="794af-216">審核要求來源</span><span class="sxs-lookup"><span data-stu-id="794af-216">Audit Request Source</span></span></p></td>
<td align="left"><p><span data-ttu-id="794af-217">代理 TPM 解除鎖定</span><span class="sxs-lookup"><span data-stu-id="794af-217">Agent TPM unlock</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="794af-218">金鑰類型</span><span class="sxs-lookup"><span data-stu-id="794af-218">Key Type</span></span></p></td>
<td align="left"><p><span data-ttu-id="794af-219">TPM 密碼雜湊</span><span class="sxs-lookup"><span data-stu-id="794af-219">TPM Password Hash</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="794af-220">原因描述</span><span class="sxs-lookup"><span data-stu-id="794af-220">Reason Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="794af-221">TPM 重設</span><span class="sxs-lookup"><span data-stu-id="794af-221">TPM Reset</span></span></p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="bkmk-secure-databases"></a><span data-ttu-id="794af-222">安全連線至 SQL Server</span><span class="sxs-lookup"><span data-stu-id="794af-222">Secure connections to SQL Server</span></span>


<span data-ttu-id="794af-223">在 MBAM 中，SQL Server 會與 SQL Server Reporting Services 以及管理和監控網站及自助服務入口網站的 web 服務進行通訊。</span><span class="sxs-lookup"><span data-stu-id="794af-223">In MBAM, SQL Server communicates with SQL Server Reporting Services and with the web services for the Administration and Monitoring Website and Self-Service Portal.</span></span> <span data-ttu-id="794af-224">我們建議您保護與 SQL Server 的通訊。</span><span class="sxs-lookup"><span data-stu-id="794af-224">We recommend that you secure the communication with SQL Server.</span></span> <span data-ttu-id="794af-225">如需詳細資訊，請參閱[加密連線至 SQL Server](https://technet.microsoft.com/library/ms189067.aspx)。</span><span class="sxs-lookup"><span data-stu-id="794af-225">For more information, see [Encrypting Connections to SQL Server](https://technet.microsoft.com/library/ms189067.aspx).</span></span>

<span data-ttu-id="794af-226">如需加強 MBAM 網站安全的詳細資訊，請參閱[規劃如何保護 MBAM 網站](planning-how-to-secure-the-mbam-websites.md)。</span><span class="sxs-lookup"><span data-stu-id="794af-226">For more information about securing the MBAM websites, see [Planning How to Secure the MBAM Websites](planning-how-to-secure-the-mbam-websites.md).</span></span>

## <a href="" id="bkmk-accts-groups"></a><span data-ttu-id="794af-227">建立帳戶和群組</span><span class="sxs-lookup"><span data-stu-id="794af-227">Create accounts and groups</span></span>


<span data-ttu-id="794af-228">管理使用者帳戶的最佳做法是建立網域全域群組，並在其中新增使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="794af-228">The best practice for managing user accounts is to create domain global groups and add user accounts to them.</span></span> <span data-ttu-id="794af-229">如需建議的帳戶和群組的描述，請參閱[規劃 MBAM 2.5 群組和帳戶](planning-for-mbam-25-groups-and-accounts.md)。</span><span class="sxs-lookup"><span data-stu-id="794af-229">For a description of the recommended accounts and groups, see [Planning for MBAM 2.5 Groups and Accounts](planning-for-mbam-25-groups-and-accounts.md).</span></span>

## <a href="" id="bkmk-logfiles"></a><span data-ttu-id="794af-230">使用 MBAM 記錄檔</span><span class="sxs-lookup"><span data-stu-id="794af-230">Use MBAM log files</span></span>


<span data-ttu-id="794af-231">本節說明 MBAM 伺服器和 MBAM 用戶端記錄檔。</span><span class="sxs-lookup"><span data-stu-id="794af-231">This section describes the MBAM Server and MBAM Client log files.</span></span>

**<span data-ttu-id="794af-232">MBAM Server 安裝程式記錄檔</span><span class="sxs-lookup"><span data-stu-id="794af-232">MBAM Server Setup log files</span></span>**

<span data-ttu-id="794af-233">在 MBAM 安裝期間， **MBAMServerSetup.exe**檔會在使用者的 **% temp%** 資料夾中產生下列記錄檔：</span><span class="sxs-lookup"><span data-stu-id="794af-233">The **MBAMServerSetup.exe** file generates the following log files in the user’s **%temp%** folder during the MBAM installation:</span></span>

-   **<span data-ttu-id="794af-234">Microsoft \ _BitLocker \ _Administration \ _and \ _Monitoring \ _ &lt; 數位 &gt; . 記錄</span><span class="sxs-lookup"><span data-stu-id="794af-234">Microsoft\_BitLocker\_Administration\_and\_Monitoring\_&lt;14 numbers&gt;.log</span></span>**

    <span data-ttu-id="794af-235">記錄在 MBAM 設定和 MBAM 伺服器功能設定期間所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="794af-235">Logs the actions taken during the MBAM setup and the MBAM Server feature configuration.</span></span>

-   **<span data-ttu-id="794af-236">Microsoft \ _BitLocker \ _Administration \ _and \ _Monitoring \ _ &lt; 14 \ _numbers &gt;\_0\_MBAMServer.msi .log</span><span class="sxs-lookup"><span data-stu-id="794af-236">Microsoft\_BitLocker\_Administration\_and\_Monitoring\_&lt;14\_numbers&gt;\_0\_MBAMServer.msi.log</span></span>**

    <span data-ttu-id="794af-237">記錄安裝期間採取的其他動作。</span><span class="sxs-lookup"><span data-stu-id="794af-237">Logs additional action taken during installation.</span></span>

**<span data-ttu-id="794af-238">MBAM 伺服器配置記錄檔</span><span class="sxs-lookup"><span data-stu-id="794af-238">MBAM Server Configuration log files</span></span>**

-   **<span data-ttu-id="794af-239">應用程式和服務記錄/Microsoft Windows/MBAM-設定</span><span class="sxs-lookup"><span data-stu-id="794af-239">Applications and Services Logs/Microsoft Windows/MBAM-Setup</span></span>**

    <span data-ttu-id="794af-240">記錄您使用 Windows Powershell Cmdlet 時所發生的錯誤，或 MBAM 伺服器設定精靈來設定 MBAM 伺服器功能。</span><span class="sxs-lookup"><span data-stu-id="794af-240">Logs the errors that occur when you are using Windows Powershell cmdlets or the MBAM Server Configuration wizard to configure the MBAM Server features.</span></span>

**<span data-ttu-id="794af-241">MBAM 用戶端安裝記錄檔</span><span class="sxs-lookup"><span data-stu-id="794af-241">MBAM Client setup log files</span></span>**

-   **<span data-ttu-id="794af-242">MSI &lt; 5 隨機字元 &gt; 記錄</span><span class="sxs-lookup"><span data-stu-id="794af-242">MSI&lt;five random characters&gt;.log</span></span>**

    <span data-ttu-id="794af-243">記錄在 MBAM 用戶端安裝期間所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="794af-243">Logs the actions taken during the MBAM Client installation.</span></span>

**<span data-ttu-id="794af-244">MBAM-Web 記錄檔</span><span class="sxs-lookup"><span data-stu-id="794af-244">MBAM-Web log files</span></span>**

-   <span data-ttu-id="794af-245">顯示來自網頁入口網站和服務的活動。</span><span class="sxs-lookup"><span data-stu-id="794af-245">Shows activity from the web portals and services.</span></span>

## <a href="" id="bkmk-tde"></a><span data-ttu-id="794af-246">審閱 MBAM 資料庫 TDE 考慮</span><span class="sxs-lookup"><span data-stu-id="794af-246">Review MBAM database TDE considerations</span></span>


<span data-ttu-id="794af-247">在 SQL Server 中提供的透明資料加密（TDE）功能，是一個可供裝載 MBAM 資料庫功能之資料庫實例的選擇性安裝。</span><span class="sxs-lookup"><span data-stu-id="794af-247">The transparent data encryption (TDE) feature that is available in SQL Server is an optional installation for the database instances that will host the MBAM database features.</span></span>

<span data-ttu-id="794af-248">有了 TDE，您就可以執行即時的完整資料庫層級加密。</span><span class="sxs-lookup"><span data-stu-id="794af-248">With TDE, you can perform real-time, full database-level encryption.</span></span> <span data-ttu-id="794af-249">TDE 是大量加密的最佳選擇，可滿足法規遵從性或公司資料安全性標準。</span><span class="sxs-lookup"><span data-stu-id="794af-249">TDE is the optimal choice for bulk encryption to meet regulatory compliance or corporate data security standards.</span></span> <span data-ttu-id="794af-250">TDE 在檔層級運作，類似于兩個 Windows 功能： [加密檔案系統（EFS）] 和 [BitLocker 磁片磁碟機加密]。</span><span class="sxs-lookup"><span data-stu-id="794af-250">TDE works at the file level, which is similar to two Windows features: the Encrypting File System (EFS) and BitLocker Drive Encryption.</span></span> <span data-ttu-id="794af-251">這兩種功能也會對硬碟上的資料進行加密。</span><span class="sxs-lookup"><span data-stu-id="794af-251">Both features also encrypt data on the hard drive.</span></span> <span data-ttu-id="794af-252">TDE 不會取代儲存格層級的加密、EFS 或 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="794af-252">TDE does not replace cell-level encryption, EFS, or BitLocker.</span></span>

<span data-ttu-id="794af-253">在資料庫上啟用 TDE 時，所有備份都會經過加密。</span><span class="sxs-lookup"><span data-stu-id="794af-253">When TDE is enabled on a database, all backups are encrypted.</span></span> <span data-ttu-id="794af-254">因此，您必須採取特殊小心，以確保用來保護資料庫加密金鑰的憑證已在資料庫備份中備份及維護。</span><span class="sxs-lookup"><span data-stu-id="794af-254">Thus, special care must be taken to ensure that the certificate that was used to protect the database encryption key is backed up and maintained with the database backup.</span></span> <span data-ttu-id="794af-255">如果此憑證或憑證遺失，資料將無法讀取。</span><span class="sxs-lookup"><span data-stu-id="794af-255">If this certificate (or certificates) is lost, the data will be unreadable.</span></span>

<span data-ttu-id="794af-256">使用資料庫備份憑證。</span><span class="sxs-lookup"><span data-stu-id="794af-256">Back up the certificate with the database.</span></span> <span data-ttu-id="794af-257">每個證書備份都應該有兩個檔案。</span><span class="sxs-lookup"><span data-stu-id="794af-257">Each certificate backup should have two files.</span></span> <span data-ttu-id="794af-258">這兩個檔案都應該封存。</span><span class="sxs-lookup"><span data-stu-id="794af-258">Both of these files should be archived.</span></span> <span data-ttu-id="794af-259">理想的安全性，應該將它們與資料庫備份檔案分開備份。</span><span class="sxs-lookup"><span data-stu-id="794af-259">Ideally for security, they should be backed up separately from the database backup file.</span></span> <span data-ttu-id="794af-260">您也可以考慮使用可擴展金鑰管理（EKM）功能（請參閱可擴展金鑰管理）來儲存和維護用於 TDE 的金鑰。</span><span class="sxs-lookup"><span data-stu-id="794af-260">You can alternatively consider using the extensible key management (EKM) feature (see Extensible Key Management) for storage and maintenance of keys that are used for TDE.</span></span>

<span data-ttu-id="794af-261">如需如何針對 MBAM 資料庫實例啟用 TDE 的範例，請參閱[瞭解透明資料加密（TDE）](https://technet.microsoft.com/library/bb934049.aspx)。</span><span class="sxs-lookup"><span data-stu-id="794af-261">For an example of how to enable TDE for MBAM database instances, see [Understanding Transparent Data Encryption (TDE)](https://technet.microsoft.com/library/bb934049.aspx).</span></span>

## <a href="" id="bkmk-general-security"></a><span data-ttu-id="794af-262">瞭解一般的安全性考慮</span><span class="sxs-lookup"><span data-stu-id="794af-262">Understand general security considerations</span></span>


**<span data-ttu-id="794af-263">瞭解安全性風險。</span><span class="sxs-lookup"><span data-stu-id="794af-263">Understand the security risks.</span></span>** <span data-ttu-id="794af-264">當您使用 Microsoft BitLocker 管理和監控時，最嚴重的風險是，未經授權的使用者可能會利用此漏洞，在 MBAM 用戶端上重新設定 BitLocker 磁片磁碟機加密和取得 BitLocker 加密金鑰資料。</span><span class="sxs-lookup"><span data-stu-id="794af-264">The most serious risk when you use Microsoft BitLocker Administration and Monitoring is that its functionality could be compromised by an unauthorized user who could then reconfigure BitLocker Drive Encryption and gain BitLocker encryption key data on MBAM Clients.</span></span> <span data-ttu-id="794af-265">不過，由於拒絕服務攻擊而導致短時間的 MBAM 功能遺失，通常不會產生災難性影響，例如，遺失電子郵件或網路通訊或電源。</span><span class="sxs-lookup"><span data-stu-id="794af-265">However, the loss of MBAM functionality for a short period of time, due to a denial-of-service attack, does not generally have a catastrophic impact, unlike, for example, losing e-mail or network communications, or power.</span></span>

<span data-ttu-id="794af-266">**在物理上保護您的電腦**。</span><span class="sxs-lookup"><span data-stu-id="794af-266">**Physically secure your computers**.</span></span> <span data-ttu-id="794af-267">沒有物理安全性的安全性。</span><span class="sxs-lookup"><span data-stu-id="794af-267">There is no security without physical security.</span></span> <span data-ttu-id="794af-268">取得 MBAM 伺服器實際存取權的攻擊者，可能會利用它來攻擊整個用戶端基礎。</span><span class="sxs-lookup"><span data-stu-id="794af-268">An attacker who gets physical access to an MBAM Server could potentially use it to attack the entire client base.</span></span> <span data-ttu-id="794af-269">所有可能的物理攻擊都必須視為高風險，並適當地減輕問題。</span><span class="sxs-lookup"><span data-stu-id="794af-269">All potential physical attacks must be considered high risk and mitigated appropriately.</span></span> <span data-ttu-id="794af-270">MBAM 伺服器應該儲存在安全的伺服器機房中，並具有可控存取權。</span><span class="sxs-lookup"><span data-stu-id="794af-270">MBAM Servers should be stored in a secure server room with controlled access.</span></span> <span data-ttu-id="794af-271">使用作業系統鎖定電腦，或使用安全的螢幕保護裝置程式，在系統管理員沒有實際顯示的情況下，保護這些電腦的安全。</span><span class="sxs-lookup"><span data-stu-id="794af-271">Secure these computers when administrators are not physically present by having the operating system lock the computer, or by using a secured screen saver.</span></span>

<span data-ttu-id="794af-272">**將最新的安全性更新套用至所有電腦**。</span><span class="sxs-lookup"><span data-stu-id="794af-272">**Apply the most recent security updates to all computers**.</span></span> <span data-ttu-id="794af-273">透過訂閱[安全性技術中心](https://go.microsoft.com/fwlink/?LinkId=28819)的安全性通知服務，隨時瞭解 Windows 作業系統、SQL SERVER 及 MBAM 的新更新。</span><span class="sxs-lookup"><span data-stu-id="794af-273">Stay informed about new updates for Windows operating systems, SQL Server, and MBAM by subscribing to the Security Notification service at the [Security TechCenter](https://go.microsoft.com/fwlink/?LinkId=28819).</span></span>

<span data-ttu-id="794af-274">**使用強式密碼或密碼片語**。</span><span class="sxs-lookup"><span data-stu-id="794af-274">**Use strong passwords or pass phrases**.</span></span> <span data-ttu-id="794af-275">針對所有 MBAM 系統管理員帳戶，請務必將強式密碼搭配15個或更多個字元使用。</span><span class="sxs-lookup"><span data-stu-id="794af-275">Always use strong passwords with 15 or more characters for all MBAM administrator accounts.</span></span> <span data-ttu-id="794af-276">請勿使用空白密碼。</span><span class="sxs-lookup"><span data-stu-id="794af-276">Never use blank passwords.</span></span> <span data-ttu-id="794af-277">如需密碼概念的詳細資訊，請參閱[密碼原則](https://technet.microsoft.com/library/hh994572.aspx)。</span><span class="sxs-lookup"><span data-stu-id="794af-277">For more information about password concepts, see [Password Policy](https://technet.microsoft.com/library/hh994572.aspx).</span></span>



## <span data-ttu-id="794af-278">相關主題</span><span class="sxs-lookup"><span data-stu-id="794af-278">Related topics</span></span>


[<span data-ttu-id="794af-279">規劃部署 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="794af-279">Planning to Deploy MBAM 2.5</span></span>](planning-to-deploy-mbam-25.md)

 
## <span data-ttu-id="794af-280">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="794af-280">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="794af-281">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="794af-281">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span>
- <span data-ttu-id="794af-282">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="794af-282">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>
 





