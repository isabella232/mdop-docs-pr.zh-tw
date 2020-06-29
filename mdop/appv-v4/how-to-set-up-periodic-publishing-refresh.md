---
title: 如何設定定期重新整理發佈
description: 如何設定定期重新整理發佈
author: dansimp
ms.assetid: c358c765-cb88-4881-b4e7-0a2e87304870
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a5bbea1c661d6cb5a78f0bb9de29538e0222cda6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801062"
---
# <span data-ttu-id="1944a-103">如何設定定期重新整理發佈</span><span class="sxs-lookup"><span data-stu-id="1944a-103">How to Set Up Periodic Publishing Refresh</span></span>


<span data-ttu-id="1944a-104">您可以使用下列程式來設定用戶端定期重新整理 App-v 伺服器的發佈資訊。</span><span class="sxs-lookup"><span data-stu-id="1944a-104">You can use the following procedure to configure the client to periodically refresh the publishing information from the App-V servers.</span></span> <span data-ttu-id="1944a-105">用戶端設定之後，就會自動重新整理作業。</span><span class="sxs-lookup"><span data-stu-id="1944a-105">After the client is configured, the refresh operation is automatic.</span></span> <span data-ttu-id="1944a-106">這些設定會設定用戶端的預設設定，讓此電腦上的所有使用者都能看到相同的設定。</span><span class="sxs-lookup"><span data-stu-id="1944a-106">These settings configure the default settings for the client so that all users on this computer will see the same settings.</span></span>

<span data-ttu-id="1944a-107">**記事** 在您執行此程式後，在登入後第一次重新整理之後，會根據新的設定來更新發佈資訊。</span><span class="sxs-lookup"><span data-stu-id="1944a-107">**Note** After you have performed this procedure, the publishing information will be refreshed according to the new settings after the first refresh at login.</span></span> <span data-ttu-id="1944a-108">第一次重新整理髮生時，伺服器可能會根據設定的設定，覆寫電腦設定。</span><span class="sxs-lookup"><span data-stu-id="1944a-108">When this first refresh occurs, the server might override the computer settings with different settings, depending on how it is configured.</span></span> <span data-ttu-id="1944a-109">[**屬性**] 對話方塊中的 [重新**整理] 索引**標籤會顯示本機設定的用戶端電腦設定，以及任何可能已由發佈伺服器為使用者設定的設定。</span><span class="sxs-lookup"><span data-stu-id="1944a-109">The **Refresh** tab in the **Properties** dialog box shows the locally configured client computer settings and any settings that might have been configured for the user by the publishing server.</span></span>

 

**<span data-ttu-id="1944a-110">若要定期重新整理應用程式虛擬化伺服器的發佈資訊</span><span class="sxs-lookup"><span data-stu-id="1944a-110">To periodically refresh the publishing information from the Application Virtualization Servers</span></span>**

1.  <span data-ttu-id="1944a-111">按一下 [**範圍**] 窗格中的 [**發佈伺服器**]。</span><span class="sxs-lookup"><span data-stu-id="1944a-111">Click **Publishing Servers** in the **Scope** pane.</span></span>

2.  <span data-ttu-id="1944a-112">在 [**結果**] 窗格中，以滑鼠右鍵按一下所需的伺服器，然後從快顯功能表中選取 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="1944a-112">In the **Results** pane, right-click the desired server and select **Properties** from the pop-up-menu.</span></span>

3.  <span data-ttu-id="1944a-113">在 [內容 **] 對話方塊中的 [** 重新**整理] 索引**標籤上，選取 [**每隔**] 核取方塊的 [重新整理設定]，然後在欄位中輸入代表頻率的數位。</span><span class="sxs-lookup"><span data-stu-id="1944a-113">In the **Properties** dialog box, on the **Refresh** tab, select the **Refresh configuration every** check box and enter a number that represents the frequency in the field.</span></span> <span data-ttu-id="1944a-114">然後從下拉式功能表中選取 [**分鐘**]、[**小時**]、[**天**]。</span><span class="sxs-lookup"><span data-stu-id="1944a-114">Then select **Minutes**, **Hours**, **Days** from the drop-down menu.</span></span>

    <span data-ttu-id="1944a-115">**記事** 此設定將會導致用戶端在每次經過設定的期間時重新整理髮布資訊。</span><span class="sxs-lookup"><span data-stu-id="1944a-115">**Note** This setting will cause the client to refresh publishing information every time the configured period elapses.</span></span> <span data-ttu-id="1944a-116">如果您需要重新整理的使用者沒有登入，則當使用者下一次登入時，就會進行重新整理。</span><span class="sxs-lookup"><span data-stu-id="1944a-116">If the user is not logged in when it's time to do a refresh, the refresh will take place when the user next logs in.</span></span> <span data-ttu-id="1944a-117">接著，隨後就會再次啟動該計時器。</span><span class="sxs-lookup"><span data-stu-id="1944a-117">The timer is then started again for the next period.</span></span>

     

4.  <span data-ttu-id="1944a-118">按一下 **[** 套用] 以變更配置。</span><span class="sxs-lookup"><span data-stu-id="1944a-118">Click **Apply** to change the configuration.</span></span>

5.  <span data-ttu-id="1944a-119">完成伺服器的設定後，請按一下 **[確定**] 結束對話方塊，然後返回應用程式虛擬化用戶端管理主控台。</span><span class="sxs-lookup"><span data-stu-id="1944a-119">When you finish configuring the server, click **OK** to exit the dialog box and return to the Application Virtualization Client Management Console.</span></span>

## <span data-ttu-id="1944a-120">相關主題</span><span class="sxs-lookup"><span data-stu-id="1944a-120">Related topics</span></span>


[<span data-ttu-id="1944a-121">如何在 Application Virtualization Client 管理主控台中設定用戶端</span><span class="sxs-lookup"><span data-stu-id="1944a-121">How to Configure the Client in the Application Virtualization Client Management Console</span></span>](how-to-configure-the-client-in-the-application-virtualization-client-management-console.md)

 

 





