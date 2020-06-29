---
title: 開始使用 - 將 MBAM 與設定管理員搭配使用
description: 開始使用 - 將 MBAM 與設定管理員搭配使用
author: dansimp
ms.assetid: b0a1d3cc-0b01-4b69-a2cd-fd09fb3beda4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 654de38918102a41395efe37dc593ce8f49113e4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810994"
---
# <span data-ttu-id="f2205-103">開始使用 - 將 MBAM 與設定管理員搭配使用</span><span class="sxs-lookup"><span data-stu-id="f2205-103">Getting Started - Using MBAM with Configuration Manager</span></span>


<span data-ttu-id="f2205-104">當您安裝 Microsoft BitLocker 管理和監控（MBAM）時，您可以選擇將 MBAM 與 Configuration Manager 2007 或 SystemCenter2012 ConfigurationManager 整合的拓撲。</span><span class="sxs-lookup"><span data-stu-id="f2205-104">When you install Microsoft BitLocker Administration and Monitoring (MBAM), you can choose a topology that integrates MBAM with Configuration Manager 2007 or SystemCenter2012 ConfigurationManager.</span></span> <span data-ttu-id="f2205-105">如需 MBAM 支援之支援版本 Configuration Manager 的清單，請參閱[規劃使用 Configuration Manager 部署 MBAM](planning-to-deploy-mbam-with-configuration-manager-2.md)。</span><span class="sxs-lookup"><span data-stu-id="f2205-105">For a list of the supported versions of Configuration Manager that MBAM supports, see [Planning to Deploy MBAM with Configuration Manager](planning-to-deploy-mbam-with-configuration-manager-2.md).</span></span> <span data-ttu-id="f2205-106">在整合拓朴中，會從 MBAM 中移除硬體合規性和報告功能，並從 Configuration Manager 存取。</span><span class="sxs-lookup"><span data-stu-id="f2205-106">In the integrated topology, the hardware compliance and reporting features are removed from MBAM and are accessed from Configuration Manager.</span></span>

<span data-ttu-id="f2205-107">**重要** 當您安裝 MBAM 與 Configuration Manager 2007 的整合拓撲時，系統不支援 Windows To Go。</span><span class="sxs-lookup"><span data-stu-id="f2205-107">**Important** Windows To Go is not supported when you install the integrated topology of MBAM with Configuration Manager 2007.</span></span>

 

## <span data-ttu-id="f2205-108">使用 MBAM 搭配 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f2205-108">Using MBAM with Configuration Manager</span></span>


<span data-ttu-id="f2205-109">MBAM 的整合是依據將下列三個專案安裝到 Configuration Manager 2007 或 SystemCenter2012 ConfigurationManager 的新配置套件所決定，以下各節將詳細說明這些專案：</span><span class="sxs-lookup"><span data-stu-id="f2205-109">The integration of MBAM is based on a new Configuration Pack that installs the following three items into Configuration Manager 2007 or SystemCenter2012 ConfigurationManager, which are described in detail in the following sections:</span></span>

<span data-ttu-id="f2205-110">由設定項目和配置比較基準組成的配置資料</span><span class="sxs-lookup"><span data-stu-id="f2205-110">Configuration data that consists of configuration items and a configuration baseline</span></span>

<span data-ttu-id="f2205-111">集合</span><span class="sxs-lookup"><span data-stu-id="f2205-111">Collection</span></span>

<span data-ttu-id="f2205-112">報告</span><span class="sxs-lookup"><span data-stu-id="f2205-112">Reports</span></span>

### <span data-ttu-id="f2205-113">配置資料</span><span class="sxs-lookup"><span data-stu-id="f2205-113">Configuration Data</span></span>

<span data-ttu-id="f2205-114">配置資料會安裝名為「BitLocker Protection」的設定比較基準，其中包含兩個設定專案：「BitLocker 作業系統磁片磁碟機保護」和「BitLocker 固定資料磁碟機保護」。</span><span class="sxs-lookup"><span data-stu-id="f2205-114">The configuration data installs a configuration baseline, called “BitLocker Protection,” which contains two configuration items: “BitLocker Operating System Drive Protection” and “BitLocker Fixed Data Drives Protection.”</span></span> <span data-ttu-id="f2205-115">配置基線會部署到集合，在安裝 MBAM 時也會建立該集合。</span><span class="sxs-lookup"><span data-stu-id="f2205-115">The configuration baseline is deployed to the collection, which is also created when MBAM is installed.</span></span> <span data-ttu-id="f2205-116">這兩個設定專案提供評估用戶端電腦合規性狀態的基礎。</span><span class="sxs-lookup"><span data-stu-id="f2205-116">The two configuration items provide the basis for evaluating the compliance status of the client computers.</span></span> <span data-ttu-id="f2205-117">此資訊是在 Configuration Manager 中捕獲、儲存及評估。</span><span class="sxs-lookup"><span data-stu-id="f2205-117">This information is captured, stored, and evaluated in Configuration Manager.</span></span> <span data-ttu-id="f2205-118">設定專案是根據作業系統磁片磁碟機（OSDs）和固定資料磁碟機（FDDs）的規範需求而定。</span><span class="sxs-lookup"><span data-stu-id="f2205-118">The configuration items are based on the compliance requirements for operating system drives (OSDs) and Fixed Data Drives (FDDs).</span></span> <span data-ttu-id="f2205-119">系統會收集已部署電腦所需的詳細資料，以便評估這些磁碟機類型的合規性。</span><span class="sxs-lookup"><span data-stu-id="f2205-119">The required details for the deployed computers are collected so that the compliance for those drive types can be evaluated.</span></span> <span data-ttu-id="f2205-120">根據預設，設定比較基準會每隔12小時評估合規性狀態，並將合規性資料傳送至 Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="f2205-120">By default, the configuration baseline evaluates the compliance status every 12 hours and sends the compliance data to Configuration Manager.</span></span>

### <span data-ttu-id="f2205-121">集合</span><span class="sxs-lookup"><span data-stu-id="f2205-121">Collection</span></span>

<span data-ttu-id="f2205-122">MBAM 會建立一個名為 MBAM 支援的電腦的集合。</span><span class="sxs-lookup"><span data-stu-id="f2205-122">MBAM creates a collection that is called MBAM Supported Computers.</span></span> <span data-ttu-id="f2205-123">配置基線是針對此集合中的用戶端電腦所設定。</span><span class="sxs-lookup"><span data-stu-id="f2205-123">The configuration baseline is targeted to client computers that are in this collection.</span></span> <span data-ttu-id="f2205-124">這是一種動態集合，預設會每12小時執行一次，並會評估成員資格。</span><span class="sxs-lookup"><span data-stu-id="f2205-124">This is a dynamic collection that, by default, runs every 12 hours and evaluates membership.</span></span> <span data-ttu-id="f2205-125">成員資格以三個準則為基礎：</span><span class="sxs-lookup"><span data-stu-id="f2205-125">Membership is based on three criteria:</span></span>

-   <span data-ttu-id="f2205-126">它是受支援版本的 Windows 作業系統。</span><span class="sxs-lookup"><span data-stu-id="f2205-126">It is a supported version of the Windows operating system.</span></span> <span data-ttu-id="f2205-127">目前，MBAM 只支援 Windows 7 企業版和 Windows 7 旗艦版、Windows 8 企業版和 Windows To Go，在 Windows 8 企業版上執行 Windows。</span><span class="sxs-lookup"><span data-stu-id="f2205-127">Currently, MBAM supports only Windows 7 Enterprise and Windows 7 Ultimate, Windows 8 Enterprise, and Windows To Go, when Windows To Go is running on Windows 8 Enterprise.</span></span>

-   <span data-ttu-id="f2205-128">它是物理電腦。</span><span class="sxs-lookup"><span data-stu-id="f2205-128">It is a physical computer.</span></span> <span data-ttu-id="f2205-129">不支援虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="f2205-129">Virtual machines are not supported.</span></span>

-   <span data-ttu-id="f2205-130">可使用受信任的平臺模組（TPM）。</span><span class="sxs-lookup"><span data-stu-id="f2205-130">Trusted Platform Module (TPM) is available.</span></span> <span data-ttu-id="f2205-131">Windows 7 需要相容版本的 TPM 1.2 或更新版本。</span><span class="sxs-lookup"><span data-stu-id="f2205-131">A compatible version of TPM 1.2 or later is required for Windows 7.</span></span> <span data-ttu-id="f2205-132">Windows 8 和 Windows To Go 不需要 TPM。</span><span class="sxs-lookup"><span data-stu-id="f2205-132">Windows 8 and Windows To Go do not require a TPM.</span></span>

<span data-ttu-id="f2205-133">針對所有電腦評估集合，並建立相容電腦的子集，為 MBAM 整合提供合規性評估與報告的基礎。</span><span class="sxs-lookup"><span data-stu-id="f2205-133">The collection is evaluated against all computers and creates the subset of compatible computers that provides the basis for compliance evaluation and reporting for the MBAM integration.</span></span>

### <span data-ttu-id="f2205-134">報告</span><span class="sxs-lookup"><span data-stu-id="f2205-134">Reports</span></span>

<span data-ttu-id="f2205-135">您可以使用四種報告來查看合規性。</span><span class="sxs-lookup"><span data-stu-id="f2205-135">There are four reports that you can use to view compliance.</span></span> <span data-ttu-id="f2205-136">這些類型包括：</span><span class="sxs-lookup"><span data-stu-id="f2205-136">They are:</span></span>

-   <span data-ttu-id="f2205-137">**BitLocker Enterprise 合規性儀表板**-可讓 IT 系統管理員在單一報告上提供三種不同的資訊視圖：合規性狀態發佈、不相容–錯誤發佈，以及依磁片磁碟機類型進行合規性狀態發佈。</span><span class="sxs-lookup"><span data-stu-id="f2205-137">**BitLocker Enterprise Compliance Dashboard** – gives IT administrators three different views of information on a single report: Compliance Status Distribution, Non Compliant – Errors Distribution, and Compliance Status Distribution By Drive Type.</span></span> <span data-ttu-id="f2205-138">報表中的向下切入選項可讓 IT 系統管理員依序按一下資料，並查看符合您所選狀態的電腦清單。</span><span class="sxs-lookup"><span data-stu-id="f2205-138">Drill-down options on the report let IT administrators click through the data and view a list of computers that match the state that you select.</span></span>

-   <span data-ttu-id="f2205-139">**BitLocker Enterprise 合規性詳細資料**：讓 IT 系統管理員可以查看企業的 BitLocker 加密合規性狀態相關資訊，並包括每個電腦的相容性狀態。</span><span class="sxs-lookup"><span data-stu-id="f2205-139">**BitLocker Enterprise Compliance Details** – lets IT administrators view information about the BitLocker encryption compliance status of the enterprise and includes the compliance status for each computer.</span></span> <span data-ttu-id="f2205-140">報表中的向下切入選項可讓 IT 系統管理員依序按一下資料，並查看符合您所選狀態的電腦清單。</span><span class="sxs-lookup"><span data-stu-id="f2205-140">Drill-down options on the report let IT administrators click through the data and view a list of computers that match the state that you select.</span></span>

-   <span data-ttu-id="f2205-141">**BitLocker 電腦合規性**-可讓 IT 系統管理員查看個別的電腦，並判斷它為什麼會以符合或不符合規範的特定狀態報表。</span><span class="sxs-lookup"><span data-stu-id="f2205-141">**BitLocker Computer Compliance** – lets IT administrators view an individual computer and determine why it was reported with a given status of compliant or not compliant.</span></span> <span data-ttu-id="f2205-142">報告也會顯示作業系統磁片磁碟機（OSD）和固定資料磁碟機（FDDs）的加密狀態。</span><span class="sxs-lookup"><span data-stu-id="f2205-142">The report also displays the encryption state of the operating system drives (OSD) and fixed data drives (FDDs).</span></span>

-   <span data-ttu-id="f2205-143">**BitLocker Enterprise 合規性摘要**：可讓 IT 系統管理員透過 MBAM 原則來查看企業合規性的狀態。</span><span class="sxs-lookup"><span data-stu-id="f2205-143">**BitLocker Enterprise Compliance Summary** – lets IT administrators view the status of the compliance of the enterprise with MBAM policy.</span></span> <span data-ttu-id="f2205-144">會評估每個電腦的狀態，而報告會顯示企業中所有電腦對原則的合規性摘要。</span><span class="sxs-lookup"><span data-stu-id="f2205-144">Each computer’s state is evaluated, and the report shows a summary of the compliance of all computers in the enterprise against the policy.</span></span> <span data-ttu-id="f2205-145">報表中的向下切入選項可讓 IT 系統管理員依序按一下資料，並查看符合您所選狀態的電腦清單。</span><span class="sxs-lookup"><span data-stu-id="f2205-145">Drill-down options on the report let IT administrators click through the data and view a list of computers that match the state that you select.</span></span>

## <span data-ttu-id="f2205-146">含 Configuration Manager 之 MBAM 的高層次架構</span><span class="sxs-lookup"><span data-stu-id="f2205-146">High-Level Architecture of MBAM with Configuration Manager</span></span>


<span data-ttu-id="f2205-147">下圖顯示具有 Configuration Manager 拓撲的 MBAM 結構。</span><span class="sxs-lookup"><span data-stu-id="f2205-147">The following image shows the MBAM architecture with the Configuration Manager topology.</span></span> <span data-ttu-id="f2205-148">此設定在生產環境中最多可支援 200000 MBAM 用戶端。</span><span class="sxs-lookup"><span data-stu-id="f2205-148">This configuration supports up to 200,000 MBAM clients in a production environment.</span></span>

![含 configuration manager 的 mbam 架構](images/mbam2-cmserver.gif)

<span data-ttu-id="f2205-150">此架構的伺服器、資料庫和功能說明如下。</span><span class="sxs-lookup"><span data-stu-id="f2205-150">A description of the servers, databases, and features of this architecture follows.</span></span> <span data-ttu-id="f2205-151">體系結構中的伺服器功能和資料庫會列在電腦或伺服器下，我們建議您安裝它們。</span><span class="sxs-lookup"><span data-stu-id="f2205-151">The server features and databases in the architecture image are listed under the computer or server where we recommend that you install them.</span></span>

-   <span data-ttu-id="f2205-152">**資料庫伺服器**–復原**資料庫**、**審核資料庫**及**審核報告**都安裝在 Windows Server 和支援的 SQLServer 實例上。</span><span class="sxs-lookup"><span data-stu-id="f2205-152">**Database Server** – The **Recovery Database**, **Audit Database**, and **Audit Reports** are installed on a Windows server and supported SQLServer instance.</span></span> <span data-ttu-id="f2205-153">復原資料庫會儲存從 MBAM 用戶端電腦收集的復原資料。</span><span class="sxs-lookup"><span data-stu-id="f2205-153">The Recovery database stores recovery data that is collected from MBAM client computers.</span></span> <span data-ttu-id="f2205-154">審核資料庫會儲存從已存取復原資料的用戶端電腦收集的審核活動資料。</span><span class="sxs-lookup"><span data-stu-id="f2205-154">The Audit Database stores audit activity data that is collected from client computers that have accessed recovery data.</span></span> <span data-ttu-id="f2205-155">審計報告提供企業中用戶端電腦合規性狀態的相關資料。</span><span class="sxs-lookup"><span data-stu-id="f2205-155">The Audit Reports provide data about the compliance status of client computers in your enterprise.</span></span>

-   <span data-ttu-id="f2205-156">**Configuration Manager 主要網站伺服器**： Configuration manager 伺服器包含含 System Center Configuration Manager 整合拓撲的 MBAM 伺服器安裝，必須安裝在 Configuration Manager 主要網站伺服器上。</span><span class="sxs-lookup"><span data-stu-id="f2205-156">**Configuration Manager Primary Site Server** – The Configuration Manager Server contains of the MBAM server installation with the System Center Configuration Manager Integration topology, which must be installed on a Configuration Manager primary site server.</span></span> <span data-ttu-id="f2205-157">Configuration Manager 伺服器會從用戶端電腦收集硬體清查資訊，並使用它來報告用戶端電腦的 BitLocker 合規性。</span><span class="sxs-lookup"><span data-stu-id="f2205-157">The Configuration Manager Server collects the hardware inventory information from client computers and is used to report BitLocker compliance of client computers.</span></span> <span data-ttu-id="f2205-158">當您執行 MBAM 安裝伺服器安裝時，系統會在 Configuration Manager 主要網站伺服器上安裝集合和設定資料。</span><span class="sxs-lookup"><span data-stu-id="f2205-158">When you run the MBAM Setup server installation, a collection and the configuration data are installed on the Configuration Manager Primary Site Server.</span></span>

-   <span data-ttu-id="f2205-159">**管理和監控伺服器**-系統會在 Windows Server 上安裝 [**管理與監控伺服器**]，並由 [管理與監控] 網站和 [監視] web 服務組成。</span><span class="sxs-lookup"><span data-stu-id="f2205-159">**Administration and Monitoring Server** - The **Administration and Monitoring Server** is installed on a Windows server and consists of the Administration and Monitoring website and the monitoring web services.</span></span> <span data-ttu-id="f2205-160">管理和監控網站是用來審核活動，以及存取復原資料（例如，BitLocker 復原金鑰）。</span><span class="sxs-lookup"><span data-stu-id="f2205-160">The Administration and Monitoring website is used to audit activity and to access recovery data (for example, BitLocker recovery keys).</span></span> <span data-ttu-id="f2205-161">[**自助式入口網站**] 也會安裝在 [管理] 和 [監視伺服器] 上。</span><span class="sxs-lookup"><span data-stu-id="f2205-161">The **Self-Service Portal** is also installed on the Administration and Monitoring Server.</span></span> <span data-ttu-id="f2205-162">入口網站可讓用戶端電腦上的使用者能夠獨立登錄至網站，以取得復原金鑰（如果他們遺失或忘記其 BitLocker 密碼）。</span><span class="sxs-lookup"><span data-stu-id="f2205-162">The Portal enables end users on client computers to independently log onto a website to get a recovery key if they lose or forget their BitLocker password.</span></span> <span data-ttu-id="f2205-163">審計報告也會安裝在 [管理和監控伺服器] 上。</span><span class="sxs-lookup"><span data-stu-id="f2205-163">The Audit reports are also installed on the Administration and Monitoring Server.</span></span>

-   <span data-ttu-id="f2205-164">**管理工作站**-**原則範本**是由定義 BitLocker 磁片磁碟機加密之 MBAM 實現設定的群組原則物件所組成。</span><span class="sxs-lookup"><span data-stu-id="f2205-164">**Management Workstation** - The **Policy Template** consists of Group Policy Objects that define MBAM implementation settings for BitLocker drive encryption.</span></span> <span data-ttu-id="f2205-165">您可以在任何伺服器或工作站上安裝此原則範本，但通常會將它安裝在支援 Windows server 或用戶端電腦的管理工作站上。</span><span class="sxs-lookup"><span data-stu-id="f2205-165">You can install the Policy template on any server or workstation, but it is commonly installed on a management workstation that is a supported Windows server or client computer.</span></span> <span data-ttu-id="f2205-166">工作站不一定是專用電腦。</span><span class="sxs-lookup"><span data-stu-id="f2205-166">The workstation does not have to be a dedicated computer.</span></span>

-   <span data-ttu-id="f2205-167">**MBAM 用戶端**與**Configuration Manager 用戶端**電腦</span><span class="sxs-lookup"><span data-stu-id="f2205-167">**MBAM Client** and **Configuration Manager Client** computer</span></span>

    -   <span data-ttu-id="f2205-168">**MBAM 用戶端**會執行下列任務：</span><span class="sxs-lookup"><span data-stu-id="f2205-168">The **MBAM Client** performs the following tasks:</span></span>

        -   <span data-ttu-id="f2205-169">使用群組原則物件來強制執行企業用戶端電腦的 BitLocker 加密。</span><span class="sxs-lookup"><span data-stu-id="f2205-169">Uses Group Policy Objects to enforce the BitLocker encryption of client computers in the enterprise.</span></span>

        -   <span data-ttu-id="f2205-170">收集三個 BitLocker 資料磁片磁碟機類型的復原金鑰：操作系統磁碟機、固定資料磁碟機，以及可移動資料（USB）硬碟。</span><span class="sxs-lookup"><span data-stu-id="f2205-170">Collects the recovery key for the three BitLocker data drive types: operating system drives, fixed data drives, and removable data (USB) drives.</span></span>

        -   <span data-ttu-id="f2205-171">收集用戶端電腦的恢復資訊和電腦資訊。</span><span class="sxs-lookup"><span data-stu-id="f2205-171">Collects recovery information and computer information about the client computers.</span></span>

    -   <span data-ttu-id="f2205-172">**Configuration Manager 用戶端**-configuration manager 用戶端可讓 configuration manager 收集用戶端電腦的硬體相容性資料，並讓 configuration manager 報告合規性資訊。</span><span class="sxs-lookup"><span data-stu-id="f2205-172">**Configuration Manager Client** – The Configuration Manager client enables Configuration Manager to collect hardware compatibility data about the client computers, and enables Configuration Manager to report compliance information.</span></span>

## <span data-ttu-id="f2205-173">相關主題</span><span class="sxs-lookup"><span data-stu-id="f2205-173">Related topics</span></span>


[<span data-ttu-id="f2205-174">使用 MBAM 搭配 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="f2205-174">Using MBAM with Configuration Manager</span></span>](using-mbam-with-configuration-manager.md)

 

 





