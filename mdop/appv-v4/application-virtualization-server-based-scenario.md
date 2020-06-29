---
title: 以 Application Virtualization 伺服器為基礎的案例
description: 以 Application Virtualization 伺服器為基礎的案例
author: dansimp
ms.assetid: 10ed0b18-087d-470f-951b-5083f4cb076f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d6699bdc734258f67e4938e33266a2f061531939
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802253"
---
# <span data-ttu-id="87655-103">以 Application Virtualization 伺服器為基礎的案例</span><span class="sxs-lookup"><span data-stu-id="87655-103">Application Virtualization Server-Based Scenario</span></span>


<span data-ttu-id="87655-104">如果您打算針對 Microsoft 應用程式虛擬化（App-v）環境使用以伺服器為基礎的部署案例，您應該瞭解應用程式虛擬化管理伺服器與應用程式虛擬化資料流程伺服器之間的差異。</span><span class="sxs-lookup"><span data-stu-id="87655-104">If you plan to use a server-based deployment scenario for your Microsoft Application Virtualization (App-V) environment, you should understand the differences between the Application Virtualization Management Server and the Application Virtualization Streaming Server.</span></span> <span data-ttu-id="87655-105">本節中的主題描述這些差異，並提供套件傳遞方法、傳輸通訊協定和外部元件的相關資訊，您必須考慮在您繼續進行部署。</span><span class="sxs-lookup"><span data-stu-id="87655-105">The topics in this section describe those differences and also provide information about package delivery methods, transmission protocols, and external components that you have to consider as you continue with your deployment.</span></span> <span data-ttu-id="87655-106">本節也提供安裝和設定 App-v 管理伺服器與應用程式虛擬化資料流程伺服器的逐步程式。</span><span class="sxs-lookup"><span data-stu-id="87655-106">This section also provides step-by-step procedures for installing and configuring the App-V Management Server and the Application Virtualization Streaming Servers.</span></span>

## <span data-ttu-id="87655-107">本節內容</span><span class="sxs-lookup"><span data-stu-id="87655-107">In This Section</span></span>


<a href="" id="application-virtualization-server-based-scenario-overview"></a>[<span data-ttu-id="87655-108">以 Application Virtualization 伺服器為基礎的案例概觀</span><span class="sxs-lookup"><span data-stu-id="87655-108">Application Virtualization Server-Based Scenario Overview</span></span>](application-virtualization-server-based-scenario-overview.md)  
<span data-ttu-id="87655-109">提供有關應用程式虛擬化管理伺服器、應用程式虛擬化資料流程伺服器以及與您伺服器的部署方案相關的套件傳遞方法、協定和外部元件的重要部署資訊。</span><span class="sxs-lookup"><span data-stu-id="87655-109">Provides important deployment information about the Application Virtualization Management Server, the Application Virtualization Streaming Server, and the package delivery methods, protocols, and external components relevant to your server-based deployment plan.</span></span>

<a href="" id="how-to-install-the-servers-and-system-components"></a>[<span data-ttu-id="87655-110">如何安裝伺服器和系統元件</span><span class="sxs-lookup"><span data-stu-id="87655-110">How to Install the Servers and System Components</span></span>](how-to-install-the-servers-and-system-components.md)  
<span data-ttu-id="87655-111">說明如何安裝以伺服器為基礎的部署所需的 Microsoft Application Virtualization 平台元件。</span><span class="sxs-lookup"><span data-stu-id="87655-111">Describes how to install the Microsoft Application Virtualization platform components required for your server-based deployment.</span></span>

<a href="" id="how-to-configure-servers-for-server-based-deployment"></a>[<span data-ttu-id="87655-112">如何針對以伺服器為基礎的部署設定伺服器</span><span class="sxs-lookup"><span data-stu-id="87655-112">How to Configure Servers for Server-Based Deployment</span></span>](how-to-configure-servers-for-server-based-deployment.md)  
<span data-ttu-id="87655-113">說明如何設定應用程式虛擬化管理伺服器、應用程式虛擬化資料流程伺服器、網際網路資訊整合（IIS）伺服器和檔案伺服器。</span><span class="sxs-lookup"><span data-stu-id="87655-113">Describes how to configure the Application Virtualization Management Server, the Application Virtualization Streaming Server, the Internet Information Integration (IIS) server, and the file server.</span></span>

<a href="" id="how-to-configure-a-read-only-cache-on-the-app-v-client--vdi-"></a>[<span data-ttu-id="87655-114">如何在 App-V 用戶端 (VDI) 上設定唯讀快取</span><span class="sxs-lookup"><span data-stu-id="87655-114">How to Configure a Read-only Cache on the App-V Client (VDI)</span></span>](how-to-configure-a-read-only-cache-on-the-app-v-client--vdi-.md)  
<span data-ttu-id="87655-115">說明如何將 App-v 用戶端設定為使用唯讀快取。</span><span class="sxs-lookup"><span data-stu-id="87655-115">Describes how to configure the App-V client to use read-only cache.</span></span>

<a href="" id="how-to-configure-a-read-only-cache-on-the-app-v-client--rds-"></a>[<span data-ttu-id="87655-116">如何在 App-V 用戶端 (RDS) 上設定唯讀快取</span><span class="sxs-lookup"><span data-stu-id="87655-116">How to Configure a Read-only Cache on the App-V Client (RDS)</span></span>](how-to-configure-a-read-only-cache-on-the-app-v-client--rds--sp1.md)  
<span data-ttu-id="87655-117">說明如何將 App-v 用戶端設定為使用唯讀快取。</span><span class="sxs-lookup"><span data-stu-id="87655-117">Describes how to configure the App-V client to use read-only cache.</span></span>

<a href="" id="how-to-configure-microsoft-sql-server-mirroring-support-for-app-v"></a>[<span data-ttu-id="87655-118">如何為 App-V 設定 Microsoft SQL Server 鏡像支援</span><span class="sxs-lookup"><span data-stu-id="87655-118">How to Configure Microsoft SQL Server Mirroring Support for App-V</span></span>](how-to-configure-microsoft-sql-server-mirroring-support-for-app-v.md)  
<span data-ttu-id="87655-119">說明如何使用 Microsoft SQL Server 針對您的 App-v 系統來設定資料庫鏡像。</span><span class="sxs-lookup"><span data-stu-id="87655-119">Describes how to configure database mirroring by using Microsoft SQL Server for your App-V system.</span></span>

## <span data-ttu-id="87655-120">參考</span><span class="sxs-lookup"><span data-stu-id="87655-120">Reference</span></span>


[<span data-ttu-id="87655-121">Application Virtualization Client 安裝程式命令列參數</span><span class="sxs-lookup"><span data-stu-id="87655-121">Application Virtualization Client Installer Command-Line Parameters</span></span>](application-virtualization-client-installer-command-line-parameters.md)

## <span data-ttu-id="87655-122">相關章節</span><span class="sxs-lookup"><span data-stu-id="87655-122">Related Sections</span></span>


[<span data-ttu-id="87655-123">以電子軟體發佈為基礎的案例</span><span class="sxs-lookup"><span data-stu-id="87655-123">Electronic Software Distribution-Based Scenario</span></span>](electronic-software-distribution-based-scenario.md)

## <span data-ttu-id="87655-124">相關主題</span><span class="sxs-lookup"><span data-stu-id="87655-124">Related topics</span></span>


[<span data-ttu-id="87655-125">Application Virtualization 部署與升級考量</span><span class="sxs-lookup"><span data-stu-id="87655-125">Application Virtualization Deployment and Upgrade Considerations</span></span>](application-virtualization-deployment-and-upgrade-considerations.md)

[<span data-ttu-id="87655-126">Application Virtualization Client 的獨立傳遞案例</span><span class="sxs-lookup"><span data-stu-id="87655-126">Stand-Alone Delivery Scenario for Application Virtualization Clients</span></span>](stand-alone-delivery-scenario-for-application-virtualization-clients.md)

 

 





