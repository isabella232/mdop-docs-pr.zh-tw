---
title: 驗證 MBAM 2.5 伺服器功能設定
description: 驗證 MBAM 2.5 伺服器功能設定
author: dansimp
ms.assetid: f4983a33-ce18-4186-a471-dd6415940504
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f955e0b9ccb7952995574e4aa981674f7c7667fe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812141"
---
# <span data-ttu-id="3bff8-103">驗證 MBAM 2.5 伺服器功能設定</span><span class="sxs-lookup"><span data-stu-id="3bff8-103">Validating the MBAM 2.5 Server Feature Configuration</span></span>


<span data-ttu-id="3bff8-104">當您完成 Microsoft BitLocker 管理和監控（MBAM） 2.5 Server 功能部署時，建議您驗證部署，以確保所有功能都已成功設定。</span><span class="sxs-lookup"><span data-stu-id="3bff8-104">When you finish the Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 Server feature deployment, we recommend that you validate the deployment to ensure that all features have been successfully configured.</span></span> <span data-ttu-id="3bff8-105">使用與您部署的拓撲（獨立或系統中心 Configuration Manager 整合）相符的程式。</span><span class="sxs-lookup"><span data-stu-id="3bff8-105">Use the procedure that matches the topology (Stand-alone or System Center Configuration Manager Integration) that you deployed.</span></span>

## <span data-ttu-id="3bff8-106">使用獨立拓朴驗證 MBAM 伺服器部署</span><span class="sxs-lookup"><span data-stu-id="3bff8-106">Validating the MBAM Server deployment with the Stand-alone topology</span></span>


<span data-ttu-id="3bff8-107">使用下列步驟，透過獨立拓朴驗證您的 MBAM 伺服器部署。</span><span class="sxs-lookup"><span data-stu-id="3bff8-107">Use the following steps to validate your MBAM Server deployment with the Stand-alone topology.</span></span>

**<span data-ttu-id="3bff8-108">驗證獨立的 MBAM 伺服器部署</span><span class="sxs-lookup"><span data-stu-id="3bff8-108">To validate a Stand-alone MBAM Server deployment</span></span>**

1.  <span data-ttu-id="3bff8-109">在部署 MBAM 功能的每個伺服器上，按一下 [**控制台**] 中的 [程式 &gt; **Programs** &gt; **和功能**]。</span><span class="sxs-lookup"><span data-stu-id="3bff8-109">On each server where an MBAM feature is deployed, click **Control Panel** &gt; **Programs** &gt; **Programs and Features**.</span></span> <span data-ttu-id="3bff8-110">確認 [**程式和功能**] 清單中出現 [ **Microsoft BitLocker 管理及監視**]。</span><span class="sxs-lookup"><span data-stu-id="3bff8-110">Verify that **Microsoft BitLocker Administration and Monitoring** appears in the **Programs and Features** list.</span></span>

    **<span data-ttu-id="3bff8-111">注意</span><span class="sxs-lookup"><span data-stu-id="3bff8-111">Note</span></span>**  
    <span data-ttu-id="3bff8-112">若要進行驗證，您必須使用在每個伺服器上都有本機電腦管理認證的網域帳戶。</span><span class="sxs-lookup"><span data-stu-id="3bff8-112">To do the validation, you must use a domain account that has local computer administrative credentials on each server.</span></span>



2.  <span data-ttu-id="3bff8-113">在已設定恢復資料庫的伺服器上，開啟 SQL Server Management Studio，並確認已設定**MBAM 復原與硬體**資料庫。</span><span class="sxs-lookup"><span data-stu-id="3bff8-113">On the server where the Recovery Database is configured, open SQL Server Management Studio and verify that the **MBAM Recovery and Hardware** database is configured.</span></span>

3.  <span data-ttu-id="3bff8-114">在已設定合規性和審核資料庫的伺服器上，開啟 SQL Server Management Studio 並確認已設定**MBAM 合規性狀態資料庫**。</span><span class="sxs-lookup"><span data-stu-id="3bff8-114">On the server where the Compliance and Audit Database is configured, open SQL Server Management Studio and verify that the **MBAM Compliance Status Database** is configured.</span></span>

4.  <span data-ttu-id="3bff8-115">在已設定 [報表] 功能的伺服器上，使用系統管理認證開啟網頁瀏覽器，然後流覽至 SQL Server Reporting Services 網站的 "Home"。</span><span class="sxs-lookup"><span data-stu-id="3bff8-115">On the server where the Reports feature is configured, open a web browser with administrative credentials and browse to the "Home" of the SQL Server Reporting Services site.</span></span>

    <span data-ttu-id="3bff8-116">SQL Server Reporting Services 網站實例的預設首頁位置是：</span><span class="sxs-lookup"><span data-stu-id="3bff8-116">The default Home location of a SQL Server Reporting Services site instance is at:</span></span>

    <span data-ttu-id="3bff8-117">HTTP （s）// &lt; *MBAMReportsServerName* &gt; ： &lt; *埠* &gt; /Reports.aspx</span><span class="sxs-lookup"><span data-stu-id="3bff8-117">http(s)://&lt; *MBAMReportsServerName*&gt;:&lt;*port*&gt;/Reports.aspx</span></span>

    <span data-ttu-id="3bff8-118">若要尋找實際的 URL，請使用 Reporting Services Configuration Manager 工具，然後選取您在安裝期間指定的實例。</span><span class="sxs-lookup"><span data-stu-id="3bff8-118">To find the actual URL, use the Reporting Services Configuration Manager tool and select the instances that you specified during setup.</span></span>

5.  <span data-ttu-id="3bff8-119">確認名為**Microsoft BitLocker 管理和監視**的報表資料夾包含名為**MaltaDataSource**及語言資料夾的資料來源。</span><span class="sxs-lookup"><span data-stu-id="3bff8-119">Confirm that a reports folder named **Microsoft BitLocker Administration and Monitoring** contains a data source called **MaltaDataSource** as well as the language folders.</span></span> <span data-ttu-id="3bff8-120">資料來源包含的資料夾的名稱代表語言（例如，en-us）。</span><span class="sxs-lookup"><span data-stu-id="3bff8-120">The data source contains folders with names that represent languages (for example, en-us).</span></span> <span data-ttu-id="3bff8-121">報告位於 [語言] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="3bff8-121">The reports are in the language folders.</span></span>

    **<span data-ttu-id="3bff8-122">注意</span><span class="sxs-lookup"><span data-stu-id="3bff8-122">Note</span></span>**  
    <span data-ttu-id="3bff8-123">如果 SQL Server Reporting Services （SSRS）設定為命名實例，URL 應如下所示： HTTP （s）// &lt; *MBAMReportsServerName* &gt; ： &lt; *port* &gt; /Reports\_ &lt; *SSRSInstanceName*&gt;</span><span class="sxs-lookup"><span data-stu-id="3bff8-123">If SQL Server Reporting Services (SSRS) was configured as a named instance, the URL should resemble the following: http(s)://&lt; *MBAMReportsServerName*&gt;:&lt;*port*&gt;/Reports\_&lt;*SSRSInstanceName*&gt;</span></span>



~~~
**Note**  
If SSRS was not configured to use Secure Socket Layer (SSL), the URL for the reports will be set to HTTP instead of HTTPS when you install the MBAM Server. If you then go to the Administration and Monitoring Website (also known as Help Desk) and select a report, the following message appears: "Only Secure Content is Displayed." To show the report, click **Show All Content**.
~~~



6. <span data-ttu-id="3bff8-124">在已設定 [管理及監視網站] 功能的伺服器上，執行 [**伺服器管理員**]，流覽至 [**角色**]，然後選取 [ **Web server （iis）** &gt; **Internet information Services （IIS）管理員**]。</span><span class="sxs-lookup"><span data-stu-id="3bff8-124">On the server where the Administration and Monitoring Website feature is configured, run **Server Manager**, browse to **Roles**, and then select **Web Server (IIS)** &gt; **Internet Information Services (IIS) Manager**.</span></span>

7. <span data-ttu-id="3bff8-125">在 [連線] 中，流覽至 [ \* &lt; 電腦名稱稱 &gt; \* **]，然後**選取 [**網站** &gt; **Microsoft BitLocker 管理及監視**]。</span><span class="sxs-lookup"><span data-stu-id="3bff8-125">In **Connections**, browse to *&lt;computer name&gt;* and select **Sites** &gt; **Microsoft BitLocker Administration and Monitoring**.</span></span> <span data-ttu-id="3bff8-126">確認下列專案已列出：</span><span class="sxs-lookup"><span data-stu-id="3bff8-126">Verify that the following are listed:</span></span>

   -   **<span data-ttu-id="3bff8-127">MBAMAdministrationService</span><span class="sxs-lookup"><span data-stu-id="3bff8-127">MBAMAdministrationService</span></span>**

   -   **<span data-ttu-id="3bff8-128">MBAMComplianceStatusService</span><span class="sxs-lookup"><span data-stu-id="3bff8-128">MBAMComplianceStatusService</span></span>**

   -   **<span data-ttu-id="3bff8-129">MBAMRecoveryAndHardwareService</span><span class="sxs-lookup"><span data-stu-id="3bff8-129">MBAMRecoveryAndHardwareService</span></span>**

8. <span data-ttu-id="3bff8-130">在已設定 [管理] 和 [監視] 網站及自助服務入口網站的伺服器上，使用系統管理認證開啟網頁瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="3bff8-130">On the server where the Administration and Monitoring Website and Self-Service Portal are configured, open a web browser with administrative credentials.</span></span>

9. <span data-ttu-id="3bff8-131">流覽至下列網站，確認他們已順利載入：</span><span class="sxs-lookup"><span data-stu-id="3bff8-131">Browse to the following websites to verify that they load successfully:</span></span>

   -   <span data-ttu-id="3bff8-132">HTTPs （s）// &lt; *MBAMAdministrationServerName* &gt; ： &lt; *port* &gt; /HelpDesk/-確認流覽與報告的每個連結</span><span class="sxs-lookup"><span data-stu-id="3bff8-132">https(s)://&lt;*MBAMAdministrationServerName*&gt;:&lt;*port*&gt;/HelpDesk/ - confirm each of the links for navigation and reports</span></span>

   -   <span data-ttu-id="3bff8-133">HTTP （s）// &lt; *MBAMAdministrationServerName* &gt; ： &lt; *埠* &gt; /SelfService/</span><span class="sxs-lookup"><span data-stu-id="3bff8-133">http(s)://&lt; *MBAMAdministrationServerName*&gt;:&lt;*port*&gt;/SelfService/</span></span>

   **<span data-ttu-id="3bff8-134">注意</span><span class="sxs-lookup"><span data-stu-id="3bff8-134">Note</span></span>**  
   <span data-ttu-id="3bff8-135">假設您已在不含網路加密的情況下，在預設埠上設定伺服器功能。</span><span class="sxs-lookup"><span data-stu-id="3bff8-135">It is assumed that you configured the server features on the default port without network encryption.</span></span> <span data-ttu-id="3bff8-136">如果您已將伺服器功能設定在不同的埠或虛擬目錄，請將 Url 變更為包含適當的埠，例如：</span><span class="sxs-lookup"><span data-stu-id="3bff8-136">If you configured the server features on a different port or virtual directory, change the URLs to include the appropriate port, for example:</span></span>

   <span data-ttu-id="3bff8-137">HTTP （s）// &lt; *主機名稱* &gt; ： &lt; *埠* &gt; /HelpDesk/</span><span class="sxs-lookup"><span data-stu-id="3bff8-137">http(s)://&lt; *host name*&gt;:&lt;*port*&gt;/HelpDesk/</span></span>

   <span data-ttu-id="3bff8-138">HTTP （s）// &lt; *主機名稱* &gt; ： &lt; *埠* &gt; / &lt; *virtualdirectory*&gt;/</span><span class="sxs-lookup"><span data-stu-id="3bff8-138">http(s)://&lt; *host name*&gt;:&lt;*port*&gt;/&lt;*virtualdirectory*&gt;/</span></span>

   <span data-ttu-id="3bff8-139">如果伺服器功能已設定網路加密，請將 HTTP://變更為 HTTPs://。</span><span class="sxs-lookup"><span data-stu-id="3bff8-139">If the server features were configured with network encryption, change http:// to https://.</span></span>



10. <span data-ttu-id="3bff8-140">流覽至下列 web 服務，確認他們已順利載入。</span><span class="sxs-lookup"><span data-stu-id="3bff8-140">Browse to the following web services to verify that they load successfully.</span></span> <span data-ttu-id="3bff8-141">隨即會開啟一個頁面，指出服務正在執行，但頁面不會顯示任何中繼資料。</span><span class="sxs-lookup"><span data-stu-id="3bff8-141">A page opens to indicate that the service is running, but the page does not display any metadata.</span></span>

    -   <span data-ttu-id="3bff8-142">HTTP （s）// &lt; *MBAMAdministrationServerName* &gt; ： &lt; *埠* &gt; /MBAMAdministrationService/AdministrationService.svc</span><span class="sxs-lookup"><span data-stu-id="3bff8-142">http(s)://&lt; *MBAMAdministrationServerName*&gt;:&lt;*port*&gt;/MBAMAdministrationService/AdministrationService.svc</span></span>

    -   <span data-ttu-id="3bff8-143">HTTP （s）// &lt; *MBAMAdministrationServerName* &gt; ： &lt; *埠* &gt; /MBAMUserSupportService/UserSupportService.svc</span><span class="sxs-lookup"><span data-stu-id="3bff8-143">http(s)://&lt; *MBAMAdministrationServerName*&gt;:&lt;*port*&gt;/MBAMUserSupportService/UserSupportService.svc</span></span>

    -   <span data-ttu-id="3bff8-144">HTTP （s）// &lt; *MBAMAdministrationServerName* &gt; ： &lt; *埠* &gt; /MBAMComplianceStatusService/StatusReportingService.svc</span><span class="sxs-lookup"><span data-stu-id="3bff8-144">http(s)://&lt; *MBAMAdministrationServerName*&gt;:&lt;*port*&gt;/MBAMComplianceStatusService/StatusReportingService.svc</span></span>

    -   <span data-ttu-id="3bff8-145">HTTP （s）// &lt; *MBAMAdministrationServerName* &gt; ： &lt; *埠* &gt; /MBAMRecoveryAndHardwareService/CoreService.svc</span><span class="sxs-lookup"><span data-stu-id="3bff8-145">http(s)://&lt; *MBAMAdministrationServerName*&gt;:&lt;*port*&gt;/MBAMRecoveryAndHardwareService/CoreService.svc</span></span>

## <span data-ttu-id="3bff8-146">使用 Configuration Manager 整合拓朴驗證 MBAM 伺服器部署</span><span class="sxs-lookup"><span data-stu-id="3bff8-146">Validating the MBAM Server deployment with the Configuration Manager Integration topology</span></span>


<span data-ttu-id="3bff8-147">使用下列步驟，透過 Configuration Manager 整合拓朴驗證您的 MBAM 部署。</span><span class="sxs-lookup"><span data-stu-id="3bff8-147">Use the following steps to validate your MBAM deployment with the Configuration Manager Integration topology.</span></span> <span data-ttu-id="3bff8-148">完成符合您所使用之 Configuration Manager 版本的驗證步驟。</span><span class="sxs-lookup"><span data-stu-id="3bff8-148">Complete the validation steps that match the version of Configuration Manager that you are using.</span></span>

### <a href="" id="validating-the-mbam-server-deployment-with-system-center-2012-configuration-manager-"></a><span data-ttu-id="3bff8-149">使用 System Center 2012 Configuration Manager 驗證 MBAM Server 部署</span><span class="sxs-lookup"><span data-stu-id="3bff8-149">Validating the MBAM Server deployment with System Center 2012 Configuration Manager</span></span>

<span data-ttu-id="3bff8-150">當您將 MBAM 與 System Center 2012 Configuration Manager 搭配使用時，請使用這些步驟來驗證您的 MBAM 伺服器部署。</span><span class="sxs-lookup"><span data-stu-id="3bff8-150">Use these steps to validate your MBAM Server deployment when you are using MBAM with System Center 2012 Configuration Manager.</span></span>

**<span data-ttu-id="3bff8-151">驗證 Configuration Manager 整合 MBAM 伺服器部署– System Center 2012 Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="3bff8-151">To validate a Configuration Manager Integration MBAM Server deployment – System Center 2012 Configuration Manager</span></span>**

1.  <span data-ttu-id="3bff8-152">在部署 System Center 2012 Configuration Manager 的伺服器上，在 [**控制台**] 中開啟 [**程式和功能**]，然後確認出現 [ **Microsoft BitLocker 管理與監視**]。</span><span class="sxs-lookup"><span data-stu-id="3bff8-152">On the server where System Center 2012 Configuration Manager is deployed, open **Programs and Features** in **Control Panel**, and verify that **Microsoft BitLocker Administration and Monitoring** appears.</span></span>

    **<span data-ttu-id="3bff8-153">注意</span><span class="sxs-lookup"><span data-stu-id="3bff8-153">Note</span></span>**  
    <span data-ttu-id="3bff8-154">若要驗證配置，您必須使用在每個伺服器上都有本機電腦管理認證的網域帳戶。</span><span class="sxs-lookup"><span data-stu-id="3bff8-154">To validate the configuration, you must use a domain account that has local computer administrative credentials on each server.</span></span>



2.  <span data-ttu-id="3bff8-155">在 Configuration Manager 主控台中，按一下 [**資產] 和 [合規性**工作區] &gt; **裝置集合**，確認會顯示名為 [ **MBAM 支援的電腦**] 的新集合。</span><span class="sxs-lookup"><span data-stu-id="3bff8-155">In the Configuration Manager console, click the **Assets and Compliance** workspace &gt; **Device Collections**, and confirm that a new collection called **MBAM Supported Computers** is displayed.</span></span>

3.  <span data-ttu-id="3bff8-156">在 Configuration Manager 主控台中，按一下 [**監視**工作區 &gt; **報表**] &gt; **Reports** &gt; **MBAM**。</span><span class="sxs-lookup"><span data-stu-id="3bff8-156">In the Configuration Manager console, click the **Monitoring** workspace &gt; **Reporting** &gt; **Reports** &gt; **MBAM**.</span></span>

4.  <span data-ttu-id="3bff8-157">確認**MBAM**資料夾包含子資料夾，且名稱代表不同語言，且下列報表列在每個語言子資料夾中：</span><span class="sxs-lookup"><span data-stu-id="3bff8-157">Verify that the **MBAM** folder contains subfolders, with names that represent different languages, and that the following reports are listed in each language subfolder:</span></span>

    -   <span data-ttu-id="3bff8-158">BitLocker 電腦合規性</span><span class="sxs-lookup"><span data-stu-id="3bff8-158">BitLocker Computer Compliance</span></span>

    -   <span data-ttu-id="3bff8-159">BitLocker Enterprise 合規性儀表板</span><span class="sxs-lookup"><span data-stu-id="3bff8-159">BitLocker Enterprise Compliance Dashboard</span></span>

    -   <span data-ttu-id="3bff8-160">BitLocker 企業合規性詳細資料</span><span class="sxs-lookup"><span data-stu-id="3bff8-160">BitLocker Enterprise Compliance Details</span></span>

    -   <span data-ttu-id="3bff8-161">BitLocker Enterprise 合規性摘要</span><span class="sxs-lookup"><span data-stu-id="3bff8-161">BitLocker Enterprise Compliance Summary</span></span>

5.  <span data-ttu-id="3bff8-162">在 Configuration Manager 主控台中，按一下 [**資產與合規性**工作區 &gt; **合規性設定] 設定** &gt; **配置基線**，然後確認已列出 [設定比較基準**BitLocker] 保護**。</span><span class="sxs-lookup"><span data-stu-id="3bff8-162">In the Configuration Manager console, click the **Assets and Compliance** workspace &gt; **Compliance Settings** &gt; **Configuration Baselines**, and confirm that the configuration baseline **BitLocker Protection** is listed.</span></span>

6.  <span data-ttu-id="3bff8-163">在 Configuration Manager 主控台中，按一下 [**資產與合規性**工作區 &gt; **合規性設定] 設定** &gt; **專案**，並確認顯示下列新的設定專案：</span><span class="sxs-lookup"><span data-stu-id="3bff8-163">In the Configuration Manager console, click the **Assets and Compliance** workspace &gt; **Compliance Settings** &gt; **Configuration Items**, and confirm that the following new configuration items are displayed:</span></span>

    -   <span data-ttu-id="3bff8-164">BitLocker 固定資料磁碟機保護</span><span class="sxs-lookup"><span data-stu-id="3bff8-164">BitLocker Fixed Data Drives Protection</span></span>

    -   <span data-ttu-id="3bff8-165">BitLocker 作業系統磁片磁碟機保護</span><span class="sxs-lookup"><span data-stu-id="3bff8-165">BitLocker Operating System Drive Protection</span></span>

### <span data-ttu-id="3bff8-166">驗證 Configuration Manager 2007 的 MBAM 伺服器部署</span><span class="sxs-lookup"><span data-stu-id="3bff8-166">Validating the MBAM Server deployment with Configuration Manager 2007</span></span>

<span data-ttu-id="3bff8-167">當您將 MBAM 與 Configuration Manager 2007 搭配使用時，請使用這些步驟來驗證您的 MBAM 伺服器部署。</span><span class="sxs-lookup"><span data-stu-id="3bff8-167">Use these steps to validate your MBAM Server deployment when you are using MBAM with Configuration Manager 2007.</span></span>

**<span data-ttu-id="3bff8-168">驗證 Configuration Manager 整合 MBAM 伺服器部署-Configuration Manager 2007</span><span class="sxs-lookup"><span data-stu-id="3bff8-168">To validate a Configuration Manager Integration MBAM Server deployment – Configuration Manager 2007</span></span>**

1.  <span data-ttu-id="3bff8-169">在部署 Configuration Manager 2007 的伺服器上，在 [**控制台**] 上開啟 [**程式和功能**]，然後確認出現 [ **Microsoft BitLocker 管理和監視**]。</span><span class="sxs-lookup"><span data-stu-id="3bff8-169">On the server where Configuration Manager 2007 is deployed, open **Programs and Features** on **Control Panel** , and verify that **Microsoft BitLocker Administration and Monitoring** appears.</span></span>

    **<span data-ttu-id="3bff8-170">注意</span><span class="sxs-lookup"><span data-stu-id="3bff8-170">Note</span></span>**  
    <span data-ttu-id="3bff8-171">若要驗證配置，您必須使用在每個伺服器上都有本機電腦管理認證的網域帳戶。</span><span class="sxs-lookup"><span data-stu-id="3bff8-171">To validate the configuration, you must use a domain account that has local computer administrative credentials on each server.</span></span>



2.  <span data-ttu-id="3bff8-172">在 Configuration Manager 主控台中，按一下 [**網站資料庫 &lt; SiteCode &gt;  -  &lt; 伺服器 &gt; （ &lt; SiteName）]、[ &gt; 電腦管理**]，然後確認顯示稱為 [ **MBAM 支援的電腦**] 的新集合。</span><span class="sxs-lookup"><span data-stu-id="3bff8-172">In the Configuration Manager console, click **Site Database &lt;SiteCode&gt; - &lt;ServerName&gt;, &lt;SiteName&gt;), Computer Management**, and confirm that a new collection called **MBAM Supported Computers** is displayed.</span></span>

3.  <span data-ttu-id="3bff8-173">在 Configuration Manager 主控台中，按一下 [**報告** &gt; **服務** &gt; \*\* \\\\ &lt; 伺服器 &gt; 名稱伺服器\*\* &gt; **報告資料夾** &gt; **MBAM**]。</span><span class="sxs-lookup"><span data-stu-id="3bff8-173">In the Configuration Manager console, click **Reporting** &gt; **Reporting Services** &gt; **\\\\&lt;ServerName&gt;** &gt; **Report Folders** &gt; **MBAM**.</span></span>

    <span data-ttu-id="3bff8-174">確認**MBAM**資料夾包含子資料夾，且名稱代表不同語言，且下列報表列在每個語言子資料夾中：</span><span class="sxs-lookup"><span data-stu-id="3bff8-174">Verify that the **MBAM** folder contains subfolders, with names that represent different languages, and that the following reports are listed in each language subfolder:</span></span>

    -   <span data-ttu-id="3bff8-175">BitLocker 電腦合規性</span><span class="sxs-lookup"><span data-stu-id="3bff8-175">BitLocker Computer Compliance</span></span>

    -   <span data-ttu-id="3bff8-176">BitLocker Enterprise 合規性儀表板</span><span class="sxs-lookup"><span data-stu-id="3bff8-176">BitLocker Enterprise Compliance Dashboard</span></span>

    -   <span data-ttu-id="3bff8-177">BitLocker 企業合規性詳細資料</span><span class="sxs-lookup"><span data-stu-id="3bff8-177">BitLocker Enterprise Compliance Details</span></span>

    -   <span data-ttu-id="3bff8-178">BitLocker Enterprise 合規性摘要</span><span class="sxs-lookup"><span data-stu-id="3bff8-178">BitLocker Enterprise Compliance Summary</span></span>

4.  <span data-ttu-id="3bff8-179">在 Configuration Manager 主控台中，按一下 [**所需**的設定管理設定 &gt; **基準**]，並確認已列出 [設定比較基準**BitLocker] 保護**。</span><span class="sxs-lookup"><span data-stu-id="3bff8-179">In the Configuration Manager console, click **Desired Configuration Management** &gt; **Configuration Baselines**, and confirm that the configuration baseline **BitLocker Protection** is listed.</span></span>

5.  <span data-ttu-id="3bff8-180">在 Configuration Manager 主控台中，按一下 [**所需**的設定管理設定 &gt; **專案**]，然後確認顯示下列新的設定專案：</span><span class="sxs-lookup"><span data-stu-id="3bff8-180">In the Configuration Manager console, click **Desired Configuration Management** &gt; **Configuration Items**, and confirm that the following new configuration items are displayed:</span></span>

    -   <span data-ttu-id="3bff8-181">BitLocker 固定資料磁碟機保護</span><span class="sxs-lookup"><span data-stu-id="3bff8-181">BitLocker Fixed Data Drives Protection</span></span>

    -   <span data-ttu-id="3bff8-182">BitLocker 作業系統磁片磁碟機保護</span><span class="sxs-lookup"><span data-stu-id="3bff8-182">BitLocker Operating System Drive Protection</span></span>



## <span data-ttu-id="3bff8-183">相關主題</span><span class="sxs-lookup"><span data-stu-id="3bff8-183">Related topics</span></span>


[<span data-ttu-id="3bff8-184">設定 MBAM 2.5 伺服器功能</span><span class="sxs-lookup"><span data-stu-id="3bff8-184">Configuring the MBAM 2.5 Server Features</span></span>](configuring-the-mbam-25-server-features.md)


## <span data-ttu-id="3bff8-185">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="3bff8-185">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="3bff8-186">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="3bff8-186">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="3bff8-187">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="3bff8-187">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>






