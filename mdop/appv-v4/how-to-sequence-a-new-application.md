---
title: 如何排序新應用程式
description: 如何排序新應用程式
author: dansimp
ms.assetid: e01e98cd-2378-478f-9739-f72c465bf79a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: aab769256116e2635edbc4bcf55d212e3a2152f8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801109"
---
# <span data-ttu-id="1b5df-103">如何排序新應用程式</span><span class="sxs-lookup"><span data-stu-id="1b5df-103">How to Sequence a New Application</span></span>


<span data-ttu-id="1b5df-104">應用程式虛擬化（App-v） Sequencer 會建立可在虛擬環境中執行的應用程式。</span><span class="sxs-lookup"><span data-stu-id="1b5df-104">The Application Virtualization (App-V) Sequencer creates applications that can be run in a virtual environment.</span></span> <span data-ttu-id="1b5df-105">App-v 排序器會監視應用程式的安裝與設定程式，並記錄應用程式在虛擬環境中執行所需的資訊。</span><span class="sxs-lookup"><span data-stu-id="1b5df-105">The App-V Sequencer monitors the installation and setup process for an application, and it records the information necessary for the application to run in a virtual environment.</span></span> <span data-ttu-id="1b5df-106">您也可以使用 App-v 排序器，來設定哪些檔案和設定適用于所有的使用者，以及使用者可以自訂哪些檔案和配置。</span><span class="sxs-lookup"><span data-stu-id="1b5df-106">You can also use the App-V Sequencer to configure which files and configurations are applicable to all users and which files and configurations users can customize.</span></span> <span data-ttu-id="1b5df-107">當您為應用程式排序時，您應該將套件儲存到您正在進行排序的電腦的本機磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="1b5df-107">When you sequence an application, you should save the package to a drive that is local to the computer you are sequencing on.</span></span>

<span data-ttu-id="1b5df-108">已排序的應用程式不會與作業系統互動，因為每個應用程式都是在虛擬環境中執行，且獨立于可能在目的電腦上安裝或執行的其他應用程式。</span><span class="sxs-lookup"><span data-stu-id="1b5df-108">A sequenced application does not interact with the operating system because each application runs in a virtual environment and is isolated from other applications that might be installed or running on the target computer.</span></span> <span data-ttu-id="1b5df-109">這個隔離會大大減少應用程式衝突，並減少所需的應用程式預先部署測試數量。</span><span class="sxs-lookup"><span data-stu-id="1b5df-109">This isolation dramatically reduces application conflicts and decreases the required amount of application pre-deployment testing.</span></span>

<span data-ttu-id="1b5df-110">當您成功地順序應用程式後，就可以在 App-v 排序器主控台中使用它。</span><span class="sxs-lookup"><span data-stu-id="1b5df-110">After you successfully sequence the application, it is available in the App-V Sequencer Console.</span></span> <span data-ttu-id="1b5df-111">在安全模式中執行 App-v 排序器不受支援。</span><span class="sxs-lookup"><span data-stu-id="1b5df-111">Running the App-V sequencer in Safe Mode is not supported.</span></span>

**<span data-ttu-id="1b5df-112">為新的應用程式排序</span><span class="sxs-lookup"><span data-stu-id="1b5df-112">To sequence a new application</span></span>**

1.  <span data-ttu-id="1b5df-113">您必須建立應用程式虛擬化磁片磁碟機，以針對新的虛擬應用程式進行排序。</span><span class="sxs-lookup"><span data-stu-id="1b5df-113">You must create the Application Virtualization drive to sequence a new virtual application.</span></span> <span data-ttu-id="1b5df-114">若要建立應用程式虛擬化磁片磁碟機，請將 Q:\\ 磁片磁碟機對應至可在您為應用程式排序時用來儲存檔案的位置。</span><span class="sxs-lookup"><span data-stu-id="1b5df-114">To create the Application Virtualization drive, map the Q:\\ drive to a location that can be used to save files while you are sequencing an application.</span></span> <span data-ttu-id="1b5df-115">接著，您必須針對您打算在 Q:\\ 磁片磁碟機上順序的每個應用程式建立個別的目錄。</span><span class="sxs-lookup"><span data-stu-id="1b5df-115">You must then create individual directories for each application you plan to sequence on the Q:\\ drive.</span></span> <span data-ttu-id="1b5df-116">您可以在為應用程式排序前先建立虛擬應用程式目的檔案夾，或在此程式的步驟5中建立。</span><span class="sxs-lookup"><span data-stu-id="1b5df-116">You can create the virtual application target folders before you sequence an application, or you can create it in step 5 of this procedure.</span></span>

2.  <span data-ttu-id="1b5df-117">若要啟動 app-v 排序器主控台，請在執行 app-v 排序器的電腦上，選取 [**開始**  /  **程式**]  /  **microsoft application virtualization**  /  **microsoft application virtualization sequencer**。</span><span class="sxs-lookup"><span data-stu-id="1b5df-117">To start the App-V Sequencer Console, on the computer that is running the App-V Sequencer, select **Start** / **Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span> <span data-ttu-id="1b5df-118">若要啟動 [**順序] 嚮導**，**請選取 [** 檔案  /  **新套件**]。</span><span class="sxs-lookup"><span data-stu-id="1b5df-118">To start the **Sequencing Wizard**, select **File** / **New Package**.</span></span>

3.  <span data-ttu-id="1b5df-119">在 [**套件資訊**] 頁面上，指定將指派給虛擬應用程式的**套件名稱**。</span><span class="sxs-lookup"><span data-stu-id="1b5df-119">On the **Package Information** page, specify the **Package Name** that will be assigned to the virtual application.</span></span> <span data-ttu-id="1b5df-120">需要套件名稱來產生相關聯的 Windows 安裝程式檔案。</span><span class="sxs-lookup"><span data-stu-id="1b5df-120">The package name is required for generating the associated Windows Installer file.</span></span> <span data-ttu-id="1b5df-121">您也應該加入將指派給套件的選擇性批註，並提供虛擬應用程式的詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="1b5df-121">You should also add an optional comment that will be assigned to the package and that provides detailed information about the virtual application.</span></span> <span data-ttu-id="1b5df-122">若要顯示 [**高級選項**] 頁面，請選取 [**顯示高級監視選項**]。</span><span class="sxs-lookup"><span data-stu-id="1b5df-122">To display the **Advanced Options** page, select **Show Advanced Monitoring Options**.</span></span> <span data-ttu-id="1b5df-123">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="1b5df-123">Click **Next**.</span></span>

    **<span data-ttu-id="1b5df-124">注意</span><span class="sxs-lookup"><span data-stu-id="1b5df-124">Note</span></span>**  
    <span data-ttu-id="1b5df-125">若要顯示 [**高級選項**] 頁面，您必須選取 [**顯示高級監視選項**]。</span><span class="sxs-lookup"><span data-stu-id="1b5df-125">To display the **Advanced Options** page, you must select **Show Advanced Monitoring Options**.</span></span> <span data-ttu-id="1b5df-126">如果您不需要 [**高級選項**] 頁面，請跳至步驟4。</span><span class="sxs-lookup"><span data-stu-id="1b5df-126">If you do not require the **Advanced Options** page, skip to step 4.</span></span>



4.  <span data-ttu-id="1b5df-127">在 [**高級選項**] 頁面上，若要指定虛擬應用程式的**區塊大小**，請選取您想要的大小。</span><span class="sxs-lookup"><span data-stu-id="1b5df-127">On the **Advanced Options** page, to specify the **Block Size** for the virtual application, select the size you want.</span></span> <span data-ttu-id="1b5df-128">區塊大小決定如何將**sft**檔案分割成將整個網路套件封裝在目的電腦上。</span><span class="sxs-lookup"><span data-stu-id="1b5df-128">The block size determines how the **.sft** file will be divided for streaming the package across the network to target computers.</span></span> <span data-ttu-id="1b5df-129">若要允許 Microsoft 更新更新已排序的應用程式，請按選取 [**允許 Microsoft Update 在監視期間執行**]。</span><span class="sxs-lookup"><span data-stu-id="1b5df-129">To allow Microsoft Update to update the application as it is being sequenced; select **Allow Microsoft Update to run during monitoring**.</span></span> <span data-ttu-id="1b5df-130">如果您選取此選項，系統會在監視階段中允許安裝 Microsoft 更新，您必須接受相關的更新，才能安裝它們。</span><span class="sxs-lookup"><span data-stu-id="1b5df-130">If you select this option, Microsoft Updates are allowed to be installed during the monitoring phase and you will need to accept the associated updates for them to be installed.</span></span> <span data-ttu-id="1b5df-131">若要重新映射支援的動態連結程式庫（.dll）檔案，以便它們使用連續的 RAM 空間，請選取 [**變基 dll**]。</span><span class="sxs-lookup"><span data-stu-id="1b5df-131">To remap the supported dynamic link library (.dll) files so that they use a contiguous space of RAM, select **Rebase DLLs**.</span></span> <span data-ttu-id="1b5df-132">選取此選項可以保留記憶體，並協助改善效能。</span><span class="sxs-lookup"><span data-stu-id="1b5df-132">Selecting this option can conserve memory and help improve performance.</span></span> <span data-ttu-id="1b5df-133">許多應用程式不支援此選項，但在具有有限 RAM （例如在終端伺服器案例中）的環境中很有用。</span><span class="sxs-lookup"><span data-stu-id="1b5df-133">Many applications do not support this option, but it is useful in environments with limited RAM such as in Terminal Server scenarios.</span></span> <span data-ttu-id="1b5df-134">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="1b5df-134">Click **Next**.</span></span>

5.  <span data-ttu-id="1b5df-135">在 [**顯示器安裝**] 頁面上，若要監視應用程式的安裝，請按一下 [**開始監視**]。</span><span class="sxs-lookup"><span data-stu-id="1b5df-135">On the **Monitor Installation** page, to monitor the installation of an application, click **Begin Monitoring**.</span></span> <span data-ttu-id="1b5df-136">按一下 [**開始監視**] 後，指定 Q:\\ 磁片磁碟機上將安裝應用程式的目錄。</span><span class="sxs-lookup"><span data-stu-id="1b5df-136">After you click **Begin Monitoring**, specify the directory on the Q:\\ drive where the application will be installed.</span></span> <span data-ttu-id="1b5df-137">若要將應用程式安裝至尚未建立的資料夾，請按一下 [**建立新資料夾**]。</span><span class="sxs-lookup"><span data-stu-id="1b5df-137">To install the application to a folder that has not been created, click **Make New Folder**.</span></span> <span data-ttu-id="1b5df-138">您必須將每個程式序列安裝在不同的目錄中。</span><span class="sxs-lookup"><span data-stu-id="1b5df-138">You must install each application that you sequence into a separate directory.</span></span>

    **<span data-ttu-id="1b5df-139">重要</span><span class="sxs-lookup"><span data-stu-id="1b5df-139">Important</span></span>**  
    <span data-ttu-id="1b5df-140">您指定的資料夾名稱不得超過8個字元。</span><span class="sxs-lookup"><span data-stu-id="1b5df-140">The folder name you specify must not be longer than 8 characters.</span></span>



~~~
Wait for the virtual environment to load, and then install the application so that the App-V Sequencer can monitor the process. When you have completed the installation, click **Stop Monitoring** and then click **Next**.
~~~

6. <span data-ttu-id="1b5df-141">在 [**要對應至虛擬檔案系統（vfs）的其他**檔案] 頁面上，若要指定要新增至虛擬檔案系統（vfs）的其他檔案，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="1b5df-141">On the **Additional Files to Map to Virtual File System (VFS)** page, to specify additional files to be added to the Virtual File System (VFS), click **Add**.</span></span> <span data-ttu-id="1b5df-142">流覽至您要新增的檔案，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="1b5df-142">Browse to the file you want to add, and click **Open**.</span></span> <span data-ttu-id="1b5df-143">若要清除已新增的現有檔案，請按一下 [**重設**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="1b5df-143">To clear existing files that have been added, click **Reset** and then click **Next**.</span></span>

7. <span data-ttu-id="1b5df-144">在 [**設定應用程式**] 頁面上，設定將與虛擬應用程式建立關聯的快速鍵與檔案類型關聯。</span><span class="sxs-lookup"><span data-stu-id="1b5df-144">On the **Configure Applications** page, configure the shortcuts and file type associations that will be associated with the virtual application.</span></span> <span data-ttu-id="1b5df-145">選取您要更新的元素，然後按一下 [**編輯位置**]。</span><span class="sxs-lookup"><span data-stu-id="1b5df-145">Select the element you want to update, and then click **Edit Locations**.</span></span> <span data-ttu-id="1b5df-146">在 [**快捷方式位置**] 對話方塊中指定設定。</span><span class="sxs-lookup"><span data-stu-id="1b5df-146">Specify the configurations in the **Shortcut Locations** dialog box.</span></span> <span data-ttu-id="1b5df-147">按一下 **[確定]** ，然後按一下 **[下一步**]。</span><span class="sxs-lookup"><span data-stu-id="1b5df-147">Click **OK** and then click **Next**.</span></span>

8. <span data-ttu-id="1b5df-148">在 [**啟動應用程式**] 頁面上，若要啟動應用程式以確保套件針對流式處理進行優化，請選取套件，然後按一下 [**啟動**]。</span><span class="sxs-lookup"><span data-stu-id="1b5df-148">On the **Launch Applications** page, to start the application to ensure that the package is optimized for streaming, select the package and click **Launch**.</span></span> <span data-ttu-id="1b5df-149">此步驟可讓您設定在將套件提供給用戶端之前，如何開始在目的電腦上執行應用程式，以及接受任何相關的授權協定。</span><span class="sxs-lookup"><span data-stu-id="1b5df-149">This step is useful for configuring how the application initially runs on target computers and for accepting any associated license agreements before the package is made available to clients.</span></span> <span data-ttu-id="1b5df-150">如果有多個應用程式與此套件相關聯，您可以選取 [**全部啟動**] 來開啟所有的應用程式。</span><span class="sxs-lookup"><span data-stu-id="1b5df-150">If there are multiple applications associated with this package, you can select **Launch All** to open all of the applications.</span></span> <span data-ttu-id="1b5df-151">若要對套件進行排序，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="1b5df-151">To sequence the package, click **Next**.</span></span>

9. <span data-ttu-id="1b5df-152">在 [**序列套件**] 頁面上，若要關閉嚮導，請按一下 **[完成**]。</span><span class="sxs-lookup"><span data-stu-id="1b5df-152">On the **Sequence Package** page, to close the wizard, click **Finish**.</span></span>

10. <span data-ttu-id="1b5df-153">成功建立套件後，若要儲存套件，請在應用程式 V 排序器主控台中 **，選取 [** 檔案  /  **儲存**]，然後指定要儲存套件的名稱和位置。</span><span class="sxs-lookup"><span data-stu-id="1b5df-153">After you have successfully created the package, to save the package, in the App-V Sequencer Console, select **File** / **Save** and specify the name and the location where the package will be saved.</span></span>

## <span data-ttu-id="1b5df-154">相關主題</span><span class="sxs-lookup"><span data-stu-id="1b5df-154">Related topics</span></span>


[<span data-ttu-id="1b5df-155">Application Virtualization Sequencer 的工作</span><span class="sxs-lookup"><span data-stu-id="1b5df-155">Tasks for the Application Virtualization Sequencer</span></span>](tasks-for-the-application-virtualization-sequencer.md)









