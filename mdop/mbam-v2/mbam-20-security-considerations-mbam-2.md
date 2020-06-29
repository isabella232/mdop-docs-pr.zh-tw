---
title: MBAM 2.0 安全性考量
description: MBAM 2.0 安全性考量
author: dansimp
ms.assetid: 0aa5c6e2-d92c-4e30-9f6a-b48abb667ae5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 04dc9b667faddecab629b50f4c5d909fd7b2829e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810239"
---
# <span data-ttu-id="163bc-103">MBAM 2.0 安全性考量</span><span class="sxs-lookup"><span data-stu-id="163bc-103">MBAM 2.0 Security Considerations</span></span>


<span data-ttu-id="163bc-104">本主題包含有關帳戶和群組、記錄檔案，以及 Microsoft BitLocker 管理與監控的其他安全相關考慮（MBAM）的簡短概述。</span><span class="sxs-lookup"><span data-stu-id="163bc-104">This topic contains a brief overview about the accounts and groups, log files, and other security-related considerations for Microsoft BitLocker Administration and Monitoring (MBAM).</span></span> <span data-ttu-id="163bc-105">如需詳細資訊，請參閱本文中的連結。</span><span class="sxs-lookup"><span data-stu-id="163bc-105">For more information, follow the links within this article.</span></span>

## <span data-ttu-id="163bc-106">一般安全性考慮</span><span class="sxs-lookup"><span data-stu-id="163bc-106">General Security Considerations</span></span>


**<span data-ttu-id="163bc-107">瞭解安全性風險。</span><span class="sxs-lookup"><span data-stu-id="163bc-107">Understand the security risks.</span></span>** <span data-ttu-id="163bc-108">Microsoft BitLocker 管理和監控最嚴重的風險是，未經授權的使用者可能會劫持其功能，讓您可以在 MBAM 用戶端上重新設定 BitLocker 加密並取得 BitLocker 加密金鑰資料。</span><span class="sxs-lookup"><span data-stu-id="163bc-108">The most serious risk from Microsoft BitLocker Administration and Monitoring is that its functionality could be hijacked by an unauthorized user who could then reconfigure BitLocker encryption and gain BitLocker encryption key data on MBAM Clients.</span></span> <span data-ttu-id="163bc-109">不過，由於拒絕服務攻擊而導致短時間的 MBAM 功能遺失，通常不會產生災難性影響，例如電子郵件、網路通訊、光線與電源。。</span><span class="sxs-lookup"><span data-stu-id="163bc-109">However, the loss of MBAM functionality for a short period of time, due to a denial-of-service attack, does not generally have a catastrophic impact, unlike, for example, e-mail, network communications, light, and power.</span></span>

<span data-ttu-id="163bc-110">**在物理上保護您的電腦**。</span><span class="sxs-lookup"><span data-stu-id="163bc-110">**Physically secure your computers**.</span></span> <span data-ttu-id="163bc-111">沒有物理安全性的安全性。</span><span class="sxs-lookup"><span data-stu-id="163bc-111">There is no security without physical security.</span></span> <span data-ttu-id="163bc-112">取得 MBAM 伺服器實際存取權的攻擊者，可能會利用它來攻擊整個用戶端基礎。</span><span class="sxs-lookup"><span data-stu-id="163bc-112">An attacker who gets physical access to an MBAM Server could potentially use it to attack the entire client base.</span></span> <span data-ttu-id="163bc-113">所有可能的物理攻擊都必須視為高風險，並適當地減輕問題。</span><span class="sxs-lookup"><span data-stu-id="163bc-113">All potential physical attacks must be considered high risk and mitigated appropriately.</span></span> <span data-ttu-id="163bc-114">MBAM 伺服器應該儲存在安全的伺服器機房中，並具有可控存取權。</span><span class="sxs-lookup"><span data-stu-id="163bc-114">MBAM servers should be stored in a secure server room with controlled access.</span></span> <span data-ttu-id="163bc-115">使用作業系統鎖定電腦，或使用安全的螢幕保護裝置程式，在系統管理員沒有實際顯示的情況下，保護這些電腦的安全。</span><span class="sxs-lookup"><span data-stu-id="163bc-115">Secure these computers when administrators are not physically present by having the operating system lock the computer, or by using a secured screen saver.</span></span>

<span data-ttu-id="163bc-116">**將最新的安全性更新套用至所有電腦**。</span><span class="sxs-lookup"><span data-stu-id="163bc-116">**Apply the most recent security updates to all computers**.</span></span> <span data-ttu-id="163bc-117">訂閱安全性通知服務（），隨時瞭解作業系統、Microsoft SQL Server 及 MBAM 的新更新 <https://go.microsoft.com/fwlink/?LinkId=28819> 。</span><span class="sxs-lookup"><span data-stu-id="163bc-117">Stay informed about new updates for operating systems, Microsoft SQL Server, and MBAM by subscribing to the Security Notification service (<https://go.microsoft.com/fwlink/?LinkId=28819>).</span></span>

<span data-ttu-id="163bc-118">**使用強式密碼或密碼片語**。</span><span class="sxs-lookup"><span data-stu-id="163bc-118">**Use strong passwords or pass phrases**.</span></span> <span data-ttu-id="163bc-119">針對所有 MBAM 及 MBAM 系統管理員帳戶，請務必使用具有15個或以上字元的強式密碼。</span><span class="sxs-lookup"><span data-stu-id="163bc-119">Always use strong passwords with 15 or more characters for all MBAM and MBAM administrator accounts.</span></span> <span data-ttu-id="163bc-120">請勿使用空白密碼。</span><span class="sxs-lookup"><span data-stu-id="163bc-120">Never use blank passwords.</span></span> <span data-ttu-id="163bc-121">如需密碼概念的詳細資訊，請參閱 TechNet 上的「帳戶密碼及原則」白皮書 <https://go.microsoft.com/fwlink/?LinkId=30009> 。</span><span class="sxs-lookup"><span data-stu-id="163bc-121">For more information about password concepts, see the “Account Passwords and Policies” white paper on TechNet (<https://go.microsoft.com/fwlink/?LinkId=30009>).</span></span>

## <span data-ttu-id="163bc-122">MBAM 中的帳戶和群組</span><span class="sxs-lookup"><span data-stu-id="163bc-122">Accounts and Groups in MBAM</span></span>


<span data-ttu-id="163bc-123">管理使用者帳戶的最佳做法是建立網域全域群組，並在其中新增使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="163bc-123">The best practice for managing user accounts is to create domain global groups and add user accounts to them.</span></span> <span data-ttu-id="163bc-124">然後，將網域通用帳戶新增到 MBAM 伺服器上必要的 MBAM 本機群組。</span><span class="sxs-lookup"><span data-stu-id="163bc-124">Then, add the domain global accounts to the necessary MBAM local groups on the MBAM Servers.</span></span>

### <span data-ttu-id="163bc-125">ActiveDirectoryDomainServices 群組</span><span class="sxs-lookup"><span data-stu-id="163bc-125">ActiveDirectoryDomainServices Groups</span></span>

<span data-ttu-id="163bc-126">在 MBAM 設定程式期間，不會自動建立 Active Directory 群組。</span><span class="sxs-lookup"><span data-stu-id="163bc-126">No Active Directory groups are created automatically during the MBAM setup process.</span></span> <span data-ttu-id="163bc-127">不過，建議您建立下列 ActiveDirectoryDomainServices 全域群組，以管理 MBAM 作業。</span><span class="sxs-lookup"><span data-stu-id="163bc-127">However, it is recommended that you create the following ActiveDirectoryDomainServices global groups to manage MBAM operations.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="163bc-128">群組名稱</span><span class="sxs-lookup"><span data-stu-id="163bc-128">Group Name</span></span></th>
<th align="left"><span data-ttu-id="163bc-129">詳細資料</span><span class="sxs-lookup"><span data-stu-id="163bc-129">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="163bc-130">MBAM 高級支援人員的使用者</span><span class="sxs-lookup"><span data-stu-id="163bc-130">MBAM Advanced Helpdesk Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="163bc-131">建立此群組以管理在 MBAM 設定期間建立的 MBAM Advanced 服務台使用者當地群組的成員。</span><span class="sxs-lookup"><span data-stu-id="163bc-131">Create this group to manage members of the MBAM Advanced Helpdesk Users local group created during MBAM Setup.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="163bc-132">MBAM 合規性審核資料庫存取</span><span class="sxs-lookup"><span data-stu-id="163bc-132">MBAM Compliance Auditing DB Access</span></span></p></td>
<td align="left"><p><span data-ttu-id="163bc-133">建立此群組以管理在 MBAM 設定期間建立的 MBAM 合規性審核資料庫存取本機群組的成員。</span><span class="sxs-lookup"><span data-stu-id="163bc-133">Create this group to manage members of the MBAM Compliance Auditing DB Access local group created during MBAM Setup.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="163bc-134">MBAM 支援人員的使用者</span><span class="sxs-lookup"><span data-stu-id="163bc-134">MBAM Helpdesk Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="163bc-135">建立此群組以管理在 MBAM 設定期間建立的 MBAM [支援的使用者] 本機群組的成員。</span><span class="sxs-lookup"><span data-stu-id="163bc-135">Create this group to manage members of the MBAM Helpdesk Users local group created during MBAM Setup.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="163bc-136">MBAM 恢復與硬體資料庫存取</span><span class="sxs-lookup"><span data-stu-id="163bc-136">MBAM Recovery and Hardware DB Access</span></span></p></td>
<td align="left"><p><span data-ttu-id="163bc-137">建立此群組，以管理在 MBAM 設定期間建立的 MBAM 復原與硬體資料庫存取本機群組的成員。</span><span class="sxs-lookup"><span data-stu-id="163bc-137">Create this group to manage members of the MBAM Recovery and Hardware DB Access local group created during MBAM Setup.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="163bc-138">MBAM 報表使用者</span><span class="sxs-lookup"><span data-stu-id="163bc-138">MBAM Report Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="163bc-139">建立此群組以管理在 MBAM 設定期間建立的 MBAM 報告使用者當地群組的成員。</span><span class="sxs-lookup"><span data-stu-id="163bc-139">Create this group to manage members of the MBAM Report Users local group created during MBAM Setup.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="163bc-140">MBAM 系統管理員</span><span class="sxs-lookup"><span data-stu-id="163bc-140">MBAM System Administrators</span></span></p></td>
<td align="left"><p><span data-ttu-id="163bc-141">建立此群組以管理在 MBAM 設定期間建立的 MBAM 系統管理員本機群組的成員。</span><span class="sxs-lookup"><span data-stu-id="163bc-141">Create this group to manage members of the MBAM System Administrators local group created during MBAM Setup.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="163bc-142">BitLocker 加密免除</span><span class="sxs-lookup"><span data-stu-id="163bc-142">BitLocker Encryption Exemptions</span></span></p></td>
<td align="left"><p><span data-ttu-id="163bc-143">[建立此群組] 可管理要從其登入之電腦開始的 BitLocker 加密所免除的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="163bc-143">Create this group to manage user accounts that should be exempted from BitLocker encryption starting on computers that they log on to.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <a href="" id="-------------mbam-server-local-groups"></a> <span data-ttu-id="163bc-144">MBAM Server 本機群組</span><span class="sxs-lookup"><span data-stu-id="163bc-144">MBAM Server Local Groups</span></span>

<span data-ttu-id="163bc-145">MBAM 安裝程式會建立本機群組以支援 MBAM 作業。</span><span class="sxs-lookup"><span data-stu-id="163bc-145">MBAM Setup creates local groups to support MBAM operations.</span></span> <span data-ttu-id="163bc-146">您應該將 ActiveDirectoryDomainServices 全域群組新增至適當的 MBAM 本機群組，以設定 MBAM 安全性與資料存取許可權。</span><span class="sxs-lookup"><span data-stu-id="163bc-146">You should add the ActiveDirectoryDomainServices global groups to the appropriate MBAM local groups to configure MBAM security and data access permissions.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="163bc-147">群組名稱</span><span class="sxs-lookup"><span data-stu-id="163bc-147">Group Name</span></span></th>
<th align="left"><span data-ttu-id="163bc-148">詳細資料</span><span class="sxs-lookup"><span data-stu-id="163bc-148">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="163bc-149">MBAM 高級支援人員的使用者</span><span class="sxs-lookup"><span data-stu-id="163bc-149">MBAM Advanced Helpdesk Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="163bc-150">此群組的成員已增加從 MBAM 存取服務台功能的許可權。</span><span class="sxs-lookup"><span data-stu-id="163bc-150">Members of this group have increased access to the Help Desk features from MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="163bc-151">MBAM 合規性審核資料庫存取</span><span class="sxs-lookup"><span data-stu-id="163bc-151">MBAM Compliance Auditing DB Access</span></span></p></td>
<td align="left"><p><span data-ttu-id="163bc-152">包含可存取 MBAM 合規性和審核資料庫的電腦。</span><span class="sxs-lookup"><span data-stu-id="163bc-152">Contains the machines that have access to the MBAM Compliance and Auditing Database.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="163bc-153">MBAM 支援人員的使用者</span><span class="sxs-lookup"><span data-stu-id="163bc-153">MBAM Helpdesk Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="163bc-154">此群組的成員可以從 MBAM 存取某些支援中心的功能。</span><span class="sxs-lookup"><span data-stu-id="163bc-154">Members of this group have access to some of the Help Desk features from MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="163bc-155">MBAM 恢復與硬體資料庫存取</span><span class="sxs-lookup"><span data-stu-id="163bc-155">MBAM Recovery and Hardware DB Access</span></span></p></td>
<td align="left"><p><span data-ttu-id="163bc-156">包含可存取 MBAM Recovery 資料庫的電腦。</span><span class="sxs-lookup"><span data-stu-id="163bc-156">Contains the machines that have access to the MBAM Recovery Database.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="163bc-157">MBAM 報表使用者</span><span class="sxs-lookup"><span data-stu-id="163bc-157">MBAM Report Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="163bc-158">此群組的成員可以存取 MBAM 中的合規性和審核報告。</span><span class="sxs-lookup"><span data-stu-id="163bc-158">Members of this group have access to the Compliance and Audit reports from MBAM.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="163bc-159">MBAM 系統管理員</span><span class="sxs-lookup"><span data-stu-id="163bc-159">MBAM System Administrators</span></span></p></td>
<td align="left"><p><span data-ttu-id="163bc-160">此群組的成員可以存取所有的 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="163bc-160">Members of this group have access to all MBAM features.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="163bc-161">SSRS 報表服務帳戶</span><span class="sxs-lookup"><span data-stu-id="163bc-161">SSRS Reports Service Account</span></span>

<span data-ttu-id="163bc-162">SSRS Reports 服務帳戶會提供安全性內容，以執行透過 SSRS 提供的 MBAM 報告。</span><span class="sxs-lookup"><span data-stu-id="163bc-162">The SSRS Reports service account provides the security context to run the MBAM reports available through SSRS.</span></span> <span data-ttu-id="163bc-163">在 MBAM 設定期間進行設定。</span><span class="sxs-lookup"><span data-stu-id="163bc-163">It is configured during MBAM Setup.</span></span>

<span data-ttu-id="163bc-164">當您設定 SSRS 報表服務帳戶時，請指定網域使用者帳戶，並將密碼設定為永不過期。</span><span class="sxs-lookup"><span data-stu-id="163bc-164">When you configure the SSRS Reports service account, specify a domain user account, and configure the password to never expire.</span></span>

<span data-ttu-id="163bc-165">**記事** 如果您在部署 MBAM 之後變更服務帳戶的名稱，您必須重新設定報告資料來源，以使用新的服務帳戶認證。</span><span class="sxs-lookup"><span data-stu-id="163bc-165">**Note** If you change the name of the service account after you deploy MBAM, you must reconfigure the reporting data source to use the new service account credentials.</span></span> <span data-ttu-id="163bc-166">否則，您將無法存取技術支援人員入口網站。</span><span class="sxs-lookup"><span data-stu-id="163bc-166">Otherwise, you will not be able to access the Help Desk Portal.</span></span>

 

## <a href="" id="---------mbam-log-files"></a> <span data-ttu-id="163bc-167">MBAM 記錄檔</span><span class="sxs-lookup"><span data-stu-id="163bc-167">MBAM Log Files</span></span>


<span data-ttu-id="163bc-168">在安裝 MBAM 期間，會在安裝使用者的% temp% 資料夾中建立下列 MBAM 安裝記錄檔：</span><span class="sxs-lookup"><span data-stu-id="163bc-168">The following MBAM Setup log files are created in the installing user’s %temp% folder during MBAM Setup:</span></span>

**<span data-ttu-id="163bc-169">MBAM Server 安裝程式記錄檔</span><span class="sxs-lookup"><span data-stu-id="163bc-169">MBAM Server Setup log files</span></span>**

<a href="" id="msi-five-random-characters--log"></a><span data-ttu-id="163bc-170">MSI <em> &lt; 5 隨機字元 &gt; </em> 記錄</span><span class="sxs-lookup"><span data-stu-id="163bc-170">MSI<em>&lt;five random characters&gt;</em>.log</span></span>  
<span data-ttu-id="163bc-171">記錄在 MBAM 設定和 MBAM 伺服器功能安裝期間所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="163bc-171">Logs the actions taken during MBAM Setup and MBAM Server Feature installation.</span></span>

<a href="" id="installcompliancedatabase-log"></a><span data-ttu-id="163bc-172">InstallComplianceDatabase 記錄</span><span class="sxs-lookup"><span data-stu-id="163bc-172">InstallComplianceDatabase.log</span></span>  
<span data-ttu-id="163bc-173">記錄所採取的動作，以建立 MBAM 合規性和審核資料庫設定。</span><span class="sxs-lookup"><span data-stu-id="163bc-173">Logs actions taken to create the MBAM Compliance and Audit Database setup.</span></span>

<a href="" id="installkeycompliancedatabase-log"></a><span data-ttu-id="163bc-174">InstallKeyComplianceDatabase 記錄</span><span class="sxs-lookup"><span data-stu-id="163bc-174">InstallKeyComplianceDatabase.log</span></span>  
<span data-ttu-id="163bc-175">記錄建立 MBAM 復原資料庫所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="163bc-175">Logs actions taken to create the MBAM Recovery Database.</span></span>

<a href="" id="addhelpdeskdbauditusers-log"></a><span data-ttu-id="163bc-176">AddHelpDeskDbAuditUsers 記錄</span><span class="sxs-lookup"><span data-stu-id="163bc-176">AddHelpDeskDbAuditUsers.log</span></span>  
<span data-ttu-id="163bc-177">記錄在 MBAM 合規性和審核資料庫上建立 SQL Server 登入所採取的動作，並針對報表授權支援人員的 web 服務。</span><span class="sxs-lookup"><span data-stu-id="163bc-177">Logs actions taken to create the SQL Server logins on the MBAM Compliance and Audit database and authorize the HelpDesk web service to the database for reports.</span></span>

<a href="" id="addhelpdeskdbusers-log"></a><span data-ttu-id="163bc-178">AddHelpDeskDbUsers 記錄</span><span class="sxs-lookup"><span data-stu-id="163bc-178">AddHelpDeskDbUsers.log</span></span>  
<span data-ttu-id="163bc-179">記錄在授權 web 服務時所採取的動作，以取得金鑰復原的資料庫，並建立 MBAM 復原資料庫的登入。</span><span class="sxs-lookup"><span data-stu-id="163bc-179">Logs actions taken to authorize web services to database for key recovery and create logins to the MBAM Recovery Database.</span></span>

<a href="" id="addkeycompliancedbusers-log"></a><span data-ttu-id="163bc-180">AddKeyComplianceDbUsers 記錄</span><span class="sxs-lookup"><span data-stu-id="163bc-180">AddKeyComplianceDbUsers.log</span></span>  
<span data-ttu-id="163bc-181">記錄授權 web 服務所採取的動作，以 MBAM 合規性和審核資料庫以進行合規性報告。</span><span class="sxs-lookup"><span data-stu-id="163bc-181">Logs actions taken to authorize web services to MBAM Compliance and Audit Database for compliance reporting.</span></span>

<a href="" id="addrecoveryandhardwaredbusers-log"></a><span data-ttu-id="163bc-182">AddRecoveryAndHardwareDbUsers 記錄</span><span class="sxs-lookup"><span data-stu-id="163bc-182">AddRecoveryAndHardwareDbUsers.log</span></span>  
<span data-ttu-id="163bc-183">記錄針對金鑰復原將 web 服務授權至 MBAM 復原資料庫所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="163bc-183">Logs actions taken to authorize web services to the MBAM Recovery database for key recovery.</span></span>

<span data-ttu-id="163bc-184">**記事** 若要取得其他 MBAM 安裝記錄檔，您必須使用 msiexec 套件和/L location 選項來安裝 MBAM &lt; &gt; 。</span><span class="sxs-lookup"><span data-stu-id="163bc-184">**Note** In order to obtain additional MBAM Setup log files, you have to install MBAM by using the msiexec package and the /L &lt;location&gt; option.</span></span> <span data-ttu-id="163bc-185">在指定的位置中建立記錄檔。</span><span class="sxs-lookup"><span data-stu-id="163bc-185">Log files are created in the location specified.</span></span>

 

**<span data-ttu-id="163bc-186">MBAM 用戶端安裝記錄檔</span><span class="sxs-lookup"><span data-stu-id="163bc-186">MBAM Client Setup log files</span></span>**

<a href="" id="msi-five-random-characters--log"></a><span data-ttu-id="163bc-187">MSI <em> &lt; 5 隨機字元 &gt; </em> 記錄</span><span class="sxs-lookup"><span data-stu-id="163bc-187">MSI<em>&lt;five random characters&gt;</em>.log</span></span>  
<span data-ttu-id="163bc-188">記錄在 MBAM 用戶端安裝期間所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="163bc-188">Logs the actions taken during MBAM Client installation.</span></span>

## <a href="" id="---------mbam-database-tde-considerations"></a> <span data-ttu-id="163bc-189">MBAM 資料庫 TDE 考慮</span><span class="sxs-lookup"><span data-stu-id="163bc-189">MBAM Database TDE Considerations</span></span>


<span data-ttu-id="163bc-190">在 SQL Server 中提供的透明資料加密（TDE）功能，是一個可供裝載 MBAM 資料庫功能之資料庫實例的選擇性安裝。</span><span class="sxs-lookup"><span data-stu-id="163bc-190">The transparent data encryption (TDE) feature that is available in SQL Server is an optional installation for the database instances that will host MBAM database features.</span></span>

<span data-ttu-id="163bc-191">有了 TDE，您就可以執行即時的完整資料庫層級加密。</span><span class="sxs-lookup"><span data-stu-id="163bc-191">With TDE, you can perform real-time, full database-level encryption.</span></span> <span data-ttu-id="163bc-192">TDE 是大量加密的最佳選擇，可滿足法規遵從性或公司資料安全性標準。</span><span class="sxs-lookup"><span data-stu-id="163bc-192">TDE is the optimal choice for bulk encryption to meet regulatory compliance or corporate data security standards.</span></span> <span data-ttu-id="163bc-193">TDE 在檔層級運作，與兩個 Windows 功能類似： [加密檔案系統（EFS）] 和 [BitLocker 磁碟機加密]，這兩者也會對硬碟上的資料進行加密。</span><span class="sxs-lookup"><span data-stu-id="163bc-193">TDE works at the file level, which is similar to two Windows features: the Encrypting File System (EFS) and BitLocker Drive Encryption, both of which also encrypt data on the hard drive.</span></span> <span data-ttu-id="163bc-194">TDE 不會取代儲存格層級的加密、EFS 或 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="163bc-194">TDE does not replace cell-level encryption, EFS, or BitLocker.</span></span>

<span data-ttu-id="163bc-195">在資料庫上啟用 TDE 時，所有備份都會經過加密。</span><span class="sxs-lookup"><span data-stu-id="163bc-195">When TDE is enabled on a database, all backups are encrypted.</span></span> <span data-ttu-id="163bc-196">因此，您必須採取特殊小心，以確保用來保護資料庫加密金鑰的憑證已在資料庫備份中備份及維護。</span><span class="sxs-lookup"><span data-stu-id="163bc-196">Thus, special care must be taken to ensure that the certificate that was used to protect the database encryption key is backed up and maintained with the database backup.</span></span> <span data-ttu-id="163bc-197">如果此憑證或憑證遺失，資料將無法讀取。</span><span class="sxs-lookup"><span data-stu-id="163bc-197">If this certificate (or certificates) is lost, the data will be unreadable.</span></span> <span data-ttu-id="163bc-198">備份憑證及資料庫。</span><span class="sxs-lookup"><span data-stu-id="163bc-198">Back up the certificate along with the database.</span></span> <span data-ttu-id="163bc-199">每個證書備份都應該有兩個檔案。</span><span class="sxs-lookup"><span data-stu-id="163bc-199">Each certificate backup should have two files.</span></span> <span data-ttu-id="163bc-200">這兩個檔案應該都要封存（最好是從資料庫備份檔案以取得安全性）。</span><span class="sxs-lookup"><span data-stu-id="163bc-200">Both of these files should be archived (ideally separately from the database backup file for security).</span></span> <span data-ttu-id="163bc-201">您也可以考慮使用可擴展金鑰管理（EKM）功能（請參閱可擴展金鑰管理）來儲存及維護用於 TDE 的金鑰。</span><span class="sxs-lookup"><span data-stu-id="163bc-201">You can alternatively consider using the extensible key management (EKM) feature (see Extensible Key Management) for storage and maintenance of keys used for TDE.</span></span>

<span data-ttu-id="163bc-202">如需如何針對 MBAM 資料庫實例啟用 TDE 的範例，請參閱[評估 MBAM 2.0](evaluating-mbam-20-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="163bc-202">For an example of how to enable TDE for MBAM database instances, see [Evaluating MBAM 2.0](evaluating-mbam-20-mbam-2.md).</span></span>

<span data-ttu-id="163bc-203">如需有關 SQLServer 2008 中 TDE 的詳細資訊，請參閱[SQL Server 加密]( https://go.microsoft.com/fwlink/?LinkId=299883)。</span><span class="sxs-lookup"><span data-stu-id="163bc-203">For more information about TDE in SQLServer 2008, see [SQL Server Encryption]( https://go.microsoft.com/fwlink/?LinkId=299883).</span></span>

## <span data-ttu-id="163bc-204">相關主題</span><span class="sxs-lookup"><span data-stu-id="163bc-204">Related topics</span></span>


[<span data-ttu-id="163bc-205">MBAM 2.0 的安全性與隱私權</span><span class="sxs-lookup"><span data-stu-id="163bc-205">Security and Privacy for MBAM 2.0</span></span>](security-and-privacy-for-mbam-20-mbam-2.md)

 

 





