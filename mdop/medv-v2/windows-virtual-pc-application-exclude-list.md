---
title: Windows Virtual PC 應用程式排除清單
description: Windows Virtual PC 應用程式排除清單
author: dansimp
ms.assetid: 7715f198-f5ed-421e-8740-0cec2ca4ece3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 04/28/2017
ms.openlocfilehash: 190049ce99865ef237d8d26e14a8279def7da521
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810107"
---
# <span data-ttu-id="26179-103">Windows Virtual PC 應用程式排除清單</span><span class="sxs-lookup"><span data-stu-id="26179-103">Windows Virtual PC Application Exclude List</span></span>


<span data-ttu-id="26179-104">在某些情況下，您可能不想將 MED-V 工作區中安裝的應用程式發佈到主機電腦的 [**開始**] 功能表。</span><span class="sxs-lookup"><span data-stu-id="26179-104">In some instances, you might not want applications that are installed in the MED-V workspace to be published to the host computer **Start** menu.</span></span> <span data-ttu-id="26179-105">您可以按照指示在[Med-v 工作區中發佈及取消發佈應用程式](how-to-publish-and-unpublish-an-application-on-the-med-v-workspace.md)的指示，以取消發佈這些應用程式。</span><span class="sxs-lookup"><span data-stu-id="26179-105">You can unpublish these applications by following the instructions at [How to Publish and Unpublish an Application on the MED-V Workspace](how-to-publish-and-unpublish-an-application-on-the-med-v-workspace.md).</span></span> <span data-ttu-id="26179-106">不過，如果程式自動更新，也可能會自動重新發佈。</span><span class="sxs-lookup"><span data-stu-id="26179-106">However, if the program ever automatically updates, it might also be automatically republished.</span></span> <span data-ttu-id="26179-107">這會讓您再次取消發佈應用程式。</span><span class="sxs-lookup"><span data-stu-id="26179-107">This causes you to have to unpublish the application again.</span></span>

<span data-ttu-id="26179-108">Windows 虛擬電腦包含稱為「排除清單」的功能，可讓您指定一些您不想發佈到主機 [**開始**] 功能表的已安裝應用程式。</span><span class="sxs-lookup"><span data-stu-id="26179-108">Windows Virtual PC includes a feature known as the "Exclude List" that lets you specify certain installed applications that you do not want published to the host **Start** menu.</span></span> <span data-ttu-id="26179-109">[排除清單] 位於 HKLM\\Software\\Microsoft\\Windows NT\\CurrentVersion\\Virtual Machine\\VPCVAppExcludeList 金鑰中的來賓登錄，並列出那些未發佈至主機 [**開始**] 功能表的應用程式。</span><span class="sxs-lookup"><span data-stu-id="26179-109">The "Exclude List" is located in the guest registry in the HKLM\\Software\\Microsoft\\Windows NT\\CurrentVersion\\Virtual Machine\\VPCVAppExcludeList key and lists those applications that are not published to the host **Start** menu.</span></span> <span data-ttu-id="26179-110">您可以將「排除清單」視為永久取消發佈指定的應用程式，因為所列出之應用程式的任何自動更新將不會自動重新發佈。</span><span class="sxs-lookup"><span data-stu-id="26179-110">You can think of the “Exclude List” as permanently unpublishing the specified applications because any automatic updates to the applications that are listed will not cause them to be automatically republished.</span></span>

## <span data-ttu-id="26179-111">使用 Windows 虛擬電腦中的排除清單管理應用程式</span><span class="sxs-lookup"><span data-stu-id="26179-111">Managing Applications by Using the Exclude List in Windows Virtual PC</span></span>


****

1.  <span data-ttu-id="26179-112">以全螢幕開啟 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="26179-112">Open the MED-V workspace in full screen.</span></span>

    <span data-ttu-id="26179-113">如需使用 MED-V 管理工具組以全螢幕模式開啟 MED-V 工作區的相關資訊，請參閱[查看 Med-v 工作區](viewing-med-v-workspace-configurations.md#bkmk-fullscreen)設定。</span><span class="sxs-lookup"><span data-stu-id="26179-113">For information about opening the MED-V workspace in full-screen mode by using the MED-V Administration Toolkit, see [Viewing MED-V Workspace Configurations](viewing-med-v-workspace-configurations.md#bkmk-fullscreen).</span></span> <span data-ttu-id="26179-114">或者，您可以按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **windows 虛擬電腦**]，按一下 [ **WINDOWS 虛擬電腦**]，然後按兩下 med-v 工作區，以全螢幕方式手動開啟。</span><span class="sxs-lookup"><span data-stu-id="26179-114">Or you can manually open it in full screen by clicking **Start**, click **All Programs**, click **Windows Virtual PC**, click **Windows Virtual PC**, and then double-click the MED-V workspace.</span></span>

2.  <span data-ttu-id="26179-115">在 MED-V 工作區 Windows 虛擬電腦視窗中，開啟 [登錄編輯程式]。</span><span class="sxs-lookup"><span data-stu-id="26179-115">In the MED-V workspace Windows Virtual PC window, open Registry Editor.</span></span>

    <span data-ttu-id="26179-116">按一下 [**開始**]，按一下 [**執行**]，然後輸入 regedit。</span><span class="sxs-lookup"><span data-stu-id="26179-116">Click **Start**, click **Run**, and then type regedit.</span></span> <span data-ttu-id="26179-117">然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="26179-117">Then click **OK**.</span></span>

3.  <span data-ttu-id="26179-118">在 [登錄編輯程式] 中，找出 HKLM\\Software\\Microsoft\\Windows NT\\CurrentVersion\\Virtual Machine\\VPCVAppExcludeList 登錄機碼。</span><span class="sxs-lookup"><span data-stu-id="26179-118">In Registry Editor, locate the HKLM\\Software\\Microsoft\\Windows NT\\CurrentVersion\\Virtual Machine\\VPCVAppExcludeList registry key.</span></span>

4.  <span data-ttu-id="26179-119">針對您不想將其發佈到主機電腦 [**開始**] 功能表的已安裝應用程式，建立新的登錄值。</span><span class="sxs-lookup"><span data-stu-id="26179-119">Create a new registry value for the installed application that you do not want published to the host computer **Start** menu.</span></span> <span data-ttu-id="26179-120">例如，如果您想要取消發佈自動發佈的程式 Microsoft Silverlight，請遵循下列步驟：</span><span class="sxs-lookup"><span data-stu-id="26179-120">For example, if you want to unpublish the automatically published program Microsoft Silverlight, follow these steps:</span></span>

    1.  <span data-ttu-id="26179-121">在 VPCVAppExcludeList 登錄機碼醒目提示時，按一下 [**編輯**]，按一下 [**新增**]，然後按一下 [**字串值**]。</span><span class="sxs-lookup"><span data-stu-id="26179-121">With the VPCVAppExcludeList registry key highlighted, click **Edit**, click **New**, and then click **String Value**.</span></span>

    2.  <span data-ttu-id="26179-122">輸入新註冊值的名稱。</span><span class="sxs-lookup"><span data-stu-id="26179-122">Enter the name for the new registry value.</span></span> <span data-ttu-id="26179-123">例如，在 Microsoft Silverlight 中，您可以輸入 sllauncher.exe。</span><span class="sxs-lookup"><span data-stu-id="26179-123">For example, for Microsoft Silverlight, you might enter sllauncher.exe.</span></span>

    3.  <span data-ttu-id="26179-124">按兩下新的註冊表值，然後輸入值資料。</span><span class="sxs-lookup"><span data-stu-id="26179-124">Double-click the new registry value and enter the value data.</span></span>

        <span data-ttu-id="26179-125">[值資料] 是您要取消發佈之命令的完整路徑。</span><span class="sxs-lookup"><span data-stu-id="26179-125">The value data is the full path for the command that you want to unpublish.</span></span> <span data-ttu-id="26179-126">您可以在不想要發行之應用程式的 [**開始**] 功能表上，以滑鼠右鍵按一下快捷方式，然後按一下 [**屬性**]，找到完整路徑。</span><span class="sxs-lookup"><span data-stu-id="26179-126">You can find the full path by right-clicking on the shortcut on the **Start** menu for the application that you do not want published and then clicking **Properties**.</span></span> <span data-ttu-id="26179-127">完整路徑會列于 [**目標**] 底下的 [**快捷方式**] 索引標籤中。</span><span class="sxs-lookup"><span data-stu-id="26179-127">The full path is listed in the **Shortcut** tab under **Target**.</span></span>

        <span data-ttu-id="26179-128">例如，對於程式 Microsoft Silverlight，完整路徑可能是「C:\\program files Files\\Microsoft Silverlight\\4.0.50917.0\\Silverlight.Configuration.exe」。</span><span class="sxs-lookup"><span data-stu-id="26179-128">For example, for the program Microsoft Silverlight, the full path might be "C:\\Program Files\\Microsoft Silverlight\\4.0.50917.0\\Silverlight.Configuration.exe."</span></span>

        <span data-ttu-id="26179-129">**重要** 如果適用的話，請在 [值資料] 欄位中，移除完整路徑中的引號。</span><span class="sxs-lookup"><span data-stu-id="26179-129">**Important** If applicable, remove the quotation marks from the full path when you enter it into the value data field.</span></span>

         

5.  <span data-ttu-id="26179-130">關閉 [登錄編輯程式]，然後重新開機 MED-V 工作區虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="26179-130">Close Registry Editor and restart the MED-V workspace virtual machine.</span></span>

    <span data-ttu-id="26179-131">應用程式仍安裝在 MED-V 工作區中，但現在已從主機電腦的 [**開始**] 功能表中移除。</span><span class="sxs-lookup"><span data-stu-id="26179-131">The application is still installed in the MED-V workspace but is now removed from the host computer **Start** menu.</span></span>

<span data-ttu-id="26179-132">您也可以從 VPCVAppExcludeList 鍵中刪除對應的值，將排除的應用程式重新發佈至主機 [**開始**] 功能表。</span><span class="sxs-lookup"><span data-stu-id="26179-132">You can also republish an excluded application to the host **Start** menu by deleting the corresponding value from the VPCVAppExcludeList key.</span></span> <span data-ttu-id="26179-133">例如，若要重新發佈 Microsoft Silverlight，請以滑鼠右鍵按一下註冊表值 sllauncher.exe 然後選取 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="26179-133">For example, to republish Microsoft Silverlight, right-click the registry value sllauncher.exe and select **Delete**.</span></span>

## <span data-ttu-id="26179-134">相關主題</span><span class="sxs-lookup"><span data-stu-id="26179-134">Related topics</span></span>


[<span data-ttu-id="26179-135">MED-V 技術參考資料</span><span class="sxs-lookup"><span data-stu-id="26179-135">Technical Reference for MED-V</span></span>](technical-reference-for-med-v.md)

[<span data-ttu-id="26179-136">如何發佈與取消發佈 MED-V 工作區上的應用程式</span><span class="sxs-lookup"><span data-stu-id="26179-136">How to Publish and Unpublish an Application on the MED-V Workspace</span></span>](how-to-publish-and-unpublish-an-application-on-the-med-v-workspace.md)

 

 





