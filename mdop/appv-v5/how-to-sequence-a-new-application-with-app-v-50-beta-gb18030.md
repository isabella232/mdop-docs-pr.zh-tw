---
title: 如何使用 App-V 5.0 為新應用程式進行序列化
description: 如何使用 App-V 5.0 為新應用程式進行序列化
author: dansimp
ms.assetid: a263fa84-cd6d-4219-a5c2-eb6a553b826c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 13fdda066f79d918da1970e0cab6c1d6e60f6585
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800414"
---
# <span data-ttu-id="f4ca1-103">如何使用 App-V 5.0 為新應用程式進行序列化</span><span class="sxs-lookup"><span data-stu-id="f4ca1-103">How to Sequence a New Application with App-V 5.0</span></span>


**<span data-ttu-id="f4ca1-104">若要在開始排序前查看或執行</span><span class="sxs-lookup"><span data-stu-id="f4ca1-104">To review or do before you start sequencing</span></span>**

1.  <span data-ttu-id="f4ca1-105">判斷您想要建立的虛擬化應用程式套件類型：</span><span class="sxs-lookup"><span data-stu-id="f4ca1-105">Determine the type of virtualized application package you want to create:</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="f4ca1-106">應用程式類型</span><span class="sxs-lookup"><span data-stu-id="f4ca1-106">Application type</span></span></th>
    <th align="left"><span data-ttu-id="f4ca1-107">描述</span><span class="sxs-lookup"><span data-stu-id="f4ca1-107">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="f4ca1-108">Standard</span><span class="sxs-lookup"><span data-stu-id="f4ca1-108">Standard</span></span></p></td>
    <td align="left"><p><span data-ttu-id="f4ca1-109">建立包含應用程式或應用程式套件的套件。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-109">Creates a package that contains an application or a suite of applications.</span></span> <span data-ttu-id="f4ca1-110">這是大部分應用程式類型的首選選項。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-110">This is the preferred option for most application types.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="f4ca1-111">附加元件或外掛程式</span><span class="sxs-lookup"><span data-stu-id="f4ca1-111">Add-on or plug-in</span></span></p></td>
    <td align="left"><p><span data-ttu-id="f4ca1-112">建立可延伸標準應用程式功能的套件，例如 Microsoft Excel 的外掛程式。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-112">Creates a package that extends the functionality of a standard application, for example, a plug-in for Microsoft Excel.</span></span> <span data-ttu-id="f4ca1-113">此外，您也可以將外掛程式用於本機已安裝的應用程式，或針對使用連線群組連結的其他套件使用外掛程式。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-113">Additionally, you can use plug-ins for natively installed applications, or for another package that is linked by using connection groups.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="f4ca1-114">中介軟體</span><span class="sxs-lookup"><span data-stu-id="f4ca1-114">Middleware</span></span></p></td>
    <td align="left"><p><span data-ttu-id="f4ca1-115">建立標準應用程式所需的套件（例如，JAVA）。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-115">Creates a package that is required by a standard application, for example, Java.</span></span> <span data-ttu-id="f4ca1-116">中介軟體套件是使用連線群組來連結到其他套件。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-116">Middleware packages are used for linking to other packages by using connection groups.</span></span></p></td>
    </tr>
    </tbody>
    </table>



2.  <span data-ttu-id="f4ca1-117">將所有所需的安裝檔案複製到執行排序器的電腦上。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-117">Copy all required installation files to the computer that is running the sequencer.</span></span>

3.  <span data-ttu-id="f4ca1-118">將應用程式排序前，請先製作虛擬環境的備份影像，然後在您完成應用程式的排序之後，每次都要還原到該影像。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-118">Make a backup image of your virtual environment before sequencing an application, and then revert to that image each time after you finish sequencing an application.</span></span>

4.  <span data-ttu-id="f4ca1-119">檢查下列專案：</span><span class="sxs-lookup"><span data-stu-id="f4ca1-119">Review the following items:</span></span>

    -   <span data-ttu-id="f4ca1-120">如果應用程式安裝程式將安全性存取變更為新的或現有的檔案或目錄，就不會在套件中捕獲這些變更。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-120">If an application installer changes the security access to a new or existing file or directory, those changes are not captured in the package.</span></span>

    -   <span data-ttu-id="f4ca1-121">如果已針對虛擬化套件的目標卷停用短路徑，您也必須將套件排序為已建立且仍有停用短路徑的磁片。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-121">If short paths have been disabled for the virtualized package’s target volume, you must also sequence the package to a volume that was created and still has short-paths disabled.</span></span> <span data-ttu-id="f4ca1-122">它不可以是系統音量。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-122">It cannot be the system volume.</span></span>

    -   <span data-ttu-id="f4ca1-123">從 App-v 5.0 SP3 開始，主要虛擬應用程式目錄（PVAD）是隱藏的，但您可以將它重新開啟。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-123">Starting in App-V 5.0 SP3, the primary virtual application directory (PVAD) is hidden, but you can turn it back on.</span></span> <span data-ttu-id="f4ca1-124">請參閱[關於 App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-pvad-hidden)。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-124">See [About App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-pvad-hidden).</span></span>

**<span data-ttu-id="f4ca1-125">為新的標準應用程式排序</span><span class="sxs-lookup"><span data-stu-id="f4ca1-125">To sequence a new standard application</span></span>**

1.  <span data-ttu-id="f4ca1-126">在執行排序器的電腦上，按一下 [**所有程式**]，然後按一下 [ **microsoft application**virtualization]，然後按一下 [ **microsoft application virtualization 排序**器]。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-126">On the computer that runs the sequencer, click **All Programs**, and then Click **Microsoft Application Virtualization**, and then click **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="f4ca1-127">在排序器中，按一下 [**建立新的虛擬應用程式套件**]。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-127">In the sequencer, click **Create a New Virtual Application Package**.</span></span> <span data-ttu-id="f4ca1-128">選取 [**建立套件（預設）**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-128">Select **Create Package (default)**, and then click **Next**.</span></span>

3.  <span data-ttu-id="f4ca1-129">在 [**準備電腦**] 頁面上，查看可能導致套件建立失敗的問題，或可能導致套件包含不必要的資料。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-129">On the **Prepare Computer** page, review the issues that could cause the package creation to fail or could cause the package to contain unnecessary data.</span></span> <span data-ttu-id="f4ca1-130">繼續進行之前，您應該先解決所有潛在問題。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-130">You should resolve all potential issues before you continue.</span></span> <span data-ttu-id="f4ca1-131">進行任何修正之後 **，按一下 [** 重新整理] 以顯示更新的資訊。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-131">After making any corrections, click **Refresh** to display the updated information.</span></span> <span data-ttu-id="f4ca1-132">解決所有可能的問題之後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-132">After you have resolved all potential issues, click **Next**.</span></span>

    **<span data-ttu-id="f4ca1-133">重要</span><span class="sxs-lookup"><span data-stu-id="f4ca1-133">Important</span></span>**  
    <span data-ttu-id="f4ca1-134">如果您需要停用病毒掃描軟體，您應該先掃描執行 sequencer 的電腦，以確保無法將不想要的或惡意檔案新增到套件中。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-134">If you are required to disable virus scanning software, you should first scan the computer that runs the sequencer in order to ensure that no unwanted or malicious files could be added to the package.</span></span>



4.  <span data-ttu-id="f4ca1-135">在 [**應用程式類型**] 頁面上，按一下 [**標準應用程式（預設）** ] 核取方塊，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-135">On the **Type of Application** page, click the **Standard Application (default)** check box, and then click **Next**.</span></span>

5.  <span data-ttu-id="f4ca1-136">在 [**選取安裝程式**] 頁面上，按一下 **[流覽]** ，然後指定應用程式的安裝檔。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-136">On the **Select Installer** page, click **Browse** and specify the installation file for the application.</span></span>

    **<span data-ttu-id="f4ca1-137">注意</span><span class="sxs-lookup"><span data-stu-id="f4ca1-137">Note</span></span>**  
    <span data-ttu-id="f4ca1-138">如果指定的應用程式安裝程式修改檔案或目錄的安全性存取（現有或新），將不會將相關的變更捕獲到套件中。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-138">If the specified application installer modifies security access to a file or directory, existing or new, the associated changes will not be captured into the package.</span></span>



~~~
If the application does not have an associated installer file and you plan to run all installation steps manually, select the **Perform a Custom Installation** check box, and then Click **Next**.
~~~

6. <span data-ttu-id="f4ca1-139">在 [**套件名稱**] 頁面上，輸入將與套件建立關聯的名稱。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-139">On the **Package Name** page, type a name that will be associated with the package.</span></span> <span data-ttu-id="f4ca1-140">使用名稱，協助識別將新增到套件中之應用程式的用途和版本。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-140">Use a name that helps identify the purpose and version of the application that will be added to the package.</span></span> <span data-ttu-id="f4ca1-141">套件的名稱會顯示在 App-v 5.0 管理主控台中。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-141">The package name is displayed in the App-V 5.0 Management Console.</span></span>

   <span data-ttu-id="f4ca1-142">**主要虛擬應用程式目錄**會顯示應用程式將在目的電腦上安裝的路徑。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-142">The **Primary Virtual Application Directory** displays the path where the application will be installed on target computers.</span></span> <span data-ttu-id="f4ca1-143">若要指定此位置，請選取 **[流覽]**。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-143">To specify this location, select **Browse**.</span></span>

   **<span data-ttu-id="f4ca1-144">注意</span><span class="sxs-lookup"><span data-stu-id="f4ca1-144">Note</span></span>**  
   <span data-ttu-id="f4ca1-145">從 App-v 5.0 SP3 開始，主要虛擬應用程式目錄（PVAD）是隱藏的，但您可以將它重新開啟。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-145">Starting in App-V 5.0 SP3, the primary virtual application directory (PVAD) is hidden, but you can turn it back on.</span></span> <span data-ttu-id="f4ca1-146">請參閱[關於 App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-pvad-hidden)。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-146">See [About App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-pvad-hidden).</span></span>



~~~
**Important**  
The primary application virtual directory should match the installation location for the application that is being sequenced. For example, if you install Notepad to **C:\\Program Files\\Notepad**; you should configure **C:\\Program Files\\Notepad** as your primary virtual directory. Alternatively, you can choose to set **C:\\Notepad** as the primary virtual application directory, as long as during installation time, you configure the installer to install to **C:\\Notepad**. Editing the Application Virtualization path is an advanced configuration task. For most applications, the default path is recommended for the following reasons:

-   Application Compatibility. Some virtualized applications will not function correctly, or will fail to open if the directories are not configured with identical virtual directory paths.

-   Performance. Since no file system redirection is required, the runtime performance can improve.



**Tip**  
It is recommended that prior to Sequencing an application, you open the associated installer to determine the default installation directory, and then configure that location as the **Primary Virtual Application Directory**.



Click **Next**.
~~~

7. <span data-ttu-id="f4ca1-147">在 [**安裝**] 頁面上，當排序器和應用程式安裝程式準備好時，您可以繼續安裝應用程式，讓排序器可以監視安裝程式。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-147">On the **Installation** page, when the sequencer and application installer are ready you can proceed to install the application so that the sequencer can monitor the installation process.</span></span>

   **<span data-ttu-id="f4ca1-148">重要</span><span class="sxs-lookup"><span data-stu-id="f4ca1-148">Important</span></span>**  
   <span data-ttu-id="f4ca1-149">您應該一直在安全的位置安裝應用程式，並確認在監視期間沒有其他使用者登入執行排序器的電腦。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-149">You should always install applications to a secure location and make sure no other users are logged on to the computer running the sequencer during monitoring.</span></span>



~~~
Use the application's installation process to perform the installation. If additional installation files must be run as part of the installation, click **Run** to locate and run the additional installation files. When you are finished with the installation, select **I am finished installing**. Click **Next**.
~~~

8. <span data-ttu-id="f4ca1-150">在 [**安裝**] 頁面上，請稍候，sequencer 會設定虛擬化的應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-150">On the **Installation** page, wait while the sequencer configures the virtualized application package.</span></span>

9. <span data-ttu-id="f4ca1-151">在 [**設定軟體**] 頁面上，選擇性地執行套件中包含的程式。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-151">On the **Configure Software** page, optionally run the programs contained in the package.</span></span> <span data-ttu-id="f4ca1-152">此步驟可讓您在部署和執行目的電腦上的套件之前，先完成任何必要的授權或配置工作。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-152">This step allows you to complete any necessary license or configuration tasks before you deploy and run the package on target computers.</span></span> <span data-ttu-id="f4ca1-153">若要一次執行所有程式，請選取至少一個程式，然後按一下 [**全部執行**]。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-153">To run all the programs at one time, select at least one program, and then click **Run All**.</span></span> <span data-ttu-id="f4ca1-154">若要執行特定程式，請選取該程式或程式，然後按一下 [**執行選取**的專案]。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-154">To run specific programs, select the program or programs, and then click **Run Selected**.</span></span> <span data-ttu-id="f4ca1-155">完成所需的配置工作，然後關閉應用程式。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-155">Complete the required configuration tasks and then close the applications.</span></span> <span data-ttu-id="f4ca1-156">您可能需要等候數分鐘的時間，所有程式才會執行。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-156">You may need to wait several minutes for all programs to run.</span></span>

   **<span data-ttu-id="f4ca1-157">注意</span><span class="sxs-lookup"><span data-stu-id="f4ca1-157">Note</span></span>**  
   <span data-ttu-id="f4ca1-158">若要針對清單中無法使用的任何應用程式執行第一次使用工作，請開啟應用程式。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-158">To run first-use tasks for any application that is not available in the list, open the application.</span></span> <span data-ttu-id="f4ca1-159">相關的資訊將會在此步驟中捕獲。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-159">The associated information will be captured during this step.</span></span>



~~~
Click **Next**.
~~~

10. <span data-ttu-id="f4ca1-160">在 [**安裝報告**] 頁面上，您可以查看您剛剛排序的虛擬化應用程式套件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-160">On the **Installation Report** page, you can review information about the virtualized application package you have just sequenced.</span></span> <span data-ttu-id="f4ca1-161">在 [**其他資訊**] 中，按兩下事件以取得更詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-161">In **Additional Information**, double-click an event to obtain more detailed information.</span></span> <span data-ttu-id="f4ca1-162">若要繼續，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-162">To proceed, click **Next**.</span></span>

11. <span data-ttu-id="f4ca1-163">隨即會顯示 [**自訂**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-163">The **Customize** page is displayed.</span></span> <span data-ttu-id="f4ca1-164">如果您已完成安裝並設定虛擬應用程式，請選取 [**立即停止**]，然後跳至此程式的步驟14。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-164">If you are finished installing and configuring the virtual application, select **Stop now** and skip to step 14 of this procedure.</span></span> <span data-ttu-id="f4ca1-165">若要執行下列其中一項自訂作業，請選取 [**自訂**]。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-165">To perform either of the following customizations, select **Customize**.</span></span>

    -   <span data-ttu-id="f4ca1-166">準備虛擬套件以進行流式處理。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-166">Prepare the virtual package for streaming.</span></span> <span data-ttu-id="f4ca1-167">[資料流程] 可改善虛擬應用程式套件在目的電腦上執行時的體驗。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-167">Streaming improves the experience when the virtual application package is run on target computers.</span></span>

    -   <span data-ttu-id="f4ca1-168">指定可以執行此套件的作業系統。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-168">Specify the operating systems that can run this package.</span></span>

    <span data-ttu-id="f4ca1-169">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-169">Click **Next**.</span></span>

12. <span data-ttu-id="f4ca1-170">在 [**流式處理**] 頁面上，執行每個程式，讓它能在目的電腦上優化並更有效率地執行。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-170">On the **Streaming** page, run each program so that it can be optimized and run more efficiently on target computers.</span></span> <span data-ttu-id="f4ca1-171">可能需要幾分鐘的時間，所有應用程式才會執行。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-171">It can take several minutes for all the applications to run.</span></span> <span data-ttu-id="f4ca1-172">在所有應用程式都已執行之後，請關閉每個應用程式，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-172">After all applications have run, close each of the applications, and then click **Next**.</span></span>

   **<span data-ttu-id="f4ca1-173">注意</span><span class="sxs-lookup"><span data-stu-id="f4ca1-173">Note</span></span>**  
   <span data-ttu-id="f4ca1-174">如果您在這個步驟中沒有開啟任何應用程式，預設的流式處理方法是點播傳送。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-174">If you do not open any applications during this step, the default streaming method is on-demand streaming delivery.</span></span> <span data-ttu-id="f4ca1-175">這表示應用程式將會按位下載，直到可以開啟，然後根據背景載入的設定方式，將會載入應用程式的其餘部分。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-175">This means applications will be downloaded bit by bit until it can be opened, and then depending on how the background loading is configured, will load the rest of the application.</span></span>



13. <span data-ttu-id="f4ca1-176">在 [**目標作業系統**] 頁面上，指定可執行此套件的作業系統。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-176">On the **Target OS** page, specify the operating systems that can run this package.</span></span> <span data-ttu-id="f4ca1-177">若要允許您環境中所有受支援的作業系統執行這個套件，請選取 [**允許此套件在任何作業系統上執行**]。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-177">To allow all supported operating systems in your environment to run this package, select **Allow this package to run on any operating system**.</span></span> <span data-ttu-id="f4ca1-178">若要將這個套件設定為只在特定作業系統上執行，請選取 [**只允許此套件在下列作業系統上**執行]，然後選取可以執行此套件的作業系統。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-178">To configure this package to run only on specific operating systems, select **Allow this package to run only on the following operating systems** and select the operating systems that can run this package.</span></span> <span data-ttu-id="f4ca1-179">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-179">Click **Next**.</span></span>

   **<span data-ttu-id="f4ca1-180">重要</span><span class="sxs-lookup"><span data-stu-id="f4ca1-180">Important</span></span>**  
   <span data-ttu-id="f4ca1-181">請確定您在此處指定的作業系統是由您所排序的應用程式所支援。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-181">Make sure that the operating systems you specify here are supported by the application you are sequencing.</span></span>



14. <span data-ttu-id="f4ca1-182">隨即會顯示 [**建立套件**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-182">The **Create Package** page is displayed.</span></span> <span data-ttu-id="f4ca1-183">若要在不儲存的情況下修改套件，請選取 [**繼續使用套件編輯器修改套件而不儲存**]。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-183">To modify the package without saving it, select **Continue to modify package without saving using the package editor**.</span></span> <span data-ttu-id="f4ca1-184">此選項會在 sequencer 視窗中開啟套件，讓您可以在儲存套件之前加以修改。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-184">This option opens the package in the sequencer console so that you can modify the package before it is saved.</span></span> <span data-ttu-id="f4ca1-185">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-185">Click **Next**.</span></span>

   <span data-ttu-id="f4ca1-186">若要立即儲存套件，請選取 [**立即儲存套件**] （預設）。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-186">To save the package immediately, select **Save the package now** (default).</span></span> <span data-ttu-id="f4ca1-187">新增要與套件相關聯的選擇性**批註**。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-187">Add optional **Comments** to be associated with the package.</span></span> <span data-ttu-id="f4ca1-188">若要識別程式版本及有關套件的其他資訊，可以使用批註。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-188">Comments are useful for identifying the program version and other information about the package.</span></span>

   **<span data-ttu-id="f4ca1-189">重要</span><span class="sxs-lookup"><span data-stu-id="f4ca1-189">Important</span></span>**  
   <span data-ttu-id="f4ca1-190">系統不支援**批註**和**描述**中不能列印的字元。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-190">The system does not support non-printable characters in **Comments** and **Descriptions**.</span></span>



~~~
The default **Save Location** is also displayed on this page. To change the default location, click **Browse** and specify the new location. Click **Create**.
~~~

15. <span data-ttu-id="f4ca1-191">[**完成**] 頁面隨即出現。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-191">The **Completion** page is displayed.</span></span> <span data-ttu-id="f4ca1-192">視需要查看**虛擬應用程式套件報告**窗格中的資訊，然後按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-192">Review the information in the **Virtual Application Package Report** pane as needed, then click **Close**.</span></span> <span data-ttu-id="f4ca1-193">您也可以在建立套件之目錄中的**Report.xml**檔案中找到此資訊。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-193">This information is also available in the **Report.xml** file that is located in the directory where the package was created.</span></span>

   <span data-ttu-id="f4ca1-194">套件現在可在 sequencer 中取得。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-194">The package is now available in the sequencer.</span></span>

   **<span data-ttu-id="f4ca1-195">重要</span><span class="sxs-lookup"><span data-stu-id="f4ca1-195">Important</span></span>**  
   <span data-ttu-id="f4ca1-196">成功建立虛擬應用程式套件之後，您就無法在執行排序器的電腦上執行虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-196">After you have successfully created a virtual application package, you cannot run the virtual application package on the computer that is running the sequencer.</span></span>



**<span data-ttu-id="f4ca1-197">為附加元件或外掛程式應用程式排序</span><span class="sxs-lookup"><span data-stu-id="f4ca1-197">To sequence an add-on or plug-in application</span></span>**

1.  

    **<span data-ttu-id="f4ca1-198">注意</span><span class="sxs-lookup"><span data-stu-id="f4ca1-198">Note</span></span>**  
    <span data-ttu-id="f4ca1-199">在執行下列程式之前，請先在執行排序器的電腦上本機安裝上層應用程式。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-199">Before performing the following procedure, install the parent application locally on the computer that is running the sequencer.</span></span> <span data-ttu-id="f4ca1-200">或者，如果您已將上層應用程式虛擬化，您可以按照附加元件或外掛程式工作流程中的步驟，將上層應用程式解包到電腦上。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-200">Or if you have the parent application virtualized, you can follow the steps in the add-on or plug-in workflow to unpack the parent application on the computer.</span></span>

    <span data-ttu-id="f4ca1-201">例如，如果您要為 Microsoft Excel 的外掛程式進行排序，請在執行排序器的電腦上本機安裝 Microsoft Excel。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-201">For example, if you are sequencing a plug-in for Microsoft Excel, install Microsoft Excel locally on the computer that is running the sequencer.</span></span> <span data-ttu-id="f4ca1-202">您也可以在安裝了應用程式的目的電腦上，將上層應用程式安裝在同一個目錄中。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-202">Also install the parent application in the same directory where the application is installed on target computers.</span></span> <span data-ttu-id="f4ca1-203">如果外掛程式或附加元件要與現有的虛擬應用程式套件搭配使用，請在建立父虛擬應用程式套件時，將應用程式安裝在所用的同一個虛擬應用程式磁碟機上。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-203">If the plug-in or add-on is going to be used with an existing virtual application package, install the application on the same virtual application drive that was used when you created the parent virtual application package.</span></span>



~~~
On the computer that runs the sequencer, click **All Programs**, and then Click **Microsoft Application Virtualization**, and then click **Microsoft Application Virtualization Sequencer**.
~~~

2. <span data-ttu-id="f4ca1-204">*<strong><em>在 sequencer 中，按一下 [* </em> 建立新的虛擬應用程式套件] </strong> 。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-204">\*<strong><em>In the sequencer, click \*</em>Create a New Virtual Application Package</strong>.</span></span> <span data-ttu-id="f4ca1-205">選取 [**建立套件（預設）**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-205">Select **Create Package (default)**, and then click **Next**.</span></span>

3. <span data-ttu-id="f4ca1-206">在 [**準備電腦**] 頁面上，查看可能導致套件建立失敗的問題，或可能導致套件包含不必要的資料。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-206">On the **Prepare Computer** page, review the issues that might cause the package creation to fail or could cause the package to contain unnecessary data.</span></span> <span data-ttu-id="f4ca1-207">繼續進行之前，您應該先解決所有潛在問題。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-207">You should resolve all potential issues before you continue.</span></span> <span data-ttu-id="f4ca1-208">進行任何修正之後 **，按一下 [** 重新整理] 以顯示更新的資訊。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-208">After making any corrections, click **Refresh** to display the updated information.</span></span> <span data-ttu-id="f4ca1-209">解決所有可能的問題之後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-209">After you have resolved all potential issues, click **Next**.</span></span>

   **<span data-ttu-id="f4ca1-210">重要</span><span class="sxs-lookup"><span data-stu-id="f4ca1-210">Important</span></span>**  
   <span data-ttu-id="f4ca1-211">如果您需要停用病毒掃描軟體，您應該先掃描執行 sequencer 的電腦，以確保無法將不想要的或惡意檔案新增到套件中。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-211">If you are required to disable virus scanning software, you should first scan the computer that runs the sequencer in order to ensure that no unwanted or malicious files could be added to the package.</span></span>



4. <span data-ttu-id="f4ca1-212">在 [**應用程式類型**] 頁面上，選取 [**附加元件] 或 [外掛程式]**，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-212">On the **Type of Application** page, select **Add-on or Plug-in**, and then click **Next**.</span></span>

5. <span data-ttu-id="f4ca1-213">在 [**選取安裝程式**] 頁面上，按一下 **[流覽]** ，然後指定附加元件或外掛程式的安裝檔。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-213">On the **Select Installer** page, click **Browse** and specify the installation file for the add-on or plug-in.</span></span> <span data-ttu-id="f4ca1-214">如果附加元件或外掛程式沒有關聯的安裝程式檔案，且您打算手動執行所有安裝步驟，請選取 [**選取此選項以執行自訂安裝**] 核取方塊，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-214">If the add-on or plug-in does not have an associated installer file and you plan to run all installation steps manually, select the **Select this option to perform a custom installation** check box, and then click **Next**.</span></span>

6. <span data-ttu-id="f4ca1-215">在 [**安裝] 主**版頁面上，確認已在執行排序器的電腦上安裝主要應用程式。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-215">On the **Install Primary** page, ensure that the primary application is installed on the computer that runs the sequencer.</span></span> <span data-ttu-id="f4ca1-216">或者，您可以在執行排序器的電腦上，展開已儲存在本機的現有套件。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-216">Alternatively, you can expand an existing package that has been saved locally on the computer that runs the sequencer.</span></span> <span data-ttu-id="f4ca1-217">若要這樣做，請按一下 [**展開套件**]，然後選取套件。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-217">To do this, click **Expand Package**, and then select the package.</span></span> <span data-ttu-id="f4ca1-218">展開或安裝上層程式後，請選取 **[我已安裝主要上層程式**]。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-218">After you have expanded or installed the parent program, select **I have installed the primary parent program**.</span></span>

   <span data-ttu-id="f4ca1-219">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-219">Click **Next**.</span></span>

7. <span data-ttu-id="f4ca1-220">在 [**套件名稱**] 頁面上，輸入將與套件建立關聯的名稱。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-220">On the **Package Name** page, type a name that will be associated with the package.</span></span> <span data-ttu-id="f4ca1-221">使用名稱，協助識別將新增到套件中之應用程式的用途和版本。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-221">Use a name that helps identify the purpose and version of the application that will be added to the package.</span></span> <span data-ttu-id="f4ca1-222">套件名稱將會顯示在 App-v 5.0 管理主控台中。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-222">The package name will be displayed in the App-V 5.0 Management Console.</span></span> <span data-ttu-id="f4ca1-223">**主要虛擬應用程式目錄**會顯示應用程式的安裝路徑。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-223">The **Primary Virtual Application Directory** displays the path where the application will be installed.</span></span> <span data-ttu-id="f4ca1-224">若要指定此位置，請輸入路徑，或按一下 **[流覽]**。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-224">To specify this location, type the path, or click **Browse**.</span></span>

   **<span data-ttu-id="f4ca1-225">注意</span><span class="sxs-lookup"><span data-stu-id="f4ca1-225">Note</span></span>**  
   <span data-ttu-id="f4ca1-226">從 App-v 5.0 SP3 開始，主要虛擬應用程式目錄（PVAD）是隱藏的，但您可以將它重新開啟。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-226">Starting in App-V 5.0 SP3, the primary virtual application directory (PVAD) is hidden, but you can turn it back on.</span></span> <span data-ttu-id="f4ca1-227">請參閱[關於 App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-pvad-hidden)。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-227">See [About App-V 5.0 SP3](about-app-v-50-sp3.md#bkmk-pvad-hidden).</span></span>



~~~
Click **Next**.
~~~

8. <span data-ttu-id="f4ca1-228">在 [**安裝**] 頁面上，當排序器和應用程式安裝程式準備好時，您可以繼續安裝外掛程式或增益集應用程式，讓排序器可以監視安裝程式。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-228">On the **Installation** page, when the sequencer and application installer are ready you can proceed to install the plug-in or add-in application so the sequencer can monitor the installation process.</span></span> <span data-ttu-id="f4ca1-229">使用應用程式的安裝程式來執行安裝。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-229">Use the application's installation process to perform the installation.</span></span> <span data-ttu-id="f4ca1-230">如果安裝時必須執行其他安裝檔案，請按一下 [**執行**]，然後找出並執行其他安裝檔案。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-230">If additional installation files must be run as part of the installation, click **Run** and locate and run the additional installation files.</span></span> <span data-ttu-id="f4ca1-231">完成安裝後，請選取 [**我已完成安裝**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-231">When you are finished with the installation, select **I am finished installing**, and then click **Next**.</span></span>

9. <span data-ttu-id="f4ca1-232">在 [**安裝報告**] 頁面上，您可以查看剛剛排序的虛擬應用程式套件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-232">On the **Installation Report** page, you can review information about the virtual application package that you just sequenced.</span></span> <span data-ttu-id="f4ca1-233">如需**其他資訊**所顯示之資訊的詳細說明，請按兩下該事件。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-233">For a more detailed explanation about the information displayed in **Additional Information**, double-click the event.</span></span> <span data-ttu-id="f4ca1-234">審閱資訊之後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-234">After you have reviewed the information, click **Next**.</span></span>

10. <span data-ttu-id="f4ca1-235">隨即會顯示 [**自訂**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-235">The **Customize** page is displayed.</span></span> <span data-ttu-id="f4ca1-236">如果您已完成安裝並設定虛擬應用程式，請選取 [**立即停止**]，然後跳至此程式的步驟12。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-236">If you are finished installing and configuring the virtual application, select **Stop now** and skip to step 12 of this procedure.</span></span> <span data-ttu-id="f4ca1-237">若要執行下列其中一項自訂作業，請選取 [**自訂**]。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-237">To perform either of the following customizations, select **Customize**.</span></span>

    -   <span data-ttu-id="f4ca1-238">優化套件在慢速或不可靠的網路上的執行方式。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-238">Optimize how the package will run across a slow or unreliable network.</span></span>

    -   <span data-ttu-id="f4ca1-239">指定可以執行此套件的作業系統。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-239">Specify the operating systems that can run this package.</span></span>

    <span data-ttu-id="f4ca1-240">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-240">Click **Next**.</span></span>

11. <span data-ttu-id="f4ca1-241">在 [**流式處理**] 頁面上，執行每個程式，讓它能在目的電腦上優化並更有效率地執行。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-241">On the **Streaming** page, run each program so that it can be optimized and run more efficiently on target computers.</span></span> <span data-ttu-id="f4ca1-242">[資料流程] 可改善在高延遲網路上的目的電腦上執行虛擬應用程式套件時的體驗。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-242">Streaming improves the experience when the virtual application package is run on target computers on high-latency networks.</span></span> <span data-ttu-id="f4ca1-243">可能需要幾分鐘的時間，所有應用程式才會執行。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-243">It can take several minutes for all the applications to run.</span></span> <span data-ttu-id="f4ca1-244">在所有應用程式都已執行之後，請關閉每個應用程式。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-244">After all applications have run, close each of the applications.</span></span> <span data-ttu-id="f4ca1-245">您也可以選取 [**強制下載應用程式**] 核取方塊，將套件設定為必須在開啟之前完全下載。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-245">You can also configure the package to be required to be fully downloaded before opening by selecting the **Force applications to be downloaded** check-box.</span></span> <span data-ttu-id="f4ca1-246">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-246">Click **Next**.</span></span>

   **<span data-ttu-id="f4ca1-247">注意</span><span class="sxs-lookup"><span data-stu-id="f4ca1-247">Note</span></span>**  
   <span data-ttu-id="f4ca1-248">如有需要，您可以在此步驟中停止應用程式的載入。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-248">If necessary, you can stop an application from loading during this step.</span></span> <span data-ttu-id="f4ca1-249">在 [**應用程式啟動**] 對話方塊中，按一下 [**停止**]，然後選取其中一個核取方塊： [**停止所有應用程式**] 或 [**僅停止此應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-249">In the **Application Launch** dialog box, click **Stop** and select one of the check boxes: **Stop all applications** or **Stop this application only**.</span></span>



12. <span data-ttu-id="f4ca1-250">在 [**目標作業系統**] 頁面上，指定可執行此套件的作業系統。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-250">On the **Target OS** page, specify the operating systems that can run this package.</span></span> <span data-ttu-id="f4ca1-251">若要允許您環境中所有支援的作業系統執行這個套件，請選取 [**允許此套件在任何作業系統上執行**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-251">To allow all supported operating systems in your environment to run this package, select the **Allow this package to run on any operating system** check box.</span></span> <span data-ttu-id="f4ca1-252">若要將這個套件設定為只在特定作業系統上執行，請選取 [**只允許此套件在下列作業系統上執行**] 核取方塊，然後選取可以執行此套件的作業系統。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-252">To configure this package to run only on specific operating systems, select the **Allow this package to run only on the following operating systems** check box, and then select the operating systems that can run this package.</span></span> <span data-ttu-id="f4ca1-253">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-253">Click **Next**.</span></span>

13. <span data-ttu-id="f4ca1-254">隨即會顯示 [**建立套件**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-254">The **Create Package** page is displayed.</span></span> <span data-ttu-id="f4ca1-255">若要在不儲存的情況下修改套件，請選取 **[繼續使用套件編輯器修改套件但不儲存**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-255">To modify the package without saving it, select **Continue to modify package without saving using the package editor** check box.</span></span> <span data-ttu-id="f4ca1-256">此選項會在 sequencer 視窗中開啟套件，讓您可以在儲存套件之前加以修改。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-256">This option opens the package in the sequencer console so that you can modify the package before it is saved.</span></span> <span data-ttu-id="f4ca1-257">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-257">Click **Next**.</span></span>

   <span data-ttu-id="f4ca1-258">若要立即儲存套件，請選取 **[立即儲存套件**]。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-258">To save the package immediately, select **Save the package now**.</span></span> <span data-ttu-id="f4ca1-259">您也可以選擇新增與套件相關聯的**描述**。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-259">Optionally, add a **Description** that will be associated with the package.</span></span> <span data-ttu-id="f4ca1-260">描述對於識別套件的版本和其他資訊很有用。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-260">Descriptions are useful for identifying the version and other information about the package.</span></span>

   **<span data-ttu-id="f4ca1-261">重要</span><span class="sxs-lookup"><span data-stu-id="f4ca1-261">Important</span></span>**  
   <span data-ttu-id="f4ca1-262">系統不支援批註和描述中不能列印的字元。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-262">The system does not support non-printable characters in Comments and Descriptions.</span></span>



~~~
The default **Save Location** is also displayed on this page. To change the default location, click **Browse** and specify the new location. Click **Create**.
~~~

**<span data-ttu-id="f4ca1-263">為中介軟體應用程式排序</span><span class="sxs-lookup"><span data-stu-id="f4ca1-263">To sequence a middleware application</span></span>**

1. <span data-ttu-id="f4ca1-264">在執行排序器的電腦上，按一下 [**所有程式**]，然後按一下 [ **microsoft application**virtualization]，然後按一下 [ **microsoft application virtualization 排序**器]。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-264">On the computer that runs the sequencer, click **All Programs**, and then Click **Microsoft Application Virtualization**, and then click **Microsoft Application Virtualization Sequencer**.</span></span>

2. <span data-ttu-id="f4ca1-265">*<strong><em>在 sequencer 中，按一下 [* </em> 建立新的虛擬應用程式套件] </strong> 。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-265">\*<strong><em>In the sequencer, click \*</em>Create a New Virtual Application Package</strong>.</span></span> <span data-ttu-id="f4ca1-266">選取 [**建立套件（預設）**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-266">Select **Create Package (default)**, and then click **Next**.</span></span>

3. <span data-ttu-id="f4ca1-267">在 [**準備電腦**] 頁面上，查看可能導致套件建立失敗的問題，或可能導致套件包含不必要的資料。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-267">On the **Prepare Computer** page, review the issues that could cause the package creation to fail or could cause the package to contain unnecessary data.</span></span> <span data-ttu-id="f4ca1-268">繼續進行之前，您應該先解決所有潛在問題。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-268">You should resolve all potential issues before you continue.</span></span> <span data-ttu-id="f4ca1-269">進行任何修正之後 **，按一下 [** 重新整理] 以顯示更新的資訊。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-269">After making any corrections, click **Refresh** to display the updated information.</span></span> <span data-ttu-id="f4ca1-270">解決所有可能的問題之後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-270">After you have resolved all potential issues, click **Next**.</span></span>

   **<span data-ttu-id="f4ca1-271">重要</span><span class="sxs-lookup"><span data-stu-id="f4ca1-271">Important</span></span>**  
   <span data-ttu-id="f4ca1-272">如果您需要停用病毒掃描軟體，您應該先掃描執行 App-v 5.0 Sequencer 的電腦，以確保無法將不想要的或惡意檔案新增到套件中。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-272">If you are required to disable virus scanning software, you should first scan the computer that runs the App-V 5.0 Sequencer in order to ensure that no unwanted or malicious files can be added to the package.</span></span>



4. <span data-ttu-id="f4ca1-273">在 [**應用程式類型**] 頁面上，選取 [**中介軟體**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-273">On the **Type of Application** page, select **Middleware**, and then click **Next**.</span></span>

5. <span data-ttu-id="f4ca1-274">在 [**選取安裝程式**] 頁面上，按一下 **[流覽]** ，然後指定應用程式的安裝檔。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-274">On the **Select Installer** page, click **Browse** and specify the installation file for the application.</span></span> <span data-ttu-id="f4ca1-275">如果應用程式沒有關聯的安裝程式檔案，且您打算手動執行所有安裝步驟，請選取 [**選取此選項以執行自訂安裝**] 核取方塊，然後按一下 [**下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-275">If the application does not have an associated installer file and you plan to run all installation steps manually, select the **Select this option to perform a custom installation** check box, and then click **Next**.</span></span>

6. <span data-ttu-id="f4ca1-276">在 [**套件名稱**] 頁面上，輸入將與套件建立關聯的名稱。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-276">On the **Package Name** page, type a name that will be associated with the package.</span></span> <span data-ttu-id="f4ca1-277">使用名稱，協助識別將新增到套件中之應用程式的用途和版本。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-277">Use a name that helps identify the purpose and version of the application that will be added to the package.</span></span> <span data-ttu-id="f4ca1-278">套件的名稱會顯示在 App-v 5.0 管理主控台中。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-278">The package name is displayed in the App-V 5.0 Management Console.</span></span> <span data-ttu-id="f4ca1-279">**主要虛擬應用程式目錄**會顯示應用程式的安裝路徑。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-279">The **Primary Virtual Application Directory** displays the path where the application will be installed.</span></span> <span data-ttu-id="f4ca1-280">若要指定此位置，請輸入路徑，或按一下 **[流覽]**。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-280">To specify this location, type the path or click **Browse**.</span></span>

   <span data-ttu-id="f4ca1-281">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-281">Click **Next**.</span></span>

7. <span data-ttu-id="f4ca1-282">在 [**安裝**] 頁面上，當 sequencer 與中介軟體應用程式安裝程式準備就緒時，您可以繼續安裝應用程式，讓排序器可以監視安裝程式。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-282">On the **Installation** page, when the sequencer and middleware application installer are ready you can proceed to install the application so that the sequencer can monitor the installation process.</span></span> <span data-ttu-id="f4ca1-283">使用應用程式的安裝程式來執行安裝。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-283">Use the application's installation process to perform the installation.</span></span> <span data-ttu-id="f4ca1-284">如果安裝時必須執行其他安裝檔，請按一下 [**執行**]，找出並執行其他安裝檔案。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-284">If additional installation files must be run as part of the installation, click **Run**, to locate and run the additional installation files.</span></span> <span data-ttu-id="f4ca1-285">完成安裝後，請選取 [**我已完成安裝**] 核取方塊，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-285">When you are finished with the installation, select the **I am finished installing** check box, and then click **Next**.</span></span>

8. <span data-ttu-id="f4ca1-286">在 [**安裝**] 頁面上，請稍候，sequencer 會設定虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-286">On the **Installation** page, wait while the sequencer configures the virtual application package.</span></span>

9. <span data-ttu-id="f4ca1-287">在 [**安裝報告**] 頁面上，您可以查看您剛剛排序的虛擬應用程式套件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-287">On the **Installation Report** page, you can review information about the virtual application package that you have just sequenced.</span></span> <span data-ttu-id="f4ca1-288">在 [**其他資訊**] 中，按兩下事件以取得更詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-288">In **Additional Information**, double-click an event to obtain more detailed information.</span></span> <span data-ttu-id="f4ca1-289">若要繼續，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-289">To proceed, click **Next**.</span></span>

10. <span data-ttu-id="f4ca1-290">在 [**目標作業系統**] 頁面上，指定可執行此套件的作業系統。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-290">On the **Target OS** page, specify the operating systems that can run this package.</span></span> <span data-ttu-id="f4ca1-291">若要在您的環境中啟用所有受支援的作業系統來執行這個套件，請選取 [**允許此套件在任何作業系統上執行**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-291">To enable all supported operating systems in your environment to run this package, select the **Allow this package to run on any operating system** check box.</span></span> <span data-ttu-id="f4ca1-292">若要將這個套件設定為只在特定作業系統上執行，請選取 [**只允許此套件在下列作業系統上執行**] 核取方塊，然後選取可以執行此套件的作業系統。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-292">To configure this package to run only on specific operating systems, select the **Allow this package to run only on the following operating systems** check box and select the operating systems that can run this package.</span></span> <span data-ttu-id="f4ca1-293">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-293">Click **Next**.</span></span>

11. <span data-ttu-id="f4ca1-294">在 [**建立套件**] 頁面上隨即出現。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-294">On the **Create Package** page is displayed.</span></span> <span data-ttu-id="f4ca1-295">若要在不儲存的情況下修改套件，請選取 [**繼續使用套件編輯器修改套件而不儲存**]。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-295">To modify the package without saving it, select **Continue to modify package without saving using the package editor**.</span></span> <span data-ttu-id="f4ca1-296">此選項會在 sequencer 視窗中開啟套件，讓您可以在儲存套件之前加以修改。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-296">This option opens the package in the sequencer console so that you can modify the package before it is saved.</span></span> <span data-ttu-id="f4ca1-297">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-297">Click **Next**.</span></span>

    <span data-ttu-id="f4ca1-298">若要立即儲存套件，請選取 **[立即儲存套件**]。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-298">To save the package immediately, select **Save the package now**.</span></span> <span data-ttu-id="f4ca1-299">或者，您也可以新增要與套件相關聯的**描述**。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-299">Optionally, add a **Description** to be associated with the package.</span></span> <span data-ttu-id="f4ca1-300">描述對於識別套件的程式版本和其他資訊很有用。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-300">Descriptions are useful for identifying the program version and other information about the package.</span></span>

    **<span data-ttu-id="f4ca1-301">重要</span><span class="sxs-lookup"><span data-stu-id="f4ca1-301">Important</span></span>**  
    <span data-ttu-id="f4ca1-302">系統不支援批註和描述中不能列印的字元。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-302">The system does not support non-printable characters in Comments and Descriptions.</span></span>



~~~
The default **Save Location** is also displayed on this page. To change the default location, click **Browse** and specify the new location. Click **Create**.
~~~

12. <span data-ttu-id="f4ca1-303">[**完成**] 頁面隨即出現。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-303">The **Completion** page is displayed.</span></span> <span data-ttu-id="f4ca1-304">視需要查看**虛擬應用程式套件報告**窗格中的資訊，然後按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-304">Review the information in the **Virtual Application Package Report** pane as needed, then click **Close**.</span></span> <span data-ttu-id="f4ca1-305">您也可以在此程式步驟11所指定之目錄中的**Report.xml**檔案中找到此資訊。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-305">This information is also available in the **Report.xml** file that is located in the directory specified in step 11 of this procedure.</span></span>

   <span data-ttu-id="f4ca1-306">套件現在可在 sequencer 中取得。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-306">The package is now available in the sequencer.</span></span> <span data-ttu-id="f4ca1-307">若要編輯套件屬性，請按一下 **[編輯 \ [套件名稱 \]]**。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-307">To edit the package properties, click **Edit \[Package Name\]**.</span></span>

   **<span data-ttu-id="f4ca1-308">重要</span><span class="sxs-lookup"><span data-stu-id="f4ca1-308">Important</span></span>**  
   <span data-ttu-id="f4ca1-309">成功建立虛擬應用程式套件之後，您就無法在執行排序器的電腦上執行虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="f4ca1-309">After you have successfully created a virtual application package, you cannot run the virtual application package on the computer that is running the sequencer.</span></span>



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## <span data-ttu-id="f4ca1-310">相關主題</span><span class="sxs-lookup"><span data-stu-id="f4ca1-310">Related topics</span></span>


[<span data-ttu-id="f4ca1-311">App-V 5.0 作業</span><span class="sxs-lookup"><span data-stu-id="f4ca1-311">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)









