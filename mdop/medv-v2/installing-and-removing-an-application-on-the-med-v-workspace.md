---
title: 安裝和移除 MED-V 工作區上的應用程式
description: 安裝和移除 MED-V 工作區上的應用程式
author: dansimp
ms.assetid: 24f32720-51ab-4385-adfe-4f5a65e45fdf
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 22cb98c167b53b1b206b8b5be2ba18fc0fba4f06
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812224"
---
# <span data-ttu-id="182f5-103">安裝和移除 MED-V 工作區上的應用程式</span><span class="sxs-lookup"><span data-stu-id="182f5-103">Installing and Removing an Application on the MED-V Workspace</span></span>


<span data-ttu-id="182f5-104">與主機作業系統不相容的應用程式可以在 med-v 工作區中執行，並在 MED-V 工作區中開啟，就與從主機電腦（在 [**開始**] 功能表上，或使用 localhost 快捷方式）中開啟的方式相同。</span><span class="sxs-lookup"><span data-stu-id="182f5-104">Applications that are incompatible with the host operating system can be run in the MED-V workspace and opened in the MED-V workspace in the same manner in which they are opened from the host computer, on the **Start** menu or by using a localhost shortcut.</span></span>

<span data-ttu-id="182f5-105">在您部署 MED-V 工作區之後，您有幾種不同的選項可供您在 MED-V 工作區中安裝及移除應用程式。</span><span class="sxs-lookup"><span data-stu-id="182f5-105">After you have deployed a MED-V workspace, you have several different options available to you for installing and removing applications in the MED-V workspace.</span></span> <span data-ttu-id="182f5-106">這些選項包括下列各項：</span><span class="sxs-lookup"><span data-stu-id="182f5-106">These options include the following:</span></span>

-   [<span data-ttu-id="182f5-107">使用群組原則</span><span class="sxs-lookup"><span data-stu-id="182f5-107">Using Group Policy</span></span>](#bkmk-grouppolicy)

-   [<span data-ttu-id="182f5-108">使用電子軟體發佈系統</span><span class="sxs-lookup"><span data-stu-id="182f5-108">Using an Electronic Software Distribution System</span></span>](#bkmk-esd)

-   [<span data-ttu-id="182f5-109">使用應用程式虛擬化（APP-V）</span><span class="sxs-lookup"><span data-stu-id="182f5-109">Using Application Virtualization (APP-V)</span></span>](#bkmk-appv)

-   [<span data-ttu-id="182f5-110">更新核心影像</span><span class="sxs-lookup"><span data-stu-id="182f5-110">Updating the Core Image</span></span>](#bkmk-coreimage)

<span data-ttu-id="182f5-111">**重要** 若要確保已安裝的應用程式會自動發佈到主機，請在虛擬機器上為**所有使用者**安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="182f5-111">**Important** To make sure that an installed application is automatically published to the host, install the application on the virtual machine for **All Users**.</span></span> <span data-ttu-id="182f5-112">如需應用程式發佈的詳細資訊，請參閱[如何在 Med-v 工作區發佈及取消發佈應用程式](how-to-publish-and-unpublish-an-application-on-the-med-v-workspace.md)。</span><span class="sxs-lookup"><span data-stu-id="182f5-112">For more information about application publishing, see [How to Publish and Unpublish an Application on the MED-V Workspace](how-to-publish-and-unpublish-an-application-on-the-med-v-workspace.md).</span></span>

 

<span data-ttu-id="182f5-113">**秘訣** MED-V 不支援進行內容處理的來賓對主機重新導向，例如在 MED-V 工作區中按兩下 Internet Explorer 中的 Microsoft Word 檔。</span><span class="sxs-lookup"><span data-stu-id="182f5-113">**Tip** MED-V does not support guest-to-host redirection for content handling, such as double-clicking a Microsoft Word document in Internet Explorer in the MED-V workspace.</span></span> <span data-ttu-id="182f5-114">因此，必須在 MED-V 工作區中安裝所需的應用程式（例如 Microsoft Word），才能提供最終使用者可能預期的預設內容處理功能。</span><span class="sxs-lookup"><span data-stu-id="182f5-114">Therefore, the required applications, such as Microsoft Word, must be installed in MED-V workspace to provide the default content handling functionality that an end user might expect.</span></span>

 

## <a href="" id="bkmk-grouppolicy"></a> <span data-ttu-id="182f5-115">使用群組原則新增及移除應用程式</span><span class="sxs-lookup"><span data-stu-id="182f5-115">Adding and Removing Applications by Using Group Policy</span></span>


<span data-ttu-id="182f5-116">您可以使用群組原則和群組原則物件，將應用程式指派或發佈至企業中的所有或一些 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="182f5-116">You can use Group Policy and Group Policy objects to assign or publish applications to all or some MED-V workspaces in your enterprise.</span></span> <span data-ttu-id="182f5-117">針對指派的應用程式，當使用者登入其電腦時，應用程式就會出現在 [**開始**] 功能表上。</span><span class="sxs-lookup"><span data-stu-id="182f5-117">For assigned applications, when an end user logs on to their computer, the application appears on the **Start** menu.</span></span> <span data-ttu-id="182f5-118">當他們第一次選取新的應用程式時，應用程式就會安裝並準備好使用。</span><span class="sxs-lookup"><span data-stu-id="182f5-118">When they select the new application for the first time, the application installs and is ready for use.</span></span> <span data-ttu-id="182f5-119">針對已發佈的應用程式，應用程式不會出現在 [**開始**] 功能表上。</span><span class="sxs-lookup"><span data-stu-id="182f5-119">For published applications, the application does not appear on the **Start** menu.</span></span> <span data-ttu-id="182f5-120">只有在使用者使用 [**控制台**] 中的 [**新增或移除程式**] 或開啟與應用程式相關聯的檔案時，才能安裝它。</span><span class="sxs-lookup"><span data-stu-id="182f5-120">It is only available for the end user to install by using **Add or Remove Programs** in **Control Panel** or by opening a file that is associated with the application.</span></span>

<span data-ttu-id="182f5-121">您也可以使用群組原則與群組原則物件，從 MED-V 工作區移除應用程式。</span><span class="sxs-lookup"><span data-stu-id="182f5-121">You can also use Group Policy and Group Policy objects in the same manner to remove applications from the MED-V workspace.</span></span>

<span data-ttu-id="182f5-122">如需如何使用 [群組原則] 新增及移除應用程式的詳細資訊，請參閱[群群組原則軟體安裝](https://go.microsoft.com/fwlink/?LinkId=195931)（ https://go.microsoft.com/fwlink/?LinkId=195931) 。</span><span class="sxs-lookup"><span data-stu-id="182f5-122">For more information about how to add and remove applications by using Group Policy, see [Group Policy Software Installation](https://go.microsoft.com/fwlink/?LinkId=195931) (https://go.microsoft.com/fwlink/?LinkId=195931).</span></span>

## <a href="" id="bkmk-esd"></a> <span data-ttu-id="182f5-123">使用 ESD 系統新增及移除應用程式</span><span class="sxs-lookup"><span data-stu-id="182f5-123">Adding and Removing Applications by Using an ESD System</span></span>


<span data-ttu-id="182f5-124">電子軟體發佈（ESD）系統設計為透過網路連線將軟體及其他資訊高效部署到許多不同的電腦。</span><span class="sxs-lookup"><span data-stu-id="182f5-124">An electronic software distribution (ESD) system is designed to efficiently deploy software and other information to many different computers over network connections.</span></span> <span data-ttu-id="182f5-125">如果您的組織使用 ESD 系統來部署軟體，您就可以使用它來新增和移除 MED-V 工作區上的應用程式，就像您在物理電腦上新增及移除應用程式一樣。</span><span class="sxs-lookup"><span data-stu-id="182f5-125">If your organization uses an ESD system to deploy software, you can use it to add and remove applications on MED-V workspaces just as you add and remove applications on physical computers.</span></span>

## <a href="" id="bkmk-appv"></a> <span data-ttu-id="182f5-126">使用 APP-V 新增及移除應用程式</span><span class="sxs-lookup"><span data-stu-id="182f5-126">Adding and Removing Applications by Using APP-V</span></span>


<span data-ttu-id="182f5-127">Microsoft Application Virtualization （App-v）提供系統管理功能，可讓使用者在不需直接在那些電腦上安裝應用程式的情況下，就能將應用程式提供給終端使用者的電腦。</span><span class="sxs-lookup"><span data-stu-id="182f5-127">Microsoft Application Virtualization (App-V) provides the administrative capability to make applications available to end-user computers without having to install the applications directly on those computers.</span></span> <span data-ttu-id="182f5-128">例如，如果您的組織有您在 Windows XP 中以 App-v 排序的應用程式，而您想要將它重新排序，則您可能會想要使用 MED-V 與 app-v，這樣就會延遲您的遷移到 Windows 7。</span><span class="sxs-lookup"><span data-stu-id="182f5-128">You might want to use MED-V and App-V together if, for example, your organization has applications that you sequenced with App-V in Windows XP, and re-sequencing them would delay your migration to Windows 7.</span></span>

<span data-ttu-id="182f5-129">您可以搭配 App-v 搭配使用 MED-V，在已部署的 MED-V 工作區上新增和移除虛擬應用程式。</span><span class="sxs-lookup"><span data-stu-id="182f5-129">You can use MED-V together with App-V to add and remove virtual applications on a deployed MED-V workspace.</span></span> <span data-ttu-id="182f5-130">若要以這種方式管理應用程式，您必須先在 MED-V 客體作業系統上安裝 App-v 代理程式。</span><span class="sxs-lookup"><span data-stu-id="182f5-130">To manage applications in this manner, you must first install the App-V agent on the MED-V guest operating system.</span></span> <span data-ttu-id="182f5-131">接著，您可以在 MED-V 工作區中使用 App-v 來新增和移除虛擬應用程式。</span><span class="sxs-lookup"><span data-stu-id="182f5-131">You can then use App-V in the MED-V workspace to add and remove the virtual applications.</span></span>

<span data-ttu-id="182f5-132">如需如何安裝及使用 App-v 的相關資訊，請參閱[應用程式虛擬化](https://go.microsoft.com/fwlink/?LinkId=122939)（ https://go.microsoft.com/fwlink/?LinkId=122939) 。</span><span class="sxs-lookup"><span data-stu-id="182f5-132">For information about how to install and use App-V, see [Application Virtualization](https://go.microsoft.com/fwlink/?LinkId=122939) (https://go.microsoft.com/fwlink/?LinkId=122939).</span></span>

<span data-ttu-id="182f5-133">**重要** 您發佈到 MED-V 工作區的 app-v 應用程式具有無法從主機電腦重新導向至來賓虛擬機器的檔案類型關聯性。</span><span class="sxs-lookup"><span data-stu-id="182f5-133">**Important** App-V applications that you publish to the MED-V workspace have file-type associations that cannot redirect from the host computer to the guest virtual machine.</span></span> <span data-ttu-id="182f5-134">不過，使用者仍然可以按一下 [檔案 **]，然後按一下 [** 在已發佈的 app-v 應用程式上**開啟**] 來存取這些檔案類型。</span><span class="sxs-lookup"><span data-stu-id="182f5-134">However, the end user can still access these file types by clicking **File**, and then by clicking **Open** on the published App-V application.</span></span>

<span data-ttu-id="182f5-135">若要強制重新導向這些檔案類型關聯，請在來賓虛擬機器的命令提示字元中輸入下列內容，以在來賓虛擬機器中的命令提示字元中輸入下列內容： **sftmime/QUERY OBJ： type**。</span><span class="sxs-lookup"><span data-stu-id="182f5-135">To force redirection of those file-type associations, query App-V for mapped file type associations by typing the following at a command prompt in the guest virtual machine: **sftmime /QUERY OBJ:TYPE**.</span></span> <span data-ttu-id="182f5-136">然後，在主機電腦中對應這些檔案類型關聯。</span><span class="sxs-lookup"><span data-stu-id="182f5-136">Then, map those file type associations in the host computer.</span></span>

 

## <a href="" id="bkmk-coreimage"></a> <span data-ttu-id="182f5-137">在核心影像上新增及移除應用程式</span><span class="sxs-lookup"><span data-stu-id="182f5-137">Adding and Removing Applications on the Core Image</span></span>


<span data-ttu-id="182f5-138">雖然不會被視為 MED-V 最佳做法，但您可以直接在核心影像上新增及移除應用程式。</span><span class="sxs-lookup"><span data-stu-id="182f5-138">Although not considered a MED-V best practice, you can add and remove applications directly on the core image.</span></span> <span data-ttu-id="182f5-139">在您新增或移除應用程式之後，您就可以將 MED-V 工作區重新部署到您的企業，就像當初部署它一樣。</span><span class="sxs-lookup"><span data-stu-id="182f5-139">After you have added or removed an application, you can redeploy the MED-V workspace back out to your enterprise just as you deployed it originally.</span></span>

<span data-ttu-id="182f5-140">如需如何在核心影像上新增或移除應用程式的詳細資訊，請參閱[在 Windows 虛擬電腦映射上安裝應用程式](installing-applications-on-a-windows-virtual-pc-image.md)。</span><span class="sxs-lookup"><span data-stu-id="182f5-140">For more information about how to add or remove applications on the core image, see [Installing Applications on a Windows Virtual PC Image](installing-applications-on-a-windows-virtual-pc-image.md).</span></span>

<span data-ttu-id="182f5-141">**重要** 我們不建議這個管理應用程式的方法。</span><span class="sxs-lookup"><span data-stu-id="182f5-141">**Important** We do not recommend this method of managing applications.</span></span> <span data-ttu-id="182f5-142">如果您新增或移除核心影像上的應用程式，然後重新部署 MED-V 工作區至您的企業，第一次必須再次執行安裝程式，而且儲存在虛擬機器上的任何資料都會遺失。</span><span class="sxs-lookup"><span data-stu-id="182f5-142">If you add or remove applications on the core image and redeploy the MED-V workspace back out to your enterprise, first time setup must run again, and any data saved on the virtual machine is lost.</span></span>

 

<span data-ttu-id="182f5-143">**記事** 即使應用程式已安裝在 MED-V 工作區中，您也可能還必須先發佈應用程式，才能供使用者使用。</span><span class="sxs-lookup"><span data-stu-id="182f5-143">**Note** Even though an application is installed into a MED-V workspace, you might also have to publish the application before it becomes available to the end user.</span></span> <span data-ttu-id="182f5-144">例如，如果安裝沒有在 [**開始**] 功能表上自動建立快捷方式，您可能必須發佈已安裝的應用程式。</span><span class="sxs-lookup"><span data-stu-id="182f5-144">For example, you might have to publish an installed application if the installation did not automatically create a shortcut on the **Start** menu.</span></span> <span data-ttu-id="182f5-145">同樣地，若要取消發佈應用程式，您可能必須手動移除 [**開始**] 功能表的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="182f5-145">Likewise, to unpublish an application, you might have to manually remove a shortcut from the **Start** menu.</span></span>

<span data-ttu-id="182f5-146">根據預設，大部分的應用程式會在安裝時發佈，在自動建立及啟用快捷方式時發佈。</span><span class="sxs-lookup"><span data-stu-id="182f5-146">By default, most applications are published at the time that they are installed, when shortcuts are automatically created and enabled.</span></span>

 

## <span data-ttu-id="182f5-147">相關主題</span><span class="sxs-lookup"><span data-stu-id="182f5-147">Related topics</span></span>


[<span data-ttu-id="182f5-148">如何測試應用程式發佈</span><span class="sxs-lookup"><span data-stu-id="182f5-148">How to Test Application Publishing</span></span>](how-to-test-application-publishing.md)

[<span data-ttu-id="182f5-149">如何發佈與取消發佈 MED-V 工作區上的應用程式</span><span class="sxs-lookup"><span data-stu-id="182f5-149">How to Publish and Unpublish an Application on the MED-V Workspace</span></span>](how-to-publish-and-unpublish-an-application-on-the-med-v-workspace.md)

 

 





