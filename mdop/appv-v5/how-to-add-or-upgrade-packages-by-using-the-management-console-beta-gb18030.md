---
title: 如何使用 Management Console 新增或升級套件
description: 如何使用 Management Console 新增或升級套件
author: dansimp
ms.assetid: 4e389d7e-f402-44a7-bc4c-42c2a8440573
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 583ac07168c44c7d0a605b81512ae01a6d979db2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800601"
---
# <span data-ttu-id="ca7c1-103">如何使用 Management Console 新增或升級套件</span><span class="sxs-lookup"><span data-stu-id="ca7c1-103">How to Add or Upgrade Packages by Using the Management Console</span></span>


<span data-ttu-id="ca7c1-104">您可以使用下列程式，將套件新增或升級到 App-v 5.0 管理主控台。</span><span class="sxs-lookup"><span data-stu-id="ca7c1-104">You can the following procedure to add or upgrade a package to the App-V 5.0 Management Console.</span></span> <span data-ttu-id="ca7c1-105">若要升級已存在於管理主控台中的套件，請使用下列步驟，並使用相同的套件**名稱**匯入升級後的套件。</span><span class="sxs-lookup"><span data-stu-id="ca7c1-105">To upgrade a package that already exists in the Management Console, use the following steps and import the upgraded package using the same package **Name**.</span></span>

**<span data-ttu-id="ca7c1-106">將套件新增到管理主控台</span><span class="sxs-lookup"><span data-stu-id="ca7c1-106">To add a package to the Management Console</span></span>**

1.  <span data-ttu-id="ca7c1-107">按一下管理主控台顯示的 [功能窗格] 中的 [**套件**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="ca7c1-107">Click the **Packages** tab in the navigation pane of the Management Console display.</span></span>

    <span data-ttu-id="ca7c1-108">主控台會顯示已新增到伺服器的套件清單，以及每個套件的狀態資訊。</span><span class="sxs-lookup"><span data-stu-id="ca7c1-108">The console displays the list of packages that have been added to the server along with status information about each package.</span></span> <span data-ttu-id="ca7c1-109">選取套件時，套件窗格中會顯示有關**套件的詳細**資訊。</span><span class="sxs-lookup"><span data-stu-id="ca7c1-109">When a package is selected, detailed information about the package is displayed in the **PACKAGES** pane.</span></span>

    <span data-ttu-id="ca7c1-110">按一下 [**取消**群組] 下拉式清單方塊，並指定套件在主控台中的顯示方式。</span><span class="sxs-lookup"><span data-stu-id="ca7c1-110">Click the **Ungrouped** drop-down list box and specify how the packages are to be displayed in the console.</span></span> <span data-ttu-id="ca7c1-111">您也可以按一下相關聯的欄標題來排序套件。</span><span class="sxs-lookup"><span data-stu-id="ca7c1-111">You can also click the associated column header to sort the packages.</span></span>

2.  <span data-ttu-id="ca7c1-112">若要指定您想要新增的套件，請按一下 [**新增或升級套件**]。</span><span class="sxs-lookup"><span data-stu-id="ca7c1-112">To specify the package you want to add, click **Add or Upgrade Packages**.</span></span>

3.  <span data-ttu-id="ca7c1-113">輸入您要新增之套件的完整路徑。</span><span class="sxs-lookup"><span data-stu-id="ca7c1-113">Type the full path to the package that you want to add.</span></span> <span data-ttu-id="ca7c1-114">使用 UNC 或 HTTP 路徑格式，例如**\\\\servername\\sharename\\foldername\\packagename.appv**或 **http://server.1234/file.appv** ，然後按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="ca7c1-114">Use the UNC or HTTP path format, for example **\\\\servername\\sharename\\foldername\\packagename.appv** or **http://server.1234/file.appv**, and then click **Add**.</span></span>

    <span data-ttu-id="ca7c1-115">**重要** 您必須選取具有**appv**副檔名的套件。</span><span class="sxs-lookup"><span data-stu-id="ca7c1-115">**Important** You must select a package with the **.appv** file name extension.</span></span>

     

4.  <span data-ttu-id="ca7c1-116">頁面會顯示 [\*\*新增 &lt; Packagename &gt; \*\*] 的狀態訊息。</span><span class="sxs-lookup"><span data-stu-id="ca7c1-116">The page displays the status message **Adding &lt;Packagename&gt;**.</span></span> <span data-ttu-id="ca7c1-117">按一下 [匯**入狀態**]，查看您已匯入之套件的狀態。</span><span class="sxs-lookup"><span data-stu-id="ca7c1-117">Click **IMPORT STATUS** to check the status of a package that you have imported.</span></span>

    <span data-ttu-id="ca7c1-118">按一下 **[確定]** 以新增套件，然後關閉 [**新增套件**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="ca7c1-118">Click **OK** to add the package and close the **Add Package** page.</span></span> <span data-ttu-id="ca7c1-119">如果匯入期間發生錯誤，請按一下套件 [匯**入**] 頁面上的 [**詳細資料**] 以取得詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="ca7c1-119">If there was an error during the import, click **Detail** on the **Package Import** page for more information.</span></span> <span data-ttu-id="ca7c1-120">您現在可以在 [**套件**] 窗格中使用新新增的套件。</span><span class="sxs-lookup"><span data-stu-id="ca7c1-120">The newly added package is now available in the **PACKAGES** pane.</span></span>

5.  <span data-ttu-id="ca7c1-121">按一下 [**關閉**]，關閉 [**新增或升級套件**] 頁面。</span><span class="sxs-lookup"><span data-stu-id="ca7c1-121">Click **Close** to close the **Add or Upgrade Packages** page.</span></span>

    <span data-ttu-id="ca7c1-122">您**有應用程式-V 的建議**嗎？</span><span class="sxs-lookup"><span data-stu-id="ca7c1-122">**Got a suggestion for App-V**?</span></span> <span data-ttu-id="ca7c1-123">在[此](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization)新增或投票建議。</span><span class="sxs-lookup"><span data-stu-id="ca7c1-123">Add or vote on suggestions [here](http://appv.uservoice.com/forums/280448-microsoft-application-virtualization).</span></span> **<span data-ttu-id="ca7c1-124">有應用程式-V 問題嗎？</span><span class="sxs-lookup"><span data-stu-id="ca7c1-124">Got an App-V issue?</span></span>** <span data-ttu-id="ca7c1-125">使用[App-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopappv)。</span><span class="sxs-lookup"><span data-stu-id="ca7c1-125">Use the [App-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopappv).</span></span>

## <span data-ttu-id="ca7c1-126">相關主題</span><span class="sxs-lookup"><span data-stu-id="ca7c1-126">Related topics</span></span>


[<span data-ttu-id="ca7c1-127">App-V 5.0 作業</span><span class="sxs-lookup"><span data-stu-id="ca7c1-127">Operations for App-V 5.0</span></span>](operations-for-app-v-50.md)

 

 





