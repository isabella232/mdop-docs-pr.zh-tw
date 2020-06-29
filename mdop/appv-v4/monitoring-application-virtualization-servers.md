---
title: 監視 Application Virtualization 伺服器
description: 監視 Application Virtualization 伺服器
author: dansimp
ms.assetid: d84355ae-4fe4-41d9-ac3a-3eaa32d9a61f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a53c0c37ca609c701727a7f4e18019a9f20110ed
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800960"
---
# <span data-ttu-id="734a7-103">監視 Application Virtualization 伺服器</span><span class="sxs-lookup"><span data-stu-id="734a7-103">Monitoring Application Virtualization Servers</span></span>


<span data-ttu-id="734a7-104">若要簡化應用程式虛擬化（App-v）伺服器管理，您可以使用 System Center Operations Manager2007 管理套件。</span><span class="sxs-lookup"><span data-stu-id="734a7-104">To simplify Application Virtualization (App-V) Server management, you can use the System Center Operations Manager2007 Management Pack.</span></span> <span data-ttu-id="734a7-105">此管理套件只支援應用程式虛擬化（App-v）4.5 伺服器;它不支援舊版伺服器版本。</span><span class="sxs-lookup"><span data-stu-id="734a7-105">This Management Pack supports only Application Virtualization (App-V) 4.5 servers; it does not support previous server versions.</span></span> <span data-ttu-id="734a7-106">管理套件可將 App V 伺服器可用性最大化，以處理 App-v 用戶端的要求。</span><span class="sxs-lookup"><span data-stu-id="734a7-106">The Management Pack maximizes App-V Server availability for handling App-V Client requests.</span></span>

## <span data-ttu-id="734a7-107">狀態指示器</span><span class="sxs-lookup"><span data-stu-id="734a7-107">Status Indicators</span></span>


<span data-ttu-id="734a7-108">App-v 伺服器健康情況指示器以色彩標示。</span><span class="sxs-lookup"><span data-stu-id="734a7-108">The App-V Server health status indicators are color-coded.</span></span> <span data-ttu-id="734a7-109">這些色彩代表下列狀態值：</span><span class="sxs-lookup"><span data-stu-id="734a7-109">The colors represent the following status values:</span></span>

-   <span data-ttu-id="734a7-110">[無色彩] 表示伺服器執行沒有無法復原的錯誤。</span><span class="sxs-lookup"><span data-stu-id="734a7-110">No color indicates that the server is running without non-recoverable errors.</span></span>

-   <span data-ttu-id="734a7-111">黃色表示其中一個元件無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="734a7-111">Yellow indicates that one of the components is not functioning correctly.</span></span> <span data-ttu-id="734a7-112">伺服器的整體功能已降級，但伺服器仍可供使用。</span><span class="sxs-lookup"><span data-stu-id="734a7-112">The overall functionality of the server is degraded, but the server is still available.</span></span>

-   <span data-ttu-id="734a7-113">紅色表示伺服器無法使用且無法提供重要服務或與外部服務相依性進行通訊。</span><span class="sxs-lookup"><span data-stu-id="734a7-113">Red indicates that the server is not available and that it cannot provide key services or communicate with external service dependencies.</span></span>

## <span data-ttu-id="734a7-114">監視準則</span><span class="sxs-lookup"><span data-stu-id="734a7-114">Monitoring Criteria</span></span>


<span data-ttu-id="734a7-115">管理套件會監視伺服器健康情況的下列幾個方面：</span><span class="sxs-lookup"><span data-stu-id="734a7-115">The Management Pack monitors the following aspects of server health:</span></span>

-   <span data-ttu-id="734a7-116">伺服器狀態-監視伺服器事件以驗證服務器是否提供其預期的服務。</span><span class="sxs-lookup"><span data-stu-id="734a7-116">Server Status—monitors server events to validate that the server is providing its expected services.</span></span>

-   <span data-ttu-id="734a7-117">資料儲存區存取：追蹤一或多個應用程式 V 管理伺服器存取並與 App-v 資料儲存區通訊的能力。</span><span class="sxs-lookup"><span data-stu-id="734a7-117">Data Store Access—tracks the ability of one or more of the App-V Management Servers to access and communicate with the App-V data store.</span></span>

-   <span data-ttu-id="734a7-118">內容資料存取-監視 \\Content 目錄的存取權（可能是本機目錄或網路共用），以及讀取要求的檔案的功能。</span><span class="sxs-lookup"><span data-stu-id="734a7-118">Content Data Access—monitors access to the \\Content directory, which might be a local directory or a network share, and the ability to read the requested files.</span></span>

-   <span data-ttu-id="734a7-119">安全性：使用 App-v 伺服器的憑證和安全通訊來報告錯誤。</span><span class="sxs-lookup"><span data-stu-id="734a7-119">Security—reports errors with the App-V Server’s certificate and secure communications.</span></span>

-   <span data-ttu-id="734a7-120">用戶端要求處理-監視一或多個 App-v 伺服器處理的功能，並正確回應用戶端要求。</span><span class="sxs-lookup"><span data-stu-id="734a7-120">Client Request Handling—monitors the ability of one or more of the App-V Servers to handle and correctly respond to client requests.</span></span> <span data-ttu-id="734a7-121">這些要求包括發佈諸如設定要求、套件載入要求，以及不順序要求等專案。</span><span class="sxs-lookup"><span data-stu-id="734a7-121">These requests include publishing such items as configuration requests, package load requests, and out of sequence requests.</span></span>

-   <span data-ttu-id="734a7-122">伺服器設定：檢查 App-v 伺服器的設定設定。</span><span class="sxs-lookup"><span data-stu-id="734a7-122">Server Configuration—checks the configuration settings of the App-V Server.</span></span> <span data-ttu-id="734a7-123">這些設定會將設定包含在 registry 和 App-v 資料儲存區中。</span><span class="sxs-lookup"><span data-stu-id="734a7-123">These configuration settings include the settings in the registry and in the App-V data store.</span></span>

## <span data-ttu-id="734a7-124">伺服器差異</span><span class="sxs-lookup"><span data-stu-id="734a7-124">Server Differences</span></span>


<span data-ttu-id="734a7-125">App V 管理伺服器與 App-v 流式處理伺服器之間的主要差異如下：</span><span class="sxs-lookup"><span data-stu-id="734a7-125">The main differences between the App-V Management Server and the App-V Streaming Server are as follows:</span></span>

-   <span data-ttu-id="734a7-126">App-v 管理伺服器可提供發佈、流式處理、管理及報表服務。</span><span class="sxs-lookup"><span data-stu-id="734a7-126">App-V Management Servers can provide publishing, streaming, management, and reporting services.</span></span> <span data-ttu-id="734a7-127">因此，管理套件可以管理 App-v Management Server 的其他方面，而不能在僅提供套件資料流程的 App-v 資料流程伺服器上管理。</span><span class="sxs-lookup"><span data-stu-id="734a7-127">Therefore, the Management Pack can manage more aspects of the App-V Management Server than it can manage on the App-V Streaming Server, which provides only package streaming.</span></span>

-   <span data-ttu-id="734a7-128">App-v 流式處理伺服器沒有 App-v 資料儲存區，因此不會監視資料儲存區存取。</span><span class="sxs-lookup"><span data-stu-id="734a7-128">The App-V Streaming Server does not have an App-V data store, so data store access is not monitored.</span></span> <span data-ttu-id="734a7-129">App-v 流式處理伺服器的設定資訊是在登錄中進行管理。</span><span class="sxs-lookup"><span data-stu-id="734a7-129">The configuration information for the App-V Streaming Server is managed in the registry.</span></span>

-   <span data-ttu-id="734a7-130">App-v 流式處理伺服器不使用 App-v Server 管理主控台介面;使用其他工具管理設定。</span><span class="sxs-lookup"><span data-stu-id="734a7-130">The App-V Streaming Server does not use the App-V Server Management Console interface; use other tools to manage the configuration.</span></span>

## <span data-ttu-id="734a7-131">相關主題</span><span class="sxs-lookup"><span data-stu-id="734a7-131">Related topics</span></span>


[<span data-ttu-id="734a7-132">Application Virtualization 伺服器</span><span class="sxs-lookup"><span data-stu-id="734a7-132">Application Virtualization Server</span></span>](application-virtualization-server.md)

 

 





