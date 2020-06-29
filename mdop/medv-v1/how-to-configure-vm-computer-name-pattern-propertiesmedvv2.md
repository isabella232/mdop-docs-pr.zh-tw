---
title: 如何設定 VM 電腦名稱模式內容
description: 如何設定 VM 電腦名稱模式內容
author: dansimp
ms.assetid: ddf79ace-8cc3-4ee6-be5a-5940b4df5c36
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: aa171712b6624b73fb5e0756aaf56277baa4c8cc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812140"
---
# <span data-ttu-id="010bc-103">如何設定 VM 電腦名稱模式內容</span><span class="sxs-lookup"><span data-stu-id="010bc-103">How to Configure VM Computer Name Pattern Properties</span></span>


<span data-ttu-id="010bc-104">您可以針對 revertible 和持續性的 MED-V 工作區，指派虛擬機器電腦名稱稱模式。</span><span class="sxs-lookup"><span data-stu-id="010bc-104">A virtual machine computer name pattern can be assigned both for revertible and for persistent MED-V workspaces.</span></span>

-   <span data-ttu-id="010bc-105">Revertible-管理員可以為每個 Revertible 的 MED-V 工作區實例指派唯一名稱，以在多部電腦上使用相同的 MED-V 工作區來區分。</span><span class="sxs-lookup"><span data-stu-id="010bc-105">Revertible—Administrators can assign a unique name to each revertible MED-V workspace instance to differentiate between multiple computers using the same MED-V workspace.</span></span>

-   <span data-ttu-id="010bc-106">Persistent：在持久的 MED-V 工作區中，管理員可以將電腦設定為在安裝程式腳本中重新命名。</span><span class="sxs-lookup"><span data-stu-id="010bc-106">Persistent—In a persistent MED-V workspace, administrators can set a computer to be renamed during a setup script.</span></span>

## <span data-ttu-id="010bc-107">如何將虛擬電腦的電腦名稱稱模式指派給 Revertible MED-V-V 工作區</span><span class="sxs-lookup"><span data-stu-id="010bc-107">How to Assign a Virtual Machine Computer Name Pattern to a Revertible MED-V Workspace</span></span>


**<span data-ttu-id="010bc-108">將虛擬電腦電腦名稱稱模式指派給 revertible MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="010bc-108">To assign a virtual machine computer name pattern to a revertible MED-V workspace</span></span>**

1.  <span data-ttu-id="010bc-109">按一下要設定的 revertible MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="010bc-109">Click the revertible MED-V workspace to configure.</span></span>

2.  <span data-ttu-id="010bc-110">在 [ **REVERTIBLE VM 設定**] 區段中，選取 [**根據電腦名稱稱模式重新命名 VM** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="010bc-110">In the **Revertible VM Setup** section, select the **Rename the VM based on the computer name pattern** check box.</span></span>

3.  <span data-ttu-id="010bc-111">在 [ **VM 電腦名稱稱模式**] 區段中，輸入要用來命名虛擬機器影像的模式，使用下列選項：</span><span class="sxs-lookup"><span data-stu-id="010bc-111">In the **VM Computer Name Pattern** section, enter the pattern to use for naming virtual machine images, using the following options:</span></span>

    -   <span data-ttu-id="010bc-112">**常數**-在使用 med-v 工作區的所有電腦上輸入完全不變的文字。</span><span class="sxs-lookup"><span data-stu-id="010bc-112">**Constant**—Enter free text that will be constant on all computers using the MED-V workspace.</span></span>

    -   <span data-ttu-id="010bc-113">[**變數**]：輸入變數，請按一下 [**插入變數**]，然後選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="010bc-113">**Variable**—Enter a variable, by clicking **Insert Variable**, and select from one of the following:</span></span>

        -   **<span data-ttu-id="010bc-114">使用者名稱</span><span class="sxs-lookup"><span data-stu-id="010bc-114">User name</span></span>**

        -   **<span data-ttu-id="010bc-115">網域名稱 (Domain name)</span><span class="sxs-lookup"><span data-stu-id="010bc-115">Domain name</span></span>**

        -   **<span data-ttu-id="010bc-116">主機名稱</span><span class="sxs-lookup"><span data-stu-id="010bc-116">Host name</span></span>**

        -   **<span data-ttu-id="010bc-117">工作區名稱</span><span class="sxs-lookup"><span data-stu-id="010bc-117">Workspace name</span></span>**

        -   **<span data-ttu-id="010bc-118">虛擬機器名稱</span><span class="sxs-lookup"><span data-stu-id="010bc-118">Virtual machine name</span></span>**

        <span data-ttu-id="010bc-119">選取的變數會與使用 MED-V 工作區的電腦相關。</span><span class="sxs-lookup"><span data-stu-id="010bc-119">The variable selected will be specific to the computer using the MED-V workspace.</span></span> <span data-ttu-id="010bc-120">例如，如果已選取 [**功能變數名稱**]，則每個電腦的唯一名稱將會包含電腦的功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="010bc-120">For example, if **Domain name** is selected, the unique name for each computer will include the computer's domain name.</span></span>

    -   <span data-ttu-id="010bc-121">**隨機字元**：針對要包含在模式中的每個隨機字元輸入 "\ #"。</span><span class="sxs-lookup"><span data-stu-id="010bc-121">**Random characters**—Enter “\#” for each random character to include in the pattern.</span></span> <span data-ttu-id="010bc-122">使用 MED-V 工作區的每個電腦將會有指定長度的尾碼（隨機產生）。</span><span class="sxs-lookup"><span data-stu-id="010bc-122">Each computer using the MED-V workspace will have a suffix of the length specified, which is generated randomly.</span></span>

    **<span data-ttu-id="010bc-123">注意</span><span class="sxs-lookup"><span data-stu-id="010bc-123">Note</span></span>**  
    <span data-ttu-id="010bc-124">電腦名稱稱的長度限制為15個字元。</span><span class="sxs-lookup"><span data-stu-id="010bc-124">The computer name has a limit of 15 characters.</span></span> <span data-ttu-id="010bc-125">如果模式超過限制，將會被截斷。</span><span class="sxs-lookup"><span data-stu-id="010bc-125">If the pattern exceeds the limit, it will be truncated.</span></span>



4.  <span data-ttu-id="010bc-126">在 [**原則**] 功能表上，選取 [**確認**]。</span><span class="sxs-lookup"><span data-stu-id="010bc-126">On the **Policy** menu, select **Commit**.</span></span>

    **<span data-ttu-id="010bc-127">注意</span><span class="sxs-lookup"><span data-stu-id="010bc-127">Note</span></span>**  
    <span data-ttu-id="010bc-128">已核取根據電腦名稱稱模式（在 [ **REVERTIBLE VM 設定**] 區段）中的 **[重新命名 vm** ] 時，可以指派 revertible VM 電腦名稱稱模式。</span><span class="sxs-lookup"><span data-stu-id="010bc-128">A revertible VM computer name pattern can be assigned only when **Rename the VM based on the computer name patterns** (in the **Revertible VM Setup** section) is checked.</span></span>



~~~
**Note**  
A unique computer name can be assigned only if it is configured prior to MED-V workspace setup. Changing the name will not affect MED-V workspaces that were already set up.
~~~



## <span data-ttu-id="010bc-129">如何將虛擬電腦電腦名稱稱模式指派給持久的 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="010bc-129">How to Assign a Virtual Machine Computer Name Pattern to a Persistent MED-V Workspace</span></span>


**<span data-ttu-id="010bc-130">將虛擬電腦電腦名稱稱模式指派至持久的 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="010bc-130">To assign a virtual machine computer name pattern to a persistent MED-V workspace</span></span>**

1.  <span data-ttu-id="010bc-131">按一下要設定的持久 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="010bc-131">Click the persistent MED-V workspace to configure.</span></span>

2.  <span data-ttu-id="010bc-132">在 [**永久 VM 設定**] 區段中，按一下 [**腳本編輯器**]。</span><span class="sxs-lookup"><span data-stu-id="010bc-132">In the **Persistent VM Setup** section, click **Script Editor**.</span></span>

3.  <span data-ttu-id="010bc-133">在 [**腳本動作**] 對話方塊中，按一下 [**新增**]，然後在子功能表上，按一下 [**重新命名電腦**]。</span><span class="sxs-lookup"><span data-stu-id="010bc-133">In the **Script Actions** dialog box, click **Add**, and on the submenu, click **Rename Computer**.</span></span>

4.  <span data-ttu-id="010bc-134">按一下 **[確定]** 以關閉 [**腳本動作**] 對話方塊。</span><span class="sxs-lookup"><span data-stu-id="010bc-134">Click **OK** to close the **Script Actions** dialog box.</span></span>

5.  <span data-ttu-id="010bc-135">在 [ **Vm 設定**] 索引標籤上，于 [ **Vm 電腦名稱稱模式**] 區段中，輸入要用來重新命名電腦的模式，使用下列程式：</span><span class="sxs-lookup"><span data-stu-id="010bc-135">On the **VM Setup** tab, in the **VM Computer Name Pattern** section, enter the pattern to use for renaming the computer, using the following:</span></span>

    -   <span data-ttu-id="010bc-136">[**固定**]：輸入電腦名稱稱中將包含的自由文字。</span><span class="sxs-lookup"><span data-stu-id="010bc-136">**Constant**— Enter free text that will be included in the computer name.</span></span>

    -   <span data-ttu-id="010bc-137">[**變數**]：輸入變數，請按一下 [**插入變數**]，然後選取下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="010bc-137">**Variable**—Enter a variable, by clicking **Insert Variable**, and select from one of the following:</span></span>

        -   **<span data-ttu-id="010bc-138">使用者名稱</span><span class="sxs-lookup"><span data-stu-id="010bc-138">User name</span></span>**

        -   **<span data-ttu-id="010bc-139">網域名稱 (Domain name)</span><span class="sxs-lookup"><span data-stu-id="010bc-139">Domain name</span></span>**

        -   **<span data-ttu-id="010bc-140">主機名稱</span><span class="sxs-lookup"><span data-stu-id="010bc-140">Host name</span></span>**

        -   **<span data-ttu-id="010bc-141">工作區名稱</span><span class="sxs-lookup"><span data-stu-id="010bc-141">Workspace name</span></span>**

        -   **<span data-ttu-id="010bc-142">虛擬機器名稱</span><span class="sxs-lookup"><span data-stu-id="010bc-142">Virtual machine name</span></span>**

        <span data-ttu-id="010bc-143">已選取的變數會針對要重新命名的電腦而定。</span><span class="sxs-lookup"><span data-stu-id="010bc-143">The variable selected will be specific to the computer that is being renamed.</span></span> <span data-ttu-id="010bc-144">例如，如果已選取 [**功能變數名稱**]，電腦名稱稱將會包含電腦的功能變數名稱。</span><span class="sxs-lookup"><span data-stu-id="010bc-144">For example, if **Domain name** is selected, the computer name will include the computer's domain name.</span></span>

    -   <span data-ttu-id="010bc-145">**隨機字元**：針對要包含在模式中的每個隨機字元輸入 "\ #"。</span><span class="sxs-lookup"><span data-stu-id="010bc-145">**Random characters**— Enter “\#” for each random character to include in the pattern.</span></span> <span data-ttu-id="010bc-146">電腦將會有指定長度的尾碼（隨機產生）。</span><span class="sxs-lookup"><span data-stu-id="010bc-146">The computer will have a suffix of the length specified, which is generated randomly.</span></span>

    **<span data-ttu-id="010bc-147">注意</span><span class="sxs-lookup"><span data-stu-id="010bc-147">Note</span></span>**  
    <span data-ttu-id="010bc-148">電腦名稱稱的長度限制為15個字元。</span><span class="sxs-lookup"><span data-stu-id="010bc-148">The computer name has a limit of 15 characters.</span></span> <span data-ttu-id="010bc-149">如果模式超過限制，將會被截斷。</span><span class="sxs-lookup"><span data-stu-id="010bc-149">If the pattern exceeds the limit, it will be truncated.</span></span>



6.  <span data-ttu-id="010bc-150">在 [**原則**] 功能表上，選取 [**確認**]。</span><span class="sxs-lookup"><span data-stu-id="010bc-150">On the **Policy** menu, select **Commit**.</span></span>

    **<span data-ttu-id="010bc-151">注意</span><span class="sxs-lookup"><span data-stu-id="010bc-151">Note</span></span>**  
    <span data-ttu-id="010bc-152">只有在 [**腳本動作**] 對話方塊中將其設定為動作時，才會重新命名電腦。</span><span class="sxs-lookup"><span data-stu-id="010bc-152">The computer will be renamed only if it is set as an action in the **Script Actions** dialog box.</span></span> <span data-ttu-id="010bc-153">如需詳細資訊，請參閱[如何設定腳本動作](how-to-set-up-script-actions.md)。</span><span class="sxs-lookup"><span data-stu-id="010bc-153">For detailed information, see [How to Set Up Script Actions](how-to-set-up-script-actions.md).</span></span>



## <span data-ttu-id="010bc-154">相關主題</span><span class="sxs-lookup"><span data-stu-id="010bc-154">Related topics</span></span>


[<span data-ttu-id="010bc-155">使用 MED-V 管理主控台使用者介面</span><span class="sxs-lookup"><span data-stu-id="010bc-155">Using the MED-V Management Console User Interface</span></span>](using-the-med-v-management-console-user-interface.md)

[<span data-ttu-id="010bc-156">建立 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="010bc-156">Creating a MED-V Workspace</span></span>](creating-a-med-v-workspacemedv-10-sp1.md)

[<span data-ttu-id="010bc-157">如何設定指令碼動作</span><span class="sxs-lookup"><span data-stu-id="010bc-157">How to Set Up Script Actions</span></span>](how-to-set-up-script-actions.md)

[<span data-ttu-id="010bc-158">虛擬機器設定的範例</span><span class="sxs-lookup"><span data-stu-id="010bc-158">Examples of Virtual Machine Configurations</span></span>](examples-of-virtual-machine-configurationsv2.md)









