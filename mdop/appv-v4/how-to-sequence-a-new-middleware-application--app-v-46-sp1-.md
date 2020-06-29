---
title: 如何排序新的中介軟體應用程式 (App-V 4.6 SP1)
description: 如何排序新的中介軟體應用程式 (App-V 4.6 SP1)
author: dansimp
ms.assetid: 304045c2-5e5e-4c91-b59e-a91fdf2500fb
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: b26559b8f5c451d01fefe899e96a83dd388b8140
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801110"
---
# <span data-ttu-id="84398-103">如何排序新的中介軟體應用程式 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="84398-103">How to Sequence a New Middleware Application (App-V 4.6 SP1)</span></span>


<span data-ttu-id="84398-104">使用下列程式，使用 Application Virtualization （App-v） Sequencer 來建立新的中介軟體虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="84398-104">Use the following procedure to create a new middleware virtual application package using the Application Virtualization (App-V) Sequencer.</span></span> <span data-ttu-id="84398-105">中介軟體應用程式是連接軟體模組或應用程式的軟體。</span><span class="sxs-lookup"><span data-stu-id="84398-105">A middleware application is software that connects software modules or applications.</span></span> <span data-ttu-id="84398-106">如需可排序之應用程式類型的詳細資訊，請參閱[如何判斷要順序的應用程式類型（app-v 4.6 SP1）](how-to-determine-which-type-of-application-to-sequence---app-v-46-sp1-.md)。</span><span class="sxs-lookup"><span data-stu-id="84398-106">For more information about the types of applications that you can sequence, see [How to Determine Which Type of Application to Sequence (App-V 4.6 SP1)](how-to-determine-which-type-of-application-to-sequence---app-v-46-sp1-.md).</span></span>

<span data-ttu-id="84398-107">在 App-v 中使用動態套件組合來使用這種類型的套件。</span><span class="sxs-lookup"><span data-stu-id="84398-107">Use this type of package by using Dynamic Suite Composition in App-V.</span></span> <span data-ttu-id="84398-108">動態套件組合可讓您定義虛擬應用程式套件，以依賴另一個虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="84398-108">Dynamic Suite Composition enables you to define a virtual application package as being dependent on another virtual application package.</span></span> <span data-ttu-id="84398-109">相依性可讓應用程式與虛擬環境中的中介軟體或外掛程式互動，這通常會造成這種互動。</span><span class="sxs-lookup"><span data-stu-id="84398-109">The dependency enables the application to interact with the middleware or plug-in in the virtual environment, where typically this interaction is prevented.</span></span> <span data-ttu-id="84398-110">這個功能非常實用，因為次應用程式套件可以與數個其他主要應用程式搭配使用，這可讓每個主要的應用程式都能參考同一個副套件。</span><span class="sxs-lookup"><span data-stu-id="84398-110">This is useful because a secondary application package can be used with several other primary applications, which enables each primary application to reference the same secondary package.</span></span> <span data-ttu-id="84398-111">如需如何使用動態套件組合的詳細資訊，請參閱如何在 Microsoft 技術文件庫（）中[使用動態套件組合](https://go.microsoft.com/fwlink/?LinkID=203804&clcid=0x409) https://go.microsoft.com/fwlink/?LinkID=203804&clcid=0x409) 。</span><span class="sxs-lookup"><span data-stu-id="84398-111">For more information about how to use Dynamic Suite Composition, see [How To Use Dynamic Suite Composition](https://go.microsoft.com/fwlink/?LinkID=203804&clcid=0x409) in the Microsoft Technical Library (https://go.microsoft.com/fwlink/?LinkID=203804&clcid=0x409).</span></span>

**<span data-ttu-id="84398-112">重要</span><span class="sxs-lookup"><span data-stu-id="84398-112">Important</span></span>**  
<span data-ttu-id="84398-113">在排序期間，如果執行 app-v 排序器的電腦是執行 Windows Vista 或 Windows 7，且在虛擬環境之外啟動重新開機，例如**開始**  /  **關閉**，則當系統提示您關閉禁止 Windows 關閉的程式時，您必須按一下 [**取消**]。</span><span class="sxs-lookup"><span data-stu-id="84398-113">During sequencing, if the computer running the App-V Sequencer is running Windows Vista or Windows 7 and a restart is initiated outside of the virtual environment, for example, **Start** / **Shut Down**, you must click **Cancel** when prompted to close the program that is preventing Windows from shutting down.</span></span> <span data-ttu-id="84398-114">如果您按一下 [**強制關閉**]，套件建立就會失敗。</span><span class="sxs-lookup"><span data-stu-id="84398-114">If you click **Force shut down**, the package creation fails.</span></span> <span data-ttu-id="84398-115">當您按一下 [**取消**] 時，app-v Sequencer 會在應用程式排序時成功記錄重新開機。</span><span class="sxs-lookup"><span data-stu-id="84398-115">When you click **Cancel**, App-V Sequencer successfully records the restart while the application is being sequenced.</span></span>



**<span data-ttu-id="84398-116">為新的中介軟體應用程式排序</span><span class="sxs-lookup"><span data-stu-id="84398-116">To sequence a new middleware application</span></span>**

1.  <span data-ttu-id="84398-117">若要啟動 app-v 排序器，請在執行 app-v 排序器的電腦上，按一下 [**開始**  /  **所有程式**]  /  **microsoft application virtualization**  /  **microsoft application virtualization 排序**器。</span><span class="sxs-lookup"><span data-stu-id="84398-117">To start App-V Sequencer, on the computer that is running App-V Sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="84398-118">若要啟動 [**建立新套件] 嚮導**，請按一下 [**建立新的虛擬應用程式套件**]。</span><span class="sxs-lookup"><span data-stu-id="84398-118">To start the **Create New Package Wizard**, click **Create a New Virtual Application Package**.</span></span> <span data-ttu-id="84398-119">若要建立套件，請選取 [**建立套件（預設）**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="84398-119">To create the package, select **Create Package (default)**, and then click **Next**.</span></span>

3.  <span data-ttu-id="84398-120">在 [**準備電腦**] 頁面上，查看可能導致套件建立失敗的問題，或套件中包含不必要的資料。</span><span class="sxs-lookup"><span data-stu-id="84398-120">On the **Prepare Computer** page, review the issues that might cause the package creation to fail, or for the package to contain unnecessary data.</span></span> <span data-ttu-id="84398-121">我們強烈建議您在繼續進行之前先解決所有潛在問題。</span><span class="sxs-lookup"><span data-stu-id="84398-121">We strongly recommend that you resolve all potential issues before you continue.</span></span> <span data-ttu-id="84398-122">修正衝突之後，若要更新顯示的資訊，**請按一下 [** 重新整理]。</span><span class="sxs-lookup"><span data-stu-id="84398-122">After you have fixed the conflicts, to update the information displayed, click **Refresh**.</span></span> <span data-ttu-id="84398-123">解決所有可能的問題之後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="84398-123">After you have resolved all potential issues, click **Next**.</span></span>

    **<span data-ttu-id="84398-124">重要</span><span class="sxs-lookup"><span data-stu-id="84398-124">Important</span></span>**  
    <span data-ttu-id="84398-125">如果您需要停用病毒掃描軟體，您必須掃描執行應用程式 VSequencer 的電腦，以確保無法在套件中新增不需要的或惡意檔案。</span><span class="sxs-lookup"><span data-stu-id="84398-125">If you are required to disable virus scanning software, you must scan the computer running the App-VSequencer to ensure that no unwanted or malicious files can be added to the package.</span></span>



4.  <span data-ttu-id="84398-126">在 [**應用程式類型**] 頁面上，選取 [**中介軟體**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="84398-126">On the **Type of Application** page, select **Middleware**, and then click **Next**.</span></span>

    <span data-ttu-id="84398-127">如需可排序之應用程式類型的詳細資訊，請參閱[如何判斷要順序的應用程式類型（app-v 4.6 SP1）](how-to-determine-which-type-of-application-to-sequence---app-v-46-sp1-.md)。</span><span class="sxs-lookup"><span data-stu-id="84398-127">For more information about the types of applications that you can sequence, see [How to Determine Which Type of Application to Sequence (App-V 4.6 SP1)](how-to-determine-which-type-of-application-to-sequence---app-v-46-sp1-.md).</span></span>

5.  <span data-ttu-id="84398-128">在 [**選取安裝程式**] 頁面上，按一下 **[流覽]** ，然後指定應用程式的安裝檔。</span><span class="sxs-lookup"><span data-stu-id="84398-128">On the **Select Installer** page, click **Browse** and specify the installation file for the application.</span></span> <span data-ttu-id="84398-129">如果應用程式沒有關聯的安裝程式檔案，且您打算手動執行所有安裝步驟，請選取 [**選取此選項以執行自訂安裝**] 核取方塊，然後按一下 [**下一步]**。</span><span class="sxs-lookup"><span data-stu-id="84398-129">If the application does not have an associated installer file and you plan to run all installation steps manually, select the **Select this option to perform a custom installation** check box, and then click **Next**.</span></span>

6.  <span data-ttu-id="84398-130">在 [**套件名稱**] 頁面上，指定將與套件建立關聯的名稱。</span><span class="sxs-lookup"><span data-stu-id="84398-130">On the **Package Name** page, specify a name that will be associated with the package.</span></span> <span data-ttu-id="84398-131">名稱可協助識別將新增到套件中之應用程式的用途和版本。</span><span class="sxs-lookup"><span data-stu-id="84398-131">The name helps identify the purpose and version of the application that will be added to the package.</span></span> <span data-ttu-id="84398-132">套件名稱也會顯示在 App V 管理主控台中。</span><span class="sxs-lookup"><span data-stu-id="84398-132">The package name is also displayed in the App-V Management Console.</span></span> <span data-ttu-id="84398-133">**安裝位置**會顯示應用程式的虛擬化路徑，將會安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="84398-133">The **Installation Location** displays the application virtualization path where the application will be installed.</span></span> <span data-ttu-id="84398-134">若要編輯此位置，請選取 **[編輯] （[高級]）**。</span><span class="sxs-lookup"><span data-stu-id="84398-134">To edit this location, select **Edit (Advanced)**.</span></span>

    **<span data-ttu-id="84398-135">重要</span><span class="sxs-lookup"><span data-stu-id="84398-135">Important</span></span>**  
    <span data-ttu-id="84398-136">編輯應用程式虛擬化路徑是一個高級的配置工作。</span><span class="sxs-lookup"><span data-stu-id="84398-136">Editing the Application Virtualization path is an advanced configuration task.</span></span> <span data-ttu-id="84398-137">您應該完全瞭解變更路徑的意義。</span><span class="sxs-lookup"><span data-stu-id="84398-137">You should fully understand the implications of changing the path.</span></span> <span data-ttu-id="84398-138">對於大部分的應用程式，我們建議預設路徑。</span><span class="sxs-lookup"><span data-stu-id="84398-138">For most applications, we recommend the default path.</span></span>



~~~
Click **Next**.
~~~

7. <span data-ttu-id="84398-139">在 [**安裝**] 頁面上，當 sequencer 和中介軟體應用程式安裝程式準備好時，請安裝應用程式，讓排序器可以監視安裝程式。</span><span class="sxs-lookup"><span data-stu-id="84398-139">On the **Installation** page, when the Sequencer and middleware application installer are ready, install the application so that the Sequencer can monitor the installation process.</span></span> <span data-ttu-id="84398-140">使用應用程式的安裝程式來執行安裝。</span><span class="sxs-lookup"><span data-stu-id="84398-140">Perform the installation by using the application’s installation process.</span></span> <span data-ttu-id="84398-141">如果安裝時必須執行其他安裝檔，請按一下 [**執行**]，找出並執行其他安裝檔案。</span><span class="sxs-lookup"><span data-stu-id="84398-141">If additional installation files must be run as part of the installation, click **Run**, to locate and run the additional installation files.</span></span> <span data-ttu-id="84398-142">完成安裝後，請選取 [**我已完成安裝**] 核取方塊，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="84398-142">When you are finished with the installation, select the **I am finished installing** check box, and then click **Next**.</span></span>

8. <span data-ttu-id="84398-143">在 [**安裝**] 頁面上，請稍候，Sequencer 會設定虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="84398-143">On the **Installation** page, wait while the Sequencer configures the virtual application package.</span></span>

9. <span data-ttu-id="84398-144">在 [**安裝報告**] 頁面上，您可以查看剛剛排序的虛擬應用程式套件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="84398-144">On the **Installation Report** page, you can review information about the virtual application package that you just sequenced.</span></span> <span data-ttu-id="84398-145">如需**其他資訊**所顯示之資訊的詳細說明，請按兩下該事件。</span><span class="sxs-lookup"><span data-stu-id="84398-145">For a more detailed explanation about the information displayed in **Additional Information**, double-click the event.</span></span> <span data-ttu-id="84398-146">審閱資訊之後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="84398-146">After you have reviewed the information, click **Next**.</span></span>

10. <span data-ttu-id="84398-147">在 [**目標作業系統**] 頁面上，指定可執行此套件的作業系統。</span><span class="sxs-lookup"><span data-stu-id="84398-147">On the **Target OS** page, specify the operating systems that can run this package.</span></span> <span data-ttu-id="84398-148">若要在您的環境中啟用所有受支援的作業系統來執行這個套件，請選取 [**允許此套件在任何作業系統上執行**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="84398-148">To enable all supported operating systems in your environment to run this package, select the **Allow this package to run on any operating system** check box.</span></span> <span data-ttu-id="84398-149">若要將這個套件設定為只在特定作業系統上執行，請選取 [**只允許此套件在下列作業系統上執行**] 核取方塊，然後選取可以執行此套件的作業系統。</span><span class="sxs-lookup"><span data-stu-id="84398-149">To configure this package to run only on specific operating systems, select the **Allow this package to run only on the following operating systems** check box and select the operating systems that can run this package.</span></span> <span data-ttu-id="84398-150">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="84398-150">Click **Next**.</span></span>

11. <span data-ttu-id="84398-151">在 [**建立套件**] 頁面上，若要修改套件但不儲存，請選取 [**繼續使用套件編輯器來修改套件但不儲存**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="84398-151">On the **Create Package** page, to modify the package without saving it, select the **Continue to modify package without saving using the package editor** check box.</span></span> <span data-ttu-id="84398-152">選取此選項會在 Sequencer 視窗中開啟套件，讓您可以在儲存套件之前加以修改。</span><span class="sxs-lookup"><span data-stu-id="84398-152">Selecting this option opens the package in the Sequencer console so that you can modify the package before it is saved.</span></span> <span data-ttu-id="84398-153">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="84398-153">Click **Next**.</span></span>

   <span data-ttu-id="84398-154">若要立即儲存套件，請選取預設值 [**立即儲存套件**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="84398-154">To save the package immediately, select the default, the **Save the package now** check box.</span></span> <span data-ttu-id="84398-155">在 [**批註**] 方塊中新增要與套件相關聯的選擇性批註。</span><span class="sxs-lookup"><span data-stu-id="84398-155">Add optional comments in the **Comments** box that will be associated with the package.</span></span> <span data-ttu-id="84398-156">若要識別套件的版本及其他資訊，可以使用 [批註]。</span><span class="sxs-lookup"><span data-stu-id="84398-156">Comments are useful for identifying version and other information about the package.</span></span> <span data-ttu-id="84398-157">也會顯示預設的**儲存位置**。</span><span class="sxs-lookup"><span data-stu-id="84398-157">The default **Save Location** is also displayed.</span></span> <span data-ttu-id="84398-158">若要變更預設位置，請按一下 **[流覽]**，然後指定新的位置。</span><span class="sxs-lookup"><span data-stu-id="84398-158">To change the default location, click **Browse**, and then specify the new location.</span></span> <span data-ttu-id="84398-159">隨即會顯示未壓縮的套件大小。</span><span class="sxs-lookup"><span data-stu-id="84398-159">The uncompressed package size is displayed.</span></span> <span data-ttu-id="84398-160">如果套件大小超過 4 GB （未壓縮），且您打算將套件資料流程資料流至目的電腦，您必須選取 [**壓縮套件**]。</span><span class="sxs-lookup"><span data-stu-id="84398-160">If the package size exceeds 4 GB (uncompressed) and you plan to stream the package to target computers, you must select **Compress Package**.</span></span> <span data-ttu-id="84398-161">按一下 \[建立\]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="84398-161">Click **Create**.</span></span>

12. <span data-ttu-id="84398-162">在 [**完成**] 頁面上，檢查 [**虛擬應用程式套件報告**] 窗格中顯示的資訊後，按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="84398-162">On the **Completion** page, after you have reviewed the information displayed in the **Virtual Application Package Report** pane, click **Close**.</span></span> <span data-ttu-id="84398-163">在 [**虛擬應用程式套件報告**] 窗格中顯示的資訊，也可在此程式的步驟11所指定的目錄中取得，在名為**Report.xml**的檔案中提供。</span><span class="sxs-lookup"><span data-stu-id="84398-163">The information displayed in the **Virtual Application Package Report** pane is also available in the directory specified in step 11 of this procedure, in a file named **Report.xml**.</span></span>

   <span data-ttu-id="84398-164">套件現在可在 Sequencer 中取得。</span><span class="sxs-lookup"><span data-stu-id="84398-164">The package is now available in the Sequencer.</span></span> <span data-ttu-id="84398-165">若要編輯套件屬性，請按一下 **[編輯 \ [套件名稱 \]]**。</span><span class="sxs-lookup"><span data-stu-id="84398-165">To edit the package properties, click **Edit \[Package Name\]**.</span></span> <span data-ttu-id="84398-166">如需有關修改套件的詳細資訊，請參閱[如何修改現有的虛擬應用程式套件（app-v 4.6 SP1）](how-to-modify-an-existing-virtual-application-package--app-v-46-sp1-.md)</span><span class="sxs-lookup"><span data-stu-id="84398-166">For more information about modifying a package, see [How to Modify an Existing Virtual Application Package (App-V 4.6 SP1)](how-to-modify-an-existing-virtual-application-package--app-v-46-sp1-.md)</span></span>

   **<span data-ttu-id="84398-167">重要</span><span class="sxs-lookup"><span data-stu-id="84398-167">Important</span></span>**  
   <span data-ttu-id="84398-168">成功建立虛擬應用程式套件之後，您就無法在執行排序器的電腦上執行虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="84398-168">After you have successfully created a virtual application package, you cannot run the virtual application package on the computer that is running the Sequencer.</span></span>



## <span data-ttu-id="84398-169">相關主題</span><span class="sxs-lookup"><span data-stu-id="84398-169">Related topics</span></span>


[<span data-ttu-id="84398-170">Application Virtualization Sequencer 的工作 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="84398-170">Tasks for the Application Virtualization Sequencer (App-V 4.6 SP1)</span></span>](tasks-for-the-application-virtualization-sequencer--app-v-46-sp1-.md)

[<span data-ttu-id="84398-171">如何判斷要順序的應用程式類型（App-v 4.6 SP1）</span><span class="sxs-lookup"><span data-stu-id="84398-171">How to Determine Which Type of Application to Sequence (App-V 4.6 SP1)</span></span>](how-to-determine-which-type-of-application-to-sequence---app-v-46-sp1-.md)









