---
title: 設定憑證以支援 APP-V Web 管理服務
description: 設定憑證以支援 APP-V Web 管理服務
author: dansimp
ms.assetid: b7960161-2c19-4cbf-a98a-d4b06f547dce
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 23839e6fad79c1f10eb2416941396ad3c6f04d26
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809026"
---
# <span data-ttu-id="26db3-103">設定憑證以支援 APP-V Web 管理服務</span><span class="sxs-lookup"><span data-stu-id="26db3-103">Configuring Certificates to Support the App-V Web Management Service</span></span>


<span data-ttu-id="26db3-104">App-v Web 管理服務必須設定為支援以 SSL 為基礎的連線，以協助保護通訊。</span><span class="sxs-lookup"><span data-stu-id="26db3-104">The App-V Web Management Service must be configured to support SSL-based connections to help secure the communication.</span></span> <span data-ttu-id="26db3-105">這個程式要求安裝管理服務的 Web 服務器或電腦已將憑證頒發給服務或電腦。</span><span class="sxs-lookup"><span data-stu-id="26db3-105">This process requires that the Web server or computer on which the Management Service is installed has a certificate issued to the service or computer.</span></span>

<span data-ttu-id="26db3-106">下列案例說明如何取得憑證以達到此目的：</span><span class="sxs-lookup"><span data-stu-id="26db3-106">The following scenarios illustrate how to obtain a certificate for this purpose:</span></span>

1.  <span data-ttu-id="26db3-107">公司基礎結構已經有一個將憑證自動頒發給電腦的公開金鑰基礎結構（PKI）。</span><span class="sxs-lookup"><span data-stu-id="26db3-107">The company infrastructure already has a public key infrastructure (PKI) in place that automatically issues certificates to computers.</span></span>

2.  <span data-ttu-id="26db3-108">公司基礎結構已經有一個 PKI，雖然它不會自動將憑證頒發給電腦。</span><span class="sxs-lookup"><span data-stu-id="26db3-108">The company infrastructure already has a PKI in place, although it does not automatically issue certificates to computers.</span></span>

3.  <span data-ttu-id="26db3-109">公司基礎結構沒有正確的 PKI。</span><span class="sxs-lookup"><span data-stu-id="26db3-109">The company infrastructure has no PKI in place.</span></span>

<span data-ttu-id="26db3-110">在上述每個案例中，取得憑證的方法會有所不同，但最終結果是一樣的。</span><span class="sxs-lookup"><span data-stu-id="26db3-110">In each of the preceding scenarios, the method for obtaining a certificate is different, but the end result is the same.</span></span> <span data-ttu-id="26db3-111">系統管理員必須將憑證指派給 IIS 預設的網站，並將 App-V Web 管理服務設定為需要安全通訊。</span><span class="sxs-lookup"><span data-stu-id="26db3-111">The administrator must assign a certificate to the IIS Default Web Site and configure the App-V Web Management Service to require secure communications.</span></span>

<span data-ttu-id="26db3-112">**重要** 憑證名必須符合伺服器的名稱。</span><span class="sxs-lookup"><span data-stu-id="26db3-112">**Important** The name of the certificate must match the name of the server.</span></span> <span data-ttu-id="26db3-113">最佳做法是針對憑證的通用名稱使用完整的功能變數名稱（Fqdn）。</span><span class="sxs-lookup"><span data-stu-id="26db3-113">It is a best practice to use fully qualified domain names (FQDNs) for the common name of the certificate.</span></span>

 

<span data-ttu-id="26db3-114">App-v 可以使用 IIS 伺服器來支援不同的基礎結構配置。</span><span class="sxs-lookup"><span data-stu-id="26db3-114">App-V can use IIS servers to support different infrastructure configurations.</span></span> <span data-ttu-id="26db3-115">如需有關設定 IIS 伺服器以支援 HTTPS 的詳細資訊，請參閱 <https://go.microsoft.com/fwlink/?LinkId=151972> 。</span><span class="sxs-lookup"><span data-stu-id="26db3-115">For more information about configuring IIS servers to support HTTPS, see <https://go.microsoft.com/fwlink/?LinkId=151972>.</span></span>

## <span data-ttu-id="26db3-116">相關主題</span><span class="sxs-lookup"><span data-stu-id="26db3-116">Related topics</span></span>


[<span data-ttu-id="26db3-117">如何安裝及設定 APP-V 管理主控台以用於更安全的環境</span><span class="sxs-lookup"><span data-stu-id="26db3-117">How to Install and Configure the App-V Management Console for a More Secure Environment</span></span>](how-to-install-and-configure-the-app-v-management-console-for-a-more-secure-environment.md)

 

 





