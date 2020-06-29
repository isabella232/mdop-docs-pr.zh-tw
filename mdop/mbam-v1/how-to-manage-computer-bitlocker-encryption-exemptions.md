---
title: 如何管理電腦 BitLocker 加密豁免
description: 如何管理電腦 BitLocker 加密豁免
author: dansimp
ms.assetid: d4400a0d-b36b-4cf5-a294-1f53ec47f9ee
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 51b93061468508900eaee7fce8a7827e2db61d19
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811300"
---
# <span data-ttu-id="b1bef-103">如何管理電腦 BitLocker 加密豁免</span><span class="sxs-lookup"><span data-stu-id="b1bef-103">How to Manage Computer BitLocker Encryption Exemptions</span></span>


<span data-ttu-id="b1bef-104">Microsoft BitLocker 管理和監控（MBAM）可用於免除特定電腦的 BitLocker 保護。</span><span class="sxs-lookup"><span data-stu-id="b1bef-104">Microsoft BitLocker Administration and Monitoring (MBAM) can be used to exempt certain computers from BitLocker protection.</span></span> <span data-ttu-id="b1bef-105">例如，組織可能會決定在電腦上控制 BitLocker 免除。</span><span class="sxs-lookup"><span data-stu-id="b1bef-105">For example, an organization may decide to control BitLocker exemption on a computer-by-computer basis.</span></span>

<span data-ttu-id="b1bef-106">若要將電腦從 BitLocker 加密中免除，您必須將電腦新增至 ActiveDirectoryDomainServices 中的安全性群組，才能略過任何電腦的 BitLocker 保護規則。</span><span class="sxs-lookup"><span data-stu-id="b1bef-106">To exempt a computer from BitLocker encryption, you must add the computer to a security group in ActiveDirectoryDomainServices in order to bypass any computer-based BitLocker protection rules.</span></span>

<span data-ttu-id="b1bef-107">**記事** 如果電腦已受 BitLocker 保護，電腦豁免原則就不會有任何作用。</span><span class="sxs-lookup"><span data-stu-id="b1bef-107">**Note** If the computer is already BitLocker-protected, the computer exemption policy has no effect.</span></span>

 

**<span data-ttu-id="b1bef-108">從 BitLocker 加密中免除電腦</span><span class="sxs-lookup"><span data-stu-id="b1bef-108">To exempt a computer from BitLocker encryption</span></span>**

1.  <span data-ttu-id="b1bef-109">將您要免除的電腦帳戶新增至 ActiveDirectoryDomainServices 中的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="b1bef-109">Add the computer account that you want to be exempted to a security group in ActiveDirectoryDomainServices.</span></span> <span data-ttu-id="b1bef-110">這可讓您略過任何電腦式的 BitLocker 保護規則。</span><span class="sxs-lookup"><span data-stu-id="b1bef-110">This allows you to bypass any computer-based BitLocker protection rules.</span></span>

2.  <span data-ttu-id="b1bef-111">使用 MBAM 群組原則範本建立群組原則物件，然後將 [群組原則] 物件與您在上一個步驟中建立的 Active Directory 群組建立關聯。</span><span class="sxs-lookup"><span data-stu-id="b1bef-111">Create a Group Policy Object by using the MBAM Group Policy template, then associate the Group Policy Object with the Active Directory group that you created in the previous step.</span></span> <span data-ttu-id="b1bef-112">如需建立必要的群組原則物件的詳細資訊，請參閱[部署 MBAM 1.0 群組原則物件](deploying-mbam-10-group-policy-objects.md)。</span><span class="sxs-lookup"><span data-stu-id="b1bef-112">For more information about creating the necessary Group Policy Objects, see [Deploying MBAM 1.0 Group Policy Objects](deploying-mbam-10-group-policy-objects.md).</span></span>

3.  <span data-ttu-id="b1bef-113">當免除的電腦啟動時，MBAM 用戶端會根據電腦是否為 BitLocker 免除安全性群組的一部分，檢查電腦豁免原則設定並暫停保護。</span><span class="sxs-lookup"><span data-stu-id="b1bef-113">When an exempted computer starts, the MBAM client checks the Computer Exemption Policy setting and suspends protection based on whether the computer is part of the BitLocker exemption security group.</span></span>

## <span data-ttu-id="b1bef-114">相關主題</span><span class="sxs-lookup"><span data-stu-id="b1bef-114">Related topics</span></span>


[<span data-ttu-id="b1bef-115">管理 MBAM 1.0 功能</span><span class="sxs-lookup"><span data-stu-id="b1bef-115">Administering MBAM 1.0 Features</span></span>](administering-mbam-10-features.md)

 

 





