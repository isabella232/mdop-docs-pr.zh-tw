---
title: 使用 PowerShell 與 WMI 來管理 UE-V 1.0 設定位置範本
description: 使用 PowerShell 與 WMI 來管理 UE-V 1.0 設定位置範本
author: dansimp
ms.assetid: 4b911c78-a5e9-4199-bfeb-72ab764d47c1
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 06/16/2016
ms.openlocfilehash: d8dab0997cdfaf7c96862fcce4bc012c3edfe0c0
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800107"
---
# 使用 PowerShell 與 WMI 來管理 UE-V 1.0 設定位置範本


Microsoft 使用者體驗虛擬化（UE-V）使用設定位置範本（XML 檔案），定義使用者體驗虛擬化所捕獲並套用的設定。 UE-V 包含一組標準設定位置範本。 它也包含 UE-V 發生器工具，可讓您建立自訂設定位置範本。 在您建立並部署設定位置範本之後，您可以使用 PowerShell 或 WMI 管理這些範本。

## 使用 WMI 和 PowerShell 管理設定位置範本


UE-V 的 WMI 和 PowerShell 功能包括啟用、停用、註冊、更新及登出設定位置範本的功能。 您可以使用這些功能，透過 UE-V agent 程式來自動註冊、更新或登出範本。 您也可以使用 WMI 和 PowerShell 命令，手動註冊範本。 透過將這些功能與電子軟體發佈方案、群組原則或其他自動部署方法（例如腳本）搭配使用，您就可以進一步自動化該程式。

您必須具備系統管理員許可權，才能更新、註冊或登出設定位置範本。 啟用或停用範本不需要系統管理員許可權。

**使用 PowerShell 管理設定位置範本**

1.  使用具有系統管理員許可權的帳戶來開啟 Windows PowerShell 視窗。 若要匯入**MICROSOFT Ue-v PowerShell**模組，請在 PowerShell 命令提示字元中輸入下列命令。

    ``` syntax
    Import-module UEV
    ```

2.  使用下列 PowerShell Cmdlet 來註冊及管理 UE-V 設定位置範本。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><strong>PowerShell 命令</strong></th>
    <th align="left"><strong>描述</strong></th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p>UevTemplate</p></td>
    <td align="left"><p>列出電腦上已註冊的所有設定位置範本。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Register-UevTemplate</p></td>
    <td align="left"><p>使用 UE-V 註冊設定位置範本。 範本註冊之後，UE-V 會同步處理在已註冊範本的電腦之間，在範本中定義的設定。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>取消註冊-UevTemplate</p></td>
    <td align="left"><p>使用 UE-V 登出 [設定位置] 範本。 範本取消註冊之後，UE-V 就不會再同步處理在電腦之間的範本中定義的設定。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>更新-UevTemplate</p></td>
    <td align="left"><p>使用最新版本的範本更新設定位置範本。 新範本的版本必須晚于現有範本。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>Disable-UevTemplate</p></td>
    <td align="left"><p>停用電腦目前使用者的設定位置範本。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>Enable-UevTemplate</p></td>
    <td align="left"><p>啟用電腦目前使用者的設定位置範本。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>Test-UevTemplate</p></td>
    <td align="left"><p>判斷指定設定位置範本是否符合其 XML 架構。</p></td>
    </tr>
    </tbody>
    </table>

     

UE-V PowerShell 功能可讓您管理企業中部署的一組設定範本。 若要使用 PowerShell 管理範本群組，請執行下列動作。

**使用 PowerShell 管理設定位置範本群組**

1.  修改或更新所需的設定位置範本。

2.  將所需的設定位置範本部署到本機電腦可存取的資料夾。

3.  在本機電腦上，以系統管理員許可權開啟 Windows PowerShell 視窗。

4.  若要匯入 Microsoft UE-V PowerShell 模組，請輸入下列命令。

    ``` syntax
    Import-module UEV
    ```

5.  輸入下列命令，以取消註冊所有先前已註冊的範本版本。

    ``` syntax
    Get-UevTemplate | Unregister-UevTemplate
    ```

    這將會登出電腦上的所有活動範本。

6.  輸入下列命令來註冊更新的範本。

    ``` syntax
    Register-UevTemplate <path to template folder>\*.xml
    ```

    這會註冊位於指定範本資料夾中的所有設定位置範本。

使用者體驗虛擬化提供下列一組 WMI 命令。 系統管理員可以使用這些介面，從 Windows PowerShell 管理設定位置範本，並自動執行範本管理工作。

**使用 WMI 管理設定位置範本**

1.  使用具有系統管理員許可權的帳戶來開啟 Windows PowerShell 視窗。

2.  使用下列 WMI 命令來註冊及管理 UE-V 設定位置範本。

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
    <td align="left"><p>WmiObject-Namespace root\Microsoft\UEV SettingsLocationTemplate |選取-Object TemplateId、TemplateName、TemplateVersion、Enabled |[格式]-[表格自動調整]</p></td>
    <td align="left"><p>列出電腦已註冊的所有設定位置範本。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>WmiMethod-命名空間 root\Microsoft\UEV-Class SettingsLocationTemplate-Name Register-ArgumentList &lt; 範本路徑&gt;</p></td>
    <td align="left"><p>使用 UE-V 註冊設定位置範本。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>WmiMethod-命名空間 root\Microsoft\UEV-Class SettingsLocationTemplate-Name UnregisterByTemplateId-ArgumentList &lt; 範本識別碼&gt;</p></td>
    <td align="left"><p>使用 UE-V 登出 [設定位置] 範本。 範本取消註冊之後，UE-V 就不會再同步處理在電腦之間的範本中定義的設定。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>WmiMethod-命名空間 root\Microsoft\UEV-Class SettingsLocationTemplate-Name EnableByTemplateId-ArgumentList &lt; 範本識別碼&gt;</p></td>
    <td align="left"><p>使用 UE-V 啟用設定位置範本</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>WmiMethod-命名空間 root\Microsoft\UEV-Class SettingsLocationTemplate-Name DisableByTemplateId-ArgumentList &lt; 範本識別碼&gt;</p></td>
    <td align="left"><p>使用 UE-V 停用設定位置範本</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p>WmiMethod-命名空間 root\Microsoft\UEV-類別 SettingsLocationTemplate-名稱更新-ArgumentList &lt; 範本路徑&gt;</p></td>
    <td align="left"><p>使用 UE-V 更新設定位置範本。 新範本的版本必須高於現有範本。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>WmiMethod-命名空間 root\Microsoft\UEV-Class SettingsLocationTemplate-Name 驗證-ArgumentList &lt; 範本路徑&gt;</p></td>
    <td align="left"><p>判斷指定設定位置範本是否符合其 XML 架構。</p></td>
    </tr>
    </tbody>
    </table>

     

**如何使用 PowerShell 部署 UE-V agent**

1.  在易於存取的網路共用中階段進行 UE-V 安裝程式檔案。

    **記事** 使用 AgentSetup.exe 來部署32位與64位的 UE-V Agent 版本。 Windows Installer 檔案版本、AgentSetupx86.msi 和 AgentSetupx64.msi，都可供每個架構使用。 若要在稍後使用安裝檔來卸載 UE-V Agent，您必須使用相同的檔案類型。

     

2.  使用下列其中一個 PowerShell 命令來安裝代理程式。

    `& AgentSetup.exe /quiet /norestart /log "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

    `& msiexec.exe /i "<path to msi file>" /quiet /norestart /l*v "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

## 相關主題


[使用 PowerShell 與 WMI 來管理 UE-V 1.0 Agent 與套件](managing-the-ue-v-10-agent-and-packages-with-powershell-and-wmi.md)

[管理 UE-V 1.0](administering-ue-v-10.md)

[UE-V 1.0 作業](operations-for-ue-v-10.md)

 

 





