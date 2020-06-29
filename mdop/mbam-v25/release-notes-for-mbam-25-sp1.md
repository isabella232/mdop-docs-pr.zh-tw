---
title: MBAM 2.5 SP1 版本資訊
description: MBAM 2.5 SP1 版本資訊
author: dansimp
ms.assetid: 3ac424c8-c490-4d62-aba4-1b462c02e962
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 09/06/2017
ms.openlocfilehash: 837892897aeca341433de54aca1228c0faeee124
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810886"
---
# <span data-ttu-id="42d9b-103">MBAM 2.5 SP1 版本資訊</span><span class="sxs-lookup"><span data-stu-id="42d9b-103">Release Notes for MBAM 2.5 SP1</span></span>


<span data-ttu-id="42d9b-104">若要搜尋這些版本筆記，請按 Ctrl + F。</span><span class="sxs-lookup"><span data-stu-id="42d9b-104">To search these release notes, press Ctrl+F.</span></span>

<span data-ttu-id="42d9b-105">在安裝 Microsoft BitLocker 管理與監控（MBAM） 2.5 SP1 之前，請先閱讀這些版本資訊。</span><span class="sxs-lookup"><span data-stu-id="42d9b-105">Read these release notes thoroughly before you install Microsoft BitLocker Administration and Monitoring (MBAM) 2.5 SP1.</span></span> <span data-ttu-id="42d9b-106">這些版本資訊包含成功安裝 MBAM 所需的資訊，而且可能包含產品檔中不提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="42d9b-106">These release notes contain information that is required to successfully install MBAM and can contain information that is not available in the product documentation.</span></span> <span data-ttu-id="42d9b-107">如果這些版本資訊與其他 MBAM 2.5 SP1 檔不同，請考慮將最新變更設為權威性。</span><span class="sxs-lookup"><span data-stu-id="42d9b-107">If these release notes differ from other MBAM 2.5 SP1 documentation, consider the latest change to be authoritative.</span></span> <span data-ttu-id="42d9b-108">這些版本資訊取代本產品隨附的內容。</span><span class="sxs-lookup"><span data-stu-id="42d9b-108">These release notes supersede the content that is included with this product.</span></span>

## <a href="" id="---------mbam-2-5-sp1-known-issues"></a> <span data-ttu-id="42d9b-109">MBAM 2.5 SP1 已知問題</span><span class="sxs-lookup"><span data-stu-id="42d9b-109">MBAM 2.5 SP1 known issues</span></span>


<span data-ttu-id="42d9b-110">本節包含適用于 MBAM 2.5 SP1 的版本資訊。</span><span class="sxs-lookup"><span data-stu-id="42d9b-110">This section contains release notes for MBAM 2.5 SP1.</span></span>

### <a href="" id="powershell-read-ad--cmdlets-do-not-provide-feedback-if-user-does-not-have-sufficient-rights"></a><span data-ttu-id="42d9b-111">PowerShell Read-AD \ \* Cmdlet 不會在使用者沒有足夠許可權的情況中提供意見反應</span><span class="sxs-lookup"><span data-stu-id="42d9b-111">PowerShell Read-AD\* cmdlets do not provide feedback if user does not have sufficient rights</span></span>

<span data-ttu-id="42d9b-112">如果您嘗試使用 PowerShell Read-AD \ \* Cmdlet MBAM 伺服器沒有讀取 Active Directory 復原資訊的使用者權利，或無法讀取 TPM 資訊，則 Cmdlet 不會提供任何錯誤或警告的使用者。</span><span class="sxs-lookup"><span data-stu-id="42d9b-112">If a user trying to use the PowerShell Read-AD\* cmdlets for the MBAM Server does not have user rights to read the Active Directory recovery information or to read the TPM information, the cmdlets will not provide the user with any error or warning.</span></span>

<span data-ttu-id="42d9b-113">因應措施 **：** 如果您擁有所需的使用者許可權，請只使用 PowerShell Read AD \ \* Cmdlet。</span><span class="sxs-lookup"><span data-stu-id="42d9b-113">**Workaround:** Only use the PowerShell Read-AD\* cmdlets if you have the required user rights.</span></span>

### <span data-ttu-id="42d9b-114">MBAM Active Directory （AD）遷移 Cmdlet 不會檢索大量恢復資訊</span><span class="sxs-lookup"><span data-stu-id="42d9b-114">MBAM Active Directory (AD) Migration cmdlets do not retrieve volume recovery information</span></span>

<span data-ttu-id="42d9b-115">MBAM Active Directory （AD）遷移 Cmdlet 無法在組織單位（Ou）中檢索電腦的大量復原資訊（如果該反斜線字元（/）是組織單位名稱的一部分）。</span><span class="sxs-lookup"><span data-stu-id="42d9b-115">MBAM Active Directory (AD) Migration cmdlets fail to retrieve volume recovery information for computers in organizational units (OUs) if the forward slash character (/) is part of the OU name.</span></span> <span data-ttu-id="42d9b-116">當遇到此錯誤時，會發生重複的 AD 拉出，且有管線終止錯誤。</span><span class="sxs-lookup"><span data-stu-id="42d9b-116">Repeated AD pulls will fail with a pipeline terminating error when this error is encountered.</span></span>

<span data-ttu-id="42d9b-117">**技術詳細資料：** 執行命令時，您會看到這個錯誤：</span><span class="sxs-lookup"><span data-stu-id="42d9b-117">**Technical Details:** You will see this error when running the command:</span></span>

``` syntax
Read-ADRecoveryInformation : Unknown error (0x80005000)
At line:1 char:1
+ Read-ADRecoveryInformation -Server "…" -SearchBase " ...
+ ~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~~
    + CategoryInfo          : NotSpecified: (:) [Read-ADRecoveryInformation], COMException
    + FullyQualifiedErrorId : System.Runtime.InteropServices.COMException,Microsoft.Mbam.Server.Commands.ADPullCommands.ReadADRecoveryInformationCommand
```

<span data-ttu-id="42d9b-118">此外，例外狀況堆疊追蹤 `Error[0].Exception.StackTrace` 看起來會像這樣：</span><span class="sxs-lookup"><span data-stu-id="42d9b-118">In addition, the Exception stack trace `Error[0].Exception.StackTrace` will look like this:</span></span>

``` syntax
   at System.DirectoryServices.DirectoryEntry.Bind(Boolean throwIfFail)
   at System.DirectoryServices.DirectoryEntry.Bind()
   at System.DirectoryServices.DirectoryEntry.get_AdsObject()
   at System.DirectoryServices.PropertyValueCollection.PopulateList()
   at System.DirectoryServices.PropertyValueCollection..ctor(DirectoryEntry entry, String propertyName)
   at System.DirectoryServices.PropertyCollection.get_Item(String propertyName)
   at Microsoft.Mbam.Server.Commands.ADPullCommands.ReadCore.VerifySettingsConnectivity()
   at Microsoft.Mbam.Server.Commands.ADPullCommands.ReadCore.ExecuteRead()
   at Microsoft.Mbam.Server.Commands.ADPullCommands.ReadADInformationBase.ProcessRecord()
   at System.Management.Automation.CommandProcessor.ProcessRecord()
```

<span data-ttu-id="42d9b-119">因應措施 **：** 若要解決此問題，請執行下列其中一項工作：</span><span class="sxs-lookup"><span data-stu-id="42d9b-119">**Workaround:** Perform one of these tasks to resolve this situation:</span></span>

-   <span data-ttu-id="42d9b-120">重新命名 OU 以移除正斜杠字元，然後執行腳本。</span><span class="sxs-lookup"><span data-stu-id="42d9b-120">Rename the OU to remove the forward slash character and then run the script.</span></span>

-   <span data-ttu-id="42d9b-121">若要從備份程式中排除任何有問題的 OU，請找出名稱不含正斜線字元的 Ou 清單。</span><span class="sxs-lookup"><span data-stu-id="42d9b-121">To exclude any problematic OU from the backup process, find a list of OUs whose names do not contain the forward slash character.</span></span> <span data-ttu-id="42d9b-122">在這些 Ou 上執行腳本（一次一個 OU）。</span><span class="sxs-lookup"><span data-stu-id="42d9b-122">Run the script on these OUs, one OU at a time.</span></span>

### <a href="" id="-------------mbam-fails-to-encrypt-a-volume-and-reports-an-error-if-you-set-a-tpm---pin-protector-on-a-tablet-device"></a> <span data-ttu-id="42d9b-123">如果您在平板電腦裝置上設定 TPM + PIN 保護器，MBAM 無法加密某個卷，並報告錯誤</span><span class="sxs-lookup"><span data-stu-id="42d9b-123">MBAM fails to encrypt a volume and reports an error if you set a TPM + PIN protector on a tablet device</span></span>

<span data-ttu-id="42d9b-124">如果使用者嘗試在平板電腦裝置上設定 TPM + PIN 保護器，MBAM 無法加密，且會報告錯誤。</span><span class="sxs-lookup"><span data-stu-id="42d9b-124">If end users try to set a TPM + PIN protector on a tablet device, MBAM fails to encrypt, and it reports an error.</span></span> <span data-ttu-id="42d9b-125">這個問題是因為平板電腦裝置沒有預啟動環境鍵盤。</span><span class="sxs-lookup"><span data-stu-id="42d9b-125">This issue occurs because tablet devices do not have a pre-boot environment keyboard.</span></span>

<span data-ttu-id="42d9b-126">因應措施 **：** 啟用 [**啟用在平板電腦上使用 [在平板電腦上預啟動鍵盤輸入**] 策略設定的 BitLocker 驗證。</span><span class="sxs-lookup"><span data-stu-id="42d9b-126">**Workaround:** Enable the **Enable use of BitLocker authentication requiring preboot keyboard input on tablets** Group Policy setting.</span></span> <span data-ttu-id="42d9b-127">此設定是 BitLocker 群組原則設定，且無法在 MBAM 群組原則範本中使用。</span><span class="sxs-lookup"><span data-stu-id="42d9b-127">This setting is a BitLocker Group Policy setting and is not available in the MBAM Group Policy Templates.</span></span>

### <span data-ttu-id="42d9b-128">所有服務帳戶都需要使用者主要名稱</span><span class="sxs-lookup"><span data-stu-id="42d9b-128">User principal name is required for all service accounts</span></span>

<span data-ttu-id="42d9b-129">您必須針對 MBAM 中的所有服務帳戶設定使用者主體名稱（UPN）。</span><span class="sxs-lookup"><span data-stu-id="42d9b-129">A user principal name (UPN) must be set for all service accounts in MBAM.</span></span> <span data-ttu-id="42d9b-130">如果您無法建立帳戶的 UPN，在設定過程中會出現錯誤訊息，指出在 Active Directory 中找不到該使用者或群組。</span><span class="sxs-lookup"><span data-stu-id="42d9b-130">If you fail to create a UPN for an account, an error message appears during the configuration process to indicate that the user or group could not be found in Active Directory.</span></span>

<span data-ttu-id="42d9b-131">因應措施 **：** 將 UPN 新增至服務帳戶。</span><span class="sxs-lookup"><span data-stu-id="42d9b-131">**Workaround:** Add the UPN to the service account.</span></span>

### <span data-ttu-id="42d9b-132">在您升級 IIS 至 .NET Framework 4.5 之後，無法開啟自助服務入口網站與管理和監控網站</span><span class="sxs-lookup"><span data-stu-id="42d9b-132">Self-Service Portal and the Administration and Monitoring Website do not open after you upgrade IIS to .NET Framework 4.5</span></span>

<span data-ttu-id="42d9b-133">當您將網際網路資訊服務（IIS）升級至 Microsoft .NET Framework 4.5 時，系統不會開啟自助入口網站與管理與監控網站。</span><span class="sxs-lookup"><span data-stu-id="42d9b-133">When you upgrade Internet Information Services (IIS) to the Microsoft .NET Framework 4.5, the Self-Service Portal and the Administration and Monitoring Website do not open.</span></span>

<span data-ttu-id="42d9b-134">因應措施 **：** 在[您安裝 .Net Framework 4.0：「無法載入類型 ' system.servicemodel. HttpModule ' 之後](https://go.microsoft.com/fwlink/?LinkId=393568)，請參閱文章錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="42d9b-134">**Workaround:** See the article [Error message after you install the .NET Framework 4.0: "Could not load type 'System.ServiceModel.Activation.HttpModule'](https://go.microsoft.com/fwlink/?LinkId=393568).</span></span>

### <span data-ttu-id="42d9b-135">[管理及監視網站] 會在未設定報表時顯示「找不到報表」的錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="42d9b-135">Administration and Monitoring Website displays a "Report cannot be found" error message when Reports are not configured</span></span>

<span data-ttu-id="42d9b-136">如果您設定了 [管理及監視] 網站，然後嘗試先查看報表，但不需先設定報表功能，則錯誤訊息會指出找不到該報表。</span><span class="sxs-lookup"><span data-stu-id="42d9b-136">If you configure the Administration and Monitoring Website and then try to view a report without configuring the Reports feature first, an error message indicates that the report cannot be found.</span></span>

<span data-ttu-id="42d9b-137">因應措施 **：** 設定 web 應用程式之前，請先設定 [報告] 功能。</span><span class="sxs-lookup"><span data-stu-id="42d9b-137">**Workaround:** Configure the Reports feature before you configure the web applications.</span></span>

### <span data-ttu-id="42d9b-138">如果未在 SSRS 中設定 SSL，系統管理和監控網站中的報告會顯示警告</span><span class="sxs-lookup"><span data-stu-id="42d9b-138">Reports in the Administration and Monitoring Website display a warning if SSL is not configured in SSRS</span></span>

<span data-ttu-id="42d9b-139">如果 SQL Server Reporting Services （SSRS）未設定為使用安全通訊端層（SSL），當您設定 MBAM 伺服器時，會將報表功能的 URL 改為 HTTP，而不是 HTTPS。</span><span class="sxs-lookup"><span data-stu-id="42d9b-139">If SQL Server Reporting Services (SSRS) was not configured to use Secure Socket Layer (SSL), the URL for the Reports feature will be set to HTTP instead of to HTTPS when you configure the MBAM Server.</span></span> <span data-ttu-id="42d9b-140">如果您接著開啟 [管理及監視] 網站並選取報告，就會出現下列錯誤訊息：「只會顯示安全內容」。</span><span class="sxs-lookup"><span data-stu-id="42d9b-140">If you then open the Administration and Monitoring Website and select a report, the following error message appears: "Only Secure Content is Displayed."</span></span>

<span data-ttu-id="42d9b-141">因應措施 **：** 若要顯示報表，請按一下 [**顯示所有內容**]。</span><span class="sxs-lookup"><span data-stu-id="42d9b-141">**Workaround:** To show the report, click **Show All Content**.</span></span> <span data-ttu-id="42d9b-142">若要修正此問題，請移至安裝 SQL Server Reporting Services 的 MBAM 電腦，執行**Reporting Services Configuration Manager**，然後按一下 [ **Web 服務 URL**]。</span><span class="sxs-lookup"><span data-stu-id="42d9b-142">To correct this issue, go to the MBAM computer where SQL Server Reporting Services is installed, run **Reporting Services Configuration Manager**, and then click **Web Service URL**.</span></span> <span data-ttu-id="42d9b-143">針對伺服器選取適當的 SSL 憑證，輸入適當的 SSL 埠（預設埠是443），**然後按一下 [** 套用]。</span><span class="sxs-lookup"><span data-stu-id="42d9b-143">Select the appropriate SSL certificate for the server, enter the appropriate SSL port (the default port is 443), and then click **Apply**.</span></span>

### <span data-ttu-id="42d9b-144">按一下 [BitLocker 規範摘要] 報告中的 [上一步] 可能會引發錯誤</span><span class="sxs-lookup"><span data-stu-id="42d9b-144">Clicking "Back" in the BitLocker Compliance Summary report might throw an error</span></span>

<span data-ttu-id="42d9b-145">如果您向下切入 BitLocker 相容性摘要報告，然後按一下 SSRS 報表中的**Back**連結，可能會引發錯誤。</span><span class="sxs-lookup"><span data-stu-id="42d9b-145">If you drill down into a BitLocker Compliance Summary report, and then click the **Back** link in the SSRS report, an error might be thrown.</span></span>

<span data-ttu-id="42d9b-146">因應措施 **：** 所有.</span><span class="sxs-lookup"><span data-stu-id="42d9b-146">**Workaround:** None.</span></span>

### <span data-ttu-id="42d9b-147">密碼強度在 BitLocker 電腦合規性報告上無法正確顯示</span><span class="sxs-lookup"><span data-stu-id="42d9b-147">Cipher strength displays incorrectly on the BitLocker Computer Compliance report</span></span>

<span data-ttu-id="42d9b-148">如果您沒有在 [**選擇磁片磁碟機加密方法] 與 [密碼強度**] 群群組原則物件中設定特定的密碼強度，即使密碼強度使用預設的128位加密，Configuration Manager 整合拓撲中的 BitLocker 電腦合規性報告仍會顯示密碼強度 "unknown"。</span><span class="sxs-lookup"><span data-stu-id="42d9b-148">If you do not set a specific cipher strength in the **Choose drive encryption method and cipher strength** Group Policy Object, the BitLocker Computer Compliance report in the Configuration Manager Integration topology always displays "unknown" for the cipher strength, even when the cipher strength uses the default of 128-bit encryption.</span></span> <span data-ttu-id="42d9b-149">如果您在群組原則物件中設定特定的密碼強度，報告會顯示正確的密碼強度。</span><span class="sxs-lookup"><span data-stu-id="42d9b-149">The report displays the correct cipher strength if you set a specific cipher strength in the Group Policy Object.</span></span>

<span data-ttu-id="42d9b-150">因應措施 **：** 在 [**選擇磁片磁碟機加密方法及密碼強度**] 群群組原則物件中，一定要設定特定的密碼強度。</span><span class="sxs-lookup"><span data-stu-id="42d9b-150">**Workaround:** Always set a specific cipher strength in the **Choose drive encryption method and cipher strength** Group Policy Object.</span></span>

### <span data-ttu-id="42d9b-151">依磁片磁碟機類型進行合規性狀態發佈會在您更新設定專案後顯示舊資料</span><span class="sxs-lookup"><span data-stu-id="42d9b-151">Compliance Status Distribution By Drive Type displays old data after you update configuration items</span></span>

<span data-ttu-id="42d9b-152">更新 SystemCenter2012 ConfigurationManager 中的 MBAM 設定專案之後，由 BitLocker Enterprise 合規性儀表板上的 [磁碟機類型] 橫條圖顯示的 [遵從性狀態發佈] 會顯示以舊版本的設定項目資訊為基礎的資料。</span><span class="sxs-lookup"><span data-stu-id="42d9b-152">After you update MBAM configuration items in SystemCenter2012 ConfigurationManager, the Compliance Status Distribution By Drive Type bar chart on the BitLocker Enterprise Compliance Dashboard shows data that is based on information from old versions of the configuration items.</span></span>

<span data-ttu-id="42d9b-153">因應措施 **：** 所有.</span><span class="sxs-lookup"><span data-stu-id="42d9b-153">**Workaround:** None.</span></span> <span data-ttu-id="42d9b-154">不支援修改 MBAM 設定專案，而且報告可能不會如預期所示。</span><span class="sxs-lookup"><span data-stu-id="42d9b-154">Modification of the MBAM configuration items is not supported, and the report might not appear as expected.</span></span>

### <span data-ttu-id="42d9b-155">[增強的安全性設定] 可能會導致報告無法正確顯示錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="42d9b-155">Enhanced Security Configuration might cause reports to display an error message incorrectly</span></span>

<span data-ttu-id="42d9b-156">如果開啟 Internet Explorer 增強的安全性設定（ESC），當您嘗試在 MBAM 伺服器上查看報告時，可能會出現「拒絕存取」錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="42d9b-156">If Internet Explorer Enhanced Security Configuration (ESC) is turned on, an "Access Denied" error message might appear when you try to view reports on the MBAM Server.</span></span> <span data-ttu-id="42d9b-157">根據預設，ESC 會開啟以保護伺服器，方法是將伺服器暴露在網頁內容和應用程式腳本中可能會發生的可能攻擊。</span><span class="sxs-lookup"><span data-stu-id="42d9b-157">By default, ESC is turned on to protect the server by decreasing the server’s exposure to potential attacks that can occur through web content and application scripts.</span></span>

<span data-ttu-id="42d9b-158">因應措施 **：** 當您嘗試在 MBAM 伺服器上查看報告時，如果出現「拒絕存取」錯誤訊息，您可以在影像中設定群組原則物件或手動變更預設值，以停用增強的安全性設定。</span><span class="sxs-lookup"><span data-stu-id="42d9b-158">**Workaround:** If the "Access Denied" error message appears when you try to view reports on the MBAM Server, you can set a Group Policy Object or change the default manually in your image to disable Enhanced Security Configuration.</span></span> <span data-ttu-id="42d9b-159">您也可以在未啟用 ESC 的另一部電腦上，查看報表。</span><span class="sxs-lookup"><span data-stu-id="42d9b-159">You can also alternatively view the reports from another computer on which ESC is not enabled.</span></span>

### <span data-ttu-id="42d9b-160">支援 Bitlocker XTS-AES 加密演算法</span><span class="sxs-lookup"><span data-stu-id="42d9b-160">Support for Bitlocker XTS-AES encryption algorithm</span></span>
<span data-ttu-id="42d9b-161">Bitlocker 已在 Windows 10 版本1511中新增 XTS-AES 加密演算法的支援。</span><span class="sxs-lookup"><span data-stu-id="42d9b-161">Bitlocker added support for the XTS-AES encryption algorithm in Windows 10, version 1511.</span></span> <span data-ttu-id="42d9b-162">使用 HF02、MBAM 新增此 Bitlocker 選項和 HF04 中的用戶端支援，即會新增伺服器端支援。</span><span class="sxs-lookup"><span data-stu-id="42d9b-162">With HF02, MBAM added client support for this Bitlocker option and in HF04, the server-side support was added.</span></span> <span data-ttu-id="42d9b-163">不過，有一個已知的限制：</span><span class="sxs-lookup"><span data-stu-id="42d9b-163">However, there is one known limitation:</span></span>

* <span data-ttu-id="42d9b-164">客戶必須在同一部電腦上使用相同的作業系統和資料量加密強度。</span><span class="sxs-lookup"><span data-stu-id="42d9b-164">Customers must use the same encryption strength for OS and data volumes on the same machine.</span></span>
<span data-ttu-id="42d9b-165">如果使用不同的加密強度，MBAM 會將電腦報告為**不相容**。</span><span class="sxs-lookup"><span data-stu-id="42d9b-165">If different encryption strengths are used, MBAM will report the machine as **non-compliant**.</span></span>

### <span data-ttu-id="42d9b-166">自助服務入口網站會自動在金鑰識別碼專案上新增 "-"</span><span class="sxs-lookup"><span data-stu-id="42d9b-166">Self-Service Portal automatically adds "-" on Key ID entry</span></span>
<span data-ttu-id="42d9b-167">從 HF02，MBAM 自助服務入口網站會自動在金鑰識別碼專案加上 '-」。</span><span class="sxs-lookup"><span data-stu-id="42d9b-167">As of HF02, the MBAM Self-Service Portal automatically adds the '-' on Key ID entry.</span></span>  
<span data-ttu-id="42d9b-168">**注意：** 必須重新佈建服務器，才能使 JAVAscript 生效。</span><span class="sxs-lookup"><span data-stu-id="42d9b-168">**Note:** The Server has to be reconfigured for the Javascript to take effect.</span></span>

### <span data-ttu-id="42d9b-169">MBAM 2.5 Sp1 報告無法正常運作/轉譯</span><span class="sxs-lookup"><span data-stu-id="42d9b-169">MBAM 2.5 Sp1 Reports does not work / render properly</span></span>
<span data-ttu-id="42d9b-170">當 SSRS 託管于 SQL Server 2016 edition 上時，無法正確呈現 [報告] 頁面。</span><span class="sxs-lookup"><span data-stu-id="42d9b-170">Reports Page does not render properly when SSRS is hosted on SQL Server 2016 edition.</span></span> 
<span data-ttu-id="42d9b-171">例如，流覽至 [支援人員] –按一下 [報表] （醒目提示的部分在其上有 "x"）使用這會進一步說明此情況：當您按一下 [報表] 時，它看起來就像是使用 HTML 4.0 轉譯格式來呼叫 SSRS 頁面。</span><span class="sxs-lookup"><span data-stu-id="42d9b-171">For example – Browsing to Helpdesk – Clicking on Reports – ( Highlighted portion have “x” on it ) Digging this further with Fiddler – it does look like once we click on Reports – it calls the SSRS page with HTML 4.0 rendering format.</span></span>

<span data-ttu-id="42d9b-172">因應措施 **：** 看看網站的主要程式碼，並注意到 X-UA 模式是 IE8。</span><span class="sxs-lookup"><span data-stu-id="42d9b-172">**Workaround:** Looking at the site.master code and noticed the X-UA mode was dictated as IE8.</span></span> <span data-ttu-id="42d9b-173">因為 IE8 是在生活結束之後，而且客戶使用 IE11。</span><span class="sxs-lookup"><span data-stu-id="42d9b-173">As IE8 is WAY past the end of life, and customer is using IE11.</span></span> <span data-ttu-id="42d9b-174">更新以下程式碼的設定。</span><span class="sxs-lookup"><span data-stu-id="42d9b-174">Update the setting to the below code.</span></span> <span data-ttu-id="42d9b-175">這可讓網站利用 IE11 轉譯技術</span><span class="sxs-lookup"><span data-stu-id="42d9b-175">This allows the site to utilize IE11 rendering technologies</span></span>

    <meta http-equiv="X-UA-Compatible" content="IE=Edge" />

<span data-ttu-id="42d9b-176">原始設定為：</span><span class="sxs-lookup"><span data-stu-id="42d9b-176">Original setting is:</span></span> 

    <meta http-equiv="X-UA-Compatible" content="IE=8" />


<span data-ttu-id="42d9b-177">這是使用其他瀏覽器（例如 Chrome、Firefox 等）無法看到問題的原因。</span><span class="sxs-lookup"><span data-stu-id="42d9b-177">This is the reason why the issue was not seen with other browsers like Chrome, Firefox etc.</span></span>



## <span data-ttu-id="42d9b-178">相關主題</span><span class="sxs-lookup"><span data-stu-id="42d9b-178">Related topics</span></span>


[<span data-ttu-id="42d9b-179">關於 MBAM 2.5</span><span class="sxs-lookup"><span data-stu-id="42d9b-179">About MBAM 2.5</span></span>](about-mbam-25.md)

 

## <span data-ttu-id="42d9b-180">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="42d9b-180">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="42d9b-181">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="42d9b-181">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="42d9b-182">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="42d9b-182">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





