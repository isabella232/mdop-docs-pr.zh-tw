---
title: 使用企業軟體發佈系統來部署 MED-V 工作區
description: 使用企業軟體發佈系統來部署 MED-V 工作區
author: dansimp
ms.assetid: 867faed6-74ce-4573-84be-8bf26e66c08c
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: fb9ebbc0fb605f84c5a8e67fc77fd9be51b29ff4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810070"
---
# <span data-ttu-id="d5d7c-103">使用企業軟體發佈系統來部署 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="d5d7c-103">Deploying a MED-V Workspace Using an Enterprise Software Distribution System</span></span>


<span data-ttu-id="d5d7c-104">MED-V 用戶端可以使用企業軟體發佈系統（例如 Microsoft System Center Configuration Manager）進行發佈。</span><span class="sxs-lookup"><span data-stu-id="d5d7c-104">MED-V client can be distributed using an enterprise software distribution system, such as Microsoft System Center Configuration Manager.</span></span>

<span data-ttu-id="d5d7c-105">**記事** 如果 MED-V 是使用 Microsoft System Center Configuration Manager 安裝，則在建立 MED-V 的套件時，請將 [執行模式] 設定為 [系統管理許可權]。</span><span class="sxs-lookup"><span data-stu-id="d5d7c-105">**Note** If MED-V is installed by using Microsoft System Center Configuration Manager, when creating a package for MED-V, set the run mode to administrative rights.</span></span>

 

<span data-ttu-id="d5d7c-106">在使用企業軟體發佈系統部署 MED-V 之前，請先確定您已建立 MED-V 影像以供部署。</span><span class="sxs-lookup"><span data-stu-id="d5d7c-106">Before deploying MED-V using an enterprise software distribution system, ensure that you have created a MED-V image ready for deployment.</span></span> <span data-ttu-id="d5d7c-107">如需建立 MED-V 影像的詳細資訊，請參閱[建立 Med-v 影像](creating-a-med-v-image.md)。</span><span class="sxs-lookup"><span data-stu-id="d5d7c-107">For more information on creating a MED-V image, see [Creating a MED-V Image](creating-a-med-v-image.md).</span></span>

<span data-ttu-id="d5d7c-108">準備好 MED-V 影像之後，請考慮在您的環境中散佈影像的最佳方法。</span><span class="sxs-lookup"><span data-stu-id="d5d7c-108">After the MED-V image is prepared, consider the best method for distributing the image in your environment.</span></span> <span data-ttu-id="d5d7c-109">影像可以採用下列其中一種方式來散佈：</span><span class="sxs-lookup"><span data-stu-id="d5d7c-109">The image can be distributed in one of the following ways:</span></span>

-   <span data-ttu-id="d5d7c-110">已上傳至 Web 並透過網頁下載進行發佈，可選擇利用修剪轉移技術。</span><span class="sxs-lookup"><span data-stu-id="d5d7c-110">Uploaded to the Web and distributed via Web download, optionally utilizing Trim Transfer technology.</span></span>

-   <span data-ttu-id="d5d7c-111">使用影像預分段進行發佈。</span><span class="sxs-lookup"><span data-stu-id="d5d7c-111">Distributed using image pre-staging.</span></span>

## <span data-ttu-id="d5d7c-112">透過網路部署影像</span><span class="sxs-lookup"><span data-stu-id="d5d7c-112">Deploying the Image via the Web</span></span>


<span data-ttu-id="d5d7c-113">如果您是透過網路部署影像，請將 MED-V 影像上傳到影像 Web 發佈伺服器。</span><span class="sxs-lookup"><span data-stu-id="d5d7c-113">If you are deploying the image via the Web, upload the MED-V image to an image Web distribution server.</span></span> <span data-ttu-id="d5d7c-114">如需有關配置影像 Web 發佈伺服器的資訊，請參閱[如何設定影像 Web 發佈伺服器](how-to-configure-the-image-web-distribution-server.md)。</span><span class="sxs-lookup"><span data-stu-id="d5d7c-114">For information on configuring an image Web distribution server, see [How to Configure the Image Web Distribution Server](how-to-configure-the-image-web-distribution-server.md).</span></span> <span data-ttu-id="d5d7c-115">如需將影像上傳到伺服器的詳細資訊，請參閱[如何將 Med-v 影像上傳到伺服器](how-to-upload-a-med-v-image-to-the-server.md)。</span><span class="sxs-lookup"><span data-stu-id="d5d7c-115">For information on uploading an image to the server, see [How to Upload a MED-V Image to the Server](how-to-upload-a-med-v-image-to-the-server.md).</span></span>

## <span data-ttu-id="d5d7c-116">透過預分段部署影像</span><span class="sxs-lookup"><span data-stu-id="d5d7c-116">Deploying the Image via Pre-staging</span></span>


<span data-ttu-id="d5d7c-117">如果您是透過圖像預先暫存來部署影像，請設定 [前期階段] 資料夾，然後將 MED-V 影像推至資料夾。</span><span class="sxs-lookup"><span data-stu-id="d5d7c-117">If you are deploying the image via image pre-staging, configure the pre-stage folder, and push the MED-V image to the folder.</span></span> <span data-ttu-id="d5d7c-118">如需有關設定影像預暫存的詳細資訊，請參閱[如何設定影像預暫存](how-to-configure-image-pre-staging.md)。</span><span class="sxs-lookup"><span data-stu-id="d5d7c-118">For more information on configuring image pre-staging, see [How to Configure Image Pre-staging](how-to-configure-image-pre-staging.md).</span></span>

<span data-ttu-id="d5d7c-119">**記事** 如果您使用的是影像預暫存，請務必先設定影像前階段資料夾，然後再推送用戶端 .msi 封裝。</span><span class="sxs-lookup"><span data-stu-id="d5d7c-119">**Note** If you are using image pre-staging, it is important to configure the image pre-stage folder prior to pushing the client .msi package.</span></span> <span data-ttu-id="d5d7c-120">資料夾路徑必須包含在用戶端 .msi 套件中。</span><span class="sxs-lookup"><span data-stu-id="d5d7c-120">The folder path needs to be included in the client .msi package.</span></span>

 

<span data-ttu-id="d5d7c-121">最後，使用您的企業軟體發行中心推送用戶端 .msi 封裝。</span><span class="sxs-lookup"><span data-stu-id="d5d7c-121">Finally, push the client .msi package using your enterprise software distribution center.</span></span> <span data-ttu-id="d5d7c-122">接著，可以安裝 MED-V 並部署影像。</span><span class="sxs-lookup"><span data-stu-id="d5d7c-122">MED-V can then be installed and the image deployed.</span></span> <span data-ttu-id="d5d7c-123">如需安裝 MED-V 用戶端的詳細資訊，請參閱[如何安裝 med-v-v 用戶端](how-to-install-med-v-clientesds.md)。</span><span class="sxs-lookup"><span data-stu-id="d5d7c-123">For more information on installing MED-V client, see [How to Install MED-V Client](how-to-install-med-v-clientesds.md).</span></span> <span data-ttu-id="d5d7c-124">如需有關部署影像的詳細資訊，請參閱[如何部署工作區影像](how-to-deploy-a-workspace-imageesds.md)。</span><span class="sxs-lookup"><span data-stu-id="d5d7c-124">For more information on deploying the image, see [How to Deploy a Workspace Image](how-to-deploy-a-workspace-imageesds.md).</span></span>

 

 





