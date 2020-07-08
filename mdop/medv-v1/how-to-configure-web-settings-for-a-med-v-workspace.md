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
# 如何設定 MED-V 工作區的網頁設定


只能在舊版 Internet Explorer 中顯示，且不存在於主機作業系統中的網站，可以在 MED-V 工作區的舊版 Internet Explorer 中查看。 使用者不需要在 MED-V 工作區中開啟瀏覽器，即可查看指定的網站。 使用者可以開啟主機上的瀏覽器，並自動重新導向到 MED-V 工作區，反之亦然。

下列程式描述如何設定 MED-V 工作區的網頁流覽規則清單。 規則中包含的所有網站，都可以在 MED-V 工作區或主機上流覽，如系統管理員所定義。 所有未在規則中定義的網站，都會從要求的環境中進行流覽。 不過，您也可以將它們設定為群組，在 MED-V 工作區或主機中進行流覽。

**注意**  
網站設定僅適用于 Internet Explorer，不會套用至其他瀏覽器。



[所有網站設定] 都在 [**網頁**] 索引標籤上的 [**原則**] 模組中設定。

## 如何設定 MED-V 工作區的 Web 設定


**若要設定 MED-V 工作區的網頁設定**

1.  按一下要設定的 MED-V-V 工作區。

2.  選取 [**流覽下表中定義的 url 清單]** 核取方塊，以將使用者移至 med-v 工作區或主機內的瀏覽器，當使用者流覽至符合指定之網頁規則的 URL 時，就會重新導向使用者。

3.  按一下下列其中一項：

    -   **在工作區中**-重新導向到 med-v 工作區中的瀏覽器。

    -   **在主機中**-重新導向主機上的瀏覽器。

4.  選取 [**流覽所有其他 Url]** 核取方塊，將所有從網頁規則中排除的 url 重新導向到主機或 med-v 工作區。

5.  按一下下列其中一項：

    -   **在工作區中**-將所有其他 url 重新導向到 med-v 工作區中的瀏覽器。

    -   **在主機中**，將所有其他 url 重新導向至主機上的瀏覽器。

6.  在 [**原則**] 功能表上，選取 [**確認**]。

## 如何新增網頁規則


**新增網頁規則**

1.  選取 [**流覽下表中定義的 url 清單]** 核取方塊以啟用網頁流覽規則。

2.  按一下**新增**。

    新增網頁規則。

3.  按照下表所述，設定 [Web 規則] 屬性。

4.  在 [**原則**] 功能表上，選取 [**確認**]。

**MED-V 工作區網頁屬性**

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
<td align="left"><p>類型</p></td>
<td align="left"><ul>
<li><p><strong>[網域尾碼] </strong> ：存取以 Value 屬性中指定的尾碼結尾的任何主機位址 <strong> </strong> ，並根據在網頁流覽中設定的選項加以設定 <strong> </strong> 。</p></li>
<li><p><strong>[IP 首碼] </strong> ：在 Value 屬性所指定之前置詞的範圍內，存取任何完整或部分的 ip 位址 <strong> </strong> ，並根據在網頁流覽中設定的選項加以設定 <strong> </strong> 。</p></li>
<li><p><strong>所有本機位址 </strong> ：存取沒有 &#39; 的所有位址。 &#39; 並根據在網頁流覽中設定的選項加以設定。 <strong> </strong></p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>值</p></td>
<td align="left"><ul>
<li><p>如果在 <strong> </strong> [Type] （類型）屬性中選取了 [網域尾碼] <strong> </strong> ，請輸入網域尾碼。</p>
<div class="alert">
<strong>注意</strong><br/><ul>
<li><p>不要 &quot; * &quot; 在尾碼前輸入。</p></li>
<li><p>網域尾碼也支援別名。</p></li>
</ul>
</div>
<div>

</div></li>
<li><p>如果在 [Type] （類型）屬性中選取了 [IP 首碼] <strong> </strong> ，請輸入完整或部分的 ip 位址。</p></li>
</ul></td>
</tr>
</tbody>
</table>



## 如何刪除網頁規則


**刪除網頁規則**

1.  在**網頁**窗格中，選取要刪除的網頁規則。

2.  按一下 [**移除**]。

    該網頁規則即會被刪除。

## 相關主題


[使用 MED-V 管理主控台使用者介面](using-the-med-v-management-console-user-interface.md)

[建立 MED-V 工作區](creating-a-med-v-workspacemedv-10-sp1.md)









