---
title: 如何管理 MBAM 系統管理員角色
description: 如何管理 MBAM 系統管理員角色
author: dansimp
ms.assetid: c0f25a42-dbff-418d-a776-4fe23ee07d16
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9d00b8ebf66d2b066afae33e67298691285ce9fa
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800226"
---
# <span data-ttu-id="5cbb9-103">如何管理 MBAM 系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="5cbb9-103">How to Manage MBAM Administrator Roles</span></span>


<span data-ttu-id="5cbb9-104">在 Microsoft BitLocker 管理和監控（MBAM）完成所有伺服器功能之後，系統必須授與系統管理員對這些伺服器功能的存取權。</span><span class="sxs-lookup"><span data-stu-id="5cbb9-104">After Microsoft BitLocker Administration and Monitoring (MBAM) Setup is complete for all server features, administrative users must be granted access to these server features.</span></span> <span data-ttu-id="5cbb9-105">最佳做法是，要管理或使用 MBAM 伺服器功能的系統管理員應該指派給 Active Directory 安全性群組，然後將那些群組新增至適當的 MBAM 系統管理本機群組。</span><span class="sxs-lookup"><span data-stu-id="5cbb9-105">As a best practice, administrators who will manage or use MBAM server features, should be assigned to Active Directory security groups and then those groups should be added to the appropriate MBAM administrative local group.</span></span>

**<span data-ttu-id="5cbb9-106">管理 MBAM 管理員角色成員資格</span><span class="sxs-lookup"><span data-stu-id="5cbb9-106">To manage MBAM Administrator Role memberships</span></span>**

1.  <span data-ttu-id="5cbb9-107">將系統管理使用者指派給 ActiveDirectoryDomain Services 中的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="5cbb9-107">Assign administrative users to security groups in ActiveDirectoryDomain Services.</span></span>

2.  <span data-ttu-id="5cbb9-108">將 ActiveDirectoryDomain Services 安全性群組新增至 Microsoft BitLocker 管理和監視伺服器上的 MBAM 管理本機群組，以進行個別功能。</span><span class="sxs-lookup"><span data-stu-id="5cbb9-108">Add ActiveDirectoryDomain Services security groups to the roles for MBAM administrative local groups on the Microsoft BitLocker Administration and Monitoring server for the respective features.</span></span> <span data-ttu-id="5cbb9-109">使用者角色如下所示：</span><span class="sxs-lookup"><span data-stu-id="5cbb9-109">The user roles are as follows:</span></span>

    -   <span data-ttu-id="5cbb9-110">**MBAM 系統管理員**可以存取 MBAM 管理網站中的所有 Microsoft BitLocker 管理和監控功能。</span><span class="sxs-lookup"><span data-stu-id="5cbb9-110">**MBAM System Administrators** have access to all Microsoft BitLocker Administration and Monitoring features in the MBAM administration website.</span></span>

    -   <span data-ttu-id="5cbb9-111">**MBAM 硬體使用者**可以存取 MBAM 管理網站中的硬體相容性功能。</span><span class="sxs-lookup"><span data-stu-id="5cbb9-111">**MBAM Hardware Users** have access to the Hardware Compatibility features in the MBAM administration website.</span></span>

    -   <span data-ttu-id="5cbb9-112">**MBAM 的支援人員**可存取 MBAM 管理網站中的 [管理 TPM 及磁片磁碟機復原] 選項，但在使用其中一個選項時，必須填入所有欄位。</span><span class="sxs-lookup"><span data-stu-id="5cbb9-112">**MBAM Helpdesk Users** have access to the Manage TPM and Drive Recovery options in the MBAM administration website, but must fill in all fields when they use either option.</span></span>

    -   <span data-ttu-id="5cbb9-113">**MBAM 報表使用者**可以存取 MBAM 管理網站中的合規性和審核報告。</span><span class="sxs-lookup"><span data-stu-id="5cbb9-113">**MBAM Report Users** have access to the Compliance and Audit reports in the MBAM administration website.</span></span>

    -   <span data-ttu-id="5cbb9-114">**MBAM 高級支援人員的使用**可存取 MBAM 管理網站中的 [管理 TPM 及磁片磁碟機復原] 選項。</span><span class="sxs-lookup"><span data-stu-id="5cbb9-114">**MBAM Advanced Helpdesk Uses** have access to the Manage TPM and Drive Recovery options in the MBAM administration website.</span></span> <span data-ttu-id="5cbb9-115">當您使用任一選項時，不需要這些使用者填寫所有欄位。</span><span class="sxs-lookup"><span data-stu-id="5cbb9-115">These users are not required to fill in all fields when they use either option.</span></span>

    <span data-ttu-id="5cbb9-116">如需有關 Microsoft BitLocker 管理和監控角色的詳細資訊，請參閱[規劃 MBAM 1.0 系統管理員角色](planning-for-mbam-10-administrator-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="5cbb9-116">For more information about roles for Microsoft BitLocker Administration and Monitoring, see [Planning for MBAM 1.0 Administrator Roles](planning-for-mbam-10-administrator-roles.md).</span></span>

## <span data-ttu-id="5cbb9-117">相關主題</span><span class="sxs-lookup"><span data-stu-id="5cbb9-117">Related topics</span></span>


[<span data-ttu-id="5cbb9-118">管理 MBAM 1.0 功能</span><span class="sxs-lookup"><span data-stu-id="5cbb9-118">Administering MBAM 1.0 Features</span></span>](administering-mbam-10-features.md)

 

 





