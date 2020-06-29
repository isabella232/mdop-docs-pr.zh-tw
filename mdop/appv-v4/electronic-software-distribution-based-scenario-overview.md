---
title: 以電子軟體發佈為基礎的案例概觀
description: 以電子軟體發佈為基礎的案例概觀
author: dansimp
ms.assetid: e9e94b8a-6cba-4de8-9b57-73897796b6a0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: cfbdf40f5ac0f61721c05d0da5cd49e910b16154
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808852"
---
# <span data-ttu-id="a2133-103">以電子軟體發佈為基礎的案例概觀</span><span class="sxs-lookup"><span data-stu-id="a2133-103">Electronic Software Distribution-Based Scenario Overview</span></span>


<span data-ttu-id="a2133-104">如果您打算使用電子軟體發佈（ESD）方案來部署虛擬應用程式，請務必瞭解該決策所要進入並受到影響的因素。</span><span class="sxs-lookup"><span data-stu-id="a2133-104">If you plan to use an electronic software distribution (ESD) solution to deploy virtual applications, it is important to understand the factors that go into and are affected by that decision.</span></span> <span data-ttu-id="a2133-105">本主題描述使用 ESD 式案例的優點，並提供發佈與套件流式處理方法的相關資訊，在您繼續進行部署時，您將需要考慮這些資訊。</span><span class="sxs-lookup"><span data-stu-id="a2133-105">This topic describes the benefits of using an ESD-based scenario and provides information about the publishing and package streaming methods that you will need to consider as you proceed with your deployment.</span></span>

<span data-ttu-id="a2133-106">**重要** 無論您使用的是哪一種 ESD 方案，您都必須熟悉特定解決方案的需求。</span><span class="sxs-lookup"><span data-stu-id="a2133-106">**Important** Whichever ESD solution you use, you must be familiar with the requirements of your particular solution.</span></span> <span data-ttu-id="a2133-107">如果您使用的是 Microsoft 端點設定管理員，請參閱位於的 Configuration Manager 檔 <https://go.microsoft.com/fwlink/?LinkId=66999> 。</span><span class="sxs-lookup"><span data-stu-id="a2133-107">If you are using Microsoft Endpoint Configuration Manager, see the Configuration Manager documentation at <https://go.microsoft.com/fwlink/?LinkId=66999>.</span></span>

 

<span data-ttu-id="a2133-108">使用現有的 ESD 系統會為您提供下列好處：</span><span class="sxs-lookup"><span data-stu-id="a2133-108">Using an existing ESD system provides you with the following benefits:</span></span>

-   <span data-ttu-id="a2133-109">消除雙管理基礎結構</span><span class="sxs-lookup"><span data-stu-id="a2133-109">Eliminates dual management infrastructures</span></span>

-   <span data-ttu-id="a2133-110">減少額外硬體的成本</span><span class="sxs-lookup"><span data-stu-id="a2133-110">Reduces the cost of additional hardware</span></span>

-   <span data-ttu-id="a2133-111">減少額外作業系統和資料庫授權的成本</span><span class="sxs-lookup"><span data-stu-id="a2133-111">Reduces the cost of additional operating system and database licenses</span></span>

## <span data-ttu-id="a2133-112">發佈方法</span><span class="sxs-lookup"><span data-stu-id="a2133-112">Publishing Methods</span></span>


<span data-ttu-id="a2133-113">使用 ESD 案例時，您可以選擇將應用程式發佈到用戶端的下列選項：</span><span class="sxs-lookup"><span data-stu-id="a2133-113">When using an ESD-based scenario, you have the following choices for publishing the application to the clients:</span></span>

-   **<span data-ttu-id="a2133-114">獨立 Windows 安裝程式。</span><span class="sxs-lookup"><span data-stu-id="a2133-114">Stand-alone Windows Installer.</span></span>** <span data-ttu-id="a2133-115">Windows Installer 檔案包含用戶端用來設定套件的資訊清單和 OSD 及 .ICO 檔案。</span><span class="sxs-lookup"><span data-stu-id="a2133-115">The Windows Installer file contains the manifest and the OSD and ICO files the clients use to configure a package.</span></span> <span data-ttu-id="a2133-116">Windows 安裝程式檔案也會將 SFT 檔案複製到用戶端，因為這個案例不使用伺服器。</span><span class="sxs-lookup"><span data-stu-id="a2133-116">The Windows Installer file also copies the SFT file to the client because this scenario does not use a server.</span></span>

-   **<span data-ttu-id="a2133-117">包含套件資訊清單的 Windows 安裝程式。</span><span class="sxs-lookup"><span data-stu-id="a2133-117">Windows Installer with the package manifest.</span></span>** <span data-ttu-id="a2133-118">Windows Installer 檔案包含用戶端用來設定套件的資訊清單和 OSD 及 .ICO 檔案。</span><span class="sxs-lookup"><span data-stu-id="a2133-118">The Windows Installer file contains the manifest and the OSD and ICO files the clients use to configure a package.</span></span> <span data-ttu-id="a2133-119">SFT 檔案會儲存在伺服器上。</span><span class="sxs-lookup"><span data-stu-id="a2133-119">The SFT file is stored on a server.</span></span> <span data-ttu-id="a2133-120">命令列參數會將用戶端導向到 SFT 檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="a2133-120">A command-line parameter directs the client to the location of the SFT file.</span></span>

-   **<span data-ttu-id="a2133-121">SFTMIME 命令。</span><span class="sxs-lookup"><span data-stu-id="a2133-121">SFTMIME commands.</span></span>** <span data-ttu-id="a2133-122">SFTMIME 命令會與資訊清單、OSD、.ICO 及 SFT 檔案搭配使用，以將套件新增到用戶端。</span><span class="sxs-lookup"><span data-stu-id="a2133-122">SFTMIME commands are used with the manifest, OSD, ICO, and SFT files to add packages to the client.</span></span> <span data-ttu-id="a2133-123">資訊清單檔案必須在用戶端電腦上，或必須可透過 UNC 路徑進行存取。</span><span class="sxs-lookup"><span data-stu-id="a2133-123">The manifest file must be on the client computer, or it must be accessible through a UNC path.</span></span> <span data-ttu-id="a2133-124">根據用戶端設定與命令列選項，OSD、.ICO 和 SFT 檔案可以位於用戶端電腦或伺服器上。</span><span class="sxs-lookup"><span data-stu-id="a2133-124">Depending on the client configuration and the command-line options, the OSD, ICO, and SFT files can be on the client computer or on a server.</span></span>

<span data-ttu-id="a2133-125">如需上述發佈方法的詳細資訊，請參閱[決定發佈方法](determine-your-publishing-method.md)。</span><span class="sxs-lookup"><span data-stu-id="a2133-125">For more detailed information about the preceding publishing methods, see [Determine Your Publishing Method](determine-your-publishing-method.md).</span></span>

## <span data-ttu-id="a2133-126">套件流式處理方法</span><span class="sxs-lookup"><span data-stu-id="a2133-126">Package Streaming Methods</span></span>


<span data-ttu-id="a2133-127">您必須判斷您的應用程式虛擬化系統會用來從伺服器將虛擬應用程式套件（或 SFT 檔案）資料流到用戶端的方法。</span><span class="sxs-lookup"><span data-stu-id="a2133-127">You will need to determine the method your Application Virtualization System will use to stream the virtual application packages, or SFT files, from the server to the clients.</span></span> <span data-ttu-id="a2133-128">下列資料流程選項可供使用：</span><span class="sxs-lookup"><span data-stu-id="a2133-128">The following streaming options are available:</span></span>

-   **<span data-ttu-id="a2133-129">應用程式虛擬化資料流程伺服器。</span><span class="sxs-lookup"><span data-stu-id="a2133-129">Application Virtualization Streaming Server.</span></span>** <span data-ttu-id="a2133-130">如果您在設定中使用應用程式虛擬化資料流程伺服器，則會使用 RTSP 或 RTSPS 通訊協定，將 SFT 檔案從該伺服器流入用戶端。</span><span class="sxs-lookup"><span data-stu-id="a2133-130">If you use an Application Virtualization Streaming Server in your configuration, the SFT files are streamed to the clients from that server using RTSP or RTSPS protocols.</span></span> <span data-ttu-id="a2133-131">您必須在電腦上安裝伺服器軟體，而且您必須透過登錄進行設定，但此設定不會依賴于 SQL 或 Active Directory 網域服務等服務。</span><span class="sxs-lookup"><span data-stu-id="a2133-131">You must install the server software on a computer and you must configure it through the registry, but this configuration does not depend on services such as SQL or Active Directory Domain Services.</span></span> <span data-ttu-id="a2133-132">SFT 檔案會儲存在伺服器上用戶端可存取的位置。</span><span class="sxs-lookup"><span data-stu-id="a2133-132">The SFT files are stored on the server at a location accessible by the clients.</span></span> <span data-ttu-id="a2133-133">發佈資訊可透過任何散佈機制分發給用戶端。</span><span class="sxs-lookup"><span data-stu-id="a2133-133">Publishing information can be distributed to the clients through any distribution mechanism.</span></span> <span data-ttu-id="a2133-134">不過，當設定時，用戶端會自動接收套件升級，且支援進行中的升級。</span><span class="sxs-lookup"><span data-stu-id="a2133-134">However, when configured, the client receives package upgrades automatically and active upgrade is supported.</span></span>

-   **<span data-ttu-id="a2133-135">應用程式虛擬化管理伺服器。</span><span class="sxs-lookup"><span data-stu-id="a2133-135">Application Virtualization Management Server.</span></span>** <span data-ttu-id="a2133-136">如果您在設定中使用應用程式虛擬化管理伺服器，則會使用 RTSP 或 RTSPS 通訊協定，將 SFT 檔案從該伺服器流入用戶端。</span><span class="sxs-lookup"><span data-stu-id="a2133-136">If you use an Application Virtualization Management Server in your configuration, the SFT files are streamed to the clients from that server using RTSP or RTSPS protocols.</span></span> <span data-ttu-id="a2133-137">您可以透過應用程式虛擬化管理主控台來管理此伺服器。</span><span class="sxs-lookup"><span data-stu-id="a2133-137">You manage this server through the Application Virtualization Management Console.</span></span> <span data-ttu-id="a2133-138">此設定會使用 SQL 資料庫和 Active Directory 服務。</span><span class="sxs-lookup"><span data-stu-id="a2133-138">This configuration uses a SQL database and Active Directory services.</span></span> <span data-ttu-id="a2133-139">伺服器可將發佈資訊散佈到用戶端，因此不需要額外的發佈機制。</span><span class="sxs-lookup"><span data-stu-id="a2133-139">The server can distribute publishing information to the clients, so additional publishing mechanisms are not needed.</span></span>

-   **<span data-ttu-id="a2133-140">檔案伺服器。</span><span class="sxs-lookup"><span data-stu-id="a2133-140">File server.</span></span>** <span data-ttu-id="a2133-141">如果您在設定中使用檔案伺服器，則會使用 SMB 通訊協定，將 SFT 檔案流式處理到其他用戶端電腦。</span><span class="sxs-lookup"><span data-stu-id="a2133-141">If you use a file server in your configuration, the SFT files are streamed to the other client computers by using SMB protocols.</span></span> <span data-ttu-id="a2133-142">此設定中使用的檔案伺服器是透過在檔案共用和 SFT 檔案上建立存取控制清單（Acl）來管理。</span><span class="sxs-lookup"><span data-stu-id="a2133-142">File servers used in this configuration are managed by creating access control lists (ACLs) on the file shares and SFT files.</span></span> <span data-ttu-id="a2133-143">請務必小心，將用戶端引導至檔案伺服器上的正確檔案。</span><span class="sxs-lookup"><span data-stu-id="a2133-143">Care must be taken to direct the clients to the correct files on the file server.</span></span>

-   **<span data-ttu-id="a2133-144">IIS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="a2133-144">IIS server.</span></span>** <span data-ttu-id="a2133-145">如果您在設定中使用 IIS 伺服器，則會使用 HTTP 或 HTTPS 通訊協定，將 SFT 檔案從該伺服器流入用戶端。</span><span class="sxs-lookup"><span data-stu-id="a2133-145">If you use an IIS server in your configuration, the SFT files are streamed to the clients from that server using HTTP or HTTPS protocols.</span></span> <span data-ttu-id="a2133-146">IIS 伺服器很容易設定和管理。</span><span class="sxs-lookup"><span data-stu-id="a2133-146">The IIS server is easy to configure and manage.</span></span> <span data-ttu-id="a2133-147">請務必小心，將用戶端引導至 IIS 伺服器上的正確檔案。</span><span class="sxs-lookup"><span data-stu-id="a2133-147">Care must be taken to direct the clients to the correct files on the IIS server.</span></span>

<span data-ttu-id="a2133-148">如需上述流式處理方法的詳細資訊，請參閱[判斷您的流式處理方法](determine-your-streaming-method.md)。</span><span class="sxs-lookup"><span data-stu-id="a2133-148">For more detailed information about the preceding streaming methods, see [Determine Your Streaming Method](determine-your-streaming-method.md).</span></span>

## <span data-ttu-id="a2133-149">相關主題</span><span class="sxs-lookup"><span data-stu-id="a2133-149">Related topics</span></span>


[<span data-ttu-id="a2133-150">Application Virtualization Client 安裝程式命令列參數</span><span class="sxs-lookup"><span data-stu-id="a2133-150">Application Virtualization Client Installer Command-Line Parameters</span></span>](application-virtualization-client-installer-command-line-parameters.md)

[<span data-ttu-id="a2133-151">以 Application Virtualization 伺服器為基礎的案例</span><span class="sxs-lookup"><span data-stu-id="a2133-151">Application Virtualization Server-Based Scenario</span></span>](application-virtualization-server-based-scenario.md)

[<span data-ttu-id="a2133-152">決定您的發佈方法</span><span class="sxs-lookup"><span data-stu-id="a2133-152">Determine Your Publishing Method</span></span>](determine-your-publishing-method.md)

[<span data-ttu-id="a2133-153">決定您的串流方法</span><span class="sxs-lookup"><span data-stu-id="a2133-153">Determine Your Streaming Method</span></span>](determine-your-streaming-method.md)

[<span data-ttu-id="a2133-154">以電子軟體發佈為基礎的案例</span><span class="sxs-lookup"><span data-stu-id="a2133-154">Electronic Software Distribution-Based Scenario</span></span>](electronic-software-distribution-based-scenario.md)

[<span data-ttu-id="a2133-155">SFTMIME 命令參考</span><span class="sxs-lookup"><span data-stu-id="a2133-155">SFTMIME Command Reference</span></span>](sftmime--command-reference.md)

 

 





