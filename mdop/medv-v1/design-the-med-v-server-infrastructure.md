---
title: 設計 MED-V 伺服器基礎結構
description: 設計 MED-V 伺服器基礎結構
author: dansimp
ms.assetid: 2781040f-880e-4e16-945d-a38c0adb4151
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 4ba4c38328c5484b7daa292f9fc33a4e59824327
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810401"
---
# <span data-ttu-id="8f288-103">設計 MED-V 伺服器基礎結構</span><span class="sxs-lookup"><span data-stu-id="8f288-103">Design the MED-V Server Infrastructure</span></span>


<span data-ttu-id="8f288-104">在本主題中，您將針對每個 MED-V 實例設計伺服器基礎結構。</span><span class="sxs-lookup"><span data-stu-id="8f288-104">In this topic, you will design the server infrastructure for each MED-V instance.</span></span> <span data-ttu-id="8f288-105">這包括判斷 SQL Server 實例是否會存在於 MED-V 伺服器或遠端伺服器上，以及 SQL Server 資料庫的大小。</span><span class="sxs-lookup"><span data-stu-id="8f288-105">This includes determining whether the SQL Server instance will exist on the MED-V server or on a remote server, as well as the size of the SQL Server database.</span></span> <span data-ttu-id="8f288-106">您也將決定管理主控台的位置。</span><span class="sxs-lookup"><span data-stu-id="8f288-106">You will also determine the location of the management console.</span></span>

## <span data-ttu-id="8f288-107">針對每個 MED-V 實例設計並放置伺服器</span><span class="sxs-lookup"><span data-stu-id="8f288-107">Design and Place the Server for Each MED-V Instance</span></span>


<span data-ttu-id="8f288-108">MED-V 伺服器會實施原則，並儲存其用戶端的狀態與記錄資料。</span><span class="sxs-lookup"><span data-stu-id="8f288-108">The MED-V server implements policies and stores state and history data about its clients.</span></span>

### <span data-ttu-id="8f288-109">外形規格</span><span class="sxs-lookup"><span data-stu-id="8f288-109">Form Factor</span></span>

<span data-ttu-id="8f288-110">MED-V 建議您使用 2.8 GHz 的雙核 CPU 伺服器（2GB） RAM。</span><span class="sxs-lookup"><span data-stu-id="8f288-110">MED-V recommends using a 2.8-GHz dual core CPU server with 2GB of RAM.</span></span> <span data-ttu-id="8f288-111">這個建議是依據假設 MED-V 伺服器將在專用電腦上執行，而該 SQL Server 和 MED-V 管理主控台會在不同的電腦上執行。</span><span class="sxs-lookup"><span data-stu-id="8f288-111">This recommendation is based on the assumption that the MED-V server will run on a dedicated machine and that SQL Server and the MED-V management console will run on separate machines.</span></span>

<span data-ttu-id="8f288-112">考慮到這種工作負荷，MED-V 伺服器應該相對輕微地載入。</span><span class="sxs-lookup"><span data-stu-id="8f288-112">Given this workload, the MED-V server should be relatively lightly loaded.</span></span> <span data-ttu-id="8f288-113">在伺服器外形規格沒有特定的體系結構指導方針的情況下，使用 MED-V 建議（含與組織標準規格相符的記憶體）設計伺服器。</span><span class="sxs-lookup"><span data-stu-id="8f288-113">In the absence of specific architectural guidance on the server form factor, design the server using the MED-V recommendation, with memory that matches the organization’s standard form factor.</span></span> <span data-ttu-id="8f288-114">MED-V 伺服器可以在 Windows Server2008 上的虛擬電腦（VM）上執行，即 Hyper-v。</span><span class="sxs-lookup"><span data-stu-id="8f288-114">The MED-V server can be run on a virtual machine (VM) on Windows Server2008 Hyper-V.</span></span> <span data-ttu-id="8f288-115">如果將使用 VM，請確定它有權存取與針對物理電腦所指定的 CPU 和記憶體資源。</span><span class="sxs-lookup"><span data-stu-id="8f288-115">If a VM will be used, ensure that it has access to CPU and memory resources equivalent to those specified for a physical machine.</span></span>

<span data-ttu-id="8f288-116">MED-V 伺服器所需的磁片容量必須足以儲存 MED-V 工作區設定檔。</span><span class="sxs-lookup"><span data-stu-id="8f288-116">The disk capacity the MED-V server requires must be sufficient to store the MED-V workspace configuration files.</span></span> <span data-ttu-id="8f288-117">MED-V 工作區只能針對一或多位使用者使用一個 VM 和一個原則。</span><span class="sxs-lookup"><span data-stu-id="8f288-117">A MED-V workspace can only use one VM, and one policy, for one or more users.</span></span> <span data-ttu-id="8f288-118">因此，必須儲存的 MED-V 工作區數量取決於相同 VM 的不同使用者所需的不同原則，以及要使用的虛擬機器數量的程度。</span><span class="sxs-lookup"><span data-stu-id="8f288-118">Therefore, the number of MED-V workspaces that must be stored depends on the degree to which different policies are required for different users of the same VM, as well as the number of VMs that will be used.</span></span> <span data-ttu-id="8f288-119">MED-V 工作區 XML 檔案的大小會與典型的 MED-V 工作區30KB。</span><span class="sxs-lookup"><span data-stu-id="8f288-119">The MED-V workspace XML files are around 30KB in size for a typical MED-V workspace.</span></span> <span data-ttu-id="8f288-120">若要判斷所需的磁片容量，請將 30 KB 乘以 MED-V 伺服器將儲存的 MED-V 工作區數。</span><span class="sxs-lookup"><span data-stu-id="8f288-120">To determine the required disk capacity, multiply 30 KB by the number of MED-V workspaces that the MED-V server will store.</span></span>

<span data-ttu-id="8f288-121">MED-V 伺服器最重要的網路連線是其用戶端的連結，因此請將伺服器放在可提供最可用頻寬和其用戶端最穩定連結的網路位置。</span><span class="sxs-lookup"><span data-stu-id="8f288-121">The MED-V server’s most important network connections are the links to its clients, therefore place the server in a network location that provides the most available bandwidth and the most robust links to its clients.</span></span>

### <span data-ttu-id="8f288-122">容錯</span><span class="sxs-lookup"><span data-stu-id="8f288-122">Fault Tolerance</span></span>

<span data-ttu-id="8f288-123">在 MED-V 實例中，只能有一個作用中的 MED-V 伺服器，而 MED-V 不包含將伺服器放在 Microsoft 叢集服務器（MSCS）群集中以提供容錯的標準功能。</span><span class="sxs-lookup"><span data-stu-id="8f288-123">There can only be one active MED-V server in a MED-V instance, and MED-V does not include standard capabilities to place the server in a Microsoft Cluster Server (MSCS) cluster to provide fault tolerance.</span></span> <span data-ttu-id="8f288-124">被動備份伺服器可以手動設定。</span><span class="sxs-lookup"><span data-stu-id="8f288-124">A passive backup server can be manually configured.</span></span>

<span data-ttu-id="8f288-125">若要決定是否應該針對 MED-V 實例手動設定被動式備份伺服器，請判斷是否允許使用者在離線模式中使用 MED-V 影像。</span><span class="sxs-lookup"><span data-stu-id="8f288-125">To decide whether a passive backup server should be manually configured for the MED-V instance, determine whether users will be permitted to use the MED-V images in offline mode.</span></span> <span data-ttu-id="8f288-126">如需離線模式的詳細資訊，請參閱[如何設定網域使用者或群組](how-to-configure-a-domain-user-or-groupmedvv2.md)。</span><span class="sxs-lookup"><span data-stu-id="8f288-126">For information on offline mode, see [How to Configure a Domain User or Group](how-to-configure-a-domain-user-or-groupmedvv2.md).</span></span> <span data-ttu-id="8f288-127">如果不允許使用者離線工作，即使已在用戶端上啟動 MED-V 工作區，也無法繼續在 MED-V 伺服器失敗的事件中運作。</span><span class="sxs-lookup"><span data-stu-id="8f288-127">If users are not allowed to work offline, they will be unable to continue working in the event of a MED-V server failure, even if the MED-V workspace has already been started on the client.</span></span> <span data-ttu-id="8f288-128">如果允許離線工作，請針對每個 MED-V 工作區，決定用戶端在必須進行驗證之前離線工作的時間。</span><span class="sxs-lookup"><span data-stu-id="8f288-128">If offline work is permitted, for each MED-V workspace, determine how long the client is allowed to work offline before it must authenticate.</span></span> <span data-ttu-id="8f288-129">這是伺服器無法使用的最大時間長度。</span><span class="sxs-lookup"><span data-stu-id="8f288-129">This is the maximum amount of time that the server can be unavailable.</span></span>

## <span data-ttu-id="8f288-130">設計並放置 SQL Server 資料庫</span><span class="sxs-lookup"><span data-stu-id="8f288-130">Design and Place the SQL Server Database</span></span>


<span data-ttu-id="8f288-131">MED-V 伺服器會使用 SQL Server 資料庫來儲存用戶端狀態及事件。</span><span class="sxs-lookup"><span data-stu-id="8f288-131">The MED-V server uses the SQL Server database to store client status and events.</span></span> <span data-ttu-id="8f288-132">您可以在與 MED-V 伺服器相同的電腦上安裝 SQL Server 資料庫，也可以將它放在執行 SQL Server 的個別伺服器上（選擇性是 [遠端]）。</span><span class="sxs-lookup"><span data-stu-id="8f288-132">You can install the SQL Server database on the same machine as the MED-V server or you can place it on a separate server running SQL Server, which can optionally be remote.</span></span> <span data-ttu-id="8f288-133">您可以與其他 MED-V 實例共用資料庫，在這種情況下，來自這些實例的事件和警報會儲存在相同的資料庫中，而報告將包含來自所有實例的事件。</span><span class="sxs-lookup"><span data-stu-id="8f288-133">You can share the database with other MED-V instances, in which case events and alerts from those instances will be stored in the same database, and reports will include events from all instances.</span></span> <span data-ttu-id="8f288-134">您可以在現有的 SQL Server 實例中安裝資料庫，而其他 MED-V 伺服器的資料庫可以駐留在該實例中。</span><span class="sxs-lookup"><span data-stu-id="8f288-134">You can install the database in an existing SQL Server instance, and the databases of other MED-V servers can reside in that same instance.</span></span>

<span data-ttu-id="8f288-135">如果您將資料庫伺服器放在一個從 MED-V 伺服器遠端的位置，且在沒有足夠頻寬可用的網路連結中，報告可能會在主機中載入緩慢，而且可能不會顯示來自用戶端的最新資料。</span><span class="sxs-lookup"><span data-stu-id="8f288-135">If you place the database server in a location that is remote from the MED-V server, across networks links that do not have sufficient bandwidth available, reports may be slow to load in the console and may not display the latest data from clients.</span></span> <span data-ttu-id="8f288-136">請參閱您在[定義專案範圍](define-the-project-scope.md)中所決定的組織服務層級預期，並使用該資訊來決定放置 SQL Server 資料庫的位置。</span><span class="sxs-lookup"><span data-stu-id="8f288-136">Refer to the organization service level expectations that you determined in [Define the Project Scope](define-the-project-scope.md) and use that information to decide where to place the SQL Server database.</span></span>

### <span data-ttu-id="8f288-137">外形規格</span><span class="sxs-lookup"><span data-stu-id="8f288-137">Form Factor</span></span>

<span data-ttu-id="8f288-138">如果您將在與 MED-V 相同的伺服器上執行 SQL Server，且如果 SQL Server 只是用來儲存該伺服器的資料，請從 MED-V 建議開始，並為 SQL Server load 新增資源。</span><span class="sxs-lookup"><span data-stu-id="8f288-138">If you will run SQL Server on the same server as MED-V, and if SQL Server will only be used to store data for that server, start with the MED-V recommendation and add resources for the SQL Server load.</span></span> <span data-ttu-id="8f288-139">如果 SQL Server 要儲存來自多個 MED-V 實例的事件與警報，請參閱[基礎結構規劃與設計 MICROSOFT SQL Server 2008](https://go.microsoft.com/fwlink/?LinkId=163302)指南（HTTP://go.microsoft.com/fwlink/?LinkId=163302）。</span><span class="sxs-lookup"><span data-stu-id="8f288-139">If SQL Server will store events and alerts from more than one MED-V instance, for information on how to scale up the server form factor, see the [Infrastructure Planning and Design Microsoft SQL Server 2008](https://go.microsoft.com/fwlink/?LinkId=163302) guide (http:// go.microsoft.com/fwlink/?LinkId=163302).</span></span>

<span data-ttu-id="8f288-140">資料庫的大小取決於資料庫將儲存的用戶端事件數量。</span><span class="sxs-lookup"><span data-stu-id="8f288-140">The size of the database depends on the number of client events that the database will store.</span></span> <span data-ttu-id="8f288-141">事件是由用戶端的一般操作（例如，啟動 MED-V 工作區時，或在 MED-V 工作區中發生錯誤時）建立。</span><span class="sxs-lookup"><span data-stu-id="8f288-141">Events are created by normal operation of the client, such as when a MED-V workspace is started, or when there is an error in the MED-V workspace.</span></span> <span data-ttu-id="8f288-142">用戶端傳送事件的預設間隔是1分鐘。</span><span class="sxs-lookup"><span data-stu-id="8f288-142">The default interval at which the client sends events is 1 minute.</span></span>

<span data-ttu-id="8f288-143">若要估計資料庫的大小，請判斷下列事項：</span><span class="sxs-lookup"><span data-stu-id="8f288-143">To estimate the size of the database, determine the following:</span></span>

-   <span data-ttu-id="8f288-144">MED-V 實例中的用戶端數量。</span><span class="sxs-lookup"><span data-stu-id="8f288-144">Number of clients in the MED-V instance.</span></span> <span data-ttu-id="8f288-145">最大值為5000。</span><span class="sxs-lookup"><span data-stu-id="8f288-145">The maximum is 5,000.</span></span>

-   <span data-ttu-id="8f288-146">典型的事件到達速度。</span><span class="sxs-lookup"><span data-stu-id="8f288-146">Typical event arrival rate.</span></span> <span data-ttu-id="8f288-147">這個速度取決於用戶端使用方式的行為，但每個用戶端每天大約有15到20個事件。</span><span class="sxs-lookup"><span data-stu-id="8f288-147">This rate depends on client usage behavior but is approximately 15 to 20 events per day per client.</span></span>

-   <span data-ttu-id="8f288-148">事件大小。</span><span class="sxs-lookup"><span data-stu-id="8f288-148">Event size.</span></span> <span data-ttu-id="8f288-149">此大小通常大約200個位元組。</span><span class="sxs-lookup"><span data-stu-id="8f288-149">The size is typically around 200 bytes.</span></span>

-   <span data-ttu-id="8f288-150">儲存空間量。</span><span class="sxs-lookup"><span data-stu-id="8f288-150">Storage amount.</span></span> <span data-ttu-id="8f288-151">要儲存事件的天數。</span><span class="sxs-lookup"><span data-stu-id="8f288-151">The number of days for which events will be stored.</span></span>

<span data-ttu-id="8f288-152">將這些值相乘，以位元組為單位計算所需的資料儲存大小，然後在下列專案中新增安全要素：</span><span class="sxs-lookup"><span data-stu-id="8f288-152">Multiply these values together to calculate the size of the required data storage in bytes, and then add a safety factor to account for the following:</span></span>

-   <span data-ttu-id="8f288-153">錯誤，這可能會在短時間內從用戶端建立大量事件。</span><span class="sxs-lookup"><span data-stu-id="8f288-153">Errors, which could create a large number of events from a client in a short period of time.</span></span>

-   <span data-ttu-id="8f288-154">資料庫資料表和組織空間。</span><span class="sxs-lookup"><span data-stu-id="8f288-154">Database table and organizational space.</span></span>

<span data-ttu-id="8f288-155">若要估計每秒基礎結構優化（IOPs）需求，請使用上述值，將一般事件到貨率乘以實例中的用戶端數。</span><span class="sxs-lookup"><span data-stu-id="8f288-155">To approximate the infrastructure optimization per second (IOPs) requirement, use the above values, multiplying the typical event arrival rate by the number of clients in the instance.</span></span> <span data-ttu-id="8f288-156">這會產生每天可以撰寫的記錄數。</span><span class="sxs-lookup"><span data-stu-id="8f288-156">This yields the number of records that can be written per day.</span></span> <span data-ttu-id="8f288-157">將該數除以86400，以衍生每秒寫入的記錄數。</span><span class="sxs-lookup"><span data-stu-id="8f288-157">Divide that number by 86,400 to derive the number of records written per second.</span></span> <span data-ttu-id="8f288-158">如果可以使用單一基礎結構優化（IO）作業 equated 寫入操作，這個數位就是所需的寫入 IOPs。</span><span class="sxs-lookup"><span data-stu-id="8f288-158">If a write operations can be equated with a single infrastructure optimization (IO) operation, this number is the write IOPs required.</span></span> <span data-ttu-id="8f288-159">在報告活動時新增緩衝區。</span><span class="sxs-lookup"><span data-stu-id="8f288-159">Add a buffer to that for reporting activity.</span></span> <span data-ttu-id="8f288-160">這是難以判斷的，但視與實例搭配使用的主控台數量以及它們用於產生報告的頻率而定。</span><span class="sxs-lookup"><span data-stu-id="8f288-160">This is difficult to determine but depends on the number of consoles in use with the instance and the frequency with which they are used to generate reports.</span></span>

### <span data-ttu-id="8f288-161">容錯</span><span class="sxs-lookup"><span data-stu-id="8f288-161">Fault Tolerance</span></span>

<span data-ttu-id="8f288-162">當 MED-V 用戶端正在執行時，如果伺服器無法使用，系統就會在用戶端上備份事件，而且管理主控台將無法使用報告。</span><span class="sxs-lookup"><span data-stu-id="8f288-162">When MED-V client is running, if the server is unavailable, events will be backed up on the client and reports will be unavailable in the management console.</span></span> <span data-ttu-id="8f288-163">請參閱[定義專案範圍](define-the-project-scope.md)來決定是否需要容錯 SQL Server 基礎結構的設計，以確定組織的服務等級預期。</span><span class="sxs-lookup"><span data-stu-id="8f288-163">Refer to the organization’s service level expectations determined in [Define the Project Scope](define-the-project-scope.md) to decide whether the design of a fault-tolerant SQL Server infrastructure is necessary.</span></span>

<span data-ttu-id="8f288-164">MED-V 不提供在 MSCS 群集中運行 SQL Server 的支援。</span><span class="sxs-lookup"><span data-stu-id="8f288-164">MED-V does not provide support for running SQL Server in an MSCS cluster.</span></span> <span data-ttu-id="8f288-165">為了提供熱備用，並避免發生失敗的資料遺失，您可以將 SQL Server 放在記錄傳送設定中。</span><span class="sxs-lookup"><span data-stu-id="8f288-165">In order to provide warm standby and to avoid data loss in the event of a failure, you can place SQL Server in a log shipping configuration.</span></span> <span data-ttu-id="8f288-166">如需有關記錄傳送的詳細資訊，請參閱[基礎結構規劃與設計 MICROSOFT SQL Server 2008](https://go.microsoft.com/fwlink/?LinkId=163302)指南（ https://go.microsoft.com/fwlink/?LinkId=163302) 。</span><span class="sxs-lookup"><span data-stu-id="8f288-166">For information on log shipping, see the [Infrastructure Planning and Design Microsoft SQL Server 2008](https://go.microsoft.com/fwlink/?LinkId=163302) guide (https://go.microsoft.com/fwlink/?LinkId=163302).</span></span>

## <span data-ttu-id="8f288-167">設計管理主控台</span><span class="sxs-lookup"><span data-stu-id="8f288-167">Design the Management Console</span></span>


<span data-ttu-id="8f288-168">MED-V 管理主控台的其中一部分功能是先測試 Vm，然後再將其打包以發佈到 MED-V 用戶端。</span><span class="sxs-lookup"><span data-stu-id="8f288-168">Part of the functionality of the MED-V management console is to test VMs before they are packed for distribution to MED-V clients.</span></span> <span data-ttu-id="8f288-169">因此，管理主控台的設計方式應該與典型的 MED-V 用戶端電腦的外形規格一樣，以盡可能接近的方式來設計。</span><span class="sxs-lookup"><span data-stu-id="8f288-169">Therefore, the management console should be designed with a form factor that resembles, as closely as possible, the form factor of a typical MED-V client machine.</span></span>

<span data-ttu-id="8f288-170">管理主控台應用程式是與 MED-V 用戶端一起安裝，並將 Microsoft Virtual PC2007 SP1 與 Microsoft 知識庫文章974918中所述的修正程式搭配使用。</span><span class="sxs-lookup"><span data-stu-id="8f288-170">The management console application is installed together with the MED-V client and uses Microsoft Virtual PC2007 SP1 with the hotfix that is described in Microsoft Knowledge Base article 974918.</span></span> <span data-ttu-id="8f288-171">必須使用用戶端作業系統;MED-V 管理主控台無法在與 MED-V 伺服器相同的系統上執行。</span><span class="sxs-lookup"><span data-stu-id="8f288-171">A client operating system must be used; the MED-V management console cannot run on the same system as the MED-V server.</span></span>

<span data-ttu-id="8f288-172">您無法與多個 MED-V 伺服器實例共用管理主控台。</span><span class="sxs-lookup"><span data-stu-id="8f288-172">You cannot share a management console with multiple MED-V server instances.</span></span> <span data-ttu-id="8f288-173">MED-V 伺服器的位址是在安裝管理主控台的 MED-V 用戶端期間指定;此功能可以在安裝後進行變更，但在任何時候，管理主控台只能與單一 MED-V 伺服器搭配使用。</span><span class="sxs-lookup"><span data-stu-id="8f288-173">The address of the MED-V server is specified during the installation of the management console’s MED-V client; this can be changed after installation, but at any time the management console can only work with a single MED-V server.</span></span>

<span data-ttu-id="8f288-174">您可以將多個管理主控台搭配單一的 MED-V 伺服器使用。</span><span class="sxs-lookup"><span data-stu-id="8f288-174">You can use multiple management consoles with a single MED-V server.</span></span> <span data-ttu-id="8f288-175">為了避免發生衝突，有一個可讓其他主控台使用者在其中一個主機變更 MED-V 工作區的機制。</span><span class="sxs-lookup"><span data-stu-id="8f288-175">To avoid conflicts, a mechanism is available that notifies other console users when one console has made changes to a MED-V workspace.</span></span>

<span data-ttu-id="8f288-176">針對每個 MED-V 實例，判斷需要多少管理主控台，以及它們將放在哪裡。</span><span class="sxs-lookup"><span data-stu-id="8f288-176">For each MED-V instance, determine how many management consoles will be needed and where they will be placed.</span></span> <span data-ttu-id="8f288-177">選取要用於管理主控台的典型 MED-V 用戶端外形規格。</span><span class="sxs-lookup"><span data-stu-id="8f288-177">Select a typical MED-V client form factor to be used for the management console.</span></span>

## <span data-ttu-id="8f288-178">相關主題</span><span class="sxs-lookup"><span data-stu-id="8f288-178">Related topics</span></span>


[<span data-ttu-id="8f288-179">MED-V 1.0 SP1 支援的組態</span><span class="sxs-lookup"><span data-stu-id="8f288-179">MED-V 1.0 SP1 Supported Configurations</span></span>](med-v-10-sp1-supported-configurationsmedv-10-sp1.md)

[<span data-ttu-id="8f288-180">設定叢集模式的 MED-V 伺服器</span><span class="sxs-lookup"><span data-stu-id="8f288-180">Configuring MED-V Server for Cluster Mode</span></span>](configuring-med-v-server-for-cluster-mode.md)

[<span data-ttu-id="8f288-181">如何安裝 MED-V 用戶端及 MED-V 管理主控台</span><span class="sxs-lookup"><span data-stu-id="8f288-181">How to Install MED-V Client and MED-V Management Console</span></span>](how-to-install-med-v-client-and-med-v-management-console.md)

[<span data-ttu-id="8f288-182">使用 MED-V 管理主控台使用者介面</span><span class="sxs-lookup"><span data-stu-id="8f288-182">Using the MED-V Management Console User Interface</span></span>](using-the-med-v-management-console-user-interface.md)

 

 





