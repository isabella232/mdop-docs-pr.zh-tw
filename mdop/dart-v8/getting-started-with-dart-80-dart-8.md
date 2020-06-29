---
title: 開始使用 DaRT 8.0
description: 開始使用 DaRT 8.0
author: dansimp
ms.assetid: 579d18c5-7434-4a0e-9725-fb81ca5e3c6d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 138700b01749a1dd3f75524673f2d7631d7fe97b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810424"
---
# <span data-ttu-id="be376-103">開始使用 DaRT 8.0</span><span class="sxs-lookup"><span data-stu-id="be376-103">Getting Started with DaRT 8.0</span></span>


<span data-ttu-id="be376-104">Microsoft Diagnostics 和復原工具組（DaRT）8.0 必須在部署前進行完整的規劃，或使用其功能。</span><span class="sxs-lookup"><span data-stu-id="be376-104">Microsoft Diagnostics and Recovery Toolset (DaRT) 8.0 requires thorough planning before you deploy it or use its features.</span></span> <span data-ttu-id="be376-105">如果您是本產品的新使用者，建議您仔細閱讀檔。</span><span class="sxs-lookup"><span data-stu-id="be376-105">If you are new to this product, we recommend that you read the documentation carefully.</span></span> <span data-ttu-id="be376-106">在您將產品部署到生產環境之前，我們也建議您在測試網路環境中驗證您的部署規劃。</span><span class="sxs-lookup"><span data-stu-id="be376-106">Before you deploy the product to a production environment, we also recommend that you validate your deployment plan in a test network environment.</span></span> <span data-ttu-id="be376-107">您也可以考慮參與相關技術的課程。</span><span class="sxs-lookup"><span data-stu-id="be376-107">You might also consider taking a class about relevant technologies.</span></span> <span data-ttu-id="be376-108">如需 Microsoft 訓練商機的詳細資訊，請參閱 Microsoft 訓練概覽 [https://go.microsoft.com/fwlink/p/?LinkId=80347](https://go.microsoft.com/fwlink/?LinkId=80347) 。</span><span class="sxs-lookup"><span data-stu-id="be376-108">For more information about Microsoft training opportunities, see the Microsoft Training Overview at [https://go.microsoft.com/fwlink/p/?LinkId=80347](https://go.microsoft.com/fwlink/?LinkId=80347).</span></span>

<span data-ttu-id="be376-109">**記事** 此系統管理員指南的可下載版本無法使用。</span><span class="sxs-lookup"><span data-stu-id="be376-109">**Note** A downloadable version of this administrator’s guide is not available.</span></span> <span data-ttu-id="be376-110">不過，您可以瞭解 TechNet 文件庫的特殊模式，讓您選取文章、將其群組在集合中，或在 <https://go.microsoft.com/fwlink/?LinkId=272493> （ https://go.microsoft.com/fwlink/?LinkId=272493) 。</span><span class="sxs-lookup"><span data-stu-id="be376-110">However, you can learn about a special mode of the TechNet Library that allows you to select articles, group them in a collection, and print them or export them to a file at <https://go.microsoft.com/fwlink/?LinkId=272493> (https://go.microsoft.com/fwlink/?LinkId=272493).</span></span>

<span data-ttu-id="be376-111">您也可以在中找到有關此產品的其他可下載資訊 <https://go.microsoft.com/fwlink/?LinkId=267420> 。</span><span class="sxs-lookup"><span data-stu-id="be376-111">Additional downloadable information about this product can also be found at <https://go.microsoft.com/fwlink/?LinkId=267420>.</span></span>

 

## <span data-ttu-id="be376-112">DaRT 8.0 快速入門</span><span class="sxs-lookup"><span data-stu-id="be376-112">Getting started with DaRT 8.0</span></span>


-   [<span data-ttu-id="be376-113">關於 DaRT 8.0</span><span class="sxs-lookup"><span data-stu-id="be376-113">About DaRT 8.0</span></span>](about-dart-80-dart-8.md)

    <span data-ttu-id="be376-114">提供與 DaRT 相關的資訊，包括 DaRT 8.0 的新功能。</span><span class="sxs-lookup"><span data-stu-id="be376-114">Provides information specifically related to DaRT, including what is new in DaRT 8.0.</span></span>

-   [<span data-ttu-id="be376-115">DaRT 8.0 中的工具簡介</span><span class="sxs-lookup"><span data-stu-id="be376-115">Overview of the Tools in DaRT 8.0</span></span>](overview-of-the-tools-in-dart-80-dart-8.md)

    <span data-ttu-id="be376-116">說明 DaRT 8.0 中的工具。</span><span class="sxs-lookup"><span data-stu-id="be376-116">Describes the tools in DaRT 8.0.</span></span>

-   [<span data-ttu-id="be376-117">DaRT 8.0 的協助工具</span><span class="sxs-lookup"><span data-stu-id="be376-117">Accessibility for DaRT 8.0</span></span>](accessibility-for-dart-80-dart-8.md)

    <span data-ttu-id="be376-118">提供有關讓殘障人士更容易存取本產品及其對應檔的功能與服務的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="be376-118">Provides information about features and services that make this product and its corresponding documentation more accessible for people with disabilities.</span></span>

## <span data-ttu-id="be376-119">如何取得 DaRT 8。0</span><span class="sxs-lookup"><span data-stu-id="be376-119">How to Get DaRT 8.0</span></span>


<span data-ttu-id="be376-120">DaRT 8.0 是 Microsoft 桌面優化套件（MDOP）的一部分。</span><span class="sxs-lookup"><span data-stu-id="be376-120">DaRT 8.0 is a part of the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="be376-121">MDOP 是 Microsoft 軟體保證的一部分。</span><span class="sxs-lookup"><span data-stu-id="be376-121">MDOP is part of Microsoft Software Assurance.</span></span> <span data-ttu-id="be376-122">如需 Microsoft 軟體保證及取得 MDOP 的詳細資訊，請參閱[如何取得 mdop](https://go.microsoft.com/fwlink/?LinkId=322049) （ https://go.microsoft.com/fwlink/?LinkId=322049) 。</span><span class="sxs-lookup"><span data-stu-id="be376-122">For more information about Microsoft Software Assurance and acquiring MDOP, see [How Do I Get MDOP](https://go.microsoft.com/fwlink/?LinkId=322049) (https://go.microsoft.com/fwlink/?LinkId=322049).</span></span>

## <a href="" id="other-resources-for-this-product-"></a><span data-ttu-id="be376-123">此產品的其他資源</span><span class="sxs-lookup"><span data-stu-id="be376-123">Other resources for this product</span></span>


[<span data-ttu-id="be376-124">診斷與修復工具組8管理員指南</span><span class="sxs-lookup"><span data-stu-id="be376-124">Diagnostics and Recovery Toolset 8 Administrator's Guide</span></span>](index.md)

[<span data-ttu-id="be376-125">規劃 DaRT 8.0</span><span class="sxs-lookup"><span data-stu-id="be376-125">Planning for DaRT 8.0</span></span>](planning-for-dart-80-dart-8.md)

[<span data-ttu-id="be376-126">部署 DaRT 8.0</span><span class="sxs-lookup"><span data-stu-id="be376-126">Deploying DaRT 8.0</span></span>](deploying-dart-80-dart-8.md)

[<span data-ttu-id="be376-127">適用於 DaRT 8.0 的操作</span><span class="sxs-lookup"><span data-stu-id="be376-127">Operations for DaRT 8.0</span></span>](operations-for-dart-80-dart-8.md)

[<span data-ttu-id="be376-128">疑難排解 DaRT 8.0</span><span class="sxs-lookup"><span data-stu-id="be376-128">Troubleshooting DaRT 8.0</span></span>](troubleshooting-dart-80-dart-8.md)

 

 





