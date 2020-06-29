---
title: MBAM 2.5 部署的功能圖例
description: MBAM 2.5 部署的功能圖例
author: dansimp
ms.assetid: 7b5eff42-af8c-4bd0-a20a-18cc2e779f01
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/15/2018
ms.openlocfilehash: c3b205d4f0b4b18cf8bdbf51982b5a59e5e1b9d5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800083"
---
# <span data-ttu-id="523e6-103">MBAM 2.5 部署的功能圖例</span><span class="sxs-lookup"><span data-stu-id="523e6-103">Illustrated Features of an MBAM 2.5 Deployment</span></span>


<span data-ttu-id="523e6-104">本主題描述針對下列拓撲進行 Microsoft BitLocker 管理和監控（MBAM）2.5 部署的個別功能：</span><span class="sxs-lookup"><span data-stu-id="523e6-104">This topic describes the individual features that make up a Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 deployment for the following topologies:</span></span>

-   <span data-ttu-id="523e6-105">獨立 MBAM</span><span class="sxs-lookup"><span data-stu-id="523e6-105">MBAM Stand-alone</span></span>

-   <span data-ttu-id="523e6-106">System Center Configuration Manager 整合</span><span class="sxs-lookup"><span data-stu-id="523e6-106">System Center Configuration Manager Integration</span></span>

**<span data-ttu-id="523e6-107">重要</span><span class="sxs-lookup"><span data-stu-id="523e6-107">Important</span></span>**  
<span data-ttu-id="523e6-108">這些功能不代表部署 MBAM 的建議結構。</span><span class="sxs-lookup"><span data-stu-id="523e6-108">These features do not represent the recommended architecture for deploying MBAM.</span></span> <span data-ttu-id="523e6-109">此資訊只能用來瞭解組成 MBAM 部署的個別功能。</span><span class="sxs-lookup"><span data-stu-id="523e6-109">Use this information only as a guide to understand the individual features that make up an MBAM deployment.</span></span> <span data-ttu-id="523e6-110">請參閱適用于[MBAM 2.5 的高層次架構](high-level-architecture-for-mbam-25.md)，以取得 MBAM 的建議架構。</span><span class="sxs-lookup"><span data-stu-id="523e6-110">See [High-Level Architecture for MBAM 2.5](high-level-architecture-for-mbam-25.md) for the recommended architecture for MBAM.</span></span>



<span data-ttu-id="523e6-111">如需本主題中所述軟體支援版本的清單，請參閱[MBAM 2.5 支援](mbam-25-supported-configurations.md)的設定。</span><span class="sxs-lookup"><span data-stu-id="523e6-111">For a list of the supported versions of the software mentioned in this topic, see [MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md).</span></span>

## <a href="" id="bkmk-standalone"></a> <span data-ttu-id="523e6-112">MBAM 獨立拓朴</span><span class="sxs-lookup"><span data-stu-id="523e6-112">MBAM Stand-alone topology</span></span>


<span data-ttu-id="523e6-113">下列影像和表格說明 MBAM 獨立拓撲中的功能。</span><span class="sxs-lookup"><span data-stu-id="523e6-113">The following image and table explain the features in an MBAM Stand-alone topology.</span></span>

![mbab2\-5](images/mbam2-5-standalonecomponents.png)

|<span data-ttu-id="523e6-115">功能類型</span><span class="sxs-lookup"><span data-stu-id="523e6-115">Feature type</span></span>|<span data-ttu-id="523e6-116">描述</span><span class="sxs-lookup"><span data-stu-id="523e6-116">Description</span></span>|<span data-ttu-id="523e6-117">資料庫</span><span class="sxs-lookup"><span data-stu-id="523e6-117">Database</span></span>|
|-|-|-|
|<span data-ttu-id="523e6-118">復原資料庫</span><span class="sxs-lookup"><span data-stu-id="523e6-118">Recovery Database</span></span>|<span data-ttu-id="523e6-119">此資料庫儲存從 MBAM 用戶端電腦收集的復原資料。</span><span class="sxs-lookup"><span data-stu-id="523e6-119">This database stores recovery data that is collected from MBAM client computers.</span></span>|<span data-ttu-id="523e6-120">此功能是在執行 Windows Server 的伺服器以及支援的 SQL Server 實例上設定。</span><span class="sxs-lookup"><span data-stu-id="523e6-120">This feature is configured on a server running Windows Server and a supported SQL Server instance.</span></span>|
|<span data-ttu-id="523e6-121">合規性和審核資料庫</span><span class="sxs-lookup"><span data-stu-id="523e6-121">Compliance and Audit Database</span></span>|<span data-ttu-id="523e6-122">此資料庫儲存合規性資料，主要用於 SQL Server Reporting Services 主機的報表。</span><span class="sxs-lookup"><span data-stu-id="523e6-122">This database stores compliance data, which is used primarily for the Reports that SQL Server Reporting Services hosts.</span></span>|<span data-ttu-id="523e6-123">此功能是在執行 Windows Server 的伺服器以及支援的 SQL Server 實例上設定。</span><span class="sxs-lookup"><span data-stu-id="523e6-123">This feature is configured on a server running Windows Server and a supported SQL Server instance.</span></span>|
|<span data-ttu-id="523e6-124">合規性與審計報告</span><span class="sxs-lookup"><span data-stu-id="523e6-124">Compliance and Audit Reports</span></span>|||
|<span data-ttu-id="523e6-125">報告 Web 服務</span><span class="sxs-lookup"><span data-stu-id="523e6-125">Reporting Web Service</span></span>|<span data-ttu-id="523e6-126">此 web 服務可讓您在管理與監控網站以及儲存報告資料的 SQL Server 實例之間進行通訊。</span><span class="sxs-lookup"><span data-stu-id="523e6-126">This web service enables communication between the Administration and Monitoring Website and the SQL Server instance where reporting data is stored.</span></span>|<span data-ttu-id="523e6-127">此功能已安裝在執行 Windows Server 的伺服器上。</span><span class="sxs-lookup"><span data-stu-id="523e6-127">This feature is installed on a server running Windows Server.</span></span>|
|<span data-ttu-id="523e6-128">報告網站（管理和監控網站）</span><span class="sxs-lookup"><span data-stu-id="523e6-128">Reporting Website (Administration and Monitoring Website)</span></span>|<span data-ttu-id="523e6-129">您可以從 [管理和監控] 網站查看報告。</span><span class="sxs-lookup"><span data-stu-id="523e6-129">You view Reports from the Administration and Monitoring Website.</span></span> <span data-ttu-id="523e6-130">報告會提供企業中用戶端電腦的復原審核及合規性狀態資料。</span><span class="sxs-lookup"><span data-stu-id="523e6-130">The Reports provide recovery audit and compliance status data about the client computers in your enterprise.</span></span>|<span data-ttu-id="523e6-131">此功能是在執行 Windows Server 的伺服器上設定。</span><span class="sxs-lookup"><span data-stu-id="523e6-131">This feature is configured on a server running Windows Server.</span></span>|
|<span data-ttu-id="523e6-132">SQL Server Reporting Services （SSRS）</span><span class="sxs-lookup"><span data-stu-id="523e6-132">SQL Server Reporting Services (SSRS)</span></span>|<span data-ttu-id="523e6-133">報告是在 SSRS 資料庫實例中設定。</span><span class="sxs-lookup"><span data-stu-id="523e6-133">Reports are configured in an SSRS database instance.</span></span> <span data-ttu-id="523e6-134">報告可以直接從 SSRS 查看，或從管理和監控網站查看。</span><span class="sxs-lookup"><span data-stu-id="523e6-134">Reports can be viewed directly from SSRS or from the Administration and Monitoring Website.</span></span>|<span data-ttu-id="523e6-135">此功能是在執行 Windows Server 的伺服器以及執行 SSRS 的支援的 SQL Server 實例上設定。</span><span class="sxs-lookup"><span data-stu-id="523e6-135">This feature is configured on a server running Windows Server and a supported SQL Server instance that is running SSRS.</span></span>|
|<span data-ttu-id="523e6-136">自助服務伺服器</span><span class="sxs-lookup"><span data-stu-id="523e6-136">Self-Service Server</span></span>|||
|<span data-ttu-id="523e6-137">自助服務 Web 服務</span><span class="sxs-lookup"><span data-stu-id="523e6-137">Self-Service Web Service</span></span>|<span data-ttu-id="523e6-138">此 web 服務是由 MBAM 用戶端和 [管理及監視] 網站和自助服務入口網站使用，以與恢復資料庫進行通訊。</span><span class="sxs-lookup"><span data-stu-id="523e6-138">This web service is used by the MBAM Client and the Administration and Monitoring Website and Self-Service Portal to communicate to the Recovery Database.</span></span>|<span data-ttu-id="523e6-139">此功能已安裝在執行 Windows Server 的電腦上。</span><span class="sxs-lookup"><span data-stu-id="523e6-139">This feature is installed on a computer running Windows Server.</span></span>|
|<span data-ttu-id="523e6-140">自助式網站（自助服務入口網站）</span><span class="sxs-lookup"><span data-stu-id="523e6-140">Self-Service Website (Self-Service Portal)</span></span>|<span data-ttu-id="523e6-141">此網站可讓用戶端電腦上的使用者能夠獨立登入網站，以取得復原金鑰（如果他們遺失或忘記其 BitLocker 密碼）。</span><span class="sxs-lookup"><span data-stu-id="523e6-141">This website enables end users on client computers to independently sign in to a website to get a recovery key if they lose or forget their BitLocker password.</span></span>|<span data-ttu-id="523e6-142">此功能是在執行 Windows Server 的電腦上設定。</span><span class="sxs-lookup"><span data-stu-id="523e6-142">This feature is configured on a computer running Windows Server.</span></span>|
|<span data-ttu-id="523e6-143">管理和監控伺服器</span><span class="sxs-lookup"><span data-stu-id="523e6-143">Administration and Monitoring Server</span></span>|||
|<span data-ttu-id="523e6-144">管理和監控 Web 服務</span><span class="sxs-lookup"><span data-stu-id="523e6-144">Administration and Monitoring Web Service</span></span>|<span data-ttu-id="523e6-145">MBAM 用戶端和網站會使用監視 Web 服務來與資料庫進行通訊。</span><span class="sxs-lookup"><span data-stu-id="523e6-145">The Monitoring Web Service is used by the MBAM Client and the websites to communicate to the databases.</span></span>|<span data-ttu-id="523e6-146">此功能已安裝在執行 Windows Server 的電腦上。</span><span class="sxs-lookup"><span data-stu-id="523e6-146">This feature is installed on a computer running Windows Server.</span></span>|

**<span data-ttu-id="523e6-147">重要</span><span class="sxs-lookup"><span data-stu-id="523e6-147">Important</span></span>**  
<span data-ttu-id="523e6-148">在 Microsoft BitLocker 管理和監控（MBAM） 2.5 SP1 中不再提供自助服務 Web 服務，其中的 MBAM 用戶端、管理和監控網站，以及自助式入口網站直接與恢復資料庫進行通訊。</span><span class="sxs-lookup"><span data-stu-id="523e6-148">The Self-Service Web Service is no longer available in Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 SP1, in which the MBAM Client, the Administration and Monitoring Website, and the Self-Service Portal communicate directly with the Recovery Database.</span></span>

**<span data-ttu-id="523e6-149">重要</span><span class="sxs-lookup"><span data-stu-id="523e6-149">Important</span></span>**  
<span data-ttu-id="523e6-150">因為 MBAM 用戶端和網站直接與復原資料庫通訊，所以在 Microsoft BitLocker 管理和監控（MBAM） 2.5 SP1 中已不再提供監視 Web 服務。</span><span class="sxs-lookup"><span data-stu-id="523e6-150">The Monitoring Web Service is no longer available in Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 SP1 since the MBAM Client and the websites communicate directly with the Recovery Database.</span></span>


## <a href="" id="bkmk-cmintegrated"></a><span data-ttu-id="523e6-151">System Center Configuration Manager 整合拓撲</span><span class="sxs-lookup"><span data-stu-id="523e6-151">System Center Configuration Manager Integration topology</span></span>

<span data-ttu-id="523e6-152">下列影像和表格說明系統中心 Configuration Manager 整合拓撲中的功能。</span><span class="sxs-lookup"><span data-stu-id="523e6-152">The following image and table explain the features in the System Center Configuration Manager Integration topology.</span></span>

![mbam2\-5](images/mbam2-5-cmcomponents.png)

**<span data-ttu-id="523e6-154">重要</span><span class="sxs-lookup"><span data-stu-id="523e6-154">Important</span></span>**  
<span data-ttu-id="523e6-155">在 Microsoft BitLocker 管理和監控（MBAM） 2.5 SP1 中不再提供自助服務 Web 服務，其中的 MBAM 用戶端、管理和監控網站，以及自助式入口網站直接與恢復資料庫進行通訊。</span><span class="sxs-lookup"><span data-stu-id="523e6-155">The Self-Service Web Service is no longer available in Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 SP1, in which the MBAM Client, the Administration and Monitoring Website, and the Self-Service Portal communicate directly with the Recovery Database.</span></span>

**<span data-ttu-id="523e6-156">警告</span><span class="sxs-lookup"><span data-stu-id="523e6-156">Warning</span></span>**  
<span data-ttu-id="523e6-157">因為 MBAM 用戶端和網站直接與復原資料庫通訊，所以在 Microsoft BitLocker 管理和監控（MBAM） 2.5 SP1 中已不再提供監視 Web 服務。</span><span class="sxs-lookup"><span data-stu-id="523e6-157">The Monitoring Web Service is no longer available in Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 SP1 since the MBAM Client and the websites communicate directly with the Recovery Database.</span></span>


|                        <span data-ttu-id="523e6-158">功能類型</span><span class="sxs-lookup"><span data-stu-id="523e6-158">Feature type</span></span>                        |                                                                                                    <span data-ttu-id="523e6-159">描述</span><span class="sxs-lookup"><span data-stu-id="523e6-159">Description</span></span>                                                                                                    |
|------------------------------------------------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
|                    <span data-ttu-id="523e6-160">自助服務伺服器</span><span class="sxs-lookup"><span data-stu-id="523e6-160">Self-Service Server</span></span>                     |                                                                                                                                                                                                                   |
|                  <span data-ttu-id="523e6-161">自助服務 Web 服務</span><span class="sxs-lookup"><span data-stu-id="523e6-161">Self-Service Web Service</span></span>                  |                                                 <span data-ttu-id="523e6-162">此 web 服務是由 MBAM 用戶端和自助入口網站使用，以與恢復資料庫進行通訊。</span><span class="sxs-lookup"><span data-stu-id="523e6-162">This web service is used by the MBAM Client and the Self-Service Portal to communicate to the Recovery Database.</span></span>                                                  |
|                    <span data-ttu-id="523e6-163">自助服務網站</span><span class="sxs-lookup"><span data-stu-id="523e6-163">Self-Service Website</span></span>                    |                          <span data-ttu-id="523e6-164">此網站可讓用戶端電腦上的使用者能夠獨立登入網站，以取得復原金鑰（如果他們遺失或忘記其 BitLocker 密碼）。</span><span class="sxs-lookup"><span data-stu-id="523e6-164">This website enables end users on client computers to independently sign in to a website to get a recovery key if they lose or forget their BitLocker password.</span></span>                          |
| <span data-ttu-id="523e6-165">管理和監控伺服器/復原審核報告</span><span class="sxs-lookup"><span data-stu-id="523e6-165">Administration and Monitoring Server/Recovery Audit Report</span></span> |                                                                                                                                                                                                                   |
|         <span data-ttu-id="523e6-166">管理和監控 Web 服務</span><span class="sxs-lookup"><span data-stu-id="523e6-166">Administration and Monitoring Web Service</span></span>          |                               <span data-ttu-id="523e6-167">此 web 服務可讓您在管理與監控網站以及儲存報告資料的 SQL Server 資料庫之間進行通訊。</span><span class="sxs-lookup"><span data-stu-id="523e6-167">This web service enables communication between the Administration and Monitoring Website and the SQL Server databases where reporting data is stored.</span></span>                               |
|           <span data-ttu-id="523e6-168">管理和監控網站</span><span class="sxs-lookup"><span data-stu-id="523e6-168">Administration and Monitoring Website</span></span>            | <span data-ttu-id="523e6-169">[恢復審核] 報告是透過 [管理] 和 [監視] 網站查看。</span><span class="sxs-lookup"><span data-stu-id="523e6-169">The Recovery Audit report is viewed from the Administration and Monitoring Website.</span></span> <span data-ttu-id="523e6-170">使用 Configuration Manager 主控台來查看所有其他報表，或直接從 SQL Server Reporting Services 查看報表。</span><span class="sxs-lookup"><span data-stu-id="523e6-170">Use the Configuration Manager console to view all other reports, or view reports directly from SQL Server Reporting Services.</span></span> |
|                         <span data-ttu-id="523e6-171">資料庫</span><span class="sxs-lookup"><span data-stu-id="523e6-171">Databases</span></span>                          |                                                                                                                                                                                                                   |
|                     <span data-ttu-id="523e6-172">復原資料庫</span><span class="sxs-lookup"><span data-stu-id="523e6-172">Recovery Database</span></span>                      |                                                                 <span data-ttu-id="523e6-173">此資料庫儲存從 MBAM 用戶端電腦收集的復原資料。</span><span class="sxs-lookup"><span data-stu-id="523e6-173">This database stores recovery data that is collected from MBAM client computers.</span></span>                                                                  |
|                       <span data-ttu-id="523e6-174">審核資料庫</span><span class="sxs-lookup"><span data-stu-id="523e6-174">Audit Database</span></span>                       |                                                                   <span data-ttu-id="523e6-175">此資料庫儲存有關恢復嘗試與活動的審核資訊。</span><span class="sxs-lookup"><span data-stu-id="523e6-175">This database stores audit information about recovery attempts and activity.</span></span>                                                                    |
|               <span data-ttu-id="523e6-176">Configuration Manager 功能</span><span class="sxs-lookup"><span data-stu-id="523e6-176">Configuration Manager Features</span></span>               |                                                                                                                                                                                                                   |
|          <span data-ttu-id="523e6-177">Configuration Manager 管理主控台</span><span class="sxs-lookup"><span data-stu-id="523e6-177">Configuration Manager Management console</span></span>          |                                                                   <span data-ttu-id="523e6-178">這個主控台內嵌于 Configuration Manager 中，用來查看報告。</span><span class="sxs-lookup"><span data-stu-id="523e6-178">This console is built into Configuration Manager and is used to view reports.</span></span>                                                                   |
|               <span data-ttu-id="523e6-179">Configuration Manager 報告</span><span class="sxs-lookup"><span data-stu-id="523e6-179">Configuration Manager Reports</span></span>                |                                                             <span data-ttu-id="523e6-180">報告顯示企業中用戶端電腦的合規性與復原審核資料。</span><span class="sxs-lookup"><span data-stu-id="523e6-180">Reports show compliance and recovery audit data for client computers in your enterprise.</span></span>                                                              |
|               <span data-ttu-id="523e6-181">SQL Server Reporting Services</span><span class="sxs-lookup"><span data-stu-id="523e6-181">SQL Server Reporting Services</span></span>                |                                                <span data-ttu-id="523e6-182">SSRS 會啟用 MBAM 報告。</span><span class="sxs-lookup"><span data-stu-id="523e6-182">SSRS enables the MBAM Reports.</span></span> <span data-ttu-id="523e6-183">報告可以直接從 SSRS 或從 Configuration Manager 主控台查看。</span><span class="sxs-lookup"><span data-stu-id="523e6-183">Reports can be viewed directly from SSRS or from the Configuration Manager console.</span></span>                                                 |

## <span data-ttu-id="523e6-184">相關主題</span><span class="sxs-lookup"><span data-stu-id="523e6-184">Related topics</span></span>

[<span data-ttu-id="523e6-185">MBAM 2.5 的概要架構</span><span class="sxs-lookup"><span data-stu-id="523e6-185">High-Level Architecture for MBAM 2.5</span></span>](high-level-architecture-for-mbam-25.md)

[<span data-ttu-id="523e6-186">開始使用 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="523e6-186">Getting Started with MBAM 2.5</span></span>](getting-started-with-mbam-25.md)

## <span data-ttu-id="523e6-187">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="523e6-187">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="523e6-188">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="523e6-188">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="523e6-189">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="523e6-189">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>




