---
title: 如何建立 App-V 封裝加速器 (App-V 4.6 SP1)
description: 如何建立 App-V 封裝加速器 (App-V 4.6 SP1)
author: dansimp
ms.assetid: 585e692e-cebb-48ac-93ab-b2e7eb7ae7ad
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: eb806ccf04fcd5ae7db87c5de21e85217739fcbc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801497"
---
# <span data-ttu-id="7c30f-103">如何建立 App-V 封裝加速器 (App-V 4.6 SP1)</span><span class="sxs-lookup"><span data-stu-id="7c30f-103">How to Create App-V Package Accelerators (App-V 4.6 SP1)</span></span>


<span data-ttu-id="7c30f-104">您可以使用 App-v 包加速器來自動產生新的虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="7c30f-104">You can use App-V Package Accelerators to automatically generate a new virtual application package.</span></span> <span data-ttu-id="7c30f-105">成功建立套件加速器之後，您可以重複使用並共用套件加速器。</span><span class="sxs-lookup"><span data-stu-id="7c30f-105">After you have successfully created a Package Accelerator, you can reuse and share the Package Accelerator.</span></span> <span data-ttu-id="7c30f-106">如需有關套件加速器的詳細資訊，請參閱[關於 App v 封裝快速鍵（app-v 4.6 SP1）](about-app-v-package-accelerators--app-v-46-sp1-.md)。</span><span class="sxs-lookup"><span data-stu-id="7c30f-106">For more information about Package Accelerators, see [About App-V Package Accelerators (App-V 4.6 SP1)](about-app-v-package-accelerators--app-v-46-sp1-.md).</span></span> <span data-ttu-id="7c30f-107">建立 App-v 套件快速鍵是一個高級任務。</span><span class="sxs-lookup"><span data-stu-id="7c30f-107">Creating App-V Package Accelerators is an advanced task.</span></span> <span data-ttu-id="7c30f-108">套件加速器可以包含密碼和使用者專用的資訊。</span><span class="sxs-lookup"><span data-stu-id="7c30f-108">Package Accelerators can contain password and user-specific information.</span></span> <span data-ttu-id="7c30f-109">因此，您必須將套件加速器及相關安裝媒體儲存在安全的位置，而且您應該在建立套件加速器之後進行數位簽章，以便在套用 V 套件加速器時驗證發行商的發行程式。</span><span class="sxs-lookup"><span data-stu-id="7c30f-109">Therefore you must save Package Accelerators and the associated installation media in a secure location, and you should digitally sign the Package Accelerator after you create it so that the publisher can be verified when the App-V Package Accelerator is applied.</span></span>

<span data-ttu-id="7c30f-110">在某些情況下，若要建立套件加速器，您可能必須在執行排序器的電腦上本機安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="7c30f-110">In some situations, to create the Package Accelerator, you might have to install the application locally on the computer running the Sequencer.</span></span> <span data-ttu-id="7c30f-111">首先，嘗試使用安裝媒體建立套件加速器，如果有多個需要的遺失檔案，請在執行排序器的電腦上本機安裝應用程式，然後建立套件加速器。</span><span class="sxs-lookup"><span data-stu-id="7c30f-111">First try to create the Package Accelerator by using the installation media, and if there are a number of missing files that are required, install the application locally to the computer running the Sequencer, and then create the Package Accelerator.</span></span>

**<span data-ttu-id="7c30f-112">重要</span><span class="sxs-lookup"><span data-stu-id="7c30f-112">Important</span></span>**  
<span data-ttu-id="7c30f-113">開始進行下列程式前，您應該執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="7c30f-113">Before you begin the following procedure, you should do the following:</span></span>

-   <span data-ttu-id="7c30f-114">複製您必須用來在執行排序器的電腦本機建立套件加速器的虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="7c30f-114">Copy the virtual application package that you must use to create the Package Accelerator locally to the computer running the Sequencer.</span></span>

-   <span data-ttu-id="7c30f-115">將與虛擬應用程式套件相關的所有必要安裝檔案複製到執行排序器的電腦上。</span><span class="sxs-lookup"><span data-stu-id="7c30f-115">Copy all required installation files associated with the virtual application package to the computer running the Sequencer.</span></span>



**<span data-ttu-id="7c30f-116">重要</span><span class="sxs-lookup"><span data-stu-id="7c30f-116">Important</span></span>**  
<span data-ttu-id="7c30f-117">免責聲明： Microsoft Application Virtualization Sequencer 不會提供您用來建立套件加速器之軟體應用程式的授權權利。</span><span class="sxs-lookup"><span data-stu-id="7c30f-117">Disclaimer: The Microsoft Application Virtualization Sequencer does not give you any license rights to the software application you are using to create a Package Accelerator.</span></span> <span data-ttu-id="7c30f-118">您必須遵守此類應用程式的所有使用者授權合約。</span><span class="sxs-lookup"><span data-stu-id="7c30f-118">You must abide by all end user license terms for such application.</span></span> <span data-ttu-id="7c30f-119">您有責任確認軟體應用程式的授權條款可讓您使用 Application Virtualization 排序器建立套件加速器。</span><span class="sxs-lookup"><span data-stu-id="7c30f-119">It is your responsibility to make sure the software application’s license terms allow you to create a Package Accelerator using Application Virtualization Sequencer.</span></span>



**<span data-ttu-id="7c30f-120">若要建立 App-v 套件加速器</span><span class="sxs-lookup"><span data-stu-id="7c30f-120">To create an App-V Package Accelerator</span></span>**

1.  <span data-ttu-id="7c30f-121">若要啟動 app-v 排序器，請在執行 app-v 排序器的電腦上，按一下 [**開始**  /  **所有程式**]  /  **microsoft application virtualization**  /  **microsoft application virtualization 排序**器。</span><span class="sxs-lookup"><span data-stu-id="7c30f-121">To start the App-V Sequencer, on the computer that is running the App-V Sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="7c30f-122">若要啟動 app-v [**建立套件加速器**] 嚮導，請在 app-v 排序器中，按一下 [**工具**]  /  **建立套件加速器**。</span><span class="sxs-lookup"><span data-stu-id="7c30f-122">To start the App-V **Create Package Accelerator** wizard, in the App-V Sequencer, click **Tools** / **Create Package Accelerator**.</span></span>

3.  <span data-ttu-id="7c30f-123">在 [**選取套件**] 頁面上，若要指定要用來建立套件加速器的現有虛擬應用程式套件，請按一下 **[流覽]**，然後找出現有的虛擬應用程式套件（sprj 檔案）。</span><span class="sxs-lookup"><span data-stu-id="7c30f-123">On the **Select Package** page, to specify an existing virtual application package to use to create the Package Accelerator, click **Browse**, and locate the existing virtual application package (.sprj file).</span></span>

    **<span data-ttu-id="7c30f-124">提示</span><span class="sxs-lookup"><span data-stu-id="7c30f-124">Tip</span></span>**  
    <span data-ttu-id="7c30f-125">將與您計畫要在本機使用的虛擬應用程式套件相關聯的檔案複製到執行排序器的電腦上。</span><span class="sxs-lookup"><span data-stu-id="7c30f-125">Copy the files associated with the virtual application package you plan to use locally to the computer running the Sequencer.</span></span>



~~~
Click **Next**.
~~~

4. <span data-ttu-id="7c30f-126">在 [**安裝**檔案] 頁面上，若要指定包含您用來建立原始虛擬應用程式套件之安裝檔案的資料夾，請按一下 **[流覽]**，然後選取包含安裝檔的目錄。</span><span class="sxs-lookup"><span data-stu-id="7c30f-126">On the **Installation Files** page, to specify the folder that contains the installation files that you used to create the original virtual application package, click **Browse**, and then select the directory that contains the installation files.</span></span>

   **<span data-ttu-id="7c30f-127">提示</span><span class="sxs-lookup"><span data-stu-id="7c30f-127">Tip</span></span>**  
   <span data-ttu-id="7c30f-128">在執行排序器的電腦上，複製包含所需安裝檔案的資料夾。</span><span class="sxs-lookup"><span data-stu-id="7c30f-128">Copy the folder that contains the required installation files to the computer running the Sequencer.</span></span>



~~~
If the application is already installed on the computer running the Sequencer, to specify the installation file, select **Files installed on local system**. To use this option, the application must already be installed in the default installation location.
~~~

5. <span data-ttu-id="7c30f-129">在 [**收集資訊**] 頁面上，查看在此嚮導的 [**安裝**檔案] 頁面上指定的位置中找不到的檔案。</span><span class="sxs-lookup"><span data-stu-id="7c30f-129">On the **Gathering Information** page, review the files that were not found in the location specified on the **Installation Files** page of this wizard.</span></span> <span data-ttu-id="7c30f-130">如果不需要顯示的檔案，請選取 [**移除這些**檔案]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="7c30f-130">If the files displayed are not required, select **Remove these files**, and then click **Next**.</span></span> <span data-ttu-id="7c30f-131">如果檔案是必要的，請按一下 [**上一步**]，然後將所需的檔案複製到 [**安裝**檔案] 頁面上指定的目錄。</span><span class="sxs-lookup"><span data-stu-id="7c30f-131">If the files are required, click **Previous** and copy the required files to the directory specified on the **Installation Files** page.</span></span>

   **<span data-ttu-id="7c30f-132">注意</span><span class="sxs-lookup"><span data-stu-id="7c30f-132">Note</span></span>**  
   <span data-ttu-id="7c30f-133">您必須移除 unrequired 檔案，或按一下 [**上一**步]，然後找出所需的檔案，以移至此嚮導的下一個頁面。</span><span class="sxs-lookup"><span data-stu-id="7c30f-133">You must either remove the unrequired files, or click **Previous** and locate the required files to advance to the next page of this wizard.</span></span>



6. <span data-ttu-id="7c30f-134">在 [**選取**檔案] 頁面上，仔細查看已偵測到的檔案，並清除任何應從套件加速器移除的檔案。</span><span class="sxs-lookup"><span data-stu-id="7c30f-134">On the **Select Files** page, carefully review the files that were detected, and clear any file that should be removed from the Package Accelerator.</span></span> <span data-ttu-id="7c30f-135">只選取應用程式成功執行所需的檔案，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="7c30f-135">Select only files that are required for the application to run successfully, and then click **Next**.</span></span>

7. <span data-ttu-id="7c30f-136">在 [**驗證應用程式**] 頁面上，確認已顯示組建套件所需的所有安裝檔案。</span><span class="sxs-lookup"><span data-stu-id="7c30f-136">On the **Verify Applications** page, confirm that all installation files that are required to build the package are displayed.</span></span> <span data-ttu-id="7c30f-137">當套件加速器用來建立新的套件時，在 [**應用程式**] 窗格中顯示的所有安裝檔案都是建立套件所需的專案。</span><span class="sxs-lookup"><span data-stu-id="7c30f-137">When the Package Accelerator is used to create a new package, all installation files displayed in the **Applications** pane are required to create the package.</span></span>

   <span data-ttu-id="7c30f-138">如有需要，若要新增其他安裝程式檔案，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="7c30f-138">If necessary, to add additional Installer files, click **Add**.</span></span> <span data-ttu-id="7c30f-139">若要移除不必要的安裝檔，請選取安裝程式檔案，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="7c30f-139">To remove unnecessary installation files, select the Installer file, and then click **Delete**.</span></span> <span data-ttu-id="7c30f-140">若要編輯與安裝程式相關聯的屬性，請按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="7c30f-140">To edit the properties associated with an installer, click **Edit**.</span></span> <span data-ttu-id="7c30f-141">當您使用套件加速器建立新的虛擬應用程式套件時，系統會要求在此步驟中指定的安裝檔案。</span><span class="sxs-lookup"><span data-stu-id="7c30f-141">The installation files specified in this step will be required when the Package Accelerator is used to create a new virtual application package.</span></span> <span data-ttu-id="7c30f-142">確認顯示的資訊後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="7c30f-142">After you have confirmed the information displayed, click **Next**.</span></span>

8. <span data-ttu-id="7c30f-143">在 [**選取指導**者] 頁面上，若要指定包含套件加速器之相關資訊的檔案，請按一下 **[流覽]**。</span><span class="sxs-lookup"><span data-stu-id="7c30f-143">On the **Select Guidance** page, to specify a file that contains information about how the Package Accelerator, click **Browse**.</span></span> <span data-ttu-id="7c30f-144">例如，此檔案可以包含執行排序器的電腦配置、目的電腦的應用程式必備資訊，以及一般筆記的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="7c30f-144">For example, this file can contain information about how the computer running the Sequencer should be configured, application prerequisite information for target computers, and general notes.</span></span> <span data-ttu-id="7c30f-145">您應該提供套件加速器所需的所有必要資訊，才能成功套用。</span><span class="sxs-lookup"><span data-stu-id="7c30f-145">You should provide all required information for the Package Accelerator to be successfully applied.</span></span> <span data-ttu-id="7c30f-146">您所選取的檔案必須是 rtf （.rtf）或文字檔（.txt）格式。</span><span class="sxs-lookup"><span data-stu-id="7c30f-146">The file you select must be in rich text (.rtf) or text file (.txt) format.</span></span> <span data-ttu-id="7c30f-147">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="7c30f-147">Click **Next**.</span></span>

9. <span data-ttu-id="7c30f-148">在 [**建立套件加速器**] 頁面上，若要指定要儲存套件加速器的位置，請按一下 **[流覽]** ，然後選取目錄。</span><span class="sxs-lookup"><span data-stu-id="7c30f-148">On the **Create Package Accelerator** page, to specify where to save the Package Accelerator, click **Browse** and select the directory.</span></span>

10. <span data-ttu-id="7c30f-149">在**完成**頁面上，若要關閉 [**建立套件快速鍵**嚮導]，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="7c30f-149">On the **Completion** page, to close the **Create Package Accelerator** wizard, click **Close**.</span></span>

   **<span data-ttu-id="7c30f-150">重要</span><span class="sxs-lookup"><span data-stu-id="7c30f-150">Important</span></span>**  
   <span data-ttu-id="7c30f-151">為了協助確保套件加速器盡可能安全，且在套用套件加速器時可驗證發行者，您應該必須以數位方式簽署套件加速器。</span><span class="sxs-lookup"><span data-stu-id="7c30f-151">To help ensure that the Package Accelerator is as secure as possible, and so that the publisher can be verified when the Package Accelerator is applied, you should always digitally sign the Package Accelerator.</span></span>



## <span data-ttu-id="7c30f-152">相關主題</span><span class="sxs-lookup"><span data-stu-id="7c30f-152">Related topics</span></span>


<span data-ttu-id="7c30f-153">設定應用程式虛擬化排序器（App-v 4.6 SP1）[如何套用套件加速器以建立虛擬應用程式套件（app-v 4.6 sp1）](how-to-apply-a-package-accelerator-to-create-a-virtual-application-package---app-v-46-sp1-.md)</span><span class="sxs-lookup"><span data-stu-id="7c30f-153">Configuring the Application Virtualization Sequencer (App-V 4.6 SP1) [How to Apply a Package Accelerator to Create a Virtual Application Package (App-V 4.6 SP1)](how-to-apply-a-package-accelerator-to-create-a-virtual-application-package---app-v-46-sp1-.md)</span></span>









