---
title: 使用 PowerShell 與 WMI 來管理 UE-V 1.0 Agent 與套件
description: 使用 PowerShell 與 WMI 來管理 UE-V 1.0 Agent 與套件
author: dansimp
ms.assetid: c8989b01-1769-4e69-82b1-4aadb261d2d5
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: 79268e3384aaaf08bdd4e9b92d74b039ce96596a
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10802161"
---
# 使用 PowerShell 與 WMI 來管理 UE-V 1.0 Agent 與套件


您可以使用 WMI 和 PowerShell 來管理 Microsoft 使用者體驗虛擬化（UE-V） Agent 設定和同步處理行為。

**如何使用 PowerShell 部署 UE-V agent**

1.  在易於存取的網路共用中階段進行 UE-V 安裝程式檔案。

    **注意**  
    使用 AgentSetup.exe 來部署32位與64位的 UE-V Agent 版本。 Windows Installer 檔案版本、AgentSetupx86.msi 和 AgentSetupx64.msi，都可供每個架構使用。 若要在稍後使用安裝檔來卸載 UE-V Agent，您必須使用相同的檔案類型。



2.  使用下列其中一個 PowerShell 命令來安裝代理程式。

    `& AgentSetup.exe /quiet /norestart /log "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

    `& msiexec.exe /i "<path to msi file>" /quiet /norestart /l*v "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

**如何使用 PowerShell 設定 UE-V Agent**

1.  使用具有系統管理員許可權的帳戶來開啟 PowerShell 視窗。 使用下列命令匯入 UE-V PowerShell 模組。

    ``` syntax
    Import-module UEV
    ```

2.  使用下列 PowerShell 命令來設定代理程式。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong>PowerShell 命令</strong></p></td>
    <td align="left"><p><strong>描述</strong></p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>UevConfiguration</p>
    <p></p></td>
    <td align="left"><p>查看有效的 UE-V agent 設定。 [使用者專用] 設定的優先順序高於 [電腦設定]。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>UevConfiguration-CurrentComputerUser</p>
    <p></p></td>
    <td align="left"><p>僅針對目前的使用者，查看 UE-V agent 設定值。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>UevConfiguration-電腦</p></td>
    <td align="left"><p>針對電腦上的所有使用者，查看 UE-V agent 設定的值。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>UevConfiguration-電腦-SettingsStoragePath &lt; 路徑至 _settings_storage_location&gt;</p></td>
    <td align="left"><p>定義每個電腦的設定儲存位置。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>UevConfiguration-CurrentComputerUser-SettingsStoragePath &lt; 路徑至 _settings_storage_location&gt;</p></td>
    <td align="left"><p>定義每個使用者的設定儲存位置。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>Set-UevConfiguration-電腦-SyncTimeoutInMilliseconds &lt; 超時（毫秒）&gt;</p></td>
    <td align="left"><p>設定同步處理超時值（以毫秒為單位）</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>UevConfiguration-CurrentComputerUser-SyncTimeoutInMilliseconds 超時（ &lt; 以毫秒為單位）&gt;</p></td>
    <td align="left"><p>設定目前使用者的同步處理超時。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>UevConfiguration-電腦-MaxPackageSizeInBytes 大小（ &lt; 以位元組為單位）&gt;</p></td>
    <td align="left"><p>設定 UE-V agent 在設定套件檔案大小達到已定義的閾值時進行報告。 設定閥值套件大小（以位元組為單位）。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>UevConfiguration-CurrentComputerUser-MaxPackageSizeInBytes 大小（ &lt; 以位元組為單位）&gt;</p></td>
    <td align="left"><p>設定目前使用者的套件大小警告閾值。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>UevConfiguration –電腦– SettingsTemplateCatalogPath &lt; 路徑至目錄&gt;</p></td>
    <td align="left"><p>設定 [設定] 範本的目錄路徑。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>UevConfiguration-電腦-SyncMethod 同步處理 &lt; 方法&gt;</p></td>
    <td align="left"><p>設定同步處理方法： [OfflineFiles] 或 [無]。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>UevConfiguration-CurrentComputerUser-SyncMethod 同步處理 &lt; 方法&gt;</p></td>
    <td align="left"><p>為目前的使用者設定同步處理方法： OfflineFiles 或 [無]。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>UEVConfiguration-電腦– EnableSettingsImportNotify</p></td>
    <td align="left"><p>當使用者的 [匯入] 設定延遲時，啟用通知。</p>
    <p>使用– DisableSettingsImportNotify 停用通知。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>Set-UEVConfiguration-CurrentComputerUser-EnableSettingsImportNotify</p></td>
    <td align="left"><p>當使用者的 [匯入] 設定為延遲時，啟用目前使用者的通知。</p>
    <p>使用– DisableSettingsImportNotify 停用通知。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>UEVConfiguration-電腦-SettingsImportNotifyDelayInSeconds</p></td>
    <td align="left"><p>指定通知使用者前的時間（以秒為單位）</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>Set-UEVConfiguration-CurrentComputerUser-SettingsImportNotifyDelayInSeconds</p></td>
    <td align="left"><p>指定目前使用者的通知前的時間（以秒為單位）。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>UevConfiguration –電腦– DisableSync</p></td>
    <td align="left"><p>針對電腦上的所有使用者停用 UE-V。</p>
    <p>使用– EnableSync 以啟用或重新啟用。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>UevConfiguration – CurrentComputerUser-DisableSync</p></td>
    <td align="left"><p>針對電腦上的目前使用者停用 UE-V。</p>
    <p>使用– EnableSync 以啟用或重新啟用。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>UevConfiguration –電腦 &lt; 設定名稱&gt;</p></td>
    <td align="left"><p>針對電腦上的所有使用者，清除特定設定。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>UevConfiguration – CurrentComputerUser- &lt; 設定名稱&gt;</p></td>
    <td align="left"><p>請清除目前使用者的特定設定。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Export-UevConfiguration &lt; 設定遷移檔&gt;</p></td>
    <td align="left"><p>將 UE-V 電腦設定匯出至設定遷移檔案。 檔案副檔名必須是 ". uev"。</p>
    <p>Export Cmdlet 會匯出所有可使用-電腦參數設定的 UE-V agent 設定。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>匯入-UevConfiguration &lt; 設定遷移檔&gt;</p></td>
    <td align="left"><p>從設定遷移檔案（uev 檔案）匯入 UE-V 電腦設定。</p></td>
    </tr>
    </tbody>
    </table>



**如何使用 PowerShell 匯出 UE-V 封裝設定及修復 UE-V 範本**

1.  以系統管理員身分開啟 PowerShell 視窗。 使用下列命令匯入 UE-V PowerShell 模組。

    ``` syntax
    Import-module UEV
    ```

2.  使用下列 PowerShell 命令來設定代理程式。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <tbody>
    <tr class="odd">
    <td align="left"><p><strong>PowerShell 命令</strong></p></td>
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



**如何設定 UE-V Agent 與 WMI**

1.  使用者體驗虛擬化提供下列一組 WMI 命令。 系統管理員可以使用此介面，從命令列設定 UE-V agent，並自動執行一般的配置工作。

    使用具有系統管理員許可權的帳戶來開啟 PowerShell 視窗。

2.  使用下列 WMI 命令來設定代理程式。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left">PowerShell 命令</th>
    <th align="left">描述</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>WmiObject-命名空間 root\Microsoft\UEV 設定</p>
    <p></p></td>
    <td align="left"><p>查看活動的 UE-V agent 設定。 [使用者專用] 設定的優先順序高於 [電腦設定]。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>WmiObject-Namespace root\Microsoft\UEV UserConfiguration</p></td>
    <td align="left"><p>查看為使用者定義的 UE-V agent 設定。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>WmiObject-Namespace root\Microsoft\UEV ComputerConfiguration</p></td>
    <td align="left"><p>查看為電腦定義的 UE-V agent 設定。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>$config = WmiObject-Namespace root\Microsoft\UEV ComputerConfiguration</p>
    <p>$config]。SettingsStoragePath = &lt; path_to_settings_storage_location&gt;</p>
    <p>$config]。Put （）</p></td>
    <td align="left"><p>定義每個電腦的設定儲存位置。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>$config = WmiObject-Namespace root\Microsoft\UEV UserConfiguration</p>
    <p>$config]。SettingsStoragePath = &lt; path_to_settings_storage_location&gt;</p>
    <p>$config]。Put （）</p></td>
    <td align="left"><p>定義每個使用者的設定儲存位置。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>$config = WmiObject-Namespace root\Microsoft\UEV ComputerConfiguration</p>
    <p>$config]。SyncTimeoutInMilliseconds = &lt; timeout_in_milliseconds&gt;</p>
    <p>$config]。Put （）</p></td>
    <td align="left"><p>設定同步處理超時（以毫秒為單位）。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>$config = WmiObject-Namespace root\Microsoft\UEV ComputerConfiguration</p>
    <p>$config]。MaxPackageSizeInBytes = &lt; size_in_bytes&gt;</p>
    <p>$config]。Put （）</p></td>
    <td align="left"><p>設定 UE-V agent 在設定套件檔案大小達到已定義的閾值時進行報告。 設定閾值套件檔案大小（以位元組為單位）。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>$config = WmiObject-Namespace root\Microsoft\UEV ComputerConfiguration</p>
    <p>$config]。SyncMethod = &lt; sync_method&gt;</p>
    <p>$config]。Put （）</p></td>
    <td align="left"><p>設定同步處理方法： [OfflineFiles] 或 [無]。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>$config = WmiObject-Namespace root\Microsoft\UEV ComputerConfiguration</p>
    <p>$config]。 &lt;設定名稱 &gt;  =  &lt; 設定值&gt;</p>
    <p>$config]。Put （）</p></td>
    <td align="left"><p>更新特定的每電腦設定。 若要清除此設定，請使用 $null 做為設定值。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>$config = WmiObject-Namespace root\Microsoft\UEV ComputerConfiguration</p>
    <p>$config]。 &lt;設定名稱 &gt;  =  &lt; 設定值&gt;</p>
    <p>$config]。Put （）</p></td>
    <td align="left"><p>更新特定的每個使用者設定。 若要清除此設定，請使用 $null 做為設定值。</p></td>
    </tr>
    </tbody>
    </table>



~~~
Upon configuration of the UE-V Agent with WMI and PowerShell, the defined configuration is stored in the registry in the following locations:

`\HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\UEV\Agent\Configuration`

`\HKEY_CURRENT_USER\SOFTWARE\Microsoft\UEV\Agent\Configuration`
~~~

## 相關主題


[管理 UE-V 1.0](administering-ue-v-10.md)

[UE-V 1.0 作業](operations-for-ue-v-10.md)









