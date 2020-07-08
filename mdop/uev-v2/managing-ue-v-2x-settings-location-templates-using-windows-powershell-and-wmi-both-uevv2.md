---
title: 使用 Windows PowerShell 和 WMI 管理 UE-V a.x 設定位置範本
description: 使用 Windows PowerShell 和 WMI 管理 UE-V a.x 設定位置範本
author: dansimp
ms.assetid: b5253050-acc3-4274-90d0-1fa4c480331d
ms.reviewer: ''
manager: dansimp
ms.author: dansimp
ms.pagetype: mdop, virtualization
ms.mktglfcycl: deploy
ms.sitesec: library
ms.prod: w10
ms.date: 08/30/2016
ms.openlocfilehash: 9788ff1a11f1c70e52b75dd2187a198f5472f77f
ms.sourcegitcommit: 354664bc527d93f80687cd2eba70d1eea024c7c3
ms.translationtype: MT
ms.contentlocale: zh-TW
ms.lasthandoff: 06/26/2020
ms.locfileid: "10800204"
---
# 使用 Windows PowerShell 和 WMI 管理 UE-V a.x 設定位置範本


Microsoft 使用者體驗虛擬化（UE-V）2.0、2.1 和 2.1 SP1 使用 XML 設定位置範本來定義使用者體驗虛擬化捕獲並套用的設定。 UE-V 包含一組標準設定位置範本。 它也包含 UE-V 發生器工具，可讓您建立自訂設定位置範本。 在您建立並部署設定位置範本之後，您可以使用 Windows PowerShell 和 Windows 管理工具（WMI）管理這些範本。 如需 UE-V PowerShell Cmdlet 的完整清單，請參閱[ue-v 2 Cmdlet 參考](https://go.microsoft.com/fwlink/p/?LinkId=393495)（ https://go.microsoft.com/fwlink/p/?LinkId=393495) 。

## 使用 Windows PowerShell 管理 UE-V 2 設定位置範本


UE-V 的 WMI 和 Windows PowerShell 功能包括啟用、停用、註冊、更新及登出設定位置範本的功能。 您可以使用這些功能，透過 UE-V Agent 程式來自動註冊、更新或登出範本。 您也可以使用 WMI 和 Windows PowerShell 命令，手動註冊範本。 透過將這些功能與電子軟體發佈方案、群組原則或其他自動部署方法（例如腳本）搭配使用，您就可以進一步自動化該程式。

您必須具備系統管理員許可權，才能更新、註冊或登出設定位置範本。 [啟用]、[停用] 或 [清單] 範本不需要系統管理員許可權。

***<em>使用 Windows PowerShell 管理設定位置範本ell</em>***

1.  使用具有系統管理員許可權的帳戶來開啟 Windows PowerShell 命令提示字元。

2.  使用下列 Windows PowerShell Cmdlet 來註冊及管理 UE-V 設定位置範本。

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
    <td align="left"><p><code>Get-UevTemplate</code></p></td>
    <td align="left"><p>列出電腦上已註冊的所有設定位置範本。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Get-UevTemplate –Application &lt;string&gt;</code></p></td>
    <td align="left"><p>列出電腦上已登錄且應用程式名稱或範本名稱包含字串的所有設定位置範本 &lt; &gt; 。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Get-UevTemplate –TemplateID &lt;string&gt;</code></p></td>
    <td align="left"><p>列出已在電腦上登錄且範本識別碼包含字串的所有設定位置範本 &lt; &gt; 。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Get-UevTemplate [-ApplicationOrTemplateID] &lt;string&gt;</code></p></td>
    <td align="left"><p>列出在電腦上註冊的所有設定位置範本，或範本識別碼包含字串的電腦 &lt; &gt; 。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Get-UevTemplateProgram [-ID] &lt;template ID&gt;</code></p></td>
    <td align="left"><p>取得程式與版本資訊的名稱，這取決於範本識別碼。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Get-UevAppXPackage</code></p></td>
    <td align="left"><p>取得有效的 Windows app 清單。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Get-UevAppXPackage -Computer</code></p></td>
    <td align="left"><p>取得為電腦設定的 Windows app 清單。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Get-UevAppXPackage -CurrentComputerUser</code></p></td>
    <td align="left"><p>取得為目前使用者設定的 Windows app 清單。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Register-UevTemplate [-Path] &lt;template file path&gt;[,&lt;template file path&gt;]</code></p></td>
    <td align="left"><p>在檔路徑中使用相對路徑和/或萬用字元，以 UE-V 註冊一或多個設定位置範本。 範本註冊之後，UE-V 會同步處理範本中定義的設定，這些設定是在已註冊範本的電腦之間進行。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Register-UevTemplate –LiteralPath &lt;template file path&gt;[,&lt;template file path&gt;]</code></p></td>
    <td align="left"><p>使用文字路徑登錄一個或多個設定位置範本，其中不能將任何字元轉譯成萬用字元字元。 範本註冊之後，UE-V 會同步處理範本中定義的設定，這些設定是在已註冊範本的電腦之間進行。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Unregister-UevTemplate [-ID] &lt;template ID&gt;</code></p></td>
    <td align="left"><p>使用 UE-V 登出 [設定位置] 範本。 取消註冊範本後，UE-V 就不會再同步處理在電腦之間的範本中定義的設定。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Unregister-UevTemplate -All</code></p></td>
    <td align="left"><p>使用 UE-V 登出所有設定位置範本。 取消註冊範本後，UE-V 就不會再同步處理在電腦之間的範本中定義的設定。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Update-UevTemplate [-Path] &lt;template file path&gt;[,&lt;template file path&gt;]</code></p></td>
    <td align="left"><p>使用最新版本的範本更新一或多個設定位置範本。 在檔路徑中使用相對路徑和/或萬用字元。 新範本的版本必須比現有範本更新。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Update-UevTemplate –LiteralPath &lt;template file path&gt;[,&lt;template file path&gt;]</code></p></td>
    <td align="left"><p>使用最新版本的範本更新一或多個設定位置範本。 使用完整路徑至範本檔案，其中不能將任何字元轉譯成萬用字元字元。 新範本的版本必須比現有範本更新。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Clear-UevAppXPackage –Computer [-PackageFamilyName] &lt;package family name&gt;[,&lt;package family name&gt;]</code></p></td>
    <td align="left"><p>從電腦 Windows app 清單移除一或多個 Windows 應用程式。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Clear-UevAppXPackage -CurrentComputerUser</code></p></td>
    <td align="left"><p>從目前使用者的 Windows 應用程式清單移除 Windows 應用程式。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Clear-UevAppXPackage –Computer -All</code></p></td>
    <td align="left"><p>從電腦 Windows app 清單移除所有 Windows 應用程式。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Clear-UevAppXPackage [–CurrentComputerUser] [-PackageFamilyName] &lt;package family name&gt;[,&lt;package family name&gt;]</code></p></td>
    <td align="left"><p>從目前使用者的 Windows 應用程式清單移除一或多個 Windows 應用程式。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Clear-UevAppXPackage [–CurrentComputerUser] -All</code></p></td>
    <td align="left"><p>從目前使用者的 Windows 應用程式清單移除所有 Windows 應用程式。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Disable-UevTemplate [-ID] &lt;template ID&gt;</code></p></td>
    <td align="left"><p>停用電腦目前使用者的設定位置範本。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Disable-UevAppXPackage –Computer [-PackageFamilyName] &lt;package family name&gt;[,&lt;package family name&gt;]</code></p></td>
    <td align="left"><p>停用電腦視窗 app 清單中的一個或多個 Windows 應用程式。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Disable-UevAppXPackage [–CurrentComputerUser] [-PackageFamilyName] &lt;package family name&gt;[,&lt;package family name&gt;]</code></p></td>
    <td align="left"><p>停用目前使用者 Windows 應用程式清單中的一個或多個 Windows 應用程式。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Enable-UevTemplate [-ID] &lt;template ID&gt;</code></p></td>
    <td align="left"><p>啟用電腦目前使用者的設定位置範本。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Enable-UevAppXPackage –Computer [-PackageFamilyName] &lt;package family name&gt;[,&lt;package family name&gt;]</code></p></td>
    <td align="left"><p>啟用電腦 Windows 應用程式清單中的一個或多個 Windows 應用程式。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Enable-UevAppXPackage [–CurrentComputerUser] [-PackageFamilyName] &lt;package family name&gt;[,&lt;package family name&gt;]</code></p></td>
    <td align="left"><p>在目前的使用者 Windows 應用程式清單中啟用一個或多個 Windows 應用程式。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Test-UevTemplate [-Path] &lt;template file path&gt;[,&lt;template file path&gt;]</code></p></td>
    <td align="left"><p>判斷一個或多個設定位置範本是否符合其 XML 架構。 可以使用相對路徑和萬用字元。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Test-UevTemplate –LiteralPath &lt;template file path&gt;[,&lt;template file path&gt;]</code></p></td>
    <td align="left"><p>判斷一個或多個設定位置範本是否符合其 XML 架構。 路徑必須是範本檔案的完整路徑，但不會包含萬用字元字元。</p></td>
    </tr>
    </tbody>
    </table>



UE-V Windows PowerShell 功能可讓您管理企業中部署的一組設定範本。 使用下列程式，使用 Windows PowerShell 來管理一組範本。

**使用 Windows PowerShell 管理設定位置範本群組**

1.  修改或更新所需的設定位置範本。

2.  如果您想要修改或更新設定位置範本，請將這些設定位置範本部署到本機電腦無法存取的資料夾中。

3.  在本機電腦上，以系統管理員許可權開啟 Windows PowerShell 視窗。

4.  輸入下列命令，以取消註冊所有先前已註冊的範本版本。

    ``` syntax
    Unregister-UevTemplate -All
    ```

    這個命令會登出電腦上所有的活動範本。

5.  輸入下列命令來註冊更新的範本。

    ``` syntax
    Register-UevTemplate <path to template folder>\*.xml
    ```

    這個命令會註冊位於指定範本資料夾中的所有設定位置範本。

### <a href="" id="win8applist"></a>Windows 應用程式清單

在 Windows 應用程式清單中列出 Windows 應用程式，即可指定是否已啟用或停用應用程式的設定同步處理。 應用程式會依其套件系列名稱在清單中加以識別，以及該 app 是否應該啟用或停用設定同步處理。 當您使用這些設定以及未列出的預設同步處理行為設定時，您可以控制是否已同步處理 Windows 應用程式。

若要顯示已安裝的 Windows 應用程式套件系列名稱，請在 Windows PowerShell 命令提示字元輸入：

``` syntax
Get-AppxPackage | Sort-Object PackageFamilyName | Format-Table PackageFamilyName
```

若要在 Windows PowerShell 命令提示字元上顯示可同步處理電腦設定的 Windows app 清單，以及其套件系列名稱、啟用狀態，以及已啟用的來源，請輸入： `Get-UevAppxPackage`

**UevAppxPackage 屬性的定義**

<a href="" id="displayname"></a>**DisplayName**  
在 [公司設定中心] 應用程式中顯示給使用者的名稱。 `DisplayName`屬性衍生自 `PackageFamilyName` 屬性。

<a href="" id="packagefamilyname"></a>**PackageFamilyName**  
為目前使用者安裝的套件名稱。

<a href="" id="enabled"></a>**啟用**  
定義應用程式的設定是否設定為同步處理。

<a href="" id="enabledsource"></a>**EnabledSource**  
啟用或停用 app 之設定的位置。 可能的值為： *NotSet*、 *LocalMachine*、 *LocalUser*、 *PolicyMachine*和*PolicyUser*。

<a href="" id="notset"></a>**NotSet**  
未將原則設定為同步處理此應用程式。

<a href="" id="localmachine"></a>**My**  
[啟用] 狀態是在註冊表的 [本機電腦] 區段中設定。

<a href="" id="localuser"></a>**LocalUser**  
[啟用] 狀態是在登錄的 [目前使用者] 區段中設定。

<a href="" id="policymachine"></a>**PolicyMachine**  
[啟用] 狀態是在註冊表的 [本機電腦] 區段的 [原則] 區段中設定。

若要取得使用者設定的 Windows 應用程式清單，請在 Windows PowerShell 命令提示字元輸入： `Get-UevAppxPackage –CurrentComputerUser`

若要取得電腦設定的 Windows 應用程式清單，請在 Windows PowerShell 命令提示字元輸入： `Get-UevAppxPackage –Computer`

無論是參數、CurrentComputerUser 或電腦，此 Cmdlet 都會傳回在使用者或電腦層級設定的 Windows app 清單。

**屬性的定義**

<a href="" id="displayname"></a>**DisplayName**  
在 [公司設定中心] 應用程式中顯示給使用者的名稱。 `DisplayName`屬性衍生自 `PackageFamilyName` 屬性。

<a href="" id="packagefamilyname"></a>**PackageFamilyName**  
為目前使用者安裝的套件名稱。

<a href="" id="enabled"></a>**啟用**  
定義應用程式的設定是否已設定為針對指定的交換器（也就是**使用者**或**電腦**）進行同步處理。

<a href="" id="installed"></a>**已安裝**  
如果應用程式是針對目前的使用者安裝 PackageFamilyName，則為 True。

### 使用 WMI 管理 UE-V 2 設定位置範本

使用者體驗虛擬化提供下列一組 WMI 命令。 系統管理員可以使用這些介面，從 Windows PowerShell 管理設定位置範本，並自動執行範本管理工作。

**使用 WMI 管理設定位置範本**

1.  使用具有系統管理員許可權的帳戶來開啟 Windows PowerShell 視窗。

2.  使用下列 WMI 命令來註冊及管理 UE-V 設定位置範本。

    <table>
    <colgroup>
    <col width="50%" />
    <col width="50%" />
    </colgroup>
    <thead>
    <tr class="header">
    <th align="left"><code>                         Windows PowerShell command</code></th>
    <th align="left">描述</th>
    </tr>
    </thead>
    <tbody>
    <tr class="odd">
    <td align="left"><p><code>Get-WmiObject -Namespace root\Microsoft\UEV SettingsLocationTemplate | Select-Object TemplateId,TemplateName, TemplateVersion,Enabled | Format-Table -Autosize</code></p></td>
    <td align="left"><p>列出已針對電腦註冊的所有設定位置範本。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod –Namespace root\Microsoft\UEV –Class SettingsLocationTemplate –Name GetProcessInfoByTemplateId &lt;template Id&gt;</code></p></td>
    <td align="left"><p>取得程式與版本資訊的名稱，這取決於範本名稱。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Get-WmiObject -Namespace root\Microsoft\UEV EffectiveWindows8App</code></p></td>
    <td align="left"><p>取得有效的 Windows app 清單。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p>WmiObject-Namespace root\Microsoft\UEV MachineConfiguredWindows8App</p></td>
    <td align="left"><p>取得為電腦設定的 Windows app 清單。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Get-WmiObject -Namespace root\Microsoft\UEV UserConfiguredWindows8App</code></p></td>
    <td align="left"><p>取得為目前使用者設定的 Windows app 清單。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name Register -ArgumentList &lt;template path &gt;</code></p></td>
    <td align="left"><p>使用 UE-V 註冊設定位置範本。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name UnregisterByTemplateId -ArgumentList &lt;template ID&gt;</code></p></td>
    <td align="left"><p>使用 UE-V 登出 [設定位置] 範本。 範本取消註冊之後，UE-V 就不會再同步處理在電腦之間的範本中定義的設定。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name Update -ArgumentList &lt;template path&gt;</code></p></td>
    <td align="left"><p>使用 UE-V 更新設定位置範本。 新範本的版本必須比現有範本更新。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class MachineConfiguredWindows8App -Name RemoveApp -ArgumentList &lt;package family name | package family name&gt;</code></p></td>
    <td align="left"><p>從電腦 Windows app 清單移除一或多個 Windows 應用程式。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class UserConfiguredWindows8App -Name RemoveApp -ArgumentList &lt;package family name | package family name&gt;</code></p></td>
    <td align="left"><p>從目前使用者的 Windows 應用程式清單移除一或多個 Windows 應用程式。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name DisableByTemplateId -ArgumentList &lt;template ID&gt;</code></p></td>
    <td align="left"><p>使用 UE-V 停用一或多個設定位置範本。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class MachineConfiguredWindows8App -Name DisableApp -ArgumentList &lt;package family name | package family name&gt;</code></p></td>
    <td align="left"><p>停用電腦視窗 app 清單中的一個或多個 Windows 應用程式。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class UserConfiguredWindows8App -Name DisableApp -ArgumentList &lt;package family name | package family name&gt;</code></p></td>
    <td align="left"><p>停用目前使用者 Windows 應用程式清單中的一個或多個 Windows 應用程式。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name EnableByTemplateId -ArgumentList &lt;template ID&gt;</code></p></td>
    <td align="left"><p>使用 UE-V 啟用 [設定位置] 範本。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class MachineConfiguredWindows8App -Name EnableApp -ArgumentList &lt;package family name | package family name&gt;</code></p></td>
    <td align="left"><p>啟用電腦 Windows 應用程式清單中的 Windows 應用程式。</p></td>
    </tr>
    <tr class="even">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class UserConfiguredWindows8App -Name EnableApp -ArgumentList &lt;package family name | package family name&gt;</code></p></td>
    <td align="left"><p>啟用目前使用者的 windows 應用程式清單中的 Windows 應用程式。</p></td>
    </tr>
    <tr class="odd">
    <td align="left"><p><code>Invoke-WmiMethod -Namespace root\Microsoft\UEV -Class SettingsLocationTemplate -Name Validate -ArgumentList &lt;template path&gt;</code></p></td>
    <td align="left"><p>判斷指定設定位置範本是否符合其 XML 架構。</p></td>
    </tr>
    </tbody>
    </table>



~~~
**Note**  
Where a list of Package Family Names is called by the WMI command, the list must be in quotes and separated by a pipe symbol, for example, `"<package family name | package family name>"`.
~~~



### 使用 Windows PowerShell 部署 UE-V Agent

**如何使用 Windows PowerShell 部署 UE-V Agent**

1.  在易存取的網路共用中暫存 UE-V Agent 安裝套件。

    **注意**  
    使用 AgentSetup.exe 來部署32位與64位的 UE-V Agent 版本。 Windows Installer 套件、AgentSetupx86.msi 和 AgentSetupx64.msi，都可供每個架構使用。 若要在稍後使用安裝檔案卸載 UE-V Agent，您必須使用相同的檔案類型。



2.  使用下列其中一個 Windows PowerShell 命令來安裝 UE-V Agent。

    -   `& AgentSetup.exe /quiet /norestart /log "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

    -   `& msiexec.exe /i "<path to msi file>" /quiet /norestart /l*v "%temp%\UE-VAgentInstaller.log" SettingsStoragePath=\\server\settingsshare\%username%`

**為 ue-v 提供建議**嗎？ 在[此](http://uev.uservoice.com/forums/280428-microsoft-user-experience-virtualization)新增或投票建議。 是否**有 ue-v 問題**？ 使用[Ue-v TechNet 論壇](https://social.technet.microsoft.com/Forums/home?forum=mdopuev)。

## 相關主題


[使用 Windows PowerShell 和 WMI 管理 UE-V 2. x](administering-ue-v-2x-with-windows-powershell-and-wmi-both-uevv2.md)

[管理 UE-V 2。](administering-ue-v-2x-new-uevv2.md)









