---
title: 變更 UE-V 2. x 排程任務的頻率
description: 變更 UE-V 2. x 排程任務的頻率
author: dansimp
ms.assetid: ee486570-c6cf-4fd9-ba48-0059ba877c10
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 09/29/2016
ms.openlocfilehash: 1c1e3c091431dc56068dcd1fe0e849b0df1f6aa0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10810550"
---
# 變更 UE-V 2. x 排程任務的頻率


Microsoft 使用者體驗虛擬化（UE-V）2.0、2.1 或 2.1 SP1 代理安裝程式（AgentSetup.exe）會在 UE-V Agent 安裝期間建立下列排程的任務：

-   **監視應用程式設定**

-   **同步處理控制器應用程式**

-   **在登出時同步處理設定**

-   **範本自動更新**

-   **收集 CEIP 資料**

-   **上傳 CEIP 資料**

**記事** 除收集 CEIP 資料以外，這些工作必須保持啟用，因為 UE-V 無法正常運作。

 

這些排程的任務無法使用 UE-V 工具進行設定。 如果系統管理員想要變更這些專案的排程任務，就可以建立使用 Schtasks.exe 命令列選項的腳本。

如需 Schtasks.exe 的詳細資訊，請參閱[如何使用 Schtasks、exe 來排程 Windows Server 2003 中的任務](https://go.microsoft.com/fwlink/?LinkID=264854)。

如需詳細資訊，請參閱

## UE-V 排程的任務


下列排程的任務包含在 UE-V 2 中，並提供範例排程任務設定命令。

### 收集 CEIP 資料

如果您在安裝的使用者或系統管理員 choses 參與客戶經驗改進計畫（CEIP），UE-V 會收集資料，以協助改善未來版本中的產品。 只有在登入時，才會執行此排程的工作。 [**收集 CEIP 資料**] 任務會執行 UevSqmSession.exe，該作業位於 ue-v agent 安裝目錄中。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">任務名稱</th>
<th align="left">預設事件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>\Microsoft\UE-V\Collect CEIP 資料</p></td>
<td align="left"><p>標識</p></td>
</tr>
</tbody>
</table>

 

### 監視應用程式設定

[**監視應用程式設定**] 工作是用來同步處理 Windows 應用程式的設定。 它會在登入，但延遲為30秒，不會影響登入 detrimentally。 [監視應用程式狀態] 任務會執行位於 UE-V Agent 安裝目錄中的 UevAppMonitor.exe 檔案。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">任務名稱</th>
<th align="left">預設事件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>\Microsoft\UE-V\Monitor 應用程式狀態</p></td>
<td align="left"><p>標識</p></td>
</tr>
</tbody>
</table>

 

### 同步處理控制器應用程式

**同步處理控制器應用程式**工作是用來啟動同步處理控制器，以便將電腦的設定同步處理到 [設定] 儲存位置。 根據預設，任務會每30分鐘執行一次。 此時，本機設定會同步處理至 [設定] 儲存位置，而設定儲存位置上的更新設定會同步處理到電腦。 同步控制器應用程式會執行 Microsoft.Uev.SyncController.exe，該位於 UE-V Agent 安裝目錄中。
**注意：** 根據 [**監視器應用程式設定**] 工作，此工作是在登入時執行，但延遲為30秒，不會影響登入 detrimentally。
<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">任務名稱</th>
<th align="left">預設事件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>\Microsoft\UE-V\Sync 控制器應用程式</p></td>
<td align="left"><p>登入，此後每30分鐘</p></td>
</tr>
</tbody>
</table>

 

例如，下列命令會將 agent 設定為每15分鐘同步處理設定，而不是預設的30分鐘。

``` syntax
Schtasks /change /tn “Microsoft\UE-V\Sync Controller Application” /ri 15
```

### 在登出時同步處理設定

[登出工作] 的 [**同步處理設定**] 是用來在登錄時啟動應用程式，以控制應用程式在 ue-v 登出時的同步處理。 [登出] 工作的 [同步處理設定] 會執行 Microsoft.Uev.SyncController.exe 檔案，該檔案位於 UE-V Agent 安裝目錄中。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">任務名稱</th>
<th align="left">預設事件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>登出時的 \Microsoft\UE-V\Synchronize 設定</p></td>
<td align="left"><p>標識</p></td>
</tr>
</tbody>
</table>

 

### 範本自動更新

**範本自動更新**工作會檢查 [設定] 範本目錄，以瞭解新的、更新或移除的範本。 只有在 SettingsTemplateCatalog 已設定的情況下，才會執行此工作。 **範本自動更新**工作會執行 ApplySettingsCatalog.exe 檔案，該檔案位於 ue-v agent 安裝目錄中。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">任務名稱</th>
<th align="left">預設事件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>\Microsoft\UE-V\Template 自動更新</p></td>
<td align="left"><p>在1小時視窗中的隨機時間內，于每日的系統啟動和每天3:30</p></td>
</tr>
</tbody>
</table>

 

**範例：** 下列命令會將 UE-V Agent 設定為每小時檢查設定範本的目錄存放區。

``` syntax
schtasks /change /tn "Microsoft\UE-V\Template Auto Update" /ri 60
```

### 上傳 CEIP 資料

如果使用者或系統管理員選擇參與客戶經驗改進計畫（CEIP），則會在安裝期間，**上傳 CEIP 資料**工作會執行。 此工作會將資料上傳到您用來協助改善產品以供將來版本 UE-V 發行之 CEIP 伺服器。 此排程的任務會在登入之後每隔4小時執行一次。 [**上傳 CEIP 資料**] 任務會執行 UevSqmUploader.exe 檔案，該檔案位於 ue-v agent 安裝目錄中。

<table>
<colgroup>
<col width="50%" />
<col width="50%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">任務名稱</th>
<th align="left">預設事件</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>\Microsoft\UE-V\Upload CEIP 資料</p></td>
<td align="left"><p>登入及每4小時</p></td>
</tr>
</tbody>
</table>

 

## UE-V 2 排程的任務詳細資料


下列圖表提供 UE-V 2 排程任務的其他相關資訊：

<table style="width:100%;">
<colgroup>
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
<col width="16%" />
</colgroup>
<tbody>
<tr class="odd">
<td align="left"><p><strong>任務名稱 </strong> （檔案名）</p></td>
<td align="left"><p><strong>預設頻率</strong></p></td>
<td align="left"><p><strong>Power 開關</strong></p></td>
<td align="left"><p><strong>僅空閒</strong></p></td>
<td align="left"><p><strong>網路連線</strong></p></td>
<td align="left"><p><strong>描述</strong></p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>監視應用程式設定 </strong> （UevAppMonitor.exe）</p></td>
<td align="left"><p>登入後的30秒後開始，並持續至登出。</p></td>
<td align="left"><p>不可以</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>無</p></td>
<td align="left"><p>同步處理 Windows （AppX）應用程式的設定。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>同步處理控制器應用程式 </strong> （Microsoft.Uev.SyncController.exe）</p></td>
<td align="left"><p>登入及此後每30分鐘。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>僅在網路已連線的情況</p></td>
<td align="left"><p>啟動同步處理控制器，將本機設定與設定儲存位置同步處理。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>在登出時同步處理設定 </strong> （Microsoft.Uev.SyncController.exe）</p></td>
<td align="left"><p>登入，然後等待登出同步處理設定。</p></td>
<td align="left"><p>不可以</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>無</p></td>
<td align="left"><p>在登入時啟動應用程式，以控制應用程式在登出時的同步處理。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>範本自動更新 </strong> （ApplySettingsCatalog.exe）</p></td>
<td align="left"><p>在最初登入時執行，此後每天的3:30 會執行。</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>否</p></td>
<td align="left"><p>無</p></td>
<td align="left"><p>針對新的、更新的或已移除的範本，檢查設定範本目錄。 只有在設定 SettingsTemplateCatalog 之後，才能執行此工作。</p></td>
</tr>
<tr class="even">
<td align="left"><p><strong>收集 CEIP 資料 </strong> （UevSqmSession.exe）</p></td>
<td align="left"><p>登入後啟動服務</p></td>
<td align="left"><p>否</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>無</p></td>
<td align="left"><p>如果使用者或系統管理員將您加入客戶經驗改進計畫（CEIP），此任務會收集可協助改善 UE-V 未來發行的資料。</p></td>
</tr>
<tr class="odd">
<td align="left"><p><strong>上傳 CEIP 資料 </strong> （UevSqmUploader.exe）</p></td>
<td align="left"><p>在登入之後，每一天的 4:00 AM 都會執行。</p></td>
<td align="left"><p>否</p></td>
<td align="left"><p>是</p></td>
<td align="left"><p>僅在網路已連線的情況</p></td>
<td align="left"><p>如果使用者或系統管理員將您加入客戶經驗改進計畫（CEIP），此任務會將資料上傳到 CEIP 伺服器。</p></td>
</tr>
</tbody>
</table>

 

**說明**

-   [**電源] 開關**– [任務排程器] 會在未連線到交流電源時，優化電源使用量。 如果電腦切換至電池電源，工作可能會停止執行。

-   [**只有空閒**]-如果電腦停止閒置，工作就會停止執行。 根據預設，當電腦再次空閒時，任務不會重新開機。 相反，任務會在下一個工作觸發程式再次開始。

-   **網路**連線–標示為「是」的工作只有在電腦有可用的網路連線時才會執行。 無論網路連通性為何，標示為「N/A」的工作。

### 如何管理排程任務

若要尋找排程的任務，請執行下列動作：

1.  在使用者電腦上開啟「排程任務」。

2.  流覽至：任務排程器-工作排程器文檔 &gt; 庫- &gt; Microsoft- &gt; ue-v

3.  在 [詳細資料] 窗格中，選取您想要管理和設定的排程任務。

### 其他資訊

下列額外資訊適用于 UE-V 排程的任務：

-   [ll] 任務序列程式是位於 UE-V Agent 安裝資料夾（ `%programFiles%\Microsoft User Experience Virtualization\Agent\[architecture]\` 依預設）。

-   當 UE-V SyncMethod 設定為 "SyncProvider" （UE-V 2 預設設定）時，同步處理控制器應用程式排程任務是重要的元件。 這個排程的工作會使 SettingsSToragePath 與本機快取設定套件檔案的版本保持同步。 如果使用者抱怨設定不會經常同步處理，則您可以將排程的任務設定減少為1分鐘。如有需要，您也可以將30分鐘預設值增加至較高的金額。 如果使用者抱怨在登入時設定的同步處理速度不夠快，您可以移除排程任務的 [延遲] 設定。 （您可以在 [**編輯觸發**] 對話方塊中找到 [延遲] 設定

-   如果您使用其他方法讓用戶端的範本保持同步（亦即群組原則或 Configuration Manager 比較基準），就不需要停用範本自動更新排程的工作。 保留 SettingsTemplateCatalog 屬性值為空白，可避免 UE-V 檢查自訂範本的設定目錄。 這個排程的任務 ApplySettingsCatalog.exe 會執行，主要會立即返回。

-   [監視應用程式設定排程的工作] 會即時更新 Windows 應用程式（AppX）設定，根據每個 app 內建的 Windows 應用程式設定觸發程式。






## 相關主題


[管理 UE-V 2。](administering-ue-v-2x-new-uevv2.md)

[部署自訂應用程式的 UE-V 2. x](deploy-ue-v-2x-for-custom-applications-new-uevv2.md#deploycatalogue)

 

 





