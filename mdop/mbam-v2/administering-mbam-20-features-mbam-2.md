---
title: 管理 MBAM 2.0 功能
description: 管理 MBAM 2.0 功能
author: dansimp
ms.assetid: 065e0704-069e-4372-9b86-0b57dd7638dd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 35bb855e185ad8e3fa6880853938074cf6185a0d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809998"
---
# <span data-ttu-id="9489d-103">管理 MBAM 2.0 功能</span><span class="sxs-lookup"><span data-stu-id="9489d-103">Administering MBAM 2.0 Features</span></span>


<span data-ttu-id="9489d-104">完成所有必要的規劃，然後部署 Microsoft BitLocker 管理與監控（MBAM）之後，您可以設定並使用它來管理整個企業的 BitLocker 加密本區段中的資訊說明安裝後的日常 Microsoft BitLocker 管理及監視功能作業工作。</span><span class="sxs-lookup"><span data-stu-id="9489d-104">After completing all necessary planning and then deploying Microsoft BitLocker Administration and Monitoring (MBAM), you can configure and use it to manage BitLocker encryption across the enterprise The information in this section describes post-installation day-to-day Microsoft BitLocker Administration and Monitoring feature operations tasks.</span></span>

## <span data-ttu-id="9489d-105">管理 MBAM 管理員角色</span><span class="sxs-lookup"><span data-stu-id="9489d-105">Manage MBAM Administrator Roles</span></span>


<span data-ttu-id="9489d-106">完成所有伺服器功能的 MBAM 設定之後，系統必須授與系統管理員的存取權。</span><span class="sxs-lookup"><span data-stu-id="9489d-106">After MBAM Setup is complete for all server features, administrative users have to be granted access to them.</span></span> <span data-ttu-id="9489d-107">最佳做法是將管理或使用 MBAM 伺服器功能的系統管理員指派給 Active Directory 網域服務安全性群組，然後將那些群組新增至適當的 MBAM 系統管理本機群組。</span><span class="sxs-lookup"><span data-stu-id="9489d-107">As a best practice, administrators who will manage or use MBAM server features should be assigned to Active Directory Domain Services security groups, and then those groups should be added to the appropriate MBAM administrative local group.</span></span>

[<span data-ttu-id="9489d-108">如何管理 MBAM 系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="9489d-108">How to Manage MBAM Administrator Roles</span></span>](how-to-manage-mbam-administrator-roles-mbam-2.md)

## <span data-ttu-id="9489d-109">管理 BitLocker 加密免除</span><span class="sxs-lookup"><span data-stu-id="9489d-109">Manage BitLocker Encryption Exemptions</span></span>


<span data-ttu-id="9489d-110">MBAM 可讓您將加密免除授權給不需要或不想要加密之磁片磁碟機的特定使用者。</span><span class="sxs-lookup"><span data-stu-id="9489d-110">MBAM lets you grant encryption exemptions to specific users who do not need or want their drives encrypted.</span></span> <span data-ttu-id="9489d-111">當公司擁有不需要加密的電腦（例如在開發或測試中使用的電腦），或是不支援 BitLocker 的舊版電腦時，通常會使用電腦例外。</span><span class="sxs-lookup"><span data-stu-id="9489d-111">Computer exemption is typically used when a company has computers that do not have to be encrypted, such as computers that are used in development or testing, or older computers that do not support BitLocker.</span></span> <span data-ttu-id="9489d-112">在某些情況下，當地法律也可能需要特定電腦不加密。</span><span class="sxs-lookup"><span data-stu-id="9489d-112">In some cases, local law may also require that certain computers are not encrypted.</span></span>

[<span data-ttu-id="9489d-113">如何管理使用者 BitLocker 加密豁免</span><span class="sxs-lookup"><span data-stu-id="9489d-113">How to Manage User BitLocker Encryption Exemptions</span></span>](how-to-manage-user-bitlocker-encryption-exemptions-mbam-2.md)

## <span data-ttu-id="9489d-114">使用 [控制台] 管理 MBAM 用戶端 BitLocker 加密選項</span><span class="sxs-lookup"><span data-stu-id="9489d-114">Manage MBAM Client BitLocker Encryption Options by Using the Control Panel</span></span>


<span data-ttu-id="9489d-115">MBAM 提供一個名為 [BitLocker 加密選項] 的自訂控制台，這些面板會出現在 [**系統及安全性**] 下。</span><span class="sxs-lookup"><span data-stu-id="9489d-115">MBAM provides a custom control panel, called BitLocker Encryption Options, that will appear under **System and Security**.</span></span> <span data-ttu-id="9489d-116">MBAM [控制台] 可用來解除鎖定加密的固定和移除磁片磁碟機，也可管理 PIN 或密碼。</span><span class="sxs-lookup"><span data-stu-id="9489d-116">The MBAM control panel can be used to unlock encrypted fixed and removable drives, and also manage your PIN or password.</span></span>

<span data-ttu-id="9489d-117">**記事** 這個自訂的 [控制台] 不會取代預設的 Windows BitLocker [控制台]。</span><span class="sxs-lookup"><span data-stu-id="9489d-117">**Note** This customized control panel does not replace the default Windows BitLocker control panel.</span></span>

 

[<span data-ttu-id="9489d-118">如何使用控制台管理 MBAM 用戶端 BitLocker 加密選項</span><span class="sxs-lookup"><span data-stu-id="9489d-118">How to Manage MBAM Client BitLocker Encryption Options by Using the Control Panel</span></span>](how-to-manage-mbam-client-bitlocker-encryption-options-by-using-the-control-panel-mbam-2.md)

## <span data-ttu-id="9489d-119">管理 MBAM 功能的其他資源</span><span class="sxs-lookup"><span data-stu-id="9489d-119">Other Resources for Administering MBAM Features</span></span>


[<span data-ttu-id="9489d-120">適用於 MBAM 2.0 的操作</span><span class="sxs-lookup"><span data-stu-id="9489d-120">Operations for MBAM 2.0</span></span>](operations-for-mbam-20-mbam-2.md)

 

 





