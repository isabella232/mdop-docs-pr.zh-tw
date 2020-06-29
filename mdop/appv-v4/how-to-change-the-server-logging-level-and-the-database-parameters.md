---
title: 如何變更伺服器登入層級和資料庫參數
description: 如何變更伺服器登入層級和資料庫參數
author: dansimp
ms.assetid: e3ebaee5-6c4c-4aa8-9766-c5aeb00f477a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: bb35ac09c5e23f4847662171b68284f868e66dee
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801654"
---
# <span data-ttu-id="899de-103">如何變更伺服器登入層級和資料庫參數</span><span class="sxs-lookup"><span data-stu-id="899de-103">How to Change the Server Logging Level and the Database Parameters</span></span>


<span data-ttu-id="899de-104">您可以使用下列程式來變更應用程式虛擬化伺服器管理主控台的記錄層級和資料庫記錄參數。</span><span class="sxs-lookup"><span data-stu-id="899de-104">You can use the following procedures to change the logging level and the database log parameters from the Application Virtualization Server Management Console.</span></span>

<span data-ttu-id="899de-105">提供下列記錄層級：</span><span class="sxs-lookup"><span data-stu-id="899de-105">The following logging levels are available:</span></span>

-   <span data-ttu-id="899de-106">僅交易</span><span class="sxs-lookup"><span data-stu-id="899de-106">Transaction Only</span></span>

-   <span data-ttu-id="899de-107">致命錯誤</span><span class="sxs-lookup"><span data-stu-id="899de-107">Fatal Errors</span></span>

-   <span data-ttu-id="899de-108">錯誤</span><span class="sxs-lookup"><span data-stu-id="899de-108">Errors</span></span>

-   <span data-ttu-id="899de-109">警告/錯誤</span><span class="sxs-lookup"><span data-stu-id="899de-109">Warnings/Errors</span></span>

-   <span data-ttu-id="899de-110">資訊/警告/錯誤</span><span class="sxs-lookup"><span data-stu-id="899de-110">Info/Warnings/Errors</span></span>

-   <span data-ttu-id="899de-111">冗長</span><span class="sxs-lookup"><span data-stu-id="899de-111">Verbose</span></span>

<span data-ttu-id="899de-112">**記事** 由於您使用**詳細**模式時所產生的記錄檔案大小，因此建議您不要使用此記錄集等級設定來執行生產伺服器。</span><span class="sxs-lookup"><span data-stu-id="899de-112">**Note** Because of the size of the log file produced when you use **Verbose** mode, the recommendation is that you do not run production servers with this level of logging set.</span></span>

 

<span data-ttu-id="899de-113">資料庫記錄參數決定了資料庫驅動程式類型、存取認證及記錄資料庫的位置。</span><span class="sxs-lookup"><span data-stu-id="899de-113">The database logging parameters determine the database driver type, access credentials, and location of the logging database.</span></span>

**<span data-ttu-id="899de-114">若要變更管理伺服器的記錄層級</span><span class="sxs-lookup"><span data-stu-id="899de-114">To change the logging level for Management Servers</span></span>**

1.  <span data-ttu-id="899de-115">按一下 [**伺服器群組**] 節點，以顯示 [伺服器群組]。</span><span class="sxs-lookup"><span data-stu-id="899de-115">Click the **Server Groups** node to display the server groups.</span></span>

2.  <span data-ttu-id="899de-116">以滑鼠右鍵按一下 [伺服器] 群組，然後選取 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="899de-116">Right-click the server group, and select **Properties**.</span></span>

3.  <span data-ttu-id="899de-117">在 [**屬性**] 對話方塊中，選取 [**記錄**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="899de-117">In the **Properties** dialog box, select the **Logging** tab.</span></span>

4.  <span data-ttu-id="899de-118">在 [**伺服器群組屬性**] 對話方塊中，選取伺服器，然後按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="899de-118">In the **Server Group Properties** dialog box, select the server and then click **Edit**.</span></span>

5.  <span data-ttu-id="899de-119">在 [**新增/編輯記錄模組**] 對話方塊中，從 [**事件種類**] 下拉式清單中選取記錄層級。</span><span class="sxs-lookup"><span data-stu-id="899de-119">In the **Add/Edit Log Module** dialog box, select the logging level from the **Event Type** drop-down list.</span></span>

6.  <span data-ttu-id="899de-120">按一下 \[確定\] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="899de-120">Click **OK**.</span></span>

7.  <span data-ttu-id="899de-121">在 [**伺服器群組屬性**] 對話方塊中，按一下 **[確定] 或 [套用]** 。 **Apply**</span><span class="sxs-lookup"><span data-stu-id="899de-121">In the **Server Group Properties** dialog box, click **OK** or **Apply**.</span></span>

**<span data-ttu-id="899de-122">變更流式處理伺服器的記錄層級</span><span class="sxs-lookup"><span data-stu-id="899de-122">To change the logging level for Streaming Servers</span></span>**

1.  <span data-ttu-id="899de-123">編輯下列登錄機碼值，以變更記錄層級：</span><span class="sxs-lookup"><span data-stu-id="899de-123">Edit the following registry key value to change the logging level:</span></span>

    -   <span data-ttu-id="899de-124">HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\DistributionServer\\LogLevel</span><span class="sxs-lookup"><span data-stu-id="899de-124">HKEY\_LOCAL\_MACHINE\\SOFTWARE\\Microsoft\\SoftGrid\\4.5\\DistributionServer\\LogLevel</span></span>

2.  <span data-ttu-id="899de-125">選取下列其中一個值來設定記錄層級。</span><span class="sxs-lookup"><span data-stu-id="899de-125">Select one of the following values to set the logging level.</span></span>

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><span data-ttu-id="899de-126">值</span><span class="sxs-lookup"><span data-stu-id="899de-126">Value</span></span></th>
    <th align="left"><span data-ttu-id="899de-127">記錄層級</span><span class="sxs-lookup"><span data-stu-id="899de-127">Logging Level</span></span></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="899de-128">0</span><span class="sxs-lookup"><span data-stu-id="899de-128">0</span></span></p></td>
    <td align="left"><p><span data-ttu-id="899de-129">僅交易</span><span class="sxs-lookup"><span data-stu-id="899de-129">Transactions Only</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="899de-130">sr-1</span><span class="sxs-lookup"><span data-stu-id="899de-130">1</span></span></p></td>
    <td align="left"><p><span data-ttu-id="899de-131">致命錯誤</span><span class="sxs-lookup"><span data-stu-id="899de-131">Fatal Errors</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="899de-132">pplx-2</span><span class="sxs-lookup"><span data-stu-id="899de-132">2</span></span></p></td>
    <td align="left"><p><span data-ttu-id="899de-133">錯誤</span><span class="sxs-lookup"><span data-stu-id="899de-133">Errors</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="899de-134">3</span><span class="sxs-lookup"><span data-stu-id="899de-134">3</span></span></p></td>
    <td align="left"><p><span data-ttu-id="899de-135">警告/錯誤</span><span class="sxs-lookup"><span data-stu-id="899de-135">Warnings/Errors</span></span></p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><span data-ttu-id="899de-136">4</span><span class="sxs-lookup"><span data-stu-id="899de-136">4</span></span></p></td>
    <td align="left"><p><span data-ttu-id="899de-137">資訊/警告/錯誤</span><span class="sxs-lookup"><span data-stu-id="899de-137">Information/ Warnings/Errors</span></span></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><span data-ttu-id="899de-138">500</span><span class="sxs-lookup"><span data-stu-id="899de-138">5</span></span></p></td>
    <td align="left"><p><span data-ttu-id="899de-139">冗長</span><span class="sxs-lookup"><span data-stu-id="899de-139">Verbose</span></span></p></td>
    </tr>
    </tbody>
    </table>

     

**<span data-ttu-id="899de-140">變更資料庫記錄參數</span><span class="sxs-lookup"><span data-stu-id="899de-140">To change database log parameters</span></span>**

1.  <span data-ttu-id="899de-141">按一下 [**伺服器群組**] 節點，以顯示 [伺服器群組]。</span><span class="sxs-lookup"><span data-stu-id="899de-141">Click the **Server Groups** node to display the server groups.</span></span>

2.  <span data-ttu-id="899de-142">以滑鼠右鍵按一下 [伺服器] 群組，然後選取 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="899de-142">Right-click the server group, and select **Properties**.</span></span>

3.  <span data-ttu-id="899de-143">在 [**屬性**] 對話方塊中，選取 [**記錄**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="899de-143">In the **Properties** dialog box, select the **Logging** tab.</span></span>

4.  <span data-ttu-id="899de-144">在 [**伺服器群組屬性**] 對話方塊中，選取伺服器，然後按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="899de-144">In the **Server Group Properties** dialog box, select the server and then click **Edit**.</span></span>

5.  <span data-ttu-id="899de-145">在 [**新增/編輯記錄模組**] 對話方塊中，從 [**資料庫驅動程式**] 下拉式清單中選取資料庫驅動程式。</span><span class="sxs-lookup"><span data-stu-id="899de-145">In the **Add/Edit Log Module** dialog box, select a database driver from the **Database Driver** drop-down list.</span></span>

6.  <span data-ttu-id="899de-146">輸入**DNS 主機名稱**。</span><span class="sxs-lookup"><span data-stu-id="899de-146">Enter a **DNS Host Name**.</span></span>

7.  <span data-ttu-id="899de-147">按一下 [**動態判斷埠**] 核取方塊，或在 [**埠**] 欄位中輸入埠號碼。</span><span class="sxs-lookup"><span data-stu-id="899de-147">Click the **Dynamically Determine Port** check box, or enter a port number in the **Port** field.</span></span>

8.  <span data-ttu-id="899de-148">在對應欄位中輸入**服務名稱**。</span><span class="sxs-lookup"><span data-stu-id="899de-148">Enter a **Service Name** in the corresponding field.</span></span>

9.  <span data-ttu-id="899de-149">按一下 \[確定\] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="899de-149">Click **OK**.</span></span>

10. <span data-ttu-id="899de-150">在 [**伺服器群組屬性**] 對話方塊中，按一下 **[確定] 或 [套用]** 。 **Apply**</span><span class="sxs-lookup"><span data-stu-id="899de-150">On the **Server Group Properties** dialog box, click **OK** or **Apply**.</span></span>

## <span data-ttu-id="899de-151">相關主題</span><span class="sxs-lookup"><span data-stu-id="899de-151">Related topics</span></span>


[<span data-ttu-id="899de-152">如何在伺服器管理主控台中自訂 Application Virtualization 系統</span><span class="sxs-lookup"><span data-stu-id="899de-152">How to Customize an Application Virtualization System in the Server Management Console</span></span>](how-to-customize-an-application-virtualization-system-in-the-server-management-console.md)

 

 





