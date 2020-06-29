---
title: 限制儲存的 GPO 版本
description: 限制儲存的 GPO 版本
author: dansimp
ms.assetid: d802c7b6-f303-4b23-aefd-f19f1300b0ff
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: df6f6df2e2b1bae2cd972b67b76c27905622a723
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802689"
---
# <span data-ttu-id="c4301-103">限制儲存的 GPO 版本</span><span class="sxs-lookup"><span data-stu-id="c4301-103">Limit the GPO Versions Stored</span></span>


<span data-ttu-id="c4301-104">根據預設，所有受控制的群群組原則物件（GPO）版本都會保留在 AGPM 服務器上的封存中。</span><span class="sxs-lookup"><span data-stu-id="c4301-104">By default, all versions of every controlled Group Policy Object (GPO) are retained in the archive on the AGPM Server.</span></span> <span data-ttu-id="c4301-105">不過，您可以限制每個 GPO 保留的版本數，並在超過該限制時刪除較舊的版本。</span><span class="sxs-lookup"><span data-stu-id="c4301-105">However, you can limit the number of versions retained for each GPO and delete older versions when that limit is exceeded.</span></span> <span data-ttu-id="c4301-106">當 GPO 版本刪除時，版本的記錄會保留在 GPO 的記錄中，但 GPO 版本本身已從封存中刪除。</span><span class="sxs-lookup"><span data-stu-id="c4301-106">When GPO versions are deleted, a record of the version remains in the history of the GPO, but the GPO version itself is deleted from the archive.</span></span>

<span data-ttu-id="c4301-107">您必須具備高級群組原則管理（AGPM）中具有 AGPM 系統管理員（完全控制）角色或必要許可權的使用者帳戶，才能完成此程式。</span><span class="sxs-lookup"><span data-stu-id="c4301-107">A user account with the AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="c4301-108">請參閱本主題中的「其他注意事項」中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="c4301-108">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="c4301-109">限制儲存的 GPO 版本數</span><span class="sxs-lookup"><span data-stu-id="c4301-109">To limit the number of GPO versions stored</span></span>**

1.  <span data-ttu-id="c4301-110">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="c4301-110">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="c4301-111">在 [詳細資料] 窗格中，按一下 [ **AGPM 服務器**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="c4301-111">In the details pane, click the **AGPM Server** tab.</span></span>

3.  <span data-ttu-id="c4301-112">選取 [**從封存刪除每個 gpo 的舊版版本**] 核取方塊，然後輸入要儲存的每個 gpo 的最大 gpo 版本數（不包括目前的版本）。</span><span class="sxs-lookup"><span data-stu-id="c4301-112">Select the **Delete old versions of each GPO from the archive** check box, and type the maximum number of GPO versions to store for each GPO, not including the current version.</span></span> <span data-ttu-id="c4301-113">若要只保留目前的版本，請輸入0。</span><span class="sxs-lookup"><span data-stu-id="c4301-113">To retain only the current version, enter 0.</span></span> <span data-ttu-id="c4301-114">最大值不得大於999。</span><span class="sxs-lookup"><span data-stu-id="c4301-114">The maximum must be no greater than 999.</span></span>

    <span data-ttu-id="c4301-115">**重要** 只有 [歷程**記錄**] 視窗 [**唯一版本**] 索引標籤上顯示的 GPO 版本，才會計算出該限制。</span><span class="sxs-lookup"><span data-stu-id="c4301-115">**Important** Only GPO versions displayed on the **Unique Versions** tab of the **History** window count toward the limit.</span></span>

     

4.  <span data-ttu-id="c4301-116">按一下 [**套用**] 按鈕。</span><span class="sxs-lookup"><span data-stu-id="c4301-116">Click the **Apply** button.</span></span>

### <span data-ttu-id="c4301-117">其他考量</span><span class="sxs-lookup"><span data-stu-id="c4301-117">Additional considerations</span></span>

-   <span data-ttu-id="c4301-118">根據預設，您必須是 AGPM 系統管理員（完全控制）才能執行此程式。</span><span class="sxs-lookup"><span data-stu-id="c4301-118">By default, you must be an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="c4301-119">具體說來，您必須擁有 [**清單內容**] 和 [修改網域的**選項**] 許可權。</span><span class="sxs-lookup"><span data-stu-id="c4301-119">Specifically, you must have **List Contents** and **Modify Options** permissions for the domain.</span></span>

-   <span data-ttu-id="c4301-120">您可以在歷程記錄中將其標示為無法刪除，以防止 GPO 版本遭到刪除。</span><span class="sxs-lookup"><span data-stu-id="c4301-120">You can prevent a GPO version from being deleted by marking it in the history as ineligible for deletion.</span></span> <span data-ttu-id="c4301-121">若要這樣做，請以滑鼠右鍵按一下 GPO 歷程記錄中的版本，然後按一下 [**不要刪除**]。</span><span class="sxs-lookup"><span data-stu-id="c4301-121">To do so, right-click the version in the history of the GPO and click **Do Not Delete**.</span></span>

### <span data-ttu-id="c4301-122">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="c4301-122">Additional references</span></span>

-   [<span data-ttu-id="c4301-123">管理封存</span><span class="sxs-lookup"><span data-stu-id="c4301-123">Managing the Archive</span></span>](managing-the-archive-agpm40.md)

 

 





