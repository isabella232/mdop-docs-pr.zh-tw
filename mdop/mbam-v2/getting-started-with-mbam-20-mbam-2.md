---
title: 開始使用 MBAM 2.0
description: 開始使用 MBAM 2.0
author: dansimp
ms.assetid: 29f5c9af-5bbf-4d37-aa0f-0716046904af
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7c683e3d8718da24ebd2164328bda0dab0123037
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811282"
---
# <span data-ttu-id="f1ef3-103">開始使用 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="f1ef3-103">Getting Started with MBAM 2.0</span></span>


<span data-ttu-id="f1ef3-104">Microsoft BitLockerAdministration 和 Monitoring （MBAM）2.0 需要在部署前進行完整的規劃，或使用其功能。</span><span class="sxs-lookup"><span data-stu-id="f1ef3-104">Microsoft BitLockerAdministration and Monitoring(MBAM)2.0 requires thorough planning before you deploy it or use its features.</span></span> <span data-ttu-id="f1ef3-105">因為這個產品可能會影響貴組織中的每一部電腦，所以如果您不小心規劃您的部署，可能會中斷整個網路。</span><span class="sxs-lookup"><span data-stu-id="f1ef3-105">Because this product can affect every computer in your organization, you might disrupt your entire network if you do not plan your deployment carefully.</span></span> <span data-ttu-id="f1ef3-106">不過，如果您仔細規劃部署並加以管理，讓它符合您的業務需求，BitLockerAdministration 和監控2.0 可協助降低您的管理負荷及擁有權總成本。</span><span class="sxs-lookup"><span data-stu-id="f1ef3-106">However, if you plan your deployment carefully and manage it so that it meets your business requirements, BitLockerAdministration and Monitoring2.0 can help reduce your administrative overhead and total cost of ownership.</span></span>

<span data-ttu-id="f1ef3-107">如果您是本產品的新使用者，建議您仔細閱讀檔。</span><span class="sxs-lookup"><span data-stu-id="f1ef3-107">If you are new to this product, we recommend that you read the documentation carefully.</span></span> <span data-ttu-id="f1ef3-108">若要取得 MBAM 軟體，請參閱[如何取得 MDOP？](https://go.microsoft.com/fwlink/p/?LinkId=322049)。</span><span class="sxs-lookup"><span data-stu-id="f1ef3-108">To get the MBAM software, see [How Do I Get MDOP?](https://go.microsoft.com/fwlink/p/?LinkId=322049).</span></span> <span data-ttu-id="f1ef3-109">在您將 MBAM 部署到生產環境之前，我們也建議您在測試環境中驗證您的部署規劃。</span><span class="sxs-lookup"><span data-stu-id="f1ef3-109">Before you deploy MBAM to a production environment, we also recommend that you validate your deployment plan in a test environment.</span></span> <span data-ttu-id="f1ef3-110">您也可以考慮參與相關技術的課程。</span><span class="sxs-lookup"><span data-stu-id="f1ef3-110">You might also consider taking a class about relevant technologies.</span></span> <span data-ttu-id="f1ef3-111">如需 Microsoft 訓練商機的詳細資訊，請參閱 Microsoft 訓練概覽 <https://go.microsoft.com/fwlink/p/?LinkId=80347> 。</span><span class="sxs-lookup"><span data-stu-id="f1ef3-111">For more information about Microsoft training opportunities, see the Microsoft Training Overview at <https://go.microsoft.com/fwlink/p/?LinkId=80347>.</span></span>

<span data-ttu-id="f1ef3-112">MBAM 2.0 系統管理員指南的本節包含 MBAM 2.0 的高層資訊，在您開始規劃部署之前，先提供對產品的基本瞭解。</span><span class="sxs-lookup"><span data-stu-id="f1ef3-112">This section of the MBAM2.0 Administrator’s Guide includes high-level information about MBAM2.0 to provide a basic understanding of the product before you begin to plan deployment.</span></span> <span data-ttu-id="f1ef3-113">如需使用 Configuration Manager 整合拓朴部署 MBAM 的特定資訊，請參閱[使用 MBAM 與 Configuration manager](using-mbam-with-configuration-manager.md)。</span><span class="sxs-lookup"><span data-stu-id="f1ef3-113">For specific information about deploying MBAM with the Configuration Manager integrated topology, see [Using MBAM with Configuration Manager](using-mbam-with-configuration-manager.md).</span></span> <span data-ttu-id="f1ef3-114">您可以在 [Microsoft BitLocker 管理與監控] （MBAM）檔資源下載頁面上找到其他 MBAM 檔 <https://go.microsoft.com/fwlink/p/?LinkId=258391> 。</span><span class="sxs-lookup"><span data-stu-id="f1ef3-114">You can find additional MBAM documentation on the Microsoft BitLocker Administration and Monitoring (MBAM) Documentation Resources Download Page at <https://go.microsoft.com/fwlink/p/?LinkId=258391>.</span></span>

## <span data-ttu-id="f1ef3-115">MBAM 2.0 快速入門</span><span class="sxs-lookup"><span data-stu-id="f1ef3-115">Getting Started with MBAM2.0</span></span>


-   [<span data-ttu-id="f1ef3-116">關於 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="f1ef3-116">About MBAM 2.0</span></span>](about-mbam-20-mbam-2.md)

    <span data-ttu-id="f1ef3-117">提供 MBAM 2.0 的高層次概覽，並說明如何在您的組織中使用它。</span><span class="sxs-lookup"><span data-stu-id="f1ef3-117">Provides a high-level overview of MBAM2.0 and describes how it can be used in your organization.</span></span>

-   [<span data-ttu-id="f1ef3-118">評估 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="f1ef3-118">Evaluating MBAM 2.0</span></span>](evaluating-mbam-20-mbam-2.md)

    <span data-ttu-id="f1ef3-119">提供如何最佳評估 MBAM 2.0 以供貴組織使用的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="f1ef3-119">Provides information about how you can best evaluate MBAM2.0 for use in your organization.</span></span>

-   [<span data-ttu-id="f1ef3-120">MBAM 2.0 的概要架構</span><span class="sxs-lookup"><span data-stu-id="f1ef3-120">High-Level Architecture for MBAM 2.0</span></span>](high-level-architecture-for-mbam-20-mbam-2.md)

    <span data-ttu-id="f1ef3-121">說明生產環境的 MBAM 2.0 功能及建議的架構。</span><span class="sxs-lookup"><span data-stu-id="f1ef3-121">Describes the MBAM2.0 features and the recommended architecture for a production environment.</span></span>

-   [<span data-ttu-id="f1ef3-122">MBAM 2.0 的協助工具</span><span class="sxs-lookup"><span data-stu-id="f1ef3-122">Accessibility for MBAM 2.0</span></span>](accessibility-for-mbam-20-mbam-2.md)

    <span data-ttu-id="f1ef3-123">說明可用於 MBAM 2.0 的鍵盤快速鍵。</span><span class="sxs-lookup"><span data-stu-id="f1ef3-123">Describes the keyboard shortcuts that are available for MBAM2.0.</span></span>

## <a href="" id="other-resources-for-this-product-"></a><span data-ttu-id="f1ef3-124">此產品的其他資源</span><span class="sxs-lookup"><span data-stu-id="f1ef3-124">Other Resources for this Product</span></span>


[<span data-ttu-id="f1ef3-125">Microsoft BitLocker 管理和監視2管理員指南</span><span class="sxs-lookup"><span data-stu-id="f1ef3-125">Microsoft BitLocker Administration and Monitoring 2 Administrator's Guide</span></span>](index.md)

[<span data-ttu-id="f1ef3-126">MBAM 2.0 規劃</span><span class="sxs-lookup"><span data-stu-id="f1ef3-126">Planning for MBAM 2.0</span></span>](planning-for-mbam-20-mbam-2.md)

[<span data-ttu-id="f1ef3-127">部署 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="f1ef3-127">Deploying MBAM 2.0</span></span>](deploying-mbam-20-mbam-2.md)

[<span data-ttu-id="f1ef3-128">適用於 MBAM 2.0 的操作</span><span class="sxs-lookup"><span data-stu-id="f1ef3-128">Operations for MBAM 2.0</span></span>](operations-for-mbam-20-mbam-2.md)

[<span data-ttu-id="f1ef3-129">MBAM 2.0 疑難排解</span><span class="sxs-lookup"><span data-stu-id="f1ef3-129">Troubleshooting MBAM 2.0</span></span>](troubleshooting-mbam-20-mbam-2.md)

 

 





