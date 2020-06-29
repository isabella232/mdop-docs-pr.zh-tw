---
title: MBAM 2.5 搭配獨立拓撲的概要架構
description: MBAM 2.5 搭配獨立拓撲的概要架構
author: dansimp
ms.assetid: 35f8c5f6-8be3-443d-baf0-56d68b08f3bc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 75e878e24b4675f2f2f574791d0f06ecadd0196d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811828"
---
# <span data-ttu-id="325f7-103">MBAM 2.5 搭配獨立拓撲的概要架構</span><span class="sxs-lookup"><span data-stu-id="325f7-103">High-Level Architecture of MBAM 2.5 with Stand-alone Topology</span></span>


<span data-ttu-id="325f7-104">本主題描述使用 Configuration Manager 獨立拓朴部署 Microsoft BitLocker 管理和監控（MBAM）的建議架構。</span><span class="sxs-lookup"><span data-stu-id="325f7-104">This topic describes the recommended architecture for deploying Microsoft BitLocker Administration and Monitoring (MBAM) with the Configuration Manager Stand-alone topology.</span></span> <span data-ttu-id="325f7-105">在這個拓朴中，MBAM 是作為獨立產品進行部署。</span><span class="sxs-lookup"><span data-stu-id="325f7-105">In this topology, MBAM is deployed as a stand-alone product.</span></span> <span data-ttu-id="325f7-106">您也可以使用 Configuration Manager 整合拓朴來部署 MBAM，並將 MBAM 與 Configuration Manager 整合在一起。</span><span class="sxs-lookup"><span data-stu-id="325f7-106">You can alternatively deploy MBAM with the Configuration Manager Integration topology, which integrates MBAM with Configuration Manager.</span></span> <span data-ttu-id="325f7-107">如需詳細資訊，請參閱[含 Configuration Manager 整合拓朴的 MBAM 2.5 高層架構](high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md)。</span><span class="sxs-lookup"><span data-stu-id="325f7-107">For more information, see [High-Level Architecture of MBAM 2.5 with Configuration Manager Integration Topology](high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md).</span></span>

<span data-ttu-id="325f7-108">如需本主題中所述軟體支援版本的清單，請參閱[MBAM 2.5 支援](mbam-25-supported-configurations.md)的設定。</span><span class="sxs-lookup"><span data-stu-id="325f7-108">For a list of the supported versions of the software mentioned in this topic, see [MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md).</span></span>

<span data-ttu-id="325f7-109">**記事** 我們建議您只在測試環境中使用單一伺服器結構。</span><span class="sxs-lookup"><span data-stu-id="325f7-109">**Note** We recommend you use a single-server architecture in test environments only.</span></span>

 

## <span data-ttu-id="325f7-110">建議的伺服器數和支援的用戶端數量</span><span class="sxs-lookup"><span data-stu-id="325f7-110">Recommended number of servers and supported number of clients</span></span>


<span data-ttu-id="325f7-111">在生產環境中，建議的伺服器數量及支援的用戶端數量如下：</span><span class="sxs-lookup"><span data-stu-id="325f7-111">The recommended number of servers and supported number of clients in a production environment is as follows:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="325f7-112">生產環境中的建議架構</span><span class="sxs-lookup"><span data-stu-id="325f7-112">Recommended architecture in a production environment</span></span></th>
<th align="left"><span data-ttu-id="325f7-113">詳細資料</span><span class="sxs-lookup"><span data-stu-id="325f7-113">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="325f7-114">伺服器和其他電腦的數目</span><span class="sxs-lookup"><span data-stu-id="325f7-114">Number of servers and other computers</span></span></p></td>
<td align="left"><p><span data-ttu-id="325f7-115">兩個伺服器</span><span class="sxs-lookup"><span data-stu-id="325f7-115">Two servers</span></span></p>
<p><span data-ttu-id="325f7-116">一個工作站</span><span class="sxs-lookup"><span data-stu-id="325f7-116">One workstation</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="325f7-117">支援的用戶端電腦數目</span><span class="sxs-lookup"><span data-stu-id="325f7-117">Number of client computers supported</span></span></p></td>
<td align="left"><p><span data-ttu-id="325f7-118">500000</span><span class="sxs-lookup"><span data-stu-id="325f7-118">500,000</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="325f7-119">使用獨立拓朴的建議 MBAM 高層次架構</span><span class="sxs-lookup"><span data-stu-id="325f7-119">Recommended MBAM high-level architecture with the Stand-alone topology</span></span>


<span data-ttu-id="325f7-120">下列圖表和表格描述了建議的高層次、雙伺服器架構，以供獨立拓朴 MBAM 使用。</span><span class="sxs-lookup"><span data-stu-id="325f7-120">The following diagram and table describe the recommended high-level, two-server architecture for MBAM with the Stand-alone topology.</span></span> <span data-ttu-id="325f7-121">MBAM 多林部署需要單向或雙向信任。</span><span class="sxs-lookup"><span data-stu-id="325f7-121">MBAM multi-forest deployments require a one-way or two-way trust.</span></span> <span data-ttu-id="325f7-122">單向信任要求伺服器網域信任用戶端網域。</span><span class="sxs-lookup"><span data-stu-id="325f7-122">One-way trusts require that the server domain trusts the client domain.</span></span>

![mbam2](images/mbam2-5-2servers.png)

<span data-ttu-id="325f7-124">在此伺服器上設定的伺服器功能說明資料庫伺服器</span><span class="sxs-lookup"><span data-stu-id="325f7-124">Server Features to configure on this server Description Database server</span></span>

<span data-ttu-id="325f7-125">合規性和審核資料庫</span><span class="sxs-lookup"><span data-stu-id="325f7-125">Compliance and Audit Database</span></span>

<span data-ttu-id="325f7-126">此功能已在執行 Windows Server 和支援的 SQL Server 實例的伺服器上設定。</span><span class="sxs-lookup"><span data-stu-id="325f7-126">This feature is configured on a server running Windows Server and supported SQL Server instance.</span></span>

<span data-ttu-id="325f7-127">**合規性和審核資料庫**會儲存規範資料，主要用於 SQL Server Reporting Services 主機的報表。</span><span class="sxs-lookup"><span data-stu-id="325f7-127">The **Compliance and Audit Database** stores compliance data, which is used primarily for reports that SQL Server Reporting Services hosts.</span></span>

<span data-ttu-id="325f7-128">復原資料庫</span><span class="sxs-lookup"><span data-stu-id="325f7-128">Recovery Database</span></span>

<span data-ttu-id="325f7-129">此功能已在執行 Windows Server 和支援的 SQL Server 實例的伺服器上設定。</span><span class="sxs-lookup"><span data-stu-id="325f7-129">This feature is configured on a server running Windows Server and supported SQL Server instance.</span></span>

<span data-ttu-id="325f7-130">復原**資料庫**會儲存從 MBAM 用戶端電腦收集的復原資料。</span><span class="sxs-lookup"><span data-stu-id="325f7-130">The **Recovery Database** stores recovery data that is collected from MBAM client computers.</span></span>

<span data-ttu-id="325f7-131">報告</span><span class="sxs-lookup"><span data-stu-id="325f7-131">Reports</span></span>

<span data-ttu-id="325f7-132">此功能已在執行 Windows Server 和支援的 SQL Server 實例的伺服器上設定。</span><span class="sxs-lookup"><span data-stu-id="325f7-132">This feature is configured on a server running Windows Server and supported SQL Server instance.</span></span>

<span data-ttu-id="325f7-133">**報告**會提供企業中用戶端電腦的復原審核及合規性狀態資料。</span><span class="sxs-lookup"><span data-stu-id="325f7-133">The **Reports** provide recovery audit and compliance status data about the client computers in your enterprise.</span></span> <span data-ttu-id="325f7-134">您可以從 [管理] 和 [監視] 網站或直接從 SQL Server Reporting Services 存取報表。</span><span class="sxs-lookup"><span data-stu-id="325f7-134">You can access the reports from the Administration and Monitoring Website or directly from SQL Server Reporting Services.</span></span>

<span data-ttu-id="325f7-135">管理和監控伺服器</span><span class="sxs-lookup"><span data-stu-id="325f7-135">Administration and Monitoring Server</span></span>

<span data-ttu-id="325f7-136">管理和監控網站</span><span class="sxs-lookup"><span data-stu-id="325f7-136">Administration and Monitoring Website</span></span>

<span data-ttu-id="325f7-137">此功能是在執行 Windows Server 的電腦上設定。</span><span class="sxs-lookup"><span data-stu-id="325f7-137">This feature is configured on a computer running Windows Server.</span></span>

<span data-ttu-id="325f7-138">**管理和監控網站**是用來：</span><span class="sxs-lookup"><span data-stu-id="325f7-138">The **Administration and Monitoring Website** is used to:</span></span>

-   <span data-ttu-id="325f7-139">當使用者鎖定時，協助使用者重新取得電腦存取權。（此網站區域通常稱為 [技術支援中心]。）</span><span class="sxs-lookup"><span data-stu-id="325f7-139">Help end users regain access to their computers when they are locked out. (This area of the Website is commonly called the Help Desk.)</span></span>

-   <span data-ttu-id="325f7-140">查看顯示用戶端電腦合規性狀態與復原活動的報告。</span><span class="sxs-lookup"><span data-stu-id="325f7-140">View reports that show compliance status and recovery activity for client computers.</span></span>

<span data-ttu-id="325f7-141">自助服務入口網站</span><span class="sxs-lookup"><span data-stu-id="325f7-141">Self-Service Portal</span></span>

<span data-ttu-id="325f7-142">此功能是在執行 Windows Server 的電腦上設定。</span><span class="sxs-lookup"><span data-stu-id="325f7-142">This feature is configured on a computer running Windows Server.</span></span>

<span data-ttu-id="325f7-143">**自助式入口**網站是一種網站，可讓用戶端電腦上的使用者能夠獨立登入網站，以取得復原金鑰（如果他們遺失或忘記其 BitLocker 密碼）。</span><span class="sxs-lookup"><span data-stu-id="325f7-143">The **Self-Service Portal** is a website that enables end users on client computers to independently log on to a website to get a recovery key if they lose or forget their BitLocker password.</span></span>

<span data-ttu-id="325f7-144">監視此網站的 web 服務</span><span class="sxs-lookup"><span data-stu-id="325f7-144">Monitoring web services for this website</span></span>

<span data-ttu-id="325f7-145">此功能是在執行 Windows Server 的電腦上設定。</span><span class="sxs-lookup"><span data-stu-id="325f7-145">This feature is configured on a computer running Windows Server.</span></span>

<span data-ttu-id="325f7-146">MBAM 用戶端和網站會使用**監視 web 服務**來與資料庫進行通訊。</span><span class="sxs-lookup"><span data-stu-id="325f7-146">The **monitoring web services** are used by the MBAM Client and the websites to communicate to the database.</span></span>

<span data-ttu-id="325f7-147">**重要** 在 Microsoft BitLocker 管理和監控（MBAM） 2.5 SP1 中不再提供監視 Web 服務，因為 MBAM 網站會直接與恢復資料庫通訊。</span><span class="sxs-lookup"><span data-stu-id="325f7-147">**Important** The Monitoring Web Service is no longer available in Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 SP1 since the MBAM websites communicate directly with the Recovery Database.</span></span>

 

<span data-ttu-id="325f7-148">管理工作站</span><span class="sxs-lookup"><span data-stu-id="325f7-148">Management workstation</span></span>

<span data-ttu-id="325f7-149">MBAM 群組原則範本</span><span class="sxs-lookup"><span data-stu-id="325f7-149">MBAM Group Policy Templates</span></span>

-   <span data-ttu-id="325f7-150">MBAM 群組原則範本是定義 MBAM 之實現設定的群組原則設定，可讓您管理 BitLocker 磁碟機加密。</span><span class="sxs-lookup"><span data-stu-id="325f7-150">The MBAM Group Policy Templates are Group Policy settings that define implementation settings for MBAM, which enable you to manage BitLocker Drive Encryption.</span></span>

-   <span data-ttu-id="325f7-151">在執行 MBAM 之前，您必須從[如何取得 MDOP 組原則（admx）範本](https://go.microsoft.com/fwlink/p/?LinkId=393941)下載群組原則範本，並將其複製到執行支援的 Windows Server 或 Windows 作業系統的伺服器或工作站。</span><span class="sxs-lookup"><span data-stu-id="325f7-151">Before you run MBAM, you must download the Group Policy Templates from [How to Get MDOP Group Policy (.admx) Templates](https://go.microsoft.com/fwlink/p/?LinkId=393941) and copy them to a server or workstation that is running a supported Windows Server or Windows operating system.</span></span>

-   <span data-ttu-id="325f7-152">工作站不一定是專用電腦。</span><span class="sxs-lookup"><span data-stu-id="325f7-152">The workstation does not have to be a dedicated computer.</span></span>

<span data-ttu-id="325f7-153">MBAM 用戶端與 Configuration Manager 用戶端電腦</span><span class="sxs-lookup"><span data-stu-id="325f7-153">MBAM Client and Configuration Manager client computer</span></span>

<span data-ttu-id="325f7-154">MBAM 用戶端軟體</span><span class="sxs-lookup"><span data-stu-id="325f7-154">MBAM Client software</span></span>

<span data-ttu-id="325f7-155">MBAM 用戶端：</span><span class="sxs-lookup"><span data-stu-id="325f7-155">The MBAM Client:</span></span>

-   <span data-ttu-id="325f7-156">使用群組原則物件，在企業中的用戶端電腦上強制執行 BitLocker 磁碟機加密。</span><span class="sxs-lookup"><span data-stu-id="325f7-156">Uses Group Policy Objects to enforce BitLocker Drive Encryption on client computers in the enterprise.</span></span>

-   <span data-ttu-id="325f7-157">收集三種資料磁片磁碟機類型的 Bitlocker 復原金鑰：操作系統磁碟機、固定資料磁碟機，以及可移動（USB）資料磁碟機。</span><span class="sxs-lookup"><span data-stu-id="325f7-157">Collects the Bitlocker recovery key for three data drive types: operating system drives, fixed data drives, and removable (USB) data drives.</span></span>

-   <span data-ttu-id="325f7-158">收集用戶端電腦的恢復資訊和電腦資訊。</span><span class="sxs-lookup"><span data-stu-id="325f7-158">Collects recovery information and computer information about the client computers.</span></span>



## <span data-ttu-id="325f7-159">相關主題</span><span class="sxs-lookup"><span data-stu-id="325f7-159">Related topics</span></span>


[<span data-ttu-id="325f7-160">開始使用 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="325f7-160">Getting Started with MBAM 2.5</span></span>](getting-started-with-mbam-25.md)

[<span data-ttu-id="325f7-161">MBAM 2.5 搭配 Configuration Manager 整合拓撲的概要架構</span><span class="sxs-lookup"><span data-stu-id="325f7-161">High-Level Architecture of MBAM 2.5 with Configuration Manager Integration Topology</span></span>](high-level-architecture-of-mbam-25-with-configuration-manager-integration-topology.md)

[<span data-ttu-id="325f7-162">MBAM 2.5 部署的功能圖例</span><span class="sxs-lookup"><span data-stu-id="325f7-162">Illustrated Features of an MBAM 2.5 Deployment</span></span>](illustrated-features-of-an-mbam-25-deployment.md)

 

## <span data-ttu-id="325f7-163">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="325f7-163">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="325f7-164">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="325f7-164">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="325f7-165">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="325f7-165">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





