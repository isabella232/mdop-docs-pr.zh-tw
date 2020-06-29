---
title: 如何開始、停止及重新啟動 MED-V 工作區
description: 如何開始、停止及重新啟動 MED-V 工作區
author: dansimp
ms.assetid: 54ce139c-8f32-499e-944b-72f123ebfd2d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c2739ace085a4d57d333daf7872e01a7712a7fbd
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811325"
---
# <span data-ttu-id="1bb72-103">如何開始、停止及重新啟動 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="1bb72-103">How to Start, Stop, and Restart a MED-V Workspace</span></span>


**<span data-ttu-id="1bb72-104">啟動 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="1bb72-104">To start a MED-V workspace</span></span>**

1.  <span data-ttu-id="1bb72-105">在通知區域中，以滑鼠右鍵按一下 MED-V 圖示。</span><span class="sxs-lookup"><span data-stu-id="1bb72-105">In the notification area, right-click the MED-V icon.</span></span>

2.  <span data-ttu-id="1bb72-106">在子功能表上，按一下 [**啟動工作區**]。</span><span class="sxs-lookup"><span data-stu-id="1bb72-106">On the submenu, click **Start Workspace**.</span></span>

    -   <span data-ttu-id="1bb72-107">如果在電腦上執行多個 MED-V 工作區，則會出現 [**工作區選取範圍**] 視窗。</span><span class="sxs-lookup"><span data-stu-id="1bb72-107">If there are multiple MED-V workspaces running on the computer, the **Workspace Selection** window appears.</span></span>

        1.  <span data-ttu-id="1bb72-108">選取 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="1bb72-108">Select a MED-V workspace.</span></span>

        2.  <span data-ttu-id="1bb72-109">選取 [**啟動選取的工作區但不要求我**] 核取方塊，以在下次啟動用戶端時跳過此視窗，並自動開啟選取的 med-v 工作區。</span><span class="sxs-lookup"><span data-stu-id="1bb72-109">Select the **Start the selected Workspace without asking me** check box to skip this window the next time the client is started and to automatically open the selected MED-V workspace.</span></span>

        3.  <span data-ttu-id="1bb72-110">按一下 \[確定\] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bb72-110">Click **OK**.</span></span>

    <span data-ttu-id="1bb72-111">隨即會出現 [**啟動工作區驗證**] 視窗。</span><span class="sxs-lookup"><span data-stu-id="1bb72-111">The **Start Workspace Authentication** window appears.</span></span>

    -   <span data-ttu-id="1bb72-112">如果電腦上有數個 MED-V 工作區，而且您選擇要使用指定的 MED-V 工作區，則會出現如下圖所示的視窗。</span><span class="sxs-lookup"><span data-stu-id="1bb72-112">If there are several MED-V workspaces on the computer and you have opted to use a specified MED-V workspace, the window shown in the following figure appears.</span></span>

        ![](images/medv-logon.gif)

    -   <span data-ttu-id="1bb72-113">如果電腦上只有一個 MED-V 工作區，則 [啟動上次使用的工作區] 選項無法使用。</span><span class="sxs-lookup"><span data-stu-id="1bb72-113">If there is only one MED-V workspace on the computer, the “Start last used Workspace” option is unavailable.</span></span>

3.  <span data-ttu-id="1bb72-114">輸入您的網域使用者認證。</span><span class="sxs-lookup"><span data-stu-id="1bb72-114">Type in your domain user credentials.</span></span>

    <span data-ttu-id="1bb72-115">**記事** 第一次啟動 med-v 工作區時，使用者名稱應該是下列格式： &lt; 功能變數名稱 &gt; \\ &lt; 使用者名稱 &gt; 。</span><span class="sxs-lookup"><span data-stu-id="1bb72-115">**Note** The first time a MED-V workspace is started, the user name should be in the following format: &lt;domain name&gt;\\&lt;user name&gt;.</span></span>

     

4.  <span data-ttu-id="1bb72-116">選取 [**儲存我的密碼**]，在會話之間儲存密碼。</span><span class="sxs-lookup"><span data-stu-id="1bb72-116">Select **Save my password** to save your password between sessions.</span></span>

    <span data-ttu-id="1bb72-117">**記事** 若要啟用 [儲存密碼] 功能，在 ClientSettings.xml 檔案中必須將 EnableSavePassword 屬性設為 True。</span><span class="sxs-lookup"><span data-stu-id="1bb72-117">**Note** To enable the save password feature, the EnableSavePassword attribute must be set to True in the ClientSettings.xml file.</span></span> <span data-ttu-id="1bb72-118">檔案可以在 [ *Servers\\Configuration Server\\* ] 資料夾中找到。</span><span class="sxs-lookup"><span data-stu-id="1bb72-118">The file can be found in the *Servers\\Configuration Server\\* folder.</span></span>

     

5.  <span data-ttu-id="1bb72-119">清除 [**啟動上次使用的工作區**] 核取方塊，選擇不同的 med-v 工作區。</span><span class="sxs-lookup"><span data-stu-id="1bb72-119">Clear the **Start last used workspace** check box to choose a different MED-V workspace.</span></span>

6.  <span data-ttu-id="1bb72-120">按一下 \[確定\] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1bb72-120">Click **OK**.</span></span>

    <span data-ttu-id="1bb72-121">視 MED-V 工作區設定而定，會出現幾個狀態畫面。</span><span class="sxs-lookup"><span data-stu-id="1bb72-121">Several status screens appear depending on the MED-V workspace configuration.</span></span>

    <span data-ttu-id="1bb72-122">[**啟動工作區**] 畫面隨即出現。</span><span class="sxs-lookup"><span data-stu-id="1bb72-122">The **Starting Workspace** screen appears.</span></span>

**<span data-ttu-id="1bb72-123">重新開機 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="1bb72-123">To restart a MED-V workspace</span></span>**

1.  <span data-ttu-id="1bb72-124">當用戶端正在執行時，請在通知區域中，以滑鼠右鍵按一下 MED-V 圖示。</span><span class="sxs-lookup"><span data-stu-id="1bb72-124">When the client is running, in the notification area, right-click the MED-V icon.</span></span>

2.  <span data-ttu-id="1bb72-125">在子功能表上，按一下 [**重新開機工作區**]。</span><span class="sxs-lookup"><span data-stu-id="1bb72-125">On the submenu, click **Restart Workspace**.</span></span>

    <span data-ttu-id="1bb72-126">隨後便會重新開機 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="1bb72-126">The MED-V workspace is restarted.</span></span>

    -   <span data-ttu-id="1bb72-127">在持久的 MED-V 工作區中，虛擬機器會關閉並重新啟動。</span><span class="sxs-lookup"><span data-stu-id="1bb72-127">In a persistent MED-V workspace, the virtual machine is shut down and then restarted.</span></span>

    -   <span data-ttu-id="1bb72-128">在 revertible MED-V 工作區中，虛擬機器實際上不會關閉;相反地，它會回到原始狀態。</span><span class="sxs-lookup"><span data-stu-id="1bb72-128">In a revertible MED-V workspace, the virtual machine does not actually shut down; instead, it returns to its original state.</span></span>

**<span data-ttu-id="1bb72-129">停止 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="1bb72-129">To stop a MED-V workspace</span></span>**

1.  <span data-ttu-id="1bb72-130">在通知區域中，以滑鼠右鍵按一下 MED-V 圖示。</span><span class="sxs-lookup"><span data-stu-id="1bb72-130">In the notification area, right-click the MED-V icon.</span></span>

2.  <span data-ttu-id="1bb72-131">在子功能表上，按一下 [**停止工作區**]。</span><span class="sxs-lookup"><span data-stu-id="1bb72-131">On the submenu, click **Stop Workspace**.</span></span>

    <span data-ttu-id="1bb72-132">MED-V 工作區已停止。</span><span class="sxs-lookup"><span data-stu-id="1bb72-132">The MED-V workspace is stopped.</span></span>

## <span data-ttu-id="1bb72-133">相關主題</span><span class="sxs-lookup"><span data-stu-id="1bb72-133">Related topics</span></span>


[<span data-ttu-id="1bb72-134">如何開始和結束 MED-V 用戶端</span><span class="sxs-lookup"><span data-stu-id="1bb72-134">How to Start and Exit the MED-V Client</span></span>](how-to-start-and-exit-the-med-v-client.md)

 

 





