---
title: 如何排序新附加元件或外掛應用程式 (App-V 4.6 SP1)
description: 如何排序新附加元件或外掛應用程式 (App-V 4.6 SP1)
author: dansimp
ms.assetid: 2c018215-66e5-4301-8481-159891a6b35b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5c5bc1e96ead819459cda3879127ebdaf94f0ee7
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801125"
---
# <span data-ttu-id="96db5-103">如何排序新附加元件或外掛應用程式 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="96db5-103">How to Sequence a New Add-on or Plug-in Application (App-V 4.6 SP1)</span></span>


<span data-ttu-id="96db5-104">使用下列程式，透過應用程式虛擬化（App-v） Sequencer 來建立新的附加元件或外掛程式虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="96db5-104">Use the following procedure to create a new add-on or plug-in virtual application package by using the Application Virtualization (App-V) Sequencer.</span></span> <span data-ttu-id="96db5-105">附加元件或外掛程式應用程式是一種可擴展應用程式功能的應用程式，例如 Microsoft Excel 的外掛程式。</span><span class="sxs-lookup"><span data-stu-id="96db5-105">An add-on or plug-in application is an application that extends the functionality of an application, for example, a plug-in for Microsoft Excel.</span></span> <span data-ttu-id="96db5-106">如需有關您可以排序之應用程式類型的詳細資訊，請參閱[如何判斷要順序的應用程式類型（app-v 4.6 SP1）](how-to-determine-which-type-of-application-to-sequence---app-v-46-sp1-.md)。</span><span class="sxs-lookup"><span data-stu-id="96db5-106">For more information about the types of applications you can sequence, see [How to Determine Which Type of Application to Sequence (App-V 4.6 SP1)](how-to-determine-which-type-of-application-to-sequence---app-v-46-sp1-.md).</span></span>

**<span data-ttu-id="96db5-107">重要</span><span class="sxs-lookup"><span data-stu-id="96db5-107">Important</span></span>**  
<span data-ttu-id="96db5-108">在執行下列程式之前，請先在執行排序器的電腦上本機安裝上層應用程式。</span><span class="sxs-lookup"><span data-stu-id="96db5-108">Before performing the following procedure, install the parent application locally on the computer that is running the sequencer.</span></span> <span data-ttu-id="96db5-109">例如，如果您要為 Microsoft Excel 的外掛程式進行排序，請在執行排序器的電腦上本機安裝 Microsoft Excel。</span><span class="sxs-lookup"><span data-stu-id="96db5-109">For example, if you are sequencing a plug-in for Microsoft Excel, install Microsoft Excel locally on the computer that is running the sequencer.</span></span> <span data-ttu-id="96db5-110">您也可以在安裝了應用程式的目的電腦上，將上層應用程式安裝在同一個目錄中。</span><span class="sxs-lookup"><span data-stu-id="96db5-110">Also install the parent application in the same directory where the application is installed on target computers.</span></span> <span data-ttu-id="96db5-111">如果外掛程式或附加元件要與現有的虛擬應用程式套件搭配使用，請在建立父虛擬應用程式套件時，將應用程式安裝在所用的同一個虛擬應用程式磁碟機上。</span><span class="sxs-lookup"><span data-stu-id="96db5-111">If the plug-in or add-on is going to be used with an existing virtual application package, install the application on the same virtual application drive that was used when you created the parent virtual application package.</span></span>



<span data-ttu-id="96db5-112">您也可以使用現有的虛擬應用程式套件做為父應用程式。</span><span class="sxs-lookup"><span data-stu-id="96db5-112">You can also use an existing virtual application package as the parent application.</span></span> <span data-ttu-id="96db5-113">若要使用現有的虛擬應用程式套件，請在為新的附加元件或外掛程式排序前，先使用下列程式。</span><span class="sxs-lookup"><span data-stu-id="96db5-113">To use an existing virtual application package, use the following procedure before sequencing the new add-on or plug-in.</span></span>

1.  <span data-ttu-id="96db5-114">若要啟動 app-v 排序器，請在執行 app-v 排序器的電腦上，按一下 [**開始**  /  **所有程式**]  /  **microsoft application virtualization**  /  **microsoft application virtualization 排序**器。</span><span class="sxs-lookup"><span data-stu-id="96db5-114">To start the App-V Sequencer, on the computer that is running the App-V Sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="96db5-115">若要將現有的套件展開至執行排序器的電腦，請按一下 [**工具**]，將 [  /  **套件] 展開至 [本機系統**</span><span class="sxs-lookup"><span data-stu-id="96db5-115">To expand an existing package to the computer running the sequencer, click **Tools** / **Expand Package to Local System**.</span></span>

3.  <span data-ttu-id="96db5-116">流覽並選取您要展開的套件（**sprj**檔案），然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="96db5-116">Browse to and select the package (**.sprj** file) that you want to expand, and then click **Open**.</span></span> <span data-ttu-id="96db5-117">繼續執行下列程式。</span><span class="sxs-lookup"><span data-stu-id="96db5-117">Continue with the following procedure.</span></span>

**<span data-ttu-id="96db5-118">為新的附加元件或外掛程式應用程式排序</span><span class="sxs-lookup"><span data-stu-id="96db5-118">To sequence a new add-on or plug-in application</span></span>**

1.  <span data-ttu-id="96db5-119">若要啟動 app-v 排序器，請在執行 app-v 排序器的電腦上，按一下 [**開始**  /  **所有程式**]  /  **microsoft application virtualization**  /  **microsoft application virtualization 排序**器。</span><span class="sxs-lookup"><span data-stu-id="96db5-119">To start the App-V Sequencer, on the computer that is running the App-V Sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="96db5-120">若要啟動 [**建立新套件] 嚮導**，請按一下 [**建立新的虛擬應用程式套件**]。</span><span class="sxs-lookup"><span data-stu-id="96db5-120">To start the **Create New Package Wizard**, click **Create a New Virtual Application Package**.</span></span> <span data-ttu-id="96db5-121">若要建立套件，請選取 [**建立套件（預設）**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="96db5-121">To create the package, select **Create Package (default)**, and click then **Next**.</span></span>

3.  <span data-ttu-id="96db5-122">在 [**準備電腦**] 頁面上，查看可能導致套件建立失敗的問題，或套件中包含不必要的資料。</span><span class="sxs-lookup"><span data-stu-id="96db5-122">On the **Prepare Computer** page, review the issues that might cause the package creation to fail, or for the package to contain unnecessary data.</span></span> <span data-ttu-id="96db5-123">我們強烈建議您在繼續進行之前先解決所有潛在問題。</span><span class="sxs-lookup"><span data-stu-id="96db5-123">We strongly recommend that you resolve all potential issues before you continue.</span></span> <span data-ttu-id="96db5-124">修正衝突之後，若要更新顯示的資訊，**請按一下 [** 重新整理]。</span><span class="sxs-lookup"><span data-stu-id="96db5-124">After you have fixed the conflicts, to update the information displayed, click **Refresh**.</span></span> <span data-ttu-id="96db5-125">解決所有可能的問題之後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="96db5-125">After you have resolved all potential issues, click **Next**.</span></span>

    **<span data-ttu-id="96db5-126">重要</span><span class="sxs-lookup"><span data-stu-id="96db5-126">Important</span></span>**  
    <span data-ttu-id="96db5-127">如果您需要停用病毒掃描軟體，請掃描執行 sequencer 的電腦，以確保無法在套件中新增不需要的或惡意的檔案。</span><span class="sxs-lookup"><span data-stu-id="96db5-127">If you are required to disable virus scanning software, scan the computer running the sequencer to ensure that no unwanted or malicious files could be added to the package.</span></span>



4.  <span data-ttu-id="96db5-128">在 [**應用程式類型**] 頁面上，選取 [**附加元件] 或 [外掛程式]**，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="96db5-128">On the **Type of Application** page, select **Add-on or Plug-in**, and then click **Next**.</span></span>

    <span data-ttu-id="96db5-129">如需可排序之應用程式類型的詳細資訊，請參閱[如何判斷要順序的應用程式類型（app-v 4.6 SP1）](how-to-determine-which-type-of-application-to-sequence---app-v-46-sp1-.md)。</span><span class="sxs-lookup"><span data-stu-id="96db5-129">For more information about the types of applications that you can sequence, see [How to Determine Which Type of Application to Sequence (App-V 4.6 SP1)](how-to-determine-which-type-of-application-to-sequence---app-v-46-sp1-.md).</span></span>

5.  <span data-ttu-id="96db5-130">在 [**選取安裝程式**] 頁面上，按一下 **[流覽]** ，然後指定附加元件或外掛程式的安裝檔。</span><span class="sxs-lookup"><span data-stu-id="96db5-130">On the **Select Installer** page, click **Browse** and specify the installation file for the add-on or plug-in.</span></span> <span data-ttu-id="96db5-131">如果應用程式沒有關聯的安裝程式檔案，且您打算手動執行所有安裝步驟，請選取 [**選取此選項以執行自訂安裝**] 核取方塊，然後按一下 [**下一步]**。</span><span class="sxs-lookup"><span data-stu-id="96db5-131">If the application does not have an associated installer file and you plan to run all installation steps manually, select the **Select this option to perform a custom installation** check box, and then click **Next**.</span></span>

6.  <span data-ttu-id="96db5-132">在 [**選取主要**頁面] 上，按一下 **[流覽]** ，然後指定上層應用程式。</span><span class="sxs-lookup"><span data-stu-id="96db5-132">On the **Select Primary** page, click **Browse** and specify the parent application.</span></span>

    **<span data-ttu-id="96db5-133">重要</span><span class="sxs-lookup"><span data-stu-id="96db5-133">Important</span></span>**  
    <span data-ttu-id="96db5-134">如果您要安裝的附加元件或外掛程式無法在本機安裝，請停止這裡，然後在執行排序器的電腦上安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="96db5-134">If the parent application that the add-on or plug-in you are installing is going to support has not been installed locally, stop here and install the application on the computer running the sequencer.</span></span> <span data-ttu-id="96db5-135">例如，您必須在本機安裝 Microsoft Excel 外掛程式的**Excel.exe**程式檔。</span><span class="sxs-lookup"><span data-stu-id="96db5-135">For example, the **Excel.exe** program file must be installed locally for a Microsoft Excel plug-in.</span></span>



~~~
Click **Next**.
~~~

7. <span data-ttu-id="96db5-136">在 [**套件名稱**] 頁面上，指定將與套件建立關聯的名稱。</span><span class="sxs-lookup"><span data-stu-id="96db5-136">On the **Package Name** page, specify a name that will be associated with the package.</span></span> <span data-ttu-id="96db5-137">使用名稱，協助識別將新增到套件中之應用程式的用途和版本。</span><span class="sxs-lookup"><span data-stu-id="96db5-137">Use a name that helps identify the purpose and version of the application that will be added to the package.</span></span> <span data-ttu-id="96db5-138">套件名稱也會顯示在 App V 管理主控台中。</span><span class="sxs-lookup"><span data-stu-id="96db5-138">The package name will also be displayed in the App-V management console.</span></span> <span data-ttu-id="96db5-139">**安裝位置**會顯示應用程式的虛擬化路徑，將會安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="96db5-139">The **Installation Location** displays the Application Virtualization path where the application will be installed.</span></span> <span data-ttu-id="96db5-140">若要編輯此位置，請選取 **[編輯] （[高級]）**。</span><span class="sxs-lookup"><span data-stu-id="96db5-140">To edit this location, select **Edit (Advanced)**.</span></span>

   **<span data-ttu-id="96db5-141">重要</span><span class="sxs-lookup"><span data-stu-id="96db5-141">Important</span></span>**  
   <span data-ttu-id="96db5-142">編輯應用程式虛擬化路徑是一個高級的配置工作。</span><span class="sxs-lookup"><span data-stu-id="96db5-142">Editing the Application Virtualization path is an advanced configuration task.</span></span> <span data-ttu-id="96db5-143">您應該完全瞭解變更路徑的意義。</span><span class="sxs-lookup"><span data-stu-id="96db5-143">You should fully understand the implications of changing the path.</span></span> <span data-ttu-id="96db5-144">對於大部分的應用程式，我們建議預設路徑。</span><span class="sxs-lookup"><span data-stu-id="96db5-144">For most applications, we recommend the default path.</span></span>



~~~
Click **Next**.
~~~

8. <span data-ttu-id="96db5-145">在 [**安裝**] 頁面上，當排序器和應用程式安裝程式準備好時，請安裝外掛程式或增益集應用程式，讓排序器可以監視安裝程式。</span><span class="sxs-lookup"><span data-stu-id="96db5-145">On the **Installation** page, when the sequencer and application installer are ready, install the plug-in or add-in application so the sequencer can monitor the installation process.</span></span> <span data-ttu-id="96db5-146">使用應用程式的安裝程式來執行安裝。</span><span class="sxs-lookup"><span data-stu-id="96db5-146">Perform the installation by using the application’s installation process.</span></span> <span data-ttu-id="96db5-147">如果安裝時必須執行其他安裝檔案，請按一下 [**執行**]，然後找出並執行其他安裝檔案。</span><span class="sxs-lookup"><span data-stu-id="96db5-147">If additional installation files must be run as part of the installation, click **Run** and locate and run the additional installation files.</span></span> <span data-ttu-id="96db5-148">完成安裝後，請選取 [**我已完成安裝**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="96db5-148">When you are finished with the installation, select **I am finished installing**, and then click **Next**.</span></span>

9. <span data-ttu-id="96db5-149">在 [**安裝報告**] 頁面上，您可以查看剛剛排序的虛擬應用程式套件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="96db5-149">On the **Installation Report** page, you can review information about the virtual application package that you just sequenced.</span></span> <span data-ttu-id="96db5-150">如需**其他資訊**所顯示之資訊的詳細說明，請按兩下該事件。</span><span class="sxs-lookup"><span data-stu-id="96db5-150">For a more detailed explanation about the information displayed in **Additional Information**, double-click the event.</span></span> <span data-ttu-id="96db5-151">審閱資訊之後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="96db5-151">After you have reviewed the information, click **Next**.</span></span>

10. <span data-ttu-id="96db5-152">如果您已完成安裝並設定虛擬應用程式，請在 [**自訂**] 頁面上選取 [**立即停止**]，然後跳至此程式的步驟14。</span><span class="sxs-lookup"><span data-stu-id="96db5-152">On the **Customize** page, if you are finished installing and configuring the virtual application, select **Stop now** and skip to step 14 of this procedure.</span></span> <span data-ttu-id="96db5-153">如果您想要自訂以下清單中的任何專案，請選取 [**自訂**]。</span><span class="sxs-lookup"><span data-stu-id="96db5-153">If you want to customize any of the items in the following list, select **Customize**.</span></span>

    -   <span data-ttu-id="96db5-154">編輯與應用程式相關聯的檔案類型關聯。</span><span class="sxs-lookup"><span data-stu-id="96db5-154">Edit the file type associations associated with an application.</span></span>

    -   <span data-ttu-id="96db5-155">準備虛擬套件以進行流式處理。</span><span class="sxs-lookup"><span data-stu-id="96db5-155">Prepare the virtual package for streaming.</span></span> <span data-ttu-id="96db5-156">[資料流程] 可改善虛擬應用程式套件在目的電腦上執行時的體驗。</span><span class="sxs-lookup"><span data-stu-id="96db5-156">Streaming improves the experience when the virtual application package is run on target computers.</span></span>

    -   <span data-ttu-id="96db5-157">指定可以執行此套件的作業系統。</span><span class="sxs-lookup"><span data-stu-id="96db5-157">Specify the operating systems that can run this package.</span></span>

    <span data-ttu-id="96db5-158">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="96db5-158">Click **Next**.</span></span>

11. <span data-ttu-id="96db5-159">在 [**編輯快速鍵**] 頁面上，您可以選擇性地設定將與套件中各種應用程式相關聯的檔案類型關聯（FTA）。</span><span class="sxs-lookup"><span data-stu-id="96db5-159">On the **Edit Shortcuts** page, you can optionally configure the file type associations (FTA) that will be associated with the various applications in the package.</span></span> <span data-ttu-id="96db5-160">若要建立新的 FTA，請在左窗格中，選取並展開您要自訂的應用程式，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="96db5-160">To create a new FTA, in the left pane, select and expand the application that you want to customize, and then click **Add**.</span></span> <span data-ttu-id="96db5-161">在 [**新增檔案類型關聯**] 對話方塊中，為新的 FTA 提供必要的資訊。</span><span class="sxs-lookup"><span data-stu-id="96db5-161">In the **Add File Type Association** dialog box, provide the necessary information for the new FTA.</span></span> <span data-ttu-id="96db5-162">在應用程式底下，選取 [**快速鍵**]，查看與應用程式相關聯的快捷方式資訊。</span><span class="sxs-lookup"><span data-stu-id="96db5-162">Under the application, select **Shortcuts** to review the shortcut information associated with an application.</span></span> <span data-ttu-id="96db5-163">在 [**位置**] 窗格中，您可以查看圖示檔資訊。</span><span class="sxs-lookup"><span data-stu-id="96db5-163">In the **Location** pane, you can review the icon file information.</span></span> <span data-ttu-id="96db5-164">若要編輯現有的 FTA，請按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="96db5-164">To edit an existing FTA, click **Edit**.</span></span> <span data-ttu-id="96db5-165">若要移除 FTA，請選取 FTA，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="96db5-165">To remove an FTA, select the FTA, and then click **Remove**.</span></span> <span data-ttu-id="96db5-166">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="96db5-166">Click **Next**.</span></span>

12. <span data-ttu-id="96db5-167">在 [**流式處理**] 頁面上，執行每個程式，讓它能在目的電腦上優化並更有效率地執行。</span><span class="sxs-lookup"><span data-stu-id="96db5-167">On the **Streaming** page, run each program so that it can be optimized and run more efficiently on target computers.</span></span> <span data-ttu-id="96db5-168">可能需要幾分鐘的時間，所有應用程式才會執行。</span><span class="sxs-lookup"><span data-stu-id="96db5-168">It can take several minutes for all the applications to run.</span></span> <span data-ttu-id="96db5-169">在所有應用程式都已執行之後，請關閉每個應用程式，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="96db5-169">After all applications have run, close each of the applications, and then click **Next**.</span></span>

   **<span data-ttu-id="96db5-170">注意</span><span class="sxs-lookup"><span data-stu-id="96db5-170">Note</span></span>**  
   <span data-ttu-id="96db5-171">如果您想要在此步驟中停止載入應用程式，請在 [**應用程式啟動**] 對話方塊中，按一下 [**停止**]，然後選取其中一個核取方塊、[**停止所有應用程式**] 或 [**僅停止此應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="96db5-171">If you want to stop an application from loading during this step, in the **Application Launch** dialog box, click **Stop** and select one of the check boxes, **Stop all applications** or **Stop this application only**.</span></span>



13. <span data-ttu-id="96db5-172">在 [**目標作業系統**] 頁面上，指定可執行此套件的作業系統。</span><span class="sxs-lookup"><span data-stu-id="96db5-172">On the **Target OS** page, specify the operating systems that can run this package.</span></span> <span data-ttu-id="96db5-173">若要在您的環境中啟用所有受支援的作業系統來執行這個套件，請選取 [**允許此套件在任何作業系統上執行**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="96db5-173">To enable all supported operating systems in your environment to run this package, select the **Allow this package to run on any operating system** check box.</span></span> <span data-ttu-id="96db5-174">若要將這個套件設定為只在特定作業系統上執行，請選取 [**只允許此套件在下列作業系統上執行**] 核取方塊，然後選取可以執行此套件的作業系統。</span><span class="sxs-lookup"><span data-stu-id="96db5-174">To configure this package to run only on specific operating systems, select the **Allow this package to run only on the following operating systems** check box, and then select the operating systems that can run this package.</span></span> <span data-ttu-id="96db5-175">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="96db5-175">Click **Next**.</span></span>

14. <span data-ttu-id="96db5-176">在 [**建立套件**] 頁面上，若要修改套件但不儲存，請選取 **[繼續使用套件編輯器修改套件但不儲存**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="96db5-176">On the **Create Package** page, to modify the package without saving it, select **Continue to modify package without saving using the package editor** check box.</span></span> <span data-ttu-id="96db5-177">選取此選項會在 Sequencer 視窗中開啟套件，讓您可以在儲存套件之前加以修改。</span><span class="sxs-lookup"><span data-stu-id="96db5-177">Selecting this option opens the package in the Sequencer console so that you can modify the package before it is saved.</span></span> <span data-ttu-id="96db5-178">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="96db5-178">Click **Next**.</span></span>

   <span data-ttu-id="96db5-179">若要立即儲存套件，請選取 [**立即儲存套件**] 的預設值。</span><span class="sxs-lookup"><span data-stu-id="96db5-179">To save the package immediately, select the default **Save the package now**.</span></span> <span data-ttu-id="96db5-180">或者，您也可以選取 [**批註**]，以新增將與套件相關聯的批註。</span><span class="sxs-lookup"><span data-stu-id="96db5-180">Optionally, select **Comments** to add comments that will be associated with the package.</span></span> <span data-ttu-id="96db5-181">若要識別套件的版本及其他資訊，可以使用 [批註]。</span><span class="sxs-lookup"><span data-stu-id="96db5-181">Comments are useful for identifying version and other information about the package.</span></span> <span data-ttu-id="96db5-182">也會顯示預設的**儲存位置**。</span><span class="sxs-lookup"><span data-stu-id="96db5-182">The default **Save Location** is also displayed.</span></span> <span data-ttu-id="96db5-183">若要變更預設位置，請按一下 **[流覽]** ，然後指定新的位置。</span><span class="sxs-lookup"><span data-stu-id="96db5-183">To change the default location, click **Browse** and specify the new location.</span></span> <span data-ttu-id="96db5-184">隨即會顯示未壓縮的套件大小。</span><span class="sxs-lookup"><span data-stu-id="96db5-184">The uncompressed package size is displayed.</span></span> <span data-ttu-id="96db5-185">如果套件大小超過 4 GB （未壓縮），且您打算將套件資料流程資料流至目的電腦，您必須選取 [**壓縮套件**]。</span><span class="sxs-lookup"><span data-stu-id="96db5-185">If the package size exceeds 4 GB (uncompressed) and you plan to stream the package to target computers, you must select **Compress Package**.</span></span> <span data-ttu-id="96db5-186">按一下 \[建立\]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="96db5-186">Click **Create**.</span></span>

15. <span data-ttu-id="96db5-187">在 [**完成**] 頁面上，在您回顧了 [**成功的虛擬應用程式套件報告**] 窗格中顯示的資訊後，按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="96db5-187">On the **Completion** page, after you have reviewed the information that is displayed in the **Successful Virtual Application Package Report** pane, click **Close**.</span></span> <span data-ttu-id="96db5-188">[**成功的虛擬應用程式套件報告**] 窗格中顯示的資訊也適用于此程式步驟14（名為**Reports.xml**的檔案）中所指定的目錄。</span><span class="sxs-lookup"><span data-stu-id="96db5-188">The information displayed in the **Successful Virtual Application Package Report** pane is also available in the directory specified in step 14 of this procedure, in a file named **Reports.xml**.</span></span>

   <span data-ttu-id="96db5-189">套件現在可在 sequencer 中取得。</span><span class="sxs-lookup"><span data-stu-id="96db5-189">The package is now available in the sequencer.</span></span> <span data-ttu-id="96db5-190">按一下 **[編輯 \ [套件名稱 \]** 編輯套件屬性。</span><span class="sxs-lookup"><span data-stu-id="96db5-190">Click **Edit \[Package Name\]** to edit the package properties.</span></span> <span data-ttu-id="96db5-191">如需有關修改套件的詳細資訊，請參閱[如何修改現有的虛擬應用程式套件（app-v 4.6 SP1）](how-to-modify-an-existing-virtual-application-package--app-v-46-sp1-.md)。</span><span class="sxs-lookup"><span data-stu-id="96db5-191">For more information about modifying a package, see [How to Modify an Existing Virtual Application Package (App-V 4.6 SP1)](how-to-modify-an-existing-virtual-application-package--app-v-46-sp1-.md).</span></span>

   **<span data-ttu-id="96db5-192">重要</span><span class="sxs-lookup"><span data-stu-id="96db5-192">Important</span></span>**  
   <span data-ttu-id="96db5-193">成功建立虛擬應用程式套件之後，您就無法在執行排序器的電腦上執行虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="96db5-193">After you have successfully created a virtual application package, you cannot run the virtual application package on the computer that is running the sequencer.</span></span>



## <span data-ttu-id="96db5-194">相關主題</span><span class="sxs-lookup"><span data-stu-id="96db5-194">Related topics</span></span>


[<span data-ttu-id="96db5-195">Application Virtualization Sequencer 的工作 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="96db5-195">Tasks for the Application Virtualization Sequencer (App-V 4.6 SP1)</span></span>](tasks-for-the-application-virtualization-sequencer--app-v-46-sp1-.md)

[<span data-ttu-id="96db5-196">如何判斷要順序的應用程式類型（App-v 4.6 SP1）</span><span class="sxs-lookup"><span data-stu-id="96db5-196">How to Determine Which Type of Application to Sequence (App-V 4.6 SP1)</span></span>](how-to-determine-which-type-of-application-to-sequence---app-v-46-sp1-.md)









