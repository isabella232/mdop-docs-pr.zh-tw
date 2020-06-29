---
title: 規劃伺服器安全性
description: 規劃伺服器安全性
author: dansimp
ms.assetid: c7cd8227-b359-41e7-a8ae-d0d5718a76a2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9bea1bd8287a15385200bbfb425ed8e00fbcdb02
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800912"
---
# <span data-ttu-id="8c712-103">規劃伺服器安全性</span><span class="sxs-lookup"><span data-stu-id="8c712-103">Planning for Server Security</span></span>


<span data-ttu-id="8c712-104">若要加強環境的安全性，您必須在環境中查看是否有任何可能的威脅。</span><span class="sxs-lookup"><span data-stu-id="8c712-104">To enhance the security of an environment, you must look at the exposure to any potential threats in the environment.</span></span> <span data-ttu-id="8c712-105">提供 App-v 基礎結構的安全性需要您使用特定的 App V 安全性功能，以及基礎基礎結構的安全做法和功能。</span><span class="sxs-lookup"><span data-stu-id="8c712-105">Providing security for an App-V infrastructure requires you to use the specific App-V security features as well as the security practices and features for the underlying infrastructure.</span></span> <span data-ttu-id="8c712-106">針對 Internet 資訊服務（IIS）、Active Directory 網域服務與 SQL Server 等服務，保護基礎基礎結構的安全，將會改善 App V 系統的整體安全性。</span><span class="sxs-lookup"><span data-stu-id="8c712-106">Securing the underlying infrastructure for services such as Internet Information Services (IIS), Active Directory Domain Services, and SQL Server will improve the overall security for your App-V system.</span></span>

<span data-ttu-id="8c712-107">伺服器安裝的預設設定會提供最高的安全性等級。</span><span class="sxs-lookup"><span data-stu-id="8c712-107">The default settings for the server installation provide the highest levels of security.</span></span> <span data-ttu-id="8c712-108">不過，某些元件依賴的基礎基礎結構並未設定為安裝的一部分。</span><span class="sxs-lookup"><span data-stu-id="8c712-108">However, some of the components rely on underlying infrastructure that is not configured as part of the installation.</span></span> <span data-ttu-id="8c712-109">依照安裝後的步驟進行後續步驟，將加強 App-v 基礎結構的安全性。</span><span class="sxs-lookup"><span data-stu-id="8c712-109">Following up with post-installation steps will enhance the security of the App-V infrastructure.</span></span>

<span data-ttu-id="8c712-110">內容目錄包含要流入用戶端的所有套件。</span><span class="sxs-lookup"><span data-stu-id="8c712-110">The content directory contains all of the packages that are to be streamed to clients.</span></span> <span data-ttu-id="8c712-111">這些資源必須盡可能安全，才能消除許多可能的安全性威脅。</span><span class="sxs-lookup"><span data-stu-id="8c712-111">These resources need to be as secure as possible to eliminate many possible security threats.</span></span> <span data-ttu-id="8c712-112">下列清單提供一些其他指導方針：</span><span class="sxs-lookup"><span data-stu-id="8c712-112">The following list offers some additional guidance:</span></span>

-   <span data-ttu-id="8c712-113">UNC 式發佈和/或資料流程：此專案的許可權在環境中應該是最嚴格的限制式。</span><span class="sxs-lookup"><span data-stu-id="8c712-113">UNC-based publishing and/or streaming—The permissions for this item should be the most restrictive in the environment.</span></span> <span data-ttu-id="8c712-114">使用 NTFS 許可權來針對內容目錄執行最嚴格限制的存取控制清單（Acl）（使用者 = 讀取，系統管理員 = 讀取和寫入）。</span><span class="sxs-lookup"><span data-stu-id="8c712-114">Use NTFS permissions to implement the most restrictive access control lists (ACLs) for the content directory (Users=Read, Administrators=Read and Write).</span></span>

-   <span data-ttu-id="8c712-115">用於發佈和/或資料流程的 IIS —將 IIS 設定為僅支援 Windows 整合式驗證。</span><span class="sxs-lookup"><span data-stu-id="8c712-115">IIS used for publishing and/or streaming—Configure IIS to support only Windows Integrated authentication.</span></span> <span data-ttu-id="8c712-116">移除 IIS 伺服器的匿名存取，並以 NTFS 許可權限制對目錄的存取權。</span><span class="sxs-lookup"><span data-stu-id="8c712-116">Remove anonymous access to the IIS server, and restrict access to the directory with NTFS permissions.</span></span>

-   <span data-ttu-id="8c712-117">RTSP/RTSPS 以串流應用程式套件-將 App-v 提供者原則設定為需要驗證、強制進行存取許可權，並僅允許必要的群組存取提供者原則。</span><span class="sxs-lookup"><span data-stu-id="8c712-117">RTSP/RTSPS to stream application packages—Configure the App-V Provider Policy to require authentication, enforce access permissions, and enable only required groups to have access to the provider policy.</span></span> <span data-ttu-id="8c712-118">在資料庫中使用適當的許可權來設定應用程式。</span><span class="sxs-lookup"><span data-stu-id="8c712-118">Configure applications with the appropriate permissions in the database.</span></span>

<span data-ttu-id="8c712-119">將具有管理許可權的使用者數保持在最小，以減少資料存放區中的資料可能威脅，並避免將惡意的應用程式發佈到基礎結構中。</span><span class="sxs-lookup"><span data-stu-id="8c712-119">Keep the number of users with administrative privileges to a minimum to reduce possible threats to the data in the data store and to avoid publishing malicious applications into the infrastructure.</span></span>

## <span data-ttu-id="8c712-120">應用程式虛擬化安全性</span><span class="sxs-lookup"><span data-stu-id="8c712-120">Application Virtualization Security</span></span>


<span data-ttu-id="8c712-121">App-V 在基礎結構的各個元件之間使用數種通訊方式。</span><span class="sxs-lookup"><span data-stu-id="8c712-121">App-V uses several methods of communication between the various components of the infrastructure.</span></span> <span data-ttu-id="8c712-122">規劃 app-v 基礎結構時，保護伺服器間的通訊可能會降低現有網路上可能已經存在的安全性風險。</span><span class="sxs-lookup"><span data-stu-id="8c712-122">When you plan your App-V infrastructure, securing the communications between servers can reduce the security risks that might already be present on the existing network.</span></span>

### <span data-ttu-id="8c712-123">資料存放區</span><span class="sxs-lookup"><span data-stu-id="8c712-123">Data Store</span></span>

<span data-ttu-id="8c712-124">應用程式虛擬化管理伺服器與應用程式虛擬化管理服務會透過 TCP 埠1433使用 SQL 連線來與資料存放區進行通訊。</span><span class="sxs-lookup"><span data-stu-id="8c712-124">The Application Virtualization Management Server and Application Virtualization Management Service communicate with the data store by using an SQL connection over TCP port 1433.</span></span> <span data-ttu-id="8c712-125">管理伺服器使用資料存放區來取得應用程式和設定資料，並將使用資訊寫入資料庫。</span><span class="sxs-lookup"><span data-stu-id="8c712-125">The Management Server uses the data store to retrieve application and configuration data, and it writes usage information to the database.</span></span> <span data-ttu-id="8c712-126">管理服務代表設定 App-v 基礎結構的管理員，與資料儲存區進行通訊。</span><span class="sxs-lookup"><span data-stu-id="8c712-126">The Management Service communicates with the data store on behalf of an administrator who is configuring the App-V infrastructure.</span></span> <span data-ttu-id="8c712-127">因為資料存放區包含重要資訊，所以請務必將此資料的威脅降至最低。</span><span class="sxs-lookup"><span data-stu-id="8c712-127">Because the data store contains critical information, it is important to minimize threats to this data.</span></span>

<span data-ttu-id="8c712-128">建議在 App-v 管理伺服器、管理服務與資料存放區之間的通訊使用網際網路通訊協定安全性（IPsec）加以保護。</span><span class="sxs-lookup"><span data-stu-id="8c712-128">It is recommended that communications between App-V Management Server, Management Service and the data store be secured with Internet Protocol Security (IPsec).</span></span> <span data-ttu-id="8c712-129">具體說來，建立可保護資料存放區（SQL）與管理伺服器以及資料存放區與管理服務之間通訊通道的原則。</span><span class="sxs-lookup"><span data-stu-id="8c712-129">Specifically, create policies that secure the communication channel between the data store (SQL) and the Management Server and the data store and the Management Service.</span></span> <span data-ttu-id="8c712-130">您也可以使用 [IPsec] 來部署伺服器與網域隔離，以確保所有 App-v 基礎結構元件只與安全通道進行通訊。</span><span class="sxs-lookup"><span data-stu-id="8c712-130">You can also deploy server and domain isolation with IPsec, ensuring all App-V infrastructure components communicate only with secure channels.</span></span> <span data-ttu-id="8c712-131">如需有關實施 IPsec 的資訊，請參閱下列檔：</span><span class="sxs-lookup"><span data-stu-id="8c712-131">For information about implementing IPsec, refer to the following documentation:</span></span>

-   <span data-ttu-id="8c712-132">若是 Windows Server2003，請參閱 <https://go.microsoft.com/fwlink/?LinkId=133226> （） https://go.microsoft.com/fwlink/?LinkId=133226) 。</span><span class="sxs-lookup"><span data-stu-id="8c712-132">For Windows Server2003, see <https://go.microsoft.com/fwlink/?LinkId=133226> (https://go.microsoft.com/fwlink/?LinkId=133226).</span></span>

-   <span data-ttu-id="8c712-133">若是 Windows Server2008，請參閱 <https://go.microsoft.com/fwlink/?LinkId=133227> （） https://go.microsoft.com/fwlink/?LinkId=133227) 。</span><span class="sxs-lookup"><span data-stu-id="8c712-133">For Windows Server2008, see <https://go.microsoft.com/fwlink/?LinkId=133227> (https://go.microsoft.com/fwlink/?LinkId=133227).</span></span>

### <span data-ttu-id="8c712-134">內容目錄</span><span class="sxs-lookup"><span data-stu-id="8c712-134">Content Directory</span></span>

<span data-ttu-id="8c712-135">App-v Management Server 安裝會設定內容目錄的位置。</span><span class="sxs-lookup"><span data-stu-id="8c712-135">The App-V Management Server installation configures a location for the content directory.</span></span> <span data-ttu-id="8c712-136">此目錄是虛擬化應用程式套件的儲存位置。</span><span class="sxs-lookup"><span data-stu-id="8c712-136">This directory is the storage location for virtualized application packages.</span></span> <span data-ttu-id="8c712-137">這個位置可以是伺服器的本地位置，也可以放在遠端網路共用上。</span><span class="sxs-lookup"><span data-stu-id="8c712-137">This location can be local to the server, or it can be placed on a remote network share.</span></span> <span data-ttu-id="8c712-138">因此，請實現 IPsec 以協助保護與內容目錄的遠端位置進行通訊。</span><span class="sxs-lookup"><span data-stu-id="8c712-138">Therefore, implement IPsec to help secure the communication with a remote location for the content directory.</span></span>

<span data-ttu-id="8c712-139">您也可以使用 IIS 伺服器上的虛擬目錄，將套件傳輸到用戶端。</span><span class="sxs-lookup"><span data-stu-id="8c712-139">You can also use a virtual directory on an IIS server to stream packages to the clients.</span></span> <span data-ttu-id="8c712-140">如果為內容建立的虛擬目錄位於遠端來源，請使用 IPsec 來協助保護 IIS 伺服器與遠端儲存位置之間的通訊。</span><span class="sxs-lookup"><span data-stu-id="8c712-140">If the virtual directory that is created for content is located on a remote source, use IPsec to help secure the communication between the IIS server and the remote storage location.</span></span>

<span data-ttu-id="8c712-141">內容目錄包含所有流入用戶端的套件。</span><span class="sxs-lookup"><span data-stu-id="8c712-141">The content directory contains all of the packages that are streamed to clients.</span></span> <span data-ttu-id="8c712-142">這些資源必須盡可能安全，才能消除許多可能的安全性威脅。</span><span class="sxs-lookup"><span data-stu-id="8c712-142">These resources need to be as secure as possible to eliminate many possible security threats.</span></span>

### <span data-ttu-id="8c712-143">安全性協定</span><span class="sxs-lookup"><span data-stu-id="8c712-143">Security Protocols</span></span>

<span data-ttu-id="8c712-144">您可以使用 RTSPS 或 HTTPS 來加強安全通訊。</span><span class="sxs-lookup"><span data-stu-id="8c712-144">You can use RTSPS or HTTPS for enhanced secure communications.</span></span> <span data-ttu-id="8c712-145">RTSPS 是應用程式 V 伺服器所使用的通訊協定，而 HTTPS 是 IIS 伺服器所使用的通訊協定。</span><span class="sxs-lookup"><span data-stu-id="8c712-145">RTSPS is the protocol used by App-V servers, and HTTPS is the protocol used by IIS servers.</span></span> <span data-ttu-id="8c712-146">從伺服器將應用程式發佈到應用程式虛擬化桌面用戶端時，會用到這些通訊協定。</span><span class="sxs-lookup"><span data-stu-id="8c712-146">These protocols are used when publishing applications from the server to the Application Virtualization Desktop Client.</span></span> <span data-ttu-id="8c712-147">在您決定想要的通訊協定後，請新增使用該通訊協定的發佈伺服器。</span><span class="sxs-lookup"><span data-stu-id="8c712-147">After you determine the desired protocol, add a publishing server that uses that protocol.</span></span>

### <a href="" id="configuring-app-v-servers-for-rtsps-"></a><span data-ttu-id="8c712-148">設定 RTSPS 的 App-v 伺服器</span><span class="sxs-lookup"><span data-stu-id="8c712-148">Configuring App-V Servers for RTSPS</span></span>

<span data-ttu-id="8c712-149">安裝或設定 App V 管理伺服器或流式伺服器若要使用 [增強的安全性（例如 TLS）]，必須將 x.509 V3 憑證預配至 App-v 伺服器。</span><span class="sxs-lookup"><span data-stu-id="8c712-149">Installing or configuring an App-V Management Server or Streaming Server to use Enhanced Security (for example, TLS) requires that an X.509 V3 certificate be provisioned to the App-V server.</span></span> <span data-ttu-id="8c712-150">當您準備安裝或設定伺服器的安全性時，必須履行一些特定需求。</span><span class="sxs-lookup"><span data-stu-id="8c712-150">When you prepare to install or configure security for a server, you must fulfill some specific requirements.</span></span> <span data-ttu-id="8c712-151">針對更安全的 App-v 管理伺服器或流式伺服器部署和設定憑證的技術需求包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="8c712-151">Technical requirements for deploying and configuring certificates for a more secure App-V Management Server or Streaming Server include the following:</span></span>

-   <span data-ttu-id="8c712-152">憑證必須是有效的。</span><span class="sxs-lookup"><span data-stu-id="8c712-152">Certificate must be valid.</span></span> <span data-ttu-id="8c712-153">否則，用戶端會終止連線。</span><span class="sxs-lookup"><span data-stu-id="8c712-153">Otherwise, the client terminates the connection.</span></span>

-   <span data-ttu-id="8c712-154">憑證必須包含正確的增強型金鑰用法（EKU）-伺服器驗證（OID 1.3.6.1.5.5.7.3.1）。</span><span class="sxs-lookup"><span data-stu-id="8c712-154">Certificate must contain the correct Enhanced Key Usage (EKU) - Server Authentication (OID 1.3.6.1.5.5.7.3.1).</span></span> <span data-ttu-id="8c712-155">否則，用戶端會終止連線。</span><span class="sxs-lookup"><span data-stu-id="8c712-155">Otherwise, the client terminates the connection.</span></span>

-   <span data-ttu-id="8c712-156">證書的完整功能變數名稱（FQDN）必須與安裝它的伺服器相符。</span><span class="sxs-lookup"><span data-stu-id="8c712-156">Certificate fully qualified domain name (FQDN) must match the server on which it is installed.</span></span> <span data-ttu-id="8c712-157">例如，如果用戶端正在通話 `RTSPS://Myserver.mycompany.com/content/MyApp.sft` ，但 [**頒發給**] 欄位的憑證包含 `Myserver1.mycompany.com` ，用戶端就不會連線到伺服器，而且會話會終止，即使 `Myserver.mycompany.com` 並 `Myserver1.mycompany.com` 解析為相同的 IP 位址也一樣。</span><span class="sxs-lookup"><span data-stu-id="8c712-157">For example, if the client is calling `RTSPS://Myserver.mycompany.com/content/MyApp.sft`, but the certificate **Issued To** field contains `Myserver1.mycompany.com`, the client will not connect to the server and the session is terminated, even if `Myserver.mycompany.com` and `Myserver1.mycompany.com` resolve to the same IP address.</span></span>

    <span data-ttu-id="8c712-158">**記事** 如果您在網路負載平衡群集中使用 App-v，則必須使用*Subject 替代名稱*（san）來設定憑證以支援 RTSPS。</span><span class="sxs-lookup"><span data-stu-id="8c712-158">**Note** If you use App-V in a network load balanced cluster, the certificate must be configured with *Subject Alternate Names* (SANs) to support RTSPS.</span></span> <span data-ttu-id="8c712-159">如需有關設定憑證授權單位（CA）及使用 San 建立憑證的詳細資訊，請參閱 <https://go.microsoft.com/fwlink/?LinkId=133228> （ https://go.microsoft.com/fwlink/?LinkId=133228) 。</span><span class="sxs-lookup"><span data-stu-id="8c712-159">For information about configuring the certification authority (CA) and creating certificates with SANs, see <https://go.microsoft.com/fwlink/?LinkId=133228> (https://go.microsoft.com/fwlink/?LinkId=133228).</span></span>

     

-   <span data-ttu-id="8c712-160">將憑證頒發給 App-v server 的 CA 必須受用戶端連線到伺服器的信任。</span><span class="sxs-lookup"><span data-stu-id="8c712-160">The CA issuing the certificate to the App-V server must be trusted by the client connecting to the server.</span></span> <span data-ttu-id="8c712-161">否則，用戶端會終止連線。</span><span class="sxs-lookup"><span data-stu-id="8c712-161">Otherwise, the client terminates the connection.</span></span>

-   <span data-ttu-id="8c712-162">您必須變更*證書私密金鑰*的許可權，才能透過伺服器 app-v 服務來啟用存取。</span><span class="sxs-lookup"><span data-stu-id="8c712-162">You must change the permissions for the *Certificate Private Key* to enable access by the Server App-V Service.</span></span> <span data-ttu-id="8c712-163">根據預設，應用程式 V 管理伺服器與流式處理伺服器服務會在網路服務帳戶下執行。</span><span class="sxs-lookup"><span data-stu-id="8c712-163">By default, the App-V Management Server and Streaming Server services run under the Network Service account.</span></span> <span data-ttu-id="8c712-164">當在伺服器上產生 PKCS \ #10 時，就會建立一個私用金鑰。</span><span class="sxs-lookup"><span data-stu-id="8c712-164">When a PKCS\#10 is generated on the server, a private key is created.</span></span> <span data-ttu-id="8c712-165">只有 [本機系統] 和 [管理員] 群組有權存取此金鑰。</span><span class="sxs-lookup"><span data-stu-id="8c712-165">Only the Local System and Administrators groups have access to this key.</span></span> <span data-ttu-id="8c712-166">這些預設 Acl 會防止 App-v 伺服器接受安全連線。</span><span class="sxs-lookup"><span data-stu-id="8c712-166">These default ACLs prevent the App-V server from accepting secure connections.</span></span>

    <span data-ttu-id="8c712-167">**記事** 如需有關設定公開金鑰基礎結構（PKI）的資訊，請參閱 <https://go.microsoft.com/fwlink/?LinkId=133229> （ https://go.microsoft.com/fwlink/?LinkId=133229) 。</span><span class="sxs-lookup"><span data-stu-id="8c712-167">**Note** For information about configuring a public key infrastructure (PKI), see <https://go.microsoft.com/fwlink/?LinkId=133229> (https://go.microsoft.com/fwlink/?LinkId=133229).</span></span>

     

### <span data-ttu-id="8c712-168">使用 HTTPS 設定 IIS 伺服器</span><span class="sxs-lookup"><span data-stu-id="8c712-168">Configuring IIS Servers with HTTPS</span></span>

<span data-ttu-id="8c712-169">App-v 可能會在某些基礎結構設定中使用 IIS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="8c712-169">App-V might use IIS servers in certain infrastructure configurations.</span></span> <span data-ttu-id="8c712-170">如需有關設定 IIS 伺服器的詳細資訊，請參閱 <https://go.microsoft.com/fwlink/?LinkId=133230> （） https://go.microsoft.com/fwlink/?LinkId=133230) 。</span><span class="sxs-lookup"><span data-stu-id="8c712-170">For more information about configuring IIS servers, see <https://go.microsoft.com/fwlink/?LinkId=133230> (https://go.microsoft.com/fwlink/?LinkId=133230).</span></span>

<span data-ttu-id="8c712-171">**記事** 如果您使用 IIS 來發佈 .ICO 和 OSD 檔案，請設定 OSD = TXT 的 MIME 類型;否則，IIS 將拒絕將 .ICO 和 OSD 檔案提供給用戶端。</span><span class="sxs-lookup"><span data-stu-id="8c712-171">**Note** If you are using IIS to publish the ICO and OSD files, configure a MIME type for OSD=TXT; otherwise, IIS will refuse to serve the ICO and OSD files to clients.</span></span>

 

### <span data-ttu-id="8c712-172">應用程式層級安全性</span><span class="sxs-lookup"><span data-stu-id="8c712-172">Application-Level Security</span></span>

<span data-ttu-id="8c712-173">您可以將伺服器設定為將特定應用程式資料流至使用者的桌面。</span><span class="sxs-lookup"><span data-stu-id="8c712-173">You can configure the servers to stream specific applications to a user’s desktop.</span></span> <span data-ttu-id="8c712-174">不過，實際是在封裝層級，而不是在應用程式層級授與存取許可權。</span><span class="sxs-lookup"><span data-stu-id="8c712-174">However, access permission actually is granted at the package level, not at the application level.</span></span> <span data-ttu-id="8c712-175">雖然特定應用程式可能無法發佈至使用者的桌面，但如果使用者有權新增應用程式或用戶端電腦上的系統管理員，則使用者可以在用戶端上建立並使用快捷方式來執行套件中的所有應用程式。</span><span class="sxs-lookup"><span data-stu-id="8c712-175">Although a specific application might not be published to the user’s desktop, if the user has permission to add applications or is an administrator on the client computer, the user can create and use a shortcut on the client to run all the applications in a package.</span></span>

## <span data-ttu-id="8c712-176">設定分散式環境的 App-V 系統管理</span><span class="sxs-lookup"><span data-stu-id="8c712-176">Configuring App-V Administration for a Distributed Environment</span></span>


<span data-ttu-id="8c712-177">針對您的特定組織設計基礎結構時，您可以在安裝 App-v Management Server 的電腦以外的電腦上安裝 App-v Management Web 服務。</span><span class="sxs-lookup"><span data-stu-id="8c712-177">When designing the infrastructure for your specific organization, you can install the App-V Management Web Service on a computer other than the computer where you install the App-V Management Server.</span></span> <span data-ttu-id="8c712-178">分隔這些 App V 元件的常見原因包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="8c712-178">Common reasons for separating these App-V components include the following:</span></span>

-   <span data-ttu-id="8c712-179">效能</span><span class="sxs-lookup"><span data-stu-id="8c712-179">Performance</span></span>

-   <span data-ttu-id="8c712-180">可靠性</span><span class="sxs-lookup"><span data-stu-id="8c712-180">Reliability</span></span>

-   <span data-ttu-id="8c712-181">可用性</span><span class="sxs-lookup"><span data-stu-id="8c712-181">Availability</span></span>

-   <span data-ttu-id="8c712-182">延展性</span><span class="sxs-lookup"><span data-stu-id="8c712-182">Scalability</span></span>

<span data-ttu-id="8c712-183">若要讓基礎結構正常運作，請在應用程式 V 管理主控台、管理伺服器與管理 Web 服務之間分隔，需要進行額外的設定。</span><span class="sxs-lookup"><span data-stu-id="8c712-183">For the infrastructure to operate correctly, separating the App-V Management Console, Management Server and Management Web Service requires additional configuration.</span></span> <span data-ttu-id="8c712-184">如需如何設定伺服器的詳細資訊，請參閱[如何將伺服器設定為信任委派](how-to-configure-the-server-to-be-trusted-for-delegation.md)。</span><span class="sxs-lookup"><span data-stu-id="8c712-184">For detailed information about how to configure the server, see [How to Configure the Server to be Trusted for Delegation](how-to-configure-the-server-to-be-trusted-for-delegation.md).</span></span>

## <span data-ttu-id="8c712-185">相關主題</span><span class="sxs-lookup"><span data-stu-id="8c712-185">Related topics</span></span>


[<span data-ttu-id="8c712-186">規劃安全性與保護</span><span class="sxs-lookup"><span data-stu-id="8c712-186">Planning for Security and Protection</span></span>](planning-for-security-and-protection.md)

 

 





