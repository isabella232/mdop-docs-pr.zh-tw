---
title: 檢閱 GPO 連結
description: 檢閱 GPO 連結
author: dansimp
ms.assetid: 3aaba9da-f0aa-466f-bd1c-49f11d00ea54
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3884a6f3852986cf02e499af59bb56fcaf404ef8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801781"
---
# <span data-ttu-id="2ee46-103">檢閱 GPO 連結</span><span class="sxs-lookup"><span data-stu-id="2ee46-103">Review GPO Links</span></span>


<span data-ttu-id="2ee46-104">您可以顯示一個圖表，顯示您所選取的群組原則物件（GPO）或 Gpo 連結至組織單位的位置。</span><span class="sxs-lookup"><span data-stu-id="2ee46-104">You can display a diagram showing where a Group Policy Object (GPO) or GPOs that you select are linked to organizational units.</span></span> <span data-ttu-id="2ee46-105">GPO 連結圖表會在每次控制、匯入或檢入 GPO 時進行更新。</span><span class="sxs-lookup"><span data-stu-id="2ee46-105">GPO link diagrams are updated each time the GPO is controlled, imported, or checked in.</span></span>

<span data-ttu-id="2ee46-106">具有 [檢閱者]、[編輯者] 或 [AGPM 管理員] （完全控制）角色的使用者帳戶，或需要高級群組原則管理（AGPM）中的必要許可權，才能完成此程式。</span><span class="sxs-lookup"><span data-stu-id="2ee46-106">A user account with the Reviewer, Editor, Approver, or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management (AGPM)is required to complete this procedure.</span></span> <span data-ttu-id="2ee46-107">請參閱本主題中的「其他注意事項」中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="2ee46-107">Review the details in "Additional considerations" in this topic.</span></span>

## <span data-ttu-id="2ee46-108">查看 GPO 連結</span><span class="sxs-lookup"><span data-stu-id="2ee46-108">Reviewing GPO links</span></span>


-   [<span data-ttu-id="2ee46-109">一或多個 Gpo</span><span class="sxs-lookup"><span data-stu-id="2ee46-109">For one or more GPOs</span></span>](#bkmk-gpos)

-   [<span data-ttu-id="2ee46-110">針對一或多個 GPO 版本</span><span class="sxs-lookup"><span data-stu-id="2ee46-110">For one or more versions of a GPO</span></span>](#bkmk-gpo-versions)

### <a href="" id="bkmk-gpos"></a>

**<span data-ttu-id="2ee46-111">顯示一個或多個 Gpo 的 GPO 連結</span><span class="sxs-lookup"><span data-stu-id="2ee46-111">To display GPO links for one or more GPOs</span></span>**

1.  <span data-ttu-id="2ee46-112">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="2ee46-112">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="2ee46-113">在 [詳細資料] 窗格的 [**內容**] 索引標籤上，按一下 [**控制**]、[**待定**] 或 [**回收站**] 索引標籤以顯示 gpo</span><span class="sxs-lookup"><span data-stu-id="2ee46-113">On the **Contents** tab in the details pane, click the **Controlled**, **Pending**, or **Recycle Bin** tab to display GPOs.</span></span>

3.  <span data-ttu-id="2ee46-114">選取一個或多個要顯示連結的 Gpo，以滑鼠右鍵按一下選取的 GPO，按一下 [**設定**]，然後按一下 [ **GPO 連結**]，以顯示包含所選 gpo 連結的網域和組織單位圖表。</span><span class="sxs-lookup"><span data-stu-id="2ee46-114">Select one or more GPOs for which to display links, right-click a selected GPO, click **Settings**, and then click **GPO Links** to display a diagram of domains and organizational units with links to the selected GPO(s).</span></span>

### <a href="" id="bkmk-gpo-versions"></a>

**<span data-ttu-id="2ee46-115">顯示一個或多個版本 GPO 的 GPO 連結</span><span class="sxs-lookup"><span data-stu-id="2ee46-115">To display GPO links for one or more versions of a GPO</span></span>**

1.  <span data-ttu-id="2ee46-116">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="2ee46-116">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="2ee46-117">在 [詳細資料] 窗格的 [**內容**] 索引標籤上，按一下 [**控制**] 或 [**回收站**] 索引標籤以顯示 gpo</span><span class="sxs-lookup"><span data-stu-id="2ee46-117">On the **Contents** tab in the details pane, click the **Controlled** or **Recycle Bin** tab to display GPOs.</span></span>

3.  <span data-ttu-id="2ee46-118">按兩下該 GPO 以顯示其歷程記錄。</span><span class="sxs-lookup"><span data-stu-id="2ee46-118">Double-click the GPO to display its history.</span></span>

4.  <span data-ttu-id="2ee46-119">以滑鼠右鍵按一下要查看其設定的 GPO 版本，按一下 [**設定**]，然後按一下 [ **HTML 報表**] 或 [ **XML 報表**]，以顯示 GPO 設定的摘要。</span><span class="sxs-lookup"><span data-stu-id="2ee46-119">Right-click the GPO version for which to review the settings, click **Settings**, and then click **HTML Report** or **XML Report** to display a summary of the GPO's settings.</span></span>

### <span data-ttu-id="2ee46-120">其他考量</span><span class="sxs-lookup"><span data-stu-id="2ee46-120">Additional considerations</span></span>

-   <span data-ttu-id="2ee46-121">根據預設，您必須是檢閱者、編輯者或 AGPM 管理員（完全控制），才能執行此程式。</span><span class="sxs-lookup"><span data-stu-id="2ee46-121">By default, you must be a Reviewer, an Editor, an Approver, or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="2ee46-122">具體來說，您必須擁有 [**清單內容**] 和 [**讀取設定**] 許可權給 GPO。</span><span class="sxs-lookup"><span data-stu-id="2ee46-122">Specifically, you must have **List Contents** and **Read Settings** permissions for the GPO.</span></span> <span data-ttu-id="2ee46-123">此外，若要顯示 Gpo 清單，您必須擁有該網域的 [**清單內容**] 許可權。</span><span class="sxs-lookup"><span data-stu-id="2ee46-123">Also, to display the list of GPOs, you must have **List Contents** permission for the domain.</span></span>

### <span data-ttu-id="2ee46-124">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="2ee46-124">Additional references</span></span>

-   [<span data-ttu-id="2ee46-125">執行檢閱者工作</span><span class="sxs-lookup"><span data-stu-id="2ee46-125">Performing Reviewer Tasks</span></span>](performing-reviewer-tasks-agpm40.md)

 

 





