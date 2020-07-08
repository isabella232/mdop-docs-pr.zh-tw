---
title: SFTTRAY 命令參考資料
description: SFTTRAY 命令參考資料
author: dansimp
ms.assetid: 6fa3a939-b047-4d6c-bd1d-dfb93e065eb2
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, appcompat, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 45a664b91ff7edd5f8536f035417cc3b0f52d7ca
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800802"
---
# SFTTRAY 命令參考資料


Microsoft Application Virtualization （App-v）用戶端工作列應用程式 sfttray.exe，是使用者在正常使用期間將與其互動的 App V 用戶端主要使用者介面元素。 這個程式會控制資料流程並開始所有的虛擬應用程式，並以滑鼠右鍵按一下顯示在通知區域中的圖示，以顯示用戶端函數的功能表，以進行存取。 此功能表可讓使用者載入應用程式、啟動發佈重新整理、取消要求，或將用戶端變更為離線模式。 使用者也可以按一下 [結束]，關閉應用程式虛擬化用戶端工作列應用程式和所有**作用中的**應用程式。

雖然您可以使用 SFTTRAY 命令來控制此行為，但是預設會在虛擬應用程式啟動時顯示圖示。 應用程式虛擬化用戶端工作列應用程式也會針對每個已啟動的應用程式顯示進度列，以及有關作用中應用程式的狀態訊息。 按一下進度列會顯示一則訊息，讓您取消載入或啟動應用程式。

## SFTTRAY 命令


您可以從命令視窗執行下列命令，以顯示命令與命令列開關的清單。

**注意**  
每個使用者內容只有一個應用程式虛擬化用戶端工作列實例，所以如果您開始新的 SFTTRAY 命令，就會將它傳遞到已在執行中的程式。



`Sfttray.exe /?`

### 命令用法

`Sfttray.exe [/HIDE | /SHOW]`

`Sfttray.exe [/HIDE | /SHOW] [/QUIET] [/EXE alternate-exe] /LAUNCH app [args]`

`Sfttray.exe [/HIDE | /SHOW] [/QUIET] /LOAD app [/SFTFILE sft]`

`Sfttray.exe [/HIDE | /SHOW] [/QUIET] /LOADALL`

`Sfttray.exe [/HIDE | /SHOW] [/QUIET] /REFRESHALL`

`Sfttray.exe [/HIDE | /SHOW] [/QUIET] /LAUNCHRESULT <UNIQUE ID>  /LAUNCH app [args]`

`Sfttray.exe /EXIT`

### 命令列參數

下表說明 SFTTRAY 命令列參數。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">切換</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>/HIDE</p></td>
<td align="left"><p>隱藏 Windows 通知區域中的 [SFTTRAY] 圖示。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/SHOW</p></td>
<td align="left"><p>在 Windows 通知區域中顯示 [SFTTRAY] 圖示。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/QUIET</p></td>
<td align="left"><p>支援無人參與的使用方式，避免錯誤顯示需要使用者確認的訊息框。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/EXE &lt; 替代 EXE&gt;</p></td>
<td align="left"><p>與/LAUNCH 搭配使用，以指定在啟動虛擬應用程式以取代 OSD 中指定的目標檔案時，會在虛擬環境中啟動一個可執行程式。</p>
<div class="alert">
<strong>注意</strong><br/><p>例如，使用「SFTTRAY.EXE/EXE REGEDIT.EXE/LAUNCH app」， &lt; &gt; 讓您檢查應用程式在其中執行之虛擬環境的註冊表。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>/LAUNCH &lt; 應用程式 &gt; [ &lt; 參數 &gt; ]</p></td>
<td align="left"><p>啟動虛擬應用程式。 指定應用程式的名稱和版本，或是 OSD 檔案的路徑。 您也可以將命令列引數傳遞到虛擬應用程式。</p>
<div class="alert">
<strong>注意</strong><br/><p>使用命令「SFTMIME.EXE/QUERY OBJ：應用程式/SHORT」取得可用虛擬應用程式的名稱和版本清單。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p>/LOAD</p></td>
<td align="left"><p>載入或匯入虛擬應用程式。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/LOADALL</p></td>
<td align="left"><p>將所有應用程式載入到快取中。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/REFRESHALL</p></td>
<td align="left"><p>針對所有應用程式啟動 [發佈重新整理]。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/LAUNCHRESULT &lt; 唯一識別碼&gt;</p></td>
<td align="left"><p>將啟動結果代碼傳回啟動 sfttray.exe 的處理常式，方法是使用全域事件，以及根據指定的根名稱（針對唯一識別碼. ¹）的記憶體對應檔案。</p></td>
</tr>
<tr class="even">
<td align="left"><p>/SFTFILE &lt; sft&gt;</p></td>
<td align="left"><p>與/LOAD 搭配使用的選用開關，可指定應用程式 SFT 檔案的路徑。 如果已指定，就會匯入應用程式，而不是載入。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>/EXIT</p></td>
<td align="left"><p>關閉 SFTTRAY 程式及所有作用中的虛擬應用程式，並移除 Windows 通知區域中的圖示。</p></td>
</tr>
</tbody>
</table>



**注意**  
¹ */LAUNCHRESULT*命令列參數為啟動 sfttray.exe 的程式提供一種方式，以指定全域事件的根名稱，以及用來將啟動結果程式碼傳回處理常式的記憶體對應檔案。 唯一識別碼名稱應該以 "SFT-" 開頭，以避免事件名稱在虛擬環境中呼叫啟動程式時得到虛擬化。 記憶體對應的區域將為64位大小。

若要使用這個參數，啟動程式會建立一個名稱為 "unique ID-result \ _event" 的事件，該檔案的名稱為「 &lt; &gt; &lt; unique id &gt; -result \ _value」，並選擇性地 &lt; &gt; sfttray.exe 啟動處理 _event 程式，並等待事件發出信號，然後等待事件停止。 事件「 &lt; UNIQUE ID &gt; -result \ _event」超時之後，啟動程式會從記憶體對應區域中檢索64位傳回碼。

如果 &lt; &gt; 當虛擬應用程式退出時，會出現選擇性事件「唯一識別碼-shutdown \ _event」，sfttray.exe 會開啟併發出事件信號。 啟動程式會在此關閉事件時等待，如果它需要判斷虛擬應用程式何時退出。











