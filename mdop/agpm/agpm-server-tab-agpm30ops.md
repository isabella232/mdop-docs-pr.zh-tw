---
title: AGPM 伺服器索引標籤
description: AGPM 伺服器索引標籤
author: dansimp
ms.assetid: fb3b0265-53ed-4bf6-88a4-c409f5f1bed4
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 335cad07691f914884583636cef01be8dbaa0266
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802157"
---
# <span data-ttu-id="db176-103">AGPM 伺服器索引標籤</span><span class="sxs-lookup"><span data-stu-id="db176-103">AGPM Server Tab</span></span>


<span data-ttu-id="db176-104">[**變更控制**] 窗格上的 [ **AGPM 服務器**] 索引標籤可讓您透過輸入完整的電腦名稱稱和埠來選取 agpm 伺服器，以及從封存刪除較舊版本的群組原則物件（gpo），以節省 AGPM 服務器的磁碟空間。</span><span class="sxs-lookup"><span data-stu-id="db176-104">The **AGPM Server** tab on the **Change Control** pane enables you to select an AGPM Server by entering a fully-qualified computer name and port, and to delete older versions of Group Policy Objects (GPOs) from the archive to conserve disk space on the AGPM Server.</span></span>

## <span data-ttu-id="db176-105">指定 AGPM 服務器</span><span class="sxs-lookup"><span data-stu-id="db176-105">Specifying the AGPM Server</span></span>


<span data-ttu-id="db176-106">已選取的 AGPM 服務器決定要在 [**內容**] 索引標籤上顯示哪個封存，以及**將哪些**位置套用到哪個位置。</span><span class="sxs-lookup"><span data-stu-id="db176-106">The AGPM Server selected determines which archive is displayed for you on the **Contents** tab and to which location the **Domain Delegation** settings are applied.</span></span> <span data-ttu-id="db176-107">[高級群組原則管理（AGPM）] 的預設埠是埠4600。</span><span class="sxs-lookup"><span data-stu-id="db176-107">The default port for Advanced Group Policy Management (AGPM) is port 4600.</span></span>

<span data-ttu-id="db176-108">如果 AGPM 服務器連線是使用系統管理範本設定來集中設定，則此索引標籤上用於設定連線的選項將無法使用。</span><span class="sxs-lookup"><span data-stu-id="db176-108">If the AGPM Server connection is centrally configured using Administrative template settings, the options on this tab for configuring the connection are unavailable.</span></span> <span data-ttu-id="db176-109">如需詳細資訊，請參閱[設定 AGPM 服務器](configure-agpm-server-connections-agpm30ops.md)連線。</span><span class="sxs-lookup"><span data-stu-id="db176-109">For more information, see [Configure AGPM Server Connections](configure-agpm-server-connections-agpm30ops.md).</span></span>

## <span data-ttu-id="db176-110">刪除舊的 GPO 版本</span><span class="sxs-lookup"><span data-stu-id="db176-110">Deleting old GPO versions</span></span>


<span data-ttu-id="db176-111">根據預設，每個受控制的 GPO 的所有版本都會保留在封存中。</span><span class="sxs-lookup"><span data-stu-id="db176-111">By default, all versions of every controlled GPO are retained in the archive.</span></span> <span data-ttu-id="db176-112">不過，您可以設定 AGPM 服務來限制每個 GPO 保留的版本數，並在超過該限制時自動刪除最舊的版本。</span><span class="sxs-lookup"><span data-stu-id="db176-112">However, you can configure the AGPM Service to limit the number of versions retained for each GPO and automatically delete the oldest version when that limit is exceeded.</span></span> <span data-ttu-id="db176-113">只有 [歷程**記錄**] 視窗 [**唯一版本**] 索引標籤上顯示的 GPO 版本，才會計算出該限制。</span><span class="sxs-lookup"><span data-stu-id="db176-113">Only GPO versions displayed on the **Unique Versions** tab of the **History** window count toward the limit.</span></span>

<span data-ttu-id="db176-114">**記事** 要儲存于每個 GPO 的唯一版本數上限不包括目前的版本，因此輸入0只保留目前的版本。</span><span class="sxs-lookup"><span data-stu-id="db176-114">**Note** The maximum number of unique versions to store for each GPO does not include the current version, so entering 0 retains only the current version.</span></span> <span data-ttu-id="db176-115">限制必須不超過999版本。</span><span class="sxs-lookup"><span data-stu-id="db176-115">The limit must be no greater than 999 versions.</span></span>

<span data-ttu-id="db176-116">當 GPO 版本刪除時，該版本的記錄會保留在 GPO 的記錄中，但 GPO 版本本身已從封存中刪除。</span><span class="sxs-lookup"><span data-stu-id="db176-116">When a GPO version is deleted, a record of that version remains in the history of the GPO, but the GPO version itself is deleted from the archive.</span></span> <span data-ttu-id="db176-117">您可以在歷程記錄中將其標示為不可刪除，以避免刪除 GPO 版本。</span><span class="sxs-lookup"><span data-stu-id="db176-117">You can prevent a GPO version from being deleted by marking it in the history as not deletable.</span></span>

 

### <span data-ttu-id="db176-118">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="db176-118">Additional references</span></span>

-   [<span data-ttu-id="db176-119">使用者介面：進階群組原則管理</span><span class="sxs-lookup"><span data-stu-id="db176-119">User Interface: Advanced Group Policy Management</span></span>](user-interface-advanced-group-policy-management-agpm30ops.md)

-   [<span data-ttu-id="db176-120">執行 AGPM 系統管理員工作</span><span class="sxs-lookup"><span data-stu-id="db176-120">Performing AGPM Administrator Tasks</span></span>](performing-agpm-administrator-tasks-agpm30ops.md)

-   [<span data-ttu-id="db176-121">執行檢閱者工作</span><span class="sxs-lookup"><span data-stu-id="db176-121">Performing Reviewer Tasks</span></span>](performing-reviewer-tasks-agpm30ops.md)

 

 





