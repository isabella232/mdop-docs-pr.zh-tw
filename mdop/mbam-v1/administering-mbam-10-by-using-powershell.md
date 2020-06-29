---
title: 使用 PowerShell 管理 MBAM 1.0
description: 使用 PowerShell 管理 MBAM 1.0
author: dansimp
ms.assetid: 3bf2eca5-4ab7-4e84-9e80-c0c7d709647b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 3547bee9b2efc58252bb6f0a1cb0aa4c484e4e80
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810976"
---
# 使用 PowerShell 管理 MBAM 1.0


Microsoft BitLocker 管理與監控（MBAM）提供下列所列的 Windows PowerShell Cmdlet 集合。 系統管理員可以使用這些 PowerShell Cmdlet，從命令提示字元執行各種 MBAM 伺服器工作，而不是從 MBAM 管理網站執行。

## 如何使用 PowerShell 管理 MBAM


使用這裡所述的 PowerShell Cmdlet 來管理 MBAM。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名稱</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>附加 MbamHardwareType</p></td>
<td align="left"><p>將新的硬體模型新增至 MBAM 硬體清單。 這個 Cmdlet 也可以指定是否支援或不支援 BitLocker 磁片磁碟機加密的硬體。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MbamBitLockerRecoveryKey</p></td>
<td align="left"><p>要求可讓使用者解除鎖定電腦或加密磁片磁碟機的 MBAM 復原金鑰。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MbamHardwareType</p></td>
<td align="left"><p>取得含有資料的主硬體清單，指出硬體模型相容性或與 BitLocker 磁片磁碟機加密不相容。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MbamTPMOwnerPassword</p></td>
<td align="left"><p>為使用者提供 TPM 擁有者密碼來管理其 TPM （受信任的平臺模組）存取權。 可在 TPM 已鎖定並將不再接受其 PIN 時，協助使用者。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>安裝-Mbam</p></td>
<td align="left"><p>安裝可提供高級群組原則、加密、金鑰復原及合規性報告工具的 MBAM 功能。</p></td>
</tr>
<tr class="even">
<td align="left"><p>移除-MbamHardwareType</p></td>
<td align="left"><p>從硬體清點移除硬體模型。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>Set-MbamHardwareType</p></td>
<td align="left"><p>允許管理主要硬體清查，以指定硬體模型是否可以執行 BitLocker 加密。</p></td>
</tr>
<tr class="even">
<td align="left"><p>卸載-Mbam</p></td>
<td align="left"><p>移除先前安裝的 MBAM 功能，提供高級原則、加密、金鑰復原及合規性報告工具。</p></td>
</tr>
</tbody>
</table>

 

## 相關主題


[適用於 MBAM 1.0 的操作](operations-for-mbam-10.md)

 

 





