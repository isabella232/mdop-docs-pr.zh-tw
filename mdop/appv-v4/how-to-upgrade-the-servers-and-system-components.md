---
title: 如何升級伺服器和系統元件
description: 如何升級伺服器和系統元件
author: dansimp
ms.assetid: 7d8374fe-5897-452e-923e-556a854b2024
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 61f8742a2f5e3c17083a77b839dfbee85ea00e24
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801016"
---
# <span data-ttu-id="42b12-103">如何升級伺服器和系統元件</span><span class="sxs-lookup"><span data-stu-id="42b12-103">How to Upgrade the Servers and System Components</span></span>


<span data-ttu-id="42b12-104">使用下列程式升級在所有應用程式虛擬化系統電腦上安裝的軟體元件。</span><span class="sxs-lookup"><span data-stu-id="42b12-104">Use the following procedure to upgrade software components installed on all Application Virtualization System computers.</span></span> <span data-ttu-id="42b12-105">在每個電腦升級之後，應用程式虛擬化系統服務將會自動重新開機。</span><span class="sxs-lookup"><span data-stu-id="42b12-105">Application Virtualization System services will be restarted automatically on each computer after it has been upgraded.</span></span>

**<span data-ttu-id="42b12-106">注意</span><span class="sxs-lookup"><span data-stu-id="42b12-106">Note</span></span>**  
-   <span data-ttu-id="42b12-107">升級程式會停止所有的應用程式虛擬化系統服務，因此，系統會讓系統停止服務。</span><span class="sxs-lookup"><span data-stu-id="42b12-107">The upgrade process stops all Application Virtualization System services, thereby taking the system out of service.</span></span> <span data-ttu-id="42b12-108">您必須先關閉使用者會話，才能開始升級程式，而且您應該停止在您的環境中的所有應用程式虛擬化伺服器服務。</span><span class="sxs-lookup"><span data-stu-id="42b12-108">User sessions should be shut down before you begin the upgrade process, and you should stop all Application Virtualization Server services in your environment.</span></span>

-   <span data-ttu-id="42b12-109">如果您有多個伺服器共用應用程式虛擬化資料庫的存取權，所有這些伺服器都必須在資料庫升級時離線。</span><span class="sxs-lookup"><span data-stu-id="42b12-109">If you have more than one server that is sharing access to the Application Virtualization database, all those servers must be taken offline while the database is being upgraded.</span></span> <span data-ttu-id="42b12-110">您應該遵循資料庫升級的一般業務做法，但強烈建議您在測試伺服器上先使用資料庫的備份複本來測試資料庫升級。</span><span class="sxs-lookup"><span data-stu-id="42b12-110">You should follow your normal business practices for the database upgrade, but it is highly advisable that you test the database upgrade by using a backup copy of the database first on a test server.</span></span> <span data-ttu-id="42b12-111">接著，您應該選取其中一個伺服器進行第一次升級，這會升級資料庫架構。</span><span class="sxs-lookup"><span data-stu-id="42b12-111">Then, you should select one of the servers for the first upgrade, which will upgrade the database schema.</span></span> <span data-ttu-id="42b12-112">成功升級生產資料庫之後，您就可以升級其他伺服器。</span><span class="sxs-lookup"><span data-stu-id="42b12-112">After the production database has been successfully upgraded, you can upgrade the other servers.</span></span>

-   <span data-ttu-id="42b12-113">您只能從 Microsoft Application Virtualization （App-v）4.1 或 4.1 SP1 升級至 Microsoft Application Virtualization （App-v）4.5。</span><span class="sxs-lookup"><span data-stu-id="42b12-113">You can upgrade to Microsoft Application Virtualization (App-V)4.5 only from Microsoft Application Virtualization (App-V)4.1 or4.1 SP1.</span></span> <span data-ttu-id="42b12-114">您必須先卸載或升級到4.1 或 4.1 SP1，然後再升級至 App-v 4.5。</span><span class="sxs-lookup"><span data-stu-id="42b12-114">App-V4.0 and earlier must be uninstalled or upgraded to4.1 or4.1 SP1 before upgrading to App-V4.5.</span></span>

 

**<span data-ttu-id="42b12-115">升級應用程式虛擬化系統電腦上的軟體元件</span><span class="sxs-lookup"><span data-stu-id="42b12-115">To upgrade software components on Application Virtualization System computers</span></span>**

1.  <span data-ttu-id="42b12-116">流覽至網路上安裝程式的位置，請從網路執行此程式，或將它的目錄複寫到目的電腦，然後按兩下 Setup.exe 的檔案。</span><span class="sxs-lookup"><span data-stu-id="42b12-116">Navigate to the location of the Setup program on the network, either run this program from the network or copy its directory to the target computer, and then double-click the Setup.exe file.</span></span>

2.  <span data-ttu-id="42b12-117">在 [安裝精靈] 的 [**歡迎**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="42b12-117">On the **Welcome** page of the Installation Wizard, click **Next**.</span></span>

3.  <span data-ttu-id="42b12-118">在 [**授權協定**] 頁面上，閱讀 [授權協定]，核取 [**我接受授權合約中的條款**]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="42b12-118">On the **License Agreement** page, read the license agreement, check **I accept the terms in the license agreement**, and click **Next**.</span></span>

4.  <span data-ttu-id="42b12-119">當 [**已安裝的軟體**] 頁面開啟，並顯示已安裝的應用程式虛擬化系統元件及每個元件版本的清單時，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="42b12-119">When the **Installed Software** page opens and displays a list of the installed Application Virtualization System components and the version of each component, click **Next**.</span></span>

5.  <span data-ttu-id="42b12-120">在 [**會話遺失警告**] 頁面上，朗讀顯示的訊息，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="42b12-120">On the **Session Loss Warning** page, read the displayed message and click **Next**.</span></span>

6.  <span data-ttu-id="42b12-121">在 [連線**至設定資料庫]** 頁面上，檢查頁面上的內容，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="42b12-121">On the **Connect to Configuration Database** page, review the content on the page and click **Next**.</span></span>

7.  <span data-ttu-id="42b12-122">如果顯示 [**需要資料庫升級**] 頁面，則需要進行資料庫升級。</span><span class="sxs-lookup"><span data-stu-id="42b12-122">If the **Database Upgrade Required** page is displayed, a database upgrade is required.</span></span> <span data-ttu-id="42b12-123">輸入資料庫管理認證，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="42b12-123">Enter the database administrative credentials, and then click **Next**.</span></span> <span data-ttu-id="42b12-124">如果未顯示此頁面，請跳至步驟9。</span><span class="sxs-lookup"><span data-stu-id="42b12-124">If this page is not displayed, skip to Step 9.</span></span>

8.  <span data-ttu-id="42b12-125">在 [**備份設定資料庫**] 頁面上，選取適當的方塊以執行備份，然後將其匯出到現有的位置，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="42b12-125">On the **Backup Configuration Database** page, check the appropriate boxes to perform the backup and export it to an existing location, and then click **Next**.</span></span>

    <span data-ttu-id="42b12-126">**重要** 如果您想要在升級失敗時回滾到前一個版本，請確認您已核取 [**執行設定資料庫備份**] 方塊，否則您將會遺失設定資料。</span><span class="sxs-lookup"><span data-stu-id="42b12-126">**Important** If you want to be able to roll back to the previous version in the event of an upgrade failure, make sure you check the **Perform a backup of the configuration database** box, or you will lose the configuration data.</span></span>

    <span data-ttu-id="42b12-127">當您想要使用 VSS 還原資料庫時，您必須先停止管理伺服器上的 App-v Server 服務。</span><span class="sxs-lookup"><span data-stu-id="42b12-127">When you want to restore a database with VSS, you must first stop the App-V Server Service on the Management Server.</span></span> <span data-ttu-id="42b12-128">如果有多個伺服器連線至同一個資料庫，就應該在每個管理伺服器上完成此操作。</span><span class="sxs-lookup"><span data-stu-id="42b12-128">This should be done on every Management server if there is more than one server connected to the same database.</span></span>

     

9.  <span data-ttu-id="42b12-129">在 [第一份**套件驗證**] 頁面上，閱讀內容，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="42b12-129">On the first **Package Validation** page, read the content and then click **Next**.</span></span>

10. <span data-ttu-id="42b12-130">在 [第二個**套件驗證**] 頁面上，您可以選擇在記事本視窗中顯示套件驗證的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="42b12-130">On the second **Package Validation** page, you have the option of displaying the details of the package validation in a Notepad window.</span></span> <span data-ttu-id="42b12-131">若要查看詳細資料，請按一下 [**詳細資料**];否則，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="42b12-131">To see the details, click **Details**; otherwise, click **Next**.</span></span>

11. <span data-ttu-id="42b12-132">在 [**準備升級程式**] 頁面上，按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="42b12-132">On the **Ready to Upgrade the Program** page, click **Next**.</span></span>

12. <span data-ttu-id="42b12-133">在 [**安裝精靈已完成]** 頁面上，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="42b12-133">On the **Installation Wizard Completed** page, click **Finish**.</span></span>

13. <span data-ttu-id="42b12-134">在安裝應用程式虛擬化管理主控台或 Application Virtualization Server 軟體元件的所有其他電腦上，重複步驟1到12。</span><span class="sxs-lookup"><span data-stu-id="42b12-134">Repeat steps 1–12 on all other computers where you installed the Application Virtualization Management Console or the Application Virtualization Server software component.</span></span>

    <span data-ttu-id="42b12-135">升級資料儲存區之後，您可以繼續進行正常作業。</span><span class="sxs-lookup"><span data-stu-id="42b12-135">After upgrading the data store, you can resume normal operation.</span></span> <span data-ttu-id="42b12-136">（當您升級任何伺服器或應用程式 V 管理 Web 服務時，就會升級資料存儲區。）</span><span class="sxs-lookup"><span data-stu-id="42b12-136">(The data store is upgraded when you upgrade any server or the App-V Management Web Service.)</span></span>

## <span data-ttu-id="42b12-137">相關主題</span><span class="sxs-lookup"><span data-stu-id="42b12-137">Related topics</span></span>


[<span data-ttu-id="42b12-138">Application Virtualization 部署與升級考量</span><span class="sxs-lookup"><span data-stu-id="42b12-138">Application Virtualization Deployment and Upgrade Considerations</span></span>](application-virtualization-deployment-and-upgrade-considerations.md)

 

 





