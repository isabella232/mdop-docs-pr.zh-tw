---
title: 如何排序新的標準應用程式 (App-V 4.6 SP1)
description: 如何排序新的標準應用程式 (App-V 4.6 SP1)
author: dansimp
ms.assetid: c4a2eb33-def8-4535-b93a-3d2de21ce29f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 47c93b4880d0095c87a98292fda743acc1659e81
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801106"
---
# <span data-ttu-id="9da8d-103">如何排序新的標準應用程式 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="9da8d-103">How to Sequence a New Standard Application (App-V 4.6 SP1)</span></span>


<span data-ttu-id="9da8d-104">使用下列程式，透過應用程式虛擬化（App-v） Sequencer 來建立新的標準虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="9da8d-104">Use the following procedure to create a new standard virtual application package by using the Application Virtualization (App-V) Sequencer.</span></span> <span data-ttu-id="9da8d-105">此程式適用于您所排序的大部分應用程式。</span><span class="sxs-lookup"><span data-stu-id="9da8d-105">This procedure applies to most applications that you sequence.</span></span> <span data-ttu-id="9da8d-106">如需有關您可以排序之應用程式類型的詳細資訊，請參閱[如何判斷要順序的應用程式類型（app-v 4.6 SP1）](how-to-determine-which-type-of-application-to-sequence---app-v-46-sp1-.md)。</span><span class="sxs-lookup"><span data-stu-id="9da8d-106">For more information about the types of applications you can sequence, see [How to Determine Which Type of Application to Sequence (App-V 4.6 SP1)](how-to-determine-which-type-of-application-to-sequence---app-v-46-sp1-.md).</span></span> <span data-ttu-id="9da8d-107">您必須使用具有系統管理員許可權的帳戶來執行 sequencer （**SFTSequencer.exe**），因為排序器對本機系統所做的變更。</span><span class="sxs-lookup"><span data-stu-id="9da8d-107">You must run the sequencer (**SFTSequencer.exe**) using an account that has administrator privileges because of the changes the sequencer makes to the local system.</span></span> <span data-ttu-id="9da8d-108">這些變更可以包括將檔案寫入**C:\\program files files**目錄、進行登錄、啟動及停止服務、更新檔案的安全性描述項，以及變更許可權。</span><span class="sxs-lookup"><span data-stu-id="9da8d-108">These changes can include writing files to the **C:\\Program Files** directory, making registry changes, starting and stopping services, updating security descriptors for files, and changing permissions.</span></span>

**<span data-ttu-id="9da8d-109">重要</span><span class="sxs-lookup"><span data-stu-id="9da8d-109">Important</span></span>**  
<span data-ttu-id="9da8d-110">在排序期間，如果執行 Sequencer 的電腦是執行 Windows Vista 或 Windows 7，且在虛擬環境之外啟動重新開機，例如**開始**  /  **關閉**，則當系統提示您關閉阻礙 Windows vista 或 windows 關閉的程式時，您必須按一下 [**取消**]。</span><span class="sxs-lookup"><span data-stu-id="9da8d-110">During sequencing, if the computer running the Sequencer is running Windows Vista or Windows 7 and a restart is initiated outside of the virtual environment, for example, **Start** / **Shut Down**, you must click **Cancel** when prompted to close the program that is preventing Windows Vista or Windows from shutting down.</span></span> <span data-ttu-id="9da8d-111">如果您按一下 [**強制關閉**]，套件建立就會失敗。</span><span class="sxs-lookup"><span data-stu-id="9da8d-111">If you click **Force shut down**, the package creation fails.</span></span> <span data-ttu-id="9da8d-112">當您按一下 [**取消**] 時，Sequencer 會在應用程式排序時成功記錄重新開機。</span><span class="sxs-lookup"><span data-stu-id="9da8d-112">When you click **Cancel**, the Sequencer successfully records the restart while the application is being sequenced.</span></span>



**<span data-ttu-id="9da8d-113">注意</span><span class="sxs-lookup"><span data-stu-id="9da8d-113">Note</span></span>**  
<span data-ttu-id="9da8d-114">在安全模式中執行 App-v 排序器不受支援。</span><span class="sxs-lookup"><span data-stu-id="9da8d-114">Running the App-V sequencer in Safe Mode is not supported.</span></span>



**<span data-ttu-id="9da8d-115">為新的標準應用程式排序</span><span class="sxs-lookup"><span data-stu-id="9da8d-115">To sequence a new standard application</span></span>**

1.  <span data-ttu-id="9da8d-116">若要啟動 app-v 排序器，請在執行 app-v 排序器的電腦上，按一下 [**開始**  /  **所有程式**]  /  **microsoft application virtualization**  /  **microsoft application virtualization 排序**器。</span><span class="sxs-lookup"><span data-stu-id="9da8d-116">To start the App-V Sequencer, on the computer that is running the App-V Sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="9da8d-117">若要啟動 [**建立新套件] 嚮導**，請按一下 [**建立新的虛擬應用程式套件**]。</span><span class="sxs-lookup"><span data-stu-id="9da8d-117">To start the **Create New Package Wizard**, click **Create a New Virtual Application Package**.</span></span> <span data-ttu-id="9da8d-118">若要建立套件，請選取 [**建立套件（預設）**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="9da8d-118">To create the package, select **Create Package (default)**, and then click **Next**.</span></span>

3.  <span data-ttu-id="9da8d-119">在 [**準備電腦**] 頁面上，查看可能導致套件建立失敗的問題，或針對套件包含不必要的資料。</span><span class="sxs-lookup"><span data-stu-id="9da8d-119">On the **Prepare Computer** page, review the issues that could cause the package creation to fail, or for the package to contain unnecessary data.</span></span> <span data-ttu-id="9da8d-120">我們強烈建議您在繼續進行之前先解決所有潛在問題。</span><span class="sxs-lookup"><span data-stu-id="9da8d-120">We strongly recommend that you resolve all potential issues before you continue.</span></span> <span data-ttu-id="9da8d-121">修正衝突之後，若要更新所顯示的資訊，**請按一下 [** 重新整理]。</span><span class="sxs-lookup"><span data-stu-id="9da8d-121">After you have fixed the conflicts, to update the information that is displayed, click **Refresh**.</span></span> <span data-ttu-id="9da8d-122">解決所有可能的問題之後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="9da8d-122">After you have resolved all potential issues, click **Next**.</span></span>

    **<span data-ttu-id="9da8d-123">重要</span><span class="sxs-lookup"><span data-stu-id="9da8d-123">Important</span></span>**  
    <span data-ttu-id="9da8d-124">如果您需要停用病毒掃描軟體，請掃描執行 Sequencer 的電腦，以確保無法在套件中新增不需要的或惡意的檔案。</span><span class="sxs-lookup"><span data-stu-id="9da8d-124">If you are required to disable virus scanning software, scan the computer running the Sequencer to ensure that no unwanted or malicious files could be added to the package.</span></span>



4.  <span data-ttu-id="9da8d-125">在 [**應用程式類型**] 頁面上，按一下 [**標準應用程式（預設）** ] 核取方塊，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="9da8d-125">On the **Type of Application** page, click **Standard Application (default)** check box, and then click **Next**.</span></span>

    <span data-ttu-id="9da8d-126">如需可排序之應用程式類型的詳細資訊，請參閱[如何判斷要順序的應用程式類型（app-v 4.6 SP1）](how-to-determine-which-type-of-application-to-sequence---app-v-46-sp1-.md)。</span><span class="sxs-lookup"><span data-stu-id="9da8d-126">For more information about the types of applications that you can sequence, see [How to Determine Which Type of Application to Sequence (App-V 4.6 SP1)](how-to-determine-which-type-of-application-to-sequence---app-v-46-sp1-.md).</span></span>

5.  <span data-ttu-id="9da8d-127">在 [**選取安裝程式**] 頁面上，按一下 **[流覽]** ，然後指定應用程式的安裝檔。</span><span class="sxs-lookup"><span data-stu-id="9da8d-127">On the **Select Installer** page, click **Browse** and specify the installation file for the application.</span></span> <span data-ttu-id="9da8d-128">如果應用程式沒有關聯的安裝程式檔案，且您打算手動執行所有安裝步驟，請選取 [**執行自訂安裝**] 核取方塊，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="9da8d-128">If the application does not have an associated installer file and you plan to run all installation steps manually, select the **Perform a Custom Installation** check box, and then Click **Next**.</span></span>

6.  <span data-ttu-id="9da8d-129">在 [**套件名稱**] 頁面上，指定將與套件建立關聯的名稱。</span><span class="sxs-lookup"><span data-stu-id="9da8d-129">On the **Package Name** page, specify a name that will be associated with the package.</span></span> <span data-ttu-id="9da8d-130">名稱可協助識別已新增到套件中之應用程式的用途和版本。</span><span class="sxs-lookup"><span data-stu-id="9da8d-130">The name helps identify the purpose and version of the application that are added to the package.</span></span> <span data-ttu-id="9da8d-131">套件名稱也會顯示在 App V 管理主控台中。</span><span class="sxs-lookup"><span data-stu-id="9da8d-131">The package name is also displayed in the App-V management console.</span></span> <span data-ttu-id="9da8d-132">**主要虛擬應用程式目錄**會顯示應用程式虛擬化路徑，應用程式將會安裝在目的電腦上。</span><span class="sxs-lookup"><span data-stu-id="9da8d-132">The **Primary Virtual Application Directory** displays the Application Virtualization path where the application will be installed on target computers.</span></span> <span data-ttu-id="9da8d-133">若要編輯此位置，請選取 **[編輯] （[高級]）**。</span><span class="sxs-lookup"><span data-stu-id="9da8d-133">To edit this location, select **Edit (Advanced)**.</span></span>

    **<span data-ttu-id="9da8d-134">重要</span><span class="sxs-lookup"><span data-stu-id="9da8d-134">Important</span></span>**  
    <span data-ttu-id="9da8d-135">編輯應用程式虛擬化路徑是一個高級的配置工作。</span><span class="sxs-lookup"><span data-stu-id="9da8d-135">Editing the Application Virtualization path is an advanced configuration task.</span></span> <span data-ttu-id="9da8d-136">您應該完全瞭解變更路徑的意義。</span><span class="sxs-lookup"><span data-stu-id="9da8d-136">You should fully understand the implications of changing the path.</span></span> <span data-ttu-id="9da8d-137">在大部分的應用程式中，建議使用預設路徑。</span><span class="sxs-lookup"><span data-stu-id="9da8d-137">For most applications, the default path is recommended.</span></span>



~~~
Click **Next**.
~~~

7. <span data-ttu-id="9da8d-138">在 [**安裝**] 頁面上，當排序器和應用程式安裝程式準備好時，請安裝應用程式，讓排序器可以監視安裝程式。</span><span class="sxs-lookup"><span data-stu-id="9da8d-138">On the **Installation** page, when the Sequencer and application installer are ready, install the application so that the Sequencer can monitor the installation process.</span></span> <span data-ttu-id="9da8d-139">使用應用程式的安裝程式來執行安裝。</span><span class="sxs-lookup"><span data-stu-id="9da8d-139">Perform the installation by using the application’s installation process.</span></span> <span data-ttu-id="9da8d-140">如果安裝時必須執行其他安裝檔案，請按一下 [**執行**]，找出並執行其他安裝檔案。</span><span class="sxs-lookup"><span data-stu-id="9da8d-140">If additional installation files must be run as part of the installation, click **Run** to locate and run the additional installation files.</span></span> <span data-ttu-id="9da8d-141">完成安裝後，請選取 [**我已完成安裝**]。</span><span class="sxs-lookup"><span data-stu-id="9da8d-141">When you are finished with the installation, select **I am finished installing**.</span></span> <span data-ttu-id="9da8d-142">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="9da8d-142">Click **Next**.</span></span>

8. <span data-ttu-id="9da8d-143">在 [**安裝**] 頁面上，請稍候，Sequencer 會設定虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="9da8d-143">On the **Installation** page, wait while the Sequencer configures the virtual application package.</span></span>

9. <span data-ttu-id="9da8d-144">在 [**設定軟體**] 頁面上，選擇性地執行套件中包含的程式。</span><span class="sxs-lookup"><span data-stu-id="9da8d-144">On the **Configure Software** page, optionally run the programs contained in the package.</span></span> <span data-ttu-id="9da8d-145">此步驟可協助您完成在您部署並在目的電腦上執行套件之前，執行應用程式所需的任何相關授權或配置工作。</span><span class="sxs-lookup"><span data-stu-id="9da8d-145">This step helps complete any associated license or configuration tasks that are required to run the application before you deploy and run the package on target computers.</span></span> <span data-ttu-id="9da8d-146">若要一次執行所有程式，請選取至少一個程式，然後按一下 [**全部執行**]。</span><span class="sxs-lookup"><span data-stu-id="9da8d-146">To run all the programs at one time, select at least one program, and then click **Run All**.</span></span> <span data-ttu-id="9da8d-147">若要執行特定程式，請選取您要執行的程式或程式，然後按一下 [**執行選取**的專案]。</span><span class="sxs-lookup"><span data-stu-id="9da8d-147">To run specific programs, select the program or programs you want to run, and then click **Run Selected**.</span></span> <span data-ttu-id="9da8d-148">完成所需的配置工作，然後關閉應用程式。</span><span class="sxs-lookup"><span data-stu-id="9da8d-148">Complete the required configuration tasks and then close the applications.</span></span> <span data-ttu-id="9da8d-149">所有程式都可能需要幾分鐘的時間才能執行。</span><span class="sxs-lookup"><span data-stu-id="9da8d-149">It can take several minutes for all programs to run.</span></span> <span data-ttu-id="9da8d-150">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="9da8d-150">Click **Next**.</span></span>

10. <span data-ttu-id="9da8d-151">在 [**安裝報告**] 頁面上，您可以查看您剛剛排序的虛擬應用程式套件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="9da8d-151">On the **Installation Report** page, you can review information about the virtual application package you just sequenced.</span></span> <span data-ttu-id="9da8d-152">如需**其他資訊**所顯示之資訊的詳細說明，請按兩下該事件。</span><span class="sxs-lookup"><span data-stu-id="9da8d-152">For a more detailed explanation about the information displayed in **Additional Information**, double-click the event.</span></span> <span data-ttu-id="9da8d-153">審閱資訊之後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="9da8d-153">After you have reviewed the information, click **Next**.</span></span>

11. <span data-ttu-id="9da8d-154">在 [**自訂**] 頁面上，如果您已完成安裝並設定虛擬應用程式，請選取 [**立即停止**]，然後跳至此程式的步驟15。</span><span class="sxs-lookup"><span data-stu-id="9da8d-154">On the **Customize** page, if you are finished installing and configuring the virtual application, select **Stop now** and skip to step 15 of this procedure.</span></span> <span data-ttu-id="9da8d-155">如果您想要自訂以下清單中的任何專案，請選取 [**自訂**]。</span><span class="sxs-lookup"><span data-stu-id="9da8d-155">If you want to customize any of the items in the following list, select **Customize**.</span></span>

    -   <span data-ttu-id="9da8d-156">編輯檔案類型關聯及與應用程式相關聯的圖示。</span><span class="sxs-lookup"><span data-stu-id="9da8d-156">Edit the file type associations and the icons associated with an application.</span></span>

    -   <span data-ttu-id="9da8d-157">準備虛擬套件以進行流式處理。</span><span class="sxs-lookup"><span data-stu-id="9da8d-157">Prepare the virtual package for streaming.</span></span> <span data-ttu-id="9da8d-158">[資料流程] 可改善虛擬應用程式套件在目的電腦上執行時的體驗。</span><span class="sxs-lookup"><span data-stu-id="9da8d-158">Streaming improves the experience when the virtual application package is run on target computers.</span></span>

    -   <span data-ttu-id="9da8d-159">指定可以執行此套件的作業系統。</span><span class="sxs-lookup"><span data-stu-id="9da8d-159">Specify the operating systems that can run this package.</span></span>

    <span data-ttu-id="9da8d-160">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="9da8d-160">Click **Next**.</span></span>

12. <span data-ttu-id="9da8d-161">在 [**編輯快速鍵**] 頁面上，您可以選擇性地設定檔案類型關聯（FTA），以及將與套件中各種應用程式相關聯的快捷方式位置。</span><span class="sxs-lookup"><span data-stu-id="9da8d-161">On the **Edit Shortcuts** page, you can optionally configure the file type associations (FTA) and shortcut locations that will be associated with the various applications in the package.</span></span> <span data-ttu-id="9da8d-162">若要建立新的 FTA，請在左窗格中，選取並展開您要自訂的應用程式，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="9da8d-162">To create a new FTA, in the left pane, select and expand the application you want to customize, and then click **Add**.</span></span> <span data-ttu-id="9da8d-163">在 [**新增檔案類型關聯**] 對話方塊中，為新的 FTA 提供必要的資訊。</span><span class="sxs-lookup"><span data-stu-id="9da8d-163">In the **Add File Type Association** dialog box, provide the necessary information for the new FTA.</span></span> <span data-ttu-id="9da8d-164">若要查看與應用程式相關聯的快捷方式資訊，請在應用程式底下選取 [**快速鍵**]，然後在 [**位置**] 窗格中，您可以編輯圖示檔資訊。</span><span class="sxs-lookup"><span data-stu-id="9da8d-164">To review the shortcut information associated with an application, under the application, select **Shortcuts**, and in the **Location** pane, you can edit the icon file information.</span></span> <span data-ttu-id="9da8d-165">若要編輯現有的 FTA，請按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="9da8d-165">To edit an existing FTA, click **Edit**.</span></span> <span data-ttu-id="9da8d-166">若要移除 FTA，請選取 FTA，然後按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="9da8d-166">To remove an FTA, select the FTA, and then click **Remove**.</span></span> <span data-ttu-id="9da8d-167">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="9da8d-167">Click **Next**.</span></span>

13. <span data-ttu-id="9da8d-168">在 [**流式處理**] 頁面上，執行每個程式，讓它能在目的電腦上優化並更有效率地執行。</span><span class="sxs-lookup"><span data-stu-id="9da8d-168">On the **Streaming** page, run each program so that it can be optimized and run more efficiently on target computers.</span></span> <span data-ttu-id="9da8d-169">可能需要幾分鐘的時間，所有應用程式才會執行。</span><span class="sxs-lookup"><span data-stu-id="9da8d-169">It can take several minutes for all the applications to run.</span></span> <span data-ttu-id="9da8d-170">在所有應用程式都已執行之後，請關閉每個應用程式，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="9da8d-170">After all applications have run, close each of the applications, and then click **Next**.</span></span>

   **<span data-ttu-id="9da8d-171">注意</span><span class="sxs-lookup"><span data-stu-id="9da8d-171">Note</span></span>**  
   <span data-ttu-id="9da8d-172">如果您想要在此步驟中停止載入應用程式，請在 [**應用程式啟動**] 對話方塊中，按一下 [**停止**]，然後選取其中一個核取方塊、[**停止所有應用程式**] 或 [**僅停止此應用程式**] （視您的需求而定）。</span><span class="sxs-lookup"><span data-stu-id="9da8d-172">If you want to stop an application from loading during this step, in the **Application Launch** dialog box, click **Stop**, and select one of the check boxes, **Stop all applications** or **Stop this application only**, depending on what you want.</span></span>



14. <span data-ttu-id="9da8d-173">在 [**目標作業系統**] 頁面上，指定可執行此套件的作業系統。</span><span class="sxs-lookup"><span data-stu-id="9da8d-173">On the **Target OS** page, specify the operating systems that can run this package.</span></span> <span data-ttu-id="9da8d-174">若要在您的環境中啟用所有受支援的作業系統來執行這個套件，請選取 [**允許此套件在任何作業系統上執行**]。</span><span class="sxs-lookup"><span data-stu-id="9da8d-174">To enable all supported operating systems in your environment to run this package, select **Allow this package to run on any operating system**.</span></span> <span data-ttu-id="9da8d-175">若要將這個套件設定為只在特定作業系統上執行，請選取 [**只允許此套件在下列作業系統上**執行]，並指定可執行此套件的作業系統。</span><span class="sxs-lookup"><span data-stu-id="9da8d-175">To configure this package to run only on specific operating systems, select **Allow this package to run only on the following operating systems** and specify the operating systems that can run this package.</span></span> <span data-ttu-id="9da8d-176">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="9da8d-176">Click **Next**.</span></span>

   **<span data-ttu-id="9da8d-177">重要</span><span class="sxs-lookup"><span data-stu-id="9da8d-177">Important</span></span>**  
   <span data-ttu-id="9da8d-178">此步驟中指定的作業系統會反映已啟用可執行套件的目的電腦作業系統。</span><span class="sxs-lookup"><span data-stu-id="9da8d-178">The operating systems specified during this step reflect the operating systems on target computers that are enabled to run the package.</span></span> <span data-ttu-id="9da8d-179">您必須確保您所排序的應用程式支援所指定的作業系統。</span><span class="sxs-lookup"><span data-stu-id="9da8d-179">You must ensure that the operating systems specified are supported by the application you are sequencing.</span></span>



15. <span data-ttu-id="9da8d-180">在 [**建立套件**] 頁面上，若要修改套件但不儲存，請選取 **[繼續]，不使用 [封裝編輯器] 儲存來修改套件**。</span><span class="sxs-lookup"><span data-stu-id="9da8d-180">On the **Create Package** page, to modify the package without saving it, select **Continue to modify package without saving using the package editor**.</span></span> <span data-ttu-id="9da8d-181">選取此選項會在 Sequencer 視窗中開啟套件，讓您可以在儲存套件之前加以修改。</span><span class="sxs-lookup"><span data-stu-id="9da8d-181">Selecting this option opens the package in the Sequencer console so that you can modify the package before it is saved.</span></span> <span data-ttu-id="9da8d-182">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="9da8d-182">Click **Next**.</span></span>

   <span data-ttu-id="9da8d-183">若要立即儲存套件，請選取 [**立即儲存套件**] 的預設值。</span><span class="sxs-lookup"><span data-stu-id="9da8d-183">To save the package immediately, select the default **Save the package now**.</span></span> <span data-ttu-id="9da8d-184">新增將與套件相關聯的選擇性**批註**。</span><span class="sxs-lookup"><span data-stu-id="9da8d-184">Add optional **Comments** that will be associated with the package.</span></span> <span data-ttu-id="9da8d-185">若要識別套件的版本及其他資訊，可以使用 [批註]。</span><span class="sxs-lookup"><span data-stu-id="9da8d-185">Comments are useful for identifying version and other information about the package.</span></span> <span data-ttu-id="9da8d-186">也會顯示預設的**儲存位置**。</span><span class="sxs-lookup"><span data-stu-id="9da8d-186">The default **Save Location** is also displayed.</span></span> <span data-ttu-id="9da8d-187">若要變更預設位置，請按一下 **[流覽]** ，然後指定新的位置。</span><span class="sxs-lookup"><span data-stu-id="9da8d-187">To change the default location, click **Browse** and specify the new location.</span></span> <span data-ttu-id="9da8d-188">隨即會顯示未壓縮的套件大小。</span><span class="sxs-lookup"><span data-stu-id="9da8d-188">The uncompressed package size is displayed.</span></span> <span data-ttu-id="9da8d-189">如果套件大小超過 4 GB （未壓縮），且您打算將套件資料流程資料流至目的電腦，您必須選取 [**壓縮套件**]。</span><span class="sxs-lookup"><span data-stu-id="9da8d-189">If the package size exceeds 4 GB (uncompressed) and you plan to stream the package to target computers, you must select **Compress Package**.</span></span> <span data-ttu-id="9da8d-190">按一下 \[建立\]\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9da8d-190">Click **Create**.</span></span>

16. <span data-ttu-id="9da8d-191">在 [**完成**] 頁面上，檢查 [**虛擬應用程式套件報告**] 窗格中顯示的資訊後，按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="9da8d-191">On the **Completion** page, after you have reviewed the information displayed in the **Virtual Application Package Report** pane, click **Close**.</span></span> <span data-ttu-id="9da8d-192">在 [**虛擬應用程式套件報告**] 窗格中顯示的資訊，也可在此程式的步驟15中指定的目錄中取得，在名為**Report.xml**的檔案中提供。</span><span class="sxs-lookup"><span data-stu-id="9da8d-192">The information displayed in the **Virtual Application Package Report** pane is also available in the directory specified in step 15 of this procedure, in a file named **Report.xml**.</span></span>

    <span data-ttu-id="9da8d-193">套件現在可在 Sequencer 中取得。</span><span class="sxs-lookup"><span data-stu-id="9da8d-193">The package is now available in the Sequencer.</span></span> <span data-ttu-id="9da8d-194">若要編輯套件屬性，請按一下 **[編輯 \ [套件名稱 \]]**。</span><span class="sxs-lookup"><span data-stu-id="9da8d-194">To edit the package properties, click **Edit \[Package Name\]**.</span></span> <span data-ttu-id="9da8d-195">如需有關修改套件的詳細資訊，請參閱[如何修改現有的虛擬應用程式套件（app-v 4.6 SP1）](how-to-modify-an-existing-virtual-application-package--app-v-46-sp1-.md)</span><span class="sxs-lookup"><span data-stu-id="9da8d-195">For more information about modifying a package, see [How to Modify an Existing Virtual Application Package (App-V 4.6 SP1)](how-to-modify-an-existing-virtual-application-package--app-v-46-sp1-.md)</span></span>

    **<span data-ttu-id="9da8d-196">重要</span><span class="sxs-lookup"><span data-stu-id="9da8d-196">Important</span></span>**  
    <span data-ttu-id="9da8d-197">成功建立虛擬應用程式套件之後，您就無法在執行排序器的電腦上執行虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="9da8d-197">After you have successfully created a virtual application package, you cannot run the virtual application package on the computer that is running the Sequencer.</span></span>



## <span data-ttu-id="9da8d-198">相關主題</span><span class="sxs-lookup"><span data-stu-id="9da8d-198">Related topics</span></span>


[<span data-ttu-id="9da8d-199">Application Virtualization Sequencer 的工作 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="9da8d-199">Tasks for the Application Virtualization Sequencer (App-V 4.6 SP1)</span></span>](tasks-for-the-application-virtualization-sequencer--app-v-46-sp1-.md)

[<span data-ttu-id="9da8d-200">如何判斷要順序的應用程式類型（App-v 4.6 SP1）</span><span class="sxs-lookup"><span data-stu-id="9da8d-200">How to Determine Which Type of Application to Sequence (App-V 4.6 SP1)</span></span>](how-to-determine-which-type-of-application-to-sequence---app-v-46-sp1-.md)









