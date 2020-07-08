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
# 如何設定 MED-V 工作區的虛擬機器設定


在 [ **VM 設定**] 索引標籤上的 [**原則**] 模組中設定所有虛擬機器設定設定設定。

## 如何設定持久 MED-V 工作區的虛擬機器設定


**針對持久的 MED-V 工作區設定虛擬機器設定**

1.  按一下要設定的持久 MED-V 工作區。

2.  在 [**永久 VM 設定**] 區段中，按照下表所述的方式來設定屬性。

    **注意**  
    只有在持久的 MED-V 工作區中，才能啟用持久性 VM 設定屬性。



3.  在 [**原則**] 功能表上，選取 [**確認**]。

**持久性 VM 設定屬性**

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
<td align="left"><p>執行 VM 設定</p></td>
<td align="left"><p>選取此核取方塊，以在第一次執行 MED-V 工作區時執行安裝程式腳本。</p></td>
</tr>
<tr class="even">
<td align="left"><p>[腳本編輯器]</p></td>
<td align="left"><p>按一下以設定安裝程式腳本。 如需詳細資訊，請參閱 <a href="how-to-set-up-script-actions.md" data-raw-source="[How to Set Up Script Actions](how-to-set-up-script-actions.md)"> 如何設定腳本動作 </a> 。</p>
<div class="alert">
<strong>注意</strong><br/><p>只有在 <strong> 選取 [執行 VM 設定腳本] 時，才會啟用此按鈕 </strong> 。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>腳本執行時所顯示的訊息</p></td>
<td align="left"><p>在腳本執行時要顯示的訊息。 如果保留空白，則會顯示預設的訊息。</p>
<div class="alert">
<strong>注意</strong><br/><p>只有在 <strong> 選取 [執行 VM 設定腳本] 時，才會啟用此欄位 </strong> 。</p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



## 如何設定 Revertible MED-V 工作區的虛擬機器設定


**若要設定 revertible MED-V 工作區的虛擬機器設定**

1.  按一下要設定的 revertible MED-V 工作區。

2.  在 [ **REVERTIBLE VM 設定**] 區段中，按照下表所述的方式來設定屬性。

    **注意**  
    僅針對 revertible MED-V 工作區啟用 revertible VM 設定屬性。



3.  在 [**原則**] 功能表上，選取 [**確認**]。

**Revertible VM 設定屬性**

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
<td align="left"><p>根據電腦名稱稱模式重新命名 VM</p></td>
<td align="left"><p>選取此核取方塊以使用 MED-V 工作區將唯一名稱指派給每個電腦，讓您可以使用相同的 MED-V 工作區區分多部電腦。</p>
<p>如需設定電腦影像名稱的詳細資訊，請參閱 <a href="how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md" data-raw-source="[How to Configure VM Computer Name Pattern Properties](how-to-configure-vm-computer-name-pattern-propertiesmedvv2.md)"> 如何設定 VM 電腦名稱稱模式屬性 </a> 。</p></td>
</tr>
</tbody>
</table>



## 相關主題


[使用 MED-V 管理主控台使用者介面](using-the-med-v-management-console-user-interface.md)

[建立 MED-V 工作區](creating-a-med-v-workspacemedv-10-sp1.md)

[虛擬機器設定的範例](examples-of-virtual-machine-configurationsv2.md)









