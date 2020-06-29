---
title: Microsoft 進階群組原則管理 4.0 SP1 版本資訊
description: Microsoft 進階群組原則管理 4.0 SP1 版本資訊
author: dansimp
ms.assetid: 91835bf8-e53c-4202-986e-8d37050d1267
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ff9ce0405df766aef9b30e67d07ceb579c4fa89f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801854"
---
# <span data-ttu-id="6de9e-103">Microsoft 進階群組原則管理 4.0 SP1 版本資訊</span><span class="sxs-lookup"><span data-stu-id="6de9e-103">Release Notes for Microsoft Advanced Group Policy Management 4.0 SP1</span></span>


<span data-ttu-id="6de9e-104">若要搜尋這些版本筆記，請按 Ctrl + F。</span><span class="sxs-lookup"><span data-stu-id="6de9e-104">To search these release notes, press Ctrl+F.</span></span>

<span data-ttu-id="6de9e-105">安裝 Microsoft 高級群組原則管理（AGPM） 4.0 SP1 之前，請先閱讀這些版本資訊。</span><span class="sxs-lookup"><span data-stu-id="6de9e-105">Read these release notes thoroughly before you install Microsoft Advanced Group Policy Management (AGPM) 4.0 SP1.</span></span> <span data-ttu-id="6de9e-106">這些版本資訊包含成功安裝 AGPM 4.0 SP1 所需的資訊，且包含產品檔中無法提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="6de9e-106">These release notes contain information that is required to successfully install AGPM 4.0 SP1 and contain information that is not available in the product documentation.</span></span> <span data-ttu-id="6de9e-107">如果這些版本資訊與其他 AGPM 檔之間有差異，最新變更應該視為權威性。</span><span class="sxs-lookup"><span data-stu-id="6de9e-107">If there is a difference between these release notes and other AGPM documentation, the latest change should be considered authoritative.</span></span> <span data-ttu-id="6de9e-108">這些版本資訊取代本產品隨附的內容。</span><span class="sxs-lookup"><span data-stu-id="6de9e-108">These release notes supersede the content included with this product.</span></span>

## <span data-ttu-id="6de9e-109">AGPM 4.0 SP1 已知問題</span><span class="sxs-lookup"><span data-stu-id="6de9e-109">AGPM 4.0 SP1 known issues</span></span>


<span data-ttu-id="6de9e-110">本節包含適用于 AGPM 4.0 SP1 的版本資訊。</span><span class="sxs-lookup"><span data-stu-id="6de9e-110">This section contains release notes for AGPM 4.0 SP1.</span></span>

### <a href="" id="control-panel-s--uninstall--tool-may-not-work-when-you-try-to-change-agpm-server-settings"></a><span data-ttu-id="6de9e-111">當您嘗試變更 AGPM 服務器設定時，[控制台] 的 [卸載] 工具可能無法運作</span><span class="sxs-lookup"><span data-stu-id="6de9e-111">Control Panel’s “Uninstall” tool may not work when you try to change AGPM Server settings</span></span>

<span data-ttu-id="6de9e-112">[控制台] 中的工具可讓您卸載或變更程式在您嘗試變更 AGPM 服務器設定時可能無法運作。</span><span class="sxs-lookup"><span data-stu-id="6de9e-112">The tool in Control Panel that lets you uninstall or change a program may not work when you try to change AGPM server settings.</span></span>

<span data-ttu-id="6de9e-113">因應措施：在您嘗試使用 [控制台] 變更 AGPM 服務器設定之前，請製作 [AGPM 封存] 資料夾的複本。</span><span class="sxs-lookup"><span data-stu-id="6de9e-113">WORKAROUND: Before you try to change AGPM server settings by using Control Panel, make a copy of the AGPM Archive folder.</span></span> <span data-ttu-id="6de9e-114">然後，您可以使用 Setup.exe 重新安裝 AGPM 服務器，然後選擇您想要的設定參數。</span><span class="sxs-lookup"><span data-stu-id="6de9e-114">You can then use Setup.exe to reinstall the AGPM server and choose the configuration parameters that you want.</span></span>

### <span data-ttu-id="6de9e-115">報告不會顯示已新增至群組原則物件的連結</span><span class="sxs-lookup"><span data-stu-id="6de9e-115">Reports do not display the links that were added to a Group Policy Object</span></span>

<span data-ttu-id="6de9e-116">[AGPM 設定] 和 [差異] 報告不會顯示已新增至群組原則物件（GPO）的連結。</span><span class="sxs-lookup"><span data-stu-id="6de9e-116">The AGPM settings and difference reports do not display the links that were added to a Group Policy Object (GPO).</span></span>

<span data-ttu-id="6de9e-117">因應措施：若要在報表中查看連結，請在 [群組原則管理主控台（GPMC）] 中選取 GPO，然後按一下右窗格中的 [**設定**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="6de9e-117">WORKAROUND: To view the links in the reports, select the GPO in the Group Policy Management Console (GPMC), and click the **Settings** tab in the right pane.</span></span>

### <a href="" id="reports-do-not-display-all--choice-options-properties--settings"></a><span data-ttu-id="6de9e-118">報告不會顯示所有「選擇選項屬性」設定</span><span class="sxs-lookup"><span data-stu-id="6de9e-118">Reports do not display all “Choice Options Properties” settings</span></span>

<span data-ttu-id="6de9e-119">[AGPM 設定] 和 [差異] 報告不會顯示在 [群群組原則物件編輯器] 的 [選擇選項屬性] 視窗中選取的所有設定。</span><span class="sxs-lookup"><span data-stu-id="6de9e-119">The AGPM settings and difference reports do not display all of the settings that were selected on the Choice Options Properties window in the Group Policy Object Editor.</span></span>

<span data-ttu-id="6de9e-120">因應措施：使用 GPMC 在報表中查看選取的 [選擇選項] 屬性設定。</span><span class="sxs-lookup"><span data-stu-id="6de9e-120">WORKAROUND: Use the GPMC to view the selected Choice Options Properties settings in the reports.</span></span>

### <span data-ttu-id="6de9e-121">報表不會顯示某些瀏覽器中的 [顯示] 和 [隱藏] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="6de9e-121">Reports do not display the Show and Hide tabs in certain browsers</span></span>

<span data-ttu-id="6de9e-122">當您在 Google Chrome 或 Mozilla Firefox 中查看報表時，[顯示] 和 [隱藏] 索引標籤會顯示在 [AGPM 設定] 和 [差異] 報告的右側。</span><span class="sxs-lookup"><span data-stu-id="6de9e-122">The Show and Hide tabs, shown on the right side of the AGPM settings and difference reports, are not displayed when you view the reports in Google Chrome or Mozilla Firefox.</span></span>

<span data-ttu-id="6de9e-123">解決方法：使用 Internet Explorer 來查看報表。</span><span class="sxs-lookup"><span data-stu-id="6de9e-123">WORKAROUND: View the reports by using Internet Explorer.</span></span>

### <span data-ttu-id="6de9e-124">AGPM 設定和差異報告可能會顯示 GPMC 報告的不同內容</span><span class="sxs-lookup"><span data-stu-id="6de9e-124">AGPM settings and difference reports may show different content from GPMC reports</span></span>

<span data-ttu-id="6de9e-125">在群組原則管理主控台（GPMC）中，AGPM 設定和差異報告可能不會顯示與報告相同的內容。</span><span class="sxs-lookup"><span data-stu-id="6de9e-125">The AGPM settings and difference reports may not show the same content as reports in the Group Policy Management Console (GPMC).</span></span>

<span data-ttu-id="6de9e-126">解決方法：使用 GPMC 來查看 AGPM 報告。</span><span class="sxs-lookup"><span data-stu-id="6de9e-126">WORKAROUND: Use the GPMC to view the AGPM reports.</span></span>

### <span data-ttu-id="6de9e-127">如果網網域控制站沒有線上，則 AGPM 服務無法啟動</span><span class="sxs-lookup"><span data-stu-id="6de9e-127">AGPM Service does not start if the domain controller is not online</span></span>

<span data-ttu-id="6de9e-128">當 AGPM 服務安裝在 Windows 8 上的網網域控制站上時，如果網網域控制站沒有線上，該服務就不會啟動。</span><span class="sxs-lookup"><span data-stu-id="6de9e-128">When the AGPM Service is installed on a domain controller on Windows 8, the Service does not start if the domain controller is not online.</span></span>

<span data-ttu-id="6de9e-129">因應措施：在網網域控制站處於線上狀態之後，手動啟動 AGPM 服務。</span><span class="sxs-lookup"><span data-stu-id="6de9e-129">WORKAROUND: Manually start the AGPM Service after the domain controller is online.</span></span>

### <span data-ttu-id="6de9e-130">將 AGPM 服務器升級至 AGPM 4.0 SP1 時，當您從 AGPM 4.0 發行加上此熱修復程式後，就會遭到封鎖</span><span class="sxs-lookup"><span data-stu-id="6de9e-130">Upgrade of AGPM Server to AGPM 4.0 SP1 is blocked when you upgrade from the AGPM 4.0 release plus the hotfix</span></span>

<span data-ttu-id="6de9e-131">如果您嘗試將 AGPM 服務器升級至 AGPM 4.0。</span><span class="sxs-lookup"><span data-stu-id="6de9e-131">If you try to upgrade the AGPM server to AGPM 4.0.</span></span> <span data-ttu-id="6de9e-132">SP1 安裝 AGPM 4.0 之後，接著安裝 AGPM 修復程式（請參閱知識庫文章[2643502](https://go.microsoft.com/fwlink/?LinkId=254474)），升級失敗且無法完成。</span><span class="sxs-lookup"><span data-stu-id="6de9e-132">SP1 after installing AGPM 4.0 and then installing the AGPM hotfix (see Knowledge Base article [2643502](https://go.microsoft.com/fwlink/?LinkId=254474)), the upgrade fails and cannot be completed.</span></span>

<span data-ttu-id="6de9e-133">解決方法：卸載 AGPM 4.0 伺服器，然後安裝 AGPM 4.0 SP1。</span><span class="sxs-lookup"><span data-stu-id="6de9e-133">WORKAROUND: Uninstall the AGPM 4.0 Server and then install AGPM 4.0 SP1.</span></span>

### <span data-ttu-id="6de9e-134">報告不會顯示組織單位連結</span><span class="sxs-lookup"><span data-stu-id="6de9e-134">Reports do not display organizational unit links</span></span>

<span data-ttu-id="6de9e-135">如果您將不受管理的 GPO 連結至組織單位，然後使用 AGPM 控制該 GPO，則 AGPM 設定和差異報告不會顯示組織單位連結。</span><span class="sxs-lookup"><span data-stu-id="6de9e-135">If you link an uncontrolled GPO to an organizational unit and then control that GPO using AGPM, the AGPM settings and difference reports do not display the organizational unit links.</span></span>

<span data-ttu-id="6de9e-136">因應措施：從 [**變更設定**] 節點的 [**受控**] 索引標籤上，以滑鼠右鍵按一下該 GPO，然後按一下 [**設定**]，再按一下 [ **gpo 連結**] 來查看組織連結。</span><span class="sxs-lookup"><span data-stu-id="6de9e-136">WORKAROUND: From the **Controlled** tab of the **Change Settings** node, right-click the GPO and click **Settings** and then click **GPO Links** to view the organizational links.</span></span> <span data-ttu-id="6de9e-137">或者，您可以使用 GPMC 從 [**範圍**] 索引標籤中查看 GPO 的連結。</span><span class="sxs-lookup"><span data-stu-id="6de9e-137">Alternatively, you can use the GPMC to view the links to a GPO from the **Scope** tab.</span></span>

## <span data-ttu-id="6de9e-138">相關主題</span><span class="sxs-lookup"><span data-stu-id="6de9e-138">Related topics</span></span>


[<span data-ttu-id="6de9e-139">進階群組原則管理</span><span class="sxs-lookup"><span data-stu-id="6de9e-139">Advanced Group Policy Management</span></span>](index.md)

[<span data-ttu-id="6de9e-140">AGPM 4.0 SP1 的新功能</span><span class="sxs-lookup"><span data-stu-id="6de9e-140">What's New in AGPM 4.0 SP1</span></span>](whats-new-in-agpm-40-sp1.md)

 

 





