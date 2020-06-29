---
title: Microsoft 進階群組原則管理 4.0 SP3 版本資訊
description: Microsoft 進階群組原則管理 4.0 SP3 版本資訊
author: dansimp
ms.assetid: 955d7674-a8d9-4fc5-b18a-5a1639e38014
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 09/27/2016
ms.openlocfilehash: 6e0da04d67b3d29135071e0bc82b8e01789e4e81
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801850"
---
# <span data-ttu-id="2a512-103">Microsoft 進階群組原則管理 4.0 SP3 版本資訊</span><span class="sxs-lookup"><span data-stu-id="2a512-103">Release Notes for Microsoft Advanced Group Policy Management 4.0 SP3</span></span>


<span data-ttu-id="2a512-104">若要搜尋這些版本筆記，請按 Ctrl + F。</span><span class="sxs-lookup"><span data-stu-id="2a512-104">To search these release notes, press Ctrl+F.</span></span>

<span data-ttu-id="2a512-105">安裝 Microsoft 高級群組原則管理（AGPM）4.0 服務 Pack3 （SP3）之前，請先閱讀這些版本資訊。</span><span class="sxs-lookup"><span data-stu-id="2a512-105">Read these release notes thoroughly before you install Microsoft Advanced Group Policy Management (AGPM)4.0 Service Pack3 (SP3).</span></span> <span data-ttu-id="2a512-106">這些版本資訊包含成功安裝 AGPM 4.0 SP3 所需的資訊，且包含產品檔中不提供的資訊。</span><span class="sxs-lookup"><span data-stu-id="2a512-106">These release notes contain information that is required to successfully install AGPM4.0 SP3 and contain information that is not available in the product documentation.</span></span> <span data-ttu-id="2a512-107">如果這些版本資訊與其他 AGPM 檔之間有差異，請考慮最新的變更權威性。</span><span class="sxs-lookup"><span data-stu-id="2a512-107">If there is a difference between these release notes and other AGPM documentation, consider the latest change authoritative.</span></span> <span data-ttu-id="2a512-108">這些版本資訊取代本產品隨附的內容。</span><span class="sxs-lookup"><span data-stu-id="2a512-108">These release notes supersede the content included with this product.</span></span>

## <span data-ttu-id="2a512-109">AGPM 4.0 SP3 的已知問題</span><span class="sxs-lookup"><span data-stu-id="2a512-109">AGPM4.0 SP3 known issues</span></span>


<span data-ttu-id="2a512-110">本節說明適用于 AGPM 4.0 SP3 的已知問題。</span><span class="sxs-lookup"><span data-stu-id="2a512-110">This section describes the known issues for AGPM 4.0 SP3.</span></span>

### <span data-ttu-id="2a512-111">在 Windows 10 中 AGPM 安裝失敗</span><span class="sxs-lookup"><span data-stu-id="2a512-111">AGPM installation fails in Windows 10</span></span>

<span data-ttu-id="2a512-112">AGPM 內部在安裝期間啟用 Windows Communication Foundation （WCF）-NonHTTP-啟用功能。</span><span class="sxs-lookup"><span data-stu-id="2a512-112">AGPM internally enables the Windows Communication Foundation (WCF)-NonHTTP-Activation feature during installation.</span></span> <span data-ttu-id="2a512-113">在 Windows 10 中，WCF 現在包含在啟用 WCF NonHTTP-啟用功能之後重新開機 Windows 的需求。</span><span class="sxs-lookup"><span data-stu-id="2a512-113">In Windows 10, WCF now includes a requirement to restart Windows after enabling the WCF NonHTTP-Activation feature.</span></span> <span data-ttu-id="2a512-114">不過，目前的 AGPM 安裝程式程式碼不會處理此重新開機要求，並會在等待服務啟用時停止回應。</span><span class="sxs-lookup"><span data-stu-id="2a512-114">However, the current AGPM installer code does not handle this restart requirement and stops responding while it waits for the service to be activated.</span></span>

<span data-ttu-id="2a512-115">因應措施 **：** 在執行 AGPM 安裝程式之前，請先啟用 WCF 非 HTTP 啟用功能，然後重新開機 Windows。</span><span class="sxs-lookup"><span data-stu-id="2a512-115">**Workaround:** Before you run the AGPM installer, enable the WCF Non-HTTP Activation feature and then restart Windows.</span></span>

### <a href="" id="control-panel-s--uninstall--tool-may-not-work-when-you-try-to-change-agpm-server-settings"></a><span data-ttu-id="2a512-116">當您嘗試變更 AGPM 服務器設定時，[控制台] 的 [卸載] 工具可能無法運作</span><span class="sxs-lookup"><span data-stu-id="2a512-116">Control Panel’s “Uninstall” tool may not work when you try to change AGPM Server settings</span></span>

<span data-ttu-id="2a512-117">當您嘗試變更 AGPM 服務器設定時，在 [控制台] 中用來卸載或變更程式的工具可能無法運作。</span><span class="sxs-lookup"><span data-stu-id="2a512-117">The tool in Control Panel that you use to uninstall or change a program may not work when you try to change AGPM Server settings.</span></span>

<span data-ttu-id="2a512-118">因應措施 **：** 在您嘗試使用 [控制台] 變更 AGPM 服務器設定之前，請製作 [AGPM 封存] 資料夾的複本。</span><span class="sxs-lookup"><span data-stu-id="2a512-118">**Workaround:** Before you try to change AGPM Server settings by using Control Panel, make a copy of the AGPM Archive folder.</span></span> <span data-ttu-id="2a512-119">然後，您可以使用 Setup.exe 重新安裝 AGPM 服務器，然後選擇您想要的設定參數。</span><span class="sxs-lookup"><span data-stu-id="2a512-119">You can then use Setup.exe to reinstall the AGPM Server and choose the configuration parameters that you want.</span></span>

### <span data-ttu-id="2a512-120">報告不會顯示已新增至群組原則物件的連結</span><span class="sxs-lookup"><span data-stu-id="2a512-120">Reports do not display the links that were added to a Group Policy Object</span></span>

<span data-ttu-id="2a512-121">[AGPM 設定] 和 [差異] 報告不會顯示已新增至群組原則物件（GPO）的連結。</span><span class="sxs-lookup"><span data-stu-id="2a512-121">The AGPM settings and difference reports do not display the links that were added to a Group Policy Object (GPO).</span></span>

<span data-ttu-id="2a512-122">因應措施 **：** 若要查看報表中的連結，請在 [群組原則管理主控台（GPMC）] 中選取 GPO，然後按一下右窗格中的 [**設定**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="2a512-122">**Workaround:** To view the links in the reports, select the GPO in the Group Policy Management Console (GPMC), and then click the **Settings** tab in the right pane.</span></span>

### <span data-ttu-id="2a512-123">報表不會顯示所有選項屬性設定</span><span class="sxs-lookup"><span data-stu-id="2a512-123">Reports do not display all Choice Options Properties settings</span></span>

<span data-ttu-id="2a512-124">[AGPM 設定] 和 [差異] 報告不會顯示在 [群群組原則物件編輯器] 的 [**選擇選項屬性**] 視窗中選取的所有設定。</span><span class="sxs-lookup"><span data-stu-id="2a512-124">The AGPM settings and difference reports do not display all of the settings that were selected in the **Choice Options Properties** window in the Group Policy Object Editor.</span></span>

<span data-ttu-id="2a512-125">因應措施 **：** 使用 GPMC 在報表中查看選取的 [**選擇選項] 屬性**設定。</span><span class="sxs-lookup"><span data-stu-id="2a512-125">**Workaround:** Use the GPMC to view the selected **Choice Options Properties** settings in the reports.</span></span>

### <span data-ttu-id="2a512-126">報表可能不會顯示某些瀏覽器中的 [顯示] 和 [隱藏] 索引標籤</span><span class="sxs-lookup"><span data-stu-id="2a512-126">Reports may not display the Show and Hide tabs in certain browsers</span></span>

<span data-ttu-id="2a512-127">當您在 Google Chrome 或 Mozilla Firefox 中查看報表時，可能不會顯示 [AGPM 設定] 和 [差異] 報告右側的 [**顯示**及**隱藏**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="2a512-127">The **Show** and **Hide** tabs, on the right side of the AGPM settings and difference reports, may not appear when you view the reports in Google Chrome or Mozilla Firefox.</span></span>

<span data-ttu-id="2a512-128">因應措施 **：** 使用 Internet Explorer 瀏覽器來查看報表。</span><span class="sxs-lookup"><span data-stu-id="2a512-128">**Workaround:** View the reports by using the Internet Explorer browser.</span></span>

### <span data-ttu-id="2a512-129">AGPM 設定和差異報告可能會顯示 GPMC 報告的不同內容</span><span class="sxs-lookup"><span data-stu-id="2a512-129">AGPM settings and difference reports may show different content from GPMC reports</span></span>

<span data-ttu-id="2a512-130">AGPM 設定和差異報告可能不會顯示與 GPMC 中報表相同的內容。</span><span class="sxs-lookup"><span data-stu-id="2a512-130">The AGPM settings and difference reports may not show the same content as reports in the GPMC.</span></span>

<span data-ttu-id="2a512-131">因應措施 **：** 使用 GPMC 來查看 AGPM 報告。</span><span class="sxs-lookup"><span data-stu-id="2a512-131">**Workaround:** Use the GPMC to view the AGPM reports.</span></span>

### <span data-ttu-id="2a512-132">如果網網域控制站離線，AGPM 服務就無法啟動</span><span class="sxs-lookup"><span data-stu-id="2a512-132">AGPM Service does not start if the domain controller is offline</span></span>

<span data-ttu-id="2a512-133">當 AGPM 服務安裝在 Windows®8作業系統或更新版本作業系統的網網域控制站上時，如果網網域控制站處於離線狀態，則服務無法啟動。</span><span class="sxs-lookup"><span data-stu-id="2a512-133">When the AGPM Service is installed on a domain controller on the Windows® 8 operating systems or later operating systems, the service does not start if the domain controller is offline.</span></span>

<span data-ttu-id="2a512-134">因應措施 **：** 在網網域控制站連線之後，手動啟動 AGPM 服務。</span><span class="sxs-lookup"><span data-stu-id="2a512-134">**Workaround:** Manually start the AGPM Service after the domain controller is online.</span></span>

### <span data-ttu-id="2a512-135">從 AGPM 4.0 發行加上 hotfix1 升級 AGPM 服務器到 AGPM 4.0 SP2 時會遭到封鎖</span><span class="sxs-lookup"><span data-stu-id="2a512-135">Upgrade of AGPM Server to AGPM4.0 SP2 is blocked when you upgrade from the AGPM4.0 release plus hotfix1</span></span>

<span data-ttu-id="2a512-136">如果您嘗試將 AGPM 服務器升級至 AGPM 4.0。</span><span class="sxs-lookup"><span data-stu-id="2a512-136">If you try to upgrade the AGPM server to AGPM 4.0.</span></span> <span data-ttu-id="2a512-137">安裝 AGPM 4.0 Server 之後，然後安裝名為 AGPM 4.0 的 AGPM 熱修復程式，在 HTML 報表中報告的差異不正確（請參閱知識庫文章[2643502](https://go.microsoft.com/fwlink/?LinkId=254474)），升級失敗且無法完成。</span><span class="sxs-lookup"><span data-stu-id="2a512-137">SP2 after installing AGPM 4.0 Server and then installing the AGPM hotfix named AGPM 4.0 reports incorrect differences in the HTML report (see Knowledge Base article [2643502](https://go.microsoft.com/fwlink/?LinkId=254474)), the upgrade fails and cannot be completed.</span></span>

<span data-ttu-id="2a512-138">因應措施 **：** 卸載 AGPM 4.0 伺服器，然後安裝 AGPM 4.0 SP2。</span><span class="sxs-lookup"><span data-stu-id="2a512-138">**Workaround:** Uninstall the AGPM 4.0 Server and then install AGPM 4.0 SP2.</span></span>

### <span data-ttu-id="2a512-139">報告不會顯示組織單位連結</span><span class="sxs-lookup"><span data-stu-id="2a512-139">Reports do not display organizational unit links</span></span>

<span data-ttu-id="2a512-140">如果您將不受管理的 GPO 連結至組織單位，然後使用 AGPM 控制該 GPO，則 AGPM 設定和差異報告不會顯示組織單位連結。</span><span class="sxs-lookup"><span data-stu-id="2a512-140">If you link an uncontrolled GPO to an organizational unit and then control that GPO by using AGPM, the AGPM settings and difference reports do not display the organizational unit links.</span></span>

<span data-ttu-id="2a512-141">因應措施 **：** 在 [**變更設定**] 節點的 [**受控**] 索引標籤上，以滑鼠右鍵按一下該 GPO，按一下 [**設定**]，然後按一下 [ **gpo 連結**] 來查看組織連結。</span><span class="sxs-lookup"><span data-stu-id="2a512-141">**Workaround:** On the **Controlled** tab of the **Change Settings** node, right-click the GPO, click **Settings**, and then click **GPO Links** to view the organizational links.</span></span> <span data-ttu-id="2a512-142">或者，您可以使用 GPMC 從 [**範圍**] 索引標籤中查看 GPO 的連結。</span><span class="sxs-lookup"><span data-stu-id="2a512-142">Alternatively, you can use the GPMC to view the links to a GPO from the **Scope** tab.</span></span>

### <span data-ttu-id="2a512-143">如果您按一下 [變更]、[修復] 或 [移除 AGPM 用戶端] 對話方塊中的 [返回] 按鈕，則 AGPM 會顯示錯誤。</span><span class="sxs-lookup"><span data-stu-id="2a512-143">AGPM displays an error if you click the Back button from the Change, Repair, or Remove AGPM Client dialog box</span></span>

<span data-ttu-id="2a512-144">如果您流覽至 [控制台] 中的 [**程式和功能**]，然後選取 [ **Microsoft 高級群組原則管理–用戶端**]，當您按一下 [**修改**]，然後按一下 [**變更]、[修復] 或 [移除 AGPM 用戶端**] 對話方塊中的 [**上一頁**] 按鈕，就會顯示錯誤</span><span class="sxs-lookup"><span data-stu-id="2a512-144">If you browse to **Programs and Features** in Control Panel and then select **Microsoft Advanced Group Policy Management – Client**, AGPM displays an error if you click **Modify** and then click the **Back** button in the **Change, Repair, or Remove AGPM Client** dialog box.</span></span>

<span data-ttu-id="2a512-145">因應措施 **：** 按一下 [**取消**] 以清除錯誤，然後再次啟動程式。</span><span class="sxs-lookup"><span data-stu-id="2a512-145">**Workaround:** Click **Cancel** to clear the error, and then start the process again.</span></span> <span data-ttu-id="2a512-146">按一下 [**修改**] 後，請不要按一下 [**返回**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="2a512-146">Do not click the **Back** button after you click **Modify** .</span></span>

### <span data-ttu-id="2a512-147">當核准者部署 GPO 並輸入批註時，無法在 [歷程記錄] 視窗中顯示批註</span><span class="sxs-lookup"><span data-stu-id="2a512-147">Comment fails to appear in the History window when the Approver deploys a GPO and enters a comment</span></span>

<span data-ttu-id="2a512-148">如果擁有 Editor 角色的使用者提交部署 GPO 的要求，且擁有核准者角色的使用者接著部署該 GPO 並輸入批註，則批註將無法出現在 [歷程**記錄**] 視窗中。</span><span class="sxs-lookup"><span data-stu-id="2a512-148">If a user who has the Editor role submits a request to deploy a GPO, and the user who has the Approver role then deploys the GPO and enters a comment, the comment fails to appear in the **History** window.</span></span>

<span data-ttu-id="2a512-149">因應措施 **：** 所有.</span><span class="sxs-lookup"><span data-stu-id="2a512-149">**Workaround:** None.</span></span>

### <span data-ttu-id="2a512-150">已新增可覆寫刪除 GPO 許可權變更之 AGPM 預設行為的機制</span><span class="sxs-lookup"><span data-stu-id="2a512-150">Added mechanism to override AGPM default behavior of removing GPO permission changes</span></span>

<span data-ttu-id="2a512-151">從 HF02，AGPM 已新增登錄機碼，以啟用覆寫預設的 AGPM GPO 許可權行為。</span><span class="sxs-lookup"><span data-stu-id="2a512-151">As of HF02, AGPM has added a registry key to enable overriding the default AGPM GPO permission behavior.</span></span> <span data-ttu-id="2a512-152">如需詳細資訊，請參閱[已忽略透過 AGPM 對群組原則物件許可權所做的變更](https://support.microsoft.com/kb/3174540)</span><span class="sxs-lookup"><span data-stu-id="2a512-152">For more information, please see [Changes to Group Policy object permissions through AGPM are ignored](https://support.microsoft.com/kb/3174540)</span></span>

## <span data-ttu-id="2a512-153">相關主題</span><span class="sxs-lookup"><span data-stu-id="2a512-153">Related topics</span></span>


[<span data-ttu-id="2a512-154">進階群組原則管理</span><span class="sxs-lookup"><span data-stu-id="2a512-154">Advanced Group Policy Management</span></span>](index.md)

[<span data-ttu-id="2a512-155">AGPM 4.0 SP3 的新功能</span><span class="sxs-lookup"><span data-stu-id="2a512-155">What's New in AGPM 4.0 SP3</span></span>](whats-new-in-agpm-40-sp3.md)

 

 





