---
title: Application Virtualization 部署與升級考量
description: Application Virtualization 部署與升級考量
author: dansimp
ms.assetid: adc562ee-7276-4b14-b10a-da17f05e1682
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dd9e6c1a624b9da18bba75c5f3816a8e9c5391a8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809237"
---
# <span data-ttu-id="170d7-103">Application Virtualization 部署與升級考量</span><span class="sxs-lookup"><span data-stu-id="170d7-103">Application Virtualization Deployment and Upgrade Considerations</span></span>


<span data-ttu-id="170d7-104">開始部署 Microsoft Application Virtualization 前，您可能需要檢查您的環境需求，包括安裝各種應用程式虛擬化元件所需的硬體和軟體需求。</span><span class="sxs-lookup"><span data-stu-id="170d7-104">Before you begin the deployment of Microsoft Application Virtualization, you might need to review your environment requirements, including the hardware and software requirements for installing the various Application Virtualization components.</span></span> <span data-ttu-id="170d7-105">此外，如果您是從舊版升級，本節中的主題會提供升級您目前的排序器、伺服器和用戶端版本的資訊。</span><span class="sxs-lookup"><span data-stu-id="170d7-105">Also, if you are upgrading from a previous version, the topics in this section provide information about upgrading your current Sequencer, server, and client versions.</span></span>

## <span data-ttu-id="170d7-106">本節內容</span><span class="sxs-lookup"><span data-stu-id="170d7-106">In This Section</span></span>


<a href="" id="application-virtualization-deployment-requirements"></a>[<span data-ttu-id="170d7-107">Application Virtualization 部署需求</span><span class="sxs-lookup"><span data-stu-id="170d7-107">Application Virtualization Deployment Requirements</span></span>](application-virtualization-deployment-requirements.md)  
<span data-ttu-id="170d7-108">提供應用程式虛擬化部署之系統需求和升級考慮事項的一般資訊。</span><span class="sxs-lookup"><span data-stu-id="170d7-108">Provides general information about system requirements and upgrade considerations for your Application Virtualization deployment.</span></span>

<a href="" id="how-to-upgrade-the-application-virtualization-client"></a>[<span data-ttu-id="170d7-109">如何升級 Application Virtualization Client</span><span class="sxs-lookup"><span data-stu-id="170d7-109">How to Upgrade the Application Virtualization Client</span></span>](how-to-upgrade-the-application-virtualization-client.md)  
<span data-ttu-id="170d7-110">提供升級應用程式虛擬化桌面用戶端或適用于遠端桌面服務（舊稱終端服務）之應用程式虛擬化用戶端的逐步程式。</span><span class="sxs-lookup"><span data-stu-id="170d7-110">Provides step-by-step procedures for upgrading the Application Virtualization Desktop Client or the Application Virtualization Client for Remote Desktop Services (formerly Terminal Services).</span></span>

<a href="" id="how-to-upgrade-the-servers-and-system-components"></a>[<span data-ttu-id="170d7-111">如何升級伺服器和系統元件</span><span class="sxs-lookup"><span data-stu-id="170d7-111">How to Upgrade the Servers and System Components</span></span>](how-to-upgrade-the-servers-and-system-components.md)  
<span data-ttu-id="170d7-112">提供分步程式，您可以用來升級安裝在所有應用程式虛擬化系統電腦上的軟體元件。</span><span class="sxs-lookup"><span data-stu-id="170d7-112">Provides a step-by-step procedure you can use to upgrade the software components installed on all Application Virtualization System computers.</span></span>

<a href="" id="how-to-upgrade-the-application-virtualization-sequencer"></a>[<span data-ttu-id="170d7-113">如何升級 Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="170d7-113">How to Upgrade the Application Virtualization Sequencer</span></span>](how-to-upgrade-the-application-virtualization-sequencer.md)  
<span data-ttu-id="170d7-114">提供在執行 Windows Vista 或 WindowsXP 的電腦上升級 Sequencer 的逐步程式。</span><span class="sxs-lookup"><span data-stu-id="170d7-114">Provides step-by-step procedures for upgrading the Sequencer on computers running Windows Vista or WindowsXP.</span></span>

<a href="" id="how-to-install-the-application-virtualization-sequencer"></a>[<span data-ttu-id="170d7-115">如何安裝 Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="170d7-115">How to Install the Application Virtualization Sequencer</span></span>](how-to-install-the-application-virtualization-sequencer.md)  
<span data-ttu-id="170d7-116">提供安裝排序器的逐步程式。</span><span class="sxs-lookup"><span data-stu-id="170d7-116">Provides a step-by-step procedure for installing the Sequencer.</span></span>

## <span data-ttu-id="170d7-117">相關主題</span><span class="sxs-lookup"><span data-stu-id="170d7-117">Related topics</span></span>


[<span data-ttu-id="170d7-118">Application Virtualization 參考資料</span><span class="sxs-lookup"><span data-stu-id="170d7-118">Application Virtualization Reference</span></span>](application-virtualization-reference.md)

[<span data-ttu-id="170d7-119">以 Application Virtualization 伺服器為基礎的案例</span><span class="sxs-lookup"><span data-stu-id="170d7-119">Application Virtualization Server-Based Scenario</span></span>](application-virtualization-server-based-scenario.md)

[<span data-ttu-id="170d7-120">以電子軟體發佈為基礎的案例</span><span class="sxs-lookup"><span data-stu-id="170d7-120">Electronic Software Distribution-Based Scenario</span></span>](electronic-software-distribution-based-scenario.md)

[<span data-ttu-id="170d7-121">Application Virtualization Client 的獨立傳遞案例</span><span class="sxs-lookup"><span data-stu-id="170d7-121">Stand-Alone Delivery Scenario for Application Virtualization Clients</span></span>](stand-alone-delivery-scenario-for-application-virtualization-clients.md)

 

 





