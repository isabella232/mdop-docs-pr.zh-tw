---
title: 要求建立新的受控制 GPO
description: 要求建立新的受控制 GPO
author: dansimp
ms.assetid: e1875d81-8553-42ee-8f3a-023d6ced86ca
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b7994e1af80c0ae32940d52955f7e5f773d1ee6a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802566"
---
# <span data-ttu-id="4ff10-103">要求建立新的受控制 GPO</span><span class="sxs-lookup"><span data-stu-id="4ff10-103">Request the Creation of a New Controlled GPO</span></span>


<span data-ttu-id="4ff10-104">除非您是核准者或 AGPM 系統管理員（完全控制），否則如果要使用高級群組原則管理（AGPM）來管理新的群組原則物件（GPO），則必須要求建立。</span><span class="sxs-lookup"><span data-stu-id="4ff10-104">Unless you are an Approver or an AGPM Administrator (Full Control), you must request the creation of a new Group Policy object (GPO) if it is to be managed using Advanced Group Policy Management (AGPM).</span></span>

<span data-ttu-id="4ff10-105">必須具備高級組原則管理中具有編輯者或檢閱者角色或必要許可權的使用者帳戶，才能完成此程式。</span><span class="sxs-lookup"><span data-stu-id="4ff10-105">A user account with the Editor or Reviewer role or necessary permissions in Advanced Group Policy Management is required to complete this procedure.</span></span> <span data-ttu-id="4ff10-106">請參閱本主題中的「其他注意事項」中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="4ff10-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="4ff10-107">若要建立透過 AGPM 管理變更控制的新 GPO</span><span class="sxs-lookup"><span data-stu-id="4ff10-107">To create a new GPO with change control managed through AGPM</span></span>**

1.  <span data-ttu-id="4ff10-108">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="4ff10-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="4ff10-109">以滑鼠右鍵按一下 [**變更控制**] 節點，然後按一下 [**新增受控制的 GPO**]。</span><span class="sxs-lookup"><span data-stu-id="4ff10-109">Right-click the **Change Control** node, and then click **New Controlled GPO**.</span></span>

3.  <span data-ttu-id="4ff10-110">除非您有建立 Gpo 的特殊許可權，否則您必須提交建立的要求。</span><span class="sxs-lookup"><span data-stu-id="4ff10-110">Unless you have special permission to create GPOs, you must submit a request for creation.</span></span> <span data-ttu-id="4ff10-111">在 [**新的受控 GPO** ] 對話方塊中：</span><span class="sxs-lookup"><span data-stu-id="4ff10-111">In the **New Controlled GPO** dialog box:</span></span>

    1.  <span data-ttu-id="4ff10-112">若要接收要求的複本，請在 [**抄送**] 欄位中輸入您的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="4ff10-112">To receive a copy of the request, enter your e-mail address in the **Cc** field.</span></span>

    2.  <span data-ttu-id="4ff10-113">輸入新 GPO 的名稱。</span><span class="sxs-lookup"><span data-stu-id="4ff10-113">Type a name for the new GPO.</span></span>

    3.  <span data-ttu-id="4ff10-114">[選用]：輸入新 GPO 的批註。</span><span class="sxs-lookup"><span data-stu-id="4ff10-114">Optional: Type a comment for the new GPO.</span></span>

    4.  <span data-ttu-id="4ff10-115">若要在核准後立即在生產環境中部署新的 GPO，請按一下 [**建立 live**]。</span><span class="sxs-lookup"><span data-stu-id="4ff10-115">To deploy the new GPO to the production environment immediately upon approval, click **Create live**.</span></span> <span data-ttu-id="4ff10-116">若要在離線時建立新的 GPO，而不想在核准時立即部署，請按一下 [**離線建立**]。</span><span class="sxs-lookup"><span data-stu-id="4ff10-116">To create the new GPO offline without immediately deploying it upon approval, click **Create offline**.</span></span>

    5.  <span data-ttu-id="4ff10-117">選取要用來做為新 GPO 起點的 GPO 範本。</span><span class="sxs-lookup"><span data-stu-id="4ff10-117">Select the GPO template to use as a starting point for the new GPO.</span></span>

    6.  <span data-ttu-id="4ff10-118">按一下 **\[提交\]**。</span><span class="sxs-lookup"><span data-stu-id="4ff10-118">Click **Submit**.</span></span>

4.  <span data-ttu-id="4ff10-119">當**進度**視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="4ff10-119">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="4ff10-120">新的 GPO 會顯示在 [**擱置**] 索引標籤的 [gpo] 清單中。當核准者核准您的要求之後，該 GPO 就會移至 [**受控**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="4ff10-120">The new GPO is displayed in the list of GPOs on the **Pending** tab. When an Approver has approved your request, the GPO will be moved to the **Controlled** tab.</span></span>

### <span data-ttu-id="4ff10-121">其他考量</span><span class="sxs-lookup"><span data-stu-id="4ff10-121">Additional considerations</span></span>

-   <span data-ttu-id="4ff10-122">根據預設，您必須是編輯者或檢閱者，才能執行此程式。</span><span class="sxs-lookup"><span data-stu-id="4ff10-122">By default, you must be an Editor or a Reviewer to perform this procedure.</span></span> <span data-ttu-id="4ff10-123">具體說來，您必須擁有該網域的 [**清單內容**] 許可權。</span><span class="sxs-lookup"><span data-stu-id="4ff10-123">Specifically, you must have **List Contents** permission for the domain.</span></span>

-   <span data-ttu-id="4ff10-124">若要在獲核准前收回您的要求，請按一下 [**待定**] 索引標籤。以滑鼠右鍵按一下該 GPO，然後按一下 [**收回**]。</span><span class="sxs-lookup"><span data-stu-id="4ff10-124">To withdraw your request before it has been approved, click the **Pending** tab. Right-click the GPO, then click **Withdraw**.</span></span> <span data-ttu-id="4ff10-125">GPO 將損毀。</span><span class="sxs-lookup"><span data-stu-id="4ff10-125">The GPO will be destroyed.</span></span>

### <span data-ttu-id="4ff10-126">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="4ff10-126">Additional references</span></span>

-   [<span data-ttu-id="4ff10-127">建立、控制或匯入 GPO</span><span class="sxs-lookup"><span data-stu-id="4ff10-127">Creating, Controlling, or Importing a GPO</span></span>](creating-controlling-or-importing-a-gpo-editor.md)

 

 





