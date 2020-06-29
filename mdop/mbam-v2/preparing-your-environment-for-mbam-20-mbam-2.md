---
title: MBAM 2.0 的環境準備
description: MBAM 2.0 的環境準備
author: dansimp
ms.assetid: 5fb01da9-620e-4992-9e54-2ed3fb69e6af
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f1be989112d456064db302952d50159d00b5597a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811258"
---
# <span data-ttu-id="d7ae4-103">MBAM 2.0 的環境準備</span><span class="sxs-lookup"><span data-stu-id="d7ae4-103">Preparing your Environment for MBAM 2.0</span></span>


<span data-ttu-id="d7ae4-104">開始進行 Microsoft BitLocker 管理與監控（MBAM）安裝之前，您應該確定您已滿足安裝產品的先決條件。</span><span class="sxs-lookup"><span data-stu-id="d7ae4-104">Before beginning Microsoft BitLocker Administration and Monitoring (MBAM) Setup, you should make sure that you have met the prerequisites to install the product.</span></span> <span data-ttu-id="d7ae4-105">當您知道必備的先決條件之後，您就可以高效地部署產品並啟用其功能，讓它能更有效率地支援貴組織的業務目標。</span><span class="sxs-lookup"><span data-stu-id="d7ae4-105">When you know what the prerequisites are ahead of time, you can efficiently deploy the product and enable its features so that it most effectively supports your organization’s business objectives.</span></span>

<span data-ttu-id="d7ae4-106">如果您是使用 Microsoft System Center Configuration Manager 2007 或 MicrosoftSystemCenter2012 ConfigurationManager 部署 Microsoft BitLocker 管理和監視，請參閱[規劃以使用 Configuration Manager 部署 MBAM](planning-to-deploy-mbam-with-configuration-manager-2.md)。</span><span class="sxs-lookup"><span data-stu-id="d7ae4-106">If you are deploying Microsoft BitLocker Administration and Monitoring with Microsoft System Center Configuration Manager 2007 or MicrosoftSystemCenter2012 ConfigurationManager, see [Planning to Deploy MBAM with Configuration Manager](planning-to-deploy-mbam-with-configuration-manager-2.md).</span></span>

## <span data-ttu-id="d7ae4-107">評審 MBAM 2.0 部署先決條件</span><span class="sxs-lookup"><span data-stu-id="d7ae4-107">Review MBAM 2.0 Deployment Prerequisites</span></span>


<span data-ttu-id="d7ae4-108">MBAM 用戶端和每個 MBAM 伺服器功能都有特定的先決條件，必須先滿足才能成功安裝。</span><span class="sxs-lookup"><span data-stu-id="d7ae4-108">The MBAM Client and each of the MBAM Server features have specific prerequisites that must be met before they can be successfully installed.</span></span>

<span data-ttu-id="d7ae4-109">為了確保成功安裝 MBAM 用戶端和 MBAM 伺服器功能，請確定針對 MBAM 用戶端或 MBAM Server 功能安裝指定的電腦已正確準備好進行 MBAM 設定。</span><span class="sxs-lookup"><span data-stu-id="d7ae4-109">To ensure successful installation of MBAM Clients and MBAM Server features, ensure that computers specified for MBAM Client or MBAM Server feature installation are properly prepared for MBAM Setup.</span></span>

<span data-ttu-id="d7ae4-110">**記事** MBAM 安裝程式會在安裝開始前檢查是否已滿足所有先決條件。</span><span class="sxs-lookup"><span data-stu-id="d7ae4-110">**Note** MBAM Setup checks that all prerequisites are met before installation starts.</span></span> <span data-ttu-id="d7ae4-111">如果不符合所有先決條件，安裝程式將會失敗。</span><span class="sxs-lookup"><span data-stu-id="d7ae4-111">If all prerequisites are not met, Setup will fail.</span></span>

 

[<span data-ttu-id="d7ae4-112">MBAM 2.0 部署必要條件</span><span class="sxs-lookup"><span data-stu-id="d7ae4-112">MBAM 2.0 Deployment Prerequisites</span></span>](mbam-20-deployment-prerequisites-mbam-2.md)

## <span data-ttu-id="d7ae4-113">規劃 MBAM 2.0 群組原則需求</span><span class="sxs-lookup"><span data-stu-id="d7ae4-113">Plan for MBAM 2.0 Group Policy Requirements</span></span>


<span data-ttu-id="d7ae4-114">在 MBAM 可以管理企業中的用戶端之前，您必須針對環境的加密需求定義群組原則。</span><span class="sxs-lookup"><span data-stu-id="d7ae4-114">Before MBAM can manage clients in the enterprise, you must define Group Policy for the encryption requirements of your environment.</span></span>

<span data-ttu-id="d7ae4-115">**重要** MBAM 將無法與獨立的 BitLocker 磁片磁碟機加密原則搭配使用。</span><span class="sxs-lookup"><span data-stu-id="d7ae4-115">**Important** MBAM will not work with policies for stand-alone BitLocker drive encryption.</span></span> <span data-ttu-id="d7ae4-116">必須針對 MBAM 定義群組原則設定，否則 BitLocker 加密和強制執行將會失敗。</span><span class="sxs-lookup"><span data-stu-id="d7ae4-116">Group Policy settings must be defined for MBAM, or BitLocker encryption and enforcement will fail.</span></span>

 

[<span data-ttu-id="d7ae4-117">MBAM 2.0 群組原則需求規劃</span><span class="sxs-lookup"><span data-stu-id="d7ae4-117">Planning for MBAM 2.0 Group Policy Requirements</span></span>](planning-for-mbam-20-group-policy-requirements-mbam-2.md)

## <span data-ttu-id="d7ae4-118">規劃 MBAM 2.0 系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="d7ae4-118">Plan for MBAM 2.0 Administrator Roles</span></span>


<span data-ttu-id="d7ae4-119">MBAM 系統管理員角色是由在您安裝 BitLocker 管理和監視伺服器、合規性和審核報告功能，以及合規性和審核狀態資料庫時，由 MBAM 安裝程式所建立的本機群組所管理。</span><span class="sxs-lookup"><span data-stu-id="d7ae4-119">MBAM administrator roles are managed by local groups that are created by MBAM Setup when you install the BitLocker Administration and Monitoring Server, the Compliance and Audit Reports feature, and the Compliance and Audit Status Database.</span></span>

<span data-ttu-id="d7ae4-120">您可以在 ActiveDirectoryDomainServices 中建立安全性群組，將適當的管理員帳戶新增至那些群組，然後將這些安全性群組新增至 BitLocker 管理和監視本機群組，以進行管理，以取得 Microsoft BitLocker 管理和監視角色的成員資格。</span><span class="sxs-lookup"><span data-stu-id="d7ae4-120">The membership of Microsoft BitLocker Administration and Monitoring roles can best be managed by creating security groups in ActiveDirectoryDomainServices, adding the appropriate administrator accounts to those groups, and then adding those security groups to the BitLocker Administration and Monitoring local groups.</span></span> <span data-ttu-id="d7ae4-121">如需詳細資訊，請參閱[如何管理 MBAM 管理員角色](how-to-manage-mbam-administrator-roles-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="d7ae4-121">For more information, see [How to Manage MBAM Administrator Roles](how-to-manage-mbam-administrator-roles-mbam-2.md).</span></span>

## <span data-ttu-id="d7ae4-122">MBAM 規劃的其他資源</span><span class="sxs-lookup"><span data-stu-id="d7ae4-122">Other Resources for MBAM Planning</span></span>


[<span data-ttu-id="d7ae4-123">MBAM 2.0 規劃</span><span class="sxs-lookup"><span data-stu-id="d7ae4-123">Planning for MBAM 2.0</span></span>](planning-for-mbam-20-mbam-2.md)

[<span data-ttu-id="d7ae4-124">MBAM 2.0 支援的組態</span><span class="sxs-lookup"><span data-stu-id="d7ae4-124">MBAM 2.0 Supported Configurations</span></span>](mbam-20-supported-configurations-mbam-2.md)

 

 





