---
title: 如何使用 App-V 5.1 為新應用程式進行序列化
description: 如何使用 App-V 5.1 為新應用程式進行序列化
author: dansimp
ms.assetid: 7d7699b1-0cb8-450d-94e7-5af937e16c21
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 43edd9357e31f4884ed7baec3d35fa01bf2abe54
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800413"
---
# <span data-ttu-id="4deb2-103">如何使用 App-V 5.1 為新應用程式進行序列化</span><span class="sxs-lookup"><span data-stu-id="4deb2-103">How to Sequence a New Application with App-V 5.1</span></span>


**<span data-ttu-id="4deb2-104">若要在開始排序前查看或執行</span><span class="sxs-lookup"><span data-stu-id="4deb2-104">To review or do before you start sequencing</span></span>**

1.  <span data-ttu-id="4deb2-105">判斷您想要建立的虛擬化應用程式套件類型：</span><span class="sxs-lookup"><span data-stu-id="4deb2-105">Determine the type of virtualized application package you want to create:</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="4deb2-106">應用程式類型</span><span class="sxs-lookup"><span data-stu-id="4deb2-106">Application type</span></span></th>
    <th align="left"><span data-ttu-id="4deb2-107">描述</span><span class="sxs-lookup"><span data-stu-id="4deb2-107">Description</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="4deb2-108">Standard</span><span class="sxs-lookup"><span data-stu-id="4deb2-108">Standard</span></span></p></td>
    <td align="left"><p><span data-ttu-id="4deb2-109">建立包含應用程式或應用程式套件的套件。</span><span class="sxs-lookup"><span data-stu-id="4deb2-109">Creates a package that contains an application or a suite of applications.</span></span> <span data-ttu-id="4deb2-110">這是大部分應用程式類型的首選選項。</span><span class="sxs-lookup"><span data-stu-id="4deb2-110">This is the preferred option for most application types.</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="4deb2-111">附加元件或外掛程式</span><span class="sxs-lookup"><span data-stu-id="4deb2-111">Add-on or plug-in</span></span></p></td>
    <td align="left"><p><span data-ttu-id="4deb2-112">建立可延伸標準應用程式功能的套件，例如 Microsoft Excel 的外掛程式。</span><span class="sxs-lookup"><span data-stu-id="4deb2-112">Creates a package that extends the functionality of a standard application, for example, a plug-in for Microsoft Excel.</span></span> <span data-ttu-id="4deb2-113">此外，您也可以將外掛程式用於本機已安裝的應用程式，或針對使用連線群組連結的其他套件使用外掛程式。</span><span class="sxs-lookup"><span data-stu-id="4deb2-113">Additionally, you can use plug-ins for natively installed applications, or for another package that is linked by using connection groups.</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="4deb2-114">中介軟體</span><span class="sxs-lookup"><span data-stu-id="4deb2-114">Middleware</span></span></p></td>
    <td align="left"><p><span data-ttu-id="4deb2-115">建立標準應用程式所需的套件（例如，JAVA）。</span><span class="sxs-lookup"><span data-stu-id="4deb2-115">Creates a package that is required by a standard application, for example, Java.</span></span> <span data-ttu-id="4deb2-116">中介軟體套件是使用連線群組來連結到其他套件。</span><span class="sxs-lookup"><span data-stu-id="4deb2-116">Middleware packages are used for linking to other packages by using connection groups.</span></span></p></td>
    </tr>
    </tbody>
    </table>



2.  <span data-ttu-id="4deb2-117">將所有所需的安裝檔案複製到執行排序器的電腦上。</span><span class="sxs-lookup"><span data-stu-id="4deb2-117">Copy all required installation files to the computer that is running the sequencer.</span></span>

3.  <span data-ttu-id="4deb2-118">將應用程式排序前，請先製作虛擬環境的備份影像，然後在您完成應用程式的排序之後，每次都要還原到該影像。</span><span class="sxs-lookup"><span data-stu-id="4deb2-118">Make a backup image of your virtual environment before sequencing an application, and then revert to that image each time after you finish sequencing an application.</span></span>

4.  <span data-ttu-id="4deb2-119">檢查下列專案：</span><span class="sxs-lookup"><span data-stu-id="4deb2-119">Review the following items:</span></span>

    -   <span data-ttu-id="4deb2-120">如果應用程式安裝程式將安全性存取變更為新的或現有的檔案或目錄，就不會在套件中捕獲這些變更。</span><span class="sxs-lookup"><span data-stu-id="4deb2-120">If an application installer changes the security access to a new or existing file or directory, those changes are not captured in the package.</span></span>

    -   <span data-ttu-id="4deb2-121">如果已針對虛擬化套件的目標卷停用短路徑，您也必須將套件排序為已建立且仍有停用短路徑的磁片。</span><span class="sxs-lookup"><span data-stu-id="4deb2-121">If short paths have been disabled for the virtualized package’s target volume, you must also sequence the package to a volume that was created and still has short-paths disabled.</span></span> <span data-ttu-id="4deb2-122">它不可以是系統音量。</span><span class="sxs-lookup"><span data-stu-id="4deb2-122">It cannot be the system volume.</span></span>

> [!NOTE]  
> <span data-ttu-id="4deb2-123">App-V-x Sequencer 無法使用與 "CO_ x" 相符的檔案名來排序應用程式， &lt; &gt; 其中 x 是任何數位。</span><span class="sxs-lookup"><span data-stu-id="4deb2-123">The App-V 5.x Sequencer cannot sequence applications with filenames matching "CO_&lt;x&gt;" where x is any numeral.</span></span> <span data-ttu-id="4deb2-124">將會產生錯誤0x8007139F。</span><span class="sxs-lookup"><span data-stu-id="4deb2-124">Error 0x8007139F will be generated.</span></span>

**<span data-ttu-id="4deb2-125">為新的標準應用程式排序</span><span class="sxs-lookup"><span data-stu-id="4deb2-125">To sequence a new standard application</span></span>**

1.  <span data-ttu-id="4deb2-126">在執行排序器的電腦上，按一下 [**所有程式**]，然後按一下 [ **microsoft application**virtualization]，然後按一下 [ **microsoft application virtualization 排序**器]。</span><span class="sxs-lookup"><span data-stu-id="4deb2-126">On the computer that runs the sequencer, click **All Programs**, and then Click **Microsoft Application Virtualization**, and then click **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="4deb2-127">在排序器中，按一下 [**建立新的虛擬應用程式套件**]。</span><span class="sxs-lookup"><span data-stu-id="4deb2-127">In the sequencer, click **Create a New Virtual Application Package**.</span></span> <span data-ttu-id="4deb2-128">選取 [**建立套件（預設）**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4deb2-128">Select **Create Package (default)**, and then click **Next**.</span></span>

3.  <span data-ttu-id="4deb2-129">在 [**準備電腦**] 頁面上，查看可能導致套件建立失敗的問題，或可能導致套件包含不必要的資料。</span><span class="sxs-lookup"><span data-stu-id="4deb2-129">On the **Prepare Computer** page, review the issues that could cause the package creation to fail or could cause the package to contain unnecessary data.</span></span> <span data-ttu-id="4deb2-130">繼續進行之前，您應該先解決所有潛在問題。</span><span class="sxs-lookup"><span data-stu-id="4deb2-130">You should resolve all potential issues before you continue.</span></span> <span data-ttu-id="4deb2-131">進行任何修正之後 **，按一下 [** 重新整理] 以顯示更新的資訊。</span><span class="sxs-lookup"><span data-stu-id="4deb2-131">After making any corrections, click **Refresh** to display the updated information.</span></span> <span data-ttu-id="4deb2-132">解決所有可能的問題之後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4deb2-132">After you have resolved all potential issues, click **Next**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="4deb2-133">如果您需要停用病毒掃描軟體，您應該先掃描執行 sequencer 的電腦，以確保無法將不想要的或惡意檔案新增到套件中。</span><span class="sxs-lookup"><span data-stu-id="4deb2-133">If you are required to disable virus scanning software, you should first scan the computer that runs the sequencer in order to ensure that no unwanted or malicious files could be added to the package.</span></span>



~~~
> [!NOTE]  
> There is currently no way to disable Windows Defender in Windows 10. If you receive a warning, you can safely ignore it. It is unlikely that Windows Defender will affect sequencing at all.
~~~



4. <span data-ttu-id="4deb2-134">在 [**應用程式類型**] 頁面上，按一下 [**標準應用程式（預設）** ] 核取方塊，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4deb2-134">On the **Type of Application** page, click the **Standard Application (default)** check box, and then click **Next**.</span></span>

5. <span data-ttu-id="4deb2-135">在 [**選取安裝程式**] 頁面上，按一下 **[流覽]** ，然後指定應用程式的安裝檔。</span><span class="sxs-lookup"><span data-stu-id="4deb2-135">On the **Select Installer** page, click **Browse** and specify the installation file for the application.</span></span>

   > [!NOTE]  
   > <span data-ttu-id="4deb2-136">如果指定的應用程式安裝程式修改檔案或目錄的安全性存取（現有或新），將不會將相關的變更捕獲到套件中。</span><span class="sxs-lookup"><span data-stu-id="4deb2-136">If the specified application installer modifies security access to a file or directory, existing or new, the associated changes will not be captured into the package.</span></span>



~~~
If the application does not have an associated installer file and you plan to run all installation steps manually, select the **Perform a Custom Installation** check box, and then Click **Next**.
~~~

6. <span data-ttu-id="4deb2-137">在 [**套件名稱**] 頁面上，輸入將與套件建立關聯的名稱。</span><span class="sxs-lookup"><span data-stu-id="4deb2-137">On the **Package Name** page, type a name that will be associated with the package.</span></span> <span data-ttu-id="4deb2-138">使用名稱，協助識別將新增到套件中之應用程式的用途和版本。</span><span class="sxs-lookup"><span data-stu-id="4deb2-138">Use a name that helps identify the purpose and version of the application that will be added to the package.</span></span> <span data-ttu-id="4deb2-139">套件的名稱會顯示在 App-v 5.0 管理主控台中。</span><span class="sxs-lookup"><span data-stu-id="4deb2-139">The package name is displayed in the App-V 5.0 Management Console.</span></span>

   <span data-ttu-id="4deb2-140">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="4deb2-140">Click **Next**.</span></span>

7. <span data-ttu-id="4deb2-141">在 [**安裝**] 頁面上，當排序器和應用程式安裝程式準備好時，您可以繼續安裝應用程式，讓排序器可以監視安裝程式。</span><span class="sxs-lookup"><span data-stu-id="4deb2-141">On the **Installation** page, when the sequencer and application installer are ready you can proceed to install the application so that the sequencer can monitor the installation process.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="4deb2-142">您應該一直在安全的位置安裝應用程式，並確認在監視期間沒有其他使用者登入執行排序器的電腦。</span><span class="sxs-lookup"><span data-stu-id="4deb2-142">You should always install applications to a secure location and make sure no other users are logged on to the computer running the sequencer during monitoring.</span></span>



~~~
Use the application's installation process to perform the installation. If additional installation files must be run as part of the installation, click **Run** to locate and run the additional installation files. When you are finished with the installation, select **I am finished installing**. Click **Next**.
~~~

8. <span data-ttu-id="4deb2-143">在 [**安裝**] 頁面上，請稍候，sequencer 會設定虛擬化的應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="4deb2-143">On the **Installation** page, wait while the sequencer configures the virtualized application package.</span></span>

9. <span data-ttu-id="4deb2-144">在 [**設定軟體**] 頁面上，選擇性地執行套件中包含的程式。</span><span class="sxs-lookup"><span data-stu-id="4deb2-144">On the **Configure Software** page, optionally run the programs contained in the package.</span></span> <span data-ttu-id="4deb2-145">此步驟可讓您在部署和執行目的電腦上的套件之前，先完成任何必要的授權或配置工作。</span><span class="sxs-lookup"><span data-stu-id="4deb2-145">This step allows you to complete any necessary license or configuration tasks before you deploy and run the package on target computers.</span></span> <span data-ttu-id="4deb2-146">若要一次執行所有程式，請選取至少一個程式，然後按一下 [**全部執行**]。</span><span class="sxs-lookup"><span data-stu-id="4deb2-146">To run all the programs at one time, select at least one program, and then click **Run All**.</span></span> <span data-ttu-id="4deb2-147">若要執行特定程式，請選取該程式或程式，然後按一下 [**執行選取**的專案]。</span><span class="sxs-lookup"><span data-stu-id="4deb2-147">To run specific programs, select the program or programs, and then click **Run Selected**.</span></span> <span data-ttu-id="4deb2-148">完成所需的配置工作，然後關閉應用程式。</span><span class="sxs-lookup"><span data-stu-id="4deb2-148">Complete the required configuration tasks and then close the applications.</span></span> <span data-ttu-id="4deb2-149">您可能需要等候數分鐘的時間，所有程式才會執行。</span><span class="sxs-lookup"><span data-stu-id="4deb2-149">You may need to wait several minutes for all programs to run.</span></span>

   > [!NOTE]  
   > <span data-ttu-id="4deb2-150">若要針對清單中無法使用的任何應用程式執行第一次使用工作，請開啟應用程式。</span><span class="sxs-lookup"><span data-stu-id="4deb2-150">To run first-use tasks for any application that is not available in the list, open the application.</span></span> <span data-ttu-id="4deb2-151">相關的資訊將會在此步驟中捕獲。</span><span class="sxs-lookup"><span data-stu-id="4deb2-151">The associated information will be captured during this step.</span></span>



~~~
Click **Next**.
~~~

10. <span data-ttu-id="4deb2-152">在 [**安裝報告**] 頁面上，您可以查看您剛剛排序的虛擬化應用程式套件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="4deb2-152">On the **Installation Report** page, you can review information about the virtualized application package you have just sequenced.</span></span> <span data-ttu-id="4deb2-153">在 [**其他資訊**] 中，按兩下事件以取得更詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="4deb2-153">In **Additional Information**, double-click an event to obtain more detailed information.</span></span> <span data-ttu-id="4deb2-154">若要繼續，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4deb2-154">To proceed, click **Next**.</span></span>

11. <span data-ttu-id="4deb2-155">隨即會顯示 [**自訂**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="4deb2-155">The **Customize** page is displayed.</span></span> <span data-ttu-id="4deb2-156">如果您已完成安裝並設定虛擬應用程式，請選取 [**立即停止**]，然後跳至此程式的步驟14。</span><span class="sxs-lookup"><span data-stu-id="4deb2-156">If you are finished installing and configuring the virtual application, select **Stop now** and skip to step 14 of this procedure.</span></span> <span data-ttu-id="4deb2-157">若要執行下列其中一項自訂作業，請選取 [**自訂**]。</span><span class="sxs-lookup"><span data-stu-id="4deb2-157">To perform either of the following customizations, select **Customize**.</span></span>

    -   <span data-ttu-id="4deb2-158">準備虛擬套件以進行流式處理。</span><span class="sxs-lookup"><span data-stu-id="4deb2-158">Prepare the virtual package for streaming.</span></span> <span data-ttu-id="4deb2-159">[資料流程] 可改善虛擬應用程式套件在目的電腦上執行時的體驗。</span><span class="sxs-lookup"><span data-stu-id="4deb2-159">Streaming improves the experience when the virtual application package is run on target computers.</span></span>

    -   <span data-ttu-id="4deb2-160">指定可以執行此套件的作業系統。</span><span class="sxs-lookup"><span data-stu-id="4deb2-160">Specify the operating systems that can run this package.</span></span>

    <span data-ttu-id="4deb2-161">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="4deb2-161">Click **Next**.</span></span>

12. <span data-ttu-id="4deb2-162">在 [**流式處理**] 頁面上，執行每個程式，讓它能在目的電腦上優化並更有效率地執行。</span><span class="sxs-lookup"><span data-stu-id="4deb2-162">On the **Streaming** page, run each program so that it can be optimized and run more efficiently on target computers.</span></span> <span data-ttu-id="4deb2-163">可能需要幾分鐘的時間，所有應用程式才會執行。</span><span class="sxs-lookup"><span data-stu-id="4deb2-163">It can take several minutes for all the applications to run.</span></span> <span data-ttu-id="4deb2-164">在所有應用程式都已執行之後，請關閉每個應用程式，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4deb2-164">After all applications have run, close each of the applications, and then click **Next**.</span></span>

   > [!NOTE]  
   > <span data-ttu-id="4deb2-165">如果您在這個步驟中沒有開啟任何應用程式，預設的流式處理方法是點播傳送。</span><span class="sxs-lookup"><span data-stu-id="4deb2-165">If you do not open any applications during this step, the default streaming method is on-demand streaming delivery.</span></span> <span data-ttu-id="4deb2-166">這表示應用程式將會按位下載，直到可以開啟，然後根據背景載入的設定方式，將會載入應用程式的其餘部分。</span><span class="sxs-lookup"><span data-stu-id="4deb2-166">This means applications will be downloaded bit by bit until it can be opened, and then depending on how the background loading is configured, will load the rest of the application.</span></span>



13. <span data-ttu-id="4deb2-167">在 [**目標作業系統**] 頁面上，指定可執行此套件的作業系統。</span><span class="sxs-lookup"><span data-stu-id="4deb2-167">On the **Target OS** page, specify the operating systems that can run this package.</span></span> <span data-ttu-id="4deb2-168">若要允許您環境中所有受支援的作業系統執行這個套件，請選取 [**允許此套件在任何作業系統上執行**]。</span><span class="sxs-lookup"><span data-stu-id="4deb2-168">To allow all supported operating systems in your environment to run this package, select **Allow this package to run on any operating system**.</span></span> <span data-ttu-id="4deb2-169">若要將這個套件設定為只在特定作業系統上執行，請選取 [**只允許此套件在下列作業系統上**執行]，然後選取可以執行此套件的作業系統。</span><span class="sxs-lookup"><span data-stu-id="4deb2-169">To configure this package to run only on specific operating systems, select **Allow this package to run only on the following operating systems** and select the operating systems that can run this package.</span></span> <span data-ttu-id="4deb2-170">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="4deb2-170">Click **Next**.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="4deb2-171">請確定您在此處指定的作業系統是由您所排序的應用程式所支援。</span><span class="sxs-lookup"><span data-stu-id="4deb2-171">Make sure that the operating systems you specify here are supported by the application you are sequencing.</span></span>



14. <span data-ttu-id="4deb2-172">隨即會顯示 [**建立套件**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="4deb2-172">The **Create Package** page is displayed.</span></span> <span data-ttu-id="4deb2-173">若要在不儲存的情況下修改套件，請選取 [**繼續使用套件編輯器修改套件而不儲存**]。</span><span class="sxs-lookup"><span data-stu-id="4deb2-173">To modify the package without saving it, select **Continue to modify package without saving using the package editor**.</span></span> <span data-ttu-id="4deb2-174">此選項會在 sequencer 視窗中開啟套件，讓您可以在儲存套件之前加以修改。</span><span class="sxs-lookup"><span data-stu-id="4deb2-174">This option opens the package in the sequencer console so that you can modify the package before it is saved.</span></span> <span data-ttu-id="4deb2-175">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="4deb2-175">Click **Next**.</span></span>

   <span data-ttu-id="4deb2-176">若要立即儲存套件，請選取 [**立即儲存套件**] （預設）。</span><span class="sxs-lookup"><span data-stu-id="4deb2-176">To save the package immediately, select **Save the package now** (default).</span></span> <span data-ttu-id="4deb2-177">新增要與套件相關聯的選擇性**批註**。</span><span class="sxs-lookup"><span data-stu-id="4deb2-177">Add optional **Comments** to be associated with the package.</span></span> <span data-ttu-id="4deb2-178">若要識別程式版本及有關套件的其他資訊，可以使用批註。</span><span class="sxs-lookup"><span data-stu-id="4deb2-178">Comments are useful for identifying the program version and other information about the package.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="4deb2-179">系統不支援**批註**和**描述**中不能列印的字元。</span><span class="sxs-lookup"><span data-stu-id="4deb2-179">The system does not support non-printable characters in **Comments** and **Descriptions**.</span></span>



~~~
The default **Save Location** is also displayed on this page. To change the default location, click **Browse** and specify the new location. Click **Create**.
~~~

15. <span data-ttu-id="4deb2-180">[**完成**] 頁面隨即出現。</span><span class="sxs-lookup"><span data-stu-id="4deb2-180">The **Completion** page is displayed.</span></span> <span data-ttu-id="4deb2-181">視需要查看**虛擬應用程式套件報告**窗格中的資訊，然後按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="4deb2-181">Review the information in the **Virtual Application Package Report** pane as needed, then click **Close**.</span></span> <span data-ttu-id="4deb2-182">您也可以在建立套件之目錄中的**Report.xml**檔案中找到此資訊。</span><span class="sxs-lookup"><span data-stu-id="4deb2-182">This information is also available in the **Report.xml** file that is located in the directory where the package was created.</span></span>

   <span data-ttu-id="4deb2-183">套件現在可在 sequencer 中取得。</span><span class="sxs-lookup"><span data-stu-id="4deb2-183">The package is now available in the sequencer.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="4deb2-184">成功建立虛擬應用程式套件之後，您就無法在執行排序器的電腦上執行虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="4deb2-184">After you have successfully created a virtual application package, you cannot run the virtual application package on the computer that is running the sequencer.</span></span>



**<span data-ttu-id="4deb2-185">為附加元件或外掛程式應用程式排序</span><span class="sxs-lookup"><span data-stu-id="4deb2-185">To sequence an add-on or plug-in application</span></span>**

1. > [!NOTE]  
   > <span data-ttu-id="4deb2-186">在執行下列程式之前，請先在執行排序器的電腦上本機安裝上層應用程式。</span><span class="sxs-lookup"><span data-stu-id="4deb2-186">Before performing the following procedure, install the parent application locally on the computer that is running the sequencer.</span></span> <span data-ttu-id="4deb2-187">或者，如果您已將上層應用程式虛擬化，您可以按照附加元件或外掛程式工作流程中的步驟，將上層應用程式解包到電腦上。</span><span class="sxs-lookup"><span data-stu-id="4deb2-187">Or if you have the parent application virtualized, you can follow the steps in the add-on or plug-in workflow to unpack the parent application on the computer.</span></span>
   >
   > <span data-ttu-id="4deb2-188">例如，如果您要為 Microsoft Excel 的外掛程式進行排序，請在執行排序器的電腦上本機安裝 Microsoft Excel。</span><span class="sxs-lookup"><span data-stu-id="4deb2-188">For example, if you are sequencing a plug-in for Microsoft Excel, install Microsoft Excel locally on the computer that is running the sequencer.</span></span> <span data-ttu-id="4deb2-189">您也可以在安裝了應用程式的目的電腦上，將上層應用程式安裝在同一個目錄中。</span><span class="sxs-lookup"><span data-stu-id="4deb2-189">Also install the parent application in the same directory where the application is installed on target computers.</span></span> <span data-ttu-id="4deb2-190">如果外掛程式或附加元件要與現有的虛擬應用程式套件搭配使用，請在建立父虛擬應用程式套件時，將應用程式安裝在所用的同一個虛擬應用程式磁碟機上。</span><span class="sxs-lookup"><span data-stu-id="4deb2-190">If the plug-in or add-on is going to be used with an existing virtual application package, install the application on the same virtual application drive that was used when you created the parent virtual application package.</span></span>



~~~
On the computer that runs the sequencer, click **All Programs**, and then Click **Microsoft Application Virtualization**, and then click **Microsoft Application Virtualization Sequencer**.
~~~

2. <span data-ttu-id="4deb2-191">*<strong><em>在 sequencer 中，按一下 [* </em> 建立新的虛擬應用程式套件] </strong> 。</span><span class="sxs-lookup"><span data-stu-id="4deb2-191">\*<strong><em>In the sequencer, click \*</em>Create a New Virtual Application Package</strong>.</span></span> <span data-ttu-id="4deb2-192">選取 [**建立套件（預設）**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4deb2-192">Select **Create Package (default)**, and then click **Next**.</span></span>

3. <span data-ttu-id="4deb2-193">在 [**準備電腦**] 頁面上，查看可能導致套件建立失敗的問題，或可能導致套件包含不必要的資料。</span><span class="sxs-lookup"><span data-stu-id="4deb2-193">On the **Prepare Computer** page, review the issues that might cause the package creation to fail or could cause the package to contain unnecessary data.</span></span> <span data-ttu-id="4deb2-194">繼續進行之前，您應該先解決所有潛在問題。</span><span class="sxs-lookup"><span data-stu-id="4deb2-194">You should resolve all potential issues before you continue.</span></span> <span data-ttu-id="4deb2-195">進行任何修正之後 **，按一下 [** 重新整理] 以顯示更新的資訊。</span><span class="sxs-lookup"><span data-stu-id="4deb2-195">After making any corrections, click **Refresh** to display the updated information.</span></span> <span data-ttu-id="4deb2-196">解決所有可能的問題之後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4deb2-196">After you have resolved all potential issues, click **Next**.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="4deb2-197">如果您需要停用病毒掃描軟體，您應該先掃描執行 sequencer 的電腦，以確保無法將不想要的或惡意檔案新增到套件中。</span><span class="sxs-lookup"><span data-stu-id="4deb2-197">If you are required to disable virus scanning software, you should first scan the computer that runs the sequencer in order to ensure that no unwanted or malicious files could be added to the package.</span></span>



4. <span data-ttu-id="4deb2-198">在 [**應用程式類型**] 頁面上，選取 [**附加元件] 或 [外掛程式]**，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4deb2-198">On the **Type of Application** page, select **Add-on or Plug-in**, and then click **Next**.</span></span>

5. <span data-ttu-id="4deb2-199">在 [**選取安裝程式**] 頁面上，按一下 **[流覽]** ，然後指定附加元件或外掛程式的安裝檔。</span><span class="sxs-lookup"><span data-stu-id="4deb2-199">On the **Select Installer** page, click **Browse** and specify the installation file for the add-on or plug-in.</span></span> <span data-ttu-id="4deb2-200">如果附加元件或外掛程式沒有關聯的安裝程式檔案，且您打算手動執行所有安裝步驟，請選取 [**選取此選項以執行自訂安裝**] 核取方塊，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4deb2-200">If the add-on or plug-in does not have an associated installer file and you plan to run all installation steps manually, select the **Select this option to perform a custom installation** check box, and then click **Next**.</span></span>

6. <span data-ttu-id="4deb2-201">在 [**安裝] 主**版頁面上，確認已在執行排序器的電腦上安裝主要應用程式。</span><span class="sxs-lookup"><span data-stu-id="4deb2-201">On the **Install Primary** page, ensure that the primary application is installed on the computer that runs the sequencer.</span></span> <span data-ttu-id="4deb2-202">或者，您可以在執行排序器的電腦上，展開已儲存在本機的現有套件。</span><span class="sxs-lookup"><span data-stu-id="4deb2-202">Alternatively, you can expand an existing package that has been saved locally on the computer that runs the sequencer.</span></span> <span data-ttu-id="4deb2-203">若要這樣做，請按一下 [**展開套件**]，然後選取套件。</span><span class="sxs-lookup"><span data-stu-id="4deb2-203">To do this, click **Expand Package**, and then select the package.</span></span> <span data-ttu-id="4deb2-204">展開或安裝上層程式後，請選取 **[我已安裝主要上層程式**]。</span><span class="sxs-lookup"><span data-stu-id="4deb2-204">After you have expanded or installed the parent program, select **I have installed the primary parent program**.</span></span>

   <span data-ttu-id="4deb2-205">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="4deb2-205">Click **Next**.</span></span>

7. <span data-ttu-id="4deb2-206">在 [**套件名稱**] 頁面上，輸入將與套件建立關聯的名稱。</span><span class="sxs-lookup"><span data-stu-id="4deb2-206">On the **Package Name** page, type a name that will be associated with the package.</span></span> <span data-ttu-id="4deb2-207">使用名稱，協助識別將新增到套件中之應用程式的用途和版本。</span><span class="sxs-lookup"><span data-stu-id="4deb2-207">Use a name that helps identify the purpose and version of the application that will be added to the package.</span></span> <span data-ttu-id="4deb2-208">套件名稱將會顯示在 App-v 5.0 管理主控台中。</span><span class="sxs-lookup"><span data-stu-id="4deb2-208">The package name will be displayed in the App-V 5.0 Management Console.</span></span>

   <span data-ttu-id="4deb2-209">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="4deb2-209">Click **Next**.</span></span>

8. <span data-ttu-id="4deb2-210">在 [**安裝**] 頁面上，當排序器和應用程式安裝程式準備好時，您可以繼續安裝外掛程式或增益集應用程式，讓排序器可以監視安裝程式。</span><span class="sxs-lookup"><span data-stu-id="4deb2-210">On the **Installation** page, when the sequencer and application installer are ready you can proceed to install the plug-in or add-in application so the sequencer can monitor the installation process.</span></span> <span data-ttu-id="4deb2-211">使用應用程式的安裝程式來執行安裝。</span><span class="sxs-lookup"><span data-stu-id="4deb2-211">Use the application's installation process to perform the installation.</span></span> <span data-ttu-id="4deb2-212">如果安裝時必須執行其他安裝檔案，請按一下 [**執行**]，然後找出並執行其他安裝檔案。</span><span class="sxs-lookup"><span data-stu-id="4deb2-212">If additional installation files must be run as part of the installation, click **Run** and locate and run the additional installation files.</span></span> <span data-ttu-id="4deb2-213">完成安裝後，請選取 [**我已完成安裝**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4deb2-213">When you are finished with the installation, select **I am finished installing**, and then click **Next**.</span></span>

9. <span data-ttu-id="4deb2-214">在 [**安裝報告**] 頁面上，您可以查看剛剛排序的虛擬應用程式套件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="4deb2-214">On the **Installation Report** page, you can review information about the virtual application package that you just sequenced.</span></span> <span data-ttu-id="4deb2-215">如需**其他資訊**所顯示之資訊的詳細說明，請按兩下該事件。</span><span class="sxs-lookup"><span data-stu-id="4deb2-215">For a more detailed explanation about the information displayed in **Additional Information**, double-click the event.</span></span> <span data-ttu-id="4deb2-216">審閱資訊之後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4deb2-216">After you have reviewed the information, click **Next**.</span></span>

10. <span data-ttu-id="4deb2-217">隨即會顯示 [**自訂**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="4deb2-217">The **Customize** page is displayed.</span></span> <span data-ttu-id="4deb2-218">如果您已完成安裝並設定虛擬應用程式，請選取 [**立即停止**]，然後跳至此程式的步驟12。</span><span class="sxs-lookup"><span data-stu-id="4deb2-218">If you are finished installing and configuring the virtual application, select **Stop now** and skip to step 12 of this procedure.</span></span> <span data-ttu-id="4deb2-219">若要執行下列其中一項自訂作業，請選取 [**自訂**]。</span><span class="sxs-lookup"><span data-stu-id="4deb2-219">To perform either of the following customizations, select **Customize**.</span></span>

    -   <span data-ttu-id="4deb2-220">優化套件在慢速或不可靠的網路上的執行方式。</span><span class="sxs-lookup"><span data-stu-id="4deb2-220">Optimize how the package will run across a slow or unreliable network.</span></span>

    -   <span data-ttu-id="4deb2-221">指定可以執行此套件的作業系統。</span><span class="sxs-lookup"><span data-stu-id="4deb2-221">Specify the operating systems that can run this package.</span></span>

    <span data-ttu-id="4deb2-222">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="4deb2-222">Click **Next**.</span></span>

11. <span data-ttu-id="4deb2-223">在 [**流式處理**] 頁面上，執行每個程式，讓它能在目的電腦上優化並更有效率地執行。</span><span class="sxs-lookup"><span data-stu-id="4deb2-223">On the **Streaming** page, run each program so that it can be optimized and run more efficiently on target computers.</span></span> <span data-ttu-id="4deb2-224">[資料流程] 可改善在高延遲網路上的目的電腦上執行虛擬應用程式套件時的體驗。</span><span class="sxs-lookup"><span data-stu-id="4deb2-224">Streaming improves the experience when the virtual application package is run on target computers on high-latency networks.</span></span> <span data-ttu-id="4deb2-225">可能需要幾分鐘的時間，所有應用程式才會執行。</span><span class="sxs-lookup"><span data-stu-id="4deb2-225">It can take several minutes for all the applications to run.</span></span> <span data-ttu-id="4deb2-226">在所有應用程式都已執行之後，請關閉每個應用程式。</span><span class="sxs-lookup"><span data-stu-id="4deb2-226">After all applications have run, close each of the applications.</span></span> <span data-ttu-id="4deb2-227">您也可以選取 [**強制下載應用程式**] 核取方塊，將套件設定為必須在開啟之前完全下載。</span><span class="sxs-lookup"><span data-stu-id="4deb2-227">You can also configure the package to be required to be fully downloaded before opening by selecting the **Force applications to be downloaded** check-box.</span></span> <span data-ttu-id="4deb2-228">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="4deb2-228">Click **Next**.</span></span>

    > [!NOTE]  
    > <span data-ttu-id="4deb2-229">如有需要，您可以在此步驟中停止應用程式的載入。</span><span class="sxs-lookup"><span data-stu-id="4deb2-229">If necessary, you can stop an application from loading during this step.</span></span> <span data-ttu-id="4deb2-230">在 [**應用程式啟動**] 對話方塊中，按一下 [**停止**]，然後選取其中一個核取方塊： [**停止所有應用程式**] 或 [**僅停止此應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="4deb2-230">In the **Application Launch** dialog box, click **Stop** and select one of the check boxes: **Stop all applications** or **Stop this application only**.</span></span>



12. <span data-ttu-id="4deb2-231">在 [**目標作業系統**] 頁面上，指定可執行此套件的作業系統。</span><span class="sxs-lookup"><span data-stu-id="4deb2-231">On the **Target OS** page, specify the operating systems that can run this package.</span></span> <span data-ttu-id="4deb2-232">若要允許您環境中所有支援的作業系統執行這個套件，請選取 [**允許此套件在任何作業系統上執行**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="4deb2-232">To allow all supported operating systems in your environment to run this package, select the **Allow this package to run on any operating system** check box.</span></span> <span data-ttu-id="4deb2-233">若要將這個套件設定為只在特定作業系統上執行，請選取 [**只允許此套件在下列作業系統上執行**] 核取方塊，然後選取可以執行此套件的作業系統。</span><span class="sxs-lookup"><span data-stu-id="4deb2-233">To configure this package to run only on specific operating systems, select the **Allow this package to run only on the following operating systems** check box, and then select the operating systems that can run this package.</span></span> <span data-ttu-id="4deb2-234">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="4deb2-234">Click **Next**.</span></span>

13. <span data-ttu-id="4deb2-235">隨即會顯示 [**建立套件**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="4deb2-235">The **Create Package** page is displayed.</span></span> <span data-ttu-id="4deb2-236">若要在不儲存的情況下修改套件，請選取 **[繼續使用套件編輯器修改套件但不儲存**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="4deb2-236">To modify the package without saving it, select **Continue to modify package without saving using the package editor** check box.</span></span> <span data-ttu-id="4deb2-237">此選項會在 sequencer 視窗中開啟套件，讓您可以在儲存套件之前加以修改。</span><span class="sxs-lookup"><span data-stu-id="4deb2-237">This option opens the package in the sequencer console so that you can modify the package before it is saved.</span></span> <span data-ttu-id="4deb2-238">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="4deb2-238">Click **Next**.</span></span>

    <span data-ttu-id="4deb2-239">若要立即儲存套件，請選取 **[立即儲存套件**]。</span><span class="sxs-lookup"><span data-stu-id="4deb2-239">To save the package immediately, select **Save the package now**.</span></span> <span data-ttu-id="4deb2-240">您也可以選擇新增與套件相關聯的**描述**。</span><span class="sxs-lookup"><span data-stu-id="4deb2-240">Optionally, add a **Description** that will be associated with the package.</span></span> <span data-ttu-id="4deb2-241">描述對於識別套件的版本和其他資訊很有用。</span><span class="sxs-lookup"><span data-stu-id="4deb2-241">Descriptions are useful for identifying the version and other information about the package.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="4deb2-242">系統不支援批註和描述中不能列印的字元。</span><span class="sxs-lookup"><span data-stu-id="4deb2-242">The system does not support non-printable characters in Comments and Descriptions.</span></span>



~~~
The default **Save Location** is also displayed on this page. To change the default location, click **Browse** and specify the new location. Click **Create**.
~~~

**<span data-ttu-id="4deb2-243">為中介軟體應用程式排序</span><span class="sxs-lookup"><span data-stu-id="4deb2-243">To sequence a middleware application</span></span>**

1. <span data-ttu-id="4deb2-244">在執行排序器的電腦上，按一下 [**所有程式**]，然後按一下 [ **microsoft application**virtualization]，然後按一下 [ **microsoft application virtualization 排序**器]。</span><span class="sxs-lookup"><span data-stu-id="4deb2-244">On the computer that runs the sequencer, click **All Programs**, and then Click **Microsoft Application Virtualization**, and then click **Microsoft Application Virtualization Sequencer**.</span></span>

2. <span data-ttu-id="4deb2-245">*<strong><em>在 sequencer 中，按一下 [* </em> 建立新的虛擬應用程式套件] </strong> 。</span><span class="sxs-lookup"><span data-stu-id="4deb2-245">\*<strong><em>In the sequencer, click \*</em>Create a New Virtual Application Package</strong>.</span></span> <span data-ttu-id="4deb2-246">選取 [**建立套件（預設）**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4deb2-246">Select **Create Package (default)**, and then click **Next**.</span></span>

3. <span data-ttu-id="4deb2-247">在 [**準備電腦**] 頁面上，查看可能導致套件建立失敗的問題，或可能導致套件包含不必要的資料。</span><span class="sxs-lookup"><span data-stu-id="4deb2-247">On the **Prepare Computer** page, review the issues that could cause the package creation to fail or could cause the package to contain unnecessary data.</span></span> <span data-ttu-id="4deb2-248">繼續進行之前，您應該先解決所有潛在問題。</span><span class="sxs-lookup"><span data-stu-id="4deb2-248">You should resolve all potential issues before you continue.</span></span> <span data-ttu-id="4deb2-249">進行任何修正之後 **，按一下 [** 重新整理] 以顯示更新的資訊。</span><span class="sxs-lookup"><span data-stu-id="4deb2-249">After making any corrections, click **Refresh** to display the updated information.</span></span> <span data-ttu-id="4deb2-250">解決所有可能的問題之後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4deb2-250">After you have resolved all potential issues, click **Next**.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="4deb2-251">如果您需要停用病毒掃描軟體，您應該先掃描執行 App-v 5.0 Sequencer 的電腦，以確保無法將不想要的或惡意檔案新增到套件中。</span><span class="sxs-lookup"><span data-stu-id="4deb2-251">If you are required to disable virus scanning software, you should first scan the computer that runs the App-V 5.0 Sequencer in order to ensure that no unwanted or malicious files can be added to the package.</span></span>



4. <span data-ttu-id="4deb2-252">在 [**應用程式類型**] 頁面上，選取 [**中介軟體**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4deb2-252">On the **Type of Application** page, select **Middleware**, and then click **Next**.</span></span>

5. <span data-ttu-id="4deb2-253">在 [**選取安裝程式**] 頁面上，按一下 **[流覽]** ，然後指定應用程式的安裝檔。</span><span class="sxs-lookup"><span data-stu-id="4deb2-253">On the **Select Installer** page, click **Browse** and specify the installation file for the application.</span></span> <span data-ttu-id="4deb2-254">如果應用程式沒有關聯的安裝程式檔案，且您打算手動執行所有安裝步驟，請選取 [**選取此選項以執行自訂安裝**] 核取方塊，然後按一下 [**下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4deb2-254">If the application does not have an associated installer file and you plan to run all installation steps manually, select the **Select this option to perform a custom installation** check box, and then click **Next**.</span></span>

6. <span data-ttu-id="4deb2-255">在 [**套件名稱**] 頁面上，輸入將與套件建立關聯的名稱。</span><span class="sxs-lookup"><span data-stu-id="4deb2-255">On the **Package Name** page, type a name that will be associated with the package.</span></span> <span data-ttu-id="4deb2-256">使用名稱，協助識別將新增到套件中之應用程式的用途和版本。</span><span class="sxs-lookup"><span data-stu-id="4deb2-256">Use a name that helps identify the purpose and version of the application that will be added to the package.</span></span> <span data-ttu-id="4deb2-257">套件的名稱會顯示在 App-v 5.0 管理主控台中。</span><span class="sxs-lookup"><span data-stu-id="4deb2-257">The package name is displayed in the App-V 5.0 Management Console.</span></span>

   <span data-ttu-id="4deb2-258">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="4deb2-258">Click **Next**.</span></span>

7. <span data-ttu-id="4deb2-259">在 [**安裝**] 頁面上，當 sequencer 與中介軟體應用程式安裝程式準備就緒時，您可以繼續安裝應用程式，讓排序器可以監視安裝程式。</span><span class="sxs-lookup"><span data-stu-id="4deb2-259">On the **Installation** page, when the sequencer and middleware application installer are ready you can proceed to install the application so that the sequencer can monitor the installation process.</span></span> <span data-ttu-id="4deb2-260">使用應用程式的安裝程式來執行安裝。</span><span class="sxs-lookup"><span data-stu-id="4deb2-260">Use the application's installation process to perform the installation.</span></span> <span data-ttu-id="4deb2-261">如果安裝時必須執行其他安裝檔，請按一下 [**執行**]，找出並執行其他安裝檔案。</span><span class="sxs-lookup"><span data-stu-id="4deb2-261">If additional installation files must be run as part of the installation, click **Run**, to locate and run the additional installation files.</span></span> <span data-ttu-id="4deb2-262">完成安裝後，請選取 [**我已完成安裝**] 核取方塊，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4deb2-262">When you are finished with the installation, select the **I am finished installing** check box, and then click **Next**.</span></span>

8. <span data-ttu-id="4deb2-263">在 [**安裝**] 頁面上，請稍候，sequencer 會設定虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="4deb2-263">On the **Installation** page, wait while the sequencer configures the virtual application package.</span></span>

9. <span data-ttu-id="4deb2-264">在 [**安裝報告**] 頁面上，您可以查看您剛剛排序的虛擬應用程式套件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="4deb2-264">On the **Installation Report** page, you can review information about the virtual application package that you have just sequenced.</span></span> <span data-ttu-id="4deb2-265">在 [**其他資訊**] 中，按兩下事件以取得更詳細的資訊。</span><span class="sxs-lookup"><span data-stu-id="4deb2-265">In **Additional Information**, double-click an event to obtain more detailed information.</span></span> <span data-ttu-id="4deb2-266">若要繼續，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="4deb2-266">To proceed, click **Next**.</span></span>

10. <span data-ttu-id="4deb2-267">在 [**目標作業系統**] 頁面上，指定可執行此套件的作業系統。</span><span class="sxs-lookup"><span data-stu-id="4deb2-267">On the **Target OS** page, specify the operating systems that can run this package.</span></span> <span data-ttu-id="4deb2-268">若要在您的環境中啟用所有受支援的作業系統來執行這個套件，請選取 [**允許此套件在任何作業系統上執行**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="4deb2-268">To enable all supported operating systems in your environment to run this package, select the **Allow this package to run on any operating system** check box.</span></span> <span data-ttu-id="4deb2-269">若要將這個套件設定為只在特定作業系統上執行，請選取 [**只允許此套件在下列作業系統上執行**] 核取方塊，然後選取可以執行此套件的作業系統。</span><span class="sxs-lookup"><span data-stu-id="4deb2-269">To configure this package to run only on specific operating systems, select the **Allow this package to run only on the following operating systems** check box and select the operating systems that can run this package.</span></span> <span data-ttu-id="4deb2-270">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="4deb2-270">Click **Next**.</span></span>

11. <span data-ttu-id="4deb2-271">在 [**建立套件**] 頁面上隨即出現。</span><span class="sxs-lookup"><span data-stu-id="4deb2-271">On the **Create Package** page is displayed.</span></span> <span data-ttu-id="4deb2-272">若要在不儲存的情況下修改套件，請選取 [**繼續使用套件編輯器修改套件而不儲存**]。</span><span class="sxs-lookup"><span data-stu-id="4deb2-272">To modify the package without saving it, select **Continue to modify package without saving using the package editor**.</span></span> <span data-ttu-id="4deb2-273">此選項會在 sequencer 視窗中開啟套件，讓您可以在儲存套件之前加以修改。</span><span class="sxs-lookup"><span data-stu-id="4deb2-273">This option opens the package in the sequencer console so that you can modify the package before it is saved.</span></span> <span data-ttu-id="4deb2-274">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="4deb2-274">Click **Next**.</span></span>

    <span data-ttu-id="4deb2-275">若要立即儲存套件，請選取 **[立即儲存套件**]。</span><span class="sxs-lookup"><span data-stu-id="4deb2-275">To save the package immediately, select **Save the package now**.</span></span> <span data-ttu-id="4deb2-276">或者，您也可以新增要與套件相關聯的**描述**。</span><span class="sxs-lookup"><span data-stu-id="4deb2-276">Optionally, add a **Description** to be associated with the package.</span></span> <span data-ttu-id="4deb2-277">描述對於識別套件的程式版本和其他資訊很有用。</span><span class="sxs-lookup"><span data-stu-id="4deb2-277">Descriptions are useful for identifying the program version and other information about the package.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="4deb2-278">系統不支援批註和描述中不能列印的字元。</span><span class="sxs-lookup"><span data-stu-id="4deb2-278">The system does not support non-printable characters in Comments and Descriptions.</span></span>



~~~
The default **Save Location** is also displayed on this page. To change the default location, click **Browse** and specify the new location. Click **Create**.
~~~

12. <span data-ttu-id="4deb2-279">[**完成**] 頁面隨即出現。</span><span class="sxs-lookup"><span data-stu-id="4deb2-279">The **Completion** page is displayed.</span></span> <span data-ttu-id="4deb2-280">視需要查看**虛擬應用程式套件報告**窗格中的資訊，然後按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="4deb2-280">Review the information in the **Virtual Application Package Report** pane as needed, then click **Close**.</span></span> <span data-ttu-id="4deb2-281">您也可以在此程式步驟11所指定之目錄中的**Report.xml**檔案中找到此資訊。</span><span class="sxs-lookup"><span data-stu-id="4deb2-281">This information is also available in the **Report.xml** file that is located in the directory specified in step 11 of this procedure.</span></span>

   <span data-ttu-id="4deb2-282">套件現在可在 sequencer 中取得。</span><span class="sxs-lookup"><span data-stu-id="4deb2-282">The package is now available in the sequencer.</span></span> <span data-ttu-id="4deb2-283">若要編輯套件屬性，請按一下 **[編輯 \ [套件名稱 \]]**。</span><span class="sxs-lookup"><span data-stu-id="4deb2-283">To edit the package properties, click **Edit \[Package Name\]**.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="4deb2-284">成功建立虛擬應用程式套件之後，您就無法在執行排序器的電腦上執行虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="4deb2-284">After you have successfully created a virtual application package, you cannot run the virtual application package on the computer that is running the sequencer.</span></span>



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## <span data-ttu-id="4deb2-285">相關主題</span><span class="sxs-lookup"><span data-stu-id="4deb2-285">Related topics</span></span>


[<span data-ttu-id="4deb2-286">App-V 5.1 作業</span><span class="sxs-lookup"><span data-stu-id="4deb2-286">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)









