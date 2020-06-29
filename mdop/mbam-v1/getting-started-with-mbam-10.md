---
title: 開始使用 MBAM 1.0
description: 開始使用 MBAM 1.0
author: dansimp
ms.assetid: 4fab4e4a-d25e-4661-b235-2b45bf5ac3e4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e0bbbcabfb25cfc8b24cbb4cbc3d344d4e7f209b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811055"
---
# <span data-ttu-id="95b3f-103">開始使用 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="95b3f-103">Getting Started with MBAM 1.0</span></span>

> <span data-ttu-id="95b3f-104">**重要**MBAM 1.0 將于2021年9月14日結束支援。</span><span class="sxs-lookup"><span data-stu-id="95b3f-104">**IMPORTANT** MBAM 1.0 will reach end of support on September 14, 2021.</span></span> 
> <span data-ttu-id="95b3f-105">如需詳細資訊，請參閱我們的 [[生命週期] 頁面](https://support.microsoft.com/lifecycle/search?alpha=Microsoft%20BitLocker%20Administration%20and%20Monitoring%201.0)。</span><span class="sxs-lookup"><span data-stu-id="95b3f-105">See our [lifecycle page](https://support.microsoft.com/lifecycle/search?alpha=Microsoft%20BitLocker%20Administration%20and%20Monitoring%201.0) for more information.</span></span> <span data-ttu-id="95b3f-106">我們建議您[遷移至 MBAM 2.5](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/upgrading-to-mbam-25-or-mbam-25-sp1-from-previous-versions)或其他支援版本的 MBAM，或將您的 BitLocker 管理遷移至[Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)。</span><span class="sxs-lookup"><span data-stu-id="95b3f-106">We recommend [migrating to MBAM 2.5](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/upgrading-to-mbam-25-or-mbam-25-sp1-from-previous-versions) or another supported version of MBAM, or migrating your BitLocker management to [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager).</span></span>


<span data-ttu-id="95b3f-107">Microsoft BitLocker 管理和監控（MBAM）需要進行完整的規劃，才能部署或使用其功能。</span><span class="sxs-lookup"><span data-stu-id="95b3f-107">Microsoft BitLocker Administration and Monitoring (MBAM) requires thorough planning before you deploy it or use its features.</span></span> <span data-ttu-id="95b3f-108">因為這個產品可能會影響貴組織中的每一部電腦，所以如果您不小心規劃您的部署，可能會中斷整個網路。</span><span class="sxs-lookup"><span data-stu-id="95b3f-108">Because this product can affect every computer in your organization, you might disrupt your entire network if you do not plan your deployment carefully.</span></span> <span data-ttu-id="95b3f-109">不過，如果您仔細規劃部署並加以管理，讓它符合您的業務需求，MBAM 可以協助降低您的管理負荷及總擁有權成本。</span><span class="sxs-lookup"><span data-stu-id="95b3f-109">However, if you plan your deployment carefully and manage it so that it meets your business needs, MBAM can help reduce your administrative overhead and total cost of ownership.</span></span>

<span data-ttu-id="95b3f-110">如果您是本產品的新使用者，建議您仔細閱讀檔。</span><span class="sxs-lookup"><span data-stu-id="95b3f-110">If you are new to this product, we recommend that you read the documentation thoroughly.</span></span> <span data-ttu-id="95b3f-111">在您將它部署到生產環境之前，我們也建議您在測試網路環境中驗證您的部署規劃。</span><span class="sxs-lookup"><span data-stu-id="95b3f-111">Before you deploy it to a production environment, we also recommend that you validate your deployment plan in a test network environment.</span></span> <span data-ttu-id="95b3f-112">您也可以考慮參與相關技術的課程。</span><span class="sxs-lookup"><span data-stu-id="95b3f-112">You might also consider taking a class about relevant technologies.</span></span> <span data-ttu-id="95b3f-113">如需 Microsoft 訓練商機的詳細資訊，請參閱 Microsoft 訓練概覽 <https://go.microsoft.com/fwlink/p/?LinkId=80347> 。</span><span class="sxs-lookup"><span data-stu-id="95b3f-113">For more information about Microsoft training opportunities, see the Microsoft Training Overview at <https://go.microsoft.com/fwlink/p/?LinkId=80347>.</span></span>

<span data-ttu-id="95b3f-114">**記事** 您可以在以下網址找到本檔與 MBAM 評估指南的可下載版本 <https://go.microsoft.com/fwlink/p/?LinkId=225356> 。</span><span class="sxs-lookup"><span data-stu-id="95b3f-114">**Note** You can find a downloadable version of this documentation and the MBAM Evaluation Guide at <https://go.microsoft.com/fwlink/p/?LinkId=225356>.</span></span>

 

<span data-ttu-id="95b3f-115">MBAM 系統管理員指南的本節包含 MBAM 的高層資訊，可讓您在開始進行部署規劃之前，提供對產品的基本瞭解。</span><span class="sxs-lookup"><span data-stu-id="95b3f-115">This section of the MBAM Administrator’s Guide includes high-level information about MBAM to provide you with a basic understanding of the product before you begin the deployment planning.</span></span> <span data-ttu-id="95b3f-116">您可以在 [MBAM] 檔資源下載頁面上找到其他 MBAM 檔 <https://go.microsoft.com/fwlink/p/?LinkId=258391> 。</span><span class="sxs-lookup"><span data-stu-id="95b3f-116">Additional MBAM documentation can be found on the MBAM Documentation Resources Download page at <https://go.microsoft.com/fwlink/p/?LinkId=258391>.</span></span>

## <span data-ttu-id="95b3f-117">MBAM 1.0 快速入門</span><span class="sxs-lookup"><span data-stu-id="95b3f-117">Getting started with MBAM 1.0</span></span>


-   [<span data-ttu-id="95b3f-118">關於 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="95b3f-118">About MBAM 1.0</span></span>](about-mbam-10.md)

    <span data-ttu-id="95b3f-119">提供 MBAM 的高層概覽，以及如何在您的組織中使用它。</span><span class="sxs-lookup"><span data-stu-id="95b3f-119">Provides a high-level overview of MBAM and how it can be used in your organization.</span></span>

-   [<span data-ttu-id="95b3f-120">評估 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="95b3f-120">Evaluating MBAM 1.0</span></span>](evaluating-mbam-10.md)

    <span data-ttu-id="95b3f-121">提供如何針對貴組織中使用的最佳評估 MBAM 的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="95b3f-121">Provides information about how you can best evaluate MBAM for use in your organization.</span></span>

-   [<span data-ttu-id="95b3f-122">MBAM 1.0 的高階架構</span><span class="sxs-lookup"><span data-stu-id="95b3f-122">High Level Architecture for MBAM 1.0</span></span>](high-level-architecture-for-mbam-10.md)

    <span data-ttu-id="95b3f-123">提供 MBAM 功能及它們共同運作方式的描述。</span><span class="sxs-lookup"><span data-stu-id="95b3f-123">Provides a description of the MBAM features and how they work together.</span></span>

-   [<span data-ttu-id="95b3f-124">MBAM 1.0 的協助工具</span><span class="sxs-lookup"><span data-stu-id="95b3f-124">Accessibility for MBAM 1.0</span></span>](accessibility-for-mbam-10.md)

    <span data-ttu-id="95b3f-125">提供有關讓殘障人士更容易存取本產品及其對應檔的功能與服務的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="95b3f-125">Provides information about features and services that make this product and its corresponding documentation more accessible for people with disabilities.</span></span>

## <a href="" id="other-resources-for-this-product-"></a><span data-ttu-id="95b3f-126">此產品的其他資源</span><span class="sxs-lookup"><span data-stu-id="95b3f-126">Other resources for this product</span></span>


-   [<span data-ttu-id="95b3f-127">Microsoft BitLocker 管理和監視1管理員指南</span><span class="sxs-lookup"><span data-stu-id="95b3f-127">Microsoft BitLocker Administration and Monitoring 1 Administrator's Guide</span></span>](index.md)

-   [<span data-ttu-id="95b3f-128">MBAM 1.0 規劃</span><span class="sxs-lookup"><span data-stu-id="95b3f-128">Planning for MBAM 1.0</span></span>](planning-for-mbam-10.md)

-   [<span data-ttu-id="95b3f-129">部署 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="95b3f-129">Deploying MBAM 1.0</span></span>](deploying-mbam-10.md)

-   [<span data-ttu-id="95b3f-130">適用於 MBAM 1.0 的操作</span><span class="sxs-lookup"><span data-stu-id="95b3f-130">Operations for MBAM 1.0</span></span>](operations-for-mbam-10.md)

-   [<span data-ttu-id="95b3f-131">MBAM 1.0 疑難排解</span><span class="sxs-lookup"><span data-stu-id="95b3f-131">Troubleshooting MBAM 1.0</span></span>](troubleshooting-mbam-10.md)

 

 





