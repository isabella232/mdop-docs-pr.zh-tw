---
title: UE-V 2.1 SP1 的新功能
description: UE-V 2.1 SP1 的新功能
author: dansimp
ms.assetid: 9a40c737-ad9a-4ec1-b42b-31bfabe0f170
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 1f4b6210d95795c352a7ef1402b0353c6f52774b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812350"
---
# <span data-ttu-id="2aa6c-103">UE-V 2.1 SP1 的新功能</span><span class="sxs-lookup"><span data-stu-id="2aa6c-103">What's New in UE-V 2.1 SP1</span></span>


<span data-ttu-id="2aa6c-104">使用者體驗虛擬化 2.1 SP1 與 UE-V 2.1 相比，提供這些新功能和功能。</span><span class="sxs-lookup"><span data-stu-id="2aa6c-104">User Experience Virtualization 2.1 SP1 provides these new features and functionality compared to UE-V 2.1.</span></span> <span data-ttu-id="2aa6c-105">[Microsoft 使用者體驗虛擬化（ue-v） 2.1 Sp1 版本資訊](microsoft-user-experience-virtualization--ue-v--21-sp1-release-notes.md)提供關於 UE-V 2.1 SP1 發行的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="2aa6c-105">The [Microsoft User Experience Virtualization (UE-V) 2.1 SP1 Release Notes](microsoft-user-experience-virtualization--ue-v--21-sp1-release-notes.md) provide more information about the UE-V 2.1 SP1 release.</span></span>

## <span data-ttu-id="2aa6c-106">Windows 10 支援</span><span class="sxs-lookup"><span data-stu-id="2aa6c-106">Support for Windows 10</span></span>


<span data-ttu-id="2aa6c-107">UE-V 2.1 SP1 會新增 Windows 10 支援，以及舊版 UE-V 所支援的相同軟體。</span><span class="sxs-lookup"><span data-stu-id="2aa6c-107">UE-V 2.1 SP1 adds support for Windows 10, in addition to the same software that is supported in earlier versions of UE-V.</span></span>

### <span data-ttu-id="2aa6c-108">與 Microsoft Azure 的相容性</span><span class="sxs-lookup"><span data-stu-id="2aa6c-108">Compatibility with Microsoft Azure</span></span>

<span data-ttu-id="2aa6c-109">Windows 10 可讓企業使用者將 Windows 應用程式設定和 Windows 作業系統設定同步處理至 Azure，而非 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="2aa6c-109">Windows 10 lets enterprise users synchronize Windows app settings and Windows operating system settings to Azure instead of to OneDrive.</span></span> <span data-ttu-id="2aa6c-110">您可以在僅限內部部署網域的電腦上，搭配使用 Windows 10 企業版同步處理功能與 UE-V。</span><span class="sxs-lookup"><span data-stu-id="2aa6c-110">You can use the Windows 10 enterprise sync functionality together with UE-V for on-premises domain-joined computers only.</span></span> <span data-ttu-id="2aa6c-111">若要啟用 Windows 10 與 UE-V 之間的共存，您必須在每一個用戶端或群組原則上使用任一 PowerShell 來停用下列 UE-V 範本。</span><span class="sxs-lookup"><span data-stu-id="2aa6c-111">To enable coexistence between Windows 10 and UE-V, you must disable the following UE-V templates using either PowerShell on each client or Group Policy.</span></span>

<span data-ttu-id="2aa6c-112">在 [群組原則] 中的 [Microsoft 使用者體驗虛擬化] 節點下，設定以下原則設定：</span><span class="sxs-lookup"><span data-stu-id="2aa6c-112">In Group Policy, under the Microsoft User Experience Virtualization node, configure these policy settings:</span></span>

-   <span data-ttu-id="2aa6c-113">啟用「不要同步處理 Windows 應用程式」</span><span class="sxs-lookup"><span data-stu-id="2aa6c-113">Enable “Do Not Synchronize Windows Apps”</span></span>

-   <span data-ttu-id="2aa6c-114">停用「同步處理 Windows 設定」</span><span class="sxs-lookup"><span data-stu-id="2aa6c-114">Disable “Sync Windows Settings”</span></span>

### <span data-ttu-id="2aa6c-115">Windows 10 支援的設定同步處理行為已變更</span><span class="sxs-lookup"><span data-stu-id="2aa6c-115">Settings Synchronization Behavior Changed for Windows 10 Support</span></span>

<span data-ttu-id="2aa6c-116">UE-V 2.1 SP1 會在 Windows 10 裝置之間漫遊工作列設定。</span><span class="sxs-lookup"><span data-stu-id="2aa6c-116">UE-V 2.1 SP1 roams taskbar settings between Windows 10 devices.</span></span> <span data-ttu-id="2aa6c-117">不過，UE-V 不會在執行舊版作業系統的 Windows 10 裝置與裝置之間同步處理工作列設定。</span><span class="sxs-lookup"><span data-stu-id="2aa6c-117">However, UE-V does not synchronize taskbar settings between Windows 10 devices and devices running previous operating systems.</span></span>

<span data-ttu-id="2aa6c-118">此外，UE-V 2.1 SP1 不會同步處理 Windows 10 中的 Microsoft 計算機與舊版作業系統中的 Microsoft 計算機之間的設定。</span><span class="sxs-lookup"><span data-stu-id="2aa6c-118">In addition, UE-V 2.1 SP1 does not synchronize settings between the Microsoft Calculator in Windows 10 and the Microsoft Calculator in previous operating systems.</span></span>

## <span data-ttu-id="2aa6c-119">針對漫遊網路印表機新增的支援</span><span class="sxs-lookup"><span data-stu-id="2aa6c-119">Support Added for Roaming Network Printers</span></span>


<span data-ttu-id="2aa6c-120">UE-V 2.1 SP1 可讓網路印表機在裝置之間漫遊，讓使用者在登入網路上的任何裝置時都能存取其網路印表機。</span><span class="sxs-lookup"><span data-stu-id="2aa6c-120">UE-V 2.1 SP1 lets network printers roam between devices so that a user has access to their network printers when logged on to any device on the network.</span></span> <span data-ttu-id="2aa6c-121">這包括將其設為預設值的印表機漫遊。</span><span class="sxs-lookup"><span data-stu-id="2aa6c-121">This includes roaming the printer that they set as the default.</span></span>

<span data-ttu-id="2aa6c-122">UE-V 中的印表機漫遊需要下列其中一種情況：</span><span class="sxs-lookup"><span data-stu-id="2aa6c-122">Printer roaming in UE-V requires one of these scenarios:</span></span>

-   <span data-ttu-id="2aa6c-123">列印伺服器可以在漫遊至新裝置時下載所需的驅動程式。</span><span class="sxs-lookup"><span data-stu-id="2aa6c-123">The print server can download the required driver when it roams to a new device.</span></span>

-   <span data-ttu-id="2aa6c-124">漫遊網路印表機的驅動程式已預先安裝在任何需要存取該網路印表機的裝置上。</span><span class="sxs-lookup"><span data-stu-id="2aa6c-124">The driver for the roaming network printer is pre-installed on any device that needs to access that network printer.</span></span>

-   <span data-ttu-id="2aa6c-125">您可以從 Windows Update 取得印表機驅動程式。</span><span class="sxs-lookup"><span data-stu-id="2aa6c-125">The printer driver can be obtained from Windows Update.</span></span>

<span data-ttu-id="2aa6c-126">**記事** UE-V 印表機漫遊**功能不會漫遊印表機**設定或喜好設定，例如雙面列印。</span><span class="sxs-lookup"><span data-stu-id="2aa6c-126">**Note** The UE-V printer roaming feature does **not** roam printer settings or preferences, such as printing double-sided.</span></span>

 

## <span data-ttu-id="2aa6c-127">Office 2013 設定位置範本</span><span class="sxs-lookup"><span data-stu-id="2aa6c-127">Office 2013 Settings Location Template</span></span>


<span data-ttu-id="2aa6c-128">UE-V 2.1 和 2.1 SP1 包含 Microsoft Office 2013 設定位置範本，以及改良的 Outlook 簽名支援。</span><span class="sxs-lookup"><span data-stu-id="2aa6c-128">UE-V 2.1 and 2.1 SP1 include the Microsoft Office 2013 settings location template with improved Outlook signature support.</span></span> <span data-ttu-id="2aa6c-129">我們已新增新、回復和轉寄電子郵件的預設簽名設定同步處理。</span><span class="sxs-lookup"><span data-stu-id="2aa6c-129">We’ve added synchronization of default signature settings for new, reply, and forwarded emails.</span></span> <span data-ttu-id="2aa6c-130">客戶不需要再選擇預設的簽名設定。</span><span class="sxs-lookup"><span data-stu-id="2aa6c-130">Customers no longer have to choose the default signature settings.</span></span>

<span data-ttu-id="2aa6c-131">**記事** 您必須為使用者要同步處理其 Outlook 簽名的任何裝置建立 Outlook 設定檔。</span><span class="sxs-lookup"><span data-stu-id="2aa6c-131">**Note** An Outlook profile must be created for any device on which a user wants to sync their Outlook signature.</span></span> <span data-ttu-id="2aa6c-132">如果尚未建立設定檔，使用者可以建立一個，然後重新開機該裝置上的 Outlook，以啟用簽名同步處理。</span><span class="sxs-lookup"><span data-stu-id="2aa6c-132">If the profile is not already created, the user can create one and then restart Outlook on that device to enable signature synchronization.</span></span>

 

<span data-ttu-id="2aa6c-133">先前的 UE-V 包含 Microsoft Office 2010 設定位置範本，這些範本是透過 UE-V Agent 自動分發及註冊。</span><span class="sxs-lookup"><span data-stu-id="2aa6c-133">Previously UE-V included Microsoft Office 2010 settings location templates that were automatically distributed and registered with the UE-V Agent.</span></span> <span data-ttu-id="2aa6c-134">UE-V 2.1 可與 Office 365 搭配使用，以判斷 office 2013 設定是否由 Office 365 所漫遊。</span><span class="sxs-lookup"><span data-stu-id="2aa6c-134">UE-V 2.1 works with Office 365 to determine whether Office 2013 settings are roamed by Office 365.</span></span> <span data-ttu-id="2aa6c-135">如果設定是由 Office 365 漫遊，就不會透過 UE-V 漫遊。</span><span class="sxs-lookup"><span data-stu-id="2aa6c-135">If settings are roamed by Office 365 they are not roamed by UE-V.</span></span> <span data-ttu-id="2aa6c-136">[Office 2013 的使用者和漫遊設定概覽](https://go.microsoft.com/fwlink/p/?LinkID=391220)提供詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="2aa6c-136">[Overview of user and roaming settings for Office 2013](https://go.microsoft.com/fwlink/p/?LinkID=391220) provides more information.</span></span>

<span data-ttu-id="2aa6c-137">若要使用 UE-V 2.1 啟用設定同步處理，請執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="2aa6c-137">To enable settings synchronization using UE-V 2.1, do one of the following:</span></span>

-   <span data-ttu-id="2aa6c-138">使用群組原則來停用 Office 365 同步處理</span><span class="sxs-lookup"><span data-stu-id="2aa6c-138">Use Group Policy to disable Office 365 synchronization</span></span>

-   <span data-ttu-id="2aa6c-139">在安裝 Office 2013 期間，請勿啟用 Office 365 同步處理體驗</span><span class="sxs-lookup"><span data-stu-id="2aa6c-139">Do not enable the Office 365 synchronization experience during Office 2013 installation</span></span>

<span data-ttu-id="2aa6c-140">UE-V 2.1 隨附[office 2013 和 office 2010 範本](https://technet.microsoft.com/library/dn458932.aspx#autosyncsettings)。</span><span class="sxs-lookup"><span data-stu-id="2aa6c-140">UE-V 2.1 ships [Office 2013 and Office 2010 templates](https://technet.microsoft.com/library/dn458932.aspx#autosyncsettings).</span></span> <span data-ttu-id="2aa6c-141">此版本會移除 Office 2007 範本。</span><span class="sxs-lookup"><span data-stu-id="2aa6c-141">This release removes the Office 2007 templates.</span></span> <span data-ttu-id="2aa6c-142">使用者仍然可以使用 UE-V 2.0 或較舊版本的 Office 2007 範本，但仍可在[此處](https://go.microsoft.com/fwlink/p/?LinkID=246589)取得 ue-v 範本庫的範本。</span><span class="sxs-lookup"><span data-stu-id="2aa6c-142">Users can still use Office 2007 templates from UE-V 2.0 or earlier and can still get the templates from the UE-V template gallery located [here](https://go.microsoft.com/fwlink/p/?LinkID=246589).</span></span>






## <span data-ttu-id="2aa6c-143">相關主題</span><span class="sxs-lookup"><span data-stu-id="2aa6c-143">Related topics</span></span>


[<span data-ttu-id="2aa6c-144">UE-V 2.x 入門</span><span class="sxs-lookup"><span data-stu-id="2aa6c-144">Get Started with UE-V 2.x</span></span>](get-started-with-ue-v-2x-new-uevv2.md)

[<span data-ttu-id="2aa6c-145">準備 UE-V a.x 部署</span><span class="sxs-lookup"><span data-stu-id="2aa6c-145">Prepare a UE-V 2.x Deployment</span></span>](prepare-a-ue-v-2x-deployment-new-uevv2.md)

[<span data-ttu-id="2aa6c-146">Microsoft User Experience Virtualization (UE-V) 2.1 SP1 版本資訊</span><span class="sxs-lookup"><span data-stu-id="2aa6c-146">Microsoft User Experience Virtualization (UE-V) 2.1 SP1 Release Notes</span></span>](microsoft-user-experience-virtualization--ue-v--21-sp1-release-notes.md)

 

 





