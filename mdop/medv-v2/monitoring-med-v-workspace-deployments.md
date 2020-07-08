---
title: 監控 MED-V 工作區部署
description: 監控 MED-V 工作區部署
author: dansimp
ms.assetid: 5de0cb06-b8a9-48a5-b8b3-836954295765
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 6ec4c7c85326e7945aa3d61b7f96872afe24fe37
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10812219"
---
# 監控 MED-V 工作區部署


Microsoft 企業桌面虛擬化（MED-V）2.0 中的 [監視] 功能可讓您在個別的 MED-V 工作區上執行查詢，以判斷在部署 MED-V 工作區之後，是否要讓整個企業中的第一次都成功完成設定。 監控第一次設定的成功與否，是因為 MED-V 在第一次成功完成之前並不是使用中的狀態。

本節提供資訊與指示，協助您監控第一次設定的成功或失敗。

## 監視 MED-V 工作區部署


[監視] 功能是由結合的進程內 Windows 管理規範（WMI）提供者所組成，您可以使用 WMI 查詢語言來查詢，以探索 MED-V 工作區中所有最終使用者的第一次設定狀態。

WMI 提供者是使用來自 Microsoft .Net Framework 3.5 的 WMI 提供程式擴充架構來實現。 WMI 提供者會在 LocalService 的內容中執行，並在 \\ProgramData. 下安全地儲存第一次設定狀態。

WMI 提供者是在**root\\microsoft\\medv**命名空間中實現，並實現 class **FTS \ _Status**，這會公開方法**SetFtsState**。 MED-V 會使用**SetFtsState**來設定第一次設定狀態。

此類別包含下列屬性。

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
<td align="left"><p><strong>電腦</strong></p></td>
<td align="left"><p><strong>[唯讀] </strong> 屬性，包含由第一次設定所配的來賓虛擬機器名稱。 此金鑰包含來賓在第一次設定失敗時所擁有的名稱。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>StatusCode</strong></p></td>
<td align="left"><p><strong></strong>第一次設定成功時，包含零的唯讀屬性。 傳回的任何其他值都等於記錄之錯誤的事件 ID。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>時間</strong></p></td>
<td align="left"><p>第一次設定完成時的 UTC 時間。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>使用者</strong></p></td>
<td align="left"><p>第一次執行設定的使用者。</p></td>
</tr>
</tbody>
</table>

 

下列程式碼會顯示定義**FTS \ _Status**類別的 Managed 物件格式（MOF）檔案。

``` syntax
[dynamic: ToInstance, provider("MedvWmi, Version=2.0.258.0, Culture=neutral, PublicKeyToken=14986c3f172d1c2c")]
class FTS_Status
{
[read, key] string User;
[read] string Machine;
[read] sint32 StatusCode;
[read] datetime Time;
[static, implemented] void SetFtsState([in] sint32 statusCode, [in] string machine);
};
```

因為您主要關心的是那些第一次未成功完成設定的 MED-V 工作區，所以您可以撰寫您的查詢，只返回那些第一次設定失敗的專案，例如：

``` syntax
Select * from FTS_Status where StatusCode != 0
```

在這種情況下，[監視] 功能會傳回那些第一次設定失敗的那些 MED-V 工作區清單，您可以用來採取適當的動作來解決失敗。

## 相關主題


[監控 MED-V 工作區](monitor-med-v-workspaces.md)

[如何驗證第一次安裝設定](how-to-verify-first-time-setup-settings.md)

 

 





