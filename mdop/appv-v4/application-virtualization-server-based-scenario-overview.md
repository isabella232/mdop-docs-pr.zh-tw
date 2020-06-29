---
title: 以 Application Virtualization 伺服器為基礎的案例概觀
description: 以 Application Virtualization 伺服器為基礎的案例概觀
author: dansimp
ms.assetid: 2d91392b-5085-4a5d-94f2-15eed1ed2928
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7b3ac3f10a5b7c7705e6d72c122d52be801a6d50
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809147"
---
# <span data-ttu-id="0818c-103">以 Application Virtualization 伺服器為基礎的案例概觀</span><span class="sxs-lookup"><span data-stu-id="0818c-103">Application Virtualization Server-Based Scenario Overview</span></span>


<span data-ttu-id="0818c-104">如果您打算針對您的 Microsoft 應用程式虛擬化環境使用以伺服器為基礎的部署案例，請務必瞭解*應用程式虛擬化管理伺服器*與*應用程式虛擬化資料流程伺服器*之間的差異。</span><span class="sxs-lookup"><span data-stu-id="0818c-104">If you plan to use a server-based deployment scenario for your Microsoft Application Virtualization environment, it is important to understand the differences between the *Application Virtualization Management Server* and the *Application Virtualization Streaming Server*.</span></span> <span data-ttu-id="0818c-105">本主題描述這些差異，並提供封裝傳遞方法、傳輸通訊協定和外部元件的相關資訊，在您繼續進行部署時，您將需要考慮。</span><span class="sxs-lookup"><span data-stu-id="0818c-105">This topic describes those differences and also provides information about package delivery methods, transmission protocols, and external components that you will need to consider as you proceed with your deployment.</span></span>

## <span data-ttu-id="0818c-106">應用程式虛擬化管理伺服器</span><span class="sxs-lookup"><span data-stu-id="0818c-106">Application Virtualization Management Server</span></span>


<span data-ttu-id="0818c-107">應用程式虛擬化管理伺服器會執行發佈功能與流式處理函數。</span><span class="sxs-lookup"><span data-stu-id="0818c-107">The Application Virtualization Management Server performs both the publishing function and the streaming function.</span></span> <span data-ttu-id="0818c-108">伺服器會將應用程式圖示、快速鍵及檔案類型關聯發佈到適用于已授權使用者的 App-v 用戶端。</span><span class="sxs-lookup"><span data-stu-id="0818c-108">The server publishes application icons, shortcuts, and file type associations to the App-V clients for authorized users.</span></span> <span data-ttu-id="0818c-109">當使用者要求應用程式要求時，系統會使用 RTSP 或 RTSPS 通訊協定，將資料按需求傳送給授權的使用者。</span><span class="sxs-lookup"><span data-stu-id="0818c-109">When user requests for applications are received the server streams that data on-demand to authorized users using RTSP or RTSPS protocols.</span></span> <span data-ttu-id="0818c-110">在使用這個伺服器的大部分配置中，一或多個管理伺服器會共用一個常見的資料存放區，以取得設定和封裝資訊。</span><span class="sxs-lookup"><span data-stu-id="0818c-110">In most configurations using this server, one or more Management Servers share a common data store for configuration and package information.</span></span>

<span data-ttu-id="0818c-111">應用程式虛擬化管理伺服器使用 Active Directory 群組來管理使用者的授權。</span><span class="sxs-lookup"><span data-stu-id="0818c-111">The Application Virtualization Management Servers use Active Directory groups to manage user authorization.</span></span> <span data-ttu-id="0818c-112">除了 Active Directory 網域服務之外，這些伺服器還安裝 SQL Server 來管理資料庫和資料存放區。</span><span class="sxs-lookup"><span data-stu-id="0818c-112">In addition to Active Directory Domain Services, these servers have SQL Server installed to manage the database and data store.</span></span> <span data-ttu-id="0818c-113">管理伺服器是透過應用程式虛擬化管理主控台（由 Microsoft 管理主控台的一個快照）來控制。</span><span class="sxs-lookup"><span data-stu-id="0818c-113">The Management Server is controlled through the Application Virtualization Management Console, a snap-in to the Microsoft Management Console.</span></span>

<span data-ttu-id="0818c-114">由於應用程式虛擬化管理伺服器會根據需求將應用程式流式處理應用程式，因此這些伺服器非常適合擁有可靠、高頻寬局域網的系統組態。</span><span class="sxs-lookup"><span data-stu-id="0818c-114">Because the Application Virtualization Management Servers stream applications to end-users on demand, these servers are ideally suited for system configurations that have reliable, high-bandwidth LANs.</span></span>

## <span data-ttu-id="0818c-115">應用程式虛擬化資料流程伺服器</span><span class="sxs-lookup"><span data-stu-id="0818c-115">Application Virtualization Streaming Server</span></span>


<span data-ttu-id="0818c-116">應用程式虛擬化資料流程伺服器會提供管理伺服器所提供的相同資料流程與套件升級功能，但不含其 Active Directory 或 SQL Server 的需求。</span><span class="sxs-lookup"><span data-stu-id="0818c-116">The Application Virtualization Streaming Server delivers the same streaming and package upgrade capabilities provided by the Management Server, but without its Active Directory or SQL Server requirements.</span></span> <span data-ttu-id="0818c-117">不過，流式處理伺服器沒有發佈服務，也沒有授權或測定功能。</span><span class="sxs-lookup"><span data-stu-id="0818c-117">However, the Streaming Server does not have a publishing service, nor does it have licensing or metering capabilities.</span></span> <span data-ttu-id="0818c-118">個別的 App-v 管理伺服器的發佈服務會與 App-v 資料流程伺服器搭配使用。</span><span class="sxs-lookup"><span data-stu-id="0818c-118">The publishing service of a separate App-V Management Server is used in conjunction with the App-V Streaming Server.</span></span> <span data-ttu-id="0818c-119">App-v 流式處理伺服器可滿足在多個位置使用應用程式虛擬化的企業需求，以及傳統伺服器設定的資料流程功能，但在每個位置中可能不會有支援 App-v 管理伺服器的基礎結構。</span><span class="sxs-lookup"><span data-stu-id="0818c-119">The App-V Streaming Server addresses the needs of businesses that want to use Application Virtualization in multiple locations with the streaming capabilities of the classic server configuration but might not have the infrastructure to support App-V Management Servers in every location.</span></span>

<span data-ttu-id="0818c-120">應用程式虛擬化資料流程伺服器也可以在具備現有電子軟體發佈系統（ESD）的環境中使用。</span><span class="sxs-lookup"><span data-stu-id="0818c-120">The Application Virtualization Streaming Server can also be used in environments with an existing electronic software distribution system (ESD).</span></span> <span data-ttu-id="0818c-121">您使用 ESD 來管理流式處理應用程式。</span><span class="sxs-lookup"><span data-stu-id="0818c-121">You use the ESD to manage streaming applications.</span></span> <span data-ttu-id="0818c-122">與應用程式虛擬化管理伺服器不同，流式處理伺服器不使用 SQL 或管理主控台。</span><span class="sxs-lookup"><span data-stu-id="0818c-122">Unlike the Application Virtualization Management Server, the Streaming Server does not use SQL or a management console.</span></span> <span data-ttu-id="0818c-123">這些伺服器使用存取控制清單（Acl）來授與使用者的授權。</span><span class="sxs-lookup"><span data-stu-id="0818c-123">These servers use access control lists (ACLs) to grant user authorization.</span></span>

## <span data-ttu-id="0818c-124">封裝傳送方法</span><span class="sxs-lookup"><span data-stu-id="0818c-124">Package Delivery Methods</span></span>


<span data-ttu-id="0818c-125">如果您打算使用應用程式虛擬化伺服器作為發佈傳送方法，您必須判斷您的案例會採用下列哪一種套件傳遞方法：</span><span class="sxs-lookup"><span data-stu-id="0818c-125">If you plan to use an Application Virtualization Server as the publishing delivery method, you need to determine which of the following package delivery methods your scenario employs:</span></span>

-   *<span data-ttu-id="0818c-126">動態套件遞送</span><span class="sxs-lookup"><span data-stu-id="0818c-126">Dynamic package delivery</span></span>*

-   *<span data-ttu-id="0818c-127">從檔案套件傳送中載入</span><span class="sxs-lookup"><span data-stu-id="0818c-127">Load from file package delivery</span></span>*

### <span data-ttu-id="0818c-128">動態套件遞送</span><span class="sxs-lookup"><span data-stu-id="0818c-128">Dynamic Package Delivery</span></span>

<span data-ttu-id="0818c-129">在動態套件遞送期間，伺服器（應用程式虛擬化管理伺服器、應用程式虛擬化資料流程伺服器或 IIS 伺服器）透過隨選部署將虛擬化的應用程式傳送給最終使用者。</span><span class="sxs-lookup"><span data-stu-id="0818c-129">During dynamic package delivery, the server (Application Virtualization Management Server, Application Virtualization Streaming Server, or IIS server) delivers the virtualized applications to the end users through on-demand deployment.</span></span> <span data-ttu-id="0818c-130">只有在使用者第一次嘗試啟動應用程式時（根據需求），伺服器才會將虛擬化的應用程式和套件傳送到用戶端電腦。</span><span class="sxs-lookup"><span data-stu-id="0818c-130">The server delivers the virtualized applications and packages to a client computer only when a user first attempts to launch an application (on demand).</span></span> <span data-ttu-id="0818c-131">伺服器只會資料流程啟動應用程式所需的區塊（主要功能區塊）。</span><span class="sxs-lookup"><span data-stu-id="0818c-131">The server streams only the blocks needed to start the application (primary feature block).</span></span> <span data-ttu-id="0818c-132">在主要功能區區塊轉送到用戶端之後，應用程式會執行;用戶端不會收到完整的應用程式（增量式部署），除非用戶端需要存取不在主要功能區塊中的部分應用程式。</span><span class="sxs-lookup"><span data-stu-id="0818c-132">After the primary feature block is delivered to the client, the application runs; the client does not receive the complete application (incremental deployment) unless the client needs access to a part of the application that is not included in the primary feature block.</span></span> <span data-ttu-id="0818c-133">發生這種情況時，用戶端會執行順序外的要求，而次要功能區塊則會以資料流程傳送給用戶端。</span><span class="sxs-lookup"><span data-stu-id="0818c-133">When this occurs, the client performs an out-of-sequence request and the secondary feature block is streamed to the client.</span></span> <span data-ttu-id="0818c-134">動態套件傳遞可讓應用程式快速啟動。</span><span class="sxs-lookup"><span data-stu-id="0818c-134">Dynamic package delivery allows for rapid application launch.</span></span>

### <span data-ttu-id="0818c-135">從檔案套件傳送中載入</span><span class="sxs-lookup"><span data-stu-id="0818c-135">Load from File Package Delivery</span></span>

<span data-ttu-id="0818c-136">若要從檔案套件傳送載入，伺服器會在使用者啟動應用程式之前，將整個虛擬化的應用程式套件傳送到用戶端電腦。</span><span class="sxs-lookup"><span data-stu-id="0818c-136">For load from file package delivery, the server delivers the entire virtualized application package to a client computer before the user launches the application.</span></span> <span data-ttu-id="0818c-137">在這種情況下，虛擬化的應用程式是以完整套件的形式傳送，而不是透過動態傳遞模型所使用的動態、增量方法來傳送。</span><span class="sxs-lookup"><span data-stu-id="0818c-137">In this scenario, virtualized applications are delivered as a full package, rather than through the dynamic, incremental method used by the dynamic delivery model.</span></span>

<span data-ttu-id="0818c-138">**記事** 針對每個傳遞方法，初始的虛擬應用程式傳遞程式和虛擬應用程式更新程式都相同;已更新的虛擬應用程式套件會取代原始應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="0818c-138">**Note** For each delivery method, the initial virtual application delivery process and the virtual application update process are the same; the updated virtual application package replaces the original application package.</span></span>

 

<span data-ttu-id="0818c-139">下表比較每個套件傳送方法的優點與缺點。</span><span class="sxs-lookup"><span data-stu-id="0818c-139">The following table compares the advantages and disadvantages of each package delivery method.</span></span>

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="0818c-140">方法</span><span class="sxs-lookup"><span data-stu-id="0818c-140">Method</span></span></th>
<th align="left"><span data-ttu-id="0818c-141">優點</span><span class="sxs-lookup"><span data-stu-id="0818c-141">Advantages</span></span></th>
<th align="left"><span data-ttu-id="0818c-142">缺點</span><span class="sxs-lookup"><span data-stu-id="0818c-142">Disadvantages</span></span></th>
<th align="left"><span data-ttu-id="0818c-143">註解</span><span class="sxs-lookup"><span data-stu-id="0818c-143">Comments</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0818c-144">動態套件遞送</span><span class="sxs-lookup"><span data-stu-id="0818c-144">Dynamic package delivery</span></span></p></td>
<td align="left"><p><span data-ttu-id="0818c-145">應用程式會根據需求傳送並更新。</span><span class="sxs-lookup"><span data-stu-id="0818c-145">Applications are delivered and updated on demand.</span></span></p>
<p><span data-ttu-id="0818c-146">應用程式會以遞增的方式進行傳遞並更新，以優化啟動時間。</span><span class="sxs-lookup"><span data-stu-id="0818c-146">Applications are delivered and updated incrementally to optimize launch time.</span></span></p>
<p><span data-ttu-id="0818c-147">更新會自動傳送到用戶端桌面。</span><span class="sxs-lookup"><span data-stu-id="0818c-147">Updates are delivered automatically to the client desktop.</span></span></p></td>
<td align="left"><p><span data-ttu-id="0818c-148">由於伺服器需求，企業拓朴中的需求量較大。</span><span class="sxs-lookup"><span data-stu-id="0818c-148">Larger footprint in enterprise topology because of server requirements.</span></span></p>
<p><span data-ttu-id="0818c-149">應用程式資料流程應該在局域網上;WAN 上的部署案例或在伺服器與用戶端之間使用不可靠或間歇性連接的情況，可能無法使用。</span><span class="sxs-lookup"><span data-stu-id="0818c-149">Application streaming should be over a LAN; deployment scenarios over a WAN or that use an unreliable or intermittent connection between the server and client might be unusable.</span></span></p></td>
<td align="left"><p><span data-ttu-id="0818c-150">需要流式處理基礎結構。</span><span class="sxs-lookup"><span data-stu-id="0818c-150">Requires a streaming infrastructure.</span></span></p>
<p><span data-ttu-id="0818c-151">用來將應用程式虛擬化桌面用戶端軟體部署到終端使用者電腦的 Windows 安裝程式。</span><span class="sxs-lookup"><span data-stu-id="0818c-151">Windows Installer used to deploy Application Virtualization Desktop Client software to end-user computers.</span></span></p>
<p><span data-ttu-id="0818c-152">大型企業應該使用應用程式虛擬化資料流程伺服器作為發佈點。</span><span class="sxs-lookup"><span data-stu-id="0818c-152">Large enterprises should use Application Virtualization Streaming Servers as distribution points.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0818c-153">從檔案套件傳送中載入</span><span class="sxs-lookup"><span data-stu-id="0818c-153">Load from file package delivery</span></span></p></td>
<td align="left"><p><span data-ttu-id="0818c-154">與典型的企業管理做法一致。</span><span class="sxs-lookup"><span data-stu-id="0818c-154">Consistent with typical enterprise management practices.</span></span></p>
<p><span data-ttu-id="0818c-155">支援獨立的配置案例。</span><span class="sxs-lookup"><span data-stu-id="0818c-155">Supports stand-alone configuration scenario.</span></span></p>
<p><span data-ttu-id="0818c-156">提供對 office 的微分支問題的解決方案。</span><span class="sxs-lookup"><span data-stu-id="0818c-156">Provides solution to micro–branch office problem.</span></span></p></td>
<td align="left"><p><span data-ttu-id="0818c-157">應用程式傳遞與更新不可能隨選。</span><span class="sxs-lookup"><span data-stu-id="0818c-157">Application delivery and update is not possible on-demand.</span></span></p>
<p><span data-ttu-id="0818c-158">應用程式傳遞與更新不是增量式的;它會增加相對於動態傳遞的資源使用量。</span><span class="sxs-lookup"><span data-stu-id="0818c-158">Application delivery and update is not incremental; it increases resource consumption relative to dynamic delivery.</span></span></p></td>
<td align="left"><p><span data-ttu-id="0818c-159">IT 組織通常負責管理應用程式授權、使用者授權和驗證。</span><span class="sxs-lookup"><span data-stu-id="0818c-159">The IT organization is often responsible for managing application licenses, user authorization, and authentication.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="0818c-160">伺服器相關通訊協定與外部元件</span><span class="sxs-lookup"><span data-stu-id="0818c-160">Server-Related Protocols and External Components</span></span>


<span data-ttu-id="0818c-161">下表列出可在應用程式虛擬化伺服器案例中使用的伺服器類型，以及其對應的傳輸通訊協定，以及支援特定伺服器設定所需的外部元件。</span><span class="sxs-lookup"><span data-stu-id="0818c-161">The following table lists the server types that can be used in an Application Virtualization Server-based scenarios, along with their corresponding transmission protocols and the external components needed to support the specific server configuration.</span></span> <span data-ttu-id="0818c-162">此表格也包含每個伺服器類型的報告機制及作用中升級機制。</span><span class="sxs-lookup"><span data-stu-id="0818c-162">The table also includes the reporting mechanism and the active upgrade mechanism for each server type.</span></span> <span data-ttu-id="0818c-163">因為這些案例都使用應用程式虛擬化管理伺服器，所以您可以使用系統內建的內部報告功能。</span><span class="sxs-lookup"><span data-stu-id="0818c-163">Because these scenarios all use the Application Virtualization Management Server, you can use the internal reporting functionality that is built into the system.</span></span> <span data-ttu-id="0818c-164">如果您使用應用程式虛擬化管理或應用程式虛擬化資料流程伺服器來傳送套件給用戶端，則在使用者登入用戶端時，伺服器上的套件會自動升級;如果您使用 IIS 伺服器或檔案將套件傳送到用戶端，則用戶端上的套件必須手動升級。</span><span class="sxs-lookup"><span data-stu-id="0818c-164">If you use an Application Virtualization Management or an Application Virtualization Streaming Server to deliver packages to the client, packages on the server are automatically upgraded when a user logs into the client; if you use IIS servers or a file to deliver the packages to the client, the packages on the client must be upgraded manually.</span></span>

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="0818c-165">伺服器類型</span><span class="sxs-lookup"><span data-stu-id="0818c-165">Server Type</span></span></th>
<th align="left"><span data-ttu-id="0818c-166">通訊協定</span><span class="sxs-lookup"><span data-stu-id="0818c-166">Protocols</span></span></th>
<th align="left"><span data-ttu-id="0818c-167">需要外部元件</span><span class="sxs-lookup"><span data-stu-id="0818c-167">External Components Needed</span></span></th>
<th align="left"><span data-ttu-id="0818c-168">報告</span><span class="sxs-lookup"><span data-stu-id="0818c-168">Reporting</span></span></th>
<th align="left"><span data-ttu-id="0818c-169">活動升級</span><span class="sxs-lookup"><span data-stu-id="0818c-169">Active Upgrade</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0818c-170">應用程式虛擬化管理伺服器</span><span class="sxs-lookup"><span data-stu-id="0818c-170">Application Virtualization Management Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="0818c-171">RTSP</span><span class="sxs-lookup"><span data-stu-id="0818c-171">RTSP</span></span></p>
<p><span data-ttu-id="0818c-172">RTSPS</span><span class="sxs-lookup"><span data-stu-id="0818c-172">RTSPS</span></span></p></td>
<td align="left"><p><span data-ttu-id="0818c-173">使用 HTTPS 時，請使用 IIS 伺服器下載 [.ICO] 和 [OSD] 檔案和防火牆，以保護伺服器不暴露在網際網路上。</span><span class="sxs-lookup"><span data-stu-id="0818c-173">When using HTTPS, use an IIS server to download ICO and OSD files and a firewall to protect the server from exposure to the Internet.</span></span></p></td>
<td align="left"><p><span data-ttu-id="0818c-174">內部</span><span class="sxs-lookup"><span data-stu-id="0818c-174">Internal</span></span></p></td>
<td align="left"><p><span data-ttu-id="0818c-175">支援</span><span class="sxs-lookup"><span data-stu-id="0818c-175">Supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0818c-176">應用程式虛擬化資料流程伺服器</span><span class="sxs-lookup"><span data-stu-id="0818c-176">Application Virtualization Streaming Server</span></span></p></td>
<td align="left"><p><span data-ttu-id="0818c-177">RTSP</span><span class="sxs-lookup"><span data-stu-id="0818c-177">RTSP</span></span></p>
<p><span data-ttu-id="0818c-178">RTSPS</span><span class="sxs-lookup"><span data-stu-id="0818c-178">RTSPS</span></span></p></td>
<td align="left"><p><span data-ttu-id="0818c-179">使用機制來同步處理管理伺服器與流式處理伺服器之間的內容。</span><span class="sxs-lookup"><span data-stu-id="0818c-179">Use a mechanism to synchronize the content between the Management Server and the Streaming Server.</span></span> <span data-ttu-id="0818c-180">使用 HTTPS 時，請使用 IIS 伺服器下載 [.ICO] 和 [OSD] 檔案，並使用防火牆來保護伺服器不暴露在網際網路上。</span><span class="sxs-lookup"><span data-stu-id="0818c-180">When using HTTPS, use an IIS server to download ICO and OSD files and use a firewall to protect the server from exposure to the Internet.</span></span></p></td>
<td align="left"><p><span data-ttu-id="0818c-181">內部</span><span class="sxs-lookup"><span data-stu-id="0818c-181">Internal</span></span></p></td>
<td align="left"><p><span data-ttu-id="0818c-182">支援</span><span class="sxs-lookup"><span data-stu-id="0818c-182">Supported</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="0818c-183">IIS 伺服器</span><span class="sxs-lookup"><span data-stu-id="0818c-183">IIS server</span></span></p></td>
<td align="left"><p><span data-ttu-id="0818c-184">HTTP</span><span class="sxs-lookup"><span data-stu-id="0818c-184">HTTP</span></span></p>
<p><span data-ttu-id="0818c-185">HTTPS</span><span class="sxs-lookup"><span data-stu-id="0818c-185">HTTPS</span></span></p></td>
<td align="left"><p><span data-ttu-id="0818c-186">使用機制來同步處理管理伺服器與流式處理伺服器之間的內容。</span><span class="sxs-lookup"><span data-stu-id="0818c-186">Use a mechanism to synchronize the content between the Management Server and the Streaming Server.</span></span> <span data-ttu-id="0818c-187">使用 HTTP 或 HTTPS 時，請使用 IIS 伺服器下載 [.ICO] 和 [OSD] 檔案和防火牆，以保護伺服器不暴露在網際網路上。</span><span class="sxs-lookup"><span data-stu-id="0818c-187">When using HTTP or HTTPS, use an IIS server to download ICO and OSD files and a firewall to protect the server from exposure to the Internet.</span></span></p></td>
<td align="left"><p><span data-ttu-id="0818c-188">內部</span><span class="sxs-lookup"><span data-stu-id="0818c-188">Internal</span></span></p></td>
<td align="left"><p><span data-ttu-id="0818c-189">不支援</span><span class="sxs-lookup"><span data-stu-id="0818c-189">Not Supported</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="0818c-190">檔案</span><span class="sxs-lookup"><span data-stu-id="0818c-190">File</span></span></p></td>
<td align="left"><p><span data-ttu-id="0818c-191">SMB</span><span class="sxs-lookup"><span data-stu-id="0818c-191">SMB</span></span></p></td>
<td align="left"><p><span data-ttu-id="0818c-192">您需要在管理伺服器與流式處理伺服器之間同步處理內容的方式。</span><span class="sxs-lookup"><span data-stu-id="0818c-192">You need a way to synchronize the content between the Management Server and the Streaming Server.</span></span> <span data-ttu-id="0818c-193">您需要具有檔案共用或流式處理功能的用戶端電腦。</span><span class="sxs-lookup"><span data-stu-id="0818c-193">You need a client computer with file sharing or streaming capability.</span></span></p></td>
<td align="left"><p><span data-ttu-id="0818c-194">內部</span><span class="sxs-lookup"><span data-stu-id="0818c-194">Internal</span></span></p></td>
<td align="left"><p><span data-ttu-id="0818c-195">不支援</span><span class="sxs-lookup"><span data-stu-id="0818c-195">Not Supported</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="0818c-196">相關主題</span><span class="sxs-lookup"><span data-stu-id="0818c-196">Related topics</span></span>


[<span data-ttu-id="0818c-197">以電子軟體發佈為基礎的案例</span><span class="sxs-lookup"><span data-stu-id="0818c-197">Electronic Software Distribution-Based Scenario</span></span>](electronic-software-distribution-based-scenario.md)

[<span data-ttu-id="0818c-198">如何針對以伺服器為基礎的部署設定伺服器</span><span class="sxs-lookup"><span data-stu-id="0818c-198">How to Configure Servers for Server-Based Deployment</span></span>](how-to-configure-servers-for-server-based-deployment.md)

[<span data-ttu-id="0818c-199">如何安裝伺服器和系統元件</span><span class="sxs-lookup"><span data-stu-id="0818c-199">How to Install the Servers and System Components</span></span>](how-to-install-the-servers-and-system-components.md)

 

 





