---
title: 關於 MBAM 2.5
description: 關於 MBAM 2.5
author: dansimp
ms.assetid: 1ce218ec-4d2e-4a75-8d1a-68d737a8f3c9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: d4c9ff0bc5ee3f7dc51a56cc428081a7c3783694
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810419"
---
# <span data-ttu-id="95efd-103">關於 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="95efd-103">About MBAM 2.5</span></span>


<span data-ttu-id="95efd-104">Microsoft BitLocker 管理和監控（MBAM）2.5 提供簡化的 BitLocker 磁碟機加密管理介面。</span><span class="sxs-lookup"><span data-stu-id="95efd-104">Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 provides a simplified administrative interface for BitLocker Drive Encryption.</span></span> <span data-ttu-id="95efd-105">BitLocker 針對遺失或被盜電腦的資料竊取或資料暴露提供增強型保護。</span><span class="sxs-lookup"><span data-stu-id="95efd-105">BitLocker offers enhanced protection against data theft or data exposure for computers that are lost or stolen.</span></span> <span data-ttu-id="95efd-106">BitLocker 會加密儲存在 Windows 作業系統的磁片、磁碟機及已設定的資料磁碟機上的所有資料。</span><span class="sxs-lookup"><span data-stu-id="95efd-106">BitLocker encrypts all data that is stored on the Windows operating system volumes and drives and configured data drives.</span></span>

## <span data-ttu-id="95efd-107">MBAM 概覽</span><span class="sxs-lookup"><span data-stu-id="95efd-107">Overview of MBAM</span></span>


<span data-ttu-id="95efd-108">MBAM 2.5 具有下列功能：</span><span class="sxs-lookup"><span data-stu-id="95efd-108">MBAM 2.5 has the following features:</span></span>

-   <span data-ttu-id="95efd-109">可讓系統管理員自動處理整個企業用戶端電腦上的加密量。</span><span class="sxs-lookup"><span data-stu-id="95efd-109">Enables administrators to automate the process of encrypting volumes on client computers across the enterprise.</span></span>

-   <span data-ttu-id="95efd-110">可讓安全性監察官快速判斷個別電腦或甚至企業本身的合規性狀態。</span><span class="sxs-lookup"><span data-stu-id="95efd-110">Enables security officers to quickly determine the compliance state of individual computers or even of the enterprise itself.</span></span>

-   <span data-ttu-id="95efd-111">使用 Microsoft System Center Configuration Manager 提供集中式報告及硬體管理。</span><span class="sxs-lookup"><span data-stu-id="95efd-111">Provides centralized reporting and hardware management with Microsoft System Center Configuration Manager.</span></span>

-   <span data-ttu-id="95efd-112">減少支援中心的工作負荷，協助最終使用者使用 BitLocker PIN 和復原金鑰要求。</span><span class="sxs-lookup"><span data-stu-id="95efd-112">Reduces the workload on the Help Desk to assist end users with BitLocker PIN and recovery key requests.</span></span>

-   <span data-ttu-id="95efd-113">讓使用者能夠使用自助入口網站，獨立地復原加密的裝置。</span><span class="sxs-lookup"><span data-stu-id="95efd-113">Enables end users to recover encrypted devices independently by using the Self-Service Portal.</span></span>

-   <span data-ttu-id="95efd-114">讓安全官員能夠輕鬆地審核存取權，以復原金鑰資訊。</span><span class="sxs-lookup"><span data-stu-id="95efd-114">Enables security officers to easily audit access to recover key information.</span></span>

-   <span data-ttu-id="95efd-115">讓 Windows 企業使用者能在任何地方繼續運作，保證公司資料受到保護。</span><span class="sxs-lookup"><span data-stu-id="95efd-115">Empowers Windows Enterprise users to continue working anywhere with the assurance that their corporate data is protected.</span></span>

<span data-ttu-id="95efd-116">MBAM 會強制執行您針對企業所設定的 BitLocker 加密原則選項、監控用戶端電腦與這些原則的合規性，以及企業及個人電腦的加密狀態報表。</span><span class="sxs-lookup"><span data-stu-id="95efd-116">MBAM enforces the BitLocker encryption policy options that you set for your enterprise, monitors the compliance of client computers with those policies, and reports on the encryption status of the enterprise’s and individual’s computers.</span></span> <span data-ttu-id="95efd-117">此外，MBAM 可讓您在使用者忘記其 PIN 或密碼時，或當他們的 BIOS 或開機記錄變更時，存取復原金鑰資訊。</span><span class="sxs-lookup"><span data-stu-id="95efd-117">In addition, MBAM lets you access the recovery key information when users forget their PIN or password, or when their BIOS or boot records change.</span></span>

<span data-ttu-id="95efd-118">下列群組可能會對使用 MBAM 來管理 BitLocker 感興趣：</span><span class="sxs-lookup"><span data-stu-id="95efd-118">The following groups might be interested in using MBAM to manage BitLocker:</span></span>

-   <span data-ttu-id="95efd-119">管理員、IT 安全性專業人員，以及負責確保機密資料在未授權的情況下公開的合規性官員</span><span class="sxs-lookup"><span data-stu-id="95efd-119">Administrators, IT security professionals, and compliance officers who are responsible for ensuring that confidential data is not disclosed without authorization</span></span>

-   <span data-ttu-id="95efd-120">負責遠端或分支辦公室中電腦安全性性的管理員</span><span class="sxs-lookup"><span data-stu-id="95efd-120">Administrators who are responsible for computer security in remote or branch offices</span></span>

-   <span data-ttu-id="95efd-121">負責執行 Windows 之用戶端電腦的系統管理員</span><span class="sxs-lookup"><span data-stu-id="95efd-121">Administrators who are responsible for client computers that are running Windows</span></span>

<span data-ttu-id="95efd-122">**記事** 在本 MBAM 檔中不詳細說明 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="95efd-122">**Note** BitLocker is not explained in detail in this MBAM documentation.</span></span> <span data-ttu-id="95efd-123">如需詳細資訊，請參閱[BitLocker 磁片磁碟機加密概述](https://go.microsoft.com/fwlink/p/?LinkId=225013)。</span><span class="sxs-lookup"><span data-stu-id="95efd-123">For more information, see [BitLocker Drive Encryption Overview](https://go.microsoft.com/fwlink/p/?LinkId=225013).</span></span>

 

## <a href="" id="what-s-new-in-mbam-2-5"></a><span data-ttu-id="95efd-124">MBAM 2.5 的新功能</span><span class="sxs-lookup"><span data-stu-id="95efd-124">What’s new in MBAM 2.5</span></span>


<span data-ttu-id="95efd-125">本節將說明 MBAM 2.5 中的新功能。</span><span class="sxs-lookup"><span data-stu-id="95efd-125">This section describes the new features in MBAM 2.5.</span></span>

### <span data-ttu-id="95efd-126">Microsoft SQL Server 2014 支援</span><span class="sxs-lookup"><span data-stu-id="95efd-126">Support for Microsoft SQL Server 2014</span></span>

<span data-ttu-id="95efd-127">除了舊版 MBAM 中支援的相同軟體之外，MBAM 也會新增 Microsoft SQL Server 2014 的支援。</span><span class="sxs-lookup"><span data-stu-id="95efd-127">MBAM adds support for Microsoft SQL Server 2014, in addition to the same software that is supported in earlier versions of MBAM.</span></span>

### <a href="" id="-------------mbam-group-policy-templates-downloaded-separately"></a> <span data-ttu-id="95efd-128">MBAM 群組原則範本個別下載</span><span class="sxs-lookup"><span data-stu-id="95efd-128">MBAM Group Policy Templates downloaded separately</span></span>

<span data-ttu-id="95efd-129">MBAM 群組原則範本必須從 MBAM 安裝中單獨下載。</span><span class="sxs-lookup"><span data-stu-id="95efd-129">The MBAM Group Policy Templates must be downloaded separately from the MBAM installation.</span></span> <span data-ttu-id="95efd-130">在舊版 MBAM 中，MBAM 安裝套裝程式含一個 MBAM 原則範本，其中包含所需的 MBAM 特定組原則物件（Gpo），這些物件定義 BitLocker 磁片磁碟機加密的 MBAM 實現設定。</span><span class="sxs-lookup"><span data-stu-id="95efd-130">In previous versions of MBAM, the MBAM installer included an MBAM Policy Template, which contained the required MBAM-specific Group Policy Objects (GPOs) that define MBAM implementation settings for BitLocker Drive Encryption.</span></span> <span data-ttu-id="95efd-131">這些 Gpo 已從 MBAM 安裝程式中移除。</span><span class="sxs-lookup"><span data-stu-id="95efd-131">These GPOs have been removed from the MBAM installer.</span></span> <span data-ttu-id="95efd-132">您現在可以在開始 MBAM 用戶端安裝之前，先從[如何取得 MDOP 組原則（admx）範本](https://go.microsoft.com/fwlink/p/?LinkId=393941)下載 gpo，並將它們複製到伺服器或工作站。</span><span class="sxs-lookup"><span data-stu-id="95efd-132">You now download the GPOs from [How to Get MDOP Group Policy (.admx) Templates](https://go.microsoft.com/fwlink/p/?LinkId=393941) and copy them to a server or workstation before you begin the MBAM Client installation.</span></span> <span data-ttu-id="95efd-133">您可以將群組原則範本複製到執行受支援版本的 Windows Server 或 Windows 作業系統的任何伺服器或工作站。</span><span class="sxs-lookup"><span data-stu-id="95efd-133">You can copy the Group Policy Templates to any server or workstation that is running a supported version of the Windows Server or Windows operating system.</span></span>

<span data-ttu-id="95efd-134">**重要** 請勿變更**BitLocker 磁片磁碟機加密**節點中的群組原則設定，否則 MBAM 將無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="95efd-134">**Important** Do not change the Group Policy settings in the **BitLocker Drive Encryption** node, or MBAM will not work correctly.</span></span> <span data-ttu-id="95efd-135">當您在**MDOP MBAM （BitLocker 管理）** 節點中設定群組原則設定時，MBAM 會自動為您設定 BitLocker 磁片磁碟機加密設定。</span><span class="sxs-lookup"><span data-stu-id="95efd-135">When you configure the Group Policy settings in the **MDOP MBAM (BitLocker Management)** node, MBAM automatically configures the BitLocker Drive Encryption settings for you.</span></span>

 

<span data-ttu-id="95efd-136">您需要複製到伺服器或工作站的範本檔案如下：</span><span class="sxs-lookup"><span data-stu-id="95efd-136">The template files that you need to copy to a server or workstation are:</span></span>

-   <span data-ttu-id="95efd-137">BitLockerManagement. adml</span><span class="sxs-lookup"><span data-stu-id="95efd-137">BitLockerManagement.adml</span></span>

-   <span data-ttu-id="95efd-138">BitLockerManagement admx</span><span class="sxs-lookup"><span data-stu-id="95efd-138">BitLockerManagement.admx</span></span>

-   <span data-ttu-id="95efd-139">BitLockerUserManagement. adml</span><span class="sxs-lookup"><span data-stu-id="95efd-139">BitLockerUserManagement.adml</span></span>

-   <span data-ttu-id="95efd-140">BitLockerUserManagement admx</span><span class="sxs-lookup"><span data-stu-id="95efd-140">BitLockerUserManagement.admx</span></span>

<span data-ttu-id="95efd-141">將範本檔案複製到最符合您需求的位置。</span><span class="sxs-lookup"><span data-stu-id="95efd-141">Copy the template files to the location that best meets your needs.</span></span> <span data-ttu-id="95efd-142">針對必須複製到語言特定資料夾的語言特定檔案，需要使用 [群組原則管理主控台] 來查看檔案。</span><span class="sxs-lookup"><span data-stu-id="95efd-142">For the language-specific files, which must be copied to a language-specific folder, the Group Policy Management Console is required to view the files.</span></span>

- <span data-ttu-id="95efd-143">若要在本機的伺服器或工作站上安裝範本檔案，請將檔案複製到下列其中一個位置。</span><span class="sxs-lookup"><span data-stu-id="95efd-143">To install the template files locally on a server or workstation, copy the files to one of the following locations.</span></span>

  <table>
  <colgroup>
  <col width="50%" />
  <col width="50%" />
  </colgroup>
  <thead>
  <tr class="header">
  <th align="left"><span data-ttu-id="95efd-144">檔案類型</span><span class="sxs-lookup"><span data-stu-id="95efd-144">File type</span></span></th>
  <th align="left"><span data-ttu-id="95efd-145">檔案位置</span><span class="sxs-lookup"><span data-stu-id="95efd-145">File location</span></span></th>
  </tr>
  </thead>
  <tbody>
  <tr class="odd">
  <td align="left"><p><span data-ttu-id="95efd-146">語言中立（admx）</span><span class="sxs-lookup"><span data-stu-id="95efd-146">language neutral (.admx)</span></span></p></td>
  <td align="left"><p><em><span data-ttu-id="95efd-147">% systemroot% </em> \policyDefinitions</span><span class="sxs-lookup"><span data-stu-id="95efd-147">%systemroot%</em>\policyDefinitions</span></span></p></td>
  </tr>
  <tr class="even">
  <td align="left"><p><span data-ttu-id="95efd-148">語言專用（adml）</span><span class="sxs-lookup"><span data-stu-id="95efd-148">language specific (.adml)</span></span></p></td>
  <td align="left"><p><em><span data-ttu-id="95efd-149">% systemroot% </em> \policyDefinitions [ <em> MUIculture </em> ] （例如，美國英文專用檔案將會儲存在 <em> % systemroot% &lt; /em &gt; policyDefinitions\en-us）中</span><span class="sxs-lookup"><span data-stu-id="95efd-149">%systemroot%</em>\policyDefinitions[<em>MUIculture</em>] (for example, the U.S. English language specific file will be stored in <em>%systemroot%&lt;/em&gt;policyDefinitions\en-us)</span></span></p></td>
  </tr>
  </tbody>
  </table>

     

- <span data-ttu-id="95efd-150">若要讓網域中的所有群組原則管理員都能使用這些範本，請將檔案複製到網網域控制站上下列其中一個位置。</span><span class="sxs-lookup"><span data-stu-id="95efd-150">To make the templates available to all Group Policy administrators in a domain, copy the files to one of the following locations on a domain controller.</span></span>

  <table>
  <colgroup>
  <col width="50%" />
  <col width="50%" />
  </colgroup>
  <thead>
  <tr class="header">
  <th align="left"><span data-ttu-id="95efd-151">檔案類型</span><span class="sxs-lookup"><span data-stu-id="95efd-151">File type</span></span></th>
  <th align="left"><span data-ttu-id="95efd-152">網網域控制站檔案位置</span><span class="sxs-lookup"><span data-stu-id="95efd-152">Domain controller file location</span></span></th>
  </tr>
  </thead>
  <tbody>
  <tr class="odd">
  <td align="left"><p><span data-ttu-id="95efd-153">語言中立（admx）</span><span class="sxs-lookup"><span data-stu-id="95efd-153">Language neutral (.admx)</span></span></p></td>
  <td align="left"><p><em><span data-ttu-id="95efd-154">% systemroot% </em> sysvol\domain\policies\PolicyDefinitions</span><span class="sxs-lookup"><span data-stu-id="95efd-154">%systemroot%</em>sysvol\domain\policies\PolicyDefinitions</span></span></p></td>
  </tr>
  <tr class="even">
  <td align="left"><p><span data-ttu-id="95efd-155">語言專用（adml）</span><span class="sxs-lookup"><span data-stu-id="95efd-155">Language specific (.adml)</span></span></p></td>
  <td align="left"><p><em><span data-ttu-id="95efd-156">% systemroot% </em> \sysvol\domain\policies\PolicyDefinitions [ <em> MUIculture </em> ] （例如，美國英文語言專用檔案將會儲存在 <em> % systemroot% </em> \sysvol\domain\policies\PolicyDefinitions\en-us 中）</span><span class="sxs-lookup"><span data-stu-id="95efd-156">%systemroot%</em>\sysvol\domain\policies\PolicyDefinitions[<em>MUIculture</em>] (for example, the U.S. English language-specific file will be stored in <em>%systemroot%</em>\sysvol\domain\policies\PolicyDefinitions\en-us)</span></span></p></td>
  </tr>
  </tbody>
  </table>

     

<span data-ttu-id="95efd-157">如需範本檔案的詳細資訊，請參閱[管理群組原則 ADMX 檔案逐步指南](https://go.microsoft.com/fwlink/?LinkId=392818)。</span><span class="sxs-lookup"><span data-stu-id="95efd-157">For more information about template files, see [Managing Group Policy ADMX Files Step-by-Step Guide](https://go.microsoft.com/fwlink/?LinkId=392818).</span></span>

### <span data-ttu-id="95efd-158">能夠在作業系統和固定資料磁碟機上強制執行加密原則</span><span class="sxs-lookup"><span data-stu-id="95efd-158">Ability to enforce encryption policies on operating system and fixed data drives</span></span>

<span data-ttu-id="95efd-159">MBAM 2.5 可讓您針對組織中的電腦強制執行加密原則和固定資料磁碟機，並限制最終使用者可要求的天數，以符合 MBAM 加密原則的需求。</span><span class="sxs-lookup"><span data-stu-id="95efd-159">MBAM2.5 enables you to enforce encryption policies on operating system and fixed data drives for computers in your organization and limit the number of days that end users can request a postponement of the requirement to comply with MBAM encryption policies.</span></span>

<span data-ttu-id="95efd-160">若要讓您設定加密原則強制，已為作業系統磁片磁碟機及固定資料磁碟機新增了新的群組原則設定（稱為「加密原則強制執行設定」）。</span><span class="sxs-lookup"><span data-stu-id="95efd-160">To enable you to configure encryption policy enforcement, a new Group Policy setting, called Encryption Policy Enforcement Settings, has been added for operating system drives and fixed data drives.</span></span> <span data-ttu-id="95efd-161">此原則如下表所述。</span><span class="sxs-lookup"><span data-stu-id="95efd-161">This policy is described in the following table.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="95efd-162">群組原則設定</span><span class="sxs-lookup"><span data-stu-id="95efd-162">Group Policy setting</span></span></th>
<th align="left"><span data-ttu-id="95efd-163">描述</span><span class="sxs-lookup"><span data-stu-id="95efd-163">Description</span></span></th>
<th align="left"><span data-ttu-id="95efd-164">用來設定此設定的群組原則節點</span><span class="sxs-lookup"><span data-stu-id="95efd-164">Group Policy node used to configure this setting</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="95efd-165">加密原則強制設定（作業系統磁片磁碟機）</span><span class="sxs-lookup"><span data-stu-id="95efd-165">Encryption Policy Enforcement Settings (Operating System Drive)</span></span></p></td>
<td align="left"><p><span data-ttu-id="95efd-166">針對此設定，請使用選項 <strong> 設定作業系統磁片磁碟機設定寬限期的不符合寬限期間天數 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="95efd-166">For this setting, use the option <strong>Configure the number of noncompliance grace period days for operating system drives</strong> to configure a grace period.</span></span></p>
<p><span data-ttu-id="95efd-167">寬限期指定在第一次偵測到磁碟機之後，最終使用者可在其操作系統磁碟機中延遲遵守 MBAM 原則的天數。</span><span class="sxs-lookup"><span data-stu-id="95efd-167">The grace period specifies the number of days that end users can postpone compliance with MBAM policies for their operating system drive after the drive is first detected as noncompliant.</span></span></p>
<p><span data-ttu-id="95efd-168">在設定的寬限期到期後，使用者將無法延遲所需的動作，或要求它提出例外狀況。</span><span class="sxs-lookup"><span data-stu-id="95efd-168">After the configured grace period expires, users cannot postpone the required action or request an exemption from it.</span></span></p>
<p><span data-ttu-id="95efd-169">如果需要使用者互動（例如，如果您使用的是受信任的平臺模組（TPM） + PIN 或使用密碼保護器），則會顯示對話方塊，且使用者無法關閉它，直到它們提供所需的資訊為止。</span><span class="sxs-lookup"><span data-stu-id="95efd-169">If user interaction is required (for example, if you are using the Trusted Platform Module (TPM) + PIN or using a password protector), a dialog box appears, and users cannot close it until they provide the required information.</span></span> <span data-ttu-id="95efd-170">如果保護器只有 TPM，則在不使用使用者輸入的情況下，會立即在背景中開始加密。</span><span class="sxs-lookup"><span data-stu-id="95efd-170">If the protector is TPM only, encryption begins immediately in the background without user input.</span></span></p>
<p><span data-ttu-id="95efd-171">使用者無法透過 BitLocker 加密嚮導要求免除。</span><span class="sxs-lookup"><span data-stu-id="95efd-171">Users cannot request exemptions through the BitLocker encryption wizard.</span></span> <span data-ttu-id="95efd-172">相反地，他們必須與技術支援人員聯繫，或使用其組織針對豁免要求所使用的任何流程。</span><span class="sxs-lookup"><span data-stu-id="95efd-172">Instead, they must contact their Help Desk or use whatever process their organization uses for exemption requests.</span></span></p></td>
<td align="left"><p><span data-ttu-id="95efd-173">電腦設定 &gt; 策略系統 &gt; 管理範本 &gt; WINDOWS 元件 &gt; MDOP MBAM （BitLocker Management） &gt; 作業系統磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="95efd-173">Computer Configuration &gt; Policies &gt; Administrative Templates &gt; Windows Components &gt; MDOP MBAM (BitLocker Management) &gt; Operating System Drive</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="95efd-174">加密原則強制設定（固定資料磁碟機）</span><span class="sxs-lookup"><span data-stu-id="95efd-174">Encryption Policy Enforcement Settings (Fixed Data Drives)</span></span></p></td>
<td align="left"><p><span data-ttu-id="95efd-175">針對此設定，請使用選項 <strong> 設定固定磁碟機的不符合寬限期間天數 </strong> ，以設定寬限期。</span><span class="sxs-lookup"><span data-stu-id="95efd-175">For this setting, use the option <strong>Configure the number of noncompliance grace period days for fixed drives</strong> to configure a grace period.</span></span></p>
<p><span data-ttu-id="95efd-176">寬限期指定在第一次偵測到磁碟機為不相容之後，最終使用者可以針對其固定磁片磁碟機的 MBAM 原則，將合規性延遲的天數。</span><span class="sxs-lookup"><span data-stu-id="95efd-176">The grace period specifies the number of days that end users can postpone compliance with MBAM policies for their fixed drive after the drive is first detected as noncompliant.</span></span></p>
<p><span data-ttu-id="95efd-177">寬限期的開始時間是將固定的磁片決定為不相容。</span><span class="sxs-lookup"><span data-stu-id="95efd-177">The grace period begins when the fixed drive is determined to be noncompliant.</span></span> <span data-ttu-id="95efd-178">如果您使用的是自動解除鎖定，則必須符合操作系統磁碟機，才能強制執行原則。</span><span class="sxs-lookup"><span data-stu-id="95efd-178">If you are using auto-unlock, the policy will not be enforced until the operating system drive is compliant.</span></span> <span data-ttu-id="95efd-179">不過，如果您不是使用自動解鎖，就可以在作業系統磁片磁碟機完全加密之前，先開始加密固定資料磁碟機。</span><span class="sxs-lookup"><span data-stu-id="95efd-179">However, if you are not using auto-unlock, encryption of the fixed data drive can begin before the operating system drive is fully encrypted.</span></span></p>
<p><span data-ttu-id="95efd-180">在設定的寬限期到期後，使用者將無法延遲所需的動作，或要求它提出例外狀況。</span><span class="sxs-lookup"><span data-stu-id="95efd-180">After the configured grace period expires, users cannot postpone the required action or request an exemption from it.</span></span> <span data-ttu-id="95efd-181">如果需要使用者互動，就會出現對話方塊，且使用者必須提供所需的資訊，才能將其關閉。</span><span class="sxs-lookup"><span data-stu-id="95efd-181">If user interaction is required, a dialog box appears and users cannot close it until they provide the required information.</span></span></p></td>
<td align="left"><p><span data-ttu-id="95efd-182">電腦 &gt; 設定策略系統 &gt; 管理範本 &gt; WINDOWS 元件 &gt; MDOP MBAM （BitLocker Management）已 &gt; 固定的磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="95efd-182">Computer Configuration &gt; Policies &gt; Administrative Templates &gt; Windows Components &gt; MDOP MBAM (BitLocker Management) &gt; Fixed Drive</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="95efd-183">能夠在 BitLocker 磁片磁碟機加密嚮導中提供 URL，以指向您的安全性原則</span><span class="sxs-lookup"><span data-stu-id="95efd-183">Ability to provide a URL in the BitLocker Drive Encryption wizard to point to your security policy</span></span>

<span data-ttu-id="95efd-184">新的群組原則設定是**提供安全性原則連結的 url**，可讓您設定 url，以將其出示給最終使用者作為名為 [**公司安全性原則**] 的連結。</span><span class="sxs-lookup"><span data-stu-id="95efd-184">A new Group Policy setting, **Provide the URL for the Security Policy link**, enables you to configure a URL that will be presented to end users as a link called **Company Security Policy**.</span></span> <span data-ttu-id="95efd-185">當 MBAM 提示使用者加密卷時，就會出現這個連結。</span><span class="sxs-lookup"><span data-stu-id="95efd-185">This link will appear when MBAM prompts users to encrypt a volume.</span></span>

<span data-ttu-id="95efd-186">如果您啟用此原則設定，您可以設定 [**公司安全性原則**] 連結的 URL。</span><span class="sxs-lookup"><span data-stu-id="95efd-186">If you enable this policy setting, you can configure the URL for the **Company Security Policy** link.</span></span> <span data-ttu-id="95efd-187">如果您停用或不設定此原則設定，系統就不會向使用者顯示 [**公司安全性原則**] 連結。</span><span class="sxs-lookup"><span data-stu-id="95efd-187">If you disable or do not configure this policy setting, the **Company Security Policy** link is not displayed to users.</span></span>

<span data-ttu-id="95efd-188">新的群組原則設定位於下列 GPO 節點： [電腦設定**Computer Configuration** &gt; **策略**] &gt; **管理範本** &gt; **Windows 元件** &gt; **MDOP MBAM （BitLocker Management） &gt; 用戶端管理**。</span><span class="sxs-lookup"><span data-stu-id="95efd-188">The new Group Policy setting is located in the following GPO node: **Computer Configuration** &gt; **Policies** &gt; **Administrative Templates** &gt; **Windows Components** &gt; **MDOP MBAM (BitLocker Management) &gt; Client Management**.</span></span>

### <span data-ttu-id="95efd-189">支援 FIPS 相容的修復金鑰</span><span class="sxs-lookup"><span data-stu-id="95efd-189">Support for FIPS-compliant recovery keys</span></span>

<span data-ttu-id="95efd-190">MBAM 2.5 支援執行 Windows 8.1 作業系統之裝置上的聯邦資訊處理標準（FIPS）相容的 BitLocker 復原金鑰。</span><span class="sxs-lookup"><span data-stu-id="95efd-190">MBAM2.5 supports Federal Information Processing Standard (FIPS)-compliant BitLocker recovery keys on devices that are running the Windows8.1 operating system.</span></span> <span data-ttu-id="95efd-191">在舊版 Windows 中，修復金鑰不符合 FIPS 規範。</span><span class="sxs-lookup"><span data-stu-id="95efd-191">The recovery key was not FIPS compliant in earlier versions of Windows.</span></span> <span data-ttu-id="95efd-192">此增強功能改善了需要 FIPS 合規性之組織中的磁片磁碟機復原程式，因為它能讓使用者使用自助入口網站或管理和監控網站（問訊台），在忘記其 PIN 或密碼或封鎖電腦的情況下，復原其硬碟。</span><span class="sxs-lookup"><span data-stu-id="95efd-192">This enhancement improves the drive recovery process in organizations that require FIPS compliance because it enables end users to use the Self-Service Portal or Administration and Monitoring Website (Help Desk) to recover their drives if they forget their PIN or password or get locked out of their computers.</span></span> <span data-ttu-id="95efd-193">新的 FIPS 相容性功能不會延伸到密碼保護器。</span><span class="sxs-lookup"><span data-stu-id="95efd-193">The new FIPS compliance feature does not extend to password protectors.</span></span>

<span data-ttu-id="95efd-194">若要在貴組織中啟用 FIPS 相容性，您必須設定聯邦資訊處理標準（FIPS）群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="95efd-194">To enable FIPS compliance in your organization, you must configure the Federal Information Processing Standard (FIPS) Group Policy settings.</span></span> <span data-ttu-id="95efd-195">如需配置指示，請參閱[BitLocker 群組原則設定](https://go.microsoft.com/fwlink/?LinkId=393560)。</span><span class="sxs-lookup"><span data-stu-id="95efd-195">For configuration instructions, see [BitLocker Group Policy Settings](https://go.microsoft.com/fwlink/?LinkId=393560).</span></span>

<span data-ttu-id="95efd-196">對於執行 Windows8 或 Windows7 作業系統的用戶端電腦（沒有安裝的[BitLocker 修復程式](https://support.microsoft.com/kb/3015477)），IT 系統管理員會繼續在 FIPS 相容的環境中使用資料修復代理程式（DRA）保護器。</span><span class="sxs-lookup"><span data-stu-id="95efd-196">For client computers that are running the Windows8 or Windows7 operating systems without the [installed BitLocker hotfix](https://support.microsoft.com/kb/3015477), IT administrators will continue to use the Data Recovery Agents (DRA) protector in FIPS-compliant environments.</span></span> <span data-ttu-id="95efd-197">如需 DRA 的相關資訊，請參閱將[資料修復代理程式與 BitLocker 配合使用](https://go.microsoft.com/fwlink/?LinkId=393557)。</span><span class="sxs-lookup"><span data-stu-id="95efd-197">For information about DRA, see [Using Data Recovery Agents with BitLocker](https://go.microsoft.com/fwlink/?LinkId=393557).</span></span>

<span data-ttu-id="95efd-198">若要下載並安裝適用于 Windows 7 和 Windows 8 電腦的 BitLocker 修復程式，請參閱[BitLocker 管理和監視2.5 的修補程式套件 2](https://support.microsoft.com/kb/3015477) 。</span><span class="sxs-lookup"><span data-stu-id="95efd-198">See [Hotfix Package 2 for BitLocker Administration and Monitoring 2.5](https://support.microsoft.com/kb/3015477) to download and install the BitLocker hotfix for Windows 7 and Windows 8 computers.</span></span>

### <span data-ttu-id="95efd-199">支援高可用性部署</span><span class="sxs-lookup"><span data-stu-id="95efd-199">Support for high availability deployments</span></span>

<span data-ttu-id="95efd-200">除了標準的雙伺服器與 Configuration Manager 整合拓朴之外，MBAM 還支援下列高可用性案例：</span><span class="sxs-lookup"><span data-stu-id="95efd-200">MBAM supports the following high-availability scenarios in addition to the standard two-server and Configuration Manager Integration topologies:</span></span>

-   <span data-ttu-id="95efd-201">SQL Server AlwaysOn 可用性群組</span><span class="sxs-lookup"><span data-stu-id="95efd-201">SQL Server AlwaysOn availability groups</span></span>

-   <span data-ttu-id="95efd-202">SQL Server 群集</span><span class="sxs-lookup"><span data-stu-id="95efd-202">SQL Server clustering</span></span>

-   <span data-ttu-id="95efd-203">網路負載平衡（NLB）</span><span class="sxs-lookup"><span data-stu-id="95efd-203">Network load balancing (NLB)</span></span>

-   <span data-ttu-id="95efd-204">SQL Server 鏡像</span><span class="sxs-lookup"><span data-stu-id="95efd-204">SQL Server mirroring</span></span>

-   <span data-ttu-id="95efd-205">[卷影複製服務（VSS）] 備份</span><span class="sxs-lookup"><span data-stu-id="95efd-205">Volume Shadow Copy Service (VSS) Backup</span></span>

<span data-ttu-id="95efd-206">如需這些功能的詳細資訊，請參閱[規劃 MBAM 2.5 高可用性](planning-for-mbam-25-high-availability.md)。</span><span class="sxs-lookup"><span data-stu-id="95efd-206">For more information about these features, see [Planning for MBAM 2.5 High Availability](planning-for-mbam-25-high-availability.md).</span></span>

### <a href="" id="management-of-roles-for-administration-and-monitoring-website-changed-"></a><span data-ttu-id="95efd-207">管理和監控網站已變更的角色管理</span><span class="sxs-lookup"><span data-stu-id="95efd-207">Management of roles for Administration and Monitoring Website changed</span></span>

<span data-ttu-id="95efd-208">在 MBAM 2.5 中，您必須在 Active Directory 網域服務（新增）中建立安全性群組，以管理提供管理和監視網站存取權的角色。</span><span class="sxs-lookup"><span data-stu-id="95efd-208">In MBAM2.5, you must create security groups in Active Directory Domain Services (ADDS) to manage the roles that provide access rights to the Administration and Monitoring Website.</span></span> <span data-ttu-id="95efd-209">角色可讓特定安全群組中的使用者在網站中執行不同的工作，例如查看報表或協助使用者復原加密的磁碟機。</span><span class="sxs-lookup"><span data-stu-id="95efd-209">Roles enable users who are in specific security groups to perform different tasks in the website such as viewing reports or helping end users recover encrypted drives.</span></span> <span data-ttu-id="95efd-210">在舊版 MBAM 中，角色是使用本機群組來管理。</span><span class="sxs-lookup"><span data-stu-id="95efd-210">In previous versions of MBAM, roles were managed by using local groups.</span></span>

<span data-ttu-id="95efd-211">在 MBAM 2.5 中，「角色」一詞會取代舊版 MBAM 中使用的「管理員角色」一詞。</span><span class="sxs-lookup"><span data-stu-id="95efd-211">In MBAM2.5, the term “roles” replaces the term “administrator roles,” which was used in earlier versions of MBAM.</span></span> <span data-ttu-id="95efd-212">此外，在 MBAM 2.5 中，"MBAM 系統管理員" 角色已移除。</span><span class="sxs-lookup"><span data-stu-id="95efd-212">In addition, in MBAM2.5 the “MBAM System Administrators” role has been removed.</span></span>

<span data-ttu-id="95efd-213">下表列出您必須在 AD DS 中建立的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="95efd-213">The following table lists the security groups that you must create in AD DS.</span></span> <span data-ttu-id="95efd-214">您可以針對安全性群組使用任何名稱。</span><span class="sxs-lookup"><span data-stu-id="95efd-214">You can use any name for the security groups.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="95efd-215">角色</span><span class="sxs-lookup"><span data-stu-id="95efd-215">Role</span></span></th>
<th align="left"><span data-ttu-id="95efd-216">此角色在 [管理] 和 [監視] 網站上的存取權限</span><span class="sxs-lookup"><span data-stu-id="95efd-216">Access rights for this role on the Administration and Monitoring Website</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="95efd-217">MBAM 支援人員的使用者</span><span class="sxs-lookup"><span data-stu-id="95efd-217">MBAM Helpdesk Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="95efd-218">提供存取 MBAM 管理和監控網站之 [管理 TPM] 和 [磁片磁碟機] 區域的許可權。</span><span class="sxs-lookup"><span data-stu-id="95efd-218">Provides access to the Manage TPM and Drive Recovery areas of the MBAM Administration and Monitoring Website.</span></span> <span data-ttu-id="95efd-219">擁有這些區域存取權的使用者，在使用任一區域時，都必須填入所有欄位。</span><span class="sxs-lookup"><span data-stu-id="95efd-219">Users who have access to these areas must fill in all fields when they use either area.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="95efd-220">MBAM 報表使用者</span><span class="sxs-lookup"><span data-stu-id="95efd-220">MBAM Report Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="95efd-221">提供管理和監控網站中報告的存取權。</span><span class="sxs-lookup"><span data-stu-id="95efd-221">Provides access to the Reports in the Administration and Monitoring Website.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="95efd-222">MBAM 高級支援人員的使用者</span><span class="sxs-lookup"><span data-stu-id="95efd-222">MBAM Advanced Helpdesk Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="95efd-223">提供管理和監控網站中所有區域的存取權。</span><span class="sxs-lookup"><span data-stu-id="95efd-223">Provides access to all areas in the Administration and Monitoring Website.</span></span> <span data-ttu-id="95efd-224">這個群組中的使用者在協助使用者復原其磁碟機時，只需要輸入復原金鑰，而不是使用者的網域和使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="95efd-224">Users in this group have to enter only the recovery key, not the end user’s domain and user name, when helping end users recover their drives.</span></span> <span data-ttu-id="95efd-225">如果使用者是 MBAM [支援人員] 群組和 MBAM [高級服務台使用者] 群組的成員，MBAM [高級支援人員] 群組許可權會覆寫 MBAM 的 [支援人員] 群組許可權。</span><span class="sxs-lookup"><span data-stu-id="95efd-225">If a user is a member of the MBAM Helpdesk Users group and the MBAM Advanced Helpdesk Users group, the MBAM Advanced Helpdesk Users group permissions override the MBAM Helpdesk Users group permissions.</span></span></p></td>
</tr>
</tbody>
</table>

 

<span data-ttu-id="95efd-226">在新增中建立安全性群組之後，請將使用者和/或群組指派給適當的安全性群組，以啟用管理與監視網站的對應層級存取。</span><span class="sxs-lookup"><span data-stu-id="95efd-226">After you create the security groups in ADDS, assign users and/or groups to the appropriate security group to enable the corresponding level of access to the Administration and Monitoring Website.</span></span> <span data-ttu-id="95efd-227">若要讓每個角色的使用者都能存取 [管理] 和 [監視] 網站，您也必須在設定管理和監視網站時指定每個安全性群組。</span><span class="sxs-lookup"><span data-stu-id="95efd-227">To enable individuals with each role to access the Administration and Monitoring Website, you must also specify each security group when you are configuring the Administration and Monitoring Website.</span></span>

### <span data-ttu-id="95efd-228">用來設定 MBAM 伺服器功能的 Windows PowerShell Cmdlet</span><span class="sxs-lookup"><span data-stu-id="95efd-228">Windows PowerShell cmdlets for configuring MBAM Server features</span></span>

<span data-ttu-id="95efd-229">MBAM 2.5 的 Windows PowerShell Cmdlet 可讓您設定及管理 MBAM 伺服器功能。</span><span class="sxs-lookup"><span data-stu-id="95efd-229">Windows PowerShell cmdlets for MBAM2.5 enable you to configure and manage the MBAM Server features.</span></span> <span data-ttu-id="95efd-230">每個功能都有對應的 Windows PowerShell Cmdlet，您可以用來啟用或停用功能，或是取得該功能的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="95efd-230">Each feature has a corresponding Windows PowerShell cmdlet that you can use to enable or disable features, or to get information about the feature.</span></span>

<span data-ttu-id="95efd-231">如需使用 Windows PowerShell 的先決條件與先決條件，請參閱[使用 Windows powershell 設定 MBAM 2.5 伺服器功能](configuring-mbam-25-server-features-by-using-windows-powershell.md)。</span><span class="sxs-lookup"><span data-stu-id="95efd-231">For prerequisites and prerequisites for using Windows PowerShell, see [Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md).</span></span>

**<span data-ttu-id="95efd-232">若要在安裝 MBAM 伺服器軟體後載入 Windows PowerShell Cmdlet 的 MBAM 2.5 說明</span><span class="sxs-lookup"><span data-stu-id="95efd-232">To load the MBAM 2.5 Help for Windows PowerShell cmdlets after installing the MBAM Server software</span></span>**

1.  <span data-ttu-id="95efd-233">開啟 Windows PowerShell 或 Windows PowerShell 整合式腳本環境（ISE）。</span><span class="sxs-lookup"><span data-stu-id="95efd-233">Open Windows PowerShell or Windows PowerShell Integrated Scripting Environment (ISE).</span></span>

2.  <span data-ttu-id="95efd-234">類型**更新-說明-MODULE MBAM**。</span><span class="sxs-lookup"><span data-stu-id="95efd-234">Type **Update-Help –Module Microsoft.MBAM**.</span></span>

<span data-ttu-id="95efd-235">MBAM 的 Windows PowerShell 說明提供下列格式：</span><span class="sxs-lookup"><span data-stu-id="95efd-235">Windows PowerShell Help for MBAM is available in the following formats:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="95efd-236">Windows PowerShell 說明格式</span><span class="sxs-lookup"><span data-stu-id="95efd-236">Windows PowerShell Help format</span></span></th>
<th align="left"><span data-ttu-id="95efd-237">詳細資訊</span><span class="sxs-lookup"><span data-stu-id="95efd-237">More information</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="95efd-238">在 Windows PowerShell 命令提示字元中，輸入 <strong> get-help </strong> &lt; <em> Cmdlet</em>&gt;</span><span class="sxs-lookup"><span data-stu-id="95efd-238">At a Windows PowerShell command prompt, type <strong>Get-Help</strong> &lt;<em>cmdlet</em>&gt;</span></span></p></td>
<td align="left"><p><span data-ttu-id="95efd-239">若要上傳最新的 Windows PowerShell Cmdlet，請按照上一節中如何載入 MBAM 的 Windows PowerShell 說明一節中的指示進行。</span><span class="sxs-lookup"><span data-stu-id="95efd-239">To upload the latest Windows PowerShell cmdlets, follow the instructions in the previous section on how to load Windows PowerShell Help for MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="95efd-240">在 TechNet 上做為網頁</span><span class="sxs-lookup"><span data-stu-id="95efd-240">On TechNet as webpages</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393498" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393498">https://go.microsoft.com/fwlink/?LinkId=393498</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="95efd-241">以單字 .docx 檔案的形式在下載中心</span><span class="sxs-lookup"><span data-stu-id="95efd-241">On the Download Center as a Word .docx file</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393497" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393497">https://go.microsoft.com/fwlink/?LinkId=393497</a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="95efd-242">以 .pdf 檔案的形式在下載中心</span><span class="sxs-lookup"><span data-stu-id="95efd-242">On the Download Center as a .pdf file</span></span></p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393499" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393499">https://go.microsoft.com/fwlink/?LinkId=393499</a></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="95efd-243">支援僅限 ASCII 且增強的 Pin，以及防止順序及重複字元的能力</span><span class="sxs-lookup"><span data-stu-id="95efd-243">Support for ASCII-only and enhanced PINs and ability to prevent sequential and repeating characters</span></span>

**<span data-ttu-id="95efd-244">允許 [啟動] 群組原則設定的增強型 Pin</span><span class="sxs-lookup"><span data-stu-id="95efd-244">Allow enhanced PINs for startup Group Policy setting</span></span>**

<span data-ttu-id="95efd-245">[群組原則] 設定是 [**允許增強的 pin 以進行啟動**]，可讓您設定是否與 BitLocker 搭配使用增強的啟動 pin。</span><span class="sxs-lookup"><span data-stu-id="95efd-245">The Group Policy setting, **Allow enhanced PINs for startup**, enables you to configure whether enhanced startup PINs are used with BitLocker.</span></span> <span data-ttu-id="95efd-246">增強的啟動 Pin 功能可讓使用者在完整的鍵盤上輸入任何按鍵，包括大寫及小寫字母、符號、數位和空格。</span><span class="sxs-lookup"><span data-stu-id="95efd-246">Enhanced startup PINs permit users to enter any keys on a full keyboard, including uppercase and lowercase letters, symbols, numbers, and spaces.</span></span> <span data-ttu-id="95efd-247">如果您啟用此原則設定，所有設定的新 BitLocker 啟動 Pin 都將是增強的 Pin。</span><span class="sxs-lookup"><span data-stu-id="95efd-247">If you enable this policy setting, all new BitLocker startup PINs that are set will be enhanced PINs.</span></span> <span data-ttu-id="95efd-248">如果您停用或不設定此原則設定，就無法使用增強的 Pin。</span><span class="sxs-lookup"><span data-stu-id="95efd-248">If you disable or do not configure this policy setting, enhanced PINs cannot be used.</span></span>

<span data-ttu-id="95efd-249">並非所有電腦都支援開機前執行環境（PXE）中的增強型 Pin 輸入。</span><span class="sxs-lookup"><span data-stu-id="95efd-249">Not all computers support the entry of enhanced PINs in the Pre-Boot Execution Environment (PXE).</span></span> <span data-ttu-id="95efd-250">在您的組織啟用此群組原則設定之前，請先執行 BitLocker 安裝程式期間的系統檢查，以確保電腦的 BIOS 支援在 PXE 中使用完整的鍵盤。</span><span class="sxs-lookup"><span data-stu-id="95efd-250">Before you enable this Group Policy setting for your organization, run a system check during the BitLocker setup process to ensure that the computer’s BIOS supports the use of the full keyboard in PXE.</span></span> <span data-ttu-id="95efd-251">如需詳細資訊，請參閱[規劃 MBAM 2.5 群組原則需求](planning-for-mbam-25-group-policy-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="95efd-251">For more information, see [Planning for MBAM 2.5 Group Policy Requirements](planning-for-mbam-25-group-policy-requirements.md).</span></span>

**<span data-ttu-id="95efd-252">[需要 ASCII 專用 Pin] 核取方塊</span><span class="sxs-lookup"><span data-stu-id="95efd-252">Require ASCII-only PINs check box</span></span>**

<span data-ttu-id="95efd-253">[**允許啟動群組的增強型 pin** ] 群組原則設定也包含 [**需要 ASCII 專用 pin** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="95efd-253">The **Allow enhanced PINs for startup** Group Policy setting also contains a **Require ASCII-only PINs** check box.</span></span> <span data-ttu-id="95efd-254">如果貴組織中的電腦不支援在 PXE 中使用完整的鍵盤，您可以啟用 [**允許啟動**] 群群組原則設定的 [已增強的 pin]，然後選取 [**需要 ASCII 專用 pin** ] 核取方塊，以要求 [增強 pin] 只使用可列印的 ascii 字元。</span><span class="sxs-lookup"><span data-stu-id="95efd-254">If the computers in your organization do not support the use of the full keyboard in PXE, you can enable the **Allow enhanced PINs for startup** Group Policy setting, and then select the **Require ASCII-only PINs** check box to require that enhanced PINs use only printable ASCII characters.</span></span>

**<span data-ttu-id="95efd-255">強制使用非順序和非重複字元</span><span class="sxs-lookup"><span data-stu-id="95efd-255">Enforced use of nonsequential and nonrepeating characters</span></span>**

<span data-ttu-id="95efd-256">MBAM 2.5 可防止最終使用者建立由重複數位（例如1111）或連續數位（例如1234）的 Pin。</span><span class="sxs-lookup"><span data-stu-id="95efd-256">MBAM2.5 prevents end users from creating PINs that consist of repeating numbers (such as 1111) or sequential numbers (such as 1234).</span></span> <span data-ttu-id="95efd-257">如果使用者嘗試輸入包含三個或多個重複或連續數位的密碼，則 Bitlocker 磁片磁碟機加密嚮導會顯示錯誤訊息，並防止使用者輸入包含禁止字元的 PIN。</span><span class="sxs-lookup"><span data-stu-id="95efd-257">If end users try to enter a password that contains three or more repeating or sequential numbers, the Bitlocker Drive Encryption wizard displays an error message and prevents users from entering a PIN with the prohibited characters.</span></span>

### <span data-ttu-id="95efd-258">將 DRA 憑證加入 BitLocker 電腦合規性報告</span><span class="sxs-lookup"><span data-stu-id="95efd-258">Addition of DRA Certificate to BitLocker Computer Compliance report</span></span>

<span data-ttu-id="95efd-259">已在 Configuration Manager 的 BitLocker 電腦合規性報告中新增了新的保護器類型，即資料復原代理程式（DRA）憑證。</span><span class="sxs-lookup"><span data-stu-id="95efd-259">A new protector type, the Data Recovery Agent (DRA) Certificate, has been added to the BitLocker Computer Compliance Report in Configuration Manager.</span></span> <span data-ttu-id="95efd-260">此保護器類型適用于操作系統磁碟機，且出現在 [**保護類型**] 欄的 [**電腦卷**] 區段中。</span><span class="sxs-lookup"><span data-stu-id="95efd-260">This protector type applies to operating system drives, and it appears in the **Computer Volume(s)** section in the **Protector Types** column.</span></span>

### <span data-ttu-id="95efd-261">支援多林支援部署</span><span class="sxs-lookup"><span data-stu-id="95efd-261">Support for multi-forest support deployments</span></span>

<span data-ttu-id="95efd-262">MBAM 2.5 支援下列多目錄林部署類型：</span><span class="sxs-lookup"><span data-stu-id="95efd-262">MBAM 2.5 supports the following types of multi-forest deployments:</span></span>

-   <span data-ttu-id="95efd-263">單一目錄林與單一網域</span><span class="sxs-lookup"><span data-stu-id="95efd-263">Single forest with single domain</span></span>

-   <span data-ttu-id="95efd-264">具有單一樹狀結構和多個網域的單一目錄林</span><span class="sxs-lookup"><span data-stu-id="95efd-264">Single forest with a single tree and multiple domains</span></span>

-   <span data-ttu-id="95efd-265">具有多個樹和不連續命名空間的單一目錄林</span><span class="sxs-lookup"><span data-stu-id="95efd-265">Single forest with multiple trees and disjoint namespaces</span></span>

-   <span data-ttu-id="95efd-266">中央目錄林拓撲中的多個林</span><span class="sxs-lookup"><span data-stu-id="95efd-266">Multiple forests in a central forest topology</span></span>

-   <span data-ttu-id="95efd-267">資原始目錄林拓朴中的多個目錄林</span><span class="sxs-lookup"><span data-stu-id="95efd-267">Multiple forests in a resource forest topology</span></span>

<span data-ttu-id="95efd-268">不支援林遷移（從單一到多、多到單、資源到整個林等），或是升級或降級。</span><span class="sxs-lookup"><span data-stu-id="95efd-268">There is no support for forest migration (going from single to multiple, multiple to single, resource to across the forest, etc.), or upgrade or downgrade.</span></span>

<span data-ttu-id="95efd-269">在多目錄林部署中部署 MBAM 的先決條件包括：</span><span class="sxs-lookup"><span data-stu-id="95efd-269">The prerequisites for deploying MBAM in multi-forest deployments are:</span></span>

-   <span data-ttu-id="95efd-270">林中必須在支援的 Windows Server 版本上執行。</span><span class="sxs-lookup"><span data-stu-id="95efd-270">Forest must be running on supported versions of Windows Server.</span></span>

-   <span data-ttu-id="95efd-271">需要雙向或單向信任。</span><span class="sxs-lookup"><span data-stu-id="95efd-271">A two-way or one-way trust is required.</span></span> <span data-ttu-id="95efd-272">單向信任要求伺服器的網域信任用戶端的網域。</span><span class="sxs-lookup"><span data-stu-id="95efd-272">One-way trusts require that the server’s domain trusts the client’s domain.</span></span> <span data-ttu-id="95efd-273">換句話說，伺服器的網域指向用戶端的網域。</span><span class="sxs-lookup"><span data-stu-id="95efd-273">In other words, the server’s domain is pointed at the client’s domain.</span></span>

### <span data-ttu-id="95efd-274">MBAM 加密硬碟的用戶端支援</span><span class="sxs-lookup"><span data-stu-id="95efd-274">MBAM Client support for Encrypted Hard Drives</span></span>

<span data-ttu-id="95efd-275">MBAM 支援針對 Opal 和 IEEE 1667 標準提供 TCG 規格需求的加密硬碟磁碟機上的 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="95efd-275">MBAM supports BitLocker on Encrypted Hard Drives that meet TCG specification requirements for Opal as well as IEEE 1667 standards.</span></span> <span data-ttu-id="95efd-276">在這些裝置上啟用 BitLocker 時，它會在加密的磁片磁碟機上產生金鑰並執行管理功能。</span><span class="sxs-lookup"><span data-stu-id="95efd-276">When BitLocker is enabled on these devices, it will generate keys and perform management functions on the encrypted drive.</span></span> <span data-ttu-id="95efd-277">如需詳細資訊，請參閱[加密的硬碟](https://technet.microsoft.com/library/hh831627.aspx)。</span><span class="sxs-lookup"><span data-stu-id="95efd-277">See [Encrypted Hard Drive](https://technet.microsoft.com/library/hh831627.aspx) for more information.</span></span>

## <span data-ttu-id="95efd-278">如何取得 MDOP 技術</span><span class="sxs-lookup"><span data-stu-id="95efd-278">How to Get MDOP Technologies</span></span>


<span data-ttu-id="95efd-279">MBAM 是 Microsoft Desktop 優化套件（MDOP）的一部分。</span><span class="sxs-lookup"><span data-stu-id="95efd-279">MBAM is a part of the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="95efd-280">MDOP 是 Microsoft 軟體保證程式的一部分。</span><span class="sxs-lookup"><span data-stu-id="95efd-280">MDOP is part of the Microsoft Software Assurance program.</span></span> <span data-ttu-id="95efd-281">如需 Microsoft 軟體保證計畫的詳細資訊，以及如何取得 MDOP，請參閱[如何取得 mdop？](https://go.microsoft.com/fwlink/?LinkId=322049)。</span><span class="sxs-lookup"><span data-stu-id="95efd-281">For more information about the Microsoft Software Assurance program and how to acquire the MDOP, see [How Do I Get MDOP?](https://go.microsoft.com/fwlink/?LinkId=322049).</span></span>

## <a href="" id="---------mbam-2-5-release-notes"></a> <span data-ttu-id="95efd-282">MBAM 2.5 版本資訊</span><span class="sxs-lookup"><span data-stu-id="95efd-282">MBAM 2.5 Release Notes</span></span>


<span data-ttu-id="95efd-283">如需本檔中未包含的詳細資訊及最新資訊，請參閱[MBAM 2.5 的版本](release-notes-for-mbam-25.md)資訊。</span><span class="sxs-lookup"><span data-stu-id="95efd-283">For more information and late-breaking news that is not included in this documentation, see [Release Notes for MBAM 2.5](release-notes-for-mbam-25.md).</span></span>

## <span data-ttu-id="95efd-284">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="95efd-284">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="95efd-285">在[這裡](https://support.microsoft.com/help/4021566/windows-10-send-feedback-to-microsoft-with-feedback-hub)傳送您的意見反應。</span><span class="sxs-lookup"><span data-stu-id="95efd-285">Send your feedback [here](https://support.microsoft.com/help/4021566/windows-10-send-feedback-to-microsoft-with-feedback-hub).</span></span> 
- <span data-ttu-id="95efd-286">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="95efd-286">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>

## <span data-ttu-id="95efd-287">相關主題</span><span class="sxs-lookup"><span data-stu-id="95efd-287">Related topics</span></span>


[<span data-ttu-id="95efd-288">Microsoft BitLocker Administration and Monitoring 2.5</span><span class="sxs-lookup"><span data-stu-id="95efd-288">Microsoft BitLocker Administration and Monitoring 2.5</span></span>](index.md)

[<span data-ttu-id="95efd-289">開始使用 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="95efd-289">Getting Started with MBAM 2.5</span></span>](getting-started-with-mbam-25.md)

 

 





