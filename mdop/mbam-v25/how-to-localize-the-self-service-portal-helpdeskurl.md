---
title: 如何當地語系化自助入口網站的 HelpdeskURL
description: 如何當地語系化自助入口網站的 HelpdeskURL
author: dansimp
ms.assetid: 86798460-077b-459b-8d54-4b605e07d2f1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 0d7ec4ce87bbe5aab56e9fa877ced5f51625a5dc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811918"
---
# <span data-ttu-id="4eeea-103">如何當地語系化自助入口網站的 HelpdeskURL</span><span class="sxs-lookup"><span data-stu-id="4eeea-103">How to Localize the Self-Service Portal “HelpdeskURL”</span></span>


<span data-ttu-id="4eeea-104">您可以設定當地語系化版本的自助入口網站 URL，預設會顯示給使用者。</span><span class="sxs-lookup"><span data-stu-id="4eeea-104">You can configure a localized version of the Self-Service Portal URL to display to end users by default.</span></span> <span data-ttu-id="4eeea-105">自助入口網站 URL 是由參數**HelpdeskURL**表示。</span><span class="sxs-lookup"><span data-stu-id="4eeea-105">The Self-Service Portal URL is represented by the parameter **HelpdeskURL**.</span></span>

<span data-ttu-id="4eeea-106">如果您建立當地語系化版本，請參閱下列指示中的 [Microsoft BitLocker 管理與監視（MBAM）]，找出並顯示當地語系化版本。</span><span class="sxs-lookup"><span data-stu-id="4eeea-106">If you create a localized version, as described in the following instructions, Microsoft BitLocker Administration and Monitoring (MBAM) finds and displays the localized version.</span></span> <span data-ttu-id="4eeea-107">如果 MBAM 找不到當地語系化版本，則會顯示針對參數**HelpDeskURL**設定的 URL。</span><span class="sxs-lookup"><span data-stu-id="4eeea-107">If MBAM does not find a localized version, it displays the URL that is configured for the parameter **HelpDeskURL**.</span></span>

<span data-ttu-id="4eeea-108">**記事** 在下列指示中， *SelfService*是自助服務入口網站的預設虛擬目錄名稱。</span><span class="sxs-lookup"><span data-stu-id="4eeea-108">**Note** In the following instructions, *SelfService* is the default virtual directory name for the Self-Service Portal.</span></span> <span data-ttu-id="4eeea-109">您在設定自助入口網站時，可能會使用不同的名稱。</span><span class="sxs-lookup"><span data-stu-id="4eeea-109">You might have used a different name when you configured the Self-Service Portal.</span></span>

 

**<span data-ttu-id="4eeea-110">若要當地語系化自助入口網站 URL</span><span class="sxs-lookup"><span data-stu-id="4eeea-110">To localize the Self-Service Portal URL</span></span>**

1.  <span data-ttu-id="4eeea-111">在您設定自助入口網站的伺服器上，流覽至 [**網站** &gt; **Microsoft BitLocker 管理及監視** &gt; **SelfService** &gt; **應用程式設定**]。</span><span class="sxs-lookup"><span data-stu-id="4eeea-111">On the server where you configured the Self-Service Portal, browse to **Sites** &gt; **Microsoft BitLocker Administration and Monitoring** &gt; **SelfService** &gt; **Application Settings**.</span></span>

2.  <span data-ttu-id="4eeea-112">在 [**動作**] 窗格中，按一下 [**新增**] 以開啟 [**新增應用程式設定**] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="4eeea-112">In the **Actions** pane, click **Add** to open the **Add Application Setting** dialog box.</span></span>

3.  <span data-ttu-id="4eeea-113">在 [ **Name** ] （名稱）欄位中，輸入**HelpdeskURL**\ _ &lt; *語言* &gt; ，其中 &lt; [*語言*] &gt; 是 URL 的適當語言代碼。</span><span class="sxs-lookup"><span data-stu-id="4eeea-113">In the **Name** field, type **HelpdeskURL**\_&lt;*Language*&gt;, where &lt;*Language*&gt; is the appropriate language code for the URL.</span></span>

    <span data-ttu-id="4eeea-114">例如，若要在西班牙文中建立值的當地語系化版本 `HelpdeskURL` ，請將參數**HelpdeskURL 為 \ _es**。</span><span class="sxs-lookup"><span data-stu-id="4eeea-114">For example, to create a localized version of the `HelpdeskURL` value in Spanish, name the parameter **HelpdeskURL\_es-es**.</span></span>

    <span data-ttu-id="4eeea-115">語言資料夾的名稱也可以是語言中性名稱**es** ，而不是**es**。</span><span class="sxs-lookup"><span data-stu-id="4eeea-115">The name of the Language folder can also be the language neutral name **es** instead of **es-es**.</span></span> <span data-ttu-id="4eeea-116">如果最終使用者的瀏覽器設定為**es** ，且該資料夾不存在，則會以遞迴方式檢索及檢查父區域設定（在 .net 中定義），並在最終成為預設 Notice.txt 檔案之前，進行遞迴檢索及檢查 &lt; MBAM 自助安裝目錄 &gt;\\SelfServiceWebsite\\es\\Notice.txt。</span><span class="sxs-lookup"><span data-stu-id="4eeea-116">If the end user’s browser is set to **es-es** and that folder does not exist, the parent locale (as defined in .NET) is recursively retrieved and checked, resolving to &lt;MBAM Self-Service Install Directory&gt;\\SelfServiceWebsite\\es\\Notice.txt before finally becoming the default Notice.txt file.</span></span> <span data-ttu-id="4eeea-117">這個遞迴回退會模仿 .NET 資源載入規則。</span><span class="sxs-lookup"><span data-stu-id="4eeea-117">This recursive fallback mimics the .NET resource loading rules.</span></span>

    <span data-ttu-id="4eeea-118">如需您可以使用的有效語言代碼清單，請參閱[本國語言支援（NLS） API 參考](https://go.microsoft.com/fwlink/?LinkId=317947)。</span><span class="sxs-lookup"><span data-stu-id="4eeea-118">For a list of the valid language codes you can use, see [National Language Support (NLS) API Reference](https://go.microsoft.com/fwlink/?LinkId=317947).</span></span>

4.  <span data-ttu-id="4eeea-119">在 [**值**] 欄位中，輸入 `HelpdeskURL` 您要向使用者顯示的值的當地語系化版本。</span><span class="sxs-lookup"><span data-stu-id="4eeea-119">In the **Value** field, type the localized version of the `HelpdeskURL` value that you want to display to end users.</span></span>



## <span data-ttu-id="4eeea-120">相關主題</span><span class="sxs-lookup"><span data-stu-id="4eeea-120">Related topics</span></span>


[<span data-ttu-id="4eeea-121">為組織自訂自助入口網站</span><span class="sxs-lookup"><span data-stu-id="4eeea-121">Customizing the Self-Service Portal for Your Organization</span></span>](customizing-the-self-service-portal-for-your-organization.md)

 

 
## <span data-ttu-id="4eeea-122">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="4eeea-122">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="4eeea-123">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="4eeea-123">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="4eeea-124">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="4eeea-124">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>




