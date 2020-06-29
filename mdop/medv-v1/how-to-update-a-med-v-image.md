---
title: 如何更新 MED-V 映像
description: 如何更新 MED-V 映像
author: dansimp
ms.assetid: 61eacf50-3a00-4bb8-b2f3-7350a6467fa1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 2f62cbd54d8593646460700a86ea48b5df4ce437
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800108"
---
# <span data-ttu-id="a0b68-103">如何更新 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="a0b68-103">How to Update a MED-V Image</span></span>


## <span data-ttu-id="a0b68-104">如何更新 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="a0b68-104">How to Update a MED-V Image</span></span>


<span data-ttu-id="a0b68-105">您可以更新現有的 MED-V 影像，從而建立新版本的影像。</span><span class="sxs-lookup"><span data-stu-id="a0b68-105">An existing MED-V image can be updated, thereby creating a new version of the image.</span></span> <span data-ttu-id="a0b68-106">新版本可以部署在用戶端電腦上，以取代現有的影像。</span><span class="sxs-lookup"><span data-stu-id="a0b68-106">The new version can then be deployed on client computers, replacing the existing image.</span></span>

<span data-ttu-id="a0b68-107">**記事** 在用戶端上部署新的版本時，會覆寫現有的影像。</span><span class="sxs-lookup"><span data-stu-id="a0b68-107">**Note** When a new version is deployed on the client, it overwrites the existing image.</span></span> <span data-ttu-id="a0b68-108">更新影像時，請確定用戶端上不需要儲存任何資料。</span><span class="sxs-lookup"><span data-stu-id="a0b68-108">When updating an image, ensure that no data on the client needs to be saved.</span></span>

 

**<span data-ttu-id="a0b68-109">更新 MED-V 影像</span><span class="sxs-lookup"><span data-stu-id="a0b68-109">To update a MED-V image</span></span>**

1.  <span data-ttu-id="a0b68-110">在 [虛擬 PC2007] 中開啟現有的影像。</span><span class="sxs-lookup"><span data-stu-id="a0b68-110">Open the existing image in Virtual PC2007.</span></span>

2.  <span data-ttu-id="a0b68-111">對影像進行所需的變更，更新影像（例如安裝新軟體）。</span><span class="sxs-lookup"><span data-stu-id="a0b68-111">Make the required changes to the image, updating the image (such as installing new software).</span></span>

3.  <span data-ttu-id="a0b68-112">關閉 [虛擬 PC2007]。</span><span class="sxs-lookup"><span data-stu-id="a0b68-112">Close Virtual PC2007.</span></span>

4.  <span data-ttu-id="a0b68-113">測試影像。</span><span class="sxs-lookup"><span data-stu-id="a0b68-113">Test the image.</span></span>

5.  <span data-ttu-id="a0b68-114">測試完圖像之後，請使用與現有影像相同的名稱將它打包至本機知識庫。</span><span class="sxs-lookup"><span data-stu-id="a0b68-114">After the image is tested, pack it to the local repository, using the same name as the existing image.</span></span>

    <span data-ttu-id="a0b68-115">**記事** 如果您將影像命名為與現有版本不同的名稱，將會建立新的影像，而不是現有影像的新版本。</span><span class="sxs-lookup"><span data-stu-id="a0b68-115">**Note** If you name the image a different name than the existing version, a new image will be created rather than a new version of the existing image.</span></span>

     

6.  <span data-ttu-id="a0b68-116">將新版本上傳到伺服器或透過部署套件發佈。</span><span class="sxs-lookup"><span data-stu-id="a0b68-116">Upload the new version to the server or distribute it via a deployment package.</span></span>

## <span data-ttu-id="a0b68-117">相關主題</span><span class="sxs-lookup"><span data-stu-id="a0b68-117">Related topics</span></span>


[<span data-ttu-id="a0b68-118">建立 MED-V 的虛擬電腦映像</span><span class="sxs-lookup"><span data-stu-id="a0b68-118">Creating a Virtual PC Image for MED-V</span></span>](creating-a-virtual-pc-image-for-med-v.md)

[<span data-ttu-id="a0b68-119">如何建立和測試 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="a0b68-119">How to Create and Test a MED-V Image</span></span>](how-to-create-and-test-a-med-v-image.md)

[<span data-ttu-id="a0b68-120">如何封裝 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="a0b68-120">How to Pack a MED-V Image</span></span>](how-to-pack-a-med-v-image.md)

[<span data-ttu-id="a0b68-121">如何上傳 MED-V 映像至伺服器</span><span class="sxs-lookup"><span data-stu-id="a0b68-121">How to Upload a MED-V Image to the Server</span></span>](how-to-upload-a-med-v-image-to-the-server.md)

[<span data-ttu-id="a0b68-122">更新 MED-V 工作區映像</span><span class="sxs-lookup"><span data-stu-id="a0b68-122">Updating a MED-V Workspace Image</span></span>](updating-a-med-v-workspace-image.md)

 

 





