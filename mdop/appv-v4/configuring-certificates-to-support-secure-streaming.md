---
title: 支援憑證以支援安全串流
description: 支援憑證以支援安全串流
author: dansimp
ms.assetid: 88dc76d8-7745-4729-92a1-af089c921244
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9376634a1b9843f46dba4cd452e672cc9e535226
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809027"
---
# <span data-ttu-id="376ab-103">支援憑證以支援安全串流</span><span class="sxs-lookup"><span data-stu-id="376ab-103">Configuring Certificates to Support Secure Streaming</span></span>


<span data-ttu-id="376ab-104">根據預設，App-v 服務會在網路服務帳戶下執行。</span><span class="sxs-lookup"><span data-stu-id="376ab-104">By default, the App-V service runs under the Network Service account.</span></span> <span data-ttu-id="376ab-105">不過，您可以在 Active Directory 網域服務中建立服務帳戶，並以 Active Directory 網域帳戶取代網路服務帳戶。</span><span class="sxs-lookup"><span data-stu-id="376ab-105">However, you can create a service account in Active Directory Domain Services and replace the Network Service account with the Active Directory Domain account.</span></span>

<span data-ttu-id="376ab-106">服務執行所用的安全性內容對於設定增強的安全通訊非常重要。</span><span class="sxs-lookup"><span data-stu-id="376ab-106">The security context under which the service runs is important for configuring enhanced secure communications.</span></span> <span data-ttu-id="376ab-107">這個安全性內容必須具備證書私密金鑰的讀取權限。</span><span class="sxs-lookup"><span data-stu-id="376ab-107">This security context must have read permissions for the certificate private key.</span></span> <span data-ttu-id="376ab-108">當針對 App-v server 產生 #10*憑證簽署要求*（CSR）時，就會呼叫 Windows*加密服務提供者*，並產生一個私用機碼。</span><span class="sxs-lookup"><span data-stu-id="376ab-108">When a PKCS\#10 *Certificate Signing Request* (CSR) is generated for the App-V server, the Windows *Cryptographic Service Provider* is called and a private key is generated.</span></span> <span data-ttu-id="376ab-109">您只會以系統和管理員帳戶所提供的許可權來保護私人金鑰。</span><span class="sxs-lookup"><span data-stu-id="376ab-109">The private key is secured with permissions given to the System and Administrator accounts only.</span></span>

<span data-ttu-id="376ab-110">您必須修改私人金鑰上的存取控制清單（Acl），讓 App-v 管理或流式伺服器存取成功的 TLS 安全通訊所需的私密金鑰。</span><span class="sxs-lookup"><span data-stu-id="376ab-110">You must modify the access control lists (ACLs) on the private key to let the App-V Management or Streaming Server access the private key required for successful TLS secured communication.</span></span>

## <span data-ttu-id="376ab-111">取得並安裝憑證</span><span class="sxs-lookup"><span data-stu-id="376ab-111">Obtaining and Installing a Certificate</span></span>


<span data-ttu-id="376ab-112">取得並安裝 App-v 的憑證的案例如下所示：</span><span class="sxs-lookup"><span data-stu-id="376ab-112">The scenarios for obtaining and installing a certificate for App-V are as follows:</span></span>

-   <span data-ttu-id="376ab-113">內部公用金鑰基礎結構（PKI）。</span><span class="sxs-lookup"><span data-stu-id="376ab-113">Internal public key infrastructure (PKI).</span></span>

-   <span data-ttu-id="376ab-114">協力廠商憑證發行憑證授權單位（CA）。</span><span class="sxs-lookup"><span data-stu-id="376ab-114">Third-party certificate issuing certification authority (CA).</span></span>

    <span data-ttu-id="376ab-115">**記事** 如果您需要從協力廠商 CA 取得憑證，請遵循該 CA 網站上提供的檔。</span><span class="sxs-lookup"><span data-stu-id="376ab-115">**Note** If you need to obtain a certificate from a third-party CA, follow the documentation available on that CA’s Web site.</span></span>

     

<span data-ttu-id="376ab-116">如果已部署 PKI 基礎結構，請諮詢 PKI 管理員，取得符合本主題所述需求的憑證。</span><span class="sxs-lookup"><span data-stu-id="376ab-116">If a PKI infrastructure has been deployed, consult with the PKI administrators to acquire a certificate that complies with the requirements described in this topic.</span></span> <span data-ttu-id="376ab-117">如果沒有提供 PKI 基礎結構，請使用協力廠商 CA 來取得有效的憑證。</span><span class="sxs-lookup"><span data-stu-id="376ab-117">If a PKI infrastructure is not available, use a third-party CA to obtain a valid certificate.</span></span>

<span data-ttu-id="376ab-118">如需取得和安裝憑證的逐步指導方針，請參閱 <https://go.microsoft.com/fwlink/?LinkId=151969> 。</span><span class="sxs-lookup"><span data-stu-id="376ab-118">For step-by-step guidance for obtaining and installing a certificate, see <https://go.microsoft.com/fwlink/?LinkId=151969>.</span></span>

## <span data-ttu-id="376ab-119">相關主題</span><span class="sxs-lookup"><span data-stu-id="376ab-119">Related topics</span></span>


<span data-ttu-id="376ab-120">將憑證設定為支援安全資料流程[如何修改私人金鑰許可權以支援管理伺服器或流式處理伺服器](how-to-modify-private-key-permissions-to-support-management-server-or-streaming-server.md)</span><span class="sxs-lookup"><span data-stu-id="376ab-120">Configuring Certificates to Support Secure Streaming [How to Modify Private Key Permissions to Support Management Server or Streaming Server](how-to-modify-private-key-permissions-to-support-management-server-or-streaming-server.md)</span></span>

 

 





