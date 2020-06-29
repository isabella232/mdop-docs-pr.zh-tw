---
title: 如何升級循序虛擬應用程式封裝
description: 如何升級循序虛擬應用程式封裝
author: dansimp
ms.assetid: ffa989f3-6621-4c59-9599-e3c3b3332f67
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 45f7b3370e7989bfa860c25fd4ac81f2c2eb0959
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801034"
---
# <span data-ttu-id="e9b3e-103">如何升級循序虛擬應用程式封裝</span><span class="sxs-lookup"><span data-stu-id="e9b3e-103">How to Upgrade a Sequenced Virtual Application Package</span></span>


<span data-ttu-id="e9b3e-104">您可以使用應用程式虛擬化（App-v）排序器，將現有的虛擬應用程式升級至新版本。</span><span class="sxs-lookup"><span data-stu-id="e9b3e-104">You can upgrade an existing virtual application to a new version by using the Application Virtualization (App-V) Sequencer.</span></span> <span data-ttu-id="e9b3e-105">升級程式類似于建立新的虛擬應用程式。</span><span class="sxs-lookup"><span data-stu-id="e9b3e-105">The upgrade process is similar to creating a new virtual application.</span></span> <span data-ttu-id="e9b3e-106">您必須開啟現有的虛擬應用程式以進行升級、進行必要的更新，然後將更新的虛擬應用程式儲存到套件根目錄中的新位置。</span><span class="sxs-lookup"><span data-stu-id="e9b3e-106">You must open the existing virtual application for an upgrade, make the necessary updates, and then save the updated virtual application to a new location in the package root directory.</span></span> <span data-ttu-id="e9b3e-107">您也可以使用 App-v 排序器主控台來變更現有的虛擬應用程式，而不需執行升級。</span><span class="sxs-lookup"><span data-stu-id="e9b3e-107">You can also use the App-V Sequencer Console to make changes to an existing virtual application without performing an upgrade.</span></span> <span data-ttu-id="e9b3e-108">不過，您無法使用此方法對虛擬應用程式的檔案系統進行修改，因為 App-v 排序器不會實際解碼關聯的 sft 檔案。</span><span class="sxs-lookup"><span data-stu-id="e9b3e-108">However, you cannot make modifications to the virtual application’s file system by using this method because the App-V Sequencer does not actually decode the associated .sft file.</span></span> <span data-ttu-id="e9b3e-109">例如，您可以在 App-v 排序器主控台中，選取 [檔案 **] 功能表上的 [** **開啟**]，以開啟現有的虛擬應用程式。</span><span class="sxs-lookup"><span data-stu-id="e9b3e-109">For example; you can open an existing virtual application in the App-V Sequencer Console by selecting **Open** on the **File** menu.</span></span> <span data-ttu-id="e9b3e-110">您可以更新**套件名稱**和相關聯的**批註**，而且您可以變更虛擬檔案系統和虛擬機器碼。</span><span class="sxs-lookup"><span data-stu-id="e9b3e-110">You can update the **Package Name** and the associated **Comments**, and you can make changes to the virtual file system and virtual registry.</span></span> <span data-ttu-id="e9b3e-111">您也可以建立 Windows 安裝程式檔案。</span><span class="sxs-lookup"><span data-stu-id="e9b3e-111">You can also create a Windows Installer file.</span></span>

<span data-ttu-id="e9b3e-112">**小心** 當您升級現有的虛擬應用程式套件時，您不應該參照舊版的 Windows Installer （.msi）檔案，因為升級期間將會修改前一版的 sft 檔案。</span><span class="sxs-lookup"><span data-stu-id="e9b3e-112">**Caution** You should not reference a previous version of the Windows Installer (.msi) file when you upgrade an existing virtual application package because the previous version of the .sft file will be modified during the upgrade.</span></span>

 

<span data-ttu-id="e9b3e-113">使用下列程式來升級現有的虛擬應用程式。</span><span class="sxs-lookup"><span data-stu-id="e9b3e-113">Use the following procedure to upgrade an existing virtual application.</span></span>

**<span data-ttu-id="e9b3e-114">若要升級現有的虛擬應用程式</span><span class="sxs-lookup"><span data-stu-id="e9b3e-114">To upgrade an existing virtual application</span></span>**

1.  <span data-ttu-id="e9b3e-115">若要啟動 app-v 排序器主控台，請在執行 app-v 排序器的電腦上，選取 [**開始** / **程式**] / **microsoft application virtualization** / **microsoft application virtualization sequencer**。</span><span class="sxs-lookup"><span data-stu-id="e9b3e-115">To start the App-V Sequencer Console, on the computer running the App-V Sequencer, select **Start**/**Programs**/**Microsoft Application Virtualization**/**Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="e9b3e-116">若要開啟現有的虛擬應用程式，請在應用程式 V 主機中 **，選取 [** / **開啟檔案以進行套件升級**]。</span><span class="sxs-lookup"><span data-stu-id="e9b3e-116">To open the existing virtual application, in the App-V Console, select **File**/**Open for Package Upgrade**.</span></span> <span data-ttu-id="e9b3e-117">使用 [**開啟以進行套件升級**] 對話方塊，找出您要開啟以進行升級的相關 SPRJ 檔案。</span><span class="sxs-lookup"><span data-stu-id="e9b3e-117">Use the **Open For Package Upgrade** dialog box to locate the associated SPRJ file you want to open for upgrade.</span></span>

3.  <span data-ttu-id="e9b3e-118">若要指定要將更新套件解碼的位置，請使用 [**流覽資料夾**] 對話方塊流覽至該位置。</span><span class="sxs-lookup"><span data-stu-id="e9b3e-118">To specify the location of where the updated package will be decoded, browse to the location by using the **Browse For Folder** dialog box.</span></span> <span data-ttu-id="e9b3e-119">這個位置是您在關聯的 SFT 檔案中指定的套件根目錄建立位置。</span><span class="sxs-lookup"><span data-stu-id="e9b3e-119">This is the location where the package root directory will be created as specified in the associated SFT file.</span></span> <span data-ttu-id="e9b3e-120">您指定的目錄必須與原始版本的虛擬應用程式儲存在不同的位置。</span><span class="sxs-lookup"><span data-stu-id="e9b3e-120">The directory that you specify must be a different location from where the original version of the virtual application is saved.</span></span> <span data-ttu-id="e9b3e-121">如果尚未建立新的目的檔案夾，您可以按一下 [**建立新資料夾**]。</span><span class="sxs-lookup"><span data-stu-id="e9b3e-121">You can click **Make New Folder** if the new target folder has not been created yet.</span></span> <span data-ttu-id="e9b3e-122">您應該選取應用程式虛擬化磁片磁碟機的根目錄以建立資料夾。</span><span class="sxs-lookup"><span data-stu-id="e9b3e-122">You should select the root of the Application Virtualization drive to create the folder.</span></span> <span data-ttu-id="e9b3e-123">當您建立套件的更新版本時，它會以目錄名稱的順序新增來表示，例如，"**.1**" 將會新增至位於 Q:\\ 磁片磁碟機上的目錄名稱。</span><span class="sxs-lookup"><span data-stu-id="e9b3e-123">When you create the updated version of the package, it will be denoted with a sequential addition to the directory name—for example, “**.1**” will be added to the directory name located on the Q:\\ drive.</span></span>

    <span data-ttu-id="e9b3e-124">**重要** 您指定的目錄必須位於 Q:\\ 磁片磁碟機上的套件根目錄中。</span><span class="sxs-lookup"><span data-stu-id="e9b3e-124">**Important** The directory that you specify must be located in the package root directory on the Q:\\ drive.</span></span> <span data-ttu-id="e9b3e-125">您可以建立新的資料夾，或者您可以在儲存原始虛擬應用程式的目錄下建立子資料夾。</span><span class="sxs-lookup"><span data-stu-id="e9b3e-125">You can create a new folder, or you can create a subfolder under the directory where the original virtual application is saved.</span></span> <span data-ttu-id="e9b3e-126">指派給新資料夾的名稱不得超過 8 8 個字元。</span><span class="sxs-lookup"><span data-stu-id="e9b3e-126">The name assigned to the new folder must not be longer than 8 eight characters.</span></span>

     

4.  <span data-ttu-id="e9b3e-127">若要開啟 [順序] 嚮導，請選取 [**工具** / **先後順序] 嚮導**。</span><span class="sxs-lookup"><span data-stu-id="e9b3e-127">To open the Sequencing Wizard, select **Tools**/**Sequencing Wizard**.</span></span> <span data-ttu-id="e9b3e-128">在 [**套件資訊**] 頁面上，選擇性地指定新的**套件名稱**，並新增將與已更新的虛擬應用程式相關聯的選擇性批註。</span><span class="sxs-lookup"><span data-stu-id="e9b3e-128">On the **Package Information** page, optionally specify the new **Package Name** and add optional comments that will be associated with the updated virtual application.</span></span> <span data-ttu-id="e9b3e-129">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="e9b3e-129">Click **Next**.</span></span>

5.  <span data-ttu-id="e9b3e-130">在 [**顯示器安裝**] 頁面上，若要開始監視新的安裝，請按一下 [**開始監視**]。</span><span class="sxs-lookup"><span data-stu-id="e9b3e-130">On the **Monitor Installation** page, to begin monitoring the new installation, click **Begin Monitoring**.</span></span> <span data-ttu-id="e9b3e-131">在虛擬環境完成載入之後，安裝應用程式的更新版本，或將更新套用至現有的應用程式。</span><span class="sxs-lookup"><span data-stu-id="e9b3e-131">After the virtual environment has finished loading, install the updated version of the application, or apply updates to the existing application.</span></span> <span data-ttu-id="e9b3e-132">更新虛擬應用程式完成後，請按一下 [**停止監視**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e9b3e-132">After you have finished updating the virtual application, click **Stop Monitoring**, and then click **Next**.</span></span>

6.  <span data-ttu-id="e9b3e-133">在 [**要對應至虛擬檔案系統（vfs）的其他**檔案] 頁面上，若要指定要新增至虛擬檔案系統（vfs）的其他檔案，請按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="e9b3e-133">On the **Additional Files to Map to Virtual File System (VFS)** page, to specify additional files to be added to the Virtual File System (VFS), click **Add**.</span></span> <span data-ttu-id="e9b3e-134">流覽至您要新增的檔案，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="e9b3e-134">Browse to the file you want to add, and click **Open**.</span></span> <span data-ttu-id="e9b3e-135">若要清除已新增的現有檔案，請按一下 [**重設**]，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e9b3e-135">To clear existing files that have been added, click **Reset**, and then click **Next**.</span></span>

7.  <span data-ttu-id="e9b3e-136">在 [**設定應用程式**] 頁面上，設定將與已更新虛擬應用程式相關聯的快捷方式和檔案類型關聯。</span><span class="sxs-lookup"><span data-stu-id="e9b3e-136">On the **Configure Applications** page, configure the shortcuts and file type associations that will be associated with the updated virtual application.</span></span> <span data-ttu-id="e9b3e-137">選取您要更新的元素，然後按一下 [**編輯位置**]。</span><span class="sxs-lookup"><span data-stu-id="e9b3e-137">Select the element you want to update, and then click **Edit Locations**.</span></span> <span data-ttu-id="e9b3e-138">在 [**快捷方式位置**] 對話方塊中指定設定，然後按一下 **[下一步**]。</span><span class="sxs-lookup"><span data-stu-id="e9b3e-138">Specify the configurations in the **Shortcut Locations** dialog box, and then click **Next**.</span></span>

8.  <span data-ttu-id="e9b3e-139">在 [**啟動應用程式**] 頁面上，若要啟動應用程式以確保套件針對流式處理進行優化，請選取套件，然後按一下 [**啟動**]。</span><span class="sxs-lookup"><span data-stu-id="e9b3e-139">On the **Launch Applications** page, to start the application to ensure that the package is optimized for streaming, select the package and click **Launch**.</span></span> <span data-ttu-id="e9b3e-140">此步驟可讓您設定在將套件提供給用戶端之前，如何開始在目的電腦上執行應用程式，以及接受任何相關的授權協定。</span><span class="sxs-lookup"><span data-stu-id="e9b3e-140">This step is useful for configuring how the application initially runs on target computers and for accepting any associated license agreements before the package is made available to clients.</span></span> <span data-ttu-id="e9b3e-141">如果有多個應用程式與此套件相關聯，您可以選取 [**全部啟動**] 來開啟所有的應用程式。</span><span class="sxs-lookup"><span data-stu-id="e9b3e-141">If there are multiple applications associated with this package, you can select **Launch All** to open all of the applications.</span></span> <span data-ttu-id="e9b3e-142">若要為新版本的虛擬應用程式排序，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="e9b3e-142">To sequence the new version of the virtual application, click **Next**.</span></span>

9.  <span data-ttu-id="e9b3e-143">若要完成並關閉 [順序] 嚮導，請在 [**順序包**] 頁面上，按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="e9b3e-143">To finish and to close the Sequencing Wizard, on the **Sequence Package** page, click **Finish**.</span></span>

10. <span data-ttu-id="e9b3e-144">成功更新虛擬應用程式後，若要儲存套件，請在 App V 排序器**主控台的 [檔案] 功能表上**，選取 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="e9b3e-144">After you have successfully updated the virtual application, to save the package, in the App-V Sequencer Console, on the **File** menu, select **Save**.</span></span> <span data-ttu-id="e9b3e-145">您可以在步驟3中指定的目錄中存取虛擬應用程式。</span><span class="sxs-lookup"><span data-stu-id="e9b3e-145">The virtual application can be accessed in the directory specified in step 3.</span></span>

## <span data-ttu-id="e9b3e-146">相關主題</span><span class="sxs-lookup"><span data-stu-id="e9b3e-146">Related topics</span></span>


[<span data-ttu-id="e9b3e-147">Application Virtualization Sequencer 的工作</span><span class="sxs-lookup"><span data-stu-id="e9b3e-147">Tasks for the Application Virtualization Sequencer</span></span>](tasks-for-the-application-virtualization-sequencer.md)

 

 





