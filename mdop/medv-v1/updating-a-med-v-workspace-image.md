---
title: 更新 MED-V 工作區映像
description: 更新 MED-V 工作區映像
author: dansimp
ms.assetid: 1b9c4a73-3487-43d2-98e3-43dbc79e10e3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 60a5d12622e0cb7012c6d0a22124d63c085f6d0a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811403"
---
# <span data-ttu-id="bdfff-103">更新 MED-V 工作區映像</span><span class="sxs-lookup"><span data-stu-id="bdfff-103">Updating a MED-V Workspace Image</span></span>


<span data-ttu-id="bdfff-104">您可以使用下列其中一種方式來更新影像：</span><span class="sxs-lookup"><span data-stu-id="bdfff-104">An image can be updated in one of the following ways:</span></span>

-   <span data-ttu-id="bdfff-105">您可以使用企業軟體發佈系統，將更新推送到客體作業系統。</span><span class="sxs-lookup"><span data-stu-id="bdfff-105">The update can be pushed to the guest operating system using your enterprise software distribution system.</span></span>

-   <span data-ttu-id="bdfff-106">更新可以上傳到影像 Web 發佈伺服器，然後由用戶端下載並套用至 MED-V 影像。</span><span class="sxs-lookup"><span data-stu-id="bdfff-106">The update can be uploaded to the image Web distribution server, and then downloaded by the client and applied to the MED-V image.</span></span>

-   <span data-ttu-id="bdfff-107">MED-V 基底影像可以更新並重新部署。</span><span class="sxs-lookup"><span data-stu-id="bdfff-107">The MED-V base image can be updated and redeployed.</span></span>

## <a href="" id="bkmk-howtoupdateamedvimageusinganesd"></a><span data-ttu-id="bdfff-108">如何使用企業軟體發佈系統更新 MED-V 影像</span><span class="sxs-lookup"><span data-stu-id="bdfff-108">How to Update a MED-V Image Using an Enterprise Software Distribution System</span></span>


**<span data-ttu-id="bdfff-109">使用企業軟體發佈系統來更新 MED-V 影像</span><span class="sxs-lookup"><span data-stu-id="bdfff-109">To update a MED-V image using an enterprise software distribution system</span></span>**

-   <span data-ttu-id="bdfff-110">請參閱您正在使用的系統檔。</span><span class="sxs-lookup"><span data-stu-id="bdfff-110">Refer to the documentation of the system you are using.</span></span>

## <a href="" id="bkmk-howtoupdateamedvimageusingwebdownload"></a><span data-ttu-id="bdfff-111">如何使用網頁下載來更新 MED-V 影像</span><span class="sxs-lookup"><span data-stu-id="bdfff-111">How to Update a MED-V Image Using Web Download</span></span>


**<span data-ttu-id="bdfff-112">使用網頁下載來更新 MED-V 影像</span><span class="sxs-lookup"><span data-stu-id="bdfff-112">To update a MED-V image using Web download</span></span>**

1.  <span data-ttu-id="bdfff-113">在 MED-V 管理中，請在 [**虛擬機器**] 索引標籤上，確保將下列設定套用到與要更新之 med-v 影像相關聯的 med-v 工作區原則：</span><span class="sxs-lookup"><span data-stu-id="bdfff-113">In MED-V management, on the **Virtual Machine** tab, ensure that the following settings are applied to the MED-V workspace policies that are associated with the MED-V image being updated:</span></span>

    -   <span data-ttu-id="bdfff-114">已選取 [**新版本可供使用時的建議更新**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="bdfff-114">The **Suggest update when a new version is available** check box is selected.</span></span>

    -   <span data-ttu-id="bdfff-115">或者，用戶端應該在已選取 [**下載此工作區的影像時，使用修剪轉移**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="bdfff-115">Optionally, the **Clients should use Trim Transfer when downloading images for this Workspace** check box is selected.</span></span>

    <span data-ttu-id="bdfff-116">如需詳細資訊，請參閱[如何將虛擬機器設定套用至 Med-v 工作區](how-to-apply-virtual-machine-settings-to-a-med-v-workspace.md)。</span><span class="sxs-lookup"><span data-stu-id="bdfff-116">For more information, see [How to Apply Virtual Machine Settings to a MED-V Workspace](how-to-apply-virtual-machine-settings-to-a-med-v-workspace.md).</span></span>

2.  <span data-ttu-id="bdfff-117">將影像更新上傳到影像 Web 發佈伺服器。</span><span class="sxs-lookup"><span data-stu-id="bdfff-117">Upload the image update to the image Web distribution server.</span></span>

    <span data-ttu-id="bdfff-118">所有含有需要更新之影像的用戶端，都會自動下載更新並將其套用至影像。</span><span class="sxs-lookup"><span data-stu-id="bdfff-118">All clients with images that need to be updated automatically download the update and apply it to the image.</span></span>

## <a href="" id="bkmk-howtoupdateamedvbaseimage"></a><span data-ttu-id="bdfff-119">如何更新 MED-V 基底影像</span><span class="sxs-lookup"><span data-stu-id="bdfff-119">How to Update a MED-V Base Image</span></span>


**<span data-ttu-id="bdfff-120">若要更新 MED-V 基底影像</span><span class="sxs-lookup"><span data-stu-id="bdfff-120">To update a MED-V base image</span></span>**

1.  <span data-ttu-id="bdfff-121">在 [虛擬 PC2007] 中開啟現有的影像。</span><span class="sxs-lookup"><span data-stu-id="bdfff-121">Open the existing image in Virtual PC2007.</span></span>

2.  <span data-ttu-id="bdfff-122">對影像進行所需的變更，更新影像（例如安裝新軟體）。</span><span class="sxs-lookup"><span data-stu-id="bdfff-122">Make the required changes to the image, updating the image (such as installing new software).</span></span>

3.  <span data-ttu-id="bdfff-123">關閉 [虛擬 PC2007]。</span><span class="sxs-lookup"><span data-stu-id="bdfff-123">Close Virtual PC2007.</span></span>

4.  <span data-ttu-id="bdfff-124">測試影像。</span><span class="sxs-lookup"><span data-stu-id="bdfff-124">Test the image.</span></span>

5.  <span data-ttu-id="bdfff-125">測試完圖像之後，請使用與現有影像相同的名稱將它打包至本機知識庫。</span><span class="sxs-lookup"><span data-stu-id="bdfff-125">After the image is tested, pack it to the local repository, using the same name as the existing image.</span></span>

    <span data-ttu-id="bdfff-126">**記事** 如果您將影像命名為與現有版本不同的名稱，將會建立新的影像，而不是現有影像的新版本。</span><span class="sxs-lookup"><span data-stu-id="bdfff-126">**Note** If you name the image a different name than the existing version, a new image will be created rather than a new version of the existing image.</span></span>

     

6.  <span data-ttu-id="bdfff-127">將新版本上傳到伺服器、將其推入影像的暫存資料夾，或透過部署套件發佈。</span><span class="sxs-lookup"><span data-stu-id="bdfff-127">Upload the new version to the server, push it to the image pre-stage folder, or distribute it via a deployment package.</span></span>

## <span data-ttu-id="bdfff-128">相關主題</span><span class="sxs-lookup"><span data-stu-id="bdfff-128">Related topics</span></span>


[<span data-ttu-id="bdfff-129">建立 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="bdfff-129">Creating a MED-V Image</span></span>](creating-a-med-v-image.md)

[<span data-ttu-id="bdfff-130">如何更新 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="bdfff-130">How to Update a MED-V Image</span></span>](how-to-update-a-med-v-image.md)

[<span data-ttu-id="bdfff-131">設定 MED-V 工作區原則</span><span class="sxs-lookup"><span data-stu-id="bdfff-131">Configuring MED-V Workspace Policies</span></span>](configuring-med-v-workspace-policies.md)

[<span data-ttu-id="bdfff-132">如何設定映像 Web 發佈伺服器</span><span class="sxs-lookup"><span data-stu-id="bdfff-132">How to Configure the Image Web Distribution Server</span></span>](how-to-configure-the-image-web-distribution-server.md)

 

 





