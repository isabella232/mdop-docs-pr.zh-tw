---
title: 如何使用 Management Console 檢視及設定應用程式與預設虛擬應用程式延伸模組
description: 如何使用 Management Console 檢視及設定應用程式與預設虛擬應用程式延伸模組
author: dansimp
ms.assetid: c77e6662-7a18-4da1-8da8-b58068b65fa1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c5a8cd5c914d1ddd720ebfef318e3a094cdc6f0b
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800389"
---
# <span data-ttu-id="50acf-103">如何使用 Management Console 檢視及設定應用程式與預設虛擬應用程式延伸模組</span><span class="sxs-lookup"><span data-stu-id="50acf-103">How to View and Configure Applications and Default Virtual Application Extensions by Using the Management Console</span></span>


<span data-ttu-id="50acf-104">使用下列程式來查看和設定預設套件延伸。</span><span class="sxs-lookup"><span data-stu-id="50acf-104">Use the following procedure to view and configure default package extensions.</span></span>

**<span data-ttu-id="50acf-105">若要查看和設定預設的虛擬應用程式擴充功能</span><span class="sxs-lookup"><span data-stu-id="50acf-105">To view and configure default virtual application extensions</span></span>**

1.  <span data-ttu-id="50acf-106">若要查看您要設定的套件，請開啟 App-V 5.0 管理主控台。</span><span class="sxs-lookup"><span data-stu-id="50acf-106">To view the package that you want to configure, open the App-V 5.0 Management Console.</span></span> <span data-ttu-id="50acf-107">選取您要設定的套件，以滑鼠右鍵按一下套件名稱，然後選取 [**編輯預設**設定]。</span><span class="sxs-lookup"><span data-stu-id="50acf-107">Select the package that you want to configure, right-click the package name and select **edit default configuration**.</span></span>

2.  <span data-ttu-id="50acf-108">若要查看包含在指定套件中的應用程式，請在 [**預設**設定] 窗格中按一下 [**應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="50acf-108">To view the applications contained in the specified package, in the **Default Configuration** pane, click **Applications**.</span></span> <span data-ttu-id="50acf-109">若要查看該套件的快捷方式，請按一下 [**快速鍵**]。</span><span class="sxs-lookup"><span data-stu-id="50acf-109">To view the shortcuts for that package, click **Shortcuts**.</span></span> <span data-ttu-id="50acf-110">若要查看該套件的檔案類型關聯，請按一下 [**檔案類型**]。</span><span class="sxs-lookup"><span data-stu-id="50acf-110">To view the file type associations for that package, click **File Types**.</span></span>

3.  <span data-ttu-id="50acf-111">若要啟用應用程式延伸，請選取 [**啟用**]。</span><span class="sxs-lookup"><span data-stu-id="50acf-111">To enable the application extensions, select **ENABLE**.</span></span>

    <span data-ttu-id="50acf-112">若要啟用快速鍵，請選取 [**啟用快速鍵**]。</span><span class="sxs-lookup"><span data-stu-id="50acf-112">To enable shortcuts, select **ENABLE SHORTCUTS**.</span></span> <span data-ttu-id="50acf-113">若要為所選取的應用程式新增快速鍵，請在 [**快捷方式**] 窗格中以滑鼠右鍵按一下該應用程式，然後選取 [**新增快捷方式**]。</span><span class="sxs-lookup"><span data-stu-id="50acf-113">To add a new shortcut for the selected application, right-click the application in the **SHORTCUTS** pane and select **Add new shortcut**.</span></span> <span data-ttu-id="50acf-114">若要移除快速鍵，請在 [**快捷方式**] 窗格中以滑鼠右鍵按一下應用程式，然後選取 [**移除快捷方式**]。</span><span class="sxs-lookup"><span data-stu-id="50acf-114">To remove a shortcut, right-click the application in the **SHORTCUTS** pane and select **Remove Shortcut**.</span></span> <span data-ttu-id="50acf-115">若要編輯現有的快捷方式，請以滑鼠右鍵按一下該應用程式，然後選取 [**編輯快捷方式**]。</span><span class="sxs-lookup"><span data-stu-id="50acf-115">To edit an existing shortcut, right-click the application and select **Edit Shortcut**.</span></span>

4.  <span data-ttu-id="50acf-116">若要查看任何其他應用程式延伸，請按一下 [**高級**]，然後按一下 [**匯出配置**]。</span><span class="sxs-lookup"><span data-stu-id="50acf-116">To view any other application extensions, click **Advanced** and click **Export Configuration**.</span></span> <span data-ttu-id="50acf-117">輸入檔案名，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="50acf-117">Type in a filename and click **Save**.</span></span> <span data-ttu-id="50acf-118">您可以使用設定檔來查看與套件相關聯的所有應用程式擴充功能。</span><span class="sxs-lookup"><span data-stu-id="50acf-118">You can view all application extensions associated with the package using the configuration file.</span></span>

5.  <span data-ttu-id="50acf-119">若要編輯其他應用程式延伸，請修改設定檔，然後按一下 [匯**入並覆寫此**設定]。</span><span class="sxs-lookup"><span data-stu-id="50acf-119">To edit other application extensions, modify the configuration file and click **Import and Overwrite this Configuration**.</span></span> <span data-ttu-id="50acf-120">選取已修改的檔案，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="50acf-120">Select the modified file and click **Open**.</span></span> <span data-ttu-id="50acf-121">在對話方塊中，按一下 [**覆寫**] 以完成處理常式。</span><span class="sxs-lookup"><span data-stu-id="50acf-121">In the dialog box, click **Overwrite** to complete the process.</span></span>

    <span data-ttu-id="50acf-122">您**有應用程式-V 的建議**嗎？</span><span class="sxs-lookup"><span data-stu-id="50acf-122">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="50acf-123">在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="50acf-123">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="50acf-124">有應用程式-V 問題嗎？</span><span class="sxs-lookup"><span data-stu-id="50acf-124">Got an App-V issue?</span></span>** <span data-ttu-id="50acf-125">使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="50acf-125">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="50acf-126">相關主題</span><span class="sxs-lookup"><span data-stu-id="50acf-126">Related topics</span></span>


[<span data-ttu-id="50acf-127">App-V 5.0 作業</span><span class="sxs-lookup"><span data-stu-id="50acf-127">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

 

 





