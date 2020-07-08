---
title: MED-V 事件記錄檔訊息
description: MED-V 事件記錄檔訊息
author: dansimp
ms.assetid: 7ba7344d-153b-4cc4-a00a-5d42aee9986b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: b5d8dcf1cce48d6c1e29d46b4db7ac1550aa9477
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809740"
---
# MED-V 事件記錄檔訊息


Microsoft 企業版桌面虛擬化（MED-V）2.0 的記錄檔提供有關如何在企業中部署和管理 MED-V 的詳細資訊，並協助驗證功能或協助您解決問題。

## 事件識別碼


以下是 MED-V 事件識別碼的清單，可協助您在部署或管理 MED-V 時所遇到的問題進行疑難排解。

### Fts

顯示第一次設定的 [事件識別碼]。

### 事件 ID 3066

啟動虛擬機器操作失敗。

<a href="" id="description"></a>**描述**  
您用來建立 MED-V 工作區的虛擬硬碟（VHD）可能存在問題。

<a href="" id="solution"></a>**解決方案**  
請確認您可以使用 med-v 進行 med-v，然後啟動該虛擬機器。

### 事件 ID 3071

虛擬機器準備失敗。

<a href="" id="description"></a>**描述**  
第一次設定可能是由許多不同的問題所造成的，因此發生問題。 這包括網路連線的問題。

<a href="" id="solution"></a>**解決方案**  
重新開機 MED-V 主機代理程式，以便在第一次安裝時重新執行。

### 事件 ID 3078

虛擬機器準備失敗。

<a href="" id="description"></a>**描述**  
您用來建立 MED-V 工作區的 VHD 可能存在問題。

<a href="" id="solution"></a>**解決方案**  
請確認您可以使用 med-v 進行 med-v，然後啟動該虛擬機器。

### 事件 ID 3079

正在重新嘗試虛擬機器。

<a href="" id="description"></a>**描述**  
MED-V 正在嘗試準備虛擬機器。

<a href="" id="solution"></a>**解決方案**  
不需要執行任何動作。 [第一次設定完成]。

### 事件 ID 3080

用戶端在準備虛擬機器時已停止。

<a href="" id="description"></a>**描述**  
MED-V 在嘗試準備虛擬機器時，會意外停止。

<a href="" id="solution"></a>**解決方案**  
啟動 MED-V 主機代理程式，並讓第一次設定完成

### 事件 ID 3084

虛擬機器無效。 第一次需要重新執行設定。

<a href="" id="description"></a>**描述**  
MED-V 主機代理程式偵測到虛擬機器的問題。

<a href="" id="solution"></a>**解決方案**  
不需要執行任何動作。 [第一次設定完成]。

### 事件 ID 3099

啟動虛擬機器的呼叫失敗。

<a href="" id="description"></a>**描述**  
您用來建立 MED-V 工作區的 VHD 可能存在問題。

<a href="" id="solution"></a>**解決方案**  
確認您可以使用 med-v 進行 med-v，然後才能開啟虛擬機器。

### VM 管理

### 事件 ID 4022

向 VM 發出命令時發生 VMManagerException 致命錯誤。

<a href="" id="description"></a>**描述**  
最終使用者嘗試登入，或關閉 MED-V 主機來結束 MED-V，且超過 VMTaskTimeout 設定設定。

<a href="" id="solution"></a>**解決方案**  
重新開機 MED-V。

### 事件 ID 4028

VM 操作超時。

<a href="" id="description"></a>**描述**  
最終使用者嘗試登入，或關閉主機，並超過 VMTaskTimeout 設定設定，即可結束 MED-V。

<a href="" id="solution"></a>**解決方案**  
重新開機 MED-V。

### 事件 ID 4038

Vmsal 已將錯誤訊息張貼給使用者。

<a href="" id="description"></a>**描述**  
系統會向最終使用者顯示錯誤訊息，指出 MED-V 無法啟動虛擬應用程式。

<a href="" id="solution"></a>**解決方案**  
如果錯誤是在一列中記錄兩次以上的時間，請停止 MED-V 並使用 Windows Virtual PC 主控台連線至虛擬機器，並嘗試以全螢幕啟動應用程式。

### 事件 ID 4040

因為未在來賓中初始化 TerminalServices，所以回收新增功能。

<a href="" id="description"></a>**描述**  
MED-V 已重新開機虛擬機器，因為遠端桌面服務未在虛擬機器上初始化。

<a href="" id="solution"></a>**解決方案**  
如果錯誤是在一列中記錄兩次以上的時間，請停止 MED-V 並使用 Windows Virtual PC 主控台連線至虛擬機器。

### 事件 ID 4042

無法回收來賓中的新增功能。

<a href="" id="description"></a>**描述**  
MED-V 無法回收虛擬機器上的虛擬機器新增功能。

<a href="" id="solution"></a>**解決方案**  
如果錯誤是在一列中記錄兩次以上的時間，請停止 MED-V 並使用 Windows Virtual PC 主控台連線至虛擬機器。

### 事件 ID 4043

無法在虛擬機器中重設過期的密碼。

<a href="" id="description"></a>**描述**  
最終使用者未在虛擬機器中重設密碼，已過期。 因此，使用者可能無法存取網路資源或儲存工作。

<a href="" id="solution"></a>**解決方案**  
關閉 MED-V 來賓，然後重新開機它。

### URL 重新導向

### 事件 ID 5005

無法從配置取得 VM 名稱;無法啟動來賓瀏覽器。

<a href="" id="description"></a>**描述**  
URL 重新導向無法從配置取得 MED-V 工作區名稱。 因此，它無法通知 Windows 虛擬電腦在 MED-V 工作區瀏覽器中開啟重新導向的 URL。

<a href="" id="solution"></a>**解決方案**  
確定 MED-V 工作區名稱已設定，且與 C:\\Users\\ &lt; *使用者* &gt; \\Virtual 電腦目錄中的虛擬電腦名稱稱相符。 MED-V 工作區名稱位於 HKLM\\SOFTWARE\\Microsoft\\Medv\\v2\\VM\\Name。

例如，如果使用者是 "Matt"，而工作區名稱是 "mattsworkspace"，HKLM\\SOFTWARE\\Microsoft\\Medv\\v2\\VM\\Name 的值應該是 "mattsworkspace"，且應該有一個名為 C:\\Users\\Matt\\Virtual Machines\\mattsworkspace.vcmx. 的檔案。

### 事件 ID 5006

無法建立管道伺服器。

<a href="" id="description"></a>**描述**  
URL 重新導向服務無法建立管道伺服器來與 Internet Explorer 進行通訊。

<a href="" id="solution"></a>**解決方案**  
檢查系統事件記錄，以嘗試建立路徑開頭如下所示的檔案或資源： "\\\\.\\pipe\\MEDVUrlRedirectionPipe\_"，並以使用者的使用者名稱和功能變數名稱結束。 如果事件記錄中不存在這項功能，請重新開機電腦。

### ConfigMgr （來賓）

### 事件 ID 7001

主機網路設定資料格式不正確。

<a href="" id="description"></a>**描述**  
從主機接收的網路設定是格式不正確的 XML 字串，或從主機傳回的網路資訊無法寫入 XML 檔。

<a href="" id="solution"></a>**解決方案**  
重新開機主機電腦和虛擬機器。

### 事件 ID 7005

已偵測到主機網路設定的變更，但由於主機網路設定資料格式不正確而無法套用。

<a href="" id="description"></a>**描述**  
主機網路設定的變更已傳送到虛擬機器，但無法在虛擬機器中處理，因為錯誤。 此錯誤可能是因為資料格式不正確，或無法將資訊設定成 Windows Management Instrumentation （WMI） CCMNetworkAdapter 實例。

<a href="" id="solution"></a>**解決方案**  
重新開機主機和虛擬機器。

### ConfigMgr （主機）

### 事件 ID 8006

找不到虛擬機器。

<a href="" id="description"></a>**描述**  
Windows Virtual 電腦7找不到虛擬機器。 虛擬機器可能已被刪除、移動、移除或存取遭到拒絕。

<a href="" id="solution"></a>**解決方案**  
重新安裝虛擬機器。

### 事件 ID 8008

無法檢索工作站的網路設定資訊。

<a href="" id="description"></a>**描述**  
無法從 MED-V 主機收集網路設定資訊，很可能是因為 .NET Framework 中的系統呼叫失敗。 如果從 MED-V 主機傳回的網路資訊無法寫入 XML 檔，也會發生此錯誤。

<a href="" id="solution"></a>**解決方案**  
重新開機主機工作站。

### 事件 ID 8010

無法在虛擬機器中設定網路設定資料。

<a href="" id="description"></a>**描述**  
MED-V hostnetwork 位址轉換（NAT）無法傳送到虛擬機器，很可能是因為虛擬機器處於錯誤的狀態，或未安裝或啟用 Windows 虛擬電腦的新增功能。

<a href="" id="solution"></a>**解決方案**  
關閉並重新啟動虛擬機器。 此外，您可能還需要重新安裝虛擬機器。

### 事件 ID 8011

無法在虛擬機器中重設網路設定資料。

<a href="" id="description"></a>**描述**  
MED-V hostnetwork 設定（橋）無法傳送到虛擬機器，很可能是因為虛擬機器處於錯誤狀態，或未安裝或啟用 Windows 虛擬電腦的新增功能。

<a href="" id="solution"></a>**解決方案**  
關閉並重新啟動虛擬機器。 此外，您可能還需要重新安裝虛擬機器。

### 印表機重新導向

### 事件 ID 9001

檔案許可權錯誤。

<a href="" id="description"></a>**描述**  
使用者無權存取開啟或建立要讀取的 MED-V 印表機檔案所需的資料夾。

<a href="" id="solution"></a>**解決方案**  
確認您可以存取 User\\AppData\\ 路徑，以及使用者有權讀取及寫入該路徑。 例如，如果使用者是 "Matt"，則路徑 C:\\Users\\Matt\\AppData\\ 和其中的所有檔案都應該有讀取和寫入權限。 如果它存在，則路徑 C:\\Users\\Matt\\AppData\\Local\\Microsoft\\MEDV\\v2\\ 及其中的所有檔案，都應該擁有讀取和寫入權限。

### 事件 ID 9002

檔案許可權錯誤。

<a href="" id="description"></a>**描述**  
使用者無權存取開啟或建立要寫入的 MED-V 印表機檔案所需的資料夾。

<a href="" id="solution"></a>**解決方案**  
確定可存取 User\\AppData\\ 路徑，且使用者有權讀取及寫入該路徑。 例如，如果使用者是「Matt」，則路徑 C:\\Users\\Matt\\AppData\\ 及其中的所有檔案都應該有讀取和寫入權限。 如果它存在，則路徑 C:\\Users\\Matt\\AppData\\Local\\Microsoft\\MEDV\\v2\\ 及其中的所有檔案，都應該擁有讀取和寫入權限。

### 事件 ID 9004

無法建立儲存 MEDV 印表機檔案的路徑。

<a href="" id="description"></a>**描述**  
印表機重新導向服務無法存取檔案，或無法建立儲存印表機資訊所需的目錄。

<a href="" id="solution"></a>**解決方案**  
確認您可以存取 User\\AppData\\ 路徑，以及使用者有權讀取及寫入該路徑。 例如，如果使用者是「Matt」，則路徑 C:\\Users\\Matt\\AppData\\ 及其中的所有檔案都應該有讀取和寫入權限。 如果它存在，則路徑 C:\\Users\\Matt\\AppData\\Local\\Microsoft\\MEDV\\v2\\ 及其中的所有檔案，都應該擁有讀取和寫入權限。

### 事件 ID 9005

無法從配置取得 VM 名稱;無法啟動來賓安裝程式。 無法更新 MED-V-未偵測到主機網路。

<a href="" id="description"></a>**描述**  
印表機重新導向服務無法從 MED-V 設定取得 MED-V 工作區名稱，而且無法通知 Windows Virtual 電腦在 MED-V 來賓上啟動安裝程式。

<a href="" id="solution"></a>**解決方案**  
確定 MED-V 工作區名稱已設定，且與 C:\\Users\\ &lt; *使用者* &gt; \\Virtual 電腦目錄中的虛擬電腦名稱稱相符。 MED-V 工作區名稱位於 HKLM\\SOFTWARE\\Microsoft\\Medv\\v2\\VM\\Name。

例如，如果使用者是 "Matt"，而工作區名稱是 "mattsworkspace"，HKLM\\SOFTWARE\\Microsoft\\Medv\\v2\\VM\\Name 的值應該是 "mattsworkspace"，且應該有一個名為 C:\\Users\\Matt\\Virtual Machines\\mattsworkspace.vcmx. 的檔案。

### 應用程式發佈

### 事件 ID 10015

協調程式處理期間發生檔案系統錯誤。 [協調] 處理常式不會處理 &lt; *檔案名，* &gt; 但會繼續處理任何其他變更。

<a href="" id="description"></a>**描述**  
在建立或刪除快捷方式時，發生未授權的存取或 i/o 錯誤。

<a href="" id="solution"></a>**解決方案**  
檢查檔案路徑是否可存取，以及使用者是否擁有建立或刪除指定檔案的許可權。

### 事件 ID 10021

檔案 &lt; 的錯誤*\ _information*檔案作業 &gt; &lt; *操作 \ _name*檔案 &gt; &lt; *檔案名*上 &gt; 。

<a href="" id="description"></a>**描述**  
在建立或刪除快捷方式時，發生未授權的存取或 i/o 錯誤。

<a href="" id="solution"></a>**解決方案**  
檢查檔案路徑是否可存取，以及使用者是否擁有建立或刪除指定檔案的許可權。

### 來賓修補

### 事件 ID 11001

來賓喚醒任務使用方式訊息。

<a href="" id="description"></a>**描述**  
使用/GuestWakeup 選項的 MedvHost.exe 無法正確執行，或命令格式不正確。

<a href="" id="solution"></a>**解決方案**  
確定命令是以下列格式執行：

Medvhost.exe/GuestWakeup/d： &lt; *duration \ _in \ _minutes* &gt; /v：「 &lt; *工作區 \ _name*」 &gt; 位置

&lt;*duration \ _in \ _minutes* &gt;虛擬機器應保持在喚醒狀態的分鐘數（預設值為240）和

&lt;*工作區 \ _name* &gt;是應喚醒的虛擬機器名稱。

### 事件 ID 11002

無法更新 MED-V-未偵測到主機網路。

<a href="" id="description"></a>**描述**  
無法完成來賓修補，因為沒有探測到主機網路連線。

<a href="" id="solution"></a>**解決方案**  
在執行來賓修補程式之前，請先將 MED-V 主機連線至使用中的網路連線。

### 事件 ID 11003

無法更新 MED-V-未在 A/C powerFailed 上執行的主機，無法建立管道伺服器。

<a href="" id="description"></a>**描述**  
無法完成來賓修補，因為主機看起來好像是在電池電源執行，而不是從電源線執行。

<a href="" id="solution"></a>**解決方案**  
在執行來賓修補之前，請先將主機電腦連接至電源線。

### 用戶端 UX

### 事件 ID 14003

下列送紙器狀態訊息太長且無法顯示： &lt; *紙盒 \ _status \ _message*&gt;

<a href="" id="description"></a>**描述**  
MED-V 針對工作列工具提示或氣球訊息所建立的意外字串太長。 因此，顯示的郵件已被截斷。

<a href="" id="solution"></a>**解決方案**  
在 MED-V 隨機建立工具提示文字時，可能會發生這種不常見的錯誤。 沒有解決方法。

### 事件 ID 14004

由於未處理的例外狀況，MED-V 已停止。

<a href="" id="description"></a>**描述**  
未處理的例外導致 MED-V 停止意外停止。

<a href="" id="solution"></a>**解決方案**  
重新開機 MED-V。

### 事件 ID 14005

伺服器試圖建立 mutex，但已經存在。

<a href="" id="description"></a>**描述**  
MedvHost.exe 的第二個實例停滯在記憶體中。

<a href="" id="solution"></a>**解決方案**  
開啟 TaskManager 並結束所有 MedvHost.exe 處理常式。

### 事件 ID 14006

修改或刪除註冊表值 registry 時發生錯誤 &lt; *\ _value* &gt; 。

<a href="" id="description"></a>**描述**  
MED-V 無法在註冊表中修改指定的專案。

<a href="" id="solution"></a>**解決方案**  
確定您是使用系統管理認證來安裝或卸載 MED-V。

### 事件 ID 14007

指定的檔案（ &lt; *filename* &gt; ）無效。

<a href="" id="description"></a>**描述**  
在安裝或卸載期間，已將損毀的臨時檔案傳遞到 MED-V 主機。

<a href="" id="solution"></a>**解決方案**  
刪除 Temp 資料夾中的所有檔案，然後重新安裝或卸載 MED-V。

### 事件 ID 14008

找不到檔案： &lt; *檔案名* &gt; 。

<a href="" id="description"></a>**描述**  
在安裝或卸載期間，找不到所需 temp 檔案的路徑。

<a href="" id="solution"></a>**解決方案**  
刪除 Temp 資料夾中的所有檔案，然後重新安裝或卸載 MED-V。

### 事件 ID 14009

無法讀取參數檔 &lt; *檔案名* &gt; 。

<a href="" id="description"></a>**描述**  
在安裝或卸載程式期間，MED-V 無法讀取 temp 檔案。

<a href="" id="solution"></a>**解決方案**  
刪除 Temp 資料夾中的所有檔案，然後重新安裝或卸載 MED-V。 此外，請確認使用者擁有 Temp 資料夾的必要權利和許可權。

### 事件 ID 14010

反序列化參數 &lt; *檔案名* &gt; 的錯誤。

<a href="" id="description"></a>**描述**  
在安裝或卸載程式期間，MED-V 遇到損毀檔案。

<a href="" id="solution"></a>**解決方案**  
刪除 Temp 資料夾中的所有檔案，然後重新安裝或卸載 MED-V。 此外，請確認使用者擁有 Temp 資料夾的必要權利和許可權。

### 事件 ID 14011

反序列化參數檔案名時產生意外 &lt; *filename* &gt; 的錯誤。

<a href="" id="description"></a>**描述**  
在安裝或卸載程式期間，MED-V 遇到損毀檔案。

<a href="" id="solution"></a>**解決方案**  
刪除 Temp 資料夾中的所有檔案，然後重新安裝或卸載 MED-V。 此外，請確認使用者擁有 Temp 資料夾的必要權利和許可權。

### 事件 ID 14012

[資料夾 &lt; *資料夾 \* ] 的設定權力為 [_name &gt; 使用者使用者 &lt; *名稱*] 時，發生意外 &gt; 的錯誤。

<a href="" id="description"></a>**描述**  
當 MED-V 無法在安裝期間設定特定資料夾的許可權和許可權時，就會發生錯誤。

<a href="" id="solution"></a>**解決方案**  
檢查下列資料夾的系統管理員許可權：

@"%ProgramData%\\Microsoft\\Medv\\AllUsers"

@"%ProgramData%\\Microsoft\\Medv\\MedvLock"

@"%ProgramData%\\Microsoft\\Medv\\Monitoring"

### 事件 ID 14013

建立鎖定檔案時發生意外的錯誤。

<a href="" id="description"></a>**描述**  
當 MED-V 無法在安裝期間在 @ "%ProgramData%\\Microsoft\\Medv\\MedvLock" 資料夾中建立檔案時，就會發生錯誤。

<a href="" id="solution"></a>**解決方案**  
檢查 [MedvLock] 資料夾的系統管理員許可權。

## 相關主題


[疑難排解 MED-V](troubleshooting-med-vmedv2.md)

 

 





