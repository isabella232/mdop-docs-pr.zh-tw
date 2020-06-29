---
title: 刪除 GPO
description: 刪除 GPO
author: dansimp
ms.assetid: 66be3dde-653e-4c25-8cb7-00e7090c8d31
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6c27ddf87a12ed6010c481d93bfc85bb531f3d4f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802830"
---
# <span data-ttu-id="4c3b5-103">刪除 GPO</span><span class="sxs-lookup"><span data-stu-id="4c3b5-103">Delete a GPO</span></span>


<span data-ttu-id="4c3b5-104">做為編輯者，您可能不具備完成群組原則物件（GPO）刪除的許可權，但您必須具備開始程式的許可權，並提交您的要求給核准者。</span><span class="sxs-lookup"><span data-stu-id="4c3b5-104">As an Editor, you may not have permission to complete the deletion of a Group Policy object (GPO), but you do have the permission necessary to begin the process and submit your request to an Approver.</span></span>

<span data-ttu-id="4c3b5-105">必須具備高級組原則管理中具有 [編輯者角色] 或 [必要] 許可權的使用者帳戶，才能完成此程式。</span><span class="sxs-lookup"><span data-stu-id="4c3b5-105">A user account with the Editor role or necessary permissions in Advanced Group Policy Management is required to complete this procedure.</span></span> <span data-ttu-id="4c3b5-106">請參閱本主題中的「其他注意事項」中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="4c3b5-106">Review the details in "Additional considerations" in this topic.</span></span>

**<span data-ttu-id="4c3b5-107">要求刪除受控制的 GPO</span><span class="sxs-lookup"><span data-stu-id="4c3b5-107">To request the deletion of a controlled GPO</span></span>**

1.  <span data-ttu-id="4c3b5-108">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="4c3b5-108">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="4c3b5-109">在 [**內容**] 索引標籤上，按一下 [**受控**] 索引標籤以顯示受控制的 gpo。</span><span class="sxs-lookup"><span data-stu-id="4c3b5-109">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

3.  <span data-ttu-id="4c3b5-110">以滑鼠右鍵按一下要刪除的 GPO，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="4c3b5-110">Right-click the GPO to delete, and then click **Delete**.</span></span>

    -   <span data-ttu-id="4c3b5-111">若要將 GPO 從封存中刪除，同時在生產環境中保持不變的 GPO 部署版本，請按一下 [**僅從封存刪除 gpo] （uncontrol）**。</span><span class="sxs-lookup"><span data-stu-id="4c3b5-111">To delete the GPO from the archive while leaving the deployed version of the GPO untouched in the production environment, click **Delete GPO from archive only (uncontrol)**.</span></span>

    -   <span data-ttu-id="4c3b5-112">若要從封存與生產環境中刪除 GPO，請按一下 [**從封存及生產刪除 gpo**]。</span><span class="sxs-lookup"><span data-stu-id="4c3b5-112">To delete the GPO from both the archive and production environment, click **Delete GPO from archive and production**.</span></span>

        <span data-ttu-id="4c3b5-113">除非您有刪除 Gpo 的特殊許可權，否則您必須提交刪除已部署的 GPO 的要求。</span><span class="sxs-lookup"><span data-stu-id="4c3b5-113">Unless you have special permission to delete GPOs, you must submit a request for deletion of the deployed GPO.</span></span> <span data-ttu-id="4c3b5-114">若要接收申請的複本，請在 [**抄送**] 欄位中輸入您的電子郵件地址。</span><span class="sxs-lookup"><span data-stu-id="4c3b5-114">To receive a copy of the request, type your e-mail address in the **Cc** field.</span></span> <span data-ttu-id="4c3b5-115">輸入要顯示在 GPO 的審核追蹤中的批註，然後按一下 [**提交**]。</span><span class="sxs-lookup"><span data-stu-id="4c3b5-115">Type a comment to be displayed in the audit trail for the GPO, and then click **Submit**.</span></span>

4.  <span data-ttu-id="4c3b5-116">當**進度**視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="4c3b5-116">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="4c3b5-117">GPO 會顯示在 [**擱置**] 索引標籤上的 [gpo] 清單中。當核准者核准您的要求之後，該 GPO 就會從 [**擱置**] 索引標籤移至 [**回收站**] 索引標籤，在這裡可以還原或銷毀。</span><span class="sxs-lookup"><span data-stu-id="4c3b5-117">The GPO is displayed on the list of GPOs on the **Pending** tab. When an Approver has approved your request, the GPO will be moved from the **Pending** tab to the **Recycle Bin** tab, where it can be restored or destroyed.</span></span>

### <span data-ttu-id="4c3b5-118">其他考量</span><span class="sxs-lookup"><span data-stu-id="4c3b5-118">Additional considerations</span></span>

-   <span data-ttu-id="4c3b5-119">根據預設，您必須是編輯器，才能要求刪除已部署的 GPO。</span><span class="sxs-lookup"><span data-stu-id="4c3b5-119">By default, you must be an Editor to request the deletion of a deployed GPO.</span></span> <span data-ttu-id="4c3b5-120">具體說來，您必須擁有 [**清單內容**] 和 [**編輯設定**] GPO 的 [設定] 許可權。</span><span class="sxs-lookup"><span data-stu-id="4c3b5-120">Specifically, you must have **List Contents** and **Edit Settings** permissions for the GPO.</span></span>

-   <span data-ttu-id="4c3b5-121">根據預設，您必須是編輯者、核准者或 AGPM 系統管理員（完全控制），才能從封存中刪除 GPO。</span><span class="sxs-lookup"><span data-stu-id="4c3b5-121">By default, you must be an Editor, an Approver, or an AGPM Administrator (Full Control) to delete a GPO from the archive.</span></span> <span data-ttu-id="4c3b5-122">具體說來，您必須擁有**清單內容**，並**編輯設定**或**刪除**gpo 的 gpo 許可權。</span><span class="sxs-lookup"><span data-stu-id="4c3b5-122">Specifically, you must have **List Contents** and either **Edit Settings** or **Delete GPO** permissions for the GPO.</span></span>

-   <span data-ttu-id="4c3b5-123">若要在獲核准前收回您的要求，請按一下 [**待定**] 索引標籤。以滑鼠右鍵按一下該 GPO，然後按一下 [**收回**]。</span><span class="sxs-lookup"><span data-stu-id="4c3b5-123">To withdraw your request before it has been approved, click the **Pending** tab. Right-click the GPO, and then click **Withdraw**.</span></span> <span data-ttu-id="4c3b5-124">GPO 將會傳回 [**受控**] 索引標籤。</span><span class="sxs-lookup"><span data-stu-id="4c3b5-124">The GPO will be returned to the **Controlled** tab.</span></span>

-   <span data-ttu-id="4c3b5-125">若要從生產環境刪除不受管理的 GPO，而不需先進行控制，請在 [**群組原則管理] 主控台**中，按一下 [**樹林**]，按一下 [**網域**]，按一下 [ \*\* &lt; MyDomain &gt; **]，然後按一下 [**群群組原則物件\*\*</span><span class="sxs-lookup"><span data-stu-id="4c3b5-125">To delete an uncontrolled GPO from the production environment without first controlling it, in the **Group Policy Management Console**, click **Forest**, click **Domains**, click **&lt;MyDomain&gt;**, and then click **Group Policy Objects**.</span></span> <span data-ttu-id="4c3b5-126">以滑鼠右鍵按一下無法控制的 GPO，然後按一下 [**刪除**]。</span><span class="sxs-lookup"><span data-stu-id="4c3b5-126">Right-click the uncontrolled GPO, and then click **Delete**.</span></span>

### <span data-ttu-id="4c3b5-127">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="4c3b5-127">Additional references</span></span>

-   [<span data-ttu-id="4c3b5-128">執行編輯器工作</span><span class="sxs-lookup"><span data-stu-id="4c3b5-128">Performing Editor Tasks</span></span>](performing-editor-tasks.md)

 

 





