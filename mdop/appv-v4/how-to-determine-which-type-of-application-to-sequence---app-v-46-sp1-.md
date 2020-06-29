---
title: 如何判斷要順序的應用程式類型（App-v 4.6 SP1）
description: 如何判斷要順序的應用程式類型（App-v 4.6 SP1）
author: dansimp
ms.assetid: 936abee2-98f1-45fb-9f0d-786e1d7464b1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 001f6afa36ca28eb1b8e0cc2ccc161cef4194d24
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801437"
---
# 如何判斷要順序的應用程式類型（App-v 4.6 SP1）


您可以使用 Microsoft Application Virtualization （App-v） Sequencer 來排列三種基本類型的應用程式。

## 若要判斷要排序的應用程式類型


使用下表來判斷您應該序列化的應用程式類型，並取得如何為應用程式排序的詳細資訊。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">應用程式類型</th>
<th align="left">描述</th>
<th align="left">其他資訊</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Standard</p></td>
<td align="left"><p>選取此選項以建立包含應用程式或應用程式套件的套件。 您應該針對您打算順序的大部分應用程式選取此選項。</p></td>
<td align="left"><p><a href="how-to-sequence-a-new-standard-application--app-v-46-sp1-.md" data-raw-source="[How to Sequence a New Standard Application (App-V 4.6 SP1)](how-to-sequence-a-new-standard-application--app-v-46-sp1-.md)">如何排序新的標準應用程式 (App-V 4.6 SP1)</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>附加元件或外掛程式</p></td>
<td align="left"><p>選取此選項以建立可擴展標準應用程式功能的套件，例如 Microsoft Excel 的外掛程式。 此外，您也可以使用本機安裝應用程式的外掛程式，或是使用動態套件組合連結的其他套件。 如需有關動態套件組合的詳細資訊，請參閱 <a href="https://go.microsoft.com/fwlink/?LinkId=203804" data-raw-source="[How To Use Dynamic Suite Composition](https://go.microsoft.com/fwlink/?LinkId=203804)"> 如何使用動態套件組合 </a> （ <a href="https://go.microsoft.com/fwlink/?LinkId=203804" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=203804"> https://go.microsoft.com/fwlink/?LinkId=203804 </a> ）。</p></td>
<td align="left"><p><a href="how-to-sequence-a-new-add-on-or-plug-in-application--app-v-46-sp1-.md" data-raw-source="[How to Sequence a New Add-on or Plug-in Application (App-V 4.6 SP1)](how-to-sequence-a-new-add-on-or-plug-in-application--app-v-46-sp1-.md)">如何排序新附加元件或外掛應用程式 (App-V 4.6 SP1)</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>中介軟體</p></td>
<td align="left"><p>選取此選項以建立標準應用程式所需的套件，例如 Microsoft .NET Framework。 中介軟體套件是使用動態套件組合來連結到其他套件。 如需有關動態套件組合的詳細資訊，請參閱 <a href="https://go.microsoft.com/fwlink/?LinkId=203804" data-raw-source="[How To Use Dynamic Suite Composition](https://go.microsoft.com/fwlink/?LinkId=203804)"> 如何使用動態套件組合 </a> （ <a href="https://go.microsoft.com/fwlink/?LinkId=203804" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=203804"> https://go.microsoft.com/fwlink/?LinkId=203804 </a> ）。</p></td>
<td align="left"><p><a href="how-to-sequence-a-new-middleware-application--app-v-46-sp1-.md" data-raw-source="[How to Sequence a New Middleware Application (App-V 4.6 SP1)](how-to-sequence-a-new-middleware-application--app-v-46-sp1-.md)">如何排序新的中介軟體應用程式 (App-V 4.6 SP1)</a></p></td>
</tr>
</tbody>
</table>

 

## 相關主題


[Application Virtualization Sequencer 的工作 (App-V 4.6 SP1)](tasks-for-the-application-virtualization-sequencer--app-v-46-sp1-.md)

 

 





