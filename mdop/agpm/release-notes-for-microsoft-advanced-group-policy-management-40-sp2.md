---
title: Microsoft 進階群組原則管理 4.0 SP2 版本資訊
description: Microsoft 進階群組原則管理 4.0 SP2 版本資訊
author: dansimp
ms.assetid: 0593cd11-3308-4942-bf19-8a7bb9447f01
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 736eb8d41cbb72b274a2941c60b0357bbc948c9d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802597"
---
# <span data-ttu-id="ed643-103">Microsoft 進階群組原則管理 4.0 SP2 版本資訊</span><span class="sxs-lookup"><span data-stu-id="ed643-103">Release Notes for Microsoft Advanced Group Policy Management 4.0 SP2</span></span>


<span data-ttu-id="ed643-104">若要搜尋這些版本筆記，請按 Ctrl + F。</span><span class="sxs-lookup"><span data-stu-id="ed643-104">To search these release notes, press Ctrl+F.</span></span>

<span data-ttu-id="ed643-105">安裝 Microsoft 高級群組原則管理（AGPM）4.0 服務 Pack2 （SP2）之前，請先閱讀這些版本資訊。</span><span class="sxs-lookup"><span data-stu-id="ed643-105">Read these release notes thoroughly before you install Microsoft Advanced Group Policy Management (AGPM)4.0 Service Pack2 (SP2).</span></span> <span data-ttu-id="ed643-106">這些版本資訊包含成功安裝 AGPM 4.0 SP2 所需的資訊，且包含產品檔中不提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="ed643-106">These release notes contain information that is required to successfully install AGPM4.0 SP2 and contain information that is not available in the product documentation.</span></span> <span data-ttu-id="ed643-107">如果這些版本資訊與其他 AGPM 檔之間有差異，請考慮最新的變更權威性。</span><span class="sxs-lookup"><span data-stu-id="ed643-107">If there is a difference between these release notes and other AGPM documentation, consider the latest change authoritative.</span></span> <span data-ttu-id="ed643-108">這些版本資訊取代本產品隨附的內容。</span><span class="sxs-lookup"><span data-stu-id="ed643-108">These release notes supersede the content included with this product.</span></span>

## <span data-ttu-id="ed643-109">AGPM 4.0 SP2 已知問題</span><span class="sxs-lookup"><span data-stu-id="ed643-109">AGPM4.0 SP2 known issues</span></span>


<span data-ttu-id="ed643-110">本節說明適用于 AGPM 4.0 SP2 的已知問題。</span><span class="sxs-lookup"><span data-stu-id="ed643-110">This section describes the known issues for AGPM 4.0 SP2.</span></span>

### <a href="" id="control-panel-s--uninstall--tool-may-not-work-when-you-try-to-change-agpm-server-settings"></a><span data-ttu-id="ed643-111">當您嘗試變更 AGPM 服務器設定時，[控制台] 的 [卸載] 工具可能無法運作</span><span class="sxs-lookup"><span data-stu-id="ed643-111">Control Panel’s “Uninstall” tool may not work when you try to change AGPM Server settings</span></span>

<span data-ttu-id="ed643-112">當您嘗試變更 AGPM 服務器設定時，在 [控制台] 中用來卸載或變更程式的工具可能無法運作。</span><span class="sxs-lookup"><span data-stu-id="ed643-112">The tool in Control Panel that you use to uninstall or change a program may not work when you try to change AGPM Server settings.</span></span>

<span data-ttu-id="ed643-113">因應措施 **：** 在您嘗試使用 [控制台] 變更 AGPM 服務器設定之前，請製作 [AGPM 封存] 資料夾的複本。</span><span class="sxs-lookup"><span data-stu-id="ed643-113">**Workaround:** Before you try to change AGPM Server settings by using Control Panel, make a copy of the AGPM Archive folder.</span></span> <span data-ttu-id="ed643-114">然後，您可以使用 Setup.exe 重新安裝 AGPM 服務器，然後選擇您想要的設定參數。</span><span class="sxs-lookup"><span data-stu-id="ed643-114">You can then use Setup.exe to reinstall the AGPM Server and choose the configuration parameters that you want.</span></span>

### <span data-ttu-id="ed643-115">報告不會顯示已新增至群組原則物件的連結</span><span class="sxs-lookup"><span data-stu-id="ed643-115">Reports do not display the links that were added to a Group Policy Object</span></span>

<span data-ttu-id="ed643-116">[AGPM 設定] 和 [差異] 報告不會顯示已新增至群組原則物件（GPO）的連結。</span><span class="sxs-lookup"><span data-stu-id="ed643-116">The AGPM settings and difference reports do not display the links that were added to a Group Policy Object (GPO).</span></span>

<span data-ttu-id="ed643-117">因應措施 **：** 若要查看報表中的連結，請在 [群組原則管理主控台（GPMC）] 中選取 GPO，然後按一下右窗格中的 [**設定**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="ed643-117">**Workaround:** To view the links in the reports, select the GPO in the Group Policy Management Console (GPMC), and then click the **Settings** tab in the right pane.</span></span>

### <span data-ttu-id="ed643-118">報表不會顯示所有選項屬性設定</span><span class="sxs-lookup"><span data-stu-id="ed643-118">Reports do not display all Choice Options Properties settings</span></span>

<span data-ttu-id="ed643-119">[AGPM 設定] 和 [差異] 報告不會顯示在 [群群組原則物件編輯器] 的 [**選擇選項屬性**] 視窗中選取的所有設定。</span><span class="sxs-lookup"><span data-stu-id="ed643-119">The AGPM settings and difference reports do not display all of the settings that were selected in the **Choice Options Properties** window in the Group Policy Object Editor.</span></span>

<span data-ttu-id="ed643-120">因應措施 **：** 使用 GPMC 在報表中查看選取的 [**選擇選項] 屬性**設定。</span><span class="sxs-lookup"><span data-stu-id="ed643-120">**Workaround:** Use the GPMC to view the selected **Choice Options Properties** settings in the reports.</span></span>

### <span data-ttu-id="ed643-121">報表可能不會顯示某些瀏覽器中的 [顯示] 和 [隱藏] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="ed643-121">Reports may not display the Show and Hide tabs in certain browsers</span></span>

<span data-ttu-id="ed643-122">當您在 Google Chrome 或 Mozilla Firefox 中查看報表時，可能不會顯示 [AGPM 設定] 和 [差異] 報告右側的 [**顯示**及**隱藏**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="ed643-122">The **Show** and **Hide** tabs, on the right side of the AGPM settings and difference reports, may not appear when you view the reports in Google Chrome or Mozilla Firefox.</span></span>

<span data-ttu-id="ed643-123">因應措施 **：** 使用 Internet Explorer 瀏覽器來查看報表。</span><span class="sxs-lookup"><span data-stu-id="ed643-123">**Workaround:** View the reports by using the Internet Explorer browser.</span></span>

### <span data-ttu-id="ed643-124">AGPM 設定和差異報告可能會顯示 GPMC 報告的不同內容</span><span class="sxs-lookup"><span data-stu-id="ed643-124">AGPM settings and difference reports may show different content from GPMC reports</span></span>

<span data-ttu-id="ed643-125">AGPM 設定和差異報告可能不會顯示與 GPMC 中報表相同的內容。</span><span class="sxs-lookup"><span data-stu-id="ed643-125">The AGPM settings and difference reports may not show the same content as reports in the GPMC.</span></span>

<span data-ttu-id="ed643-126">因應措施 **：** 使用 GPMC 來查看 AGPM 報告。</span><span class="sxs-lookup"><span data-stu-id="ed643-126">**Workaround:** Use the GPMC to view the AGPM reports.</span></span>

### <span data-ttu-id="ed643-127">如果網網域控制站離線，AGPM 服務就無法啟動</span><span class="sxs-lookup"><span data-stu-id="ed643-127">AGPM Service does not start if the domain controller is offline</span></span>

<span data-ttu-id="ed643-128">當 AGPM 服務安裝在 Windows®8作業系統或更新版本作業系統的網網域控制站上時，如果網網域控制站處於離線狀態，則服務無法啟動。</span><span class="sxs-lookup"><span data-stu-id="ed643-128">When the AGPM Service is installed on a domain controller on the Windows® 8 operating systems or later operating systems, the service does not start if the domain controller is offline.</span></span>

<span data-ttu-id="ed643-129">因應措施 **：** 在網網域控制站連線之後，手動啟動 AGPM 服務。</span><span class="sxs-lookup"><span data-stu-id="ed643-129">**Workaround:** Manually start the AGPM Service after the domain controller is online.</span></span>

### <span data-ttu-id="ed643-130">從 AGPM 4.0 發行加上 hotfix1 升級 AGPM 服務器到 AGPM 4.0 SP2 時會遭到封鎖</span><span class="sxs-lookup"><span data-stu-id="ed643-130">Upgrade of AGPM Server to AGPM4.0 SP2 is blocked when you upgrade from the AGPM4.0 release plus hotfix1</span></span>

<span data-ttu-id="ed643-131">如果您嘗試將 AGPM 服務器升級至 AGPM 4.0。</span><span class="sxs-lookup"><span data-stu-id="ed643-131">If you try to upgrade the AGPM server to AGPM 4.0.</span></span> <span data-ttu-id="ed643-132">安裝 AGPM 4.0 Server 之後，然後安裝名為 AGPM 4.0 的 AGPM 熱修復程式，在 HTML 報表中報告的差異不正確（請參閱知識庫文章[2643502](https://go.microsoft.com/fwlink/?LinkId=254474)），升級失敗且無法完成。</span><span class="sxs-lookup"><span data-stu-id="ed643-132">SP2 after installing AGPM 4.0 Server and then installing the AGPM hotfix named AGPM 4.0 reports incorrect differences in the HTML report (see Knowledge Base article [2643502](https://go.microsoft.com/fwlink/?LinkId=254474)), the upgrade fails and cannot be completed.</span></span>

<span data-ttu-id="ed643-133">因應措施 **：** 卸載 AGPM 4.0 伺服器，然後安裝 AGPM 4.0 SP2。</span><span class="sxs-lookup"><span data-stu-id="ed643-133">**Workaround:** Uninstall the AGPM 4.0 Server and then install AGPM 4.0 SP2.</span></span>

### <span data-ttu-id="ed643-134">報告不會顯示組織單位連結</span><span class="sxs-lookup"><span data-stu-id="ed643-134">Reports do not display organizational unit links</span></span>

<span data-ttu-id="ed643-135">如果您將不受管理的 GPO 連結至組織單位，然後使用 AGPM 控制該 GPO，則 AGPM 設定和差異報告不會顯示組織單位連結。</span><span class="sxs-lookup"><span data-stu-id="ed643-135">If you link an uncontrolled GPO to an organizational unit and then control that GPO by using AGPM, the AGPM settings and difference reports do not display the organizational unit links.</span></span>

<span data-ttu-id="ed643-136">因應措施 **：** 在 [**變更設定**] 節點的 [**受控**] 索引標籤上，以滑鼠右鍵按一下該 GPO，按一下 [**設定**]，然後按一下 [ **gpo 連結**] 來查看組織連結。</span><span class="sxs-lookup"><span data-stu-id="ed643-136">**Workaround:** On the **Controlled** tab of the **Change Settings** node, right-click the GPO, click **Settings**, and then click **GPO Links** to view the organizational links.</span></span> <span data-ttu-id="ed643-137">或者，您可以使用 GPMC 從 [**範圍**] 索引標籤中查看 GPO 的連結。</span><span class="sxs-lookup"><span data-stu-id="ed643-137">Alternatively, you can use the GPMC to view the links to a GPO from the **Scope** tab.</span></span>

### <span data-ttu-id="ed643-138">如果您按一下 [變更]、[修復] 或 [移除 AGPM 用戶端] 對話方塊中的 [返回] 按鈕，則 AGPM 會顯示錯誤。</span><span class="sxs-lookup"><span data-stu-id="ed643-138">AGPM displays an error if you click the Back button from the Change, Repair, or Remove AGPM Client dialog box</span></span>

<span data-ttu-id="ed643-139">如果您流覽至 [控制台] 中的 [**程式和功能**]，然後選取 [ **Microsoft 高級群組原則管理–用戶端**]，當您按一下 [**修改**]，然後按一下 [**變更]、[修復] 或 [移除 AGPM 用戶端**] 對話方塊中的 [**上一頁**] 按鈕，就會顯示錯誤</span><span class="sxs-lookup"><span data-stu-id="ed643-139">If you browse to **Programs and Features** in Control Panel and then select **Microsoft Advanced Group Policy Management – Client**, AGPM displays an error if you click **Modify** and then click the **Back** button in the **Change, Repair, or Remove AGPM Client** dialog box.</span></span>

<span data-ttu-id="ed643-140">因應措施 **：** 按一下 [**取消**] 以清除錯誤，然後再次啟動程式。</span><span class="sxs-lookup"><span data-stu-id="ed643-140">**Workaround:** Click **Cancel** to clear the error, and then start the process again.</span></span> <span data-ttu-id="ed643-141">按一下 [**修改**] 後，請不要按一下 [**返回**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="ed643-141">Do not click the **Back** button after you click **Modify** .</span></span>

### <span data-ttu-id="ed643-142">當核准者部署 GPO 並輸入批註時，無法在 [歷程記錄] 視窗中顯示批註</span><span class="sxs-lookup"><span data-stu-id="ed643-142">Comment fails to appear in the History window when the Approver deploys a GPO and enters a comment</span></span>

<span data-ttu-id="ed643-143">如果擁有 Editor 角色的使用者提交部署 GPO 的要求，且擁有核准者角色的使用者接著部署該 GPO 並輸入批註，則批註將無法出現在 [歷程**記錄**] 視窗中。</span><span class="sxs-lookup"><span data-stu-id="ed643-143">If a user who has the Editor role submits a request to deploy a GPO, and the user who has the Approver role then deploys the GPO and enters a comment, the comment fails to appear in the **History** window.</span></span>

<span data-ttu-id="ed643-144">因應措施 **：** 所有.</span><span class="sxs-lookup"><span data-stu-id="ed643-144">**Workaround:** None.</span></span>

## <span data-ttu-id="ed643-145">相關主題</span><span class="sxs-lookup"><span data-stu-id="ed643-145">Related topics</span></span>


[<span data-ttu-id="ed643-146">進階群組原則管理</span><span class="sxs-lookup"><span data-stu-id="ed643-146">Advanced Group Policy Management</span></span>](index.md)

[<span data-ttu-id="ed643-147">AGPM 4.0 SP2 的新功能</span><span class="sxs-lookup"><span data-stu-id="ed643-147">What's New in AGPM 4.0 SP2</span></span>](whats-new-in-agpm-40-sp2.md)

 

 





