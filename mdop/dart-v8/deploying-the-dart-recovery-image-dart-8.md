---
title: 部署 DaRT 復原映像
description: 部署 DaRT 復原映像
author: dansimp
ms.assetid: df5cb54a-be8c-4ed2-89ea-d3c67c2ef4d4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: e445873324f005455ba3c96319847dea8ba761ae
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810359"
---
# <span data-ttu-id="4e0aa-103">部署 DaRT 復原映像</span><span class="sxs-lookup"><span data-stu-id="4e0aa-103">Deploying the DaRT Recovery Image</span></span>


<span data-ttu-id="4e0aa-104">在您建立包含 Microsoft Diagnostics 與復原工具集（DaRT）8.0 復原影像的國際標準組織（ISO）檔案之後，您就可以在整個企業中部署 DaRT 8.0 復原影像，讓使用者可以使用它提供給最終使用者和技術支援人員。</span><span class="sxs-lookup"><span data-stu-id="4e0aa-104">After you have created the International Organization for Standardization (ISO) file that contains the Microsoft Diagnostics and Recovery Toolset (DaRT) 8.0 recovery image, you can deploy the DaRT 8.0 recovery image throughout your enterprise so that it is available to end users and help desk workers.</span></span> <span data-ttu-id="4e0aa-105">您可以使用四種受支援的方法來部署 DaRT 恢復影像。</span><span class="sxs-lookup"><span data-stu-id="4e0aa-105">There are four supported methods that you can use to deploy the DaRT recovery image.</span></span> <span data-ttu-id="4e0aa-106">若要查看每個方法的優點與缺點，請參閱[規劃如何儲存和部署 DaRT 8.0 恢復影像](planning-how-to-save-and-deploy-the-dart-80-recovery-image-dart-8.md)。</span><span class="sxs-lookup"><span data-stu-id="4e0aa-106">To review the advantages and disadvantages of each method, see [Planning How to Save and Deploy the DaRT 8.0 Recovery Image](planning-how-to-save-and-deploy-the-dart-80-recovery-image-dart-8.md).</span></span>

<span data-ttu-id="4e0aa-107">使用 DaRT 復原影像嚮導將 ISO 映像檔燒制到 CD 或 DVD</span><span class="sxs-lookup"><span data-stu-id="4e0aa-107">Burn the ISO image file to a CD or DVD by using the DaRT Recovery Image wizard</span></span>

<span data-ttu-id="4e0aa-108">使用 DaRT 復原影像嚮導，將 ISO 映像檔的內容儲存至 USB 快閃記憶體磁片磁碟機（UFD）</span><span class="sxs-lookup"><span data-stu-id="4e0aa-108">Save the contents of the ISO image file to a USB Flash Drive (UFD) by using the DaRT Recovery Image wizard</span></span>

<span data-ttu-id="4e0aa-109">從 ISO 映像解壓縮啟動 .wim 檔案，並部署為可供最終使用者電腦使用的遠端分區</span><span class="sxs-lookup"><span data-stu-id="4e0aa-109">Extract the boot.wim file from the ISO image and deploy as a remote partition that is available to end-user computers</span></span>

<span data-ttu-id="4e0aa-110">從 ISO 映像抽取 boot.ini 檔案，並在新的 Windows 8 安裝的 [恢復] 分區中部署</span><span class="sxs-lookup"><span data-stu-id="4e0aa-110">Extract the boot.wim file from the ISO image and deploy in the recovery partition of a new Windows 8 installation</span></span>

<span data-ttu-id="4e0aa-111">**重要** **DaRT 復原影像嚮導**提供將影像燒制至 CD、DVD 或 UFD 的選項，但其他儲存及部署恢復影像的方法需要額外的步驟，涉及 DaRT 中未包含的工具。</span><span class="sxs-lookup"><span data-stu-id="4e0aa-111">**Important** The **DaRT Recovery Image Wizard** provides the option to burn the image to a CD, DVD or UFD, but the other methods of saving and deploying the recovery image require additional steps that involve tools that are not included in DaRT.</span></span> <span data-ttu-id="4e0aa-112">本節中提供了這些其他方法的一些指導方針和連結。</span><span class="sxs-lookup"><span data-stu-id="4e0aa-112">Some guidance and links for these other methods are provided in this section.</span></span>

 

## <span data-ttu-id="4e0aa-113">將 DaRT 復原影像部署成恢復分區的一部分</span><span class="sxs-lookup"><span data-stu-id="4e0aa-113">Deploy the DaRT recovery image as part of a recovery partition</span></span>


<span data-ttu-id="4e0aa-114">在您完成執行 DaRT 復原映射嚮導並建立復原映像之後，您可以從 ISO 映像檔解壓縮 boot.ini 檔案，並將它部署為 Windows 8 影像中的復原分區。</span><span class="sxs-lookup"><span data-stu-id="4e0aa-114">After you have finished running the DaRT Recovery Image wizard and created the recovery image, you can extract the boot.wim file from the ISO image file and deploy it as a recovery partition in a Windows 8 image.</span></span>

[<span data-ttu-id="4e0aa-115">如何部署 DaRT 復原映像做為修復磁碟分割的一部分</span><span class="sxs-lookup"><span data-stu-id="4e0aa-115">How to Deploy the DaRT Recovery Image as Part of a Recovery Partition</span></span>](how-to-deploy-the-dart-recovery-image-as-part-of-a-recovery-partition-dart-8.md)

## <span data-ttu-id="4e0aa-116">將 DaRT 復原映像部署為遠端分區</span><span class="sxs-lookup"><span data-stu-id="4e0aa-116">Deploy the DaRT recovery image as a remote partition</span></span>


<span data-ttu-id="4e0aa-117">您可以在中央網路啟動伺服器（例如 Windows 部署服務）上託管復原影像，並允許使用者或支援人員將影像資料流程傳輸給電腦的需求。</span><span class="sxs-lookup"><span data-stu-id="4e0aa-117">You can host the recovery image on a central network boot server, such as Windows Deployment Services, and allow users or support staff to stream the image to computers on demand.</span></span>

[<span data-ttu-id="4e0aa-118">如何部署 DaRT 復原映像做為遠端磁碟分割</span><span class="sxs-lookup"><span data-stu-id="4e0aa-118">How to Deploy the DaRT Recovery Image as a Remote Partition</span></span>](how-to-deploy-the-dart-recovery-image-as-a-remote-partition-dart-8.md)

## <span data-ttu-id="4e0aa-119">部署 DaRT 恢復影像的其他資源</span><span class="sxs-lookup"><span data-stu-id="4e0aa-119">Other resources for deploying the DaRT recovery image</span></span>


[<span data-ttu-id="4e0aa-120">部署 DaRT 8.0</span><span class="sxs-lookup"><span data-stu-id="4e0aa-120">Deploying DaRT 8.0</span></span>](deploying-dart-80-dart-8.md)

 

 





