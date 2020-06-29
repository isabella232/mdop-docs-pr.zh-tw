---
title: AGPM 3.0 的新功能
description: AGPM 3.0 的新功能
author: dansimp
ms.assetid: 0d082b86-63c5-45ce-9529-6e5f37254f9d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 811a19798e6669ef1cdaf8a53493dbbc2faa007e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801706"
---
# <span data-ttu-id="a7a98-103">AGPM 3.0 的新功能</span><span class="sxs-lookup"><span data-stu-id="a7a98-103">What's New in AGPM 3.0</span></span>


<span data-ttu-id="a7a98-104">Microsoft 高級群組原則管理（AGPM）3.0 包含下列新增或變更的功能：</span><span class="sxs-lookup"><span data-stu-id="a7a98-104">Microsoft Advanced Group Policy Management (AGPM)3.0 includes the following new or changed features:</span></span>

-   <span data-ttu-id="a7a98-105">支援 WindowsServer2008 和 WindowsVista Service Pack 1，其中包含32位和64位版本</span><span class="sxs-lookup"><span data-stu-id="a7a98-105">Support for WindowsServer2008 and WindowsVista with Service Pack 1 that includes 32-bit and 64-bit versions</span></span>

-   <span data-ttu-id="a7a98-106">改良安裝程式</span><span class="sxs-lookup"><span data-stu-id="a7a98-106">Improved installation process</span></span>

-   <span data-ttu-id="a7a98-107">簡化了修改 AGPM 服務器所監聽之埠的程式</span><span class="sxs-lookup"><span data-stu-id="a7a98-107">Simplified procedure for modifying the port on which the AGPM Server listens</span></span>

-   <span data-ttu-id="a7a98-108">每個 GPO 之歷程記錄中的詳細資訊</span><span class="sxs-lookup"><span data-stu-id="a7a98-108">More detailed information in the History of each GPO</span></span>

-   <span data-ttu-id="a7a98-109">能夠從 AGPM 委派對生產環境的存取權</span><span class="sxs-lookup"><span data-stu-id="a7a98-109">Ability to delegate access to the production environment from AGPM</span></span>

-   <span data-ttu-id="a7a98-110">限制儲存在封存中之 GPO 版本數的能力</span><span class="sxs-lookup"><span data-stu-id="a7a98-110">Ability to limit the number of GPO versions stored in the archive</span></span>

-   <span data-ttu-id="a7a98-111">能夠設定 AGPM 的電子郵件安全性</span><span class="sxs-lookup"><span data-stu-id="a7a98-111">Ability to configure e-mail security for AGPM</span></span>

-   <span data-ttu-id="a7a98-112">AGPM 原則設定的易記名稱</span><span class="sxs-lookup"><span data-stu-id="a7a98-112">Friendlier names for AGPM policy settings</span></span>

-   <span data-ttu-id="a7a98-113">編輯者角色現在需要從封存中刪除 Gpo 的許可權</span><span class="sxs-lookup"><span data-stu-id="a7a98-113">The Editor role now requires permission to delete GPOs from the archive</span></span>

<span data-ttu-id="a7a98-114">此外，您還會針對下列語言當地語系化 AGPM 3.0：</span><span class="sxs-lookup"><span data-stu-id="a7a98-114">Additionally, AGPM3.0 is localized for the following languages:</span></span>

-   <span data-ttu-id="a7a98-115">中文 (簡體)</span><span class="sxs-lookup"><span data-stu-id="a7a98-115">Chinese (Simplified)</span></span>

-   <span data-ttu-id="a7a98-116">中文 (台灣)</span><span class="sxs-lookup"><span data-stu-id="a7a98-116">Chinese (Taiwan)</span></span>

-   <span data-ttu-id="a7a98-117">英文（美國）</span><span class="sxs-lookup"><span data-stu-id="a7a98-117">English (U.S.)</span></span>

-   <span data-ttu-id="a7a98-118">法文</span><span class="sxs-lookup"><span data-stu-id="a7a98-118">French</span></span>

-   <span data-ttu-id="a7a98-119">德文</span><span class="sxs-lookup"><span data-stu-id="a7a98-119">German</span></span>

-   <span data-ttu-id="a7a98-120">義大利文</span><span class="sxs-lookup"><span data-stu-id="a7a98-120">Italian</span></span>

-   <span data-ttu-id="a7a98-121">日文</span><span class="sxs-lookup"><span data-stu-id="a7a98-121">Japanese</span></span>

-   <span data-ttu-id="a7a98-122">韓文</span><span class="sxs-lookup"><span data-stu-id="a7a98-122">Korean</span></span>

-   <span data-ttu-id="a7a98-123">葡萄牙文 (巴西)</span><span class="sxs-lookup"><span data-stu-id="a7a98-123">Portuguese (Brazil)</span></span>

-   <span data-ttu-id="a7a98-124">俄文</span><span class="sxs-lookup"><span data-stu-id="a7a98-124">Russian</span></span>

-   <span data-ttu-id="a7a98-125">西班牙文</span><span class="sxs-lookup"><span data-stu-id="a7a98-125">Spanish</span></span>

### <span data-ttu-id="a7a98-126">其他考量</span><span class="sxs-lookup"><span data-stu-id="a7a98-126">Additional considerations</span></span>

<span data-ttu-id="a7a98-127">AGPM 3.0 支援 Windows Server2008 和 WindowsVista 與 SP1。</span><span class="sxs-lookup"><span data-stu-id="a7a98-127">AGPM3.0 supports Windows Server2008 and WindowsVista with SP1.</span></span> <span data-ttu-id="a7a98-128">它不支援未安裝 service pack 的 WindowsServer2003 或 WindowsVista。</span><span class="sxs-lookup"><span data-stu-id="a7a98-128">It does not support WindowsServer2003 or WindowsVista with no service packs installed.</span></span> <span data-ttu-id="a7a98-129">AGPM 2.5 支援這些環境。</span><span class="sxs-lookup"><span data-stu-id="a7a98-129">AGPM2.5 supports those environments.</span></span> <span data-ttu-id="a7a98-130">如需詳細資訊，請參閱[選擇要安裝的 AGPM 版本](choosing-which-version-of-agpm-to-install.md)。</span><span class="sxs-lookup"><span data-stu-id="a7a98-130">For more information, see [Choosing Which Version of AGPM to Install](choosing-which-version-of-agpm-to-install.md).</span></span>

 

 





