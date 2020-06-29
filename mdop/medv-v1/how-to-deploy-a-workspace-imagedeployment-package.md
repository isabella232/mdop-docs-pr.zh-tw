---
title: 如何部署工作區映像
description: 如何部署工作區映像
author: dansimp
ms.assetid: b2c77e0d-101d-4956-a27c-8beb0e4f262e
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d691514691286c92bd62d6fda6666345e17eb9f3
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812099"
---
# <span data-ttu-id="07180-103">如何部署工作區映像</span><span class="sxs-lookup"><span data-stu-id="07180-103">How to Deploy a Workspace Image</span></span>


<span data-ttu-id="07180-104">使用部署套件時，可以使用下列其中一種方法，將新的影像部署到用戶端電腦上：</span><span class="sxs-lookup"><span data-stu-id="07180-104">When using a deployment package, a new image can be deployed onto client computers in one of the following ways:</span></span>

-   [<span data-ttu-id="07180-105">網頁下載</span><span class="sxs-lookup"><span data-stu-id="07180-105">Web download</span></span>](#bkmk-howtodeployaworkspaceimageviatheweb)

-   [<span data-ttu-id="07180-106">影像預暫存</span><span class="sxs-lookup"><span data-stu-id="07180-106">Image pre-staging</span></span>](#bkmk-howtodeployaworkspaceimageusingimageprestaging)

-   [<span data-ttu-id="07180-107">在部署套件內部署映射</span><span class="sxs-lookup"><span data-stu-id="07180-107">Deploying the image inside the deployment package</span></span>](#bkmk-howtodeployaworkspaceimageusingadeploymentapackage)

## <a href="" id="bkmk-howtodeployaworkspaceimageviatheweb"></a><span data-ttu-id="07180-108">如何透過 Web 部署工作區圖像</span><span class="sxs-lookup"><span data-stu-id="07180-108">How to Deploy a Workspace Image via the Web</span></span>


**<span data-ttu-id="07180-109">透過 Web 部署工作區圖像</span><span class="sxs-lookup"><span data-stu-id="07180-109">To deploy a workspace image via the Web</span></span>**

1.  <span data-ttu-id="07180-110">將 MED-V 圖像上傳到伺服器。</span><span class="sxs-lookup"><span data-stu-id="07180-110">Upload the MED-V image to the server.</span></span>

    <span data-ttu-id="07180-111">如需有關上傳影像的詳細資訊，請參閱[如何將 Med-v 影像上傳到伺服器](how-to-upload-a-med-v-image-to-the-server.md)。</span><span class="sxs-lookup"><span data-stu-id="07180-111">For information on uploading the image, see [How to Upload a MED-V Image to the Server](how-to-upload-a-med-v-image-to-the-server.md).</span></span>

2.  <span data-ttu-id="07180-112">建立部署套件，並將伺服器路徑納入至影像的位置。</span><span class="sxs-lookup"><span data-stu-id="07180-112">Create a deployment package, and include the server path to the location of the image.</span></span>

    <span data-ttu-id="07180-113">如需建立部署套件的相關資訊，請參閱[如何設定部署套件](how-to-configure-a-deployment-package.md)。</span><span class="sxs-lookup"><span data-stu-id="07180-113">For information on creating a deployment package, see [How to Configure a Deployment Package](how-to-configure-a-deployment-package.md).</span></span>

3.  <span data-ttu-id="07180-114">將套件部署到最終使用者。</span><span class="sxs-lookup"><span data-stu-id="07180-114">Deploy the package to end users.</span></span>

    <span data-ttu-id="07180-115">如需有關部署套件的詳細資訊，請參閱[如何安裝 Med-v 用戶端](how-to-install-med-v-clientdeployment-package.md)。</span><span class="sxs-lookup"><span data-stu-id="07180-115">For information on deploying the package, see [How to Install MED-V Client](how-to-install-med-v-clientdeployment-package.md).</span></span>

    <span data-ttu-id="07180-116">MED-V 用戶端會在第一次安裝並啟動。</span><span class="sxs-lookup"><span data-stu-id="07180-116">MED-V client is installed and started for the first time.</span></span> <span data-ttu-id="07180-117">在初次開機時，用戶端會從用戶端安裝中指定的伺服器位址下載影像。</span><span class="sxs-lookup"><span data-stu-id="07180-117">On first-time startup, the client downloads the image from the server address specified in the client installation.</span></span>

## <a href="" id="bkmk-howtodeployaworkspaceimageusingimageprestaging"></a><span data-ttu-id="07180-118">如何使用影像預暫存來部署工作區圖像</span><span class="sxs-lookup"><span data-stu-id="07180-118">How to Deploy a Workspace Image Using Image Pre-staging</span></span>


**<span data-ttu-id="07180-119">使用影像預暫存來部署工作區圖像</span><span class="sxs-lookup"><span data-stu-id="07180-119">To deploy a workspace image using image pre-staging</span></span>**

1.  <span data-ttu-id="07180-120">建立影像的暫存資料夾，並將影像推至資料夾。</span><span class="sxs-lookup"><span data-stu-id="07180-120">Create an image pre-stage folder, and push the image to the folder.</span></span>

    <span data-ttu-id="07180-121">如需有關如何設定影像預暫存的詳細資訊，請參閱[如何設定影像預暫存](how-to-configure-image-pre-staging.md)。</span><span class="sxs-lookup"><span data-stu-id="07180-121">For information on configuring image pre-staging, see [How to Configure Image Pre-staging](how-to-configure-image-pre-staging.md).</span></span>

2.  <span data-ttu-id="07180-122">建立部署套件，並包含影像前暫存資料夾的路徑。</span><span class="sxs-lookup"><span data-stu-id="07180-122">Create a deployment package, and include the path to the image pre-stage folder.</span></span>

    <span data-ttu-id="07180-123">如需建立部署套件的相關資訊，請參閱[如何設定部署套件](how-to-configure-a-deployment-package.md)。</span><span class="sxs-lookup"><span data-stu-id="07180-123">For information on creating a deployment package, see [How to Configure a Deployment Package](how-to-configure-a-deployment-package.md).</span></span>

3.  <span data-ttu-id="07180-124">將套件部署到最終使用者。</span><span class="sxs-lookup"><span data-stu-id="07180-124">Deploy the package to end users.</span></span>

    <span data-ttu-id="07180-125">如需有關部署套件的詳細資訊，請參閱[如何安裝 Med-v 用戶端](how-to-install-med-v-clientdeployment-package.md)。</span><span class="sxs-lookup"><span data-stu-id="07180-125">For information on deploying the package, see [How to Install MED-V Client](how-to-install-med-v-clientdeployment-package.md).</span></span>

    <span data-ttu-id="07180-126">MED-V 用戶端會在第一次安裝並啟動。</span><span class="sxs-lookup"><span data-stu-id="07180-126">MED-V client is installed and started for the first time.</span></span> <span data-ttu-id="07180-127">在第一次啟動時，用戶端會從在用戶端安裝中指定的前階段資料夾中，提取影像。</span><span class="sxs-lookup"><span data-stu-id="07180-127">On first-time startup, the client fetches the image from the pre-stage folder specified in the client installation.</span></span>

## <a href="" id="bkmk-howtodeployaworkspaceimageusingadeploymentapackage"></a><span data-ttu-id="07180-128">如何使用部署套件部署工作區圖像</span><span class="sxs-lookup"><span data-stu-id="07180-128">How to Deploy a Workspace Image Using a Deployment Package</span></span>


**<span data-ttu-id="07180-129">使用部署套件部署工作區圖像</span><span class="sxs-lookup"><span data-stu-id="07180-129">To deploy a workspace image using a deployment package</span></span>**

1.  <span data-ttu-id="07180-130">建立部署套件，並將影像包含在套件中。</span><span class="sxs-lookup"><span data-stu-id="07180-130">Create a deployment package, and include the image in the package.</span></span>

    <span data-ttu-id="07180-131">如需建立部署套件的相關資訊，請參閱[如何設定部署套件](how-to-configure-a-deployment-package.md)。</span><span class="sxs-lookup"><span data-stu-id="07180-131">For information on creating a deployment package, see [How to Configure a Deployment Package](how-to-configure-a-deployment-package.md).</span></span>

2.  <span data-ttu-id="07180-132">將套件部署到最終使用者。</span><span class="sxs-lookup"><span data-stu-id="07180-132">Deploy the package to end users.</span></span>

    <span data-ttu-id="07180-133">如需有關部署套件的詳細資訊，請參閱[如何安裝 Med-v 用戶端](how-to-install-med-v-clientdeployment-package.md)。</span><span class="sxs-lookup"><span data-stu-id="07180-133">For information on deploying the package, see [How to Install MED-V Client](how-to-install-med-v-clientdeployment-package.md).</span></span>

    <span data-ttu-id="07180-134">在套件安裝過程中，會將圖像匯入到主機。</span><span class="sxs-lookup"><span data-stu-id="07180-134">The image is imported to the host as part of the package installation.</span></span>

## <span data-ttu-id="07180-135">相關主題</span><span class="sxs-lookup"><span data-stu-id="07180-135">Related topics</span></span>


[<span data-ttu-id="07180-136">如何設定映像 Web 發佈伺服器</span><span class="sxs-lookup"><span data-stu-id="07180-136">How to Configure the Image Web Distribution Server</span></span>](how-to-configure-the-image-web-distribution-server.md)

[<span data-ttu-id="07180-137">如何設定部署套件</span><span class="sxs-lookup"><span data-stu-id="07180-137">How to Configure a Deployment Package</span></span>](how-to-configure-a-deployment-package.md)

 

 





