---
title: 如何管理使用者 BitLocker 加密豁免
description: 如何管理使用者 BitLocker 加密豁免
author: dansimp
ms.assetid: f582ab82-5bb5-4cd3-ad7c-483240533cf9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c4224a0fb6d905c2362659efe7cf05e16756f7c0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811967"
---
# <span data-ttu-id="03fe0-103">如何管理使用者 BitLocker 加密豁免</span><span class="sxs-lookup"><span data-stu-id="03fe0-103">How to Manage User BitLocker Encryption Exemptions</span></span>


<span data-ttu-id="03fe0-104">Microsoft BitLocker 管理和監控（MBAM）可讓您從 BitLocker 磁片磁碟機加密需求中免除使用者。</span><span class="sxs-lookup"><span data-stu-id="03fe0-104">Microsoft BitLocker Administration and Monitoring (MBAM) enables you to exempt users from BitLocker Drive Encryption requirements.</span></span>

<span data-ttu-id="03fe0-105">若要將使用者從 BitLocker 保護中免除，您必須：</span><span class="sxs-lookup"><span data-stu-id="03fe0-105">To exempt users from BitLocker protection, you have to:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="03fe0-106">工作</span><span class="sxs-lookup"><span data-stu-id="03fe0-106">Task</span></span></th>
<th align="left"><span data-ttu-id="03fe0-107">詳細資料</span><span class="sxs-lookup"><span data-stu-id="03fe0-107">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="03fe0-108">建立基礎結構以支援免除的使用者。</span><span class="sxs-lookup"><span data-stu-id="03fe0-108">Create an infrastructure to support exempted users.</span></span></p></td>
<td align="left"><p><span data-ttu-id="03fe0-109">此基礎結構的範例包括提供使用者的電話號碼、網頁或郵寄地址，讓他們可以用來要求豁免。</span><span class="sxs-lookup"><span data-stu-id="03fe0-109">Examples of this infrastructure include providing users with a contact telephone number, webpage, or mailing address that they can use to request an exemption.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="03fe0-110">針對專門針對免除的使用者設定的群組原則物件，將免除的使用者新增到安全性群組。</span><span class="sxs-lookup"><span data-stu-id="03fe0-110">Add the exempted user to a security group for a Group Policy Object that is configured specifically for exempted users.</span></span></p></td>
<td align="left"><p><span data-ttu-id="03fe0-111">當這個安全性群組的成員登入電腦時，使用者的群組原則設定會從 BitLocker 保護 exempts 使用者。</span><span class="sxs-lookup"><span data-stu-id="03fe0-111">When members of this security group sign in to a computer, the user’s Group Policy setting exempts the user from BitLocker protection.</span></span> <span data-ttu-id="03fe0-112">使用者的 [群組原則] 設定會覆寫電腦原則，電腦將保持不受 BitLocker 加密的免除。</span><span class="sxs-lookup"><span data-stu-id="03fe0-112">The user’s Group Policy setting overwrites the computer policy, and the computer will remain exempt from BitLocker encryption.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="03fe0-113">注意</span><span class="sxs-lookup"><span data-stu-id="03fe0-113">Note</span></span></strong><br/><p><span data-ttu-id="03fe0-114">如果電腦已受 BitLocker 保護且已免除使用者，MBAM 不會制定加密原則。</span><span class="sxs-lookup"><span data-stu-id="03fe0-114">MBAM does not enact the encryption policy if the computer is already BitLocker-protected and the user is exempted.</span></span> <span data-ttu-id="03fe0-115">不過，如果不是由加密原則免除的另一個使用者登入電腦，就會進行加密。</span><span class="sxs-lookup"><span data-stu-id="03fe0-115">However, if another user who is not exempt from the encryption policy signs in to the computer, encryption will take place.</span></span></p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



<span data-ttu-id="03fe0-116">下列步驟說明當使用者從 MBAM 用戶端或您組織所使用的任何程式來要求 BitLocker 磁碟機加密免除程式的例外情況時，會發生什麼情況。</span><span class="sxs-lookup"><span data-stu-id="03fe0-116">The following steps describe what occurs when end users request an exemption from the BitLocker Drive Encryption exemption process through the MBAM Client or through whatever process your organization uses.</span></span> <span data-ttu-id="03fe0-117">您必須設定 MBAM 組原則設定，以允許使用者從 BitLocker 磁片磁碟機加密要求免除。</span><span class="sxs-lookup"><span data-stu-id="03fe0-117">You must configure MBAM Group Policy settings to allow end users to request an exemption from BitLocker Drive Encryption.</span></span>

1.  <span data-ttu-id="03fe0-118">當使用者登入需要加密的電腦時，會收到其電腦即將加密的通知。</span><span class="sxs-lookup"><span data-stu-id="03fe0-118">When end users sign in to a computer that is required to be encrypted, they receive a notification that their computer is going to be encrypted.</span></span> <span data-ttu-id="03fe0-119">您可以選取 [**延遲**]，選取 [**要求免除**]，然後選取 [**開始加密**] 來接受 BitLocker 加密。</span><span class="sxs-lookup"><span data-stu-id="03fe0-119">They can select **Request Exemption** and postpone the encryption by selecting **Postpone**, or they can select **Start Encryption** to accept the BitLocker encryption.</span></span>

    **<span data-ttu-id="03fe0-120">注意</span><span class="sxs-lookup"><span data-stu-id="03fe0-120">Note</span></span>**  
    <span data-ttu-id="03fe0-121">選取 [**要求免除**]：推遲 BitLocker 防護，直到使用者豁免原則中設定的最大時間為止。</span><span class="sxs-lookup"><span data-stu-id="03fe0-121">Selecting **Request Exemption** postpones the BitLocker protection until the maximum time that is set in the User Exemption Policy.</span></span>



2.  <span data-ttu-id="03fe0-122">如果使用者選取 [**要求免除**]，他們會收到通知，告知他們與組織的 BitLocker 管理群組。</span><span class="sxs-lookup"><span data-stu-id="03fe0-122">If end users select **Request Exemption**, they receive a notification telling them to contact the organization’s BitLocker administration group.</span></span> <span data-ttu-id="03fe0-123">視設定**使用者例外原則**的設定方式而定，使用者提供下列一或多個連絡人方法：</span><span class="sxs-lookup"><span data-stu-id="03fe0-123">Depending on how the **Configure User Exemption Policy** is configured, users are provided with one or more of the following contact methods:</span></span>

    -   <span data-ttu-id="03fe0-124">電話號碼</span><span class="sxs-lookup"><span data-stu-id="03fe0-124">Phone number</span></span>

    -   <span data-ttu-id="03fe0-125">網頁 URL</span><span class="sxs-lookup"><span data-stu-id="03fe0-125">Webpage URL</span></span>

    -   <span data-ttu-id="03fe0-126">郵寄地址</span><span class="sxs-lookup"><span data-stu-id="03fe0-126">Mailing address</span></span>

3.  <span data-ttu-id="03fe0-127">在收到免除要求之後，MBAM 系統管理員會決定是否要將使用者新增到 BitLocker 免除 Active Directory 網域服務（AD DS）群組。</span><span class="sxs-lookup"><span data-stu-id="03fe0-127">After the exemption request is received, the MBAM administrator decides whether to add the user to the BitLocker Exemption Active Directory Domain Services (AD DS) group.</span></span>

4.  <span data-ttu-id="03fe0-128">在最終使用者提交免除要求之後，MBAM 用戶端會將使用者報告為「暫時免除」。</span><span class="sxs-lookup"><span data-stu-id="03fe0-128">After an end user submits an exemption request, the MBAM Client reports the user as “Temporarily exempt.”</span></span> <span data-ttu-id="03fe0-129">用戶端接著會等到指定的天數（IT 系統管理員設定的天數），才能再次檢查電腦的相容性。</span><span class="sxs-lookup"><span data-stu-id="03fe0-129">The Client then waits a specified number of days, which IT administrators configure, before it checks the computer’s compliance again.</span></span> <span data-ttu-id="03fe0-130">如果 MBAM 管理員拒絕免除要求，則會停用 [免除要求] 選項，這會防止使用者再次要求例外。</span><span class="sxs-lookup"><span data-stu-id="03fe0-130">If the MBAM administrator rejects the exemption request, the exemption request option is deactivated, which prevents the user from requesting the exemption again.</span></span>

<span data-ttu-id="03fe0-131">Microsoft BitLocker 管理和監控（MBAM）可讓您從 BitLocker 磁片磁碟機加密需求中免除使用者。</span><span class="sxs-lookup"><span data-stu-id="03fe0-131">Microsoft BitLocker Administration and Monitoring (MBAM) enables you to exempt users from BitLocker Drive Encryption requirements.</span></span>

<span data-ttu-id="03fe0-132">若要將使用者從 BitLocker 保護中免除，您必須：</span><span class="sxs-lookup"><span data-stu-id="03fe0-132">To exempt users from BitLocker protection, you have to:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="03fe0-133">工作</span><span class="sxs-lookup"><span data-stu-id="03fe0-133">Task</span></span></th>
<th align="left"><span data-ttu-id="03fe0-134">詳細資料</span><span class="sxs-lookup"><span data-stu-id="03fe0-134">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="03fe0-135">建立基礎結構以支援免除的使用者。</span><span class="sxs-lookup"><span data-stu-id="03fe0-135">Create an infrastructure to support exempted users.</span></span></p></td>
<td align="left"><p><span data-ttu-id="03fe0-136">此基礎結構的範例包括提供使用者的電話號碼、網頁或郵寄地址，讓他們可以用來要求豁免。</span><span class="sxs-lookup"><span data-stu-id="03fe0-136">Examples of this infrastructure include providing users with a contact telephone number, webpage, or mailing address that they can use to request an exemption.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="03fe0-137">針對專門針對免除的使用者設定的群組原則物件，將免除的使用者新增到安全性群組。</span><span class="sxs-lookup"><span data-stu-id="03fe0-137">Add the exempted user to a security group for a Group Policy Object that is configured specifically for exempted users.</span></span></p></td>
<td align="left"><p><span data-ttu-id="03fe0-138">當這個安全性群組的成員登入電腦時，使用者的群組原則設定會從 BitLocker 保護 exempts 使用者。</span><span class="sxs-lookup"><span data-stu-id="03fe0-138">When members of this security group sign in to a computer, the user’s Group Policy setting exempts the user from BitLocker protection.</span></span> <span data-ttu-id="03fe0-139">使用者的 [群組原則] 設定會覆寫電腦原則，電腦將保持不受 BitLocker 加密的免除。</span><span class="sxs-lookup"><span data-stu-id="03fe0-139">The user’s Group Policy setting overwrites the computer policy, and the computer will remain exempt from BitLocker encryption.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="03fe0-140">注意</span><span class="sxs-lookup"><span data-stu-id="03fe0-140">Note</span></span></strong><br/><p><span data-ttu-id="03fe0-141">如果電腦已受 BitLocker 保護，使用者豁免原則就不會有任何作用。</span><span class="sxs-lookup"><span data-stu-id="03fe0-141">If the computer is already BitLocker-protected, the User Exemption Policy has no effect.</span></span> <span data-ttu-id="03fe0-142">此外，如果其他使用者登入的電腦未從加密原則中免除，就會進行加密。</span><span class="sxs-lookup"><span data-stu-id="03fe0-142">In addition, if another user signs in to a computer that is not exempt from the encryption policy, encryption will take place.</span></span></p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



<span data-ttu-id="03fe0-143">下列步驟說明當使用者從 MBAM 用戶端或您組織所使用的任何程式來要求 BitLocker 磁碟機加密免除程式的例外情況時，會發生什麼情況。</span><span class="sxs-lookup"><span data-stu-id="03fe0-143">The following steps describe what occurs when end users request an exemption from the BitLocker Drive Encryption exemption process through the MBAM Client or through whatever process your organization uses.</span></span> <span data-ttu-id="03fe0-144">您必須設定 MBAM 組原則設定，以允許使用者從 BitLocker 磁片磁碟機加密要求免除。</span><span class="sxs-lookup"><span data-stu-id="03fe0-144">You must configure MBAM Group Policy settings to allow end users to request an exemption from BitLocker Drive Encryption.</span></span>

1.  <span data-ttu-id="03fe0-145">當使用者登入需要加密的電腦時，會收到其電腦即將加密的通知。</span><span class="sxs-lookup"><span data-stu-id="03fe0-145">When end users sign in to a computer that is required to be encrypted, they receive a notification that their computer is going to be encrypted.</span></span> <span data-ttu-id="03fe0-146">您可以選取 [**延遲**]，選取 [**要求免除**]，然後選取 [**開始加密**] 來接受 BitLocker 加密。</span><span class="sxs-lookup"><span data-stu-id="03fe0-146">They can select **Request Exemption** and postpone the encryption by selecting **Postpone**, or they can select **Start Encryption** to accept the BitLocker encryption.</span></span>

    **<span data-ttu-id="03fe0-147">注意</span><span class="sxs-lookup"><span data-stu-id="03fe0-147">Note</span></span>**  
    <span data-ttu-id="03fe0-148">選取 [**要求免除**]：推遲 BitLocker 防護，直到使用者豁免原則中設定的最大時間為止。</span><span class="sxs-lookup"><span data-stu-id="03fe0-148">Selecting **Request Exemption** postpones the BitLocker protection until the maximum time that is set in the User Exemption Policy.</span></span>



2.  <span data-ttu-id="03fe0-149">如果使用者選取 [**要求免除**]，他們會收到通知，告知他們與組織的 BitLocker 管理群組。</span><span class="sxs-lookup"><span data-stu-id="03fe0-149">If end users select **Request Exemption**, they receive a notification telling them to contact the organization’s BitLocker administration group.</span></span> <span data-ttu-id="03fe0-150">視設定**使用者例外原則**的設定方式而定，使用者提供下列一或多個連絡人方法：</span><span class="sxs-lookup"><span data-stu-id="03fe0-150">Depending on how the **Configure User Exemption Policy** is configured, users are provided with one or more of the following contact methods:</span></span>

    -   <span data-ttu-id="03fe0-151">電話號碼</span><span class="sxs-lookup"><span data-stu-id="03fe0-151">Phone number</span></span>

    -   <span data-ttu-id="03fe0-152">網頁 URL</span><span class="sxs-lookup"><span data-stu-id="03fe0-152">Webpage URL</span></span>

    -   <span data-ttu-id="03fe0-153">郵寄地址</span><span class="sxs-lookup"><span data-stu-id="03fe0-153">Mailing address</span></span>

3.  <span data-ttu-id="03fe0-154">在收到免除要求之後，MBAM 系統管理員會決定是否要將使用者新增到 BitLocker 免除 Active Directory 網域服務（AD DS）群組。</span><span class="sxs-lookup"><span data-stu-id="03fe0-154">After the exemption request is received, the MBAM administrator decides whether to add the user to the BitLocker Exemption Active Directory Domain Services (AD DS) group.</span></span>

4.  <span data-ttu-id="03fe0-155">在最終使用者提交免除要求之後，MBAM 用戶端會將使用者報告為「暫時免除」。</span><span class="sxs-lookup"><span data-stu-id="03fe0-155">After an end user submits an exemption request, the MBAM Client reports the user as “Temporarily exempt.”</span></span> <span data-ttu-id="03fe0-156">用戶端接著會等到指定的天數（IT 系統管理員設定的天數），才能再次檢查電腦的相容性。</span><span class="sxs-lookup"><span data-stu-id="03fe0-156">The Client then waits a specified number of days, which IT administrators configure, before it checks the computer’s compliance again.</span></span> <span data-ttu-id="03fe0-157">如果 MBAM 管理員拒絕免除要求，則會停用 [免除要求] 選項，這會防止使用者再次要求例外。</span><span class="sxs-lookup"><span data-stu-id="03fe0-157">If the MBAM administrator rejects the exemption request, the exemption request option is deactivated, which prevents the user from requesting the exemption again.</span></span>

**<span data-ttu-id="03fe0-158">從 BitLocker 磁碟機加密免除使用者</span><span class="sxs-lookup"><span data-stu-id="03fe0-158">To exempt a user from BitLocker Drive Encryption</span></span>**

1.  <span data-ttu-id="03fe0-159">建立將用來從 BitLocker 加密需求管理使用者免除的 AD DS 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="03fe0-159">Create an AD DS security group that will be used to manage user exemptions from BitLocker encryption requirements.</span></span>

2.  <span data-ttu-id="03fe0-160">使用 Microsoft BitLocker 管理和監視群群組原則範本來建立群組原則物件。</span><span class="sxs-lookup"><span data-stu-id="03fe0-160">Create a Group Policy Object by using the Microsoft BitLocker Administration and Monitoring Group Policy Templates.</span></span>

3.  <span data-ttu-id="03fe0-161">將 [群組原則] 物件與您在上一個步驟中建立的 AD DS 群組建立關聯。</span><span class="sxs-lookup"><span data-stu-id="03fe0-161">Associate the Group Policy Object with the AD DS group that you created in the previous step.</span></span> <span data-ttu-id="03fe0-162">免除使用者的原則設定是位於： UserConfiguration 系統**UserConfiguration** &gt; **管理範本** &gt; **Windows 元件** &gt; **MDOP MBAM （BitLocker Management）**。</span><span class="sxs-lookup"><span data-stu-id="03fe0-162">The policy settings to exempt users are located at: **UserConfiguration** &gt; **Administrative Templates** &gt; **Windows Components** &gt; **MDOP MBAM (BitLocker Management)**.</span></span>

4.  <span data-ttu-id="03fe0-163">針對您針對 BitLocker 免除的使用者所建立的安全性群組，請新增要求豁免之使用者的名稱。</span><span class="sxs-lookup"><span data-stu-id="03fe0-163">To the security group you created for BitLocker exempted users, add the names of the users who are requesting an exemption.</span></span>

    <span data-ttu-id="03fe0-164">當使用者登入由 BitLocker 控制的電腦時，MBAM 用戶端會檢查使用者豁免原則設定。</span><span class="sxs-lookup"><span data-stu-id="03fe0-164">When a user signs in to a computer controlled by BitLocker, the MBAM Client checks the User Exemption Policy setting.</span></span> <span data-ttu-id="03fe0-165">如果電腦已加密，就不會暫停 BitLocker 保護。</span><span class="sxs-lookup"><span data-stu-id="03fe0-165">If the computer is already encrypted, BitLocker protection is not suspended.</span></span> <span data-ttu-id="03fe0-166">如果電腦未加密，MBAM 不會提示使用者進行加密。</span><span class="sxs-lookup"><span data-stu-id="03fe0-166">If the computer is not encrypted, MBAM does not prompt the user to encrypt.</span></span>

    **<span data-ttu-id="03fe0-167">重要</span><span class="sxs-lookup"><span data-stu-id="03fe0-167">Important</span></span>**  
    <span data-ttu-id="03fe0-168">如果您使用的是 BitLocker 使用者免除，共用電腦案例需要特殊考慮。</span><span class="sxs-lookup"><span data-stu-id="03fe0-168">Shared computer scenarios require special consideration when you are using BitLocker user exemptions.</span></span> <span data-ttu-id="03fe0-169">如果非豁免使用者登入與豁免使用者共用的電腦，電腦可能會經過加密。</span><span class="sxs-lookup"><span data-stu-id="03fe0-169">If a non-exempt user signs in to a computer that is shared with an exempt user, the computer may be encrypted.</span></span>




## <span data-ttu-id="03fe0-170">相關主題</span><span class="sxs-lookup"><span data-stu-id="03fe0-170">Related topics</span></span>


[<span data-ttu-id="03fe0-171">管理 MBAM 2.5 功能</span><span class="sxs-lookup"><span data-stu-id="03fe0-171">Administering MBAM 2.5 Features</span></span>](administering-mbam-25-features.md)

[<span data-ttu-id="03fe0-172">MBAM 2.5 群組原則需求規劃</span><span class="sxs-lookup"><span data-stu-id="03fe0-172">Planning for MBAM 2.5 Group Policy Requirements</span></span>](planning-for-mbam-25-group-policy-requirements.md)




## <span data-ttu-id="03fe0-173">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="03fe0-173">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="03fe0-174">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="03fe0-174">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="03fe0-175">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="03fe0-175">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>




