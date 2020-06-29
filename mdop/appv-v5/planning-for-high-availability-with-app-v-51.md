---
title: App-V 5.1 高可用性規劃
description: App-V 5.1 高可用性規劃
author: dansimp
ms.assetid: 1f190a0e-10ee-4fbe-a602-7e807e943033
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 5c8e0e684051859a4caa2c4ef983c040295bc6d4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800354"
---
# <span data-ttu-id="0b575-103">App-V 5.1 高可用性規劃</span><span class="sxs-lookup"><span data-stu-id="0b575-103">Planning for High Availability with App-V 5.1</span></span>


<span data-ttu-id="0b575-104">Microsoft 應用程式虛擬化（App-v）5.1 系統組態可以利用維護高層次可用服務的選項。</span><span class="sxs-lookup"><span data-stu-id="0b575-104">Microsoft Application Virtualization (App-V) 5.1 system configurations can take advantage of options that maintain a high level of available service.</span></span>

<span data-ttu-id="0b575-105">使用下列各節中的資訊，協助您瞭解在高可用性配置中部署 app-v 5.1 的選項。</span><span class="sxs-lookup"><span data-stu-id="0b575-105">Use the information in the following sections to help you understand the options to deploy App-V 5.1 in a highly available configuration.</span></span>

-   [<span data-ttu-id="0b575-106">Microsoft SQL Server 群集支援</span><span class="sxs-lookup"><span data-stu-id="0b575-106">Support for Microsoft SQL Server clustering</span></span>](#bkmk-sqlcluster)

-   [<span data-ttu-id="0b575-107">支援 IIS 網路負載平衡</span><span class="sxs-lookup"><span data-stu-id="0b575-107">Support for IIS Network Load Balancing</span></span>](#bkmk-iisloadbal)

-   [<span data-ttu-id="0b575-108">在執行時支援群集檔案伺服器（SCS）模式</span><span class="sxs-lookup"><span data-stu-id="0b575-108">Support for clustered file servers when running (SCS) mode</span></span>](#bkmk-clusterscsmode)

-   [<span data-ttu-id="0b575-109">Microsoft SQL Server 鏡像支援</span><span class="sxs-lookup"><span data-stu-id="0b575-109">Support for Microsoft SQL Server Mirroring</span></span>](#bkmk-sqlmirroring)

-   [<span data-ttu-id="0b575-110">Microsoft SQL Server 的支援永遠開啟</span><span class="sxs-lookup"><span data-stu-id="0b575-110">Support for Microsoft SQL Server Always On</span></span>](#bkmk-sqlalwayson)

## <a href="" id="bkmk-sqlcluster"></a><span data-ttu-id="0b575-111">Microsoft SQL Server 群集支援</span><span class="sxs-lookup"><span data-stu-id="0b575-111">Support for Microsoft SQL Server clustering</span></span>


<span data-ttu-id="0b575-112">您可以在執行 Microsoft SQL Server 群集的電腦上執行 App-v 管理資料庫和報告資料庫。</span><span class="sxs-lookup"><span data-stu-id="0b575-112">You can run the App-V Management database and Reporting database on computers that are running Microsoft SQL Server clusters.</span></span> <span data-ttu-id="0b575-113">不過，您必須使用腳本來安裝資料庫。</span><span class="sxs-lookup"><span data-stu-id="0b575-113">However, you must install the databases using scripts.</span></span>

<span data-ttu-id="0b575-114">如需相關指示，請參閱[如何使用 SQL 腳本部署 App-v 資料庫](how-to-deploy-the-app-v-databases-by-using-sql-scripts51.md)。</span><span class="sxs-lookup"><span data-stu-id="0b575-114">For instructions, see [How to Deploy the App-V Databases by Using SQL Scripts](how-to-deploy-the-app-v-databases-by-using-sql-scripts51.md).</span></span>

## <a href="" id="bkmk-iisloadbal"></a><span data-ttu-id="0b575-115">支援 IIS 網路負載平衡</span><span class="sxs-lookup"><span data-stu-id="0b575-115">Support for IIS Network Load Balancing</span></span>


<span data-ttu-id="0b575-116">您可以使用 Internet Information Services （IIS）網路負載平衡，為執行 App-v 5 a.x 管理、發佈和報表服務的電腦（透過 IIS 部署）設定高可用性環境。</span><span class="sxs-lookup"><span data-stu-id="0b575-116">You can use Internet Information Services (IIS) Network Load Balancing to configure a highly available environment for computers running the App-V 5.x Management, Publishing, and Reporting services which are deployed through IIS.</span></span>

<span data-ttu-id="0b575-117">如需針對執行 Windows Server 作業系統的電腦設定 IIS 和網路負載平衡的詳細資訊，請參閱下列內容：</span><span class="sxs-lookup"><span data-stu-id="0b575-117">Review the following for more information about configuring IIS and Network Load Balancing for computers running Windows Server operating systems:</span></span>

-   <span data-ttu-id="0b575-118">提供有關設定網際網路資訊服務（IIS）7.0 的資訊。</span><span class="sxs-lookup"><span data-stu-id="0b575-118">Provides information about configuring Internet Information Services (IIS) 7.0.</span></span>

    <span data-ttu-id="0b575-119">[實現高可用性和可伸縮性-ARR 與 NLB](https://go.microsoft.com/fwlink/?LinkId=316369) （https://go.microsoft.com/fwlink/?LinkId=316369)</span><span class="sxs-lookup"><span data-stu-id="0b575-119">[Achieving High Availability and Scalability - ARR and NLB](https://go.microsoft.com/fwlink/?LinkId=316369) (https://go.microsoft.com/fwlink/?LinkId=316369)</span></span>

-   <span data-ttu-id="0b575-120">正在設定 Microsoft Windows Server</span><span class="sxs-lookup"><span data-stu-id="0b575-120">Configuring Microsoft Windows Server</span></span>

    <span data-ttu-id="0b575-121">[網路負載平衡](https://go.microsoft.com/fwlink/?LinkId=316370)（ https://go.microsoft.com/fwlink/?LinkId=316370) 。</span><span class="sxs-lookup"><span data-stu-id="0b575-121">[Network Load Balancing](https://go.microsoft.com/fwlink/?LinkId=316370) (https://go.microsoft.com/fwlink/?LinkId=316370).</span></span>

    <span data-ttu-id="0b575-122">這項資訊也適用于 Windows Server2008、Windows Server2008R2 或 Windows Server2012 中的 IIS 網路負載平衡（NLB）群集。</span><span class="sxs-lookup"><span data-stu-id="0b575-122">This information also applies to IIS Network Load Balancing (NLB) clusters in Windows Server2008, Windows Server2008R2, or Windows Server2012.</span></span>

    <span data-ttu-id="0b575-123">**記事** Windows Server2012 中的 IIS 網路負載平衡功能通常與 Windows Server2008R2 中的相同。</span><span class="sxs-lookup"><span data-stu-id="0b575-123">**Note** The IIS Network Load Balancing functionality in Windows Server2012 is generally the same as in Windows Server2008R2.</span></span> <span data-ttu-id="0b575-124">不過，某些任務的詳細資料會在 Windows Server2012 中變更。</span><span class="sxs-lookup"><span data-stu-id="0b575-124">However, some task details are changed in Windows Server2012.</span></span> <span data-ttu-id="0b575-125">如需新的執行工作方式的詳細資訊，請參閱[Windows Server 2012 R2 Preview 和 Windows server 2012 中的常見管理工作與流覽](https://go.microsoft.com/fwlink/?LinkId=316371)（ https://go.microsoft.com/fwlink/?LinkId=316371) 。</span><span class="sxs-lookup"><span data-stu-id="0b575-125">For information on new ways to do tasks, see [Common Management Tasks and Navigation in Windows Server 2012 R2 Preview and Windows Server 2012](https://go.microsoft.com/fwlink/?LinkId=316371) (https://go.microsoft.com/fwlink/?LinkId=316371).</span></span>

     

## <a href="" id="bkmk-clusterscsmode"></a><span data-ttu-id="0b575-126">在執行時支援群集檔案伺服器（SCS）模式</span><span class="sxs-lookup"><span data-stu-id="0b575-126">Support for clustered file servers when running (SCS) mode</span></span>


<span data-ttu-id="0b575-127">支援在具有群集檔案伺服器的共用內容存放區（SCS）模式中執行 App-v 5.1。</span><span class="sxs-lookup"><span data-stu-id="0b575-127">Running App-V 5.1 in Share Content Store (SCS) mode with clustered file servers is supported.</span></span>

<span data-ttu-id="0b575-128">您可以使用下列步驟來啟用此設定：</span><span class="sxs-lookup"><span data-stu-id="0b575-128">The following steps can be used to enable this configuration:</span></span>

-   <span data-ttu-id="0b575-129">將 App-v 5.1 設定為在用戶端 SCS 模式中執行。</span><span class="sxs-lookup"><span data-stu-id="0b575-129">Configure App-V 5.1 to run in client SCS mode.</span></span> <span data-ttu-id="0b575-130">如需設定 App-v 5.1 SCS 模式的詳細資訊，請參閱[如何安裝 app-v 5.1 用戶端以取得共用內容存放區模式](how-to-install-the-app-v-51-client-for-shared-content-store-mode.md)。</span><span class="sxs-lookup"><span data-stu-id="0b575-130">For more information about configuring App-V 5.1 SCS mode, see [How to Install the App-V 5.1 Client for Shared Content Store Mode](how-to-install-the-app-v-51-client-for-shared-content-store-mode.md).</span></span>

-   <span data-ttu-id="0b575-131">在 Microsoft Server2012 橫向模式和使用虛擬 SAN 的**2012**模式中設定檔案伺服器群集。</span><span class="sxs-lookup"><span data-stu-id="0b575-131">Configure the file server cluster configured in both the Microsoft Server2012 scale out mode and pre **2012** mode with a virtual SAN.</span></span>

<span data-ttu-id="0b575-132">您可以使用下列步驟來驗證配置：</span><span class="sxs-lookup"><span data-stu-id="0b575-132">The following steps can be used to validate the configuration:</span></span>

1.  <span data-ttu-id="0b575-133">在發佈伺服器上新增套件。</span><span class="sxs-lookup"><span data-stu-id="0b575-133">Add a package on the publishing server.</span></span> <span data-ttu-id="0b575-134">如需有關新增套件的詳細資訊，請參閱[如何使用管理主控台新增或升級套件](how-to-add-or-upgrade-packages-by-using-the-management-console-51-gb18030.md)。</span><span class="sxs-lookup"><span data-stu-id="0b575-134">For more information about adding a package, see [How to Add or Upgrade Packages by Using the Management Console](how-to-add-or-upgrade-packages-by-using-the-management-console-51-gb18030.md).</span></span>

2.  <span data-ttu-id="0b575-135">在執行 App-v 5.1 用戶端的電腦上執行發佈更新，並開啟應用程式。</span><span class="sxs-lookup"><span data-stu-id="0b575-135">Perform a publishing refresh on the computer running the App-V 5.1 client and open an application.</span></span>

3.  <span data-ttu-id="0b575-136">切換叢集節點的中間發佈更新及中端資料流程，以確保容錯移轉正常運作。</span><span class="sxs-lookup"><span data-stu-id="0b575-136">Switch cluster nodes mid-publishing refresh and mid-streaming to ensure fail-over works correctly.</span></span>

<span data-ttu-id="0b575-137">如需有關設定 Windows Server 容錯移轉叢集的詳細資訊，請參閱下列內容：</span><span class="sxs-lookup"><span data-stu-id="0b575-137">Review the following for more information about configuring Windows Server Failover clusters:</span></span>

-   <span data-ttu-id="0b575-138">[檢查清單：建立群集檔案伺服器](https://go.microsoft.com/fwlink/?LinkId=316372)（ https://go.microsoft.com/fwlink/?LinkId=316372) 。</span><span class="sxs-lookup"><span data-stu-id="0b575-138">[Checklist: Create a Clustered File Server](https://go.microsoft.com/fwlink/?LinkId=316372) (https://go.microsoft.com/fwlink/?LinkId=316372).</span></span>

-   <span data-ttu-id="0b575-139">[在 Windows Server 2012 的 [容錯移轉叢集] 中使用群集共用的磁片](https://go.microsoft.com/fwlink/?LinkId=316373) https://go.microsoft.com/fwlink/?LinkId=316373) 。</span><span class="sxs-lookup"><span data-stu-id="0b575-139">[Use Cluster Shared Volumes in a Windows Server 2012 Failover Cluster](https://go.microsoft.com/fwlink/?LinkId=316373) (https://go.microsoft.com/fwlink/?LinkId=316373).</span></span>

## <a href="" id="bkmk-sqlmirroring"></a><span data-ttu-id="0b575-140">Microsoft SQL Server 鏡像支援</span><span class="sxs-lookup"><span data-stu-id="0b575-140">Support for Microsoft SQL Server Mirroring</span></span>


<span data-ttu-id="0b575-141">5.1 如果您使用 Microsoft SQL Server 鏡像，即會支援 app-v 5.1 管理伺服器資料庫使用兩個 SQL Server 實例進行鏡像。</span><span class="sxs-lookup"><span data-stu-id="0b575-141">Using Microsoft SQL Server mirroring, where the App-V 5.1 management server database is mirrored utilizing two SQL Server instances, for App-V 5.1 management server databases is supported.</span></span>

<span data-ttu-id="0b575-142">如需有關設定 Microsoft SQL Server 鏡像的詳細資訊，請參閱下列內容：</span><span class="sxs-lookup"><span data-stu-id="0b575-142">Review the following for more information about configuring Microsoft SQL Server Mirroring:</span></span>

-   <span data-ttu-id="0b575-143">[操作方法：準備鏡像資料庫以進行鏡像（transact-sql）](https://go.microsoft.com/fwlink/?LinkId=316375) （https://go.microsoft.com/fwlink/?LinkId=316375)</span><span class="sxs-lookup"><span data-stu-id="0b575-143">[How to: Prepare a Mirror Database for Mirroring (Transact-SQL)](https://go.microsoft.com/fwlink/?LinkId=316375) (https://go.microsoft.com/fwlink/?LinkId=316375)</span></span>

-   <span data-ttu-id="0b575-144">[使用 Windows 驗證（SQL Server Management Studio）建立資料庫鏡像會話](https://go.microsoft.com/fwlink/?LinkId=316377)（https://go.microsoft.com/fwlink/?LinkId=316377)</span><span class="sxs-lookup"><span data-stu-id="0b575-144">[Establish a Database Mirroring Session Using Windows Authentication (SQL Server Management Studio)](https://go.microsoft.com/fwlink/?LinkId=316377) (https://go.microsoft.com/fwlink/?LinkId=316377)</span></span>

<span data-ttu-id="0b575-145">您可以使用下列步驟來驗證配置：</span><span class="sxs-lookup"><span data-stu-id="0b575-145">The following steps can be used to validate the configuration:</span></span>

1.  <span data-ttu-id="0b575-146">啟動 Microsoft SQL Server 鏡像會話。</span><span class="sxs-lookup"><span data-stu-id="0b575-146">Initiate a Microsoft SQL Server Mirroring session.</span></span>

2.  <span data-ttu-id="0b575-147">選取 [**容錯移轉**] 以指定新的主 Microsoft SQL Server 實例。</span><span class="sxs-lookup"><span data-stu-id="0b575-147">Select **Failover** to designate a new master Microsoft SQL Server instance.</span></span>

3.  <span data-ttu-id="0b575-148">驗證在容錯移轉之後，App-v 5.1 管理伺服器仍能正常發揮預期的作用。</span><span class="sxs-lookup"><span data-stu-id="0b575-148">Verify that the App-V 5.1 management server continues to function as expected after the failover.</span></span>

<span data-ttu-id="0b575-149">管理伺服器上的連接字串可以修改，以包含\*\*容錯移轉夥伴 = &lt; server2 &gt; \*\*。</span><span class="sxs-lookup"><span data-stu-id="0b575-149">The connection string on the management server can be modified to include **failover partner = &lt;server2&gt;**.</span></span> <span data-ttu-id="0b575-150">這只會在鏡像的主要元件容錯移轉到次要電腦，而執行 App-v 5.1 用戶端的電腦正在進行全新連線（例如重新開機之後）時提供協助。</span><span class="sxs-lookup"><span data-stu-id="0b575-150">This will only help when the primary on the mirror has failed over to the secondary and the computer running the App-V 5.1 client is doing a fresh connection (say after reboot).</span></span>

<span data-ttu-id="0b575-151">使用下列步驟來修改連接字串，以包含\*\*容錯移轉夥伴 = &lt; server2 &gt; \*\*：</span><span class="sxs-lookup"><span data-stu-id="0b575-151">Use the following steps to modify the connection string to include **failover partner = &lt;server2&gt;**:</span></span>

<span data-ttu-id="0b575-152">**重要** 本主題說明如何使用 [登錄編輯程式] 變更 Windows 登錄。</span><span class="sxs-lookup"><span data-stu-id="0b575-152">**Important** This topic describes how to change the Windows registry by using Registry Editor.</span></span> <span data-ttu-id="0b575-153">如果您不正確地變更 Windows 登錄，可能會導致嚴重的問題，可能需要重新安裝 Windows。</span><span class="sxs-lookup"><span data-stu-id="0b575-153">If you change the Windows registry incorrectly, you can cause serious problems that might require you to reinstall Windows.</span></span> <span data-ttu-id="0b575-154">變更登錄前，您應該先製作一份登錄檔案（系統 .dat 和使用者 .dat）的備份複本。</span><span class="sxs-lookup"><span data-stu-id="0b575-154">You should make a backup copy of the registry files (System.dat and User.dat) before you change the registry.</span></span> <span data-ttu-id="0b575-155">Microsoft 不能保證變更註冊表時可能會發生的問題，可以解決。</span><span class="sxs-lookup"><span data-stu-id="0b575-155">Microsoft cannot guarantee that the problems that might occur when you change the registry can be resolved.</span></span> <span data-ttu-id="0b575-156">變更註冊表的風險由您自行承擔。</span><span class="sxs-lookup"><span data-stu-id="0b575-156">Change the registry at your own risk.</span></span>

 

1.  <span data-ttu-id="0b575-157">登入管理伺服器並開啟**regedit**。</span><span class="sxs-lookup"><span data-stu-id="0b575-157">Login to the management server and open **regedit**.</span></span>

2.  <span data-ttu-id="0b575-158">流覽至**HKEY \ _LOCAL \ _MACHINE**  \\  **軟體**  \\  **Microsoft**  \\  **AppV**  \\  **Server**  \\  **ManagementService**。</span><span class="sxs-lookup"><span data-stu-id="0b575-158">Navigate to **HKEY\_LOCAL\_MACHINE** \\ **Software** \\ **Microsoft** \\ **AppV** \\ **Server** \\ **ManagementService**.</span></span>

3.  <span data-ttu-id="0b575-159">使用**容錯移轉夥伴 = &lt; &gt; Server2**來修改**管理 \ _SQL \ _CONNECTION \ _STRING**值。</span><span class="sxs-lookup"><span data-stu-id="0b575-159">Modify the **MANAGEMENT\_SQL\_CONNECTION\_STRING** value with the **failover partner = &lt;server2&gt;**.</span></span>

4.  <span data-ttu-id="0b575-160">使用 IIS 主控台重新開機管理服務。</span><span class="sxs-lookup"><span data-stu-id="0b575-160">Restart management service using the IIS console.</span></span>

    <span data-ttu-id="0b575-161">**記事** 資料庫鏡像是針對 Microsoft SQL Server2012 的已過時資料庫引擎功能清單，因為 Microsoft SQL Server 2012 提供了**AlwaysOn**功能。</span><span class="sxs-lookup"><span data-stu-id="0b575-161">**Note** Database Mirroring is on the list of Deprecated Database Engine Features for Microsoft SQL Server2012 due to the **AlwaysOn** feature available with Microsoft SQL Server 2012.</span></span>

     

<span data-ttu-id="0b575-162">如需詳細資訊，請按一下下列任何一個連結：</span><span class="sxs-lookup"><span data-stu-id="0b575-162">Click any of the following links for more information:</span></span>

-   <span data-ttu-id="0b575-163">[操作方法：準備鏡像資料庫以進行鏡像（transact-sql）](https://go.microsoft.com/fwlink/?LinkId=394235) （ https://go.microsoft.com/fwlink/?LinkId=394235) 。</span><span class="sxs-lookup"><span data-stu-id="0b575-163">[How to: Prepare a Mirror Database for Mirroring (Transact-SQL)](https://go.microsoft.com/fwlink/?LinkId=394235) (https://go.microsoft.com/fwlink/?LinkId=394235).</span></span>

-   <span data-ttu-id="0b575-164">[操作方法：設定資料庫鏡像會話（SQL Server Management Studio）](https://go.microsoft.com/fwlink/?LinkId=394236) （ https://go.microsoft.com/fwlink/?LinkId=394236) 。</span><span class="sxs-lookup"><span data-stu-id="0b575-164">[How to: Configure a Database Mirroring Session (SQL Server Management Studio)](https://go.microsoft.com/fwlink/?LinkId=394236) (https://go.microsoft.com/fwlink/?LinkId=394236).</span></span>

-   <span data-ttu-id="0b575-165">[使用 Windows 驗證（SQL Server Management Studio）建立資料庫鏡像會話](https://go.microsoft.com/fwlink/?LinkId=394237)（ https://go.microsoft.com/fwlink/?LinkId=394237) 。</span><span class="sxs-lookup"><span data-stu-id="0b575-165">[Establish a Database Mirroring Session Using Windows Authentication (SQL Server Management Studio)](https://go.microsoft.com/fwlink/?LinkId=394237) (https://go.microsoft.com/fwlink/?LinkId=394237).</span></span>

-   <span data-ttu-id="0b575-166">[SQL Server 2012 中已過時的資料庫引擎功能](https://go.microsoft.com/fwlink/?LinkId=394238)（ https://go.microsoft.com/fwlink/?LinkId=394238) 。</span><span class="sxs-lookup"><span data-stu-id="0b575-166">[Deprecated Database Engine Features in SQL Server 2012](https://go.microsoft.com/fwlink/?LinkId=394238) (https://go.microsoft.com/fwlink/?LinkId=394238).</span></span>

## <a href="" id="bkmk-sqlalwayson"></a><span data-ttu-id="0b575-167">Microsoft SQL Server 的支援總在設定上</span><span class="sxs-lookup"><span data-stu-id="0b575-167">Support for Microsoft SQL Server Always On configuration</span></span>


<span data-ttu-id="0b575-168">App-v 5.1 管理伺服器資料庫支援使用 [**永遠開啟**] 設定，將部署到執行 Microsoft SQL server 的電腦。</span><span class="sxs-lookup"><span data-stu-id="0b575-168">The App-V 5.1 management server database supports deployments to computers running Microsoft SQL Server with the **Always On** configuration.</span></span>






## <span data-ttu-id="0b575-169">相關主題</span><span class="sxs-lookup"><span data-stu-id="0b575-169">Related topics</span></span>


[<span data-ttu-id="0b575-170">規劃部署 App-V</span><span class="sxs-lookup"><span data-stu-id="0b575-170">Planning to Deploy App-V</span></span>](planning-to-deploy-app-v51.md)

 

 





