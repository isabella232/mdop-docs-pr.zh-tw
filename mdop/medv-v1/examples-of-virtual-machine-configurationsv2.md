---
title: 虛擬機器設定的範例
description: 虛擬機器設定的範例
author: dansimp
ms.assetid: 5937601e-41ab-4ca2-8fa1-3c9154710cd6
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6b9fc7b1f88b2b30ea149fe73a387826fdbb2a66
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810646"
---
# <span data-ttu-id="bfe53-103">虛擬機器設定的範例</span><span class="sxs-lookup"><span data-stu-id="bfe53-103">Examples of Virtual Machine Configurations</span></span>


<span data-ttu-id="bfe53-104">下列是典型的虛擬機器配置範例：一個是在持久性的 MED-V 工作區，另一個是在 revertible MED-V 工作區中。</span><span class="sxs-lookup"><span data-stu-id="bfe53-104">The following are examples of typical virtual machine configurations: one in a persistent MED-V workspace and one in a revertible MED-V workspace.</span></span>

<span data-ttu-id="bfe53-105">**記事** 這些範例不適合在所有環境中使用。</span><span class="sxs-lookup"><span data-stu-id="bfe53-105">**Note** These examples are not intended for use in all environments.</span></span> <span data-ttu-id="bfe53-106">根據您的環境調整設定。</span><span class="sxs-lookup"><span data-stu-id="bfe53-106">Adjust the configuration according to your environment.</span></span>

 

**<span data-ttu-id="bfe53-107">在持久的 MED-V 工作區中設定一般的網域設定</span><span class="sxs-lookup"><span data-stu-id="bfe53-107">To configure a typical domain setup in a persistent MED-V workspace</span></span>**

1.  <span data-ttu-id="bfe53-108">在基本映射上設定 Sysprep，以建立唯一的 SID。</span><span class="sxs-lookup"><span data-stu-id="bfe53-108">Configure Sysprep on the base image to create a unique SID.</span></span> <span data-ttu-id="bfe53-109">如需詳細資訊，請參閱[建立 med-v 的虛擬電腦影像](creating-a-virtual-pc-image-for-med-v.md#bkmk-howtoconfiguresysprepformedvimages)。</span><span class="sxs-lookup"><span data-stu-id="bfe53-109">For more information, see [Creating a Virtual PC Image for MED-V](creating-a-virtual-pc-image-for-med-v.md#bkmk-howtoconfiguresysprepformedvimages).</span></span>

2.  <span data-ttu-id="bfe53-110">在 [ **VM 設定**] 索引標籤上，選取 [**執行 VM 設定**] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="bfe53-110">On the **VM Setup** tab, select the **Run VM Setup** check box.</span></span>

3.  <span data-ttu-id="bfe53-111">在 [ **VM 電腦名稱稱模式**] 區段中，設定電腦影像名稱的模式。</span><span class="sxs-lookup"><span data-stu-id="bfe53-111">In the **VM Computer Name Pattern** section, configure the pattern for the machine image name.</span></span> <span data-ttu-id="bfe53-112">如需詳細資訊，請參閱[如何設定 VM 電腦名稱稱模式屬性](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md)。</span><span class="sxs-lookup"><span data-stu-id="bfe53-112">For more information, see [How to Configure VM Computer Name Pattern Properties](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md).</span></span>

4.  <span data-ttu-id="bfe53-113">按一下 [**腳本編輯器**]，然後在 [ **VM 設定腳本編輯器**] 對話方塊中，設定下列動作：</span><span class="sxs-lookup"><span data-stu-id="bfe53-113">Click **Script Editor**, and in the **VM Setup Script Editor** dialog box, configure the following actions:</span></span>

    1.  **<span data-ttu-id="bfe53-114">重新命名電腦</span><span class="sxs-lookup"><span data-stu-id="bfe53-114">Rename Computer</span></span>**

    2.  **<span data-ttu-id="bfe53-115">重新開機 Windows</span><span class="sxs-lookup"><span data-stu-id="bfe53-115">Restart Windows</span></span>**

    3.  **<span data-ttu-id="bfe53-116">檢查連線性</span><span class="sxs-lookup"><span data-stu-id="bfe53-116">Check Connectivity</span></span>**

    4.  **<span data-ttu-id="bfe53-117">加入網域</span><span class="sxs-lookup"><span data-stu-id="bfe53-117">Join Domain</span></span>**

    5.  **<span data-ttu-id="bfe53-118">停用自動登入</span><span class="sxs-lookup"><span data-stu-id="bfe53-118">Disable Auto-Logon</span></span>**

    <span data-ttu-id="bfe53-119">如需詳細資訊，請參閱[如何設定腳本動作](how-to-set-up-script-actions.md)。</span><span class="sxs-lookup"><span data-stu-id="bfe53-119">For more information, see [How to Set Up Script Actions](how-to-set-up-script-actions.md).</span></span>

5.  <span data-ttu-id="bfe53-120">按一下 [**原則**] 功能表上的 [**確認**]。</span><span class="sxs-lookup"><span data-stu-id="bfe53-120">On the **Policy** menu, click **Commit**.</span></span>

**<span data-ttu-id="bfe53-121">在 revertible 工作區中設定典型設定</span><span class="sxs-lookup"><span data-stu-id="bfe53-121">To configure a typical setup in a revertible workspace</span></span>**

1.  <span data-ttu-id="bfe53-122">在 [ **VM 設定**] 索引標籤上，選取 [**根據電腦名稱稱模式重新命名 VM** ] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="bfe53-122">On the **VM Setup** tab, select the **Rename the VM based on the computer name pattern** check box.</span></span>

2.  <span data-ttu-id="bfe53-123">在 [ **VM 電腦名稱稱模式**] 區段中，設定電腦影像名稱的模式。</span><span class="sxs-lookup"><span data-stu-id="bfe53-123">In the **VM Computer Name Pattern** section, configure the pattern for the machine image name.</span></span> <span data-ttu-id="bfe53-124">如需詳細資訊，請參閱[如何設定 VM 電腦名稱稱模式屬性](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md)。</span><span class="sxs-lookup"><span data-stu-id="bfe53-124">For more information, see [How to Configure VM Computer Name Pattern Properties](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md).</span></span>

3.  <span data-ttu-id="bfe53-125">按一下 [**原則**] 功能表上的 [**確認**]。</span><span class="sxs-lookup"><span data-stu-id="bfe53-125">On the **Policy** menu, click **Commit**.</span></span>

## <span data-ttu-id="bfe53-126">相關主題</span><span class="sxs-lookup"><span data-stu-id="bfe53-126">Related topics</span></span>


[<span data-ttu-id="bfe53-127">如何設定 MED-V 工作區的虛擬機器設定</span><span class="sxs-lookup"><span data-stu-id="bfe53-127">How to Configure the Virtual Machine Setup for a MED-V Workspace</span></span>](how-to-configure-the-virtual-machine-setup-for-a-med-v-workspacemedvv2.md)

[<span data-ttu-id="bfe53-128">如何設定 VM 電腦名稱模式內容</span><span class="sxs-lookup"><span data-stu-id="bfe53-128">How to Configure VM Computer Name Pattern Properties</span></span>](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md)

[<span data-ttu-id="bfe53-129">如何設定指令碼動作</span><span class="sxs-lookup"><span data-stu-id="bfe53-129">How to Set Up Script Actions</span></span>](how-to-set-up-script-actions.md)

 

 





