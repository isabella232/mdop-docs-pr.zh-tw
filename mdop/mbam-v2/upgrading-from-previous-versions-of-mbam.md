---
title: 從舊版 MBAM 升級
description: 從舊版 MBAM 升級
author: dansimp
ms.assetid: 73b425cf-9cd9-4ebc-a35e-1b3bf18596ce
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: af45d193a5e8001288e70389ff220cb5d8269918
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810178"
---
# <span data-ttu-id="e28a9-103">從舊版 MBAM 升級</span><span class="sxs-lookup"><span data-stu-id="e28a9-103">Upgrading from Previous Versions of MBAM</span></span>


<span data-ttu-id="e28a9-104">您可以執行下列動作，將 Microsoft BitLocker 管理和監控（MBAM）升級至 MBAM 2.0，包括獨立拓撲或 Configuration Manager 拓撲。</span><span class="sxs-lookup"><span data-stu-id="e28a9-104">You can upgrade Microsoft BitLocker Administration and Monitoring (MBAM) to MBAM2.0, with the Stand-alone topology or Configuration Manager topology, by doing the following:</span></span>

-   <span data-ttu-id="e28a9-105">**手動就地伺服器取代**-若要升級 MBAM 伺服器，請使用 [安裝程式] 或 [控制台] 手動卸載 MBAM，然後安裝 MBAM 2.0 基礎結構。</span><span class="sxs-lookup"><span data-stu-id="e28a9-105">**Manual in-place server replacement** – To upgrade the MBAM Server, manually uninstall MBAM by using either the installer or Control Panel, and then install the MBAM2.0 infrastructure.</span></span> <span data-ttu-id="e28a9-106">您不需要移除資料庫。</span><span class="sxs-lookup"><span data-stu-id="e28a9-106">You do not have to remove the databases.</span></span> <span data-ttu-id="e28a9-107">卸載 MBAM 1.0 伺服器時，會讓 MBAM 資料庫保持不變。</span><span class="sxs-lookup"><span data-stu-id="e28a9-107">Uninstalling the MBAM 1.0 Server leaves the MBAM databases intact.</span></span> <span data-ttu-id="e28a9-108">如果您指定的是 MBAM 1.0 所使用的相同資料庫，MBAM 2.0 安裝會在資料庫中保留 MBAM 1.0 資料，並將資料庫轉換成與 MBAM 2.0 搭配使用。</span><span class="sxs-lookup"><span data-stu-id="e28a9-108">If you specify the same databases that MBAM 1.0 was using, the MBAM2.0 installation retains MBAM 1.0 data in the databases and converts the databases to work with MBAM2.0.</span></span>

-   <span data-ttu-id="e28a9-109">**分散式用戶端升級**-如果您使用的是獨立 MBAM 拓朴，您可以在安裝 MBAM 2.0 伺服器基礎結構之後，逐漸升級 MBAM 用戶端。</span><span class="sxs-lookup"><span data-stu-id="e28a9-109">**Distributed Client Upgrade** - If you are using the Stand-alone MBAM topology, you can upgrade the MBAM Clients gradually after you install the MBAM 2.0 Server infrastructure.</span></span> <span data-ttu-id="e28a9-110">MBAM 2.0 伺服器會偵測現有用戶端的版本，並執行所需的步驟以升級至2.0 用戶端。</span><span class="sxs-lookup"><span data-stu-id="e28a9-110">The MBAM 2.0 Server detects the version of the existing Client and performs the required steps to upgrade to the 2.0 Client.</span></span>

    <span data-ttu-id="e28a9-111">在您升級 MBAM 2.0 伺服器基礎結構之後，MBAM 1.0 用戶端會繼續成功向 MBAM 2.0 伺服器報告，escrowing 復原資料，但合規性將根據 MBAM 1.0 中的原則而定。</span><span class="sxs-lookup"><span data-stu-id="e28a9-111">After you upgrade the MBAM 2.0 Server infrastructure, MBAM 1.0 Clients continue to report to the MBAM 2.0 Server successfully, escrowing recovery data, but compliance will be based on the policies in MBAM 1.0.</span></span> <span data-ttu-id="e28a9-112">您必須將用戶端升級至 MBAM 2.0，讓用戶端電腦能根據 MBAM 2.0 原則精確地報告合規性。</span><span class="sxs-lookup"><span data-stu-id="e28a9-112">You must upgrade clients to MBAM 2.0 to have client computers accurately report compliance against the MBAM 2.0 policies.</span></span> <span data-ttu-id="e28a9-113">您可以將用戶端升級至 MBAM 2.0 用戶端，而不卸載先前的用戶端，用戶端就會開始套用並報告 MBAM 2.0 原則。</span><span class="sxs-lookup"><span data-stu-id="e28a9-113">You can upgrade the clients to the MBAM 2.0 Client without uninstalling the previous client, and the client will start to apply and report MBAM 2.0 policies.</span></span>

    <span data-ttu-id="e28a9-114">如果您是使用 MBAM 與 Configuration Manager，您必須將 MBAM 1.0 用戶端升級至 MBAM 2.0。</span><span class="sxs-lookup"><span data-stu-id="e28a9-114">If you are using MBAM with Configuration Manager, you must upgrade the MBAM 1.0 clients to MBAM 2.0.</span></span>

## <span data-ttu-id="e28a9-115">從雙伺服器架構升級 MBAM</span><span class="sxs-lookup"><span data-stu-id="e28a9-115">Upgrading MBAM from a Two-Server Architecture</span></span>


<span data-ttu-id="e28a9-116">當您使用的是雙伺服器架構時，請使用下列指示從舊版 MBAM 升級，其中一個伺服器會託管 Microsoft SQL Server 元件，而另一個伺服器則是託管網站和服務。</span><span class="sxs-lookup"><span data-stu-id="e28a9-116">Use the following instructions to upgrade from a previous version of MBAM when you are using a two-server architecture, where one server is hosting the Microsoft SQL Server components, and the other server is hosting the websites and services.</span></span>

**<span data-ttu-id="e28a9-117">從雙伺服器架構升級 MBAM</span><span class="sxs-lookup"><span data-stu-id="e28a9-117">To upgrade MBAM from a two-server architecture</span></span>**

1.  <span data-ttu-id="e28a9-118">在具有 SQL Server 功能的伺服器上，選取 [控制台] 中的 [**程式和功能**]，然後卸載**Microsoft BitLocker 管理與監視**。</span><span class="sxs-lookup"><span data-stu-id="e28a9-118">On the server with the SQL Server features, in Control Panel, select **Programs and Features**, and then uninstall **Microsoft BitLocker Administration and Monitoring**.</span></span> <span data-ttu-id="e28a9-119">復原資料庫與合規性與審計資料庫保持不變。</span><span class="sxs-lookup"><span data-stu-id="e28a9-119">The Recovery Database and Compliance and Audit database remain unchanged.</span></span>

2.  <span data-ttu-id="e28a9-120">針對版本 MBAM 2.0 執行**MBAMSetup.exe** ，選擇性地選取 [**客戶經驗改進計畫**]，然後按一下 [**開始**]。</span><span class="sxs-lookup"><span data-stu-id="e28a9-120">Run **MBAMSetup.exe** for version MBAM 2.0, optionally select the **Customer Experience Improvement Program**, and then click **Start**.</span></span>

3.  <span data-ttu-id="e28a9-121">閱讀並接受 Microsoft 軟體授權協定，然後按一下 **[下一步]** 繼續安裝。</span><span class="sxs-lookup"><span data-stu-id="e28a9-121">Read and accept the Microsoft Software License Agreement, and then click **Next** to continue the installation.</span></span>

4.  <span data-ttu-id="e28a9-122">在 [**拓撲選取範圍**] 頁面上，選取**獨立**或**系統中心 Configuration Manager 整合**拓撲，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e28a9-122">On the **Topology Selection** page, select the **Stand-alone** or **System Center Configuration Manager Integration** topology, and then click **Next**.</span></span>

5.  <span data-ttu-id="e28a9-123">在 [**選取要安裝的功能**] 頁面上，清除 [**自助式伺服器**與**管理及監視伺服器**功能]，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e28a9-123">On the **Select features to install** page, clear the **Self-Service Server** and **Administration and Monitoring Server** features, and then click **Next**.</span></span>

6.  <span data-ttu-id="e28a9-124">等待必備檢查完成，然後按 **[下一步**]。</span><span class="sxs-lookup"><span data-stu-id="e28a9-124">Wait for the prerequisite checks to finish, and then click **Next**.</span></span> <span data-ttu-id="e28a9-125">如果偵測到遺失的先決條件，請解決缺少的先決條件，然後再次按一下 [**檢查先決條件**]。</span><span class="sxs-lookup"><span data-stu-id="e28a9-125">If a missing prerequisite is detected, resolve the missing prerequisites, and then click **Check prerequisites again**.</span></span>

7.  <span data-ttu-id="e28a9-126">在 [**提供用來存取 MBAM 資料庫的帳戶**] 頁面上，提供將主控網站和服務之伺服器的電腦名稱稱，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e28a9-126">On the **Provide account used to access the MBAM databases** page, provide the computer name for the server that will host the sites and services, and then click **Next**.</span></span>

8.  <span data-ttu-id="e28a9-127">在 [**設定復原資料庫**] 頁面上，指定 SQL Server 實例名稱和要儲存恢復資料的資料庫名稱。</span><span class="sxs-lookup"><span data-stu-id="e28a9-127">On the **Configure the Recovery database** page, specify the SQL Server instance name and the name of the database that will store the recovery data.</span></span> <span data-ttu-id="e28a9-128">您也必須指定資料庫檔案和記錄資訊的存放位置。</span><span class="sxs-lookup"><span data-stu-id="e28a9-128">You must also specify where the database files and log information will be located.</span></span>

9.  <span data-ttu-id="e28a9-129">按 \[**下一步**\] 繼續。</span><span class="sxs-lookup"><span data-stu-id="e28a9-129">Click **Next** to continue.</span></span>

10. <span data-ttu-id="e28a9-130">在 [**設定合規性和審核資料庫**] 頁面上，指定要儲存合規性與審核資料之資料庫的 SQL Server 實例名稱和名稱。</span><span class="sxs-lookup"><span data-stu-id="e28a9-130">On the **Configure the Compliance and Audit database** page, specify the SQL Server instance name and the name of the database that will store the compliance and audit data.</span></span>

11. <span data-ttu-id="e28a9-131">按 \[**下一步**\] 繼續。</span><span class="sxs-lookup"><span data-stu-id="e28a9-131">Click **Next** to continue.</span></span>

12. <span data-ttu-id="e28a9-132">在 [**設定合規性和審核報告**] 頁面上，指定要安裝合規性和審核報告的 SQL Server Reporting Services 實例，並提供網域使用者帳戶和密碼來存取合規性和審核資料庫。</span><span class="sxs-lookup"><span data-stu-id="e28a9-132">On the **Configure the Compliance and Audit Reports** page, specify the SQL Server Reporting Services instance where the Compliance and Audit reports will be installed, and provide a domain user account and password to access the Compliance and Audit database.</span></span> <span data-ttu-id="e28a9-133">將此帳戶的密碼設定為永不過期。</span><span class="sxs-lookup"><span data-stu-id="e28a9-133">Configure the password for this account to never expire.</span></span> <span data-ttu-id="e28a9-134">使用者帳戶可以存取 [MBAM 報告使用者] 群組中所有可用的資料。</span><span class="sxs-lookup"><span data-stu-id="e28a9-134">The user account can access all data available to the MBAM Reports Users group.</span></span>

13. <span data-ttu-id="e28a9-135">按 \[**下一步**\] 繼續。</span><span class="sxs-lookup"><span data-stu-id="e28a9-135">Click **Next** to continue.</span></span>

14. <span data-ttu-id="e28a9-136">指定是否要使用 Microsoft 更新，協助保護您的電腦安全性，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e28a9-136">Specify whether to use Microsoft Updates to help keep your computer secure, and then click **Next**.</span></span> <span data-ttu-id="e28a9-137">這不會在 Windows 中開啟自動更新。</span><span class="sxs-lookup"><span data-stu-id="e28a9-137">This does not turn on Automatic Updates in Windows.</span></span> <span data-ttu-id="e28a9-138">如果您先前選擇將 Microsoft 更新用於此產品或其他產品，則不會顯示 [Microsoft Update] 頁面。</span><span class="sxs-lookup"><span data-stu-id="e28a9-138">If you previously chose to use Microsoft Update for this product or another product, the Microsoft Update page does not appear.</span></span>

15. <span data-ttu-id="e28a9-139">在 [**安裝摘要**] 頁面上，檢查將要安裝的功能，然後按一下 [**安裝**] 以開始安裝。</span><span class="sxs-lookup"><span data-stu-id="e28a9-139">On the **Installation Summary** page, review the features that will be installed, and then click **Install** to start the installation.</span></span>

**<span data-ttu-id="e28a9-140">若要卸載管理和監視伺服器功能並完成升級</span><span class="sxs-lookup"><span data-stu-id="e28a9-140">To uninstall the Administration and Monitoring Server features and to complete the upgrade</span></span>**

1.  <span data-ttu-id="e28a9-141">在託管 [管理及監視伺服器] 功能的電腦上，選取 [控制台] 中的 [**程式和功能**]，然後 [卸載 MBAM]，移除先前已安裝的網站和服務。</span><span class="sxs-lookup"><span data-stu-id="e28a9-141">On the computer that hosts the Administration and Monitoring Server features, in Control Panel, select **Programs and Features**, and then uninstall MBAM to remove the previously installed websites and services.</span></span>

2.  <span data-ttu-id="e28a9-142">針對版本2.0 執行**MBAMSetup.exe** ，您可以選擇選取 [**客戶經驗改進計畫**]，然後按一下 [**開始**]。</span><span class="sxs-lookup"><span data-stu-id="e28a9-142">Run the **MBAMSetup.exe** for version 2.0, optionally select the **Customer Experience Improvement Program**, and then click **Start**.</span></span>

3.  <span data-ttu-id="e28a9-143">閱讀並接受 Microsoft 軟體授權協定，然後按一下 **[下一步]** 繼續安裝。</span><span class="sxs-lookup"><span data-stu-id="e28a9-143">Read and accept the Microsoft Software License Agreement, and then click **Next** to continue the installation.</span></span>

4.  <span data-ttu-id="e28a9-144">在 [**拓撲選取範圍**] 頁面上，選取**獨立**或**系統中心 Configuration Manager 整合**拓撲，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e28a9-144">On the **Topology Selection** page, select the **Stand-alone** or **System Center Configuration Manager Integration** topology, and then click **Next**.</span></span>

5.  <span data-ttu-id="e28a9-145">在 [**選取要安裝的功能**] 頁面上，清除 [復原**資料庫**與**合規性] 與 [審核資料庫**與**合規性] 與 [審核報告**功能]，然後按 **[下一步]**</span><span class="sxs-lookup"><span data-stu-id="e28a9-145">On the **Select features to install** page, clear the **Recovery Database** and **Compliance and Audit Database** and **Compliance and Audit Reports** features, and then click **Next**.</span></span>

6.  <span data-ttu-id="e28a9-146">等待必備檢查完成，然後按 **[下一步**]。</span><span class="sxs-lookup"><span data-stu-id="e28a9-146">Wait for the prerequisite checks to finish, and then click **Next**.</span></span> <span data-ttu-id="e28a9-147">如果偵測到遺失的先決條件，請先解決缺少的先決條件，然後再次按一下 [**檢查先決條件**]。</span><span class="sxs-lookup"><span data-stu-id="e28a9-147">If a missing prerequisite is detected, resolve the missing prerequisites first, and then click **Check prerequisites again**.</span></span>

7.  <span data-ttu-id="e28a9-148">在 [**設定網路通訊安全性**] 頁面上，選擇是否要針對網站和服務使用安全通訊端層（SSL）加密。</span><span class="sxs-lookup"><span data-stu-id="e28a9-148">On the **Configure network communication security** page, choose whether to use Secure Socket Layer (SSL) encryption for the websites and services.</span></span> <span data-ttu-id="e28a9-149">如果您決定要加密通訊，請選取要用來加密的憑證授權單位（CA）憑證。</span><span class="sxs-lookup"><span data-stu-id="e28a9-149">If you decide to encrypt the communication, select the certification authority (CA) certificate to use for encryption.</span></span>

    <span data-ttu-id="e28a9-150">**記事** 您必須先建立憑證，才能在此頁面上選取。</span><span class="sxs-lookup"><span data-stu-id="e28a9-150">**Note** The certificate must be created before this step to enable you to select it on this page.</span></span>

     

8.  <span data-ttu-id="e28a9-151">在 [**設定合規性狀態資料庫的位置**] 頁面上，指定 SQL Server 實例名稱和儲存合規性和審核資料之資料庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="e28a9-151">On the **Configure the location of the Compliance Status database** page, specify the SQL Server instance name and the name of the database that stores the compliance and audit data.</span></span> <span data-ttu-id="e28a9-152">您也必須指定資料庫檔案和記錄資訊的存放位置。</span><span class="sxs-lookup"><span data-stu-id="e28a9-152">You must also specify where the database files and log information will be located.</span></span>

9.  <span data-ttu-id="e28a9-153">按 \[**下一步**\] 繼續。</span><span class="sxs-lookup"><span data-stu-id="e28a9-153">Click **Next** to continue.</span></span>

10. <span data-ttu-id="e28a9-154">在 [**設定復原資料庫的位置**] 頁面上，指定 SQL Server 實例名稱和儲存復原資料之資料庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="e28a9-154">On the **Configure the location of the Recovery Database** page, specify the SQL Server instance name and the name of the database that stores the recovery data.</span></span>

11. <span data-ttu-id="e28a9-155">按 \[**下一步**\] 繼續。</span><span class="sxs-lookup"><span data-stu-id="e28a9-155">Click **Next** to continue.</span></span>

12. <span data-ttu-id="e28a9-156">在 [**設定合規性和審核報告**] 頁面上，輸入您在其他伺服器上設定的報告實例 URL。</span><span class="sxs-lookup"><span data-stu-id="e28a9-156">On the **Configure the Compliance and Audit Reports** page, enter the URL for the reporting instance that you configured on the other server.</span></span> <span data-ttu-id="e28a9-157">使用 [**測試**] 按鈕確認您可以存取該網站。</span><span class="sxs-lookup"><span data-stu-id="e28a9-157">Use the **Test** button to verify that you can reach the site.</span></span>

13. <span data-ttu-id="e28a9-158">按 \[**下一步**\] 繼續。</span><span class="sxs-lookup"><span data-stu-id="e28a9-158">Click **Next** to continue.</span></span>

14. <span data-ttu-id="e28a9-159">在 [**設定自助入口網站**] 頁面上，輸入自助服務入口網站的埠號碼、主機名稱、虛擬目錄名稱和安裝路徑。</span><span class="sxs-lookup"><span data-stu-id="e28a9-159">On the **Configure the Self-Service Portal** page, enter the port number, host name, virtual directory name, and installation path for the Self-Service Portal.</span></span>

    <span data-ttu-id="e28a9-160">**記事** 除非您指定唯一主機標頭名稱，否則您指定的埠號碼必須是管理和監視伺服器上未使用的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="e28a9-160">**Note** The port number that you specify must be an unused port number on the Administration and Monitoring Server unless you specify a unique host header name.</span></span>

     

15. <span data-ttu-id="e28a9-161">在 [**設定管理與監視伺服器**] 頁面上，指定所需的技術支援網站虛擬目錄。</span><span class="sxs-lookup"><span data-stu-id="e28a9-161">On the **Configure the Administration and Monitoring Server** page, specify the desired virtual directory for the Help Desk website.</span></span>

16. <span data-ttu-id="e28a9-162">指定是否要使用 Microsoft 更新，協助保護您的電腦安全性，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e28a9-162">Specify whether to use Microsoft Updates to help keep your computer secure, and then click **Next**.</span></span> <span data-ttu-id="e28a9-163">這個步驟不會在 Windows 中開啟自動更新。</span><span class="sxs-lookup"><span data-stu-id="e28a9-163">This step does not turn on Automatic Updates in Windows.</span></span> <span data-ttu-id="e28a9-164">如果您先前選擇將 Microsoft 更新用於此產品或其他產品，則不會顯示 [Microsoft Update] 頁面。</span><span class="sxs-lookup"><span data-stu-id="e28a9-164">If you previously chose to use Microsoft Update for this product or another product, the Microsoft Update page does not appear.</span></span>

17. <span data-ttu-id="e28a9-165">在 [**安裝摘要**] 頁面上，檢查將要安裝的功能，然後按一下 [**安裝**] 以開始安裝。</span><span class="sxs-lookup"><span data-stu-id="e28a9-165">On the **Installation Summary** page, review the features that will be installed, and then click **Install** to start the installation.</span></span>

18. <span data-ttu-id="e28a9-166">若要驗證升級是否成功，請確認您可以從網域中的另一部電腦取得每個網站。</span><span class="sxs-lookup"><span data-stu-id="e28a9-166">To validate that the upgrade was successful, verify that you can reach each site from another computer in the domain.</span></span>

## <span data-ttu-id="e28a9-167">在最終使用者電腦上升級 MBAM 用戶端</span><span class="sxs-lookup"><span data-stu-id="e28a9-167">Upgrading the MBAM Client on End-User Computers</span></span>


<span data-ttu-id="e28a9-168">若要將使用者電腦升級至 MBAM 2.0 用戶端，請在每個用戶端電腦上執行**MbamClientSetup.exe** 。</span><span class="sxs-lookup"><span data-stu-id="e28a9-168">To upgrade end-user computers to the MBAM 2.0 Client, run **MbamClientSetup.exe** on each client computer.</span></span> <span data-ttu-id="e28a9-169">安裝程式會自動將用戶端更新至 MBAM 2.0 用戶端。</span><span class="sxs-lookup"><span data-stu-id="e28a9-169">The installer automatically updates the Client to the MBAM 2.0 Client.</span></span> <span data-ttu-id="e28a9-170">您可以透過電子軟體發佈系統（例如 Active Directory 網域服務或 System Center Configuration Manager）來安裝 MBAM 用戶端。</span><span class="sxs-lookup"><span data-stu-id="e28a9-170">You can install the MBAM Client through an electronic software distribution system, tools such as Active Directory Domain Services or System Center Configuration Manager.</span></span>

<span data-ttu-id="e28a9-171">若要驗證用戶端升級，請執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="e28a9-171">To validate the Client upgrade, do the following:</span></span>

1.  <span data-ttu-id="e28a9-172">等到設定的報告週期完成，然後在 SQL Server 電腦上啟動**Sql Server Management Studio** 。</span><span class="sxs-lookup"><span data-stu-id="e28a9-172">Wait until the configured reporting cycle is finished, and then start **SQL Server Management Studio** on the SQL Server computer.</span></span>

2.  <span data-ttu-id="e28a9-173">在 SQL Server 電腦上，啟動**Sql Server Management Studio**。</span><span class="sxs-lookup"><span data-stu-id="e28a9-173">On the SQL Server computer, start **SQL Server Management Studio**.</span></span>

3.  <span data-ttu-id="e28a9-174">確認 [ **RecoveryAndHardwareCore** ] 資料表包含的列顯示使用者的電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="e28a9-174">Verify that the **RecoveryAndHardwareCore.Machines** table contains a row that shows the end-user’s computer name.</span></span>

## <span data-ttu-id="e28a9-175">相關主題</span><span class="sxs-lookup"><span data-stu-id="e28a9-175">Related topics</span></span>


[<span data-ttu-id="e28a9-176">部署 MBAM 2.0</span><span class="sxs-lookup"><span data-stu-id="e28a9-176">Deploying MBAM 2.0</span></span>](deploying-mbam-20-mbam-2.md)

 

 





