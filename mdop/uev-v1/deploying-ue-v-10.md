---
title: 部署 UE-V 1.0
description: 部署 UE-V 1.0
author: dansimp
ms.assetid: 519598bb-8c81-4af7-bee7-357696bff880
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1a1c515f9be950d8ca7b0a199344d34f7852073d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812182"
---
# <span data-ttu-id="0e706-103">部署 UE-V 1.0</span><span class="sxs-lookup"><span data-stu-id="0e706-103">Deploying UE-V 1.0</span></span>


<span data-ttu-id="0e706-104">Microsoft 使用者體驗虛擬化（UE-V）支援多種不同的部署設定。</span><span class="sxs-lookup"><span data-stu-id="0e706-104">There are a number of different deployment configurations that Microsoft User Experience Virtualization (UE-V) supports.</span></span> <span data-ttu-id="0e706-105">本節包含一般資訊和逐步程式，可協助您成功執行必須在部署的不同階段完成的工作。</span><span class="sxs-lookup"><span data-stu-id="0e706-105">This section includes general information and step-by-step procedures to help you successfully perform the tasks that you must complete at different stages of your deployment.</span></span>

## <span data-ttu-id="0e706-106">UE-V 的部署資訊</span><span class="sxs-lookup"><span data-stu-id="0e706-106">Deployment information for UE-V</span></span>


<span data-ttu-id="0e706-107">UE-V 部署需要網路共用上的設定儲存位置，以及在同步處理設定的每台電腦上安裝 UE-V agent。</span><span class="sxs-lookup"><span data-stu-id="0e706-107">A UE-V deployment requires a settings storage location on a network share and a UE-V agent installed on every computer that synchronizes settings.</span></span> <span data-ttu-id="0e706-108">UE-V 群組原則範本可用於管理 UE-V 設定。</span><span class="sxs-lookup"><span data-stu-id="0e706-108">The UE-V Group Policy templates can be used to manage UE-V settings.</span></span> <span data-ttu-id="0e706-109">下列主題說明如何部署這些功能。</span><span class="sxs-lookup"><span data-stu-id="0e706-109">The following topics describe how to deploy these features.</span></span>

[<span data-ttu-id="0e706-110">部署適用於 UE-V 1.0 的設定儲存位置</span><span class="sxs-lookup"><span data-stu-id="0e706-110">Deploying the Settings Storage Location for UE-V 1.0</span></span>](deploying-the-settings-storage-location-for-ue-v-10.md)

<span data-ttu-id="0e706-111">所有 UE-V 部署都需要設定儲存位置，其中包含同步處理設定值的設定套件位於其中。</span><span class="sxs-lookup"><span data-stu-id="0e706-111">All UE-V deployments require a settings storage location where the settings packages that contain the synchronized setting values are located.</span></span>

[<span data-ttu-id="0e706-112">部署 UE-V 代理程式</span><span class="sxs-lookup"><span data-stu-id="0e706-112">Deploying the UE-V Agent</span></span>](deploying-the-ue-v-agent.md)

<span data-ttu-id="0e706-113">若要使用 UE-V 同步處理設定，電腦必須已安裝並執行 UE-V Agent。</span><span class="sxs-lookup"><span data-stu-id="0e706-113">To synchronize settings by using UE-V, a computer must have the UE-V Agent installed and running.</span></span>

[<span data-ttu-id="0e706-114">安裝 UE-V 群組原則 ADMX 範本</span><span class="sxs-lookup"><span data-stu-id="0e706-114">Installing the UE-V Group Policy ADMX Templates</span></span>](installing-the-ue-v-group-policy-admx-templates.md)

<span data-ttu-id="0e706-115">在部署 UE-V Agent 及標準 UE-V 設定之前，您可以使用群組原則來預先配置 UE-V 設定。</span><span class="sxs-lookup"><span data-stu-id="0e706-115">You can use Group Policy to preconfigure UE-V settings before you deploy the UE-V Agent as well as standard UE-V configuration.</span></span>

## <span data-ttu-id="0e706-116">自訂範本部署的部署資訊</span><span class="sxs-lookup"><span data-stu-id="0e706-116">Deployment information for custom template deployment</span></span>


<span data-ttu-id="0e706-117">如果您打算針對包含在 UE-V 中的 Microsoft 應用程式以外的應用程式建立自訂設定位置範本（例如商務線應用程式），您可以部署設定範本目錄，而且您必須安裝 UE-V 發生器來建立這些範本。</span><span class="sxs-lookup"><span data-stu-id="0e706-117">If you plan to create custom settings location templates for applications other than the Microsoft applications that are included in UE-V, such as line-of-business applications, then you can deploy a settings template catalog and you must install the UE-V Generator to create those templates.</span></span> <span data-ttu-id="0e706-118">如需詳細資訊，請參閱[規劃 ue-v 1.0 的自訂範本部署](planning-for-custom-template-deployment-for-ue-v-10.md)。</span><span class="sxs-lookup"><span data-stu-id="0e706-118">For more information, see [Planning for Custom Template Deployment for UE-V 1.0](planning-for-custom-template-deployment-for-ue-v-10.md).</span></span>

[<span data-ttu-id="0e706-119">安裝 UE-V 產生器</span><span class="sxs-lookup"><span data-stu-id="0e706-119">Installing the UE-V Generator</span></span>](installing-the-ue-v-generator.md)

<span data-ttu-id="0e706-120">使用 UE-V 發生器來建立、編輯及驗證自訂設定位置範本，協助同步處理應用程式（而非預設應用程式）的設定。</span><span class="sxs-lookup"><span data-stu-id="0e706-120">Use the UE-V Generator to create, edit, and validate custom settings location templates that help synchronize settings of applications other than the default applications.</span></span>

[<span data-ttu-id="0e706-121">部署適用於 UE-V 1.0 的設定範本類別目錄</span><span class="sxs-lookup"><span data-stu-id="0e706-121">Deploying the Settings Template Catalog for UE-V 1.0</span></span>](deploying-the-settings-template-catalog-for-ue-v-10.md)

<span data-ttu-id="0e706-122">如果您需要將自訂設定位置範本部署成支援 UE-V Agent 中預設應用程式以外的應用程式，您必須設定設定範本目錄來儲存。</span><span class="sxs-lookup"><span data-stu-id="0e706-122">If you need to deploy custom settings location templates to support applications other than the default applications in the UE-V Agent, you must configure a settings template catalog to store them.</span></span>

[<span data-ttu-id="0e706-123">部署適用於 UE-V 1.0 的 UE-V 設定位置範本</span><span class="sxs-lookup"><span data-stu-id="0e706-123">Deploying UE-V Settings Location Templates for UE-V 1.0</span></span>](deploying-ue-v-settings-location-templates-for-ue-v-10.md)

<span data-ttu-id="0e706-124">如果您需要同步處理 UE-V Agent 中的預設應用程式以外的應用程式，則可將使用 UE-V 發生器建立的自訂設定位置範本發佈到 UE-V 設定範本目錄。</span><span class="sxs-lookup"><span data-stu-id="0e706-124">If you need to synchronize applications other than the default applications in the UE-V Agent, the custom setting location templates that are created with UE-V Generator can be distributed to the UE-V settings template catalog.</span></span>

<span data-ttu-id="0e706-125">**記事** 部署自訂範本需要設定範本目錄。</span><span class="sxs-lookup"><span data-stu-id="0e706-125">**Note** Deploying custom templates requires a settings template catalog.</span></span> <span data-ttu-id="0e706-126">預設的 Microsoft 應用程式範本是與 UE-V Agent 一起部署。</span><span class="sxs-lookup"><span data-stu-id="0e706-126">The default Microsoft application templates are deployed with the UE-V Agent.</span></span>

 

## <span data-ttu-id="0e706-127">此產品的主題</span><span class="sxs-lookup"><span data-stu-id="0e706-127">Topics for this product</span></span>


[<span data-ttu-id="0e706-128">Microsoft User Experience Virtualization (UE-V) 1.0</span><span class="sxs-lookup"><span data-stu-id="0e706-128">Microsoft User Experience Virtualization (UE-V) 1.0</span></span>](index.md)

[<span data-ttu-id="0e706-129">開始使用 User Experience Virtualization 1.0</span><span class="sxs-lookup"><span data-stu-id="0e706-129">Getting Started With User Experience Virtualization 1.0</span></span>](getting-started-with-user-experience-virtualization-10.md)

[<span data-ttu-id="0e706-130">為 UE-V 1.0 進行規劃</span><span class="sxs-lookup"><span data-stu-id="0e706-130">Planning for UE-V 1.0</span></span>](planning-for-ue-v-10.md)

[<span data-ttu-id="0e706-131">UE-V 1.0 作業</span><span class="sxs-lookup"><span data-stu-id="0e706-131">Operations for UE-V 1.0</span></span>](operations-for-ue-v-10.md)

[<span data-ttu-id="0e706-132">疑難排解 UE-V 1.0</span><span class="sxs-lookup"><span data-stu-id="0e706-132">Troubleshooting UE-V 1.0</span></span>](troubleshooting-ue-v-10.md)

 

 





