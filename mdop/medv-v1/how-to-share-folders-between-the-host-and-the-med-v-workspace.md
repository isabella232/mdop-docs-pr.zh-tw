---
title: 如何在主機和 MED-V 工作區之間共用資料夾
description: 如何在主機和 MED-V 工作區之間共用資料夾
author: dansimp
ms.assetid: 3cb295f2-c07e-4ee6-aa3c-ce4c8c45c191
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 87f315c9894cd38834413d2549e652a36c5cc16d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811343"
---
# <span data-ttu-id="97d18-103">如何在主機和 MED-V 工作區之間共用資料夾</span><span class="sxs-lookup"><span data-stu-id="97d18-103">How to Share Folders Between the Host and the MED-V Workspace</span></span>


<span data-ttu-id="97d18-104">您可以在主機與 MED-V 工作區之間共用資料夾。</span><span class="sxs-lookup"><span data-stu-id="97d18-104">You can share folders between the host and the MED-V workspace.</span></span> <span data-ttu-id="97d18-105">共用資料夾可以儲存在下列各項：</span><span class="sxs-lookup"><span data-stu-id="97d18-105">The shared folders can be stored on the following:</span></span>

-   <span data-ttu-id="97d18-106">網路上的外部電腦</span><span class="sxs-lookup"><span data-stu-id="97d18-106">An external computer on the network</span></span>

-   <span data-ttu-id="97d18-107">主機電腦</span><span class="sxs-lookup"><span data-stu-id="97d18-107">The host computer</span></span>

<span data-ttu-id="97d18-108">下列程式示範如何在主機與 MED-V 工作區之間共用資料夾。</span><span class="sxs-lookup"><span data-stu-id="97d18-108">The following procedures demonstrate how to share folders between the host and the MED-V workspace.</span></span>

**<span data-ttu-id="97d18-109">共用位於網路上的資料夾</span><span class="sxs-lookup"><span data-stu-id="97d18-109">To share folders located on the network</span></span>**

1.  <span data-ttu-id="97d18-110">在完整桌面圖案中設定 MED-V。</span><span class="sxs-lookup"><span data-stu-id="97d18-110">Configure MED-V in full desktop mode.</span></span>

2.  <span data-ttu-id="97d18-111">在 MED-V 管理的 [網路] 索引標籤上，按一下 [**使用與主機不同的 IP 位址] （橋接器）**。</span><span class="sxs-lookup"><span data-stu-id="97d18-111">In MED-V management, on the Network tab, click **Use different IP address than host (Bridge)**.</span></span>

3.  <span data-ttu-id="97d18-112">在主機電腦上執行下列動作：</span><span class="sxs-lookup"><span data-stu-id="97d18-112">Do the following on the host computer:</span></span>

    1.  <span data-ttu-id="97d18-113">在 [控制台] 中，按一下 [**查看網路狀態及**工作]，然後將**網路探索**設定為 [**開啟**]。</span><span class="sxs-lookup"><span data-stu-id="97d18-113">In Control Panel, click **View network status and tasks**, and set **Network discovery** to **On**.</span></span>

    2.  <span data-ttu-id="97d18-114">在 [開始] 功能表上，以滑鼠右鍵按一下 [**電腦**]，然後按一下 [**對應網路磁片磁碟機**]。</span><span class="sxs-lookup"><span data-stu-id="97d18-114">On the Start menu, right-click **Computer**, and click **Map network drive**.</span></span>

    3.  <span data-ttu-id="97d18-115">在 [**對應網路磁碟機**] 對話方塊的 [**磁碟機**] 欄位中，選取一個磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="97d18-115">In the **Map Network Drive** dialog box, in the **Drive** field, select a drive.</span></span>

        <span data-ttu-id="97d18-116">**記事** 確定兩部電腦不使用相同的磁碟機盤符。</span><span class="sxs-lookup"><span data-stu-id="97d18-116">**Note** Ensure that the same drive letter is not in use on both computers.</span></span>

         

    4.  <span data-ttu-id="97d18-117">按一下 \[瀏覽\]。\*\*\*\*</span><span class="sxs-lookup"><span data-stu-id="97d18-117">Click **Browse**.</span></span>

    5.  <span data-ttu-id="97d18-118">在 [**流覽資料夾**] 對話方塊中，流覽至共用的磁片磁碟機，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="97d18-118">In the **Browse For Folder** dialog box, browse to the shared drive, and click **OK**.</span></span>

    6.  <span data-ttu-id="97d18-119">按一下 **\[完成\]**。</span><span class="sxs-lookup"><span data-stu-id="97d18-119">Click **Finish**.</span></span>

4.  <span data-ttu-id="97d18-120">在 MED-V 工作區中重複步驟3。</span><span class="sxs-lookup"><span data-stu-id="97d18-120">Repeat step 3 in the MED-V workspace.</span></span> <span data-ttu-id="97d18-121">指向主機電腦上的同一個磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="97d18-121">Point to the same drive as on the host computer.</span></span>

**<span data-ttu-id="97d18-122">共用位於主機上的資料夾</span><span class="sxs-lookup"><span data-stu-id="97d18-122">To share folders located on the host</span></span>**

1.  <span data-ttu-id="97d18-123">將資料夾設定為與適當的許可權共用。</span><span class="sxs-lookup"><span data-stu-id="97d18-123">Configure the folder to be shared with the appropriate permissions.</span></span>

2.  <span data-ttu-id="97d18-124">從 MED-V 工作區，移至 [**網路位置**] 並找出共用資料夾。</span><span class="sxs-lookup"><span data-stu-id="97d18-124">From the MED-V workspace, go to **My network places** and locate the shared folder.</span></span>

3.  <span data-ttu-id="97d18-125">從 MED-V 工作區，找出共用資料夾。</span><span class="sxs-lookup"><span data-stu-id="97d18-125">From the MED-V workspace, locate the shared folder.</span></span>

<span data-ttu-id="97d18-126">**記事** 確定主機和 MED-V 工作區電腦都在同一個網域或工作組中。</span><span class="sxs-lookup"><span data-stu-id="97d18-126">**Note** Ensure that both the host and MED-V workspace computers are in the same domain or workgroup.</span></span>

 

 

 





