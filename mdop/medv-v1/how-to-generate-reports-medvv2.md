---
title: 如何產生報告
description: 如何產生報告
author: dansimp
ms.assetid: 9f8ba28e-1993-4c11-a28a-493718051e5d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 930b7061d3e5e2fb9951d45b1422915836cbc00e
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812087"
---
# 如何產生報告


下列報告類型可以由系統管理員在 MED-V 中建立：

-   [狀態](#bkmk-generatingastatusreport)-使用 [狀態] 報告來查看所有作用中使用者的目前狀態，以及每個使用者的所有 med-v 工作區（根據已定義的一段時間）。 這包括查看目前已連線到伺服器的電腦，或者如果目前未連線的電腦、其上次連線至伺服器的日期和時間、每個電腦的狀態，以及其他相關資訊。

-   [[活動記錄](#bkmk-generatinganactivitylogreport)]-使用此報告來查看源自已定義日期範圍內特定主機或使用者的事件。

-   [錯誤記錄](#bkmk-generatinganerrorlogreport)-使用此報告來查看源自已定義日期範圍內特定主機或使用者的錯誤。

按一下適當的欄名，即可依任何資料行來排序報告結果。

您可以將欄標題拖曳到報表頂端，將報表結果分組。 拖曳多個資料列標題，將一個資料行逐一分組。

## <a href="" id="bkmk-generatingastatusreport"></a>如何產生狀態報表


**產生狀態報表**

1.  按一下 [**報告**管理] 按鈕。

2.  在 [**報表**] 模組的 [**報表類型**] 功能表上，選取 [**狀態**]，然後按一下 [**產生**]。

    [報表參數] 對話方塊隨即出現。

3.  在 [**報表參數**] 對話方塊的 [**天數**] 欄位中，輸入數位，或使用箭號來選取要包含在狀態報表中的天數，然後按一下 **[確定]**。

    即會產生狀態報表。 報表參數是在下表中定義。

**用戶端 MED-V 工作區屬性**

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
<td align="left"><p>時間</p></td>
<td align="left"><p>事件發生的日期和時間。</p>
<div class="alert">
<strong>注意</strong><br/><p>根據預設，事件會以遞減的日期順序顯示。 不過，您可以按一下 [接收時間] 欄來變更它。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>使用者名稱</p></td>
<td align="left"><p>啟動事件的使用者。</p>
<div class="alert">
<strong>注意</strong><br/><p>如果在使用者登入時發生事件，則使用者名稱為 SYSTEM。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>主機名稱</p></td>
<td align="left"><p>主機電腦的名稱。</p></td>
</tr>
<tr class="even">
<td align="left"><p>工作區名稱</p></td>
<td align="left"><p>MED-V 工作區的名稱。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>工作區電腦名稱稱</p></td>
<td align="left"><p>MED-V 工作區正在執行的電腦名稱稱。</p></td>
</tr>
<tr class="even">
<td align="left"><p>Online</p></td>
<td align="left"><p>用戶端電腦的目前狀態：</p>
<ul>
<li><p><strong>被</strong></p></li>
<li><p><strong>在 &lt; 工作區開始的日期和時間開始&gt;</strong></p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>用戶端版本</p></td>
<td align="left"><p>用戶端的版本號碼。</p></td>
</tr>
<tr class="even">
<td align="left"><p>原則版本</p></td>
<td align="left"><p>MED-V 工作區目前使用的原則版本。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>圖像名稱</p></td>
<td align="left"><p>影像的名稱。</p></td>
</tr>
<tr class="even">
<td align="left"><p>影像版本</p></td>
<td align="left"><p>MED-V 工作區目前使用的影像版本。</p>
<div class="alert">
<strong>注意</strong><br/><p>如果 MED-V 的工作區版本尚未下載到電腦上，可能會是未知的。</p>
</div>
<div>

</div></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-generatinganactivitylogreport"></a>如何產生活動記錄報告


**產生活動記錄報告**

1.  按一下 [**報告**管理] 按鈕。

    [報表] 模組隨即出現。

2.  在 [**報表**] 模組的 [**報表類型**] 功能表上，選取 [**活動記錄**]，然後按一下 [**產生**]。

3.  在 [**報表參數**] 對話方塊中，設定下列一或多個參數：

    -   **天數**—要顯示在報表中的天數。

    -   [**使用者名稱**]：您的使用者名稱包含輸入之文字的任何事件，都包含在報表中。

    -   [**主機名稱**]：包含所輸入文字的任何事件，都包含在報告中。

4.  按一下 \[確定\] ****。

    報告會在已選取事件和日期的情況下產生。 報表參數是在下表中定義。

**活動記錄報告屬性**

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
<td align="left"><p>事件識別碼</p></td>
<td align="left"><p>事件 ID。</p></td>
</tr>
<tr class="even">
<td align="left"><p>嚴重性</p></td>
<td align="left"><p><strong>資訊、錯誤、警告</strong></p></td>
</tr>
<tr class="odd">
<td align="left"><p>類別</p></td>
<td align="left"><p>報告所參照的模組。</p></td>
</tr>
<tr class="even">
<td align="left"><p>描述</p></td>
<td align="left"><p>事件的描述。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>收到時間</p></td>
<td align="left"><p>在伺服器上接收事件的日期和時間。</p>
<div class="alert">
<strong>注意</strong><br/><p>如果用戶端離線工作，伺服器會在用戶端線上時接收報告。</p>
</div>
<div>

</div>
<div class="alert">
<strong>注意</strong><br/><p>根據預設，事件會以遞減的日期順序顯示。 不過，您可以按一下 [接收時間] 欄來變更它 <strong> </strong> 。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>用戶端時間</p></td>
<td align="left"><p>根據用戶端時鐘事件發生的日期和時間。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>主機名稱</p></td>
<td align="left"><p>主機電腦的名稱。</p></td>
</tr>
<tr class="even">
<td align="left"><p>使用者名稱</p></td>
<td align="left"><p>啟動事件的使用者。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>工作區名稱</p></td>
<td align="left"><p>MED-V 工作區的名稱。</p></td>
</tr>
<tr class="even">
<td align="left"><p>工作區電腦名稱稱</p></td>
<td align="left"><p>MED-V 工作區正在執行的電腦名稱稱。</p></td>
</tr>
</tbody>
</table>



## <a href="" id="bkmk-generatinganerrorlogreport"></a>如何產生錯誤記錄報告


**產生錯誤記錄報告**

1.  按一下 [**報告**管理] 按鈕。

2.  在 [**報表**] 模組的 [**報表類型**] 功能表上，選取 [**錯誤記錄**]，然後按一下 [**產生**]。

3.  在 [**報表參數**] 對話方塊中，設定下列一或多個參數：

    -   **天數**—要顯示在報表中的天數。

    -   [**使用者名稱**]：您的使用者名稱包含輸入之文字的任何事件，都包含在報表中。

    -   [**主機名稱**]：包含所輸入文字的任何事件，都包含在報告中。

4.  按一下 \[確定\] ****。

    報告會在已選取事件和日期的情況下產生。 報表參數是在下表中定義。

**錯誤記錄報表屬性**

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
<td align="left"><p>事件識別碼</p></td>
<td align="left"><p>事件 ID。</p></td>
</tr>
<tr class="even">
<td align="left"><p>類別</p></td>
<td align="left"><p>報告所參照的模組。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>描述</p></td>
<td align="left"><p>事件的描述。</p></td>
</tr>
<tr class="even">
<td align="left"><p>收到時間</p></td>
<td align="left"><p>在伺服器上接收事件的日期和時間。</p>
<div class="alert">
<strong>注意</strong><br/><p>如果用戶端離線工作，伺服器會在用戶端線上時接收報告。</p>
</div>
<div>

</div>
<div class="alert">
<strong>注意</strong><br/><p>根據預設，事件會以遞減的日期順序顯示。 不過，您可以按一下 [接收時間] 欄來變更它 <strong> </strong> 。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>用戶端時間</p></td>
<td align="left"><p>根據用戶端時鐘事件發生的日期和時間。</p></td>
</tr>
<tr class="even">
<td align="left"><p>主機名稱</p></td>
<td align="left"><p>主機電腦的名稱。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>使用者名稱</p></td>
<td align="left"><p>啟動事件的使用者。</p></td>
</tr>
<tr class="even">
<td align="left"><p>工作區名稱</p></td>
<td align="left"><p>MED-V 工作區的名稱。</p></td>
</tr>
</tbody>
</table>











