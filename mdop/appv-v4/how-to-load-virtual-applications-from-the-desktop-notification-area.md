---
title: 如何從桌面通知區域載入虛擬應用程式
description: 如何從桌面通知區域載入虛擬應用程式
author: dansimp
ms.assetid: f52758eb-8b81-4b3c-9bc3-adcf7c00c238
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d7004f9e0031dfeeedc8b6a916e2f3488f1d31e1
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801329"
---
# <span data-ttu-id="b5594-103">如何從桌面通知區域載入虛擬應用程式</span><span class="sxs-lookup"><span data-stu-id="b5594-103">How to Load Virtual Applications from the Desktop Notification Area</span></span>


<span data-ttu-id="b5594-104">如果您是行動使用者，您可能會想要將您的應用程式完全載入在快取中，以便在斷開式作業或離線模式時使用。</span><span class="sxs-lookup"><span data-stu-id="b5594-104">If you are a mobile user, you might want to fully load your applications in the cache to use them during disconnected operation or offline mode.</span></span> <span data-ttu-id="b5594-105">若要從應用程式虛擬化（App-v）伺服器或應用程式虛擬化（app-v）流式處理伺服器傳送應用程式，您必須連線到伺服器才能載入應用程式。</span><span class="sxs-lookup"><span data-stu-id="b5594-105">To stream applications from the Application Virtualization (App-V) Server or the Application Virtualization (App-V) Streaming Server, you must be connected to a server to load applications.</span></span> <span data-ttu-id="b5594-106">如果您在嘗試載入應用程式時未連線至伺服器，系統會產生適當的錯誤訊息。</span><span class="sxs-lookup"><span data-stu-id="b5594-106">If you are not connected to the server when you attempt to load applications, your system will generate an appropriate error message.</span></span> <span data-ttu-id="b5594-107">您也可以從檔案或磁片將應用程式資料流到用戶端。</span><span class="sxs-lookup"><span data-stu-id="b5594-107">You can also stream applications to the client from a file or disk.</span></span>

<span data-ttu-id="b5594-108">應用程式一次會載入一個應用程式。</span><span class="sxs-lookup"><span data-stu-id="b5594-108">The applications are loaded one application at a time.</span></span> <span data-ttu-id="b5594-109">[進度列] 會顯示您的應用程式名稱、已載入的應用程式百分比，以及與已排入佇列之應用程式總數相比已處理的應用程式數量。</span><span class="sxs-lookup"><span data-stu-id="b5594-109">The progress bar shows you the application name, the percentage of application loaded, and the number of applications already processed compared to the total number of the applications queued.</span></span> <span data-ttu-id="b5594-110">您可以略過正在進行的任何應用程式，然後再載入100%。</span><span class="sxs-lookup"><span data-stu-id="b5594-110">You can skip any application in progress before it is 100% loaded.</span></span> <span data-ttu-id="b5594-111">您也可以略過載入所有剩餘的應用程式。</span><span class="sxs-lookup"><span data-stu-id="b5594-111">You can skip the loading of all remaining applications as well.</span></span>

<span data-ttu-id="b5594-112">**記事** 如果您的系統在載入應用程式時遇到錯誤，它會向您報告錯誤。</span><span class="sxs-lookup"><span data-stu-id="b5594-112">**Note** If your system encounters an error while loading an application, it reports the error to you.</span></span> <span data-ttu-id="b5594-113">您必須先關閉錯誤對話方塊，才能載入下一個應用程式。</span><span class="sxs-lookup"><span data-stu-id="b5594-113">You must dismiss the error dialog before it will load the next application.</span></span>

 

**<span data-ttu-id="b5594-114">載入所有應用程式</span><span class="sxs-lookup"><span data-stu-id="b5594-114">To load all applications</span></span>**

1.  <span data-ttu-id="b5594-115">以滑鼠右鍵按一下通知區域中的 [應用程式虛擬化系統] 圖示。</span><span class="sxs-lookup"><span data-stu-id="b5594-115">Right-click the Application Virtualization System icon in the notification area.</span></span>

2.  <span data-ttu-id="b5594-116">從快顯功能表中選取 [**載入應用程式**]。</span><span class="sxs-lookup"><span data-stu-id="b5594-116">Select **Load Applications** from the pop-up menu.</span></span>

**<span data-ttu-id="b5594-117">略過應用程式</span><span class="sxs-lookup"><span data-stu-id="b5594-117">To skip applications</span></span>**

1.  <span data-ttu-id="b5594-118">按一下進度列以顯示對話方塊。</span><span class="sxs-lookup"><span data-stu-id="b5594-118">Click the progress bar to display the dialog box.</span></span>

2.  <span data-ttu-id="b5594-119">選取下列其中一個按鈕以取得預期的結果：</span><span class="sxs-lookup"><span data-stu-id="b5594-119">Select one of the following buttons to achieve the desired results:</span></span>

    1.  <span data-ttu-id="b5594-120">[**略過**]：略過目前載入的應用程式。</span><span class="sxs-lookup"><span data-stu-id="b5594-120">**Skip**—To skip the currently loading application.</span></span>

    2.  <span data-ttu-id="b5594-121">[**全部略過**]：略過所有剩餘的應用程式。</span><span class="sxs-lookup"><span data-stu-id="b5594-121">**Skip All**—To skip all remaining applications.</span></span>

    3.  <span data-ttu-id="b5594-122">[**繼續**]：取消對話方塊並繼續載入應用程式。</span><span class="sxs-lookup"><span data-stu-id="b5594-122">**Continue**—To cancel the dialog box and continue loading applications.</span></span>

## <span data-ttu-id="b5594-123">相關主題</span><span class="sxs-lookup"><span data-stu-id="b5594-123">Related topics</span></span>


[<span data-ttu-id="b5594-124">如何使用 Application Virtualization Client Management 的桌面通知區域</span><span class="sxs-lookup"><span data-stu-id="b5594-124">How to Use the Desktop Notification Area for Application Virtualization Client Management</span></span>](how-to-use-the-desktop-notification-area-for-application-virtualization-client-management.md)

 

 





