---
title: 如何為 App-V 設定 Microsoft SQL Server 鏡像支援
description: 如何為 App-V 設定 Microsoft SQL Server 鏡像支援
author: dansimp
ms.assetid: 6d069eb5-109f-460a-836a-de49473b7035
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: fb572442cd12bb32fc9406de65f05a3bf061f946
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801614"
---
# <span data-ttu-id="d6736-103">如何為 App-V 設定 Microsoft SQL Server 鏡像支援</span><span class="sxs-lookup"><span data-stu-id="d6736-103">How to Configure Microsoft SQL Server Mirroring Support for App-V</span></span>


<span data-ttu-id="d6736-104">您可以使用下列程式來設定您的 Microsoft Application Virtualization （App-v）環境，以使用 Microsoft SQL Server 資料庫鏡像。</span><span class="sxs-lookup"><span data-stu-id="d6736-104">You can use the following procedure to configure your Microsoft Application Virtualization (App-V) environment to use Microsoft SQL Server database mirroring.</span></span> <span data-ttu-id="d6736-105">設定資料庫鏡像可協助災害復原與容錯移轉案例。</span><span class="sxs-lookup"><span data-stu-id="d6736-105">Configuring database mirroring can help with disaster recovery and failover scenarios.</span></span> <span data-ttu-id="d6736-106">App-V 4.5 SP2 支援 Microsoft SQL Server 2005 和 SQL Server 2008 目前可使用的所有資料庫鏡像模式。</span><span class="sxs-lookup"><span data-stu-id="d6736-106">App-V 4.5 SP2 supports all modes of database mirroring currently available for Microsoft SQL Server 2005 and SQL Server 2008.</span></span>

**<span data-ttu-id="d6736-107">注意</span><span class="sxs-lookup"><span data-stu-id="d6736-107">Note</span></span>**  
<span data-ttu-id="d6736-108">這個程式是針對熟悉使用 Microsoft SQL Server 設定及設定 SQL Server 資料庫及資料庫鏡像的系統管理員所撰寫，因此只涵蓋 App-v 所特有的特定配置設定。</span><span class="sxs-lookup"><span data-stu-id="d6736-108">This procedure is written for administrators who are familiar with setting up and configuring SQL Server databases and database mirroring with Microsoft SQL Server, and therefore covers only the specific configuration settings that are unique to App-V.</span></span>



**<span data-ttu-id="d6736-109">設定您的 App-v 環境以使用 Microsoft SQL Server 資料庫鏡像</span><span class="sxs-lookup"><span data-stu-id="d6736-109">To configure your App-V environment to use Microsoft SQL Server database mirroring</span></span>**

1.  <span data-ttu-id="d6736-110">在資料庫鏡像的標準商務做法之後，設定 App V 資料庫的 SQL Server 資料庫鏡像。</span><span class="sxs-lookup"><span data-stu-id="d6736-110">Set up SQL Server database mirroring of the App-V database following your standard business practices for database mirroring.</span></span> <span data-ttu-id="d6736-111">針對執行 Microsoft SQL Server 資料庫鏡像的一般資訊，請使用下列連結：</span><span class="sxs-lookup"><span data-stu-id="d6736-111">Use the following links for general information about implementing Microsoft SQL Server database mirroring:</span></span>

    -   <span data-ttu-id="d6736-112">**MICROSOFT SQL 2005**-[設定資料庫鏡像](https://go.microsoft.com/fwlink/?LinkId=187478)（https://go.microsoft.com/fwlink/?LinkId=187478)</span><span class="sxs-lookup"><span data-stu-id="d6736-112">**Microsoft SQL 2005**—[Setting Up Database Mirroring](https://go.microsoft.com/fwlink/?LinkId=187478) (https://go.microsoft.com/fwlink/?LinkId=187478)</span></span>

    -   <span data-ttu-id="d6736-113">**MICROSOFT SQL 2008**-[設定資料庫鏡像](https://go.microsoft.com/fwlink/?LinkId=187477)（https://go.microsoft.com/fwlink/?LinkId=187477)</span><span class="sxs-lookup"><span data-stu-id="d6736-113">**Microsoft SQL 2008**—[Setting Up Database Mirroring](https://go.microsoft.com/fwlink/?LinkId=187477) (https://go.microsoft.com/fwlink/?LinkId=187477)</span></span>

    <span data-ttu-id="d6736-114">此外，您可以在[資料庫鏡像最佳做法和效能考慮](https://go.microsoft.com/fwlink/?LinkId=190270)（.）中找到最佳做法資訊 https://go.microsoft.com/fwlink/?LinkId=190270) 。</span><span class="sxs-lookup"><span data-stu-id="d6736-114">In addition, you can find Best Practices information in [Database Mirroring Best Practices and Performance Considerations](https://go.microsoft.com/fwlink/?LinkId=190270) (https://go.microsoft.com/fwlink/?LinkId=190270).</span></span>

2.  <span data-ttu-id="d6736-115">在設定鏡像之後，請確認 App-v 資料庫顯示狀態為 **[主體]、[已同步**處理]，且鏡像資料庫顯示狀態為 **[（鏡像]、[已同步處理/正在還原]）**。</span><span class="sxs-lookup"><span data-stu-id="d6736-115">After mirroring has been set up, verify that the App-V database shows a status of **(Principal, Synchronized)**, and the mirrored database shows a status of **(Mirror, Synchronized / Restoring)**.</span></span> <span data-ttu-id="d6736-116">先解決任何鏡像問題，然後再繼續進行下一個步驟。</span><span class="sxs-lookup"><span data-stu-id="d6736-116">Resolve any mirroring issues before proceeding to the next step.</span></span> <span data-ttu-id="d6736-117">如需有關監控狀態的其他資訊，請參閱[監視鏡像狀態](https://go.microsoft.com/fwlink/?LinkId=190279)（ https://go.microsoft.com/fwlink/?LinkId=190279) 。</span><span class="sxs-lookup"><span data-stu-id="d6736-117">For additional information about monitoring the status, see [Monitoring Mirroring Status](https://go.microsoft.com/fwlink/?LinkId=190279) (https://go.microsoft.com/fwlink/?LinkId=190279).</span></span>

3.  <span data-ttu-id="d6736-118">在託管 app-v 資料庫鏡像的 sql server 電腦上，使用 [帳戶名稱\*\* &lt; 網域 &gt; \\ &lt; ManagementServerHostName &gt; $ \*\*] 建立 app-v 管理伺服器的網路服務帳戶的 sql server 登入。</span><span class="sxs-lookup"><span data-stu-id="d6736-118">On the SQL Server computer that hosts the mirror of the App-V database, create the SQL Server Login for the network service account of the App-V Management Server by using the account name **&lt;domain&gt;\\&lt;ManagementServerHostName&gt;$**.</span></span>

4.  <span data-ttu-id="d6736-119">在 App-V 管理伺服器上安裝 Microsoft SQL Server Native Client，以及在執行 App-v Management Web 服務的電腦（如果安裝在其他電腦上的話）。</span><span class="sxs-lookup"><span data-stu-id="d6736-119">Install the Microsoft SQL Server Native Client on the App-V Management Server, and on the computer running the App-V Management Web Service if installed on a different computer.</span></span> <span data-ttu-id="d6736-120">如果您打算將其他 App-v 管理伺服器連線到鏡像的 SQL 資料庫以進行負載平衡，您也必須在這些電腦上安裝 Microsoft SQL Server Native 用戶端。</span><span class="sxs-lookup"><span data-stu-id="d6736-120">If you plan to have additional App-V Management Servers connect to the mirrored SQL database for load balancing, you must install the Microsoft SQL Server Native Client on those computers as well.</span></span> <span data-ttu-id="d6736-121">您可以從 microsoft 下載中心的 [ [MICROSOFT Sql server 2008 功能套件](https://go.microsoft.com/fwlink/?LinkId=187479)] 頁面下載 Microsoft Sql Server Native Client https://go.microsoft.com/fwlink/?LinkId=187479) 。</span><span class="sxs-lookup"><span data-stu-id="d6736-121">You can download the Microsoft SQL Server Native Client from the [Microsoft SQL Server 2008 Feature Pack](https://go.microsoft.com/fwlink/?LinkId=187479) page in the Microsoft Download Center (https://go.microsoft.com/fwlink/?LinkId=187479).</span></span>

5.  <span data-ttu-id="d6736-122">檢查登錄機碼**HKEY _LOCAL \ _MACHINE \\software\\microsoft\\softgrid\\4.5\\server\\sqlservername** ，並確認它只包含 SQL Server 的主機名稱。</span><span class="sxs-lookup"><span data-stu-id="d6736-122">Check the registry key **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Softgrid\\4.5\\Server\\SQLServerName** and make sure that it contains only the host name of the SQL Server.</span></span> <span data-ttu-id="d6736-123">如果它包含實例名稱（例如*serverhostname\\instancename*），則必須移除實例名稱。</span><span class="sxs-lookup"><span data-stu-id="d6736-123">If it includes an instance name, for example *serverhostname\\instancename*, the instance name must be removed.</span></span>

    **<span data-ttu-id="d6736-124">重要</span><span class="sxs-lookup"><span data-stu-id="d6736-124">Important</span></span>**  
    <span data-ttu-id="d6736-125">App-V 管理伺服器會使用 TCP/IP 網路文件庫，在啟用資料庫鏡像時與 SQL Server 通訊，因此不能使用實例名稱。</span><span class="sxs-lookup"><span data-stu-id="d6736-125">The App-V Management Server uses the TCP/IP networking library to communicate with the SQL Server when database mirroring is enabled, and therefore instance names cannot be used.</span></span> <span data-ttu-id="d6736-126">您必須在登錄機碼中指定埠號碼。</span><span class="sxs-lookup"><span data-stu-id="d6736-126">The port numbers must be specified in the registry keys instead.</span></span>



6.  <span data-ttu-id="d6736-127">檢查登錄機碼**HKEY _LOCAL \ _MACHINE \\software\\microsoft\\softgrid\\4.5\\server\\sqlserverport** ，並確認它包含在 sql Server 電腦上用於 sql 的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="d6736-127">Check the registry key **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Softgrid\\4.5\\Server\\SQLServerPort** and make sure that it contains the port number that is used for SQL on the SQL Server computer.</span></span> <span data-ttu-id="d6736-128">如果您使用的是命名實例，此金鑰值必須設定為命名實例所用的埠。</span><span class="sxs-lookup"><span data-stu-id="d6736-128">If you are using a named instance this key value must be set to the port that is used for the named instance.</span></span>

7.  <span data-ttu-id="d6736-129">建立登錄機碼**HKEY \ _LOCAL \ _MACHINE \\software\\microsoft\\softgrid\\4.5\\server\\sqlfailoverservername**做為 REG \ _SZ 然後將此值設定為裝載鏡像之 SQL Server 的主機名稱。</span><span class="sxs-lookup"><span data-stu-id="d6736-129">Create the registry key **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Softgrid\\4.5\\Server\\SQLFailoverServerName** as REG\_SZ and then set the value to the host name of the SQL Server that hosts the mirror.</span></span>

8.  <span data-ttu-id="d6736-130">建立登錄機碼**HKEY \ _LOCAL \ _MACHINE \\software\\microsoft\\softgrid\\4.5\\server\\sqlfailoverserverport**作為 DWORD，然後在執行 sql Server 的電腦上，將此值設定為使用 sql Server 託管鏡像的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="d6736-130">Create the registry key **HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\Softgrid\\4.5\\Server\\SQLFailoverServerPort** as DWORD and then set the value to the port number that is used for SQL on the computer that is running SQL Server to host the mirror.</span></span> <span data-ttu-id="d6736-131">如果您使用的是鏡像的命名實例，此鍵值必須設定為命名實例所用的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="d6736-131">If you are using a named instance for the mirror this key value must be set to the port number that is used for the named instance.</span></span>

9.  <span data-ttu-id="d6736-132">在執行 App-v Management Web 服務的電腦上，設定 [通用資料連結（UDL）] 文字檔。</span><span class="sxs-lookup"><span data-stu-id="d6736-132">On the computer that is running the App-V Management Web Service, configure the Universal Data Link (UDL) text file.</span></span> <span data-ttu-id="d6736-133">在安裝 App-v 的目錄中，按兩下**SftMgmt** ，然後指定下列值：</span><span class="sxs-lookup"><span data-stu-id="d6736-133">In the directory where App-V is installed, double-click **SftMgmt.udl** and specify the following values:</span></span>

    -   <span data-ttu-id="d6736-134">在 [**提供者**] 索引標籤上，選取 [OLE DB 提供者**SQL Server 原生用戶端 10.0**]。</span><span class="sxs-lookup"><span data-stu-id="d6736-134">On the **Provider** tab, select the OLE DB provider **SQL Server Native Client 10.0**.</span></span>

    -   <span data-ttu-id="d6736-135">按一下 **[下一步** **]，選取 [連線] 索引**標籤。在 [**伺服器名稱**] 方塊中，輸入 SQL 伺服器的伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="d6736-135">Click **Next** to select the **Connection** tab. In the **Server Name** box, enter the server name of the SQL Server.</span></span> <span data-ttu-id="d6736-136">接著，選取 [**使用 WINDOWS NT 整合的安全性**]。</span><span class="sxs-lookup"><span data-stu-id="d6736-136">Next, select **Use Windows NT Integrated Security**.</span></span> <span data-ttu-id="d6736-137">最後，按一下清單**選取資料庫**，然後選取 app-v 資料庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="d6736-137">Finally, click the list **Select the database**, and then select the App-V database name.</span></span>

    -   <span data-ttu-id="d6736-138">按一下 [**全部**] 索引標籤，然後選取 [專案**容錯移轉] 合作夥伴**。</span><span class="sxs-lookup"><span data-stu-id="d6736-138">Click the **All** tab, and then select the entry **Failover Partner**.</span></span> <span data-ttu-id="d6736-139">按一下 [**編輯值**]，然後輸入容錯移轉 SQL server 的伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="d6736-139">Click **Edit Value**, and then enter the server name of the failover SQL Server.</span></span> <span data-ttu-id="d6736-140">按一下 \[確定\] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="d6736-140">Click **OK**.</span></span>

    **<span data-ttu-id="d6736-141">重要</span><span class="sxs-lookup"><span data-stu-id="d6736-141">Important</span></span>**  
    <span data-ttu-id="d6736-142">App-v 系統會使用 Kerberos 驗證。</span><span class="sxs-lookup"><span data-stu-id="d6736-142">The App-V system uses Kerberos authentication.</span></span> <span data-ttu-id="d6736-143">因此，當您設定在 SQL Server 上啟用 Kerberos 驗證的 SQL 鏡像，且 SQL Server 服務在網域使用者帳戶下執行時，您必須手動設定 SPN。</span><span class="sxs-lookup"><span data-stu-id="d6736-143">Therefore, when you configure SQL mirroring where Kerberos Authentication is enabled on the SQL Server and the SQL Server service runs under a domain user account, you must manually configure an SPN.</span></span> <span data-ttu-id="d6736-144">如需詳細資訊，請參閱針對[分散式環境設定 App-v 管理一](https://go.microsoft.com/fwlink/?LinkId=203186)文中的「SQL 服務使用網域版帳戶」 https://go.microsoft.com/fwlink/?LinkId=203186) 。</span><span class="sxs-lookup"><span data-stu-id="d6736-144">For more information, see “When SQL Service Uses Domain-Based Account” in the article [Configuring App-V Administration for a Distributed Environment](https://go.microsoft.com/fwlink/?LinkId=203186) (https://go.microsoft.com/fwlink/?LinkId=203186).</span></span>



10. <span data-ttu-id="d6736-145">若要確認資料庫鏡像正常執行，請測試容錯移轉並確認 App-v 管理伺服器繼續正常運作。</span><span class="sxs-lookup"><span data-stu-id="d6736-145">To verify that database mirroring is running correctly, test the failover and confirm that the App-V Management Server continues to function correctly.</span></span>

    **<span data-ttu-id="d6736-146">重要</span><span class="sxs-lookup"><span data-stu-id="d6736-146">Important</span></span>**  
    <span data-ttu-id="d6736-147">請務必小心，並遵循您的標準商務做法，以確保系統操作不會在發生失敗時中斷。</span><span class="sxs-lookup"><span data-stu-id="d6736-147">Proceed with care, and follow your standard business practices to ensure that system operations are not disrupted in the event of a failure.</span></span>



~~~
After the failover has occurred successfully, as verified by using the SQL Server status monitoring information, right-click the **Applications** node in the App-V Management Console, and then select **Refresh**. The list of applications should display normally if the system is working correctly.
~~~

## <span data-ttu-id="d6736-148">相關主題</span><span class="sxs-lookup"><span data-stu-id="d6736-148">Related topics</span></span>


[<span data-ttu-id="d6736-149">如何在 Application Virtualization 伺服器管理主控台中執行系統管理工作</span><span class="sxs-lookup"><span data-stu-id="d6736-149">How to Perform Administrative Tasks in the Application Virtualization Server Management Console</span></span>](how-to-perform-administrative-tasks-in-the-application-virtualization-server-management-console.md)









