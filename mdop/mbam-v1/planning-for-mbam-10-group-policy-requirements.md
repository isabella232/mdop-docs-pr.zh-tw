---
title: MBAM 1.0 群組原則需求規劃
description: MBAM 1.0 群組原則需求規劃
author: dansimp
ms.assetid: 0fc9c509-7850-4a8e-bb82-b949025bcb02
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f5061748107dc1d00baa41188b8cf240ec187317
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800093"
---
# <span data-ttu-id="5824b-103">MBAM 1.0 群組原則需求規劃</span><span class="sxs-lookup"><span data-stu-id="5824b-103">Planning for MBAM 1.0 Group Policy Requirements</span></span>


<span data-ttu-id="5824b-104">Microsoft BitLocker 管理與監控（MBAM）用戶端管理需要套用自訂群組策略設定。</span><span class="sxs-lookup"><span data-stu-id="5824b-104">Microsoft BitLocker Administration and Monitoring (MBAM) Client management requires custom Group Policy settings to be applied.</span></span> <span data-ttu-id="5824b-105">本主題說明當您使用 MBAM 管理企業中的 BitLocker 磁碟機加密時，群組原則物件（GPO）可用的原則選項。</span><span class="sxs-lookup"><span data-stu-id="5824b-105">This topic describes the available policy options for Group Policy Object (GPO) when you use MBAM to manage BitLocker Drive Encryption in the enterprise.</span></span>

**<span data-ttu-id="5824b-106">重要</span><span class="sxs-lookup"><span data-stu-id="5824b-106">Important</span></span>**  
<span data-ttu-id="5824b-107">MBAM 不會使用 Windows BitLocker 磁片磁碟機加密的預設 GPO 設定。</span><span class="sxs-lookup"><span data-stu-id="5824b-107">MBAM does not use the default GPO settings for Windows BitLocker drive encryption.</span></span> <span data-ttu-id="5824b-108">如果預設設定為啟用，可能會造成衝突行為。</span><span class="sxs-lookup"><span data-stu-id="5824b-108">If the default settings are enabled, they can cause conflicting behavior.</span></span> <span data-ttu-id="5824b-109">若要啟用 MBAM 來管理 BitLocker，您必須在安裝 MBAM 群群組原則範本之後定義 GPO 原則設定。</span><span class="sxs-lookup"><span data-stu-id="5824b-109">To enable MBAM to manage BitLocker, you must define the GPO policy settings after you install the MBAM Group Policy Template.</span></span>



<span data-ttu-id="5824b-110">在您安裝 MBAM 群組原則範本之後，您可以查看及修改可讓 MBAM 管理企業 BitLocker 加密的可用自訂 MBAM GPO 原則策略設定。</span><span class="sxs-lookup"><span data-stu-id="5824b-110">After you install the MBAM Group Policy template, you can view and modify the available custom MBAM GPO policy settings that enable MBAM to manage the enterprise BitLocker encryption.</span></span> <span data-ttu-id="5824b-111">MBAM 群組原則範本必須安裝在能夠執行群組原則管理主控台（GPMC）或高級群組原則管理（AGPM） MDOP 技術的電腦上。</span><span class="sxs-lookup"><span data-stu-id="5824b-111">The MBAM Group Policy template must be installed on a computer that is capable of running the Group Policy Management Console (GPMC) or the Advanced Group Policy Management (AGPM) MDOP technology.</span></span> <span data-ttu-id="5824b-112">接著，若要編輯適用的 GPO，請開啟 GPMC 或 AGPM，然後流覽至下列 GPO 節點： [**電腦設定] 系統** \\ **管理範本** \\ **Windows 元件** \\ **MDOP MBAM （BitLocker Management）**。</span><span class="sxs-lookup"><span data-stu-id="5824b-112">Next, to edit the applicable GPO, open the GPMC or AGPM, and then navigate to the following GPO node: **Computer Configuration**\\**Administrative Templates**\\**Windows Components**\\**MDOP MBAM (BitLocker Management)**.</span></span>

<span data-ttu-id="5824b-113">MDOP MBAM （BitLocker 管理） GPO 節點分別包含四個全域原則設定和四個子 GPO 設定節點。</span><span class="sxs-lookup"><span data-stu-id="5824b-113">The MDOP MBAM (BitLocker Management) GPO node contains four global policy settings and four child GPO setting nodes, respectively.</span></span> <span data-ttu-id="5824b-114">四個 GPO 全域原則設定為：用戶端管理、固定磁片磁碟機、作業系統磁片磁碟機及抽取式磁碟磁碟機。</span><span class="sxs-lookup"><span data-stu-id="5824b-114">The four GPO global policy settings are: Client Management, Fixed Drive, Operating System Drive, and Removable Drive.</span></span> <span data-ttu-id="5824b-115">下列各節提供原則定義及建議的原則設定，以協助您規劃 MBAM GPO 原則設定需求。</span><span class="sxs-lookup"><span data-stu-id="5824b-115">The following sections provide policy definitions and suggested policy settings to help you plan for the MBAM GPO policy setting requirements.</span></span>

**<span data-ttu-id="5824b-116">注意</span><span class="sxs-lookup"><span data-stu-id="5824b-116">Note</span></span>**  
<span data-ttu-id="5824b-117">如需設定最小建議的 GPO 設定以啟用 MBAM 管理 BitLocker 加密的詳細資訊，請參閱[如何編輯 MBAM 1.0 GPO 設定](how-to-edit-mbam-10-gpo-settings.md)。</span><span class="sxs-lookup"><span data-stu-id="5824b-117">For more information about configuring the minimum suggested GPO settings to enable MBAM to manage BitLocker encryption, see [How to Edit MBAM 1.0 GPO Settings](how-to-edit-mbam-10-gpo-settings.md).</span></span>



## <span data-ttu-id="5824b-118">全域原則定義</span><span class="sxs-lookup"><span data-stu-id="5824b-118">Global policy definitions</span></span>


<span data-ttu-id="5824b-119">本節說明可在下列 GPO 節點上找到的 MBAM 全域原則定義： [電腦設定]**系統** \\ **管理範本** \\ **Windows 元件** \\ **MDOP MBAM （BitLocker Management）**。</span><span class="sxs-lookup"><span data-stu-id="5824b-119">This section describes the MBAM Global policy definitions, which can be found at the following GPO node: **Computer Configuration**\\**Administrative Templates**\\**Windows Components**\\**MDOP MBAM (BitLocker Management)**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5824b-120">原則名稱</span><span class="sxs-lookup"><span data-stu-id="5824b-120">Policy Name</span></span></th>
<th align="left"><span data-ttu-id="5824b-121">[概覽] 和 [建議的原則] 設定</span><span class="sxs-lookup"><span data-stu-id="5824b-121">Overview and Suggested Policy Setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5824b-122">選擇磁片磁碟機加密方法與密碼強度</span><span class="sxs-lookup"><span data-stu-id="5824b-122">Choose drive encryption method and cipher strength</span></span></p></td>
<td align="left"><p><span data-ttu-id="5824b-123">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="5824b-123">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="5824b-124">將此原則設定為使用特定的加密方法與密碼強度。</span><span class="sxs-lookup"><span data-stu-id="5824b-124">Configure this policy to use a specific encryption method and cipher strength.</span></span></p>
<p><span data-ttu-id="5824b-125">如果未設定此原則，BitLocker 會將 AES 128 位的預設加密方法與擴散器或由安裝腳本指定的加密方法結合使用。</span><span class="sxs-lookup"><span data-stu-id="5824b-125">When this policy is not configured, BitLocker uses the default encryption method of AES 128-bit with Diffuser or the encryption method specified by the setup script.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5824b-126">在重新開機時避免記憶體覆寫</span><span class="sxs-lookup"><span data-stu-id="5824b-126">Prevent memory overwrite on restart</span></span></p></td>
<td align="left"><p><span data-ttu-id="5824b-127">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="5824b-127">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="5824b-128">設定此原則以改善重新開機效能，而不在重新開機時覆寫記憶體中的 BitLocker 機密。</span><span class="sxs-lookup"><span data-stu-id="5824b-128">Configure this policy to improve restart performance without overwriting BitLocker secrets in memory on restart.</span></span></p>
<p><span data-ttu-id="5824b-129">如果未設定此原則，當電腦重新開機時，會從記憶體中移除 BitLocker 密碼。</span><span class="sxs-lookup"><span data-stu-id="5824b-129">When this policy is not configured, BitLocker secrets are removed from memory when the computer restarts.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5824b-130">驗證智慧卡憑證使用規則</span><span class="sxs-lookup"><span data-stu-id="5824b-130">Validate smart card certificate usage rule</span></span></p></td>
<td align="left"><p><span data-ttu-id="5824b-131">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="5824b-131">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="5824b-132">設定此原則以使用以智慧卡憑證為基礎的 BitLocker 保護。</span><span class="sxs-lookup"><span data-stu-id="5824b-132">Configure this policy to use smartcard certificate-based BitLocker protection.</span></span></p>
<p><span data-ttu-id="5824b-133">如果未設定此原則，則會使用預設物件識別碼1.3.6.1.4.1.311.67.1.1 來指定憑證。</span><span class="sxs-lookup"><span data-stu-id="5824b-133">When this policy is not configured, a default object identifier 1.3.6.1.4.1.311.67.1.1 is used to specify a certificate.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5824b-134">為您的組織提供唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="5824b-134">Provide the unique identifiers for your organization</span></span></p></td>
<td align="left"><p><span data-ttu-id="5824b-135">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="5824b-135">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="5824b-136">將此原則設定為使用以憑證為基礎的資料復原代理程式或 BitLocker To Go reader。</span><span class="sxs-lookup"><span data-stu-id="5824b-136">Configure this policy to use a certificate-based data recovery agent or the BitLocker To Go reader.</span></span></p>
<p><span data-ttu-id="5824b-137">如果未設定此原則， <strong> </strong> 就不會使用 [識別] 欄位。</span><span class="sxs-lookup"><span data-stu-id="5824b-137">When this policy is not configured, the <strong>Identification</strong> field is not used.</span></span></p>
<p><span data-ttu-id="5824b-138">如果您的公司需要較高的安全性測量，您可能會想要設定 <strong> 識別 </strong> 欄位，以確保所有的 USB 裝置都有此欄位集，且與此群組原則設定一致。</span><span class="sxs-lookup"><span data-stu-id="5824b-138">If your company requires higher security measurements, you may want to configure the <strong>Identification</strong> field to make sure that all USB devices have this field set and that they are aligned with this Group Policy setting.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="5824b-139">用戶端管理原則定義</span><span class="sxs-lookup"><span data-stu-id="5824b-139">Client Management policy definitions</span></span>


<span data-ttu-id="5824b-140">本節說明 MBAM 的用戶端管理原則定義，可在下列 GPO 節點找到： [**電腦設定] 系統** \\ **管理範本** \\ **Windows 元件** \\ **MDOP MBAM （BitLocker Management）**  \\  **用戶端管理**。</span><span class="sxs-lookup"><span data-stu-id="5824b-140">This section describes the Client Management policy definitions for MBAM, found at the following GPO node: **Computer Configuration**\\**Administrative Templates**\\**Windows Components**\\**MDOP MBAM (BitLocker Management)** \\ **Client Management**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5824b-141">原則名稱</span><span class="sxs-lookup"><span data-stu-id="5824b-141">Policy Name</span></span></th>
<th align="left"><span data-ttu-id="5824b-142">概覽和建議的原則設定</span><span class="sxs-lookup"><span data-stu-id="5824b-142">Overview and Suggested Policy Settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5824b-143">設定 MBAM 服務</span><span class="sxs-lookup"><span data-stu-id="5824b-143">Configure MBAM Services</span></span></p></td>
<td align="left"><p><span data-ttu-id="5824b-144">建議的設定： <strong> 已啟用</span><span class="sxs-lookup"><span data-stu-id="5824b-144">Suggested Configuration: <strong>Enabled</span></span></strong></p>
<ul>
<li><p><strong><span data-ttu-id="5824b-145">MBAM [恢復與硬體服務] 端點 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="5824b-145">MBAM Recovery and Hardware service endpoint</strong>.</span></span> <span data-ttu-id="5824b-146">這是您必須設定以啟用 MBAM 用戶端 BitLocker 加密管理的第一個策略設定。</span><span class="sxs-lookup"><span data-stu-id="5824b-146">This is the first policy setting that you must configure to enable the MBAM Client BitLocker encryption management.</span></span> <span data-ttu-id="5824b-147">針對此設定，請輸入與下列範例類似的端點位置： <strong> HTTP:// </strong><em> &lt; MBAM 管理及監視伺服器名稱 &gt; </em><strong> ： </strong><em> &lt; 埠該 web 服務已系結至 &gt; </em><strong> /MBAMRecoveryAndHardwareService/CoreService.svc </strong> 。</span><span class="sxs-lookup"><span data-stu-id="5824b-147">For this setting, enter the endpoint location similar to the following example: <strong>http://</strong><em>&lt;MBAM Administration and Monitoring Server Name&gt;</em><strong>:</strong><em>&lt;port the web service is bound to&gt;</em><strong>/MBAMRecoveryAndHardwareService/CoreService.svc</strong>.</span></span></p></li>
<li><p><strong><span data-ttu-id="5824b-148">選取要儲存的 BitLocker 復原資訊 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="5824b-148">Select BitLocker recovery information to store</strong>.</span></span> <span data-ttu-id="5824b-149">此原則設定可讓您設定金鑰復原服務來備份 BitLocker 恢復資訊。</span><span class="sxs-lookup"><span data-stu-id="5824b-149">This policy setting lets you configure the key recovery service to back up the BitLocker recovery information.</span></span> <span data-ttu-id="5824b-150">它也可讓您設定用於收集合規性和審核報告的狀態報表服務。</span><span class="sxs-lookup"><span data-stu-id="5824b-150">It also lets you configure the status reporting service for collecting compliance and audit reports.</span></span> <span data-ttu-id="5824b-151">原則提供一種系統管理方法，可復原由 BitLocker 加密的資料，以協助防止因缺少重要資訊而造成資料遺失。</span><span class="sxs-lookup"><span data-stu-id="5824b-151">The policy provides an administrative method of recovering data encrypted by BitLocker to help prevent data loss due to the lack of key information.</span></span> <span data-ttu-id="5824b-152">狀態報表和金鑰復原活動將會自動傳送到已設定的報表伺服器位置。</span><span class="sxs-lookup"><span data-stu-id="5824b-152">Status report and key recovery activity will automatically and silently be sent to the configured report server location.</span></span></p>
<p><span data-ttu-id="5824b-153">如果您未設定或停用此原則設定，就不會儲存金鑰復原資訊，且狀態報表和金鑰復原活動將不會報告給伺服器。</span><span class="sxs-lookup"><span data-stu-id="5824b-153">If you do not configure or if you disable this policy setting, the key recovery information will not be saved, and status report and key recovery activity will not be reported to server.</span></span> <span data-ttu-id="5824b-154">當此設定設定為 [復原 <strong> 密碼及金鑰套件] 時，系統會自動將復原 </strong> 密碼及金鑰套件備份到已設定的金鑰復原伺服器位置。</span><span class="sxs-lookup"><span data-stu-id="5824b-154">When this setting is set to <strong>Recovery Password and key package</strong>, the recovery password and key package will be automatically and silently backed up to the configured key recovery server location.</span></span></p></li>
<li><p><strong><span data-ttu-id="5824b-155">輸入用戶端檢查狀態頻率（分鐘） </strong> 。</span><span class="sxs-lookup"><span data-stu-id="5824b-155">Enter the client checking status frequency in minutes</strong>.</span></span> <span data-ttu-id="5824b-156">此原則設定會管理用戶端檢查 BitLocker 保護原則的頻率，以及用戶端電腦上的狀態。</span><span class="sxs-lookup"><span data-stu-id="5824b-156">This policy setting manages how frequently the client checks the BitLocker protection policies and the status on the client computer.</span></span> <span data-ttu-id="5824b-157">此原則也會管理將用戶端合規性狀態儲存到伺服器的頻率。</span><span class="sxs-lookup"><span data-stu-id="5824b-157">This policy also manages how frequently the client compliance status is saved to the server.</span></span> <span data-ttu-id="5824b-158">用戶端會檢查用戶端電腦上的 BitLocker 保護原則和狀態，同時也會以設定的頻率來備份用戶端復原金鑰。</span><span class="sxs-lookup"><span data-stu-id="5824b-158">The client checks the BitLocker protection policies and status on the client computer, and it also backs up the client recovery key at the configured frequency.</span></span></p>
<p><span data-ttu-id="5824b-159">根據公司所建立的需求來設定此頻率，以查看電腦合規性狀態的頻率，以及備份用戶端復原金鑰的頻率。</span><span class="sxs-lookup"><span data-stu-id="5824b-159">Set this frequency based on the requirement established by your company on how frequently to check the compliance status of the computer, and how frequently to back up the client recovery key.</span></span></p></li>
<li><p><strong><span data-ttu-id="5824b-160">MBAM 狀態報表服務端點 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="5824b-160">MBAM Status reporting service endpoint</strong>.</span></span> <span data-ttu-id="5824b-161">這是您必須設定以啟用 MBAM 用戶端 BitLocker 加密管理的第二個原則設定。</span><span class="sxs-lookup"><span data-stu-id="5824b-161">This is the second policy setting that you must configure to enable MBAM Client BitLocker encryption management.</span></span> <span data-ttu-id="5824b-162">針對此設定，請使用下列範例輸入端點位置： <strong> HTTP:// </strong><em> &lt; MBAM 管理和監視伺服器名稱 &gt; </em><strong> ： </strong><em> &lt; 埠該 web 服務已系結至 &gt; </em><strong> /MBAMComplianceStatusService/StatusReportingService。</span><span class="sxs-lookup"><span data-stu-id="5824b-162">For this setting, enter the endpoint location by using the following example: <strong>http://</strong><em>&lt;MBAM Administration and Monitoring Server Name&gt;</em><strong>:</strong><em>&lt;port the web service is bound to&gt;</em><strong>/MBAMComplianceStatusService/StatusReportingService.</span></span> <span data-ttu-id="5824b-163">svc </strong> 。</span><span class="sxs-lookup"><span data-stu-id="5824b-163">svc</strong>.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5824b-164">允許硬體相容性檢查</span><span class="sxs-lookup"><span data-stu-id="5824b-164">Allow hardware compatibility checking</span></span></p></td>
<td align="left"><p><span data-ttu-id="5824b-165">建議的設定： <strong> 已啟用</span><span class="sxs-lookup"><span data-stu-id="5824b-165">Suggested Configuration: <strong>Enabled</span></span></strong></p>
<p><span data-ttu-id="5824b-166">此原則設定可讓您在 MBAM 用戶端電腦的磁片磁碟機上啟用 BitLocker 保護之前，管理硬體相容性驗證。</span><span class="sxs-lookup"><span data-stu-id="5824b-166">This policy setting lets you manage the verification of hardware compatibility before you enable BitLocker protection on drives of MBAM client computers.</span></span></p>
<p><span data-ttu-id="5824b-167">如果您的企業的電腦硬體或電腦不支援信任的平臺模組（TPM），您就應該啟用此原則選項。</span><span class="sxs-lookup"><span data-stu-id="5824b-167">You should enable this policy option if your enterprise has older computer hardware or computers that do not support Trusted Platform Module (TPM).</span></span> <span data-ttu-id="5824b-168">如果下列其中一個準則為 true，請啟用硬體相容性驗證，以確保 MBAM 僅適用于支援 BitLocker 的電腦模型。</span><span class="sxs-lookup"><span data-stu-id="5824b-168">If either of these criteria is true, enable the hardware compatibility verification to make sure that MBAM is applied only to computer models that support BitLocker.</span></span> <span data-ttu-id="5824b-169">如果貴組織中的所有電腦都支援 BitLocker，您就不需要部署硬體相容性，而且您可以將此原則設定為 [ <strong> 未設定] </strong> 。</span><span class="sxs-lookup"><span data-stu-id="5824b-169">If all computers in your organization support BitLocker, you do not have to deploy the Hardware Compatibility, and you can set this policy to <strong>Not Configured</strong>.</span></span></p>
<p><span data-ttu-id="5824b-170">如果您啟用此原則設定，在策略在電腦磁碟機上啟用 BitLocker 保護前，每24小時都會驗證一次電腦的硬體相容性清單。</span><span class="sxs-lookup"><span data-stu-id="5824b-170">If you enable this policy setting, the model of the computer is validated against the hardware compatibility list once every 24 hours, before the policy enables BitLocker protection on a computer drive.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="5824b-171">注意</span><span class="sxs-lookup"><span data-stu-id="5824b-171">Note</span></span></strong><br/><p><span data-ttu-id="5824b-172">在啟用此原則設定之前，請確認您已 <strong> </strong> 在 [ <strong> 設定 MBAM 服務原則] 選項中設定了 [MBAM 復原與硬體服務端點] 設定 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="5824b-172">Before enabling this policy setting, make sure that you have configured the <strong>MBAM Recovery and Hardware service endpoint</strong> setting in the <strong>Configure MBAM Services</strong> policy options.</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="5824b-173">如果您停用或不設定此原則設定，就不會針對硬體相容性清單驗證電腦模型。</span><span class="sxs-lookup"><span data-stu-id="5824b-173">If you either disable or do not configure this policy setting, the computer model is not validated against the hardware compatibility list.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5824b-174">設定使用者豁免原則</span><span class="sxs-lookup"><span data-stu-id="5824b-174">Configure user exemption policy</span></span></p></td>
<td align="left"><p><span data-ttu-id="5824b-175">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="5824b-175">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="5824b-176">此原則設定可讓您設定網站位址、電子郵件地址或電話號碼，這將會指示使用者從 BitLocker 加密要求例外。</span><span class="sxs-lookup"><span data-stu-id="5824b-176">This policy setting lets you configure a web site address, email address, or phone number that will instruct a user to request an exemption from BitLocker encryption.</span></span></p>
<p><span data-ttu-id="5824b-177">如果您啟用此原則設定並提供網站位址、電子郵件地址或電話號碼，使用者將會看到一個對話方塊，其中顯示如何針對 BitLocker 保護申請免除的相關指示。</span><span class="sxs-lookup"><span data-stu-id="5824b-177">If you enable this policy setting and provide a web site address, email address, or phone number, users will see a dialog with instructions on how to apply for an exemption from BitLocker protection.</span></span> <span data-ttu-id="5824b-178">如需如何為使用者啟用 BitLocker 加密免除的詳細資訊，請參閱 <a href="how-to-manage-user-bitlocker-encryption-exemptions-mbam-1.md" data-raw-source="[How to Manage User BitLocker Encryption Exemptions](how-to-manage-user-bitlocker-encryption-exemptions-mbam-1.md)"> 如何管理使用者 Bitlocker 加密免除 </a> 。</span><span class="sxs-lookup"><span data-stu-id="5824b-178">For more information about how to enable BitLocker encryption exemptions for users, see <a href="how-to-manage-user-bitlocker-encryption-exemptions-mbam-1.md" data-raw-source="[How to Manage User BitLocker Encryption Exemptions](how-to-manage-user-bitlocker-encryption-exemptions-mbam-1.md)">How to Manage User BitLocker Encryption Exemptions</a>.</span></span></p>
<p><span data-ttu-id="5824b-179">如果您停用或不設定此原則設定，就不會向使用者顯示如何申請免除申請的指示。</span><span class="sxs-lookup"><span data-stu-id="5824b-179">If you either disable or do not configure this policy setting, the instructions about how to apply for an exemption request will not be presented to users.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="5824b-180">注意</span><span class="sxs-lookup"><span data-stu-id="5824b-180">Note</span></span></strong><br/><p><span data-ttu-id="5824b-181">使用者豁免是針對每個使用者管理，而不是針對每個電腦。</span><span class="sxs-lookup"><span data-stu-id="5824b-181">User exemption is managed per user, not per computer.</span></span> <span data-ttu-id="5824b-182">如果有多個使用者登入同一部電腦，而一位使用者並未免除，電腦將會經過加密。</span><span class="sxs-lookup"><span data-stu-id="5824b-182">If multiple users log on to the same computer and one user is not exempt, the computer will be encrypted.</span></span></p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="5824b-183">固定的磁片磁碟機原則定義</span><span class="sxs-lookup"><span data-stu-id="5824b-183">Fixed Drive policy definitions</span></span>


<span data-ttu-id="5824b-184">本節說明 MBAM 的固定磁片磁碟機原則定義，可在下列 GPO 節點找到： [電腦設定]**系統** \\ **管理範本** \\ **Windows 元件** \\ **MDOP MBAM （BitLocker Management）** 已  \\  **固定的磁片磁碟機**。</span><span class="sxs-lookup"><span data-stu-id="5824b-184">This section describes the Fixed Drive policy definitions for MBAM, which can be found at the following GPO node: **Computer Configuration**\\**Administrative Templates**\\**Windows Components**\\**MDOP MBAM (BitLocker Management)** \\ **Fixed Drive**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5824b-185">原則名稱</span><span class="sxs-lookup"><span data-stu-id="5824b-185">Policy Name</span></span></th>
<th align="left"><span data-ttu-id="5824b-186">[概覽] 和 [建議的原則] 設定</span><span class="sxs-lookup"><span data-stu-id="5824b-186">Overview and Suggested Policy Setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5824b-187">固定資料磁片磁碟機加密設定</span><span class="sxs-lookup"><span data-stu-id="5824b-187">Fixed data drive encryption settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="5824b-188">建議 <strong> </strong> 的設定： [啟用]，然後選取 [ <strong> 啟用自動解鎖固定資料磁碟機] </strong> 核取方塊（如果需要加密作業系統卷）。</span><span class="sxs-lookup"><span data-stu-id="5824b-188">Suggested Configuration: <strong>Enabled</strong>, and select the <strong>Enable auto-unlock fixed data drive</strong> check box if the operating system volume is required to be encrypted.</span></span></p>
<p><span data-ttu-id="5824b-189">此原則設定可讓您管理是否要加密固定的磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="5824b-189">This policy setting lets you manage whether or not to encrypt the fixed drives.</span></span></p>
<p><span data-ttu-id="5824b-190">當您啟用此原則時，請勿停 <strong> 用設定固定資料磁碟機的密碼使用 </strong> 原則。</span><span class="sxs-lookup"><span data-stu-id="5824b-190">When you enable this policy, do not disable the <strong>Configure use of password for fixed data drives</strong> policy.</span></span></p>
<p><span data-ttu-id="5824b-191">如果 <strong> 已選取 [啟用自動解鎖固定資料磁碟機] </strong> 核取方塊，則必須加密作業系統量。</span><span class="sxs-lookup"><span data-stu-id="5824b-191">If the <strong>Enable auto-unlock fixed data drive</strong> check box is selected, the operating system volume must be encrypted.</span></span></p>
<p><span data-ttu-id="5824b-192">如果您啟用此原則設定，使用者必須將所有固定磁片放在 BitLocker 保護之下，這將會加密磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="5824b-192">If you enable this policy setting, users are required to put all fixed drives under BitLocker protection, which will encrypt the drives.</span></span></p>
<p><span data-ttu-id="5824b-193">如果您未設定此原則，或如果您停用此原則，使用者就不需要將固定磁片放在 BitLocker 保護下。</span><span class="sxs-lookup"><span data-stu-id="5824b-193">If you do not configure this policy or if you disable this policy, users are not required to put fixed drives under BitLocker protection.</span></span></p>
<p><span data-ttu-id="5824b-194">如果您停用這項原則，MBAM agent 會解密任何已加密的固定磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="5824b-194">If you disable this policy, the MBAM agent decrypts any encrypted fixed drives.</span></span></p>
<p><span data-ttu-id="5824b-195">如果不需要加密作業系統卷，請清除 [ <strong> 啟用自動解鎖固定資料磁碟機] </strong> 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="5824b-195">If encrypting the operating system volume is not required, clear the <strong>Enable auto-unlock fixed data drive</strong> check box.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5824b-196">拒絕 [寫入] 許可權給不受 BitLocker 保護的固定磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="5824b-196">Deny “write” permission to fixed drives that are not protected by BitLocker</span></span></p></td>
<td align="left"><p><span data-ttu-id="5824b-197">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="5824b-197">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="5824b-198">此原則設定決定電腦上固定磁片磁碟機是否需要 BitLocker 保護，才能讓它們能寫入。</span><span class="sxs-lookup"><span data-stu-id="5824b-198">This policy setting determines if BitLocker protection is required for fixed drives on a computer so that they are writable.</span></span> <span data-ttu-id="5824b-199">當您開啟 BitLocker 時，就會套用此原則設定。</span><span class="sxs-lookup"><span data-stu-id="5824b-199">This policy setting is applied when you turn on BitLocker.</span></span></p>
<p><span data-ttu-id="5824b-200">如果未設定原則，電腦上所有的固定磁片磁碟機都會以讀/寫許可權掛載。</span><span class="sxs-lookup"><span data-stu-id="5824b-200">When the policy is not configured, all fixed drives on the computer are mounted with read/write permissions.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5824b-201">允許從較舊版本的 Windows 存取受 BitLocker 保護的固定磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="5824b-201">Allow access to BitLocker-protected fixed drives from earlier versions of Windows</span></span></p></td>
<td align="left"><p><span data-ttu-id="5824b-202">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="5824b-202">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="5824b-203">在執行 Windows Server 2008、Windows Vista、windows XP （含 SP3）或 Windows XP （含 SP2）的電腦上，啟用此原則來解除鎖定並查看以檔案配置資料表（FAT）檔案系統格式化的固定磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="5824b-203">Enable this policy to unlock and view the fixed drives that are formatted with the file allocation table (FAT) file system on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2.</span></span></p>
<p><span data-ttu-id="5824b-204">這些作業系統對受 BitLocker 保護的磁片磁碟機擁有唯讀許可權。</span><span class="sxs-lookup"><span data-stu-id="5824b-204">These operating systems have read-only permissions to BitLocker-protected drives.</span></span></p>
<p><span data-ttu-id="5824b-205">當原則停用時，使用 FAT 檔案系統格式化的固定磁片磁碟機將無法解除鎖定，而且無法在執行 Windows Server 2008、Windows Vista、Windows XP （含 SP3）的電腦上，或使用 SP2 的 Windows XP 中查看其內容。</span><span class="sxs-lookup"><span data-stu-id="5824b-205">When the policy is disabled, fixed drives formatted with the FAT file system cannot be unlocked and their content cannot be viewed on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5824b-206">設定在固定磁片磁碟機使用密碼</span><span class="sxs-lookup"><span data-stu-id="5824b-206">Configure use of password for fixed drives</span></span></p></td>
<td align="left"><p><span data-ttu-id="5824b-207">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="5824b-207">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="5824b-208">啟用此原則，在固定磁片磁碟機上設定密碼保護。</span><span class="sxs-lookup"><span data-stu-id="5824b-208">Enable this policy to configure password protection on fixed drives.</span></span></p>
<p><span data-ttu-id="5824b-209">如果未設定原則，預設設定就會支援密碼，這不會包含密碼複雜性需求，且只需要八個字元。</span><span class="sxs-lookup"><span data-stu-id="5824b-209">When the policy is not configured, passwords will be supported with the default settings, which do not include password complexity requirements and require only eight characters.</span></span></p>
<p><span data-ttu-id="5824b-210">若要獲得較高的安全性，請啟用此原則，並選取 [ <strong> 需要密碼才能修正資料磁碟機] </strong> ，選取 <strong> [需要密碼複雜性] </strong> ，然後設定所需的 <strong> 最小密碼長度 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="5824b-210">For higher security, enable this policy and select <strong>Require password for fixed data drive</strong>, select <strong>Require password complexity</strong>, and set the desired <strong>minimum password length</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5824b-211">選擇如何復原受 BitLocker 保護的固定磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="5824b-211">Choose how BitLocker-protected fixed drives can be recovered</span></span></p></td>
<td align="left"><p><span data-ttu-id="5824b-212">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="5824b-212">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="5824b-213">設定此原則以啟用 BitLocker 資料復原代理程式，或將 BitLocker 復原資訊儲存至 Active Directory 網域服務（AD DS）。</span><span class="sxs-lookup"><span data-stu-id="5824b-213">Configure this policy to enable the BitLocker data recovery agent or to save BitLocker recovery information to Active Directory Domain Services (AD DS).</span></span></p>
<p><span data-ttu-id="5824b-214">如果未設定此原則，就會允許 BitLocker 資料復原代理程式，且不會將復原資訊備份到 AD DS。</span><span class="sxs-lookup"><span data-stu-id="5824b-214">When this policy is not configured, the BitLocker data recovery agent is allowed, and recovery information is not backed up to AD DS.</span></span> <span data-ttu-id="5824b-215">MBAM 不需要將復原資訊備份到 AD DS。</span><span class="sxs-lookup"><span data-stu-id="5824b-215">MBAM does not require the recovery information to be backed up to AD DS.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="5824b-216">作業系統磁片磁碟機原則定義</span><span class="sxs-lookup"><span data-stu-id="5824b-216">Operating System Drive policy definitions</span></span>


<span data-ttu-id="5824b-217">本節說明 MBAM 的作業系統磁片磁碟機原則定義，可在下列 GPO 節點找到： [電腦設定]**系統** \\ **管理範本** \\ **Windows 元件** \\ **MDOP MBAM （BitLocker 管理）**  \\  **作業系統磁片磁碟機**。</span><span class="sxs-lookup"><span data-stu-id="5824b-217">This section describes the Operating System Drive policy definitions for MBAM, found at the following GPO node: **Computer Configuration**\\**Administrative Templates**\\**Windows Components**\\**MDOP MBAM (BitLocker Management)** \\ **Operating System Drive**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5824b-218">原則名稱</span><span class="sxs-lookup"><span data-stu-id="5824b-218">Policy Name</span></span></th>
<th align="left"><span data-ttu-id="5824b-219">[概覽] 和 [建議的原則] 設定</span><span class="sxs-lookup"><span data-stu-id="5824b-219">Overview and Suggested Policy Setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5824b-220">作業系統磁片磁碟機加密設定</span><span class="sxs-lookup"><span data-stu-id="5824b-220">Operating system drive encryption settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="5824b-221">建議的設定： <strong> 已啟用</span><span class="sxs-lookup"><span data-stu-id="5824b-221">Suggested configuration: <strong>Enabled</span></span></strong></p>
<p><span data-ttu-id="5824b-222">此原則設定決定作業系統磁片磁碟機是否會經過加密。</span><span class="sxs-lookup"><span data-stu-id="5824b-222">This policy setting determines if the operating system drive will be encrypted.</span></span></p>
<p><span data-ttu-id="5824b-223">設定此原則以執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="5824b-223">Configure this policy to do the following:</span></span></p>
<ul>
<li><p><span data-ttu-id="5824b-224">針對作業系統磁片磁碟機強制執行 BitLocker 保護。</span><span class="sxs-lookup"><span data-stu-id="5824b-224">Enforce BitLocker protection for the operating system drive.</span></span></p></li>
<li><p><span data-ttu-id="5824b-225">設定 PIN 使用量，以使用受信任的平臺模組（TPM） PIN 來保護作業系統。</span><span class="sxs-lookup"><span data-stu-id="5824b-225">Configure PIN usage to use a Trusted Platform Module (TPM) PIN for operating system protection.</span></span></p></li>
<li><p><span data-ttu-id="5824b-226">設定增強的啟動 Pin，以允許字元（例如大寫、小寫字母和數位）。</span><span class="sxs-lookup"><span data-stu-id="5824b-226">Configure enhanced startup PINs to permit characters such as uppercase and lowercase letters, and numbers.</span></span> <span data-ttu-id="5824b-227">MBAM 不支援使用符號和空格來增強 Pin，即使 BitLocker 支援符號和空格也一樣。</span><span class="sxs-lookup"><span data-stu-id="5824b-227">MBAM does not support the use of symbols and spaces for enhanced PINs, even though BitLocker supports symbols and spaces.</span></span></p></li>
</ul>
<p><span data-ttu-id="5824b-228">如果您啟用此原則設定，就必須由使用者使用 BitLocker 來保護作業系統磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="5824b-228">If you enable this policy setting, users are required to secure the operating system drive by using BitLocker.</span></span></p>
<p><span data-ttu-id="5824b-229">如果您未設定或停用此設定，則不需要使用者使用 BitLocker 來保護作業系統磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="5824b-229">If you do not configure or if you disable the setting, users are not required to secure the operating system drive by using BitLocker.</span></span></p>
<p><span data-ttu-id="5824b-230">如果您停用這個原則，MBAM 代理程式會解密作業系統的磁片卷（如果它是加密的）。</span><span class="sxs-lookup"><span data-stu-id="5824b-230">If you disable this policy, the MBAM agent decrypts the operating system volume if it is encrypted.</span></span></p>
<p><span data-ttu-id="5824b-231">啟用此原則設定時，系統會要求使用者使用 BitLocker 保護來保護作業系統，而且磁片磁碟機已加密。</span><span class="sxs-lookup"><span data-stu-id="5824b-231">When it is enabled, this policy setting requires users to secure the operating system by using BitLocker protection, and the drive is encrypted.</span></span> <span data-ttu-id="5824b-232">根據您的加密需求，您可以選取作業系統磁片磁碟機的保護方法。</span><span class="sxs-lookup"><span data-stu-id="5824b-232">Based on your encryption requirements, you may select the method of protection for the operating system drive.</span></span></p>
<p><span data-ttu-id="5824b-233">如需較高的安全性需求，請使用 TPM + PIN、允許增強的 Pin，並將最小 PIN 長度設定為八個字元。</span><span class="sxs-lookup"><span data-stu-id="5824b-233">For higher security requirements, use TPM + PIN, allow enhanced PINs, and set the minimum PIN length to eight characters.</span></span></p>
<p><span data-ttu-id="5824b-234">使用 TPM + PIN 保護器啟用此原則時，您可以考慮停用 [ <strong> 系統 </strong>  /  <strong> 電源管理 </strong>  /  <strong> 睡眠設定 </strong> ] 底下的下列原則：</span><span class="sxs-lookup"><span data-stu-id="5824b-234">When this policy is enabled with the TPM + PIN protector, you can consider disabling the following policies under <strong>System</strong> / <strong>Power Management</strong> / <strong>Sleep Settings</strong>:</span></span></p>
<ul>
<li><p><span data-ttu-id="5824b-235">在休眠（電源開啟）時允許待機狀態（S1-S3）</span><span class="sxs-lookup"><span data-stu-id="5824b-235">Allow Standby States (S1-S3) When Sleeping (Plugged In)</span></span></p></li>
<li><p><span data-ttu-id="5824b-236">在睡眠時允許待機狀態（S1-S3）（使用電池）</span><span class="sxs-lookup"><span data-stu-id="5824b-236">Allow Standby States (S1-S3) When Sleeping (On Battery)</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5824b-237">設定 TPM 平臺驗證設定檔</span><span class="sxs-lookup"><span data-stu-id="5824b-237">Configure TPM platform validation profile</span></span></p></td>
<td align="left"><p><span data-ttu-id="5824b-238">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="5824b-238">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="5824b-239">此原則設定可讓您設定電腦上的 TPM 安全硬體如何保護 BitLocker 加密金鑰。</span><span class="sxs-lookup"><span data-stu-id="5824b-239">This policy setting lets you configure how the TPM security hardware on a computer secures the BitLocker encryption key.</span></span> <span data-ttu-id="5824b-240">如果電腦沒有相容的 TPM，或者 BitLocker 已啟用 TPM 保護，則此原則設定不適用。</span><span class="sxs-lookup"><span data-stu-id="5824b-240">This policy setting does not apply if the computer does not have a compatible TPM or if BitLocker already has TPM protection enabled.</span></span></p>
<p><span data-ttu-id="5824b-241">如果未設定此原則，TPM 會使用預設平臺驗證設定檔或由安裝腳本指定的平臺驗證設定檔。</span><span class="sxs-lookup"><span data-stu-id="5824b-241">When this policy is not configured, the TPM uses the default platform validation profile or the platform validation profile specified by the setup script.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5824b-242">選擇如何復原受 BitLocker 保護的作業系統磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="5824b-242">Choose how to recover BitLocker-protected operating system drives</span></span></p></td>
<td align="left"><p><span data-ttu-id="5824b-243">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="5824b-243">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="5824b-244">設定此原則以啟用 BitLocker 資料復原代理程式，或將 BitLocker 復原資訊儲存至 Active Directory 網域服務（AD DS）。</span><span class="sxs-lookup"><span data-stu-id="5824b-244">Configure this policy to enable the BitLocker data recovery agent or to save BitLocker recovery information to Active Directory Domain Services (AD DS).</span></span></p>
<p><span data-ttu-id="5824b-245">如果未設定此原則，就可以使用資料復原代理程式，且不會將復原資訊備份到 AD DS。</span><span class="sxs-lookup"><span data-stu-id="5824b-245">When this policy is not configured, the data recovery agent is allowed, and the recovery information is not backed up to AD DS.</span></span></p>
<p><span data-ttu-id="5824b-246">MBAM 操作不需要將復原資訊備份到 AD DS。</span><span class="sxs-lookup"><span data-stu-id="5824b-246">MBAM operation does not require the recovery information to be backed up to AD DS.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="5824b-247">移除磁片磁碟機原則定義</span><span class="sxs-lookup"><span data-stu-id="5824b-247">Removable Drive policy definitions</span></span>


<span data-ttu-id="5824b-248">本節說明 MBAM 的抽取式磁碟磁碟機原則定義，可在下列 GPO 節點找到： [**電腦設定] 系統** \\ **管理範本** \\ **Windows 元件** \\ **MDOP MBAM （BitLocker 管理）**  \\  **抽取式磁碟磁碟機**。</span><span class="sxs-lookup"><span data-stu-id="5824b-248">This section describes the Removable Drive Policy definitions for MBAM, found at the following GPO node: **Computer Configuration**\\**Administrative Templates**\\**Windows Components**\\**MDOP MBAM (BitLocker Management)** \\ **Removable Drive**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="5824b-249">原則名稱</span><span class="sxs-lookup"><span data-stu-id="5824b-249">Policy Name</span></span></th>
<th align="left"><span data-ttu-id="5824b-250">[概覽] 和 [建議的原則] 設定</span><span class="sxs-lookup"><span data-stu-id="5824b-250">Overview and Suggested Policy Setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5824b-251">控制抽取式磁碟磁碟機上的 BitLocker 使用</span><span class="sxs-lookup"><span data-stu-id="5824b-251">Control the use of BitLocker on removable drives</span></span></p></td>
<td align="left"><p><span data-ttu-id="5824b-252">建議的設定： <strong> 已啟用</span><span class="sxs-lookup"><span data-stu-id="5824b-252">Suggested configuration: <strong>Enabled</span></span></strong></p>
<p><span data-ttu-id="5824b-253">此原則控制如何在可移動資料磁碟機上使用 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="5824b-253">This policy controls the use of BitLocker on removable data drives.</span></span></p>
<p><span data-ttu-id="5824b-254">啟用 [ <strong> 允許使用者在可移動資料磁碟機上套用 bitlocker 保護 </strong> ] 選項，以允許使用者在可移除的資料磁碟機上執行 bitlocker 設定向導。</span><span class="sxs-lookup"><span data-stu-id="5824b-254">Enable the <strong>Allow users to apply BitLocker protection on removable data drives</strong> option, to allow users to run the BitLocker setup wizard on a removable data drive.</span></span></p>
<p><span data-ttu-id="5824b-255">啟用 [ <strong> 允許使用者暫停並解密可移動資料磁碟機上的 bitlocker] </strong> 選項，允許使用者從磁片磁碟機中移除 bitlocker 磁片磁碟機加密，或在執行維護時暫停加密。</span><span class="sxs-lookup"><span data-stu-id="5824b-255">Enable the <strong>Allow users to suspend and decrypt BitLocker on removable data drives</strong> option to allow users to remove BitLocker drive encryption from the drive or to suspend the encryption while maintenance is performed.</span></span></p>
<p><span data-ttu-id="5824b-256">如果已啟用此原則，且已 <strong> 選取 [允許使用者在可移動資料磁片磁碟機上套用 BitLocker 保護] </strong> 選項，則 MBAM 用戶端會將抽取式磁碟磁碟機的復原資訊儲存至 MBAM 金鑰復原伺服器，並允許使用者在密碼遺失時復原磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="5824b-256">When this policy is enabled and the <strong>Allow users to apply BitLocker protection on removable data drives</strong> option is selected, the MBAM Client saves the recovery information about removable drives to the MBAM key recovery server, and it allows users to recover the drive if the password is lost.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5824b-257">拒絕不受 BitLocker 保護的抽取式磁碟磁碟機的 [寫入] 許可權</span><span class="sxs-lookup"><span data-stu-id="5824b-257">Deny the “write” permissions to removable drives that are not protected by BitLocker</span></span></p></td>
<td align="left"><p><span data-ttu-id="5824b-258">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="5824b-258">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="5824b-259">啟用此原則以允許只寫許可權使用受 BitLocker 保護的磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="5824b-259">Enable this policy to allow write-only permissions to BitLocker protected drives.</span></span></p>
<p><span data-ttu-id="5824b-260">啟用此原則時，電腦上所有的可移動資料磁碟機都需要加密，才能允許寫入權限。</span><span class="sxs-lookup"><span data-stu-id="5824b-260">When this policy is enabled, all removable data drives on the computer require encryption before write permissions are allowed.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5824b-261">允許從舊版 Windows 存取受 BitLocker 保護的抽取式磁碟磁碟機</span><span class="sxs-lookup"><span data-stu-id="5824b-261">Allow access to BitLocker-protected removable drives from earlier versions of Windows</span></span></p></td>
<td align="left"><p><span data-ttu-id="5824b-262">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="5824b-262">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="5824b-263">在執行 Windows Server 2008、Windows Vista、windows XP （含 SP3）或 Windows XP （含 SP2）的電腦上，啟用此原則來解除鎖定並查看格式化為（FAT）檔案系統的固定磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="5824b-263">Enable this policy to unlock and view the fixed drives that are formatted with the (FAT) file system on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2.</span></span></p>
<p><span data-ttu-id="5824b-264">這些作業系統對受 BitLocker 保護的磁片磁碟機擁有唯讀許可權。</span><span class="sxs-lookup"><span data-stu-id="5824b-264">These operating systems have read-only permissions to BitLocker-protected drives.</span></span></p>
<p><span data-ttu-id="5824b-265">當原則停用時，無法在執行 Windows Server 2008、Windows Vista、windows XP 的電腦上，或使用 SP2，在執行 Windows Server、Windows Vista、Windows XP 或 Windows XP 的電腦上，查看以 FAT 檔案系統格式化的抽取式磁碟磁碟機。</span><span class="sxs-lookup"><span data-stu-id="5824b-265">When the policy is disabled, removable drives formatted with the FAT file system cannot be unlocked and their content cannot be viewed on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="5824b-266">設定可移除資料磁碟機的密碼使用方式</span><span class="sxs-lookup"><span data-stu-id="5824b-266">Configure the use of password for removable data drives</span></span></p></td>
<td align="left"><p><span data-ttu-id="5824b-267">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="5824b-267">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="5824b-268">啟用此原則，在可移動資料磁碟機上設定密碼保護。</span><span class="sxs-lookup"><span data-stu-id="5824b-268">Enable this policy to configure password protection on removable data drives.</span></span></p>
<p><span data-ttu-id="5824b-269">如果未設定此原則，預設設定就會支援密碼，這不會包含密碼複雜性需求，而且只需要八個字元。</span><span class="sxs-lookup"><span data-stu-id="5824b-269">When this policy is not configured, passwords are supported with the default settings, which do not include password complexity requirements and require only eight characters.</span></span></p>
<p><span data-ttu-id="5824b-270">若要提高安全性，您可以啟用此原則，然後選取 [ <strong> 移除資料磁碟機需要密碼] </strong> ，選取 <strong> [需要密碼複雜性] </strong> ，然後設定首選的 <strong> 最小密碼長度 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="5824b-270">For increased security, you can enable this policy and select <strong>Require password for removable data drive</strong>, select <strong>Require password complexity</strong>, and then set the preferred <strong>minimum password length</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="5824b-271">選擇可如何復原受 BitLocker 保護的抽取式磁碟磁碟機</span><span class="sxs-lookup"><span data-stu-id="5824b-271">Choose how BitLocker-protected removable drives can be recovered</span></span></p></td>
<td align="left"><p><span data-ttu-id="5824b-272">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="5824b-272">Suggested Configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="5824b-273">您可以設定此原則來啟用 BitLocker 資料復原代理程式，或將 BitLocker 復原資訊儲存至 Active Directory 網域服務（AD DS）。</span><span class="sxs-lookup"><span data-stu-id="5824b-273">You can configure this policy to enable the BitLocker data recovery agent or to save BitLocker recovery information to Active Directory Domain Services (AD DS).</span></span></p>
<p><span data-ttu-id="5824b-274">如果原則設定為 [ <strong> 未設定] </strong> ，則允許資料復原代理程式，且不會將復原資訊備份到 AD DS。</span><span class="sxs-lookup"><span data-stu-id="5824b-274">When the policy is set to <strong>Not Configured</strong>, the data recovery agent is allowed and recovery information is not backed up to AD DS.</span></span></p>
<p><span data-ttu-id="5824b-275">MBAM 操作不需要將復原資訊備份到 AD DS。</span><span class="sxs-lookup"><span data-stu-id="5824b-275">MBAM operation does not require the recovery information to be backed up to AD DS.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="5824b-276">相關主題</span><span class="sxs-lookup"><span data-stu-id="5824b-276">Related topics</span></span>


[<span data-ttu-id="5824b-277">MBAM 1.0 的環境準備</span><span class="sxs-lookup"><span data-stu-id="5824b-277">Preparing your Environment for MBAM 1.0</span></span>](preparing-your-environment-for-mbam-10.md)









