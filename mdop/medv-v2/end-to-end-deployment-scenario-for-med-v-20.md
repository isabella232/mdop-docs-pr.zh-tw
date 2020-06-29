---
title: MED-V 2.0 端對端部署案例
description: MED-V 2.0 端對端部署案例
author: dansimp
ms.assetid: 91bb5a9a-5fb1-4743-8494-9d4dee2ec222
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6d56e70ad359ebf2d76cf3f30f54f73cd9ca1c66
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811595"
---
# <span data-ttu-id="976b5-103">MED-V 2.0 端對端部署案例</span><span class="sxs-lookup"><span data-stu-id="976b5-103">End-to-End Deployment Scenario for MED-V 2.0</span></span>


<span data-ttu-id="976b5-104">此範例案例 Microsoft 企業版桌面虛擬化（MED-V）2.0 可協助您在企業中部署 MED-V 元件，方法是使用端對端進行。</span><span class="sxs-lookup"><span data-stu-id="976b5-104">This sample scenario for Microsoft Enterprise Desktop Virtualization (MED-V) 2.0 helps you deploy the MED-V components in your enterprise by using multiple scenarios end-to-end.</span></span> <span data-ttu-id="976b5-105">您可以將這個範例案例想像成案例研究，協助將個別案例和程式放在內容中。</span><span class="sxs-lookup"><span data-stu-id="976b5-105">You can think of this sample scenario as a case study that helps put the individual scenarios and procedures in context.</span></span>

<span data-ttu-id="976b5-106">本節提供在企業中部署 MED-V 元件作為端對端方案的基本資訊和指示。</span><span class="sxs-lookup"><span data-stu-id="976b5-106">This section provides basic information and directions for deploying MED-V components as an end-to-end solution in your enterprise.</span></span>

## <span data-ttu-id="976b5-107">MED-V 部署逐步方案</span><span class="sxs-lookup"><span data-stu-id="976b5-107">MED-V Deployment Step-by-step Scenario</span></span>


<span data-ttu-id="976b5-108">此逐步方案中的主題包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="976b5-108">The topics in this step-by-step scenario include the following:</span></span>

-   <span data-ttu-id="976b5-109">[Med-v 2.0 支援](med-v-20-supported-configurations.md)的設定會討論在您的環境中安裝並執行 Microsoft 企業桌面虛擬化（med-v）2.0 所需的需求。</span><span class="sxs-lookup"><span data-stu-id="976b5-109">[MED-V 2.0 Supported Configurations](med-v-20-supported-configurations.md) discusses the requirements that you must have to install and run Microsoft Enterprise Desktop Virtualization (MED-V) 2.0in your environment.</span></span> <span data-ttu-id="976b5-110">本主題指定作業系統需求、配置需求，以及 MED-V 工作區需求。</span><span class="sxs-lookup"><span data-stu-id="976b5-110">This topic specifies the operating system requirements, configuration requirements, and MED-V workspace requirements.</span></span> <span data-ttu-id="976b5-111">本主題也包含 MED-V 2.0 支援之語言的當地語系化資訊。</span><span class="sxs-lookup"><span data-stu-id="976b5-111">This topic also includes localization information about the languages that MED-V 2.0 supports.</span></span>

-   <span data-ttu-id="976b5-112">[Med-v 2.0 部署概述](med-v-20-deployment-overview.md)討論一般資訊與指示，協助您在整個企業中安裝並部署 med-v。</span><span class="sxs-lookup"><span data-stu-id="976b5-112">[MED-V 2.0 Deployment Overview](med-v-20-deployment-overview.md) discusses general information and instructions to help you install and deploy MED-V throughout your enterprise.</span></span> <span data-ttu-id="976b5-113">MED-V 元件是以用戶端為基礎，並使用您現有的企業基礎結構和程式來提供和管理。</span><span class="sxs-lookup"><span data-stu-id="976b5-113">The MED-V components are client-based and are delivered and managed by using your existing enterprise infrastructure and processes.</span></span> <span data-ttu-id="976b5-114">本主題概述了 MED-V 解決方案，其中包含有關 MED-V 安裝檔案和您部署之 MED-V 元件的資訊。</span><span class="sxs-lookup"><span data-stu-id="976b5-114">This topic provides an overview of the MED-V solution that includes information about the MED-V installation files and the MED-V components that you deploy.</span></span> <span data-ttu-id="976b5-115">本主題也提供 MED-V 安裝與部署程式的高層次概覽。</span><span class="sxs-lookup"><span data-stu-id="976b5-115">This topic also provides a high-level overview of the MED-V installation and deployment process.</span></span>

-   <span data-ttu-id="976b5-116">[為 Med-v 準備部署環境](prepare-the-deployment-environment-for-med-v.md)討論如何為 med-v 2.0 部署準備您的環境。</span><span class="sxs-lookup"><span data-stu-id="976b5-116">[Prepare the Deployment Environment for MED-V](prepare-the-deployment-environment-for-med-v.md) discusses how to prepare your environment for a MED-V 2.0 deployment.</span></span> <span data-ttu-id="976b5-117">本節說明 MED-V 環境所需的先決條件，例如 Microsoft Windows 7 和 Active Directory 基礎結構，您可以在其中使用群組原則來提供作業系統、應用程式及使用者設定的集中式管理和配置。</span><span class="sxs-lookup"><span data-stu-id="976b5-117">This section describes the prerequisites that are required for the MED-V environment, such as Microsoft Windows 7 and an Active Directory infrastructure in which you use Group Policy to provide centralized management and configuration of operating systems, applications, and users' settings.</span></span> <span data-ttu-id="976b5-118">本節也說明在整個企業中安裝並部署 MED-V 2.0 所需的先決條件，例如 Windows Virtual PC 和必要的 Windows 虛擬電腦更新。</span><span class="sxs-lookup"><span data-stu-id="976b5-118">This section also describes the prerequisites that you must have for installing and deploying MED-V 2.0 throughout your enterprise, such as Windows Virtual PC and the required Windows Virtual PC update.</span></span>

-   <span data-ttu-id="976b5-119">[部署 Med-v 元件](deploy-the-med-v-components.md)討論您可以在整個企業中安裝所有必要的安裝檔案和 med-v 元件的不同方式。</span><span class="sxs-lookup"><span data-stu-id="976b5-119">[Deploy the MED-V Components](deploy-the-med-v-components.md) discusses the different ways you can install all of the necessary installation files and MED-V components throughout your enterprise.</span></span> <span data-ttu-id="976b5-120">若要安裝和部署 MED-V，您通常必須遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="976b5-120">To install and deploy MED-V, you typically follow these steps:</span></span>

    1.  <span data-ttu-id="976b5-121">在您將用來建立 MED-V 工作區套件的系統管理員電腦上安裝**Med-v 工作區包裝**程式。</span><span class="sxs-lookup"><span data-stu-id="976b5-121">Install the **MED-V Workspace Packager** on the administrator computer that you will use to build the MED-V workspace packages.</span></span> <span data-ttu-id="976b5-122">如需詳細資訊，請參閱[如何安裝 Med-v 工作區包裝程式](how-to-install-the-med-v-workspace-packager.md)。</span><span class="sxs-lookup"><span data-stu-id="976b5-122">For more information, see [How to Install the MED-V Workspace Packager](how-to-install-the-med-v-workspace-packager.md).</span></span>

    2.  <span data-ttu-id="976b5-123">建立並測試您的 MED-V 工作區套件。</span><span class="sxs-lookup"><span data-stu-id="976b5-123">Create and test your MED-V workspace packages.</span></span> <span data-ttu-id="976b5-124">如需詳細資訊，請參閱[建立 Med-v 工作區套件](create-a-med-v-workspace-package.md)及[測試 Med-v 工作區封裝](testing-the-med-v-workspace-package.md)。</span><span class="sxs-lookup"><span data-stu-id="976b5-124">For more information, see [Create a MED-V Workspace Package](create-a-med-v-workspace-package.md) and [Testing the MED-V Workspace Package](testing-the-med-v-workspace-package.md).</span></span>

    3.  <span data-ttu-id="976b5-125">使用貴公司現有的部署應用程式方法，在整個企業中部署 MED-V。</span><span class="sxs-lookup"><span data-stu-id="976b5-125">Deploy MED-V throughout your enterprise by using your company’s existing method for deploying applications.</span></span> <span data-ttu-id="976b5-126">如需詳細資訊，請參閱[部署 Med-v 工作區套件](deploying-the-med-v-workspace-package.md)。</span><span class="sxs-lookup"><span data-stu-id="976b5-126">For more information, see [Deploying the MED-V Workspace Package](deploying-the-med-v-workspace-package.md).</span></span>

## <span data-ttu-id="976b5-127">相關主題</span><span class="sxs-lookup"><span data-stu-id="976b5-127">Related topics</span></span>


[<span data-ttu-id="976b5-128">MED-V 部署</span><span class="sxs-lookup"><span data-stu-id="976b5-128">Deployment of MED-V</span></span>](deployment-of-med-v.md)

[<span data-ttu-id="976b5-129">MED-V 2.0 端對端規劃案例</span><span class="sxs-lookup"><span data-stu-id="976b5-129">End-to-End Planning Scenario for MED-V 2.0</span></span>](end-to-end-planning-scenario-for-med-v-20.md)

[<span data-ttu-id="976b5-130">MED-V 2.0 端對端操作案例</span><span class="sxs-lookup"><span data-stu-id="976b5-130">End-to-End Operations Scenario for MED-V 2.0</span></span>](end-to-end-operations-scenario-for-med-v-20.md)

 

 





