---
title: 使用 PowerShell 管理 App-V
description: 使用 PowerShell 管理 App-V
author: dansimp
ms.assetid: 1ff4686a-1e19-4eff-b648-ada091281094
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 0e7f9171e0ac5589d8f1935e715dfdb9c349192d
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800699"
---
# 使用 PowerShell 管理 App-V


Microsoft Application Virtualization （App-v）5.0 提供 Windows PowerShell Cmdlet，可協助系統管理員執行各種應用程式 V 5.0 任務。 下列各節提供在 App-v 5.0 中使用 PowerShell 的詳細資訊。

## 如何使用 PowerShell 管理 App-v 5。0


使用下列 PowerShell 程式來執行各種應用程式 V 5.0 任務。

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
<td align="left"><p><a href="how-to-load-the-powershell-cmdlets-and-get-cmdlet-help-50-sp3.md" data-raw-source="[How to Load the PowerShell Cmdlets and Get Cmdlet Help](how-to-load-the-powershell-cmdlets-and-get-cmdlet-help-50-sp3.md)">如何載入 PowerShell Cmdlet 及取得 Cmdlet 說明</a></p></td>
<td align="left"><p>說明如何安裝 PowerShell Cmdlet 及尋找 Cmdlet 說明和範例。</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md" data-raw-source="[How to Manage App-V 5.0 Packages Running on a Stand-Alone Computer by Using PowerShell](how-to-manage-app-v-50-packages-running-on-a-stand-alone-computer-by-using-powershell.md)">如何使用 PowerShell 來管理獨立電腦上執行的 App-V 5.0 封裝</a></p></td>
<td align="left"><p>說明如何使用 PowerShell 在獨立電腦上管理用戶端套件生命週期。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md" data-raw-source="[How to Manage Connection Groups on a Stand-alone Computer by Using PowerShell](how-to-manage-connection-groups-on-a-stand-alone-computer-by-using-powershell.md)">如何使用 PowerShell 來管理獨立電腦上的連線群組</a></p></td>
<td align="left"><p>說明如何使用 PowerShell 管理連線群組。</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="how-to-modify-client-configuration-by-using-powershell.md" data-raw-source="[How to Modify Client Configuration by Using PowerShell](how-to-modify-client-configuration-by-using-powershell.md)">如何使用 PowerShell 來修改用戶端組態</a></p></td>
<td align="left"><p>說明如何使用 PowerShell 修改用戶端。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="how-to-apply-the-user-configuration-file-by-using-powershell.md" data-raw-source="[How to Apply the User Configuration File by Using PowerShell](how-to-apply-the-user-configuration-file-by-using-powershell.md)">如何使用 PowerShell 來套用使用者設定檔案</a></p></td>
<td align="left"><p>說明如何使用 PowerShell 來套用使用者設定檔。</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="how-to-apply-the-deployment-configuration-file-by-using-powershell.md" data-raw-source="[How to Apply the Deployment Configuration File by Using PowerShell](how-to-apply-the-deployment-configuration-file-by-using-powershell.md)">如何使用 PowerShell 來套用部署設定檔案</a></p></td>
<td align="left"><p>說明如何使用 PowerShell 來套用部署設定檔。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="how-to-sequence-a-package--by-using-powershell-50.md" data-raw-source="[How to Sequence a Package by Using PowerShell](how-to-sequence-a-package--by-using-powershell-50.md)">如何使用 PowerShell 對套件進行排序</a></p></td>
<td align="left"><p>說明如何使用 PowerShell 建立新的套件。</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="how-to-create-a-package-accelerator-by-using-powershell.md" data-raw-source="[How to Create a Package Accelerator by Using PowerShell](how-to-create-a-package-accelerator-by-using-powershell.md)">如何使用 PowerShell 來建立封裝加速器</a></p></td>
<td align="left"><p>說明如何使用 PowerShell 建立套件加速器。 您可以使用套件加速器自動序列化大型、複雜的應用程式。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><a href="how-to-enable-reporting-on-the-app-v-50-client-by-using-powershell.md" data-raw-source="[How to Enable Reporting on the App-V 5.0 Client by Using PowerShell](how-to-enable-reporting-on-the-app-v-50-client-by-using-powershell.md)">如何使用 PowerShell 在 App-V 5.0 用戶端上啟用報表</a></p></td>
<td align="left"><p>說明如何啟用執行 App-v 5.0 的電腦來傳送報告資訊。</p></td>
</tr>
<tr class="even">
<td align="left"><p><a href="how-to-install-the-app-v-databases-and-convert-the-associated-security-identifiers--by-using-powershell.md" data-raw-source="[How to Install the App-V Databases and Convert the Associated Security Identifiers by Using PowerShell](how-to-install-the-app-v-databases-and-convert-the-associated-security-identifiers--by-using-powershell.md)">如何安裝 App-v 資料庫，以及如何使用 PowerShell 轉換關聯的安全性識別碼</a></p></td>
<td align="left"><p>說明如何取得帳戶名稱陣列，並將每個帳戶名稱轉換成標準及十六進位格式的對應 SID。</p></td>
</tr>
</tbody>
</table>

 

## PowerShell 錯誤處理


請參閱下表以取得 App-v 5.0 PowerShell 錯誤處理的相關資訊。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">事件</th>
<th align="left">動作</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>在內嵌腳本中使用 RollbackOnError 屬性</p></td>
<td align="left"><p>當您將 <strong> RollbackOnError </strong> 屬性與內嵌腳本搭配使用時，系統會忽略下列事件的屬性：</p>
<ul>
<li><p>移除套件</p></li>
<li><p>取消發佈套件</p></li>
<li><p>終止虛擬環境</p></li>
<li><p>終止進程</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>套件名稱包含<strong>$</strong></p></td>
<td align="left"><p>如果套件名稱包含字元（ <strong> $ </strong> ），則必須使用單引號（ <strong> ' </strong> ），例如</p>
<p><strong>AppvClientPackage "Contoso $ App. appv"</strong></p></td>
</tr>
</tbody>
</table>

 






## 相關主題


[App-V 5.0 作業](operations-for-app-v-50.md)

 

 





