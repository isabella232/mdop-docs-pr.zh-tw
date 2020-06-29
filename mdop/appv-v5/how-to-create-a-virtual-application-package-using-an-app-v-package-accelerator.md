---
title: 如何使用 App-V 封裝加速器建立虛擬應用程式套件
description: 如何使用 App-V 封裝加速器建立虛擬應用程式套件
author: dansimp
ms.assetid: 715e7526-e100-419c-8fc1-75cbfe433835
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 547cb93f334e025243937a97a1f904410fe2d504
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800551"
---
# <span data-ttu-id="642b2-103">如何使用 App-V 封裝加速器建立虛擬應用程式套件</span><span class="sxs-lookup"><span data-stu-id="642b2-103">How to Create a Virtual Application Package Using an App-V Package Accelerator</span></span>


**<span data-ttu-id="642b2-104">重要</span><span class="sxs-lookup"><span data-stu-id="642b2-104">Important</span></span>**  
<span data-ttu-id="642b2-105">App-v 5.0 Sequencer 不會授與您用來建立套件加速器之軟體應用程式的任何授權許可權。</span><span class="sxs-lookup"><span data-stu-id="642b2-105">The App-V 5.0 Sequencer does not grant any license rights to the software application that you use to create the Package Accelerator.</span></span> <span data-ttu-id="642b2-106">您必須遵守您所使用之應用程式的所有使用者授權合約。</span><span class="sxs-lookup"><span data-stu-id="642b2-106">You must abide by all end user license terms for the application that you use.</span></span> <span data-ttu-id="642b2-107">您有責任確認軟體應用程式的授權條款可讓您使用 App-v 5.0 排序器建立套件加速器。</span><span class="sxs-lookup"><span data-stu-id="642b2-107">It is your responsibility to make sure that the software application’s license terms allow you to create a Package Accelerator with the App-V 5.0 Sequencer.</span></span>



<span data-ttu-id="642b2-108">使用下列程式來建立含有 App-v 5.0 套件加速器的虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="642b2-108">Use the following procedure to create a virtual application package with the App-V 5.0 Package Accelerator.</span></span>

**<span data-ttu-id="642b2-109">注意</span><span class="sxs-lookup"><span data-stu-id="642b2-109">Note</span></span>**  
<span data-ttu-id="642b2-110">開始此程式之前，請先將所需的套件加速器複製到執行 App-v 5.0 排序器的電腦上。</span><span class="sxs-lookup"><span data-stu-id="642b2-110">Before you start this procedure, copy the required Package Accelerator locally to the computer that runs the App-V 5.0 Sequencer.</span></span> <span data-ttu-id="642b2-111">您也應該將套件的所有必要安裝檔案，複製到執行排序器的電腦上的本機目錄。</span><span class="sxs-lookup"><span data-stu-id="642b2-111">You should also copy all required installation files for the package to a local directory on the computer that runs the Sequencer.</span></span> <span data-ttu-id="642b2-112">這是您必須在此程式步驟5中指定的目錄。</span><span class="sxs-lookup"><span data-stu-id="642b2-112">This is the directory that you have to specify in step 5 of this procedure.</span></span>



**<span data-ttu-id="642b2-113">若要使用 App-v 5.0 套件加速器建立虛擬應用程式套件</span><span class="sxs-lookup"><span data-stu-id="642b2-113">To create a virtual application package with an App-V 5.0 Package Accelerator</span></span>**

1.  <span data-ttu-id="642b2-114">若要啟動 app-v 排序器，請在執行 app-v 5.0 排序器的電腦上，按一下 [**開始**  /  **所有程式**]  /  。**microsoft application virtualization**  /  **microsoft application virtualization 排序**器。</span><span class="sxs-lookup"><span data-stu-id="642b2-114">To start the App-V Sequencer, on the computer that runs the App-V 5.0 Sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="642b2-115">若要啟動 [**建立新套件] 嚮導**，請按一下 [**建立新的虛擬應用程式套件**]。</span><span class="sxs-lookup"><span data-stu-id="642b2-115">To start the **Create New Package Wizard**, click **Create a New Virtual Application Package**.</span></span> <span data-ttu-id="642b2-116">若要建立套件，請選取 [**使用套件加速器建立套件**] 核取方塊，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="642b2-116">To create the package, select the **Create Package using a Package Accelerator** check box, and then click **Next**.</span></span>

3.  <span data-ttu-id="642b2-117">若要指定將用來建立新的虛擬應用程式套件的套件加速器，請在 [**選取套件加速器**] 頁面上按一下 **[流覽]** 。</span><span class="sxs-lookup"><span data-stu-id="642b2-117">To specify the package accelerator that will be used to create the new virtual application package, click **Browse** on the **Select Package Accelerator** page.</span></span> <span data-ttu-id="642b2-118">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="642b2-118">Click **Next**.</span></span>

    **<span data-ttu-id="642b2-119">重要</span><span class="sxs-lookup"><span data-stu-id="642b2-119">Important</span></span>**  
    <span data-ttu-id="642b2-120">如果無法驗證套件加速器的發行者，且不包含有效的數位簽章，請在您按一下 [**執行**] 前，確認您是否信任套件加速器的來源。</span><span class="sxs-lookup"><span data-stu-id="642b2-120">If the publisher of the package accelerator cannot be verified and does not contain a valid digital signature, then before you click **Run**, you must confirm that you trust the source of the package accelerator.</span></span> <span data-ttu-id="642b2-121">在 [**安全性警告**] 對話方塊中確認您的選擇。</span><span class="sxs-lookup"><span data-stu-id="642b2-121">Confirm your choice in the **Security Warning** dialog box.</span></span>



4.  <span data-ttu-id="642b2-122">在 [**指導**方針] 頁面上，查看 [資訊] 窗格中顯示的發佈指導資訊。</span><span class="sxs-lookup"><span data-stu-id="642b2-122">On the **Guidance** page, review the publishing guidance information that is displayed in the information pane.</span></span> <span data-ttu-id="642b2-123">此資訊是在建立套件加速器時新增，且包含如何建立及發佈套件的相關指導方針。</span><span class="sxs-lookup"><span data-stu-id="642b2-123">This information was added when the Package Accelerator was created and it contains guidance about how to create and publish the package.</span></span> <span data-ttu-id="642b2-124">若要將指南資訊匯出至文字（.txt）檔案，請按一下 [**匯出**] 並指定要儲存檔案的位置，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="642b2-124">To export the guidance information to a text (.txt) file, click **Export** and specify the location where the file should be saved, and then click **Next**.</span></span>

5.  <span data-ttu-id="642b2-125">在 [**選取安裝**檔案] 頁面上，按一下 [**建立新資料夾**]，以建立一個本機資料夾，其中包含套件所需的所有安裝檔案，並指定該資料夾的儲存位置。</span><span class="sxs-lookup"><span data-stu-id="642b2-125">On the **Select Installation Files** page, click **Make New Folder** to create a local folder that contains all required installation files for the package, and specify where the folder should be saved.</span></span> <span data-ttu-id="642b2-126">您也必須指定要指派給資料夾的名稱。</span><span class="sxs-lookup"><span data-stu-id="642b2-126">You must also specify a name to be assigned to the folder.</span></span> <span data-ttu-id="642b2-127">接著，您必須將所有所需的安裝檔案複製到您指定的位置。</span><span class="sxs-lookup"><span data-stu-id="642b2-127">You must then copy all required installation files to the location that you specified.</span></span> <span data-ttu-id="642b2-128">如果包含安裝檔的資料夾已經存在於執行排序器的電腦上，請按一下 **[流覽]** 以選取該資料夾。</span><span class="sxs-lookup"><span data-stu-id="642b2-128">If the folder that contains the installation files already exists on the computer that runs the Sequencer, click **Browse** to select the folder.</span></span>

    <span data-ttu-id="642b2-129">或者，如果您已將安裝檔案複製到此電腦上的目錄，請按一下 [**建立新資料夾**]，流覽到包含安裝檔案的資料夾，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="642b2-129">Alternatively, if you have already copied the installation files to a directory on this computer, click **Make New Folder**, browse to the folder that contains the installation files, and then click **Next**.</span></span>

    **<span data-ttu-id="642b2-130">注意</span><span class="sxs-lookup"><span data-stu-id="642b2-130">Note</span></span>**  
    <span data-ttu-id="642b2-131">您可以指定下列支援的安裝檔案類型：</span><span class="sxs-lookup"><span data-stu-id="642b2-131">You can specify the following types of supported installation files:</span></span>

    -   <span data-ttu-id="642b2-132">Windows Installer 檔案（**.msi**）</span><span class="sxs-lookup"><span data-stu-id="642b2-132">Windows Installer files (**.msi**)</span></span>

    -   <span data-ttu-id="642b2-133">Cabinet 檔案（.cab）</span><span class="sxs-lookup"><span data-stu-id="642b2-133">Cabinet files (.cab)</span></span>

    -   <span data-ttu-id="642b2-134">副檔名為 .zip 的壓縮檔案</span><span class="sxs-lookup"><span data-stu-id="642b2-134">Compressed files with a .zip file name extension</span></span>

    -   <span data-ttu-id="642b2-135">實際的應用程式檔案</span><span class="sxs-lookup"><span data-stu-id="642b2-135">The actual application files</span></span>

    <span data-ttu-id="642b2-136">下列檔案類型不受支援： **.msp**與 **.exe**檔案。</span><span class="sxs-lookup"><span data-stu-id="642b2-136">The following file types are not supported: **.msp** and **.exe** files.</span></span> <span data-ttu-id="642b2-137">如果您指定 **.exe**檔案，您必須手動解壓縮安裝檔案。</span><span class="sxs-lookup"><span data-stu-id="642b2-137">If you specify an **.exe** file, you must extract the installation files manually.</span></span>



~~~
If the package accelerator requires an application to be installed before you apply the Package Accelerator, and if you have already installed the required application, select **I have installed all applications**, and then click **Next** on the **Local Installation** page.
~~~

6. <span data-ttu-id="642b2-138">在 [**套件名稱**] 頁面上，指定將與套件建立關聯的名稱。</span><span class="sxs-lookup"><span data-stu-id="642b2-138">On the **Package Name** page, specify a name that will be associated with the package.</span></span> <span data-ttu-id="642b2-139">您指定的名稱會在 App V 管理主控台中識別套件。</span><span class="sxs-lookup"><span data-stu-id="642b2-139">The name that you specify identifies the package in the App-V Management Console.</span></span> <span data-ttu-id="642b2-140">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="642b2-140">Click **Next**.</span></span>

7. <span data-ttu-id="642b2-141">在 [**建立套件**] 頁面上，提供將與套件相關聯的批註。</span><span class="sxs-lookup"><span data-stu-id="642b2-141">On the **Create Package** page, provide comments that will be associated with the package.</span></span> <span data-ttu-id="642b2-142">批註應該包含您正在建立之套件的識別資訊。</span><span class="sxs-lookup"><span data-stu-id="642b2-142">The comments should contain identifying information about the package that you are creating.</span></span> <span data-ttu-id="642b2-143">若要確認建立套件的位置，請查看 [**儲存位置**] 中顯示的資訊。</span><span class="sxs-lookup"><span data-stu-id="642b2-143">To confirm the location where the package is created, review the information that is displayed in **Save Location**.</span></span> <span data-ttu-id="642b2-144">若要壓縮套件，請選取 [**壓縮套件**]。</span><span class="sxs-lookup"><span data-stu-id="642b2-144">To compress the package, select **Compress Package**.</span></span> <span data-ttu-id="642b2-145">如果套件將在網路上流動，或者套件大小超過 4 GB，請選取 [**壓縮套件**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="642b2-145">Select the **Compress Package** check box if the package will be streamed across the network, or when the package size exceeds 4 GB.</span></span>

   <span data-ttu-id="642b2-146">若要建立套件，請按一下 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="642b2-146">To create the package, click **Create**.</span></span> <span data-ttu-id="642b2-147">建立套件後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="642b2-147">After the package is created, click **Next**.</span></span>

8. <span data-ttu-id="642b2-148">在 [**設定軟體**] 頁面上，若要啟用排序器來設定套件中包含的應用程式，請選取 [**設定軟體**]。</span><span class="sxs-lookup"><span data-stu-id="642b2-148">On the **Configure Software** page, to enable the Sequencer to configure the applications that are contained in the package, select **Configure Software**.</span></span> <span data-ttu-id="642b2-149">在此步驟中，您可以設定任何必須完成才能在目的電腦上執行應用程式的相關工作。</span><span class="sxs-lookup"><span data-stu-id="642b2-149">In this step you can configure any associated tasks that must be completed in order to run the application on the target computers.</span></span> <span data-ttu-id="642b2-150">例如，您可以設定任何相關的授權協定。</span><span class="sxs-lookup"><span data-stu-id="642b2-150">For example, you can configure any associated license agreements.</span></span>

   <span data-ttu-id="642b2-151">如果您選取 [**設定軟體**]，則可以使用 Sequencer 來設定下列專案，做為此步驟的一部分：</span><span class="sxs-lookup"><span data-stu-id="642b2-151">If you select **Configure Software**, the following items can be configured using the Sequencer as part of this step:</span></span>

   -   <span data-ttu-id="642b2-152">**載入套件**。</span><span class="sxs-lookup"><span data-stu-id="642b2-152">**Load Package**.</span></span> <span data-ttu-id="642b2-153">Sequencer 會載入與套件相關聯的檔案。</span><span class="sxs-lookup"><span data-stu-id="642b2-153">The Sequencer loads the files that are associated with the package.</span></span> <span data-ttu-id="642b2-154">解碼套件可能需要數秒到1小時的時間。</span><span class="sxs-lookup"><span data-stu-id="642b2-154">It can take several seconds to an hour to decode the package.</span></span>

   -   <span data-ttu-id="642b2-155">**執行每個程式**。</span><span class="sxs-lookup"><span data-stu-id="642b2-155">**Run Each Program**.</span></span> <span data-ttu-id="642b2-156">您也可以選擇執行套件中包含的程式。</span><span class="sxs-lookup"><span data-stu-id="642b2-156">Optionally run the programs that are contained in the package.</span></span> <span data-ttu-id="642b2-157">在您部署並在目的電腦上執行套件之前，請先完成執行應用程式所需的任何相關授權或配置工作，才能執行此步驟。</span><span class="sxs-lookup"><span data-stu-id="642b2-157">This step is helpful to complete any associated license or configuration tasks that are required to run the application before you deploy and run the package on target computers.</span></span> <span data-ttu-id="642b2-158">若要一次執行所有程式，請選取至少一個程式，然後按一下 [**全部執行**]。</span><span class="sxs-lookup"><span data-stu-id="642b2-158">To run all the programs at once, select at least one program, and then click **Run All**.</span></span> <span data-ttu-id="642b2-159">若要執行特定程式，請選取您要執行的程式或程式，然後按一下 [**執行選取**的專案]。</span><span class="sxs-lookup"><span data-stu-id="642b2-159">To run specific programs, select the program or programs that you want to run, and then click **Run Selected**.</span></span> <span data-ttu-id="642b2-160">完成所需的設定任務，然後關閉應用程式。</span><span class="sxs-lookup"><span data-stu-id="642b2-160">Complete the required configuration tasks, and then close the applications.</span></span> <span data-ttu-id="642b2-161">所有程式都可能需要幾分鐘的時間才能執行。</span><span class="sxs-lookup"><span data-stu-id="642b2-161">It can take several minutes for all programs to run.</span></span> <span data-ttu-id="642b2-162">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="642b2-162">Click **Next**.</span></span>

   -   <span data-ttu-id="642b2-163">[**儲存套件**]。</span><span class="sxs-lookup"><span data-stu-id="642b2-163">**Save Package**.</span></span> <span data-ttu-id="642b2-164">Sequencer 會儲存套件。</span><span class="sxs-lookup"><span data-stu-id="642b2-164">The Sequencer saves the package.</span></span>

   -   <span data-ttu-id="642b2-165">**主要功能區塊**。</span><span class="sxs-lookup"><span data-stu-id="642b2-165">**Primary Feature Block**.</span></span> <span data-ttu-id="642b2-166">排序器透過重建主要功能區塊來優化資料流程套件。</span><span class="sxs-lookup"><span data-stu-id="642b2-166">The Sequencer optimizes the package for streaming by rebuilding the primary feature block.</span></span>

   <span data-ttu-id="642b2-167">如果您不想要設定應用程式，請按一下 [**略過此步驟**]，然後移至此程式的步驟9，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="642b2-167">If you do not want to configure the applications, click **Skip this step**, and to go to step 9 of this procedure, and then click **Next**.</span></span>

9. <span data-ttu-id="642b2-168">在 [**完成**] 頁面上，檢查 [**虛擬應用程式套件報告**] 窗格中顯示的資訊後，按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="642b2-168">On the **Completion** page, after you review the information that is displayed in the **Virtual Application Package Report** pane, click **Close**.</span></span>

   <span data-ttu-id="642b2-169">套件現在可在 Sequencer 中取得。</span><span class="sxs-lookup"><span data-stu-id="642b2-169">The package is now available in the Sequencer.</span></span> <span data-ttu-id="642b2-170">若要編輯套件屬性，請按一下 **[編輯 \ [套件名稱 \]]**。</span><span class="sxs-lookup"><span data-stu-id="642b2-170">To edit the package properties, click **Edit \[Package Name\]**.</span></span> <span data-ttu-id="642b2-171">如需如何修改套件的詳細資訊，請參閱[如何修改現有的虛擬應用程式套件](how-to-modify-an-existing-virtual-application-package-beta.md)。</span><span class="sxs-lookup"><span data-stu-id="642b2-171">For more information about how to modify a package, see [How to Modify an Existing Virtual Application Package](how-to-modify-an-existing-virtual-application-package-beta.md).</span></span>

   <span data-ttu-id="642b2-172">您**有應用程式-V 的建議**嗎？</span><span class="sxs-lookup"><span data-stu-id="642b2-172">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="642b2-173">在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="642b2-173">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="642b2-174">有應用程式-V 問題嗎？</span><span class="sxs-lookup"><span data-stu-id="642b2-174">Got an App-V issue?</span></span>** <span data-ttu-id="642b2-175">使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="642b2-175">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="642b2-176">相關主題</span><span class="sxs-lookup"><span data-stu-id="642b2-176">Related topics</span></span>


[<span data-ttu-id="642b2-177">App-V 5.0 作業</span><span class="sxs-lookup"><span data-stu-id="642b2-177">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)









