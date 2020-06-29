---
title: 以獨立設定進行 MBAM 2.5 部署
description: 說明如何以獨立的設定部署 MBAM 2.5。
author: Deland-Han
ms.reviewer: dcscontentpm
manager: dansimp
ms.author: delhan
ms.sitesec: library
ms.prod: w10
ms.date: 09/16/2019
ms.openlocfilehash: 905eb7a40483a7a7b499d6dced8472331c87b838
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811751"
---
# <span data-ttu-id="d4b73-103">在獨立配置中部署 MBAM 2。5</span><span class="sxs-lookup"><span data-stu-id="d4b73-103">Deploying MBAM 2.5 in a standalone configuration</span></span>

<span data-ttu-id="d4b73-104">本文提供在獨立設定中安裝 Microsoft BitLocker 管理和監控（MBAM）2.5 的逐步指示。</span><span class="sxs-lookup"><span data-stu-id="d4b73-104">This article provides step-by-step instructions for installing Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 in a standalone configuration.</span></span> <span data-ttu-id="d4b73-105">在本指南中，我們將使用雙伺服器設定。</span><span class="sxs-lookup"><span data-stu-id="d4b73-105">In this guide we will use a two-server configuration.</span></span> <span data-ttu-id="d4b73-106">這兩個伺服器的其中一個就是執行 Microsoft SQL Server 2012 的資料庫伺服器。</span><span class="sxs-lookup"><span data-stu-id="d4b73-106">One of the two servers will be a database server running Microsoft SQL Server 2012.</span></span> <span data-ttu-id="d4b73-107">這個伺服器將裝載 MBAM 資料庫與報告。</span><span class="sxs-lookup"><span data-stu-id="d4b73-107">This server will host the MBAM databases and reports.</span></span> <span data-ttu-id="d4b73-108">額外的伺服器將是 Windows Server 2012，它是「管理和監控伺服器」和「自助服務入口網站」。</span><span class="sxs-lookup"><span data-stu-id="d4b73-108">The additional server will be a Windows Server 2012 web server hosting "Administration and Monitoring Server" and "Self-Service Portal."</span></span>

## <span data-ttu-id="d4b73-109">安裝 MBAM 2.5 server 軟體之前的準備步驟</span><span class="sxs-lookup"><span data-stu-id="d4b73-109">Preparation steps before installing MBAM 2.5 server software</span></span>

### <span data-ttu-id="d4b73-110">步驟1：伺服器的安裝與設定</span><span class="sxs-lookup"><span data-stu-id="d4b73-110">Step 1: Installation and configuration of servers</span></span>

<span data-ttu-id="d4b73-111">開始設定 MBAM 2.5 之前，我們必須確定兩個伺服器都設定為每個 MBAM 的系統需求。</span><span class="sxs-lookup"><span data-stu-id="d4b73-111">Before we start configuring MBAM 2.5, we have to make sure that both servers are configured as per MBAM system requirements.</span></span> <span data-ttu-id="d4b73-112">請參閱[MBAM 最低系統需求](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/mbam-25-supported-configurations#-mbam-server-system-requirements)，然後選取符合這些需求的設定。</span><span class="sxs-lookup"><span data-stu-id="d4b73-112">See the [MBAM minimum system requirements](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/mbam-25-supported-configurations#-mbam-server-system-requirements), and select a configuration that meets these requirements.</span></span> 

#### <span data-ttu-id="d4b73-113">步驟1.1：部署資料庫和報表伺服器的先決條件</span><span class="sxs-lookup"><span data-stu-id="d4b73-113">Step 1.1: Deploying prerequisites for database and reporting server</span></span>

1. <span data-ttu-id="d4b73-114">安裝並設定執行 Windows Server 2008 R2 （或更新版本）作業系統的伺服器。</span><span class="sxs-lookup"><span data-stu-id="d4b73-114">Install and configure a server running Windows Server 2008 R2 (or later) operating system.</span></span>

2. <span data-ttu-id="d4b73-115">安裝 Windows PowerShell 3.0。</span><span class="sxs-lookup"><span data-stu-id="d4b73-115">Install Windows PowerShell 3.0.</span></span>

3. <span data-ttu-id="d4b73-116">安裝 Microsoft SQL Server 2008 R2 或更新版本，其中包含最新的 service pack。</span><span class="sxs-lookup"><span data-stu-id="d4b73-116">Install Microsoft SQL Server 2008 R2 or a later version that includes the latest service pack.</span></span> <span data-ttu-id="d4b73-117">如果您要為 MBAM 安裝新的 SQL Server 實例，請確定您安裝的 SQL Server 包含 SQL_Latin1_General_CP1_CI_AS 的排序規則。</span><span class="sxs-lookup"><span data-stu-id="d4b73-117">If you are installing a new instance of SQL Server for MBAM, make sure the SQL Server you install includes the SQL_Latin1_General_CP1_CI_AS collation.</span></span> <span data-ttu-id="d4b73-118">您必須安裝下列 SQL Server 功能：</span><span class="sxs-lookup"><span data-stu-id="d4b73-118">You’ll have to install the following SQL Server features:</span></span>

    * <span data-ttu-id="d4b73-119">資料庫引擎</span><span class="sxs-lookup"><span data-stu-id="d4b73-119">Database Engine</span></span>
    * <span data-ttu-id="d4b73-120">Reporting Services</span><span class="sxs-lookup"><span data-stu-id="d4b73-120">Reporting Services</span></span>
    * <span data-ttu-id="d4b73-121">用戶端工具連線性</span><span class="sxs-lookup"><span data-stu-id="d4b73-121">Client Tools Connectivity</span></span>
    * <span data-ttu-id="d4b73-122">管理工具–完成</span><span class="sxs-lookup"><span data-stu-id="d4b73-122">Management Tools – Complete</span></span>

    > [!Note]
    > <span data-ttu-id="d4b73-123">或者，您也可以[在 SQL Server 中安裝透明資料加密（TDE）功能](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/mbam-25-security-considerations)。</span><span class="sxs-lookup"><span data-stu-id="d4b73-123">Optionally, you can also install the [Transparent Data Encryption (TDE) feature in SQL Server](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/mbam-25-security-considerations).</span></span>

    <span data-ttu-id="d4b73-124">SQL Server Reporting Services 必須安裝並設定為「原生」模式，而不是使用未設定或「SharePoint」模式。</span><span class="sxs-lookup"><span data-stu-id="d4b73-124">SQL Server Reporting Services must be installed and configured in "native" mode and not in unconfigured or "SharePoint" mode.</span></span>

    ![所需的 SQL Server 功能](images/deploying-MBAM-1.png)

4. <span data-ttu-id="d4b73-126">如果您打算針對管理和監控網站使用 SSL，請務必先設定 SQL Server Reporting Services （SSRS），以使用安全通訊端層（SSL）協定，然後再設定管理和監視網站。</span><span class="sxs-lookup"><span data-stu-id="d4b73-126">If you plan to use SSL for the Administration and Monitoring website, make sure that you configure SQL Server Reporting Services (SSRS) to use the Secure Sockets Layer (SSL) protocol before you configure the Administration and Monitoring website.</span></span> <span data-ttu-id="d4b73-127">否則，報告功能將會使用未加密（HTTPS）資料傳輸，而不是加密（HTTPS）。</span><span class="sxs-lookup"><span data-stu-id="d4b73-127">Otherwise, the Reports feature will use unencrypted (HTTP) data transport instead of encrypted (HTTPS).</span></span>

    <span data-ttu-id="d4b73-128">您可以遵循在原生模式報表伺服器上[設定 ssl](https://docs.microsoft.com/sql/reporting-services/security/configure-ssl-connections-on-a-native-mode-report-server?view=sql-server-2017)連線，在報表伺服器上設定 ssl。</span><span class="sxs-lookup"><span data-stu-id="d4b73-128">You can follow [Configure SSL Connections](https://docs.microsoft.com/sql/reporting-services/security/configure-ssl-connections-on-a-native-mode-report-server?view=sql-server-2017) on a Native Mode Report Server to configure SSL on Report Server.</span></span>
    
    > [!Note]
    > <span data-ttu-id="d4b73-129">您可以遵循 SQL server 安裝指南中適用于您的各個版本的 SQL Server 來安裝 SQL Server。</span><span class="sxs-lookup"><span data-stu-id="d4b73-129">You can follow the SQL Server Installation Guide for your respective version of SQL Server to install SQL Server.</span></span> <span data-ttu-id="d4b73-130">連結如下所示：</span><span class="sxs-lookup"><span data-stu-id="d4b73-130">The links are as follows:</span></span>
        > * [<span data-ttu-id="d4b73-131">SQL Server 2014</span><span class="sxs-lookup"><span data-stu-id="d4b73-131">SQL Server 2014</span></span>](https://docs.microsoft.com/sql/sql-server/install/planning-a-sql-server-installation?view=sql-server-2014)
        > * [<span data-ttu-id="d4b73-132">SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="d4b73-132">SQL Server 2012</span></span>](https://docs.microsoft.com/previous-versions/sql/sql-server-2012/bb500442(v=sql.110))
        > * [<span data-ttu-id="d4b73-133">SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="d4b73-133">SQL Server 2008 R2</span></span>](https://docs.microsoft.com/previous-versions/sql/sql-server-2012/bb500442(v=sql.110))

5. <span data-ttu-id="d4b73-134">在 SQL Server 的安裝後，請確認您已在 SQL Server 中提供使用者帳戶，並將下列許可權指派給將在資料庫伺服器上設定 MBAM 資料庫及報告角色的使用者。</span><span class="sxs-lookup"><span data-stu-id="d4b73-134">In the post-installation of SQL Server, make sure that you provision the user account in SQL Server, and assign the following permissions to the user who will configure the MBAM database and reporting roles on the database server.</span></span>

    <span data-ttu-id="d4b73-135">SQL Server 實例的角色：</span><span class="sxs-lookup"><span data-stu-id="d4b73-135">Roles for the instance of SQL Server:</span></span>
        
    * <span data-ttu-id="d4b73-136">dbcreator</span><span class="sxs-lookup"><span data-stu-id="d4b73-136">dbcreator</span></span>
    * <span data-ttu-id="d4b73-137">processadmin</span><span class="sxs-lookup"><span data-stu-id="d4b73-137">processadmin</span></span>

    <span data-ttu-id="d4b73-138">SQL Server Reporting Services 實例的許可權：</span><span class="sxs-lookup"><span data-stu-id="d4b73-138">Rights for the instance of SQL Server Reporting Services:</span></span>
    
    * <span data-ttu-id="d4b73-139">建立資料夾</span><span class="sxs-lookup"><span data-stu-id="d4b73-139">Create Folders</span></span>
    * <span data-ttu-id="d4b73-140">發佈報表</span><span class="sxs-lookup"><span data-stu-id="d4b73-140">Publish Reports</span></span>

<span data-ttu-id="d4b73-141">您的資料庫伺服器已準備好可供您設定 MBAM 2.5 角色。</span><span class="sxs-lookup"><span data-stu-id="d4b73-141">Your database server is ready for configuration of MBAM 2.5 roles.</span></span> <span data-ttu-id="d4b73-142">讓我們移至下一個伺服器。</span><span class="sxs-lookup"><span data-stu-id="d4b73-142">Let’s move to the next server.</span></span>

#### <span data-ttu-id="d4b73-143">步驟1.2：部署管理和監視伺服器的先決條件</span><span class="sxs-lookup"><span data-stu-id="d4b73-143">Step 1.2: Deploying prerequisites for administration and monitoring server</span></span>

<span data-ttu-id="d4b73-144">選擇符合[MBAM 系統需求檔](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/mbam-25-supported-configurations#-mbam-server-system-requirements)中所述之硬體設定的伺服器。</span><span class="sxs-lookup"><span data-stu-id="d4b73-144">Choose a server that meets the hardware configuration as explained in the [MBAM system requirements document](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/mbam-25-supported-configurations#-mbam-server-system-requirements).</span></span> <span data-ttu-id="d4b73-145">它必須執行 Windows Server 2008 R2 或更新版本的作業系統以及最新的 service pack 和更新。</span><span class="sxs-lookup"><span data-stu-id="d4b73-145">It must be running Windows Server 2008 R2 or a later operating system together with latest service pack and updates.</span></span> <span data-ttu-id="d4b73-146">在伺服器就緒之後，請安裝下列角色和功能：</span><span class="sxs-lookup"><span data-stu-id="d4b73-146">After the server is ready, install the following roles and features:</span></span>

##### <span data-ttu-id="d4b73-147">角色</span><span class="sxs-lookup"><span data-stu-id="d4b73-147">Roles</span></span>

* <span data-ttu-id="d4b73-148">Web 服務器（IIS）管理工具（選取 [IIS 管理腳本與工具]）。</span><span class="sxs-lookup"><span data-stu-id="d4b73-148">Web Server (IIS) Management Tools (Select IIS Management Scripts and Tools.)</span></span>

* <span data-ttu-id="d4b73-149">Web 服務器角色服務</span><span class="sxs-lookup"><span data-stu-id="d4b73-149">Web Server Role Services</span></span>

    * <span data-ttu-id="d4b73-150">一般 HTTP 功能</span><span class="sxs-lookup"><span data-stu-id="d4b73-150">Common HTTP features</span></span><br />
      <span data-ttu-id="d4b73-151">靜態內容</span><span class="sxs-lookup"><span data-stu-id="d4b73-151">Static Content</span></span><br />
      <span data-ttu-id="d4b73-152">預設檔</span><span class="sxs-lookup"><span data-stu-id="d4b73-152">Default Document</span></span>

    * <span data-ttu-id="d4b73-153">應用程式開發</span><span class="sxs-lookup"><span data-stu-id="d4b73-153">Application development</span></span><br />
      <span data-ttu-id="d4b73-154">ASP.NET</span><span class="sxs-lookup"><span data-stu-id="d4b73-154">ASP.NET</span></span><br />
      <span data-ttu-id="d4b73-155">.NET 擴充性</span><span class="sxs-lookup"><span data-stu-id="d4b73-155">.NET Extensibility</span></span><br />
      <span data-ttu-id="d4b73-156">ISAPI 延伸</span><span class="sxs-lookup"><span data-stu-id="d4b73-156">ISAPI Extensions</span></span><br />
      <span data-ttu-id="d4b73-157">ISAPI 篩選</span><span class="sxs-lookup"><span data-stu-id="d4b73-157">ISAPI Filters</span></span><br />
      <span data-ttu-id="d4b73-158">安全性</span><span class="sxs-lookup"><span data-stu-id="d4b73-158">Security</span></span><br />
      <span data-ttu-id="d4b73-159">Windows 驗證</span><span class="sxs-lookup"><span data-stu-id="d4b73-159">Windows Authentication</span></span><br />
      <span data-ttu-id="d4b73-160">要求篩選</span><span class="sxs-lookup"><span data-stu-id="d4b73-160">Request Filtering</span></span>

    * <span data-ttu-id="d4b73-161">Web 服務 IIS 管理工具</span><span class="sxs-lookup"><span data-stu-id="d4b73-161">Web Service IIS Management Tools</span></span>

##### <span data-ttu-id="d4b73-162">功能</span><span class="sxs-lookup"><span data-stu-id="d4b73-162">Feature</span></span>

* <span data-ttu-id="d4b73-163">.NET Framework 4.5 功能</span><span class="sxs-lookup"><span data-stu-id="d4b73-163">.NET Framework 4.5 features</span></span>
  
  * <span data-ttu-id="d4b73-164">Microsoft .NET Framework 4。5</span><span class="sxs-lookup"><span data-stu-id="d4b73-164">Microsoft .NET Framework 4.5</span></span>
  
    <span data-ttu-id="d4b73-165">針對 Windows Server 2012 或 Windows Server 2012 R2，已針對這些版本的 Windows Server 安裝 .NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="d4b73-165">For Windows Server 2012 or Windows Server 2012 R2, .NET Framework 4.5 is already installed for these versions of Windows Server.</span></span> <span data-ttu-id="d4b73-166">不過，您必須啟用它。</span><span class="sxs-lookup"><span data-stu-id="d4b73-166">However, you must enable it.</span></span>
  
    <span data-ttu-id="d4b73-167">對於 Windows Server 2008 R2，Windows Server 2008 R2 中不包含 .NET Framework 4.5。</span><span class="sxs-lookup"><span data-stu-id="d4b73-167">For Windows Server 2008 R2, .NET Framework 4.5 is not included with Windows Server 2008 R2.</span></span> <span data-ttu-id="d4b73-168">因此，您必須下載 .NET Framework 4.5 並另行安裝。</span><span class="sxs-lookup"><span data-stu-id="d4b73-168">So, you must download .NET Framework 4.5 and install it separately.</span></span>
  
  * <span data-ttu-id="d4b73-169">WCF 啟用</span><span class="sxs-lookup"><span data-stu-id="d4b73-169">WCF Activation</span></span><br />
    <span data-ttu-id="d4b73-170">HTTP 啟用</span><span class="sxs-lookup"><span data-stu-id="d4b73-170">HTTP Activation</span></span><br />
    <span data-ttu-id="d4b73-171">非 HTTP 啟用</span><span class="sxs-lookup"><span data-stu-id="d4b73-171">Non-HTTP Activation</span></span>
  
  * <span data-ttu-id="d4b73-172">TCP 啟用</span><span class="sxs-lookup"><span data-stu-id="d4b73-172">TCP Activation</span></span>
  
  * <span data-ttu-id="d4b73-173">Windows Process Activation Service：</span><span class="sxs-lookup"><span data-stu-id="d4b73-173">Windows Process Activation Service:</span></span><br />
    <span data-ttu-id="d4b73-174">處理模型</span><span class="sxs-lookup"><span data-stu-id="d4b73-174">Process Model</span></span><br />
    <span data-ttu-id="d4b73-175">.NET Framework 環境</span><span class="sxs-lookup"><span data-stu-id="d4b73-175">.NET Framework Environment</span></span><br />
    <span data-ttu-id="d4b73-176">配置 Api</span><span class="sxs-lookup"><span data-stu-id="d4b73-176">Configuration APIs</span></span>

<span data-ttu-id="d4b73-177">若要讓自助服務入口網站正常運作，您也應該[下載並安裝 ASP.NET MVC 4.0](https://go.microsoft.com/fwlink/?linkid=392271)。</span><span class="sxs-lookup"><span data-stu-id="d4b73-177">For the self-service portal to work, you should also [download and install ASP.NET MVC 4.0](https://go.microsoft.com/fwlink/?linkid=392271).</span></span>

<span data-ttu-id="d4b73-178">下一步是在 Active Directory 中建立所需的 MBAM 使用者和群組。</span><span class="sxs-lookup"><span data-stu-id="d4b73-178">The next step is to create the required MBAM users and groups in Active Directory.</span></span>

### <span data-ttu-id="d4b73-179">步驟2：在 Active Directory 網域服務中建立使用者和群組</span><span class="sxs-lookup"><span data-stu-id="d4b73-179">Step 2: Creating users and groups in Active Directory Domain Services</span></span>
 
<span data-ttu-id="d4b73-180">作為先決條件的一部分，您必須定義在 MBAM 中使用的特定角色和帳戶，以提供特定伺服器與功能的安全性與存取權，例如在 SQL Server 實例上執行的資料庫，以及在管理和監視伺服器上執行的 web 應用程式。</span><span class="sxs-lookup"><span data-stu-id="d4b73-180">As part of the prerequisites, you must define certain roles and accounts that are used in MBAM to provide security and access rights to specific servers and features, such as the databases that are running on the instance of SQL Server and the web applications that are running on the Administration and Monitoring Server.</span></span>

<span data-ttu-id="d4b73-181">在 Active Directory 中建立下列群組和使用者。</span><span class="sxs-lookup"><span data-stu-id="d4b73-181">Create the following groups and users in Active Directory.</span></span> <span data-ttu-id="d4b73-182">（您可以將任何名稱用於群組和使用者。）使用者不需要有更多的使用者權限。</span><span class="sxs-lookup"><span data-stu-id="d4b73-182">(You can use any name for the groups and users.) Users do not have to have greater user rights.</span></span> <span data-ttu-id="d4b73-183">網域使用者帳戶已足夠。</span><span class="sxs-lookup"><span data-stu-id="d4b73-183">A domain user account is sufficient.</span></span> <span data-ttu-id="d4b73-184">在 MBAM 2.5 的設定期間，您必須指定這些群組的名稱：</span><span class="sxs-lookup"><span data-stu-id="d4b73-184">You’ll have to specify the name of these groups during configuration of MBAM 2.5:</span></span>

* **<span data-ttu-id="d4b73-185">MBAMAppPool</span><span class="sxs-lookup"><span data-stu-id="d4b73-185">MBAMAppPool</span></span>**  

  <span data-ttu-id="d4b73-186">**類型**：網域使用者</span><span class="sxs-lookup"><span data-stu-id="d4b73-186">**Type**: Domain User</span></span>

  <span data-ttu-id="d4b73-187">**描述**：對合規性和審核資料庫及復原資料庫擁有讀取或寫入權限的網域使用者，以讓 web 應用程式存取這些資料庫中的資料和報表。</span><span class="sxs-lookup"><span data-stu-id="d4b73-187">**Description**: Domain user who has Read or Write permission to the Compliance and Audit Database and the Recovery Database to enable the web applications to access the data and reports in these databases.</span></span> <span data-ttu-id="d4b73-188">它也會供 web 應用程式的應用程式池使用。</span><span class="sxs-lookup"><span data-stu-id="d4b73-188">It will also be used by the application pool for the web applications.</span></span>

  <span data-ttu-id="d4b73-189">**帳戶角色（在 MBAM 的配置期間）**：</span><span class="sxs-lookup"><span data-stu-id="d4b73-189">**Account Roles (During Configuration of MBAM)**:</span></span>

  1. <span data-ttu-id="d4b73-190">Web 服務應用程式池網域帳戶</span><span class="sxs-lookup"><span data-stu-id="d4b73-190">Web service application pool domain account</span></span>

  2. <span data-ttu-id="d4b73-191">合規性與審計資料庫及復原資料庫已讀/寫使用者的報告</span><span class="sxs-lookup"><span data-stu-id="d4b73-191">Compliance and Audit Database and Recovery Database read/write user for reports</span></span>

* **<span data-ttu-id="d4b73-192">MBAMROUser</span><span class="sxs-lookup"><span data-stu-id="d4b73-192">MBAMROUser</span></span>**

  <span data-ttu-id="d4b73-193">**類型**：網域使用者</span><span class="sxs-lookup"><span data-stu-id="d4b73-193">**Type**: Domain User</span></span>

  <span data-ttu-id="d4b73-194">**描述**：將能以唯讀方式存取合規性和審核資料庫的網域使用者，以讓報告能夠存取此資料庫中的合規性和審核資料。</span><span class="sxs-lookup"><span data-stu-id="d4b73-194">**Description**: Domain user who will have Read-Only access to the Compliance and Audit Database to enable the reports to access the compliance and audit data in this database.</span></span> <span data-ttu-id="d4b73-195">它也會是由本機 SQL Server Reporting Services 實例用來存取合規性和審核資料庫的網域使用者帳戶。</span><span class="sxs-lookup"><span data-stu-id="d4b73-195">It will also be the domain user account that the local SQL Server Reporting Services instance uses to access the Compliance and Audit Database.</span></span>

  <span data-ttu-id="d4b73-196">**帳戶角色（在 MBAM 的配置期間）**：</span><span class="sxs-lookup"><span data-stu-id="d4b73-196">**Account Roles (During Configuration of MBAM)**:</span></span>

  1. <span data-ttu-id="d4b73-197">相容性與審核資料庫唯讀使用者的報表</span><span class="sxs-lookup"><span data-stu-id="d4b73-197">Compliance and Audit Database read-only user for reports</span></span>

  2. <span data-ttu-id="d4b73-198">合規性與審計資料庫網域使用者帳戶</span><span class="sxs-lookup"><span data-stu-id="d4b73-198">Compliance and Audit Database domain user account</span></span>

* **<span data-ttu-id="d4b73-199">MBAMAdvHelpDsk</span><span class="sxs-lookup"><span data-stu-id="d4b73-199">MBAMAdvHelpDsk</span></span>**

  <span data-ttu-id="d4b73-200">**類型**：網域群組</span><span class="sxs-lookup"><span data-stu-id="d4b73-200">**Type**: Domain Group</span></span>

  <span data-ttu-id="d4b73-201">**描述**： MBAM [高級支援人員] 使用者訪問群組：其成員可以存取 [管理] 和 [監視] 網站所有區域的網域使用者群組。</span><span class="sxs-lookup"><span data-stu-id="d4b73-201">**Description**: MBAM Advanced Helpdesk Users access group: Domain user group whose members have access to all areas of the Administration and Monitoring Website.</span></span> <span data-ttu-id="d4b73-202">擁有此角色的使用者在協助使用者復原磁片磁碟機時，只需要輸入復原金鑰，而不是使用者的網域和使用者名稱即可。</span><span class="sxs-lookup"><span data-stu-id="d4b73-202">Users who have this role have to enter only the recovery key, not the user’s domain and user name, when they are helping users recover their drives.</span></span> <span data-ttu-id="d4b73-203">如果使用者是 MBAM [支援人員] 群組和 MBAM [高級服務台使用者] 群組的成員，MBAM [高級支援人員] 群組許可權會覆寫 MBAM [服務台] 群組的許可權。</span><span class="sxs-lookup"><span data-stu-id="d4b73-203">If a user is a member of both the MBAM Helpdesk Users group and the MBAM Advanced Helpdesk Users group, the MBAM Advanced Helpdesk Users group permissions override the MBAM Helpdesk Group permissions.</span></span>

  <span data-ttu-id="d4b73-204">**帳戶角色（在 MBAM 的設定期間）**： MBAM 高級技術支援人員的使用者</span><span class="sxs-lookup"><span data-stu-id="d4b73-204">**Account Roles (During Configuration of MBAM)**: MBAM Advanced Helpdesk Users</span></span>

* **<span data-ttu-id="d4b73-205">MBAMHelpDsk</span><span class="sxs-lookup"><span data-stu-id="d4b73-205">MBAMHelpDsk</span></span>**

  <span data-ttu-id="d4b73-206">**類型**：網域群組</span><span class="sxs-lookup"><span data-stu-id="d4b73-206">**Type**: Domain Group</span></span>

  <span data-ttu-id="d4b73-207">**描述**： MBAM [支援人員] 的 [使用者] 訪問群組：網域使用者群組，其成員可以存取 MBAM 管理和監視網站的 [管理 TPM] 和 [磁片磁碟機] 恢復區域。</span><span class="sxs-lookup"><span data-stu-id="d4b73-207">**Description**: MBAM Helpdesk Users access group: Domain user group whose members have access to the Manage TPM and Drive Recovery areas of the MBAM Administration and Monitoring Website.</span></span> <span data-ttu-id="d4b73-208">擁有此角色的人員在使用任一選項時，都必須填入所有欄位。</span><span class="sxs-lookup"><span data-stu-id="d4b73-208">People who have this role must fill in all fields when they use either option.</span></span> <span data-ttu-id="d4b73-209">這包括使用者的網域和帳戶名稱。</span><span class="sxs-lookup"><span data-stu-id="d4b73-209">This includes the user’s domain and account name.</span></span>

  <span data-ttu-id="d4b73-210">**帳戶角色（在 MBAM 的設定期間）**： MBAM 支援人員的使用者</span><span class="sxs-lookup"><span data-stu-id="d4b73-210">**Account Roles (During Configuration of MBAM)**: MBAM Helpdesk Users</span></span>

* **<span data-ttu-id="d4b73-211">MBAMRUGrp</span><span class="sxs-lookup"><span data-stu-id="d4b73-211">MBAMRUGrp</span></span>**

  <span data-ttu-id="d4b73-212">**類型**：網域群組</span><span class="sxs-lookup"><span data-stu-id="d4b73-212">**Type**: Domain Group</span></span>

  <span data-ttu-id="d4b73-213">**描述**：其成員對 [管理] 和 [監視] 網站上的 [報表] 區域中的報表擁有唯讀存取權的網域使用者群組。</span><span class="sxs-lookup"><span data-stu-id="d4b73-213">**Description**: Domain user group whose members have read-only access to the reports in the Reports area of the Administration and Monitoring Website.</span></span>

  <span data-ttu-id="d4b73-214">**帳戶角色（在 MBAM 的配置期間）**：</span><span class="sxs-lookup"><span data-stu-id="d4b73-214">**Account Roles (During Configuration of MBAM)**:</span></span>

  1. <span data-ttu-id="d4b73-215">報告唯讀網域存取群組</span><span class="sxs-lookup"><span data-stu-id="d4b73-215">Reports read-only domain access group</span></span>

  2. <span data-ttu-id="d4b73-216">MBAM 報表使用者存取群組</span><span class="sxs-lookup"><span data-stu-id="d4b73-216">MBAM Report Users access group</span></span>

### <span data-ttu-id="d4b73-217">步驟3（選用）：在管理與監視伺服器上設定及安裝 SSL 憑證</span><span class="sxs-lookup"><span data-stu-id="d4b73-217">Step 3 (Optional): Configure and install SSL certificate on administration and monitoring server</span></span>

<span data-ttu-id="d4b73-218">雖然它是選擇性的，但我們強烈建議您使用憑證來協助保護 MBAM 用戶端與管理與監控網站及自助服務入口網站之間的通訊。</span><span class="sxs-lookup"><span data-stu-id="d4b73-218">Although it’s optional, we highly recommend that you use a certificate to help secure the communication between the MBAM Client and the Administration and Monitoring Website and the Self-Service Portal websites.</span></span> <span data-ttu-id="d4b73-219">我們不建議您使用自行簽署的憑證，因為這是很明顯的安全性原因。</span><span class="sxs-lookup"><span data-stu-id="d4b73-219">We do not recommend that you use self-signed certificates because of obvious security reasons.</span></span> <span data-ttu-id="d4b73-220">建議您使用來自受信任之憑證授權單位的 Web 服務器類型認證。</span><span class="sxs-lookup"><span data-stu-id="d4b73-220">We suggest that you use a Web Server Type Certificate from a trusted Certification Authority.</span></span> <span data-ttu-id="d4b73-221">若要這樣做，您可以參考[知識庫 2754259](https://support.microsoft.com/help/2754259)中的 [使用由憑證授權單位核准的憑證] 區段。</span><span class="sxs-lookup"><span data-stu-id="d4b73-221">To do this, you can refer the "Using Certificate Approved by Certificate Authority" section from [KB 2754259](https://support.microsoft.com/help/2754259).</span></span>

<span data-ttu-id="d4b73-222">在頒發證書之後，您應該將憑證新增到 [管理和監視伺服器] 的個人存放區。</span><span class="sxs-lookup"><span data-stu-id="d4b73-222">After the certificate is issued, you should add the certificate to the personal store of the Administration and Monitoring Server.</span></span> <span data-ttu-id="d4b73-223">若要新增憑證，請開啟本機電腦上的 [憑證] 存放區。</span><span class="sxs-lookup"><span data-stu-id="d4b73-223">To add the certificate, open the Certificates store on the local computer.</span></span> <span data-ttu-id="d4b73-224">若要這樣做，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="d4b73-224">To do this, follow these steps:</span></span>

1. <span data-ttu-id="d4b73-225">以滑鼠右鍵選取 [開始]，然後選取 [執行]。</span><span class="sxs-lookup"><span data-stu-id="d4b73-225">Right-select Start, and then select Run.</span></span>

   ![<span data-ttu-id="d4b73-226">選取</span><span class="sxs-lookup"><span data-stu-id="d4b73-226">Select</span></span> ](images/deploying-MBAM-2.png)

2. <span data-ttu-id="d4b73-227">輸入 "MMC.EXE" （不加上引號），然後選取 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="d4b73-227">Type "MMC.EXE" (without the quotation marks), and then select **OK**.</span></span>

   ![[執行] 方塊](images/deploying-MBAM-3.png) 

3. <span data-ttu-id="d4b73-229">在您開啟的新 MMC 中選取 [檔案]，**然後選取 [** 新增 **/移除管理單元**]。</span><span class="sxs-lookup"><span data-stu-id="d4b73-229">Select **File** in the new MMC that you opened, and then select **Add/Remove Snap-in**.</span></span>
   
   ![選取](images/deploying-MBAM-4.png)

4. <span data-ttu-id="d4b73-231">醒目提示 [**憑證**] 管理單元，然後選取 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="d4b73-231">Highlight the **Certificates** snap-in, and then select **Add**.</span></span>

   ![[新增或移除管理單元] 視窗](images/deploying-MBAM-5.png)

5. <span data-ttu-id="d4b73-233">選取 [**電腦帳戶**] 選項，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d4b73-233">Select the **Computer account** option, and then select **Next**.</span></span>
   
   ![[憑證] 管理單元視窗](images/deploying-MBAM-6.png)

6. <span data-ttu-id="d4b73-235">選取下一個畫面上的 [**本機電腦**]，然後選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="d4b73-235">Select **Local Computer** on the next screen, and then select **Finish**.</span></span>
   
   ![選取電腦視窗](images/deploying-MBAM-7.png)

7. <span data-ttu-id="d4b73-237">您現在已新增 [憑證] 管理單元。</span><span class="sxs-lookup"><span data-stu-id="d4b73-237">You have now added the Certificates snap-in.</span></span> <span data-ttu-id="d4b73-238">這可讓您使用電腦憑證存放區中的任何憑證。</span><span class="sxs-lookup"><span data-stu-id="d4b73-238">This will enable you to work with any certificates in your computer's certificate store.</span></span>

   ![[新增或移除管理單元] 視窗](images/deploying-MBAM-8.png)

8. <span data-ttu-id="d4b73-240">將 web 伺服器憑證匯入到電腦的憑證存放區。</span><span class="sxs-lookup"><span data-stu-id="d4b73-240">Import the web server certificate into your computer's certificate store.</span></span>

   <span data-ttu-id="d4b73-241">現在您可以存取 [憑證] 管理單元，您可以將 web 伺服器憑證匯入到電腦的憑證存放區。</span><span class="sxs-lookup"><span data-stu-id="d4b73-241">Now that you have access to the Certificates snap-in, you can import the web server certificate into your computer's certificate store.</span></span> <span data-ttu-id="d4b73-242">若要這樣做，請按照後續步驟進行。</span><span class="sxs-lookup"><span data-stu-id="d4b73-242">To do this, follow the next steps.</span></span>

9. <span data-ttu-id="d4b73-243">開啟 [憑證（本機電腦）] 管理單元，然後流覽至 [**個人**]，然後選取 [**憑證**]。</span><span class="sxs-lookup"><span data-stu-id="d4b73-243">Open the Certificates (Local Computer) snap-in, and browse to **Personal** and then **Certificates**.</span></span>
   
   ![[憑證（本機電腦）] 管理單元視窗](images/deploying-MBAM-9.png)

   > [!Note]
   > <span data-ttu-id="d4b73-245">[憑證] 管理單元可能不會列出。</span><span class="sxs-lookup"><span data-stu-id="d4b73-245">The Certificates snap-in may not be listed.</span></span> <span data-ttu-id="d4b73-246">如果不是，則不會安裝任何憑證。</span><span class="sxs-lookup"><span data-stu-id="d4b73-246">If it is not, no certificates are installed.</span></span>

10. <span data-ttu-id="d4b73-247">以滑鼠右鍵選取 [**憑證**]，選取 [**所有任務**]，然後選取 [匯**入**]。</span><span class="sxs-lookup"><span data-stu-id="d4b73-247">Right-select **Certificates**, select **All Tasks**, and then select **Import**.</span></span>

    ![[憑證（本機電腦）] 管理單元視窗](images/deploying-MBAM-10.png)

11. <span data-ttu-id="d4b73-249">嚮導啟動後，選取 **[下一步**]。</span><span class="sxs-lookup"><span data-stu-id="d4b73-249">When the wizard starts, select **Next**.</span></span> <span data-ttu-id="d4b73-250">流覽至您所建立的包含伺服器憑證和私人金鑰的檔案，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d4b73-250">Browse to the file that you created that contains your server certificate and private key, and then select **Next**.</span></span>

    ![[證書匯入] 嚮導視窗](images/deploying-MBAM-11.png)

12. <span data-ttu-id="d4b73-252">如果您在建立檔案時為其指定一個密碼，請輸入密碼。</span><span class="sxs-lookup"><span data-stu-id="d4b73-252">Enter the password if you specified one for the file when you created it.</span></span>

   ![[輸入密碼] 視窗](images/deploying-MBAM-12.png)

   > [!Note]
   > <span data-ttu-id="d4b73-254">如果您想要從這台電腦再次匯出金鑰組，請確定已選取 [將**金鑰標示為可匯出**] 選項。</span><span class="sxs-lookup"><span data-stu-id="d4b73-254">Make sure that the **Mark the key as exportable** option is selected if you want to be able to export the key pair again from this computer.</span></span> <span data-ttu-id="d4b73-255">您可能會想要將這個選項保留為已加上的安全措施，以確保沒有人可以備份您的私人金鑰。</span><span class="sxs-lookup"><span data-stu-id="d4b73-255">As an added security measure, you may want to leave this option cleared to make sure that no one can make a backup of your private key.</span></span>
 
13. <span data-ttu-id="d4b73-256">選取 **[下一步]**，然後選取您要儲存憑證的**憑證存放區**。</span><span class="sxs-lookup"><span data-stu-id="d4b73-256">Select **Next**, and then select the **Certificate Store** to which you want to save the certificate.</span></span>

    ![[證書匯入] 嚮導視窗](images/deploying-MBAM-13.png)

    > [!Note]
    > <span data-ttu-id="d4b73-258">您應該選取 [**個人**]，因為它是 web 伺服器憑證。</span><span class="sxs-lookup"><span data-stu-id="d4b73-258">You should select **Personal**, because it is a web server certificate.</span></span> <span data-ttu-id="d4b73-259">如果您已在證書階層階層中包含憑證，也會將它新增到此存放區。</span><span class="sxs-lookup"><span data-stu-id="d4b73-259">If you included the certificate in the certification hierarchy, it will also be added to this store.</span></span>
 
14. <span data-ttu-id="d4b73-260">選取 **[下一步**]，然後選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="d4b73-260">Select **Next**, and then select **Finish**.</span></span>

    ![[證書匯入] 嚮導視窗](images/deploying-MBAM-14.png)

<span data-ttu-id="d4b73-262">您現在會在 [個人憑證] 清單中看到您網頁伺服器的伺服器憑證。</span><span class="sxs-lookup"><span data-stu-id="d4b73-262">You will now see the server certificate for your web server in the Personal Certificates list.</span></span> <span data-ttu-id="d4b73-263">它會以伺服器的通用名稱表示。</span><span class="sxs-lookup"><span data-stu-id="d4b73-263">It will be denoted by the common name of the server.</span></span> <span data-ttu-id="d4b73-264">（您可以在憑證的 [主語] 區段中找到此功能。）</span><span class="sxs-lookup"><span data-stu-id="d4b73-264">(You can find this in the subject section of the certificate.)</span></span>

<span data-ttu-id="d4b73-265">如需進一步參考：</span><span class="sxs-lookup"><span data-stu-id="d4b73-265">For further reference:</span></span>

[<span data-ttu-id="d4b73-266">MBAM 2.5 安全性考量</span><span class="sxs-lookup"><span data-stu-id="d4b73-266">MBAM 2.5 Security Considerations</span></span>](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/mbam-25-security-considerations)

[<span data-ttu-id="d4b73-267">如何保護 MBAM 網站的規劃</span><span class="sxs-lookup"><span data-stu-id="d4b73-267">Planning How to Secure the MBAM Websites</span></span>](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-how-to-secure-the-mbam-websites)

<span data-ttu-id="d4b73-268">下一步是登錄應用程式池帳戶的服務主體名稱。</span><span class="sxs-lookup"><span data-stu-id="d4b73-268">The next step is to register a service principle name for the application pool account.</span></span>

### <span data-ttu-id="d4b73-269">步驟4：為 MBAM Web 服務器設定 SSL 憑證</span><span class="sxs-lookup"><span data-stu-id="d4b73-269">Step 4: Configuring SSL certificate for MBAM Web Server</span></span>

<span data-ttu-id="d4b73-270">如果您是在用戶端與伺服器之間使用 SSL 通訊，您應該確定憑證已增強金鑰用法 Oid （1.3.6.1.5.5.7.3.1）和（1.3.6.1.5.5.7.3.2）。</span><span class="sxs-lookup"><span data-stu-id="d4b73-270">If you are using SSL communication between the client and server, you should make sure that the certificate has Enhanced Key Usage OIDs (1.3.6.1.5.5.7.3.1) and (1.3.6.1.5.5.7.3.2).</span></span> <span data-ttu-id="d4b73-271">也就是說，您應該確認已新增伺服器驗證與用戶端驗證。</span><span class="sxs-lookup"><span data-stu-id="d4b73-271">That is, you should make sure that Server Authentication and Client Authentication are added.</span></span>

<span data-ttu-id="d4b73-272">如果您在嘗試流覽服務 Url 時收到憑證錯誤，表示您使用的是頒發給其他名稱的憑證，或者您是使用不正確的 URL 進行流覽。</span><span class="sxs-lookup"><span data-stu-id="d4b73-272">If you receive a certificate error when you try to browse service URLs, you are using a certificate that was issued to a different name, or you are browsing by using an incorrect URL.</span></span>

<span data-ttu-id="d4b73-273">雖然瀏覽器可能會提示您輸入憑證錯誤訊息，但仍可讓您繼續，但 MBAM web 服務不會忽略憑證錯誤，並會封鎖連線。</span><span class="sxs-lookup"><span data-stu-id="d4b73-273">Although the browser may prompt you with a certificate error message but let you continue, the MBAM web service will not ignore certificate errors and will block the connection.</span></span> <span data-ttu-id="d4b73-274">您會在 MBAM 用戶端的 MBAM 系統管理員事件記錄檔中注意到與憑證相關的錯誤。</span><span class="sxs-lookup"><span data-stu-id="d4b73-274">You will notice certificate-related errors in the MBAM client’s MBAM Admin event log.</span></span> <span data-ttu-id="d4b73-275">如果您使用別名連線至 [管理] 和 [監視伺服器]，您應該將憑證頒發給別名名稱。</span><span class="sxs-lookup"><span data-stu-id="d4b73-275">If you are using an alias to connect to the Administration and Monitoring server, you should issue a certificate to the alias name.</span></span> <span data-ttu-id="d4b73-276">也就是說，證書的受領人名稱應該是別名，而本機伺服器的 DNS 名稱則應該新增至憑證的 [ **Subject 替換名稱**] 欄位。</span><span class="sxs-lookup"><span data-stu-id="d4b73-276">That is, the subject name of the certificate should be the alias name, and the local server’s DNS name should be added to the **Subject Alternative Name** field of the certificate.</span></span>

<span data-ttu-id="d4b73-277">範例：</span><span class="sxs-lookup"><span data-stu-id="d4b73-277">Example:</span></span>

<span data-ttu-id="d4b73-278">如果虛擬名稱是 "bitlocker.contoso.com"，而 MBAM 管理和監視伺服器名稱是「adminserver.contoso.com」，則應該將憑證頒發給 bitlocker.contoso.com （subject 名稱），而且應該將 adminserver.contoso.com 新增至憑證的 [ **Subject 備用名稱**] 欄位。</span><span class="sxs-lookup"><span data-stu-id="d4b73-278">If the virtual name is "bitlocker.contoso.com" and the MBAM Administration and Monitoring server name is "adminserver.contoso.com," the certificate should be issued to bitlocker.contoso.com (subject name), and adminserver.contoso.com should be added to **Subject Alternative Name** field of the certificate.</span></span>

<span data-ttu-id="d4b73-279">同樣地，如果您安裝了多個管理和監視伺服器來平衡負載平衡，您應該將 SSL 憑證頒發給虛擬名稱。</span><span class="sxs-lookup"><span data-stu-id="d4b73-279">Similarly, if you have multiple Administration and Monitoring servers installed to balance the load by using a load balancer, you should issue the SSL certificate to the virtual name.</span></span> <span data-ttu-id="d4b73-280">也就是說，證書的 [主旨名稱] 欄位應該擁有虛擬名稱，且所有的本機伺服器名稱都應該新增到憑證的 [ **Subject 替換名稱**] 欄位中。</span><span class="sxs-lookup"><span data-stu-id="d4b73-280">That is, the subject name field of the certificate should have the virtual name, and the names of all the local servers should be added in the **Subject Alternative Name** field of the certificate.</span></span>

<span data-ttu-id="d4b73-281">範例：</span><span class="sxs-lookup"><span data-stu-id="d4b73-281">Example:</span></span>

<span data-ttu-id="d4b73-282">如果虛擬名稱是 "bitlocker.contoso.com"，且伺服器為「adminserver1.contoso.com」和「adminiserver2.contoso.com」，則應該將憑證頒發給 bitlocker.contoso.com （subject 名稱）和 adminserver1.contoso.com，並將 adminiserver2.contoso.com 新增至憑證的 [ **Subject 替換名稱**] 欄位。</span><span class="sxs-lookup"><span data-stu-id="d4b73-282">If the virtual name is "bitlocker.contoso.com" and the servers are "adminserver1.contoso.com" and "adminiserver2.contoso.com," the certificate should be issued to bitlocker.contoso.com (subject name) and adminserver1.contoso.com, and adminiserver2.contoso.com should be added to the **Subject Alternative Name** field of the certificate.</span></span>

<span data-ttu-id="d4b73-283">使用 MBAM 設定 SSL 通訊的步驟，請參閱下列知識庫文章： [KB 2754259](https://support.microsoft.com/help/2754259)。</span><span class="sxs-lookup"><span data-stu-id="d4b73-283">The steps to configure SSL communication by using MBAM are described in the following Knowledge Base article: [KB 2754259](https://support.microsoft.com/help/2754259).</span></span>

### <span data-ttu-id="d4b73-284">步驟5：註冊應用程式池帳戶的 SPN 並設定受限制的委派</span><span class="sxs-lookup"><span data-stu-id="d4b73-284">Step 5: Register SPNS for the application pool account and configure constrained delegation</span></span>

> [!Note]
> <span data-ttu-id="d4b73-285">受限制的委派只需2.5，而 2.5 Service Pack 1 及更新版本則不需要。</span><span class="sxs-lookup"><span data-stu-id="d4b73-285">Constrained delegation is required only for 2.5 and is not required for 2.5 Service Pack 1 and later.</span></span>

<span data-ttu-id="d4b73-286">若要讓 MBAM 伺服器從管理和監控網站和自助服務入口網站驗證通訊，您必須在您用於 web 應用程式池的網域帳戶下，為主機名稱註冊服務主要名稱（SPN）。</span><span class="sxs-lookup"><span data-stu-id="d4b73-286">To enable the MBAM servers to authenticate communication from the Administration and Monitoring Website and the Self-Service Portal, you must register a Service Principal Name (SPN) for the host name under the domain account that you are using for the web application pool.</span></span> <span data-ttu-id="d4b73-287">下列文章包含註冊 Spn 的逐步指示：[規劃如何保護 MBAM 網站](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-how-to-secure-the-mbam-websites)</span><span class="sxs-lookup"><span data-stu-id="d4b73-287">The following article contains step-by-step instructions to register SPNs: [Planning How to Secure the MBAM Websites](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-how-to-secure-the-mbam-websites)</span></span>

<span data-ttu-id="d4b73-288">設定 SPN 之後，您應該在 SPN 上設定受限制的委派。</span><span class="sxs-lookup"><span data-stu-id="d4b73-288">After you have the SPN configured, you should set up constrained delegation on the SPN.</span></span> <span data-ttu-id="d4b73-289">若要這樣做，請執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="d4b73-289">To do this, follow these steps:</span></span>

1. <span data-ttu-id="d4b73-290">移至 Active Directory，然後尋找您在先前步驟中針對 MBAM 網站所設定的應用程式池認證。</span><span class="sxs-lookup"><span data-stu-id="d4b73-290">Go to Active Directory, and find the app pool credentials that you configured for MBAM websites in the previous steps.</span></span>

2. <span data-ttu-id="d4b73-291">以滑鼠右鍵按一下認證，然後選取 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="d4b73-291">Right-click the credentials, and then select **properties**.</span></span>

3. <span data-ttu-id="d4b73-292">選取 [**委派**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="d4b73-292">Select the **delegation** tab.</span></span>

4. <span data-ttu-id="d4b73-293">選取 Kerberos 驗證的選項。</span><span class="sxs-lookup"><span data-stu-id="d4b73-293">Select the option for Kerberos authentication.</span></span>

5. <span data-ttu-id="d4b73-294">選取 **[流覽]**，然後再次流覽您的應用程式池認證。</span><span class="sxs-lookup"><span data-stu-id="d4b73-294">Select **browse**, and browse again for your app pool credentials.</span></span> <span data-ttu-id="d4b73-295">接著，您應該會看到在應用程式集的 [憑據] 帳戶上設定的所有 Spn。</span><span class="sxs-lookup"><span data-stu-id="d4b73-295">You should then see the all the SPNs that are set up on the app pool creds account.</span></span> <span data-ttu-id="d4b73-296">（SPN 應該與 "HTTP/bitlocker. .com" 類似）。</span><span class="sxs-lookup"><span data-stu-id="d4b73-296">(The SPN should resemble "http/bitlocker.fqdn.com").</span></span> <span data-ttu-id="d4b73-297">醒目提示 [SPN] 與您在 MBAM 安裝期間所指定的主機名稱稱相同。</span><span class="sxs-lookup"><span data-stu-id="d4b73-297">Highlight the SPN that is the same as the host name that you specified during the MBAM installation.</span></span>

6. <span data-ttu-id="d4b73-298">選取 **\[確定\]**。</span><span class="sxs-lookup"><span data-stu-id="d4b73-298">Select **OK**.</span></span>

<span data-ttu-id="d4b73-299">現在，您已經準備好使用先決條件了。</span><span class="sxs-lookup"><span data-stu-id="d4b73-299">Now you are good with prerequisites.</span></span> <span data-ttu-id="d4b73-300">在後續步驟中，您將在伺服器上安裝 MBAM 軟體並加以設定。</span><span class="sxs-lookup"><span data-stu-id="d4b73-300">In the next steps, you will install the MBAM software on the servers and configure it.</span></span>

## <span data-ttu-id="d4b73-301">安裝和設定 MBAM 2.5 server 軟體</span><span class="sxs-lookup"><span data-stu-id="d4b73-301">Installing and configuring MBAM 2.5 server software</span></span>

### <span data-ttu-id="d4b73-302">步驟6：安裝 MBAM 2.5 server 軟體</span><span class="sxs-lookup"><span data-stu-id="d4b73-302">Step 6: Install MBAM 2.5 server software</span></span> 

<span data-ttu-id="d4b73-303">若要在資料庫伺服器以及管理和監控伺服器上使用 Microsoft BitLocker 管理和監視設定向導來安裝 MBAM Server 軟體，請依照下列步驟進行。</span><span class="sxs-lookup"><span data-stu-id="d4b73-303">To install the MBAM Server software by using the Microsoft BitLocker Administration and Monitoring Setup wizard both on Database Server and on Administration and Monitoring Server, follow these steps.</span></span>

1. <span data-ttu-id="d4b73-304">在您想要安裝 MBAM 的伺服器上，執行 MBAMserversetup.exe 以啟動 Microsoft BitLocker 管理及監視安裝程式嚮導。</span><span class="sxs-lookup"><span data-stu-id="d4b73-304">On the server on which you want to install MBAM, run MBAMserversetup.exe to start the Microsoft BitLocker Administration and Monitoring Setup wizard.</span></span>

2. <span data-ttu-id="d4b73-305">在 [歡迎] 頁面上，選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d4b73-305">On the Welcome page, select **Next**.</span></span>

3. <span data-ttu-id="d4b73-306">閱讀並接受 Microsoft 軟體授權協定，然後選取 **[下一步]** 繼續安裝。</span><span class="sxs-lookup"><span data-stu-id="d4b73-306">Read and accept the Microsoft Software License Agreement, and then select **Next** to continue the installation.</span></span>

4. <span data-ttu-id="d4b73-307">在您檢查更新時，決定是否要使用 Microsoft Update，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d4b73-307">Decide whether to use Microsoft Update when you check for updates, and then select **Next**.</span></span>

5. <span data-ttu-id="d4b73-308">決定是否要參與客戶經驗改進計畫，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d4b73-308">Decide whether to participate in the Customer Experience Improvement Program, and then select **Next**.</span></span>

6. <span data-ttu-id="d4b73-309">若要開始安裝，請選取 [**安裝**]。</span><span class="sxs-lookup"><span data-stu-id="d4b73-309">To start the installation, select **Install**.</span></span>

7. <span data-ttu-id="d4b73-310">若要在 MBAM Server 軟體完成安裝之後設定伺服器功能，請選取 [在**嚮導關閉後執行 MBAM 伺服器設定]** 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d4b73-310">To configure the server features after the MBAM Server software finishes installing, select the **Run MBAM Server Configuration after the wizard closes** check box.</span></span> <span data-ttu-id="d4b73-311">或者，您可以在稍後使用伺服器安裝在 [**開始**] 功能表上建立的 [ **MBAM 伺服器**設定] 快捷方式來設定 MBAM。</span><span class="sxs-lookup"><span data-stu-id="d4b73-311">Or, you can configure MBAM later by using the **MBAM Server Configuration** shortcut that the server installation creates on your **Start** menu.</span></span>

8. <span data-ttu-id="d4b73-312">選取 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="d4b73-312">Select **Finish**.</span></span>

<span data-ttu-id="d4b73-313">如需詳細資訊，請參閱[安裝 MBAM 2.5 Server 軟體](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/installing-the-mbam-25-server-software)。</span><span class="sxs-lookup"><span data-stu-id="d4b73-313">For more information, see [Installing the MBAM 2.5 Server Software](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/installing-the-mbam-25-server-software).</span></span>

### <span data-ttu-id="d4b73-314">步驟7：設定 MBAM 2.5 資料庫和報告角色</span><span class="sxs-lookup"><span data-stu-id="d4b73-314">Step 7: Configure MBAM 2.5 database and reports role</span></span>

<span data-ttu-id="d4b73-315">在此步驟中，我們將使用 [MBAM] 嚮導來設定 MBAM 2.5 資料庫和報告元件：</span><span class="sxs-lookup"><span data-stu-id="d4b73-315">In this step, we will configure the MBAM 2.5 databases and reporting component by using the MBAM Wizard:</span></span>

1. <span data-ttu-id="d4b73-316">使用嚮導來設定合規性和審核資料庫及復原資料庫：</span><span class="sxs-lookup"><span data-stu-id="d4b73-316">Configure the Compliance and Audit Database and the Recovery Database by using the wizard:</span></span>
   
   1. <span data-ttu-id="d4b73-317">在您想要設定資料庫的伺服器上，啟動 [ **MBAM 伺服器設定] 嚮導**。</span><span class="sxs-lookup"><span data-stu-id="d4b73-317">On the server on which you want to configure the databases, start the **MBAM Server Configuration wizard**.</span></span> <span data-ttu-id="d4b73-318">您可以選取 [**開始**] 功能表上的 [ **MBAM 伺服器**設定] 來開啟嚮導。</span><span class="sxs-lookup"><span data-stu-id="d4b73-318">You can select **MBAM Server Configuration** on the **Start** menu to open the wizard.</span></span>

   2. <span data-ttu-id="d4b73-319">選取 [**新增功能**]，選取 [**合規性與審計資料庫**]、[復原**資料庫及報告**]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d4b73-319">Select **Add New Features**, select **Compliance and Audit Database**, **Recovery Database and Reports**, and then select **Next**.</span></span> <span data-ttu-id="d4b73-320">嚮導會檢查資料庫的所有先決條件是否都已滿足。</span><span class="sxs-lookup"><span data-stu-id="d4b73-320">The wizard checks that all prerequisites for the databases are met.</span></span>

   3. <span data-ttu-id="d4b73-321">如果先決條件檢查成功，請選取 **[下一步]** 繼續。</span><span class="sxs-lookup"><span data-stu-id="d4b73-321">If the prerequisite check is successful, select **Next** to continue.</span></span> <span data-ttu-id="d4b73-322">否則，請解決任何缺少的先決條件，然後**再次選取 [檢查先決條件**]。</span><span class="sxs-lookup"><span data-stu-id="d4b73-322">Otherwise, resolve any missing prerequisites, and then select **Check prerequisites again**.</span></span>
   
   4. <span data-ttu-id="d4b73-323">使用下列說明，在嚮導中輸入欄位值：</span><span class="sxs-lookup"><span data-stu-id="d4b73-323">Using the following descriptions, enter the field values in the wizard:</span></span>

2. <span data-ttu-id="d4b73-324">合規性和審核資料庫</span><span class="sxs-lookup"><span data-stu-id="d4b73-324">Compliance and audit database</span></span>

   |<span data-ttu-id="d4b73-325">欄位</span><span class="sxs-lookup"><span data-stu-id="d4b73-325">Field</span></span>   |<span data-ttu-id="d4b73-326">描述</span><span class="sxs-lookup"><span data-stu-id="d4b73-326">Description</span></span>|
   |-------|-------|
   |<span data-ttu-id="d4b73-327">SQL Server 名稱</span><span class="sxs-lookup"><span data-stu-id="d4b73-327">SQL Server name</span></span> |<span data-ttu-id="d4b73-328">您正在設定合規性和審核資料庫之伺服器的名稱。</span><span class="sxs-lookup"><span data-stu-id="d4b73-328">Name of the server on which you are configuring the Compliance and Audit Database.</span></span> <br /> <span data-ttu-id="d4b73-329">您必須在合規性和審核資料庫電腦上新增例外狀況，才能在 SQL Server 埠上啟用入站流量。</span><span class="sxs-lookup"><span data-stu-id="d4b73-329">You must add an exception on the Compliance and Audit Database computer to enable incoming inbound traffic on the SQL Server port.</span></span> <span data-ttu-id="d4b73-330">預設埠號碼是1433。</span><span class="sxs-lookup"><span data-stu-id="d4b73-330">The default port number is 1433.</span></span>|
   |<span data-ttu-id="d4b73-331">SQL Server 資料庫實例</span><span class="sxs-lookup"><span data-stu-id="d4b73-331">SQL Server database instance</span></span>    |<span data-ttu-id="d4b73-332">儲存合規性和審核資料之資料庫實例的名稱。</span><span class="sxs-lookup"><span data-stu-id="d4b73-332">Name of the database instance where the compliance and audit data will be stored.</span></span> <span data-ttu-id="d4b73-333">如果您使用的是預設實例，則必須將此欄位留白。</span><span class="sxs-lookup"><span data-stu-id="d4b73-333">If you are using the default instance, you must leave this field blank.</span></span> <span data-ttu-id="d4b73-334">您也必須指定資料庫資訊的位置。</span><span class="sxs-lookup"><span data-stu-id="d4b73-334">You must also specify where the database information will be located.</span></span>|
   |<span data-ttu-id="d4b73-335">資料庫名稱</span><span class="sxs-lookup"><span data-stu-id="d4b73-335">Database name</span></span>   |<span data-ttu-id="d4b73-336">儲存合規性資料之資料庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="d4b73-336">Name of the database that will store the compliance data.</span></span> <span data-ttu-id="d4b73-337">您必須記下您在此處指定的資料庫名稱，因為您將必須在後續步驟中提供此資訊。</span><span class="sxs-lookup"><span data-stu-id="d4b73-337">You must note the name of the database that you are specifying here because you will have to provide this information in later steps.</span></span>|
   |<span data-ttu-id="d4b73-338">讀取/寫入權限網域使用者或群組</span><span class="sxs-lookup"><span data-stu-id="d4b73-338">Read/write permission domain user or group</span></span>  |<span data-ttu-id="d4b73-339">根據步驟2中的設定，指定 MBAMAppPool 使用者的名稱。</span><span class="sxs-lookup"><span data-stu-id="d4b73-339">Specify the name of the MBAMAppPool user as configured in step 2.</span></span>|
   |<span data-ttu-id="d4b73-340">唯讀存取網域使用者或群組</span><span class="sxs-lookup"><span data-stu-id="d4b73-340">Read-only access domain user or group</span></span>   |<span data-ttu-id="d4b73-341">根據步驟2中的設定，指定 MBAMROUser 使用者的名稱。</span><span class="sxs-lookup"><span data-stu-id="d4b73-341">Specify the name of the MBAMROUser user as configured in step 2.</span></span>|

3. <span data-ttu-id="d4b73-342">[恢復資料庫]。</span><span class="sxs-lookup"><span data-stu-id="d4b73-342">Recovery database.</span></span>

   |<span data-ttu-id="d4b73-343">欄位</span><span class="sxs-lookup"><span data-stu-id="d4b73-343">Field</span></span>   |<span data-ttu-id="d4b73-344">描述</span><span class="sxs-lookup"><span data-stu-id="d4b73-344">Description</span></span>|
   |-----|-----|
   |<span data-ttu-id="d4b73-345">SQL Server 名稱</span><span class="sxs-lookup"><span data-stu-id="d4b73-345">SQL Server name</span></span> |<span data-ttu-id="d4b73-346">您正在設定復原資料庫之伺服器的名稱。</span><span class="sxs-lookup"><span data-stu-id="d4b73-346">Name of the server on which you are configuring the Recovery Database.</span></span> <span data-ttu-id="d4b73-347">您必須在復原資料庫電腦上新增例外狀況，才能在 SQL Server 埠上啟用入站流量。</span><span class="sxs-lookup"><span data-stu-id="d4b73-347">You must add an exception on the Recovery Database computer to enable incoming inbound traffic on the SQL Server port.</span></span> <span data-ttu-id="d4b73-348">預設埠號碼是1433。</span><span class="sxs-lookup"><span data-stu-id="d4b73-348">The default port number is 1433.</span></span>|
   |<span data-ttu-id="d4b73-349">SQL Server 資料庫實例</span><span class="sxs-lookup"><span data-stu-id="d4b73-349">SQL Server database instance</span></span>    |<span data-ttu-id="d4b73-350">儲存恢復資料之資料庫實例的名稱。</span><span class="sxs-lookup"><span data-stu-id="d4b73-350">Name of the database instance where the recovery data will be stored.</span></span> <span data-ttu-id="d4b73-351">如果您使用的是預設實例，則必須將此欄位留白。</span><span class="sxs-lookup"><span data-stu-id="d4b73-351">If you are using the default instance, you must leave this field blank.</span></span> <span data-ttu-id="d4b73-352">您也必須指定資料庫資訊的位置。</span><span class="sxs-lookup"><span data-stu-id="d4b73-352">You must also specify where the database information will be located.</span></span>|
   |<span data-ttu-id="d4b73-353">資料庫名稱</span><span class="sxs-lookup"><span data-stu-id="d4b73-353">Database name</span></span>   |<span data-ttu-id="d4b73-354">儲存修復資料之資料庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="d4b73-354">Name of the database that will store the recovery data.</span></span>|
   |<span data-ttu-id="d4b73-355">讀取/寫入權限網域使用者或群組</span><span class="sxs-lookup"><span data-stu-id="d4b73-355">Read/write permission domain user or group</span></span>  |<span data-ttu-id="d4b73-356">擁有此資料庫讀/寫許可權的網域使用者或群組，可讓 web 應用程式存取此資料庫中的資料和報表。</span><span class="sxs-lookup"><span data-stu-id="d4b73-356">Domain user or group that has read/write permission to this database to enable the web applications to access the data and reports in this database.</span></span> <br /><span data-ttu-id="d4b73-357">如果您在此欄位中輸入使用者，其值必須與 [**設定 Web 應用程式**] 頁面上的 [ **web 服務應用程式池網域帳戶**] 欄位中的值相同。</span><span class="sxs-lookup"><span data-stu-id="d4b73-357">If you enter a user in this field, it must be the same value as the value in the **Web service application pool domain account** field on the **Configure Web Applications** page.</span></span> <br /><span data-ttu-id="d4b73-358">如果您在此欄位中輸入群組，則 [**設定 Web 應用程式**] 頁面上的 [ **Web 服務應用程式群組網域帳戶**] 欄位中的值必須是您在這個欄位中輸入之群組的成員。</span><span class="sxs-lookup"><span data-stu-id="d4b73-358">If you enter a group in this field, the value in the **Web service application pool domain account** field on the **Configure Web Applications** page must be a member of the group that you enter in this field.</span></span>|
   
   <span data-ttu-id="d4b73-359">完成專案後，請選取 **[下一步**]。</span><span class="sxs-lookup"><span data-stu-id="d4b73-359">When you finish your entries, select **Next**.</span></span> <span data-ttu-id="d4b73-360">嚮導會檢查資料庫的所有先決條件是否都已滿足。</span><span class="sxs-lookup"><span data-stu-id="d4b73-360">The wizard checks that all prerequisites for the databases are met.</span></span>
   
   <span data-ttu-id="d4b73-361">如果先決條件檢查成功，請選取 **[下一步]** 繼續。</span><span class="sxs-lookup"><span data-stu-id="d4b73-361">If the prerequisite check is successful, select **Next** to continue.</span></span> <span data-ttu-id="d4b73-362">否則，請解決任何缺少的先決條件，然後再次選取 **[下一步]** 。</span><span class="sxs-lookup"><span data-stu-id="d4b73-362">Otherwise, resolve any missing prerequisites, and then select **Next** again.</span></span>

4. <span data-ttu-id="d4b73-363">有關.</span><span class="sxs-lookup"><span data-stu-id="d4b73-363">Reports.</span></span>

   |<span data-ttu-id="d4b73-364">欄位</span><span class="sxs-lookup"><span data-stu-id="d4b73-364">Field</span></span>   |<span data-ttu-id="d4b73-365">描述</span><span class="sxs-lookup"><span data-stu-id="d4b73-365">Description</span></span>|
   |----|----|
   |<span data-ttu-id="d4b73-366">SQL Server Reporting Services 實例</span><span class="sxs-lookup"><span data-stu-id="d4b73-366">SQL Server Reporting Services instance</span></span>  |<span data-ttu-id="d4b73-367">將設定報告的 SQL Server Reporting Services 實例。</span><span class="sxs-lookup"><span data-stu-id="d4b73-367">Instance of SQL Server Reporting Services where the reports will be configured.</span></span> <span data-ttu-id="d4b73-368">如果您使用的是預設實例，則必須將此欄位留白。</span><span class="sxs-lookup"><span data-stu-id="d4b73-368">If you are using the default instance, you must leave this field blank.</span></span>|
   |<span data-ttu-id="d4b73-369">報告角色網域群組</span><span class="sxs-lookup"><span data-stu-id="d4b73-369">Reporting role domain group</span></span> |<span data-ttu-id="d4b73-370">如步驟2所述，指定 MBAMRUGrp 的名稱。</span><span class="sxs-lookup"><span data-stu-id="d4b73-370">Specify the name of the MBAMRUGrp as mentioned in step 2.</span></span>|
   |<span data-ttu-id="d4b73-371">SQL Server 名稱</span><span class="sxs-lookup"><span data-stu-id="d4b73-371">SQL Server name</span></span> |<span data-ttu-id="d4b73-372">已設定合規性和審核資料庫之伺服器的名稱。</span><span class="sxs-lookup"><span data-stu-id="d4b73-372">Name of the server on which the Compliance and Audit Database is configured.</span></span>|
   |<span data-ttu-id="d4b73-373">SQL Server 資料庫實例</span><span class="sxs-lookup"><span data-stu-id="d4b73-373">SQL Server database instance</span></span>    |<span data-ttu-id="d4b73-374">已設定合規性和審核資料之資料庫實例的名稱。</span><span class="sxs-lookup"><span data-stu-id="d4b73-374">Name of the database instance where the compliance and audit data is configured.</span></span> <span data-ttu-id="d4b73-375">如果您使用的是預設實例，則必須將此欄位留白。</span><span class="sxs-lookup"><span data-stu-id="d4b73-375">If you are using the default instance, you must leave this field blank.</span></span> <br /><span data-ttu-id="d4b73-376">您必須在報表電腦上新增例外狀況，才能在報表伺服器的埠上啟用傳入流量。</span><span class="sxs-lookup"><span data-stu-id="d4b73-376">You must add an exception on the Reports computer to enable incoming traffic on the port of the Reporting Server.</span></span> <span data-ttu-id="d4b73-377">（預設埠是80。）</span><span class="sxs-lookup"><span data-stu-id="d4b73-377">(The default port is 80.)</span></span>|
   |<span data-ttu-id="d4b73-378">資料庫名稱</span><span class="sxs-lookup"><span data-stu-id="d4b73-378">Database name</span></span>|  <span data-ttu-id="d4b73-379">合規性和審核資料庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="d4b73-379">Name of the Compliance and Audit Database.</span></span> <span data-ttu-id="d4b73-380">根據預設，資料庫名稱是 MBAM 合規性狀態。</span><span class="sxs-lookup"><span data-stu-id="d4b73-380">By default, the database name is MBAM Compliance Status.</span></span>|
   |<span data-ttu-id="d4b73-381">合規性與審計資料庫網域帳戶</span><span class="sxs-lookup"><span data-stu-id="d4b73-381">Compliance and Audit Database domain account</span></span>    |<span data-ttu-id="d4b73-382">根據步驟2中的設定，指定 MBAMROUser 使用者的名稱。</span><span class="sxs-lookup"><span data-stu-id="d4b73-382">Specify the name of the MBAMROUser user as configured in step 2.</span></span>|
   
   <span data-ttu-id="d4b73-383">完成專案後，請選取 **[下一步**]。</span><span class="sxs-lookup"><span data-stu-id="d4b73-383">When you finish your entries, select **Next**.</span></span> <span data-ttu-id="d4b73-384">嚮導會檢查是否符合 [報告] 功能的所有先決條件。</span><span class="sxs-lookup"><span data-stu-id="d4b73-384">The wizard checks that all prerequisites for the Reports feature are met.</span></span> <span data-ttu-id="d4b73-385">選取 [下一步] 以繼續。</span><span class="sxs-lookup"><span data-stu-id="d4b73-385">Select Next to continue.</span></span> <span data-ttu-id="d4b73-386">在 [**摘要**] 頁面上，查看將新增的功能。</span><span class="sxs-lookup"><span data-stu-id="d4b73-386">On the **Summary** page, review the features that will be added.</span></span>
   
   <span data-ttu-id="d4b73-387">如需詳細資訊，請參閱下列文章：[如何設定 MBAM 2.5 資料庫](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-configure-the-mbam-25-databases)。</span><span class="sxs-lookup"><span data-stu-id="d4b73-387">For more information, see the following article: [How to Configure the MBAM 2.5 Databases](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-configure-the-mbam-25-databases).</span></span>

### <span data-ttu-id="d4b73-388">步驟8：設定 MBAM 2.5 Web 應用程式角色</span><span class="sxs-lookup"><span data-stu-id="d4b73-388">Step 8: Configure the MBAM 2.5 Web applications role</span></span>

1. <span data-ttu-id="d4b73-389">在您想要設定 web 應用程式的伺服器上，啟動 [MBAM 伺服器設定] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="d4b73-389">On the server on which you want to configure the web applications, start the MBAM Server Configuration wizard.</span></span> <span data-ttu-id="d4b73-390">您可以選取 [**開始**] 功能表上的 [ **MBAM 伺服器**設定] 來開啟嚮導。</span><span class="sxs-lookup"><span data-stu-id="d4b73-390">You can select **MBAM Server Configuration** on the **Start** menu to open the wizard.</span></span>

2. <span data-ttu-id="d4b73-391">選取 [**新增功能**]，選取 [**管理及監視網站**與**自助式入口**網站]，然後選取 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="d4b73-391">Select **Add New Features**, select **Administration and Monitoring Website** and **Self-Service Portal**, and then select **Next**.</span></span> <span data-ttu-id="d4b73-392">嚮導會檢查資料庫的所有先決條件是否都已滿足。</span><span class="sxs-lookup"><span data-stu-id="d4b73-392">The wizard checks that all prerequisites for the databases are met.</span></span>

3. <span data-ttu-id="d4b73-393">如果先決條件檢查成功，請選取 **[下一步]** 繼續。</span><span class="sxs-lookup"><span data-stu-id="d4b73-393">If the prerequisite check is successful, select **Next** to continue.</span></span> <span data-ttu-id="d4b73-394">否則，請解決任何缺少的先決條件，然後**再次選取 [檢查先決條件**]。</span><span class="sxs-lookup"><span data-stu-id="d4b73-394">Otherwise, resolve any missing prerequisites, and then select **Check prerequisites again**.</span></span>

4. <span data-ttu-id="d4b73-395">使用下列描述在嚮導中輸入欄位值。</span><span class="sxs-lookup"><span data-stu-id="d4b73-395">Use the following descriptions to enter the field values in the wizard.</span></span>

   |<span data-ttu-id="d4b73-396">欄位</span><span class="sxs-lookup"><span data-stu-id="d4b73-396">Field</span></span>   |<span data-ttu-id="d4b73-397">描述</span><span class="sxs-lookup"><span data-stu-id="d4b73-397">Description</span></span>|
   |-----|-----|
   |<span data-ttu-id="d4b73-398">安全性憑證</span><span class="sxs-lookup"><span data-stu-id="d4b73-398">Security certificate</span></span>    |<span data-ttu-id="d4b73-399">在步驟3中選取先前建立的憑證，以選擇性地將 web 服務與您要設定管理和監控網站的伺服器進行通訊。</span><span class="sxs-lookup"><span data-stu-id="d4b73-399">Select a previously created certificate in step 3 to optionally encrypt the communication between the web services and the server on which you are configuring the Administration and Monitoring Website.</span></span> <span data-ttu-id="d4b73-400">如果您選取 [不使用憑證]，您的 web 通訊可能不安全。</span><span class="sxs-lookup"><span data-stu-id="d4b73-400">If you select Do not use a certificate, your web communication may not be secure.</span></span>|
   |<span data-ttu-id="d4b73-401">主機名稱</span><span class="sxs-lookup"><span data-stu-id="d4b73-401">Host name</span></span>   |<span data-ttu-id="d4b73-402">您要在其上設定管理和監視網站的主機名稱稱。</span><span class="sxs-lookup"><span data-stu-id="d4b73-402">Name of the host computer on which you are configuring the Administration and Monitoring Website.</span></span> <br /><span data-ttu-id="d4b73-403">它不一定是電腦的主機名稱，可能是什麼。</span><span class="sxs-lookup"><span data-stu-id="d4b73-403">It does not have to be the hostname of the machine, it could be anything.</span></span> <span data-ttu-id="d4b73-404">不過，如果主機名稱與電腦的 netbios 名稱不同，您就必須建立 A 記錄，並確定 SPN 使用的是自訂主機名稱，而不是 netbios 名稱。</span><span class="sxs-lookup"><span data-stu-id="d4b73-404">However, if the hostname is different than the netbios name of the computer, you have to create an A record and make sure the SPN uses the custom hostname, not the netbios name.</span></span> <span data-ttu-id="d4b73-405">這在負載平衡案例中是常見的。</span><span class="sxs-lookup"><span data-stu-id="d4b73-405">This is common on load balancing scenarios.</span></span>|
   |<span data-ttu-id="d4b73-406">安裝路徑</span><span class="sxs-lookup"><span data-stu-id="d4b73-406">Installation path</span></span>   |<span data-ttu-id="d4b73-407">您要安裝管理和監控網站的路徑。</span><span class="sxs-lookup"><span data-stu-id="d4b73-407">Path on which you are installing the Administration and Monitoring Website.</span></span>|
   |<span data-ttu-id="d4b73-408">連接埠</span><span class="sxs-lookup"><span data-stu-id="d4b73-408">Port</span></span>    |<span data-ttu-id="d4b73-409">要用於網站通訊的埠號碼。</span><span class="sxs-lookup"><span data-stu-id="d4b73-409">Port number to use for website communication.</span></span> <br /> <span data-ttu-id="d4b73-410">您必須設定防火牆例外狀況，才能透過指定的埠進行通訊。</span><span class="sxs-lookup"><span data-stu-id="d4b73-410">You must set a firewall exception to enable communication through the specified port.</span></span>|
   |<span data-ttu-id="d4b73-411">Web 服務應用程式池網域帳戶和密碼</span><span class="sxs-lookup"><span data-stu-id="d4b73-411">Web service application pool domain account and password</span></span>    |<span data-ttu-id="d4b73-412">根據步驟2中的設定，指定 MBAMAppPool 使用者的使用者帳戶和密碼。</span><span class="sxs-lookup"><span data-stu-id="d4b73-412">Specify the user account and password of the MBAMAppPool user as configured in step 2.</span></span> <br /> <span data-ttu-id="d4b73-413">若要提高安全性，請將認證中指定的帳號設定為擁有有限的使用者權限。</span><span class="sxs-lookup"><span data-stu-id="d4b73-413">For improved security, set the account that is specified in the credentials to have limited user rights.</span></span> <span data-ttu-id="d4b73-414">此外，將帳戶的密碼設定為永不過期。</span><span class="sxs-lookup"><span data-stu-id="d4b73-414">Also, set the password of the account to never expire.</span></span>|

5. <span data-ttu-id="d4b73-415">確認內建的 IIS_IUSRS 帳戶或應用程式池帳戶已新增至**驗證之後模仿用戶端**，並以**批次工作**的本機安全性設定登入。</span><span class="sxs-lookup"><span data-stu-id="d4b73-415">Verify that the built-in IIS_IUSRS account or the application pool account was added to the **Impersonate a client after authentication** and the **Log on as a batch job** local security settings.</span></span>

   <span data-ttu-id="d4b73-416">若要檢查是否已將帳戶新增到本機安全性設定，請開啟 [**本機安全性原則編輯器**]，展開 [**本機原則**] 節點，選取 [**使用者權利指派**] 節點，然後在驗證之後，按兩下 [**模仿用戶端**]，然後在右側窗格中**以批次工作原則登**入。</span><span class="sxs-lookup"><span data-stu-id="d4b73-416">To check whether the account was added to the local security settings, open the **Local Security Policy editor**, expand the **Local Policies** node, select the **User Rights Assignment** node, and double-select **Impersonate a client after authentication** and **Log on as a batch job** policies in the right-side pane.</span></span>

6. <span data-ttu-id="d4b73-417">使用下欄欄位描述來設定合規性和審核資料庫的嚮導中的連線資訊。</span><span class="sxs-lookup"><span data-stu-id="d4b73-417">Use the following field descriptions to configure the connection information in the wizard for the Compliance and Audit Database.</span></span>
   |<span data-ttu-id="d4b73-418">欄位</span><span class="sxs-lookup"><span data-stu-id="d4b73-418">Field</span></span>   |<span data-ttu-id="d4b73-419">描述</span><span class="sxs-lookup"><span data-stu-id="d4b73-419">Description</span></span>|
   |------|------|
   |<span data-ttu-id="d4b73-420">SQL Server 名稱</span><span class="sxs-lookup"><span data-stu-id="d4b73-420">SQL Server name</span></span> |<span data-ttu-id="d4b73-421">已設定合規性和審核資料庫之伺服器的名稱。</span><span class="sxs-lookup"><span data-stu-id="d4b73-421">Name of the server on which the Compliance and Audit Database is configured.</span></span>|
   |<span data-ttu-id="d4b73-422">SQL Server 資料庫實例</span><span class="sxs-lookup"><span data-stu-id="d4b73-422">SQL Server database instance</span></span>    |<span data-ttu-id="d4b73-423">SQL Server 實例的名稱（例如 \<Server Name\> ），以及設定合規性和審核資料庫的物件。</span><span class="sxs-lookup"><span data-stu-id="d4b73-423">Name of the instance of SQL Server (for example, \<Server Name\>) and on which the Compliance and Audit Database is configured.</span></span> <span data-ttu-id="d4b73-424">如果您使用的是預設實例，請將此選項留白。</span><span class="sxs-lookup"><span data-stu-id="d4b73-424">Leave this blank if you are using the default instance.</span></span>|
   |<span data-ttu-id="d4b73-425">資料庫名稱</span><span class="sxs-lookup"><span data-stu-id="d4b73-425">Database name</span></span>   |<span data-ttu-id="d4b73-426">合規性和審核資料庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="d4b73-426">Name of the Compliance and Audit Database.</span></span> <span data-ttu-id="d4b73-427">根據預設，它是「MBAM 合規性狀態」。</span><span class="sxs-lookup"><span data-stu-id="d4b73-427">By default, it’s "MBAM Compliance Status".</span></span>|

7. <span data-ttu-id="d4b73-428">使用下欄欄位描述來設定恢復資料庫的嚮導中的連線資訊。</span><span class="sxs-lookup"><span data-stu-id="d4b73-428">Use the following field descriptions to configure the connection information in the wizard for the Recovery Database.</span></span>
   |<span data-ttu-id="d4b73-429">欄位</span><span class="sxs-lookup"><span data-stu-id="d4b73-429">Field</span></span>   |<span data-ttu-id="d4b73-430">描述</span><span class="sxs-lookup"><span data-stu-id="d4b73-430">Description</span></span>|
   |----|----|
   |<span data-ttu-id="d4b73-431">SQL Server 名稱</span><span class="sxs-lookup"><span data-stu-id="d4b73-431">SQL Server name</span></span> |<span data-ttu-id="d4b73-432">已設定復原資料庫之伺服器的名稱。</span><span class="sxs-lookup"><span data-stu-id="d4b73-432">Name of the server on which the Recovery Database is configured.</span></span>|
   |<span data-ttu-id="d4b73-433">SQL Server 資料庫實例</span><span class="sxs-lookup"><span data-stu-id="d4b73-433">SQL Server database instance</span></span>    |<span data-ttu-id="d4b73-434">在其上設定復原資料庫的 SQL Server 實例名稱（例如， \<Server Name\> ）。</span><span class="sxs-lookup"><span data-stu-id="d4b73-434">Name of the instance of SQL Server (for example, \<Server Name\>) on which the Recovery Database is configured.</span></span> <span data-ttu-id="d4b73-435">如果您使用的是預設實例，請將此選項留白。</span><span class="sxs-lookup"><span data-stu-id="d4b73-435">Leave this blank if you are using the default instance.</span></span>|
   |<span data-ttu-id="d4b73-436">資料庫名稱</span><span class="sxs-lookup"><span data-stu-id="d4b73-436">Database name</span></span>   |<span data-ttu-id="d4b73-437">恢復資料庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="d4b73-437">Name of the Recovery Database.</span></span> <span data-ttu-id="d4b73-438">根據預設，它是「MBAM 恢復和硬體」。</span><span class="sxs-lookup"><span data-stu-id="d4b73-438">By default, it’s "MBAM Recovery and Hardware".</span></span>|

8. <span data-ttu-id="d4b73-439">使用下列描述在嚮導中輸入欄位值，以設定管理和監視網站。</span><span class="sxs-lookup"><span data-stu-id="d4b73-439">Use the following descriptions to enter the field values in the wizard to configure the Administration and Monitoring Website.</span></span>
   |<span data-ttu-id="d4b73-440">欄位</span><span class="sxs-lookup"><span data-stu-id="d4b73-440">Field</span></span>   |<span data-ttu-id="d4b73-441">描述</span><span class="sxs-lookup"><span data-stu-id="d4b73-441">Description</span></span>|
   |----|----|
   |<span data-ttu-id="d4b73-442">[高級支援人員] 角色網域群組</span><span class="sxs-lookup"><span data-stu-id="d4b73-442">Advanced Helpdesk role domain group</span></span> |<span data-ttu-id="d4b73-443">指定 MBAMAdvHelpDsk 群組的名稱，如步驟2所設定。</span><span class="sxs-lookup"><span data-stu-id="d4b73-443">Specify the name of the MBAMAdvHelpDsk Group as configured in step 2.</span></span>|
   |<span data-ttu-id="d4b73-444">支援人員角色網域群組</span><span class="sxs-lookup"><span data-stu-id="d4b73-444">Helpdesk role domain group</span></span>  |<span data-ttu-id="d4b73-445">指定 MBAMHelpDsk 群組的名稱，如步驟2所設定。</span><span class="sxs-lookup"><span data-stu-id="d4b73-445">Specify the name of the MBAMHelpDsk Group as configured in step 2.</span></span>|
   |<span data-ttu-id="d4b73-446">使用 System Center Configuration Manager 整合</span><span class="sxs-lookup"><span data-stu-id="d4b73-446">Use System Center Configuration Manager Integration</span></span> |<span data-ttu-id="d4b73-447">選取以清除此核取方塊。</span><span class="sxs-lookup"><span data-stu-id="d4b73-447">Select to clear this check box.</span></span>     |
   |<span data-ttu-id="d4b73-448">報告角色網域群組</span><span class="sxs-lookup"><span data-stu-id="d4b73-448">Reporting role domain group</span></span> |<span data-ttu-id="d4b73-449">指定 MBAMRUGrp 群組的名稱，如步驟2所設定。</span><span class="sxs-lookup"><span data-stu-id="d4b73-449">Specify the name of the MBAMRUGrp Group as configured in step 2.</span></span>    |
   |<span data-ttu-id="d4b73-450">SQL Server Reporting Services URL</span><span class="sxs-lookup"><span data-stu-id="d4b73-450">SQL Server Reporting Services URL</span></span>   |<span data-ttu-id="d4b73-451">指定要在其上設定 MBAM 報告之 SSRS 伺服器的 Web 服務 URL。</span><span class="sxs-lookup"><span data-stu-id="d4b73-451">Specify the Web Service URL for the SSRS server on which the MBAM reports are configured.</span></span> <span data-ttu-id="d4b73-452">您可以在資料庫伺服器上登入 Reporting Services Configuration Manager，以找到這項資訊。</span><span class="sxs-lookup"><span data-stu-id="d4b73-452">You can find this information by logging in to Reporting Services Configuration Manager on the Database Server.</span></span> <br /> <span data-ttu-id="d4b73-453">完整功能變數名稱的範例：https://MyReportServer.Contoso.com/ReportServer</span><span class="sxs-lookup"><span data-stu-id="d4b73-453">Example of a fully qualified domain name: https://MyReportServer.Contoso.com/ReportServer</span></span> <br /><span data-ttu-id="d4b73-454">自訂主機名稱範例：https://MyReportServer/ReportServer</span><span class="sxs-lookup"><span data-stu-id="d4b73-454">Example of a custom host name: https://MyReportServer/ReportServer</span></span>|
   |<span data-ttu-id="d4b73-455">虛擬目錄</span><span class="sxs-lookup"><span data-stu-id="d4b73-455">Virtual directory</span></span>   |<span data-ttu-id="d4b73-456">[管理] 和 [監視] 網站的虛擬目錄。</span><span class="sxs-lookup"><span data-stu-id="d4b73-456">Virtual directory of the Administration and Monitoring Website.</span></span> <span data-ttu-id="d4b73-457">這個名稱會對應到伺服器上的網站物理目錄，並會附加到網站的主機名稱。</span><span class="sxs-lookup"><span data-stu-id="d4b73-457">This name corresponds to the website’s physical directory on the server and is appended to the website’s host name.</span></span> <span data-ttu-id="d4b73-458">例如：</span><span class="sxs-lookup"><span data-stu-id="d4b73-458">For example:</span></span> <br /><span data-ttu-id="d4b73-459">HTTP （s）：// *\<host name\>* ： *\<port\>* /HelpDesk/</span><span class="sxs-lookup"><span data-stu-id="d4b73-459">http(s)://*\<host name\>*:*\<port\>*/HelpDesk/</span></span> <br /><span data-ttu-id="d4b73-460">如果您沒有指定虛擬目錄，就會使用 [價值支援人員]。</span><span class="sxs-lookup"><span data-stu-id="d4b73-460">If you do not specify a virtual directory, the value HelpDesk will be used.</span></span>     |

9. <span data-ttu-id="d4b73-461">使用下列描述在嚮導中輸入欄位值以設定自助入口網站。</span><span class="sxs-lookup"><span data-stu-id="d4b73-461">Use the following description to enter the field values in the wizard to configure the Self-Service Portal.</span></span>

   |<span data-ttu-id="d4b73-462">欄位</span><span class="sxs-lookup"><span data-stu-id="d4b73-462">Field</span></span>   |<span data-ttu-id="d4b73-463">描述</span><span class="sxs-lookup"><span data-stu-id="d4b73-463">Description</span></span>|
   |----|----|
   |<span data-ttu-id="d4b73-464">虛擬目錄</span><span class="sxs-lookup"><span data-stu-id="d4b73-464">Virtual directory</span></span>   |<span data-ttu-id="d4b73-465">Web 應用程式的虛擬目錄。</span><span class="sxs-lookup"><span data-stu-id="d4b73-465">Virtual directory of the web application.</span></span> <span data-ttu-id="d4b73-466">這個名稱會對應到伺服器上的網站物理目錄，並會附加到網站的主機名稱。</span><span class="sxs-lookup"><span data-stu-id="d4b73-466">This name corresponds to the website’s physical directory on the server and is appended to the website’s host name.</span></span> <span data-ttu-id="d4b73-467">例如：</span><span class="sxs-lookup"><span data-stu-id="d4b73-467">For example:</span></span><br /><span data-ttu-id="d4b73-468">HTTP （s）：// *\<host name\>* ： *\<port\>* /SelfService/</span><span class="sxs-lookup"><span data-stu-id="d4b73-468">http(s)://*\<host name\>*:*\<port\>*/SelfService/</span></span><br /> <span data-ttu-id="d4b73-469">如果您沒有指定虛擬目錄，則會使用值 "SelfService"。</span><span class="sxs-lookup"><span data-stu-id="d4b73-469">If you do not specify a virtual directory, the value "SelfService" will be used.</span></span>|

10. <span data-ttu-id="d4b73-470">完成專案後，請選取 **[下一步**]。</span><span class="sxs-lookup"><span data-stu-id="d4b73-470">When you finish your entries, select **Next**.</span></span> <span data-ttu-id="d4b73-471">嚮導會檢查是否符合 web 應用程式的所有先決條件。</span><span class="sxs-lookup"><span data-stu-id="d4b73-471">The wizard checks that all prerequisites for the web applications are met.</span></span>

11. <span data-ttu-id="d4b73-472">選取 **[下一步]** 繼續。</span><span class="sxs-lookup"><span data-stu-id="d4b73-472">Select **Next** to continue.</span></span>

12. <span data-ttu-id="d4b73-473">在 [**摘要**] 頁面上，查看將新增的功能。</span><span class="sxs-lookup"><span data-stu-id="d4b73-473">On the **Summary** page, review the features that will be added.</span></span>

13. <span data-ttu-id="d4b73-474">選取 [**新增**]，將 web 應用程式新增至伺服器，然後選取 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="d4b73-474">Select **Add** to add the web applications to the server, and then select **Close**.</span></span>

## <span data-ttu-id="d4b73-475">在安裝 MBAM 2.5 server 軟體之後自訂和驗證步驟</span><span class="sxs-lookup"><span data-stu-id="d4b73-475">Customizing and validating steps after installing MBAM 2.5 server software</span></span>

### <span data-ttu-id="d4b73-476">步驟9：自訂貴組織的自助伺服器入口網站</span><span class="sxs-lookup"><span data-stu-id="d4b73-476">Step 9: Customizing the self-server portal for your organization</span></span>

<span data-ttu-id="d4b73-477">若要自訂自助式入口網站，只要新增自訂的指示文字、您的公司名稱、指向詳細資訊的指標等，請參閱[自訂貴組織的自助入口網站](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/customizing-the-self-service-portal-for-your-organization)。</span><span class="sxs-lookup"><span data-stu-id="d4b73-477">To customize the Self-Service Portal by adding custom notice text, your company name, pointers to more information, and so on, see [Customizing the Self-Service Portal for Your Organization](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/customizing-the-self-service-portal-for-your-organization).</span></span>
 
### <span data-ttu-id="d4b73-478">步驟10：如果用戶端電腦無法存取 CDN，請設定自助伺服器入口網站</span><span class="sxs-lookup"><span data-stu-id="d4b73-478">Step 10: Configure the self-server portal if client computers cannot access the CDN</span></span> 

<span data-ttu-id="d4b73-479">判斷您的用戶端電腦是否有權存取 Microsoft AJAX 內容傳遞網路（CDN）。</span><span class="sxs-lookup"><span data-stu-id="d4b73-479">Determine whether your client computers have access to the Microsoft AJAX Content Delivery Network (CDN).</span></span> <span data-ttu-id="d4b73-480">CDN 為自助入口網站提供對某些 JavaScript 檔案所需的存取權。</span><span class="sxs-lookup"><span data-stu-id="d4b73-480">The CDN gives the Self-Service Portal the access it requires to certain JavaScript files.</span></span> <span data-ttu-id="d4b73-481">如果您未在用戶端電腦無法存取 CDN 時設定自助入口網站，則只有公司名稱和使用者登入的帳戶才會顯示。</span><span class="sxs-lookup"><span data-stu-id="d4b73-481">If you don’t configure the Self-Service Portal when client computers cannot access the CDN, only the company name and the account under which the user signed in will be displayed.</span></span> <span data-ttu-id="d4b73-482">不會顯示任何錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="d4b73-482">No error message will be shown.</span></span>

<span data-ttu-id="d4b73-483">執行下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="d4b73-483">Do one of the following:</span></span>

* <span data-ttu-id="d4b73-484">如果您的用戶端電腦具有 CDN 的存取權，請執行任何動作。</span><span class="sxs-lookup"><span data-stu-id="d4b73-484">If your client computers have access to the CDN, do nothing.</span></span> <span data-ttu-id="d4b73-485">您的自助入口網站設定已完成。</span><span class="sxs-lookup"><span data-stu-id="d4b73-485">Your Self-Service Portal configuration is complete.</span></span>

* <span data-ttu-id="d4b73-486">如果您的用戶端電腦沒有 CDN 的存取權，請按照在[用戶端電腦無法存取 Microsoft 內容傳遞網路時，如何設定自助入口網站](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-configure-the-self-service-portal-when-client-computers-cannot-access-the-microsoft-content-delivery-network)中的步驟進行。</span><span class="sxs-lookup"><span data-stu-id="d4b73-486">If your client computers do not have access to the CDN, follow the steps in [How to Configure the Self-Service Portal When Client Computers Cannot Access the Microsoft Content Delivery Network](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-configure-the-self-service-portal-when-client-computers-cannot-access-the-microsoft-content-delivery-network).</span></span>

### <span data-ttu-id="d4b73-487">步驟11：驗證 MBAM 2.5 伺服器功能設定</span><span class="sxs-lookup"><span data-stu-id="d4b73-487">Step 11: Validate the MBAM 2.5 server feature configuration</span></span> 

<span data-ttu-id="d4b73-488">若要驗證您的 MBAM 伺服器部署以使用獨立拓撲，請遵循下列步驟。</span><span class="sxs-lookup"><span data-stu-id="d4b73-488">To validate your MBAM Server deployment to use the standalone topology, follow these steps.</span></span>

1. <span data-ttu-id="d4b73-489">在部署 MBAM 功能的每個伺服器上，選取 [**控制台**] 的 [程式  >  **Programs**  >  **和功能**]。</span><span class="sxs-lookup"><span data-stu-id="d4b73-489">On each server on which an MBAM feature is deployed, select **Control Panel** > **Programs** > **Programs and Features**.</span></span> <span data-ttu-id="d4b73-490">確認 [**程式和功能**] 清單中出現 [ **Microsoft BitLocker 管理及監視**]。</span><span class="sxs-lookup"><span data-stu-id="d4b73-490">Verify that **Microsoft BitLocker Administration and Monitoring** appears in the **Programs and Features** list.</span></span>
   > [!Note]
   > <span data-ttu-id="d4b73-491">若要執行驗證，您必須使用在每個伺服器上都有本機電腦管理認證的網域帳戶。</span><span class="sxs-lookup"><span data-stu-id="d4b73-491">To perform the validation, you must use a domain account that has local computer administrative credentials on each server.</span></span>

2. <span data-ttu-id="d4b73-492">在已設定復原資料庫的伺服器上，開啟 [SQL Server Management Studio]，然後確認已設定**MBAM 復原與硬體**資料庫。</span><span class="sxs-lookup"><span data-stu-id="d4b73-492">On the server on which the Recovery Database is configured, open SQL Server Management Studio, and verify that the **MBAM Recovery and Hardware** database is configured.</span></span>

3. <span data-ttu-id="d4b73-493">在已設定合規性和審核資料庫的伺服器 om 上，開啟 SQL Server Management Studio，然後確認已設定 MBAM 合規性狀態資料庫。</span><span class="sxs-lookup"><span data-stu-id="d4b73-493">On the server om which the Compliance and Audit Database is configured, open SQL Server Management Studio, and verify that the MBAM Compliance Status Database is configured.</span></span>

4. <span data-ttu-id="d4b73-494">在已設定報告功能的伺服器 onm 上，使用管理認證開啟網頁瀏覽器，然後流覽至 SQL Server Reporting Services 網站的首頁。</span><span class="sxs-lookup"><span data-stu-id="d4b73-494">On the server onm which the Reports feature is configured, open a web browser by using administrative credentials, and browse to the homepage of the SQL Server Reporting Services site.</span></span>
   
   <span data-ttu-id="d4b73-495">SQL Server Reporting Services 網站實例的預設首頁位置如下所示： HTTP （s）：：// *\<MBAM Reports Server Name\>* ： *\<port\>* /Reports.aspx</span><span class="sxs-lookup"><span data-stu-id="d4b73-495">The default homepage location of a SQL Server Reporting Services site instance is as follows: http(s)://*\<MBAM Reports Server Name\>*:*\<port\>*/Reports.aspx</span></span>
   
   <span data-ttu-id="d4b73-496">若要尋找實際的 URL，請使用 Reporting Services Configuration Manager 工具，然後選取您在安裝期間指定的實例。</span><span class="sxs-lookup"><span data-stu-id="d4b73-496">To find the actual URL, use the Reporting Services Configuration Manager tool, and select the instances that you specified during setup.</span></span>
   
5. <span data-ttu-id="d4b73-497">確認名為 Microsoft BitLocker 管理及監視的報表資料夾包含名為 MaltaDataSource 的資料來源。</span><span class="sxs-lookup"><span data-stu-id="d4b73-497">Verify that a reports folder that is named Microsoft BitLocker Administration and Monitoring contains a data source that is named MaltaDataSource.</span></span> <span data-ttu-id="d4b73-498">此資料來源包含的資料夾的名稱代表語言地區（例如，en-us）。</span><span class="sxs-lookup"><span data-stu-id="d4b73-498">This data source contains folders that have names that represent language locales (for example, en-us).</span></span> <span data-ttu-id="d4b73-499">報告位於 [語言] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="d4b73-499">The reports are in the language folders.</span></span>

   > [!Note]
   > <span data-ttu-id="d4b73-500">如果 SQL Server Reporting Services （SSRS）設定為命名實例，URL 應如下所示： HTTP （s）// \<MBAM Reports Server Name\> ： \<port\> /Reports_</span><span class="sxs-lookup"><span data-stu-id="d4b73-500">If SQL Server Reporting Services (SSRS) was configured as a named instance, the URL should resemble the following: http(s)://\<MBAM Reports Server Name\>:\<port\>/Reports_</span></span>\<SSRS Instance Name\>
   >
   > <span data-ttu-id="d4b73-501">如果未將 SSRS 設定為使用安全通訊端層（SSL），當您安裝 MBAM 伺服器時，報告的 URL 將會設定為 "HTTP"，而不是 "HTTPS"。</span><span class="sxs-lookup"><span data-stu-id="d4b73-501">If SSRS was not configured to use Secure Socket Layer (SSL), the URL for the reports will be set to "HTTP" instead of "HTTPS" when you install the MBAM server.</span></span> <span data-ttu-id="d4b73-502">如果您接著移至 [管理和監控] 網站（又稱為 [支援人員]）並選取報告，您會收到下列訊息：「只會顯示安全內容」。</span><span class="sxs-lookup"><span data-stu-id="d4b73-502">If you then go to the Administration and Monitoring Website (also known as Helpdesk) and select a report, you receive the following message: "Only Secure Content is Displayed."</span></span> <span data-ttu-id="d4b73-503">若要顯示報表，請選取 [**顯示所有內容**]。</span><span class="sxs-lookup"><span data-stu-id="d4b73-503">To show the report, select **Show All Content**.</span></span>

6. <span data-ttu-id="d4b73-504">在已設定 [管理及監視網站] 功能的伺服器上，執行 [伺服器管理員]，流覽至 [**角色**]，然後選取 [ **Web server （iis）**  >  **Internet information Services （IIS）** 管理員]。</span><span class="sxs-lookup"><span data-stu-id="d4b73-504">On the server on which the Administration and Monitoring Website feature is configured, run Server Manager, browse to **Roles**, and then select **Web Server (IIS)** > **Internet Information Services (IIS)** Manager.</span></span>

7. <span data-ttu-id="d4b73-505">在 **[連線] 中，** 流覽至 [網站]， \<computer name\> 然後選取 [**網站**  >  **Microsoft BitLocker 管理與監視**]。</span><span class="sxs-lookup"><span data-stu-id="d4b73-505">In **Connections**, browse to \<computer name\> and then select **Sites** > **Microsoft BitLocker Administration and Monitoring**.</span></span> <span data-ttu-id="d4b73-506">確認下列專案已列出：</span><span class="sxs-lookup"><span data-stu-id="d4b73-506">Verify that the following are listed:</span></span>

   * <span data-ttu-id="d4b73-507">MBAMAdministrationService</span><span class="sxs-lookup"><span data-stu-id="d4b73-507">MBAMAdministrationService</span></span>
   * <span data-ttu-id="d4b73-508">MBAMComplianceStatusService</span><span class="sxs-lookup"><span data-stu-id="d4b73-508">MBAMComplianceStatusService</span></span>
   * <span data-ttu-id="d4b73-509">MBAMRecoveryAndHardwareService</span><span class="sxs-lookup"><span data-stu-id="d4b73-509">MBAMRecoveryAndHardwareService</span></span>

8. <span data-ttu-id="d4b73-510">在已設定 [管理] 和 [監視] 和 [自助式入口網站] 的伺服器上，使用管理認證開啟網頁瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="d4b73-510">On the server on which the Administration and Monitoring Website and Self-Service Portal are configured, open a web browser by using administrative credentials.</span></span>

9. <span data-ttu-id="d4b73-511">流覽至下列網站，確認他們已順利載入：</span><span class="sxs-lookup"><span data-stu-id="d4b73-511">Browse to the following websites to verify that they load successfully:</span></span>
   * <span data-ttu-id="d4b73-512">HTTPs （s） \<MBAM Administration Server Name\> ：：//： \<port\> /HelpDesk/（請確認流覽和報告的每個連結）</span><span class="sxs-lookup"><span data-stu-id="d4b73-512">https(s)://\<MBAM Administration Server Name\>:\<port\>/HelpDesk/ (confirm each link for navigation and reports)</span></span>
   * <span data-ttu-id="d4b73-513">HTTP （s）：// \<MBAM Administration Server Name\> ： \<port\> /SelfService/</span><span class="sxs-lookup"><span data-stu-id="d4b73-513">http(s)://\<MBAM Administration Server Name\>:\<port\>/SelfService/</span></span>

   > [!Note]
   > <span data-ttu-id="d4b73-514">假設您已在不含網路加密的情況下，在預設埠上設定伺服器功能。</span><span class="sxs-lookup"><span data-stu-id="d4b73-514">It is assumed that you configured the server features on the default port without network encryption.</span></span> <span data-ttu-id="d4b73-515">如果您已將伺服器功能設定在不同的埠或虛擬目錄，請變更 Url，以包含適當的埠。</span><span class="sxs-lookup"><span data-stu-id="d4b73-515">If you configured the server features on a different port or virtual directory, change the URLs to include the appropriate port.</span></span> <span data-ttu-id="d4b73-516">例如： HTTP （s）// \<host name\> ： \<port\> /HelpDesk/HTTP （s）：// \<host name\> ： \<port\> / \<virtualdirectory\> /如果伺服器功能已設定為使用網路加密，請將 HTTP://變更為 HTTPs://。</span><span class="sxs-lookup"><span data-stu-id="d4b73-516">For example: http(s)://\<host name\>:\<port\>/HelpDesk/ http(s)://\<host name\>:\<port\>/\<virtualdirectory\>/ If the server features were configured to use network encryption, change http:// to https://.</span></span>
   
10. <span data-ttu-id="d4b73-517">流覽至下列 web 服務，確認他們已順利載入。</span><span class="sxs-lookup"><span data-stu-id="d4b73-517">Browse to the following web services to verify that they load successfully.</span></span> <span data-ttu-id="d4b73-518">隨即會開啟一個頁面，指出服務正在執行。</span><span class="sxs-lookup"><span data-stu-id="d4b73-518">A page opens to indicate that the service is running.</span></span> <span data-ttu-id="d4b73-519">不過，此頁面不會顯示中繼資料。</span><span class="sxs-lookup"><span data-stu-id="d4b73-519">However, the page displays no metadata.</span></span>

    * <span data-ttu-id="d4b73-520">HTTP （s）：// \<MBAM Administration Server Name> ： \<port> /MBAMAdministrationService/AdministrationService.svc</span><span class="sxs-lookup"><span data-stu-id="d4b73-520">http(s)://\<MBAM Administration Server Name>:\<port>/MBAMAdministrationService/AdministrationService.svc</span></span>
    * <span data-ttu-id="d4b73-521">HTTP （s）：// \<MBAM Administration Server Name> ： \<port> /MBAMUserSupportService/UserSupportService.svc</span><span class="sxs-lookup"><span data-stu-id="d4b73-521">http(s)://\<MBAM Administration Server Name>:\<port>/MBAMUserSupportService/UserSupportService.svc</span></span>
    * <span data-ttu-id="d4b73-522">HTTP （s）：// \<MBAM Administration Server Name> ： \<port> /MBAMComplianceStatusService/StatusReportingService.svc</span><span class="sxs-lookup"><span data-stu-id="d4b73-522">http(s)://\<MBAM Administration Server Name>:\<port>/MBAMComplianceStatusService/StatusReportingService.svc</span></span>
    * <span data-ttu-id="d4b73-523">HTTP （s）：// \<MBAM Administration Server Name> ： \<port> /MBAMRecoveryAndHardwareService/CoreService.svc</span><span class="sxs-lookup"><span data-stu-id="d4b73-523">http(s)://\<MBAM Administration Server Name>:\<port>/MBAMRecoveryAndHardwareService/CoreService.svc</span></span>

### <span data-ttu-id="d4b73-524">步驟12：設定 MBAM 群組原則範本</span><span class="sxs-lookup"><span data-stu-id="d4b73-524">Step 12: Configure the MBAM Group policy templates</span></span>

<span data-ttu-id="d4b73-525">若要部署 MBAM，您必須設定定義 BitLocker 磁片磁碟機加密之 MBAM 實現設定的 [組原則] 設定。</span><span class="sxs-lookup"><span data-stu-id="d4b73-525">To deploy MBAM, you have to set Group Policy settings that define MBAM implementation settings for BitLocker Drive Encryption.</span></span> <span data-ttu-id="d4b73-526">若要完成這項工作，您必須將 MBAM 群組原則範本複製到可執行群組原則管理主控台（GPMC）或高級群組原則管理（AGPM）的伺服器或工作站，然後編輯設定。</span><span class="sxs-lookup"><span data-stu-id="d4b73-526">To complete this task, you must copy the MBAM Group Policy templates to a server or workstation that can run Group Policy Management Console (GPMC) or Advanced Group Policy Management (AGPM), and then edit the settings.</span></span>

> [!Important]
> <span data-ttu-id="d4b73-527">請勿變更**BitLocker 磁片磁碟機加密**節點中的群組原則設定，否則 MBAM 將無法正常運作。</span><span class="sxs-lookup"><span data-stu-id="d4b73-527">Do not change the Group Policy settings in the **BitLocker Drive Encryption** node or MBAM will not work correctly.</span></span> <span data-ttu-id="d4b73-528">當您在**MDOP MBAM （BitLocker 管理）** 節點中設定群組原則設定時，MBAM 會自動為您設定**BitLocker 磁片磁碟機加密**設定。</span><span class="sxs-lookup"><span data-stu-id="d4b73-528">When you configure the Group Policy settings in the **MDOP MBAM (BitLocker Management)** node, MBAM automatically configures the **BitLocker Drive Encryption** settings for you.</span></span>
 
#### <span data-ttu-id="d4b73-529">複製 MBAM 2.5 群組原則範本</span><span class="sxs-lookup"><span data-stu-id="d4b73-529">Copying the MBAM 2.5 Group Policy templates</span></span>

<span data-ttu-id="d4b73-530">在您安裝 MBAM 用戶端之前，您必須將 MBAM 專用的群組原則物件（Gpo）複製到管理工作站。</span><span class="sxs-lookup"><span data-stu-id="d4b73-530">Before you install the MBAM Client, you must copy MBAM-specific Group Policy Objects (GPOs) to the management workstation.</span></span> <span data-ttu-id="d4b73-531">這些 Gpo 定義 BitLocker 的 MBAM 實現設定。</span><span class="sxs-lookup"><span data-stu-id="d4b73-531">These GPOs define MBAM implementation settings for BitLocker.</span></span> <span data-ttu-id="d4b73-532">您可以將群組原則範本複製到所有受支援 Windows 型伺服器或用戶端電腦的伺服器或工作站，而且可以執行群組原則管理主控台（GPMC）或高級群組原則管理（AGPM）。</span><span class="sxs-lookup"><span data-stu-id="d4b73-532">You can copy the Group Policy templates to any server or workstation that is a supported Windows-based server or client computer and that can run the Group Policy Management Console (GPMC) or Advanced Group Policy Management (AGPM).</span></span>

<span data-ttu-id="d4b73-533">如需詳細資訊，請參閱[複製 MBAM 2.5 群組原則範本](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/copying-the-mbam-25-group-policy-templates)。</span><span class="sxs-lookup"><span data-stu-id="d4b73-533">For more information, see [Copying the MBAM 2.5 Group Policy Templates](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/copying-the-mbam-25-group-policy-templates).</span></span>
 
#### <span data-ttu-id="d4b73-534">編輯 MBAM 2.5 GPO 設定</span><span class="sxs-lookup"><span data-stu-id="d4b73-534">Editing MBAM 2.5 GPO settings</span></span>

<span data-ttu-id="d4b73-535">在您建立必要的 Gpo 之後，您必須將 MBAM 群組原則設定部署到貴組織的用戶端電腦。</span><span class="sxs-lookup"><span data-stu-id="d4b73-535">After you create the necessary GPOs, you must deploy the MBAM Group Policy settings to your organization’s client computers.</span></span> <span data-ttu-id="d4b73-536">若要查看和建立 Gpo，您必須已安裝群組原則管理主控台（GPMC）或高級群組原則管理（AGPM）。</span><span class="sxs-lookup"><span data-stu-id="d4b73-536">To view and create GPOs, you must have Group Policy Management Console (GPMC) or Advanced Group Policy Management (AGPM) installed.</span></span>

<span data-ttu-id="d4b73-537">如需詳細資訊，請參閱[編輯 MBAM 2.5 群組原則設定](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/editing-the-mbam-25-group-policy-settings)及[規劃 MBAM 2.5 群組原則需求](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-for-mbam-25-group-policy-requirements)。</span><span class="sxs-lookup"><span data-stu-id="d4b73-537">For more information, see [Editing the MBAM 2.5 Group Policy Settings](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/editing-the-mbam-25-group-policy-settings) and [Planning for MBAM 2.5 Group Policy Requirements](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-for-mbam-25-group-policy-requirements).</span></span>
 
### <span data-ttu-id="d4b73-538">步驟13：部署 MBAM 2.5 用戶端</span><span class="sxs-lookup"><span data-stu-id="d4b73-538">Step 13: Deploying the MBAM 2.5 Client</span></span>

<span data-ttu-id="d4b73-539">視您部署 Microsoft BitLocker 管理和監視用戶端軟體的情況而定，您可以在使用者接收電腦前，或在此後使用企業軟體部署系統來部署 MBAM 用戶端軟體，在您組織的電腦上啟用 BitLocker。</span><span class="sxs-lookup"><span data-stu-id="d4b73-539">Depending on when you deploy the Microsoft BitLocker Administration and Monitoring Client software, you can enable BitLocker on a computer in your organization either before the user receives the computer or afterward by configuring Group Policy and deploying the MBAM Client software by using an enterprise software deployment system.</span></span>
 
#### <span data-ttu-id="d4b73-540">將 MBAM 用戶端部署到桌上型電腦或可擕式電腦</span><span class="sxs-lookup"><span data-stu-id="d4b73-540">Deploy the MBAM Client to desktop or portable computers</span></span>

<span data-ttu-id="d4b73-541">在您設定群組原則設定之後，您可以使用企業軟體部署系統產品（例如 Microsoft System Center 2012 Configuration Manager 或 Active Directory 網域服務（AD DS）），將 MBAM 用戶端安裝 Windows 安裝程式檔案部署至目的電腦。</span><span class="sxs-lookup"><span data-stu-id="d4b73-541">After you configure Group Policy settings, you can use an enterprise software deployment system product such as Microsoft System Center 2012 Configuration Manager or Active Directory Domain Services (AD DS) to deploy the MBAM client installation Windows Installer files to target computers.</span></span> <span data-ttu-id="d4b73-542">您可以使用32位或64位 MbamClientSetup.exe 檔案，或是32位或64位 MBAMClient.msi 檔案。</span><span class="sxs-lookup"><span data-stu-id="d4b73-542">You can use either the 32-bit or 64-bit MbamClientSetup.exe files or the 32-bit or 64-bit MBAMClient.msi files.</span></span> <span data-ttu-id="d4b73-543">這些與 MBAM 用戶端軟體一起提供。</span><span class="sxs-lookup"><span data-stu-id="d4b73-543">These are provided together with the MBAM Client software.</span></span>

<span data-ttu-id="d4b73-544">如需詳細資訊，請參閱[如何將 MBAM 用戶端部署到桌上型電腦或膝上型電腦](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-deploy-the-mbam-client-to-desktop-or-laptop-computers-mbam-25)。</span><span class="sxs-lookup"><span data-stu-id="d4b73-544">For more information, see [How to Deploy the MBAM Client to Desktop or Laptop Computers](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-deploy-the-mbam-client-to-desktop-or-laptop-computers-mbam-25).</span></span>
 
#### <span data-ttu-id="d4b73-545">部署 MBAM 用戶端做為 Windows 部署的一部分</span><span class="sxs-lookup"><span data-stu-id="d4b73-545">Deploy the MBAM Client as part of a Windows deployment</span></span>

<span data-ttu-id="d4b73-546">在已集中接收和設定電腦的組織中，您可以安裝 MBAM 用戶端，在每個電腦上管理 BitLocker 磁碟機加密，然後再寫入任何使用者資料。</span><span class="sxs-lookup"><span data-stu-id="d4b73-546">In organizations in which computers are received and configured centrally, you can install the MBAM Client to manage BitLocker Drive Encryption on each computer before any user data is written to it.</span></span> <span data-ttu-id="d4b73-547">此程式的優點是，每個電腦都符合 BitLocker 規範。</span><span class="sxs-lookup"><span data-stu-id="d4b73-547">The benefit of this process is that every computer is then BitLocker-compliant.</span></span> <span data-ttu-id="d4b73-548">這個方法不依賴使用者的動作，因為系統管理員已經將電腦加密。</span><span class="sxs-lookup"><span data-stu-id="d4b73-548">This method does not rely on user action because the administrator has already encrypted the computer.</span></span> <span data-ttu-id="d4b73-549">這個案例的主要假設是組織原則是在電腦傳送給使用者之前，先安裝公司的 Windows 影像。</span><span class="sxs-lookup"><span data-stu-id="d4b73-549">A key assumption for this scenario is that the policy of the organization is to install a corporate Windows image before the computer is delivered to the user.</span></span> <span data-ttu-id="d4b73-550">如果將群組原則設定設定為 [需要 PIN]，系統會在收到原則之後提示使用者設定 PIN。</span><span class="sxs-lookup"><span data-stu-id="d4b73-550">If the Group Policy settings are configured to require a PIN, users are prompted to set a PIN after they receive the policy.</span></span>

<span data-ttu-id="d4b73-551">如需詳細資訊，請參閱[如何在 Windows 部署中部署 MBAM 用戶端](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-enable-bitlocker-by-using-mbam-as-part-of-a-windows-deploymentmbam-25)。</span><span class="sxs-lookup"><span data-stu-id="d4b73-551">For more information, see [How to Deploy the MBAM Client as Part of a Windows Deployment](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-enable-bitlocker-by-using-mbam-as-part-of-a-windows-deploymentmbam-25).</span></span>
 
#### <span data-ttu-id="d4b73-552">如何使用命令列部署 MBAM 用戶端</span><span class="sxs-lookup"><span data-stu-id="d4b73-552">How to deploy the MBAM Client by using a command line</span></span>

<span data-ttu-id="d4b73-553">如需詳細資訊，請參閱[如何使用命令列部署 MBAM 用戶端](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-deploy-the-mbam-client-by-using-a-command-line)。</span><span class="sxs-lookup"><span data-stu-id="d4b73-553">For more information see [How to Deploy the MBAM Client by Using a Command Line](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/how-to-deploy-the-mbam-client-by-using-a-command-line).</span></span>

#### <span data-ttu-id="d4b73-554">用戶端部署之後</span><span class="sxs-lookup"><span data-stu-id="d4b73-554">Post-deployment of clients</span></span>

<span data-ttu-id="d4b73-555">現在您已完成部署活動，您應該查看下列記錄，並判斷用戶端是否已成功向 MBAM 資料庫報告。</span><span class="sxs-lookup"><span data-stu-id="d4b73-555">Now that you have finished the deployment activity, you should review the following logs and determine whether the clients are reporting successfully to the MBAM database.</span></span>

## <span data-ttu-id="d4b73-556">常見問題集</span><span class="sxs-lookup"><span data-stu-id="d4b73-556">FAQ</span></span>

### <span data-ttu-id="d4b73-557">如何建立負載平衡的 IIS 伺服器</span><span class="sxs-lookup"><span data-stu-id="d4b73-557">How to create a Load balanced IIS servers</span></span>

* <span data-ttu-id="d4b73-558">SPN 必須只登錄到易記的名稱（例如： bitlocker.corp.net），而且不能登錄到個別的 IIS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="d4b73-558">SPN must be registered only to the friendly name (for example: bitlocker.corp.net), and must not be registered to individual IIS servers.</span></span>

* <span data-ttu-id="d4b73-559">如果使用了憑證，憑證必須在 [匯入平衡] 群組中的所有 IIS 伺服器的 [ **Subject 替換名稱**] 欄位中，輸入 FQDN 和 NetBIOS 名稱，也就是易記的名稱（例如： bitlocker.corp.net）。</span><span class="sxs-lookup"><span data-stu-id="d4b73-559">If a certificate is used, the certificate must have both FQDN and NetBIOS names entered into the **Subject Alternative Name** field for all IIS servers in the load balance group and also as the Friendly Name (for example: bitlocker.corp.net).</span></span> <span data-ttu-id="d4b73-560">否則，當您流覽負載平衡位址時，瀏覽器就會將憑證報告為不受信任。</span><span class="sxs-lookup"><span data-stu-id="d4b73-560">Otherwise, the certificate will be reported as not trusted by the browser when you browse load-balanced addresses.</span></span>

<span data-ttu-id="d4b73-561">如需詳細資訊，請參閱[IIS 網路負載平衡](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-for-mbam-25-high-availability#a-href-idbkmk-load-balanceaiis-network-load-balancing)及[註冊應用程式池帳戶的 spn](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-how-to-secure-the-mbam-websites#registering-spns-for-the-application-pool-account)。</span><span class="sxs-lookup"><span data-stu-id="d4b73-561">For more information, see [IIS Network Load Balancing](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-for-mbam-25-high-availability#a-href-idbkmk-load-balanceaiis-network-load-balancing) and [Registering SPNs for the application pool account](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-how-to-secure-the-mbam-websites#registering-spns-for-the-application-pool-account).</span></span>

### <span data-ttu-id="d4b73-562">如何設定憑證</span><span class="sxs-lookup"><span data-stu-id="d4b73-562">How to configure a certificate</span></span>

* <span data-ttu-id="d4b73-563">您必須有兩個憑證。</span><span class="sxs-lookup"><span data-stu-id="d4b73-563">You’ll have to have two certificates.</span></span> <span data-ttu-id="d4b73-564">其中一個證書用於 SQL server，另一個用於 IIS。</span><span class="sxs-lookup"><span data-stu-id="d4b73-564">One certificate is used for SQL server, and the other is used for IIS.</span></span> <span data-ttu-id="d4b73-565">啟動 MBAM 安裝之前，必須先安裝它們。</span><span class="sxs-lookup"><span data-stu-id="d4b73-565">They must be installed before starting MBAM installation.</span></span>

* <span data-ttu-id="d4b73-566">我們建議您使用安裝程式將憑證新增至 IIS 配置，而不是手動編輯 web.config 檔案。</span><span class="sxs-lookup"><span data-stu-id="d4b73-566">We recommend that you use the installer to add the certificate to the IIS configuration instead of manually editing the web.config file.</span></span>

* <span data-ttu-id="d4b73-567">如果憑證上的「頒發給」欄位與伺服器的名稱不相符，則 MBAM 配置器就不會接受證書。</span><span class="sxs-lookup"><span data-stu-id="d4b73-567">The certificate will not be accepted by the MBAM Configurator if the “Issued To” field on the certificate does not match the name of the server.</span></span> <span data-ttu-id="d4b73-568">在這種情況下，暫時從 IIS 主控台建立自我簽署憑證，然後在配置器中使用它。</span><span class="sxs-lookup"><span data-stu-id="d4b73-568">In this case, temporarily create a self-signed certificate from the IIS Console, and use it in the Configurator.</span></span> <span data-ttu-id="d4b73-569">這會讓 nsure 針對 SSL 和 HTTPS 安裝 Web 應用程式。</span><span class="sxs-lookup"><span data-stu-id="d4b73-569">This will make nsure that the Web Apps are installed for SSL and HTTPS.</span></span> <span data-ttu-id="d4b73-570">之後，您可以將證書從 MBAM 網站的 IIS 系結變更為另一個。</span><span class="sxs-lookup"><span data-stu-id="d4b73-570">After that, you can change the certificate to one from IIS bindings for the MBAM Website.</span></span>

### <span data-ttu-id="d4b73-571">安裝的 SQL 許可權需求</span><span class="sxs-lookup"><span data-stu-id="d4b73-571">The SQL permissions requirement for installation</span></span>

<span data-ttu-id="d4b73-572">為 MBAM 應用程式池建立帳戶，並僅提供 SecurityAdmin、Public 和 DBCreator 許可權。</span><span class="sxs-lookup"><span data-stu-id="d4b73-572">Create an account for MBAM App Pool, and give it only SecurityAdmin, Public, and DBCreator permissions.</span></span>

<span data-ttu-id="d4b73-573">如需詳細資訊，請參閱[MBAM 資料庫配置–最低許可權](https://blogs.technet.microsoft.com/dubaisec/2016/02/02/mbam-database-configuration-minimum-permissions/)。</span><span class="sxs-lookup"><span data-stu-id="d4b73-573">See [MBAM Database configuration – minimum permissions](https://blogs.technet.microsoft.com/dubaisec/2016/02/02/mbam-database-configuration-minimum-permissions/) for more information.</span></span>

> [!Note]
> * <span data-ttu-id="d4b73-574">在某些情況下，初始安裝和升級作業需要有更多許可權。</span><span class="sxs-lookup"><span data-stu-id="d4b73-574">In some situations, more permissions are required for the initial installation and upgrade operations.</span></span>
> * <span data-ttu-id="d4b73-575">使用具有暫時 SA 的帳戶進行安裝。</span><span class="sxs-lookup"><span data-stu-id="d4b73-575">Use an account that has temporary SA for the installation.</span></span>
> * <span data-ttu-id="d4b73-576">請勿在沒有足夠許可權來變更 SQL Server 的使用者帳戶內容中啟動配置器，因為這會造成安裝錯誤。</span><span class="sxs-lookup"><span data-stu-id="d4b73-576">Do not start the Configurator in the context of a user account (Run As) that does not have enough permissions to make changes to SQL Server because this will cause installation errors.</span></span>
> * <span data-ttu-id="d4b73-577">您必須使用在 SQL Server 上擁有許可權的帳戶登入。</span><span class="sxs-lookup"><span data-stu-id="d4b73-577">You must be logged on by using an account that has permissions on SQL Server.</span></span> <span data-ttu-id="d4b73-578">您可以透過遠端執行 MBAM 配置器來建立或更新 SQL Server 資料庫。</span><span class="sxs-lookup"><span data-stu-id="d4b73-578">Only SQL Server databases can be created or updated by running MBAM Configurator remotely.</span></span> <span data-ttu-id="d4b73-579">若是 SSRS server，您必須安裝 MBAM 並在本機執行配置程式，才能安裝或更新 MBAM SSRS 報告。</span><span class="sxs-lookup"><span data-stu-id="d4b73-579">For SSRS server, you must install MBAM and run Configurator locally to install or update the MBAM SSRS reports.</span></span>

### <span data-ttu-id="d4b73-580">SPN 註冊所需的許可權</span><span class="sxs-lookup"><span data-stu-id="d4b73-580">The permission required for SPN Registration</span></span>

<span data-ttu-id="d4b73-581">用於 IIS 入口安裝的帳戶必須具有寫入 ServicePrincipalName 並寫入驗證的 SPN 許可權。</span><span class="sxs-lookup"><span data-stu-id="d4b73-581">An account that's used for IIS portal installation must have Write ServicePrincipalName and Write Validated SPN permissions.</span></span> <span data-ttu-id="d4b73-582">如果沒有這些許可權，安裝會傳回一則警告訊息，指出它無法註冊 SPN。</span><span class="sxs-lookup"><span data-stu-id="d4b73-582">Without these permissions, the installation will return a warning message that states that it cannot register the SPN.</span></span>

> [!Note]
> <span data-ttu-id="d4b73-583">您將會收到這則警告訊息兩次。</span><span class="sxs-lookup"><span data-stu-id="d4b73-583">You will this receive this warning message twice.</span></span> <span data-ttu-id="d4b73-584">這並不表示 SPN 必須有兩個註冊物件。</span><span class="sxs-lookup"><span data-stu-id="d4b73-584">This does not mean that the SPN must have two objects registered to it.</span></span>

<span data-ttu-id="d4b73-585">如需詳細資訊，請參閱[MBAM 安裝失敗，並顯示「註冊 SPN 延遲」的錯誤訊息](https://support.microsoft.com/help/2754138/)。</span><span class="sxs-lookup"><span data-stu-id="d4b73-585">For more information, see [MBAM Setup fails with “Register SPN Deferred” error message](https://support.microsoft.com/help/2754138/).</span></span>

### <span data-ttu-id="d4b73-586">我是否需要將 ADMX 範本更新為最新版本？</span><span class="sxs-lookup"><span data-stu-id="d4b73-586">Did I have to update the ADMX templates to the latest version?</span></span>

<span data-ttu-id="d4b73-587">在您將 ADMX 範本更新為其最新版本之後，您會在 GPO 的 [MBAM 根節點] 中看到多個 OS 選項。</span><span class="sxs-lookup"><span data-stu-id="d4b73-587">You'll see multiple OS options in the MBAM root node for GPO after you update the ADMX templates to their latest versions.</span></span> <span data-ttu-id="d4b73-588">例如，Windows 7、Windows 8.1、Windows 10 版本1511及更新版本。</span><span class="sxs-lookup"><span data-stu-id="d4b73-588">For example, Windows 7, Windows 8.1, and Windows 10, version 1511 and later versions.</span></span>

<span data-ttu-id="d4b73-589">如需如何更新 ADMX 範本的詳細資訊，請參閱下列文章：</span><span class="sxs-lookup"><span data-stu-id="d4b73-589">For more information about how to update the ADMX templates, see the following articles:</span></span>
* [<span data-ttu-id="d4b73-590">如何下載及部署 MDOP 群組原則 (.admx) 範本</span><span class="sxs-lookup"><span data-stu-id="d4b73-590">How to Download and Deploy MDOP Group Policy (.admx) Templates</span></span>](https://docs.microsoft.com/microsoft-desktop-optimization-pack/solutions/how-to-download-and-deploy-mdop-group-policy--admx--templates)
* [<span data-ttu-id="d4b73-591">MBAM 2.5 群組原則需求規劃</span><span class="sxs-lookup"><span data-stu-id="d4b73-591">Planning for MBAM 2.5 Group Policy Requirements</span></span>](https://docs.microsoft.com/microsoft-desktop-optimization-pack/mbam-v25/planning-for-mbam-25-group-policy-requirements)
* [<span data-ttu-id="d4b73-592">Microsoft 桌面優化套件群群組原則管理範本</span><span class="sxs-lookup"><span data-stu-id="d4b73-592">Microsoft Desktop Optimization Pack Group Policy Administrative Templates</span></span>](https://www.microsoft.com/en-us/download/details.aspx?id=55531)
