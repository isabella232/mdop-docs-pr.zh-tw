---
title: 如何上傳 MED-V 映像至伺服器
description: 如何上傳 MED-V 映像至伺服器
author: dansimp
ms.assetid: 0e70dfdf-3e3a-4860-970c-535806caa907
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6703eb24bc3542c280af41988a257a2f14643645
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811313"
---
# <span data-ttu-id="d8c2f-103">如何上傳 MED-V 映像至伺服器</span><span class="sxs-lookup"><span data-stu-id="d8c2f-103">How to Upload a MED-V Image to the Server</span></span>


<span data-ttu-id="d8c2f-104">測試完 MED-V 圖像之後，就可以將它打包，然後上傳到伺服器。</span><span class="sxs-lookup"><span data-stu-id="d8c2f-104">After a MED-V image has been tested, it can be packed and then uploaded to the server.</span></span> <span data-ttu-id="d8c2f-105">如需有關配置影像 Web 發佈伺服器的資訊，請參閱[如何設定影像 Web 發佈伺服器](how-to-configure-the-image-web-distribution-server.md)。</span><span class="sxs-lookup"><span data-stu-id="d8c2f-105">For information on configuring an image Web distribution server, see [How to Configure the Image Web Distribution Server](how-to-configure-the-image-web-distribution-server.md).</span></span>

<span data-ttu-id="d8c2f-106">將 MED-V 影像打包並上傳到伺服器之後，就可以使用企業軟體發行中心將它發佈給使用者，或使用部署套件來供使用者下載。</span><span class="sxs-lookup"><span data-stu-id="d8c2f-106">Once a MED-V image is packed and uploaded to the server, it can be distributed to users by using an enterprise software distribution center, or it can be downloaded by users using a deployment package.</span></span> <span data-ttu-id="d8c2f-107">如需使用企業軟體發行中心進行部署的詳細資訊，請參閱[使用企業軟體發佈系統部署 Med-v 工作區](deploying-a-med-v-workspace-using-an-enterprise-software-distribution-system.md)。</span><span class="sxs-lookup"><span data-stu-id="d8c2f-107">For information on deployment using an enterprise software distribution center, see [Deploying a MED-V Workspace Using an Enterprise Software Distribution System](deploying-a-med-v-workspace-using-an-enterprise-software-distribution-system.md).</span></span> <span data-ttu-id="d8c2f-108">如需使用套件進行部署的相關資訊，請參閱[使用部署套件部署 Med-v 工作區](deploying-a-med-v-workspace-using-a-deployment-package.md)。</span><span class="sxs-lookup"><span data-stu-id="d8c2f-108">For information on deployment using a package, see [Deploying a MED-V Workspace Using a Deployment Package](deploying-a-med-v-workspace-using-a-deployment-package.md).</span></span>

**<span data-ttu-id="d8c2f-109">注意</span><span class="sxs-lookup"><span data-stu-id="d8c2f-109">Note</span></span>**  
<span data-ttu-id="d8c2f-110">在上傳影像之前，請確認未在瀏覽器設定中定義網頁 proxy，且目前未執行 Windows Update。</span><span class="sxs-lookup"><span data-stu-id="d8c2f-110">Before uploading an image, verify that a Web proxy is not defined in your browser settings and that Windows Update is not currently running.</span></span>



**<span data-ttu-id="d8c2f-111">將 MED-V 影像上傳到伺服器</span><span class="sxs-lookup"><span data-stu-id="d8c2f-111">To upload a MED-V image to the server</span></span>**

1.  <span data-ttu-id="d8c2f-112">在 [**本機打包影像**] 窗格中，選取您建立的影像。</span><span class="sxs-lookup"><span data-stu-id="d8c2f-112">In the **Local Packed Images** pane, select the image you created.</span></span>

2.  <span data-ttu-id="d8c2f-113">按一下 **[上傳**]。</span><span class="sxs-lookup"><span data-stu-id="d8c2f-113">Click **Upload**.</span></span>

    <span data-ttu-id="d8c2f-114">圖像會上傳到伺服器。</span><span class="sxs-lookup"><span data-stu-id="d8c2f-114">The image is uploaded to the server.</span></span> <span data-ttu-id="d8c2f-115">這可能需要花費相當長的時間。</span><span class="sxs-lookup"><span data-stu-id="d8c2f-115">This might take a considerable amount of time.</span></span>

    <span data-ttu-id="d8c2f-116">伺服器上的影像是由下表所列的屬性所定義。</span><span class="sxs-lookup"><span data-stu-id="d8c2f-116">Images on the server are defined with the properties listed in the following table.</span></span>

**<span data-ttu-id="d8c2f-117">在伺服器屬性上打包的影像</span><span class="sxs-lookup"><span data-stu-id="d8c2f-117">Packed Images on Server Properties</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="d8c2f-118">屬性</span><span class="sxs-lookup"><span data-stu-id="d8c2f-118">Property</span></span></th>
<th align="left"><span data-ttu-id="d8c2f-119">描述</span><span class="sxs-lookup"><span data-stu-id="d8c2f-119">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d8c2f-120">圖像名稱</span><span class="sxs-lookup"><span data-stu-id="d8c2f-120">Image Name</span></span></p></td>
<td align="left"><p><span data-ttu-id="d8c2f-121">在管理員建立影像時所定義之打包影像的名稱。</span><span class="sxs-lookup"><span data-stu-id="d8c2f-121">The name of the packed image as it was defined when the administrator created the image.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d8c2f-122">版本</span><span class="sxs-lookup"><span data-stu-id="d8c2f-122">Version</span></span></p></td>
<td align="left"><p><span data-ttu-id="d8c2f-123">所顯示影像的版本。</span><span class="sxs-lookup"><span data-stu-id="d8c2f-123">The version of the displayed image.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="d8c2f-124">注意</span><span class="sxs-lookup"><span data-stu-id="d8c2f-124">Note</span></span></strong><br/><p><span data-ttu-id="d8c2f-125">除非刪除，否則所有先前的版本都會保留。</span><span class="sxs-lookup"><span data-stu-id="d8c2f-125">All previous versions are kept unless deleted.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="d8c2f-126">檔案大小（壓縮）</span><span class="sxs-lookup"><span data-stu-id="d8c2f-126">File Size (compressed)</span></span></p></td>
<td align="left"><p><span data-ttu-id="d8c2f-127">影像的實際壓縮大小。</span><span class="sxs-lookup"><span data-stu-id="d8c2f-127">The physical compressed size of the image.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="d8c2f-128">影像大小（未壓縮）</span><span class="sxs-lookup"><span data-stu-id="d8c2f-128">Image Size (uncompressed)</span></span></p></td>
<td align="left"><p><span data-ttu-id="d8c2f-129">影像的實際未壓縮大小。</span><span class="sxs-lookup"><span data-stu-id="d8c2f-129">The physical uncompressed size of the image.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="d8c2f-130">相關主題</span><span class="sxs-lookup"><span data-stu-id="d8c2f-130">Related topics</span></span>


[<span data-ttu-id="d8c2f-131">如何安裝 MED-V 用戶端及 MED-V 管理主控台</span><span class="sxs-lookup"><span data-stu-id="d8c2f-131">How to Install MED-V Client and MED-V Management Console</span></span>](how-to-install-med-v-client-and-med-v-management-console.md)

[<span data-ttu-id="d8c2f-132">使用 MED-V 管理主控台使用者介面</span><span class="sxs-lookup"><span data-stu-id="d8c2f-132">Using the MED-V Management Console User Interface</span></span>](using-the-med-v-management-console-user-interface.md)

[<span data-ttu-id="d8c2f-133">建立 MED-V 的虛擬電腦映像</span><span class="sxs-lookup"><span data-stu-id="d8c2f-133">Creating a Virtual PC Image for MED-V</span></span>](creating-a-virtual-pc-image-for-med-v.md)

[<span data-ttu-id="d8c2f-134">如何封裝 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="d8c2f-134">How to Pack a MED-V Image</span></span>](how-to-pack-a-med-v-image.md)









