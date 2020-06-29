---
title: 如何設定 MED-V 工作區的虛擬機器設定
description: 如何設定 MED-V 工作區的虛擬機器設定
author: dansimp
ms.assetid: 50bbf58b-842c-4b63-bb93-3783903f6c7d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d0ba24f0e9aa5befeaf385acf06273a53feaae29
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812135"
---
# <span data-ttu-id="f8483-103">如何設定 MED-V 工作區的虛擬機器設定</span><span class="sxs-lookup"><span data-stu-id="f8483-103">How to Configure the Virtual Machine Setup for a MED-V Workspace</span></span>


<span data-ttu-id="f8483-104">在 [ **VM 設定**] 索引標籤上的 [**原則**] 模組中設定所有虛擬機器設定設定設定。</span><span class="sxs-lookup"><span data-stu-id="f8483-104">All virtual machine setup configuration settings are configured in the **Policy** module, on the **VM Setup** tab.</span></span>

## <span data-ttu-id="f8483-105">如何設定持久 MED-V 工作區的虛擬機器設定</span><span class="sxs-lookup"><span data-stu-id="f8483-105">How to Configure the Virtual Machine Setup for a Persistent MED-V Workspace</span></span>


**<span data-ttu-id="f8483-106">針對持久的 MED-V 工作區設定虛擬機器設定</span><span class="sxs-lookup"><span data-stu-id="f8483-106">To configure the virtual machine setup for a persistent MED-V workspace</span></span>**

1.  <span data-ttu-id="f8483-107">按一下要設定的持久 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="f8483-107">Click a persistent MED-V workspace to be configured.</span></span>

2.  <span data-ttu-id="f8483-108">在 [**永久 VM 設定**] 區段中，按照下表所述的方式來設定屬性。</span><span class="sxs-lookup"><span data-stu-id="f8483-108">In the **Persistent VM Setup** section, configure the properties as described in the following table.</span></span>

    **<span data-ttu-id="f8483-109">注意</span><span class="sxs-lookup"><span data-stu-id="f8483-109">Note</span></span>**  
    <span data-ttu-id="f8483-110">只有在持久的 MED-V 工作區中，才能啟用持久性 VM 設定屬性。</span><span class="sxs-lookup"><span data-stu-id="f8483-110">The persistent VM setup properties are enabled only for a persistent MED-V workspace.</span></span>



3.  <span data-ttu-id="f8483-111">在 [**原則**] 功能表上，選取 [**確認**]。</span><span class="sxs-lookup"><span data-stu-id="f8483-111">On the **Policy** menu, select **Commit**.</span></span>

**<span data-ttu-id="f8483-112">持久性 VM 設定屬性</span><span class="sxs-lookup"><span data-stu-id="f8483-112">Persistent VM Setup Properties</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f8483-113">屬性</span><span class="sxs-lookup"><span data-stu-id="f8483-113">Property</span></span></th>
<th align="left"><span data-ttu-id="f8483-114">描述</span><span class="sxs-lookup"><span data-stu-id="f8483-114">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f8483-115">執行 VM 設定</span><span class="sxs-lookup"><span data-stu-id="f8483-115">Run VM Setup</span></span></p></td>
<td align="left"><p><span data-ttu-id="f8483-116">選取此核取方塊，以在第一次執行 MED-V 工作區時執行安裝程式腳本。</span><span class="sxs-lookup"><span data-stu-id="f8483-116">Select this check box to run a setup script the first time the MED-V workspace is run.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="f8483-117">[腳本編輯器]</span><span class="sxs-lookup"><span data-stu-id="f8483-117">Script Editor</span></span></p></td>
<td align="left"><p><span data-ttu-id="f8483-118">按一下以設定安裝程式腳本。</span><span class="sxs-lookup"><span data-stu-id="f8483-118">Click to configure the setup script.</span></span> <span data-ttu-id="f8483-119">如需詳細資訊，請參閱 <a href="how-to-set-up-script-actions.md" data-raw-source="[How to Set Up Script Actions](how-to-set-up-script-actions.md)"> 如何設定腳本動作 </a> 。</span><span class="sxs-lookup"><span data-stu-id="f8483-119">For more information, see <a href="how-to-set-up-script-actions.md" data-raw-source="[How to Set Up Script Actions](how-to-set-up-script-actions.md)">How to Set Up Script Actions</a>.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="f8483-120">注意</span><span class="sxs-lookup"><span data-stu-id="f8483-120">Note</span></span></strong><br/><p><span data-ttu-id="f8483-121">只有在 <strong> 選取 [執行 VM 設定腳本] 時，才會啟用此按鈕 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="f8483-121">This button is enabled only when <strong>Run VM Setup script</strong> is selected.</span></span></p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f8483-122">腳本執行時所顯示的訊息</span><span class="sxs-lookup"><span data-stu-id="f8483-122">Message displayed when script is running</span></span></p></td>
<td align="left"><p><span data-ttu-id="f8483-123">在腳本執行時要顯示的訊息。</span><span class="sxs-lookup"><span data-stu-id="f8483-123">A message to be displayed while the script is running.</span></span> <span data-ttu-id="f8483-124">如果保留空白，則會顯示預設的訊息。</span><span class="sxs-lookup"><span data-stu-id="f8483-124">If left blank, the default message is displayed.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="f8483-125">注意</span><span class="sxs-lookup"><span data-stu-id="f8483-125">Note</span></span></strong><br/><p><span data-ttu-id="f8483-126">只有在 <strong> 選取 [執行 VM 設定腳本] 時，才會啟用此欄位 </strong> 。</span><span class="sxs-lookup"><span data-stu-id="f8483-126">This field is enabled only when <strong>Run VM Setup script</strong> is checked.</span></span></p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="f8483-127">如何設定 Revertible MED-V 工作區的虛擬機器設定</span><span class="sxs-lookup"><span data-stu-id="f8483-127">How to Configure the Virtual Machine Setup for a Revertible MED-V Workspace</span></span>


**<span data-ttu-id="f8483-128">若要設定 revertible MED-V 工作區的虛擬機器設定</span><span class="sxs-lookup"><span data-stu-id="f8483-128">To configure the virtual machine setup for a revertible MED-V workspace</span></span>**

1.  <span data-ttu-id="f8483-129">按一下要設定的 revertible MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="f8483-129">Click a revertible MED-V workspace to configure.</span></span>

2.  <span data-ttu-id="f8483-130">在 [ **REVERTIBLE VM 設定**] 區段中，按照下表所述的方式來設定屬性。</span><span class="sxs-lookup"><span data-stu-id="f8483-130">In the **Revertible VM Setup** section, configure the properties as described in the following table.</span></span>

    **<span data-ttu-id="f8483-131">注意</span><span class="sxs-lookup"><span data-stu-id="f8483-131">Note</span></span>**  
    <span data-ttu-id="f8483-132">僅針對 revertible MED-V 工作區啟用 revertible VM 設定屬性。</span><span class="sxs-lookup"><span data-stu-id="f8483-132">The revertible VM setup properties are enabled only for a revertible MED-V workspace.</span></span>



3.  <span data-ttu-id="f8483-133">在 [**原則**] 功能表上，選取 [**確認**]。</span><span class="sxs-lookup"><span data-stu-id="f8483-133">On the **Policy** menu, select **Commit**.</span></span>

**<span data-ttu-id="f8483-134">Revertible VM 設定屬性</span><span class="sxs-lookup"><span data-stu-id="f8483-134">Revertible VM Setup Properties</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="f8483-135">屬性</span><span class="sxs-lookup"><span data-stu-id="f8483-135">Property</span></span></th>
<th align="left"><span data-ttu-id="f8483-136">描述</span><span class="sxs-lookup"><span data-stu-id="f8483-136">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="f8483-137">根據電腦名稱稱模式重新命名 VM</span><span class="sxs-lookup"><span data-stu-id="f8483-137">Rename the VM based on the computer name pattern</span></span></p></td>
<td align="left"><p><span data-ttu-id="f8483-138">選取此核取方塊以使用 MED-V 工作區將唯一名稱指派給每個電腦，讓您可以使用相同的 MED-V 工作區區分多部電腦。</span><span class="sxs-lookup"><span data-stu-id="f8483-138">Select this check box to assign a unique name to each computer using the MED-V workspace so that you can differentiate between multiple computers using the same MED-V workspace.</span></span></p>
<p><span data-ttu-id="f8483-139">如需設定電腦影像名稱的詳細資訊，請參閱 <a href="how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md" data-raw-source="[How to Configure VM Computer Name Pattern Properties](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md)"> 如何設定 VM 電腦名稱稱模式屬性 </a> 。</span><span class="sxs-lookup"><span data-stu-id="f8483-139">For more information on configuring computer image names, see <a href="how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md" data-raw-source="[How to Configure VM Computer Name Pattern Properties](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md)">How to Configure VM Computer Name Pattern Properties</a>.</span></span></p></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="f8483-140">相關主題</span><span class="sxs-lookup"><span data-stu-id="f8483-140">Related topics</span></span>


[<span data-ttu-id="f8483-141">使用 MED-V 管理主控台使用者介面</span><span class="sxs-lookup"><span data-stu-id="f8483-141">Using the MED-V Management Console User Interface</span></span>](using-the-med-v-management-console-user-interface.md)

[<span data-ttu-id="f8483-142">建立 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="f8483-142">Creating a MED-V Workspace</span></span>](creating-a-med-v-workspacemedv-10-sp1.md)

[<span data-ttu-id="f8483-143">虛擬機器設定的範例</span><span class="sxs-lookup"><span data-stu-id="f8483-143">Examples of Virtual Machine Configurations</span></span>](examples-of-virtual-machine-configurationsv2.md)









