---
title: 判斷裝置為何收到不合規的訊息
description: 判斷裝置為何收到不合規的訊息
author: dansimp
ms.assetid: 793df330-a0ee-4759-b53a-95618ac74428
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 08/22/2017
ms.openlocfilehash: ce1d344676ebf4328506228f1bfa87c76e8036f9
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810635"
---
# 判斷裝置為何收到不合規的訊息


WMI 提供下列不相容程式碼，並說明 MBAM 為不符合的特定裝置所報告的原因。

您可以使用您慣用的方法來查看 WMI。 如果您使用的是 PowerShell，請 `gwmi -class mbam_volume -Namespace root\microsoft\mbam` 從 PowerShell 提示執行，然後搜尋 ReasonsForNoncompliance。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">不合規性程式碼</th>
<th align="left">違反規範的原因</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>0</p></td>
<td align="left"><p>密碼強度不是 AES 256。</p></td>
</tr>
<tr class="even">
<td align="left"><p>sr-1</p></td>
<td align="left"><p>MBAM 原則需要加密這個卷，但不需要加密。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>pplx-2</p></td>
<td align="left"><p>MBAM 原則需要此卷沒有加密，但它是。</p></td>
</tr>
<tr class="even">
<td align="left"><p>3</p></td>
<td align="left"><p>MBAM 原則需要這個大量的磁片才能使用 TPM 保護器，但不需要。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>4</p></td>
<td align="left"><p>MBAM 原則需要此大量的磁片才能使用 TPM + PIN 保護器，但不需要。</p></td>
</tr>
<tr class="even">
<td align="left"><p>500</p></td>
<td align="left"><p>MBAM 原則不允許非 TPM 電腦報告為合規性。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>6</p></td>
<td align="left"><p>Volume 有 TPM 保護器，但看不到 TPM （在 BIOS 中停用 TPM 之後，以復原金鑰啟動）。</p></td>
</tr>
<tr class="even">
<td align="left"><p>utf-7</p></td>
<td align="left"><p>MBAM 原則需要使用密碼保護器，但沒有密碼保護器。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>型</p></td>
<td align="left"><p>MBAM 原則需要此磁片卷不使用密碼保護器，但有一個密碼保護器。</p></td>
</tr>
<tr class="even">
<td align="left"><p>9</p></td>
<td align="left"><p>MBAM 原則需要使用自動解除鎖定的保護器，但沒有任何一個。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>第</p></td>
<td align="left"><p>MBAM 原則需要此磁片卷不使用自動解除鎖定保護器，但有一個。</p></td>
</tr>
<tr class="even">
<td align="left"><p>11</p></td>
<td align="left"><p>偵測到原則衝突，防止 MBAM 將此卷報告為合規性。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>之間</p></td>
<td align="left"><p>需要系統磁碟區來加密作業系統，但不存在。</p></td>
</tr>
<tr class="even">
<td align="left"><p>合</p></td>
<td align="left"><p>已針對該卷暫停保護。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>4</p></td>
<td align="left"><p>除非 OS 卷已加密，否則 AutoUnlock 不安全。</p></td>
</tr>
<tr class="even">
<td align="left"><p>工資</p></td>
<td align="left"><p>原則需要最小 cypher 強度為 XTS-AES-128 位，實際 cypher 強度弱。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>位</p></td>
<td align="left"><p>原則需要最小 cypher 強度為 XTS-AES-256 位，實際 cypher 強度弱。</p></td>
</tr>
</tbody>
</table>

 

## 相關主題


[MBAM 2.5 技術參考資料](technical-reference-for-mbam-25.md)

[使用 Windows PowerShell 設定 MBAM 2.5 伺服器功能](configuring-mbam-25-server-features-by-using-windows-powershell.md)

 
## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。
 





