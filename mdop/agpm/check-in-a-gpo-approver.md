---
title: 存回 GPO
description: 存回 GPO
author: dansimp
ms.assetid: e428cfff-651f-4903-bf01-d742714d2fa9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6adbcfa1c2b0d79389bc16dd1dde5afc0a4ec4a5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802101"
---
# <span data-ttu-id="c62a7-103">存回 GPO</span><span class="sxs-lookup"><span data-stu-id="c62a7-103">Check In a GPO</span></span>


<span data-ttu-id="c62a7-104">通常，編輯人員應該在其修改完成時，檢查他們已編輯的群組原則物件（Gpo）。</span><span class="sxs-lookup"><span data-stu-id="c62a7-104">Ordinarily, Editors should check in Group Policy objects (GPOs) that they have edited when their modifications are complete.</span></span> <span data-ttu-id="c62a7-105">（如需詳細資訊，請參閱在[離線編輯 GPO](edit-a-gpo-offline.md)。）不過，如果編輯工具無法使用，核准者也可以在 GPO 中存回。</span><span class="sxs-lookup"><span data-stu-id="c62a7-105">(For details, see [Edit a GPO Offline](edit-a-gpo-offline.md).) However, if the Editor is unavailable, an Approver can also check in a GPO.</span></span>

<span data-ttu-id="c62a7-106">具有 [編輯者]、[核准者] 或 [AGPM 管理員（完全控制）] 角色或 [高級群組原則管理] 中的必要許可權的使用者帳戶必須完成此程式。</span><span class="sxs-lookup"><span data-stu-id="c62a7-106">A user account with the Editor, Approver, or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management is required to complete this procedure.</span></span> <span data-ttu-id="c62a7-107">請參閱本主題中的「其他注意事項」中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="c62a7-107">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="c62a7-108">若要存回由編輯工具取出的 GPO</span><span class="sxs-lookup"><span data-stu-id="c62a7-108">To check in a GPO that has been checked out by an Editor</span></span>**

1.  <span data-ttu-id="c62a7-109">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="c62a7-109">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="c62a7-110">在 [詳細資料] 窗格的 [**內容**] 索引標籤上，按一下 [**受控**] 索引標籤以顯示受控 gpo。</span><span class="sxs-lookup"><span data-stu-id="c62a7-110">On the **Contents** tab in the details pane, click the **Controlled** tab to display the controlled GPOs.</span></span>

    -   <span data-ttu-id="c62a7-111">若要捨棄編輯器所做的任何變更，請以滑鼠右鍵按一下該 GPO，按一下 [**復原取出**]，然後按一下 **[是]** 以確認。</span><span class="sxs-lookup"><span data-stu-id="c62a7-111">To discard any changes made by the Editor, right-click the GPO, click **Undo Check Out**, and then click **Yes** to confirm.</span></span>

    -   <span data-ttu-id="c62a7-112">若要保留編輯器所做的變更，請以滑鼠右鍵按一下該 GPO，然後按一下 [**存回**]。</span><span class="sxs-lookup"><span data-stu-id="c62a7-112">To retain changes made by the Editor, right-click the GPO and then click **Check In**.</span></span>

3.  <span data-ttu-id="c62a7-113">輸入要在 [GPO 審核追蹤] 中顯示的批註，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="c62a7-113">Type a comment to be displayed in the audit trail of the GPO, and then click **OK**.</span></span>

4.  <span data-ttu-id="c62a7-114">當**進度**視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="c62a7-114">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="c62a7-115">在 [**受控**] 索引標籤上，GPO 的狀態會標示為 [**已核**取]。</span><span class="sxs-lookup"><span data-stu-id="c62a7-115">On the **Controlled** tab, the state of the GPO is identified as **Checked In**.</span></span>

### <span data-ttu-id="c62a7-116">其他考量</span><span class="sxs-lookup"><span data-stu-id="c62a7-116">Additional considerations</span></span>

-   <span data-ttu-id="c62a7-117">根據預設，您必須是編輯者、核准者或 AGPM 系統管理員（完全控制），才能執行此程式。</span><span class="sxs-lookup"><span data-stu-id="c62a7-117">By default, you must be an Editor, an Approver, or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="c62a7-118">具體說來，您必須擁有**清單內容**，並**編輯設定**或為 gpo**部署 gpo**許可權。</span><span class="sxs-lookup"><span data-stu-id="c62a7-118">Specifically, you must have **List Contents** and either **Edit Settings** or **Deploy GPO** permissions for the GPO.</span></span> <span data-ttu-id="c62a7-119">如果您不是核准者或 AGPM 管理員（或具有「**部署 GPO** 」許可權的其他群組原則管理員），則您必須是已取出該 Gpo 的編輯者。</span><span class="sxs-lookup"><span data-stu-id="c62a7-119">If you are not an Approver or AGPM Administrator (or other Group Policy administrator with **Deploy GPO** permission), you must be the Editor who has checked out the GPO.</span></span>

### <span data-ttu-id="c62a7-120">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="c62a7-120">Additional references</span></span>

-   [<span data-ttu-id="c62a7-121">執行核准者工作</span><span class="sxs-lookup"><span data-stu-id="c62a7-121">Performing Approver Tasks</span></span>](performing-approver-tasks.md)

-   [<span data-ttu-id="c62a7-122">離線編輯 GPO</span><span class="sxs-lookup"><span data-stu-id="c62a7-122">Edit a GPO Offline</span></span>](edit-a-gpo-offline.md)

 

 





