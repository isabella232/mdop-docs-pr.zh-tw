---
title: 部署 DaRT 8.0
description: 部署 DaRT 8.0
author: dansimp
ms.assetid: 5a976d4e-3372-4ef6-9095-1b48e99af21b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 7cc847836587abb0eaa22c009c8fd18d0ba0899b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810389"
---
# <span data-ttu-id="d4f22-103">部署 DaRT 8.0</span><span class="sxs-lookup"><span data-stu-id="d4f22-103">Deploying DaRT 8.0</span></span>


<span data-ttu-id="d4f22-104">Microsoft Diagnostics 與修復工具組（DaRT）8.0 支援多種不同的部署配置。</span><span class="sxs-lookup"><span data-stu-id="d4f22-104">Microsoft Diagnostics and Recovery Toolset (DaRT) 8.0 supports a number of different deployment configurations.</span></span> <span data-ttu-id="d4f22-105">本節包含您應該考慮的有關 DaRT 8.0 和逐步程式部署的資訊，以協助您成功執行必須在部署的不同階段完成的工作。</span><span class="sxs-lookup"><span data-stu-id="d4f22-105">This section includes information you should consider about the deployment of DaRT 8.0 and step-by-step procedures to help you successfully perform the tasks that you must complete at different stages of your deployment.</span></span>

## <span data-ttu-id="d4f22-106">部署資訊</span><span class="sxs-lookup"><span data-stu-id="d4f22-106">Deployment Information</span></span>


-   [<span data-ttu-id="d4f22-107">部署 DaRT 8.0 到系統管理員電腦</span><span class="sxs-lookup"><span data-stu-id="d4f22-107">Deploying DaRT 8.0 to Administrator Computers</span></span>](deploying-dart-80-to-administrator-computers-dart-8.md)

    <span data-ttu-id="d4f22-108">本節說明您需求的不同 DaRT 部署選項，並說明如何進行部署。</span><span class="sxs-lookup"><span data-stu-id="d4f22-108">This section describes the different DaRT deployment options for your requirements and explains how to deploy them.</span></span>

-   [<span data-ttu-id="d4f22-109">建立 DaRT 8.0 復原映像</span><span class="sxs-lookup"><span data-stu-id="d4f22-109">Creating the DaRT 8.0 Recovery Image</span></span>](creating-the-dart-80-recovery-image-dart-8.md)

    <span data-ttu-id="d4f22-110">本節說明您可以用來建立 DaRT 復原影像的方法，並提供使用 DaRT 復原影像嚮導建立復原影像的指示。</span><span class="sxs-lookup"><span data-stu-id="d4f22-110">This section describes the methods you can use to create the DaRT recovery image and provides instructions to create the recovery image by using the DaRT Recovery Image wizard.</span></span>

-   [<span data-ttu-id="d4f22-111">部署 DaRT 復原映像</span><span class="sxs-lookup"><span data-stu-id="d4f22-111">Deploying the DaRT Recovery Image</span></span>](deploying-the-dart-recovery-image-dart-8.md)

    <span data-ttu-id="d4f22-112">本節提供的資訊可協助您針對您的需求決定最佳的 DaRT 復原影像部署選項，並提供如何部署恢復影像的指示。</span><span class="sxs-lookup"><span data-stu-id="d4f22-112">This section provides information to help you decide on the best DaRT recovery image deployment option for your requirements and provides instructions on how to deploy the recovery image.</span></span>

-   [<span data-ttu-id="d4f22-113">DaRT 8.0 部署檢查清單</span><span class="sxs-lookup"><span data-stu-id="d4f22-113">DaRT 8.0 Deployment Checklist</span></span>](dart-80-deployment-checklist-dart-8.md)

    <span data-ttu-id="d4f22-114">本節包含可協助您部署 DaRT 的部署檢查清單。</span><span class="sxs-lookup"><span data-stu-id="d4f22-114">This section contains a deployment checklist that can help you to deploy DaRT.</span></span>

### <span data-ttu-id="d4f22-115">如何取得 DaRT</span><span class="sxs-lookup"><span data-stu-id="d4f22-115">How to get DaRT</span></span>

<span data-ttu-id="d4f22-116">這項技術是 Microsoft 桌面優化套件（MDOP）的一部分。</span><span class="sxs-lookup"><span data-stu-id="d4f22-116">This technology is a part of the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="d4f22-117">企業客戶可以使用 Microsoft 軟體保證進行 MDOP。</span><span class="sxs-lookup"><span data-stu-id="d4f22-117">Enterprise customers can get MDOP with Microsoft Software Assurance.</span></span> <span data-ttu-id="d4f22-118">如需 Microsoft 軟體保證及取得 MDOP 的詳細資訊，請參閱[如何取得 mdop](https://go.microsoft.com/fwlink/p/?LinkId=322049) （ https://go.microsoft.com/fwlink/p/?LinkId=322049) 。</span><span class="sxs-lookup"><span data-stu-id="d4f22-118">For more information about Microsoft Software Assurance and acquiring MDOP, see [How Do I Get MDOP](https://go.microsoft.com/fwlink/p/?LinkId=322049) (https://go.microsoft.com/fwlink/p/?LinkId=322049).</span></span>

## <span data-ttu-id="d4f22-119">部署 DaRT 的其他資源</span><span class="sxs-lookup"><span data-stu-id="d4f22-119">Other Resources for deploying DaRT</span></span>


[<span data-ttu-id="d4f22-120">診斷與修復工具組8管理員指南</span><span class="sxs-lookup"><span data-stu-id="d4f22-120">Diagnostics and Recovery Toolset 8 Administrator's Guide</span></span>](index.md)

[<span data-ttu-id="d4f22-121">開始使用 DaRT 8.0</span><span class="sxs-lookup"><span data-stu-id="d4f22-121">Getting Started with DaRT 8.0</span></span>](getting-started-with-dart-80-dart-8.md)

[<span data-ttu-id="d4f22-122">規劃 DaRT 8.0</span><span class="sxs-lookup"><span data-stu-id="d4f22-122">Planning for DaRT 8.0</span></span>](planning-for-dart-80-dart-8.md)

[<span data-ttu-id="d4f22-123">適用於 DaRT 8.0 的操作</span><span class="sxs-lookup"><span data-stu-id="d4f22-123">Operations for DaRT 8.0</span></span>](operations-for-dart-80-dart-8.md)

[<span data-ttu-id="d4f22-124">疑難排解 DaRT 8.0</span><span class="sxs-lookup"><span data-stu-id="d4f22-124">Troubleshooting DaRT 8.0</span></span>](troubleshooting-dart-80-dart-8.md)

 

 





