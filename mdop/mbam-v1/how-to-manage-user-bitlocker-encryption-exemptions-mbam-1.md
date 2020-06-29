---
title: 如何管理使用者 BitLocker 加密豁免
description: 如何管理使用者 BitLocker 加密豁免
author: dansimp
ms.assetid: 48d69721-504f-4524-8a04-b9ce213ac9b4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 8c3d70558a65c3288174413d6c36cc9c77bc9eaa
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800225"
---
# <span data-ttu-id="f2eb4-103">如何管理使用者 BitLocker 加密豁免</span><span class="sxs-lookup"><span data-stu-id="f2eb4-103">How to Manage User BitLocker Encryption Exemptions</span></span>


<span data-ttu-id="f2eb4-104">Microsoft BitLocker 管理和監控（MBAM）可透過 exempting 不需要或不想要磁片磁碟機加密的使用者來管理 BitLocker 保護。</span><span class="sxs-lookup"><span data-stu-id="f2eb4-104">Microsoft BitLocker Administration and Monitoring (MBAM) can be used to manage BitLocker protection by exempting users who do not need or want their drives encrypted.</span></span>

<span data-ttu-id="f2eb4-105">若要將使用者從 BitLocker 保護中免除，組織必須先建立一個支援此類免除的基礎結構。</span><span class="sxs-lookup"><span data-stu-id="f2eb4-105">To exempt users from BitLocker protection, an organization must first create an infrastructure to support such exemptions.</span></span> <span data-ttu-id="f2eb4-106">支援基礎結構可能包含連絡人電話號碼、網頁或郵寄地址來要求豁免。</span><span class="sxs-lookup"><span data-stu-id="f2eb4-106">The supporting infrastructure might include a contact telephone number, webpage, or mailing address to request exemption.</span></span> <span data-ttu-id="f2eb4-107">此外，任何免除使用者也必須新增到專為免除的使用者所建立之群群組原則的安全性群組中。</span><span class="sxs-lookup"><span data-stu-id="f2eb4-107">Also, any exempt user will have to be added to a security group for Group Policy created specifically for exempted users.</span></span> <span data-ttu-id="f2eb4-108">當此安全性群組的成員登入電腦時，使用者群組原則會顯示使用者已從 BitLocker 保護中免除。</span><span class="sxs-lookup"><span data-stu-id="f2eb4-108">When members of this security group log on to a computer, the user Group Policy shows that the user is exempted from BitLocker protection.</span></span> <span data-ttu-id="f2eb4-109">使用者原則會覆寫電腦原則，電腦將保持不受 BitLocker 加密的免除。</span><span class="sxs-lookup"><span data-stu-id="f2eb4-109">The user policy overwrites the computer policy, and the computer will remain exempt from BitLocker encryption.</span></span>

<span data-ttu-id="f2eb4-110">**記事** 如果電腦已受 BitLocker 保護，使用者豁免原則就不會有任何作用。</span><span class="sxs-lookup"><span data-stu-id="f2eb4-110">**Note** If the computer is already BitLocker-protected, the user exemption policy has no effect.</span></span>

 

<span data-ttu-id="f2eb4-111">下表顯示如何根據免除的設定來套用 BitLocker 保護。</span><span class="sxs-lookup"><span data-stu-id="f2eb4-111">The following table shows how BitLocker protection is applied based on how exemptions are set.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f2eb4-112">使用者狀態</span><span class="sxs-lookup"><span data-stu-id="f2eb4-112">User Status</span></span></th>
<th align="left"><span data-ttu-id="f2eb4-113">未免除的電腦</span><span class="sxs-lookup"><span data-stu-id="f2eb4-113">Computer Not Exempt</span></span></th>
<th align="left"><span data-ttu-id="f2eb4-114">電腦豁免</span><span class="sxs-lookup"><span data-stu-id="f2eb4-114">Computer Exempt</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="f2eb4-115">使用者不受豁免</span><span class="sxs-lookup"><span data-stu-id="f2eb4-115">User not exempt</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="f2eb4-116">在電腦上強制執行 BitLocker 保護。</span><span class="sxs-lookup"><span data-stu-id="f2eb4-116">BitLocker protection is enforced on the computer.</span></span></p></td>
<td align="left"><p><span data-ttu-id="f2eb4-117">在電腦上未強制執行 BitLocker 保護。</span><span class="sxs-lookup"><span data-stu-id="f2eb4-117">BitLocker protection is not enforced on the computer.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="f2eb4-118">使用者豁免</span><span class="sxs-lookup"><span data-stu-id="f2eb4-118">User exempt</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="f2eb4-119">在電腦上未強制執行 BitLocker 保護。</span><span class="sxs-lookup"><span data-stu-id="f2eb4-119">BitLocker protection is not enforced on the computer.</span></span></p></td>
<td align="left"><p><span data-ttu-id="f2eb4-120">在電腦上未強制執行 BitLocker 保護。</span><span class="sxs-lookup"><span data-stu-id="f2eb4-120">BitLocker protection is not enforced on the computer.</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="f2eb4-121">從 BitLocker 加密免除使用者</span><span class="sxs-lookup"><span data-stu-id="f2eb4-121">To exempt a user from BitLocker Encryption</span></span>**

1.  <span data-ttu-id="f2eb4-122">建立將用來從 BitLocker 加密管理使用者免除的 ActiveDirectoryDomainServices 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="f2eb4-122">Create an ActiveDirectoryDomainServices security group that will be used to manage user exemptions from BitLocker encryption.</span></span>

2.  <span data-ttu-id="f2eb4-123">使用 MBAM 群組原則範本來建立群組原則物件設定。</span><span class="sxs-lookup"><span data-stu-id="f2eb4-123">Create a Group Policy Object setting by using the MBAM Group Policy template.</span></span> <span data-ttu-id="f2eb4-124">將群組原則物件與您在上一個步驟中建立的 Active Directory 群組建立關聯。</span><span class="sxs-lookup"><span data-stu-id="f2eb4-124">Associate the Group Policy Object with the Active Directory group that you created in the previous step.</span></span> <span data-ttu-id="f2eb4-125">如需讓使用者從 BitLocker 加密中要求豁免所需原則設定的詳細資訊，請參閱[規劃 MBAM 1.0 群組原則需求](planning-for-mbam-10-group-policy-requirements.md)中的 [設定使用者豁免原則] 區段。</span><span class="sxs-lookup"><span data-stu-id="f2eb4-125">For more information about the necessary policy settings to enable users to request exemption from BitLocker encryption, see the Configure User Exemption Policy section in [Planning for MBAM 1.0 Group Policy Requirements](planning-for-mbam-10-group-policy-requirements.md).</span></span>

3.  <span data-ttu-id="f2eb4-126">在為 BitLocker 免除的使用者建立安全性群組之後，請將要求豁免的使用者名稱新增到此群組中。</span><span class="sxs-lookup"><span data-stu-id="f2eb4-126">After creating a security group for BitLocker-exempted users, add to this group the names of the users who are requesting exemption.</span></span> <span data-ttu-id="f2eb4-127">當使用者登入由 BitLocker 控制的電腦時，MBAM 用戶端會檢查使用者豁免原則設定，並根據使用者是否為 BitLocker 豁免安全性群組的一部分來暫停保護。</span><span class="sxs-lookup"><span data-stu-id="f2eb4-127">When a user logs on to a computer controlled by BitLocker, the MBAM client will check the User Exemption Policy setting and will suspend protection based on whether the user is part of the BitLocker exemption security group.</span></span>

    <span data-ttu-id="f2eb4-128">**記事** 共用電腦案例需要關於使用者例外的特殊考慮。</span><span class="sxs-lookup"><span data-stu-id="f2eb4-128">**Note** Shared computer scenarios require special consideration regarding user exemption.</span></span> <span data-ttu-id="f2eb4-129">如果非豁免使用者登入與豁免使用者共用的電腦，電腦可能會經過加密。</span><span class="sxs-lookup"><span data-stu-id="f2eb4-129">If a non-exempt user logs on to a computer shared with an exempt user, the computer may be encrypted.</span></span>

     

**<span data-ttu-id="f2eb4-130">讓使用者從 BitLocker 加密要求豁免</span><span class="sxs-lookup"><span data-stu-id="f2eb4-130">To enable users to request exemption from BitLocker Encryption</span></span>**

1.  <span data-ttu-id="f2eb4-131">在您以 usingwith MBAM 原則範本設定使用者豁免原則之後，使用者就可以透過 MBAM 用戶端要求 BitLocker 保護的例外情況。</span><span class="sxs-lookup"><span data-stu-id="f2eb4-131">After you have configured user-exemption policies by usingwith the MBAM Policy template, a user can request exemption from BitLocker protection through the MBAM client.</span></span>

2.  <span data-ttu-id="f2eb4-132">當使用者登入 MBAM 硬體相容性清單中標示為**相容**的電腦時，系統會向使用者顯示電腦即將加密的通知。</span><span class="sxs-lookup"><span data-stu-id="f2eb4-132">When a user logs on to a computer that is marked as **Compatible** in the MBAM Hardware Compatibility list, the system presents the user with a notification that the computer is going to be encrypted.</span></span> <span data-ttu-id="f2eb4-133">使用者可以選取 [**要求免除**]，**然後選取 [\*\*\*\*開始**] 以接受 BitLocker 加密。</span><span class="sxs-lookup"><span data-stu-id="f2eb4-133">The user can select **Request Exemption** and postpone the encryption by selecting **Later**, or select **Start** to accept the BitLocker encryption.</span></span>

    <span data-ttu-id="f2eb4-134">**記事** 選取 [**要求免除**] 會延遲 BitLocker 防護，直到使用者豁免原則中設定的最大時間為止。</span><span class="sxs-lookup"><span data-stu-id="f2eb4-134">**Note** Selecting **Request Exemption** will postpone the BitLocker protection until the maximum time set in the User Exemption Policy.</span></span>

     

3.  <span data-ttu-id="f2eb4-135">當使用者選取 [**要求豁免**] 時，系統會通知使用者與組織的 BitLocker 管理群組。</span><span class="sxs-lookup"><span data-stu-id="f2eb4-135">When a user selects **Request Exemption**, the user is notified to contact the organization's BitLocker administration group.</span></span> <span data-ttu-id="f2eb4-136">視設定使用者例外原則的設定方式而定，使用者提供下列一或多個連絡人方法：</span><span class="sxs-lookup"><span data-stu-id="f2eb4-136">Depending on how the Configure User Exemption Policy is configured, users are provided with one or more of the following contact methods:</span></span>

    -   <span data-ttu-id="f2eb4-137">電話號碼</span><span class="sxs-lookup"><span data-stu-id="f2eb4-137">Phone Number</span></span>

    -   <span data-ttu-id="f2eb4-138">網頁 URL</span><span class="sxs-lookup"><span data-stu-id="f2eb4-138">Webpage URL</span></span>

    -   <span data-ttu-id="f2eb4-139">郵寄地址</span><span class="sxs-lookup"><span data-stu-id="f2eb4-139">Mailing Address</span></span>

    <span data-ttu-id="f2eb4-140">在提交要求之後，MBAM 管理員可以決定是否適當地將使用者新增至 BitLocker 免除 Active Directory 群組。</span><span class="sxs-lookup"><span data-stu-id="f2eb4-140">After submittal of the request, the MBAM Administrator can decide if it is appropriate to add the user to the BitLocker Exemption Active Directory group.</span></span>

    <span data-ttu-id="f2eb4-141">**記事** 當使用者免除原則的延遲時間限制已過期之後，使用者就不會看到要求免除加密原則的選項。</span><span class="sxs-lookup"><span data-stu-id="f2eb4-141">**Note** Once the postpone time limit from the User Exemption Policy has expired, users will not see the option to request exemption to the encryption policy.</span></span> <span data-ttu-id="f2eb4-142">此時，使用者必須直接與 MBAM 管理員聯繫，才能從 BitLocker 保護接收例外。</span><span class="sxs-lookup"><span data-stu-id="f2eb4-142">At this point, users must contact the MBAM administrator directly in order to receive exemption from BitLocker Protection.</span></span>

     

## <span data-ttu-id="f2eb4-143">相關主題</span><span class="sxs-lookup"><span data-stu-id="f2eb4-143">Related topics</span></span>


[<span data-ttu-id="f2eb4-144">管理 MBAM 1.0 功能</span><span class="sxs-lookup"><span data-stu-id="f2eb4-144">Administering MBAM 1.0 Features</span></span>](administering-mbam-10-features.md)

 

 





