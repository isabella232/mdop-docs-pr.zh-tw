---
title: 如何當地語系化自助入口網站聲明文字
description: 如何當地語系化自助入口網站聲明文字
author: dansimp
ms.assetid: a4c878b7-e5c8-45af-a537-761bb2991659
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a2385f6b00713e7373bd1707b02324b80f300c0d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811919"
---
# <span data-ttu-id="00df1-103">如何當地語系化自助入口網站聲明文字</span><span class="sxs-lookup"><span data-stu-id="00df1-103">How to Localize the Self-Service Portal Notice Text</span></span>


<span data-ttu-id="00df1-104">您可以設定在自助入口網站中預設顯示給使用者的當地語系化通知文字。</span><span class="sxs-lookup"><span data-stu-id="00df1-104">You can configure localized notice text to display to end users by default in the Self-Service Portal.</span></span> <span data-ttu-id="00df1-105">顯示通知文字的 Notice.txt 檔案位於下列根目錄中：</span><span class="sxs-lookup"><span data-stu-id="00df1-105">The Notice.txt file that displays the notice text is in the following root directory:</span></span>

<span data-ttu-id="00df1-106">&lt;*MBAM 自助安裝目錄* &gt;\\Self Service Website</span><span class="sxs-lookup"><span data-stu-id="00df1-106">&lt;*MBAM Self-Service Install Directory*&gt;\\Self Service Website</span></span>\\

<span data-ttu-id="00df1-107">若要顯示當地語系化的通知文字，您需要建立當地語系化的 Notice.txt 檔案，然後將其儲存在下列範例目錄中的特定語言資料夾中：</span><span class="sxs-lookup"><span data-stu-id="00df1-107">To display localized notice text, you create a localized Notice.txt file, and then save it under a specific language folder in the following example directory:</span></span>

<span data-ttu-id="00df1-108">&lt;*MBAM 自助安裝目錄* &gt;\\Self Service Website</span><span class="sxs-lookup"><span data-stu-id="00df1-108">&lt;*MBAM Self-Service Install Directory*&gt;\\Self Service Website</span></span>\\

<span data-ttu-id="00df1-109">**記事** 您可以使用 [**應用程式設定**] 中的 [ **NoticeTextPath** ] 專案來設定路徑。</span><span class="sxs-lookup"><span data-stu-id="00df1-109">**Note** You can configure the path by using the **NoticeTextPath** item in **Application Settings**.</span></span>

 

<span data-ttu-id="00df1-110">MBAM 會根據下列規則顯示通知文字：</span><span class="sxs-lookup"><span data-stu-id="00df1-110">MBAM displays the notice text, based on the following rules:</span></span>

-   <span data-ttu-id="00df1-111">如果您在適當的語言資料夾中建立當地語系化的**Notice.txt**檔案，MBAM 會顯示預設**Notice.txt**檔案存在的當地語系化聲明文字。</span><span class="sxs-lookup"><span data-stu-id="00df1-111">If you create a localized **Notice.txt** file in the appropriate language folder, MBAM displays the localized notice text if the default **Notice.txt** file exists.</span></span> <span data-ttu-id="00df1-112">如果缺少預設**Notice.txt**檔案，則會顯示一則訊息，指出預設檔案遺失。</span><span class="sxs-lookup"><span data-stu-id="00df1-112">If the default **Notice.txt** file is missing, a message displays indicating that the default file is missing.</span></span>

-   <span data-ttu-id="00df1-113">如果 MBAM 找不到 Notice.txt 檔案的當地語系化版本，則會顯示預設 Notice.txt 檔案中的文字。</span><span class="sxs-lookup"><span data-stu-id="00df1-113">If MBAM does not find a localized version of the Notice.txt file, it displays the text in the default Notice.txt file.</span></span>

-   <span data-ttu-id="00df1-114">如果 MBAM 找不到預設的 Notice.txt 檔案，它會在自助入口網站中顯示預設文字。</span><span class="sxs-lookup"><span data-stu-id="00df1-114">If MBAM does not find a default Notice.txt file, it displays the default text in the Self-Service Portal.</span></span>

<span data-ttu-id="00df1-115">**記事** 如果將最終使用者的瀏覽器設定為沒有對應的語言子資料夾或 Notice.txt 的語言，則會顯示下列根目錄中的 Notice.txt 檔案中的文字：</span><span class="sxs-lookup"><span data-stu-id="00df1-115">**Note** If an end user’s browser is set to a language that does not have a corresponding language subfolder or Notice.txt, the text in the Notice.txt file in the following root directory is displayed:</span></span>

<span data-ttu-id="00df1-116">&lt;*MBAM 自助安裝目錄* &gt;\\Self Service Website</span><span class="sxs-lookup"><span data-stu-id="00df1-116">&lt;*MBAM Self-Service Install Directory*&gt;\\Self Service Website</span></span>\\

 

**<span data-ttu-id="00df1-117">建立當地語系化的 Notice.txt 檔案</span><span class="sxs-lookup"><span data-stu-id="00df1-117">To create a localized Notice.txt file</span></span>**

1.  <span data-ttu-id="00df1-118">在您設定自助入口網站的伺服器上，在 &lt; *Language* &gt; 下列範例目錄中建立語言資料夾，其中的 &lt; *語言* &gt; 代表當地語系化語言的名稱：</span><span class="sxs-lookup"><span data-stu-id="00df1-118">On the server where you configured the Self-Service Portal, create a &lt;*Language*&gt; folder in the following example directory, where &lt;*Language*&gt; represents the name of the localized language:</span></span>

    <span data-ttu-id="00df1-119">&lt;*MBAM 自助安裝目錄* &gt;\\Self Service Website</span><span class="sxs-lookup"><span data-stu-id="00df1-119">&lt;*MBAM Self-Service Install Directory*&gt;\\Self Service Website</span></span>\\

    <span data-ttu-id="00df1-120">**記事** 某些語言資料夾已經存在，因此您可能不需要建立資料夾。</span><span class="sxs-lookup"><span data-stu-id="00df1-120">**Note** Some language folders already exist, so you might not have to create a folder.</span></span> <span data-ttu-id="00df1-121">如果您確實需要建立語言資料夾，請參閱[本國語言支援（NLS） API 參考](https://go.microsoft.com/fwlink/?LinkId=317947)，瞭解您可以用於 &lt; *語言*資料夾的有效名稱清單 &gt; 。</span><span class="sxs-lookup"><span data-stu-id="00df1-121">If you do have to create a language folder, see [National Language Support (NLS) API Reference](https://go.microsoft.com/fwlink/?LinkId=317947) for a list of the valid names that you can use for the &lt;*Language*&gt; folder.</span></span>

     

2.  <span data-ttu-id="00df1-122">建立包含當地語系化通知文字的 Notice.txt 檔案。</span><span class="sxs-lookup"><span data-stu-id="00df1-122">Create a Notice.txt file that contains the localized notice text.</span></span>

3.  <span data-ttu-id="00df1-123">將 Notice.txt 檔案儲存于 [ &lt; *語言*] &gt; 資料夾中。</span><span class="sxs-lookup"><span data-stu-id="00df1-123">Save the Notice.txt file in the &lt;*Language*&gt; folder.</span></span> <span data-ttu-id="00df1-124">例如，若要在西班牙文中建立當地語系化的 Notice.txt 檔案，請在下列範例目錄中儲存已當地語系化的 Notice.txt 檔案：</span><span class="sxs-lookup"><span data-stu-id="00df1-124">For example, to create a localized Notice.txt file in Spanish, save the localized Notice.txt file in the following example directory:</span></span>

    <span data-ttu-id="00df1-125">&lt;*MBAM 自助安裝目錄* &gt;\\Self Service Website\\Es-es</span><span class="sxs-lookup"><span data-stu-id="00df1-125">&lt;*MBAM Self-Service Install Directory*&gt;\\Self Service Website\\Es-es</span></span>

    <span data-ttu-id="00df1-126">語言資料夾的名稱也可以是語言中性名稱**es** ，而不是**es**。</span><span class="sxs-lookup"><span data-stu-id="00df1-126">The name of the Language folder can also be the language neutral name **es** instead of **es-es**.</span></span> <span data-ttu-id="00df1-127">如果最終使用者的瀏覽器設定為**es** ，且該資料夾不存在，則會以遞迴方式檢索及檢查父區域設定（在 .net 中定義），並在最終成為預設 Notice.txt 檔案之前，進行遞迴檢索及檢查 &lt; MBAM 自助安裝目錄 &gt;\\SelfServiceWebsite\\es\\Notice.txt。</span><span class="sxs-lookup"><span data-stu-id="00df1-127">If the end user’s browser is set to **es-es** and that folder does not exist, the parent locale (as defined in .NET) is recursively retrieved and checked, resolving to &lt;MBAM Self-Service Install Directory&gt;\\SelfServiceWebsite\\es\\Notice.txt before finally becoming the default Notice.txt file.</span></span> <span data-ttu-id="00df1-128">這個遞迴回退會模仿 .NET 資源載入規則。</span><span class="sxs-lookup"><span data-stu-id="00df1-128">This recursive fallback mimics the .NET resource loading rules.</span></span>



## <span data-ttu-id="00df1-129">相關主題</span><span class="sxs-lookup"><span data-stu-id="00df1-129">Related topics</span></span>


[<span data-ttu-id="00df1-130">為組織自訂自助入口網站</span><span class="sxs-lookup"><span data-stu-id="00df1-130">Customizing the Self-Service Portal for Your Organization</span></span>](customizing-the-self-service-portal-for-your-organization.md)

 

## <span data-ttu-id="00df1-131">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="00df1-131">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="00df1-132">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="00df1-132">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="00df1-133">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="00df1-133">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span> 





