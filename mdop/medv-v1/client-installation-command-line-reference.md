---
title: 用戶端安裝命令列參考資料
description: 用戶端安裝命令列參考資料
author: dansimp
ms.assetid: 122a593d-3314-4e9b-858a-08a25ed00c32
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 708daf82699c63dfaa1f99ae595911cf6bad3737
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811930"
---
# 用戶端安裝命令列參考資料


**從命令列安裝 MED-V**

1.  從命令列執行 MED-V 套件，接著接著下表所述的任何選擇性參數。

2.  會呼叫 MED-V 封裝*MED-V\_x.msi*，其中*x*是版本號碼。

    例如， *MED-V\_1.0.65.msi*。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">參數</th>
<th align="left">值</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>/quiet</p></td>
<td align="left"><p></p></td>
<td align="left"><p>無訊息安裝</p></td>
</tr>
<tr class="even">
<td align="left"><p>/log &lt; 記錄檔的完整路徑&gt;</p></td>
<td align="left"><p>記錄檔的完整路徑。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>INSTALLDIR</p></td>
<td align="left"><p>安裝目錄的完整路徑。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>VMSFOLDER</p></td>
<td align="left"><p>虛擬機器資料夾的完整路徑。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>INSTALL_ADMIN_TOOLS</p></td>
<td align="left"><p><strong>1、0</strong></p>
<p>預設值： <strong> 0</strong></p></td>
<td align="left"><p>安裝 MED-V 管理工具。</p></td>
</tr>
<tr class="even">
<td align="left"><p>START_AUTOMATICALLY</p></td>
<td align="left"><p><strong>1、0</strong></p>
<p>預設值： <strong> 0</strong></p></td>
<td align="left"><p>每次使用者登入 Windows 時，自動啟動 MED-V 用戶端。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>SERVER_ADDRESS</p></td>
<td align="left"><p>主機名稱或 IP</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>SERVER_PORT</p></td>
<td align="left"><p>連接埠</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>SERVER_SSL</p></td>
<td align="left"><p><strong>1、0</strong></p>
<p><strong>HTTPs </strong> 或 <strong> HTTP</strong></p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>START_MEDV</p></td>
<td align="left"><p><strong>1、0</strong></p>
<p>預設值： <strong> 1</strong></p></td>
<td align="left"><p>完成 MED-V 安裝後，就會開始 MED-V。</p>
<div class="alert">
<strong>注意</strong><br/><p>建議在系統安裝的情況下，設定 START_MEDV = 0。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>DESKTOP_SHORTCUT</p></td>
<td align="left"><p><strong>1、0</strong></p>
<p>預設值： <strong> 1</strong></p></td>
<td align="left"><p>在桌面建立快捷方式，這會啟動 MED-V-V 用戶端。</p></td>
</tr>
<tr class="even">
<td align="left"><p>MINIMAL_RAM_REQUIRED</p></td>
<td align="left"><p>RAM （MB）</p></td>
<td align="left"><p>安裝 MED-V 時，會檢查電腦是否有指定的最小 RAM 數。 如果不是，安裝就會中止。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>SKIP_OS_CHECK</p></td>
<td align="left"><p><strong>1、0</strong></p></td>
<td align="left"><p>省略作業系統驗證。</p></td>
</tr>
</tbody>
</table>











