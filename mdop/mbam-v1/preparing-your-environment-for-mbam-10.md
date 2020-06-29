---
title: MBAM 1.0 的環境準備
description: MBAM 1.0 的環境準備
author: dansimp
ms.assetid: 915f7c3c-70ad-4a90-a434-73e7fba97ecb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9a2de4e825d5c89aeabcf57d78dc856bacb03e11
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809807"
---
# <span data-ttu-id="460bf-103">MBAM 1.0 的環境準備</span><span class="sxs-lookup"><span data-stu-id="460bf-103">Preparing your Environment for MBAM 1.0</span></span>


<span data-ttu-id="460bf-104">開始進行 Microsoft BitLocker 管理與監控（MBAM）安裝之前，請確定您已滿足安裝產品所需的先決條件。</span><span class="sxs-lookup"><span data-stu-id="460bf-104">Before you begin the Microsoft BitLocker Administration and Monitoring (MBAM) Setup, make sure that you have met the necessary prerequisites to install the product.</span></span> <span data-ttu-id="460bf-105">如果您事先知道先決條件，您就可以高效地部署產品並啟用其功能，以便更有效率地支援貴組織的業務目標。</span><span class="sxs-lookup"><span data-stu-id="460bf-105">If you know the prerequisites in advance, you can efficiently deploy the product and enable its features, which can support the business objectives of your organization more effectively.</span></span>

## <span data-ttu-id="460bf-106">評審 MBAM 1.0 部署先決條件</span><span class="sxs-lookup"><span data-stu-id="460bf-106">Review MBAM 1.0 deployment prerequisites</span></span>


<span data-ttu-id="460bf-107">MBAM 用戶端和每個 MBAM 伺服器功能都有特定的先決條件，必須先滿足才能成功安裝。</span><span class="sxs-lookup"><span data-stu-id="460bf-107">The MBAM Client and each of the MBAM Server features have specific prerequisites that must be met before they can be successfully installed.</span></span>

<span data-ttu-id="460bf-108">若要確保成功安裝 MBAM 用戶端和 MBAM 伺服器功能，您應該規劃確保針對 MBAM 用戶端或 MBAM Server 功能安裝所指定的電腦已正確準備好進行 MBAM 設定。</span><span class="sxs-lookup"><span data-stu-id="460bf-108">To ensure successful installation of MBAM Clients and MBAM Server features, you should plan to ensure that computers specified for MBAM Client or MBAM Server feature installation are properly prepared for MBAM Setup.</span></span>

<span data-ttu-id="460bf-109">**記事** MBAM 安裝程式會在安裝開始前驗證是否已滿足所有先決條件。</span><span class="sxs-lookup"><span data-stu-id="460bf-109">**Note** MBAM Setup verifies if all prerequisites are met before installation starts.</span></span> <span data-ttu-id="460bf-110">如果不符合，安裝程式將會失敗。</span><span class="sxs-lookup"><span data-stu-id="460bf-110">If they are not met, Setup will fail.</span></span>

 

[<span data-ttu-id="460bf-111">MBAM 1.0 部署必要條件</span><span class="sxs-lookup"><span data-stu-id="460bf-111">MBAM 1.0 Deployment Prerequisites</span></span>](mbam-10-deployment-prerequisites.md)

## <span data-ttu-id="460bf-112">規劃 MBAM 1.0 群組原則需求</span><span class="sxs-lookup"><span data-stu-id="460bf-112">Plan for MBAM 1.0 Group Policy requirements</span></span>


<span data-ttu-id="460bf-113">在 MBAM 可以管理企業中的用戶端之前，您必須針對環境的加密需求定義群組原則。</span><span class="sxs-lookup"><span data-stu-id="460bf-113">Before MBAM can manage clients in the enterprise, you must define the Group Policy for the encryption requirements of your environment.</span></span>

<span data-ttu-id="460bf-114">**重要** MBAM 將無法與獨立的 BitLocker 磁片磁碟機加密原則搭配使用。</span><span class="sxs-lookup"><span data-stu-id="460bf-114">**Important** MBAM will not work with policies for stand-alone BitLocker drive encryption.</span></span> <span data-ttu-id="460bf-115">必須針對 MBAM 定義群群組原則;否則，BitLocker 加密和強制將會失敗。</span><span class="sxs-lookup"><span data-stu-id="460bf-115">Group Policy must be defined for MBAM; otherwise, the BitLocker encryption and enforcement will fail.</span></span>

 

[<span data-ttu-id="460bf-116">MBAM 1.0 群組原則需求規劃</span><span class="sxs-lookup"><span data-stu-id="460bf-116">Planning for MBAM 1.0 Group Policy Requirements</span></span>](planning-for-mbam-10-group-policy-requirements.md)

## <span data-ttu-id="460bf-117">規劃 MBAM 1.0 系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="460bf-117">Plan for MBAM 1.0 administrator roles</span></span>


<span data-ttu-id="460bf-118">MBAM 系統管理員角色是由在您安裝下列各項時由 MBAM 安裝程式所建立的本機群組所管理： BitLocker 管理與監視伺服器、合規性和審核報告功能，以及合規性與審核狀態資料庫。</span><span class="sxs-lookup"><span data-stu-id="460bf-118">MBAM administrator roles are managed by local groups that are created by MBAM Setup when you install the following: BitLocker Administration and Monitoring Server, the Compliance and Audit Reports feature, and the Compliance and Audit Status Database.</span></span>

<span data-ttu-id="460bf-119">如果您在 ActiveDirectoryDomainServices 中建立安全性群組，就能更有效地管理 MBAM 角色的成員資格，將適當的管理員帳戶新增到這些群組，然後將這些安全性群組新增至 MBAM 本機群組。</span><span class="sxs-lookup"><span data-stu-id="460bf-119">The membership of MBAM roles can be managed more effectively if you create security groups in ActiveDirectoryDomainServices, add the appropriate administrator accounts to those groups, and then add those security groups to the MBAM local groups.</span></span> <span data-ttu-id="460bf-120">如需詳細資訊，請參閱[如何管理 MBAM 管理員角色](how-to-manage-mbam-administrator-roles-mbam-1.md)。</span><span class="sxs-lookup"><span data-stu-id="460bf-120">For more information, see [How to Manage MBAM Administrator Roles](how-to-manage-mbam-administrator-roles-mbam-1.md).</span></span>

[<span data-ttu-id="460bf-121">MBAM 1.0 系統管理員角色規劃</span><span class="sxs-lookup"><span data-stu-id="460bf-121">Planning for MBAM 1.0 Administrator Roles</span></span>](planning-for-mbam-10-administrator-roles.md)

## <span data-ttu-id="460bf-122">MBAM 規劃的其他資源</span><span class="sxs-lookup"><span data-stu-id="460bf-122">Other resources for MBAM planning</span></span>


[<span data-ttu-id="460bf-123">MBAM 1.0 規劃</span><span class="sxs-lookup"><span data-stu-id="460bf-123">Planning for MBAM 1.0</span></span>](planning-for-mbam-10.md)

 

 





