---
title: 設定 IIS 以用於安全串流
description: 設定 IIS 以用於安全串流
author: dansimp
ms.assetid: 9a80a703-4642-4bec-b7af-dc7cb6b76925
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 724fd247d98c265421cea13f4b91c97049a2b4d4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809021"
---
# <span data-ttu-id="94544-103">設定 IIS 以用於安全串流</span><span class="sxs-lookup"><span data-stu-id="94544-103">Configuring IIS for Secure Streaming</span></span>


<span data-ttu-id="94544-104">在發行 Microsoft Application Virtualization （App-v）版本4.5 時，您可以使用 HTTP 和 HTTPS 做為應用程式套件的通訊協定，以傳送到 App-v 用戶端。</span><span class="sxs-lookup"><span data-stu-id="94544-104">With the release of Microsoft Application Virtualization (App-V) version 4.5, you can use HTTP and HTTPS as protocols for streaming application packages to the App-V clients.</span></span> <span data-ttu-id="94544-105">這個選項可讓組織利用 IIS 通常提供的其他可伸縮性。</span><span class="sxs-lookup"><span data-stu-id="94544-105">This option enables organizations to leverage the additional scalability that IIS typically offers.</span></span> <span data-ttu-id="94544-106">當您使用 IIS 作為流式處理伺服器時，您可以使用 HTTPS （而不是 HTTP），協助保護用戶端與伺服器之間的通訊安全。</span><span class="sxs-lookup"><span data-stu-id="94544-106">When you use IIS as a streaming server, you can help secure the communications between the client and server by using HTTPS instead of HTTP.</span></span>

<span data-ttu-id="94544-107">**記事** 如果您想要從檔案伺服器對流進行應用程式，您應該加強與應用程式套件通訊的安全性。</span><span class="sxs-lookup"><span data-stu-id="94544-107">**Note** If you want to stream applications from a file server, you should enhance the security of the communications to the application packages.</span></span> <span data-ttu-id="94544-108">這可以使用 IPsec 來實現。</span><span class="sxs-lookup"><span data-stu-id="94544-108">This can be achieved using IPsec.</span></span> <span data-ttu-id="94544-109">如需詳細資訊，請參閱 TechNet 文件庫中的下列主題：</span><span class="sxs-lookup"><span data-stu-id="94544-109">For more information see the following topics in the TechNet Library:</span></span>

-   <span data-ttu-id="94544-110">針對 Windows Server2003，</span><span class="sxs-lookup"><span data-stu-id="94544-110">For Windows Server2003,</span></span> <https://go.microsoft.com/fwlink/?LinkId=133226>

-   <span data-ttu-id="94544-111">針對 Windows Server 2008，</span><span class="sxs-lookup"><span data-stu-id="94544-111">For Windows Server 2008,</span></span> <https://go.microsoft.com/fwlink/?LinkId=133227>

 

## <span data-ttu-id="94544-112">MIME 類型</span><span class="sxs-lookup"><span data-stu-id="94544-112">MIME Types</span></span>


<span data-ttu-id="94544-113">當您使用 IIS 以 HTTP 或 HTTPS 流式處理虛擬應用程式時，若要支援 App-v，必須在 IIS 伺服器中新增下列 MIME 類型：</span><span class="sxs-lookup"><span data-stu-id="94544-113">When you use IIS to stream virtual applications with HTTP or HTTPS, to support App-V, the following MIME types must be added to the IIS server:</span></span>

-   <span data-ttu-id="94544-114">.OSD = TXT</span><span class="sxs-lookup"><span data-stu-id="94544-114">.OSD=TXT</span></span>

-   <span data-ttu-id="94544-115">.SFT = Binary</span><span class="sxs-lookup"><span data-stu-id="94544-115">.SFT=Binary</span></span>

<span data-ttu-id="94544-116">使用下列 KB 文章做為新增 MIME 類型的指導方針：</span><span class="sxs-lookup"><span data-stu-id="94544-116">Use the following KB articles as guidance for adding MIME types:</span></span>

<span data-ttu-id="94544-117">IIS 6.0：</span><span class="sxs-lookup"><span data-stu-id="94544-117">IIS 6.0:</span></span> <https://go.microsoft.com/fwlink/?LinkId=151973>

<span data-ttu-id="94544-118">IIS 7.0：</span><span class="sxs-lookup"><span data-stu-id="94544-118">IIS 7.0:</span></span> <https://go.microsoft.com/fwlink/?LinkId=151977>

## <span data-ttu-id="94544-119">Kerberos 驗證</span><span class="sxs-lookup"><span data-stu-id="94544-119">Kerberos Authentication</span></span>


<span data-ttu-id="94544-120">當您使用 HTTP 或 HTTPS 與 Kerberos 驗證來資料流 .ICO、OSD 或 SFT 檔案時，您將會增強環境的安全性。</span><span class="sxs-lookup"><span data-stu-id="94544-120">When you use HTTP or HTTPS and Kerberos authentication to stream ICO, OSD, or SFT files, you are enhancing the security of your environment.</span></span> <span data-ttu-id="94544-121">不過，若要讓 IIS 支援 Kerberos 驗證，您必須設定適當的服務主體名稱（SPN）。</span><span class="sxs-lookup"><span data-stu-id="94544-121">However, for IIS to support Kerberos authentication, you must configure a proper Service Principal Name (SPN).</span></span> <span data-ttu-id="94544-122">`setspn.exe`從安裝 CD 的支援工具中，Windows Server2003 提供此工具，而且它是內建的 Windows Server2008。</span><span class="sxs-lookup"><span data-stu-id="94544-122">The `setspn.exe` tool is available for Windows Server2003 from the Support Tools on the installation CD and is built-in to Windows Server2008.</span></span>

<span data-ttu-id="94544-123">若要建立 SPN，請在以 `setspn.exe` 網域管理員成員身分登入命令提示字元的情況下，執行該 SPN （例如，） `setspn.exe –A HTTP/FQDN of Server ServerName` 。</span><span class="sxs-lookup"><span data-stu-id="94544-123">To create an SPN, run `setspn.exe` from a command prompt while logged in as a member of Domain Administrators—for example, `setspn.exe –A HTTP/FQDN of Server ServerName`.</span></span>

## <span data-ttu-id="94544-124">相關主題</span><span class="sxs-lookup"><span data-stu-id="94544-124">Related topics</span></span>


[<span data-ttu-id="94544-125">設定管理或串流伺服器以供安裝後續安全通訊</span><span class="sxs-lookup"><span data-stu-id="94544-125">Configuring Management or Streaming Server for Secure Communications Post-Installation</span></span>](configuring-management-or-streaming-server-for-secure-communications-post-installation.md)

 

 





