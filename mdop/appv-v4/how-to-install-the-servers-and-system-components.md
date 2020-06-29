---
title: 如何安裝伺服器和系統元件
description: 如何安裝伺服器和系統元件
author: dansimp
ms.assetid: c6f5fef0-522a-4ef1-8585-05b292d0289b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2ceb5b8376189aee7631229dca912140e454536b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801338"
---
# <span data-ttu-id="b74d2-103">如何安裝伺服器和系統元件</span><span class="sxs-lookup"><span data-stu-id="b74d2-103">How to Install the Servers and System Components</span></span>


<span data-ttu-id="b74d2-104">在您可以將應用程式提供給使用者之前，您必須安裝 Microsoft Application Virtualization 平台元件。</span><span class="sxs-lookup"><span data-stu-id="b74d2-104">Before you can deliver applications to users, you must install the Microsoft Application Virtualization Platform components.</span></span> <span data-ttu-id="b74d2-105">本節中的主題提供安裝應用程式虛擬化伺服器與其他應用程式虛擬化系統元件所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="b74d2-105">The topics in this section provide the information required to install the Application Virtualization Servers and the other Application Virtualization System components.</span></span>

<span data-ttu-id="b74d2-106">**記事** 本區段中的程式會帶您進行自訂安裝，您可以在其中挑選並選擇元件，以在不同的電腦上安裝，如在生產環境中的建議。</span><span class="sxs-lookup"><span data-stu-id="b74d2-106">**Note** The procedures in this section take you through a customized installation, where you pick and choose components to install on separate computers, as recommended in a production environment.</span></span> <span data-ttu-id="b74d2-107">不過，您的操作程式可能會決定不同的方法，而且在安裝程式期間，您可能想要將元件組成群組。</span><span class="sxs-lookup"><span data-stu-id="b74d2-107">However, your operating procedures might dictate a different approach, and during the installation process you might want to group components together.</span></span> <span data-ttu-id="b74d2-108">不論元件的安裝位置為何，您都可以以任何順序安裝它們。</span><span class="sxs-lookup"><span data-stu-id="b74d2-108">Regardless of where you install the components, you can install them in any order.</span></span>

 

## <span data-ttu-id="b74d2-109">本節內容</span><span class="sxs-lookup"><span data-stu-id="b74d2-109">In This Section</span></span>


<a href="" id="how-to-install-application-virtualization-management-server"></a>[<span data-ttu-id="b74d2-110">如何安裝 Application Virtualization Management Server</span><span class="sxs-lookup"><span data-stu-id="b74d2-110">How to Install Application Virtualization Management Server</span></span>](how-to-install-application-virtualization-management-server.md)  
<span data-ttu-id="b74d2-111">提供安裝應用程式虛擬化管理伺服器並將其指派給適當伺服器群組的逐步程式。</span><span class="sxs-lookup"><span data-stu-id="b74d2-111">Provides a step-by-step procedure for installing the Application Virtualization Management Server and assigning it to the appropriate server group.</span></span>

<a href="" id="how-to-install-the-application-virtualization-streaming-server"></a>[<span data-ttu-id="b74d2-112">如何安裝 Application Virtualization Streaming Server</span><span class="sxs-lookup"><span data-stu-id="b74d2-112">How to Install the Application Virtualization Streaming Server</span></span>](how-to-install-the-application-virtualization-streaming-server.md)  
<span data-ttu-id="b74d2-113">提供安裝應用程式虛擬化資料流程伺服器並將它指派給適當的伺服器群組的逐步程式。</span><span class="sxs-lookup"><span data-stu-id="b74d2-113">Provides a step-by-step procedure for installing the Application Virtualization Streaming Server and assigning it to the appropriate server group.</span></span>

<a href="" id="how-to-install-the-management-web-service"></a>[<span data-ttu-id="b74d2-114">如何安裝 Management Web Service</span><span class="sxs-lookup"><span data-stu-id="b74d2-114">How to Install the Management Web Service</span></span>](how-to-install-the-management-web-service.md)  
<span data-ttu-id="b74d2-115">提供在您的網路上的目的電腦上安裝應用程式虛擬化管理 Web 服務的逐步程式。</span><span class="sxs-lookup"><span data-stu-id="b74d2-115">Provides a step-by-step procedure for installing the Application Virtualization Management Web Service on a target computer on your network.</span></span>

<a href="" id="how-to-install-the-management-console"></a>[<span data-ttu-id="b74d2-116">如何安裝管理主控台</span><span class="sxs-lookup"><span data-stu-id="b74d2-116">How to Install the Management Console</span></span>](how-to-install-the-management-console.md)  
<span data-ttu-id="b74d2-117">提供在您的網路上的目的電腦上安裝應用程式虛擬化管理主控台的逐步程式。</span><span class="sxs-lookup"><span data-stu-id="b74d2-117">Provides a step-by-step procedure for installing the Application Virtualization Management Console on a target computer on your network.</span></span>

<a href="" id="how-to-install-a-database"></a>[<span data-ttu-id="b74d2-118">如何安裝資料庫</span><span class="sxs-lookup"><span data-stu-id="b74d2-118">How to Install a Database</span></span>](how-to-install-a-database.md)  
<span data-ttu-id="b74d2-119">提供針對您的應用程式虛擬化部署（如果資料庫尚未推出）來安裝資料庫的逐步程式。</span><span class="sxs-lookup"><span data-stu-id="b74d2-119">Provides a step-by-step procedure for installing a database for your server-based deployment of Application Virtualization, if a database is not already available.</span></span>

<a href="" id="how-to-remove-the-application-virtualization-system-components"></a>[<span data-ttu-id="b74d2-120">如何移除 Application Virtualization 系統元件</span><span class="sxs-lookup"><span data-stu-id="b74d2-120">How to Remove the Application Virtualization System Components</span></span>](how-to-remove-the-application-virtualization-system-components.md)  
<span data-ttu-id="b74d2-121">提供從目的電腦中移除所有或已選取的應用程式虛擬化軟體元件的逐步程式。</span><span class="sxs-lookup"><span data-stu-id="b74d2-121">Provides step-by-step procedures to remove all or selected Application Virtualization software components from a target computer.</span></span>

## <span data-ttu-id="b74d2-122">相關主題</span><span class="sxs-lookup"><span data-stu-id="b74d2-122">Related topics</span></span>


[<span data-ttu-id="b74d2-123">以 Application Virtualization 伺服器為基礎的案例概觀</span><span class="sxs-lookup"><span data-stu-id="b74d2-123">Application Virtualization Server-Based Scenario Overview</span></span>](application-virtualization-server-based-scenario-overview.md)

[<span data-ttu-id="b74d2-124">如何針對以伺服器為基礎的部署設定伺服器</span><span class="sxs-lookup"><span data-stu-id="b74d2-124">How to Configure Servers for Server-Based Deployment</span></span>](how-to-configure-servers-for-server-based-deployment.md)

[<span data-ttu-id="b74d2-125">如何升級伺服器和系統元件</span><span class="sxs-lookup"><span data-stu-id="b74d2-125">How to Upgrade the Servers and System Components</span></span>](how-to-upgrade-the-servers-and-system-components.md)

 

 





