---
title: 如何套用套件加速器以建立虛擬應用程式套件（App-v 4.6 SP1）
description: 如何套用套件加速器以建立虛擬應用程式套件（App-v 4.6 SP1）
author: dansimp
ms.assetid: ca0bd514-2bbf-4130-8c77-98d991cbe016
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ce6960fb95cce7f5e0eeb111412f27f945b0c1a5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808721"
---
# <span data-ttu-id="be7b5-103">如何套用套件加速器以建立虛擬應用程式套件（App-v 4.6 SP1）</span><span class="sxs-lookup"><span data-stu-id="be7b5-103">How to Apply a Package Accelerator to Create a Virtual Application Package (App-V 4.6 SP1)</span></span>


<span data-ttu-id="be7b5-104">您可以使用 App-v 包加速器來自動產生新的虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="be7b5-104">You can use App-V Package Accelerators to automatically generate a new virtual application package.</span></span> <span data-ttu-id="be7b5-105">如需有關套件加速器的詳細資訊，請參閱[關於 App v 封裝快速鍵（app-v 4.6 SP1）](about-app-v-package-accelerators--app-v-46-sp1-.md)。</span><span class="sxs-lookup"><span data-stu-id="be7b5-105">For more information about Package Accelerators, see [About App-V Package Accelerators (App-V 4.6 SP1)](about-app-v-package-accelerators--app-v-46-sp1-.md).</span></span>

**<span data-ttu-id="be7b5-106">重要</span><span class="sxs-lookup"><span data-stu-id="be7b5-106">Important</span></span>**  
<span data-ttu-id="be7b5-107">免責聲明：應用程式虛擬化 Sequencer 不會提供您用來建立套件加速器之軟體應用程式的授權權利。</span><span class="sxs-lookup"><span data-stu-id="be7b5-107">Disclaimer: The Application Virtualization Sequencer does not give you any license rights to the software application you are using to create a Package Accelerator.</span></span> <span data-ttu-id="be7b5-108">您必須遵守此類應用程式的所有使用者授權合約。</span><span class="sxs-lookup"><span data-stu-id="be7b5-108">You must abide by all end user license terms for such application.</span></span> <span data-ttu-id="be7b5-109">您有責任確認軟體應用程式的授權條款可讓您使用 Application Virtualization 排序器建立套件加速器。</span><span class="sxs-lookup"><span data-stu-id="be7b5-109">It is your responsibility to make sure the software application’s license terms allow you to create a Package Accelerator using Application Virtualization Sequencer.</span></span>



**<span data-ttu-id="be7b5-110">注意</span><span class="sxs-lookup"><span data-stu-id="be7b5-110">Note</span></span>**  
<span data-ttu-id="be7b5-111">開始此程式之前，請先在執行 App-v 排序器的電腦上，將所需的套件加速器複製到本機。</span><span class="sxs-lookup"><span data-stu-id="be7b5-111">Before starting this procedure, copy the required Package Accelerator locally to the computer running the App-V Sequencer.</span></span> <span data-ttu-id="be7b5-112">您也應該將套件的所有必要安裝檔案，複製到執行排序器的電腦上的本機目錄。</span><span class="sxs-lookup"><span data-stu-id="be7b5-112">You should also copy all required installation files for the package to a local directory on the computer running the Sequencer.</span></span> <span data-ttu-id="be7b5-113">這是您必須在此程式步驟5中指定的目錄。</span><span class="sxs-lookup"><span data-stu-id="be7b5-113">This is the directory that you have to specify in step 5 of this procedure.</span></span>



<span data-ttu-id="be7b5-114">使用下列程式來建立使用套件加速器的虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="be7b5-114">Use the following procedure to create a virtual application package by using a Package Accelerator.</span></span>

**<span data-ttu-id="be7b5-115">使用 App-v 包加速器建立虛擬應用程式套件</span><span class="sxs-lookup"><span data-stu-id="be7b5-115">To create a virtual application package by using an App-V Package Accelerator</span></span>**

1. <span data-ttu-id="be7b5-116">若要啟動 app-v 排序器，請在執行 app-v 排序器的電腦上，按一下 [**開始**  /  **所有程式**]  /  **microsoft application virtualization**  /  **microsoft application virtualization 排序**器。</span><span class="sxs-lookup"><span data-stu-id="be7b5-116">To start the App-V Sequencer, on the computer that is running the App-V Sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span>

2. <span data-ttu-id="be7b5-117">若要啟動 [**建立新套件] 嚮導**，請按一下 [**建立新的虛擬應用程式套件**]。</span><span class="sxs-lookup"><span data-stu-id="be7b5-117">To start the **Create New Package Wizard**, click **Create a New Virtual Application Package**.</span></span> <span data-ttu-id="be7b5-118">若要建立套件，請選取 [**使用套件加速器建立套件**] 核取方塊，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="be7b5-118">To create the package, select the **Create Package using a Package Accelerator** check box, and then click **Next**.</span></span>

3. <span data-ttu-id="be7b5-119">在 [**選取套件加速器**] 頁面上，若要指定將用來建立新的虛擬應用程式套件的套件加速器，請按一下 **[流覽]** ，找出您要使用的套件加速器。</span><span class="sxs-lookup"><span data-stu-id="be7b5-119">On the **Select Package Accelerator** page, to specify the Package Accelerator that will be used to create the new virtual application package, click **Browse** to locate the Package Accelerator that you want to use.</span></span> <span data-ttu-id="be7b5-120">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="be7b5-120">Click **Next**.</span></span>

   **<span data-ttu-id="be7b5-121">重要</span><span class="sxs-lookup"><span data-stu-id="be7b5-121">Important</span></span>**  
   <span data-ttu-id="be7b5-122">如果無法驗證套件加速器的發行者，且不包含有效的數位簽章，請在 [**安全性警告**] 對話方塊中，確認您在按一下 [**執行**] 之前，必須先確認您信任套件加速器的來源。</span><span class="sxs-lookup"><span data-stu-id="be7b5-122">If the publisher of the Package Accelerator cannot be verified and does not contain a valid digital signature, in the **Security Warning** dialog box, you must confirm that you trust the source of the Package Accelerator before you click **Run**.</span></span>



4. <span data-ttu-id="be7b5-123">在 [**指導**方針] 頁面上，查看 [資訊] 窗格中顯示的發佈指導資訊。</span><span class="sxs-lookup"><span data-stu-id="be7b5-123">On the **Guidance** page, review the publishing guidance information displayed in the information pane.</span></span> <span data-ttu-id="be7b5-124">所顯示的資訊是在建立套件加速器時新增，並包含建立及發佈套件的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="be7b5-124">The information displayed was added when the Package Accelerator was created and contains information about creating and publishing the package.</span></span> <span data-ttu-id="be7b5-125">若要將指南資訊匯出至文字（.txt）檔案，請按一下 [**匯出**] 並指定要儲存檔案的位置，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="be7b5-125">To export the guidance information to a text (.txt) file, click **Export** and specify the location where the file should be saved, and then click **Next**.</span></span>

5. <span data-ttu-id="be7b5-126">在 [**選取安裝**檔案] 頁面上，若要建立包含套件全部所需安裝檔案的本機資料夾，請按一下 [**建立新資料夾**]，並指定資料夾的儲存位置。</span><span class="sxs-lookup"><span data-stu-id="be7b5-126">On the **Select Installation Files** page, to create a local folder that contains all required installation files for the package, click **Make New Folder** and specify where the folder should be saved.</span></span> <span data-ttu-id="be7b5-127">您也必須指定要指派給資料夾的名稱。</span><span class="sxs-lookup"><span data-stu-id="be7b5-127">You must also specify a name to be assigned to the folder.</span></span> <span data-ttu-id="be7b5-128">接著，您必須將所有所需的安裝檔案複製到您指定的位置。</span><span class="sxs-lookup"><span data-stu-id="be7b5-128">You must then copy all required installation files to the location that you specified.</span></span> <span data-ttu-id="be7b5-129">如果包含安裝檔的資料夾已經存在於執行排序器的電腦上，請按一下 **[流覽]** 以選取該資料夾。</span><span class="sxs-lookup"><span data-stu-id="be7b5-129">If the folder that contains the installation files already exists on the computer running the Sequencer, click **Browse** to select the folder.</span></span>

   <span data-ttu-id="be7b5-130">或者，如果您已將安裝檔案複製到此電腦上的目錄，請按一下 [**建立新資料夾**]，流覽到包含安裝檔案的資料夾，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="be7b5-130">Alternatively, if you have already copied the installation files to a directory on this computer, click **Make New Folder**, browse to the folder that contains the installation files, and then click **Next**.</span></span>

   **<span data-ttu-id="be7b5-131">注意</span><span class="sxs-lookup"><span data-stu-id="be7b5-131">Note</span></span>**  
   <span data-ttu-id="be7b5-132">您可以指定下列支援的安裝檔案類型：</span><span class="sxs-lookup"><span data-stu-id="be7b5-132">You can specify the following types of supported installation files:</span></span>

   -   <span data-ttu-id="be7b5-133">Windows Installer 檔案（**.msi** ）</span><span class="sxs-lookup"><span data-stu-id="be7b5-133">Windows Installer files(**.msi**</span></span>

   -   <span data-ttu-id="be7b5-134">.cab 檔案</span><span class="sxs-lookup"><span data-stu-id="be7b5-134">.cab files</span></span>

   -   <span data-ttu-id="be7b5-135">副檔名為 .zip 的壓縮檔案</span><span class="sxs-lookup"><span data-stu-id="be7b5-135">Compressed files with a .zip file name extension</span></span>

   -   <span data-ttu-id="be7b5-136">實際的應用程式檔案</span><span class="sxs-lookup"><span data-stu-id="be7b5-136">The actual application files</span></span>

   <span data-ttu-id="be7b5-137">下列檔案類型不受支援： **.msp**與 .exe 檔案 <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="be7b5-137">The following file types are not supported: **.msp** and<strong>.exe</strong> files.</span></span> <span data-ttu-id="be7b5-138">如果您指定 **.exe**檔案，您必須手動解壓縮安裝檔案。</span><span class="sxs-lookup"><span data-stu-id="be7b5-138">If you specify an **.exe** file you must extract the installation files manually.</span></span>



~~~
If the Package Accelerator requires an application be installed prior to applying the Package Accelerator and you have installed the application, on the **Local Installation** page, select the check box **I have installed all applications**, and then click **Next**.
~~~

6. <span data-ttu-id="be7b5-139">在 [**套件名稱**] 頁面上，指定將與套件建立關聯的名稱。</span><span class="sxs-lookup"><span data-stu-id="be7b5-139">On the **Package Name** page, specify a name that will be associated with the package.</span></span> <span data-ttu-id="be7b5-140">指定的名稱會識別應用程式 V 管理主控台中的套件。</span><span class="sxs-lookup"><span data-stu-id="be7b5-140">The name specified identifies the package in the App-V Management Console.</span></span> <span data-ttu-id="be7b5-141">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="be7b5-141">Click **Next**.</span></span>

7. <span data-ttu-id="be7b5-142">在 [**建立套件**] 頁面上，提供將與套件相關聯的批註。</span><span class="sxs-lookup"><span data-stu-id="be7b5-142">On the **Create Package** page, provide comments that will be associated with the package.</span></span> <span data-ttu-id="be7b5-143">批註應該包含您要建立之套件的識別資訊。</span><span class="sxs-lookup"><span data-stu-id="be7b5-143">The comments should contain identifying information about the package you are creating.</span></span> <span data-ttu-id="be7b5-144">若要確認建立套件的位置，請查看 [**儲存位置**] 中顯示的資訊。</span><span class="sxs-lookup"><span data-stu-id="be7b5-144">To confirm the location where the package is created, review the information displayed in **Save Location**.</span></span> <span data-ttu-id="be7b5-145">若要壓縮套件，請選取 [**壓縮套件**]。</span><span class="sxs-lookup"><span data-stu-id="be7b5-145">To compress the package, select **Compress Package**.</span></span> <span data-ttu-id="be7b5-146">如果套件將在網路上流動，或者套件大小超過 4 GB，請選取 [**壓縮套件**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="be7b5-146">Select the **Compress Package** check box if the package will be streamed across the network, or when the package size exceeds 4 GB.</span></span>

   <span data-ttu-id="be7b5-147">若要建立套件，請按一下 [**建立**]。</span><span class="sxs-lookup"><span data-stu-id="be7b5-147">To create the package, click **Create**.</span></span> <span data-ttu-id="be7b5-148">建立套件之後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="be7b5-148">After the package has been created, click **Next**.</span></span>

8. <span data-ttu-id="be7b5-149">在 [**設定軟體**] 頁面上，若要啟用排序器來設定套件中包含的應用程式，請選取 [**設定軟體**]。</span><span class="sxs-lookup"><span data-stu-id="be7b5-149">On the **Configure Software** page, to enable the Sequencer to configure the applications contained in the package, select **Configure Software**.</span></span> <span data-ttu-id="be7b5-150">此步驟適用于設定任何必須完成以在目的電腦上執行應用程式的相關工作，例如設定任何相關聯的授權協定。</span><span class="sxs-lookup"><span data-stu-id="be7b5-150">This step is useful for configuring any associated tasks that must be completed to run the application on target computers, such as configuring any associated license agreements.</span></span>

   <span data-ttu-id="be7b5-151">如果您選取 [**設定軟體**]，則會由 Sequencer 來設定下列專案，做為此步驟的一部分：</span><span class="sxs-lookup"><span data-stu-id="be7b5-151">If you select **Configure Software**, the following items are configured by the Sequencer as part of this step:</span></span>

   -   <span data-ttu-id="be7b5-152">**載入套件**。</span><span class="sxs-lookup"><span data-stu-id="be7b5-152">**Load Package**.</span></span> <span data-ttu-id="be7b5-153">Sequencer 會載入與套件相關聯的檔案。</span><span class="sxs-lookup"><span data-stu-id="be7b5-153">The Sequencer loads the files associated with the package.</span></span> <span data-ttu-id="be7b5-154">解碼套件的時間可能需要數秒到數小時。</span><span class="sxs-lookup"><span data-stu-id="be7b5-154">It can take several seconds to up to an hour to decode the package.</span></span>

   -   <span data-ttu-id="be7b5-155">**執行每個程式**。</span><span class="sxs-lookup"><span data-stu-id="be7b5-155">**Run Each Program**.</span></span> <span data-ttu-id="be7b5-156">您也可以選擇執行套件中包含的程式。</span><span class="sxs-lookup"><span data-stu-id="be7b5-156">Optionally run the programs contained in the package.</span></span> <span data-ttu-id="be7b5-157">此步驟對於完成在您部署並在目的電腦上執行套件之前，執行應用程式所需的任何相關授權或配置工作很有説明。</span><span class="sxs-lookup"><span data-stu-id="be7b5-157">This step is helpful for completing any associated license or configuration tasks that are required to run the application before you deploy and run the package on target computers.</span></span> <span data-ttu-id="be7b5-158">若要一次執行所有程式，請選取至少一個程式，然後按一下 [**全部執行**]。</span><span class="sxs-lookup"><span data-stu-id="be7b5-158">To run all the programs at one time, select at least one program, and then click **Run All**.</span></span> <span data-ttu-id="be7b5-159">若要執行特定程式，請選取您要執行的程式或程式，然後按一下 [**執行選取**的專案]。</span><span class="sxs-lookup"><span data-stu-id="be7b5-159">To run specific programs, select the program or programs you want to run, and then click **Run Selected**.</span></span> <span data-ttu-id="be7b5-160">完成所需的設定任務，然後關閉應用程式。</span><span class="sxs-lookup"><span data-stu-id="be7b5-160">Complete the required configuration tasks, and then close the applications.</span></span> <span data-ttu-id="be7b5-161">所有程式都可能需要幾分鐘的時間才能執行。</span><span class="sxs-lookup"><span data-stu-id="be7b5-161">It can take several minutes for all programs to run.</span></span> <span data-ttu-id="be7b5-162">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="be7b5-162">Click **Next**.</span></span>

   -   <span data-ttu-id="be7b5-163">[**儲存套件**]。</span><span class="sxs-lookup"><span data-stu-id="be7b5-163">**Save Package**.</span></span> <span data-ttu-id="be7b5-164">Sequencer 會儲存套件。</span><span class="sxs-lookup"><span data-stu-id="be7b5-164">The Sequencer saves the package.</span></span>

   -   <span data-ttu-id="be7b5-165">**主要功能區塊**。</span><span class="sxs-lookup"><span data-stu-id="be7b5-165">**Primary Feature Block**.</span></span> <span data-ttu-id="be7b5-166">排序器透過重建主要功能區塊來優化資料流程套件。</span><span class="sxs-lookup"><span data-stu-id="be7b5-166">The Sequencer optimizes the package for streaming by rebuilding the primary feature block.</span></span>

   <span data-ttu-id="be7b5-167">如果您不想要設定應用程式，請按一下 [**略過此步驟**]，然後移至此程式的步驟9，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="be7b5-167">If you do not want to configure the applications, click **Skip this step**, and to go to step 9 of this procedure, and then click **Next**.</span></span>

9. <span data-ttu-id="be7b5-168">在 [**完成**] 頁面上，檢查 [**虛擬應用程式套件報告**] 窗格中顯示的資訊後，按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="be7b5-168">On the **Completion** page, after you have reviewed the information displayed in the **Virtual Application Package Report** pane, click **Close**.</span></span>

   <span data-ttu-id="be7b5-169">套件現在可在 Sequencer 中取得。</span><span class="sxs-lookup"><span data-stu-id="be7b5-169">The package is now available in the Sequencer.</span></span> <span data-ttu-id="be7b5-170">若要編輯套件屬性，請按一下 **[編輯 \ [套件名稱 \]]**。</span><span class="sxs-lookup"><span data-stu-id="be7b5-170">To edit the package properties, click **Edit \[Package Name\]**.</span></span> <span data-ttu-id="be7b5-171">如需有關修改套件的詳細資訊，請參閱[如何修改現有的虛擬應用程式套件（app-v 4.6 SP1）](how-to-modify-an-existing-virtual-application-package--app-v-46-sp1-.md)。</span><span class="sxs-lookup"><span data-stu-id="be7b5-171">For more information about modifying a package, see [How to Modify an Existing Virtual Application Package (App-V 4.6 SP1)](how-to-modify-an-existing-virtual-application-package--app-v-46-sp1-.md).</span></span>

## <span data-ttu-id="be7b5-172">相關主題</span><span class="sxs-lookup"><span data-stu-id="be7b5-172">Related topics</span></span>


[<span data-ttu-id="be7b5-173">設定 Application Virtualization Sequencer (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="be7b5-173">Configuring the Application Virtualization Sequencer (App-V 4.6 SP1)</span></span>](configuring-the-application-virtualization-sequencer--app-v-46-sp1-.md)

[<span data-ttu-id="be7b5-174">如何建立 App-V 封裝加速器 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="be7b5-174">How to Create App-V Package Accelerators (App-V 4.6 SP1)</span></span>](how-to-create-app-v-package-accelerators--app-v-46-sp1-.md)









