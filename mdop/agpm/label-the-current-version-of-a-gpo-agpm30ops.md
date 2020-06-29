---
title: 標示 GPO 的目前版本
description: 標示 GPO 的目前版本
author: dansimp
ms.assetid: 3845211a-0bc9-4875-9906-cb758c443825
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: f9e656258591a56397c5a8053b2e98772f57949a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802709"
---
# <span data-ttu-id="dd9b0-103">標示 GPO 的目前版本</span><span class="sxs-lookup"><span data-stu-id="dd9b0-103">Label the Current Version of a GPO</span></span>


<span data-ttu-id="dd9b0-104">您可以標示目前版本的群組原則物件（GPO），以便在其記錄中輕鬆識別。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-104">You can label the current version of a Group Policy Object (GPO) for easy identification in its history.</span></span> <span data-ttu-id="dd9b0-105">如果發生問題，您可以使用標籤來找出您可以回滾的已知完好版本。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-105">You can use a label to identify a known good version to which you could roll back if a problem occurs.</span></span> <span data-ttu-id="dd9b0-106">此外，您也可以一次將多個 Gpo 標示成相同的標籤，您可以將相關的 Gpo 標示為必須回滾到同一個點（如果稍後需要回滾）。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-106">Also, by labeling multiple GPOs with the same label at one time, you can mark related GPOs that should be rolled back to the same point if rollback should later be necessary.</span></span>

<span data-ttu-id="dd9b0-107">具有 [編輯者]、[核准者] 或 [AGPM 管理員（完全控制）] 角色的使用者帳戶，或 [高級群組原則管理] （AGPM）中的必要許可權，才能完成此程式。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-107">A user account with the Editor, Approver, or AGPM Administrator (Full Control) role or necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="dd9b0-108">請參閱本主題中的「其他注意事項」中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-108">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="dd9b0-109">在其歷史記錄中標示目前的 Gpo 版本</span><span class="sxs-lookup"><span data-stu-id="dd9b0-109">To label the current version of GPOs in their histories</span></span>**

1.  <span data-ttu-id="dd9b0-110">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-110">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="dd9b0-111">在 [**內容**] 索引標籤上，按一下 [**受控**] 索引標籤以顯示受控制的 gpo。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-111">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

3.  <span data-ttu-id="dd9b0-112">按一下要為目前版本加上標籤的 GPO。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-112">Click a GPO for which to label the current version.</span></span> <span data-ttu-id="dd9b0-113">若要選取多個 Gpo，請按 SHIFT 鍵，然後按一下連續 Gpo 群組中的最後一個 GPO，或按下 CTRL 並按一下個別 Gpo。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-113">To select multiple GPOs, press SHIFT and click the last GPO in a contiguous group of GPOs, or press CTRL and click individual GPOs.</span></span> <span data-ttu-id="dd9b0-114">以滑鼠右鍵按一下選取的 GPO，然後按一下 [**標籤**]。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-114">Right-click a selected GPO, and then click **Label**.</span></span>

4.  <span data-ttu-id="dd9b0-115">輸入要在選取的每個 GPO 之歷程記錄中顯示的標籤和批註，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-115">Type a label and a comment to be displayed in the history of each GPO selected, and then click **OK**.</span></span>

5.  <span data-ttu-id="dd9b0-116">當**進度**視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-116">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span>

### <span data-ttu-id="dd9b0-117">其他考量</span><span class="sxs-lookup"><span data-stu-id="dd9b0-117">Additional considerations</span></span>

-   <span data-ttu-id="dd9b0-118">根據預設，您必須是編輯者、核准者或 AGPM 系統管理員（完全控制），才能執行此程式。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-118">By default, you must be an Editor, an Approver, or an AGPM Administrator (Full Control) to perform this procedure.</span></span> <span data-ttu-id="dd9b0-119">具體說來，您必須擁有**清單內容**，並**編輯設定**或為 gpo**部署 gpo**許可權。</span><span class="sxs-lookup"><span data-stu-id="dd9b0-119">Specifically, you must have **List Contents** and either **Edit Settings** or **Deploy GPO** permissions for the GPO.</span></span>

### <span data-ttu-id="dd9b0-120">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="dd9b0-120">Additional references</span></span>

-   [<span data-ttu-id="dd9b0-121">編輯 GPO</span><span class="sxs-lookup"><span data-stu-id="dd9b0-121">Editing a GPO</span></span>](editing-a-gpo-agpm30ops.md)

 

 





