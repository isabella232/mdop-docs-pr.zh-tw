---
title: 如何部署 DaRT 復原映像做為遠端磁碟分割
description: 如何部署 DaRT 復原映像做為遠端磁碟分割
author: dansimp
ms.assetid: 58f4a6c6-6193-42bd-a095-0de868711af9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: e9a6e3a9dc25139210ae22ba767da984e9a7b86d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808654"
---
# <span data-ttu-id="99735-103">如何部署 DaRT 復原映像做為遠端磁碟分割</span><span class="sxs-lookup"><span data-stu-id="99735-103">How to Deploy the DaRT Recovery Image as a Remote Partition</span></span>


<span data-ttu-id="99735-104">當您執行完 Microsoft Diagnostics 與復原工具集（DaRT）8.0 恢復鏡像嚮導並建立復原影像之後，您可以從 ISO 映像檔中解壓縮 boot.ini 檔案，並將它部署為網路上的遠端分區。</span><span class="sxs-lookup"><span data-stu-id="99735-104">After you have finished running the Microsoft Diagnostics and Recovery Toolset (DaRT) 8.0 Recovery Image wizard and created the recovery image, you can extract the boot.wim file from the ISO image file and deploy it as a remote partition on the network.</span></span>

**<span data-ttu-id="99735-105">將 DaRT 8.0 部署為遠端分區</span><span class="sxs-lookup"><span data-stu-id="99735-105">To deploy DaRT 8.0 as a remote partition</span></span>**

1.  <span data-ttu-id="99735-106">從 DaRT ISO 映像檔解壓縮啟動 .wim 檔案。</span><span class="sxs-lookup"><span data-stu-id="99735-106">Extract the boot.wim file from the DaRT ISO image file.</span></span>

    1.  <span data-ttu-id="99735-107">裝載您在 [**建立啟動影像**] 對話方塊中建立的 ISO 映像檔，方法是使用貴公司用來裝載影像的最佳方式。</span><span class="sxs-lookup"><span data-stu-id="99735-107">Mount the ISO image file that you created in the **Create Startup Image** dialog box by using your company’s preferred method of mounting an image.</span></span>

    2.  <span data-ttu-id="99735-108">開啟 ISO 映像檔，然後從裝載的影像中的 [\\sources] 資料夾將 boot.ini 檔案複製到電腦上或外部磁片磁碟機上的位置。</span><span class="sxs-lookup"><span data-stu-id="99735-108">Open the ISO image file and copy the boot.wim file from the \\sources folder in the mounted image to a location on your computer or on an external drive.</span></span>

        <span data-ttu-id="99735-109">**記事** 如果您燒錄了復原影像的 CD 或 DVD，您可以在 CD 或 DVD 上開啟檔案，然後從 \\sources 資料夾中複製 boot.ini 檔案。</span><span class="sxs-lookup"><span data-stu-id="99735-109">**Note** If you burned a CD or DVD of the recovery image, you can open the files on the CD or DVD and copy the boot.wim file from the \\sources folder.</span></span> <span data-ttu-id="99735-110">這可讓您略過裝入影像的需求。</span><span class="sxs-lookup"><span data-stu-id="99735-110">This lets you skip the need to mount the image.</span></span>

         

2.  <span data-ttu-id="99735-111">將啟動 .wim 檔案部署到可從企業中的最終使用者電腦存取的 WDS 伺服器。</span><span class="sxs-lookup"><span data-stu-id="99735-111">Deploy the boot.wim file to a WDS server that can be accessed from end-user computers in your enterprise.</span></span>

3.  <span data-ttu-id="99735-112">依照您的標準 WDS 部署程式，將 WDS 伺服器設定為使用 DaRT 的 boot.ini 檔案。</span><span class="sxs-lookup"><span data-stu-id="99735-112">Configure the WDS server to use the boot.wim file for DaRT by following your standard WDS deployment procedures.</span></span>

<span data-ttu-id="99735-113">如需如何將 DaRT 部署為遠端分區的詳細資訊，請參閱[逐步引導：使用 PXE](https://go.microsoft.com/fwlink/?LinkId=212108)和[Windows 部署服務快速入門手冊](https://go.microsoft.com/fwlink/?LinkId=212106)來部署影像。</span><span class="sxs-lookup"><span data-stu-id="99735-113">For more information about how to deploy DaRT as a remote partition, see [Walkthrough: Deploy an Image by Using PXE](https://go.microsoft.com/fwlink/?LinkId=212108) and [Windows Deployment Services Getting Started Guide](https://go.microsoft.com/fwlink/?LinkId=212106).</span></span>

## <span data-ttu-id="99735-114">相關主題</span><span class="sxs-lookup"><span data-stu-id="99735-114">Related topics</span></span>


[<span data-ttu-id="99735-115">建立 DaRT 8.0 復原映像</span><span class="sxs-lookup"><span data-stu-id="99735-115">Creating the DaRT 8.0 Recovery Image</span></span>](creating-the-dart-80-recovery-image-dart-8.md)

[<span data-ttu-id="99735-116">部署 DaRT 復原映像</span><span class="sxs-lookup"><span data-stu-id="99735-116">Deploying the DaRT Recovery Image</span></span>](deploying-the-dart-recovery-image-dart-8.md)

[<span data-ttu-id="99735-117">規劃 DaRT 8.0</span><span class="sxs-lookup"><span data-stu-id="99735-117">Planning for DaRT 8.0</span></span>](planning-for-dart-80-dart-8.md)

 

 





