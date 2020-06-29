---
title: 如何發佈與取消發佈 MED-V 工作區上的應用程式
description: 如何發佈與取消發佈 MED-V 工作區上的應用程式
author: dansimp
ms.assetid: fd5a62e9-0577-44d2-ae17-61c0aef78ce8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cc8f9579d800aa0e5da0d67e0cd71bcae5e912a0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812045"
---
# <span data-ttu-id="aa2da-103">如何發佈與取消發佈 MED-V 工作區上的應用程式</span><span class="sxs-lookup"><span data-stu-id="aa2da-103">How to Publish and Unpublish an Application on the MED-V Workspace</span></span>


<span data-ttu-id="aa2da-104">即使應用程式已安裝在 MED-V 工作區中，您也可能還必須先發佈應用程式，才能供使用者使用。</span><span class="sxs-lookup"><span data-stu-id="aa2da-104">Even though an application is installed in a MED-V workspace, you might also have to publish the application before it becomes available to the end user.</span></span> <span data-ttu-id="aa2da-105">根據預設，大部分的應用程式會在安裝時發佈，並建立並啟用快速鍵。</span><span class="sxs-lookup"><span data-stu-id="aa2da-105">By default, most applications are published at the time that they are installed and shortcuts are created and enabled.</span></span>

<span data-ttu-id="aa2da-106">在某些情況下，您可能會想要在 MED-V 工作區上安裝應用程式，而不讓最終使用者使用，例如病毒掃描軟體。</span><span class="sxs-lookup"><span data-stu-id="aa2da-106">In some cases, you might want to install applications on the MED-V workspace without making them available to the end user, for example, virus-scanning software.</span></span> <span data-ttu-id="aa2da-107">同樣地，您還是想要發佈的應用程式是已安裝在由使用者先前無法使用的 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="aa2da-107">Similarly, there are occasions in which you want to publish an application that is installed on the MED-V workspace that was previously unavailable to the end user.</span></span> <span data-ttu-id="aa2da-108">例如，如果安裝沒有在 [**開始**] 功能表上自動建立快捷方式，您可能必須發佈已安裝的應用程式。</span><span class="sxs-lookup"><span data-stu-id="aa2da-108">For example, you might have to publish an installed application if the installation did not automatically create a shortcut on the **Start** menu.</span></span>

<span data-ttu-id="aa2da-109">**重要** 如果您發佈的應用程式不支援 UNC 路徑，我們建議您將應用程式對應至磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="aa2da-109">**Important** If you publish an application that does not support UNC paths, we recommend that you map the application to a drive.</span></span>

 

<span data-ttu-id="aa2da-110">您可以執行下列其中一項任務，將應用程式發佈或取消發佈到已部署的 MED-V 工作區：</span><span class="sxs-lookup"><span data-stu-id="aa2da-110">You can publish or unpublish applications to a deployed MED-V workspace by performing one of the following tasks:</span></span>

**<span data-ttu-id="aa2da-111">發佈或取消發佈已安裝的應用程式</span><span class="sxs-lookup"><span data-stu-id="aa2da-111">To publish or unpublish an installed application</span></span>**

1.  <span data-ttu-id="aa2da-112">若要在已部署的 MED-V 工作區發佈應用程式，請將該應用程式的快捷方式複製到虛擬機器上的下列資料夾：</span><span class="sxs-lookup"><span data-stu-id="aa2da-112">To publish an application on a deployed MED-V workspace, copy a shortcut for that application to the following folder on the virtual machine:</span></span>

    <span data-ttu-id="aa2da-113">[C:\\Documents] 和 [Settings\\All Users\\Start] 功能表</span><span class="sxs-lookup"><span data-stu-id="aa2da-113">C:\\Documents and Settings\\All Users\\Start Menu</span></span>

    <span data-ttu-id="aa2da-114">如有需要，請使用 [群組原則] 或 [ESD 系統] 來部署腳本，將該應用程式的快捷方式複製到 [全部 Users\\Start] 功能表資料夾中。</span><span class="sxs-lookup"><span data-stu-id="aa2da-114">If it is necessary, use Group Policy or an ESD system to deploy a script that copies the shortcut for that application to the All Users\\Start Menu folder.</span></span>

2.  <span data-ttu-id="aa2da-115">若要在已部署的 MED-V 工作區上取消發佈應用程式，請從虛擬機器上的下列資料夾中刪除該應用程式的快捷方式：</span><span class="sxs-lookup"><span data-stu-id="aa2da-115">To unpublish an application on a deployed MED-V workspace, delete the shortcut for that application from the following folder on the virtual machine:</span></span>

    <span data-ttu-id="aa2da-116">[C:\\Documents] 和 [Settings\\All Users\\Start] 功能表</span><span class="sxs-lookup"><span data-stu-id="aa2da-116">C:\\Documents and Settings\\All Users\\Start Menu</span></span>

    <span data-ttu-id="aa2da-117">如有需要，請使用 [群組原則] 或 [ESD 系統] 來部署腳本，從 [所有 Users\\Start] 功能表資料夾中刪除該應用程式的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="aa2da-117">If it is necessary, use Group Policy or an ESD system to deploy a script that deletes the shortcut for that application from the All Users\\Start Menu folder.</span></span>

    <span data-ttu-id="aa2da-118">**記事** 在您卸載應用程式時，會經常從主機電腦的 [**開始**] 功能表刪除快捷方式。</span><span class="sxs-lookup"><span data-stu-id="aa2da-118">**Note** Frequently, the shortcut is automatically deleted from the host computer **Start** menu when you uninstall the application.</span></span> <span data-ttu-id="aa2da-119">不過，在某些情況下（例如針對共用電腦的所有使用者所設定的 MED-V 工作區），您可能必須在卸載應用程式後，手動刪除 [**開始**] 功能表上的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="aa2da-119">However, in some cases, such as for a MED-V workspace that is configured for all users of a shared computer, you might have to manually delete the shortcut on the **Start** menu after the application is uninstalled.</span></span> <span data-ttu-id="aa2da-120">最終使用者可以用滑鼠右鍵按一下快捷方式，然後選取 [**刪除**] 來執行此動作。</span><span class="sxs-lookup"><span data-stu-id="aa2da-120">The end-user can do this by right-clicking the shortcut and selecting **Delete**.</span></span>

     

<span data-ttu-id="aa2da-121">若要測試應用程式是否已發佈或未發佈，請在 MED-V 工作區中驗證是否有對應的快速鍵可供使用。</span><span class="sxs-lookup"><span data-stu-id="aa2da-121">To test that the application was published or unpublished, verify on the MED-V workspace whether the corresponding shortcut is available or not.</span></span>

<span data-ttu-id="aa2da-122">**記事** Windows XP SP3 中包含且位於 [虛擬機器開始] 功能表資料夾中的應用程式不會自動發佈到主機。</span><span class="sxs-lookup"><span data-stu-id="aa2da-122">**Note** Applications that are included in Windows XP SP3 and are located in the virtual machine Start Menu folder are not automatically published to the host.</span></span> <span data-ttu-id="aa2da-123">它們是由封鎖自動發佈的註冊表設定所控制。</span><span class="sxs-lookup"><span data-stu-id="aa2da-123">They are controlled by registry settings that block automatic publishing.</span></span> <span data-ttu-id="aa2da-124">如需詳細資訊，請參閱[Windows 虛擬電腦應用程式排除清單](windows-virtual-pc-application-exclude-list.md)。</span><span class="sxs-lookup"><span data-stu-id="aa2da-124">For more information, see [Windows Virtual PC Application Exclude List](windows-virtual-pc-application-exclude-list.md).</span></span>

 

**<span data-ttu-id="aa2da-125">發佈 [控制台] 專案</span><span class="sxs-lookup"><span data-stu-id="aa2da-125">To publish Control Panel items</span></span>**

1.  <span data-ttu-id="aa2da-126">在目標為專案名稱的虛擬機器上建立快捷方式，例如 [C:\\WINDOWS\\system32\\appwiz.cpl]。</span><span class="sxs-lookup"><span data-stu-id="aa2da-126">Create a shortcut on the virtual machine where the target is the name of the item, such as C:\\WINDOWS\\system32\\appwiz.cpl.</span></span>

    <span data-ttu-id="aa2da-127">快捷方式必須在 [%ALLUSERSPROFILE%\\Start Menu\\] 資料夾或其中一個子資料夾中建立或移至它。</span><span class="sxs-lookup"><span data-stu-id="aa2da-127">The shortcut must be either created in or moved to the "%ALLUSERSPROFILE%\\Start Menu\\" folder or one of its subfolders.</span></span>

    <span data-ttu-id="aa2da-128">該專案將會發佈到主機 [開始] 功能表資料夾中相對應位置的主機電腦。</span><span class="sxs-lookup"><span data-stu-id="aa2da-128">The item will be published to the host computer in the corresponding location in the host Start Menu folder.</span></span>

2.  <span data-ttu-id="aa2da-129">在主機中啟動專案的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="aa2da-129">Start the shortcut for the item in the host.</span></span>

<span data-ttu-id="aa2da-130">**小心** 當您建立快捷方式時，請不要指定% SystemRoot% \\control.exe。</span><span class="sxs-lookup"><span data-stu-id="aa2da-130">**Caution** When you create the shortcut, do not specify %SystemRoot%\\control.exe.</span></span> <span data-ttu-id="aa2da-131">此應用程式將不會發佈，因為它包含在封鎖自動發佈的註冊表設定中。</span><span class="sxs-lookup"><span data-stu-id="aa2da-131">This application will not be published because it is contained in the registry settings that block automatic publishing.</span></span>

 

**<span data-ttu-id="aa2da-132">MED-V 如何處理自動應用程式發佈</span><span class="sxs-lookup"><span data-stu-id="aa2da-132">How MED-V handles automatic application publishing</span></span>**

1.  <span data-ttu-id="aa2da-133">在應用程式發佈期間，MED-V 會嘗試與來賓中存在的資料夾階層相符，以將來賓虛擬機器的快速鍵複製到主機電腦。</span><span class="sxs-lookup"><span data-stu-id="aa2da-133">During application publishing, MED-V copies the shortcuts from the guest virtual machine to the host computer by trying to match the folder hierarchy that exists in the guest.</span></span> <span data-ttu-id="aa2da-134">如此一來，MED-V 會按照下列步驟，將來賓的快速鍵複製到主機：</span><span class="sxs-lookup"><span data-stu-id="aa2da-134">By doing this, MED-V copies shortcuts from the guest to the host by following these steps:</span></span>

    1.  <span data-ttu-id="aa2da-135">MED-V 會嘗試在名為「開始 Menu\\Programs」的主機電腦中，找到與快捷方式所在之來賓中的資料夾相同的資料夾。</span><span class="sxs-lookup"><span data-stu-id="aa2da-135">MED-V tries to locate a folder under Start Menu\\Programs in the host computer that is named the same as the folder in the guest where the shortcut resides.</span></span>

    2.  <span data-ttu-id="aa2da-136">如果沒有相符的資料夾，MED-V 會嘗試在主機 [開始] 功能表資料夾中找出名稱與快捷方式所在之來賓中的資料夾相同的資料夾。</span><span class="sxs-lookup"><span data-stu-id="aa2da-136">If there is no matching folder, MED-V then tries to locate a folder in the host Start Menu folder that is named the same as the folder in the guest where the shortcut resides.</span></span>

    3.  <span data-ttu-id="aa2da-137">如果沒有相符的資料夾，MED-V 會將快捷方式複製到主機上的預設資料夾，即 [開始 Menu\\Programs] 資料夾。</span><span class="sxs-lookup"><span data-stu-id="aa2da-137">If there is no matching folder, MED-V copies the shortcut to the default folder on the host, the Start Menu\\Programs folder.</span></span>

2.  <span data-ttu-id="aa2da-138">應用程式發佈程式範例：</span><span class="sxs-lookup"><span data-stu-id="aa2da-138">Example of application publishing process:</span></span>

    1.  <span data-ttu-id="aa2da-139">如果應用程式快捷方式發佈至來賓中的 [開始 Menu\\Programs\\AppShortcuts] 資料夾，則 MED-V 會在主機電腦中尋找 [開始 Menu\\Programs\\ AppShortcuts] 資料夾，如果找到，就會將快捷方式複製到該資料夾。</span><span class="sxs-lookup"><span data-stu-id="aa2da-139">If an application shortcut is published to the Start Menu\\Programs\\AppShortcuts folder in the guest, then MED-V looks in the host computer for a Start Menu\\Programs\\ AppShortcuts folder and if found, copies the shortcut to that folder.</span></span>

    2.  <span data-ttu-id="aa2da-140">如果找不到資料夾，則 MED-V 會在主機電腦中尋找開始 Menu\\AppShortcuts 資料夾，如果有找到，就會將快捷方式複製到該資料夾。</span><span class="sxs-lookup"><span data-stu-id="aa2da-140">If the folder is not found, then MED-V looks in the host computer for a Start Menu\\AppShortcuts folder and if found, copies the shortcut to that folder.</span></span>

    3.  <span data-ttu-id="aa2da-141">如果找不到資料夾，則 MED-V 會將快捷方式複製到 [開始] Menu\\Programs 資料夾。</span><span class="sxs-lookup"><span data-stu-id="aa2da-141">If the folder is not found, then MED-V copies the shortcut to the Start Menu\\Programs folder.</span></span>

<span data-ttu-id="aa2da-142">**記事** 該資料夾必須已經存在於 MED-V 中的主機電腦的 [開始] 功能表資料夾中，才能複製快捷方式。</span><span class="sxs-lookup"><span data-stu-id="aa2da-142">**Note** A folder must already exist in the host computer Start Menu folder for MED-V to copy the shortcut there.</span></span> <span data-ttu-id="aa2da-143">如果資料夾不存在，MED-V 就不會建立該資料夾。</span><span class="sxs-lookup"><span data-stu-id="aa2da-143">MED-V does not create the folder if it does not already exist.</span></span>

 

## <span data-ttu-id="aa2da-144">相關主題</span><span class="sxs-lookup"><span data-stu-id="aa2da-144">Related topics</span></span>


[<span data-ttu-id="aa2da-145">安裝和移除 MED-V 工作區上的應用程式</span><span class="sxs-lookup"><span data-stu-id="aa2da-145">Installing and Removing an Application on the MED-V Workspace</span></span>](installing-and-removing-an-application-on-the-med-v-workspace.md)

[<span data-ttu-id="aa2da-146">管理 MED-V 工作區的軟體更新</span><span class="sxs-lookup"><span data-stu-id="aa2da-146">Managing Software Updates for MED-V Workspaces</span></span>](managing-software-updates-for-med-v-workspaces.md)

[<span data-ttu-id="aa2da-147">Windows Virtual PC 應用程式排除清單</span><span class="sxs-lookup"><span data-stu-id="aa2da-147">Windows Virtual PC Application Exclude List</span></span>](windows-virtual-pc-application-exclude-list.md)

 

 





