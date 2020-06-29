---
title: MBAM 2.5 搭配 Configuration Manager 整合拓撲的概要架構
description: MBAM 2.5 搭配 Configuration Manager 整合拓撲的概要架構
author: dansimp
ms.assetid: 075bafa1-792b-4c24-9d8e-5d3153e2112c
ms.reviewer: ''
manager: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/23/2018
ms.author: dansimp
ms.openlocfilehash: 75af2e22981d76568916c36acadbbb25648b1f1d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811349"
---
# <span data-ttu-id="36380-103">MBAM 2.5 的高層次架構與 Configuration Manager 整合拓撲</span><span class="sxs-lookup"><span data-stu-id="36380-103">High-level architecture of MBAM 2.5 with Configuration Manager Integration topology</span></span>

<span data-ttu-id="36380-104">本主題描述使用 Configuration Manager 整合拓撲來部署 Microsoft BitLocker 管理和監控（MBAM）的建議架構。</span><span class="sxs-lookup"><span data-stu-id="36380-104">This topic describes the recommended architecture for deploying Microsoft BitLocker Administration and Monitoring (MBAM) with the Configuration Manager Integration topology.</span></span> <span data-ttu-id="36380-105">此拓撲會與 System Center Configuration Manager 整合 MBAM。</span><span class="sxs-lookup"><span data-stu-id="36380-105">This topology integrates MBAM with System Center Configuration Manager.</span></span> <span data-ttu-id="36380-106">若要在獨立拓朴中部署 MBAM，請參閱[MBAM 2.5 的高層次架構（含獨立拓朴](high-level-architecture-of-mbam-25-with-stand-alone-topology.md)）。</span><span class="sxs-lookup"><span data-stu-id="36380-106">To deploy MBAM with the Stand-alone topology, see [High-Level Architecture of MBAM 2.5 with Stand-alone Topology](high-level-architecture-of-mbam-25-with-stand-alone-topology.md).</span></span>

<span data-ttu-id="36380-107">如需本主題中所述軟體支援版本的清單，請參閱[MBAM 2.5 支援](mbam-25-supported-configurations.md)的設定。</span><span class="sxs-lookup"><span data-stu-id="36380-107">For a list of the supported versions of the software mentioned in this topic, see [MBAM 2.5 Supported Configurations](mbam-25-supported-configurations.md).</span></span>

<span data-ttu-id="36380-108">**重要** 當您使用 Configuration Manager 2007 時，Configuration Manager 整合拓撲安裝不支援 Windows To Go。</span><span class="sxs-lookup"><span data-stu-id="36380-108">**Important** Windows To Go is not supported for the Configuration Manager Integration topology installation when you are using Configuration Manager 2007.</span></span>

 

## <span data-ttu-id="36380-109">建議的伺服器數和支援的用戶端數量</span><span class="sxs-lookup"><span data-stu-id="36380-109">Recommended number of servers and supported number of clients</span></span>


<span data-ttu-id="36380-110">在生產環境中，建議的伺服器數量及支援的用戶端數量如下：</span><span class="sxs-lookup"><span data-stu-id="36380-110">The recommended number of servers and supported number of clients in a production environment is as follows:</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="36380-111">建議的架構</span><span class="sxs-lookup"><span data-stu-id="36380-111">Recommended architecture</span></span></th>
<th align="left"><span data-ttu-id="36380-112">詳細資料</span><span class="sxs-lookup"><span data-stu-id="36380-112">Details</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="36380-113">伺服器和其他電腦的數目</span><span class="sxs-lookup"><span data-stu-id="36380-113">Number of servers and other computers</span></span></p></td>
<td align="left"><p><span data-ttu-id="36380-114">三台伺服器</span><span class="sxs-lookup"><span data-stu-id="36380-114">Three servers</span></span></p>
<p><span data-ttu-id="36380-115">一個工作站</span><span class="sxs-lookup"><span data-stu-id="36380-115">One workstation</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="36380-116">支援的用戶端電腦數目</span><span class="sxs-lookup"><span data-stu-id="36380-116">Number of client computers supported</span></span></p></td>
<td align="left"><p><span data-ttu-id="36380-117">500000</span><span class="sxs-lookup"><span data-stu-id="36380-117">500,000</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="36380-118">Configuration Manager 整合與獨立拓朴間的差異</span><span class="sxs-lookup"><span data-stu-id="36380-118">Differences between Configuration Manager Integration and stand-alone topologies</span></span>


<span data-ttu-id="36380-119">拓撲結構的主要差異為：</span><span class="sxs-lookup"><span data-stu-id="36380-119">The main differences between the topologies are:</span></span>

-   <span data-ttu-id="36380-120">相容性與報告功能會從 MBAM 中移除，且可從 Configuration Manager 存取。</span><span class="sxs-lookup"><span data-stu-id="36380-120">The compliance and reporting features are removed from MBAM and are accessed from Configuration Manager.</span></span>

-   <span data-ttu-id="36380-121">報告是從 Configuration Manager 管理主控台查看，除了復原審核報告例外之外，您仍可從 MBAM 管理和監控網站繼續進行查看。</span><span class="sxs-lookup"><span data-stu-id="36380-121">Reports are viewed from the Configuration Manager Management Console, with the exception of the Recovery Audit Report, which you continue to view from the MBAM Administration and Monitoring Website.</span></span>

## <span data-ttu-id="36380-122">建議的 MBAM 高層次架構與 Configuration Manager 整合拓撲</span><span class="sxs-lookup"><span data-stu-id="36380-122">Recommended MBAM high-level architecture with the Configuration Manager Integration topology</span></span>


<span data-ttu-id="36380-123">下列圖表與表格說明 MBAM 與 Configuration Manager 整合拓朴的建議高層次架構。</span><span class="sxs-lookup"><span data-stu-id="36380-123">The following diagram and table describe the recommended high-level architecture for MBAM with the Configuration Manager Integration topology.</span></span> <span data-ttu-id="36380-124">MBAM 多林部署需要單向或雙向信任。</span><span class="sxs-lookup"><span data-stu-id="36380-124">MBAM multi-forest deployments require a one-way or two-way trust.</span></span> <span data-ttu-id="36380-125">單向信任要求伺服器網域信任用戶端網域。</span><span class="sxs-lookup"><span data-stu-id="36380-125">One-way trusts require that the server domain trusts the client domain.</span></span>

![mbam2\-5](images/mbam2-5-cmserver.png)

### <span data-ttu-id="36380-127">資料庫伺服器</span><span class="sxs-lookup"><span data-stu-id="36380-127">Database server</span></span>

#### <span data-ttu-id="36380-128">復原資料庫</span><span class="sxs-lookup"><span data-stu-id="36380-128">Recovery database</span></span>

<span data-ttu-id="36380-129">此功能已在執行 Windows Server 和支援的 SQL Server 實例的電腦上設定。</span><span class="sxs-lookup"><span data-stu-id="36380-129">This feature is configured on a computer running Windows Server and supported SQL Server instance.</span></span>

<span data-ttu-id="36380-130">復原**資料庫**會儲存從 MBAM 用戶端電腦收集的復原資料。</span><span class="sxs-lookup"><span data-stu-id="36380-130">The **Recovery Database** stores recovery data that is collected from MBAM Client computers.</span></span>

#### <span data-ttu-id="36380-131">審核資料庫</span><span class="sxs-lookup"><span data-stu-id="36380-131">Audit database</span></span>

<span data-ttu-id="36380-132">此功能已在執行 Windows Server 和支援的 SQL Server 實例的電腦上設定。</span><span class="sxs-lookup"><span data-stu-id="36380-132">This feature is configured on a computer running Windows Server and supported SQL Server instance.</span></span>

<span data-ttu-id="36380-133">**審核資料庫**會儲存從已存取復原資料的用戶端電腦收集的審核活動資料。</span><span class="sxs-lookup"><span data-stu-id="36380-133">The **Audit Database** stores audit activity data that is collected from client computers that have accessed recovery data.</span></span>

#### <span data-ttu-id="36380-134">報告</span><span class="sxs-lookup"><span data-stu-id="36380-134">Reports</span></span>

<span data-ttu-id="36380-135">此功能已在執行 Windows Server 和支援的 SQL Server 實例的電腦上設定。</span><span class="sxs-lookup"><span data-stu-id="36380-135">This feature is configured on a computer running Windows Server and supported SQL Server instance.</span></span>

<span data-ttu-id="36380-136">**報告**會提供企業中用戶端電腦的復原審核資料。</span><span class="sxs-lookup"><span data-stu-id="36380-136">The **Reports** provide recovery audit data for the client computers in your enterprise.</span></span> <span data-ttu-id="36380-137">您可以透過 Configuration Manager 主控台或直接從 SQL Server Reporting Services 來查看報表。</span><span class="sxs-lookup"><span data-stu-id="36380-137">You can view reports from the Configuration Manager console or directly from SQL Server Reporting Services.</span></span>

### <span data-ttu-id="36380-138">Configuration Manager 主要網站伺服器</span><span class="sxs-lookup"><span data-stu-id="36380-138">Configuration Manager primary site server</span></span>

<span data-ttu-id="36380-139">系統中心 Configuration Manager 整合功能</span><span class="sxs-lookup"><span data-stu-id="36380-139">System Center Configuration Manager Integration feature</span></span>

-   <span data-ttu-id="36380-140">此功能是在 Configuration Manager 主要網站伺服器（即 Configuration Manager 基礎結構中的頂層伺服器）上設定。</span><span class="sxs-lookup"><span data-stu-id="36380-140">This feature is configured on the Configuration Manager Primary Site Server, which is the top-tier server in your Configuration Manager infrastructure.</span></span>

-   <span data-ttu-id="36380-141">**Configuration Manager 伺服器**會從用戶端電腦收集硬體清查資訊，並使用它來報告用戶端電腦的 BitLocker 合規性。</span><span class="sxs-lookup"><span data-stu-id="36380-141">The **Configuration Manager Server** collects the hardware inventory information from client computers and is used to report BitLocker compliance of client computers.</span></span>

-   <span data-ttu-id="36380-142">當您執行 Microsoft BitLocker 管理及監視設定向導來安裝伺服器軟體時，系統會在 Configuration Manager 主要網站伺服器上設定 MBAM 支援的電腦集合、配置基線及報告。</span><span class="sxs-lookup"><span data-stu-id="36380-142">When you run the Microsoft BitLocker Administration and Monitoring Setup wizard to install the server software, the MBAM Supported Computers collection, configuration baseline, and reports are configured on the Configuration Manager Primary Site Server.</span></span>

-   <span data-ttu-id="36380-143">**Configuration Manager 主控台**必須安裝在您安裝 MBAM Server 軟體的同一部電腦上。</span><span class="sxs-lookup"><span data-stu-id="36380-143">The **Configuration Manager console** must be installed on the same computer on which you install the MBAM Server software.</span></span>

### <span data-ttu-id="36380-144">管理和監控伺服器</span><span class="sxs-lookup"><span data-stu-id="36380-144">Administration and monitoring server</span></span>

#### <span data-ttu-id="36380-145">管理和監控網站</span><span class="sxs-lookup"><span data-stu-id="36380-145">Administration and monitoring website</span></span>

<span data-ttu-id="36380-146">此功能是在執行 Windows Server 的電腦上設定。</span><span class="sxs-lookup"><span data-stu-id="36380-146">This feature is configured on a computer running Windows Server.</span></span>

<span data-ttu-id="36380-147">**管理和監控網站**是用來：</span><span class="sxs-lookup"><span data-stu-id="36380-147">The **Administration and monitoring website** is used to:</span></span>

-   <span data-ttu-id="36380-148">當使用者鎖定時，協助使用者重新取得電腦存取權。（此網站區域通常稱為 [技術支援中心]。）</span><span class="sxs-lookup"><span data-stu-id="36380-148">Help end users regain access to their computers when they are locked out. (This area of the Website is commonly called the Help Desk.)</span></span>

-   <span data-ttu-id="36380-149">查看復原審核報告，其中顯示用戶端電腦的恢復活動。</span><span class="sxs-lookup"><span data-stu-id="36380-149">View the Recovery Audit Report, which shows recovery activity for client computers.</span></span> <span data-ttu-id="36380-150">您可以從 Configuration Manager 主控台查看其他報告。</span><span class="sxs-lookup"><span data-stu-id="36380-150">Other reports are viewed from the Configuration Manager console.</span></span>

#### <span data-ttu-id="36380-151">自助服務入口網站</span><span class="sxs-lookup"><span data-stu-id="36380-151">Self-service portal</span></span>

<span data-ttu-id="36380-152">此功能是在執行 Windows Server 的電腦上設定。</span><span class="sxs-lookup"><span data-stu-id="36380-152">This feature is configured on a computer running Windows Server.</span></span>

<span data-ttu-id="36380-153">**自助式入口**網站是一種網站，可讓用戶端電腦上的使用者能夠獨立登入網站，以取得復原金鑰（如果他們遺失或忘記其 BitLocker 密碼）。</span><span class="sxs-lookup"><span data-stu-id="36380-153">The **Self-Service Portal** is a website that enables end users on client computers to independently log on to a website to get a recovery key if they lose or forget their BitLocker password.</span></span>

#### <span data-ttu-id="36380-154">監視此網站的 web 服務</span><span class="sxs-lookup"><span data-stu-id="36380-154">Monitoring web services for this website</span></span>

<span data-ttu-id="36380-155">此功能已安裝在執行 Windows Server 的電腦上。</span><span class="sxs-lookup"><span data-stu-id="36380-155">This feature is installed on a computer running Windows Server.</span></span>

<span data-ttu-id="36380-156">MBAM 用戶端和網站會使用**監視 web 服務**來與資料庫進行通訊。</span><span class="sxs-lookup"><span data-stu-id="36380-156">The **monitoring web services** are used by the MBAM Client and the websites to communicate to the database.</span></span>

**<span data-ttu-id="36380-157">重要</span><span class="sxs-lookup"><span data-stu-id="36380-157">Important</span></span>**<br><span data-ttu-id="36380-158">在 Microsoft BitLocker 管理和監控（MBAM） 2.5 SP1 中不再提供監視 Web 服務，因為 MBAM 網站會直接與恢復資料庫通訊。</span><span class="sxs-lookup"><span data-stu-id="36380-158">The Monitoring Web Service is no longer available in Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 SP1 since the MBAM websites communicate directly with the Recovery Database.</span></span> 

 

### <span data-ttu-id="36380-159">管理工作站</span><span class="sxs-lookup"><span data-stu-id="36380-159">Management workstation</span></span>

#### <span data-ttu-id="36380-160">MBAM 群組原則範本</span><span class="sxs-lookup"><span data-stu-id="36380-160">MBAM group policy templates</span></span>

-   <span data-ttu-id="36380-161">**MBAM 群組原則範本**是定義 MBAM 之實現設定的群組原則設定，可讓您管理 BitLocker 磁碟機加密。</span><span class="sxs-lookup"><span data-stu-id="36380-161">The **MBAM Group Policy Templates** are Group Policy settings that define implementation settings for MBAM, which enable you to manage BitLocker drive encryption.</span></span>

-   <span data-ttu-id="36380-162">在執行 MBAM 之前，您必須從[如何取得 MDOP 組原則（admx）範本](https://go.microsoft.com/fwlink/p/?LinkId=393941)下載群組原則範本，並將其複製到執行支援的 Windows Server 或 Windows 作業系統的伺服器或工作站。</span><span class="sxs-lookup"><span data-stu-id="36380-162">Before you run MBAM, you must download the Group Policy Templates from [How to Get MDOP Group Policy (.admx) Templates](https://go.microsoft.com/fwlink/p/?LinkId=393941) and copy them to a server or workstation that is running a supported Windows Server or Windows operating system.</span></span>

    **<span data-ttu-id="36380-163">注意</span><span class="sxs-lookup"><span data-stu-id="36380-163">NOTE</span></span>**<br><span data-ttu-id="36380-164">工作站不一定是專用電腦。</span><span class="sxs-lookup"><span data-stu-id="36380-164">The workstation does not have to be a dedicated computer.</span></span>

     

### <span data-ttu-id="36380-165">MBAM 用戶端與 Configuration Manager 用戶端電腦</span><span class="sxs-lookup"><span data-stu-id="36380-165">MBAM Client and Configuration Manager Client computer</span></span>

#### <span data-ttu-id="36380-166">MBAM 用戶端軟體</span><span class="sxs-lookup"><span data-stu-id="36380-166">MBAM Client software</span></span>

<span data-ttu-id="36380-167">**MBAM 用戶端**：</span><span class="sxs-lookup"><span data-stu-id="36380-167">The **MBAM Client**:</span></span>

-   <span data-ttu-id="36380-168">使用群組原則物件，在企業中的用戶端電腦上強制執行 BitLocker 磁碟機加密。</span><span class="sxs-lookup"><span data-stu-id="36380-168">Uses Group Policy Objects to enforce BitLocker drive encryption on client computers in the enterprise.</span></span>

-   <span data-ttu-id="36380-169">收集三種資料磁片磁碟機類型的 BitLocker 復原金鑰：操作系統磁碟機、固定資料磁碟機，以及可移動（USB）資料磁碟機。</span><span class="sxs-lookup"><span data-stu-id="36380-169">Collects the BitLocker recovery key for three data drive types: operating system drives, fixed data drives, and removable (USB) data drives.</span></span>

-   <span data-ttu-id="36380-170">收集用戶端電腦的恢復資訊和電腦資訊。</span><span class="sxs-lookup"><span data-stu-id="36380-170">Collects recovery information and computer information about the client computers.</span></span>

#### <span data-ttu-id="36380-171">Configuration Manager 用戶端</span><span class="sxs-lookup"><span data-stu-id="36380-171">Configuration Manager Client</span></span>

<span data-ttu-id="36380-172">**Configuration Manager 用戶端**可讓 configuration manager 收集用戶端電腦的硬體相容性資料，並報告合規性資訊。</span><span class="sxs-lookup"><span data-stu-id="36380-172">The **Configuration Manager Client** enables Configuration Manager to collect hardware compatibility data about the client computers and report compliance information.</span></span>

 

## <span data-ttu-id="36380-173">支援的 Configuration Manager 版本的 MBAM 部署差異</span><span class="sxs-lookup"><span data-stu-id="36380-173">Differences in MBAM deployment for supported Configuration Manager versions</span></span>


<span data-ttu-id="36380-174">當您使用 Configuration Manager 整合拓撲部署 MBAM 時，您可以在主要的網站伺服器上安裝 MBAM。</span><span class="sxs-lookup"><span data-stu-id="36380-174">When you deploy MBAM with the Configuration Manager Integration topology, you can install MBAM on a primary site server.</span></span> <span data-ttu-id="36380-175">不過，MBAM 安裝在系統 Center2012 Configuration Manager 和設定 Manager2007 中的運作方式會有所不同。</span><span class="sxs-lookup"><span data-stu-id="36380-175">However, the MBAM installation works differently for System Center2012 Configuration Manager and Configuration Manager2007.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="36380-176">Configuration Manager 版本</span><span class="sxs-lookup"><span data-stu-id="36380-176">Configuration Manager version</span></span></th>
<th align="left"><span data-ttu-id="36380-177">描述</span><span class="sxs-lookup"><span data-stu-id="36380-177">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="36380-178">System Center2012 R2 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="36380-178">System Center2012 R2 Configuration Manager</span></span></p>
<p><span data-ttu-id="36380-179">系統 Center2012 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="36380-179">System Center2012 Configuration Manager</span></span></p></td>
<td align="left"><p><span data-ttu-id="36380-180">如果您在主要的網站伺服器或中央管理伺服器上安裝 MBAM，MBAM 會在該網站伺服器上執行所有安裝動作。</span><span class="sxs-lookup"><span data-stu-id="36380-180">If you install MBAM on a primary site server or on a central administration server, MBAM performs all of the installation actions on that site server.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="36380-181">Configuration Manager2007 R2</span><span class="sxs-lookup"><span data-stu-id="36380-181">Configuration Manager2007 R2</span></span></p>
<p><span data-ttu-id="36380-182">配置 Manager2007</span><span class="sxs-lookup"><span data-stu-id="36380-182">Configuration Manager2007</span></span></p></td>
<td align="left"><p><span data-ttu-id="36380-183">如果您在擁有中央網站父伺服器的大型 Configuration Manager 階層的主要網站伺服器上安裝 MBAM，MBAM 會識別中央網站父伺服器，並在該父伺服器上執行所有安裝動作。</span><span class="sxs-lookup"><span data-stu-id="36380-183">If you install MBAM on a primary site server that is part of a larger Configuration Manager hierarchy with a central site parent server, MBAM identifies the central site parent server and performs all of the installation actions on that parent server.</span></span> <span data-ttu-id="36380-184">安裝包括檢查先決條件及安裝 Configuration Manager 物件和報告。</span><span class="sxs-lookup"><span data-stu-id="36380-184">The installation includes checking prerequisites and installing the Configuration Manager objects and reports.</span></span></p>
<p><span data-ttu-id="36380-185">例如，如果您在主要網站伺服器上安裝 MBAM，而該伺服器是中央網站父伺服器的子網站，MBAM 會在父伺服器上安裝所有 Configuration Manager 物件和報告。</span><span class="sxs-lookup"><span data-stu-id="36380-185">For example, if you install MBAM on a primary site server that is a child of a central site parent server, MBAM installs all of the Configuration Manager objects and reports on the parent server.</span></span> <span data-ttu-id="36380-186">如果您在父伺服器上安裝 MBAM，MBAM 會在該父伺服器上執行所有安裝動作。</span><span class="sxs-lookup"><span data-stu-id="36380-186">If you install MBAM on the parent server, MBAM performs all of the installation actions on that parent server.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="36380-187">MBAM 如何與 Configuration Manager 搭配運作</span><span class="sxs-lookup"><span data-stu-id="36380-187">How MBAM works with Configuration Manager</span></span>


<span data-ttu-id="36380-188">與 Configuration Manager 的 MBAM 整合是以安裝下表所述之專案的配置套件為基礎。</span><span class="sxs-lookup"><span data-stu-id="36380-188">The integration of MBAM with Configuration Manager is based on a configuration pack that installs the items described in the following table.</span></span>

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="36380-189">已安裝至 Configuration Manager 的專案</span><span class="sxs-lookup"><span data-stu-id="36380-189">Items installed into Configuration Manager</span></span></th>
<th align="left"><span data-ttu-id="36380-190">描述</span><span class="sxs-lookup"><span data-stu-id="36380-190">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="36380-191">配置資料</span><span class="sxs-lookup"><span data-stu-id="36380-191">Configuration data</span></span></p></td>
<td align="left"><p><span data-ttu-id="36380-192">配置資料會安裝名為「BitLocker Protection」的配置比較基準，其中包含兩個設定專案：</span><span class="sxs-lookup"><span data-stu-id="36380-192">The configuration data installs a configuration baseline, called “BitLocker Protection,” which contains two configuration items:</span></span></p>
<ul>
<li><p><span data-ttu-id="36380-193">BitLocker 作業系統磁片磁碟機保護</span><span class="sxs-lookup"><span data-stu-id="36380-193">BitLocker Operating System Drive Protection</span></span></p></li>
<li><p><span data-ttu-id="36380-194">BitLocker 固定資料磁碟機保護</span><span class="sxs-lookup"><span data-stu-id="36380-194">BitLocker Fixed Data Drives Protection</span></span></p></li>
</ul>
<p><span data-ttu-id="36380-195">配置基線會部署到 [支援的 MBAM 電腦] 集合，也會在安裝 MBAM 時建立。</span><span class="sxs-lookup"><span data-stu-id="36380-195">The configuration baseline is deployed to the MBAM Supported Computers collection, which is also created when MBAM is installed.</span></span></p>
<p><span data-ttu-id="36380-196">這兩個設定專案提供評估用戶端電腦合規性狀態的基礎。</span><span class="sxs-lookup"><span data-stu-id="36380-196">The two configuration items provide the basis for evaluating the compliance status of the client computers.</span></span> <span data-ttu-id="36380-197">此資訊是在 Configuration Manager 中捕獲、儲存及評估。</span><span class="sxs-lookup"><span data-stu-id="36380-197">This information is captured, stored, and evaluated in Configuration Manager.</span></span></p>
<p><span data-ttu-id="36380-198">設定專案是根據作業系統磁片磁碟機和固定資料磁碟機的規範需求而定。</span><span class="sxs-lookup"><span data-stu-id="36380-198">The configuration items are based on the compliance requirements for operating system drives and fixed data drives.</span></span> <span data-ttu-id="36380-199">系統會收集已部署電腦所需的詳細資料，以便評估這些磁碟機類型的合規性。</span><span class="sxs-lookup"><span data-stu-id="36380-199">The required details for the deployed computers are collected so that the compliance for those drive types can be evaluated.</span></span></p>
<p><span data-ttu-id="36380-200">根據預設，設定基準會評估合規性狀態 every12 時間，並將合規性資料傳送至 Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="36380-200">By default, the configuration baseline evaluates the compliance status every12 hours and sends the compliance data to Configuration Manager.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="36380-201">MBAM 支援的電腦集合</span><span class="sxs-lookup"><span data-stu-id="36380-201">MBAM Supported Computers collection</span></span></p></td>
<td align="left"><p><span data-ttu-id="36380-202">MBAM 會建立一個名為 MBAM 支援的電腦的集合。</span><span class="sxs-lookup"><span data-stu-id="36380-202">MBAM creates a collection that is called MBAM Supported Computers.</span></span> <span data-ttu-id="36380-203">配置基線是針對此集合中的用戶端電腦所設定。</span><span class="sxs-lookup"><span data-stu-id="36380-203">The configuration baseline is targeted to client computers that are in this collection.</span></span></p>
<p><span data-ttu-id="36380-204">這是動態集合。</span><span class="sxs-lookup"><span data-stu-id="36380-204">This is a dynamic collection.</span></span> <span data-ttu-id="36380-205">根據預設，它會根據三個準則來執行 every12 時間及評估成員資格：</span><span class="sxs-lookup"><span data-stu-id="36380-205">By default, it runs every12 hours and evaluates membership, based on three criteria:</span></span></p>
<ul>
<li><p><span data-ttu-id="36380-206">電腦是受支援版本的 Windows 作業系統。</span><span class="sxs-lookup"><span data-stu-id="36380-206">The computer is a supported version of the Windows operating system.</span></span></p></li>
<li><p><span data-ttu-id="36380-207">電腦是物理電腦。</span><span class="sxs-lookup"><span data-stu-id="36380-207">The computer is a physical computer.</span></span> <span data-ttu-id="36380-208">不支援虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="36380-208">Virtual machines are not supported.</span></span></p></li>
<li><p><span data-ttu-id="36380-209">電腦有可用的可信平臺模組（TPM）。</span><span class="sxs-lookup"><span data-stu-id="36380-209">The computer has a Trusted Platform Module (TPM) that is available.</span></span> <span data-ttu-id="36380-210">Windows7 需要相容版本的 TPM 1.2 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="36380-210">A compatible version of TPM1.2 or later is required for Windows7.</span></span> <span data-ttu-id="36380-211">Windows10、Windows 8.1、Windows8 和 Windows To Go 不需要 TPM。</span><span class="sxs-lookup"><span data-stu-id="36380-211">Windows10, Windows8.1, Windows8, and Windows To Go do not require a TPM.</span></span></p></li>
</ul>
<p><span data-ttu-id="36380-212">這個集合是針對所有電腦來評估，而且會建立相容電腦的子集，這為 MBAM 整合提供合規性評估與報告的基礎。</span><span class="sxs-lookup"><span data-stu-id="36380-212">The collection is evaluated against all computers and a subset of compatible computers is created, which provides the basis for compliance evaluation and reporting for the MBAM integration.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="36380-213">報告</span><span class="sxs-lookup"><span data-stu-id="36380-213">Reports</span></span></p></td>
<td align="left"><p><span data-ttu-id="36380-214">當您使用 Configuration Manager 整合拓朴設定 MBAM 時，您會在 Configuration Manager 中查看所有報表，除了復原審核報告之外，您還可以在 MBAM 管理和監視網站中繼續進行查看。</span><span class="sxs-lookup"><span data-stu-id="36380-214">When you configure MBAM with the Configuration Manager Integration topology, you view all reports in Configuration Manager, except the Recovery Audit Report, the latter of which you continue to view in the MBAM Administration and Monitoring Website.</span></span> <span data-ttu-id="36380-215">[Configuration Manager] 中提供的報表如下：</span><span class="sxs-lookup"><span data-stu-id="36380-215">The reports available in Configuration Manager are:</span></span></p>
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="36380-216">報告</span><span class="sxs-lookup"><span data-stu-id="36380-216">Report</span></span></th>
<th align="left"><span data-ttu-id="36380-217">描述</span><span class="sxs-lookup"><span data-stu-id="36380-217">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="36380-218">BitLocker Enterprise 合規性儀表板</span><span class="sxs-lookup"><span data-stu-id="36380-218">BitLocker Enterprise Compliance Dashboard</span></span></p></td>
<td align="left"><p><span data-ttu-id="36380-219">在單一報告中，為 IT 系統管理員提供三個資訊視圖：合規性狀態發佈、不合規性-錯誤發佈，以及依磁片磁碟機類型進行合規性狀態發佈。</span><span class="sxs-lookup"><span data-stu-id="36380-219">Gives IT administrators three views of information in a single report: Compliance Status Distribution, Non Compliant – Errors Distribution, and Compliance Status Distribution By Drive Type.</span></span> <span data-ttu-id="36380-220">報表中的向下切入選項可讓 IT 系統管理員依序按一下資料，並查看符合所選狀態的電腦清單。</span><span class="sxs-lookup"><span data-stu-id="36380-220">Drill-down options on the report let IT administrators click through the data and view a list of computers that match the selected state.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="36380-221">BitLocker 企業合規性詳細資料</span><span class="sxs-lookup"><span data-stu-id="36380-221">BitLocker Enterprise Compliance Details</span></span></p></td>
<td align="left"><p><span data-ttu-id="36380-222">讓 IT 系統管理員可以查看企業的 BitLocker 加密合規性狀態相關資訊，並包括每個電腦的相容性狀態。</span><span class="sxs-lookup"><span data-stu-id="36380-222">Lets IT administrators view information about the BitLocker encryption compliance status of the enterprise and includes the compliance status for each computer.</span></span> <span data-ttu-id="36380-223">報表中的向下切入選項可讓 IT 系統管理員依序按一下資料，並查看符合所選狀態的電腦清單。</span><span class="sxs-lookup"><span data-stu-id="36380-223">Drill-down options on the report let IT administrators click through the data and view a list of computers that match the selected state.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="36380-224">BitLocker 電腦合規性</span><span class="sxs-lookup"><span data-stu-id="36380-224">BitLocker Computer Compliance</span></span></p></td>
<td align="left"><p><span data-ttu-id="36380-225">讓 IT 系統管理員可以查看個別的電腦，並判斷為什麼報告的狀態符合合規性或不規範。</span><span class="sxs-lookup"><span data-stu-id="36380-225">Lets IT administrators view an individual computer and determine why it was reported with a status of compliant or not compliant.</span></span> <span data-ttu-id="36380-226">報告也會顯示操作系統磁碟機和固定資料磁碟機的加密狀態。</span><span class="sxs-lookup"><span data-stu-id="36380-226">The report also displays the encryption state of the operating system drives and fixed data drives.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="36380-227">BitLocker Enterprise 合規性摘要</span><span class="sxs-lookup"><span data-stu-id="36380-227">BitLocker Enterprise Compliance Summary</span></span></p></td>
<td align="left"><p><span data-ttu-id="36380-228">讓 IT 系統管理員在企業中查看 MBAM 原則規範的狀態。</span><span class="sxs-lookup"><span data-stu-id="36380-228">Lets IT administrators view the status of MBAM policy compliance in the enterprise.</span></span> <span data-ttu-id="36380-229">會評估每個電腦的狀態，而報告會顯示企業中所有電腦對原則的合規性摘要。</span><span class="sxs-lookup"><span data-stu-id="36380-229">Each computer’s state is evaluated, and the report shows a summary of the compliance of all computers in the enterprise against the policy.</span></span> <span data-ttu-id="36380-230">報表中的向下切入選項可讓 IT 系統管理員依序按一下資料，並查看符合所選狀態的電腦清單。</span><span class="sxs-lookup"><span data-stu-id="36380-230">Drill-down options on the report let IT administrators click through the data and view a list of computers that match the selected state.</span></span></p></td>
</tr>
</tbody>
</table>
<p> </p></td>
</tr>
</tbody>
</table>

 


## <span data-ttu-id="36380-231">相關主題</span><span class="sxs-lookup"><span data-stu-id="36380-231">Related topics</span></span>


[<span data-ttu-id="36380-232">開始使用 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="36380-232">Getting Started with MBAM 2.5</span></span>](getting-started-with-mbam-25.md)

[<span data-ttu-id="36380-233">MBAM 2.5 搭配獨立拓撲的概要架構</span><span class="sxs-lookup"><span data-stu-id="36380-233">High-Level Architecture of MBAM 2.5 with Stand-alone Topology</span></span>](high-level-architecture-of-mbam-25-with-stand-alone-topology.md)

[<span data-ttu-id="36380-234">MBAM 2.5 部署的功能圖例</span><span class="sxs-lookup"><span data-stu-id="36380-234">Illustrated Features of an MBAM 2.5 Deployment</span></span>](illustrated-features-of-an-mbam-25-deployment.md)

 

 
## <span data-ttu-id="36380-235">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="36380-235">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="36380-236">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="36380-236">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="36380-237">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="36380-237">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>




