---
title: 如何在 App-V 用戶端 (RDS) 上設定唯讀快取
description: 如何在 App-V 用戶端 (RDS) 上設定唯讀快取
author: dansimp
ms.assetid: b6607fe2-6f92-4567-99f1-d8e3c8a591e0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a44844ae9ffc3497151be7713f6a43fda0ccd8fa
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801621"
---
# <span data-ttu-id="a3d38-103">如何在 App-V 用戶端 (RDS) 上設定唯讀快取</span><span class="sxs-lookup"><span data-stu-id="a3d38-103">How to Configure a Read-only Cache on the App-V Client (RDS)</span></span>


<span data-ttu-id="a3d38-104">**重要** 您必須執行 App-V 4.6、SP1，才能使用此程式。</span><span class="sxs-lookup"><span data-stu-id="a3d38-104">**Important** You must be running App-V 4.6, SP1 to use this procedure.</span></span>

 

<span data-ttu-id="a3d38-105">您可以使用已填入所有使用者所需的所有應用程式的共用快取來部署 App-v 用戶端。</span><span class="sxs-lookup"><span data-stu-id="a3d38-105">You can deploy the App-V client by using a shared cache that is populated with all the applications required for all users.</span></span> <span data-ttu-id="a3d38-106">然後，將 App-v 遠端桌面服務（RDS）用戶端設定為使用相同的快取檔案。</span><span class="sxs-lookup"><span data-stu-id="a3d38-106">Then you configure the App-V Remote Desktop Services (RDS) Clients to use the same cache file.</span></span> <span data-ttu-id="a3d38-107">使用者可以使用 App-v 發佈程式來獲准存取特定的應用程式。</span><span class="sxs-lookup"><span data-stu-id="a3d38-107">Users are granted access to specific applications by using the App-V publishing process.</span></span> <span data-ttu-id="a3d38-108">因為已預先預先載入所有應用程式的快取，所以當使用者啟動應用程式時，不會發生任何資料流程。</span><span class="sxs-lookup"><span data-stu-id="a3d38-108">Because the cache is already preloaded with all applications, no streaming occurs when a user starts an application.</span></span> <span data-ttu-id="a3d38-109">不過，您必須將用來預裝快取的套件放在支援即時資料流通訊協定（RTSP）資料流程的 App-v 伺服器上，並授予 App-v 用戶端的存取權限。</span><span class="sxs-lookup"><span data-stu-id="a3d38-109">However, the packages used to prepopulate the cache must be put on an App-V server that supports Real Time Streaming Protocol (RTSP) streaming and that grants access permissions to the App-V Clients.</span></span> <span data-ttu-id="a3d38-110">如果您使用 App-v 管理伺服器發佈應用程式，您可以使用它來提供此資料流程函數。</span><span class="sxs-lookup"><span data-stu-id="a3d38-110">If you publish the applications by using an App-V Management Server, you can use it to provide this streaming function.</span></span>

<span data-ttu-id="a3d38-111">**記事** 這些程式中所述的詳細資料僅做為範例。</span><span class="sxs-lookup"><span data-stu-id="a3d38-111">**Note** The details outlined in these procedures are intended as examples only.</span></span> <span data-ttu-id="a3d38-112">您可能會使用不同的方法來完成整個程式。</span><span class="sxs-lookup"><span data-stu-id="a3d38-112">You might use different methods to complete the overall process.</span></span>

 

## <span data-ttu-id="a3d38-113">在 RDS 案例中部署 App-v 用戶端</span><span class="sxs-lookup"><span data-stu-id="a3d38-113">Deploying the App-V Client in an RDS Scenario</span></span>


<span data-ttu-id="a3d38-114">部署程式是由四個主要任務所組成：</span><span class="sxs-lookup"><span data-stu-id="a3d38-114">The deployment process consists of four primary tasks:</span></span>

-   <span data-ttu-id="a3d38-115">建立及填充主共用的快取檔案</span><span class="sxs-lookup"><span data-stu-id="a3d38-115">Creating and populating the master shared cache file</span></span>

-   <span data-ttu-id="a3d38-116">將共用的快取檔案複製到伺服器儲存體</span><span class="sxs-lookup"><span data-stu-id="a3d38-116">Copying the shared cache file to the server storage</span></span>

-   <span data-ttu-id="a3d38-117">配置 App-v 用戶端軟體</span><span class="sxs-lookup"><span data-stu-id="a3d38-117">Configuring the App-V client software</span></span>

-   <span data-ttu-id="a3d38-118">在初始部署之後管理共用快取檔案的更新部署週期</span><span class="sxs-lookup"><span data-stu-id="a3d38-118">Managing the update deployment cycle for the shared cache file after the initial deployment</span></span>

<span data-ttu-id="a3d38-119">這些工作需要謹慎規劃。</span><span class="sxs-lookup"><span data-stu-id="a3d38-119">These tasks require careful planning.</span></span> <span data-ttu-id="a3d38-120">我們建議您為您的組織準備並記錄可重複使用的程式，以供貴組織追蹤。</span><span class="sxs-lookup"><span data-stu-id="a3d38-120">We recommend that you prepare and document a methodical, reproducible process for your organization to follow.</span></span> <span data-ttu-id="a3d38-121">這對於主共用快取檔案的準備及部署尤為重要，而且對於應用程式更新的持續管理，每一個都需要更新主共用快取。</span><span class="sxs-lookup"><span data-stu-id="a3d38-121">This is especially important for the preparation and deployment of the master shared cache file, and for the ongoing management of application updates, each of which require an update to the master shared cache.</span></span> <span data-ttu-id="a3d38-122">使用下列程式完成這些主要任務。</span><span class="sxs-lookup"><span data-stu-id="a3d38-122">Use the following procedures to complete these primary tasks.</span></span>

<span data-ttu-id="a3d38-123">**記事** 雖然您可以使用數種不同的方法發佈應用程式，但下列程式是以您使用 App-v 管理伺服器來發佈的程式為基礎。</span><span class="sxs-lookup"><span data-stu-id="a3d38-123">**Note** Although you can publish the applications by using several different methods, the following procedures are based on your using an App-V Management Server for publishing.</span></span>

 

**<span data-ttu-id="a3d38-124">針對初始部署設定唯讀快取</span><span class="sxs-lookup"><span data-stu-id="a3d38-124">To configure the read-only cache for initial deployment</span></span>**

1. <span data-ttu-id="a3d38-125">設定和設定 App-v 管理伺服器來提供使用者驗證及發佈支援。</span><span class="sxs-lookup"><span data-stu-id="a3d38-125">Set up and configure an App-V Management Server to provide user authentication and publishing support.</span></span>

2. <span data-ttu-id="a3d38-126">以所有使用者所需的所有應用程式套件填入此管理伺服器的 [內容] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="a3d38-126">Populate the Content folder of this Management Server with all the application packages required for all users.</span></span>

3. <span data-ttu-id="a3d38-127">設定已安裝應用程式 V 用戶端的暫存電腦。</span><span class="sxs-lookup"><span data-stu-id="a3d38-127">Set up a staging computer that has the App-V Client installed.</span></span> <span data-ttu-id="a3d38-128">使用可存取所有應用程式的帳戶登入暫存電腦，以便將一組完整的應用程式發佈到電腦，然後將應用程式流式處理成可完全載入。</span><span class="sxs-lookup"><span data-stu-id="a3d38-128">Log on to the staging computer by using an account that has access to all applications so that the complete set of applications are published to the computer, and then stream the applications to cache so that they are fully loaded.</span></span>

   **<span data-ttu-id="a3d38-129">重要</span><span class="sxs-lookup"><span data-stu-id="a3d38-129">Important</span></span>**  
   <span data-ttu-id="a3d38-130">暫存電腦所使用的作業系統類型和系統架構必須與應用程式 V 用戶端將執行的 Vm 所使用的相同。</span><span class="sxs-lookup"><span data-stu-id="a3d38-130">The staging computer must use the same operating system type and system architecture as those used by the VMs on which the App-V Client will run.</span></span>

     

4. <span data-ttu-id="a3d38-131">在安全模式中重新開機暫存電腦，以確保驅動程式未啟動，因為這會鎖定快取檔案。</span><span class="sxs-lookup"><span data-stu-id="a3d38-131">Restart the staging computer in safe mode to make sure that the drivers are not started, because this would lock the cache file.</span></span>

   **<span data-ttu-id="a3d38-132">注意</span><span class="sxs-lookup"><span data-stu-id="a3d38-132">Note</span></span>**  
   <span data-ttu-id="a3d38-133">或者，您可以停止並停用應用程式虛擬化服務，然後重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="a3d38-133">Or, you can stop and disable the Application Virtualization service, and then restart the computer.</span></span> <span data-ttu-id="a3d38-134">複製檔案之後，請記住要啟用並再次啟動該服務。</span><span class="sxs-lookup"><span data-stu-id="a3d38-134">After the file is copied, remember to enable and start the service again.</span></span>

     

5. <span data-ttu-id="a3d38-135">將 Sftfs fsd cache 檔案複製到 SAN，其中所有 RDS 伺服器都可以存取，例如共用資料夾。</span><span class="sxs-lookup"><span data-stu-id="a3d38-135">Copy the Sftfs.fsd cache file to a SAN where all the RDS servers can access it, such as in a shared folder.</span></span> <span data-ttu-id="a3d38-136">針對將管理快取檔案更新的管理員，將 [資料夾存取許可權] 設定為 [所有人都能使用唯讀] 和 [完全控制]。</span><span class="sxs-lookup"><span data-stu-id="a3d38-136">Set the folder access permissions to Read-only for the group Everyone and to Full Control for administrators who will manage the cache file updates.</span></span> <span data-ttu-id="a3d38-137">可以從 registry AppFS\\FileName. 取得快取檔案的位置</span><span class="sxs-lookup"><span data-stu-id="a3d38-137">The location of the cache file can be obtained from the registry AppFS\\FileName.</span></span>

   **<span data-ttu-id="a3d38-138">重要</span><span class="sxs-lookup"><span data-stu-id="a3d38-138">Important</span></span>**  
   <span data-ttu-id="a3d38-139">您必須將 FSD 檔案放在具有與本機附加儲存效能（例如 SAN）相同的回應與可靠性等位置。</span><span class="sxs-lookup"><span data-stu-id="a3d38-139">You must put the FSD file in a location that has the responsiveness and reliability equal to locally attached storage performance, for example, a SAN.</span></span>

     

6. <span data-ttu-id="a3d38-140">在每個 RDS 伺服器上安裝 app-v RDS 用戶端，然後將下列登錄機碼值新增到用戶端的 AppFS 鍵，將其設定為使用唯讀快取。</span><span class="sxs-lookup"><span data-stu-id="a3d38-140">Install the App-V RDS Client on each RDS server, and then configure it to use the read-only cache by adding the following registry key values to the AppFS key on the client.</span></span> <span data-ttu-id="a3d38-141">AppFS 鍵位於 HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\\] Microsoft\\SoftGrid\\4.5\\Client\\AppFS 32 位電腦，以及 HKEY \ _LOCAL \ 64 位電腦的 \\software\\wow6432node\\microsoft\\softgrid\\4.5\\client\\appfs \ \ _MACHINE。</span><span class="sxs-lookup"><span data-stu-id="a3d38-141">The AppFS key is located at HKEY\_LOCAL\_MACHINE\\SOFTWARE\\\]Microsoft\\SoftGrid\\4.5\\Client\\AppFS for 32-bit computers and at HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\SoftGrid\\4.5\\Client\\AppFS for 64-bit computers.</span></span>

   <table>
   <colgroup>
   <col width="25%" />
   <col width="25%" />
   <col width="25%" />
   <col width="25%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left"><span data-ttu-id="a3d38-142">索引鍵</span><span class="sxs-lookup"><span data-stu-id="a3d38-142">Key</span></span></th>
   <th align="left"><span data-ttu-id="a3d38-143">類型</span><span class="sxs-lookup"><span data-stu-id="a3d38-143">Type</span></span></th>
   <th align="left"><span data-ttu-id="a3d38-144">值</span><span class="sxs-lookup"><span data-stu-id="a3d38-144">Value</span></span></th>
   <th align="left"><span data-ttu-id="a3d38-145">用途</span><span class="sxs-lookup"><span data-stu-id="a3d38-145">Purpose</span></span></th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="a3d38-146">FileName</span><span class="sxs-lookup"><span data-stu-id="a3d38-146">FileName</span></span></p></td>
   <td align="left"><p><span data-ttu-id="a3d38-147">字串</span><span class="sxs-lookup"><span data-stu-id="a3d38-147">String</span></span></p></td>
   <td align="left"><p><span data-ttu-id="a3d38-148">FSD 路徑</span><span class="sxs-lookup"><span data-stu-id="a3d38-148">path of FSD</span></span></p></td>
   <td align="left"><p><span data-ttu-id="a3d38-149">指定共用快取檔案的路徑，例如 \RDSServername\Sharefolder\SFTFS。FSD （必要）。</span><span class="sxs-lookup"><span data-stu-id="a3d38-149">Specifies the path of the shared cache file, for example, \RDSServername\Sharefolder\SFTFS.FSD (Required).</span></span></p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><span data-ttu-id="a3d38-150">ReadOnlyFSD</span><span class="sxs-lookup"><span data-stu-id="a3d38-150">ReadOnlyFSD</span></span></p></td>
   <td align="left"><p><span data-ttu-id="a3d38-151">DWORD</span><span class="sxs-lookup"><span data-stu-id="a3d38-151">DWORD</span></span></p></td>
   <td align="left"><p><span data-ttu-id="a3d38-152">sr-1</span><span class="sxs-lookup"><span data-stu-id="a3d38-152">1</span></span></p></td>
   <td align="left"><p><span data-ttu-id="a3d38-153">將用戶端配置為以唯讀模式運作。</span><span class="sxs-lookup"><span data-stu-id="a3d38-153">Configures the client to operate in Read-Only mode.</span></span> <span data-ttu-id="a3d38-154">這可確保用戶端不會嘗試將更新資料流程傳輸到套件快取。</span><span class="sxs-lookup"><span data-stu-id="a3d38-154">This ensures that the client will not try to stream updates to the package cache.</span></span> <span data-ttu-id="a3d38-155">(必要項)</span><span class="sxs-lookup"><span data-stu-id="a3d38-155">(Required)</span></span></p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><span data-ttu-id="a3d38-156">ErrorLogLocation</span><span class="sxs-lookup"><span data-stu-id="a3d38-156">ErrorLogLocation</span></span></p></td>
   <td align="left"><p><span data-ttu-id="a3d38-157">字串</span><span class="sxs-lookup"><span data-stu-id="a3d38-157">String</span></span></p></td>
   <td align="left"><p><span data-ttu-id="a3d38-158">錯誤記錄（.etl）檔案的路徑</span><span class="sxs-lookup"><span data-stu-id="a3d38-158">path of error log (.etl) file</span></span></p></td>
   <td align="left"><p><span data-ttu-id="a3d38-159">用來指定錯誤記錄路徑的專案。</span><span class="sxs-lookup"><span data-stu-id="a3d38-159">Entry used to specify the path of the error log.</span></span> <span data-ttu-id="a3d38-160">採用.</span><span class="sxs-lookup"><span data-stu-id="a3d38-160">(Recommended.</span></span> <span data-ttu-id="a3d38-161">使用本機路徑（例如 C:\Logs\Sftfs.etl）。</span><span class="sxs-lookup"><span data-stu-id="a3d38-161">Use a local path such as C:\Logs\Sftfs.etl).</span></span></p></td>
   </tr>
   </tbody>
   </table>

     

7. <span data-ttu-id="a3d38-162">將伺服器陣列中的每個 RDS 伺服器設定為使用發佈伺服器，並在使用者登入時使用發佈更新。</span><span class="sxs-lookup"><span data-stu-id="a3d38-162">Configure each RDS server in the farm to use the publishing server and to use publishing update when users log on.</span></span> <span data-ttu-id="a3d38-163">當使用者登入 RDS 伺服器時，會發生發佈更新週期併發布其帳戶已獲得授權的所有應用程式。</span><span class="sxs-lookup"><span data-stu-id="a3d38-163">As users log on to the RDS servers, a publishing update cycle occurs and publishes all the applications for which their account is authorized.</span></span> <span data-ttu-id="a3d38-164">這些應用程式是從共用的快取中執行。</span><span class="sxs-lookup"><span data-stu-id="a3d38-164">These applications are run from the shared cache.</span></span>

**<span data-ttu-id="a3d38-165">設定 RDS 用戶端以進行套件升級</span><span class="sxs-lookup"><span data-stu-id="a3d38-165">To configure the RDS client for package upgrade</span></span>**

1.  <span data-ttu-id="a3d38-166">完成應用程式套件的升級與測試。</span><span class="sxs-lookup"><span data-stu-id="a3d38-166">Complete the upgrade and testing of the application package.</span></span>

2.  <span data-ttu-id="a3d38-167">在 App-V 伺服器上升級套件。</span><span class="sxs-lookup"><span data-stu-id="a3d38-167">Upgrade the package on the App-V server.</span></span> <span data-ttu-id="a3d38-168">然後，在暫存電腦上將新版本的應用程式發佈並資料流程到用戶端，讓它們完全載入到快取中。</span><span class="sxs-lookup"><span data-stu-id="a3d38-168">Then, publish and stream the new version of the applications to the client on the staging computer so that they are fully loaded into cache.</span></span>

3.  <span data-ttu-id="a3d38-169">在安全模式中重新開機暫存電腦，以確保驅動程式不會啟動。</span><span class="sxs-lookup"><span data-stu-id="a3d38-169">Restart the staging computer in safe mode to ensure the drivers are not started.</span></span>

    <span data-ttu-id="a3d38-170">**記事** 或者，您可以先停止並停用 services.msc 中的 Application Virtualization 服務，然後重新開機電腦。</span><span class="sxs-lookup"><span data-stu-id="a3d38-170">**Note** Or, you can first stop and then disable the Application Virtualization service in the Services.msc, and restart the computer.</span></span> <span data-ttu-id="a3d38-171">複製檔案之後，請記得再次啟用並啟動該服務。</span><span class="sxs-lookup"><span data-stu-id="a3d38-171">After the file has been copied, remember to enable and start the service again.</span></span>

     

4.  <span data-ttu-id="a3d38-172">將 Sftfs fsd cache 檔案複製到 SAN，其中所有 RDS 伺服器都可以存取，例如共用資料夾。</span><span class="sxs-lookup"><span data-stu-id="a3d38-172">Copy the Sftfs.fsd cache file to a SAN where all the RDS servers can access it, such as in a shared folder.</span></span> <span data-ttu-id="a3d38-173">您可以使用不同的檔案名，例如，SFTFS \ _V2。FSD，以區別新版本。</span><span class="sxs-lookup"><span data-stu-id="a3d38-173">You can use a different file name, for example, SFTFS\_V2.FSD, to distinguish the new version.</span></span>

5.  <span data-ttu-id="a3d38-174">若要在伺服器陣列中的每個 RDS 伺服器上設定 App-v RDS 用戶端，以使用更新的共用快取檔案，請將 AppFS 登錄項 FILENAME 值，以指向更新檔案的位置，例如 \\\\RDSServername\\Sharefolder\\SFTFS\ _V2。FSD.</span><span class="sxs-lookup"><span data-stu-id="a3d38-174">To configure the App-V RDS Client on each RDS server in the farm to use the updated shared cache file, change the AppFS registry key FILENAME value to point to the location of the updated file, for example, \\\\RDSServername\\Sharefolder\\SFTFS\_V2.FSD.</span></span> <span data-ttu-id="a3d38-175">這可保證在應用程式 Vclient 的驅動程式重新開機時，每個 RDS 伺服器都會收到更新的快取複本。</span><span class="sxs-lookup"><span data-stu-id="a3d38-175">This guarantees that each RDS server receives the updated copy of the cache when the App-Vclient drivers restart.</span></span>

    <span data-ttu-id="a3d38-176">**重要** 您必須重新開機 RDS 伺服器，才能使用更新的共用快取檔案。</span><span class="sxs-lookup"><span data-stu-id="a3d38-176">**Important** You must restart the RDS servers in order to use the updated shared cache file.</span></span>

     

## <span data-ttu-id="a3d38-177">如何在升級快取時使用符號連結</span><span class="sxs-lookup"><span data-stu-id="a3d38-177">How to Use Symbolic Links when Upgrading the Cache</span></span>


<span data-ttu-id="a3d38-178">您可以在下列作業系統中使用符號連結，而不是在每次部署新的快取檔案時，不會變更 AppFS 金鑰檔案名值： Windows Vista、Windows 7 和 Windows Server 2008。</span><span class="sxs-lookup"><span data-stu-id="a3d38-178">Instead of changing the AppFS key FILENAME value every time that a new cache file is deployed that contains new or upgraded packages, you can use a symbolic link in the following operating systems: Windows Vista, Windows 7, and Windows Server 2008.</span></span> <span data-ttu-id="a3d38-179">如需符號連結的詳細資訊，請參閱[符號連結](https://go.microsoft.com/fwlink/?LinkId=157626)（ https://go.microsoft.com/fwlink/?LinkId=157626) 。</span><span class="sxs-lookup"><span data-stu-id="a3d38-179">For more information about symbolic links, see [Symbolic Links](https://go.microsoft.com/fwlink/?LinkId=157626) (https://go.microsoft.com/fwlink/?LinkId=157626).</span></span> <span data-ttu-id="a3d38-180">相反地，Windows XP 不支援使用符號連結，而且您必須改用連接點。</span><span class="sxs-lookup"><span data-stu-id="a3d38-180">In contrast, Windows XP does not support the use of symbolic links, and you must use junction points instead.</span></span> <span data-ttu-id="a3d38-181">如需交接的詳細資訊，請參閱 Microsoft 知識庫中的[文章 205524](https://go.microsoft.com/fwlink/?LinkId=182553) （以及 https://go.microsoft.com/fwlink/?LinkId=182553) 工具[交叉口 v 1.05](https://go.microsoft.com/fwlink/?LinkId=182554) （） https://go.microsoft.com/fwlink/?LinkId=182554) 。</span><span class="sxs-lookup"><span data-stu-id="a3d38-181">For more information about junctions, see [article 205524](https://go.microsoft.com/fwlink/?LinkId=182553) in the Microsoft Knowledge Base (https://go.microsoft.com/fwlink/?LinkId=182553), and also the tool [Junction v1.05](https://go.microsoft.com/fwlink/?LinkId=182554) (https://go.microsoft.com/fwlink/?LinkId=182554).</span></span>

**<span data-ttu-id="a3d38-182">設定符號連結以參照快取</span><span class="sxs-lookup"><span data-stu-id="a3d38-182">To configure a symbolic link to reference the cache</span></span>**

1.  <span data-ttu-id="a3d38-183">在初始部署階段中，以 RDS 伺服器主機作業系統上的本機系統管理員身分開啟命令提示字元視窗。</span><span class="sxs-lookup"><span data-stu-id="a3d38-183">During the initial deployment stage, open a Command Prompt window as a local administrator on the RDS server host operating system.</span></span>

2.  <span data-ttu-id="a3d38-184">使用 MKLINK 命令建立符號連結，然後將它設定為指向 Sftfs fsd 檔案。</span><span class="sxs-lookup"><span data-stu-id="a3d38-184">Create a symbolic link by using the MKLINK command, and then configure it to point to the Sftfs.fsd file.</span></span>

    **     <span data-ttu-id="a3d38-185">mklink symlinkname \\\\rdshostserver\\sharefolder\\sftfs.fsd</span><span class="sxs-lookup"><span data-stu-id="a3d38-185">mklink symlinkname \\\\rdshostserver\\sharefolder\\sftfs.fsd</span></span>**

3.  <span data-ttu-id="a3d38-186">在 VDI 主 VM 影像中，使用 [**以系統管理員身分執行**] 選項來開啟命令提示字元視窗，然後授與遠端連結許可權，讓 VM 可以存取 VDI 主機作業系統上的符號連結。</span><span class="sxs-lookup"><span data-stu-id="a3d38-186">On the VDI Master VM Image, open a Command Prompt window by using the **Run as administrator** option and grant remote link permissions so that the VM can access the symbolic link on the VDI Host operating system.</span></span> <span data-ttu-id="a3d38-187">根據預設，遠端連結許可權是停用的。</span><span class="sxs-lookup"><span data-stu-id="a3d38-187">By default, remote link permissions are disabled.</span></span>

    **<span data-ttu-id="a3d38-188">fsutil behavior set SymlinkEvaluation R2R：1</span><span class="sxs-lookup"><span data-stu-id="a3d38-188">fsutil behavior set SymlinkEvaluation R2R:1</span></span>**

    <span data-ttu-id="a3d38-189">**記事** 在 storage server 上，必須啟用適當的連結許可權。</span><span class="sxs-lookup"><span data-stu-id="a3d38-189">**Note** On the storage server, appropriate link permissions must be enabled.</span></span> <span data-ttu-id="a3d38-190">視連結的位置和 Sftfs 的 fsd 檔案而定，許可權是**L2L： 1**或**L2R：** 1 或**R2L** ：1或 R2R： 1**或：1。**</span><span class="sxs-lookup"><span data-stu-id="a3d38-190">Depending on the location of link and the Sftfs.fsd file, the permissions are **L2L:1** or **L2R:1** or **R2L:1** or **R2R:1**.</span></span>

     

4.  <span data-ttu-id="a3d38-191">當您設定 App-v RDS 用戶端時，請將 AppFS 項 FILENAME 值設為等於使用符號連結之 FSD 檔案的 UNC 路徑。</span><span class="sxs-lookup"><span data-stu-id="a3d38-191">When you configure the App-V RDS Client, set the AppFS key FILENAME value equal to the UNC path of the FSD file that is using the symbolic link.</span></span> <span data-ttu-id="a3d38-192">例如，將檔案名設定為 \\\\VDIHostserver\\Symlinkname。</span><span class="sxs-lookup"><span data-stu-id="a3d38-192">For example, set the file name to \\\\VDIHostserver\\Symlinkname.</span></span> <span data-ttu-id="a3d38-193">當 App-v 用戶端第一次存取快取時，符號連結會傳送到用戶端的快取檔案控制碼。</span><span class="sxs-lookup"><span data-stu-id="a3d38-193">When the App-V client first accesses the cache, the symbolic link passes to the client a handle to the cache file.</span></span> <span data-ttu-id="a3d38-194">只要用戶端執行，用戶端就會繼續使用該控制碼。</span><span class="sxs-lookup"><span data-stu-id="a3d38-194">The client continues to use that handle as long as the client is running.</span></span> <span data-ttu-id="a3d38-195">即使現有用戶端已開啟舊的共用快取，您也可以安全地更新符號連結的值。</span><span class="sxs-lookup"><span data-stu-id="a3d38-195">The value of the symbolic link can safely be updated even if existing clients have the old shared cache open.</span></span>

5.  <span data-ttu-id="a3d38-196">當您必須升級套件，或將新套件新增至快取時，請依照升級程式的步驟1到4進行。</span><span class="sxs-lookup"><span data-stu-id="a3d38-196">When you must upgrade a package or to add a new package to the cache, follow steps 1 through 4 of the upgrade procedure.</span></span> <span data-ttu-id="a3d38-197">然後，刪除符號連結，然後重新建立，以指向共用快取檔案的新版本。</span><span class="sxs-lookup"><span data-stu-id="a3d38-197">Then, delete the symbolic link and re-create it to point to the new version of the shared cache file.</span></span> <span data-ttu-id="a3d38-198">這可確保當 App-v server 驅動程式重新開機時，每個 RDS 伺服器都會收到更新的快取複本。</span><span class="sxs-lookup"><span data-stu-id="a3d38-198">This guarantees that each RDS server receives the updated copy of the cache when the App-V client drivers restart.</span></span> <span data-ttu-id="a3d38-199">當您重新開機 RDS 伺服器時，App-v 用戶端會接收更新的快取複本複本，因為用戶端會使用包含更新符號連結的路徑。</span><span class="sxs-lookup"><span data-stu-id="a3d38-199">When the RDS server is restarted, the App-V client receives a handle to the updated copy of the cache because the client uses the path that contains the updated symbolic link.</span></span> <span data-ttu-id="a3d38-200">然後，使用者可以存取新的和更新的應用程式。</span><span class="sxs-lookup"><span data-stu-id="a3d38-200">Then, the users have access to the new and updated applications.</span></span>

## <span data-ttu-id="a3d38-201">相關主題</span><span class="sxs-lookup"><span data-stu-id="a3d38-201">Related topics</span></span>


[<span data-ttu-id="a3d38-202">如何安裝 Application Virtualization Management Server</span><span class="sxs-lookup"><span data-stu-id="a3d38-202">How to Install Application Virtualization Management Server</span></span>](how-to-install-application-virtualization-management-server.md)

[<span data-ttu-id="a3d38-203">如何手動安裝 Application Virtualization Client</span><span class="sxs-lookup"><span data-stu-id="a3d38-203">How to Manually Install the Application Virtualization Client</span></span>](how-to-manually-install-the-application-virtualization-client.md)

[<span data-ttu-id="a3d38-204">如何使用命令列安裝用戶端</span><span class="sxs-lookup"><span data-stu-id="a3d38-204">How to Install the Client by Using the Command Line</span></span>](how-to-install-the-client-by-using-the-command-line-new.md)

 

 





