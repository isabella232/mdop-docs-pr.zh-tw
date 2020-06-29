---
title: 如何變更快取大小以及磁碟機代號的指定
description: 如何變更快取大小以及磁碟機代號的指定
author: dansimp
ms.assetid: e7d7b635-079e-41aa-a5e6-655f33b4e317
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: cf972f114845064ecf3027cf52d1a038dc6a5118
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801657"
---
# <span data-ttu-id="1f6b6-103">如何變更快取大小以及磁碟機代號的指定</span><span class="sxs-lookup"><span data-stu-id="1f6b6-103">How to Change the Cache Size and the Drive Letter Designation</span></span>


<span data-ttu-id="1f6b6-104">您可以直接從應用程式虛擬化用戶端管理主控台的**應用程式虛擬化**節點變更快取大小與磁片磁碟機號符號。</span><span class="sxs-lookup"><span data-stu-id="1f6b6-104">You can change the cache size and drive letter designation directly from the **Application Virtualization** node in the Application Virtualization Client Management Console.</span></span>

**<span data-ttu-id="1f6b6-105">注意</span><span class="sxs-lookup"><span data-stu-id="1f6b6-105">Note</span></span>**  
<span data-ttu-id="1f6b6-106">設定快取大小之後，就不能變小。</span><span class="sxs-lookup"><span data-stu-id="1f6b6-106">After the cache size has been set, it cannot be made smaller.</span></span>



**<span data-ttu-id="1f6b6-107">變更快取大小</span><span class="sxs-lookup"><span data-stu-id="1f6b6-107">To change the cache size</span></span>**

1.  <span data-ttu-id="1f6b6-108">以滑鼠右鍵按一下**應用程式虛擬化**節點，然後從快顯功能表中選取 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="1f6b6-108">Right-click the **Application Virtualization** node, and select **Properties** from the pop-up menu.</span></span>

2.  <span data-ttu-id="1f6b6-109">選取 [**屬性**] 對話方塊上的 [檔案**系統**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="1f6b6-109">Select the **File System** tab on the **Properties** dialog box.</span></span> <span data-ttu-id="1f6b6-110">在 [**用戶端**快取設定] 區段中，按一下下列其中一個選項按鈕，選擇如何管理快取空間：</span><span class="sxs-lookup"><span data-stu-id="1f6b6-110">In the **Client Cache Configuration Settings** section, click one of the following radio buttons to choose how to manage the cache space:</span></span>

    **<span data-ttu-id="1f6b6-111">重要</span><span class="sxs-lookup"><span data-stu-id="1f6b6-111">Important</span></span>**  
    <span data-ttu-id="1f6b6-112">如果您選取 [**使用可用磁碟空間閾值**] 設定，您所輸入的值會將快取大小設定為磁片總大小減去您所輸入的可用磁碟空間閾值。</span><span class="sxs-lookup"><span data-stu-id="1f6b6-112">If you select the **Use free disk space threshold** setting, the value you enter will set the cache size to the total disk size minus the free disk space threshold number you entered.</span></span> <span data-ttu-id="1f6b6-113">如果您想要使用 [**使用最大**快取大小] 設定還原，您必須指定比現有快取大小更大的數位。</span><span class="sxs-lookup"><span data-stu-id="1f6b6-113">If you then want revert to using the **Use maximum cache size** setting, you must specify a larger number than the existing cache size.</span></span> <span data-ttu-id="1f6b6-114">否則，就會出現「新大小必須大於現有的快取大小」錯誤。</span><span class="sxs-lookup"><span data-stu-id="1f6b6-114">Otherwise, the error “New size must be larger than the existing cache size” will appear.</span></span>



~~~
-   **Use maximum cache size**

    Enter a numeric value from 100 to 1,048,576 (1 TB) in the **Maximum size (MB)** field to specify the maximum size of the cache. The value shown in **Reserved Cache Size** indicates the amount of cache in use.

-   **Use free disk space threshold**

    Enter a numeric value to specify the amount of free disk space, in MB, that the cache must leave available on the disk. This allows the cache to grow until the amount of free disk space reaches this limit. The value shown in **Free disk space remaining** indicates how much disk space is unused.
~~~

3. <span data-ttu-id="1f6b6-115">按一下 **[確定]** **或**[套用] 來變更設定。</span><span class="sxs-lookup"><span data-stu-id="1f6b6-115">Click **OK** or **Apply** to change the setting.</span></span>

**<span data-ttu-id="1f6b6-116">若要變更磁片磁碟機字母指定</span><span class="sxs-lookup"><span data-stu-id="1f6b6-116">To change the drive letter designation</span></span>**

1.  <span data-ttu-id="1f6b6-117">以滑鼠右鍵按一下**應用程式虛擬化**節點，然後從快顯功能表中選取 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="1f6b6-117">Right-click the **Application Virtualization** node, and select **Properties** from the pop-up menu.</span></span>

2.  <span data-ttu-id="1f6b6-118">在 **[內容] 對話方塊的**[檔案**系統**] 索引標籤上，于 [**要使用的磁片磁碟機**] 欄位中，從可用的磁片磁碟機盤符下拉式清單中選取所需的磁碟機盤符。</span><span class="sxs-lookup"><span data-stu-id="1f6b6-118">On the **File System** tab in the **Properties** dialog box, in the **Drive to use** field, select the desired drive letter from the drop-down list of available drive letters.</span></span> <span data-ttu-id="1f6b6-119">當電腦重新開機時，此設定就會生效。</span><span class="sxs-lookup"><span data-stu-id="1f6b6-119">This setting becomes effective when the computer is rebooted.</span></span>

3.  <span data-ttu-id="1f6b6-120">按一下 **[確定]** **或**[套用] 來變更設定。</span><span class="sxs-lookup"><span data-stu-id="1f6b6-120">Click **OK** or **Apply** to change the setting.</span></span>

## <span data-ttu-id="1f6b6-121">相關主題</span><span class="sxs-lookup"><span data-stu-id="1f6b6-121">Related topics</span></span>


[<span data-ttu-id="1f6b6-122">如何在 Application Virtualization Client 管理主控台中設定用戶端</span><span class="sxs-lookup"><span data-stu-id="1f6b6-122">How to Configure the Client in the Application Virtualization Client Management Console</span></span>](how-to-configure-the-client-in-the-application-virtualization-client-management-console.md)









