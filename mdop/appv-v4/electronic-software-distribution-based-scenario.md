---
title: 以電子軟體發佈為基礎的案例
description: 以電子軟體發佈為基礎的案例
author: dansimp
ms.assetid: 18be0f8d-60ee-449b-aa83-93c86d1a908e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 52b9a30f2b1d403ec41090252f331a984225fd19
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808847"
---
# <span data-ttu-id="c9690-103">以電子軟體發佈為基礎的案例</span><span class="sxs-lookup"><span data-stu-id="c9690-103">Electronic Software Distribution-Based Scenario</span></span>


<span data-ttu-id="c9690-104">如果您打算針對您的 Microsoft 應用程式虛擬化環境使用電子軟體發佈（ESD）部署案例，請務必瞭解該決策所影響的因素。</span><span class="sxs-lookup"><span data-stu-id="c9690-104">If you plan to use an electronic software distribution (ESD) deployment scenario for your Microsoft Application Virtualization environment, it is important to understand the factors that go into and are affected by that decision.</span></span> <span data-ttu-id="c9690-105">本節中的主題描述 ESD 案例，並提供套件傳遞方法、傳輸通訊協定及外部元件的相關資訊，您將需要在部署策略中考慮。</span><span class="sxs-lookup"><span data-stu-id="c9690-105">The topics in this section describe the ESD scenario and provide information about package delivery methods, transmission protocols, and external components that you will need to consider in your deployment strategy.</span></span> <span data-ttu-id="c9690-106">您也可以使用本節中的程式，透過部署驗證階段從伺服器設定階段完成您的部署。</span><span class="sxs-lookup"><span data-stu-id="c9690-106">You can also use the procedures in this section to complete your deployment, from the server configuration phase through the deployment verification phase.</span></span>

## <span data-ttu-id="c9690-107">本節內容</span><span class="sxs-lookup"><span data-stu-id="c9690-107">In This Section</span></span>


<a href="" id="electronic-software-distribution-based-scenario-overview"></a>[<span data-ttu-id="c9690-108">以電子軟體發佈為基礎的案例概觀</span><span class="sxs-lookup"><span data-stu-id="c9690-108">Electronic Software Distribution-Based Scenario Overview</span></span>](electronic-software-distribution-based-scenario-overview.md)  
<span data-ttu-id="c9690-109">提供您可用於 ESD 式部署的發佈與流式處理方法的重要資訊。</span><span class="sxs-lookup"><span data-stu-id="c9690-109">Provides important information about the publishing and streaming methods you can use for an ESD-based deployment.</span></span>

<a href="" id="how-to-configure-servers-for-esd-based-deployment"></a>[<span data-ttu-id="c9690-110">如何針對以 ESD 為基礎的部署設定伺服器</span><span class="sxs-lookup"><span data-stu-id="c9690-110">How to Configure Servers for ESD-Based Deployment</span></span>](how-to-configure-servers-for-esd-based-deployment.md)  
<span data-ttu-id="c9690-111">本節提供的程式可讓您用來針對以電子軟體發佈為基礎的部署策略設定應用程式虛擬化資料流程伺服器、IIS 伺服器及檔案伺服器。</span><span class="sxs-lookup"><span data-stu-id="c9690-111">This section provides procedures you can use to configure the Application Virtualization Streaming Servers, the IIS server, and the file server for your electronic software distribution–based deployment strategy.</span></span>

<a href="" id="how-to-install-the-client-by-using-the-command-line"></a>[<span data-ttu-id="c9690-112">如何使用命令列安裝用戶端</span><span class="sxs-lookup"><span data-stu-id="c9690-112">How to Install the Client by Using the Command Line</span></span>](how-to-install-the-client-by-using-the-command-line-new.md)  
<span data-ttu-id="c9690-113">提供使用 setup.exe 或 setup.msi 檔案來安裝應用程式虛擬化用戶端的命令列程式。</span><span class="sxs-lookup"><span data-stu-id="c9690-113">Provides command-line procedures for installing the Application Virtualization Client, using either the setup.exe or the setup.msi file.</span></span>

<a href="" id="how-to-uninstall-the-app-v-client"></a>[<span data-ttu-id="c9690-114">如何解除安裝 App-V Client</span><span class="sxs-lookup"><span data-stu-id="c9690-114">How to Uninstall the App-V Client</span></span>](how-to-uninstall-the-app-v-client.md)  
<span data-ttu-id="c9690-115">提供您可以用來確認應用程式虛擬化用戶端已安裝且正常運作的逐步程式。</span><span class="sxs-lookup"><span data-stu-id="c9690-115">Provides a step-by-step procedure you can use to confirm that the Application Virtualization Client has been installed and is functioning correctly.</span></span>

<a href="" id="how-to-publish-a-virtual-application-on-the-client"></a>[<span data-ttu-id="c9690-116">如何在用戶端上發佈虛擬應用程式</span><span class="sxs-lookup"><span data-stu-id="c9690-116">How to Publish a Virtual Application on the Client</span></span>](how-to-publish-a-virtual-application-on-the-client.md)  
<span data-ttu-id="c9690-117">提供使用 Windows Installer 或 SFTMIME 發佈應用程式套件的命令列程式。</span><span class="sxs-lookup"><span data-stu-id="c9690-117">Provides command-line procedures for publishing an application package, using either Windows Installer or SFTMIME.</span></span>

## <span data-ttu-id="c9690-118">參考</span><span class="sxs-lookup"><span data-stu-id="c9690-118">Reference</span></span>


[<span data-ttu-id="c9690-119">Application Virtualization Client 安裝程式命令列參數</span><span class="sxs-lookup"><span data-stu-id="c9690-119">Application Virtualization Client Installer Command-Line Parameters</span></span>](application-virtualization-client-installer-command-line-parameters.md)

## <span data-ttu-id="c9690-120">相關章節</span><span class="sxs-lookup"><span data-stu-id="c9690-120">Related Sections</span></span>


[<span data-ttu-id="c9690-121">以 Application Virtualization 伺服器為基礎的案例</span><span class="sxs-lookup"><span data-stu-id="c9690-121">Application Virtualization Server-Based Scenario</span></span>](application-virtualization-server-based-scenario.md)

## <span data-ttu-id="c9690-122">相關主題</span><span class="sxs-lookup"><span data-stu-id="c9690-122">Related topics</span></span>


[<span data-ttu-id="c9690-123">Application Virtualization 部署與升級考量</span><span class="sxs-lookup"><span data-stu-id="c9690-123">Application Virtualization Deployment and Upgrade Considerations</span></span>](application-virtualization-deployment-and-upgrade-considerations.md)

[<span data-ttu-id="c9690-124">Application Virtualization Client 的獨立傳遞案例</span><span class="sxs-lookup"><span data-stu-id="c9690-124">Stand-Alone Delivery Scenario for Application Virtualization Clients</span></span>](stand-alone-delivery-scenario-for-application-virtualization-clients.md)

 

 





