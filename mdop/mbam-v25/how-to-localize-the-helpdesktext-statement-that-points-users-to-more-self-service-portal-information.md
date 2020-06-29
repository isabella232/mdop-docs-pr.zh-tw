---
title: 如何將 HelpdeskText 聲明當地語系化，指引使用者取得更多自助入口網站資訊
description: 如何將 HelpdeskText 聲明當地語系化，指引使用者取得更多自助入口網站資訊
author: dansimp
ms.assetid: 09ba2a07-3186-45d9-adef-4034c70ae7cf
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 2367424185da813a46fa52f3614c03083864f75f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809945"
---
# <span data-ttu-id="18959-103">如何將 HelpdeskText 聲明當地語系化，指引使用者取得更多自助入口網站資訊</span><span class="sxs-lookup"><span data-stu-id="18959-103">How to Localize the “HelpdeskText” Statement that Points Users to More Self-Service Portal Information</span></span>


<span data-ttu-id="18959-104">您可以設定當地語系化版本的自助入口 "HelpdeskText" 語句，這會通知最終使用者如何在使用自助入口網站時取得其他協助。</span><span class="sxs-lookup"><span data-stu-id="18959-104">You can configure a localized version of the Self-Service Portal "HelpdeskText" statement, which informs end users about how to get additional help when they are using the Self-Service Portal.</span></span> <span data-ttu-id="18959-105">如果您設定語句的當地語系化文字，請參閱下列指示中的 MBAM 顯示當地語系化版本。</span><span class="sxs-lookup"><span data-stu-id="18959-105">If you configure localized text for the statement, as described in the following instructions, MBAM displays the localized version.</span></span> <span data-ttu-id="18959-106">如果 MBAM 找不到已當地語系化的版本，則會顯示**HelpdeskText**參數中的值。</span><span class="sxs-lookup"><span data-stu-id="18959-106">If MBAM does not find the localized version, it displays the value that is in the **HelpdeskText** parameter.</span></span>

<span data-ttu-id="18959-107">**記事** 在下列指示中， *SelfService*是自助服務入口網站的預設虛擬目錄名稱。</span><span class="sxs-lookup"><span data-stu-id="18959-107">**Note** In the following instructions, *SelfService* is the default virtual directory name for the Self-Service Portal.</span></span> <span data-ttu-id="18959-108">您在設定自助入口網站時，可能會使用不同的名稱。</span><span class="sxs-lookup"><span data-stu-id="18959-108">You might have used a different name when you configured the Self-Service Portal.</span></span>

 

**<span data-ttu-id="18959-109">顯示 HelpdeskText 語句的當地語系化版本</span><span class="sxs-lookup"><span data-stu-id="18959-109">To display a localized version of the HelpdeskText statement</span></span>**

1.  <span data-ttu-id="18959-110">在您設定自助入口網站的伺服器上，流覽至 [**網站** &gt; **Microsoft BitLocker 管理及監視** &gt; **SelfService** &gt; **應用程式設定**]。</span><span class="sxs-lookup"><span data-stu-id="18959-110">On the server where you configured the Self-Service Portal, browse to **Sites** &gt; **Microsoft BitLocker Administration and Monitoring** &gt; **SelfService** &gt; **Application Settings**.</span></span>

2.  <span data-ttu-id="18959-111">在 [**動作**] 窗格中，按一下 [**新增**] 以開啟 [**新增應用程式設定**] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="18959-111">In the **Actions** pane, click **Add** to open the **Add Application Setting** dialog box.</span></span>

3.  <span data-ttu-id="18959-112">在 [ **Name** ] （名稱）欄位中，輸入**HelpdeskText**\ _ &lt; *語言* &gt; ，其中 [ &lt; *語言*] &gt; 是該文字的適當語言代碼。</span><span class="sxs-lookup"><span data-stu-id="18959-112">In the **Name** field, type **HelpdeskText**\_&lt;*Language*&gt;, where &lt;*Language*&gt; is the appropriate language code for the text.</span></span>

    <span data-ttu-id="18959-113">例如，若要在西班牙文中建立當地語系化的 HelpdeskText 語句，請將參數命名為**HelpdeskText \ _es-es**。</span><span class="sxs-lookup"><span data-stu-id="18959-113">For example, to create a localized HelpdeskText statement in Spanish, name the parameter **HelpdeskText\_es-es**.</span></span>

    <span data-ttu-id="18959-114">語言資料夾的名稱也可以是語言中性名稱**es** ，而不是**es**。</span><span class="sxs-lookup"><span data-stu-id="18959-114">The name of the Language folder can also be the language neutral name **es** instead of **es-es**.</span></span> <span data-ttu-id="18959-115">如果最終使用者的瀏覽器設定為**es** ，且該資料夾不存在，則會以遞迴方式檢索及檢查父區域設定（在 .net 中定義），並在最終成為預設 Notice.txt 檔案之前，進行遞迴檢索及檢查 &lt; MBAM 自助安裝目錄 &gt;\\SelfServiceWebsite\\es\\Notice.txt。</span><span class="sxs-lookup"><span data-stu-id="18959-115">If the end user’s browser is set to **es-es** and that folder does not exist, the parent locale (as defined in .NET) is recursively retrieved and checked, resolving to &lt;MBAM Self-Service Install Directory&gt;\\SelfServiceWebsite\\es\\Notice.txt before finally becoming the default Notice.txt file.</span></span> <span data-ttu-id="18959-116">這個遞迴回退會模仿 .NET 資源載入規則。</span><span class="sxs-lookup"><span data-stu-id="18959-116">This recursive fallback mimics the .NET resource loading rules.</span></span>

    <span data-ttu-id="18959-117">如需您可以使用的有效語言代碼清單，請參閱[本國語言支援（NLS） API 參考](https://go.microsoft.com/fwlink/?LinkId=317947)。</span><span class="sxs-lookup"><span data-stu-id="18959-117">For a list of the valid language codes you can use, see [National Language Support (NLS) API Reference](https://go.microsoft.com/fwlink/?LinkId=317947).</span></span>

4.  <span data-ttu-id="18959-118">在 [**值**] 欄位中，輸入您要顯示給最終使用者的當地語系化文字。</span><span class="sxs-lookup"><span data-stu-id="18959-118">In the **Value** field, type the localized text that you want to display to end users.</span></span>



## <span data-ttu-id="18959-119">相關主題</span><span class="sxs-lookup"><span data-stu-id="18959-119">Related topics</span></span>


[<span data-ttu-id="18959-120">為組織自訂自助入口網站</span><span class="sxs-lookup"><span data-stu-id="18959-120">Customizing the Self-Service Portal for Your Organization</span></span>](customizing-the-self-service-portal-for-your-organization.md)

 

 

## <span data-ttu-id="18959-121">取得 MBAM 的建議嗎？</span><span class="sxs-lookup"><span data-stu-id="18959-121">Got a suggestion for MBAM?</span></span>
- <span data-ttu-id="18959-122">在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="18959-122">Add or vote on suggestions [here](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring).</span></span> 
- <span data-ttu-id="18959-123">如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。</span><span class="sxs-lookup"><span data-stu-id="18959-123">For MBAM issues, use the [MBAM TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam).</span></span>



