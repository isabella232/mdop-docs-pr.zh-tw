---
title: 如何在分散式伺服器上安裝及設定 MBAM
description: 如何在分散式伺服器上安裝及設定 MBAM
author: dansimp
ms.assetid: 67b91e6b-ae2e-4e47-9ef2-6819aba95976
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 841b894430d14604f0fd923703708d7a3f588c07
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810328"
---
# <span data-ttu-id="749be-103">如何在分散式伺服器上安裝及設定 MBAM</span><span class="sxs-lookup"><span data-stu-id="749be-103">How to Install and Configure MBAM on Distributed Servers</span></span>


<span data-ttu-id="749be-104">本主題中的程式說明如何在分散式伺服器上的獨立拓撲中安裝 Microsoft BitLocker 管理和監控（MBAM）2.0。</span><span class="sxs-lookup"><span data-stu-id="749be-104">The procedures in this topic describe how to install Microsoft BitLocker Administration and Monitoring (MBAM) 2.0 in the Stand-alone topology on distributed servers.</span></span> <span data-ttu-id="749be-105">若要查看建議架構的圖表，以及資料庫與功能的描述，請參閱[部署 MBAM 2.0 伺服器基礎結構](deploying-the-mbam-20-server-infrastructure-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="749be-105">To see a diagram of the recommended architecture, along with a description of the databases and features, see [Deploying the MBAM 2.0 Server Infrastructure](deploying-the-mbam-20-server-infrastructure-mbam-2.md).</span></span> <span data-ttu-id="749be-106">若要使用 Configuration Manager 拓撲來安裝 Microsoft BitLocker 管理及監視，請參閱[使用 Configuration Manager 部署 MBAM](deploying-mbam-with-configuration-manager-mbam2.md)。</span><span class="sxs-lookup"><span data-stu-id="749be-106">To install Microsoft BitLocker Administration and Monitoring with the Configuration Manager topology, see [Deploying MBAM with Configuration Manager](deploying-mbam-with-configuration-manager-mbam2.md).</span></span>

<span data-ttu-id="749be-107">每個伺服器功能都有特定的先決條件。</span><span class="sxs-lookup"><span data-stu-id="749be-107">Each server feature has certain prerequisites.</span></span> <span data-ttu-id="749be-108">若要確認您已符合系統必備與硬體和軟體需求，請參閱[MBAM 2.0 部署先決條件](mbam-20-deployment-prerequisites-mbam-2.md)和[MBAM 2.0 支援](mbam-20-supported-configurations-mbam-2.md)的設定。</span><span class="sxs-lookup"><span data-stu-id="749be-108">To verify that you have met the prerequisites and hardware and software requirements, see [MBAM 2.0 Deployment Prerequisites](mbam-20-deployment-prerequisites-mbam-2.md) and [MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md).</span></span> <span data-ttu-id="749be-109">此外，部分功能需要您在安裝程式期間提供特定資訊，才能成功部署該功能。</span><span class="sxs-lookup"><span data-stu-id="749be-109">In addition, some features require that you provide certain information during the installation process to successfully deploy the feature.</span></span> <span data-ttu-id="749be-110">您也應該在開始 MBAM 部署之前，先複習[規劃 MBAM 2.0 伺服器部署](planning-for-mbam-20-server-deployment-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="749be-110">You should also review [Planning for MBAM 2.0 Server Deployment](planning-for-mbam-20-server-deployment-mbam-2.md) before you start the MBAM deployment.</span></span>

**<span data-ttu-id="749be-111">注意</span><span class="sxs-lookup"><span data-stu-id="749be-111">Note</span></span>**  
<span data-ttu-id="749be-112">若要取得安裝記錄檔，您必須使用 Msiexec 套件和 **/l** &lt; location &gt; 選項來安裝 MBAM。</span><span class="sxs-lookup"><span data-stu-id="749be-112">To obtain the setup log files, you have to use the Msiexec package and the **/L** &lt;location&gt; option to install MBAM.</span></span> <span data-ttu-id="749be-113">記錄檔案是在您指定的位置建立。</span><span class="sxs-lookup"><span data-stu-id="749be-113">Log files are created in the location that you specify.</span></span>

<span data-ttu-id="749be-114">在安裝 MBAM 的使用者伺服器上，會在% temp% 資料夾中建立額外的設定記錄檔。</span><span class="sxs-lookup"><span data-stu-id="749be-114">Additional setup log files are created in the %temp% folder on the server of the user who is installing MBAM.</span></span>



## <a href="" id="deploying-mbam-server-features-"></a><span data-ttu-id="749be-115">部署 MBAM Server 功能</span><span class="sxs-lookup"><span data-stu-id="749be-115">Deploying MBAM Server Features</span></span>


<span data-ttu-id="749be-116">下列步驟說明如何安裝一般 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="749be-116">The following steps describe how to install general MBAM features.</span></span>

**<span data-ttu-id="749be-117">啟動 MBAM Server 安裝精靈</span><span class="sxs-lookup"><span data-stu-id="749be-117">To start the MBAM Server installation wizard</span></span>**

1.  <span data-ttu-id="749be-118">在您要安裝 Microsoft BitLocker 管理與監視的伺服器上，執行**MBAMSetup.exe**以啟動 MBAM 安裝精靈。</span><span class="sxs-lookup"><span data-stu-id="749be-118">On the server where you want to install Microsoft BitLocker Administration and Monitoring, run **MBAMSetup.exe** to start the MBAM installation wizard.</span></span>

2.  <span data-ttu-id="749be-119">在 [**歡迎**] 頁面上，選擇性地選取 [**客戶經驗改進計畫**]，然後按一下 [**開始**]。</span><span class="sxs-lookup"><span data-stu-id="749be-119">On the **Welcome** page, optionally select the **Customer Experience Improvement Program**, and then click **Start**.</span></span>

3.  <span data-ttu-id="749be-120">閱讀並接受 Microsoft 軟體授權協定，然後按一下 **[下一步]** 繼續安裝。</span><span class="sxs-lookup"><span data-stu-id="749be-120">Read and accept the Microsoft Software License Agreement, and then click **Next** to continue the installation.</span></span>

4.  <span data-ttu-id="749be-121">在 [**拓撲選取範圍**] 頁面上，選取**獨立**拓朴，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="749be-121">On the **Topology Selection** page, select the **Stand-alone** topology, and then click **Next**.</span></span>

    **<span data-ttu-id="749be-122">注意</span><span class="sxs-lookup"><span data-stu-id="749be-122">Note</span></span>**  
    <span data-ttu-id="749be-123">如果您想要使用 Configuration Manager 整合拓撲來安裝 MBAM，請參閱[使用 Configuration Manager 部署 MBAM](deploying-mbam-with-configuration-manager-mbam2.md)。</span><span class="sxs-lookup"><span data-stu-id="749be-123">If you want to install MBAM with the Configuration Manager integrated topology, see [Deploying MBAM with Configuration Manager](deploying-mbam-with-configuration-manager-mbam2.md).</span></span>



5.  <span data-ttu-id="749be-124">選取您要安裝的功能。</span><span class="sxs-lookup"><span data-stu-id="749be-124">Select the features that you want to install.</span></span> <span data-ttu-id="749be-125">根據預設，所有的 MBAM 功能都已選取 [安裝]。</span><span class="sxs-lookup"><span data-stu-id="749be-125">By default, all MBAM features are selected for installation.</span></span> <span data-ttu-id="749be-126">清除您想要安裝在其他位置的功能。</span><span class="sxs-lookup"><span data-stu-id="749be-126">Clear the features that you want to install elsewhere.</span></span> <span data-ttu-id="749be-127">在同一部電腦上安裝的功能，必須同時安裝在一起。</span><span class="sxs-lookup"><span data-stu-id="749be-127">Features that will be installed on the same computer must be installed together at the same time.</span></span> <span data-ttu-id="749be-128">您必須以下列順序安裝 MBAM 功能：</span><span class="sxs-lookup"><span data-stu-id="749be-128">You must install MBAM features in the following order:</span></span>

    -   <span data-ttu-id="749be-129">復原資料庫</span><span class="sxs-lookup"><span data-stu-id="749be-129">Recovery Database</span></span>

    -   <span data-ttu-id="749be-130">合規性和審核資料庫</span><span class="sxs-lookup"><span data-stu-id="749be-130">Compliance and Audit Database</span></span>

    -   <span data-ttu-id="749be-131">合規性與審計報告</span><span class="sxs-lookup"><span data-stu-id="749be-131">Compliance and Audit Reports</span></span>

    -   <span data-ttu-id="749be-132">自助服務入口網站</span><span class="sxs-lookup"><span data-stu-id="749be-132">Self-Service Portal</span></span>

    -   <span data-ttu-id="749be-133">管理和監控伺服器</span><span class="sxs-lookup"><span data-stu-id="749be-133">Administration and Monitoring Server</span></span>

    -   <span data-ttu-id="749be-134">MBAM 群組原則範本</span><span class="sxs-lookup"><span data-stu-id="749be-134">MBAM Group Policy template</span></span>

    **<span data-ttu-id="749be-135">注意</span><span class="sxs-lookup"><span data-stu-id="749be-135">Note</span></span>**  
    <span data-ttu-id="749be-136">安裝精靈會檢查安裝的先決條件，並顯示遺失的先決條件。</span><span class="sxs-lookup"><span data-stu-id="749be-136">The installation wizard checks the prerequisites for your installation and displays the prerequisites that are missing.</span></span> <span data-ttu-id="749be-137">如果符合所有先決條件，安裝會繼續進行。</span><span class="sxs-lookup"><span data-stu-id="749be-137">If all of the prerequisites are met, the installation continues.</span></span> <span data-ttu-id="749be-138">如果偵測到遺失的先決條件，您必須先解決遺失的先決條件，然後再次按一下 [**檢查必備元件**]。</span><span class="sxs-lookup"><span data-stu-id="749be-138">If a missing prerequisite is detected, you have to resolve the missing prerequisites, and then click **Check prerequisites again**.</span></span> <span data-ttu-id="749be-139">如果此時間符合所有先決條件，安裝就會繼續。</span><span class="sxs-lookup"><span data-stu-id="749be-139">If all prerequisites are met this time, the installation resumes.</span></span>



~~~
The MBAM Setup wizard displays installation pages for the features that you select. The following sections describe the installation procedures for each feature.

**Note**  
For the following instructions, it is assumed that each feature is to be installed on a separate server. If you install multiple features on a single server, you can change or eliminate some steps.
~~~



**<span data-ttu-id="749be-140">若要安裝恢復資料庫</span><span class="sxs-lookup"><span data-stu-id="749be-140">To install the Recovery Database</span></span>**

1.  <span data-ttu-id="749be-141">在 [**設定復原資料庫**] 頁面上，指定將執行 [管理及監視伺服器] 功能的電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="749be-141">On the **Configure the Recovery database** page, specify the names of the computers that will be running the Administration and Monitoring Server feature.</span></span> <span data-ttu-id="749be-142">部署管理和監視伺服器功能之後，它會使用其網域帳戶來連線至資料庫。</span><span class="sxs-lookup"><span data-stu-id="749be-142">After the Administration and Monitoring Server feature is deployed, it uses its domain account to connect to the database.</span></span>

2.  <span data-ttu-id="749be-143">按 \[**下一步**\] 繼續。</span><span class="sxs-lookup"><span data-stu-id="749be-143">Click **Next** to continue.</span></span>

3.  <span data-ttu-id="749be-144">指定要儲存恢復資料之資料庫的 SQL Server 實例名稱和名稱。</span><span class="sxs-lookup"><span data-stu-id="749be-144">Specify the SQL Server instance name and the name of the database that will store the recovery data.</span></span> <span data-ttu-id="749be-145">您也必須指定資料庫的位置和記錄資訊所在的位置。</span><span class="sxs-lookup"><span data-stu-id="749be-145">You must also specify both where the database will be located and where the log information will be located.</span></span>

4.  <span data-ttu-id="749be-146">按一下 **[下一步**] 以繼續使用 [MBAM 設定] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="749be-146">Click **Next** to continue with the MBAM Setup wizard.</span></span>

**<span data-ttu-id="749be-147">若要安裝合規性和審核資料庫</span><span class="sxs-lookup"><span data-stu-id="749be-147">To install the Compliance and Audit Database</span></span>**

1.  <span data-ttu-id="749be-148">在 [**設定合規性和審核資料庫**] 頁面上，指定將用來存取報表資料庫的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="749be-148">On the **Configure the Compliance and Audit Database** page, specify the user account that will be used to access the database for reports.</span></span>

2.  <span data-ttu-id="749be-149">指定要執行管理和監視伺服器以及合規性與審核報告的電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="749be-149">Specify the computer names of the computers that will be running the Administration and Monitoring Server and the Compliance and Audit Reports.</span></span> <span data-ttu-id="749be-150">管理及監視及合規性與審計報表服務器部署之後，他們就會使用其網域帳戶連線至資料庫。</span><span class="sxs-lookup"><span data-stu-id="749be-150">After the Administration and Monitoring and the Compliance and Audit Reports Server are deployed, they use their domain accounts to connect to the databases.</span></span>

    **<span data-ttu-id="749be-151">注意</span><span class="sxs-lookup"><span data-stu-id="749be-151">Note</span></span>**  
    <span data-ttu-id="749be-152">如果您在沒有合規性和審核報告功能的情況下安裝合規性和審核資料庫，您必須在合規性和審核資料庫電腦上新增例外狀況，才能在 Microsoft SQL Server 埠上啟用入站流量。</span><span class="sxs-lookup"><span data-stu-id="749be-152">If you are installing the Compliance and Audit Database without the Compliance and Audit Reports feature, you must add an exception on the Compliance and Audit Database computer to enable inbound traffic on the Microsoft SQL Server port.</span></span> <span data-ttu-id="749be-153">預設埠號碼是1433。</span><span class="sxs-lookup"><span data-stu-id="749be-153">The default port number is 1433.</span></span>



3.  <span data-ttu-id="749be-154">指定 SQL Server 實例名稱和要儲存合規性和審核資料之資料庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="749be-154">Specify the SQL Server instance name and the name of the database that will store the compliance and audit data.</span></span> <span data-ttu-id="749be-155">您也必須指定資料庫和記錄資訊的存放位置。</span><span class="sxs-lookup"><span data-stu-id="749be-155">You must also specify where the database and log information will be located.</span></span>

4.  <span data-ttu-id="749be-156">按一下 **[下一步]** 以繼續使用 Microsoft BitLocker 管理及監視設定向導。</span><span class="sxs-lookup"><span data-stu-id="749be-156">Click **Next** to continue with the Microsoft BitLocker Administration and Monitoring Setup wizard.</span></span>

**<span data-ttu-id="749be-157">若要安裝合規性和審核報告</span><span class="sxs-lookup"><span data-stu-id="749be-157">To install the Compliance and Audit Reports</span></span>**

1.  <span data-ttu-id="749be-158">在 [**設定合規性和審核報告**] 頁面上，指定 &lt; &gt; 安裝合規性和審核資料庫的遠端 SQL Server 實例名稱（例如，ServerName）。</span><span class="sxs-lookup"><span data-stu-id="749be-158">On the **Configure the Compliance and Audit Reports** page, specify the remote SQL Server instance name (for example, &lt;ServerName&gt;) where the Compliance and Audit Database was installed.</span></span>

    **<span data-ttu-id="749be-159">注意</span><span class="sxs-lookup"><span data-stu-id="749be-159">Note</span></span>**  
    <span data-ttu-id="749be-160">如果您在沒有管理和監控伺服器的情況下安裝合規性和審核報告，您必須在合規性和審核報告電腦上新增例外狀況，才能在報表伺服器埠上啟用輸入流量（預設埠為80）。</span><span class="sxs-lookup"><span data-stu-id="749be-160">If you are installing the Compliance and Audit Reports without the Administration and Monitoring Server, you must add an exception on the Compliance and Audit Report computer to enable inbound traffic on the Reporting Server port (the default port is 80).</span></span>



2.  <span data-ttu-id="749be-161">指定合規性和審核資料庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="749be-161">Specify the name of the Compliance and Audit Database.</span></span> <span data-ttu-id="749be-162">根據預設，資料庫名稱是 MBAM 合規性狀態，不過您可以在安裝合規性和審核資料庫時變更名稱。</span><span class="sxs-lookup"><span data-stu-id="749be-162">By default, the database name is MBAM Compliance Status, although you can change the name when you install the Compliance and Audit Database.</span></span>

3.  <span data-ttu-id="749be-163">按 \[**下一步**\] 繼續。</span><span class="sxs-lookup"><span data-stu-id="749be-163">Click **Next** to continue.</span></span>

4.  <span data-ttu-id="749be-164">選取將安裝合規性和審核報告的 SQL Server Reporting Services 實例。</span><span class="sxs-lookup"><span data-stu-id="749be-164">Select the instance of SQL Server Reporting Services where the Compliance and Audit Reports will be installed.</span></span> <span data-ttu-id="749be-165">提供網域使用者帳戶和密碼以存取合規性和審核資料庫。</span><span class="sxs-lookup"><span data-stu-id="749be-165">Provide a domain user account and password to access the Compliance and Audit Database.</span></span> <span data-ttu-id="749be-166">將此帳戶的密碼設定為永不過期。</span><span class="sxs-lookup"><span data-stu-id="749be-166">Configure the password for this account to never expire.</span></span> <span data-ttu-id="749be-167">使用者帳戶應該能夠存取 MBAM [報告使用者] 群組提供的所有資料。</span><span class="sxs-lookup"><span data-stu-id="749be-167">The user account should be able to access all data that is available to the MBAM Reports Users group.</span></span>

5.  <span data-ttu-id="749be-168">按一下 **[下一步]** 以繼續使用 Microsoft BitLocker 管理及監視設定向導。</span><span class="sxs-lookup"><span data-stu-id="749be-168">Click **Next** to continue with the Microsoft BitLocker Administration and Monitoring Setup wizard.</span></span>

**<span data-ttu-id="749be-169">安裝自助服務入口網站</span><span class="sxs-lookup"><span data-stu-id="749be-169">To install the Self-Service Portal</span></span>**

1.  <span data-ttu-id="749be-170">在 [**設定自助入口網站**] 頁面上，您可以選擇性地加密自助入口網站與管理與監視伺服器之間的通訊。</span><span class="sxs-lookup"><span data-stu-id="749be-170">On the **Configure the Self-Service Portal** page, you can optionally encrypt the communication between the Self-Service Portal and the Administration and Monitoring servers.</span></span> <span data-ttu-id="749be-171">如果您選擇加密通訊的選項，系統會提示您選取憑證授權單位預配的憑證以用於加密。</span><span class="sxs-lookup"><span data-stu-id="749be-171">If you choose the option to encrypt the communication, you are prompted to select the certification authority-provisioned certificate to use for encryption.</span></span>

2.  <span data-ttu-id="749be-172">按 \[**下一步**\] 繼續。</span><span class="sxs-lookup"><span data-stu-id="749be-172">Click **Next** to continue.</span></span>

3.  <span data-ttu-id="749be-173">指定安裝合規性和審核資料庫的 SQL Server 遠端實例（例如\* &lt; ServerName &gt; \*）。</span><span class="sxs-lookup"><span data-stu-id="749be-173">Specify the remote instance of SQL Server (for example, *&lt;ServerName&gt;*) where the Compliance and Audit Database was installed.</span></span>

4.  <span data-ttu-id="749be-174">指定合規性和審核資料庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="749be-174">Specify the name of the Compliance and Audit Database.</span></span> <span data-ttu-id="749be-175">根據預設，資料庫名稱是 MBAM 合規性狀態。</span><span class="sxs-lookup"><span data-stu-id="749be-175">By default, the database name is MBAM Compliance Status.</span></span> <span data-ttu-id="749be-176">不過，您可以在安裝合規性和審核資料庫時變更名稱。</span><span class="sxs-lookup"><span data-stu-id="749be-176">However, you can change the name when you install the Compliance and Audit Database.</span></span>

5.  <span data-ttu-id="749be-177">按 \[**下一步**\] 繼續。</span><span class="sxs-lookup"><span data-stu-id="749be-177">Click **Next** to continue.</span></span>

6.  <span data-ttu-id="749be-178">指定安裝了復原資料庫的 SQL Server 遠端實例（例如， \* &lt; ServerName &gt; \*）。</span><span class="sxs-lookup"><span data-stu-id="749be-178">Specify the remote instance of SQL Server (for example, *&lt;ServerName&gt;*) where the Recovery Database was installed.</span></span>

7.  <span data-ttu-id="749be-179">指定恢復資料庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="749be-179">Specify the name of the Recovery Database.</span></span> <span data-ttu-id="749be-180">根據預設，資料庫名稱是**MBAM 復原與硬體**。</span><span class="sxs-lookup"><span data-stu-id="749be-180">By default, the database name is **MBAM Recovery and Hardware**.</span></span> <span data-ttu-id="749be-181">不過，您可以在安裝 [恢復資料庫] 功能時變更名稱。</span><span class="sxs-lookup"><span data-stu-id="749be-181">However, you can change the name when you install the Recovery Database feature.</span></span>

8.  <span data-ttu-id="749be-182">按 \[**下一步**\] 繼續。</span><span class="sxs-lookup"><span data-stu-id="749be-182">Click **Next** to continue.</span></span>

9.  <span data-ttu-id="749be-183">輸入**埠號碼**、**主機名稱**（選用），以及 MBAM 管理和監視伺服器的**安裝路徑**。</span><span class="sxs-lookup"><span data-stu-id="749be-183">Enter the **Port Number**, the **Host Name** (optional), and the **Installation Path** for the MBAM Administration and Monitoring Server.</span></span>

    **<span data-ttu-id="749be-184">注意</span><span class="sxs-lookup"><span data-stu-id="749be-184">Note</span></span>**  
    <span data-ttu-id="749be-185">除非您指定唯一主機標頭名稱，否則您指定的埠號碼必須是管理和監視伺服器上未使用的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="749be-185">The port number that you specify must be an unused port number on the Administration and Monitoring server unless you specify a unique host header name.</span></span> <span data-ttu-id="749be-186">如果您使用的是 Windows 防火牆，則會自動開啟埠。</span><span class="sxs-lookup"><span data-stu-id="749be-186">If you are using Windows Firewall, the port will be opened automatically.</span></span>



10. <span data-ttu-id="749be-187">若要選擇性地註冊自助服務入口網站的服務主體名稱（SPN），請選取 [**使用 Active Directory 註冊此電腦的服務主體名稱（spn）] （Windows 驗證所需）**。</span><span class="sxs-lookup"><span data-stu-id="749be-187">To optionally register a Service Principal Name (SPN) for the Self-Service Portal, select **Register this machine’s Service Principal Names (SPN) with Active Directory (Required for Windows Authentication)**.</span></span> <span data-ttu-id="749be-188">如果您選取此核取方塊，MBAM 安裝程式將不會嘗試註冊現有的 Spn，您可以在 MBAM 安裝之前或之後手動註冊 SPN。</span><span class="sxs-lookup"><span data-stu-id="749be-188">If you select this check box, MBAM Setup will not try to register the existing SPNs, and you can manually register the SPN before or after the MBAM installation.</span></span> <span data-ttu-id="749be-189">如需手動登記 SPN 的指示，請參閱[手動 SPN 註冊](https://go.microsoft.com/fwlink/?LinkId=286758)。</span><span class="sxs-lookup"><span data-stu-id="749be-189">For instructions on registering the SPN manually, see [Manual SPN Registration](https://go.microsoft.com/fwlink/?LinkId=286758).</span></span>

11. <span data-ttu-id="749be-190">按一下 **[下一步]** 以繼續使用 Microsoft BitLocker 管理及監視設定向導。</span><span class="sxs-lookup"><span data-stu-id="749be-190">Click **Next** to continue with the Microsoft BitLocker Administration and Monitoring Setup wizard.</span></span>

12. <span data-ttu-id="749be-191">指定是否要使用 Microsoft 更新，協助保護您的電腦安全性，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="749be-191">Specify whether to use Microsoft Updates to help keep your computer secure, and then click **Next**.</span></span>

13. <span data-ttu-id="749be-192">完成選取的 MBAM 功能資訊之後，您就可以使用 [設定] 嚮導開始進行 MBAM 安裝了。</span><span class="sxs-lookup"><span data-stu-id="749be-192">When the selected MBAM feature information is completed, you are ready to start the MBAM installation by using the Setup wizard.</span></span> <span data-ttu-id="749be-193">如果您必須檢查或變更您的安裝設定，請按一下 [**返回**]，在嚮導中移動。</span><span class="sxs-lookup"><span data-stu-id="749be-193">Click **Back** to move through the wizard if you have to review or change your installation settings.</span></span> <span data-ttu-id="749be-194">按一下 [**安裝**] 以開始安裝。</span><span class="sxs-lookup"><span data-stu-id="749be-194">Click **Install** to start the installation.</span></span> <span data-ttu-id="749be-195">按一下 [**取消**] 結束嚮導。</span><span class="sxs-lookup"><span data-stu-id="749be-195">Click **Cancel** to exit the wizard.</span></span> <span data-ttu-id="749be-196">安裝程式會安裝您所選取的 MBAM 功能，並通知您安裝已完成。</span><span class="sxs-lookup"><span data-stu-id="749be-196">Setup installs the MBAM features that you selected and notifies you that the installation is finished.</span></span>

14. <span data-ttu-id="749be-197">按一下 **[完成] 結束**嚮導。</span><span class="sxs-lookup"><span data-stu-id="749be-197">Click **Finish** to exit the wizard.</span></span>

    **<span data-ttu-id="749be-198">注意</span><span class="sxs-lookup"><span data-stu-id="749be-198">Note</span></span>**  
    <span data-ttu-id="749be-199">若要在安裝自助入口網站之後設定它，請使用您的公司名稱和其他公司特定資訊來標記自助入口網站，瞭解[如何為自助服務入口網站打造品牌](how-to-brand-the-self-service-portal.md)，以取得相關指示。</span><span class="sxs-lookup"><span data-stu-id="749be-199">To configure the Self-Service Portal after you installed it, brand the Self-Service Portal with your company name and other company-specific information, see [How to Brand the Self-Service Portal](how-to-brand-the-self-service-portal.md) for instructions.</span></span>



15. <span data-ttu-id="749be-200">如果用戶端電腦具有 Microsoft 內容傳遞網路（CDN）的存取權，讓自助服務入口網站必須存取某些 JavaScript 檔案，您就完成了自助式入口網站的安裝。</span><span class="sxs-lookup"><span data-stu-id="749be-200">If the client computers have access to the Microsoft Content Delivery Network (CDN), which gives the Self-Service Portal the required access to certain JavaScript files, you are finished with the Self-Service Portal installation.</span></span> <span data-ttu-id="749be-201">如果用戶端電腦沒有 Microsoft CDN 的存取權，請完成下一節中的步驟，將自助式入口網站設定為從易於存取的來源中參考 JavaScript 檔案。</span><span class="sxs-lookup"><span data-stu-id="749be-201">If the client computers does not have access to the Microsoft CDN, complete the steps in the next section to configure the Self-Service Portal to reference the JavaScript files from an accessible source.</span></span>

**<span data-ttu-id="749be-202">當使用者無法存取 Microsoft 內容傳遞網路時，設定自助服務入口網站</span><span class="sxs-lookup"><span data-stu-id="749be-202">To configure the Self-Service Portal when end users cannot access the Microsoft Content Delivery Network</span></span>**

1. <span data-ttu-id="749be-203">如果用戶端電腦具有 Microsoft 內容傳遞網路（CDN）的存取權，讓自助入口網站安裝特定 JavaScript 檔案，就會完成自助入口網站的安裝。</span><span class="sxs-lookup"><span data-stu-id="749be-203">If the client computers have access to the Microsoft Content Delivery Network (CDN), which gives the Self-Service Portal the required access to certain JavaScript files, the Self-Service Portal installation is completed.</span></span> <span data-ttu-id="749be-204">如果用戶端電腦沒有 Microsoft CDN 的存取權，請完成本節中的其餘步驟，將自助式入口網站設定為從易於存取的來源中參考 JavaScript 檔案。</span><span class="sxs-lookup"><span data-stu-id="749be-204">If the client computers do not have access to the Microsoft CDN, complete the remaining steps in this section to configure the Self-Service Portal to reference the JavaScript files from an accessible source.</span></span>

2. <span data-ttu-id="749be-205">從 Microsoft CDN 下載四個 JavaScript 檔案：</span><span class="sxs-lookup"><span data-stu-id="749be-205">Download the four JavaScript files from the Microsoft CDN:</span></span>

   -   <span data-ttu-id="749be-206">jQuery-1.7.2.min.js-[https://go.microsoft.com/p/fwlink/?LinkID=271736](https://go.microsoft.com/fwlink/p/?LinkID=271736)</span><span class="sxs-lookup"><span data-stu-id="749be-206">jQuery-1.7.2.min.js - [https://go.microsoft.com/p/fwlink/?LinkID=271736](https://go.microsoft.com/fwlink/p/?LinkID=271736)</span></span>

   -   <span data-ttu-id="749be-207">MicrosoftAjax.js –[https://go.microsoft.com/p/fwlink/?LinkId=272283](https://go.microsoft.com/fwlink/p/?LinkId=272283)</span><span class="sxs-lookup"><span data-stu-id="749be-207">MicrosoftAjax.js –[https://go.microsoft.com/p/fwlink/?LinkId=272283](https://go.microsoft.com/fwlink/p/?LinkId=272283)</span></span>

   -   <span data-ttu-id="749be-208">MicrosoftMvcAjax.js-[https://go.microsoft.com/p/fwlink/?LinkId=272284](https://go.microsoft.com/fwlink/p/?LinkId=272284)</span><span class="sxs-lookup"><span data-stu-id="749be-208">MicrosoftMvcAjax.js - [https://go.microsoft.com/p/fwlink/?LinkId=272284](https://go.microsoft.com/fwlink/p/?LinkId=272284)</span></span>

   -   <span data-ttu-id="749be-209">MicrosoftMvcValidation.js-</span><span class="sxs-lookup"><span data-stu-id="749be-209">MicrosoftMvcValidation.js -</span></span> <https://go.microsoft.com/fwlink/p/?LinkId=272285>

3. <span data-ttu-id="749be-210">將 JavaScript 檔案複製到自助服務入口網站的 [**腳本**] 目錄。</span><span class="sxs-lookup"><span data-stu-id="749be-210">Copy the JavaScript files to the **Scripts** directory of the Self-Service Portal.</span></span> <span data-ttu-id="749be-211">此目錄位於 <em> &lt; MBAM 自助安裝目錄 &gt; \\ </em> 自助服務 Website\\Scripts。</span><span class="sxs-lookup"><span data-stu-id="749be-211">This directory is located in <em>&lt;MBAM Self-Service Install Directory&gt;\\</em>Self Service Website\\Scripts.</span></span>

4. <span data-ttu-id="749be-212">開啟 **[網際網路資訊服務（IIS）管理員**]。</span><span class="sxs-lookup"><span data-stu-id="749be-212">Open **Internet Information Services (IIS) Manager**.</span></span>

5. <span data-ttu-id="749be-213">展開 [**網站** &gt; **Microsoft BitLocker 管理與監視**]，然後醒目提示 [ **SelfService**]。</span><span class="sxs-lookup"><span data-stu-id="749be-213">Expand **Sites** &gt; **Microsoft BitLocker Administration and Monitoring**, and highlight **SelfService**.</span></span>

   **<span data-ttu-id="749be-214">注意</span><span class="sxs-lookup"><span data-stu-id="749be-214">Note</span></span>**  
   <span data-ttu-id="749be-215">*SelfService*是預設的虛擬目錄名稱。</span><span class="sxs-lookup"><span data-stu-id="749be-215">*SelfService* is the default virtual directory name.</span></span> <span data-ttu-id="749be-216">如果您在安裝期間為此目錄選擇了其他名稱，請記得使用您所選擇的名稱來取代其餘指令中的*SelfService* 。</span><span class="sxs-lookup"><span data-stu-id="749be-216">If you chose a different name for this directory during installation, remember to replace *SelfService* in the rest of these instructions with the name you chose.</span></span>



6. <span data-ttu-id="749be-217">按兩下中間窗格中的 [**應用程式設定**]。</span><span class="sxs-lookup"><span data-stu-id="749be-217">In the middle pane, double-click **Application Settings**.</span></span>

7. <span data-ttu-id="749be-218">針對下列清單中的每個專案，透過 &lt; &gt; 使用/SelfService/（或您在安裝時選擇的名稱）取代虛擬目錄，來編輯應用程式設定以參照新的位置。</span><span class="sxs-lookup"><span data-stu-id="749be-218">For each item in the following list, edit the application settings to reference the new location by replacing &lt;virtual directory&gt; with /SelfService/ (or the name you chose during installation).</span></span> <span data-ttu-id="749be-219">例如，虛擬目錄路徑會類似/selfservice/scripts/jquery-1.7.2.min.js。</span><span class="sxs-lookup"><span data-stu-id="749be-219">For example, the virtual directory path will be similar to /selfservice/scripts/jquery-1.7.2.min.js.</span></span>

   -   <span data-ttu-id="749be-220">jQueryPath：/ &lt; virtual directory &gt; /Scripts/jQuery-1.7.2.min.js</span><span class="sxs-lookup"><span data-stu-id="749be-220">jQueryPath: /&lt;virtual directory&gt;/Scripts/ jQuery-1.7.2.min.js</span></span>

   -   <span data-ttu-id="749be-221">MicrosoftAjaxPath：/ &lt; virtual directory &gt; /Scripts/MicrosoftAjax.js</span><span class="sxs-lookup"><span data-stu-id="749be-221">MicrosoftAjaxPath: /&lt;virtual directory&gt;/Scripts/ MicrosoftAjax.js</span></span>

   -   <span data-ttu-id="749be-222">MicrosoftMvcAjaxPath：/ &lt; virtual directory &gt; /Scripts/MicrosoftMvcAjax.js</span><span class="sxs-lookup"><span data-stu-id="749be-222">MicrosoftMvcAjaxPath: /&lt;virtual directory&gt;/Scripts/ MicrosoftMvcAjax.js</span></span>

   -   <span data-ttu-id="749be-223">MicrosoftMvcValidationPath：/ &lt; virtual directory &gt; /Scripts/MicrosoftMvcValidation.js</span><span class="sxs-lookup"><span data-stu-id="749be-223">MicrosoftMvcValidationPath: /&lt;virtual directory&gt;/Scripts/ MicrosoftMvcValidation.js</span></span>

**<span data-ttu-id="749be-224">若要安裝 [管理及監視伺服器] 功能</span><span class="sxs-lookup"><span data-stu-id="749be-224">To install the Administration and Monitoring Server feature</span></span>**

1. <span data-ttu-id="749be-225">MBAM 可以加密 Web 服務與管理與監視伺服器之間的通訊。</span><span class="sxs-lookup"><span data-stu-id="749be-225">MBAM can encrypt the communication between the Web Services and the Administration and Monitoring servers.</span></span> <span data-ttu-id="749be-226">如果您選擇加密通訊的選項，系統會提示您選取憑證授權單位預配的憑證以用於加密。</span><span class="sxs-lookup"><span data-stu-id="749be-226">If you choose the option to encrypt the communication, you are prompted to select the certification authority-provisioned certificate to use for encryption.</span></span>

2. <span data-ttu-id="749be-227">按 \[**下一步**\] 繼續。</span><span class="sxs-lookup"><span data-stu-id="749be-227">Click **Next** to continue.</span></span>

3. <span data-ttu-id="749be-228">指定安裝合規性和審核資料庫的 SQL Server 遠端實例（例如： \* &lt; ServerName &gt; \*）。</span><span class="sxs-lookup"><span data-stu-id="749be-228">Specify the remote instance of SQL Server (for example: *&lt;ServerName&gt;*) where the Compliance and Audit Database was installed.</span></span>

4. <span data-ttu-id="749be-229">指定合規性和審核資料庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="749be-229">Specify the name of the Compliance and Audit Database.</span></span> <span data-ttu-id="749be-230">根據預設，資料庫名稱是 MBAM 合規性狀態。</span><span class="sxs-lookup"><span data-stu-id="749be-230">By default, the database name is MBAM Compliance Status.</span></span> <span data-ttu-id="749be-231">不過，您可以在安裝合規性和審核資料庫時變更名稱。</span><span class="sxs-lookup"><span data-stu-id="749be-231">However, you can change the name when you install the Compliance and Audit Database.</span></span>

5. <span data-ttu-id="749be-232">按 \[**下一步**\] 繼續。</span><span class="sxs-lookup"><span data-stu-id="749be-232">Click **Next** to continue.</span></span>

6. <span data-ttu-id="749be-233">指定安裝恢復資料庫的 SQL Server 遠端實例（例如： \* &lt; ServerName &gt; \*）。</span><span class="sxs-lookup"><span data-stu-id="749be-233">Specify the remote instance of SQL Server (for example: *&lt;ServerName&gt;*) where the Recovery Database was installed.</span></span>

7. <span data-ttu-id="749be-234">指定恢復資料庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="749be-234">Specify the name of the Recovery Database.</span></span> <span data-ttu-id="749be-235">根據預設，資料庫名稱是**MBAM 復原與硬體**。</span><span class="sxs-lookup"><span data-stu-id="749be-235">By default, the database name is **MBAM Recovery and Hardware**.</span></span> <span data-ttu-id="749be-236">不過，您可以在安裝 [恢復資料庫] 功能時變更名稱。</span><span class="sxs-lookup"><span data-stu-id="749be-236">However, you can change the name when you install the Recovery Database feature.</span></span>

8. <span data-ttu-id="749be-237">按 \[**下一步**\] 繼續。</span><span class="sxs-lookup"><span data-stu-id="749be-237">Click **Next** to continue.</span></span>

9. <span data-ttu-id="749be-238">指定 SQL Server Reporting Services （SRS）網站的 "Home" URL。</span><span class="sxs-lookup"><span data-stu-id="749be-238">Specify the URL for the “Home” of the SQL Server Reporting Services (SRS) site.</span></span> <span data-ttu-id="749be-239">SQL Server Reporting Services 網站實例的預設首頁位置是：</span><span class="sxs-lookup"><span data-stu-id="749be-239">The default Home location of a SQL Server Reporting Services site instance is at:</span></span>

   <span data-ttu-id="749be-240">HTTP:// <em> &lt; NameofMBAMReportsServer &gt; / </em> ReportServer</span><span class="sxs-lookup"><span data-stu-id="749be-240">http://<em>&lt;NameofMBAMReportsServer&gt;/</em>ReportServer</span></span>

   **<span data-ttu-id="749be-241">注意</span><span class="sxs-lookup"><span data-stu-id="749be-241">Note</span></span>**  
   <span data-ttu-id="749be-242">如果 SQL Server Reporting Services 已設定為命名實例，URL 會類似下列： HTTP://\* &lt; NameofMBAMReportsServer &gt; */ReportServer\_* &lt; SRSInstanceName &gt; \*。</span><span class="sxs-lookup"><span data-stu-id="749be-242">If SQL Server Reporting Services was configured as a named instance, the URL resembles the following: http://*&lt;NameofMBAMReportsServer&gt;*/ReportServer\_*&lt;SRSInstanceName&gt;*.</span></span>



10. <span data-ttu-id="749be-243">按 \[**下一步**\] 繼續。</span><span class="sxs-lookup"><span data-stu-id="749be-243">Click **Next** to continue.</span></span>

11. <span data-ttu-id="749be-244">輸入**埠號碼**、**主機名稱**（選用），以及 MBAM 管理和監視伺服器的**安裝路徑**。</span><span class="sxs-lookup"><span data-stu-id="749be-244">Enter the **Port Number**, the **Host Name** (optional), and the **Installation Path** for the MBAM Administration and Monitoring Server.</span></span>

    **<span data-ttu-id="749be-245">注意</span><span class="sxs-lookup"><span data-stu-id="749be-245">Note</span></span>**  
    <span data-ttu-id="749be-246">除非您指定唯一主機標頭名稱，否則您指定的埠號碼必須是管理和監視伺服器上未使用的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="749be-246">The port number that you specify must be an unused port number on the Administration and Monitoring server unless you specify a unique host header name.</span></span> <span data-ttu-id="749be-247">如果您使用的是 Windows 防火牆，則會自動開啟埠。</span><span class="sxs-lookup"><span data-stu-id="749be-247">If you are using Windows Firewall, the port will be opened automatically.</span></span>



12. <span data-ttu-id="749be-248">若要選擇性地註冊自助服務入口網站的服務主體名稱（SPN），請選取 [**使用 Active Directory 註冊此電腦的服務主體名稱（spn）] （Windows 驗證所需）**。</span><span class="sxs-lookup"><span data-stu-id="749be-248">To optionally register a Service Principal Name (SPN) for the Self-Service Portal, select **Register this machine’s Service Principal Names (SPN) with Active Directory (Required for Windows Authentication)**.</span></span> <span data-ttu-id="749be-249">如果您選取此核取方塊，MBAM 安裝程式將不會嘗試註冊現有的 Spn，您可以在 MBAM 安裝之前或之後手動註冊 SPN。</span><span class="sxs-lookup"><span data-stu-id="749be-249">If you select this check box, MBAM Setup will not try to register the existing SPNs, and you can manually register the SPN before or after the MBAM installation.</span></span> <span data-ttu-id="749be-250">如需手動登記 SPN 的指示，請參閱[手動 SPN 註冊](https://go.microsoft.com/fwlink/?LinkId=286758)。</span><span class="sxs-lookup"><span data-stu-id="749be-250">For instructions on registering the SPN manually, see [Manual SPN Registration](https://go.microsoft.com/fwlink/?LinkId=286758).</span></span>

13. <span data-ttu-id="749be-251">按一下 **[下一步]** 以繼續使用 Microsoft BitLocker 管理及監視設定向導。</span><span class="sxs-lookup"><span data-stu-id="749be-251">Click **Next** to continue with the Microsoft BitLocker Administration and Monitoring Setup wizard.</span></span>

14. <span data-ttu-id="749be-252">指定是否要使用 Microsoft 更新，協助保護您的電腦安全性，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="749be-252">Specify whether to use Microsoft Updates to help keep your computer secure, and then click **Next**.</span></span>

15. <span data-ttu-id="749be-253">完成選取的 MBAM 功能資訊之後，您就可以使用 [設定] 嚮導開始進行 MBAM 安裝了。</span><span class="sxs-lookup"><span data-stu-id="749be-253">When the selected MBAM feature information is completed, you are ready to start the MBAM installation by using the Setup wizard.</span></span> <span data-ttu-id="749be-254">如果您必須檢查或變更您的安裝設定，請按一下 [**返回**]，在嚮導中移動。</span><span class="sxs-lookup"><span data-stu-id="749be-254">Click **Back** to move through the wizard if you have to review or change your installation settings.</span></span> <span data-ttu-id="749be-255">按一下 [**安裝**] 進行安裝。</span><span class="sxs-lookup"><span data-stu-id="749be-255">Click **Install** to being the installation.</span></span> <span data-ttu-id="749be-256">按一下 [**取消**] 結束嚮導。</span><span class="sxs-lookup"><span data-stu-id="749be-256">Click **Cancel** to exit the wizard.</span></span> <span data-ttu-id="749be-257">安裝程式會安裝您所選取的 MBAM 功能，並通知您安裝已完成。</span><span class="sxs-lookup"><span data-stu-id="749be-257">Setup installs the MBAM features that you selected and notifies you that the installation is finished.</span></span>

16. <span data-ttu-id="749be-258">按一下 **[完成] 結束**嚮導。</span><span class="sxs-lookup"><span data-stu-id="749be-258">Click **Finish** to exit the wizard.</span></span>

**<span data-ttu-id="749be-259">若要執行安裝後設定</span><span class="sxs-lookup"><span data-stu-id="749be-259">To perform post-installation configuration</span></span>**

1.  <span data-ttu-id="749be-260">在 [管理和監視伺服器] 上，將使用者新增至下列本機群組，以授予他們存取 MBAM 管理和監視網站上的功能。</span><span class="sxs-lookup"><span data-stu-id="749be-260">On the Administration and Monitoring Server, add users to the following local groups to give them access to the features on the MBAM Administration and Monitoring website.</span></span>

    -   <span data-ttu-id="749be-261">**MBAM 支援人員**：此本機群組的成員可以存取 [MBAM 管理及監視] 網站上的 [磁碟機復原] 及 [管理 TPM] 功能。</span><span class="sxs-lookup"><span data-stu-id="749be-261">**MBAM Helpdesk Users**: Members of this local group can access the Drive Recovery and Manage TPM features on the MBAM Administration and Monitoring website.</span></span> <span data-ttu-id="749be-262">[磁碟機復原] 和 [管理 TPM] 中的所有欄位都是技術支援人員的必要欄位。</span><span class="sxs-lookup"><span data-stu-id="749be-262">All fields in Drive Recovery and Manage TPM are required fields for a Helpdesk User.</span></span>

    -   <span data-ttu-id="749be-263">**MBAM 高級支援人員的使用者**：此本機群組的成員可以高級存取磁片磁碟機，並在 [MBAM 管理] 和 [監視] 網站上管理 TPM 功能。</span><span class="sxs-lookup"><span data-stu-id="749be-263">**MBAM Advanced Helpdesk Users**: Members of this local group have advanced access to the Drive Recovery and Manage TPM features on the MBAM Administration and Monitoring website.</span></span> <span data-ttu-id="749be-264">針對高級支援人員的使用者，磁片磁碟機復原只需要 [金鑰識別碼] 欄位。</span><span class="sxs-lookup"><span data-stu-id="749be-264">For Advanced Helpdesk Users, only the Key ID field is required in Drive Recovery.</span></span> <span data-ttu-id="749be-265">在 [**管理 TPM**] 中，只需要 [**電腦網域**] 欄位和 [**電腦名稱稱**] 欄位。</span><span class="sxs-lookup"><span data-stu-id="749be-265">In **Manage TPM**, only the **Computer Domain** field and **Computer Name** field are required.</span></span>

2.  <span data-ttu-id="749be-266">在承載管理和監控伺服器以及合規性和審核資料庫的伺服器上，以及駐留合規性和審核報告的伺服器上，將使用者新增至下列當地群組，以授予他們存取 MBAM 管理和監控網站上的 [報告] 功能。</span><span class="sxs-lookup"><span data-stu-id="749be-266">On the server that hosts Administration and Monitoring Server and the Compliance and Audit Database and on the server that hosts the Compliance and Audit Reports, add users to the following local group to give them access to the Reports feature on the MBAM Administration and Monitoring website.</span></span>

    -   <span data-ttu-id="749be-267">**MBAM 報表使用者**：此本機群組的成員可以存取 MBAM 管理和監控網站上的報告。</span><span class="sxs-lookup"><span data-stu-id="749be-267">**MBAM Report Users**: Members of this local group can access the reports on the MBAM Administration and Monitoring website.</span></span>

    **<span data-ttu-id="749be-268">注意</span><span class="sxs-lookup"><span data-stu-id="749be-268">Note</span></span>**  
    <span data-ttu-id="749be-269">**MBAM 報告**的使用者或群組成員資格使用者的本機群組必須在已安裝 MBAM 管理和監控伺服器功能、合規性和審核資料庫以及合規性和審核報告的所有電腦上維持。</span><span class="sxs-lookup"><span data-stu-id="749be-269">Identical user or group membership of the **MBAM Report Users** local group must be maintained on all computers where the MBAM Administration and Monitoring Server features, Compliance and Audit Database, and the Compliance and Audit Reports are installed.</span></span>



## <span data-ttu-id="749be-270">驗證 MBAM Server 功能安裝</span><span class="sxs-lookup"><span data-stu-id="749be-270">Validating the MBAM Server Feature Installation</span></span>


<span data-ttu-id="749be-271">當 Microsoft BitLocker 管理和監視伺服器功能安裝完成後，建議您確認安裝已成功設定 MBAM 的所有必要功能。</span><span class="sxs-lookup"><span data-stu-id="749be-271">When Microsoft BitLocker Administration and Monitoring Server feature installation is completed, we recommend that you validate that the installation has successfully set up all the necessary features for MBAM.</span></span> <span data-ttu-id="749be-272">使用下列程式來確認 Microsoft BitLocker 管理及監視服務運作正常。</span><span class="sxs-lookup"><span data-stu-id="749be-272">Use the following procedure to confirm that the Microsoft BitLocker Administration and Monitoring service is functional.</span></span>

**<span data-ttu-id="749be-273">驗證 MBAM 伺服器安裝</span><span class="sxs-lookup"><span data-stu-id="749be-273">To validate an MBAM Server installation</span></span>**

1. <span data-ttu-id="749be-274">在部署 MBAM 功能的每個伺服器上，開啟 [**控制台**]，選取 [**程式**]，然後選取 [**程式和功能**]。</span><span class="sxs-lookup"><span data-stu-id="749be-274">On each server where an MBAM feature is deployed, open **Control Panel**, select **Programs**, and then select **Programs and Features**.</span></span> <span data-ttu-id="749be-275">確認 [**程式和功能**] 清單中出現 [ **Microsoft BitLocker 管理及監視**]。</span><span class="sxs-lookup"><span data-stu-id="749be-275">Verify that **Microsoft BitLocker Administration and Monitoring** appears in the **Programs and Features** list.</span></span>

   **<span data-ttu-id="749be-276">注意</span><span class="sxs-lookup"><span data-stu-id="749be-276">Note</span></span>**  
   <span data-ttu-id="749be-277">若要驗證 MBAM 安裝，您必須使用在每個伺服器上都有本機電腦管理認證的網域帳戶。</span><span class="sxs-lookup"><span data-stu-id="749be-277">To validate the MBAM installation, you must use a domain account that has local computer administrative credentials on each server.</span></span>



2. <span data-ttu-id="749be-278">在安裝了復原資料庫的伺服器上，開啟 SQL Server Management Studio 並確認已安裝**MBAM 復原與硬體**資料庫。</span><span class="sxs-lookup"><span data-stu-id="749be-278">On the server where the Recovery Database is installed, open SQL Server Management Studio and verify that the **MBAM Recovery and Hardware** database is installed.</span></span>

3. <span data-ttu-id="749be-279">在已安裝合規性和審核資料庫的伺服器上，開啟 SQL Server Management Studio 並確認已安裝**MBAM 合規性狀態資料庫**。</span><span class="sxs-lookup"><span data-stu-id="749be-279">On the server where the Compliance and Audit Database is installed, open SQL Server Management Studio and verify that the **MBAM Compliance Status Database** is installed.</span></span>

4. <span data-ttu-id="749be-280">在已安裝合規性和審核報告的伺服器上，使用系統管理認證開啟網頁瀏覽器，然後流覽至 SQL Server Reporting Services 網站的 "Home"。</span><span class="sxs-lookup"><span data-stu-id="749be-280">On the server where the Compliance and Audit Reports are installed, open a web browser with administrative credentials and browse to the “Home” of the SQL Server Reporting Services site.</span></span>

   <span data-ttu-id="749be-281">您可以在 HTTP:// <em> &lt; NameofMBAMReportsServer &gt; </em> /Reports.aspx. 中找到 SQL Server Reporting Services 網站實例的預設首頁位置。</span><span class="sxs-lookup"><span data-stu-id="749be-281">The default Home location of a SQL Server Reporting Services site instance can be found is at http://<em>&lt;NameofMBAMReportsServer&gt;</em>/Reports.aspx.</span></span> <span data-ttu-id="749be-282">若要尋找實際的 URL，請使用 Reporting Services Configuration Manager 工具，然後選取在安裝期間指定的實例。</span><span class="sxs-lookup"><span data-stu-id="749be-282">To find the actual URL, use the Reporting Services Configuration Manager tool and select the instances that were specified during setup.</span></span>

   <span data-ttu-id="749be-283">確認名為**Microsoft BitLocker 管理和監視**的報表資料夾包含名為**MaltaDataSource**的資料來源，且**en-us**資料夾包含四個報表。</span><span class="sxs-lookup"><span data-stu-id="749be-283">Confirm that a reports folder named **Microsoft BitLocker Administration and Monitoring** contains a data source called **MaltaDataSource** and that an **en-us** folder contains four reports.</span></span>

   **<span data-ttu-id="749be-284">注意</span><span class="sxs-lookup"><span data-stu-id="749be-284">Note</span></span>**  
   <span data-ttu-id="749be-285">如果 SQL Server Reporting Services 已設定為命名實例，URL 應該會類似下列內容： HTTP：//\* &lt; NameofMBAMReportsServer &gt; */Reports\_* &lt; SRSInstanceName &gt; \*</span><span class="sxs-lookup"><span data-stu-id="749be-285">If SQL Server Reporting Services was configured as a named instance, the URL should resemble the following:http://*&lt;NameofMBAMReportsServer&gt;*/Reports\_*&lt;SRSInstanceName&gt;*</span></span>



~~~
**Note**  
If SSRS was not configured to use Secure Socket Layer (SSL), the URL for the reports will be set to HTTP instead of HTTPS when you install the MBAM Server. If you then go to the Administration and Monitoring website and select a report, the following message appears: “Only Secure Content is Displayed.” To show the report, click **Show All Content**.
~~~



5. <span data-ttu-id="749be-286">在已安裝 [管理及監視] 功能的伺服器上，執行 [**伺服器管理員**] 並流覽至 [**角色**]。</span><span class="sxs-lookup"><span data-stu-id="749be-286">On the server where the Administration and Monitoring feature is installed, run **Server Manager** and browse to **Roles**.</span></span> <span data-ttu-id="749be-287">選取 **[Web 服務器（iis）**]，然後按一下 [**網際網路資訊服務（iis）管理員**]。</span><span class="sxs-lookup"><span data-stu-id="749be-287">Select **Web Server (IIS)**, and then click **Internet Information Services (IIS) Manager**.</span></span>

6. <span data-ttu-id="749be-288">在 **[連線] 中，** 流覽至 [ \* &lt; computername &gt; \*]，選取 [**網站**]，然後選取 [ **Microsoft BitLocker 管理與監視**]。</span><span class="sxs-lookup"><span data-stu-id="749be-288">In **Connections**, browse to *&lt;computername&gt;*, select **Sites**, and select **Microsoft BitLocker Administration and Monitoring**.</span></span> <span data-ttu-id="749be-289">確認 [ **MBAMAdministrationService**]、[ **MBAMComplianceStatusService**] 和 [ **MBAMRecoveryAndHardwareService** ] 都已列出。</span><span class="sxs-lookup"><span data-stu-id="749be-289">Verify that **MBAMAdministrationService**, **MBAMComplianceStatusService**, and **MBAMRecoveryAndHardwareService** are listed.</span></span>

7. <span data-ttu-id="749be-290">在已安裝 [管理] 和 [監視] 功能及 [自助式入口網站] 的伺服器上，使用系統管理認證開啟網頁瀏覽器，並流覽至下列位置，以確認它們已順利載入。</span><span class="sxs-lookup"><span data-stu-id="749be-290">On the server where the Administration and Monitoring features and Self-Service Portal are installed, open a web browser with administrative credentials and browse to the following locations to verify that they load successfully.</span></span>

   **<span data-ttu-id="749be-291">注意</span><span class="sxs-lookup"><span data-stu-id="749be-291">Note</span></span>**  
   <span data-ttu-id="749be-292">以 ".svc" 結尾的 Url 不會顯示網站。</span><span class="sxs-lookup"><span data-stu-id="749be-292">The URLs ending in “.svc” do not display a website.</span></span> <span data-ttu-id="749be-293">成功是由「此服務目前已停用的中繼資料發佈」或類似程式碼的資訊所指示。</span><span class="sxs-lookup"><span data-stu-id="749be-293">Success is indicated by the message “Metadata publishing for this service is currently disabled” or by information resembling code.</span></span> <span data-ttu-id="749be-294">如果您看到一些其他的錯誤訊息，或是找不到頁面，就沒有成功載入頁面。</span><span class="sxs-lookup"><span data-stu-id="749be-294">If you see some other error message or if the page cannot be found, the page has not loaded successfully.</span></span>



~~~
-   *http://&lt;hostname&gt;/HelpDesk/default.aspx* and confirm each of the links for navigation and reports

-   *http://&lt;hostname&gt;/SelfService&gt;/*

-   *http://&lt;computername&gt;/MBAMAdministrationService/AdministrationService.svc*

-   *http://&lt;hostname&gt;/MBAMUserSupportService/UserSupportService.svc*

-   *http://&lt;computername&gt;/MBAMComplianceStatusService/StatusReportingService.svc*

-   *http://&lt;computername&gt;/MBAMRecoveryAndHardwareService/CoreService.svc*

**Note**  
It is assumed that the server features were installed on the default port without network encryption. If you installed the server features on a different port or virtual directory, change the URLs to include the appropriate port, for example, *http://&lt;hostname&gt;:&lt;port&gt;/HelpDesk/default.aspx* or*http://&lt;hostname&gt;:&lt;port&gt;/&lt;virtualdirectory&gt;/default.aspx*

If the server features were installed with network encryption, change http:// to https://.
~~~



8. <span data-ttu-id="749be-295">確認每個網頁都已順利載入。</span><span class="sxs-lookup"><span data-stu-id="749be-295">Verify that each webpage loads successfully.</span></span>

## <span data-ttu-id="749be-296">相關主題</span><span class="sxs-lookup"><span data-stu-id="749be-296">Related topics</span></span>


[<span data-ttu-id="749be-297">部署 MBAM 2.0 伺服器基礎結構</span><span class="sxs-lookup"><span data-stu-id="749be-297">Deploying the MBAM 2.0 Server Infrastructure</span></span>](deploying-the-mbam-20-server-infrastructure-mbam-2.md)









