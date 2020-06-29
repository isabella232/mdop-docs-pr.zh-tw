---
title: 如何當地語系化 MED-V 映像
description: 如何當地語系化 MED-V 映像
author: dansimp
ms.assetid: adc148b3-8cfe-42a0-8847-be6b689a673a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 04a56e4e097462bc1f76c7e981cc6c4e077d6d38
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811072"
---
# <span data-ttu-id="dc8fb-103">如何當地語系化 MED-V 映像</span><span class="sxs-lookup"><span data-stu-id="dc8fb-103">How to Localize a MED-V Image</span></span>


<span data-ttu-id="dc8fb-104">MED-V 影像可以當地語系化，只要將封裝的影像解包或從伺服器下載影像即可。</span><span class="sxs-lookup"><span data-stu-id="dc8fb-104">A MED-V image can be localized, either by unpacking a packed image or by downloading an image from the server.</span></span> <span data-ttu-id="dc8fb-105">所有本機映射都會出現在本機知識庫中。</span><span class="sxs-lookup"><span data-stu-id="dc8fb-105">All local images appear in the local repository.</span></span>

## <a href="" id="bkmk-extractinganimageforusebythelocalclient"></a><span data-ttu-id="dc8fb-106">如何提取由本機用戶端使用的 MED-V 影像</span><span class="sxs-lookup"><span data-stu-id="dc8fb-106">How to Extract a MED-V Image for Use by the Local Client</span></span>


<span data-ttu-id="dc8fb-107">您可以透過解壓縮，將打包的影像解包到本機知識庫。</span><span class="sxs-lookup"><span data-stu-id="dc8fb-107">A packed image can be unpacked to the local repository by extracting it.</span></span> <span data-ttu-id="dc8fb-108">然後，就不需要從伺服器下載它。</span><span class="sxs-lookup"><span data-stu-id="dc8fb-108">It then does not need to be downloaded from the server.</span></span>

**<span data-ttu-id="dc8fb-109">若要提取 MED-V 影像</span><span class="sxs-lookup"><span data-stu-id="dc8fb-109">To extract a MED-V image</span></span>**

1.  <span data-ttu-id="dc8fb-110">在 [**本機打包影像**] 窗格中，選取影像。</span><span class="sxs-lookup"><span data-stu-id="dc8fb-110">In the **Local Packed Images** pane, select an image.</span></span>

2.  <span data-ttu-id="dc8fb-111">以滑鼠右鍵按一下，然後從下拉式功能表中選取 [**提取影像**]。</span><span class="sxs-lookup"><span data-stu-id="dc8fb-111">Right-click, and from the drop-down menu, select **Extract image**.</span></span>

    <span data-ttu-id="dc8fb-112">影像會解壓縮到本機磁片磁碟機，而且現在可以由在電腦上執行的本機用戶端使用。</span><span class="sxs-lookup"><span data-stu-id="dc8fb-112">The image is extracted to the local drive and can now be used by the local client running on the computer.</span></span>

## <a href="" id="bkmk-downloadinganimagetothelocalrepoitory"></a><span data-ttu-id="dc8fb-113">如何將 MED-V 影像下載到本機知識庫</span><span class="sxs-lookup"><span data-stu-id="dc8fb-113">How to Download a MED-V Image to the Local Repository</span></span>


**<span data-ttu-id="dc8fb-114">若要下載 MED-V 影像</span><span class="sxs-lookup"><span data-stu-id="dc8fb-114">To download a MED-V image</span></span>**

1.  <span data-ttu-id="dc8fb-115">在 [伺服器] 窗格上的 [**打包影像**] 中，選取要下載之影像的影像或版本。</span><span class="sxs-lookup"><span data-stu-id="dc8fb-115">In the **Packed Images on Server** pane, select the image or version of the image to download.</span></span>

2.  <span data-ttu-id="dc8fb-116">按一下 [**下載**]。</span><span class="sxs-lookup"><span data-stu-id="dc8fb-116">Click **Download**.</span></span>

    <span data-ttu-id="dc8fb-117">影像會下載到您的本機電腦。</span><span class="sxs-lookup"><span data-stu-id="dc8fb-117">The image is downloaded to your local computer.</span></span>

    <span data-ttu-id="dc8fb-118">**記事** 下載的影像將不會出現在 [**本機影像**] 窗格中，直到您重新整理頁面。</span><span class="sxs-lookup"><span data-stu-id="dc8fb-118">**Note** The downloaded image will not appear in the **Local Images** pane until you refresh the page.</span></span> <span data-ttu-id="dc8fb-119">按一下 [重新整理]，即可在 [**本機影像**] 窗格中查看已下載的影像。</span><span class="sxs-lookup"><span data-stu-id="dc8fb-119">Click Refresh to see the downloaded image in the **Local Images** pane.</span></span>

     

## <span data-ttu-id="dc8fb-120">相關主題</span><span class="sxs-lookup"><span data-stu-id="dc8fb-120">Related topics</span></span>


[<span data-ttu-id="dc8fb-121">如何安裝 MED-V 用戶端及 MED-V 管理主控台</span><span class="sxs-lookup"><span data-stu-id="dc8fb-121">How to Install MED-V Client and MED-V Management Console</span></span>](how-to-install-med-v-client-and-med-v-management-console.md)

[<span data-ttu-id="dc8fb-122">使用 MED-V 管理主控台使用者介面</span><span class="sxs-lookup"><span data-stu-id="dc8fb-122">Using the MED-V Management Console User Interface</span></span>](using-the-med-v-management-console-user-interface.md)

[<span data-ttu-id="dc8fb-123">如何上傳 MED-V 映像至伺服器</span><span class="sxs-lookup"><span data-stu-id="dc8fb-123">How to Upload a MED-V Image to the Server</span></span>](how-to-upload-a-med-v-image-to-the-server.md)

 

 





