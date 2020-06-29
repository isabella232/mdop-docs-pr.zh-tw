---
title: 如何在分散式伺服器上安裝及設定 MBAM
description: 如何在分散式伺服器上安裝及設定 MBAM
author: dansimp
ms.assetid: 9ee766aa-6339-422a-8d00-4f58e4646a5e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 51f56a12d4e59226f834c7e474af0f1e96c1e8e9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811288"
---
# <span data-ttu-id="321f1-103">如何在分散式伺服器上安裝及設定 MBAM</span><span class="sxs-lookup"><span data-stu-id="321f1-103">How to Install and Configure MBAM on Distributed Servers</span></span>


<span data-ttu-id="321f1-104">本主題中的程式說明分散式伺服器上的 Microsoft BitLocker 管理與監視（MBAM）功能的完整安裝。</span><span class="sxs-lookup"><span data-stu-id="321f1-104">The procedures in this topic describe the full installation of the Microsoft BitLocker Administration and Monitoring (MBAM) features on distributed servers.</span></span>

<span data-ttu-id="321f1-105">每個伺服器功能都有特定的先決條件。</span><span class="sxs-lookup"><span data-stu-id="321f1-105">Each server feature has certain prerequisites.</span></span> <span data-ttu-id="321f1-106">若要確認您已符合系統必備與硬體和軟體需求，請參閱[MBAM 1.0 部署先決條件](mbam-10-deployment-prerequisites.md)和[MBAM 1.0 支援](mbam-10-supported-configurations.md)的設定。</span><span class="sxs-lookup"><span data-stu-id="321f1-106">To verify that you have met the prerequisites and hardware and software requirements, see [MBAM 1.0 Deployment Prerequisites](mbam-10-deployment-prerequisites.md) and [MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md).</span></span> <span data-ttu-id="321f1-107">此外，部分功能需要您在安裝程式期間提供特定資訊，才能成功部署該功能。</span><span class="sxs-lookup"><span data-stu-id="321f1-107">In addition, some features require that you provide certain information during the installation process to successfully deploy the feature.</span></span>

**<span data-ttu-id="321f1-108">注意</span><span class="sxs-lookup"><span data-stu-id="321f1-108">Note</span></span>**  
<span data-ttu-id="321f1-109">若要取得安裝記錄檔，您必須使用**msiexec**套件和 \*\*/l &lt; LOCATION &gt; \*\*選項來安裝 MBAM。</span><span class="sxs-lookup"><span data-stu-id="321f1-109">To obtain the setup log files, you have to install MBAM by using the **msiexec** package and the **/l &lt;location&gt;** option.</span></span> <span data-ttu-id="321f1-110">記錄檔案是在您指定的位置建立。</span><span class="sxs-lookup"><span data-stu-id="321f1-110">Log files are created in the location that you specify.</span></span>

<span data-ttu-id="321f1-111">在執行 MBAM 安裝的使用者的% temp% 資料夾中，會建立其他設定記錄檔。</span><span class="sxs-lookup"><span data-stu-id="321f1-111">Additional setup log files are created in the %temp% folder of the user that runs the MBAM installation.</span></span>



## <a href="" id="deploy-the-mbam-server-features-"></a><span data-ttu-id="321f1-112">部署 MBAM 伺服器功能</span><span class="sxs-lookup"><span data-stu-id="321f1-112">Deploy the MBAM Server features</span></span>


<span data-ttu-id="321f1-113">下列步驟說明如何安裝一般 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="321f1-113">The following steps describe how to install the general MBAM features.</span></span>

**<span data-ttu-id="321f1-114">注意</span><span class="sxs-lookup"><span data-stu-id="321f1-114">Note</span></span>**  
<span data-ttu-id="321f1-115">請務必在32位伺服器上使用32位設定，以及在64位伺服器上進行64位設定。</span><span class="sxs-lookup"><span data-stu-id="321f1-115">Make sure that you use the 32-bit setup on 32-bit servers and the 64-bit setup on 64-bit servers.</span></span>



**<span data-ttu-id="321f1-116">部署 MBAM 伺服器功能</span><span class="sxs-lookup"><span data-stu-id="321f1-116">To Deploy MBAM Server features</span></span>**

1.  <span data-ttu-id="321f1-117">啟動 [MBAM 安裝] 嚮導，然後按一下 [歡迎] 頁面上的 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="321f1-117">Start the MBAM installation wizard, and click **Install** at the Welcome page.</span></span>

2.  <span data-ttu-id="321f1-118">閱讀並接受 Microsoft 軟體授權條款，然後按一下 **[下一步]** 繼續安裝。</span><span class="sxs-lookup"><span data-stu-id="321f1-118">Read and accept the Microsoft Software License Terms, and then click **Next** to continue the installation.</span></span>

3.  <span data-ttu-id="321f1-119">根據預設，所有的 MBAM 功能都已選取 [安裝]。</span><span class="sxs-lookup"><span data-stu-id="321f1-119">By default, all MBAM features are selected for installation.</span></span> <span data-ttu-id="321f1-120">清除您想要安裝在其他位置的功能。</span><span class="sxs-lookup"><span data-stu-id="321f1-120">Clear the features that you want to install elsewhere.</span></span> <span data-ttu-id="321f1-121">您要在同一部電腦上安裝的功能，必須同時安裝所有功能。</span><span class="sxs-lookup"><span data-stu-id="321f1-121">Features that you want to install on the same computer must be installed all at the same time.</span></span> <span data-ttu-id="321f1-122">MBAM 功能必須以下列順序安裝：</span><span class="sxs-lookup"><span data-stu-id="321f1-122">MBAM features must be installed in the following order:</span></span>

    -   <span data-ttu-id="321f1-123">恢復與硬體資料庫</span><span class="sxs-lookup"><span data-stu-id="321f1-123">Recovery and Hardware Database</span></span>

    -   <span data-ttu-id="321f1-124">合規性和審核資料庫</span><span class="sxs-lookup"><span data-stu-id="321f1-124">Compliance and Audit Database</span></span>

    -   <span data-ttu-id="321f1-125">合規性審核與報告</span><span class="sxs-lookup"><span data-stu-id="321f1-125">Compliance Audit and Reports</span></span>

    -   <span data-ttu-id="321f1-126">管理和監控伺服器</span><span class="sxs-lookup"><span data-stu-id="321f1-126">Administration and Monitoring Server</span></span>

    -   <span data-ttu-id="321f1-127">MBAM 群組原則範本</span><span class="sxs-lookup"><span data-stu-id="321f1-127">MBAM Group Policy Template</span></span>

    **<span data-ttu-id="321f1-128">注意</span><span class="sxs-lookup"><span data-stu-id="321f1-128">Note</span></span>**  
    <span data-ttu-id="321f1-129">安裝精靈會檢查安裝的先決條件，並顯示遺失的先決條件。</span><span class="sxs-lookup"><span data-stu-id="321f1-129">The installation wizard checks the prerequisites for your installation and displays the prerequisites that are missing.</span></span> <span data-ttu-id="321f1-130">如果符合所有先決條件，安裝會繼續進行。</span><span class="sxs-lookup"><span data-stu-id="321f1-130">If all the prerequisites are met, the installation continues.</span></span> <span data-ttu-id="321f1-131">如果偵測到遺失的先決條件，您必須先解決遺失的先決條件，然後再次按一下 [**檢查必備元件**]。</span><span class="sxs-lookup"><span data-stu-id="321f1-131">If a missing prerequisite is detected, you have to resolve the missing prerequisites, and then click **Check prerequisites again**.</span></span> <span data-ttu-id="321f1-132">如果此時間符合所有先決條件，安裝將會繼續。</span><span class="sxs-lookup"><span data-stu-id="321f1-132">If all prerequisites are met this time, the installation will resume.</span></span>



4.  <span data-ttu-id="321f1-133">[MBAM 設定] 嚮導會顯示所選功能的安裝頁面。</span><span class="sxs-lookup"><span data-stu-id="321f1-133">The MBAM Setup wizard will display the installation pages for the selected features.</span></span> <span data-ttu-id="321f1-134">下列各節說明每個功能的安裝程式。</span><span class="sxs-lookup"><span data-stu-id="321f1-134">The following sections describe the installation procedures for each feature.</span></span>

    **<span data-ttu-id="321f1-135">注意</span><span class="sxs-lookup"><span data-stu-id="321f1-135">Note</span></span>**  
    <span data-ttu-id="321f1-136">一般來說，每個功能都安裝在不同的伺服器上。</span><span class="sxs-lookup"><span data-stu-id="321f1-136">Typically, each feature is installed on a separate server.</span></span> <span data-ttu-id="321f1-137">如果您想要在單一伺服器上安裝多項功能，您可以變更或刪除下列部分步驟。</span><span class="sxs-lookup"><span data-stu-id="321f1-137">If you want to install multiple features on a single server, you may change or eliminate some of the following steps.</span></span>



~~~
**To install the Recovery and Hardware Database**

1.  Choose an option for MBAM communication encryption. MBAM can encrypt the communication between the Recovery and Hardware Database and the Administration and Monitoring servers. If you choose the option to encrypt communication, you are asked to select the authority-provisioned certificate that is used for encryption.

2.  Click **Next** to continue.

3.  Specify the names of the computers that will be running the Administration and Monitoring Server feature, to configure access to the Recovery and Hardware Database.. Once the Administration and Monitoring Server feature is deployed, it connects to the database by using its domain account.

4.  Click **Next** to continue.

5.  Specify the **Database Configuration** for the SQL Server instance that stores the recovery and hardware data. You must also specify where the database will be located and where the log information will be located.

6.  Click **Next** to continue with the MBAM Setup wizard.

**To install the Compliance and Audit Database**

1.  Choose an option for the MBAM communication encryption. MBAM can encrypt the communication between the Compliance and Audit Database and the Administration and Monitoring servers. If you choose the option to encrypt communication, you are asked to select the authority-provisioned certificate that will be used for encryption.

2.  Click **Next** to continue.

3.  Specify the user account that will be used to access the database for reports.

4.  Click **Next** to continue.

5.  Specify the computer names of the computers that you want to run the Administration and Monitoring Server and the Compliance and Audit Reports, to configure the access to the Compliance and Audit Database.. After the Administration and Monitoring and the Compliance and Audit Reports Server are deployed, they will connect to the databases by using their domain accounts.

6.  Specify the **Database Configuration** for the SQL Server instance that will store the compliance and audit data. You must also specify where the database will be located and where the log information will be located.

7.  Click **Next** to continue with the MBAM Setup wizard.

**To install the Compliance and Audit Reports**

1.  Specify the remote SQL Server instance. For example, *&lt;ServerName&gt;*,where the Compliance and Audit Database are installed.

2.  Specify the name of the Compliance and Audit Database. By default, the database name is “MBAM Compliance Status”, but you can change the name when you install the Compliance and Audit Database.

3.  Click **Next** to continue.

4.  Select the SQL Server Reporting Services instance where the Compliance and Audit Reports will be installed. Provide the username and password used to access the compliance database.

5.  Click **Next** to continue with the MBAM Setup wizard.

**To install the Administration and Monitoring Server feature**

1.  Choose an option for the MBAM communication encryption. MBAM can encrypt the communication between the Recovery and Hardware Database and the Administration and Monitoring servers. If you choose the option to encrypt communication, you are asked to select the authority-provisioned certificate that is used for encryption.

2.  Click **Next** to continue.

3.  Specify the remote SQL Server instance, For example, *&lt;ServerName&gt;*, where the Compliance and Audit Database are installed.

4.  Specify the name of the Compliance and Audit Database. By default, the database name is MBAM Compliance Status, but, you can change the name when you install the Compliance and Audit Database.

5.  Click **Next** to continue.

6.  Specify the remote SQL Server instance. For example, *&lt;ServerName&gt;*,where the Recovery and Hardware Database are installed.

7.  Specify the name of the Recovery and Hardware Database. By default, the database name is **MBAM Recovery and Hardware**, but you can change the name when you install the Recovery and Hardware Database feature.

8.  Click **Next** to continue.

9.  Specify the URL for the “Home” of the SQL Server Reporting Services (SRS) site. The default Home location of a SQL Server Reporting Services site instance is at:

    http://*&lt;NameofMBAMReportsServer&gt;/*ReportServer

    **Note**  
    If you configured the SQL Server Reporting Services as a named instance, the URL resembles the following:http://*&lt;NameofMBAMReportsServer&gt;*/ReportServer\_*&lt;SRSInstanceName&gt;*



10. Click **Next** to continue.

11. Enter the **Port Number**, the **Host Name** (optional), and the **Installation Path** for the MBAM Administration and Monitoring server

    **Warning**  
    The port number that you specify must be an unused port number on the Administration and Monitoring server, unless you specify a unique host header name.



12. Click **Next** to continue with the MBAM Setup wizard.
~~~

5. 

   <span data-ttu-id="321f1-138">指定是否要使用 Microsoft 更新，協助保護您的電腦安全性，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="321f1-138">Specify whether to use Microsoft Updates to help keep your computer secure, and then click **Next**.</span></span>

6. <span data-ttu-id="321f1-139">當選取的 MBAM 功能資訊完成後，您就可以使用 [設定] 嚮導開始進行 MBAM 安裝了。</span><span class="sxs-lookup"><span data-stu-id="321f1-139">When the selected MBAM feature information is complete, you are ready to start the MBAM installation by using the Setup wizard.</span></span> <span data-ttu-id="321f1-140">如果您必須檢查或變更您的安裝設定，請按一下 [**返回**]，在嚮導中移動。</span><span class="sxs-lookup"><span data-stu-id="321f1-140">Click **Back** to move through the wizard if you have to review or change your installation settings.</span></span> <span data-ttu-id="321f1-141">按一下 [**安裝**] 以開始安裝。</span><span class="sxs-lookup"><span data-stu-id="321f1-141">Click **Install** to begin the installation.</span></span> <span data-ttu-id="321f1-142">按一下 [**取消**] 結束嚮導。</span><span class="sxs-lookup"><span data-stu-id="321f1-142">Click **Cancel** to exit the Wizard.</span></span> <span data-ttu-id="321f1-143">安裝程式會安裝您所選取的 MBAM 功能，並通知您安裝已完成。</span><span class="sxs-lookup"><span data-stu-id="321f1-143">Setup installs the MBAM features that you selected and notifies you that the installation is finished.</span></span>

7. <span data-ttu-id="321f1-144">按一下 **[完成] 結束**嚮導。</span><span class="sxs-lookup"><span data-stu-id="321f1-144">Click **Finish** to exit the wizard.</span></span>

8. <span data-ttu-id="321f1-145">在安裝 MBAM 伺服器功能之後，將使用者新增至適當的 MBAM 角色。</span><span class="sxs-lookup"><span data-stu-id="321f1-145">Add users to appropriate MBAM roles, after the MBAM server features are installed..</span></span> <span data-ttu-id="321f1-146">如需詳細資訊，請參閱[規劃 MBAM 1.0 系統管理員角色](planning-for-mbam-10-administrator-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="321f1-146">For more information, see [Planning for MBAM 1.0 Administrator Roles](planning-for-mbam-10-administrator-roles.md).</span></span>

**<span data-ttu-id="321f1-147">安裝後的設定</span><span class="sxs-lookup"><span data-stu-id="321f1-147">Post-installation configuration</span></span>**

1.  <span data-ttu-id="321f1-148">MBAM 安裝完成後，您必須先新增使用者角色，才能在使用者存取 MBAM 管理網站中的功能。</span><span class="sxs-lookup"><span data-stu-id="321f1-148">After MBAM Setup is finished, you must add user Roles before users can access to features in the MBAM administration website.</span></span> <span data-ttu-id="321f1-149">在 [管理及監視伺服器] 上，將使用者新增至下列本機群組。</span><span class="sxs-lookup"><span data-stu-id="321f1-149">On the Administration and Monitoring Server, add users to the following local groups.</span></span>

    -   <span data-ttu-id="321f1-150">**MBAM 硬體使用者**：此本機群組的成員可以存取 MBAM 管理網站中的硬體功能。</span><span class="sxs-lookup"><span data-stu-id="321f1-150">**MBAM Hardware Users**: Members of this local group can access the Hardware feature in the MBAM administration website.</span></span>

    -   <span data-ttu-id="321f1-151">**MBAM 支援人員**：此本機群組的成員可以存取 MBAM 管理網站中的 [磁碟機復原] 和 [管理受信任的平臺模組（TPM）] 功能。</span><span class="sxs-lookup"><span data-stu-id="321f1-151">**MBAM Helpdesk Users**: Members of this local group can access the Drive Recovery and Manage Trusted Platform Modules (TPM) features in the MBAM administration website.</span></span> <span data-ttu-id="321f1-152">[磁碟機復原] 和 [管理 TPM] 中的所有欄位都是技術支援人員的必要欄位。</span><span class="sxs-lookup"><span data-stu-id="321f1-152">All fields in Drive Recovery and Manage TPM are required fields for a Helpdesk User.</span></span>

    -   <span data-ttu-id="321f1-153">**MBAM 高級支援人員的使用者**：此本機群組的成員可以高級存取磁片磁碟機，並在 MBAM 管理網站中管理 TPM 功能。</span><span class="sxs-lookup"><span data-stu-id="321f1-153">**MBAM Advanced Helpdesk Users**: Members of this local group have advanced access to the Drive Recovery and Manage TPM features in the MBAM administration website.</span></span> <span data-ttu-id="321f1-154">針對高級支援人員的使用者，磁片磁碟機復原只需要 [金鑰識別碼] 欄位。</span><span class="sxs-lookup"><span data-stu-id="321f1-154">For Advanced Helpdesk Users, only the Key ID field is required in Drive Recovery.</span></span> <span data-ttu-id="321f1-155">在 [管理 TPM] 中，只需要 [電腦網域] 欄位和 [電腦名稱稱] 欄位。</span><span class="sxs-lookup"><span data-stu-id="321f1-155">In Manage TPM, only the Computer Domain field and Computer Name field are required.</span></span>

2.  <span data-ttu-id="321f1-156">在 [管理與監控伺服器]、[合規性] 和 [審核] 資料庫，以及駐留合規性和審核報告的伺服器上，將使用者新增至下列當地群組，以授予他們存取 MBAM 管理網站中的 [報告] 功能。</span><span class="sxs-lookup"><span data-stu-id="321f1-156">On the Administration and Monitoring Server, Compliance and Audit Database, and on the server that hosts the Compliance and Audit Reports, add users to the following local group to give them access to the Reports feature in the MBAM administration website.</span></span>

    -   <span data-ttu-id="321f1-157">**MBAM 報表使用者**：此本機群組的成員可以存取 MBAM 管理網站中的報表。</span><span class="sxs-lookup"><span data-stu-id="321f1-157">**MBAM Report Users**: Members of this local group can access the Reports in the MBAM administration website.</span></span>

    **<span data-ttu-id="321f1-158">注意</span><span class="sxs-lookup"><span data-stu-id="321f1-158">Note</span></span>**  
    <span data-ttu-id="321f1-159">**MBAM 報告**的使用者或群組成員資格使用者的本機群組必須在已安裝 MBAM 管理和監控伺服器功能、合規性和審核資料庫以及合規性和審核報告的所有電腦上維持。</span><span class="sxs-lookup"><span data-stu-id="321f1-159">Identical user or group membership of the **MBAM Report Users** local group must be maintained on all computers where the MBAM Administration and Monitoring Server features, Compliance and Audit Database, and the Compliance and Audit Reports are installed.</span></span>



## <span data-ttu-id="321f1-160">驗證 MBAM 伺服器功能安裝</span><span class="sxs-lookup"><span data-stu-id="321f1-160">Validate the MBAM Server feature installation</span></span>


<span data-ttu-id="321f1-161">當 MBAM 伺服器功能安裝完成後，您應該確認安裝已成功設定 MBAM 的所有必要功能。</span><span class="sxs-lookup"><span data-stu-id="321f1-161">When the MBAM Server feature installation is complete, you should validate that the installation has successfully set up all the necessary features for MBAM.</span></span> <span data-ttu-id="321f1-162">使用下列程式來確認 MBAM 服務是否正常運作。</span><span class="sxs-lookup"><span data-stu-id="321f1-162">Use the following procedure to confirm that the MBAM service is functional.</span></span>

**<span data-ttu-id="321f1-163">驗證 MBAM 安裝</span><span class="sxs-lookup"><span data-stu-id="321f1-163">To validate an MBAM installation</span></span>**

1. <span data-ttu-id="321f1-164">在每個已部署 MBAM 功能的伺服器上，開啟 [**控制台**]，按一下 [**程式**]，然後按一下 [**程式和功能**]。</span><span class="sxs-lookup"><span data-stu-id="321f1-164">On each server, where an MBAM feature is deployed, open **Control Panel**, click **Programs**, and then click **Programs and Features**.</span></span> <span data-ttu-id="321f1-165">確認 [**程式和功能**] 清單中出現 [ **Microsoft BitLocker 管理及監視**]。</span><span class="sxs-lookup"><span data-stu-id="321f1-165">Verify that **Microsoft BitLocker Administration and Monitoring** appears in the **Programs and Features** list.</span></span>

   **<span data-ttu-id="321f1-166">注意</span><span class="sxs-lookup"><span data-stu-id="321f1-166">Note</span></span>**  
   <span data-ttu-id="321f1-167">若要驗證 MBAM 安裝，您必須使用在每個伺服器上都有本機電腦管理認證的網域帳戶。</span><span class="sxs-lookup"><span data-stu-id="321f1-167">To validate the MBAM installation, you must use a Domain Account that has local computer administrative credentials on each server.</span></span>



2. <span data-ttu-id="321f1-168">在已安裝復原與硬體資料庫的伺服器上，開啟 SQL Server Management Studio 並確認已安裝**MBAM 復原與硬體**資料庫。</span><span class="sxs-lookup"><span data-stu-id="321f1-168">On the server where the Recovery and Hardware Database is installed, open SQL Server Management Studio and verify that the **MBAM Recovery and Hardware** database is installed.</span></span>

3. <span data-ttu-id="321f1-169">在已安裝合規性和審核資料庫的伺服器上，開啟 SQL Server Management Studio 並確認已安裝**MBAM 合規性狀態**資料庫。</span><span class="sxs-lookup"><span data-stu-id="321f1-169">On the server where the Compliance and Audit Database is installed, open SQL Server Management Studio and verify that the **MBAM Compliance Status** database is installed.</span></span>

4. <span data-ttu-id="321f1-170">在已安裝合規性和審核報告的伺服器上，以系統管理許可權開啟網頁瀏覽器，並流覽至 SQL Server Reporting Services 網站的 "Home"。</span><span class="sxs-lookup"><span data-stu-id="321f1-170">On the server where the Compliance and Audit Reports are installed, open a web browser with administrative privileges and browse to the “Home” of the SQL Server Reporting Services site.</span></span>

   <span data-ttu-id="321f1-171">SQL Server Reporting Services 網站實例的預設首頁位置可以在 HTTP:// <em> &lt; NameofMBAMReportsServer &gt; </em> /Reports.aspx. 中找到</span><span class="sxs-lookup"><span data-stu-id="321f1-171">The default Home location of a SQL Server Reporting Services site instance can be found at http://<em>&lt;NameofMBAMReportsServer&gt;</em>/Reports.aspx.</span></span> <span data-ttu-id="321f1-172">若要尋找實際的 URL，請使用 Reporting Services Configuration Manager 工具，然後選取在安裝期間指定的實例。</span><span class="sxs-lookup"><span data-stu-id="321f1-172">To find the actual URL, use the Reporting Services Configuration Manager tool and select the instances specified during setup.</span></span>

   <span data-ttu-id="321f1-173">確認已列出名為「**馬爾他規範**」的資料夾，且包含五個報表和一個資料來源。</span><span class="sxs-lookup"><span data-stu-id="321f1-173">Confirm that a folder named **Malta Compliance Reports** is listed and that it contains five reports and one data source.</span></span>

   **<span data-ttu-id="321f1-174">注意</span><span class="sxs-lookup"><span data-stu-id="321f1-174">Note</span></span>**  
   <span data-ttu-id="321f1-175">如果 SQL Server Reporting Services 已設定為命名實例，URL 應該會類似下列內容： HTTP：//\* &lt; NameofMBAMReportsServer &gt; */Reports\_* &lt; SRSInstanceName &gt; \*</span><span class="sxs-lookup"><span data-stu-id="321f1-175">If SQL Server Reporting Services was configured as a named instance, the URL should resemble the following:http://*&lt;NameofMBAMReportsServer&gt;*/Reports\_*&lt;SRSInstanceName&gt;*</span></span>



5. <span data-ttu-id="321f1-176">在已安裝 [管理及監視] 功能的伺服器上，執行 [**伺服器管理員**] 並流覽至 [**角色**]，選取 [ **Web 服務器（iis）**]，然後按一下 [**網際網路資訊服務（iis）管理員**]。</span><span class="sxs-lookup"><span data-stu-id="321f1-176">On the server where the Administration and Monitoring feature is installed, run **Server Manager** and browse to **Roles**, select **Web Server (IIS)**, and then click **Internet Information Services (IIS) Manager**.</span></span> <span data-ttu-id="321f1-177">在 **[連線**] 中流覽至 [ \* &lt; computername &gt; \*]，按一下 [**網站**]，然後按一下 [ **Microsoft BitLocker 管理與監視**]。</span><span class="sxs-lookup"><span data-stu-id="321f1-177">In **Connections** browse to *&lt;computername&gt;*, click **Sites**, and click **Microsoft BitLocker Administration and Monitoring**.</span></span> <span data-ttu-id="321f1-178">確認 [ **MBAMAdministrationService**]、[ **MBAMComplianceStatusService**] 和 [ **MBAMRecoveryAndHardwareService** ] 都已列出。</span><span class="sxs-lookup"><span data-stu-id="321f1-178">Verify that **MBAMAdministrationService**, **MBAMComplianceStatusService**, and **MBAMRecoveryAndHardwareService** are listed.</span></span>

6. <span data-ttu-id="321f1-179">在已安裝 [管理及監視] 功能的伺服器上，以系統管理許可權開啟網頁瀏覽器，並流覽至 MBAM 網站中的下列位置，確認他們已順利載入：</span><span class="sxs-lookup"><span data-stu-id="321f1-179">On the server where the Administration and Monitoring feature is installed, open a web browser with administrative privileges and browse to the following locations in the MBAM web site, to verify that they load successfully:</span></span>

   -   <span data-ttu-id="321f1-180">*HTTP:// &lt; computername &gt; /default.aspx*並確認流覽與報告的每個連結</span><span class="sxs-lookup"><span data-stu-id="321f1-180">*http://&lt;computername&gt;/default.aspx* and confirm each of the links for navigation and reports</span></span>

   -   *<span data-ttu-id="321f1-181">HTTP:// &lt; computername &gt; /MBAMAdministrationService/AdministrationService.svc</span><span class="sxs-lookup"><span data-stu-id="321f1-181">http://&lt;computername&gt;/MBAMAdministrationService/AdministrationService.svc</span></span>*

   -   *<span data-ttu-id="321f1-182">HTTP:// &lt; computername &gt; /MBAMComplianceStatusService/StatusReportingService.svc</span><span class="sxs-lookup"><span data-stu-id="321f1-182">http://&lt;computername&gt;/MBAMComplianceStatusService/StatusReportingService.svc</span></span>*

   -   *<span data-ttu-id="321f1-183">HTTP:// &lt; computername &gt; /MBAMRecoveryAndHardwareService/CoreService.svc</span><span class="sxs-lookup"><span data-stu-id="321f1-183">http://&lt;computername&gt;/MBAMRecoveryAndHardwareService/CoreService.svc</span></span>*

   **<span data-ttu-id="321f1-184">注意</span><span class="sxs-lookup"><span data-stu-id="321f1-184">Note</span></span>**  
   <span data-ttu-id="321f1-185">通常，服務會安裝在預設埠80，而不需要網路加密。</span><span class="sxs-lookup"><span data-stu-id="321f1-185">Typically, services are installed on the default port 80 without network encryption.</span></span> <span data-ttu-id="321f1-186">如果服務安裝在不同的埠上，請變更 Url，使其包含適當的埠。</span><span class="sxs-lookup"><span data-stu-id="321f1-186">If the services are installed on a different port, change the URLs to include the appropriate port.</span></span> <span data-ttu-id="321f1-187">例如，HTTP://\* &lt; computername &gt; ： &lt; port &gt; \*/default.aspx 或 HTTP:// <em> &lt; hostheadername &gt; / </em> default .aspx</span><span class="sxs-lookup"><span data-stu-id="321f1-187">For example, http://*&lt;computername&gt;:&lt;port&gt;*/default.aspx or http://<em>&lt;hostheadername&gt;/</em>default.aspx</span></span>

   <span data-ttu-id="321f1-188">如果服務是以網路加密的方式安裝，請將 HTTP://變更為 HTTPs://。</span><span class="sxs-lookup"><span data-stu-id="321f1-188">If the services were installed with network encryption, change http:// to https://.</span></span>



~~~
Verify that each web page loads successfully.
~~~

## <span data-ttu-id="321f1-189">相關主題</span><span class="sxs-lookup"><span data-stu-id="321f1-189">Related topics</span></span>


[<span data-ttu-id="321f1-190">部署 MBAM 1.0 伺服器基礎結構</span><span class="sxs-lookup"><span data-stu-id="321f1-190">Deploying the MBAM 1.0 Server Infrastructure</span></span>](deploying-the-mbam-10-server-infrastructure.md)









