---
title: MBAM 1.0 伺服器部署規劃
description: MBAM 1.0 伺服器部署規劃
author: dansimp
ms.assetid: 3cbef284-3092-4c42-9234-2826b18ddef1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 76ff9c444ce3f9c39161341610fb0cd9a763dc6d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800091"
---
# <span data-ttu-id="e6752-103">MBAM 1.0 伺服器部署規劃</span><span class="sxs-lookup"><span data-stu-id="e6752-103">Planning for MBAM 1.0 Server Deployment</span></span>


<span data-ttu-id="e6752-104">Microsoft BitLocker 管理與監視（MBAM）伺服器基礎結構，視您的企業需求而定，您可以在一或多台伺服器電腦上安裝一組伺服器功能。</span><span class="sxs-lookup"><span data-stu-id="e6752-104">The Microsoft BitLocker Administration and Monitoring (MBAM) server infrastructure depends on a set of server features that can be installed on one or more server computers, based on the requirements of your enterprise.</span></span>

## <span data-ttu-id="e6752-105">規劃 MBAM Server 部署</span><span class="sxs-lookup"><span data-stu-id="e6752-105">Planning for MBAM Server deployment</span></span>


<span data-ttu-id="e6752-106">下列 MBAM 功能代表 MBAM 伺服器部署的伺服器基礎結構：</span><span class="sxs-lookup"><span data-stu-id="e6752-106">The following MBAM features represent the server infrastructure for an MBAM server deployment:</span></span>

-   <span data-ttu-id="e6752-107">恢復與硬體資料庫</span><span class="sxs-lookup"><span data-stu-id="e6752-107">Recovery and Hardware Database</span></span>

-   <span data-ttu-id="e6752-108">合規性和審核資料庫</span><span class="sxs-lookup"><span data-stu-id="e6752-108">Compliance and Audit Database</span></span>

-   <span data-ttu-id="e6752-109">合規性與審計報告</span><span class="sxs-lookup"><span data-stu-id="e6752-109">Compliance and Audit Reports</span></span>

-   <span data-ttu-id="e6752-110">管理和監控伺服器</span><span class="sxs-lookup"><span data-stu-id="e6752-110">Administration and Monitoring Server</span></span>

<span data-ttu-id="e6752-111">您可以根據您的可伸縮性需求，在不同的設定中安裝 MBAM 伺服器資料庫和功能。</span><span class="sxs-lookup"><span data-stu-id="e6752-111">MBAM server databases and features can be installed in different configurations, depending on your scalability needs.</span></span> <span data-ttu-id="e6752-112">所有的 MBAM 伺服器功能都可以安裝在單一伺服器上，或是分佈在多個伺服器上。</span><span class="sxs-lookup"><span data-stu-id="e6752-112">All MBAM Server features can be installed on a single server or distributed across multiple servers.</span></span> <span data-ttu-id="e6752-113">一般來說，我們建議您針對生產環境使用三台伺服器或五台伺服器設定，不過，您也可以根據自己的計算需求，使用兩個或四個伺服器的配置。</span><span class="sxs-lookup"><span data-stu-id="e6752-113">Generally, we recommend that you use a three-server or five-server configuration for production environments, although configurations of two or four servers can also be used, depending on your computing needs.</span></span>

<span data-ttu-id="e6752-114">**記事** 如需 MBAM 和建議部署拓撲的效能伸縮性的詳細資訊，請參閱 MBAM 可伸縮性及高可用性指南白皮書 <https://go.microsoft.com/fwlink/p/?LinkId=258314> 。</span><span class="sxs-lookup"><span data-stu-id="e6752-114">**Note** For more information about performance scalability of MBAM and recommended deployment topologies, see the MBAM Scalability and High-Availability Guide white paper at <https://go.microsoft.com/fwlink/p/?LinkId=258314>.</span></span>

 

<span data-ttu-id="e6752-115">每個 MBAM 功能都有特定的先決條件。</span><span class="sxs-lookup"><span data-stu-id="e6752-115">Each MBAM feature has specific prerequisites.</span></span> <span data-ttu-id="e6752-116">如需伺服器功能必備元件和硬體及軟體需求的完整清單，請參閱[MBAM 1.0 部署先決條件](mbam-10-deployment-prerequisites.md)和[MBAM 1.0 支援](mbam-10-supported-configurations.md)的設定。</span><span class="sxs-lookup"><span data-stu-id="e6752-116">For a full list of server feature prerequisites and hardware and software requirements, see [MBAM 1.0 Deployment Prerequisites](mbam-10-deployment-prerequisites.md) and [MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md).</span></span>

<span data-ttu-id="e6752-117">除了伺服器相關的 MBAM 功能之外，伺服器安裝應用程式還包含 MBAM 群組原則範本。</span><span class="sxs-lookup"><span data-stu-id="e6752-117">In addition to the server-related MBAM features, the server Setup application includes an MBAM Group Policy template.</span></span> <span data-ttu-id="e6752-118">此範本可安裝在任何能夠執行群組原則管理主控台（GPMC）或高級群組原則管理（AGPM）的電腦上。</span><span class="sxs-lookup"><span data-stu-id="e6752-118">This template can be installed on any computer that is able to run the Group Policy Management Console (GPMC) or Advanced Group Policy Management (AGPM).</span></span>

## <span data-ttu-id="e6752-119">部署 MBAM 伺服器功能的順序</span><span class="sxs-lookup"><span data-stu-id="e6752-119">Order of deployment of MBAM Server Features</span></span>


<span data-ttu-id="e6752-120">當您部署 MBAM 伺服器功能時，請依照下列順序安裝這些功能：</span><span class="sxs-lookup"><span data-stu-id="e6752-120">When you deploy the MBAM Server features, install the features in the following order:</span></span>

1.  <span data-ttu-id="e6752-121">恢復與硬體資料庫</span><span class="sxs-lookup"><span data-stu-id="e6752-121">Recovery and Hardware Database</span></span>

2.  <span data-ttu-id="e6752-122">合規性和審核資料庫</span><span class="sxs-lookup"><span data-stu-id="e6752-122">Compliance and Audit Database</span></span>

3.  <span data-ttu-id="e6752-123">合規性審核與報告</span><span class="sxs-lookup"><span data-stu-id="e6752-123">Compliance Audit and Reports</span></span>

4.  <span data-ttu-id="e6752-124">管理和監控伺服器</span><span class="sxs-lookup"><span data-stu-id="e6752-124">Administration and Monitoring Server</span></span>

5.  <span data-ttu-id="e6752-125">原則範本</span><span class="sxs-lookup"><span data-stu-id="e6752-125">Policy Template</span></span>

<span data-ttu-id="e6752-126">**記事** 追蹤安裝每個功能的電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="e6752-126">**Note** Keep track of the names of the computers on which you install each feature.</span></span> <span data-ttu-id="e6752-127">您將會在整個安裝過程中使用此資訊。</span><span class="sxs-lookup"><span data-stu-id="e6752-127">You will use this information throughout the installation process.</span></span> <span data-ttu-id="e6752-128">您可以列印並使用部署檢查清單來協助您完成安裝程式。</span><span class="sxs-lookup"><span data-stu-id="e6752-128">You can print and use a deployment checklist to assist you in the installation process.</span></span> <span data-ttu-id="e6752-129">如需 MBAM 部署檢查清單的詳細資訊，請參閱[MBAM 1.0 部署檢查清單](mbam-10-deployment-checklist.md)。</span><span class="sxs-lookup"><span data-stu-id="e6752-129">For more information about the MBAM deployment checklist, see [MBAM 1.0 Deployment Checklist](mbam-10-deployment-checklist.md).</span></span>

 

## <span data-ttu-id="e6752-130">相關主題</span><span class="sxs-lookup"><span data-stu-id="e6752-130">Related topics</span></span>


[<span data-ttu-id="e6752-131">規劃部署 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="e6752-131">Planning to Deploy MBAM 1.0</span></span>](planning-to-deploy-mbam-10.md)

[<span data-ttu-id="e6752-132">部署 MBAM 1.0 伺服器基礎結構</span><span class="sxs-lookup"><span data-stu-id="e6752-132">Deploying the MBAM 1.0 Server Infrastructure</span></span>](deploying-the-mbam-10-server-infrastructure.md)

 

 





