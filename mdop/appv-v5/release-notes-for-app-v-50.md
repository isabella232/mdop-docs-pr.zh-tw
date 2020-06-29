---
title: App-V 5.0 的版本資訊
description: App-V 5.0 的版本資訊
author: dansimp
ms.assetid: 68a6a5a1-4b3c-4c09-b00c-9ca4237695d5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e49f6072d738b45afe25de24f2ee9a2d09d64a2e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800314"
---
# <span data-ttu-id="9c9bc-103">App-V 5.0 的版本資訊</span><span class="sxs-lookup"><span data-stu-id="9c9bc-103">Release Notes for App-V 5.0</span></span>


**<span data-ttu-id="9c9bc-104">若要在這些版本筆記中搜尋特定問題，請按 CTRL + F。</span><span class="sxs-lookup"><span data-stu-id="9c9bc-104">To search for a specific issue in these release notes, press CTRL+F.</span></span>**

<span data-ttu-id="9c9bc-105">安裝 App-v 5.0 之前，請先閱讀這些版本資訊。</span><span class="sxs-lookup"><span data-stu-id="9c9bc-105">Read these release notes thoroughly before you install App-V 5.0.</span></span>

<span data-ttu-id="9c9bc-106">這些版本資訊包含成功安裝 App-v 5.0 所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="9c9bc-106">These release notes contain information that is required to successfully install App-V 5.0.</span></span> <span data-ttu-id="9c9bc-107">版本資訊中也包含產品檔中不提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="9c9bc-107">The release notes also contain information that is not available in the product documentation.</span></span> <span data-ttu-id="9c9bc-108">如果這些版本資訊與其他 App-v 5.0 檔有差異，最新的變更應該視為權威性。</span><span class="sxs-lookup"><span data-stu-id="9c9bc-108">If there is a difference between these release notes and other App-V 5.0 documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="9c9bc-109">這些版本資訊取代本產品隨附的內容。</span><span class="sxs-lookup"><span data-stu-id="9c9bc-109">These release notes supersede the content that is included with this product.</span></span>

## <span data-ttu-id="9c9bc-110">關於產品檔</span><span class="sxs-lookup"><span data-stu-id="9c9bc-110">About the Product Documentation</span></span>


<span data-ttu-id="9c9bc-111">如需 App-V 5.0 檔的相關資訊，請參閱 Microsoft TechNet 上的 app-v 5.0 首頁。</span><span class="sxs-lookup"><span data-stu-id="9c9bc-111">For information about App-V 5.0 documentation, see the App-V 5.0 home page on Microsoft TechNet.</span></span>

## <span data-ttu-id="9c9bc-112">提供意見反應</span><span class="sxs-lookup"><span data-stu-id="9c9bc-112">Provide Feedback</span></span>


<span data-ttu-id="9c9bc-113">我們對 App-v 5.0 的意見反應感興趣。</span><span class="sxs-lookup"><span data-stu-id="9c9bc-113">We are interested in your feedback on App-V 5.0.</span></span> <span data-ttu-id="9c9bc-114">您可以將意見反應傳送給您 <mdopdocs@microsoft.com> 。</span><span class="sxs-lookup"><span data-stu-id="9c9bc-114">You can send your feedback to <mdopdocs@microsoft.com>.</span></span>

<span data-ttu-id="9c9bc-115">**記事** 此電子郵件地址不是支援頻道，但您的意見反應將協助我們規劃我們的檔和產品版本中的未來變更。</span><span class="sxs-lookup"><span data-stu-id="9c9bc-115">**Note** This email address is not a support channel, but your feedback will help us to plan for future changes in our documentation and product releases.</span></span>

 

<span data-ttu-id="9c9bc-116">如需 MDOP 及其他學習資源的最新資訊，請參閱[Mdop 資訊體驗](https://go.microsoft.com/fwlink/p/?LinkId=236032)頁面。</span><span class="sxs-lookup"><span data-stu-id="9c9bc-116">For the latest information about MDOP and additional learning resources, see the [MDOP Information Experience](https://go.microsoft.com/fwlink/p/?LinkId=236032) page.</span></span>

<span data-ttu-id="9c9bc-117">如需新更新或提供意見反應的詳細資訊，請在[Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445)或[Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447)上關注我們。</span><span class="sxs-lookup"><span data-stu-id="9c9bc-117">For more information about new updates or to provide feedback, follow us on [Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445) or [Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447).</span></span>

## <span data-ttu-id="9c9bc-118">App-v 5.0 的已知問題</span><span class="sxs-lookup"><span data-stu-id="9c9bc-118">Known Issues with App-V 5.0</span></span>


<span data-ttu-id="9c9bc-119">本節包含有關 App-V 5.0 已知問題的版本資訊。</span><span class="sxs-lookup"><span data-stu-id="9c9bc-119">This section contains release notes about the known issues with App-V 5.0.</span></span>

### <span data-ttu-id="9c9bc-120">使用伺服器 PowerShell Cmdlet 時無法終止新增套件</span><span class="sxs-lookup"><span data-stu-id="9c9bc-120">Unable to terminate adding packages when using server PowerShell cmdlets</span></span>

<span data-ttu-id="9c9bc-121">使用 PowerShell 新增套件時，沒有任何方法可結束新增套件。</span><span class="sxs-lookup"><span data-stu-id="9c9bc-121">When you add a package using PowerShell, there is no method to exit adding new packages.</span></span>

<span data-ttu-id="9c9bc-122">因應措施：若要停止新增套件，請在新增最終套件後按**enter** 。</span><span class="sxs-lookup"><span data-stu-id="9c9bc-122">WORKAROUND: To stop adding packages, press **enter** after you have added the final package.</span></span>

### <a href="" id="-------------app-v-5-0-client-rejects-packages-from-servers-whose-ssl-certificate-has-been-revoked"></a> <span data-ttu-id="9c9bc-123">App-V 5.0 用戶端拒絕從已吊銷 SSL 憑證的伺服器套件</span><span class="sxs-lookup"><span data-stu-id="9c9bc-123">App-V 5.0 client rejects packages from servers whose SSL certificate has been revoked</span></span>

<span data-ttu-id="9c9bc-124">使用 HTTPS 通訊協定時，App-v 5.0 用戶端預設會拒絕來自已吊銷 SSL 憑證的伺服器的套件。</span><span class="sxs-lookup"><span data-stu-id="9c9bc-124">When using the HTTPS protocol, the App-V 5.0 client will by default reject packages from servers whose SSL certificate has been revoked.</span></span> <span data-ttu-id="9c9bc-125">您可以透過修改**VerifyCertificateRevocationList**設定，將此行為關閉。</span><span class="sxs-lookup"><span data-stu-id="9c9bc-125">This behavior can be turned off through configuration by modifying the **VerifyCertificateRevocationList** setting.</span></span> <span data-ttu-id="9c9bc-126">將 App-v 5.0 服務重新開機之後，才會將此設定的新設定套用到應用程式。</span><span class="sxs-lookup"><span data-stu-id="9c9bc-126">Applying new configuration for this setting will not take effect until the App-V 5.0 service is restarted.</span></span>

<span data-ttu-id="9c9bc-127">解決方法：重新開機 App-v 5.0 服務。</span><span class="sxs-lookup"><span data-stu-id="9c9bc-127">WORKAROUND: Restart the App-V 5.0 service.</span></span>

## <span data-ttu-id="9c9bc-128">版本資訊版權資訊</span><span class="sxs-lookup"><span data-stu-id="9c9bc-128">Release Notes Copyright Information</span></span>


<span data-ttu-id="9c9bc-129">Microsoft、Active Directory、ActiveX、Bing、Excel、Silverlight、SQLServer、Windows、MicrosoftIntune 和 WindowsPowerShell 是 Microsoft 公司群組的商標。</span><span class="sxs-lookup"><span data-stu-id="9c9bc-129">Microsoft, Active Directory, ActiveX, Bing, Excel, Silverlight, SQLServer, Windows, MicrosoftIntune, and WindowsPowerShell are trademarks of the Microsoft group of companies.</span></span> <span data-ttu-id="9c9bc-130">所有其他商標都是其各自擁有者的財產。</span><span class="sxs-lookup"><span data-stu-id="9c9bc-130">All other trademarks are property of their respective owners.</span></span>








## <span data-ttu-id="9c9bc-131">相關主題</span><span class="sxs-lookup"><span data-stu-id="9c9bc-131">Related topics</span></span>


[<span data-ttu-id="9c9bc-132">關於 App-V 5.0</span><span class="sxs-lookup"><span data-stu-id="9c9bc-132">About App-V 5.0</span></span>](about-app-v-50.md)

 

 





