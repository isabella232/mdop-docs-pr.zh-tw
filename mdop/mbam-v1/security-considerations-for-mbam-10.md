---
title: MBAM 1.0 的安全性考量
description: MBAM 1.0 的安全性考量
author: dansimp
ms.assetid: 5e1c8b8c-235b-4a92-8b0b-da50dca17353
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: b06c343c8193293dde91bc7af2541f35f332d261
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811607"
---
# <span data-ttu-id="2f3b3-103">MBAM 1.0 的安全性考量</span><span class="sxs-lookup"><span data-stu-id="2f3b3-103">Security Considerations for MBAM 1.0</span></span>


<span data-ttu-id="2f3b3-104">本主題包含帳戶與群組、記錄檔案，以及 Microsoft BitLocker 管理與監控的其他安全相關考慮（MBAM）的簡短概述。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-104">This topic contains a brief overview of the accounts and groups, log files, and other security-related considerations for Microsoft BitLocker Administration and Monitoring (MBAM).</span></span> <span data-ttu-id="2f3b3-105">如需詳細資訊，請參閱本文中的連結。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-105">For more information, follow the links in this article.</span></span>

## <span data-ttu-id="2f3b3-106">一般安全性考慮</span><span class="sxs-lookup"><span data-stu-id="2f3b3-106">General security considerations</span></span>


**<span data-ttu-id="2f3b3-107">瞭解安全性風險。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-107">Understand the security risks.</span></span>** <span data-ttu-id="2f3b3-108">MBAM 最嚴重的風險是，未經授權的使用者可能會劫持其功能，讓您可以在 MBAM 用戶端重新設定 BitLocker 加密並取得 BitLocker 加密金鑰資料。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-108">The most serious risk to MBAM is that its functionality could be hijacked by an unauthorized user who could then reconfigure BitLocker encryption and gain BitLocker encryption key data on MBAM Clients.</span></span> <span data-ttu-id="2f3b3-109">不過，因拒絕服務攻擊而導致短時間內的 MBAM 功能遺失，通常不會產生災難性影響。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-109">However, the loss of MBAM functionality for a short period of time due to a denial-of-service attack would not generally have a catastrophic impact.</span></span>

<span data-ttu-id="2f3b3-110">**在物理上保護您的電腦**。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-110">**Physically secure your computers**.</span></span> <span data-ttu-id="2f3b3-111">安全性不完整，沒有實際的安全性。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-111">Security is incomplete without physical security.</span></span> <span data-ttu-id="2f3b3-112">對 MBAM 伺服器擁有物理存取權的任何人，都可能會攻擊整個用戶端基礎。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-112">Anyone with physical access to an MBAM Server could potentially attack the entire client base.</span></span> <span data-ttu-id="2f3b3-113">任何潛在的物理攻擊都必須被視為高風險，並適當地減輕問題。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-113">Any potential physical attacks must be considered high risk and mitigated appropriately.</span></span> <span data-ttu-id="2f3b3-114">MBAM 伺服器應該儲存在具有可控存取權的物理安全伺服器機房中。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-114">MBAM servers should be stored in a physically secure server room with controlled access.</span></span> <span data-ttu-id="2f3b3-115">使用作業系統鎖定電腦，或使用安全的螢幕保護裝置程式，在系統管理員沒有實際顯示的情況下，保護這些電腦的安全。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-115">Secure these computers when administrators are not physically present by having the operating system lock the computer, or by using a secured screen saver.</span></span>

<span data-ttu-id="2f3b3-116">**將最新的安全性更新套用至所有電腦**。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-116">**Apply the most recent security updates to all computers**.</span></span> <span data-ttu-id="2f3b3-117">訂閱安全性通知服務（），隨時瞭解作業系統、Microsoft SQL Server 及 MBAM 的新更新 <https://go.microsoft.com/fwlink/p/?LinkId=28819> 。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-117">Stay informed about new updates for operating systems, Microsoft SQL Server, and MBAM by subscribing to the Security Notification service (<https://go.microsoft.com/fwlink/p/?LinkId=28819>).</span></span>

<span data-ttu-id="2f3b3-118">**使用強式密碼或密碼片語**。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-118">**Use strong passwords or pass phrases**.</span></span> <span data-ttu-id="2f3b3-119">針對所有 MBAM 及 MBAM 系統管理員帳戶，請務必使用具有15個或以上字元的強式密碼。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-119">Always use strong passwords with 15 or more characters for all MBAM and MBAM administrator accounts.</span></span> <span data-ttu-id="2f3b3-120">請勿使用空白密碼。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-120">Never use blank passwords.</span></span> <span data-ttu-id="2f3b3-121">如需密碼概念的詳細資訊，請參閱 TechNet 上的「帳戶密碼及原則」白皮書 <https://go.microsoft.com/fwlink/p/?LinkId=30009> 。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-121">For more information about password concepts, see the “Account Passwords and Policies” white paper on TechNet (<https://go.microsoft.com/fwlink/p/?LinkId=30009>).</span></span>

## <span data-ttu-id="2f3b3-122">MBAM 中的帳戶和群組</span><span class="sxs-lookup"><span data-stu-id="2f3b3-122">Accounts and Groups in MBAM</span></span>


<span data-ttu-id="2f3b3-123">使用者帳戶管理的最佳做法是建立網域全域群組，並在其中新增使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-123">A best practice for user account management is to create domain global groups and add user accounts to them.</span></span> <span data-ttu-id="2f3b3-124">然後，將網域通用帳戶新增到 MBAM 伺服器上必要的 MBAM 本機群組。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-124">Then, add the domain global accounts to the necessary MBAM local groups on the MBAM Servers.</span></span>

### <span data-ttu-id="2f3b3-125">ActiveDirectoryDomainServices 群組</span><span class="sxs-lookup"><span data-stu-id="2f3b3-125">ActiveDirectoryDomainServices Groups</span></span>

<span data-ttu-id="2f3b3-126">在 MBAM 設定期間，不會自動建立群組。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-126">No groups are created automatically during MBAM Setup.</span></span> <span data-ttu-id="2f3b3-127">不過，您應該建立下列 ActiveDirectoryDomainServices 全域群組，以管理 MBAM 作業。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-127">However, you should create the following ActiveDirectoryDomainServices global groups to manage MBAM operations.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2f3b3-128">群組名稱</span><span class="sxs-lookup"><span data-stu-id="2f3b3-128">Group Name</span></span></th>
<th align="left"><span data-ttu-id="2f3b3-129">詳細資料</span><span class="sxs-lookup"><span data-stu-id="2f3b3-129">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2f3b3-130">MBAM 高級支援人員的使用者</span><span class="sxs-lookup"><span data-stu-id="2f3b3-130">MBAM Advanced Helpdesk Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="2f3b3-131">建立此群組以管理在 MBAM 設定期間建立的 MBAM 高級支援人員使用者當地群組的成員。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-131">Create this group to manage members of the MBAM Advanced Helpdesk Users local group that was created during MBAM Setup.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2f3b3-132">MBAM 合規性審核資料庫存取</span><span class="sxs-lookup"><span data-stu-id="2f3b3-132">MBAM Compliance Auditing DB Access</span></span></p></td>
<td align="left"><p><span data-ttu-id="2f3b3-133">建立此群組，以管理在 MBAM 設定期間建立的 MBAM 合規性審核資料庫存取本機群組的成員。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-133">Create this group to manage members of the MBAM Compliance Auditing DB Access local group that was created during MBAM Setup.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2f3b3-134">MBAM 硬體使用者</span><span class="sxs-lookup"><span data-stu-id="2f3b3-134">MBAM Hardware Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="2f3b3-135">建立此群組以管理在 MBAM 設定期間建立的 MBAM 硬體使用者本機群組的成員。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-135">Create this group to manage members of the MBAM Hardware Users local group that was created during MBAM Setup.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2f3b3-136">MBAM 支援人員的使用者</span><span class="sxs-lookup"><span data-stu-id="2f3b3-136">MBAM Helpdesk Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="2f3b3-137">建立此群組以管理在 MBAM 設定期間建立的 MBAM [支援的使用者] 本機群組的成員。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-137">Create this group to manage members of the MBAM Helpdesk Users local group that was created during MBAM Setup.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2f3b3-138">MBAM 恢復與硬體資料庫存取</span><span class="sxs-lookup"><span data-stu-id="2f3b3-138">MBAM Recovery and Hardware DB Access</span></span></p></td>
<td align="left"><p><span data-ttu-id="2f3b3-139">建立此群組以管理在 MBAM 設定期間建立的 MBAM 復原與硬體資料庫存取本機群組的成員。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-139">Create this group to manage members of the MBAM Recovery and Hardware DB Access local group that was created during MBAM Setup.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2f3b3-140">MBAM 報表使用者</span><span class="sxs-lookup"><span data-stu-id="2f3b3-140">MBAM Report Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="2f3b3-141">建立此群組以管理在 MBAM 設定期間建立的 MBAM 報表使用者本機群組的成員。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-141">Create this group to manage members of the MBAM Report Users local group that was created during MBAM Setup.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2f3b3-142">MBAM 系統管理員</span><span class="sxs-lookup"><span data-stu-id="2f3b3-142">MBAM System Administrators</span></span></p></td>
<td align="left"><p><span data-ttu-id="2f3b3-143">建立此群組以管理在 MBAM 設定期間建立的 MBAM 系統管理員本機群組的成員。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-143">Create this group to manage members of the MBAM System Administrators local group that was created during MBAM Setup.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2f3b3-144">BitLocker 加密免除</span><span class="sxs-lookup"><span data-stu-id="2f3b3-144">BitLocker Encryption Exemptions</span></span></p></td>
<td align="left"><p><span data-ttu-id="2f3b3-145">[建立此群組] 可管理要從其登入之電腦開始的 BitLocker 加密所免除的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-145">Create this group to manage user accounts that should be exempted from BitLocker encryption starting on computers that they log on to.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="2f3b3-146">MBAM Server 本機群組</span><span class="sxs-lookup"><span data-stu-id="2f3b3-146">MBAM Server Local Groups</span></span>

<span data-ttu-id="2f3b3-147">MBAM 安裝程式會建立本機群組以支援 MBAM 作業。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-147">MBAM Setup creates local groups to support MBAM operations.</span></span> <span data-ttu-id="2f3b3-148">您應該將 ActiveDirectoryDomainServices 全域群組新增至適當的 MBAM 本機群組，以設定 MBAM 安全性與資料存取許可權。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-148">You should add the ActiveDirectoryDomainServices Global Groups to the appropriate MBAM local groups to configure MBAM security and data access permissions.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="2f3b3-149">群組名稱</span><span class="sxs-lookup"><span data-stu-id="2f3b3-149">Group Name</span></span></th>
<th align="left"><span data-ttu-id="2f3b3-150">詳細資料</span><span class="sxs-lookup"><span data-stu-id="2f3b3-150">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2f3b3-151">MBAM 高級支援人員的使用者</span><span class="sxs-lookup"><span data-stu-id="2f3b3-151">MBAM Advanced Helpdesk Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="2f3b3-152">此群組的成員已展開存取 Microsoft BitLocker 管理和監控的支援人員功能。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-152">Members of this group have expanded access to the Helpdesk features of Microsoft BitLocker Administration and Monitoring.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2f3b3-153">MBAM 合規性審核資料庫存取</span><span class="sxs-lookup"><span data-stu-id="2f3b3-153">MBAM Compliance Auditing DB Access</span></span></p></td>
<td align="left"><p><span data-ttu-id="2f3b3-154">此群組包含可存取 MBAM 合規性審核資料庫的電腦。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-154">This group contains the machines that have access to the MBAM Compliance Auditing Database.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2f3b3-155">MBAM 硬體使用者</span><span class="sxs-lookup"><span data-stu-id="2f3b3-155">MBAM Hardware Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="2f3b3-156">此群組的成員可以存取 Microsoft BitLocker 管理和監控的一些硬體功能功能。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-156">Members of this group have access to some of the Hardware Capability features from Microsoft BitLocker Administration and Monitoring.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2f3b3-157">MBAM 支援人員的使用者</span><span class="sxs-lookup"><span data-stu-id="2f3b3-157">MBAM Helpdesk Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="2f3b3-158">此群組的成員可以存取 Microsoft BitLocker 管理和監控中的某些技術支援人員功能。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-158">Members of this group have access to some of the Helpdesk features from Microsoft BitLocker Administration and Monitoring.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2f3b3-159">MBAM 恢復與硬體資料庫存取</span><span class="sxs-lookup"><span data-stu-id="2f3b3-159">MBAM Recovery and Hardware DB Access</span></span></p></td>
<td align="left"><p><span data-ttu-id="2f3b3-160">這個群組包含可存取 MBAM 復原與硬體資料庫的電腦。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-160">This group contains the computers that have access to the MBAM Recovery and Hardware Database.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="2f3b3-161">MBAM 報表使用者</span><span class="sxs-lookup"><span data-stu-id="2f3b3-161">MBAM Report Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="2f3b3-162">此群組的成員可以存取來自 Microsoft BitLocker 管理和監視的合規性和審核報告。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-162">Members of this group have access to the Compliance and Audit reports from Microsoft BitLocker Administration and Monitoring.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="2f3b3-163">MBAM 系統管理員</span><span class="sxs-lookup"><span data-stu-id="2f3b3-163">MBAM System Administrators</span></span></p></td>
<td align="left"><p><span data-ttu-id="2f3b3-164">此群組的成員可以存取 Microsoft BitLocker 管理和監控的所有功能。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-164">Members of this group have access to all the features of Microsoft BitLocker Administration and Monitoring.</span></span></p></td>
</tr>
</tbody>
</table>

 

### <span data-ttu-id="2f3b3-165">SSRS 報告存取帳戶</span><span class="sxs-lookup"><span data-stu-id="2f3b3-165">SSRS Reports Access Account</span></span>

<span data-ttu-id="2f3b3-166">SQL Server Reporting Services （SSRS）報表服務帳戶會提供安全性內容，以執行透過 SSRS 提供的 MBAM 報告。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-166">The SQL Server Reporting Services (SSRS) Reports Service Account provides the security context to run the MBAM reports available through SSRS.</span></span> <span data-ttu-id="2f3b3-167">這個帳戶是在 MBAM 安裝期間設定。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-167">This account is configured during MBAM Setup.</span></span>

## <span data-ttu-id="2f3b3-168">MBAM 記錄檔</span><span class="sxs-lookup"><span data-stu-id="2f3b3-168">MBAM Log Files</span></span>


<span data-ttu-id="2f3b3-169">在 MBAM 設定期間，下列 MBAM 安裝記錄檔案是在安裝的使用者的% temp% 資料夾中建立</span><span class="sxs-lookup"><span data-stu-id="2f3b3-169">During MBAM Setup, the following MBAM Setup log files are created in the %temp% folder of the user who installs the</span></span>

**<span data-ttu-id="2f3b3-170">MBAM Server 安裝程式記錄檔</span><span class="sxs-lookup"><span data-stu-id="2f3b3-170">MBAM Server Setup log files</span></span>**

<a href="" id="msi-five-random-characters--log"></a><span data-ttu-id="2f3b3-171">MSI <em> &lt; 5 隨機字元 &gt; </em> 記錄</span><span class="sxs-lookup"><span data-stu-id="2f3b3-171">MSI<em>&lt;five random characters&gt;</em>.log</span></span>  
<span data-ttu-id="2f3b3-172">記錄在 MBAM 設定和 MBAM 伺服器功能安裝期間所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-172">Logs the actions taken during MBAM Setup and MBAM Server Feature installation.</span></span>

<a href="" id="installcompliancedatabase-log"></a><span data-ttu-id="2f3b3-173">InstallComplianceDatabase 記錄</span><span class="sxs-lookup"><span data-stu-id="2f3b3-173">InstallComplianceDatabase.log</span></span>  
<span data-ttu-id="2f3b3-174">記錄建立 MBAM 合規性狀態資料庫設定所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-174">Logs the actions taken to create the MBAM Compliance Status database setup.</span></span>

<a href="" id="installkeycompliancedatabase-log"></a><span data-ttu-id="2f3b3-175">InstallKeyComplianceDatabase 記錄</span><span class="sxs-lookup"><span data-stu-id="2f3b3-175">InstallKeyComplianceDatabase.log</span></span>  
<span data-ttu-id="2f3b3-176">記錄建立 MBAM 復原與硬體資料庫所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-176">Logs the actions taken to create the MBAM Recovery and Hardware database.</span></span>

<a href="" id="addhelpdeskdbauditusers-log"></a><span data-ttu-id="2f3b3-177">AddHelpDeskDbAuditUsers 記錄</span><span class="sxs-lookup"><span data-stu-id="2f3b3-177">AddHelpDeskDbAuditUsers.log</span></span>  
<span data-ttu-id="2f3b3-178">記錄在 MBAM 合規性狀態資料庫上建立 SQL Server 登入所採取的動作，以及授權支援人員的 web 服務至資料庫以取得報告。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-178">Logs the actions taken to create the SQL Server logins on the MBAM Compliance Status database and authorize helpdesk web service to the database for reports.</span></span>

<a href="" id="addhelpdeskdbusers-log"></a><span data-ttu-id="2f3b3-179">AddHelpDeskDbUsers 記錄</span><span class="sxs-lookup"><span data-stu-id="2f3b3-179">AddHelpDeskDbUsers.log</span></span>  
<span data-ttu-id="2f3b3-180">記錄針對金鑰復原授權 web 服務所採取的動作，並建立 MBAM 復原與硬體資料庫的登入。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-180">Logs the actions taken to authorize web services to database for key recovery and create logins to the MBAM Recovery and Hardware database.</span></span>

<a href="" id="addkeycompliancedbusers-log"></a><span data-ttu-id="2f3b3-181">AddKeyComplianceDbUsers 記錄</span><span class="sxs-lookup"><span data-stu-id="2f3b3-181">AddKeyComplianceDbUsers.log</span></span>  
<span data-ttu-id="2f3b3-182">記錄針對合規性報告進行授權 web 服務時所採取的動作，以 MBAM 合規性狀態資料庫。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-182">Logs the actions taken to authorize web services to MBAM Compliance Status database for compliance reporting.</span></span>

<a href="" id="addrecoveryandhardwaredbusers-log"></a><span data-ttu-id="2f3b3-183">AddRecoveryAndHardwareDbUsers 記錄</span><span class="sxs-lookup"><span data-stu-id="2f3b3-183">AddRecoveryAndHardwareDbUsers.log</span></span>  
<span data-ttu-id="2f3b3-184">記錄在授權 web 服務時所採取的動作，以 MBAM 復原及硬體資料庫，以取得金鑰復原能力。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-184">Logs the actions taken to authorize web services to MBAM Recovery and Hardware database for key recovery.</span></span>

<span data-ttu-id="2f3b3-185">**記事** 若要取得其他 MBAM 安裝記錄檔，您必須使用**msiexec**套件和 **/l** Location 選項來安裝 Microsoft BitLocker 管理和監視 &lt; &gt; 。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-185">**Note** In order to obtain additional MBAM Setup log files, you must install Microsoft BitLocker Administration and Monitoring by using the **msiexec** package and the **/l** &lt;location&gt; option.</span></span> <span data-ttu-id="2f3b3-186">在指定的位置中建立記錄檔。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-186">Log files are created in the location specified.</span></span>

 

**<span data-ttu-id="2f3b3-187">MBAM 用戶端安裝記錄檔</span><span class="sxs-lookup"><span data-stu-id="2f3b3-187">MBAM Client Setup log files</span></span>**

<a href="" id="msi-five-random-characters--log"></a><span data-ttu-id="2f3b3-188">MSI <em> &lt; 5 隨機字元 &gt; </em> 記錄</span><span class="sxs-lookup"><span data-stu-id="2f3b3-188">MSI<em>&lt;five random characters&gt;</em>.log</span></span>  
<span data-ttu-id="2f3b3-189">記錄在 MBAM 用戶端安裝期間所採取的動作。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-189">Logs the actions taken during MBAM Client installation.</span></span>

## <span data-ttu-id="2f3b3-190">MBAM 資料庫 TDE 考慮</span><span class="sxs-lookup"><span data-stu-id="2f3b3-190">MBAM Database TDE considerations</span></span>


<span data-ttu-id="2f3b3-191">SQL Server 2008 中提供的透明資料加密（TDE）功能，是將裝載 MBAM 資料庫功能之資料庫實例所需的安裝必要。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-191">The Transparent Data Encryption (TDE) feature available in SQL Server 2008 is a required installation prerequisite for the database instances that will host MBAM database features.</span></span>

<span data-ttu-id="2f3b3-192">有了 TDE，您就可以執行即時的完整資料庫層級加密。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-192">With TDE, you can perform real-time, full database-level encryption.</span></span> <span data-ttu-id="2f3b3-193">TDE 是一種非常適合的大量加密選項，以符合法規規範或公司資料安全標準。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-193">TDE is a well-suited choice for bulk encryption to meet regulatory compliance or corporate data security standards.</span></span> <span data-ttu-id="2f3b3-194">TDE 在檔層級運作，與兩個 Windows 功能類似： [加密檔案系統（EFS）] 和 [BitLocker 磁碟機加密]，這兩者也會對硬碟上的資料進行加密。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-194">TDE works at the file level, which is similar to two Windows features: the Encrypting File System (EFS) and BitLocker Drive Encryption, both of which also encrypt data on the hard drive.</span></span> <span data-ttu-id="2f3b3-195">TDE 不會取代儲存格層級的加密、EFS 或 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-195">TDE does not replace cell-level encryption, EFS, or BitLocker.</span></span>

<span data-ttu-id="2f3b3-196">在資料庫上啟用 TDE 時，所有備份都會經過加密。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-196">When TDE is enabled on a database, all backups are encrypted.</span></span> <span data-ttu-id="2f3b3-197">因此，您必須採取特殊小心，以確保用來保護資料庫加密金鑰（DEK）的憑證已在資料庫備份中備份及維護。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-197">Thus, special care must be taken to ensure that the certificate that was used to protect the Database Encryption Key (DEK) is backed up and maintained with the database backup.</span></span> <span data-ttu-id="2f3b3-198">如果沒有憑證，資料將無法讀取。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-198">Without a certificate, the data will be unreadable.</span></span> <span data-ttu-id="2f3b3-199">備份憑證及資料庫。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-199">Back up the certificate along with the database.</span></span> <span data-ttu-id="2f3b3-200">每個證書備份都應該有兩個檔案;這兩個檔案都應該封存。最好是將它們與資料庫備份檔案分開，以取得安全性。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-200">Each certificate backup should have two files; both of these files should be archived .It is best to archive them separately from the database backup file for security.</span></span>

<span data-ttu-id="2f3b3-201">如需如何針對 MBAM 資料庫實例啟用 TDE 的範例，請參閱[評估 MBAM 1.0](evaluating-mbam-10.md)。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-201">For an example of how to enable TDE for MBAM database instances, see [Evaluating MBAM 1.0](evaluating-mbam-10.md).</span></span>

<span data-ttu-id="2f3b3-202">如需有關 SQLServer 2008 中 TDE 的詳細資訊，請參閱[SQL Server 2008 Enterprise Edition 中的資料庫加密](https://go.microsoft.com/fwlink/?LinkId=269703)。</span><span class="sxs-lookup"><span data-stu-id="2f3b3-202">For more information about TDE in SQLServer 2008, see [Database Encryption in SQL Server 2008 Enterprise Edition](https://go.microsoft.com/fwlink/?LinkId=269703).</span></span>

## <span data-ttu-id="2f3b3-203">相關主題</span><span class="sxs-lookup"><span data-stu-id="2f3b3-203">Related topics</span></span>


[<span data-ttu-id="2f3b3-204">MBAM 1.0 的安全性與隱私權</span><span class="sxs-lookup"><span data-stu-id="2f3b3-204">Security and Privacy for MBAM 1.0</span></span>](security-and-privacy-for-mbam-10.md)

 

 





