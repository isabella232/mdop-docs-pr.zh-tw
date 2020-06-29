---
title: 如何建立和測試 MED-V 映像
description: 如何建立和測試 MED-V 映像
author: dansimp
ms.assetid: 40e4aba6-12cb-4794-967d-2c09dc20d808
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 9f7989871a695b09c987124ab02c0143082148f3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812117"
---
# <span data-ttu-id="9c8d3-103">如何建立和測試 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="9c8d3-103">How to Create and Test a MED-V Image</span></span>


<span data-ttu-id="9c8d3-104">MED-V 系統管理員會建立 MED-V 影像，讓它可以上傳，與 MED-V 工作區建立關聯，然後透過網路發佈至用戶端、新增至 MED-V 套件，或使用協力廠商系統下載到用戶端。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-104">The MED-V administrator creates a MED-V image so that it can be uploaded, associated with a MED-V workspace, and then distributed to the client over the Web, added to a MED-V package, or downloaded to the client by using a third-party system.</span></span> <span data-ttu-id="9c8d3-105">建議您先建立測試影像，並在 MED-V 用戶端上進行測試，然後再進行部署。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-105">It is recommended to first create a test image and test it on MED-V client before deploying it.</span></span>

<span data-ttu-id="9c8d3-106">建立 MED-V 影像時，會透過下列階段進行：</span><span class="sxs-lookup"><span data-stu-id="9c8d3-106">When creating a MED-V image, it goes through the following stages:</span></span>

1.  <span data-ttu-id="9c8d3-107">**本機測試影像**：可在本機測試的基本影像。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-107">**Local test image**—A basic image that can be tested locally.</span></span>

2.  <span data-ttu-id="9c8d3-108">**本機封裝影像**：在測試影像之後，影像會封裝為在測試之前存在的影像。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-108">**Local packed image**—After the image is tested, the image is packed as it existed prior to testing.</span></span> <span data-ttu-id="9c8d3-109">在測試期間進行的變更不會包含在打包的影像中。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-109">No changes made during testing are included in the packed image.</span></span>

3.  <span data-ttu-id="9c8d3-110">**在伺服器上封裝影像**：打包的影像會上傳到伺服器。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-110">**Packed image on server**—The packed image is uploaded to the server.</span></span>

## <span data-ttu-id="9c8d3-111">如何建立 MED-V 測試圖像</span><span class="sxs-lookup"><span data-stu-id="9c8d3-111">How to Create a MED-V Test Image</span></span>


**<span data-ttu-id="9c8d3-112">若要建立新的 MED-V 測試影像</span><span class="sxs-lookup"><span data-stu-id="9c8d3-112">To create a new MED-V test image</span></span>**

1.  <span data-ttu-id="9c8d3-113">按一下 [**影像**管理] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-113">Click the **Images** management button.</span></span>

    <span data-ttu-id="9c8d3-114">[**影像**] 模組隨即出現。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-114">The **Images** module appears.</span></span>

    -   <span data-ttu-id="9c8d3-115">[**影像**] 模組由下列窗格組成：</span><span class="sxs-lookup"><span data-stu-id="9c8d3-115">The **Images** module consists of the following panes:</span></span>

        -   <span data-ttu-id="9c8d3-116">**本機測試影像**-本機解包圖像。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-116">**Local Test Images**—Local unpacked images.</span></span>

        -   <span data-ttu-id="9c8d3-117">**本機打包的影像**-在本機電腦上的所有打包影像。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-117">**Local Packed Images**—All packed images on the local computer.</span></span>

        -   <span data-ttu-id="9c8d3-118">**在伺服器上打包的影像**：已打包並上傳到伺服器的所有影像。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-118">**Packed Images on Server**—All images that have been packed and uploaded to the server.</span></span>

    -   <span data-ttu-id="9c8d3-119">在**本機打包的影像**和**伺服器窗格上打包的影像**中，每個影像的最新版本都會顯示為父節點。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-119">In the **Local Packed Images** and **Packed Images on Server** panes, the most recent version of each image is displayed as the parent node.</span></span> <span data-ttu-id="9c8d3-120">按一下父節點，以查看所有其他現有的圖像版本。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-120">Click the parent node to view all other existing versions of the image.</span></span>

2.  <span data-ttu-id="9c8d3-121">在 [**本機測試影像**] 窗格中，按一下 [**新增**]。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-121">In the **Local Test Images** pane, click **New**.</span></span>

3.  <span data-ttu-id="9c8d3-122">在 [**測試影像建立**] 對話方塊中，執行下列其中一項動作，選取您要設定為 med-v 測試影像的虛擬機器影像：</span><span class="sxs-lookup"><span data-stu-id="9c8d3-122">On the **Test Image Creation** dialog box, select the virtual machine image that you want to configure as a MED-V test image by doing one of the following:</span></span>

    -   <span data-ttu-id="9c8d3-123">在 [**基底圖像**檔案] 欄位中，輸入為 med-v 準備的 MICROSOFT Virtual 電腦影像準備的目錄完整路徑。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-123">In the **Base image** file field, type the full path to the directory where the Microsoft Virtual PC image prepared for MED-V is located.</span></span>

    -   <span data-ttu-id="9c8d3-124">按一下 **[流覽**]，流覽至準備 Med-v-V 的 MICROSOFT Virtual 電腦影像所在的目錄。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-124">Click **Browse** to browse to the directory where the Microsoft Virtual PC image prepared for MED-V is located.</span></span>

4.  <span data-ttu-id="9c8d3-125">在 [**影像名稱**] 欄位中，輸入或選取想要的名稱。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-125">In the **Image name** field, type or select the desired name.</span></span>

    <span data-ttu-id="9c8d3-126">**記事** 下列字元不能包含在影像名稱中： space " &lt; &gt; |\\ / : \* ?</span><span class="sxs-lookup"><span data-stu-id="9c8d3-126">**Note** The following characters cannot be included in the image name: space " &lt; &gt; | \\ / : \* ?</span></span>

     

5.  <span data-ttu-id="9c8d3-127">按一下 \[確定\] \*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-127">Click **OK**.</span></span>

    <span data-ttu-id="9c8d3-128">您的主機電腦上會建立新的 MED-V 測試影像，其屬性在下表中定義。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-128">A new MED-V test image is created on your host computer with the properties defined in the following table.</span></span>

    <span data-ttu-id="9c8d3-129">如需有關設定 MED-V 工作區圖像的詳細資訊，請參閱設定[Med-v 工作區原則](configuring-med-v-workspace-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-129">For more information about configuring the MED-V workspace image, refer to [Configuring MED-V Workspace Policies](configuring-med-v-workspace-policies.md).</span></span>

**<span data-ttu-id="9c8d3-130">本機測試影像屬性</span><span class="sxs-lookup"><span data-stu-id="9c8d3-130">Local Test Images Properties</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="9c8d3-131">屬性</span><span class="sxs-lookup"><span data-stu-id="9c8d3-131">Property</span></span></th>
<th align="left"><span data-ttu-id="9c8d3-132">描述</span><span class="sxs-lookup"><span data-stu-id="9c8d3-132">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9c8d3-133">圖像名稱</span><span class="sxs-lookup"><span data-stu-id="9c8d3-133">Image Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c8d3-134">在管理員建立影像時所定義之測試映射的名稱。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-134">The name of the test image as it was defined when the administrator created the image.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="9c8d3-135">影像路徑</span><span class="sxs-lookup"><span data-stu-id="9c8d3-135">Image Path</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c8d3-136">測試影像的本機路徑。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-136">The local path of the test image.</span></span></p></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="9c8d3-137">新建</span><span class="sxs-lookup"><span data-stu-id="9c8d3-137">Created</span></span></p></td>
<td align="left"><p><span data-ttu-id="9c8d3-138">已建立測試影像的日期。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-138">The date the test image was created.</span></span></p></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="9c8d3-139">如何從 MED-V 用戶端測試 MED-V 影像</span><span class="sxs-lookup"><span data-stu-id="9c8d3-139">How to Test a MED-V Image from the MED-V Client</span></span>


<span data-ttu-id="9c8d3-140">建立 MED-V 測試圖像之後，請使用下列程式在本機測試影像。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-140">After a MED-V test image is created, use the following procedure to test the image locally.</span></span>

**<span data-ttu-id="9c8d3-141">測試 MED-V 影像</span><span class="sxs-lookup"><span data-stu-id="9c8d3-141">To test a MED-V image</span></span>**

1.  <span data-ttu-id="9c8d3-142">按一下 [**原則**管理] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-142">Click the **Policy** management button.</span></span>

2.  <span data-ttu-id="9c8d3-143">在**原則**模組中，執行下列動作，將 med-v 測試影像指派給 med-v 工作區：</span><span class="sxs-lookup"><span data-stu-id="9c8d3-143">In the **Policy** module, assign the MED-V test image to a MED-V workspace by doing the following:</span></span>

    1.  <span data-ttu-id="9c8d3-144">按一下 [**虛擬機器**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-144">Click the **Virtual Machine** tab.</span></span>

    2.  <span data-ttu-id="9c8d3-145">在 [**指派的影像**] 欄位中，選取您所建立的 med-v 測試影像。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-145">In the **Assigned Image** field, select the MED-V test image you created.</span></span> <span data-ttu-id="9c8d3-146">如果您的測試影像不在清單中，請**按一下 [** 重新整理]。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-146">If your test image is not in the list, click **Refresh**.</span></span>

    3.  <span data-ttu-id="9c8d3-147">按一下工具列上的 [**儲存變更**]。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-147">On the toolbar, click **Save changes**.</span></span>

3.  <span data-ttu-id="9c8d3-148">設定要測試的任何其他 MED-V 工作區設定。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-148">Configure any other MED-V workspace settings to be tested.</span></span> <span data-ttu-id="9c8d3-149">如需詳細資訊，請參閱設定[Med-v 工作區原則](configuring-med-v-workspace-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-149">For more information, see [Configuring MED-V Workspace Policies](configuring-med-v-workspace-policies.md).</span></span>

4.  <span data-ttu-id="9c8d3-150">啟動 MED-V-V 用戶端。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-150">Start MED-V client.</span></span>

5.  <span data-ttu-id="9c8d3-151">在 [**確認執行測試**確認] 方塊中，按一下 [**使用測試影像**]。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-151">In the **Confirm Running Test** confirmation box, click **Use Test Image**.</span></span>

6.  <span data-ttu-id="9c8d3-152">測試 MED-V 工作區測試影像。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-152">Test the MED-V workspace test image.</span></span>

    <span data-ttu-id="9c8d3-153">如需啟動和執行 MED-V 用戶端的相關資訊，請參閱[Med-v 用戶端作業](med-v-client-operations.md)。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-153">For information about starting and running MED-V client, see [MED-V Client Operations](med-v-client-operations.md).</span></span>

<span data-ttu-id="9c8d3-154">**記事** 測試影像時，請不要開啟 VPC 並變更影像。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-154">**Note** While testing an image, do not open VPC and make changes to the image.</span></span>

 

<span data-ttu-id="9c8d3-155">**記事** 測試影像時，不會將變更儲存至會話之間的影像;相反地，這些檔案是儲存在個別的臨時檔案中。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-155">**Note** When testing an image, no changes are saved to the image between sessions; instead, they are saved in a separate, temporary file.</span></span> <span data-ttu-id="9c8d3-156">這是為了確保影像在生產環境中打包並執行時，它是原始的乾淨影像。</span><span class="sxs-lookup"><span data-stu-id="9c8d3-156">This is to ensure that when the image is packed and run on the production environment, it is the original, clean image.</span></span>

 

## <span data-ttu-id="9c8d3-157">相關主題</span><span class="sxs-lookup"><span data-stu-id="9c8d3-157">Related topics</span></span>


[<span data-ttu-id="9c8d3-158">建立 MED-V 的虛擬電腦映像</span><span class="sxs-lookup"><span data-stu-id="9c8d3-158">Creating a Virtual PC Image for MED-V</span></span>](creating-a-virtual-pc-image-for-med-v.md)

[<span data-ttu-id="9c8d3-159">建立 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="9c8d3-159">Creating a MED-V Workspace</span></span>](creating-a-med-v-workspacemedv-10-sp1.md)

[<span data-ttu-id="9c8d3-160">設定 MED-V 工作區原則</span><span class="sxs-lookup"><span data-stu-id="9c8d3-160">Configuring MED-V Workspace Policies</span></span>](configuring-med-v-workspace-policies.md)

[<span data-ttu-id="9c8d3-161">MED-V 用戶端操作</span><span class="sxs-lookup"><span data-stu-id="9c8d3-161">MED-V Client Operations</span></span>](med-v-client-operations.md)

 

 





