---
title: 設定 AGPM 伺服器連線
description: 設定 AGPM 伺服器連線
author: dansimp
ms.assetid: 409cbbcf-3b0e-459d-9bd2-75cb7b9430b0
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d7fdc26045b478da14957cdfe6000d58ab72a064
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802074"
---
# <span data-ttu-id="89d71-103">設定 AGPM 伺服器連線</span><span class="sxs-lookup"><span data-stu-id="89d71-103">Configure an AGPM Server Connection</span></span>


<span data-ttu-id="89d71-104">若要確保您已連線至正確的中央封存，請查看 AGPM 服務器連線的設定。</span><span class="sxs-lookup"><span data-stu-id="89d71-104">To ensure that you are connected to the correct central archive, review the configuration of the AGPM Server connection.</span></span> <span data-ttu-id="89d71-105">如果 AGPM 系統管理員（完全控制）尚未為您設定 AGPM 服務器連線，則您必須手動設定。</span><span class="sxs-lookup"><span data-stu-id="89d71-105">If an AGPM Administrator (Full Control) has not configured an AGPM Server connection for you, then you must manually configure it.</span></span>

**<span data-ttu-id="89d71-106">選取 AGPM 服務器</span><span class="sxs-lookup"><span data-stu-id="89d71-106">To select an AGPM Server</span></span>**

1.  <span data-ttu-id="89d71-107">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="89d71-107">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="89d71-108">在 [詳細資料] 窗格中，按一下 [ **AGPM 服務器**] 索引標籤：</span><span class="sxs-lookup"><span data-stu-id="89d71-108">In the details pane, click the **AGPM Server** tab:</span></span>

    -   <span data-ttu-id="89d71-109">如果 [ **Agpm 伺服器**] 索引標籤上的選項無法使用，就是由 AGPM 系統管理員集中設定。</span><span class="sxs-lookup"><span data-stu-id="89d71-109">If the options on the **AGPM Server** tab are unavailable, they have been centrally configured by an AGPM Administrator.</span></span>

    -   <span data-ttu-id="89d71-110">如果 [ **Agpm server** ] 索引標籤上有可用的選項，請為 agpm 伺服器（例如 server.contoso.com）和 agpm 服務偵聽的埠（預設為埠4600）輸入完整的電腦名稱稱。</span><span class="sxs-lookup"><span data-stu-id="89d71-110">If the options on the **AGPM Server** tab are available, type the fully-qualified computer name for the AGPM Server (for example, server.contoso.com) and the port on which the AGPM Service listens (by default, port 4600).</span></span> <span data-ttu-id="89d71-111">按一下 [套用] **，然後按一下** **[是]** 以確認。</span><span class="sxs-lookup"><span data-stu-id="89d71-111">Click **Apply**, then click **Yes** to confirm.</span></span>

### <span data-ttu-id="89d71-112">其他考量</span><span class="sxs-lookup"><span data-stu-id="89d71-112">Additional considerations</span></span>

-   <span data-ttu-id="89d71-113">已選取的 AGPM 服務器會決定要顯示在 [**目錄**] 索引標籤上的 gpo，以及 [**網域委派**] 索引標籤設定的套用位置。</span><span class="sxs-lookup"><span data-stu-id="89d71-113">The AGPM Servers selected determine which GPOs are displayed on the **Contents** tab and to what location the **Domain Delegation** tab settings are applied.</span></span> <span data-ttu-id="89d71-114">如果不是透過管理範本來集中管理，每個群組原則管理員都必須設定此設定，以指向網域的 AGPM 服務器。</span><span class="sxs-lookup"><span data-stu-id="89d71-114">If not centrally managed through the Administrative template, each Group Policy administrator must configure this setting to point to the AGPM Server for the domain.</span></span>

### <span data-ttu-id="89d71-115">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="89d71-115">Additional references</span></span>

-   [<span data-ttu-id="89d71-116">執行檢閱者工作</span><span class="sxs-lookup"><span data-stu-id="89d71-116">Performing Reviewer Tasks</span></span>](performing-reviewer-tasks-agpm40.md)

 

 





