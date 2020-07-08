---
title: 使用 Windows PowerShell 管理 MBAM 2.5
description: 使用 Windows PowerShell 管理 MBAM 2.5
author: dansimp
ms.assetid: 64668e76-2cba-433d-8d2d-50df0a4b2997
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 11/02/2016
ms.openlocfilehash: 8db305bfbdf79723da2b186dd5cc00406a4089cc
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800168"
---
# 使用 Windows PowerShell 管理 MBAM 2.5


本主題描述 Microsoft BitLocker 管理與監控（MBAM）的 Windows PowerShell Cmdlet，這些 Cmdlet 會在使用者鎖定時，與復原電腦或磁片磁碟機有關。

針對您用來設定 MBAM 伺服器功能的 Cmdlet，請參閱[使用 Windows PowerShell 配置 MBAM 2.5 伺服器功能](configuring-mbam-25-server-features-by-using-windows-powershell.md)。

## <a href="" id="cmdlets-for-recovering-computers-or-drives-that-are-managed-by-mbam-"></a>用來復原由 MBAM 管理的電腦或磁片磁碟機的 Cmdlet


使用下列 Windows PowerShell Cmdlet 來復原由 MBAM 管理的電腦或磁片磁碟機。

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
<td align="left"><p>MbamBitLockerRecoveryKey</p></td>
<td align="left"><p>要求使用者解除鎖定電腦或加密磁片磁碟機的 MBAM 復原金鑰。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MbamTPMOwnerPassword</p></td>
<td align="left"><p>提供擁有 TPM 擁有者密碼的使用者，這些密碼可用來解除鎖定受信任的平臺模組（TPM），而 TPM 已將它們鎖定並將不再接受其 PIN。</p></td>
</tr>
</tbody>
</table>

 

## <a href="" id="---------mbam-cmdlet-help"></a> MBAM Cmdlet 說明


MBAM Cmdlet 的 Windows PowerShell 說明提供下列格式：

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">Windows PowerShell 說明格式</th>
<th align="left">詳細資訊</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>在 Windows PowerShell 命令提示字元中，輸入 <strong> get-help </strong> &lt; <em> Cmdlet</em>&gt;</p></td>
<td align="left"><p>若要上傳最新的 Windows PowerShell Cmdlet，請依照 <a href="configuring-mbam-25-server-features-by-using-windows-powershell.md" data-raw-source="[Configuring MBAM 2.5 Server Features by Using Windows PowerShell](configuring-mbam-25-server-features-by-using-windows-powershell.md)"> 使用 Windows powershell 設定 MBAM 2.5 伺服器功能中的指示進行。</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>在 TechNet 上做為網頁</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393498" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393498">https://go.microsoft.com/fwlink/?LinkId=393498</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>以單字 .docx 檔案的形式在下載中心</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393497" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393497">https://go.microsoft.com/fwlink/?LinkId=393497</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>以 .pdf 檔案的形式在下載中心</p></td>
<td align="left"><p><a href="https://go.microsoft.com/fwlink/?LinkId=393499" data-raw-source="https://go.microsoft.com/fwlink/?LinkId=393499">https://go.microsoft.com/fwlink/?LinkId=393499</a></p></td>
</tr>
</tbody>
</table>

 



## 相關主題


[管理 MBAM 2.5 功能](administering-mbam-25-features.md)

[使用 Windows PowerShell 設定 MBAM 2.5 伺服器功能](configuring-mbam-25-server-features-by-using-windows-powershell.md)

 

## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





