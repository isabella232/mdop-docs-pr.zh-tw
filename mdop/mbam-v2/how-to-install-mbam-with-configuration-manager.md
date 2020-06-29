---
title: 如何安裝 MBAM 搭配 Configuration Manager
description: 如何安裝 MBAM 搭配 Configuration Manager
author: dansimp
ms.assetid: fd0832e4-3b79-4e56-9550-d2f396be6d09
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a556ce961e6a423caecdd0766cf8623383897b58
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810970"
---
# <span data-ttu-id="dec26-103">如何安裝 MBAM 搭配 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="dec26-103">How to Install MBAM with Configuration Manager</span></span>


<span data-ttu-id="dec26-104">本節說明使用 [開始] 中的 [[使用 MBAM 與 Configuration manager](getting-started---using-mbam-with-configuration-manager.md)] 來安裝 MBAM 與 configuration manager 的步驟。</span><span class="sxs-lookup"><span data-stu-id="dec26-104">This section describes the steps to install MBAM with Configuration Manager by using the recommended configuration, which is illustrated in [Getting Started - Using MBAM with Configuration Manager](getting-started---using-mbam-with-configuration-manager.md).</span></span> <span data-ttu-id="dec26-105">這些步驟分為下列任務：</span><span class="sxs-lookup"><span data-stu-id="dec26-105">The steps are divided into the following tasks:</span></span>

-   <span data-ttu-id="dec26-106">在 Configuration Manager 伺服器上安裝和設定 MBAM</span><span class="sxs-lookup"><span data-stu-id="dec26-106">Install and configure MBAM on the Configuration Manager Server</span></span>

-   <span data-ttu-id="dec26-107">在資料庫伺服器上安裝復原和審核資料庫</span><span class="sxs-lookup"><span data-stu-id="dec26-107">Install the Recovery and Audit Databases on the Database Server</span></span>

-   <span data-ttu-id="dec26-108">在管理和監控伺服器上安裝管理和監控伺服器功能</span><span class="sxs-lookup"><span data-stu-id="dec26-108">Install the Administration and Monitoring Server features on the Administration and Monitoring Server</span></span>

<span data-ttu-id="dec26-109">開始安裝之前，請先確定您已編輯或建立必要的 mof 檔案。</span><span class="sxs-lookup"><span data-stu-id="dec26-109">Before you begin the installation, ensure that you have edited or created the necessary mof files.</span></span> <span data-ttu-id="dec26-110">如需相關指示，請參閱[如何建立或編輯 mof](how-to-create-or-edit-the-mof-files.md)檔案。</span><span class="sxs-lookup"><span data-stu-id="dec26-110">For instructions, see [How to Create or Edit the mof Files](how-to-create-or-edit-the-mof-files.md).</span></span>

<span data-ttu-id="dec26-111">**重要** 如果您使用的不是預設的 SQL Server Reporting Services （SSRS）實例，您必須使用下列命令列來啟動 MBAM 設定，以指定 SSRS 命名的實例：</span><span class="sxs-lookup"><span data-stu-id="dec26-111">**Important** If you are using a non-default SQL Server Reporting Services (SSRS) instance, you must start the MBAM Setup by using the following command line to specify the SSRS named instance:</span></span>

`MbamSetup.exe CM_SSRS_INSTANCE_NAME=<NamedInstance>`

 

**<span data-ttu-id="dec26-112">在 Configuration Manager 伺服器上安裝 MBAM</span><span class="sxs-lookup"><span data-stu-id="dec26-112">To install MBAM on the Configuration Manager Server</span></span>**

1.  <span data-ttu-id="dec26-113">在 Configuration Manager 伺服器上，執行**MBAMSetup.exe**以啟動 MBAM 安裝精靈。</span><span class="sxs-lookup"><span data-stu-id="dec26-113">On the Configuration Manager Server, run **MBAMSetup.exe** to start the MBAM installation wizard.</span></span>

    <span data-ttu-id="dec26-114">**記事** 若要取得安裝記錄檔，您必須使用 Msiexec 套件和 **/l** &lt; location &gt; 選項來安裝 Configuration Manager。</span><span class="sxs-lookup"><span data-stu-id="dec26-114">**Note** To obtain the setup log files, you have to use the Msiexec package and the **/L** &lt;location&gt; option to install Configuration Manager.</span></span> <span data-ttu-id="dec26-115">記錄檔案是在您指定的位置建立。</span><span class="sxs-lookup"><span data-stu-id="dec26-115">Log files are created in the location that you specify.</span></span>

    <span data-ttu-id="dec26-116">在安裝 Configuration Manager 之使用者的電腦上，在 [% temp%] 資料夾中，會建立其他設定記錄檔。</span><span class="sxs-lookup"><span data-stu-id="dec26-116">Additional setup log files are created in the %temp% folder on the computer of the user who is installing Configuration Manager.</span></span>

     

2.  <span data-ttu-id="dec26-117">在 [**歡迎**] 頁面上，選擇性地選取 [**客戶經驗改進計畫**]，然後按一下 [**開始**]。</span><span class="sxs-lookup"><span data-stu-id="dec26-117">On the **Welcome** page, optionally select the **Customer Experience Improvement Program**, and then click **Start**.</span></span>

3.  <span data-ttu-id="dec26-118">閱讀並接受 Microsoft 軟體授權協定，然後按一下 **[下一步]** 繼續安裝。</span><span class="sxs-lookup"><span data-stu-id="dec26-118">Read and accept the Microsoft Software License Agreement, and then click **Next** to continue the installation.</span></span>

4.  <span data-ttu-id="dec26-119">在 [**拓撲選取範圍**] 頁面上，選取 [ **System Center Configuration Manager 整合**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="dec26-119">On the **Topology Selection** page, select **System Center Configuration Manager Integration**, and then click **Next**.</span></span>

5.  <span data-ttu-id="dec26-120">在 [**選取要安裝的功能**] 頁面上，選取**System Center Configuration Manager 整合**。</span><span class="sxs-lookup"><span data-stu-id="dec26-120">On the **Select features to install** page, select **System Center Configuration Manager Integration**.</span></span>

    <span data-ttu-id="dec26-121">**記事** 在 [**檢查先決條件**] 頁面上，在 [安裝精靈] 檢查安裝的先決條件並確認沒有遺漏的情況下，按一下 **[下一步**]。</span><span class="sxs-lookup"><span data-stu-id="dec26-121">**Note** On the **Checking Prerequisites** page, click **Next** after the installation wizard checks the prerequisites for your installation and confirms that none are missing.</span></span> <span data-ttu-id="dec26-122">如果偵測到遺失的先決條件，您必須先解決遺失的先決條件，然後再次按一下 [**檢查必備元件]。**</span><span class="sxs-lookup"><span data-stu-id="dec26-122">If a missing prerequisite is detected, you have to resolve the missing prerequisites, and then click **Check prerequisites again.**</span></span>

     

6.  <span data-ttu-id="dec26-123">指定是否要使用 Microsoft 更新，協助保護您的電腦安全性，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="dec26-123">Specify whether to use Microsoft Updates to help keep your computer secure, and then click **Next**.</span></span> <span data-ttu-id="dec26-124">使用 Microsoft 更新並不會開啟 Windows 中的自動更新。</span><span class="sxs-lookup"><span data-stu-id="dec26-124">Using Microsoft Updates does not turn on Automatic Updates in Windows.</span></span>

7.  <span data-ttu-id="dec26-125">按 \[**下一步**\] 繼續。</span><span class="sxs-lookup"><span data-stu-id="dec26-125">Click **Next** to continue.</span></span>

8.  <span data-ttu-id="dec26-126">在 [**安裝摘要**] 頁面上，查看將要安裝的功能清單，然後按一下 [**安裝**] 以開始安裝 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="dec26-126">On the **Installation Summary** page, review the list of features that will be installed, and click **Install** to start installing the MBAM features.</span></span> <span data-ttu-id="dec26-127">如果您必須檢查或變更您的安裝設定，請按一下 [**返回**]，回到嚮導中，或按一下 [**取消**] 結束安裝程式。</span><span class="sxs-lookup"><span data-stu-id="dec26-127">Click **Back** to move back through the wizard if you have to review or change your installation settings, or click **Cancel** to exit Setup.</span></span> <span data-ttu-id="dec26-128">安裝程式會安裝 MBAM 功能，並通知您安裝已完成。</span><span class="sxs-lookup"><span data-stu-id="dec26-128">Setup installs the MBAM features and notifies you that the installation is completed.</span></span>

9.  <span data-ttu-id="dec26-129">按一下 **[完成] 結束**嚮導。</span><span class="sxs-lookup"><span data-stu-id="dec26-129">Click **Finish** to exit the wizard.</span></span>

**<span data-ttu-id="dec26-130">在資料庫伺服器上安裝復原和審核資料庫</span><span class="sxs-lookup"><span data-stu-id="dec26-130">To install the Recovery and Audit Databases on the Database Server</span></span>**

1.  <span data-ttu-id="dec26-131">在資料庫伺服器上，執行**MBAMSetup.exe**以啟動 MBAM 安裝精靈。</span><span class="sxs-lookup"><span data-stu-id="dec26-131">On the Database Server, run **MBAMSetup.exe** to start the MBAM installation wizard.</span></span>

2.  <span data-ttu-id="dec26-132">在 [**歡迎**] 頁面上，選擇性地選取 [**客戶經驗改進計畫**]，然後按一下 [**開始**]。</span><span class="sxs-lookup"><span data-stu-id="dec26-132">On the **Welcome** page, optionally select the **Customer Experience Improvement Program**, and then click **Start**.</span></span>

3.  <span data-ttu-id="dec26-133">閱讀並接受 Microsoft 軟體授權協定，然後按一下 **[下一步]** 繼續安裝。</span><span class="sxs-lookup"><span data-stu-id="dec26-133">Read and accept the Microsoft Software License Agreement, and then click **Next** to continue the installation.</span></span>

4.  <span data-ttu-id="dec26-134">在 [**拓撲選取專案**] 頁面上，選取 [ **System Center Configuration Manager 整合**拓撲]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="dec26-134">On the **Topology Selection** page, select the **System Center Configuration Manager Integration** topology, and then click **Next**.</span></span>

5.  <span data-ttu-id="dec26-135">從要安裝的功能清單中，選取 [**恢復資料庫**和**審核資料庫**]，然後清除其餘的功能。</span><span class="sxs-lookup"><span data-stu-id="dec26-135">From the list of features to install, select **Recovery Database** and **Audit Database**, and clear the remaining features.</span></span>

    <span data-ttu-id="dec26-136">**記事** 安裝精靈會檢查安裝的先決條件，並顯示遺失的先決條件。</span><span class="sxs-lookup"><span data-stu-id="dec26-136">**Note** The installation wizard checks the prerequisites for your installation and displays the prerequisites that are missing.</span></span> <span data-ttu-id="dec26-137">如果符合所有先決條件，安裝會繼續進行。</span><span class="sxs-lookup"><span data-stu-id="dec26-137">If all of the prerequisites are met, the installation continues.</span></span> <span data-ttu-id="dec26-138">如果偵測到遺失的先決條件，您必須先解決遺失的先決條件，然後再次按一下 [**檢查必備元件**]。</span><span class="sxs-lookup"><span data-stu-id="dec26-138">If a missing prerequisite is detected, you have to resolve the missing prerequisites, and then click **Check prerequisites again**.</span></span> <span data-ttu-id="dec26-139">如果此時間符合所有先決條件，安裝就會繼續。</span><span class="sxs-lookup"><span data-stu-id="dec26-139">If all prerequisites are met this time, the installation resumes.</span></span>

     

6.  <span data-ttu-id="dec26-140">在 [**設定復原資料庫**] 頁面上，指定將執行 [管理及監視伺服器] 功能的電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="dec26-140">On the **Configure the Recovery Database** page, specify the names of the computers that will be running the Administration and Monitoring Server feature.</span></span> <span data-ttu-id="dec26-141">部署管理和監視伺服器功能之後，它會使用其網域帳戶來連線至資料庫。</span><span class="sxs-lookup"><span data-stu-id="dec26-141">After the Administration and Monitoring Server feature is deployed, it uses its domain account to connect to the database.</span></span>

7.  <span data-ttu-id="dec26-142">按 \[**下一步**\] 繼續。</span><span class="sxs-lookup"><span data-stu-id="dec26-142">Click **Next** to continue.</span></span>

8.  <span data-ttu-id="dec26-143">指定要儲存恢復資料之資料庫的 SQL Server 實例名稱和名稱。</span><span class="sxs-lookup"><span data-stu-id="dec26-143">Specify the SQL Server instance name and the name of the database that will store the recovery data.</span></span> <span data-ttu-id="dec26-144">您也必須指定資料庫的位置和記錄資訊所在的位置。</span><span class="sxs-lookup"><span data-stu-id="dec26-144">You must also specify both where the database will be located and where the log information will be located.</span></span>

9.  <span data-ttu-id="dec26-145">按一下 **[下一步]** ，繼續執行 MBAM 安裝程式安裝精靈。</span><span class="sxs-lookup"><span data-stu-id="dec26-145">Click **Next** to continue with the MBAM Setup installation wizard.</span></span>

10. <span data-ttu-id="dec26-146">在 [**設定審核資料庫**] 頁面上，指定將用來存取報表資料庫的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="dec26-146">On the **Configure the Audit Database** page, specify the user account that will be used to access the database for reports.</span></span>

11. <span data-ttu-id="dec26-147">指定將執行管理和監視伺服器以及審核報告的電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="dec26-147">Specify the computer names of the computers that will be running the Administration and Monitoring Server and the Audit Reports.</span></span> <span data-ttu-id="dec26-148">在部署管理和監視及審核報告功能之後，就會使用其網域帳戶來連線至資料庫。</span><span class="sxs-lookup"><span data-stu-id="dec26-148">After the Administration and Monitoring and the Audit Reports features are deployed, their domain accounts will be used to connect to the databases.</span></span>

    <span data-ttu-id="dec26-149">**記事** 如果您在沒有 [審核報告] 功能的情況下安裝審核資料庫，您必須在審核資料庫電腦上新增例外狀況，才能在 Microsoft SQL Server 埠上啟用入站流量。</span><span class="sxs-lookup"><span data-stu-id="dec26-149">**Note** If you are installing the Audit Database without the Audit Reports feature, you must add an exception on the Audit Database computer to enable inbound traffic on the Microsoft SQL Server port.</span></span> <span data-ttu-id="dec26-150">預設埠號碼是1433。</span><span class="sxs-lookup"><span data-stu-id="dec26-150">The default port number is 1433.</span></span>

     

12. <span data-ttu-id="dec26-151">指定要儲存審計資料之資料庫的 SQL Server 實例名稱與名稱。</span><span class="sxs-lookup"><span data-stu-id="dec26-151">Specify the SQL Server instance name and the name of the database that will store the audit data.</span></span> <span data-ttu-id="dec26-152">您也必須指定資料庫和記錄資訊的存放位置。</span><span class="sxs-lookup"><span data-stu-id="dec26-152">You must also specify where the database and log information will be located.</span></span>

13. <span data-ttu-id="dec26-153">按一下 [**安裝**] 以開始安裝，然後按一下 **[完成]** 以完成安裝。</span><span class="sxs-lookup"><span data-stu-id="dec26-153">Click **Install** to start the installation, and then click **Finish** to complete the installation.</span></span>

**<span data-ttu-id="dec26-154">若要在管理和監控伺服器上安裝管理和監控伺服器功能</span><span class="sxs-lookup"><span data-stu-id="dec26-154">To install the Administration and Monitoring Server features on the Administration and Monitoring Server</span></span>**

1.  <span data-ttu-id="dec26-155">在 [管理及監視伺服器] 上，執行**MBAMSetup.exe** ，啟動 [MBAM 安裝] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="dec26-155">On the Administration and Monitoring Server, run **MBAMSetup.exe** to start the MBAM installation wizard.</span></span>

2.  <span data-ttu-id="dec26-156">在 [**歡迎**] 頁面上，選擇性地選取 [**客戶經驗改進計畫**]，然後按一下 [**開始**]。</span><span class="sxs-lookup"><span data-stu-id="dec26-156">On the **Welcome** page, optionally select the **Customer Experience Improvement Program**, and then click **Start**.</span></span>

3.  <span data-ttu-id="dec26-157">閱讀並接受 Microsoft 軟體授權協定，然後按一下 **[下一步]** 繼續安裝。</span><span class="sxs-lookup"><span data-stu-id="dec26-157">Read and accept the Microsoft Software License Agreement, and then click **Next** to continue the installation.</span></span>

4.  <span data-ttu-id="dec26-158">在 [**拓撲選取專案**] 頁面上，選取 [ **System Center Configuration Manager 整合**拓撲]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="dec26-158">On the **Topology Selection** page, select the **System Center Configuration Manager Integration** topology, and then click **Next**.</span></span>

5.  <span data-ttu-id="dec26-159">從要安裝的功能清單中，選取 [**管理及監視伺服器**與**自助式入口網站**]，然後清除其餘的功能。</span><span class="sxs-lookup"><span data-stu-id="dec26-159">From the list of features to install, select **Administration and Monitoring Server** and **Self-Service Portal**, and clear the remaining features.</span></span>

    <span data-ttu-id="dec26-160">**記事** 安裝精靈會檢查安裝的先決條件，並顯示遺失的先決條件。</span><span class="sxs-lookup"><span data-stu-id="dec26-160">**Note** The installation wizard checks the prerequisites for your installation and displays the prerequisites that are missing.</span></span> <span data-ttu-id="dec26-161">如果符合所有先決條件，安裝會繼續進行。</span><span class="sxs-lookup"><span data-stu-id="dec26-161">If all of the prerequisites are met, the installation continues.</span></span> <span data-ttu-id="dec26-162">如果偵測到遺失的先決條件，您必須先解決遺失的先決條件，然後再次按一下 [**檢查必備元件**]。</span><span class="sxs-lookup"><span data-stu-id="dec26-162">If a missing prerequisite is detected, you have to resolve the missing prerequisites, and then click **Check prerequisites again**.</span></span> <span data-ttu-id="dec26-163">如果此時間符合所有先決條件，安裝就會繼續。</span><span class="sxs-lookup"><span data-stu-id="dec26-163">If all prerequisites are met this time, the installation resumes.</span></span>

     

6.  <span data-ttu-id="dec26-164">若要安裝[和設定分散式伺服器上的 MBAM，](how-to-install-and-configure-mbam-on-distributed-servers-mbam-2.md)請依照安裝**自助**入口網站一節中的步驟安裝自助式入口網站。</span><span class="sxs-lookup"><span data-stu-id="dec26-164">Install the Self-Service Portal by following the steps in the **To install the Self-Service Portal** section in [How to Install and Configure MBAM on Distributed Servers](how-to-install-and-configure-mbam-on-distributed-servers-mbam-2.md).</span></span>

    <span data-ttu-id="dec26-165">**記事** 如果用戶端電腦將無法存取 Microsoft 內容傳遞網路（CDN），這會提供自助服務入口網站所需的特定 JavaScript 檔案存取權，完成在在分散式伺服器上**設定自助入口網站**以設定自助式入口網站，以將來自無障礙來源的 JavaScript 檔案的[安裝和設定 MBAM](how-to-install-and-configure-mbam-on-distributed-servers-mbam-2.md)的步驟。</span><span class="sxs-lookup"><span data-stu-id="dec26-165">**Note** If the client computers will not have access to the Microsoft Content Delivery Network (CDN), which gives the Self-Service Portal the required access to certain JavaScript files, complete the steps in the **To configure the Self-Service Portal when end users cannot access the Microsoft Content Delivery Network** section [How to Install and Configure MBAM on Distributed Servers](how-to-install-and-configure-mbam-on-distributed-servers-mbam-2.md) to configure the Self-Service Portal to reference the JavaScript files from an accessible source.</span></span>

     

7.  <span data-ttu-id="dec26-166">[若要安裝和設定分散式伺服器上的 MBAM，請依照如何安裝及設定分散式伺服器上的](how-to-install-and-configure-mbam-on-distributed-servers-mbam-2.md)，按照安裝**管理和監視伺服器功能**一節中的步驟安裝管理和監控伺服器功能一節。</span><span class="sxs-lookup"><span data-stu-id="dec26-166">Install the Administration and Monitoring Server features by following the steps in the **To install the Administration and Monitoring Server feature** section in [How to Install and Configure MBAM on Distributed Servers](how-to-install-and-configure-mbam-on-distributed-servers-mbam-2.md).</span></span>

8.  <span data-ttu-id="dec26-167">按一下 **[完成]** 以完成安裝。</span><span class="sxs-lookup"><span data-stu-id="dec26-167">Click **Finish** to complete the installation.</span></span>

## <span data-ttu-id="dec26-168">相關主題</span><span class="sxs-lookup"><span data-stu-id="dec26-168">Related topics</span></span>


[<span data-ttu-id="dec26-169">如何使用 Configuration Manager 驗證 MBAM 安裝</span><span class="sxs-lookup"><span data-stu-id="dec26-169">How to Validate the MBAM Installation with Configuration Manager</span></span>](how-to-validate-the-mbam-installation-with-configuration-manager.md)

[<span data-ttu-id="dec26-170">使用設定管理員來部署 MBAM</span><span class="sxs-lookup"><span data-stu-id="dec26-170">Deploying MBAM with Configuration Manager</span></span>](deploying-mbam-with-configuration-manager-mbam2.md)

 

 





