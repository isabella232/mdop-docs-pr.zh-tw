---
title: 加入網域及未加入網域的用戶端
description: 加入網域及未加入網域的用戶端
author: dansimp
ms.assetid: a935dc98-de60-45f3-ab74-2444ce082e88
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: c4385ab3f26bb867dd649fe768e1500c9d015ffa
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10808871"
---
# <span data-ttu-id="67c24-103">加入網域及未加入網域的用戶端</span><span class="sxs-lookup"><span data-stu-id="67c24-103">Domain-Joined and Non-Domain-Joined Clients</span></span>


<span data-ttu-id="67c24-104">App-v Desktop 用戶端可以設定為允許連線至網路，不論用戶端是否已加入網域或未加入網域。</span><span class="sxs-lookup"><span data-stu-id="67c24-104">The App-V Desktop Client can be configured to allow connection to a network regardless of whether the client is domain joined or non-domain joined.</span></span>

## <span data-ttu-id="67c24-105">加入網域的用戶端</span><span class="sxs-lookup"><span data-stu-id="67c24-105">Domain-Joined Clients</span></span>


<span data-ttu-id="67c24-106">已加入網域但內部網路以外的用戶端可以使用 VPN 連線與 App-v 基礎結構進行通訊。</span><span class="sxs-lookup"><span data-stu-id="67c24-106">Clients that are domain joined, but outside the internal network, can communicate with the App-V infrastructure by using a VPN connection.</span></span> <span data-ttu-id="67c24-107">當您想要讓使用者能夠離開內部網路，但仍在 App-v 基礎結構中進行通訊時，您的環境需要極少的設定。</span><span class="sxs-lookup"><span data-stu-id="67c24-107">When you want to provide users the ability to leave the internal network but still communicate in an App-V infrastructure, your environment requires very little setup.</span></span> <span data-ttu-id="67c24-108">因為使用者已是網域的一部分，所以您只需要確保用戶端支援緩存的認證。</span><span class="sxs-lookup"><span data-stu-id="67c24-108">Because the users are already part of the domain, you simply need to ensure that Cached Credentials are supported on the client.</span></span> <span data-ttu-id="67c24-109">這是預設設定，此設定的任何變更都可以從群群組原則完成。</span><span class="sxs-lookup"><span data-stu-id="67c24-109">This is the default configuration, and any changes to this setting can be accomplished from Group Policies.</span></span>

<span data-ttu-id="67c24-110">如在 App-V 安全性最佳做法指南中所述，使用者將會嘗試將其使用者票證傳送給 App-v 基礎結構以進行驗證。</span><span class="sxs-lookup"><span data-stu-id="67c24-110">As mentioned in the App-V Security Best Practices Guide, the user will attempt to send their user ticket to the App-V infrastructure for authentication.</span></span> <span data-ttu-id="67c24-111">如果票證已過期，系統會將它還原為使用 NTLM 和電腦上的快取認證。</span><span class="sxs-lookup"><span data-stu-id="67c24-111">If the ticket is expired, it will revert to using NTLM and the cached credentials on the computer.</span></span> <span data-ttu-id="67c24-112">若要允許漫遊，系統管理員必須確保內部存取的發佈伺服器與外部的名稱可正常解決。</span><span class="sxs-lookup"><span data-stu-id="67c24-112">To allow roaming, administrators must ensure that the publishing server being accessed internally is available at the same name externally for the names to resolve properly.</span></span>

## <span data-ttu-id="67c24-113">非網域加入的用戶端</span><span class="sxs-lookup"><span data-stu-id="67c24-113">Non-Domain-Joined Clients</span></span>


<span data-ttu-id="67c24-114">未加入網域但需要在 App-v 基礎結構中進行通訊的用戶端，必須設定為確保 App-v 基礎結構的驗證成功。</span><span class="sxs-lookup"><span data-stu-id="67c24-114">Clients that are non-domain joined but need to communicate in the App-V infrastructure must be configured to ensure that authentication to the App-V infrastructure is successful.</span></span> <span data-ttu-id="67c24-115">App-v Desktop 用戶端不允許提示發佈重新整理程式，因此必須將用戶端設定為向 App-v 管理伺服器提供適當的認證。</span><span class="sxs-lookup"><span data-stu-id="67c24-115">The App-V Desktop Client does not permit prompting for the publishing refresh process, so the client must be configured to present the proper credentials to the App-V Management Server.</span></span>

<span data-ttu-id="67c24-116">發佈伺服器是針對從非網域加入用戶端發佈重新整理而設定的，需要在發佈伺服器憑證上將用戶端存取的外部名稱設定為公用名或 subject 替代名稱（SAN）。</span><span class="sxs-lookup"><span data-stu-id="67c24-116">The publishing server, which is configured for publishing refresh from the non-domain joined client, requires that the external name that clients access is configured as the common name or a subject alternate name (SAN) on the publishing server’s certificate.</span></span>

## <span data-ttu-id="67c24-117">相關主題</span><span class="sxs-lookup"><span data-stu-id="67c24-117">Related topics</span></span>


[<span data-ttu-id="67c24-118">如何為 Windows Vista 指派適當的認證</span><span class="sxs-lookup"><span data-stu-id="67c24-118">How to Assign the Proper Credentials for Windows Vista</span></span>](how-to-assign--the-proper-credentials-for-windows-vista.md)

[<span data-ttu-id="67c24-119">如何為 Windows XP 指派適當的認證</span><span class="sxs-lookup"><span data-stu-id="67c24-119">How to Assign the Proper Credentials for Windows XP</span></span>](how-to-assign--the-proper-credentials-for-windows-xp.md)

 

 





