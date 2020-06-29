---
title: 如何變更記錄報告層級以及重設記錄檔
description: 如何變更記錄報告層級以及重設記錄檔
author: dansimp
ms.assetid: 9561d6fb-b35c-491b-a355-000064583194
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 7307dee0030d9c03a8107d9d0ceef2086a94df07
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801661"
---
# <span data-ttu-id="80651-103">如何變更記錄報告層級以及重設記錄檔</span><span class="sxs-lookup"><span data-stu-id="80651-103">How to Change the Log Reporting Levels and Reset the Log Files</span></span>


<span data-ttu-id="80651-104">您可以使用下列程式，在應用程式虛擬化管理主控台中變更**應用程式虛擬化**節點的記錄報告層級。</span><span class="sxs-lookup"><span data-stu-id="80651-104">You can use the following procedure to change the log reporting level from the **Application Virtualization** node in the Application Virtualization Management Console.</span></span> <span data-ttu-id="80651-105">當記錄檔案達到最大大小時（預設值為 256 MB），當下次寫入記錄時，就會強制執行重設。</span><span class="sxs-lookup"><span data-stu-id="80651-105">When the log file reaches the maximum size (default is 256 MB), a reset is forced when the next write to the log occurs.</span></span> <span data-ttu-id="80651-106">[重設] 會建立新的記錄檔案，而舊的檔案會重新命名為 [備份]。</span><span class="sxs-lookup"><span data-stu-id="80651-106">A reset causes a new log file to be created, and the old file is renamed as a backup.</span></span>

**<span data-ttu-id="80651-107">變更記錄報告層級</span><span class="sxs-lookup"><span data-stu-id="80651-107">To change the log reporting level</span></span>**

1.  <span data-ttu-id="80651-108">以滑鼠右鍵按一下**應用程式虛擬化**節點，然後從快顯功能表中選取 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="80651-108">Right-click the **Application Virtualization** node, and select **Properties** from the pop-up menu.</span></span>

2.  <span data-ttu-id="80651-109">在 **[內容] 對話方塊的**[**一般**] 索引標籤上，從 [**記錄層級**] 下拉式清單中，選取想要的記錄層級。</span><span class="sxs-lookup"><span data-stu-id="80651-109">On the **General** tab in the **Properties** dialog box, from the **Log Level** drop-down list, select the desired log level.</span></span>

    <span data-ttu-id="80651-110">**記事** 如果您選擇 [**詳細**] 作為記錄層級，記錄檔就會很快變大。</span><span class="sxs-lookup"><span data-stu-id="80651-110">**Note** If you choose **Verbose** as the logging level, the log files will grow large very quickly.</span></span> <span data-ttu-id="80651-111">這可能會影響用戶端效能，所以最佳做法是只使用這個記錄層級來診斷特定問題。</span><span class="sxs-lookup"><span data-stu-id="80651-111">This might inhibit client performance, so best practice is to use this log level only for diagnosing specific problems.</span></span>

     

3.  <span data-ttu-id="80651-112">在 **[內容] 對話方塊的**[**一般**] 索引標籤上，從 [**系統記錄層級**] 下拉式清單中，選取想要的記錄層級。</span><span class="sxs-lookup"><span data-stu-id="80651-112">On the **General** tab in the **Properties** dialog box, from the **System Log Level** drop-down list, select the desired log level.</span></span>

    <span data-ttu-id="80651-113">**記事** **系統記錄層級**設定控制傳送至系統事件記錄條的訊息層級。</span><span class="sxs-lookup"><span data-stu-id="80651-113">**Note** The **System Log Level** setting controls the level of messages sent to the system event log.</span></span> <span data-ttu-id="80651-114">記錄的訊息與記錄在用戶端事件日誌中的訊息完全相同，但會儲存在不同的位置。</span><span class="sxs-lookup"><span data-stu-id="80651-114">The logged messages are identical to the messages that get logged to the client event log, but they are stored in a different location.</span></span>

     

4.  <span data-ttu-id="80651-115">按一下 **[確定]** **或**[套用] 來變更設定。</span><span class="sxs-lookup"><span data-stu-id="80651-115">Click **OK** or **Apply** to change the setting.</span></span>

**<span data-ttu-id="80651-116">重設記錄檔</span><span class="sxs-lookup"><span data-stu-id="80651-116">To reset the log file</span></span>**

1.  <span data-ttu-id="80651-117">以滑鼠右鍵按一下**應用程式虛擬化**節點，然後從快顯功能表中選取 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="80651-117">Right-click the **Application Virtualization** node, and select **Properties** from the pop-up menu.</span></span>

2.  <span data-ttu-id="80651-118">在 [**屬性**] 對話方塊的 [**一般**] 索引標籤上，按一下 [**重設記錄**] 以備份目前的記錄檔，並立即開始新的記錄檔。</span><span class="sxs-lookup"><span data-stu-id="80651-118">On the **General** tab in the **Properties** dialog box, click **Reset Log** to back up the current log file and immediately start a new log file.</span></span> <span data-ttu-id="80651-119">備份記錄檔儲存在相同的資料夾中。</span><span class="sxs-lookup"><span data-stu-id="80651-119">The backup log files are stored in the same folder.</span></span>

3.  <span data-ttu-id="80651-120">按一下 **[確定]** **或**[套用] 來變更設定。</span><span class="sxs-lookup"><span data-stu-id="80651-120">Click **OK** or **Apply** to change the setting.</span></span>

## <span data-ttu-id="80651-121">相關主題</span><span class="sxs-lookup"><span data-stu-id="80651-121">Related topics</span></span>


[<span data-ttu-id="80651-122">如何在 Application Virtualization Client 管理主控台中設定用戶端</span><span class="sxs-lookup"><span data-stu-id="80651-122">How to Configure the Client in the Application Virtualization Client Management Console</span></span>](how-to-configure-the-client-in-the-application-virtualization-client-management-console.md)

[<span data-ttu-id="80651-123">Application Virtualization Client 中的使用者存取權限</span><span class="sxs-lookup"><span data-stu-id="80651-123">User Access Permissions in Application Virtualization Client</span></span>](user-access-permissions-in-application-virtualization-client.md)

 

 





