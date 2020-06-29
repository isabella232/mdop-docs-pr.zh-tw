---
title: 離線編輯 GPO
description: 離線編輯 GPO
author: dansimp
ms.assetid: 9c75eb3c-d4d5-41e0-b65e-8b4464a42cd9
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d7ba0f72d7bfa8e2c597f62f7675a754807525ac
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802798"
---
# <span data-ttu-id="6f311-103">離線編輯 GPO</span><span class="sxs-lookup"><span data-stu-id="6f311-103">Edit a GPO Offline</span></span>


<span data-ttu-id="6f311-104">若要變更受控制的群組原則物件（GPO），您必須先從封存中取出一個 GPO 複本。</span><span class="sxs-lookup"><span data-stu-id="6f311-104">To make changes to a controlled Group Policy Object (GPO), you must first check out a copy of the GPO from the archive.</span></span> <span data-ttu-id="6f311-105">除非再次存回 GPO，否則任何人都無法修改該 GPO，從而避免由多個群組原則管理員引入相互衝突的變更。</span><span class="sxs-lookup"><span data-stu-id="6f311-105">No one else will be able to modify the GPO until it is checked in again, preventing the introduction of conflicting changes by multiple Group Policy administrators.</span></span> <span data-ttu-id="6f311-106">修改完 GPO 之後，您可以將它簽入封存，以便在生產環境中審查並部署。</span><span class="sxs-lookup"><span data-stu-id="6f311-106">When you have finished modifying the GPO, you check it into the archive so that it can be reviewed and deployed to the production environment.</span></span>

<span data-ttu-id="6f311-107">具有 [編輯者] 或 [AGPM 管理員] （完全控制）角色的使用者帳戶、建立 GPO 之核准者的使用者帳戶，或是必須具備高級群組原則管理（AGPM）中所需許可權的使用者帳戶才能完成此程式。</span><span class="sxs-lookup"><span data-stu-id="6f311-107">A user account with the Editor or AGPM Administrator (Full Control) role, the user account of the Approver who created the GPO, or a user account with the necessary permissions in Advanced Group Policy Management (AGPM) is required to complete this procedure.</span></span> <span data-ttu-id="6f311-108">請參閱本主題中的「其他注意事項」中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="6f311-108">Review the details in "Additional considerations" in this topic.</span></span>

## <span data-ttu-id="6f311-109">離線編輯 GPO</span><span class="sxs-lookup"><span data-stu-id="6f311-109">Editing a GPO offline</span></span>


<span data-ttu-id="6f311-110">若要編輯 GPO，您可以從封存中取出該 gpo，在離線時編輯該 gpo，然後將該 GPO 核取到封存中，讓它可以檢查並部署（或由其他編輯者修改）。</span><span class="sxs-lookup"><span data-stu-id="6f311-110">To edit a GPO, you check out the GPO from the archive, edit the GPO offline, and then check the GPO into the archive so that it can be reviewed and deployed (or modified by other Editors).</span></span>

-   [<span data-ttu-id="6f311-111">從封存中取出一個 GPO 進行編輯</span><span class="sxs-lookup"><span data-stu-id="6f311-111">Check out a GPO from the archive for editing</span></span>](#bkmk-checkout)

-   [<span data-ttu-id="6f311-112">離線編輯 GPO</span><span class="sxs-lookup"><span data-stu-id="6f311-112">Edit a GPO offline</span></span>](#bkmk-edit)

-   [<span data-ttu-id="6f311-113">將 GPO 檢查到封存</span><span class="sxs-lookup"><span data-stu-id="6f311-113">Check a GPO into the archive</span></span>](#bkmk-checkin)

### <a href="" id="bkmk-checkout"></a>

**<span data-ttu-id="6f311-114">從封存取出一個 GPO 進行編輯</span><span class="sxs-lookup"><span data-stu-id="6f311-114">To check out a GPO from the archive for editing</span></span>**

1.  <span data-ttu-id="6f311-115">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="6f311-115">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="6f311-116">在 [**內容**] 索引標籤上，按一下 [**受控**] 索引標籤以顯示受控制的 gpo。</span><span class="sxs-lookup"><span data-stu-id="6f311-116">On the **Contents** tab, click the **Controlled** tab to display the controlled GPOs.</span></span>

3.  <span data-ttu-id="6f311-117">以滑鼠右鍵按一下要編輯的 GPO，然後按一下 [**取出]。**</span><span class="sxs-lookup"><span data-stu-id="6f311-117">Right-click the GPO to be edited, and then click **Check Out**.</span></span>

4.  <span data-ttu-id="6f311-118">輸入要在已取出之 GPO 之歷程記錄中顯示的批註，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="6f311-118">Type a comment to be displayed in the History of the GPO while it is checked out, and then click **OK**.</span></span>

5.  <span data-ttu-id="6f311-119">當**進度**視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="6f311-119">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="6f311-120">在 [**受控**] 索引標籤上，GPO 的狀態現在已標示為 [**已取出**]。</span><span class="sxs-lookup"><span data-stu-id="6f311-120">On the **Controlled** tab, the state of the GPO is now identified as **Checked Out**.</span></span>

### <a href="" id="bkmk-edit"></a>

**<span data-ttu-id="6f311-121">若要離線編輯 GPO</span><span class="sxs-lookup"><span data-stu-id="6f311-121">To edit a GPO offline</span></span>**

1.  <span data-ttu-id="6f311-122">在 [**受控**] 索引標籤上，以滑鼠右鍵按一下要編輯的 GPO，然後按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="6f311-122">On the **Controlled** tab, right-click the GPO to be edited, and then click **Edit**.</span></span>

2.  <span data-ttu-id="6f311-123">在 [**群組原則管理編輯器**] 視窗中，對 GPO 的離線複本進行變更。</span><span class="sxs-lookup"><span data-stu-id="6f311-123">In the **Group Policy Management Editor** window, make changes to an offline copy of the GPO.</span></span>

    <span data-ttu-id="6f311-124">**記事** 若要停用所有電腦設定設定或所有使用者設定設定，請在 [**群組原則管理編輯器**] 視窗中，以滑鼠右鍵按一下該 GPO，然後按一下 [**屬性**]。</span><span class="sxs-lookup"><span data-stu-id="6f311-124">**Note** To disable all Computer Configuration settings or all User Configuration settings, right-click the GPO in the **Group Policy Management Editor** window and click **Properties**.</span></span> <span data-ttu-id="6f311-125">視需要選取 [**停用電腦設定**] 或 [**停用使用者設定設定**]。</span><span class="sxs-lookup"><span data-stu-id="6f311-125">Select **Disable Computer Configuration settings** or **Disable User Configuration settings** as appropriate.</span></span>

     

3.  <span data-ttu-id="6f311-126">修改完 GPO 之後，請關閉 [**群組原則管理編輯器**] 視窗。</span><span class="sxs-lookup"><span data-stu-id="6f311-126">When you have finished modifying the GPO, close the **Group Policy Management Editor** window.</span></span>

### <a href="" id="bkmk-checkin"></a>

**<span data-ttu-id="6f311-127">將 GPO 檢查到封存</span><span class="sxs-lookup"><span data-stu-id="6f311-127">To check a GPO into the archive</span></span>**

1.  <span data-ttu-id="6f311-128">在 [**受控**] 索引標籤上：</span><span class="sxs-lookup"><span data-stu-id="6f311-128">On the **Controlled** tab:</span></span>

    -   <span data-ttu-id="6f311-129">如果您沒有對 GPO 進行任何變更，請以滑鼠右鍵按一下該 GPO，然後按一下 [**復原**取出]，然後按一下 **[是]** 以進行確認。</span><span class="sxs-lookup"><span data-stu-id="6f311-129">If you have made no changes to the GPO, right-click the GPO and click **Undo Check Out**, and then click **Yes** to confirm.</span></span>

    -   <span data-ttu-id="6f311-130">如果您已對 GPO 進行變更，請以滑鼠右鍵按一下該 GPO，然後按一下 [**存回**]。</span><span class="sxs-lookup"><span data-stu-id="6f311-130">If you have made changes to the GPO, right-click the GPO and click **Check In**.</span></span>

2.  <span data-ttu-id="6f311-131">輸入要在 [GPO 審核追蹤] 中顯示的批註，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="6f311-131">Type a comment to be displayed in the audit trail of the GPO, and then click **OK**.</span></span>

3.  <span data-ttu-id="6f311-132">當**進度**視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="6f311-132">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="6f311-133">在 [**受控**] 索引標籤上，GPO 的狀態會標示為 [**已核**取]。</span><span class="sxs-lookup"><span data-stu-id="6f311-133">On the **Controlled** tab, the state of the GPO is identified as **Checked In**.</span></span>

### <span data-ttu-id="6f311-134">其他考量</span><span class="sxs-lookup"><span data-stu-id="6f311-134">Additional considerations</span></span>

-   <span data-ttu-id="6f311-135">若要取出並編輯 GPO，請根據預設，您必須是建立或控制 GPO、編輯者或 AGPM 系統管理員的核准者（完全控制）。</span><span class="sxs-lookup"><span data-stu-id="6f311-135">To check out and edit a GPO, by default you must be the Approver who created or controlled the GPO, an Editor, or an AGPM Administrator (Full Control).</span></span> <span data-ttu-id="6f311-136">具體說來，您必須擁有 [**清單內容**] 和 [**編輯設定**] GPO 的 [設定] 許可權。</span><span class="sxs-lookup"><span data-stu-id="6f311-136">Specifically, you must have **List Contents** and **Edit Settings** permissions for the GPO.</span></span> <span data-ttu-id="6f311-137">此外，若要編輯 GPO，您必須是已取出 GPO 的人員。</span><span class="sxs-lookup"><span data-stu-id="6f311-137">Additionally, to edit the GPO you must be the individual who has checked out the GPO.</span></span>

-   <span data-ttu-id="6f311-138">若要在 GPO 中檢入，您必須是 [編輯者]、[核准者] 或 [AGPM 管理員（完全控制）]。</span><span class="sxs-lookup"><span data-stu-id="6f311-138">To check in a GPO, by default, you must be an Editor, an Approver, or an AGPM Administrator (Full Control).</span></span> <span data-ttu-id="6f311-139">具體說來，您必須擁有**清單內容**，並**編輯設定**或為 gpo**部署 gpo**許可權。</span><span class="sxs-lookup"><span data-stu-id="6f311-139">Specifically, you must have **List Contents** and either **Edit Settings** or **Deploy GPO** permissions for the GPO.</span></span> <span data-ttu-id="6f311-140">如果您不是核准者或 AGPM 管理員（或具有「**部署 GPO** 」許可權的其他群組原則管理員），則您必須是已取出該 Gpo 的編輯者。</span><span class="sxs-lookup"><span data-stu-id="6f311-140">If you are not an Approver or AGPM Administrator (or other Group Policy administrator with **Deploy GPO** permission), you must be the Editor who has checked out the GPO.</span></span>

-   <span data-ttu-id="6f311-141">在編輯 GPO 時，在其他 GPO 中，任何群組原則軟體安裝套件的升級，都應該參照已部署的 GPO，而不是取出的版本。</span><span class="sxs-lookup"><span data-stu-id="6f311-141">When editing a GPO, any Group Policy Software Installation upgrade of a package in another GPO should reference the deployed GPO, and not the checked-out copy.</span></span>

### <span data-ttu-id="6f311-142">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="6f311-142">Additional references</span></span>

-   [<span data-ttu-id="6f311-143">編輯 GPO</span><span class="sxs-lookup"><span data-stu-id="6f311-143">Editing a GPO</span></span>](editing-a-gpo-agpm40.md)

-   <span data-ttu-id="6f311-144">檢查 GPO</span><span class="sxs-lookup"><span data-stu-id="6f311-144">Reviewing a GPO</span></span>

    -   [<span data-ttu-id="6f311-145">檢閱 GPO 設定</span><span class="sxs-lookup"><span data-stu-id="6f311-145">Review GPO Settings</span></span>](review-gpo-settings-agpm40.md)

    -   [<span data-ttu-id="6f311-146">檢閱 GPO 連結</span><span class="sxs-lookup"><span data-stu-id="6f311-146">Review GPO Links</span></span>](review-gpo-links-agpm40.md)

    -   [<span data-ttu-id="6f311-147">找出 GPO、GPO 版本或範本之間的差異</span><span class="sxs-lookup"><span data-stu-id="6f311-147">Identify Differences Between GPOs, GPO Versions, or Templates</span></span>](identify-differences-between-gpos-gpo-versions-or-templates-agpm40.md)

-   <span data-ttu-id="6f311-148">部署 GPO</span><span class="sxs-lookup"><span data-stu-id="6f311-148">Deploying a GPO</span></span>

    -   [<span data-ttu-id="6f311-149">要求部署 GPO</span><span class="sxs-lookup"><span data-stu-id="6f311-149">Request Deployment of a GPO</span></span>](request-deployment-of-a-gpo-agpm40.md)

    -   [<span data-ttu-id="6f311-150">部署 GPO</span><span class="sxs-lookup"><span data-stu-id="6f311-150">Deploy a GPO</span></span>](deploy-a-gpo-agpm40.md)

 

 





