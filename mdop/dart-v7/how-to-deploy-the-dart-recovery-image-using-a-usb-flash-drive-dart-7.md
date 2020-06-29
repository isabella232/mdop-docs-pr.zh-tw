---
title: 如何使用 USB 快閃磁碟來部署 DaRT 復原映像
description: 如何使用 USB 快閃磁碟來部署 DaRT 復原映像
author: dansimp
ms.assetid: 5b7aa843-731e-47e7-b5f9-48d08da732d6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: support
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 1228c9cb5f870162f285d726d48721dde1185107
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810094"
---
# <span data-ttu-id="5f092-103">如何使用 USB 快閃磁碟來部署 DaRT 復原映像</span><span class="sxs-lookup"><span data-stu-id="5f092-103">How to Deploy the DaRT Recovery Image Using a USB Flash Drive</span></span>


<span data-ttu-id="5f092-104">完成執行**DaRT 復原映射嚮導**之後，您可以使用 at 中的工具，將 <https://go.microsoft.com/fwlink/?LinkId=218888> ISO 映像檔案複製到 USB 快閃記憶體磁片磁碟機（UFD）。</span><span class="sxs-lookup"><span data-stu-id="5f092-104">After you have finished running the **DaRT Recovery Image Wizard**, you can use the tool at <https://go.microsoft.com/fwlink/?LinkId=218888> to copy the ISO image file to a USB flash drive (UFD).</span></span>

<span data-ttu-id="5f092-105">您也可以按照本節中提供的步驟，手動將 ISO 映像檔案複製到 UFD。</span><span class="sxs-lookup"><span data-stu-id="5f092-105">You can also manually copy the ISO image file to a UFD by following the steps provided in this section.</span></span>

**<span data-ttu-id="5f092-106">將 DaRT 恢復影像儲存至 USB 快閃記憶體磁片磁碟機</span><span class="sxs-lookup"><span data-stu-id="5f092-106">To save the DaRT recovery image to a USB flash drive</span></span>**

1.  <span data-ttu-id="5f092-107">格式化 USB 快閃記憶體盤磁碟機。</span><span class="sxs-lookup"><span data-stu-id="5f092-107">Format the USB flash drive.</span></span>

    1.  <span data-ttu-id="5f092-108">從執行中的有效作業系統或 WindowsPE 會話中，插入您的 UFD。</span><span class="sxs-lookup"><span data-stu-id="5f092-108">From a running valid operating system or WindowsPE session, insert your UFD.</span></span>

    2.  <span data-ttu-id="5f092-109">在具有系統管理員許可權的命令提示字元中，輸入**DISKPART** ，然後輸入**清單磁片**。</span><span class="sxs-lookup"><span data-stu-id="5f092-109">At the command prompt with administrator permissions, type **DISKPART** and then type **LIST DISK**.</span></span>

        <span data-ttu-id="5f092-110">[命令提示字元] 視窗會顯示 UFD 的磁片編號，例如**磁片 1**。</span><span class="sxs-lookup"><span data-stu-id="5f092-110">The Command Prompt window displays the disk number of your UFD, for example **DISK 1**.</span></span>

    3.  <span data-ttu-id="5f092-111">在命令提示字元中，一次輸入一個下列命令。</span><span class="sxs-lookup"><span data-stu-id="5f092-111">Enter the following commands one at a time at the command prompt.</span></span>

        ``` syntax
        SELECT DISK 1
        CLEAN
        CREATE PARTITION PRIMARY
        SELECT PARTITION 1
        ACTIVE
        FORMAT FS=NTFS
        ASSIGN
        EXIT
        ```

        <span data-ttu-id="5f092-112">**記事** 上述程式碼範例假設 Disk1 是 UFD。</span><span class="sxs-lookup"><span data-stu-id="5f092-112">**Note** The previous code example assumes Disk1 is the UFD.</span></span> <span data-ttu-id="5f092-113">如有需要，請將磁片1取代為您的磁片號碼。</span><span class="sxs-lookup"><span data-stu-id="5f092-113">If it is necessary, replace DISK 1 with your disk number.</span></span>

         

2.  <span data-ttu-id="5f092-114">您可以使用貴公司的慣用方法裝載影像，裝載您在**DaRT 復原映射嚮導**的 [**建立啟動影像**] 對話方塊中建立的 ISO 映像檔。</span><span class="sxs-lookup"><span data-stu-id="5f092-114">By using your company’s preferred method of mounting an image, mount the ISO image file that you created in the **Create Startup Image** dialog box of the **DaRT Recovery Image Wizard**.</span></span> <span data-ttu-id="5f092-115">這需要您有可裝載影像檔案的方法。</span><span class="sxs-lookup"><span data-stu-id="5f092-115">This requires that you have a method available to mount an image file.</span></span>

3.  <span data-ttu-id="5f092-116">開啟掛載的 ISO 映像檔，並將所有內容複寫到格式化的 USB 快閃記憶體磁片磁碟機。</span><span class="sxs-lookup"><span data-stu-id="5f092-116">Open the mounted ISO image file and copy all its contents to the formatted USB flash drive.</span></span>

    <span data-ttu-id="5f092-117">**記事** 如果您燒錄的是 CD 或 DVD 的復原影像，您可以開啟 CD 或 DVD 上的檔案，並將內容複寫到 UFD 中。</span><span class="sxs-lookup"><span data-stu-id="5f092-117">**Note** If you burned a CD or DVD of the recovery image, you can open the files on the CD or DVD and copy the contents to the UFD.</span></span> <span data-ttu-id="5f092-118">這可讓您略過裝入影像的需求。</span><span class="sxs-lookup"><span data-stu-id="5f092-118">This lets you skip the need to mount the image.</span></span>

     

## <span data-ttu-id="5f092-119">相關主題</span><span class="sxs-lookup"><span data-stu-id="5f092-119">Related topics</span></span>


[<span data-ttu-id="5f092-120">部署 DaRT 7.0 復原映像</span><span class="sxs-lookup"><span data-stu-id="5f092-120">Deploying the DaRT 7.0 Recovery Image</span></span>](deploying-the-dart-70-recovery-image-dart-7.md)

 

 





