---
title: MBAM 2.0 SP1 版本資訊
description: MBAM 2.0 SP1 版本資訊
author: dansimp
ms.assetid: b39002ba-33c6-45ec-9d1b-464327b60f5c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 54a77fc7a493b36217ae2cdc875226b25fdc6e7b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811241"
---
# <span data-ttu-id="ce694-103">MBAM 2.0 SP1 版本資訊</span><span class="sxs-lookup"><span data-stu-id="ce694-103">Release Notes for MBAM 2.0 SP1</span></span>


<span data-ttu-id="ce694-104">若要搜尋這些版本筆記，請按 Ctrl + F。</span><span class="sxs-lookup"><span data-stu-id="ce694-104">To search these release notes, press Ctrl+F.</span></span>

<span data-ttu-id="ce694-105">安裝 Microsoft BitLocker 管理與監控（MBAM） 2.0 Service Pack 1 （SP1）之前，請先閱讀這些版本資訊。</span><span class="sxs-lookup"><span data-stu-id="ce694-105">Read these release notes thoroughly before you install Microsoft BitLocker Administration and Monitoring (MBAM) 2.0 Service Pack 1 (SP1).</span></span> <span data-ttu-id="ce694-106">這些版本資訊包含成功安裝 BitLocker 管理和監控 2.0 SP1 所需的資訊，且包含產品檔中不提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="ce694-106">These release notes contain information that is required to successfully install BitLocker Administration and Monitoring 2.0 SP1, and they contain information that is not available in the product documentation.</span></span> <span data-ttu-id="ce694-107">如果這些版本資訊與其他 MBAM 2.0 SP1 檔有差異，最新的變更應該視為權威性。</span><span class="sxs-lookup"><span data-stu-id="ce694-107">If there is a difference between these release notes and other MBAM 2.0 SP1 documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="ce694-108">這些版本資訊取代本產品隨附的內容。</span><span class="sxs-lookup"><span data-stu-id="ce694-108">These release notes supersede the content that is included with this product.</span></span>

## <a href="" id="---------mbam-2-0-sp1-known-issues"></a> <span data-ttu-id="ce694-109">MBAM 2.0 SP1 已知問題</span><span class="sxs-lookup"><span data-stu-id="ce694-109">MBAM 2.0 SP1 known issues</span></span>


<span data-ttu-id="ce694-110">本節包含 MBAM 2.0 SP1 的已知問題。</span><span class="sxs-lookup"><span data-stu-id="ce694-110">This section contains known issues for MBAM 2.0 SP1.</span></span>

### <span data-ttu-id="ce694-111">將 Configuration Manager 整合拓朴的 MBAM 升級至 MBAM 2.0 SP1 需要手動移除 Configuration Manager 物件</span><span class="sxs-lookup"><span data-stu-id="ce694-111">Upgrade of MBAM with Configuration Manager Integrated topology to MBAM 2.0 SP1 requires manual removal of Configuration Manager objects</span></span>

<span data-ttu-id="ce694-112">如果您是使用 MBAM 與 Configuration Manager，且想要升級至 MBAM 2.0 SP1，您必須手動移除已安裝到 Configuration Manager 的所有 Configuration Manager 物件，作為 MBAM 安裝的一部分。</span><span class="sxs-lookup"><span data-stu-id="ce694-112">If you are using MBAM with Configuration Manager, and you want to upgrade to MBAM 2.0 SP1, you must manually remove all of the Configuration Manager objects that were installed into Configuration Manager as a part of the MBAM installation.</span></span> <span data-ttu-id="ce694-113">您必須手動移除的物件是 [MBAM] 報告、MBAM 支援的電腦集合，以及 BitLocker 保護設定基準及其相關的設定項目。</span><span class="sxs-lookup"><span data-stu-id="ce694-113">The objects that you must manually remove are the MBAM reports, MBAM Supported Computers collection, and the BitLocker Protection Configuration Baseline and its associated configuration items.</span></span>

<span data-ttu-id="ce694-114">因應**措施：完成**下列步驟以升級 Configuration Manager 物件：</span><span class="sxs-lookup"><span data-stu-id="ce694-114">**Workaround**: Upgrade the Configuration Manager objects by completing the following steps:</span></span>

1.  <span data-ttu-id="ce694-115">將現有的合規性資料備份到外部檔案，如下列步驟所述。</span><span class="sxs-lookup"><span data-stu-id="ce694-115">Back up existing compliance data to an external file, as described in the following steps.</span></span>

    <span data-ttu-id="ce694-116">**記事** 當您在 Configuration Manager 中刪除現有的比較基準時，將會刪除所有現有的 BitLocker 相容性資料。</span><span class="sxs-lookup"><span data-stu-id="ce694-116">**Note** All existing BitLocker compliance data will be deleted when you delete the existing baseline in Configuration Manager.</span></span> <span data-ttu-id="ce694-117">資料會隨著時間重新產生，但建議您儲存一份資料複本，以防在您需要特定電腦的合規性資料之後，才能重新產生合規性資料。</span><span class="sxs-lookup"><span data-stu-id="ce694-117">The data will be regenerated over time, but it is recommended that you save a copy of the data in case you need the compliance data for a particular computer before the compliance data has been regenerated.</span></span>

     

    1.  <span data-ttu-id="ce694-118">若要儲存已記錄的 BitLocker 合規性資料，請開啟**Bitlocker 企業合規性詳細**資料包告。</span><span class="sxs-lookup"><span data-stu-id="ce694-118">To save historical BitLocker compliance data, open the **BitLocker Enterprise Compliance Details** Report.</span></span>

    2.  <span data-ttu-id="ce694-119">按一下報表中的 [**儲存**] 圖示，然後選取 [ **Excel**]。</span><span class="sxs-lookup"><span data-stu-id="ce694-119">Click the **Save** icon in the report and select **Excel**.</span></span>

        <span data-ttu-id="ce694-120">儲存的報告將會包含以下資料，例如電腦名稱稱、功能變數名稱、合規性狀態、豁免、裝置使用者、合規性狀態詳細資料，以及最後一個連絡人的日期/時間。</span><span class="sxs-lookup"><span data-stu-id="ce694-120">The saved report will contain data such as the computer name, domain name, compliance status, exemption, device users, compliance status details, and last contact date/time.</span></span> <span data-ttu-id="ce694-121">某些資訊（例如詳細的大量資訊和加密強度）不會儲存。</span><span class="sxs-lookup"><span data-stu-id="ce694-121">Some information, such as detailed volume information and encryption strength, are not saved.</span></span>

2.  <span data-ttu-id="ce694-122">使用**MBAM**安裝程式從伺服器卸載**MBAM** 。</span><span class="sxs-lookup"><span data-stu-id="ce694-122">Uninstall **MBAM** from the server by using the **MBAM** installer.</span></span>

3.  <span data-ttu-id="ce694-123">從 Configuration Manager 手動刪除下列物件：</span><span class="sxs-lookup"><span data-stu-id="ce694-123">Manually delete the following objects from Configuration Manager:</span></span>

    -   <span data-ttu-id="ce694-124">MBAM 支援的電腦集合</span><span class="sxs-lookup"><span data-stu-id="ce694-124">MBAM Supported Computers collection</span></span>

    -   <span data-ttu-id="ce694-125">BitLocker 保護比較基準</span><span class="sxs-lookup"><span data-stu-id="ce694-125">BitLocker Protection baseline</span></span>

    -   <span data-ttu-id="ce694-126">BitLocker 作業系統磁片磁碟機保護設定專案</span><span class="sxs-lookup"><span data-stu-id="ce694-126">BitLocker Operating System Drive Protection configuration item</span></span>

    -   <span data-ttu-id="ce694-127">BitLocker 固定資料磁碟機保護設定專案</span><span class="sxs-lookup"><span data-stu-id="ce694-127">BitLocker Fixed Data Drives Protection configuration item</span></span>

4.  <span data-ttu-id="ce694-128">手動刪除 Configuration Manager SQL Server Reporting Services 網站中的 [MBAM 報表] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="ce694-128">Manually delete the MBAM Reports folder in the Configuration Manager SQL Server Reporting Services site.</span></span> <span data-ttu-id="ce694-129">做法如下：</span><span class="sxs-lookup"><span data-stu-id="ce694-129">To do this:</span></span>

    1.  <span data-ttu-id="ce694-130">使用 Internet Explorer 流覽至 reporting services 點，例如，HTTP:// &lt; yourcmserver &gt; /reports。</span><span class="sxs-lookup"><span data-stu-id="ce694-130">Use Internet Explorer to browse to the reporting services point, for example, http://&lt;yourcmserver&gt;/reports.</span></span>

    2.  <span data-ttu-id="ce694-131">按一下適當的 Configuration Manager [網站程式碼] 連結。</span><span class="sxs-lookup"><span data-stu-id="ce694-131">Click the appropriate Configuration Manager site code link.</span></span>

    3.  <span data-ttu-id="ce694-132">刪除 [MBAM] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="ce694-132">Delete the MBAM folder.</span></span>

5.  <span data-ttu-id="ce694-133">使用 MBAM 伺服器安裝程式重新安裝 Configuration Manager 整合物件。</span><span class="sxs-lookup"><span data-stu-id="ce694-133">Use the MBAM Server installer to reinstall the Configuration Manager Integration objects.</span></span> <span data-ttu-id="ce694-134">用戶端電腦將會在一段時間後再次開始上傳 BitLocker 合規性資料。</span><span class="sxs-lookup"><span data-stu-id="ce694-134">The client computers will begin to upload BitLocker compliance data again over time.</span></span>

### <span data-ttu-id="ce694-135">自助版入口網站上的 [Submit] （提交）按鈕無法在網際網路 Explorer10 中運作</span><span class="sxs-lookup"><span data-stu-id="ce694-135">Submit button on Self-Service Portal does not work in Internet Explorer10</span></span>

<span data-ttu-id="ce694-136">當您使用網際網路 Explorer10 存取管理和監控網站時，網站上的 [Submit] （**提交**）按鈕無法運作。</span><span class="sxs-lookup"><span data-stu-id="ce694-136">When you use Internet Explorer10 to access the Administration and Monitoring Website, the **Submit** button on the website does not work.</span></span>

<span data-ttu-id="ce694-137">因應**措施：在**您安裝 [管理及監視] 網站的伺服器上，安裝[ASP.NET 瀏覽器定義檔案的修復程式](https://go.microsoft.com/fwlink/?LinkId=317798)。</span><span class="sxs-lookup"><span data-stu-id="ce694-137">**Workaround**: On the server where you installed the Administration and Monitoring Website, install [Hotfix for ASP.NET browser definition files](https://go.microsoft.com/fwlink/?LinkId=317798).</span></span>

### <span data-ttu-id="ce694-138">不支援國際功能變數名稱</span><span class="sxs-lookup"><span data-stu-id="ce694-138">International domain names are not supported</span></span>

<span data-ttu-id="ce694-139">MBAM 2.0 SP1 不支援國際功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="ce694-139">MBAM 2.0 SP1 does not support international domain names.</span></span>

<span data-ttu-id="ce694-140">因應**措施：無**。</span><span class="sxs-lookup"><span data-stu-id="ce694-140">**Workaround**: None.</span></span>

### <span data-ttu-id="ce694-141">如果未在 SSRS 中設定 SSL，系統管理和監控網站中的報告會顯示警告</span><span class="sxs-lookup"><span data-stu-id="ce694-141">Reports in the Administration and Monitoring website display a warning if SSL is not configured in SSRS</span></span>

<span data-ttu-id="ce694-142">如果 SQLServer Reporting Services （SSRS）未設定為使用安全通訊端層（SSL），那麼當您安裝 MBAM 伺服器時，會將報表的 URL 設定為 HTTP，而不是 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="ce694-142">If SQLServer Reporting Services (SSRS) was not configured to use Secure Socket Layer (SSL), the URL for the reports will be set to HTTP instead of HTTPS when you install the MBAM Server.</span></span> <span data-ttu-id="ce694-143">如果您接著流覽至 [管理及監視] 網站並選取報告，則會顯示下列訊息：「只會顯示安全內容」。</span><span class="sxs-lookup"><span data-stu-id="ce694-143">If you then browse to the Administration and Monitoring website and select a report, the following message displays: “Only Secure Content is Displayed.”</span></span>

<span data-ttu-id="ce694-144">因應**措施：若**要修正此問題，請在安裝了 SQLServer reporting SERVICES 的 MBAM 伺服器上，設定**Reporting Services 組態管理員**中的 SSL。</span><span class="sxs-lookup"><span data-stu-id="ce694-144">**Workaround**: To correct this issue, configure SSL in **Reporting Services Configuration Manager** on the MBAM server where SQLServer Reporting Services is installed.</span></span> <span data-ttu-id="ce694-145">卸載並重新安裝 [管理及監視伺服器] 網站。</span><span class="sxs-lookup"><span data-stu-id="ce694-145">Uninstall and then reinstall the Administration and Monitoring Server website.</span></span>

### <span data-ttu-id="ce694-146">按一下 [合規性摘要] 報告中的 [返回] 可能會產生錯誤</span><span class="sxs-lookup"><span data-stu-id="ce694-146">Clicking Back in the Compliance Summary report might create an error</span></span>

<span data-ttu-id="ce694-147">如果您向下切入至 [達標摘要] 報告，然後按一下 SSRS 報表中的 [**返回**] 連結，可能會發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="ce694-147">If you drill down into a Compliance Summary report, and then click the **Back** link in the SSRS report, an error might occur.</span></span>

<span data-ttu-id="ce694-148">因應**措施：無**。</span><span class="sxs-lookup"><span data-stu-id="ce694-148">**Workaround**: None.</span></span>

### <span data-ttu-id="ce694-149">只有使用中的空間加密無法正常運作</span><span class="sxs-lookup"><span data-stu-id="ce694-149">Used Space Only Encryption does not work correctly</span></span>

<span data-ttu-id="ce694-150">如果您在安裝 MBAM 用戶端後第一次將電腦加密，且已將群組原則物件設定為只執行加密，請 MBAM 錯誤地加密整個磁片，而不是只加密磁片的已使用空間。</span><span class="sxs-lookup"><span data-stu-id="ce694-150">If you encrypt a computer for the first time after you install the MBAM Client, and you have set a Group Policy Object to implement Used Space Only Encryption, MBAM erroneously encrypts the entire disk instead of encrypting only the disk’s used space.</span></span> <span data-ttu-id="ce694-151">如果電腦已在安裝 MBAM 用戶端之前使用 [僅限已使用空間] 加密，且您已將相同的已使用空間設定為「加密」群組原則物件，則 MBAM 會辨識該設定，並在合規性報告中正確報告加密。</span><span class="sxs-lookup"><span data-stu-id="ce694-151">If a computer is already encrypted with Used Space Only Encryption before you install the MBAM Client, and you have set the same Used Space Only Encryption Group Policy Object, MBAM recognizes the setting and reports the encryption correctly in the compliance reports.</span></span>

<span data-ttu-id="ce694-152">因應**措施：無**。</span><span class="sxs-lookup"><span data-stu-id="ce694-152">**Workaround**: None.</span></span>

### <span data-ttu-id="ce694-153">密碼強度在電腦合規性報告中無法正確顯示</span><span class="sxs-lookup"><span data-stu-id="ce694-153">Cipher strength displays incorrectly in the Computer Compliance report</span></span>

<span data-ttu-id="ce694-154">如果您沒有在 [**選擇磁片磁碟機加密方法] 和 [密碼強度**] 群群組原則物件中設定特定的密碼強度，即使密碼強度使用預設的128位加密，Configuration Manager 整合拓撲中的電腦合規性報告也會不**會顯示密碼**強度。</span><span class="sxs-lookup"><span data-stu-id="ce694-154">If you do not set a specific cipher strength in the **Choose drive encryption method and cipher strength** Group Policy Object, the Computer Compliance report in the Configuration Manager integrated topology always displays **Unknown** for the cipher strength, even when the cipher strength uses the default of 128-bit encryption.</span></span> <span data-ttu-id="ce694-155">如果您在群組原則物件中設定特定的密碼強度，報告會顯示正確的密碼強度。</span><span class="sxs-lookup"><span data-stu-id="ce694-155">The report displays the correct cipher strength if you set a specific cipher strength in the Group Policy Object.</span></span>

<span data-ttu-id="ce694-156">因應**措施：在**[**選擇磁片磁碟機加密方法及密碼強度**] 群群組原則物件中，永遠都要設定特定的密碼強度。</span><span class="sxs-lookup"><span data-stu-id="ce694-156">**Workaround**: Always set a specific cipher strength in the **Choose drive encryption method and cipher strength** Group Policy Object.</span></span>

### <span data-ttu-id="ce694-157">依磁片磁碟機類型進行合規性狀態發佈會在您更新設定專案後顯示舊資料</span><span class="sxs-lookup"><span data-stu-id="ce694-157">Compliance Status Distribution By Drive Type displays old data after you update configuration items</span></span>

<span data-ttu-id="ce694-158">更新 SystemCenter2012 ConfigurationManager 中的 MBAM 設定專案之後，由 BitLocker Enterprise 合規性儀表板上的 [磁碟機類型] 橫條圖顯示的 [遵從性狀態發佈] 會顯示以舊版本的設定項目資訊為基礎的資料。</span><span class="sxs-lookup"><span data-stu-id="ce694-158">After you update MBAM configuration items in SystemCenter2012 ConfigurationManager, the Compliance Status Distribution By Drive Type bar chart on the BitLocker Enterprise Compliance Dashboard shows data that is based on information from old versions of the configuration items.</span></span>

<span data-ttu-id="ce694-159">因應**措施：無**。</span><span class="sxs-lookup"><span data-stu-id="ce694-159">**Workaround**: None.</span></span> <span data-ttu-id="ce694-160">不支援修改 MBAM 設定專案，而且報告可能不會如預期所示。</span><span class="sxs-lookup"><span data-stu-id="ce694-160">Modification of the MBAM configuration items is not supported, and the report might not appear as expected.</span></span>

### <span data-ttu-id="ce694-161">[增強的安全性設定] 可能會導致報告無法正確顯示</span><span class="sxs-lookup"><span data-stu-id="ce694-161">Enhanced Security Configuration may cause reports to display incorrectly</span></span>

<span data-ttu-id="ce694-162">如果開啟 Internet Explorer 增強的安全性設定（ESC），當您嘗試在 MBAM 伺服器上查看報告時，可能會出現「**拒絕存取**」訊息。</span><span class="sxs-lookup"><span data-stu-id="ce694-162">If Internet Explorer Enhanced Security Configuration (ESC) is turned on, an **Access Denied** message might appear when you try to view reports on the MBAM Server.</span></span> <span data-ttu-id="ce694-163">根據預設，增強的安全性設定是通過將伺服器暴露在網頁內容和應用程式腳本中可能會發生的可能攻擊，來保護伺服器。</span><span class="sxs-lookup"><span data-stu-id="ce694-163">By default, Enhanced Security Configuration is turned on to protect the server by decreasing the server’s exposure to potential attacks that can occur through web content and application scripts.</span></span>

<span data-ttu-id="ce694-164">因應**措施：如果**在您嘗試在 MBAM 伺服器上查看報告時出現 [**拒絕存取**] 訊息，您可以在影像中設定群組原則物件或手動變更預設值，以停用增強的安全性設定。</span><span class="sxs-lookup"><span data-stu-id="ce694-164">**Workaround**: If the **Access Denied** message appears when you try to view reports on the MBAM Server, you can set a Group Policy Object or change the default manually in your image to disable Enhanced Security Configuration.</span></span> <span data-ttu-id="ce694-165">您也可以在未啟用增強安全性設定的另一部電腦上，視需要查看報告。</span><span class="sxs-lookup"><span data-stu-id="ce694-165">You can also alternatively view the reports from another computer on which Enhanced Security Configuration is not enabled.</span></span>

### <a href="" id="-------------mbam-server-installation-fails-when-you-upgrade-from-sql-server-2008-to-sql-server-2012"></a> <span data-ttu-id="ce694-166">從 SQLServer2008 升級至 SQLServer2012 時，MBAM 伺服器安裝失敗</span><span class="sxs-lookup"><span data-stu-id="ce694-166">MBAM Server installation fails when you upgrade from SQLServer2008 to SQLServer2012</span></span>

<span data-ttu-id="ce694-167">如果您從 SQLServer2008 升級到 SQLServer2012，然後嘗試安裝合規性和審核資料庫或復原資料庫，安裝就會失敗並回滾。</span><span class="sxs-lookup"><span data-stu-id="ce694-167">If you upgrade from SQLServer2008 to SQLServer2012, and then try to install the Compliance and Audit Database or the Recovery Database, the installation fails and rolls back.</span></span> <span data-ttu-id="ce694-168">發生失敗的原因是，在 SQLServer 升級期間已移除所需的 SQLCMD.exe 檔案，且 MBAM 安裝程式無法找到該檔案。</span><span class="sxs-lookup"><span data-stu-id="ce694-168">The failure occurs because the required SQLCMD.exe file was removed during the SQLServer upgrade, and it cannot be found by the MBAM installer.</span></span> <span data-ttu-id="ce694-169">MSI 記錄檔行可能看起來類似下列：</span><span class="sxs-lookup"><span data-stu-id="ce694-169">The MSI log file lines may look similar to the following:</span></span>

<span data-ttu-id="ce694-170">RunDbInstallScript 復原資料庫 CA： BinDir-E:\\MSSQL\\100\\Tools\\Binn\\SqlCmd.exeRunDbInstallScript 復原資料庫 CA： dbInstance-xxxxxx\\I01RunDbInstallScript Recovery Db CA： sqlScript-C:\\program files Files\\Microsoft\\Microsoft _HardwareRunDbInstallScript _and _Recovery \ [\ Monitoring\\Setup\\KeyRecovery.sqlRunDbInstallScript db ca： dbName-MBAM \ _Recovery \ _and _HardwareRunDbInstallScript Recovery Db CA： DefaultFileName-MBAMI01\\MSSQL\\DATA\\RunDbInstallScript Recovery Db CA： defaultLogPath-K:\\MSSQL\\MSSQL10。I01\\MSSQL\\Data\\RunDbInstallScript 復原資料庫 CA： scriptLogPath-C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\InstallKeyComplianceDatabase.log-e-E-S xxxxxxx\\I01-i "C:\\program files Files\\Microsoft\\Microsoft BitLocker 管理和 Monitoring\\Setup\\KeyRecovery.sql"-v DatabaseName = "MBAM \ _Recovery \ _and \ _Hardware" DefaultFileName = "MBAM \ _Recovery \ _and \ _Hardware" DefaultDataPath = "F:\\MSSQL\\MSSQL10。I01\\MSSQL\\DATA\\ "DefaultLogPath =" K:\\MSSQL\\MSSQL10。I01\\MSSQL\\Data\\ "-o" C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\InstallKeyComplianceDatabase.log "RunDbInstallScript 復原資料庫 ca：開始執行恢復資料庫的安裝 scriptRunDbInstallScript 復原資料庫 CA： Sqlcmd 記錄檔案位於 C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\\\InstallKeyRecoveryDatabase.logRunDbInstallScript 復原 Db CA 例外狀況：安裝復原資料庫自訂操作命令列輸出例外狀況：系統找不到指定的檔案</span><span class="sxs-lookup"><span data-stu-id="ce694-170">RunDbInstallScript Recovery Db CA: BinDir - E:\\MSSQL\\100\\Tools\\Binn\\SqlCmd.exeRunDbInstallScript Recovery Db CA: dbInstance - xxxxxx\\I01RunDbInstallScript Recovery Db CA: sqlScript- C:\\Program Files\\Microsoft\\Microsoft BitLocker Administration and Monitoring\\Setup\\KeyRecovery.sqlRunDbInstallScript Recovery Db CA: dbName- MBAM\_Recovery\_and\_HardwareRunDbInstallScript Recovery Db CA: defaultFileName- MBAM\_Recovery\_and\_HardwareRunDbInstallScript Recovery Db CA: defaultDataPath- F:\\MSSQL\\MSSQL10.I01\\MSSQL\\DATA\\RunDbInstallScript Recovery Db CA: defaultLogPath- K:\\MSSQL\\MSSQL10.I01\\MSSQL\\Data\\RunDbInstallScript Recovery Db CA: scriptLogPath - C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\InstallKeyComplianceDatabase.log-e -E -S xxxxxxx\\I01 -i "C:\\Program Files\\Microsoft\\Microsoft BitLocker Administration and Monitoring\\Setup\\KeyRecovery.sql" -v DatabaseName="MBAM\_Recovery\_and\_Hardware" DefaultFileName="MBAM\_Recovery\_and\_Hardware" DefaultDataPath="F:\\MSSQL\\MSSQL10.I01\\MSSQL\\DATA\\" DefaultLogPath="K:\\MSSQL\\MSSQL10.I01\\MSSQL\\Data\\" -o "C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\InstallKeyComplianceDatabase.log"RunDbInstallScript Recovery Db CA:Starting to run the Recovery database install scriptRunDbInstallScript Recovery Db CA: Sqlcmd log file is located in C:\\Users\\xxxxxx\\AppData\\Local\\Temp\\\\InstallKeyRecoveryDatabase.logRunDbInstallScript Recovery Db CA Exception: Install Recovery database Custom Action command line output Exception: The system cannot find the file specified</span></span>

<span data-ttu-id="ce694-171">您可以在 [HKLM\\Software\\Microsoft\\Microsoft] 下的 [登錄] 底下的 [Path 字串] 值中查看 MBAM 伺服器 Windows 安裝程式，以尋找 SQLCMD.exe 路徑。</span><span class="sxs-lookup"><span data-stu-id="ce694-171">The MBAM Server Windows Installer is hardcoded to find the SQLCMD.exe path by looking in the Path string value in the registry under HKLM\\Software\\Microsoft\\Microsoft SQLServer\\100\\Tools\\ClientSetup.</span></span> <span data-ttu-id="ce694-172">從 SQLServer2008 到 SQLServer2012 的遷移期間，該金鑰仍然存在，但資料值所參照的路徑不會包含 SQLCMD.exe 檔案，因為 SQLupgrade 程式已移除檔案。</span><span class="sxs-lookup"><span data-stu-id="ce694-172">The key is still present during the migration from SQLServer2008 to SQLServer2012, but the path that is referenced by the data value does not contain the SQLCMD.exe file, because the SQLupgrade process removed the file.</span></span>

<span data-ttu-id="ce694-173">因應**措施：暫時**將 HKLM\\Software\\Microsoft\\Microsoft SQLServer\\100\\Tools\\ClientSetup path 字串值重新命名為**path \ _old**，然後再次在 MBAM 伺服器上執行 Windows Installer。</span><span class="sxs-lookup"><span data-stu-id="ce694-173">**Workaround**: Temporarily rename the HKLM\\Software\\Microsoft\\Microsoft SQLServer\\100\\Tools\\ClientSetup path string value to **Path\_old**, and then run Windows Installer on the MBAM Server again.</span></span> <span data-ttu-id="ce694-174">當安裝成功完成並在 SQLServer2012 中建立資料庫時，重新命名**路徑 \ _old**至**path**。</span><span class="sxs-lookup"><span data-stu-id="ce694-174">When the installation completes successfully and creates the databases in SQLServer2012, rename **Path\_old** to **Path**.</span></span>

## <span data-ttu-id="ce694-175">MBAM 2.0 SP1 的修補程式和知識庫文章</span><span class="sxs-lookup"><span data-stu-id="ce694-175">Hotfixes and Knowledge Base articles for MBAM 2.0 SP1</span></span>


<span data-ttu-id="ce694-176">本節包含適用于 MBAM 2.0 SP1 的修補程式和知識庫文章。</span><span class="sxs-lookup"><span data-stu-id="ce694-176">This section contains hotfixes and KB articles for MBAM 2.0 SP1.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="ce694-177">知識庫文章</span><span class="sxs-lookup"><span data-stu-id="ce694-177">KB Article</span></span></strong></th>
<th align="left"><span data-ttu-id="ce694-178">Title</span><span class="sxs-lookup"><span data-stu-id="ce694-178">Title</span></span></th>
<th align="left"><strong><span data-ttu-id="ce694-179">連結</span><span class="sxs-lookup"><span data-stu-id="ce694-179">Link</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ce694-180">2831166</span><span class="sxs-lookup"><span data-stu-id="ce694-180">2831166</span></span></p></td>
<td align="left"><p><span data-ttu-id="ce694-181">安裝 Microsoft BitLocker 管理和監控（MBAM）2.0 失敗， &quot; 已安裝 System CENTER CM 物件&quot;</span><span class="sxs-lookup"><span data-stu-id="ce694-181">Installing Microsoft BitLocker Administration and Monitoring (MBAM) 2.0 fails with &quot;System Center CM Objects Already Installed&quot;</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2831166/EN-US" data-raw-source="[support.microsoft.com/kb/2831166/EN-US](https://support.microsoft.com/kb/2831166/EN-US)"><span data-ttu-id="ce694-182">support.microsoft.com/kb/2831166/EN-US</span><span class="sxs-lookup"><span data-stu-id="ce694-182">support.microsoft.com/kb/2831166/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ce694-183">2870849</span><span class="sxs-lookup"><span data-stu-id="ce694-183">2870849</span></span></p></td>
<td align="left"><p><span data-ttu-id="ce694-184">使用者無法使用 MBAM 2.0 自助服務入口網站來取得 BitLocker 復原金鑰</span><span class="sxs-lookup"><span data-stu-id="ce694-184">Users cannot retrieve BitLocker Recovery key using MBAM2.0 Self Service Portal</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870849/EN-US" data-raw-source="[support.microsoft.com/kb/2870849/EN-US](https://support.microsoft.com/kb/2870849/EN-US)"><span data-ttu-id="ce694-185">support.microsoft.com/kb/2870849/EN-US</span><span class="sxs-lookup"><span data-stu-id="ce694-185">support.microsoft.com/kb/2870849/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ce694-186">2756402</span><span class="sxs-lookup"><span data-stu-id="ce694-186">2756402</span></span></p></td>
<td align="left"><p><span data-ttu-id="ce694-187">事件描述中的 MBAM 用戶端將無法使用事件 ID 4 和錯誤碼0x8004100E</span><span class="sxs-lookup"><span data-stu-id="ce694-187">MBAM client would fail with Event ID 4 and error code 0x8004100E in the Event description</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2756402/EN-US" data-raw-source="[support.microsoft.com/kb/2756402/EN-US](https://support.microsoft.com/kb/2756402/EN-US)"><span data-ttu-id="ce694-188">support.microsoft.com/kb/2756402/EN-US</span><span class="sxs-lookup"><span data-stu-id="ce694-188">support.microsoft.com/kb/2756402/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ce694-189">2620287</span><span class="sxs-lookup"><span data-stu-id="ce694-189">2620287</span></span></p></td>
<td align="left"><p><span data-ttu-id="ce694-190">按一下 MBAM 中的 [報表] 索引標籤時，出現「/Reports ' 應用程式」的 [伺服器錯誤] 錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="ce694-190">Error Message “Server Error in ‘/Reports’ Application” When You Click Reports Tab in MBAM</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2620287/EN-US" data-raw-source="[support.microsoft.com/kb/2620287/EN-US](https://support.microsoft.com/kb/2620287/EN-US)"><span data-ttu-id="ce694-191">support.microsoft.com/kb/2620287/EN-US</span><span class="sxs-lookup"><span data-stu-id="ce694-191">support.microsoft.com/kb/2620287/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ce694-192">2639518</span><span class="sxs-lookup"><span data-stu-id="ce694-192">2639518</span></span></p></td>
<td align="left"><p><span data-ttu-id="ce694-193">在 MBAM 中開啟企業或電腦合規性報告時發生錯誤</span><span class="sxs-lookup"><span data-stu-id="ce694-193">Error opening Enterprise or Computer Compliance Reports in MBAM</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2639518/EN-US" data-raw-source="[support.microsoft.com/kb/2639518/EN-US](https://support.microsoft.com/kb/2639518/EN-US)"><span data-ttu-id="ce694-194">support.microsoft.com/kb/2639518/EN-US</span><span class="sxs-lookup"><span data-stu-id="ce694-194">support.microsoft.com/kb/2639518/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ce694-195">2620269</span><span class="sxs-lookup"><span data-stu-id="ce694-195">2620269</span></span></p></td>
<td align="left"><p><span data-ttu-id="ce694-196">MBAM 企業報告無法取得更新</span><span class="sxs-lookup"><span data-stu-id="ce694-196">MBAM Enterprise Reporting Not Getting Updated</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2620269/EN-US" data-raw-source="[support.microsoft.com/kb/2620269/EN-US](https://support.microsoft.com/kb/2620269/EN-US)"><span data-ttu-id="ce694-197">support.microsoft.com/kb/2620269/EN-US</span><span class="sxs-lookup"><span data-stu-id="ce694-197">support.microsoft.com/kb/2620269/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ce694-198">2712461</span><span class="sxs-lookup"><span data-stu-id="ce694-198">2712461</span></span></p></td>
<td align="left"><p><span data-ttu-id="ce694-199">不支援在網網域控制站上安裝 MBAM</span><span class="sxs-lookup"><span data-stu-id="ce694-199">Installing MBAM on a Domain Controller is not supported</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2712461/EN-US" data-raw-source="[support.microsoft.com/kb/2712461/EN-US](https://support.microsoft.com/kb/2712461/EN-US)"><span data-ttu-id="ce694-200">support.microsoft.com/kb/2712461/EN-US</span><span class="sxs-lookup"><span data-stu-id="ce694-200">support.microsoft.com/kb/2712461/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ce694-201">2876732</span><span class="sxs-lookup"><span data-stu-id="ce694-201">2876732</span></span></p></td>
<td align="left"><p><span data-ttu-id="ce694-202">您在獨立或 Configuration Manager 集成設定 MBAM 2.0 期間收到錯誤代碼0x80071a90</span><span class="sxs-lookup"><span data-stu-id="ce694-202">You receive error code 0x80071a90 during Standalone or Configuration Manager Integration setup of MBAM2.0</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2876732/EN-US" data-raw-source="[support.microsoft.com/kb/2876732/EN-US](https://support.microsoft.com/kb/2876732/EN-US)"><span data-ttu-id="ce694-203">support.microsoft.com/kb/2876732/EN-US</span><span class="sxs-lookup"><span data-stu-id="ce694-203">support.microsoft.com/kb/2876732/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ce694-204">2754259</span><span class="sxs-lookup"><span data-stu-id="ce694-204">2754259</span></span></p></td>
<td align="left"><p><span data-ttu-id="ce694-205">MBAM 及安全的網路通訊</span><span class="sxs-lookup"><span data-stu-id="ce694-205">MBAM and Secure Network Communication</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2754259/EN-US" data-raw-source="[support.microsoft.com/kb/2754259/EN-US](https://support.microsoft.com/kb/2754259/EN-US)"><span data-ttu-id="ce694-206">support.microsoft.com/kb/2754259/EN-US</span><span class="sxs-lookup"><span data-stu-id="ce694-206">support.microsoft.com/kb/2754259/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ce694-207">2870842</span><span class="sxs-lookup"><span data-stu-id="ce694-207">2870842</span></span></p></td>
<td align="left"><p><span data-ttu-id="ce694-208">MBAM 2.0 安裝程式在 Configuration Manager 整合案例中使用 SQL Server 2008 失敗</span><span class="sxs-lookup"><span data-stu-id="ce694-208">MBAM2.0 Setup fails during Configuration Manager Integration Scenario with SQL Server 2008</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870842/EN-US" data-raw-source="[support.microsoft.com/kb/2870842/EN-US](https://support.microsoft.com/kb/2870842/EN-US)"><span data-ttu-id="ce694-209">support.microsoft.com/kb/2870842/EN-US</span><span class="sxs-lookup"><span data-stu-id="ce694-209">support.microsoft.com/kb/2870842/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ce694-210">2668533</span><span class="sxs-lookup"><span data-stu-id="ce694-210">2668533</span></span></p></td>
<td align="left"><p><span data-ttu-id="ce694-211">如果未正確設定 SQL SSRS，則 MBAM 安裝程式會失敗</span><span class="sxs-lookup"><span data-stu-id="ce694-211">MBAM Setup fails if SQL SSRS is not configured properly</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2668533/EN-US" data-raw-source="[support.microsoft.com/kb/2668533/EN-US](https://support.microsoft.com/kb/2668533/EN-US)"><span data-ttu-id="ce694-212">support.microsoft.com/kb/2668533/EN-US</span><span class="sxs-lookup"><span data-stu-id="ce694-212">support.microsoft.com/kb/2668533/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ce694-213">2870847</span><span class="sxs-lookup"><span data-stu-id="ce694-213">2870847</span></span></p></td>
<td align="left"><p><span data-ttu-id="ce694-214">MBAM 2.0 安裝失敗， &quot; 檢索 &#39;Reporting Services Point&#39; 角色的 Configuration Manager 伺服器角色設定時發生錯誤&quot;</span><span class="sxs-lookup"><span data-stu-id="ce694-214">MBAM 2.0 Setup fails with &quot;Error retrieving Configuration Manager Server role settings for &#39;Reporting Services Point&#39; role&quot;</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870847/EN-US" data-raw-source="[support.microsoft.com/kb/2870847/EN-US](https://support.microsoft.com/kb/2870847/EN-US)"><span data-ttu-id="ce694-215">support.microsoft.com/kb/2870847/EN-US</span><span class="sxs-lookup"><span data-stu-id="ce694-215">support.microsoft.com/kb/2870847/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ce694-216">2870839</span><span class="sxs-lookup"><span data-stu-id="ce694-216">2870839</span></span></p></td>
<td align="left"><p><span data-ttu-id="ce694-217">由於 SQL 作業 CreateCache 失敗，所以無法在 MBAM 2.0 獨立拓朴中重新整理 MBAM 2.0 企業報告</span><span class="sxs-lookup"><span data-stu-id="ce694-217">MBAM2.0 Enterprise Reports are not refreshed in MBAM2.0 Standalone topology due to SQL job CreateCache failure</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870839/EN-US" data-raw-source="[support.microsoft.com/kb/2870839/EN-US](https://support.microsoft.com/kb/2870839/EN-US)"><span data-ttu-id="ce694-218">support.microsoft.com/kb/2870839/EN-US</span><span class="sxs-lookup"><span data-stu-id="ce694-218">support.microsoft.com/kb/2870839/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ce694-219">2620269</span><span class="sxs-lookup"><span data-stu-id="ce694-219">2620269</span></span></p></td>
<td align="left"><p><span data-ttu-id="ce694-220">MBAM 企業報告無法取得更新</span><span class="sxs-lookup"><span data-stu-id="ce694-220">MBAM Enterprise Reporting Not Getting Updated</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2620269/EN-US" data-raw-source="[support.microsoft.com/kb/2620269/EN-US](https://support.microsoft.com/kb/2620269/EN-US)"><span data-ttu-id="ce694-221">support.microsoft.com/kb/2620269/EN-US</span><span class="sxs-lookup"><span data-stu-id="ce694-221">support.microsoft.com/kb/2620269/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="ce694-222">2935997</span><span class="sxs-lookup"><span data-stu-id="ce694-222">2935997</span></span></p></td>
<td align="left"><p><span data-ttu-id="ce694-223">MBAM 支援的電腦合規性報告不正確包含不支援的產品</span><span class="sxs-lookup"><span data-stu-id="ce694-223">MBAM Supported Computers compliance reporting incorrectly includes unsupported products</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2935997/EN-US" data-raw-source="[support.microsoft.com/kb/2935997/EN-US](https://support.microsoft.com/kb/2935997/EN-US)"><span data-ttu-id="ce694-224">support.microsoft.com/kb/2935997/EN-US</span><span class="sxs-lookup"><span data-stu-id="ce694-224">support.microsoft.com/kb/2935997/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="ce694-225">2612822</span><span class="sxs-lookup"><span data-stu-id="ce694-225">2612822</span></span></p></td>
<td align="left"><p><span data-ttu-id="ce694-226">在 MBAM 中，電腦記錄遭到拒絕</span><span class="sxs-lookup"><span data-stu-id="ce694-226">Computer Record is Rejected in MBAM</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2612822/EN-US" data-raw-source="[support.microsoft.com/kb/2612822/EN-US](https://support.microsoft.com/kb/2612822/EN-US)"><span data-ttu-id="ce694-227">support.microsoft.com/kb/2612822/EN-US</span><span class="sxs-lookup"><span data-stu-id="ce694-227">support.microsoft.com/kb/2612822/EN-US</span></span></a></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="ce694-228">相關主題</span><span class="sxs-lookup"><span data-stu-id="ce694-228">Related topics</span></span>


[<span data-ttu-id="ce694-229">關於 MBAM 2.0 SP1</span><span class="sxs-lookup"><span data-stu-id="ce694-229">About MBAM 2.0 SP1</span></span>](about-mbam-20-sp1.md)

 

 





