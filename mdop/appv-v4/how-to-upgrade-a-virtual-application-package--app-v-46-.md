---
title: 如何升級虛擬應用程式封裝 (App-V 4.6)
description: 如何升級虛擬應用程式封裝 (App-V 4.6)
author: dansimp
ms.assetid: 3566227e-f3dc-4c32-af1f-e0211588118c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: ac722dc0e9ce1650f53d8dd22db5428d33cfcf13
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801025"
---
# <span data-ttu-id="57c7f-103">如何升級虛擬應用程式封裝 (App-V 4.6)</span><span class="sxs-lookup"><span data-stu-id="57c7f-103">How to Upgrade a Virtual Application Package (App-V 4.6)</span></span>


<span data-ttu-id="57c7f-104">使用下列程式來升級現有的虛擬應用程式，方法是使用應用程式虛擬化（App-v）排序器。</span><span class="sxs-lookup"><span data-stu-id="57c7f-104">Use the following procedure to upgrade an existing virtual application by using the Application Virtualization (App-V) Sequencer.</span></span> <span data-ttu-id="57c7f-105">您也可以使用 App-v 排序器主控台，在不執行升級的情況下，變更現有的虛擬應用程式，但您無法使用此方法對虛擬應用程式的檔案系統進行修改，因為 App-v 排序器不會實際解碼關聯的 sft 檔案。</span><span class="sxs-lookup"><span data-stu-id="57c7f-105">You can also use the App-V Sequencer Console to make changes to an existing virtual application without performing an upgrade, but you cannot make modifications to the virtual application’s file system by using this method because the App-V Sequencer does not actually decode the associated .sft file.</span></span> <span data-ttu-id="57c7f-106">如需編輯現有套件的詳細資訊，請參閱[如何修改虛擬應用程式套件（app-v 4.6）](how-to-modify-a-virtual-application-package--app-v-46-.md)。</span><span class="sxs-lookup"><span data-stu-id="57c7f-106">For more information about editing an existing package, see [How to Modify a Virtual Application Package (App-V 4.6)](how-to-modify-a-virtual-application-package--app-v-46-.md).</span></span>

**<span data-ttu-id="57c7f-107">若要升級現有的虛擬應用程式</span><span class="sxs-lookup"><span data-stu-id="57c7f-107">To upgrade an existing virtual application</span></span>**

1.  <span data-ttu-id="57c7f-108">若要啟動 app-v 排序器主控台，請在執行 app-v 排序器的電腦上，選取 [**開始**  /  **程式**]  /  **microsoft application virtualization**  /  **microsoft application virtualization sequencer**。</span><span class="sxs-lookup"><span data-stu-id="57c7f-108">To start the App-V Sequencer Console, on the computer running the App-V Sequencer, select **Start** / **Programs** / **Microsoft Application Virtualization** / **Microsoft Application Virtualization Sequencer**.</span></span>

2.  <span data-ttu-id="57c7f-109">若要開啟現有的虛擬應用程式套件，並啟動 [**順序] 嚮導**，請選取 [**升級套件**]。</span><span class="sxs-lookup"><span data-stu-id="57c7f-109">To open the existing virtual application package and start the **Sequencing Wizard**, select **Upgrade a Package**.</span></span> <span data-ttu-id="57c7f-110">找出您要升級的套件，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="57c7f-110">Locate the package you want to upgrade, and click **Open**.</span></span> <span data-ttu-id="57c7f-111">在 [**流覽資料夾**] 對話方塊中，指定將放置升級版本套件的位置。</span><span class="sxs-lookup"><span data-stu-id="57c7f-111">In the **Browse For Folder** dialog box, specify the location where the upgraded version of the package will be placed.</span></span> <span data-ttu-id="57c7f-112">指定的這個位置必須位於指定為應用程式虛擬化磁片磁碟機的磁片磁碟機上，通常是 Q:\\ 磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="57c7f-112">This location specified must be located on the drive specified as the application virtualization drive, which is typically the Q:\\ drive.</span></span> <span data-ttu-id="57c7f-113">若要建立新資料夾，請選取 [**建立新資料夾**]。</span><span class="sxs-lookup"><span data-stu-id="57c7f-113">To create a new folder, select **Make New Folder**.</span></span>

    <span data-ttu-id="57c7f-114">**警告** 您必須指定現有虛擬應用程式的根資料夾。</span><span class="sxs-lookup"><span data-stu-id="57c7f-114">**Warning** You must specify the root folder of the existing virtual application.</span></span> <span data-ttu-id="57c7f-115">請勿手動建立子資料夾，否則升級將會失敗。</span><span class="sxs-lookup"><span data-stu-id="57c7f-115">Do not manually create a subfolder or the upgrade will fail.</span></span>

     

3.  <span data-ttu-id="57c7f-116">在 [**封裝資訊**] 頁面上，指定將指派給更新套件的**套件名稱**。</span><span class="sxs-lookup"><span data-stu-id="57c7f-116">On the **Package Information** page, specify the **Package Name** that will be assigned to the updated package.</span></span> <span data-ttu-id="57c7f-117">需要套件名稱來產生相關聯的 Windows 安裝程式檔案。</span><span class="sxs-lookup"><span data-stu-id="57c7f-117">The package name is required for generating the associated Windows Installer file.</span></span> <span data-ttu-id="57c7f-118">您也應該加入將指派給套件的選擇性批註，並提供虛擬應用程式的詳細資訊，例如版本號碼。</span><span class="sxs-lookup"><span data-stu-id="57c7f-118">You should also add an optional comment that will be assigned to the package and that provides detailed information about the virtual application—for example, a version number.</span></span> <span data-ttu-id="57c7f-119">若要顯示 [**高級選項**] 頁面，請選取 [**顯示高級監視選項**]，然後按 **[下一步]** 否則，請繼續執行步驟5。</span><span class="sxs-lookup"><span data-stu-id="57c7f-119">To display the **Advanced Options** page, select **Show Advanced Monitoring Options** and click **Next**; otherwise, proceed to step 5.</span></span>

4.  <span data-ttu-id="57c7f-120">在 [**高級選項**] 頁面上，若要允許 microsoft update 在進行排序的情況下更新應用程式，請選取 [**允許 microsoft update 在監視期間執行**]。</span><span class="sxs-lookup"><span data-stu-id="57c7f-120">On the **Advanced Options** page, to allow Microsoft Update to update the application as it is being sequenced, select **Allow Microsoft Update to run during monitoring**.</span></span> <span data-ttu-id="57c7f-121">如果您選取此選項，系統會在監視階段中允許安裝 Microsoft 更新，您必須接受相關的更新，才能安裝它們。</span><span class="sxs-lookup"><span data-stu-id="57c7f-121">If you select this option, Microsoft Updates are allowed to be installed during the monitoring phase and you will need to accept the associated updates for them to be installed.</span></span> <span data-ttu-id="57c7f-122">若要重新映射支援的動態連結程式庫（.dll）檔案，以便它們使用連續的 RAM 空間，請選取 [**變基 dll**]。</span><span class="sxs-lookup"><span data-stu-id="57c7f-122">To remap the supported dynamic-link library (.dll) files so that they use a contiguous space of RAM, select **Rebase DLLs**.</span></span> <span data-ttu-id="57c7f-123">選取此選項可以保留記憶體，並協助改善效能。</span><span class="sxs-lookup"><span data-stu-id="57c7f-123">Selecting this option can conserve memory and help improve performance.</span></span> <span data-ttu-id="57c7f-124">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="57c7f-124">Click **Next**.</span></span>

5.  <span data-ttu-id="57c7f-125">在 [**顯示器安裝**] 頁面上，當您準備好要更新應用程式時，請按一下 [**開始監視**]。</span><span class="sxs-lookup"><span data-stu-id="57c7f-125">On the **Monitor Installation** page, when you are ready to update the application, click **Begin Monitoring**.</span></span>

    <span data-ttu-id="57c7f-126">當應用程式的更新已套用時，按一下 [**停止監視**]。</span><span class="sxs-lookup"><span data-stu-id="57c7f-126">When the updates to the application have been applied, click **Stop Monitoring**.</span></span> <span data-ttu-id="57c7f-127">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="57c7f-127">Click **Next**.</span></span>

6.  <span data-ttu-id="57c7f-128">如有需要，請在 [**設定應用程式**] 頁面上，設定將與虛擬應用程式建立關聯的快速鍵與檔案類型關聯。</span><span class="sxs-lookup"><span data-stu-id="57c7f-128">On the **Configure Applications** page, if necessary, configure the shortcuts and file type associations that will be associated with the virtual application.</span></span> <span data-ttu-id="57c7f-129">若要新增新的檔案類型關聯或快捷方式，**請按一下 [新增]**，然後在 [**新增應用程式**] 對話方塊中，指定新的元素。</span><span class="sxs-lookup"><span data-stu-id="57c7f-129">To add a new file type association or shortcut, click **Add**, and in the **Add Application** dialog box, specify the new element.</span></span> <span data-ttu-id="57c7f-130">若要移除現有的快捷方式或檔案類型關聯，請按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="57c7f-130">To remove an existing shortcut or file type association, click **Remove**.</span></span> <span data-ttu-id="57c7f-131">若要編輯現有的元素，請選取您要修改的元素，然後按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="57c7f-131">To edit an existing element, select the element you want to modify, and then click **Edit**.</span></span> <span data-ttu-id="57c7f-132">在 [**編輯應用程式**] 對話方塊中指定設定。</span><span class="sxs-lookup"><span data-stu-id="57c7f-132">Specify the configurations in the **Edit Application** dialog box.</span></span> <span data-ttu-id="57c7f-133">按一下 **[儲存]**。</span><span class="sxs-lookup"><span data-stu-id="57c7f-133">Click **Save**.</span></span> <span data-ttu-id="57c7f-134">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="57c7f-134">Click **Next**.</span></span>

7.  <span data-ttu-id="57c7f-135">在 [**啟動應用程式**] 頁面上，若要啟動應用程式以確保套件已正確安裝且已針對流式處理進行優化，請選取套件，然後按一下 [**啟動**]。</span><span class="sxs-lookup"><span data-stu-id="57c7f-135">On the **Launch Applications** page, to start the application to ensure that the package has been installed correctly and is optimized for streaming, select the package and click **Launch**.</span></span> <span data-ttu-id="57c7f-136">這個步驟非常適合用來設定應用程式在目的電腦上的初始執行方式，以及在將套件提供給 App-v 用戶端之前接受任何相關的授權協定。</span><span class="sxs-lookup"><span data-stu-id="57c7f-136">This step is useful for configuring how the application initially runs on target computers and for accepting any associated license agreements before the package is made available to App-V clients.</span></span> <span data-ttu-id="57c7f-137">如果有多個應用程式與此套件相關聯，您可以選取 [**全部啟動**] 來開啟所有的應用程式。</span><span class="sxs-lookup"><span data-stu-id="57c7f-137">If multiple applications are associated with this package, you can select **Launch All** to open all of the applications.</span></span> <span data-ttu-id="57c7f-138">若要對套件進行排序，請按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="57c7f-138">To sequence the package, click **Next**.</span></span>

8.  <span data-ttu-id="57c7f-139">若要關閉 [排序嚮導]，請按一下 **[完成]**。</span><span class="sxs-lookup"><span data-stu-id="57c7f-139">To close the Sequencing Wizard, click **Finish**.</span></span> <span data-ttu-id="57c7f-140">若要儲存更新的套件，請在 Sequencer 主控台中 **，選取 [** 檔案  /  **儲存**]。</span><span class="sxs-lookup"><span data-stu-id="57c7f-140">To save the updated package, in the Sequencer Console, select **File** / **Save**.</span></span>

    <span data-ttu-id="57c7f-141">如果您打算使用 Windows 安裝程式檔案（.msi）來部署更新的套件，您必須建立新的套件，如下所示：在 Sequencer 視窗中，選取 [**工具**  /  **建立 msi**]。</span><span class="sxs-lookup"><span data-stu-id="57c7f-141">If you plan to deploy the updated package by using a Windows Installer file (.msi), you must create new one as follows: in the Sequencer Console, select **Tools** / **Create MSI**.</span></span> <span data-ttu-id="57c7f-142">新的 Windows 安裝程式檔案將會建立，並儲存在已儲存更新虛擬應用程式套件的目錄中。</span><span class="sxs-lookup"><span data-stu-id="57c7f-142">The new Windows Installer file will be created and saved in the directory where the updated virtual application package is saved.</span></span>

## <span data-ttu-id="57c7f-143">相關主題</span><span class="sxs-lookup"><span data-stu-id="57c7f-143">Related topics</span></span>


[<span data-ttu-id="57c7f-144">如何排序新應用程式 (App-V 4.6)</span><span class="sxs-lookup"><span data-stu-id="57c7f-144">How to Sequence a New Application (App-V 4.6)</span></span>](how-to-sequence-a-new-application--app-v-46-.md)

 

 





