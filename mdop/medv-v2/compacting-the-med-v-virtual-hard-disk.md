---
title: 壓縮 MED-V 虛擬硬碟
description: 壓縮 MED-V 虛擬硬碟
author: dansimp
ms.assetid: 5e6122d1-9847-4b33-adab-594919eec3c5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f71aefb1e4e901078b4d0a421065b7bd5acdf0ee
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809860"
---
# <span data-ttu-id="c755d-103">壓縮 MED-V 虛擬硬碟</span><span class="sxs-lookup"><span data-stu-id="c755d-103">Compacting the MED-V Virtual Hard Disk</span></span>


<span data-ttu-id="c755d-104">雖然它是選擇性的，但您可以壓縮虛擬硬碟（VHD）來回收空白磁碟空間，並在設定 Windows 虛擬電腦影像之前減少 VHD 大小。</span><span class="sxs-lookup"><span data-stu-id="c755d-104">Although it is optional, you can compact the virtual hard disk (VHD) to reclaim empty disk space and reduce the size of the VHD before you configure the Windows Virtual PC image.</span></span>

<span data-ttu-id="c755d-105">**重要** 在您繼續進行之前，請先建立 Windows XP 映射的備份複本。</span><span class="sxs-lookup"><span data-stu-id="c755d-105">**Important** Before you proceed, create a backup copy of your Windows XP image.</span></span>

 

**<span data-ttu-id="c755d-106">準備虛擬硬碟</span><span class="sxs-lookup"><span data-stu-id="c755d-106">Preparing the Virtual Hard Disk</span></span>**

1.  <span data-ttu-id="c755d-107">開啟您的 Windows XP 影像。</span><span class="sxs-lookup"><span data-stu-id="c755d-107">Open your Windows XP image.</span></span>

    <span data-ttu-id="c755d-108">按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **windows 虛擬電腦**]，按一下 [ **windows 虛擬電腦**]，然後按兩下您的 Windows XP 影像。</span><span class="sxs-lookup"><span data-stu-id="c755d-108">Click **Start**, click **All Programs**, click **Windows Virtual PC**, click **Windows Virtual PC**, then double-click your Windows XP image.</span></span>

2.  <span data-ttu-id="c755d-109">清除 DLL 快取。</span><span class="sxs-lookup"><span data-stu-id="c755d-109">Clear the DLL cache.</span></span>

    1.  <span data-ttu-id="c755d-110">在虛擬機器的命令提示字元中，輸入**sfc/cachesize = 1**。</span><span class="sxs-lookup"><span data-stu-id="c755d-110">At a command prompt in the virtual machine, type **sfc /cachesize=1**.</span></span>

    2.  <span data-ttu-id="c755d-111">重新開機虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="c755d-111">Restart the virtual machine.</span></span>

    3.  <span data-ttu-id="c755d-112">在虛擬機器的命令提示字元中，輸入**sfc/purgecache**。</span><span class="sxs-lookup"><span data-stu-id="c755d-112">At a command prompt in the virtual machine, type **sfc /purgecache**.</span></span>

3.  <span data-ttu-id="c755d-113">刪除不必要的檔案，例如 uninstallers、temp 檔案、記錄檔、頁面檔案、共用資料夾等。</span><span class="sxs-lookup"><span data-stu-id="c755d-113">Delete unnecessary files, such as uninstallers, temp files, log files, page files, shared folders, and so on.</span></span>

4.  <span data-ttu-id="c755d-114">關閉系統還原。</span><span class="sxs-lookup"><span data-stu-id="c755d-114">Turn off System Restore.</span></span> <span data-ttu-id="c755d-115">您也可以在 Sysprep.inf 檔案中指定此步驟。</span><span class="sxs-lookup"><span data-stu-id="c755d-115">You can also specify this step in your Sysprep.inf file.</span></span>

    1.  <span data-ttu-id="c755d-116">在 [**控制台**] 中，按兩下 [**系統**]，然後選取 [**系統還原**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="c755d-116">In **Control Panel**, double-click **System**, and then select the **System Restore** tab.</span></span>

    2.  <span data-ttu-id="c755d-117">選取 [**關閉系統還原**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="c755d-117">Select **Turn off System Restore**, and then click **OK**.</span></span>

5.  <span data-ttu-id="c755d-118">設定最大事件記錄大小並清除所有事件。</span><span class="sxs-lookup"><span data-stu-id="c755d-118">Set maximum event log sizes and clear all events.</span></span>

    1.  <span data-ttu-id="c755d-119">開啟 [事件檢視器]。</span><span class="sxs-lookup"><span data-stu-id="c755d-119">Open the event viewer.</span></span>

        <span data-ttu-id="c755d-120">按一下 [**開始**]，按一下 [**控制台**]，按兩下 [系統**管理工具**]，然後按兩下 [**事件檢視器**]。</span><span class="sxs-lookup"><span data-stu-id="c755d-120">Click **Start**, click **Control Panel**, double-click **Administrative Tools**, then double-click **Event Viewer**.</span></span>

    2.  <span data-ttu-id="c755d-121">以滑鼠右鍵按一下 [**應用程式**]，然後按一下 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="c755d-121">Right-click **Application**, and click **Properties**.</span></span>

    3.  <span data-ttu-id="c755d-122">在 [**記錄大小**] 區域中，將 [**最大記錄大小**] 設定為512kb，然後選取 [**視需要覆寫事件**]。</span><span class="sxs-lookup"><span data-stu-id="c755d-122">In the **Log Size** area, set **Maximum Log Size** to 512KB and then select **Overwrite events as needed**.</span></span>

    4.  <span data-ttu-id="c755d-123">按一下 [**清除記錄**]。</span><span class="sxs-lookup"><span data-stu-id="c755d-123">Click **Clear Log**.</span></span> <span data-ttu-id="c755d-124">在出現的 [**事件檢視器**] 對話方塊中，按一下 [**否**]。</span><span class="sxs-lookup"><span data-stu-id="c755d-124">In the **Event Viewer** dialog box that appears, click **No**.</span></span>

    5.  <span data-ttu-id="c755d-125">按一下 [**屬性**] 視窗中的 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="c755d-125">In the **Properties** window, click **OK**.</span></span>

    6.  <span data-ttu-id="c755d-126">針對**安全性**與**系統**記錄，重複步驟 a 至 e。</span><span class="sxs-lookup"><span data-stu-id="c755d-126">Repeat steps a through e for the **Security** and **System** logs.</span></span>

6.  <span data-ttu-id="c755d-127">執行磁片清理工具。</span><span class="sxs-lookup"><span data-stu-id="c755d-127">Run the Disk Cleanup Tool.</span></span>

    <span data-ttu-id="c755d-128">按一下 [**開始**]，按一下 [**所有程式**]，按一下 [**附件**]，按一下 [**系統工具**]，然後按一下 [**磁片清理**]。</span><span class="sxs-lookup"><span data-stu-id="c755d-128">Click **Start**, click **All Programs**, click **Accessories**, click **System Tools**, and then click **Disk Cleanup**.</span></span>

7.  <span data-ttu-id="c755d-129">視需要為您的應用程式設定頁面檔案。</span><span class="sxs-lookup"><span data-stu-id="c755d-129">Configure your page file as needed for your applications.</span></span>

    1.  <span data-ttu-id="c755d-130">在 [**控制台**] 中，按兩下 [**系統**]，然後選取 [**高級**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="c755d-130">In **Control Panel**, double-click **System**, and then select the **Advanced** tab.</span></span>

    2.  <span data-ttu-id="c755d-131">在 [**效能**] 區域中，按一下 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="c755d-131">In the **Performance** area, click **Settings**.</span></span>

    3.  <span data-ttu-id="c755d-132">在 [**虛擬記憶體**] 區域中，按一下 [**變更**]。</span><span class="sxs-lookup"><span data-stu-id="c755d-132">In the **Virtual Memory** area, click **Change**.</span></span>

    4.  <span data-ttu-id="c755d-133">設定您的頁面檔案設定。</span><span class="sxs-lookup"><span data-stu-id="c755d-133">Configure your page file settings.</span></span>

8.  <span data-ttu-id="c755d-134">關閉 Windows XP 影像。</span><span class="sxs-lookup"><span data-stu-id="c755d-134">Shut down the Windows XP image.</span></span>

**<span data-ttu-id="c755d-135">整理並預先壓縮虛擬硬碟</span><span class="sxs-lookup"><span data-stu-id="c755d-135">Defragmenting and Pre-compacting the Virtual Hard Disk</span></span>**

1.  <span data-ttu-id="c755d-136">在執行 Windows 7 的主機電腦的 [**控制台**] 中，按一下 [**管理工具**]，按兩下 [**電腦管理**]，然後按一下 [**磁片管理**]。</span><span class="sxs-lookup"><span data-stu-id="c755d-136">In **Control Panel** on the host computer that is running Windows 7, click **Administrative Tools**, double-click **Computer Management**, then click **Disk Management**.</span></span>

2.  <span data-ttu-id="c755d-137">使用磁片管理主控台，附加（裝載）虛擬硬碟，然後整理磁片磁片。</span><span class="sxs-lookup"><span data-stu-id="c755d-137">By using the Disk Management Console, attach (mount) the virtual hard disk and then defragment the disk.</span></span>

3.  <span data-ttu-id="c755d-138">使用 ISO 解壓縮工具，解壓縮位於 \\Program Files\\Windows Virtual PC\\Integration 元件資料夾中的 precompact。</span><span class="sxs-lookup"><span data-stu-id="c755d-138">By using an ISO extraction tool, extract the precompact.iso located in the \\Program Files\\Windows Virtual PC\\Integration Components folder.</span></span>

4.  <span data-ttu-id="c755d-139">使用 precompact.exe 程式來壓縮 Windows XP 虛擬硬碟。</span><span class="sxs-lookup"><span data-stu-id="c755d-139">Use the precompact.exe program to compress the Windows XP virtual hard disk.</span></span>

5.  <span data-ttu-id="c755d-140">使用磁片管理主控台，分離虛擬硬碟。</span><span class="sxs-lookup"><span data-stu-id="c755d-140">By using the Disk Management Console, detach the virtual hard disk.</span></span>

**<span data-ttu-id="c755d-141">壓縮虛擬硬碟</span><span class="sxs-lookup"><span data-stu-id="c755d-141">Compacting the Virtual Hard Disk</span></span>**

1.  <span data-ttu-id="c755d-142">開啟 Windows 虛擬電腦。</span><span class="sxs-lookup"><span data-stu-id="c755d-142">Open Windows Virtual PC.</span></span>

    <span data-ttu-id="c755d-143">按一下 [**開始**]，按一下 [**所有程式**]，按一下 [ **windows 虛擬電腦**]，然後按一下 [ **windows 虛擬電腦**]。</span><span class="sxs-lookup"><span data-stu-id="c755d-143">Click **Start**, click **All Programs**, click **Windows Virtual PC**, then click **Windows Virtual PC**.</span></span>

2.  <span data-ttu-id="c755d-144">以滑鼠右鍵按一下您的 Windows XP 影像，然後選取 [**設定**]。</span><span class="sxs-lookup"><span data-stu-id="c755d-144">Right-click your Windows XP image and select **Settings**.</span></span>

3.  <span data-ttu-id="c755d-145">針對您的 Windows XP 映射，按一下 [**硬碟**]，然後按一下 [**修改**]。</span><span class="sxs-lookup"><span data-stu-id="c755d-145">Click **Hard Disk** for the one that corresponds to your Windows XP image, and then click **Modify**.</span></span>

4.  <span data-ttu-id="c755d-146">按一下 [**壓縮虛擬硬碟**]。</span><span class="sxs-lookup"><span data-stu-id="c755d-146">Click **Compact virtual hard disk**.</span></span>

5.  <span data-ttu-id="c755d-147">按一下 [**壓縮**]，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="c755d-147">Click **Compact** and then click **OK**.</span></span>

<span data-ttu-id="c755d-148">建立壓縮虛擬硬碟的備份複本。</span><span class="sxs-lookup"><span data-stu-id="c755d-148">Create a backup copy of your compacted virtual hard disk.</span></span>

## <span data-ttu-id="c755d-149">相關主題</span><span class="sxs-lookup"><span data-stu-id="c755d-149">Related topics</span></span>


[<span data-ttu-id="c755d-150">設定 MED-V 的 Windows 虛擬電腦映像</span><span class="sxs-lookup"><span data-stu-id="c755d-150">Configuring a Windows Virtual PC Image for MED-V</span></span>](configuring-a-windows-virtual-pc-image-for-med-v.md)

[<span data-ttu-id="c755d-151">MED-V 技術參考資料</span><span class="sxs-lookup"><span data-stu-id="c755d-151">Technical Reference for MED-V</span></span>](technical-reference-for-med-v.md)

 

 





