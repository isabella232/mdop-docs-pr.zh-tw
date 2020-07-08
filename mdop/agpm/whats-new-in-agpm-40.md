---
title: AGPM 4.0 的新功能
description: AGPM 4.0 的新功能
author: dansimp
ms.assetid: 31775f7f-a59c-4e64-a875-0adc9f5bc835
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 82b4445a7d22fb7c1ef4f42d896f11908a22f2f5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802482"
---
# AGPM 4.0 的新功能


Microsoft 高級群組原則管理（AGPM）4.0 包含新功能，可讓您搜尋群組原則物件（Gpo）、篩選所顯示的 Gpo 清單、匯出及匯入 GPO 至不同的林中，以及在執行 Windows7 和 Windows Server2008R2 的電腦上安裝 AGPM。

## 搜尋和篩選 Gpo


在 AGPM 4.0 中，您可以在 Gpo 清單中搜尋特定屬性，以篩選所顯示之 Gpo 的清單。 例如，您可以搜尋具有特定名稱、狀態或批註的 Gpo。 您也可以搜尋由特定群組原則系統管理員或特定日期所變更的 Gpo。

您可以使用 [格式化*GPO 屬性1：搜尋文字 1 GPO 屬性2：搜尋文字 2 ...*]，其中 gpo 屬性是 AGPM 中 gpo 清單中的任何欄標題。 例如，若要搜尋包含已取出且由使用者 Editor03 最後變更之文字「MyGPO」的所有 Gpo，您可以在 [搜尋] 方塊中輸入下列內容： **name： MyGPO state：** 已依下列方式**核**取 **： Editor03**。 搜尋會傳回部分相符的專案，讓您輸入部分的 GPO 名稱或使用者名稱，並查看其名稱中包含該文字的所有 Gpo 的清單。

此外，您也可以使用在 Windows 中搜尋時所提供的相同特殊字詞，在特定日期或日期範圍內搜尋 Gpo 已變更。 例如，[**變更日期：****lastmonth** ] 或 [**變更日期]：****thisweek**。

## 匯出及匯入 Gpo 至不同的林


您可以使用 AGPM 4.0，將受控的 GPO 從一個目錄林中的網域複製到第二個林中的網域。 例如，您可以使用 AGPM 將 GPO 從某個林中的網域匯出到 CAB 檔案，然後將該 CAB 檔案複製到 USB 磁片磁碟機，將 USB 磁片磁碟機插入第二個目錄林中網域中的電腦，然後將該 GPO 匯入到第二個目錄林中網域的 AGPM 中。 您可以將 GPO 匯入為新的受控 GPO，或將它匯入以取代已取出之現有 GPO 的設定。

## Windows Server 2008 R2 和 Windows 7 的支援


AGPM 4.0 支援 Windows Server2008R2 和 Windows7，但仍支援 Windows Server2008，且 WindowsVista Service Pack1 （SP1）®。 不過，混合環境會有一些限制，包括較新及較舊的作業系統，如下表所示。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">在其上執行 AGPM Server 4.0 的作業系統</th>
<th align="left">在其上執行 AGPM 用戶端4.0 的作業系統</th>
<th align="left">AGPM 4.0 支援的狀態</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>支援</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>Windows Server2008 或 Windows Vista （含 SP1）</p></td>
<td align="left"><p>支援，但無法編輯僅存在於 Windows Server2008R2 或 Windows7 的原則設定或喜好設定專案</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Windows Server2008 或 Windows Vista （含 SP1）</p></td>
<td align="left"><p>Windows Server2008R2 或 Windows7</p></td>
<td align="left"><p>不支援</p></td>
</tr>
<tr class="even">
<td align="left"><p>Windows Server2008 或 Windows Vista （含 SP1）</p></td>
<td align="left"><p>Windows Server2008 或 Windows Vista （含 SP1）</p></td>
<td align="left"><p>支援，但無法報告或編輯僅存在於 Windows Server2008R2 或 Windows7 的原則設定或喜好設定專案</p></td>
</tr>
</tbody>
</table>

 

 

 





