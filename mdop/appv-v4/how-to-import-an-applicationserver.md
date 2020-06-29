---
title: 如何匯入應用程式
description: 如何匯入應用程式
author: dansimp
ms.assetid: ab40acad-1025-478d-8e13-0e1ff1bd37e4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7d9cd6d065ca28b5d856acdae7d10a1280105e9d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801402"
---
# <span data-ttu-id="4ebb8-103">如何匯入應用程式</span><span class="sxs-lookup"><span data-stu-id="4ebb8-103">How to Import an Application</span></span>


<span data-ttu-id="4ebb8-104">通常，您必須匯入應用程式，才能從應用程式虛擬化管理伺服器對流進行資料流程。</span><span class="sxs-lookup"><span data-stu-id="4ebb8-104">Typically, you import applications to make them available to stream from an Application Virtualization Management Server.</span></span> <span data-ttu-id="4ebb8-105">您也可以手動新增應用程式，但您必須提供應用程式的確切詳細資訊來執行此操作。</span><span class="sxs-lookup"><span data-stu-id="4ebb8-105">You can also add an application manually, but you must provide precise, detailed information about the application to do so.</span></span> <span data-ttu-id="4ebb8-106">如需詳細資訊，請參閱[如何手動新增應用程式](how-to-manually-add-an-application.md)。</span><span class="sxs-lookup"><span data-stu-id="4ebb8-106">For more information, see [How to Manually Add an Application](how-to-manually-add-an-application.md).</span></span>

<span data-ttu-id="4ebb8-107">**記事** 若要匯入應用程式，您必須擁有其已排序的開啟軟體描述項（OSD）檔案或其 Sequencer 專案（SPRJ）檔案（在伺服器上可用）。</span><span class="sxs-lookup"><span data-stu-id="4ebb8-107">**Note** To import an application, you must have its sequenced Open Software Descriptor (OSD) file or its Sequencer Project (SPRJ) file available on the server.</span></span>

 

<span data-ttu-id="4ebb8-108">匯入應用程式時，您應該確認伺服器已在 [**系統選項**] 對話方塊的 [**一般**] 索引標籤上，將 [**預設內容路徑**] 欄位中的值設定為（可透過以滑鼠右鍵按一下 App-v Server 主控台中的 [**應用程式虛擬化系統**] 節點）。</span><span class="sxs-lookup"><span data-stu-id="4ebb8-108">When importing an application, you should make sure the server is configured with a value in the **Default Content Path** field on the **General** tab of the **System Options** dialog (accessible by right-clicking the **Application Virtualization System** node in the App-V Server Console).</span></span> <span data-ttu-id="4ebb8-109">預設的內容路徑值定義了要匯入應用程式的位置，以及在匯入程式期間，此值用於修改 SFT 檔案的 OSD 檔案中定義的路徑，以及圖示快速鍵。</span><span class="sxs-lookup"><span data-stu-id="4ebb8-109">The default content path value defines where the applications will be imported, and during the import process, this value is used to modify the paths defined in the OSD file for the SFT file and for the icon shortcuts.</span></span> <span data-ttu-id="4ebb8-110">在 OSD 檔案中，SFT 檔案的路徑是在 CODEBASE HREF 專案中指定，而圖示的路徑是在快速鍵專案中指定。</span><span class="sxs-lookup"><span data-stu-id="4ebb8-110">In the OSD file, the path for the SFT file is specified in the CODEBASE HREF entry and the path for the icons is specified in the SHORTCUTS entry.</span></span>

<span data-ttu-id="4ebb8-111">在匯入程式中，在 OSD 檔案中，在這兩個路徑中指定的埠（如果有的話）會以預設內容路徑中的值取代。</span><span class="sxs-lookup"><span data-stu-id="4ebb8-111">During the import process, the protocol, server, and, if present, port specified in these two paths in the OSD file will be replaced with the value from the default content path.</span></span> <span data-ttu-id="4ebb8-112">下表提供匯入路徑會受到影響的範例。</span><span class="sxs-lookup"><span data-stu-id="4ebb8-112">The following table provides an example of how the import path will be affected.</span></span>

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="4ebb8-113">預設內容路徑</span><span class="sxs-lookup"><span data-stu-id="4ebb8-113">Default Content Path</span></span></th>
<th align="left"><span data-ttu-id="4ebb8-114">OSD 檔案基本代碼 HREF</span><span class="sxs-lookup"><span data-stu-id="4ebb8-114">OSD File CODEBASE HREF</span></span></th>
<th align="left"><span data-ttu-id="4ebb8-115">結果值</span><span class="sxs-lookup"><span data-stu-id="4ebb8-115">Resulting Value</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="4ebb8-116">\server\content &lt; /p&gt;</span><span class="sxs-lookup"><span data-stu-id="4ebb8-116">\server\content&lt;/p&gt;</span></span></td>
<td align="left"><p><a href="http://WebServer/myFolder/package.sft" data-raw-source="http://WebServer/myFolder/package.sft">http://WebServer/myFolder/package.sft</a></p></td>
<td align="left"><p><span data-ttu-id="4ebb8-117">\server\content\myFolder\package.sft</span><span class="sxs-lookup"><span data-stu-id="4ebb8-117">\server\content\myFolder\package.sft</span></span></p></td>
</tr>
</tbody>
</table>

 

**<span data-ttu-id="4ebb8-118">匯入應用程式</span><span class="sxs-lookup"><span data-stu-id="4ebb8-118">To import an application</span></span>**

1.  <span data-ttu-id="4ebb8-119">以滑鼠右鍵按一下左窗格中的 [**應用程式**] 節點，然後選擇 [匯**入應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="4ebb8-119">Right-click the **Applications** node in the left pane, and choose **Import Applications**.</span></span>

2.  <span data-ttu-id="4ebb8-120">在 [**開啟**舊檔] 對話方塊中，流覽至應用程式的 SPRJ 或 OSD 檔案。</span><span class="sxs-lookup"><span data-stu-id="4ebb8-120">In the **Open** dialog box, navigate to the application's SPRJ or OSD file.</span></span> <span data-ttu-id="4ebb8-121">醒目提示檔案，然後按一下 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="4ebb8-121">Highlight the file and click **Open**.</span></span>

3.  <span data-ttu-id="4ebb8-122">在 [**新增應用程式] 嚮導**中，請確定已針對您要進行串流的應用程式選取 [**已啟用**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="4ebb8-122">In the **New Application Wizard**, be sure the **Enabled** box is selected for applications you want to stream.</span></span> <span data-ttu-id="4ebb8-123">您也可以在其中輸入描述並確認伺服器與檔路徑。</span><span class="sxs-lookup"><span data-stu-id="4ebb8-123">There you can also enter a description and verify the server and file paths.</span></span> <span data-ttu-id="4ebb8-124">此外，如果您已設定授權和伺服器群組，您可以選取這些使用者。</span><span class="sxs-lookup"><span data-stu-id="4ebb8-124">Also, if you have set up license and server groups, you can select those.</span></span>

4.  <span data-ttu-id="4ebb8-125">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="4ebb8-125">Click **Next**.</span></span>

5.  <span data-ttu-id="4ebb8-126">在 [**已發佈的快速鍵**] 畫面上，選取您想要在用戶端電腦上顯示應用程式快捷方式的位置方塊。</span><span class="sxs-lookup"><span data-stu-id="4ebb8-126">On the **Published Shortcuts** screen, select the boxes for the locations where you would like the application shortcuts to appear on the client computers.</span></span>

6.  <span data-ttu-id="4ebb8-127">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="4ebb8-127">Click **Next**.</span></span>

7.  <span data-ttu-id="4ebb8-128">在 [檔案**關聯**] 畫面中，您可以在此應用程式中新增新的檔案關聯。</span><span class="sxs-lookup"><span data-stu-id="4ebb8-128">In the **File Associations** screen, you can add new file associations to this application.</span></span> <span data-ttu-id="4ebb8-129">若要這樣做，請按一下 [**新增**]，輸入副檔名（不含前一個點），輸入描述，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="4ebb8-129">To do so, click **Add**, enter the extension (without a preceding dot), enter a description, and click **OK**.</span></span>

    <span data-ttu-id="4ebb8-130">**記事** 使用 Sequencer 4.0 排序的應用程式會在您匯入或透過管理主控台建立檔案時填入 [檔案**關聯**] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="4ebb8-130">**Note** Applications sequenced with Sequencer 4.0 populate the **File Associations** dialog box when you import or create them through the management console.</span></span> <span data-ttu-id="4ebb8-131">先前的 Sequencer 版本套件的應用程式不會。</span><span class="sxs-lookup"><span data-stu-id="4ebb8-131">Applications with previous Sequencer version packages do not.</span></span>

     

8.  <span data-ttu-id="4ebb8-132">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="4ebb8-132">Click **Next**.</span></span>

9.  <span data-ttu-id="4ebb8-133">在 [**存取許可權**] 畫面中，按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="4ebb8-133">In the **Access Permissions** screen, click **Add**.</span></span>

10. <span data-ttu-id="4ebb8-134">完成 [**選取群組**] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="4ebb8-134">Complete the **Select Groups** dialog box.</span></span> <span data-ttu-id="4ebb8-135">完成後，請按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="4ebb8-135">When you finish, click **OK**.</span></span>

11. <span data-ttu-id="4ebb8-136">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="4ebb8-136">Click **Next**.</span></span>

12. <span data-ttu-id="4ebb8-137">在 [**摘要**] 畫面上，您可以查看 [匯入] 設定。</span><span class="sxs-lookup"><span data-stu-id="4ebb8-137">On the **Summary** screen, you can review the import settings.</span></span> <span data-ttu-id="4ebb8-138">按一下 **[完成]**，或按一下 [**上一步**] 來變更匯入，或按一下 [**取消**] 以取消匯入。</span><span class="sxs-lookup"><span data-stu-id="4ebb8-138">Click **Finish**, or click **Back** to change the import or click **Cancel** to cancel the import.</span></span>

## <span data-ttu-id="4ebb8-139">相關主題</span><span class="sxs-lookup"><span data-stu-id="4ebb8-139">Related topics</span></span>


[<span data-ttu-id="4ebb8-140">如何在伺服器管理主控台中管理應用程式群組</span><span class="sxs-lookup"><span data-stu-id="4ebb8-140">How to Manage Application Groups in the Server Management Console</span></span>](how-to-manage-application-groups-in-the-server-management-console.md)

[<span data-ttu-id="4ebb8-141">如何在伺服器管理主控台中管理應用程式</span><span class="sxs-lookup"><span data-stu-id="4ebb8-141">How to Manage Applications in the Server Management Console</span></span>](how-to-manage-applications-in-the-server-management-console.md)

[<span data-ttu-id="4ebb8-142">如何手動新增應用程式</span><span class="sxs-lookup"><span data-stu-id="4ebb8-142">How to Manually Add an Application</span></span>](how-to-manually-add-an-application.md)

 

 





