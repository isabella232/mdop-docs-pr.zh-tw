---
title: Microsoft User Experience Virtualization (UE-V) 2.0 版本資訊
description: Microsoft User Experience Virtualization (UE-V) 2.0 版本資訊
author: dansimp
ms.assetid: 5ef66cd1-ba2b-4383-9f45-e7cde41f1ba1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: ad3deffa5cd567a70711e5447197e630f04ea254
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811061"
---
# Microsoft User Experience Virtualization (UE-V) 2.0 版本資訊


若要搜尋 Microsoft 使用者體驗虛擬化（UE-V）2.0 版本資訊，請按 Ctrl + F。

您必須先閱讀這些版本資訊，才能安裝 UE-V。 版本資訊包含成功安裝使用者體驗虛擬化所需的資訊，並包含產品檔中不提供的其他資訊。 如果這些版本資訊與其他 UE-V 檔之間有差異，最新的變更應該視為權威性。 這些版本資訊取代本產品隨附的內容。

## 提供意見反應


向我們提供您的意見反應與意見反應，告訴我們您對 MDOP 檔的想法。 將您的檔意見反應傳送給[mdopdocs@microsoft.com](mailto:mdopdocs@microsoft.com?subject=UE-V%20Documentation)。

## UE-V 已知問題


本節包含適用于使用者體驗虛擬化的版本資訊。

### 在同一部電腦上的 App-v 與原生應用程式之間的登錄設定無法同步處理

當電腦的應用程式是透過應用程式虛擬化（App-v）安裝並在本機使用 Windows Installer （.msi）檔案時，以註冊表為基礎的設定不會在技術之間同步處理。

因應措施 **：** 若要解決此問題，請選取其中一種技術來執行應用程式，但不能同時選取這兩者。

### <a href="" id="settings-do-not-synchronization-when-network-share-is-outside-user-s-domain"></a>當網路共用超出使用者網域時，設定不會同步處理

當 Windows®8嘗試作業系統設定同步處理時，同步處理失敗，並出現下列錯誤訊息：**提升：： filesystem：：存在：：不正確的使用者名稱或密碼**。 這個錯誤可能表示網路共用是在使用者網域以外，或是具有該網域之信任關係的網域。 若要檢查作業記錄事件，請開啟**事件檢視器**，然後流覽到**應用程式和服務記錄**  /  **Microsoft**  /  **使用者體驗虛擬化**  /  **記錄**作業  /  **運作**。 UE-V 設定儲存位置所用的網路共用，應該位於同一個 Active Directory 網域中，作為使用者或使用者網域的信任網域。

因應措施 **：** 使用與使用者相同 Active Directory 網域的網路共用。

### 已安裝 Office 2010 和 Office 2013 時無法預料的結果

當使用者同時安裝 Office 2010 和 Office 2013 時，兩個版本的 Office 之間的任何常見設定都是由 UE-V 漫遊。 這可能會導致 Office 2010 套件大小太大，或導致無法預知的2013衝突，特別是在使用 Office 365 的情況下。

因應措施 **：** 只安裝一個 Office 版本或限制哪些設定是由 UE-V 同步處理。

### 卸載並重新安裝 Windows 8 應用程式會將設定還原成初始狀態

在 Windows 8 應用程式使用 UE-V 設定同步處理時，如果使用者卸載應用程式，然後重新安裝應用程式，應用程式的設定就會還原為預設值。發生這種情況是因為卸載會移除 app 設定的本機（快取）複本，但不會移除本機 UE-V 設定套件。當應用程式重新安裝並啟動時，UE-V 會收集重設為 app 預設值的 app 設定，然後將預設設定上傳到中央儲存位置。其他執行 app 的電腦，然後下載預設設定。這種行為與桌面應用程式的行為完全相同。

因應措施 **：** 所有.

### Outlook 2010 的電子郵件簽名漫遊

UE-V 會在裝置之間漫遊 Outlook 2010 簽名檔案。 不過，新郵件和回復或轉寄的預設簽章選項不會同步處理。 這兩個設定會儲存在 Outlook 設定檔中，而 UE-V 不會漫遊。

因應措施 **：** 所有.

### UE-V 不支援32位與64位版本的 Microsoft Office 之間的漫遊設定

我們建議您安裝適用于新式電腦的64位版本的 Microsoft Office。 若要判斷您需要哪個版本，請[按一下這裡](https://support.office.com/article/choose-between-the-64-bit-or-32-bit-version-of-office-2dee7807-8f95-4d0c-b5fe-6c6f49b8d261?ui=en-US&rs=en-US&ad=US#32or64Bit=Newer_Versions)。 UE-V 支援相同架構版本的 Office 間的漫遊設定。 例如，32位的 Office 設定將會在所有32位的 Office 實例之間漫遊。 UE-V 不支援32位與64位版本的 Office 之間的漫遊設定。

因應措施 **：** 所有

### <a href="" id="msi-s-are-not-localized"></a>MSI 未當地語系化

UE-V 2.0 包含 UE-V Agent 與 UE-V 發生器的當地語系化安裝程式。 這些 MSI 檔案仍可供使用，但使用者介面已最小化，且 MSI 只顯示英文。 雖然檔案是英文，但安裝程式會在安裝期間安裝所有支援的語言。

因應措施 **：** 所有

### 與 Internet Explorer 9 [我的最愛] 相關聯的 Favicons 不會漫遊

與 Internet Explorer 9 [我的最愛] 相關聯的 favicons 不會受到使用者體驗虛擬化的漫遊，而且在新電腦上出現 [我的最愛] 時不會出現。

因應措施 **：** 在 Internet Explorer 9 瀏覽器中使用書簽並將其放入後，Favicons 就會顯示關聯的 [我的最愛]。

### 檔案設定路徑儲存在註冊表中

某些應用程式設定會將其設定和設定檔案的路徑儲存為註冊表中的值。 當設定在電腦之間漫遊時，必須同步處理在登錄中作為路徑所參照的檔案。

因應措施 **：** 使用 [資料夾重新導向] 或其他一些技術，以確保任何被參照為檔案設定路徑的檔案，都存在並放在 [設定] 漫遊之所有電腦上的相同位置。

### 較長的設定儲存路徑可能會導致錯誤

讓設定的儲存路徑盡可能簡短。 長條路徑可以避免解析度或同步處理。 UE-V 會使用設定儲存路徑作為儲存設定的計算路徑的一部分。 該路徑的計算方式如下：設定儲存路徑 + "settingspackages" + 套件 dir （template ID） + 套件名稱（範本識別碼） +. pkgx。 如果該計算路徑超過260字元，套件儲存將會失敗，並會在 UE-V 操作事件記錄中產生下列錯誤訊息：

`[boost::filesystem::copy_file: The system cannot find the path specified]`

若要檢查操作記錄事件，請開啟事件檢視器，然後流覽到應用程式和服務記錄/Microsoft/使用者體驗虛擬化/記錄/運作。

因應措施 **：** 所有.

### 某些作業系統設定只會在相似的作業系統版本之間漫遊

[朗讀程式] 的作業系統設定和地區專用的貨幣字元（例如 [語言] 和 [地區設定]）只能在 Windows 等作業系統版本中漫遊。 例如，貨幣字元將無法在 Windows 7 和 Windows 8 之間漫遊。

因應措施 **：** 所有

### 當應用程式在意外關閉後重新開機時，Windows 8 應用程式不會同步處理設定

如果 Windows 8 應用程式在啟動後意外關閉，則重新開機應用程式時，可能無法同步處理應用程式的設定。

因應措施 **：** 關閉 Windows 8 應用程式，關閉並重新啟動 UevAppMonitor.exe 應用程式（可以使用 TaskManager），然後重新開機 Windows 8 應用程式。

### <a href="" id="ue-v-1-agent-generates-errors-when-running-ue-v-2-templates-"></a>UE-V 1 agent 在執行 UE-V 2 範本時會產生錯誤

如果將 UE-V 2 設定位置範本發佈到與 UE-V 1 agent 一起安裝的電腦，部分設定將無法在電腦之間同步處理，以及在事件記錄檔中報告錯誤。

因應措施 **：** 從 UE-V 1 遷移到 UE-V 2 時，您可能會有電腦在執行舊版的代理程式，建立個別的 UE-V 2.0 目錄來支援 UE-V 2.0 代理程式和範本。

## UE-V 2.0 的修補程式和知識庫文章


本節包含適用于 UE-V 2.0 的修補程式和知識庫文章。

<table>
<colgroup>
<col width="33%" />
<col width="33%" />
<col width="33%" />
</colgroup>
<thead>
<tr class="header">
<th align="left"><strong>知識庫文章</strong></th>
<th align="left">Title</th>
<th align="left"><strong>連結</strong></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>2927019</p></td>
<td align="left"><p>Microsoft 使用者體驗虛擬化2.0 的修補程式套件1</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2927019" data-raw-source="[support.microsoft.com/kb/2927019](https://support.microsoft.com/kb/2927019)">support.microsoft.com/kb/2927019</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2903501</p></td>
<td align="left"><p>UE-V：使用者體驗虛擬化（UE-V）與使用者設定檔的相容性</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2903501/EN-US" data-raw-source="[support.microsoft.com/kb/2903501/EN-US](https://support.microsoft.com/kb/2903501/EN-US)">support.microsoft.com/kb/2903501/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2770042</p></td>
<td align="left"><p>UE-V 註冊表設定</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2770042/EN-US" data-raw-source="[support.microsoft.com/kb/2770042/EN-US](https://support.microsoft.com/kb/2770042/EN-US)">support.microsoft.com/kb/2770042/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2847017</p></td>
<td align="left"><p>由 Internet Explorer 複製的 UE-V 設定</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2847017/EN-US" data-raw-source="[support.microsoft.com/kb/2847017/EN-US](https://support.microsoft.com/kb/2847017/EN-US)">support.microsoft.com/kb/2847017/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2930271</p></td>
<td align="left"><p>瞭解 Microsoft UE-V 中的漫遊 Outlook 簽名限制</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2930271/EN-US" data-raw-source="[support.microsoft.com/kb/2930271/EN-US](https://support.microsoft.com/kb/2930271/EN-US)">support.microsoft.com/kb/2930271/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2769631</p></td>
<td align="left"><p>如何修復損毀的 UE-V 安裝</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2769631/EN-US" data-raw-source="[support.microsoft.com/kb/2769631/EN-US](https://support.microsoft.com/kb/2769631/EN-US)">support.microsoft.com/kb/2769631/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2850989</p></td>
<td align="left"><p>不支援使用 Microsoft UE-V 遷移 MAPI 設定檔</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2850989/EN-US" data-raw-source="[support.microsoft.com/kb/2850989/EN-US](https://support.microsoft.com/kb/2850989/EN-US)">support.microsoft.com/kb/2850989/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2769586</p></td>
<td align="left"><p>UE-V 會漫遊空白資料夾和登錄機碼</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2769586/EN-US" data-raw-source="[support.microsoft.com/kb/2769586/EN-US](https://support.microsoft.com/kb/2769586/EN-US)">support.microsoft.com/kb/2769586/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2782997</p></td>
<td align="left"><p>如何在 Microsoft 使用者體驗虛擬化（UE-V）中啟用調試記錄</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2782997/EN-US" data-raw-source="[support.microsoft.com/kb/2782997/EN-US](https://support.microsoft.com/kb/2782997/EN-US)">support.microsoft.com/kb/2782997/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2769570</p></td>
<td align="left"><p>UE-V 不會在 RDS 或 VDI 會話上更新主題</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2769570/EN-US" data-raw-source="[support.microsoft.com/kb/2769570/EN-US](https://support.microsoft.com/kb/2769570/EN-US)">support.microsoft.com/kb/2769570/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2901856</p></td>
<td align="left"><p>在啟用 UE-V 的電腦上強制重新開機後，應用程式設定不會同步處理</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2901856/EN-US" data-raw-source="[support.microsoft.com/kb/2901856/EN-US](https://support.microsoft.com/kb/2901856/EN-US)">support.microsoft.com/kb/2901856/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2850582</p></td>
<td align="left"><p>如何在 App V 應用程式中使用 Microsoft 使用者體驗虛擬化</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2850582/EN-US" data-raw-source="[support.microsoft.com/kb/2850582/EN-US](https://support.microsoft.com/kb/2850582/EN-US)">support.microsoft.com/kb/2850582/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>3041879</p></td>
<td align="left"><p>Microsoft 使用者體驗虛擬化的目前檔版本</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/3041879/EN-US" data-raw-source="[support.microsoft.com/kb/3041879/EN-US](https://support.microsoft.com/kb/3041879/EN-US)">support.microsoft.com/kb/3041879/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2843592</p></td>
<td align="left"><p>使用者體驗虛擬化與高可用性的相關資訊</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2843592/EN-US" data-raw-source="[support.microsoft.com/kb/2843592/EN-US](https://support.microsoft.com/kb/2843592/EN-US)">support.microsoft.com/kb/2843592/EN-US</a></p></td>
</tr>
</tbody>
</table>

 

 

 





