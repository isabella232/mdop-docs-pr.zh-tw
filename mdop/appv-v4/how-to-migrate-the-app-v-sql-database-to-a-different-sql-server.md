---
title: 如何將 App-V SQL 資料庫移轉至不同的 SQL Server
description: 如何將 App-V SQL 資料庫移轉至不同的 SQL Server
author: dansimp
ms.assetid: 353892a1-9327-4489-a19c-4ec7bd1b736f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e3d84b0cb328873db3722ad3eb9af6a2b442fdcf
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801270"
---
# <span data-ttu-id="6ac20-103">如何將 App-V SQL 資料庫移轉至不同的 SQL Server</span><span class="sxs-lookup"><span data-stu-id="6ac20-103">How to Migrate the App-V SQL Database to a Different SQL Server</span></span>


<span data-ttu-id="6ac20-104">下列程式詳細說明如何將 Microsoft Application Virtualization （App-v）管理伺服器的 SQL 資料庫遷移至不同的 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="6ac20-104">The following procedures describe in detail how to migrate the SQL database of the Microsoft Application Virtualization (App-V) Management Server to a different SQL Server.</span></span>

<span data-ttu-id="6ac20-105">**重要** 這個程式需要停止 App-v server 服務，這會讓使用者無法使用其應用程式。</span><span class="sxs-lookup"><span data-stu-id="6ac20-105">**Important** This procedure requires that the App-V server service is stopped and this will prevent end-users from using their applications.</span></span>

 

**<span data-ttu-id="6ac20-106">若要備份 app-v SQL 資料庫</span><span class="sxs-lookup"><span data-stu-id="6ac20-106">To back up the App-V SQL database</span></span>**

1.  <span data-ttu-id="6ac20-107">開啟 services.msc 程式，並在所有使用要遷移之資料庫的管理伺服器上停止 App-v Management Server 服務。</span><span class="sxs-lookup"><span data-stu-id="6ac20-107">Open the Services.msc program and stop the App-V Management Server service on all Management Servers that use the database to be migrated.</span></span>

2.  <span data-ttu-id="6ac20-108">在 App V 資料庫所在的電腦上，開啟 [SQL Server Management Studio]。</span><span class="sxs-lookup"><span data-stu-id="6ac20-108">On the computer where the App-V database is located, open SQL Server Management Studio.</span></span>

3.  <span data-ttu-id="6ac20-109">展開 [**資料庫**] 節點並找到 app-v 資料庫（預設名稱為 APPVIRT）。</span><span class="sxs-lookup"><span data-stu-id="6ac20-109">Expand the **Databases** node and locate the App-V database (default name is APPVIRT).</span></span>

4.  <span data-ttu-id="6ac20-110">以滑鼠右鍵按一下資料庫，然後選取 [**任務**]，然後選取 [**備份**]。</span><span class="sxs-lookup"><span data-stu-id="6ac20-110">Right-click the database and select **Tasks** and then select **Back Up**.</span></span>

5.  <span data-ttu-id="6ac20-111">確認 [**恢復模型**] 已設定為 [**簡易**]，且 [**備份類型**] 設定為 [**完整**]。</span><span class="sxs-lookup"><span data-stu-id="6ac20-111">Verify that **Recovery model** is set to **SIMPLE** and the **Backup type** is set to **Full**.</span></span> <span data-ttu-id="6ac20-112">如有需要，請變更 [**備份組**] 和 [**目的地**] 設定。</span><span class="sxs-lookup"><span data-stu-id="6ac20-112">Change the **Backup set** and **Destination** settings if it is necessary.</span></span>

6.  <span data-ttu-id="6ac20-113">按一下 **[確定]** 以備份資料庫。</span><span class="sxs-lookup"><span data-stu-id="6ac20-113">Click **OK** to back up the database.</span></span> <span data-ttu-id="6ac20-114">成功完成備份之後，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="6ac20-114">After the backup has completed successfully, click **OK**.</span></span>

7.  <span data-ttu-id="6ac20-115">開啟 Windows 資源管理器，然後流覽至包含資料庫備份檔案的資料夾，例如 APPVIRT。.BAK.</span><span class="sxs-lookup"><span data-stu-id="6ac20-115">Open Windows Explorer and browse to the folder that contains the database backup file, for example APPVIRT.BAK.</span></span> <span data-ttu-id="6ac20-116">將資料庫備份檔案複製到執行 SQL Server 的目的電腦。</span><span class="sxs-lookup"><span data-stu-id="6ac20-116">Copy the database backup file to the destination computer that is running SQL Server.</span></span>

**<span data-ttu-id="6ac20-117">將 App-v SQL 資料庫還原到目的地電腦</span><span class="sxs-lookup"><span data-stu-id="6ac20-117">To restore the App-V SQL database to the destination computer</span></span>**

1.  <span data-ttu-id="6ac20-118">在目的地電腦上，開啟 SQL Server Management Studio，以滑鼠右鍵按一下 [**資料庫**] 節點，然後選取 [**還原資料庫**]。</span><span class="sxs-lookup"><span data-stu-id="6ac20-118">On the destination computer, open SQL Server Management Studio, right-click the **Databases** node and select **Restore Database**.</span></span>

2.  <span data-ttu-id="6ac20-119">在 [**還原的來源**] 底下，選擇 [**從裝置**]，然後按一下 [**...**]。</span><span class="sxs-lookup"><span data-stu-id="6ac20-119">Under **Source for Restore**, choose **From device** and then click the “**…**”</span></span> <span data-ttu-id="6ac20-120">按鈕。</span><span class="sxs-lookup"><span data-stu-id="6ac20-120">button.</span></span>

3.  <span data-ttu-id="6ac20-121">在 [**指定備份**] 對話方塊中，確認**備份媒體**已設定為 [檔案] **，然後按一下**[**新增**]。</span><span class="sxs-lookup"><span data-stu-id="6ac20-121">In the **Specify Backup** dialog box, make sure that the **Backup Media** is set to **File** and then click **Add**.</span></span>

4.  <span data-ttu-id="6ac20-122">選取您從執行 SQL Server 的原始電腦複製的備份檔案，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="6ac20-122">Select the backup file that you copied from the original computer that is running SQL Server, and then click **OK**.</span></span>

5.  <span data-ttu-id="6ac20-123">按一下 **[確定]** ，然後按一下以選取要還原的備份組。</span><span class="sxs-lookup"><span data-stu-id="6ac20-123">Click **OK** and then click to select the backup set to restore.</span></span>

6.  <span data-ttu-id="6ac20-124">在 [**還原目的地**] 底下，按一下 [**資料庫**] 下拉式清單，然後選取 App-V 資料庫名稱（例如 APPVIRT）。</span><span class="sxs-lookup"><span data-stu-id="6ac20-124">Under **Destination for restore**, click the drop-down for **To database** and select the App-V database name, for example APPVIRT.</span></span>

7.  <span data-ttu-id="6ac20-125">按一下 **[確定]** 以開始還原。</span><span class="sxs-lookup"><span data-stu-id="6ac20-125">Click **OK** to start the restore.</span></span> <span data-ttu-id="6ac20-126">成功完成還原之後，按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="6ac20-126">After the restore has completed successfully, click **OK**.</span></span>

8.  <span data-ttu-id="6ac20-127">展開 [**安全性**] 節點，以滑鼠右鍵按一下 [**登錄**]，然後選取 **[新增登**入]。</span><span class="sxs-lookup"><span data-stu-id="6ac20-127">Expand the **Security** node, right-click **Logins** and select **New Login**.</span></span>

9.  <span data-ttu-id="6ac20-128">在 [**登入名稱**] 欄位中，以 DOMAIN\\SERVERNAME $ 的格式輸入 App V 管理伺服器的網路服務帳戶詳細資料。</span><span class="sxs-lookup"><span data-stu-id="6ac20-128">In the **Login Name** field, enter the Network Service account details for the App-V Management Server in the format of DOMAIN\\SERVERNAME$.</span></span>

10. <span data-ttu-id="6ac20-129">在 [**預設資料庫**] 下的 **[一般**] 頁面上，選取 app-v 資料庫名稱（例如 APPVIRT），然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="6ac20-129">On the **General** page under **Default database** select the App-V database name, for example, APPVIRT, and then click **OK**.</span></span>

11. <span data-ttu-id="6ac20-130">在 [**選取頁面**] 底下，按一下以選取 [**使用者對應**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="6ac20-130">Under **Select a page**, click to select the **User Mapping** page.</span></span> <span data-ttu-id="6ac20-131">在 [**對應至此登**入的使用者] 下，按一下 [**對應**] 欄中的核取方塊以選取 app-v 資料庫。</span><span class="sxs-lookup"><span data-stu-id="6ac20-131">Under **Users mapped to this login**, click the check box in the **Map** column to select the App-V database.</span></span>

12. <span data-ttu-id="6ac20-132">在 **： &lt; appvdatabasename &gt; 的 [資料庫角色成員資格**] 底下，按一下以選取 [ **SFTEveryone** ]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="6ac20-132">Under **Database role membership for: &lt;appvdatabasename&gt;**, click to select **SFTEveryone** and then click **OK**.</span></span>

13. <span data-ttu-id="6ac20-133">確定執行 SQL Server 的新電腦上的 Windows 防火牆已設定為允許 App-v Management Server 存取系統。</span><span class="sxs-lookup"><span data-stu-id="6ac20-133">Make sure that the Windows Firewall on the new computer that is running SQL Server is configured to allow the App-V Management Server to access the system.</span></span> <span data-ttu-id="6ac20-134">在 [**管理工具**] 底下，使用 [**高級安全性**] 程式的 Windows 防火牆，為 SQL Server 所使用的埠建立**入站規則**（預設為埠1433）。</span><span class="sxs-lookup"><span data-stu-id="6ac20-134">Under **Administrative Tools**, use the **Windows Firewall with Advanced Security** program to create an **Inbound Rule** for the port that is used by SQL Server (default is port 1433).</span></span>

**<span data-ttu-id="6ac20-135">遷移 app-v SQL Server 代理程式作業</span><span class="sxs-lookup"><span data-stu-id="6ac20-135">To migrate the App-V SQL Server Agent jobs</span></span>**

1.  <span data-ttu-id="6ac20-136">在執行 SQL Server 的原始電腦上，在 SQL Server Management Studio 中，展開 [ **Sql Server 代理程式**] 節點，然後展開 [**作業**] 節點。</span><span class="sxs-lookup"><span data-stu-id="6ac20-136">On the original computer that is running SQL Server, in SQL Server Management Studio, expand the **SQL Server Agent** node, and then expand the **Jobs** node.</span></span>

2.  <span data-ttu-id="6ac20-137">以滑鼠右鍵按一下下列四個 App-v 作業，然後選取 [**腳本作業] 做為 |建立至 |檔案，並**將每個腳本儲存到一個資料夾，並為每個腳本指定一個描述性的名稱。</span><span class="sxs-lookup"><span data-stu-id="6ac20-137">Right-click the following four App-V jobs and select **Script Job as | CREATE to | File**, and save each script to a folder and give each script a descriptive name.</span></span>

    -   **<span data-ttu-id="6ac20-138">Softgrid 資料庫（appvdbname）檢查使用方式歷程記錄</span><span class="sxs-lookup"><span data-stu-id="6ac20-138">Softgrid Database (appvdbname) Check Usage History</span></span>**

    -   **<span data-ttu-id="6ac20-139">Softgrid 資料庫（appvdbname）關閉孤立的會話</span><span class="sxs-lookup"><span data-stu-id="6ac20-139">Softgrid Database (appvdbname) Close Orphaned Sessions</span></span>**

    -   **<span data-ttu-id="6ac20-140">Softgrid 資料庫（appvdbname）強制大小限制</span><span class="sxs-lookup"><span data-stu-id="6ac20-140">Softgrid Database (appvdbname) Enforce Size Limit</span></span>**

    -   **<span data-ttu-id="6ac20-141">Softgrid 資料庫（appvdbname）監視警報/作業狀態</span><span class="sxs-lookup"><span data-stu-id="6ac20-141">Softgrid Database (appvdbname) Monitor Alert/Job Status</span></span>**

3.  <span data-ttu-id="6ac20-142">將四個腳本檔案（.sql）複製到執行 SQL Server 的目的電腦，並開啟 SQL Server Management Studio。</span><span class="sxs-lookup"><span data-stu-id="6ac20-142">Copy the four script files (.sql) to the destination computer that is running SQL Server and open SQL Server Management Studio.</span></span>

4.  <span data-ttu-id="6ac20-143">在 Windows 資源管理器中，以滑鼠右鍵按一下每個 .sql 檔案，然後按一下 [**執行**]。</span><span class="sxs-lookup"><span data-stu-id="6ac20-143">In Windows Explorer, right-click each .sql file and then click **Run**.</span></span> <span data-ttu-id="6ac20-144">每個腳本都會在 SQL Server Management Studio 中的查詢視窗中開啟。</span><span class="sxs-lookup"><span data-stu-id="6ac20-144">Each script will open in a query window in SQL Server Management Studio.</span></span> <span data-ttu-id="6ac20-145">針對每個腳本，按一下 [**執行**]，然後確認每個腳本都已順利完成。</span><span class="sxs-lookup"><span data-stu-id="6ac20-145">Click **Execute** for each script and verify that each is completed successfully.</span></span>

5.  <span data-ttu-id="6ac20-146">重新整理 [ **SQL Server 代理程式**] 節點下的 [**作業**] 節點，確認已成功建立四個作業。</span><span class="sxs-lookup"><span data-stu-id="6ac20-146">Refresh the **Jobs** node under the **SQL Server Agent** node and confirm that the four jobs are created successfully.</span></span>

**<span data-ttu-id="6ac20-147">更新 App V 管理伺服器的設定</span><span class="sxs-lookup"><span data-stu-id="6ac20-147">To update the configuration of the App-V Management Server</span></span>**

1.  <span data-ttu-id="6ac20-148">在 App-v Management Server 上，修改下列登錄機碼：</span><span class="sxs-lookup"><span data-stu-id="6ac20-148">On the App-V Management Server, modify the following registry keys:</span></span>

    -   <span data-ttu-id="6ac20-149">**SQLServerName**  =  SQLServerName &lt;newservername&gt;</span><span class="sxs-lookup"><span data-stu-id="6ac20-149">**SQLServerName** = &lt;newservername&gt;</span></span>

    -   <span data-ttu-id="6ac20-150">**SQLServerPort**  =  SQLServerPort &lt;newserverport&gt;</span><span class="sxs-lookup"><span data-stu-id="6ac20-150">**SQLServerPort** = &lt;newserverport&gt;</span></span>

    <span data-ttu-id="6ac20-151">然後重新開機 App-v server 服務。</span><span class="sxs-lookup"><span data-stu-id="6ac20-151">Then restart the App-V server service.</span></span>

2.  <span data-ttu-id="6ac20-152">流覽以尋找 App-v Management Server 安裝目錄下的 SftMgmt 檔案（預設為 C:\\program files Files\\Microsoft System Center App Virt 管理 Server\\App Virt 管理服務）。</span><span class="sxs-lookup"><span data-stu-id="6ac20-152">Browse to find the file SftMgmt.udl under the App-V Management Server installation directory (default is C:\\Program Files\\Microsoft System Center App Virt Management Server\\App Virt Management Service).</span></span> <span data-ttu-id="6ac20-153">以滑鼠右鍵按一下檔案，然後選取 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="6ac20-153">Right-click the file and select **Open**.</span></span>

3.  <span data-ttu-id="6ac20-154">**在 [連線**] 索引標籤上，輸入執行 SQL Server 之目的電腦的名稱，然後按一下 [**測試**連線]。</span><span class="sxs-lookup"><span data-stu-id="6ac20-154">On the **Connection** tab, enter the name of the destination computer that is running SQL Server, and then click **Test Connection**.</span></span> <span data-ttu-id="6ac20-155">測試成功時，請按一下 **[確定]** ，然後再按一下 **[確定]** 。</span><span class="sxs-lookup"><span data-stu-id="6ac20-155">When the test is successful, click **OK** and then click **OK** again.</span></span>

4.  <span data-ttu-id="6ac20-156">針對 4.5 SP2 之前的 App-v 管理伺服器版本，您必須更新 SQL 記錄設定。</span><span class="sxs-lookup"><span data-stu-id="6ac20-156">For App-V Management Server versions before 4.5 SP2, you must update the SQL Logging settings.</span></span> <span data-ttu-id="6ac20-157">在 [**伺服器群組**] 底下，以滑鼠右鍵按一下伺服器所屬的伺服器群組，然後選取 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="6ac20-157">Under **Server Groups**, right-click the server group the server is a member of and select **Properties**.</span></span>

5.  <span data-ttu-id="6ac20-158">按一下 [**記錄**] 索引標籤上的 **[選取 SQL 資料庫**專案]，然後按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="6ac20-158">On the **Logging** tab click to select the **SQL Database** entry and then click **Edit**.</span></span>

6.  <span data-ttu-id="6ac20-159">將**DNS 主機名稱**變更為執行 SQL Server 的新電腦的主機名稱，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="6ac20-159">Change the **DNS Host Name** to the host name of the new computer that is running SQL Server and then click **OK**.</span></span> <span data-ttu-id="6ac20-160">再按兩次 **[確定]** ，然後重新開機 app-v server 服務。</span><span class="sxs-lookup"><span data-stu-id="6ac20-160">Click **OK** two times more, and then restart the App-V server service.</span></span>

7.  <span data-ttu-id="6ac20-161">開啟 App V 管理主控台，以滑鼠右鍵按一下 [**應用程式**] 節點，**然後選取 [** 重新整理]。</span><span class="sxs-lookup"><span data-stu-id="6ac20-161">Open the App-V Management Console, right-click the **Applications** node and select **Refresh**.</span></span> <span data-ttu-id="6ac20-162">應用程式清單應該顯示為 [之前]。</span><span class="sxs-lookup"><span data-stu-id="6ac20-162">The list of applications should be displayed as before.</span></span>

 

 





