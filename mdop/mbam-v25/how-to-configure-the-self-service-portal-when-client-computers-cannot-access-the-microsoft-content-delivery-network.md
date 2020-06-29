---
title: 如何在用戶端電腦無法存取 Microsoft 內容傳遞網路時設定自助入口網站
description: 如何在用戶端電腦無法存取 Microsoft 內容傳遞網路時設定自助入口網站
author: dansimp
ms.assetid: 90ee76db-9876-41b5-994a-118556d5ed3b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ffce3dd023cb6ff9bd5cdb13ea789b348661de24
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810587"
---
# <span data-ttu-id="390e9-103">如何在用戶端電腦無法存取 Microsoft 內容傳遞網路時設定自助入口網站</span><span class="sxs-lookup"><span data-stu-id="390e9-103">How to Configure the Self-Service Portal When Client Computers Cannot Access the Microsoft Content Delivery Network</span></span>


<span data-ttu-id="390e9-104">如果貴組織中的用戶端電腦無法存取 Microsoft Ajax 內容傳遞網路（CDN），請遵循下列指示進行。</span><span class="sxs-lookup"><span data-stu-id="390e9-104">Follow these instructions if the client computers in your organization do not have access to the Microsoft Ajax Content Delivery Network (CDN).</span></span>

**<span data-ttu-id="390e9-105">為什麼您需要設定：</span><span class="sxs-lookup"><span data-stu-id="390e9-105">Why you need to configure this:</span></span>**

<span data-ttu-id="390e9-106">您的用戶端電腦需要存取 CDN，這可讓自助服務入口網站所需的特定 JavaScript 檔案存取權。</span><span class="sxs-lookup"><span data-stu-id="390e9-106">Your client computers need access to the CDN, which gives the Self-Service Portal the required access to certain JavaScript files.</span></span> <span data-ttu-id="390e9-107">如果您未在用戶端電腦無法存取 CDN 時設定自助入口網站，則只有公司名稱和最終使用者登入所使用的帳戶才會顯示。</span><span class="sxs-lookup"><span data-stu-id="390e9-107">If you don’t configure the Self-Service Portal when client computers cannot access CDN, only the company name and the account under which the end user logs in will be displayed.</span></span> <span data-ttu-id="390e9-108">不會顯示任何錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="390e9-108">No error message will be shown.</span></span>

<span data-ttu-id="390e9-109">**記事** 在 MBAM 2.5 SP1 中，JavaScript 檔案包含在產品中，您不需要按照本節中的指示，將 SSP 設定為支援無法存取網際網路的用戶端。</span><span class="sxs-lookup"><span data-stu-id="390e9-109">**Note** In MBAM 2.5 SP1, the JavaScript files are included in the product, and you do not need to follow the instructions in this section to configure the SSP to support clients that cannot access the internet.</span></span>

 

**<span data-ttu-id="390e9-110">當用戶端電腦無法存取 CDN 時，如何設定自助服務入口網站</span><span class="sxs-lookup"><span data-stu-id="390e9-110">How to configure the Self-Service Portal when client computers cannot access the CDN</span></span>**

1. <span data-ttu-id="390e9-111">從 CDN 下載下列 JavaScript 檔案：</span><span class="sxs-lookup"><span data-stu-id="390e9-111">Download the following JavaScript files from the CDN:</span></span>

   -   [<span data-ttu-id="390e9-112">jQuery-1.10.2.min.js</span><span class="sxs-lookup"><span data-stu-id="390e9-112">jQuery-1.10.2.min.js</span></span>](https://go.microsoft.com/fwlink/?LinkID=390515)

   -   [<span data-ttu-id="390e9-113">jQuery.validate.min.js</span><span class="sxs-lookup"><span data-stu-id="390e9-113">jQuery.validate.min.js</span></span>](https://go.microsoft.com/fwlink/?LinkID=390516)

   -   [<span data-ttu-id="390e9-114">jQuery.validate.unobtrusive.min.js</span><span class="sxs-lookup"><span data-stu-id="390e9-114">jQuery.validate.unobtrusive.min.js</span></span>](https://go.microsoft.com/fwlink/?LinkID=390517)

2. <span data-ttu-id="390e9-115">將 JavaScript 檔案複製到自助服務入口網站的 [**腳本**] 目錄。</span><span class="sxs-lookup"><span data-stu-id="390e9-115">Copy the JavaScript files to the **Scripts** directory of the Self-Service Portal.</span></span> <span data-ttu-id="390e9-116">此目錄位於 <em> &lt; MBAM 自助安裝目錄 &gt; \\ </em> 自助服務 Website\\Scripts。</span><span class="sxs-lookup"><span data-stu-id="390e9-116">This directory is located in <em>&lt;MBAM Self-Service Install Directory&gt;\\</em>Self Service Website\\Scripts.</span></span>

3. <span data-ttu-id="390e9-117">開啟 [網際網路資訊服務（IIS）管理員]。</span><span class="sxs-lookup"><span data-stu-id="390e9-117">Open Internet Information Services (IIS) Manager.</span></span>

4. <span data-ttu-id="390e9-118">展開 [**網站** &gt; **Microsoft BitLocker 管理與監視**]，然後醒目提示 [ **SelfService**]。</span><span class="sxs-lookup"><span data-stu-id="390e9-118">Expand **Sites** &gt; **Microsoft BitLocker Administration and Monitoring**, and highlight **SelfService**.</span></span>

   **<span data-ttu-id="390e9-119">注意</span><span class="sxs-lookup"><span data-stu-id="390e9-119">Note</span></span>**  
   <span data-ttu-id="390e9-120">*SelfService*是預設的虛擬目錄名稱。</span><span class="sxs-lookup"><span data-stu-id="390e9-120">*SelfService* is the default virtual directory name.</span></span> <span data-ttu-id="390e9-121">如果您在設定期間為此目錄選擇其他名稱，請記得以您所選擇的名稱取代這些指示中的*SelfService* 。</span><span class="sxs-lookup"><span data-stu-id="390e9-121">If you chose a different name for this directory during the configuration, remember to replace *SelfService* in these instructions with the name you chose.</span></span>

     

5. <span data-ttu-id="390e9-122">按兩下中間窗格中的 [**應用程式設定**]。</span><span class="sxs-lookup"><span data-stu-id="390e9-122">In the middle pane, double-click **Application Settings**.</span></span>

6. <span data-ttu-id="390e9-123">針對下列清單中的每個專案，透過 &lt; 使用/SelfService/（或您在設定期間選擇的任何名稱）來取代/*虛擬目錄*/以參照新位置來編輯應用程式設定 &gt; 。</span><span class="sxs-lookup"><span data-stu-id="390e9-123">For each item in the following list, edit the application settings to reference the new location by replacing /&lt;*virtual directory*&gt;/ with /SelfService/ (or whatever name you chose during configuration).</span></span> <span data-ttu-id="390e9-124">例如，虛擬目錄路徑會類似/selfservice/Scripts/jQuery-1.10.2.min.js。</span><span class="sxs-lookup"><span data-stu-id="390e9-124">For example, the virtual directory path will be similar to /selfservice/Scripts/ jQuery-1.10.2.min.js.</span></span>

   -   <span data-ttu-id="390e9-125">jQueryPath：/ &lt; *virtual directory* &gt; /Scripts/jQuery-1.10.2.min.js</span><span class="sxs-lookup"><span data-stu-id="390e9-125">jQueryPath: /&lt;*virtual directory*&gt;/Scripts/jQuery-1.10.2.min.js</span></span>

   -   <span data-ttu-id="390e9-126">jQueryValidatePath：/ &lt; *virtual directory* &gt; /Scripts/jQuery.validate.min.js</span><span class="sxs-lookup"><span data-stu-id="390e9-126">jQueryValidatePath: /&lt;*virtual directory*&gt;/Scripts/jQuery.validate.min.js</span></span>

   -   <span data-ttu-id="390e9-127">jQueryValidateUnobtrusivePath：/ &lt; *virtual directory* &gt; /Scripts/jQuery.validate.unobtrusive.min.js</span><span class="sxs-lookup"><span data-stu-id="390e9-127">jQueryValidateUnobtrusivePath: /&lt;*virtual directory*&gt;/Scripts/jQuery.validate.unobtrusive.min.js</span></span>



## <span data-ttu-id="390e9-128">相關主題</span><span class="sxs-lookup"><span data-stu-id="390e9-128">Related topics</span></span>


[<span data-ttu-id="390e9-129">如何設定 MBAM 2.5 Web 應用程式</span><span class="sxs-lookup"><span data-stu-id="390e9-129">How to Configure the MBAM 2.5 Web Applications</span></span>](how-to-configure-the-mbam-25-web-applications.md)

 

## <span data-ttu-id="390e9-130">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="390e9-130">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="390e9-131">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="390e9-131">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="390e9-132">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="390e9-132">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





