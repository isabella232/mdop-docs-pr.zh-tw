---
title: Application Virtualization 部署與升級考量
description: Application Virtualization 部署與升級考量
author: dansimp
ms.assetid: c3c38930-0da3-43e6-b240-945edfd00a01
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 09e6943c74c7f17b6a61bc7be4bcde925a54be56
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809255"
---
# <span data-ttu-id="ead99-103">Application Virtualization 部署與升級考量</span><span class="sxs-lookup"><span data-stu-id="ead99-103">Application Virtualization Deployment and Upgrade Considerations</span></span>


<span data-ttu-id="ead99-104">開始部署 Microsoft Application Virtualization (App-v) 之前，您可能必須審查您的環境需求，包括安裝各種應用程式虛擬化元件所需的硬體和軟體需求。</span><span class="sxs-lookup"><span data-stu-id="ead99-104">Before you begin the deployment of Microsoft Application Virtualization (App-V), you might have to review your environment requirements that includes the hardware and software requirements for installing the various Application Virtualization components.</span></span> <span data-ttu-id="ead99-105">此外，如果您是從舊版升級，本節中的主題會提供有關如何升級您目前的排序器、伺服器和用戶端版本的資訊。</span><span class="sxs-lookup"><span data-stu-id="ead99-105">Also, if you are upgrading from an earlier version, the topics in this section provide information about how to upgrade your current Sequencer, Server, and Client versions.</span></span>

## <span data-ttu-id="ead99-106">本節內容</span><span class="sxs-lookup"><span data-stu-id="ead99-106">In This Section</span></span>


<a href="" id="application-virtualization-deployment-requirements"></a>[<span data-ttu-id="ead99-107">Application Virtualization 部署需求</span><span class="sxs-lookup"><span data-stu-id="ead99-107">Application Virtualization Deployment Requirements</span></span>](application-virtualization-deployment-requirements.md)  
<span data-ttu-id="ead99-108">提供應用程式虛擬化部署之系統需求和升級考慮事項的一般資訊。</span><span class="sxs-lookup"><span data-stu-id="ead99-108">Provides general information about system requirements and upgrade considerations for your Application Virtualization deployment.</span></span>

<a href="" id="application-virtualization-deployment-and-upgrade-checklists"></a>[<span data-ttu-id="ead99-109">Application Virtualization 部署與升級檢查清單</span><span class="sxs-lookup"><span data-stu-id="ead99-109">Application Virtualization Deployment and Upgrade Checklists</span></span>](application-virtualization-deployment-and-upgrade-checklists.md)  
<span data-ttu-id="ead99-110">提供詳細的安裝與升級工作清單，其中包含特定程式的連結。</span><span class="sxs-lookup"><span data-stu-id="ead99-110">Provides detailed lists of installation and upgrade tasks with links to the specific procedures.</span></span>

<a href="" id="how-to-install-the-servers-and-system-components"></a>[<span data-ttu-id="ead99-111">如何安裝伺服器和系統元件</span><span class="sxs-lookup"><span data-stu-id="ead99-111">How to Install the Servers and System Components</span></span>](how-to-install-the-servers-and-system-components.md)  
<span data-ttu-id="ead99-112">說明如何安裝應用程式虛擬化 (App-v) 平臺元件（針對伺服器的部署所需）。</span><span class="sxs-lookup"><span data-stu-id="ead99-112">Describes how to install the Application Virtualization (App-V) platform components required for your server-based deployment.</span></span>

<a href="" id="how-to-manually-install-the-application-virtualization-client"></a>[<span data-ttu-id="ead99-113">如何手動安裝 Application Virtualization Client</span><span class="sxs-lookup"><span data-stu-id="ead99-113">How to Manually Install the Application Virtualization Client</span></span>](how-to-manually-install-the-application-virtualization-client.md)  
<span data-ttu-id="ead99-114">說明如何安裝應用程式虛擬化用戶端軟體。</span><span class="sxs-lookup"><span data-stu-id="ead99-114">Describes how to install the Application Virtualization Client software.</span></span>

<a href="" id="how-to-install-the-application-virtualization-sequencer"></a>[<span data-ttu-id="ead99-115">如何安裝 Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="ead99-115">How to Install the Application Virtualization Sequencer</span></span>](how-to-install-the-application-virtualization-sequencer.md)  
<span data-ttu-id="ead99-116">說明如何安裝應用程式虛擬化排序器。</span><span class="sxs-lookup"><span data-stu-id="ead99-116">Describes how to install the Application Virtualization Sequencer.</span></span>

<a href="" id="how-to-upgrade-the-application-virtualization-client"></a>[<span data-ttu-id="ead99-117">如何升級 Application Virtualization Client</span><span class="sxs-lookup"><span data-stu-id="ead99-117">How to Upgrade the Application Virtualization Client</span></span>](how-to-upgrade-the-application-virtualization-client.md)  
<span data-ttu-id="ead99-118">說明如何為遠端桌面服務升級應用程式虛擬化桌面用戶端或應用程式虛擬化用戶端， (先前的終端服務) 。</span><span class="sxs-lookup"><span data-stu-id="ead99-118">Describes how to upgrade the Application Virtualization Desktop Client or the Application Virtualization Client for Remote Desktop Services (formerly Terminal Services).</span></span>

<a href="" id="how-to-upgrade-the-servers-and-system-components"></a>[<span data-ttu-id="ead99-119">如何升級伺服器和系統元件</span><span class="sxs-lookup"><span data-stu-id="ead99-119">How to Upgrade the Servers and System Components</span></span>](how-to-upgrade-the-servers-and-system-components.md)  
<span data-ttu-id="ead99-120">說明如何升級安裝在所有應用程式虛擬化管理系統電腦上的軟體元件。</span><span class="sxs-lookup"><span data-stu-id="ead99-120">Describes how to upgrade the software components installed on all Application Virtualization Management System computers.</span></span>

<a href="" id="how-to-upgrade-the-application-virtualization-sequencer"></a>[<span data-ttu-id="ead99-121">如何升級 Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="ead99-121">How to Upgrade the Application Virtualization Sequencer</span></span>](how-to-upgrade-the-application-virtualization-sequencer.md)  
<span data-ttu-id="ead99-122">說明如何在執行 WindowsVista 或 WindowsXP 的電腦上升級 Sequencer。</span><span class="sxs-lookup"><span data-stu-id="ead99-122">Describes how to upgrade the Sequencer on computers that are running WindowsVista or WindowsXP.</span></span>

## <span data-ttu-id="ead99-123">相關主題</span><span class="sxs-lookup"><span data-stu-id="ead99-123">Related topics</span></span>


[<span data-ttu-id="ead99-124">Application Virtualization 參考資料</span><span class="sxs-lookup"><span data-stu-id="ead99-124">Application Virtualization Reference</span></span>](application-virtualization-reference.md)

[<span data-ttu-id="ead99-125">以 Application Virtualization 伺服器為基礎的案例</span><span class="sxs-lookup"><span data-stu-id="ead99-125">Application Virtualization Server-Based Scenario</span></span>](application-virtualization-server-based-scenario.md)

[<span data-ttu-id="ead99-126">以電子軟體發佈為基礎的案例</span><span class="sxs-lookup"><span data-stu-id="ead99-126">Electronic Software Distribution-Based Scenario</span></span>](electronic-software-distribution-based-scenario.md)

[<span data-ttu-id="ead99-127">Application Virtualization Client 的獨立傳遞案例</span><span class="sxs-lookup"><span data-stu-id="ead99-127">Stand-Alone Delivery Scenario for Application Virtualization Clients</span></span>](stand-alone-delivery-scenario-for-application-virtualization-clients.md)

 

 





