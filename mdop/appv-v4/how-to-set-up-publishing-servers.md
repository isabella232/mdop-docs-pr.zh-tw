---
title: 如何設定發佈伺服器
description: 如何設定發佈伺服器
author: dansimp
ms.assetid: 2111f079-c202-4c49-b2a6-f4237068b2dc
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2f060d862fd1449f5240ad495b53a1fa4e97697f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801053"
---
# <span data-ttu-id="325af-103">如何設定發佈伺服器</span><span class="sxs-lookup"><span data-stu-id="325af-103">How to Set Up Publishing Servers</span></span>


<span data-ttu-id="325af-104">您可以使用下列程式，直接從用戶端管理主控台新增及設定應用程式虛擬化伺服器。</span><span class="sxs-lookup"><span data-stu-id="325af-104">You can use the following procedures to add and configure Application Virtualization Servers directly from the Client Management Console.</span></span>

**<span data-ttu-id="325af-105">新增應用程式發佈伺服器</span><span class="sxs-lookup"><span data-stu-id="325af-105">To add an application publishing server</span></span>**

1.  <span data-ttu-id="325af-106">在 [**結果**] 窗格中，以滑鼠右鍵按一下，然後從快顯功能表中選取 [**新增伺服器**]，以啟動 [新的應用程式虛擬化伺服器] 嚮導，或者，以滑鼠右鍵按一下 [**發佈伺服器**] 節點，然後從快顯功能表中選取 [**新增伺服器**]。</span><span class="sxs-lookup"><span data-stu-id="325af-106">In the **Results** pane, right-click and select **New Server** from the pop-up-menu to start the New Application Virtualization Server Wizard, or alternatively, right-click the **Publishing Server** node and select **New Server** from the pop-up-menu.</span></span>

2.  <span data-ttu-id="325af-107">在嚮導的第一頁上，于 [**顯示名稱**] 欄位中輸入伺服器名稱，然後從 [**類型**] 下拉式清單中選取 [伺服器類型]。</span><span class="sxs-lookup"><span data-stu-id="325af-107">On page one of the wizard, enter the name of the server in the **Display Name** field and select the server type from the **Type** drop-down list.</span></span> <span data-ttu-id="325af-108">您可以從伺服器類型的下拉式清單中，選擇 [**應用程式虛擬化伺服器**]、[**增強的安全性應用程式虛擬化伺服器**]、[**標準 HTTP 伺服器**] 或 [**增強的安全性 HTTP 伺服器**]。</span><span class="sxs-lookup"><span data-stu-id="325af-108">You can choose **Application Virtualization Server**, **Enhanced Security Application Virtualization Server**, **Standard HTTP Server**, or **Enhanced Security HTTP Server** from the drop-down list of server types.</span></span>

3.  <span data-ttu-id="325af-109">按 **\[下一步\]**。</span><span class="sxs-lookup"><span data-stu-id="325af-109">Click **Next**.</span></span>

4.  <span data-ttu-id="325af-110">在嚮導的第二頁，請在 [**主機名稱**] 和 [**埠**] 欄位中輸入適當的資訊。</span><span class="sxs-lookup"><span data-stu-id="325af-110">On page two of the wizard, type the appropriate information into the **Host Name** and **Port** fields.</span></span> <span data-ttu-id="325af-111">應用程式虛擬化伺服器無法編輯**路徑**欄位。</span><span class="sxs-lookup"><span data-stu-id="325af-111">The **Path** field is not editable for Application Virtualization Servers.</span></span> <span data-ttu-id="325af-112">您必須輸入標準 HTTP 伺服器的路徑或增強的安全性 HTTP 伺服器。</span><span class="sxs-lookup"><span data-stu-id="325af-112">You must enter a path for Standard HTTP Server or Enhanced Security HTTP Server.</span></span>

5.  <span data-ttu-id="325af-113">按一下 **[完成]** 以新增伺服器。</span><span class="sxs-lookup"><span data-stu-id="325af-113">Click **Finish** to add the server.</span></span>

**<span data-ttu-id="325af-114">設定應用程式發佈伺服器</span><span class="sxs-lookup"><span data-stu-id="325af-114">To set up an application publishing server</span></span>**

1.  <span data-ttu-id="325af-115">在 [**結果**] 窗格中，以滑鼠右鍵按一下所需的伺服器，然後從快顯功能表中選取 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="325af-115">In the **Results** pane, right-click the desired server and select **Properties** from the pop-up menu.</span></span>

2.  <span data-ttu-id="325af-116">按一下 [**一般**] 索引標籤（您可以在其中變更伺服器名稱），從伺服器類型的下拉式清單中選取一種類型，然後指定主機名稱和埠。</span><span class="sxs-lookup"><span data-stu-id="325af-116">Click the **General** tab, where you can change the server name, select a type from the drop-down list of server types, and specify the host name and port.</span></span> <span data-ttu-id="325af-117">當伺服器類型是標準的 HTTP 伺服器或增強的安全性 HTTP 伺服器時，**路徑**欄位也是可編輯的。</span><span class="sxs-lookup"><span data-stu-id="325af-117">When the server type is Standard HTTP Server or Enhanced Security HTTP Server, the **Path** field is also editable.</span></span>

3.  <span data-ttu-id="325af-118">按一下 [重新**整理] 索引**標籤，此索引標籤會預設為已選取 [重新整理**使用者登**入] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="325af-118">Click the **Refresh** tab, where the **Refresh publishing on user login** check box is selected by default.</span></span> <span data-ttu-id="325af-119">若要變更重新整理比率，請選取 [重新整理**發佈**] 核取方塊，然後在欄位中輸入代表頻率的數位。</span><span class="sxs-lookup"><span data-stu-id="325af-119">To change the refresh rate, select the **Refresh publishing every** check box and enter a number that represents the frequency in the field.</span></span> <span data-ttu-id="325af-120">然後從下拉式功能表中選取 [**分鐘**]、[**小時**]、[**天**]。</span><span class="sxs-lookup"><span data-stu-id="325af-120">Then select **Minutes**, **Hours**, **Days** from the drop-down menu.</span></span> <span data-ttu-id="325af-121">（您可以輸入的最短時間為30分鐘。）</span><span class="sxs-lookup"><span data-stu-id="325af-121">(The minimum amount of time you can enter is 30 minutes.)</span></span>

4.  <span data-ttu-id="325af-122">按一下 **[** 套用] 以變更配置。</span><span class="sxs-lookup"><span data-stu-id="325af-122">Click **Apply** to change the configuration.</span></span>

5.  <span data-ttu-id="325af-123">發佈完成後，請按一下 **[確定**] 結束對話方塊，然後返回 [用戶端管理] 主控台。</span><span class="sxs-lookup"><span data-stu-id="325af-123">When you are finished publishing, click **OK** to exit the dialog box and return to the Client Management Console.</span></span>

## <span data-ttu-id="325af-124">相關主題</span><span class="sxs-lookup"><span data-stu-id="325af-124">Related topics</span></span>


[<span data-ttu-id="325af-125">如何停用或修改中斷連線的操作模式設定</span><span class="sxs-lookup"><span data-stu-id="325af-125">How to Disable or Modify Disconnected Operation Mode Settings</span></span>](how-to-disable-or-modify-disconnected-operation-mode-settings.md)

 

 





