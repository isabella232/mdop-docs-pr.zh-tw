---
title: 如何針對以伺服器為基礎的部署設定伺服器
description: 如何針對以伺服器為基礎的部署設定伺服器
author: dansimp
ms.assetid: 6371c37a-46eb-44e8-ad6b-4430c866c8b4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4c60ae89bc42fddad8aeb6a4f6df0f2c0b4ee4f2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801609"
---
# <span data-ttu-id="d57c2-103">如何針對以伺服器為基礎的部署設定伺服器</span><span class="sxs-lookup"><span data-stu-id="d57c2-103">How to Configure Servers for Server-Based Deployment</span></span>


<span data-ttu-id="d57c2-104">本節提供的程式可供您用來設定 Microsoft System Center 應用程式虛擬化（App-v）管理伺服器與 Microsoft System Center 應用程式虛擬化流式伺服器，以及 Internet Information Services （IIS）與檔案伺服器（適用于應用程式虛擬化伺服器的部署策略）。</span><span class="sxs-lookup"><span data-stu-id="d57c2-104">This section provides procedures you can use to configure the Microsoft System Center Application Virtualization (App-V) Management Servers and Microsoft System Center Application Virtualization Streaming Servers, and the Internet Information Services (IIS) and file servers, as appropriate for your Application Virtualization Server-based deployment strategy.</span></span>

## <span data-ttu-id="d57c2-105">本節內容</span><span class="sxs-lookup"><span data-stu-id="d57c2-105">In This Section</span></span>


<a href="" id="how-to-configure-the-application-virtualization-management-servers"></a>[<span data-ttu-id="d57c2-106">如何設定 Application Virtualization Management Server</span><span class="sxs-lookup"><span data-stu-id="d57c2-106">How to Configure the Application Virtualization Management Servers</span></span>](how-to-configure-the-application-virtualization-management-servers.md)  
<span data-ttu-id="d57c2-107">提供配置應用程式虛擬化管理伺服器的逐步程式。</span><span class="sxs-lookup"><span data-stu-id="d57c2-107">Provides a step-by-step procedure for configuring the Application Virtualization Management Servers.</span></span>

<a href="" id="how-to-configure-the-application-virtualization-streaming-servers"></a>[<span data-ttu-id="d57c2-108">如何設定 Application Virtualization Streaming Server</span><span class="sxs-lookup"><span data-stu-id="d57c2-108">How to Configure the Application Virtualization Streaming Servers</span></span>](how-to-configure-the-application-virtualization-streaming-servers.md)  
<span data-ttu-id="d57c2-109">提供配置應用程式虛擬化資料流程伺服器的逐步程式。</span><span class="sxs-lookup"><span data-stu-id="d57c2-109">Provides a step-by-step procedure for configuring the Application Virtualization Streaming Servers.</span></span>

<a href="" id="how-to-configure-the-server-for-iis"></a>[<span data-ttu-id="d57c2-110">如何設定伺服器使用 IIS</span><span class="sxs-lookup"><span data-stu-id="d57c2-110">How to Configure the Server for IIS</span></span>](how-to-configure-the-server-for-iis.md)  
<span data-ttu-id="d57c2-111">提供針對伺服器式部署設定 IIS 伺服器的逐步程式。</span><span class="sxs-lookup"><span data-stu-id="d57c2-111">Provides a step-by-step procedure for configuring the IIS server for your server-based deployment.</span></span>

<a href="" id="how-to-configure-the-server-to-be-trusted-for-delegation"></a>[<span data-ttu-id="d57c2-112">如何將伺服器設定成受信任可以委派</span><span class="sxs-lookup"><span data-stu-id="d57c2-112">How to Configure the Server to be Trusted for Delegation</span></span>](how-to-configure-the-server-to-be-trusted-for-delegation.md)  
<span data-ttu-id="d57c2-113">提供有關如何將伺服器設定為信任委派的詳細指示。</span><span class="sxs-lookup"><span data-stu-id="d57c2-113">Provides detailed instructions about how to configure the server to be trusted for delegation.</span></span>

<a href="" id="configuring-the-firewall-for-the-app-v-servers"></a>[<span data-ttu-id="d57c2-114">設定 App-V 伺服器所需的防火牆</span><span class="sxs-lookup"><span data-stu-id="d57c2-114">Configuring the Firewall for the App-V Servers</span></span>](configuring-the-firewall-for-the-app-v-servers.md)  
<span data-ttu-id="d57c2-115">說明 App-v 伺服器所需的防火牆設定。</span><span class="sxs-lookup"><span data-stu-id="d57c2-115">Describes the firewall settings required for the App-V servers.</span></span>

<a href="" id="how-to-install-and-configure-the-default-application"></a>[<span data-ttu-id="d57c2-116">如何安裝和設定 Default Application</span><span class="sxs-lookup"><span data-stu-id="d57c2-116">How to Install and Configure the Default Application</span></span>](how-to-install-and-configure-the-default-application.md)  
<span data-ttu-id="d57c2-117">說明如何安裝和設定用來測試 app-v 系統的預設應用程式。</span><span class="sxs-lookup"><span data-stu-id="d57c2-117">Describes how to install and configure the default application for testing the App-V system.</span></span>

## <span data-ttu-id="d57c2-118">相關主題</span><span class="sxs-lookup"><span data-stu-id="d57c2-118">Related topics</span></span>


[<span data-ttu-id="d57c2-119">以 Application Virtualization 伺服器為基礎的案例概觀</span><span class="sxs-lookup"><span data-stu-id="d57c2-119">Application Virtualization Server-Based Scenario Overview</span></span>](application-virtualization-server-based-scenario-overview.md)

[<span data-ttu-id="d57c2-120">以電子軟體發佈為基礎的案例</span><span class="sxs-lookup"><span data-stu-id="d57c2-120">Electronic Software Distribution-Based Scenario</span></span>](electronic-software-distribution-based-scenario.md)

[<span data-ttu-id="d57c2-121">如何安裝伺服器和系統元件</span><span class="sxs-lookup"><span data-stu-id="d57c2-121">How to Install the Servers and System Components</span></span>](how-to-install-the-servers-and-system-components.md)

 

 





