---
title: App-V 5.1 的版本資訊
description: App-V 5.1 的版本資訊
author: dansimp
ms.assetid: 62c5be3b-0a46-4512-93ed-97c23184f343
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 09/26/2016
ms.openlocfilehash: 7437a16bc10b21bb15b0f8307c2711177e78cb72
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800311"
---
# <span data-ttu-id="fbb95-103">App-V 5.1 的版本資訊</span><span class="sxs-lookup"><span data-stu-id="fbb95-103">Release Notes for App-V 5.1</span></span>


<span data-ttu-id="fbb95-104">下列是 Microsoft Application Virtualization （App-v）5.1 的已知問題。</span><span class="sxs-lookup"><span data-stu-id="fbb95-104">The following are known issues in Microsoft Application Virtualization (App-V) 5.1.</span></span>

## <span data-ttu-id="fbb95-105">在 Windows 10 上的 App-v 5.0 SP3 管理伺服器與 App-v 5.1 用戶端之間的發佈更新期間發生錯誤</span><span class="sxs-lookup"><span data-stu-id="fbb95-105">Error occurs during publishing refresh between App-V 5.0 SP3 Management Server and App-V 5.1 Client on Windows 10</span></span>


<span data-ttu-id="fbb95-106">將套件從 App-v 5.0 SP3 管理伺服器同步處理到 Windows 10 上的 App-v 5.1 用戶端時，會在發佈重新整理期間產生錯誤。</span><span class="sxs-lookup"><span data-stu-id="fbb95-106">An error is generated during publishing refresh when synchronizing packages from the App-V 5.0 SP3 management server to an App-V 5.1 client on Windows 10 .</span></span> <span data-ttu-id="fbb95-107">發生此錯誤的原因是，app-v 5.0 SP3 伺服器不知道發佈 URL 中指定的 Windows 10 作業系統。</span><span class="sxs-lookup"><span data-stu-id="fbb95-107">This error occurs because the App-V 5.0 SP3 server does not understand the Windows 10 operating system that is specified in the publishing URL.</span></span> <span data-ttu-id="fbb95-108">這個問題針對 App-v 5.1 發佈伺服器已修正，但無法 backported 至 App-v 5.0 SP3 或更舊版本。</span><span class="sxs-lookup"><span data-stu-id="fbb95-108">The issue is fixed for App-V 5.1 publishing server, but is not backported to versions of App-V 5.0 SP3 or earlier.</span></span>

<span data-ttu-id="fbb95-109">**解決方法**：將 App-v 5.0 管理伺服器升級至 Windows 10 用戶端的 App-v 5.1 管理伺服器。</span><span class="sxs-lookup"><span data-stu-id="fbb95-109">**Workaround**: Upgrade the App-V 5.0 Management server to the App-V 5.1 Management server for Windows 10 Clients.</span></span>

## <span data-ttu-id="fbb95-110">如果您使用 App-v 5.1 Server 設定，就不會針對將在全域發行的套件套用自訂設定。</span><span class="sxs-lookup"><span data-stu-id="fbb95-110">Custom configurations do not get applied for packages that will be published globally if they are set using the App-V 5.1 Server</span></span>


<span data-ttu-id="fbb95-111">如果您將套件指派給包含電腦帳戶的 AD 群組，並使用 App-v 伺服器將自訂設定套用至該群組，則自訂設定將不會套用至這些電腦。</span><span class="sxs-lookup"><span data-stu-id="fbb95-111">If you assign a package to an AD group that contains machine accounts and apply a custom configuration to that group using the App-V Server, the custom configuration will not be applied to those machines.</span></span> <span data-ttu-id="fbb95-112">App-v 5.1 用戶端將在全域發佈指派給電腦帳戶的套件。</span><span class="sxs-lookup"><span data-stu-id="fbb95-112">The App-V 5.1 Client will publish packages assigned to a machine account globally.</span></span> <span data-ttu-id="fbb95-113">不過，它會在每個使用者的設定檔中儲存每位使用者的自訂設定檔。</span><span class="sxs-lookup"><span data-stu-id="fbb95-113">However, it stores custom configuration files per user in each user’s profile.</span></span> <span data-ttu-id="fbb95-114">全域發佈的套件將無法存取此自訂設定。</span><span class="sxs-lookup"><span data-stu-id="fbb95-114">Globally published packages will not have access to this custom configuration.</span></span>

<span data-ttu-id="fbb95-115">**解決方法**：執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="fbb95-115">**Workaround**: Do one of the following:</span></span>

-   <span data-ttu-id="fbb95-116">將套件指派給只包含使用者帳戶的群組。</span><span class="sxs-lookup"><span data-stu-id="fbb95-116">Assign the package to groups containing only user accounts.</span></span> <span data-ttu-id="fbb95-117">這將確保套件的自訂設定會儲存在每個使用者的設定檔中，且會正確套用。</span><span class="sxs-lookup"><span data-stu-id="fbb95-117">This will ensure that the package’s custom configuration will be stored in each user’s profile and will be applied correctly.</span></span>

-   <span data-ttu-id="fbb95-118">使用 AppvClientPackage Cmdlet 和– DynamicDeploymentConfiguration 參數，建立自訂部署設定檔，並將它套用到用戶端上的套件。</span><span class="sxs-lookup"><span data-stu-id="fbb95-118">Create a custom deployment configuration file and apply it to the package on the client using the Add-AppvClientPackage cmdlet with the –DynamicDeploymentConfiguration parameter.</span></span> <span data-ttu-id="fbb95-119">如需詳細資訊，請參閱[關於 App-V 5.1 動態配置](about-app-v-51-dynamic-configuration.md)。</span><span class="sxs-lookup"><span data-stu-id="fbb95-119">See [About App-V 5.1 Dynamic Configuration](about-app-v-51-dynamic-configuration.md) for more information.</span></span>

-   <span data-ttu-id="fbb95-120">使用 App-v 5.1 排序器，建立含自訂設定的新套件。</span><span class="sxs-lookup"><span data-stu-id="fbb95-120">Create a new package with the custom configuration using the App-V 5.1 Sequencer.</span></span>

## <span data-ttu-id="fbb95-121">在新的 App-v 5.1 Server 安裝之後，不會刪除伺服器檔案</span><span class="sxs-lookup"><span data-stu-id="fbb95-121">Server files not deleted after new App-V 5.1 Server installation</span></span>


<span data-ttu-id="fbb95-122">如果您卸載 App-v 5.0 SP1 伺服器，然後安裝 App-v 5.1 伺服器，安裝會失敗、安裝了錯誤的管理伺服器版本，且會傳回錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="fbb95-122">If you uninstall the App-V 5.0 SP1 Server and then install the App-V 5.1 Server, the installation fails, the wrong version of the Management server is installed, and an error message is returned.</span></span> <span data-ttu-id="fbb95-123">發生這個問題的原因是，當您卸載 app-v 5.0 SP1 時，伺服器檔案並未刪除，所以安裝程式會執行升級，而不是全新的安裝。</span><span class="sxs-lookup"><span data-stu-id="fbb95-123">The issue occurs because the Server files are not being deleted when you uninstall App-V 5.0 SP1, so the installation process does an upgrade instead of a new installation.</span></span>

<span data-ttu-id="fbb95-124">因應**措施：請**先刪除此登錄機碼，然後再開始安裝應用程式-V 5.1：</span><span class="sxs-lookup"><span data-stu-id="fbb95-124">**Workaround**: Delete this registry key before you start installing App-V 5.1:</span></span>

<span data-ttu-id="fbb95-125">在 HKEY _LOCAL \ _MACHINE \\SOFTWARE\\Wow6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall 下，找出並刪除包含 DWORD 值 "DisplayName" （含值資料 "Microsoft Application Virtualization （App-v） Server"）的安裝 GUID 金鑰。</span><span class="sxs-lookup"><span data-stu-id="fbb95-125">Under HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Wow6432Node\\Microsoft\\Windows\\CurrentVersion\\Uninstall, locate and delete the installation GUID key that contains the DWORD value "DisplayName" with value data "Microsoft Application Virtualization (App-V) Server".</span></span> <span data-ttu-id="fbb95-126">這是唯一應該刪除的索引鍵。</span><span class="sxs-lookup"><span data-stu-id="fbb95-126">This is the only key that should be deleted.</span></span>

## <span data-ttu-id="fbb95-127">手動新增的檔案類型關聯無法正確儲存</span><span class="sxs-lookup"><span data-stu-id="fbb95-127">File type associations added manually are not saved correctly</span></span>


<span data-ttu-id="fbb95-128">使用應用程式升級嚮導結尾的 [快速鍵] 和 [FTAs] 索引標籤，以手動方式新增到應用程式套件中的檔案類型關聯，並不會正確儲存。</span><span class="sxs-lookup"><span data-stu-id="fbb95-128">File type associations added to an application package manually using the Shortcuts and FTAs tab at the end of the application upgrade wizard are not saved correctly.</span></span> <span data-ttu-id="fbb95-129">當您再次更新已儲存的套件時，App-v 用戶端或 Sequencer 將無法使用它們。</span><span class="sxs-lookup"><span data-stu-id="fbb95-129">They will not be available to the App-V Client or to the Sequencer when updating the saved package again.</span></span>

<span data-ttu-id="fbb95-130">因應**措施：若**要新增檔案類型關聯，請開啟套件以進行修改，然後執行更新嚮導。</span><span class="sxs-lookup"><span data-stu-id="fbb95-130">**Workaround**: To add a file type association, open the package for modification and run the update wizard.</span></span> <span data-ttu-id="fbb95-131">在安裝步驟中，透過作業系統新增新的檔案類型關聯。</span><span class="sxs-lookup"><span data-stu-id="fbb95-131">During the Installation step, add the new file type association through the operating system.</span></span> <span data-ttu-id="fbb95-132">排序器會偵測系統登錄中的新關聯，並將它新增至套件的虛擬機器碼，以供用戶端使用。</span><span class="sxs-lookup"><span data-stu-id="fbb95-132">The sequencer will detect the new association in the system registry and add it to the package’s virtual registry, where it will be available to the client.</span></span>

## <span data-ttu-id="fbb95-133">當您將共用內容存儲區（SCS）模式中的資料流程封裝到同時使用 AppLocker 管理的用戶端時，額外的資料會寫入本機磁片。</span><span class="sxs-lookup"><span data-stu-id="fbb95-133">When streaming packages in Shared Content Store (SCS) mode to a client that is also managed with AppLocker, additional data is written to the local disk.</span></span>


<span data-ttu-id="fbb95-134">若要減少寫入用戶端本機磁片的資料量，您可以在應用程式 V 5.1 用戶端上啟用 SCS 模式，以根據需要對流進行套件的內容。</span><span class="sxs-lookup"><span data-stu-id="fbb95-134">To decrease the amount of data written to a client’s local disk, you can enable SCS mode on the App-V 5.1 Client to stream the contents of a package on demand.</span></span> <span data-ttu-id="fbb95-135">不過，如果 AppLocker 在套件中管理應用程式，則某些資料可能會寫入到用戶端的本機磁片，而不會以其他方式寫入。</span><span class="sxs-lookup"><span data-stu-id="fbb95-135">However, if AppLocker manages an application within the package, some data might be written to the client’s local disk that would not otherwise be written.</span></span>

<span data-ttu-id="fbb95-136">因應**措施：無**</span><span class="sxs-lookup"><span data-stu-id="fbb95-136">**Workaround**: None</span></span>

## <span data-ttu-id="fbb95-137">在 [管理主控台新增套件] 對話方塊中，使用 Chrome 或 Firefox 時無法使用 [流覽] 按鈕</span><span class="sxs-lookup"><span data-stu-id="fbb95-137">In the Management Console Add Package dialog box, the Browse button is not available when using Chrome or Firefox</span></span>


<span data-ttu-id="fbb95-138">在管理主控台的 [套件] 頁面上，如果您按一下右下角的 [**新增] 或 [升級**]，就會出現 [**新增套件**] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="fbb95-138">On the Packages page of the Management Console, if you click **Add or Upgrade** in the lower-right corner, the **Add Package** dialog box appears.</span></span> <span data-ttu-id="fbb95-139">如果您是使用 Chrome 或 Firefox 作為瀏覽器來存取管理主控台，您將無法流覽至套件的位置。</span><span class="sxs-lookup"><span data-stu-id="fbb95-139">If you are accessing the Management Console using Chrome or Firefox as your browser, you will not be able to browse to the location of the package.</span></span>

<span data-ttu-id="fbb95-140">因應**措施：在**[**新增套件**輸入] 欄位中，輸入或複製並貼上套件的路徑。</span><span class="sxs-lookup"><span data-stu-id="fbb95-140">**Workaround**: Type or copy and paste the path to the package into the **Add Package** input field.</span></span> <span data-ttu-id="fbb95-141">如果管理主機擁有此路徑的存取權，您就可以新增套件。</span><span class="sxs-lookup"><span data-stu-id="fbb95-141">If the Management Console has access to this path, you will be able to add the package.</span></span> <span data-ttu-id="fbb95-142">如果套件位於網路共用位置，您可以執行下列步驟，流覽至使用檔案資源管理器的位置：</span><span class="sxs-lookup"><span data-stu-id="fbb95-142">If the package is on a network share, you can browse to the location using File Explorer by doing these steps:</span></span>

1.  <span data-ttu-id="fbb95-143">按下**Shift 鍵**，並以滑鼠右鍵按一下套件檔案</span><span class="sxs-lookup"><span data-stu-id="fbb95-143">While pressing **Shift**, right-click on the package file</span></span>

2.  <span data-ttu-id="fbb95-144">選取 [**複製為路徑**]</span><span class="sxs-lookup"><span data-stu-id="fbb95-144">Select **Copy as path**</span></span>

3.  <span data-ttu-id="fbb95-145">將路徑貼到 [**新增套件**] 對話方塊的輸入欄位</span><span class="sxs-lookup"><span data-stu-id="fbb95-145">Paste the path into the **Add Package** dialog box input field</span></span>

## <a href="" id="upgrading-app-v-management-server-to-5-1-sometimes-fails-with-the-message--a-database-error-occurred-"></a><span data-ttu-id="fbb95-146">將 App-v 管理伺服器升級至5.1 時，有時會失敗，並出現「發生資料庫錯誤」的訊息</span><span class="sxs-lookup"><span data-stu-id="fbb95-146">Upgrading App-V Management Server to 5.1 sometimes fails with the message “A database error occurred”</span></span>


<span data-ttu-id="fbb95-147">如果您安裝應用程式-V 5.0 SP1 管理伺服器，然後嘗試升級至 App-v 5.1 伺服器，且已設定並啟用多個連線群組，則會顯示下列錯誤：「資料庫發生錯誤。</span><span class="sxs-lookup"><span data-stu-id="fbb95-147">If you install the App-V 5.0 SP1 Management Server, and then try to upgrade to App-V 5.1 Server when multiple connection groups are configured and enabled, the following error is displayed: “A database error occurred.</span></span> <span data-ttu-id="fbb95-148">原因：「不正確欄名稱 ' PackageOptional」。</span><span class="sxs-lookup"><span data-stu-id="fbb95-148">Reason: 'Invalid column name 'PackageOptional'.</span></span> <span data-ttu-id="fbb95-149">不正確欄名稱 ' VersionOptional」。</span><span class="sxs-lookup"><span data-stu-id="fbb95-149">Invalid column name 'VersionOptional'.”</span></span>

<span data-ttu-id="fbb95-150">因應措施：在您的 SQL 資料庫**上執行這個**命令：</span><span class="sxs-lookup"><span data-stu-id="fbb95-150">**Workaround**: Run this command on your SQL database:</span></span>

`ALTER TABLE AppVManagement.dbo.PackageGroupMembers ADD PackageOptional bit NOT NULL DEFAULT 0, VersionOptional bit NOT NULL DEFAULT 0`

<span data-ttu-id="fbb95-151">其中，"AppVManagement" 是資料庫的名稱。</span><span class="sxs-lookup"><span data-stu-id="fbb95-151">where “AppVManagement” is the name of the database.</span></span>

## <span data-ttu-id="fbb95-152">如果您新增或移除選擇性套件，使用者就無法在使用者發佈的連線群組中開啟套件</span><span class="sxs-lookup"><span data-stu-id="fbb95-152">Users cannot open a package in a user-published connection group if you add or remove an optional package</span></span>


<span data-ttu-id="fbb95-153">在執行 RDS 用戶端的環境中，或在每個電腦上有多個併發使用者的情況下，如果在連線群組中新增或移除選擇性套件，則登入使用者無法開啟使用者發佈連線群組中的套件中的應用程式。</span><span class="sxs-lookup"><span data-stu-id="fbb95-153">In environments that are running the RDS Client or that have multiple concurrent users per computer, logged-in users cannot open applications in packages that are in a user-published connection group if an optional package is added to or removed from the connection group.</span></span>

<span data-ttu-id="fbb95-154">因應**措施：讓**使用者登出後再重新登入。</span><span class="sxs-lookup"><span data-stu-id="fbb95-154">**Workaround**: Have users log out and then log back in.</span></span>

## <span data-ttu-id="fbb95-155">當連線群組只發行給使用者時，會出現錯誤訊息</span><span class="sxs-lookup"><span data-stu-id="fbb95-155">Error message is erroneously displayed when the connection group is published only to the user</span></span>


<span data-ttu-id="fbb95-156">當您執行修復 AppvClientConnectionGroup 時，會顯示下列錯誤，即使連線群組只發行給使用者時也一樣：「內部 App-v 整合錯誤：套件未針對使用者整合。</span><span class="sxs-lookup"><span data-stu-id="fbb95-156">When you run Repair-AppvClientConnectionGroup, the following error is displayed, even when the connection group is published only to the user: “Internal App-V Integration error: Package not integrated for the user.</span></span> <span data-ttu-id="fbb95-157">請確定套件已新增至電腦併發布給使用者。</span><span class="sxs-lookup"><span data-stu-id="fbb95-157">Please ensure that the package is added to the machine and published to the user.”</span></span>

<span data-ttu-id="fbb95-158">**解決方法**：執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="fbb95-158">**Workaround**: Do one of the following:</span></span>

-   <span data-ttu-id="fbb95-159">發佈連線群組中的所有套件。</span><span class="sxs-lookup"><span data-stu-id="fbb95-159">Publish all packages in a connection group.</span></span>

    <span data-ttu-id="fbb95-160">當修復的連線群組有遺失或無法提供給使用者的套件（也就是不是全域發佈或使用者）時，就會發生此問題。</span><span class="sxs-lookup"><span data-stu-id="fbb95-160">The problem arises when the connection group being repaired has packages that are missing or not available to the user (that is, not published globally or to the user).</span></span> <span data-ttu-id="fbb95-161">不過，如果所有的連線群組套件都可用，修復就會運作，因此請確定所有套件都已發佈。</span><span class="sxs-lookup"><span data-stu-id="fbb95-161">However, the repair will work if all of the connection group’s packages are available, so ensure that all packages are published.</span></span>

-   <span data-ttu-id="fbb95-162">使用 [修復 AppvClientPackage] 命令（而不是 [修復] AppvClientConnectionGroup 命令）個別修復套件。</span><span class="sxs-lookup"><span data-stu-id="fbb95-162">Repair packages individually using the Repair-AppvClientPackage command rather than the Repair-AppvClientConnectionGroup command.</span></span>

    <span data-ttu-id="fbb95-163">決定使用者可以使用哪些套件，然後針對每個套件執行一次 AppvClientPackage 命令。</span><span class="sxs-lookup"><span data-stu-id="fbb95-163">Determine which packages are available to users and then run the Repair-AppvClientPackage command once for each package.</span></span> <span data-ttu-id="fbb95-164">使用 PowerShell Cmdlet 執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="fbb95-164">Use PowerShell cmdlets to do the following:</span></span>

    1.  <span data-ttu-id="fbb95-165">取得連接群組中的所有套件。</span><span class="sxs-lookup"><span data-stu-id="fbb95-165">Get all the packages in a connection group.</span></span>

    2.  <span data-ttu-id="fbb95-166">查看每個套件目前是否已發佈。</span><span class="sxs-lookup"><span data-stu-id="fbb95-166">Check to see if each package is currently published.</span></span>

    3.  <span data-ttu-id="fbb95-167">如果套件目前已發佈，請在該套件上執行 Repair AppvClientPackage。</span><span class="sxs-lookup"><span data-stu-id="fbb95-167">If the package is currently published, run Repair-AppvClientPackage on that package.</span></span>

## <span data-ttu-id="fbb95-168">無法在 Sequencer 中正確顯示圖示</span><span class="sxs-lookup"><span data-stu-id="fbb95-168">Icons not displayed properly in Sequencer</span></span>


<span data-ttu-id="fbb95-169">修改 App-v 排序器中的套件時，[快速鍵] 和 [檔案類型關聯] 索引標籤中的圖示無法正確顯示。</span><span class="sxs-lookup"><span data-stu-id="fbb95-169">Icons in the Shortcuts and File Type Associations tab are not displayed correctly when modifying a package in the App-V Sequencer.</span></span> <span data-ttu-id="fbb95-170">當圖示大小不是16x16 或32x32 時，就會發生此問題。</span><span class="sxs-lookup"><span data-stu-id="fbb95-170">This problem occurs when the size of the icons are not 16x16 or 32x32.</span></span>

<span data-ttu-id="fbb95-171">**解決方法**：只使用16x16 或32x32 的圖示。</span><span class="sxs-lookup"><span data-stu-id="fbb95-171">**Workaround**: Only use icons that are 16x16 or 32x32.</span></span>

## <span data-ttu-id="fbb95-172">管理資料庫已不再需要 InsertVersionInfo sql 腳本</span><span class="sxs-lookup"><span data-stu-id="fbb95-172">InsertVersionInfo.sql script no longer required for the Management Database</span></span>


<span data-ttu-id="fbb95-173">在 app-v 5.0 SP3 之後的 App-v management 資料庫版本中，不需要 InsertVersionInfo 腳本。</span><span class="sxs-lookup"><span data-stu-id="fbb95-173">The InsertVersionInfo.sql script is not required for versions of the App-V management database later than App-V 5.0 SP3.</span></span>

<span data-ttu-id="fbb95-174">必須依據[知識庫文章 3031340](https://support.microsoft.com/kb/3031340)中的**步驟 2**來更新 [sql 腳本]。</span><span class="sxs-lookup"><span data-stu-id="fbb95-174">The Permissions.sql script should be updated according to **Step 2** in [KB article 3031340](https://support.microsoft.com/kb/3031340).</span></span>

<span data-ttu-id="fbb95-175">**重要** 
在 app-v 5.0 SP3 的版本之後，不需要**步驟 1** 。</span><span class="sxs-lookup"><span data-stu-id="fbb95-175">**Important**
**Step 1** is not required for versions of App-V later than App-V 5.0 SP3.</span></span>

 

## <span data-ttu-id="fbb95-176">不支援 Microsoft Visual Studio 2012</span><span class="sxs-lookup"><span data-stu-id="fbb95-176">Microsoft Visual Studio 2012 not supported</span></span>


<span data-ttu-id="fbb95-177">App-V 5.1 不支援 Visual Studio 2012。</span><span class="sxs-lookup"><span data-stu-id="fbb95-177">App-V 5.1 does not support Visual Studio 2012.</span></span>

<span data-ttu-id="fbb95-178">因應**措施：無**</span><span class="sxs-lookup"><span data-stu-id="fbb95-178">**Workaround**: None</span></span>

## <span data-ttu-id="fbb95-179">App 的應用程式檔案名限制-V 5. 排序器</span><span class="sxs-lookup"><span data-stu-id="fbb95-179">Application filename restrictions for App-V 5.x Sequencer</span></span>


<span data-ttu-id="fbb95-180">App-V-x Sequencer 無法使用與 "CO_ x" 相符的檔案名來排序應用程式， &lt; &gt; 其中 x 是任何數位。</span><span class="sxs-lookup"><span data-stu-id="fbb95-180">The App-V 5.x Sequencer cannot sequence applications with filenames matching "CO_&lt;x&gt;" where x is any numeral.</span></span> <span data-ttu-id="fbb95-181">將會產生錯誤0x8007139F。</span><span class="sxs-lookup"><span data-stu-id="fbb95-181">Error 0x8007139F will be generated.</span></span>

<span data-ttu-id="fbb95-182">**解決方法**：使用不同的檔案名</span><span class="sxs-lookup"><span data-stu-id="fbb95-182">**Workaround**: Use a different filename</span></span>

## <span data-ttu-id="fbb95-183">裝載套件時，發生間歇性的 [找不到檔案] 錯誤</span><span class="sxs-lookup"><span data-stu-id="fbb95-183">Intermittent "File Not Found" error when Mounting a Package</span></span>


<span data-ttu-id="fbb95-184">在安裝套件時，有時會產生「找不到檔案」（0x80070002）錯誤。</span><span class="sxs-lookup"><span data-stu-id="fbb95-184">Occasionally when mounting a package, a "File Not Found" (0x80070002) error is generated.</span></span> <span data-ttu-id="fbb95-185">通常，當 App-v 中的資料夾包含許多檔案（亦即20K 或更多檔案）時，就會發生這種情況。</span><span class="sxs-lookup"><span data-stu-id="fbb95-185">Typically, this occurs when a folder in an App-V package contains many files ( i.e. 20K or more).</span></span> <span data-ttu-id="fbb95-186">這可能會導致串流時間超過預期，而且會產生「找不到檔案」錯誤的時間。</span><span class="sxs-lookup"><span data-stu-id="fbb95-186">This can cause streaming to take longer than expected and to time out which generates the "File Not Found" error.</span></span>

<span data-ttu-id="fbb95-187">因應**措施：從**HF06 開始，引入了新的登錄機碼，以啟用延伸此超時期間。</span><span class="sxs-lookup"><span data-stu-id="fbb95-187">**Workaround**: Starting with HF06, a new registry key has been introduced to enable extending this time-out period.</span></span>

<table>
<colgroup>
<col width="20%" />
<col width="80%" />
</colgroup>
<tbody>
<tr>
<td align="left"><span data-ttu-id="fbb95-188">路徑</span><span class="sxs-lookup"><span data-stu-id="fbb95-188">Path</span></span></td>
<td align="left"><span data-ttu-id="fbb95-189">HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\AppV\Client\Streaming</span><span class="sxs-lookup"><span data-stu-id="fbb95-189">HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\AppV\Client\Streaming</span></span></td>
</tr>
<tr>
<td align="left"><span data-ttu-id="fbb95-190">設定</span><span class="sxs-lookup"><span data-stu-id="fbb95-190">Setting</span></span></td>
<td align="left"><span data-ttu-id="fbb95-191">StreamResponseWaitTimeout</span><span class="sxs-lookup"><span data-stu-id="fbb95-191">StreamResponseWaitTimeout</span></span></td>
</tr>
<tr>
<td align="left"><span data-ttu-id="fbb95-192">類型</span><span class="sxs-lookup"><span data-stu-id="fbb95-192">DataType</span></span></td>
<td align="left"><span data-ttu-id="fbb95-193">DWORD</span><span class="sxs-lookup"><span data-stu-id="fbb95-193">DWORD</span></span></td>
</tr>
<tr>
<td align="left"><span data-ttu-id="fbb95-194">訂購</span><span class="sxs-lookup"><span data-stu-id="fbb95-194">Units</span></span></td>
<td align="left"><span data-ttu-id="fbb95-195">秒</span><span class="sxs-lookup"><span data-stu-id="fbb95-195">Seconds</span></span></td>
</tr>
<tr>
<td align="left"><span data-ttu-id="fbb95-196">預設值</span><span class="sxs-lookup"><span data-stu-id="fbb95-196">Default</span></span></td>
<td align="left"><span data-ttu-id="fbb95-197">500</span><span class="sxs-lookup"><span data-stu-id="fbb95-197">5</span></span><br />
<strong><span data-ttu-id="fbb95-198">注意 </strong> ：如果未定義登錄機碼或 &lt; 指定值 = 5，則此值為預設值。</span><span class="sxs-lookup"><span data-stu-id="fbb95-198">Note</strong>: this value is the default if the registry key is not defined or a value &lt;=5 is specified.</span></span>
</td>
</tr>
</tbody>
</table>






## <span data-ttu-id="fbb95-199">相關主題</span><span class="sxs-lookup"><span data-stu-id="fbb95-199">Related topics</span></span>


[<span data-ttu-id="fbb95-200">關於 App-V 5.1</span><span class="sxs-lookup"><span data-stu-id="fbb95-200">About App-V 5.1</span></span>](about-app-v-51.md)

 

 





