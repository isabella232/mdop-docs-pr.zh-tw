---
title: 使用 PowerShell 管理 MBAM 2.0
description: 使用 PowerShell 管理 MBAM 2.0
author: dansimp
ms.assetid: d785a8df-0a8c-4d70-abd2-93a762b4f3de
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 736943e707b5d033b8ba6c26641393f02f0cdaf8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809993"
---
# 使用 PowerShell 管理 MBAM 2.0


Microsoft BitLocker 管理與監控（MBAM）提供下列所列的 Windows PowerShell Cmdlet 集合。 系統管理員可以使用這些 PowerShell Cmdlet，從命令列執行各種 Microsoft BitLocker 管理及監視伺服器工作，而不是從 MBAM 管理網站執行。

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
<td align="left"><p>安裝-Mbam</p></td>
<td align="left"><p>安裝提供高級原則、加密、金鑰復原及合規性報告的 MBAM 功能。</p></td>
</tr>
<tr class="even">
<td align="left"><p>卸載-Mbam</p></td>
<td align="left"><p>移除提供高級原則、加密、金鑰復原及合規性報告工具的 MBAM 功能。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MbamBitLockerRecoveryKey</p></td>
<td align="left"><p>要求能讓使用者解除鎖定電腦或加密磁片磁碟機的 MBAM 復原金鑰。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MbamTPMOwnerPassword</p></td>
<td align="left"><p>提供擁有 TPM 擁有者密碼的使用者，這些密碼可用來解除鎖定受信任的平臺模組（TPM），而 TPM 已將它們鎖定並將不再接受其 PIN。</p></td>
</tr>
</tbody>
</table>

 

## 相關主題


[適用於 MBAM 2.0 的操作](operations-for-mbam-20-mbam-2.md)

 

 





