---
title: 如何建立封裝加速器
description: 如何建立封裝加速器
author: dansimp
ms.assetid: b61f3581-7933-443e-b872-a96bed9ff8d7
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6893f2e9bb9db473d285026015c3399fb0074015
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800550"
---
# <span data-ttu-id="32a13-103">如何建立封裝加速器</span><span class="sxs-lookup"><span data-stu-id="32a13-103">How to Create a Package Accelerator</span></span>


<span data-ttu-id="32a13-104">App-v 5.1 套件加速器會自動產生新的虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="32a13-104">App-V 5.1 package accelerators automatically generate new virtual application packages.</span></span>

**<span data-ttu-id="32a13-105">注意</span><span class="sxs-lookup"><span data-stu-id="32a13-105">Note</span></span>**  
<span data-ttu-id="32a13-106">您可以使用 PowerShell 建立套件加速器。</span><span class="sxs-lookup"><span data-stu-id="32a13-106">You can use PowerShell to create a package accelerator.</span></span> <span data-ttu-id="32a13-107">如需詳細資訊，請參閱[如何使用 PowerShell 建立套件加速器](how-to-create-a-package-accelerator-by-using-powershell51.md)。</span><span class="sxs-lookup"><span data-stu-id="32a13-107">For more information see [How to Create a Package Accelerator by Using PowerShell](how-to-create-a-package-accelerator-by-using-powershell51.md).</span></span>



<span data-ttu-id="32a13-108">使用下列程式建立套件加速器。</span><span class="sxs-lookup"><span data-stu-id="32a13-108">Use the following procedure to create a package accelerator.</span></span>

**<span data-ttu-id="32a13-109">重要</span><span class="sxs-lookup"><span data-stu-id="32a13-109">Important</span></span>**  
<span data-ttu-id="32a13-110">套件加速器可以包含密碼和使用者專用的資訊。</span><span class="sxs-lookup"><span data-stu-id="32a13-110">Package Accelerators can contain password and user-specific information.</span></span> <span data-ttu-id="32a13-111">因此，您必須將套件加速器與關聯安裝媒體儲存在安全的位置，而且您應該在建立套件加速器之後進行數位簽章，以便在套用 app-v 5.1 套件加速器時驗證發行者。</span><span class="sxs-lookup"><span data-stu-id="32a13-111">Therefore you must save Package Accelerators and the associated installation media in a secure location, and you should digitally sign the Package Accelerator after you create it so that the publisher can be verified when the App-V 5.1 Package Accelerator is applied.</span></span>



**<span data-ttu-id="32a13-112">重要</span><span class="sxs-lookup"><span data-stu-id="32a13-112">Important</span></span>**  
<span data-ttu-id="32a13-113">開始進行下列程式前，您應該執行下列步驟：</span><span class="sxs-lookup"><span data-stu-id="32a13-113">Before you begin the following procedure, you should perform the following:</span></span>

-   <span data-ttu-id="32a13-114">複製您將用來在執行排序器的電腦上將用來建立套件加速器的虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="32a13-114">Copy the virtual application package that you will use to create the package accelerator locally to the computer running the sequencer.</span></span>

-   <span data-ttu-id="32a13-115">將與虛擬應用程式套件相關的所有必要安裝檔案複製到執行排序器的電腦上。</span><span class="sxs-lookup"><span data-stu-id="32a13-115">Copy all required installation files associated with the virtual application package to the computer running the sequencer.</span></span>



**<span data-ttu-id="32a13-116">建立套件加速器</span><span class="sxs-lookup"><span data-stu-id="32a13-116">To create a package accelerator</span></span>**

1.  **<span data-ttu-id="32a13-117">重要</span><span class="sxs-lookup"><span data-stu-id="32a13-117">Important</span></span>**  
    <span data-ttu-id="32a13-118">App-v 5.1 Sequencer 不會將任何您用來建立套件加速器之軟體應用程式的授權權利授與。</span><span class="sxs-lookup"><span data-stu-id="32a13-118">The App-V 5.1 Sequencer does not grant any license rights to the software application you are using to create the Package Accelerator.</span></span> <span data-ttu-id="32a13-119">您必須遵守所使用之應用程式的所有使用者授權合約。</span><span class="sxs-lookup"><span data-stu-id="32a13-119">You must abide by all end user license terms for the application you are using.</span></span> <span data-ttu-id="32a13-120">您有責任確認軟體應用程式的授權條款可讓您使用 App-v 5.1 排序器來建立套件加速器。</span><span class="sxs-lookup"><span data-stu-id="32a13-120">It is your responsibility to make sure the software application’s license terms allow you to create a Package Accelerator using App-V 5.1 Sequencer.</span></span>



~~~
To start the App-V 5.1 sequencer, on the computer that is running the sequencer, click **Start** / **All Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.
~~~

2. <span data-ttu-id="32a13-121">若要啟動 app-v 5.1 [**建立套件加速器**] 嚮導，請在 app-v 5.1 排序器主控台中，按一下 [**工具**  /  **建立加速器**]。</span><span class="sxs-lookup"><span data-stu-id="32a13-121">To start the App-V 5.1 **Create Package Accelerator** wizard, in the App-V 5.1 sequencer console, click **Tools** / **Create Accelerator**.</span></span>

3. <span data-ttu-id="32a13-122">在 [**選取套件**] 頁面上，若要指定要用來建立套件加速器的現有虛擬應用程式套件，請按一下 **[流覽]**，然後找出現有的虛擬應用程式套件（appv 檔案）。</span><span class="sxs-lookup"><span data-stu-id="32a13-122">On the **Select Package** page, to specify an existing virtual application package to use to create the Package Accelerator, click **Browse**, and locate the existing virtual application package (.appv file).</span></span>

   **<span data-ttu-id="32a13-123">提示</span><span class="sxs-lookup"><span data-stu-id="32a13-123">Tip</span></span>**  
   <span data-ttu-id="32a13-124">將與您計畫要在本機使用的虛擬應用程式套件相關聯的檔案複製到執行排序器的電腦上。</span><span class="sxs-lookup"><span data-stu-id="32a13-124">Copy the files associated with the virtual application package you plan to use locally to the computer running the Sequencer.</span></span>



~~~
Click **Next**.
~~~

4. <span data-ttu-id="32a13-125">在 [**安裝**檔案] 頁面上，若要指定包含您用來建立原始虛擬應用程式套件之安裝檔案的資料夾，請按一下 **[流覽]**，然後選取包含安裝檔的目錄。</span><span class="sxs-lookup"><span data-stu-id="32a13-125">On the **Installation Files** page, to specify the folder that contains the installation files that you used to create the original virtual application package, click **Browse**, and then select the directory that contains the installation files.</span></span>

   **<span data-ttu-id="32a13-126">提示</span><span class="sxs-lookup"><span data-stu-id="32a13-126">Tip</span></span>**  
   <span data-ttu-id="32a13-127">在執行排序器的電腦上，複製包含所需安裝檔案的資料夾。</span><span class="sxs-lookup"><span data-stu-id="32a13-127">Copy the folder that contains the required installation files to the computer running the Sequencer.</span></span>



5. <span data-ttu-id="32a13-128">如果應用程式已安裝在執行排序器的電腦上，若要指定安裝檔案，請選取 [**本機系統上已安裝的**檔案]。</span><span class="sxs-lookup"><span data-stu-id="32a13-128">If the application is already installed on the computer running the sequencer, to specify the installation file, select **Files installed on local system**.</span></span> <span data-ttu-id="32a13-129">若要使用此選項，應用程式必須已安裝在預設安裝位置。</span><span class="sxs-lookup"><span data-stu-id="32a13-129">To use this option, the application must already be installed in the default installation location.</span></span>

6. <span data-ttu-id="32a13-130">在 [**收集資訊**] 頁面上，查看在此嚮導的 [**安裝**檔案] 頁面上指定的位置中找不到的檔案。</span><span class="sxs-lookup"><span data-stu-id="32a13-130">On the **Gathering Information** page, review the files that were not found in the location specified on the **Installation Files** page of this wizard.</span></span> <span data-ttu-id="32a13-131">如果不需要顯示的檔案，請選取 [**移除這些**檔案]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="32a13-131">If the files displayed are not required, select **Remove these files**, and then click **Next**.</span></span> <span data-ttu-id="32a13-132">如果檔案是必要的，請按一下 [**上一步**]，然後將所需的檔案複製到 [**安裝**檔案] 頁面上指定的目錄。</span><span class="sxs-lookup"><span data-stu-id="32a13-132">If the files are required, click **Previous** and copy the required files to the directory specified on the **Installation Files** page.</span></span>

   **<span data-ttu-id="32a13-133">注意</span><span class="sxs-lookup"><span data-stu-id="32a13-133">Note</span></span>**  
   <span data-ttu-id="32a13-134">您必須移除 unrequired 檔案，或按一下 [**上一**步]，然後找出所需的檔案，以移至此嚮導的下一個頁面。</span><span class="sxs-lookup"><span data-stu-id="32a13-134">You must either remove the unrequired files, or click **Previous** and locate the required files to advance to the next page of this wizard.</span></span>



7. <span data-ttu-id="32a13-135">在 [**選取**檔案] 頁面上，仔細查看已偵測到的檔案，並清除任何應從套件加速器移除的檔案。</span><span class="sxs-lookup"><span data-stu-id="32a13-135">On the **Select Files** page, carefully review the files that were detected, and clear any file that should be removed from the package accelerator.</span></span> <span data-ttu-id="32a13-136">只選取應用程式成功執行所需的檔案，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="32a13-136">Select only files that are required for the application to run successfully, and then click **Next**.</span></span>

8. <span data-ttu-id="32a13-137">在 [**驗證應用程式**] 頁面上，確認已顯示組建套件所需的所有安裝檔案。</span><span class="sxs-lookup"><span data-stu-id="32a13-137">On the **Verify Applications** page, confirm that all installation files that are required to build the package are displayed.</span></span> <span data-ttu-id="32a13-138">當套件加速器用來建立新的套件時，在 [**應用程式**] 窗格中顯示的所有安裝檔案都是建立套件所需的專案。</span><span class="sxs-lookup"><span data-stu-id="32a13-138">When the Package Accelerator is used to create a new package, all installation files displayed in the **Applications** pane are required to create the package.</span></span>

   <span data-ttu-id="32a13-139">如有需要，若要新增其他安裝程式檔案，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="32a13-139">If necessary, to add additional Installer files, click **Add**.</span></span> <span data-ttu-id="32a13-140">若要移除不必要的安裝檔，請選取安裝程式檔案，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="32a13-140">To remove unnecessary installation files, select the Installer file, and then click **Delete**.</span></span> <span data-ttu-id="32a13-141">若要編輯與安裝程式相關聯的屬性，請按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="32a13-141">To edit the properties associated with an installer, click **Edit**.</span></span> <span data-ttu-id="32a13-142">當您使用套件加速器建立新的虛擬應用程式套件時，系統會要求在此步驟中指定的安裝檔案。</span><span class="sxs-lookup"><span data-stu-id="32a13-142">The installation files specified in this step will be required when the Package Accelerator is used to create a new virtual application package.</span></span> <span data-ttu-id="32a13-143">確認顯示的資訊後，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="32a13-143">After you have confirmed the information displayed, click **Next**.</span></span>

9. <span data-ttu-id="32a13-144">在 [**選取指導**者] 頁面上，若要指定包含套件加速器之相關資訊的檔案，請按一下 **[流覽]**。</span><span class="sxs-lookup"><span data-stu-id="32a13-144">On the **Select Guidance** page, to specify a file that contains information about how the Package Accelerator, click **Browse**.</span></span> <span data-ttu-id="32a13-145">例如，此檔案可以包含執行排序器的電腦配置、目的電腦的應用程式必備資訊，以及一般筆記的相關資訊。</span><span class="sxs-lookup"><span data-stu-id="32a13-145">For example, this file can contain information about how the computer running the Sequencer should be configured, application prerequisite information for target computers, and general notes.</span></span> <span data-ttu-id="32a13-146">您應該提供套件加速器所需的所有必要資訊，才能成功套用。</span><span class="sxs-lookup"><span data-stu-id="32a13-146">You should provide all required information for the Package Accelerator to be successfully applied.</span></span> <span data-ttu-id="32a13-147">您所選取的檔案必須是 rtf （.rtf）或文字檔（.txt）格式。</span><span class="sxs-lookup"><span data-stu-id="32a13-147">The file you select must be in rich text (.rtf) or text file (.txt) format.</span></span> <span data-ttu-id="32a13-148">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="32a13-148">Click **Next**.</span></span>

10. <span data-ttu-id="32a13-149">在 [**建立套件加速器**] 頁面上，若要指定要儲存套件加速器的位置，請按一下 **[流覽]** ，然後選取目錄。</span><span class="sxs-lookup"><span data-stu-id="32a13-149">On the **Create Package Accelerator** page, to specify where to save the Package Accelerator, click **Browse** and select the directory.</span></span>

11. <span data-ttu-id="32a13-150">在**完成**頁面上，若要關閉 [**建立套件快速鍵**嚮導]，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="32a13-150">On the **Completion** page, to close the **Create Package Accelerator** wizard, click **Close**.</span></span>

   **<span data-ttu-id="32a13-151">重要</span><span class="sxs-lookup"><span data-stu-id="32a13-151">Important</span></span>**  
   <span data-ttu-id="32a13-152">為了協助確保套件加速器盡可能安全，且在套用套件加速器時可驗證發行者，您應該必須以數位方式簽署套件加速器。</span><span class="sxs-lookup"><span data-stu-id="32a13-152">To help ensure that the package accelerator is as secure as possible, and so that the publisher can be verified when the package accelerator is applied, you should always digitally sign the package accelerator.</span></span>



~~~
**Got a suggestion for App-V**? Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization). **Got an App-V issue?** Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).
~~~

## <span data-ttu-id="32a13-153">相關主題</span><span class="sxs-lookup"><span data-stu-id="32a13-153">Related topics</span></span>


[<span data-ttu-id="32a13-154">App-V 5.1 作業</span><span class="sxs-lookup"><span data-stu-id="32a13-154">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

[<span data-ttu-id="32a13-155">如何使用 App-V 封裝加速器建立虛擬應用程式套件</span><span class="sxs-lookup"><span data-stu-id="32a13-155">How to Create a Virtual Application Package Using an App-V Package Accelerator</span></span>](how-to-create-a-virtual-application-package-using-an-app-v-package-accelerator51.md)









