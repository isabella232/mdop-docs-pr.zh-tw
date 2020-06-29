---
title: 管理 MBAM 1.0 功能
description: 管理 MBAM 1.0 功能
author: dansimp
ms.assetid: dd9a9eff-f1ad-4af3-85d9-c19131a4ad22
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a99ac556227c0f113fb20f3aca32d21c204877b0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808625"
---
# <span data-ttu-id="8158d-103">管理 MBAM 1.0 功能</span><span class="sxs-lookup"><span data-stu-id="8158d-103">Administering MBAM 1.0 Features</span></span>


<span data-ttu-id="8158d-104">完成所有必要的 Microsoft BitLocker 管理和監控（MBAM）規劃與部署之後，您可以設定及使用 MBAM 來管理企業 BitLocker 加密。</span><span class="sxs-lookup"><span data-stu-id="8158d-104">After you complete all necessary Microsoft BitLocker Administration and Monitoring (MBAM) planning and deployment, you can configure and use MBAM to manage enterprise BitLocker encryption.</span></span> <span data-ttu-id="8158d-105">本節中的資訊說明安裝後的日常 MBAM 功能作業作業。</span><span class="sxs-lookup"><span data-stu-id="8158d-105">The information in this section describes post-installation day-to-day MBAM feature operations tasks.</span></span>

## <span data-ttu-id="8158d-106">管理 MBAM 管理員角色</span><span class="sxs-lookup"><span data-stu-id="8158d-106">Manage MBAM Administrator Roles</span></span>


<span data-ttu-id="8158d-107">完成所有伺服器功能的 MBAM 設定之後，系統必須授與系統管理員對這些伺服器功能的存取權。</span><span class="sxs-lookup"><span data-stu-id="8158d-107">After MBAM Setup is complete for all server features, administrative users must be granted access to these server features.</span></span> <span data-ttu-id="8158d-108">最佳做法是，要管理或使用 MBAM 伺服器功能的系統管理員應該指派給 Active Directory 安全性群組，然後將那些群組新增至適當的 MBAM 系統管理本機群組。</span><span class="sxs-lookup"><span data-stu-id="8158d-108">As a best practice, administrators who will manage or use MBAM server features, should be assigned to Active Directory security groups and then those groups should be added to the appropriate MBAM administrative local group.</span></span>

[<span data-ttu-id="8158d-109">如何管理 MBAM 系統管理員角色</span><span class="sxs-lookup"><span data-stu-id="8158d-109">How to Manage MBAM Administrator Roles</span></span>](how-to-manage-mbam-administrator-roles-mbam-1.md)

## <span data-ttu-id="8158d-110">管理硬體相容性</span><span class="sxs-lookup"><span data-stu-id="8158d-110">Manage Hardware Compatibility</span></span>


<span data-ttu-id="8158d-111">MBAM 硬體相容性功能可協助您確保只有您指定為支援 BitLocker 的電腦硬體會受到加密。</span><span class="sxs-lookup"><span data-stu-id="8158d-111">The MBAM Hardware Compatibility feature can help you to ensure that only the computer hardware that you specify as supporting BitLocker will be encrypted.</span></span> <span data-ttu-id="8158d-112">開啟此功能時，bit _admmontla 只會加密標示為相容的電腦。</span><span class="sxs-lookup"><span data-stu-id="8158d-112">When this feature is turned on, bit\_admmontla will encrypt only computers that are marked as Compatible.</span></span>

<span data-ttu-id="8158d-113">**重要** 關閉此功能時，系統會將部署 MBAM 原則的所有電腦加密。</span><span class="sxs-lookup"><span data-stu-id="8158d-113">**Important** When this feature is turned off, all computers where the MBAM policy is deployed will be encrypted.</span></span>

 

<span data-ttu-id="8158d-114">如果您部署了 [允許硬體相容性檢查] 群組原則，MBAM 可以收集用戶端電腦的品牌與型號資訊。</span><span class="sxs-lookup"><span data-stu-id="8158d-114">MBAM can collect information on both the make and model of client computers if you deploy the “Allow Hardware Compatibility Checking” Group Policy.</span></span> <span data-ttu-id="8158d-115">如果您設定此原則，當您在用戶端電腦上部署 MBAM 用戶端時，MBAM 代理會向 MBAM 伺服器報告電腦品牌和模型資訊。</span><span class="sxs-lookup"><span data-stu-id="8158d-115">If you configure this policy, the MBAM agent reports the computer make and model information to the MBAM Server when the MBAM Client is deployed on a client computer.</span></span>

[<span data-ttu-id="8158d-116">如何管理硬體相容性</span><span class="sxs-lookup"><span data-stu-id="8158d-116">How to Manage Hardware Compatibility</span></span>](how-to-manage-hardware-compatibility-mbam-1.md)

[<span data-ttu-id="8158d-117">如何管理使用者 BitLocker 加密豁免</span><span class="sxs-lookup"><span data-stu-id="8158d-117">How to Manage User BitLocker Encryption Exemptions</span></span>](how-to-manage-user-bitlocker-encryption-exemptions-mbam-1.md)

## <span data-ttu-id="8158d-118">管理 BitLocker 加密免除</span><span class="sxs-lookup"><span data-stu-id="8158d-118">Manage BitLocker encryption exemptions</span></span>


<span data-ttu-id="8158d-119">MBAM 可以從 BitLocker 加密中授予兩種形式的免除：電腦豁免與使用者豁免。</span><span class="sxs-lookup"><span data-stu-id="8158d-119">MBAM can grant two forms of exemption from BitLocker encryption: computer exemption and user exemption.</span></span> <span data-ttu-id="8158d-120">當公司擁有不需要加密的電腦（例如在開發或測試中使用的電腦），或是不支援 BitLocker 的舊版電腦時，通常會使用電腦例外。</span><span class="sxs-lookup"><span data-stu-id="8158d-120">Computer exemption is typically used when a company has computers that do not have to be encrypted, such as computers that are used in development or testing, or older computers that do not support BitLocker.</span></span> <span data-ttu-id="8158d-121">在某些情況下，當地法律也可能需要特定電腦不加密。</span><span class="sxs-lookup"><span data-stu-id="8158d-121">In some cases, local law may also require that certain computers are not encrypted.</span></span> <span data-ttu-id="8158d-122">您也可以選擇免除不需要或不想要加密其磁片磁碟機的使用者。</span><span class="sxs-lookup"><span data-stu-id="8158d-122">You may also choose to exempt users who do not need or want their drives encrypted.</span></span>

[<span data-ttu-id="8158d-123">如何管理電腦 BitLocker 加密豁免</span><span class="sxs-lookup"><span data-stu-id="8158d-123">How to Manage Computer BitLocker Encryption Exemptions</span></span>](how-to-manage-computer-bitlocker-encryption-exemptions.md)

## <span data-ttu-id="8158d-124">使用 [控制台] 管理 MBAM 用戶端 BitLocker 加密選項</span><span class="sxs-lookup"><span data-stu-id="8158d-124">Manage MBAM Client BitLocker Encryption Options by using the Control Panel</span></span>


<span data-ttu-id="8158d-125">如果透過群群組原則物件（GPO）啟用，則會在 [**系統及安全性**] 下提供一個名為 [BitLocker 加密選項] 的自訂 MBAM [控制台]。</span><span class="sxs-lookup"><span data-stu-id="8158d-125">If enabled through a Group Policy Objects (GPO), a custom MBAM control panel that is named BitLocker Encryption Options will be available under **System and Security**.</span></span> <span data-ttu-id="8158d-126">這個自訂的 [控制台] 會取代預設的 Windows BitLocker [控制台]。</span><span class="sxs-lookup"><span data-stu-id="8158d-126">This customized control panel replaces the default Windows BitLocker control panel.</span></span> <span data-ttu-id="8158d-127">[MBAM 控制台] 可讓您解除鎖定加密的磁碟機（固定和移除），也可協助您管理 PIN 或密碼。</span><span class="sxs-lookup"><span data-stu-id="8158d-127">The MBAM control panel enables you to unlock encrypted drives (fixed and removable), and also helps you manage your PIN or password.</span></span>

[<span data-ttu-id="8158d-128">如何使用控制台管理 MBAM 用戶端 BitLocker 加密選項</span><span class="sxs-lookup"><span data-stu-id="8158d-128">How to Manage MBAM Client BitLocker Encryption Options by Using the Control Panel</span></span>](how-to-manage-mbam-client-bitlocker-encryption-options-by-using-the-control-panel-mbam-1.md)

## <span data-ttu-id="8158d-129">管理 MBAM 功能的其他資源</span><span class="sxs-lookup"><span data-stu-id="8158d-129">Other resources for Administering MBAM features</span></span>


[<span data-ttu-id="8158d-130">適用於 MBAM 1.0 的操作</span><span class="sxs-lookup"><span data-stu-id="8158d-130">Operations for MBAM 1.0</span></span>](operations-for-mbam-10.md)

 

 





