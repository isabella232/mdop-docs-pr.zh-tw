---
title: 了解控制台中的 BitLocker 加密選項與 BitLocker 磁碟機加密項目
description: 了解控制台中的 BitLocker 加密選項與 BitLocker 磁碟機加密項目
author: dansimp
ms.assetid: f8a01cc2-0c77-48b9-8351-8194e80b0cf8
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 739b65680ebfdf19f006ee8f3079f7c7e602f697
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800177"
---
# 了解控制台中的 BitLocker 加密選項與 BitLocker 磁碟機加密項目


本主題描述**Bitlocker 加密選項**和**Bitlocker 磁片磁碟機加密**控制台專案，並說明下列事項：

-   如何建立這些專案

-   可讓您執行的工作

-   **管理 BitLocker**[以滑鼠右鍵按一下] 快顯功能表可見且隱藏，以及如何將其設定為預設為可見

## BitLocker 加密選項和 BitLocker 磁片磁碟機加密控制台專案


下表列出您可以從每個 [控制台] 專案執行的工作，並說明這些專案的建立方式。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left">BitLocker 加密選項（MBAM）</th>
<th align="left">BitLocker 磁片磁碟機加密（Windows）</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>您可以執行的工作</p></td>
<td align="left"><ul>
<li><p>變更您的 PIN 或密碼</p></li>
<li><p>檢查磁片磁碟機的加密狀態</p></li>
<li><p>開啟 TPM 管理主控台</p></li>
<li><p>[開啟 BitLocker]</p></li>
</ul></td>
<td align="left"><ul>
<li><p>暫停對磁片磁碟機的保護</p></li>
<li><p>備份您的復原金鑰</p></li>
<li><p>變更您的 PIN</p></li>
<li><p>關閉磁片磁碟機的 BitLocker</p></li>
<li><p>針對磁片磁碟機開啟 BitLocker</p></li>
<li><p>開啟 TPM 管理主控台</p></li>
<li><p>解密磁片磁碟機（只有在未安裝 MBAM 用戶端時才會出現）</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>[控制版面] 專案的建立方式</p></td>
<td align="left"><p>當您安裝 MBAM 用戶端時，在 [控制台] 中建立。 無法隱藏此專案。</p>
<div class="alert">
<strong>注意</strong><br/><p>這個專案除了出現，但不會取代預設的 [BitLocker 磁片磁碟機加密] 控制台專案。</p>
</div>
<div>

</div></td>
<td align="left"><p>預設會在 [控制台] 中顯示為 Windows 作業系統的一部分，但您可以將它隱藏。</p>
<p>若要隱藏它，請參閱 <a href="hiding-the-default-bitlocker-drive-encryption-item-in-control-panel-mbam-25.md" data-raw-source="[Hiding the Default BitLocker Drive Encryption Item in Control Panel](hiding-the-default-bitlocker-drive-encryption-item-in-control-panel-mbam-25.md)"> 隱藏 [控制台] 中的 [預設 BitLocker 磁片磁碟機加密專案] </a> 。</p></td>
</tr>
</tbody>
</table>



## <a href="" id="-manage-bitlocker--shortcut-menu"></a>[管理 BitLocker] 快顯功能表


下表說明根據是否已安裝 MBAM 用戶端，[**管理 BitLocker** ] 快顯功能表會有所不同。 「快捷方式功能表」一詞是指當您以滑鼠右鍵按一下 Windows 資源管理器中的磁片磁碟機時所顯示的選項。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"></th>
<th align="left">安裝 MBAM 用戶端時</th>
<th align="left">未安裝 MBAM 用戶端</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>快捷方式功能表的可見度</p></td>
<td align="left"><p>[管理 BitLocker] 選項是 [隱藏]。</p>
<p>若要讓 [管理 BitLocker] 選項顯示在快捷方式功能表上，這會顯示解密磁片磁碟機的選項，請刪除下列登錄機碼：</p>
<pre class="syntax" space="preserve"><code>HKEY_CLASSES_ROOT\Drive\Shell\manage-bde \REG_SZ LegacyDisable</code></pre></td>
<td align="left"><p>[管理 BitLocker] 選項會出現在快捷方式功能表上。</p></td>
</tr>
<tr class="even">
<td align="left"><p>使用者可以執行的動作</p></td>
<td align="left"><p>隱藏快速鍵之後，使用者就可以開啟 BitLocker 磁片磁碟機加密控制台專案，但無法使用 [解密磁片] 選項。</p></td>
<td align="left"><p>顯示快捷方式之後，選取 [ <strong> 管理 BitLocker] </strong> 選項會開啟 [BitLocker 磁碟機加密控制台] 專案，其中會顯示解密磁片磁碟機的選項。</p></td>
</tr>
</tbody>
</table>




## 相關主題


[管理 MBAM 2.5 功能](administering-mbam-25-features.md)



## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。 





