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
# 如何套用網路設定到 MED-V 工作區


系統管理員可以為每個 MED-V 工作區定義網路設定。

所有網路設定都在 [**網路**] 索引標籤上的 [**原則**] 模組中設定。

**將網路設定套用至 MED-V 工作區**

1.  按一下要設定的 MED-V 工作區。

2.  在 [**網路**] 窗格中，按照下表所述設定設定。

3.  在 [**原則**] 功能表上，選取 [**確認**]。

**MED-V 工作區網路屬性**

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">屬性</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>TCP/IP 屬性</p></td>
<td align="left"><ul>
<li><p><strong>使用主機的 IP 位址（NAT） </strong> —工作區將會使用 NAT 來共用主機的 ip，以進行外寄流量。</p></li>
<li><p><strong>使用與主機不同的 IP 位址（橋接器） </strong> — med-v 工作區會有自己的網路位址，通常是透過 DHCP 取得的。</p></li>
</ul>
<p>選取 <strong> </strong> 當主機電腦有多個配接器時，請選取 [將多個配接器對應到工作區] 核取方塊。 當主機在使用不同配接器的不同網路之間移動時，建議使用這個設定。</p></td>
</tr>
<tr class="even">
<td align="left"><p>DNS 伺服器</p></td>
<td align="left"><ul>
<li><p><strong>不會變更 </strong> ：在 med-v 工作區虛擬機器中設定的 DNS 設定將不會變更。</p></li>
<li><p><strong>使用主機的 DNS 位址 </strong> ： med-v 工作區 dns 設定將會同步處理，以符合主機的設定。 DNS 同步處理是動態的。 它會定期與主機進行同步處理，以便在主機上變更它時，它會在 MED-V 工作區中動態變更。</p></li>
<li><p><strong>使用特定的 DNS 位址 </strong> ： med-v 工作區會根據指定使用特定的 dns。</p>
<p>在 <strong> 主要 </strong> 和 <strong> 次要欄位中 </strong> ，輸入主要和次要的 DNS 位址。</p>
<p>選取 [ <strong> 附加主機的 DNS 位址] </strong> 核取方塊，將主機附加到已設定的 DNS 位址。</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>指派 DNS 尾碼</p></td>
<td align="left"><ul>
<li><p><strong>指派下列尾碼 </strong> ：選取此核取方塊以指派特定的 DNS 尾碼; 在方塊中，輸入以逗號分隔的尾碼或多個尾碼。</p></li>
<li><p><strong>[附加主機尾碼] </strong> -選取此核取方塊即可將主機尾碼附加到 DNS 位址。</p></li>
</ul></td>
</tr>
</tbody>
</table>

 

## 相關主題


[建立 MED-V 工作區](creating-a-med-v-workspacemedv-10-sp1.md)

[使用 MED-V 管理主控台使用者介面](using-the-med-v-management-console-user-interface.md)

 

 





