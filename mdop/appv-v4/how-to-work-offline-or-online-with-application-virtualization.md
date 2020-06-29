---
title: 如何以 Application Virtualization 離線或線上工作
description: 如何以 Application Virtualization 離線或線上工作
author: dansimp
ms.assetid: aa532b37-8a00-4db4-9b51-e1e8354b2495
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0dfdd315fe607156135247c4a34d0248ef8fbdd9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801007"
---
# <span data-ttu-id="f60b8-103">如何以 Application Virtualization 離線或線上工作</span><span class="sxs-lookup"><span data-stu-id="f60b8-103">How to Work Offline or Online with Application Virtualization</span></span>


<span data-ttu-id="f60b8-104">如果您計畫在較長的時間內中斷網路連線，您可以在離線模式下工作，以避免應用程式虛擬化用戶端嘗試與伺服器通訊時可能發生的延遲。</span><span class="sxs-lookup"><span data-stu-id="f60b8-104">If you plan to be disconnected from the network for an extended period of time, you can work in offline mode to eliminate possible delays when the Application Virtualization client attempts to communicate with the server.</span></span> <span data-ttu-id="f60b8-105">在離線模式中，應用程式虛擬化用戶端不會嘗試與發佈伺服器進行通訊，因此應用程式必須完全快取，才能啟用離線模式。</span><span class="sxs-lookup"><span data-stu-id="f60b8-105">In offline mode, the Application Virtualization client will not attempt to communicate with the publishing server, so applications must be fully cached before enabling offline mode.</span></span> <span data-ttu-id="f60b8-106">即使是在電腦上的本機磁片上，也不會從內容共用中檢索應用程式。</span><span class="sxs-lookup"><span data-stu-id="f60b8-106">Applications will not be retrieved from the content share even if they are on the local disk on the computer.</span></span> <span data-ttu-id="f60b8-107">您可以使用下列 Application Virtualization 用戶端程式，在離線和線上工作之間切換。</span><span class="sxs-lookup"><span data-stu-id="f60b8-107">You can use the following Application Virtualization Client procedure to toggle between working offline and online.</span></span>

<span data-ttu-id="f60b8-108">**記事** 根據預設，遠端桌面服務的用戶端會停用**離線工作**（以前稱為 [終端服務]）。</span><span class="sxs-lookup"><span data-stu-id="f60b8-108">**Note** By default, **Work Offline** is disabled for the Client for Remote Desktop Services (formerly Terminal Services).</span></span> <span data-ttu-id="f60b8-109">您的系統管理員必須變更您的使用者許可權，才能允許您在用戶端上使用遠端桌面服務的此設定。</span><span class="sxs-lookup"><span data-stu-id="f60b8-109">Your system administrator must change your user permissions to allow you to use this setting on a Client for Remote Desktop Services.</span></span>

 

**<span data-ttu-id="f60b8-110">離線工作</span><span class="sxs-lookup"><span data-stu-id="f60b8-110">To work offline</span></span>**

-   <span data-ttu-id="f60b8-111">以滑鼠右鍵按一下通知區域中的 [應用程式虛擬化系統] 圖示，然後從快顯功能表中選取 [**離線工作**]。</span><span class="sxs-lookup"><span data-stu-id="f60b8-111">Right-click the Application Virtualization System icon in the notification area, and select **Work Offline** from the pop-up menu.</span></span>

**<span data-ttu-id="f60b8-112">若要線上工作</span><span class="sxs-lookup"><span data-stu-id="f60b8-112">To work online</span></span>**

-   <span data-ttu-id="f60b8-113">以滑鼠右鍵按一下通知區域中的 [應用程式虛擬化系統] 圖示，然後從快顯功能表中選取 [**線上工作**]。</span><span class="sxs-lookup"><span data-stu-id="f60b8-113">Right-click the Application Virtualization System icon in the notification area, and select **Work Online** from the pop-up menu.</span></span>

## <span data-ttu-id="f60b8-114">相關主題</span><span class="sxs-lookup"><span data-stu-id="f60b8-114">Related topics</span></span>


[<span data-ttu-id="f60b8-115">如何使用 Application Virtualization Client Management 的桌面通知區域</span><span class="sxs-lookup"><span data-stu-id="f60b8-115">How to Use the Desktop Notification Area for Application Virtualization Client Management</span></span>](how-to-use-the-desktop-notification-area-for-application-virtualization-client-management.md)

 

 





