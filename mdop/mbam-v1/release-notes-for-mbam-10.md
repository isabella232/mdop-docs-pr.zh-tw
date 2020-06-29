---
title: MBAM 1.0 版本資訊
description: MBAM 1.0 版本資訊
author: dansimp
ms.assetid: d82fddde-c360-48ef-86a0-d9b5fe066861
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 705fd1b936da1454081dd14a7f075f642fc4a405
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811510"
---
# <span data-ttu-id="60c57-103">MBAM 1.0 版本資訊</span><span class="sxs-lookup"><span data-stu-id="60c57-103">Release Notes for MBAM 1.0</span></span>


**<span data-ttu-id="60c57-104">若要在這些版本筆記中搜尋特定問題，請按 CTRL + F。</span><span class="sxs-lookup"><span data-stu-id="60c57-104">To search for a specific issue in these release notes, press CTRL+F.</span></span>**

<span data-ttu-id="60c57-105">安裝 Microsoft BitLocker 管理和監控（MBAM）之前，請先閱讀這些版本資訊。</span><span class="sxs-lookup"><span data-stu-id="60c57-105">Read these release notes thoroughly before you install Microsoft BitLocker Administration and Monitoring (MBAM).</span></span>

<span data-ttu-id="60c57-106">這些版本資訊包含成功安裝 MBAM 所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="60c57-106">These release notes contain information that is required to successfully install MBAM.</span></span> <span data-ttu-id="60c57-107">版本資訊中也包含產品檔中不提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="60c57-107">The release notes also contain information that is not available in the product documentation.</span></span> <span data-ttu-id="60c57-108">如果這些版本資訊與其他 MBAM 檔有差異，最新的變更應該視為權威性。</span><span class="sxs-lookup"><span data-stu-id="60c57-108">If there is a difference between these release notes and other MBAM documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="60c57-109">這些版本資訊取代本產品隨附的內容。</span><span class="sxs-lookup"><span data-stu-id="60c57-109">These release notes supersede the content that is included with this product.</span></span>

## <span data-ttu-id="60c57-110">關於產品檔</span><span class="sxs-lookup"><span data-stu-id="60c57-110">About the Product Documentation</span></span>


<span data-ttu-id="60c57-111">如需 MBAM 檔的相關資訊，請參閱 Microsoft TechNet 上的 [MBAM] 首頁。</span><span class="sxs-lookup"><span data-stu-id="60c57-111">For information about MBAM documentation, see the MBAM home page on Microsoft TechNet.</span></span>

<span data-ttu-id="60c57-112">若要取得 MBAM 檔的可下載複本，請參閱 <https://go.microsoft.com/fwlink/p/?LinkId=225356> Microsoft 下載中心。</span><span class="sxs-lookup"><span data-stu-id="60c57-112">To obtain a downloadable copy of the MBAM documentation, see <https://go.microsoft.com/fwlink/p/?LinkId=225356> on the Microsoft Download Center.</span></span>

## <span data-ttu-id="60c57-113">提供意見反應</span><span class="sxs-lookup"><span data-stu-id="60c57-113">Provide Feedback</span></span>


<span data-ttu-id="60c57-114">我們對您在 MBAM 的意見反應感興趣。</span><span class="sxs-lookup"><span data-stu-id="60c57-114">We are interested in your feedback on MBAM.</span></span> <span data-ttu-id="60c57-115">您可以將意見反應傳送給您 <mdopdocs@microsoft.com> 。</span><span class="sxs-lookup"><span data-stu-id="60c57-115">You can send your feedback to <mdopdocs@microsoft.com>.</span></span>

<span data-ttu-id="60c57-116">**記事** 此電子郵件地址不是支援頻道，但您的意見反應將協助我們規劃我們的檔和產品版本中的未來變更。</span><span class="sxs-lookup"><span data-stu-id="60c57-116">**Note** This email address is not a support channel, but your feedback will help us to plan for future changes in our documentation and product releases.</span></span>

 

<span data-ttu-id="60c57-117">如需 MDOP 及其他學習資源的最新資訊，請參閱[Mdop 資訊體驗](https://go.microsoft.com/fwlink/p/?LinkId=236032)頁面。</span><span class="sxs-lookup"><span data-stu-id="60c57-117">For the latest information about MDOP and additional learning resources, see the [MDOP Information Experience](https://go.microsoft.com/fwlink/p/?LinkId=236032) page.</span></span>

<span data-ttu-id="60c57-118">如需新更新或提供意見反應的詳細資訊，請在[Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445)或[Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447)上關注我們。</span><span class="sxs-lookup"><span data-stu-id="60c57-118">For more information about new updates or to provide feedback, follow us on [Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445) or [Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447).</span></span>

## <span data-ttu-id="60c57-119">MBAM 1.0 的已知問題</span><span class="sxs-lookup"><span data-stu-id="60c57-119">Known Issues with MBAM 1.0</span></span>


<span data-ttu-id="60c57-120">本節包含有關 MBAM 設定和安裝之已知問題的發行記錄。</span><span class="sxs-lookup"><span data-stu-id="60c57-120">This section contains release notes about the known issues with MBAM setup and installation.</span></span>

### <a href="" id="if-you-select-the--use-a-certificate-to-encrypt-the-network-communication--option-during-setup--existing-database-connections-and-dependent-applications-can-stop-functioning-"></a><span data-ttu-id="60c57-121">如果您在安裝期間選取 [使用憑證來加密網路通訊] 選項，現有的資料庫連線和相依的應用程式就會停止運作</span><span class="sxs-lookup"><span data-stu-id="60c57-121">If you select the “Use a certificate to encrypt the network communication” option during Setup, existing database connections and dependent applications can stop functioning</span></span>

<span data-ttu-id="60c57-122">您可以在安裝 [復原] 和 [硬體資料庫] 或 [合規性狀態資料庫] 功能之後，設定**加密網路通訊**的 MBAM。</span><span class="sxs-lookup"><span data-stu-id="60c57-122">You can configure MBAM for **Encrypted network communication** after you install either the Recovery and Hardware Database or the Compliance Status Database features.</span></span> <span data-ttu-id="60c57-123">如果您選擇設定 MBAM 以進行加密的網路通訊，MBAM 的安裝程式會將 SQL Server 資料庫引擎的實例設定為使用安全通訊端層（SSL），以進行適用資料庫與管理與監視伺服器以及合規性和審核報表伺服器功能之間的通訊。</span><span class="sxs-lookup"><span data-stu-id="60c57-123">If you choose to configure MBAM for Encrypted network communication, MBAM Setup configures the instance of the SQL Server Database Engine to use Secure Sockets Layer (SSL) for communication between the applicable database and both the Administration and Monitoring Server and the Compliance and Audit Report Server features.</span></span>

-   <span data-ttu-id="60c57-124">如果 SQL Server 資料庫引擎實例尚未設定為使用 SSL，請 MBAM 安裝程式將其設定為使用 SSL。</span><span class="sxs-lookup"><span data-stu-id="60c57-124">If the instance of the SQL Server Database Engine is not already configured to use SSL, MBAM Setup configures it to do so.</span></span> <span data-ttu-id="60c57-125">這可防止嘗試在 SQL Server 資料庫引擎實例上使用非 MBAM 資料庫的應用程式與其資料庫進行通訊。</span><span class="sxs-lookup"><span data-stu-id="60c57-125">This can prevent applications that try to use non-MBAM databases on the instance of the SQL Server Database Engine from communicating with their databases.</span></span>

-   <span data-ttu-id="60c57-126">如果 SQL Server 資料庫引擎的實例已設定為使用 SSL，則會將其設定為使用使用者在安裝期間選取的憑證。</span><span class="sxs-lookup"><span data-stu-id="60c57-126">If the instance of the SQL Server Database Engine is already configured to use SSL, it is configured to use the certificate that the user selected during setup.</span></span> <span data-ttu-id="60c57-127">如果這個證書與已在使用的憑證不同，就可以避免在 SQL Server 資料庫引擎實例上使用 SQL Server 資料庫的應用程式執行。</span><span class="sxs-lookup"><span data-stu-id="60c57-127">If this certificate differs from the one that was already in use, it can prevent applications that use SQL Server databases on the instance of the SQL Server Database Engine from running.</span></span>

<span data-ttu-id="60c57-128">因應措施 **：** 所有</span><span class="sxs-lookup"><span data-stu-id="60c57-128">**WORKAROUND:** None</span></span>

### <span data-ttu-id="60c57-129">當您使用本機系統管理員帳戶時，在安裝期間 MBAM 安裝失敗</span><span class="sxs-lookup"><span data-stu-id="60c57-129">MBAM Setup fails during installation when you use a local Administrator account</span></span>

<span data-ttu-id="60c57-130">如果您使用的是本機系統管理員帳戶，MBAM 安裝程式就會失敗。</span><span class="sxs-lookup"><span data-stu-id="60c57-130">MBAM Setup fails when you use a local Administrator account.</span></span> <span data-ttu-id="60c57-131">記錄檔包含下列資訊：</span><span class="sxs-lookup"><span data-stu-id="60c57-131">The log file contains the following information:</span></span>

``` syntax
Locating group 'MBAM Report Users'
Adding <GUID>' to group 'MBAM Report Users'
Locating group 'MBAM Recovery and Hardware DB Access'
Adding 'S-1-5-20' to group 'MBAM Recovery and Hardware DB Access'
Exception: A new member could not be added to a local group because the member has the wrong account type.
 
  StackTrace:    at System.DirectoryServices.AccountManagement.SAMStoreCtx.UpdateGroupMembership(Principal group, DirectoryEntry de, NetCred credentials, AuthenticationTypes authTypes)
   at System.DirectoryServices.AccountManagement.SDSUtils.ApplyChangesToDirectory(Principal p, StoreCtx storeCtx, GroupMembershipUpdater updateGroupMembership, NetCred credentials, AuthenticationTypes authTypes)
   at System.DirectoryServices.AccountManagement.SAMStoreCtx.Update(Principal p)
   at Microsoft.Windows.Mdop.BitlockerManagement.Setup.Groups.CreateGroupsDeferred(Session session)
  InnerException:Exception: A new member could not be added to a local group because the member has the wrong account type.
 
    InnerException:StackTrace:    at System.DirectoryServices.AccountManagement.UnsafeNativeMethods.IADsGroup.Add(String bstrNewItem)
   at System.DirectoryServices.AccountManagement.SAMStoreCtx.UpdateGroupMembership(Principal group, DirectoryEntry de, NetCred credentials, AuthenticationTypes authTypes)
CustomAction MbamCreateGroupsDeferred returned actual error code 1603 (note this may not be 100% accurate if translation happened inside sandbox)
Action ended 11:41:29: InstallExecute. Return value 3.
```

<span data-ttu-id="60c57-132">因應措施 **：** 當您安裝 MBAM 時，請在伺服器電腦上使用網域帳戶和系統管理認證。</span><span class="sxs-lookup"><span data-stu-id="60c57-132">**WORKAROUND:** Use a domain account with administrative credentials on the server computer when you install MBAM.</span></span>

### <span data-ttu-id="60c57-133">如果您選取 [不要加密網路通訊]，MBAM 安裝程式會將 SQL Server 資料庫引擎的實例重新設定為不使用 SSL</span><span class="sxs-lookup"><span data-stu-id="60c57-133">MBAM Setup reconfigures the instance of the SQL Server Database Engine to not use SSL if you select “Do not encrypt network communication”</span></span>

<span data-ttu-id="60c57-134">當您安裝 [恢復] 和 [硬體] 資料庫或 [合規性狀態] 資料庫時，您可以使用安裝程式來設定 MBAM，方法是選取**加密的網路通訊**。</span><span class="sxs-lookup"><span data-stu-id="60c57-134">When you install either the Recovery and Hardware Database or the Compliance Status Database, you can use Setup to configure MBAM by selecting **Encrypted network communication**.</span></span> <span data-ttu-id="60c57-135">如果您決定不加密網路通訊，MBAM 安裝程式會重新設定 SQL Server 資料庫引擎的實例，使其不使用 SSL。</span><span class="sxs-lookup"><span data-stu-id="60c57-135">If you decide not to encrypt the network communication, MBAM Setup reconfigures the instance of the SQL Server Database Engine so that it does not use SSL.</span></span>

-   <span data-ttu-id="60c57-136">如果 SQL Server 資料庫引擎的實例已設定為使用 SSL，MBAM 安裝程式會在 SQL Server 資料庫引擎的實例上停用 SSL。</span><span class="sxs-lookup"><span data-stu-id="60c57-136">If the instance of the SQL Server Database Engine is already configured to use SSL, MBAM Setup disables SSL on the instance of the SQL Server Database Engine.</span></span> <span data-ttu-id="60c57-137">這會變更使用與 SQL Server 資料庫引擎實例上的 MBAM 資料庫無關之資料庫之應用程式之間的通訊安全。</span><span class="sxs-lookup"><span data-stu-id="60c57-137">This changes the communication security between the applications that use databases that are not related to MBAM databases on the instance of the SQL Server Database Engine.</span></span>

<span data-ttu-id="60c57-138">因應措施 **：** 所有</span><span class="sxs-lookup"><span data-stu-id="60c57-138">**WORKAROUND:** None</span></span>

### <span data-ttu-id="60c57-139">缺少 Internet Information Services （IIS）管理腳本與工具網頁伺服器功能的先決條件</span><span class="sxs-lookup"><span data-stu-id="60c57-139">Missing prerequisite for the Internet Information Services (IIS) Management Scripts and Tools web server feature</span></span>

<span data-ttu-id="60c57-140">MBAM 安裝程式會依賴 IIS 管理腳本與工具網頁伺服器功能，但不是強制性的先決條件。</span><span class="sxs-lookup"><span data-stu-id="60c57-140">MBAM Setup is dependent on the IIS Management Scripts and Tools web server feature, but it is not an enforced prerequisite.</span></span> <span data-ttu-id="60c57-141">伺服器安裝程式可讓您在遺失此功能時安裝 MBAM。</span><span class="sxs-lookup"><span data-stu-id="60c57-141">Server setup lets you install MBAM when this feature is missing.</span></span> <span data-ttu-id="60c57-142">不過，這將會導致備份服務 MBAM VSS 書寫器開始並停止，因為它找不到 Windows Management Instrumentation （WMI）和 Internet Information Services （IIS）提供者。</span><span class="sxs-lookup"><span data-stu-id="60c57-142">However, this will cause the backup service MBAM VSS Writer to start and then stop, because it cannot locate the Windows Management Instrumentation (WMI) and the Internet Information Services (IIS) provider.</span></span> <span data-ttu-id="60c57-143">此條件不會出現錯誤訊息，但在事件記錄檔中則不會發生。</span><span class="sxs-lookup"><span data-stu-id="60c57-143">There is no error message for this condition, except that which occurs in the event log.</span></span> <span data-ttu-id="60c57-144">不含 IIS 管理腳本與工具的 MBAM 安裝，就不會針對 MBAM 執行備份作業。</span><span class="sxs-lookup"><span data-stu-id="60c57-144">Installation of MBAM without IIS Management Scripts and Tools causes the backup operations not to run for MBAM.</span></span>

<span data-ttu-id="60c57-145">因應措施 **：** 在您啟動 MBAM 安裝程式之前，請先確認已安裝 IIS 管理腳本及工具網頁伺服器功能。</span><span class="sxs-lookup"><span data-stu-id="60c57-145">**WORKAROUND:** Ensure that the IIS Management Scripts and Tools web server feature is installed before you start the MBAM Setup.</span></span>

### <a href="" id="mbam-setup-stops-responding-during-the--installing-selected-features--phase-when-setup-is-configured-to-use-a-certificate"></a><span data-ttu-id="60c57-146">安裝程式設定為使用憑證時，MBAM 安裝程式在「安裝選取的功能」階段停止回應</span><span class="sxs-lookup"><span data-stu-id="60c57-146">MBAM Setup stops responding during the “Installing selected features” phase when setup is configured to use a certificate</span></span>

<span data-ttu-id="60c57-147">MBAM 安裝程式在**安裝選取的功能**階段期間停止回應。</span><span class="sxs-lookup"><span data-stu-id="60c57-147">MBAM Setup stops responding during the **Installing selected features** phase of setup.</span></span> <span data-ttu-id="60c57-148">這會在您選取 [**使用憑證來加密網路通訊**] 選項期間，在安裝恢復與硬體資料庫或合規性狀態資料庫期間發生。</span><span class="sxs-lookup"><span data-stu-id="60c57-148">This occurs during the installation of the Recovery and Hardware Database or the Compliance Status Database, after you select the **Use a certificate to encrypt the network communication** option.</span></span> <span data-ttu-id="60c57-149">此外，如果 SQL Server 資料庫引擎的實例無法存取在安裝期間指定的憑證，MBAM 安裝程式就會停止回應。</span><span class="sxs-lookup"><span data-stu-id="60c57-149">Furthermore, the MBAM Setup stops responding if the instance of the SQL Server Database Engine cannot access the certificate that was specified during setup.</span></span>

<span data-ttu-id="60c57-150">因應措施 **：** 更新憑證上的許可權，讓 SQL Server 資料庫引擎適用實例的 Windows 服務可以存取憑證。</span><span class="sxs-lookup"><span data-stu-id="60c57-150">**WORKAROUND:** Update the permissions on the certificate, so that the Windows service for the applicable instance of the SQL Server Database Engine can access the certificate.</span></span> <span data-ttu-id="60c57-151">您也可以變更 SQL Server 資料庫引擎實例在其上執行的帳戶，以供資料庫引擎使用憑證。</span><span class="sxs-lookup"><span data-stu-id="60c57-151">You can also change the account under which the instance of the SQL Server Database Engine runs, for the database engine to use the certificate.</span></span> <span data-ttu-id="60c57-152">若要判斷憑證的許可權，請在命令提示字元中輸入下列命令： **certutil-v-將 MY**</span><span class="sxs-lookup"><span data-stu-id="60c57-152">To determine the permissions for the certificate, type the following command at the command prompt: **certutil -v -store MY**</span></span>

### <span data-ttu-id="60c57-153">安裝 SQL Server Reporting Services 時，MBAM 安裝程式暫停</span><span class="sxs-lookup"><span data-stu-id="60c57-153">MBAM Setup pauses when you install SQL Server Reporting Services</span></span>

<span data-ttu-id="60c57-154">在 MBAM 安裝期間，當您選取的 SQL Server Reporting Services （SSRS）實例無法使用或未正確設定時，MBAM 的安裝程式在嘗試與 SSRS 實例通訊時，最多可能暫停一分鐘。</span><span class="sxs-lookup"><span data-stu-id="60c57-154">During MBAM installation, when you select an instance of SQL Server Reporting Services (SSRS) and SSRS instance is not available or it is configured incorrectly, the MBAM Setup might pause for up to one minute while it attempts to communicate with the SSRS instance.</span></span>

<span data-ttu-id="60c57-155">因應措施 **：** 在安裝程式嘗試與 SSRS 實例取得聯繫時，請至少等待1分鐘的時間，MBAM 設定才能繼續。</span><span class="sxs-lookup"><span data-stu-id="60c57-155">**WORKAROUND:** Wait for at least one minute for MBAM Setup to resume while the Setup program attempts to contact the instance of SSRS.</span></span>

### <a href="" id="administration-and-monitoring-server-does-not-run-after-setup-"></a><span data-ttu-id="60c57-156">在安裝之後，系統管理和監控伺服器不會執行</span><span class="sxs-lookup"><span data-stu-id="60c57-156">Administration and Monitoring Server does not run after setup</span></span>

<span data-ttu-id="60c57-157">MBAM 安裝程式成功安裝 [管理及監視伺服器] 功能後，當您嘗試存取 MBAM 管理員網站時，MBAM 會顯示錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="60c57-157">After MBAM Setup successfully installs the Administration and Monitoring Server feature, MBAM displays error messages when you try to access the MBAM administrator website.</span></span> <span data-ttu-id="60c57-158">這個問題可能是由下列其中一個原因所導致：</span><span class="sxs-lookup"><span data-stu-id="60c57-158">This issue occurs for one of the following reasons:</span></span>

-   <span data-ttu-id="60c57-159">在 MBAM 安裝之後，系統會移除管理和監視伺服器上的一個或多個先決條件。</span><span class="sxs-lookup"><span data-stu-id="60c57-159">One or more prerequisites on the Administration and Monitoring Server were removed after the MBAM installation.</span></span>

-   <span data-ttu-id="60c57-160">在伺服器上安裝一個或多個先決條件之後，在執行 MBAM 安裝程式之前，這些系統會將它們移除。</span><span class="sxs-lookup"><span data-stu-id="60c57-160">One or more prerequisites were installed on the server and later they were removed before running the MBAM Setup.</span></span>

<span data-ttu-id="60c57-161">因應措施 **：** 請參閱 MBAM 檔，並確認已安裝所有 MBAM 必備元件。</span><span class="sxs-lookup"><span data-stu-id="60c57-161">**WORKAROUND:** Review the MBAM documentation and confirm that all MBAM prerequisites are installed.</span></span>

### <span data-ttu-id="60c57-162">在安裝過程中按一下 [檔] 連結會導致安裝程式完成後出現應用程式錯誤</span><span class="sxs-lookup"><span data-stu-id="60c57-162">Clicking documentation links during Setup results in an application error after Setup is finished</span></span>

<span data-ttu-id="60c57-163">當您在安裝期間按一下檔連結，然後按一下 [**取消**] 或 [在安裝程式成功完成後**完成]** ，就會出現應用程式錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="60c57-163">When you click a documentation link during setup and then close the Setup program by clicking **Cancel** or **Finish** after Setup has successfully finished, an application error message appears..</span></span> <span data-ttu-id="60c57-164">這個問題是由於 Windows 工作排程器中發生存取侵犯錯誤所造成。</span><span class="sxs-lookup"><span data-stu-id="60c57-164">The problem is caused by an access violation error in the Windows Task Scheduler.</span></span>

<span data-ttu-id="60c57-165">因應措施 **：** 所有.</span><span class="sxs-lookup"><span data-stu-id="60c57-165">**WORKAROUND:** None.</span></span> <span data-ttu-id="60c57-166">您可以忽略這個錯誤。</span><span class="sxs-lookup"><span data-stu-id="60c57-166">You can ignore this error.</span></span>

### <span data-ttu-id="60c57-167">失敗的 MBAM 設定無法移除新資料庫</span><span class="sxs-lookup"><span data-stu-id="60c57-167">Failed MBAM Setup does not remove new databases</span></span>

<span data-ttu-id="60c57-168">如果 MBAM 設定失敗，安裝程式可能不會移除新建立的資料庫。</span><span class="sxs-lookup"><span data-stu-id="60c57-168">If the MBAM Setup fails, Setup might not remove the newly created databases.</span></span> <span data-ttu-id="60c57-169">這可能會導致後續安裝失敗。</span><span class="sxs-lookup"><span data-stu-id="60c57-169">This can cause failures during subsequent installations.</span></span>

<span data-ttu-id="60c57-170">因應措施 **：** 在後續安裝期間，為資料庫實例選擇其他名稱。</span><span class="sxs-lookup"><span data-stu-id="60c57-170">**WORKAROUND:** Choose a different name for the database instance during the subsequent installation.</span></span>

### <span data-ttu-id="60c57-171">MBAM 安裝程式無法辨識有效的網路負載平衡群集憑證</span><span class="sxs-lookup"><span data-stu-id="60c57-171">MBAM Setup does not recognize valid network load-balancing cluster certificates</span></span>

<span data-ttu-id="60c57-172">在 MBAM 管理和監視伺服器安裝期間，選取 [網路加密] 選項時，系統不會將群集憑證識別為有效的憑證。</span><span class="sxs-lookup"><span data-stu-id="60c57-172">During the MBAM Administration and Monitoring Server installation, with the network encryption option selected, the cluster certificate is not recognized as a valid certificate.</span></span> <span data-ttu-id="60c57-173">當已安裝與資料庫通訊的憑證，但由於負載平衡群集而遭到拒絕通訊時，就認為它是有效的。</span><span class="sxs-lookup"><span data-stu-id="60c57-173">It is recognized as valid when the certificate for communication with the database is installed, but it is rejected for communication by the load-balancing cluster.</span></span>

<span data-ttu-id="60c57-174">因應措施 **：** 確認可存取與憑證相關聯的憑證吊銷清單（CRL），或使用不需要使用 CRL 驗證的憑證。</span><span class="sxs-lookup"><span data-stu-id="60c57-174">**WORKAROUND:** Confirm that the certificate revocation list (CRL) associated with the certificate is accessible, or use a certificate that does not require validation by using the CRL.</span></span>

## <span data-ttu-id="60c57-175">版本資訊版權資訊</span><span class="sxs-lookup"><span data-stu-id="60c57-175">Release Notes Copyright Information</span></span>


<span data-ttu-id="60c57-176">Microsoft、Active Directory、ActiveX、Bing、Excel、Silverlight、SQLServer、Windows、MicrosoftIntune 和 WindowsPowerShell 是 Microsoft 公司群組的商標。</span><span class="sxs-lookup"><span data-stu-id="60c57-176">Microsoft, Active Directory, ActiveX, Bing, Excel, Silverlight, SQLServer, Windows, MicrosoftIntune, and WindowsPowerShell are trademarks of the Microsoft group of companies.</span></span> <span data-ttu-id="60c57-177">所有其他商標都是其各自擁有者的財產。</span><span class="sxs-lookup"><span data-stu-id="60c57-177">All other trademarks are property of their respective owners.</span></span>



## <span data-ttu-id="60c57-178">相關主題</span><span class="sxs-lookup"><span data-stu-id="60c57-178">Related topics</span></span>


[<span data-ttu-id="60c57-179">關於 MBAM 1.0</span><span class="sxs-lookup"><span data-stu-id="60c57-179">About MBAM 1.0</span></span>](about-mbam-10.md)

 

 





