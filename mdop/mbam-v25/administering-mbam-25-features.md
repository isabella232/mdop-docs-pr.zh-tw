---
title: 管理 MBAM 2.5 功能
description: 管理 MBAM 2.5 功能
author: dansimp
ms.assetid: ca15f818-cf07-4437-8ffa-425af603a3c8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2a365442c11479563d43159e6ef9859c252ce28b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810412"
---
# <span data-ttu-id="ba4fe-103">管理 MBAM 2.5 功能</span><span class="sxs-lookup"><span data-stu-id="ba4fe-103">Administering MBAM 2.5 Features</span></span>


<span data-ttu-id="ba4fe-104">完成所有必要的規劃，然後部署 Microsoft BitLocker 管理與監控（MBAM）之後，您可以設定並使用它來管理整個企業的 BitLocker 加密本區段中的資訊說明安裝後的日常 Microsoft BitLocker 管理及監視功能作業工作。</span><span class="sxs-lookup"><span data-stu-id="ba4fe-104">After completing all necessary planning and then deploying Microsoft BitLocker Administration and Monitoring (MBAM), you can configure and use it to manage BitLocker encryption across the enterprise The information in this section describes post-installation day-to-day Microsoft BitLocker Administration and Monitoring feature operations tasks.</span></span>

## <span data-ttu-id="ba4fe-105">管理 BitLocker 加密免除</span><span class="sxs-lookup"><span data-stu-id="ba4fe-105">Manage BitLocker Encryption Exemptions</span></span>


<span data-ttu-id="ba4fe-106">MBAM 可讓您將加密免除授權給不需要或不想要加密之磁片磁碟機的特定使用者。</span><span class="sxs-lookup"><span data-stu-id="ba4fe-106">MBAM lets you grant encryption exemptions to specific users who do not need or want their drives encrypted.</span></span> <span data-ttu-id="ba4fe-107">當公司擁有不需要加密的電腦（例如在開發或測試中使用的電腦），或是不支援 BitLocker 的舊版電腦時，通常會使用電腦例外。</span><span class="sxs-lookup"><span data-stu-id="ba4fe-107">Computer exemption is typically used when a company has computers that do not have to be encrypted, such as computers that are used in development or testing, or older computers that do not support BitLocker.</span></span> <span data-ttu-id="ba4fe-108">在某些情況下，當地法律也可能需要特定電腦不加密。</span><span class="sxs-lookup"><span data-stu-id="ba4fe-108">In some cases, local law may also require that certain computers are not encrypted.</span></span>

[<span data-ttu-id="ba4fe-109">如何管理使用者 BitLocker 加密豁免</span><span class="sxs-lookup"><span data-stu-id="ba4fe-109">How to Manage User BitLocker Encryption Exemptions</span></span>](how-to-manage-user-bitlocker-encryption-exemptions-mbam-25.md)

## <span data-ttu-id="ba4fe-110">瞭解 [控制台] 中的 BitLocker 加密選項和 BitLocker 磁片磁碟機加密專案</span><span class="sxs-lookup"><span data-stu-id="ba4fe-110">Understand the BitLocker Encryption Options and BitLocker Drive Encryption Items in Control Panel</span></span>


<span data-ttu-id="ba4fe-111">MBAM 提供一個名為 [在**系統及安全性**] 底下的自訂控制台，稱為 [BitLocker 加密選項]。</span><span class="sxs-lookup"><span data-stu-id="ba4fe-111">MBAM provides a custom control panel, called BitLocker Encryption Options, that appears under **System and Security**.</span></span> <span data-ttu-id="ba4fe-112">MBAM [控制台] 可用來解除鎖定加密的固定和移除磁片磁碟機，也可管理 PIN 或密碼。</span><span class="sxs-lookup"><span data-stu-id="ba4fe-112">The MBAM control panel can be used to unlock encrypted fixed and removable drives, and also manage your PIN or password.</span></span>

<span data-ttu-id="ba4fe-113">**記事** 這個自訂的 [控制台] 不會取代預設的 Windows BitLocker [控制台]。</span><span class="sxs-lookup"><span data-stu-id="ba4fe-113">**Note** This customized control panel does not replace the default Windows BitLocker control panel.</span></span>

 

[<span data-ttu-id="ba4fe-114">了解控制台中的 BitLocker 加密選項與 BitLocker 磁碟機加密項目</span><span class="sxs-lookup"><span data-stu-id="ba4fe-114">Understanding the BitLocker Encryption Options and BitLocker Drive Encryption Items in Control Panel</span></span>](understanding-the-bitlocker-encryption-options-and-bitlocker-drive-encryption-items-in-control-panel.md)

## <span data-ttu-id="ba4fe-115">管理 MBAM 功能的其他資源</span><span class="sxs-lookup"><span data-stu-id="ba4fe-115">Other Resources for Administering MBAM Features</span></span>


[<span data-ttu-id="ba4fe-116">適用於 MBAM 2.5 的操作</span><span class="sxs-lookup"><span data-stu-id="ba4fe-116">Operations for MBAM 2.5</span></span>](operations-for-mbam-25.md)

## <span data-ttu-id="ba4fe-117">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="ba4fe-117">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="ba4fe-118">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="ba4fe-118">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="ba4fe-119">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="ba4fe-119">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>

 

 





