---
title: Microsoft User Experience Virtualization (UE-V) 2.1 SP1 版本資訊
description: Microsoft User Experience Virtualization (UE-V) 2.1 SP1 版本資訊
author: dansimp
ms.assetid: 561988c4-cc5c-4e15-970b-16e942c8f2ef
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 03/30/2017
ms.openlocfilehash: 974914421c61c829b5a32e336bddf8ea1addf514
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811211"
---
# Microsoft User Experience Virtualization (UE-V) 2.1 SP1 版本資訊


若要搜尋 Microsoft 使用者體驗虛擬化 2.1 SP1 版本資訊，請按 Ctrl + F。

您必須先閱讀這些版本資訊，才能安裝 UE-V。 版本資訊包含成功安裝使用者體驗虛擬化所需的資訊，並包含產品檔中不提供的其他資訊。 如果這些版本資訊與其他 UE-V 檔之間有差異，最新的變更應該視為權威性。 這些版本資訊取代本產品隨附的內容。

## 提供意見反應


向我們提供您的意見反應與意見反應，告訴我們您對 MDOP 檔的想法。 將您的檔意見反應傳送給[mdopdocs@microsoft.com](mailto:mdopdocs@microsoft.com?subject=UE-V%20Documentation)。

## UE-V 已知問題


本節包含適用于使用者體驗虛擬化 2.1 SP1 的版本資訊。

### 用於 Skype 的 UE-V 設定位置範本會造成 Skype 損毀

當使用者為 Skype 傳統型應用程式產生有效的設定位置範本時，會進行註冊，然後啟動 Skype 桌面應用程式，Skype 會當機。 會在應用程式事件記錄檔中記錄 [存取 \ _VIOLATION]。

因應措施：移除或取消註冊 Skype 範本，以允許 Skype 再次運作。

### 自行安裝 UE-V 的現有腳本可能失敗

在安裝 UE-V 2.1 SP1 時，對 UE-V 安裝程式所做的兩項變更可能會造成在舊版 UE-V 中使用的緘默安裝腳本無法正常運作。 第一項是使用者必須接受授權條款並同意或拒絕參與客戶經驗改進計畫（CEIP）的新需求（即使是在緘默安裝期間也一樣）。 使用/q 參數已不再足夠，以表示接受授權條款與合約參與 CEIP。

其次，安裝程式現在會在安裝 UE-V Agent 之後強制重新開機電腦。 這可能會導致安裝腳本在不需要重新開機時失敗（例如，它會先安裝 UE-V Agent，然後立即安裝發生器）。

解決方法： UE-V 安裝程式（.msi）有兩個支援緘默安裝的新命令列參數。

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
<td align="left"><p><strong>/ACCEPTLICENSETERMS = True</strong></p></td>
<td align="left"><p>將此參數設定為 <strong> True </strong> 以自行安裝 ue-v。 新增此參數表示使用者接受在這裡找到（預設為）的 UE-V 授權條款：%ProgramFiles%\Microsoft 使用者體驗 Virtualization\Agent</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>/NORESTART</strong></p></td>
<td align="left"><p>此參數可避免在安裝 UE-V agent 之後強制重新開機。 3010的傳回代碼表示在使用 UE-V 之前需要重新開機。</p></td>
</tr>
</tbody>
</table>

 

### 在同一部電腦上的 App-v 與原生應用程式之間的登錄設定無法同步處理

當電腦的應用程式是透過應用程式虛擬化（App-v）安裝並在本機使用 Windows Installer （.msi）檔案時，以註冊表為基礎的設定不會在技術之間同步處理。

因應措施：若要解決此問題，請選取其中一種技術來執行應用程式，但不能同時選取兩者。

### 已安裝 Office 2010 和 Office 2013 時無法預料的結果

當使用者同時安裝 Office 2010 和 Office 2013 時，兩個版本的 Office 之間的任何常見設定都是由 UE-V 漫遊。 這可能會導致 Office 2010 套件大小太大，或導致無法預知的2013衝突，特別是在使用 Office 365 的情況下。

因應措施：只安裝一個 Office 版本，或限制由 UE-V 同步處理哪些設定。

### 卸載並重新安裝 Windows 8 應用程式會將設定還原成初始狀態

在 Windows 8 應用程式使用 UE-V 設定同步處理時，如果使用者卸載應用程式，然後重新安裝應用程式，應用程式的設定就會還原為預設值。發生這種情況是因為卸載會移除 app 設定的本機（快取）複本，但不會移除本機 UE-V 設定套件。當應用程式重新安裝並啟動時，UE-V 會收集重設為 app 預設值的 app 設定，然後將預設設定上傳到中央儲存位置。其他執行 app 的電腦，然後下載預設設定。這種行為與桌面應用程式的行為完全相同。

因應措施：無。

### UE-V 不支援32位與64位版本的 Microsoft Office 之間的漫遊設定

我們建議您為32位和64位作業系統安裝32位版本的 Microsoft Office。 若要選擇您需要的 Microsoft Office 版本，請按一下這裡。 ([http://office.microsoft.com/word-help/choose-the-32-bit-or-64-bit-version-of-microsoft-office-HA010369476.aspx](https://go.microsoft.com/fwlink/?LinkID=247623)). UE-V 支援相同架構版本的 Office 間的漫遊設定。 例如，32位的 Office 設定將會在所有32位的 Office 實例之間漫遊。 UE-V 不支援32位與64位版本的 Office 之間的漫遊設定。

因應措施：無

### <a href="" id="msi-s-are-not-localized"></a>MSI 未當地語系化

UE-V 包含針對 UE-V Agent 和 UE-V 發生器的當地語系化安裝程式。 這些 MSI 檔案仍可供使用，但使用者介面已最小化，且 MSI 只顯示英文。 雖然檔案是英文，但安裝程式會在安裝期間安裝所有支援的語言。

因應措施：無

### 與 Internet Explorer 9 [我的最愛] 相關聯的 Favicons 不會漫遊

與 Internet Explorer 9 [我的最愛] 相關聯的 favicons 不會受到使用者體驗虛擬化的漫遊，而且在新電腦上出現 [我的最愛] 時不會出現。

因應措施：當您使用書簽並將其放入 Internet Explorer 9 瀏覽器中後，就會顯示 Favicons 的相關連絡人。

### 檔案設定路徑儲存在註冊表中

某些應用程式設定會將其設定和設定檔案的路徑儲存為註冊表中的值。 當設定在電腦之間漫遊時，必須同步處理在登錄中作為路徑所參照的檔案。

因應措施：使用 [資料夾重新導向] 或其他技術，以確保任何被參照為檔案設定路徑的檔案都存在並放在 [設定] 漫遊之所有電腦上的相同位置。

### 較長的設定儲存路徑可能會導致錯誤

讓設定的儲存路徑盡可能簡短。 長條路徑可以避免解析度或同步處理。 UE-V 會使用設定儲存路徑作為儲存設定的計算路徑的一部分。 該路徑的計算方式如下：設定儲存路徑 + "settingspackages" + 套件 dir （template ID） + 套件名稱（範本識別碼） +. pkgx。 如果該計算路徑超過260字元，套件儲存將會失敗，並會在 UE-V 操作事件記錄中產生下列錯誤訊息：

`[boost::filesystem::copy_file: The system cannot find the path specified]`

若要檢查操作記錄事件，請開啟事件檢視器，然後流覽到應用程式和服務記錄/Microsoft/使用者體驗虛擬化/記錄/運作。

因應措施：無。

### 某些作業系統設定只會在相似的作業系統版本之間漫遊

[朗讀程式] 的作業系統設定和地區專用的貨幣字元（例如 [語言] 和 [地區設定]）只能在 Windows 等作業系統版本中漫遊。 例如，貨幣字元將無法在 Windows 7 和 Windows 8 之間漫遊。

因應措施：無

### <a href="" id="ue-v-1-agent-generates-errors-when-running-ue-v-2-templates-"></a>UE-V 1 agent 在執行 UE-V 2 範本時會產生錯誤

如果將 UE-V 2 設定位置範本發佈到與 UE-V 1 agent 一起安裝的電腦，部分設定將無法在電腦之間同步處理，以及在事件記錄檔中報告錯誤。

因應措施：從 UE-V 1 遷移到 UE-V 2 時，您可能會在電腦上執行舊版的代理程式，建立個別的 UE-V 2. 編目，以支援 UE-V a.x Agent 和範本。

### UE-V 登出延遲

在登出時，UE-V 會花很長的時間同步處理設定。 這通常是由於高延遲網路或不正確使用 Distrubuted 檔案系統（DFS）所造成。
如需 DFS 支援，請參閱關於[複製的使用者設定檔資料的 Microsoft 支援聲明](https://support.microsoft.com/kb/2533009)，以取得進一步的詳細資料。

因應措施：從 HF03 開始，新的登錄機碼已引進下列登錄機碼提供一種機制，讓您可以指定最大的登出延遲 \\Software\\Microsoft\\UEV\\Agent\\Configuration\\LogOffWaitInterval

如需詳細資訊，請參閱[ue-v 註冊表設定](https://support.microsoft.com/kb/2770042)

## UE-V 2.1 SP1 的修補程式和知識庫文章


本節包含適用于 UE-V 2.1 SP1 的修補程式和知識庫文章。

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
<td align="left"><p>3018608</p></td>
<td align="left"><p>UE-V 2.1-當缺少 UE-V WMI 類別時，TemplateConsole.exe 會當機</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/3018608/EN-US" data-raw-source="[support.microsoft.com/kb/3018608/EN-US](https://support.microsoft.com/kb/3018608/EN-US)">support.microsoft.com/kb/3018608/EN-US</a></p></td>
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
<td align="left"><p>2769631</p></td>
<td align="left"><p>如何修復損毀的 UE-V 安裝</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2769631/EN-US" data-raw-source="[support.microsoft.com/kb/2769631/EN-US](https://support.microsoft.com/kb/2769631/EN-US)">support.microsoft.com/kb/2769631/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2850989</p></td>
<td align="left"><p>不支援使用 Microsoft UE-V 遷移 MAPI 設定檔</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2850989/EN-US" data-raw-source="[support.microsoft.com/kb/2850989/EN-US](https://support.microsoft.com/kb/2850989/EN-US)">support.microsoft.com/kb/2850989/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2769586</p></td>
<td align="left"><p>UE-V 會漫遊空白資料夾和登錄機碼</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2769586/EN-US" data-raw-source="[support.microsoft.com/kb/2769586/EN-US](https://support.microsoft.com/kb/2769586/EN-US)">support.microsoft.com/kb/2769586/EN-US</a></p></td>
</tr>
<tr class="even">
<td align="left"><p>2782997</p></td>
<td align="left"><p>如何在 Microsoft 使用者體驗虛擬化（UE-V）中啟用調試記錄</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2782997/EN-US" data-raw-source="[support.microsoft.com/kb/2782997/EN-US](https://support.microsoft.com/kb/2782997/EN-US)">support.microsoft.com/kb/2782997/EN-US</a></p></td>
</tr>
<tr class="odd">
<td align="left"><p>2769570</p></td>
<td align="left"><p>UE-V 不會在 RDS 或 VDI 會話上更新主題</p></td>
<td align="left"><p><a href="https://support.microsoft.com/kb/2769570/EN-US" data-raw-source="[support.microsoft.com/kb/2769570/EN-US](https://support.microsoft.com/kb/2769570/EN-US)">support.microsoft.com/kb/2769570/EN-US</a></p></td>
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

 






 

 





