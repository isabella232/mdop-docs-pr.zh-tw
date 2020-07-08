---
title: 如何使用命令列部署 MBAM 用戶端
description: 如何使用命令列部署 MBAM 用戶端
author: dansimp
ms.assetid: ac1d4ffe-c26d-41c9-9737-a4f2b37fde24
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 416d76ad876c5114e3a8764111b6a15c879b13b5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810586"
---
# 如何使用命令列部署 MBAM 用戶端


您可以使用命令列來部署 Microsoft BitLocker 管理和監控（MBAM）用戶端軟體。

## 部署 MBAM 用戶端軟體的命令列


在命令提示字元中輸入下列命令，以在部署 MBAM 用戶端軟體時自動接受使用者授權合約。

**MBAMClientSetup.exe/acceptEula = 是**

**記事** **/Ju**和 **/jm**命令列選項不受支援，且無法用來安裝 MBAM 用戶端軟體。

 

在命令提示字元中輸入下列命令，以解壓並安裝 MSP：

**MBAMClientSetup.exe/extract &lt; 路徑來解壓縮 MSI &gt; /AcceptEula = 是**

然後，執行下列命令，以無訊息方式安裝 MSI：

**msiexec/i &lt; 路徑解壓至已解壓縮的 MSI &gt; /qb ALLUSERS = 1 重新開機 = ReallySuppress**

**記事** 從 MBAM 2.5 SP1 開始，MBAM 產品不再隨附個別的 MSI。 不過，您可以在接受 EULA 之後，從產品隨附的可執行檔（.exe）中解壓縮 MSI。

 

## <a href="" id="optin-for-microsoft-updates-1-command-line-option"></a>OPTIN \ _FOR \ _MICROSOFT \ _UPDATES = 1 命令列選項


您也可以選擇在 `OPTIN_FOR_MICROSOFT_UPDATES=1` 用戶端軟體安裝期間指定命令列選項，在用戶端電腦上自動安裝 Microsoft 更新。 指定此選項會讓 Microsoft Update 在用戶端軟體安裝完成後，自動啟動並搜尋可用的更新以進行安裝。

您可以將這個命令列選項與下列其中一個安裝方法搭配使用。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">使用 MBAM 用戶端軟體安裝</th>
<th align="left">範例</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p><strong>MBAMClientSetup.exe</strong></p></td>
<td align="left"><p><strong>MbamClientSetup.exe OPTIN_FOR_MICROSOFT_UPDATES = 1</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>msiexec/i MBAMClient.msi</strong></p></td>
<td align="left"><p><strong>msiexec/i MBAMClient.msi OPTIN_FOR_MICROSOFT_UPDATES = 1</strong></p></td>
</tr>
</tbody>
</table>

 


## 相關主題


[部署 MBAM 2.5 用戶端](deploying-the-mbam-25-client.md)

 

 
## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。 
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。




