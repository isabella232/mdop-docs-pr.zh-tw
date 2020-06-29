---
title: 如何產生報告
description: 如何產生報告
author: dansimp
ms.assetid: 9f8ba28e-1993-4c11-a28a-493718051e5d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 930b7061d3e5e2fb9951d45b1422915836cbc00e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812087"
---
# <span data-ttu-id="a104c-103">如何產生報告</span><span class="sxs-lookup"><span data-stu-id="a104c-103">How to Generate Reports</span></span>


<span data-ttu-id="a104c-104">下列報告類型可以由系統管理員在 MED-V 中建立：</span><span class="sxs-lookup"><span data-stu-id="a104c-104">The following report types can be created by administrators in MED-V:</span></span>

-   <span data-ttu-id="a104c-105">[狀態](#bkmk-generatingastatusreport)-使用 [狀態] 報告來查看所有作用中使用者的目前狀態，以及每個使用者的所有 med-v 工作區（根據已定義的一段時間）。</span><span class="sxs-lookup"><span data-stu-id="a104c-105">[Status](#bkmk-generatingastatusreport)—Use the status report to review the current status of all active users and all MED-V workspaces of each user based on a defined period of time.</span></span> <span data-ttu-id="a104c-106">這包括查看目前已連線到伺服器的電腦，或者如果目前未連線的電腦、其上次連線至伺服器的日期和時間、每個電腦的狀態，以及其他相關資訊。</span><span class="sxs-lookup"><span data-stu-id="a104c-106">This includes viewing computers that are currently connected to the server or, if they are not currently connected, the date and time they were last connected to the server, the status of each computer, and other relevant information.</span></span>

-   <span data-ttu-id="a104c-107">[[活動記錄](#bkmk-generatinganactivitylogreport)]-使用此報告來查看源自已定義日期範圍內特定主機或使用者的事件。</span><span class="sxs-lookup"><span data-stu-id="a104c-107">[Activity Log](#bkmk-generatinganactivitylogreport)—Use this report to review events that originated from a specific host or user in a defined date range.</span></span>

-   <span data-ttu-id="a104c-108">[錯誤記錄](#bkmk-generatinganerrorlogreport)-使用此報告來查看源自已定義日期範圍內特定主機或使用者的錯誤。</span><span class="sxs-lookup"><span data-stu-id="a104c-108">[Error Log](#bkmk-generatinganerrorlogreport)—Use this report to view errors that originated from a specific host or user in a defined date range.</span></span>

<span data-ttu-id="a104c-109">按一下適當的欄名，即可依任何資料行來排序報告結果。</span><span class="sxs-lookup"><span data-stu-id="a104c-109">The report results can be sorted by any column by clicking the appropriate column name.</span></span>

<span data-ttu-id="a104c-110">您可以將欄標題拖曳到報表頂端，將報表結果分組。</span><span class="sxs-lookup"><span data-stu-id="a104c-110">The report results can be grouped by dragging a column header to the top of the report.</span></span> <span data-ttu-id="a104c-111">拖曳多個資料列標題，將一個資料行逐一分組。</span><span class="sxs-lookup"><span data-stu-id="a104c-111">Drag multiple column headers to group one column after another.</span></span>

## <a href="" id="bkmk-generatingastatusreport"></a><span data-ttu-id="a104c-112">如何產生狀態報表</span><span class="sxs-lookup"><span data-stu-id="a104c-112">How to Generate a Status Report</span></span>


**<span data-ttu-id="a104c-113">產生狀態報表</span><span class="sxs-lookup"><span data-stu-id="a104c-113">To generate a status report</span></span>**

1.  <span data-ttu-id="a104c-114">按一下 [**報告**管理] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="a104c-114">Click the **Reports** management button.</span></span>

2.  <span data-ttu-id="a104c-115">在 [**報表**] 模組的 [**報表類型**] 功能表上，選取 [**狀態**]，然後按一下 [**產生**]。</span><span class="sxs-lookup"><span data-stu-id="a104c-115">In the **Reports** module, on the **Report Types** menu, select **Status**, and click **Generate**.</span></span>

    <span data-ttu-id="a104c-116">[報表參數] 對話方塊隨即出現。</span><span class="sxs-lookup"><span data-stu-id="a104c-116">The Report Parameters dialog box appears.</span></span>

3.  <span data-ttu-id="a104c-117">在 [**報表參數**] 對話方塊的 [**天數**] 欄位中，輸入數位，或使用箭號來選取要包含在狀態報表中的天數，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="a104c-117">In the **Report Parameters** dialog box, in the **Number of days** field, enter a number or use the arrows to select the number of days to include in the status report, and click **OK**.</span></span>

    <span data-ttu-id="a104c-118">即會產生狀態報表。</span><span class="sxs-lookup"><span data-stu-id="a104c-118">A status report is generated.</span></span> <span data-ttu-id="a104c-119">報表參數是在下表中定義。</span><span class="sxs-lookup"><span data-stu-id="a104c-119">The report parameters are defined in the following table.</span></span>

**<span data-ttu-id="a104c-120">用戶端 MED-V 工作區屬性</span><span class="sxs-lookup"><span data-stu-id="a104c-120">Client MED-V Workspace Properties</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a104c-121">屬性</span><span class="sxs-lookup"><span data-stu-id="a104c-121">Property</span></span></th>
<th align="left"><span data-ttu-id="a104c-122">描述</span><span class="sxs-lookup"><span data-stu-id="a104c-122">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a104c-123">時間</span><span class="sxs-lookup"><span data-stu-id="a104c-123">Time</span></span></p></td>
<td align="left"><p><span data-ttu-id="a104c-124">事件發生的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="a104c-124">The date and time the event occurred.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="a104c-125">注意</span><span class="sxs-lookup"><span data-stu-id="a104c-125">Note</span></span></strong><br/><p><span data-ttu-id="a104c-126">根據預設，事件會以遞減的日期順序顯示。</span><span class="sxs-lookup"><span data-stu-id="a104c-126">By default, the events are displayed in descending date order.</span></span> <span data-ttu-id="a104c-127">不過，您可以按一下 [接收時間] 欄來變更它。</span><span class="sxs-lookup"><span data-stu-id="a104c-127">However, it can be changed by clicking the Time Received column.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a104c-128">使用者名稱</span><span class="sxs-lookup"><span data-stu-id="a104c-128">User Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="a104c-129">啟動事件的使用者。</span><span class="sxs-lookup"><span data-stu-id="a104c-129">The user who initiated the event.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="a104c-130">注意</span><span class="sxs-lookup"><span data-stu-id="a104c-130">Note</span></span></strong><br/><p><span data-ttu-id="a104c-131">如果在使用者登入時發生事件，則使用者名稱為 SYSTEM。</span><span class="sxs-lookup"><span data-stu-id="a104c-131">If the event occurred before a user logged on, the user name is SYSTEM.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a104c-132">主機名稱</span><span class="sxs-lookup"><span data-stu-id="a104c-132">Host Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="a104c-133">主機電腦的名稱。</span><span class="sxs-lookup"><span data-stu-id="a104c-133">The name of the host computer.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a104c-134">工作區名稱</span><span class="sxs-lookup"><span data-stu-id="a104c-134">Workspace Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="a104c-135">MED-V 工作區的名稱。</span><span class="sxs-lookup"><span data-stu-id="a104c-135">The name of the MED-V workspace.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a104c-136">工作區電腦名稱稱</span><span class="sxs-lookup"><span data-stu-id="a104c-136">Workspace Computer Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="a104c-137">MED-V 工作區正在執行的電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="a104c-137">The name of the computer the MED-V workspace is running on.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a104c-138">Online</span><span class="sxs-lookup"><span data-stu-id="a104c-138">Online</span></span></p></td>
<td align="left"><p><span data-ttu-id="a104c-139">用戶端電腦的目前狀態：</span><span class="sxs-lookup"><span data-stu-id="a104c-139">The current state of the client computer:</span></span></p>
<ul>
<li><p><strong><span data-ttu-id="a104c-140">被</span><span class="sxs-lookup"><span data-stu-id="a104c-140">Stopped</span></span></strong></p></li>
<li><p><strong><span data-ttu-id="a104c-141">在 &lt; 工作區開始的日期和時間開始&gt;</span><span class="sxs-lookup"><span data-stu-id="a104c-141">Started at &lt;date and time the workspace was started&gt;</span></span></strong></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a104c-142">用戶端版本</span><span class="sxs-lookup"><span data-stu-id="a104c-142">Client Version</span></span></p></td>
<td align="left"><p><span data-ttu-id="a104c-143">用戶端的版本號碼。</span><span class="sxs-lookup"><span data-stu-id="a104c-143">The version number of the client.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a104c-144">原則版本</span><span class="sxs-lookup"><span data-stu-id="a104c-144">Policy Version</span></span></p></td>
<td align="left"><p><span data-ttu-id="a104c-145">MED-V 工作區目前使用的原則版本。</span><span class="sxs-lookup"><span data-stu-id="a104c-145">The policy version that the MED-V workspace is currently using.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a104c-146">圖像名稱</span><span class="sxs-lookup"><span data-stu-id="a104c-146">Image Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="a104c-147">影像的名稱。</span><span class="sxs-lookup"><span data-stu-id="a104c-147">The name of the image.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a104c-148">影像版本</span><span class="sxs-lookup"><span data-stu-id="a104c-148">Image Version</span></span></p></td>
<td align="left"><p><span data-ttu-id="a104c-149">MED-V 工作區目前使用的影像版本。</span><span class="sxs-lookup"><span data-stu-id="a104c-149">The image version that the MED-V workspace is currently using.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="a104c-150">注意</span><span class="sxs-lookup"><span data-stu-id="a104c-150">Note</span></span></strong><br/><p><span data-ttu-id="a104c-151">如果 MED-V 的工作區版本尚未下載到電腦上，可能會是未知的。</span><span class="sxs-lookup"><span data-stu-id="a104c-151">MED-V workspace version can be Unknown if it has not yet been downloaded onto a computer.</span></span></p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-generatinganactivitylogreport"></a><span data-ttu-id="a104c-152">如何產生活動記錄報告</span><span class="sxs-lookup"><span data-stu-id="a104c-152">How to Generate an Activity Log Report</span></span>


**<span data-ttu-id="a104c-153">產生活動記錄報告</span><span class="sxs-lookup"><span data-stu-id="a104c-153">To generate an activity log report</span></span>**

1.  <span data-ttu-id="a104c-154">按一下 [**報告**管理] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="a104c-154">Click the **Reports** management button.</span></span>

    <span data-ttu-id="a104c-155">[報表] 模組隨即出現。</span><span class="sxs-lookup"><span data-stu-id="a104c-155">The Reports module appears.</span></span>

2.  <span data-ttu-id="a104c-156">在 [**報表**] 模組的 [**報表類型**] 功能表上，選取 [**活動記錄**]，然後按一下 [**產生**]。</span><span class="sxs-lookup"><span data-stu-id="a104c-156">In the **Reports** module, on the **Report Types** menu, select **Activity Log**, and click **Generate**.</span></span>

3.  <span data-ttu-id="a104c-157">在 [**報表參數**] 對話方塊中，設定下列一或多個參數：</span><span class="sxs-lookup"><span data-stu-id="a104c-157">In the **Report Parameters** dialog box, configure one or more of the following parameters:</span></span>

    -   <span data-ttu-id="a104c-158">**天數**—要顯示在報表中的天數。</span><span class="sxs-lookup"><span data-stu-id="a104c-158">**Number of days**—The number of days to display in the report.</span></span>

    -   <span data-ttu-id="a104c-159">[**使用者名稱**]：您的使用者名稱包含輸入之文字的任何事件，都包含在報表中。</span><span class="sxs-lookup"><span data-stu-id="a104c-159">**User name contains**—Any event where the user name contains the text entered is included in the report.</span></span>

    -   <span data-ttu-id="a104c-160">[**主機名稱**]：包含所輸入文字的任何事件，都包含在報告中。</span><span class="sxs-lookup"><span data-stu-id="a104c-160">**Host name contains**—Any event where the host name contains the text entered is included in the report.</span></span>

4.  <span data-ttu-id="a104c-161">按一下 \[確定\] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a104c-161">Click **OK**.</span></span>

    <span data-ttu-id="a104c-162">報告會在已選取事件和日期的情況下產生。</span><span class="sxs-lookup"><span data-stu-id="a104c-162">A report is generated with the events and dates selected.</span></span> <span data-ttu-id="a104c-163">報表參數是在下表中定義。</span><span class="sxs-lookup"><span data-stu-id="a104c-163">The report parameters are defined in the following table.</span></span>

**<span data-ttu-id="a104c-164">活動記錄報告屬性</span><span class="sxs-lookup"><span data-stu-id="a104c-164">Activity Log Report Properties</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a104c-165">屬性</span><span class="sxs-lookup"><span data-stu-id="a104c-165">Property</span></span></th>
<th align="left"><span data-ttu-id="a104c-166">描述</span><span class="sxs-lookup"><span data-stu-id="a104c-166">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a104c-167">事件識別碼</span><span class="sxs-lookup"><span data-stu-id="a104c-167">Event ID</span></span></p></td>
<td align="left"><p><span data-ttu-id="a104c-168">事件 ID。</span><span class="sxs-lookup"><span data-stu-id="a104c-168">The event ID.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a104c-169">嚴重性</span><span class="sxs-lookup"><span data-stu-id="a104c-169">Severity</span></span></p></td>
<td align="left"><p><strong><span data-ttu-id="a104c-170">資訊、錯誤、警告</span><span class="sxs-lookup"><span data-stu-id="a104c-170">Information, Error, Warning</span></span></strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a104c-171">類別</span><span class="sxs-lookup"><span data-stu-id="a104c-171">Category</span></span></p></td>
<td align="left"><p><span data-ttu-id="a104c-172">報告所參照的模組。</span><span class="sxs-lookup"><span data-stu-id="a104c-172">The module that the report is referring to.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a104c-173">描述</span><span class="sxs-lookup"><span data-stu-id="a104c-173">Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="a104c-174">事件的描述。</span><span class="sxs-lookup"><span data-stu-id="a104c-174">A description of the event.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a104c-175">收到時間</span><span class="sxs-lookup"><span data-stu-id="a104c-175">Time Received</span></span></p></td>
<td align="left"><p><span data-ttu-id="a104c-176">在伺服器上接收事件的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="a104c-176">The date and time the event was received on the server.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="a104c-177">注意</span><span class="sxs-lookup"><span data-stu-id="a104c-177">Note</span></span></strong><br/><p><span data-ttu-id="a104c-178">如果用戶端離線工作，伺服器會在用戶端線上時接收報告。</span><span class="sxs-lookup"><span data-stu-id="a104c-178">If the client is working offline, the server receives the reports when the client is online.</span></span></p>
</div>
<div>

</div>
<div class="alert">
<strong><span data-ttu-id="a104c-179">注意</span><span class="sxs-lookup"><span data-stu-id="a104c-179">Note</span></span></strong><br/><p><span data-ttu-id="a104c-180">根據預設，事件會以遞減的日期順序顯示。</span><span class="sxs-lookup"><span data-stu-id="a104c-180">By default, the events are displayed in descending date order.</span></span> <span data-ttu-id="a104c-181">不過，您可以按一下 [接收時間] 欄來變更它 <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="a104c-181">However, it can be changed by clicking the <strong>Time Received</strong> column.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a104c-182">用戶端時間</span><span class="sxs-lookup"><span data-stu-id="a104c-182">Client Time</span></span></p></td>
<td align="left"><p><span data-ttu-id="a104c-183">根據用戶端時鐘事件發生的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="a104c-183">The date and time the event occurred according to the client clock.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a104c-184">主機名稱</span><span class="sxs-lookup"><span data-stu-id="a104c-184">Host Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="a104c-185">主機電腦的名稱。</span><span class="sxs-lookup"><span data-stu-id="a104c-185">The name of the host computer.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a104c-186">使用者名稱</span><span class="sxs-lookup"><span data-stu-id="a104c-186">User Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="a104c-187">啟動事件的使用者。</span><span class="sxs-lookup"><span data-stu-id="a104c-187">The user who initiated the event.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a104c-188">工作區名稱</span><span class="sxs-lookup"><span data-stu-id="a104c-188">Workspace Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="a104c-189">MED-V 工作區的名稱。</span><span class="sxs-lookup"><span data-stu-id="a104c-189">The name of the MED-V workspace.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a104c-190">工作區電腦名稱稱</span><span class="sxs-lookup"><span data-stu-id="a104c-190">Workspace Computer Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="a104c-191">MED-V 工作區正在執行的電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="a104c-191">The name of the computer the MED-V workspace is running on.</span></span></p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-generatinganerrorlogreport"></a><span data-ttu-id="a104c-192">如何產生錯誤記錄報告</span><span class="sxs-lookup"><span data-stu-id="a104c-192">How to Generate an Error Log Report</span></span>


**<span data-ttu-id="a104c-193">產生錯誤記錄報告</span><span class="sxs-lookup"><span data-stu-id="a104c-193">To generate an error log report</span></span>**

1.  <span data-ttu-id="a104c-194">按一下 [**報告**管理] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="a104c-194">Click the **Reports** management button.</span></span>

2.  <span data-ttu-id="a104c-195">在 [**報表**] 模組的 [**報表類型**] 功能表上，選取 [**錯誤記錄**]，然後按一下 [**產生**]。</span><span class="sxs-lookup"><span data-stu-id="a104c-195">In the **Reports** module, on the **Report Types** menu, select **Error Log**, and click **Generate**.</span></span>

3.  <span data-ttu-id="a104c-196">在 [**報表參數**] 對話方塊中，設定下列一或多個參數：</span><span class="sxs-lookup"><span data-stu-id="a104c-196">In the **Report Parameters** dialog box, configure one or more of the following parameters:</span></span>

    -   <span data-ttu-id="a104c-197">**天數**—要顯示在報表中的天數。</span><span class="sxs-lookup"><span data-stu-id="a104c-197">**Number of days**—The number of days to display in the report.</span></span>

    -   <span data-ttu-id="a104c-198">[**使用者名稱**]：您的使用者名稱包含輸入之文字的任何事件，都包含在報表中。</span><span class="sxs-lookup"><span data-stu-id="a104c-198">**User name contains**—Any event where the user name contains the text entered is included in the report.</span></span>

    -   <span data-ttu-id="a104c-199">[**主機名稱**]：包含所輸入文字的任何事件，都包含在報告中。</span><span class="sxs-lookup"><span data-stu-id="a104c-199">**Host name contains**—Any event where the host name contains the text entered is included in the report.</span></span>

4.  <span data-ttu-id="a104c-200">按一下 \[確定\] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="a104c-200">Click **OK**.</span></span>

    <span data-ttu-id="a104c-201">報告會在已選取事件和日期的情況下產生。</span><span class="sxs-lookup"><span data-stu-id="a104c-201">A report is generated with the events and dates selected.</span></span> <span data-ttu-id="a104c-202">報表參數是在下表中定義。</span><span class="sxs-lookup"><span data-stu-id="a104c-202">The report parameters are defined in the following table.</span></span>

**<span data-ttu-id="a104c-203">錯誤記錄報表屬性</span><span class="sxs-lookup"><span data-stu-id="a104c-203">Error Log Report Properties</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="a104c-204">屬性</span><span class="sxs-lookup"><span data-stu-id="a104c-204">Property</span></span></th>
<th align="left"><span data-ttu-id="a104c-205">描述</span><span class="sxs-lookup"><span data-stu-id="a104c-205">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a104c-206">事件識別碼</span><span class="sxs-lookup"><span data-stu-id="a104c-206">Event ID</span></span></p></td>
<td align="left"><p><span data-ttu-id="a104c-207">事件 ID。</span><span class="sxs-lookup"><span data-stu-id="a104c-207">The event ID.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a104c-208">類別</span><span class="sxs-lookup"><span data-stu-id="a104c-208">Category</span></span></p></td>
<td align="left"><p><span data-ttu-id="a104c-209">報告所參照的模組。</span><span class="sxs-lookup"><span data-stu-id="a104c-209">The module that the report is referring to.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a104c-210">描述</span><span class="sxs-lookup"><span data-stu-id="a104c-210">Description</span></span></p></td>
<td align="left"><p><span data-ttu-id="a104c-211">事件的描述。</span><span class="sxs-lookup"><span data-stu-id="a104c-211">A description of the event.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a104c-212">收到時間</span><span class="sxs-lookup"><span data-stu-id="a104c-212">Time Received</span></span></p></td>
<td align="left"><p><span data-ttu-id="a104c-213">在伺服器上接收事件的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="a104c-213">The date and time the event was received on the server.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="a104c-214">注意</span><span class="sxs-lookup"><span data-stu-id="a104c-214">Note</span></span></strong><br/><p><span data-ttu-id="a104c-215">如果用戶端離線工作，伺服器會在用戶端線上時接收報告。</span><span class="sxs-lookup"><span data-stu-id="a104c-215">If the client is working offline, the server receives the reports when the client is online.</span></span></p>
</div>
<div>

</div>
<div class="alert">
<strong><span data-ttu-id="a104c-216">注意</span><span class="sxs-lookup"><span data-stu-id="a104c-216">Note</span></span></strong><br/><p><span data-ttu-id="a104c-217">根據預設，事件會以遞減的日期順序顯示。</span><span class="sxs-lookup"><span data-stu-id="a104c-217">By default, the events are displayed in descending date order.</span></span> <span data-ttu-id="a104c-218">不過，您可以按一下 [接收時間] 欄來變更它 <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="a104c-218">However, it can be changed by clicking the <strong>Time Received</strong> column.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a104c-219">用戶端時間</span><span class="sxs-lookup"><span data-stu-id="a104c-219">Client Time</span></span></p></td>
<td align="left"><p><span data-ttu-id="a104c-220">根據用戶端時鐘事件發生的日期和時間。</span><span class="sxs-lookup"><span data-stu-id="a104c-220">The date and time the event occurred according to the client clock.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a104c-221">主機名稱</span><span class="sxs-lookup"><span data-stu-id="a104c-221">Host Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="a104c-222">主機電腦的名稱。</span><span class="sxs-lookup"><span data-stu-id="a104c-222">The name of the host computer.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="a104c-223">使用者名稱</span><span class="sxs-lookup"><span data-stu-id="a104c-223">User Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="a104c-224">啟動事件的使用者。</span><span class="sxs-lookup"><span data-stu-id="a104c-224">The user who initiated the event.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="a104c-225">工作區名稱</span><span class="sxs-lookup"><span data-stu-id="a104c-225">Workspace Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="a104c-226">MED-V 工作區的名稱。</span><span class="sxs-lookup"><span data-stu-id="a104c-226">The name of the MED-V workspace.</span></span></p></td>
</tr>
</tbody>
</table>











