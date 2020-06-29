---
title: 如何部署工作區映像
description: 如何部署工作區映像
author: dansimp
ms.assetid: ccc8e89b-1625-4b58-837e-4c6d93d46070
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 4cb16b0a4c278d135fdc9b737aa7a6e9b46115e1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812093"
---
# <span data-ttu-id="10db7-103">如何部署工作區映像</span><span class="sxs-lookup"><span data-stu-id="10db7-103">How to Deploy a Workspace Image</span></span>


<span data-ttu-id="10db7-104">使用企業軟體發佈系統時，可以使用下列其中一種方式，將新影像部署到用戶端電腦上：</span><span class="sxs-lookup"><span data-stu-id="10db7-104">When using an enterprise software distribution system, a new image can be deployed onto client computers in one of the following ways:</span></span>

-   [<span data-ttu-id="10db7-105">網頁下載</span><span class="sxs-lookup"><span data-stu-id="10db7-105">Web download</span></span>](#bkmk-howtodeployaworkspaceimageviatheweb)

-   [<span data-ttu-id="10db7-106">影像預暫存</span><span class="sxs-lookup"><span data-stu-id="10db7-106">Image pre-staging</span></span>](#bkmk-howtodeployaworkspaceimageusingimageprestaging)

## <a href="" id="bkmk-howtodeployaworkspaceimageviatheweb"></a><span data-ttu-id="10db7-107">如何透過 Web 部署工作區圖像</span><span class="sxs-lookup"><span data-stu-id="10db7-107">How to Deploy a Workspace Image via the Web</span></span>


**<span data-ttu-id="10db7-108">透過 Web 部署工作區圖像</span><span class="sxs-lookup"><span data-stu-id="10db7-108">To deploy a workspace image via the Web</span></span>**

1.  <span data-ttu-id="10db7-109">將 MED-V 圖像上傳到伺服器。</span><span class="sxs-lookup"><span data-stu-id="10db7-109">Upload the MED-V image to the server.</span></span>

    <span data-ttu-id="10db7-110">如需有關上傳影像的詳細資訊，請參閱[如何將 Med-v 影像上傳到伺服器](how-to-upload-a-med-v-image-to-the-server.md)。</span><span class="sxs-lookup"><span data-stu-id="10db7-110">For information on uploading the image, see [How to Upload a MED-V Image to the Server](how-to-upload-a-med-v-image-to-the-server.md).</span></span>

2.  <span data-ttu-id="10db7-111">使用您的企業軟體發佈系統，在使用者的電腦上安裝 MED-V 封裝。</span><span class="sxs-lookup"><span data-stu-id="10db7-111">Using your enterprise software distribution system, install the MED-V client .msi package on users’ computers.</span></span>

    <span data-ttu-id="10db7-112">如需安裝 MED-V 用戶端 .msi 套件的相關資訊，請參閱[如何安裝 Med-v 用戶端](how-to-install-med-v-clientesds.md)。</span><span class="sxs-lookup"><span data-stu-id="10db7-112">For information on installing the MED-V client .msi package, see [How to Install MED-V Client](how-to-install-med-v-clientesds.md).</span></span>

    <span data-ttu-id="10db7-113">MED-V 用戶端會在第一次安裝並啟動。</span><span class="sxs-lookup"><span data-stu-id="10db7-113">MED-V client is installed and started for the first time.</span></span> <span data-ttu-id="10db7-114">在初次開機時，用戶端會從用戶端安裝中指定的伺服器位址下載影像。</span><span class="sxs-lookup"><span data-stu-id="10db7-114">On first-time startup, the client downloads the image from the server address specified in the client installation.</span></span>

## <a href="" id="bkmk-howtodeployaworkspaceimageusingimageprestaging"></a><span data-ttu-id="10db7-115">如何使用影像預暫存來部署工作區圖像</span><span class="sxs-lookup"><span data-stu-id="10db7-115">How to Deploy a Workspace Image Using Image Pre-staging</span></span>


**<span data-ttu-id="10db7-116">使用影像預暫存來部署工作區圖像</span><span class="sxs-lookup"><span data-stu-id="10db7-116">To deploy a workspace image using image pre-staging</span></span>**

1.  <span data-ttu-id="10db7-117">建立影像的暫存資料夾，並將影像推至資料夾。</span><span class="sxs-lookup"><span data-stu-id="10db7-117">Create an image pre-stage folder, and push the image to the folder.</span></span>

    <span data-ttu-id="10db7-118">如需有關如何設定影像預暫存的詳細資訊，請參閱[如何設定影像預暫存](how-to-configure-image-pre-staging.md)。</span><span class="sxs-lookup"><span data-stu-id="10db7-118">For information on configuring image pre-staging, see [How to Configure Image Pre-staging](how-to-configure-image-pre-staging.md).</span></span>

2.  <span data-ttu-id="10db7-119">使用您的企業軟體發佈系統，在使用者的電腦上安裝 MED-V 封裝。</span><span class="sxs-lookup"><span data-stu-id="10db7-119">Using your enterprise software distribution system, install the MED-V client .msi package on users’ computers.</span></span>

    <span data-ttu-id="10db7-120">如需安裝 MED-V 用戶端 .msi 套件的相關資訊，請參閱[如何安裝 Med-v 用戶端](how-to-install-med-v-clientesds.md)。</span><span class="sxs-lookup"><span data-stu-id="10db7-120">For information on installing the MED-V client .msi package, see [How to Install MED-V Client](how-to-install-med-v-clientesds.md).</span></span>

    <span data-ttu-id="10db7-121">MED-V 用戶端會在第一次安裝並啟動。</span><span class="sxs-lookup"><span data-stu-id="10db7-121">MED-V client is installed and started for the first time.</span></span> <span data-ttu-id="10db7-122">在第一次啟動時，用戶端會從在用戶端安裝中指定的前階段資料夾中，提取影像。</span><span class="sxs-lookup"><span data-stu-id="10db7-122">On first-time startup, the client fetches the image from the pre-stage folder specified in the client installation.</span></span>

## <span data-ttu-id="10db7-123">相關主題</span><span class="sxs-lookup"><span data-stu-id="10db7-123">Related topics</span></span>


[<span data-ttu-id="10db7-124">如何設定映像 Web 發佈伺服器</span><span class="sxs-lookup"><span data-stu-id="10db7-124">How to Configure the Image Web Distribution Server</span></span>](how-to-configure-the-image-web-distribution-server.md)

 

 





