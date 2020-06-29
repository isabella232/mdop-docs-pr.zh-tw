---
title: 建立 MED-V 映像
description: 建立 MED-V 映像
author: dansimp
ms.assetid: 7cbbcd22-83f5-4b60-825f-781b4c6a2d36
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: de1c2cd87d85bbe2fc40b9007eba8f86d2ed6f60
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800109"
---
# <span data-ttu-id="a183b-103">建立 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="a183b-103">Creating a MED-V Image</span></span>


## <span data-ttu-id="a183b-104">本節內容</span><span class="sxs-lookup"><span data-stu-id="a183b-104">In This Section</span></span>


<span data-ttu-id="a183b-105">本節說明如何在已安裝 MED-V 用戶端和 MED-V 管理應用程式的電腦上設定 MED-V 影像，並說明下列事項：</span><span class="sxs-lookup"><span data-stu-id="a183b-105">This section describes how to configure a MED-V image on a computer on which the MED-V client and MED-V management application are installed, and explains the following:</span></span>

<a href="" id="how-to-create-and-test-a-med-v-image"></a>[<span data-ttu-id="a183b-106">如何建立和測試 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="a183b-106">How to Create and Test a MED-V Image</span></span>](how-to-create-and-test-a-med-v-image.md)  
<span data-ttu-id="a183b-107">說明如何建立 MED-V 圖像，然後在本機測試影像。</span><span class="sxs-lookup"><span data-stu-id="a183b-107">Describes how to create a MED-V image, and then test the image locally.</span></span>

<a href="" id="how-to-pack-a-med-v-image"></a>[<span data-ttu-id="a183b-108">如何封裝 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="a183b-108">How to Pack a MED-V Image</span></span>](how-to-pack-a-med-v-image.md)  
<span data-ttu-id="a183b-109">說明如何將 MED-V 影像打包，以便將它新增至部署套件或上傳至伺服器。</span><span class="sxs-lookup"><span data-stu-id="a183b-109">Describes how to pack a MED-V image so that it can be added to a deployment package or uploaded to the server.</span></span>

<a href="" id="how-to-upload-a-med-v-image-to-the-server"></a>[<span data-ttu-id="a183b-110">如何上傳 MED-V 映像至伺服器</span><span class="sxs-lookup"><span data-stu-id="a183b-110">How to Upload a MED-V Image to the Server</span></span>](how-to-upload-a-med-v-image-to-the-server.md)  
<span data-ttu-id="a183b-111">說明如何將 MED-V 影像上傳到伺服器。</span><span class="sxs-lookup"><span data-stu-id="a183b-111">Describes how to upload a MED-V image to the server.</span></span>

<a href="" id="how-to-localize-a-med-v-image"></a>[<span data-ttu-id="a183b-112">如何當地語系化 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="a183b-112">How to Localize a MED-V Image</span></span>](how-to-localize-a-med-v-image.md)  
<span data-ttu-id="a183b-113">說明如何透過提取或下載影像來當地語系化 MED-V 影像。</span><span class="sxs-lookup"><span data-stu-id="a183b-113">Describes how to localize a MED-V image either through extracting or downloading the image.</span></span>

<a href="" id="how-to-update-a-med-v-image"></a>[<span data-ttu-id="a183b-114">如何更新 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="a183b-114">How to Update a MED-V Image</span></span>](how-to-update-a-med-v-image.md)  
<span data-ttu-id="a183b-115">說明如何更新 MED-V 影像來建立新版本的影像。</span><span class="sxs-lookup"><span data-stu-id="a183b-115">Describes how to update a MED-V image to create a new version of the image.</span></span>

<a href="" id="how-to-delete-a-med-v-image"></a>[<span data-ttu-id="a183b-116">如何刪除 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="a183b-116">How to Delete a MED-V Image</span></span>](how-to-delete-a-med-v-image.md)  
<span data-ttu-id="a183b-117">說明如何刪除 MED-V 影像。</span><span class="sxs-lookup"><span data-stu-id="a183b-117">Describes how to delete a MED-V image.</span></span>

<span data-ttu-id="a183b-118">**記事** 在配置 MED-V 圖像之後，電腦不應該是網域的一部分，因為在部署之後，您應該在用戶端上執行 join 網域程式（作為 MED-V 工作區設定的一部分）。</span><span class="sxs-lookup"><span data-stu-id="a183b-118">**Note** After the MED-V image is configured, the computer should not be part of a domain because the join domain procedure should be performed on the client after the deployment, as part of the MED-V workspace setup.</span></span>

 

 

 





