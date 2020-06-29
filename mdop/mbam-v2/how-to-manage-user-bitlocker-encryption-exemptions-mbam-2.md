---
title: 如何管理使用者 BitLocker 加密豁免
description: 如何管理使用者 BitLocker 加密豁免
author: dansimp
ms.assetid: 1bfd9d66-6a9a-4d0e-b54a-e5a6627f5ada
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4d5530701fd208d42dc1f6774fac11ee9ca2036b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810935"
---
# <span data-ttu-id="d9374-103">如何管理使用者 BitLocker 加密豁免</span><span class="sxs-lookup"><span data-stu-id="d9374-103">How to Manage User BitLocker Encryption Exemptions</span></span>


<span data-ttu-id="d9374-104">如果使用者不需要或想要將其磁碟機加密，Microsoft BitLocker 管理和監控（MBAM）可以用來管理 BitLocker 保護。</span><span class="sxs-lookup"><span data-stu-id="d9374-104">Microsoft BitLocker Administration and Monitoring (MBAM) can be used to manage BitLocker protection by exempting users if there are users who do not need or want their drives encrypted.</span></span>

<span data-ttu-id="d9374-105">若要將使用者從 BitLocker 保護中免除，組織必須建立支援免除的使用者的基礎結構，例如給予使用者使用的連絡人電話號碼、網頁或郵寄地址來要求豁免。</span><span class="sxs-lookup"><span data-stu-id="d9374-105">To exempt users from BitLocker protection, an organization will have to create an infrastructure to support exempted users, such as giving the user a contact telephone number, webpage, or mailing address to use to request an exemption.</span></span> <span data-ttu-id="d9374-106">此外，豁免使用者必須新增到專為免除使用者建立之群組原則物件的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="d9374-106">Also, an exempt user will have to be added to a security group for a Group Policy Object that was created specifically for exempted users.</span></span> <span data-ttu-id="d9374-107">當這個安全性群組的成員登入電腦時，使用者的 [群組原則] 設定會顯示使用者已從 BitLocker 保護中免除。</span><span class="sxs-lookup"><span data-stu-id="d9374-107">When members of this security group log on to a computer, the user’s Group Policy setting shows that the user is exempted from BitLocker protection.</span></span> <span data-ttu-id="d9374-108">使用者的 [群組原則] 設定會覆寫電腦原則，電腦將保持不受 BitLocker 加密的免除。</span><span class="sxs-lookup"><span data-stu-id="d9374-108">The user’s Group Policy setting overwrites the computer policy, and the computer will remain exempt from BitLocker encryption.</span></span>

<span data-ttu-id="d9374-109">**記事** 如果電腦已受 BitLocker 保護，使用者豁免原則就不會有任何作用。</span><span class="sxs-lookup"><span data-stu-id="d9374-109">**Note** If the computer is already BitLocker-protected, the user exemption policy has no effect.</span></span>

 

<span data-ttu-id="d9374-110">下表顯示如何根據免除的設定來套用 BitLocker 保護。</span><span class="sxs-lookup"><span data-stu-id="d9374-110">The following table shows how BitLocker protection is applied based on how exemptions are set.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d9374-111">使用者狀態</span><span class="sxs-lookup"><span data-stu-id="d9374-111">User Status</span></span></th>
<th align="left"><span data-ttu-id="d9374-112">未免除的電腦</span><span class="sxs-lookup"><span data-stu-id="d9374-112">Computer Not Exempt</span></span></th>
<th align="left"><span data-ttu-id="d9374-113">電腦豁免</span><span class="sxs-lookup"><span data-stu-id="d9374-113">Computer Exempt</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong><span data-ttu-id="d9374-114">使用者不受豁免</span><span class="sxs-lookup"><span data-stu-id="d9374-114">User not exempt</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="d9374-115">在電腦上強制執行 BitLocker 保護</span><span class="sxs-lookup"><span data-stu-id="d9374-115">BitLocker protection is enforced on computer</span></span></p></td>
<td align="left"><p><span data-ttu-id="d9374-116">在電腦上未強制執行 BitLocker 保護</span><span class="sxs-lookup"><span data-stu-id="d9374-116">BitLocker protection is not enforced on computer</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong><span data-ttu-id="d9374-117">使用者豁免</span><span class="sxs-lookup"><span data-stu-id="d9374-117">User exempt</span></span></strong></p></td>
<td align="left"><p><span data-ttu-id="d9374-118">在電腦上未強制執行 BitLocker 保護</span><span class="sxs-lookup"><span data-stu-id="d9374-118">BitLocker protection is not enforced on computer</span></span></p></td>
<td align="left"><p><span data-ttu-id="d9374-119">在電腦上未強制執行 BitLocker 保護</span><span class="sxs-lookup"><span data-stu-id="d9374-119">BitLocker protection is not enforced on computer</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="d9374-120">從 BitLocker 加密免除使用者</span><span class="sxs-lookup"><span data-stu-id="d9374-120">To exempt a user from BitLocker encryption</span></span>**

1.  <span data-ttu-id="d9374-121">建立將用來從 BitLocker 加密需求管理使用者免除的 ActiveDirectoryDomainServices 安全性群組。</span><span class="sxs-lookup"><span data-stu-id="d9374-121">Create an ActiveDirectoryDomainServices security group that will be used to manage user exemptions from BitLocker encryption requirements.</span></span>

2.  <span data-ttu-id="d9374-122">使用 Microsoft BitLocker 管理和監視群群組原則範本建立群組原則物件設定，並將它與您在上一個步驟中建立的 Active Directory 群組建立關聯。</span><span class="sxs-lookup"><span data-stu-id="d9374-122">Create a Group Policy Object setting by using the Microsoft BitLocker Administration and Monitoring Group Policy template and associate it with the Active Directory group that you created in the previous step.</span></span> <span data-ttu-id="d9374-123">您可以在**UserConfiguration\\Administrative Templates\\Windows COMPONENTS\\MDOP MBAM （BitLocker Management）** 下找到免除使用者的原則設定。</span><span class="sxs-lookup"><span data-stu-id="d9374-123">The policy settings to exempt users can be found under **UserConfiguration\\Administrative Templates\\Windows Components\\MDOP MBAM (BitLocker Management)**.</span></span>

3.  <span data-ttu-id="d9374-124">在為 BitLocker 免除的使用者建立安全性群組之後，請將要求豁免的使用者名稱新增到此群組中。</span><span class="sxs-lookup"><span data-stu-id="d9374-124">After creating a security group for BitLocker-exempted users, add to this group the names of the users who are requesting an exemption.</span></span> <span data-ttu-id="d9374-125">當使用者登入 BitLocker 所控制的電腦時，MBAM 用戶端將會檢查使用者豁免原則設定，並根據使用者是否為 BitLocker 豁免安全性群組的一部分來暫停保護。</span><span class="sxs-lookup"><span data-stu-id="d9374-125">When users log on to a computer controlled by BitLocker, the MBAM client will check the User Exemption Policy setting and will suspend protection based on whether the user is part of the BitLocker exemption security group.</span></span>

    <span data-ttu-id="d9374-126">**重要** 在使用使用者例外狀況時，共用電腦案例需要特殊考慮。</span><span class="sxs-lookup"><span data-stu-id="d9374-126">**Important** Shared computer scenarios require special consideration when using user exemptions.</span></span> <span data-ttu-id="d9374-127">如果非豁免使用者登入與豁免使用者共用的電腦，電腦可能會經過加密。</span><span class="sxs-lookup"><span data-stu-id="d9374-127">If a non-exempt user logs on to a computer shared with an exempt user, the computer may be encrypted.</span></span>

     

**<span data-ttu-id="d9374-128">讓使用者從 BitLocker 加密要求免除</span><span class="sxs-lookup"><span data-stu-id="d9374-128">To enable users to request an exemption from BitLocker encryption</span></span>**

1.  <span data-ttu-id="d9374-129">如果您已使用 MBAM 原則範本設定使用者豁免原則，使用者可以透過 MBAM 用戶端要求 BitLocker 保護的免除。</span><span class="sxs-lookup"><span data-stu-id="d9374-129">If you have configured user exemption policies by using the MBAM policy template, a user can request an exemption from BitLocker protection through the MBAM client.</span></span>

2.  <span data-ttu-id="d9374-130">當使用者登入需要加密的電腦時，他們會收到一則通知，告知其電腦即將加密。</span><span class="sxs-lookup"><span data-stu-id="d9374-130">When users log on to a computer that is required to be encrypted, they receive a notification that their computer is going to be encrypted.</span></span> <span data-ttu-id="d9374-131">他們可以選取 [**要求免除**]，**然後選取 [\*\*\*\*開始**] 以接受 BitLocker 加密。</span><span class="sxs-lookup"><span data-stu-id="d9374-131">They can select **Request Exemption** and postpone the encryption by selecting **Later**, or select **Start** to accept the BitLocker encryption.</span></span>

    <span data-ttu-id="d9374-132">**記事** 選取 [**要求免除**]：推遲 BitLocker 防護，直到使用者豁免原則中設定的最大時間為止。</span><span class="sxs-lookup"><span data-stu-id="d9374-132">**Note** Selecting **Request Exemption** postpones the BitLocker protection until the maximum time that is set in the User Exemption Policy.</span></span>

     

3.  <span data-ttu-id="d9374-133">如果使用者選取 [**要求免除**]，他們會收到通知，告知他們與您組織的 BitLocker 管理群組。</span><span class="sxs-lookup"><span data-stu-id="d9374-133">If users select **Request Exemption**, they receive a notification telling them to contact your organization’s BitLocker administration group.</span></span> <span data-ttu-id="d9374-134">視設定使用者例外原則的設定方式而定，使用者提供下列一或多個連絡人方法：</span><span class="sxs-lookup"><span data-stu-id="d9374-134">Depending on how the Configure User Exemption Policy is configured, users are provided with one or more of the following contact methods:</span></span>

    -   <span data-ttu-id="d9374-135">電話號碼</span><span class="sxs-lookup"><span data-stu-id="d9374-135">Phone Number</span></span>

    -   <span data-ttu-id="d9374-136">網頁 URL</span><span class="sxs-lookup"><span data-stu-id="d9374-136">Webpage URL</span></span>

    -   <span data-ttu-id="d9374-137">郵寄地址</span><span class="sxs-lookup"><span data-stu-id="d9374-137">Mailing Address</span></span>

    <span data-ttu-id="d9374-138">在收到免除要求之後，MBAM 系統管理員可以決定是否要將使用者新增到 BitLocker 豁免 Active Directory 群組。</span><span class="sxs-lookup"><span data-stu-id="d9374-138">After the exemption request is received, the MBAM Administrator can take decide if it is appropriate to add the user to the BitLocker Exemption Active Directory group.</span></span>

    <span data-ttu-id="d9374-139">**記事** 使用者提交免除要求之後，MBAM 代理就會將使用者報告為「暫時免除」，然後等待可設定的天數，才能再次檢查電腦的合規性。</span><span class="sxs-lookup"><span data-stu-id="d9374-139">**Note** Once a user submits an exemption request, the MBAM agent reports the user as “temporarily exempt” and then waits a configurable number of days before it checks the computer’s compliance again.</span></span> <span data-ttu-id="d9374-140">如果 MBAM 管理員拒絕免除要求，則會停用 [免除要求] 選項，這會讓使用者無法再次要求例外。</span><span class="sxs-lookup"><span data-stu-id="d9374-140">If the MBAM administrator rejects the exemption request, the exemption request option is deactivated, which prevents the user from being able to request the exemption again.</span></span>

     

## <span data-ttu-id="d9374-141">相關主題</span><span class="sxs-lookup"><span data-stu-id="d9374-141">Related topics</span></span>


[<span data-ttu-id="d9374-142">管理 MBAM 2.0 功能</span><span class="sxs-lookup"><span data-stu-id="d9374-142">Administering MBAM 2.0 Features</span></span>](administering-mbam-20-features-mbam-2.md)

 

 





