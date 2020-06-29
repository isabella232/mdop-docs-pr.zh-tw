---
title: 部署 MBAM 2.0 伺服器基礎結構
description: 部署 MBAM 2.0 伺服器基礎結構
author: dansimp
ms.assetid: 52e68d94-e2b4-4b06-ae55-f900ea6cc59f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 22a69fe8f6853c02a818bb026b36771cd09632f0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810748"
---
# <span data-ttu-id="321c6-103">部署 MBAM 2.0 伺服器基礎結構</span><span class="sxs-lookup"><span data-stu-id="321c6-103">Deploying the MBAM 2.0 Server Infrastructure</span></span>


<span data-ttu-id="321c6-104">您可以在生產環境中的兩個或多個伺服器上，將獨立拓朴的 Microsoft BitLocker 管理與監控（MBAM）伺服器功能安裝在不同的配置中。</span><span class="sxs-lookup"><span data-stu-id="321c6-104">Microsoft BitLocker Administration and Monitoring (MBAM) Server features for the Stand-alone topology can be installed in different configurations on two or more servers in a production environment.</span></span> <span data-ttu-id="321c6-105">根據您的可伸縮性需求而定，建議的配置是針對生產環境的兩個伺服器。</span><span class="sxs-lookup"><span data-stu-id="321c6-105">The recommended configuration is two servers for a production environment, depending on your scalability requirements.</span></span> <span data-ttu-id="321c6-106">僅在測試環境中使用單一伺服器進行 MBAM 安裝。</span><span class="sxs-lookup"><span data-stu-id="321c6-106">Use a single server for an MBAM installation only in test environments.</span></span> <span data-ttu-id="321c6-107">如需規劃 MBAM Server 功能部署的詳細資訊，請參閱[MBAM 2.0 Server 部署規劃](planning-for-mbam-20-server-deployment-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="321c6-107">For more information about planning for the MBAM Server feature deployment, see [Planning for MBAM 2.0 Server Deployment](planning-for-mbam-20-server-deployment-mbam-2.md).</span></span>

<span data-ttu-id="321c6-108">下圖顯示您可以如何設定建議的雙伺服器 MBAM 部署的範例。</span><span class="sxs-lookup"><span data-stu-id="321c6-108">The following diagram shows an example of how you can configure the recommended two-server MBAM deployment.</span></span> <span data-ttu-id="321c6-109">此設定在生產環境中最多可支援 200000 MBAM 用戶端。</span><span class="sxs-lookup"><span data-stu-id="321c6-109">This configuration supports up to 200,000 MBAM clients in a production environment.</span></span> <span data-ttu-id="321c6-110">體系結構中的伺服器功能和資料庫會在下一節中說明，並列在電腦或伺服器（我們建議您安裝它們）底下。</span><span class="sxs-lookup"><span data-stu-id="321c6-110">The server features and databases in the architecture image are described in the following section and are listed under the computer or server where we recommend that you install them.</span></span>

![mbam 2 2-伺服器部署拓朴](images/mbam2-3-servers.gif)

## <span data-ttu-id="321c6-112">管理和監控伺服器</span><span class="sxs-lookup"><span data-stu-id="321c6-112">Administration and Monitoring Server</span></span>


<span data-ttu-id="321c6-113">此伺服器上已安裝下列功能：</span><span class="sxs-lookup"><span data-stu-id="321c6-113">The following features are installed on this server:</span></span>

-   <span data-ttu-id="321c6-114">**管理和監控伺服器**。</span><span class="sxs-lookup"><span data-stu-id="321c6-114">**Administration and Monitoring Server**.</span></span> <span data-ttu-id="321c6-115">系統會在 Windows Server 上安裝 [管理和監控伺服器] 功能，並由技術支援網站和監視 web 服務組成。</span><span class="sxs-lookup"><span data-stu-id="321c6-115">The Administration and Monitoring Server feature is installed on a Windows server and consists of the Help Desk website and the monitoring web services.</span></span>

-   <span data-ttu-id="321c6-116">**自助入口網站**。</span><span class="sxs-lookup"><span data-stu-id="321c6-116">**Self-Service Portal**.</span></span> <span data-ttu-id="321c6-117">自助入口網站已安裝在 Windows 伺服器上。</span><span class="sxs-lookup"><span data-stu-id="321c6-117">The Self-Service Portal is installed on a Windows server.</span></span> <span data-ttu-id="321c6-118">自助式入口網站可讓用戶端電腦上的使用者能夠獨立地登入網站，讓他們可以取得修復金鑰來復原鎖定的 BitLocker 卷。</span><span class="sxs-lookup"><span data-stu-id="321c6-118">The Self-Service Portal enables end users on client computers to independently log on to a website, where they can obtain a recovery key to recover a locked BitLocker volume.</span></span>

## <span data-ttu-id="321c6-119">資料庫伺服器</span><span class="sxs-lookup"><span data-stu-id="321c6-119">Database Server</span></span>


<span data-ttu-id="321c6-120">此伺服器上已安裝下列功能：</span><span class="sxs-lookup"><span data-stu-id="321c6-120">The following features are installed on this server:</span></span>

-   <span data-ttu-id="321c6-121">[**恢復資料庫**]。</span><span class="sxs-lookup"><span data-stu-id="321c6-121">**Recovery Database**.</span></span> <span data-ttu-id="321c6-122">已在 Windows server 和支援的 Microsoft SQLServer 實例上安裝復原資料庫。</span><span class="sxs-lookup"><span data-stu-id="321c6-122">The Recovery Database is installed on a Windows server and a supported instance of Microsoft SQLServer.</span></span> <span data-ttu-id="321c6-123">此資料庫儲存從 MBAM 用戶端電腦收集的復原資料。</span><span class="sxs-lookup"><span data-stu-id="321c6-123">This database stores recovery data that is collected from MBAM client computers.</span></span>

-   <span data-ttu-id="321c6-124">**合規性和審核資料庫**。</span><span class="sxs-lookup"><span data-stu-id="321c6-124">**Compliance and Audit Database**.</span></span> <span data-ttu-id="321c6-125">合規性與審計資料庫是安裝在 Windows server 和支援的 SQLServer 實例上。</span><span class="sxs-lookup"><span data-stu-id="321c6-125">The Compliance and Audit Database is installed on a Windows server and a supported instance of SQLServer.</span></span> <span data-ttu-id="321c6-126">此資料庫儲存 MBAM 用戶端電腦的合規性資料。</span><span class="sxs-lookup"><span data-stu-id="321c6-126">This database stores compliance data for MBAM client computers.</span></span> <span data-ttu-id="321c6-127">此資料主要用於 SQL Server Reporting Services （SSRS）主機的報表。</span><span class="sxs-lookup"><span data-stu-id="321c6-127">This data is used primarily for reports that SQL Server Reporting Services (SSRS) hosts.</span></span>

-   <span data-ttu-id="321c6-128">**合規性和審核報告**。</span><span class="sxs-lookup"><span data-stu-id="321c6-128">**Compliance and Audit Reports**.</span></span> <span data-ttu-id="321c6-129">合規性和審核報告會安裝在 Windows server 上，以及已安裝 SQL Server Reporting Services （SSRS）功能的 SQLServer 實例支援。</span><span class="sxs-lookup"><span data-stu-id="321c6-129">The Compliance and Audit Reports are installed on a Windows server and a supported instance of SQLServer that has the SQL Server Reporting Services (SSRS) feature installed.</span></span> <span data-ttu-id="321c6-130">這些報表提供 MBAM 報表，您可以從技術支援網站或從 SSRS 伺服器直接存取。</span><span class="sxs-lookup"><span data-stu-id="321c6-130">These reports provide MBAM reports that you can access from the Help Desk website or directly from the SSRS server.</span></span>

## <span data-ttu-id="321c6-131">管理工作站</span><span class="sxs-lookup"><span data-stu-id="321c6-131">Management Workstation</span></span>


<span data-ttu-id="321c6-132">下列功能已安裝在管理工作站（可以是 Windows server 或用戶端電腦）上。</span><span class="sxs-lookup"><span data-stu-id="321c6-132">The following feature is installed on the Management Workstation, which can be a Windows server or a client computer.</span></span>

-   <span data-ttu-id="321c6-133">**原則範本**。</span><span class="sxs-lookup"><span data-stu-id="321c6-133">**Policy Template**.</span></span> <span data-ttu-id="321c6-134">原則範本由定義 BitLocker 磁片磁碟機加密之 MBAM 實現設定的群組原則所組成。</span><span class="sxs-lookup"><span data-stu-id="321c6-134">The Policy Template consists of Group Policies that define MBAM implementation settings for BitLocker drive encryption.</span></span> <span data-ttu-id="321c6-135">您可以在任何伺服器或工作站上安裝此原則範本，但通常會將它安裝在管理工作站上（這是受支援的 Windows server 或用戶端電腦）。</span><span class="sxs-lookup"><span data-stu-id="321c6-135">You can install the Policy template on any server or workstation, but it is commonly installed on a management workstation, which is a supported Windows server or client computer.</span></span> <span data-ttu-id="321c6-136">工作站不一定是專用電腦。</span><span class="sxs-lookup"><span data-stu-id="321c6-136">The workstation does not have to be a dedicated computer.</span></span>

## <a href="" id="---------mbam-client"></a> <span data-ttu-id="321c6-137">MBAM 用戶端</span><span class="sxs-lookup"><span data-stu-id="321c6-137">MBAM Client</span></span>


<span data-ttu-id="321c6-138">MBAM 用戶端已安裝在 Windows 電腦上，且具有下列特性：</span><span class="sxs-lookup"><span data-stu-id="321c6-138">The MBAM Client is installed on a Windows computer and has the following characteristics:</span></span>

-   <span data-ttu-id="321c6-139">使用群組原則，強制企業中用戶端電腦的 BitLocker 磁碟機加密。</span><span class="sxs-lookup"><span data-stu-id="321c6-139">Uses Group Policy to enforce the BitLocker drive encryption of client computers in the enterprise.</span></span>

-   <span data-ttu-id="321c6-140">收集三個 BitLocker 資料磁片磁碟機類型的復原金鑰：操作系統磁碟機、固定資料磁碟機，以及可移動資料（USB）硬碟。</span><span class="sxs-lookup"><span data-stu-id="321c6-140">Collects the recovery key for the three BitLocker data drive types: operating system drives, fixed data drives, and removable data (USB) drives.</span></span>

-   <span data-ttu-id="321c6-141">收集電腦的規範資料，並將資料傳遞到報告系統。</span><span class="sxs-lookup"><span data-stu-id="321c6-141">Collects compliance data for the computer and passes the data to the reporting system.</span></span>

## <span data-ttu-id="321c6-142">部署 MBAM 2.0 Server 功能的其他資源</span><span class="sxs-lookup"><span data-stu-id="321c6-142">Other Resources for Deploying MBAM 2.0 Server Features</span></span>


[<span data-ttu-id="321c6-143">部署 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="321c6-143">Deploying MBAM 2.0</span></span>](deploying-mbam-20-mbam-2.md)

 

 





