---
title: 如何設定捷徑和檔案類型關聯行為
description: 如何設定捷徑和檔案類型關聯行為
author: dansimp
ms.assetid: d6fd1728-4de6-4066-b36b-d4837d593d40
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 84e3e0cdd43cfc26cf56f1b5ac72560b1c702ae6
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10801606"
---
# 如何設定捷徑和檔案類型關聯行為


快捷方式和檔案類型關聯（FTA）發佈原則是由發佈 XML 檔案定義並加以控制，在發佈重新整理作業期間，由發佈伺服器傳送給用戶端。 當用戶端收到此資訊時，會新增有關應用程式（例如圖示與 FTAs）的任何新近發佈資料。 接著，它會移除任何過時的發佈資料。

在 App-V 版本4.6 中，已定義兩個登錄機碼值，讓系統管理員可以控制此行為。 根據預設，使用用戶端主控台在本機建立的快速鍵現在會保留下來。

## 如何變更快速鍵與 FTA 行為


已針對用戶端配置登錄機碼（"FileTypePolicy" 和 "ShortcutPolicy"）定義兩個新的 DWORD 值登錄值。 預設不會顯示這些 DWORD 登錄值，但可以手動新增它們。 配置登錄機碼位於 HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\\ [Wow6432Node\\\] Microsoft\\SoftGrid\\4.5\\Client\\Configuration。

下表中定義了四個原則值，它們都適用于兩個登錄機碼值。 下列清單顯示註冊表設定的數值，以及在發佈重新整理作業上套用至檔案類型或快速鍵的行為。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p>名稱</p></td>
<td align="left"><p>類型</p></td>
<td align="left"><p>資料（範例）</p></td>
<td align="left"><p>描述</p></td>
</tr>
<tr class="even">
<td align="left"><p>FileTypePolicy</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設值 = 0x2 （App-v 4.6）</p></td>
<td align="left"><p>（0x0）-"ClientOnly"-從相同的發佈資訊來源移除任何現有的專案，並只保留在本機新增的專案</p>
<p>（0x1）-"ServerOnly"-從相同的發佈資訊來源以及任何在本機加入的專案，移除任何過期的專案，並新增專案</p>
<p>（0x2）-"ClientAndServer"-從相同的發佈資訊來源中移除任何過時的專案、將專案新增到本機，以及新增專案（如果 App-v 4.6 不存在，則為預設值）</p>
<p>（0x3）– "NoChange"-不對檔案類型或快速鍵進行任何變更</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ShortcutPolicy</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設 = 0x2</p></td>
<td align="left"><p>（0x0）-"ClientOnly"-從相同的發佈資訊來源移除任何現有的專案，並只保留在本機新增的專案</p>
<p>（0x1）-"ServerOnly"-從相同的發佈資訊來源以及任何在本機加入的專案，移除任何過期的專案，並新增專案</p>
<p>（0x2）-"ClientAndServer"-從相同的發佈資訊來源中移除任何過時的專案，將專案保留在本機，並新增專案（如果沒有的話則為預設值）</p>
<p>（0x3）– "NoChange"-不對檔案類型或快速鍵進行任何變更</p></td>
</tr>
</tbody>
</table>

 

**記事** 文字值會參照發佈 XML 檔案中 XML 屬性的值。如果您已執行自訂 HTTP 發佈解決方案，您可以手動設定這些值。

 

 

 





