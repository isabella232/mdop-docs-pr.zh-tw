---
title: 如何修改現有的虛擬應用程式封裝 (App-V 4.6 SP1)
description: 如何修改現有的虛擬應用程式封裝 (App-V 4.6 SP1)
author: dansimp
ms.assetid: f43a9927-4325-4b2d-829f-3068e4e84349
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f0e9d45a32afa240ce7f6fb2ee5dfbc51889c1fa
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801257"
---
# <span data-ttu-id="06754-103">如何修改現有的虛擬應用程式封裝 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="06754-103">How to Modify an Existing Virtual Application Package (App-V 4.6 SP1)</span></span>


<span data-ttu-id="06754-104">使用下列程式來修改現有的虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="06754-104">Use the following procedures to modify an existing virtual application package.</span></span> <span data-ttu-id="06754-105">您可以使用這些程式來執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="06754-105">You can use these procedures to:</span></span>

-   <span data-ttu-id="06754-106">更新屬於現有虛擬應用程式套件的應用程式。</span><span class="sxs-lookup"><span data-stu-id="06754-106">Update an application that is part of an existing virtual application package.</span></span> <span data-ttu-id="06754-107">若要執行這項工作，請使用這份檔中的「**更新現有應用程式套件中的應用程式」程式**。</span><span class="sxs-lookup"><span data-stu-id="06754-107">To perform this task, use the procedure **"To update an application in an existing application package"** in this document.</span></span>

-   <span data-ttu-id="06754-108">修改與現有虛擬應用程式套件相關聯的屬性。</span><span class="sxs-lookup"><span data-stu-id="06754-108">Modify the properties associated with an existing virtual application package.</span></span> <span data-ttu-id="06754-109">若要執行這項工作，請使用這份檔中的「**修改現有虛擬應用程式套件所關聯的屬性**」程式。</span><span class="sxs-lookup"><span data-stu-id="06754-109">To perform this task, use the procedure **"To modify the properties associated with an existing virtual application package"** in this document.</span></span>

-   <span data-ttu-id="06754-110">將新的應用程式新增至現有的虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="06754-110">Add a new application to an existing virtual application package.</span></span> <span data-ttu-id="06754-111">若要執行這項工作，請使用這份檔中的 [**將新的應用程式新增至現有的虛擬應用程式套件]** 程式。</span><span class="sxs-lookup"><span data-stu-id="06754-111">To perform this task, use the procedure **"To add a new application to an existing virtual application package"** in this document.</span></span>

<span data-ttu-id="06754-112">您必須已安裝 App-v 排序器，才能修改虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="06754-112">You must have the App-V Sequencer installed to modify a virtual application package.</span></span> <span data-ttu-id="06754-113">如需安裝 App-v 排序器的詳細資訊，請參閱[如何安裝 Sequencer （app-v 4.6 SP1）](how-to-install-the-sequencer---app-v-46-sp1-.md)。</span><span class="sxs-lookup"><span data-stu-id="06754-113">For more information about installing the App-V Sequencer, see [How to Install the Sequencer (App-V 4.6 SP1)](how-to-install-the-sequencer---app-v-46-sp1-.md).</span></span>

**<span data-ttu-id="06754-114">更新現有虛擬應用程式套件中的應用程式</span><span class="sxs-lookup"><span data-stu-id="06754-114">To update an application in an existing virtual application package</span></span>**

1.  <span data-ttu-id="06754-115">若要啟動 app-v 排序器，請在執行 app-v 排序器的電腦上，按一下 [**開始**  /  **所有程式**]  /  **microsoft application virtualization**  /  **microsoft application virtualization 排序**器。</span><span class="sxs-lookup"><span data-stu-id="06754-115">To start the App-V Sequencer, on the computer that is running the App-V Sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="06754-116">在 App-v 排序器中，按一下 [**修改現有的虛擬應用程式套件**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="06754-116">In the App-V Sequencer, click **Modify an Existing Virtual Application Package**, and then click **Next**.</span></span>

3.  <span data-ttu-id="06754-117">在 [**選取**工作] 頁面上，按一下 [**在現有套件中更新應用程式**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="06754-117">On the **Select Task** page, click **Update Application in Existing Package**, and then click **Next**.</span></span>

4.  <span data-ttu-id="06754-118">在 [**選取套件**] 頁面上，按一下 **[流覽]** ，找出包含您要更新之應用程式的虛擬應用程式套件，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="06754-118">On the **Select Package** page, click **Browse** to locate the virtual application package that contains the application that you want to update, and then click **Next**.</span></span>

5.  <span data-ttu-id="06754-119">在 [**準備電腦**] 頁面上，查看可能導致應用程式更新失敗的問題，或應用程式更新包含不必要的資料。</span><span class="sxs-lookup"><span data-stu-id="06754-119">On the **Prepare Computer** page, review the issues that could cause the application update to fail, or for the application update to contain unnecessary data.</span></span> <span data-ttu-id="06754-120">我們強烈建議您在繼續進行之前先解決所有潛在問題。</span><span class="sxs-lookup"><span data-stu-id="06754-120">We strongly recommend that you resolve all potential issues before you continue.</span></span> <span data-ttu-id="06754-121">修正衝突之後，若要更新所顯示的資訊，**請按一下 [** 重新整理]。</span><span class="sxs-lookup"><span data-stu-id="06754-121">After you have fixed the conflicts, to update the information that is displayed, click **Refresh**.</span></span> <span data-ttu-id="06754-122">解決所有可能的問題之後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="06754-122">After you have resolved all potential issues, click **Next**.</span></span>

    <span data-ttu-id="06754-123">**重要** 如果您需要停用病毒掃描軟體，請掃描執行 sequencer 的電腦，以確保不會在套件中新增不需要的或惡意的檔案。</span><span class="sxs-lookup"><span data-stu-id="06754-123">**Important** If you are required to disable virus scanning software, scan the computer running the sequencer to ensure that no unwanted or malicious files are added to the package.</span></span>

     

6.  <span data-ttu-id="06754-124">在 [**選取安裝程式**] 頁面上，按一下 **[流覽]** ，然後指定應用程式的更新安裝檔案。</span><span class="sxs-lookup"><span data-stu-id="06754-124">On the **Select Installer** page, click **Browse** and specify the update installation file for the application.</span></span> <span data-ttu-id="06754-125">如果更新沒有關聯的安裝程式檔案，且您打算手動執行所有安裝步驟，請選取 [**選取此選項以執行自訂安裝**] 核取方塊，然後按一下 [**下一步]**。</span><span class="sxs-lookup"><span data-stu-id="06754-125">If the update does not have an associated installer file and you plan to run all installation steps manually, select the **Select this option to perform a custom installation** check box, and then click **Next**.</span></span>

7.  <span data-ttu-id="06754-126">在 [**安裝**] 頁面上，當排序器和應用程式安裝程式準備好時，請安裝應用程式更新，讓排序器可以監視安裝程式。</span><span class="sxs-lookup"><span data-stu-id="06754-126">On the **Installation** page, when the sequencer and application installer are ready, install the application update so the sequencer can monitor the installation process.</span></span> <span data-ttu-id="06754-127">如果安裝時必須執行其他安裝檔案，請按一下 [**執行**]，然後找出並執行其他安裝檔案。</span><span class="sxs-lookup"><span data-stu-id="06754-127">If additional installation files must be run as part of the installation, click **Run** and locate and run the additional installation files.</span></span> <span data-ttu-id="06754-128">完成安裝後，請選取 [**我已完成安裝**]。</span><span class="sxs-lookup"><span data-stu-id="06754-128">When you are finished with the installation, select **I am finished installing**.</span></span> <span data-ttu-id="06754-129">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="06754-129">Click **Next**.</span></span>

    <span data-ttu-id="06754-130">**記事** 排序器會監視執行排序器的電腦所做的所有變更和安裝，包括在順序嚮導之外執行的變更和安裝。</span><span class="sxs-lookup"><span data-stu-id="06754-130">**Note** The sequencer monitors all changes and installations to the computer running the sequencer, including the changes and installations that are performed outside of the sequencing wizard.</span></span>

     

8.  <span data-ttu-id="06754-131">在 [**安裝報告**] 頁面上，您可以查看您剛更新之虛擬應用程式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="06754-131">On the **Installation Report** page, you can review information about the virtual application you just updated.</span></span> <span data-ttu-id="06754-132">如需**其他資訊**所顯示之資訊的詳細說明，請按兩下該事件。</span><span class="sxs-lookup"><span data-stu-id="06754-132">For a more detailed explanation about the information displayed in **Additional Information**, double-click the event.</span></span> <span data-ttu-id="06754-133">審閱資訊之後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="06754-133">After you have reviewed the information, click **Next**.</span></span>

9.  <span data-ttu-id="06754-134">在 [**流式處理**] 頁面上，執行每個程式，讓它能在目的電腦上優化並更有效率地執行。</span><span class="sxs-lookup"><span data-stu-id="06754-134">On the **Streaming** page, run each program so that it can be optimized and run more efficiently on target computers.</span></span> <span data-ttu-id="06754-135">可能需要幾分鐘的時間，所有應用程式才會執行。</span><span class="sxs-lookup"><span data-stu-id="06754-135">It can take several minutes for all the applications to run.</span></span> <span data-ttu-id="06754-136">在所有應用程式都已執行之後，請關閉每個應用程式，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="06754-136">After all applications have run, close each of the applications, and then click **Next**.</span></span>

    <span data-ttu-id="06754-137">**記事** 如果您想要在此步驟中停止載入應用程式，請在 [**應用程式啟動**] 對話方塊中，按一下 [**停止**]，然後按一下下列其中一個選項： [**停止所有應用程式**] 或 [**僅停止此應用程式**]，視您想要的專案而定。</span><span class="sxs-lookup"><span data-stu-id="06754-137">**Note** If you want to stop an application from loading during this step, in the **Application Launch** dialog box, click **Stop**, and then click one of the following options, **Stop all applications** or **Stop this application only**, depending on what you want.</span></span>

     

10. <span data-ttu-id="06754-138">在 [**建立套件**] 頁面上，若要修改套件但不儲存，請選取 [**繼續使用套件編輯器來修改套件但不儲存**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="06754-138">On the **Create Package** page, to modify the package without saving it, select the **Continue to modify package without saving using the package editor** check box.</span></span> <span data-ttu-id="06754-139">當您選取此選項時，會開啟 Sequencer 視窗中的套件，讓您可以在儲存套件之前加以修改。</span><span class="sxs-lookup"><span data-stu-id="06754-139">When you select this option, the package in the Sequencer console opens so that you can modify the package before it is saved.</span></span> <span data-ttu-id="06754-140">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="06754-140">Click **Next**.</span></span>

    <span data-ttu-id="06754-141">若要立即儲存套件，請選取 [**立即儲存套件**] 的預設值。</span><span class="sxs-lookup"><span data-stu-id="06754-141">To save the package immediately, select the default **Save the package now**.</span></span> <span data-ttu-id="06754-142">新增將與套件相關聯的選擇性**批註**。</span><span class="sxs-lookup"><span data-stu-id="06754-142">Add optional **Comments** that will be associated with the package.</span></span> <span data-ttu-id="06754-143">若要識別套件的版本及其他資訊，可以使用 [批註]。</span><span class="sxs-lookup"><span data-stu-id="06754-143">Comments are useful for identifying version and other information about the package.</span></span> <span data-ttu-id="06754-144">也會顯示預設的**儲存位置**。</span><span class="sxs-lookup"><span data-stu-id="06754-144">The default **Save Location** is also displayed.</span></span> <span data-ttu-id="06754-145">若要變更預設位置，請按一下 **[流覽]** ，然後指定新的位置。</span><span class="sxs-lookup"><span data-stu-id="06754-145">To change the default location, click **Browse** and specify the new location.</span></span> <span data-ttu-id="06754-146">隨即會顯示未壓縮的套件大小。</span><span class="sxs-lookup"><span data-stu-id="06754-146">The uncompressed package size is displayed.</span></span> <span data-ttu-id="06754-147">如果套件大小超過 4 GB （未壓縮），且您打算將套件資料流程資料流至目的電腦，您必須選取 [**壓縮套件**]，然後按一下 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="06754-147">If the package size exceeds 4 GB (uncompressed) and you plan to stream the package to target computers, you must select **Compress Package**, and then click **Create**.</span></span>

11. <span data-ttu-id="06754-148">在**完成**頁面上，按一下 [**關閉**] 以關閉嚮導。</span><span class="sxs-lookup"><span data-stu-id="06754-148">On the **Completion** page, click **Close** to close the wizard.</span></span> <span data-ttu-id="06754-149">套件現在可在 sequencer 中取得。</span><span class="sxs-lookup"><span data-stu-id="06754-149">The package is now available in the sequencer.</span></span>

**<span data-ttu-id="06754-150">修改與現有虛擬應用程式套件相關聯的屬性</span><span class="sxs-lookup"><span data-stu-id="06754-150">To modify the properties associated with an existing virtual application package</span></span>**

1.  <span data-ttu-id="06754-151">若要啟動 app-v 排序器，請在執行 app-v 排序器的電腦上，按一下 [**開始**  /  **所有程式**]  /  **microsoft application virtualization**  /  **microsoft application virtualization 排序**器。</span><span class="sxs-lookup"><span data-stu-id="06754-151">To start the App-V Sequencer, on the computer that is running the App-V Sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="06754-152">在 App-v 排序器中，按一下 [**修改現有的虛擬應用程式套件**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="06754-152">In the App-V Sequencer, click **Modify an Existing Virtual Application Package**, and then click **Next**.</span></span>

3.  <span data-ttu-id="06754-153">在 [**選取**工作] 頁面上，按一下 [**編輯套件**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="06754-153">On the **Select Task** page, click **Edit Package**, and then click **Next**.</span></span>

4.  <span data-ttu-id="06754-154">在 [**選取套件**] 頁面上，按一下 **[流覽]** ，找出包含您要修改之應用程式屬性的虛擬應用程式套件，然後按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="06754-154">On the **Select Package** page, click **Browse** to locate the virtual application package that contains the application properties that you want to modify, and then click **Edit**.</span></span>

5.  <span data-ttu-id="06754-155">在 Sequencer 主控台中，您可以執行下列任何一項工作：</span><span class="sxs-lookup"><span data-stu-id="06754-155">In the Sequencer console, you can perform any of the following tasks:</span></span>

    -   <span data-ttu-id="06754-156">[查看套件屬性]。</span><span class="sxs-lookup"><span data-stu-id="06754-156">View package properties.</span></span>

    -   <span data-ttu-id="06754-157">[查看套件變更歷程記錄]。</span><span class="sxs-lookup"><span data-stu-id="06754-157">View package change history.</span></span>

    -   <span data-ttu-id="06754-158">[查看關聯的套件檔案]。</span><span class="sxs-lookup"><span data-stu-id="06754-158">View associated package files.</span></span>

    -   <span data-ttu-id="06754-159">編輯註冊表設定。</span><span class="sxs-lookup"><span data-stu-id="06754-159">Edit registry settings.</span></span>

    -   <span data-ttu-id="06754-160">查看其他套件設定（除了作業系統檔案屬性之外）。</span><span class="sxs-lookup"><span data-stu-id="06754-160">Review additional package settings (except operating system file properties).</span></span>

    -   <span data-ttu-id="06754-161">建立相關聯的 Windows Installer （MSI）。</span><span class="sxs-lookup"><span data-stu-id="06754-161">Create an associated Windows Installer (MSI).</span></span>

    -   <span data-ttu-id="06754-162">[修改 OSD 檔案]。</span><span class="sxs-lookup"><span data-stu-id="06754-162">Modify OSD file.</span></span>

    -   <span data-ttu-id="06754-163">壓縮和解壓縮套件。</span><span class="sxs-lookup"><span data-stu-id="06754-163">Compress and uncompress package.</span></span>

    -   <span data-ttu-id="06754-164">新增檔案類型關聯。</span><span class="sxs-lookup"><span data-stu-id="06754-164">Add file type associations.</span></span>

    -   <span data-ttu-id="06754-165">設定虛擬化登錄機碼的狀態（覆寫或合併）。</span><span class="sxs-lookup"><span data-stu-id="06754-165">Set virtualized registry key state (override or merge).</span></span>

    -   <span data-ttu-id="06754-166">設定虛擬化資料夾的狀態。</span><span class="sxs-lookup"><span data-stu-id="06754-166">Set virtualized folder state.</span></span>

    -   <span data-ttu-id="06754-167">編輯虛擬檔案系統對應。</span><span class="sxs-lookup"><span data-stu-id="06754-167">Edit virtual file system mappings.</span></span>

6.  <span data-ttu-id="06754-168">當您完成修改套件屬性時，**請按一下 [**  /  **儲存**] 以儲存套件。</span><span class="sxs-lookup"><span data-stu-id="06754-168">When you have finished modifying the package properties, click **File** / **Save** to save the package,.</span></span>

**<span data-ttu-id="06754-169">將新的應用程式新增至現有的虛擬應用程式套件</span><span class="sxs-lookup"><span data-stu-id="06754-169">To add a new application to an existing virtual application package</span></span>**

1.  <span data-ttu-id="06754-170">若要啟動 app-v 排序器，請在執行 app-v 排序器的電腦上，按一下 [**開始**  /  **所有程式**]  /  **microsoft application virtualization**  /  **microsoft application virtualization 排序**器。</span><span class="sxs-lookup"><span data-stu-id="06754-170">To start the App-V Sequencer, on the computer that is running the App-V Sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="06754-171">在 App-v 排序器中，按一下 [**修改現有的虛擬應用程式套件**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="06754-171">In the App-V Sequencer, click **Modify an Existing Virtual Application Package**, and then click **Next**.</span></span>

3.  <span data-ttu-id="06754-172">在 [**選取**工作] 頁面上，按一下 [新增**應用程式**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="06754-172">On the **Select Task** page, click **Add New Application**, and then click **Next**.</span></span>

4.  <span data-ttu-id="06754-173">在 [**選取套件**] 頁面上，按一下 **[流覽]** ，找出您要新增應用程式的虛擬應用程式套件，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="06754-173">On the **Select Package** page, click **Browse** to locate the virtual application package that you want to add the application to, and then click **Next**.</span></span>

5.  <span data-ttu-id="06754-174">在 [**準備電腦**] 頁面上，查看可能導致套件建立失敗的問題，或更新以包含不必要的資料。</span><span class="sxs-lookup"><span data-stu-id="06754-174">On the **Prepare Computer** page, review the issues that could cause the package creation to fail, or for the update to contain unnecessary data.</span></span> <span data-ttu-id="06754-175">我們強烈建議您在繼續進行之前先解決所有潛在問題。</span><span class="sxs-lookup"><span data-stu-id="06754-175">We strongly recommend that you resolve all potential issues before you continue.</span></span> <span data-ttu-id="06754-176">修正衝突之後，若要更新所顯示的資訊，**請按一下 [** 重新整理]。</span><span class="sxs-lookup"><span data-stu-id="06754-176">After you have fixed the conflicts, to update the information that is displayed, click **Refresh**.</span></span> <span data-ttu-id="06754-177">解決所有可能的問題之後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="06754-177">After you have resolved all potential issues, click **Next**.</span></span>

    <span data-ttu-id="06754-178">**重要** 如果您需要停用病毒掃描軟體，請掃描執行 sequencer 的電腦，以確保不會在套件中新增不需要的或惡意的檔案。</span><span class="sxs-lookup"><span data-stu-id="06754-178">**Important** If you are required to disable virus scanning software, scan the computer running the sequencer to ensure that no unwanted or malicious files can be added to the package.</span></span>

     

6.  <span data-ttu-id="06754-179">在 [**選取安裝程式**] 頁面上，按一下 **[流覽]** ，然後指定應用程式的安裝檔。</span><span class="sxs-lookup"><span data-stu-id="06754-179">On the **Select Installer** page, click **Browse** and specify the installation file for the application.</span></span> <span data-ttu-id="06754-180">如果應用程式沒有關聯的安裝程式檔案，且您打算手動執行所有安裝步驟，請選取 [**選取此選項以執行自訂安裝**] 核取方塊，然後按一下 [**下一步]**。</span><span class="sxs-lookup"><span data-stu-id="06754-180">If the application does not have an associated installer file and you plan to run all installation steps manually, select the **Select this option to perform a custom installation** check box, and then click **Next**.</span></span>

7.  <span data-ttu-id="06754-181">在 [**安裝**] 頁面上，當排序器和應用程式安裝程式準備好時，請安裝應用程式，讓排序器可以監視安裝程式。</span><span class="sxs-lookup"><span data-stu-id="06754-181">On the **Installation** page, when the sequencer and application installer are ready, install the application so the sequencer can monitor the installation process.</span></span> <span data-ttu-id="06754-182">如果安裝時必須執行其他安裝檔案，請按一下 [**執行**]，然後找出並執行其他安裝檔案。</span><span class="sxs-lookup"><span data-stu-id="06754-182">If additional installation files must be run as part of the installation, click **Run**, and locate and run the additional installation files.</span></span> <span data-ttu-id="06754-183">完成安裝後，請選取 [**我已完成安裝**]。</span><span class="sxs-lookup"><span data-stu-id="06754-183">When you are finished with the installation, select **I am finished installing**.</span></span> <span data-ttu-id="06754-184">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="06754-184">Click **Next**.</span></span> <span data-ttu-id="06754-185">在 [**流覽資料夾**] 對話方塊中，指定將安裝應用程式的主要目錄。</span><span class="sxs-lookup"><span data-stu-id="06754-185">In the **Browse for Folder** dialog box, specify the primary directory where the application will be installed.</span></span> <span data-ttu-id="06754-186">這應該是新的位置，因此您不會覆寫現有的虛擬應用程式套件版本。</span><span class="sxs-lookup"><span data-stu-id="06754-186">This should be a new location so that you do not overwrite the existing version of the virtual application package.</span></span>

    <span data-ttu-id="06754-187">**記事** 排序器會監視執行排序器的電腦的所有變更和安裝，包括在順序嚮導之外執行的變更和安裝。</span><span class="sxs-lookup"><span data-stu-id="06754-187">**Note** All changes and installations to the computer running the sequencer are monitored by the sequencer, including the changes and installations that are performed outside of the sequencing wizard.</span></span>

     

8.  <span data-ttu-id="06754-188">在 [**設定軟體**] 頁面上，選擇性地執行套件中包含的程式。</span><span class="sxs-lookup"><span data-stu-id="06754-188">On the **Configure Software** page, optionally run the programs contained in the package.</span></span> <span data-ttu-id="06754-189">此步驟可協助您完成在您部署並在目的電腦上執行套件之前，執行應用程式所需的任何相關授權或配置工作。</span><span class="sxs-lookup"><span data-stu-id="06754-189">This step helps complete any associated license or configuration tasks that are required to run the application before you deploy and run the package on target computers.</span></span> <span data-ttu-id="06754-190">若要同時執行所有程式，請選取至少一個程式，然後按一下 [**全部執行**]。</span><span class="sxs-lookup"><span data-stu-id="06754-190">To run all the programs at the same time, select at least one program, and then click **Run All**.</span></span> <span data-ttu-id="06754-191">若要執行特定程式，請選取您要執行的程式或程式，然後按一下 [**執行選取**的專案]。</span><span class="sxs-lookup"><span data-stu-id="06754-191">To run specific programs, select the program or programs you want to run, and then click **Run Selected**.</span></span> <span data-ttu-id="06754-192">完成所需的配置工作，然後關閉應用程式。</span><span class="sxs-lookup"><span data-stu-id="06754-192">Complete the required configuration tasks and then close the applications.</span></span> <span data-ttu-id="06754-193">所有程式都可能需要幾分鐘的時間才能執行。</span><span class="sxs-lookup"><span data-stu-id="06754-193">It can take several minutes for all programs to run.</span></span> <span data-ttu-id="06754-194">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="06754-194">Click **Next**.</span></span>

9.  <span data-ttu-id="06754-195">在 [**安裝報告**] 頁面上，您可以查看您剛更新之虛擬應用程式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="06754-195">On the **Installation Report** page, you can review information about the virtual application you just updated.</span></span> <span data-ttu-id="06754-196">如需**其他資訊**所顯示之資訊的詳細說明，請按兩下該事件。</span><span class="sxs-lookup"><span data-stu-id="06754-196">For a more detailed explanation about the information displayed in **Additional Information**, double-click the event.</span></span> <span data-ttu-id="06754-197">審閱資訊之後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="06754-197">After you have reviewed the information, click **Next**.</span></span>

10. <span data-ttu-id="06754-198">如果您已完成安裝並設定虛擬應用程式，請在 [**自訂**] 頁面上選取 [**立即停止**]，然後跳至此程式的步驟14。</span><span class="sxs-lookup"><span data-stu-id="06754-198">On the **Customize** page, if you are finished installing and configuring the virtual application, select **Stop now** and skip to step 14 of this procedure.</span></span> <span data-ttu-id="06754-199">如果您想要自訂以下清單中的任何專案，請按一下 [**自訂**]。</span><span class="sxs-lookup"><span data-stu-id="06754-199">If you want to customize any of the items in the following list, click **Customize**.</span></span>

    -   <span data-ttu-id="06754-200">編輯與應用程式相關聯的檔案類型關聯。</span><span class="sxs-lookup"><span data-stu-id="06754-200">Edit the file type associations associated with an application.</span></span>

    -   <span data-ttu-id="06754-201">準備虛擬套件以進行流式處理。</span><span class="sxs-lookup"><span data-stu-id="06754-201">Prepare the virtual package for streaming.</span></span> <span data-ttu-id="06754-202">[資料流程] 可改善虛擬應用程式套件在目的電腦上執行時的體驗。</span><span class="sxs-lookup"><span data-stu-id="06754-202">Streaming improves the experience when the virtual application package is run on target computers.</span></span>

    <span data-ttu-id="06754-203">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="06754-203">Click **Next**.</span></span>

11. <span data-ttu-id="06754-204">在 [**編輯快速鍵**] 頁面上，您可以選擇性地設定將與套件中各種應用程式相關聯的檔案類型關聯（FTA）。</span><span class="sxs-lookup"><span data-stu-id="06754-204">On the **Edit Shortcuts** page, you can optionally configure the file type associations (FTA) that will be associated with the various applications in the package.</span></span> <span data-ttu-id="06754-205">若要建立新的 FTA，請在左窗格中選取並展開您要自訂的應用程式，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="06754-205">To create a new FTA, select and expand the application that you want to customize in the left pane, and then click **Add**.</span></span> <span data-ttu-id="06754-206">在 [**新增檔案類型關聯**] 對話方塊中，為新的 FTA 提供必要的資訊。</span><span class="sxs-lookup"><span data-stu-id="06754-206">In the **Add File Type Association** dialog box, provide the necessary information for the new FTA.</span></span> <span data-ttu-id="06754-207">若要查看與應用程式相關聯的快捷方式資訊，請選取 [**快捷方式**] 核取方塊，然後在 [**位置**] 窗格中，您可以查看圖示檔資訊。</span><span class="sxs-lookup"><span data-stu-id="06754-207">To review the shortcut information associated with an application, under the application, select the **Shortcuts** check box, and in the **Location** pane, you can review the icon file information.</span></span> <span data-ttu-id="06754-208">若要編輯現有的 FTA，請按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="06754-208">To edit an existing FTA, click **Edit**.</span></span> <span data-ttu-id="06754-209">若要移除 FTA，請選取 FTA，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="06754-209">To remove an FTA, select the FTA, and then click **Remove**.</span></span> <span data-ttu-id="06754-210">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="06754-210">Click **Next**.</span></span>

12. <span data-ttu-id="06754-211">在 [**流式處理**] 頁面上，執行每個程式，讓它能在目的電腦上優化並更有效率地執行。</span><span class="sxs-lookup"><span data-stu-id="06754-211">On the **Streaming** page, run each program so that it can be optimized and run more efficiently on target computers.</span></span> <span data-ttu-id="06754-212">可能需要幾分鐘的時間，所有應用程式才會執行。</span><span class="sxs-lookup"><span data-stu-id="06754-212">It can take several minutes for all the applications to run.</span></span> <span data-ttu-id="06754-213">在所有應用程式都已執行之後，請關閉每個應用程式，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="06754-213">After all applications have run, close each of the applications, and then click **Next**.</span></span>

    <span data-ttu-id="06754-214">**記事** 如果您想要在此步驟期間停止載入應用程式，請在 [**應用程式啟動**] 對話方塊中，按一下 [**停止**]，然後選取 [**停止所有應用程式**] 或 [**僅停止此應用程式**] 核取方塊（視您想要的專案而定）。</span><span class="sxs-lookup"><span data-stu-id="06754-214">**Note** If you want to stop an application from loading during this step, in the **Application Launch** dialog box, click **Stop** and select either the **Stop all applications** or the **Stop this application only** check box, depending on what you want.</span></span>

     

13. <span data-ttu-id="06754-215">在 [**建立套件**] 頁面上，選取 [**繼續使用套件編輯器來修改套件但不儲存**] 核取方塊，即可修改套件而不儲存。</span><span class="sxs-lookup"><span data-stu-id="06754-215">On the **Create Package** page, select the **Continue to modify package without saving using the package editor** check box, to modify the package without saving it.</span></span> <span data-ttu-id="06754-216">當您選取此選項時，會開啟 sequencer 視窗中的套件，讓您可以在儲存套件之前加以修改。</span><span class="sxs-lookup"><span data-stu-id="06754-216">When you select this option, the package in the sequencer console opens so that you can modify the package before it is saved.</span></span> <span data-ttu-id="06754-217">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="06754-217">Click **Next**.</span></span>

    <span data-ttu-id="06754-218">選取 [**立即儲存套件**]，立即儲存套件。</span><span class="sxs-lookup"><span data-stu-id="06754-218">Select the default **Save the package now**, to save the package immediately.</span></span> <span data-ttu-id="06754-219">新增將與套件相關聯的選擇性**批註**。</span><span class="sxs-lookup"><span data-stu-id="06754-219">Add optional **Comments** that will be associated with the package.</span></span> <span data-ttu-id="06754-220">若要識別套件的版本及其他資訊，可以使用 [批註]。</span><span class="sxs-lookup"><span data-stu-id="06754-220">Comments are useful for identifying version and other information about the package.</span></span> <span data-ttu-id="06754-221">也會顯示預設的**儲存位置**。</span><span class="sxs-lookup"><span data-stu-id="06754-221">The default **Save Location** is also displayed.</span></span> <span data-ttu-id="06754-222">若要變更預設位置，請按一下 **[流覽]** ，然後指定新的位置。</span><span class="sxs-lookup"><span data-stu-id="06754-222">To change the default location, click **Browse** and specify the new location.</span></span> <span data-ttu-id="06754-223">隨即會顯示未壓縮的套件大小。</span><span class="sxs-lookup"><span data-stu-id="06754-223">The uncompressed package size is displayed.</span></span> <span data-ttu-id="06754-224">如果套件大小超過 4 GB （未壓縮），且您打算將套件資料流程資料流至目的電腦，您必須選取 [**壓縮套件**]。</span><span class="sxs-lookup"><span data-stu-id="06754-224">If the package size exceeds 4 GB (uncompressed) and you plan to stream the package to target computers, you must select **Compress Package**.</span></span> <span data-ttu-id="06754-225">按一下 \[建立\]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="06754-225">Click **Create**.</span></span>

14. <span data-ttu-id="06754-226">在**完成**頁面上，按一下**關閉**。</span><span class="sxs-lookup"><span data-stu-id="06754-226">On the **Completion** page, click **Close**.</span></span> <span data-ttu-id="06754-227">套件現在可在 sequencer 中取得。</span><span class="sxs-lookup"><span data-stu-id="06754-227">The package is now available in the sequencer.</span></span>

## <span data-ttu-id="06754-228">相關主題</span><span class="sxs-lookup"><span data-stu-id="06754-228">Related topics</span></span>


[<span data-ttu-id="06754-229">Application Virtualization Sequencer 的工作 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="06754-229">Tasks for the Application Virtualization Sequencer (App-V 4.6 SP1)</span></span>](tasks-for-the-application-virtualization-sequencer--app-v-46-sp1-.md)

 

 





