---
title: 如何設定在登入時重新整理發佈
description: 如何設定在登入時重新整理發佈
author: dansimp
ms.assetid: 196448db-7645-4fd5-a854-ef6405b15db4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: dd131ab5acbb8224e60077dfcc4272d4aa132b5e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801065"
---
# <span data-ttu-id="fb1e6-103">如何設定在登入時重新整理發佈</span><span class="sxs-lookup"><span data-stu-id="fb1e6-103">How to Set Up Publishing Refresh on Login</span></span>


<span data-ttu-id="fb1e6-104">您可以使用下列程式設定應用程式虛擬化（App-v）用戶端，在您每次登入電腦時，重新整理伺服器的發佈資訊。</span><span class="sxs-lookup"><span data-stu-id="fb1e6-104">You can use the following procedure to configure the Application Virtualization (App-V) Client to refresh the publishing information from the server each time you log in to the computer.</span></span> <span data-ttu-id="fb1e6-105">用戶端設定之後，就會自動重新整理作業。</span><span class="sxs-lookup"><span data-stu-id="fb1e6-105">After the client is configured, the refresh operation is automatic.</span></span>

**<span data-ttu-id="fb1e6-106">若要重新整理登入的發佈資訊</span><span class="sxs-lookup"><span data-stu-id="fb1e6-106">To refresh the publishing information on login</span></span>**

1.  <span data-ttu-id="fb1e6-107">按一下 [**範圍**] 窗格中的 [**發佈伺服器**]。</span><span class="sxs-lookup"><span data-stu-id="fb1e6-107">Click **Publishing Servers** in the **Scope** pane.</span></span>

2.  <span data-ttu-id="fb1e6-108">在 [**結果**] 窗格中，以滑鼠右鍵按一下所需的伺服器，然後從快顯功能表中選取 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="fb1e6-108">In the **Results** pane, right-click the desired server and select **Properties** from the pop-up-menu.</span></span>

3.  <span data-ttu-id="fb1e6-109">在 [**屬性**] 對話方塊中的 [重新整理] 索引標籤上，選取 [**在使用者登**入時重新整理 configuration server **] 複選**框。</span><span class="sxs-lookup"><span data-stu-id="fb1e6-109">In the **Properties** dialog box, on the **Refresh** tab, select the **Refresh configuration server on user login** check box.</span></span>

4.  <span data-ttu-id="fb1e6-110">按一下 **[** 套用] 以變更配置。</span><span class="sxs-lookup"><span data-stu-id="fb1e6-110">Click **Apply** to change the configuration.</span></span>

5.  <span data-ttu-id="fb1e6-111">設定完成後，請按一下 **[確定**] 結束對話方塊，然後返回應用程式虛擬化管理主控台。</span><span class="sxs-lookup"><span data-stu-id="fb1e6-111">When you finish configuring the settings, click **OK** to exit the dialog box and return to the Application Virtualization Management Console.</span></span>

    <span data-ttu-id="fb1e6-112">發佈資訊將會在您每次登入系統時重新整理。</span><span class="sxs-lookup"><span data-stu-id="fb1e6-112">The publishing information will now be refreshed each time you log in to the system.</span></span>

## <span data-ttu-id="fb1e6-113">相關主題</span><span class="sxs-lookup"><span data-stu-id="fb1e6-113">Related topics</span></span>


[<span data-ttu-id="fb1e6-114">如何在 Application Virtualization Client 管理主控台中設定用戶端</span><span class="sxs-lookup"><span data-stu-id="fb1e6-114">How to Configure the Client in the Application Virtualization Client Management Console</span></span>](how-to-configure-the-client-in-the-application-virtualization-client-management-console.md)

 

 





