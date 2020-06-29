---
title: 如何套用網路設定到 MED-V 工作區
description: 如何套用網路設定到 MED-V 工作區
author: dansimp
ms.assetid: 641f46b3-a56f-478a-823b-1d90aa1716b3
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 5a13227518945e74be9e4b3772af97eadbce3fc4
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811804"
---
# <span data-ttu-id="288ec-103">如何套用網路設定到 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="288ec-103">How to Apply Network Settings to a MED-V Workspace</span></span>


<span data-ttu-id="288ec-104">系統管理員可以為每個 MED-V 工作區定義網路設定。</span><span class="sxs-lookup"><span data-stu-id="288ec-104">Administrators can define the network settings for each MED-V workspace.</span></span>

<span data-ttu-id="288ec-105">所有網路設定都在 [**網路**] 索引標籤上的 [**原則**] 模組中設定。</span><span class="sxs-lookup"><span data-stu-id="288ec-105">All network settings are configured in the **Policy** module, on the **Network** tab.</span></span>

**<span data-ttu-id="288ec-106">將網路設定套用至 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="288ec-106">To apply network settings to a MED-V workspace</span></span>**

1.  <span data-ttu-id="288ec-107">按一下要設定的 MED-V 工作區。</span><span class="sxs-lookup"><span data-stu-id="288ec-107">Click the MED-V workspace to configure.</span></span>

2.  <span data-ttu-id="288ec-108">在 [**網路**] 窗格中，按照下表所述設定設定。</span><span class="sxs-lookup"><span data-stu-id="288ec-108">In the **Network** pane, configure the settings as described in the following table.</span></span>

3.  <span data-ttu-id="288ec-109">在 [**原則**] 功能表上，選取 [**確認**]。</span><span class="sxs-lookup"><span data-stu-id="288ec-109">On the **Policy** menu, select **Commit**.</span></span>

**<span data-ttu-id="288ec-110">MED-V 工作區網路屬性</span><span class="sxs-lookup"><span data-stu-id="288ec-110">MED-V Workspace Network Properties</span></span>**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><span data-ttu-id="288ec-111">屬性</span><span class="sxs-lookup"><span data-stu-id="288ec-111">Property</span></span></th>
<th align="left"><span data-ttu-id="288ec-112">描述</span><span class="sxs-lookup"><span data-stu-id="288ec-112">Description</span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><span data-ttu-id="288ec-113">TCP/IP 屬性</span><span class="sxs-lookup"><span data-stu-id="288ec-113">TCP/IP Properties</span></span></p></td>
<td align="left"><ul>
<li><p><strong><span data-ttu-id="288ec-114">使用主機的 IP 位址（NAT） </strong> —工作區將會使用 NAT 來共用主機的 ip，以進行外寄流量。</span><span class="sxs-lookup"><span data-stu-id="288ec-114">Use host's IP address (NAT)</strong>—The workspace will use NAT to share the host's IP for outgoing traffic.</span></span></p></li>
<li><p><strong><span data-ttu-id="288ec-115">使用與主機不同的 IP 位址（橋接器） </strong> — med-v 工作區會有自己的網路位址，通常是透過 DHCP 取得的。</span><span class="sxs-lookup"><span data-stu-id="288ec-115">Use different IP address than host (Bridge)</strong>—The MED-V workspace will have its own network address, usually obtained via DHCP.</span></span></p></li>
</ul>
<p><span data-ttu-id="288ec-116">選取 <strong> </strong> 當主機電腦有多個配接器時，請選取 [將多個配接器對應到工作區] 核取方塊。</span><span class="sxs-lookup"><span data-stu-id="288ec-116">Select the <strong>Map multiple adapters into Workspace</strong> check box when the host computer has multiple adapters.</span></span> <span data-ttu-id="288ec-117">當主機在使用不同配接器的不同網路之間移動時，建議使用這個設定。</span><span class="sxs-lookup"><span data-stu-id="288ec-117">It is recommended to use this configuration when the host moves between different networks using different adapters.</span></span></p></td>
</tr>
<tr class="even">
<td align="left"><p><span data-ttu-id="288ec-118">DNS 伺服器</span><span class="sxs-lookup"><span data-stu-id="288ec-118">DNS Server</span></span></p></td>
<td align="left"><ul>
<li><p><strong><span data-ttu-id="288ec-119">不會變更 </strong> ：在 med-v 工作區虛擬機器中設定的 DNS 設定將不會變更。</span><span class="sxs-lookup"><span data-stu-id="288ec-119">Don't change</strong>—DNS settings that are set within the MED-V workspace virtual machine will not be changed.</span></span></p></li>
<li><p><strong><span data-ttu-id="288ec-120">使用主機的 DNS 位址 </strong> ： med-v 工作區 dns 設定將會同步處理，以符合主機的設定。</span><span class="sxs-lookup"><span data-stu-id="288ec-120">Use Host's DNS address</strong>—MED-V workspace DNS settings will be synchronized to match the host's settings.</span></span> <span data-ttu-id="288ec-121">DNS 同步處理是動態的。</span><span class="sxs-lookup"><span data-stu-id="288ec-121">The DNS synchronization is dynamic.</span></span> <span data-ttu-id="288ec-122">它會定期與主機進行同步處理，以便在主機上變更它時，它會在 MED-V 工作區中動態變更。</span><span class="sxs-lookup"><span data-stu-id="288ec-122">It is synchronized periodically with the host so that if it is changed on the host, it will change dynamically in the MED-V workspace.</span></span></p></li>
<li><p><strong><span data-ttu-id="288ec-123">使用特定的 DNS 位址 </strong> ： med-v 工作區會根據指定使用特定的 dns。</span><span class="sxs-lookup"><span data-stu-id="288ec-123">Use specific DNS addresses</strong>—The MED-V workspace will use a specific DNS, as specified.</span></span></p>
<p><span data-ttu-id="288ec-124">在 <strong> 主要 </strong> 和 <strong> 次要欄位中 </strong> ，輸入主要和次要的 DNS 位址。</span><span class="sxs-lookup"><span data-stu-id="288ec-124">In the <strong>Primary</strong> and <strong>Secondary</strong> fields, enter the primary and secondary DNS addresses.</span></span></p>
<p><span data-ttu-id="288ec-125">選取 [ <strong> 附加主機的 DNS 位址] </strong> 核取方塊，將主機附加到已設定的 DNS 位址。</span><span class="sxs-lookup"><span data-stu-id="288ec-125">Select the <strong>Append Host's DNS addresses</strong> check box to append the host to the configured DNS addresses.</span></span></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p><span data-ttu-id="288ec-126">指派 DNS 尾碼</span><span class="sxs-lookup"><span data-stu-id="288ec-126">Assign DNS Suffixes</span></span></p></td>
<td align="left"><ul>
<li><p><strong><span data-ttu-id="288ec-127">指派下列尾碼 </strong> ：選取此核取方塊以指派特定的 DNS 尾碼; 在方塊中，輸入以逗號分隔的尾碼或多個尾碼。</span><span class="sxs-lookup"><span data-stu-id="288ec-127">Assign the following suffixes</strong>—Select this check box to assign specific DNS suffixes; in the box, enter a suffix or multiple suffixes separated by commas.</span></span></p></li>
<li><p><strong><span data-ttu-id="288ec-128">[附加主機尾碼] </strong> -選取此核取方塊即可將主機尾碼附加到 DNS 位址。</span><span class="sxs-lookup"><span data-stu-id="288ec-128">Append host suffixes</strong>—Select this check box to append the host suffixes to the DNS address.</span></span></p></li>
</ul></td>
</tr>
</tbody>
</table>

 

## <span data-ttu-id="288ec-129">相關主題</span><span class="sxs-lookup"><span data-stu-id="288ec-129">Related topics</span></span>


[<span data-ttu-id="288ec-130">建立 MED-V 工作區</span><span class="sxs-lookup"><span data-stu-id="288ec-130">Creating a MED-V Workspace</span></span>](creating-a-med-v-workspacemedv-10-sp1.md)

[<span data-ttu-id="288ec-131">使用 MED-V 管理主控台使用者介面</span><span class="sxs-lookup"><span data-stu-id="288ec-131">Using the MED-V Management Console User Interface</span></span>](using-the-med-v-management-console-user-interface.md)

 

 





