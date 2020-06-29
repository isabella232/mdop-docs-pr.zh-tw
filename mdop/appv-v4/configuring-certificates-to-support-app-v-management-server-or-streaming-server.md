---
title: 設定憑證以支援 APP-V Management Server 或 Streaming Server
description: 設定憑證以支援 APP-V Management Server 或 Streaming Server
author: dansimp
ms.assetid: 2f24e550-585e-4b7e-b486-22a3f181f543
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e537244b24d7303af550b3ced8286ba2680009e7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809032"
---
# <span data-ttu-id="4a373-103">設定憑證以支援 APP-V Management Server 或 Streaming Server</span><span class="sxs-lookup"><span data-stu-id="4a373-103">Configuring Certificates to Support App-V Management Server or Streaming Server</span></span>


<span data-ttu-id="4a373-104">完成證書置備程式並變更私人金鑰許可權以支援 App-v 安裝之後，您就可以啟動管理伺服器或流式處理伺服器的設定。</span><span class="sxs-lookup"><span data-stu-id="4a373-104">After you complete the certificate provisioning process and change the private key permissions to support the App-V installation, you can launch the setup of the Management Server or the Streaming Server.</span></span> <span data-ttu-id="4a373-105">在安裝期間，如果在執行安裝程式前已提供憑證，嚮導會在連線**安全模式**畫面中顯示憑證，而且預設會選取 [**使用增強型安全性**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="4a373-105">During setup, if a certificate is provisioned before running the setup program, the wizard displays the certificate in the **Connection Security Mode** screen and, by default, the **Use enhanced security** check box is selected.</span></span>

<span data-ttu-id="4a373-106">**記事** 選取針對此伺服器預配有一個以上的憑證的情況下為 App-v 設定的憑證。</span><span class="sxs-lookup"><span data-stu-id="4a373-106">**Note** Select the certificate that was configured for App-V if there is more than one certificate provisioned for this server.</span></span>

 

<span data-ttu-id="4a373-107">**重要** 從版本4.2 升級到版本4.5 時，安裝程式會提供使用 [**增強的安全性**] 的選項。不過，選取此選項並不會停用 RTSP 的資料流程。</span><span class="sxs-lookup"><span data-stu-id="4a373-107">**Important** When upgrading from version 4.2 to version 4.5, the setup has an option for **Use enhanced security**; however, selecting this option will not disable streaming over RTSP.</span></span> <span data-ttu-id="4a373-108">安裝之後，您必須使用管理主控台停用 RTSP。</span><span class="sxs-lookup"><span data-stu-id="4a373-108">You must use the Management Console to disable RTSP after installation.</span></span>

 

<span data-ttu-id="4a373-109">選取服務將用於用戶端通訊的 TCP 埠。</span><span class="sxs-lookup"><span data-stu-id="4a373-109">Select the TCP port that the service will use for client communications.</span></span> <span data-ttu-id="4a373-110">預設埠是 TCP 322;不過，您可以將埠變更為您環境的自訂埠。</span><span class="sxs-lookup"><span data-stu-id="4a373-110">The default port is TCP 322; however, you can change the port to a custom port for your environment.</span></span>

<span data-ttu-id="4a373-111">嚮導的其餘步驟與您在不使用 [**增強的安全性**] 功能的情況下部署 App V 管理或流式伺服器一樣。</span><span class="sxs-lookup"><span data-stu-id="4a373-111">The remaining steps of the wizard are the same as if you were deploying an App-V Management or Streaming Server without using the **Enhanced security** feature.</span></span>

## <span data-ttu-id="4a373-112">為 NLB 環境設定憑證</span><span class="sxs-lookup"><span data-stu-id="4a373-112">Configuring Certificates for NLB Environments</span></span>


<span data-ttu-id="4a373-113">為了支援大型企業，通常會將管理伺服器放在網路負載平衡（NLB）群集中，以支援大量連線。</span><span class="sxs-lookup"><span data-stu-id="4a373-113">To support large enterprises, often the Management Server is placed into a Network Load Balancing (NLB) cluster to support the large number of connections.</span></span> <span data-ttu-id="4a373-114">這需要至少兩個顯示為單一管理伺服器的管理伺服器。</span><span class="sxs-lookup"><span data-stu-id="4a373-114">This requires at least two Management Servers that appear to be a single Management Server.</span></span> <span data-ttu-id="4a373-115">當您的環境使用具有多個管理伺服器的 NLB 群集時，您必須具備用於 NLB 群集的憑證的高級配置。</span><span class="sxs-lookup"><span data-stu-id="4a373-115">When your environment uses an NLB cluster with several Management Servers, you need an advanced configuration of the certificate used for the NLB cluster.</span></span>

<span data-ttu-id="4a373-116">App-v 憑證會提交至在執行 Windows Server2003 的電腦上設定的認證機構（CA）。</span><span class="sxs-lookup"><span data-stu-id="4a373-116">The App-V certificate is submitted to a certification authority (CA) that is configured on a computer running Windows Server2003.</span></span> <span data-ttu-id="4a373-117">SAN 可讓您使用與實際電腦名稱稱不同的網域名稱系統（DNS）名稱，連線到特定的管理伺服器 NLB 群集主機名稱，因為可能會有多達32台組成 NLB 群集的伺服器。</span><span class="sxs-lookup"><span data-stu-id="4a373-117">The SAN lets you connect to a specific Management Server NLB cluster host name by using a Domain Name System (DNS) name that might differ from the actual computer names, because there can be up to 32 servers that comprise the NLB cluster.</span></span>

<span data-ttu-id="4a373-118">這個設定只有在使用 NLB 群集時才有必要。</span><span class="sxs-lookup"><span data-stu-id="4a373-118">This configuration is necessary only when using an NLB cluster.</span></span> <span data-ttu-id="4a373-119">當用戶端連線到伺服器時，它會使用 NLB 群集的完整功能變數名稱（FQDN），而不是個別伺服器的 FQDN 來連線。</span><span class="sxs-lookup"><span data-stu-id="4a373-119">When the client connects to the server, it will connect using the fully qualified domain name (FQDN) of the NLB cluster and not the FQDN of an individual server.</span></span> <span data-ttu-id="4a373-120">如果您沒有使用群集中伺服器節點的 FQDN 新增 SAN 屬性，所有用戶端連線都會遭到拒絕，因為證書的公用名不符合伺服器名稱。</span><span class="sxs-lookup"><span data-stu-id="4a373-120">If you do not add the SAN property with the FQDN of the server nodes in the cluster, all client connections are refused because the common name of the certificate won’t match the server name.</span></span>

<span data-ttu-id="4a373-121">如需使用 SAN 屬性設定憑證的詳細資訊，請參閱 <https://go.microsoft.com/fwlink/?LinkId=133228> 。</span><span class="sxs-lookup"><span data-stu-id="4a373-121">For more detailed information about configuring certificates with the SAN attribute, see <https://go.microsoft.com/fwlink/?LinkId=133228>.</span></span>

## <span data-ttu-id="4a373-122">相關主題</span><span class="sxs-lookup"><span data-stu-id="4a373-122">Related topics</span></span>


[<span data-ttu-id="4a373-123">支援憑證以支援安全串流</span><span class="sxs-lookup"><span data-stu-id="4a373-123">Configuring Certificates to Support Secure Streaming</span></span>](configuring-certificates-to-support-secure-streaming.md)

[<span data-ttu-id="4a373-124">如何修改私密金鑰權限以支援管理伺服器或串流伺服器</span><span class="sxs-lookup"><span data-stu-id="4a373-124">How to Modify Private Key Permissions to Support Management Server or Streaming Server</span></span>](how-to-modify-private-key-permissions-to-support-management-server-or-streaming-server.md)

 

 





