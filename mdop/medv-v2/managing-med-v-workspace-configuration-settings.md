---
title: 管理 MED-V 工作區組態設定
description: 管理 MED-V 工作區組態設定
author: dansimp
ms.assetid: 517d04de-c31f-4b50-b2b3-5f8c312ed37b
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 97add695f605b71547b564789cce07a1d58763f2
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811588"
---
# 管理 MED-V 工作區組態設定


Microsoft 企業版桌面虛擬化（MED-V）2.0 儲存其在註冊表中的設定。 我們在這裡提供的有關登錄的資訊可協助您更好地管理 MED-V 服務。

在尋找結果設定值時，MED-V 會使用下列搜尋路徑：

MED-V 會先在電腦原則中尋找。

如果找不到這個值，MED-V 就會在使用者原則中尋找。

如果找不到這個值，MED-V 會在 HKEY \ _LOCAL \ _MACHINE \\System hive）中尋找。

如果找不到這個值，MED-V 會在 HKEY \ _CURRENT 使用者登錄配置儲存格中尋找。

如果仍找不到該值，MED-V 會使用預設值。

一般的最佳做法是在 HKEY \ _LOCAL \ _MACHINE \\System hive 或電腦原則中設定值。 但如果您想讓使用者能夠設定特定設定，您應該將它保留下來。

**注意**  
在您部署 MED-V 工作區之前，您可以使用 [腳本編輯器] 來變更 MED-V 工作區包裝程式所建立的 Windows PowerShell 腳本（ps1 檔案）。 如需詳細資訊，請參閱[使用 Windows PowerShell 配置高級設定](configuring-advanced-settings-by-using-windows-powershell.md)。

部署 MED-V 工作區之後，您可以透過編輯登錄專案來變更某些 MED-V 設定設定。



本節列出所有可設定的 MED-V 登錄機碼，並說明其用法。

## 診斷金鑰


下表提供與 HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\Medv\\v2\\Diagnostics 金鑰有關之註冊表值的相關資訊。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名稱 </th>
<th align="left">類型 </th>
<th align="left">資料/預設值 </th>
<th align="left">描述 </th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>EventLogLevel </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>預設值 = 3</p></td>
<td align="left"><p>記錄在事件記錄檔中的資訊類型。 階層包括下列專案：0（無）、1（錯誤）、2（警告）、3（資訊）、4（調試）。</p></td>
</tr>
</tbody>
</table>



## Fts 鍵


下表提供與 HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\Medv\\v2\\Fts 金鑰有關之註冊表值的相關資訊。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名稱</th>
<th align="left">類型</th>
<th align="left">資料/預設值</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>AddUserToAdminGroupEnabled </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設 = 0</p></td>
<td align="left"><p>設定第一次設定是否會自動將使用者新增到管理員&#39;s 群組。 0 = false;1 = true。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false：第一次設定不會自動將最終使用者新增到管理員&#39;s 群組。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true：第一次設定會自動將最終使用者新增到管理員&#39;s 群組。</p></td>
</tr>
<tr class="even">
<td align="left"><p>ComputerNameMask </p></td>
<td align="left"><p>SZ</p></td>
<td align="left"><p>MEDV* </p></td>
<td align="left"><p>用來建立來賓虛擬機器&#39;s 電腦名稱稱的電腦名稱稱遮罩。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>遮罩可以包含% username% 標籤，以插入使用者名稱作為電腦名稱稱的一部分。 同樣地，% hostname% 標籤會插入主機電腦的名稱。</p>
<p>&quot; # &quot; 遮罩中的每個字元都會以亂數字取代。 遮罩末端的星號（*）字元會以隨機的字母數位字元取代。</p>
<p>您可以使用方括弧來捕獲% hostname% 與% username% 的特定字元數。 例如， &quot; % username% [3] &quot; 會使用使用者名稱的前三個字元。</p></td>
</tr>
<tr class="even">
<td align="left"><p>DeleteVMStateTimeout</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設值 = 90</p></td>
<td align="left"><p>第一次安裝程式嘗試刪除虛擬機器時的超時值（以秒為單位）。 範圍 = 0 至2147483647。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>DetachVfdTimeout</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設 = 120</p></td>
<td align="left"><p>第一次安裝程式嘗試從虛擬機器分離虛擬磁碟磁片時的超時值（以秒為單位）。 範圍 = 0 至2147483647。</p></td>
</tr>
<tr class="even">
<td align="left"><p>DialogUrl </p></td>
<td align="left"><p>SZ</p></td>
<td align="left"><p></p></td>
<td align="left"><p>連結至內部網頁的可自訂 URL，且會在第一次顯示設定對話方塊訊息時顯示。 </p></td>
</tr>
<tr class="odd">
<td align="left"><p>ExplorerTimeout</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設 = 900</p></td>
<td align="left"><p>第一次安裝程式等待 Windows Explorer 的超時值（以秒為單位）。 範圍 = 0 至2147483647。</p></td>
</tr>
<tr class="even">
<td align="left"><p>FailureDialogMsg </p></td>
<td align="left"><p>MULTI_SZ</p></td>
<td align="left"><p>在資源檔中找到郵件 </p></td>
<td align="left"><p>可自訂的訊息，在第一次設定無法完成時顯示給最終使用者。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>GiveUserGroupRightsMaxRetryCount </p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>預設值 = 3</p></td>
<td align="left"><p>MED-V 嘗試給予使用者群組權利的最大次數。 超過指定的 retry 值，且不能成功給予使用者群組許可權，可能會導致虛擬電腦的準備失敗，並服從 MaxRetryCount 值。 範圍 = 0 至2147483647。</p></td>
</tr>
<tr class="even">
<td align="left"><p>GiveUserGroupRightsTimeout </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設值 = 300</p></td>
<td align="left"><p>提供使用者群組權力的超時值（以秒為單位）。 範圍 = 0 至2147483647。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>LogFilePaths </p></td>
<td align="left"><p>MULTI_SZ</p></td>
<td align="left"><p></p></td>
<td align="left"><p>在第一次設定期間，由 MED-V 收集的記錄檔路徑清單。 </p></td>
</tr>
<tr class="even">
<td align="left"><p>MaxPostponeTime </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設 = 120</p></td>
<td align="left"><p>一次最多可由最終使用者推遲設定的最大小時數。 範圍 = 0 至2147483647。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MaxRetryCount </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設值 = 3</p></td>
<td align="left"><p>如果每次嘗試都在軟體錯誤以外的失敗時間結束，則 MED-V 會嘗試準備虛擬機器的最大次數。 當虛擬機器準備失敗且超過設定的第一次重試次數時，MED-V 會通知最終使用者發生失敗，且不會提供重試選項。 每次啟動 MED-V 時，都會重新設定計數。 範圍 = 0 至2147483647。</p></td>
</tr>
<tr class="even">
<td align="left"><p>模式 </p></td>
<td align="left"><p>SZ</p></td>
<td align="left"><p>預設 = 無人參與</p></td>
<td align="left"><p>配置第一次設定與使用者互動的方式。 可能的值如下所示：</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong>上月.</strong> 最終使用者必須在第一次設定期間輸入資訊。</p>
<div class="alert">
<strong>注意</strong><br/><p>如果您建立了 Sysprep.inf 檔案，讓迷你安裝程式需要使用者輸入才能完成，則您必須選取 [ <strong> 有人值守 </strong> ] 模式，否則可能會在第一次設定期間發生問題。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong>無人參與 </strong> 。 在第一次設定期間，虛擬機器不會顯示給最終使用者，但在第一次啟動安裝程式之前，系統會提示使用者。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong>[無提示] </strong> 。 在第一次設定期間，不會向最終使用者顯示虛擬機器。</p></td>
</tr>
<tr class="even">
<td align="left"><p>NonInteractiveRetryTimeoutInc </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設 = 15</p></td>
<td align="left"><p>當重新嘗試安裝程式時，第一次必須在第一次設定互動式模式時完成設定的超時值（以分鐘為單位）。 範圍 = 0 至2147483647。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>NonInteractiveTimeout </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設值 = 45</p></td>
<td align="left"><p>第一次設定在第一次設定互動式模式時必須完成的超時值（以分鐘為單位）。 範圍 = 0 至2147483647。</p></td>
</tr>
<tr class="even">
<td align="left"><p>PostponeUtcDateTimeLimit </p></td>
<td align="left"><p>SZ</p></td>
<td align="left"><p></p></td>
<td align="left"><p>第一次設定可延後的日期及時間（以 UTC 日期時間格式表示）。 &quot; &quot; 使用24小時制標準，以 [YYYY-mm-dd hh： MM] 的格式輸入。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>RetryDialogMsg </p></td>
<td align="left"><p>MULTI_SZ</p></td>
<td align="left"><p>在資源檔中找到郵件 </p></td>
<td align="left"><p>可自訂的訊息，在第一次安裝程式必須重新嘗試設定時，會顯示給最終使用者。</p></td>
</tr>
<tr class="even">
<td align="left"><p>SetComputerNameEnabled </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設 = 0</p></td>
<td align="left"><p>設定來賓中 Sysprep.inf 檔案的 [UserData] 區段下的 ComputerName 專案是否應該根據指定的 ComputerNameMask 進行更新。   0 = false;1 = true。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false： Sysprep.inf 檔案中的 ComputerName 專案不會根據 ComputerNameMask 進行更新。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true： Sysprep.inf 檔案中的 ComputerName 專案會根據 ComputerNameMask 進行更新。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>SetJoinDomainEnabled </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設 = 0</p></td>
<td align="left"><p>設定來賓中 Sysprep.inf 檔案的 [身分識別] 區段下的 [JoinDomain] 設定是否應該更新，以符合主機上的設定。  0 = false;1 = true。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false： Sysprep.inf 檔案中的 JoinDomain 設定不會更新，以符合主機上的設定。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true： Sysprep.inf 檔案中的 JoinDomain 設定會更新，以符合主機上的設定。</p></td>
</tr>
<tr class="even">
<td align="left"><p>SetMachineObjectOUEnabled </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設 = 0</p></td>
<td align="left"><p>設定來賓中 Sysprep.inf 檔案的 [身分識別] 區段下的 [MachineObjectOU] 設定是否已更新，以符合主機。  0 = false;1 = true。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false： Sysprep.inf 檔案中的 MachineObjectOU 設定不會更新，以符合主機上的設定。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true： Sysprep.inf 檔案中的 MachineObjectOU 設定會更新，以符合主機上的設定。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>SetRegionalSettingsEnabled </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設 = 0</p></td>
<td align="left"><p>設定來賓中 Sysprep.inf 檔案的 [RegionalSettings] 區段下的設定是否已更新，以符合主機的需要。  0 = false;1 = true。</p>
<div class="alert">
<strong>注意</strong><br/><p>根據預設，來賓中的時區設定總是與主機中的時區設定同步處理。</p>
</div>
<div>

</div></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false：來賓中 Sysprep.inf 檔案之 [RegionalSettings] 區段下的設定不會更新以符合主機。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true：來賓中 Sysprep.inf 檔案之 [RegionalSettings] 區段下的設定會更新，以符合主機的需要。</p></td>
</tr>
<tr class="even">
<td align="left"><p>SetUserDataEnabled </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設 = 0</p></td>
<td align="left"><p>設定來賓中 Sysprep.inf 檔案的 [UserData] 區段下的 [FullName] 和 [OrgName] 設定是否已更新，以符合主機上的設定。  0 = false;1 = true。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false： Sysprep.inf 檔案中的 [FullName] 和 [OrgName] 設定不會更新，以符合主機上的設定。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true： Sysprep.inf 檔案中的 [FullName] 和 [OrgName] 設定會更新，以符合主機上的設定。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>StartDialogMsg </p></td>
<td align="left"><p>MULTI_SZ</p></td>
<td align="left"><p>在資源檔中找到郵件 </p></td>
<td align="left"><p>可自訂的訊息，在第一次設定準備開始時顯示給最終使用者。 </p></td>
</tr>
<tr class="even">
<td align="left"><p>TaskCancelTimeout</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設 = 30</p></td>
<td align="left"><p>"超時值] （以秒為單位），在第一次安裝程式等待來自虛擬機器的回應以進行取消操作時。 範圍 = 0 至2147483647。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>TaskVMTurnOffTimeout</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設值 = 60</p></td>
<td align="left"><p>第一次安裝程式等到虛擬機器關閉時，的超時值（以秒為單位）。 範圍 = 0 至2147483647。</p></td>
</tr>
<tr class="even">
<td align="left"><p>UpgradeTimeout</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設 = 600</p></td>
<td align="left"><p>嘗試升級 MED-V 來賓代理軟體超時前的時間（以秒為單位）。範圍 = 0 至2147483647。</p></td>
</tr>
</tbody>
</table>



## UserExperience 鍵


下表提供與 HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\Medv\\v2\\UserExperience 金鑰和 HKEY \ _CURRENT \ _USER \\Software\\Microsoft\\Medv\\v2\\UserExperience 金鑰相關聯之註冊表值的相關資訊。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名稱</th>
<th align="left">類型</th>
<th align="left">資料/預設值</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>AppPublishingEnabled </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設 = 1</p></td>
<td align="left"><p>配置是否已啟用從來賓到主機的應用程式發佈。  0 = false;1 = true。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false：停用來賓向主機發佈的應用程式。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true：啟用從來賓到主機的應用程式發佈。</p></td>
</tr>
<tr class="even">
<td align="left"><p>AudioSharingEnabled </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設 = 1</p></td>
<td align="left"><p>設定是否已啟用在來賓與主機之間共用音訊 i/o 裝置的功能。  0 = false;1 = true。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false：停用來賓與主機之間的音訊 i/o 裝置共用。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true：啟用在來賓與主機之間共用音訊 i/o 裝置。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>ClipboardSharingEnabled </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設 = 1</p></td>
<td align="left"><p>設定是否啟用 [在來賓與主機之間共用剪貼簿]。  0 = false;1 = true。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false：停用來賓與主機之間的剪貼簿共用。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true：啟用來賓與主機之間的剪貼簿共用。</p></td>
</tr>
<tr class="even">
<td align="left"><p>DialogTimeout</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設值 = 300</p></td>
<td align="left"><p>第一次設定開始對話方塊超時之前的時間（以秒為單位）。範圍 = 0 至2147483647。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>HideVmTimeout</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設 = 30</p></td>
<td align="left"><p>超時值（以分鐘為單位），在長時間登錄嘗試中，全螢幕虛擬機器視窗會隱藏在最終使用者中。</p></td>
</tr>
<tr class="even">
<td align="left"><p>LogonStartEnabled </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設 = 1</p></td>
<td align="left"><p>設定使用者登入桌面或第一次來賓應用程式啟動時，是否應啟動來賓。  0 = false;1 = true。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false：啟動第一個來賓應用程式時，會啟動來賓。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true：當使用者登入桌面時，就會啟動來賓。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>PrinterSharingEnabled </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設 = 1</p></td>
<td align="left"><p>設定來賓與主機之間的印表機共用是否已啟用。  0 = false;1 = true。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false：停用來賓與主機之間的印表機共用。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true：啟用來賓與主機之間的印表機共用功能。</p></td>
</tr>
<tr class="even">
<td align="left"><p>RebootAbsoluteDelayTimeout </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設 = 1440</p></td>
<td align="left"><p>第一次安裝程式等待重新開機的超時值（以分鐘為單位）。 範圍 = 0 至2147483647。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>RedirectUrls </p></td>
<td align="left"><p>MULTI_SZ</p></td>
<td align="left"><p>指定的 URL 清單</p></td>
<td align="left"><p>指定要從主機重新導向至來賓的 Url 清單。 </p></td>
</tr>
<tr class="even">
<td align="left"><p>SmartCardLogonEnabled</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設 = 0</p></td>
<td align="left"><p>設定智慧卡是否可以用來向 MED-V 驗證使用者。 0 = false;1 = true。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false：不讓智慧卡驗證最終使用者至 MED-V。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true：讓智慧卡向 MED-V 驗證最終使用者。</p>
<div class="alert">
<strong>重要</strong><br/><p>如果 SmartCardLogonEnabled 和 CredentialCacheEnabled 都已啟用，SmartCardLogonEnabled 會覆寫 CredentialCacheEnabled。</p>
</div>
<div>

</div></td>
</tr>
<tr class="odd">
<td align="left"><p>SmartCardSharingEnabled </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設 = 1</p></td>
<td align="left"><p>設定來賓與主機之間的智慧卡共用是否已啟用。  0 = false;1 = true。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false：停用來賓與主機之間的智慧卡共用。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true：啟用來賓與主機之間的智慧卡共用。</p></td>
</tr>
<tr class="even">
<td align="left"><p>USBDeviceSharingEnabled </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設 = 1</p></td>
<td align="left"><p>設定來賓與主機之間的 USB 裝置共用是否已啟用。  0 = false;1 = true。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false：停用來賓與主機之間的 USB 裝置共用。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true：啟用來賓與主機之間的 USB 裝置共用功能。</p></td>
</tr>
</tbody>
</table>



## VM 金鑰


下表提供與 HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\Medv\\v2\\VM 金鑰和 HKEY \ _CURRENT \ _USER \\Software\\Microsoft\\Medv\\v2\\VM 金鑰相關聯之註冊表值的相關資訊。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名稱</th>
<th align="left">類型</th>
<th align="left">資料/預設值</th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>CloseAction </p></td>
<td align="left"><p>SZ</p></td>
<td align="left"><p>預設 = 休眠</p></td>
<td align="left"><p>虛擬機器在執行的最後一個應用程式關閉之後所執行的動作。 如果啟用 LogonStartEnabled 值，則會忽略此設定。 可能的選項如下所示：</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong>[休眠] </strong> 。 這個選項會釋放虛擬機器所使用的所有物理資源，例如記憶體和 CPU，並儲存所有執行的應用程式和作業的狀態。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong>關閉 </strong> 。 這個選項會安全地關閉客體作業系統，然後釋放虛擬機器所使用的所有物理資源，例如記憶體和 CPU。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong>關閉 </strong> 。 這個選項可能會造成資料遺失，因為它與關閉電源按鈕或在物理電腦上拉出電源線一樣。 只有在您無法使用其他兩個選項時，才能使用這個選項。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>GuestMemFromHostMem </p></td>
<td align="left"><p>MULTI_SZ</p></td>
<td align="left"><p>378、512、1024、1536、2048 </p></td>
<td align="left"><p>來賓的記憶體（MB）值清單。 這個值是用來判斷來賓可以使用多少 RAM。 結合 HostMemToGuestMem，就會建立查閱表格，判斷要在來賓虛擬機器上配置多少 RAM。 可能的值可能是從128到3712。</p></td>
</tr>
<tr class="even">
<td align="left"><p>GuestUpdateDuration </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設 = 240</p></td>
<td align="left"><p>MED-V 應該讓來賓保持訪客喚醒以進行自動更新，從在 GuestUpdateTime 值中指定的時間開始。 範圍 = 0 至1440。 將此值設定為零（0）會停用來賓修補功能。</p>
<p>如需有關來賓修補程式以進行自動更新的詳細資訊，請參閱 <a href="managing-automatic-updates-for-med-v-workspaces.md" data-raw-source="[Managing Automatic Updates for MED-V Workspaces](managing-automatic-updates-for-med-v-workspaces.md)"> 管理 Med-v 工作區的自動更新 </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>GuestUpdateTime </p></td>
<td align="left"><p>SZ</p></td>
<td align="left"><p>預設值 = 00：00</p></td>
<td align="left"><p>MED-V 應該使用24小時制的標準，將訪客喚醒以進行自動更新。 以 HH： MM 格式指定時間  </p>
<p>如需有關來賓修補程式以進行自動更新的詳細資訊，請參閱 <a href="managing-automatic-updates-for-med-v-workspaces.md" data-raw-source="[Managing Automatic Updates for MED-V Workspaces](managing-automatic-updates-for-med-v-workspaces.md)"> 管理 Med-v 工作區的自動更新 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>HostMemToGuestMem </p></td>
<td align="left"><p>MULTI_SZ</p></td>
<td align="left"><p>1024、2048、4096、8192、16384 </p></td>
<td align="left"><p>來賓的記憶體（MB）值清單，由主機上可用的 RAM 決定。 結合 GuestMemFromHostMem，就會建立查閱表格，判斷要在來賓虛擬機器上配置多少 RAM。 可能的值可能是從1024到16384。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>HostMemToGuestMemCalcEnabled</p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設 = 1</p></td>
<td align="left"><p>設定為來賓指派的記憶體是否是從主機上的記憶體計算而來。  0 = false;1 = true。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false：為來賓指派的記憶體不會從主機上的記憶體計算。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true：為來賓指派的記憶體是從主機上的記憶體計算而來。</p></td>
</tr>
<tr class="even">
<td align="left"><p>記憶體 </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設值 = 512</p></td>
<td align="left"><p>應該為來賓虛擬機器指派的 RAM （MB）。 如果啟用 HostMemToGuestMemEnabled 設定，則會忽略此設定。 範圍 = 128 至2048。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>MultiUserEnabled </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設 = 0</p></td>
<td align="left"><p>設定多個使用者是否共用同一個 MED-V 工作區。  0 = false;1 = true。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>0 = false：多個使用者不共用同一個 MED-V 工作區。</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>1 = true：多個使用者共用同一個 MED-V 工作區。</p></td>
</tr>
<tr class="even">
<td align="left"><p>NetworkingMode </p></td>
<td align="left"><p>SZ</p></td>
<td align="left"><p>預設 = NAT</p></td>
<td align="left"><p>來賓上所用的網路連線類型。 可能的值如下所示：</p></td>
</tr>
<tr class="odd">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong>已橋接 </strong> 。 MED-V 有自己的網路位址，通常是透過 DHCP 取得的。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p><strong>NAT </strong> 。 MED-V 使用網路位址轉譯（NAT）來共用主機&#39;s IP 以進行外寄通訊。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>TaskTimeout </p></td>
<td align="left"><p>DWORD</p></td>
<td align="left"><p>預設 = 600</p></td>
<td align="left"><p>一般超時值（以秒為單位），即由 MED-V 等待完成工作，例如重新開機及關閉。 範圍 = 0 至2147483647。</p></td>
</tr>
</tbody>
</table>



## 來賓註冊設定


本節列出可設定的 MED-V 來賓登錄機碼，並說明其用法。

### v2

下表提供與 HKEY \ _LOCAL \ _MACHINE \\SOFTWARE\\Microsoft\\Medv\\v2\\ 金鑰相關聯之來賓登錄值的相關資訊。

<table>
<colgroup>
<col width="25%" />
<col width="25%" />
<col width="25%" />
<col width="25%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">名稱 </th>
<th align="left">類型 </th>
<th align="left">資料/預設值 </th>
<th align="left">描述</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>EnableGPWorkarounds</p></td>
<td align="left"><p>DWORD </p></td>
<td align="left"><p>預設 = 1 </p></td>
<td align="left"><p>配置 MED-V 處理金鑰 BufferPolicyReads 和 GroupPolicyMinTransferRate 的方式。</p></td>
</tr>
<tr class="even">
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p></p></td>
<td align="left"><p>根據預設，MED-V 會依以下方式設定這些金鑰：</p>
<p>BufferPolicyReads = 1 和 GroupPolicyMinTransferRate = 0。</p>
<p>如果您不想要 MED-V 變更 BufferPolicyReads 和 GroupPolicyMinTransferRate 的預設設定，請視需要建立 EnableGPWorkarounds 金鑰（如果有必要的話），並將該金鑰設定為零。</p>
<div class="alert">
<strong>注意</strong><br/><p>如果您的 MED-V 工作區是在 NAT 模式下執行，EnableGPWorkarounds 會影響登錄機碼 BufferPolicyReads 和 GroupPolicyMinTransferRate。 如果您的 MED-V 工作區是以橋接模式執行，EnableGPWorkarounds 只會影響登錄機碼 BufferPolicyReads。</p>
</div>
<div>

</div>
<p>1 = true： MED-V 會將鍵設定為 BufferPolicyReads = 1 和 GroupPolicyMinTransferRate = 0 （如果在 NAT 模式下執行），或僅 BufferPolicyReads = 1 （如果以橋接模式執行）。</p>
<p>0 = false： MED-V 不會對金鑰 BufferPolicyReads 和 GroupPolicyMinTransferRate 進行任何變更。</p></td>
</tr>
</tbody>
</table>



## 相關主題


[管理 MED-V 工作區應用程式](manage-med-v-workspace-applications.md)

[管理 MED-V URL 重新導向](manage-med-v-url-redirection.md)

[管理 MED-V 工作區設定](manage-med-v-workspace-settings.md)









