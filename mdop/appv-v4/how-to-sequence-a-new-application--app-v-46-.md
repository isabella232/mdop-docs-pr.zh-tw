---
title: 如何排序新應用程式 (App-V 4.6)
description: 如何排序新應用程式 (App-V 4.6)
author: dansimp
ms.assetid: f2c398c6-9200-4be3-b502-e00386fcd150
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9a36021adf45f0f4c80ab08bcabbf9f18bf6e66b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801121"
---
# <span data-ttu-id="f6659-103">如何排序新應用程式 (App-V 4.6)</span><span class="sxs-lookup"><span data-stu-id="f6659-103">How to Sequence a New Application (App-V 4.6)</span></span>


<span data-ttu-id="f6659-104">使用下列程式，透過應用程式虛擬化（App-v） Sequencer 來建立新的虛擬應用程式。</span><span class="sxs-lookup"><span data-stu-id="f6659-104">Use the following procedure to create a new virtual application by using the Application Virtualization (App-V) Sequencer.</span></span> <span data-ttu-id="f6659-105">您也可以使用 App-v 排序器，來設定哪些檔案和設定適用于所有的使用者，以及使用者可以自訂哪些檔案和配置。</span><span class="sxs-lookup"><span data-stu-id="f6659-105">You can also use the App-V Sequencer to configure which files and configurations are applicable to all users and which files and configurations users can customize.</span></span> <span data-ttu-id="f6659-106">成功排序應用程式後，就可以在 App-v 排序器中使用它。</span><span class="sxs-lookup"><span data-stu-id="f6659-106">After you successfully sequence the application, it is available in the App-V Sequencer.</span></span>

**<span data-ttu-id="f6659-107">重要</span><span class="sxs-lookup"><span data-stu-id="f6659-107">Important</span></span>**  
<span data-ttu-id="f6659-108">在排序期間，如果執行排序器的電腦是執行 Windows Vista 或 Windows 7，且在虛擬環境外啟動重新開機，例如，按一下 [**開始**  /  **關閉**]，系統會在系統提示您關閉禁止 Windows 關閉的程式時，按一下 [**取消**]。</span><span class="sxs-lookup"><span data-stu-id="f6659-108">During sequencing, if the computer running the sequencer is running Windows Vista or Windows 7, and a restart is initiated outside of the virtual environment, for example, by clicking **Start** / **Shut Down**, you must click **Cancel** when prompted to close the program that is preventing Windows from shutting down.</span></span> <span data-ttu-id="f6659-109">如果您按一下 [**強制關閉**]，套件建立將會失敗，電腦將會重新開機。</span><span class="sxs-lookup"><span data-stu-id="f6659-109">If you click **Force shut down**, the package creation will fail, and the computer will restart.</span></span> <span data-ttu-id="f6659-110">當您按一下 [**取消**] 時，sequencer 會在應用程式排序時成功記錄重新開機。</span><span class="sxs-lookup"><span data-stu-id="f6659-110">When you click **Cancel**, the sequencer successfully records the restart while the application is being sequenced.</span></span>



**<span data-ttu-id="f6659-111">為新的應用程式排序</span><span class="sxs-lookup"><span data-stu-id="f6659-111">To sequence a new application</span></span>**

1.  <span data-ttu-id="f6659-112">若要建立 App-v 磁片磁碟機，請將 [磁碟機 Q] 設定為在您為應用程式排序時可以用來儲存檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="f6659-112">To create the App-V drive, configure drive Q as the location that can be used to save files while you are sequencing an application.</span></span> <span data-ttu-id="f6659-113">接著，您必須針對每個您打算在磁碟機 Q 中排序的應用程式建立個別的目錄。您可以在為應用程式排序前建立虛擬應用程式的目的檔案夾，或者您可以在此程式的步驟5中建立。</span><span class="sxs-lookup"><span data-stu-id="f6659-113">You must then create individual directories for each application that you plan to sequence on drive Q. You can create the virtual application targeted folders before you sequence an application, or you can create them in step 5 of this procedure.</span></span>

    **<span data-ttu-id="f6659-114">注意</span><span class="sxs-lookup"><span data-stu-id="f6659-114">Note</span></span>**  
    <span data-ttu-id="f6659-115">您指定的 App-v 磁片磁碟機必須可在目的電腦上存取。</span><span class="sxs-lookup"><span data-stu-id="f6659-115">The App-V drive you specify must be accessible on targeted computers.</span></span> <span data-ttu-id="f6659-116">如果無法存取磁碟機 Q，您可以選擇不同的磁片磁碟機盤符。</span><span class="sxs-lookup"><span data-stu-id="f6659-116">If drive Q is not accessible, you can choose a different drive letter.</span></span>



2.  <span data-ttu-id="f6659-117">若要啟動 app-v 排序器主控台，請在執行 app-v 排序器的電腦上，選取 [**開始**  /  **程式**]  /  **microsoft application virtualization**  /  **microsoft application virtualization sequencer**。</span><span class="sxs-lookup"><span data-stu-id="f6659-117">To start the App-V Sequencer Console, on the computer that is running the App-V Sequencer, select **Start** / **Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span> <span data-ttu-id="f6659-118">若要啟動 [排序嚮導]，請按一下 [**建立套件**]。</span><span class="sxs-lookup"><span data-stu-id="f6659-118">To start the Sequencing Wizard, click **Create a Package**.</span></span>

3.  <span data-ttu-id="f6659-119">在 [**套件資訊**] 頁面上，指定將指派給虛擬應用程式的**套件名稱**。</span><span class="sxs-lookup"><span data-stu-id="f6659-119">On the **Package Information** page, specify the **Package Name** that will be assigned to the virtual application.</span></span> <span data-ttu-id="f6659-120">需要套件名稱來產生相關聯的 Windows 安裝程式檔案。</span><span class="sxs-lookup"><span data-stu-id="f6659-120">The package name is required for generating the associated Windows Installer file.</span></span> <span data-ttu-id="f6659-121">您也應該加入將指派給套件的選擇性批註，並提供虛擬應用程式的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="f6659-121">You should also add an optional comment that will be assigned to the package and that provides detailed information about the virtual application.</span></span> <span data-ttu-id="f6659-122">若要顯示 [**高級選項**] 頁面，請選取 [**顯示高級監視選項**]，然後按 **[下一步]**。否則，請繼續執行步驟5。</span><span class="sxs-lookup"><span data-stu-id="f6659-122">To display the **Advanced Options** page, select **Show Advanced Monitoring Options**, and then click **Next**; otherwise, proceed to step 5.</span></span>

4.  <span data-ttu-id="f6659-123">在 [**高級選項**] 頁面上，若要允許 microsoft update 在進行排序的情況下更新應用程式，請選取 [**允許 microsoft update 在監視期間執行**]。</span><span class="sxs-lookup"><span data-stu-id="f6659-123">On the **Advanced Options** page, to allow Microsoft Update to update the application as it is being sequenced, select **Allow Microsoft Update to run during monitoring**.</span></span> <span data-ttu-id="f6659-124">如果您選取此選項，則可以在監視階段安裝 Microsoft 更新，您必須接受相關的更新，才能安裝它們。</span><span class="sxs-lookup"><span data-stu-id="f6659-124">If you select this option, Microsoft Updates can be installed during the monitoring phase, and you have to accept the associated updates for them to be installed.</span></span> <span data-ttu-id="f6659-125">若要重新映射支援的動態連結程式庫（.dll）檔案，以便它們使用連續的 RAM 空間，請選取 [**變基 dll**]。</span><span class="sxs-lookup"><span data-stu-id="f6659-125">To remap the supported dynamic link library (.dll) files so that they use a contiguous space of RAM, select **Rebase DLLs**.</span></span> <span data-ttu-id="f6659-126">選取此選項可以保留記憶體，並協助改善效能。</span><span class="sxs-lookup"><span data-stu-id="f6659-126">Selecting this option can conserve memory and help improve performance.</span></span> <span data-ttu-id="f6659-127">許多應用程式不支援此選項，但在具有有限 RAM （例如在終端伺服器案例中）的環境中很有用。</span><span class="sxs-lookup"><span data-stu-id="f6659-127">Many applications do not support this option, but it is useful in environments with limited RAM such as in Terminal Server scenarios.</span></span> <span data-ttu-id="f6659-128">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="f6659-128">Click **Next**.</span></span>

5.  <span data-ttu-id="f6659-129">在 [**顯示器安裝**] 頁面上，當您準備好要安裝應用程式時，請按一下 [**開始監視**]，然後在 [**流覽資料夾**] 對話方塊中，指定將安裝應用程式的磁碟機 Q 目錄。</span><span class="sxs-lookup"><span data-stu-id="f6659-129">On the **Monitor Installation** page, when you are ready to install the application, click **Begin Monitoring**, and in the **Browse for Folder** dialog box, specify the directory on drive Q where the application will be installed.</span></span> <span data-ttu-id="f6659-130">如果您沒有設定磁碟機 Q，且針對應用程式虛擬化磁片磁碟機使用不同的磁片磁碟機盤符，請選取您在此程式步驟1中指定的磁碟機盤符。</span><span class="sxs-lookup"><span data-stu-id="f6659-130">If you did not configure drive Q and used a different drive letter for the application virtualization drive, select the drive letter you specified in step 1 of this procedure.</span></span> <span data-ttu-id="f6659-131">若要將應用程式安裝至未在應用程式虛擬化磁片磁碟機上建立的資料夾，請按一下 [**建立新資料夾**]。</span><span class="sxs-lookup"><span data-stu-id="f6659-131">To install the application to a folder that has not been created on the application virtualization drive, click **Make New Folder**.</span></span> <span data-ttu-id="f6659-132">指定資料夾之後，請稍候，排序器會將電腦設定為進行排序。</span><span class="sxs-lookup"><span data-stu-id="f6659-132">After you specify the folder, wait while the Sequencer configures the computer for sequencing.</span></span>

    **<span data-ttu-id="f6659-133">重要</span><span class="sxs-lookup"><span data-stu-id="f6659-133">Important</span></span>**  
    <span data-ttu-id="f6659-134">您必須安裝您在虛擬應用程式磁碟機上的個別目錄中順序的每個應用程式，且關聯資料夾名稱不得超過八個字元。</span><span class="sxs-lookup"><span data-stu-id="f6659-134">You must install each application that you sequence into a separate directory on the virtual application drive, and the associated folder name must not be longer than eight characters.</span></span>



~~~
After the computer has been configured for sequencing, install the application so that the App-V Sequencer can monitor the installation; when you are finished, click **Stop Monitoring**, and then click **Next**.
~~~

6. <span data-ttu-id="f6659-135">如有需要，請在 [**設定應用程式**] 頁面上，設定將與虛擬應用程式建立關聯的快速鍵與檔案類型關聯。</span><span class="sxs-lookup"><span data-stu-id="f6659-135">On the **Configure Applications** page, if necessary, configure the shortcuts and file type associations that will be associated with the virtual application.</span></span> <span data-ttu-id="f6659-136">若要新增新的檔案類型關聯或快捷方式，**請按一下 [新增]**，然後在 [**新增應用程式**] 對話方塊中，指定新的元素。</span><span class="sxs-lookup"><span data-stu-id="f6659-136">To add a new file type association or shortcut, click **Add**, and in the **Add Application** dialog box, specify the new element.</span></span> <span data-ttu-id="f6659-137">若要移除現有的快捷方式或檔案類型關聯，請按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="f6659-137">To remove an existing shortcut or file type association, click **Remove**.</span></span> <span data-ttu-id="f6659-138">若要編輯現有的元素，請選取您要修改的元素，然後按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="f6659-138">To edit an existing element, select the element you want to modify, and then click **Edit**.</span></span> <span data-ttu-id="f6659-139">在 [**編輯應用程式**] 對話方塊中指定設定。</span><span class="sxs-lookup"><span data-stu-id="f6659-139">Specify the configurations in the **Edit Application** dialog box.</span></span> <span data-ttu-id="f6659-140">按一下 [**儲存**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f6659-140">Click **Save**, and then click **Next**.</span></span>

7. <span data-ttu-id="f6659-141">在 [**啟動應用程式**] 頁面上，若要啟動應用程式以確保套件已正確安裝且已針對流式處理進行優化，請選取套件，然後按一下 [**啟動**]。</span><span class="sxs-lookup"><span data-stu-id="f6659-141">On the **Launch Applications** page, to start the application to ensure that the package has been installed correctly and is optimized for streaming, select the package, and then click **Launch**.</span></span> <span data-ttu-id="f6659-142">此步驟適用于設定應用程式在目的電腦上的初始執行方式，以及在套件可提供給 App-v 用戶端之前接受任何相關聯的授權協定。</span><span class="sxs-lookup"><span data-stu-id="f6659-142">This step is useful for configuring how the application initially runs on targeted computers and for accepting any associated license agreements before the package becomes available to App-V clients.</span></span> <span data-ttu-id="f6659-143">如果有多個應用程式與此套件相關聯，您可以選取 [**全部啟動**] 來開啟所有的應用程式。</span><span class="sxs-lookup"><span data-stu-id="f6659-143">If multiple applications are associated with this package, you can select **Launch All** to open all of the applications.</span></span> <span data-ttu-id="f6659-144">若要對套件進行排序，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="f6659-144">To sequence the package, click **Next**.</span></span>

8. <span data-ttu-id="f6659-145">成功建立套件後，請在 App V 排序器主控台中 **，選取 [** 檔案儲存]，  /  **Save**並指定要儲存套件的名稱和虛擬磁片磁碟機位置。</span><span class="sxs-lookup"><span data-stu-id="f6659-145">After you have successfully created the package, in the App-V Sequencer Console, select **File** / **Save** and specify the name and the virtual drive location where the package will be saved.</span></span>

   <span data-ttu-id="f6659-146">您也可以選擇建立關聯的 Windows 安裝程式檔案（**.msi**），在目的電腦上安裝虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="f6659-146">You can optionally create an associated Windows Installer file (**.msi**) to install the virtual application package on targeted computers.</span></span> <span data-ttu-id="f6659-147">若要建立 Windows 安裝程式檔案，請在 Sequencer 中開啟套件，然後選取 [**工具**] [  /  **建立 MSI**]。</span><span class="sxs-lookup"><span data-stu-id="f6659-147">To create a Windows Installer file, open the package in the Sequencer and select **Tools** / **Create MSI**.</span></span> <span data-ttu-id="f6659-148">Windows 安裝程式檔案將會建立並儲存在儲存虛擬應用程式套件的目錄中。</span><span class="sxs-lookup"><span data-stu-id="f6659-148">The Windows Installer file will be created and saved in the directory where the virtual application package is saved.</span></span>

   **<span data-ttu-id="f6659-149">重要</span><span class="sxs-lookup"><span data-stu-id="f6659-149">Important</span></span>**  
   <span data-ttu-id="f6659-150">成功建立虛擬應用程式套件之後，您就無法在執行排序器的電腦上執行虛擬應用程式套件。</span><span class="sxs-lookup"><span data-stu-id="f6659-150">After you have successfully created a virtual application package, you cannot run the virtual application package on the computer running the sequencer.</span></span>



## <span data-ttu-id="f6659-151">相關主題</span><span class="sxs-lookup"><span data-stu-id="f6659-151">Related topics</span></span>


[<span data-ttu-id="f6659-152">如何升級虛擬應用程式封裝 (App-V 4.6)</span><span class="sxs-lookup"><span data-stu-id="f6659-152">How to Upgrade a Virtual Application Package (App-V 4.6)</span></span>](how-to-upgrade-a-virtual-application-package--app-v-46-.md)









