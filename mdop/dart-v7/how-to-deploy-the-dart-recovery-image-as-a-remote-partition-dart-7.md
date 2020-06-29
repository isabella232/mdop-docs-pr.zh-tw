---
title: 如何部署 DaRT 復原映像做為遠端磁碟分割
description: 如何部署 DaRT 復原映像做為遠端磁碟分割
author: dansimp
ms.assetid: 757c9340-8eac-42e8-85de-4302e436713a
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: a3acdbf72a2c6dac0238f868c7280f1c389b1311
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810034"
---
# <span data-ttu-id="ada49-103">如何部署 DaRT 復原映像做為遠端磁碟分割</span><span class="sxs-lookup"><span data-stu-id="ada49-103">How to Deploy the DaRT Recovery Image as a Remote Partition</span></span>


<span data-ttu-id="ada49-104">當您執行了 DaRT 復原映射嚮導並建立復原映像之後，您可以從 ISO 映像檔中解壓縮 boot.ini 檔案，並將它部署為網路上的遠端分區。</span><span class="sxs-lookup"><span data-stu-id="ada49-104">After you have finished running the DaRT Recovery Image Wizard and created the recovery image, you can extract the boot.wim file from the ISO image file and deploy it as a remote partition on the network.</span></span>

**<span data-ttu-id="ada49-105">將 DaRT 部署為遠端分區</span><span class="sxs-lookup"><span data-stu-id="ada49-105">To deploy DaRT as a remote partition</span></span>**

1.  <span data-ttu-id="ada49-106">從 DaRT ISO 映像檔解壓縮啟動 .wim 檔案。</span><span class="sxs-lookup"><span data-stu-id="ada49-106">Extract the boot.wim file from the DaRT ISO image file.</span></span>

    1.  <span data-ttu-id="ada49-107">裝載您在 [**建立啟動影像**] 對話方塊中建立的 ISO 映像檔，方法是使用貴公司用來裝載影像的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="ada49-107">Mount the ISO image file that you created in the **Create Startup Image** dialog box by using your company’s preferred method of mounting an image.</span></span>

    2.  <span data-ttu-id="ada49-108">開啟 ISO 映像檔，然後從裝載的影像中的 [\\sources] 資料夾將 boot.ini 檔案複製到電腦上或外部磁片磁碟機上的位置。</span><span class="sxs-lookup"><span data-stu-id="ada49-108">Open the ISO image file and copy the boot.wim file from the \\sources folder in the mounted image to a location on your computer or on an external drive.</span></span>

        <span data-ttu-id="ada49-109">**記事** 如果您燒錄了復原影像的 CD 或 DVD，您可以在 CD 或 DVD 上開啟檔案，然後從 \\sources 資料夾中複製 boot.ini 檔案。</span><span class="sxs-lookup"><span data-stu-id="ada49-109">**Note** If you burned a CD or DVD of the recovery image, you can open the files on the CD or DVD and copy the boot.wim file from the \\sources folder.</span></span> <span data-ttu-id="ada49-110">這可讓您略過裝入影像的需求。</span><span class="sxs-lookup"><span data-stu-id="ada49-110">This lets you skip the need to mount the image.</span></span>

         

2.  <span data-ttu-id="ada49-111">將啟動 .wim 檔案部署到可從企業中的最終使用者電腦存取的 WDS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="ada49-111">Deploy the boot.wim file to a WDS server that can be accessed from end-user computers in your enterprise.</span></span>

3.  <span data-ttu-id="ada49-112">依照您的標準 WDS 部署程式，將 WDS 伺服器設定為使用 DaRT 的 boot.ini 檔案。</span><span class="sxs-lookup"><span data-stu-id="ada49-112">Configure the WDS server to use the boot.wim file for DaRT by following your standard WDS deployment procedures.</span></span>

<span data-ttu-id="ada49-113">如需如何將 DaRT 部署為遠端分區的詳細資訊，請參閱下列內容：</span><span class="sxs-lookup"><span data-stu-id="ada49-113">For more information about how to deploy DaRT as a remote partition, see the following:</span></span>

-   [<span data-ttu-id="ada49-114">逐步解說：使用 PXE 部署影像</span><span class="sxs-lookup"><span data-stu-id="ada49-114">Walkthrough: Deploy an Image by Using PXE</span></span>](https://go.microsoft.com/fwlink/?LinkId=212108)

-   [<span data-ttu-id="ada49-115">Windows 部署服務快速入門手冊</span><span class="sxs-lookup"><span data-stu-id="ada49-115">Windows Deployment Services Getting Started Guide</span></span>](https://go.microsoft.com/fwlink/?LinkId=212106)

## <span data-ttu-id="ada49-116">相關主題</span><span class="sxs-lookup"><span data-stu-id="ada49-116">Related topics</span></span>


[<span data-ttu-id="ada49-117">部署 DaRT 7.0 復原映像</span><span class="sxs-lookup"><span data-stu-id="ada49-117">Deploying the DaRT 7.0 Recovery Image</span></span>](deploying-the-dart-70-recovery-image-dart-7.md)

 

 





