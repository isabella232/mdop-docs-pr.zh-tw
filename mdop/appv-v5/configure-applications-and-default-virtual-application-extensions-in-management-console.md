---
title: 在管理主控台中設定應用程式和預設虛擬應用程式延伸模組
description: 如何使用 Management Console 檢視及設定應用程式與預設虛擬應用程式延伸模組
author: dansimp
ms.assetid: 1e1941d3-fb22-4077-8ec6-7a0cb80335d8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 09/26/2019
ms.openlocfilehash: 7c29ba0e40cf1adbc2b2297124cfb245a65a7ffe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800660"
---
#   <span data-ttu-id="b6b55-103">在管理主控台中設定應用程式和預設虛擬應用程式延伸模組</span><span class="sxs-lookup"><span data-stu-id="b6b55-103">Configure Applications and Default Virtual Application Extensions in Management Console</span></span>

<span data-ttu-id="b6b55-104">使用下列程式來*查看*和*設定*預設套件延伸。</span><span class="sxs-lookup"><span data-stu-id="b6b55-104">Use the following procedure to *view* and *configure* default package extensions.</span></span>

**<span data-ttu-id="b6b55-105">若要查看和設定預設的虛擬應用程式擴充功能</span><span class="sxs-lookup"><span data-stu-id="b6b55-105">To view and configure default virtual application extensions</span></span>**

1.  <span data-ttu-id="b6b55-106">若要查看您要設定的套件，請開啟 App-V 5.1 管理主控台。</span><span class="sxs-lookup"><span data-stu-id="b6b55-106">To view the package that you want to configure, open the App-V 5.1 Management Console.</span></span> <span data-ttu-id="b6b55-107">選取您要設定的套件，以滑鼠右鍵按一下套件名稱，然後選取 [**編輯預設**設定]。</span><span class="sxs-lookup"><span data-stu-id="b6b55-107">Select the package that you want to configure, right-click the package name and select **edit default configuration**.</span></span>

2.  <span data-ttu-id="b6b55-108">若要查看包含在指定套件中的應用程式，請在 [**預設**設定] 窗格中按一下 [**應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="b6b55-108">To view the applications contained in the specified package, in the **Default Configuration** pane, click **Applications**.</span></span> <span data-ttu-id="b6b55-109">若要查看該套件的快捷方式，請按一下 [**快速鍵**]。</span><span class="sxs-lookup"><span data-stu-id="b6b55-109">To view the shortcuts for that package, click **Shortcuts**.</span></span> <span data-ttu-id="b6b55-110">若要查看該套件的檔案類型關聯，請按一下 [**檔案類型**]。</span><span class="sxs-lookup"><span data-stu-id="b6b55-110">To view the file type associations for that package, click **File Types**.</span></span>

3.  <span data-ttu-id="b6b55-111">若要啟用應用程式延伸，請選取 [**啟用**]。</span><span class="sxs-lookup"><span data-stu-id="b6b55-111">To enable the application extensions, select **ENABLE**.</span></span>

    <span data-ttu-id="b6b55-112">若要啟用快速鍵，請選取 [**啟用快速鍵**]。</span><span class="sxs-lookup"><span data-stu-id="b6b55-112">To enable shortcuts, select **ENABLE SHORTCUTS**.</span></span> <span data-ttu-id="b6b55-113">若要為所選取的應用程式新增快速鍵，請在 [**快捷方式**] 窗格中以滑鼠右鍵按一下該應用程式，然後選取 [**新增快捷方式**]。</span><span class="sxs-lookup"><span data-stu-id="b6b55-113">To add a new shortcut for the selected application, right-click the application in the **SHORTCUTS** pane and select **Add new shortcut**.</span></span> <span data-ttu-id="b6b55-114">若要移除快速鍵，請在 [**快捷方式**] 窗格中以滑鼠右鍵按一下應用程式，然後選取 [**移除快捷方式**]。</span><span class="sxs-lookup"><span data-stu-id="b6b55-114">To remove a shortcut, right-click the application in the **SHORTCUTS** pane and select **Remove Shortcut**.</span></span> <span data-ttu-id="b6b55-115">若要編輯現有的快捷方式，請以滑鼠右鍵按一下該應用程式，然後選取 [**編輯快捷方式**]。</span><span class="sxs-lookup"><span data-stu-id="b6b55-115">To edit an existing shortcut, right-click the application and select **Edit Shortcut**.</span></span>

4.  <span data-ttu-id="b6b55-116">若要查看任何其他應用程式延伸，請按一下 [**高級**]，然後按一下 [**匯出配置**]。</span><span class="sxs-lookup"><span data-stu-id="b6b55-116">To view any other application extensions, click **Advanced** and click **Export Configuration**.</span></span> <span data-ttu-id="b6b55-117">輸入檔案名，然後按一下 [**儲存**]。</span><span class="sxs-lookup"><span data-stu-id="b6b55-117">Type in a filename and click **Save**.</span></span> <span data-ttu-id="b6b55-118">您可以使用設定檔來查看與套件相關聯的所有應用程式擴充功能。</span><span class="sxs-lookup"><span data-stu-id="b6b55-118">You can view all application extensions associated with the package using the configuration file.</span></span>

5.  <span data-ttu-id="b6b55-119">若要編輯其他應用程式延伸，請修改設定檔，然後按一下 [匯**入並覆寫此**設定]。</span><span class="sxs-lookup"><span data-stu-id="b6b55-119">To edit other application extensions, modify the configuration file and click **Import and Overwrite this Configuration**.</span></span> <span data-ttu-id="b6b55-120">選取已修改的檔案，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="b6b55-120">Select the modified file and click **Open**.</span></span> <span data-ttu-id="b6b55-121">在對話方塊中，按一下 [**覆寫**] 以完成處理常式。</span><span class="sxs-lookup"><span data-stu-id="b6b55-121">In the dialog box, click **Overwrite** to complete the process.</span></span>

><span data-ttu-id="b6b55-122">**記事**如果上傳失敗且您的配置檔案大小超過4MB，您將需要增加伺服器所允許的最大檔案大小。</span><span class="sxs-lookup"><span data-stu-id="b6b55-122">**Note** If the upload fails and the size of your configuration file is above 4MB, you will need to increase the maximum file size allowed by the server.</span></span> <span data-ttu-id="b6b55-123">若要完成此動作，您可以將 maxRequestLength 屬性加上大於您配置檔案大小（KB）的值加到的 HTTPRuntime 元素 `C:\Program Files\Microsoft Application Virtualization Server\ManagementService\Web.config` 。</span><span class="sxs-lookup"><span data-stu-id="b6b55-123">This can be done by adding the maxRequestLength attribute with a value greater than the size of your configuration file (in KB) to the httpRuntime element on line 26 of `C:\Program Files\Microsoft Application Virtualization Server\ManagementService\Web.config`.</span></span>  
<span data-ttu-id="b6b55-124">例如， `<httpRuntime targetFramework="4.5"/>` 將 [變更為] `<httpRuntime targetFramework="4.5" maxRequestLength="8192"/>` 會將最大大小增加至8mb</span><span class="sxs-lookup"><span data-stu-id="b6b55-124">For example, changing `<httpRuntime targetFramework="4.5"/>` to `<httpRuntime targetFramework="4.5" maxRequestLength="8192"/>` will increase the maximum size to 8MB</span></span>


<span data-ttu-id="b6b55-125">您**有應用程式-V 的建議**嗎？</span><span class="sxs-lookup"><span data-stu-id="b6b55-125">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="b6b55-126">在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="b6b55-126">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="b6b55-127">有應用程式-V 問題嗎？</span><span class="sxs-lookup"><span data-stu-id="b6b55-127">Got an App-V issue?</span></span>** <span data-ttu-id="b6b55-128">使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="b6b55-128">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="b6b55-129">相關主題</span><span class="sxs-lookup"><span data-stu-id="b6b55-129">Related topics</span></span>


[<span data-ttu-id="b6b55-130">App-V 5.1 作業</span><span class="sxs-lookup"><span data-stu-id="b6b55-130">Operations for App-V 5.1</span></span>](operations-for-app-v-51.md)

 

 





