---
title: 如何修改現有的虛擬應用程式套件
description: 如何修改現有的虛擬應用程式套件
author: dansimp
ms.assetid: 6cdeec00-e4fe-4210-b4c7-6ca1ac643ddd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 11/01/2016
ms.openlocfilehash: 95963610c8b725412f6d516ee22b1c2f4e186df6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800450"
---
# <span data-ttu-id="16272-103">如何修改現有的虛擬應用程式套件</span><span class="sxs-lookup"><span data-stu-id="16272-103">How to Modify an Existing Virtual Application Package</span></span>


<span data-ttu-id="16272-104">本主題說明如何：</span><span class="sxs-lookup"><span data-stu-id="16272-104">This topic explains how to:</span></span>

-   [<span data-ttu-id="16272-105">更新現有虛擬應用程式套件中的應用程式</span><span class="sxs-lookup"><span data-stu-id="16272-105">Update an application in an existing virtual application package</span></span>](#bkmk-update-app-in-pkg)

-   [<span data-ttu-id="16272-106">修改與現有虛擬應用程式套件相關聯的屬性</span><span class="sxs-lookup"><span data-stu-id="16272-106">Modify the properties associated with an existing virtual application package</span></span>](#bkmk-chg-props-in-pkg)

-   [<span data-ttu-id="16272-107">將新的應用程式新增至現有的虛擬應用程式套件</span><span class="sxs-lookup"><span data-stu-id="16272-107">Add a new application to an existing virtual application package</span></span>](#bkmk-add-app-to-pkg)

**<span data-ttu-id="16272-108">更新套件前：</span><span class="sxs-lookup"><span data-stu-id="16272-108">Before you update a package:</span></span>**

-   <span data-ttu-id="16272-109">確定您已安裝 Microsoft Application Virtualization （App-v） Sequencer，這是修改虛擬應用程式套件所需的。</span><span class="sxs-lookup"><span data-stu-id="16272-109">Ensure that you’ve installed the Microsoft Application Virtualization (App-V) Sequencer, which is required for modifying a virtual application package.</span></span> <span data-ttu-id="16272-110">若要安裝應用程式 V 排序器，請參閱[如何安裝排序](how-to-install-the-sequencer-51beta-gb18030.md)器。</span><span class="sxs-lookup"><span data-stu-id="16272-110">To install the App-V Sequencer, see [How to Install the Sequencer](how-to-install-the-sequencer-51beta-gb18030.md).</span></span>

-   <span data-ttu-id="16272-111">將此 appv 檔案儲存在安全的位置，並在嘗試開啟套件進行編輯之前，永遠相信來源。</span><span class="sxs-lookup"><span data-stu-id="16272-111">Save the .appv file in a secure location and always trust the source before trying to open the package for editing.</span></span>

-   <span data-ttu-id="16272-112">當您更新套件時，系統會錯誤地從部署設定檔中移除 [管理授權] 區段。</span><span class="sxs-lookup"><span data-stu-id="16272-112">The Managing Authority section is erroneously removed from the deployment configuration file when you update a package.</span></span> <span data-ttu-id="16272-113">開始更新之前，請先從現有的部署配置檔案複製管理機構區段，然後在轉換完成後，將複製的節貼到新的設定檔中。</span><span class="sxs-lookup"><span data-stu-id="16272-113">Before starting the update, copy the Managing Authority section from the existing deployment configuration file, and then paste the copied section into the new configuration file after the conversion is complete.</span></span>

-   <span data-ttu-id="16272-114">如果您在 Sequencer 中按一下 [**修改現有的虛擬應用程式套件**]，以編輯套件，但接著不做任何變更並關閉套件，則會變更套件的資料流程行為。</span><span class="sxs-lookup"><span data-stu-id="16272-114">If you click **Modify an Existing Virtual Application Package** in the Sequencer in order to edit a package, but then make no changes and close the package, the streaming behavior of the package is changed.</span></span> <span data-ttu-id="16272-115">主要功能區塊會從 StreamMap.xml 檔案中移除，且發佈功能區塊中所列的任何檔案都會被移除。</span><span class="sxs-lookup"><span data-stu-id="16272-115">The primary feature block is removed from the StreamMap.xml file, and any files that were listed in the publishing feature block are removed.</span></span> <span data-ttu-id="16272-116">收到已編輯套件體驗的使用者，不論原始套件的設定方式為何，都會將其打包成資料流程發生故障。</span><span class="sxs-lookup"><span data-stu-id="16272-116">Users who receive the edited package experience that package as if it were stream-faulted, regardless of how the original package was configured.</span></span>

<a href="" id="bkmk-update-app-in-pkg"></a>**<span data-ttu-id="16272-117">更新現有虛擬應用程式套件中的應用程式</span><span class="sxs-lookup"><span data-stu-id="16272-117">Update an application in an existing virtual application package</span></span>**

1.  <span data-ttu-id="16272-118">在執行排序器的電腦上，按一下 [**所有程式**]，指向 [ **Microsoft application virtualization**]，然後按一下 [ **microsoft application Virtualization 排序**器]。</span><span class="sxs-lookup"><span data-stu-id="16272-118">On the computer that runs the sequencer, click **All Programs**, point to **Microsoft Application Virtualization**, and then click **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="16272-119">在 app-v 排序器中，按一下 [**修改現有的虛擬應用程式套件** &gt; **]**。</span><span class="sxs-lookup"><span data-stu-id="16272-119">In the App-V Sequencer, click **Modify an Existing Virtual Application Package** &gt; **Next**.</span></span>

3.  <span data-ttu-id="16272-120">在 [**選取**工作] 頁面上，按一下 [**在現有套件中更新應用程式** &gt; **] 下一步**。</span><span class="sxs-lookup"><span data-stu-id="16272-120">On the **Select Task** page, click **Update Application in Existing Package** &gt; **Next**.</span></span>

4.  <span data-ttu-id="16272-121">在 [**選取套件**] 頁面上，按一下 **[流覽]** ，找出包含要更新之應用程式的虛擬應用程式套件，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="16272-121">On the **Select Package** page, click **Browse** to locate the virtual application package that contains the application to update, and then click **Next**.</span></span>

5.  <span data-ttu-id="16272-122">在 [**準備電腦**] 頁面上，查看可能導致應用程式更新失敗的問題，或導致更新的應用程式包含不必要的資料。</span><span class="sxs-lookup"><span data-stu-id="16272-122">On the **Prepare Computer** page, review the issues that could cause the application update to fail or cause the updated application to contain unnecessary data.</span></span> <span data-ttu-id="16272-123">繼續進行之前，請先解決所有潛在問題。</span><span class="sxs-lookup"><span data-stu-id="16272-123">Resolve all potential issues before you continue.</span></span> <span data-ttu-id="16272-124">在進行任何可能的修正並解決所有潛在問題之後 **，按一下**[重新整理 &gt; **下一步]**。</span><span class="sxs-lookup"><span data-stu-id="16272-124">After making any corrections and resolving all potential issues, click **Refresh** &gt; **Next**.</span></span>

    <span data-ttu-id="16272-125">**重要** 如果您需要停用病毒掃描軟體，請先掃描執行 sequencer 的電腦，以確保套件中不會新增不需要的或惡意的檔案。</span><span class="sxs-lookup"><span data-stu-id="16272-125">**Important** If you are required to disable virus scanning software, first scan the computer that runs the sequencer to ensure that no unwanted or malicious files are added to the package.</span></span>

6.  <span data-ttu-id="16272-126">在 [**選取安裝程式**] 頁面上，按一下 **[流覽]** ，然後指定應用程式的更新安裝檔案。</span><span class="sxs-lookup"><span data-stu-id="16272-126">On the **Select Installer** page, click **Browse** and specify the update installation file for the application.</span></span> <span data-ttu-id="16272-127">如果更新沒有關聯的安裝程式檔案，且您打算手動執行所有安裝步驟，請選取 [**選取此選項以執行自訂安裝**] 核取方塊，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="16272-127">If the update does not have an associated installer file, and if you plan to run all installation steps manually, select the **Select this option to perform a custom installation** check box, and then click **Next**.</span></span>

7.  <span data-ttu-id="16272-128">在 [**安裝**] 頁面上，當排序器和應用程式安裝程式準備好時，您可以繼續安裝應用程式更新，讓排序器可以監視安裝程式。</span><span class="sxs-lookup"><span data-stu-id="16272-128">On the **Installation** page, when the sequencer and application installer are ready you can proceed to install the application update so the sequencer can monitor the installation process.</span></span> <span data-ttu-id="16272-129">如果安裝時必須執行其他安裝檔案，請按一下 [**執行**]，然後找出並執行其他安裝檔案。</span><span class="sxs-lookup"><span data-stu-id="16272-129">If additional installation files must be run as part of the installation, click **Run**, and then locate and run the additional installation files.</span></span> <span data-ttu-id="16272-130">完成安裝後，請選取 [**我已完成安裝**]。</span><span class="sxs-lookup"><span data-stu-id="16272-130">When you are finished with the installation, select **I am finished installing**.</span></span> <span data-ttu-id="16272-131">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="16272-131">Click **Next**.</span></span>

    <span data-ttu-id="16272-132">**記事** 排序器會監視執行排序器的電腦上發生的所有變更和安裝。</span><span class="sxs-lookup"><span data-stu-id="16272-132">**Note** The sequencer monitors all changes and installations that occur on the computer that runs the sequencer.</span></span> <span data-ttu-id="16272-133">這包括在先後順序嚮導之外執行的任何變更和安裝。</span><span class="sxs-lookup"><span data-stu-id="16272-133">This includes any changes and installations that are performed outside of the sequencing wizard.</span></span>

8.  <span data-ttu-id="16272-134">在 [**安裝報告**] 頁面上，您可以查看已更新虛擬應用程式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="16272-134">On the **Installation Report** page, you can review information about the updated virtual application.</span></span> <span data-ttu-id="16272-135">在 [**其他資訊**] 中，按兩下事件以取得更詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="16272-135">In **Additional Information**, double-click the event to obtain more detailed information.</span></span> <span data-ttu-id="16272-136">若要繼續，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="16272-136">To proceed, click **Next**.</span></span>

9.  <span data-ttu-id="16272-137">在 [**流式處理**] 頁面上，執行每個程式，讓它能在目的電腦上優化並更有效率地執行。</span><span class="sxs-lookup"><span data-stu-id="16272-137">On the **Streaming** page, run each program so that it can be optimized and run more efficiently on target computers.</span></span> <span data-ttu-id="16272-138">可能需要幾分鐘的時間，才能執行所有的應用程式。</span><span class="sxs-lookup"><span data-stu-id="16272-138">It can take several minutes for all of the applications to run.</span></span> <span data-ttu-id="16272-139">在所有應用程式都已執行之後，請關閉每個應用程式，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="16272-139">After all applications have run, close each of the applications, and then click **Next**.</span></span>

    <span data-ttu-id="16272-140">**記事** 您可以在此步驟中停止載入應用程式。</span><span class="sxs-lookup"><span data-stu-id="16272-140">**Note** You can stop an application from loading during this step.</span></span> <span data-ttu-id="16272-141">在 [**應用程式啟動**] 對話方塊中，按一下 [**停止**]，然後選取 [**停止所有應用程式**] 或 [**僅停止此應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="16272-141">In the **Application Launch** dialog box, click **Stop**, and then select either **Stop all applications** or **Stop this application only**.</span></span>   

10. <span data-ttu-id="16272-142">在 [**建立套件**] 頁面上，若要修改套件但不儲存，請選取 [**繼續修改套件] 核取方塊，但不要使用 [封裝編輯器] 儲存**。</span><span class="sxs-lookup"><span data-stu-id="16272-142">On the **Create Package** page, to modify the package without saving it, select the check box for **Continue to modify package without saving using the package editor**.</span></span> <span data-ttu-id="16272-143">當您選取此選項時，會在 App V 排序器主控台中開啟套件，您可以在儲存之前修改套件。</span><span class="sxs-lookup"><span data-stu-id="16272-143">When you select this option, the package opens in the App-V Sequencer console, where you can modify the package before it is saved.</span></span> <span data-ttu-id="16272-144">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="16272-144">Click **Next**.</span></span>

    <span data-ttu-id="16272-145">若要立即儲存套件，請選取 [**立即儲存套件**] 的預設值。</span><span class="sxs-lookup"><span data-stu-id="16272-145">To save the package immediately, select the default **Save the package now**.</span></span> <span data-ttu-id="16272-146">新增要與套件相關聯的選擇性**批註**。</span><span class="sxs-lookup"><span data-stu-id="16272-146">Add optional **Comments** to associate with the package.</span></span> <span data-ttu-id="16272-147">[批註] 可用於識別應用程式版本，並提供有關套件的其他資訊。</span><span class="sxs-lookup"><span data-stu-id="16272-147">Comments are useful to identify the application version and provide other information about the package.</span></span> <span data-ttu-id="16272-148">也會顯示預設的**儲存位置**。</span><span class="sxs-lookup"><span data-stu-id="16272-148">The default **Save Location** is also displayed.</span></span> <span data-ttu-id="16272-149">若要變更預設位置，請按一下 **[流覽]** ，然後指定新的位置。</span><span class="sxs-lookup"><span data-stu-id="16272-149">To change the default location, click **Browse** and specify the new location.</span></span> <span data-ttu-id="16272-150">按一下 \[建立\]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="16272-150">Click **Create**.</span></span>

11. <span data-ttu-id="16272-151">在**完成**頁面上，按一下 [**關閉**] 以關閉嚮導。</span><span class="sxs-lookup"><span data-stu-id="16272-151">On the **Completion** page, click **Close** to close the wizard.</span></span> <span data-ttu-id="16272-152">套件現在可在 sequencer 中取得。</span><span class="sxs-lookup"><span data-stu-id="16272-152">The package is now available in the sequencer.</span></span>

<a href="" id="bkmk-chg-props-in-pkg"></a>**<span data-ttu-id="16272-153">修改與現有虛擬應用程式套件相關聯的屬性</span><span class="sxs-lookup"><span data-stu-id="16272-153">Modify the properties associated with an existing virtual application package</span></span>**

1.  <span data-ttu-id="16272-154">在執行排序器的電腦上，按一下 [**所有程式**]，指向 [ **Microsoft application virtualization**]，然後按一下 [ **microsoft application Virtualization 排序**器]。</span><span class="sxs-lookup"><span data-stu-id="16272-154">On the computer that runs the sequencer, click **All Programs**, point to **Microsoft Application Virtualization**, and then click **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="16272-155">在 app-v 排序器中，按一下 [**修改現有的虛擬應用程式套件** &gt; **]**。</span><span class="sxs-lookup"><span data-stu-id="16272-155">In the App-V Sequencer, click **Modify an Existing Virtual Application Package** &gt; **Next**.</span></span>

3.  <span data-ttu-id="16272-156">在 [**選取**工作] 頁面上，按一下 [**編輯包** &gt; **] [下一步]**。</span><span class="sxs-lookup"><span data-stu-id="16272-156">On the **Select Task** page, click **Edit Package** &gt; **Next**.</span></span>

4.  <span data-ttu-id="16272-157">在 [**選取套件**] 頁面上，按一下 **[流覽]** ，找出包含要修改之應用程式屬性的虛擬應用程式套件，然後按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="16272-157">On the **Select Package** page, click **Browse** to locate the virtual application package that contains the application properties to modify, and then click **Edit**.</span></span>

5.  <span data-ttu-id="16272-158">在 App-v 排序器主控台中，視需要執行下列任何一項作業：</span><span class="sxs-lookup"><span data-stu-id="16272-158">In the App-V Sequencer console, perform any of the following tasks as needed:</span></span>

    -   <span data-ttu-id="16272-159">匯入及匯出資訊清單檔案。</span><span class="sxs-lookup"><span data-stu-id="16272-159">Import and export the manifest file.</span></span>

    -   <span data-ttu-id="16272-160">啟用或停用瀏覽器小幫手物件。</span><span class="sxs-lookup"><span data-stu-id="16272-160">Enable or disable Browser Helper Objects.</span></span>

    -   <span data-ttu-id="16272-161">匯入或匯出 VFS 檔案。</span><span class="sxs-lookup"><span data-stu-id="16272-161">Import or export a VFS file.</span></span>

    -   <span data-ttu-id="16272-162">將目錄匯入到虛擬檔案系統中。</span><span class="sxs-lookup"><span data-stu-id="16272-162">Import a directory into the virtual file system.</span></span>

    -   <span data-ttu-id="16272-163">匯入及匯出虛擬登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="16272-163">Import and export virtual registry keys.</span></span>

    -   <span data-ttu-id="16272-164">[查看套件屬性]。</span><span class="sxs-lookup"><span data-stu-id="16272-164">View package properties.</span></span>

    -   <span data-ttu-id="16272-165">[查看關聯的套件檔案]。</span><span class="sxs-lookup"><span data-stu-id="16272-165">View associated package files.</span></span>

    -   <span data-ttu-id="16272-166">編輯註冊表設定。</span><span class="sxs-lookup"><span data-stu-id="16272-166">Edit registry settings.</span></span>

    -   <span data-ttu-id="16272-167">查看其他套件設定（除了作業系統檔案屬性之外）。</span><span class="sxs-lookup"><span data-stu-id="16272-167">Review additional package settings (except operating system file properties).</span></span>

    -   <span data-ttu-id="16272-168">設定虛擬化登錄機碼的狀態（覆寫或合併）。</span><span class="sxs-lookup"><span data-stu-id="16272-168">Set virtualized registry key state (override or merge).</span></span>

    -   <span data-ttu-id="16272-169">設定虛擬化資料夾的狀態。</span><span class="sxs-lookup"><span data-stu-id="16272-169">Set virtualized folder state.</span></span>

    -   <span data-ttu-id="16272-170">新增或編輯快速鍵與檔案類型關聯。</span><span class="sxs-lookup"><span data-stu-id="16272-170">Add or edit shortcuts and file type associations.</span></span>

        <span data-ttu-id="16272-171">**記事** 若要編輯快速鍵或檔案類型關聯，您必須先開啟套件進行升級，才能新增新的應用程式，然後繼續進行最後一個編輯頁面。</span><span class="sxs-lookup"><span data-stu-id="16272-171">**Note** To edit shortcuts or file type associations, you must first open the package for upgrade to add a new application, and then proceed to the final editing page.</span></span>

6.  <span data-ttu-id="16272-172">當您完成變更套件屬性時 **，按一下 [** 儲存檔案] &gt; **Save**儲存套件。</span><span class="sxs-lookup"><span data-stu-id="16272-172">When you finish changing the package properties, click **File** &gt; **Save** to save the package.</span></span>

<a href="" id="bkmk-add-app-to-pkg"></a>**<span data-ttu-id="16272-173">將新的應用程式新增至現有的虛擬應用程式套件</span><span class="sxs-lookup"><span data-stu-id="16272-173">Add a new application to an existing virtual application package</span></span>**

1.  <span data-ttu-id="16272-174">在執行排序器的電腦上，按一下 [**所有程式**]，指向 [ **Microsoft application virtualization**]，然後按一下 [ **microsoft application Virtualization 排序**器]。</span><span class="sxs-lookup"><span data-stu-id="16272-174">On the computer that runs the sequencer, click **All Programs**, point to **Microsoft Application Virtualization**, and then click **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="16272-175">在 app-v 排序器中，按一下 [**修改現有的虛擬應用程式套件** &gt; **]**。</span><span class="sxs-lookup"><span data-stu-id="16272-175">In the App-V Sequencer, click **Modify an Existing Virtual Application Package** &gt; **Next**.</span></span>

3.  <span data-ttu-id="16272-176">在 [**選取**工作] 頁面上，按一下 [新增**應用程式** &gt; **] 下一步**。</span><span class="sxs-lookup"><span data-stu-id="16272-176">On the **Select Task** page, click **Add New Application** &gt; **Next**.</span></span>

4.  <span data-ttu-id="16272-177">在 [**選取套件**] 頁面上，按一下 **[流覽]** ，找出您要新增應用程式的虛擬應用程式套件，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="16272-177">On the **Select Package** page, click **Browse** to locate the virtual application package to which you will add the application, and then click **Next**.</span></span>

5.  <span data-ttu-id="16272-178">在 [**準備電腦**] 頁面上，查看可能導致套件建立失敗的問題，或導致已修改的套件包含不必要的資料。</span><span class="sxs-lookup"><span data-stu-id="16272-178">On the **Prepare Computer** page, review the issues that could cause the package creation to fail or cause the revised package to contain unnecessary data.</span></span> <span data-ttu-id="16272-179">繼續進行之前，請先解決所有潛在問題。</span><span class="sxs-lookup"><span data-stu-id="16272-179">Resolve all potential issues before you continue.</span></span> <span data-ttu-id="16272-180">在進行任何可能的修正並解決所有潛在問題之後 **，按一下**[重新整理 &gt; **下一步]**。</span><span class="sxs-lookup"><span data-stu-id="16272-180">After making any corrections and resolving all potential issues, click **Refresh** &gt; **Next**.</span></span>

    <span data-ttu-id="16272-181">**重要** 如果您需要停用病毒掃描軟體，請先掃描執行 sequencer 的電腦，以確保不會在套件中新增不需要的或惡意的檔案。</span><span class="sxs-lookup"><span data-stu-id="16272-181">**Important** If you are required to disable virus scanning software, first scan the computer that runs the sequencer to ensure that no unwanted or malicious files can be added to the package.</span></span>

6.  <span data-ttu-id="16272-182">在 [**選取安裝程式**] 頁面上，按一下 **[流覽]** ，然後指定應用程式的安裝檔。</span><span class="sxs-lookup"><span data-stu-id="16272-182">On the **Select Installer** page, click **Browse** and specify the installation file for the application.</span></span> <span data-ttu-id="16272-183">如果應用程式沒有關聯的安裝程式檔案，且您打算手動執行所有安裝步驟，請選取 [**選取此選項以執行自訂安裝**] 核取方塊，然後按一下 [**下一步]**。</span><span class="sxs-lookup"><span data-stu-id="16272-183">If the application does not have an associated installer file and you plan to run all installation steps manually, select the **Select this option to perform a custom installation** check box, and then click **Next**.</span></span>

7.  <span data-ttu-id="16272-184">在 [**安裝**] 頁面上，當排序器和應用程式安裝程式準備好時，請安裝應用程式，讓排序器可以監視安裝程式。</span><span class="sxs-lookup"><span data-stu-id="16272-184">On the **Installation** page, when the sequencer and application installer are ready, install the application so that the sequencer can monitor the installation process.</span></span> <span data-ttu-id="16272-185">如果安裝時必須執行其他安裝檔案，請按一下 [**執行**]，然後找出並執行其他安裝檔案。</span><span class="sxs-lookup"><span data-stu-id="16272-185">If additional installation files must be run as part of the installation, click **Run**, and locate and run the additional installation files.</span></span> <span data-ttu-id="16272-186">完成安裝後，請選取 [**我完成**了 &gt; **下一步]**。</span><span class="sxs-lookup"><span data-stu-id="16272-186">When you finish the installation, select **I am finished installing** &gt; **Next**.</span></span> <span data-ttu-id="16272-187">在 [**流覽資料夾**] 對話方塊中，指定將安裝應用程式的主要目錄。</span><span class="sxs-lookup"><span data-stu-id="16272-187">In the **Browse for Folder** dialog box, specify the primary directory where the application will be installed.</span></span> <span data-ttu-id="16272-188">確定這是新的位置，因此您不會覆寫現有的虛擬應用程式套件版本。</span><span class="sxs-lookup"><span data-stu-id="16272-188">Ensure that this is a new location so that you don’t overwrite the existing version of the virtual application package.</span></span>

    <span data-ttu-id="16272-189">**記事** 排序器會監視執行排序器的電腦上發生的所有變更和安裝。</span><span class="sxs-lookup"><span data-stu-id="16272-189">**Note** The sequencer monitors all changes and installations that occur on the computer that runs the sequencer.</span></span> <span data-ttu-id="16272-190">這包括在先後順序嚮導之外執行的任何變更和安裝。</span><span class="sxs-lookup"><span data-stu-id="16272-190">This includes any changes and installations that are performed outside of the sequencing wizard.</span></span>

8.  <span data-ttu-id="16272-191">在 [**設定軟體**] 頁面上，選擇性地執行套件中包含的程式。</span><span class="sxs-lookup"><span data-stu-id="16272-191">On the **Configure Software** page, optionally run the programs contained in the package.</span></span> <span data-ttu-id="16272-192">此步驟會完成在您部署並在目的電腦上執行套件之前，執行應用程式所需的任何相關授權或設定工作。</span><span class="sxs-lookup"><span data-stu-id="16272-192">This step completes any associated license or configuration tasks that are required to run the application before you deploy and run the package on target computers.</span></span> <span data-ttu-id="16272-193">若要同時執行所有程式，請選取至少一個程式，然後按一下 [**全部執行**]。</span><span class="sxs-lookup"><span data-stu-id="16272-193">To run all the programs at the same time, select at least one program, and then click **Run All**.</span></span> <span data-ttu-id="16272-194">若要執行特定程式，請選取您要執行的程式或程式，然後按一下 [**執行選取**的專案]。</span><span class="sxs-lookup"><span data-stu-id="16272-194">To run specific programs, select the program or programs you want to run, and then click **Run Selected**.</span></span> <span data-ttu-id="16272-195">完成所需的配置工作，然後關閉應用程式。</span><span class="sxs-lookup"><span data-stu-id="16272-195">Complete the required configuration tasks and then close the applications.</span></span> <span data-ttu-id="16272-196">所有程式都可能需要幾分鐘的時間才能執行。</span><span class="sxs-lookup"><span data-stu-id="16272-196">It can take several minutes for all programs to run.</span></span> <span data-ttu-id="16272-197">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="16272-197">Click **Next**.</span></span>

9.  <span data-ttu-id="16272-198">在 [**安裝報告**] 頁面上，您可以查看已更新虛擬應用程式的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="16272-198">On the **Installation Report** page, you can review information about the updated virtual application.</span></span> <span data-ttu-id="16272-199">在 [**其他資訊**] 中，按兩下事件以取得更詳細的資訊，然後按一下 **[下一步]** 以開啟 [**自訂**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="16272-199">In **Additional Information**, double-click the event to obtain more detailed information, and then click **Next** to open the **Customize** page.</span></span>

10. <span data-ttu-id="16272-200">如果您已完成安裝並設定虛擬應用程式，請選取 [**立即停止**]，然後跳至此程式的步驟13。</span><span class="sxs-lookup"><span data-stu-id="16272-200">If you are finished installing and configuring the virtual application, select **Stop now** and skip to step 13 of this procedure.</span></span> <span data-ttu-id="16272-201">如果您想要執行下列描述的自訂操作，請按一下 [**自訂**]。</span><span class="sxs-lookup"><span data-stu-id="16272-201">If you want to perform the following described customization, click **Customize**.</span></span>

    <span data-ttu-id="16272-202">如果您是自訂，請準備用於流式處理的虛擬套件，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="16272-202">If you are customizing, prepare the virtual package for streaming, and then click **Next**.</span></span> <span data-ttu-id="16272-203">[資料流程] 可改善虛擬應用程式套件在目的電腦上執行時的體驗。</span><span class="sxs-lookup"><span data-stu-id="16272-203">Streaming improves the experience when the virtual application package is run on target computers.</span></span>

11. <span data-ttu-id="16272-204">在 [**流式處理**] 頁面上，執行每個程式，讓它能在目的電腦上優化並更有效率地執行。</span><span class="sxs-lookup"><span data-stu-id="16272-204">On the **Streaming** page, run each program so that it can be optimized and run more efficiently on target computers.</span></span> <span data-ttu-id="16272-205">可能需要幾分鐘的時間，所有應用程式才會執行。</span><span class="sxs-lookup"><span data-stu-id="16272-205">It can take several minutes for all the applications to run.</span></span> <span data-ttu-id="16272-206">在所有應用程式都已執行之後，請關閉每個應用程式，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="16272-206">After all applications have run, close each of the applications, and then click **Next**.</span></span>

    <span data-ttu-id="16272-207">**記事** 您可以在此步驟中停止載入應用程式。</span><span class="sxs-lookup"><span data-stu-id="16272-207">**Note** You can stop an application from loading during this step.</span></span> <span data-ttu-id="16272-208">在 [**應用程式啟動**] 對話方塊中，按一下 [**停止**]，然後選取 [**停止所有應用程式**] 或 [**僅停止此應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="16272-208">In the **Application Launch** dialog box, click **Stop** and then select either **Stop all applications** or **Stop this application only**.</span></span>

12. <span data-ttu-id="16272-209">在 [**建立套件**] 頁面上，若要修改套件但不儲存，請選取 [**繼續使用套件編輯器來修改套件但不儲存**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="16272-209">On the **Create Package** page, to modify the package without saving it, select the **Continue to modify package without saving using the package editor** check box.</span></span> <span data-ttu-id="16272-210">選取此選項會在 App-V 排序器視窗中開啟套件，您可以在儲存之前修改套件。</span><span class="sxs-lookup"><span data-stu-id="16272-210">Selecting this option opens the package in the App-V Sequencer console, where you can modify the package before saving it.</span></span> <span data-ttu-id="16272-211">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="16272-211">Click **Next**.</span></span>

    <span data-ttu-id="16272-212">若要立即儲存套件，請選取 [**立即儲存套件**] 的預設值。</span><span class="sxs-lookup"><span data-stu-id="16272-212">To save the package immediately, select the default **Save the package now**.</span></span> <span data-ttu-id="16272-213">新增要與套件相關聯的選擇性**批註**。</span><span class="sxs-lookup"><span data-stu-id="16272-213">Add optional **Comments** to associate with the package.</span></span> <span data-ttu-id="16272-214">若要提供應用程式版本及套件的其他相關資訊，請參閱意見。</span><span class="sxs-lookup"><span data-stu-id="16272-214">Comments are useful for providing application versions and other information about the package.</span></span> <span data-ttu-id="16272-215">也會顯示預設的**儲存位置**。</span><span class="sxs-lookup"><span data-stu-id="16272-215">The default **Save Location** is also displayed.</span></span> <span data-ttu-id="16272-216">若要變更預設位置，請按一下 **[流覽]** ，然後指定新的位置。</span><span class="sxs-lookup"><span data-stu-id="16272-216">To change the default location, click **Browse** and specify the new location.</span></span> <span data-ttu-id="16272-217">隨即會顯示未壓縮的套件大小。</span><span class="sxs-lookup"><span data-stu-id="16272-217">The uncompressed package size is displayed.</span></span> <span data-ttu-id="16272-218">按一下 \[建立\]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="16272-218">Click **Create**.</span></span>

13. <span data-ttu-id="16272-219">在**完成**頁面上，按一下**關閉**。</span><span class="sxs-lookup"><span data-stu-id="16272-219">On the **Completion** page, click **Close**.</span></span> <span data-ttu-id="16272-220">套件現在可在 sequencer 中取得。</span><span class="sxs-lookup"><span data-stu-id="16272-220">The package is now available in the sequencer.</span></span>

    <span data-ttu-id="16272-221">您**有應用程式-V 的建議**嗎？</span><span class="sxs-lookup"><span data-stu-id="16272-221">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="16272-222">在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="16272-222">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="16272-223">有應用程式-V 問題嗎？</span><span class="sxs-lookup"><span data-stu-id="16272-223">Got an App-V issue?</span></span>** <span data-ttu-id="16272-224">使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="16272-224">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="16272-225">相關主題</span><span class="sxs-lookup"><span data-stu-id="16272-225">Related topics</span></span>

[<span data-ttu-id="16272-226">App-V 5.1 作業</span><span class="sxs-lookup"><span data-stu-id="16272-226">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

 

 





