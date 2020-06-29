---
title: 使用 MBAM 搭配 Configuration Manager
description: 使用 MBAM 搭配 Configuration Manager
author: dansimp
ms.assetid: 03868717-4aa7-4897-8166-9a3df5e9519e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9e3c5dd199010ac758ab701b0753d913ea323efd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810166"
---
# <span data-ttu-id="a7a1a-103">使用 MBAM 搭配 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="a7a1a-103">Using MBAM with Configuration Manager</span></span>


<span data-ttu-id="a7a1a-104">當您安裝 Microsoft BitLocker 管理和監控（MBAM）時，您可以選擇將 Microsoft BitLocker 管理和監視與 System Center Configuration Manager 整合在一起的安裝。</span><span class="sxs-lookup"><span data-stu-id="a7a1a-104">When you install Microsoft BitLocker Administration and Monitoring (MBAM), you can choose an installation that integrates Microsoft BitLocker Administration and Monitoring with System Center Configuration Manager.</span></span> <span data-ttu-id="a7a1a-105">如需支援的 Configuration Manager 版本清單，請參閱[規劃使用 Configuration Manager 部署 MBAM](planning-to-deploy-mbam-with-configuration-manager-2.md)。</span><span class="sxs-lookup"><span data-stu-id="a7a1a-105">For a list of the supported versions of Configuration Manager, see [Planning to Deploy MBAM with Configuration Manager](planning-to-deploy-mbam-with-configuration-manager-2.md).</span></span>

<span data-ttu-id="a7a1a-106">這項整合將 Microsoft BitLocker 管理和監控合規性與報告基礎結構移至 Microsoft System Center Configuration Manager 的原生環境。</span><span class="sxs-lookup"><span data-stu-id="a7a1a-106">This integration moves the Microsoft BitLocker Administration and Monitoring compliance and reporting infrastructure into the native environment of Microsoft System Center Configuration Manager.</span></span> <span data-ttu-id="a7a1a-107">透過 Configuration Manager 拓撲結構，IT 系統管理員可以從 Configuration Manager 管理主控台查看其企業的報告和合規性狀態。</span><span class="sxs-lookup"><span data-stu-id="a7a1a-107">With the Configuration Manager topology, IT administrators can view reports and the compliance status of their enterprise from the Configuration Manager Management Console.</span></span>

<span data-ttu-id="a7a1a-108">**重要** 當您安裝 MBAM 與 Configuration Manager 2007 的整合拓撲時，系統不支援 Windows To Go。</span><span class="sxs-lookup"><span data-stu-id="a7a1a-108">**Important** Windows To Go is not supported when you install the integrated topology of MBAM with Configuration Manager 2007.</span></span>

 

## <a href="" id="getting-started---using-mbam-with-configuration-manager"></a><span data-ttu-id="a7a1a-109">快速入門–配合 Configuration Manager 使用 MBAM</span><span class="sxs-lookup"><span data-stu-id="a7a1a-109">Getting Started – Using MBAM with Configuration Manager</span></span>


<span data-ttu-id="a7a1a-110">本節說明 MBAM 如何與 Configuration Manager 搭配運作，並說明使用 Configuration Manager 整合拓朴部署 MBAM 的建議架構。</span><span class="sxs-lookup"><span data-stu-id="a7a1a-110">This section describes how MBAM works with Configuration Manager and explains the recommended architecture for deploying MBAM with the Configuration Manager Integration topology.</span></span>

[<span data-ttu-id="a7a1a-111">開始使用 - 將 MBAM 與設定管理員搭配使用</span><span class="sxs-lookup"><span data-stu-id="a7a1a-111">Getting Started - Using MBAM with Configuration Manager</span></span>](getting-started---using-mbam-with-configuration-manager.md)

## <span data-ttu-id="a7a1a-112">規劃使用設定管理員進行 MBAM 部署</span><span class="sxs-lookup"><span data-stu-id="a7a1a-112">Planning to Deploy MBAM with Configuration Manager</span></span>


<span data-ttu-id="a7a1a-113">本節說明您必須先考慮的安裝先決條件、支援的設定，以及在使用 Configuration Manager 拓撲安裝 MBAM 之前需要考慮的硬體和軟體需求。</span><span class="sxs-lookup"><span data-stu-id="a7a1a-113">This section describes the installation prerequisites, supported configurations, and hardware and software requirements that you need to consider before you install MBAM with the Configuration Manager topology.</span></span>

[<span data-ttu-id="a7a1a-114">規劃使用設定管理員進行 MBAM 部署</span><span class="sxs-lookup"><span data-stu-id="a7a1a-114">Planning to Deploy MBAM with Configuration Manager</span></span>](planning-to-deploy-mbam-with-configuration-manager-2.md)

## <span data-ttu-id="a7a1a-115">使用設定管理員來部署 MBAM</span><span class="sxs-lookup"><span data-stu-id="a7a1a-115">Deploying MBAM with Configuration Manager</span></span>


<span data-ttu-id="a7a1a-116">本節說明如何使用 Configuration Manager 來部署 MBAM，並提供在管理和監控伺服器與 Configuration Manager 伺服器上安裝及設定 MBAM 的指示。</span><span class="sxs-lookup"><span data-stu-id="a7a1a-116">This section describes how to deploy MBAM with Configuration Manager, and includes instructions for installing and configuring the MBAM on the Administration and Monitoring Server and Configuration Manager Server.</span></span>

[<span data-ttu-id="a7a1a-117">使用設定管理員來部署 MBAM</span><span class="sxs-lookup"><span data-stu-id="a7a1a-117">Deploying MBAM with Configuration Manager</span></span>](deploying-mbam-with-configuration-manager-mbam2.md)

## <span data-ttu-id="a7a1a-118">瞭解 Configuration Manager 中的 MBAM 報告</span><span class="sxs-lookup"><span data-stu-id="a7a1a-118">Understanding MBAM Reports in Configuration Manager</span></span>


<span data-ttu-id="a7a1a-119">本節說明您可以從 Configuration Manager 執行的 MBAM 報告，以顯示貴企業中的企業及個人電腦合規性。</span><span class="sxs-lookup"><span data-stu-id="a7a1a-119">This section describes the MBAM reports that you can run from Configuration Manager to show the compliance of your enterprise and compliance of individual computers in your enterprise.</span></span>

[<span data-ttu-id="a7a1a-120">瞭解 Configuration Manager 中的 MBAM 報告</span><span class="sxs-lookup"><span data-stu-id="a7a1a-120">Understanding MBAM Reports in Configuration Manager</span></span>](understanding-mbam-reports-in-configuration-manager.md)

## <span data-ttu-id="a7a1a-121">相關主題</span><span class="sxs-lookup"><span data-stu-id="a7a1a-121">Related topics</span></span>


[<span data-ttu-id="a7a1a-122">適用於 MBAM 2.0 的操作</span><span class="sxs-lookup"><span data-stu-id="a7a1a-122">Operations for MBAM 2.0</span></span>](operations-for-mbam-20-mbam-2.md)

 

 





