---
title: 要求控制先前不受控制的 GPO
description: 要求控制先前不受控制的 GPO
author: dansimp
ms.assetid: 00e8725d-5d7f-4eed-a5e6-c3631632cfbd
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: a92db48d87398568900fc0031e688c862a69b417
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801826"
---
# <span data-ttu-id="83a37-103">要求控制先前不受控制的 GPO</span><span class="sxs-lookup"><span data-stu-id="83a37-103">Request Control of a Previously Uncontrolled GPO</span></span>


<span data-ttu-id="83a37-104">若要使用高級群組原則管理（AGPM）來為現有的群群組原則物件（GPO）提供變更控制，必須使用 AGPM 來控制 GPO。</span><span class="sxs-lookup"><span data-stu-id="83a37-104">To use Advanced Group Policy Management (AGPM) to provide change control for an existing Group Policy object (GPO), the GPO must be controlled with AGPM.</span></span> <span data-ttu-id="83a37-105">除非您是核准者或 AGPM 系統管理員（完全控制），否則您必須要求對 GPO 進行控制。</span><span class="sxs-lookup"><span data-stu-id="83a37-105">Unless you are an Approver or an AGPM Administrator (Full Control), you must request that the GPO be controlled.</span></span>

<span data-ttu-id="83a37-106">必須具備高級組原則管理中具有編輯者或檢閱者角色或必要許可權的使用者帳戶，才能完成此程式。</span><span class="sxs-lookup"><span data-stu-id="83a37-106">A user account with the Editor or Reviewer role or necessary permissions in Advanced Group Policy Management is required to complete this procedure.</span></span> <span data-ttu-id="83a37-107">請參閱本主題中的「其他注意事項」中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="83a37-107">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="83a37-108">控制先前不受管理的 GPO</span><span class="sxs-lookup"><span data-stu-id="83a37-108">To control a previously uncontrolled GPO</span></span>**

1.  <span data-ttu-id="83a37-109">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="83a37-109">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="83a37-110">在 [詳細資料] 窗格的 [**內容**] 索引標籤上，按一下 [**失控**資料] 索引標籤以顯示不受</span><span class="sxs-lookup"><span data-stu-id="83a37-110">On the **Contents** tab in the details pane, click the **Uncontrolled** tab to display the uncontrolled GPOs.</span></span>

3.  <span data-ttu-id="83a37-111">以滑鼠右鍵按一下要使用 AGPM 進行控制的 GPO，然後按一下 [**控制**]。</span><span class="sxs-lookup"><span data-stu-id="83a37-111">Right-click the GPO to be controlled with AGPM, and then click **Control**.</span></span>

4.  <span data-ttu-id="83a37-112">除非您有控制 Gpo 的特殊許可權，否則您必須提交控制權要求。</span><span class="sxs-lookup"><span data-stu-id="83a37-112">Unless you have special permission to control GPOs, you must submit a request for control.</span></span> <span data-ttu-id="83a37-113">若要接收申請的複本，請在 [**抄送**] 欄位中輸入您的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="83a37-113">To receive a copy of the request, type your e-mail address in the **Cc** field.</span></span> <span data-ttu-id="83a37-114">輸入要顯示在 GPO 歷程**記錄**中的批註，然後按一下 [**提交**]。</span><span class="sxs-lookup"><span data-stu-id="83a37-114">Type a comment to be displayed in the **History** of the GPO, and then click **Submit**.</span></span>

5.  <span data-ttu-id="83a37-115">當**進度**視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="83a37-115">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="83a37-116">GPO 會從 [無法**控制**] 索引標籤上的清單中移除，並新增至 [**擱置**] 索引標籤。當核准者核准您的要求之後，該 GPO 就會移至 [**受控**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="83a37-116">The GPO is removed from the list on the **Uncontrolled** tab and added to the **Pending** tab. When an Approver has approved your request, the GPO will be moved to the **Controlled** tab.</span></span>

### <span data-ttu-id="83a37-117">其他考量</span><span class="sxs-lookup"><span data-stu-id="83a37-117">Additional considerations</span></span>

-   <span data-ttu-id="83a37-118">根據預設，您必須是編輯者或檢閱者，才能執行此程式。</span><span class="sxs-lookup"><span data-stu-id="83a37-118">By default, you must be an Editor or a Reviewer to perform this procedure.</span></span> <span data-ttu-id="83a37-119">具體說來，您必須擁有 [**清單內容**] 和 [**讀取設定**] 許可權給網域。</span><span class="sxs-lookup"><span data-stu-id="83a37-119">Specifically, you must have **List Contents** and **Read Settings** permissions for the domain.</span></span>

-   <span data-ttu-id="83a37-120">若要在獲核准前收回您的要求，請按一下 [**待定**] 索引標籤。以滑鼠右鍵按一下該 GPO，然後按一下 [**收回**]。</span><span class="sxs-lookup"><span data-stu-id="83a37-120">To withdraw your request before it has been approved, click the **Pending** tab. Right-click the GPO, and then click **Withdraw**.</span></span> <span data-ttu-id="83a37-121">GPO 將會傳回 [無法**控制**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="83a37-121">The GPO will be returned to the **Uncontrolled** tab.</span></span>

### <span data-ttu-id="83a37-122">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="83a37-122">Additional references</span></span>

-   [<span data-ttu-id="83a37-123">建立、控制或匯入 GPO</span><span class="sxs-lookup"><span data-stu-id="83a37-123">Creating, Controlling, or Importing a GPO</span></span>](creating-controlling-or-importing-a-gpo-editor.md)

 

 





