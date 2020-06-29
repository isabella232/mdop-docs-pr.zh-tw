---
title: 中斷連線的操作模式
description: 中斷連線的操作模式
author: dansimp
ms.assetid: 3f9849ea-ba53-4c68-85d3-87a4218f59c6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6e9534b93f23b17e5258ef5e2d548eb93213f2f8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808865"
---
# <span data-ttu-id="5c29c-103">中斷連線的操作模式</span><span class="sxs-lookup"><span data-stu-id="5c29c-103">Disconnected Operation Mode</span></span>


<span data-ttu-id="5c29c-104">中斷式作業模式設定（由滑鼠右鍵按一下**應用程式虛擬化**節點、選取 [**屬性**]，然後按一下 [**連接**] 索引標籤），可讓遠端桌面服務的應用程式虛擬化桌面用戶端或用戶端在用戶端無法連線到應用程式虛擬化管理伺服器時，執行儲存在用戶端檔案系統快取中的應用程式。</span><span class="sxs-lookup"><span data-stu-id="5c29c-104">The disconnected operation mode settings—accessible by right-clicking the **Application Virtualization** node, selecting **Properties**, and clicking the **Connectivity** tab—enables the Application Virtualization Desktop Client or Client for Remote Desktop Services (formerly Terminal Services) to run applications that are stored in the file system cache of the client when the client is unable to connect to the Application Virtualization Management Server.</span></span>

<span data-ttu-id="5c29c-105">無法連線至伺服器的原因包括伺服器故障、網路中斷或從網路斷開連線。</span><span class="sxs-lookup"><span data-stu-id="5c29c-105">Reasons for failure to connect to the server include server failure, network outage, or disconnection from the network.</span></span> <span data-ttu-id="5c29c-106">如果發生任何失敗，用戶端會自動切換到 [中斷連線] 的操作。</span><span class="sxs-lookup"><span data-stu-id="5c29c-106">If any failure occurs, the client will automatically switch to disconnected operation.</span></span> <span data-ttu-id="5c29c-107">中斷連線後，如果用戶端需要來自伺服器的其他資料來繼續執行應用程式，或斷開連接的作業超時時間已過期，用戶端會嘗試重新連線到伺服器。</span><span class="sxs-lookup"><span data-stu-id="5c29c-107">After it is disconnected, if the client needs additional data from the server to continue to run an application or if the disconnected operation time-out expires, the client will attempt to reconnect to the server.</span></span> <span data-ttu-id="5c29c-108">如果此連接嘗試失敗，應用程式將會關閉。</span><span class="sxs-lookup"><span data-stu-id="5c29c-108">If this connection attempt fails, the application will be shut down.</span></span>

<span data-ttu-id="5c29c-109">根據預設，會啟用中斷連線的作業，而超時會設定為90天。</span><span class="sxs-lookup"><span data-stu-id="5c29c-109">By default, disconnected operation is enabled and the time-out is set to 90 days.</span></span> <span data-ttu-id="5c29c-110">超時值是指定為您要限制斷開連接操作模式的天數，您可以輸入1到999之間的值。</span><span class="sxs-lookup"><span data-stu-id="5c29c-110">The time-out value is specified as the number of days you want to limit disconnected operation mode, and you can enter a value from 1–999.</span></span>

## <span data-ttu-id="5c29c-111">相關主題</span><span class="sxs-lookup"><span data-stu-id="5c29c-111">Related topics</span></span>


[<span data-ttu-id="5c29c-112">如何停用或修改中斷連線的操作模式設定</span><span class="sxs-lookup"><span data-stu-id="5c29c-112">How to Disable or Modify Disconnected Operation Mode Settings</span></span>](how-to-disable-or-modify-disconnected-operation-mode-settings.md)

 

 





