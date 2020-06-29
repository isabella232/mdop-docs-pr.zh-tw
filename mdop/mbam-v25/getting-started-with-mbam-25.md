---
title: 開始使用 MBAM 2.5
description: 開始使用 MBAM 2.5
author: dansimp
ms.assetid: 23d0cfbb-e2ef-4c34-bf29-1b7ab4c48f00
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 1ddab83d85ecdaf49827114167bc006c820e8cd8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809759"
---
# <span data-ttu-id="01f09-103">開始使用 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="01f09-103">Getting Started with MBAM 2.5</span></span>


<span data-ttu-id="01f09-104">本主題提供的連結清單可協助您瞭解 Microsoft BitLocker 管理和監控（MBAM）2.5、其用途、功能、建議的架構，以及在測試環境中評估 MBAM 的步驟。</span><span class="sxs-lookup"><span data-stu-id="01f09-104">This topic provides a list of links to help you learn about Microsoft BitLocker Administration and Monitoring (MBAM) 2.5, its purpose, features, recommended architecture, and steps for evaluating MBAM in a test environment.</span></span>

<span data-ttu-id="01f09-105">請參閱下列資源以取得其他 MBAM 檔：</span><span class="sxs-lookup"><span data-stu-id="01f09-105">See the following resources for additional MBAM documentation:</span></span>

-   [<span data-ttu-id="01f09-106">Microsoft BitLocker 管理和監控部署指南</span><span class="sxs-lookup"><span data-stu-id="01f09-106">Microsoft BitLocker Administration and Monitoring Deployment Guide</span></span>](https://go.microsoft.com/fwlink/?LinkId=396653)

<span data-ttu-id="01f09-107">在您將 MBAM 部署到生產環境之前，我們建議您在測試環境中驗證您的部署規劃。</span><span class="sxs-lookup"><span data-stu-id="01f09-107">Before you deploy MBAM to a production environment, we recommend that you validate your deployment plan in a test environment.</span></span>

## <span data-ttu-id="01f09-108">MBAM 2.5 快速入門</span><span class="sxs-lookup"><span data-stu-id="01f09-108">Getting started with MBAM 2.5</span></span>


<span data-ttu-id="01f09-109">開始規劃 MBAM 部署之前，請先複習下列主題。</span><span class="sxs-lookup"><span data-stu-id="01f09-109">Before you start planning your MBAM deployment, review the following topics.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="01f09-110">主題描述</span><span class="sxs-lookup"><span data-stu-id="01f09-110">Topic description</span></span></th>
<th align="left"><span data-ttu-id="01f09-111">主題的連結</span><span class="sxs-lookup"><span data-stu-id="01f09-111">Links to topics</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="01f09-112">MBAM 2.5 的高層概覽，說明您可以在組織中使用它的方式。</span><span class="sxs-lookup"><span data-stu-id="01f09-112">High-level overview of MBAM 2.5 that describes how you can use it in your organization.</span></span></p></td>
<td align="left"><p><a href="about-mbam-25.md" data-raw-source="[About MBAM 2.5](about-mbam-25.md)"><span data-ttu-id="01f09-113">關於 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="01f09-113">About MBAM 2.5</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="01f09-114">[版本資訊]，其中列出產品的已知問題。</span><span class="sxs-lookup"><span data-stu-id="01f09-114">Release notes, which lists known issues in the product.</span></span></p></td>
<td align="left"><p><a href="release-notes-for-mbam-25.md" data-raw-source="[Release Notes for MBAM 2.5](release-notes-for-mbam-25.md)"><span data-ttu-id="01f09-115">MBAM 2.5 版本資訊</span><span class="sxs-lookup"><span data-stu-id="01f09-115">Release Notes for MBAM 2.5</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="01f09-116">有關如何在測試環境中評估 MBAM 2.5 的資訊。</span><span class="sxs-lookup"><span data-stu-id="01f09-116">Information about how you can evaluate MBAM 2.5 in a test environment.</span></span></p></td>
<td align="left"><p><a href="evaluating-mbam-25-in-a-test-environment.md" data-raw-source="[Evaluating MBAM 2.5 in a Test Environment](evaluating-mbam-25-in-a-test-environment.md)"><span data-ttu-id="01f09-117">在測試環境中評估 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="01f09-117">Evaluating MBAM 2.5 in a Test Environment</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="01f09-118">MBAM 2.5 功能的描述，以及在生產環境中獨立與 Configuration Manager 整合拓朴的建議結構。</span><span class="sxs-lookup"><span data-stu-id="01f09-118">Description of the MBAM 2.5 features and the recommended architecture of the Stand-alone and Configuration Manager Integration topologies in a production environment.</span></span></p></td>
<td align="left"><p><a href="high-level-architecture-for-mbam-25.md" data-raw-source="[High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md)"><span data-ttu-id="01f09-119">MBAM 2.5 的概要架構</span><span class="sxs-lookup"><span data-stu-id="01f09-119">High-Level Architecture for MBAM 2.5</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="01f09-120">每個 MBAM 伺服器功能的描述與圖例，不含建議的架構。</span><span class="sxs-lookup"><span data-stu-id="01f09-120">Description and illustration of each MBAM Server feature, without the recommended architecture.</span></span></p></td>
<td align="left"><p><a href="illustrated-features-of-an-mbam-25-deployment.md" data-raw-source="[Illustrated Features of an MBAM 2.5 Deployment](illustrated-features-of-an-mbam-25-deployment.md)"><span data-ttu-id="01f09-121">MBAM 2.5 部署的功能圖例</span><span class="sxs-lookup"><span data-stu-id="01f09-121">Illustrated Features of an MBAM 2.5 Deployment</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="01f09-122">說明可供 MBAM 2.5 使用的鍵盤快速鍵。</span><span class="sxs-lookup"><span data-stu-id="01f09-122">Describes the keyboard shortcuts that are available for MBAM 2.5.</span></span></p></td>
<td align="left"><p><a href="accessibility-for-mbam-25.md" data-raw-source="[Accessibility for MBAM 2.5](accessibility-for-mbam-25.md)"><span data-ttu-id="01f09-123">MBAM 2.5 的協助工具</span><span class="sxs-lookup"><span data-stu-id="01f09-123">Accessibility for MBAM 2.5</span></span></a></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="01f09-124">如何取得 MDOP 技術</span><span class="sxs-lookup"><span data-stu-id="01f09-124">How to get MDOP technologies</span></span>


<span data-ttu-id="01f09-125">MBAM 2.5 是 Microsoft 桌面優化套件（MDOP）的一部分。</span><span class="sxs-lookup"><span data-stu-id="01f09-125">MBAM 2.5 is a part of the Microsoft Desktop Optimization Pack (MDOP).</span></span> <span data-ttu-id="01f09-126">MDOP 是 Microsoft 軟體保證的一部分。</span><span class="sxs-lookup"><span data-stu-id="01f09-126">MDOP is part of Microsoft Software Assurance.</span></span> <span data-ttu-id="01f09-127">如需有關 Microsoft 軟體保證及取得 MDOP 的詳細資訊，請參閱[如何取得 mdop](https://go.microsoft.com/fwlink/?LinkId=322049) （ https://go.microsoft.com/fwlink/?LinkId=322049) 。</span><span class="sxs-lookup"><span data-stu-id="01f09-127">For more information about Microsoft Software Assurance and about acquiring MDOP, see [How Do I Get MDOP](https://go.microsoft.com/fwlink/?LinkId=322049) (https://go.microsoft.com/fwlink/?LinkId=322049).</span></span>

## <a href="" id="other-resources-for-this-product-"></a><span data-ttu-id="01f09-128">此產品的其他資源</span><span class="sxs-lookup"><span data-stu-id="01f09-128">Other resources for this product</span></span>


[<span data-ttu-id="01f09-129">Microsoft BitLocker Administration and Monitoring 2.5</span><span class="sxs-lookup"><span data-stu-id="01f09-129">Microsoft BitLocker Administration and Monitoring 2.5</span></span>](index.md)

[<span data-ttu-id="01f09-130">MBAM 2.5 規劃</span><span class="sxs-lookup"><span data-stu-id="01f09-130">Planning for MBAM 2.5</span></span>](planning-for-mbam-25.md)

[<span data-ttu-id="01f09-131">部署 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="01f09-131">Deploying MBAM 2.5</span></span>](deploying-mbam-25.md)

[<span data-ttu-id="01f09-132">適用於 MBAM 2.5 的操作</span><span class="sxs-lookup"><span data-stu-id="01f09-132">Operations for MBAM 2.5</span></span>](operations-for-mbam-25.md)

[<span data-ttu-id="01f09-133">MBAM 2.5 疑難排解</span><span class="sxs-lookup"><span data-stu-id="01f09-133">Troubleshooting MBAM 2.5</span></span>](troubleshooting-mbam-25.md)

[<span data-ttu-id="01f09-134">MBAM 2.5 技術參考資料</span><span class="sxs-lookup"><span data-stu-id="01f09-134">Technical Reference for MBAM 2.5</span></span>](technical-reference-for-mbam-25.md)

## <span data-ttu-id="01f09-135">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="01f09-135">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="01f09-136">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="01f09-136">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="01f09-137">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="01f09-137">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>

 

 





