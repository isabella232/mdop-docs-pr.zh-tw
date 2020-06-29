---
title: 如何部署 DaRT 復原映像做為修復磁碟分割的一部分
description: 如何部署 DaRT 復原映像做為修復磁碟分割的一部分
author: dansimp
ms.assetid: 462f2d08-f03b-4a07-b2d3-c69205dc6f70
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e75c3f9e58d784c13003feb84001f89c4607115d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810028"
---
# <span data-ttu-id="def53-103">如何部署 DaRT 復原映像做為修復磁碟分割的一部分</span><span class="sxs-lookup"><span data-stu-id="def53-103">How to Deploy the DaRT Recovery Image as Part of a Recovery Partition</span></span>


<span data-ttu-id="def53-104">在您完成執行 DaRT 復原映射嚮導並建立復原映像之後，您可以從 ISO 映像檔中解壓縮 boot.ini 檔案，並將它部署為 Windows 7 影像中的復原分區。</span><span class="sxs-lookup"><span data-stu-id="def53-104">After you have finished running the DaRT Recovery Image Wizard and created the recovery image, you can extract the boot.wim file from the ISO image file and deploy it as a recovery partition in a Windows 7 image.</span></span>

**<span data-ttu-id="def53-105">在 Windows 7 影像的 [恢復] 分區中部署 DaRT</span><span class="sxs-lookup"><span data-stu-id="def53-105">To deploy DaRT in the recovery partition of a Windows 7 image</span></span>**

1.  <span data-ttu-id="def53-106">在您的 Windows 7 影像中建立一個等於或大於您使用**DaRT 復原影像嚮導**所建立之 ISO 映像檔案大小的目標磁碟分割。</span><span class="sxs-lookup"><span data-stu-id="def53-106">Create a target partition in your Windows 7 image that is equal to or greater than the size of the ISO image file that you created by using the **DaRT Recovery Image Wizard**.</span></span>

    <span data-ttu-id="def53-107">DaRT 分區所需的最小大小約為300MB。</span><span class="sxs-lookup"><span data-stu-id="def53-107">The minimum size required for a DaRT partition is approximately 300MB.</span></span> <span data-ttu-id="def53-108">不過，我們建議您450MB，以適應 DaRT 中的遠端連線功能。</span><span class="sxs-lookup"><span data-stu-id="def53-108">However, we recommend 450MB to accommodate for the remote connection functionality in DaRT.</span></span>

2.  <span data-ttu-id="def53-109">從 DaRT ISO 映像檔解壓縮啟動 .wim 檔案。</span><span class="sxs-lookup"><span data-stu-id="def53-109">Extract the boot.wim file from the DaRT ISO image file.</span></span>

    1.  <span data-ttu-id="def53-110">裝載您在 [**建立啟動影像**] 對話方塊中建立的 ISO 映像檔，方法是使用貴公司用來裝載影像的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="def53-110">Mount the ISO image file that you created in the **Create Startup Image** dialog box by using your company’s preferred method of mounting an image.</span></span>

    2.  <span data-ttu-id="def53-111">開啟 ISO 映像檔，然後從裝載的影像中的 [\\sources] 資料夾將 boot.ini 檔案複製到電腦上或外部磁片磁碟機上的位置。</span><span class="sxs-lookup"><span data-stu-id="def53-111">Open the ISO image file and copy the boot.wim file from the \\sources folder in the mounted image to a location on your computer or on an external drive.</span></span>

        <span data-ttu-id="def53-112">**記事** 如果您燒錄了復原影像的 CD 或 DVD，您可以在 CD 或 DVD 上開啟檔案，然後從 \\sources 資料夾中複製 boot.ini 檔案。</span><span class="sxs-lookup"><span data-stu-id="def53-112">**Note** If you burned a CD or DVD of the recovery image, you can open the files on the CD or DVD and copy the boot.wim file from the \\sources folder.</span></span> <span data-ttu-id="def53-113">這可讓您略過裝入影像的需求。</span><span class="sxs-lookup"><span data-stu-id="def53-113">This lets you skip the need to mount the image.</span></span>

         

3.  <span data-ttu-id="def53-114">使用 boot.ini 檔案，透過您公司的標準方法建立自訂的 Windows RE 影像，以建立可引導的復原分區。</span><span class="sxs-lookup"><span data-stu-id="def53-114">Use the boot.wim file to create a bootable recovery partition by using your company’s standard method for creating a custom Windows RE image.</span></span>

    <span data-ttu-id="def53-115">如需如何建立或自訂恢復分區的詳細資訊，請參閱[自訂 WINDOWS RE 體驗](https://go.microsoft.com/fwlink/?LinkId=214222)。</span><span class="sxs-lookup"><span data-stu-id="def53-115">For more information about how to create or customize a recovery partition, see [Customizing the Windows RE Experience](https://go.microsoft.com/fwlink/?LinkId=214222).</span></span>

4.  <span data-ttu-id="def53-116">使用 [恢復] 分區取代 Windows 7 影像中的目標分區。</span><span class="sxs-lookup"><span data-stu-id="def53-116">Replace the target partition in your Windows 7 image with the recovery partition.</span></span>

<span data-ttu-id="def53-117">在您的 Windows 7 映射準備就緒之後，您可以使用公司的標準影像部署程式，將影像發佈到企業中的電腦。</span><span class="sxs-lookup"><span data-stu-id="def53-117">After your Windows 7 image is ready, distribute the image to computers in your enterprise by using your company’s standard image deployment process.</span></span> <span data-ttu-id="def53-118">如需如何建立 Windows 7 影像的詳細資訊，請參閱[建立 windows 7 的標準影像：逐步指南](https://go.microsoft.com/fwlink/?LinkId=212103)。</span><span class="sxs-lookup"><span data-stu-id="def53-118">For more information about how to create a Windows 7 image, see [Building a Standard Image of Windows 7: Step-by-Step Guide](https://go.microsoft.com/fwlink/?LinkId=212103).</span></span>

<span data-ttu-id="def53-119">如需有關如何部署恢復解決方案以在系統發生故障時重新安裝 factory 映射的詳細資訊，請參閱[部署系統復原影像](https://go.microsoft.com/fwlink/?LinkId=214221)。</span><span class="sxs-lookup"><span data-stu-id="def53-119">For more information about how to deploy a recovery solution to reinstall the factory image in the event of a system failure, see [Deploy a System Recovery Image](https://go.microsoft.com/fwlink/?LinkId=214221).</span></span>

## <span data-ttu-id="def53-120">相關主題</span><span class="sxs-lookup"><span data-stu-id="def53-120">Related topics</span></span>


[<span data-ttu-id="def53-121">部署 DaRT 7.0 復原映像</span><span class="sxs-lookup"><span data-stu-id="def53-121">Deploying the DaRT 7.0 Recovery Image</span></span>](deploying-the-dart-70-recovery-image-dart-7.md)

 

 





