---
title: 規劃 Application Virtualization Client 部署
description: 規劃 Application Virtualization Client 部署
author: dansimp
ms.assetid: a352f80f-f0f9-4fbf-ac10-24c510b2d6be
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6c9fc4f29020af83a8606827015947e78761f4d7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800922"
---
# <span data-ttu-id="dd14f-103">規劃 Application Virtualization Client 部署</span><span class="sxs-lookup"><span data-stu-id="dd14f-103">Planning for Application Virtualization Client Deployment</span></span>


<span data-ttu-id="dd14f-104">決定如何將虛擬應用程式套件發佈並部署到您的最終使用者電腦之後，您應該規劃應用程式虛擬化用戶端軟體的部署。</span><span class="sxs-lookup"><span data-stu-id="dd14f-104">After you have decided how you will publish and deploy virtual application packages to your end user computers, you should plan the deployment of the Application Virtualization Client software.</span></span>

<span data-ttu-id="dd14f-105">應用程式虛擬化用戶端是實際執行虛擬應用程式的元件。</span><span class="sxs-lookup"><span data-stu-id="dd14f-105">The Application Virtualization Client is the component that actually runs the virtual applications.</span></span> <span data-ttu-id="dd14f-106">應用程式虛擬化用戶端可讓使用者與圖示互動，並按兩下檔案類型來啟動虛擬應用程式。</span><span class="sxs-lookup"><span data-stu-id="dd14f-106">The Application Virtualization Client enables users to interact with icons and to double-click file types to start a virtual application.</span></span> <span data-ttu-id="dd14f-107">它也會從流式處理伺服器處理應用程式內容的資料流程，並在啟動應用程式之前先將其進行緩衝。</span><span class="sxs-lookup"><span data-stu-id="dd14f-107">It also handles streaming of the application content from a streaming server and caches it before starting the application.</span></span> <span data-ttu-id="dd14f-108">應用程式內容的結構化，即啟動應用程式及處理初始使用者互動所需的所有內容都會先以資料流程傳送給最終使用者的電腦。</span><span class="sxs-lookup"><span data-stu-id="dd14f-108">The application content is structured such that all the content needed to start the application and handle initial user interaction is streamed to the end user computer first.</span></span> <span data-ttu-id="dd14f-109">應用程式虛擬化用戶端軟體有兩種不同的類型：遠端桌面服務（舊稱終端服務）的應用程式虛擬化用戶端，用於遠端桌面工作階段主機（RDSession 主機）伺服器系統，以及適用于所有其他電腦的應用程式虛擬化桌面用戶端。</span><span class="sxs-lookup"><span data-stu-id="dd14f-109">There are two different types of Application Virtualization Client software: the Application Virtualization Client for Remote Desktop Services (formerly Terminal Services), which is used on Remote Desktop Session Host (RDSession Host) server systems, and the Application Virtualization Desktop Client, which is used for all other computers.</span></span>

<span data-ttu-id="dd14f-110">應用程式虛擬化用戶端應該在安裝期間以應用程式虛擬化管理主控台或透過安裝程式命令列來設定，包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="dd14f-110">The Application Virtualization Client should be configured at installation time, either in the Application Virtualization Management Console or via the installer command line, with a number of important settings, including the following:</span></span>

-   <span data-ttu-id="dd14f-111">所有應用程式之圖示的位置。</span><span class="sxs-lookup"><span data-stu-id="dd14f-111">Locations of the icons for all the applications.</span></span>

-   <span data-ttu-id="dd14f-112">包含套件定義資訊的 OSD 檔案位置。</span><span class="sxs-lookup"><span data-stu-id="dd14f-112">The location of the OSD file that contains the package definition information.</span></span>

-   <span data-ttu-id="dd14f-113">應用程式內容來源。</span><span class="sxs-lookup"><span data-stu-id="dd14f-113">The application content source.</span></span>

-   <span data-ttu-id="dd14f-114">檢索前面的專案時要使用的通訊通訊協定。</span><span class="sxs-lookup"><span data-stu-id="dd14f-114">The communications protocol to be used when retrieving the preceding items.</span></span>

-   <span data-ttu-id="dd14f-115">要使用的快取大小與快取大小管理方法。</span><span class="sxs-lookup"><span data-stu-id="dd14f-115">The cache size and cache size management method to be used.</span></span>

<span data-ttu-id="dd14f-116">若要在使用電子軟體發佈（ESD）方案時，加速應用程式虛擬化用戶端軟體的部署，必須事先謹慎定義前面的設定。</span><span class="sxs-lookup"><span data-stu-id="dd14f-116">To expedite the deployment of the Application Virtualization Client software when using an electronic software distribution (ESD) solution, the preceding settings must be defined carefully in advance.</span></span> <span data-ttu-id="dd14f-117">當您的電腦位於不同的辦公室，且需要將其用戶端設定為使用不同的來源位置時，這一點尤為重要。</span><span class="sxs-lookup"><span data-stu-id="dd14f-117">This is especially important when you have computers in different offices, where their clients would need to be configured to use different source locations.</span></span>

**<span data-ttu-id="dd14f-118">注意</span><span class="sxs-lookup"><span data-stu-id="dd14f-118">Note</span></span>**  
-   <span data-ttu-id="dd14f-119">在選擇發佈方法時（無論是使用 Windows Installer 或 SFTMIME），圖示位置和 OSD 檔案值都是要考慮的重要因素。</span><span class="sxs-lookup"><span data-stu-id="dd14f-119">The icon location and OSD file values are an important factor to consider when choosing your publishing method, whether using Windows Installer or SFTMIME.</span></span> <span data-ttu-id="dd14f-120">應用程式內容來源的設定是由您選擇的流式處理方法所定義。</span><span class="sxs-lookup"><span data-stu-id="dd14f-120">The setting for the application content source is defined by your choice of streaming method.</span></span>

-   <span data-ttu-id="dd14f-121">若要確保快取已為所有已部署套件指派足夠的空間，請使用設定用戶端時使用的 [**可用磁碟空間閾值**] 設定，讓快取視需要增加。</span><span class="sxs-lookup"><span data-stu-id="dd14f-121">To ensure that the cache has sufficient space allocated for all packages that might be deployed, use the **Use free disk space threshold** setting when you configure the client so that the cache can grow as needed.</span></span> <span data-ttu-id="dd14f-122">或者，您可以在安裝期間預先決定需要多少磁碟空間，並在安裝時設定快取大小。</span><span class="sxs-lookup"><span data-stu-id="dd14f-122">Alternatively, determine in advance how much disk space will be needed for the App-V cache, and at installation time, set the cache size accordingly.</span></span> <span data-ttu-id="dd14f-123">如需有關緩衝空間管理功能的詳細資訊，請參閱如何使用 Microsoft Application Virtualization （App-v）操作指南中的快取**空間管理功能**。</span><span class="sxs-lookup"><span data-stu-id="dd14f-123">For more information about the cache space management feature, see **How to Use the Cache Space Management Feature** in the Microsoft Application Virtualization (App-V) Operations Guide.</span></span>

-   <span data-ttu-id="dd14f-124">在發佈與 HTTP （S）資料流程作業期間，App-v 4.5 SP1 用戶端會使用在使用者電腦上的 Internet Explorer 中設定的 proxy 伺服器設定。</span><span class="sxs-lookup"><span data-stu-id="dd14f-124">During both the publishing and HTTP(S) streaming operations,App-V 4.5 SP1 clients use the proxy server settings that are configured in Internet Explorer on the user’s computer.</span></span>

<span data-ttu-id="dd14f-125">如需有關設定用戶端安裝參數的詳細資訊，請參閱[應用程式虛擬化用戶端安裝程式命令列參數](application-virtualization-client-installer-command-line-parameters.md)。</span><span class="sxs-lookup"><span data-stu-id="dd14f-125">For more information about configuring the client installation parameters, see [Application Virtualization Client Installer Command-Line Parameters](application-virtualization-client-installer-command-line-parameters.md).</span></span>

 

<span data-ttu-id="dd14f-126">最後，您必須決定如何為桌面用戶端部署 Application Virtualization 桌面用戶端軟體。</span><span class="sxs-lookup"><span data-stu-id="dd14f-126">Finally, you need to determine how to deploy the Application Virtualization Desktop Client software for the desktop clients.</span></span> <span data-ttu-id="dd14f-127">雖然您可以在每個電腦上手動部署應用程式虛擬化桌面用戶端，但大多陣列織必須透過一些自動化程式來執行此操作。</span><span class="sxs-lookup"><span data-stu-id="dd14f-127">Although it is possible to deploy the Application Virtualization Desktop Client manually on each computer, most organizations would need to do this through some automated process.</span></span> <span data-ttu-id="dd14f-128">中型或大型組織可能會有 ESD 系統在運作中，這是部署用戶端的理想方式。</span><span class="sxs-lookup"><span data-stu-id="dd14f-128">A medium or large organization might have an ESD system in operation, and that would be an ideal way to deploy the client.</span></span> <span data-ttu-id="dd14f-129">如果不存在 ESD 系統，您可以使用您在組織中安裝軟體的標準方法。</span><span class="sxs-lookup"><span data-stu-id="dd14f-129">If no ESD system exists, you can use your standard method of installing software in your organization.</span></span> <span data-ttu-id="dd14f-130">選項包括群組原則或各種腳本技術。</span><span class="sxs-lookup"><span data-stu-id="dd14f-130">Choices include Group Policy or various scripting techniques.</span></span> <span data-ttu-id="dd14f-131">視您擁有的辦公室數量和規模而定，此部署程式可能很複雜，而且您必須使用結構化的方法，以確保所有電腦都能以正確的設定來取得安裝的用戶端。</span><span class="sxs-lookup"><span data-stu-id="dd14f-131">Depending on the number and size of the offices you have, this deployment process can be complex, and it is essential that you take a structured approach to ensure all computers get a client installed with the correct configuration.</span></span>

## <span data-ttu-id="dd14f-132">相關主題</span><span class="sxs-lookup"><span data-stu-id="dd14f-132">Related topics</span></span>


[<span data-ttu-id="dd14f-133">規劃 Application Virtualization 系統部署</span><span class="sxs-lookup"><span data-stu-id="dd14f-133">Planning for Application Virtualization System Deployment</span></span>](planning-for-application-virtualization-system-deployment.md)

[<span data-ttu-id="dd14f-134">如何使用命令列安裝用戶端</span><span class="sxs-lookup"><span data-stu-id="dd14f-134">How to Install the Client by Using the Command Line</span></span>](how-to-install-the-client-by-using-the-command-line-new.md)

[<span data-ttu-id="dd14f-135">如何在用戶端上發佈虛擬應用程式</span><span class="sxs-lookup"><span data-stu-id="dd14f-135">How to Publish a Virtual Application on the Client</span></span>](how-to-publish-a-virtual-application-on-the-client.md)

[<span data-ttu-id="dd14f-136">如何升級 Application Virtualization Client</span><span class="sxs-lookup"><span data-stu-id="dd14f-136">How to Upgrade the Application Virtualization Client</span></span>](how-to-upgrade-the-application-virtualization-client.md)

[<span data-ttu-id="dd14f-137">如何解除安裝 App-V Client</span><span class="sxs-lookup"><span data-stu-id="dd14f-137">How to Uninstall the App-V Client</span></span>](how-to-uninstall-the-app-v-client.md)

 

 





