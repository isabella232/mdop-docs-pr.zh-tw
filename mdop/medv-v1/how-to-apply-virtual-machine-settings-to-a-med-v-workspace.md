---
title: 如何套用虛擬機器設定到 MED-V 工作區
description: 如何套用虛擬機器設定到 MED-V 工作區
author: dansimp
ms.assetid: b50d0dfb-8d61-4543-9607-a29bbb1ed45f
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9662bb8202285d51971eeea8beaef938b98ed6b0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811475"
---
# <span data-ttu-id="2a089-103">如何套用虛擬機器設定到 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="2a089-103">How to Apply Virtual Machine Settings to a MED-V Workspace</span></span>


<span data-ttu-id="2a089-104">每個 MED-V 工作區都必須有一個與它相關聯的 Microsoft 虛擬電腦影像。</span><span class="sxs-lookup"><span data-stu-id="2a089-104">Every MED-V workspace must have a Microsoft Virtual PC image associated with it.</span></span> <span data-ttu-id="2a089-105">虛擬機器設定可讓您指派虛擬電腦影像，以及設定其他虛擬機器屬性。</span><span class="sxs-lookup"><span data-stu-id="2a089-105">The virtual machine settings enable you to assign a Virtual PC image as well as set other virtual machine properties.</span></span>

<span data-ttu-id="2a089-106">[**虛擬機器設定**] 索引標籤上的 [**原則**] 模組中的所有虛擬機器設定都已設定。</span><span class="sxs-lookup"><span data-stu-id="2a089-106">All virtual machine settings are configured in the **Policy** module, on the **Virtual Machine Settings** tab.</span></span>

**<span data-ttu-id="2a089-107">將虛擬機器設定套用至 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="2a089-107">To apply virtual machine settings to a MED-V workspace</span></span>**

1.  <span data-ttu-id="2a089-108">按一下要設定的 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="2a089-108">Click the MED-V workspace to configure.</span></span>

2.  <span data-ttu-id="2a089-109">按照下表所述，設定虛擬機器屬性。</span><span class="sxs-lookup"><span data-stu-id="2a089-109">Configure the virtual machine properties as described in the following table.</span></span>

3.  <span data-ttu-id="2a089-110">在 [**原則**] 功能表上，選取 [**確認**]。</span><span class="sxs-lookup"><span data-stu-id="2a089-110">On the **Policy** menu, select **Commit**.</span></span>

**<span data-ttu-id="2a089-111">虛擬機器屬性</span><span class="sxs-lookup"><span data-stu-id="2a089-111">Virtual Machine Properties</span></span>**

<span data-ttu-id="2a089-112">[屬性描述]*虛擬電腦設定*</span><span class="sxs-lookup"><span data-stu-id="2a089-112">Property Description *Virtual Machine Settings*</span></span>

<span data-ttu-id="2a089-113">已指派影像</span><span class="sxs-lookup"><span data-stu-id="2a089-113">Assigned Image</span></span>

<span data-ttu-id="2a089-114">指派給 MED-V 工作區的實際 Microsoft 虛擬電腦影像。</span><span class="sxs-lookup"><span data-stu-id="2a089-114">The actual Microsoft Virtual PC image assigned to the MED-V workspace.</span></span> <span data-ttu-id="2a089-115">功能表會提供所有可用虛擬電腦影像的清單。</span><span class="sxs-lookup"><span data-stu-id="2a089-115">The menu provides a list of all available Virtual PC images.</span></span> <span data-ttu-id="2a089-116">下列圖像類型位於 [**活動**影像] 清單中：</span><span class="sxs-lookup"><span data-stu-id="2a089-116">The following image types are in the **Active** image list:</span></span>

-   <span data-ttu-id="2a089-117">**本機測試影像**：本機電腦上尚未打包的影像。</span><span class="sxs-lookup"><span data-stu-id="2a089-117">**Local test images**—Images on the local computer that are not yet packed.</span></span> <span data-ttu-id="2a089-118">這些圖像名稱後面接著是括弧（test）中的「test」一詞，且僅供測試之用。</span><span class="sxs-lookup"><span data-stu-id="2a089-118">These image names are followed by the word “test” in parentheses (test) and are for testing purposes only.</span></span>

-   <span data-ttu-id="2a089-119">**本機打包的影像**，即在本機電腦上打包的影像。</span><span class="sxs-lookup"><span data-stu-id="2a089-119">**Local packed images**—Packed images on the local computer.</span></span> <span data-ttu-id="2a089-120">這些影像後面接著是括弧（local）中的「local」，且不能由用戶端下載，直到系統管理員將它們上傳到伺服器為止。</span><span class="sxs-lookup"><span data-stu-id="2a089-120">These images are followed by the word “local” in parentheses (local) and cannot be downloaded by clients until the administrator uploads them to the server.</span></span>

    <span data-ttu-id="2a089-121">如果您要建立會透過卸除式媒體（例如 USB 或 DVD）分發給用戶端的套件，可以選取本機影像。</span><span class="sxs-lookup"><span data-stu-id="2a089-121">A local image can be selected if you are creating a package that will be distributed to the client via removable media (such as USB or DVD).</span></span>

-   <span data-ttu-id="2a089-122">**在伺服器上打包的影像**，也就是伺服器上的影像，且可供用戶端下載。</span><span class="sxs-lookup"><span data-stu-id="2a089-122">**Packed images on server**—Images that are on the server and are available for download by clients.</span></span> <span data-ttu-id="2a089-123">按一下 [重新整理] 以重新整理影像清單。</span><span class="sxs-lookup"><span data-stu-id="2a089-123">Click Refresh to refresh the images list.</span></span>

    <span data-ttu-id="2a089-124">**記事** 每個 MED-V 工作區圖像只能由一個 Windows 使用者使用。</span><span class="sxs-lookup"><span data-stu-id="2a089-124">**Note** Each MED-V workspace image can only be used by one Windows user.</span></span>

     

<span data-ttu-id="2a089-125">工作區持久</span><span class="sxs-lookup"><span data-stu-id="2a089-125">Workspace is persistent</span></span>

<span data-ttu-id="2a089-126">選取此核取方塊以將 MED-V 工作區設定為 persistent。</span><span class="sxs-lookup"><span data-stu-id="2a089-126">Select this check box to configure the MED-V workspace as persistent.</span></span> <span data-ttu-id="2a089-127">在持久的 MED-V 工作區中，當 MED-V 工作區停止時，會將對 MED-V 工作區所做的變更和新增儲存在 MED-V 工作區中。</span><span class="sxs-lookup"><span data-stu-id="2a089-127">In a persistent MED-V workspace, when the MED-V workspace is stopped, changes and additions to the MED-V workspace are saved in the MED-V workspace.</span></span>

<span data-ttu-id="2a089-128">對於網域 MED-V 工作區，必須選取此選項。</span><span class="sxs-lookup"><span data-stu-id="2a089-128">For a Domain MED-V workspace, this option must be selected.</span></span>

<span data-ttu-id="2a089-129">**記事** 在將 MED-V 工作區部署給使用者之後，就不應該變更這個設定。</span><span class="sxs-lookup"><span data-stu-id="2a089-129">**Note** This setting should not be changed after a MED-V workspace is deployed to users.</span></span>

 

<span data-ttu-id="2a089-130">停止工作區時關閉 VM</span><span class="sxs-lookup"><span data-stu-id="2a089-130">Shut down the VM when stopping the Workspace</span></span>

<span data-ttu-id="2a089-131">選取此核取方塊，以在停止 MED-V 工作區時關閉虛擬機器。</span><span class="sxs-lookup"><span data-stu-id="2a089-131">Select this check box to shut down the virtual machine when stopping the MED-V workspace.</span></span> <span data-ttu-id="2a089-132">如果清除此核取方塊，則在每個會話完成時，虛擬機器不會關閉，而是取得虛擬機器的快照。</span><span class="sxs-lookup"><span data-stu-id="2a089-132">If this check box is cleared, at the completion of each session, the virtual machine is not shut down but instead takes a snapshot of the virtual machine.</span></span> <span data-ttu-id="2a089-133">啟動新的會話時，Windows 會從快照開始（也就是 Windows 不會重新開機，也不需要登入）。</span><span class="sxs-lookup"><span data-stu-id="2a089-133">Upon the initiation of a new session, Windows starts from the snapshot (that is, Windows does not restart and no login is required).</span></span>

<span data-ttu-id="2a089-134">**記事** 只有在已選取 [**工作區永久**] 時，才會啟用此屬性。</span><span class="sxs-lookup"><span data-stu-id="2a089-134">**Note** This property is enabled only if **Workspace is persistent** is selected.</span></span>

 

<span data-ttu-id="2a089-135">使用 MED-V 認證（SSO）在 VM 中登入 Windows</span><span class="sxs-lookup"><span data-stu-id="2a089-135">Logon to Windows in VM using MED-V credentials (SSO)</span></span>

<span data-ttu-id="2a089-136">選取此核取方塊，即可在登入 MED-V 用戶端時，使用輸入的 MED-V 認證，在虛擬機器上登入 Windows。</span><span class="sxs-lookup"><span data-stu-id="2a089-136">Select this check box to log in to Windows on the virtual machine by using the MED-V credentials entered when logging in to MED-V client.</span></span>

<span data-ttu-id="2a089-137">**記事** 只有在已選取 [**工作區永久**] 時，才會啟用此屬性。</span><span class="sxs-lookup"><span data-stu-id="2a089-137">**Note** This property is enabled only when **Workspace is persistent** is selected.</span></span>

 

<span data-ttu-id="2a089-138">工作區為 revertible</span><span class="sxs-lookup"><span data-stu-id="2a089-138">Workspace is revertible</span></span>

<span data-ttu-id="2a089-139">選取此核取方塊以將 MED-V 工作區設定為 revertible。</span><span class="sxs-lookup"><span data-stu-id="2a089-139">Select this check box to configure the MED-V workspace as revertible.</span></span> <span data-ttu-id="2a089-140">在 revertible MED-V 工作區的每個會話完成時（也就是當使用者停止 MED-V-V 工作區時），MED-V 工作區會還原為部署期間的原始狀態。</span><span class="sxs-lookup"><span data-stu-id="2a089-140">In a revertible MED-V workspace, at the completion of each session (that is, when the user stops the MED-V workspace), the MED-V workspace reverts to the original state it was in during deployment.</span></span> <span data-ttu-id="2a089-141">使用者所做的任何變更或附加都不會儲存在 [會話] 之間的 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="2a089-141">No changes or additions that the user made are saved on the MED-V workspace between sessions.</span></span>

<span data-ttu-id="2a089-142">**記事** 在將 MED-V 工作區部署給使用者之後，就不應該變更這個設定。</span><span class="sxs-lookup"><span data-stu-id="2a089-142">**Note** This setting should not be changed after a MED-V workspace is deployed to users.</span></span>

 

<span data-ttu-id="2a089-143">同步處理工作區時區與主機</span><span class="sxs-lookup"><span data-stu-id="2a089-143">Synchronize Workspace time zone with host</span></span>

<span data-ttu-id="2a089-144">選取此核取方塊，以將 MED-V 工作區中的時區與主機同步處理。</span><span class="sxs-lookup"><span data-stu-id="2a089-144">Select this check box to synchronize the time zone in the MED-V workspace with the host.</span></span>

<span data-ttu-id="2a089-145">同步處理的運作方式會根據 MED-V 工作區是否為 persistent 或 revertible 而有所不同，如下所示：</span><span class="sxs-lookup"><span data-stu-id="2a089-145">The synchronization works differently depending on whether the MED-V workspace is persistent or revertible, as follows:</span></span>

-   <span data-ttu-id="2a089-146">在持久的 MED-V 工作區中，時區會先嘗試與伺服器同步處理。</span><span class="sxs-lookup"><span data-stu-id="2a089-146">In a persistent MED-V workspace, the time zone first tries to synchronize with the server.</span></span> <span data-ttu-id="2a089-147">如果失敗，它會與主機同步處理。</span><span class="sxs-lookup"><span data-stu-id="2a089-147">If that fails, it synchronizes with the host.</span></span>

-   <span data-ttu-id="2a089-148">在 revertible MED-V 工作區中，時區與主機進行同步處理。</span><span class="sxs-lookup"><span data-stu-id="2a089-148">In a revertible MED-V workspace, the time zone synchronizes with the host.</span></span>

*<span data-ttu-id="2a089-149">鎖定設定</span><span class="sxs-lookup"><span data-stu-id="2a089-149">Lock Settings</span></span>*

<span data-ttu-id="2a089-150">鎖定主機待機/休眠事件的工作區</span><span class="sxs-lookup"><span data-stu-id="2a089-150">Lock the Workspace on host standby/hibernate event</span></span>

<span data-ttu-id="2a089-151">選取此核取方塊，以在主機電腦進入待機或休眠狀態時，自動鎖定 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="2a089-151">Select this check box to automatically lock the MED-V workspace when the host computer goes into standby or hibernate.</span></span>

<span data-ttu-id="2a089-152">後鎖定工作區</span><span class="sxs-lookup"><span data-stu-id="2a089-152">Lock the Workspace after</span></span>

<span data-ttu-id="2a089-153">選取此核取方塊，當 MED-V-V 工作區在指定的一段時間內閒置時，鎖定 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="2a089-153">Select this check box to lock the MED-V workspace when the MED-V workspace is idle for a specified period of time.</span></span> <span data-ttu-id="2a089-154">選取此選項時，會啟用 [編號] 方塊。</span><span class="sxs-lookup"><span data-stu-id="2a089-154">When selected, the number box is enabled.</span></span> <span data-ttu-id="2a089-155">輸入在鎖定 MED-V 工作區之前閒置時間的分鐘數。</span><span class="sxs-lookup"><span data-stu-id="2a089-155">Enter the number of minutes of idle time before locking the MED-V workspace.</span></span>

<span data-ttu-id="2a089-156">**記事** 閒置時間指的是 MED-V 工作區應用程式（而非主機應用程式）。</span><span class="sxs-lookup"><span data-stu-id="2a089-156">**Note** The idle time refers to the MED-V workspace applications (not the host applications).</span></span>

 

*<span data-ttu-id="2a089-157">影像更新設定</span><span class="sxs-lookup"><span data-stu-id="2a089-157">Image Update Settings</span></span>*

<span data-ttu-id="2a089-158">只保留</span><span class="sxs-lookup"><span data-stu-id="2a089-158">Keep only</span></span>

<span data-ttu-id="2a089-159">選取此核取方塊，以限制要保留的舊影像版本數。</span><span class="sxs-lookup"><span data-stu-id="2a089-159">Select this check box to limit the number of old image versions to keep.</span></span>

<span data-ttu-id="2a089-160">選取此選項時，會啟用 [編號] 方塊。</span><span class="sxs-lookup"><span data-stu-id="2a089-160">When selected, the number box is enabled.</span></span> <span data-ttu-id="2a089-161">輸入要保留的舊版本數。</span><span class="sxs-lookup"><span data-stu-id="2a089-161">Enter the number of old versions to keep.</span></span>

<span data-ttu-id="2a089-162">提供新版本時的建議更新</span><span class="sxs-lookup"><span data-stu-id="2a089-162">Suggest update when a new version is available</span></span>

<span data-ttu-id="2a089-163">選取此核取方塊可在有新版本的影像時建議（但不強制）更新。</span><span class="sxs-lookup"><span data-stu-id="2a089-163">Select this check box to suggest (but not force) an update when a new version of the image is available.</span></span>

<span data-ttu-id="2a089-164">用戶端應該在下載此工作區的影像時使用修剪轉移</span><span class="sxs-lookup"><span data-stu-id="2a089-164">Clients should use Trim Transfer when downloading images for this Workspace</span></span>

<span data-ttu-id="2a089-165">選取此核取方塊以啟用修剪傳輸（如需詳細資訊，請參閱[Med-v 修剪傳輸技術](med-v-trim-transfer-technology-medvv2.md)），下載與此 med-v 工作區相關聯的影像。</span><span class="sxs-lookup"><span data-stu-id="2a089-165">Select this check box to enable Trim Transfer (for more information, see [MED-V Trim Transfer Technology](med-v-trim-transfer-technology-medvv2.md)) when downloading images associated with this MED-V workspace.</span></span> <span data-ttu-id="2a089-166">如果清除此核取方塊，將會下載完整的影像。</span><span class="sxs-lookup"><span data-stu-id="2a089-166">If this check box is cleared, the full image will be downloaded.</span></span>

<span data-ttu-id="2a089-167">**記事** 修剪轉移需要為硬碟編制索引，這可能需要花費相當長的時間。</span><span class="sxs-lookup"><span data-stu-id="2a089-167">**Note** Trim Transfer requires indexing the hard drive, which might take a considerable amount of time.</span></span> <span data-ttu-id="2a089-168">建議您在編制硬碟索引時，使用修剪轉移比下載新影像版本更有效率，例如下載與現有版本類似的影像版本。</span><span class="sxs-lookup"><span data-stu-id="2a089-168">It is recommended to use Trim Transfer when indexing the hard drive is more efficient than downloading the new image version, such as when downloading an image version that is similar to the existing version.</span></span>

 

 

## <span data-ttu-id="2a089-169">相關主題</span><span class="sxs-lookup"><span data-stu-id="2a089-169">Related topics</span></span>


[<span data-ttu-id="2a089-170">建立 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="2a089-170">Creating a MED-V Image</span></span>](creating-a-med-v-image.md)

[<span data-ttu-id="2a089-171">使用 MED-V 管理主控台使用者介面</span><span class="sxs-lookup"><span data-stu-id="2a089-171">Using the MED-V Management Console User Interface</span></span>](using-the-med-v-management-console-user-interface.md)

[<span data-ttu-id="2a089-172">建立 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="2a089-172">Creating a MED-V Workspace</span></span>](creating-a-med-v-workspacemedv-10-sp1.md)

 

 





