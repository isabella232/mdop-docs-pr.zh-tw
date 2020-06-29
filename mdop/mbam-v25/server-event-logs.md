---
title: 伺服器事件記錄檔
description: 伺服器事件記錄檔
author: dansimp
ms.assetid: 04e724d2-28cc-4fa8-86a1-0d4ab0234b11
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, security
ms.mktglfcycl: manage
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 269e9b4bc2644fae4dc5796652c7587bb0ef6076
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10809921"
---
# 伺服器事件記錄檔


本節中的資料表提供有關 MBAM Server 記錄事件識別碼的資訊。

## 設定


下表包含在設定期間，在 MBAM 伺服器上可能發生之事件識別碼的訊息與疑難排解資訊。

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">事件識別碼</th>
<th align="left">Source</th>
<th align="left">事件符號</th>
<th align="left">訊息</th>
<th align="left">疑難排解</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>103</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-伺服器/運營</p></td>
<td align="left"><p>VssRegistrationException</p></td>
<td align="left"><p>在 VSS 註冊期間拋出例外狀況。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>104</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-伺服器/運營</p></td>
<td align="left"><p>VssDeregistrationException</p></td>
<td align="left"><p>在 VSS 取消登出期間拋出例外狀況。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>300</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-伺服器/Admin</p></td>
<td align="left"><p>CmdletError</p></td>
<td align="left"><p>移除資料夾失敗。</p></td>
<td align="left"><p>表示執行工作時，發生終止錯誤。 檢查記錄中的其他事件訊息，進一步診斷 MBAM 設定。</p></td>
</tr>
<tr class="even">
<td align="left"><p>301</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-伺服器/Admin</p></td>
<td align="left"><p>CmdletUnexpectedError</p></td>
<td align="left"><p>意外的 Cmdlet 錯誤。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>302</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-伺服器/Admin</p></td>
<td align="left"><p>CmdletWarning</p></td>
<td align="left"><p>Cmdlet 警告。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>303</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-伺服器/運營</p></td>
<td align="left"><p>CmdletInformation</p></td>
<td align="left"><p>Cmdlet 資訊。</p></td>
<td align="left"><p>僅提供資訊;不需要進行疑難排解。 事件指出由 Cmdlet （例如 enabling\disabling 功能或取消作業）所進行的工作。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>400</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-伺服器/Admin</p></td>
<td align="left"><p>ConfiguratorError</p></td>
<td align="left"><p>配置器錯誤。</p></td>
<td align="left"><p>表示啟動 MBAM 配置器時發生錯誤。 確認使用者擁有足夠的許可權來啟動 MBAM 配置器。</p></td>
</tr>
<tr class="even">
<td align="left"><p>401</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-伺服器/Admin</p></td>
<td align="left"><p>ConfiguratorUnexpectedError</p></td>
<td align="left"><p>意外的配置器錯誤。</p></td>
<td align="left"><p>指示在執行 MBAM 配置程式任務時，發生了終止錯誤。 錯誤訊息將包含更多關於錯誤的詳細資料。 檢查事件記錄檔中的其他錯誤訊息，進一步診斷 MBAM 設定。 已知錯誤包括：</p>
<ul>
<li><p>無法檢索或驗證使用者所選取的憑證</p></li>
<li><p>分析報表 URL 失敗</p></li>
<li><p>無法開啟使用者的事件記錄</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>402</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-伺服器/Admin</p></td>
<td align="left"><p>ConfiguratorWarning</p></td>
<td align="left"><p>配置器警告。</p></td>
<td align="left"><p>表示 MBAM 配置器工作未如預期完成，但未完全失敗。 已知工作包括在 [web 應用程式] 功能中設定的 LocalMachine\My 存放區中缺少憑證，或擱置中的任務超時。</p></td>
</tr>
<tr class="even">
<td align="left"><p>410</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-伺服器/運營</p></td>
<td align="left"><p>ConfiguratorInformation</p></td>
<td align="left"><p>配置器資訊。</p></td>
<td align="left"><p>僅提供資訊;不需要進行疑難排解。 事件指出任務正由 MBAM 配置程式呼叫。 已知任務包括：</p>
<ul>
<li><p>啟動配置器</p></li>
<li><p>檢查 MBAM 功能的軟體先決條件</p></li>
<li><p>驗證 MBAM 功能的參數</p></li>
<li><p>Enabling\disabling\committing MBAM 功能</p></li>
<li><p>從配置器產生 PowerShell 腳本</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>500</p></td>
<td align="left"><p>Microsoft_Windows_MBAM_Server_Admin</p></td>
<td align="left"><p>WebProviderUnexpectedError</p></td>
<td align="left"><p>Web 應用程式提供者意外錯誤。</p></td>
<td align="left"><p>指示在 IIS 中啟用及設定 MBAM 網站或 web 服務時發生錯誤。 已知錯誤包括：</p>
<ul>
<li><p>找不到 IIS WWW 根資料夾</p></li>
<li><p>無法在 web.config 由於格式錯誤的檔案或遺失的設定而存取 IIS 配置</p></li>
<li><p>無法建立或移除 web 應用程式</p></li>
<li><p>IIS 存取侵犯</p></li>
</ul>
<p>如果 MBAM 無法存取 Active Directory （AD）來驗證使用者帳戶，也會記錄這個錯誤。 確認已安裝並正確設定 IIS，且 IIS 服務正在執行。 確認所有 MBAM 軟體先決條件檢查都經過。 確認使用者擁有正確的許可權，才能在 IIS 實例上建立 web 應用程式。 確認使用者有權閱讀 AD 中的使用者帳戶物件。</p></td>
</tr>
<tr class="even">
<td align="left"><p>501</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-伺服器/Admin</p></td>
<td align="left"><p>WebProviderError</p></td>
<td align="left"><p>Web 應用程式提供者意外錯誤。</p></td>
<td align="left"><p>指示在 IIS 中啟用、停用或設定 MBAM 網站或 web 服務時發生錯誤。 已知錯誤包括：</p>
<ul>
<li><p>無法從 IIS 讀取基本或 WSHttp 系結資訊</p></li>
<li><p>在 IIS 配置檔案的 [身分識別] 區段中缺少身分識別區段或 DNS 專案</p></li>
<li><p>無法開啟登錄機碼 HKLM\SOFTWARE\Microsoft\InetStp</p></li>
<li><p>無法從登錄機碼讀取值 PathWWWRoot HKLM\SOFTWARE\Microsoft\InetStp</p></li>
<li><p>使用者正在嘗試使用保留名稱指定 MBAM 的虛擬目錄名稱</p></li>
</ul>
<p>確認已安裝並正確設定 IIS。 確認登錄機碼 HKLM\SOFTWARE\Microsoft\InetStp： PathWWWRoot 存在且易於存取。 確認 IIS 中的系結資訊未損壞。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>502</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-伺服器/Admin</p></td>
<td align="left"><p>WebProviderWarning</p></td>
<td align="left"><p>Web 應用程式提供者警告。</p></td>
<td align="left"><p>表示啟用 MBAM 網站或 web 服務時發生非終止錯誤。 已知錯誤包括：</p>
<ul>
<li><p>無法存取廣告以驗證應用程式池帳戶上的服務主體名稱（SPN）</p></li>
<li><p>無法驗證 SPN，因為已將它指派給 AD 中的多個帳戶</p></li>
<li><p>無法在 AD 中的應用程式池帳戶上註冊 SPN</p></li>
<li><p>在 AD 中的應用程式池以外的帳戶上註冊 SPN</p></li>
<li><p>在回滾作業期間，無法從 AD 中的 [應用程式池帳戶] 移除 SPN</p></li>
<li><p>無法檢查是否已在 IIS 伺服器上以批次許可權登入 IIS_IUSRS 群組</p></li>
</ul>
<p>事件訊息將包含有關特定錯誤的詳細資訊。 確認該 AD 可從執行 MBAM 安裝程式的伺服器進行訪問。 確認執行 MBAM 安裝程式的使用者具有 AD 中應用程式池帳戶的讀取權限。 如果 SPN 已在 AD 中的 [應用程式池] 帳戶上註冊，請確定該 SPN 未在其他帳戶上註冊。</p></td>
</tr>
<tr class="even">
<td align="left"><p>503</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-伺服器/運營</p></td>
<td align="left"><p>WebProviderInformation</p></td>
<td align="left"><p>Web 應用程式提供者資訊。 說明</p></td>
<td align="left"><p>僅提供資訊;不需要進行疑難排解。 事件指出任務正由 MBAM 設定所呼叫。 已知工作包括取得「綁定資訊」和「根網站」等 IIS 設定，以及設定服務主體名稱（SPN）。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>600</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-伺服器/Admin</p></td>
<td align="left"><p>SetupUnexpectedError</p></td>
<td align="left"><p>意外的設定錯誤。</p></td>
<td align="left"><p>表示 enabling\disabling 或設定 MBAM 功能時發生終止錯誤。 已知錯誤包括：</p>
<ul>
<li><p>無法在錯誤後回滾任務</p></li>
<li><p>無法從註冊表讀取</p></li>
<li><p>無法在檔案系統中建立或刪除資料夾</p></li>
<li><p>無法讀取 SQL 版本資訊</p></li>
<li><p>無法在 SQL 中註冊 VSS 寫入程式</p></li>
</ul>
<p>事件訊息將包含有關特定錯誤的詳細資訊。 確認所有的 MBAM 軟體先決條件檢查都經過了。 請確定 MBAM 登錄路徑（如果有的話） HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\MBAM 伺服器，且所有的子專案都是可讀的。 確認該 AD 可從執行 MBAM 安裝程式的伺服器進行訪問。 確認執行 MBAM 安裝程式的使用者在 AD 中有讀取權限。</p>
<p>若要成功進行 VSS 寫入程式註冊，請確認已安裝受支援的 SQL 版本，且執行 MBAM 設定的使用者可以存取該實例。 如果停用 MBAM 功能或卸載 MBAM，請確認所有檔案（例如記錄檔案和 web.config 檔案）都已關閉，所以 MBAM 可以移除其網站和 web 服務。</p></td>
</tr>
<tr class="even">
<td align="left"><p>601</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-伺服器/Admin</p></td>
<td align="left"><p>SetupError</p></td>
<td align="left"><p>安裝程式錯誤。</p></td>
<td align="left"><p>表示 enabling\disabling 或設定 MBAM 功能時發生終止錯誤。 已知錯誤包括：</p>
<ul>
<li><p>無法在 IIS 中讀取 MBAM 設定</p></li>
<li><p>IIS 配置中的 [損壞的 appSettings] 區段或設定錯誤的設定</p></li>
<li><p>無法驗證主機名稱</p></li>
<li><p>無法讀取 SQL 版本資訊</p></li>
<li><p>無法在 SQL 中註冊 VSS 寫入程式</p></li>
</ul>
<p>事件訊息將包含有關特定錯誤的詳細資訊。 確認已正確安裝及設定 IIS。 確認所有的 MBAM 軟體先決條件檢查都經過了。 若要成功進行 VSS 寫入程式註冊，請確認已安裝受支援的 SQL 版本，且執行 MBAM 設定的使用者可以存取該實例。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>602</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-伺服器/Admin</p></td>
<td align="left"><p>SetupWarning</p></td>
<td align="left"><p>[設定] 警告。</p></td>
<td align="left"><p>表示 enabling\disabling 或設定 MBAM 功能（例如 Configuration Manager （CM）整合或 MBAM web 應用程式時，發生非終止錯誤。 已知錯誤包括：無法從 CM 中的 SRS 角色點刪除 MBAM 報表，也無法從網網域控制站解析主機名稱。 事件訊息將包含有關特定錯誤的詳細資訊。</p>
<p>確認該 AD 可從執行 MBAM 安裝程式的伺服器進行訪問。 確認執行 MBAM 安裝程式的使用者具有在在 CM 中設定為 SRS 角色點的 SSRS 實例上的 [移除] 許可權。</p></td>
</tr>
<tr class="even">
<td align="left"><p>603</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-伺服器/運營</p></td>
<td align="left"><p>SetupInformation</p></td>
<td align="left"><p>設定資訊。</p></td>
<td align="left"><p>僅提供資訊;不需要進行疑難排解。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>605</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-伺服器/Admin</p></td>
<td align="left"><p>WebProviderSoftwareCheckFailure</p></td>
<td align="left"><p>無法啟用 Web 應用程式，因為無法符合一或多個軟體相依性。</p></td>
<td align="left"><p>在 MBAM web site/web 服務安裝期間，MBAM 安裝程式會驗證必要的先決條件是否已就緒。 此訊息表示 MBAM 無法安裝要求的網站/web 服務，因為缺少必要的先決條件。 請參閱此訊息前面的錯誤訊息，以取得關於缺少的先決條件的詳細資訊。</p></td>
</tr>
<tr class="even">
<td align="left"><p>606</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-伺服器/Admin</p></td>
<td align="left"><p>SetupParameterValidationFailure</p></td>
<td align="left"><p>啟用伺服器功能所需的參數未指定，或未通過驗證。</p></td>
<td align="left"><p>表示設定 MBAM 功能所需的參數未指定，或未通過驗證。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>607</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-伺服器/Admin</p></td>
<td align="left"><p>SetupParameterValidationFailureWithError</p></td>
<td align="left"><p>嘗試驗證啟用伺服器功能所需的指定參數時遇到錯誤。</p></td>
<td align="left"><p>表示嘗試驗證啟用伺服器功能所需的指定參數時，遇到錯誤。</p></td>
</tr>
<tr class="even">
<td align="left"><p>700</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-伺服器/Admin</p></td>
<td align="left"><p>DbProviderUnexpectedError</p></td>
<td align="left"><p>DB 提供者意外錯誤。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>701</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-伺服器/Admin</p></td>
<td align="left"><p>DbProviderError</p></td>
<td align="left"><p>DB 提供者錯誤。</p></td>
<td align="left"><p>EventDetails 區段中所包含的訊息應該提供關於實際錯誤的詳細資訊。 以下是一些要驗證的區域：</p>
<ul>
<li><p>MBAM 安裝程式無法使用提供的連線資訊連線至資料庫。 驗證提供給 MBAM 安裝程式的連接字串詳細資料。</p></li>
<li><p>MBAM 安裝程式無法使用提供的網域帳號憑證連線到指定的資料庫。 確認網域帳戶的使用者名稱和密碼是有效的。</p></li>
<li><p>MBAM 安裝程式無法使用提供的網域帳號憑證連線到指定的資料庫。 確認提供的網域帳戶有適當的許可權，可以連線至 MBAM 資料庫。</p></li>
<li><p>如果已安裝更新版本的 MBAM 資料庫，MBAM Dac pac 將會失敗。 確認新版本的 MBAM 伺服器不存在於指定的 SQL server 上。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>702</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-伺服器/Admin</p></td>
<td align="left"><p>DbProviderWarning</p></td>
<td align="left"><p>DB 提供者警告。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="odd">
<td align="left"><p>703</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-伺服器/運營</p></td>
<td align="left"><p>DbProviderInformation</p></td>
<td align="left"><p>DB 提供者資訊。</p></td>
<td align="left"><p>僅提供資訊;不需要進行疑難排解。</p></td>
</tr>
<tr class="even">
<td align="left"><p>704</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-伺服器/Admin</p></td>
<td align="left"><p>DbProviderDacError</p></td>
<td align="left"><p>部署資料層應用程式時發生錯誤。</p></td>
<td align="left"><p>MBAM 會將其資料庫封裝為資料層級應用程式，並嘗試使用 DacServices 將其註冊。 內容中的錯誤訊息是由 DAC 服務報告。 事件應包含導致其發生之情況的詳細資訊。 閱讀錯誤訊息中的資訊，以疑難排解並修正問題。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>705</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-伺服器/Admin</p></td>
<td align="left"><p>DbProviderDacWarning</p></td>
<td align="left"><p>部署資料層應用程式時出現警告。</p></td>
<td align="left"><p>MBAM 會將其資料庫封裝為資料層級應用程式，並嘗試使用 DacServices 將其註冊。 內容中的警告訊息是由 DAC 服務報告。 事件應包含導致其發生之情況的詳細資訊。 閱讀警告訊息中的資訊，以疑難排解並修正問題。</p></td>
</tr>
<tr class="even">
<td align="left"><p>706</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-伺服器/運營</p></td>
<td align="left"><p>DbProviderDacInformation</p></td>
<td align="left"><p>部署資料層應用程式時引發了訊息。</p></td>
<td align="left"><p>僅提供資訊;不需要進行疑難排解。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>800</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-伺服器/Admin</p></td>
<td align="left"><p>ReportProviderUnexpectedError</p></td>
<td align="left"><p>報表提供者意外錯誤。</p></td>
<td align="left"><p>報表提供者意外錯誤。 說明{exceptionDetails}以下是一些可能例外狀況的詳細資料：</p>
<p><strong>取得目錄 &#39; {directoryName} 的名稱時，發生錯誤 &#39;</strong></p>
<p><strong>取得目錄 &#39; {directoryName} 的檔案時發生例外狀況 &#39;</strong></p>
<p><strong>列舉目錄 &#39; {directoryName} 中的目錄時發生例外狀況 &#39;</strong></p>
<p><strong>讀取檔案 &#39; {fileName} 的所有位元組時發生例外狀況 &#39;</strong></p>
<p>在 MBAM 安裝期間，MBAM [設定] unzips 所有報告檔案，移至指定的安裝路徑。 在報表安裝過程中，安裝模組會嘗試在安裝路徑存取解壓縮的報表檔案，並與 SQL Reporting services 進行通訊，以發佈報表檔案。 當 MBAM 無法存取解壓縮安裝路徑中的檔案/資料夾時，就會發生上述錯誤。 以下是一些針對此問題進行疑難排解的秘訣：</p>
<ul>
<li><p>確認已安裝 MBAM。</p></li>
<li><p>確認 regkey HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\MBAM Server\InstallationPath 存在，且可供執行的使用者存取。</p></li>
<li><p>確認 [MBAM InstallationPath] 下的 [報告檔案] 路徑不超過248個字元。</p></li>
<li><p>確認 MBAM Setup 資料夾或 MBAM 安裝路徑中所包含的檔案在安裝後沒有被修改過。</p></li>
<li><p>確認執行安裝程式的使用者已獲得授權，可從 MBAM 安裝資料夾讀取/寫入。</p></li>
</ul>
<p><strong>Reporting Services 連線失敗。{exceptionDetails}</strong></p>
<p>在 MBAM 報告安裝期間，模組會嘗試與 SSRS web 服務進行通訊，以建立資料夾併發布報表。 上述訊息表示 MBAM 無法找到或與 SSRS web 服務進行通訊。 以下是一些針對此問題進行疑難排解的秘訣：</p>
<ul>
<li><p>確認已在指定的電腦上安裝 SSRS。</p></li>
<li><p>使用 SSRS 主控台驗證 SSRS 已啟用且正在執行。</p></li>
<li><p>確認執行設定的使用者有權存取 SSRS。</p></li>
</ul>
<p><strong>無法使用 Reporting Services 實例 URL 來移除 MBAM 報告，&#39; {SSRSInstanceUrl} &#39;。確定 MBAM 報表所需的 SSRS 實例正在執行且設定正確。</strong></p>
<p>當 MBAM 安裝失敗或使用者停用 MBAM 報告功能時，安裝模組會移除 SSRS 報告。 上述訊息表示 MBAM 無法移除 SSRS 報告。 以下是一些針對此問題進行疑難排解的秘訣：</p>
<ul>
<li><p>確認已在指定的電腦上安裝 SSRS。</p></li>
<li><p>使用 SSRS 主控台驗證 SSRS 已啟用且正在執行。</p></li>
<li><p>確認執行設定的使用者有權存取 SSRS。</p></li>
</ul>
<p><strong>發佈報表時，發生錯誤。{exceptionDetails}.</strong></p>
<p>在 MBAM 報告安裝期間，模組會嘗試與 SSRS web 服務進行通訊，以建立資料夾併發布報表。 上述訊息指出在發佈報表時，SSRS web 服務報告和例外狀況。 以下是一些針對此問題進行疑難排解的秘訣：</p>
<ul>
<li><p>使用 SSRS 主控台驗證 SSRS 已啟用且正在執行。</p></li>
<li><p>確認執行設定的使用者有權存取/將報告發布至 SSRS。</p></li>
</ul>
<p><strong>群組使用者名稱 &#39; {userName} &#39; 已存在的原則。 如果這不正確，請手動修正重複或無效原則的報表服務。</strong></p>
<p>發佈 MBAM 報表之後，MBAM 安裝程式會嘗試建立 MBAM 報表使用者角色（如果尚未存在）並設定對應的使用者原則。 上述錯誤表示 SSRS web 服務在設定報表使用者角色原則時拋出例外狀況。 依照事件訊息中的指示進行，然後參閱 &quot; <a href="https://www.microsoft.com/technet/support/ee/transform.aspx?ProdName=SQL+Server+Reporting+Services&amp;ProdVer=8.00&amp;EvtID=rsInvalidPolicyDefinition&amp;EvtSrc=Microsoft.ReportingServices.Diagnostics.ErrorStrings.resources.Strings&amp;LCID=1033&amp;quot" data-raw-source="https://www.microsoft.com/technet/support/ee/transform.aspx?ProdName=SQL+Server+Reporting+Services&amp;amp;ProdVer=8.00&amp;amp;EvtID=rsInvalidPolicyDefinition&amp;amp;EvtSrc=Microsoft.ReportingServices.Diagnostics.ErrorStrings.resources.Strings&amp;amp;LCID=1033&amp;quot"> https://www.microsoft.com/technet/support/ee/transform.aspx?ProdName=SQL+Server+Reporting+Services&amp 。ProdVer = 8.00 &amp; EvtID = rsInvalidPolicyDefinition EvtSrc = ReportingServices. ErrorStrings... &amp; 字串 &amp; LCID = 1033&q </a> ; 如需更多協助。</p>
<p><strong>驗證 SSRS {exceptionDetails} 的存取權時發生錯誤。</strong></p>
<p>在先決條件檢查中，MBAM 安裝程式會驗證使用者是否具有在 SSRS 下存取/建立資料夾的必要許可權。 錯誤訊息指出在驗證對 SSRS 的存取時，發生了例外狀況。 如需調試秘訣的詳細資訊，請參閱例外狀況。</p>
<p><strong>檢查 SSRS URL 時發生 SOAP 錯誤。{exceptionDetails}</strong></p>
<p><strong>檢查 SSRS URL 時發生 web 錯誤。{exceptionDetails}</strong></p>
<p><strong>檢查 SSRS URL 時發生 HTTP/HTTPs 錯誤。{exceptionDetails}</strong></p>
<p><strong>檢查 SSRS URL 時發生錯誤。{exceptionDetails}</strong></p>
<p>在先決條件檢查中，MBAM 安裝程式會檢索與提供的 SSRS 實例相關聯的 Url，並嘗試與 SSRS web 服務進行通訊。 上述錯誤訊息指出位於指定 URL 的 SSRS web 服務引發了例外狀況，如需詳細資訊，請參閱例外狀況詳細資料。 以下是解決 SSRS 通訊問題的一些秘訣。</p>
<ul>
<li><p>確認已在指定的電腦上安裝 SSRS。</p></li>
<li><p>使用 SSRS 主控台驗證 SSRS 已啟用且正在執行。</p></li>
<li><p>確認執行設定的使用者有權存取 SSRS。</p></li>
</ul>
<p><strong>檢索 SSRS 版本時發生錯誤。 {exceptionDetails}</strong></p>
<p>在先決條件檢查中，MBAM [安裝程式查詢 WMI]，以取得與提供的 SSRS 實例相關聯的版本號碼。 上述錯誤訊息指出查詢 WMI 時發生例外狀況。 如需詳細資訊，請參閱 exceptionDetails。 以下是您可以執行的一些檢查：</p>
<ul>
<li><p>確認在指定的電腦上已安裝具有指定實例名稱的 SSRS。</p></li>
<li><p>使用 SSRS 主控台驗證 SSRS 已啟用且正在執行。</p></li>
<li><p>確認執行設定的使用者已獲得授權，可在 WMI 命名空間下查詢 SSRS 類別。</p></li>
</ul>
<p><strong>目前的使用者無權存取 WMI 命名空間 &#39; {ssrsWMINamespace} &#39;。</strong></p>
<p><strong>列舉命名空間 &#39; {ssrsWMINamespace} &#39; 時發生錯誤。 找不到本機主機上 SSRS WMI 提供者的 RPC 伺服器。</strong></p>
<p><strong>列舉命名空間 &#39; {ssrsNamespace} &#39; 時發生錯誤。 無法在本機主機上找到 SSRS 的實例。</strong></p>
<p><strong>存取 WMI 時發生錯誤。 找不到實例 &#39; {ssrsInstance} &#39; 的 RPC 伺服器。</strong></p>
<p><strong>存取 WMI 時發生錯誤。 實例名稱 &#39; {ssrsInstanceName} &#39; 不正確。</strong></p>
<p><strong>存取 WMI 時發生錯誤。 在本機主機上，找不到 &#39; {ssrsInstanceName} &#39; 的實例。</strong></p>
<p>在先決條件檢查中，MBAM [安裝程式查詢 WMI]，以取得與指定實例相關的 WMI 命名空間。 上述錯誤訊息表示在查詢 WMI 時，發生和例外狀況。 如需詳細資訊，請參閱 exceptionDetails。 以下是您可以執行的一些檢查：</p>
<ul>
<li><p>確認在指定的電腦上已安裝具有指定實例名稱的 SSRS。</p></li>
<li><p>使用 SSRS 主控台驗證 SSRS 已啟用且正在執行。</p></li>
<li><p>確認執行設定的使用者有權在 WMI 命名空間下存取/查詢 SSRS 類別。</p></li>
</ul></td>
</tr>
<tr class="even">
<td align="left"><p>801</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-伺服器/Admin</p></td>
<td align="left"><p>ReportProviderError</p></td>
<td align="left"><p>報表提供者意外錯誤。</p></td>
<td align="left"><p>已知 SQL server reporting services 實例名稱，MBAM 會嘗試尋找與報告實例相對應的 WMI 命名空間，並連接到該命名空間。 如果 MBAM 在 MBAM 搜尋或嘗試連線至 SSRS WMI 命名空間時遇到例外狀況，就會發生此錯誤。 若要取得更多詳細資料，請參閱 MBAM 安裝通道中記錄的錯誤訊息中的資訊。 以下是您可以檢查的一些事項：</p>
<ul>
<li><p>確認已提供實例名稱的 SSRS 已啟動且正在執行</p></li>
<li><p>確認執行 MBAM 安裝的使用者帳戶具有查詢/連線至 SSRS WMI 命名空間的必要許可權</p></li>
</ul></td>
</tr>
<tr class="odd">
<td align="left"><p>802</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-伺服器/Admin</p></td>
<td align="left"><p>ReportProviderWarning</p></td>
<td align="left"><p>報表提供者警告。</p></td>
<td align="left"><p></p></td>
</tr>
<tr class="even">
<td align="left"><p>803</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-伺服器/運營</p></td>
<td align="left"><p>ReportProviderInformation</p></td>
<td align="left"><p>報表提供者資訊。</p></td>
<td align="left"><p>僅提供資訊;不需要進行疑難排解。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>900</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-伺服器/Admin</p></td>
<td align="left"><p>CMProviderUnexpectedError</p></td>
<td align="left"><p>CM 提供者意外錯誤。</p></td>
<td align="left"><p>指示在 MBAM 中 enabling\disabling 或設定 Configuration Manager （CM）整合功能時發生終止錯誤。 已知錯誤包括：</p>
<ul>
<li><p>無法透過 SMS 提供者連接至 CM 網站伺服器</p></li>
<li><p>無法從註冊表讀取</p></li>
<li><p>無法在檔案系統中建立或刪除資料夾</p></li>
<li><p>在本機電腦上找不到 Configuration Manager 主控台安裝的問題</p></li>
<li><p>無法為在 CM 中設定為 SRS 角色點的 SSRS 實例取得資訊</p></li>
</ul>
<p>事件訊息將包含有關特定錯誤的詳細資訊。 確認所有的 MBAM 軟體先決條件檢查都經過了。 確認 MBAM 登錄路徑（如果存在） HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\MBAM 伺服器，且所有的子專案都是可讀的。 確認 MBAM 已與支援的 Configuration Manager 版本整合。 確認已在呼叫 MBAM 設定的電腦上安裝 Configuration Manager 主控台，且可以使用該主機連線至目標 CM 網站伺服器。 確認在 CM 中已將有效的 SSRS 實例設定為 SRS 角色點，且執行 MBAM 安裝程式的使用者擁有 SSRS 實例的 read\write 許可權。</p></td>
</tr>
<tr class="even">
<td align="left"><p>901</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-伺服器/Admin</p></td>
<td align="left"><p>CMProviderError</p></td>
<td align="left"><p>CM 提供者意外錯誤。</p></td>
<td align="left"><p>指示在 MBAM 中 enabling\disabling 或設定 Configuration Manager （CM）整合功能時發生終止錯誤。 已知錯誤包括：</p>
<ul>
<li><p>無法透過 SMS 提供者連接至 CM 網站伺服器</p></li>
<li><p>無法從註冊表讀取</p></li>
<li><p>無法在檔案系統中建立或刪除資料夾</p></li>
<li><p>在本機電腦上找不到 Configuration Manager 主控台安裝的問題</p></li>
<li><p>在 SSRS 中缺少 ConfigMgr 資料夾做為 SRS 角色點報告的根資料夾</p></li>
<li><p>在 SSRS 中遺失 ConfigMgr 共用資料來源</p></li>
<li><p>在在 CM 中設定為 SRS 角色點的 SSRS 實例中，無法部署 SSRS 報告</p></li>
<li><p>無法在 CM 中建立設定項目與比較基準</p></li>
</ul>
<p>事件訊息將包含有關特定錯誤的詳細資訊。 確認所有的 MBAM 軟體先決條件檢查都經過了。 確認 MBAM 登錄路徑（如果存在） HKEY_LOCAL_MACHINE \SOFTWARE\Microsoft\MBAM 伺服器，且所有的子專案都是可讀的。 確認 MBAM 已與支援的 Configuration Manager 版本整合。 確認已在呼叫 MBAM 設定的電腦上安裝 Configuration Manager 主控台，且可以使用該主機連線至目標 CM 網站伺服器。 確認使用者擁有所需的 read\write 許可權，才能在 CM 中建立設定項目、比較基準及集合。 確認在 CM 中已將有效的 SSRS 實例設定為 SRS 角色點，且執行 MBAM 安裝程式的使用者擁有 SSRS 實例的 read\write 許可權。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>902</p></td>
<td align="left"><p>Microsoft_Windows_MBAM_Server_Admin</p></td>
<td align="left"><p>CMProviderWarning</p></td>
<td align="left"><p>CM 提供者警告。</p></td>
<td align="left"><p>表示啟用 Configuration Manager （CM）整合功能時發生非終止錯誤。 已知錯誤包括：無法在 MBAM 支援的電腦集合中以 CM 提交集合規則，以及其他 SSRS 與網路相關錯誤。</p>
<p>事件訊息將包含有關特定錯誤的詳細資訊。 產生此警告的部分作業會在警告之後停用。 如果在數個重試之後再次出現錯誤，則 MBAM 可能會以實際的錯誤為結束。 檢查記錄中的其他事件訊息，進一步診斷 MBAM 設定。</p></td>
</tr>
<tr class="even">
<td align="left"><p>903</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-伺服器/運營</p></td>
<td align="left"><p>CMProviderInformation</p></td>
<td align="left"><p>CM 提供者資訊。</p></td>
<td align="left"><p>僅提供資訊;不需要進行疑難排解。</p></td>
</tr>
</tbody>
</table>

 

## 作業


下表包含在 MBAM 執行時可能發生的事件識別碼的訊息與疑難排解資訊。

<table>
<colgroup>
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
<col width="20%" />
</colgroup>
<thead>
<tr class="header">
<th align="left">事件識別碼</th>
<th align="left">Source</th>
<th align="left">事件符號</th>
<th align="left">訊息</th>
<th align="left">疑難排解</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left"><p>sr-1</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/系統管理員</p></td>
<td align="left"><p>WebAppSpnError</p></td>
<td align="left"><p>應用程式： {SiteName} {VirtualDirectory} 缺少下列服務主體名稱（Spn）： {ListOfSpns} 在帳戶上註冊所需的 Spn： {ExecutionAccount}。</p></td>
<td align="left"><p>若要將集成的 Windows 驗證成功，必須在適當的地方使用必要的 Spn。 此訊息表示 MBAM 應用程式所需的 SPN 未正確設定。 此事件中所包含的詳細資料應提供詳細資訊。</p>
<p><a href="mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md#bkmk-prereqsams" data-raw-source="[MBAM 2.5 Server Prerequisites for Stand-alone and Configuration Manager Integration Topologies](mbam-25-server-prerequisites-for-stand-alone-and-configuration-manager-integration-topologies.md#bkmk-prereqsams)">如需詳細資訊，請參閱適用于獨立與 Configuration Manager 整合拓朴的 MBAM 2.5 Server 必備元件中的「服務主要名稱（SPN）」 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>4</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/運營</p></td>
<td align="left"><p>PerformanceCounterError</p></td>
<td align="left"><p>檢索效能計數器時發生錯誤。</p>
<p>訊息： {EventMessage} 類別： {CategoryOfPerformanceCounter} 效能計數器： {NameOfPerformanceCounter} Instance： {效能計數器類別實例的名稱} 例外狀況： {ExceptionThrown}</p>
<p>追蹤訊息將包含實際的例外訊息，這裡有一些說明：</p>
<p><strong>ArgumentNullException </strong> ：如果要求的效能計數器的類別、計數器或實例無效，就會引發此例外狀況。</p>
<p><strong>InvalidOperationException </strong> ： [類別] 是空字串（ &quot; &quot; ）。-或-counterName 是一個空字串（ &quot; &quot; ）。</p>
<p>-或-要求的讀取/寫入權限設定對於這個計數器無效。</p>
<p>-或-指定的類別不存在（若為 readOnly 則為 true）。</p>
<p>-或-指定類別不是 .NET Framework 自訂類別（如果 readOnly 是 false）。</p>
<p>-或-指定類別會標示為多重實例，且需要使用實例名稱建立效能計數器。</p>
<p>-或-instanceName 超過127個字元。</p>
<p>-或-類別和 counterName 已當地語系化成不同的語言。</p>
<p><strong>ComponentModel </strong> ：存取系統 API 時發生錯誤。</p>
<p><strong>PlatformNotSupportedException </strong> ：平臺是 windows 98 或 Windows Millennium Edition （我），不支援效能計數器。</p>
<p><strong>UnauthorizedAccessException </strong> ：執行的程式碼沒有系統管理許可權，因此試圖讀取效能計數器。</p></td>
<td align="left"><p>事件中所包含的訊息將提供更多關於所引發之例外狀況的詳細資料。 如果引發 UnauthorizedAccessException，請確認 MBAM 執行帳戶（應用程式池）有權存取效能計數器 Api。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>100</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/系統管理員</p></td>
<td align="left"><p>AdminServiceRecoveryDbError</p></td>
<td align="left"><p><strong>GetMachineUsers </strong> ：從資料庫取得使用者資訊時發生錯誤。 訊息： {message}-或-</p>
<p><strong>GetRecoveryKey </strong> ：從資料庫取得復原金鑰時發生錯誤。 訊息： {message}-或-</p>
<p><strong>GetRecoveryKey </strong> ：從資料庫取得使用者資訊時發生錯誤。 訊息： {message}-或-</p>
<p><strong>GetRecoveryKeyIds </strong> ：從資料庫取得復原金鑰識別碼時發生錯誤。 訊息： {message}-或-</p>
<p><strong>GetTpmHashForUser </strong> ：從復原資料庫取得 TPM 雜湊資料時發生錯誤。 訊息： {message}-或-</p>
<p><strong>GetTpmHashForUser </strong> ：從復原資料庫取得 TPM 雜湊資料時發生錯誤。 訊息： {message}-或-</p>
<p><strong>QueryDriveRecoveryData </strong> ：從資料庫取得磁片磁碟機恢復資料時發生錯誤。 訊息： {message}-或-</p>
<p><strong>QueryRecoveryKeyIdsForUser </strong> ：從資料庫取得復原金鑰識別碼時發生錯誤。 訊息： {message}-或-</p>
<p><strong>QueryVolumeUsers </strong> ：從資料庫取得使用者資訊時發生錯誤。</p></td>
<td align="left"><p>每當與 MBAM 復原資料庫進行通訊時，就會記錄此訊息。 通讀追蹤中所包含的資訊，以取得例外狀況的特定詳細資料。</p>
<p>如需詳細的疑難排解步驟，請參閱 TechNet 文章 <a href="https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx" data-raw-source="[How to Troubleshoot Connecting to the SQL Server Database Engine](https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx)"> 如何排查連線至 SQL Server 資料庫引擎的問題 </a> 。</p></td>
</tr>
<tr class="even">
<td align="left"><p>101</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/系統管理員</p></td>
<td align="left"><p>AdminServiceComplianceDbError</p></td>
<td align="left"><p><strong>GetRecoveryKey </strong> ：將審核事件記錄到合規性資料庫時發生錯誤。 訊息： {message}-或-</p>
<p><strong>GetRecoveryKeyIds </strong> ：將審核事件記錄到合規性資料庫時發生錯誤。 訊息： {message}-或-</p>
<p><strong>GetTpmHashForUser </strong> ：將審核事件記錄到合規性資料庫時發生錯誤。 訊息： {message}-或-</p>
<p><strong>QueryRecoveryKeyIdsForUser </strong> ：將審核事件記錄到合規性資料庫時發生錯誤。 訊息： {message}-或-</p>
<p><strong>QueryDriveRecoveryData </strong> ：將審核事件記錄到合規性資料庫時發生錯誤。 訊息： {message}</p></td>
<td align="left"><p>每當通報 MBAM 合規性資料庫時發生例外狀況時，就會記錄此訊息。 通讀追蹤中所包含的資訊，以取得例外狀況的特定詳細資料。</p>
<p>如需詳細的疑難排解步驟，請參閱 TechNet 文章 <a href="https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx" data-raw-source="[How to Troubleshoot Connecting to the SQL Server Database Engine](https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx)"> 如何排查連線至 SQL Server 資料庫引擎的問題 </a> 。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>102</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/系統管理員</p></td>
<td align="left"><p>AgentServiceRecoveryDbError</p></td>
<td align="left"><p></p></td>
<td align="left"><p>此訊息表示 MBAM Agent 服務嘗試與恢復資料庫通訊時發生例外狀況。 通讀事件中所包含的訊息，以取得例外狀況的特定資訊。</p>
<p>請參閱 TechNet 文章 <a href="https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx" data-raw-source="[How to Troubleshoot Connecting to the SQL Server Database Engine](https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx)"> 如何針對連線至 SQL Server 資料庫引擎進行疑難排解 </a> ，以驗證 MBAM 應用程式池帳戶是否有適當的許可權，以在 MBAM 復原資料庫上連線或執行。</p></td>
</tr>
<tr class="even">
<td align="left"><p>103</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/系統管理員</p></td>
<td align="left"><p>AgentServiceError</p></td>
<td align="left"><p>無法偵測到用戶端電腦帳戶或資料移轉使用者帳戶。 -或-</p>
<p>呼叫者身分識別的帳戶驗證失敗。</p></td>
<td align="left"><p>每當呼叫 &quot; PostKeyRecoveryInfo &quot; 、 &quot; IsRecoveryKeyResetRequired &quot; 、 &quot; CommitRecoveryKeyRest &quot; 或 &quot; GetTpmHash &quot; 網頁方法在 MBAM Agent services 上時，它都會檢索呼叫者內容來取得呼叫者認證。 如果呼叫者內容為 null 或空，則 MBAM Agent 服務記錄 &quot; 無法偵測用戶端電腦帳戶或資料移轉使用者帳戶。&quot;</p>
<p>&quot; &quot; 如果網頁方法預期呼叫者是電腦帳戶，而呼叫者不是電腦帳戶，或者網頁方法是 excepting 呼叫者是使用者帳戶，且呼叫者不是資料移轉群群組帳戶的使用者帳戶或成員，就會記錄呼叫者身分識別的訊息帳戶驗證失敗。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>104</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/系統管理員</p></td>
<td align="left"><p>StatusServiceComplianceDbConfigError</p></td>
<td align="left"><p>&quot;Registry 中的合規性資料庫連線字串為空白。&quot;</p></td>
<td align="left"><p>每當合規性 db 連接字串無效時，就會記錄此訊息。</p>
<p>驗證登錄機碼 HKLM\Software\Microsoft\MBAM 的值 Server\Web\ComplianceDBConnectionString</p></td>
</tr>
<tr class="even">
<td align="left"><p>105</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/系統管理員</p></td>
<td align="left"><p>StatusServiceComplianceDbError</p></td>
<td align="left"><p></p></td>
<td align="left"><p>此錯誤表示 MBAM 網站/web 服務無法連線至 MBAMCompliance 資料庫。</p>
<p>請參閱 TechNet 文章 <a href="https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx" data-raw-source="[How to Troubleshoot Connecting to the SQL Server Database Engine](https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx)"> 如何排查連線至 SQL Server 資料庫引擎的問題， </a> 以確認 IIS 應用程式池帳戶可以連線到 MBAM 合規性資料庫。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>106</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/系統管理員</p></td>
<td align="left"><p>HelpdeskError</p></td>
<td align="left"><p>URL {URL} 的要求導致內部錯誤。 -或-</p>
<p>取得執行內容資訊時發生錯誤。 無法驗證服務主體名稱（SPN）註冊。 -或-</p>
<p>驗證服務主體名稱（SPN）註冊時發生錯誤。</p></td>
<td align="left"><p>表示已在技術支援應用程式中引發未處理的例外狀況。 在 MBAM 系統管理員的操作通道中查看記錄專案，找出特定的例外狀況。 或</p>
<p>在最初的技術支援網站載入作業期間，會執行 SPN 檢查。 若要驗證 SPN，技術支援人員需要執行帳戶資訊、IIS Sitename，以及對應至技術支援網站的 ApplicationVirtualPath。 當其中一個或多個無效或遺失時，就會記錄此錯誤訊息。 或</p>
<p>這則訊息表示執行 SPN 驗證時，會發生安全性例外狀況。 請參閱事件詳細資料區段中包含的例外狀況。</p></td>
</tr>
<tr class="even">
<td align="left"><p>107</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/系統管理員</p></td>
<td align="left"><p>SelfServicePortalError</p></td>
<td align="left"><p>取得使用者的復原金鑰時發生錯誤。 EventDetails： {ExceptionMessage}-或-</p>
<p>取得執行內容資訊時發生錯誤。 無法驗證服務主體名稱（SPN）註冊。 EventDetails：使用者： {username 身分識別} 應用程式： {SiteName\ApplicationVirtualPath}-或-</p>
<p>驗證服務主體名稱（SPN）註冊時發生錯誤。 EventDetails:{ExceptionMessage}</p></td>
<td align="left"><p>指示在要求取得檢索復原金鑰時，引發了意外的例外狀況。 請參閱 [事件詳細資料] 區段中包含的例外狀況訊息。 如果 MBAM 支援人員已啟用追蹤功能，請參閱追蹤資料，以取得詳細的例外訊息。 或</p>
<p>在初始載入作業期間，自助入口網站（SSP）會檢索與自助網站相關的執行帳戶資訊、IIS Sitename 及 ApplicationVirtualPath，以驗證 SPN。 當這些錯誤訊息中有一或多個無效時，就會記錄此錯誤訊息。 或</p>
<p>這則訊息表示執行 SPN 驗證時發生安全性例外狀況。 請參閱事件詳細資料區段中包含的例外狀況。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>108</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/系統管理員</p></td>
<td align="left"><p>DomainControllerError</p></td>
<td align="left"><p>解析功能變數名稱 {DomainName} 時發生錯誤，發生記憶體分配失敗。 -或-</p>
<p>無法調用 DsGetDcName 方法。 EventDetails:{ExceptionMessage}</p></td>
<td align="left"><p>若要解析功能變數名稱，MBAM 會利用 &quot; DsGetDcName &quot; windows API。 當 &quot; DsGetDcName 傳回 &quot; &quot; ERROR_NOT_ENOUGH_MEMORY &quot; 表示記憶體分配失敗時，就會記錄此訊息。 或</p>
<p>此訊息表示 &quot; &quot; 無法在託管系統上使用 DsGetDcName API 方法。</p></td>
</tr>
<tr class="even">
<td align="left"><p>109</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/系統管理員</p></td>
<td align="left"><p>WebAppRecoveryDbError</p></td>
<td align="left"><p>讀取恢復資料庫的設定時發生錯誤。 未設定恢復資料庫的連線字串。 訊息： {message}-或-</p>
<p><strong>DoesUserHaveMatchingRecoveryKey </strong> ：取得使用者的復原金鑰識別碼時發生錯誤。 訊息： {message}-或-</p>
<p><strong>QueryDriveRecoveryData </strong> ：取得磁片磁碟機修復資料時發生錯誤。 訊息： {message}-或-</p>
<p><strong>QueryRecoveryKeyIdsForUser </strong> ：取得使用者的復原金鑰識別碼時發生錯誤。 訊息： {message}-或-</p>
<p>從復原資料庫取得 TPM 密碼雜湊時，發生錯誤。 EventDetails:{ExceptionMessage}</p></td>
<td align="left"><p>此訊息表示 HKLM\Software\Microsoft\MBAM Server\Web\RecoveryDBConnectionString 上的復原資料庫連線字串資訊 &quot; &quot; 無效。 確認指定的登錄機碼值。 或</p>
<p>如果記錄任何剩餘的訊息，請參閱 TechNet 文章 <a href="https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx" data-raw-source="[How to Troubleshoot Connecting to the SQL Server Database Engine](https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx)"> 說明如何疑難排解連線至 SQL Server 資料庫引擎的疑難排解步驟， </a> 以驗證是否可以使用應用程式池認證從 IIS 伺服器連線至 MBAM Recovery 資料庫。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>110</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/系統管理員</p></td>
<td align="left"><p>WebAppComplianceDbError</p></td>
<td align="left"><p>讀取合規性資料庫的設定時發生錯誤。 未設定合規性資料庫的連線字串。 -或-</p>
<p><strong>GetRecoveryKeyForCurrentUser </strong> ：將審核事件記錄到合規性資料庫時發生錯誤。 訊息： {message}-或-</p>
<p><strong>QueryRecoveryKeyIdsForUser </strong> ：將審核事件記錄到合規性資料庫時發生錯誤。 訊息： {message}-或-</p>
<p><strong>QueryRecoveryKeyIdsForUser </strong> ：將審核事件記錄到合規性資料庫時發生錯誤。 訊息： {message}</p></td>
<td align="left"><p>此訊息表示 HKLM\Software\Microsoft\MBAM Server\Web\ComplianceDBConnectionString 的合規性 db 連接字串資訊 &quot; &quot; 無效。 確認與上方的登錄機碼相對應的值。 或</p>
<p>如果記錄任何剩餘的訊息，請參閱 TechNet 文章 <a href="https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx" data-raw-source="[How to Troubleshoot Connecting to the SQL Server Database Engine](https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx)"> 說明如何疑難排解連線至 SQL Server 資料庫引擎的疑難排解步驟， </a> 以驗證是否可以使用應用程式池認證從 IIS 伺服器連線至 MBAM 合規性資料庫。</p></td>
</tr>
<tr class="even">
<td align="left"><p>111</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/系統管理員</p></td>
<td align="left"><p>WebAppDbError</p></td>
<td align="left"><p></p></td>
<td align="left"><p>這些錯誤指出下列兩種情況之一</p>
<ul>
<li><p>MBAM 網站/webservices 無法連接至 MBAMCompliance 或 MBAMRecovery 資料庫</p></li>
<li><p>MBAM 網站/webservices 執行帳戶（應用程式池帳戶）無法在 MBAMCompliance 或 MBAMRecovery 資料庫上執行 GetVersion 預存程序</p></li>
</ul>
<p>事件中所包含的訊息將會提供更多關於例外狀況的詳細資料。</p>
<p>請參閱 TechNet 文章中所列的疑難排解步驟，以 <a href="https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx" data-raw-source="[How to Troubleshoot Connecting to the SQL Server Database Engine](https://social.technet.microsoft.com/wiki/contents/articles/2102.how-to-troubleshoot-connecting-to-the-sql-server-database-engine.aspx)"> 驗證連線至 SQL Server 資料庫引擎的方式， </a> 以確認 MBAM 執行帳戶（應用程式池帳戶）可以連線至 MBAM 合規性/復原資料庫，且具有適當的許可權，可以執行 GetVersion 預存程序。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>112</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/系統管理員</p></td>
<td align="left"><p>WebAppError</p></td>
<td align="left"><p>驗證服務主體名稱（SPN）註冊時發生錯誤。 EventDetails:{ExceptionMessage}</p></td>
<td align="left"><p>若要執行 SPN 驗證，請 MBAM 查詢 Active Directory，以取得 Spn 對應的 [執行] 帳戶清單。 MBAM 也會查詢 &quot;ApplicationHost.config&quot; ，以取得 MBAM 的網站系結。 此錯誤訊息指出 MBAM 無法與 Active Directory 進行通訊，或無法載入 applicationHost.config 檔案。</p>
<p>確認執行帳戶（應用程式池帳戶）具有查詢 AD 或 ApplicationHost.config 檔案的許可權。 此外，請確認 ApplicationHost.config 檔案中的網站系結專案。</p></td>
</tr>
<tr class="even">
<td align="left"><p>200</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/運營</p></td>
<td align="left"><p>HelpDeskInformation</p></td>
<td align="left"><p>管理網站應用程式已成功找到並聯機到受支援的復原資料庫版本。 -或-</p>
<p>管理網站應用程式已成功找到並聯機到受支援版本的合規性資料庫。</p></td>
<td align="left"><p>指示從 MBAM 支援人員網站成功連線至 [恢復/合規性資料庫]。</p></td>
</tr>
<tr class="odd">
<td align="left"><p>201</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/運營</p></td>
<td align="left"><p>SelfServicePortalInformation</p></td>
<td align="left"><p>自助服務入口網站已成功找到並聯機到受支援的復原資料庫版本。 -或-</p>
<p>自助服務入口網站已成功找到並聯機到受支援版本的合規性資料庫。</p></td>
<td align="left"><p>指示從 MBAM 自助服務入口網站成功連線到恢復/合規性資料庫。</p></td>
</tr>
<tr class="even">
<td align="left"><p>202</p></td>
<td align="left"><p>Microsoft-Windows-MBAM-Web/運營</p></td>
<td align="left"><p>WebAppInformation</p></td>
<td align="left"><p>應用程式的 Spn 註冊正確。</p></td>
<td align="left"><p>表示 MBAM 技術支援網站所需的 Spn 已正確登錄至執行中的帳戶。</p></td>
</tr>
</tbody>
</table>

 


## 相關主題


[MBAM 2.5 技術參考資料](technical-reference-for-mbam-25.md)

[用戶端事件記錄檔](client-event-logs.md)

 
## 取得 MBAM 的建議嗎？
- 在[此](http://mbam.uservoice.com/forums/268571-microsoft-bitlocker-administration-and-monitoring)新增或投票建議。
- 如需 MBAM 問題，請使用[MBAM TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopmbam)。
 





