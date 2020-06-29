---
title: 如何管理 MBAM 系統管理員角色
description: 如何管理 MBAM 系統管理員角色
author: dansimp
ms.assetid: 813ac0c4-3cf9-47af-b4cb-9395fd915e5c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 14e9128904b448b20e0596a2630627b7ca8e711d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810964"
---
# <span data-ttu-id="b45f1-103">如何管理 MBAM 系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="b45f1-103">How to Manage MBAM Administrator Roles</span></span>


<span data-ttu-id="b45f1-104">在 Microsoft BitLocker 管理和監控（MBAM）完成所有伺服器功能之後，系統必須授與系統管理員的存取權。</span><span class="sxs-lookup"><span data-stu-id="b45f1-104">After Microsoft BitLocker Administration and Monitoring (MBAM) Setup is complete for all server features, administrative users will have to be granted access to them.</span></span> <span data-ttu-id="b45f1-105">最佳做法是，要管理或使用 Microsoft BitLocker 管理和監視伺服器功能的系統管理員應該指派給網域服務安全性群組，然後將那些群組新增至適當的 MBAM 系統管理本機群組。</span><span class="sxs-lookup"><span data-stu-id="b45f1-105">As a best practice, administrators who will manage or use Microsoft BitLocker Administration and Monitoring Server features should be assigned to Domain Services security groups, and then those groups should be added to the appropriate MBAM administrative local group.</span></span>

**<span data-ttu-id="b45f1-106">管理 MBAM 管理員角色成員資格</span><span class="sxs-lookup"><span data-stu-id="b45f1-106">To manage MBAM Administrator Role memberships</span></span>**

1.  <span data-ttu-id="b45f1-107">將系統管理使用者指派給 ActiveDirectory 網域服務中的安全性群組。</span><span class="sxs-lookup"><span data-stu-id="b45f1-107">Assign administrative users to security groups in ActiveDirectory Domain Services.</span></span>

2.  <span data-ttu-id="b45f1-108">在 MBAM 伺服器上，將 ActiveDirectory 安全性群組新增至 MBAM 系統管理本機群組的角色，以取得各自的功能。</span><span class="sxs-lookup"><span data-stu-id="b45f1-108">Add ActiveDirectory security groups to the roles for MBAM administrative local groups on the MBAM server for the respective features.</span></span>

    -   <span data-ttu-id="b45f1-109">**MBAM 系統管理員**可以存取 MBAM 管理和監控網站中的所有 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="b45f1-109">**MBAM System Administrators** have access to all MBAM features in the MBAM Administration and Monitoring website.</span></span>

    -   <span data-ttu-id="b45f1-110">**MBAM 支援者使用者**可以存取 MBAM 管理和監控網站中的 [管理 TPM 及磁片磁碟機復原] 選項，但在使用其中一個選項時，必須填入所有欄位。</span><span class="sxs-lookup"><span data-stu-id="b45f1-110">**MBAM Helpdesk Users** have access to the Manage TPM and Drive Recovery options in the MBAM Administration and Monitoring website, but must fill in all fields when they use either option.</span></span>

    -   <span data-ttu-id="b45f1-111">**MBAM 報表使用者**可以存取 MBAM 管理和監視網站中的合規性和審核報告。</span><span class="sxs-lookup"><span data-stu-id="b45f1-111">**MBAM Report Users** have access to the Compliance and Audit reports in the MBAM Administration and Monitoring website.</span></span>

    -   <span data-ttu-id="b45f1-112">**MBAM 高級支援人員的使用者**可以存取 MBAM 管理和監控網站中的 [管理 TPM] 和 [磁碟機復原] 選項，但在使用任一選項時，不需要填寫所有欄位。</span><span class="sxs-lookup"><span data-stu-id="b45f1-112">**MBAM Advanced Helpdesk Users** have access to the Manage TPM and Drive Recovery options in the MBAM Administration and Monitoring website, but are not required to fill in all fields when they use either option.</span></span>

    <span data-ttu-id="b45f1-113">如需有關 Microsoft BitLocker 管理和監控角色的詳細資訊，請參閱[規劃 MBAM 2.0 系統管理員角色](planning-for-mbam-20-administrator-roles-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="b45f1-113">For more information about roles for Microsoft BitLocker Administration and Monitoring, see [Planning for MBAM 2.0 Administrator Roles](planning-for-mbam-20-administrator-roles-mbam-2.md).</span></span>

## <span data-ttu-id="b45f1-114">相關主題</span><span class="sxs-lookup"><span data-stu-id="b45f1-114">Related topics</span></span>


[<span data-ttu-id="b45f1-115">管理 MBAM 2.0 功能</span><span class="sxs-lookup"><span data-stu-id="b45f1-115">Administering MBAM 2.0 Features</span></span>](administering-mbam-20-features-mbam-2.md)

 

 





