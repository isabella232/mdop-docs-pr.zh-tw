---
title: 如何在單一伺服器上安裝及設定 MBAM
description: 如何在單一伺服器上安裝及設定 MBAM
author: dansimp
ms.assetid: 45e6a012-6c8c-4d90-902c-d09de9a0cbea
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 53e170f421bdce8dd6f771af3902af627a15a085
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810334"
---
# <span data-ttu-id="34afa-103">如何在單一伺服器上安裝及設定 MBAM</span><span class="sxs-lookup"><span data-stu-id="34afa-103">How to Install and Configure MBAM on a Single Server</span></span>


<span data-ttu-id="34afa-104">本主題中的程式說明如何在單一伺服器上的獨立拓撲中安裝 Microsoft BitLocker 管理和監控（MBAM）。</span><span class="sxs-lookup"><span data-stu-id="34afa-104">The procedures in this topic describe how to install Microsoft BitLocker Administration and Monitoring (MBAM) in the Stand-alone topology on a single server.</span></span> <span data-ttu-id="34afa-105">只能在測試環境中使用單伺服器設定。</span><span class="sxs-lookup"><span data-stu-id="34afa-105">Use the single-server configuration only in a test environment.</span></span> <span data-ttu-id="34afa-106">在生產環境中，請使用兩個或多個伺服器。</span><span class="sxs-lookup"><span data-stu-id="34afa-106">For production environments, use two or more servers.</span></span> <span data-ttu-id="34afa-107">如果您是使用 Configuration Manager 拓撲來安裝 Microsoft BitLocker 管理和監視，請參閱使用[Configuration Manager 部署 MBAM](deploying-mbam-with-configuration-manager-mbam2.md)。</span><span class="sxs-lookup"><span data-stu-id="34afa-107">If you are installing Microsoft BitLocker Administration and Monitoring by using the Configuration Manager topology, see [Deploying MBAM with Configuration Manager](deploying-mbam-with-configuration-manager-mbam2.md).</span></span>

<span data-ttu-id="34afa-108">下圖顯示單一伺服器結構的範例。</span><span class="sxs-lookup"><span data-stu-id="34afa-108">The following diagram shows an example of a single-server architecture.</span></span> <span data-ttu-id="34afa-109">如需資料庫與功能的描述，請參閱[MBAM 2.0 的高層架構](high-level-architecture-for-mbam-20-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="34afa-109">For a description of the databases and features, see [High-Level Architecture for MBAM 2.0](high-level-architecture-for-mbam-20-mbam-2.md).</span></span>

![mbam 2 單伺服器部署拓朴](images/mbam2-1-server.gif)

<span data-ttu-id="34afa-111">每個伺服器功能都有特定的先決條件。</span><span class="sxs-lookup"><span data-stu-id="34afa-111">Each server feature has certain prerequisites.</span></span> <span data-ttu-id="34afa-112">若要確認您已符合系統必備與硬體和軟體需求，請參閱[MBAM 2.0 部署先決條件](mbam-20-deployment-prerequisites-mbam-2.md)和[MBAM 2.0 支援](mbam-20-supported-configurations-mbam-2.md)的設定。</span><span class="sxs-lookup"><span data-stu-id="34afa-112">To verify that you have met the prerequisites and hardware and software requirements, see [MBAM 2.0 Deployment Prerequisites](mbam-20-deployment-prerequisites-mbam-2.md) and [MBAM 2.0 Supported Configurations](mbam-20-supported-configurations-mbam-2.md).</span></span> <span data-ttu-id="34afa-113">此外，某些功能也有一些資訊，必須在安裝過程中提供，才能成功部署該功能。</span><span class="sxs-lookup"><span data-stu-id="34afa-113">In addition, some features also have information that must be provided during the installation process to successfully deploy the feature.</span></span> <span data-ttu-id="34afa-114">您也應該在開始 MBAM 部署之前，先複習[準備 MBAM 2.0 的環境](preparing-your-environment-for-mbam-20-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="34afa-114">You should also review [Preparing your Environment for MBAM 2.0](preparing-your-environment-for-mbam-20-mbam-2.md) before you start MBAM deployment.</span></span>

**<span data-ttu-id="34afa-115">注意</span><span class="sxs-lookup"><span data-stu-id="34afa-115">Note</span></span>**  
<span data-ttu-id="34afa-116">若要取得安裝記錄檔，您必須使用 Msiexec 套件和 **/l** &lt; location &gt; 選項來安裝 MBAM。</span><span class="sxs-lookup"><span data-stu-id="34afa-116">To obtain the setup log files, you have use the Msiexec package and the **/L** &lt;location&gt; option to install MBAM.</span></span> <span data-ttu-id="34afa-117">記錄檔案是在您指定的位置建立。</span><span class="sxs-lookup"><span data-stu-id="34afa-117">Log files are created in the location that you specify.</span></span>

<span data-ttu-id="34afa-118">在安裝 MBAM 的使用者伺服器上，會在% temp% 資料夾中建立額外的設定記錄檔。</span><span class="sxs-lookup"><span data-stu-id="34afa-118">Additional setup log files are created in the %temp% folder on the server of the user who is installing MBAM.</span></span>



## <span data-ttu-id="34afa-119">在單一伺服器上安裝 MBAM Server 功能</span><span class="sxs-lookup"><span data-stu-id="34afa-119">To install MBAM Server features on a single server</span></span>


<span data-ttu-id="34afa-120">下列步驟說明如何安裝一般 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="34afa-120">The following steps describe how to install general MBAM features.</span></span>

**<span data-ttu-id="34afa-121">啟動 MBAM Server 功能安裝</span><span class="sxs-lookup"><span data-stu-id="34afa-121">To start the MBAM Server features installation</span></span>**

1.  <span data-ttu-id="34afa-122">在您要安裝 MBAM 的伺服器上，執行**MBAMSetup.exe** ，啟動 [MBAM 安裝] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="34afa-122">On the server where you want to install MBAM, run **MBAMSetup.exe** to start the MBAM installation wizard.</span></span>

2.  <span data-ttu-id="34afa-123">在 [**歡迎**] 頁面上，選擇性地選取 [**客戶經驗改進計畫**]，然後按一下 [**開始**]。</span><span class="sxs-lookup"><span data-stu-id="34afa-123">On the **Welcome** page, optionally select the **Customer Experience Improvement Program**, and then click **Start**.</span></span>

3.  <span data-ttu-id="34afa-124">閱讀並接受 Microsoft 軟體授權協定，然後按一下 **[下一步]** 繼續安裝。</span><span class="sxs-lookup"><span data-stu-id="34afa-124">Read and accept the Microsoft Software License Agreement, and then click **Next** to continue the installation.</span></span>

4.  <span data-ttu-id="34afa-125">在 [**拓撲選取範圍**] 頁面上，選取**獨立**拓朴，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="34afa-125">On the **Topology Selection** page, select the **Stand-alone** topology, and then click **Next**.</span></span>

5.  <span data-ttu-id="34afa-126">在 [**選取要安裝的功能**] 頁面上，選取您要安裝的功能。</span><span class="sxs-lookup"><span data-stu-id="34afa-126">On the **Select features to install** page, select the features that you want to install.</span></span> <span data-ttu-id="34afa-127">根據預設，所有的 MBAM 功能都已選取 [安裝]。</span><span class="sxs-lookup"><span data-stu-id="34afa-127">By default, all MBAM features are selected for installation.</span></span> <span data-ttu-id="34afa-128">在同一部電腦上安裝的功能，必須同時安裝在一起。</span><span class="sxs-lookup"><span data-stu-id="34afa-128">Features that are to be installed on the same computer must be installed together at the same time.</span></span> <span data-ttu-id="34afa-129">針對您想要安裝到其他位置的任何功能，清除其核取方塊。</span><span class="sxs-lookup"><span data-stu-id="34afa-129">Clear the check boxes for any features that you want to install elsewhere.</span></span> <span data-ttu-id="34afa-130">您必須以下列順序安裝 MBAM 功能：</span><span class="sxs-lookup"><span data-stu-id="34afa-130">You must install MBAM features in the following order:</span></span>

    -   <span data-ttu-id="34afa-131">復原資料庫</span><span class="sxs-lookup"><span data-stu-id="34afa-131">Recovery Database</span></span>

    -   <span data-ttu-id="34afa-132">合規性和審核資料庫</span><span class="sxs-lookup"><span data-stu-id="34afa-132">Compliance and Audit Database</span></span>

    -   <span data-ttu-id="34afa-133">合規性與審計報告</span><span class="sxs-lookup"><span data-stu-id="34afa-133">Compliance and Audit Reports</span></span>

    -   <span data-ttu-id="34afa-134">自助服務伺服器</span><span class="sxs-lookup"><span data-stu-id="34afa-134">Self-Service Server</span></span>

    -   <span data-ttu-id="34afa-135">管理和監控伺服器</span><span class="sxs-lookup"><span data-stu-id="34afa-135">Administration and Monitoring Server</span></span>

    -   <span data-ttu-id="34afa-136">MBAM 群組原則範本</span><span class="sxs-lookup"><span data-stu-id="34afa-136">MBAM Group Policy template</span></span>

    **<span data-ttu-id="34afa-137">注意</span><span class="sxs-lookup"><span data-stu-id="34afa-137">Note</span></span>**  
    <span data-ttu-id="34afa-138">安裝精靈會檢查安裝的先決條件，並顯示遺失的先決條件。</span><span class="sxs-lookup"><span data-stu-id="34afa-138">The installation wizard checks the prerequisites for your installation and displays the prerequisites that are missing.</span></span> <span data-ttu-id="34afa-139">如果符合所有先決條件，安裝會繼續進行。</span><span class="sxs-lookup"><span data-stu-id="34afa-139">If all of the prerequisites are met, the installation continues.</span></span> <span data-ttu-id="34afa-140">如果偵測到遺失的先決條件，您必須先解決遺失的先決條件，然後再次按一下 [**檢查必備元件**]。</span><span class="sxs-lookup"><span data-stu-id="34afa-140">If a missing prerequisite is detected, you have to resolve the missing prerequisites, and then click **Check prerequisites again**.</span></span> <span data-ttu-id="34afa-141">如果此時間符合所有先決條件，安裝就會繼續。</span><span class="sxs-lookup"><span data-stu-id="34afa-141">If all prerequisites are met this time, the installation resumes.</span></span>



6.  <span data-ttu-id="34afa-142">在 [**設定網路通訊安全性**] 頁面上，選擇是否要加密管理與監視伺服器與用戶端的 Web 服務之間的通訊。</span><span class="sxs-lookup"><span data-stu-id="34afa-142">On the **Configure network communication security** page, choose whether to encrypt the communication between the Web Services on the Administration and Monitoring Server and the clients.</span></span> <span data-ttu-id="34afa-143">如果您決定要加密通訊，請選取憑證授權單位預配的憑證以用於加密。</span><span class="sxs-lookup"><span data-stu-id="34afa-143">If you decide to encrypt the communication, select the certification authority-provisioned certificate to use for encryption.</span></span> <span data-ttu-id="34afa-144">您必須先建立憑證，才能在此頁面上選取。</span><span class="sxs-lookup"><span data-stu-id="34afa-144">The certificate must be created prior to this step to enable you to select it on this page.</span></span>

    **<span data-ttu-id="34afa-145">注意</span><span class="sxs-lookup"><span data-stu-id="34afa-145">Note</span></span>**  
    <span data-ttu-id="34afa-146">只有當您在 [**選取要安裝的功能**] 頁面上選取 [自助式入口網站] 或 [管理及監視伺服器] 功能時，才會顯示此頁面。</span><span class="sxs-lookup"><span data-stu-id="34afa-146">This page appears only if you selected the Self-Service Portal or the Administration and Monitoring Server feature on the **Select features to install** page.</span></span>



7.  <span data-ttu-id="34afa-147">按一下 **[下一步**]，然後繼續進行下一組步驟來設定 MBAM 伺服器功能。</span><span class="sxs-lookup"><span data-stu-id="34afa-147">Click **Next**, and then continue to the next set of steps to configure the MBAM Server features.</span></span>

**<span data-ttu-id="34afa-148">設定 MBAM 伺服器功能</span><span class="sxs-lookup"><span data-stu-id="34afa-148">To configure the MBAM Server features</span></span>**

1.  <span data-ttu-id="34afa-149">在 [**設定復原資料庫**] 頁面上，指定 SQL Server 實例名稱和要儲存恢復資料的資料庫名稱。</span><span class="sxs-lookup"><span data-stu-id="34afa-149">On the **Configure the Recovery database** page, specify the SQL Server instance name and the name of the database that will store the recovery data.</span></span> <span data-ttu-id="34afa-150">您也必須指定資料庫檔案所在的位置和記錄資訊所在的位置。</span><span class="sxs-lookup"><span data-stu-id="34afa-150">You must also specify both where the database files will be located and where the log information will be located.</span></span>

2.  <span data-ttu-id="34afa-151">按 \[**下一步**\] 繼續。</span><span class="sxs-lookup"><span data-stu-id="34afa-151">Click **Next** to continue.</span></span>

3.  <span data-ttu-id="34afa-152">在 [**設定合規性和審核資料庫**] 頁面上，指定要儲存合規性與審核資料之資料庫的 SQL Server 實例名稱和名稱。</span><span class="sxs-lookup"><span data-stu-id="34afa-152">On the **Configure the Compliance and Audit database** page, specify the SQL Server instance name and the name of the database that will store the compliance and audit data.</span></span> <span data-ttu-id="34afa-153">您也必須指定資料庫檔案的所在位置及記錄資訊所在的位置。</span><span class="sxs-lookup"><span data-stu-id="34afa-153">You must also specify where the database files will be located and where the log information will be located.</span></span>

4.  <span data-ttu-id="34afa-154">按 \[**下一步**\] 繼續。</span><span class="sxs-lookup"><span data-stu-id="34afa-154">Click **Next** to continue.</span></span>

5.  <span data-ttu-id="34afa-155">在 [**設定合規性和審核報告**] 頁面上，指定要安裝合規性和審核報告的 SQL Server Reporting Services 實例，並提供用於存取合規性和審核資料庫的網域使用者帳戶和密碼。</span><span class="sxs-lookup"><span data-stu-id="34afa-155">On the **Configure the Compliance and Audit Reports** page, specify the SQL Server Reporting Services instance where the Compliance and Audit reports will be installed, and provide a domain user account and password for accessing the Compliance and Audit database.</span></span> <span data-ttu-id="34afa-156">將此帳戶的密碼設定為永不過期。</span><span class="sxs-lookup"><span data-stu-id="34afa-156">Configure the password for this account to never expire.</span></span> <span data-ttu-id="34afa-157">使用者帳戶應該能夠存取 [MBAM 報告使用者] 群組中所有可用的資料。</span><span class="sxs-lookup"><span data-stu-id="34afa-157">The user account should be able to access all data available to the MBAM Reports Users group.</span></span>

6.  <span data-ttu-id="34afa-158">按 \[**下一步**\] 繼續。</span><span class="sxs-lookup"><span data-stu-id="34afa-158">Click **Next** to continue.</span></span>

7.  <span data-ttu-id="34afa-159">在 [**設定自助入口網站**] 頁面上，輸入自助服務入口網站的埠號碼、主機名稱、虛擬目錄名稱和安裝路徑。</span><span class="sxs-lookup"><span data-stu-id="34afa-159">On the **Configure the Self-Service Portal** page, enter the port number, host name, virtual directory name, and installation path for the Self-Service Portal.</span></span>

    **<span data-ttu-id="34afa-160">注意</span><span class="sxs-lookup"><span data-stu-id="34afa-160">Note</span></span>**  
    <span data-ttu-id="34afa-161">除非您指定唯一主機標頭名稱，否則您指定的埠號碼必須是管理和監視伺服器上未使用的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="34afa-161">The port number that you specify must be an unused port number on the Administration and Monitoring Server unless you specify a unique host header name.</span></span> <span data-ttu-id="34afa-162">如果您使用的是 Windows 防火牆，則會自動開啟埠。</span><span class="sxs-lookup"><span data-stu-id="34afa-162">If you are using Windows Firewall, the port will be opened automatically.</span></span>



8.  <span data-ttu-id="34afa-163">按 \[**下一步**\] 繼續。</span><span class="sxs-lookup"><span data-stu-id="34afa-163">Click **Next** to continue.</span></span>

9.  <span data-ttu-id="34afa-164">指定是否要使用 Microsoft 更新，協助保護您的電腦安全性，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="34afa-164">Specify whether to use Microsoft Updates to help keep your computer secure, and then click **Next**.</span></span> <span data-ttu-id="34afa-165">這不會在 Windows 中開啟自動更新。</span><span class="sxs-lookup"><span data-stu-id="34afa-165">This does not turn on Automatic Updates in Windows.</span></span>

10. <span data-ttu-id="34afa-166">在 [**設定管理和監視伺服器**] 頁面上，輸入 [技術支援中心] 網站的埠號碼、主機名稱、虛擬目錄名稱和安裝路徑。</span><span class="sxs-lookup"><span data-stu-id="34afa-166">On the **Configure the Administration and Monitoring Server** page, enter the port number, host name, virtual directory name, and installation path for the Help Desk website.</span></span>

    **<span data-ttu-id="34afa-167">注意</span><span class="sxs-lookup"><span data-stu-id="34afa-167">Note</span></span>**  
    <span data-ttu-id="34afa-168">除非您指定唯一主機標頭名稱，否則您指定的埠號碼必須是管理和監視伺服器上未使用的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="34afa-168">The port number that you specify must be an unused port number on the Administration and Monitoring Server unless you specify a unique host header name.</span></span> <span data-ttu-id="34afa-169">如果您使用的是 Windows 防火牆，則會自動開啟埠。</span><span class="sxs-lookup"><span data-stu-id="34afa-169">If you are using Windows Firewall, the port will be opened automatically.</span></span>



11. <span data-ttu-id="34afa-170">在 [**安裝摘要**] 頁面上，查看將要安裝的功能清單，然後按一下 [**安裝**] 以開始安裝 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="34afa-170">On the **Installation Summary** page, review the list of features that will be installed, and click **Install** to start installing the MBAM features.</span></span> <span data-ttu-id="34afa-171">如果您必須檢查或變更您的安裝設定，請按一下 [**返回**]，回到嚮導中，或按一下 [**取消**] 結束安裝程式。</span><span class="sxs-lookup"><span data-stu-id="34afa-171">Click **Back** to move back through the wizard if you have to review or change your installation settings, or click **Cancel** to exit Setup.</span></span> <span data-ttu-id="34afa-172">安裝程式會安裝 MBAM 功能，並通知您安裝已完成。</span><span class="sxs-lookup"><span data-stu-id="34afa-172">Setup installs the MBAM features and notifies you that the installation is complete.</span></span>

12. <span data-ttu-id="34afa-173">按一下 **[完成] 結束**嚮導。</span><span class="sxs-lookup"><span data-stu-id="34afa-173">Click **Finish** to exit the wizard.</span></span> <span data-ttu-id="34afa-174">安裝 Microsoft BitLocker 管理和監視伺服器功能之後，請繼續閱讀下一節，並完成步驟，以將使用者新增至 Microsoft BitLocker 管理和監視角色。</span><span class="sxs-lookup"><span data-stu-id="34afa-174">After the Microsoft BitLocker Administration and Monitoring Server features have been installed, continue to the next section and complete the steps have to add users to the Microsoft BitLocker Administration and Monitoring roles.</span></span> <span data-ttu-id="34afa-175">如需有關角色的詳細資訊，請參閱[規劃 MBAM 2.0 系統管理員角色](planning-for-mbam-20-administrator-roles-mbam-2.md)。</span><span class="sxs-lookup"><span data-stu-id="34afa-175">For more information about roles, see [Planning for MBAM 2.0 Administrator Roles](planning-for-mbam-20-administrator-roles-mbam-2.md).</span></span>

**<span data-ttu-id="34afa-176">若要執行安裝後設定</span><span class="sxs-lookup"><span data-stu-id="34afa-176">To perform post-installation configuration</span></span>**

1.  <span data-ttu-id="34afa-177">在 [管理及監視伺服器] 上，將使用者新增至下列當地群組，以授予他們存取 MBAM 技術支援中心網站功能的許可權：</span><span class="sxs-lookup"><span data-stu-id="34afa-177">On the Administration and Monitoring Server, add users to the following local groups to give them access to the MBAM Help Desk website features:</span></span>

    -   <span data-ttu-id="34afa-178">**MBAM 支援人員**：此本機群組的成員可以存取 [MBAM 管理及監視] 網站上的 [磁碟機復原] 及 [管理 TPM] 功能。</span><span class="sxs-lookup"><span data-stu-id="34afa-178">**MBAM Helpdesk Users**: Members of this local group can access the Drive Recovery and Manage TPM features on the MBAM Administration and Monitoring website.</span></span> <span data-ttu-id="34afa-179">[磁碟機復原] 和 [管理 TPM] 中的所有欄位都是技術支援人員的必要欄位。</span><span class="sxs-lookup"><span data-stu-id="34afa-179">All fields in Drive Recovery and Manage TPM are required fields for a Helpdesk User.</span></span>

    -   <span data-ttu-id="34afa-180">**MBAM 高級支援人員的使用者**：此本機群組的成員可以高級存取磁片磁碟機，並在 [MBAM 管理] 和 [監視] 網站上管理 TPM 功能。</span><span class="sxs-lookup"><span data-stu-id="34afa-180">**MBAM Advanced Helpdesk Users**: Members of this local group have advanced access to the Drive Recovery and Manage TPM features on the MBAM Administration and Monitoring website.</span></span> <span data-ttu-id="34afa-181">針對高級支援人員的使用者，磁片磁碟機復原只需要 [**金鑰識別碼**] 欄位。</span><span class="sxs-lookup"><span data-stu-id="34afa-181">For Advanced Helpdesk Users, only the **Key ID** field is required in Drive Recovery.</span></span> <span data-ttu-id="34afa-182">在 [管理 TPM] 中，只需要 [**電腦網域**] 欄位和 [**電腦名稱稱**] 欄位。</span><span class="sxs-lookup"><span data-stu-id="34afa-182">In Manage TPM, only the **Computer Domain** field and **Computer Name** field are required.</span></span>

2.  <span data-ttu-id="34afa-183">在 [管理及監視伺服器] 上，將使用者新增至下列本機群組，讓他們能夠存取 MBAM 管理和監控網站上的 [報告] 功能：</span><span class="sxs-lookup"><span data-stu-id="34afa-183">On the Administration and Monitoring Server, add users to the following local group to enable them to access the Reports feature on the MBAM Administration and Monitoring website:</span></span>

    -   <span data-ttu-id="34afa-184">**MBAM 報表使用者**：此本機群組的成員可以存取 MBAM 管理和監控網站上的 [報表] 功能。</span><span class="sxs-lookup"><span data-stu-id="34afa-184">**MBAM Report Users**: Members of this local group can access the Reports features on the MBAM Administration and Monitoring website.</span></span>

    -   <span data-ttu-id="34afa-185">使用您的公司名稱、注意事項文字及其他公司特定資訊，為自助服務入口網站加上品牌。</span><span class="sxs-lookup"><span data-stu-id="34afa-185">Brand the Self-Service Portal with your company name, notice text, and other company-specific information.</span></span> <span data-ttu-id="34afa-186">如需相關指示，請參閱[如何為自助服務入口網站打造品牌](how-to-brand-the-self-service-portal.md)。</span><span class="sxs-lookup"><span data-stu-id="34afa-186">For instructions, see [How to Brand the Self-Service Portal](how-to-brand-the-self-service-portal.md).</span></span>

    **<span data-ttu-id="34afa-187">注意</span><span class="sxs-lookup"><span data-stu-id="34afa-187">Note</span></span>**  
    <span data-ttu-id="34afa-188">**MBAM 報告**的使用者或群組成員資格使用者的本機群組必須在已安裝 MBAM 管理和監控伺服器功能、合規性和審核資料庫以及合規性和審核報告的所有電腦上維持。</span><span class="sxs-lookup"><span data-stu-id="34afa-188">Identical user or group membership of the **MBAM Report Users** local group must be maintained on all computers where the MBAM Administration and Monitoring Server features, Compliance and Audit Database, and Compliance and Audit Reports are installed.</span></span> <span data-ttu-id="34afa-189">建議的做法是建立網域安全性群組，並將該網域群組新增至每個當地 MBAM 的 [使用者] 群組。</span><span class="sxs-lookup"><span data-stu-id="34afa-189">The recommended way to do this is to create a domain security group and add that domain group to each local MBAM Report Users group.</span></span> <span data-ttu-id="34afa-190">當您使用這個程式時，請依網域群組的方式管理群組成員資格。</span><span class="sxs-lookup"><span data-stu-id="34afa-190">When you use this process, manage the group memberships by way of the domain group.</span></span>



## <span data-ttu-id="34afa-191">驗證 MBAM Server 功能安裝</span><span class="sxs-lookup"><span data-stu-id="34afa-191">Validating the MBAM Server feature installation</span></span>


<span data-ttu-id="34afa-192">當 Microsoft BitLocker 管理和監視安裝完成後，請確認安裝已成功設定 BitLocker 管理所需的所有必要 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="34afa-192">When the Microsoft BitLocker Administration and Monitoring installation is completed, validate that the installation has successfully set up all the necessary MBAM features that are required for BitLocker management.</span></span> <span data-ttu-id="34afa-193">使用下列程式來確認 MBAM 服務是否正常運作。</span><span class="sxs-lookup"><span data-stu-id="34afa-193">Use the following procedure to confirm that the MBAM service is functional.</span></span>

**<span data-ttu-id="34afa-194">驗證 MBAM 伺服器功能安裝</span><span class="sxs-lookup"><span data-stu-id="34afa-194">To validate the MBAM Server feature installation</span></span>**

1. <span data-ttu-id="34afa-195">在部署 MBAM 功能的每個伺服器上，開啟 [**控制台**]。</span><span class="sxs-lookup"><span data-stu-id="34afa-195">On each server where a MBAM feature is deployed, open **Control Panel**.</span></span> <span data-ttu-id="34afa-196">選取 [**程式**]，然後選取 [**程式和功能**]。</span><span class="sxs-lookup"><span data-stu-id="34afa-196">Select **Programs**, and then select **Programs and Features**.</span></span> <span data-ttu-id="34afa-197">確認 [**程式和功能**] 清單中出現 [ **Microsoft BitLocker 管理及監視**]。</span><span class="sxs-lookup"><span data-stu-id="34afa-197">Verify that **Microsoft BitLocker Administration and Monitoring** appears in the **Programs and Features** list.</span></span>

   **<span data-ttu-id="34afa-198">注意</span><span class="sxs-lookup"><span data-stu-id="34afa-198">Note</span></span>**  
   <span data-ttu-id="34afa-199">若要驗證安裝，您必須使用在每個伺服器上都有本機電腦管理認證的網域帳戶。</span><span class="sxs-lookup"><span data-stu-id="34afa-199">To validate the installation, you must use a domain account that has local computer administrative credentials on each server.</span></span>



2. <span data-ttu-id="34afa-200">在安裝了復原資料庫的伺服器上，開啟 [SQL Server Management Studio]，然後確認已安裝**MBAM 復原與硬體**資料庫。</span><span class="sxs-lookup"><span data-stu-id="34afa-200">On the server where the Recovery Database is installed, open SQL Server Management Studio, and verify that the **MBAM Recovery and Hardware** database is installed.</span></span>

3. <span data-ttu-id="34afa-201">在已安裝合規性和審核資料庫的伺服器上，開啟 SQL Server Management Studio，並確認已安裝**MBAM 合規性狀態資料庫**。</span><span class="sxs-lookup"><span data-stu-id="34afa-201">On the server where the Compliance and Audit Database is installed, open SQL Server Management Studio, and verify that the **MBAM Compliance Status Database** is installed.</span></span>

4. <span data-ttu-id="34afa-202">在已安裝合規性和審核報告的伺服器上，使用系統管理認證開啟網頁瀏覽器，然後流覽至 SQL Server Reporting Services 網站的 "Home"。</span><span class="sxs-lookup"><span data-stu-id="34afa-202">On the server where the Compliance and Audit Reports are installed, open a web browser with administrative credentials and browse to the “Home” of the SQL Server Reporting Services site.</span></span>

   <span data-ttu-id="34afa-203">SQL Server Reporting Services 網站實例的預設首頁位置是 HTTP:// <em> &lt; NameofMBAMReportsServer &gt; </em> /Reports。</span><span class="sxs-lookup"><span data-stu-id="34afa-203">The default Home location of a SQL Server Reporting Services site instance is at http://<em>&lt;NameofMBAMReportsServer&gt;</em>/Reports.</span></span> <span data-ttu-id="34afa-204">若要尋找實際的 URL，請使用 Reporting Services Configuration Manager 工具，然後選取在安裝期間指定的實例。</span><span class="sxs-lookup"><span data-stu-id="34afa-204">To find the actual URL, use the Reporting Services Configuration Manager tool and select the instances that are specified during setup.</span></span>

   <span data-ttu-id="34afa-205">確認名為 Microsoft BitLocker 管理和監視的報表資料夾包含名為**MaltaDataSource**的資料來源，且**en-us**資料夾包含四個報表。</span><span class="sxs-lookup"><span data-stu-id="34afa-205">Confirm that a Reports folder named Microsoft BitLocker Administration and Monitoring contains a data source called **MaltaDataSource** and that an **en-us** folder contains four reports.</span></span>

   **<span data-ttu-id="34afa-206">注意</span><span class="sxs-lookup"><span data-stu-id="34afa-206">Note</span></span>**  
   <span data-ttu-id="34afa-207">如果 SQL Server Reporting Services 已設定為命名實例，URL 應該會類似下列： HTTP://\* &lt; NameofMBAMReportsServer &gt; */Reports\_* &lt; SRSInstanceName &gt; \*</span><span class="sxs-lookup"><span data-stu-id="34afa-207">If SQL Server Reporting Services was configured as a named instance, the URL should resemble the following: http://*&lt;NameofMBAMReportsServer&gt;*/Reports\_*&lt;SRSInstanceName&gt;*</span></span>



~~~
**Note**  
If SSRS was not configured to use Secure Socket Layer (SSL), the URL for the reports will be set to HTTP instead of HTTPS when you install the MBAM Server. If you then go to the Administration and Monitoring website and select a report, the following message appears: “Only Secure Content is Displayed.” To show the report, click **Show All Content**.
~~~



5. <span data-ttu-id="34afa-208">在已安裝 [管理及監視] 功能的伺服器上，執行 [**伺服器管理員**] 並流覽至 [**角色**]。</span><span class="sxs-lookup"><span data-stu-id="34afa-208">On the server where the Administration and Monitoring feature is installed, run **Server Manager** and browse to **Roles**.</span></span> <span data-ttu-id="34afa-209">選取 **[Web 服務器（iis）**]，然後按一下 [**網際網路資訊服務（iis）管理員]。**</span><span class="sxs-lookup"><span data-stu-id="34afa-209">Select **Web Server (IIS)**, and then click **Internet Information Services (IIS) Manager.**</span></span>

6. <span data-ttu-id="34afa-210">在 [連線] 中 **，** 流覽至 [ \* &lt; 電腦名稱稱 &gt; \*]，選取 [**網站**]，然後選取 [ **Microsoft BitLocker 管理與監視**]。</span><span class="sxs-lookup"><span data-stu-id="34afa-210">In **Connections,** browse to *&lt;computername&gt;*, select **Sites**, and then select **Microsoft BitLocker Administration and Monitoring**.</span></span> <span data-ttu-id="34afa-211">確認 [ **MBAMAdministrationService**]、[ **MBAMUserSupportService**]、[ **MBAMComplianceStatusService**] 和 [ **MBAMRecoveryAndHardwareService** ] 都已列出。</span><span class="sxs-lookup"><span data-stu-id="34afa-211">Verify that **MBAMAdministrationService**, **MBAMUserSupportService**, **MBAMComplianceStatusService**, and **MBAMRecoveryAndHardwareService** are listed.</span></span>

7. <span data-ttu-id="34afa-212">在已安裝 [管理] 和 [監視] 功能及 [自助式入口網站] 的伺服器上，使用系統管理認證開啟網頁瀏覽器，並流覽至下列位置，確認載入成功：</span><span class="sxs-lookup"><span data-stu-id="34afa-212">On the server where the Administration and Monitoring features and Self-Service Portal are installed, open a web browser with administrative credentials and browse to the following locations to verify that they load successfully:</span></span>

   -   <span data-ttu-id="34afa-213">*HTTP:// &lt; hostname &gt; /HelpDesk/default.aspx*並確認流覽和報告的每個連結</span><span class="sxs-lookup"><span data-stu-id="34afa-213">*http://&lt;hostname&gt;/HelpDesk/default.aspx* and confirm each of the links for navigation and reports</span></span>

   -   *<span data-ttu-id="34afa-214">HTTP:// &lt; hostname &gt; /SelfService&gt;/</span><span class="sxs-lookup"><span data-stu-id="34afa-214">http://&lt;hostname&gt;/SelfService&gt;/</span></span>*

   -   *<span data-ttu-id="34afa-215">HTTP:// &lt; computername &gt; /MBAMAdministrationService/AdministrationService.svc</span><span class="sxs-lookup"><span data-stu-id="34afa-215">http://&lt;computername&gt;/MBAMAdministrationService/AdministrationService.svc</span></span>*

   -   *<span data-ttu-id="34afa-216">HTTP:// &lt; hostname &gt; /MBAMUserSupportService/UserSupportService.svc</span><span class="sxs-lookup"><span data-stu-id="34afa-216">http://&lt;hostname&gt;/MBAMUserSupportService/UserSupportService.svc</span></span>*

   -   *<span data-ttu-id="34afa-217">HTTP:// &lt; computername &gt; /MBAMComplianceStatusService/StatusReportingService.svc</span><span class="sxs-lookup"><span data-stu-id="34afa-217">http://&lt;computername&gt;/MBAMComplianceStatusService/StatusReportingService.svc</span></span>*

   -   *<span data-ttu-id="34afa-218">HTTP:// &lt; computername &gt; /MBAMRecoveryAndHardwareService/CoreService.svc</span><span class="sxs-lookup"><span data-stu-id="34afa-218">http://&lt;computername&gt;/MBAMRecoveryAndHardwareService/CoreService.svc</span></span>*

   **<span data-ttu-id="34afa-219">注意</span><span class="sxs-lookup"><span data-stu-id="34afa-219">Note</span></span>**  
   <span data-ttu-id="34afa-220">假設伺服器功能已安裝在預設埠上，而不需要網路加密。</span><span class="sxs-lookup"><span data-stu-id="34afa-220">It is assumed that the server features were installed on the default port without network encryption.</span></span> <span data-ttu-id="34afa-221">如果您已將伺服器功能安裝在不同的埠或虛擬目錄，請將 url 變更為包含適當的埠，例如， *HTTP:// &lt; hostname &gt; ： &lt; port &gt; /HelpDesk/default.asp*x 或*HTTP:// &lt; hostname &gt; ： &lt; port &gt; / &lt; virtualdirectory &gt; /default.aspx*</span><span class="sxs-lookup"><span data-stu-id="34afa-221">If you installed the server features on a different port or virtual directory, change the URLs to include the appropriate port, for example, *http://&lt;hostname&gt;:&lt;port&gt;/HelpDesk/default.asp*x or*http://&lt;hostname&gt;:&lt;port&gt;/&lt;virtualdirectory&gt;/default.aspx*</span></span>

   <span data-ttu-id="34afa-222">如果伺服器功能是使用網路加密來安裝，請將 HTTP://變更為 HTTPs://。</span><span class="sxs-lookup"><span data-stu-id="34afa-222">If the server features were installed with network encryption, change http:// to https://.</span></span>



## <span data-ttu-id="34afa-223">相關主題</span><span class="sxs-lookup"><span data-stu-id="34afa-223">Related topics</span></span>


[<span data-ttu-id="34afa-224">部署 MBAM 2.0 伺服器基礎結構</span><span class="sxs-lookup"><span data-stu-id="34afa-224">Deploying the MBAM 2.0 Server Infrastructure</span></span>](deploying-the-mbam-20-server-infrastructure-mbam-2.md)









