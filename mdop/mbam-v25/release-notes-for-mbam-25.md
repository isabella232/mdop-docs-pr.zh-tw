---
title: MBAM 2.5 版本資訊
description: MBAM 2.5 版本資訊
author: dansimp
ms.assetid: fcaf03e6-5e39-4771-af3c-a3cd468f3961
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 4bcc17d6295b14a7f3276146d5630b869b94b7f0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810881"
---
# <span data-ttu-id="f0da7-103">MBAM 2.5 版本資訊</span><span class="sxs-lookup"><span data-stu-id="f0da7-103">Release Notes for MBAM 2.5</span></span>


<span data-ttu-id="f0da7-104">若要搜尋這些版本筆記，請按 Ctrl + F。</span><span class="sxs-lookup"><span data-stu-id="f0da7-104">To search these release notes, press Ctrl+F.</span></span>

<span data-ttu-id="f0da7-105">在安裝 Microsoft BitLocker 管理和監控（MBAM）2.5 之前，請先閱讀這些版本資訊。</span><span class="sxs-lookup"><span data-stu-id="f0da7-105">Read these release notes thoroughly before you install Microsoft BitLocker Administration and Monitoring (MBAM) 2.5.</span></span> <span data-ttu-id="f0da7-106">這些版本資訊包含成功安裝 MBAM 所需的資訊，而且可能包含產品檔中不提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="f0da7-106">These release notes contain information that is required to successfully install MBAM and can contain information that is not available in the product documentation.</span></span> <span data-ttu-id="f0da7-107">如果這些版本資訊與其他 MBAM 2.5 檔不同，請考慮將最新變更設為權威性。</span><span class="sxs-lookup"><span data-stu-id="f0da7-107">If these release notes differ from other MBAM 2.5 documentation, consider the latest change to be authoritative.</span></span> <span data-ttu-id="f0da7-108">這些版本資訊取代本產品隨附的內容。</span><span class="sxs-lookup"><span data-stu-id="f0da7-108">These release notes supersede the content that is included with this product.</span></span>

## <a href="" id="---------mbam-2-5-known-issues"></a> <span data-ttu-id="f0da7-109">MBAM 2.5 已知問題</span><span class="sxs-lookup"><span data-stu-id="f0da7-109">MBAM 2.5 known issues</span></span>


<span data-ttu-id="f0da7-110">本節包含適用于 MBAM 2.5 的版本資訊。</span><span class="sxs-lookup"><span data-stu-id="f0da7-110">This section contains release notes for MBAM 2.5.</span></span>

### <span data-ttu-id="f0da7-111">在無意中以系統管理員身分執行網頁瀏覽器</span><span class="sxs-lookup"><span data-stu-id="f0da7-111">Web browser unintentionally run as administrator</span></span>

<span data-ttu-id="f0da7-112">MBAM Server 組態工具中的 [說明] 連結會導致瀏覽器視窗以系統管理員許可權開啟。</span><span class="sxs-lookup"><span data-stu-id="f0da7-112">Help links in the MBAM Server Configuration tool can cause browser windows to open with administrator rights.</span></span>

<span data-ttu-id="f0da7-113">因應措施 **：** 在流覽至其他網站前，請先啟用 Internet Explorer 增強的安全性設定（IESC）或關閉您的網頁瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="f0da7-113">**Workaround:** Enable Internet Explorer Enhanced Security Configuration (IESC) or close your web browser before navigating to other sites.</span></span>

<span data-ttu-id="f0da7-114">**記事** 這個問題已在 MBAM 2.5 SP1 中修正。</span><span class="sxs-lookup"><span data-stu-id="f0da7-114">**Note** This is fixed in MBAM 2.5 SP1.</span></span>

 

### <a href="" id="-------------mbam-reports-as-noncompliant-a-client-encrypted-with-aes-256-bit-encryption-keys-and-diffuser"></a> <span data-ttu-id="f0da7-115">將報表 MBAM 為不相容已使用 AES 256 位加密金鑰和擴散器加密的用戶端</span><span class="sxs-lookup"><span data-stu-id="f0da7-115">MBAM reports as noncompliant a client encrypted with AES 256-bit encryption keys and Diffuser</span></span>

<span data-ttu-id="f0da7-116">如果電腦已安裝 MBAM 2.5 用戶端，且是使用具有擴散器密碼強度的 AES 256 位加密，則 MBAM 用戶端會在 MBAM 合規性報告中報告為不相容。</span><span class="sxs-lookup"><span data-stu-id="f0da7-116">If a computer has the MBAM 2.5 client installed and is encrypted by using the AES 256-bit with Diffuser cipher strength, the MBAM client is reported as noncompliant in the MBAM compliance reports.</span></span>

<span data-ttu-id="f0da7-117">因應措施 **：** 在[KB2975636](https://go.microsoft.com/fwlink/?LinkId=511972)安裝此熱修復程式。</span><span class="sxs-lookup"><span data-stu-id="f0da7-117">**Workaround:** Install the hotfix at [KB2975636](https://go.microsoft.com/fwlink/?LinkId=511972).</span></span>

### <a href="" id="-------------mbam-fails-to-encrypt-a-volume-and-reports-an-error-if-you-set-a-tpm---pin-protector-on-a-tablet-device"></a> <span data-ttu-id="f0da7-118">如果您在平板電腦裝置上設定 TPM + PIN 保護器，MBAM 無法加密某個卷，並報告錯誤</span><span class="sxs-lookup"><span data-stu-id="f0da7-118">MBAM fails to encrypt a volume and reports an error if you set a TPM + PIN protector on a tablet device</span></span>

<span data-ttu-id="f0da7-119">如果使用者嘗試在平板電腦裝置上設定 TPM + PIN 保護器，MBAM 無法加密，且會報告錯誤。</span><span class="sxs-lookup"><span data-stu-id="f0da7-119">If end users try to set a TPM + PIN protector on a tablet device, MBAM fails to encrypt, and it reports an error.</span></span> <span data-ttu-id="f0da7-120">這個問題是因為平板電腦裝置沒有預啟動環境鍵盤。</span><span class="sxs-lookup"><span data-stu-id="f0da7-120">This issue occurs because tablet devices do not have a pre-boot environment keyboard.</span></span>

<span data-ttu-id="f0da7-121">因應措施 **：** 啟用 [**啟用在平板電腦上使用 [在平板電腦上預啟動鍵盤輸入**] 策略設定的 BitLocker 驗證。</span><span class="sxs-lookup"><span data-stu-id="f0da7-121">**Workaround:** Enable the **Enable use of BitLocker authentication requiring preboot keyboard input on tablets** Group Policy setting.</span></span> <span data-ttu-id="f0da7-122">此設定是 BitLocker 群組原則設定，且無法在 MBAM 群組原則範本中使用。</span><span class="sxs-lookup"><span data-stu-id="f0da7-122">This setting is a BitLocker Group Policy setting and is not available in the MBAM Group Policy Templates.</span></span>

### <span data-ttu-id="f0da7-123">所有服務帳戶都需要使用者主要名稱</span><span class="sxs-lookup"><span data-stu-id="f0da7-123">User principal name is required for all service accounts</span></span>

<span data-ttu-id="f0da7-124">您必須針對 MBAM 中的所有服務帳戶設定使用者主體名稱（UPN）。</span><span class="sxs-lookup"><span data-stu-id="f0da7-124">A user principal name (UPN) must be set for all service accounts in MBAM.</span></span> <span data-ttu-id="f0da7-125">如果您無法建立帳戶的 UPN，在設定過程中會出現錯誤訊息，指出在 Active Directory 中找不到該使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="f0da7-125">If you fail to create a UPN for an account, an error message appears during the configuration process to indicate that the user or group could not be found in Active Directory.</span></span>

<span data-ttu-id="f0da7-126">因應措施 **：** 將 UPN 新增至服務帳戶。</span><span class="sxs-lookup"><span data-stu-id="f0da7-126">**Workaround:** Add the UPN to the service account.</span></span>

### <span data-ttu-id="f0da7-127">如果用戶端電腦無法存取 Microsoft Ajax 內容傳遞網路，自助服務入口網站需要進行其他配置</span><span class="sxs-lookup"><span data-stu-id="f0da7-127">Self-Service Portal requires additional configuration if client computers cannot access Microsoft Ajax Content Delivery Network</span></span>

<span data-ttu-id="f0da7-128">如果您的用戶端電腦無法存取 Microsoft Ajax 內容傳遞網路（CDN），提供自助入口網站對某些 JavaScript 檔案所需的存取權，您必須設定自助入口網站，以參照來自易於存取之來源的 JavaScript 檔案。</span><span class="sxs-lookup"><span data-stu-id="f0da7-128">If your client computers do not have access to the Microsoft Ajax Content Delivery Network (CDN), which gives the Self-Service Portal the access that it requires to certain JavaScript files, you must configure the Self-Service Portal to reference the JavaScript files from an accessible source.</span></span> <span data-ttu-id="f0da7-129">如果您未在用戶端電腦無法存取 CDN 時設定自助入口網站，則只會顯示公司名稱和您登入的帳戶。</span><span class="sxs-lookup"><span data-stu-id="f0da7-129">If you don’t configure the Self-Service Portal when client computers cannot access CDN, only the company name and the account under which you logged on is displayed.</span></span> <span data-ttu-id="f0da7-130">不會出現錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="f0da7-130">No error message appears.</span></span>

<span data-ttu-id="f0da7-131">因應措施 **：** 安裝 MBAM 2.5 SP1。</span><span class="sxs-lookup"><span data-stu-id="f0da7-131">**Workaround:** Install MBAM 2.5 SP1.</span></span> <span data-ttu-id="f0da7-132">或遵循下列指示來設定自助入口網站：[如何在用戶端電腦無法存取 Microsoft 內容傳遞網路時，設定自助入口網站](how-to-configure-the-self-service-portal-when-client-computers-cannot-access-the-microsoft-content-delivery-network.md)。</span><span class="sxs-lookup"><span data-stu-id="f0da7-132">or configure the Self-Service Portal by following these instructions: [How to Configure the Self-Service Portal When Client Computers Cannot Access the Microsoft Content Delivery Network](how-to-configure-the-self-service-portal-when-client-computers-cannot-access-the-microsoft-content-delivery-network.md).</span></span>

### <span data-ttu-id="f0da7-133">在您升級 IIS 至 .NET Framework 4.5 之後，無法開啟自助服務入口網站與管理和監控網站</span><span class="sxs-lookup"><span data-stu-id="f0da7-133">Self-Service Portal and the Administration and Monitoring Website do not open after you upgrade IIS to .NET Framework 4.5</span></span>

<span data-ttu-id="f0da7-134">當您將網際網路資訊服務（IIS）升級至 Microsoft .NET Framework 4.5 時，系統不會開啟自助入口網站與管理與監控網站。</span><span class="sxs-lookup"><span data-stu-id="f0da7-134">When you upgrade Internet Information Services (IIS) to the Microsoft .NET Framework 4.5, the Self-Service Portal and the Administration and Monitoring Website do not open.</span></span>

<span data-ttu-id="f0da7-135">因應措施 **：** 在[您安裝 .Net Framework 4.0：「無法載入類型 ' system.servicemodel. HttpModule ' 之後](https://go.microsoft.com/fwlink/?LinkId=393568)，請參閱文章錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="f0da7-135">**Workaround:** See the article [Error message after you install the .NET Framework 4.0: "Could not load type 'System.ServiceModel.Activation.HttpModule'](https://go.microsoft.com/fwlink/?LinkId=393568).</span></span>

### <span data-ttu-id="f0da7-136">[管理及監視網站] 會在未設定報表時顯示「找不到報表」的錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="f0da7-136">Administration and Monitoring Website displays a "Report cannot be found" error message when Reports are not configured</span></span>

<span data-ttu-id="f0da7-137">如果您設定了 [管理及監視] 網站，然後嘗試先查看報表，但不需先設定報表功能，則錯誤訊息會指出找不到該報表。</span><span class="sxs-lookup"><span data-stu-id="f0da7-137">If you configure the Administration and Monitoring Website and then try to view a report without configuring the Reports feature first, an error message indicates that the report cannot be found.</span></span>

<span data-ttu-id="f0da7-138">因應措施 **：** 設定 web 應用程式之前，請先設定 [報告] 功能。</span><span class="sxs-lookup"><span data-stu-id="f0da7-138">**Workaround:** Configure the Reports feature before you configure the web applications.</span></span>

### <span data-ttu-id="f0da7-139">如果未在 SSRS 中設定 SSL，系統管理和監控網站中的報告會顯示警告</span><span class="sxs-lookup"><span data-stu-id="f0da7-139">Reports in the Administration and Monitoring Website display a warning if SSL is not configured in SSRS</span></span>

<span data-ttu-id="f0da7-140">如果 SQL Server Reporting Services （SSRS）未設定為使用安全通訊端層（SSL），當您設定 MBAM 伺服器時，會將報表功能的 URL 改為 HTTP，而不是 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="f0da7-140">If SQL Server Reporting Services (SSRS) was not configured to use Secure Socket Layer (SSL), the URL for the Reports feature will be set to HTTP instead of to HTTPS when you configure the MBAM Server.</span></span> <span data-ttu-id="f0da7-141">如果您接著開啟 [管理及監視] 網站並選取報告，就會出現下列錯誤訊息：「只會顯示安全內容」。</span><span class="sxs-lookup"><span data-stu-id="f0da7-141">If you then open the Administration and Monitoring Website and select a report, the following error message appears: "Only Secure Content is Displayed."</span></span>

<span data-ttu-id="f0da7-142">因應措施 **：** 若要顯示報表，請按一下 [**顯示所有內容**]。</span><span class="sxs-lookup"><span data-stu-id="f0da7-142">**Workaround:** To show the report, click **Show All Content**.</span></span> <span data-ttu-id="f0da7-143">若要修正此問題，請移至安裝 SQL Server Reporting Services 的 MBAM 電腦，執行**Reporting Services Configuration Manager**，然後按一下 [ **Web 服務 URL**]。</span><span class="sxs-lookup"><span data-stu-id="f0da7-143">To correct this issue, go to the MBAM computer where SQL Server Reporting Services is installed, run **Reporting Services Configuration Manager**, and then click **Web Service URL**.</span></span> <span data-ttu-id="f0da7-144">針對伺服器選取適當的 SSL 憑證，輸入適當的 SSL 埠（預設埠是443），**然後按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="f0da7-144">Select the appropriate SSL certificate for the server, enter the appropriate SSL port (the default port is 443), and then click **Apply**.</span></span>

### <span data-ttu-id="f0da7-145">按一下 [BitLocker 規範摘要] 報告中的 [上一步] 可能會引發錯誤</span><span class="sxs-lookup"><span data-stu-id="f0da7-145">Clicking "Back" in the BitLocker Compliance Summary report might throw an error</span></span>

<span data-ttu-id="f0da7-146">如果您向下切入 BitLocker 相容性摘要報告，然後按一下 SSRS 報表中的**Back**連結，可能會引發錯誤。</span><span class="sxs-lookup"><span data-stu-id="f0da7-146">If you drill down into a BitLocker Compliance Summary report, and then click the **Back** link in the SSRS report, an error might be thrown.</span></span>

<span data-ttu-id="f0da7-147">因應措施 **：** 所有.</span><span class="sxs-lookup"><span data-stu-id="f0da7-147">**Workaround:** None.</span></span>

### <span data-ttu-id="f0da7-148">只有使用中的空間加密無法正常運作</span><span class="sxs-lookup"><span data-stu-id="f0da7-148">Used Space Only Encryption does not work correctly</span></span>

<span data-ttu-id="f0da7-149">如果您在安裝 MBAM 用戶端後第一次將電腦加密，且已將群組原則設定設為只執行加密，請 MBAM 錯誤地加密整個磁片，而不是只加密磁片的已使用空間。</span><span class="sxs-lookup"><span data-stu-id="f0da7-149">If you encrypt a computer for the first time after you install the MBAM Client, and you have configured a Group Policy setting to implement Used Space Only encryption, MBAM erroneously encrypts the entire disk instead of encrypting only the disk’s used space.</span></span> <span data-ttu-id="f0da7-150">如果電腦已在您安裝 MBAM 用戶端且已設定相同的群組原則設定的情況下經過加密，而您已設定相同的群組原則設定，MBAM 會報告磁片磁碟機已正確加密，且不會嘗試重新加密磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="f0da7-150">If a computer is already encrypted with Used Space Only when you install the MBAM Client, and you have configured the same Group Policy setting, MBAM reports that the drive is encrypted correctly, and does not try to re-encrypt the drive.</span></span>

<span data-ttu-id="f0da7-151">因應措施 **：** 所有.</span><span class="sxs-lookup"><span data-stu-id="f0da7-151">**Workaround:** None.</span></span>

### <span data-ttu-id="f0da7-152">密碼強度在 BitLocker 電腦合規性報告上無法正確顯示</span><span class="sxs-lookup"><span data-stu-id="f0da7-152">Cipher strength displays incorrectly on the BitLocker Computer Compliance report</span></span>

<span data-ttu-id="f0da7-153">如果您沒有在 [**選擇磁片磁碟機加密方法] 與 [密碼強度**] 群群組原則物件中設定特定的密碼強度，即使密碼強度使用預設的128位加密，Configuration Manager 整合拓撲中的 BitLocker 電腦合規性報告仍會顯示密碼強度 "unknown"。</span><span class="sxs-lookup"><span data-stu-id="f0da7-153">If you do not set a specific cipher strength in the **Choose drive encryption method and cipher strength** Group Policy Object, the BitLocker Computer Compliance report in the Configuration Manager Integration topology always displays "unknown" for the cipher strength, even when the cipher strength uses the default of 128-bit encryption.</span></span> <span data-ttu-id="f0da7-154">如果您在群組原則物件中設定特定的密碼強度，報告會顯示正確的密碼強度。</span><span class="sxs-lookup"><span data-stu-id="f0da7-154">The report displays the correct cipher strength if you set a specific cipher strength in the Group Policy Object.</span></span>

<span data-ttu-id="f0da7-155">因應措施 **：** 在 [**選擇磁片磁碟機加密方法及密碼強度**] 群群組原則物件中，一定要設定特定的密碼強度。</span><span class="sxs-lookup"><span data-stu-id="f0da7-155">**Workaround:** Always set a specific cipher strength in the **Choose drive encryption method and cipher strength** Group Policy Object.</span></span>

### <span data-ttu-id="f0da7-156">依磁片磁碟機類型進行合規性狀態發佈會在您更新設定專案後顯示舊資料</span><span class="sxs-lookup"><span data-stu-id="f0da7-156">Compliance Status Distribution by Drive Type displays old data after you update configuration items</span></span>

<span data-ttu-id="f0da7-157">更新 SystemCenter2012 ConfigurationManager 中的 MBAM 設定專案之後，由 BitLocker Enterprise 合規性儀表板上的 [磁碟機類型] 橫條圖顯示的 [遵從性狀態發佈] 會顯示以舊版本的設定項目資訊為基礎的資料。</span><span class="sxs-lookup"><span data-stu-id="f0da7-157">After you update MBAM configuration items in SystemCenter2012 ConfigurationManager, the Compliance Status Distribution By Drive Type bar chart on the BitLocker Enterprise Compliance Dashboard shows data that is based on information from old versions of the configuration items.</span></span>

<span data-ttu-id="f0da7-158">因應措施 **：** 所有.</span><span class="sxs-lookup"><span data-stu-id="f0da7-158">**Workaround:** None.</span></span> <span data-ttu-id="f0da7-159">不支援修改 MBAM 設定專案，而且報告可能不會如預期所示。</span><span class="sxs-lookup"><span data-stu-id="f0da7-159">Modification of the MBAM configuration items is not supported, and the report might not appear as expected.</span></span>

### <span data-ttu-id="f0da7-160">[增強的安全性設定] 可能會導致報告無法正確顯示錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="f0da7-160">Enhanced Security Configuration might cause reports to display an error message incorrectly</span></span>

<span data-ttu-id="f0da7-161">如果開啟 Internet Explorer 增強的安全性設定（ESC），當您嘗試在 MBAM 伺服器上查看報告時，可能會出現「拒絕存取」錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="f0da7-161">If Internet Explorer Enhanced Security Configuration (ESC) is turned on, an "Access Denied" error message might appear when you try to view reports on the MBAM Server.</span></span> <span data-ttu-id="f0da7-162">根據預設，ESC 會開啟以保護伺服器，方法是將伺服器暴露在網頁內容和應用程式腳本中可能會發生的可能攻擊。</span><span class="sxs-lookup"><span data-stu-id="f0da7-162">By default, ESC is turned on to protect the server by decreasing the server’s exposure to potential attacks that can occur through web content and application scripts.</span></span>

<span data-ttu-id="f0da7-163">因應措施 **：** 當您嘗試在 MBAM 伺服器上查看報告時，如果出現「拒絕存取」錯誤訊息，您可以在影像中設定群組原則物件或手動變更預設值，以停用增強的安全性設定。</span><span class="sxs-lookup"><span data-stu-id="f0da7-163">**Workaround:** If the "Access Denied" error message appears when you try to view reports on the MBAM Server, you can set a Group Policy Object or change the default manually in your image to disable Enhanced Security Configuration.</span></span> <span data-ttu-id="f0da7-164">您也可以在未啟用 ESC 的另一部電腦上，查看報表。</span><span class="sxs-lookup"><span data-stu-id="f0da7-164">You can also alternatively view the reports from another computer on which ESC is not enabled.</span></span>

## <a href="" id="hotfixes-and-knowledge-base-articles-for-mbam-2-5-"></a><span data-ttu-id="f0da7-165">MBAM 2.5 的修補程式和知識庫文章</span><span class="sxs-lookup"><span data-stu-id="f0da7-165">Hotfixes and Knowledge Base articles for MBAM 2.5</span></span>


<span data-ttu-id="f0da7-166">下表列出 MBAM 2.5 的修正程式和知識庫文章。</span><span class="sxs-lookup"><span data-stu-id="f0da7-166">This table lists the hotfixes and KB articles for MBAM 2.5.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong><span data-ttu-id="f0da7-167">知識庫文章</span><span class="sxs-lookup"><span data-stu-id="f0da7-167">KB Article</span></span></strong></th>
<th align="left"><span data-ttu-id="f0da7-168">Title</span><span class="sxs-lookup"><span data-stu-id="f0da7-168">Title</span></span></th>
<th align="left"><strong><span data-ttu-id="f0da7-169">連結</span><span class="sxs-lookup"><span data-stu-id="f0da7-169">Link</span></span></strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f0da7-170">2975636</span><span class="sxs-lookup"><span data-stu-id="f0da7-170">2975636</span></span></p></td>
<td align="left"><p><span data-ttu-id="f0da7-171">Microsoft BitLocker 管理和監視2.5 的修補程式套件1</span><span class="sxs-lookup"><span data-stu-id="f0da7-171">Hotfix Package 1 for Microsoft BitLocker Administration and Monitoring 2.5</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2975636/EN-US" data-raw-source="[support.microsoft.com/kb/2975636/EN-US](https://support.microsoft.com/kb/2975636/EN-US)"><span data-ttu-id="f0da7-172">support.microsoft.com/kb/2975636/EN-US</span><span class="sxs-lookup"><span data-stu-id="f0da7-172">support.microsoft.com/kb/2975636/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f0da7-173">3015477</span><span class="sxs-lookup"><span data-stu-id="f0da7-173">3015477</span></span></p></td>
<td align="left"><p><span data-ttu-id="f0da7-174">BitLocker 管理和監視2.5 的修補程式套件2</span><span class="sxs-lookup"><span data-stu-id="f0da7-174">Hotfix Package 2 for BitLocker Administration and Monitoring 2.5</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/3015477" data-raw-source="[support.microsoft.com/kb/3015477](https://support.microsoft.com/kb/3015477)"><span data-ttu-id="f0da7-175">support.microsoft.com/kb/3015477</span><span class="sxs-lookup"><span data-stu-id="f0da7-175">support.microsoft.com/kb/3015477</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f0da7-176">3011022</span><span class="sxs-lookup"><span data-stu-id="f0da7-176">3011022</span></span></p></td>
<td align="left"><p><span data-ttu-id="f0da7-177">如果 SSRS 實例的名稱包含底線，MBAM 2.5 安裝或 Configuration Manager 報告就會失敗</span><span class="sxs-lookup"><span data-stu-id="f0da7-177">MBAM 2.5 installation or Configuration Manager reporting fails if the name of SSRS instance contains an underscore</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/3011022/EN-US" data-raw-source="[support.microsoft.com/kb/3011022/EN-US](https://support.microsoft.com/kb/3011022/EN-US)"><span data-ttu-id="f0da7-178">support.microsoft.com/kb/3011022/EN-US</span><span class="sxs-lookup"><span data-stu-id="f0da7-178">support.microsoft.com/kb/3011022/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f0da7-179">2756402</span><span class="sxs-lookup"><span data-stu-id="f0da7-179">2756402</span></span></p></td>
<td align="left"><p><span data-ttu-id="f0da7-180">事件描述中的 MBAM 用戶端將無法使用事件 ID 4 和錯誤碼0x8004100E</span><span class="sxs-lookup"><span data-stu-id="f0da7-180">MBAM client would fail with Event ID 4 and error code 0x8004100E in the Event description</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2756402/EN-US" data-raw-source="[support.microsoft.com/kb/2756402/EN-US](https://support.microsoft.com/kb/2756402/EN-US)"><span data-ttu-id="f0da7-181">support.microsoft.com/kb/2756402/EN-US</span><span class="sxs-lookup"><span data-stu-id="f0da7-181">support.microsoft.com/kb/2756402/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f0da7-182">2639518</span><span class="sxs-lookup"><span data-stu-id="f0da7-182">2639518</span></span></p></td>
<td align="left"><p><span data-ttu-id="f0da7-183">在 MBAM 中開啟企業或電腦合規性報告時發生錯誤</span><span class="sxs-lookup"><span data-stu-id="f0da7-183">Error opening Enterprise or Computer Compliance Reports in MBAM</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2639518/EN-US" data-raw-source="[support.microsoft.com/kb/2639518/EN-US](https://support.microsoft.com/kb/2639518/EN-US)"><span data-ttu-id="f0da7-184">support.microsoft.com/kb/2639518/EN-US</span><span class="sxs-lookup"><span data-stu-id="f0da7-184">support.microsoft.com/kb/2639518/EN-US</span></span></a></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f0da7-185">2870842</span><span class="sxs-lookup"><span data-stu-id="f0da7-185">2870842</span></span></p></td>
<td align="left"><p><span data-ttu-id="f0da7-186">MBAM 2.0 安裝程式在 Configuration Manager 整合案例中使用 SQL Server 2008 失敗</span><span class="sxs-lookup"><span data-stu-id="f0da7-186">MBAM 2.0 Setup fails during Configuration Manager Integration Scenario with SQL Server 2008</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2870842/EN-US" data-raw-source="[support.microsoft.com/kb/2870842/EN-US](https://support.microsoft.com/kb/2870842/EN-US)"><span data-ttu-id="f0da7-187">support.microsoft.com/kb/2870842/EN-US</span><span class="sxs-lookup"><span data-stu-id="f0da7-187">support.microsoft.com/kb/2870842/EN-US</span></span></a></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f0da7-188">2975472</span><span class="sxs-lookup"><span data-stu-id="f0da7-188">2975472</span></span></p></td>
<td align="left"><p><span data-ttu-id="f0da7-189">當許多 MBAM 用戶端連線至 MBAM 復原資料庫時，會發生 SQL 鎖死</span><span class="sxs-lookup"><span data-stu-id="f0da7-189">SQL deadlocks when many MBAM clients connect to the MBAM recovery database</span></span></p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2975472/EN-US" data-raw-source="[support.microsoft.com/kb/2975472/EN-US](https://support.microsoft.com/kb/2975472/EN-US)"><span data-ttu-id="f0da7-190">support.microsoft.com/kb/2975472/EN-US</span><span class="sxs-lookup"><span data-stu-id="f0da7-190">support.microsoft.com/kb/2975472/EN-US</span></span></a></p></td>
</tr>
</tbody>
</table>

 


## <span data-ttu-id="f0da7-191">相關主題</span><span class="sxs-lookup"><span data-stu-id="f0da7-191">Related topics</span></span>


[<span data-ttu-id="f0da7-192">關於 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="f0da7-192">About MBAM 2.5</span></span>](about-mbam-25.md)

 

## <span data-ttu-id="f0da7-193">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="f0da7-193">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="f0da7-194">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="f0da7-194">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span>
- <span data-ttu-id="f0da7-195">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="f0da7-195">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





