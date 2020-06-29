---
title: 安全性與保護概觀
description: 安全性與保護概觀
author: dansimp
ms.assetid: a43e1c53-7936-4d48-a110-0be26c8e9d97
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b08b7dcb3defa8a01a4fd8a3e7234b5ac2956c4e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800863"
---
# <span data-ttu-id="eed03-103">安全性與保護概觀</span><span class="sxs-lookup"><span data-stu-id="eed03-103">Security and Protection Overview</span></span>


<span data-ttu-id="eed03-104">Microsoft Application Virtualization 4.5 提供下列增強的安全性功能，可協助您規劃及執行更安全的部署策略：</span><span class="sxs-lookup"><span data-stu-id="eed03-104">Microsoft Application Virtualization4.5 provides the following enhanced security features to help you plan and implement a more secure deployment strategy:</span></span>

-   <span data-ttu-id="eed03-105">應用程式虛擬化現在支援使用 x.509 V3 憑證的傳輸層安全性（TLS）。</span><span class="sxs-lookup"><span data-stu-id="eed03-105">Application Virtualization now supports Transport Layer Security (TLS) using X.509 V3 certificates.</span></span> <span data-ttu-id="eed03-106">如果您已將伺服器憑證預配至規劃的應用程式虛擬化管理或流式處理伺服器，則安裝將預設為使用 RTSPS 通訊協定，透過埠322進行保護。</span><span class="sxs-lookup"><span data-stu-id="eed03-106">Provided that a server certificate has been provisioned to the planned Application Virtualization Management or Streaming Server, the installation will default to secure, using the RTSPS protocol over port 322.</span></span> <span data-ttu-id="eed03-107">使用 RTSPS 可確保應用程式虛擬化伺服器與應用程式虛擬化用戶端之間的通訊已簽署並加密。</span><span class="sxs-lookup"><span data-stu-id="eed03-107">Using RTSPS ensures that communication between the Application Virtualization Servers and the Application Virtualization Clients is signed and encrypted.</span></span> <span data-ttu-id="eed03-108">如果未在應用程式虛擬化伺服器安裝期間將憑證指派給伺服器，通訊將會設定為經由埠554的 RTSP。</span><span class="sxs-lookup"><span data-stu-id="eed03-108">If no certificate is assigned to the server during the Application Virtualization Server installation, the communication will be set to RTSP over port 554.</span></span>

    **<span data-ttu-id="eed03-109">安全性注意事項：</span><span class="sxs-lookup"><span data-stu-id="eed03-109">Security Note:</span></span>**

    <span data-ttu-id="eed03-110">若要協助提供伺服器的安全設定，您必須先確定 RTSP 埠已停用，即使您已將所有套件設定為使用 RTSPS。</span><span class="sxs-lookup"><span data-stu-id="eed03-110">To help provide a secure setup of the server, you must make sure that RTSP ports are disabled even if you have all packages configured to use RTSPS.</span></span>

    <span data-ttu-id="eed03-111">如果您在安裝伺服器之後在伺服器中新增安全性憑證，伺服器可能無法偵測到憑證。</span><span class="sxs-lookup"><span data-stu-id="eed03-111">If you add security certificates to the server after installing the server, the server might not detect the certificates.</span></span> <span data-ttu-id="eed03-112">若要協助確保安全性憑證偵測，請在新增憑證後重新開機伺服器。</span><span class="sxs-lookup"><span data-stu-id="eed03-112">To help ensure security certificate detection, restart the server after adding the certificates.</span></span>

-   <span data-ttu-id="eed03-113">用戶端必須設定為使用與伺服器相同的通訊協定和埠，否則就不能與伺服器通訊。</span><span class="sxs-lookup"><span data-stu-id="eed03-113">The client must be configured to use the same protocol and port as the server, or it will not be able to communicate with the server.</span></span> <span data-ttu-id="eed03-114">用戶端也必須信任憑證的 issuer，並隨附在其受信任的根存放區中的幾個主要提供者。</span><span class="sxs-lookup"><span data-stu-id="eed03-114">The client must also trust the issuer of the certificate and ships with several of the primary providers in its Trusted Root Store.</span></span> <span data-ttu-id="eed03-115">您可以使用自我簽署的憑證，但是您需要更新用戶端。</span><span class="sxs-lookup"><span data-stu-id="eed03-115">You can use self-signed certificates, but you will need to update the clients.</span></span>

-   <span data-ttu-id="eed03-116">將 IIS 伺服器設定為使用 HTTPS 通訊協定進行流式處理時，您必須在 IIS 伺服器上設定安全通訊端層（SSL），並為伺服器提供憑證。</span><span class="sxs-lookup"><span data-stu-id="eed03-116">When configuring IIS servers to use the HTTPS protocol for streaming, you will need to set up Secure Sockets Layer (SSL) on the IIS server and provision the certificate for the server.</span></span> <span data-ttu-id="eed03-117">用戶端也必須設定為信任頒發伺服器憑證的根憑證授權單位。</span><span class="sxs-lookup"><span data-stu-id="eed03-117">The clients will also need to be configured to trust the root certification authority that issued the server certificate.</span></span>

-   <span data-ttu-id="eed03-118">已將 Kerberos 驗證新增至 Microsoft Application Virtualization 作為預設驗證機制。</span><span class="sxs-lookup"><span data-stu-id="eed03-118">Kerberos authentication has been added to Microsoft Application Virtualization as the default authentication mechanism.</span></span> <span data-ttu-id="eed03-119">早期版本依賴于 NTLM V2 進行驗證。</span><span class="sxs-lookup"><span data-stu-id="eed03-119">Earlier versions relied upon NTLM V2 for authentication.</span></span> <span data-ttu-id="eed03-120">使用 Kerberos 驗證能增強用戶端與應用程式虛擬化伺服器之間通訊的安全性。</span><span class="sxs-lookup"><span data-stu-id="eed03-120">Using Kerberos Authentication strengthens the security of the communication between the client and the Application Virtualization server.</span></span> <span data-ttu-id="eed03-121">從用戶端啟動連線時，應用程式虛擬化伺服器會使用金鑰發佈中心（KDC）來驗證會話票證。</span><span class="sxs-lookup"><span data-stu-id="eed03-121">When a connection has been initiated from the client, the Application Virtualization Server verifies the session ticket with the Key Distribution Center (KDC).</span></span>

-   <span data-ttu-id="eed03-122">由於支援使用伺服器憑證以及使用 RTSPS 或 HTTPS 通訊協定，您現在可以支援公司網路以外的用戶端。</span><span class="sxs-lookup"><span data-stu-id="eed03-122">Because of the support for using server certificates and using the RTSPS or HTTPS protocols, you can now support clients outside of the corporate network.</span></span> <span data-ttu-id="eed03-123">這可協助您在啟動應用程式虛擬化設定的應用程式之前，避免行動使用者設定安全連線至公司網路（VPN、RAS 等）的需求。</span><span class="sxs-lookup"><span data-stu-id="eed03-123">This can help eliminate the need for mobile users to set up a secure connection to the corporate network (VPN, RAS, and so on) prior to launching Application Virtualization provisioned applications.</span></span>

<span data-ttu-id="eed03-124">考慮的其他重要安全考慮事項包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="eed03-124">Other important security considerations to consider include the following:</span></span>

-   <span data-ttu-id="eed03-125">永遠保持伺服器完全更新並受到保護。</span><span class="sxs-lookup"><span data-stu-id="eed03-125">Always keep servers fully updated and protected.</span></span>

-   <span data-ttu-id="eed03-126">若要新增憑證以啟用更安全的與應用程式虛擬化管理伺服器通訊，必須符合下列準則：</span><span class="sxs-lookup"><span data-stu-id="eed03-126">To add a certificate to enable more secure communications to the Application Virtualization Management Server, the following criteria must be met:</span></span>

    -   <span data-ttu-id="eed03-127">要新增憑證的使用者，必須是憑證存放所在伺服器的系統管理員。</span><span class="sxs-lookup"><span data-stu-id="eed03-127">The user who will be adding the certificate must be an administrator on the server where the certificate store is located.</span></span>

    -   <span data-ttu-id="eed03-128">必須啟動伺服器服務。</span><span class="sxs-lookup"><span data-stu-id="eed03-128">The server service must be started.</span></span>

    -   <span data-ttu-id="eed03-129">管理伺服器上的埠139必須開啟至 Web 服務 server'sIP。</span><span class="sxs-lookup"><span data-stu-id="eed03-129">Port 139 on the Management Server must be open to the Web Service server’sIP.</span></span>

-   <span data-ttu-id="eed03-130">使用存取控制清單（Acl），以確保應用程式套件和所有套件檔案受到保護且無法被篡改。</span><span class="sxs-lookup"><span data-stu-id="eed03-130">Use access control lists (ACLs) to ensure that the application packages and all package files are protected and cannot be tampered.</span></span> <span data-ttu-id="eed03-131">Acl 會限制對儲存套件之位置或資料夾的存取權，只允許存取特定帳戶。</span><span class="sxs-lookup"><span data-stu-id="eed03-131">ACLs restrict access to the location or folder where you store the packages, allowing access only to certain accounts.</span></span>

-   <span data-ttu-id="eed03-132">確定應用程式虛擬化管理伺服器與資料庫之間的通道是安全的，例如，使用 IPsec。</span><span class="sxs-lookup"><span data-stu-id="eed03-132">Make sure that the channel between the Application Virtualization Management Server and the database is secured—for example, by using IPsec.</span></span>

-   <span data-ttu-id="eed03-133">如果套件儲存在 SAN 或 NAS 上，請確定中央存放裝置與應用程式虛擬化伺服器之間的連線已受到保護。</span><span class="sxs-lookup"><span data-stu-id="eed03-133">If packages are stored on a SAN or NAS, ensure the connection between the central storage device and the Application Virtualization Servers is protected.</span></span>

-   <span data-ttu-id="eed03-134">用戶端的所有通訊通道都應該受到保護，包括與發佈伺服器的連線、應用程式虛擬化伺服器，以及 OSD 與 .ICO 檔案的路徑，方法是使用 HTTPS 或 IPsec 等通訊協定。</span><span class="sxs-lookup"><span data-stu-id="eed03-134">All communication channels to the client should be protected—including connections to the publishing server, the Application Virtualization Server, and the path to the OSD and ICO files—by using a protocol such as HTTPS or IPsec.</span></span> 

-   <span data-ttu-id="eed03-135">應該設定用戶端許可權，以協助確保使用者無法篡改套件。</span><span class="sxs-lookup"><span data-stu-id="eed03-135">Client permissions should be configured to help ensure that packages cannot be tampered with by users.</span></span> <span data-ttu-id="eed03-136">您不會在與多個使用者共用的系統（例如遠端桌面工作階段主機（RDSession 主機）伺服器）上，給予使用者新增或更新套件的許可權，特別重要。</span><span class="sxs-lookup"><span data-stu-id="eed03-136">It is especially important that you do not grant users permission to add or update packages on systems, such as Remote Desktop Session Host (RDSession Host) servers, that are shared with multiple users.</span></span>

-   <span data-ttu-id="eed03-137">若要讓伺服器管理主控台能正常運作，必須跨網域或林環境允許 Kerberos 驗證。</span><span class="sxs-lookup"><span data-stu-id="eed03-137">Kerberos authentication must be permitted across domain or forest environments for the Server Management Console to work correctly.</span></span>

-   <span data-ttu-id="eed03-138">這個版本的軟體不支援在相同的電腦上託管 Kerberos 式 RTSP 伺服器和僅限 Microsoft NTLM 的 IIS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="eed03-138">This release of the software does not support hosting a Kerberos-based RTSP server and a Microsoft NTLM-only-based IIS server on the same computer.</span></span> <span data-ttu-id="eed03-139">若要在同一部電腦上託管 RTSP 伺服器和 IIS 伺服器，請從 IIS 伺服器移除 SPN，然後使用 NTLM 驗證。</span><span class="sxs-lookup"><span data-stu-id="eed03-139">To host an RTSP server and an IIS server on the same computer, remove the SPN from the IIS server and use NTLM authentication.</span></span>

## <span data-ttu-id="eed03-140">相關主題</span><span class="sxs-lookup"><span data-stu-id="eed03-140">Related topics</span></span>


[<span data-ttu-id="eed03-141">規劃 Application Virtualization 系統部署</span><span class="sxs-lookup"><span data-stu-id="eed03-141">Planning for Application Virtualization System Deployment</span></span>](planning-for-application-virtualization-system-deployment.md)

 

 





