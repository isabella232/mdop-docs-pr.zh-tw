---
title: 如何發佈應用程式捷徑
description: 如何發佈應用程式捷徑
author: dansimp
ms.assetid: fc5efe86-1bbe-438b-b7d8-4f9b815cc58e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: eafdb85414a1a6cf3e1072fdc5532bcd04699653
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801178"
---
# <span data-ttu-id="71418-103">如何發佈應用程式捷徑</span><span class="sxs-lookup"><span data-stu-id="71418-103">How to Publish Application Shortcuts</span></span>


<span data-ttu-id="71418-104">您可以使用下列程式，直接從應用程式虛擬化用戶端管理主控台中 [**應用程式**] 節點的 [**結果**] 窗格發佈應用程式的快捷方式。</span><span class="sxs-lookup"><span data-stu-id="71418-104">You can use the following procedure to publish shortcuts to an application directly from the **Results** pane of the **Application** node in the Application Virtualization Client Management Console.</span></span>

**<span data-ttu-id="71418-105">發佈應用程式快速鍵</span><span class="sxs-lookup"><span data-stu-id="71418-105">To publish application shortcuts</span></span>**

1.  <span data-ttu-id="71418-106">將游標移至 [**結果**] 窗格，以滑鼠右鍵按一下所需的應用程式，然後從快顯功能表中選取 [**新增快速鍵**]，以顯示 [新增快速鍵] 嚮導。</span><span class="sxs-lookup"><span data-stu-id="71418-106">Move the cursor to the **Results** pane, right-click the desired application, and select **New Shortcut** from the pop-up menu to display the New Shortcut Wizard.</span></span>

2.  <span data-ttu-id="71418-107">在 [新增快捷方式] 嚮導的第一頁上，選取一個圖示，然後指定快捷方式的名稱。</span><span class="sxs-lookup"><span data-stu-id="71418-107">On the first page of the New Shortcut Wizard, select an icon and specify a name for the shortcut.</span></span>

    1.  <span data-ttu-id="71418-108">[**變更] 圖示**-顯示標準的 Windows 圖示瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="71418-108">**Change Icon**—Displays a standard Windows icon browser.</span></span> <span data-ttu-id="71418-109">流覽並選取所要的圖示。</span><span class="sxs-lookup"><span data-stu-id="71418-109">Browse to and select the desired icon.</span></span>

    2.  <span data-ttu-id="71418-110">[**快捷方式標題**]：輸入要賦予快速鍵的名稱。</span><span class="sxs-lookup"><span data-stu-id="71418-110">**Shortcut Title**—Enter the name you want to give the shortcut.</span></span> <span data-ttu-id="71418-111">這個欄位預設為應用程式現有的名稱和版本。</span><span class="sxs-lookup"><span data-stu-id="71418-111">This field defaults to the existing name and version of the application.</span></span>

3.  <span data-ttu-id="71418-112">在嚮導的第二個頁面上，決定已發佈快捷方式的位置。</span><span class="sxs-lookup"><span data-stu-id="71418-112">On the second page of the wizard, determine the location of the published shortcut.</span></span>

    1.  <span data-ttu-id="71418-113">**桌面**-選取此核取方塊即可將快捷方式發佈至桌面。</span><span class="sxs-lookup"><span data-stu-id="71418-113">**The Desktop**—Select this check box to publish the shortcut to the desktop.</span></span>

    2.  <span data-ttu-id="71418-114">**[快速啟動] 工具列**-選取此核取方塊即可將快捷方式發佈至 [快速啟動] 工具列。</span><span class="sxs-lookup"><span data-stu-id="71418-114">**The Quick Launch Toolbar**—Select this check box to publish the shortcut to the Quick Launch toolbar.</span></span>

    3.  <span data-ttu-id="71418-115">**[傳送至] 功能表**：選取此核取方塊，即可將快捷方式發佈至 [**傳送至**] 功能表。</span><span class="sxs-lookup"><span data-stu-id="71418-115">**The Send To Menu**—Select this check box to publish the shortcut to the **Send To** menu.</span></span>

    4.  <span data-ttu-id="71418-116">**[開始] 功能表中的程式**：當您選取 [**開始] 功能表**核取方塊時，這個欄位就會變成作用中。</span><span class="sxs-lookup"><span data-stu-id="71418-116">**Programs in the Start Menu**—When you select the **Start Menu** check box, this field becomes active.</span></span> <span data-ttu-id="71418-117">將此欄位保留空白，即可將快捷方式直接發佈至 [程式] 資料夾的根目錄，或輸入資料夾名稱或階層（例如，「我的 _Computer \\Office 應用程式」）。</span><span class="sxs-lookup"><span data-stu-id="71418-117">Leave this field blank to publish the shortcut directly to the root of the Programs folder, or enter a folder name or hierarchy—for example, "My\_Computer\\Office Applications."</span></span> <span data-ttu-id="71418-118">以這種方式建立的快速鍵只適用于目前的使用者。</span><span class="sxs-lookup"><span data-stu-id="71418-118">Shortcuts created this way are available only for the current user.</span></span>

    5.  <span data-ttu-id="71418-119">[**其他位置** **] 和 [流覽]** 按鈕：當您選取 [**其他位置**] 核取方塊時，此欄位就會變成作用中。</span><span class="sxs-lookup"><span data-stu-id="71418-119">**Another location** and **Browse** button—When you select the **Another location** check box, this field becomes active.</span></span> <span data-ttu-id="71418-120">輸入電腦上的任何有效位置或任何可用的 UNC 路徑（網路上的共用檔案或目錄）。</span><span class="sxs-lookup"><span data-stu-id="71418-120">Enter any valid location on the computer or any available UNC path (shared file or directory on a network).</span></span> <span data-ttu-id="71418-121">[**流覽]** 按鈕會顯示標準的 Windows 檔案 [**開啟**舊檔] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="71418-121">The **Browse** button displays a standard Windows **File Open** dialog box.</span></span>

4.  <span data-ttu-id="71418-122">在嚮導的第三個頁面上，輸入所需的命令列參數。</span><span class="sxs-lookup"><span data-stu-id="71418-122">On the third page of the wizard, enter desired command-line parameters.</span></span>

5.  <span data-ttu-id="71418-123">按一下 **[完成]** ，發佈快捷方式並移至 [**結果**] 窗格。</span><span class="sxs-lookup"><span data-stu-id="71418-123">Click **Finish** to publish the shortcuts and exit to the **Results** pane.</span></span>

## <span data-ttu-id="71418-124">相關主題</span><span class="sxs-lookup"><span data-stu-id="71418-124">Related topics</span></span>


[<span data-ttu-id="71418-125">如何新增檔案類型關聯</span><span class="sxs-lookup"><span data-stu-id="71418-125">How to Add a File Type Association</span></span>](how-to-add-a-file-type-association.md)

[<span data-ttu-id="71418-126">如何新增應用程式</span><span class="sxs-lookup"><span data-stu-id="71418-126">How to Add an Application</span></span>](how-to-add-an-application.md)

[<span data-ttu-id="71418-127">如何刪除檔案類型關聯</span><span class="sxs-lookup"><span data-stu-id="71418-127">How to Delete a File Type Association</span></span>](how-to-delete-a-file-type-association.md)

 

 





