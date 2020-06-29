---
title: 應用程式虛擬化系統的規劃與部署指南
description: 應用程式虛擬化系統的規劃與部署指南
author: dansimp
ms.assetid: 6c012e33-9ac6-4cd8-84ff-54f40973833f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 10bcac26fddae2f0e5826dbd7335adda06d3987e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800923"
---
# <span data-ttu-id="37e2b-103">應用程式虛擬化系統的規劃與部署指南</span><span class="sxs-lookup"><span data-stu-id="37e2b-103">Planning and Deployment Guide for the Application Virtualization System</span></span>


<span data-ttu-id="37e2b-104">Microsoft Application Virtualization 管理提供將應用程式提供給最終使用者電腦的功能，而不需要直接在那些電腦上安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="37e2b-104">Microsoft Application Virtualization Management provides the capability to make applications available to end user computers without having to install the applications directly on those computers.</span></span> <span data-ttu-id="37e2b-105">您可以透過稱為*應用程式順序的程式*來進行這項工作，這可讓每個應用程式在自己的用戶端電腦上獨立的虛擬環境中執行。</span><span class="sxs-lookup"><span data-stu-id="37e2b-105">This is made possible through a process known as *sequencing the application*, which enables each application to run in its own self-contained virtual environment on the client computer.</span></span> <span data-ttu-id="37e2b-106">順序化的應用程式彼此隔離，以消除應用程式衝突，但仍可與用戶端電腦互動。</span><span class="sxs-lookup"><span data-stu-id="37e2b-106">The sequenced applications are isolated from one another, eliminating application conflicts, yet can still interact with the client computer.</span></span>

<span data-ttu-id="37e2b-107">應用程式虛擬化用戶端是應用程式虛擬化系統元件，可讓使用者在應用程式發佈到電腦之後，與應用程式互動。</span><span class="sxs-lookup"><span data-stu-id="37e2b-107">The Application Virtualization Client is the Application Virtualization system component that enables the end user to interact with the applications after they have been published to the computer.</span></span> <span data-ttu-id="37e2b-108">用戶端管理虛擬化應用程式在每個電腦上執行的虛擬環境。</span><span class="sxs-lookup"><span data-stu-id="37e2b-108">The client manages the virtual environment in which the virtualized applications run on each computer.</span></span> <span data-ttu-id="37e2b-109">在電腦上安裝用戶端之後，您必須透過稱為*發佈*的程式，將應用程式提供給電腦，讓使用者能夠執行虛擬應用程式。</span><span class="sxs-lookup"><span data-stu-id="37e2b-109">After the client has been installed on a computer, the applications must be made available to the computer through a process known as *publishing*, which enables the end user to run the virtual applications.</span></span> <span data-ttu-id="37e2b-110">發佈程式會將虛擬應用程式圖示與電腦上的快捷方式放在電腦上（通常位於 Windows 桌面或 [**開始**] 功能表上），而且也會將套件定義及檔案類型關聯資訊放在電腦上。</span><span class="sxs-lookup"><span data-stu-id="37e2b-110">The publishing process places the virtual application icons and shortcuts on the computer—typically on the Windows desktop or on the **Start** menu—and also places the package definition and file type association information on the computer.</span></span> <span data-ttu-id="37e2b-111">發佈也會將應用程式套件內容提供給最終使用者的電腦。</span><span class="sxs-lookup"><span data-stu-id="37e2b-111">Publishing also makes the application package content available to the end user’s computer.</span></span>

<span data-ttu-id="37e2b-112">虛擬應用程式套件內容可以放置在一或多個應用程式虛擬化伺服器上，讓它可以根據需要流入用戶端，並在本機上緩存。</span><span class="sxs-lookup"><span data-stu-id="37e2b-112">The virtual application package content can be placed on one or more Application Virtualization servers so that it can be streamed down to the clients on demand and cached locally.</span></span> <span data-ttu-id="37e2b-113">檔案伺服器和 Web 服務器也可以用來做為流式伺服器，或者內容可以直接放在最終使用者的電腦上，例如，如果您使用的是電子軟體發佈系統（例如 Microsoft 端點設定管理員）。</span><span class="sxs-lookup"><span data-stu-id="37e2b-113">File servers and Web servers can also be used as streaming servers, or the content can be placed directly on the end user’s computer—for example, if you are using an electronic software distribution system, such as Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="37e2b-114">在多重伺服器的實現中，維護封裝內容並在所有流式處理伺服器上保持在最新狀態，都需要綜合的套件管理解決方案。</span><span class="sxs-lookup"><span data-stu-id="37e2b-114">In a multi-server implementation, maintaining the package content and keeping it up to date on all the streaming servers requires a comprehensive package management solution.</span></span> <span data-ttu-id="37e2b-115">視貴組織的規模而定，您可能需要有許多虛擬應用程式可供整個世界各地的使用者存取。</span><span class="sxs-lookup"><span data-stu-id="37e2b-115">Depending on the size of your organization, you might need to have many virtual applications accessible to end users located all over the world.</span></span> <span data-ttu-id="37e2b-116">管理套件，確保所有使用者都能存取適當的應用程式，以及他們需要存取這些專案的時間，因此是必不可少的需求。</span><span class="sxs-lookup"><span data-stu-id="37e2b-116">Managing the packages to ensure that the right applications are available to all users where and when they need access to them is therefore an essential requirement.</span></span>

<span data-ttu-id="37e2b-117">應用程式虛擬化規劃與部署指南提供的資訊可協助您更清楚地瞭解及部署 Microsoft Application Virtualization 應用程式及其元件。</span><span class="sxs-lookup"><span data-stu-id="37e2b-117">The Application Virtualization Planning and Deployment Guide provides information to help you better understand and deploy the Microsoft Application Virtualization application and its components.</span></span> <span data-ttu-id="37e2b-118">它也提供實現主要部署案例的逐步程式。</span><span class="sxs-lookup"><span data-stu-id="37e2b-118">It also provides step-by-step procedures for implementing the key deployment scenarios.</span></span>

## <span data-ttu-id="37e2b-119">本節內容</span><span class="sxs-lookup"><span data-stu-id="37e2b-119">In This Section</span></span>


<a href="" id="planning-for-application-virtualization-system-deployment"></a>[<span data-ttu-id="37e2b-120">規劃 Application Virtualization 系統部署</span><span class="sxs-lookup"><span data-stu-id="37e2b-120">Planning for Application Virtualization System Deployment</span></span>](planning-for-application-virtualization-system-deployment.md)  
<span data-ttu-id="37e2b-121">提供規劃應用程式虛擬化系統的實施與部署所需的指導方針。</span><span class="sxs-lookup"><span data-stu-id="37e2b-121">Provides the guidance necessary to plan the implementation and deployment of your Application Virtualization system.</span></span>

<a href="" id="application-virtualization-deployment-and-upgrade-considerations"></a>[<span data-ttu-id="37e2b-122">Application Virtualization 部署與升級考量</span><span class="sxs-lookup"><span data-stu-id="37e2b-122">Application Virtualization Deployment and Upgrade Considerations</span></span>](application-virtualization-deployment-and-upgrade-considerations.md)  
<span data-ttu-id="37e2b-123">提供安裝各種應用程式虛擬化元件以及升級資訊的硬體和軟體需求的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="37e2b-123">Provides information about hardware and software requirements for installing the various Application Virtualization components, as well as upgrade information.</span></span>

<a href="" id="electronic-software-distribution-based-scenario"></a>[<span data-ttu-id="37e2b-124">以電子軟體發佈為基礎的案例</span><span class="sxs-lookup"><span data-stu-id="37e2b-124">Electronic Software Distribution-Based Scenario</span></span>](electronic-software-distribution-based-scenario.md)  
<span data-ttu-id="37e2b-125">提供有關使用電子軟體發佈（ESD）系統部署應用程式虛擬化的資訊。</span><span class="sxs-lookup"><span data-stu-id="37e2b-125">Provides information about deploying Application Virtualization using an electronic software distribution (ESD) system.</span></span>

<a href="" id="application-virtualization-server-based-scenario"></a>[<span data-ttu-id="37e2b-126">以 Application Virtualization 伺服器為基礎的案例</span><span class="sxs-lookup"><span data-stu-id="37e2b-126">Application Virtualization Server-Based Scenario</span></span>](application-virtualization-server-based-scenario.md)  
<span data-ttu-id="37e2b-127">提供有關使用應用程式虛擬化管理伺服器部署應用程式虛擬化的資訊。</span><span class="sxs-lookup"><span data-stu-id="37e2b-127">Provides information about deploying Application Virtualization using the Application Virtualization Management Server.</span></span>

<a href="" id="stand-alone-delivery-scenario-for-application-virtualization-clients"></a>[<span data-ttu-id="37e2b-128">Application Virtualization Client 的獨立傳遞案例</span><span class="sxs-lookup"><span data-stu-id="37e2b-128">Stand-Alone Delivery Scenario for Application Virtualization Clients</span></span>](stand-alone-delivery-scenario-for-application-virtualization-clients.md)  
<span data-ttu-id="37e2b-129">說明如何在獨立模式中部署應用程式虛擬化，而不使用 ESD 或伺服器資源。</span><span class="sxs-lookup"><span data-stu-id="37e2b-129">Describes how to deploy Application Virtualization in a stand-alone mode, without the use of ESD or server-based resources.</span></span>

<a href="" id="application-virtualization-reference"></a>[<span data-ttu-id="37e2b-130">Application Virtualization 參考資料</span><span class="sxs-lookup"><span data-stu-id="37e2b-130">Application Virtualization Reference</span></span>](application-virtualization-reference.md)  
<span data-ttu-id="37e2b-131">包含有關安裝與管理系統元件的詳細技術參考資料。</span><span class="sxs-lookup"><span data-stu-id="37e2b-131">Contains detailed technical reference material related to installing and managing system components.</span></span>

 

 





