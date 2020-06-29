---
title: 如何建立排序器封裝根目錄
description: 如何建立排序器封裝根目錄
author: dansimp
ms.assetid: 23fe28f1-c284-43ee-b8b7-1dfbed94eea5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5150e87915202794624b6c51510e56454d2c7d36
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801489"
---
# <span data-ttu-id="5aa9b-103">如何建立排序器封裝根目錄</span><span class="sxs-lookup"><span data-stu-id="5aa9b-103">How to Create the Sequencer Package Root Directory</span></span>


<span data-ttu-id="5aa9b-104">[套件根目錄] 是電腦上執行 App-v 排序器之檔案的目錄，其中安裝已排序之應用程式的檔案。</span><span class="sxs-lookup"><span data-stu-id="5aa9b-104">The package root directory is the directory on the computer running the App-V Sequencer where files for the sequenced application are installed.</span></span> <span data-ttu-id="5aa9b-105">這個目錄也會在您的電腦上以資料流程的方式存在。</span><span class="sxs-lookup"><span data-stu-id="5aa9b-105">This directory also exists virtually on the computer to which a sequenced application will be streamed.</span></span> <span data-ttu-id="5aa9b-106">您應該先建立套件根目錄，然後再監視安裝新的應用程式。</span><span class="sxs-lookup"><span data-stu-id="5aa9b-106">You should create the package root directory before you monitor the installation of a new application.</span></span>

<span data-ttu-id="5aa9b-107">建立套件根目錄之後，您就可以開始順序應用程式。</span><span class="sxs-lookup"><span data-stu-id="5aa9b-107">After you have created the package root directory, you can begin sequencing applications.</span></span> <span data-ttu-id="5aa9b-108">如需針對新的應用程式排序的詳細資訊，請參閱[如何為應用程式](how-to-sequence-an-application.md)排序。</span><span class="sxs-lookup"><span data-stu-id="5aa9b-108">For more information about sequencing a new application, see [How to Sequence an Application](how-to-sequence-an-application.md).</span></span>

**<span data-ttu-id="5aa9b-109">建立套件根目錄</span><span class="sxs-lookup"><span data-stu-id="5aa9b-109">To create the package root directory</span></span>**

1.  <span data-ttu-id="5aa9b-110">若要在執行 App-v 排序器的電腦上建立套件根目錄，請將 Q:\\ 磁片磁碟機對應至指定的網路位置。</span><span class="sxs-lookup"><span data-stu-id="5aa9b-110">To create the package root directory, on the computer running the App-V Sequencer, map the Q:\\ drive to the specified network location.</span></span> <span data-ttu-id="5aa9b-111">您指定的位置應該有足夠的空間來儲存您正在排序的應用程式。</span><span class="sxs-lookup"><span data-stu-id="5aa9b-111">The location you specify should have sufficient space to save the application you are sequencing.</span></span>

2.  <span data-ttu-id="5aa9b-112">若要建立可用於新虛擬應用程式的目錄，請在 Q:\\ 磁片磁碟機上建立一個資料夾，並為它指派名稱。</span><span class="sxs-lookup"><span data-stu-id="5aa9b-112">To create a directory that you can use for a new virtual application, create a folder on the Q:\\ drive and assign it a name.</span></span>

    <span data-ttu-id="5aa9b-113">**重要** 您指派給將儲存在套件根目錄中之虛擬應用程式檔案的名稱，應該使用8.3 命名格式。</span><span class="sxs-lookup"><span data-stu-id="5aa9b-113">**Important** The name you assign to virtual application files that will be saved in the package root directory should use the 8.3 naming format.</span></span> <span data-ttu-id="5aa9b-114">檔案名不應長於8個字元，且具有三個字元的副檔名。</span><span class="sxs-lookup"><span data-stu-id="5aa9b-114">The file names should be no longer than 8 characters with a three-character file name extension.</span></span>

     

## <span data-ttu-id="5aa9b-115">相關主題</span><span class="sxs-lookup"><span data-stu-id="5aa9b-115">Related topics</span></span>


[<span data-ttu-id="5aa9b-116">Application Virtualization Sequencer</span><span class="sxs-lookup"><span data-stu-id="5aa9b-116">Application Virtualization Sequencer</span></span>](application-virtualization-sequencer.md)

[<span data-ttu-id="5aa9b-117">如何修改記錄檔目錄位置</span><span class="sxs-lookup"><span data-stu-id="5aa9b-117">How to Modify the Log Directory Location</span></span>](how-to-modify-the-log-directory-location.md)

[<span data-ttu-id="5aa9b-118">如何修改臨時目錄位置</span><span class="sxs-lookup"><span data-stu-id="5aa9b-118">How to Modify the Scratch Directory Location</span></span>](how-to-modify-the-scratch-directory-location.md)

 

 





