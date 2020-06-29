---
title: 規劃用戶端安全性
description: 規劃用戶端安全性
author: dansimp
ms.assetid: 4840a60f-4c91-489c-ad0b-6671882abf9b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e0038f7cbc8592d6c7fcdfa485111da88c17791d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800918"
---
# <span data-ttu-id="16ae3-103">規劃用戶端安全性</span><span class="sxs-lookup"><span data-stu-id="16ae3-103">Planning for Client Security</span></span>


<span data-ttu-id="16ae3-104">App-v 用戶端提供數個舊版產品中不存在的安全性增強功能。</span><span class="sxs-lookup"><span data-stu-id="16ae3-104">The App-V Client provides several security enhancements that were not present in previous versions of the product.</span></span> <span data-ttu-id="16ae3-105">這些變更可在安裝之後及日後設定用戶端設定時提供改良的安全性。</span><span class="sxs-lookup"><span data-stu-id="16ae3-105">These changes provide improved security after installation and through later configuration of the client settings.</span></span> <span data-ttu-id="16ae3-106">本主題說明其中一些增強功能，並指出您在規劃程式期間應考慮的幾個重要安全相關設定設定。</span><span class="sxs-lookup"><span data-stu-id="16ae3-106">This topic describes some of those enhancements and identifies several important security-related configuration settings that you should consider during your planning process.</span></span> <span data-ttu-id="16ae3-107">請務必記住，虛擬應用程式仍是可執行檔，因此您必須確保這些資產無法受到未經授權的人員篡改。</span><span class="sxs-lookup"><span data-stu-id="16ae3-107">It is important to remember that virtual applications are still executables, so you must ensure that these assets cannot be tampered with by unauthorized people.</span></span> <span data-ttu-id="16ae3-108">基於這個原因，開啟的軟體描述項（OSD）檔案快取會受到保護，如本主題稍後所述，我們強烈建議您使用 RTSPS、HTTPS 及 IPsec 來保護髮布和資料流程。</span><span class="sxs-lookup"><span data-stu-id="16ae3-108">For this reason, the Open Software Descriptor (OSD) file cache is protected as described later in this topic, and we strongly recommend that you use RTSPS, HTTPS, and IPsec to protect publishing and streaming.</span></span>

## <span data-ttu-id="16ae3-109">App-V 用戶端安全性</span><span class="sxs-lookup"><span data-stu-id="16ae3-109">App-V Client Security</span></span>


<span data-ttu-id="16ae3-110">根據預設，在安裝時，App-v 用戶端會設定為允許使用者執行發佈更新及啟動應用程式所需的最低許可權。</span><span class="sxs-lookup"><span data-stu-id="16ae3-110">By default, at installation the App-V client is configured with the minimum permissions required to allow a user to perform a publishing refresh and to start applications.</span></span> <span data-ttu-id="16ae3-111">App-V 用戶端提供的其他安全性增強功能包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="16ae3-111">Other security enhancements provided in the App-V client include the following:</span></span>

-   <span data-ttu-id="16ae3-112">根據預設，OSD 檔案快取只能由系統管理員更新，而是使用發佈重新整理程式。</span><span class="sxs-lookup"><span data-stu-id="16ae3-112">By default, the OSD file cache can be updated only by administrators and by using the publishing refresh process.</span></span>

-   <span data-ttu-id="16ae3-113">記錄檔（sftlog.txt）只有擁有用戶端的本機系統管理存取權的帳戶才能存取。</span><span class="sxs-lookup"><span data-stu-id="16ae3-113">The log file (sftlog.txt) is accessible only by accounts with local administrative access to the client.</span></span>

-   <span data-ttu-id="16ae3-114">記錄檔現在有最大大小。</span><span class="sxs-lookup"><span data-stu-id="16ae3-114">The log file now has a maximum size.</span></span>

### <span data-ttu-id="16ae3-115">檔案類型關聯</span><span class="sxs-lookup"><span data-stu-id="16ae3-115">File Type Associations</span></span>

<span data-ttu-id="16ae3-116">根據預設，安裝用戶端會為 OSD 檔案註冊檔案類型關聯（FTAs），讓使用者可以直接從 OSD 檔案啟動應用程式，而不是已發佈的快速鍵。</span><span class="sxs-lookup"><span data-stu-id="16ae3-116">By default, the installation of the client registers file type associations (FTAs) for OSD files, which enables users to start applications directly from OSD files instead of the published shortcuts.</span></span> <span data-ttu-id="16ae3-117">如果擁有本機系統管理員許可權的使用者收到包含惡意程式碼的 OSD 檔案（無論是透過電子郵件或從網站下載），使用者可以開啟 OSD 檔案並啟動應用程式，即使用戶端已設定為限制 [**新增應用程式**] 許可權。</span><span class="sxs-lookup"><span data-stu-id="16ae3-117">If a user with local administrator rights receives an OSD file containing malicious code, either in e-mail or downloaded from a Web site, the user can open the OSD file and start the application even if the client has been set to restrict the **Add Application** permission.</span></span> <span data-ttu-id="16ae3-118">您可以取消註冊 OSD 的 FTAs，以減少此風險。</span><span class="sxs-lookup"><span data-stu-id="16ae3-118">You can unregister the FTAs for the OSD to reduce this risk.</span></span> <span data-ttu-id="16ae3-119">此外，請考慮在電子郵件系統和防火牆封鎖此延伸。</span><span class="sxs-lookup"><span data-stu-id="16ae3-119">Also, consider blocking this extension in the e-mail system and at the firewall.</span></span> <span data-ttu-id="16ae3-120">如需設定 Outlook 封鎖延伸的詳細資訊，請參閱 <https://go.microsoft.com/fwlink/?LinkId=133278> 。</span><span class="sxs-lookup"><span data-stu-id="16ae3-120">For more information about configuring Outlook to block extensions, see <https://go.microsoft.com/fwlink/?LinkId=133278>.</span></span>

**<span data-ttu-id="16ae3-121">安全性注意事項：</span><span class="sxs-lookup"><span data-stu-id="16ae3-121">Security Note:</span></span>**

<span data-ttu-id="16ae3-122">從應用程式-V 版本4.6 開始，在新安裝用戶端期間，就不會再為 OSD 檔案建立檔案類型關聯，不過在從 App-v 用戶端的版本4.2 或4.5 升級期間，現有的設定將會保留。</span><span class="sxs-lookup"><span data-stu-id="16ae3-122">Starting with App-V version4.6, the file type association is no longer created for OSD files during a new installation of the client, although the existing settings will be maintained during an upgrade from version 4.2 or 4.5 of the App-V client.</span></span> <span data-ttu-id="16ae3-123">如果由於任何原因必須建立檔案類型關聯，您可以建立下列登錄機碼並設定其值，如下所示：</span><span class="sxs-lookup"><span data-stu-id="16ae3-123">If for any reason it is essential to create the file type association, you can create the following registry keys and set their values as shown:</span></span>

    Create HKEY\_CLASSES\_ROOT\\.osd with a default value of SoftGrid.osd.File

    Under HKEY\_LOCAL\_MACHINE\\software\\classes\\Softgrid.osd.file, create a string value named AppUserModelID with a data value of Microsoft.AppV.Client.Tray

### <span data-ttu-id="16ae3-124">授權</span><span class="sxs-lookup"><span data-stu-id="16ae3-124">Authorization</span></span>

<span data-ttu-id="16ae3-125">在安裝期間，您可以使用**RequireAuthorizationIfCached**參數來設定用戶端在使用者嘗試啟動應用程式時需要來自伺服器的授權。</span><span class="sxs-lookup"><span data-stu-id="16ae3-125">During installation, you can use the **RequireAuthorizationIfCached** parameter to configure the client to require authorization from the server when the user tries to start an application.</span></span> <span data-ttu-id="16ae3-126">您應該小心地考慮如何設定此參數。</span><span class="sxs-lookup"><span data-stu-id="16ae3-126">You should consider carefully how to set this parameter.</span></span> <span data-ttu-id="16ae3-127">如果 App-v 伺服器由於任何原因而無法使用，應用程式將會使用此參數最近儲存的狀態來控制使用者對應用程式的存取權。</span><span class="sxs-lookup"><span data-stu-id="16ae3-127">If the App-V server is unavailable for any reason, the application will use the most recent stored state of this parameter to control user access to the application.</span></span> <span data-ttu-id="16ae3-128">如果使用者在 App-v 伺服器無法使用前沒有成功啟動應用程式，則在它們可以與伺服器通訊並接收授權之前，將無法啟動該應用程式。</span><span class="sxs-lookup"><span data-stu-id="16ae3-128">If the user has not launched the application successfully before the App-V server becomes unavailable, they will not be able to launch the application until they can communicate with the server and receive authorization.</span></span> <span data-ttu-id="16ae3-129">不過，如果您將參數設定為用戶端不需要授權，且伺服器無法使用，則所有先前快取的應用程式都可以啟動（無論是否已獲授權）。</span><span class="sxs-lookup"><span data-stu-id="16ae3-129">However, if you set the parameter so that the client does not require authorization and if the server is unavailable, all previously cached applications can be started whether authorized or not.</span></span> <span data-ttu-id="16ae3-130">此外，如果使用者有權透過許可權將用戶端變更為 [離線] 模式，或者如果使用者是本機管理員，則使用者可以開啟所有快取的套件，就像 App-v 基礎結構無法使用一樣。</span><span class="sxs-lookup"><span data-stu-id="16ae3-130">Also, if the user has permission to change the client to Work Offline mode through permissions or if the user is a local administrator, the user would be able to open all cached packages as if the App-V infrastructure was unavailable.</span></span>

### <span data-ttu-id="16ae3-131">防病毒掃描</span><span class="sxs-lookup"><span data-stu-id="16ae3-131">Antivirus Scanning</span></span>

<span data-ttu-id="16ae3-132">在 App-V 用戶端電腦上執行的防毒軟體可以在虛擬環境中偵測並報告感染病毒的檔案。</span><span class="sxs-lookup"><span data-stu-id="16ae3-132">Antivirus software running on an App-V Client computer can detect and report an infected file in the virtual environment.</span></span> <span data-ttu-id="16ae3-133">不過，它無法殺毒檔案。</span><span class="sxs-lookup"><span data-stu-id="16ae3-133">However, it cannot disinfect the file.</span></span> <span data-ttu-id="16ae3-134">如果在虛擬環境中偵測到病毒，防毒軟體將會在快取中執行已設定的隔離或修復作業，而不是在實際的套件中執行。</span><span class="sxs-lookup"><span data-stu-id="16ae3-134">If a virus is detected in the virtual environment, the antivirus software would perform the configured quarantine or repair operation in the cache, not in the actual package.</span></span> <span data-ttu-id="16ae3-135">針對 sftfs 檔案設定防毒軟體，並提供例外狀況。</span><span class="sxs-lookup"><span data-stu-id="16ae3-135">Configure the antivirus software with an exception for the sftfs.fsd file.</span></span> <span data-ttu-id="16ae3-136">此檔案是將套件儲存在 App-v 用戶端的快取檔案。</span><span class="sxs-lookup"><span data-stu-id="16ae3-136">This file is the cache file that stores packages on the App-V Client.</span></span>

**<span data-ttu-id="16ae3-137">安全性注意事項：</span><span class="sxs-lookup"><span data-stu-id="16ae3-137">Security Note:</span></span>**

<span data-ttu-id="16ae3-138">如果在生產環境中部署的應用程式或套件中偵測到病毒，請以無病毒版本取代應用程式或套件。</span><span class="sxs-lookup"><span data-stu-id="16ae3-138">If a virus is detected in an application or package deployed in the production environment, replace the application or package with a virus-free version.</span></span>

## <span data-ttu-id="16ae3-139">用戶端與伺服器之間的通訊</span><span class="sxs-lookup"><span data-stu-id="16ae3-139">Communication Between Client and Server</span></span>


<span data-ttu-id="16ae3-140">發佈更新及套件資料流程也是與用戶端伺服器通訊相關的安全性考慮的區域。</span><span class="sxs-lookup"><span data-stu-id="16ae3-140">Publishing refreshes and package streaming are also areas where security considerations relating to client-server communication are important.</span></span>

### <span data-ttu-id="16ae3-141">發佈更新</span><span class="sxs-lookup"><span data-stu-id="16ae3-141">Publishing Refresh</span></span>

<span data-ttu-id="16ae3-142">當用戶端與伺服器通訊以執行發佈重新整理時，它會使用已登入使用者的認證來要求應用程式套件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="16ae3-142">When the client communicates with the server to perform a publishing refresh, it uses the credentials of the logged on user to request information about the application packages.</span></span> <span data-ttu-id="16ae3-143">您應該保護在 App V 用戶端與 App-v 管理伺服器之間發生的通訊，以確保任何發佈資訊都無法在傳輸中受到篡改。</span><span class="sxs-lookup"><span data-stu-id="16ae3-143">You should secure the communication that occurs between the App-V client and App-V Management Server to ensure that none of the publishing information can be tampered with in transit.</span></span> <span data-ttu-id="16ae3-144">這是使用 [增強安全性] 選項完成，這會使用 RTSPS/HTTPS。</span><span class="sxs-lookup"><span data-stu-id="16ae3-144">This is done by using the Enhanced Security option, which will use RTSPS/HTTPS.</span></span> <span data-ttu-id="16ae3-145">在用戶端與 [.ICO] 和 [OSD] 檔案儲存位置之間的通訊，應該使用 IPsec 來取得 SMB/CIFS 共用和 HTTPS （適用于 IIS 伺服器）。</span><span class="sxs-lookup"><span data-stu-id="16ae3-145">Communication between the Client and the location where the ICO and OSD files are stored should use IPsec for SMB/CIFS shares and HTTPS for an IIS server.</span></span>

<span data-ttu-id="16ae3-146">**記事** 如果您使用 IIS 來發佈 .ICO 和 OSD 檔案，請設定 OSD = TXT 的 MIME 類型;否則，IIS 將拒絕將 .ICO 和 OSD 檔案提供給用戶端。</span><span class="sxs-lookup"><span data-stu-id="16ae3-146">**Note** If you are using IIS to publish the ICO and OSD files, configure a MIME type for OSD=TXT; otherwise, IIS will refuse to serve the ICO and OSD files to clients.</span></span>

 

### <span data-ttu-id="16ae3-147">套件資料流程</span><span class="sxs-lookup"><span data-stu-id="16ae3-147">Package Streaming</span></span>

<span data-ttu-id="16ae3-148">當使用者第一次啟動應用程式時，或者如果在用戶端上已設定自動載入參數，應用程式套件會從伺服器流向用戶端快取。</span><span class="sxs-lookup"><span data-stu-id="16ae3-148">When a user launches an application for the first time, or if auto-loading parameters have been set on the client, the application package is streamed from a server to the client cache.</span></span> <span data-ttu-id="16ae3-149">這個程式支援 RTSP/RTSPS、HTTP/HTTPS 及 SMB/CIFS 通訊協定。</span><span class="sxs-lookup"><span data-stu-id="16ae3-149">This process supports the RTSP/RTSPS, HTTP/HTTPS, and SMB/CIFS protocols.</span></span> <span data-ttu-id="16ae3-150">除非用戶端上已設定**ApplicationSourceRoot**或**OverrideURL**設定，否則 OSD 檔案就會控制所使用的通訊協定。</span><span class="sxs-lookup"><span data-stu-id="16ae3-150">The OSD files control which protocols are used, unless the **ApplicationSourceRoot** or **OverrideURL** setting has been configured on the clients.</span></span> <span data-ttu-id="16ae3-151">您應該設定與 SMB/CIFS 的 RTSPS、HTTPS 或 IPsec 進行通訊，以達到較高的安全性。</span><span class="sxs-lookup"><span data-stu-id="16ae3-151">You should configure communication to occur over RTSPS, HTTPS, or IPsec for SMB/CIFS to achieve higher levels of security.</span></span> <span data-ttu-id="16ae3-152">如需有關如何選擇要使用哪種通訊方法的詳細資訊，請參閱 App V 規劃與部署指南 <https://go.microsoft.com/fwlink/?LinkId=122063> 。</span><span class="sxs-lookup"><span data-stu-id="16ae3-152">For more information about choosing which communication method to use, see the App-V Planning and Deployment Guide at <https://go.microsoft.com/fwlink/?LinkId=122063>.</span></span>

<span data-ttu-id="16ae3-153">**記事** 如果您使用 IIS 發佈套件（SFT 檔案），請針對 SFT = Binary 設定 MIME 類型;否則，IIS 將拒絕將 SFT 檔案提供給用戶端。</span><span class="sxs-lookup"><span data-stu-id="16ae3-153">**Note** If you are using IIS to publish packages (SFT files), configure a MIME type for SFT=Binary; otherwise, IIS will refuse to serve the SFT files to clients.</span></span>

 

### <span data-ttu-id="16ae3-154">漫遊設定檔與資料夾重新導向</span><span class="sxs-lookup"><span data-stu-id="16ae3-154">Roaming Profiles and Folder Redirection</span></span>

<span data-ttu-id="16ae3-155">App-v 系統會將使用者特定的變更儲存至 usrvol \ _sftfs \ _v1 installer.pkg 檔案中的套件。</span><span class="sxs-lookup"><span data-stu-id="16ae3-155">The App-V system stores user-specific changes to packages in the usrvol\_sftfs\_v1.pkg file.</span></span> <span data-ttu-id="16ae3-156">此檔案位於使用者設定檔的 [應用程式資料] 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="16ae3-156">This file is located in the Application Data folder of a user’s profile.</span></span> <span data-ttu-id="16ae3-157">因為設定檔或重新導向的應用程式資料檔案夾是在用戶端與伺服器之間傳輸，所以請使用 IPsec 來保護通訊。</span><span class="sxs-lookup"><span data-stu-id="16ae3-157">Because the profile or a redirected Application Data folder is transferred between the client and the server, use IPsec to secure the communication.</span></span>

## <span data-ttu-id="16ae3-158">面向網際網路的用戶端注意事項</span><span class="sxs-lookup"><span data-stu-id="16ae3-158">Considerations for Internet-Facing Clients</span></span>


<span data-ttu-id="16ae3-159">對於面向網際網路的用戶端，請務必考慮用戶端是否已加入網域或未加入網域。</span><span class="sxs-lookup"><span data-stu-id="16ae3-159">For Internet-facing clients, it is important to consider whether the client is domain joined or non-domain joined.</span></span>

### <span data-ttu-id="16ae3-160">網域加入用戶端</span><span class="sxs-lookup"><span data-stu-id="16ae3-160">Domain Joined Client</span></span>

<span data-ttu-id="16ae3-161">根據預設，App-v 用戶端會使用 Active Directory 網域服務在內部網路上進行驗證和授權所頒發的 Kerberos 票證。</span><span class="sxs-lookup"><span data-stu-id="16ae3-161">By default, App-V Clients use Kerberos tickets that were issued by Active Directory Domain Services for authentication and authorization on the intranet.</span></span> <span data-ttu-id="16ae3-162">這些 Kerberos 票證預設有效期為10小時。</span><span class="sxs-lookup"><span data-stu-id="16ae3-162">These Kerberos tickets are valid for 10 hours by default.</span></span> <span data-ttu-id="16ae3-163">只要票證有效，用戶端就會使用此票證存取 App-v server，即使電腦無法連線至網網域控制站以重新整理票證也一樣。</span><span class="sxs-lookup"><span data-stu-id="16ae3-163">The client will use this ticket to access the App-V server for as long as the ticket is valid, even if the computer is unable to connect to the domain controller to refresh the ticket.</span></span> <span data-ttu-id="16ae3-164">如果 Kerberos 票證到期，應用程式-V 用戶端將會還原為 NTLM 驗證，並使用使用者的快取認證。</span><span class="sxs-lookup"><span data-stu-id="16ae3-164">If the Kerberos ticket expires, the App-V client will revert to NTLM authentication and use the user’s cached credentials.</span></span>

### <span data-ttu-id="16ae3-165">非網域加入的用戶端</span><span class="sxs-lookup"><span data-stu-id="16ae3-165">Non-Domain Joined Client</span></span>

<span data-ttu-id="16ae3-166">如果使用者是家用的，且電腦未加入公司網域，App-v 仍可支援提供應用程式。</span><span class="sxs-lookup"><span data-stu-id="16ae3-166">If a user is home-based and the computer is not joined to the company domain, App-V can still support delivering applications.</span></span> <span data-ttu-id="16ae3-167">若要驗證及授權使用者執行發佈重新整理並啟動應用程式，請設定用戶端電腦上的使用者帳戶，以儲存可存取 app-v 環境的使用者名稱和密碼，並提供應用程式的適當許可權。</span><span class="sxs-lookup"><span data-stu-id="16ae3-167">To authenticate and authorize a user to perform a publishing refresh and to start applications, configure the user account on the client computer to store the user name and password that has access to the App-V environment and to provide appropriate permissions to the applications.</span></span>

## <span data-ttu-id="16ae3-168">相關主題</span><span class="sxs-lookup"><span data-stu-id="16ae3-168">Related topics</span></span>


[<span data-ttu-id="16ae3-169">規劃安全性與保護</span><span class="sxs-lookup"><span data-stu-id="16ae3-169">Planning for Security and Protection</span></span>](planning-for-security-and-protection.md)

 

 





