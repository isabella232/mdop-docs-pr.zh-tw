---
title: 如何在單一伺服器上安裝及設定 MBAM
description: 如何在單一伺服器上安裝及設定 MBAM
author: dansimp
ms.assetid: 55841c63-bad9-44e7-b7fd-ea7037febbd7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 225f66493ceafce5461df3fcc6f701e9a2922a5f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810352"
---
# <span data-ttu-id="398e5-103">如何在單一伺服器上安裝及設定 MBAM</span><span class="sxs-lookup"><span data-stu-id="398e5-103">How to Install and Configure MBAM on a Single Server</span></span>


<span data-ttu-id="398e5-104">本主題中的程式說明在單一伺服器上完整安裝 Microsoft BitLocker 管理和監控（MBAM）功能。</span><span class="sxs-lookup"><span data-stu-id="398e5-104">The procedures in this topic describe the full installation of the Microsoft BitLocker Administration and Monitoring (MBAM) features on a single server.</span></span>

<span data-ttu-id="398e5-105">每個伺服器功能都有特定的先決條件。</span><span class="sxs-lookup"><span data-stu-id="398e5-105">Each server feature has certain prerequisites.</span></span> <span data-ttu-id="398e5-106">若要確認您已符合先決條件以及硬體和軟體需求，請參閱[MBAM 1.0 部署先決條件](mbam-10-deployment-prerequisites.md)和[MBAM 1.0 支援](mbam-10-supported-configurations.md)的設定。</span><span class="sxs-lookup"><span data-stu-id="398e5-106">To verify that you have met the prerequisites and the hardware and software requirements, see [MBAM 1.0 Deployment Prerequisites](mbam-10-deployment-prerequisites.md) and [MBAM 1.0 Supported Configurations](mbam-10-supported-configurations.md).</span></span> <span data-ttu-id="398e5-107">此外，某些功能也有一些資訊，必須在安裝過程中提供，才能成功部署該功能。</span><span class="sxs-lookup"><span data-stu-id="398e5-107">In addition, some features also have information that must be provided during the installation process to successfully deploy the feature.</span></span> <span data-ttu-id="398e5-108">您也應該在開始 MBAM 部署之前，先複習[準備 MBAM 1.0 的環境](preparing-your-environment-for-mbam-10.md)。</span><span class="sxs-lookup"><span data-stu-id="398e5-108">You should also review [Preparing your Environment for MBAM 1.0](preparing-your-environment-for-mbam-10.md) before you begin the MBAM deployment.</span></span>

<span data-ttu-id="398e5-109">**記事** 若要取得安裝記錄檔，您必須使用**msiexec**套件和 **/l** &lt; location 選項來安裝 MBAM &gt; 。</span><span class="sxs-lookup"><span data-stu-id="398e5-109">**Note** To obtain the setup log files, you must install MBAM by using the **msiexec** package and the **/l** &lt;location&gt; option.</span></span> <span data-ttu-id="398e5-110">記錄檔案是在您指定的位置建立。</span><span class="sxs-lookup"><span data-stu-id="398e5-110">Log files are created in the location that you specify.</span></span>

<span data-ttu-id="398e5-111">在安裝 MBAM 的使用者的% temp% 資料夾中，會建立其他設定記錄檔。</span><span class="sxs-lookup"><span data-stu-id="398e5-111">Additional setup log files are created in the %temp% folder of the user who is installing MBAM.</span></span>

 

## <span data-ttu-id="398e5-112">在單一伺服器上安裝 MBAM Server 功能</span><span class="sxs-lookup"><span data-stu-id="398e5-112">To install MBAM Server features on a single server</span></span>


<span data-ttu-id="398e5-113">下列步驟說明如何安裝一般 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="398e5-113">The following steps describe how to install general MBAM features.</span></span>

<span data-ttu-id="398e5-114">**記事** 請務必在32位伺服器上使用32位設定，以及在64位伺服器上進行64位設定。</span><span class="sxs-lookup"><span data-stu-id="398e5-114">**Note** Make sure that you use the 32-bit setup on 32-bit servers and the 64-bit setup on 64-bit servers.</span></span>

 

**<span data-ttu-id="398e5-115">若要啟動 MBAM 伺服器功能安裝</span><span class="sxs-lookup"><span data-stu-id="398e5-115">To start MBAM Server features installation</span></span>**

1.  <span data-ttu-id="398e5-116">啟動 MBAM 安裝精靈。</span><span class="sxs-lookup"><span data-stu-id="398e5-116">Start the MBAM installation wizard.</span></span> <span data-ttu-id="398e5-117">按一下 [歡迎] 頁面上的 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="398e5-117">Click **Install** at the Welcome page.</span></span>

2.  <span data-ttu-id="398e5-118">閱讀並接受 Microsoft 軟體授權條款，然後按一下 **[下一步]** 繼續安裝。</span><span class="sxs-lookup"><span data-stu-id="398e5-118">Read and accept the Microsoft Software License Terms, and then click **Next** to continue the installation.</span></span>

3.  <span data-ttu-id="398e5-119">根據預設，所有的 MBAM 功能都已選取 [安裝]。</span><span class="sxs-lookup"><span data-stu-id="398e5-119">By default, all MBAM features are selected for installation.</span></span> <span data-ttu-id="398e5-120">在同一部電腦上安裝的功能，必須同時安裝在一起。</span><span class="sxs-lookup"><span data-stu-id="398e5-120">Features that will be installed on the same computer must be installed together at the same time.</span></span> <span data-ttu-id="398e5-121">清除您想要安裝在其他位置的功能。</span><span class="sxs-lookup"><span data-stu-id="398e5-121">Clear the features that you want to install elsewhere.</span></span> <span data-ttu-id="398e5-122">您必須以下列順序安裝 MBAM 功能：</span><span class="sxs-lookup"><span data-stu-id="398e5-122">You must install the MBAM features in the following order:</span></span>

    -   <span data-ttu-id="398e5-123">恢復與硬體資料庫</span><span class="sxs-lookup"><span data-stu-id="398e5-123">Recovery and Hardware Database</span></span>

    -   <span data-ttu-id="398e5-124">合規性和審核資料庫</span><span class="sxs-lookup"><span data-stu-id="398e5-124">Compliance and Audit Database</span></span>

    -   <span data-ttu-id="398e5-125">合規性審核與報告</span><span class="sxs-lookup"><span data-stu-id="398e5-125">Compliance Audit and Reports</span></span>

    -   <span data-ttu-id="398e5-126">管理和監控伺服器</span><span class="sxs-lookup"><span data-stu-id="398e5-126">Administration and Monitoring Server</span></span>

    -   <span data-ttu-id="398e5-127">MBAM 群組原則範本</span><span class="sxs-lookup"><span data-stu-id="398e5-127">MBAM Group Policy Template</span></span>

    <span data-ttu-id="398e5-128">**記事** 安裝精靈會檢查安裝的先決條件，並顯示遺失的先決條件。</span><span class="sxs-lookup"><span data-stu-id="398e5-128">**Note** The installation wizard checks the prerequisites for your installation and displays the prerequisites that are missing.</span></span> <span data-ttu-id="398e5-129">如果符合所有先決條件，安裝會繼續進行。</span><span class="sxs-lookup"><span data-stu-id="398e5-129">If all the prerequisites are met, the installation continues.</span></span> <span data-ttu-id="398e5-130">如果偵測到遺失的先決條件，您必須先解決遺失的先決條件，然後再次按一下 [**檢查必備元件**]。</span><span class="sxs-lookup"><span data-stu-id="398e5-130">If a missing prerequisite is detected, you must resolve the missing prerequisites, and then click **Check prerequisites again**.</span></span> <span data-ttu-id="398e5-131">在所有先決條件都符合之後，就會繼續安裝。</span><span class="sxs-lookup"><span data-stu-id="398e5-131">After all prerequisites are met, the installation resumes.</span></span>

     

4.  <span data-ttu-id="398e5-132">系統會提示您設定網路通訊安全。</span><span class="sxs-lookup"><span data-stu-id="398e5-132">You are prompted to configure the network communication security.</span></span> <span data-ttu-id="398e5-133">MBAM 可以加密復原與硬體資料庫、管理與監視伺服器以及用戶端之間的通訊。</span><span class="sxs-lookup"><span data-stu-id="398e5-133">MBAM can encrypt the communication between the Recovery and Hardware Database, the Administration and Monitoring Server, and the clients.</span></span> <span data-ttu-id="398e5-134">如果您決定要加密通訊，系統會要求您選取要用來加密的頒發機構預配憑證。</span><span class="sxs-lookup"><span data-stu-id="398e5-134">If you decide to encrypt the communication, you are asked to select the authority-provisioned certificate that will be used for encryption.</span></span>

5.  <span data-ttu-id="398e5-135">按 \[**下一步**\] 繼續。</span><span class="sxs-lookup"><span data-stu-id="398e5-135">Click **Next** to continue.</span></span>

6.  <span data-ttu-id="398e5-136">[MBAM 設定] 嚮導會顯示所選功能的安裝頁面。</span><span class="sxs-lookup"><span data-stu-id="398e5-136">The MBAM Setup wizard will display the installation pages for the selected features.</span></span>

**<span data-ttu-id="398e5-137">部署 MBAM 伺服器功能</span><span class="sxs-lookup"><span data-stu-id="398e5-137">To deploy MBAM Server features</span></span>**

1.  <span data-ttu-id="398e5-138">在 [**設定復原與硬體資料庫**] 視窗中，指定 SQL Server 實例，以及將儲存恢復與硬體資料之資料庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="398e5-138">In the **Configure the Recovery and Hardware database** window, specify the instance of SQL Server and the name of the database that will store the recovery and hardware data.</span></span> <span data-ttu-id="398e5-139">您也必須同時指定資料庫檔案位置和記錄資訊位置。</span><span class="sxs-lookup"><span data-stu-id="398e5-139">You must also specify both the database files location and the log information location.</span></span>

2.  <span data-ttu-id="398e5-140">按 \[**下一步**\] 繼續。</span><span class="sxs-lookup"><span data-stu-id="398e5-140">Click **Next** to continue.</span></span>

3.  <span data-ttu-id="398e5-141">在 [**設定合規性和審核資料庫**] 視窗中，指定 SQL Server 的實例，以及將儲存合規性和審核資料之資料庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="398e5-141">In the **Configure the Compliance and Audit database** window, specify the instance of the SQL Server and the name of the database that will store the compliance and audit data.</span></span> <span data-ttu-id="398e5-142">然後，指定資料庫檔案位置和記錄資訊位置。</span><span class="sxs-lookup"><span data-stu-id="398e5-142">Then, specify the database files location and the log information location.</span></span>

4.  <span data-ttu-id="398e5-143">按 \[**下一步**\] 繼續。</span><span class="sxs-lookup"><span data-stu-id="398e5-143">Click **Next** to continue.</span></span>

5.  <span data-ttu-id="398e5-144">在 [**合規性與審計報告**] 視窗中，指定要使用的報表服務實例，並提供用來存取資料庫的網域使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="398e5-144">In the **Compliance and Audit Reports** window, specify the report service instance that will be used and provide a domain user account for accessing the database.</span></span> <span data-ttu-id="398e5-145">這應該是專為此用途預配的使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="398e5-145">This should be a user account that is provisioned specifically for this use.</span></span> <span data-ttu-id="398e5-146">使用者帳戶應該能夠存取 [MBAM 報告使用者] 群組中所有可用的資料。</span><span class="sxs-lookup"><span data-stu-id="398e5-146">The user account should be able to access all data available to the MBAM Reports Users group.</span></span>

6.  <span data-ttu-id="398e5-147">按 \[**下一步**\] 繼續。</span><span class="sxs-lookup"><span data-stu-id="398e5-147">Click **Next** to continue.</span></span>

7.  <span data-ttu-id="398e5-148">在 [**設定管理及監視伺服器**] 視窗中，輸入**埠**系結、**主機名稱**（選用），以及 MBAM 管理和監視伺服器的**安裝路徑**。</span><span class="sxs-lookup"><span data-stu-id="398e5-148">In the **Configure the Administration and Monitoring Server** window, enter the **Port Binding**, the **Host Name** (optional), and the **Installation Path** for the MBAM Administration and Monitoring server.</span></span>

    <span data-ttu-id="398e5-149">**警告** 您指定的埠號碼必須是系統管理和監視伺服器上未使用的埠號碼（除非已指定唯一的主機標頭名稱）。</span><span class="sxs-lookup"><span data-stu-id="398e5-149">**Warning** The port number that you specify must be an unused port number on the Administration and Monitoring server, unless a unique host header name is specified.</span></span>

     

8.  <span data-ttu-id="398e5-150">按 \[**下一步**\] 繼續。</span><span class="sxs-lookup"><span data-stu-id="398e5-150">Click **Next** to continue.</span></span>

9.  <span data-ttu-id="398e5-151">指定是否要使用 Microsoft 更新，協助保護您的電腦安全性，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="398e5-151">Specify whether to use Microsoft Updates to help keep your computer secure, and then click **Next**.</span></span> <span data-ttu-id="398e5-152">[Microsoft Update] 選項不會開啟 Windows 中的自動更新。</span><span class="sxs-lookup"><span data-stu-id="398e5-152">The Microsoft Updates option does not turn on the Automatic Updates in Windows.</span></span>

10. <span data-ttu-id="398e5-153">當 [安裝精靈] 收集必要的功能資訊之後，就可以開始 MBAM 安裝了。</span><span class="sxs-lookup"><span data-stu-id="398e5-153">When the Setup wizard has collected the necessary feature information, the MBAM installation is ready to start.</span></span> <span data-ttu-id="398e5-154">如果您想要查看或變更您的安裝設定，請按一下 [**返回**]，在嚮導中向後移動。</span><span class="sxs-lookup"><span data-stu-id="398e5-154">Click **Back** to move back through the wizard if you want to review or change your installation settings.</span></span> <span data-ttu-id="398e5-155">按一下 [**安裝**] 以開始安裝。</span><span class="sxs-lookup"><span data-stu-id="398e5-155">Click **Install** to begin the installation.</span></span> <span data-ttu-id="398e5-156">按一下 [**取消**] 結束安裝程式。</span><span class="sxs-lookup"><span data-stu-id="398e5-156">Click **Cancel** to exit Setup.</span></span> <span data-ttu-id="398e5-157">安裝程式會安裝 MBAM 功能，並通知您安裝已完成。</span><span class="sxs-lookup"><span data-stu-id="398e5-157">Setup installs the MBAM features and notifies you that the installation is completed.</span></span>

11. <span data-ttu-id="398e5-158">按一下 **[完成] 結束**嚮導。</span><span class="sxs-lookup"><span data-stu-id="398e5-158">Click **Finish** to exit the wizard.</span></span>

12. <span data-ttu-id="398e5-159">安裝 MBAM server 功能之後，您必須將使用者新增至 MBAM 角色。</span><span class="sxs-lookup"><span data-stu-id="398e5-159">After you install MBAM server features, you must add users to the MBAM roles.</span></span> <span data-ttu-id="398e5-160">如需詳細資訊，請參閱[規劃 MBAM 1.0 系統管理員角色](planning-for-mbam-10-administrator-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="398e5-160">For more information, see [Planning for MBAM 1.0 Administrator Roles](planning-for-mbam-10-administrator-roles.md).</span></span>

**<span data-ttu-id="398e5-161">若要執行安裝後設定</span><span class="sxs-lookup"><span data-stu-id="398e5-161">To perform post installation configuration</span></span>**

1.  <span data-ttu-id="398e5-162">安裝程式完成後，您必須新增使用者角色，以便讓使用者能夠存取 MBAM 管理網站中的功能。</span><span class="sxs-lookup"><span data-stu-id="398e5-162">After Setup is finished, you must add user roles so that you can give users access to features in the MBAM administration website.</span></span> <span data-ttu-id="398e5-163">在 [管理及監視伺服器] 上，將使用者新增至下列本機群組：</span><span class="sxs-lookup"><span data-stu-id="398e5-163">On the Administration and Monitoring Server, add users to the following local groups:</span></span>

    -   <span data-ttu-id="398e5-164">**MBAM 硬體使用者**：此本機群組的成員可以存取 MBAM 管理網站中的硬體功能。</span><span class="sxs-lookup"><span data-stu-id="398e5-164">**MBAM Hardware Users**: Members of this local group can access the Hardware feature in the MBAM administration website.</span></span>

    -   <span data-ttu-id="398e5-165">**MBAM 支援人員**：此本機群組的成員可以存取 MBAM 管理網站中的 [磁碟機復原] 和 [管理 TPM 功能]。</span><span class="sxs-lookup"><span data-stu-id="398e5-165">**MBAM Helpdesk Users**: Members of this local group can access the Drive Recovery and Manage TPM features in the MBAM administration website.</span></span> <span data-ttu-id="398e5-166">[磁碟機復原] 和 [管理 TPM] 中的所有欄位都是技術支援人員的必要欄位。</span><span class="sxs-lookup"><span data-stu-id="398e5-166">All fields in Drive Recovery and Manage TPM are required fields for a Helpdesk User.</span></span>

    -   <span data-ttu-id="398e5-167">**MBAM 高級支援人員的使用者**：此本機群組的成員可以高級存取磁片磁碟機，並在 MBAM 管理網站中管理 TPM 功能。</span><span class="sxs-lookup"><span data-stu-id="398e5-167">**MBAM Advanced Helpdesk Users**: Members of this local group have advanced access to the Drive Recovery and Manage TPM features in the MBAM administration website.</span></span> <span data-ttu-id="398e5-168">針對高級支援人員的使用者，磁片磁碟機復原只需要 [金鑰識別碼] 欄位。</span><span class="sxs-lookup"><span data-stu-id="398e5-168">For Advanced Helpdesk Users, only the Key ID field is required in Drive Recovery.</span></span> <span data-ttu-id="398e5-169">針對管理 TPM 使用者，只需要 [電腦網域] 欄位和 [電腦名稱稱] 欄位。</span><span class="sxs-lookup"><span data-stu-id="398e5-169">For Manage TPM users, only the Computer Domain field and Computer Name field are required.</span></span>

2.  <span data-ttu-id="398e5-170">在 [管理與監控伺服器]、[合規性] 和 [審核] 資料庫，以及駐留合規性和審核報告的電腦上，將使用者新增至下列本機群組，以讓他們能夠存取 MBAM 管理網站中的 [報告] 功能：</span><span class="sxs-lookup"><span data-stu-id="398e5-170">On the Administration and Monitoring Server, Compliance and Audit Database, and on the computer that hosts the Compliance and Audit Reports, add users to the following local group to enable them to access the Reports feature in the MBAM administration website:</span></span>

    -   <span data-ttu-id="398e5-171">**MBAM 報表使用者**：此本機群組的成員可以存取 MBAM 管理網站中的 [報表] 功能。</span><span class="sxs-lookup"><span data-stu-id="398e5-171">**MBAM Report Users**: Members of this local group can access the Reports features in the MBAM administration website.</span></span>

    <span data-ttu-id="398e5-172">**記事** **MBAM 報表**的相同使用者成員資格或群組成員資格：必須在所有電腦上保留管理和監控伺服器功能、合規性和審核資料庫，以及合規性和審核報告。</span><span class="sxs-lookup"><span data-stu-id="398e5-172">**Note** Identical user membership or group membership of the **MBAM Report Users** local group must be maintained on all computers where the Administration and Monitoring Server features, Compliance and Audit Database, and Compliance and Audit Reports are installed.</span></span>

    <span data-ttu-id="398e5-173">若要在所有電腦上維持相同的成員資格，您應該建立一個網域安全性群組，並將該網域群組新增至每個當地 MBAM Report Users 群組。</span><span class="sxs-lookup"><span data-stu-id="398e5-173">To maintain identical memberships on all computers, you should create a domain security group and add that domain group to each local MBAM Report Users group.</span></span> <span data-ttu-id="398e5-174">如此一來，您就可以使用 [網域] 群組來管理群組成員資格。</span><span class="sxs-lookup"><span data-stu-id="398e5-174">When you do this, you can manage the group memberships by using the domain group.</span></span>

     

## <span data-ttu-id="398e5-175">驗證 MBAM Server 功能安裝</span><span class="sxs-lookup"><span data-stu-id="398e5-175">Validating the MBAM Server feature installation</span></span>


<span data-ttu-id="398e5-176">MBAM 安裝完成後，請確認安裝已成功設定 BitLocker 管理所需的所有必要 MBAM 功能。</span><span class="sxs-lookup"><span data-stu-id="398e5-176">When the MBAM installation is complete, validate that the installation has successfully set up all the necessary MBAM features that are required for BitLocker management.</span></span> <span data-ttu-id="398e5-177">使用下列程式來確認 MBAM 服務是否正常運作：</span><span class="sxs-lookup"><span data-stu-id="398e5-177">Use the following procedure to confirm that the MBAM service is functional:</span></span>

**<span data-ttu-id="398e5-178">驗證 MBAM Server 功能安裝</span><span class="sxs-lookup"><span data-stu-id="398e5-178">To validate MBAM Server feature installation</span></span>**

1. <span data-ttu-id="398e5-179">在部署 MBAM 功能的每個伺服器上，開啟 [**控制台**]。</span><span class="sxs-lookup"><span data-stu-id="398e5-179">On each server where an MBAM feature is deployed, open **Control Panel**.</span></span> <span data-ttu-id="398e5-180">按一下 [**程式**]，然後按一下 [**程式和功能**]。</span><span class="sxs-lookup"><span data-stu-id="398e5-180">Click **Programs**, and then click **Programs and Features**.</span></span> <span data-ttu-id="398e5-181">確認 [**程式和功能**] 清單中出現 [ **Microsoft BitLocker 管理及監視**]。</span><span class="sxs-lookup"><span data-stu-id="398e5-181">Verify that **Microsoft BitLocker Administration and Monitoring** appears in the **Programs and Features** list.</span></span>

   **<span data-ttu-id="398e5-182">注意</span><span class="sxs-lookup"><span data-stu-id="398e5-182">Note</span></span>**  
   <span data-ttu-id="398e5-183">若要驗證安裝，您必須使用在每個伺服器上都有本機電腦管理認證的網域帳戶。</span><span class="sxs-lookup"><span data-stu-id="398e5-183">To validate the installation, you must use a Domain Account that has local computer administrative credentials on each server.</span></span>

     

2. <span data-ttu-id="398e5-184">在已安裝復原與硬體資料庫的伺服器上，開啟 SQL Server Management Studio 並確認已安裝**MBAM 復原與硬體**資料庫。</span><span class="sxs-lookup"><span data-stu-id="398e5-184">On the server where the Recovery and Hardware Database is installed, open SQL Server Management Studio and verify that the **MBAM Recovery and Hardware** database is installed.</span></span>

3. <span data-ttu-id="398e5-185">在已安裝合規性和審核資料庫的伺服器上，開啟 SQL Server Management Studio 並確認已安裝**MBAM 合規性和審核資料庫**。</span><span class="sxs-lookup"><span data-stu-id="398e5-185">On the server where the Compliance and Audit Database is installed, open SQL Server Management Studio and verify that the **MBAM Compliance and Audit Database** is installed.</span></span>

4. <span data-ttu-id="398e5-186">在已安裝合規性和審核報告的伺服器上，以系統管理許可權開啟網頁瀏覽器，並流覽至 SQL Server Reporting Services 網站的 "Home"。</span><span class="sxs-lookup"><span data-stu-id="398e5-186">On the server where the Compliance and Audit Reports are installed, open a web browser with administrative privileges and browse to the “Home” of the SQL Server Reporting Services site.</span></span>

   <span data-ttu-id="398e5-187">SQL Server Reporting Services 網站實例的預設首頁位置是 HTTP:// <em> &lt; NameofMBAMReportsServer &gt; </em> /Reports。</span><span class="sxs-lookup"><span data-stu-id="398e5-187">The default Home location of a SQL Server Reporting Services site instance is at http://<em>&lt;NameofMBAMReportsServer&gt;</em>/Reports.</span></span> <span data-ttu-id="398e5-188">若要尋找實際的 URL，請使用 Reporting Services Configuration Manager 工具，然後選取在安裝期間指定的實例。</span><span class="sxs-lookup"><span data-stu-id="398e5-188">To find the actual URL, use the Reporting Services Configuration Manager tool and select the instances specified during setup.</span></span>

   <span data-ttu-id="398e5-189">確認已列出名為「**馬爾他規範**」的資料夾，且包含五個報表和一個資料來源。</span><span class="sxs-lookup"><span data-stu-id="398e5-189">Confirm that a folder named **Malta Compliance Reports** is listed and that it contains five reports and one data source.</span></span>

   **<span data-ttu-id="398e5-190">注意</span><span class="sxs-lookup"><span data-stu-id="398e5-190">Note</span></span>**  
   <span data-ttu-id="398e5-191">如果 SQL Server Reporting Services 已設定為命名實例，URL 應該會類似下列內容： HTTP：//\* &lt; NameofMBAMReportsServer &gt; */Reports\_* &lt; SRSInstanceName &gt; \*</span><span class="sxs-lookup"><span data-stu-id="398e5-191">If SQL Server Reporting Services was configured as a named instance, the URL should resemble the following:http://*&lt;NameofMBAMReportsServer&gt;*/Reports\_*&lt;SRSInstanceName&gt;*</span></span>

     

5. <span data-ttu-id="398e5-192">在已安裝 [管理與監視] 功能的伺服器上，執行 [**伺服器管理員**] 並流覽至 [**角色**]，選取 [ **Web 服務器（iis）**]，然後按一下 [**網際網路資訊服務（iis）管理員**]。</span><span class="sxs-lookup"><span data-stu-id="398e5-192">On the server where the Administration and Monitoring feature is installed, run **Server Manager** and browse to **Roles**, select **Web Server (IIS)**, and click **Internet Information Services (IIS) Manager**</span></span>

6. <span data-ttu-id="398e5-193">在 **[連線] 中，** 流覽至 [ \* &lt; computername &gt; \*]，選取 [**網站**]，然後選取 [ **Microsoft BitLocker 管理與監視**]。</span><span class="sxs-lookup"><span data-stu-id="398e5-193">In **Connections**, browse to *&lt;computername&gt;*, select **Sites**, and select **Microsoft BitLocker Administration and Monitoring**.</span></span> <span data-ttu-id="398e5-194">確認 [ **MBAMAdministrationService**]、[ **MBAMComplianceStatusService**] 和 [ **MBAMRecoveryAndHardwareService** ] 都已列出。</span><span class="sxs-lookup"><span data-stu-id="398e5-194">Verify that **MBAMAdministrationService**, **MBAMComplianceStatusService**, and **MBAMRecoveryAndHardwareService** are listed.</span></span>

7. <span data-ttu-id="398e5-195">在已安裝 [管理及監視] 功能的伺服器上，以系統管理許可權開啟網頁瀏覽器，然後流覽至 MBAM 網站中的下列位置，以驗證它們已順利載入：</span><span class="sxs-lookup"><span data-stu-id="398e5-195">On the server where the Administration and Monitoring feature is installed, open a web browser with administrative privileges, and then browse to the following locations in the MBAM website to verify that they load successfully:</span></span>

   -   <span data-ttu-id="398e5-196">*HTTP:// &lt; computername &gt; /default.aspx*並確認流覽與報告的每個連結</span><span class="sxs-lookup"><span data-stu-id="398e5-196">*http://&lt;computername&gt;/default.aspx* and confirm each of the links for navigation and reports</span></span>

   -   *<span data-ttu-id="398e5-197">HTTP:// &lt; computername &gt; /MBAMAdministrationService/AdministrationService.svc</span><span class="sxs-lookup"><span data-stu-id="398e5-197">http://&lt;computername&gt;/MBAMAdministrationService/AdministrationService.svc</span></span>*

   -   *<span data-ttu-id="398e5-198">HTTP:// &lt; computername &gt; /MBAMComplianceStatusService/StatusReportingService.svc</span><span class="sxs-lookup"><span data-stu-id="398e5-198">http://&lt;computername&gt;/MBAMComplianceStatusService/StatusReportingService.svc</span></span>*

   -   *<span data-ttu-id="398e5-199">HTTP:// &lt; computername &gt; /MBAMRecoveryAndHardwareService/CoreService.svc</span><span class="sxs-lookup"><span data-stu-id="398e5-199">http://&lt;computername&gt;/MBAMRecoveryAndHardwareService/CoreService.svc</span></span>*

   **<span data-ttu-id="398e5-200">注意</span><span class="sxs-lookup"><span data-stu-id="398e5-200">Note</span></span>**  
   <span data-ttu-id="398e5-201">通常，服務會安裝在預設埠80，而不需要網路加密。</span><span class="sxs-lookup"><span data-stu-id="398e5-201">Typically, the services are installed on the default port 80 without network encryption.</span></span> <span data-ttu-id="398e5-202">如果服務安裝在不同的埠上，請變更 Url，使其包含適當的埠。</span><span class="sxs-lookup"><span data-stu-id="398e5-202">If the services are installed on a different port, change the URLs to include the appropriate port.</span></span> <span data-ttu-id="398e5-203">例如，HTTP://\* &lt; computername &gt; ： &lt; port &gt; \*/default.aspx 或 HTTP:// <em> &lt; hostheadername &gt; / </em> default .aspx。</span><span class="sxs-lookup"><span data-stu-id="398e5-203">For example, http://*&lt;computername&gt;:&lt;port&gt;*/default.aspx or http://<em>&lt;hostheadername&gt;/</em>default.aspx.</span></span>

   <span data-ttu-id="398e5-204">如果服務是以網路加密的方式安裝，請將 HTTP://變更為 HTTPs://。</span><span class="sxs-lookup"><span data-stu-id="398e5-204">If the services are installed with network encryption, change http:// to https://.</span></span>

     

## <span data-ttu-id="398e5-205">相關主題</span><span class="sxs-lookup"><span data-stu-id="398e5-205">Related topics</span></span>


[<span data-ttu-id="398e5-206">部署 MBAM 1.0 伺服器基礎結構</span><span class="sxs-lookup"><span data-stu-id="398e5-206">Deploying the MBAM 1.0 Server Infrastructure</span></span>](deploying-the-mbam-10-server-infrastructure.md)

 

 





