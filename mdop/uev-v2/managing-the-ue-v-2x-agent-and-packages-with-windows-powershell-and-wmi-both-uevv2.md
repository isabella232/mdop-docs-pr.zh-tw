---
title: 使用 Windows PowerShell 和 WMI 管理 UE-V 2 x Agent 和套件
description: 使用 Windows PowerShell 和 WMI 管理 UE-V 2 x Agent 和套件
author: dansimp
ms.assetid: 56e6780b-8b2c-4717-91c8-2af63062ab75
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 6a709d2c66266cf33b8e89ddd905aa0f21eb7dfe
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10811973"
---
# 使用 Windows PowerShell 和 WMI 管理 UE-V 2 x Agent 和套件


您可以使用 Windows 管理工具（WMI）和 Windows PowerShell 來管理 Microsoft 使用者體驗虛擬化（UE-V）2.0、2.1 和 2.1 SP1 Agent 設定和同步處理行為。 如需 UE-V PowerShell Cmdlet 的完整清單，請參閱[ue-v 2 Cmdlet 參考](https://go.microsoft.com/fwlink/?LinkId=393495)（ https://go.microsoft.com/fwlink/?LinkId=393495) 。

**使用 Windows PowerShell 部署 UE-V Agent**

1.  在易於存取的網路共用中階段進行 UE-V 安裝程式檔案。

    **注意**  
    使用 AgentSetup.exe 來部署32位與64位的 UE-V Agent 版本。 Windows Installer 套件、AgentSetupx86.msi 和 AgentSetupx64.msi，可供每個架構使用。 若要在稍後使用安裝檔案卸載 UE-V Agent，您必須使用相同的檔案類型。



2.  使用下列其中一個 Windows PowerShell 命令來安裝 UE-V Agent。

    -   `& AgentSetup.exe /quiet /norestart /log "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

    -   `& msiexec.exe /i "<path to msi file>" /quiet /norestart /l*v "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

**使用 Windows PowerShell 來設定 UE-V Agent**

1. 開啟 Windows PowerShell 視窗。 若要使用 [*電腦*] 參數管理影響電腦所有使用者的電腦設定，請以具有系統管理員許可權的帳戶開啟視窗。

2. 使用下列 Windows PowerShell 命令來設定代理程式。

   <table>
   <colgroup>
   <col width="50%" />
   <col width="50%" />
   </colgroup>
   <thead>
   <tr class="header">
   <th align="left">Windows PowerShell 命令</th>
   <th align="left">描述</th>
   </tr>
   </thead>
   <tbody>
   <tr class="odd">
   <td align="left"><p><code>Get-UevConfiguration</code></p>
   <p></p></td>
   <td align="left"><p>取得有效的 UE-V Agent 設定。 [使用者專用] 設定的優先順序高於 [電腦設定]。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Get-UevConfiguration - CurrentComputerUser</code></p>
   <p></p></td>
   <td align="left"><p>僅取得目前使用者的 UE-V Agent 設定值。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Get-UevConfiguration -Computer</code></p></td>
   <td align="left"><p>取得電腦上所有使用者的 UE-V Agent 設定值。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Get-UevConfiguration -Details</code></p></td>
   <td align="left"><p>取得每個設定設定的詳細資料。 顯示設定的設定位置，或是否使用預設值。 如果目前設定有效，就會顯示。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer –ContactITDescription &lt;IT description&gt;</code></p></td>
   <td align="left"><p>設定 [公司設定中心] 中顯示的 [說明] 連結文字。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration -Computer -ContactITUrl &lt;string&gt;</code></p></td>
   <td align="left"><p>在 [公司設定中心] 中設定 [說明] 連結的連結 URL。 您可以使用任何 URL 通訊協定。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer –EnableDontSyncWindows8AppSettings</code></p></td>
   <td align="left"><p>設定 UE-V Agent 不會同步處理電腦上所有使用者的任何 Windows app。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration -CurrentComputerUser – EnableDontSyncWindows8AppSettings</code></p></td>
   <td align="left"><p>將 UE-V Agent 設定為不同步處理目前電腦使用者的任何 Windows 應用程式。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer –EnableFirstUseNotification</code></p></td>
   <td align="left"><p>針對電腦上的所有使用者，將 UE-V Agent 設定為在代理程式第一次執行時顯示通知。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration -Computer –DisableFirstUseNotification</code></p></td>
   <td align="left"><p>針對電腦上的所有使用者，將 UE-V Agent 設定為在第一次執行代理程式時不顯示通知。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer –EnableSettingsImportNotify</code></p></td>
   <td align="left"><p>當設定同步處理延遲時，會設定 UE-V Agent 通知電腦上的所有使用者。</p>
   <p>使用 <em> DisableSettingsImportNotify </em> 參數來停用通知。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration - CurrentComputerUser -EnableSettingsImportNotify</code></p></td>
   <td align="left"><p>將 UE-V Agent 設定為當設定同步處理延遲時通知目前使用者。</p>
   <p>使用 <em> DisableSettingsImportNotify </em> 參數來停用通知。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer –EnableSyncUnlistedWindows8Apps</code></p></td>
   <td align="left"><p>針對電腦的所有使用者，設定 UE-V Agent 來同步處理未明確停用 Windows 應用程式清單的所有 Windows 應用程式。 如需詳細資訊，請參閱 &quot; &quot; <a href="managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md" data-raw-source="[Managing UE-V 2.x Settings Location Templates Using Windows PowerShell and WMI](managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md)"> 使用 WINDOWS PowerShell 和 WMI 管理 Ue-v A.x 設定位置範本中的 UevAppxPackage </a> 。</p>
   <p>使用 <em> DisableSyncUnlistedWindows8Apps </em> 參數設定 ue-v Agent，只同步處理 Windows 應用程式清單明確啟用的 windows 應用程式。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration - CurrentComputerUser - EnableSyncUnlistedWindows8Apps</code></p></td>
   <td align="left"><p>針對電腦上目前使用者的 Windows 應用程式清單，設定 UE-V Agent 來同步處理所有未明確停用的 Windows 應用程式。 如需詳細資訊，請參閱 &quot; &quot; <a href="managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md" data-raw-source="[Managing UE-V 2.x Settings Location Templates Using Windows PowerShell and WMI](managing-ue-v-2x-settings-location-templates-using-windows-powershell-and-wmi-both-uevv2.md)"> 使用 WINDOWS PowerShell 和 WMI 管理 Ue-v A.x 設定位置範本中的 UevAppxPackage </a> 。</p>
   <p>使用 <em> DisableSyncUnlistedWindows8Apps </em> 參數設定 ue-v Agent，只同步處理 Windows 應用程式清單明確啟用的 windows 應用程式。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration –Computer –DisableSync</code></p></td>
   <td align="left"><p>針對電腦上的所有使用者停用 UE-V。</p>
   <p>使用 <em> EnableSync </em> 參數來啟用或重新啟用。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration –CurrentComputerUser -DisableSync</code></p></td>
   <td align="left"><p>針對電腦上的目前使用者停用 UE-V。</p>
   <p>使用 <em> EnableSync </em> 參數來啟用或重新啟用。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer –EnableTrayIcon</code></p></td>
   <td align="left"><p>針對電腦的所有使用者，在通知區域啟用 UE-V 圖示。</p>
   <p>使用 <em> DisableTrayIcon </em> 參數來停用圖示。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration -Computer -MaxPackageSizeInBytes &lt;size in bytes&gt;</code></p></td>
   <td align="left"><p>設定 UE-V agent 在設定套件檔案大小達到電腦上所有使用者的已定義閾值時進行報告。 設定閥值套件大小（以位元組為單位）。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -CurrentComputerUser -MaxPackageSizeInBytes &lt;size in bytes&gt;</code></p></td>
   <td align="left"><p>設定 UE-V agent 在設定套件檔案大小達到已定義的閾值時進行報告。 設定目前使用者的套件大小警告閾值。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration -Computer -SettingsImportNotifyDelayInSeconds</code></p></td>
   <td align="left"><p>指定使用者收到電腦所有使用者的通知時間（以秒為單位）</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration - CurrentComputerUser -SettingsImportNotifyDelayInSeconds</code></p></td>
   <td align="left"><p>指定傳送目前使用者的通知前的時間（以秒為單位）。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration -Computer -SettingsStoragePath &lt;path to _settings_storage_location&gt;</code></p></td>
   <td align="left"><p>針對電腦的所有使用者定義每電腦設定的儲存位置。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -CurrentComputerUser -SettingsStoragePath &lt;path to _settings_storage_location&gt;</code></p></td>
   <td align="left"><p>定義每個使用者的設定儲存位置。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration –Computer –SettingsTemplateCatalogPath &lt;path to catalog&gt;</code></p></td>
   <td align="left"><p>為電腦的所有使用者設定設定範本的目錄路徑。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer -SyncMethod &lt;sync method&gt;</code></p></td>
   <td align="left"><p>為電腦的所有使用者設定同步處理方法： SyncProvider 或 [無]。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set-UevConfiguration -CurrentComputerUser  -SyncMethod &lt;sync method&gt;</code></p></td>
   <td align="left"><p>為目前的使用者設定同步處理方法： SyncProvider 或 [無]。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Set-UevConfiguration -Computer -SyncTimeoutInMilliseconds &lt;timeout in milliseconds&gt;</code></p></td>
   <td align="left"><p>針對電腦的所有使用者設定同步超時時間（毫秒）</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Set- UevConfiguration -CurrentComputerUser -SyncTimeoutInMilliseconds &lt;timeout in milliseconds&gt;</code></p></td>
   <td align="left"><p>為目前的使用者設定同步處理超時時間。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Clear-UevConfiguration –Computer -&lt;setting name&gt;</code></p></td>
   <td align="left"><p>針對電腦上的所有使用者清除指定的設定。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Clear-UevConfiguration –CurrentComputerUser -&lt;setting name&gt;</code></p></td>
   <td align="left"><p>僅清除目前使用者的指定設定。</p></td>
   </tr>
   <tr class="odd">
   <td align="left"><p><code>Export-UevConfiguration &lt;settings migration file&gt;</code></p></td>
   <td align="left"><p>將 UE-V 電腦設定匯出為設定遷移檔案。 副檔名必須是. uev。</p>
   <p>這個 <code>Export</code> Cmdlet 會匯出所有可使用電腦參數設定的 Ue-v agent 設定 <em> </em> 。</p></td>
   </tr>
   <tr class="even">
   <td align="left"><p><code>Import-UevConfiguration &lt;settings migration file&gt;</code></p></td>
   <td align="left"><p>從設定遷移檔案匯入 UE-V 電腦設定。 副檔名必須是. uev。</p></td>
   </tr>
   </tbody>
   </table>



**若要匯出 UE-V 封裝設定並使用 Windows PowerShell 修復 UE-V 範本**

1.  以系統管理員身分開啟 Windows PowerShell 視窗。

2.  使用下列 Windows PowerShell 命令來設定代理程式。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong>Windows PowerShell 命令</strong></p></td>
    <td align="left"><p><strong>描述</strong></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Export-UevPackage MicrosoftCalculator6. pkgx</p></td>
    <td align="left"><p>從 Microsoft 計算機套件檔案提取設定，並將其轉換成 XML 中的使用者可閱讀格式。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>修復 UevTemplateIndex</p></td>
    <td align="left"><p>修復 UE-V 設定位置範本的索引。</p></td>
    </tr>
    </tbody>
    </table>



**使用 WMI 來設定 UE-V Agent**

1.  使用者體驗虛擬化提供下列一組 WMI 命令。 系統管理員可以使用此介面，在命令列設定 UE-V agent，並自動執行一般的配置工作。

    使用具有系統管理員許可權的帳戶來開啟 Windows PowerShell 視窗。

2.  使用下列 WMI 命令來設定代理程式。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><code>Windows PowerShell command</code></th>
    <th align="left">描述</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><code>Get-WmiObject -Namespace root\Microsoft\UEV Configuration</code></p>
    <p></p></td>
    <td align="left"><p>顯示作用中 UE-V Agent 設定。 [使用者專用] 設定的優先順序高於 [電腦設定]。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Get-WmiObject -Namespace root\Microsoft\UEV UserConfiguration</code></p></td>
    <td align="left"><p>顯示為使用者定義的 UE-V Agent 配置。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p></td>
    <td align="left"><p>顯示為電腦定義的 UE-V Agent 配置。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Get-WmiObject –Namespace root\Microsoft\Uev ConfigurationItem</code></p></td>
    <td align="left"><p>顯示每個設定專案的詳細資料。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code>$config.SettingsStoragePath = &lt;path_to_settings_storage_location&gt;</code></p>
    <p>$config]。Put （）</p></td>
    <td align="left"><p>定義每個電腦的設定儲存位置。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV UserConfiguration</code></p>
    <p><code>$config.SettingsStoragePath = &lt;path_to_settings_storage_location&gt;</code></p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p>定義每個使用者的設定儲存位置。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code>$config.SyncTimeoutInMilliseconds = &lt;timeout_in_milliseconds&gt;</code></p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p>針對電腦的所有使用者設定同步超時時間（以毫秒為單位）。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code>$config.MaxPackageSizeInBytes = &lt;size_in_bytes&gt;</code></p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p>設定 UE-V Agent 在設定套件檔案大小達到已定義的閾值時進行報告。 針對電腦的所有使用者，設定閾值套件檔案大小（以位元組為單位）。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code>$config.SyncMethod = &lt;sync_method&gt;</code></p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p>為電腦的所有使用者設定同步處理方法： SyncProvider 或 [無]。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code>$config.&lt;setting name&gt; = $true</code></p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p>若要啟用特定的每電腦設定，請清除該設定，然後使用 <em> $null </em> 做為設定值。 針對每位使用者設定使用 UserConfiguration。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code>$config.&lt;setting name&gt; = $false</code></p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p>若要停用特定的每電腦設定，請清除該設定，然後使用 <em> $null </em> 做為設定值。 針對每位使用者設定使用 [使用者設定]。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code>$config.&lt;setting name&gt; = &lt;setting value&gt;</code></p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p>更新特定的每電腦設定。 若要清除此設定，請使用 <em> $null </em> 做為設定值。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>$config = Get-WmiObject -Namespace root\Microsoft\UEV ComputerConfiguration</code></p>
    <p><code></code>$config]。 &lt;設定名稱 &gt;  =  &lt; 設定值&gt;</p>
    <p><code>$config.Put()</code></p></td>
    <td align="left"><p>針對電腦的所有使用者更新特定的每個使用者設定。 若要清除此設定，請使用 <em> $null </em> 做為設定值。</p></td>
    </tr>
    </tbody>
    </table>



~~~
Upon configuration of the UE-V Agent with WMI and Windows PowerShell, the defined configuration is stored in the registry in the following locations.

`\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\UEV\Agent\Configuration`

`\HKEY_CURRENT_USER\SOFTWARE\Microsoft\UEV\Agent\Configuration`
~~~

**若要匯出 UE-V 封裝設定並使用 WMI 修復 UE-V 範本**

1.  UE-V 提供下列幾組 WMI 命令。 系統管理員可以使用此介面匯出套件或修復 UE-V 範本。

2.  使用下列 WMI 命令。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">WMI 命令</th>
    <th align="left">描述</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class UserSettings -Name ExportPackage -ArgumentList &lt;package name&gt;</code></p></td>
    <td align="left"><p>從套件檔案提取設定，並將其轉換成 XML 中的使用者可閱讀格式。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name RebuildIndex</code></p></td>
    <td align="left"><p>修復 UE-V 設定位置範本的索引。 必須以系統管理員身分執行。</p></td>
    </tr>
    </tbody>
    </table>



~~~
**Got a suggestion for UE-V**? Add or vote on suggestions [here](http://uev.uservoice.com/forums/280428-microsoft-user-experience-virtualization). **Got a UE-V issue**? Use the [UE-V TechNet Forum](https://social.technet.microsoft.com/Forums/home?forum=mdopuev).
~~~

## 相關主題


[使用 Windows PowerShell 和 WMI 管理 UE-V 2. x](administering-ue-v-2x-with-windows-powershell-and-wmi-both-uevv2.md)

[管理 UE-V 2。](administering-ue-v-2x-new-uevv2.md)









