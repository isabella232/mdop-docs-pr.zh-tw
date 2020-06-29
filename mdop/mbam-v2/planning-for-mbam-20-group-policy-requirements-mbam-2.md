---
title: MBAM 2.0 群組原則需求規劃
description: MBAM 2.0 群組原則需求規劃
author: dansimp
ms.assetid: f5e19dcb-eb15-4722-bb71-0734b3799eb8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f6092507996fe6f0234178c8b1abae5cea7bf836
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800191"
---
# <span data-ttu-id="abe6c-103">MBAM 2.0 群組原則需求規劃</span><span class="sxs-lookup"><span data-stu-id="abe6c-103">Planning for MBAM 2.0 Group Policy Requirements</span></span>


<span data-ttu-id="abe6c-104">若要管理 Microsoft BitLocker 管理與監控（MBAM）用戶端電腦，您需要考慮您要在組織中支援的 BitLocker 保護器類型，然後設定您要套用的對應群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="abe6c-104">To manage Microsoft BitLocker Administration and Monitoring (MBAM) client computers, you need to consider the types of BitLocker protectors that you want to support in your organization, and then configure the corresponding Group Policy settings that you want to apply.</span></span> <span data-ttu-id="abe6c-105">本主題說明當您使用 Microsoft BitLocker 管理和監視來管理企業中的 BitLocker 磁碟機加密時可使用的群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="abe6c-105">This topic describes the Group Policy settings that are available for use when you are using Microsoft BitLocker Administration and Monitoring to manage BitLocker Drive Encryption in the enterprise.</span></span>

<span data-ttu-id="abe6c-106">MBAM 支援下列作業系統磁片磁碟機的 BitLocker 保護器類型：受信任的平臺模組（TPM）、TPM + PIN、TPM + USB 金鑰，以及 TPM + PIN + USB 金鑰、密碼、數位密碼及資料修復代理程式。</span><span class="sxs-lookup"><span data-stu-id="abe6c-106">MBAM supports the following types of BitLocker protectors for operating system drives: Trusted Platform Module (TPM), TPM + PIN, TPM + USB key, and TPM + PIN + USB key, password, numerical password, and Data Recovery Agent.</span></span> <span data-ttu-id="abe6c-107">只有 Windows To Go 裝置以及沒有 TPM 的 Windows 8 裝置支援密碼保護器。</span><span class="sxs-lookup"><span data-stu-id="abe6c-107">The password protector is supported only for Windows To Go devices and for Windows 8 devices that do not have a TPM.</span></span> <span data-ttu-id="abe6c-108">只有在安裝 MBAM 之後才會加密作業系統標籤，MBAM 才支援 TPM + USB 金鑰和 TPM + PIN + USB 金鑰保護器。</span><span class="sxs-lookup"><span data-stu-id="abe6c-108">MBAM supports the TPM + USB key and the TPM + PIN + USB key protectors only when the operating system volume is encrypted before MBAM is installed.</span></span>

<span data-ttu-id="abe6c-109">MBAM 支援下列固定資料磁碟機類型的 BitLocker 保護器：密碼、自動解鎖、數位密碼及資料修復代理程式。</span><span class="sxs-lookup"><span data-stu-id="abe6c-109">MBAM supports the following types of BitLocker protectors for fixed data drives: password, auto-unlock, numerical password, and Data Recovery Agent.</span></span>

<span data-ttu-id="abe6c-110">數位密碼保護程式會自動套用為大量加密的一部分，而且不需要加以設定。</span><span class="sxs-lookup"><span data-stu-id="abe6c-110">The numeric password protector is applied automatically as part of volume encryption and does not need to be configured.</span></span>

**<span data-ttu-id="abe6c-111">重要</span><span class="sxs-lookup"><span data-stu-id="abe6c-111">Important</span></span>**  
<span data-ttu-id="abe6c-112">MBAM 不會使用預設的 Windows BitLocker 磁碟機加密群組原則物件（GPO）設定，而且可能會造成衝突行為（如果已啟用的話）。</span><span class="sxs-lookup"><span data-stu-id="abe6c-112">The default Windows BitLocker drive encryption Group Policy Object (GPO) settings are not used by MBAM and can cause conflicting behavior if they are enabled.</span></span> <span data-ttu-id="abe6c-113">若要啟用 MBAM 來管理 BitLocker，您必須在安裝 MBAM 群組原則範本之後，才能定義 MBAM 群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="abe6c-113">To enable MBAM to manage BitLocker, you must define the MBAM Group Policy settings only after installing the MBAM Group Policy template.</span></span>



<span data-ttu-id="abe6c-114">增強的啟動 Pin 可以包含字元，例如大寫、小寫字母和數位。</span><span class="sxs-lookup"><span data-stu-id="abe6c-114">Enhanced startup PINs can contain characters, such as uppercase and lowercase letters, and numbers.</span></span> <span data-ttu-id="abe6c-115">與 BitLocker 不同的是，MBAM 不支援使用符號和空格來增強針腳。</span><span class="sxs-lookup"><span data-stu-id="abe6c-115">Unlike BitLocker, MBAM does not support the use of symbols and spaces for enhanced PINs.</span></span>

<span data-ttu-id="abe6c-116">在能夠執行群組原則管理主控台（GPMC）或高級群組原則管理（AGPM） MDOP 技術的電腦上，安裝 MBAM 群組原則範本。</span><span class="sxs-lookup"><span data-stu-id="abe6c-116">Install the MBAM Group Policy template on a computer that is capable of running the Group Policy Management Console (GPMC) or the Advanced Group Policy Management (AGPM) MDOP technology.</span></span> <span data-ttu-id="abe6c-117">若要編輯啟用 MBAM 功能的 GPO 設定，您必須先安裝 MBAM 群組原則範本，然後開啟 GPMC 或 AGPM 來編輯適用的 gpo，然後流覽至下列 GPO 節點： [電腦設定**Computer Configuration** \\ **原則**] \\ **管理範本** \\ **Windows 元件** \\ **MDOP MBAM （BitLocker Management）。**</span><span class="sxs-lookup"><span data-stu-id="abe6c-117">To edit the GPO settings that enable MBAM functionality, you must first install the MBAM Group Policy template, open the GPMC or AGPM to edit the applicable GPO, and then navigate to the following GPO node: **Computer Configuration**\\**Policies**\\**Administrative Templates**\\**Windows Components**\\**MDOP MBAM (BitLocker Management).**</span></span>

<span data-ttu-id="abe6c-118">MDOP MBAM （BitLocker 管理） GPO 節點包含四個全域原則設定和四個子 GPO 設定節點：用戶端管理、固定磁片磁碟機、作業系統磁片磁碟機及抽取式磁碟磁碟機。</span><span class="sxs-lookup"><span data-stu-id="abe6c-118">The MDOP MBAM (BitLocker Management) GPO node contains four global policy settings and four child GPO settings nodes: Client Management, Fixed Drive, Operating System Drive, and Removable Drive.</span></span> <span data-ttu-id="abe6c-119">下列各節提供原則定義及建議的原則設定，以協助您規劃 MBAM GPO 原則設定需求。</span><span class="sxs-lookup"><span data-stu-id="abe6c-119">The following sections provide policy definitions and suggested policy settings to assist you in planning for MBAM GPO policy setting requirements.</span></span>

**<span data-ttu-id="abe6c-120">注意</span><span class="sxs-lookup"><span data-stu-id="abe6c-120">Note</span></span>**  
<span data-ttu-id="abe6c-121">如需設定最小（建議的） GPO 設定以啟用 MBAM 以管理 BitLocker 加密的詳細資訊，請參閱[如何編輯 MBAM 2.0 GPO 設定](how-to-edit-mbam-20-gpo-settings-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="abe6c-121">For more information about configuring the minimum, recommended GPO settings to enable MBAM to manage BitLocker encryption, see [How to Edit MBAM 2.0 GPO Settings](how-to-edit-mbam-20-gpo-settings-mbam-2.md).</span></span>



## <span data-ttu-id="abe6c-122">全域原則定義</span><span class="sxs-lookup"><span data-stu-id="abe6c-122">Global Policy Definitions</span></span>


<span data-ttu-id="abe6c-123">本節說明在下列 GPO 節點上找到的 MBAM 全域原則定義：**電腦**設定 \\ **策略** \\ **管理範本** \\ **Windows 元件** \\ **MDOP MBAM （BitLocker Management）**。</span><span class="sxs-lookup"><span data-stu-id="abe6c-123">This section describes MBAM Global policy definitions found at the following GPO node: **Computer Configuration**\\**Policies**\\**Administrative Templates**\\**Windows Components**\\**MDOP MBAM (BitLocker Management)**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="abe6c-124">原則名稱</span><span class="sxs-lookup"><span data-stu-id="abe6c-124">Policy Name</span></span></th>
<th align="left"><span data-ttu-id="abe6c-125">[概覽] 和 [建議的原則] 設定</span><span class="sxs-lookup"><span data-stu-id="abe6c-125">Overview and Suggested Policy Setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="abe6c-126">選擇磁片磁碟機加密方法與密碼強度</span><span class="sxs-lookup"><span data-stu-id="abe6c-126">Choose drive encryption method and cipher strength</span></span></p></td>
<td align="left"><p><span data-ttu-id="abe6c-127">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="abe6c-127">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="abe6c-128">將此原則設定為使用特定的加密方法與密碼強度。</span><span class="sxs-lookup"><span data-stu-id="abe6c-128">Configure this policy to use a specific encryption method and cipher strength.</span></span></p>
<p><span data-ttu-id="abe6c-129">如果未設定此原則，BitLocker 會將 AES 128 位的預設加密方法與擴散器或由安裝腳本指定的加密方法結合使用。</span><span class="sxs-lookup"><span data-stu-id="abe6c-129">When this policy is not configured, BitLocker uses the default encryption method of AES 128-bit with Diffuser or the encryption method specified by the setup script.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="abe6c-130">在重新開機時避免記憶體覆寫</span><span class="sxs-lookup"><span data-stu-id="abe6c-130">Prevent memory overwrite on restart</span></span></p></td>
<td align="left"><p><span data-ttu-id="abe6c-131">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="abe6c-131">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="abe6c-132">設定此原則以改善重新開機效能，而不在重新開機時覆寫記憶體中的 BitLocker 機密。</span><span class="sxs-lookup"><span data-stu-id="abe6c-132">Configure this policy to improve restart performance without overwriting BitLocker secrets in memory on restart.</span></span></p>
<p><span data-ttu-id="abe6c-133">如果未設定此原則，當電腦重新開機時，會從記憶體中移除 BitLocker 密碼。</span><span class="sxs-lookup"><span data-stu-id="abe6c-133">When this policy is not configured, BitLocker secrets are removed from memory when the computer restarts.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="abe6c-134">驗證智慧卡憑證使用規則</span><span class="sxs-lookup"><span data-stu-id="abe6c-134">Validate smart card certificate usage rule</span></span></p></td>
<td align="left"><p><span data-ttu-id="abe6c-135">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="abe6c-135">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="abe6c-136">設定此原則以使用以智慧卡憑證為基礎的 BitLocker 保護。</span><span class="sxs-lookup"><span data-stu-id="abe6c-136">Configure this policy to use smartcard certificate-based BitLocker protection.</span></span></p>
<p><span data-ttu-id="abe6c-137">如果未設定此原則，則會使用預設物件識別碼1.3.6.1.4.1.311.67.1.1 來指定憑證。</span><span class="sxs-lookup"><span data-stu-id="abe6c-137">When this policy is not configured, a default object identifier 1.3.6.1.4.1.311.67.1.1 is used to specify a certificate.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="abe6c-138">為您的組織提供唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="abe6c-138">Provide the unique identifiers for your organization</span></span></p></td>
<td align="left"><p><span data-ttu-id="abe6c-139">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="abe6c-139">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="abe6c-140">將此原則設定為使用以憑證為基礎的資料復原代理程式或 BitLocker To Go reader。</span><span class="sxs-lookup"><span data-stu-id="abe6c-140">Configure this policy to use a certificate-based data recovery agent or the BitLocker To Go reader.</span></span></p>
<p><span data-ttu-id="abe6c-141">如果未設定此原則， <strong> </strong> 就不會使用 [識別] 欄位。</span><span class="sxs-lookup"><span data-stu-id="abe6c-141">When this policy is not configured, the <strong>Identification</strong> field is not used.</span></span></p>
<p><span data-ttu-id="abe6c-142">如果您的公司需要較高的安全性測量，您可能會想要設定 <strong> 識別 </strong> 欄位，以確保所有的 USB 裝置都有此欄位集，且與此群組原則設定一致。</span><span class="sxs-lookup"><span data-stu-id="abe6c-142">If your company requires higher security measurements, you may want to configure the <strong>Identification</strong> field to make sure that all USB devices have this field set and that they are aligned with this Group Policy setting.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="abe6c-143">用戶端管理原則定義</span><span class="sxs-lookup"><span data-stu-id="abe6c-143">Client Management Policy Definitions</span></span>


<span data-ttu-id="abe6c-144">本節說明 Microsoft BitLocker 管理和監控在下列 GPO 節點上找到的用戶端管理原則定義：**電腦**設定 \\ **策略**系統 \\ **管理範本** \\ **Windows 元件** \\ **MDOP MBAM （BitLocker Management）** \\ **用戶端管理**。</span><span class="sxs-lookup"><span data-stu-id="abe6c-144">This section describes Client Management policy definitions for Microsoft BitLocker Administration and Monitoring found at the following GPO node: **Computer Configuration**\\**Policies**\\**Administrative Templates**\\**Windows Components**\\**MDOP MBAM (BitLocker Management)**\\**Client Management**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="abe6c-145">原則名稱</span><span class="sxs-lookup"><span data-stu-id="abe6c-145">Policy Name</span></span></th>
<th align="left"><span data-ttu-id="abe6c-146">概覽和建議的原則設定</span><span class="sxs-lookup"><span data-stu-id="abe6c-146">Overview and Suggested Policy Settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="abe6c-147">設定 MBAM 服務</span><span class="sxs-lookup"><span data-stu-id="abe6c-147">Configure MBAM Services</span></span></p></td>
<td align="left"><p><span data-ttu-id="abe6c-148">建議的設定： <strong> 已啟用</span><span class="sxs-lookup"><span data-stu-id="abe6c-148">Suggested Configuration: <strong>Enabled</span></span></strong></p>
<ul>
<li><p><strong><span data-ttu-id="abe6c-149">MBAM [恢復與硬體服務] 端點 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="abe6c-149">MBAM Recovery and Hardware service endpoint</strong>.</span></span> <span data-ttu-id="abe6c-150">使用此設定來啟用 MBAM 用戶端 BitLocker 加密管理。</span><span class="sxs-lookup"><span data-stu-id="abe6c-150">Use this setting to enable MBAM Client BitLocker encryption management.</span></span> <span data-ttu-id="abe6c-151">輸入與下列範例類似的端點位置： <strong> HTTP:// </strong><em> &lt; MBAM 管理及監視伺服器名稱 &gt; </em><strong> ： </strong><em> &lt; 埠該 web 服務已系結至 &gt; </em><strong> /MBAMRecoveryAndHardwareService/CoreService.svc </strong> 。</span><span class="sxs-lookup"><span data-stu-id="abe6c-151">Enter an endpoint location that is similar to the following example: <strong>http://</strong><em>&lt;MBAM Administration and Monitoring Server Name&gt;</em><strong>:</strong><em>&lt;port the web service is bound to&gt;</em><strong>/MBAMRecoveryAndHardwareService/CoreService.svc</strong>.</span></span></p></li>
<li><p><strong><span data-ttu-id="abe6c-152">選取要儲存的 BitLocker 復原資訊 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="abe6c-152">Select BitLocker recovery information to store</strong>.</span></span> <span data-ttu-id="abe6c-153">此原則設定可讓您設定金鑰復原服務來備份 BitLocker 復原資訊。</span><span class="sxs-lookup"><span data-stu-id="abe6c-153">This policy setting lets you configure the key recovery service to back up BitLocker recovery information.</span></span> <span data-ttu-id="abe6c-154">它也可讓您設定狀態報表服務，以收集合規性和審核報告。</span><span class="sxs-lookup"><span data-stu-id="abe6c-154">It also lets you configure status reporting service for collecting compliance and audit reports.</span></span> <span data-ttu-id="abe6c-155">原則提供一種系統管理方法，可復原由 BitLocker 加密的資料，避免由於缺少重要資訊而造成資料遺失。</span><span class="sxs-lookup"><span data-stu-id="abe6c-155">The policy provides an administrative method of recovering data encrypted by BitLocker to prevent data loss due to the lack of key information.</span></span> <span data-ttu-id="abe6c-156">狀態報表和金鑰復原活動將會自動傳送到已設定的報表伺服器位置。</span><span class="sxs-lookup"><span data-stu-id="abe6c-156">Status report and key recovery activity will automatically and silently be sent to the configured report server location.</span></span></p>
<p><span data-ttu-id="abe6c-157">如果您未設定或停用此原則設定，就不會儲存金鑰復原資訊，且狀態報表和金鑰復原活動將不會報告給伺服器。</span><span class="sxs-lookup"><span data-stu-id="abe6c-157">If you do not configure or if you disable this policy setting, the Key recovery information will not be saved, and status report and key recovery activity will not be reported to server.</span></span> <span data-ttu-id="abe6c-158">當此設定設定為 [復原 <strong> 密碼及金鑰套件] 時，系統會自動將復原 </strong> 密碼及金鑰套件備份到已設定的金鑰復原伺服器位置。</span><span class="sxs-lookup"><span data-stu-id="abe6c-158">When this setting is set to <strong>Recovery Password and key package</strong>, the recovery password and key package will be automatically and silently backed up to the configured key recovery server location.</span></span></p></li>
<li><p><strong><span data-ttu-id="abe6c-159">輸入用戶端檢查狀態頻率（分鐘） </strong> 。</span><span class="sxs-lookup"><span data-stu-id="abe6c-159">Enter client checking status frequency in minutes</strong>.</span></span> <span data-ttu-id="abe6c-160">此原則設定會管理用戶端檢查用戶端電腦上的 BitLocker 保護原則和狀態的頻率。</span><span class="sxs-lookup"><span data-stu-id="abe6c-160">This policy setting manages how frequently the client checks the BitLocker protection policies and status on the client computer.</span></span> <span data-ttu-id="abe6c-161">此原則也會管理將用戶端合規性狀態儲存到伺服器的頻率。</span><span class="sxs-lookup"><span data-stu-id="abe6c-161">This policy also manages how frequently the client compliance status is saved to the server.</span></span> <span data-ttu-id="abe6c-162">用戶端會檢查用戶端電腦上的 BitLocker 保護原則和狀態，同時也會以設定的頻率來備份用戶端復原金鑰。</span><span class="sxs-lookup"><span data-stu-id="abe6c-162">The client checks the BitLocker protection policies and status on the client computer and also backs up the client recovery key at the configured frequency.</span></span></p>
<p><span data-ttu-id="abe6c-163">根據貴公司所設定的需求來設定此頻率，以查看電腦合規性狀態的頻率，以及備份用戶端復原金鑰的頻率。</span><span class="sxs-lookup"><span data-stu-id="abe6c-163">Set this frequency based on the requirement set by your company on how frequently to check the compliance status of the computer, and how frequently to back up the client recovery key.</span></span></p></li>
<li><p><strong><span data-ttu-id="abe6c-164">MBAM 狀態報表服務端點 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="abe6c-164">MBAM Status reporting service endpoint</strong>.</span></span> <span data-ttu-id="abe6c-165">您必須設定此設定，才能啟用 MBAM 用戶端 BitLocker 加密管理。</span><span class="sxs-lookup"><span data-stu-id="abe6c-165">You must configure this setting to enable MBAM Client BitLocker encryption management.</span></span> <span data-ttu-id="abe6c-166">輸入與下列範例類似的端點位置： <strong> HTTP:// </strong><em> &lt; MBAM 管理及監視伺服器名稱 &gt; </em><strong> ： </strong><em> &lt; 埠該 web 服務已系結至 &gt; </em><strong> /MBAMComplianceStatusService/StatusReportingService.svc </strong> 。</span><span class="sxs-lookup"><span data-stu-id="abe6c-166">Enter an endpoint location that is similar to the following example: <strong>http://</strong><em>&lt;MBAM Administration and Monitoring Server Name&gt;</em><strong>:</strong><em>&lt;port the web service is bound to&gt;</em><strong>/MBAMComplianceStatusService/StatusReportingService.svc</strong>.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="abe6c-167">設定使用者豁免原則</span><span class="sxs-lookup"><span data-stu-id="abe6c-167">Configure user exemption policy</span></span></p></td>
<td align="left"><p><span data-ttu-id="abe6c-168">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="abe6c-168">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="abe6c-169">此原則設定可讓您設定網站位址、電子郵件地址或電話號碼，這將會指示使用者從 BitLocker 加密要求例外。</span><span class="sxs-lookup"><span data-stu-id="abe6c-169">This policy setting lets you configure a web site address, email address, or phone number that will instruct a user to request an exemption from BitLocker encryption.</span></span></p>
<p><span data-ttu-id="abe6c-170">如果您啟用此原則設定並提供網站位址、電子郵件地址或電話號碼，使用者將會看到一個對話方塊，提供給他們如何針對 BitLocker 保護申請免除的指示。</span><span class="sxs-lookup"><span data-stu-id="abe6c-170">If you enable this policy setting and provide a web site address, email address, or phone number, users will see a dialog that gives them instructions on how to apply for an exemption from BitLocker protection.</span></span> <span data-ttu-id="abe6c-171">如需針對使用者啟用 BitLocker 加密免除的詳細資訊，請參閱 <a href="how-to-manage-user-bitlocker-encryption-exemptions-mbam-2.md" data-raw-source="[How to Manage User BitLocker Encryption Exemptions](how-to-manage-user-bitlocker-encryption-exemptions-mbam-2.md)"> 如何管理使用者 Bitlocker 加密免除 </a> 。</span><span class="sxs-lookup"><span data-stu-id="abe6c-171">For more information about enabling BitLocker encryption exemptions for users, see <a href="how-to-manage-user-bitlocker-encryption-exemptions-mbam-2.md" data-raw-source="[How to Manage User BitLocker Encryption Exemptions](how-to-manage-user-bitlocker-encryption-exemptions-mbam-2.md)">How to Manage User BitLocker Encryption Exemptions</a>.</span></span></p>
<p><span data-ttu-id="abe6c-172">如果您停用或不設定此原則設定，就不會向使用者顯示免除要求指示。</span><span class="sxs-lookup"><span data-stu-id="abe6c-172">If you either disable or do not configure this policy setting, the exemption request instructions will not be presented to users.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="abe6c-173">注意</span><span class="sxs-lookup"><span data-stu-id="abe6c-173">Note</span></span></strong><br/><p><span data-ttu-id="abe6c-174">使用者豁免是針對每個使用者管理，而不是針對每個電腦。</span><span class="sxs-lookup"><span data-stu-id="abe6c-174">User exemption is managed per user, not per computer.</span></span> <span data-ttu-id="abe6c-175">如果有多個使用者登入同一部電腦，而任何一個使用者並未免除，電腦將會經過加密。</span><span class="sxs-lookup"><span data-stu-id="abe6c-175">If multiple users log on to the same computer and any one user is not exempt, the computer will be encrypted.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="abe6c-176">設定客戶經驗改進計畫</span><span class="sxs-lookup"><span data-stu-id="abe6c-176">Configure customer experience improvement program</span></span></p></td>
<td align="left"><p><span data-ttu-id="abe6c-177">此原則設定可讓您設定 MBAM 使用者如何加入客戶經驗改進計畫。</span><span class="sxs-lookup"><span data-stu-id="abe6c-177">This policy setting lets you configure how MBAM users can join the Customer Experience Improvement Program.</span></span> <span data-ttu-id="abe6c-178">這個程式會收集電腦硬體的相關資訊，以及使用者如何使用 MBAM，而不會中斷他們的工作。</span><span class="sxs-lookup"><span data-stu-id="abe6c-178">This program collects information about computer hardware and how users use MBAM without interrupting their work.</span></span> <span data-ttu-id="abe6c-179">此資訊可協助 Microsoft 識別要改善的 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="abe6c-179">The information helps Microsoft to identify which MBAM features to improve.</span></span> <span data-ttu-id="abe6c-180">Microsoft 不會使用這種資訊來識別或與 MBAM 使用者。</span><span class="sxs-lookup"><span data-stu-id="abe6c-180">Microsoft will not use this information to identify or contact MBAM users.</span></span></p>
<p><span data-ttu-id="abe6c-181">如果您啟用此原則設定，使用者將能夠加入客戶經驗改進計畫。</span><span class="sxs-lookup"><span data-stu-id="abe6c-181">If you enable this policy setting, users will be able to join the Customer Experience Improvement Program.</span></span></p>
<p><span data-ttu-id="abe6c-182">如果您停用此原則設定，使用者將無法加入客戶經驗改進計畫。</span><span class="sxs-lookup"><span data-stu-id="abe6c-182">If you disable this policy setting, users will not be able to join the Customer Experience Improvement Program.</span></span></p>
<p><span data-ttu-id="abe6c-183">如果您未設定此原則設定，使用者將可以加入宣告客戶經驗改進計畫。</span><span class="sxs-lookup"><span data-stu-id="abe6c-183">If you do not configure this policy setting, users will have the option to join the Customer Experience Improvement Program.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="abe6c-184">固定的磁片磁碟機原則定義</span><span class="sxs-lookup"><span data-stu-id="abe6c-184">Fixed Drive Policy Definitions</span></span>


<span data-ttu-id="abe6c-185">本節說明在下列 GPO 節點上找到的 Microsoft BitLocker 管理和監視的固定磁片磁碟機原則定義：**電腦**設定 \\ **策略**系統 \\ **管理範本** \\ **Windows 元件** \\ **MDOP MBAM （BitLocker Management）** 已固定的 \\ **磁片磁碟機**。</span><span class="sxs-lookup"><span data-stu-id="abe6c-185">This section describes Fixed Drive policy definitions for Microsoft BitLocker Administration and Monitoring found at the following GPO node: **Computer Configuration**\\**Policies**\\**Administrative Templates**\\**Windows Components**\\**MDOP MBAM (BitLocker Management)**\\**Fixed Drive**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="abe6c-186">原則名稱</span><span class="sxs-lookup"><span data-stu-id="abe6c-186">Policy Name</span></span></th>
<th align="left"><span data-ttu-id="abe6c-187">[概覽] 和 [建議的原則] 設定</span><span class="sxs-lookup"><span data-stu-id="abe6c-187">Overview and Suggested Policy Setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="abe6c-188">固定資料磁片磁碟機加密設定</span><span class="sxs-lookup"><span data-stu-id="abe6c-188">Fixed data drive encryption settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="abe6c-189">建議的設定： <strong> 已啟用</span><span class="sxs-lookup"><span data-stu-id="abe6c-189">Suggested Configuration: <strong>Enabled</span></span></strong></p>
<p><span data-ttu-id="abe6c-190">此原則設定可讓您管理是否必須加密固定的磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="abe6c-190">This policy setting let you manage whether fixed drives must be encrypted.</span></span></p>
<p><span data-ttu-id="abe6c-191">如果需要加密作業系統卷，請選取 [ <strong> 啟用自動解鎖固定資料磁碟機] </strong> 選項。</span><span class="sxs-lookup"><span data-stu-id="abe6c-191">If the operating system volume is required to be encrypted, select the <strong>Enable auto-unlock fixed data drive</strong> option.</span></span></p>
<p><span data-ttu-id="abe6c-192">啟用此原則時， <strong> </strong> 除非允許或需要在固定資料磁碟機上使用自動解鎖，否則您不能停用 [設定使用密碼來固定資料磁碟機策略]。</span><span class="sxs-lookup"><span data-stu-id="abe6c-192">When enabling this policy, you must not disable the <strong>Configure use of password for fixed data drives</strong> policy unless the use of Auto-Unlock for fixed data drives is allowed or required.</span></span></p>
<p><span data-ttu-id="abe6c-193">如果您需要在固定資料磁碟機上使用自動解鎖，您必須設定要加密的作業系統卷。</span><span class="sxs-lookup"><span data-stu-id="abe6c-193">If you require the use of Auto-Unlock for fixed data drives, you must configure operating system volumes to be encrypted.</span></span></p>
<p><span data-ttu-id="abe6c-194">如果您啟用此原則設定，使用者必須將所有固定磁碟機放在 BitLocker 保護之下，且這些磁碟機將會經過加密。</span><span class="sxs-lookup"><span data-stu-id="abe6c-194">If you enable this policy setting, users are required to put all fixed drives under BitLocker protection, and the drives will be encrypted.</span></span></p>
<p><span data-ttu-id="abe6c-195">如果您未設定此原則設定，則不需要使用者將固定磁片放在 BitLocker 保護之下。</span><span class="sxs-lookup"><span data-stu-id="abe6c-195">If you do not configure this policy setting, users are not required to put fixed drives under BitLocker protection.</span></span> <span data-ttu-id="abe6c-196">如果您在已加密固定資料磁碟機之後套用此原則，則 MBAM agent 會將加密的固定磁片磁碟機解密。</span><span class="sxs-lookup"><span data-stu-id="abe6c-196">If you apply this policy after fixed data drives are encrypted, the MBAM agent decrypts the encrypted fixed drives.</span></span></p>
<p><span data-ttu-id="abe6c-197">如果您停用此原則設定，使用者將無法將其固定資料磁碟機放在 BitLocker 保護底下。</span><span class="sxs-lookup"><span data-stu-id="abe6c-197">If you disable this policy setting, users will not be able to put their fixed data drives under BitLocker protection.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="abe6c-198">拒絕寫入存取不受 BitLocker 保護的固定式磁碟機</span><span class="sxs-lookup"><span data-stu-id="abe6c-198">Deny write access to fixed drives not protected by BitLocker</span></span></p></td>
<td align="left"><p><span data-ttu-id="abe6c-199">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="abe6c-199">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="abe6c-200">此原則設定決定在電腦上，固定磁片磁碟機是否需要進行 BitLocker 保護。</span><span class="sxs-lookup"><span data-stu-id="abe6c-200">This policy setting determines whether BitLocker protection is required for fixed drives to be writable on a computer.</span></span> <span data-ttu-id="abe6c-201">當您開啟 BitLocker 時，就會套用此原則設定。</span><span class="sxs-lookup"><span data-stu-id="abe6c-201">This policy setting is applied when you turn on BitLocker.</span></span></p>
<p><span data-ttu-id="abe6c-202">如果未設定原則，電腦上所有的固定資料磁碟機都會以讀取和寫入存取權掛載。</span><span class="sxs-lookup"><span data-stu-id="abe6c-202">When the policy is not configured, all fixed data drives on the computer are mounted with read and write access.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="abe6c-203">允許從較舊版本的 Windows 存取受 BitLocker 保護的固定磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="abe6c-203">Allow access to BitLocker-protected fixed drives from earlier versions of Windows</span></span></p></td>
<td align="left"><p><span data-ttu-id="abe6c-204">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="abe6c-204">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="abe6c-205">啟用此原則可在執行 Windows Server 2008、Windows Vista、windows XP （含 SP3）或 Windows XP （含 SP2）的電腦上解除鎖定並查看含有 FAT 檔案系統的固定磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="abe6c-205">Enable this policy to let fixed drives with the FAT file system be unlocked and viewed on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2.</span></span></p>
<p><span data-ttu-id="abe6c-206">如果已啟用或未設定原則，就可以在執行 Windows Server 2008、Windows Vista、windows XP （含 SP3）或 Windows XP 的電腦上，解除鎖定使用 FAT 檔案系統格式化的固定磁片磁碟機，以及其內容。</span><span class="sxs-lookup"><span data-stu-id="abe6c-206">When the policy is enabled or not configured, fixed drives formatted with the FAT file system can be unlocked and their content can be viewed on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2.</span></span> <span data-ttu-id="abe6c-207">這些作業系統擁有受 BitLocker 保護的磁片磁碟機的唯讀存取權。</span><span class="sxs-lookup"><span data-stu-id="abe6c-207">These operating systems have read-only access to BitLocker-protected drives.</span></span></p>
<p><span data-ttu-id="abe6c-208">當原則停用時，使用 FAT 檔案系統格式化的固定磁片磁碟機將無法解除鎖定，而且無法在執行 Windows Server 2008、Windows Vista、Windows XP （含 SP3）的電腦上，或使用 SP2 的 Windows XP 中查看其內容。</span><span class="sxs-lookup"><span data-stu-id="abe6c-208">When the policy is disabled, fixed drives formatted with the FAT file system cannot be unlocked and their content cannot be viewed on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="abe6c-209">設定在固定磁片磁碟機使用密碼</span><span class="sxs-lookup"><span data-stu-id="abe6c-209">Configure use of password for fixed drives</span></span></p></td>
<td align="left"><p><span data-ttu-id="abe6c-210">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="abe6c-210">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="abe6c-211">使用此原則來指定是否需要密碼來解除鎖定受 BitLocker 保護的固定資料磁碟機。</span><span class="sxs-lookup"><span data-stu-id="abe6c-211">Use this policy to specify whether a password is required to unlock BitLocker-protected fixed data drives.</span></span></p>
<p><span data-ttu-id="abe6c-212">如果您啟用此原則設定，使用者可以設定符合您所定義需求的密碼。</span><span class="sxs-lookup"><span data-stu-id="abe6c-212">If you enable this policy setting, users can configure a password that meets the requirements you define.</span></span> <span data-ttu-id="abe6c-213">BitLocker 將允許使用者使用磁片磁碟機上提供的任何保護程式來解除鎖定磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="abe6c-213">BitLocker will allow users to unlock a drive with any of the protectors that are available on the drive.</span></span></p>
<p><span data-ttu-id="abe6c-214">當您開啟 BitLocker 時，就會強制執行這些設定，而不是在解除音量鎖定時。</span><span class="sxs-lookup"><span data-stu-id="abe6c-214">These settings are enforced when turning on BitLocker, not when unlocking a volume.</span></span></p>
<p><span data-ttu-id="abe6c-215">如果您停用此原則設定，就不允許使用者使用密碼。</span><span class="sxs-lookup"><span data-stu-id="abe6c-215">If you disable this policy setting, users are not allowed to use a password.</span></span></p>
<p><span data-ttu-id="abe6c-216">如果未設定原則，預設設定就會支援密碼，這不會包含密碼複雜性需求，且只需要八個字元。</span><span class="sxs-lookup"><span data-stu-id="abe6c-216">When the policy is not configured, passwords are supported with the default settings, which do not include password complexity requirements and which require only eight characters.</span></span></p>
<p><span data-ttu-id="abe6c-217">若要獲得較高的安全性，請啟用此原則，並選取 [ <strong> 需要密碼才能修正資料磁碟機] </strong> ，選取 <strong> [需要密碼複雜性] </strong> ，然後設定所需的 <strong> 最小密碼長度 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="abe6c-217">For higher security, enable this policy and select <strong>Require password for fixed data drive</strong>, select <strong>Require password complexity</strong>, and set the desired <strong>minimum password length</strong>.</span></span></p>
<p><span data-ttu-id="abe6c-218">如果您停用此原則設定，就不允許使用者使用密碼。</span><span class="sxs-lookup"><span data-stu-id="abe6c-218">If you disable this policy setting, users are not allowed to use a password.</span></span></p>
<p><span data-ttu-id="abe6c-219">如果您未設定此原則設定，系統會支援密碼，預設設定不包含密碼複雜性需求，且只需要八個字元。</span><span class="sxs-lookup"><span data-stu-id="abe6c-219">If you do not configure this policy setting, passwords will be supported with the default settings, which do not include password complexity requirements and which require only eight characters.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="abe6c-220">選擇如何復原受 BitLocker 保護的固定磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="abe6c-220">Choose how BitLocker-protected fixed drives can be recovered</span></span></p></td>
<td align="left"><p><span data-ttu-id="abe6c-221">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="abe6c-221">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="abe6c-222">設定此原則以啟用 BitLocker 資料復原代理程式，或將 BitLocker 復原資訊儲存至 Active Directory 網域服務（AD DS）。</span><span class="sxs-lookup"><span data-stu-id="abe6c-222">Configure this policy to enable the BitLocker data recovery agent or to save BitLocker recovery information to Active Directory Domain Services (AD DS).</span></span></p>
<p><span data-ttu-id="abe6c-223">如果未設定原則，就會允許 BitLocker 資料復原代理程式，且不會將復原資訊備份到 AD DS。</span><span class="sxs-lookup"><span data-stu-id="abe6c-223">When the policy is not configured, the BitLocker data recovery agent is allowed, and recovery information is not backed up to AD DS.</span></span> <span data-ttu-id="abe6c-224">MBAM 不需要將復原資訊備份到 AD DS。</span><span class="sxs-lookup"><span data-stu-id="abe6c-224">MBAM does not require recovery information to be backed up to AD DS.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="abe6c-225">作業系統磁片磁碟機原則定義</span><span class="sxs-lookup"><span data-stu-id="abe6c-225">Operating System Drive Policy Definitions</span></span>


<span data-ttu-id="abe6c-226">本節說明在下列 GPO 節點上找到的 Microsoft BitLocker 管理與監視的作業系統磁片磁碟機原則定義：**電腦**設定 \\ **策略** \\ **管理範本** \\ **Windows 元件** \\ **MDOP MBAM （BitLocker Management）** \\ **作業系統磁片磁碟機**。</span><span class="sxs-lookup"><span data-stu-id="abe6c-226">This section describes Operating System Drive policy definitions for Microsoft BitLocker Administration and Monitoring found at the following GPO node: **Computer Configuration**\\**Policies**\\**Administrative Templates**\\**Windows Components**\\**MDOP MBAM (BitLocker Management)**\\**Operating System Drive**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="abe6c-227">原則名稱</span><span class="sxs-lookup"><span data-stu-id="abe6c-227">Policy Name</span></span></th>
<th align="left"><span data-ttu-id="abe6c-228">[概覽] 和 [建議的原則] 設定</span><span class="sxs-lookup"><span data-stu-id="abe6c-228">Overview and Suggested Policy Setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="abe6c-229">作業系統磁片磁碟機加密設定</span><span class="sxs-lookup"><span data-stu-id="abe6c-229">Operating system drive encryption settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="abe6c-230">建議的設定： <strong> 已啟用</span><span class="sxs-lookup"><span data-stu-id="abe6c-230">Suggested configuration: <strong>Enabled</span></span></strong></p>
<p><span data-ttu-id="abe6c-231">此原則設定可讓您管理作業系統磁片磁碟機是否必須經過加密。</span><span class="sxs-lookup"><span data-stu-id="abe6c-231">This policy setting lets you manage whether the operating system drive must be encrypted.</span></span></p>
<p><span data-ttu-id="abe6c-232">若要獲得較高的安全性，請考慮在 <strong> </strong> 使用 TPM + PIN 保護器啟用 [系統/電源管理/睡眠設定] 中，停用下列原則設定：</span><span class="sxs-lookup"><span data-stu-id="abe6c-232">For higher security, consider disabling the following policy settings in <strong>System/Power Management/Sleep Settings</strong> when you enable them with TPM + PIN protector:</span></span></p>
<ul>
<li><p><span data-ttu-id="abe6c-233">在休眠（電源開啟）時允許待機狀態（S1-S3）</span><span class="sxs-lookup"><span data-stu-id="abe6c-233">Allow Standby States (S1-S3) When Sleeping (Plugged In)</span></span></p></li>
<li><p><span data-ttu-id="abe6c-234">在睡眠時允許待機狀態（S1-S3）（使用電池）</span><span class="sxs-lookup"><span data-stu-id="abe6c-234">Allow Standby States (S1-S3) When Sleeping (On Battery)</span></span></p></li>
</ul>
<p><span data-ttu-id="abe6c-235">如果您執行的是 Microsoft Windows 8 或更新版本，而您想要在沒有 TPM 的電腦上使用 BitLocker，請選取 [ <strong> 允許沒有相容的 tpm 的 bitlocker] </strong> 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="abe6c-235">If you are running Microsoft Windows 8 or later, and you want to use BitLocker on a computer without a TPM, select the <strong>Allow BitLocker without a compatible TPM</strong> check box.</span></span> <span data-ttu-id="abe6c-236">在此模式中，啟動需要密碼。</span><span class="sxs-lookup"><span data-stu-id="abe6c-236">In this mode, a password is required for startup.</span></span> <span data-ttu-id="abe6c-237">如果您忘記密碼，您必須使用其中一個 BitLocker 復原選項來存取磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="abe6c-237">If you forget the password, you have to use one of the BitLocker recovery options to access the drive.</span></span></p>
<p><span data-ttu-id="abe6c-238">在有相容的 TPM 的電腦上，啟動時可以使用兩種類型的驗證方法，為加密資料提供額外的保護。</span><span class="sxs-lookup"><span data-stu-id="abe6c-238">On a computer with a compatible TPM, two types of authentication methods can be used at startup to provide added protection for encrypted data.</span></span> <span data-ttu-id="abe6c-239">電腦啟動時，只能使用 TPM 進行驗證，或者也可能需要輸入個人識別碼（PIN）。</span><span class="sxs-lookup"><span data-stu-id="abe6c-239">When the computer starts, it can use only the TPM for authentication, or it can also require the entry of a personal identification number (PIN).</span></span></p>
<p><span data-ttu-id="abe6c-240">如果您啟用此原則設定，使用者必須將作業系統磁片磁碟機放在 BitLocker 保護之下，而且磁片磁碟機將會經過加密。</span><span class="sxs-lookup"><span data-stu-id="abe6c-240">If you enable this policy setting, users have to put the operating system drive under BitLocker protection, and the drive will be encrypted.</span></span></p>
<p><span data-ttu-id="abe6c-241">如果您停用此原則，使用者將無法將操作系統磁碟機放在 BitLocker 保護下。</span><span class="sxs-lookup"><span data-stu-id="abe6c-241">If you disable this policy, users will not be able to put the operating system drive under BitLocker protection.</span></span> <span data-ttu-id="abe6c-242">如果您在作業系統磁片磁碟機加密之後套用此原則，磁片磁碟機將會解密。</span><span class="sxs-lookup"><span data-stu-id="abe6c-242">If you apply this policy after the operating system drive is encrypted, the drive will be decrypted.</span></span></p>
<p><span data-ttu-id="abe6c-243">如果您未設定此原則，則不需要在 BitLocker 保護下放置作業系統磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="abe6c-243">If you do not configure this policy, the operating system drive is not required to be placed under BitLocker protection.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="abe6c-244">設定 TPM 平臺驗證設定檔</span><span class="sxs-lookup"><span data-stu-id="abe6c-244">Configure TPM platform validation profile</span></span></p></td>
<td align="left"><p><span data-ttu-id="abe6c-245">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="abe6c-245">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="abe6c-246">此原則設定可讓您設定電腦上的 TPM 安全硬體如何保護 BitLocker 加密金鑰。</span><span class="sxs-lookup"><span data-stu-id="abe6c-246">This policy setting lets you configure how the TPM security hardware on a computer secures the BitLocker encryption key.</span></span> <span data-ttu-id="abe6c-247">如果電腦沒有相容的 TPM，或已使用 TPM 保護開啟 BitLocker，此原則設定就不適用。</span><span class="sxs-lookup"><span data-stu-id="abe6c-247">This policy setting does not apply if the computer does not have a compatible TPM or if BitLocker has already been turned on with TPM protection.</span></span></p>
<p><span data-ttu-id="abe6c-248">如果未設定此原則設定，TPM 會使用預設平臺驗證設定檔或由安裝腳本指定的平臺驗證設定檔。</span><span class="sxs-lookup"><span data-stu-id="abe6c-248">When this policy setting is not configured, the TPM uses the default platform validation profile or the platform validation profile that is specified by the setup script.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="abe6c-249">選擇可如何復原受 BitLocker 保護的操作系統磁碟機</span><span class="sxs-lookup"><span data-stu-id="abe6c-249">Choose how BitLocker-protected operating system drives can be recovered</span></span></p></td>
<td align="left"><p><span data-ttu-id="abe6c-250">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="abe6c-250">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="abe6c-251">設定此原則以啟用 BitLocker 資料復原代理程式，或將 BitLocker 復原資訊儲存至 Active Directory 網域服務（AD DS）。</span><span class="sxs-lookup"><span data-stu-id="abe6c-251">Configure this policy to enable the BitLocker data recovery agent or to save BitLocker recovery information to Active Directory Domain Services (AD DS).</span></span></p>
<p><span data-ttu-id="abe6c-252">如果未設定此原則，就可以使用資料復原代理程式，且不會將復原資訊備份到 AD DS。</span><span class="sxs-lookup"><span data-stu-id="abe6c-252">When this policy is not configured, the data recovery agent is allowed, and recovery information is not backed up to AD DS.</span></span></p>
<p><span data-ttu-id="abe6c-253">MBAM 操作不需要將復原資訊備份到 AD DS。</span><span class="sxs-lookup"><span data-stu-id="abe6c-253">MBAM operation does not require recovery information to be backed up to AD DS.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="abe6c-254">移除磁片磁碟機原則定義</span><span class="sxs-lookup"><span data-stu-id="abe6c-254">Removable Drive Policy Definitions</span></span>


<span data-ttu-id="abe6c-255">本節說明在下列 GPO 節點上找到的 Microsoft BitLocker 管理與監視的抽取式磁碟磁碟機原則定義： [**電腦**設定 \\ **策略**] \\ **管理範本** \\ **Windows 元件** \\ **MDOP MBAM （BitLocker 管理）**  \\  **抽取式磁碟磁碟機**。</span><span class="sxs-lookup"><span data-stu-id="abe6c-255">This section describes Removable Drive Policy definitions for Microsoft BitLocker Administration and Monitoring found at the following GPO node: **Computer Configuration**\\**Policies**\\**Administrative Templates**\\**Windows Components**\\**MDOP MBAM (BitLocker Management)** \\ **Removable Drive**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="abe6c-256">原則名稱</span><span class="sxs-lookup"><span data-stu-id="abe6c-256">Policy Name</span></span></th>
<th align="left"><span data-ttu-id="abe6c-257">[概覽] 和 [建議的原則] 設定</span><span class="sxs-lookup"><span data-stu-id="abe6c-257">Overview and Suggested Policy Setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="abe6c-258">在抽取式磁碟磁碟機上控制 BitLocker 的使用</span><span class="sxs-lookup"><span data-stu-id="abe6c-258">Control use of BitLocker on removable drives</span></span></p></td>
<td align="left"><p><span data-ttu-id="abe6c-259">建議的設定： <strong> 已啟用</span><span class="sxs-lookup"><span data-stu-id="abe6c-259">Suggested configuration: <strong>Enabled</span></span></strong></p>
<p><span data-ttu-id="abe6c-260">此原則控制如何在可移動資料磁碟機上使用 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="abe6c-260">This policy controls the use of BitLocker on removable data drives.</span></span></p>
<p><span data-ttu-id="abe6c-261">啟用 [ <strong> 允許使用者在可移動資料磁碟機上套用 bitlocker 保護 </strong> ] 選項，以允許使用者在可移除的資料磁碟機上執行 bitlocker 設定向導。</span><span class="sxs-lookup"><span data-stu-id="abe6c-261">Enable the <strong>Allow users to apply BitLocker protection on removable data drives</strong> option to allow users to run the BitLocker setup wizard on a removable data drive.</span></span></p>
<p><span data-ttu-id="abe6c-262">啟用 [ <strong> 允許使用者暫停並解密可移動資料磁碟機上的 bitlocker] </strong> 選項，允許使用者從磁片磁碟機中移除 bitlocker 磁片磁碟機加密，或在執行維護時暫停加密。</span><span class="sxs-lookup"><span data-stu-id="abe6c-262">Enable the <strong>Allow users to suspend and decrypt BitLocker on removable data drives</strong> option to allow users to remove BitLocker drive encryption from the drive or to suspend the encryption while maintenance is performed.</span></span></p>
<p><span data-ttu-id="abe6c-263">如果已啟用此原則，且已 <strong> 選取 [允許使用者在可移動資料磁片磁碟機上套用 BitLocker 保護] </strong> 選項，則 MBAM 用戶端會將抽取式磁碟磁碟機的復原資訊儲存至 MBAM 金鑰復原伺服器，並允許使用者在密碼遺失時復原磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="abe6c-263">When this policy is enabled and the <strong>Allow users to apply BitLocker protection on removable data drives</strong> option is selected, the MBAM Client saves the recovery information about removable drives to the MBAM key recovery server and allows users to recover the drive if the password is lost.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="abe6c-264">拒絕寫入存取不受 BitLocker 保護的抽取式磁碟機</span><span class="sxs-lookup"><span data-stu-id="abe6c-264">Deny write access to removable drives not protected by BitLocker</span></span></p></td>
<td align="left"><p><span data-ttu-id="abe6c-265">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="abe6c-265">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="abe6c-266">啟用此原則，只允許對受 BitLocker 保護的磁碟機進行寫入存取。</span><span class="sxs-lookup"><span data-stu-id="abe6c-266">Enable this policy to allow only write access to BitLocker protected drives.</span></span></p>
<p><span data-ttu-id="abe6c-267">啟用此原則時，電腦上所有的可移動資料磁碟機都需要加密，才能允許寫入存取。</span><span class="sxs-lookup"><span data-stu-id="abe6c-267">When this policy is enabled, all removable data drives on the computer require encryption before write access is allowed.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="abe6c-268">允許從舊版 Windows 存取受 BitLocker 保護的抽取式磁碟磁碟機</span><span class="sxs-lookup"><span data-stu-id="abe6c-268">Allow access to BitLocker-protected removable drives from earlier versions of Windows</span></span></p></td>
<td align="left"><p><span data-ttu-id="abe6c-269">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="abe6c-269">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="abe6c-270">啟用此原則可讓使用 FAT 檔案系統的固定磁片磁碟機解除鎖定，並在執行 Windows Server 2008、Windows Vista、Windows XP （含 SP3）或 Windows XP （含 SP2）的電腦上進行查看。</span><span class="sxs-lookup"><span data-stu-id="abe6c-270">Enable this policy to allow fixed drives with the FAT file system to be unlocked and viewed on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2.</span></span></p>
<p><span data-ttu-id="abe6c-271">如果未設定此原則，就可以在執行 Windows Server 2008、Windows Vista、Windows XP （含 SP3）或 Windows XP （含 SP2）的電腦上，解除鎖定以 FAT 檔案系統格式化的可移動資料磁碟機，而且可以查看其內容。</span><span class="sxs-lookup"><span data-stu-id="abe6c-271">When this policy is not configured, removable data drives formatted with the FAT file system can be unlocked on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2, and their content can be viewed.</span></span> <span data-ttu-id="abe6c-272">這些作業系統擁有受 BitLocker 保護的磁片磁碟機的唯讀存取權。</span><span class="sxs-lookup"><span data-stu-id="abe6c-272">These operating systems have read-only access to BitLocker-protected drives.</span></span></p>
<p><span data-ttu-id="abe6c-273">當原則停用時，無法在執行 Windows Server 2008、Windows Vista、windows XP 的電腦上，或使用 SP2，在執行 Windows Server、Windows Vista、Windows XP 或 Windows XP 的電腦上，查看以 FAT 檔案系統格式化的抽取式磁碟磁碟機。</span><span class="sxs-lookup"><span data-stu-id="abe6c-273">When the policy is disabled, removable drives formatted with the FAT file system cannot be unlocked and their content cannot be viewed on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="abe6c-274">針對可移動資料磁碟機設定密碼的使用方式</span><span class="sxs-lookup"><span data-stu-id="abe6c-274">Configure use of password for removable data drives</span></span></p></td>
<td align="left"><p><span data-ttu-id="abe6c-275">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="abe6c-275">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="abe6c-276">啟用此原則，在可移動資料磁碟機上設定密碼保護。</span><span class="sxs-lookup"><span data-stu-id="abe6c-276">Enable this policy to configure password protection on removable data drives.</span></span></p>
<p><span data-ttu-id="abe6c-277">如果未設定此原則，預設設定就會支援密碼，這不會包含密碼複雜性需求，且只需要八個字元。</span><span class="sxs-lookup"><span data-stu-id="abe6c-277">When this policy is not configured, passwords are supported with the default settings, which do not include password complexity requirements and which require only eight characters.</span></span></p>
<p><span data-ttu-id="abe6c-278">若要提高安全性，您可以啟用此原則，並檢查 [ <strong> 可移動資料磁碟機需要密碼] </strong> ，選取 <strong> [需要密碼複雜性] </strong> ，然後設定偏好的 <strong> 最小密碼長度 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="abe6c-278">For increased security, you may enable this policy and check <strong>Require password for removable data drive</strong>, select <strong>Require password complexity</strong>, and set the preferred <strong>minimum password length</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="abe6c-279">選擇可如何復原受 BitLocker 保護的抽取式磁碟磁碟機</span><span class="sxs-lookup"><span data-stu-id="abe6c-279">Choose how BitLocker-protected removable drives can be recovered</span></span></p></td>
<td align="left"><p><span data-ttu-id="abe6c-280">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="abe6c-280">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="abe6c-281">設定此原則以啟用 BitLocker 資料復原代理程式，或將 BitLocker 復原資訊儲存至 Active Directory 網域服務（AD DS）。</span><span class="sxs-lookup"><span data-stu-id="abe6c-281">Configure this policy to enable the BitLocker data recovery agent or to save BitLocker recovery information to Active Directory Domain Services (AD DS).</span></span></p>
<p><span data-ttu-id="abe6c-282">如果設定為 [未設定] <strong> </strong> ，則允許資料修復代理程式，且不會將復原資訊備份到 AD DS。</span><span class="sxs-lookup"><span data-stu-id="abe6c-282">When set to <strong>Not Configured</strong>, the data recovery agent is allowed and recovery information is not backed up to AD DS.</span></span></p>
<p><span data-ttu-id="abe6c-283">MBAM 操作不需要將復原資訊備份到 AD DS。</span><span class="sxs-lookup"><span data-stu-id="abe6c-283">MBAM operation does not require recovery information to be backed up to AD DS.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="abe6c-284">相關主題</span><span class="sxs-lookup"><span data-stu-id="abe6c-284">Related topics</span></span>


[<span data-ttu-id="abe6c-285">MBAM 2.0 部署必要條件</span><span class="sxs-lookup"><span data-stu-id="abe6c-285">MBAM 2.0 Deployment Prerequisites</span></span>](mbam-20-deployment-prerequisites-mbam-2.md)









