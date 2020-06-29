---
title: 如何在 App-V 用戶端 (VDI) 上設定唯讀快取
description: 如何在 App-V 用戶端 (VDI) 上設定唯讀快取
author: dansimp
ms.assetid: 7a41e017-9e23-4a6a-a659-04d23f008b83
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 114f9dfbf55a3f62b6bc8bec6b37a659ffbfaf56
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801618"
---
# <span data-ttu-id="073ed-103">如何在 App-V 用戶端 (VDI) 上設定唯讀快取</span><span class="sxs-lookup"><span data-stu-id="073ed-103">How to Configure a Read-only Cache on the App-V Client (VDI)</span></span>


<span data-ttu-id="073ed-104">在 Microsoft Application Virtualization （App-v）4.6 中，用戶端支援使用共用的唯讀快取快取。</span><span class="sxs-lookup"><span data-stu-id="073ed-104">In Microsoft Application Virtualization (App-V) 4.6 the Client supports using a shared read-only cache.</span></span> <span data-ttu-id="073ed-105">共用唯讀快取可讓用戶端能在虛擬桌面基礎結構（VDI）系統中高效地使用磁碟空間，使用者可以在其中執行資料中心伺服器環境中託管的虛擬機器（VM）上的應用程式，並在儲存區域網路（SAN）上共用網路儲存空間。</span><span class="sxs-lookup"><span data-stu-id="073ed-105">The shared read-only cache enables the Client to use disk space efficiently in a Virtual Desktop Infrastructure (VDI) system, where users run applications on Virtual Machines (VM) that are hosted in a data center server environment and share network storage on a Storage Area Network (SAN).</span></span> <span data-ttu-id="073ed-106">下列程式會提供在其中一個主要 VDI 架構（稱為「彙集 VM」或「靜態 VM」）中實現 App-v 用戶端所需程式的概覽。</span><span class="sxs-lookup"><span data-stu-id="073ed-106">The following procedures provide an overview of the process that is required to implement the App-V Client in either of the primary VDI architectures, known as “Pooled VM” or “Static VM”.</span></span> <span data-ttu-id="073ed-107">假設您熟悉 App-v system 及其元件的規劃、部署及操作，以及 VDI 伺服器的操作與管理。。。。</span><span class="sxs-lookup"><span data-stu-id="073ed-107">It is assumed that you are familiar with the planning, deployment, and operation of the App-V system and its components, and also the operation and management of the VDI server.</span></span> <span data-ttu-id="073ed-108">如需 App-v 的詳細資訊，請參閱[應用程式虛擬化](https://go.microsoft.com/fwlink/?LinkId=122939)（https://go.microsoft.com/fwlink/?LinkId=122939)</span><span class="sxs-lookup"><span data-stu-id="073ed-108">For more information about App-V, see [Application Virtualization](https://go.microsoft.com/fwlink/?LinkId=122939) (https://go.microsoft.com/fwlink/?LinkId=122939)</span></span>

<span data-ttu-id="073ed-109">**記事** 這些程式中所述的詳細資料僅做為範例。</span><span class="sxs-lookup"><span data-stu-id="073ed-109">**Note** The details outlined in these procedures are intended as examples only.</span></span> <span data-ttu-id="073ed-110">您可能會使用不同的方法來完成整個程式。</span><span class="sxs-lookup"><span data-stu-id="073ed-110">You might use different methods to complete the overall process.</span></span>

 

## <span data-ttu-id="073ed-111">在 VDI 案例中部署 App-v 用戶端</span><span class="sxs-lookup"><span data-stu-id="073ed-111">Deploying the App-V Client in a VDI Scenario</span></span>


<span data-ttu-id="073ed-112">您可以在 VDI 案例中部署 app-v 用戶端，方法是使用已填入所有使用者所需的所有應用程式的共用唯讀快取。</span><span class="sxs-lookup"><span data-stu-id="073ed-112">You can deploy the App-V Client in a VDI scenario by using a shared read-only cache that has been populated with all the applications required for all users.</span></span> <span data-ttu-id="073ed-113">接著您可以設定 VDI 主 VM 影像，讓所有 App-v 用戶端都使用相同的快取檔案。</span><span class="sxs-lookup"><span data-stu-id="073ed-113">You then configure the VDI Master VM Image so that all the App-V Clients use the same cache file.</span></span> <span data-ttu-id="073ed-114">使用者可以使用 App-v 發佈程式來獲准存取特定的應用程式。</span><span class="sxs-lookup"><span data-stu-id="073ed-114">Users are granted access to specific applications by using the App-V publishing process.</span></span> <span data-ttu-id="073ed-115">由於快取已預先載入所有的應用程式，因此當使用者啟動應用程式時，不會發生任何資料流程。</span><span class="sxs-lookup"><span data-stu-id="073ed-115">Since the cache is already preloaded with all applications, no streaming occurs when a user starts an application.</span></span> <span data-ttu-id="073ed-116">不過，您必須將用來預裝快取的套件放在支援即時資料流通訊協定（RTSP）資料流程的 App-v 伺服器上，並授予 App-v 用戶端的存取權限。</span><span class="sxs-lookup"><span data-stu-id="073ed-116">However, the packages used to prepopulate the cache must be put on an App-V server that supports Real Time Streaming Protocol (RTSP) streaming and that grants access permissions to the App-V Clients.</span></span> <span data-ttu-id="073ed-117">如果您使用 App-v 管理伺服器發佈應用程式，您可以使用它來提供此資料流程函數。</span><span class="sxs-lookup"><span data-stu-id="073ed-117">If you publish the applications by using an App-V Management Server, you can use it to provide this streaming function.</span></span>

<span data-ttu-id="073ed-118">部署程式是由四個主要任務所組成：</span><span class="sxs-lookup"><span data-stu-id="073ed-118">The deployment process consists of four primary tasks:</span></span>

-   <span data-ttu-id="073ed-119">建立及填充主共用的快取檔案</span><span class="sxs-lookup"><span data-stu-id="073ed-119">Creating and populating the master shared cache file</span></span>

-   <span data-ttu-id="073ed-120">將共用的快取檔案複製到 VDI 伺服器儲存體</span><span class="sxs-lookup"><span data-stu-id="073ed-120">Copying the shared cache file to the VDI server storage</span></span>

-   <span data-ttu-id="073ed-121">在 VDI 主映射上配置 app-v 用戶端軟體</span><span class="sxs-lookup"><span data-stu-id="073ed-121">Configuring the App-V client software on the VDI Master Image</span></span>

-   <span data-ttu-id="073ed-122">在初始部署之後管理共用快取檔案的更新部署週期</span><span class="sxs-lookup"><span data-stu-id="073ed-122">Managing the update deployment cycle for the shared cache file after the initial deployment</span></span>

<span data-ttu-id="073ed-123">這些工作需要謹慎規劃。</span><span class="sxs-lookup"><span data-stu-id="073ed-123">These tasks require careful planning.</span></span> <span data-ttu-id="073ed-124">我們建議您為您的組織準備並記錄可重複使用的程式，以供貴組織追蹤。</span><span class="sxs-lookup"><span data-stu-id="073ed-124">We recommend that you prepare and document a methodical, reproducible process for your organization to follow.</span></span> <span data-ttu-id="073ed-125">這對於主共用快取檔案的初始準備與部署尤為重要，且針對應用程式更新的日常管理，每一個都需要更新主共用快取。</span><span class="sxs-lookup"><span data-stu-id="073ed-125">This is especially important for the initial preparation and deployment of the master shared cache file, and for the on-going management of application updates, each of which require an update to the master shared cache.</span></span> <span data-ttu-id="073ed-126">使用下列程式完成這些主要任務。</span><span class="sxs-lookup"><span data-stu-id="073ed-126">Use the following procedures to complete these primary tasks.</span></span>

<span data-ttu-id="073ed-127">**記事** 雖然您可以使用數種不同的方法發佈應用程式，但下列程式是以使用 App-v 管理伺服器來發佈的方式為基礎。</span><span class="sxs-lookup"><span data-stu-id="073ed-127">**Note** Although you can publish the applications by using several different methods, the following procedures are based on the use of an App-V Management Server for publishing.</span></span>

 

**<span data-ttu-id="073ed-128">在共用 VM VDI 或靜態 VM VDI 案例中設定唯讀快取以進行初始部署</span><span class="sxs-lookup"><span data-stu-id="073ed-128">To configure the read-only cache for initial deployment in a Pooled VM VDI or Static VM VDI scenario</span></span>**

1. <span data-ttu-id="073ed-129">在 VDI 伺服器的 VM 中設定和設定 App-v 管理伺服器，以提供使用者驗證及發佈支援。</span><span class="sxs-lookup"><span data-stu-id="073ed-129">Set up and configure an App-V Management Server in a VM on the VDI server to provide user authentication and publishing support.</span></span>

2. <span data-ttu-id="073ed-130">以所有使用者所需的所有應用程式套件填入此管理伺服器的 [內容] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="073ed-130">Populate the Content folder of this Management Server with all the application packages required for all users.</span></span>

3. <span data-ttu-id="073ed-131">設定已安裝應用程式 V 用戶端的暫存電腦。</span><span class="sxs-lookup"><span data-stu-id="073ed-131">Set up a staging computer that has the App-V Client installed.</span></span> <span data-ttu-id="073ed-132">使用可存取所有應用程式的帳戶登入暫存電腦，以便將一組完整的應用程式發佈到電腦，然後將應用程式流式處理成可完全載入。</span><span class="sxs-lookup"><span data-stu-id="073ed-132">Log on to the staging computer with an account that has access to all applications so that the complete set of applications are published to the computer, and then stream the applications to cache so that they are fully loaded.</span></span>

   **<span data-ttu-id="073ed-133">重要</span><span class="sxs-lookup"><span data-stu-id="073ed-133">Important</span></span>**  
   <span data-ttu-id="073ed-134">暫存電腦所使用的作業系統類型和系統架構必須與應用程式 V 用戶端將執行的 Vm 所使用的相同。</span><span class="sxs-lookup"><span data-stu-id="073ed-134">The staging computer must use the same operating system type and system architecture as those used by the VMs on which the App-V Client will run.</span></span>

     

4. <span data-ttu-id="073ed-135">在安全模式中重新開機暫存電腦，以確保驅動程式未啟動，這會鎖定快取檔案。</span><span class="sxs-lookup"><span data-stu-id="073ed-135">Restart the staging computer in Safe Mode to ensure the drivers are not started, which would lock the cache file.</span></span>

   **<span data-ttu-id="073ed-136">注意</span><span class="sxs-lookup"><span data-stu-id="073ed-136">Note</span></span>**  
   <span data-ttu-id="073ed-137">或者，您可以停止並停用應用程式虛擬化服務，然後重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="073ed-137">Alternatively, you can stop and disable the Application Virtualization service, and then restart the computer.</span></span> <span data-ttu-id="073ed-138">複製檔案之後，請記得再次啟用並啟動該服務。</span><span class="sxs-lookup"><span data-stu-id="073ed-138">After the file has been copied, remember to enable and start the service again.</span></span>

     

5. <span data-ttu-id="073ed-139">將 Sftfs fsd cache 檔案複製到 VDI 伺服器的 SAN 中，所有 Vm 都可以存取，例如共用資料夾。</span><span class="sxs-lookup"><span data-stu-id="073ed-139">Copy the Sftfs.fsd cache file to the VDI server’s SAN where all the VMs can access it, such as in a shared folder.</span></span> <span data-ttu-id="073ed-140">針對將管理快取檔案更新的管理員，將 [資料夾存取許可權] 設定為 [所有人都能使用唯讀] 和 [完全控制]。</span><span class="sxs-lookup"><span data-stu-id="073ed-140">Set the folder access permissions to Read-only for the group Everyone and to Full Control for administrators who will manage the cache file updates.</span></span> <span data-ttu-id="073ed-141">可以從 registry AppFS\\FileName. 取得快取檔案的位置</span><span class="sxs-lookup"><span data-stu-id="073ed-141">The location of the cache file can be obtained from the registry AppFS\\FileName.</span></span>

   **<span data-ttu-id="073ed-142">重要</span><span class="sxs-lookup"><span data-stu-id="073ed-142">Important</span></span>**  
   <span data-ttu-id="073ed-143">您必須將 FSD 檔案放在具有對本機附加儲存效能（例如 SAN）同等回應與可靠性的位置。</span><span class="sxs-lookup"><span data-stu-id="073ed-143">You must put the FSD file in a location that has the responsiveness and reliability equivalent to locally attached storage performance, for example, a SAN.</span></span>

     

6. <span data-ttu-id="073ed-144">在 VDI 主 VM 影像上安裝 App-v Desktop 用戶端，然後將下列登錄機碼值新增到用戶端的 AppFS 鍵，將其設定為使用唯讀快取。</span><span class="sxs-lookup"><span data-stu-id="073ed-144">Install the App-V Desktop Client on the VDI Master VM Image, and then configure it to use the read-only cache by adding the following registry key values to the AppFS key on the client.</span></span> <span data-ttu-id="073ed-145">AppFS 鍵位於 HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\\ [Wow6432Node\\\] Microsoft\\SoftGrid\\4.5\\Client\\AppFS。</span><span class="sxs-lookup"><span data-stu-id="073ed-145">The AppFS key is located at HKEY\_LOCAL\_MACHINE\\SOFTWARE\\\[Wow6432Node\\\]Microsoft\\SoftGrid\\4.5\\Client\\AppFS.</span></span>

   <table>
   <colgroup>
   <col width="25%" />
   <col width="25%" />
   <col width="25%" />
   <col width="25%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="073ed-146">索引鍵</span><span class="sxs-lookup"><span data-stu-id="073ed-146">Key</span></span></th>
   <th align="left"><span data-ttu-id="073ed-147">類型</span><span class="sxs-lookup"><span data-stu-id="073ed-147">Type</span></span></th>
   <th align="left"><span data-ttu-id="073ed-148">值</span><span class="sxs-lookup"><span data-stu-id="073ed-148">Value</span></span></th>
   <th align="left"><span data-ttu-id="073ed-149">用途</span><span class="sxs-lookup"><span data-stu-id="073ed-149">Purpose</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="073ed-150">FileName</span><span class="sxs-lookup"><span data-stu-id="073ed-150">FileName</span></span></p></td>
   <td align="left"><p><span data-ttu-id="073ed-151">字串</span><span class="sxs-lookup"><span data-stu-id="073ed-151">String</span></span></p></td>
   <td align="left"><p><span data-ttu-id="073ed-152">FSD 路徑</span><span class="sxs-lookup"><span data-stu-id="073ed-152">path to FSD</span></span></p></td>
   <td align="left"><p><span data-ttu-id="073ed-153">指定共用快取檔案的路徑，例如 \VDIServername\Sharefolder\SFTFS。FSD （必要）。</span><span class="sxs-lookup"><span data-stu-id="073ed-153">Specifies the path to the shared cache file, for example, \VDIServername\Sharefolder\SFTFS.FSD (Required).</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="073ed-154">ReadOnlyFSD</span><span class="sxs-lookup"><span data-stu-id="073ed-154">ReadOnlyFSD</span></span></p></td>
   <td align="left"><p><span data-ttu-id="073ed-155">DWORD</span><span class="sxs-lookup"><span data-stu-id="073ed-155">DWORD</span></span></p></td>
   <td align="left"><p><span data-ttu-id="073ed-156">sr-1</span><span class="sxs-lookup"><span data-stu-id="073ed-156">1</span></span></p></td>
   <td align="left"><p><span data-ttu-id="073ed-157">將用戶端配置為以唯讀模式運作。</span><span class="sxs-lookup"><span data-stu-id="073ed-157">Configures the client to operate in Read-Only mode.</span></span> <span data-ttu-id="073ed-158">這可確保用戶端不會嘗試將更新資料流程傳輸到套件快取。</span><span class="sxs-lookup"><span data-stu-id="073ed-158">This ensures that the client will not attempt to stream updates to the package cache.</span></span> <span data-ttu-id="073ed-159">(必要項)</span><span class="sxs-lookup"><span data-stu-id="073ed-159">(Required)</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="073ed-160">ErrorLogLocation</span><span class="sxs-lookup"><span data-stu-id="073ed-160">ErrorLogLocation</span></span></p></td>
   <td align="left"><p><span data-ttu-id="073ed-161">字串</span><span class="sxs-lookup"><span data-stu-id="073ed-161">String</span></span></p></td>
   <td align="left"><p><span data-ttu-id="073ed-162">錯誤記錄（.etl）檔案的路徑</span><span class="sxs-lookup"><span data-stu-id="073ed-162">path to error log (.etl) file</span></span></p></td>
   <td align="left"><p><span data-ttu-id="073ed-163">用來指定錯誤記錄路徑的專案。</span><span class="sxs-lookup"><span data-stu-id="073ed-163">Entry used to specify the path to the error log.</span></span> <span data-ttu-id="073ed-164">採用.</span><span class="sxs-lookup"><span data-stu-id="073ed-164">(Recommended.</span></span> <span data-ttu-id="073ed-165">使用本機路徑（例如 C:\Logs\Sftfs.etl）。</span><span class="sxs-lookup"><span data-stu-id="073ed-165">Use a local path such as C:\Logs\Sftfs.etl).</span></span></p></td>
   </tr>
   </tbody>
   </table>

     

7. <span data-ttu-id="073ed-166">將主 VM 影像用戶端設定為使用發佈伺服器，並在登入時使用發佈重新整理。</span><span class="sxs-lookup"><span data-stu-id="073ed-166">Configure the Master VM Image client to use the publishing server and to use publishing refresh at logon.</span></span> <span data-ttu-id="073ed-167">當使用者登入 VDI 系統，且其 VM 是從主 VM 影像建立時，會發生發佈重新整理迴圈，併發布其帳戶已獲得授權的所有應用程式。</span><span class="sxs-lookup"><span data-stu-id="073ed-167">As users log on to the VDI system and their VM is built from the Master VM Image, a publishing refresh cycle occurs and publishes all the applications for which their account is authorized.</span></span> <span data-ttu-id="073ed-168">這些應用程式是從共用的快取中執行。</span><span class="sxs-lookup"><span data-stu-id="073ed-168">These applications are run from the shared cache.</span></span>

**<span data-ttu-id="073ed-169">在共用 VM 案例中設定用戶端進行套件升級</span><span class="sxs-lookup"><span data-stu-id="073ed-169">To configure the client for package upgrade in a Pooled VM scenario</span></span>**

1.  <span data-ttu-id="073ed-170">完成應用程式套件的升級與測試。</span><span class="sxs-lookup"><span data-stu-id="073ed-170">Complete the upgrade and testing of the application package.</span></span>

2.  <span data-ttu-id="073ed-171">在 App-V 伺服器上升級套件。</span><span class="sxs-lookup"><span data-stu-id="073ed-171">Upgrade the package on the App-V server.</span></span> <span data-ttu-id="073ed-172">然後，在暫存電腦上將新版本的應用程式發佈並資料流程到用戶端，讓它們完全載入到快取中。</span><span class="sxs-lookup"><span data-stu-id="073ed-172">Then, publish and stream the new version of the applications to the client on the staging computer so that they are fully loaded into cache.</span></span>

3.  <span data-ttu-id="073ed-173">在安全模式中重新開機暫存電腦，以確保驅動程式不會啟動。</span><span class="sxs-lookup"><span data-stu-id="073ed-173">Restart the staging computer in Safe Mode to ensure the drivers are not started.</span></span>

    <span data-ttu-id="073ed-174">**記事** 或者，您可以在 services.msc 中停止並停用應用程式虛擬化服務，然後重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="073ed-174">**Note** Alternatively, you can stop and disable the Application Virtualization service in the Services.msc, and then restart the computer.</span></span> <span data-ttu-id="073ed-175">複製檔案之後，請記得再次啟用並啟動該服務。</span><span class="sxs-lookup"><span data-stu-id="073ed-175">After the file has been copied, remember to enable and start the service again.</span></span>

     

4.  <span data-ttu-id="073ed-176">將 Sftfs fsd cache 檔案複製到 VDI 伺服器的 SAN 中，所有 Vm 都可以存取，例如共用資料夾。</span><span class="sxs-lookup"><span data-stu-id="073ed-176">Copy the Sftfs.fsd cache file to the VDI server’s SAN where all the VMs can access it, such as in a shared folder.</span></span> <span data-ttu-id="073ed-177">您可以使用不同的檔案名，例如，SFTFS \ _V2。FSD，以區別新版本。</span><span class="sxs-lookup"><span data-stu-id="073ed-177">You can use a different filename, for example, SFTFS\_V2.FSD, to distinguish the new version.</span></span>

5.  <span data-ttu-id="073ed-178">若要在 VDI 主 VM 影像上設定 App-v Desktop 用戶端，以使用更新的共用快取檔案，請將 AppFS 登錄項檔案名值設為指向更新檔案的位置，例如 \\\\VDIServername\\Sharefolder\\SFTFS\ _V2。FSD.</span><span class="sxs-lookup"><span data-stu-id="073ed-178">To configure the App-V Desktop Client on the VDI Master VM Image to use the updated shared cache file, change the AppFS registry key FILENAME value to point to the location of the updated file, for example, \\\\VDIServername\\Sharefolder\\SFTFS\_V2.FSD.</span></span> <span data-ttu-id="073ed-179">當使用者登出後再重新登入時，會使用更新的主映射建立新的 VM。</span><span class="sxs-lookup"><span data-stu-id="073ed-179">When users log off and then log on again, a new VM is created for them by using the updated Master Image.</span></span> <span data-ttu-id="073ed-180">其所有使用者設定將會保留並套用至新的 VM。</span><span class="sxs-lookup"><span data-stu-id="073ed-180">All their user settings will be retained and applied to the new VM.</span></span> <span data-ttu-id="073ed-181">然後他們就能存取已更新的應用程式。</span><span class="sxs-lookup"><span data-stu-id="073ed-181">Then they have access to the updated applications.</span></span>

**<span data-ttu-id="073ed-182">在靜態 VM 案例中設定用戶端進行套件升級</span><span class="sxs-lookup"><span data-stu-id="073ed-182">To configure the client for package upgrade in a Static VM scenario</span></span>**

1.  <span data-ttu-id="073ed-183">完成應用程式套件的升級與測試。</span><span class="sxs-lookup"><span data-stu-id="073ed-183">Complete the upgrade and testing of the application package.</span></span>

2.  <span data-ttu-id="073ed-184">在 App-V 伺服器上升級套件。</span><span class="sxs-lookup"><span data-stu-id="073ed-184">Upgrade the package on the App-V server.</span></span> <span data-ttu-id="073ed-185">然後，在暫存電腦上將新版本的應用程式發佈並資料流程到用戶端，讓應用程式完全載入到快取中。</span><span class="sxs-lookup"><span data-stu-id="073ed-185">Then, publish and stream the new version of the applications to the client on the staging computer so that the applications are fully loaded into cache.</span></span>

3.  <span data-ttu-id="073ed-186">在安全模式中重新開機暫存電腦，以確保驅動程式不會啟動。</span><span class="sxs-lookup"><span data-stu-id="073ed-186">Restart the staging computer in Safe Mode to ensure that the drivers are not started.</span></span>

    <span data-ttu-id="073ed-187">**記事** 或者，您可以在 services.msc 中停止並停用應用程式虛擬化服務，然後重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="073ed-187">**Note** Alternatively, you can stop and disable the Application Virtualization service in the Services.msc, and then restart the computer.</span></span> <span data-ttu-id="073ed-188">複製檔案之後，請記得再次啟用並啟動該服務。</span><span class="sxs-lookup"><span data-stu-id="073ed-188">After the file has been copied, remember to enable and start the service again.</span></span>

     

4.  <span data-ttu-id="073ed-189">將 Sftfs fsd cache 檔案複製到 VDI 伺服器的 SAN 中，所有 Vm 都可以存取，例如共用資料夾。</span><span class="sxs-lookup"><span data-stu-id="073ed-189">Copy the Sftfs.fsd cache file to the VDI server’s SAN where all the VMs can access it, such as in a shared folder.</span></span> <span data-ttu-id="073ed-190">您可以使用不同的檔案名，例如，SFTFS \ _V2。FSD，以區別新版本。</span><span class="sxs-lookup"><span data-stu-id="073ed-190">You can use a different filename, for example, SFTFS\_V2.FSD, to distinguish the new version.</span></span>

5.  <span data-ttu-id="073ed-191">若要在 VDI 主 VM 影像上設定 App-v Desktop 用戶端，以使用更新的共用快取檔案，請將 AppFS 登錄項檔案名值設為指向更新檔案的位置，例如 \\\\VDIServername\\Sharefolder\\SFTFS\ _V2。FSD.</span><span class="sxs-lookup"><span data-stu-id="073ed-191">To configure the App-V Desktop Client on the VDI Master VM Image to use the updated shared cache file, change the AppFS registry key FILENAME value to point to the location of the updated file, for example, \\\\VDIServername\\Sharefolder\\SFTFS\_V2.FSD.</span></span> <span data-ttu-id="073ed-192">這可確保新使用者能取得新版本。</span><span class="sxs-lookup"><span data-stu-id="073ed-192">This ensures that new users get the new version.</span></span>

6.  <span data-ttu-id="073ed-193">建立編輯 AppFS 鍵檔案名值的腳本，以將其設定為更新快取的位置，例如，\\\\VDIServername\\Sharefolder\\SFTFS\ [_V2]。FSD.</span><span class="sxs-lookup"><span data-stu-id="073ed-193">Create a script that edits the AppFS key FILENAME value to set it to the location of the updated cache, for example, \\\\VDIServername\\Sharefolder\\SFTFS\_V2.FSD.</span></span> <span data-ttu-id="073ed-194">將此腳本設定為在使用者登入或登入時執行，讓它在 App V 用戶端驅動程式啟動之前執行，例如使用群組原則設定。</span><span class="sxs-lookup"><span data-stu-id="073ed-194">Configure this script to run when the user logs off or logs on so that it runs before the App-V client drivers start, for example, by using Group Policy settings.</span></span> <span data-ttu-id="073ed-195">當使用者登出並再次登入時，他們現有的 VM 就會更新，而且會使用更新的快取複本。</span><span class="sxs-lookup"><span data-stu-id="073ed-195">When users log off and log on again, their existing VM is updated, and they will use the updated copy of the cache.</span></span> <span data-ttu-id="073ed-196">然後，他們就能存取已更新的應用程式。</span><span class="sxs-lookup"><span data-stu-id="073ed-196">Then, they have access to the updated applications.</span></span>

## <span data-ttu-id="073ed-197">如何在升級快取時使用符號連結</span><span class="sxs-lookup"><span data-stu-id="073ed-197">How to Use Symbolic Links when Upgrading the Cache</span></span>


<span data-ttu-id="073ed-198">您可以在下列作業系統中使用符號連結，而不是在每次部署新的快取檔案時，不修改 AppFS 金鑰檔案名值： Windows Vista、Windows 7 和 Windows Server 2008。</span><span class="sxs-lookup"><span data-stu-id="073ed-198">Instead of modifying the AppFS key FILENAME value every time that a new cache file is deployed that contains new or upgraded packages, you can use a symbolic link in the following operating systems: Windows Vista, Windows 7, and Windows Server 2008.</span></span> <span data-ttu-id="073ed-199">如需符號連結的詳細資訊，請參閱[符號連結](https://go.microsoft.com/fwlink/?LinkId=157626)（ https://go.microsoft.com/fwlink/?LinkId=157626) 。</span><span class="sxs-lookup"><span data-stu-id="073ed-199">For more information about symbolic links, see [Symbolic Links](https://go.microsoft.com/fwlink/?LinkId=157626) (https://go.microsoft.com/fwlink/?LinkId=157626).</span></span> <span data-ttu-id="073ed-200">相反地，Windows XP 不支援使用符號連結，而且您必須改用連接點。</span><span class="sxs-lookup"><span data-stu-id="073ed-200">In contrast, Windows XP does not support the use of symbolic links, and you must use junction points instead.</span></span> <span data-ttu-id="073ed-201">如需交接的詳細資訊，請參閱 Microsoft 知識庫中的[文章 205524](https://go.microsoft.com/fwlink/?LinkId=182553) （以及 https://go.microsoft.com/fwlink/?LinkId=182553) 工具[交叉口 v 1.05](https://go.microsoft.com/fwlink/?LinkId=182554) （） https://go.microsoft.com/fwlink/?LinkId=182554) 。</span><span class="sxs-lookup"><span data-stu-id="073ed-201">For more information about junctions, see [article 205524](https://go.microsoft.com/fwlink/?LinkId=182553) in the Microsoft Knowledge Base (https://go.microsoft.com/fwlink/?LinkId=182553), and also the tool [Junction v1.05](https://go.microsoft.com/fwlink/?LinkId=182554) (https://go.microsoft.com/fwlink/?LinkId=182554).</span></span>

**<span data-ttu-id="073ed-202">設定符號連結以參照快取</span><span class="sxs-lookup"><span data-stu-id="073ed-202">To configure a symbolic link to reference the cache</span></span>**

1.  <span data-ttu-id="073ed-203">在初始部署階段中，以 VDI 伺服器主機作業系統上的本機系統管理員身分開啟命令提示字元視窗。</span><span class="sxs-lookup"><span data-stu-id="073ed-203">During the initial deployment stage, open a Command Prompt window as a local administrator on the VDI server host operating system.</span></span>

2.  <span data-ttu-id="073ed-204">使用 MKLINK 命令建立符號連結，然後將它設定為指向 Sftfs fsd 檔案。</span><span class="sxs-lookup"><span data-stu-id="073ed-204">Create a symbolic link by using the MKLINK command, and then configure it to point to the Sftfs.fsd file.</span></span>

    **     <span data-ttu-id="073ed-205">mklink symlinkname \\\\vdihostserver\\sharefolder\\sftfs.fsd</span><span class="sxs-lookup"><span data-stu-id="073ed-205">mklink symlinkname \\\\vdihostserver\\sharefolder\\sftfs.fsd</span></span>**

3.  <span data-ttu-id="073ed-206">在 VDI 主 VM 影像中，使用 [**以系統管理員身分執行**] 選項來開啟命令提示字元視窗，然後授與遠端連結許可權，讓 VM 可以存取 VDI 主機作業系統上的符號連結。</span><span class="sxs-lookup"><span data-stu-id="073ed-206">On the VDI Master VM Image, open a Command Prompt window by using the **Run as administrator** option and grant remote link permissions so that the VM can access the symbolic link on the VDI Host operating system.</span></span> <span data-ttu-id="073ed-207">根據預設，遠端連結許可權是停用的。</span><span class="sxs-lookup"><span data-stu-id="073ed-207">By default, remote link permissions are disabled.</span></span>

    **<span data-ttu-id="073ed-208">fsutil behavior set SymlinkEvaluation R2R：1</span><span class="sxs-lookup"><span data-stu-id="073ed-208">fsutil behavior set SymlinkEvaluation R2R:1</span></span>**

    <span data-ttu-id="073ed-209">**記事** 在 storage server 上，必須啟用適當的連結許可權。</span><span class="sxs-lookup"><span data-stu-id="073ed-209">**Note** On the storage server, appropriate link permissions must be enabled.</span></span> <span data-ttu-id="073ed-210">視連結的位置和 Sftfs 的 fsd 檔案而定，許可權是**L2L： 1**或**L2R：** 1 或**R2L** ：1或 R2R： 1**或：1。**</span><span class="sxs-lookup"><span data-stu-id="073ed-210">Depending on the location of link and the Sftfs.fsd file, the permissions are **L2L:1** or **L2R:1** or **R2L:1** or **R2R:1**.</span></span>

     

4.  <span data-ttu-id="073ed-211">當您在 VDI 主 VM 影像上設定 App-v Desktop 用戶端時，請將 AppFS 項 FILENAME 值設為等於使用符號連結之 FSD 檔案的 UNC 路徑;例如，將它設定為 \\\\VDIHostserver\\Symlinkname。</span><span class="sxs-lookup"><span data-stu-id="073ed-211">When you configure the App-V Desktop Client on the VDI Master VM Image, set the AppFS key FILENAME value equal to the UNC path of the FSD file that is using the symbolic link; for example, set it to \\\\VDIHostserver\\Symlinkname.</span></span> <span data-ttu-id="073ed-212">當 App-v 用戶端第一次存取快取時，符號連結會傳送到用戶端的快取檔案控制碼。</span><span class="sxs-lookup"><span data-stu-id="073ed-212">When the App-V client first accesses the cache, the symbolic link passes to the client a handle to the cache file.</span></span> <span data-ttu-id="073ed-213">只要用戶端執行，用戶端就會繼續使用該控制碼。</span><span class="sxs-lookup"><span data-stu-id="073ed-213">The client continues to use that handle as long as the client is running.</span></span> <span data-ttu-id="073ed-214">即使現有用戶端已開啟舊的共用快取，您也可以安全地更新符號連結的值。</span><span class="sxs-lookup"><span data-stu-id="073ed-214">The value of the symbolic link can safely be updated even if existing clients have the old shared cache open.</span></span>

5.  <span data-ttu-id="073ed-215">當您必須升級套件，或將新套件新增至快取時，請針對靜態 VM 或彙集 VM 案例，執行步驟1到5的升級程式。</span><span class="sxs-lookup"><span data-stu-id="073ed-215">When you must upgrade a package or to add a new package to the cache, follow steps 1 through 5 of the upgrade procedure for either the Static VM or Pooled VM scenario.</span></span> <span data-ttu-id="073ed-216">然後，刪除符號連結，然後重新建立，以指向共用快取檔案的新版本。</span><span class="sxs-lookup"><span data-stu-id="073ed-216">Then, delete the symbolic link and re-create it to point to the new version of the shared cache file.</span></span> <span data-ttu-id="073ed-217">當 VM 重新開機時，用戶端會收到更新的快取複本複本，因為 VM 使用的路徑包含已更新的符號連結。</span><span class="sxs-lookup"><span data-stu-id="073ed-217">When the VM is restarted, the client receives a handle to the updated copy of the cache because the VM uses the path that contains the updated symbolic link.</span></span> <span data-ttu-id="073ed-218">然後，使用者可以存取新的和更新的應用程式。</span><span class="sxs-lookup"><span data-stu-id="073ed-218">Then, the users have access to the new and updated applications.</span></span>

## <span data-ttu-id="073ed-219">相關主題</span><span class="sxs-lookup"><span data-stu-id="073ed-219">Related topics</span></span>


[<span data-ttu-id="073ed-220">如何安裝 Application Virtualization Management Server</span><span class="sxs-lookup"><span data-stu-id="073ed-220">How to Install Application Virtualization Management Server</span></span>](how-to-install-application-virtualization-management-server.md)

[<span data-ttu-id="073ed-221">如何手動安裝 Application Virtualization Client</span><span class="sxs-lookup"><span data-stu-id="073ed-221">How to Manually Install the Application Virtualization Client</span></span>](how-to-manually-install-the-application-virtualization-client.md)

[<span data-ttu-id="073ed-222">如何使用命令列安裝用戶端</span><span class="sxs-lookup"><span data-stu-id="073ed-222">How to Install the Client by Using the Command Line</span></span>](how-to-install-the-client-by-using-the-command-line-new.md)

 

 





