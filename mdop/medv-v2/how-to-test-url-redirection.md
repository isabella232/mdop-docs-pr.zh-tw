---
title: 如何測試 URL 重新導向
description: 如何測試 URL 重新導向
author: dansimp
ms.assetid: 38d80088-da1d-4098-b27e-76f9e78f81dc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: d964cf9d0114d3085d7e8952eebc82486b7b76cc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810562"
---
# <span data-ttu-id="8babc-103">如何測試 URL 重新導向</span><span class="sxs-lookup"><span data-stu-id="8babc-103">How to Test URL Redirection</span></span>


<span data-ttu-id="8babc-104">在您第一次設定完成測試之後，您可以執行下列工作，以驗證 URL 重新導向功能是否如期運作。</span><span class="sxs-lookup"><span data-stu-id="8babc-104">After your test of first time setup finishes, you can verify that the URL redirection functionality is working as expected by performing the following tasks.</span></span>

<span data-ttu-id="8babc-105">**重要** MED-V 主機代理程式必須執行，URL 重新導向才能正常運作。</span><span class="sxs-lookup"><span data-stu-id="8babc-105">**Important** The MED-V Host Agent must be running for URL redirection to function correctly.</span></span>

<a href="" id="bkmk-urlredir"></a>**<span data-ttu-id="8babc-106">測試 URL 重新導向</span><span class="sxs-lookup"><span data-stu-id="8babc-106">To test URL Redirection</span></span>**

1.  <span data-ttu-id="8babc-107">在主機電腦中開啟 Internet Explorer 瀏覽器，然後輸入您指定要重新導向的 URL。</span><span class="sxs-lookup"><span data-stu-id="8babc-107">Open an Internet Explorer browser in the host computer and enter a URL that you specified for redirection.</span></span>

2.  <span data-ttu-id="8babc-108">確認網頁已在來賓虛擬機器上的 Internet Explorer 中開啟。</span><span class="sxs-lookup"><span data-stu-id="8babc-108">Verify that the webpage is opened in Internet Explorer on the guest virtual machine.</span></span>

3.  <span data-ttu-id="8babc-109">針對您要測試的每個 URL，重複此程式。</span><span class="sxs-lookup"><span data-stu-id="8babc-109">Repeat this process for each URL that you want to test.</span></span>

**<span data-ttu-id="8babc-110">若要測試可以新增或移除 URL</span><span class="sxs-lookup"><span data-stu-id="8babc-110">To test that a URL can be added or removed</span></span>**

1.  <span data-ttu-id="8babc-111">從 MED-V 工作區新增或移除 URL。</span><span class="sxs-lookup"><span data-stu-id="8babc-111">Add or remove a URL from the MED-V workspace.</span></span>

    <span data-ttu-id="8babc-112">如需有關如何在 MED-V 工作區上新增和移除重新導向 Url 的相關資訊，請參閱[管理 med-v-v URL](manage-med-v-url-redirection.md)重新導向。</span><span class="sxs-lookup"><span data-stu-id="8babc-112">For information about how to add and remove URLs for redirection on a MED-V workspace, see [Manage MED-V URL Redirection](manage-med-v-url-redirection.md).</span></span>

2.  <span data-ttu-id="8babc-113">如果您已在重新導向清單中新增 URL，請重複上述步驟[來測試 URL](#bkmk-urlredir)重新導向，以確認新的 URL 會以預期方式重新導向。</span><span class="sxs-lookup"><span data-stu-id="8babc-113">If you added a URL to the redirection list, repeat the steps in [To Test URL Redirection](#bkmk-urlredir) to verify that the new URL redirects as intended.</span></span>

3.  <span data-ttu-id="8babc-114">如果您從 [重新導向] 清單中移除 URL，請遵循下列步驟，確認已移除 URL：</span><span class="sxs-lookup"><span data-stu-id="8babc-114">If you removed a URL from the redirection list, verify that it is removed by following these steps:</span></span>

    1.  <span data-ttu-id="8babc-115">在主機電腦中開啟 Internet Explorer 瀏覽器，然後輸入您從重新導向清單中移除的 URL。</span><span class="sxs-lookup"><span data-stu-id="8babc-115">Open an Internet Explorer browser in the host computer and enter the URL that you removed from the redirection list.</span></span>

    2.  <span data-ttu-id="8babc-116">確認網頁已在主機電腦上的 Internet Explorer 中開啟，而不是在來賓虛擬機器上開啟。</span><span class="sxs-lookup"><span data-stu-id="8babc-116">Verify that the webpage is opened in Internet Explorer on the host computer instead of on the guest virtual machine.</span></span>

        <span data-ttu-id="8babc-117">**記事** 可能需要幾秒鐘的時間，URL 重新導向變更才會發生。</span><span class="sxs-lookup"><span data-stu-id="8babc-117">**Note** It can take several seconds for the URL redirection changes to take place.</span></span>

<span data-ttu-id="8babc-118">**記事** 如果您在驗證 URL 重新導向設定時遇到任何問題，請參閱[操作疑難排解](operations-troubleshooting-medv2.md)。</span><span class="sxs-lookup"><span data-stu-id="8babc-118">**Note** If you encounter any problems when verifying your URL redirection settings, see [Operations Troubleshooting](operations-troubleshooting-medv2.md).</span></span>

<span data-ttu-id="8babc-119">在 MED-V 工作區中測試完 URL 重新導向之後，您可以測試其他設定，以驗證它們正常運作。</span><span class="sxs-lookup"><span data-stu-id="8babc-119">After you have completed testing URL redirection in your MED-V workspace, you can test other configurations to verify that they function as intended.</span></span>

<span data-ttu-id="8babc-120">完成您的 MED-V 工作區套件測試並確認它已正常運作之後，您就可以將 MED-V 工作區部署到您的企業。</span><span class="sxs-lookup"><span data-stu-id="8babc-120">After you have completed testing your MED-V workspace package and have verified that it is functioning as intended, you can deploy the MED-V workspace to your enterprise.</span></span>

## <span data-ttu-id="8babc-121">相關主題</span><span class="sxs-lookup"><span data-stu-id="8babc-121">Related topics</span></span>

[<span data-ttu-id="8babc-122">如何測試應用程式發佈</span><span class="sxs-lookup"><span data-stu-id="8babc-122">How to Test Application Publishing</span></span>](how-to-test-application-publishing.md)

[<span data-ttu-id="8babc-123">如何驗證第一次安裝設定</span><span class="sxs-lookup"><span data-stu-id="8babc-123">How to Verify First Time Setup Settings</span></span>](how-to-verify-first-time-setup-settings.md)

[<span data-ttu-id="8babc-124">部署 MED-V 工作區套件</span><span class="sxs-lookup"><span data-stu-id="8babc-124">Deploying the MED-V Workspace Package</span></span>](deploying-the-med-v-workspace-package.md)

 

 





