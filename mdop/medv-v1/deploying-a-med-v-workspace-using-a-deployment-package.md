---
title: 使用部署套件來部署 MED-V 工作區
description: 使用部署套件來部署 MED-V 工作區
author: dansimp
ms.assetid: e07fa70a-1a9f-486f-9a86-b33593b234da
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dc16b32fd44e45606df5502fda2e580d404dbb19
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810071"
---
# <span data-ttu-id="50ac1-103">使用部署套件來部署 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="50ac1-103">Deploying a MED-V Workspace Using a Deployment Package</span></span>


<span data-ttu-id="50ac1-104">部署套件安裝提供了一種安裝 MED-V 用戶端的方法，以及由管理員預先定義的所有設定。</span><span class="sxs-lookup"><span data-stu-id="50ac1-104">The deployment package installation provides a method of installing MED-V client together with all its required prerequisites as well as any settings predefined by the administrator.</span></span>

<span data-ttu-id="50ac1-105">使用部署套件時，套件是透過共用的網路或卸除式媒體來發佈。</span><span class="sxs-lookup"><span data-stu-id="50ac1-105">When using a deployment package, the package is distributed via a shared network or removable media.</span></span> <span data-ttu-id="50ac1-106">影像可包含在套件中，或可單獨散佈。</span><span class="sxs-lookup"><span data-stu-id="50ac1-106">The image can be included in the package or can be distributed separately.</span></span>

<span data-ttu-id="50ac1-107">在建立部署套件之前，請先確定您已建立 MED-V 影像準備好進行部署。</span><span class="sxs-lookup"><span data-stu-id="50ac1-107">Before creating a deployment package, ensure that you have created a MED-V image ready for deployment.</span></span> <span data-ttu-id="50ac1-108">如需建立 MED-V 影像的詳細資訊，請參閱[建立 Med-v 影像](creating-a-med-v-image.md)。</span><span class="sxs-lookup"><span data-stu-id="50ac1-108">For more information on creating a MED-V image, see [Creating a MED-V Image](creating-a-med-v-image.md).</span></span>

<span data-ttu-id="50ac1-109">準備好 MED-V 影像之後，請考慮在您的環境中散佈影像的最佳方法。</span><span class="sxs-lookup"><span data-stu-id="50ac1-109">After the MED-V image is prepared, consider the best method for distributing the image in your environment.</span></span> <span data-ttu-id="50ac1-110">影像可以採用下列其中一種方式來散佈：</span><span class="sxs-lookup"><span data-stu-id="50ac1-110">The image can be distributed in one of the following ways:</span></span>

-   <span data-ttu-id="50ac1-111">已上傳至 Web 並透過網頁下載進行發佈，您可以選擇使用修剪轉移技術。</span><span class="sxs-lookup"><span data-stu-id="50ac1-111">Uploaded to the Web and distributed via Web download, optionally using Trim Transfer technology.</span></span>

-   <span data-ttu-id="50ac1-112">使用影像預分段進行發佈。</span><span class="sxs-lookup"><span data-stu-id="50ac1-112">Distributed using image pre-staging.</span></span>

-   <span data-ttu-id="50ac1-113">包含在部署套件中，並與所有其他 MED-V 元件一起散佈。</span><span class="sxs-lookup"><span data-stu-id="50ac1-113">Included in the deployment package and distributed together with all the other MED-V components.</span></span>

<span data-ttu-id="50ac1-114">如果圖像將包含在套件中，則不需要任何其他配置適用于影像。</span><span class="sxs-lookup"><span data-stu-id="50ac1-114">If the image will be included in the package, no other configurations are necessary for the image.</span></span> <span data-ttu-id="50ac1-115">如果 [部署套件] 中不包含該圖像，請執行下列其中一項操作：</span><span class="sxs-lookup"><span data-stu-id="50ac1-115">If the image will not be included in the deployment package, do one of the following:</span></span>

-   <span data-ttu-id="50ac1-116">如果您是透過網路部署影像，請將 MED-V 影像上傳到影像 Web 發佈伺服器。</span><span class="sxs-lookup"><span data-stu-id="50ac1-116">If you are deploying the image via the Web, upload the MED-V image to the image Web distribution server.</span></span> <span data-ttu-id="50ac1-117">如需有關配置影像 Web 發佈伺服器的資訊，請參閱[如何設定影像 Web 發佈伺服器](how-to-configure-the-image-web-distribution-server.md)。</span><span class="sxs-lookup"><span data-stu-id="50ac1-117">For information on configuring an image Web distribution server, see [How to Configure the Image Web Distribution Server](how-to-configure-the-image-web-distribution-server.md).</span></span> <span data-ttu-id="50ac1-118">如需將影像上傳到伺服器的詳細資訊，請參閱[如何將 Med-v 影像上傳到伺服器](how-to-upload-a-med-v-image-to-the-server.md)。</span><span class="sxs-lookup"><span data-stu-id="50ac1-118">For information on uploading an image to the server, see [How to Upload a MED-V Image to the Server](how-to-upload-a-med-v-image-to-the-server.md).</span></span>

-   <span data-ttu-id="50ac1-119">如果您是透過圖像預先暫存來部署影像，請設定 [前期階段] 資料夾，然後將 MED-V 影像推至資料夾。</span><span class="sxs-lookup"><span data-stu-id="50ac1-119">If you are deploying the image via image pre-staging, configure the pre-stage folder, and push the MED-V image to the folder.</span></span> <span data-ttu-id="50ac1-120">如需有關如何設定影像預暫存的詳細資訊，請參閱[如何設定影像預暫存](how-to-configure-image-pre-staging.md)。</span><span class="sxs-lookup"><span data-stu-id="50ac1-120">For more information on configuring the image pre-staging, see [How to Configure Image Pre-staging](how-to-configure-image-pre-staging.md).</span></span>

<span data-ttu-id="50ac1-121">**記事** 如果您使用的是影像預暫存，請務必先設定影像前階段資料夾，然後再建立部署套件。</span><span class="sxs-lookup"><span data-stu-id="50ac1-121">**Note** If you are using image pre-staging, it is important to configure the image pre-stage folder prior to creating the deployment package.</span></span> <span data-ttu-id="50ac1-122">資料夾路徑必須包含在部署套件中。</span><span class="sxs-lookup"><span data-stu-id="50ac1-122">The folder path needs to be included in the deployment package.</span></span>

 

<span data-ttu-id="50ac1-123">最後，建立部署套件。</span><span class="sxs-lookup"><span data-stu-id="50ac1-123">Finally, create the deployment package.</span></span> <span data-ttu-id="50ac1-124">如需建立部署套件的詳細資訊，請參閱[如何設定部署套件](how-to-configure-a-deployment-package.md)。</span><span class="sxs-lookup"><span data-stu-id="50ac1-124">For more information on creating a deployment package, see [How to Configure a Deployment Package](how-to-configure-a-deployment-package.md).</span></span> <span data-ttu-id="50ac1-125">套件完成後，發佈以進行部署。</span><span class="sxs-lookup"><span data-stu-id="50ac1-125">After the package is complete, distribute it for deployment.</span></span>

<span data-ttu-id="50ac1-126">部署套件發佈之後，就可以安裝 MED-V 用戶端和部署的影像。</span><span class="sxs-lookup"><span data-stu-id="50ac1-126">After the deployment package is distributed, MED-V client can be installed and the image deployed.</span></span> <span data-ttu-id="50ac1-127">如需安裝 MED-V 用戶端的詳細資訊，請參閱[如何安裝 med-v-v 用戶端](how-to-install-med-v-clientdeployment-package.md)。</span><span class="sxs-lookup"><span data-stu-id="50ac1-127">For more information on installing MED-V client, see [How to Install MED-V Client](how-to-install-med-v-clientdeployment-package.md).</span></span> <span data-ttu-id="50ac1-128">如需有關部署影像的詳細資訊，請參閱[如何部署工作區影像](how-to-deploy-a-workspace-imagedeployment-package.md)。</span><span class="sxs-lookup"><span data-stu-id="50ac1-128">For more information on deploying the image, see [How to Deploy a Workspace Image](how-to-deploy-a-workspace-imagedeployment-package.md).</span></span>

 

 





