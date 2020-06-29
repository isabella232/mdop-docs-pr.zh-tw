---
title: MED-V 用戶端工具
description: MED-V 用戶端工具
author: dansimp
ms.assetid: ea18d82e-2433-4754-85ac-6eac84bcbb01
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0e4ae67b8327e41bf5798c1d0d3fcb6253bf3b02
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810304"
---
# <span data-ttu-id="1287b-103">MED-V 用戶端工具</span><span class="sxs-lookup"><span data-stu-id="1287b-103">MED-V Client Tools</span></span>


<span data-ttu-id="1287b-104">MED-V 包含下列用戶端工具：</span><span class="sxs-lookup"><span data-stu-id="1287b-104">MED-V includes the following client tools:</span></span>

-   [<span data-ttu-id="1287b-105">檔案傳輸工具</span><span class="sxs-lookup"><span data-stu-id="1287b-105">File Transfer Tool</span></span>](#bkmk-filetransfertool)

-   [<span data-ttu-id="1287b-106">影像下載</span><span class="sxs-lookup"><span data-stu-id="1287b-106">Image Downloads</span></span>](#bkmk-imagedownloads)

-   [<span data-ttu-id="1287b-107">診斷</span><span class="sxs-lookup"><span data-stu-id="1287b-107">Diagnostics</span></span>](#bkmk-diagnostics)

## <a href="" id="bkmk-filetransfertool"></a><span data-ttu-id="1287b-108">檔案傳輸工具</span><span class="sxs-lookup"><span data-stu-id="1287b-108">File Transfer Tool</span></span>


<span data-ttu-id="1287b-109">檔案傳輸工具可用於將 MED-V 工作區中的檔案或資料夾複製到主機，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="1287b-109">The File Transfer Tool can be used to copy files or folders from the MED-V workspace to the host and vice versa.</span></span>

<span data-ttu-id="1287b-110">**記事** 只有在執行 MED-V 工作區時，才會啟用檔案傳輸工具。</span><span class="sxs-lookup"><span data-stu-id="1287b-110">**Note** The File Transfer Tool is enabled only when the MED-V workspace is running.</span></span>

 

**<span data-ttu-id="1287b-111">從目前正在執行的 MED-V 工作區複製檔案或資料夾</span><span class="sxs-lookup"><span data-stu-id="1287b-111">To copy files or folders from a MED-V workspace that is currently running</span></span>**

1.  <span data-ttu-id="1287b-112">在通知區域中，以滑鼠右鍵按一下 MED-V 圖示。</span><span class="sxs-lookup"><span data-stu-id="1287b-112">In the notification area, right-click the MED-V icon.</span></span>

2.  <span data-ttu-id="1287b-113">在子功能表上，指向 [**工具**]，然後按一下 [檔案**傳輸**]。</span><span class="sxs-lookup"><span data-stu-id="1287b-113">On the submenu, point to **Tools**, and then click **File Transfer**.</span></span>

3.  <span data-ttu-id="1287b-114">在檔案**傳輸**工具的 [**選取方向**] 欄位中，按一下下列其中一個傳輸選項：</span><span class="sxs-lookup"><span data-stu-id="1287b-114">In the **File Transfer** tool, in the **Select transfer direction** field, click one of the following transfer options:</span></span>

    -   <span data-ttu-id="1287b-115">**從 [我的電腦] 複製到 [預設工作區] 工作區**—將檔案或資料夾從主機轉移至作用中的 med-v 工作區。</span><span class="sxs-lookup"><span data-stu-id="1287b-115">**Copy from My Computer to 'default workspace' Workspace**—Transfer a file or folder from the host to the active MED-V workspace.</span></span>

    -   <span data-ttu-id="1287b-116">**從 [預設工作區] 工作區複製到 [我的電腦**] —將活動的 med-v 工作區中的檔案或資料夾傳送到主機。</span><span class="sxs-lookup"><span data-stu-id="1287b-116">**Copy from 'default workspace' Workspace to My Computer**—Transfer a file or folder from the active MED-V workspace to the host.</span></span>

4.  <span data-ttu-id="1287b-117">執行下列其中一項動作，以選取要複製的檔案或資料夾：</span><span class="sxs-lookup"><span data-stu-id="1287b-117">Select the file or folder to copy by doing one of the following:</span></span>

    -   <span data-ttu-id="1287b-118">在 [**要複製**的檔案] 欄位中，輸入要複製之檔案或資料夾所在之目錄的完整路徑。</span><span class="sxs-lookup"><span data-stu-id="1287b-118">In the **File to copy** field, type the full path to the directory where the file or folder to copy is located.</span></span>

    -   <span data-ttu-id="1287b-119">按一下 **[流覽**]，流覽要複製之檔案或資料夾所在的目錄。</span><span class="sxs-lookup"><span data-stu-id="1287b-119">Click **Browse** to browse the directory where the file or folder to copy is located.</span></span>

5.  <span data-ttu-id="1287b-120">選取 [**複製資料夾**] 核取方塊以複製整個資料夾。</span><span class="sxs-lookup"><span data-stu-id="1287b-120">Select the **Copy a folder** check box to copy an entire folder.</span></span>

6.  <span data-ttu-id="1287b-121">執行下列其中一項動作，選取要轉移檔案的目的地：</span><span class="sxs-lookup"><span data-stu-id="1287b-121">Select the destination where the file is being transferred by doing one of the following:</span></span>

    -   <span data-ttu-id="1287b-122">在 [ **Destination** ] （目的地）欄位中，輸入要傳輸檔案或資料夾之目錄的完整路徑。</span><span class="sxs-lookup"><span data-stu-id="1287b-122">In the **Destination** field, type the full path of the directory where the file or folder will be transferred.</span></span>

    -   <span data-ttu-id="1287b-123">按一下 **[流覽**]，流覽至要傳送檔案或資料夾的目錄。</span><span class="sxs-lookup"><span data-stu-id="1287b-123">Click **Browse** to browse to the directory where the file or folder will be transferred.</span></span>

7.  <span data-ttu-id="1287b-124">按一下 **\[開始\]**。</span><span class="sxs-lookup"><span data-stu-id="1287b-124">Click **Start**.</span></span>

    <span data-ttu-id="1287b-125">檔案傳輸開始。</span><span class="sxs-lookup"><span data-stu-id="1287b-125">The file transfer begins.</span></span>

## <a href="" id="bkmk-imagedownloads"></a><span data-ttu-id="1287b-126">影像下載</span><span class="sxs-lookup"><span data-stu-id="1287b-126">Image Downloads</span></span>


<span data-ttu-id="1287b-127">當 MED-V 工作區有新的影像更新，而 MED-V 工作區是作用中時，使用者就會收到一則訊息，指出已準備好下載新的影像。</span><span class="sxs-lookup"><span data-stu-id="1287b-127">When a new image update is available for a MED-V workspace and the MED-V workspace is active, the user receives a message indicating that a new image is ready for download.</span></span>

**<span data-ttu-id="1287b-128">若要查看可供下載的影像</span><span class="sxs-lookup"><span data-stu-id="1287b-128">To view available images for download</span></span>**

1.  <span data-ttu-id="1287b-129">在通知區域中，以滑鼠右鍵按一下 MED-V 圖示。</span><span class="sxs-lookup"><span data-stu-id="1287b-129">In the notification area, right-click the MED-V icon.</span></span>

2.  <span data-ttu-id="1287b-130">在子功能表上，指向 [**工具**]，然後按一下 [**影像下載**]。</span><span class="sxs-lookup"><span data-stu-id="1287b-130">On the submenu, point to **Tools**, and then click **Image Downloads**.</span></span>

    <span data-ttu-id="1287b-131">隨即會顯示所有可用的圖像下載。</span><span class="sxs-lookup"><span data-stu-id="1287b-131">All available image downloads are displayed.</span></span>

## <a href="" id="bkmk-diagnostics"></a><span data-ttu-id="1287b-132">診斷</span><span class="sxs-lookup"><span data-stu-id="1287b-132">Diagnostics</span></span>


<span data-ttu-id="1287b-133">診斷工具提供所有診斷資訊。</span><span class="sxs-lookup"><span data-stu-id="1287b-133">The diagnostics tool provides all diagnostic information.</span></span>

**<span data-ttu-id="1287b-134">若要查看診斷</span><span class="sxs-lookup"><span data-stu-id="1287b-134">To view diagnostics</span></span>**

1.  <span data-ttu-id="1287b-135">在通知區域中，以滑鼠右鍵按一下 MED-V 圖示。</span><span class="sxs-lookup"><span data-stu-id="1287b-135">In the notification area, right-click the MED-V icon.</span></span>

2.  <span data-ttu-id="1287b-136">在子功能表**上，指向**[說明]，然後按一下 [ **med-v 診斷**]。</span><span class="sxs-lookup"><span data-stu-id="1287b-136">On the submenu, point to **Help**, and then click **MED-V Diagnostics**.</span></span>

3.  <span data-ttu-id="1287b-137">在**診斷**工具中，查看所有診斷資訊。</span><span class="sxs-lookup"><span data-stu-id="1287b-137">In the **Diagnostics** tool, review all diagnostic information.</span></span>

<span data-ttu-id="1287b-138">您可以使用診斷工具來執行下列函數：</span><span class="sxs-lookup"><span data-stu-id="1287b-138">The following functions can be performed using the diagnostic tool:</span></span>

-   <span data-ttu-id="1287b-139">收集診斷記錄-收集診斷記錄，並將它們放在桌面上。</span><span class="sxs-lookup"><span data-stu-id="1287b-139">Gather diagnostic logs—Gather the diagnostic logs, and place them on the desktop.</span></span>

-   <span data-ttu-id="1287b-140">更新原則： MED-V 工作區原則會自動連線至 MED-V 伺服器，每15分鐘重新整理一次原則。</span><span class="sxs-lookup"><span data-stu-id="1287b-140">Update policy—The MED-V workspace policy automatically connects to the MED-V server to refresh the policy every 15 minutes.</span></span> <span data-ttu-id="1287b-141">不過，使用者可以使用這個選項，立即執行手動更新。</span><span class="sxs-lookup"><span data-stu-id="1287b-141">However, a user can use this option to perform a manual refresh immediately.</span></span>

-   <span data-ttu-id="1287b-142">啟用或停用 [診斷模式]-顯示 [虛擬機器] 視窗。</span><span class="sxs-lookup"><span data-stu-id="1287b-142">Enable or Disable diagnostic mode—Display the virtual machine window.</span></span> <span data-ttu-id="1287b-143">例如，當您需要查看不會顯示的 MED-V 工作區視窗時，這個函數很有説明。</span><span class="sxs-lookup"><span data-stu-id="1287b-143">This function is helpful when, for example, you need to see MED-V workspace windows that are not displayed.</span></span>

-   <span data-ttu-id="1287b-144">流覽影像存放區-查看所有可用的 MED-V 工作區影像。</span><span class="sxs-lookup"><span data-stu-id="1287b-144">Browse image store—View all available MED-V workspace images.</span></span>

 

 





