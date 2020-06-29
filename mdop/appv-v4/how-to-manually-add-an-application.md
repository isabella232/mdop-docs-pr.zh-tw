---
title: 如何手動新增應用程式
description: 如何手動新增應用程式
author: dansimp
ms.assetid: c635b07a-5c7f-4ab2-ba18-366457146cb9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 868939553fae6172ccca549ddc3f08aa76ee3c56
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801281"
---
# <span data-ttu-id="1df78-103">如何手動新增應用程式</span><span class="sxs-lookup"><span data-stu-id="1df78-103">How to Manually Add an Application</span></span>


<span data-ttu-id="1df78-104">將應用程式新增到應用程式虛擬化管理伺服器時，建議您將它匯入。</span><span class="sxs-lookup"><span data-stu-id="1df78-104">When adding an application to the Application Virtualization Management Server, it is recommended that you import it.</span></span> <span data-ttu-id="1df78-105">您可以手動新增應用程式，但您必須提供此區段中要求的應用程式確切詳細資訊。</span><span class="sxs-lookup"><span data-stu-id="1df78-105">You can add an application manually, but you must provide the precise, detailed information about the application called for in this section.</span></span>

**<span data-ttu-id="1df78-106">手動新增應用程式</span><span class="sxs-lookup"><span data-stu-id="1df78-106">To manually add a new application</span></span>**

1.  <span data-ttu-id="1df78-107">在左窗格中，以滑鼠右鍵按一下 [**應用**程式] 節點，然後選擇 [**新增應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="1df78-107">In the left pane, right-click the **Applications** node and choose **New Application**.</span></span>

2.  <span data-ttu-id="1df78-108">在 [**新增應用程式] 嚮導**中，完成 **[一般資訊**] 對話方塊：</span><span class="sxs-lookup"><span data-stu-id="1df78-108">In the **New Application Wizard**, complete the **General Information** dialog box:</span></span>

    1.  <span data-ttu-id="1df78-109">[**應用程式名稱**]-輸入您希望使用者看到的名稱。</span><span class="sxs-lookup"><span data-stu-id="1df78-109">**Application Name**—Type the name you want the users to see.</span></span>

    2.  <span data-ttu-id="1df78-110">**版本**-輸入應用程式版本。</span><span class="sxs-lookup"><span data-stu-id="1df78-110">**Version**—Type the application version.</span></span>

    3.  <span data-ttu-id="1df78-111">[**已啟用**]：您必須在建立應用程式後選取此方塊以進行串流。</span><span class="sxs-lookup"><span data-stu-id="1df78-111">**Enabled**—This box must be selected to stream the application after you create it.</span></span>

    4.  <span data-ttu-id="1df78-112">**描述**-輸入管理使用的選擇性說明。</span><span class="sxs-lookup"><span data-stu-id="1df78-112">**Description**—Type an optional description for administrative use.</span></span>

    5.  <span data-ttu-id="1df78-113">**OSD 路徑**-流覽網路至應用程式的開啟軟體描述項（OSD）檔。</span><span class="sxs-lookup"><span data-stu-id="1df78-113">**OSD Path**—Browse the network to the application's Open Software Descriptor (OSD) file.</span></span> <span data-ttu-id="1df78-114">此檔案必須在共用的網路資料夾中。</span><span class="sxs-lookup"><span data-stu-id="1df78-114">This file must be in a shared network folder.</span></span>

    6.  <span data-ttu-id="1df78-115">**圖示路徑**-流覽至應用程式的 .ico 檔案。</span><span class="sxs-lookup"><span data-stu-id="1df78-115">**Icon Path**—Browse to the application's ICO file.</span></span>

    7.  <span data-ttu-id="1df78-116">[**應用程式授權] 群組**：如果您已設定授權群組，您可以在下拉式清單中選取應用程式，將其指派給其中一個。</span><span class="sxs-lookup"><span data-stu-id="1df78-116">**Application License Group**—If you have set up license groups, you can assign the application to one by selecting it in the pull-down list.</span></span>

    8.  <span data-ttu-id="1df78-117">**伺服器群組**：如果您有多個應用程式虛擬化伺服器，您可以在下拉式清單中選取應用程式，將其指派給一個應用程式。</span><span class="sxs-lookup"><span data-stu-id="1df78-117">**Server Group**—If you have multiple Application Virtualization Servers, you can assign the application to one by selecting it in the pull-down list.</span></span>

3.  <span data-ttu-id="1df78-118">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="1df78-118">Click **Next**.</span></span>

4.  <span data-ttu-id="1df78-119">在 [**選取套件**] 對話方塊中，選取相關的套件，然後按一下 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="1df78-119">In the **Select Package** dialog box, select the related package and click **Next**.</span></span>

5.  <span data-ttu-id="1df78-120">在 [**已發佈的快速鍵**] 畫面上，針對您想要在用戶端電腦上顯示應用程式快捷方式的位置，選取方塊，然後按 **[下一步]**。</span><span class="sxs-lookup"><span data-stu-id="1df78-120">On the **Published Shortcuts** screen, select the boxes for the locations where you would like the application shortcuts to appear on the client computers and click **Next**.</span></span>

6.  <span data-ttu-id="1df78-121">在 [檔案**關聯**] 畫面中，您可以將新的類型檔案關聯新增到此應用程式。</span><span class="sxs-lookup"><span data-stu-id="1df78-121">In the **File Associations** screen, you can add new type file associations to this application.</span></span> <span data-ttu-id="1df78-122">若要這樣做，請按一下 [**新增**]，輸入副檔名（不含前一個點），輸入描述，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="1df78-122">To do so, click **Add**, enter the extension (without a preceding dot), enter a description, and click **OK**.</span></span>

7.  <span data-ttu-id="1df78-123">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="1df78-123">Click **Next**.</span></span>

8.  <span data-ttu-id="1df78-124">在 [**存取許可權**] 對話方塊中，按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="1df78-124">In the **Access Permissions** dialog box, click **Add**.</span></span>

9.  <span data-ttu-id="1df78-125">在 [**新增/編輯使用者群組**] 對話方塊中，流覽至 [使用者] 群組。</span><span class="sxs-lookup"><span data-stu-id="1df78-125">In the **Add/Edit User Group** dialog box, navigate to the user group.</span></span> <span data-ttu-id="1df78-126">您也可以在個別欄位中輸入資訊，以輸入網域和群組。</span><span class="sxs-lookup"><span data-stu-id="1df78-126">You can also enter the domain and group by typing the information in the respective fields.</span></span> <span data-ttu-id="1df78-127">完成後，請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="1df78-127">When you finish, click **OK**.</span></span> <span data-ttu-id="1df78-128">您可以使用相同的頁面新增其他群組。</span><span class="sxs-lookup"><span data-stu-id="1df78-128">You can add other groups with the same pages.</span></span>

10. <span data-ttu-id="1df78-129">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="1df78-129">Click **Next**.</span></span>

11. <span data-ttu-id="1df78-130">在 [**摘要**] 畫面上，您可以查看 [匯入] 設定。</span><span class="sxs-lookup"><span data-stu-id="1df78-130">On the **Summary** screen, you can review the import settings.</span></span> <span data-ttu-id="1df78-131">按一下 **[完成]** 以新增應用程式，按一下 [**返回**] 變更資訊，或按一下 [**取消**]。</span><span class="sxs-lookup"><span data-stu-id="1df78-131">Click **Finish** to add the application, click **Back** to change the information, or click **Cancel**.</span></span>

## <span data-ttu-id="1df78-132">相關主題</span><span class="sxs-lookup"><span data-stu-id="1df78-132">Related topics</span></span>


[<span data-ttu-id="1df78-133">如何在伺服器管理主控台中管理應用程式</span><span class="sxs-lookup"><span data-stu-id="1df78-133">How to Manage Applications in the Server Management Console</span></span>](how-to-manage-applications-in-the-server-management-console.md)

 

 





