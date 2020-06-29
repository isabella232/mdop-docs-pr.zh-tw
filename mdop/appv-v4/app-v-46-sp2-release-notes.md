---
title: App-V 4.6 SP2 版本資訊
description: App-V 4.6 SP2 版本資訊
author: dansimp
ms.assetid: abb536f0-e187-4c5b-952a-f837abd10ad2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: cf36a6361e6f49c2b868c6752e1b2eb379cc9a31
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809297"
---
# <span data-ttu-id="c14f5-103">App-V 4.6 SP2 版本資訊</span><span class="sxs-lookup"><span data-stu-id="c14f5-103">App-V 4.6 SP2 Release Notes</span></span>


**<span data-ttu-id="c14f5-104">若要搜尋這些版本筆記，請按 CTRL + F。</span><span class="sxs-lookup"><span data-stu-id="c14f5-104">To search these release notes, press CTRL+F.</span></span>**

<span data-ttu-id="c14f5-105">在安裝 Microsoft Application Virtualization （App-v） 4.6 SP2 之前，請先閱讀這些版本資訊。</span><span class="sxs-lookup"><span data-stu-id="c14f5-105">Read these release notes thoroughly before you install Microsoft Application Virtualization (App-V)4.6 SP2.</span></span>

<span data-ttu-id="c14f5-106">這些版本資訊包含成功安裝應用程式虛擬化 4.6 SP2 所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="c14f5-106">These release notes contain information that is required to successfully install Application Virtualization 4.6 SP2.</span></span> <span data-ttu-id="c14f5-107">版本資訊中也包含產品檔中不提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="c14f5-107">The release notes also contain information that is not available in the product documentation.</span></span> <span data-ttu-id="c14f5-108">如果這些版本資訊與其他 App-v 4.6 SP2 檔之間有差異，最新變更應該視為權威性。</span><span class="sxs-lookup"><span data-stu-id="c14f5-108">If there is a difference between these release notes and other App-V4.6SP2 documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="c14f5-109">這些版本資訊取代本產品隨附的內容。</span><span class="sxs-lookup"><span data-stu-id="c14f5-109">These release notes supersede the content that is included with this product.</span></span>

## <span data-ttu-id="c14f5-110">關於產品檔</span><span class="sxs-lookup"><span data-stu-id="c14f5-110">About the Product Documentation</span></span>


<span data-ttu-id="c14f5-111">如需 App-v 相關檔的詳細資訊，請參閱 Microsoft TechNet 上的 [[應用程式虛擬化](https://go.microsoft.com/fwlink/?LinkID=232982)] 頁面。</span><span class="sxs-lookup"><span data-stu-id="c14f5-111">For more information about documentation for App-V, see the [Application Virtualization](https://go.microsoft.com/fwlink/?LinkID=232982) page on Microsoft TechNet.</span></span>

## <span data-ttu-id="c14f5-112">提供意見反應</span><span class="sxs-lookup"><span data-stu-id="c14f5-112">Providing feedback</span></span>


<span data-ttu-id="c14f5-113">我們對 App-v 4.6 SP2 的意見反應感興趣。</span><span class="sxs-lookup"><span data-stu-id="c14f5-113">We are interested in your feedback on App-V4.6SP2.</span></span> <span data-ttu-id="c14f5-114">您可以將意見反應傳送給您 <mdopdocs@microsoft.com> 。</span><span class="sxs-lookup"><span data-stu-id="c14f5-114">You can send your feedback to <mdopdocs@microsoft.com>.</span></span>

<span data-ttu-id="c14f5-115">**記事** 此電子郵件地址不是支援頻道，但您的意見反應將協助我們規劃我們的檔和產品發行的未來變更。</span><span class="sxs-lookup"><span data-stu-id="c14f5-115">**Note** This email address is not a support channel, but your feedback will help us to plan future changes for our documentation and product releases.</span></span>

 

<span data-ttu-id="c14f5-116">如需 MDOP 及其他學習資源的最新資訊，請參閱[Mdop 資訊體驗](https://go.microsoft.com/fwlink/p/?LinkId=236032)頁面。</span><span class="sxs-lookup"><span data-stu-id="c14f5-116">For the latest information about MDOP and additional learning resources, see the [MDOP Information Experience](https://go.microsoft.com/fwlink/p/?LinkId=236032) page.</span></span>

<span data-ttu-id="c14f5-117">如需新更新或提供意見反應的詳細資訊，請在[Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445)或[Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447)上關注我們。</span><span class="sxs-lookup"><span data-stu-id="c14f5-117">For more information about new updates or to provide feedback, follow us on [Facebook](https://go.microsoft.com/fwlink/p/?LinkId=242445) or [Twitter](https://go.microsoft.com/fwlink/p/?LinkId=242447).</span></span>

## <a href="" id="known-issues-with-app-v-4-6-sp2-"></a><span data-ttu-id="c14f5-118">App-V 4.6 SP2 的已知問題</span><span class="sxs-lookup"><span data-stu-id="c14f5-118">Known Issues with App-V4.6SP2</span></span>


### <span data-ttu-id="c14f5-119">當您按順序時，系統會停用非系統物理磁片磁碟機的短檔案名支援</span><span class="sxs-lookup"><span data-stu-id="c14f5-119">Short file name support is disabled for non-system physical drives when you sequence</span></span>

<span data-ttu-id="c14f5-120">當您在 Windows 8 或 Windows Server 2012 上順序時，短檔案名（8.3）的支援會預設為非系統物理磁片磁碟機停用。</span><span class="sxs-lookup"><span data-stu-id="c14f5-120">When you sequence on Windows 8 or Windows Server 2012, support for short file names (8.3) is disabled by default for non-system physical drives.</span></span>

<span data-ttu-id="c14f5-121">在先後順序站上，與主要虛擬應用程式目錄（例如，"Q:\\appname"）相關聯的基礎物理磁片磁碟機，必須提供短檔案名（8.3）支援，才能讓 App-V 4.6 SP2 排序器在建立虛擬應用程式套件時產生短檔案名。</span><span class="sxs-lookup"><span data-stu-id="c14f5-121">The underlying physical drive associated with the primary virtual application directory (for example, “Q:\\appname”) on the sequencing station must provide short file name (8.3) support in order for the App-V4.6SP2 Sequencer to generate short file names when creating virtual application packages.</span></span> <span data-ttu-id="c14f5-122">預設會針對 Windows 8 或 Windows Server 2012 上的非系統物理磁片磁碟機停用短檔案名（8.3）支援。</span><span class="sxs-lookup"><span data-stu-id="c14f5-122">Short file name (8.3) support is disabled by default for non-system physical drives on Windows 8 or Windows Server 2012.</span></span>

<span data-ttu-id="c14f5-123">因應措施 **：** 啟用在非系統物理磁片磁碟機上的短檔案名（8.3）支援。</span><span class="sxs-lookup"><span data-stu-id="c14f5-123">**Workaround:** Enable short file name (8.3) support on non-system physical drives.</span></span> <span data-ttu-id="c14f5-124">您可以使用下列命令，在 Windows 8 或 Windows Server 2012 上啟用短檔案名支援。</span><span class="sxs-lookup"><span data-stu-id="c14f5-124">You can use the following command to enable short file name support on Windows 8 or Windows Server 2012.</span></span>

``` syntax
fsutil 8dot3name set <virtual drive letter>:
```

<span data-ttu-id="c14f5-125">例如，如果磁碟機字母是「問：」，請使用下列命令：</span><span class="sxs-lookup"><span data-stu-id="c14f5-125">For example, use the following command if the drive letter is “Q:”:</span></span>

``` syntax
fsutil 8dot3name set Q: 0
```

<span data-ttu-id="c14f5-126">**記事** 您不需要在 App-V 用戶端上變更此設定，因為 App-v 檔案系統會在 Windows 8 或 Windows Server 2012 上正確處理短路徑。</span><span class="sxs-lookup"><span data-stu-id="c14f5-126">**Note** You do not need to change this setting on the App-V client because the App-V file system properly handles short paths on Windows 8 or Windows Server 2012.</span></span>

 

### <a href="" id="-------------app-v-does-not-override-the-default-handler-for-file-type-or-protocol-associations-on-windows-8"></a> <span data-ttu-id="c14f5-127">在 Windows 8 上，app-v 不會覆寫檔案類型或通訊協定關聯的預設處理常式</span><span class="sxs-lookup"><span data-stu-id="c14f5-127">App-V does not override the default handler for file type or protocol associations on Windows 8</span></span>

<span data-ttu-id="c14f5-128">如果您在 Windows 8 上使用 [**控制台**] 中的 [**預設程式**] 選取預設的應用程式，app-v 將不會覆寫該應用程式的相關檔案類型關聯。</span><span class="sxs-lookup"><span data-stu-id="c14f5-128">If you select a default application by using **Default Programs** in **Control Panel** on Windows 8, App-V will not override the associated file type associations for that application.</span></span>

<span data-ttu-id="c14f5-129">因應措施 **：** 所有.</span><span class="sxs-lookup"><span data-stu-id="c14f5-129">**Workaround:** None.</span></span>

### <span data-ttu-id="c14f5-130">Windows 8 上的 mailto 可按一下連結的選項不會提供虛擬化 Outlook 2010</span><span class="sxs-lookup"><span data-stu-id="c14f5-130">Virtualized Outlook 2010 is not offered as an option for mailto clickable links on Windows 8</span></span>

<span data-ttu-id="c14f5-131">Mailto 命令介面擴展不會在 Windows 8 上提供虛擬化的 Outlook 2010。</span><span class="sxs-lookup"><span data-stu-id="c14f5-131">The mailto shell extension does not offer virtualized Outlook 2010 on Windows 8.</span></span> <span data-ttu-id="c14f5-132">例如，如果您在 Windows 8 上的虛擬化 Outlook 2010 中按一下 [mailto：] 連結，就不會建立新的電子郵件視窗。</span><span class="sxs-lookup"><span data-stu-id="c14f5-132">For example, if you click a mailto: link from virtualized Outlook 2010 that is running on Windows 8, a new email window is not created.</span></span> <span data-ttu-id="c14f5-133">此選項可在 Windows 7 和舊版 Windows 作業系統上正常運作。</span><span class="sxs-lookup"><span data-stu-id="c14f5-133">This option works correctly on Windows 7 and earlier versions of the Windows operating system.</span></span>

<span data-ttu-id="c14f5-134">因應措施 **：** 所有.</span><span class="sxs-lookup"><span data-stu-id="c14f5-134">**Workaround:** None.</span></span>

### <a href="" id="-------------application-virtualization-4-6-sp2-update-is-not-offered-on-all-locales-that-use-microsoft-update"></a> <span data-ttu-id="c14f5-135">在使用 Microsoft Update 的所有地區設定中，未提供 Application Virtualization 4.6 SP2 更新</span><span class="sxs-lookup"><span data-stu-id="c14f5-135">Application Virtualization 4.6 SP2 update is not offered on all locales that use Microsoft Update</span></span>

<span data-ttu-id="c14f5-136">當您使用 Microsoft Update 時，適用于下列語言地區設定的 App-v 4.6 SP2 更新無法使用：</span><span class="sxs-lookup"><span data-stu-id="c14f5-136">When you use Microsoft Update, the update for App-V4.6SP2 is not available for the following language locales:</span></span>

-   <span data-ttu-id="c14f5-137">哈薩克文</span><span class="sxs-lookup"><span data-stu-id="c14f5-137">Kazakh</span></span>

-   <span data-ttu-id="c14f5-138">印度文</span><span class="sxs-lookup"><span data-stu-id="c14f5-138">Hindi</span></span>

-   <span data-ttu-id="c14f5-139">塞爾維亞文-西瑞爾文</span><span class="sxs-lookup"><span data-stu-id="c14f5-139">Serbian-Cyrillic</span></span>

<span data-ttu-id="c14f5-140">因應措施 **：** 如果您使用的是 Microsoft Windows Server Update Services （WSUS），請使用英文版的更新，或從 Microsoft 更新目錄下載更新。</span><span class="sxs-lookup"><span data-stu-id="c14f5-140">**Workaround:** If you are using Microsoft Windows Server Update Services (WSUS), use the English version of the update or download the update from the Microsoft Update Catalog.</span></span>

## <span data-ttu-id="c14f5-141">版本資訊版權資訊</span><span class="sxs-lookup"><span data-stu-id="c14f5-141">Release Notes Copyright Information</span></span>


<span data-ttu-id="c14f5-142">Microsoft、Active Directory、ActiveX、Bing、Excel、Silverlight、SQLServer、Windows、MicrosoftIntune 和 WindowsPowerShell 是 Microsoft 公司群組的商標。</span><span class="sxs-lookup"><span data-stu-id="c14f5-142">Microsoft, Active Directory, ActiveX, Bing, Excel, Silverlight, SQLServer, Windows, MicrosoftIntune, and WindowsPowerShell are trademarks of the Microsoft group of companies.</span></span> <span data-ttu-id="c14f5-143">所有其他商標都是其各自擁有者的財產。</span><span class="sxs-lookup"><span data-stu-id="c14f5-143">All other trademarks are property of their respective owners.</span></span>



## <span data-ttu-id="c14f5-144">相關主題</span><span class="sxs-lookup"><span data-stu-id="c14f5-144">Related topics</span></span>


[<span data-ttu-id="c14f5-145">關於 Microsoft Application Virtualization 4.6 SP2</span><span class="sxs-lookup"><span data-stu-id="c14f5-145">About Microsoft Application Virtualization 4.6 SP2</span></span>](about-microsoft-application-virtualization-46-sp2.md)

 

 





