---
title: MBAM 2.5 群組原則需求規劃
description: MBAM 2.5 群組原則需求規劃
author: dansimp
ms.assetid: 82d545dc-3fbf-4b46-b62f-47fe178a7c44
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 4beeb9f88f16e7d48d145861c398a90fa29f3491
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810154"
---
# <span data-ttu-id="be52c-103">MBAM 2.5 群組原則需求規劃</span><span class="sxs-lookup"><span data-stu-id="be52c-103">Planning for MBAM 2.5 Group Policy Requirements</span></span>


<span data-ttu-id="be52c-104">使用下列資訊來判斷您可以用來管理企業中 Microsoft BitLocker 管理和監控（MBAM）用戶端電腦的 BitLocker 保護器類型。</span><span class="sxs-lookup"><span data-stu-id="be52c-104">Use the following information to determine the types of BitLocker protectors that you can use to manage the Microsoft BitLocker Administration and Monitoring (MBAM) client computers in your enterprise.</span></span>

## <span data-ttu-id="be52c-105">MBAM 支援的 BitLocker 保護器類型</span><span class="sxs-lookup"><span data-stu-id="be52c-105">Types of BitLocker protectors that MBAM supports</span></span>


<span data-ttu-id="be52c-106">MBAM 支援下列類型的 BitLocker 保護器。</span><span class="sxs-lookup"><span data-stu-id="be52c-106">MBAM supports the following types of BitLocker protectors.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="be52c-107">磁片磁碟機或卷的類型</span><span class="sxs-lookup"><span data-stu-id="be52c-107">Type of drive or volume</span></span></th>
<th align="left"><span data-ttu-id="be52c-108">支援的 BitLocker 保護器</span><span class="sxs-lookup"><span data-stu-id="be52c-108">Supported BitLocker protectors</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="be52c-109">作業系統量</span><span class="sxs-lookup"><span data-stu-id="be52c-109">Operating system volumes</span></span></p></td>
<td align="left"><ul>
<li><p><strong><span data-ttu-id="be52c-110">信賴平台模組 (TPM)</span><span class="sxs-lookup"><span data-stu-id="be52c-110">Trusted Platform Module (TPM)</span></span></strong></p></li>
<li><p><strong><span data-ttu-id="be52c-111">TPM + PIN</span><span class="sxs-lookup"><span data-stu-id="be52c-111">TPM + PIN</span></span></strong></p></li>
<li><p><strong><span data-ttu-id="be52c-112"></strong>只有在安裝 MBAM 之前已加密作業系統卷，才能支援 TPM + USB 金鑰</span><span class="sxs-lookup"><span data-stu-id="be52c-112">TPM + USB key</strong> – supported only when the operating system volume is encrypted before MBAM is installed</span></span></p></li>
<li><p><strong><span data-ttu-id="be52c-113"></strong> - 只有在安裝 MBAM 之前已加密作業系統卷，才支援 TPM + PIN + USB 金鑰</span><span class="sxs-lookup"><span data-stu-id="be52c-113">TPM + PIN + USB key</strong> - supported only when the operating system volume is encrypted before MBAM is installed</span></span></p></li>
<li><p><strong><span data-ttu-id="be52c-114"></strong> - 只有 Windows To Go 裝置、固定資料磁碟機、windows 8、windows 8.1 和 windows 10 裝置（沒有 TPM）支援密碼</span><span class="sxs-lookup"><span data-stu-id="be52c-114">Password</strong> - supported only for Windows To Go devices, fixed data drives, and Windows 8, Windows 8.1, and Windows 10 devices that do not have a TPM</span></span></p></li>
<li><p><strong><span data-ttu-id="be52c-115">自動套用數位密碼 </strong> - 作為大量加密的一部分，而且不需要在 Windows 7 上的 FIPS 模式中進行設定。</span><span class="sxs-lookup"><span data-stu-id="be52c-115">Numerical password</strong> - applied automatically as part of volume encryption and does not need to be configured except in FIPS mode on Windows 7</span></span></p></li>
<li><p><strong><span data-ttu-id="be52c-116">資料修復代理程式（DRA）</span><span class="sxs-lookup"><span data-stu-id="be52c-116">Data recovery agent (DRA)</span></span></strong></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="be52c-117">固定資料磁碟機</span><span class="sxs-lookup"><span data-stu-id="be52c-117">Fixed data drives</span></span></p></td>
<td align="left"><ul>
<li><p><strong><span data-ttu-id="be52c-118">密碼</span><span class="sxs-lookup"><span data-stu-id="be52c-118">Password</span></span></strong></p></li>
<li><p><strong><span data-ttu-id="be52c-119">自動解除鎖定</span><span class="sxs-lookup"><span data-stu-id="be52c-119">Auto-unlock</span></span></strong></p></li>
<li><p><strong><span data-ttu-id="be52c-120">自動套用數位密碼 </strong> - 作為大量加密的一部分，而且不需要在 Windows 7 上的 FIPS 模式中進行設定。</span><span class="sxs-lookup"><span data-stu-id="be52c-120">Numerical password</strong> - applied automatically as part of volume encryption and does not need to be configured except in FIPS mode on Windows 7</span></span></p></li>
<li><p><strong><span data-ttu-id="be52c-121">資料修復代理程式（DRA）</span><span class="sxs-lookup"><span data-stu-id="be52c-121">Data recovery agent (DRA)</span></span></strong></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="be52c-122">抽取式磁碟磁碟機</span><span class="sxs-lookup"><span data-stu-id="be52c-122">Removable drives</span></span></p></td>
<td align="left"><ul>
<li><p><strong><span data-ttu-id="be52c-123">密碼</span><span class="sxs-lookup"><span data-stu-id="be52c-123">Password</span></span></strong></p></li>
<li><p><strong><span data-ttu-id="be52c-124">自動解除鎖定</span><span class="sxs-lookup"><span data-stu-id="be52c-124">Auto-unlock</span></span></strong></p></li>
<li><p><strong><span data-ttu-id="be52c-125">自動套用數位密碼 </strong> - 作為大量加密的一部分，而且不需要進行設定</span><span class="sxs-lookup"><span data-stu-id="be52c-125">Numerical password</strong> - applied automatically as part of volume encryption and does not need to be configured</span></span></p></li>
<li><p><strong><span data-ttu-id="be52c-126">資料修復代理程式（DRA）</span><span class="sxs-lookup"><span data-stu-id="be52c-126">Data recovery agent (DRA)</span></span></strong></p></li>
</ul></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="be52c-127">支援已使用的空間加密 BitLocker 原則</span><span class="sxs-lookup"><span data-stu-id="be52c-127">Support for the Used Space Encryption BitLocker policy</span></span>

<span data-ttu-id="be52c-128">在 MBAM 2.5 SP1 中，如果您透過 BitLocker 群組原則啟用 [使用空間加密]，MBAM 用戶端就會接受這項功能。</span><span class="sxs-lookup"><span data-stu-id="be52c-128">In MBAM 2.5 SP1, if you enable Used Space Encryption via BitLocker Group policy, the MBAM Client honors it.</span></span>

<span data-ttu-id="be52c-129">這個群組原則設定稱為**在操作系統磁碟機上強制執行磁片磁碟機加密類型**，且位於下列 GPO 節點： [**電腦設定] 系統** &gt; **管理範本** &gt; **Windows 元件**（ &gt; **BitLocker 磁片磁碟機加密** &gt; **操作系統磁碟機**）。</span><span class="sxs-lookup"><span data-stu-id="be52c-129">This Group Policy setting is called **Enforce drive encryption type on operating system drives** and is located in the following GPO node: **Computer Configuration** &gt; **Administrative Templates** &gt; **Windows Components** &gt; **BitLocker Drive Encryption** &gt; **Operating System Drives**.</span></span> <span data-ttu-id="be52c-130">如果您啟用此原則，並選取 [**僅限已使用的空間**] 加密的加密類型，MBAM 將會服從原則，而 BitLocker 將只會將在該卷上使用的磁碟空間加密。</span><span class="sxs-lookup"><span data-stu-id="be52c-130">If you enable this policy and select the encryption type as **Used Space Only encryption**, MBAM will honor the policy and BitLocker will only encrypt disk space that is used on the volume.</span></span>

## <span data-ttu-id="be52c-131">如何取得 MBAM 群組原則範本並編輯設定</span><span class="sxs-lookup"><span data-stu-id="be52c-131">How to get the MBAM Group Policy Templates and edit the settings</span></span>


<span data-ttu-id="be52c-132">當您準備好要設定您想要的 MBAM 組原則設定時，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="be52c-132">When you are ready to configure the MBAM Group Policy settings you want, do the following:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="be52c-133">後續步驟</span><span class="sxs-lookup"><span data-stu-id="be52c-133">Steps to follow</span></span></th>
<th align="left"><span data-ttu-id="be52c-134">取得指示的位置</span><span class="sxs-lookup"><span data-stu-id="be52c-134">Where to get instructions</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="be52c-135">從 <a href="https://go.microsoft.com/fwlink/p/?LinkId=393941" data-raw-source="[How to Get MDOP Group Policy (.admx) Templates](https://go.microsoft.com/fwlink/p/?LinkId=393941)"> 如何取得 MDOP 組原則（admx）範本，複製 MBAM 群組原則範本 </a> ，並將其安裝在能夠執行群組原則管理主控台（GPMC）或高級群組原則管理（AGPM）的電腦上。</span><span class="sxs-lookup"><span data-stu-id="be52c-135">Copy the MBAM Group Policy Templates from <a href="https://go.microsoft.com/fwlink/p/?LinkId=393941" data-raw-source="[How to Get MDOP Group Policy (.admx) Templates](https://go.microsoft.com/fwlink/p/?LinkId=393941)">How to Get MDOP Group Policy (.admx) Templates</a> and install them on a computer that is capable of running the Group Policy Management Console (GPMC) or Advanced Group Policy Management (AGPM).</span></span></p></td>
<td align="left"><p><a href="copying-the-mbam-25-group-policy-templates.md" data-raw-source="[Copying the MBAM 2.5 Group Policy Templates](copying-the-mbam-25-group-policy-templates.md)"><span data-ttu-id="be52c-136">複製 MBAM 2.5 群組原則範本</span><span class="sxs-lookup"><span data-stu-id="be52c-136">Copying the MBAM 2.5 Group Policy Templates</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="be52c-137">設定您想要在企業中使用的群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="be52c-137">Configure the Group Policy settings that you want to use in your enterprise.</span></span></p></td>
<td align="left"><p><a href="editing-the-mbam-25-group-policy-settings.md" data-raw-source="[Editing the MBAM 2.5 Group Policy Settings](editing-the-mbam-25-group-policy-settings.md)"><span data-ttu-id="be52c-138">編輯 MBAM 2.5 群組原則設定</span><span class="sxs-lookup"><span data-stu-id="be52c-138">Editing the MBAM 2.5 Group Policy Settings</span></span></a></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="be52c-139">MBAM 群組原則設定的描述</span><span class="sxs-lookup"><span data-stu-id="be52c-139">Descriptions of the MBAM Group Policy settings</span></span>


<span data-ttu-id="be52c-140">**MDOP MBAM （BitLocker 管理）** GPO 節點包含四個全域原則設定和四個子 GPO 節點：**用戶端管理**、**固定磁片**磁碟機、**作業系統磁片磁碟機**及**抽取式磁碟磁碟機**。</span><span class="sxs-lookup"><span data-stu-id="be52c-140">The **MDOP MBAM (BitLocker Management)** GPO node contains four global policy settings and four child GPO nodes: **Client Management**, **Fixed Drive**, **Operating System Drive**, and **Removable Drive**.</span></span> <span data-ttu-id="be52c-141">下列各節說明 MBAM 群組原則設定的設定並提供建議。</span><span class="sxs-lookup"><span data-stu-id="be52c-141">The following sections describe and suggest settings for the MBAM Group Policy settings.</span></span>

**<span data-ttu-id="be52c-142">重要</span><span class="sxs-lookup"><span data-stu-id="be52c-142">Important</span></span>**  
<span data-ttu-id="be52c-143">請勿變更**BitLocker 磁片磁碟機加密**節點中的群組原則設定，否則 MBAM 將無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="be52c-143">Do not change the Group Policy settings in the **BitLocker Drive Encryption** node, or MBAM will not work correctly.</span></span> <span data-ttu-id="be52c-144">當您設定在**MDOP MBAM （BitLocker 管理）** 節點中的設定時，MBAM 會自動設定此節點中的設定。</span><span class="sxs-lookup"><span data-stu-id="be52c-144">MBAM automatically configures the settings in this node for you when you configure the settings in the **MDOP MBAM (BitLocker Management)** node.</span></span>



### <span data-ttu-id="be52c-145">通用群組策略定義</span><span class="sxs-lookup"><span data-stu-id="be52c-145">Global Group Policy definitions</span></span>

<span data-ttu-id="be52c-146">本節說明下列 GPO 節點上的 MBAM 通用群組原則定義：**電腦**設定 &gt; **原則** &gt; **管理範本** &gt; **Windows 元件** &gt; **MDOP MBAM （BitLocker 管理）**。</span><span class="sxs-lookup"><span data-stu-id="be52c-146">This section describes MBAM Global Group Policy definitions at the following GPO node: **Computer Configuration** &gt; **Policies** &gt; **Administrative Templates** &gt; **Windows Components** &gt; **MDOP MBAM (BitLocker Management)**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="be52c-147">原則名稱</span><span class="sxs-lookup"><span data-stu-id="be52c-147">Policy name</span></span></th>
<th align="left"><span data-ttu-id="be52c-148">概覽及建議的群組原則設定</span><span class="sxs-lookup"><span data-stu-id="be52c-148">Overview and suggested Group Policy settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="be52c-149">選擇磁片磁碟機加密方法與密碼強度</span><span class="sxs-lookup"><span data-stu-id="be52c-149">Choose drive encryption method and cipher strength</span></span></p></td>
<td align="left"><p><span data-ttu-id="be52c-150">建議的設定： <strong> 已啟用</span><span class="sxs-lookup"><span data-stu-id="be52c-150">Suggested configuration: <strong>Enabled</span></span></strong></p>
<p><span data-ttu-id="be52c-151">將此原則設定為使用特定的加密方法與密碼強度。</span><span class="sxs-lookup"><span data-stu-id="be52c-151">Configure this policy to use a specific encryption method and cipher strength.</span></span></p>
<p><span data-ttu-id="be52c-152">如果未設定此原則，BitLocker 會使用預設的加密方法： AES 128 位與擴散器。</span><span class="sxs-lookup"><span data-stu-id="be52c-152">When this policy is not configured, BitLocker uses the default encryption method: AES 128-bit with Diffuser.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="be52c-153">注意</span><span class="sxs-lookup"><span data-stu-id="be52c-153">Note</span></span></strong><br/><p><span data-ttu-id="be52c-154">BitLocker 電腦合規性報告的問題會使其顯示 &quot; 密碼強度的 [未知] &quot; ，即使您使用的是預設值也一樣。</span><span class="sxs-lookup"><span data-stu-id="be52c-154">An issue with the BitLocker Computer Compliance report causes it to display &quot;unknown&quot; for the cipher strength, even if you are using the default value.</span></span> <span data-ttu-id="be52c-155">若要解決此問題，請確定您已啟用此設定，並設定密碼強度的值。</span><span class="sxs-lookup"><span data-stu-id="be52c-155">To work around this issue, make sure you enable this setting and set a value for cipher strength.</span></span></p>
</div>
<div>

</div>
<ul>
<li><p><span data-ttu-id="be52c-156">僅適用于 Windows 7 的 AES 128 位（含擴散器）</span><span class="sxs-lookup"><span data-stu-id="be52c-156">AES 128-bit with Diffuser – for Windows 7 only</span></span></p></li>
<li><p><span data-ttu-id="be52c-157">適用于 Windows 8、Windows 8.1 和 Windows 10 的 AES 128</span><span class="sxs-lookup"><span data-stu-id="be52c-157">AES 128 for Windows 8, Windows 8.1, and Windows 10</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="be52c-158">在重新開機時避免記憶體覆寫</span><span class="sxs-lookup"><span data-stu-id="be52c-158">Prevent memory overwrite on restart</span></span></p></td>
<td align="left"><p><span data-ttu-id="be52c-159">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="be52c-159">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="be52c-160">設定此原則以改善重新開機效能，而不在重新開機時覆寫記憶體中的 BitLocker 機密。</span><span class="sxs-lookup"><span data-stu-id="be52c-160">Configure this policy to improve restart performance without overwriting BitLocker secrets in memory on restart.</span></span></p>
<p><span data-ttu-id="be52c-161">如果未設定此原則，當電腦重新開機時，會從記憶體中移除 BitLocker 密碼。</span><span class="sxs-lookup"><span data-stu-id="be52c-161">When this policy is not configured, BitLocker secrets are removed from memory when the computer restarts.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="be52c-162">驗證智慧卡憑證使用規則</span><span class="sxs-lookup"><span data-stu-id="be52c-162">Validate smart card certificate usage rule</span></span></p></td>
<td align="left"><p><span data-ttu-id="be52c-163">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="be52c-163">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="be52c-164">設定此原則以使用以智慧卡憑證為基礎的 BitLocker 保護。</span><span class="sxs-lookup"><span data-stu-id="be52c-164">Configure this policy to use smartcard certificate-based BitLocker protection.</span></span></p>
<p><span data-ttu-id="be52c-165">如果未設定此原則，則會使用預設的物件識別碼1.3.6.1.4.1.311.67.1.1 來指定憑證。</span><span class="sxs-lookup"><span data-stu-id="be52c-165">When this policy is not configured, the default object identifier 1.3.6.1.4.1.311.67.1.1 is used to specify a certificate.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="be52c-166">為您的組織提供唯一識別碼</span><span class="sxs-lookup"><span data-stu-id="be52c-166">Provide the unique identifiers for your organization</span></span></p></td>
<td align="left"><p><span data-ttu-id="be52c-167">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="be52c-167">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="be52c-168">將此原則設定為使用以憑證為基礎的資料復原代理程式或 BitLocker To Go reader。</span><span class="sxs-lookup"><span data-stu-id="be52c-168">Configure this policy to use a certificate-based data recovery agent or the BitLocker To Go reader.</span></span></p>
<p><span data-ttu-id="be52c-169">如果未設定此原則， <strong> </strong> 就不會使用 [識別] 欄位。</span><span class="sxs-lookup"><span data-stu-id="be52c-169">When this policy is not configured, the <strong>Identification</strong> field is not used.</span></span></p>
<p><span data-ttu-id="be52c-170">如果您的公司需要較高的安全性測量，您可以設定 <strong> 識別 </strong> 欄位，以確保所有 USB 裝置都已設定此欄位，並與此群組原則設定對齊。</span><span class="sxs-lookup"><span data-stu-id="be52c-170">If your company requires higher security measurements, you can configure the <strong>Identification</strong> field to make sure that all USB devices have this field set and that they are aligned with this Group Policy setting.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="be52c-171">用戶端管理群組原則定義</span><span class="sxs-lookup"><span data-stu-id="be52c-171">Client Management Group Policy definitions</span></span>

<span data-ttu-id="be52c-172">本節說明 MBAM 在下列 GPO 節點的用戶端管理原則定義：**電腦**設定 &gt; **策略** &gt; **管理範本** &gt; **Windows 元件** &gt; **MDOP MBAM （BitLocker Management）** &gt; **用戶端管理**。</span><span class="sxs-lookup"><span data-stu-id="be52c-172">This section describes Client Management policy definitions for MBAM at the following GPO node: **Computer Configuration** &gt; **Policies** &gt;**Administrative Templates** &gt; **Windows Components** &gt; **MDOP MBAM (BitLocker Management)** &gt; **Client Management**.</span></span>

<span data-ttu-id="be52c-173">您可以針對獨立和系統中心 Configuration Manager 整合拓朴設定相同的群組原則設定，但有一個例外狀況：如果您使用的是 Configuration Manager 整合拓撲，請停用 [設定**MBAM 服務 &gt; MBAM 狀態報表服務端點**] 設定，如下表所示。</span><span class="sxs-lookup"><span data-stu-id="be52c-173">You can set the same Group Policy settings for the Stand-alone and System Center Configuration Manager Integration topologies, with one exception: Disable the **Configure MBAM Services &gt; MBAM Status reporting service endpoint** setting if you are using the Configuration Manager Integration topology, as indicated in the following table.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="be52c-174">原則名稱</span><span class="sxs-lookup"><span data-stu-id="be52c-174">Policy name</span></span></th>
<th align="left"><span data-ttu-id="be52c-175">概覽及建議的群組原則設定</span><span class="sxs-lookup"><span data-stu-id="be52c-175">Overview and suggested Group Policy settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="be52c-176">設定 MBAM 服務</span><span class="sxs-lookup"><span data-stu-id="be52c-176">Configure MBAM Services</span></span></p></td>
<td align="left"><p><span data-ttu-id="be52c-177">建議的設定： <strong> 已啟用</span><span class="sxs-lookup"><span data-stu-id="be52c-177">Suggested configuration: <strong>Enabled</span></span></strong></p>
<ul>
<li><p><strong><span data-ttu-id="be52c-178">MBAM [恢復與硬體服務] 端點 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="be52c-178">MBAM Recovery and Hardware service endpoint</strong>.</span></span> <span data-ttu-id="be52c-179">使用此設定來啟用 MBAM 用戶端 BitLocker 加密管理。</span><span class="sxs-lookup"><span data-stu-id="be52c-179">Use this setting to enable MBAM Client BitLocker encryption management.</span></span> <span data-ttu-id="be52c-180">輸入與下列範例類似的端點位置： <strong> HTTP （s）// </strong><em> &lt; MBAM 管理和監視伺服器名稱 &gt; </em><strong> ： </strong><em> &lt; web 服務系結至/MBAMRecoveryAndHardwareService/CoreService.svc 的埠 &gt; </em><strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="be52c-180">Enter an endpoint location that is similar to the following example: <strong>http(s)://</strong><em>&lt;MBAM Administration and Monitoring Server Name&gt;</em><strong>:</strong><em>&lt;the port the web service is bound to&gt;</em><strong>/MBAMRecoveryAndHardwareService/CoreService.svc</strong>.</span></span></p></li>
<li><p><strong><span data-ttu-id="be52c-181">選取要儲存的 BitLocker 復原資訊 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="be52c-181">Select BitLocker recovery information to store</strong>.</span></span> <span data-ttu-id="be52c-182">此原則設定可讓您設定金鑰復原服務來備份 BitLocker 復原資訊。</span><span class="sxs-lookup"><span data-stu-id="be52c-182">This policy setting lets you configure the key recovery service to back up BitLocker recovery information.</span></span> <span data-ttu-id="be52c-183">您也可以使用它來設定收集報表的狀態報表服務。</span><span class="sxs-lookup"><span data-stu-id="be52c-183">It also lets you configure a status reporting service for collecting reports.</span></span> <span data-ttu-id="be52c-184">原則提供一種系統管理方法，可復原由 BitLocker 加密的資料，避免由於缺少重要資訊而造成資料遺失。</span><span class="sxs-lookup"><span data-stu-id="be52c-184">The policy provides an administrative method of recovering data encrypted by BitLocker to prevent data loss due to the lack of key information.</span></span> <span data-ttu-id="be52c-185">狀態報表和金鑰復原活動會自動及自動傳送到已設定的報表伺服器位置。</span><span class="sxs-lookup"><span data-stu-id="be52c-185">The status report and key recovery activity are automatically and silently sent to the configured report server location.</span></span></p>
<p><span data-ttu-id="be52c-186">如果您未設定或停用此原則設定，就不會儲存金鑰復原資訊，且不會向伺服器報告狀態報表和金鑰復原活動。</span><span class="sxs-lookup"><span data-stu-id="be52c-186">If you do not configure this policy setting or if you disable it, the key recovery information is not saved, and the status report and key recovery activity are not reported to the server.</span></span> <span data-ttu-id="be52c-187">當此設定設定為 [復原 <strong> 密碼及金鑰套件] 時 </strong> ，系統會自動將復原密碼及金鑰套件備份到已設定的金鑰復原伺服器位置。</span><span class="sxs-lookup"><span data-stu-id="be52c-187">When this setting is set to <strong>Recovery Password and key package</strong>, the recovery password and key package are automatically and silently backed up to the configured key recovery server location.</span></span></p></li>
<li><p><strong><span data-ttu-id="be52c-188">輸入用戶端檢查狀態頻率（分鐘） </strong> 。</span><span class="sxs-lookup"><span data-stu-id="be52c-188">Enter client checking status frequency in minutes</strong>.</span></span> <span data-ttu-id="be52c-189">此原則設定會管理用戶端檢查用戶端電腦上的 BitLocker 保護原則和狀態的頻率。</span><span class="sxs-lookup"><span data-stu-id="be52c-189">This policy setting manages how frequently the client checks the BitLocker protection policies and status on the client computer.</span></span> <span data-ttu-id="be52c-190">此原則也會管理將用戶端合規性狀態儲存到伺服器的頻率。</span><span class="sxs-lookup"><span data-stu-id="be52c-190">This policy also manages how frequently the client compliance status is saved to the server.</span></span> <span data-ttu-id="be52c-191">用戶端會檢查用戶端電腦上的 BitLocker 保護原則和狀態，同時也會以設定的頻率來備份用戶端復原金鑰。</span><span class="sxs-lookup"><span data-stu-id="be52c-191">The client checks the BitLocker protection policies and status on the client computer and also backs up the client recovery key at the configured frequency.</span></span></p>
<p><span data-ttu-id="be52c-192">根據貴公司設定的需求來設定此頻率，瞭解如何檢查電腦的合規性狀態，以及備份用戶端復原金鑰的頻率。</span><span class="sxs-lookup"><span data-stu-id="be52c-192">Set this frequency based on the requirement set by your company on how frequently to check the compliance status of the computer and how frequently to back up the client recovery key.</span></span></p></li>
<li><p><strong><span data-ttu-id="be52c-193">MBAM 狀態報表服務端點：</span><span class="sxs-lookup"><span data-stu-id="be52c-193">MBAM Status reporting service endpoint:</span></span></strong></p>
<p><strong><span data-ttu-id="be52c-194">針對獨立拓朴中的 MBAM </strong> ：您必須設定此設定，才能啟用 MBAM 用戶端 BitLocker 加密管理。</span><span class="sxs-lookup"><span data-stu-id="be52c-194">For MBAM in a Stand-alone topology</strong>: You must configure this setting to enable MBAM Client BitLocker encryption management.</span></span></p>
<p><span data-ttu-id="be52c-195">輸入與下列範例類似的端點位置：</span><span class="sxs-lookup"><span data-stu-id="be52c-195">Enter an endpoint location that is similar to the following example:</span></span></p>
<p><strong><span data-ttu-id="be52c-196">HTTP （s）// </strong><em> &lt; MBAM 管理和監視伺服器名稱 &gt; </em><strong> ： </strong><em> &lt; web 服務系結到/MBAMComplianceStatusService/StatusReportingService.svc 的埠 &gt; </em><strong></span><span class="sxs-lookup"><span data-stu-id="be52c-196">http(s)://</strong><em>&lt;MBAM Administration and Monitoring Server Name&gt;</em><strong>:</strong><em>&lt;the port the web service is bound to&gt;</em><strong>/MBAMComplianceStatusService/StatusReportingService.svc</span></span></strong></p>
<p><strong><span data-ttu-id="be52c-197">針對 Configuration Manager 整合拓撲中的 MBAM </strong> ：停用此設定。</span><span class="sxs-lookup"><span data-stu-id="be52c-197">For MBAM in the Configuration Manager Integration topology</strong>: Disable this setting.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="be52c-198">設定使用者豁免原則</span><span class="sxs-lookup"><span data-stu-id="be52c-198">Configure user exemption policy</span></span></p></td>
<td align="left"><p><span data-ttu-id="be52c-199">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="be52c-199">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="be52c-200">此原則設定可讓您設定網站位址、電子郵件地址或電話號碼，以指示使用者從 BitLocker 加密要求例外。</span><span class="sxs-lookup"><span data-stu-id="be52c-200">This policy setting lets you configure a website address, email address, or phone number that instructs a user to request an exemption from BitLocker encryption.</span></span></p>
<p><span data-ttu-id="be52c-201">如果您啟用此原則設定並提供網站位址、電子郵件地址或電話號碼，使用者會看到一個對話方塊，其中包含如何針對 BitLocker 保護申請免除的指示。</span><span class="sxs-lookup"><span data-stu-id="be52c-201">If you enable this policy setting and provide a website address, email address, or phone number, users see a dialog box with instructions on how to apply for an exemption from BitLocker protection.</span></span> <span data-ttu-id="be52c-202">如需針對使用者啟用 BitLocker 加密免除的詳細資訊，請參閱 <a href="how-to-manage-user-bitlocker-encryption-exemptions-mbam-25.md" data-raw-source="[How to Manage User BitLocker Encryption Exemptions](how-to-manage-user-bitlocker-encryption-exemptions-mbam-25.md)"> 如何管理使用者 Bitlocker 加密免除 </a> 。</span><span class="sxs-lookup"><span data-stu-id="be52c-202">For more information about enabling BitLocker encryption exemptions for users, see <a href="how-to-manage-user-bitlocker-encryption-exemptions-mbam-25.md" data-raw-source="[How to Manage User BitLocker Encryption Exemptions](how-to-manage-user-bitlocker-encryption-exemptions-mbam-25.md)">How to Manage User BitLocker Encryption Exemptions</a>.</span></span></p>
<p><span data-ttu-id="be52c-203">如果您停用或不設定此原則設定，就不會向使用者顯示免除要求指示。</span><span class="sxs-lookup"><span data-stu-id="be52c-203">If you either disable or do not configure this policy setting, the exemption request instructions are not displayed to users.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="be52c-204">注意</span><span class="sxs-lookup"><span data-stu-id="be52c-204">Note</span></span></strong><br/><p><span data-ttu-id="be52c-205">使用者豁免是針對每個使用者管理，而不是針對每個電腦。</span><span class="sxs-lookup"><span data-stu-id="be52c-205">User exemption is managed per user, not per computer.</span></span> <span data-ttu-id="be52c-206">如果有多個使用者登入同一部電腦，且任何一位使用者都沒有免除，電腦就會經過加密。</span><span class="sxs-lookup"><span data-stu-id="be52c-206">If multiple users log on to the same computer and any one user is not exempt, the computer is encrypted.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="be52c-207">設定客戶經驗改進計畫</span><span class="sxs-lookup"><span data-stu-id="be52c-207">Configure customer experience improvement program</span></span></p></td>
<td align="left"><p><span data-ttu-id="be52c-208">建議的設定： <strong> 已啟用</span><span class="sxs-lookup"><span data-stu-id="be52c-208">Suggested configuration: <strong>Enabled</span></span></strong></p>
<p><span data-ttu-id="be52c-209">此原則設定可讓您設定 MBAM 使用者如何加入客戶經驗改進計畫。</span><span class="sxs-lookup"><span data-stu-id="be52c-209">This policy setting lets you configure how MBAM users can join the Customer Experience Improvement Program.</span></span> <span data-ttu-id="be52c-210">這個程式會收集電腦硬體的相關資訊，以及使用者如何使用 MBAM，而不會中斷他們的工作。</span><span class="sxs-lookup"><span data-stu-id="be52c-210">This program collects information about computer hardware and how users use MBAM without interrupting their work.</span></span> <span data-ttu-id="be52c-211">此資訊可協助 Microsoft 識別要改善的 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="be52c-211">The information helps Microsoft to identify which MBAM features to improve.</span></span> <span data-ttu-id="be52c-212">Microsoft 不會使用這種資訊來識別或與 MBAM 使用者。</span><span class="sxs-lookup"><span data-stu-id="be52c-212">Microsoft does not use this information to identify or contact MBAM users.</span></span></p>
<p><span data-ttu-id="be52c-213">如果您啟用此原則設定，使用者可以加入客戶經驗改進計畫。</span><span class="sxs-lookup"><span data-stu-id="be52c-213">If you enable this policy setting, users can join the Customer Experience Improvement Program.</span></span></p>
<p><span data-ttu-id="be52c-214">如果您停用此原則設定，使用者就無法加入客戶經驗改進計畫。</span><span class="sxs-lookup"><span data-stu-id="be52c-214">If you disable this policy setting, users cannot join the Customer Experience Improvement Program.</span></span></p>
<p><span data-ttu-id="be52c-215">如果您未設定此原則設定，使用者可以加入宣告客戶經驗改進計畫。</span><span class="sxs-lookup"><span data-stu-id="be52c-215">If you do not configure this policy setting, users have the option to join the Customer Experience Improvement Program.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="be52c-216">提供安全性原則連結的 URL</span><span class="sxs-lookup"><span data-stu-id="be52c-216">Provide the URL for the Security Policy link</span></span></p></td>
<td align="left"><p><span data-ttu-id="be52c-217">建議的設定： <strong> 已啟用</span><span class="sxs-lookup"><span data-stu-id="be52c-217">Suggested configuration: <strong>Enabled</span></span></strong></p>
<p><span data-ttu-id="be52c-218">使用此原則設定，指定顯示給最終使用者的 URL，作為名稱為 [ &quot; 公司安全性原則] 的連結。 &quot;連結指向您公司的內部安全性原則，並為使用者提供加密需求的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="be52c-218">Use this policy setting to specify a URL that is displayed to end users as a link named &quot;Company Security Policy.&quot; The link points to your company’s internal security policy and provides end users with information about encryption requirements.</span></span> <span data-ttu-id="be52c-219">當 MBAM 提示使用者加密磁片磁碟機時，就會出現該連結。</span><span class="sxs-lookup"><span data-stu-id="be52c-219">The link appears when users are prompted by MBAM to encrypt a drive.</span></span></p>
<p><span data-ttu-id="be52c-220">如果您啟用此原則設定，您可以設定安全性原則連結的 URL。</span><span class="sxs-lookup"><span data-stu-id="be52c-220">If you enable this policy setting, you can configure the URL for the Security Policy link.</span></span></p>
<p><span data-ttu-id="be52c-221">如果您停用或不設定此原則設定，就不會向使用者顯示 [安全性原則] 連結。</span><span class="sxs-lookup"><span data-stu-id="be52c-221">If you disable or do not configure this policy setting, the Security Policy link is not displayed to users.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="be52c-222">固定磁片磁碟機群組原則定義</span><span class="sxs-lookup"><span data-stu-id="be52c-222">Fixed Drive Group Policy definitions</span></span>

<span data-ttu-id="be52c-223">本節說明在下列 GPO 節點上進行 Microsoft BitLocker 管理和監視的固定磁片磁碟機策略定義：**電腦**設定 &gt; **策略**系統 &gt; **管理範本** &gt; **Windows 元件** &gt; **MDOP MBAM （BitLocker Management）** 已固定的 &gt; **磁片磁碟機**。</span><span class="sxs-lookup"><span data-stu-id="be52c-223">This section describes Fixed Drive policy definitions for Microsoft BitLocker Administration and Monitoring at the following GPO node: **Computer Configuration** &gt; **Policies** &gt; **Administrative Templates** &gt; **Windows Components** &gt; **MDOP MBAM (BitLocker Management)** &gt; **Fixed Drive**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="be52c-224">原則名稱</span><span class="sxs-lookup"><span data-stu-id="be52c-224">Policy name</span></span></th>
<th align="left"><span data-ttu-id="be52c-225">概覽及建議的群組原則設定</span><span class="sxs-lookup"><span data-stu-id="be52c-225">Overview and suggested Group Policy settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="be52c-226">固定資料磁片磁碟機加密設定</span><span class="sxs-lookup"><span data-stu-id="be52c-226">Fixed data drive encryption settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="be52c-227">建議的設定： <strong> 已啟用</span><span class="sxs-lookup"><span data-stu-id="be52c-227">Suggested configuration: <strong>Enabled</span></span></strong></p>
<p><span data-ttu-id="be52c-228">此原則設定可讓您管理固定資料磁碟機是否必須加密。</span><span class="sxs-lookup"><span data-stu-id="be52c-228">This policy setting lets you manage whether fixed data drives must be encrypted.</span></span></p>
<p><span data-ttu-id="be52c-229">如果需要加密作業系統卷，請按一下 [ <strong> 啟用自動解鎖固定資料磁碟機] </strong> 。</span><span class="sxs-lookup"><span data-stu-id="be52c-229">If the operating system volume is required to be encrypted, click <strong>Enable auto-unlock fixed data drive</strong>.</span></span></p>
<p><span data-ttu-id="be52c-230">當您啟用此原則時， <strong> </strong> 除非您要啟用或要求對固定資料磁碟機使用自動解鎖，否則您不能停用 [設定固定資料磁碟機使用密碼] 原則。</span><span class="sxs-lookup"><span data-stu-id="be52c-230">When you enable this policy, you must not disable the <strong>Configure use of password for fixed data drives</strong> policy unless you are enabling or requiring the use of auto-unlock for fixed data drives.</span></span></p>
<p><span data-ttu-id="be52c-231">如果您必須針對固定資料磁碟機使用自動解鎖，您必須設定要加密的作業系統卷。</span><span class="sxs-lookup"><span data-stu-id="be52c-231">If you have to use auto-unlock for fixed data drives, you must configure operating system volumes to be encrypted.</span></span></p>
<p><span data-ttu-id="be52c-232">如果您啟用此原則設定，使用者必須將所有固定資料磁碟機放在 BitLocker 保護之下，然後再加密資料磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="be52c-232">If you enable this policy setting, users are required to put all fixed data drives under BitLocker protection, and the data drives are then encrypted.</span></span></p>
<p><span data-ttu-id="be52c-233">如果您未設定此原則設定，則不需要使用者將固定的資料磁碟機放在 BitLocker 保護之下。</span><span class="sxs-lookup"><span data-stu-id="be52c-233">If you do not configure this policy setting, users are not required to put fixed data drives under BitLocker protection.</span></span> <span data-ttu-id="be52c-234">如果您在已加密固定資料磁碟機之後套用此原則，則 MBAM agent 會將加密的固定資料磁碟機解密。</span><span class="sxs-lookup"><span data-stu-id="be52c-234">If you apply this policy after fixed data drives are encrypted, the MBAM agent decrypts the encrypted fixed data drives.</span></span></p>
<p><span data-ttu-id="be52c-235">如果您停用此原則設定，使用者就無法將其固定資料磁碟機放在 BitLocker 保護底下。</span><span class="sxs-lookup"><span data-stu-id="be52c-235">If you disable this policy setting, users cannot put their fixed data drives under BitLocker protection.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="be52c-236">拒絕寫入存取不受 BitLocker 保護的固定式磁碟機</span><span class="sxs-lookup"><span data-stu-id="be52c-236">Deny write access to fixed drives not protected by BitLocker</span></span></p></td>
<td align="left"><p><span data-ttu-id="be52c-237">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="be52c-237">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="be52c-238">此原則設定決定固定資料磁碟機是否需要 BitLocker 保護，才能在電腦上寫入。</span><span class="sxs-lookup"><span data-stu-id="be52c-238">This policy setting determines whether BitLocker protection is required for fixed data drives to be writable on a computer.</span></span> <span data-ttu-id="be52c-239">當您開啟 BitLocker 時，就會套用此原則設定。</span><span class="sxs-lookup"><span data-stu-id="be52c-239">This policy setting is applied when you turn on BitLocker.</span></span></p>
<p><span data-ttu-id="be52c-240">如果未設定原則，電腦上所有的固定資料磁碟機都會以讀取/寫入權限掛載。</span><span class="sxs-lookup"><span data-stu-id="be52c-240">When the policy is not configured, all fixed data drives on the computer are mounted with read/write permission.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="be52c-241">允許從較舊版本的 Windows 存取受 BitLocker 保護的固定磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="be52c-241">Allow access to BitLocker-protected fixed drives from earlier versions of Windows</span></span></p></td>
<td align="left"><p><span data-ttu-id="be52c-242">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="be52c-242">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="be52c-243">啟用此原則，以便在執行 Windows Server 2008、Windows Vista、windows XP （含 SP3）或 Windows XP 的電腦上，解除鎖定與 FAT 檔案系統的固定磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="be52c-243">Enable this policy so that fixed drives with the FAT file system can be unlocked and viewed on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2.</span></span></p>
<p><span data-ttu-id="be52c-244">如果已啟用或未設定原則，就可以在執行 Windows Server 2008、Windows Vista、windows XP （含 SP3）或 Windows XP 的電腦上，解除鎖定以 FAT 檔案系統格式化的固定磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="be52c-244">When the policy is enabled or not configured, fixed drives that are formatted with the FAT file system can be unlocked and their content can be viewed on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2.</span></span> <span data-ttu-id="be52c-245">這些作業系統擁有受 BitLocker 保護的磁片磁碟機的唯讀許可權。</span><span class="sxs-lookup"><span data-stu-id="be52c-245">These operating systems have read-only permission to BitLocker-protected drives.</span></span></p>
<p><span data-ttu-id="be52c-246">當原則停用時，使用 FAT 檔案系統格式化的固定磁片磁碟機將無法解除鎖定，而且無法在執行 Windows Server 2008、Windows Vista、Windows XP （含 SP3）的電腦上，或使用 SP2 的 Windows XP 中查看其內容。</span><span class="sxs-lookup"><span data-stu-id="be52c-246">When the policy is disabled, fixed drives that are formatted with the FAT file system cannot be unlocked and their content cannot be viewed on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="be52c-247">設定在固定磁片磁碟機使用密碼</span><span class="sxs-lookup"><span data-stu-id="be52c-247">Configure use of password for fixed drives</span></span></p></td>
<td align="left"><p><span data-ttu-id="be52c-248">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="be52c-248">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="be52c-249">使用此原則來指定是否需要密碼來解除鎖定受 BitLocker 保護的固定資料磁碟機。</span><span class="sxs-lookup"><span data-stu-id="be52c-249">Use this policy to specify whether a password is required to unlock BitLocker-protected fixed data drives.</span></span></p>
<p><span data-ttu-id="be52c-250">如果您啟用此原則設定，使用者可以設定符合您所定義需求的密碼。</span><span class="sxs-lookup"><span data-stu-id="be52c-250">If you enable this policy setting, users can configure a password that meets the requirements that you define.</span></span> <span data-ttu-id="be52c-251">BitLocker 可讓使用者以磁片磁碟機上可用的任何保護器解除鎖定磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="be52c-251">BitLocker enables users to unlock a drive with any of the protectors that are available on the drive.</span></span></p>
<p><span data-ttu-id="be52c-252">當您開啟 BitLocker，而不是當您解除鎖定時，就會強制執行這些設定。</span><span class="sxs-lookup"><span data-stu-id="be52c-252">These settings are enforced when you turn on BitLocker, not when you unlock a volume.</span></span></p>
<p><span data-ttu-id="be52c-253">如果您停用此原則設定，就不允許使用者使用密碼。</span><span class="sxs-lookup"><span data-stu-id="be52c-253">If you disable this policy setting, users are not allowed to use a password.</span></span></p>
<p><span data-ttu-id="be52c-254">如果未設定原則，預設設定就會支援密碼，這不會包含密碼複雜性需求，且只需要八個字元。</span><span class="sxs-lookup"><span data-stu-id="be52c-254">When the policy is not configured, passwords are supported with the default settings, which do not include password complexity requirements and which require only eight characters.</span></span></p>
<p><span data-ttu-id="be52c-255">若要獲得較高的安全性，請啟用此原則，然後選取 [ <strong> 針對固定資料磁碟機需要密碼] </strong> ，按一下 <strong> [需要密碼複雜性] </strong> ，然後設定 <strong> </strong> 您想要的最小密碼長度。</span><span class="sxs-lookup"><span data-stu-id="be52c-255">For higher security, enable this policy, and then select <strong>Require password for fixed data drive</strong>, click <strong>Require password complexity</strong>, and set the <strong>minimum password length</strong> that you want.</span></span></p>
<p><span data-ttu-id="be52c-256">如果您停用此原則設定，就不允許使用者使用密碼。</span><span class="sxs-lookup"><span data-stu-id="be52c-256">If you disable this policy setting, users are not allowed to use a password.</span></span></p>
<p><span data-ttu-id="be52c-257">如果您未設定此原則設定，則會支援密碼（預設設定），不包含密碼複雜性需求，且只需要八個字元。</span><span class="sxs-lookup"><span data-stu-id="be52c-257">If you do not configure this policy setting, passwords are supported with the default settings, which do not include password complexity requirements and which require only eight characters.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="be52c-258">選擇如何復原受 BitLocker 保護的固定磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="be52c-258">Choose how BitLocker-protected fixed drives can be recovered</span></span></p></td>
<td align="left"><p><span data-ttu-id="be52c-259">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="be52c-259">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="be52c-260">設定此原則以啟用 BitLocker 資料復原代理程式，或將 BitLocker 復原資訊儲存至 Active Directory 網域服務（AD DS）。</span><span class="sxs-lookup"><span data-stu-id="be52c-260">Configure this policy to enable the BitLocker data recovery agent or to save BitLocker recovery information to Active Directory Domain Services (AD DS).</span></span></p>
<p><span data-ttu-id="be52c-261">如果未設定原則，就會允許 BitLocker 資料復原代理程式，且不會將復原資訊備份到 AD DS。</span><span class="sxs-lookup"><span data-stu-id="be52c-261">When the policy is not configured, the BitLocker data recovery agent is allowed, and recovery information is not backed up to AD DS.</span></span> <span data-ttu-id="be52c-262">MBAM 不需要將復原資訊備份到 AD DS。</span><span class="sxs-lookup"><span data-stu-id="be52c-262">MBAM does not require recovery information to be backed up to AD DS.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="be52c-263">加密原則強制設定</span><span class="sxs-lookup"><span data-stu-id="be52c-263">Encryption Policy Enforcement Settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="be52c-264">建議的設定： <strong> 已啟用</span><span class="sxs-lookup"><span data-stu-id="be52c-264">Suggested configuration: <strong>Enabled</span></span></strong></p>
<p><span data-ttu-id="be52c-265">使用此原則設定來設定固定資料磁碟機可保持不相容的天數，直到強制符合 MBAM 原則為止。</span><span class="sxs-lookup"><span data-stu-id="be52c-265">Use this policy setting to configure the number of days that fixed data drives can remain noncompliant until they are forced to comply with MBAM policies.</span></span> <span data-ttu-id="be52c-266">使用者在寬限期之後，不能推遲所需的動作，也不能要求其例外狀況。</span><span class="sxs-lookup"><span data-stu-id="be52c-266">Users cannot postpone the required action or request an exemption from it after the grace period.</span></span> <span data-ttu-id="be52c-267">當固定資料磁碟機被認為不相容時，寬限期就會開始。</span><span class="sxs-lookup"><span data-stu-id="be52c-267">The grace period starts when the fixed data drive is determined to be noncompliant.</span></span> <span data-ttu-id="be52c-268">不過，除非操作系統磁碟機符合規範，否則系統不會強制執行固定資料磁碟機原則。</span><span class="sxs-lookup"><span data-stu-id="be52c-268">However, the fixed data drive policy is not enforced until the operating system drive is compliant.</span></span></p>
<p><span data-ttu-id="be52c-269">如果寬限期已到期，且固定資料磁碟機仍不合規，則使用者不能選擇推遲或要求免除。</span><span class="sxs-lookup"><span data-stu-id="be52c-269">If the grace period expires and the fixed data drive is still not compliant, users do not have the option to postpone or to request an exemption.</span></span> <span data-ttu-id="be52c-270">如果加密程式需要使用者輸入，則會顯示一個對話方塊，讓使用者無法關閉，直到它們提供所需的資訊為止。</span><span class="sxs-lookup"><span data-stu-id="be52c-270">If the encryption process requires user input, a dialog box appears that users cannot close until they provide the required information.</span></span></p>
<p><span data-ttu-id="be52c-271"><strong> </strong> 在 [設定固定磁碟機的不符合寬限期天數] 中輸入0， <strong> </strong> 即可強制在作業系統磁片磁碟機的寬限期到期後立即開始加密程式。</span><span class="sxs-lookup"><span data-stu-id="be52c-271">Enter <strong>0</strong> in the <strong>Configure the number of noncompliance grace period days for fixed drives</strong> to force the encryption process to begin immediately after the grace period expires for the operating system drive.</span></span></p>
<p><span data-ttu-id="be52c-272">如果您停用或不設定此設定，使用者就不會強制遵守 MBAM 原則。</span><span class="sxs-lookup"><span data-stu-id="be52c-272">If you disable or do not configure this setting, users are not forced to comply with MBAM policies.</span></span></p>
<p><span data-ttu-id="be52c-273">如果不需要使用者互動，即可新增保護器，則在寬限期到期之後，就會在背景中開始加密。</span><span class="sxs-lookup"><span data-stu-id="be52c-273">If no user interaction is required to add a protector, encryption begins in the background after the grace period expires.</span></span></p></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="be52c-274">作業系統磁片磁碟機群組原則定義</span><span class="sxs-lookup"><span data-stu-id="be52c-274">Operating System Drive Group Policy definitions</span></span>

<span data-ttu-id="be52c-275">本節說明 Microsoft BitLocker 在下列 GPO 節點上進行管理和監控的作業系統磁片磁碟機原則定義：**電腦**設定 &gt; **策略** &gt; **管理範本** &gt; **Windows 元件** &gt; **MDOP MBAM （BitLocker Management）** &gt; **作業系統磁片磁碟機**。</span><span class="sxs-lookup"><span data-stu-id="be52c-275">This section describes Operating System Drive policy definitions for Microsoft BitLocker Administration and Monitoring at the following GPO node: **Computer Configuration** &gt; **Policies** &gt; **Administrative Templates** &gt; **Windows Components** &gt; **MDOP MBAM (BitLocker Management)** &gt; **Operating System Drive**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="be52c-276">原則名稱</span><span class="sxs-lookup"><span data-stu-id="be52c-276">Policy name</span></span></th>
<th align="left"><span data-ttu-id="be52c-277">概覽及建議的群組原則設定</span><span class="sxs-lookup"><span data-stu-id="be52c-277">Overview and suggested Group Policy settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="be52c-278">作業系統磁片磁碟機加密設定</span><span class="sxs-lookup"><span data-stu-id="be52c-278">Operating system drive encryption settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="be52c-279">建議的設定： <strong> 已啟用</span><span class="sxs-lookup"><span data-stu-id="be52c-279">Suggested configuration: <strong>Enabled</span></span></strong></p>
<p><span data-ttu-id="be52c-280">此原則設定可讓您管理作業系統磁片磁碟機是否必須經過加密。</span><span class="sxs-lookup"><span data-stu-id="be52c-280">This policy setting lets you manage whether the operating system drive must be encrypted.</span></span></p>
<p><span data-ttu-id="be52c-281">若要獲得較高的安全性，請考慮在 <strong> </strong> &gt; <strong> </strong> &gt; <strong> </strong> 使用 TPM + PIN 保護器啟用系統電源管理睡眠設定時停用下列原則設定：</span><span class="sxs-lookup"><span data-stu-id="be52c-281">For higher security, consider disabling the following policy settings in <strong>System</strong> &gt; <strong>Power Management</strong> &gt; <strong>Sleep Settings</strong> when you enable them with TPM + PIN protector:</span></span></p>
<ul>
<li><p><span data-ttu-id="be52c-282">在休眠（電源開啟）時允許待機狀態（S1-S3）</span><span class="sxs-lookup"><span data-stu-id="be52c-282">Allow Standby States (S1-S3) When Sleeping (Plugged In)</span></span></p></li>
<li><p><span data-ttu-id="be52c-283">在睡眠時允許待機狀態（S1-S3）（使用電池）</span><span class="sxs-lookup"><span data-stu-id="be52c-283">Allow Standby States (S1-S3) When Sleeping (On Battery)</span></span></p></li>
</ul>
<p><span data-ttu-id="be52c-284">如果您執行的是 Microsoft Windows 8 或更新版本，而您想要在沒有 TPM 的電腦上使用 BitLocker，請選取 [ <strong> 允許沒有相容的 tpm 的 bitlocker] </strong> 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="be52c-284">If you are running Microsoft Windows 8 or later, and you want to use BitLocker on a computer without a TPM, select the <strong>Allow BitLocker without a compatible TPM</strong> check box.</span></span> <span data-ttu-id="be52c-285">在此模式中，啟動需要密碼。</span><span class="sxs-lookup"><span data-stu-id="be52c-285">In this mode, a password is required for startup.</span></span> <span data-ttu-id="be52c-286">如果您忘記密碼，您必須使用其中一個 BitLocker 復原選項來存取磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="be52c-286">If you forget the password, you have to use one of the BitLocker recovery options to access the drive.</span></span></p>
<p><span data-ttu-id="be52c-287">在有相容的 TPM 的電腦上，啟動時可以使用兩種類型的驗證方法，為加密資料提供額外的保護。</span><span class="sxs-lookup"><span data-stu-id="be52c-287">On a computer with a compatible TPM, two types of authentication methods can be used at startup to provide added protection for encrypted data.</span></span> <span data-ttu-id="be52c-288">電腦啟動時，只能使用 TPM 進行驗證，或者也可能需要輸入個人識別碼（PIN）。</span><span class="sxs-lookup"><span data-stu-id="be52c-288">When the computer starts, it can use only the TPM for authentication, or it can also require the entry of a personal identification number (PIN).</span></span></p>
<p><span data-ttu-id="be52c-289">如果您啟用此原則設定，使用者必須將操作系統磁碟機放在 BitLocker 保護之下，然後再加密磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="be52c-289">If you enable this policy setting, users have to put the operating system drive under BitLocker protection, and the drive is then encrypted.</span></span></p>
<p><span data-ttu-id="be52c-290">如果您停用這個原則，使用者就無法將操作系統磁碟機放在 BitLocker 保護下。</span><span class="sxs-lookup"><span data-stu-id="be52c-290">If you disable this policy, users cannot put the operating system drive under BitLocker protection.</span></span> <span data-ttu-id="be52c-291">如果您在作業系統磁片磁碟機經過加密之後套用此原則，就會解密磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="be52c-291">If you apply this policy after the operating system drive is encrypted, the drive is then decrypted.</span></span></p>
<p><span data-ttu-id="be52c-292">如果您未設定此原則，則不需要在 BitLocker 保護下放置作業系統磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="be52c-292">If you do not configure this policy, the operating system drive is not required to be placed under BitLocker protection.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="be52c-293">允許增強的 Pin 以進行啟動</span><span class="sxs-lookup"><span data-stu-id="be52c-293">Allow enhanced PINs for startup</span></span></p></td>
<td align="left"><p><span data-ttu-id="be52c-294">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="be52c-294">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="be52c-295">使用此原則設定來設定是否與 BitLocker 搭配使用增強的啟動 Pin。</span><span class="sxs-lookup"><span data-stu-id="be52c-295">Use this policy setting to configure whether enhanced startup PINs are used with BitLocker.</span></span> <span data-ttu-id="be52c-296">增強的啟動 Pin 允許使用字元，包括大寫及小寫字母、符號、數位和空格。</span><span class="sxs-lookup"><span data-stu-id="be52c-296">Enhanced startup PINs permit the use of characters including uppercase and lowercase letters, symbols, numbers, and spaces.</span></span> <span data-ttu-id="be52c-297">當您開啟 BitLocker 時，就會套用此原則設定。</span><span class="sxs-lookup"><span data-stu-id="be52c-297">This policy setting is applied when you turn on BitLocker.</span></span></p>
<p><span data-ttu-id="be52c-298">如果您啟用此原則設定，所有新的 BitLocker 啟動 Pin 設定將會讓使用者能夠建立增強的 Pin。</span><span class="sxs-lookup"><span data-stu-id="be52c-298">If you enable this policy setting, all new BitLocker startup PINs set will enable end user to create enhanced PINs.</span></span> <span data-ttu-id="be52c-299">不過，並非所有電腦都能在預先引導環境中支援增強的 Pin。</span><span class="sxs-lookup"><span data-stu-id="be52c-299">However, not all computers can support enhanced PINs in the pre-boot environment.</span></span> <span data-ttu-id="be52c-300">我們強烈建議管理員先評估其系統是否與此功能相容，才能啟用其使用。</span><span class="sxs-lookup"><span data-stu-id="be52c-300">We strongly recommend that administrators evaluate whether their systems are compatible with this feature before enabling its use.</span></span></p>
<p><span data-ttu-id="be52c-301">選取 [ <strong> 需要 ASCII 專用 pin] </strong> 核取方塊，以協助將增強的 pin 與限制可在預先啟動環境中輸入之字元類型或字元數的電腦相容。</span><span class="sxs-lookup"><span data-stu-id="be52c-301">Select the <strong>Require ASCII-only PINs</strong> check box to help make enhanced PINs more compatible with computers that limit the type or number of characters that can be entered in the pre-boot environment.</span></span></p>
<p><span data-ttu-id="be52c-302">如果您停用或不設定此原則設定，就不會使用增強的 Pin。</span><span class="sxs-lookup"><span data-stu-id="be52c-302">If you disable or do not configure this policy setting, enhanced PINs are not used.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="be52c-303">選擇可如何復原受 BitLocker 保護的操作系統磁碟機</span><span class="sxs-lookup"><span data-stu-id="be52c-303">Choose how BitLocker-protected operating system drives can be recovered</span></span></p></td>
<td align="left"><p><span data-ttu-id="be52c-304">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="be52c-304">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="be52c-305">設定此原則以啟用 BitLocker 資料復原代理程式，或將 BitLocker 復原資訊儲存至 Active Directory 網域服務（AD DS）。</span><span class="sxs-lookup"><span data-stu-id="be52c-305">Configure this policy to enable the BitLocker data recovery agent or to save BitLocker recovery information to Active Directory Domain Services (AD DS).</span></span></p>
<p><span data-ttu-id="be52c-306">如果未設定此原則，就可以使用資料復原代理程式，且不會將復原資訊備份到 AD DS。</span><span class="sxs-lookup"><span data-stu-id="be52c-306">When this policy is not configured, the data recovery agent is allowed, and recovery information is not backed up to AD DS.</span></span></p>
<p><span data-ttu-id="be52c-307">MBAM 操作不需要將復原資訊備份到 AD DS。</span><span class="sxs-lookup"><span data-stu-id="be52c-307">MBAM operation does not require recovery information to be backed up to AD DS.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="be52c-308">設定作業系統磁片磁碟機的密碼使用</span><span class="sxs-lookup"><span data-stu-id="be52c-308">Configure use of passwords for operating system drives</span></span></p></td>
<td align="left"><p><span data-ttu-id="be52c-309">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="be52c-309">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="be52c-310">使用此原則設定來設定用來解除鎖定受 BitLocker 保護之作業系統磁片磁碟機之密碼的限制。</span><span class="sxs-lookup"><span data-stu-id="be52c-310">Use this policy setting to set the constraints for passwords that are used to unlock BitLocker-protected operating system drives.</span></span> <span data-ttu-id="be52c-311">如果在作業系統磁片磁碟機上允許非 TPM 保護器，您可以為密碼設定密碼、強制執行複雜性需求，以及設定密碼的最小長度。</span><span class="sxs-lookup"><span data-stu-id="be52c-311">If non-TPM protectors are allowed on operating system drives, you can provision a password, enforce complexity requirements on the password, and configure a minimum length for the password.</span></span> <span data-ttu-id="be52c-312">為了使複雜性需求設定生效，您也必須啟用 [電腦設定] 中的 [群組原則設定 &quot; 密碼必須符合複雜性需求] （ &quot; 位於 [電腦設定] 中的 [ &gt; 設定 &gt; 安全設定] &gt; 帳戶原則 &gt; 密碼原則中）。</span><span class="sxs-lookup"><span data-stu-id="be52c-312">For the complexity requirement setting to be effective, you must also enable the Group Policy setting &quot;Password must meet complexity requirements&quot; located in Computer Configuration &gt; Windows Settings &gt; Security Settings &gt; Account Policies &gt; Password Policy.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="be52c-313">注意</span><span class="sxs-lookup"><span data-stu-id="be52c-313">Note</span></span></strong><br/><p><span data-ttu-id="be52c-314">當您開啟 BitLocker，而不是當您解除鎖定時，就會強制執行這些設定。</span><span class="sxs-lookup"><span data-stu-id="be52c-314">These settings are enforced when you turn on BitLocker, not when you unlock a volume.</span></span> <span data-ttu-id="be52c-315">BitLocker 可讓您使用磁片磁碟機上可用的任何保護器解除鎖定磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="be52c-315">BitLocker lets you unlock a drive with any of the protectors that are available on the drive.</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="be52c-316">如果您啟用此原則設定，使用者可以設定符合您所定義需求的密碼。</span><span class="sxs-lookup"><span data-stu-id="be52c-316">If you enable this policy setting, users can configure a password that meets the requirements that you define.</span></span> <span data-ttu-id="be52c-317">若要強制密碼的複雜性需求，按一下 [ <strong> 需要密碼複雜性] </strong> 。</span><span class="sxs-lookup"><span data-stu-id="be52c-317">To enforce complexity requirements on the password, click <strong>Require password complexity</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="be52c-318">針對 BIOS 式固件配置設定 TPM 平臺驗證設定檔</span><span class="sxs-lookup"><span data-stu-id="be52c-318">Configure TPM platform validation profile for BIOS-based firmware configurations</span></span></p></td>
<td align="left"><p><span data-ttu-id="be52c-319">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="be52c-319">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="be52c-320">此原則設定可讓您設定電腦&#39;s 受信任的平臺模組（TPM）安全性硬體保護 BitLocker 加密金鑰的方式。</span><span class="sxs-lookup"><span data-stu-id="be52c-320">This policy setting allows you to configure how the computer&#39;s Trusted Platform Module (TPM) security hardware secures the BitLocker encryption key.</span></span> <span data-ttu-id="be52c-321">如果電腦沒有相容的 TPM，或已使用 TPM 保護開啟 BitLocker，此原則設定就不適用。</span><span class="sxs-lookup"><span data-stu-id="be52c-321">This policy setting does not apply if the computer does not have a compatible TPM or if BitLocker has already been turned on with TPM protection.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="be52c-322">重要</span><span class="sxs-lookup"><span data-stu-id="be52c-322">Important</span></span></strong><br/><p><span data-ttu-id="be52c-323">這個群組原則設定僅適用于具備 BIOS 設定的電腦，或使用啟用相容性服務模組（CSM）的具備 UEFI 固件的電腦。</span><span class="sxs-lookup"><span data-stu-id="be52c-323">This Group Policy setting applies only to computers with BIOS configurations or to computers with UEFI firmware with a Compatibility Service Module (CSM) enabled.</span></span> <span data-ttu-id="be52c-324">使用原生 UEFI 固件配置的電腦會將不同的值儲存在平臺設定寄存器（PCRs）中。</span><span class="sxs-lookup"><span data-stu-id="be52c-324">Computers that use a native UEFI firmware configuration store different values into the Platform Configuration Registers (PCRs).</span></span> <span data-ttu-id="be52c-325">使用 [ &quot; 設定適用于原生 uefi 固件配置的 tpm 平臺驗證設定檔] &quot; 群群組原則設定，以設定適用于使用原生 UEFI 固件之電腦的 tpm PCR 設定檔。</span><span class="sxs-lookup"><span data-stu-id="be52c-325">Use the &quot;Configure TPM platform validation profile for native UEFI firmware configurations&quot; Group Policy setting to configure the TPM PCR profile for computers that use native UEFI firmware.</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="be52c-326">如果您在開啟 BitLocker 之前啟用此原則設定，您可以先設定 TPM 驗證的啟動元件，才能解除鎖定 BitLocker 加密操作系統磁碟機的存取權。</span><span class="sxs-lookup"><span data-stu-id="be52c-326">If you enable this policy setting before you turn on BitLocker, you can configure the boot components that the TPM validates before you unlock access to the BitLocker-encrypted operating system drive.</span></span> <span data-ttu-id="be52c-327">如果在 BitLocker 保護生效時，有任何元件變更，則 TPM 不會放開加密金鑰來解除鎖定磁片磁碟機，電腦則改為顯示 BitLocker 復原主機，並要求您提供恢復密碼或復原金鑰來解除鎖定磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="be52c-327">If any of these components change while BitLocker protection is in effect, the TPM does not release the encryption key to unlock the drive and the computer instead displays the BitLocker Recovery console and requires that you provide either the recovery password or recovery key to unlock the drive.</span></span></p>
<p><span data-ttu-id="be52c-328">如果您停用或不設定此原則設定，BitLocker 會使用預設平臺驗證設定檔或由安裝腳本指定的平臺驗證設定檔。</span><span class="sxs-lookup"><span data-stu-id="be52c-328">If you disable or do not configure this policy setting, BitLocker uses the default platform validation profile or the platform validation profile that is specified by the Setup script.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="be52c-329">設定 TPM 平臺驗證設定檔</span><span class="sxs-lookup"><span data-stu-id="be52c-329">Configure TPM platform validation profile</span></span></p></td>
<td align="left"><p><span data-ttu-id="be52c-330">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="be52c-330">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="be52c-331">此原則設定可讓您設定電腦&#39;s 受信任的平臺模組（TPM）安全性硬體保護 BitLocker 加密金鑰的方式。</span><span class="sxs-lookup"><span data-stu-id="be52c-331">This policy setting enables you to configure how the computer&#39;s Trusted Platform Module (TPM) security hardware secures the BitLocker encryption key.</span></span> <span data-ttu-id="be52c-332">如果電腦沒有相容的 TPM，或已使用 TPM 保護開啟 BitLocker，此原則設定就不適用。</span><span class="sxs-lookup"><span data-stu-id="be52c-332">This policy setting does not apply if the computer does not have a compatible TPM or if BitLocker has already been turned on with TPM protection.</span></span></p>
<p><span data-ttu-id="be52c-333">如果您在開啟 BitLocker 之前啟用此原則設定，您可以先設定 TPM 驗證的啟動元件，才能解除鎖定 BitLocker 加密操作系統磁碟機的存取權。</span><span class="sxs-lookup"><span data-stu-id="be52c-333">If you enable this policy setting before you turn on BitLocker, you can configure the boot components that the TPM validates before you unlock access to the BitLocker-encrypted operating system drive.</span></span> <span data-ttu-id="be52c-334">如果在 BitLocker 保護生效時，有任何元件變更，則 TPM 不會放開加密金鑰來解除鎖定磁片磁碟機，電腦則改為顯示 BitLocker 復原主機，並要求您提供恢復密碼或復原金鑰來解除鎖定磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="be52c-334">If any of these components change while BitLocker protection is in effect, the TPM does not release the encryption key to unlock the drive and the computer instead displays the BitLocker Recovery console and requires that you provide either the recovery password or recovery key to unlock the drive.</span></span></p>
<p><span data-ttu-id="be52c-335">如果您停用或不設定此原則設定，BitLocker 會使用預設平臺驗證設定檔或由安裝腳本指定的平臺驗證設定檔。</span><span class="sxs-lookup"><span data-stu-id="be52c-335">If you disable or do not configure this policy setting, BitLocker uses the default platform validation profile or the platform validation profile that is specified by the setup script.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="be52c-336">針對原生 UEFI 固件配置設定 TPM 平臺驗證設定檔</span><span class="sxs-lookup"><span data-stu-id="be52c-336">Configure TPM platform validation profile for native UEFI firmware configurations</span></span></p></td>
<td align="left"><p><span data-ttu-id="be52c-337">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="be52c-337">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="be52c-338">此原則設定可讓您設定電腦&#39;s 受信任的平臺模組（TPM）安全性硬體保護 BitLocker 加密金鑰的方式。</span><span class="sxs-lookup"><span data-stu-id="be52c-338">This policy setting allows you to configure how the computer&#39;s Trusted Platform Module (TPM) security hardware secures the BitLocker encryption key.</span></span> <span data-ttu-id="be52c-339">如果電腦沒有相容的 TPM，或已使用 TPM 保護開啟 BitLocker，此原則設定就不適用。</span><span class="sxs-lookup"><span data-stu-id="be52c-339">This policy setting does not apply if the computer does not have a compatible TPM or if BitLocker has already been turned on with TPM protection.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="be52c-340">重要</span><span class="sxs-lookup"><span data-stu-id="be52c-340">Important</span></span></strong><br/><p><span data-ttu-id="be52c-341">這個群組原則設定僅適用于具有原生 UEFI 固件配置的電腦。</span><span class="sxs-lookup"><span data-stu-id="be52c-341">This Group Policy setting applies only to computers with a native UEFI firmware configuration.</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="be52c-342">如果您在開啟 BitLocker 之前啟用此原則設定，您可以先設定 TPM 驗證的啟動元件，才能解除對 BitLocker 加密操作系統磁碟機的存取。</span><span class="sxs-lookup"><span data-stu-id="be52c-342">If you enable this policy setting before you turn on BitLocker, you can configure the boot components that the TPM validates before unlocking access to the BitLocker-encrypted operating system drive.</span></span> <span data-ttu-id="be52c-343">如果在 BitLocker 保護生效時，有任何元件變更，則 TPM 不會放開加密金鑰來解除鎖定磁片磁碟機，電腦則改為顯示 BitLocker 復原主機，並要求您提供恢復密碼或復原金鑰來解除鎖定磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="be52c-343">If any of these components change while BitLocker protection is in effect, the TPM does not release the encryption key to unlock the drive and the computer instead displays the BitLocker Recovery console and requires that you provide either the recovery password or recovery key to unlock the drive.</span></span></p>
<p><span data-ttu-id="be52c-344">如果您停用或不設定此原則設定，BitLocker 會使用預設平臺驗證設定檔或由安裝腳本指定的平臺驗證設定檔。</span><span class="sxs-lookup"><span data-stu-id="be52c-344">If you disable or do not configure this policy setting, BitLocker uses the default platform validation profile or the platform validation profile that is specified by the setup script.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="be52c-345">在 BitLocker 恢復之後重設平臺驗證資料</span><span class="sxs-lookup"><span data-stu-id="be52c-345">Reset platform validation data after BitLocker recovery</span></span></p></td>
<td align="left"><p><span data-ttu-id="be52c-346">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="be52c-346">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="be52c-347">使用此原則設定，控制在 BitLocker 復原後啟動 Windows 時，是否要重新整理 platform 驗證資料。</span><span class="sxs-lookup"><span data-stu-id="be52c-347">Use this policy setting to control whether platform validation data is refreshed when Windows is started after BitLocker recovery.</span></span></p>
<p><span data-ttu-id="be52c-348">如果您啟用此原則設定，當 Windows 在 BitLocker 恢復之後啟動時，平臺驗證資料就會重新整理。</span><span class="sxs-lookup"><span data-stu-id="be52c-348">If you enable this policy setting, platform validation data are refreshed when Windows is started after BitLocker recovery.</span></span> <span data-ttu-id="be52c-349">如果您停用此原則設定，當 Windows 在 BitLocker 恢復之後啟動時，平臺驗證資料就不會重新整理。</span><span class="sxs-lookup"><span data-stu-id="be52c-349">If you disable this policy setting, platform validation data are not refreshed when Windows is started after BitLocker recovery.</span></span> <span data-ttu-id="be52c-350">如果您未設定此原則設定，則會在 BitLocker 恢復後啟動 Windows 時，重新整理平臺驗證資料。</span><span class="sxs-lookup"><span data-stu-id="be52c-350">If you do not configure this policy setting, platform validation data are refreshed when Windows is started after BitLocker recovery.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="be52c-351">使用增強型啟動設定資料驗證設定檔</span><span class="sxs-lookup"><span data-stu-id="be52c-351">Use enhanced Boot Configuration Data validation profile</span></span></p></td>
<td align="left"><p><span data-ttu-id="be52c-352">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="be52c-352">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="be52c-353">此原則設定可讓您選擇要在平臺驗證期間進行驗證的特定開機設定資料（BCD）設定。</span><span class="sxs-lookup"><span data-stu-id="be52c-353">This policy setting allows you to choose specific Boot Configuration Data (BCD) settings to verify during platform validation.</span></span></p>
<p><span data-ttu-id="be52c-354">如果您啟用此原則設定，您可以新增其他設定、移除預設設定，或兩者皆移除。</span><span class="sxs-lookup"><span data-stu-id="be52c-354">If you enable this policy setting, you can add additional settings, remove the default settings, or both.</span></span> <span data-ttu-id="be52c-355">如果您停用此原則設定，電腦會還原為與 Windows 7 所使用的預設 BCD 設定檔類似的 BCD 設定檔。</span><span class="sxs-lookup"><span data-stu-id="be52c-355">If you disable this policy setting, the computer reverts to a BCD profile similar to the default BCD profile that is used by Windows 7.</span></span> <span data-ttu-id="be52c-356">如果您未設定此原則設定，電腦會驗證預設的 Windows BCD 設定。</span><span class="sxs-lookup"><span data-stu-id="be52c-356">If you do not configure this policy setting, the computer verifies the default Windows BCD settings.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="be52c-357">注意</span><span class="sxs-lookup"><span data-stu-id="be52c-357">Note</span></span></strong><br/><p><span data-ttu-id="be52c-358">當 BitLocker 使用安全啟動來進行平臺與啟動配置資料（BCD）完整性驗證時，如 [ &quot; 允許完整性驗證的安全引導] 原則所定義 &quot; ，則 &quot; 會忽略 [使用增強型引導設定資料驗證設定檔 &quot; 原則]。</span><span class="sxs-lookup"><span data-stu-id="be52c-358">When BitLocker uses Secure Boot for platform and Boot Configuration Data (BCD) integrity validation, as defined by the &quot;Allow Secure Boot for integrity validation&quot; policy, the &quot;Use enhanced Boot Configuration Data validation profile&quot; policy is ignored.</span></span></p>
</div>
<div>

</div>
<p><span data-ttu-id="be52c-359">控制引導調試（0x16000010）的設定總是經過驗證，且在提供的欄位中包含它時不會有任何作用。</span><span class="sxs-lookup"><span data-stu-id="be52c-359">The setting that controls boot debugging (0x16000010) is always validated and has no effect if it is included in the provided fields.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="be52c-360">加密原則強制設定</span><span class="sxs-lookup"><span data-stu-id="be52c-360">Encryption Policy Enforcement Settings</span></span></p></td>
<td align="left"><p><span data-ttu-id="be52c-361">建議的設定： <strong> 已啟用</span><span class="sxs-lookup"><span data-stu-id="be52c-361">Suggested configuration: <strong>Enabled</span></span></strong></p>
<p><span data-ttu-id="be52c-362">使用此原則設定，以設定使用者可針對其作業系統磁片磁碟機遵循 MBAM 原則而延遲的天數。</span><span class="sxs-lookup"><span data-stu-id="be52c-362">Use this policy setting to configure the number of days that users can postpone complying with MBAM policies for their operating system drive.</span></span> <span data-ttu-id="be52c-363">寬限期在第一次偵測到作業系統為不相容時開始。</span><span class="sxs-lookup"><span data-stu-id="be52c-363">The grace period begins when the operating system is first detected as noncompliant.</span></span> <span data-ttu-id="be52c-364">此寬限期到期之後，使用者就無法推遲所需的動作，或要求它提出例外狀況。</span><span class="sxs-lookup"><span data-stu-id="be52c-364">After this grace period expires, users cannot postpone the required action or request an exemption from it.</span></span></p>
<p><span data-ttu-id="be52c-365">如果加密程式需要使用者輸入，則會顯示一個對話方塊，讓使用者無法關閉，直到它們提供所需的資訊為止。</span><span class="sxs-lookup"><span data-stu-id="be52c-365">If the encryption process requires user input, a dialog box appears that users cannot close until they provide the required information.</span></span></p>
<p><span data-ttu-id="be52c-366">如果您停用或不設定此設定，使用者就不會強制遵守 MBAM 原則。</span><span class="sxs-lookup"><span data-stu-id="be52c-366">If you disable or do not configure this setting, users are not forced to comply with MBAM policies.</span></span></p>
<p><span data-ttu-id="be52c-367">如果不需要使用者互動，即可新增保護器，則在寬限期到期之後，就會在背景中開始加密。</span><span class="sxs-lookup"><span data-stu-id="be52c-367">If no user interaction is required to add a protector, encryption begins in the background after the grace period expires.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="be52c-368">設定預先啟動的恢復訊息和 URL</span><span class="sxs-lookup"><span data-stu-id="be52c-368">Configure pre-boot recovery message and URL</span></span></p></td>
<td align="left"><p><span data-ttu-id="be52c-369">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="be52c-369">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="be52c-370">啟用此原則設定以設定自訂的復原訊息，或指定當操作系統磁碟機已鎖定時，在預啟動 BitLocker 恢復畫面上顯示的 URL。</span><span class="sxs-lookup"><span data-stu-id="be52c-370">Enable this policy setting to configure a custom recovery message or to specify a URL that is then displayed on the pre-boot BitLocker recovery screen when the OS drive is locked.</span></span> <span data-ttu-id="be52c-371">這個設定只能在執行 Windows 10 的用戶端電腦上使用。</span><span class="sxs-lookup"><span data-stu-id="be52c-371">This setting is only available on client computers running Windows 10.</span></span></p>
<p><span data-ttu-id="be52c-372">啟用此原則時，您可以針對預啟動還原訊息選取下列其中一個選項：</span><span class="sxs-lookup"><span data-stu-id="be52c-372">When this policy is enabled, you can select one of these options for the pre-boot recovery message:</span></span></p>
<ul>
<li><p><strong><span data-ttu-id="be52c-373">使用自訂的復原訊息 </strong> ：選取這個選項，即可在 [預啟動 BitLocker 恢復] 畫面中包含自訂訊息。</span><span class="sxs-lookup"><span data-stu-id="be52c-373">Use custom recovery message</strong>: Select this option to include a custom message in the pre-boot BitLocker recovery screen.</span></span> <span data-ttu-id="be52c-374">在 [ <strong> 自訂復原訊息] 選項方塊中 </strong> ，輸入您要顯示的訊息。</span><span class="sxs-lookup"><span data-stu-id="be52c-374">In the <strong>Custom recovery message option</strong> box, type the message that you want displayed.</span></span> <span data-ttu-id="be52c-375">如果您也想要指定復原 URL，請將它包含在您的自訂復原訊息中。</span><span class="sxs-lookup"><span data-stu-id="be52c-375">If you also want to specify a recovery URL, include it as part of your custom recovery message.</span></span></p></li>
<li><p><strong><span data-ttu-id="be52c-376">使用自訂的復原 URL </strong> ：選取這個選項，以取代 [預啟動 BitLocker 恢復] 畫面中顯示的預設 URL。</span><span class="sxs-lookup"><span data-stu-id="be52c-376">Use custom recovery URL</strong>: Select this option to replace the default URL that is displayed in the pre-boot BitLocker recovery screen.</span></span> <span data-ttu-id="be52c-377">在 [ <strong> 自訂恢復 URL] 選項方塊中 </strong> ，輸入您要顯示的 URL。</span><span class="sxs-lookup"><span data-stu-id="be52c-377">In the <strong>Custom recovery URL option</strong> box, type the URL that you want displayed.</span></span></p></li>
<li><p><strong><span data-ttu-id="be52c-378">使用預設的復原訊息和 URL </strong> ：選取這個選項，即可在 [啟動前的 bitlocker 恢復] 畫面中顯示預設的 BitLocker 復原訊息和 URL。</span><span class="sxs-lookup"><span data-stu-id="be52c-378">Use default recovery message and URL</strong>: Select this option to display the default BitLocker recovery message and URL in the pre-boot BitLocker recovery screen.</span></span> <span data-ttu-id="be52c-379">如果您先前已設定自訂的復原訊息或 URL，且想要還原為預設訊息，您必須啟用此原則，然後選取 [ <strong> 使用預設的復原訊息與 URL] </strong> 選項。</span><span class="sxs-lookup"><span data-stu-id="be52c-379">If you previously configured a custom recovery message or URL and want to revert to the default message, you must enable this policy and select the <strong>Use default recovery message and URL</strong> option.</span></span></p></li>
</ul>
<div class="alert">
<strong><span data-ttu-id="be52c-380">注意</span><span class="sxs-lookup"><span data-stu-id="be52c-380">Note</span></span></strong><br/><p><span data-ttu-id="be52c-381">在預引導中不支援所有的字元和語言。</span><span class="sxs-lookup"><span data-stu-id="be52c-381">Not all characters and languages are supported in pre-boot.</span></span> <span data-ttu-id="be52c-382">我們建議您在預啟動 BitLocker 恢復畫面上，測試您在自訂訊息或 URL 所使用的字元是否正確顯示。</span><span class="sxs-lookup"><span data-stu-id="be52c-382">We recommend that you test that the characters you use for the custom message or URL appear correctly on the pre-boot BitLocker recovery screen.</span></span></p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



### <span data-ttu-id="be52c-383">抽取式磁碟磁碟機群組原則定義</span><span class="sxs-lookup"><span data-stu-id="be52c-383">Removable Drive Group Policy definitions</span></span>

<span data-ttu-id="be52c-384">本節說明 Microsoft BitLocker 管理和監視下列 GPO 節點的抽取式磁碟磁碟機組原則定義： [**電腦**設定 &gt; **策略**] &gt; **管理範本** &gt; **Windows 元件** &gt; **MDOP MBAM （BitLocker 管理）** &gt; **抽取式磁碟磁碟機**。</span><span class="sxs-lookup"><span data-stu-id="be52c-384">This section describes Removable Drive Group Policy definitions for Microsoft BitLocker Administration and Monitoring at the following GPO node: **Computer Configuration** &gt; **Policies** &gt; **Administrative Templates** &gt; **Windows Components** &gt; **MDOP MBAM (BitLocker Management)** &gt; **Removable Drive**.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="be52c-385">原則名稱</span><span class="sxs-lookup"><span data-stu-id="be52c-385">Policy name</span></span></th>
<th align="left"><span data-ttu-id="be52c-386">概覽及建議的群組原則設定</span><span class="sxs-lookup"><span data-stu-id="be52c-386">Overview and suggested Group Policy settings</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="be52c-387">在抽取式磁碟磁碟機上控制 BitLocker 的使用</span><span class="sxs-lookup"><span data-stu-id="be52c-387">Control use of BitLocker on removable drives</span></span></p></td>
<td align="left"><p><span data-ttu-id="be52c-388">建議的設定： <strong> 已啟用</span><span class="sxs-lookup"><span data-stu-id="be52c-388">Suggested configuration: <strong>Enabled</span></span></strong></p>
<p><span data-ttu-id="be52c-389">此原則控制如何在可移動資料磁碟機上使用 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="be52c-389">This policy controls the use of BitLocker on removable data drives.</span></span></p>
<p><span data-ttu-id="be52c-390">按一下 [ <strong> 允許使用者在可移動資料磁碟機上套用 bitlocker 保護 </strong> ]，可讓使用者在可移除的資料磁碟機上執行 bitlocker 設定向導。</span><span class="sxs-lookup"><span data-stu-id="be52c-390">Click <strong>Allow users to apply BitLocker protection on removable data drives</strong> to allow users to run the BitLocker setup wizard on a removable data drive.</span></span></p>
<p><span data-ttu-id="be52c-391">按一下 [ <strong> 允許使用者暫停並解密可移動資料磁碟機上的 bitlocker]， </strong> 可讓使用者從磁片磁碟機移除 bitlocker 磁片磁碟機加密，或在執行維護時暫停加密。</span><span class="sxs-lookup"><span data-stu-id="be52c-391">Click <strong>Allow users to suspend and decrypt BitLocker on removable data drives</strong> to enable users to remove BitLocker drive encryption from the drive or to suspend the encryption while maintenance is performed.</span></span></p>
<p><span data-ttu-id="be52c-392">啟用此原則時，當您按一下 <strong> [允許使用者在可移動資料磁碟機上套用 BitLocker 保護] 時 </strong> ，MBAM 用戶端會將抽取式磁碟磁碟機的復原資訊儲存至 MBAM 金鑰復原伺服器，並允許使用者在密碼遺失時復原磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="be52c-392">When this policy is enabled, and you click <strong>Allow users to apply BitLocker protection on removable data drives</strong>, the MBAM Client saves the recovery information about removable drives to the MBAM key recovery server and allows users to recover the drive if the password is lost.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="be52c-393">拒絕寫入存取不受 BitLocker 保護的抽取式磁碟機</span><span class="sxs-lookup"><span data-stu-id="be52c-393">Deny write access to removable drives not protected by BitLocker</span></span></p></td>
<td align="left"><p><span data-ttu-id="be52c-394">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="be52c-394">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="be52c-395">啟用此原則，只允許將寫入權限給受 BitLocker 保護的磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="be52c-395">Enable this policy to allow only write permission to BitLocker-protected drives.</span></span></p>
<p><span data-ttu-id="be52c-396">如果啟用此原則，電腦上所有的可移動資料磁碟機都必須先加密，才能允許寫入權限。</span><span class="sxs-lookup"><span data-stu-id="be52c-396">When this policy is enabled, all removable data drives on the computer require encryption before write permission is allowed.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="be52c-397">允許從舊版 Windows 存取受 BitLocker 保護的抽取式磁碟磁碟機</span><span class="sxs-lookup"><span data-stu-id="be52c-397">Allow access to BitLocker-protected removable drives from earlier versions of Windows</span></span></p></td>
<td align="left"><p><span data-ttu-id="be52c-398">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="be52c-398">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="be52c-399">啟用此原則可讓使用 FAT 檔案系統的固定磁片磁碟機解除鎖定，並在執行 Windows Server 2008、Windows Vista、Windows XP （含 SP3）或 Windows XP （含 SP2）的電腦上進行查看。</span><span class="sxs-lookup"><span data-stu-id="be52c-399">Enable this policy to allow fixed drives with the FAT file system to be unlocked and viewed on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2.</span></span></p>
<p><span data-ttu-id="be52c-400">如果未設定此原則，則可以在執行 Windows Server 2008、Windows Vista、Windows XP （含 SP3）或 Windows XP （含 SP2）的電腦上解除鎖定使用 FAT 檔案系統格式化的抽取式磁碟磁碟機，並且能夠查看其內容。</span><span class="sxs-lookup"><span data-stu-id="be52c-400">When this policy is not configured, removable drives that are formatted with the FAT file system can be unlocked on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2, and their content can be viewed.</span></span> <span data-ttu-id="be52c-401">這些作業系統擁有受 BitLocker 保護的磁片磁碟機的唯讀許可權。</span><span class="sxs-lookup"><span data-stu-id="be52c-401">These operating systems have read-only permission to BitLocker-protected drives.</span></span></p>
<p><span data-ttu-id="be52c-402">當原則停用時，無法在執行 Windows Server 2008、Windows Vista、windows XP 的電腦上，或使用 SP2，在執行 Windows Server、Windows Vista、Windows XP 或 Windows XP 的電腦上，查看以 FAT 檔案系統格式化的抽取式磁碟磁碟機。</span><span class="sxs-lookup"><span data-stu-id="be52c-402">When the policy is disabled, removable drives formatted with the FAT file system cannot be unlocked and their content cannot be viewed on computers that are running Windows Server 2008, Windows Vista, Windows XP with SP3, or Windows XP with SP2.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="be52c-403">針對可移動資料磁碟機設定密碼的使用方式</span><span class="sxs-lookup"><span data-stu-id="be52c-403">Configure use of password for removable data drives</span></span></p></td>
<td align="left"><p><span data-ttu-id="be52c-404">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="be52c-404">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="be52c-405">啟用此原則，在可移動資料磁碟機上設定密碼保護。</span><span class="sxs-lookup"><span data-stu-id="be52c-405">Enable this policy to configure password protection on removable data drives.</span></span></p>
<p><span data-ttu-id="be52c-406">如果未設定此原則，預設設定就會支援密碼，這不會包含密碼複雜性需求，且只需要八個字元。</span><span class="sxs-lookup"><span data-stu-id="be52c-406">When this policy is not configured, passwords are supported with the default settings, which do not include password complexity requirements and which require only eight characters.</span></span></p>
<p><span data-ttu-id="be52c-407">若要提高安全性，您可以啟用此原則，然後選取 [ <strong> 移除資料磁片磁碟機需要密碼] </strong> 、按一下 <strong> [需要密碼複雜性] </strong> ，然後設定首選的 <strong> 最小密碼長度 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="be52c-407">For increased security, you can enable this policy and select <strong>Require password for removable data drive</strong>, click <strong>Require password complexity</strong>, and set the preferred <strong>minimum password length</strong>.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="be52c-408">選擇可如何復原受 BitLocker 保護的抽取式磁碟磁碟機</span><span class="sxs-lookup"><span data-stu-id="be52c-408">Choose how BitLocker-protected removable drives can be recovered</span></span></p></td>
<td align="left"><p><span data-ttu-id="be52c-409">建議的配置： <strong> 未設定</span><span class="sxs-lookup"><span data-stu-id="be52c-409">Suggested configuration: <strong>Not Configured</span></span></strong></p>
<p><span data-ttu-id="be52c-410">設定此原則以啟用 BitLocker 資料復原代理程式，或將 BitLocker 復原資訊儲存至 Active Directory 網域服務（AD DS）。</span><span class="sxs-lookup"><span data-stu-id="be52c-410">Configure this policy to enable the BitLocker data recovery agent or to save BitLocker recovery information to Active Directory Domain Services (AD DS).</span></span></p>
<p><span data-ttu-id="be52c-411">如果設定為 [未設定] <strong> </strong> ，則允許資料修復代理程式，且不會將復原資訊備份到 AD DS。</span><span class="sxs-lookup"><span data-stu-id="be52c-411">When set to <strong>Not Configured</strong>, the data recovery agent is allowed, and recovery information is not backed up to AD DS.</span></span></p>
<p><span data-ttu-id="be52c-412">MBAM 操作不需要將復原資訊備份到 AD DS。</span><span class="sxs-lookup"><span data-stu-id="be52c-412">MBAM operation does not require recovery information to be backed up to AD DS.</span></span></p></td>
</tr>
</tbody>
</table>




## <span data-ttu-id="be52c-413">相關主題</span><span class="sxs-lookup"><span data-stu-id="be52c-413">Related topics</span></span>


[<span data-ttu-id="be52c-414">MBAM 2.5 的環境準備</span><span class="sxs-lookup"><span data-stu-id="be52c-414">Preparing your Environment for MBAM 2.5</span></span>](preparing-your-environment-for-mbam-25.md)

[<span data-ttu-id="be52c-415">MBAM 2.5 部署必要條件</span><span class="sxs-lookup"><span data-stu-id="be52c-415">MBAM 2.5 Deployment Prerequisites</span></span>](mbam-25-deployment-prerequisites.md)


## <span data-ttu-id="be52c-416">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="be52c-416">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="be52c-417">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="be52c-417">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="be52c-418">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="be52c-418">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>






