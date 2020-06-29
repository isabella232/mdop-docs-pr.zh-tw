---
title: MBAM 2.5 群組與帳戶規劃
description: MBAM 2.5 群組與帳戶規劃
author: dansimp
ms.assetid: 73bb9fe5-5900-4b6f-b271-ade62991fca1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 11/02/2016
ms.openlocfilehash: 3431c3602685a4f96cb4c1333700107ba9c38b96
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811373"
---
# <span data-ttu-id="b8f58-103">MBAM 2.5 群組與帳戶規劃</span><span class="sxs-lookup"><span data-stu-id="b8f58-103">Planning for MBAM 2.5 Groups and Accounts</span></span>


<span data-ttu-id="b8f58-104">本主題列出您必須在 Active Directory 網域服務（AD DS）中建立的角色和帳戶，以提供 Microsoft BitLocker 管理與監控（MBAM）資料庫、報表及 web 應用程式的安全性與存取權。</span><span class="sxs-lookup"><span data-stu-id="b8f58-104">This topic lists the roles and accounts that you must create in Active Directory Domain Services (AD DS) to provide security and access rights for the Microsoft BitLocker Administration and Monitoring (MBAM) databases, reports, and web applications.</span></span> <span data-ttu-id="b8f58-105">針對每個角色和帳戶，提供 MBAM 伺服器設定精靈中的對應欄位。</span><span class="sxs-lookup"><span data-stu-id="b8f58-105">For each role and account, the corresponding field in the MBAM Server Configuration wizard is provided.</span></span> <span data-ttu-id="b8f58-106">如需與這些帳戶相對應的 Windows PowerShell Cmdlet 和參數清單，請參閱[使用 Windows PowerShell 設定 MBAM 2.5 伺服器功能](configuring-mbam-25-server-features-by-using-windows-powershell.md#bkmk-reqd-posh-accts)。</span><span class="sxs-lookup"><span data-stu-id="b8f58-106">For a list of Windows PowerShell cmdlets and parameters that correspond to these accounts, see [Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md#bkmk-reqd-posh-accts).</span></span>

**<span data-ttu-id="b8f58-107">注意</span><span class="sxs-lookup"><span data-stu-id="b8f58-107">Note</span></span>**  
<span data-ttu-id="b8f58-108">MBAM 不支援使用受管理的服務帳戶。</span><span class="sxs-lookup"><span data-stu-id="b8f58-108">MBAM does not support the use of managed service accounts.</span></span>



## <span data-ttu-id="b8f58-109">資料庫帳戶</span><span class="sxs-lookup"><span data-stu-id="b8f58-109">Database accounts</span></span>


<span data-ttu-id="b8f58-110">針對合規性和審核資料庫以及恢復資料庫建立下列帳戶。</span><span class="sxs-lookup"><span data-stu-id="b8f58-110">Create the following accounts for the Compliance and Audit Database and the Recovery Database.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b8f58-111">帳戶名稱和用途</span><span class="sxs-lookup"><span data-stu-id="b8f58-111">Account name and purpose</span></span></th>
<th align="left"><span data-ttu-id="b8f58-112">帳戶類型</span><span class="sxs-lookup"><span data-stu-id="b8f58-112">Account type</span></span></th>
<th align="left"><span data-ttu-id="b8f58-113">與此帳戶對應的 [MBAM 伺服器設定] 嚮導欄位</span><span class="sxs-lookup"><span data-stu-id="b8f58-113">MBAM Server Configuration wizard field that corresponds to this account</span></span></th>
<th align="left"><span data-ttu-id="b8f58-114">對應至此帳戶的 [MBAM 伺服器設定] 嚮導欄位的描述</span><span class="sxs-lookup"><span data-stu-id="b8f58-114">Description of the MBAM Server Configuration wizard field that corresponds to this account</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b8f58-115">合規性與審計資料庫及復原資料庫已讀/寫使用者或群組的報告</span><span class="sxs-lookup"><span data-stu-id="b8f58-115">Compliance and Audit Database and Recovery Database read/write user or group for reports</span></span></p></td>
<td align="left"><p><span data-ttu-id="b8f58-116">使用者或群組</span><span class="sxs-lookup"><span data-stu-id="b8f58-116">User or Group</span></span></p></td>
<td align="left"><p><span data-ttu-id="b8f58-117">讀/寫存取網域使用者或群組</span><span class="sxs-lookup"><span data-stu-id="b8f58-117">Read/write access domain user or group</span></span></p></td>
<td align="left"><p><span data-ttu-id="b8f58-118">具備合規性和審核資料庫及復原資料庫之讀/寫存取權的網域使用者或群組，可讓 web 應用程式存取這些資料庫中的資料和報表。</span><span class="sxs-lookup"><span data-stu-id="b8f58-118">Domain user or group that has read/write access to the Compliance and Audit Database and the Recovery Database to enable the web applications to access the data and reports in these databases.</span></span></p>
<p><span data-ttu-id="b8f58-119">如果您在此欄位中輸入使用者名稱，它必須與 <strong> </strong> [ <strong> 設定 web 應用程式] 頁面上的 [web 服務應用程式池網域帳戶] 欄位中的值相同 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="b8f58-119">If you enter a user name in this field, it must be the same value as the value in the <strong>Web service application pool domain account</strong> field on the <strong>Configure Web Applications</strong> page.</span></span></p>
<p><span data-ttu-id="b8f58-120">如果您在此欄位中輸入組名，則 [ <strong> 設定 Web 應用程式] 頁面上的 [Web 服務應用程式群組網域帳戶] 欄位中的值 </strong> <strong> </strong> 必須是您在這個欄位中輸入之群組的成員。</span><span class="sxs-lookup"><span data-stu-id="b8f58-120">If you enter a group name in this field, the value in the <strong>Web service application pool domain account</strong> field on the <strong>Configure Web Applications</strong> page must be a member of the group you enter in this field.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b8f58-121">合規性和審核資料庫唯讀使用者或群組的報表</span><span class="sxs-lookup"><span data-stu-id="b8f58-121">Compliance and Audit Database read-only user or group for reports</span></span></p></td>
<td align="left"><p><span data-ttu-id="b8f58-122">使用者或群組</span><span class="sxs-lookup"><span data-stu-id="b8f58-122">User or Group</span></span></p></td>
<td align="left"><p><span data-ttu-id="b8f58-123">唯讀存取網域使用者或群組</span><span class="sxs-lookup"><span data-stu-id="b8f58-123">Read-only access domain user or group</span></span></p></td>
<td align="left"><p><span data-ttu-id="b8f58-124">將對合規性和審核資料庫擁有唯讀存取權的使用者或群組的名稱，以讓報告能夠存取此資料庫中的合規性和審核資料。</span><span class="sxs-lookup"><span data-stu-id="b8f58-124">Name of the user or group that will have read-only access to the Compliance and Audit Database to enable the reports to access the compliance and audit data in this database.</span></span></p>
<p><span data-ttu-id="b8f58-125">如果您在此欄位中輸入使用者名稱，該使用者必須是您在 <strong> </strong> [設定報告] 頁面上的 [合規性和審核資料庫網域帳戶] 欄位中所指定的使用者 <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="b8f58-125">If you enter a user name in this field, it must be the same user as the one you specify in the <strong>Compliance and Audit Database domain account</strong> field on the <strong>Configure Reports</strong> page.</span></span></p>
<p><span data-ttu-id="b8f58-126">如果您在此欄位中輸入組名，您在 <strong> [設定報告] 頁面上的 [合規性與審計資料庫網域帳戶] 欄位中指定的值， </strong> <strong> </strong> 必須是您在此欄位中指定之群組的成員。</span><span class="sxs-lookup"><span data-stu-id="b8f58-126">If you enter a group name in this field, the value that you specify in the <strong>Compliance and Audit Database domain account</strong> field on the <strong>Configure Reports</strong> page must be a member of the group that you specify in this field.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="b8f58-127">報告帳戶</span><span class="sxs-lookup"><span data-stu-id="b8f58-127">Reporting accounts</span></span>


<span data-ttu-id="b8f58-128">針對 [報告] 功能建立下列帳戶。</span><span class="sxs-lookup"><span data-stu-id="b8f58-128">Create the following accounts for the Reports feature.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b8f58-129">帳戶名稱/用途</span><span class="sxs-lookup"><span data-stu-id="b8f58-129">Account name/purpose</span></span></th>
<th align="left"><span data-ttu-id="b8f58-130">帳戶類型</span><span class="sxs-lookup"><span data-stu-id="b8f58-130">Account type</span></span></th>
<th align="left"><span data-ttu-id="b8f58-131">與此帳戶對應的 [MBAM 伺服器設定] 嚮導欄位</span><span class="sxs-lookup"><span data-stu-id="b8f58-131">MBAM Server Configuration wizard field that corresponds to this account</span></span></th>
<th align="left"><span data-ttu-id="b8f58-132">對應至此帳戶的 [MBAM 伺服器設定] 嚮導欄位的描述</span><span class="sxs-lookup"><span data-stu-id="b8f58-132">Description of the MBAM Server Configuration wizard field that corresponds to this account</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b8f58-133">報告唯讀網域存取群組</span><span class="sxs-lookup"><span data-stu-id="b8f58-133">Reports read-only domain access group</span></span></p></td>
<td align="left"><p><span data-ttu-id="b8f58-134">群組</span><span class="sxs-lookup"><span data-stu-id="b8f58-134">Group</span></span></p></td>
<td align="left"><p><span data-ttu-id="b8f58-135">報告角色網域群組</span><span class="sxs-lookup"><span data-stu-id="b8f58-135">Reporting role domain group</span></span></p></td>
<td align="left"><p><span data-ttu-id="b8f58-136">指定擁有 [管理及監視] 網站上的報告唯讀存取權的網域使用者群組。</span><span class="sxs-lookup"><span data-stu-id="b8f58-136">Specifies the domain user group that has read-only access to the reports in the Administration and Monitoring Website.</span></span> <span data-ttu-id="b8f58-137">您指定的群組必須是您在啟用 web 應用程式時為 [報告唯讀存取] 群組參數指定的群組。</span><span class="sxs-lookup"><span data-stu-id="b8f58-137">The group you specify must be the same group you specified for the Reports Read Only Access Group parameter when the web apps are enabled.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b8f58-138">合規性與審計資料庫網域使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="b8f58-138">Compliance and Audit Database domain user account</span></span></p></td>
<td align="left"><p><span data-ttu-id="b8f58-139">使用者</span><span class="sxs-lookup"><span data-stu-id="b8f58-139">User</span></span></p></td>
<td align="left"><p><span data-ttu-id="b8f58-140">合規性與審計資料庫網域帳戶</span><span class="sxs-lookup"><span data-stu-id="b8f58-140">Compliance and Audit Database domain account</span></span></p></td>
<td align="left"><p><span data-ttu-id="b8f58-141">本機 SQL Server Reporting Services 實例用來存取合規性和審核資料庫的網域使用者帳戶和密碼。</span><span class="sxs-lookup"><span data-stu-id="b8f58-141">Domain user account and password that the local SQL Server Reporting Services instance uses to access the Compliance and Audit Database.</span></span> <span data-ttu-id="b8f58-142">這個帳戶必須 <strong> 以批次許可權登入 </strong> 至 SQL Server Reporting Services 伺服器。</span><span class="sxs-lookup"><span data-stu-id="b8f58-142">This account requires <strong>Log On as Batch</strong> rights to the SQL Server Reporting Services server.</span></span></p>
<p><span data-ttu-id="b8f58-143">如果您在 <strong> [設定資料庫] 頁面上的 [唯讀存取網域使用者] 或 [群組] 欄位中輸入的值 </strong> <strong> </strong> 是使用者名稱，則您必須在這個欄位中輸入相同的值。</span><span class="sxs-lookup"><span data-stu-id="b8f58-143">If the value you enter in the <strong>Read-only access domain user or group</strong> field on the <strong>Configure Databases</strong> page is a user name, you must enter that same value in this field.</span></span></p>
<p><span data-ttu-id="b8f58-144">如果您在 <strong> [設定資料庫] 頁面上的 [唯讀存取網域使用者] 或 [群組] 欄位中輸入的值 </strong> <strong> </strong> 是群組名稱，則您在這個欄位中輸入的值必須是該群組的成員。</span><span class="sxs-lookup"><span data-stu-id="b8f58-144">If the value you enter in the <strong>Read-only access domain user or group</strong> field on the <strong>Configure Databases</strong> page is a group name, the value that you enter in this field must be a member of that group.</span></span></p>
<p><span data-ttu-id="b8f58-145">將此帳戶的密碼設定為永不過期。</span><span class="sxs-lookup"><span data-stu-id="b8f58-145">Configure the password for this account to never expire.</span></span> <span data-ttu-id="b8f58-146">使用者帳戶應該能夠存取 MBAM [報告使用者] 群組提供的所有資料。</span><span class="sxs-lookup"><span data-stu-id="b8f58-146">The user account should be able to access all data that is available to the MBAM Reports Users group.</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-helpdesk-roles"></a><span data-ttu-id="b8f58-147">管理和監控網站（技術支援）帳戶</span><span class="sxs-lookup"><span data-stu-id="b8f58-147">Administration and Monitoring Website (Help Desk) accounts</span></span>


<span data-ttu-id="b8f58-148">針對 [管理及監視] 網站建立下列帳戶。</span><span class="sxs-lookup"><span data-stu-id="b8f58-148">Create the following accounts for the Administration and Monitoring Website.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="b8f58-149">帳戶名稱/用途</span><span class="sxs-lookup"><span data-stu-id="b8f58-149">Account name/purpose</span></span></th>
<th align="left"><span data-ttu-id="b8f58-150">帳戶類型</span><span class="sxs-lookup"><span data-stu-id="b8f58-150">Account type</span></span></th>
<th align="left"><span data-ttu-id="b8f58-151">與此帳戶對應的 [MBAM 伺服器設定] 嚮導欄位</span><span class="sxs-lookup"><span data-stu-id="b8f58-151">MBAM Server Configuration wizard field that corresponds to this account</span></span></th>
<th align="left"><span data-ttu-id="b8f58-152">對應至此帳戶的 [MBAM 伺服器設定] 嚮導欄位的描述</span><span class="sxs-lookup"><span data-stu-id="b8f58-152">Description of the MBAM Server Configuration wizard field that corresponds to this account</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b8f58-153">Web 服務應用程式池網域帳戶</span><span class="sxs-lookup"><span data-stu-id="b8f58-153">Web service application pool domain account</span></span></p></td>
<td align="left"><p><span data-ttu-id="b8f58-154">使用者</span><span class="sxs-lookup"><span data-stu-id="b8f58-154">User</span></span></p></td>
<td align="left"><p><span data-ttu-id="b8f58-155">Web 服務應用程式池網域帳戶</span><span class="sxs-lookup"><span data-stu-id="b8f58-155">Web service application pool domain account</span></span></p></td>
<td align="left"><p><span data-ttu-id="b8f58-156">要供 web 應用程式的應用程式池使用的網域使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="b8f58-156">Domain user account to be used by the application pool for the web applications.</span></span></p>
<p><span data-ttu-id="b8f58-157">如果您在 <strong> [設定資料庫] 頁面上的 [讀/寫存取權網域使用者或群組] 欄位中輸入使用者名稱 </strong> <strong> </strong> ，您必須在這個欄位中輸入相同的值。</span><span class="sxs-lookup"><span data-stu-id="b8f58-157">If you enter a user name in the <strong>Read/write access domain user or group</strong> field on the <strong>Configure Databases</strong> page, you must enter that same value in this field.</span></span></p>
<p><span data-ttu-id="b8f58-158">如果您在 <strong> [設定資料庫] 頁面上的 [讀/寫存取網域] 或 [群組] 欄位中輸入組名 </strong> <strong> </strong> ，您在這個欄位中輸入的值必須是該群組的成員。</span><span class="sxs-lookup"><span data-stu-id="b8f58-158">If you enter a group name in the <strong>Read/write access domain user or group</strong> field on the <strong>Configure Databases</strong> page, the value you enter in this field must be a member of that group.</span></span></p>
<p><span data-ttu-id="b8f58-159">如果您沒有指定認證，則會使用為先前啟用的任何 web 應用程式所指定的認證。</span><span class="sxs-lookup"><span data-stu-id="b8f58-159">If you do not specify credentials, the credentials that were specified for any previously enabled web application will be used.</span></span> <span data-ttu-id="b8f58-160">所有 web 應用程式都必須使用相同的應用程式池認證。</span><span class="sxs-lookup"><span data-stu-id="b8f58-160">All web applications must use the same application pool credentials.</span></span> <span data-ttu-id="b8f58-161">如果您針對不同的 web 應用程式指定不同的認證，則會使用最近指定的值。</span><span class="sxs-lookup"><span data-stu-id="b8f58-161">If you specify different credentials for different web applications, the most recently specified value will be used.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="b8f58-162">重要</span><span class="sxs-lookup"><span data-stu-id="b8f58-162">Important</span></span></strong><br/><p><span data-ttu-id="b8f58-163">若要提高安全性，請將認證中指定的帳號設定為擁有有限的使用者權限。</span><span class="sxs-lookup"><span data-stu-id="b8f58-163">For improved security, set the account that is specified in the credentials to have limited user rights.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b8f58-164">MBAM 高級支援人員的使用者存取群組</span><span class="sxs-lookup"><span data-stu-id="b8f58-164">MBAM Advanced Helpdesk Users access group</span></span></p></td>
<td align="left"><p><span data-ttu-id="b8f58-165">群組</span><span class="sxs-lookup"><span data-stu-id="b8f58-165">Group</span></span></p></td>
<td align="left"><p><span data-ttu-id="b8f58-166">MBAM 高級支援人員的使用者</span><span class="sxs-lookup"><span data-stu-id="b8f58-166">MBAM Advanced Helpdesk Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="b8f58-167">網域使用者群組，其成員可以存取 [管理] 和 [監視] 網站的所有恢復區域。</span><span class="sxs-lookup"><span data-stu-id="b8f58-167">Domain user group whose members have access to all recovery areas of the Administration and Monitoring Website.</span></span> <span data-ttu-id="b8f58-168">擁有此角色的使用者在協助使用者復原其磁碟機時，只需要輸入復原金鑰，而不是最終使用者的網域和使用者名稱。</span><span class="sxs-lookup"><span data-stu-id="b8f58-168">Users who have this role have to enter only the recovery key, and not the end user’s domain and user name, when helping end users recover their drives.</span></span> <span data-ttu-id="b8f58-169">如果使用者是 MBAM [支援人員] 群組和 MBAM [高級服務台使用者] 群組的成員，MBAM [高級支援人員] 群組許可權會覆寫 MBAM [服務台] 群組的許可權。</span><span class="sxs-lookup"><span data-stu-id="b8f58-169">If a user is a member of both the MBAM Helpdesk Users group and the MBAM Advanced Helpdesk Users group, the MBAM Advanced Helpdesk Users group permissions override the MBAM Helpdesk Group permissions.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b8f58-170">MBAM 支援人員的使用者存取群組</span><span class="sxs-lookup"><span data-stu-id="b8f58-170">MBAM Helpdesk Users access group</span></span></p></td>
<td align="left"><p><span data-ttu-id="b8f58-171">群組</span><span class="sxs-lookup"><span data-stu-id="b8f58-171">Group</span></span></p></td>
<td align="left"><p><span data-ttu-id="b8f58-172">MBAM 支援人員的使用者</span><span class="sxs-lookup"><span data-stu-id="b8f58-172">MBAM Helpdesk Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="b8f58-173">網域使用者群組，其成員可以存取 MBAM 管理和監控網站的 [管理 TPM] 和 [磁碟機恢復] 區域。</span><span class="sxs-lookup"><span data-stu-id="b8f58-173">Domain user group whose members have access to the Manage TPM and Drive Recovery areas of the MBAM Administration and Monitoring Website.</span></span> <span data-ttu-id="b8f58-174">擁有此角色的人員在使用任一選項時，都必須填入所有欄位，包括最終使用者的網域和帳戶名稱。</span><span class="sxs-lookup"><span data-stu-id="b8f58-174">Individuals who have this role must fill-in all fields, including the end-user’s domain and account name, when they use either option.</span></span></p>
<p><span data-ttu-id="b8f58-175">如果使用者是 MBAM [支援人員] 群組和 MBAM [高級服務台使用者] 群組的成員，MBAM [高級支援人員] 群組許可權會覆寫 MBAM [服務台] 群組的許可權。</span><span class="sxs-lookup"><span data-stu-id="b8f58-175">If a user is a member of both the MBAM Helpdesk Users group and the MBAM Advanced Helpdesk Users group, the MBAM Advanced Helpdesk Users group permissions override the MBAM Helpdesk Group permissions.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="b8f58-176">MBAM 報表使用者存取群組</span><span class="sxs-lookup"><span data-stu-id="b8f58-176">MBAM Report Users access group</span></span></p></td>
<td align="left"><p><span data-ttu-id="b8f58-177">群組</span><span class="sxs-lookup"><span data-stu-id="b8f58-177">Group</span></span></p></td>
<td align="left"><p><span data-ttu-id="b8f58-178">MBAM 報表使用者</span><span class="sxs-lookup"><span data-stu-id="b8f58-178">MBAM Report Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="b8f58-179">其成員對 [管理] 和 [監視] 網站的 [報表] 區域中的報表擁有唯讀存取權的網域使用者群組。</span><span class="sxs-lookup"><span data-stu-id="b8f58-179">Domain user group whose members have read-only access to the reports in the Reports area of the Administration and Monitoring Website.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="b8f58-180">MBAM 資料移轉使用者群組</span><span class="sxs-lookup"><span data-stu-id="b8f58-180">MBAM Data Migration User Group</span></span></p></td>
<td align="left"><p><span data-ttu-id="b8f58-181">群組</span><span class="sxs-lookup"><span data-stu-id="b8f58-181">Group</span></span></p></td>
<td align="left"><p><span data-ttu-id="b8f58-182">MBAM 資料移轉使用者</span><span class="sxs-lookup"><span data-stu-id="b8f58-182">MBAM Data Migration Users</span></span></p></td>
<td align="left"><p><span data-ttu-id="b8f58-183">其成員具有在 MBAM 伺服器上執行的 MBAM 復原與硬體服務，擁有將資料寫入 MBAM 之許可權的選用網域使用者群組。</span><span class="sxs-lookup"><span data-stu-id="b8f58-183">Optional domain user group whose members have permissions to write data to MBAM by using the MBAM Recovery and Hardware Service running on the MBAM server.</span></span> <span data-ttu-id="b8f58-184">這個帳戶通常與 Write Mbam \* Cmdlet 搭配使用，以將復原及 TPM 資料從 Active Directory 寫入 MBAM 資料庫。</span><span class="sxs-lookup"><span data-stu-id="b8f58-184">This account is generally used with the Write-Mbam\* cmdlets to write recovery and TPM data from Active Directory into the MBAM database.</span></span></p>
<p><span data-ttu-id="b8f58-185">如需詳細資訊，請參閱 <a href="mbam-25-security-considerations.md" data-raw-source="[MBAM 2.5 Security Considerations](mbam-25-security-considerations.md)"> MBAM 2.5 安全性考慮 </a> 。</span><span class="sxs-lookup"><span data-stu-id="b8f58-185">For more information, see <a href="mbam-25-security-considerations.md" data-raw-source="[MBAM 2.5 Security Considerations](mbam-25-security-considerations.md)">MBAM 2.5 Security Considerations</a>.</span></span></p></td>
</tr>
</tbody>
</table>




## <span data-ttu-id="b8f58-186">相關主題</span><span class="sxs-lookup"><span data-stu-id="b8f58-186">Related topics</span></span>


[<span data-ttu-id="b8f58-187">MBAM 2.5 的環境準備</span><span class="sxs-lookup"><span data-stu-id="b8f58-187">Preparing your Environment for MBAM 2.5</span></span>](preparing-your-environment-for-mbam-25.md)

[<span data-ttu-id="b8f58-188">MBAM 2.5 部署必要條件</span><span class="sxs-lookup"><span data-stu-id="b8f58-188">MBAM 2.5 Deployment Prerequisites</span></span>](mbam-25-deployment-prerequisites.md)



## <span data-ttu-id="b8f58-189">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="b8f58-189">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="b8f58-190">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="b8f58-190">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="b8f58-191">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="b8f58-191">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





