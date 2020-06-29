---
title: 應用程式虛擬化安全性指南簡介
description: 應用程式虛擬化安全性指南簡介
author: dansimp
ms.assetid: 50e1d220-7a95-45b8-933b-3dadddebe26f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 4b41c65c5ad753aa606d47d2eafe4a28e035cc4e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800985"
---
# <span data-ttu-id="ff0f6-103">應用程式虛擬化安全性指南簡介</span><span class="sxs-lookup"><span data-stu-id="ff0f6-103">Introduction to the Application Virtualization Security Guide</span></span>


<span data-ttu-id="ff0f6-104">此 Microsoft Application Virtualization （App-v） security guide （應用程式-V）安全性指南為負責設定 App V 部署所選取的安全性功能的管理員提供指示。</span><span class="sxs-lookup"><span data-stu-id="ff0f6-104">This Microsoft Application Virtualization (App-V) security guide provides instructions for administrators who are responsible for configuring the security features that were selected for the App-V deployment.</span></span>

<span data-ttu-id="ff0f6-105">**記事** 本檔不提供選擇特定安全性選項的指導方針。</span><span class="sxs-lookup"><span data-stu-id="ff0f6-105">**Note** This documentation does not provide guidance for choosing the specific security options.</span></span> <span data-ttu-id="ff0f6-106">該資訊是在 App-V 安全性最佳做法中提供的白皮書中提供 <https://go.microsoft.com/fwlink/?LinkId=127120> 。</span><span class="sxs-lookup"><span data-stu-id="ff0f6-106">That information is provided in the App-V Security Best Practices white paper available at <https://go.microsoft.com/fwlink/?LinkId=127120>.</span></span>

 

<span data-ttu-id="ff0f6-107">如果您是使用本指南的 App-v 系統管理員，您應該熟悉下列與安全性相關的技術：</span><span class="sxs-lookup"><span data-stu-id="ff0f6-107">As an App-V administrator using this guide, you should be familiar with the following security-related technologies:</span></span>

-   <span data-ttu-id="ff0f6-108">Active Directory Domain Services</span><span class="sxs-lookup"><span data-stu-id="ff0f6-108">Active Directory Domain Services</span></span>

-   <span data-ttu-id="ff0f6-109">公開金鑰基礎結構（PKI）</span><span class="sxs-lookup"><span data-stu-id="ff0f6-109">Public key infrastructure (PKI)</span></span>

-   <span data-ttu-id="ff0f6-110">網際網路通訊協定安全性（IPsec）</span><span class="sxs-lookup"><span data-stu-id="ff0f6-110">Internet Protocol Security (IPsec)</span></span>

-   <span data-ttu-id="ff0f6-111">群組原則</span><span class="sxs-lookup"><span data-stu-id="ff0f6-111">Group Policies</span></span>

-   <span data-ttu-id="ff0f6-112">網際網路資訊服務（IIS）</span><span class="sxs-lookup"><span data-stu-id="ff0f6-112">Internet Information Services (IIS)</span></span>

## <span data-ttu-id="ff0f6-113">APP-V 基礎結構元件</span><span class="sxs-lookup"><span data-stu-id="ff0f6-113">APP-V Infrastructure Components</span></span>


<span data-ttu-id="ff0f6-114">規劃增強的安全性 App V 環境時，您可以考慮數種不同的基礎結構模型。</span><span class="sxs-lookup"><span data-stu-id="ff0f6-114">When planning an enhanced security App-V environment, you can consider several different infrastructure models.</span></span>

<span data-ttu-id="ff0f6-115">**記事** 如需 App V 基礎結構模型的詳細資訊，請參閱下列檔：</span><span class="sxs-lookup"><span data-stu-id="ff0f6-115">**Note** For more information about App-V infrastructure models, see the following documentation:</span></span>

-   [<span data-ttu-id="ff0f6-116">App-v 規劃與部署指南</span><span class="sxs-lookup"><span data-stu-id="ff0f6-116">App-V Planning and Deployment Guide</span></span>](https://go.microsoft.com/fwlink/?LinkId=122063)

-   [<span data-ttu-id="ff0f6-117">基礎結構規劃與設計指南系列</span><span class="sxs-lookup"><span data-stu-id="ff0f6-117">Infrastructure Planning and Design Guide Series</span></span>](https://go.microsoft.com/fwlink/?LinkId=151986)

 

<span data-ttu-id="ff0f6-118">這些模型會利用部分（但不是所有）在下圖中描述的 App-v 元件。</span><span class="sxs-lookup"><span data-stu-id="ff0f6-118">These models utilize some but possibly not all of the App-V components depicted in the following illustration.</span></span>

![app-v 分支辦公室圖表](images/appvbranchoffices.gif)

<a href="" id="application-virtualization--app-v--management-server"></a><span data-ttu-id="ff0f6-120">應用程式虛擬化（App-v）管理伺服器</span><span class="sxs-lookup"><span data-stu-id="ff0f6-120">Application Virtualization (App-V) Management Server</span></span>  
<span data-ttu-id="ff0f6-121">App-v 管理伺服器會流式處理套件內容，並將快捷方式和檔案類型關聯發佈到 App-v 用戶端。</span><span class="sxs-lookup"><span data-stu-id="ff0f6-121">The App-V Management Server streams the package content and publishes the shortcuts and file-type associations to the App-V Client.</span></span> <span data-ttu-id="ff0f6-122">App-v 管理伺服器也支援 [作用中升級]、[授權管理]，以及可用於報告的資料庫。</span><span class="sxs-lookup"><span data-stu-id="ff0f6-122">The App-V Management Server also supports active upgrade, license management, and a database that can be used for reporting.</span></span>

<a href="" id="application-virtualization--app-v--streaming-server"></a><span data-ttu-id="ff0f6-123">應用程式虛擬化（App-v）流式處理伺服器</span><span class="sxs-lookup"><span data-stu-id="ff0f6-123">Application Virtualization (App-V) Streaming Server</span></span>  
<span data-ttu-id="ff0f6-124">App-v 流式處理伺服器會將用於流式處理的套件託管至應用程式中的 App-v 用戶端（例如分支辦公室），在此情況下，到 App-v 管理伺服器的連線頻寬不足以流式套件內容傳送給用戶端。</span><span class="sxs-lookup"><span data-stu-id="ff0f6-124">The App-V Streaming Server hosts the packages for streaming to App-V Clients in environments such as branch offices, where the bandwidth of the connection to the App-V Management Server is insufficient for streaming package content to clients.</span></span> <span data-ttu-id="ff0f6-125">流式處理伺服器只包含流式處理功能，並不提供 App-v 管理主控台或 App-v Management Web 服務。</span><span class="sxs-lookup"><span data-stu-id="ff0f6-125">The Streaming Server contains only streaming functionality and does not provide you with the App-V Management Console or the App-V Management Web Service.</span></span>

<a href="" id="application-virtualization--app-v--data-store"></a><span data-ttu-id="ff0f6-126">應用程式虛擬化（App-v）資料存放區</span><span class="sxs-lookup"><span data-stu-id="ff0f6-126">Application Virtualization (App-V) Data Store</span></span>  
<span data-ttu-id="ff0f6-127">SQL 資料庫中的 App-v 資料儲存區會保留與 App-v 基礎結構相關的資訊。</span><span class="sxs-lookup"><span data-stu-id="ff0f6-127">The App-V data store, in the SQL database, retains information related to the App-V infrastructure.</span></span> <span data-ttu-id="ff0f6-128">App-v 資料存放區中的資訊包含所有應用程式記錄、應用程式指派，以及管理應用程式虛擬化環境的群組。</span><span class="sxs-lookup"><span data-stu-id="ff0f6-128">The information in the App-V data store includes all application records, application assignments, and which groups manage the Application Virtualization environment.</span></span>

<a href="" id="application-virtualization--app-v--management-service"></a><span data-ttu-id="ff0f6-129">應用程式虛擬化（App-v）管理服務</span><span class="sxs-lookup"><span data-stu-id="ff0f6-129">Application Virtualization (App-V) Management Service</span></span>  
<span data-ttu-id="ff0f6-130">App-v 管理服務會將讀/寫要求傳達給應用程式虛擬化資料存放區。</span><span class="sxs-lookup"><span data-stu-id="ff0f6-130">The App-V Management Service communicates read/write requests to the Application Virtualization data store.</span></span> <span data-ttu-id="ff0f6-131">此元件可以安裝在與 App-v 管理伺服器相同的電腦上，或安裝在裝有 IIS 的個別電腦上。</span><span class="sxs-lookup"><span data-stu-id="ff0f6-131">This component can be installed on the same computer as the App-V Management Server or on a separate computer with IIS installed.</span></span>

<a href="" id="application-virtualization--app-v--management-console"></a><span data-ttu-id="ff0f6-132">應用程式虛擬化（App-v）管理主控台</span><span class="sxs-lookup"><span data-stu-id="ff0f6-132">Application Virtualization (App-V) Management Console</span></span>  
<span data-ttu-id="ff0f6-133">App-v 管理主控台是 App-v Server 管理的管理單元管理公用程式。</span><span class="sxs-lookup"><span data-stu-id="ff0f6-133">The App-V Management Console is a snap-in management utility for App-V Server administration.</span></span> <span data-ttu-id="ff0f6-134">此元件可以安裝在應用程式 V 伺服器所在的電腦上，或安裝在裝有 MMC 3.0 和的個別工作站上。已安裝 NET 2.0。</span><span class="sxs-lookup"><span data-stu-id="ff0f6-134">This component can be installed on the same computer as the App-V Server or on a separate workstation that has MMC3.0 and .NET2.0 installed.</span></span>

<a href="" id="application-virtualization--app-v--sequencer"></a><span data-ttu-id="ff0f6-135">應用程式虛擬化（App-v） Sequencer</span><span class="sxs-lookup"><span data-stu-id="ff0f6-135">Application Virtualization (App-V) Sequencer</span></span>  
<span data-ttu-id="ff0f6-136">App-v 排序器會監視並捕獲應用程式的安裝，並建立虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="ff0f6-136">The App-V Sequencer monitors and captures the installation of applications and creates virtual application packages.</span></span> <span data-ttu-id="ff0f6-137">排序器的輸出包含應用程式圖示、包含應用程式定義資訊的 OSD 檔案、套件資訊清單檔案，以及包含應用程式內容檔案的 SFT 檔案。</span><span class="sxs-lookup"><span data-stu-id="ff0f6-137">The output of the Sequencer consists of the application icon, the OSD file containing application definition information, a package manifest file, and an SFT file containing the application’s content files.</span></span> <span data-ttu-id="ff0f6-138">或者，您可以建立 Windows 安裝程式檔案來安裝套件，而不需要使用 App-v 基礎結構。</span><span class="sxs-lookup"><span data-stu-id="ff0f6-138">Optionally, a Windows Installer file can be created for installing the package without using the App-V infrastructure.</span></span>

<a href="" id="application-virtualization--app-v--client"></a><span data-ttu-id="ff0f6-139">應用程式虛擬化（App-v）用戶端</span><span class="sxs-lookup"><span data-stu-id="ff0f6-139">Application Virtualization (App-V) Client</span></span>  
<span data-ttu-id="ff0f6-140">App v 用戶端安裝在 App-v Desktop 用戶端電腦或 App-v 終端服務用戶端電腦上。</span><span class="sxs-lookup"><span data-stu-id="ff0f6-140">The App-V Client is installed on the App-V Desktop Client computer or on the App-V Terminal Services Client computer.</span></span> <span data-ttu-id="ff0f6-141">它提供虛擬應用程式套件的虛擬環境。</span><span class="sxs-lookup"><span data-stu-id="ff0f6-141">It provides the virtual environment for the virtual application packages.</span></span> <span data-ttu-id="ff0f6-142">App-v 用戶端可將套件資料流程管理到快取、虛擬應用程式發佈重新整理，以及與應用程式虛擬化伺服器互動。</span><span class="sxs-lookup"><span data-stu-id="ff0f6-142">The App-V Client manages the package streaming to the cache, virtual application publishing refresh, and interaction with the Application Virtualization Servers.</span></span>

 

 





