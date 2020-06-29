---
title: MBAM 2.0 的概要架構
description: MBAM 2.0 的概要架構
author: dansimp
ms.assetid: 7f73dd3a-0b1f-4af6-a2f0-d0c5bc5d183a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ddc061a1aec5141548c2d2141be38f8501d2244d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810713"
---
# <span data-ttu-id="158b0-103">MBAM 2.0 的概要架構</span><span class="sxs-lookup"><span data-stu-id="158b0-103">High-Level Architecture for MBAM 2.0</span></span>


<span data-ttu-id="158b0-104">Microsoft BitLocker 管理和監控（MBAM）是一種用戶端/伺服器方案，可協助您簡化 BitLocker 的置備及部署、改善 BitLocker 的相容性與報告，並減少支援成本。</span><span class="sxs-lookup"><span data-stu-id="158b0-104">Microsoft BitLocker Administration and Monitoring (MBAM) is a client/server solution that can help you simplify BitLocker provisioning and deployment, improve compliance and reporting on BitLocker, and reduce support costs.</span></span> <span data-ttu-id="158b0-105">Microsoft BitLocker 管理和監控包括本主題中所述的功能。</span><span class="sxs-lookup"><span data-stu-id="158b0-105">Microsoft BitLocker Administration and Monitoring includes the features that are described in this topic.</span></span>

<span data-ttu-id="158b0-106">Microsoft BitLocker 管理和監視可以在獨立拓撲中部署，或是在與 Microsoft System Center Configuration Manager 2007 或 MicrosoftSystemCenter2012 ConfigurationManager 整合的拓撲中部署。</span><span class="sxs-lookup"><span data-stu-id="158b0-106">Microsoft BitLocker Administration and Monitoring can be deployed in the Stand-alone topology, or in a topology that is integrated with Microsoft System Center Configuration Manager 2007 or MicrosoftSystemCenter2012 ConfigurationManager.</span></span> <span data-ttu-id="158b0-107">本主題描述獨立拓朴的架構。</span><span class="sxs-lookup"><span data-stu-id="158b0-107">This topic describes the architecture for the Stand-alone topology.</span></span> <span data-ttu-id="158b0-108">如需在整合式 Configuration Manager 拓撲結構中進行部署的相關資訊，請參閱[與 Configuration manager 一起使用 MBAM](using-mbam-with-configuration-manager.md)。</span><span class="sxs-lookup"><span data-stu-id="158b0-108">For information about deploying in the integrated Configuration Manager topology, see [Using MBAM with Configuration Manager](using-mbam-with-configuration-manager.md).</span></span>

<span data-ttu-id="158b0-109">下圖顯示生產環境的 MBAM 建議架構，其中包含兩個伺服器與管理工作站。</span><span class="sxs-lookup"><span data-stu-id="158b0-109">The following diagram shows the MBAM recommended architecture for a production environment, which consists of two servers and a management workstation.</span></span> <span data-ttu-id="158b0-110">這個架構最多可支援 200000 MBAM 用戶端。</span><span class="sxs-lookup"><span data-stu-id="158b0-110">This architecture supports up to 200,000 MBAM clients.</span></span> <span data-ttu-id="158b0-111">體系結構中的伺服器功能和資料庫會在下一節中說明，並列在電腦或伺服器（我們建議您安裝它們）底下。</span><span class="sxs-lookup"><span data-stu-id="158b0-111">The server features and databases in the architecture image are described in the following section and are listed under the computer or server where we recommend that you install them.</span></span>

<span data-ttu-id="158b0-112">**記事** 單伺服器架構只能在測試環境中使用。</span><span class="sxs-lookup"><span data-stu-id="158b0-112">**Note** A single-server architecture should be used only in test environments.</span></span>

 

![mbam 2 2-伺服器部署拓朴](images/mbam2-3-servers.gif)

## <span data-ttu-id="158b0-114">管理和監控伺服器</span><span class="sxs-lookup"><span data-stu-id="158b0-114">Administration and Monitoring Server</span></span>


<span data-ttu-id="158b0-115">此伺服器上已安裝下列功能：</span><span class="sxs-lookup"><span data-stu-id="158b0-115">The following features are installed on this server:</span></span>

-   <span data-ttu-id="158b0-116">**管理和監控伺服器**。</span><span class="sxs-lookup"><span data-stu-id="158b0-116">**Administration and Monitoring Server**.</span></span> <span data-ttu-id="158b0-117">系統會在 Windows Server 上安裝 [管理和監控伺服器] 功能，並包含 [管理與監控] 網站，其中包含報表與 [技術支援中心] 入口網站，以及監視 web 服務。</span><span class="sxs-lookup"><span data-stu-id="158b0-117">The Administration and Monitoring Server feature is installed on a Windows server and consists of the Administration and Monitoring website, which includes the reports and the Help Desk Portal, and the monitoring web services.</span></span>

-   <span data-ttu-id="158b0-118">**自助入口網站**。</span><span class="sxs-lookup"><span data-stu-id="158b0-118">**Self-Service Portal**.</span></span> <span data-ttu-id="158b0-119">自助入口網站已安裝在 Windows 伺服器上。</span><span class="sxs-lookup"><span data-stu-id="158b0-119">The Self-Service Portal is installed on a Windows server.</span></span> <span data-ttu-id="158b0-120">自助式入口網站可讓用戶端電腦上的使用者能夠獨立地登入網站，讓他們可以取得修復金鑰來復原鎖定的 BitLocker 卷。</span><span class="sxs-lookup"><span data-stu-id="158b0-120">The Self-Service Portal enables end users on client computers to independently log on to a website, where they can obtain a recovery key to recover a locked BitLocker volume.</span></span>

## <span data-ttu-id="158b0-121">資料庫伺服器</span><span class="sxs-lookup"><span data-stu-id="158b0-121">Database Server</span></span>


<span data-ttu-id="158b0-122">此伺服器上已安裝下列功能：</span><span class="sxs-lookup"><span data-stu-id="158b0-122">The following features are installed on this server:</span></span>

-   <span data-ttu-id="158b0-123">[**恢復資料庫**]。</span><span class="sxs-lookup"><span data-stu-id="158b0-123">**Recovery Database**.</span></span> <span data-ttu-id="158b0-124">已在 Windows server 和支援的 Microsoft SQLServer 實例上安裝復原資料庫。</span><span class="sxs-lookup"><span data-stu-id="158b0-124">The Recovery Database is installed on a Windows server and a supported instance of Microsoft SQLServer.</span></span> <span data-ttu-id="158b0-125">此資料庫儲存從 MBAM 用戶端電腦收集的復原資料。</span><span class="sxs-lookup"><span data-stu-id="158b0-125">This database stores recovery data that is collected from MBAM client computers.</span></span>

-   <span data-ttu-id="158b0-126">**合規性和審核資料庫**。</span><span class="sxs-lookup"><span data-stu-id="158b0-126">**Compliance and Audit Database**.</span></span> <span data-ttu-id="158b0-127">合規性與審計資料庫是安裝在 Windows server 和支援的 SQLServer 實例上。</span><span class="sxs-lookup"><span data-stu-id="158b0-127">The Compliance and Audit Database is installed on a Windows server and a supported instance of SQLServer.</span></span> <span data-ttu-id="158b0-128">此資料庫儲存 MBAM 用戶端電腦的合規性資料。</span><span class="sxs-lookup"><span data-stu-id="158b0-128">This database stores compliance data for MBAM client computers.</span></span> <span data-ttu-id="158b0-129">此資料主要用於 SQL Server Reporting Services （SSRS）主機的報表。</span><span class="sxs-lookup"><span data-stu-id="158b0-129">This data is used primarily for reports that SQL Server Reporting Services (SSRS) hosts.</span></span>

-   <span data-ttu-id="158b0-130">**合規性和審核報告**。</span><span class="sxs-lookup"><span data-stu-id="158b0-130">**Compliance and Audit Reports**.</span></span> <span data-ttu-id="158b0-131">合規性和審核報告會安裝在 Windows server 上，以及已安裝 SQL Server Reporting Services （SSRS）功能的 SQLServer 實例支援。</span><span class="sxs-lookup"><span data-stu-id="158b0-131">The Compliance and Audit Reports are installed on a Windows server and a supported instance of SQLServer that has the SQL Server Reporting Services (SSRS) feature installed.</span></span> <span data-ttu-id="158b0-132">這些報告提供 MBAM 報告，您可以從 [管理] 和 [監視] 網站或直接從 SSRS 伺服器存取。</span><span class="sxs-lookup"><span data-stu-id="158b0-132">These reports provide MBAM reports that you can access from the Administration and Monitoring website or directly from the SSRS server.</span></span>

## <span data-ttu-id="158b0-133">管理工作站</span><span class="sxs-lookup"><span data-stu-id="158b0-133">Management Workstation</span></span>


<span data-ttu-id="158b0-134">下列功能已安裝在管理工作站（可以是 Windows server 或用戶端電腦）上。</span><span class="sxs-lookup"><span data-stu-id="158b0-134">The following feature is installed on the Management workstation, which can be a Windows server or a client computer.</span></span>

-   <span data-ttu-id="158b0-135">**原則範本**。</span><span class="sxs-lookup"><span data-stu-id="158b0-135">**Policy Template**.</span></span> <span data-ttu-id="158b0-136">原則範本是由定義 BitLocker 磁片磁碟機加密之 MBAM 實現設定的群組原則設定所組成。</span><span class="sxs-lookup"><span data-stu-id="158b0-136">The Policy Template consists of Group Policy settings that define MBAM implementation settings for BitLocker drive encryption.</span></span> <span data-ttu-id="158b0-137">您可以在任何伺服器或工作站上安裝此原則範本，但通常會將它安裝在管理工作站上（這是受支援的 Windows server 或用戶端電腦）。</span><span class="sxs-lookup"><span data-stu-id="158b0-137">You can install the Policy template on any server or workstation, but it is commonly installed on a management workstation, which is a supported Windows server or client computer.</span></span> <span data-ttu-id="158b0-138">工作站不一定是專用電腦。</span><span class="sxs-lookup"><span data-stu-id="158b0-138">The workstation does not have to be a dedicated computer.</span></span>

## <a href="" id="---------mbam-client"></a> <span data-ttu-id="158b0-139">MBAM 用戶端</span><span class="sxs-lookup"><span data-stu-id="158b0-139">MBAM Client</span></span>


<span data-ttu-id="158b0-140">MBAM 用戶端已安裝在 Windows 電腦上，且具有下列特性：</span><span class="sxs-lookup"><span data-stu-id="158b0-140">The MBAM Client is installed on a Windows computer and has the following characteristics:</span></span>

-   <span data-ttu-id="158b0-141">使用群組原則，強制企業中用戶端電腦的 BitLocker 磁碟機加密。</span><span class="sxs-lookup"><span data-stu-id="158b0-141">Uses Group Policy to enforce the BitLocker drive encryption of client computers in the enterprise.</span></span>

-   <span data-ttu-id="158b0-142">收集三個 BitLocker 資料磁片磁碟機類型的復原金鑰：操作系統磁碟機、固定資料磁碟機，以及可移動資料（USB）硬碟。</span><span class="sxs-lookup"><span data-stu-id="158b0-142">Collects the recovery key for the three BitLocker data drive types: operating system drives, fixed data drives, and removable data (USB) drives.</span></span>

-   <span data-ttu-id="158b0-143">收集電腦的規範資料，並將資料傳遞到報告系統。</span><span class="sxs-lookup"><span data-stu-id="158b0-143">Collects compliance data for the computer and passes the data to the reporting system.</span></span>

## <span data-ttu-id="158b0-144">相關主題</span><span class="sxs-lookup"><span data-stu-id="158b0-144">Related topics</span></span>


[<span data-ttu-id="158b0-145">開始使用 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="158b0-145">Getting Started with MBAM 2.0</span></span>](getting-started-with-mbam-20-mbam-2.md)

 

 





