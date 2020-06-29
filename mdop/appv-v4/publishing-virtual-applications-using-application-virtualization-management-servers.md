---
title: 使用 Application Virtualization Management Server 發佈虛擬應用程式
description: 使用 Application Virtualization Management Server 發佈虛擬應用程式
author: dansimp
ms.assetid: f3d79284-3f82-4ca3-b741-1a80b61490da
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 01b85d73ed0a6a8bf723be381e947fbbc003bf6d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800885"
---
# <span data-ttu-id="e1d67-103">使用 Application Virtualization Management Server 發佈虛擬應用程式</span><span class="sxs-lookup"><span data-stu-id="e1d67-103">Publishing Virtual Applications Using Application Virtualization Management Servers</span></span>


<span data-ttu-id="e1d67-104">在應用程式虛擬化伺服器的部署中，已排序、經過測試且找到可部署的虛擬應用程式套件會複製到應用程式虛擬化管理伺服器所要使用的主要內容共用。</span><span class="sxs-lookup"><span data-stu-id="e1d67-104">In an Application Virtualization Server-based deployment, virtual application packages that have been sequenced, tested, and found deployable are copied to the main CONTENT share to be used by the Application Virtualization Management Server.</span></span> <span data-ttu-id="e1d67-105">將套件匯入應用程式虛擬化管理伺服器之後，就可以將它們發佈給最終使用者。</span><span class="sxs-lookup"><span data-stu-id="e1d67-105">After the packages are imported on the Application Virtualization Management Server, they can be published to the end users.</span></span>

<span data-ttu-id="e1d67-106">**記事** 內容共用應該位於伺服器的已附加磁片儲存空間。</span><span class="sxs-lookup"><span data-stu-id="e1d67-106">**Note** The CONTENT share should be located on the server’s attached disk storage.</span></span> <span data-ttu-id="e1d67-107">您應該謹慎考慮使用網路儲存裝置（例如 SAN 或 DFS 共用），因為這會影響網路。</span><span class="sxs-lookup"><span data-stu-id="e1d67-107">Using a network storage device such as a SAN or a DFS share should be considered carefully because of the network impact.</span></span>

 

<span data-ttu-id="e1d67-108">將應用程式預配至 Active Directory 群組。</span><span class="sxs-lookup"><span data-stu-id="e1d67-108">Applications are provisioned to Active Directory groups.</span></span> <span data-ttu-id="e1d67-109">通常，應用程式虛擬化管理員會針對每個要發佈的虛擬應用程式建立 Active Directory 群組，然後將適當的使用者新增到這些群組。</span><span class="sxs-lookup"><span data-stu-id="e1d67-109">Typically, the Application Virtualization administrator will create Active Directory groups for each virtual application to be published and then add the appropriate users to those groups.</span></span> <span data-ttu-id="e1d67-110">當使用者登入其工作站時，應用程式虛擬化用戶端預設會使用已登入使用者的認證執行發佈重新整理。</span><span class="sxs-lookup"><span data-stu-id="e1d67-110">When the users log on to their workstations, the Application Virtualization Client, by default, performs a publishing refresh using the credentials of the logged on user.</span></span> <span data-ttu-id="e1d67-111">然後，使用者就可以從放置快速鍵的任何地方開始應用程式。</span><span class="sxs-lookup"><span data-stu-id="e1d67-111">The user can then start applications from wherever the shortcuts have been placed.</span></span> <span data-ttu-id="e1d67-112">應用程式虛擬化管理員會在應用程式排序期間判斷用戶端系統上的快速鍵位置和數目。</span><span class="sxs-lookup"><span data-stu-id="e1d67-112">The Application Virtualization administrator determines where and how many shortcuts are located on the client system during the sequencing of the application.</span></span>

<span data-ttu-id="e1d67-113">**記事** *發佈*重新整理是在應用程式虛擬化用戶端上定義之應用程式虛擬化伺服器的呼叫，以判斷要傳送給客戶供最終使用者使用的虛擬應用程式快捷方式。</span><span class="sxs-lookup"><span data-stu-id="e1d67-113">**Note** A *publishing refresh* is a call to the Application Virtualization Server that is defined on the Application Virtualization Client, to determine which virtual application shortcuts are sent to the client for use by the end user.</span></span>

 

## <span data-ttu-id="e1d67-114">相關主題</span><span class="sxs-lookup"><span data-stu-id="e1d67-114">Related topics</span></span>


[<span data-ttu-id="e1d67-115">以 Application Virtualization 伺服器為基礎的案例</span><span class="sxs-lookup"><span data-stu-id="e1d67-115">Application Virtualization Server-Based Scenario</span></span>](application-virtualization-server-based-scenario.md)

[<span data-ttu-id="e1d67-116">如何在用戶端上發佈虛擬應用程式</span><span class="sxs-lookup"><span data-stu-id="e1d67-116">How to Publish a Virtual Application on the Client</span></span>](how-to-publish-a-virtual-application-on-the-client.md)

[<span data-ttu-id="e1d67-117">Application Virtualization 系統元件概觀</span><span class="sxs-lookup"><span data-stu-id="e1d67-117">Overview of the Application Virtualization System Components</span></span>](overview-of-the-application-virtualization-system-components.md)

[<span data-ttu-id="e1d67-118">在以 Application Virtualization 伺服器為基礎的實作中規劃您的串流解決方案</span><span class="sxs-lookup"><span data-stu-id="e1d67-118">Planning Your Streaming Solution in an Application Virtualization Server-Based Implementation</span></span>](planning-your-streaming-solution-in-an-application-virtualization-server-based-implementation.md)

 

 





