---
title: 部署 DaRT 7.0 復原映像
description: 部署 DaRT 7.0 復原映像
author: dansimp
ms.assetid: 6bba7bff-800f-44e4-bcfc-e143115607ca
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: cef626e50bf1049529c51afca5e536b03b3d915d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800148"
---
# <span data-ttu-id="0f99d-103">部署 DaRT 7.0 復原映像</span><span class="sxs-lookup"><span data-stu-id="0f99d-103">Deploying the DaRT 7.0 Recovery Image</span></span>


<span data-ttu-id="0f99d-104">在您建立包含 Microsoft Diagnostics 與復原工具集（DaRT）7復原影像的國際標準組織（ISO）檔案之後，您就可以在整個企業中部署 DaRT 復原影像，讓最終使用者和技術支援人員都能使用它。</span><span class="sxs-lookup"><span data-stu-id="0f99d-104">After you have created the International Organization for Standardization (ISO) file that contains the Microsoft Diagnostics and Recovery Toolset (DaRT)7 recovery image, you can deploy the DaRT recovery image throughout your enterprise so that it is available to end users and helpdesk agents.</span></span> <span data-ttu-id="0f99d-105">您可以使用四種受支援的方法來部署 DaRT 恢復影像。</span><span class="sxs-lookup"><span data-stu-id="0f99d-105">There are four supported methods that you can use to deploy the DaRT recovery image.</span></span>

-   <span data-ttu-id="0f99d-106">將 ISO 映像檔燒錄至 CD 或 DVD</span><span class="sxs-lookup"><span data-stu-id="0f99d-106">Burn the ISO image file to a CD or DVD</span></span>

-   <span data-ttu-id="0f99d-107">將 ISO 映像檔的內容儲存至 USB 快閃記憶體磁片磁碟機（UFD）</span><span class="sxs-lookup"><span data-stu-id="0f99d-107">Save the contents of the ISO image file to a USB Flash Drive (UFD)</span></span>

-   <span data-ttu-id="0f99d-108">從 ISO 映像解壓縮啟動 .wim 檔案，並部署為可供最終使用者電腦使用的遠端分區</span><span class="sxs-lookup"><span data-stu-id="0f99d-108">Extract the boot.wim file from the ISO image and deploy as a remote partition that is available to end-user computers</span></span>

-   <span data-ttu-id="0f99d-109">從 ISO 映像抽取 boot.ini 檔案，並在新的 Windows 7 安裝的 [恢復] 分區中部署</span><span class="sxs-lookup"><span data-stu-id="0f99d-109">Extract the boot.wim file from the ISO image and deploy in the recovery partition of a new Windows 7 installation</span></span>

<span data-ttu-id="0f99d-110">**重要** **DaRT 復原映像嚮導**只提供燒錄 CD 或 DVD 的選項。</span><span class="sxs-lookup"><span data-stu-id="0f99d-110">**Important** The **DaRT Recovery Image Wizard** only provides the option to burn a CD or DVD.</span></span> <span data-ttu-id="0f99d-111">所有其他儲存及部署復原影像的方法，都需要一些額外的步驟，涉及 DaRT 中未包含的工具。</span><span class="sxs-lookup"><span data-stu-id="0f99d-111">All other methods of saving and deploying the recovery image require additional steps that involve tools that are not included in DaRT.</span></span> <span data-ttu-id="0f99d-112">本節中提供了這些其他方法的一些指導方針和連結。</span><span class="sxs-lookup"><span data-stu-id="0f99d-112">Some guidance and links for these other methods are provided in this section.</span></span>

 

## <span data-ttu-id="0f99d-113">使用 USB 快閃記憶體磁片磁碟機部署 DaRT 復原影像</span><span class="sxs-lookup"><span data-stu-id="0f99d-113">Deploy the DaRT Recovery Image Using a USB Flash Drive</span></span>


<span data-ttu-id="0f99d-114">完成執行 DaRT 復原映射嚮導之後，您可以使用 at 中的工具，將 <https://go.microsoft.com/fwlink/?LinkId=218888> ISO 映像檔案複製到 USB 快閃記憶體磁片磁碟機（UFD）。</span><span class="sxs-lookup"><span data-stu-id="0f99d-114">After you have finished running the DaRT Recovery Image Wizard, you can use the tool at <https://go.microsoft.com/fwlink/?LinkId=218888> to copy the ISO image file to a USB flash drive (UFD).</span></span>

[<span data-ttu-id="0f99d-115">如何使用 USB 快閃磁碟來部署 DaRT 復原映像</span><span class="sxs-lookup"><span data-stu-id="0f99d-115">How to Deploy the DaRT Recovery Image Using a USB Flash Drive</span></span>](how-to-deploy-the-dart-recovery-image-using-a-usb-flash-drive-dart-7.md)

## <span data-ttu-id="0f99d-116">將 DaRT 復原影像部署成恢復分區的一部分</span><span class="sxs-lookup"><span data-stu-id="0f99d-116">Deploy the DaRT Recovery Image as Part of a Recovery Partition</span></span>


<span data-ttu-id="0f99d-117">在您完成執行 DaRT 復原映射嚮導並建立復原映像之後，您可以從 ISO 映像檔中解壓縮 boot.ini 檔案，並將它部署為 Windows 7 影像中的復原分區。</span><span class="sxs-lookup"><span data-stu-id="0f99d-117">After you have finished running the DaRT Recovery Image Wizard and created the recovery image, you can extract the boot.wim file from the ISO image file and deploy it as a recovery partition in a Windows 7 image.</span></span>

[<span data-ttu-id="0f99d-118">如何部署 DaRT 復原映像做為修復磁碟分割的一部分</span><span class="sxs-lookup"><span data-stu-id="0f99d-118">How to Deploy the DaRT Recovery Image as Part of a Recovery Partition</span></span>](how-to-deploy-the-dart-recovery-image-as-part-of-a-recovery-partition-dart-7.md)

## <span data-ttu-id="0f99d-119">將 DaRT 復原映像部署為遠端分區</span><span class="sxs-lookup"><span data-stu-id="0f99d-119">Deploy the DaRT Recovery Image as a Remote Partition</span></span>


<span data-ttu-id="0f99d-120">當您執行了 DaRT 復原映射嚮導並建立復原映像之後，您可以從 ISO 映像檔中解壓縮 boot.ini 檔案，並將它部署為網路上的遠端分區。</span><span class="sxs-lookup"><span data-stu-id="0f99d-120">After you have finished running the DaRT Recovery Image Wizard and created the recovery image, you can extract the boot.wim file from the ISO image file and deploy it as a remote partition on the network.</span></span>

[<span data-ttu-id="0f99d-121">如何部署 DaRT 復原映像做為遠端磁碟分割</span><span class="sxs-lookup"><span data-stu-id="0f99d-121">How to Deploy the DaRT Recovery Image as a Remote Partition</span></span>](how-to-deploy-the-dart-recovery-image-as-a-remote-partition-dart-7.md)

## <span data-ttu-id="0f99d-122">維護部署 DaRT 恢復影像的其他資源</span><span class="sxs-lookup"><span data-stu-id="0f99d-122">Other resources for maintaining Deploying the DaRT Recovery Image</span></span>


-   [<span data-ttu-id="0f99d-123">部署 DaRT 7.0</span><span class="sxs-lookup"><span data-stu-id="0f99d-123">Deploying DaRT 7.0</span></span>](deploying-dart-70-new-ia.md)

 

 





