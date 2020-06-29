---
title: Application Virtualization Client 中的使用者存取權限
description: Application Virtualization Client 中的使用者存取權限
author: dansimp
ms.assetid: 7459374c-810c-45e3-b205-fdd1f8514f80
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 1083faffb48aa58a0ee0c81b58fae307e53548b8
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800755"
---
# Application Virtualization Client 中的使用者存取權限


在 [**屬性**] 對話方塊的 [**許可權**] 索引標籤上，以滑鼠右鍵按一下應用程式虛擬化用戶端管理主控台中的 [**應用程式虛擬化**] 節點，管理員可以授與使用者使用各種用戶端函數的許可權。

**記事** 在變更使用者許可權前，請確定任何許可權變更與組織提供使用者許可權的指導方針一致。

 

下表列出並說明可授與使用者的許可權。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">許可權名稱</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>新增應用程式</p></td>
<td align="left"><p>使用 sfttray.exe、sftmime.exe 或 MMC，將新的應用程式傳到用戶端。</p></td>
</tr>
<tr class="even">
<td align="left"><p>變更檔案系統快取大小</p></td>
<td align="left"><p>增加檔案系統快取的大小。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>變更檔系統磁碟機</p></td>
<td align="left"><p>針對檔案系統選取不同的喜好磁片磁碟機盤符。</p></td>
</tr>
<tr class="even">
<td align="left"><p>變更記錄設定</p></td>
<td align="left"><p>變更用戶端記錄檔的記錄層級或記錄路徑。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>變更 OSD 檔案</p></td>
<td align="left"><p>修改已註冊之應用程式的 OSD 檔案，並將它們傳到用戶端。 這不會影響發佈重新整理。</p></td>
</tr>
<tr class="even">
<td align="left"><p>清除應用程式設定</p></td>
<td align="left"><p>刪除目前使用者的檔案類型、快速鍵及任何設定。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>刪除應用程式</p></td>
<td align="left"><p>針對電腦上的所有使用者，從 [檔案系統] 和 [OSD 快取] 移除應用程式的所有參照。</p></td>
</tr>
<tr class="even">
<td align="left"><p>將應用程式匯入快取</p></td>
<td align="left"><p>將應用程式資料直接從指定的 SFT 檔案載入至檔案系統快取。 這會影響所有使用者。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>將應用程式載入到快取</p></td>
<td align="left"><p>從已設定的來源開始為應用程式載入 SFT 檔案，例如 App-v 串流伺服器。 這會針對電腦上的所有使用者載入應用程式。</p></td>
</tr>
<tr class="even">
<td align="left"><p>在快取中鎖定和解除鎖定應用程式</p></td>
<td align="left"><p>防止或允許從檔案系統快取中卸載應用程式。 這會影響電腦上的所有使用者。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>管理檔案類型關聯</p></td>
<td align="left"><p>新增、修改或刪除目前使用者的檔案類型關聯。</p></td>
</tr>
<tr class="even">
<td align="left"><p>管理發佈更新設定</p></td>
<td align="left"><p>變更設定，以控制電腦上所有使用者的發佈更新時間。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>管理發佈伺服器</p></td>
<td align="left"><p>新增、修改或刪除電腦上所有使用者的發佈伺服器。 此許可權會隱式包含管理發佈更新設定的許可權。</p></td>
</tr>
<tr class="even">
<td align="left"><p>發佈快速鍵</p></td>
<td align="left"><p>建立已註冊應用程式的新快速鍵。 使用者也必須具有在本機檔案系統中建立檔案的許可權。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>修復應用程式</p></td>
<td align="left"><p>移除目前使用者的應用程式特定設定，但不移除快速鍵或檔案類型關聯。</p></td>
</tr>
<tr class="even">
<td align="left"><p>啟動發佈更新</p></td>
<td align="left"><p>針對目前的使用者，啟動未排程的發佈更新。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>切換離線模式</p></td>
<td align="left"><p>針對所有使用者將整個用戶端從線上改為離線模式。</p></td>
</tr>
<tr class="even">
<td align="left"><p>從快取中卸載應用程式</p></td>
<td align="left"><p>清除檔案系統快取中所有使用者的應用程式資料，而不需移除使用者專用的設定、快速鍵或檔案類型關聯。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>查看所有應用程式</p></td>
<td align="left"><p>允許使用者查看在電腦上註冊之所有使用者的虛擬應用程式。</p></td>
</tr>
</tbody>
</table>

 

## 相關主題


[如何變更使用者存取權限](how-to-change-user-access-permissions.md)

 

 





