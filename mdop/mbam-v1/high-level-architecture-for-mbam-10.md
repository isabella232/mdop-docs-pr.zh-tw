---
title: MBAM 1.0 的高階架構
description: MBAM 1.0 的高階架構
author: dansimp
ms.assetid: b1349196-88ed-4d6c-8a1d-998f18127b6b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: de3529fdb565859fcc212d1a9a614ac4ef4b183e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811036"
---
# <span data-ttu-id="22763-103">MBAM 1.0 的高階架構</span><span class="sxs-lookup"><span data-stu-id="22763-103">High Level Architecture for MBAM 1.0</span></span>


<span data-ttu-id="22763-104">Microsoft BitLocker 管理和監控（MBAM）是一種用戶端/伺服器資料加密解決方案，可協助您簡化 BitLocker 的預配及部署、改善 BitLocker 合規性與報告，並減少支援成本。</span><span class="sxs-lookup"><span data-stu-id="22763-104">Microsoft BitLocker Administration and Monitoring (MBAM) is a client/server data encryption solution that can help you simplify BitLocker provisioning and deployment, improve BitLocker compliance and reporting, and reduce support costs.</span></span> <span data-ttu-id="22763-105">MBAM 包含本主題中所述的功能。</span><span class="sxs-lookup"><span data-stu-id="22763-105">MBAM includes the features that are described in this topic.</span></span>

<span data-ttu-id="22763-106">此外，還有一個影片，提供 MBAM 架構和 MBAM 設定的概覽。</span><span class="sxs-lookup"><span data-stu-id="22763-106">Additionally, there is a video that provides an overview of the MBAM architecture and MBAM Setup.</span></span> <span data-ttu-id="22763-107">如需詳細資訊，請參閱[MBAM 部署與架構概述](https://go.microsoft.com/fwlink/p/?LinkId=258392)。</span><span class="sxs-lookup"><span data-stu-id="22763-107">For more information, see [MBAM Deployment and Architecture Overview](https://go.microsoft.com/fwlink/p/?LinkId=258392).</span></span>

## <span data-ttu-id="22763-108">架構概述</span><span class="sxs-lookup"><span data-stu-id="22763-108">Architecture Overview</span></span>


<span data-ttu-id="22763-109">下圖顯示 MBAM 結構。</span><span class="sxs-lookup"><span data-stu-id="22763-109">The following diagram displays the MBAM architecture.</span></span> <span data-ttu-id="22763-110">會顯示單一伺服器 MBAM 部署拓朴，以介紹 MBAM 的功能。</span><span class="sxs-lookup"><span data-stu-id="22763-110">The single-server MBAM deployment topology is shown to introduce the MBAM features.</span></span> <span data-ttu-id="22763-111">不過，建議僅針對實驗室環境使用此 MBAM 部署拓撲。</span><span class="sxs-lookup"><span data-stu-id="22763-111">However, this MBAM deployment topology is recommended only for lab environments.</span></span>

<span data-ttu-id="22763-112">**記事** 針對生產部署，建議至少使用三台電腦 MBAM 部署拓撲。</span><span class="sxs-lookup"><span data-stu-id="22763-112">**Note** At least a three-computer MBAM deployment topology is recommended for a production deployment.</span></span> <span data-ttu-id="22763-113">如需 MBAM 部署拓撲的詳細資訊，請參閱[部署 MBAM 1.0 伺服器基礎結構](deploying-the-mbam-10-server-infrastructure.md)。</span><span class="sxs-lookup"><span data-stu-id="22763-113">For more information about MBAM deployment topologies, see [Deploying the MBAM 1.0 Server Infrastructure](deploying-the-mbam-10-server-infrastructure.md).</span></span>

 

![mbam 單一伺服器部署拓朴](images/mbam-1-server.jpg)

1.  <span data-ttu-id="22763-115">**管理和監控伺服器**。</span><span class="sxs-lookup"><span data-stu-id="22763-115">**Administration and Monitoring Server**.</span></span> <span data-ttu-id="22763-116">MBAM 管理和監視伺服器已安裝在 Windows 伺服器上，且託管 MBAM 管理和管理網站及監視 web 服務。</span><span class="sxs-lookup"><span data-stu-id="22763-116">The MBAM Administration and Monitoring Server is installed on a Windows server and hosts the MBAM Administration and Management website and the monitoring web services.</span></span> <span data-ttu-id="22763-117">MBAM 管理和管理網站是用來判斷企業合規性狀態、審核活動、管理硬體功能，以及存取復原資料（例如 BitLocker 復原金鑰）。</span><span class="sxs-lookup"><span data-stu-id="22763-117">The MBAM Administration and Management website is used to determine enterprise compliance status, to audit activity, to manage hardware capability, and to access recovery data, such as the BitLocker recovery keys.</span></span> <span data-ttu-id="22763-118">管理和監視伺服器會連接到下列資料庫和服務：</span><span class="sxs-lookup"><span data-stu-id="22763-118">The Administration and Monitoring Server connects to the following databases and services:</span></span>

    -   <span data-ttu-id="22763-119">[復原] 和 [硬體資料庫]。</span><span class="sxs-lookup"><span data-stu-id="22763-119">Recovery and Hardware Database.</span></span> <span data-ttu-id="22763-120">在 Windows 版伺服器和支援的 SQLServer 實例上，會安裝恢復和硬體資料庫。</span><span class="sxs-lookup"><span data-stu-id="22763-120">The Recovery and Hardware database is installed on a Windows-based server and supported SQLServer instance.</span></span> <span data-ttu-id="22763-121">此資料庫儲存從 MBAM 用戶端電腦收集的復原資料和硬體資訊。</span><span class="sxs-lookup"><span data-stu-id="22763-121">This database stores recovery data and hardware information that is collected from MBAM client computers.</span></span>

    -   <span data-ttu-id="22763-122">合規性和審核資料庫。</span><span class="sxs-lookup"><span data-stu-id="22763-122">Compliance and Audit Database.</span></span> <span data-ttu-id="22763-123">合規性與審計資料庫已安裝在 Windows server 和支援的 SQLServer 實例上。</span><span class="sxs-lookup"><span data-stu-id="22763-123">The Compliance and Audit Database is installed on a Windows server and supported SQLServer instance.</span></span> <span data-ttu-id="22763-124">此資料庫儲存 MBAM 用戶端電腦的合規性資料。</span><span class="sxs-lookup"><span data-stu-id="22763-124">This database stores compliance data for MBAM client computers.</span></span> <span data-ttu-id="22763-125">此資料主要用於由 SQL Server Reporting Services （SSRS）託管的報表。</span><span class="sxs-lookup"><span data-stu-id="22763-125">This data is used primarily for reports that are hosted by SQL Server Reporting Services (SSRS).</span></span>

    -   <span data-ttu-id="22763-126">合規性和審核報告。</span><span class="sxs-lookup"><span data-stu-id="22763-126">Compliance and Audit Reports.</span></span> <span data-ttu-id="22763-127">合規性和審核報告會安裝在 Windows 版伺服器上，且已安裝 SSRS 功能的支援 SQLServer 實例。</span><span class="sxs-lookup"><span data-stu-id="22763-127">The Compliance and Audit Reports are installed on a Windows-based server and supported SQLServer instance that has the SSRS feature installed.</span></span> <span data-ttu-id="22763-128">這些報告提供 Microsoft BitLocker 管理和監控報告。</span><span class="sxs-lookup"><span data-stu-id="22763-128">These reports provide Microsoft BitLocker Administration and Monitoring reports.</span></span> <span data-ttu-id="22763-129">您可以從 MBAM 管理和管理網站或直接從 SSRS 伺服器存取這些報告。</span><span class="sxs-lookup"><span data-stu-id="22763-129">These reports can be accessed from the MBAM Administration and Management website or directly from the SSRS Server.</span></span>

2.  <span data-ttu-id="22763-130">**MBAM 用戶端**]。</span><span class="sxs-lookup"><span data-stu-id="22763-130">**MBAM Client**.</span></span> <span data-ttu-id="22763-131">Microsoft BitLocker 管理和監視用戶端會執行下列工作：</span><span class="sxs-lookup"><span data-stu-id="22763-131">The Microsoft BitLocker Administration and Monitoring Client performs the following tasks:</span></span>

    -   <span data-ttu-id="22763-132">使用群組原則，在企業中強制執行用戶端電腦的 BitLocker 加密。</span><span class="sxs-lookup"><span data-stu-id="22763-132">Uses Group Policy to enforce the BitLocker encryption of client computers in the enterprise.</span></span>

    -   <span data-ttu-id="22763-133">收集三個 BitLocker 資料磁片磁碟機類型的復原金鑰：操作系統磁碟機、固定資料磁碟機，以及可移動資料（USB）硬碟。</span><span class="sxs-lookup"><span data-stu-id="22763-133">Collects the recovery key for the three BitLocker data drive types: operating system drives, fixed data drives, and removable data (USB) drives.</span></span>

    -   <span data-ttu-id="22763-134">收集用戶端電腦的恢復資訊和硬體資訊。</span><span class="sxs-lookup"><span data-stu-id="22763-134">Collects recovery information and hardware information about the client computers.</span></span>

    -   <span data-ttu-id="22763-135">收集電腦的規範資料，並將資料傳遞到報告系統。</span><span class="sxs-lookup"><span data-stu-id="22763-135">Collects compliance data for the computer and passes the data to the reporting system.</span></span>

3.  <span data-ttu-id="22763-136">**原則範本**。</span><span class="sxs-lookup"><span data-stu-id="22763-136">**Policy Template**.</span></span> <span data-ttu-id="22763-137">MBAM 群組原則範本是安裝在支援的 Windows 版伺服器或用戶端電腦上。</span><span class="sxs-lookup"><span data-stu-id="22763-137">The MBAM Group Policy template is installed on a supported Windows-based server or client computer.</span></span> <span data-ttu-id="22763-138">這個範本是用來指定 BitLocker 磁片磁碟機加密的 MBAM 實現設定。</span><span class="sxs-lookup"><span data-stu-id="22763-138">This template is used to specify the MBAM implementation settings for BitLocker drive encryption.</span></span>

## <span data-ttu-id="22763-139">相關主題</span><span class="sxs-lookup"><span data-stu-id="22763-139">Related topics</span></span>


[<span data-ttu-id="22763-140">開始使用 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="22763-140">Getting Started with MBAM 1.0</span></span>](getting-started-with-mbam-10.md)

 

 





