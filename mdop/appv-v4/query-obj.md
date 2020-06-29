---
title: QUERY OBJ
description: QUERY OBJ
author: dansimp
ms.assetid: 55abf0d1-c779-4172-8357-552ab010933b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 328e9feb96c70080531cbbc666d8ff1b86045ba5
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800879"
---
# QUERY OBJ


傳回目前應用程式、套件、檔案類型關聯或發佈伺服器的 tab 分隔清單。

`SFTMIME QUERY OBJ:{APP|PACKAGE|TYPE|SERVER} [/SHORT] [/GLOBAL]                 [/LOG log-pathname | /CONSOLE ]`

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">參數</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>適用</p></td>
<td align="left"><p>傳回應用程式的清單。</p></td>
</tr>
<tr class="even">
<td align="left"><p>套件</p></td>
<td align="left"><p>傳回套件清單。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>TYPE</p></td>
<td align="left"><p>傳回檔案類型關聯性清單。</p></td>
</tr>
<tr class="even">
<td align="left"><p>伺服器</p></td>
<td align="left"><p>傳回發佈伺服器的清單。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/SHORT</p></td>
<td align="left"><p>若不顯示每個屬性的完整屬性，則會傳回應用程式名稱、套件、關聯或伺服器名稱的清單。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/GLOBAL</p></td>
<td align="left"><p>針對應用程式，傳回所有已知的應用程式，而不是目前使用者有權存取的那些應用程式。 針對套件，傳回所有已知的套件，而不是目前使用者有權存取的套件。 針對關聯，只會傳回適用于所有使用者的關聯，而不會傳回使用者特定的關聯。 伺服器無效。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/LOG</p></td>
<td align="left"><p>如果已指定，輸出就會記錄到指定的路徑名稱。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/CONSOLE</p></td>
<td align="left"><p>如果已指定，輸出就會顯示在 active 主控台視窗中（預設）。</p></td>
</tr>
</tbody>
</table>

 

針對版本4.6，新增了下列選項。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>/LOGU</p></td>
<td align="left"><p>如果已指定，輸出會以 UNICODE 格式記錄到指定的路徑名稱。</p></td>
</tr>
</tbody>
</table>

 

**記事** 在版本4.6 中，已將新資料行新增至 SFTMIME 查詢 OBJ： APP \ [/GLOBAL\] 的輸出。 輸出的最後一欄是指示是否已發佈應用程式的數值。

已發佈 = 1 表示應用程式是由發佈伺服器更新所發佈，方法是使用 Windows 安裝程式檔案（。MSI），或執行 SFTMIME [新增套件]，使用套件資訊清單設定套件或發佈套件命令。

已發佈 = 0 表示應用程式尚未發佈，或是執行 [清除] 作業或執行 SFTMIME 取消發佈命令之後，就不會再發佈。

如果您使用/GLOBAL 參數，發佈的狀態將為1，適用于全域發佈的應用程式，而在使用者上下文中發佈的應用程式則為0。 如果沒有/GLOBAL 參數，則會針對執行命令之使用者的內容所發佈的應用程式傳回1的已發佈狀態，而針對全域發佈的應用程式傳回0的狀態。

 

SFTMIME 查詢 OBJ 命令可用來查詢上述所有物件（應用程式、套件、檔案類型關聯及伺服器）的相關資訊。若要示範您可以如何在一般作業工作中使用 SFTMIME QUERY OBJ 命令，下列範例會示範在您想要設定特定套件的 OVERRIDEURL 參數值來指定套件內容的新路徑時所遵循的處理常式。 

1.  若要尋找您要設定的套件，請執行下列命令：

    `SFTMIME QUERY OBJ:PACKAGE`

    這個命令會將每個發現的套件名稱傳回為輸出第一欄中的 GUID （例如，{AF78ABE1-57D4-4297-89DE-C308684AEDD6}）。

2.  若要設定 OVERRIDEURL 參數值，您可以使用 SFTMIME [[設定套件](configure-package.md)] 命令。 例如，若要將這個套件的 OVERRIDEURL 值設為*\\\\server\\share\\mypackage.sft*的值，請使用 SFTMIME 的 [設定套件] 命令，然後從步驟1的 SFTMIME 查詢 OBJ 命令輸出中，為其指定套件 GUID，後面接著是 OVERRIDEURL 參數及其新值，如下所示：

    `SFTMIME CONFIGURE PACKAGE:"{AF78ABE1-57D4-4297-89DE-C308684AEDD6}" /OVERRIDEURL "\\\\server\\share\\mypackage.sft "`

針對版本 4.6 SP2，新增了下列選項。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>/NO-UPDATE-FTA-SHORTCUT</p></td>
<td align="left"><p>指示/NO-UPDATE-FTA-SHORTCUT 旗標的目前狀態。</p></td>
</tr>
</tbody>
</table>

 

## 相關主題


[SFTMIME 命令參考](sftmime--command-reference.md)

 

 





