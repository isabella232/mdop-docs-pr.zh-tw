---
title: 離線編輯 GPO
description: 離線編輯 GPO
author: dansimp
ms.assetid: 4a148952-9fe9-4ec4-8df1-b25e37c97a54
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6753ad21adb810e60e0b284204a61d4dd58c2384
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802797"
---
# <span data-ttu-id="125d1-103">離線編輯 GPO</span><span class="sxs-lookup"><span data-stu-id="125d1-103">Edit a GPO Offline</span></span>


<span data-ttu-id="125d1-104">若要變更受控制的群組原則物件（GPO），您必須先從封存中取出一個 GPO 複本。</span><span class="sxs-lookup"><span data-stu-id="125d1-104">To make changes to a controlled Group Policy object (GPO), you must first check out a copy of the GPO from the archive.</span></span> <span data-ttu-id="125d1-105">除非再次存回 GPO，否則任何人都無法修改該 GPO，從而避免由多個群組原則管理員引入相互衝突的變更。</span><span class="sxs-lookup"><span data-stu-id="125d1-105">No one else will be able to modify the GPO until it is checked in again, preventing the introduction of conflicting changes by multiple Group Policy administrators.</span></span> <span data-ttu-id="125d1-106">修改完 GPO 之後，您可以將它簽入封存，以便在生產環境中審查並部署。</span><span class="sxs-lookup"><span data-stu-id="125d1-106">When you have finished modifying the GPO, you check it into the archive, so it can be reviewed and deployed to the production environment.</span></span>

<span data-ttu-id="125d1-107">具有 [編輯者] 或 [AGPM 管理員] （完全控制）角色的使用者帳戶、建立 GPO 之核准者的使用者帳戶，或是必須有高級群組原則管理所需許可權的使用者帳戶才能完成此程式。</span><span class="sxs-lookup"><span data-stu-id="125d1-107">A user account with the Editor or AGPM Administrator (Full Control) role, the user account of the Approver who created the GPO, or a user account with the necessary permissions in Advanced Group Policy Management is required to complete this procedure.</span></span> <span data-ttu-id="125d1-108">請參閱本主題中的「其他注意事項」中的詳細資料。</span><span class="sxs-lookup"><span data-stu-id="125d1-108">Review the details in "Additional considerations" in this topic.</span></span>

## <span data-ttu-id="125d1-109">離線編輯 GPO</span><span class="sxs-lookup"><span data-stu-id="125d1-109">Editing a GPO offline</span></span>


<span data-ttu-id="125d1-110">若要編輯 GPO，您可以從封存中取出該 gpo，在離線時編輯該 gpo，然後將該 GPO 核取到封存中，讓它可以檢查並部署（或由其他編輯者修改）。</span><span class="sxs-lookup"><span data-stu-id="125d1-110">To edit a GPO, you check out the GPO from the archive, edit the GPO offline, and then check the GPO into the archive, so it can be reviewed and deployed (or modified by other Editors).</span></span>

-   [<span data-ttu-id="125d1-111">取出 GPO</span><span class="sxs-lookup"><span data-stu-id="125d1-111">Check out a GPO</span></span>](#bkmk-checkout)

-   [<span data-ttu-id="125d1-112">編輯 GPO</span><span class="sxs-lookup"><span data-stu-id="125d1-112">Edit a GPO</span></span>](#bkmk-edit)

-   [<span data-ttu-id="125d1-113">在 GPO 中存回</span><span class="sxs-lookup"><span data-stu-id="125d1-113">Check in a GPO</span></span>](#bkmk-checkin)

### <a href="" id="bkmk-checkout"></a>

**<span data-ttu-id="125d1-114">從封存取出一個 GPO 進行編輯</span><span class="sxs-lookup"><span data-stu-id="125d1-114">To check out a GPO from the archive for editing</span></span>**

1.  <span data-ttu-id="125d1-115">在 [**群組原則管理] 主控台**樹狀結構中，按一下要管理 gpo 的林和網域中的 [**變更控制**]。</span><span class="sxs-lookup"><span data-stu-id="125d1-115">In the **Group Policy Management Console** tree, click **Change Control** in the forest and domain in which you want to manage GPOs.</span></span>

2.  <span data-ttu-id="125d1-116">在 [詳細資料] 窗格的 [**內容**] 索引標籤上，按一下 [**受控**] 索引標籤以顯示受控 gpo。</span><span class="sxs-lookup"><span data-stu-id="125d1-116">On the **Contents** tab in the details pane, click the **Controlled** tab to display the controlled GPOs.</span></span>

3.  <span data-ttu-id="125d1-117">以滑鼠右鍵按一下要編輯的 GPO，然後按一下 [**取出]。**</span><span class="sxs-lookup"><span data-stu-id="125d1-117">Right-click the GPO to be edited, and then click **Check Out**.</span></span>

4.  <span data-ttu-id="125d1-118">輸入要在已取出之 GPO 之歷程記錄中顯示的批註，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="125d1-118">Type a comment to be displayed in the History of the GPO while it is checked out, then click **OK**.</span></span>

5.  <span data-ttu-id="125d1-119">當**進度**視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="125d1-119">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="125d1-120">在 [**受控**] 索引標籤上，GPO 的狀態現在已標示為 [**已取出**]。</span><span class="sxs-lookup"><span data-stu-id="125d1-120">On the **Controlled** tab, the state of the GPO is now identified as **Checked Out**.</span></span>

### <a href="" id="bkmk-edit"></a>

**<span data-ttu-id="125d1-121">若要離線編輯 GPO</span><span class="sxs-lookup"><span data-stu-id="125d1-121">To edit a GPO offline</span></span>**

1.  <span data-ttu-id="125d1-122">在 [**受控**] 索引標籤上，以滑鼠右鍵按一下要編輯的 GPO，然後按一下 [**編輯**]。</span><span class="sxs-lookup"><span data-stu-id="125d1-122">On the **Controlled** tab, right-click the GPO to be edited, and then click **Edit**.</span></span>

2.  <span data-ttu-id="125d1-123">在 [**群組原則物件編輯器**] 中，對 GPO 的離線複本進行變更。</span><span class="sxs-lookup"><span data-stu-id="125d1-123">In the **Group Policy Object Editor**, make changes to an offline copy of the GPO.</span></span>

3.  <span data-ttu-id="125d1-124">修改完 GPO 之後，請關閉 [**群組原則物件編輯器**]。</span><span class="sxs-lookup"><span data-stu-id="125d1-124">When you have finished modifying the GPO, close the **Group Policy Object Editor**.</span></span>

### <a href="" id="bkmk-checkin"></a>

**<span data-ttu-id="125d1-125">將 GPO 檢查到封存</span><span class="sxs-lookup"><span data-stu-id="125d1-125">To check a GPO into the archive</span></span>**

1.  <span data-ttu-id="125d1-126">在 [**受控**] 索引標籤上：</span><span class="sxs-lookup"><span data-stu-id="125d1-126">On the **Controlled** tab:</span></span>

    -   <span data-ttu-id="125d1-127">如果您沒有對 GPO 進行任何變更，請以滑鼠右鍵按一下該 GPO，然後按一下 [**復原**取出]，然後按一下 **[是]** 以確認。</span><span class="sxs-lookup"><span data-stu-id="125d1-127">If you have made no changes to the GPO, right-click the GPO and click **Undo Check Out**, then click **Yes** to confirm.</span></span>

    -   <span data-ttu-id="125d1-128">如果您已對 GPO 進行變更，請以滑鼠右鍵按一下該 GPO，然後按一下 [**存回**]。</span><span class="sxs-lookup"><span data-stu-id="125d1-128">If you have made changes to the GPO, right-click the GPO and click **Check In**.</span></span>

2.  <span data-ttu-id="125d1-129">輸入要在 [GPO 審核追蹤] 中顯示的批註，然後按一下 **[確定]**。</span><span class="sxs-lookup"><span data-stu-id="125d1-129">Type a comment to be displayed in the audit trail of the GPO, and then click **OK**.</span></span>

3.  <span data-ttu-id="125d1-130">當**進度**視窗顯示整體進度完成時，請按一下 [**關閉**]。</span><span class="sxs-lookup"><span data-stu-id="125d1-130">When the **Progress** window indicates that overall progress is complete, click **Close**.</span></span> <span data-ttu-id="125d1-131">在 [**受控**] 索引標籤上，GPO 的狀態會標示為 [**已核**取]。</span><span class="sxs-lookup"><span data-stu-id="125d1-131">On the **Controlled** tab, the state of the GPO is identified as **Checked In**.</span></span>

### <span data-ttu-id="125d1-132">其他考量</span><span class="sxs-lookup"><span data-stu-id="125d1-132">Additional considerations</span></span>

-   <span data-ttu-id="125d1-133">若要取出並編輯 GPO，請根據預設，您必須是建立或控制 GPO、編輯者或 AGPM 系統管理員的核准者（完全控制）。</span><span class="sxs-lookup"><span data-stu-id="125d1-133">To check out and edit a GPO, by default, you must be the Approver who created or controlled the GPO, an Editor, or an AGPM Administrator (Full Control).</span></span> <span data-ttu-id="125d1-134">具體說來，您必須擁有 [**清單內容**] 和 [**編輯設定**] GPO 的 [設定] 許可權。</span><span class="sxs-lookup"><span data-stu-id="125d1-134">Specifically, you must have **List Contents** and **Edit Settings** permissions for the GPO.</span></span> <span data-ttu-id="125d1-135">此外，若要編輯 GPO，您必須是已取出 GPO 的人員。</span><span class="sxs-lookup"><span data-stu-id="125d1-135">Additionally, to edit the GPO you must be the individual who has checked out the GPO.</span></span>

-   <span data-ttu-id="125d1-136">若要在 GPO 中檢入，您必須是 [編輯者]、[核准者] 或 [AGPM 管理員（完全控制）]。</span><span class="sxs-lookup"><span data-stu-id="125d1-136">To check in a GPO, by default, you must be an Editor, an Approver, or an AGPM Administrator (Full Control).</span></span> <span data-ttu-id="125d1-137">具體說來，您必須擁有**清單內容**，並**編輯設定**或為 gpo**部署 gpo**許可權。</span><span class="sxs-lookup"><span data-stu-id="125d1-137">Specifically, you must have **List Contents** and either **Edit Settings** or **Deploy GPO** permissions for the GPO.</span></span> <span data-ttu-id="125d1-138">如果您不是核准者或 AGPM 管理員（或具有「**部署 GPO** 」許可權的其他群組原則管理員），則您必須是已取出該 Gpo 的編輯者。</span><span class="sxs-lookup"><span data-stu-id="125d1-138">If you are not an Approver or AGPM Administrator (or other Group Policy administrator with **Deploy GPO** permission), you must be the Editor who has checked out the GPO.</span></span>

-   <span data-ttu-id="125d1-139">在編輯 GPO 時，在另一個 GPO 中，任何群群組原則軟體安裝套件的升級，都應該參照已部署的 GPO，而不是已取出的複本。</span><span class="sxs-lookup"><span data-stu-id="125d1-139">When editing a GPO, any Group Policy Software Installation upgrade of a package in another GPO should reference the deployed GPO, not the checked-out copy.</span></span>

### <span data-ttu-id="125d1-140">其他參考資料</span><span class="sxs-lookup"><span data-stu-id="125d1-140">Additional references</span></span>

-   [<span data-ttu-id="125d1-141">編輯 GPO</span><span class="sxs-lookup"><span data-stu-id="125d1-141">Editing a GPO</span></span>](editing-a-gpo.md)

-   <span data-ttu-id="125d1-142">檢查 GPO</span><span class="sxs-lookup"><span data-stu-id="125d1-142">Reviewing a GPO</span></span>

    -   [<span data-ttu-id="125d1-143">檢閱 GPO 設定</span><span class="sxs-lookup"><span data-stu-id="125d1-143">Review GPO Settings</span></span>](review-gpo-settings.md)

    -   [<span data-ttu-id="125d1-144">檢閱 GPO 連結</span><span class="sxs-lookup"><span data-stu-id="125d1-144">Review GPO Links</span></span>](review-gpo-links.md)

    -   [<span data-ttu-id="125d1-145">找出 GPO、GPO 版本或範本之間的差異</span><span class="sxs-lookup"><span data-stu-id="125d1-145">Identify Differences Between GPOs, GPO Versions, or Templates</span></span>](identify-differences-between-gpos-gpo-versions-or-templates.md)

-   <span data-ttu-id="125d1-146">部署 GPO</span><span class="sxs-lookup"><span data-stu-id="125d1-146">Deploying a GPO</span></span>

    -   [<span data-ttu-id="125d1-147">要求部署 GPO</span><span class="sxs-lookup"><span data-stu-id="125d1-147">Request Deployment of a GPO</span></span>](request-deployment-of-a-gpo.md)

    -   [<span data-ttu-id="125d1-148">部署 GPO</span><span class="sxs-lookup"><span data-stu-id="125d1-148">Deploy a GPO</span></span>](deploy-a-gpo.md)

 

 





