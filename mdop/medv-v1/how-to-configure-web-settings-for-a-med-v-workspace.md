---
title: 如何設定 MED-V 工作區的網頁設定
description: 如何設定 MED-V 工作區的網頁設定
author: dansimp
ms.assetid: 9a6cd28f-7e4f-468f-830a-7b1d9abd3af3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 770d3fa9a03c9754db86ca348390d0b916de6d5d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812134"
---
# <span data-ttu-id="86d9c-103">如何設定 MED-V 工作區的網頁設定</span><span class="sxs-lookup"><span data-stu-id="86d9c-103">How to Configure Web Settings for a MED-V Workspace</span></span>


<span data-ttu-id="86d9c-104">只能在舊版 Internet Explorer 中顯示，且不存在於主機作業系統中的網站，可以在 MED-V 工作區的舊版 Internet Explorer 中查看。</span><span class="sxs-lookup"><span data-stu-id="86d9c-104">Web sites that can only be displayed in older versions of Internet Explorer and that do not exist in the host operating system can be viewed in older versions of Internet Explorer within the MED-V workspace.</span></span> <span data-ttu-id="86d9c-105">使用者不需要在 MED-V 工作區中開啟瀏覽器，即可查看指定的網站。</span><span class="sxs-lookup"><span data-stu-id="86d9c-105">The user does not need to open a browser in the MED-V workspace to view the specified Web sites.</span></span> <span data-ttu-id="86d9c-106">使用者可以開啟主機上的瀏覽器，並自動重新導向到 MED-V 工作區，反之亦然。</span><span class="sxs-lookup"><span data-stu-id="86d9c-106">The user can open a browser on the host and automatically be redirected to the MED-V workspace and vice versa.</span></span>

<span data-ttu-id="86d9c-107">下列程式描述如何設定 MED-V 工作區的網頁流覽規則清單。</span><span class="sxs-lookup"><span data-stu-id="86d9c-107">The following procedures describe how you can set a list of Web browsing rules for a MED-V workspace.</span></span> <span data-ttu-id="86d9c-108">規則中包含的所有網站，都可以在 MED-V 工作區或主機上流覽，如系統管理員所定義。</span><span class="sxs-lookup"><span data-stu-id="86d9c-108">All sites included in the rules can be browsed either in the MED-V workspace or on the host, as defined by the administrator.</span></span> <span data-ttu-id="86d9c-109">所有未在規則中定義的網站，都會從要求的環境中進行流覽。</span><span class="sxs-lookup"><span data-stu-id="86d9c-109">All sites not defined within the rules are browsed from the environment in which they were requested.</span></span> <span data-ttu-id="86d9c-110">不過，您也可以將它們設定為群組，在 MED-V 工作區或主機中進行流覽。</span><span class="sxs-lookup"><span data-stu-id="86d9c-110">However, you can configure them as a group as well, to be browsed in the MED-V workspace or the host.</span></span>

**<span data-ttu-id="86d9c-111">注意</span><span class="sxs-lookup"><span data-stu-id="86d9c-111">Note</span></span>**  
<span data-ttu-id="86d9c-112">網站設定僅適用于 Internet Explorer，不會套用至其他瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="86d9c-112">Web settings are applied only to Internet Explorer and to no other browsers.</span></span>



<span data-ttu-id="86d9c-113">[所有網站設定] 都在 [**網頁**] 索引標籤上的 [**原則**] 模組中設定。</span><span class="sxs-lookup"><span data-stu-id="86d9c-113">All Web settings are configured in the **Policy** module, on the **Web** tab.</span></span>

## <span data-ttu-id="86d9c-114">如何設定 MED-V 工作區的 Web 設定</span><span class="sxs-lookup"><span data-stu-id="86d9c-114">How to Configure Web Settings for the MED-V Workspace</span></span>


**<span data-ttu-id="86d9c-115">若要設定 MED-V 工作區的網頁設定</span><span class="sxs-lookup"><span data-stu-id="86d9c-115">To configure Web settings for the MED-V workspace</span></span>**

1.  <span data-ttu-id="86d9c-116">按一下要設定的 MED-V-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="86d9c-116">Click the MED-V workspace to be configured.</span></span>

2.  <span data-ttu-id="86d9c-117">選取 [**流覽下表中定義的 url 清單]** 核取方塊，以將使用者移至 med-v 工作區或主機內的瀏覽器，當使用者流覽至符合指定之網頁規則的 URL 時，就會重新導向使用者。</span><span class="sxs-lookup"><span data-stu-id="86d9c-117">Select the **Browse the list of URLs defined in the following table** check box to redirect the user to a browser within the MED-V workspace or host, when the user browses to a URL that conforms to the Web rules specified.</span></span>

3.  <span data-ttu-id="86d9c-118">按一下下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="86d9c-118">Click one of the following:</span></span>

    -   <span data-ttu-id="86d9c-119">**在工作區中**-重新導向到 med-v 工作區中的瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="86d9c-119">**In the Workspace**—Redirect to a browser in the MED-V workspace.</span></span>

    -   <span data-ttu-id="86d9c-120">**在主機中**-重新導向主機上的瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="86d9c-120">**In the host**—Redirect to a browser on the host.</span></span>

4.  <span data-ttu-id="86d9c-121">選取 [**流覽所有其他 Url]** 核取方塊，將所有從網頁規則中排除的 url 重新導向到主機或 med-v 工作區。</span><span class="sxs-lookup"><span data-stu-id="86d9c-121">Select the **Browse all other URLs** check box to redirect all URLs excluded from the Web rules to the host or MED-V workspace.</span></span>

5.  <span data-ttu-id="86d9c-122">按一下下列其中一項：</span><span class="sxs-lookup"><span data-stu-id="86d9c-122">Click one of the following:</span></span>

    -   <span data-ttu-id="86d9c-123">**在工作區中**-將所有其他 url 重新導向到 med-v 工作區中的瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="86d9c-123">**In the Workspace**—Redirect all other URLs to a browser in the MED-V workspace.</span></span>

    -   <span data-ttu-id="86d9c-124">**在主機中**，將所有其他 url 重新導向至主機上的瀏覽器。</span><span class="sxs-lookup"><span data-stu-id="86d9c-124">**In the host**—Redirect all other URLs to a browser on the host.</span></span>

6.  <span data-ttu-id="86d9c-125">在 [**原則**] 功能表上，選取 [**確認**]。</span><span class="sxs-lookup"><span data-stu-id="86d9c-125">On the **Policy** menu, select **Commit**.</span></span>

## <span data-ttu-id="86d9c-126">如何新增網頁規則</span><span class="sxs-lookup"><span data-stu-id="86d9c-126">How to Add a Web Rule</span></span>


**<span data-ttu-id="86d9c-127">新增網頁規則</span><span class="sxs-lookup"><span data-stu-id="86d9c-127">To add a Web rule</span></span>**

1.  <span data-ttu-id="86d9c-128">選取 [**流覽下表中定義的 url 清單]** 核取方塊以啟用網頁流覽規則。</span><span class="sxs-lookup"><span data-stu-id="86d9c-128">Select the **Browse the list of URLs defined in the following table** check box to enable the Web browsing rules.</span></span>

2.  <span data-ttu-id="86d9c-129">按一下**新增**。</span><span class="sxs-lookup"><span data-stu-id="86d9c-129">Click **Add**.</span></span>

    <span data-ttu-id="86d9c-130">新增網頁規則。</span><span class="sxs-lookup"><span data-stu-id="86d9c-130">A new Web rule is added.</span></span>

3.  <span data-ttu-id="86d9c-131">按照下表所述，設定 [Web 規則] 屬性。</span><span class="sxs-lookup"><span data-stu-id="86d9c-131">Configure the Web rule properties as described in the following table.</span></span>

4.  <span data-ttu-id="86d9c-132">在 [**原則**] 功能表上，選取 [**確認**]。</span><span class="sxs-lookup"><span data-stu-id="86d9c-132">On the **Policy** menu, select **Commit**.</span></span>

**<span data-ttu-id="86d9c-133">MED-V 工作區網頁屬性</span><span class="sxs-lookup"><span data-stu-id="86d9c-133">MED-V Workspace Web Properties</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="86d9c-134">屬性</span><span class="sxs-lookup"><span data-stu-id="86d9c-134">Property</span></span></th>
<th align="left"><span data-ttu-id="86d9c-135">描述</span><span class="sxs-lookup"><span data-stu-id="86d9c-135">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="86d9c-136">類型</span><span class="sxs-lookup"><span data-stu-id="86d9c-136">Type</span></span></p></td>
<td align="left"><ul>
<li><p><strong><span data-ttu-id="86d9c-137">[網域尾碼] </strong> ：存取以 Value 屬性中指定的尾碼結尾的任何主機位址 <strong> </strong> ，並根據在網頁流覽中設定的選項加以設定 <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="86d9c-137">Domain suffix</strong>—Access to any host address ending with the suffix specified in the <strong>Value</strong> property and is set according to the option set in <strong>Web Browsing</strong>.</span></span></p></li>
<li><p><strong><span data-ttu-id="86d9c-138">[IP 首碼] </strong> ：在 Value 屬性所指定之前置詞的範圍內，存取任何完整或部分的 ip 位址 <strong> </strong> ，並根據在網頁流覽中設定的選項加以設定 <strong> </strong> 。</span><span class="sxs-lookup"><span data-stu-id="86d9c-138">IP Prefix</strong>—Access to any full or partial IP address in the range of the prefix specified in the <strong>Value</strong> property and is set according to the option set in <strong>Web Browsing</strong>.</span></span></p></li>
<li><p><strong><span data-ttu-id="86d9c-139">所有本機位址 </strong> ：存取沒有 &#39; 的所有位址。 &#39; 並根據在網頁流覽中設定的選項加以設定。 <strong> </strong></span><span class="sxs-lookup"><span data-stu-id="86d9c-139">All Local Addresses</strong>—Access to all addresses without a &#39;.&#39; and is set according to the option set in <strong>Web Browsing</strong>.</span></span></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="86d9c-140">值</span><span class="sxs-lookup"><span data-stu-id="86d9c-140">Value</span></span></p></td>
<td align="left"><ul>
<li><p><span data-ttu-id="86d9c-141">如果在 <strong> </strong> [Type] （類型）屬性中選取了 [網域尾碼] <strong> </strong> ，請輸入網域尾碼。</span><span class="sxs-lookup"><span data-stu-id="86d9c-141">If <strong>Domain suffix</strong> is selected in the <strong>Type</strong> property, enter a domain suffix.</span></span></p>
<div class="alert">
<strong><span data-ttu-id="86d9c-142">注意</span><span class="sxs-lookup"><span data-stu-id="86d9c-142">Note</span></span></strong><br/><ul>
<li><p><span data-ttu-id="86d9c-143">不要 &quot; \* &quot; 在尾碼前輸入。</span><span class="sxs-lookup"><span data-stu-id="86d9c-143">Do not enter &quot;\*&quot; before the suffix.</span></span></p></li>
<li><p><span data-ttu-id="86d9c-144">網域尾碼也支援別名。</span><span class="sxs-lookup"><span data-stu-id="86d9c-144">Domain suffixes support aliases as well.</span></span></p></li>
</ul>
</div>
<div>

</div></li>
<li><p><span data-ttu-id="86d9c-145">如果在 [Type] （類型）屬性中選取了 [IP 首碼] <strong> </strong> ，請輸入完整或部分的 ip 位址。</span><span class="sxs-lookup"><span data-stu-id="86d9c-145">If IP Prefix is selected in the <strong>Type</strong> property, enter a full or partial IP address.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>



## <span data-ttu-id="86d9c-146">如何刪除網頁規則</span><span class="sxs-lookup"><span data-stu-id="86d9c-146">How to Delete a Web Rule</span></span>


**<span data-ttu-id="86d9c-147">刪除網頁規則</span><span class="sxs-lookup"><span data-stu-id="86d9c-147">To delete a Web rule</span></span>**

1.  <span data-ttu-id="86d9c-148">在**網頁**窗格中，選取要刪除的網頁規則。</span><span class="sxs-lookup"><span data-stu-id="86d9c-148">In the **Web** pane, select the Web rule to delete.</span></span>

2.  <span data-ttu-id="86d9c-149">按一下 [**移除**]。</span><span class="sxs-lookup"><span data-stu-id="86d9c-149">Click **Remove**.</span></span>

    <span data-ttu-id="86d9c-150">該網頁規則即會被刪除。</span><span class="sxs-lookup"><span data-stu-id="86d9c-150">The Web rule is deleted.</span></span>

## <span data-ttu-id="86d9c-151">相關主題</span><span class="sxs-lookup"><span data-stu-id="86d9c-151">Related topics</span></span>


[<span data-ttu-id="86d9c-152">使用 MED-V 管理主控台使用者介面</span><span class="sxs-lookup"><span data-stu-id="86d9c-152">Using the MED-V Management Console User Interface</span></span>](using-the-med-v-management-console-user-interface.md)

[<span data-ttu-id="86d9c-153">建立 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="86d9c-153">Creating a MED-V Workspace</span></span>](creating-a-med-v-workspacemedv-10-sp1.md)









